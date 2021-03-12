---
title: Módulo de banner promocional
description: En este tema se tratan los módulos de banner promocional y se describe la forma de agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: a77196be69bb71d917bf84c633199a3af3fbf478
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4986038"
---
# <a name="promo-banner-module"></a><span data-ttu-id="eae21-103">Módulo de banner promocional</span><span class="sxs-lookup"><span data-stu-id="eae21-103">Promo banner module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="eae21-104">En este tema se tratan los módulos de banner promocional y se describe la forma de agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="eae21-104">This topic covers promo banner modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="eae21-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="eae21-105">Overview</span></span>

<span data-ttu-id="eae21-106">Los módulos de banner promocional se usan para mostrar mensajes informativos en línea en una página.</span><span class="sxs-lookup"><span data-stu-id="eae21-106">Promo banner modules are used to show inline informational messages on a page.</span></span> <span data-ttu-id="eae21-107">Se pueden utilizar para mostrar las promociones en todo el sitio que aparecen en todas las páginas de un sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="eae21-107">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="eae21-108">Los módulos de banner promocional admiten un mensaje de texto y un vínculo.</span><span class="sxs-lookup"><span data-stu-id="eae21-108">Promo banner modules support a text message and a link.</span></span> <span data-ttu-id="eae21-109">Si se agregan varios mensajes a un módulo de banner promocional, se convierte en un banner de carrusel giratorio que permite a los clientes ver todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="eae21-109">If multiple messages are added to a promo banner module, it becomes a rotating carousel banner that lets customers cycle through all the messages.</span></span> 

<span data-ttu-id="eae21-110">Los módulos de banner promocional se controlan con datos desde el sistema de gestión de contenidos (CMS) y se pueden colocar en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="eae21-110">Promo banner modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a><span data-ttu-id="eae21-111">Ejemplos de uso de banners promocionales en comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="eae21-111">Usage examples of promo banners in e-Commerce</span></span>

<span data-ttu-id="eae21-112">Los banners promocionales se pueden usar en el encabezado del sitio para mostrar promociones o mensajes en todo el sitio, como en los siguientes ejemplos.</span><span class="sxs-lookup"><span data-stu-id="eae21-112">Promo banners can be used in the site header to show site-wide promotions or messages, as in the following examples.</span></span>

<span data-ttu-id="eae21-113">“La venta anual finaliza en 10 días”</span><span class="sxs-lookup"><span data-stu-id="eae21-113">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="eae21-114">“Ahorre a lo grande con la oferta de la vuelta al cole.</span><span class="sxs-lookup"><span data-stu-id="eae21-114">"Save big with back to school sale.</span></span> <span data-ttu-id="eae21-115">Compre ahora."</span><span class="sxs-lookup"><span data-stu-id="eae21-115">Shop Now."</span></span>

<span data-ttu-id="eae21-116">"¡Compre en la VENTA de Acción de Gracias!"</span><span class="sxs-lookup"><span data-stu-id="eae21-116">"Shop for Thanksgiving SALE!"</span></span> 

<span data-ttu-id="eae21-117">La siguiente imagen muestra un ejemplo de un banner promocional.</span><span class="sxs-lookup"><span data-stu-id="eae21-117">The following image shows an example of a promo banner.</span></span>

![Ejemplo de un módulo de banner promocional](./media/ecommerce-Promobanner.PNG)

## <a name="promo-banner-module-properties"></a><span data-ttu-id="eae21-119">Propiedades del módulo de banner promocional</span><span class="sxs-lookup"><span data-stu-id="eae21-119">Promo banner module properties</span></span>

