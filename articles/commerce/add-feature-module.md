---
title: Módulo de característica
description: En este tema se tratan los módulos de características y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: 76b59681d0bda11446f6db8b2685d1a0656f8f55
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785315"
---
# <a name="feature-module"></a><span data-ttu-id="76c32-103">Módulo de característica</span><span class="sxs-lookup"><span data-stu-id="76c32-103">Feature module</span></span> 

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="76c32-104">En este tema se tratan los módulos de características y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="76c32-104">This topic covers feature modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="76c32-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="76c32-105">Overview</span></span>

<span data-ttu-id="76c32-106">Un módulo de características se usa para promociones o productos de mercado a través de una combinación de imágenes y texto.</span><span class="sxs-lookup"><span data-stu-id="76c32-106">A feature module is used to market products or promotions through a combination of images and text.</span></span> <span data-ttu-id="76c32-107">Por ejemplo, un minorista puede agregar un módulo de características a una página de detalles de productos para resaltar las características del producto.</span><span class="sxs-lookup"><span data-stu-id="76c32-107">For example, a retailer can add a feature module to a product details page to highlight the features of the product.</span></span>

<span data-ttu-id="76c32-108">Un módulo de características está controlado por datos del sistema de gestión de contenidos (CMS).</span><span class="sxs-lookup"><span data-stu-id="76c32-108">A feature module is driven by data from the content management system (CMS).</span></span> <span data-ttu-id="76c32-109">Es un módulo independiente que no dependen de otros módulos de la página.</span><span class="sxs-lookup"><span data-stu-id="76c32-109">It's a stand-alone module that doesn't depend on any other modules on the page.</span></span> <span data-ttu-id="76c32-110">Un módulo de características se puede colocar en cualquier página de sitio donde un minorista desee comercializar o promocionar algo (por ejemplo, productos, ventas o características).</span><span class="sxs-lookup"><span data-stu-id="76c32-110">A feature module can be put on any site page where a retailer wants to market or promote something (for example products, sales, or features).</span></span>

## <a name="examples-of-feature-modules-in-e-commerce"></a><span data-ttu-id="76c32-111">Ejemplos de módulos de características en comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="76c32-111">Examples of feature modules in e-Commerce</span></span>

<span data-ttu-id="76c32-112">Un módulo de características se puede usar en las siguientes páginas:</span><span class="sxs-lookup"><span data-stu-id="76c32-112">A feature module can used on the following pages:</span></span>

- <span data-ttu-id="76c32-113">Una página de detalles de productos, para mostrar características de producto.</span><span class="sxs-lookup"><span data-stu-id="76c32-113">A product details page, to showcase product features</span></span>
- <span data-ttu-id="76c32-114">La página principal, para promocionar productos</span><span class="sxs-lookup"><span data-stu-id="76c32-114">The home page, to promote products</span></span>
- <span data-ttu-id="76c32-115">Una página de categoría, para resaltar una categoría de productos</span><span class="sxs-lookup"><span data-stu-id="76c32-115">A category page, to highlight a category of products</span></span>

## <a name="feature-module-properties"></a><span data-ttu-id="76c32-116">Propiedades de módulo de características</span><span class="sxs-lookup"><span data-stu-id="76c32-116">Feature module properties</span></span>

