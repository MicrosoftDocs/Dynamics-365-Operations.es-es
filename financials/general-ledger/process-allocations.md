---
title: Procesar asignaciones
description: "Este artículo proporciona información sobre las asignaciones, las opciones para procesarlas en Microsoft Dynamics 365 para las operaciones, y su uso en la planificación de presupuesto. Las asignaciones se usan para distribuir importes en varias combinaciones de cuenta contable. Ayudan a garantizar que los gastos o ingresos se cargan en objeto adecuado en contabilidad."
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: 37f4df5d0b79208a8c565bc9101ddde193a6ef5b
ms.lasthandoff: 03/31/2017


---

# <a name="process-allocations"></a>Procesar asignaciones

Este artículo proporciona información sobre las asignaciones, las opciones para procesarlas en Microsoft Dynamics 365 para las operaciones, y su uso en la planificación de presupuesto. Las asignaciones se usan para distribuir importes en varias combinaciones de cuenta contable. Ayudan a garantizar que los gastos o ingresos se cargan en objeto adecuado en contabilidad.

Microsoft Dynamics 365 para las operaciones ofrece las siguientes competencias de ese proceso:

-   Permite asignar manualmente los importes de transacción mediante la acción dividirse en distribuciones contables, o por las plantillas predeterminadas de dimensión financiera que se aplican a un documento. Para obtener más información, consulte [las distribuciones contables.] (\ \ accounting-distributions.md proveedores)
-   Asigne automáticamente los importes de las transacciones en función de los términos de asignación definidos en la cuenta principal individual. Se generarán asientos contables de asignación para cada diario según el porcentaje y la cuenta contable de destino siempre que un asiento contable cumpla los criterios definidos como la cuenta contable de origen.
-   Asigne automáticamente los saldos contables o los importes fijos según las reglas de asignación contable. Las reglas de asignación contable se procesan de manera periódica con diarios de asignación. 

###  <a name="allocations-in-budget-planning"></a>Asignaciones en planificación presupuestaria

Las reglas de asignación contable se pueden usar para planes presupuestarios. Cuando se usan reglas de asignación contable en la planificación presupuestaria, las reglas de asignación funcionan de la misma forma que el libro mayor, pero los datos de origen y los datos de destino proceden del plan presupuestario. También puede seleccionar manualmente reglas de asignación contable para usar para planes presupuestarios. Como alternativa, puede usar una programación de asignación que se ejecute como parte de un proceso de flujo de trabajo.

> [!NOTE]
> No puede usar las reglas de asignación contable de empresas vinculadas para la planificación presupuestaria.




