---
title: Módulo de elemento principal
description: En este tema se tratan los módulos de elemento principal y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: c43704992e9759e7207f1b1c9bc958449daa6d1d
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785407"
---
# <a name="hero-module"></a><span data-ttu-id="88f4e-103">Módulo de elemento principal</span><span class="sxs-lookup"><span data-stu-id="88f4e-103">Hero module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="88f4e-104">En este tema se tratan los módulos de elemento principal y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="88f4e-104">This topic covers hero modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="88f4e-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="88f4e-105">Overview</span></span>

<span data-ttu-id="88f4e-106">Un módulo de elemento principal se usa para promociones o productos de mercado a través de una combinación de imágenes y texto.</span><span class="sxs-lookup"><span data-stu-id="88f4e-106">A hero module is used to market products or promotions through a combination of images and text.</span></span> <span data-ttu-id="88f4e-107">Por ejemplo, un minorista puede agregar un módulo de elemento principal a la página principal de un sitio de comercio electrónico para promocionar un nuevo producto y atraer la atención de los clientes.</span><span class="sxs-lookup"><span data-stu-id="88f4e-107">For example, a retailer can add a hero module to the home page of an e-Commerce site to promote a new product and attract the attention of customers.</span></span>

<span data-ttu-id="88f4e-108">Un módulo de elemento de principal está controlado por datos del sistema de gestión de contenidos (CMS).</span><span class="sxs-lookup"><span data-stu-id="88f4e-108">A hero module is driven by data from the content management system (CMS).</span></span> <span data-ttu-id="88f4e-109">Es un módulo independiente que no dependen de otros módulos de la página.</span><span class="sxs-lookup"><span data-stu-id="88f4e-109">It's a stand-alone module that doesn't depend on any other modules on the page.</span></span> <span data-ttu-id="88f4e-110">Un módulo de elemento principal se puede colocar en cualquier página de sitio donde un minorista desee comercializar o promocionar algo (por ejemplo, productos, ventas o características).</span><span class="sxs-lookup"><span data-stu-id="88f4e-110">A hero module can be put on any site page where a retailer wants to market or promote something (for example, products, sales, or features).</span></span>

## <a name="examples-of-hero-module-in-e-commerce"></a><span data-ttu-id="88f4e-111">Ejemplos de módulos de elemento principal en comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="88f4e-111">Examples of hero module in e-Commerce</span></span>

- <span data-ttu-id="88f4e-112">Un módulo de elemento principal se puede usar en la página principal de un sitio de comercio electrónico para resaltar promociones y nuevos productos.</span><span class="sxs-lookup"><span data-stu-id="88f4e-112">A hero module can be used on the home page of an e-Commerce site to highlight promotions and new products.</span></span>
- <span data-ttu-id="88f4e-113">Un módulo de héroe se puede usar en una página de detalles de productos para mostrar la información del producto.</span><span class="sxs-lookup"><span data-stu-id="88f4e-113">A hero module can be used on a product details page to showcase product information.</span></span>
- <span data-ttu-id="88f4e-114">Varios módulos de elemento principal se pueden colocar en un módulo de carrusel para resaltar varios productos o promociones.</span><span class="sxs-lookup"><span data-stu-id="88f4e-114">Multiple hero modules can be put inside a carousel module to highlight multiple products or promotions.</span></span>

## <a name="hero-module-properties"></a><span data-ttu-id="88f4e-115">Propiedades del módulo de elemento principal</span><span class="sxs-lookup"><span data-stu-id="88f4e-115">Hero module properties</span></span>