| <span data-ttu-id="76c32-117">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="76c32-117">Property name</span></span>     | <span data-ttu-id="76c32-118">Valores</span><span class="sxs-lookup"><span data-stu-id="76c32-118">Values</span></span> | <span data-ttu-id="76c32-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="76c32-119">Description</span></span> |
|-------------------|--------|-------------|
| <span data-ttu-id="76c32-120">Imagen</span><span class="sxs-lookup"><span data-stu-id="76c32-120">Image</span></span>             | <span data-ttu-id="76c32-121">Archivo de imagen</span><span class="sxs-lookup"><span data-stu-id="76c32-121">Image file</span></span> | <span data-ttu-id="76c32-122">Se puede usar una imagen para comercializar el producto o la promoción.</span><span class="sxs-lookup"><span data-stu-id="76c32-122">An image can be used to market the product or promotion.</span></span> <span data-ttu-id="76c32-123">Se puede cargar una imagen en la galería de imágenes, o se puede usar una imagen existente.</span><span class="sxs-lookup"><span data-stu-id="76c32-123">An image can be uploaded to the image gallery, or an existing image can be used.</span></span> |
| <span data-ttu-id="76c32-124">Título</span><span class="sxs-lookup"><span data-stu-id="76c32-124">Heading</span></span>           | <span data-ttu-id="76c32-125">Etiqueta de encabezado y texto de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**)</span><span class="sxs-lookup"><span data-stu-id="76c32-125">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="76c32-126">Cada módulo de características puede tener un encabezado.</span><span class="sxs-lookup"><span data-stu-id="76c32-126">Every feature module can have a heading.</span></span> <span data-ttu-id="76c32-127">De forma predeterminada, la etiqueta de encabezado **H2** se usa para el encabezado.</span><span class="sxs-lookup"><span data-stu-id="76c32-127">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="76c32-128">Sin embargo, la etiqueta se puede cambiar para satisfacer los requisitos de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="76c32-128">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="76c32-129">Párrafo</span><span class="sxs-lookup"><span data-stu-id="76c32-129">Paragraph</span></span>         | <span data-ttu-id="76c32-130">Texto de párrafo</span><span class="sxs-lookup"><span data-stu-id="76c32-130">Paragraph text</span></span> | <span data-ttu-id="76c32-131">Los módulos de características admiten texto de párrafo en formato de texto enriquecido.</span><span class="sxs-lookup"><span data-stu-id="76c32-131">Feature modules support paragraph text in rich text format.</span></span> <span data-ttu-id="76c32-132">Se admiten algunas capacidades básicas de texto enriquecido, como negrita, subrayado y cursiva, además de hipervínculos.</span><span class="sxs-lookup"><span data-stu-id="76c32-132">Some basic rich text capabilities are supported, such as bold, underlined, and italic text, and hyperlinks.</span></span> <span data-ttu-id="76c32-133">Algunas de estas capacidades se pueden anular por el tema de página que se aplica al módulo.</span><span class="sxs-lookup"><span data-stu-id="76c32-133">Some of these capabilities can be overridden by the page theme that is applied to the module.</span></span> |
| <span data-ttu-id="76c32-134">Vincular</span><span class="sxs-lookup"><span data-stu-id="76c32-134">Link</span></span>              | <span data-ttu-id="76c32-135">Texto de vínculo, dirección URL de vínculo, etiqueta de aplicaciones de Internet enriquecidas accesibles (ARIA) y **Abrir vínculo en una nueva pestaña**</span><span class="sxs-lookup"><span data-stu-id="76c32-135">Link text, link URL, Accessible Rich Internet Applications (ARIA) label, and **Open link in new tab**</span></span> | <span data-ttu-id="76c32-136">Los módulos de características admiten uno o más vínculos de “llamada a la acción”.</span><span class="sxs-lookup"><span data-stu-id="76c32-136">Feature modules support one or more "call to action" links.</span></span> <span data-ttu-id="76c32-137">Si se agrega un vínculo, se requiere un texto de vínculo, una dirección URL y una etiqueta ARIA.</span><span class="sxs-lookup"><span data-stu-id="76c32-137">If a link is added, link text, a URL, and an ARIA label are required.</span></span> <span data-ttu-id="76c32-138">Las etiquetas ARIA deben ser descriptivas para cumplir los requisitos de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="76c32-138">ARIA labels should be descriptive to meet accessibility requirements.</span></span> <span data-ttu-id="76c32-139">Los vínculos se pueden configurar para abrirlos en una nueva pestaña.</span><span class="sxs-lookup"><span data-stu-id="76c32-139">Links can be configured so that they are opened on a new tab.</span></span> |
| <span data-ttu-id="76c32-140">Posición de imagen</span><span class="sxs-lookup"><span data-stu-id="76c32-140">Image placement</span></span>   | <span data-ttu-id="76c32-141">**Derecha**, **Izquierda**, **Arriba** o **Inferior**</span><span class="sxs-lookup"><span data-stu-id="76c32-141">**Right**, **Left**, **Top**, or **Bottom**</span></span> | <span data-ttu-id="76c32-142">Esta propiedad define la posición de la imagen en relación con el texto.</span><span class="sxs-lookup"><span data-stu-id="76c32-142">This property defines the position of the image relative to the text.</span></span> <span data-ttu-id="76c32-143">Por ejemplo, si se selecciona **Derecha**, la imagen aparece a la derecha del texto.</span><span class="sxs-lookup"><span data-stu-id="76c32-143">For example, if **Right** is selected, the image appears to the right of the text.</span></span> |
| <span data-ttu-id="76c32-144">Tamaño de columna de imagen</span><span class="sxs-lookup"><span data-stu-id="76c32-144">Image column size</span></span> | <span data-ttu-id="76c32-145">Un valor del **1** al **12**</span><span class="sxs-lookup"><span data-stu-id="76c32-145">A value from **1** through **12**</span></span> | <span data-ttu-id="76c32-146">Esta propiedad define el tamaño de la imagen en relación con el texto.</span><span class="sxs-lookup"><span data-stu-id="76c32-146">This property defines the size of the image relative to the text.</span></span> <span data-ttu-id="76c32-147">El tamaño se expresa como un número de columnas en la página.</span><span class="sxs-lookup"><span data-stu-id="76c32-147">Size is expressed as a number of columns on the page.</span></span> <span data-ttu-id="76c32-148">Hay 12 columnas en una página.</span><span class="sxs-lookup"><span data-stu-id="76c32-148">There are 12 columns on a page.</span></span> <span data-ttu-id="76c32-149">De forma predeterminada, la imagen y el texto tienen igual tamaño (seis columnas cada uno).</span><span class="sxs-lookup"><span data-stu-id="76c32-149">By default, the image and text have equal size (six columns each).</span></span> <span data-ttu-id="76c32-150">Sin embargo, el tamaño se puede ajustar según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="76c32-150">However, the size can be adjusted as required.</span></span> |

