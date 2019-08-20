---
title: Completar la configuración básica de un producto maestro liberado
description: En este tema se muestra cómo completar la configuración mínima requerida para poder usar el producto maestro en versiones de L. MAT.
author: ShylaThompson
manager: AnnBe
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bd7e02c9aea17fbc3312660d0e50cd8bbf39aa3d
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845026"
---
# <a name="complete-basic-setup-of-a-released-product-master"></a><span data-ttu-id="2adfa-103">Completar la configuración básica de un producto maestro liberado</span><span class="sxs-lookup"><span data-stu-id="2adfa-103">Complete basic setup of a released product master</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2adfa-104">En este tema se muestra cómo completar la configuración mínima requerida para poder usar el producto maestro en versiones de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="2adfa-104">This topic shows how to complete the minimum setup that is required before the product master can be used in BOM versions.</span></span>

<span data-ttu-id="2adfa-105">Este es el tercer procedimiento de ocho que explica cómo crear combinaciones para la configuración basada en dimensiones.</span><span class="sxs-lookup"><span data-stu-id="2adfa-105">This is the third procedure out of eight which explains how to build combinations for dimension-based configuration.</span></span> <span data-ttu-id="2adfa-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="2adfa-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="2adfa-107">Vaya a **Panel de navegación > Módulos > Gestión de información de productos > Productos > Productos emitidos**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-107">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="2adfa-108">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="2adfa-108">In the list, find and select the desired record.</span></span> <span data-ttu-id="2adfa-109">Seleccione el producto maestro que ha emitido en el segundo procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2adfa-109">Select the product master that you have released in the second procedure.</span></span> <span data-ttu-id="2adfa-110">Este producto maestro se crea con la tecnología de configuración basada en dimensiones.</span><span class="sxs-lookup"><span data-stu-id="2adfa-110">This product master is created with the dimension-based configuration technology.</span></span>  
3. <span data-ttu-id="2adfa-111">En el panel de acciones, seleccione **Producto**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-111">On the Action Pane, select **Product**.</span></span>
4. <span data-ttu-id="2adfa-112">Seleccione **Grupos de dimensiones** para abrir el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2adfa-112">Select **Dimension groups** to open the drop dialog.</span></span>
5. <span data-ttu-id="2adfa-113">En el campo **Grupo de dimensiones de almacenamiento**, haga clic en el botón de la lista desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2adfa-113">In the **Storage dimension group** field, select the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="2adfa-114">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="2adfa-114">In the list, find and select the desired record.</span></span> <span data-ttu-id="2adfa-115">El grupo de dimensiones de almacenamiento determina qué dimensiones de almacenamiento se usan para la transacción de producto.</span><span class="sxs-lookup"><span data-stu-id="2adfa-115">The storage dimension group determines which storage dimensions are used for product transaction.</span></span> <span data-ttu-id="2adfa-116">Seleccione **Sitio** para este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2adfa-116">Select **Site** for this procedure.</span></span>  
7. <span data-ttu-id="2adfa-117">En el campo **Grupo de dimensiones de seguimiento**, seleccione en el botón de la lista desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2adfa-117">In the **Tracking dimension group** field, select the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="2adfa-118">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="2adfa-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="2adfa-119">El grupo de dimensiones de seguimiento determina qué dimensiones de seguimiento se usan para la transacción de producto.</span><span class="sxs-lookup"><span data-stu-id="2adfa-119">The tracking dimension group determines which tracking dimensions are used for product transaction.</span></span> <span data-ttu-id="2adfa-120">Seleccione **Ninguno** para este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2adfa-120">Select **None** for this procedure.</span></span>  
9. <span data-ttu-id="2adfa-121">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-121">Click **OK**.</span></span>
10. <span data-ttu-id="2adfa-122">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-122">Click **Edit**.</span></span>
11. <span data-ttu-id="2adfa-123">En el campo **Grupo de modelos de artículo**, seleccione el botón de la lista desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2adfa-123">In the **Item model group** field, select the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="2adfa-124">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="2adfa-124">In the list, find and select the desired record.</span></span> <span data-ttu-id="2adfa-125">Los grupos de modelos de artículos contienen ajustes que determinan la forma de controlar y gestionar artículos en emisiones y recepciones de artículos.</span><span class="sxs-lookup"><span data-stu-id="2adfa-125">Item model groups contain settings that determine how items are controlled and handled on item receipts and issues.</span></span> <span data-ttu-id="2adfa-126">También determina la forma de calcular el consumo de los artículos.</span><span class="sxs-lookup"><span data-stu-id="2adfa-126">They also determine how item consumption is calculated.</span></span> <span data-ttu-id="2adfa-127">Seleccione **FIFO** para este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2adfa-127">Select **FIFO** for this procedure.</span></span>  
13. <span data-ttu-id="2adfa-128">Expanda la sección **Administrar costes**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-128">Expand the **Manage costs** section.</span></span>
14. <span data-ttu-id="2adfa-129">En el campo **Grupo de artículos**, seleccione el botón de la lista desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2adfa-129">In the **Item group** field, select the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="2adfa-130">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="2adfa-130">In the list, find and select the desired record.</span></span> <span data-ttu-id="2adfa-131">Los grupos de artículos se utilizan para administrar el inventario dividiendo los artículos en grupos.</span><span class="sxs-lookup"><span data-stu-id="2adfa-131">Item groups are used to manage inventory by dividing inventory items into groups.</span></span> <span data-ttu-id="2adfa-132">Seleccione **CarAudio** para este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2adfa-132">Select **CarAudio** for this procedure.</span></span>  
16. <span data-ttu-id="2adfa-133">En el panel de acciones, haga clic en **Plan**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-133">On the Action Pane, select **Plan**.</span></span>
17. <span data-ttu-id="2adfa-134">Seleccione **Configuración predeterminada de pedido**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-134">Select **Default order settings**.</span></span>
18. <span data-ttu-id="2adfa-135">En el campo **Tipo de pedido predeterminado**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="2adfa-135">In the **Default order type field**, select an option.</span></span> <span data-ttu-id="2adfa-136">Seleccione **Producción** para especificar que la opción de suministro predeterminado para este producto maestro sea producirlo.</span><span class="sxs-lookup"><span data-stu-id="2adfa-136">Select **Production** to specify that the default supply option for this product master is to produce it.</span></span>  
19. <span data-ttu-id="2adfa-137">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-137">Select **Save**.</span></span>
20. <span data-ttu-id="2adfa-138">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="2adfa-138">Close the page.</span></span>
21. <span data-ttu-id="2adfa-139">Cierre el formulario **Detalles de producto emitido**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-139">Close the **Released product details** form.</span></span>

