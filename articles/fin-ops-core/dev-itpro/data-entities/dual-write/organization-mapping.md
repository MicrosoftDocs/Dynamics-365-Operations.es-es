---
title: Jerarquía organizativa en Dataverse
description: Este tema describe la integración de datos organizatiovs entre aplicaciones de Finance and Operations y Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 9174612743c68595d12dd223f0932ace1857c0fb
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2022
ms.locfileid: "8358373"
---
# <a name="organization-hierarchy-in-dataverse"></a>Jerarquía organizativa en Dataverse

[!include [banner](../../includes/banner.md)]



Como Dynamics 365 Finance es un sistema financiero, *organización* es un concepto básico y la configuración del sistema empieza con la configuración de una jerarquía organizativa. Los operaciones empresariales se pueden seguir por tanto en el nivel de la organización y también en cualquier nivel de la jerarquía organizativa.

Aunque Dataverse no tenga el concepto de una jerarquía organizativa, tiene algunos flexibles como los ingresos de ventas totales. Como parte de la integración de Dataverse, la estructura de datos de la jerarquía se agrega a Dataverse.

## <a name="data-flow"></a>Flujo de datos

Un ecosistema de negocio que conste de aplicaciones de Finance and Operations y Dataverse seguirá teniendo una jerarquía organizativa. Esta jerarquía organizativa se basa en aplicaciones Finance and Operations pero se expone en Dataverse para fines informativos y de extensibilidad. La ilustración siguiente muestra la información de la jerarquía organizativa expuesta en Dataverse como un flujo de datos unidireccional de aplicaciones de Finance and Operations a Dataverse.

![Imagen de la arquitectura.](media/dual-write-data-flow.png)

Los mapas de tabla de la jerarquía organizativa están disponibles para la sincronización unidireccional de datos de aplicaciones de Finanzas y operaciones con Dataverse.

## <a name="templates"></a>Plantillas

Una organización es un grupo de personas que trabajan juntas para llevar a cabo un proceso empresarial o lograr un objetivo. Las jerarquías organizativas representan las relaciones que hay entre las organizaciones que forman el negocio. Puede definir los siguientes tipos de organizaciones internas: entidades jurídicas, unidades operativas y equipos. Como muestra la siguiente tabla, se crea una colección de mapas de tablas para sincronizar entidades legales, unidades operativas e información relacionada con la jerarquía de la organización.

Aplicaciones de Finance and Operations | Aplicaciones Customer Engagement     | Description
-----------------------|--------------------------------|---
[Entidades jurídicas](mapping-reference.md#102) | cdm_companies | 
[Entidades jurídicas](mapping-reference.md#142) | msdyn_internalorganizations |
[Unidad operativa](mapping-reference.md#143) | msdyn_internalorganizations |
[Jerarquía organizativa - publicada](mapping-reference.md#139) | msdyn_internalorganizationhierarchies | Esta plantilla proporciona la sincronización unidireccional de la tabla publicada de la jerarquía organizativa.
[Propósitos de jerarquía organizativa](mapping-reference.md#140) | msdyn_internalorganizationhierarchypurposes | Esta plantilla proporciona la sincronización unidireccional de la tabla de propósito de la jerarquía organizativa.
[Tipo de jerarquía organizativa](mapping-reference.md#141) | msdyn_internalorganizationhierarchytypes | Esta plantilla proporciona la sincronización unidireccional de la tabla de tipo de jerarquía organizativa.

## <a name="internal-organization"></a>Organización interna

La información de la organización interna en Dataverse se deriva de dos tablas, **Unidad operativa** y **Entidades jurídicas**.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
