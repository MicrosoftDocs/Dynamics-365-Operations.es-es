---
title: Módulo de reproductor de vídeo
description: En este tema se tratan los módulos de reproductor de vídeo y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e94658eed12b12d6666e63d2c06b86646c81a120
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025680"
---
# <a name="video-player-module"></a><span data-ttu-id="b458d-103">Módulo de reproductor de vídeo</span><span class="sxs-lookup"><span data-stu-id="b458d-103">Video player module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="b458d-104">En este tema se tratan los módulos de reproductor de vídeo y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b458d-104">This topic covers video player modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b458d-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="b458d-105">Overview</span></span>

<span data-ttu-id="b458d-106">El módulo de reproductor de vídeo se utiliza para permitir la reproducción de vídeo.</span><span class="sxs-lookup"><span data-stu-id="b458d-106">The video player module is used to support video playback.</span></span> <span data-ttu-id="b458d-107">Se puede agregar a cualquier página, siempre que el contenido de video se cargue y esté disponible en el sistema de administración de contenido (CMS).</span><span class="sxs-lookup"><span data-stu-id="b458d-107">It can be added to any page, provided that video content is uploaded to and available in the content management system (CMS).</span></span> <span data-ttu-id="b458d-108">El módulo del reproductor de video admite medios de tipo .mp4.</span><span class="sxs-lookup"><span data-stu-id="b458d-108">The video player module supports the .mp4 media type.</span></span>

## <a name="video-player-module"></a><span data-ttu-id="b458d-109">Módulo de reproductor de vídeo</span><span class="sxs-lookup"><span data-stu-id="b458d-109">Video player module</span></span>

<span data-ttu-id="b458d-110">El módulo del reproductor de vídeo se puede usar para mostrar vídeos en un sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="b458d-110">The video player module can be used to showcase videos on an e-Commerce site.</span></span> <span data-ttu-id="b458d-111">Admite todas las capacidades de reproducción, como reproducción, pausa, modo de tamaño completo, descripciones de audio y subtítulos.</span><span class="sxs-lookup"><span data-stu-id="b458d-111">It supports all playback capabilities, such as play, pause, full-size mode, audio descriptions, and closed captions.</span></span> <span data-ttu-id="b458d-112">El módulo de reproductor de vídeo también admite la personalización de subtítulos para cumplir los estándares de accesibilidad de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b458d-112">The video player module also supports customization of closed captions to meet Microsoft accessibility standards.</span></span> <span data-ttu-id="b458d-113">Por ejemplo, puede personalizar el tamaño de fuente y el color de fondo.</span><span class="sxs-lookup"><span data-stu-id="b458d-113">For example, you can customize the font size and background color.</span></span>

<span data-ttu-id="b458d-114">El módulo del reproductor de vídeo también admite pistas de audio secundarias.</span><span class="sxs-lookup"><span data-stu-id="b458d-114">The video player module also supports secondary audio tracks.</span></span> <span data-ttu-id="b458d-115">Cuando se carga un vídeo en el CMS, también se puede cargar una pista de audio secundaria.</span><span class="sxs-lookup"><span data-stu-id="b458d-115">When a video is uploaded to the CMS, a secondary audio track can also be uploaded.</span></span> <span data-ttu-id="b458d-116">El módulo del reproductor de vídeo puede reproducir la pista de audio secundaria si un usuario la selecciona.</span><span class="sxs-lookup"><span data-stu-id="b458d-116">The video player module can then play the secondary audio track if a user selects it.</span></span>

### <a name="examples-of-video-player-modules-in-e-commerce"></a><span data-ttu-id="b458d-117">Ejemplos de módulos de reproductor de vídeo en comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="b458d-117">Examples of video player modules in e-Commerce</span></span>

- <span data-ttu-id="b458d-118">Vídeos educacionales sobre las páginas de detalles de productos o páginas de marketing</span><span class="sxs-lookup"><span data-stu-id="b458d-118">Instructional videos on product details pages or marketing pages</span></span>
- <span data-ttu-id="b458d-119">Vídeos promocionales o vídeos sobre directivas en cualquier página de marketing</span><span class="sxs-lookup"><span data-stu-id="b458d-119">Promotional videos or videos about policies on any marketing page</span></span>
- <span data-ttu-id="b458d-120">Vídeos de marketing que resaltan características de productos en las páginas de detalles de productos o páginas de marketing</span><span class="sxs-lookup"><span data-stu-id="b458d-120">Marketing videos that highlight product features on product details pages or marketing pages</span></span>

### <a name="video-player-module-properties"></a><span data-ttu-id="b458d-121">Propiedades de módulo de reproductor de vídeo</span><span class="sxs-lookup"><span data-stu-id="b458d-121">Video player module properties</span></span>

