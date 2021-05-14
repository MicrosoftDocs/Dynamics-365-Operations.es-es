---
title: Crear una lista de materiales para un producto maestro basado en dimensiones
description: Para este procedimiento, debe tener completado las 4 guías anteriores de esta secuencia de ocho registros.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13053dd87242963586678b46c64493feb3383c4c
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920714"
---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a><span data-ttu-id="d4ae7-103">Crear una lista de materiales para un producto maestro basado en dimensiones</span><span class="sxs-lookup"><span data-stu-id="d4ae7-103">Create a bill of materials for a dimension-based product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d4ae7-104">Para este procedimiento, debe tener completado las 4 guías anteriores de esta secuencia de ocho registros.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-104">For this procedure you should have completed the previous 4 guides in this sequence of eight recordings.</span></span> <span data-ttu-id="d4ae7-105">Los primeros 4 registros configuraron datos necesarios para completar este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-105">The first 4 recordings set up data that is required to complete this procedure.</span></span> <span data-ttu-id="d4ae7-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="d4ae7-107">Esta tarea la gestiona normalmente el diseñador de productos.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-107">This task is typically handled by the product designer.</span></span>

## <a name="select-the-product"></a><span data-ttu-id="d4ae7-108">Seleccionar el producto</span><span class="sxs-lookup"><span data-stu-id="d4ae7-108">Select the product</span></span>

1. <span data-ttu-id="d4ae7-109">Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-109">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="d4ae7-110">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-110">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="d4ae7-111">Busque el producto maestro liberado con la tecnología de configuración basada en dimensiones que ha creado en la primera guía de tareas de esta secuencia.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-111">Find the released product master with dimension-based configuration technology that you created in the first task guide in this sequence.</span></span>  
1. <span data-ttu-id="d4ae7-112">En el panel de acciones, seleccione **Ingeniero**.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-112">On the Action Pane, select **Engineer**.</span></span>
1. <span data-ttu-id="d4ae7-113">Seleccione **Versiones de L. MAT**.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-113">Select **BOM versions**.</span></span>

## <a name="create-new-bom-and-bom-version"></a><span data-ttu-id="d4ae7-114">Crear una L. MAT y una versión de L. MAT nuevas</span><span class="sxs-lookup"><span data-stu-id="d4ae7-114">Create new BOM and BOM version</span></span>

1. <span data-ttu-id="d4ae7-115">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-115">Select **New**.</span></span>
1. <span data-ttu-id="d4ae7-116">Seleccione **L. MAT y versión de L. MAT**.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-116">Select **BOM and BOM version**.</span></span>
1. <span data-ttu-id="d4ae7-117">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-117">In the **Name** field, type a value.</span></span>
    * <span data-ttu-id="d4ae7-118">Configuración de un sitio</span><span class="sxs-lookup"><span data-stu-id="d4ae7-118">Setting a site</span></span>  
    * <span data-ttu-id="d4ae7-119">En este procedimiento no establecemos un sitio específico para la L. MAT.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-119">In this procedure we don't set a specific site for the BOM.</span></span>  
1. <span data-ttu-id="d4ae7-120">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-120">Select **OK**.</span></span>
1. <span data-ttu-id="d4ae7-121">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-121">Select **New**.</span></span>
    * <span data-ttu-id="d4ae7-122">En este procedimiento agregaremos cuatro líneas a la L. MAT.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-122">In this procedure we will add four lines to the BOM.</span></span> <span data-ttu-id="d4ae7-123">Dos líneas representan opciones de cable y dos líneas representan opciones de armario.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-123">Two lines represent cable options and two lines represent cabinet options.</span></span>  
1. <span data-ttu-id="d4ae7-124">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-124">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="d4ae7-125">En el campo **Número de artículo**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-125">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="d4ae7-126">Seleccione el número de artículo A0001, Cables HDMI de 6.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-126">Select item number A0001, HDMI 6' Cables.</span></span>  
1. <span data-ttu-id="d4ae7-127">En el campo **Grupo de configuración**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-127">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="d4ae7-128">Seleccione el grupo de configuración de cable creado en la guía 4 de esta secuencia.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-128">Select the cable configuration group created in guide 4 in this sequence.</span></span>  
1. <span data-ttu-id="d4ae7-129">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-129">Select **New**.</span></span>
    * <span data-ttu-id="d4ae7-130">Seleccione el número de artículo A0002, Cables HDMI de 12.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-130">Select item number A0002, HDMI 12' Cables.</span></span>  
1. <span data-ttu-id="d4ae7-131">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-131">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="d4ae7-132">En el campo **Número de artículo**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-132">In the **Item number** field, enter or select a value.</span></span>
1. <span data-ttu-id="d4ae7-133">En el campo **Grupo de configuración**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-133">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="d4ae7-134">Seleccione el grupo de configuración de cable de nuevo.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-134">Select the cable configuration group again.</span></span>  
1. <span data-ttu-id="d4ae7-135">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-135">Select **New**.</span></span>
1. <span data-ttu-id="d4ae7-136">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-136">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="d4ae7-137">En el campo **Número de artículo**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-137">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="d4ae7-138">Seleccione el número de artículo D0002 Armario.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-138">Select item number D0002 Cabinet.</span></span>  
1. <span data-ttu-id="d4ae7-139">En el campo **Grupo de configuración**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-139">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="d4ae7-140">Seleccione el grupo de configuración de armario para esta línea de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-140">Select the cabinet configuration group for this BOM line.</span></span>  
1. <span data-ttu-id="d4ae7-141">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-141">Select **New**.</span></span>
1. <span data-ttu-id="d4ae7-142">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-142">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="d4ae7-143">En el campo **Número de artículo**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-143">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="d4ae7-144">Seleccione el número de artículo M0007 Armario estándar como la última línea de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-144">Select Item number M0007 StandardCabinet as the last BOM line.</span></span>  
1. <span data-ttu-id="d4ae7-145">En el campo **Grupo de configuración**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-145">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="d4ae7-146">Seleccione el grupo de configuración de armario para la última línea de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-146">Select the Cabinet configuration group for the last BOM line.</span></span>  

## <a name="approve-and-activate"></a><span data-ttu-id="d4ae7-147">Aprobar y activar</span><span class="sxs-lookup"><span data-stu-id="d4ae7-147">Approve and activate</span></span>

1. <span data-ttu-id="d4ae7-148">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-148">Close the page.</span></span>
1. <span data-ttu-id="d4ae7-149">Seleccione **Aprobar**.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-149">Select **Approve**.</span></span>
1. <span data-ttu-id="d4ae7-150">En el campo **Aprobado por**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-150">In the **Approved by** field, enter or select a value.</span></span>
1. <span data-ttu-id="d4ae7-151">Seleccione *Sí* en **¿Desea aprobar también la lista de materiales?**.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-151">Select *Yes* in the **Do you also want to approve the bill of materials?** field.</span></span>
1. <span data-ttu-id="d4ae7-152">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-152">Select **OK**.</span></span>
1. <span data-ttu-id="d4ae7-153">Seleccione **Activar**.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-153">Select **Activate**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]