## <a name="add-a-feature-module-to-a-new-page"></a><span data-ttu-id="76c32-151">Agregar un módulo de características a una página nueva</span><span class="sxs-lookup"><span data-stu-id="76c32-151">Add a feature module to a new page</span></span> 

<span data-ttu-id="76c32-152">Para agregar un módulo de características a una página nueva y establecer las propiedades necesarias, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="76c32-152">To add a feature module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="76c32-153">Vaya a **Plantillas** y cree una plantilla de página con el nombre **plantilla de características**.</span><span class="sxs-lookup"><span data-stu-id="76c32-153">Go to **Templates**, and create a page template that is named **feature template**.</span></span>
1. <span data-ttu-id="76c32-154">En el espacio **Principal** de la página predeterminada, agregue un módulo de características.</span><span class="sxs-lookup"><span data-stu-id="76c32-154">In the **Main** slot of the default page, add a feature module.</span></span>
1. <span data-ttu-id="76c32-155">Proteja la plantilla y publíquela.</span><span class="sxs-lookup"><span data-stu-id="76c32-155">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="76c32-156">Use la plantilla de características que acaba de crear para crear una página con el nombre **página de características**.</span><span class="sxs-lookup"><span data-stu-id="76c32-156">Use the feature template that you just created to create a page that is named **feature page**.</span></span>
1. <span data-ttu-id="76c32-157">En el espacio **Principal** de la página predeterminada, seleccione los puntos suspensivos (**...**) y, a continuación, **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="76c32-157">In the **Main** slot of the default page, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="76c32-158">En el cuadro de diálogo **Agregar módulo**, en **Seleccionar módulos**, seleccione un módulo de características y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="76c32-158">In the **Add Module** dialog box, under **Select Modules**, select a feature module, and then select **OK**.</span></span>
1. <span data-ttu-id="76c32-159">En el árbol de esquema de la izquierda, seleccione el módulo de características.</span><span class="sxs-lookup"><span data-stu-id="76c32-159">In the outline tree on the left, select the feature module.</span></span>
1. <span data-ttu-id="76c32-160">En el panel de propiedades de la derecha, seleccione **Agregar una imagen**.</span><span class="sxs-lookup"><span data-stu-id="76c32-160">In the properties pane on the right, select **Add an image**.</span></span> <span data-ttu-id="76c32-161">A continuación, seleccione una imagen existente o cargue una imagen nueva.</span><span class="sxs-lookup"><span data-stu-id="76c32-161">Then either select an existing image or upload a new image.</span></span>
1. <span data-ttu-id="76c32-162">Seleccione **Encabezado**.</span><span class="sxs-lookup"><span data-stu-id="76c32-162">Select **Heading**.</span></span>
1. <span data-ttu-id="76c32-163">En el cuadro de diálogo **Encabezado**, agregue el texto del encabezado, seleccione el nivel de encabezado y luego **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="76c32-163">In the **Heading** dialog box, add the heading text, select the heading level, and then select **OK**.</span></span>
1. <span data-ttu-id="76c32-164">En **Texto enriquecido**, agregue el texto según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="76c32-164">Under **Rich Text**, add text as you require.</span></span>
1. <span data-ttu-id="76c32-165">Seleccione **Agregue vínculo de acción**.</span><span class="sxs-lookup"><span data-stu-id="76c32-165">Select **Add Action Link**.</span></span>
1. <span data-ttu-id="76c32-166">En el cuadro de diálogo **Vínculo de acción**, agregue el texto del vínculo, una dirección URL del vínculo y una etiqueta ARIA para el vínculo y, a continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="76c32-166">In the **Action Link** dialog box, add link text, a link URL, and an ARIA label for the link, and then select **OK**.</span></span>
1. <span data-ttu-id="76c32-167">Guarde la página y obtenga una vista previa de los cambios.</span><span class="sxs-lookup"><span data-stu-id="76c32-167">Save the page, and preview your changes.</span></span>
1. <span data-ttu-id="76c32-168">Proteja la página y publíquela.</span><span class="sxs-lookup"><span data-stu-id="76c32-168">Check in the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="76c32-169">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="76c32-169">Additional resources</span></span>

[<span data-ttu-id="76c32-170">Visión general de kit de inicio</span><span class="sxs-lookup"><span data-stu-id="76c32-170">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="76c32-171">Módulo de alerta</span><span class="sxs-lookup"><span data-stu-id="76c32-171">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="76c32-172">Módulo de carrusel</span><span class="sxs-lookup"><span data-stu-id="76c32-172">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="76c32-173">Módulo de bloque de enriquecimiento de contenido</span><span class="sxs-lookup"><span data-stu-id="76c32-173">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="76c32-174">Módulo de sustitución de contenido</span><span class="sxs-lookup"><span data-stu-id="76c32-174">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="76c32-175">Módulo de elemento principal</span><span class="sxs-lookup"><span data-stu-id="76c32-175">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="76c32-176">Módulo de reproductor de vídeo</span><span class="sxs-lookup"><span data-stu-id="76c32-176">Video player module</span></span>](add-video-player.md)
