---
title: Módulo de banner promocional
description: En este tema se tratan los módulos de banner promocional y se describe la forma de agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: be3cc9729b58fce9ebc9885d8cb20b63114362a0
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796255"
---
# <a name="promo-banner-module"></a><span data-ttu-id="88fbb-103">Módulo de banner promocional</span><span class="sxs-lookup"><span data-stu-id="88fbb-103">Promo banner module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="88fbb-104">En este tema se tratan los módulos de banner promocional y se describe la forma de agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="88fbb-104">This topic covers promo banner modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="88fbb-105">Los módulos de banner promocional se usan para mostrar mensajes informativos en línea en una página.</span><span class="sxs-lookup"><span data-stu-id="88fbb-105">Promo banner modules are used to show inline informational messages on a page.</span></span> <span data-ttu-id="88fbb-106">Se pueden utilizar para mostrar las promociones en todo el sitio que aparecen en todas las páginas de un sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="88fbb-106">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="88fbb-107">Los módulos de banner promocional admiten un mensaje de texto y un vínculo.</span><span class="sxs-lookup"><span data-stu-id="88fbb-107">Promo banner modules support a text message and a link.</span></span> <span data-ttu-id="88fbb-108">Si se agregan varios mensajes a un módulo de banner promocional, se convierte en un banner de carrusel giratorio que permite a los clientes ver todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="88fbb-108">If multiple messages are added to a promo banner module, it becomes a rotating carousel banner that lets customers cycle through all the messages.</span></span> 

<span data-ttu-id="88fbb-109">Los módulos de banner promocional se controlan con datos desde el sistema de gestión de contenidos (CMS) y se pueden colocar en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="88fbb-109">Promo banner modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a><span data-ttu-id="88fbb-110">Ejemplos de uso de banners promocionales en comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="88fbb-110">Usage examples of promo banners in e-Commerce</span></span>

<span data-ttu-id="88fbb-111">Los banners promocionales se pueden usar en el encabezado del sitio para mostrar promociones o mensajes en todo el sitio, como en los siguientes ejemplos.</span><span class="sxs-lookup"><span data-stu-id="88fbb-111">Promo banners can be used in the site header to show site-wide promotions or messages, as in the following examples.</span></span>

<span data-ttu-id="88fbb-112">“La venta anual finaliza en 10 días”</span><span class="sxs-lookup"><span data-stu-id="88fbb-112">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="88fbb-113">“Ahorre a lo grande con la oferta de la vuelta al cole.</span><span class="sxs-lookup"><span data-stu-id="88fbb-113">"Save big with back to school sale.</span></span> <span data-ttu-id="88fbb-114">Compre ahora."</span><span class="sxs-lookup"><span data-stu-id="88fbb-114">Shop Now."</span></span>

<span data-ttu-id="88fbb-115">"¡Compre en la VENTA de Acción de Gracias!"</span><span class="sxs-lookup"><span data-stu-id="88fbb-115">"Shop for Thanksgiving SALE!"</span></span> 

<span data-ttu-id="88fbb-116">La siguiente imagen muestra un ejemplo de un banner promocional.</span><span class="sxs-lookup"><span data-stu-id="88fbb-116">The following image shows an example of a promo banner.</span></span>

![Ejemplo de un módulo de banner promocional](./media/ecommerce-Promobanner.PNG)

## <a name="promo-banner-module-properties"></a><span data-ttu-id="88fbb-118">Propiedades del módulo de banner promocional</span><span class="sxs-lookup"><span data-stu-id="88fbb-118">Promo banner module properties</span></span>

