---
title: Crear una lista de materiales para un producto maestro basado en dimensiones
description: Para este procedimiento, debe tener completado las 4 guías anteriores de esta secuencia de ocho registros.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ffe30f1b5aae3e954b527e84648f4dbb4b181513
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4986913"
---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a><span data-ttu-id="3f806-103">Crear una lista de materiales para un producto maestro basado en dimensiones</span><span class="sxs-lookup"><span data-stu-id="3f806-103">Create a bill of materials for a dimension-based product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3f806-104">Para este procedimiento, debe tener completado las 4 guías anteriores de esta secuencia de ocho registros.</span><span class="sxs-lookup"><span data-stu-id="3f806-104">For this procedure you should have completed the previous 4 guides in this sequence of eight recordings.</span></span> <span data-ttu-id="3f806-105">Los primeros 4 registros configuraron datos necesarios para completar este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="3f806-105">The first 4 recordings set up data that is required to complete this procedure.</span></span> <span data-ttu-id="3f806-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="3f806-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="3f806-107">Esta tarea la gestiona normalmente el diseñador de productos.</span><span class="sxs-lookup"><span data-stu-id="3f806-107">This task is typically handled by the product designer.</span></span>


## <a name="select-the-product"></a><span data-ttu-id="3f806-108">Seleccionar el producto</span><span class="sxs-lookup"><span data-stu-id="3f806-108">Select the product</span></span>
1. <span data-ttu-id="3f806-109">Haga clic en Mantenimiento de producto emitido.</span><span class="sxs-lookup"><span data-stu-id="3f806-109">Click Released product maintenance.</span></span>
2. <span data-ttu-id="3f806-110">Haga clic en Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="3f806-110">Click Released products.</span></span>
3. <span data-ttu-id="3f806-111">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3f806-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="3f806-112">Busque el producto maestro liberado con la tecnología de configuración basada en dimensiones que ha creado en la primera guía de tareas de esta secuencia.</span><span class="sxs-lookup"><span data-stu-id="3f806-112">Find the released product master with dimension-based configuration technology that you created in the first task guide in this sequence.</span></span>  
4. <span data-ttu-id="3f806-113">En el panel de acciones, haga clic en Ingeniero.</span><span class="sxs-lookup"><span data-stu-id="3f806-113">On the Action Pane, click Engineer.</span></span>
5. <span data-ttu-id="3f806-114">Haga clic en Versiones de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="3f806-114">Click BOM versions.</span></span>

## <a name="create-new-bom-and-bom-version"></a><span data-ttu-id="3f806-115">Crear una L. MAT y una versión de L. MAT nuevas</span><span class="sxs-lookup"><span data-stu-id="3f806-115">Create new BOM and BOM version</span></span>
1. <span data-ttu-id="3f806-116">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="3f806-116">Click New.</span></span>
2. <span data-ttu-id="3f806-117">Haga clic en L. MAT y versión de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="3f806-117">Click BOM and BOM version.</span></span>
3. <span data-ttu-id="3f806-118">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3f806-118">In the Name field, type a value.</span></span>
    * <span data-ttu-id="3f806-119">Configuración de un sitio</span><span class="sxs-lookup"><span data-stu-id="3f806-119">Setting a site</span></span>  
    * <span data-ttu-id="3f806-120">En este procedimiento no establecemos un sitio específico para la L. MAT.</span><span class="sxs-lookup"><span data-stu-id="3f806-120">In this procedure we don't set a specific site for the BOM.</span></span>  
4. <span data-ttu-id="3f806-121">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3f806-121">Click OK.</span></span>
5. <span data-ttu-id="3f806-122">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="3f806-122">Click New.</span></span>
    * <span data-ttu-id="3f806-123">En este procedimiento agregaremos cuatro líneas a la L. MAT.</span><span class="sxs-lookup"><span data-stu-id="3f806-123">In this procedure we will add four lines to the BOM.</span></span> <span data-ttu-id="3f806-124">Dos líneas representan opciones de cable y dos líneas representan opciones de armario.</span><span class="sxs-lookup"><span data-stu-id="3f806-124">Two lines represent cable options and two lines represent cabinet options.</span></span>  
