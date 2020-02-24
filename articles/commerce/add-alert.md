---
title: Módulo de banner promocional
description: En este tema se tratan los módulos de banner promocional y se describe la forma de agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: da5e220e4578d1064eb7b627b441d3f585b3c095
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025629"
---
# <a name="promo-banner-module"></a><span data-ttu-id="64ea7-103">Módulo de banner promocional</span><span class="sxs-lookup"><span data-stu-id="64ea7-103">Promo banner module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="64ea7-104">En este tema se tratan los módulos de banner promocional y se describe la forma de agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="64ea7-104">This topic covers promo banner modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="64ea7-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="64ea7-105">Overview</span></span>

<span data-ttu-id="64ea7-106">Los módulos de banner promocional se usan para mostrar mensajes informativos en línea en una página.</span><span class="sxs-lookup"><span data-stu-id="64ea7-106">Promo banner modules are used to show inline informational messages on a page.</span></span> <span data-ttu-id="64ea7-107">Se pueden utilizar para mostrar las promociones en todo el sitio que aparecen en todas las páginas de un sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="64ea7-107">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="64ea7-108">Los módulos de banner promocional admiten un mensaje de texto y un vínculo.</span><span class="sxs-lookup"><span data-stu-id="64ea7-108">Promo banner modules support a text message and a link.</span></span> <span data-ttu-id="64ea7-109">Si se agregan varios mensajes a un módulo de banner promocional, se convierte en un banner de carrusel giratorio que permite a los clientes ver todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="64ea7-109">If multiple messages are added to a promo banner module, it becomes a rotating carousel banner that lets customers cycle through all the messages.</span></span> 

<span data-ttu-id="64ea7-110">Los módulos de banner promocional se controlan con datos desde el sistema de gestión de contenidos (CMS) y se pueden colocar en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="64ea7-110">Promo banner modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a><span data-ttu-id="64ea7-111">Ejemplos de uso de banners promocionales en comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="64ea7-111">Usage examples of promo banners in e-Commerce</span></span>

<span data-ttu-id="64ea7-112">Los banners promocionales se pueden usar en el encabezado del sitio para mostrar promociones o mensajes en todo el sitio, como en los siguientes ejemplos.</span><span class="sxs-lookup"><span data-stu-id="64ea7-112">Promo banners can be used in the site header to show site-wide promotions or messages, as in the following examples.</span></span>

<span data-ttu-id="64ea7-113">“La venta anual finaliza en 10 días”</span><span class="sxs-lookup"><span data-stu-id="64ea7-113">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="64ea7-114">“Ahorre a lo grande con la oferta de la vuelta al cole.</span><span class="sxs-lookup"><span data-stu-id="64ea7-114">"Save big with back to school sale.</span></span> <span data-ttu-id="64ea7-115">Compre ahora."</span><span class="sxs-lookup"><span data-stu-id="64ea7-115">Shop Now."</span></span>

## <a name="promo-banner-module-properties"></a><span data-ttu-id="64ea7-116">Propiedades del módulo de banner promocional</span><span class="sxs-lookup"><span data-stu-id="64ea7-116">Promo banner module properties</span></span>

