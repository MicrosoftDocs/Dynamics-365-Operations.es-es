---
title: "Visión general de Acumulaciones"
description: "Este artículo describe acumulaciones y proporciona información acerca de cómo configurarlas y crear transacciones."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerAccuralTable
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14131
ms.assetid: 0489b59a-37a7-4a78-87bf-4b597e9efad9
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 328a4a7bef32ee8634e4a9f4854ebe78fcc99f6d
ms.lasthandoff: 03/31/2017


---

# <a name="accruals-overview"></a>Visión general de Acumulaciones

Este artículo describe acumulaciones y proporciona información acerca de cómo configurarlas y crear transacciones.

Las acumulaciones se usan en la contabilidad por devengo para realizar un seguimiento de los ingresos que se reconoce en el período en que se ha obtenido, no cuando se recibe el pago, y para realizar un seguimiento de los gastos (costes) que se reconocen cuando se producen, no cuando se realiza el pago.

## <a name="accrual-schemes"></a>Esquemas de acumulación
Los esquemas de acumulación se usan para configurar los costes y los ingresos diferidos, y el mismo esquema de acumulación se puede usar tanto para los ingresos como para los costes. Las acumulaciones contables redistribuyen los costes o los ingresos de una línea de diario para que se reconozcan en los períodos adecuados En la página **Esquema de acumulación**, especifique las cuentas de crédito y débito que se usarán cuando se aplique el esquema de acumulación.

-   **Débito**: la cuenta principal que defina reemplazará la cuenta principal de débito en la línea del asiento de diario. Esta cuenta también se usará para la inversión del aplazamiento, en función de las transacciones de acumulaciones contables.
-   **Crédito**: la cuenta principal que defina reemplazará la cuenta principal de crédito en la línea del asiento de diario. Esta cuenta también se usará para la inversión del aplazamiento, en función de las transacciones de acumulaciones contables.

Tras determinar qué cuentas se usarán, puede especificar cómo se crea el número de asiento al crearse las transacciones de acumulación. También puede especificar la frecuencia con la que se producen las transacciones, el número de veces en que se crean las transacciones y cuándo se registran las transacciones. Tras la creación del esquema de acumulación, puede usarlo en algunos diarios a través de la función Acumulaciones contables.

## <a name="ledger-accruals"></a>Acumulaciones contables
Cuando especifique un diario, puede hacer clic en **Acumulaciones contables** en el menú**Funciones**. A continuación, al seleccionar el esquema de acumulación, verá el importe base del diario que se distribuirá por el período, según se determine por el esquema de acumulación. Por ejemplo, si paga el seguro de un empleado durante todo el año en enero, y el importe es 12,000, debe reconocer que dicho gasto cada mes. Puede seleccionar la fecha inicial. También puede especificar si el importe que se acumula se basa en la cuenta o en la cuenta de contrapartida. Después de crear sus selecciones, haga clic ** transacciones ** para ver todas las transacciones que se han creado en función del esquema de acumulación. Por ejemplo, si se amplía 12,000 en los gastos del seguro durante el año, verá 1,000 para cada mes. Después de registrar el diario, puede ver las transacciones mediante ** las transacciones de asiento ** la página de la pregunta. Si un esquema de acumulación no se puede aplicar (por ejemplo, cuando una factura de pedido de ventas o una factura de pedido de compra está involucrada), puede abonar el importe pagado por adelantado y cargar el importe de gastos. A continuación, puede seleccionar **Compensación** al aplicar el esquema de acumulación.


