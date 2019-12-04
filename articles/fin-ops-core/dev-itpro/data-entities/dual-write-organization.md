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
# <a name="organization-hierarchy-in-common-data-service"></a><span data-ttu-id="c74f2-103">Jerarquía organizativa en Common Data Service</span><span class="sxs-lookup"><span data-stu-id="c74f2-103">Organization hierarchy in Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c74f2-104">Como Dynamics 365 Finance es un sistema financiero, *organización* es un concepto básico y la configuración del sistema empieza con la configuración de una jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="c74f2-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="c74f2-105">Los operaciones empresariales se pueden seguir por tanto en el nivel de la organización y también en cualquier nivel de la jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="c74f2-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="c74f2-106">Aunque Common Data Service no tenga el concepto de una jerarquía organizativa, tiene algunos flexibles como los ingresos de ventas totales.</span><span class="sxs-lookup"><span data-stu-id="c74f2-106">Although Common Data Service doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="c74f2-107">Como parte de la integración de Common Data Service, la estructura de datos de la jerarquía se agrega a Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c74f2-107">As part of Common Data Service integration, the organization hierarchy data structure is added to Common Data Service.</span></span>

## <a name="data-flow"></a><span data-ttu-id="c74f2-108">Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="c74f2-108">Data flow</span></span>

<span data-ttu-id="c74f2-109">Un ecosistema de negocio que conste de aplicaciones de Finance and Operations y Common Data Service seguirá teniendo una jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="c74f2-109">A business ecosystem that consists of Finance and Operations apps and Common Data Service will continue to have an organization hierarchy.</span></span> <span data-ttu-id="c74f2-110">Esta jerarquía organizativa se basa en aplicaciones Finance and Operations pero se expone en Common Data Service para fines informativos y de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="c74f2-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Common Data Service for informational and extensibility purposes.</span></span> <span data-ttu-id="c74f2-111">La ilustración siguiente muestra la información de la jerarquía organizativa expuesta en Common Data Service como un flujo de datos unidireccional de aplicaciones de Finance and Operations a Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c74f2-111">The following illustration shows the organization hierarchy information that is exposed in Common Data Service as a one-way data flow from Finance and Operations apps to Common Data Service.</span></span>

![Imagen de la arquitectura](media/dual-write-data-flow.png)

## <a name="templates"></a><span data-ttu-id="c74f2-113">Plantillas</span><span class="sxs-lookup"><span data-stu-id="c74f2-113">Templates</span></span>

<span data-ttu-id="c74f2-114">Los mapas de entidad de la jerarquía organizativa están disponibles para la sincronización unidireccional de datos de aplicaciones de Finance and Operations con Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c74f2-114">Organization hierarchy entity maps are available for one-way synchronization of data from Finance and Operations apps to Common Data Service.</span></span>

## <a name="templates"></a><span data-ttu-id="c74f2-115">Plantillas</span><span class="sxs-lookup"><span data-stu-id="c74f2-115">Templates</span></span>

<span data-ttu-id="c74f2-116">La información de producto contiene toda la información relacionada con el producto y la definición, como las dimensiones del producto o el seguimiento y las dimensiones de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="c74f2-116">Product information contains all the information related to the product and its definition, such as the product dimensions or the tracking and storage dimensions.</span></span> <span data-ttu-id="c74f2-117">Como la tabla siguiente muestra, una colección de mapas de la entidad se crea para sincronizar los productos y la información relacionada.</span><span class="sxs-lookup"><span data-stu-id="c74f2-117">As the following table shows, a collection of entity maps is created to sync products and related information.</span></span>

<span data-ttu-id="c74f2-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c74f2-118">Finance and Operations</span></span> | <span data-ttu-id="c74f2-119">Otras aplicaciones de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c74f2-119">Other Dynamics 365 apps</span></span> | <span data-ttu-id="c74f2-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="c74f2-120">Description</span></span>
-----------------------|--------------------------------|---
<span data-ttu-id="c74f2-121">Propósitos de jerarquía organizativa</span><span class="sxs-lookup"><span data-stu-id="c74f2-121">Organization hierarchy purposes</span></span> | <span data-ttu-id="c74f2-122">msdyn_internalorganizationhierarchypurposes</span><span class="sxs-lookup"><span data-stu-id="c74f2-122">msdyn_internalorganizationhierarchypurposes</span></span> | <span data-ttu-id="c74f2-123">Esta plantilla proporciona la sincronización unidireccional de la entidad de propósito de la jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="c74f2-123">This template provides one-way synchronization of the Organization Hierarchy Purpose entity.</span></span>
<span data-ttu-id="c74f2-124">Tipo de jerarquía organizativa</span><span class="sxs-lookup"><span data-stu-id="c74f2-124">Organization hierarchy type</span></span> | <span data-ttu-id="c74f2-125">msdyn_internalorganizationhierarchytypes</span><span class="sxs-lookup"><span data-stu-id="c74f2-125">msdyn_internalorganizationhierarchytypes</span></span> | <span data-ttu-id="c74f2-126">Esta plantilla proporciona la sincronización unidireccional de la entidad de tipo de jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="c74f2-126">This template provides one-way synchronization of the Organization Hierarchy Type entity.</span></span>
<span data-ttu-id="c74f2-127">Jerarquía organizativa - publicada</span><span class="sxs-lookup"><span data-stu-id="c74f2-127">Organization hierarchy - published</span></span> | <span data-ttu-id="c74f2-128">msdyn_internalorganizationhierarchies</span><span class="sxs-lookup"><span data-stu-id="c74f2-128">msdyn_internalorganizationhierarchies</span></span> | <span data-ttu-id="c74f2-129">Esta plantilla proporciona la sincronización unidireccional de la entidad publicada de la jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="c74f2-129">This template provides one-way synchronization of the Organization Hierarchy Published entity.</span></span>
<span data-ttu-id="c74f2-130">Unidad operativa</span><span class="sxs-lookup"><span data-stu-id="c74f2-130">Operating unit</span></span> | <span data-ttu-id="c74f2-131">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="c74f2-131">msdyn_internalorganizations</span></span> | 
<span data-ttu-id="c74f2-132">Entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="c74f2-132">Legal entities</span></span> | <span data-ttu-id="c74f2-133">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="c74f2-133">msdyn_internalorganizations</span></span> | 
<span data-ttu-id="c74f2-134">Entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="c74f2-134">Legal entities</span></span> | <span data-ttu-id="c74f2-135">cdm_companies</span><span class="sxs-lookup"><span data-stu-id="c74f2-135">cdm_companies</span></span> | <span data-ttu-id="c74f2-136">Proporciona la sincronización bidireccional de la información de la entidad jurídica (empresa).</span><span class="sxs-lookup"><span data-stu-id="c74f2-136">Provides bidirectional synchronization of legal entity (company) information.</span></span>


[!include [banner](../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](dual-write/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](dual-write/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](dual-write/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a><span data-ttu-id="c74f2-137">Organización interna</span><span class="sxs-lookup"><span data-stu-id="c74f2-137">Internal Organization</span></span>

<span data-ttu-id="c74f2-138">La información de la organización interna en Common Data Service se deriva de dos entidades, **unidad operativa** y **entidades jurídicas**.</span><span class="sxs-lookup"><span data-stu-id="c74f2-138">Internal organization information in Common Data Service comes from two entities, **operating unit** and **legal entities**.</span></span>

[!include [Operating unit](dual-write/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](dual-write/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](dual-write/LegalEntities-Companies.md)]

