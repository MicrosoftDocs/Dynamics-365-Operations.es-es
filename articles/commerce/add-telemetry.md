---
title: Agregar secuencia de comandos a páginas del sitio para admitir telemetría
description: Este tema describe cómo agregar código de script del lado cliente a las páginas del sitio para admitir la colección de telemetría del cliente.
author: bicyclingfool
manager: annbe
ms.date: 08/31/2020
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
ms.openlocfilehash: a88f4f920154aafaa15a48af67365152e21111f7
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761258"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="ff7a7-103">Agregar secuencia de comandos a páginas del sitio para admitir telemetría</span><span class="sxs-lookup"><span data-stu-id="ff7a7-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ff7a7-104">Este tema describe cómo agregar código de script del lado cliente a las páginas del sitio para admitir la colección de telemetría del cliente.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

## <a name="overview"></a><span data-ttu-id="ff7a7-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="ff7a7-105">Overview</span></span>

<span data-ttu-id="ff7a7-106">Los análisis web son una herramienta esencial cuando desea comprender de qué manera interactúan los clientes con el sitio y toman decisiones que ayudarán a optimizar la experiencia para la conversión máxima.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-106">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="ff7a7-107">Muchos paquetes de análisis web están disponibles para ayudarle a alcanzar estos objetivos, como Google Analytics, Clicky, Moz Analytics y KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-107">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="ff7a7-108">La mayoría de los paquetes de análisis web requieren que agregue código de script del lado cliente en el elemento **\<head\>** del código HTML para todas las páginas del sitio.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-108">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="ff7a7-109">Las directrices de este tema también se aplican a otra funcionalidad del lado cliente personalizada que Microsoft Dynamics 365 Commerce no ofrece de manera nativa.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-109">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="ff7a7-110">Crear un fragmento reutilizable para su código de script</span><span class="sxs-lookup"><span data-stu-id="ff7a7-110">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="ff7a7-111">Un fragmento le permite reutilizar código de script externo o en línea en todas las páginas de su sitio, independientemente de la plantilla que utilicen.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-111">A fragment allows you to reuse inline or external script code across all pages on your site, regardless of the template they use.</span></span>

### <a name="create-a-reusable-fragment-for-your-inline-script-code"></a><span data-ttu-id="ff7a7-112">Crear un fragmento reutilizable para su código en línea de script</span><span class="sxs-lookup"><span data-stu-id="ff7a7-112">Create a reusable fragment for your inline script code</span></span>

<span data-ttu-id="ff7a7-113">Para crear un fragmento reutilizable para su código de script en línea en el generador de sitios, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-113">To create a reusable fragment for your inline script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="ff7a7-114">Vaya a **Fragmentos** y seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-114">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="ff7a7-115">En el cuadro de diálogo **Nuevo fragmento**, seleccione **Script en línea**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-115">In the **New fragment** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="ff7a7-116">En **Nombre del fragmento**, introduzca un nombre para el fragmento y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-116">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="ff7a7-117">Debajo del fragmento que creó, seleccione el módulo **Script en línea predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-117">Under the fragment that you created, select the **Default inline script** module.</span></span>
1. <span data-ttu-id="ff7a7-118">En el panel de propiedades a la derecha, debajo de **Script en línea**, introduzca su script del lado del cliente.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-118">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="ff7a7-119">Luego configure otras opciones según lo requiera.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-119">Then configure other options as you require.</span></span>
1. <span data-ttu-id="ff7a7-120">Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-120">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="ff7a7-121">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-121">Select **Publish**.</span></span>

### <a name="create-a-reusable-fragment-for-your-external-script-code"></a><span data-ttu-id="ff7a7-122">Crear un fragmento reutilizable para su código externo de script</span><span class="sxs-lookup"><span data-stu-id="ff7a7-122">Create a reusable fragment for your external script code</span></span>

<span data-ttu-id="ff7a7-123">Para crear un fragmento reutilizable para su código de script externo en el generador de sitios, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-123">To create a reusable fragment for your external script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="ff7a7-124">Vaya a **Fragmentos** y seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-124">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="ff7a7-125">En el cuadro de diálogo **Nuevo fragmento**, seleccione **Script externo**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-125">In the **New fragment** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="ff7a7-126">En **Nombre del fragmento**, introduzca un nombre para el fragmento y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-126">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="ff7a7-127">Debajo del fragmento que creó, seleccione el módulo **Script externo predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-127">Under the fragment that you created, select the **Default external script** module.</span></span>
1. <span data-ttu-id="ff7a7-128">En el panel de propiedades a la derecha, debajo de **Fuente de script**, agregue una URL externa o relativa para la fuente del script externo.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-128">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="ff7a7-129">Luego configure otras opciones según lo requiera.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-129">Then configure other options as you require.</span></span>
1. <span data-ttu-id="ff7a7-130">Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-130">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="ff7a7-131">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-131">Select **Publish**.</span></span>

## <a name="add-a-fragment-that-includes-script-code-to-a-template"></a><span data-ttu-id="ff7a7-132">Agregar un fragmento que incluya código de script a una plantilla</span><span class="sxs-lookup"><span data-stu-id="ff7a7-132">Add a fragment that includes script code to a template</span></span>

