---
title: Módulo de carrusel
description: En este tema se tratan los módulos de carrusel y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 5bc2227e08dbbf5f76a37180114e5affff131658
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797896"
---
# <a name="carousel-module"></a><span data-ttu-id="e57cc-103">Módulo de carrusel</span><span class="sxs-lookup"><span data-stu-id="e57cc-103">Carousel module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e57cc-104">En este tema se tratan los módulos de carrusel y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e57cc-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="e57cc-105">Un módulo de carrusel sirve para colocar artículos promocionales (incluidas imágenes enriquecidas) en un banner de carrusel giratorio que los clientes pueden explorar.</span><span class="sxs-lookup"><span data-stu-id="e57cc-105">A carousel module is used to put multiple promotional items (including rich images) in a rotating carousel banner that customers can browse.</span></span> <span data-ttu-id="e57cc-106">Por ejemplo, un minorista puede usar un módulo de carrusel en una página principal para mostrar productos o promociones nuevas.</span><span class="sxs-lookup"><span data-stu-id="e57cc-106">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="e57cc-107">Puede agregar los módulos de bloque de contenido dentro de un módulo de carrusel.</span><span class="sxs-lookup"><span data-stu-id="e57cc-107">You can add content block modules inside a carousel module.</span></span> <span data-ttu-id="e57cc-108">Las propiedades del módulo de carrusel definen a continuación cómo se representan esos módulos.</span><span class="sxs-lookup"><span data-stu-id="e57cc-108">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="e57cc-109">Ejemplos de módulos de carrusel en comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="e57cc-109">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="e57cc-110">Un carrusel que tiene dentro varios módulos promocionales se puede usar en una página principal.</span><span class="sxs-lookup"><span data-stu-id="e57cc-110">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="e57cc-111">Un carrusel que tiene dentro varios módulos promocionales se puede usar en una página de detalles de producto.</span><span class="sxs-lookup"><span data-stu-id="e57cc-111">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="e57cc-112">Un carrusel se puede utilizar en cualquier página de marketing para promocionar varias promociones o productos.</span><span class="sxs-lookup"><span data-stu-id="e57cc-112">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

<span data-ttu-id="e57cc-113">La siguiente imagen muestra un ejemplo de un módulo de carrusel utilizado en una página principal.</span><span class="sxs-lookup"><span data-stu-id="e57cc-113">The following image shows an example of a carousel module that is used on a home page.</span></span> <span data-ttu-id="e57cc-114">Este módulo de carrusel contiene múltiples elementos de bloque de contenido.</span><span class="sxs-lookup"><span data-stu-id="e57cc-114">This carousel module contains multiple content block items.</span></span>

![Ejemplo de módulo de carrusel](./media/Hero.PNG)

## <a name="carousel-module-properties"></a><span data-ttu-id="e57cc-116">Propiedades de módulo de carrusel</span><span class="sxs-lookup"><span data-stu-id="e57cc-116">Carousel module properties</span></span>

| <span data-ttu-id="e57cc-117">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="e57cc-117">Property name</span></span>             | <span data-ttu-id="e57cc-118">Valor</span><span class="sxs-lookup"><span data-stu-id="e57cc-118">Value</span></span>                 | <span data-ttu-id="e57cc-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="e57cc-119">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="e57cc-120">Reproducción automática</span><span class="sxs-lookup"><span data-stu-id="e57cc-120">Autoplay</span></span>                  | <span data-ttu-id="e57cc-121">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="e57cc-121">**True** or **False**</span></span> | <span data-ttu-id="e57cc-122">Si el valor está establecido en **Verdadero**, la transición entre artículos dentro de carrusel se produce automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e57cc-122">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="e57cc-123">Si el valor se establece en **Falso**, no se produce ninguna transición a menos que el cliente use el teclado o el mouse para ir de un artículo al siguiente.</span><span class="sxs-lookup"><span data-stu-id="e57cc-123">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="e57cc-124">Intervalo de transición de diapositivas</span><span class="sxs-lookup"><span data-stu-id="e57cc-124">Slide transition interval</span></span> | <span data-ttu-id="e57cc-125">Un valor en segundos</span><span class="sxs-lookup"><span data-stu-id="e57cc-125">A value in seconds</span></span>    | <span data-ttu-id="e57cc-126">El intervalo para transiciones entre artículos.</span><span class="sxs-lookup"><span data-stu-id="e57cc-126">The interval for transitions between items.</span></span> |
| <span data-ttu-id="e57cc-127">Tipo de transacción</span><span class="sxs-lookup"><span data-stu-id="e57cc-127">Transition type</span></span>           | <span data-ttu-id="e57cc-128">**Diapositiva** o **Atenuación**</span><span class="sxs-lookup"><span data-stu-id="e57cc-128">**Slide** or **Fade**</span></span> | <span data-ttu-id="e57cc-129">El efecto de transición entre elementos.</span><span class="sxs-lookup"><span data-stu-id="e57cc-129">The transition effect between items.</span></span> |
| <span data-ttu-id="e57cc-130">Ocultar impulsor de carrusel</span><span class="sxs-lookup"><span data-stu-id="e57cc-130">Hide carousel flipper</span></span>     | <span data-ttu-id="e57cc-131">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="e57cc-131">**True** or **False**</span></span> | <span data-ttu-id="e57cc-132">Si el valor se establece en **Verdadero**, la aleta del carrusel y el indicador de secuencia están ocultos.</span><span class="sxs-lookup"><span data-stu-id="e57cc-132">If the value is set to **True**, the carousel flipper and sequence indicator are hidden.</span></span> |
| <span data-ttu-id="e57cc-133">Permitir descartar carrusel</span><span class="sxs-lookup"><span data-stu-id="e57cc-133">Allow carousel dismiss</span></span>    | <span data-ttu-id="e57cc-134">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="e57cc-134">**True** or **False**</span></span> | <span data-ttu-id="e57cc-135">Si el valor se establece en **Verdadero**, los usuarios pueden descartar el carrusel.</span><span class="sxs-lookup"><span data-stu-id="e57cc-135">If the value is set to **True**, users can dismiss the carousel.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="e57cc-136">Agregar un módulo de carrusel a una página</span><span class="sxs-lookup"><span data-stu-id="e57cc-136">Add a carousel module to a page</span></span>

