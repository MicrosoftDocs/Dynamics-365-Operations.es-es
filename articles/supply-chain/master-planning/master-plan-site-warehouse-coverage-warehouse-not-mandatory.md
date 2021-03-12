---
title: Planificación maestra para cobertura de sitios y almacenes, almacén no obligatorio
description: Este tema describe cómo se planifica un artículo que tiene el sitio y el almacén como dimensiones de cobertura. La dimensión Almacén no es obligatoria.
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
ms.custom: 2514
ms.assetid: 92d47bdd-df68-4f60-ac9a-96aa08236c26
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cdd3614e52da72e32e6781bc8da7c9e2b3162832
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970415"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-not-mandatory"></a><span data-ttu-id="5c479-104">Planificación maestra para cobertura de sitios y almacenes, almacén no obligatorio</span><span class="sxs-lookup"><span data-stu-id="5c479-104">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5c479-105">Este tema describe cómo se planifica un artículo que tiene el sitio y el almacén como dimensiones de cobertura.</span><span class="sxs-lookup"><span data-stu-id="5c479-105">This topic describes how an item that has site and warehouse as coverage dimensions is planned.</span></span> <span data-ttu-id="5c479-106">La dimensión Almacén no es obligatoria.</span><span class="sxs-lookup"><span data-stu-id="5c479-106">The warehouse dimension is not mandatory.</span></span>

<span data-ttu-id="5c479-107">El escenario de planificación maestra implica las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5c479-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="5c479-108">La dimensión del sitio está definida como obligatoria y se debe especificar en la transacción de demanda.</span><span class="sxs-lookup"><span data-stu-id="5c479-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span> <span data-ttu-id="5c479-109">Este ajuste no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="5c479-109">This setting can't be modified.</span></span>
-   <span data-ttu-id="5c479-110">La dimensión Almacén no está configurada como obligatoria.</span><span class="sxs-lookup"><span data-stu-id="5c479-110">The warehouse dimension is not set to mandatory.</span></span> <span data-ttu-id="5c479-111">El almacén puede ser conocido, pero no se usa en el cálculo de la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="5c479-111">The warehouse may be known, but it is not used in the master planning calculation.</span></span>
-   <span data-ttu-id="5c479-112">La dimensión Sitio y Almacén están configuradas para la planificación de cobertura.</span><span class="sxs-lookup"><span data-stu-id="5c479-112">The site and warehouse dimensions are set for coverage planning.</span></span> <span data-ttu-id="5c479-113">Se pueden configurar otras dimensiones también para la planificación de cobertura.</span><span class="sxs-lookup"><span data-stu-id="5c479-113">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="5c479-114">Sin embargo, no se ven afectadas por la funcionalidad de multisitio.</span><span class="sxs-lookup"><span data-stu-id="5c479-114">However, they are not affected by the multisite functionality.</span></span>

<span data-ttu-id="5c479-115">El gráfico siguiente ilustra cómo tiene lugar la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="5c479-115">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="5c479-116">Los parámetros a los que se hace referencia en el gráfico, así como sus ubicaciones, son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="5c479-116">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="5c479-117">El almacén se establece en Manual.</span><span class="sxs-lookup"><span data-stu-id="5c479-117">The warehouse is set to Manual.</span></span> <span data-ttu-id="5c479-118">Haga clic en **Gestión del inventario &gt; Configurar &gt; Desglose del inventario &gt; Almacenes**.</span><span class="sxs-lookup"><span data-stu-id="5c479-118">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="5c479-119">En la ficha desplegable **Planificación maestra**, consulte el campo **Manual**.</span><span class="sxs-lookup"><span data-stu-id="5c479-119">On the **Master planning** FastTab, see the **Manual** field.</span></span>
-   <span data-ttu-id="5c479-120">La cobertura de artículos está definida para el artículo.</span><span class="sxs-lookup"><span data-stu-id="5c479-120">Item coverage is defined for the item.</span></span> <span data-ttu-id="5c479-121">Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos despachados**.</span><span class="sxs-lookup"><span data-stu-id="5c479-121">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="5c479-122">Seleccione el artículo y, a continuación, en el panel Acciones, en la pestaña **Plan**, haga clic en **Cobertura de artículos**.</span><span class="sxs-lookup"><span data-stu-id="5c479-122">Select the item, and then, on the Action Pane, on the **Plan** tab, click **Item coverage**.</span></span>
-   <span data-ttu-id="5c479-123">Están definidas relaciones de relleno para el almacén.</span><span class="sxs-lookup"><span data-stu-id="5c479-123">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="5c479-124">Haga clic en **Gestión del inventario &gt; Configurar &gt; Desglose del inventario &gt; Almacenes**.</span><span class="sxs-lookup"><span data-stu-id="5c479-124">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="5c479-125">En la ficha desplegable **Planificación maestra**, consulte el grupo de campos **Almacén principal**.</span><span class="sxs-lookup"><span data-stu-id="5c479-125">On the **Master planning** FastTab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="5c479-126">El tipo de pedido predeterminado está definido en Producción, Pedido de compra o Kanban.</span><span class="sxs-lookup"><span data-stu-id="5c479-126">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="5c479-127">Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos despachados**.</span><span class="sxs-lookup"><span data-stu-id="5c479-127">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="5c479-128">Seleccione el artículo y, a continuación, en panel Acciones, en la pestaña **Plan**, haga clic en **Configuración predeterminada de pedidos**.</span><span class="sxs-lookup"><span data-stu-id="5c479-128">Select the item, and then, on the Action Pane, on the **Plan** tab, click **Default order settings**.</span></span> <span data-ttu-id="5c479-129">En el formulario **Configuración predeterminada de pedido** consulte **Tipo de pedido predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="5c479-129">In the **Default order settings** form, see the **Default order type**.</span></span>

![Demanda para el sitio y el almacén, almacén no](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousenotmandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="5c479-131">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5c479-131">Additional resources</span></span>
--------

[<span data-ttu-id="5c479-132">Visión general de la planificación maestra y la funcionalidad multisitio</span><span class="sxs-lookup"><span data-stu-id="5c479-132">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="5c479-133">Planificación maestra para cobertura de sitios, almacén obligatorio</span><span class="sxs-lookup"><span data-stu-id="5c479-133">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="5c479-134">Planificación maestra de cobertura de sitios y almacén, almacén obligatorio</span><span class="sxs-lookup"><span data-stu-id="5c479-134">Master planning for site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="5c479-135">Planificación maestra de cobertura de sitios y almacén, almacén no obligatorio</span><span class="sxs-lookup"><span data-stu-id="5c479-135">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="5c479-136">Determinar la versión de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="5c479-136">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)



