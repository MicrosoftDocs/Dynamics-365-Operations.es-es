---
title: Jerarquía organizativa en Dataverse
description: Este tema describe la integración de datos organizativos entre aplicaciones de Finance and Operations y Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: d1ad3bc4eef1650b927d9f6dd699f788994c7e87
ms.sourcegitcommit: f65bde9ab0bf4c12a3250e7c9b2abb1555cd7931
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2021
ms.locfileid: "6542596"
---
# <a name="organization-hierarchy-in-dataverse"></a>Jerarquía organizativa en Dataverse

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Como Dynamics 365 Finance es un sistema financiero, *organización* es un concepto básico y la configuración del sistema empieza con la configuración de una jerarquía organizativa. Los operaciones empresariales se pueden seguir por tanto en el nivel de la organización y también en cualquier nivel de la jerarquía organizativa.

Aunque Dataverse no tenga el concepto de una jerarquía organizativa, tiene algunos flexibles como los ingresos de ventas totales. Como parte de la integración de Dataverse, la estructura de datos de la jerarquía se agrega a Dataverse.

## <a name="data-flow"></a>Flujo de datos

Un ecosistema de negocio que conste de aplicaciones de Finance and Operations y Dataverse seguirá teniendo una jerarquía organizativa. Esta jerarquía organizativa se basa en aplicaciones de Finance and Operations, pero se expone en Dataverse para fines informativos y de extensibilidad. La ilustración siguiente muestra la información de la jerarquía organizativa expuesta en Dataverse como un flujo de datos unidireccional de aplicaciones de Finance and Operations a Dataverse.

![Imagen de la arquitectura.](media/dual-write-data-flow.png)

Los mapas de tabla de la jerarquía organizativa están disponibles para la sincronización unidireccional de datos de aplicaciones de Finance and Operations con Dataverse.

## <a name="templates"></a>Plantillas

La información de producto contiene toda la información relacionada con el producto y la definición, como las dimensiones del producto o el seguimiento y las dimensiones de almacenamiento. Como la tabla siguiente muestra, una colección de mapas de la tabla se crea para sincronizar los productos y la información relacionada.

Aplicaciones de Finance and Operations | Aplicaciones Customer Engagement     | Descripción
-----------------------|--------------------------------|---
[Entidades jurídicas](mapping-reference.md#102) | cdm_companies | Proporciona la sincronización bidireccional de la información de la entidad jurídica (empresa).
[Entidades jurídicas](mapping-reference.md#142) | msdyn_internalorganizations |
[Unidad operativa](mapping-reference.md#143) | msdyn_internalorganizations |
[Jerarquía organizativa - publicada](mapping-reference.md#139) | msdyn_internalorganizationhierarchies | Esta plantilla proporciona la sincronización unidireccional de la tabla publicada de la jerarquía organizativa.
[Propósitos de jerarquía organizativa](mapping-reference.md#140) | msdyn_internalorganizationhierarchypurposes | Esta plantilla proporciona la sincronización unidireccional de la tabla de propósito de la jerarquía organizativa.
[Tipo de jerarquía organizativa](mapping-reference.md#141) | msdyn_internalorganizationhierarchytypes | Esta plantilla proporciona la sincronización unidireccional de la tabla de tipo de jerarquía organizativa.

## <a name="internal-organization"></a>Organización interna

La información de la organización interna en Dataverse se deriva de dos tablas, **Unidad operativa** y **Entidades jurídicas**.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