| <span data-ttu-id="b458d-122">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="b458d-122">Property name</span></span>         | <span data-ttu-id="b458d-123">Valor</span><span class="sxs-lookup"><span data-stu-id="b458d-123">Value</span></span>                               | <span data-ttu-id="b458d-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="b458d-124">Description</span></span> |
|-----------------------|-------------------------------------|-------------|
| <span data-ttu-id="b458d-125">Reproducción automática</span><span class="sxs-lookup"><span data-stu-id="b458d-125">Auto play</span></span>             | <span data-ttu-id="b458d-126">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="b458d-126">**True** or **False**</span></span>               | <span data-ttu-id="b458d-127">Si el valor está establecido en **Verdadero**, el vídeo se reproduce automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b458d-127">When the value is set to **True**, the video is automatically played.</span></span> |
| <span data-ttu-id="b458d-128">Silenciar</span><span class="sxs-lookup"><span data-stu-id="b458d-128">Mute</span></span>                  | <span data-ttu-id="b458d-129">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="b458d-129">**True** or **False**</span></span>               | <span data-ttu-id="b458d-130">Si el valor está establecido en **Verdadero**, el audio está silenciado.</span><span class="sxs-lookup"><span data-stu-id="b458d-130">When the value is set to **True**, the audio is muted.</span></span> <span data-ttu-id="b458d-131">Para este reproductor, el valor predeterminado es **Falso**.</span><span class="sxs-lookup"><span data-stu-id="b458d-131">For this player, the default value is **False**.</span></span> <span data-ttu-id="b458d-132">En el explorador de Chrome, los vídeos de reproducción automática están silenciados de manera predeterminada y el sonido solo se reproduce si el usuario reproduce el vídeo manualmente.</span><span class="sxs-lookup"><span data-stu-id="b458d-132">In the Chrome browser, autoplay videos are muted by default, and the audio is played only if the user manually plays the video.</span></span> |
| <span data-ttu-id="b458d-133">Bucle</span><span class="sxs-lookup"><span data-stu-id="b458d-133">Loop</span></span>                  | <span data-ttu-id="b458d-134">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="b458d-134">**True** or **False**</span></span>               | <span data-ttu-id="b458d-135">Si el valor está establecido en **Verdadero**, el vídeo se repite en un bucle.</span><span class="sxs-lookup"><span data-stu-id="b458d-135">When the value is set to **True**, the video is repeated in a loop.</span></span> |
| <span data-ttu-id="b458d-136">Medios</span><span class="sxs-lookup"><span data-stu-id="b458d-136">Media</span></span>                 | <span data-ttu-id="b458d-137">Nombre y ruta del archivo de vídeo</span><span class="sxs-lookup"><span data-stu-id="b458d-137">Video file path and name</span></span> | <span data-ttu-id="b458d-138">El archivo de vídeo se reproduce en el reproductor de vídeo.</span><span class="sxs-lookup"><span data-stu-id="b458d-138">The video file that is played in the video player.</span></span> |
| <span data-ttu-id="b458d-139">Reproducir pantalla completa</span><span class="sxs-lookup"><span data-stu-id="b458d-139">Play fullscreen</span></span>       | <span data-ttu-id="b458d-140">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="b458d-140">**True** or **False**</span></span>               | <span data-ttu-id="b458d-141">Si el valor está establecido en **Verdadero**, el vídeo se reproduce en modo de pantalla completa.</span><span class="sxs-lookup"><span data-stu-id="b458d-141">When the value is set to **True**, the video is played in full-screen mode.</span></span> |
| <span data-ttu-id="b458d-142">Desencadenador de reproducir/pausar</span><span class="sxs-lookup"><span data-stu-id="b458d-142">Play pause trigger</span></span>    | <span data-ttu-id="b458d-143">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="b458d-143">**True** or **False**</span></span>               | <span data-ttu-id="b458d-144">Si el valor se establece en **Verdadero**, en el vídeo se muestra un botón de reproducción/pausa.</span><span class="sxs-lookup"><span data-stu-id="b458d-144">When the value is set to **True**, a play/pause button is shown on the video.</span></span> |
| <span data-ttu-id="b458d-145">Controles de reproductor de vídeo</span><span class="sxs-lookup"><span data-stu-id="b458d-145">Video player controls</span></span> | <span data-ttu-id="b458d-146">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="b458d-146">**True** or **False**</span></span>               | <span data-ttu-id="b458d-147">Si el valor está establecido en **Verdadero**, se muestran todos los controles del reproductor de vídeo.</span><span class="sxs-lookup"><span data-stu-id="b458d-147">When the value is set to **True**, all video player controls are shown.</span></span> <span data-ttu-id="b458d-148">Estos controles incluyen los botones de reproducción y pausa, un indicador de progreso y opciones de subtítulos.</span><span class="sxs-lookup"><span data-stu-id="b458d-148">These controls include play and pause buttons, a progress indicator, and closed caption options.</span></span> |
| <span data-ttu-id="b458d-149">Ocultar imagen del publicador</span><span class="sxs-lookup"><span data-stu-id="b458d-149">Hide poster image</span></span>     | <span data-ttu-id="b458d-150">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="b458d-150">**True** or **False**</span></span>               | <span data-ttu-id="b458d-151">Un vídeo puede tener un marco de póster.</span><span class="sxs-lookup"><span data-stu-id="b458d-151">A video can have a poster frame.</span></span> <span data-ttu-id="b458d-152">Si el valor de esta propiedad se establece en **Verdadero**, se oculta el marco de póster.</span><span class="sxs-lookup"><span data-stu-id="b458d-152">When the value of this property is set to **True**, the poster frame is hidden.</span></span> |
| <span data-ttu-id="b458d-153">Nivel de máscara</span><span class="sxs-lookup"><span data-stu-id="b458d-153">Mask level</span></span>            | <span data-ttu-id="b458d-154">Un número del **0** al **100**</span><span class="sxs-lookup"><span data-stu-id="b458d-154">A number from **0** through **100**</span></span> | <span data-ttu-id="b458d-155">La máscara que se aplica al vídeo para estilo.</span><span class="sxs-lookup"><span data-stu-id="b458d-155">The mask that is applied to the video for styling.</span></span> |

