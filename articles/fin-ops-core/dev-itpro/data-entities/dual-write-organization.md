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
ms.openlocfilehash: fd159b38f69305dcaecb364ba0ccb3befabb3582
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182034"
---
## <a name="organization-hierarchy-in-common-data-service"></a>Jerarquía organizativa en Common Data Service

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Como Dynamics 365 Finance es un sistema financiero, *organización* es un concepto básico y la configuración del sistema empieza con la configuración de una jerarquía organizativa. Los operaciones empresariales se pueden seguir por tanto en el nivel de la organización y también en cualquier nivel de la jerarquía organizativa.

Aunque Common Data Service no tenga el concepto de una jerarquía organizativa, tiene algunos flexibles como los ingresos de ventas totales. Como parte de la integración de Common Data Service, la estructura de datos de la jerarquía se agrega a Common Data Service.

## <a name="data-flow"></a>Flujo de datos

Un ecosistema de negocio que conste de aplicaciones de Finance and Operations y Common Data Service seguirá teniendo una jerarquía organizativa. Esta jerarquía organizativa se basa en aplicaciones Finance and Operations pero se expone en Common Data Service para fines informativos y de extensibilidad. La ilustración siguiente muestra la información de la jerarquía organizativa expuesta en Common Data Service como un flujo de datos unidireccional de aplicaciones de Finance and Operations a Common Data Service.

![Imagen de la arquitectura](media/dual-write-data-flow.png)

## <a name="templates"></a>Plantillas

Los mapas de entidad de la jerarquía organizativa están disponibles para la sincronización unidireccional de datos de aplicaciones de Finance and Operations con Common Data Service.

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="internal-organization-hierarchy-purpose"></a>Propósito de jerarquía organizativa interna

Esta plantilla proporciona la sincronización unidireccional de la entidad de propósito de jerarquía organizativa de Finance and Operations a otras aplicaciones de Dynamics 365.

<!-- ![architecture image](media/dual-write-purpose.png) -->

Campo de origen | Tipo de asignación | Campo de destino
---|---|---
HIERARCHYTYPE | \> | msdyn\_hierarchypurposetypename
HIERARCHYTYPE | \> | msdyn\_hierarchytype.msdyn\_name
HIERARCHYPURPOSE | \>\> | msdyn\_hierarchypurpose
IMMUTABLE | \>\> | msdyn\_immutable
SETASDEFAULT | \>\> | msdyn\_setasdefault

## <a name="internal-organization-hierarchy-type"></a>Tipo de jerarquía organizativa interna

Esta plantilla proporciona la sincronización unidireccional de la entidad de propósito de tipo organizativo de Finance and Operations a otras aplicaciones de Dynamics 365.

<!-- ![architecture image](media/dual-write-type.png) -->

Campo de origen | Tipo de asignación | Campo de destino
---|---|---
NOMBRE | \> | msdyn\_name

## <a name="internal-organization-hierarchy"></a>Jerarquía organizativa interna

Esta plantilla proporciona la sincronización unidireccional de la entidad publicada de jerarquía organizativa de Finance and Operations a otras aplicaciones de Dynamics 365.

<!-- ![architecture image](media/dual-write-organization.png) -->

Campo de origen | Tipo de asignación | Campo de destino
---|---|---
VALIDTO | \> | msdyn\_validto
VALIDFROM | \> | msdyn\_validfrom
HIERARCHYTYPE | \> | msdyn\_hierarchytypename
PARENTORGANIZATIONPARTYNUMBER | \> | msdyn\_parentpartyid
CHILDORGANIZATIONPARTYNUMBER | \> | msdyn\_childpartyid
HIERARCHYTYPE | \> | msdyn\_hierarchytypeid.msdyn\_name
CHILDORGANIZATIONPARTYNUMBER | \> | msdyn\_childid.msdyn\_partynumber
PARENTORGANIZATIONPARTYNUMBER | \> | msdyn\_parentid.msdyn\_partynumber

## <a name="internal-organization"></a>Organización interna

La información de la organización interna en Common Data Service se deriva de dos entidades, **unidad operativa** y **entidades jurídicas**.

<!-- ![architecture image](media/dual-write-operating-unit.png) -->

<!-- ![architecture image](media/dual-write-legal-entities.png) -->

### <a name="operating-unit"></a>Unidad operativa

Campo de origen | Tipo de asignación | Campo de destino
---|---|---
LANGUAGEID | \> | msdyn\_languageid
NAMEALIAS | \> | msdyn\_namealias
NOMBRE | \> | msdyn\_name
PARTYNUMBER | \> | msdyn\_partynumber
OPERATINGUNITTYPE | \>\> | msdyn\_type

### <a name="legal-entity"></a>Entidad jurídica

Campo de origen | Tipo de asignación | Campo de destino
---|---|---
NAMEALIAS | \> | msdyn\_namealias
LANGUAGEID | \> | msdyn\_languageid
NOMBRE | \> | msdyn\_name
PARTYNUMBER | \> | msdyn\_partynumber
ninguno | \>\> | msdyn\_type
LEGALENTITYID | \> | msdyn\_companycode

## <a name="company"></a>Compañía

Proporciona sincronización bidireccional de la información de la entidad jurídica (empresa) entre Finance and Operations y aplicaciones de Dynamics 365.

<!-- ![architecture image](media/dual-write-company.png) -->

Campo de origen | Tipo de asignación | Campo de destino
---|---|---
NOMBRE | = | cdm\_name
LEGALENTITYID | = | cdm\_companycode
