---
title: Visión general de la planificación maestra y la funcionalidad multisitio
description: La planificación maestra tiene en cuenta la configuración del sitio y las dimensiones de inventario de almacén.
author: roxanadiaconu
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2434
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b26ff5c2f580c30113b82302bbad744bbf285ff
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213731"
---
# <a name="master-planning-and-multisite-functionality-overview"></a><span data-ttu-id="b5453-103">Visión general de la planificación maestra y la funcionalidad multisitio</span><span class="sxs-lookup"><span data-stu-id="b5453-103">Master planning and multisite functionality overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b5453-104">La planificación maestra tiene en cuenta la configuración del sitio y las dimensiones de inventario de almacén.</span><span class="sxs-lookup"><span data-stu-id="b5453-104">Master planning takes the settings of the site and warehouse inventory dimensions into account.</span></span> 

<span data-ttu-id="b5453-105">La dimensión de sitio es obligatoria, y también puede establecer la dimensión de almacén como obligatoria.</span><span class="sxs-lookup"><span data-stu-id="b5453-105">The site dimension is mandatory, and you can set the warehouse dimension to be mandatory.</span></span>

<span data-ttu-id="b5453-106">Si una dimensión es obligatoria, se debe especificar un valor de dimensión en todas las transacciones de inventario.</span><span class="sxs-lookup"><span data-stu-id="b5453-106">When a dimension is mandatory, a dimension value must be entered on all inventory transactions.</span></span> <span data-ttu-id="b5453-107">Por lo tanto, durante la planificación maestra, se conocen el sitio y el almacén para la demanda inicial.</span><span class="sxs-lookup"><span data-stu-id="b5453-107">Therefore, during master planning, the site and the warehouse for the initial demand are known.</span></span> <span data-ttu-id="b5453-108">La dimensión de sitio también es coherente de modo que, durante la expansión de la demanda de bajo nivel, el valor del sitio no cambia.</span><span class="sxs-lookup"><span data-stu-id="b5453-108">The site dimension is also consistent so that during the explosion of lower-level demand, the site value does not change.</span></span>

<span data-ttu-id="b5453-109">Si el almacén no se configura como obligatorio, es posible que no se conozca a partir de la demanda inicial.</span><span class="sxs-lookup"><span data-stu-id="b5453-109">When the warehouse is not set to mandatory, it may not be known from the initial demand.</span></span> <span data-ttu-id="b5453-110">El sistema de planificación deberá determinar qué almacén utilizar en función de la configuración definiaa para el artículo, los almacenes individuales y los detalles de la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="b5453-110">The planning engine must determine which warehouse to use based on the settings that are defined for the item, individual warehouses, and the details of the order line.</span></span>

<span data-ttu-id="b5453-111">En los siguientes temas se describe el funcionamiento del motor de planificación, cuando hay diferentes configuraciones definidas, para determinar el almacén que hay que utilizar.</span><span class="sxs-lookup"><span data-stu-id="b5453-111">The following topics describe how the planning engine works, when different settings are defined, to determine the warehouse to use.</span></span>

[<span data-ttu-id="b5453-112">Planificación maestra de cobertura de sitios y almacén, almacén obligatorio</span><span class="sxs-lookup"><span data-stu-id="b5453-112">Master planning for site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="b5453-113">Planificación maestra para cobertura de sitios, almacén obligatorio</span><span class="sxs-lookup"><span data-stu-id="b5453-113">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="b5453-114">Planificación maestra de cobertura de sitios y almacén, almacén no obligatorio</span><span class="sxs-lookup"><span data-stu-id="b5453-114">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="b5453-115">Planificación maestra para cobertura de sitios, almacén no obligatorio</span><span class="sxs-lookup"><span data-stu-id="b5453-115">Master planning for site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="b5453-116">Determinar la versión de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="b5453-116">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)



