---
title: Módulo de iframe
description: En este tema se trata el modulo de iframe y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.
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
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: b7b5935a81377e0cb6acfc497eece6148bf1eeee
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993378"
---
# <a name="iframe-module"></a><span data-ttu-id="4db39-103">Módulo de iframe</span><span class="sxs-lookup"><span data-stu-id="4db39-103">Iframe module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4db39-104">En este tema se trata el modulo de iframe y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4db39-104">This topic covers the iframe module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="4db39-105">Información general</span><span class="sxs-lookup"><span data-stu-id="4db39-105">Overview</span></span>

<span data-ttu-id="4db39-106">Un módulo de iframe proporciona un iframe (marco en línea) que aloja contenido externo en un sitio.</span><span class="sxs-lookup"><span data-stu-id="4db39-106">An iframe module provides an iframe (inline frame) that hosts external content on a site.</span></span> <span data-ttu-id="4db39-107">Por ejemplo, se puede usar para alojar un vídeo YouTube o un visor de archivos PDF en cualquier página del sitio.</span><span class="sxs-lookup"><span data-stu-id="4db39-107">For example, it can be used to host a YouTube video or a PDF file viewer on any site page.</span></span> 

<span data-ttu-id="4db39-108">Un módulo de iframe requiere una URL de destino.</span><span class="sxs-lookup"><span data-stu-id="4db39-108">An iframe module requires a target URL.</span></span> <span data-ttu-id="4db39-109">Luego aloja el contenido de la página de destino dentro de un elemento **iframe** de HTML.</span><span class="sxs-lookup"><span data-stu-id="4db39-109">It then hosts the content of the target page inside an HTML **iframe** element.</span></span> <span data-ttu-id="4db39-110">Las URL externas deben estar en la lista de permitidos según las directivas de política de seguridad de contenido (CSP) del sitio.</span><span class="sxs-lookup"><span data-stu-id="4db39-110">External URLs must be on the allow list per the site's content security policy (CSP) directives.</span></span> <span data-ttu-id="4db39-111">Para el contenido de iframe, las URL deben permitirse mediante el uso de la directiva **antepasado del marco**.</span><span class="sxs-lookup"><span data-stu-id="4db39-111">For iframe content, URLs should be allowed by using the **frame-ancestor** directive.</span></span> <span data-ttu-id="4db39-112">Para más información, consulte [Administrar la Directiva de seguridad de contenido (CSP)](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="4db39-112">For more information, see [Manage Content Security Policy (CSP)](manage-csp.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4db39-113">El módulo iframe está disponible en la versión Dynamics 365 Commerce 10.0.13.</span><span class="sxs-lookup"><span data-stu-id="4db39-113">The iframe module is available in the Dynamics 365 Commerce 10.0.13 release.</span></span>

<span data-ttu-id="4db39-114">La siguiente imagen muestra ejemplos de módulos de iframe que muestran videos externos en las páginas del sitio.</span><span class="sxs-lookup"><span data-stu-id="4db39-114">The following image shows examples of iframe modules that showcase external videos on site pages.</span></span>

![Ejemplo de módulos de iframe que muestran vídeos externos](./media/ecommerce-iframe.PNG)

## <a name="iframe-module-properties"></a><span data-ttu-id="4db39-116">Propiedades de módulo de iframe</span><span class="sxs-lookup"><span data-stu-id="4db39-116">Iframe module properties</span></span>

| <span data-ttu-id="4db39-117">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="4db39-117">Property name</span></span>             | <span data-ttu-id="4db39-118">Valor</span><span class="sxs-lookup"><span data-stu-id="4db39-118">Value</span></span>                 | <span data-ttu-id="4db39-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="4db39-119">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="4db39-120">Cabecera</span><span class="sxs-lookup"><span data-stu-id="4db39-120">Heading</span></span> | <span data-ttu-id="4db39-121">Texto</span><span class="sxs-lookup"><span data-stu-id="4db39-121">Text</span></span> | <span data-ttu-id="4db39-122">El encabezado del módulo.</span><span class="sxs-lookup"><span data-stu-id="4db39-122">The heading for the module.</span></span> |
| <span data-ttu-id="4db39-123">Dirección URL de destino</span><span class="sxs-lookup"><span data-stu-id="4db39-123">Target URL</span></span> | <span data-ttu-id="4db39-124">Dirección URL</span><span class="sxs-lookup"><span data-stu-id="4db39-124">URL</span></span> | <span data-ttu-id="4db39-125">La URL que está alojada en el módulo.</span><span class="sxs-lookup"><span data-stu-id="4db39-125">The URL that is hosted in the module.</span></span> |
| <span data-ttu-id="4db39-126">Alto</span><span class="sxs-lookup"><span data-stu-id="4db39-126">Height</span></span> | <span data-ttu-id="4db39-127">Número o porcentaje</span><span class="sxs-lookup"><span data-stu-id="4db39-127">Number or percentage</span></span> | <span data-ttu-id="4db39-128">La altura del módulo, en píxeles o como porcentaje.</span><span class="sxs-lookup"><span data-stu-id="4db39-128">The height of the module, in pixels or as a percentage.</span></span> <span data-ttu-id="4db39-129">Por ejemplo, el valor **100** se tratará como una cantidad de píxeles y el valor **100 %** se tratará como un porcentaje.</span><span class="sxs-lookup"><span data-stu-id="4db39-129">For example, the value **100** will be treated as a number of pixels, and the value **100%** will be treated as a percentage.</span></span> |
| <span data-ttu-id="4db39-130">Etiqueta Aria</span><span class="sxs-lookup"><span data-stu-id="4db39-130">Aria label</span></span> | <span data-ttu-id="4db39-131">Texto</span><span class="sxs-lookup"><span data-stu-id="4db39-131">Text</span></span> | <span data-ttu-id="4db39-132">Se puede definir una etiqueta de aplicaciones de Internet accesibles enriquecidas (ARIA) para fines de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="4db39-132">An Accessible Rich Internet Applications (ARIA) label can be defined for accessibility purposes.</span></span> |

