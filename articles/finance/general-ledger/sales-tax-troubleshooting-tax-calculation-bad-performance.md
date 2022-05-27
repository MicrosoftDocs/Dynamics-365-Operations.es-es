---
title: El rendimiento del cálculo de impuestos afecta las transacciones
description: Este tema proporciona información de resolución de problemas relacionada con el rendimiento del cálculo de impuestos y su efecto en las transacciones.
author: shtao
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 1902017a7a00d4cc068f17e23aa21cd1d2b547a7
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8695229"
---
# <a name="tax-calculation-performance-affects-transactions"></a>El rendimiento del cálculo de impuestos afecta las transacciones

[!include [banner](../includes/banner.md)]

A veces, una transacción se ve afectada por problemas de rendimiento que tiene el cálculo de impuestos. Para solucionar este problema, siga los pasos de las siguientes secciones según sea necesario.

## <a name="review-the-transaction-line-count"></a>Revisar la cuenta de líneas de la transacción

Determine si la transacción tiene una gran cantidad de líneas (por ejemplo, más de varios cientos). Si no es así, pase a la siguiente sección. Si la transacción tiene varios cientos de líneas, retrase el cálculo de impuestos. Para más información, vea [Habilitar el cálculo de impuestos diferido en diarios](enable-delayed-tax-calculation.md). 

A continuación, puede determinar si se cumple alguna de las siguientes condiciones:

- Hay transacciones de importación de archivos grandes.
- Varias sesiones procesan el mismo cálculo de impuestos sobre transacciones al mismo tiempo.
- La transacción tiene varias líneas y las vistas se actualizan en tiempo real. Por ejemplo, el campo **Importe del impuesto calculado** en la página **Diario general** se actualiza en tiempo real cuando se cambian los campos de una línea.

   [![Campo de importe de impuesto calculado en la página de asientos de diario.](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)

Si se cumple alguna de estas condiciones, retrase el cálculo de impuestos.

## <a name="review-the-call-stack"></a>Revisar la pila de llamadas

Revise la pila de llamadas para determinar si se llama varias veces al cálculo de impuestos. Si no es así, pase a la siguiente sección. Si se llama a la pila de llamadas varias veces, siga estos pasos para ayudar a reducir los tiempos de cálculo de impuestos.

1. Si el diario ha considerado la transacción, retrase el cálculo de impuestos. Para más información, vea [Habilitar el cálculo de impuestos diferido en diarios](enable-delayed-tax-calculation.md).
2. Si la transacción es una orden de compra y la versión de la aplicación es posterior a 10.0.15, puede retrasar el cálculo de impuestos hasta el cálculo final habilitando la distribución para **PurchTableChangeMgmtDistributionUpdateOnToggle_KillSwitch**.

## <a name="review-the-call-stack-timeline"></a>Revisar la escala de tiempo de la pila de llamadas

Revise la línea de tiempo de la pila de llamadas para determinar si existen los siguientes problemas. Si existen, habilite los paquetes piloto para **TaxUncommittedDoIsolateScopeFlighting** para solucionar el problema.

- La transacción hace que el sistema deje de responder hasta que finalice la sesión. Por tanto, la transacción no puede calcular el resultado de impuestos. La siguiente ilustración muestra el cuadro de mensaje "Sesión finalizada" que recibe.

    [![Mensaje de sesión terminada.](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)

- Los métodos **TaxUncommitted** llevan más tiempo que otros métodos. Por ejemplo, en la siguiente ilustración, el método **TaxUncommitted::updateTaxUncommitted()** tarda 43.347,42 segundos, pero otros métodos tardan 0,09 segundos.

    [![Duraciones del método.](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)

## <a name="customizing-and-calling-tax-calculation"></a>Personalización y llamada al cálcuo de impuestos

Cuando personalice, no llame al cálculo de impuestos al **insertar()** o **actualizar()** el método para cada línea. El cálculo de impuestos debe llamarse a nivel de transacción.

## <a name="determine-whether-customization-exists"></a>Determinar si existe personalización

Si ha completado los pasos de las secciones anteriores pero no ha encontrado problemas, determine si existe personalización. Si no existe personalización, cree una solicitud de servicio de Microsoft para obtener más soporte.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
