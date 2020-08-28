---
title: Agregar secuencia de comandos a páginas del sitio para admitir telemetría
description: Este tema describe cómo agregar código de script del lado cliente a las páginas del sitio para admitir la colección de telemetría del cliente.
author: bicyclingfool
manager: annbe
ms.date: 03/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4f26ed5b6674566f579e801f4b7be63c2d0dc38d
ms.sourcegitcommit: 81f162f2d50557d7afe292c8d326618ba0bc3259
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2020
ms.locfileid: "3686823"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="f79c3-103">Agregar secuencia de comandos a páginas del sitio para admitir telemetría</span><span class="sxs-lookup"><span data-stu-id="f79c3-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f79c3-104">Este tema describe cómo agregar código de script del lado cliente a las páginas del sitio para admitir la colección de telemetría del cliente.</span><span class="sxs-lookup"><span data-stu-id="f79c3-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

## <a name="overview"></a><span data-ttu-id="f79c3-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="f79c3-105">Overview</span></span>

<span data-ttu-id="f79c3-106">Los análisis web son una herramienta esencial cuando desea comprender de qué manera interactúan los clientes con el sitio y toman decisiones que ayudarán a optimizar la experiencia para la conversión máxima.</span><span class="sxs-lookup"><span data-stu-id="f79c3-106">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="f79c3-107">Muchos paquetes de análisis web están disponibles para ayudarle a alcanzar estos objetivos, como Google Analytics, Clicky, Moz Analytics y KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="f79c3-107">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="f79c3-108">La mayoría de los paquetes de análisis web requieren que agregue código de script del lado cliente en el elemento **\<head\>** del código HTML para todas las páginas del sitio.</span><span class="sxs-lookup"><span data-stu-id="f79c3-108">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="f79c3-109">Las directrices de este tema también se aplican a otra funcionalidad del lado cliente personalizada que Microsoft Dynamics 365 Commerce no ofrece de manera nativa.</span><span class="sxs-lookup"><span data-stu-id="f79c3-109">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-page-fragment-for-your-script-code"></a><span data-ttu-id="f79c3-110">Crear una página reutilizable para su código de script</span><span class="sxs-lookup"><span data-stu-id="f79c3-110">Create a reusable page fragment for your script code</span></span>

<span data-ttu-id="f79c3-111">Un fragmento de página le permite reutilizar código de script externo o en línea en todas las páginas de su sitio, independientemente de la plantilla que utilicen.</span><span class="sxs-lookup"><span data-stu-id="f79c3-111">A page fragment allows you to reuse inline or external script code across all pages on your site, regardless of the template they use.</span></span>

### <a name="create-a-reusable-page-fragment-for-your-inline-script-code"></a><span data-ttu-id="f79c3-112">Crear una página reutilizable para su código en línea de script</span><span class="sxs-lookup"><span data-stu-id="f79c3-112">Create a reusable page fragment for your inline script code</span></span>

<span data-ttu-id="f79c3-113">Para crear un fragmento de página reutilizable para su código de script en línea en el generador de sitios, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f79c3-113">To create a reusable page fragment for your inline script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="f79c3-114">Vaya a **Fragmentos** y seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-114">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="f79c3-115">En el cuadro de diálogo **Nuevo fragmento de página**, seleccione **Script en línea**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-115">In the **New page fragment** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="f79c3-116">En **Nombre del fragmento de página**, introduzca un nombre para el fragmento y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-116">Under **Page fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="f79c3-117">Debajo del fragmento de página que creó, seleccione el módulo **Script en línea predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-117">Under the page fragment that you created, select the **Default inline script** module.</span></span>
1. <span data-ttu-id="f79c3-118">En el panel de propiedades a la derecha, debajo de **Script en línea**, introduzca su script del lado del cliente.</span><span class="sxs-lookup"><span data-stu-id="f79c3-118">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="f79c3-119">Luego configure otras opciones según lo requiera.</span><span class="sxs-lookup"><span data-stu-id="f79c3-119">Then configure other options as you require.</span></span>
1. <span data-ttu-id="f79c3-120">Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-120">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="f79c3-121">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-121">Select **Publish**.</span></span>

