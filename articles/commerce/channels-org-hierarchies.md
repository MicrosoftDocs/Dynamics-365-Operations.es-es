---
title: Configurar jerarquías organizativas
description: En este tema se describe cómo configurar jerarquías organizativas en Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: b887616ef29396ba99ca0c7428ab89df01b3008c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4997784"
---
# <a name="set-up-organization-hierarchies"></a><span data-ttu-id="41d3e-103">Configurar jerarquías organizativas</span><span class="sxs-lookup"><span data-stu-id="41d3e-103">Set up organization hierarchies</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="41d3e-104">En este tema se describe cómo configurar jerarquías organizativas en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="41d3e-104">This topic describes how to set up organization hierarchies in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="41d3e-105">Información general</span><span class="sxs-lookup"><span data-stu-id="41d3e-105">Overview</span></span>

<span data-ttu-id="41d3e-106">Antes de crear canales, debe asegurarse de configurar sus jerarquías organizativas.</span><span class="sxs-lookup"><span data-stu-id="41d3e-106">Before creating channels, you'll want to ensure you have set up your organization hierarchies.</span></span>

<span data-ttu-id="41d3e-107">Puede usar jerarquías organizativas para ver e informar de su negocio desde diferentes perspectivas.</span><span class="sxs-lookup"><span data-stu-id="41d3e-107">You can use organization hierarchies to view and report on your business from various perspectives.</span></span> <span data-ttu-id="41d3e-108">Por ejemplo, puede configurar una jerarquía para informes estatutarios, legales o de impuestos.</span><span class="sxs-lookup"><span data-stu-id="41d3e-108">For example, you can set up one hierarchy for tax, legal, or statutory reporting.</span></span> <span data-ttu-id="41d3e-109">A continuación, puede configurar otra jerarquía para elaborar información financiera que no sea legalmente necesaria pero que se use para informes internos.</span><span class="sxs-lookup"><span data-stu-id="41d3e-109">You can then set up another hierarchy to report financial information that is not legally required, but that is used for internal reporting.</span></span>

