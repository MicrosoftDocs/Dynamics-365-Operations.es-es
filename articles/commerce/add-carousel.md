---
title: Módulo de carrusel
description: En este tema se tratan los módulos de carrusel y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: 10ff0cd566a1a8d89ccadce9571dafc5a592520b
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2020
ms.locfileid: "3620995"
---
# <a name="carousel-module"></a><span data-ttu-id="cad59-103">Módulo de carrusel</span><span class="sxs-lookup"><span data-stu-id="cad59-103">Carousel module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cad59-104">En este tema se tratan los módulos de carrusel y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="cad59-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="cad59-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="cad59-105">Overview</span></span>

<span data-ttu-id="cad59-106">Un módulo de carrusel sirve para colocar artículos promocionales (incluidas imágenes enriquecidas) en un banner de carrusel giratorio que los clientes pueden explorar.</span><span class="sxs-lookup"><span data-stu-id="cad59-106">A carousel module is used to put multiple promotional items (including rich images) in a rotating carousel banner that customers can browse.</span></span> <span data-ttu-id="cad59-107">Por ejemplo, un minorista puede usar un módulo de carrusel en una página principal para mostrar productos o promociones nuevas.</span><span class="sxs-lookup"><span data-stu-id="cad59-107">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="cad59-108">Puede agregar los módulos de bloque de contenido dentro de un módulo de carrusel.</span><span class="sxs-lookup"><span data-stu-id="cad59-108">You can add content block modules inside a carousel module.</span></span> <span data-ttu-id="cad59-109">Las propiedades del módulo de carrusel definen a continuación cómo se representan esos módulos.</span><span class="sxs-lookup"><span data-stu-id="cad59-109">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="cad59-110">Ejemplos de módulos de carrusel en comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="cad59-110">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="cad59-111">Un carrusel que tiene dentro varios módulos promocionales se puede usar en una página principal.</span><span class="sxs-lookup"><span data-stu-id="cad59-111">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="cad59-112">Un carrusel que tiene dentro varios módulos promocionales se puede usar en una página de detalles de producto.</span><span class="sxs-lookup"><span data-stu-id="cad59-112">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="cad59-113">Un carrusel se puede utilizar en cualquier página de marketing para promocionar varias promociones o productos.</span><span class="sxs-lookup"><span data-stu-id="cad59-113">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

<span data-ttu-id="cad59-114">La siguiente imagen muestra un ejemplo de un módulo de carrusel utilizado en una página principal.</span><span class="sxs-lookup"><span data-stu-id="cad59-114">The following image shows an example of a carousel module that is used on a home page.</span></span> <span data-ttu-id="cad59-115">Este módulo de carrusel contiene múltiples elementos de bloque de contenido.</span><span class="sxs-lookup"><span data-stu-id="cad59-115">This carousel module contains multiple content block items.</span></span>

![Ejemplo de módulo de carrusel](./media/Hero.PNG)

## <a name="carousel-module-properties"></a><span data-ttu-id="cad59-117">Propiedades de módulo de carrusel</span><span class="sxs-lookup"><span data-stu-id="cad59-117">Carousel module properties</span></span>

| <span data-ttu-id="cad59-118">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="cad59-118">Property name</span></span>             | <span data-ttu-id="cad59-119">Valor</span><span class="sxs-lookup"><span data-stu-id="cad59-119">Value</span></span>                 | <span data-ttu-id="cad59-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="cad59-120">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="cad59-121">Reproducción automática</span><span class="sxs-lookup"><span data-stu-id="cad59-121">Autoplay</span></span>                  | <span data-ttu-id="cad59-122">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="cad59-122">**True** or **False**</span></span> | <span data-ttu-id="cad59-123">Si el valor está establecido en **Verdadero**, la transición entre artículos dentro de carrusel se produce automáticamente.</span><span class="sxs-lookup"><span data-stu-id="cad59-123">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="cad59-124">Si el valor se establece en **Falso**, no se produce ninguna transición a menos que el cliente use el teclado o el mouse para ir de un artículo al siguiente.</span><span class="sxs-lookup"><span data-stu-id="cad59-124">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="cad59-125">Intervalo de transición de diapositivas</span><span class="sxs-lookup"><span data-stu-id="cad59-125">Slide transition interval</span></span> | <span data-ttu-id="cad59-126">Un valor en segundos</span><span class="sxs-lookup"><span data-stu-id="cad59-126">A value in seconds</span></span>    | <span data-ttu-id="cad59-127">El intervalo para transiciones entre artículos.</span><span class="sxs-lookup"><span data-stu-id="cad59-127">The interval for transitions between items.</span></span> |
| <span data-ttu-id="cad59-128">Tipo de transacción</span><span class="sxs-lookup"><span data-stu-id="cad59-128">Transition type</span></span>           | <span data-ttu-id="cad59-129">**Diapositiva** o **Atenuación**</span><span class="sxs-lookup"><span data-stu-id="cad59-129">**Slide** or **Fade**</span></span> | <span data-ttu-id="cad59-130">El efecto de transición entre elementos.</span><span class="sxs-lookup"><span data-stu-id="cad59-130">The transition effect between items.</span></span> |
| <span data-ttu-id="cad59-131">Ocultar impulsor de carrusel</span><span class="sxs-lookup"><span data-stu-id="cad59-131">Hide carousel flipper</span></span>     | <span data-ttu-id="cad59-132">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="cad59-132">**True** or **False**</span></span> | <span data-ttu-id="cad59-133">Si el valor se establece en **Verdadero**, la aleta del carrusel y el indicador de secuencia están ocultos.</span><span class="sxs-lookup"><span data-stu-id="cad59-133">If the value is set to **True**, the carousel flipper and sequence indicator are hidden.</span></span> |
| <span data-ttu-id="cad59-134">Permitir descartar carrusel</span><span class="sxs-lookup"><span data-stu-id="cad59-134">Allow carousel dismiss</span></span>    | <span data-ttu-id="cad59-135">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="cad59-135">**True** or **False**</span></span> | <span data-ttu-id="cad59-136">Si el valor se establece en **Verdadero**, los usuarios pueden descartar el carrusel.</span><span class="sxs-lookup"><span data-stu-id="cad59-136">If the value is set to **True**, users can dismiss the carousel.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="cad59-137">Agregar un módulo de carrusel a una página</span><span class="sxs-lookup"><span data-stu-id="cad59-137">Add a carousel module to a page</span></span>