### <a name="create-a-reusable-page-fragment-for-your-external-script-code"></a><span data-ttu-id="f79c3-122">Crear una página reutilizable para su código externo de script</span><span class="sxs-lookup"><span data-stu-id="f79c3-122">Create a reusable page fragment for your external script code</span></span>

<span data-ttu-id="f79c3-123">Para crear un fragmento de página reutilizable para su código de script externo en el generador de sitios, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f79c3-123">To create a reusable page fragment for your external script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="f79c3-124">Vaya a **Fragmentos** y seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-124">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="f79c3-125">En el cuadro de diálogo **Nuevo fragmento de página**, seleccione **Script externo**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-125">In the **New page fragment** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="f79c3-126">En **Nombre del fragmento de página**, introduzca un nombre para el fragmento y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-126">Under **Page fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="f79c3-127">Debajo del fragmento de página que creó, seleccione el módulo **Script externo predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-127">Under the page fragment that you created, select the **Default external script** module.</span></span>
1. <span data-ttu-id="f79c3-128">En el panel de propiedades a la derecha, debajo de **Fuente de script**, agregue una URL externa o relativa para la fuente del script externo.</span><span class="sxs-lookup"><span data-stu-id="f79c3-128">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="f79c3-129">Luego configure otras opciones según lo requiera.</span><span class="sxs-lookup"><span data-stu-id="f79c3-129">Then configure other options as you require.</span></span>
1. <span data-ttu-id="f79c3-130">Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-130">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="f79c3-131">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-131">Select **Publish**.</span></span>

## <a name="add-a-page-fragment-that-includes-script-code-to-a-template"></a><span data-ttu-id="f79c3-132">Agregar un fragmento de página que incluya código de script a una plantilla</span><span class="sxs-lookup"><span data-stu-id="f79c3-132">Add a page fragment that includes script code to a template</span></span>

<span data-ttu-id="f79c3-133">Para agregar un fragmento de página que incluye código de script a una plantilla en el generador de sitios, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f79c3-133">To add a page fragment that includes script code to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="f79c3-134">Vaya a **Plantillas** y abra la plantilla para las páginas en las que desea agregar el código de script.</span><span class="sxs-lookup"><span data-stu-id="f79c3-134">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="f79c3-135">En el panel izquierdo, expanda la jerarquía de la plantilla para mostrar la franja **Encabezado HTML**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-135">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="f79c3-136">En el espacio **Encabezado HTML**, seleccione el botón de puntos suspensivos (**...**) y después seleccione **Agregar fragmento de página**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-136">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Page Fragment**.</span></span>
1. <span data-ttu-id="f79c3-137">Seleccione el fragmento que ha creado para su código de script.</span><span class="sxs-lookup"><span data-stu-id="f79c3-137">Select the fragment that you created for your script code.</span></span>
1. <span data-ttu-id="f79c3-138">Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-138">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="f79c3-139">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-139">Select **Publish**.</span></span>

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a><span data-ttu-id="f79c3-140">Agregue un script externo o un script en línea directamente a una plantilla</span><span class="sxs-lookup"><span data-stu-id="f79c3-140">Add an external script or inline script directly to a template</span></span>

<span data-ttu-id="f79c3-141">Si desea insertar un script en línea o externo directamente en un conjunto de páginas controladas por una sola plantilla, no tiene que crear primero un fragmento de página.</span><span class="sxs-lookup"><span data-stu-id="f79c3-141">If you want to insert an inline or external script directly into a set of pages that are controlled by a single template, you don't have to create a page fragment first.</span></span>

