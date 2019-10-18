---
title: Crear una directiva de acumulación de costes
description: Este procedimiento muestra cómo crear una directiva de acumulación de costes y crea reglas para la directiva.
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
ms.openlocfilehash: facffeaf8d880bad01877b420197e29b6791ebbf
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187783"
---
# <a name="create-a-cost-rollup-policy"></a><span data-ttu-id="030b5-103">Crear una directiva de acumulación de costes</span><span class="sxs-lookup"><span data-stu-id="030b5-103">Create a cost rollup policy</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="030b5-104">Este procedimiento muestra cómo crear una directiva de acumulación de costes y crea reglas para la directiva.</span><span class="sxs-lookup"><span data-stu-id="030b5-104">This procedure shows how to create a cost rollup policy and create rules for the policy.</span></span> <span data-ttu-id="030b5-105">Los datos de demostración utilizados para crear este procedimiento son los de la empresa USP2.</span><span class="sxs-lookup"><span data-stu-id="030b5-105">The demo data used to create this procedure is USP2.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="030b5-106">Crear una directiva</span><span class="sxs-lookup"><span data-stu-id="030b5-106">Create a policy</span></span>
1. <span data-ttu-id="030b5-107">Vaya a Contabilidad de costes > Directivas > Directivas de acumulación de costes.</span><span class="sxs-lookup"><span data-stu-id="030b5-107">Go to Cost accounting > Policies > Cost rollup policies.</span></span>
2. <span data-ttu-id="030b5-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="030b5-108">Click New.</span></span>
3. <span data-ttu-id="030b5-109">En el campo Nombre de directiva, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="030b5-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="030b5-110">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="030b5-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="030b5-111">En el campo Jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="030b5-111">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="030b5-112">Seleccionar Tarjeta de crédito para acumulación de costes</span><span class="sxs-lookup"><span data-stu-id="030b5-112">Select Cost rollup CC.</span></span>  
6. <span data-ttu-id="030b5-113">En el campo Jerarquía de dimensión de elementos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="030b5-113">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="030b5-114">Seleccionar Tarjeta de crédito para acumulación de costes</span><span class="sxs-lookup"><span data-stu-id="030b5-114">Select Cost rollup CC.</span></span>  
7. <span data-ttu-id="030b5-115">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="030b5-115">Click Save.</span></span>

## <a name="create-rules-for-the-cost-rollup-policy"></a><span data-ttu-id="030b5-116">Crear reglas para la directiva de acumulación de costes</span><span class="sxs-lookup"><span data-stu-id="030b5-116">Create rules for the cost rollup policy</span></span>
1. <span data-ttu-id="030b5-117">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="030b5-117">Click New.</span></span>
2. <span data-ttu-id="030b5-118">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="030b5-118">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="030b5-119">En el campo Nodo de jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="030b5-119">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="030b5-120">Seleccione 007.</span><span class="sxs-lookup"><span data-stu-id="030b5-120">Select 007.</span></span>  
4. <span data-ttu-id="030b5-121">En el campo Nodo de jerarquía de dimensión de elementos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="030b5-121">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="030b5-122">Seleccionar BE para acumulación de costes.</span><span class="sxs-lookup"><span data-stu-id="030b5-122">Select Cost rollup CE.</span></span>  
5. <span data-ttu-id="030b5-123">En el campo Elemento de coste secundario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="030b5-123">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="030b5-124">Para este ejemplo, asigne el elemento de coste secundario CC-007 el centro de coste.</span><span class="sxs-lookup"><span data-stu-id="030b5-124">For this example, map the secondary cost element CC-007 to the cost center.</span></span>  
6. <span data-ttu-id="030b5-125">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="030b5-125">Click New.</span></span>
7. <span data-ttu-id="030b5-126">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="030b5-126">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="030b5-127">En el campo Nodo de jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="030b5-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="030b5-128">Seleccione 008.</span><span class="sxs-lookup"><span data-stu-id="030b5-128">Select 008.</span></span>  
9. <span data-ttu-id="030b5-129">En el campo Nodo de jerarquía de dimensión de elementos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="030b5-129">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="030b5-130">Seleccionar BE para acumulación de costes.</span><span class="sxs-lookup"><span data-stu-id="030b5-130">Select Cost rollup CE.</span></span>  
10. <span data-ttu-id="030b5-131">En el campo Elemento de coste secundario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="030b5-131">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="030b5-132">Para este ejemplo, asigne el elemento de coste secundario CC-008 el centro de coste.</span><span class="sxs-lookup"><span data-stu-id="030b5-132">For this example, map the secondary cost element CC-008 to the cost center.</span></span>  
11. <span data-ttu-id="030b5-133">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="030b5-133">Click New.</span></span>
12. <span data-ttu-id="030b5-134">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="030b5-134">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="030b5-135">En el campo Nodo de jerarquía de dimensión de objetos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="030b5-135">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="030b5-136">Seleccione 009.</span><span class="sxs-lookup"><span data-stu-id="030b5-136">Select 009.</span></span>  
14. <span data-ttu-id="030b5-137">En el campo Nodo de jerarquía de dimensión de elementos de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="030b5-137">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="030b5-138">Seleccionar BE para acumulación de costes.</span><span class="sxs-lookup"><span data-stu-id="030b5-138">Select Cost rollup CE.</span></span>  
15. <span data-ttu-id="030b5-139">En el campo Elemento de coste secundario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="030b5-139">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="030b5-140">Para este ejemplo, asigne el elemento de coste secundario CC-009 el centro de coste.</span><span class="sxs-lookup"><span data-stu-id="030b5-140">For this example, map the secondary cost element CC-009 to the cost center.</span></span>  
    * <span data-ttu-id="030b5-141">Continúe hasta que todos los centros de coste se hayan asignado a los elementos de coste secundarios correspondientes.</span><span class="sxs-lookup"><span data-stu-id="030b5-141">Continue until all cost centers are mapped to their corresponding secondary cost elements.</span></span>  
16. <span data-ttu-id="030b5-142">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="030b5-142">Click Save.</span></span>

