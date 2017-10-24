--- 
title: "Completar la configuración básica de un producto maestro liberado"
description: "Este procedimiento muestra cómo completar la configuración mínima requerida para poder usar el producto maestro en versiones de L. MAT."
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 35617f5bec877fbe8a89d015eda16a66ee14d335
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="complete-basic-setup-of-a-released-product-master"></a><span data-ttu-id="35bcf-103">Completar la configuración básica de un producto maestro liberado</span><span class="sxs-lookup"><span data-stu-id="35bcf-103">Complete basic setup of a released product master</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="35bcf-104">Este procedimiento muestra cómo completar la configuración mínima requerida para poder usar el producto maestro en versiones de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="35bcf-104">This procedure shows how to complete the minimum setup that is required before the product master can be used in BOM versions.</span></span>

<span data-ttu-id="35bcf-105">Este es el tercer procedimiento de ocho que explica cómo crear combinaciones para la configuración basada en dimensiones.</span><span class="sxs-lookup"><span data-stu-id="35bcf-105">This is the third procedure out of eight which explains how to build combinations for dimension-based configuration.</span></span> <span data-ttu-id="35bcf-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="35bcf-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="35bcf-107">Vaya a Gestión de información de productos > Productos > Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="35bcf-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="35bcf-108">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="35bcf-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="35bcf-109">Seleccione el producto maestro que ha emitido en el segundo procedimiento.</span><span class="sxs-lookup"><span data-stu-id="35bcf-109">Select the product master that you have released in the second procedure.</span></span> <span data-ttu-id="35bcf-110">Este producto maestro se crea con la tecnología de configuración basada en dimensiones.</span><span class="sxs-lookup"><span data-stu-id="35bcf-110">This product master is created with the dimension-based configuration technology.</span></span>  
3. <span data-ttu-id="35bcf-111">En el panel de acciones, haga clic en Producto.</span><span class="sxs-lookup"><span data-stu-id="35bcf-111">On the Action Pane, click Product.</span></span>
4. <span data-ttu-id="35bcf-112">Haga clic en Grupos de dimensiones para abrir el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="35bcf-112">Click Dimension groups to open the drop dialog.</span></span>
5. <span data-ttu-id="35bcf-113">En el campo Grupo de dimensiones de almacenamiento, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="35bcf-113">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="35bcf-114">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="35bcf-114">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="35bcf-115">El grupo de dimensiones de almacenamiento determina qué dimensiones de almacenamiento se usan para la transacción de producto.</span><span class="sxs-lookup"><span data-stu-id="35bcf-115">The storage dimension group determines which storage dimensions are used for product transaction.</span></span> <span data-ttu-id="35bcf-116">Seleccione Sitio para este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="35bcf-116">Select Site for this procedure.</span></span>  
7. <span data-ttu-id="35bcf-117">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="35bcf-117">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="35bcf-118">En el campo Grupo de dimensiones de seguimiento, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="35bcf-118">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="35bcf-119">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="35bcf-119">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="35bcf-120">El grupo de dimensiones de seguimiento determina qué dimensiones de seguimiento se usan para la transacción de producto.</span><span class="sxs-lookup"><span data-stu-id="35bcf-120">The tracking dimension group determines which tracking dimensions are used for product transaction.</span></span> <span data-ttu-id="35bcf-121">Seleccione Ninguno para este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="35bcf-121">Select None for this procedure.</span></span>  
10. <span data-ttu-id="35bcf-122">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="35bcf-122">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="35bcf-123">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="35bcf-123">Click OK.</span></span>
12. <span data-ttu-id="35bcf-124">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="35bcf-124">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="35bcf-125">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="35bcf-125">Click Edit.</span></span>
    * <span data-ttu-id="35bcf-126">Abra el formulario Detalles de producto emitido para continuar con la tarea de configuración.</span><span class="sxs-lookup"><span data-stu-id="35bcf-126">Open the Released product details form to continue the setup task.</span></span>  
14. <span data-ttu-id="35bcf-127">En el campo Grupo de modelos de artículo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="35bcf-127">In the Item model group field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="35bcf-128">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="35bcf-128">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="35bcf-129">Los grupos de modelos de artículos contienen ajustes que determinan la forma de controlar y gestionar artículos en emisiones y recepciones de artículos.</span><span class="sxs-lookup"><span data-stu-id="35bcf-129">Item model groups contain settings that determine how items are controlled and handled on item receipts and issues.</span></span> <span data-ttu-id="35bcf-130">También determina la forma de calcular el consumo de los artículos.</span><span class="sxs-lookup"><span data-stu-id="35bcf-130">They also determine how item consumption is calculated.</span></span> <span data-ttu-id="35bcf-131">Seleccione FIFO para este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="35bcf-131">Select   FIFO for this procedure.</span></span>  
16. <span data-ttu-id="35bcf-132">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="35bcf-132">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="35bcf-133">Expanda o contraiga la sección Gestionar costes.</span><span class="sxs-lookup"><span data-stu-id="35bcf-133">Expand or collapse the Manage costs section.</span></span>
18. <span data-ttu-id="35bcf-134">En el campo Grupo de artículos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="35bcf-134">In the Item group field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="35bcf-135">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="35bcf-135">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="35bcf-136">Los grupos de artículos se utilizan para administrar el inventario dividiendo los artículos en grupos.</span><span class="sxs-lookup"><span data-stu-id="35bcf-136">Item groups are used to manage inventory by dividing inventory items into groups.</span></span> <span data-ttu-id="35bcf-137">Seleccione CarAudio para este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="35bcf-137">Select   CarAudio for this procedure.</span></span>  
20. <span data-ttu-id="35bcf-138">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="35bcf-138">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="35bcf-139">En el panel de acciones, haga clic en Plan.</span><span class="sxs-lookup"><span data-stu-id="35bcf-139">On the Action Pane, click Plan.</span></span>
22. <span data-ttu-id="35bcf-140">Haga clic en Configuración predeterminada de pedido.</span><span class="sxs-lookup"><span data-stu-id="35bcf-140">Click Default order settings.</span></span>
23. <span data-ttu-id="35bcf-141">En el campo Tipo de pedido predeterminado, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="35bcf-141">In the Default order type field, select an option.</span></span>
    * <span data-ttu-id="35bcf-142">Seleccione Producción para especificar que la opción de suministro predeterminado para este producto maestro sea producirlo.</span><span class="sxs-lookup"><span data-stu-id="35bcf-142">Select Production to specify that the default supply option for this product master is to produce it.</span></span>  
24. <span data-ttu-id="35bcf-143">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="35bcf-143">Close the page.</span></span>
25. <span data-ttu-id="35bcf-144">Cierre el formulario Detalles de producto emitido.</span><span class="sxs-lookup"><span data-stu-id="35bcf-144">Close the Released product details form.</span></span>