## <a name="add-a-video-player-module-to-a-page"></a><span data-ttu-id="b458d-156">Agregar un módulo de reproductor de vídeo a una página</span><span class="sxs-lookup"><span data-stu-id="b458d-156">Add a video player module to a page</span></span>

> [!NOTE] 
> <span data-ttu-id="b458d-157">Antes de crear un módulo de reproductor de video tiene que cargar un video en la Biblioteca de medios.</span><span class="sxs-lookup"><span data-stu-id="b458d-157">Before you create a video player module, you must first upload a video to the Media Library.</span></span>

<span data-ttu-id="b458d-158">Para agregar un módulo de reproductor de vídeo a una página nueva y establecer las propiedades necesarias, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b458d-158">To add a video player module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="b458d-159">Cree una plantilla de página con el nombre **plantilla de reproductor de vídeo**.</span><span class="sxs-lookup"><span data-stu-id="b458d-159">Create a page template that is named **video player template**.</span></span>
1. <span data-ttu-id="b458d-160">En el espacio **Principal** de la página predeterminada, agregue un módulo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="b458d-160">In the **Main** slot of the default page, add a container module.</span></span>
1. <span data-ttu-id="b458d-161">En el módulo de contenedor, agregue los módulos de reproductor de vídeo y reproductor de vídeo ambiental.</span><span class="sxs-lookup"><span data-stu-id="b458d-161">In the container module, add video player and ambient video player modules.</span></span>
1. <span data-ttu-id="b458d-162">Termine de editar la plantilla y publíquela.</span><span class="sxs-lookup"><span data-stu-id="b458d-162">Finish editing the template, and publish it.</span></span>
1. <span data-ttu-id="b458d-163">Use la plantilla de reproductor de vídeo que acaba de crear para crear una página llamada **página de reproductor de vídeo**.</span><span class="sxs-lookup"><span data-stu-id="b458d-163">Use the video player template that you created to create a page that is named **video player page**.</span></span>
1. <span data-ttu-id="b458d-164">En el espacio **Principal** de la página nueva, agregue un módulo de reproductor de vídeo.</span><span class="sxs-lookup"><span data-stu-id="b458d-164">In the **Main** slot of the new page, add a video player module.</span></span>
1. <span data-ttu-id="b458d-165">En el panel de propiedades para el módulo del reproductor de video, seleccione **Agregar un video**.</span><span class="sxs-lookup"><span data-stu-id="b458d-165">In the property pane for the video player module, select **Add a video**.</span></span>
1. <span data-ttu-id="b458d-166">En el cuadro de diálogo **Selector de medios**, seleccione un video y, a continuación, seleccione **Cargar nuevo elemento multimedia**.</span><span class="sxs-lookup"><span data-stu-id="b458d-166">In the **Media Picker** dialog box, select a video, and then select **Upload new media item**.</span></span>
1. <span data-ttu-id="b458d-167">Guarde la página y obtenga una vista previa de ella.</span><span class="sxs-lookup"><span data-stu-id="b458d-167">Save and preview the page.</span></span> <span data-ttu-id="b458d-168">Debería ver el módulo de vídeo en la página.</span><span class="sxs-lookup"><span data-stu-id="b458d-168">You should see the video module on the page.</span></span> <span data-ttu-id="b458d-169">Puede cambiar la configuración adicional para personalizar el comportamiento del módulo.</span><span class="sxs-lookup"><span data-stu-id="b458d-169">You can change additional settings to customize the behavior of the module.</span></span>
1. <span data-ttu-id="b458d-170">Termine de editar la página y publíquela.</span><span class="sxs-lookup"><span data-stu-id="b458d-170">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b458d-171">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b458d-171">Additional resources</span></span>

[<span data-ttu-id="b458d-172">Visión general de kit de inicio</span><span class="sxs-lookup"><span data-stu-id="b458d-172">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="b458d-173">Módulo de banner promocional</span><span class="sxs-lookup"><span data-stu-id="b458d-173">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="b458d-174">Módulo de carrusel</span><span class="sxs-lookup"><span data-stu-id="b458d-174">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="b458d-175">Módulo de bloque de texto</span><span class="sxs-lookup"><span data-stu-id="b458d-175">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="b458d-176">Módulo de bloque de contenido</span><span class="sxs-lookup"><span data-stu-id="b458d-176">Content block module</span></span>](add-hero-module.md)
