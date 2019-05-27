---
title: Crear un producto semi-terminado (febrero de 2016)
description: Esta tarea se centra en crear un producto semi-terminado.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, InventItemPrice
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9caeae552471eed1cb1d8630f387ca31107fcece
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1567850"
---
# <a name="create-a-semi-finished-product-february-2016"></a><span data-ttu-id="1b88a-103">Crear un producto semi-terminado (febrero de 2016)</span><span class="sxs-lookup"><span data-stu-id="1b88a-103">Create a semi-finished product (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1b88a-104">Esta tarea se centra en crear un producto semi-terminado.</span><span class="sxs-lookup"><span data-stu-id="1b88a-104">This task focuses on creating a semi-finished product.</span></span> <span data-ttu-id="1b88a-105">Es la segunda tarea en las series de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="1b88a-105">It is the second task in the BOM calculation series.</span></span> <span data-ttu-id="1b88a-106">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="1b88a-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="1b88a-107">Vaya a Gestión de información de productos > Productos > Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="1b88a-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="1b88a-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="1b88a-108">Click New.</span></span>
3. <span data-ttu-id="1b88a-109">En el campo Número de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="1b88a-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="1b88a-110">Para este ejemplo, especifique BOM 2.</span><span class="sxs-lookup"><span data-stu-id="1b88a-110">For this example, type BOM_2.</span></span>  
4. <span data-ttu-id="1b88a-111">En el campo Grupo de modelos de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="1b88a-111">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="1b88a-112">Seleccione STD.</span><span class="sxs-lookup"><span data-stu-id="1b88a-112">Select STD.</span></span> <span data-ttu-id="1b88a-113">El STD representa el coste estándar y es el modelo más usado al trabajar con cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="1b88a-113">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="1b88a-114">En el campo Grupo de artículos, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="1b88a-114">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="1b88a-115">Por ejemplo, seleccione Audio.</span><span class="sxs-lookup"><span data-stu-id="1b88a-115">For example, select Audio.</span></span> <span data-ttu-id="1b88a-116">Esto no tiene aafecta de ninguna manera a los cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="1b88a-116">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="1b88a-117">En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="1b88a-117">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="1b88a-118">Seleccione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="1b88a-118">Select SiteWH.</span></span> <span data-ttu-id="1b88a-119">Para este ejemplo solo se usarán el Sitio y el Almacén.</span><span class="sxs-lookup"><span data-stu-id="1b88a-119">Only Site and Warehouse will be used for this example.</span></span>  
7. <span data-ttu-id="1b88a-120">En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="1b88a-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="1b88a-121">Las dimensiones de seguimiento no se usarán en este ejemplo, seleccione Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1b88a-121">Tracking dimensions will not be used for this example, select None.</span></span>  
8. <span data-ttu-id="1b88a-122">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="1b88a-122">Click OK.</span></span>
9. <span data-ttu-id="1b88a-123">En el panel de acciones, haga clic en Administrar inventario.</span><span class="sxs-lookup"><span data-stu-id="1b88a-123">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="1b88a-124">Haga clic en Configuración predeterminada de pedido.</span><span class="sxs-lookup"><span data-stu-id="1b88a-124">Click Default order settings.</span></span>
11. <span data-ttu-id="1b88a-125">En el campo Tipo de pedido predeterminado, seleccione "Producción".</span><span class="sxs-lookup"><span data-stu-id="1b88a-125">In the Default order type field, select 'Production'.</span></span>
    * <span data-ttu-id="1b88a-126">Dado que este es un producto semi-terminado que se generará, seleccione Producción.</span><span class="sxs-lookup"><span data-stu-id="1b88a-126">Because this is a semi-finished product that will be produced, select Production.</span></span>  
12. <span data-ttu-id="1b88a-127">En el campo Sitio de compra, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="1b88a-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="1b88a-128">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="1b88a-128">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="1b88a-129">En el campo Sitio de inventario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="1b88a-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="1b88a-130">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="1b88a-130">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="1b88a-131">En el campo Sitio de centas, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="1b88a-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="1b88a-132">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="1b88a-132">For this example, select Site 1.</span></span>  
15. <span data-ttu-id="1b88a-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="1b88a-133">Close the page.</span></span>
16. <span data-ttu-id="1b88a-134">En el panel de acciones, haga clic en Gestionar costes.</span><span class="sxs-lookup"><span data-stu-id="1b88a-134">On the Action Pane, click Manage costs.</span></span>
17. <span data-ttu-id="1b88a-135">Haga clic en Precio de artículo.</span><span class="sxs-lookup"><span data-stu-id="1b88a-135">Click Item price.</span></span>
18. <span data-ttu-id="1b88a-136">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="1b88a-136">Click New.</span></span>
19. <span data-ttu-id="1b88a-137">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1b88a-137">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="1b88a-138">En el campo Versión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="1b88a-138">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="1b88a-139">Para este ejemplo, seleccione Versión 10.</span><span class="sxs-lookup"><span data-stu-id="1b88a-139">For this example, select Version 10.</span></span>  
21. <span data-ttu-id="1b88a-140">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="1b88a-140">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="1b88a-141">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="1b88a-141">For this example, select Site 1.</span></span>  
22. <span data-ttu-id="1b88a-142">Establezca el Precio en "10".</span><span class="sxs-lookup"><span data-stu-id="1b88a-142">Set Price to '10'.</span></span>
    * <span data-ttu-id="1b88a-143">Para este ejemplo, escriba un precio de coste de 10.</span><span class="sxs-lookup"><span data-stu-id="1b88a-143">For this example, type a cost price of 10.</span></span>  
23. <span data-ttu-id="1b88a-144">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="1b88a-144">Click Save.</span></span>
24. <span data-ttu-id="1b88a-145">Haga clic en Activar precios pendientes.</span><span class="sxs-lookup"><span data-stu-id="1b88a-145">Click Activate pending price(s).</span></span>
25. <span data-ttu-id="1b88a-146">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="1b88a-146">Close the page.</span></span>
26. <span data-ttu-id="1b88a-147">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="1b88a-147">Close the page.</span></span>
27. <span data-ttu-id="1b88a-148">Haga clic en BOM_2 para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="1b88a-148">Click BOM_2 to open it.</span></span>
28. <span data-ttu-id="1b88a-149">Expanda la sección Administrar costes.</span><span class="sxs-lookup"><span data-stu-id="1b88a-149">Expand the Manage costs section.</span></span>
29. <span data-ttu-id="1b88a-150">En el campo Grupo de costes, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="1b88a-150">In the Cost group field, enter or select a value.</span></span>
    * <span data-ttu-id="1b88a-151">Para este ejemplo, seleccione Coste de grupo M1.</span><span class="sxs-lookup"><span data-stu-id="1b88a-151">For this example, select Cost group M1.</span></span>  
30. <span data-ttu-id="1b88a-152">Use el acceso directo para guardar un registro.</span><span class="sxs-lookup"><span data-stu-id="1b88a-152">Use the shortcut for saving a record.</span></span>
31. <span data-ttu-id="1b88a-153">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="1b88a-153">Close the page.</span></span>

