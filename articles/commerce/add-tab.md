---
title: Módulo de pestañas
description: En este tema se tratan los módulos de pestañas y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: c865d5e055e3fadf2dda225b49f13a163974768f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797464"
---
# <a name="tab-module"></a><span data-ttu-id="4d441-103">Módulo de pestaña</span><span class="sxs-lookup"><span data-stu-id="4d441-103">Tab module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4d441-104">En este tema se tratan los módulos de pestañas y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4d441-104">This topic covers tab modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="4d441-105">Los módulos de pestañas son módulos tipo contenedor que se utilizan para organizar la información de una página del sitio en pestañas.</span><span class="sxs-lookup"><span data-stu-id="4d441-105">Tab modules are container-like modules that are used to organize the information on a site page on tabs.</span></span> <span data-ttu-id="4d441-106">Se pueden usar en cualquier página donde la información deba presentarse en pestañas.</span><span class="sxs-lookup"><span data-stu-id="4d441-106">They can be used on any page where information must be presented on tabs.</span></span>

<span data-ttu-id="4d441-107">En cada módulo de pestañas, se pueden agregar uno o más elementos de pestaña.</span><span class="sxs-lookup"><span data-stu-id="4d441-107">In every tab module, one or more tab item modules can be added.</span></span> <span data-ttu-id="4d441-108">Cada módulo de elemento de pestaña representa una sola pestaña. En cada módulo de elemento de pestaña, se pueden agregar uno o más módulos.</span><span class="sxs-lookup"><span data-stu-id="4d441-108">Each tab item module represents a single tab. In each tab item module, one or more modules can be added.</span></span> <span data-ttu-id="4d441-109">No hay restricciones sobre los tipos de módulos que se pueden agregar a un módulo de elementos de pestaña.</span><span class="sxs-lookup"><span data-stu-id="4d441-109">There are no restrictions on the types of modules that can be added to a tab item module.</span></span>

<span data-ttu-id="4d441-110">La siguiente imagen muestra un ejemplo de un módulo de pestañas en una página de sitio.</span><span class="sxs-lookup"><span data-stu-id="4d441-110">The following image shows an example of a tab module on a site page.</span></span> <span data-ttu-id="4d441-111">En este ejemplo, está seleccionada la pestaña **Envío**.</span><span class="sxs-lookup"><span data-stu-id="4d441-111">In this example, the **Shipping** tab selected.</span></span>

![Ejemplo de un módulo de pestañas](./media/ecommerce-tab.PNG)

## <a name="tab-module-properties"></a><span data-ttu-id="4d441-113">Propiedades de los módulos de pestañas</span><span class="sxs-lookup"><span data-stu-id="4d441-113">Tab module properties</span></span>

| <span data-ttu-id="4d441-114">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="4d441-114">Property name</span></span> | <span data-ttu-id="4d441-115">Valores</span><span class="sxs-lookup"><span data-stu-id="4d441-115">Values</span></span> | <span data-ttu-id="4d441-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d441-116">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="4d441-117">Cabecera</span><span class="sxs-lookup"><span data-stu-id="4d441-117">Heading</span></span> | <span data-ttu-id="4d441-118">Texto</span><span class="sxs-lookup"><span data-stu-id="4d441-118">Text</span></span> | <span data-ttu-id="4d441-119">Esta propiedad especifica un encabezado de texto opcional para el módulo de pestañas.</span><span class="sxs-lookup"><span data-stu-id="4d441-119">This property specifies an optional text heading for the tab module.</span></span> |
| <span data-ttu-id="4d441-120">Índice de pestaña activa</span><span class="sxs-lookup"><span data-stu-id="4d441-120">Active Tab Index</span></span> | <span data-ttu-id="4d441-121">Número</span><span class="sxs-lookup"><span data-stu-id="4d441-121">Number</span></span> | <span data-ttu-id="4d441-122">Esta propiedad especifica la pestaña que debería estar activa por defecto cuando se carga una página.</span><span class="sxs-lookup"><span data-stu-id="4d441-122">This property specifies the tab that should be active by default when a page is loaded.</span></span> <span data-ttu-id="4d441-123">Si no se proporciona ningún valor, el primer elemento de la pestaña está activo de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4d441-123">If no value is provided, the first tab item is active by default.</span></span> |

## <a name="tab-item-module-properties"></a><span data-ttu-id="4d441-124">Propiedades de los módulos de elementos de pestaña</span><span class="sxs-lookup"><span data-stu-id="4d441-124">Tab item module properties</span></span>

| <span data-ttu-id="4d441-125">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="4d441-125">Property name</span></span> | <span data-ttu-id="4d441-126">Valores</span><span class="sxs-lookup"><span data-stu-id="4d441-126">Values</span></span> | <span data-ttu-id="4d441-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d441-127">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="4d441-128">Cargo</span><span class="sxs-lookup"><span data-stu-id="4d441-128">Title</span></span> | <span data-ttu-id="4d441-129">Texto</span><span class="sxs-lookup"><span data-stu-id="4d441-129">Text</span></span> | <span data-ttu-id="4d441-130">Esta propiedad especifica el texto de título del módulo de elementos de pestaña.</span><span class="sxs-lookup"><span data-stu-id="4d441-130">This property specifies the title text for the tab item module.</span></span> |

