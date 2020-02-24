---
title: Módulo de bloque de texto
description: En este tema se tratan los módulos de bloque de texto y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: fc5b2fa35633b1ce7f7ffefacec318e14fa8db3f
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025606"
---
# <a name="text-block-module"></a><span data-ttu-id="42cde-103">Módulo de bloque de texto</span><span class="sxs-lookup"><span data-stu-id="42cde-103">Text block module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="42cde-104">En este tema se tratan los módulos de bloque de texto y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="42cde-104">This topic covers text block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="42cde-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="42cde-105">Overview</span></span>

<span data-ttu-id="42cde-106">Un módulo de bloque de texto es un módulo que se utiliza para agregar contenido textual.</span><span class="sxs-lookup"><span data-stu-id="42cde-106">A text block module is a module that is used to add textual content.</span></span> <span data-ttu-id="42cde-107">Este contenido puede ser informativo o promocional.</span><span class="sxs-lookup"><span data-stu-id="42cde-107">This content can be informational or promotional.</span></span>

<span data-ttu-id="42cde-108">Los módulos de bloque de texto se controlan con datos desde el sistema de gestión de contenidos (CMS) y se pueden colocar en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="42cde-108">Text block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="42cde-109">Son módulos independientes que no dependen del contexto de página o de cualquier otro módulo.</span><span class="sxs-lookup"><span data-stu-id="42cde-109">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-text-block-modules-in-e-commerce"></a><span data-ttu-id="42cde-110">Ejemplos de módulos de bloque de texto en comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="42cde-110">Examples of text block modules in e-Commerce</span></span>

<span data-ttu-id="42cde-111">Los módulos de bloque de texto se pueden utilizar de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="42cde-111">Text block modules can be used in the following ways:</span></span>

* <span data-ttu-id="42cde-112">Para mostrar características de producto en una página de detalles de productos.</span><span class="sxs-lookup"><span data-stu-id="42cde-112">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="42cde-113">Para finalidad informativa en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="42cde-113">For informational purposes on any page.</span></span> <span data-ttu-id="42cde-114">Por ejemplo, pueden explicar los beneficios de programas de fidelización, describir las directivas de envío y devolución, responder a preguntas más frecuentes o proporcionar contenido de “acerca de nosotros”.</span><span class="sxs-lookup"><span data-stu-id="42cde-114">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="42cde-115">Para agregar mensajes personalizados en una página de detalles de productos.</span><span class="sxs-lookup"><span data-stu-id="42cde-115">To add custom messages on a product details page.</span></span> <span data-ttu-id="42cde-116">(por ejemplo, “Envío gratuito para pedidos superiores a 50 €").</span><span class="sxs-lookup"><span data-stu-id="42cde-116">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="42cde-117">Para declinaciones de responsabilidad y detalles de contacto sobre páginas de detalles de productos, páginas de finalización de compra y otras páginas (por ejemplo, "Los envíos y las directivas están sujetos a las directivas de la tienda”).</span><span class="sxs-lookup"><span data-stu-id="42cde-117">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

## <a name="text-block-module-properties"></a><span data-ttu-id="42cde-118">Propiedades de módulo de bloque de texto</span><span class="sxs-lookup"><span data-stu-id="42cde-118">Text block module properties</span></span>

