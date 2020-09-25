---
title: Crear y asignar una directiva de comportamiento de costes a una unidad de control de costes
description: El comportamiento del coste es la clasificación de los costes como fijos o variables.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostBehaviorRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3f52133df2d374d6dc0f1efb33ffc85eb7d11fa9
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759241"
---
# <a name="create-and-assign-a-cost-behavior-policy-to-a-cost-control-unit"></a><span data-ttu-id="5966d-103">Crear y asignar una directiva de comportamiento de costes a una unidad de control de costes</span><span class="sxs-lookup"><span data-stu-id="5966d-103">Create and assign a cost behavior policy to a cost control unit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5966d-104">El comportamiento del coste es la clasificación de los costes como fijos o variables.</span><span class="sxs-lookup"><span data-stu-id="5966d-104">Cost behavior is the classification of costs as either fixed or variable.</span></span> <span data-ttu-id="5966d-105">Una directiva y las reglas correspondientes tienen que asignarse a una unidad de control de costes para que la directiva entre en vigor.</span><span class="sxs-lookup"><span data-stu-id="5966d-105">A policy and the corresponding rules have to be assigned to a cost control unit for the policy to become effective.</span></span> <span data-ttu-id="5966d-106">Use este procedimiento para crear una directiva y después asignar la directiva a una unidad de control de costes.</span><span class="sxs-lookup"><span data-stu-id="5966d-106">Use this procedure to create a policy and then assign the policy to a cost control unit.</span></span>


## <a name="create-a-cost-behavior-hierarchy"></a><span data-ttu-id="5966d-107">Crear una jerarquía de comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="5966d-107">Create a cost behavior hierarchy</span></span>
1. <span data-ttu-id="5966d-108">Vaya a Contabilidad de costes > Dimensiones > Jerarquías de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="5966d-108">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="5966d-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="5966d-109">Click New.</span></span>
3. <span data-ttu-id="5966d-110">Haga clic en Crear.</span><span class="sxs-lookup"><span data-stu-id="5966d-110">Click Create.</span></span>
4. <span data-ttu-id="5966d-111">En el campo Nombre de la jerarquía de dimensiones, escriba “Jerarquía de comportamiento de costes”.</span><span class="sxs-lookup"><span data-stu-id="5966d-111">In the Dimension hierarchy name field, type 'Cost behavior hierarchy'.</span></span>
5. <span data-ttu-id="5966d-112">En el campo Dimensión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="5966d-112">In the Dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="5966d-113">Seleccionar elementos de coste.</span><span class="sxs-lookup"><span data-stu-id="5966d-113">Select Cost elements.</span></span>  
6. <span data-ttu-id="5966d-114">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="5966d-114">Click Save.</span></span>
7. <span data-ttu-id="5966d-115">Haga clic en Ver jerarquía.</span><span class="sxs-lookup"><span data-stu-id="5966d-115">Click View hierarchy.</span></span>
8. <span data-ttu-id="5966d-116">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="5966d-116">Click New.</span></span>
9. <span data-ttu-id="5966d-117">En el campo Nombre de nodo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="5966d-117">In the Node name field, type a value.</span></span>
    * <span data-ttu-id="5966d-118">Especifique el coste fijo</span><span class="sxs-lookup"><span data-stu-id="5966d-118">Enter Fixed cost.</span></span>  
10. <span data-ttu-id="5966d-119">En el árbol, seleccione "Jerarquía de comportamiento de costes”.</span><span class="sxs-lookup"><span data-stu-id="5966d-119">In the tree, select 'Cost behavior hierarchy'.</span></span>
11. <span data-ttu-id="5966d-120">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="5966d-120">Click New.</span></span>
12. <span data-ttu-id="5966d-121">En el campo Nombre de nodo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="5966d-121">In the Node name field, type a value.</span></span>
    * <span data-ttu-id="5966d-122">Especifique el coste variable.</span><span class="sxs-lookup"><span data-stu-id="5966d-122">Enter Variable cost.</span></span>  
