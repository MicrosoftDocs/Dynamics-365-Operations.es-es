---
title: Planificación maestra para cobertura de sitios y almacenes, almacén no obligatorio
description: Este tema describe cómo se planifica un artículo que tiene la dimensión del sitio establecida para cobertura.
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
ms.custom: 2474
ms.assetid: 316da918-67ae-43c5-baea-00ae559e29b0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fce7737688f34469a0355acd4c7279d006cae1b7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222906"
---
# <a name="master-planning-for-site-coverage-warehouse-not-mandatory"></a><span data-ttu-id="3af49-103">Planificación maestra para cobertura de sitios y almacenes, almacén no obligatorio</span><span class="sxs-lookup"><span data-stu-id="3af49-103">Master planning for site coverage, warehouse not mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3af49-104">Este tema describe cómo se planifica un artículo que tiene la dimensión del sitio establecida para cobertura.</span><span class="sxs-lookup"><span data-stu-id="3af49-104">This topic describes how an item that has the site dimension set for coverage is planned.</span></span>

<span data-ttu-id="3af49-105">El escenario de planificación maestra implica las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="3af49-105">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="3af49-106">La dimensión del sitio está definida como obligatoria y se debe especificar en la transacción de demanda.</span><span class="sxs-lookup"><span data-stu-id="3af49-106">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="3af49-107">La dimensión Almacén no está configurada como obligatoria.</span><span class="sxs-lookup"><span data-stu-id="3af49-107">The warehouse dimension is not set to mandatory.</span></span> <span data-ttu-id="3af49-108">El almacén puede ser conocido, pero no se usa en el cálculo de la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="3af49-108">The warehouse may be known, but it is not used in the master planning calculation.</span></span>
-   <span data-ttu-id="3af49-109">La dimensión de sitio está definida para la planificación de la cobertura.</span><span class="sxs-lookup"><span data-stu-id="3af49-109">The site dimension is set for coverage planning.</span></span>
-   <span data-ttu-id="3af49-110">La dimensión de almacén no está definida para la planificación de la cobertura.</span><span class="sxs-lookup"><span data-stu-id="3af49-110">The warehouse dimension is not set for coverage planning.</span></span> <span data-ttu-id="3af49-111">Por lo tanto, el suministro y la demanda se agregan por sitio y, quizás, también otras dimensiones planificadas por cobertura.</span><span class="sxs-lookup"><span data-stu-id="3af49-111">Therefore, supply and demand are aggregated by site and, perhaps, other coverage-planned dimensions also.</span></span>

<span data-ttu-id="3af49-112">El gráfico siguiente ilustra cómo tiene lugar la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="3af49-112">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="3af49-113">Los parámetros a los que se hace referencia en el gráfico, así como sus ubicaciones, son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3af49-113">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="3af49-114">La cobertura de artículos está definida para el artículo.</span><span class="sxs-lookup"><span data-stu-id="3af49-114">Item coverage is defined for the item.</span></span> <span data-ttu-id="3af49-115">Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos emitidos**.</span><span class="sxs-lookup"><span data-stu-id="3af49-115">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="3af49-116">Seleccione el artículo y haga clic en **Planificar &gt; Cobertura de artículos**.</span><span class="sxs-lookup"><span data-stu-id="3af49-116">Select the item, and then click **Plan &gt; Item coverage**.</span></span>
-   <span data-ttu-id="3af49-117">Están definidas relaciones de relleno para el almacén.</span><span class="sxs-lookup"><span data-stu-id="3af49-117">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="3af49-118">Haga clic en **Gestión del inventario &gt; Configurar &gt; Desglose del inventario &gt; Almacenes**.</span><span class="sxs-lookup"><span data-stu-id="3af49-118">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="3af49-119">En la ficha **Planificación maestra**, consulte el grupo de campos **Almacén principal**.</span><span class="sxs-lookup"><span data-stu-id="3af49-119">On the **Master planning** tab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="3af49-120">El tipo de pedido predeterminado está definido en Producción, Pedido de compra o Kanban.</span><span class="sxs-lookup"><span data-stu-id="3af49-120">The default order type is set to Production, Purchase order or Kanban.</span></span> <span data-ttu-id="3af49-121">Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos emitidos**.</span><span class="sxs-lookup"><span data-stu-id="3af49-121">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="3af49-122">Seleccione el artículo y, a continuación, haga clic en **Planificar &gt; Configuración predeterminada de pedido**.</span><span class="sxs-lookup"><span data-stu-id="3af49-122">Select the item, and then click **Plan &gt; Default order settings**.</span></span> <span data-ttu-id="3af49-123">En el formulario **Configuración predeterminada de pedido**, consulte el campo **Tipo de pedido predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="3af49-123">In the **Default order settings** form, see the **Default order type** field.</span></span>

![Demanda de cobertura de sitios, almacén no obligatorio](./media/multisitedemandexplosionscenarioforsitecoveragewarehousenotmandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="3af49-125">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="3af49-125">Additional resources</span></span>
--------

[<span data-ttu-id="3af49-126">Visión general de la planificación maestra y la funcionalidad multisitio</span><span class="sxs-lookup"><span data-stu-id="3af49-126">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="3af49-127">Planificación maestra de cobertura de sitios y almacén, almacén obligatorio</span><span class="sxs-lookup"><span data-stu-id="3af49-127">Master planning for site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="3af49-128">Planificación maestra para cobertura de sitios, almacén obligatorio</span><span class="sxs-lookup"><span data-stu-id="3af49-128">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="3af49-129">Planificación maestra para cobertura de sitios, almacén no obligatorio</span><span class="sxs-lookup"><span data-stu-id="3af49-129">Master planning for site coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="3af49-130">Determinar la versión de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="3af49-130">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]