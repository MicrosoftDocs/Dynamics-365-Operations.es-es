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
## <a name="organization-hierarchy-in-common-data-service"></a><span data-ttu-id="6e3fd-103">Jerarquía organizativa en Common Data Service</span><span class="sxs-lookup"><span data-stu-id="6e3fd-103">Organization hierarchy in Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="6e3fd-104">Como Dynamics 365 Finance es un sistema financiero, *organización* es un concepto básico y la configuración del sistema empieza con la configuración de una jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="6e3fd-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="6e3fd-105">Los operaciones empresariales se pueden seguir por tanto en el nivel de la organización y también en cualquier nivel de la jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="6e3fd-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="6e3fd-106">Aunque Common Data Service no tenga el concepto de una jerarquía organizativa, tiene algunos flexibles como los ingresos de ventas totales.</span><span class="sxs-lookup"><span data-stu-id="6e3fd-106">Although Common Data Service doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="6e3fd-107">Como parte de la integración de Common Data Service, la estructura de datos de la jerarquía se agrega a Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="6e3fd-107">As part of Common Data Service integration, the organization hierarchy data structure is added to Common Data Service.</span></span>

## <a name="data-flow"></a><span data-ttu-id="6e3fd-108">Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="6e3fd-108">Data flow</span></span>

<span data-ttu-id="6e3fd-109">Un ecosistema de negocio que conste de aplicaciones de Finance and Operations y Common Data Service seguirá teniendo una jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="6e3fd-109">A business ecosystem that consists of Finance and Operations apps and Common Data Service will continue to have an organization hierarchy.</span></span> <span data-ttu-id="6e3fd-110">Esta jerarquía organizativa se basa en aplicaciones Finance and Operations pero se expone en Common Data Service para fines informativos y de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="6e3fd-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Common Data Service for informational and extensibility purposes.</span></span> <span data-ttu-id="6e3fd-111">La ilustración siguiente muestra la información de la jerarquía organizativa expuesta en Common Data Service como un flujo de datos unidireccional de aplicaciones de Finance and Operations a Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="6e3fd-111">The following illustration shows the organization hierarchy information that is exposed in Common Data Service as a one-way data flow from Finance and Operations apps to Common Data Service.</span></span>

![Imagen de la arquitectura](media/dual-write-data-flow.png)

## <a name="templates"></a><span data-ttu-id="6e3fd-113">Plantillas</span><span class="sxs-lookup"><span data-stu-id="6e3fd-113">Templates</span></span>

<span data-ttu-id="6e3fd-114">Los mapas de entidad de la jerarquía organizativa están disponibles para la sincronización unidireccional de datos de aplicaciones de Finance and Operations con Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="6e3fd-114">Organization hierarchy entity maps are available for one-way synchronization of data from Finance and Operations apps to Common Data Service.</span></span>

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="internal-organization-hierarchy-purpose"></a><span data-ttu-id="6e3fd-115">Propósito de jerarquía organizativa interna</span><span class="sxs-lookup"><span data-stu-id="6e3fd-115">Internal Organization Hierarchy Purpose</span></span>

<span data-ttu-id="6e3fd-116">Esta plantilla proporciona la sincronización unidireccional de la entidad de propósito de jerarquía organizativa de Finance and Operations a otras aplicaciones de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="6e3fd-116">This template provides one-way synchronization of the Organization Hierarchy Purpose entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-purpose.png) -->

