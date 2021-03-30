---
title: Módulo de bloque de texto
description: En este tema se tratan los módulos de bloque de texto y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3926f23e4e762a49ef94ef0c8f3291e7e9a4a6a2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206400"
---
# <a name="text-block-module"></a><span data-ttu-id="1524b-103">Módulo de bloque de texto</span><span class="sxs-lookup"><span data-stu-id="1524b-103">Text block module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1524b-104">En este tema se tratan los módulos de bloque de texto y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1524b-104">This topic covers text block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="1524b-105">Un módulo de bloque de texto es un módulo que se utiliza para agregar contenido textual.</span><span class="sxs-lookup"><span data-stu-id="1524b-105">A text block module is a module that is used to add textual content.</span></span> <span data-ttu-id="1524b-106">Este contenido puede ser informativo o promocional.</span><span class="sxs-lookup"><span data-stu-id="1524b-106">This content can be informational or promotional.</span></span>

<span data-ttu-id="1524b-107">Los módulos de bloque de texto se controlan con datos desde el sistema de gestión de contenidos (CMS) y se pueden colocar en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="1524b-107">Text block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="1524b-108">Son módulos independientes que no dependen del contexto de página o de cualquier otro módulo.</span><span class="sxs-lookup"><span data-stu-id="1524b-108">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-text-block-modules-in-e-commerce"></a><span data-ttu-id="1524b-109">Ejemplos de módulos de bloque de texto en comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="1524b-109">Examples of text block modules in e-Commerce</span></span>

<span data-ttu-id="1524b-110">Los módulos de bloque de texto se pueden utilizar de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="1524b-110">Text block modules can be used in the following ways:</span></span>

* <span data-ttu-id="1524b-111">Para mostrar características de producto en una página de detalles de productos.</span><span class="sxs-lookup"><span data-stu-id="1524b-111">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="1524b-112">Para finalidad informativa en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="1524b-112">For informational purposes on any page.</span></span> <span data-ttu-id="1524b-113">Por ejemplo, pueden explicar los beneficios de programas de fidelización, describir las directivas de envío y devolución, responder a preguntas más frecuentes o proporcionar contenido de “acerca de nosotros”.</span><span class="sxs-lookup"><span data-stu-id="1524b-113">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="1524b-114">Para agregar mensajes personalizados en una página de detalles de productos.</span><span class="sxs-lookup"><span data-stu-id="1524b-114">To add custom messages on a product details page.</span></span> <span data-ttu-id="1524b-115">(por ejemplo, “Envío gratuito para pedidos superiores a 50 €").</span><span class="sxs-lookup"><span data-stu-id="1524b-115">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="1524b-116">Para declinaciones de responsabilidad y detalles de contacto sobre páginas de detalles de productos, páginas de finalización de compra y otras páginas (por ejemplo, "Los envíos y las directivas están sujetos a las directivas de la tienda”).</span><span class="sxs-lookup"><span data-stu-id="1524b-116">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

<span data-ttu-id="1524b-117">La siguiente imagen muestra un ejemplo de un módulo de bloque de texto utilizado en una página principal.</span><span class="sxs-lookup"><span data-stu-id="1524b-117">The following image shows an example of a text block module that is used on a home page.</span></span>

![Ejemplo de un módulo de bloque de texto](./media/ecommerce-textblock.PNG)

## <a name="text-block-module-properties"></a><span data-ttu-id="1524b-119">Propiedades de módulo de bloque de texto</span><span class="sxs-lookup"><span data-stu-id="1524b-119">Text block module properties</span></span>