<span data-ttu-id="cad59-138">Para agregar un módulo de carrusel a una página nueva y establecer las propiedades necesarias, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="cad59-138">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="cad59-139">Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.</span><span class="sxs-lookup"><span data-stu-id="cad59-139">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="cad59-140">En el cuadro de diálogo **Nueva plantilla**, debajo de **Nombre de la plantilla**, introduzca **Plantilla de carrusel** y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cad59-140">In the **New Template** dialog box, under **Template Name**, enter **Carousel template**, and then select **OK**.</span></span>
1. <span data-ttu-id="cad59-141">En el espacio **Cuerpo**, agregue un módulo de **Página predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="cad59-141">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="cad59-142">Seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="cad59-142">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>  
1. <span data-ttu-id="cad59-143">Use la plantilla de carrusel que acaba de crear para crear una página que se llame **página de carrusel**.</span><span class="sxs-lookup"><span data-stu-id="cad59-143">Use the carousel template that you just created to create a page that is named **Carousel page**.</span></span>
1. <span data-ttu-id="cad59-144">En el espacio **Principal** de la página nueva, agregue un módulo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="cad59-144">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="cad59-145">En el panel de la derecha, establezca el valor de **Ancho** para **Rellenar pantalla**.</span><span class="sxs-lookup"><span data-stu-id="cad59-145">In the pane on the right, set the **Width** value to **Fill Screen**.</span></span>
1. <span data-ttu-id="cad59-146">En **Esquema de la página**, agregue un módulo de carrusel al módulo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="cad59-146">Under **Page Outline**, add a carousel module to the container module.</span></span>
1. <span data-ttu-id="cad59-147">Agregue un módulo de bloque de contenido al módulo de carrusel.</span><span class="sxs-lookup"><span data-stu-id="cad59-147">Add a content block module to the carousel module.</span></span> <span data-ttu-id="cad59-148">Establezca las propiedades del módulo de bloque de contenido proporcionando **Encabezado**, **Vínculo**, **Diseño** y otras propiedades.</span><span class="sxs-lookup"><span data-stu-id="cad59-148">Set the properties of the content block module by providing **Heading**, **Link**, **Layout**, and other properties.</span></span>
1. <span data-ttu-id="cad59-149">Agregue y configure otro módulo de bloque de contenido.</span><span class="sxs-lookup"><span data-stu-id="cad59-149">Add and configure another content block module.</span></span>
1. <span data-ttu-id="cad59-150">Establezca propiedades adicionales para el módulo de carrusel según corresponda.</span><span class="sxs-lookup"><span data-stu-id="cad59-150">Set additional properties for the carousel module as you require.</span></span>
1. <span data-ttu-id="cad59-151">Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.</span><span class="sxs-lookup"><span data-stu-id="cad59-151">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="cad59-152">La página debe mostrar un carrusel con dos módulos dentro (un módulo de elemento principal y un módulo de características).</span><span class="sxs-lookup"><span data-stu-id="cad59-152">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="cad59-153">Puede cambiar las propiedades adicionales para que los módulos de carrusel, elemento principal y características logren el efecto deseado.</span><span class="sxs-lookup"><span data-stu-id="cad59-153">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="cad59-154">Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="cad59-154">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cad59-155">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="cad59-155">Additional resources</span></span>

[<span data-ttu-id="cad59-156">Visión general de kit de inicio</span><span class="sxs-lookup"><span data-stu-id="cad59-156">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="cad59-157">Módulo de banner promocional</span><span class="sxs-lookup"><span data-stu-id="cad59-157">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="cad59-158">Módulo de bloque de texto</span><span class="sxs-lookup"><span data-stu-id="cad59-158">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="cad59-159">Módulo de bloque de contenido</span><span class="sxs-lookup"><span data-stu-id="cad59-159">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="cad59-160">Módulo de reproductor de vídeo</span><span class="sxs-lookup"><span data-stu-id="cad59-160">Video player module</span></span>](add-video-player.md)
