---
title: Crear y asignar una directiva de distribución de costes a una unidad de control de costes
description: Las reglas de distribución de costes se usan para distribuir los costes que se han contado financieramente en un centro de coste colectivo.
author: ShylaThompson
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostDistributionRule
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 736b537958f65fb54d0829cfbcc819fd315b530c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810135"
---
# <a name="create-and-assign-a-cost-distribution-policy-to-a-cost-control-unit"></a><span data-ttu-id="591ef-103">Crear y asignar una directiva de distribución de costes a una unidad de control de costes</span><span class="sxs-lookup"><span data-stu-id="591ef-103">Create and assign a cost distribution policy to a cost control unit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="591ef-104">Las reglas de distribución de costes se usan para distribuir los costes que se han contado financieramente en un centro de coste colectivo.</span><span class="sxs-lookup"><span data-stu-id="591ef-104">Cost distribution rules are used to distribute costs that have been financially counted on a collective cost center.</span></span> <span data-ttu-id="591ef-105">El contable de costes se asegura de que el coste se distribuye en los centros de coste, en función de la base de asignación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="591ef-105">The cost accountant makes sure that the cost is distributed to the cost centers, based on the selected allocation base.</span></span> <span data-ttu-id="591ef-106">Una directiva y las reglas correspondientes se asignan a una unidad de control de costes.</span><span class="sxs-lookup"><span data-stu-id="591ef-106">A policy and the corresponding rules are assigned to a cost control unit.</span></span> <span data-ttu-id="591ef-107">Esta guía de tareas utiliza un ejemplo para mostrar cómo crear una directiva de distribución de costes y las reglas correspondientes.</span><span class="sxs-lookup"><span data-stu-id="591ef-107">This task guide uses an example to show how to create a cost distribution policy and the corresponding rules.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="591ef-108">Crear una directiva</span><span class="sxs-lookup"><span data-stu-id="591ef-108">Create a policy</span></span>
1. <span data-ttu-id="591ef-109">Vaya a Contabilidad de costes > Directivas > Directivas de distribución de costes.</span><span class="sxs-lookup"><span data-stu-id="591ef-109">Go to Cost accounting > Policies > Cost distribution policies.</span></span>
2. <span data-ttu-id="591ef-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="591ef-110">Click New.</span></span>
3. <span data-ttu-id="591ef-111">En el campo Nombre de directiva, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="591ef-111">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="591ef-112">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="591ef-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="591ef-113">En el campo Jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="591ef-113">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="591ef-114">Seleccione Organización.</span><span class="sxs-lookup"><span data-stu-id="591ef-114">Select Organization.</span></span>  
6. <span data-ttu-id="591ef-115">En el campo Jerarquía de dimensión de elementos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="591ef-115">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="591ef-116">Seleccione P/G de CDS.</span><span class="sxs-lookup"><span data-stu-id="591ef-116">Select CDS P/L.</span></span>  
7. <span data-ttu-id="591ef-117">En el campo Dimensión estadística, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="591ef-117">In the Statistical dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="591ef-118">Seleccione elementos estadísticos.</span><span class="sxs-lookup"><span data-stu-id="591ef-118">Select Statistical elements.</span></span>  
8. <span data-ttu-id="591ef-119">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="591ef-119">Click Save.</span></span>

## <a name="create-rules-for-the-policy"></a><span data-ttu-id="591ef-120">Cree reglas para la directiva</span><span class="sxs-lookup"><span data-stu-id="591ef-120">Create rules for the policy</span></span>
1. <span data-ttu-id="591ef-121">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="591ef-121">Click New.</span></span>
2. <span data-ttu-id="591ef-122">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="591ef-122">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="591ef-123">En el campo Nodo de jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="591ef-123">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="591ef-124">Expanda la jerarquía para seleccionar 094.</span><span class="sxs-lookup"><span data-stu-id="591ef-124">Expand the hierarchy to select 094.</span></span>  
4. <span data-ttu-id="591ef-125">En el campo Nodo de jerarquía de dimensión de elementos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="591ef-125">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="591ef-126">Seleccione Otros gastos de explotación y Limpieza de 605110.</span><span class="sxs-lookup"><span data-stu-id="591ef-126">Select Other operating expenses and then select 605110 Cleaning.</span></span>  
5. <span data-ttu-id="591ef-127">En el campo Comportamiento de costes, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="591ef-127">In the Cost behavior field, select an option.</span></span>
    * <span data-ttu-id="591ef-128">Seleccione Coste fijo.</span><span class="sxs-lookup"><span data-stu-id="591ef-128">Select Fixed cost.</span></span>  
6. <span data-ttu-id="591ef-129">En el campo Base de asignación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="591ef-129">In the Allocation base field, enter or select a value.</span></span>
7. <span data-ttu-id="591ef-130">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="591ef-130">Click New.</span></span>
8. <span data-ttu-id="591ef-131">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="591ef-131">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="591ef-132">En el campo Nodo de jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="591ef-132">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="591ef-133">Expanda la jerarquía para seleccionar 094.</span><span class="sxs-lookup"><span data-stu-id="591ef-133">Expand the hierarchy to select 094.</span></span>  
10. <span data-ttu-id="591ef-134">En el campo Nodo de jerarquía de dimensión de elementos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="591ef-134">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="591ef-135">Seleccione Otros gastos de explotación y Alquiler de 605150.</span><span class="sxs-lookup"><span data-stu-id="591ef-135">Select Other operating expenses and then select 605150 Rent.</span></span>  
11. <span data-ttu-id="591ef-136">En el campo Comportamiento de costes, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="591ef-136">In the Cost behavior field, select an option.</span></span>
    * <span data-ttu-id="591ef-137">Seleccione Coste fijo.</span><span class="sxs-lookup"><span data-stu-id="591ef-137">Select Fixed cost.</span></span>  
12. <span data-ttu-id="591ef-138">En el campo Base de asignación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="591ef-138">In the Allocation base field, enter or select a value.</span></span>
13. <span data-ttu-id="591ef-139">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="591ef-139">Click Save.</span></span>

## <a name="assign-rules-to-a-cost-control-unit"></a><span data-ttu-id="591ef-140">Asignar reglas a una unidad de control de costes</span><span class="sxs-lookup"><span data-stu-id="591ef-140">Assign rules to a cost control unit</span></span>
1. <span data-ttu-id="591ef-141">Haga clic en Asignaciones de directiva de unidad de control de costes.</span><span class="sxs-lookup"><span data-stu-id="591ef-141">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="591ef-142">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="591ef-142">Click New.</span></span>
3. <span data-ttu-id="591ef-143">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="591ef-143">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="591ef-144">En el campo Válido desde fecha contable, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="591ef-144">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="591ef-145">Seleccione 1 de septiembre en el ejercicio válido.</span><span class="sxs-lookup"><span data-stu-id="591ef-145">Select September 1 in the valid fiscal year.</span></span>  
5. <span data-ttu-id="591ef-146">En el campo Unidad de control de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="591ef-146">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="591ef-147">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="591ef-147">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]