### <a name="add-an-inline-script-directly-to-a-template"></a><span data-ttu-id="f79c3-142">Agregar un script en línea directamente a una plantilla</span><span class="sxs-lookup"><span data-stu-id="f79c3-142">Add an inline script directly to a template</span></span>

<span data-ttu-id="f79c3-143">Para agregar un script en línea directamente a una plantilla en el generador de sitios, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f79c3-143">To add an inline script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="f79c3-144">Vaya a **Plantillas** y abra la plantilla para las páginas en las que desea agregar el código de script.</span><span class="sxs-lookup"><span data-stu-id="f79c3-144">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="f79c3-145">En el panel izquierdo, expanda la jerarquía de la plantilla para mostrar la franja **Encabezado HTML**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-145">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="f79c3-146">En el espacio **Encabezado HTML**, seleccione el botón de puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-146">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f79c3-147">En el cuadro de diálogo **Agregar módulo**, seleccione **Script en línea**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-147">In the **Add Module** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="f79c3-148">En el panel de propiedades a la derecha, debajo de **Script en línea**, introduzca su script del lado del cliente.</span><span class="sxs-lookup"><span data-stu-id="f79c3-148">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="f79c3-149">Luego configure otras opciones según lo requiera.</span><span class="sxs-lookup"><span data-stu-id="f79c3-149">Then configure other options as you require.</span></span>
1. <span data-ttu-id="f79c3-150">Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-150">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="f79c3-151">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-151">Select **Publish**.</span></span>

### <a name="add-an-external-script-directly-to-a-template"></a><span data-ttu-id="f79c3-152">Agregar un script externo directamente a una plantilla</span><span class="sxs-lookup"><span data-stu-id="f79c3-152">Add an external script directly to a template</span></span>

<span data-ttu-id="f79c3-153">Para agregar un script externo directamente a una plantilla en el generador de sitios, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f79c3-153">To add an external script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="f79c3-154">Vaya a **Plantillas** y abra la plantilla para las páginas en las que desea agregar el código de script.</span><span class="sxs-lookup"><span data-stu-id="f79c3-154">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="f79c3-155">En el panel izquierdo, expanda la jerarquía de la plantilla para mostrar la franja **Encabezado HTML**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-155">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="f79c3-156">En el espacio **Encabezado HTML**, seleccione el botón de puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-156">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f79c3-157">En el cuadro de diálogo **Agregar módulo**, seleccione **Script externo**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-157">In the **Add Module** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="f79c3-158">En el panel de propiedades a la derecha, debajo de **Fuente de script**, agregue una URL externa o relativa para la fuente del script externo.</span><span class="sxs-lookup"><span data-stu-id="f79c3-158">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="f79c3-159">Luego configure otras opciones según lo requiera.</span><span class="sxs-lookup"><span data-stu-id="f79c3-159">Then configure other options as you require.</span></span>
1. <span data-ttu-id="f79c3-160">Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-160">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="f79c3-161">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="f79c3-161">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f79c3-162">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f79c3-162">Additional resources</span></span>

[<span data-ttu-id="f79c3-163">Agregar un logotipo</span><span class="sxs-lookup"><span data-stu-id="f79c3-163">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="f79c3-164">Seleccionar un tema de sitio</span><span class="sxs-lookup"><span data-stu-id="f79c3-164">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="f79c3-165">Trabajar con archivos de invalidaciones CSS</span><span class="sxs-lookup"><span data-stu-id="f79c3-165">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="f79c3-166">Agregar un icono de favoritos</span><span class="sxs-lookup"><span data-stu-id="f79c3-166">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="f79c3-167">Agregar un mensaje de bienvenida</span><span class="sxs-lookup"><span data-stu-id="f79c3-167">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="f79c3-168">Agregar un aviso de derechos de autor</span><span class="sxs-lookup"><span data-stu-id="f79c3-168">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="f79c3-169">Agregar idiomas al sitio</span><span class="sxs-lookup"><span data-stu-id="f79c3-169">Add languages to your site</span></span>](add-languages-to-site.md)