| <span data-ttu-id="1524b-120">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="1524b-120">Property name</span></span>     | <span data-ttu-id="1524b-121">Valor</span><span class="sxs-lookup"><span data-stu-id="1524b-121">Value</span></span>                                            | <span data-ttu-id="1524b-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="1524b-122">Description</span></span> |
|-------------------|--------------------------------------------------|-------------|
| <span data-ttu-id="1524b-123">Texto enriquecido</span><span class="sxs-lookup"><span data-stu-id="1524b-123">Rich text</span></span>         | <span data-ttu-id="1524b-124">Texto enriquecido</span><span class="sxs-lookup"><span data-stu-id="1524b-124">Rich text</span></span>                                        | <span data-ttu-id="1524b-125">Texto de párrafo.</span><span class="sxs-lookup"><span data-stu-id="1524b-125">Paragraph text.</span></span> <span data-ttu-id="1524b-126">Se admiten algunas capacidades básicas de texto enriquecido, como negrita, subrayado y cursiva.</span><span class="sxs-lookup"><span data-stu-id="1524b-126">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |
| <span data-ttu-id="1524b-127">Nombre de clase personalizada</span><span class="sxs-lookup"><span data-stu-id="1524b-127">Custom class name</span></span> | <span data-ttu-id="1524b-128">Un nombre de clase de hojas de estilo en cascada (CSS)</span><span class="sxs-lookup"><span data-stu-id="1524b-128">A Cascading Style Sheets (CSS) class name</span></span>        | <span data-ttu-id="1524b-129">El nombre de una clase CSS personalizada que un desarrollador proporciona para aplicar formato a este módulo.</span><span class="sxs-lookup"><span data-stu-id="1524b-129">The name of a custom CSS class that a developer provides to format this module.</span></span> <span data-ttu-id="1524b-130">El nombre de la clase debe definirse en el paquete de temas.</span><span class="sxs-lookup"><span data-stu-id="1524b-130">The class name should be defined in the theme pack.</span></span> |
| <span data-ttu-id="1524b-131">Tamaño de fuente</span><span class="sxs-lookup"><span data-stu-id="1524b-131">Font size</span></span>         | <span data-ttu-id="1524b-132">**Pequeño**, **Mediano**, **Grande** o **Extragrande**</span><span class="sxs-lookup"><span data-stu-id="1524b-132">**Small**, **Medium**, **Large**, or **X-Large**</span></span> | <span data-ttu-id="1524b-133">El tamaño de fuente del contenido.</span><span class="sxs-lookup"><span data-stu-id="1524b-133">The font size of the content.</span></span> |

## <a name="add-a-text-block-module-to-a-page"></a><span data-ttu-id="1524b-134">Agregar un módulo de bloque de texto a una página</span><span class="sxs-lookup"><span data-stu-id="1524b-134">Add a text block module to a page</span></span>

<span data-ttu-id="1524b-135">Para agregar un módulo de bloque de texto a una nueva página y establecer las propiedades necesarias, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="1524b-135">To add a text block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="1524b-136">Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.</span><span class="sxs-lookup"><span data-stu-id="1524b-136">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="1524b-137">En el cuadro de diálogo **Nueva plantilla**, en **Nombre de plantilla**, introduzca **Plantilla de contenido**.</span><span class="sxs-lookup"><span data-stu-id="1524b-137">In the **New Template** dialog box, under **Template name**, enter **Content template**.</span></span>
1. <span data-ttu-id="1524b-138">En el espacio **Cuerpo**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="1524b-138">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="1524b-139">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Página predeterminada** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1524b-139">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="1524b-140">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="1524b-140">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="1524b-141">Vaya a **Páginas** y seleccione **Nuevo** para crear una nueva página.</span><span class="sxs-lookup"><span data-stu-id="1524b-141">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="1524b-142">En el cuadro de diálogo **Elegir una plantilla**, seleccione la plantilla **Plantilla de contenido**.</span><span class="sxs-lookup"><span data-stu-id="1524b-142">In the **Choose a template** dialog box, select **Content template**.</span></span> <span data-ttu-id="1524b-143">En **Nombre de página**, introduzca **Página de contenido** y después seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1524b-143">Under **Page name**, enter **Content page**, and then select **OK**.</span></span>
1. <span data-ttu-id="1524b-144">En el espacio **Principal** de la nueva página, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="1524b-144">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="1524b-145">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1524b-145">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="1524b-146">En el panel de propiedades para el módulo de contenedor, establezca la propiedad **Ancho** en **Rellenar contenedor**.</span><span class="sxs-lookup"><span data-stu-id="1524b-146">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="1524b-147">En el espacio **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="1524b-147">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="1524b-148">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Bloque de texto** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1524b-148">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span> 
1. <span data-ttu-id="1524b-149">En el panel de propiedades del módulo de bloque de texto, agregue texto al campo **Texto enriquecido**.</span><span class="sxs-lookup"><span data-stu-id="1524b-149">In the property pane of the text block module, add text to the **Rich text** field.</span></span>
1. <span data-ttu-id="1524b-150">Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.</span><span class="sxs-lookup"><span data-stu-id="1524b-150">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="1524b-151">Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="1524b-151">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1524b-152">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="1524b-152">Additional resources</span></span>

[<span data-ttu-id="1524b-153">Visión general de la biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="1524b-153">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="1524b-154">Módulo de banner promocional</span><span class="sxs-lookup"><span data-stu-id="1524b-154">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="1524b-155">Módulo de carrusel</span><span class="sxs-lookup"><span data-stu-id="1524b-155">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="1524b-156">Módulo de bloque de contenido</span><span class="sxs-lookup"><span data-stu-id="1524b-156">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="1524b-157">Módulo de reproductor de vídeo</span><span class="sxs-lookup"><span data-stu-id="1524b-157">Video player module</span></span>](add-video-player.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]