| <span data-ttu-id="88fbb-119">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="88fbb-119">Property name</span></span>             | <span data-ttu-id="88fbb-120">Valor</span><span class="sxs-lookup"><span data-stu-id="88fbb-120">Value</span></span>                              | <span data-ttu-id="88fbb-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="88fbb-121">Description</span></span> |
|---------------------------|------------------------------------|-------------|
| <span data-ttu-id="88fbb-122">Mensajes de banner</span><span class="sxs-lookup"><span data-stu-id="88fbb-122">Banner messages</span></span>           | <span data-ttu-id="88fbb-123">Texto y vínculos</span><span class="sxs-lookup"><span data-stu-id="88fbb-123">Text and links</span></span>                     | <span data-ttu-id="88fbb-124">Una gran variedad de texto y vínculos.</span><span class="sxs-lookup"><span data-stu-id="88fbb-124">An array of text and links.</span></span> |
| <span data-ttu-id="88fbb-125">Reproducción automática</span><span class="sxs-lookup"><span data-stu-id="88fbb-125">Autoplay</span></span>                  | <span data-ttu-id="88fbb-126">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="88fbb-126">**True** or **False**</span></span>              | <span data-ttu-id="88fbb-127">Un valor que indica si los mensajes se muestran cíclicamente de manera automática, si se han configurado varios mensajes.</span><span class="sxs-lookup"><span data-stu-id="88fbb-127">A value that indicates whether messages are automatically cycled through, if multiple messages are configured.</span></span> |
| <span data-ttu-id="88fbb-128">Intervalo de transición de diapositivas</span><span class="sxs-lookup"><span data-stu-id="88fbb-128">Slide transition interval</span></span> | <span data-ttu-id="88fbb-129">Un número de milisegundos (ms)</span><span class="sxs-lookup"><span data-stu-id="88fbb-129">A number of milliseconds (ms)</span></span>      | <span data-ttu-id="88fbb-130">El intervalo que se usa para recorrer los mensajes.</span><span class="sxs-lookup"><span data-stu-id="88fbb-130">The interval that is used to cycle through messages.</span></span> |
| <span data-ttu-id="88fbb-131">Permitir descartar</span><span class="sxs-lookup"><span data-stu-id="88fbb-131">Allow dismiss</span></span>             | <span data-ttu-id="88fbb-132">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="88fbb-132">**True** or **False**</span></span>              | <span data-ttu-id="88fbb-133">Si el valor se establece en **Verdadero**, los clientes pueden descartar la alerta.</span><span class="sxs-lookup"><span data-stu-id="88fbb-133">If the value is set to **True**, customers can dismiss the alert.</span></span> |
| <span data-ttu-id="88fbb-134">Mostrar aleta de carrusel</span><span class="sxs-lookup"><span data-stu-id="88fbb-134">Show carousel flipper</span></span>     | <span data-ttu-id="88fbb-135">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="88fbb-135">**True** or **False**</span></span>              | <span data-ttu-id="88fbb-136">Un valor que indica si se deben mostrar las aletas del carrusel para que los clientes puedan desplazarse manualmente por varios elementos del banner.</span><span class="sxs-lookup"><span data-stu-id="88fbb-136">A value that indicates whether the carousel flippers should be shown, so that customers can manually cycle through multiple banner items.</span></span> |
| <span data-ttu-id="88fbb-137">Alineación de texto</span><span class="sxs-lookup"><span data-stu-id="88fbb-137">Text alignment</span></span>            | <span data-ttu-id="88fbb-138">**Derecha**, **Izquierda** o **Centro**</span><span class="sxs-lookup"><span data-stu-id="88fbb-138">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="88fbb-139">La alineación del texto en el módulo de banner promocional.</span><span class="sxs-lookup"><span data-stu-id="88fbb-139">The text alignment in the promo banner module.</span></span> |
| <span data-ttu-id="88fbb-140">Vincular</span><span class="sxs-lookup"><span data-stu-id="88fbb-140">Link</span></span>                      | <span data-ttu-id="88fbb-141">Una dirección URL</span><span class="sxs-lookup"><span data-stu-id="88fbb-141">A URL</span></span>                              | <span data-ttu-id="88fbb-142">La dirección URL para un vínculo opcional.</span><span class="sxs-lookup"><span data-stu-id="88fbb-142">The URL for an optional link.</span></span> |

