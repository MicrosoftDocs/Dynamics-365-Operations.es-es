---
title: Jerarquía organizativa en Dataverse
description: Este tema describe la integración de datos organizativos entre aplicaciones de Finance and Operations y Dataverse.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 5132fd85fdf2c08ccded9db590328c394a2f984e
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744702"
---
# <a name="organization-hierarchy-in-dataverse"></a>Jerarquía organizativa en Dataverse

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Como Dynamics 365 Finance es un sistema financiero, *organización* es un concepto básico y la configuración del sistema empieza con la configuración de una jerarquía organizativa. Los operaciones empresariales se pueden seguir por tanto en el nivel de la organización y también en cualquier nivel de la jerarquía organizativa.

Aunque Dataverse no tenga el concepto de una jerarquía organizativa, tiene algunos flexibles como los ingresos de ventas totales. Como parte de la integración de Dataverse, la estructura de datos de la jerarquía se agrega a Dataverse.

## <a name="data-flow"></a>Flujo de datos

Un ecosistema de negocio que conste de aplicaciones de Finance and Operations y Dataverse seguirá teniendo una jerarquía organizativa. Esta jerarquía organizativa se basa en aplicaciones de Finance and Operations, pero se expone en Dataverse para fines informativos y de extensibilidad. La ilustración siguiente muestra la información de la jerarquía organizativa expuesta en Dataverse como un flujo de datos unidireccional de aplicaciones de Finance and Operations a Dataverse.

![Imagen de la arquitectura](media/dual-write-data-flow.png)

Los mapas de tabla de la jerarquía organizativa están disponibles para la sincronización unidireccional de datos de aplicaciones de Finance and Operations con Dataverse.

## <a name="templates"></a>Plantillas

La información de producto contiene toda la información relacionada con el producto y la definición, como las dimensiones del producto o el seguimiento y las dimensiones de almacenamiento. Como la tabla siguiente muestra, una colección de mapas de la tabla se crea para sincronizar los productos y la información relacionada.

Aplicaciones de Finance and Operations | Otras aplicaciones de Dynamics 365 | Descripción
-----------------------|--------------------------------|---
Propósitos de jerarquía organizativa | msdyn_internalorganizationhierarchypurposes | Esta plantilla proporciona la sincronización unidireccional de la tabla de propósito de la jerarquía organizativa.
Tipo de jerarquía organizativa | msdyn_internalorganizationhierarchytypes | Esta plantilla proporciona la sincronización unidireccional de la tabla de tipo de jerarquía organizativa.
Jerarquía organizativa - publicada | msdyn_internalorganizationhierarchies | Esta plantilla proporciona la sincronización unidireccional de la tabla publicada de la jerarquía organizativa.
Unidad operativa | msdyn_internalorganizations |
Entidades jurídicas | msdyn_internalorganizations |
Entidades jurídicas | cdm_companies | Proporciona la sincronización bidireccional de la información de la entidad jurídica (empresa).

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a>Organización interna

La información de la organización interna en Dataverse se deriva de dos tablas, **unidad operativa** y **entidades jurídicas**.

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]