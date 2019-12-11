---
title: Módulo de bloque de enriquecimiento de contenido
description: En este tema se tratan los módulos de bloque de enriquecimiento de contenido y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: 27dabb425b3c9a3015ffc54ff3c0e50b7ee11749
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785430"
---
# <a name="content-rich-block-module"></a><span data-ttu-id="f8e60-103">Módulo de bloque de enriquecimiento de contenido</span><span class="sxs-lookup"><span data-stu-id="f8e60-103">Content rich block module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="f8e60-104">En este tema se tratan los módulos de bloque de enriquecimiento de contenido y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f8e60-104">This topic covers content rich block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f8e60-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="f8e60-105">Overview</span></span>

<span data-ttu-id="f8e60-106">Un módulo de bloque de enriquecimiento de contenido es un contenedor especial en el que se pueden colocar uno o más elementos de módulo de bloque de enriquecimiento de contenido.</span><span class="sxs-lookup"><span data-stu-id="f8e60-106">A content rich block module is a special container that one or more content rich block items can be put inside.</span></span> <span data-ttu-id="f8e60-107">Los módulos de bloque de enriquecimiento de contenido se utilizan para contenido textual en una página.</span><span class="sxs-lookup"><span data-stu-id="f8e60-107">Content rich block modules are used for textual content on a page.</span></span> <span data-ttu-id="f8e60-108">Este contenido puede ser informativo o promocional.</span><span class="sxs-lookup"><span data-stu-id="f8e60-108">This content can be either informational or promotional.</span></span>

<span data-ttu-id="f8e60-109">Los módulos de bloque de enriquecimiento de contenido se controlan por datos desde el sistema de gestión de contenidos (CMS) y se pueden colocar en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="f8e60-109">Content rich block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="f8e60-110">Son módulos independientes que no dependen del contexto de página o de cualquier otro módulo.</span><span class="sxs-lookup"><span data-stu-id="f8e60-110">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-content-rich-block-modules-in-e-commerce"></a><span data-ttu-id="f8e60-111">Ejemplos de módulos de bloque de enriquecimiento de contenido en comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="f8e60-111">Examples of content rich block modules in e-Commerce</span></span>

<span data-ttu-id="f8e60-112">Los módulos de bloque de enriquecimiento de contenido se pueden utilizar de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="f8e60-112">Content rich block modules can be used in the following ways:</span></span>

* <span data-ttu-id="f8e60-113">Para mostrar características de producto en una página de detalles de productos.</span><span class="sxs-lookup"><span data-stu-id="f8e60-113">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="f8e60-114">Para finalidad informativa en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="f8e60-114">For informational purposes on any page.</span></span> <span data-ttu-id="f8e60-115">Por ejemplo, pueden explicar los beneficios de programas de fidelización, describir las directivas de envío y devolución, responder a preguntas más frecuentes o proporcionar contenido de “acerca de nosotros”.</span><span class="sxs-lookup"><span data-stu-id="f8e60-115">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="f8e60-116">Para agregar mensajes personalizados en una página de detalles de productos.</span><span class="sxs-lookup"><span data-stu-id="f8e60-116">To add custom messages on a product details page.</span></span> <span data-ttu-id="f8e60-117">(por ejemplo, “Envío gratuito para pedidos superiores a 50 €").</span><span class="sxs-lookup"><span data-stu-id="f8e60-117">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="f8e60-118">Para declinaciones de responsabilidad y detalles de contacto sobre páginas de detalles de productos, páginas de finalización de compra y otras páginas (por ejemplo, "Los envíos y las directivas están sujetos a las directivas de la tienda”).</span><span class="sxs-lookup"><span data-stu-id="f8e60-118">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

## <a name="content-rich-block-module-properties"></a><span data-ttu-id="f8e60-119">Propiedades del módulo de bloque de enriquecimiento de contenido</span><span class="sxs-lookup"><span data-stu-id="f8e60-119">Content rich block module properties</span></span>

