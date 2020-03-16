---
title: Cambio sin conexión perfecto para operaciones con tarjetas regalo y notas de crédito
description: Este tema proporciona una descripción general de las mejoras que proporcionan un cambio sin conexión perfecto para tipos de pago específicos.
author: rubendel
manager: AnnBe
ms.date: 02/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 20120-02-28
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 3c2a644fd7096668fcefc73c67068fccde6894b0
ms.sourcegitcommit: 472f8bfc02acf80b07caf7c53bbb397411e946cc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "3040242"
---
# <a name="seamless-offline-switch-for-gift-card-and-credit-memo-operations"></a>Cambio sin conexión perfecto para operaciones con tarjetas regalo y notas de crédito

[!include [banner](../includes/banner.md)]

Si un dispositivo de punto de venta (PDV) pierde su conexión con la base de datos del canal, la mayoría de las operaciones y transacciones PDV que estaban en curso pueden continuar después de que el cajero recibe un mensaje de advertencia sobre la pérdida de conectividad. Sin embargo, en algunos casos, las transacciones tienen elementos que dependen del servicio en tiempo real, y esos elementos no son compatibles cuando el PDV está fuera de línea. Este tema describe algunas funcionalidades que ayudan a reducir el impacto de la conectividad perdida en estos escenarios.

## <a name="completing-gift-card-transactions-in-offline-mode"></a>Completar transacciones de tarjeta regalo en modo sin conexión

Las tarjetas de regalo internas dependen del servicio en tiempo real, porque el saldo de las tarjetas de regalo debe mantenerse centralmente en Microsoft Dynamics 365 Commerce Headquarters. Para ayudar a prevenir el fraude u otros problemas de sincronización, las tarjetas de regalo se bloquean tan pronto como se agregan a una transacción. La función de bloqueo asegura que una tarjeta regalo no se pueda usar en múltiples terminales al mismo tiempo. Una vez finalizada una transacción, la tarjeta regalo se actualiza y desbloquea automáticamente.

Sin embargo, si el PDV pierde conectividad después de agregar una tarjeta de regalo a una transacción, la tarjeta de regalo puede quedar inutilizable. Para ayudar a prevenir esta situación, Dynamics 365 Commerce tiene un parámetro que permite completar transacciones que incluyen una línea de tarjeta de regalo mientras el PDV está fuera de línea. Cuando este parámetro está activado, las transacciones de tarjetas de regalo que se fuerzan fuera de línea se guardarán junto con las transacciones fuera de línea, y se sincronizarán con Commerce Headquarters cuando se sincronicen las transacciones fuera de línea. La sincronización también desbloqueará la tarjeta de regalo para que pueda usarse en otra terminal.

Para habilitar la funcionalidad para concluir transacciones de tarjetas de regalo después de cambiar al modo fuera de línea, vaya a la pestaña **Registro** en la página **Parámetros de Commerce**. En esa pestaña, encuentre la ficha desplegable **Tarjeta regalo** y establezca **Permitir concluir transacciones de tarjetas de regalo en modo fuera de línea** a **Sí**.

![Configuración de tarjeta de regalo sin conexión](../media/gift.png)

Los parámetros de Commerce generalmente se almacenan en caché. Por lo tanto, una vez que se actualiza la configuración de este parámetro y se inicia la programación de distribución para sincronizar el cambio en el canal, el cambio puede tardar hasta 24 horas en surtir efecto. Para que el cambio entre en vigencia inmediatamente, reinicie los Servicios de Internet Information Server (IIS) de Microsoft.

## <a name="completing-credit-memo-transactions-in-offline-mode"></a>Completar transacciones de nota de crédito en modo sin conexión

Al igual que las tarjetas de regalo internas, las notas de crédito se mantienen centralmente en Commerce Headquarters. Commerce tiene un parámetro que permite completar las transacciones de notas de crédito mientras el PDV está fuera de línea. Este parámetro funciona como el parámetro de la tarjeta de regalo que se mencionó en la sección anterior. Cuando se activa el parámetro, las transacciones de notas de crédito que se fuerzan a desconectarse se sincronizarán con la base de datos del canal, junto con otras transacciones que se realizaron mientras el PDV estaba desconectado.

Para habilitar la funcionalidad para concluir transacciones de notas de crédito después de cambiar al modo fuera de línea, vaya a la pestaña **Registro** en la página **Parámetros de Commerce**. En esa pestaña, encuentre la ficha desplegable **Nota de crédito** y establezca **Permitir concluir transacciones de notas de crédito en modo fuera de línea** a **Sí**.

![Configuración de nota de crédito sin conexión](../media/creditmemo.png)

Los parámetros de Commerce generalmente se almacenan en caché. Por lo tanto, una vez que se actualiza la configuración de este parámetro y se inicia la programación de distribución para sincronizar el cambio en el canal, el cambio puede tardar hasta 24 horas en surtir efecto. Para que el cambio sea efectivo de inmediato, reinicie IIS.

## <a name="related-topics"></a>Temas relacionados

- [Funcionalidad sin conexión de punto de venta (PDV)](https://docs.microsoft.com/dynamics365/retail/pos-offline-functionality)
- [Operaciones de punto de venta (PDV) en línea y sin conexión](https://docs.microsoft.com/dynamics365/retail/pos-operations)
