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
# <a name="organization-hierarchy-in-dataverse"></a><span data-ttu-id="1934c-103">Jerarquía organizativa en Dataverse</span><span class="sxs-lookup"><span data-stu-id="1934c-103">Organization hierarchy in Dataverse</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="1934c-104">Como Dynamics 365 Finance es un sistema financiero, *organización* es un concepto básico y la configuración del sistema empieza con la configuración de una jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="1934c-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="1934c-105">Los operaciones empresariales se pueden seguir por tanto en el nivel de la organización y también en cualquier nivel de la jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="1934c-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="1934c-106">Aunque Dataverse no tenga el concepto de una jerarquía organizativa, tiene algunos flexibles como los ingresos de ventas totales.</span><span class="sxs-lookup"><span data-stu-id="1934c-106">Although Dataverse doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="1934c-107">Como parte de la integración de Dataverse, la estructura de datos de la jerarquía se agrega a Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1934c-107">As part of Dataverse integration, the organization hierarchy data structure is added to Dataverse.</span></span>

## <a name="data-flow"></a><span data-ttu-id="1934c-108">Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="1934c-108">Data flow</span></span>

<span data-ttu-id="1934c-109">Un ecosistema de negocio que conste de aplicaciones de Finance and Operations y Dataverse seguirá teniendo una jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="1934c-109">A business ecosystem that consists of Finance and Operations apps and Dataverse will continue to have an organization hierarchy.</span></span> <span data-ttu-id="1934c-110">Esta jerarquía organizativa se basa en aplicaciones de Finance and Operations, pero se expone en Dataverse para fines informativos y de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="1934c-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Dataverse for informational and extensibility purposes.</span></span> <span data-ttu-id="1934c-111">La ilustración siguiente muestra la información de la jerarquía organizativa expuesta en Dataverse como un flujo de datos unidireccional de aplicaciones de Finance and Operations a Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1934c-111">The following illustration shows the organization hierarchy information that is exposed in Dataverse as a one-way data flow from Finance and Operations apps to Dataverse.</span></span>

![Imagen de la arquitectura](media/dual-write-data-flow.png)

<span data-ttu-id="1934c-113">Los mapas de tabla de la jerarquía organizativa están disponibles para la sincronización unidireccional de datos de aplicaciones de Finance and Operations con Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1934c-113">Organization hierarchy table maps are available for one-way synchronization of data from Finance and Operations apps to Dataverse.</span></span>

## <a name="templates"></a><span data-ttu-id="1934c-114">Plantillas</span><span class="sxs-lookup"><span data-stu-id="1934c-114">Templates</span></span>

<span data-ttu-id="1934c-115">La información de producto contiene toda la información relacionada con el producto y la definición, como las dimensiones del producto o el seguimiento y las dimensiones de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="1934c-115">Product information contains all the information related to the product and its definition, such as the product dimensions or the tracking and storage dimensions.</span></span> <span data-ttu-id="1934c-116">Como la tabla siguiente muestra, una colección de mapas de la tabla se crea para sincronizar los productos y la información relacionada.</span><span class="sxs-lookup"><span data-stu-id="1934c-116">As the following table shows, a collection of table maps is created to sync products and related information.</span></span>

<span data-ttu-id="1934c-117">Aplicaciones de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="1934c-117">Finance and Operations apps</span></span> | <span data-ttu-id="1934c-118">Otras aplicaciones de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="1934c-118">Other Dynamics 365 apps</span></span> | <span data-ttu-id="1934c-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="1934c-119">Description</span></span>
-----------------------|--------------------------------|---
<span data-ttu-id="1934c-120">Propósitos de jerarquía organizativa</span><span class="sxs-lookup"><span data-stu-id="1934c-120">Organization hierarchy purposes</span></span> | <span data-ttu-id="1934c-121">msdyn_internalorganizationhierarchypurposes</span><span class="sxs-lookup"><span data-stu-id="1934c-121">msdyn_internalorganizationhierarchypurposes</span></span> | <span data-ttu-id="1934c-122">Esta plantilla proporciona la sincronización unidireccional de la tabla de propósito de la jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="1934c-122">This template provides one-way synchronization of the Organization Hierarchy Purpose table.</span></span>
<span data-ttu-id="1934c-123">Tipo de jerarquía organizativa</span><span class="sxs-lookup"><span data-stu-id="1934c-123">Organization hierarchy type</span></span> | <span data-ttu-id="1934c-124">msdyn_internalorganizationhierarchytypes</span><span class="sxs-lookup"><span data-stu-id="1934c-124">msdyn_internalorganizationhierarchytypes</span></span> | <span data-ttu-id="1934c-125">Esta plantilla proporciona la sincronización unidireccional de la tabla de tipo de jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="1934c-125">This template provides one-way synchronization of the Organization Hierarchy Type table.</span></span>
<span data-ttu-id="1934c-126">Jerarquía organizativa - publicada</span><span class="sxs-lookup"><span data-stu-id="1934c-126">Organization hierarchy - published</span></span> | <span data-ttu-id="1934c-127">msdyn_internalorganizationhierarchies</span><span class="sxs-lookup"><span data-stu-id="1934c-127">msdyn_internalorganizationhierarchies</span></span> | <span data-ttu-id="1934c-128">Esta plantilla proporciona la sincronización unidireccional de la tabla publicada de la jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="1934c-128">This template provides one-way synchronization of the Organization Hierarchy Published table.</span></span>
<span data-ttu-id="1934c-129">Unidad operativa</span><span class="sxs-lookup"><span data-stu-id="1934c-129">Operating unit</span></span> | <span data-ttu-id="1934c-130">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="1934c-130">msdyn_internalorganizations</span></span> |
<span data-ttu-id="1934c-131">Entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="1934c-131">Legal entities</span></span> | <span data-ttu-id="1934c-132">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="1934c-132">msdyn_internalorganizations</span></span> |
<span data-ttu-id="1934c-133">Entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="1934c-133">Legal entities</span></span> | <span data-ttu-id="1934c-134">cdm_companies</span><span class="sxs-lookup"><span data-stu-id="1934c-134">cdm_companies</span></span> | <span data-ttu-id="1934c-135">Proporciona la sincronización bidireccional de la información de la entidad jurídica (empresa).</span><span class="sxs-lookup"><span data-stu-id="1934c-135">Provides bidirectional synchronization of legal entity (company) information.</span></span>

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a><span data-ttu-id="1934c-136">Organización interna</span><span class="sxs-lookup"><span data-stu-id="1934c-136">Internal Organization</span></span>

<span data-ttu-id="1934c-137">La información de la organización interna en Dataverse se deriva de dos tablas, **unidad operativa** y **entidades jurídicas**.</span><span class="sxs-lookup"><span data-stu-id="1934c-137">Internal organization information in Dataverse comes from two tables, **operating unit** and **legal entities**.</span></span>

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]
