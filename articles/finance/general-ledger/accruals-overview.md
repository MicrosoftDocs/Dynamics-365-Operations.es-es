---
title: Visión general de Acumulaciones
description: Este artículo describe acumulaciones y proporciona información acerca de cómo configurarlas y crear transacciones.
author: aprilolson
ms.date: 11/21/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerAccuralTable
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "14131"
- intro-internal
ms.assetid: 0489b59a-37a7-4a78-87bf-4b597e9efad9
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 022d6574895d3263ce1e21a2f04985c418f45b61
ms.sourcegitcommit: fb9b6969218f2b82f0a4c72bfad75387fe00395c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2022
ms.locfileid: "9799416"
---
# <a name="accruals-overview"></a>Visión general de Acumulaciones

[!include [banner](../includes/banner.md)]

Este artículo describe acumulaciones y proporciona información acerca de cómo configurarlas y crear transacciones.

Las acumulaciones se usan en la contabilidad por devengo para realizar un seguimiento de los ingresos que se reconoce en el período en que se ha obtenido, no cuando se recibe el pago, y para realizar un seguimiento de los gastos (costes) que se reconocen cuando se producen, no cuando se realiza el pago.

## <a name="accrual-schemes"></a>Esquemas de acumulación
Los esquemas de acumulación se usan para configurar los costes y los ingresos diferidos, y el mismo esquema de acumulación se puede usar tanto para los ingresos como para los costes. Las acumulaciones contables redistribuyen los costes o los ingresos de una línea de diario para que se reconozcan en los períodos adecuados En la página **Esquema de acumulación**, especifique las cuentas de crédito y débito que se usarán cuando se aplique el esquema de acumulación.

-   **Débito**: la cuenta principal que defina reemplazará la cuenta principal de débito en la línea del asiento de diario. Esta cuenta también se usará para la inversión del aplazamiento, en función de las transacciones de acumulaciones contables.
-   **Crédito**: la cuenta principal que defina reemplazará la cuenta principal de crédito en la línea del asiento de diario. Esta cuenta también se usará para la inversión del aplazamiento, en función de las transacciones de acumulaciones contables.

Tras determinar qué cuentas se usarán, puede especificar cómo se crea el número de asiento al crearse las transacciones de acumulación. También puede especificar la frecuencia con la que se producen las transacciones, el número de veces en que se crean las transacciones y cuándo se registran las transacciones. Tras la creación del esquema de acumulación, puede usarlo en algunos diarios a través de la función Acumulaciones contables.

## <a name="ledger-accruals"></a>Acumulaciones contables
Cuando especifique un diario, puede hacer clic en **Acumulaciones contables** en el menú **Funciones**. A continuación, al seleccionar el esquema de acumulación, verá el importe base del diario que se distribuirá por el período, según se determine por el esquema de acumulación. 

Por ejemplo, si paga el seguro de un empleado para todo el año en enero, y el importe es 12 000, debe reconocer dicho gasto cada mes. Puede seleccionar la fecha inicial. También puede especificar si el importe que se acumula se basa en la cuenta o en la cuenta de contrapartida. Después de crear sus selecciones, haga clic en **Transacciones** para ver todas las transacciones que se han creado en función del esquema de acumulación. Por ejemplo, si distribuye el importe de 12 000 en gastos de seguros durante el año, verá 1000 para cada mes. Tras registrar el diario, podrá ver las transacciones con la página de consulta **Transacciones de asiento**. Si no se puede aplicar un esquema de acumulación (por ejemplo, cuando está implicada una factura de pedido de ventas o factura de pedido de compra), puede abonar el importe pagado por adelantado y adeudar el importe de gasto. A continuación, puede seleccionar **Compensación** al aplicar el esquema de acumulación.


Para obtener más información, consulte [Crear esquemas de acumulación](tasks/create-accrual-schemes.md) y [Crear transacciones de acumulaciones del libro mayor](tasks/create-ledger-accrual-transactions.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