6. <span data-ttu-id="3f806-125">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3f806-125">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="3f806-126">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3f806-126">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="3f806-127">Seleccione el número de artículo A0001, Cables HDMI de 6.</span><span class="sxs-lookup"><span data-stu-id="3f806-127">Select item number A0001, HDMI 6' Cables.</span></span>  
8. <span data-ttu-id="3f806-128">En el campo L. MAT y versión de L. MAT, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3f806-128">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="3f806-129">Seleccione el grupo de configuración de cable creado en la guía 4 de esta secuencia.</span><span class="sxs-lookup"><span data-stu-id="3f806-129">Select the Cable configuration group created in guide 4 in this sequence.</span></span>  
9. <span data-ttu-id="3f806-130">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="3f806-130">Click New.</span></span>
    * <span data-ttu-id="3f806-131">Seleccione el número de artículo A0002, Cables HDMI de 12.</span><span class="sxs-lookup"><span data-stu-id="3f806-131">Select item number A0002, HDMI 12' Cables.</span></span>  
10. <span data-ttu-id="3f806-132">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3f806-132">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="3f806-133">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3f806-133">In the Item number field, enter or select a value.</span></span>
12. <span data-ttu-id="3f806-134">En el campo L. MAT y versión de L. MAT, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3f806-134">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="3f806-135">Seleccione el grupo de configuración de cable de nuevo.</span><span class="sxs-lookup"><span data-stu-id="3f806-135">Select the Cable configuration group again.</span></span>  
13. <span data-ttu-id="3f806-136">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="3f806-136">Click New.</span></span>
14. <span data-ttu-id="3f806-137">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3f806-137">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="3f806-138">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3f806-138">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="3f806-139">Seleccione el número de artículo D0002 Armario.</span><span class="sxs-lookup"><span data-stu-id="3f806-139">Select item number D0002 Cabinet.</span></span>  
16. <span data-ttu-id="3f806-140">En el campo L. MAT y versión de L. MAT, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3f806-140">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="3f806-141">Seleccione el grupo de configuración de armario para esta línea de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="3f806-141">Select the Cabinet configuration group for this BOM line.</span></span>  
17. <span data-ttu-id="3f806-142">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="3f806-142">Click New.</span></span>
18. <span data-ttu-id="3f806-143">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3f806-143">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="3f806-144">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3f806-144">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="3f806-145">Seleccione el número de artículo M0007 Armario estándar como la última línea de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="3f806-145">Select Item number M0007 StandardCabinet as the last BOM line.</span></span>  
20. <span data-ttu-id="3f806-146">En el campo L. MAT y versión de L. MAT, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3f806-146">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="3f806-147">Seleccione el grupo de configuración de armario para la última línea de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="3f806-147">Select the Cabinet configuration group for the laste BOM line.</span></span>  

## <a name="approve-and-activate"></a><span data-ttu-id="3f806-148">Aprobar y activar</span><span class="sxs-lookup"><span data-stu-id="3f806-148">Approve and activate</span></span>
1. <span data-ttu-id="3f806-149">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3f806-149">Close the page.</span></span>
2. <span data-ttu-id="3f806-150">Haga clic en Aprobar.</span><span class="sxs-lookup"><span data-stu-id="3f806-150">Click Approve.</span></span>
3. <span data-ttu-id="3f806-151">En el campo Aprobado por, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3f806-151">In the Approved by field, enter or select a value.</span></span>
4. <span data-ttu-id="3f806-152">Seleccione Sí en ¿Desea aprobar también la lista de materiales? .</span><span class="sxs-lookup"><span data-stu-id="3f806-152">Select Yes in the Do you also want to approve the bill of materials? field.</span></span>
5. <span data-ttu-id="3f806-153">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3f806-153">Click OK.</span></span>
6. <span data-ttu-id="3f806-154">Haga clic en Activar.</span><span class="sxs-lookup"><span data-stu-id="3f806-154">Click Activate.</span></span>