<span data-ttu-id="6e3fd-117">Campo de origen</span><span class="sxs-lookup"><span data-stu-id="6e3fd-117">Source field</span></span> | <span data-ttu-id="6e3fd-118">Tipo de asignación</span><span class="sxs-lookup"><span data-stu-id="6e3fd-118">Map type</span></span> | <span data-ttu-id="6e3fd-119">Campo de destino</span><span class="sxs-lookup"><span data-stu-id="6e3fd-119">Destination field</span></span>
---|---|---
<span data-ttu-id="6e3fd-120">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="6e3fd-120">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="6e3fd-121">msdyn\_hierarchypurposetypename</span><span class="sxs-lookup"><span data-stu-id="6e3fd-121">msdyn\_hierarchypurposetypename</span></span>
<span data-ttu-id="6e3fd-122">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="6e3fd-122">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="6e3fd-123">msdyn\_hierarchytype.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="6e3fd-123">msdyn\_hierarchytype.msdyn\_name</span></span>
<span data-ttu-id="6e3fd-124">HIERARCHYPURPOSE</span><span class="sxs-lookup"><span data-stu-id="6e3fd-124">HIERARCHYPURPOSE</span></span> | \>\> | <span data-ttu-id="6e3fd-125">msdyn\_hierarchypurpose</span><span class="sxs-lookup"><span data-stu-id="6e3fd-125">msdyn\_hierarchypurpose</span></span>
<span data-ttu-id="6e3fd-126">IMMUTABLE</span><span class="sxs-lookup"><span data-stu-id="6e3fd-126">IMMUTABLE</span></span> | \>\> | <span data-ttu-id="6e3fd-127">msdyn\_immutable</span><span class="sxs-lookup"><span data-stu-id="6e3fd-127">msdyn\_immutable</span></span>
<span data-ttu-id="6e3fd-128">SETASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="6e3fd-128">SETASDEFAULT</span></span> | \>\> | <span data-ttu-id="6e3fd-129">msdyn\_setasdefault</span><span class="sxs-lookup"><span data-stu-id="6e3fd-129">msdyn\_setasdefault</span></span>

## <a name="internal-organization-hierarchy-type"></a><span data-ttu-id="6e3fd-130">Tipo de jerarquía organizativa interna</span><span class="sxs-lookup"><span data-stu-id="6e3fd-130">Internal Organization Hierarchy Type</span></span>

<span data-ttu-id="6e3fd-131">Esta plantilla proporciona la sincronización unidireccional de la entidad de propósito de tipo organizativo de Finance and Operations a otras aplicaciones de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="6e3fd-131">Tihs template provides one-way synchronization of the Organization Hierarchy Type entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-type.png) -->

<span data-ttu-id="6e3fd-132">Campo de origen</span><span class="sxs-lookup"><span data-stu-id="6e3fd-132">Source field</span></span> | <span data-ttu-id="6e3fd-133">Tipo de asignación</span><span class="sxs-lookup"><span data-stu-id="6e3fd-133">Map type</span></span> | <span data-ttu-id="6e3fd-134">Campo de destino</span><span class="sxs-lookup"><span data-stu-id="6e3fd-134">Destination field</span></span>
---|---|---
<span data-ttu-id="6e3fd-135">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="6e3fd-135">NAME</span></span> | \> | <span data-ttu-id="6e3fd-136">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="6e3fd-136">msdyn\_name</span></span>

## <a name="internal-organization-hierarchy"></a><span data-ttu-id="6e3fd-137">Jerarquía organizativa interna</span><span class="sxs-lookup"><span data-stu-id="6e3fd-137">Internal Organization Hierarchy</span></span>

<span data-ttu-id="6e3fd-138">Esta plantilla proporciona la sincronización unidireccional de la entidad publicada de jerarquía organizativa de Finance and Operations a otras aplicaciones de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="6e3fd-138">This template provides one-way synchronization of the Organization Hierarchy Published entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-organization.png) -->

