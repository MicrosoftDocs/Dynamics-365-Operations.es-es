---
title: Jerarquía organizativa en Common Data Service
description: Este tema describe la integración de datos organizatiovs entre aplicaciones de Finance and Operations y Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 9efc63c385c31a6d8848d016c1a8689460908dcc
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769669"
---
# <a name="organization-hierarchy-in-common-data-service"></a>Jerarquía organizativa en Common Data Service

[!include [banner](../includes/banner.md)]

Como Dynamics 365 Finance es un sistema financiero, *organización* es un concepto básico y la configuración del sistema empieza con la configuración de una jerarquía organizativa. Los operaciones empresariales se pueden seguir por tanto en el nivel de la organización y también en cualquier nivel de la jerarquía organizativa.

Aunque Common Data Service no tenga el concepto de una jerarquía organizativa, tiene algunos flexibles como los ingresos de ventas totales. Como parte de la integración de Common Data Service, la estructura de datos de la jerarquía se agrega a Common Data Service.

## <a name="data-flow"></a>Flujo de datos

Un ecosistema de negocio que conste de aplicaciones de Finance and Operations y Common Data Service seguirá teniendo una jerarquía organizativa. Esta jerarquía organizativa se basa en aplicaciones Finance and Operations pero se expone en Common Data Service para fines informativos y de extensibilidad. La ilustración siguiente muestra la información de la jerarquía organizativa expuesta en Common Data Service como un flujo de datos unidireccional de aplicaciones de Finance and Operations a Common Data Service.

![Imagen de la arquitectura](media/dual-write-data-flow.png)

## <a name="templates"></a>Plantillas

Los mapas de entidad de la jerarquía organizativa están disponibles para la sincronización unidireccional de datos de aplicaciones de Finance and Operations con Common Data Service.

## <a name="templates"></a>Plantillas

La información de producto contiene toda la información relacionada con el producto y la definición, como las dimensiones del producto o el seguimiento y las dimensiones de almacenamiento. Como la tabla siguiente muestra, una colección de mapas de la entidad se crea para sincronizar los productos y la información relacionada.

Finance and Operations | Otras aplicaciones de Dynamics 365 | Descripción
-----------------------|--------------------------------|---
Propósitos de jerarquía organizativa | msdyn_internalorganizationhierarchypurposes | Esta plantilla proporciona la sincronización unidireccional de la entidad de propósito de la jerarquía organizativa.
Tipo de jerarquía organizativa | msdyn_internalorganizationhierarchytypes | Esta plantilla proporciona la sincronización unidireccional de la entidad de tipo de jerarquía organizativa.
Jerarquía organizativa - publicada | msdyn_internalorganizationhierarchies | Esta plantilla proporciona la sincronización unidireccional de la entidad publicada de la jerarquía organizativa.
Unidad operativa | msdyn_internalorganizations | 
Entidades jurídicas | msdyn_internalorganizations | 
Entidades jurídicas | cdm_companies | Proporciona la sincronización bidireccional de la información de la entidad jurídica (empresa).


[!include [banner](../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](dual-write/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](dual-write/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](dual-write/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a>Organización interna

La información de la organización interna en Common Data Service se deriva de dos entidades, **unidad operativa** y **entidades jurídicas**.

[!include [Operating unit](dual-write/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](dual-write/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](dual-write/LegalEntities-Companies.md)]

