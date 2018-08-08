---
title: "Planificación maestra para cobertura de sitios y almacenes, almacén no obligatorio"
description: "Este tema describe cómo se planifica un artículo que tiene el sitio y el almacén como dimensiones de cobertura. La dimensión Almacén no es obligatoria."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2514
ms.assetid: 92d47bdd-df68-4f60-ac9a-96aa08236c26
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 45796049cddef137eb2ca1e4331197e4b4a65071
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---

# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-not-mandatory"></a><span data-ttu-id="cbdc4-104">Planificación maestra para cobertura de sitios y almacenes, almacén no obligatorio</span><span class="sxs-lookup"><span data-stu-id="cbdc4-104">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cbdc4-105">Este tema describe cómo se planifica un artículo que tiene el sitio y el almacén como dimensiones de cobertura.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-105">This topic describes how an item that has site and warehouse as coverage dimensions is planned.</span></span> <span data-ttu-id="cbdc4-106">La dimensión Almacén no es obligatoria.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-106">The warehouse dimension is not mandatory.</span></span>

<span data-ttu-id="cbdc4-107">El escenario de planificación maestra implica las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="cbdc4-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="cbdc4-108">La dimensión del sitio está definida como obligatoria y se debe especificar en la transacción de demanda.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span> <span data-ttu-id="cbdc4-109">Este ajuste no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-109">This setting can't be modified.</span></span>
-   <span data-ttu-id="cbdc4-110">La dimensión Almacén no está configurada como obligatoria.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-110">The warehouse dimension is not set to mandatory.</span></span> <span data-ttu-id="cbdc4-111">El almacén puede ser conocido, pero no se usa en el cálculo de la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-111">The warehouse may be known, but it is not used in the master planning calculation.</span></span>
-   <span data-ttu-id="cbdc4-112">La dimensión Sitio y Almacén están configuradas para la planificación de cobertura.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-112">The site and warehouse dimensions are set for coverage planning.</span></span> <span data-ttu-id="cbdc4-113">Se pueden configurar otras dimensiones también para la planificación de cobertura.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-113">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="cbdc4-114">Sin embargo, no se ven afectadas por la funcionalidad de multisitio.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-114">However, they are not affected by the multisite functionality.</span></span>

<span data-ttu-id="cbdc4-115">El gráfico siguiente ilustra cómo tiene lugar la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-115">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="cbdc4-116">Los parámetros a los que se hace referencia en el gráfico, así como sus ubicaciones, son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="cbdc4-116">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="cbdc4-117">El almacén se establece en Manual.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-117">The warehouse is set to Manual.</span></span> <span data-ttu-id="cbdc4-118">Haga clic en **Gestión del inventario &gt; Configurar &gt; Desglose del inventario &gt; Almacenes**.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-118">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="cbdc4-119">En la ficha desplegable **Planificación maestra**, consulte el campo **Manual**.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-119">On the **Master planning** FastTab, see the **Manual** field.</span></span>
-   <span data-ttu-id="cbdc4-120">La cobertura de artículos está definida para el artículo.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-120">Item coverage is defined for the item.</span></span> <span data-ttu-id="cbdc4-121">Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos emitidos**.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-121">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="cbdc4-122">Seleccione el artículo y, a continuación, en Panel de acciones, en la pestaña **Plan**, haga clic en **Cobertura de artículos**.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-122">Select the item, and then, on the Action pane, on the **Plan** tab, click **Item coverage**.</span></span>
-   <span data-ttu-id="cbdc4-123">Están definidas relaciones de relleno para el almacén.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-123">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="cbdc4-124">Haga clic en **Gestión del inventario &gt; Configurar &gt; Desglose del inventario &gt; Almacenes**.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-124">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="cbdc4-125">En la ficha desplegable **Planificación maestra**, consulte el grupo de campos **Almacén principal**.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-125">On the **Master planning** FastTab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="cbdc4-126">El tipo de pedido predeterminado está definido en Producción, Pedido de compra o Kanban.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-126">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="cbdc4-127">Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos emitidos**.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-127">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="cbdc4-128">Seleccione el artículo y, a continuación, en Panel de acciones, en la pestaña **Plan**, haga clic en **Configuración predeterminada de pedido**.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-128">Select the item, and then, on the Action pane, on the **Plan** tab, click **Default order settings**.</span></span> <span data-ttu-id="cbdc4-129">En el formulario **Configuración predeterminada de pedido** consulte **Tipo de pedido predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="cbdc4-129">In the **Default order settings** form, see the **Default order type**.</span></span>

![Demanda para el sitio y el almacén, almacén no](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousenotmandatory.jpg)


-



<a name="additional-resources"></a><span data-ttu-id="cbdc4-131">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="cbdc4-131">Additional resources</span></span>
--------

[<span data-ttu-id="cbdc4-132">Planificación maestra y funcionalidad multisitio</span><span class="sxs-lookup"><span data-stu-id="cbdc4-132">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="cbdc4-133">Planificación maestra: cobertura de sitios y almacenes, almacén obligatorio</span><span class="sxs-lookup"><span data-stu-id="cbdc4-133">Master planning - site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="cbdc4-134">Planificación maestra: cobertura de sitios y almacenes, almacén obligatorio</span><span class="sxs-lookup"><span data-stu-id="cbdc4-134">Master planning - site coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="cbdc4-135">Planificación maestra: cobertura de sitios y almacenes, almacén no obligatorio</span><span class="sxs-lookup"><span data-stu-id="cbdc4-135">Master planning - site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="cbdc4-136">Planificación maestra: cómo se establece la versión de la lista de materiales</span><span class="sxs-lookup"><span data-stu-id="cbdc4-136">Master planning - How the BOM version is determined</span></span>](master-plan-bom-version-determined.md)




