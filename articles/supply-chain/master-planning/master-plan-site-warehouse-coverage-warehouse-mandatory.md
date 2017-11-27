---
title: "Planificación maestra para cobertura de sitios y almacenes, almacén obligatorio"
description: "Este tema describe cómo se planifica un artículo que tiene el sitio y el almacén como dimensiones de cobertura. La dimensión de almacén es obligatoria."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2554
ms.assetid: 3211e95f-b91a-4d27-8d92-f328ae2bcf12
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: bc4b54b25edf0f1a47839e8a8253db5a8c595a8f
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-mandatory"></a><span data-ttu-id="65131-104">Planificación maestra para cobertura de sitios y almacenes, almacén obligatorio</span><span class="sxs-lookup"><span data-stu-id="65131-104">Master planning for site and warehouse coverage, warehouse mandatory</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="65131-105">Este tema describe cómo se planifica un artículo que tiene el sitio y el almacén como dimensiones de cobertura.</span><span class="sxs-lookup"><span data-stu-id="65131-105">This topic describes how an item that has site and warehouse as coverage dimensions is planned.</span></span> <span data-ttu-id="65131-106">La dimensión de almacén es obligatoria.</span><span class="sxs-lookup"><span data-stu-id="65131-106">The warehouse dimension is mandatory.</span></span>

<span data-ttu-id="65131-107">El escenario de planificación maestra implica las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="65131-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="65131-108">La dimensión del sitio está definida como obligatoria y se debe especificar en la transacción de demanda.</span><span class="sxs-lookup"><span data-stu-id="65131-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="65131-109">La dimensión de almacén está definida como obligatoria y se debe especificar en la transacción de demanda.</span><span class="sxs-lookup"><span data-stu-id="65131-109">The warehouse dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="65131-110">Las dimensiones de sitio y de almacén están definidas para la planificación de la cobertura.</span><span class="sxs-lookup"><span data-stu-id="65131-110">The site and warehouse dimensions are set for coverage planning.</span></span> <span data-ttu-id="65131-111">Se pueden configurar otras dimensiones también para la planificación de cobertura.</span><span class="sxs-lookup"><span data-stu-id="65131-111">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="65131-112">Sin embargo, no se ven afectadas por la funcionalidad de multisitio.</span><span class="sxs-lookup"><span data-stu-id="65131-112">However, they are not affected by the multisite functionality.</span></span>

<span data-ttu-id="65131-113">El gráfico siguiente ilustra cómo tiene lugar la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="65131-113">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="65131-114">Los parámetros a los que se hace referencia en el gráfico, así como sus ubicaciones, son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="65131-114">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="65131-115">El almacén se establece en **Manual**.</span><span class="sxs-lookup"><span data-stu-id="65131-115">The warehouse is set to **Manual**.</span></span> <span data-ttu-id="65131-116">Haga clic en **Gestión del inventario &gt; Configurar &gt; Desglose del inventario &gt; Almacenes**.</span><span class="sxs-lookup"><span data-stu-id="65131-116">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="65131-117">En la ficha desplegable **Planificación maestra**, consulte el campo **Manual**.</span><span class="sxs-lookup"><span data-stu-id="65131-117">On the **Master planning** FastTab, see the **Manual** field.</span></span>
-   <span data-ttu-id="65131-118">La cobertura de artículos está definida para el artículo.</span><span class="sxs-lookup"><span data-stu-id="65131-118">Item coverage is defined for the item.</span></span> <span data-ttu-id="65131-119">Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos emitidos**.</span><span class="sxs-lookup"><span data-stu-id="65131-119">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="65131-120">Seleccione el artículo y, a continuación, en Panel de acciones, en la pestaña **Plan**, haga clic en **Cobertura de artículos**.</span><span class="sxs-lookup"><span data-stu-id="65131-120">Select the item, and then, on the Action pane, on the **Plan** tab, click **Item coverage**.</span></span>
-   <span data-ttu-id="65131-121">Están definidas relaciones de relleno para el almacén.</span><span class="sxs-lookup"><span data-stu-id="65131-121">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="65131-122">Haga clic en **Gestión del inventario &gt; Configurar &gt; Desglose del inventario &gt; Almacenes**.</span><span class="sxs-lookup"><span data-stu-id="65131-122">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="65131-123">En la ficha desplegable **Planificación maestra**, consulte el grupo de campos **Almacén principal**.</span><span class="sxs-lookup"><span data-stu-id="65131-123">On the **Master planning** FastTab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="65131-124">El tipo de pedido predeterminado está definido en Producción, Pedido de compra o Kanban.</span><span class="sxs-lookup"><span data-stu-id="65131-124">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="65131-125">Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos emitidos**.</span><span class="sxs-lookup"><span data-stu-id="65131-125">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="65131-126">Seleccione el artículo y, a continuación, en Panel de acciones, en la pestaña **Plan**, haga clic en **Configuración predeterminada de pedido**.</span><span class="sxs-lookup"><span data-stu-id="65131-126">Select the item, and then, on the Action pane, on the **Plan** tab, click **Default order settings**.</span></span> <span data-ttu-id="65131-127">En el formulario **Configuración predeterminada de pedido** consulte **Tipo de pedido predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="65131-127">In the **Default order settings** form, see the **Default order type**.</span></span>

![Sitio de demanda y cobertura de almacén, almacén obligatorio](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousemandatory.jpg)



<a name="see-also"></a><span data-ttu-id="65131-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="65131-129">See also</span></span>
--------

[<span data-ttu-id="65131-130">Planificación maestra y funcionalidad multisitio</span><span class="sxs-lookup"><span data-stu-id="65131-130">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="65131-131">Planificación maestra: cobertura de sitios y almacenes, almacén obligatorio</span><span class="sxs-lookup"><span data-stu-id="65131-131">Master planning - site coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="65131-132">Planificación maestra: cobertura de sitios y almacenes, almacén no obligatorio</span><span class="sxs-lookup"><span data-stu-id="65131-132">Master planning - site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="65131-133">Planificación maestra: cobertura de sitios y almacenes, almacén no obligatorio</span><span class="sxs-lookup"><span data-stu-id="65131-133">Master planning - site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="65131-134">Planificación maestra: cómo se establece la versión de la lista de materiales</span><span class="sxs-lookup"><span data-stu-id="65131-134">Master planning - How the BOM version is determined</span></span>](master-plan-bom-version-determined.md)




