---
title: Módulo de acordeón
description: En este tema se tratan los módulos de acordeon y se describe cómo agregarlos a las páginas de sitios en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.openlocfilehash: 2bb18539f610e5af05f8d9a20a0ba9f34db5c94f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415453"
---
# <a name="accordion-module"></a><span data-ttu-id="9e8c2-103">Módulo de acordeón</span><span class="sxs-lookup"><span data-stu-id="9e8c2-103">Accordion module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9e8c2-104">En este tema se tratan los módulos de acordeon y se describe cómo agregarlos a las páginas de sitios en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-104">This topic covers accordion modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9e8c2-105">Información general</span><span class="sxs-lookup"><span data-stu-id="9e8c2-105">Overview</span></span>

<span data-ttu-id="9e8c2-106">Los módulos de acordeón son módulos en forma de contenedor que se utilizan para organizar la información o los módulos en una página al proporcionar una capacidad contraible tipo cajón.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-106">Accordion modules are container-like modules that are used to organize the information or modules on a page by providing a collapsible drawer-like capability.</span></span> <span data-ttu-id="9e8c2-107">Se puede usar un módulo de acordeón en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-107">An accordion module can be used on any page.</span></span>

<span data-ttu-id="9e8c2-108">Dentro de cada módulo de acordeón, se pueden agregar uno o más módulos de elementos de acordeón.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-108">Inside every accordion module, one or more accordion item modules can be added.</span></span> <span data-ttu-id="9e8c2-109">Cada módulo de elementos de acordeón representa un cajón contraible.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-109">Each accordion item module represents a collapsible drawer.</span></span> <span data-ttu-id="9e8c2-110">Dentro de cada módulo de elementos de acordeón, se pueden agregar uno o más módulos.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-110">Inside every accordion item module, one or more modules can be added.</span></span> <span data-ttu-id="9e8c2-111">No hay restricciones sobre los tipos de módulos que se pueden agregar a un módulo de elementos de acordeón.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-111">There are no restrictions on the types of modules that can be added to an accordion item module.</span></span>

<span data-ttu-id="9e8c2-112">La siguiente imagen muestra un ejemplo de un módulo de acordeón que se utiliza para organizar la información en la página de preguntas frecuentes (FAQ) de una tienda.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-112">The following image shows an example of an accordion module that is used to organize information on a store's frequently asked questions (FAQ) page.</span></span>

![Ejemplo de un módulo de acordeón](./media/ecommerce-accordion.PNG)

## <a name="accordion-module-properties"></a><span data-ttu-id="9e8c2-114">Propiedades de módulo de acordeón</span><span class="sxs-lookup"><span data-stu-id="9e8c2-114">Accordion module properties</span></span>

| <span data-ttu-id="9e8c2-115">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="9e8c2-115">Property name</span></span> | <span data-ttu-id="9e8c2-116">Valores</span><span class="sxs-lookup"><span data-stu-id="9e8c2-116">Values</span></span> | <span data-ttu-id="9e8c2-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e8c2-117">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="9e8c2-118">Cabecera</span><span class="sxs-lookup"><span data-stu-id="9e8c2-118">Heading</span></span> | <span data-ttu-id="9e8c2-119">Texto</span><span class="sxs-lookup"><span data-stu-id="9e8c2-119">Text</span></span> | <span data-ttu-id="9e8c2-120">Esta propiedad especifica un encabezado de texto opcional para el módulo de acordeón.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-120">This property specifies an optional text heading for the accordion module.</span></span> |
| <span data-ttu-id="9e8c2-121">Ampliar todo</span><span class="sxs-lookup"><span data-stu-id="9e8c2-121">Expand All</span></span> | <span data-ttu-id="9e8c2-122">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="9e8c2-122">**True** or **False**</span></span> | <span data-ttu-id="9e8c2-123">Si el valor se establece en **Verdadero**, la funcionalidad de expandir/contraer está activada, de modo que todos los elementos del módulo de acordeón se pueden expandir y contraer.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-123">If the value is set to **True**, expand/collapse functionality is turned on, so that all items in the accordion module can be expanded and collapsed.</span></span> |
| <span data-ttu-id="9e8c2-124">Estilo de interacción</span><span class="sxs-lookup"><span data-stu-id="9e8c2-124">Interaction Style</span></span> | <span data-ttu-id="9e8c2-125">**Independiente** o **Expandir solo un elemento**</span><span class="sxs-lookup"><span data-stu-id="9e8c2-125">**Independent** or **Expand one item only**</span></span> | <span data-ttu-id="9e8c2-126">Esta propiedad define el estilo de interacción para los elementos de acordeón.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-126">This property defines the style of interaction for accordion items.</span></span> <span data-ttu-id="9e8c2-127">Si el valor se establece en **Independiente**, cada elemento de acordeón se puede expandir o contraer de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-127">If the value is set to **Independent**, each accordion item can be expanded or collapsed independently.</span></span> <span data-ttu-id="9e8c2-128">Si el valor se establece en **Expandir solo un elemento**, solo se puede expandir un elemento a la vez.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-128">If the value is set to **Expand one item only**, only one item can be expanded at a time.</span></span> <span data-ttu-id="9e8c2-129">A medida que se expanden los elementos, los elementos previamente expandidos se contraen.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-129">As items are expanded, previously expanded items are collapsed.</span></span> |

