---
title: Módulo de iframe
description: En este tema se trata el modulo de iframe y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 07/31/2020
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
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 0616a772a416a7c9d9756a840c93b8601c08c3d0
ms.sourcegitcommit: 078befcd7f3531073ab2c08b365bcf132d6477b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2020
ms.locfileid: "3647041"
---
# <a name="iframe-module"></a><span data-ttu-id="8ceb3-103">Módulo de iframe</span><span class="sxs-lookup"><span data-stu-id="8ceb3-103">Iframe module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="8ceb3-104">En este tema se trata el modulo de iframe y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-104">This topic covers the iframe module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="8ceb3-105">Información general</span><span class="sxs-lookup"><span data-stu-id="8ceb3-105">Overview</span></span>

<span data-ttu-id="8ceb3-106">Un módulo de iframe proporciona un iframe (marco en línea) que aloja contenido externo en un sitio.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-106">An iframe module provides an iframe (inline frame) that hosts external content on a site.</span></span> <span data-ttu-id="8ceb3-107">Por ejemplo, se puede usar para alojar un vídeo YouTube o un visor de archivos PDF en cualquier página del sitio.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-107">For example, it can be used to host a YouTube video or a PDF file viewer on any site page.</span></span> 

<span data-ttu-id="8ceb3-108">Un módulo de iframe requiere una URL de destino.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-108">An iframe module requires a target URL.</span></span> <span data-ttu-id="8ceb3-109">Luego aloja el contenido de la página de destino dentro de un elemento **iframe** de HTML.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-109">It then hosts the content of the target page inside an HTML **iframe** element.</span></span> <span data-ttu-id="8ceb3-110">Las URL externas deben estar en la lista de permitidos (también conocida como "lista blanca") según las directivas de política de seguridad de contenido (CSP) del sitio.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-110">External URLs must be on the allow list (also known as a "whitelist") per the site's content security policy (CSP) directives.</span></span> <span data-ttu-id="8ceb3-111">Para el contenido de iframe, las URL deben permitirse mediante el uso de la directiva **antepasado del marco**.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-111">For iframe content, URLs should be allowed by using the **frame-ancestor** directive.</span></span> <span data-ttu-id="8ceb3-112">Para más información, consulte [Administrar la Directiva de seguridad de contenido (CSP)](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="8ceb3-112">For more information, see [Manage Content Security Policy (CSP)](manage-csp.md).</span></span>

<span data-ttu-id="8ceb3-113">La siguiente imagen muestra ejemplos de módulos de iframe que muestran videos externos en las páginas del sitio.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-113">The following image shows examples of iframe modules that showcase external videos on site pages.</span></span>

![Ejemplo de módulos de iframe que muestran vídeos externos](./media/ecommerce-iframe.PNG)

## <a name="iframe-module-properties"></a><span data-ttu-id="8ceb3-115">Propiedades de módulo de iframe</span><span class="sxs-lookup"><span data-stu-id="8ceb3-115">Iframe module properties</span></span>

| <span data-ttu-id="8ceb3-116">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="8ceb3-116">Property name</span></span>             | <span data-ttu-id="8ceb3-117">Valor</span><span class="sxs-lookup"><span data-stu-id="8ceb3-117">Value</span></span>                 | <span data-ttu-id="8ceb3-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="8ceb3-118">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="8ceb3-119">Cabecera</span><span class="sxs-lookup"><span data-stu-id="8ceb3-119">Heading</span></span> | <span data-ttu-id="8ceb3-120">Texto</span><span class="sxs-lookup"><span data-stu-id="8ceb3-120">Text</span></span> | <span data-ttu-id="8ceb3-121">El encabezado del módulo.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-121">The heading for the module.</span></span> |
| <span data-ttu-id="8ceb3-122">Dirección URL de destino</span><span class="sxs-lookup"><span data-stu-id="8ceb3-122">Target URL</span></span> | <span data-ttu-id="8ceb3-123">Dirección URL</span><span class="sxs-lookup"><span data-stu-id="8ceb3-123">URL</span></span> | <span data-ttu-id="8ceb3-124">La URL que está alojada en el módulo.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-124">The URL that is hosted in the module.</span></span> |
| <span data-ttu-id="8ceb3-125">Alto</span><span class="sxs-lookup"><span data-stu-id="8ceb3-125">Height</span></span> | <span data-ttu-id="8ceb3-126">Número o porcentaje</span><span class="sxs-lookup"><span data-stu-id="8ceb3-126">Number or percentage</span></span> | <span data-ttu-id="8ceb3-127">La altura del módulo, en píxeles o como porcentaje.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-127">The height of the module, in pixels or as a percentage.</span></span> <span data-ttu-id="8ceb3-128">Por ejemplo, el valor **100** se tratará como una cantidad de píxeles y el valor **100 %** se tratará como un porcentaje.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-128">For example, the value **100** will be treated as a number of pixels, and the value **100%** will be treated as a percentage.</span></span> |
| <span data-ttu-id="8ceb3-129">Etiqueta Aria</span><span class="sxs-lookup"><span data-stu-id="8ceb3-129">Aria label</span></span> | <span data-ttu-id="8ceb3-130">Texto</span><span class="sxs-lookup"><span data-stu-id="8ceb3-130">Text</span></span> | <span data-ttu-id="8ceb3-131">Se puede definir una etiqueta de aplicaciones de Internet accesibles enriquecidas (ARIA) para fines de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-131">An Accessible Rich Internet Applications (ARIA) label can be defined for accessibility purposes.</span></span> |

## <a name="add-an-iframe-module-to-a-page"></a><span data-ttu-id="8ceb3-132">Agregar un módulo de iframe a una página</span><span class="sxs-lookup"><span data-stu-id="8ceb3-132">Add an iframe module to a page</span></span>

<span data-ttu-id="8ceb3-133">Para agregar un módulo de iframe a una página para mostrar un vídeo externo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-133">To add an iframe module to a page to show an external video, follow these steps.</span></span>

1. <span data-ttu-id="8ceb3-134">Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-134">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="8ceb3-135">En el cuadro de diálogo **Nueva plantilla**, en **Nombre de la plantilla**, introduzca **Plantilla de marketing** y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-135">In the **New Template** dialog box, under **Template name**, enter **Marketing template**, and then select **OK**.</span></span>
1. <span data-ttu-id="8ceb3-136">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-136">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="8ceb3-137">Vaya a **Páginas** y seleccione **Nuevo** para crear una nueva página.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-137">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="8ceb3-138">En el cuadro de diálogo **Elegir una plantilla**, seleccione la plantilla **Plantilla de marketing**.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-138">In the **Choose a template** dialog box, select the **Marketing template** template.</span></span> <span data-ttu-id="8ceb3-139">En **Nombre de página**, introduzca **Página de marketing** y después seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-139">Under **Page name**, enter **Marketing page**, and then select **OK**.</span></span>
1. <span data-ttu-id="8ceb3-140">En el espacio **Principal** de la nueva página, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-140">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="8ceb3-141">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-141">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="8ceb3-142">En el panel de propiedades del módulo, establezca el valor **Ancho** para **Llenar contenedor**.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-142">In the module's properties pane, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="8ceb3-143">En el espacio **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-143">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="8ceb3-144">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **iframe** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-144">In the **Add Module** dialog box, select the **iframe** module, and then select **OK**.</span></span>
1. <span data-ttu-id="8ceb3-145">En el panel de propiedades del módulo, establezca el valor **URL de destino** a una URL externa para un vídeo.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-145">In the module's properties pane, set the **Target URL** value to an external URL for a video.</span></span>
1. <span data-ttu-id="8ceb3-146">Establecer otras propiedades, como **Bóveda** y **Altura**, como lo requiera.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-146">Set other properties, such as **Heading** and **Height**, as you require.</span></span>
1. <span data-ttu-id="8ceb3-147">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-147">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="8ceb3-148">Vaya a la página de marketing en su sitio.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-148">Go to the marketing page on your site.</span></span> <span data-ttu-id="8ceb3-149">Debería ver que el vídeo se representa en el módulo de iframe.</span><span class="sxs-lookup"><span data-stu-id="8ceb3-149">You should see that the video is rendered in the iframe module.</span></span>
 
## <a name="additional-resources"></a><span data-ttu-id="8ceb3-150">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="8ceb3-150">Additional resources</span></span>

[<span data-ttu-id="8ceb3-151">Visión general del kit de inicio</span><span class="sxs-lookup"><span data-stu-id="8ceb3-151">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="8ceb3-152">Administrar la directiva de seguridad de contenido (CSP)</span><span class="sxs-lookup"><span data-stu-id="8ceb3-152">Manage Content Security Policy (CSP)</span></span>](manage-csp.md)