| <span data-ttu-id="42cde-119">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="42cde-119">Property name</span></span>     | <span data-ttu-id="42cde-120">Valor</span><span class="sxs-lookup"><span data-stu-id="42cde-120">Value</span></span>                                            | <span data-ttu-id="42cde-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="42cde-121">Description</span></span> |
|-------------------|--------------------------------------------------|-------------|
| <span data-ttu-id="42cde-122">Texto enriquecido</span><span class="sxs-lookup"><span data-stu-id="42cde-122">Rich text</span></span>         | <span data-ttu-id="42cde-123">Texto enriquecido</span><span class="sxs-lookup"><span data-stu-id="42cde-123">Rich text</span></span>                                        | <span data-ttu-id="42cde-124">Texto de párrafo.</span><span class="sxs-lookup"><span data-stu-id="42cde-124">Paragraph text.</span></span> <span data-ttu-id="42cde-125">Se admiten algunas capacidades básicas de texto enriquecido, como negrita, subrayado y cursiva.</span><span class="sxs-lookup"><span data-stu-id="42cde-125">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |
| <span data-ttu-id="42cde-126">Nombre de clase personalizada</span><span class="sxs-lookup"><span data-stu-id="42cde-126">Custom class name</span></span> | <span data-ttu-id="42cde-127">Un nombre de clase de hojas de estilo en cascada (CSS)</span><span class="sxs-lookup"><span data-stu-id="42cde-127">A Cascading Style Sheets (CSS) class name</span></span>        | <span data-ttu-id="42cde-128">El nombre de una clase CSS personalizada que un desarrollador proporciona para aplicar formato a este módulo.</span><span class="sxs-lookup"><span data-stu-id="42cde-128">The name of a custom CSS class that a developer provides to format this module.</span></span> <span data-ttu-id="42cde-129">El nombre de la clase debe definirse en el paquete de temas.</span><span class="sxs-lookup"><span data-stu-id="42cde-129">The class name should be defined in the theme pack.</span></span> |
| <span data-ttu-id="42cde-130">Tamaño de fuente</span><span class="sxs-lookup"><span data-stu-id="42cde-130">Font size</span></span>         | <span data-ttu-id="42cde-131">**Pequeño**, **Mediano**, **Grande** o **Extragrande**</span><span class="sxs-lookup"><span data-stu-id="42cde-131">**Small**, **Medium**, **Large**, or **X-Large**</span></span> | <span data-ttu-id="42cde-132">El tamaño de fuente del contenido.</span><span class="sxs-lookup"><span data-stu-id="42cde-132">The font size of the content.</span></span> |

## <a name="add-a-text-block-module-to-a-page"></a><span data-ttu-id="42cde-133">Agregar un módulo de bloque de texto a una página</span><span class="sxs-lookup"><span data-stu-id="42cde-133">Add a text block module to a page</span></span>

<span data-ttu-id="42cde-134">Para agregar un módulo de bloque de texto a una nueva página y establecer las propiedades necesarias, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="42cde-134">To add a text block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="42cde-135">Cree una plantilla de página con el nombre **Plantilla de contenido**.</span><span class="sxs-lookup"><span data-stu-id="42cde-135">Create a page template that is named **Content template**.</span></span> 
1. <span data-ttu-id="42cde-136">En el espacio **Cuerpo**, agregue un módulo de **Página predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="42cde-136">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="42cde-137">Termine de editar la plantilla y publíquela.</span><span class="sxs-lookup"><span data-stu-id="42cde-137">Finish editing the template, and publish it.</span></span>
1. <span data-ttu-id="42cde-138">Use la plantilla de contenido que acaba de crear para crear una página que se llame **Página de contenido**.</span><span class="sxs-lookup"><span data-stu-id="42cde-138">Use the content template that you just created to create a page that is named **Content page**.</span></span>
1. <span data-ttu-id="42cde-139">En el espacio **Principal** de la página nueva, agregue un módulo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="42cde-139">In the **Main** slot of the new page, add a container module.</span></span>
1. <span data-ttu-id="42cde-140">En el panel de propiedades para el módulo de contenedor, establezca la propiedad **Ancho** en **Rellenar contenedor**.</span><span class="sxs-lookup"><span data-stu-id="42cde-140">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="42cde-141">Agregue un módulo de bloque de texto al módulo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="42cde-141">Add a text block module to the container module.</span></span> 
1. <span data-ttu-id="42cde-142">En el panel de propiedades del módulo de bloque de texto, agregue texto al campo **Texto enriquecido**.</span><span class="sxs-lookup"><span data-stu-id="42cde-142">In the property pane of the text block module, add text to the **Rich text** field.</span></span>
1. <span data-ttu-id="42cde-143">Termine de editar la página y publíquela.</span><span class="sxs-lookup"><span data-stu-id="42cde-143">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="42cde-144">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="42cde-144">Additional resources</span></span>

[<span data-ttu-id="42cde-145">Visión general de kit de inicio</span><span class="sxs-lookup"><span data-stu-id="42cde-145">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="42cde-146">Módulo de banner promocional</span><span class="sxs-lookup"><span data-stu-id="42cde-146">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="42cde-147">Módulo de carrusel</span><span class="sxs-lookup"><span data-stu-id="42cde-147">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="42cde-148">Módulo de bloque de contenido</span><span class="sxs-lookup"><span data-stu-id="42cde-148">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="42cde-149">Módulo de reproductor de vídeo</span><span class="sxs-lookup"><span data-stu-id="42cde-149">Video player module</span></span>](add-video-player.md)