## <a name="add-a-tab-module-to-a-page"></a><span data-ttu-id="4d441-131">Agregar un módulo de pestaña a una página</span><span class="sxs-lookup"><span data-stu-id="4d441-131">Add a tab module to a page</span></span>

<span data-ttu-id="4d441-132">Para agregar un módulo de pestaña a una página y establecer las propiedades, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="4d441-132">To add a tab module to a page and set the properties, follow these steps.</span></span>

1. <span data-ttu-id="4d441-133">Use la plantilla de marketing de Fabrikam (o cualquier plantilla que no tenga restricciones) para crear una nueva página con el nombre **Página de directivas de tienda**.</span><span class="sxs-lookup"><span data-stu-id="4d441-133">Use the Fabrikam marketing template (or any template that has no restrictions) to create a new page that is named **Store policies page**.</span></span>
1. <span data-ttu-id="4d441-134">En el espacio **Principal** de la **página predeterminada**, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="4d441-134">In the **Main** slot of the **Default page**, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="4d441-135">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4d441-135">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="4d441-136">En el espacio **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="4d441-136">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="4d441-137">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Pestaña** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4d441-137">In the **Add Module** dialog box, select the **Tab** module, and then select **OK**.</span></span>
1. <span data-ttu-id="4d441-138">En el panel de propiedades del módulo de pestañas, seleccione **Encabezado** al lado del símbolo de lápiz.</span><span class="sxs-lookup"><span data-stu-id="4d441-138">In the property pane of the tab module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="4d441-139">En el cuadro de diálogo **Encabezado**, en **Texto de encabezado**, introduzca el texto del encabezado (por ejemplo, **Directivas**).</span><span class="sxs-lookup"><span data-stu-id="4d441-139">In the **Heading** dialog box, under **Heading Text**, enter heading text (for example, **Policies**).</span></span> <span data-ttu-id="4d441-140">A continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4d441-140">Then select **OK**.</span></span>
1. <span data-ttu-id="4d441-141">En el espacio **Pestaña**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="4d441-141">In the **Tab** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="4d441-142">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Elemento de pestaña** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4d441-142">In the **Add Module** dialog box, select the **Tab item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="4d441-143">En el panel de propiedades del módulo de elementos de pestaña, en **Título**, introduzca el texto del título (por ejemplo, **Entrega**).</span><span class="sxs-lookup"><span data-stu-id="4d441-143">In the property pane of the tab item module, under **Title**, enter title text (for example, **Delivery**).</span></span>
1. <span data-ttu-id="4d441-144">En el espacio **Elemento de pestaña**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="4d441-144">In the **Tab item** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="4d441-145">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Bloque de texto** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4d441-145">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span>
1. <span data-ttu-id="4d441-146">En el panel de propiedades del módulo de bloque de texto, en **Texto enriquecido**, introduzca un párrafo de texto.</span><span class="sxs-lookup"><span data-stu-id="4d441-146">In the property pane of the text block module, under **Rich text**, enter a paragraph of text.</span></span>
1. <span data-ttu-id="4d441-147">En el espacio **Pestaña**, agregue algunos módulos de elementos de pestaña que tengan títulos.</span><span class="sxs-lookup"><span data-stu-id="4d441-147">In the **Tab** slot, add a few more tab item modules that have titles.</span></span> <span data-ttu-id="4d441-148">En cada módulo de elementos de pestaña, agregue un módulo de bloque de texto que tenga contenido.</span><span class="sxs-lookup"><span data-stu-id="4d441-148">In each tab item module, add a text block module that has content.</span></span>
1. <span data-ttu-id="4d441-149">Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.</span><span class="sxs-lookup"><span data-stu-id="4d441-149">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="4d441-150">La página mostrará un módulo de pestañas que contiene módulos de elementos de pestaña que tienen el contenido que agregó.</span><span class="sxs-lookup"><span data-stu-id="4d441-150">The page will show a tab module that contains tab item modules have the content that you added.</span></span>
1. <span data-ttu-id="4d441-151">Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="4d441-151">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4d441-152">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="4d441-152">Additional resources</span></span>

[<span data-ttu-id="4d441-153">Visión general de la biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="4d441-153">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="4d441-154">Módulo de contenedor</span><span class="sxs-lookup"><span data-stu-id="4d441-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="4d441-155">Módulo de acordeón</span><span class="sxs-lookup"><span data-stu-id="4d441-155">Accordion module</span></span>](add-accordion.md)

[<span data-ttu-id="4d441-156">Módulo de bloque de texto</span><span class="sxs-lookup"><span data-stu-id="4d441-156">Text block module</span></span>](add-content-rich-block.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]