| <span data-ttu-id="88f4e-116">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="88f4e-116">Property name</span></span>  | <span data-ttu-id="88f4e-117">Valores</span><span class="sxs-lookup"><span data-stu-id="88f4e-117">Values</span></span> | <span data-ttu-id="88f4e-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="88f4e-118">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="88f4e-119">Imagen</span><span class="sxs-lookup"><span data-stu-id="88f4e-119">Image</span></span>          | <span data-ttu-id="88f4e-120">Archivo de imagen</span><span class="sxs-lookup"><span data-stu-id="88f4e-120">Image file</span></span> | <span data-ttu-id="88f4e-121">Se puede usar una imagen para mostrar un producto o una promoción.</span><span class="sxs-lookup"><span data-stu-id="88f4e-121">An image can be used to showcase a product or a promotion.</span></span> <span data-ttu-id="88f4e-122">Se puede cargar una imagen en la galería de imágenes, o se puede usar una imagen existente.</span><span class="sxs-lookup"><span data-stu-id="88f4e-122">An image can be uploaded to the image gallery, or an existing image can be used.</span></span> |
| <span data-ttu-id="88f4e-123">Título</span><span class="sxs-lookup"><span data-stu-id="88f4e-123">Heading</span></span>        | <span data-ttu-id="88f4e-124">Etiqueta de encabezado y texto de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**)</span><span class="sxs-lookup"><span data-stu-id="88f4e-124">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="88f4e-125">Cada módulo de elemento principal puede tener un encabezado.</span><span class="sxs-lookup"><span data-stu-id="88f4e-125">Every hero module can have a heading.</span></span> <span data-ttu-id="88f4e-126">De forma predeterminada, la etiqueta de encabezado **H2** se usa para el encabezado.</span><span class="sxs-lookup"><span data-stu-id="88f4e-126">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="88f4e-127">Sin embargo, la etiqueta se puede cambiar para satisfacer los requisitos de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="88f4e-127">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="88f4e-128">Párrafo</span><span class="sxs-lookup"><span data-stu-id="88f4e-128">Paragraph</span></span>      | <span data-ttu-id="88f4e-129">Texto de párrafo</span><span class="sxs-lookup"><span data-stu-id="88f4e-129">Paragraph text</span></span> | <span data-ttu-id="88f4e-130">Los módulos de elemento principal admiten texto de párrafo en formato de texto enriquecido.</span><span class="sxs-lookup"><span data-stu-id="88f4e-130">Hero modules support paragraph text in rich text format.</span></span> <span data-ttu-id="88f4e-131">Se admiten algunas capacidades básicas de texto enriquecido, como negrita, subrayado y cursiva, además de hipervínculos.</span><span class="sxs-lookup"><span data-stu-id="88f4e-131">Some basic rich text capabilities are supported, such as bold, underlined, and italic text, and hyperlinks.</span></span> <span data-ttu-id="88f4e-132">Algunas de estas capacidades se pueden anular por el tema de página que se aplica al módulo.</span><span class="sxs-lookup"><span data-stu-id="88f4e-132">Some of these capabilities can be overridden by the page theme that is applied to the module.</span></span> |
| <span data-ttu-id="88f4e-133">Vincular</span><span class="sxs-lookup"><span data-stu-id="88f4e-133">Link</span></span>           | <span data-ttu-id="88f4e-134">Texto de vínculo, dirección URL de vínculo, etiqueta de aplicaciones de Internet enriquecidas accesibles (ARIA) y **Abrir vínculo en una nueva pestaña**</span><span class="sxs-lookup"><span data-stu-id="88f4e-134">Link text, link URL, Accessible Rich Internet Applications (ARIA) label, and **Open link in new tab**</span></span> | <span data-ttu-id="88f4e-135">Los módulos de elemento principal admiten uno o más vínculos de “llamada a la acción”.</span><span class="sxs-lookup"><span data-stu-id="88f4e-135">Hero modules support one or more "call to action" links.</span></span> <span data-ttu-id="88f4e-136">Si se agrega un vínculo, se requiere un texto de vínculo, una dirección URL y una etiqueta ARIA.</span><span class="sxs-lookup"><span data-stu-id="88f4e-136">If a link is added, link text, a URL, and an ARIA label are required.</span></span> <span data-ttu-id="88f4e-137">Las etiquetas ARIA deben ser descriptivas para cumplir los requisitos de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="88f4e-137">ARIA labels should be descriptive to meet accessibility requirements.</span></span> <span data-ttu-id="88f4e-138">Los vínculos se pueden configurar para abrirlos en una nueva pestaña.</span><span class="sxs-lookup"><span data-stu-id="88f4e-138">Links can be configured so that they are opened on a new tab.</span></span> |
| <span data-ttu-id="88f4e-139">Posición del texto</span><span class="sxs-lookup"><span data-stu-id="88f4e-139">Text placement</span></span> | <span data-ttu-id="88f4e-140">**Superior izquierda**, **Superior derecha**, **Centro superior**, **Inferior izquierda**, **Inferior derecha**, **Centro inferior**, **Centro izquierda**, **Centro izquierda** o **Centro centro**</span><span class="sxs-lookup"><span data-stu-id="88f4e-140">**Top Left**, **Top Right**, **Top Center**, **Bottom Left**, **Bottom Right**, **Bottom Center**, **Center Left**, **Center Right**, or **Center Center**</span></span> | <span data-ttu-id="88f4e-141">Esta propiedad define la posición de la imagen en relación con el texto.</span><span class="sxs-lookup"><span data-stu-id="88f4e-141">This property defines the position of the image relative to the text.</span></span> <span data-ttu-id="88f4e-142">Por ejemplo, si se selecciona **Derecha**, la imagen aparece a la derecha del texto.</span><span class="sxs-lookup"><span data-stu-id="88f4e-142">For example, if **Right** is selected, the image appears to the right of the text.</span></span> |
| <span data-ttu-id="88f4e-143">Tema de texto</span><span class="sxs-lookup"><span data-stu-id="88f4e-143">Text theme</span></span>     | <span data-ttu-id="88f4e-144">**Claro** u **Oscuro**</span><span class="sxs-lookup"><span data-stu-id="88f4e-144">**Light** or **Dark**</span></span> | <span data-ttu-id="88f4e-145">Un esquema de colores se puede definir para el texto, en función de la imagen de fondo.</span><span class="sxs-lookup"><span data-stu-id="88f4e-145">A color scheme can be defined for the text, based on the background image.</span></span> <span data-ttu-id="88f4e-146">Por ejemplo, si la imagen tiene un fondo oscuro, se puede aplicar un tema claro para que el texto sea más visible y cumplir las relaciones de contraste de color para fines de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="88f4e-146">For example, if the image has a dark background, a light theme can be applied to make the text more visible and to meet color contrast ratios for accessibility purposes.</span></span> |
| <span data-ttu-id="88f4e-147">Degradado</span><span class="sxs-lookup"><span data-stu-id="88f4e-147">Gradient</span></span>       | <span data-ttu-id="88f4e-148">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="88f4e-148">**True** or **False**</span></span> | <span data-ttu-id="88f4e-149">Se puede aplicar un degradado a la imagen para cumplir las relaciones de contraste de color para fines de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="88f4e-149">A gradient can be applied to the image to meet color contrast ratios for accessibility purposes.</span></span> |

