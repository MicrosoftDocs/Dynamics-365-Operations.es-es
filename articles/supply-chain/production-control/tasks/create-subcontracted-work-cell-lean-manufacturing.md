---
title: Crear una celda de trabajo subcontratado para lean manufacturing (producción ajustada)
description: Para modelar trabajo subcontratado para lean manufacturing, debe crear una celda de trabajo que esté asociada al proveedor que proporciona el trabajo.
author: cvocph
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0dc1e28202c42502cbec0f0066863d24d4396c88
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828907"
---
# <a name="create-a-subcontracted-work-cell-for-lean-manufacturing"></a><span data-ttu-id="ec5f7-103">Crear una celda de trabajo subcontratado para lean manufacturing (producción ajustada)</span><span class="sxs-lookup"><span data-stu-id="ec5f7-103">Create a subcontracted work cell for lean manufacturing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ec5f7-104">Para modelar trabajo subcontratado para lean manufacturing, debe crear una celda de trabajo que esté asociada al proveedor que proporciona el trabajo.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-104">To model subcontracted work for lean manufacturing, you must create a work cell that is associated with the vendor that provides the work.</span></span> <span data-ttu-id="ec5f7-105">Se vincula a una celda de trabajo subcontratada al proveedor a través de la asociación de un recurso del tipo proveedor.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-105">A subcontracted work cell is linked to the vendor through the association of a resource of the Vendor type.</span></span> <span data-ttu-id="ec5f7-106">Si ejecuta este registro en la empresa de demostración USMF, puede seleccionar el identificador del proveedor 1002 y el sitio 1.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-106">If you play this recording in the USMF demo company, you can select vendor account ID 1002 and site 1.</span></span>


## <a name="create-a-vendor-resource"></a><span data-ttu-id="ec5f7-107">Crear un recurso de proveedores</span><span class="sxs-lookup"><span data-stu-id="ec5f7-107">Create a vendor resource</span></span>
1. <span data-ttu-id="ec5f7-108">Vaya a Recursos.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-108">Go to Resources.</span></span>
2. <span data-ttu-id="ec5f7-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-109">Click New.</span></span>
3. <span data-ttu-id="ec5f7-110">En el campo Recurso, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-110">In the Resource field, type a value.</span></span>
4. <span data-ttu-id="ec5f7-111">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="ec5f7-112">En el campo Tipo, seleccione el tipo "Proveedor".</span><span class="sxs-lookup"><span data-stu-id="ec5f7-112">In the Type field, select 'Vendor'.</span></span>
6. <span data-ttu-id="ec5f7-113">En el campo Proveedor, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-113">In the Vendor field, click the drop-down button to open the lookup.</span></span>