<span data-ttu-id="ff7a7-133">Para agregar un fragmento que incluye código de script a una plantilla en el generador de sitios, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-133">To add a fragment that includes script code to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="ff7a7-134">Vaya a **Plantillas** y abra la plantilla para las páginas en las que desea agregar el código de script.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-134">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="ff7a7-135">En el panel izquierdo, expanda la jerarquía de la plantilla para mostrar la franja **Encabezado HTML**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-135">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="ff7a7-136">En el espacio **Encabezado HTML**, seleccione el botón de puntos suspensivos (**...**) y después seleccione **Agregar fragmento**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-136">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="ff7a7-137">Seleccione el fragmento que ha creado para su código de script.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-137">Select the fragment that you created for your script code.</span></span>
1. <span data-ttu-id="ff7a7-138">Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-138">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="ff7a7-139">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-139">Select **Publish**.</span></span>

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a><span data-ttu-id="ff7a7-140">Agregue un script externo o un script en línea directamente a una plantilla</span><span class="sxs-lookup"><span data-stu-id="ff7a7-140">Add an external script or inline script directly to a template</span></span>

<span data-ttu-id="ff7a7-141">Si desea insertar un script en línea o externo directamente en un conjunto de páginas controladas por una sola plantilla, no tiene que crear primero un fragmento.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-141">If you want to insert an inline or external script directly into a set of pages that are controlled by a single template, you don't have to create a fragment first.</span></span>

### <a name="add-an-inline-script-directly-to-a-template"></a><span data-ttu-id="ff7a7-142">Agregar un script en línea directamente a una plantilla</span><span class="sxs-lookup"><span data-stu-id="ff7a7-142">Add an inline script directly to a template</span></span>

<span data-ttu-id="ff7a7-143">Para agregar un script en línea directamente a una plantilla en el generador de sitios, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-143">To add an inline script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="ff7a7-144">Vaya a **Plantillas** y abra la plantilla para las páginas en las que desea agregar el código de script.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-144">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="ff7a7-145">En el panel izquierdo, expanda la jerarquía de la plantilla para mostrar la franja **Encabezado HTML**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-145">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="ff7a7-146">En el espacio **Encabezado HTML**, seleccione el botón de puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-146">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="ff7a7-147">En el cuadro de diálogo **Agregar módulo**, seleccione **Script en línea**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-147">In the **Add Module** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="ff7a7-148">En el panel de propiedades a la derecha, debajo de **Script en línea**, introduzca su script del lado del cliente.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-148">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="ff7a7-149">Luego configure otras opciones según lo requiera.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-149">Then configure other options as you require.</span></span>
1. <span data-ttu-id="ff7a7-150">Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-150">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="ff7a7-151">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-151">Select **Publish**.</span></span>

### <a name="add-an-external-script-directly-to-a-template"></a><span data-ttu-id="ff7a7-152">Agregar un script externo directamente a una plantilla</span><span class="sxs-lookup"><span data-stu-id="ff7a7-152">Add an external script directly to a template</span></span>

<span data-ttu-id="ff7a7-153">Para agregar un script externo directamente a una plantilla en el generador de sitios, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-153">To add an external script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="ff7a7-154">Vaya a **Plantillas** y abra la plantilla para las páginas en las que desea agregar el código de script.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-154">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="ff7a7-155">En el panel izquierdo, expanda la jerarquía de la plantilla para mostrar la franja **Encabezado HTML**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-155">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="ff7a7-156">En el espacio **Encabezado HTML**, seleccione el botón de puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-156">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="ff7a7-157">En el cuadro de diálogo **Agregar módulo**, seleccione **Script externo**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-157">In the **Add Module** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="ff7a7-158">En el panel de propiedades a la derecha, debajo de **Fuente de script**, agregue una URL externa o relativa para la fuente del script externo.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-158">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="ff7a7-159">Luego configure otras opciones según lo requiera.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-159">Then configure other options as you require.</span></span>
1. <span data-ttu-id="ff7a7-160">Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-160">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="ff7a7-161">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="ff7a7-161">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ff7a7-162">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ff7a7-162">Additional resources</span></span>

[<span data-ttu-id="ff7a7-163">Agregar un logotipo</span><span class="sxs-lookup"><span data-stu-id="ff7a7-163">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="ff7a7-164">Seleccionar un tema de sitio</span><span class="sxs-lookup"><span data-stu-id="ff7a7-164">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="ff7a7-165">Trabajar con archivos de invalidaciones CSS</span><span class="sxs-lookup"><span data-stu-id="ff7a7-165">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="ff7a7-166">Agregar un icono de favoritos</span><span class="sxs-lookup"><span data-stu-id="ff7a7-166">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="ff7a7-167">Agregar un mensaje de bienvenida</span><span class="sxs-lookup"><span data-stu-id="ff7a7-167">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="ff7a7-168">Agregar un aviso de derechos de autor</span><span class="sxs-lookup"><span data-stu-id="ff7a7-168">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="ff7a7-169">Agregar idiomas al sitio</span><span class="sxs-lookup"><span data-stu-id="ff7a7-169">Add languages to your site</span></span>](add-languages-to-site.md)