| <span data-ttu-id="eae21-120">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="eae21-120">Property name</span></span>             | <span data-ttu-id="eae21-121">Valor</span><span class="sxs-lookup"><span data-stu-id="eae21-121">Value</span></span>                              | <span data-ttu-id="eae21-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="eae21-122">Description</span></span> |
|---------------------------|------------------------------------|-------------|
| <span data-ttu-id="eae21-123">Mensajes de banner</span><span class="sxs-lookup"><span data-stu-id="eae21-123">Banner messages</span></span>           | <span data-ttu-id="eae21-124">Texto y vínculos</span><span class="sxs-lookup"><span data-stu-id="eae21-124">Text and links</span></span>                     | <span data-ttu-id="eae21-125">Una gran variedad de texto y vínculos.</span><span class="sxs-lookup"><span data-stu-id="eae21-125">An array of text and links.</span></span> |
| <span data-ttu-id="eae21-126">Reproducción automática</span><span class="sxs-lookup"><span data-stu-id="eae21-126">Autoplay</span></span>                  | <span data-ttu-id="eae21-127">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="eae21-127">**True** or **False**</span></span>              | <span data-ttu-id="eae21-128">Un valor que indica si los mensajes se muestran cíclicamente de manera automática, si se han configurado varios mensajes.</span><span class="sxs-lookup"><span data-stu-id="eae21-128">A value that indicates whether messages are automatically cycled through, if multiple messages are configured.</span></span> |
| <span data-ttu-id="eae21-129">Intervalo de transición de diapositivas</span><span class="sxs-lookup"><span data-stu-id="eae21-129">Slide transition interval</span></span> | <span data-ttu-id="eae21-130">Un número de milisegundos (ms)</span><span class="sxs-lookup"><span data-stu-id="eae21-130">A number of milliseconds (ms)</span></span>      | <span data-ttu-id="eae21-131">El intervalo que se usa para recorrer los mensajes.</span><span class="sxs-lookup"><span data-stu-id="eae21-131">The interval that is used to cycle through messages.</span></span> |
| <span data-ttu-id="eae21-132">Permitir descartar</span><span class="sxs-lookup"><span data-stu-id="eae21-132">Allow dismiss</span></span>             | <span data-ttu-id="eae21-133">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="eae21-133">**True** or **False**</span></span>              | <span data-ttu-id="eae21-134">Si el valor se establece en **Verdadero**, los clientes pueden descartar la alerta.</span><span class="sxs-lookup"><span data-stu-id="eae21-134">If the value is set to **True**, customers can dismiss the alert.</span></span> |
| <span data-ttu-id="eae21-135">Mostrar aleta de carrusel</span><span class="sxs-lookup"><span data-stu-id="eae21-135">Show carousel flipper</span></span>     | <span data-ttu-id="eae21-136">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="eae21-136">**True** or **False**</span></span>              | <span data-ttu-id="eae21-137">Un valor que indica si se deben mostrar las aletas del carrusel para que los clientes puedan desplazarse manualmente por varios elementos del banner.</span><span class="sxs-lookup"><span data-stu-id="eae21-137">A value that indicates whether the carousel flippers should be shown, so that customers can manually cycle through multiple banner items.</span></span> |
| <span data-ttu-id="eae21-138">Alineación de texto</span><span class="sxs-lookup"><span data-stu-id="eae21-138">Text alignment</span></span>            | <span data-ttu-id="eae21-139">**Derecha**, **Izquierda** o **Centro**</span><span class="sxs-lookup"><span data-stu-id="eae21-139">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="eae21-140">La alineación del texto en el módulo de banner promocional.</span><span class="sxs-lookup"><span data-stu-id="eae21-140">The text alignment in the promo banner module.</span></span> |
| <span data-ttu-id="eae21-141">Vincular</span><span class="sxs-lookup"><span data-stu-id="eae21-141">Link</span></span>                      | <span data-ttu-id="eae21-142">Una dirección URL</span><span class="sxs-lookup"><span data-stu-id="eae21-142">A URL</span></span>                              | <span data-ttu-id="eae21-143">La dirección URL para un vínculo opcional.</span><span class="sxs-lookup"><span data-stu-id="eae21-143">The URL for an optional link.</span></span> |

