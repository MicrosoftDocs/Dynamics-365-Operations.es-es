---
title: Crear y asignar una directiva de distribución de costes a una unidad de control de costes
description: Las reglas de distribución de costes se usan para distribuir los costes que se han contado financieramente en un centro de coste colectivo.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1d040f9495c7fb36985b5f96c15ac43aa226da24
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841330"
---
# <a name="create-and-assign-a-cost-distribution-policy-to-a-cost-control-unit"></a><span data-ttu-id="ce425-103">Crear y asignar una directiva de distribución de costes a una unidad de control de costes</span><span class="sxs-lookup"><span data-stu-id="ce425-103">Create and assign a cost distribution policy to a cost control unit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ce425-104">Las reglas de distribución de costes se usan para distribuir los costes que se han contado financieramente en un centro de coste colectivo.</span><span class="sxs-lookup"><span data-stu-id="ce425-104">Cost distribution rules are used to distribute costs that have been financially counted on a collective cost center.</span></span> <span data-ttu-id="ce425-105">El contable de costes se asegura de que el coste se distribuye en los centros de coste, en función de la base de asignación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ce425-105">The cost accountant makes sure that the cost is distributed to the cost centers, based on the selected allocation base.</span></span> <span data-ttu-id="ce425-106">Una directiva y las reglas correspondientes se asignan a una unidad de control de costes.</span><span class="sxs-lookup"><span data-stu-id="ce425-106">A policy and the corresponding rules are assigned to a cost control unit.</span></span> <span data-ttu-id="ce425-107">Esta guía de tareas utiliza un ejemplo para mostrar cómo crear una directiva de distribución de costes y las reglas correspondientes.</span><span class="sxs-lookup"><span data-stu-id="ce425-107">This task guide uses an example to show how to create a cost distribution policy and the corresponding rules.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="ce425-108">Crear una directiva</span><span class="sxs-lookup"><span data-stu-id="ce425-108">Create a policy</span></span>
1. <span data-ttu-id="ce425-109">Vaya a Contabilidad de costes > Directivas > Directivas de distribución de costes.</span><span class="sxs-lookup"><span data-stu-id="ce425-109">Go to Cost accounting > Policies > Cost distribution policies.</span></span>
2. <span data-ttu-id="ce425-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ce425-110">Click New.</span></span>
3. <span data-ttu-id="ce425-111">En el campo Nombre de directiva, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ce425-111">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="ce425-112">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ce425-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="ce425-113">En el campo Jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ce425-113">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="ce425-114">Seleccione Organización.</span><span class="sxs-lookup"><span data-stu-id="ce425-114">Select Organization.</span></span>  
6. <span data-ttu-id="ce425-115">En el campo Jerarquía de dimensión de elementos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ce425-115">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="ce425-116">Seleccione P/G de CDS.</span><span class="sxs-lookup"><span data-stu-id="ce425-116">Select CDS P/L.</span></span>  
7. <span data-ttu-id="ce425-117">En el campo Dimensión estadística, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ce425-117">In the Statistical dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="ce425-118">Seleccione elementos estadísticos.</span><span class="sxs-lookup"><span data-stu-id="ce425-118">Select Statistical elements.</span></span>  
8. <span data-ttu-id="ce425-119">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ce425-119">Click Save.</span></span>

## <a name="create-rules-for-the-policy"></a><span data-ttu-id="ce425-120">Cree reglas para la directiva</span><span class="sxs-lookup"><span data-stu-id="ce425-120">Create rules for the policy</span></span>
1. <span data-ttu-id="ce425-121">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ce425-121">Click New.</span></span>
2. <span data-ttu-id="ce425-122">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ce425-122">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="ce425-123">En el campo Nodo de jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ce425-123">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="ce425-124">Expanda la jerarquía para seleccionar 094.</span><span class="sxs-lookup"><span data-stu-id="ce425-124">Expand the hierarchy to select 094.</span></span>  
4. <span data-ttu-id="ce425-125">En el campo Nodo de jerarquía de dimensión de elementos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ce425-125">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="ce425-126">Seleccione Otros gastos de explotación y Limpieza de 605110.</span><span class="sxs-lookup"><span data-stu-id="ce425-126">Select Other operating expenses and then select 605110 Cleaning.</span></span>  
5. <span data-ttu-id="ce425-127">En el campo Comportamiento de costes, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="ce425-127">In the Cost behavior field, select an option.</span></span>
    * <span data-ttu-id="ce425-128">Seleccione Coste fijo.</span><span class="sxs-lookup"><span data-stu-id="ce425-128">Select Fixed cost.</span></span>  
6. <span data-ttu-id="ce425-129">En el campo Base de asignación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ce425-129">In the Allocation base field, enter or select a value.</span></span>
7. <span data-ttu-id="ce425-130">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ce425-130">Click New.</span></span>
8. <span data-ttu-id="ce425-131">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ce425-131">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="ce425-132">En el campo Nodo de jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ce425-132">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="ce425-133">Expanda la jerarquía para seleccionar 094.</span><span class="sxs-lookup"><span data-stu-id="ce425-133">Expand the hierarchy to select 094.</span></span>  
10. <span data-ttu-id="ce425-134">En el campo Nodo de jerarquía de dimensión de elementos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ce425-134">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="ce425-135">Seleccione Otros gastos de explotación y Alquiler de 605150.</span><span class="sxs-lookup"><span data-stu-id="ce425-135">Select Other operating expenses and then select 605150 Rent.</span></span>  
11. <span data-ttu-id="ce425-136">En el campo Comportamiento de costes, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="ce425-136">In the Cost behavior field, select an option.</span></span>
    * <span data-ttu-id="ce425-137">Seleccione Coste fijo.</span><span class="sxs-lookup"><span data-stu-id="ce425-137">Select Fixed cost.</span></span>  
12. <span data-ttu-id="ce425-138">En el campo Base de asignación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ce425-138">In the Allocation base field, enter or select a value.</span></span>
13. <span data-ttu-id="ce425-139">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ce425-139">Click Save.</span></span>

## <a name="assign-rules-to-a-cost-control-unit"></a><span data-ttu-id="ce425-140">Asignar reglas a una unidad de control de costes</span><span class="sxs-lookup"><span data-stu-id="ce425-140">Assign rules to a cost control unit</span></span>
1. <span data-ttu-id="ce425-141">Haga clic en Asignaciones de directiva de unidad de control de costes.</span><span class="sxs-lookup"><span data-stu-id="ce425-141">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="ce425-142">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ce425-142">Click New.</span></span>
3. <span data-ttu-id="ce425-143">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ce425-143">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="ce425-144">En el campo Válido desde fecha contable, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="ce425-144">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="ce425-145">Seleccione 1 de septiembre en el ejercicio válido.</span><span class="sxs-lookup"><span data-stu-id="ce425-145">Select September 1 in the valid fiscal year.</span></span>  
5. <span data-ttu-id="ce425-146">En el campo Unidad de control de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ce425-146">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="ce425-147">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ce425-147">Click Save.</span></span>

