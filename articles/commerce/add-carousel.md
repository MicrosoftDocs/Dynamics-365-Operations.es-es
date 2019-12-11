---
title: Módulo de carrusel
description: En este tema se tratan los módulos de carrusel y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: c2c5adc8ab2e0330f7b07e5153fd8332ab0203e5
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785246"
---
# <a name="carousel-module"></a><span data-ttu-id="51e74-103">Módulo de carrusel</span><span class="sxs-lookup"><span data-stu-id="51e74-103">Carousel module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="51e74-104">En este tema se tratan los módulos de carrusel y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="51e74-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="51e74-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="51e74-105">Overview</span></span>

<span data-ttu-id="51e74-106">Un módulo de carrusel se usa para colocar artículos promocionales en un carrusel que los clientes puedan explorar.</span><span class="sxs-lookup"><span data-stu-id="51e74-106">A carousel module is used to put multiple promotional items in a carousel that customers can browse.</span></span> <span data-ttu-id="51e74-107">Es un módulo especial de contenedor que hospeda otros módulos.</span><span class="sxs-lookup"><span data-stu-id="51e74-107">It's a special container module that hosts other modules.</span></span> <span data-ttu-id="51e74-108">Por ejemplo, un minorista puede usar un módulo de carrusel en una página principal para mostrar productos o promociones nuevas.</span><span class="sxs-lookup"><span data-stu-id="51e74-108">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="51e74-109">Puede agregar los módulos de elemento principal y características dentro de un módulo de carrusel.</span><span class="sxs-lookup"><span data-stu-id="51e74-109">You can add hero and feature modules inside a carousel module.</span></span> <span data-ttu-id="51e74-110">Las propiedades del módulo de carrusel definen a continuación cómo se representan esos módulos.</span><span class="sxs-lookup"><span data-stu-id="51e74-110">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="51e74-111">Ejemplos de módulos de carrusel en comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="51e74-111">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="51e74-112">Un carrusel que tiene dentro varios módulos promocionales se puede usar en una página principal.</span><span class="sxs-lookup"><span data-stu-id="51e74-112">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="51e74-113">Un carrusel que tiene dentro varios módulos promocionales se puede usar en una página de detalles de producto.</span><span class="sxs-lookup"><span data-stu-id="51e74-113">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="51e74-114">Un carrusel se puede utilizar en cualquier página de marketing para promocionar varias promociones o productos.</span><span class="sxs-lookup"><span data-stu-id="51e74-114">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

## <a name="carousel-module-properties"></a><span data-ttu-id="51e74-115">Propiedades de módulo de carrusel</span><span class="sxs-lookup"><span data-stu-id="51e74-115">Carousel module properties</span></span>

| <span data-ttu-id="51e74-116">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="51e74-116">Property name</span></span>             | <span data-ttu-id="51e74-117">Valor</span><span class="sxs-lookup"><span data-stu-id="51e74-117">Value</span></span>                                | <span data-ttu-id="51e74-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="51e74-118">Description</span></span> |
|---------------------------|--------------------------------------|-------------|
| <span data-ttu-id="51e74-119">Reproducción automática</span><span class="sxs-lookup"><span data-stu-id="51e74-119">Autoplay</span></span>                  | <span data-ttu-id="51e74-120">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="51e74-120">**True** or **False**</span></span>                | <span data-ttu-id="51e74-121">Si el valor está establecido en **Verdadero**, la transición entre artículos dentro de carrusel se produce automáticamente.</span><span class="sxs-lookup"><span data-stu-id="51e74-121">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="51e74-122">Si el valor se establece en **Falso**, no se produce ninguna transición a menos que el cliente use el teclado o el mouse para ir de un artículo al siguiente.</span><span class="sxs-lookup"><span data-stu-id="51e74-122">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="51e74-123">Intervalo de transición de diapositivas</span><span class="sxs-lookup"><span data-stu-id="51e74-123">Slide transition interval</span></span> | <span data-ttu-id="51e74-124">Un valor en segundos</span><span class="sxs-lookup"><span data-stu-id="51e74-124">A value in seconds</span></span>                   | <span data-ttu-id="51e74-125">El intervalo para transiciones entre artículos.</span><span class="sxs-lookup"><span data-stu-id="51e74-125">The interval for transitions between items.</span></span> |
| <span data-ttu-id="51e74-126">Animación de transición</span><span class="sxs-lookup"><span data-stu-id="51e74-126">Transition animation</span></span>      | <span data-ttu-id="51e74-127">**Diapositiva** o **Atenuación**</span><span class="sxs-lookup"><span data-stu-id="51e74-127">**Slide** or **Fade**</span></span>                | <span data-ttu-id="51e74-128">El efecto de transición.</span><span class="sxs-lookup"><span data-stu-id="51e74-128">The transition effect.</span></span> |
| <span data-ttu-id="51e74-129">Ancho</span><span class="sxs-lookup"><span data-stu-id="51e74-129">Width</span></span>                     | <span data-ttu-id="51e74-130">**Ajustar contenedor** o **Rellenar pantalla**</span><span class="sxs-lookup"><span data-stu-id="51e74-130">**Fit container** or **Fill screen**</span></span> | <span data-ttu-id="51e74-131">Si el valor se establece en **Ajustar contenedor**, los elementos que se encuentran dentro del carrusel se limitan al ancho del carrusel.</span><span class="sxs-lookup"><span data-stu-id="51e74-131">If the value is set to **Fit container**, the items inside the carousel are restricted to the width of the carousel.</span></span> <span data-ttu-id="51e74-132">Si el valor se establece en **Rellenar pantalla**, los elementos no se limitan al ancho del carrusel pero pueden entrar en el modo de pantalla completa.</span><span class="sxs-lookup"><span data-stu-id="51e74-132">If the value is set to **Fill screen**, the items aren't restricted to the carousel width but can go into full-screen mode.</span></span> <span data-ttu-id="51e74-133">Puede cambiar el valor para lograr el diseño deseado.</span><span class="sxs-lookup"><span data-stu-id="51e74-133">You can change the value to achieve the desired layout.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="51e74-134">Agregar un módulo de carrusel a una página</span><span class="sxs-lookup"><span data-stu-id="51e74-134">Add a carousel module to a page</span></span>