<span data-ttu-id="6e3fd-139">Campo de origen</span><span class="sxs-lookup"><span data-stu-id="6e3fd-139">Source field</span></span> | <span data-ttu-id="6e3fd-140">Tipo de asignación</span><span class="sxs-lookup"><span data-stu-id="6e3fd-140">Map type</span></span> | <span data-ttu-id="6e3fd-141">Campo de destino</span><span class="sxs-lookup"><span data-stu-id="6e3fd-141">Destination field</span></span>
---|---|---
<span data-ttu-id="6e3fd-142">VALIDTO</span><span class="sxs-lookup"><span data-stu-id="6e3fd-142">VALIDTO</span></span> | \> | <span data-ttu-id="6e3fd-143">msdyn\_validto</span><span class="sxs-lookup"><span data-stu-id="6e3fd-143">msdyn\_validto</span></span>
<span data-ttu-id="6e3fd-144">VALIDFROM</span><span class="sxs-lookup"><span data-stu-id="6e3fd-144">VALIDFROM</span></span> | \> | <span data-ttu-id="6e3fd-145">msdyn\_validfrom</span><span class="sxs-lookup"><span data-stu-id="6e3fd-145">msdyn\_validfrom</span></span>
<span data-ttu-id="6e3fd-146">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="6e3fd-146">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="6e3fd-147">msdyn\_hierarchytypename</span><span class="sxs-lookup"><span data-stu-id="6e3fd-147">msdyn\_hierarchytypename</span></span>
<span data-ttu-id="6e3fd-148">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="6e3fd-148">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="6e3fd-149">msdyn\_parentpartyid</span><span class="sxs-lookup"><span data-stu-id="6e3fd-149">msdyn\_parentpartyid</span></span>
<span data-ttu-id="6e3fd-150">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="6e3fd-150">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="6e3fd-151">msdyn\_childpartyid</span><span class="sxs-lookup"><span data-stu-id="6e3fd-151">msdyn\_childpartyid</span></span>
<span data-ttu-id="6e3fd-152">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="6e3fd-152">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="6e3fd-153">msdyn\_hierarchytypeid.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="6e3fd-153">msdyn\_hierarchytypeid.msdyn\_name</span></span>
<span data-ttu-id="6e3fd-154">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="6e3fd-154">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="6e3fd-155">msdyn\_childid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="6e3fd-155">msdyn\_childid.msdyn\_partynumber</span></span>
<span data-ttu-id="6e3fd-156">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="6e3fd-156">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="6e3fd-157">msdyn\_parentid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="6e3fd-157">msdyn\_parentid.msdyn\_partynumber</span></span>

## <a name="internal-organization"></a><span data-ttu-id="6e3fd-158">Organización interna</span><span class="sxs-lookup"><span data-stu-id="6e3fd-158">Internal Organization</span></span>

<span data-ttu-id="6e3fd-159">La información de la organización interna en Common Data Service se deriva de dos entidades, **unidad operativa** y **entidades jurídicas**.</span><span class="sxs-lookup"><span data-stu-id="6e3fd-159">Internal organization information in Common Data Service comes from two entities, **operating unit** and **legal entities**.</span></span>

<!-- ![architecture image](media/dual-write-operating-unit.png) -->

<!-- ![architecture image](media/dual-write-legal-entities.png) -->

### <a name="operating-unit"></a><span data-ttu-id="6e3fd-160">Unidad operativa</span><span class="sxs-lookup"><span data-stu-id="6e3fd-160">Operating unit</span></span>

<span data-ttu-id="6e3fd-161">Campo de origen</span><span class="sxs-lookup"><span data-stu-id="6e3fd-161">Source field</span></span> | <span data-ttu-id="6e3fd-162">Tipo de asignación</span><span class="sxs-lookup"><span data-stu-id="6e3fd-162">Map type</span></span> | <span data-ttu-id="6e3fd-163">Campo de destino</span><span class="sxs-lookup"><span data-stu-id="6e3fd-163">Destination field</span></span>
---|---|---
<span data-ttu-id="6e3fd-164">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="6e3fd-164">LANGUAGEID</span></span> | \> | <span data-ttu-id="6e3fd-165">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="6e3fd-165">msdyn\_languageid</span></span>
<span data-ttu-id="6e3fd-166">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="6e3fd-166">NAMEALIAS</span></span> | \> | <span data-ttu-id="6e3fd-167">msdyn\_namealias</span><span class="sxs-lookup"><span data-stu-id="6e3fd-167">msdyn\_namealias</span></span>
<span data-ttu-id="6e3fd-168">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="6e3fd-168">NAME</span></span> | \> | <span data-ttu-id="6e3fd-169">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="6e3fd-169">msdyn\_name</span></span>
<span data-ttu-id="6e3fd-170">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="6e3fd-170">PARTYNUMBER</span></span> | \> | <span data-ttu-id="6e3fd-171">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="6e3fd-171">msdyn\_partynumber</span></span>
<span data-ttu-id="6e3fd-172">OPERATINGUNITTYPE</span><span class="sxs-lookup"><span data-stu-id="6e3fd-172">OPERATINGUNITTYPE</span></span> | \>\> | <span data-ttu-id="6e3fd-173">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="6e3fd-173">msdyn\_type</span></span>

