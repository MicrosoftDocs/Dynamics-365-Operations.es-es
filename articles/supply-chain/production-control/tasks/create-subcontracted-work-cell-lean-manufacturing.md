---
title: Crear una celda de trabajo subcontratado para lean manufacturing (producción ajustada)
description: Para modelar trabajo subcontratado para lean manufacturing, debe crear una celda de trabajo que esté asociada al proveedor que proporciona el trabajo.
author: cvocph
manager: tfehr
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 86838eb81f42b0f930f3989f7edfa5ee724bd05e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006900"
---
# <a name="create-a-subcontracted-work-cell-for-lean-manufacturing"></a><span data-ttu-id="8e4c6-103">Crear una celda de trabajo subcontratado para lean manufacturing (producción ajustada)</span><span class="sxs-lookup"><span data-stu-id="8e4c6-103">Create a subcontracted work cell for lean manufacturing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8e4c6-104">Para modelar trabajo subcontratado para lean manufacturing, debe crear una celda de trabajo que esté asociada al proveedor que proporciona el trabajo.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-104">To model subcontracted work for lean manufacturing, you must create a work cell that is associated with the vendor that provides the work.</span></span> <span data-ttu-id="8e4c6-105">Se vincula a una celda de trabajo subcontratada al proveedor a través de la asociación de un recurso del tipo proveedor.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-105">A subcontracted work cell is linked to the vendor through the association of a resource of the Vendor type.</span></span> <span data-ttu-id="8e4c6-106">Si ejecuta este registro en la empresa de demostración USMF, puede seleccionar el identificador del proveedor 1002 y el sitio 1.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-106">If you play this recording in the USMF demo company, you can select vendor account ID 1002 and site 1.</span></span>


## <a name="create-a-vendor-resource"></a><span data-ttu-id="8e4c6-107">Crear un recurso de proveedores</span><span class="sxs-lookup"><span data-stu-id="8e4c6-107">Create a vendor resource</span></span>
1. <span data-ttu-id="8e4c6-108">Vaya a Recursos.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-108">Go to Resources.</span></span>
2. <span data-ttu-id="8e4c6-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-109">Click New.</span></span>
3. <span data-ttu-id="8e4c6-110">En el campo Recurso, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-110">In the Resource field, type a value.</span></span>
4. <span data-ttu-id="8e4c6-111">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="8e4c6-112">En el campo Tipo, seleccione el tipo "Proveedor".</span><span class="sxs-lookup"><span data-stu-id="8e4c6-112">In the Type field, select 'Vendor'.</span></span>
6. <span data-ttu-id="8e4c6-113">En el campo Proveedor, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-113">In the Vendor field, click the drop-down button to open the lookup.</span></span>