<span data-ttu-id="51e74-135">Para agregar un módulo de carrusel a una página nueva y establecer las propiedades necesarias, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="51e74-135">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="51e74-136">Cree una plantilla de página con el nombre **plantilla de carrusel**.</span><span class="sxs-lookup"><span data-stu-id="51e74-136">Create a page template that is named **carousel template**.</span></span>
1. <span data-ttu-id="51e74-137">En el espacio **Principal** de la página predeterminada, agregue un módulo de carrusel.</span><span class="sxs-lookup"><span data-stu-id="51e74-137">In the **Main** slot of the default page, add a carousel module.</span></span>
1. <span data-ttu-id="51e74-138">Agregar un módulo de elemento principal al módulo de carrusel.</span><span class="sxs-lookup"><span data-stu-id="51e74-138">Add a hero module to the carousel module.</span></span>
1. <span data-ttu-id="51e74-139">Agregar un módulo de características al módulo de carrusel.</span><span class="sxs-lookup"><span data-stu-id="51e74-139">Add a feature module to the carousel module.</span></span>
1. <span data-ttu-id="51e74-140">Proteja la plantilla y publíquela.</span><span class="sxs-lookup"><span data-stu-id="51e74-140">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="51e74-141">Use la plantilla de carrusel que acaba de crear para crear una página que se llame **página de carrusel**.</span><span class="sxs-lookup"><span data-stu-id="51e74-141">Use the carousel template that you just created to create a page that is named **carousel page**.</span></span>
1. <span data-ttu-id="51e74-142">En el espacio **Principal** de la página nueva, agregue un módulo de carrusel.</span><span class="sxs-lookup"><span data-stu-id="51e74-142">In the **Main** slot of the new page, add a carousel module.</span></span>
1. <span data-ttu-id="51e74-143">Establezca la propiedad **Ancho** del módulo de carrusel **Rellenar pantalla**.</span><span class="sxs-lookup"><span data-stu-id="51e74-143">Set the **Width** property of the carousel module to **Fill screen**.</span></span> 
1. <span data-ttu-id="51e74-144">Establezca la propiedad **Animación de transición** en **Diapositiva**.</span><span class="sxs-lookup"><span data-stu-id="51e74-144">Set the **Transition animation** property to **Slide**.</span></span>
1. <span data-ttu-id="51e74-145">Agregar un módulo de elemento principal al módulo de carrusel.</span><span class="sxs-lookup"><span data-stu-id="51e74-145">Add a hero module to the carousel module.</span></span>
1. <span data-ttu-id="51e74-146">En el módulo de elemento principal, agregue una imagen y una encabezado y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="51e74-146">In the hero module, add an image and a heading, and then select **Save**.</span></span>
1. <span data-ttu-id="51e74-147">Agregar un módulo de características al módulo de carrusel.</span><span class="sxs-lookup"><span data-stu-id="51e74-147">Add a feature module to the carousel module.</span></span>
1. <span data-ttu-id="51e74-148">En el módulo de características, agregue una imagen, un encabezado y un párrafo de texto.</span><span class="sxs-lookup"><span data-stu-id="51e74-148">In the feature module, add an image, a heading, and a paragraph of text.</span></span>
1. <span data-ttu-id="51e74-149">Guarde la página y obtenga una vista previa de ella.</span><span class="sxs-lookup"><span data-stu-id="51e74-149">Save and preview the page.</span></span> <span data-ttu-id="51e74-150">La página debe mostrar un carrusel con dos módulos dentro (un módulo de elemento principal y un módulo de características).</span><span class="sxs-lookup"><span data-stu-id="51e74-150">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="51e74-151">Puede cambiar las propiedades adicionales para que los módulos de carrusel, elemento principal y características logren el efecto deseado.</span><span class="sxs-lookup"><span data-stu-id="51e74-151">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="51e74-152">Proteja la página y publíquela.</span><span class="sxs-lookup"><span data-stu-id="51e74-152">Check in the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="51e74-153">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="51e74-153">Additional resources</span></span>

[<span data-ttu-id="51e74-154">Visión general de kit de inicio</span><span class="sxs-lookup"><span data-stu-id="51e74-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="51e74-155">Módulo de alerta</span><span class="sxs-lookup"><span data-stu-id="51e74-155">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="51e74-156">Módulo de bloque de enriquecimiento de contenido</span><span class="sxs-lookup"><span data-stu-id="51e74-156">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="51e74-157">Módulo de sustitución de contenido</span><span class="sxs-lookup"><span data-stu-id="51e74-157">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="51e74-158">Módulo de característica</span><span class="sxs-lookup"><span data-stu-id="51e74-158">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="51e74-159">Módulo de elemento principal</span><span class="sxs-lookup"><span data-stu-id="51e74-159">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="51e74-160">Módulo de reproductor de vídeo</span><span class="sxs-lookup"><span data-stu-id="51e74-160">Video player module</span></span>](add-video-player.md)