## <a name="add-an-iframe-module-to-a-page"></a><span data-ttu-id="4db39-133">Agregar un módulo de iframe a una página</span><span class="sxs-lookup"><span data-stu-id="4db39-133">Add an iframe module to a page</span></span>

<span data-ttu-id="4db39-134">Para agregar un módulo de iframe a una página para mostrar un vídeo externo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="4db39-134">To add an iframe module to a page to show an external video, follow these steps.</span></span>

1. <span data-ttu-id="4db39-135">Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.</span><span class="sxs-lookup"><span data-stu-id="4db39-135">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="4db39-136">En el cuadro de diálogo **Nueva plantilla**, en **Nombre de la plantilla**, introduzca **Plantilla de marketing** y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4db39-136">In the **New Template** dialog box, under **Template name**, enter **Marketing template**, and then select **OK**.</span></span>
1. <span data-ttu-id="4db39-137">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="4db39-137">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="4db39-138">Vaya a **Páginas** y seleccione **Nuevo** para crear una nueva página.</span><span class="sxs-lookup"><span data-stu-id="4db39-138">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="4db39-139">En el cuadro de diálogo **Elegir una plantilla**, seleccione la plantilla **Plantilla de marketing**.</span><span class="sxs-lookup"><span data-stu-id="4db39-139">In the **Choose a template** dialog box, select the **Marketing template** template.</span></span> <span data-ttu-id="4db39-140">En **Nombre de página**, introduzca **Página de marketing** y después seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4db39-140">Under **Page name**, enter **Marketing page**, and then select **OK**.</span></span>
1. <span data-ttu-id="4db39-141">En el espacio **Principal** de la nueva página, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="4db39-141">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="4db39-142">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4db39-142">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="4db39-143">En el panel de propiedades del módulo, establezca el valor **Ancho** para **Llenar contenedor**.</span><span class="sxs-lookup"><span data-stu-id="4db39-143">In the module's properties pane, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="4db39-144">En el espacio **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="4db39-144">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="4db39-145">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **iframe** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4db39-145">In the **Add Module** dialog box, select the **iframe** module, and then select **OK**.</span></span>
1. <span data-ttu-id="4db39-146">En el panel de propiedades del módulo, establezca el valor **URL de destino** a una URL externa para un vídeo.</span><span class="sxs-lookup"><span data-stu-id="4db39-146">In the module's properties pane, set the **Target URL** value to an external URL for a video.</span></span>
1. <span data-ttu-id="4db39-147">Establecer otras propiedades, como **Bóveda** y **Altura**, como lo requiera.</span><span class="sxs-lookup"><span data-stu-id="4db39-147">Set other properties, such as **Heading** and **Height**, as you require.</span></span>
1. <span data-ttu-id="4db39-148">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="4db39-148">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="4db39-149">Vaya a la página de marketing en su sitio.</span><span class="sxs-lookup"><span data-stu-id="4db39-149">Go to the marketing page on your site.</span></span> <span data-ttu-id="4db39-150">Debería ver que el vídeo se representa en el módulo de iframe.</span><span class="sxs-lookup"><span data-stu-id="4db39-150">You should see that the video is rendered in the iframe module.</span></span>
 
## <a name="additional-resources"></a><span data-ttu-id="4db39-151">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="4db39-151">Additional resources</span></span>

[<span data-ttu-id="4db39-152">Visión general de la biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="4db39-152">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="4db39-153">Administrar la directiva de seguridad de contenido (CSP)</span><span class="sxs-lookup"><span data-stu-id="4db39-153">Manage Content Security Policy (CSP)</span></span>](manage-csp.md)