13. <span data-ttu-id="5966d-123">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="5966d-123">Click Save.</span></span>
14. <span data-ttu-id="5966d-124">En el árbol, seleccione "Jerarquía de comportamiento de costes\Coste fijo”.</span><span class="sxs-lookup"><span data-stu-id="5966d-124">In the tree, select 'Cost behavior hierarchy\Fixed cost'.</span></span>
15. <span data-ttu-id="5966d-125">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="5966d-125">Click New.</span></span>
16. <span data-ttu-id="5966d-126">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="5966d-126">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="5966d-127">En el campo Desde miembro de dimensión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="5966d-127">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="5966d-128">El intervalo de miembros de dimensión puede contener espacios, pero los miembros no se pueden superponer.</span><span class="sxs-lookup"><span data-stu-id="5966d-128">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
18. <span data-ttu-id="5966d-129">En el campo Hasta miembro de dimensión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="5966d-129">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="5966d-130">El intervalo de miembros de dimensión puede contener espacios, pero los miembros no se pueden superponer.</span><span class="sxs-lookup"><span data-stu-id="5966d-130">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
19. <span data-ttu-id="5966d-131">En el árbol, seleccione "Jerarquía de comportamiento de costes\Coste variable”.</span><span class="sxs-lookup"><span data-stu-id="5966d-131">In the tree, select 'Cost behavior hierarchy\Variable cost'.</span></span>
20. <span data-ttu-id="5966d-132">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="5966d-132">Click New.</span></span>
21. <span data-ttu-id="5966d-133">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="5966d-133">In the list, mark the selected row.</span></span>
22. <span data-ttu-id="5966d-134">En el campo Desde miembro de dimensión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="5966d-134">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="5966d-135">El intervalo de miembros de dimensión puede contener espacios, pero los miembros no se pueden superponer.</span><span class="sxs-lookup"><span data-stu-id="5966d-135">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
23. <span data-ttu-id="5966d-136">En el campo Hasta miembro de dimensión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="5966d-136">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="5966d-137">El intervalo de miembros de dimensión puede contener espacios, pero los miembros no se pueden superponer.</span><span class="sxs-lookup"><span data-stu-id="5966d-137">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
24. <span data-ttu-id="5966d-138">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="5966d-138">Click Save.</span></span>

## <a name="create-the-policy-and-rules"></a><span data-ttu-id="5966d-139">Cree la directiva y las reglas</span><span class="sxs-lookup"><span data-stu-id="5966d-139">Create the policy and rules</span></span>
1. <span data-ttu-id="5966d-140">Vaya a Contabilidad de costes > Directivas > Directivas de comportamiento de costes.</span><span class="sxs-lookup"><span data-stu-id="5966d-140">Go to Cost accounting > Policies > Cost behavior policies.</span></span>
2. <span data-ttu-id="5966d-141">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="5966d-141">Click New.</span></span>
3. <span data-ttu-id="5966d-142">En el campo Nombre de directiva, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="5966d-142">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="5966d-143">En el campo Jerarquía de dimensión de elementos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="5966d-143">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="5966d-144">Seleccione la jerarquía de directivas que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="5966d-144">Select the policy hierarchy that you just created.</span></span>  
5. <span data-ttu-id="5966d-145">En el campo Jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="5966d-145">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="5966d-146">Seleccione Organización.</span><span class="sxs-lookup"><span data-stu-id="5966d-146">Select Organization.</span></span>  
6. <span data-ttu-id="5966d-147">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="5966d-147">Click Save.</span></span>
7. <span data-ttu-id="5966d-148">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="5966d-148">Click New.</span></span>
8. <span data-ttu-id="5966d-149">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="5966d-149">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="5966d-150">En el campo Nodo de jerarquía de dimensión de elementos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="5966d-150">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="5966d-151">Expanda la jerarquía para seleccionar Coste variable.</span><span class="sxs-lookup"><span data-stu-id="5966d-151">Expand the hierarchy to select Variable cost.</span></span>  
10. <span data-ttu-id="5966d-152">En el campo Nodo de jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="5966d-152">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="5966d-153">De forma predeterminada, el porcentaje variable es del 100 por ciento.</span><span class="sxs-lookup"><span data-stu-id="5966d-153">By default, the variable percentage is 100 percent.</span></span>  
11. <span data-ttu-id="5966d-154">Haga clic en Asignaciones de directiva de unidad de control de costes.</span><span class="sxs-lookup"><span data-stu-id="5966d-154">Click Policy assignments for cost control unit.</span></span>
12. <span data-ttu-id="5966d-155">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="5966d-155">Click New.</span></span>
13. <span data-ttu-id="5966d-156">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="5966d-156">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="5966d-157">En el campo Válido desde fecha contable, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="5966d-157">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="5966d-158">Las reglas entran en vigor en una fecha y un usuario o el sistema puede hacer vencer una regla si se crea una versión más nueva.</span><span class="sxs-lookup"><span data-stu-id="5966d-158">The rules are date-effective, and a user or the system can expire a rule if a newer version is created.</span></span>  
15. <span data-ttu-id="5966d-159">En el campo Unidad de control de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="5966d-159">In the Cost control unit field, enter or select a value.</span></span>
16. <span data-ttu-id="5966d-160">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="5966d-160">Click Save.</span></span>

