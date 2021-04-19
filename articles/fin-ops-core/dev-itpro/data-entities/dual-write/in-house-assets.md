---
title: Activos internos para servicio
description: Este tema describe cómo puede usar Microsoft Dtnamics 365 Field Service para dar servicio tanto a los activos del cliente como a los activos internos.
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
ms.openlocfilehash: 040f9d26a137ebce1edc6adf28ff226b3a81e1ae
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748602"
---
# <a name="in-house-assets-for-servicing"></a>Activos internos para mantenimiento

[!include [banner](../../includes/banner.md)]



Microsoft Dynamics 365 Field Service está diseñado para dar servicio a los activos del cliente. La gestión de activos para Dynamics 365 Supply Chain Management está diseñada para mantener los activos internos. La integración de estas dos aplicaciones le permite utilizar Field Service para atender los activos de los clientes y los activos internos. También puede clasificar los activos, según la ubicación técnica o la jerarquía, y realizar un seguimiento del servicio a un nivel detallado.

Para más información, vea [Integrar Dynamics 365 Field Service y Supply Chain Management](https://docs.microsoft.com/dynamics365/field-service/supply-chain-field-service-integration).

## <a name="templates"></a>Plantillas

Los activos internos incluyes una colección de mapas de tabla básicos que funcionan conjuntamente durante la interacción de los datos, como se muestra en la tabla siguiente.

| Aplicaciones de Finance and Operations | Aplicaciones basadas en modelos en Dynamics 365 | Descripción |
|-----------------------------|-----------------------------------|-------------|
| Administración de activos de activos de modelos de ciclos de vida | msdyn\_assetlifecyclemodels | |
| Administración de activos de activos de estados de ciclos de vida | msdyn\_assetlifecyclestates | |
| Administración de activos de activos | msdyn\_customerassets | |
| Administración de activos de tipos de activos | msdyn\_customerassetcategories | |
| Administración de activos ubicación técnica de modelos de ciclo de vida | msdyn\_functionallocationlifecyclemodels | |
| Administración de activos ubicación técnica de estados de ciclo de vida | msdyn\_functionallocationlifecyclestates | |
| Administración de activos de ubicaciones técnicas | msdyn\_functionallocations | |
| Administración de activos de tipos de ubicación técnica | msdyn\_functionallocationtypes | |
| Administración de activos de fabricantes | msdyn\_manufacturers | |
| Administración de activos de modelos | msdyn\_models | |
| Administración de activos de garantía | msdyn\_warranties | |

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