### <a name="legal-entity"></a><span data-ttu-id="6e3fd-174">Entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="6e3fd-174">Legal entity</span></span>

<span data-ttu-id="6e3fd-175">Campo de origen</span><span class="sxs-lookup"><span data-stu-id="6e3fd-175">Source field</span></span> | <span data-ttu-id="6e3fd-176">Tipo de asignación</span><span class="sxs-lookup"><span data-stu-id="6e3fd-176">Map type</span></span> | <span data-ttu-id="6e3fd-177">Campo de destino</span><span class="sxs-lookup"><span data-stu-id="6e3fd-177">Destination field</span></span>
---|---|---
<span data-ttu-id="6e3fd-178">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="6e3fd-178">NAMEALIAS</span></span> | \> | <span data-ttu-id="6e3fd-179">msdyn\_namealias</span><span class="sxs-lookup"><span data-stu-id="6e3fd-179">msdyn\_namealias</span></span>
<span data-ttu-id="6e3fd-180">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="6e3fd-180">LANGUAGEID</span></span> | \> | <span data-ttu-id="6e3fd-181">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="6e3fd-181">msdyn\_languageid</span></span>
<span data-ttu-id="6e3fd-182">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="6e3fd-182">NAME</span></span> | \> | <span data-ttu-id="6e3fd-183">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="6e3fd-183">msdyn\_name</span></span>
<span data-ttu-id="6e3fd-184">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="6e3fd-184">PARTYNUMBER</span></span> | \> | <span data-ttu-id="6e3fd-185">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="6e3fd-185">msdyn\_partynumber</span></span>
<span data-ttu-id="6e3fd-186">ninguno</span><span class="sxs-lookup"><span data-stu-id="6e3fd-186">none</span></span> | \>\> | <span data-ttu-id="6e3fd-187">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="6e3fd-187">msdyn\_type</span></span>
<span data-ttu-id="6e3fd-188">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="6e3fd-188">LEGALENTITYID</span></span> | \> | <span data-ttu-id="6e3fd-189">msdyn\_companycode</span><span class="sxs-lookup"><span data-stu-id="6e3fd-189">msdyn\_companycode</span></span>

## <a name="company"></a><span data-ttu-id="6e3fd-190">Compañía</span><span class="sxs-lookup"><span data-stu-id="6e3fd-190">Company</span></span>

<span data-ttu-id="6e3fd-191">Proporciona sincronización bidireccional de la información de la entidad jurídica (empresa) entre Finance and Operations y aplicaciones de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="6e3fd-191">Provides bidirectional synchronization of legal entity (company) information between Finance and Operations and other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-company.png) -->

<span data-ttu-id="6e3fd-192">Campo de origen</span><span class="sxs-lookup"><span data-stu-id="6e3fd-192">Source field</span></span> | <span data-ttu-id="6e3fd-193">Tipo de asignación</span><span class="sxs-lookup"><span data-stu-id="6e3fd-193">Map type</span></span> | <span data-ttu-id="6e3fd-194">Campo de destino</span><span class="sxs-lookup"><span data-stu-id="6e3fd-194">Destination field</span></span>
---|---|---
<span data-ttu-id="6e3fd-195">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="6e3fd-195">NAME</span></span> | = | <span data-ttu-id="6e3fd-196">cdm\_name</span><span class="sxs-lookup"><span data-stu-id="6e3fd-196">cdm\_name</span></span>
<span data-ttu-id="6e3fd-197">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="6e3fd-197">LEGALENTITYID</span></span> | = | <span data-ttu-id="6e3fd-198">cdm\_companycode</span><span class="sxs-lookup"><span data-stu-id="6e3fd-198">cdm\_companycode</span></span>
