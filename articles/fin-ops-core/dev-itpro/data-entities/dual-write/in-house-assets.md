---
title: Activos internos para mantenimiento
description: Este tema describe cómo puede utilizar Microsoft Dynamics 365 Field Service para dar servicio tanto a los activos del cliente como a los activos internos.
author: RamaKrishnamoorthy
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: ebda6b5679ec601513fb6d046725b396e69fe0f3
ms.sourcegitcommit: a202bf67c3c2c054e2a47cb7b3145cb7c0ee635e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/25/2021
ms.locfileid: "5941423"
---
# <a name="in-house-assets-for-servicing"></a><span data-ttu-id="6f601-103">Activos internos para mantenimiento</span><span class="sxs-lookup"><span data-stu-id="6f601-103">In-house assets for servicing</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="6f601-104">Microsoft Dynamics 365 Field Service está diseñado para dar servicio a los activos del cliente.</span><span class="sxs-lookup"><span data-stu-id="6f601-104">Microsoft Dynamics 365 Field Service is designed to service customer assets.</span></span> <span data-ttu-id="6f601-105">La gestión de activos para Dynamics 365 Supply Chain Management está diseñada para mantener los activos internos.</span><span class="sxs-lookup"><span data-stu-id="6f601-105">Asset management for Dynamics 365 Supply Chain Management is designed to maintain in-house assets.</span></span> <span data-ttu-id="6f601-106">La integración de estas dos aplicaciones le permite utilizar Field Service para atender los activos de los clientes y los activos internos.</span><span class="sxs-lookup"><span data-stu-id="6f601-106">Integration of these two apps lets you use Field Service to service both customer assets and in-house assets.</span></span> <span data-ttu-id="6f601-107">También puede clasificar los activos, según la ubicación técnica o la jerarquía, y realizar un seguimiento del servicio a un nivel detallado.</span><span class="sxs-lookup"><span data-stu-id="6f601-107">You can also classify the assets, based on functional location or hierarchy, and track the servicing at a detailed level.</span></span>

<span data-ttu-id="6f601-108">Para más información, vea [Integrar Dynamics 365 Field Service y Supply Chain Management](/dynamics365/field-service/supply-chain-field-service-integration).</span><span class="sxs-lookup"><span data-stu-id="6f601-108">For more information, see [Integrate Dynamics 365 Field Service and Supply Chain Management](/dynamics365/field-service/supply-chain-field-service-integration).</span></span>

## <a name="templates"></a><span data-ttu-id="6f601-109">Plantillas</span><span class="sxs-lookup"><span data-stu-id="6f601-109">Templates</span></span>

<span data-ttu-id="6f601-110">Los activos internos incluyes una colección de mapas de tabla básicos que funcionan conjuntamente durante la interacción de los datos, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="6f601-110">In-house-assets include a collection of core table maps that work together during data interaction, as shown in the following table.</span></span>

