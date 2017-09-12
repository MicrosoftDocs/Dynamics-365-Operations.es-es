---
title: "Planificación maestra para cobertura de sitios, almacén obligatorio"
description: "Este tema describe cómo se planifica un artículo que tiene el sitio como dimensión de cobertura. El almacén es una dimensión obligatoria."
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
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2454
ms.assetid: aa135030-f98c-48bf-902c-e52f680dc247
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 14df626025a22237afe30cc5b08d42b475fc3a4f
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---

# <a name="master-planning-for-site-coverage-mandatory-warehouse"></a><span data-ttu-id="4a994-104">Planificación maestra para cobertura de sitios, almacén obligatorio</span><span class="sxs-lookup"><span data-stu-id="4a994-104">Master planning for site coverage, mandatory warehouse</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="4a994-105">Este tema describe cómo se planifica un artículo que tiene el sitio como dimensión de cobertura.</span><span class="sxs-lookup"><span data-stu-id="4a994-105">This topic describes how an item that has the site as coverage dimension is planned.</span></span> <span data-ttu-id="4a994-106">El almacén es una dimensión obligatoria.</span><span class="sxs-lookup"><span data-stu-id="4a994-106">Warehouse is a mandatory dimension.</span></span>

<span data-ttu-id="4a994-107">El escenario de planificación maestra implica las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="4a994-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="4a994-108">La dimensión del sitio está definida como obligatoria y se debe especificar en la transacción de demanda.</span><span class="sxs-lookup"><span data-stu-id="4a994-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span> <span data-ttu-id="4a994-109">Este ajuste no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="4a994-109">This setting can't be modified.</span></span>
-   <span data-ttu-id="4a994-110">La dimensión de almacén está definida como obligatoria y se debe especificar en la transacción de demanda.</span><span class="sxs-lookup"><span data-stu-id="4a994-110">The warehouse dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="4a994-111">La dimensión de sitio está definida para la planificación de la cobertura.</span><span class="sxs-lookup"><span data-stu-id="4a994-111">The site dimension is set for coverage planning.</span></span> <span data-ttu-id="4a994-112">También se pueden definir otras dimensiones para la planificación de la cobertura.</span><span class="sxs-lookup"><span data-stu-id="4a994-112">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="4a994-113">Sin embargo, no se verán afectadas por la funcionalidad multisitio.</span><span class="sxs-lookup"><span data-stu-id="4a994-113">However, they are not affected by the multisite functionality.</span></span>
-   <span data-ttu-id="4a994-114">La dimensión de almacén no está definida para la planificación de la cobertura.</span><span class="sxs-lookup"><span data-stu-id="4a994-114">The warehouse dimension is not set for coverage planning.</span></span> <span data-ttu-id="4a994-115">Por lo tanto, el suministro y la demanda se agregan por sitio y, quizás, también otras dimensiones planificadas por cobertura.</span><span class="sxs-lookup"><span data-stu-id="4a994-115">Therefore, supply and demand are aggregated by site and, perhaps, other coverage-planned dimensions also.</span></span>

<span data-ttu-id="4a994-116">El gráfico siguiente ilustra cómo tiene lugar la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="4a994-116">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="4a994-117">Los parámetros a los que se hace referencia en el gráfico, así como sus ubicaciones, son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="4a994-117">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="4a994-118">La cobertura de artículos está definida para el artículo.</span><span class="sxs-lookup"><span data-stu-id="4a994-118">Item coverage is defined for the item.</span></span> <span data-ttu-id="4a994-119">Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos emitidos**.</span><span class="sxs-lookup"><span data-stu-id="4a994-119">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="4a994-120">Seleccione el artículo y haga clic en **Planificar &gt; Cobertura de artículos**.</span><span class="sxs-lookup"><span data-stu-id="4a994-120">Select the item, and then click **Plan &gt; Item coverage**.</span></span>
-   <span data-ttu-id="4a994-121">Están definidas relaciones de relleno para el almacén.</span><span class="sxs-lookup"><span data-stu-id="4a994-121">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="4a994-122">Haga clic en **Gestión del inventario &gt; Configurar &gt; Desglose del inventario &gt; Almacenes**.</span><span class="sxs-lookup"><span data-stu-id="4a994-122">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="4a994-123">En la ficha **Planificación maestra**, consulte el grupo de campos **Almacén principal**.</span><span class="sxs-lookup"><span data-stu-id="4a994-123">On the **Master planning** tab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="4a994-124">El tipo de pedido predeterminado está definido en Producción, Pedido de compra o Kanban.</span><span class="sxs-lookup"><span data-stu-id="4a994-124">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="4a994-125">Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos emitidos**.</span><span class="sxs-lookup"><span data-stu-id="4a994-125">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="4a994-126">Seleccione el artículo y, a continuación, haga clic en **Planificar &gt; Configuración predeterminada de pedido**.</span><span class="sxs-lookup"><span data-stu-id="4a994-126">Select the item, and then click **Plan &gt; Default order settings**.</span></span> <span data-ttu-id="4a994-127">En el formulario **Configuración predeterminada de pedido** consulte **Tipo de pedido predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="4a994-127">In the **Default order settings** form, see the **Default order type**.</span></span>

![Demanda de cobertura de sitios, almacén obligatorio](./media/multisitedemandexplosionscenarioforsitecoveragewarehousemandatory.jpg)



<a name="see-also"></a><span data-ttu-id="4a994-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4a994-129">See also</span></span>
--------

[<span data-ttu-id="4a994-130">Planificación maestra y funcionalidad multisitio</span><span class="sxs-lookup"><span data-stu-id="4a994-130">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="4a994-131">Planificación maestra: cobertura de sitios y almacenes, almacén obligatorio</span><span class="sxs-lookup"><span data-stu-id="4a994-131">Master planning - site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="4a994-132">Planificación maestra: cobertura de sitios y almacenes, almacén obligatorio</span><span class="sxs-lookup"><span data-stu-id="4a994-132">Master planning - site coverage. warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="4a994-133">Planificación maestra: cobertura de sitios y almacenes, almacén no obligatorio</span><span class="sxs-lookup"><span data-stu-id="4a994-133">Master planning - site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="4a994-134">Planificación maestra: cómo se establece la versión de la lista de materiales</span><span class="sxs-lookup"><span data-stu-id="4a994-134">Master planning - How the BOM version is determined</span></span>](master-plan-bom-version-determined.md)




