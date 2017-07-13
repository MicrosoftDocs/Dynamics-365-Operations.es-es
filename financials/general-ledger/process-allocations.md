---
title: Procesar asignaciones
description: "Este artículo proporciona información sobre las asignaciones, las opciones para procesarlas en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition y cómo se pueden usar en la planificación presupuestaria. Las asignaciones se usan para distribuir importes en varias combinaciones de cuenta contable. Ayudan a garantizar que los gastos o ingresos se cargan en objeto adecuado en contabilidad."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 298ac47e2253f8add1aa3938dda15afe186afbeb
ms.openlocfilehash: e6d88503972850f6163aba6b45547a111f44abab
ms.contentlocale: es-es
ms.lasthandoff: 06/20/2017


---

# Procesar asignaciones
<a id="process-allocations" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Este artículo proporciona información sobre las asignaciones, las opciones para procesarlas en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition y cómo se pueden usar en la planificación presupuestaria. Las asignaciones se usan para distribuir importes en varias combinaciones de cuenta contable. Ayudan a garantizar que los gastos o ingresos se cargan en objeto adecuado en contabilidad.

Microsoft Dynamics 365 for Finance and Operations proporciona las siguientes capacidades para admitir este proceso:

-   Asigne manualmente los importes de transacción con la acción Dividir en las distribuciones contables o aplicando plantillas predeterminadas de dimensión financiera a un documento. Para obtener más información sobre distribuciones, consulte [Distribuciones contables](../accounts-payable/accounting-distributions.md).
-   Asigne automáticamente los importes de las transacciones en función de los términos de asignación definidos en la cuenta principal individual. Se generarán asientos contables de asignación para cada diario según el porcentaje y la cuenta contable de destino siempre que un asiento contable cumpla los criterios definidos como la cuenta contable de origen.
-   Asigne automáticamente los saldos contables o los importes fijos según las reglas de asignación contable. Las reglas de asignación contable se procesan de manera periódica con diarios de asignación. 

###  Asignaciones en planificación presupuestaria
<a id="allocations-in-budget-planning" class="xliff"></a>

Las reglas de asignación contable se pueden usar para planes presupuestarios. Cuando se usan reglas de asignación contable en la planificación presupuestaria, las reglas de asignación funcionan de la misma forma que el libro mayor, pero los datos de origen y los datos de destino proceden del plan presupuestario. También puede seleccionar manualmente reglas de asignación contable para usar para planes presupuestarios. Como alternativa, puede usar una programación de asignación que se ejecute como parte de un proceso de flujo de trabajo.

> [!NOTE]
> No puede usar las reglas de asignación contable de empresas vinculadas para la planificación presupuestaria.