| <span data-ttu-id="64ea7-117">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="64ea7-117">Property name</span></span>             | <span data-ttu-id="64ea7-118">Valor</span><span class="sxs-lookup"><span data-stu-id="64ea7-118">Value</span></span>                              | <span data-ttu-id="64ea7-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="64ea7-119">Description</span></span> |
|---------------------------|------------------------------------|-------------|
| <span data-ttu-id="64ea7-120">Mensajes de banner</span><span class="sxs-lookup"><span data-stu-id="64ea7-120">Banner messages</span></span>           | <span data-ttu-id="64ea7-121">Texto y vínculos</span><span class="sxs-lookup"><span data-stu-id="64ea7-121">Text and links</span></span>                     | <span data-ttu-id="64ea7-122">Una gran variedad de texto y vínculos.</span><span class="sxs-lookup"><span data-stu-id="64ea7-122">An array of text and links.</span></span> |
| <span data-ttu-id="64ea7-123">Reproducción automática</span><span class="sxs-lookup"><span data-stu-id="64ea7-123">Autoplay</span></span>                  | <span data-ttu-id="64ea7-124">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="64ea7-124">**True** or **False**</span></span>              | <span data-ttu-id="64ea7-125">Un valor que indica si los mensajes se muestran cíclicamente de manera automática, si se han configurado varios mensajes.</span><span class="sxs-lookup"><span data-stu-id="64ea7-125">A value that indicates whether messages are automatically cycled through, if multiple messages are configured.</span></span> |
| <span data-ttu-id="64ea7-126">Intervalo de transición de diapositivas</span><span class="sxs-lookup"><span data-stu-id="64ea7-126">Slide transition interval</span></span> | <span data-ttu-id="64ea7-127">Un número de milisegundos (ms)</span><span class="sxs-lookup"><span data-stu-id="64ea7-127">A number of milliseconds (ms)</span></span>      | <span data-ttu-id="64ea7-128">El intervalo que se usa para recorrer los mensajes.</span><span class="sxs-lookup"><span data-stu-id="64ea7-128">The interval that is used to cycle through messages.</span></span> |
| <span data-ttu-id="64ea7-129">Permitir descartar</span><span class="sxs-lookup"><span data-stu-id="64ea7-129">Allow dismiss</span></span>             | <span data-ttu-id="64ea7-130">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="64ea7-130">**True** or **False**</span></span>              | <span data-ttu-id="64ea7-131">Si el valor se establece en **Verdadero**, los clientes pueden descartar la alerta.</span><span class="sxs-lookup"><span data-stu-id="64ea7-131">If the value is set to **True**, customers can dismiss the alert.</span></span> |
| <span data-ttu-id="64ea7-132">Mostrar aleta de carrusel</span><span class="sxs-lookup"><span data-stu-id="64ea7-132">Show carousel flipper</span></span>     | <span data-ttu-id="64ea7-133">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="64ea7-133">**True** or **False**</span></span>              | <span data-ttu-id="64ea7-134">Un valor que indica si se deben mostrar las aletas del carrusel para que los clientes puedan desplazarse manualmente por varios elementos del banner.</span><span class="sxs-lookup"><span data-stu-id="64ea7-134">A value that indicates whether the carousel flippers should be shown, so that customers can manually cycle through multiple banner items.</span></span> |
| <span data-ttu-id="64ea7-135">Alineación de texto</span><span class="sxs-lookup"><span data-stu-id="64ea7-135">Text alignment</span></span>            | <span data-ttu-id="64ea7-136">**Derecha**, **Izquierda** o **Centro**</span><span class="sxs-lookup"><span data-stu-id="64ea7-136">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="64ea7-137">La alineación del texto en el módulo de banner promocional.</span><span class="sxs-lookup"><span data-stu-id="64ea7-137">The text alignment in the promo banner module.</span></span> |
| <span data-ttu-id="64ea7-138">Vincular</span><span class="sxs-lookup"><span data-stu-id="64ea7-138">Link</span></span>                      | <span data-ttu-id="64ea7-139">Una dirección URL</span><span class="sxs-lookup"><span data-stu-id="64ea7-139">A URL</span></span>                              | <span data-ttu-id="64ea7-140">La dirección URL para un vínculo opcional.</span><span class="sxs-lookup"><span data-stu-id="64ea7-140">The URL for an optional link.</span></span> |

## <a name="add-a-promo-banner-module-to-a-page"></a><span data-ttu-id="64ea7-141">Agregar un módulo de banner promocional a una página</span><span class="sxs-lookup"><span data-stu-id="64ea7-141">Add a promo banner module to a page</span></span> 