## <a name="create-the-resource-group"></a><span data-ttu-id="8e4c6-114">Crear el grupo de recursos</span><span class="sxs-lookup"><span data-stu-id="8e4c6-114">Create the resource group</span></span>
1. <span data-ttu-id="8e4c6-115">Vaya a Grupos de recursos.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-115">Go to Resource groups.</span></span>
2. <span data-ttu-id="8e4c6-116">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-116">Click New.</span></span>
3. <span data-ttu-id="8e4c6-117">En el campo Grupo de recursos, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-117">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="8e4c6-118">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-118">In the Description field, type a value.</span></span>
5. <span data-ttu-id="8e4c6-119">En el campo Sitio, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-119">In the Site field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="8e4c6-120">Seleccione el sitio al debe asignarse la celda de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-120">Select the site that the work cell should be allocated to.</span></span> <span data-ttu-id="8e4c6-121">En teoría, un sitio puede representar un solo sitio que opera un proveedor.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-121">In theory, a site can represent a single site that is operated by a vendor.</span></span> <span data-ttu-id="8e4c6-122">Sin embargo, en la mayoría de los casos, solo los recursos subcontratados se asignan al sitio que solicita el trabajo subcontratado.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-122">However, in most cases, subcontracted resources are just allocated to the site that orders the subcontracted work.</span></span> <span data-ttu-id="8e4c6-123">Tenga en cuenta que los almacenes de entrada y salida de celdas de trabajo subcontratadas deben encontrarse en el mismo sitio.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-123">Note that the input and output warehouses of subcontracted work cells must be on the same site.</span></span>  
6. <span data-ttu-id="8e4c6-124">En el campo Sitio, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-124">In the Site field, type a value.</span></span>
7. <span data-ttu-id="8e4c6-125">@SysTaskRecorder: _RequestClose</span><span class="sxs-lookup"><span data-stu-id="8e4c6-125">@SysTaskRecorder:_RequestClose</span></span>
8. <span data-ttu-id="8e4c6-126">Seleccione o desactive la casilla Celda de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-126">Select or clear the Work cell check box.</span></span>
9. <span data-ttu-id="8e4c6-127">En el campo Almacén de entrada, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-127">In the Input warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="8e4c6-128">Seleccione el almacén y la ubicación que se usan para organizar el material para la celda de trabajo que administra el proveedor.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-128">Select the warehouse and location that are used to stage the material for the vendor-managed work cell.</span></span> <span data-ttu-id="8e4c6-129">En muchos casos, el almacén y la ubicación se crean mediante un almacén separado por proveedor y una ubicación por celda de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-129">In many cases, the warehouse and location are modeled by using a separate warehouse per vendor and one location per work cell.</span></span>  
10. <span data-ttu-id="8e4c6-130">En el campo Ubicación de entrada, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-130">In the Input location field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="8e4c6-131">En el campo Almacén de salida, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-131">In the Output warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="8e4c6-132">Definir el almacén y la ubicación donde se envía material cuando las actividades subcontratadas de la celda de trabajo se registran.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-132">Define the warehouse and location where the material is posted when the subcontracted activities of the work cell are posted.</span></span> <span data-ttu-id="8e4c6-133">El almacén y la ubicación pueden estar en el sitio del proveedor si el proveedor registra trabajos kanban.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-133">The warehouse and location can be at the vendor site if the vendor reports the kanban jobs.</span></span> <span data-ttu-id="8e4c6-134">De manera alternativa, el almacén y la ubicación pueden ser la ubicación de recepción asociada al siguiente paso del flujo de producción.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-134">Alternatively, the warehouse and location can be the receiving location that is associated with the next step of the production flow.</span></span>  
12. <span data-ttu-id="8e4c6-135">En el campo Ubicación de salida, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-135">In the Output location field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="8e4c6-136">Expanda o contraiga la sección Calendarios.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-136">Expand or collapse the Calendars section.</span></span>
14. <span data-ttu-id="8e4c6-137">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-137">Click Add.</span></span>
15. <span data-ttu-id="8e4c6-138">En el campo Calendario, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-138">In the Calendar field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="8e4c6-139">Asocie el horario de trabajo de la celda de trabajo con el grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-139">Associate the working time calendar of the work cell with the resource group.</span></span> <span data-ttu-id="8e4c6-140">Para los recursos críticos, se recomienda que defina calendarios específicos que representen los horarios de trabajo precisos y las capacidades relacionadas de la celda de trabajo o el sitio del proveedor.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-140">For critical resources, we recommend that you define specific calendars that represent the exact working times and related capacities of the work cell or vendor site.</span></span>  
16. <span data-ttu-id="8e4c6-141">Expanda o contraiga la sección Recursos.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-141">Expand or collapse the Resources section.</span></span>
17. <span data-ttu-id="8e4c6-142">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-142">Click Add.</span></span>
    * <span data-ttu-id="8e4c6-143">Un grupo de recursos subcontratado debe tener un recurso asociado del tipo proveedor que vincule el grupo de recursos a la cuenta de proveedor.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-143">A subcontracted resource group must have an associated resource of the Vendor type that links the resource group to the vendor account.</span></span>  
18. <span data-ttu-id="8e4c6-144">En el campo Recursos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-144">In the Resource field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="8e4c6-145">Seleccione o especifique el recurso de proveedor que ha creado en la subtarea anterior.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-145">Select or enter the vendor resource that you created in the previous sub-task.</span></span>  
19. <span data-ttu-id="8e4c6-146">Expanda o contraiga la sección Capacidad de la celda de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-146">Expand or collapse the Work cell capacity section.</span></span>
20. <span data-ttu-id="8e4c6-147">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-147">Click Add.</span></span>
    * <span data-ttu-id="8e4c6-148">Una celda de trabajo debe tener una capacidad definida.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-148">A work cell must have a defined capacity.</span></span> <span data-ttu-id="8e4c6-149">En este ejemplo, creamos una capacidad de rendimiento de 100 piezas por día laborable estándar.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-149">In this example, we create a throughput capacity of 100 pieces per standard workday.</span></span>  
21. <span data-ttu-id="8e4c6-150">En el campo Modelo de flujo de producción, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-150">In the Production flow model field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="8e4c6-151">En el campo Período de capacidad, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-151">In the Capacity period field, select an option.</span></span>
23. <span data-ttu-id="8e4c6-152">En el campo Cantidad promedio de proceso, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-152">In the Average throughput quantity field, enter a number.</span></span>
24. <span data-ttu-id="8e4c6-153">En el campo Unidad, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-153">In the Unit field, click the drop-down button to open the lookup.</span></span>
25. <span data-ttu-id="8e4c6-154">Resuelva los cambios en la unidad.</span><span class="sxs-lookup"><span data-stu-id="8e4c6-154">ResolveChanges the Unit.</span></span>

