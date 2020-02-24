---
title: Módulo de carrusel
description: En este tema se tratan los módulos de carrusel y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: f279d7db0a92df9e64b1d3f6ca01c65ca1478d79
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025790"
---
# <a name="carousel-module"></a><span data-ttu-id="bd3d4-103">Módulo de carrusel</span><span class="sxs-lookup"><span data-stu-id="bd3d4-103">Carousel module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="bd3d4-104">En este tema se tratan los módulos de carrusel y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="bd3d4-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="bd3d4-105">Overview</span></span>

<span data-ttu-id="bd3d4-106">Un módulo de carrusel sirve para colocar artículos promocionales (incluidas imágenes enriquecidas) en un banner de carrusel giratorio que los clientes pueden explorar.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-106">A carousel module is used to put multiple promotional items (including rich images) in a rotating carousel banner that customers can browse.</span></span> <span data-ttu-id="bd3d4-107">Por ejemplo, un minorista puede usar un módulo de carrusel en una página principal para mostrar productos o promociones nuevas.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-107">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="bd3d4-108">Puede agregar los módulos de bloque de contenido dentro de un módulo de carrusel.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-108">You can add content block modules inside a carousel module.</span></span> <span data-ttu-id="bd3d4-109">Las propiedades del módulo de carrusel definen a continuación cómo se representan esos módulos.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-109">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="bd3d4-110">Ejemplos de módulos de carrusel en comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="bd3d4-110">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="bd3d4-111">Un carrusel que tiene dentro varios módulos promocionales se puede usar en una página principal.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-111">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="bd3d4-112">Un carrusel que tiene dentro varios módulos promocionales se puede usar en una página de detalles de producto.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-112">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="bd3d4-113">Un carrusel se puede utilizar en cualquier página de marketing para promocionar varias promociones o productos.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-113">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

## <a name="carousel-module-properties"></a><span data-ttu-id="bd3d4-114">Propiedades de módulo de carrusel</span><span class="sxs-lookup"><span data-stu-id="bd3d4-114">Carousel module properties</span></span>

| <span data-ttu-id="bd3d4-115">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="bd3d4-115">Property name</span></span>             | <span data-ttu-id="bd3d4-116">Valor</span><span class="sxs-lookup"><span data-stu-id="bd3d4-116">Value</span></span>                 | <span data-ttu-id="bd3d4-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd3d4-117">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="bd3d4-118">Reproducción automática</span><span class="sxs-lookup"><span data-stu-id="bd3d4-118">Autoplay</span></span>                  | <span data-ttu-id="bd3d4-119">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="bd3d4-119">**True** or **False**</span></span> | <span data-ttu-id="bd3d4-120">Si el valor está establecido en **Verdadero**, la transición entre artículos dentro de carrusel se produce automáticamente.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-120">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="bd3d4-121">Si el valor se establece en **Falso**, no se produce ninguna transición a menos que el cliente use el teclado o el mouse para ir de un artículo al siguiente.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-121">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="bd3d4-122">Intervalo de transición de diapositivas</span><span class="sxs-lookup"><span data-stu-id="bd3d4-122">Slide transition interval</span></span> | <span data-ttu-id="bd3d4-123">Un valor en segundos</span><span class="sxs-lookup"><span data-stu-id="bd3d4-123">A value in seconds</span></span>    | <span data-ttu-id="bd3d4-124">El intervalo para transiciones entre artículos.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-124">The interval for transitions between items.</span></span> |
| <span data-ttu-id="bd3d4-125">Tipo de transacción</span><span class="sxs-lookup"><span data-stu-id="bd3d4-125">Transition type</span></span>           | <span data-ttu-id="bd3d4-126">**Diapositiva** o **Atenuación**</span><span class="sxs-lookup"><span data-stu-id="bd3d4-126">**Slide** or **Fade**</span></span> | <span data-ttu-id="bd3d4-127">El efecto de transición entre elementos.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-127">The transition effect between items.</span></span> |
| <span data-ttu-id="bd3d4-128">Ocultar impulsor de carrusel</span><span class="sxs-lookup"><span data-stu-id="bd3d4-128">Hide carousel flipper</span></span>     | <span data-ttu-id="bd3d4-129">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="bd3d4-129">**True** or **False**</span></span> | <span data-ttu-id="bd3d4-130">Si el valor se establece en **Verdadero**, la aleta del carrusel y el indicador de secuencia están ocultos.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-130">If the value is set to **True**, the carousel flipper and sequence indicator are hidden.</span></span> |
| <span data-ttu-id="bd3d4-131">Permitir descartar carrusel</span><span class="sxs-lookup"><span data-stu-id="bd3d4-131">Allow carousel dismiss</span></span>    | <span data-ttu-id="bd3d4-132">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="bd3d4-132">**True** or **False**</span></span> | <span data-ttu-id="bd3d4-133">Si el valor se establece en **Verdadero**, los usuarios pueden descartar el carrusel.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-133">If the value is set to **True**, users can dismiss the carousel.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="bd3d4-134">Agregar un módulo de carrusel a una página</span><span class="sxs-lookup"><span data-stu-id="bd3d4-134">Add a carousel module to a page</span></span>