## <a name="accordion-item-module-properties"></a><span data-ttu-id="9e8c2-130">Propiedades de módulo de elementos de acordeón</span><span class="sxs-lookup"><span data-stu-id="9e8c2-130">Accordion item module properties</span></span>

| <span data-ttu-id="9e8c2-131">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="9e8c2-131">Property name</span></span> | <span data-ttu-id="9e8c2-132">Valores</span><span class="sxs-lookup"><span data-stu-id="9e8c2-132">Values</span></span> | <span data-ttu-id="9e8c2-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e8c2-133">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="9e8c2-134">Cargo</span><span class="sxs-lookup"><span data-stu-id="9e8c2-134">Title</span></span> | <span data-ttu-id="9e8c2-135">Texto</span><span class="sxs-lookup"><span data-stu-id="9e8c2-135">Text</span></span> | <span data-ttu-id="9e8c2-136">Esta propiedad especifica el texto de título del módulo de elementos de acordeón.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-136">This property specifies the title text for the accordion item module.</span></span> <span data-ttu-id="9e8c2-137">Al seleccionar la región del título, los usuarios pueden expandir o contraer la sección.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-137">By selecting the title region, users can expand or collapse the section.</span></span> |
| <span data-ttu-id="9e8c2-138">Expandir de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="9e8c2-138">Expand by default</span></span> | <span data-ttu-id="9e8c2-139">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="9e8c2-139">**True** or **False**</span></span> | <span data-ttu-id="9e8c2-140">Si el valor se establece en **Verdadero**, el elemento de acordeón se expande de manera predeterminada cuando se carga la página.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-140">If the value is set to **True**, the accordion item is expanded by default when the page is loaded.</span></span> |

## <a name="add-an-accordion-module-to-a-faq-page"></a><span data-ttu-id="9e8c2-141">Agregar un módulo de acordeón a una página de preguntas frecuentes</span><span class="sxs-lookup"><span data-stu-id="9e8c2-141">Add an accordion module to a FAQ page</span></span>

<span data-ttu-id="9e8c2-142">Para agregar un módulo de acordeón a una página de preguntas frecuentes y establecer las propiedades en el generador de sitios, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-142">To add an accordion module to a FAQ page and set its properties in site builder, follow these steps.</span></span>