<span data-ttu-id="e57cc-137">Para agregar un módulo de carrusel a una página nueva y establecer las propiedades necesarias, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e57cc-137">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="e57cc-138">Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.</span><span class="sxs-lookup"><span data-stu-id="e57cc-138">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="e57cc-139">En el cuadro de diálogo **Nueva plantilla**, debajo de **Nombre de la plantilla**, introduzca **Plantilla de carrusel** y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e57cc-139">In the **New Template** dialog box, under **Template Name**, enter **Carousel template**, and then select **OK**.</span></span>
1. <span data-ttu-id="e57cc-140">En el espacio **Cuerpo**, agregue un módulo de **Página predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="e57cc-140">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="e57cc-141">Seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="e57cc-141">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>  
1. <span data-ttu-id="e57cc-142">Use la plantilla de carrusel que acaba de crear para crear una página que se llame **página de carrusel**.</span><span class="sxs-lookup"><span data-stu-id="e57cc-142">Use the carousel template that you just created to create a page that is named **Carousel page**.</span></span>
1. <span data-ttu-id="e57cc-143">En el espacio **Principal** de la página nueva, agregue un módulo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="e57cc-143">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="e57cc-144">En el panel de la derecha, establezca el valor de **Ancho** para **Rellenar pantalla**.</span><span class="sxs-lookup"><span data-stu-id="e57cc-144">In the pane on the right, set the **Width** value to **Fill Screen**.</span></span>
1. <span data-ttu-id="e57cc-145">En **Esquema de la página**, agregue un módulo de carrusel al módulo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="e57cc-145">Under **Page Outline**, add a carousel module to the container module.</span></span>
1. <span data-ttu-id="e57cc-146">Agregue un módulo de bloque de contenido al módulo de carrusel.</span><span class="sxs-lookup"><span data-stu-id="e57cc-146">Add a content block module to the carousel module.</span></span> <span data-ttu-id="e57cc-147">Establezca las propiedades del módulo de bloque de contenido proporcionando **Encabezado**, **Vínculo**, **Diseño** y otras propiedades.</span><span class="sxs-lookup"><span data-stu-id="e57cc-147">Set the properties of the content block module by providing **Heading**, **Link**, **Layout**, and other properties.</span></span>
1. <span data-ttu-id="e57cc-148">Agregue y configure otro módulo de bloque de contenido.</span><span class="sxs-lookup"><span data-stu-id="e57cc-148">Add and configure another content block module.</span></span>
1. <span data-ttu-id="e57cc-149">Establezca propiedades adicionales para el módulo de carrusel según corresponda.</span><span class="sxs-lookup"><span data-stu-id="e57cc-149">Set additional properties for the carousel module as you require.</span></span>
1. <span data-ttu-id="e57cc-150">Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.</span><span class="sxs-lookup"><span data-stu-id="e57cc-150">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="e57cc-151">La página debe mostrar un carrusel con dos módulos dentro (un módulo de elemento principal y un módulo de características).</span><span class="sxs-lookup"><span data-stu-id="e57cc-151">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="e57cc-152">Puede cambiar las propiedades adicionales para que los módulos de carrusel, elemento principal y características logren el efecto deseado.</span><span class="sxs-lookup"><span data-stu-id="e57cc-152">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="e57cc-153">Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="e57cc-153">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e57cc-154">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e57cc-154">Additional resources</span></span>

[<span data-ttu-id="e57cc-155">Visión general de la biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="e57cc-155">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="e57cc-156">Módulo de banner promocional</span><span class="sxs-lookup"><span data-stu-id="e57cc-156">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="e57cc-157">Módulo de bloque de texto</span><span class="sxs-lookup"><span data-stu-id="e57cc-157">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="e57cc-158">Módulo de bloque de contenido</span><span class="sxs-lookup"><span data-stu-id="e57cc-158">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="e57cc-159">Módulo de reproductor de vídeo</span><span class="sxs-lookup"><span data-stu-id="e57cc-159">Video player module</span></span>](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]