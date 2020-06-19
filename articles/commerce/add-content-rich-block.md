---
title: Módulo de bloque de texto
description: En este tema se tratan los módulos de bloque de texto y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 93ad09a05d188a30b099b9a44c35e15839be80a7
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411144"
---
# <a name="text-block-module"></a><span data-ttu-id="6af2f-103">Módulo de bloque de texto</span><span class="sxs-lookup"><span data-stu-id="6af2f-103">Text block module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="6af2f-104">En este tema se tratan los módulos de bloque de texto y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6af2f-104">This topic covers text block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="6af2f-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="6af2f-105">Overview</span></span>

<span data-ttu-id="6af2f-106">Un módulo de bloque de texto es un módulo que se utiliza para agregar contenido textual.</span><span class="sxs-lookup"><span data-stu-id="6af2f-106">A text block module is a module that is used to add textual content.</span></span> <span data-ttu-id="6af2f-107">Este contenido puede ser informativo o promocional.</span><span class="sxs-lookup"><span data-stu-id="6af2f-107">This content can be informational or promotional.</span></span>

<span data-ttu-id="6af2f-108">Los módulos de bloque de texto se controlan con datos desde el sistema de gestión de contenidos (CMS) y se pueden colocar en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="6af2f-108">Text block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="6af2f-109">Son módulos independientes que no dependen del contexto de página o de cualquier otro módulo.</span><span class="sxs-lookup"><span data-stu-id="6af2f-109">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-text-block-modules-in-e-commerce"></a><span data-ttu-id="6af2f-110">Ejemplos de módulos de bloque de texto en comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="6af2f-110">Examples of text block modules in e-Commerce</span></span>

<span data-ttu-id="6af2f-111">Los módulos de bloque de texto se pueden utilizar de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="6af2f-111">Text block modules can be used in the following ways:</span></span>

* <span data-ttu-id="6af2f-112">Para mostrar características de producto en una página de detalles de productos.</span><span class="sxs-lookup"><span data-stu-id="6af2f-112">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="6af2f-113">Para finalidad informativa en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="6af2f-113">For informational purposes on any page.</span></span> <span data-ttu-id="6af2f-114">Por ejemplo, pueden explicar los beneficios de programas de fidelización, describir las directivas de envío y devolución, responder a preguntas más frecuentes o proporcionar contenido de “acerca de nosotros”.</span><span class="sxs-lookup"><span data-stu-id="6af2f-114">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="6af2f-115">Para agregar mensajes personalizados en una página de detalles de productos.</span><span class="sxs-lookup"><span data-stu-id="6af2f-115">To add custom messages on a product details page.</span></span> <span data-ttu-id="6af2f-116">(por ejemplo, “Envío gratuito para pedidos superiores a 50 €").</span><span class="sxs-lookup"><span data-stu-id="6af2f-116">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="6af2f-117">Para declinaciones de responsabilidad y detalles de contacto sobre páginas de detalles de productos, páginas de finalización de compra y otras páginas (por ejemplo, "Los envíos y las directivas están sujetos a las directivas de la tienda”).</span><span class="sxs-lookup"><span data-stu-id="6af2f-117">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

<span data-ttu-id="6af2f-118">La siguiente imagen muestra un ejemplo de un módulo de bloque de texto utilizado en una página principal.</span><span class="sxs-lookup"><span data-stu-id="6af2f-118">The following image shows an example of a text block module that is used on a home page.</span></span>

![Ejemplo de un módulo de bloque de texto](./media/ecommerce-textblock.PNG)

## <a name="text-block-module-properties"></a><span data-ttu-id="6af2f-120">Propiedades de módulo de bloque de texto</span><span class="sxs-lookup"><span data-stu-id="6af2f-120">Text block module properties</span></span>