## <a name="add-a-promo-banner-module-to-a-page"></a><span data-ttu-id="88fbb-143">Agregar un módulo de banner promocional a una página</span><span class="sxs-lookup"><span data-stu-id="88fbb-143">Add a promo banner module to a page</span></span> 

<span data-ttu-id="88fbb-144">Para agregar un módulo banner promocional a una página y establecer las propiedades necesarias, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="88fbb-144">To add a promo banner module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="88fbb-145">Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.</span><span class="sxs-lookup"><span data-stu-id="88fbb-145">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="88fbb-146">En el cuadro de diálogo **Nueva plantilla**, debajo de **Nombre de la plantilla**, introduzca **Plantilla de banner promocional** y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="88fbb-146">In the **New Template** dialog box, under **Template Name**, enter **Promo banner template**, and then select **OK**.</span></span>
1. <span data-ttu-id="88fbb-147">En **Esquema de la página**, agregue un módulo de **Página predeterminada** a la franja **Cuerpo**.</span><span class="sxs-lookup"><span data-stu-id="88fbb-147">Under **Page Outline**, add a **Default page** module to the **Body** slot.</span></span> 
1. <span data-ttu-id="88fbb-148">Seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="88fbb-148">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 
1. <span data-ttu-id="88fbb-149">Use la plantilla que acaba de crear para crear una página que se llame **Página de banner promocional**.</span><span class="sxs-lookup"><span data-stu-id="88fbb-149">Use the template that you just created to create a page that is named **Promo banner page**.</span></span> 
1. <span data-ttu-id="88fbb-150">En el espacio **Principal** de la página nueva, agregue un módulo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="88fbb-150">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="88fbb-151">En el panel de la derecha, establezca el valor de **Ancho** en **Rellenar contenedor**.</span><span class="sxs-lookup"><span data-stu-id="88fbb-151">In the pane on the right, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="88fbb-152">En **Esquema de la página**, agregue un módulo de banner promocional al módulo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="88fbb-152">Under **Page Outline**, add a promo banner module to the container module.</span></span>
1. <span data-ttu-id="88fbb-153">En la configuración del módulo de banner, agregue uno o más mensajes de banner.</span><span class="sxs-lookup"><span data-stu-id="88fbb-153">In the settings for the banner module, add one or more banner messages.</span></span> <span data-ttu-id="88fbb-154">Cada mensaje puede tener texto junto con un vínculo.</span><span class="sxs-lookup"><span data-stu-id="88fbb-154">Each message can have text together with a link.</span></span> <span data-ttu-id="88fbb-155">Puede editar las otras propiedades para personalizar más el módulo.</span><span class="sxs-lookup"><span data-stu-id="88fbb-155">You can edit the other properties to customize the module further.</span></span>
1. <span data-ttu-id="88fbb-156">Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.</span><span class="sxs-lookup"><span data-stu-id="88fbb-156">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="88fbb-157">En la parte superior de la página, debe ver una alerta que muestra el texto que ha agregado.</span><span class="sxs-lookup"><span data-stu-id="88fbb-157">At the top of the page, you should see an alert that shows the text that you added.</span></span>
1. <span data-ttu-id="88fbb-158">Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="88fbb-158">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="88fbb-159">Un banner promocional se usa generalmente en la franja de encabezado de página o en una franja de subtítulo.</span><span class="sxs-lookup"><span data-stu-id="88fbb-159">A promo banner is typically used in the page header slot or a subheader slot.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="88fbb-160">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="88fbb-160">Additional resources</span></span>

[<span data-ttu-id="88fbb-161">Visión general de la biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="88fbb-161">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="88fbb-162">Módulo de carrusel</span><span class="sxs-lookup"><span data-stu-id="88fbb-162">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="88fbb-163">Módulo de bloque de texto</span><span class="sxs-lookup"><span data-stu-id="88fbb-163">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="88fbb-164">Módulo de bloque de contenido</span><span class="sxs-lookup"><span data-stu-id="88fbb-164">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="88fbb-165">Módulo de reproductor de vídeo</span><span class="sxs-lookup"><span data-stu-id="88fbb-165">Video player module</span></span>](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]