| <span data-ttu-id="6f601-111">Aplicaciones de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="6f601-111">Finance and Operations apps</span></span> | <span data-ttu-id="6f601-112">Aplicaciones basadas en modelos en Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="6f601-112">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="6f601-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f601-113">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="6f601-114">Administración de activos de activos de modelos de ciclos de vida</span><span class="sxs-lookup"><span data-stu-id="6f601-114">Asset management asset lifecycle models</span></span> | <span data-ttu-id="6f601-115">msdyn\_assetlifecyclemodels</span><span class="sxs-lookup"><span data-stu-id="6f601-115">msdyn\_assetlifecyclemodels</span></span> | |
| <span data-ttu-id="6f601-116">Administración de activos de activos de estados de ciclos de vida</span><span class="sxs-lookup"><span data-stu-id="6f601-116">Asset management asset lifecycle states</span></span> | <span data-ttu-id="6f601-117">msdyn\_assetlifecyclestates</span><span class="sxs-lookup"><span data-stu-id="6f601-117">msdyn\_assetlifecyclestates</span></span> | |
| <span data-ttu-id="6f601-118">Administración de activos de activos</span><span class="sxs-lookup"><span data-stu-id="6f601-118">Asset management assets</span></span> | <span data-ttu-id="6f601-119">msdyn\_customerassets</span><span class="sxs-lookup"><span data-stu-id="6f601-119">msdyn\_customerassets</span></span> | |
| <span data-ttu-id="6f601-120">Administración de activos de tipos de activos</span><span class="sxs-lookup"><span data-stu-id="6f601-120">Asset management asset types</span></span> | <span data-ttu-id="6f601-121">msdyn\_customerassetcategories</span><span class="sxs-lookup"><span data-stu-id="6f601-121">msdyn\_customerassetcategories</span></span> | |
| <span data-ttu-id="6f601-122">Administración de activos ubicación técnica de modelos de ciclo de vida</span><span class="sxs-lookup"><span data-stu-id="6f601-122">Asset management functional location lifecycle models</span></span> | <span data-ttu-id="6f601-123">msdyn\_functionallocationlifecyclemodels</span><span class="sxs-lookup"><span data-stu-id="6f601-123">msdyn\_functionallocationlifecyclemodels</span></span> | |
| <span data-ttu-id="6f601-124">Administración de activos ubicación técnica de estados de ciclo de vida</span><span class="sxs-lookup"><span data-stu-id="6f601-124">Asset management functional location lifecycle states</span></span> | <span data-ttu-id="6f601-125">msdyn\_functionallocationlifecyclestates</span><span class="sxs-lookup"><span data-stu-id="6f601-125">msdyn\_functionallocationlifecyclestates</span></span> | |
| <span data-ttu-id="6f601-126">Administración de activos de ubicaciones técnicas</span><span class="sxs-lookup"><span data-stu-id="6f601-126">Asset management functional locations</span></span> | <span data-ttu-id="6f601-127">msdyn\_functionallocations</span><span class="sxs-lookup"><span data-stu-id="6f601-127">msdyn\_functionallocations</span></span> | |
| <span data-ttu-id="6f601-128">Administración de activos de tipos de ubicación técnica</span><span class="sxs-lookup"><span data-stu-id="6f601-128">Asset management functional location types</span></span> | <span data-ttu-id="6f601-129">msdyn\_functionallocationtypes</span><span class="sxs-lookup"><span data-stu-id="6f601-129">msdyn\_functionallocationtypes</span></span> | |
| <span data-ttu-id="6f601-130">Administración de activos de fabricantes</span><span class="sxs-lookup"><span data-stu-id="6f601-130">Asset management manufacturers</span></span> | <span data-ttu-id="6f601-131">msdyn\_manufacturers</span><span class="sxs-lookup"><span data-stu-id="6f601-131">msdyn\_manufacturers</span></span> | |
| <span data-ttu-id="6f601-132">Administración de activos de modelos</span><span class="sxs-lookup"><span data-stu-id="6f601-132">Asset management models</span></span> | <span data-ttu-id="6f601-133">msdyn\_models</span><span class="sxs-lookup"><span data-stu-id="6f601-133">msdyn\_models</span></span> | |
| <span data-ttu-id="6f601-134">Administración de activos de garantía</span><span class="sxs-lookup"><span data-stu-id="6f601-134">Asset management warranty</span></span> | <span data-ttu-id="6f601-135">msdyn\_warranties</span><span class="sxs-lookup"><span data-stu-id="6f601-135">msdyn\_warranties</span></span> | |

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [lifecycle models](includes/AssetManagementAssetLifecycleModels-msdyn-assetlifecyclemodels.md)]

[!include [lifecycle states](includes/AssetManagementAssetLifecycleStates-msdyn-assetlifecyclestates.md)]

[!include [assets](includes/AssetManagementAssets-msdyn-customerassets.md)]

[!include [asset types](includes/AssetManagementAssetTypes-msdyn-customerassetcategories.md)]

[!include [functional location lifecycle models](includes/AssetManagementFunctionalLocationLifecycleModels-msdyn-functionallocationlifecyclemodels.md)]

[!include [functional location lifecycle states](includes/AssetManagementFunctionalLocationLifecycleStates-msdyn-functionallocationlifecyclestates.md)]

[!include [functional locations](includes/AssetManagementFunctionalLocations-msdyn-functionallocations.md)]

[!include [functional location types](includes/AssetManagementFunctionalLocationTypes-msdyn-functionallocationtypes.md)]

[!include [manufacturers](includes/AssetManagementManufacturers-msdyn-manufacturers.md)]

[!include [models](includes/AssetManagementModels-msdyn-models.md)]

[!include [warranty](includes/AssetManagementWarranty-msdyn-warranties.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]