---
title: Procesar asignaciones
description: Este artículo proporciona información sobre las asignaciones, las opciones para procesarlas en Microsoft Dynamics 365 Finance y cómo se pueden usar en la planificación presupuestaria. Las asignaciones se usan para distribuir importes en varias combinaciones de cuenta contable. Ayudan a garantizar que los gastos o ingresos se cargan en objeto adecuado en contabilidad.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: roschlom
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b13496e764f907201a23f0dd6772ee22efffb250
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204987"
---
# <a name="process-allocations"></a>Procesar asignaciones

[!include [banner](../includes/banner.md)]

Este artículo proporciona información sobre las asignaciones, las opciones para procesarlas y cómo se pueden usar en la planificación presupuestaria. Las asignaciones se usan para distribuir importes en varias combinaciones de cuenta contable. Ayudan a garantizar que los gastos o ingresos se cargan en objeto adecuado en contabilidad.

Las siguientes competencias admiten este proceso:

-   Asigne manualmente los importes de transacción con la acción Dividir en las distribuciones contables o aplicando plantillas predeterminadas de dimensión financiera a un documento. Para obtener más información, consulte [Distribuciones contables](../accounts-payable/accounting-distributions.md).
-   Asigne automáticamente los importes de las transacciones en función de los términos de asignación definidos en la cuenta principal individual. Se generarán asientos contables de asignación para cada diario según el porcentaje y la cuenta contable de destino siempre que un asiento contable cumpla los criterios definidos como la cuenta contable de origen. Para obtener más información, consulte [Términos de asignación de la cuenta principal](../general-ledger/main-account-allocation-terms.md).
-   Asigne automáticamente los saldos contables o los importes fijos según las reglas de asignación contable. Las reglas de asignación contable se procesan de manera periódica con diarios de asignación. Para obtener más información, consulte [Reglas de asignación](../general-ledger/ledger-allocation-rules.md).

###  <a name="allocations-in-budget-planning"></a>Asignaciones en planificación presupuestaria

Las reglas de asignación contable se pueden usar para planes presupuestarios. Cuando se usan reglas de asignación contable en la planificación presupuestaria, las reglas de asignación funcionan de la misma forma que el libro mayor, pero los datos de origen y los datos de destino proceden del plan presupuestario. También puede seleccionar manualmente reglas de asignación contable para usar para planes presupuestarios. Como alternativa, puede usar una programación de asignación que se ejecute como parte de un proceso de flujo de trabajo.

> [!NOTE]
> No puede usar las reglas de asignación contable de empresas vinculadas para la planificación presupuestaria.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]