---
title: "Planificación maestra para cobertura de sitios y almacenes, almacén no obligatorio"
description: "Este tema describe cómo se planifica un artículo que tiene la dimensión del sitio establecida para cobertura."
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
ms.custom: 2474
ms.assetid: 316da918-67ae-43c5-baea-00ae559e29b0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 79582e92daeaf0afb032448d36be12edd0926089
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="master-planning-for-site-coverage-warehouse-not-mandatory"></a><span data-ttu-id="590d4-103">Planificación maestra para cobertura de sitios y almacenes, almacén no obligatorio</span><span class="sxs-lookup"><span data-stu-id="590d4-103">Master planning for site coverage, warehouse not mandatory</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="590d4-104">Este tema describe cómo se planifica un artículo que tiene la dimensión del sitio establecida para cobertura.</span><span class="sxs-lookup"><span data-stu-id="590d4-104">This topic describes how an item that has the site dimension set for coverage is planned.</span></span>

<span data-ttu-id="590d4-105">El escenario de planificación maestra implica las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="590d4-105">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="590d4-106">La dimensión del sitio está definida como obligatoria y se debe especificar en la transacción de demanda.</span><span class="sxs-lookup"><span data-stu-id="590d4-106">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="590d4-107">La dimensión Almacén no está configurada como obligatoria.</span><span class="sxs-lookup"><span data-stu-id="590d4-107">The warehouse dimension is not set to mandatory.</span></span> <span data-ttu-id="590d4-108">El almacén puede ser conocido, pero no se usa en el cálculo de la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="590d4-108">The warehouse may be known, but it is not used in the master planning calculation.</span></span>
-   <span data-ttu-id="590d4-109">La dimensión de sitio está definida para la planificación de la cobertura.</span><span class="sxs-lookup"><span data-stu-id="590d4-109">The site dimension is set for coverage planning.</span></span>
-   <span data-ttu-id="590d4-110">La dimensión de almacén no está definida para la planificación de la cobertura.</span><span class="sxs-lookup"><span data-stu-id="590d4-110">The warehouse dimension is not set for coverage planning.</span></span> <span data-ttu-id="590d4-111">Por lo tanto, el suministro y la demanda se agregan por sitio y, quizás, también otras dimensiones planificadas por cobertura.</span><span class="sxs-lookup"><span data-stu-id="590d4-111">Therefore, supply and demand are aggregated by site and, perhaps, other coverage-planned dimensions also.</span></span>

<span data-ttu-id="590d4-112">El gráfico siguiente ilustra cómo tiene lugar la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="590d4-112">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="590d4-113">Los parámetros a los que se hace referencia en el gráfico, así como sus ubicaciones, son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="590d4-113">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="590d4-114">La cobertura de artículos está definida para el artículo.</span><span class="sxs-lookup"><span data-stu-id="590d4-114">Item coverage is defined for the item.</span></span> <span data-ttu-id="590d4-115">Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos emitidos**.</span><span class="sxs-lookup"><span data-stu-id="590d4-115">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="590d4-116">Seleccione el artículo y haga clic en **Planificar &gt; Cobertura de artículos**.</span><span class="sxs-lookup"><span data-stu-id="590d4-116">Select the item, and then click **Plan &gt; Item coverage**.</span></span>
-   <span data-ttu-id="590d4-117">Están definidas relaciones de relleno para el almacén.</span><span class="sxs-lookup"><span data-stu-id="590d4-117">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="590d4-118">Haga clic en **Gestión del inventario &gt; Configurar &gt; Desglose del inventario &gt; Almacenes**.</span><span class="sxs-lookup"><span data-stu-id="590d4-118">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="590d4-119">En la ficha **Planificación maestra**, consulte el grupo de campos **Almacén principal**.</span><span class="sxs-lookup"><span data-stu-id="590d4-119">On the **Master planning** tab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="590d4-120">El tipo de pedido predeterminado está definido en Producción, Pedido de compra o Kanban.</span><span class="sxs-lookup"><span data-stu-id="590d4-120">The default order type is set to Production, Purchase order or Kanban.</span></span> <span data-ttu-id="590d4-121">Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos emitidos**.</span><span class="sxs-lookup"><span data-stu-id="590d4-121">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="590d4-122">Seleccione el artículo y, a continuación, haga clic en **Planificar &gt; Configuración predeterminada de pedido**.</span><span class="sxs-lookup"><span data-stu-id="590d4-122">Select the item, and then click **Plan &gt; Default order settings**.</span></span> <span data-ttu-id="590d4-123">En el formulario **Configuración predeterminada de pedido**, consulte el campo **Tipo de pedido predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="590d4-123">In the **Default order settings** form, see the **Default order type** field.</span></span>

![Demanda de cobertura de sitios, almacén no obligatorio](./media/multisitedemandexplosionscenarioforsitecoveragewarehousenotmandatory.jpg)



<a name="see-also"></a><span data-ttu-id="590d4-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="590d4-125">See also</span></span>
--------

[<span data-ttu-id="590d4-126">Planificación maestra y funcionalidad multisitio</span><span class="sxs-lookup"><span data-stu-id="590d4-126">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="590d4-127">Planificación maestra: cobertura de sitios y almacenes, almacén obligatorio</span><span class="sxs-lookup"><span data-stu-id="590d4-127">Master planning - site coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="590d4-128">Planificación maestra: cobertura de sitios y almacenes, almacén no obligatorio</span><span class="sxs-lookup"><span data-stu-id="590d4-128">Master planning - site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="590d4-129">Planificación maestra: cobertura de sitios y almacenes, almacén obligatorio</span><span class="sxs-lookup"><span data-stu-id="590d4-129">Master planning - site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="590d4-130">Planificación maestra: cómo se establece la versión de la lista de materiales</span><span class="sxs-lookup"><span data-stu-id="590d4-130">Master planning - how the BOM version is determined</span></span>](master-plan-bom-version-determined.md)