<span data-ttu-id="64ea7-142">Para agregar un módulo banner promocional a una página y establecer las propiedades necesarias, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="64ea7-142">To add a promo banner module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="64ea7-143">Cree una plantilla de página con el nombre **Plantilla de banner promocional**.</span><span class="sxs-lookup"><span data-stu-id="64ea7-143">Create a page template that is named **Promo banner template**.</span></span>
1. <span data-ttu-id="64ea7-144">En **Esquema de la página**, agregue un módulo de **Página predeterminada** a la franja **Cuerpo**.</span><span class="sxs-lookup"><span data-stu-id="64ea7-144">Under **Page Outline**, add a **Default page** module to the **Body** slot.</span></span> 
1. <span data-ttu-id="64ea7-145">Proteja la plantilla y publíquela.</span><span class="sxs-lookup"><span data-stu-id="64ea7-145">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="64ea7-146">Use la plantilla que acaba de crear para crear una página que se llame **Página de banner promocional**.</span><span class="sxs-lookup"><span data-stu-id="64ea7-146">Use the template that you just created to create a page that is named **Promo banner page**.</span></span> 
1. <span data-ttu-id="64ea7-147">En el espacio **Principal** de la página nueva, agregue un módulo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="64ea7-147">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="64ea7-148">En el panel de la derecha, establezca el valor de **Ancho** en **Rellenar contenedor**.</span><span class="sxs-lookup"><span data-stu-id="64ea7-148">In the pane on the right, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="64ea7-149">En **Esquema de la página**, agregue un módulo de banner promocional al módulo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="64ea7-149">Under **Page Outline**, add a promo banner module to the container module.</span></span>
1. <span data-ttu-id="64ea7-150">En la configuración del módulo de banner, agregue uno o más mensajes de banner.</span><span class="sxs-lookup"><span data-stu-id="64ea7-150">In the settings for the banner module, add one or more banner messages.</span></span> <span data-ttu-id="64ea7-151">Cada mensaje puede tener texto junto con un vínculo.</span><span class="sxs-lookup"><span data-stu-id="64ea7-151">Each message can have text together with a link.</span></span> <span data-ttu-id="64ea7-152">Puede editar las otras propiedades para personalizar más el módulo.</span><span class="sxs-lookup"><span data-stu-id="64ea7-152">You can edit the other properties to customize the module further.</span></span>
1. <span data-ttu-id="64ea7-153">Guarde la página y obtenga una vista previa de ella.</span><span class="sxs-lookup"><span data-stu-id="64ea7-153">Save and preview the page.</span></span> <span data-ttu-id="64ea7-154">En la parte superior de la página, debe ver una alerta que muestra el texto que ha agregado.</span><span class="sxs-lookup"><span data-stu-id="64ea7-154">At the top of the page, you should see an alert that shows the text that you added.</span></span>
1. <span data-ttu-id="64ea7-155">Termine de editar la página y publíquela.</span><span class="sxs-lookup"><span data-stu-id="64ea7-155">Finish editing the page, and publish it.</span></span> 

> [!NOTE]
> <span data-ttu-id="64ea7-156">Un banner promocional se usa generalmente en la franja de encabezado de página o en una franja de subtítulo.</span><span class="sxs-lookup"><span data-stu-id="64ea7-156">A promo banner is typically used in the page header slot or a subheader slot.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="64ea7-157">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="64ea7-157">Additional resources</span></span>

[<span data-ttu-id="64ea7-158">Visión general de kit de inicio</span><span class="sxs-lookup"><span data-stu-id="64ea7-158">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="64ea7-159">Módulo de carrusel</span><span class="sxs-lookup"><span data-stu-id="64ea7-159">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="64ea7-160">Módulo de bloque de texto</span><span class="sxs-lookup"><span data-stu-id="64ea7-160">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="64ea7-161">Módulo de bloque de contenido</span><span class="sxs-lookup"><span data-stu-id="64ea7-161">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="64ea7-162">Módulo de reproductor de vídeo</span><span class="sxs-lookup"><span data-stu-id="64ea7-162">Video player module</span></span>](add-video-player.md)
