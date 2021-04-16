---
title: Agregar secuencia de comandos a páginas del sitio para admitir telemetría
description: Este tema describe cómo agregar código de script del lado cliente a las páginas del sitio para admitir la colección de telemetría del cliente.
author: bicyclingfool
ms.date: 09/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: fb1773ab10b23a586eb6a8286f145181818585b9
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797440"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="3e0df-103">Agregar secuencia de comandos a páginas del sitio para admitir telemetría</span><span class="sxs-lookup"><span data-stu-id="3e0df-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3e0df-104">Este tema describe cómo agregar código de script del lado cliente a las páginas del sitio para admitir la colección de telemetría del cliente.</span><span class="sxs-lookup"><span data-stu-id="3e0df-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

<span data-ttu-id="3e0df-105">Los análisis web son una herramienta esencial cuando desea comprender de qué manera interactúan los clientes con el sitio y toman decisiones que ayudarán a optimizar la experiencia para la conversión máxima.</span><span class="sxs-lookup"><span data-stu-id="3e0df-105">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="3e0df-106">Muchos paquetes de análisis web están disponibles para ayudarle a alcanzar estos objetivos, como Google Analytics, Clicky, Moz Analytics y KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="3e0df-106">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="3e0df-107">La mayoría de los paquetes de análisis web requieren que agregue código de script del lado cliente en el elemento **\<head\>** del código HTML para todas las páginas del sitio.</span><span class="sxs-lookup"><span data-stu-id="3e0df-107">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="3e0df-108">Las directrices de este tema también se aplican a otra funcionalidad del lado cliente personalizada que Microsoft Dynamics 365 Commerce no ofrece de manera nativa.</span><span class="sxs-lookup"><span data-stu-id="3e0df-108">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="3e0df-109">Crear un fragmento reutilizable para su código de script</span><span class="sxs-lookup"><span data-stu-id="3e0df-109">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="3e0df-110">Un fragmento le permite reutilizar código de script externo o en línea en todas las páginas de su sitio, independientemente de la plantilla que utilicen.</span><span class="sxs-lookup"><span data-stu-id="3e0df-110">A fragment allows you to reuse inline or external script code across all pages on your site, regardless of the template they use.</span></span>

### <a name="create-a-reusable-fragment-for-your-inline-script-code"></a><span data-ttu-id="3e0df-111">Crear un fragmento reutilizable para su código en línea de script</span><span class="sxs-lookup"><span data-stu-id="3e0df-111">Create a reusable fragment for your inline script code</span></span>

<span data-ttu-id="3e0df-112">Para crear un fragmento reutilizable para su código de script en línea en el generador de sitios, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="3e0df-112">To create a reusable fragment for your inline script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="3e0df-113">Vaya a **Fragmentos** y seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-113">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="3e0df-114">En el cuadro de diálogo **Nuevo fragmento**, seleccione **Script en línea**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-114">In the **New fragment** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="3e0df-115">En **Nombre del fragmento**, introduzca un nombre para el fragmento y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-115">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="3e0df-116">Debajo del fragmento que creó, seleccione el módulo **Script en línea predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-116">Under the fragment that you created, select the **Default inline script** module.</span></span>
1. <span data-ttu-id="3e0df-117">En el panel de propiedades a la derecha, debajo de **Script en línea**, introduzca su script del lado del cliente.</span><span class="sxs-lookup"><span data-stu-id="3e0df-117">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="3e0df-118">Luego configure otras opciones según lo requiera.</span><span class="sxs-lookup"><span data-stu-id="3e0df-118">Then configure other options as you require.</span></span>
1. <span data-ttu-id="3e0df-119">Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-119">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="3e0df-120">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-120">Select **Publish**.</span></span>

### <a name="create-a-reusable-fragment-for-your-external-script-code"></a><span data-ttu-id="3e0df-121">Crear un fragmento reutilizable para su código externo de script</span><span class="sxs-lookup"><span data-stu-id="3e0df-121">Create a reusable fragment for your external script code</span></span>