## <a name="add-a-promo-banner-module-to-a-page"></a><span data-ttu-id="eae21-144">Agregar un módulo de banner promocional a una página</span><span class="sxs-lookup"><span data-stu-id="eae21-144">Add a promo banner module to a page</span></span> 

<span data-ttu-id="eae21-145">Para agregar un módulo banner promocional a una página y establecer las propiedades necesarias, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="eae21-145">To add a promo banner module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="eae21-146">Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.</span><span class="sxs-lookup"><span data-stu-id="eae21-146">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="eae21-147">En el cuadro de diálogo **Nueva plantilla**, debajo de **Nombre de la plantilla**, introduzca **Plantilla de banner promocional** y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="eae21-147">In the **New Template** dialog box, under **Template Name**, enter **Promo banner template**, and then select **OK**.</span></span>
1. <span data-ttu-id="eae21-148">En **Esquema de la página**, agregue un módulo de **Página predeterminada** a la franja **Cuerpo**.</span><span class="sxs-lookup"><span data-stu-id="eae21-148">Under **Page Outline**, add a **Default page** module to the **Body** slot.</span></span> 
1. <span data-ttu-id="eae21-149">Seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="eae21-149">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 
1. <span data-ttu-id="eae21-150">Use la plantilla que acaba de crear para crear una página que se llame **Página de banner promocional**.</span><span class="sxs-lookup"><span data-stu-id="eae21-150">Use the template that you just created to create a page that is named **Promo banner page**.</span></span> 
1. <span data-ttu-id="eae21-151">En el espacio **Principal** de la página nueva, agregue un módulo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="eae21-151">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="eae21-152">En el panel de la derecha, establezca el valor de **Ancho** en **Rellenar contenedor**.</span><span class="sxs-lookup"><span data-stu-id="eae21-152">In the pane on the right, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="eae21-153">En **Esquema de la página**, agregue un módulo de banner promocional al módulo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="eae21-153">Under **Page Outline**, add a promo banner module to the container module.</span></span>
1. <span data-ttu-id="eae21-154">En la configuración del módulo de banner, agregue uno o más mensajes de banner.</span><span class="sxs-lookup"><span data-stu-id="eae21-154">In the settings for the banner module, add one or more banner messages.</span></span> <span data-ttu-id="eae21-155">Cada mensaje puede tener texto junto con un vínculo.</span><span class="sxs-lookup"><span data-stu-id="eae21-155">Each message can have text together with a link.</span></span> <span data-ttu-id="eae21-156">Puede editar las otras propiedades para personalizar más el módulo.</span><span class="sxs-lookup"><span data-stu-id="eae21-156">You can edit the other properties to customize the module further.</span></span>
1. <span data-ttu-id="eae21-157">Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.</span><span class="sxs-lookup"><span data-stu-id="eae21-157">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="eae21-158">En la parte superior de la página, debe ver una alerta que muestra el texto que ha agregado.</span><span class="sxs-lookup"><span data-stu-id="eae21-158">At the top of the page, you should see an alert that shows the text that you added.</span></span>
1. <span data-ttu-id="eae21-159">Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="eae21-159">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="eae21-160">Un banner promocional se usa generalmente en la franja de encabezado de página o en una franja de subtítulo.</span><span class="sxs-lookup"><span data-stu-id="eae21-160">A promo banner is typically used in the page header slot or a subheader slot.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="eae21-161">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="eae21-161">Additional resources</span></span>

[<span data-ttu-id="eae21-162">Visión general de la biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="eae21-162">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="eae21-163">Módulo de carrusel</span><span class="sxs-lookup"><span data-stu-id="eae21-163">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="eae21-164">Módulo de bloque de texto</span><span class="sxs-lookup"><span data-stu-id="eae21-164">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="eae21-165">Módulo de bloque de contenido</span><span class="sxs-lookup"><span data-stu-id="eae21-165">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="eae21-166">Módulo de reproductor de vídeo</span><span class="sxs-lookup"><span data-stu-id="eae21-166">Video player module</span></span>](add-video-player.md)