| <span data-ttu-id="f8e60-120">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="f8e60-120">Property name</span></span>     | <span data-ttu-id="f8e60-121">Valor</span><span class="sxs-lookup"><span data-stu-id="f8e60-121">Value</span></span>                                 | <span data-ttu-id="f8e60-122">Propiedad</span><span class="sxs-lookup"><span data-stu-id="f8e60-122">Property</span></span> |
|-------------------|---------------------------------------|----------|
| <span data-ttu-id="f8e60-123">Número de columnas</span><span class="sxs-lookup"><span data-stu-id="f8e60-123">Number of columns</span></span> | <span data-ttu-id="f8e60-124">Un número del **1** al **4**</span><span class="sxs-lookup"><span data-stu-id="f8e60-124">A number from **1** through **4**</span></span>     | <span data-ttu-id="f8e60-125">Número de columnas de un bloque de enriquecimiento de contenido.</span><span class="sxs-lookup"><span data-stu-id="f8e60-125">The number of columns in the content rich block.</span></span> <span data-ttu-id="f8e60-126">Puede haber hasta cuatro columnas.</span><span class="sxs-lookup"><span data-stu-id="f8e60-126">There can be up to four columns.</span></span> |
| <span data-ttu-id="f8e60-127">Ancho</span><span class="sxs-lookup"><span data-stu-id="f8e60-127">Width</span></span>             | <span data-ttu-id="f8e60-128">**Rellenar contenedor** o **Rellenar pantalla**</span><span class="sxs-lookup"><span data-stu-id="f8e60-128">**Fill container** or **Fill screen**</span></span> | <span data-ttu-id="f8e60-129">Si el valor se establece en **Rellenar contenedor**, los elementos que se encuentran dentro del contenedor se limitan al ancho del contenedor.</span><span class="sxs-lookup"><span data-stu-id="f8e60-129">If the value is set to **Fill container**, the items inside the container are restricted to the width of the container.</span></span> <span data-ttu-id="f8e60-130">Si el valor se establece en **Rellenar pantalla**, los elementos no se limitan al ancho del contenedor, pero pueden entrar en el modo de pantalla completa.</span><span class="sxs-lookup"><span data-stu-id="f8e60-130">If the value is set to **Fill screen**, the items aren't restricted to the container width but can go into full-screen mode.</span></span> <span data-ttu-id="f8e60-131">Puede cambiar el valor para lograr el diseño deseado.</span><span class="sxs-lookup"><span data-stu-id="f8e60-131">You can change the value to achieve the desired layout.</span></span> |

## <a name="content-rich-block-item-module-properties"></a><span data-ttu-id="f8e60-132">Propiedades del módulo de elemento de bloque de enriquecimiento de contenido</span><span class="sxs-lookup"><span data-stu-id="f8e60-132">Content rich block item module properties</span></span>

| <span data-ttu-id="f8e60-133">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="f8e60-133">Property name</span></span> | <span data-ttu-id="f8e60-134">Valor</span><span class="sxs-lookup"><span data-stu-id="f8e60-134">Value</span></span>          | <span data-ttu-id="f8e60-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8e60-135">Description</span></span> |
|---------------|----------------|-------------|
| <span data-ttu-id="f8e60-136">Párrafo</span><span class="sxs-lookup"><span data-stu-id="f8e60-136">Paragraph</span></span>     | <span data-ttu-id="f8e60-137">Texto de párrafo</span><span class="sxs-lookup"><span data-stu-id="f8e60-137">Paragraph text</span></span> | <span data-ttu-id="f8e60-138">El texto que acompaña a cada elemento de bloque de enriquecimiento de contenido.</span><span class="sxs-lookup"><span data-stu-id="f8e60-138">The text that accompanies each content rich block item.</span></span> <span data-ttu-id="f8e60-139">Se admiten algunas capacidades básicas de texto enriquecido, como negrita, subrayado y cursiva.</span><span class="sxs-lookup"><span data-stu-id="f8e60-139">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |

## <a name="add-a-content-rich-block-module-to-a-page"></a><span data-ttu-id="f8e60-140">Agregar un módulo de bloque de enriquecimiento de contenido a una página</span><span class="sxs-lookup"><span data-stu-id="f8e60-140">Add a content rich block module to a page</span></span>