| <span data-ttu-id="6af2f-121">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="6af2f-121">Property name</span></span>     | <span data-ttu-id="6af2f-122">Valor</span><span class="sxs-lookup"><span data-stu-id="6af2f-122">Value</span></span>                                            | <span data-ttu-id="6af2f-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="6af2f-123">Description</span></span> |
|-------------------|--------------------------------------------------|-------------|
| <span data-ttu-id="6af2f-124">Texto enriquecido</span><span class="sxs-lookup"><span data-stu-id="6af2f-124">Rich text</span></span>         | <span data-ttu-id="6af2f-125">Texto enriquecido</span><span class="sxs-lookup"><span data-stu-id="6af2f-125">Rich text</span></span>                                        | <span data-ttu-id="6af2f-126">Texto de párrafo.</span><span class="sxs-lookup"><span data-stu-id="6af2f-126">Paragraph text.</span></span> <span data-ttu-id="6af2f-127">Se admiten algunas capacidades básicas de texto enriquecido, como negrita, subrayado y cursiva.</span><span class="sxs-lookup"><span data-stu-id="6af2f-127">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |
| <span data-ttu-id="6af2f-128">Nombre de clase personalizada</span><span class="sxs-lookup"><span data-stu-id="6af2f-128">Custom class name</span></span> | <span data-ttu-id="6af2f-129">Un nombre de clase de hojas de estilo en cascada (CSS)</span><span class="sxs-lookup"><span data-stu-id="6af2f-129">A Cascading Style Sheets (CSS) class name</span></span>        | <span data-ttu-id="6af2f-130">El nombre de una clase CSS personalizada que un desarrollador proporciona para aplicar formato a este módulo.</span><span class="sxs-lookup"><span data-stu-id="6af2f-130">The name of a custom CSS class that a developer provides to format this module.</span></span> <span data-ttu-id="6af2f-131">El nombre de la clase debe definirse en el paquete de temas.</span><span class="sxs-lookup"><span data-stu-id="6af2f-131">The class name should be defined in the theme pack.</span></span> |
| <span data-ttu-id="6af2f-132">Tamaño de fuente</span><span class="sxs-lookup"><span data-stu-id="6af2f-132">Font size</span></span>         | <span data-ttu-id="6af2f-133">**Pequeño**, **Mediano**, **Grande** o **Extragrande**</span><span class="sxs-lookup"><span data-stu-id="6af2f-133">**Small**, **Medium**, **Large**, or **X-Large**</span></span> | <span data-ttu-id="6af2f-134">El tamaño de fuente del contenido.</span><span class="sxs-lookup"><span data-stu-id="6af2f-134">The font size of the content.</span></span> |

## <a name="add-a-text-block-module-to-a-page"></a><span data-ttu-id="6af2f-135">Agregar un módulo de bloque de texto a una página</span><span class="sxs-lookup"><span data-stu-id="6af2f-135">Add a text block module to a page</span></span>

<span data-ttu-id="6af2f-136">Para agregar un módulo de bloque de texto a una nueva página y establecer las propiedades necesarias, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6af2f-136">To add a text block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="6af2f-137">Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.</span><span class="sxs-lookup"><span data-stu-id="6af2f-137">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="6af2f-138">En el cuadro de diálogo **Nueva plantilla**, en **Nombre de plantilla**, introduzca **Plantilla de contenido**.</span><span class="sxs-lookup"><span data-stu-id="6af2f-138">In the **New Template** dialog box, under **Template name**, enter **Content template**.</span></span>
1. <span data-ttu-id="6af2f-139">En el espacio **Cuerpo**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="6af2f-139">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="6af2f-140">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Página predeterminada** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6af2f-140">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="6af2f-141">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="6af2f-141">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="6af2f-142">Vaya a **Páginas** y seleccione **Nuevo** para crear una nueva página.</span><span class="sxs-lookup"><span data-stu-id="6af2f-142">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="6af2f-143">En el cuadro de diálogo **Elegir una plantilla**, seleccione la plantilla **Plantilla de contenido**.</span><span class="sxs-lookup"><span data-stu-id="6af2f-143">In the **Choose a template** dialog box, select **Content template**.</span></span> <span data-ttu-id="6af2f-144">En **Nombre de página**, introduzca **Página de contenido** y después seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6af2f-144">Under **Page name**, enter **Content page**, and then select **OK**.</span></span>
1. <span data-ttu-id="6af2f-145">En el espacio **Principal** de la nueva página, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="6af2f-145">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="6af2f-146">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6af2f-146">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="6af2f-147">En el panel de propiedades para el módulo de contenedor, establezca la propiedad **Ancho** en **Rellenar contenedor**.</span><span class="sxs-lookup"><span data-stu-id="6af2f-147">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="6af2f-148">En el espacio **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="6af2f-148">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="6af2f-149">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Bloque de texto** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6af2f-149">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span> 
1. <span data-ttu-id="6af2f-150">En el panel de propiedades del módulo de bloque de texto, agregue texto al campo **Texto enriquecido**.</span><span class="sxs-lookup"><span data-stu-id="6af2f-150">In the property pane of the text block module, add text to the **Rich text** field.</span></span>
1. <span data-ttu-id="6af2f-151">Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.</span><span class="sxs-lookup"><span data-stu-id="6af2f-151">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="6af2f-152">Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="6af2f-152">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6af2f-153">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="6af2f-153">Additional resources</span></span>

[<span data-ttu-id="6af2f-154">Visión general del kit de inicio</span><span class="sxs-lookup"><span data-stu-id="6af2f-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="6af2f-155">Módulo de banner promocional</span><span class="sxs-lookup"><span data-stu-id="6af2f-155">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="6af2f-156">Módulo de carrusel</span><span class="sxs-lookup"><span data-stu-id="6af2f-156">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="6af2f-157">Módulo de bloque de contenido</span><span class="sxs-lookup"><span data-stu-id="6af2f-157">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="6af2f-158">Módulo de reproductor de vídeo</span><span class="sxs-lookup"><span data-stu-id="6af2f-158">Video player module</span></span>](add-video-player.md)