## <a name="add-a-hero-module-to-a-new-page"></a><span data-ttu-id="88f4e-150">Agregar un módulo de elemento principal a una página nueva</span><span class="sxs-lookup"><span data-stu-id="88f4e-150">Add a hero module to a new page</span></span>

<span data-ttu-id="88f4e-151">Para agregar un módulo de elemento principal a una página nueva y establecer las propiedades necesarias, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="88f4e-151">To add a hero module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="88f4e-152">Vaya a **Plantillas** y cree una plantilla de página con el nombre **plantilla de elemento principal**.</span><span class="sxs-lookup"><span data-stu-id="88f4e-152">Go to **Templates**, and create a page template that is named **hero template**.</span></span>
1. <span data-ttu-id="88f4e-153">En el espacio **Principal** de la página predeterminada, agregue un módulo de elemento principal.</span><span class="sxs-lookup"><span data-stu-id="88f4e-153">In the **Main** slot of the default page, add a hero module.</span></span>
1. <span data-ttu-id="88f4e-154">Proteja la plantilla y publíquela.</span><span class="sxs-lookup"><span data-stu-id="88f4e-154">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="88f4e-155">Use la plantilla de elemento principal que acaba de crear para crear una página que se llame **página de elemento principal**.</span><span class="sxs-lookup"><span data-stu-id="88f4e-155">Use the hero template that you just created to create a page that is named **hero page**.</span></span>
1. <span data-ttu-id="88f4e-156">En el espacio **Principal** de la página predeterminada, seleccione los puntos suspensivos (**...**) y, a continuación, **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="88f4e-156">In the **Main** slot of the default page, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="88f4e-157">En el cuadro de diálogo **Agregar módulo**, en **Seleccionar módulos**, seleccione el módulo de elemento principal y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="88f4e-157">In the **Add Module** dialog box, under **Select Modules**, select the hero module, and then select **OK**.</span></span>
1. <span data-ttu-id="88f4e-158">En el árbol de esquema de la izquierda, seleccione el módulo de elemento principal.</span><span class="sxs-lookup"><span data-stu-id="88f4e-158">In the outline tree on the left, select the hero module.</span></span>
1. <span data-ttu-id="88f4e-159">En el panel de propiedades de la derecha, seleccione **Agregar una imagen**.</span><span class="sxs-lookup"><span data-stu-id="88f4e-159">In the properties pane on the right, select **Add an image**.</span></span> <span data-ttu-id="88f4e-160">A continuación, seleccione una imagen existente o cargue una imagen nueva.</span><span class="sxs-lookup"><span data-stu-id="88f4e-160">Then either select an existing image or upload a new image.</span></span>
1. <span data-ttu-id="88f4e-161">Seleccione **Encabezado**.</span><span class="sxs-lookup"><span data-stu-id="88f4e-161">Select **Heading**.</span></span>
1. <span data-ttu-id="88f4e-162">En el cuadro de diálogo **Encabezado**, agregue el texto del encabezado, seleccione el nivel de encabezado y luego **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="88f4e-162">In the **Heading** dialog box, add the heading text, select the heading level, and then select **OK**.</span></span>
1. <span data-ttu-id="88f4e-163">En **Texto enriquecido**, agregue el texto según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="88f4e-163">Under **Rich Text**, add text as you require.</span></span>
1. <span data-ttu-id="88f4e-164">Seleccione **Agregue vínculo de acción**.</span><span class="sxs-lookup"><span data-stu-id="88f4e-164">Select **Add Action Link**.</span></span>
1. <span data-ttu-id="88f4e-165">En el cuadro de diálogo **Vínculo de acción**, agregue el texto del vínculo, una dirección URL del vínculo y una etiqueta ARIA para el vínculo y, a continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="88f4e-165">In the **Action Link** dialog box, add link text, a link URL, and an ARIA label for the link, and then select **OK**.</span></span>
1. <span data-ttu-id="88f4e-166">Guarde la página y obtenga una vista previa de los cambios.</span><span class="sxs-lookup"><span data-stu-id="88f4e-166">Save the page, and preview your changes.</span></span>
1. <span data-ttu-id="88f4e-167">Proteja la página y publíquela.</span><span class="sxs-lookup"><span data-stu-id="88f4e-167">Check in the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="88f4e-168">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="88f4e-168">Additional resources</span></span>

[<span data-ttu-id="88f4e-169">Visión general de kit de inicio</span><span class="sxs-lookup"><span data-stu-id="88f4e-169">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="88f4e-170">Módulo de alerta</span><span class="sxs-lookup"><span data-stu-id="88f4e-170">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="88f4e-171">Módulo de carrusel</span><span class="sxs-lookup"><span data-stu-id="88f4e-171">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="88f4e-172">Módulo de bloque de enriquecimiento de contenido</span><span class="sxs-lookup"><span data-stu-id="88f4e-172">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="88f4e-173">Módulo de sustitución de contenido</span><span class="sxs-lookup"><span data-stu-id="88f4e-173">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="88f4e-174">Módulo de característica</span><span class="sxs-lookup"><span data-stu-id="88f4e-174">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="88f4e-175">Módulo de reproductor de vídeo</span><span class="sxs-lookup"><span data-stu-id="88f4e-175">Video player module</span></span>](add-video-player.md)