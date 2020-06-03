---
title: Planificación maestra para cobertura de sitios y almacenes, almacén obligatorio
description: Este tema describe cómo se planifica un artículo que tiene el sitio y el almacén como dimensiones de cobertura. La dimensión de almacén es obligatoria.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2554
ms.assetid: 3211e95f-b91a-4d27-8d92-f328ae2bcf12
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a07a4588d042af53d6281afc174ff58ecf24ca06
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383352"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-mandatory"></a><span data-ttu-id="37052-104">Planificación maestra para cobertura de sitios y almacenes, almacén obligatorio</span><span class="sxs-lookup"><span data-stu-id="37052-104">Master planning for site and warehouse coverage, warehouse mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="37052-105">Este tema describe cómo se planifica un artículo que tiene el sitio y el almacén como dimensiones de cobertura.</span><span class="sxs-lookup"><span data-stu-id="37052-105">This topic describes how an item that has site and warehouse as coverage dimensions is planned.</span></span> <span data-ttu-id="37052-106">La dimensión de almacén es obligatoria.</span><span class="sxs-lookup"><span data-stu-id="37052-106">The warehouse dimension is mandatory.</span></span>

<span data-ttu-id="37052-107">El escenario de planificación maestra implica las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="37052-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="37052-108">La dimensión del sitio está definida como obligatoria y se debe especificar en la transacción de demanda.</span><span class="sxs-lookup"><span data-stu-id="37052-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="37052-109">La dimensión de almacén está definida como obligatoria y se debe especificar en la transacción de demanda.</span><span class="sxs-lookup"><span data-stu-id="37052-109">The warehouse dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="37052-110">Las dimensiones de sitio y de almacén están definidas para la planificación de la cobertura.</span><span class="sxs-lookup"><span data-stu-id="37052-110">The site and warehouse dimensions are set for coverage planning.</span></span> <span data-ttu-id="37052-111">Se pueden configurar otras dimensiones también para la planificación de cobertura.</span><span class="sxs-lookup"><span data-stu-id="37052-111">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="37052-112">Sin embargo, no se ven afectadas por la funcionalidad de multisitio.</span><span class="sxs-lookup"><span data-stu-id="37052-112">However, they are not affected by the multisite functionality.</span></span>

<span data-ttu-id="37052-113">El gráfico siguiente ilustra cómo tiene lugar la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="37052-113">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="37052-114">Los parámetros a los que se hace referencia en el gráfico, así como sus ubicaciones, son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="37052-114">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="37052-115">El almacén se establece en **Manual**.</span><span class="sxs-lookup"><span data-stu-id="37052-115">The warehouse is set to **Manual**.</span></span> <span data-ttu-id="37052-116">Haga clic en **Gestión del inventario &gt; Configurar &gt; Desglose del inventario &gt; Almacenes**.</span><span class="sxs-lookup"><span data-stu-id="37052-116">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="37052-117">En la ficha desplegable **Planificación maestra**, consulte el campo **Manual**.</span><span class="sxs-lookup"><span data-stu-id="37052-117">On the **Master planning** FastTab, see the **Manual** field.</span></span>
-   <span data-ttu-id="37052-118">La cobertura de artículos está definida para el artículo.</span><span class="sxs-lookup"><span data-stu-id="37052-118">Item coverage is defined for the item.</span></span> <span data-ttu-id="37052-119">Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos despachados**.</span><span class="sxs-lookup"><span data-stu-id="37052-119">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="37052-120">Seleccione el artículo y, a continuación, en el panel Acciones, en la pestaña **Plan**, haga clic en **Cobertura de artículos**.</span><span class="sxs-lookup"><span data-stu-id="37052-120">Select the item, and then, on the Action Pane, on the **Plan** tab, click **Item coverage**.</span></span>
-   <span data-ttu-id="37052-121">Están definidas relaciones de relleno para el almacén.</span><span class="sxs-lookup"><span data-stu-id="37052-121">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="37052-122">Haga clic en **Gestión del inventario &gt; Configurar &gt; Desglose del inventario &gt; Almacenes**.</span><span class="sxs-lookup"><span data-stu-id="37052-122">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="37052-123">En la ficha desplegable **Planificación maestra**, consulte el grupo de campos **Almacén principal**.</span><span class="sxs-lookup"><span data-stu-id="37052-123">On the **Master planning** FastTab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="37052-124">El tipo de pedido predeterminado está definido en Producción, Pedido de compra o Kanban.</span><span class="sxs-lookup"><span data-stu-id="37052-124">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="37052-125">Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos despachados**.</span><span class="sxs-lookup"><span data-stu-id="37052-125">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="37052-126">Seleccione el artículo y, a continuación, en panel Acciones, en la pestaña **Plan**, haga clic en **Configuración predeterminada de pedidos**.</span><span class="sxs-lookup"><span data-stu-id="37052-126">Select the item, and then, on the Action Pane, on the **Plan** tab, click **Default order settings**.</span></span> <span data-ttu-id="37052-127">En el formulario **Configuración predeterminada de pedido** consulte **Tipo de pedido predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="37052-127">In the **Default order settings** form, see the **Default order type**.</span></span>

![Sitio de demanda y cobertura de almacén, almacén obligatorio](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousemandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="37052-129">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="37052-129">Additional resources</span></span>
--------

[<span data-ttu-id="37052-130">Visión general de la planificación maestra y la funcionalidad multisitio</span><span class="sxs-lookup"><span data-stu-id="37052-130">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="37052-131">Planificación maestra para cobertura de sitios, almacén obligatorio</span><span class="sxs-lookup"><span data-stu-id="37052-131">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="37052-132">Planificación maestra para cobertura de sitios, almacén no obligatorio</span><span class="sxs-lookup"><span data-stu-id="37052-132">Master planning for site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="37052-133">Planificación maestra de cobertura de sitios y almacén, almacén no obligatorio</span><span class="sxs-lookup"><span data-stu-id="37052-133">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="37052-134">Determinar la versión de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="37052-134">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)



