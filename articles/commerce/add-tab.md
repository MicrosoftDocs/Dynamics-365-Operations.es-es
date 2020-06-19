---
title: Módulo de pestañas
description: En este tema se tratan los módulos de pestañas y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 60af9b74f7e647e83229e352a03c09d63d0c7902
ms.sourcegitcommit: 2683aacb426bfb3b541637edf1f8ec2d6cb5a745
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "3417378"
---
# <a name="tab-module"></a><span data-ttu-id="7067c-103">Módulo de pestañas</span><span class="sxs-lookup"><span data-stu-id="7067c-103">Tab module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="7067c-104">En este tema se tratan los módulos de pestañas y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7067c-104">This topic covers tab modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="7067c-105">Información general</span><span class="sxs-lookup"><span data-stu-id="7067c-105">Overview</span></span>

<span data-ttu-id="7067c-106">Los módulos de pestañas son módulos tipo contenedor que se utilizan para organizar la información de una página del sitio en pestañas.</span><span class="sxs-lookup"><span data-stu-id="7067c-106">Tab modules are container-like modules that are used to organize the information on a site page on tabs.</span></span> <span data-ttu-id="7067c-107">Se pueden usar en cualquier página donde la información deba presentarse en pestañas.</span><span class="sxs-lookup"><span data-stu-id="7067c-107">They can be used on any page where information must be presented on tabs.</span></span>

<span data-ttu-id="7067c-108">En cada módulo de pestañas, se pueden agregar uno o más elementos de pestaña.</span><span class="sxs-lookup"><span data-stu-id="7067c-108">In every tab module, one or more tab item modules can be added.</span></span> <span data-ttu-id="7067c-109">Cada módulo de elemento de pestaña representa una sola pestaña. En cada módulo de elemento de pestaña, se pueden agregar uno o más módulos.</span><span class="sxs-lookup"><span data-stu-id="7067c-109">Each tab item module represents a single tab. In each tab item module, one or more modules can be added.</span></span> <span data-ttu-id="7067c-110">No hay restricciones sobre los tipos de módulos que se pueden agregar a un módulo de elementos de pestaña.</span><span class="sxs-lookup"><span data-stu-id="7067c-110">There are no restrictions on the types of modules that can be added to a tab item module.</span></span>

<span data-ttu-id="7067c-111">La siguiente imagen muestra un ejemplo de un módulo de pestañas en una página de sitio.</span><span class="sxs-lookup"><span data-stu-id="7067c-111">The following image shows an example of a tab module on a site page.</span></span> <span data-ttu-id="7067c-112">En este ejemplo, está seleccionada la pestaña **Envío**.</span><span class="sxs-lookup"><span data-stu-id="7067c-112">In this example, the **Shipping** tab selected.</span></span>

![Ejemplo de un módulo de pestañas](./media/ecommerce-tab.PNG)

## <a name="tab-module-properties"></a><span data-ttu-id="7067c-114">Propiedades de los módulos de pestañas</span><span class="sxs-lookup"><span data-stu-id="7067c-114">Tab module properties</span></span>

| <span data-ttu-id="7067c-115">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="7067c-115">Property name</span></span> | <span data-ttu-id="7067c-116">Valores</span><span class="sxs-lookup"><span data-stu-id="7067c-116">Values</span></span> | <span data-ttu-id="7067c-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="7067c-117">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="7067c-118">Cabecera</span><span class="sxs-lookup"><span data-stu-id="7067c-118">Heading</span></span> | <span data-ttu-id="7067c-119">Texto</span><span class="sxs-lookup"><span data-stu-id="7067c-119">Text</span></span> | <span data-ttu-id="7067c-120">Esta propiedad especifica un encabezado de texto opcional para el módulo de pestañas.</span><span class="sxs-lookup"><span data-stu-id="7067c-120">This property specifies an optional text heading for the tab module.</span></span> |
| <span data-ttu-id="7067c-121">Índice de pestaña activa</span><span class="sxs-lookup"><span data-stu-id="7067c-121">Active Tab Index</span></span> | <span data-ttu-id="7067c-122">Número</span><span class="sxs-lookup"><span data-stu-id="7067c-122">Number</span></span> | <span data-ttu-id="7067c-123">Esta propiedad especifica la pestaña que debería estar activa por defecto cuando se carga una página.</span><span class="sxs-lookup"><span data-stu-id="7067c-123">This property specifies the tab that should be active by default when a page is loaded.</span></span> <span data-ttu-id="7067c-124">Si no se proporciona ningún valor, el primer elemento de la pestaña está activo de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7067c-124">If no value is provided, the first tab item is active by default.</span></span> |

## <a name="tab-item-module-properties"></a><span data-ttu-id="7067c-125">Propiedades de los módulos de elementos de pestaña</span><span class="sxs-lookup"><span data-stu-id="7067c-125">Tab item module properties</span></span>

