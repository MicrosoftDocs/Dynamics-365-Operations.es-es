---
title: Agregar una directiva de cálculo de cantidad kanban a una regla kanban
description: Este procedimiento se centra en la creación de una directiva de cálculo de cantidad kanban y su adición a una regla kanban para optimizar el tamaño y las cantidades kanban.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanQuantityPolicy, KanbanRules, KanbanQuantityCalculation
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 039c4aaa355cf2b850ded06913e8e39ee8cac543
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436586"
---
# <a name="add-a-kanban-quantity-calculation-policy-to-a-kanban-rule"></a><span data-ttu-id="01627-103">Agregar una directiva de cálculo de cantidad kanban a una regla kanban</span><span class="sxs-lookup"><span data-stu-id="01627-103">Add a kanban quantity calculation policy to a kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="01627-104">Este procedimiento se centra en la creación de una directiva de cálculo de cantidad kanban y su adición a una regla kanban para optimizar el tamaño y las cantidades kanban.</span><span class="sxs-lookup"><span data-stu-id="01627-104">This procedure focuses on creating a kanban quantity calculation policy and adding it to a kanban rule to optimize the kanban size and quantities.</span></span> <span data-ttu-id="01627-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="01627-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="01627-106">Este procedimiento va destinado al administrador del flujo de valor.</span><span class="sxs-lookup"><span data-stu-id="01627-106">This procedure is intended for the value stream manager.</span></span> <span data-ttu-id="01627-107">Este procedimiento es requisito previo para crear el procedimiento Calcular sugerencias de cantidades kanban.</span><span class="sxs-lookup"><span data-stu-id="01627-107">This procedure is a prerequisite for creating the procedure Calculate kanban quantity suggestions.</span></span> 


## <a name="create-a-kanban-quantity-calculation-policy"></a><span data-ttu-id="01627-108">Creación de una directiva de cálculo de cantidad kanban</span><span class="sxs-lookup"><span data-stu-id="01627-108">Create a kanban quantity calculation policy</span></span>
1. <span data-ttu-id="01627-109">Vaya a Control de producción > Tareas periódicas > Cálculo de cantidad kanban > Directivas de cálculo de cantidad kanban.</span><span class="sxs-lookup"><span data-stu-id="01627-109">Go to Production control > Periodic tasks > Kanban quantity calculation > Kanban quantity calculation policies.</span></span>
2. <span data-ttu-id="01627-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="01627-110">Click New.</span></span>
3. <span data-ttu-id="01627-111">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="01627-111">In the Name field, type a value.</span></span>
    * <span data-ttu-id="01627-112">Por ejemplo, escriba Speaker2016.</span><span class="sxs-lookup"><span data-stu-id="01627-112">For example, type Speaker2016.</span></span>  
4. <span data-ttu-id="01627-113">En el campo Plan maestro, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="01627-113">In the Master plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="01627-114">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="01627-114">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="01627-115">Seleccione StaticPlan para calcular la demanda.</span><span class="sxs-lookup"><span data-stu-id="01627-115">Select StaticPlan to calculate demand.</span></span>  
6. <span data-ttu-id="01627-116">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="01627-116">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="01627-117">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="01627-117">Click Save.</span></span>
8. <span data-ttu-id="01627-118">En el campo Cantidad kanban mínima, especifique "1".</span><span class="sxs-lookup"><span data-stu-id="01627-118">In the Minimum kanban quantity field, enter '1'.</span></span>
    * <span data-ttu-id="01627-119">Este es el número de kanbans adicionales que se incluyen en el cálculo de la cantidad kanban.</span><span class="sxs-lookup"><span data-stu-id="01627-119">This is the additional number of kanbans that is included in the kanban quantity calculation.</span></span>  
9. <span data-ttu-id="01627-120">Defina Factor de seguridad en "1".</span><span class="sxs-lookup"><span data-stu-id="01627-120">Set Safety factor to '1'.</span></span>
    * <span data-ttu-id="01627-121">Este es el factor que se usa para calcular la cantidad adicional de existencias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="01627-121">This is the factor that is used to calculate additional quantity of safety stock.</span></span>  
10. <span data-ttu-id="01627-122">En el campo Días por delante, especifique "30".</span><span class="sxs-lookup"><span data-stu-id="01627-122">In the Days ahead field, enter '30'.</span></span>
    * <span data-ttu-id="01627-123">Este es el número de días anteriores a la fecha de cálculo de la cantidad kanban que se incluye en el cálculo de la demanda.</span><span class="sxs-lookup"><span data-stu-id="01627-123">This is the number of days prior to the kanban quantity calculation date that is included in the demand calculation.</span></span>  
11. <span data-ttu-id="01627-124">En el campo Días por detrás, especifique "30".</span><span class="sxs-lookup"><span data-stu-id="01627-124">In the Days behind field, enter '30'.</span></span>
    * <span data-ttu-id="01627-125">Este es el número de días posteriores a la fecha de cálculo de la cantidad kanban que se incluye en el cálculo de la demanda.</span><span class="sxs-lookup"><span data-stu-id="01627-125">This is the number of days forward from the kanban quantity calculation date that is included in the demand calculation.</span></span>  <span data-ttu-id="01627-126">La fórmula usada para el cálculo muestra los valores reales.</span><span class="sxs-lookup"><span data-stu-id="01627-126">The formula used for the calculation is shown with the actual values.</span></span> <span data-ttu-id="01627-127">Por ejemplo, Cantidad kanban = ((Demanda diaria promedio x plazo x 2.00) / Cantidad de producto por unidad de gestión de material) + 1</span><span class="sxs-lookup"><span data-stu-id="01627-127">For example,  Kanban quantity = ((Average daily demand x lead time x 2.00) / Product quantity per handling unit) + 1</span></span>  
12. <span data-ttu-id="01627-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="01627-128">Close the page.</span></span>

## <a name="add-the-kanban-quantity-calculation-policy-to-a-kanban-rule"></a><span data-ttu-id="01627-129">Adición de una directiva de cálculo de cantidad kanban a una regla kanban</span><span class="sxs-lookup"><span data-stu-id="01627-129">Add the kanban quantity calculation policy to a kanban rule</span></span>
1. <span data-ttu-id="01627-130">Vaya a Gestión de información de productos > Producción ajustada > Reglas kanban.</span><span class="sxs-lookup"><span data-stu-id="01627-130">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="01627-131">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="01627-131">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="01627-132">Seleccione la regla kanban 000020 para este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="01627-132">Select kanban rule 000020 for this procedure.</span></span>  
3. <span data-ttu-id="01627-133">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="01627-133">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="01627-134">Expanda la sección Directivas de cálculo de cantidad kanban.</span><span class="sxs-lookup"><span data-stu-id="01627-134">Toggle the expansion of the Kanban quantity calculation policies section.</span></span>
5. <span data-ttu-id="01627-135">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="01627-135">Click Add.</span></span>
    * <span data-ttu-id="01627-136">Agregue la directiva de cálculo de cantidad kanban que acaba de crear en la subtarea anterior.</span><span class="sxs-lookup"><span data-stu-id="01627-136">Add the kanban quantity calculation policy that you have just created in the previous sub-task.</span></span>  
6. <span data-ttu-id="01627-137">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="01627-137">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="01627-138">En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="01627-138">In the Name field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="01627-139">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="01627-139">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="01627-140">Seleccione la directiva Speaker2016 que acaba de crear en la subtarea anterior.</span><span class="sxs-lookup"><span data-stu-id="01627-140">Select the policy Speaker2016 that you have just created in the previous sub-task.</span></span>  