1. <span data-ttu-id="9e8c2-143">Vaya a **Páginas**, y use la plantilla de marketing de Fabrikam (o cualquier plantilla que no tenga restricciones) para crear una nueva página con el nombre **Preguntas frecuentes de tienda**.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-143">Go to **Pages**, and use the Fabrikam marketing template (or any template that has no restrictions) to create a new page that is named **Store FAQ**.</span></span>
1. <span data-ttu-id="9e8c2-144">En el espacio **Principal** de la **página predeterminada**, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-144">In the **Main** slot of the **Default page**, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="9e8c2-145">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-145">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="9e8c2-146">En el espacio **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-146">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="9e8c2-147">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Acordeón** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-147">In the **Add Module** dialog box, select the **Accordion** module, and then select **OK**.</span></span>
1. <span data-ttu-id="9e8c2-148">En el panel de propiedades del módulo de acordeón, seleccione **Encabezado** al lado del símbolo de lápiz.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-148">In the property pane of the accordion module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="9e8c2-149">En el cuadro de diálogo **Encabezado**, en **Texto de encabezado**, introduzca **Preguntas frecuentes**.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-149">In the **Heading** dialog box, under **Heading Text**, enter **Frequently asked questions**.</span></span> <span data-ttu-id="9e8c2-150">A continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-150">Then select **OK**.</span></span>
1. <span data-ttu-id="9e8c2-151">En el panel de propiedades del módulo de acordeón, seleccione la casilla **Mostrar Expandir todo** y luego, en el campo **Estilo de interacción**, seleccione **Independiente**.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-151">In the property pane of the accordion module, select the **Show expand all** check box, and then, in the **Interaction style** field, select **Independent**.</span></span>
1. <span data-ttu-id="9e8c2-152">En el espacio **Acordeón**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-152">In the **Accordion** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="9e8c2-153">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Elemento de acordeón** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-153">In the **Add Module** dialog box, select the **Accordion item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="9e8c2-154">En el panel de propiedades del módulo de elementos de acordeón, en **Título**, introduzca el texto del título (por ejemplo, **¿Cómo funcionan las devoluciones?**).</span><span class="sxs-lookup"><span data-stu-id="9e8c2-154">In the property pane of the accordion item module, under **Title**, enter title text (for example, **How do returns work?**).</span></span>
1. <span data-ttu-id="9e8c2-155">En el espacio **Elemento de acordeón**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-155">In the **Accordion item** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="9e8c2-156">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Bloque de texto** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-156">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span>
1. <span data-ttu-id="9e8c2-157">En el panel de propiedades del módulo de bloque de texto, introduzca un párrafo de texto (por ejemplo, **Las devoluciones deben procesarse a través del centro de atención telefónica. Póngase en contacto con 1-800-FABRIKAM para devoluciones. Los productos tienen una política de devolución de 30 días. Las devoluciones deben iniciarse dentro de este plazo.**)</span><span class="sxs-lookup"><span data-stu-id="9e8c2-157">In the property pane of the text block module, enter a paragraph of text (for example, **Returns must be processed via the call center. Contact 1-800-FABRIKAM for returns. Products have a 30-day return policy. Returns must be initiated within this time frame.**).</span></span>
1. <span data-ttu-id="9e8c2-158">En el espacio **Acordeón**, agregue algunos módulos de elementos de acordeón más.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-158">In the **Accordion** slot, add a few more accordion item modules.</span></span> <span data-ttu-id="9e8c2-159">En cada módulo de elementos de acordeón, agregue un módulo de bloque de texto que tenga contenido.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-159">In each accordion item module, add a text block module that has content.</span></span>
1. <span data-ttu-id="9e8c2-160">Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-160">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="9e8c2-161">La página mostrará un módulo de acordeón que tiene el contenido que agregó.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-161">The page will show an accordion module that has the content that you added.</span></span>
1. <span data-ttu-id="9e8c2-162">Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="9e8c2-162">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9e8c2-163">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9e8c2-163">Additional resources</span></span>

[<span data-ttu-id="9e8c2-164">Visión general de la biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="9e8c2-164">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="9e8c2-165">Módulo de contenedor</span><span class="sxs-lookup"><span data-stu-id="9e8c2-165">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="9e8c2-166">Módulo de pestaña</span><span class="sxs-lookup"><span data-stu-id="9e8c2-166">Tab module</span></span>](add-tab.md)

[<span data-ttu-id="9e8c2-167">Módulo de bloque de texto</span><span class="sxs-lookup"><span data-stu-id="9e8c2-167">Text block module</span></span>](add-content-rich-block.md)