| <span data-ttu-id="7067c-126">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="7067c-126">Property name</span></span> | <span data-ttu-id="7067c-127">Valores</span><span class="sxs-lookup"><span data-stu-id="7067c-127">Values</span></span> | <span data-ttu-id="7067c-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="7067c-128">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="7067c-129">Cargo</span><span class="sxs-lookup"><span data-stu-id="7067c-129">Title</span></span> | <span data-ttu-id="7067c-130">Texto</span><span class="sxs-lookup"><span data-stu-id="7067c-130">Text</span></span> | <span data-ttu-id="7067c-131">Esta propiedad especifica el texto de título del módulo de elementos de pestaña.</span><span class="sxs-lookup"><span data-stu-id="7067c-131">This property specifies the title text for the tab item module.</span></span> |

## <a name="add-a-tab-module-to-a-page"></a><span data-ttu-id="7067c-132">Agregar un módulo de pestaña a una página</span><span class="sxs-lookup"><span data-stu-id="7067c-132">Add a tab module to a page</span></span>

<span data-ttu-id="7067c-133">Para agregar un módulo de pestaña a una página y establecer las propiedades, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="7067c-133">To add a tab module to a page and set the properties, follow these steps.</span></span>

1. <span data-ttu-id="7067c-134">Use la plantilla de marketing de Fabrikam (o cualquier plantilla que no tenga restricciones) para crear una nueva página con el nombre **Página de directivas de tienda**.</span><span class="sxs-lookup"><span data-stu-id="7067c-134">Use the Fabrikam marketing template (or any template that has no restrictions) to create a new page that is named **Store policies page**.</span></span>
1. <span data-ttu-id="7067c-135">En el espacio **Principal** de la **página predeterminada**, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="7067c-135">In the **Main** slot of the **Default page**, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="7067c-136">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7067c-136">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="7067c-137">En el espacio **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="7067c-137">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="7067c-138">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Pestaña** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7067c-138">In the **Add Module** dialog box, select the **Tab** module, and then select **OK**.</span></span>
1. <span data-ttu-id="7067c-139">En el panel de propiedades del módulo de pestañas, seleccione **Encabezado** al lado del símbolo de lápiz.</span><span class="sxs-lookup"><span data-stu-id="7067c-139">In the property pane of the tab module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="7067c-140">En el cuadro de diálogo **Encabezado**, en **Texto de encabezado**, introduzca el texto del encabezado (por ejemplo, **Directivas**).</span><span class="sxs-lookup"><span data-stu-id="7067c-140">In the **Heading** dialog box, under **Heading Text**, enter heading text (for example, **Policies**).</span></span> <span data-ttu-id="7067c-141">A continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7067c-141">Then select **OK**.</span></span>
1. <span data-ttu-id="7067c-142">En el espacio **Pestaña**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="7067c-142">In the **Tab** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="7067c-143">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Elemento de pestaña** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7067c-143">In the **Add Module** dialog box, select the **Tab item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="7067c-144">En el panel de propiedades del módulo de elementos de pestaña, en **Título**, introduzca el texto del título (por ejemplo, **Entrega**).</span><span class="sxs-lookup"><span data-stu-id="7067c-144">In the property pane of the tab item module, under **Title**, enter title text (for example, **Delivery**).</span></span>
1. <span data-ttu-id="7067c-145">En el espacio **Elemento de pestaña**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="7067c-145">In the **Tab item** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="7067c-146">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Bloque de texto** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7067c-146">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span>
1. <span data-ttu-id="7067c-147">En el panel de propiedades del módulo de bloque de texto, en **Texto enriquecido**, introduzca un párrafo de texto.</span><span class="sxs-lookup"><span data-stu-id="7067c-147">In the property pane of the text block module, under **Rich text**, enter a paragraph of text.</span></span>
1. <span data-ttu-id="7067c-148">En el espacio **Pestaña**, agregue algunos módulos de elementos de pestaña que tengan títulos.</span><span class="sxs-lookup"><span data-stu-id="7067c-148">In the **Tab** slot, add a few more tab item modules that have titles.</span></span> <span data-ttu-id="7067c-149">En cada módulo de elementos de pestaña, agregue un módulo de bloque de texto que tenga contenido.</span><span class="sxs-lookup"><span data-stu-id="7067c-149">In each tab item module, add a text block module that has content.</span></span>
1. <span data-ttu-id="7067c-150">Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.</span><span class="sxs-lookup"><span data-stu-id="7067c-150">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="7067c-151">La página mostrará un módulo de pestañas que contiene módulos de elementos de pestaña que tienen el contenido que agregó.</span><span class="sxs-lookup"><span data-stu-id="7067c-151">The page will show a tab module that contains tab item modules have the content that you added.</span></span>
1. <span data-ttu-id="7067c-152">Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="7067c-152">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7067c-153">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="7067c-153">Additional resources</span></span>

[<span data-ttu-id="7067c-154">Visión general del kit de inicio</span><span class="sxs-lookup"><span data-stu-id="7067c-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="7067c-155">Módulo Contenedor</span><span class="sxs-lookup"><span data-stu-id="7067c-155">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="7067c-156">Módulo de acordeón</span><span class="sxs-lookup"><span data-stu-id="7067c-156">Accordion module</span></span>](add-accordion.md)

[<span data-ttu-id="7067c-157">Módulo de bloque de texto</span><span class="sxs-lookup"><span data-stu-id="7067c-157">Text block module</span></span>](add-content-rich-block.md)