<span data-ttu-id="41d3e-110">Antes de crear una jerarquía organizativa debe crear organizaciones.</span><span class="sxs-lookup"><span data-stu-id="41d3e-110">Before you create an organization hierarchy, you must create organizations.</span></span> <span data-ttu-id="41d3e-111">Para obtener más información, consulte [Crear entidades jurídicas](channels-legal-entities.md) o [Crear unidades operativas](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="41d3e-111">For more information, see [Create legal entities](channels-legal-entities.md) or [Create operating units](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json).</span></span>


<span data-ttu-id="41d3e-112">Para obtener más información, consulte los siguientes temas.</span><span class="sxs-lookup"><span data-stu-id="41d3e-112">For more information, see the following topics.</span></span>
- [<span data-ttu-id="41d3e-113">Visión general de las organizaciones y las jerarquías organizativas</span><span class="sxs-lookup"><span data-stu-id="41d3e-113">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="41d3e-114">Planificar su jerarquía organizativa</span><span class="sxs-lookup"><span data-stu-id="41d3e-114">Plan your organization hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="41d3e-115">Crear una jerarquía organizativa</span><span class="sxs-lookup"><span data-stu-id="41d3e-115">Create an organization hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/tasks/create-organization-hierarchy.md?toc=/dynamics365/commerce/toc.json)

## <a name="create-an-organizational-hierarchy"></a><span data-ttu-id="41d3e-116">Crear una jerarquía organizativa</span><span class="sxs-lookup"><span data-stu-id="41d3e-116">Create an organizational hierarchy</span></span>

<span data-ttu-id="41d3e-117">Para crear una jerarquía organizativa, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="41d3e-117">To create an organizational hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="41d3e-118">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Jerarquía organizativa**.</span><span class="sxs-lookup"><span data-stu-id="41d3e-118">In the navigation pane, go to **Modules \> Retail and commerce \> Channel Setup \> Organization hierarchies**.</span></span>
1. <span data-ttu-id="41d3e-119">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="41d3e-119">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="41d3e-120">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="41d3e-120">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="41d3e-121">En la sección **Propósito**, seleccione **Asignar propósito**.</span><span class="sxs-lookup"><span data-stu-id="41d3e-121">In the **Purpose** section, select **Assign purpose**.</span></span>
1. <span data-ttu-id="41d3e-122">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="41d3e-122">In the list, find and select the desired record.</span></span> <span data-ttu-id="41d3e-123">Seleccione un propósito para asignar a su jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="41d3e-123">Select a purpose to assign to your organization hierarchy.</span></span>
1. <span data-ttu-id="41d3e-124">En la sección **Jerarquías asignadas**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="41d3e-124">In the **Assigned hierarchies** section, select **Add**.</span></span>
1. <span data-ttu-id="41d3e-125">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="41d3e-125">In the list, mark the selected row.</span></span> <span data-ttu-id="41d3e-126">Busque la jerarquía que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="41d3e-126">Find the hierarchy you just created.</span></span>
1. <span data-ttu-id="41d3e-127">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="41d3e-127">Select **OK**.</span></span>

<span data-ttu-id="41d3e-128">La siguiente imagen muestra un ejemplo de jerarquía organizativa creada para un conjunto de tiendas ficticio llamado "Adventure Works".</span><span class="sxs-lookup"><span data-stu-id="41d3e-128">The following image shows an example organizational hierarchy created for a fictitious "Adventure Works" set of stores.</span></span>

![Ejemplo de jerarquía organizativa](media/organizational-hierarchies.png)

### <a name="add-organizations-to-a-hierarchy"></a><span data-ttu-id="41d3e-130">Agregar organizaciones a una jerarquía</span><span class="sxs-lookup"><span data-stu-id="41d3e-130">Add organizations to a hierarchy</span></span>

<span data-ttu-id="41d3e-131">Para agregar organizaciones a una jerarquía, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="41d3e-131">To add organizations to a hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="41d3e-132">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="41d3e-132">In the list, find and select the desired record.</span></span> <span data-ttu-id="41d3e-133">Seleccione su jerarquía.</span><span class="sxs-lookup"><span data-stu-id="41d3e-133">Select your hierarchy.</span></span>
1. <span data-ttu-id="41d3e-134">En el panel de acciones, seleccione **Ver**.</span><span class="sxs-lookup"><span data-stu-id="41d3e-134">On the action pane, select **View**.</span></span>
1. <span data-ttu-id="41d3e-135">Agregue organizaciones según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="41d3e-135">Add organizations, as necessary.</span></span>
1. <span data-ttu-id="41d3e-136">Para agregar una organización, seleccione **Editar** y, a continuación, seleccione **Insertar**.</span><span class="sxs-lookup"><span data-stu-id="41d3e-136">To add an organization, select **Edit** and then select **Insert**.</span></span> <span data-ttu-id="41d3e-137">Cuando haya terminado de realizar cambios, puede guardar un borrador o publicar los cambios.</span><span class="sxs-lookup"><span data-stu-id="41d3e-137">When you are done making changes you can save a draft and publish the changes.</span></span>

<span data-ttu-id="41d3e-138">En la siguiente imagen se muestra una entidad jurídica agregada en la raíz de la jerarquía con cuatro centros de coste agregados para los canales "Centro comercial", "Tienda de ofertas", "En línea" y "Centro de llamadas".</span><span class="sxs-lookup"><span data-stu-id="41d3e-138">The following image shows a legal entity added at the hierarchy root with four cost centers added for "Mall", "Outlet", "Online" and "Call Center" channels.</span></span> <span data-ttu-id="41d3e-139">Se pueden agregar a cada uno de ellos varios canales minoristas, de centro de llamadas y en línea.</span><span class="sxs-lookup"><span data-stu-id="41d3e-139">Various retail, call center and online channels can then be added to each.</span></span>

![Ejemplo de diseñador de jerarquías](media/hierarchy-designer.png)

## <a name="additional-resources"></a><span data-ttu-id="41d3e-141">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="41d3e-141">Additional resources</span></span>

[<span data-ttu-id="41d3e-142">Visión general de las organizaciones y las jerarquías organizativas</span><span class="sxs-lookup"><span data-stu-id="41d3e-142">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="41d3e-143">Planificación de su jerarquía organizativa</span><span class="sxs-lookup"><span data-stu-id="41d3e-143">Plan your organizational hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="41d3e-144">Crear entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="41d3e-144">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="41d3e-145">Crear unidades operativas</span><span class="sxs-lookup"><span data-stu-id="41d3e-145">Create operating units</span></span>](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="41d3e-146">Resumen de canales</span><span class="sxs-lookup"><span data-stu-id="41d3e-146">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="41d3e-147">Requisitos previos de configuración de canales</span><span class="sxs-lookup"><span data-stu-id="41d3e-147">Channel setup prerequisites</span></span>](channels-prerequisites.md)