## <a name="create-the-resource-group"></a><span data-ttu-id="ec5f7-114">Crear el grupo de recursos</span><span class="sxs-lookup"><span data-stu-id="ec5f7-114">Create the resource group</span></span>
1. <span data-ttu-id="ec5f7-115">Vaya a Grupos de recursos.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-115">Go to Resource groups.</span></span>
2. <span data-ttu-id="ec5f7-116">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-116">Click New.</span></span>
3. <span data-ttu-id="ec5f7-117">En el campo Grupo de recursos, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-117">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="ec5f7-118">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-118">In the Description field, type a value.</span></span>
5. <span data-ttu-id="ec5f7-119">En el campo Sitio, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-119">In the Site field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ec5f7-120">Seleccione el sitio al debe asignarse la celda de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-120">Select the site that the work cell should be allocated to.</span></span> <span data-ttu-id="ec5f7-121">En teoría, un sitio puede representar un solo sitio que opera un proveedor.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-121">In theory, a site can represent a single site that is operated by a vendor.</span></span> <span data-ttu-id="ec5f7-122">Sin embargo, en la mayoría de los casos, solo los recursos subcontratados se asignan al sitio que solicita el trabajo subcontratado.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-122">However, in most cases, subcontracted resources are just allocated to the site that orders the subcontracted work.</span></span> <span data-ttu-id="ec5f7-123">Tenga en cuenta que los almacenes de entrada y salida de celdas de trabajo subcontratadas deben encontrarse en el mismo sitio.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-123">Note that the input and output warehouses of subcontracted work cells must be on the same site.</span></span>  
6. <span data-ttu-id="ec5f7-124">En el campo Sitio, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-124">In the Site field, type a value.</span></span>
7. <span data-ttu-id="ec5f7-125">@SysTaskRecorder: _RequestClose</span><span class="sxs-lookup"><span data-stu-id="ec5f7-125">@SysTaskRecorder:_RequestClose</span></span>
8. <span data-ttu-id="ec5f7-126">Seleccione o desactive la casilla Celda de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-126">Select or clear the Work cell check box.</span></span>
9. <span data-ttu-id="ec5f7-127">En el campo Almacén de entrada, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-127">In the Input warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ec5f7-128">Seleccione el almacén y la ubicación que se usan para organizar el material para la celda de trabajo que administra el proveedor.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-128">Select the warehouse and location that are used to stage the material for the vendor-managed work cell.</span></span> <span data-ttu-id="ec5f7-129">En muchos casos, el almacén y la ubicación se crean mediante un almacén separado por proveedor y una ubicación por celda de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-129">In many cases, the warehouse and location are modeled by using a separate warehouse per vendor and one location per work cell.</span></span>  
10. <span data-ttu-id="ec5f7-130">En el campo Ubicación de entrada, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-130">In the Input location field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="ec5f7-131">En el campo Almacén de salida, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-131">In the Output warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ec5f7-132">Definir el almacén y la ubicación donde se envía material cuando las actividades subcontratadas de la celda de trabajo se registran.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-132">Define the warehouse and location where the material is posted when the subcontracted activities of the work cell are posted.</span></span> <span data-ttu-id="ec5f7-133">El almacén y la ubicación pueden estar en el sitio del proveedor si el proveedor registra trabajos kanban.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-133">The warehouse and location can be at the vendor site if the vendor reports the kanban jobs.</span></span> <span data-ttu-id="ec5f7-134">De manera alternativa, el almacén y la ubicación pueden ser la ubicación de recepción asociada al siguiente paso del flujo de producción.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-134">Alternatively, the warehouse and location can be the receiving location that is associated with the next step of the production flow.</span></span>  
12. <span data-ttu-id="ec5f7-135">En el campo Ubicación de salida, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-135">In the Output location field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="ec5f7-136">Expanda o contraiga la sección Calendarios.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-136">Expand or collapse the Calendars section.</span></span>
14. <span data-ttu-id="ec5f7-137">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-137">Click Add.</span></span>
15. <span data-ttu-id="ec5f7-138">En el campo Calendario, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-138">In the Calendar field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ec5f7-139">Asocie el horario de trabajo de la celda de trabajo con el grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-139">Associate the working time calendar of the work cell with the resource group.</span></span> <span data-ttu-id="ec5f7-140">Para los recursos críticos, se recomienda que defina calendarios específicos que representen los horarios de trabajo precisos y las capacidades relacionadas de la celda de trabajo o el sitio del proveedor.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-140">For critical resources, we recommend that you define specific calendars that represent the exact working times and related capacities of the work cell or vendor site.</span></span>  
16. <span data-ttu-id="ec5f7-141">Expanda o contraiga la sección Recursos.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-141">Expand or collapse the Resources section.</span></span>
17. <span data-ttu-id="ec5f7-142">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-142">Click Add.</span></span>
    * <span data-ttu-id="ec5f7-143">Un grupo de recursos subcontratado debe tener un recurso asociado del tipo proveedor que vincule el grupo de recursos a la cuenta de proveedor.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-143">A subcontracted resource group must have an associated resource of the Vendor type that links the resource group to the vendor account.</span></span>  
18. <span data-ttu-id="ec5f7-144">En el campo Recursos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-144">In the Resource field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ec5f7-145">Seleccione o especifique el recurso de proveedor que ha creado en la subtarea anterior.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-145">Select or enter the vendor resource that you created in the previous sub-task.</span></span>  
19. <span data-ttu-id="ec5f7-146">Expanda o contraiga la sección Capacidad de la celda de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-146">Expand or collapse the Work cell capacity section.</span></span>
20. <span data-ttu-id="ec5f7-147">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-147">Click Add.</span></span>
    * <span data-ttu-id="ec5f7-148">Una celda de trabajo debe tener una capacidad definida.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-148">A work cell must have a defined capacity.</span></span> <span data-ttu-id="ec5f7-149">En este ejemplo, creamos una capacidad de rendimiento de 100 piezas por día laborable estándar.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-149">In this example, we create a throughput capacity of 100 pieces per standard workday.</span></span>  
21. <span data-ttu-id="ec5f7-150">En el campo Modelo de flujo de producción, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-150">In the Production flow model field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="ec5f7-151">En el campo Período de capacidad, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-151">In the Capacity period field, select an option.</span></span>
23. <span data-ttu-id="ec5f7-152">En el campo Cantidad promedio de proceso, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-152">In the Average throughput quantity field, enter a number.</span></span>
24. <span data-ttu-id="ec5f7-153">En el campo Unidad, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-153">In the Unit field, click the drop-down button to open the lookup.</span></span>
25. <span data-ttu-id="ec5f7-154">Resuelva los cambios en la unidad.</span><span class="sxs-lookup"><span data-stu-id="ec5f7-154">ResolveChanges the Unit.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]