<span data-ttu-id="bd3d4-135">Para agregar un módulo de carrusel a una página nueva y establecer las propiedades necesarias, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-135">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="bd3d4-136">Cree una plantilla de página con el nombre **plantilla de carrusel**.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-136">Create a page template that is named **carousel template**.</span></span>
1. <span data-ttu-id="bd3d4-137">En el espacio **Cuerpo**, agregue un módulo de **Página predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-137">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="bd3d4-138">Proteja la plantilla y publíquela.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-138">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="bd3d4-139">Use la plantilla de carrusel que acaba de crear para crear una página que se llame **página de carrusel**.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-139">Use the carousel template that you just created to create a page that is named **carousel page**.</span></span>
1. <span data-ttu-id="bd3d4-140">En el espacio **Principal** de la página nueva, agregue un módulo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-140">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="bd3d4-141">En el panel de la derecha, establezca el valor de **Ancho** para **Rellenar pantalla**.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-141">In the pane on the right, set the **Width** value to **Fill Screen**.</span></span>
1. <span data-ttu-id="bd3d4-142">En **Esquema de la página**, agregue un módulo de carrusel al módulo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-142">Under **Page Outline**, add a carousel module to the container module.</span></span>
1. <span data-ttu-id="bd3d4-143">Agregue un módulo de bloque de contenido al módulo de carrusel.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-143">Add a content block module to the carousel module.</span></span> <span data-ttu-id="bd3d4-144">Establezca las propiedades del módulo de bloque de contenido proporcionando **Encabezado**, **Vínculo**, **Diseño** y otras propiedades.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-144">Set the properties of the content block module by providing **Heading**, **Link**, **Layout**, and other properties.</span></span>
1. <span data-ttu-id="bd3d4-145">Agregue y configure otro módulo de bloque de contenido.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-145">Add and configure another content block module.</span></span>
1. <span data-ttu-id="bd3d4-146">Establezca propiedades adicionales para el módulo de carrusel según corresponda.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-146">Set additional properties for the carousel module as you require.</span></span>
1. <span data-ttu-id="bd3d4-147">Guarde la página y obtenga una vista previa de ella.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-147">Save and preview the page.</span></span> <span data-ttu-id="bd3d4-148">La página debe mostrar un carrusel con dos módulos dentro (un módulo de elemento principal y un módulo de características).</span><span class="sxs-lookup"><span data-stu-id="bd3d4-148">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="bd3d4-149">Puede cambiar las propiedades adicionales para que los módulos de carrusel, elemento principal y características logren el efecto deseado.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-149">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="bd3d4-150">Termine de editar la página y publíquela.</span><span class="sxs-lookup"><span data-stu-id="bd3d4-150">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bd3d4-151">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="bd3d4-151">Additional resources</span></span>

[<span data-ttu-id="bd3d4-152">Visión general de kit de inicio</span><span class="sxs-lookup"><span data-stu-id="bd3d4-152">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="bd3d4-153">Módulo de banner promocional</span><span class="sxs-lookup"><span data-stu-id="bd3d4-153">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="bd3d4-154">Módulo de bloque de texto</span><span class="sxs-lookup"><span data-stu-id="bd3d4-154">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="bd3d4-155">Módulo de bloque de contenido</span><span class="sxs-lookup"><span data-stu-id="bd3d4-155">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="bd3d4-156">Módulo de reproductor de vídeo</span><span class="sxs-lookup"><span data-stu-id="bd3d4-156">Video player module</span></span>](add-video-player.md)