<span data-ttu-id="f8e60-141">Para agregar un módulo de bloque de enriquecimiento de contenido a una nueva página y establecer las propiedades necesarias, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f8e60-141">To add a content rich block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="f8e60-142">Cree una plantilla de página con el nombre **Plantilla de contenido**.</span><span class="sxs-lookup"><span data-stu-id="f8e60-142">Create a page template that is named **Content template**.</span></span>
1. <span data-ttu-id="f8e60-143">En el espacio **Principal** de la página predeterminada, agregue un módulo de bloque de enriquecimiento de contenido.</span><span class="sxs-lookup"><span data-stu-id="f8e60-143">In the **Main** slot of the default page, add a content rich block module.</span></span>
1. <span data-ttu-id="f8e60-144">Proteja la plantilla y publíquela.</span><span class="sxs-lookup"><span data-stu-id="f8e60-144">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="f8e60-145">Use la plantilla de contenido que acaba de crear para crear una página que se llame **Página de contenido**.</span><span class="sxs-lookup"><span data-stu-id="f8e60-145">Use the content template that you just created to create a page that is named **Content page**.</span></span>
1. <span data-ttu-id="f8e60-146">En el espacio **Principal** de la nueva página, agregue un módulo de bloque de enriquecimiento de contenido.</span><span class="sxs-lookup"><span data-stu-id="f8e60-146">In the **Main** slot of the new page, add a content rich block module.</span></span>
1. <span data-ttu-id="f8e60-147">En las propiedades del módulo de bloque de enriquecimiento de contenido, establezca el número de columnas en **2**.</span><span class="sxs-lookup"><span data-stu-id="f8e60-147">In the properties of the content rich block module, set number of columns to **2**.</span></span>
1. <span data-ttu-id="f8e60-148">En el módulo de bloque de enriquecimiento de contenido, seleccione **Agregar un módulo** y agregue un elemento de bloque de enriquecimiento de contenido (por ejemplo, **elemento1**).</span><span class="sxs-lookup"><span data-stu-id="f8e60-148">In the content rich block module, select **Add a module**, and add a content rich block item (for example, **item1**).</span></span>
1. <span data-ttu-id="f8e60-149">En el nuevo elemento de bloque de enriquecimiento de contenido, agregue el texto del párrafo.</span><span class="sxs-lookup"><span data-stu-id="f8e60-149">In the new content rich block item, add paragraph text.</span></span>
1. <span data-ttu-id="f8e60-150">En el módulo de bloque de enriquecimiento de contenido, seleccione **Agregar un módulo** y agregue un elemento de bloque de enriquecimiento de contenido (por ejemplo, **elemento2**).</span><span class="sxs-lookup"><span data-stu-id="f8e60-150">In the content rich block module, select **Add a module**, and add a content rich block item (for example, **item2**).</span></span>
1. <span data-ttu-id="f8e60-151">En el nuevo elemento de bloque de enriquecimiento de contenido, agregue el texto del párrafo.</span><span class="sxs-lookup"><span data-stu-id="f8e60-151">In the new content rich block item, add paragraph text.</span></span>
1. <span data-ttu-id="f8e60-152">Guarde la página y obtenga una vista previa de los cambios.</span><span class="sxs-lookup"><span data-stu-id="f8e60-152">Save the page, and preview the changes.</span></span> <span data-ttu-id="f8e60-153">Debería ver dos bloques de texto enriquecido en una vista de dos columnas.</span><span class="sxs-lookup"><span data-stu-id="f8e60-153">You should see two rich text blocks in a two-column view.</span></span>
1. <span data-ttu-id="f8e60-154">Proteja la página y publíquela.</span><span class="sxs-lookup"><span data-stu-id="f8e60-154">Check in the page, and publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="f8e60-155">Si agrega un tercer elemento de bloque de enriquecimiento de contenido, se apilará debajo de los dos elementos que había agregado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f8e60-155">If you add a third content rich block item, it will be stacked below the two items that you previously added.</span></span> <span data-ttu-id="f8e60-156">Al cambiar el número de columnas y elementos en el contenedor, podrá lograr diferentes diseños para el contenido textual.</span><span class="sxs-lookup"><span data-stu-id="f8e60-156">By changing the number of columns and items in the container, you can achieve different layouts for textual content.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f8e60-157">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f8e60-157">Additional resources</span></span>

[<span data-ttu-id="f8e60-158">Visión general de kit de inicio</span><span class="sxs-lookup"><span data-stu-id="f8e60-158">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="f8e60-159">Módulo de alerta</span><span class="sxs-lookup"><span data-stu-id="f8e60-159">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="f8e60-160">Módulo de carrusel</span><span class="sxs-lookup"><span data-stu-id="f8e60-160">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="f8e60-161">Módulo de colocación de contenido</span><span class="sxs-lookup"><span data-stu-id="f8e60-161">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="f8e60-162">Módulo de característica</span><span class="sxs-lookup"><span data-stu-id="f8e60-162">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="f8e60-163">Módulo de elemento principal</span><span class="sxs-lookup"><span data-stu-id="f8e60-163">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="f8e60-164">Módulo de reproductor de vídeo</span><span class="sxs-lookup"><span data-stu-id="f8e60-164">Video player module</span></span>](add-video-player.md)

