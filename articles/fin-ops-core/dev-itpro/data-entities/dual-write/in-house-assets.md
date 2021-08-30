---
title: Activos internos para mantenimiento
description: Este tema describe cómo puede utilizar Microsoft Dynamics 365 Field Service para dar servicio tanto a los activos del cliente como a los activos internos.
author: RamaKrishnamoorthy
ms.date: 01/27/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: 0700025288bda1b2c67cc3ff26dc2e737216a5f8f5265464c6c62d9cb890b580
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742319"
---
# <a name="in-house-assets-for-servicing"></a>Activos internos para mantenimiento

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Field Service está diseñado para dar servicio a los activos del cliente. La gestión de activos para Dynamics 365 Supply Chain Management está diseñada para mantener los activos internos. La integración de estas dos aplicaciones le permite utilizar Field Service para atender los activos de los clientes y los activos internos. También puede clasificar los activos, según la ubicación técnica o la jerarquía, y realizar un seguimiento del servicio a un nivel detallado.

Para más información, vea [Integrar Dynamics 365 Field Service y Supply Chain Management](/dynamics365/field-service/supply-chain-field-service-integration).

## <a name="templates"></a>Plantillas

Los activos internos incluyes una colección de mapas de tabla básicos que funcionan conjuntamente durante la interacción de los datos, como se muestra en la tabla siguiente.

| Aplicaciones de Finance and Operations | Aplicaciones Customer Engagement | Descripción |
|-----------------------------|-----------------------------------|-------------|
[Administración de activos de activos de modelos de ciclos de vida](mapping-reference.md#119) | msdyn_assetlifecyclemodels | |
[Administración de activos de activos de estados de ciclos de vida](mapping-reference.md#120) | msdyn_assetlifecyclestates | |
[Administración de activos de tipos de activos](mapping-reference.md#124) | msdyn_customerassetcategories | |
[Administración de activos de activos](mapping-reference.md#125) | msdyn_customerassets | |
[Administración de activos ubicación técnica de modelos de ciclo de vida](mapping-reference.md#134) | msdyn_functionallocationlifecyclemodels | |
[Administración de activos ubicación técnica de estados de ciclo de vida](mapping-reference.md#135) | msdyn_functionallocationlifecyclestates | |
[Administración de activos de tipos de ubicación técnica](mapping-reference.md#137) | msdyn_functionallocationtypes | |
[Administración de activos de ubicaciones técnicas](mapping-reference.md#136) | msdyn_functionallocations | |
[Administración de activos de fabricantes](mapping-reference.md#153) | msdyn_manufacturers | |
[Administración de activos de modelos](mapping-reference.md#154) | msdyn_models | |
[Administración de activos de garantía](mapping-reference.md#209) | msdyn_warranties | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