<span data-ttu-id="3e0df-122">Para crear un fragmento reutilizable para su código de script externo en el generador de sitios, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="3e0df-122">To create a reusable fragment for your external script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="3e0df-123">Vaya a **Fragmentos** y seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-123">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="3e0df-124">En el cuadro de diálogo **Nuevo fragmento**, seleccione **Script externo**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-124">In the **New fragment** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="3e0df-125">En **Nombre del fragmento**, introduzca un nombre para el fragmento y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-125">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="3e0df-126">Debajo del fragmento que creó, seleccione el módulo **Script externo predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-126">Under the fragment that you created, select the **Default external script** module.</span></span>
1. <span data-ttu-id="3e0df-127">En el panel de propiedades a la derecha, debajo de **Fuente de script**, agregue una URL externa o relativa para la fuente del script externo.</span><span class="sxs-lookup"><span data-stu-id="3e0df-127">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="3e0df-128">Luego configure otras opciones según lo requiera.</span><span class="sxs-lookup"><span data-stu-id="3e0df-128">Then configure other options as you require.</span></span>
1. <span data-ttu-id="3e0df-129">Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-129">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="3e0df-130">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-130">Select **Publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="3e0df-131">Si la política de seguridad de contenido (CSP) está habilitada para su sitio, asegúrese de que todas las URL externas se agreguen a la directiva **script-src** en el creador de sitios de Commerce.</span><span class="sxs-lookup"><span data-stu-id="3e0df-131">If content security policy (CSP) is enabled for your site, ensure that all external URLs are added to the **script-src** CSP directive in Commerce site builder.</span></span> <span data-ttu-id="3e0df-132">Para más información, consulte [Administrar la Directiva de seguridad de contenido (CSP)](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="3e0df-132">For more information, see [Manage Content Security Policy (CSP)](manage-csp.md).</span></span>

## <a name="add-a-fragment-that-includes-script-code-to-a-template"></a><span data-ttu-id="3e0df-133">Agregar un fragmento que incluya código de script a una plantilla</span><span class="sxs-lookup"><span data-stu-id="3e0df-133">Add a fragment that includes script code to a template</span></span>

<span data-ttu-id="3e0df-134">Para agregar un fragmento que incluye código de script a una plantilla en el generador de sitios, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="3e0df-134">To add a fragment that includes script code to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="3e0df-135">Vaya a **Plantillas** y abra la plantilla para las páginas en las que desea agregar el código de script.</span><span class="sxs-lookup"><span data-stu-id="3e0df-135">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="3e0df-136">En el panel izquierdo, expanda la jerarquía de la plantilla para mostrar la franja **Encabezado HTML**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-136">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="3e0df-137">En el espacio **Encabezado HTML**, seleccione el botón de puntos suspensivos (**...**) y después seleccione **Agregar fragmento**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-137">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="3e0df-138">Seleccione el fragmento que ha creado para su código de script.</span><span class="sxs-lookup"><span data-stu-id="3e0df-138">Select the fragment that you created for your script code.</span></span>
1. <span data-ttu-id="3e0df-139">Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-139">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="3e0df-140">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-140">Select **Publish**.</span></span>

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a><span data-ttu-id="3e0df-141">Agregue un script externo o un script en línea directamente a una plantilla</span><span class="sxs-lookup"><span data-stu-id="3e0df-141">Add an external script or inline script directly to a template</span></span>

<span data-ttu-id="3e0df-142">Si desea insertar un script en línea o externo directamente en un conjunto de páginas controladas por una sola plantilla, no tiene que crear primero un fragmento.</span><span class="sxs-lookup"><span data-stu-id="3e0df-142">If you want to insert an inline or external script directly into a set of pages that are controlled by a single template, you don't have to create a fragment first.</span></span>

### <a name="add-an-inline-script-directly-to-a-template"></a><span data-ttu-id="3e0df-143">Agregar un script en línea directamente a una plantilla</span><span class="sxs-lookup"><span data-stu-id="3e0df-143">Add an inline script directly to a template</span></span>

<span data-ttu-id="3e0df-144">Para agregar un script en línea directamente a una plantilla en el generador de sitios, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="3e0df-144">To add an inline script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="3e0df-145">Vaya a **Plantillas** y abra la plantilla para las páginas en las que desea agregar el código de script.</span><span class="sxs-lookup"><span data-stu-id="3e0df-145">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="3e0df-146">En el panel izquierdo, expanda la jerarquía de la plantilla para mostrar la franja **Encabezado HTML**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-146">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="3e0df-147">En el espacio **Encabezado HTML**, seleccione el botón de puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-147">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3e0df-148">En el cuadro de diálogo **Agregar módulo**, seleccione **Script en línea**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-148">In the **Add Module** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="3e0df-149">En el panel de propiedades a la derecha, debajo de **Script en línea**, introduzca su script del lado del cliente.</span><span class="sxs-lookup"><span data-stu-id="3e0df-149">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="3e0df-150">Luego configure otras opciones según lo requiera.</span><span class="sxs-lookup"><span data-stu-id="3e0df-150">Then configure other options as you require.</span></span>
1. <span data-ttu-id="3e0df-151">Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-151">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="3e0df-152">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-152">Select **Publish**.</span></span>

### <a name="add-an-external-script-directly-to-a-template"></a><span data-ttu-id="3e0df-153">Agregar un script externo directamente a una plantilla</span><span class="sxs-lookup"><span data-stu-id="3e0df-153">Add an external script directly to a template</span></span>

<span data-ttu-id="3e0df-154">Para agregar un script externo directamente a una plantilla en el generador de sitios, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="3e0df-154">To add an external script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="3e0df-155">Vaya a **Plantillas** y abra la plantilla para las páginas en las que desea agregar el código de script.</span><span class="sxs-lookup"><span data-stu-id="3e0df-155">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="3e0df-156">En el panel izquierdo, expanda la jerarquía de la plantilla para mostrar la franja **Encabezado HTML**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-156">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="3e0df-157">En el espacio **Encabezado HTML**, seleccione el botón de puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-157">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3e0df-158">En el cuadro de diálogo **Agregar módulo**, seleccione **Script externo**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-158">In the **Add Module** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="3e0df-159">En el panel de propiedades a la derecha, debajo de **Fuente de script**, agregue una URL externa o relativa para la fuente del script externo.</span><span class="sxs-lookup"><span data-stu-id="3e0df-159">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="3e0df-160">Luego configure otras opciones según lo requiera.</span><span class="sxs-lookup"><span data-stu-id="3e0df-160">Then configure other options as you require.</span></span>
1. <span data-ttu-id="3e0df-161">Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-161">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="3e0df-162">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="3e0df-162">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3e0df-163">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="3e0df-163">Additional resources</span></span>

[<span data-ttu-id="3e0df-164">Agregar un logotipo</span><span class="sxs-lookup"><span data-stu-id="3e0df-164">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="3e0df-165">Seleccionar un tema de sitio</span><span class="sxs-lookup"><span data-stu-id="3e0df-165">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="3e0df-166">Trabajar con archivos de invalidaciones CSS</span><span class="sxs-lookup"><span data-stu-id="3e0df-166">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="3e0df-167">Agregar un icono de favoritos</span><span class="sxs-lookup"><span data-stu-id="3e0df-167">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="3e0df-168">Agregar un mensaje de bienvenida</span><span class="sxs-lookup"><span data-stu-id="3e0df-168">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="3e0df-169">Agregar un aviso de derechos de autor</span><span class="sxs-lookup"><span data-stu-id="3e0df-169">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="3e0df-170">Agregar idiomas al sitio</span><span class="sxs-lookup"><span data-stu-id="3e0df-170">Add languages to your site</span></span>](add-languages-to-site.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
