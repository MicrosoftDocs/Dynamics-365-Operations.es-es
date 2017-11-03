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
ms.search.scope: Core, Operations
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: cb12e24fcb8e8c91f90b91e2fdb3039dd1735ca3
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="process-allocations"></a><span data-ttu-id="b6916-105">Procesar asignaciones</span><span class="sxs-lookup"><span data-stu-id="b6916-105">Process allocations</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="b6916-106">Este artículo proporciona información sobre las asignaciones, las opciones para procesarlas en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition y cómo se pueden usar en la planificación presupuestaria.</span><span class="sxs-lookup"><span data-stu-id="b6916-106">This article provides information about allocations, the options for processing them in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, and how they can be used in budget planning.</span></span> <span data-ttu-id="b6916-107">Las asignaciones se usan para distribuir importes en varias combinaciones de cuenta contable.</span><span class="sxs-lookup"><span data-stu-id="b6916-107">Allocations are used to distribute amounts across multiple ledger account combinations.</span></span> <span data-ttu-id="b6916-108">Ayudan a garantizar que los gastos o ingresos se cargan en objeto adecuado en contabilidad.</span><span class="sxs-lookup"><span data-stu-id="b6916-108">They help guarantee that expenses or revenue is charged to the correct object in accounting.</span></span>

<span data-ttu-id="b6916-109">Microsoft Dynamics 365 for Finance and Operations proporciona las siguientes capacidades para admitir este proceso:</span><span class="sxs-lookup"><span data-stu-id="b6916-109">Microsoft Dynamics 365 for Finance and Operations provides the following capabilities to support this process:</span></span>

-   <span data-ttu-id="b6916-110">Asigne manualmente los importes de transacción con la acción Dividir en las distribuciones contables o aplicando plantillas predeterminadas de dimensión financiera a un documento.</span><span class="sxs-lookup"><span data-stu-id="b6916-110">Manually allocate transaction amounts by using the Split action in accounting distributions, or by applying financial dimension default templates to a document.</span></span> <span data-ttu-id="b6916-111">Para obtener más información sobre distribuciones, consulte [Distribuciones contables](../accounts-payable/accounting-distributions.md).</span><span class="sxs-lookup"><span data-stu-id="b6916-111">For more information, see [Accounting distributions.](../accounts-payable/accounting-distributions.md)</span></span>
-   <span data-ttu-id="b6916-112">Asigne automáticamente los importes de las transacciones en función de los términos de asignación definidos en la cuenta principal individual.</span><span class="sxs-lookup"><span data-stu-id="b6916-112">Automatically allocate transactions amounts based on allocation terms defined on individual main account.</span></span> <span data-ttu-id="b6916-113">Se generarán asientos contables de asignación para cada diario según el porcentaje y la cuenta contable de destino siempre que un asiento contable cumpla los criterios definidos como la cuenta contable de origen.</span><span class="sxs-lookup"><span data-stu-id="b6916-113">Allocation account entries will be generated for each journal based on the percentage and destination ledger account whenever an accounting entry meets the criteria defined as the source ledger account.</span></span>
-   <span data-ttu-id="b6916-114">Asigne automáticamente los saldos contables o los importes fijos según las reglas de asignación contable.</span><span class="sxs-lookup"><span data-stu-id="b6916-114">Automatically allocate ledger balances or fixed amounts based on ledger allocation rules.</span></span> <span data-ttu-id="b6916-115">Las reglas de asignación contable se procesan de manera periódica con diarios de asignación.</span><span class="sxs-lookup"><span data-stu-id="b6916-115">The ledger allocation rules are processed on a periodic basis using allocation journals.</span></span> 

###  <a name="allocations-in-budget-planning"></a><span data-ttu-id="b6916-116">Asignaciones en planificación presupuestaria</span><span class="sxs-lookup"><span data-stu-id="b6916-116">Allocations in budget planning</span></span>

<span data-ttu-id="b6916-117">Las reglas de asignación contable se pueden usar para planes presupuestarios.</span><span class="sxs-lookup"><span data-stu-id="b6916-117">Ledger allocation rules can be used for budget plans.</span></span> <span data-ttu-id="b6916-118">Cuando se usan reglas de asignación contable en la planificación presupuestaria, las reglas de asignación funcionan de la misma forma que el libro mayor, pero los datos de origen y los datos de destino proceden del plan presupuestario.</span><span class="sxs-lookup"><span data-stu-id="b6916-118">When you use ledger allocation rules in budget planning, the allocation rules work the same way they would in the ledger, but the source data and destination data comes from the budget plan.</span></span> <span data-ttu-id="b6916-119">También puede seleccionar manualmente reglas de asignación contable para usar para planes presupuestarios.</span><span class="sxs-lookup"><span data-stu-id="b6916-119">You can manually select ledger allocation rules to use for budget plans.</span></span> <span data-ttu-id="b6916-120">Como alternativa, puede usar una programación de asignación que se ejecute como parte de un proceso de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b6916-120">Alternatively, you can use an allocation schedule that runs as part of a workflow process.</span></span>

> [!NOTE]
> <span data-ttu-id="b6916-121">No puede usar las reglas de asignación contable de empresas vinculadas para la planificación presupuestaria.</span><span class="sxs-lookup"><span data-stu-id="b6916-121">You can’t use intercompany ledger allocation rules for budget planning.</span></span>






