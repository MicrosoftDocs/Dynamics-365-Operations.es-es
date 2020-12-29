---
title: Crear y asignar una directiva de asignación de costes a una unidad de control de costes
description: Use este procedimiento para crear y asignar una directiva de asignación de costes y las reglas correspondientes a una unidad de control de costes.
author: ShylaThompson
manager: AnnBe
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostAccountingLedgerPolicyAssignment
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ad95752ce40faaa84747dac9bfbf2887f7a5af42
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447751"
---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a><span data-ttu-id="f7660-103">Crear y asignar una directiva de asignación de costes a una unidad de control de costes</span><span class="sxs-lookup"><span data-stu-id="f7660-103">Create and assign a cost allocation policy to a cost control unit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f7660-104">Use este procedimiento para crear y asignar una directiva de asignación de costes y las reglas correspondientes a una unidad de control de costes.</span><span class="sxs-lookup"><span data-stu-id="f7660-104">Use this procedure to create and assign a cost allocation policy and the corresponding rules to a cost control unit.</span></span> <span data-ttu-id="f7660-105">Este registro usa la empresa USP2 con los datos para demostración.</span><span class="sxs-lookup"><span data-stu-id="f7660-105">This recording uses the USP2 demo data company.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="f7660-106">Crear una directiva</span><span class="sxs-lookup"><span data-stu-id="f7660-106">Create a policy</span></span>
1. <span data-ttu-id="f7660-107">Vaya a Contabilidad de costes > Directivas > Directivas de asignación de costes.</span><span class="sxs-lookup"><span data-stu-id="f7660-107">Go to Cost accounting > Policies > Cost allocation policies.</span></span>
2. <span data-ttu-id="f7660-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="f7660-108">Click New.</span></span>
3. <span data-ttu-id="f7660-109">En el campo Nombre de directiva, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f7660-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="f7660-110">En el campo Jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f7660-110">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="f7660-111">Seleccione Organización.</span><span class="sxs-lookup"><span data-stu-id="f7660-111">Select Organization.</span></span>  
5. <span data-ttu-id="f7660-112">En el campo Dimensión estadística, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f7660-112">In the Statistical dimension field, enter or select a value.</span></span>
6. <span data-ttu-id="f7660-113">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="f7660-113">Click Save.</span></span>

## <a name="create-allocation-rules"></a><span data-ttu-id="f7660-114">Crear reglas de asignación</span><span class="sxs-lookup"><span data-stu-id="f7660-114">Create allocation rules</span></span>
1. <span data-ttu-id="f7660-115">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="f7660-115">Click New.</span></span>
2. <span data-ttu-id="f7660-116">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f7660-116">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="f7660-117">En el campo Nodo de jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f7660-117">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
4. <span data-ttu-id="f7660-118">En el campo Comportamiento e costes, seleccione "Total".</span><span class="sxs-lookup"><span data-stu-id="f7660-118">In the Cost behavior field, select 'Total'.</span></span>
5. <span data-ttu-id="f7660-119">En el campo Base de asignación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f7660-119">In the Allocation base field, enter or select a value.</span></span>
6. <span data-ttu-id="f7660-120">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="f7660-120">Click New.</span></span>
7. <span data-ttu-id="f7660-121">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f7660-121">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="f7660-122">En el campo Nodo de jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f7660-122">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
9. <span data-ttu-id="f7660-123">En el campo Comportamiento e costes, seleccione "Total".</span><span class="sxs-lookup"><span data-stu-id="f7660-123">In the Cost behavior field, select 'Total'.</span></span>
10. <span data-ttu-id="f7660-124">En el campo Base de asignación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f7660-124">In the Allocation base field, enter or select a value.</span></span>
11. <span data-ttu-id="f7660-125">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="f7660-125">Click New.</span></span>
12. <span data-ttu-id="f7660-126">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f7660-126">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="f7660-127">En el campo Nodo de jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f7660-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
14. <span data-ttu-id="f7660-128">En el campo Comportamiento e costes, seleccione "Total".</span><span class="sxs-lookup"><span data-stu-id="f7660-128">In the Cost behavior field, select 'Total'.</span></span>
15. <span data-ttu-id="f7660-129">En el campo Base de asignación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f7660-129">In the Allocation base field, enter or select a value.</span></span>
    * <span data-ttu-id="f7660-130">Continúe hasta haber creado todas las reglas.</span><span class="sxs-lookup"><span data-stu-id="f7660-130">Continue until you've created all the rules.</span></span>  
16. <span data-ttu-id="f7660-131">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="f7660-131">Click Save.</span></span>

## <a name="assign-the-policy-to-a-cost-control-unit"></a><span data-ttu-id="f7660-132">Asignar la directiva de una unidad de control de costes</span><span class="sxs-lookup"><span data-stu-id="f7660-132">Assign the policy to a cost control unit</span></span>
1. <span data-ttu-id="f7660-133">Haga clic en Asignaciones de directiva de unidad de control de costes.</span><span class="sxs-lookup"><span data-stu-id="f7660-133">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="f7660-134">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="f7660-134">Click New.</span></span>
3. <span data-ttu-id="f7660-135">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f7660-135">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="f7660-136">En el campo Válido desde fecha contable, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="f7660-136">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="f7660-137">Las reglas entran en vigor en una fecha.</span><span class="sxs-lookup"><span data-stu-id="f7660-137">The rules are date-effective.</span></span> <span data-ttu-id="f7660-138">Un usuario o el sistema pueden hacer vencer las reglas si se crear una versión más nueva.</span><span class="sxs-lookup"><span data-stu-id="f7660-138">A user or the system can expire the rules if a newer version is created.</span></span>  
5. <span data-ttu-id="f7660-139">En el campo Unidad de control de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f7660-139">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="f7660-140">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="f7660-140">Click Save.</span></span>

