---
title: Agregar una página de directivas de Privacidad
description: En este tema se describe cómo agregar una página de directiva de privacidad a su sitio en Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 07a806ac040df9dee284e2466629221fbc3403a4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209284"
---
# <a name="add-a-privacy-policy-page"></a><span data-ttu-id="7e670-103">Agregar una página de directivas de privacidad</span><span class="sxs-lookup"><span data-stu-id="7e670-103">Add a privacy policy page</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="7e670-104">En este tema se describe cómo agregar una página de directiva de privacidad a su sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7e670-104">This topic describes how to add a privacy policy page to your site in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="7e670-105">Información general</span><span class="sxs-lookup"><span data-stu-id="7e670-105">Overview</span></span>

<span data-ttu-id="7e670-106">El cumplimiento de la privacidad incluye medidas organizativas que informan a los usuarios del sitio sobre cómo se recopilan y manejan sus datos.</span><span class="sxs-lookup"><span data-stu-id="7e670-106">Privacy compliance includes organizational measures that inform site users about how their data is collected and handled.</span></span> <span data-ttu-id="7e670-107">Los usuarios pueden decidir cómo quieren que se manejen sus datos personales y pueden tomar las medidas adecuadas.</span><span class="sxs-lookup"><span data-stu-id="7e670-107">Users can then decide how they want their personal data to be handled and can take appropriate action.</span></span>

## <a name="review-the-microsoft-privacy-statement-in-dynamics-365-commerce"></a><span data-ttu-id="7e670-108">Revisar la declaración de privacidad de Microsoft en Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="7e670-108">Review the Microsoft privacy statement in Dynamics 365 Commerce</span></span>

<span data-ttu-id="7e670-109">Para revisar la declaración de privacidad de Microsoft mientras está conectado a las herramientas de creación de Dynamics 365 Commerce, seleccione el botón **Ayuda** ( **?**) en la esquina superior derecha y luego seleccione **Privacidad y cookies**.</span><span class="sxs-lookup"><span data-stu-id="7e670-109">To review the Microsoft privacy statement while you're signed in to the Dynamics 365 Commerce authoring tools, select the **Help** button (**?**) in the upper-right corner, and then select **Privacy and cookies**.</span></span> <span data-ttu-id="7e670-110">Se abre una nueva pestaña que tiene un enlace a la [Declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement).</span><span class="sxs-lookup"><span data-stu-id="7e670-110">A new tab is opened that has a link to the [Microsoft privacy statement](https://privacy.microsoft.com/privacystatement).</span></span>

## <a name="build-a-privacy-policy-page-for-your-site"></a><span data-ttu-id="7e670-111">Crear una página de directiva de privacidad para su sitio</span><span class="sxs-lookup"><span data-stu-id="7e670-111">Build a privacy policy page for your site</span></span>

<span data-ttu-id="7e670-112">En Dynamics 365 Commerce, hay varias formas de dar a los usuarios de su sitio acceso a su directiva de privacidad.</span><span class="sxs-lookup"><span data-stu-id="7e670-112">In Dynamics 365 Commerce, there are several ways to give users of your site access to your privacy policy.</span></span> <span data-ttu-id="7e670-113">Esta sección muestra cómo crear una página de directiva de privacidad y luego hacer referencia a la página utilizando un fragmento de pie de página.</span><span class="sxs-lookup"><span data-stu-id="7e670-113">This section shows how to build a privacy policy page and then reference the page by using a footer fragment.</span></span>

<span data-ttu-id="7e670-114">La guía que sigue es un ejemplo que muestra cómo construir una página de directiva de privacidad genérica para un sitio de Commerce.</span><span class="sxs-lookup"><span data-stu-id="7e670-114">The guidance that follows is an example that shows how to build a generic privacy policy page for a Commerce site.</span></span> <span data-ttu-id="7e670-115">Usted es responsable de diseñar e implementar la solución de página de directiva de privacidad que mejor cumpla con los requisitos legales de su empresa.</span><span class="sxs-lookup"><span data-stu-id="7e670-115">You're responsible for designing and implementing a privacy policy page solution that best meets your company's legal requirements.</span></span>

<span data-ttu-id="7e670-116">Para comenzar, en las herramientas de creación, vaya al sitio para el que desea crear una página de directiva de privacidad.</span><span class="sxs-lookup"><span data-stu-id="7e670-116">To start, in the authoring tools, go to the site that you want to build a privacy policy page for.</span></span>

### <a name="create-a-template"></a><span data-ttu-id="7e670-117">Crear una plantilla</span><span class="sxs-lookup"><span data-stu-id="7e670-117">Create a template</span></span>

> [!NOTE]
> <span data-ttu-id="7e670-118">Si ya se ha creado una plantilla que se puede utilizar para la página de directiva de privacidad, salte a la sección [Crea una página de directiva de privacidad](#build-a-privacy-policy-page).</span><span class="sxs-lookup"><span data-stu-id="7e670-118">If a template that can be used for the privacy policy page has already been created, skip ahead to the [Build a privacy policy page](#build-a-privacy-policy-page) section.</span></span>

<span data-ttu-id="7e670-119">Para crear una plantilla, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="7e670-119">To create a template, follow these steps.</span></span>

1. <span data-ttu-id="7e670-120">Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una plantilla de página.</span><span class="sxs-lookup"><span data-stu-id="7e670-120">Go to **Templates**, and then select **New** to create a page template.</span></span>
1. <span data-ttu-id="7e670-121">En el cuadro de diálogo **Nueva plantilla**, debajo de **Nombre de la plantilla**, ingrese **Plantilla de banner promocional** y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7e670-121">In the **New Template** dialog box, under **Template Name**, enter **Promo banner template**, and then select **OK**.</span></span>
1. <span data-ttu-id="7e670-122">En la plantilla, agregue los módulos necesarios a los espacios de página requeridos.</span><span class="sxs-lookup"><span data-stu-id="7e670-122">In the template, add any required modules to the required page slots.</span></span> <span data-ttu-id="7e670-123">Para orientarse, pase el cursor sobre los signos de exclamación rojos.</span><span class="sxs-lookup"><span data-stu-id="7e670-123">For guidance, hover over the red exclamation marks.</span></span> <span data-ttu-id="7e670-124">(Por ejemplo, el espacio **Encabezado HTML** puede requerir un módulo **Script externo predeterminado**).</span><span class="sxs-lookup"><span data-stu-id="7e670-124">(For example, the **HTML Head** slot might require a **Default External Script** module.)</span></span>
1. <span data-ttu-id="7e670-125">En el espacio **Cuerpo**, agregue un módulo de **Página por defecto**.</span><span class="sxs-lookup"><span data-stu-id="7e670-125">In the **Body** slot, add a **Default Page** module.</span></span>
1. <span data-ttu-id="7e670-126">En el módulo **Página predeterminada**, en el espacio **Principal** agregue un módulo **Bloque de contenido enriquecido**.</span><span class="sxs-lookup"><span data-stu-id="7e670-126">In the **Default Page** module, in the **Main** slot, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="7e670-127">En el módulo **Bloque de contenido enriquecido** módulo, agregue un módulo **Elemento de bloque de contenido enriquecido**.</span><span class="sxs-lookup"><span data-stu-id="7e670-127">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="7e670-128">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="7e670-128">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

### <a name="build-a-privacy-policy-page"></a><span data-ttu-id="7e670-129">Crear una página de directivas de Privacidad</span><span class="sxs-lookup"><span data-stu-id="7e670-129">Build a privacy policy page</span></span>

<span data-ttu-id="7e670-130">Para crear una página de directiva de privacidad, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="7e670-130">To build a privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="7e670-131">Vaya a **Páginas** y después seleccione **Nuevo** para crear una página.</span><span class="sxs-lookup"><span data-stu-id="7e670-131">Go to **Pages**, and then select **New** to create a page.</span></span>
1. <span data-ttu-id="7e670-132">En el cuadro de diálogo **Elegir una plantilla**, seleccione la plantilla para la página de política de privacidad.</span><span class="sxs-lookup"><span data-stu-id="7e670-132">In the **Choose a template** dialog box, select the template for the privacy policy page.</span></span>
1. <span data-ttu-id="7e670-133">Introduzca un nombre y una URL de página y después seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7e670-133">Enter a page name and page URL, and then select **OK**.</span></span> 
1. <span data-ttu-id="7e670-134">En el espacio **Principal** de la nueva página, agregue un módulo de **Bloque de enriquecimiento de contenido**.</span><span class="sxs-lookup"><span data-stu-id="7e670-134">In the **Main** slot of the page, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="7e670-135">En el módulo **Bloque de contenido enriquecido** módulo, agregue un módulo **Elemento de bloque de contenido enriquecido**.</span><span class="sxs-lookup"><span data-stu-id="7e670-135">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="7e670-136">En el panel de propiedades para el módulo **Bloque de contenido enriquecido**, seleccione **Agregar fuente de datos** y luego seleccione **Contenido de texto enriquecido**.</span><span class="sxs-lookup"><span data-stu-id="7e670-136">In the properties pane for the **Content Rich Block** module, select **Add Data Source**, and then select **Rich Text Content**.</span></span>
1. <span data-ttu-id="7e670-137">En el editor de texto enriquecido, introduzca el contenido de la página de política de privacidad.</span><span class="sxs-lookup"><span data-stu-id="7e670-137">In the rich text editor, enter the content for the privacy policy page.</span></span> <span data-ttu-id="7e670-138">Expanda el editor de texto enriquecido al modo de pantalla completa según lo requiera.</span><span class="sxs-lookup"><span data-stu-id="7e670-138">Expand the rich text editor to full-screen mode as you require.</span></span>
1. <span data-ttu-id="7e670-139">Cuando haya terminado de introducir contenido, seleccione **Vista previa** para obtener una vista previa de la página en el navegador web.</span><span class="sxs-lookup"><span data-stu-id="7e670-139">When you've finished entering content, select **Preview** to preview the page in the web browser.</span></span>
1. <span data-ttu-id="7e670-140">Complete las adiciones restantes a las propiedades de página y módulo.</span><span class="sxs-lookup"><span data-stu-id="7e670-140">Complete any remaining additions to the page and module properties.</span></span>
1. <span data-ttu-id="7e670-141">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="7e670-141">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="7e670-142">Para publicar la URL de la página de directiva de privacidad, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="7e670-142">To publish the URL for the privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="7e670-143">Vaya a **Direcciones URL** y seleccione la URL de la página de directiva de privacidad.</span><span class="sxs-lookup"><span data-stu-id="7e670-143">Go to **URLs**, and select the URL for the privacy policy page.</span></span>
1. <span data-ttu-id="7e670-144">Seleccione **Publicar** para publicar la URL seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7e670-144">Select **Publish** to publish the selected URL.</span></span>

### <a name="create-a-link-to-the-privacy-policy-page-in-a-footer"></a><span data-ttu-id="7e670-145">Crear un enlace a la página de directiva de privacidad en un pie de página</span><span class="sxs-lookup"><span data-stu-id="7e670-145">Create a link to the privacy policy page in a footer</span></span>

<span data-ttu-id="7e670-146">Puede agregar un enlace a la página de directiva de privacidad a un fragmento.</span><span class="sxs-lookup"><span data-stu-id="7e670-146">You can add a link to the privacy policy page to a fragment.</span></span> <span data-ttu-id="7e670-147">De esta manera, puede compartir el enlace y actualizarlo en varias páginas del sitio haciendo referencia al fragmento.</span><span class="sxs-lookup"><span data-stu-id="7e670-147">In this way, you can share the link and update it across multiple site pages by referencing the fragment.</span></span> <span data-ttu-id="7e670-148">Este ejemplo muestra cómo agregar un enlace a la página de directiva de privacidad a un fragmento de pie de página.</span><span class="sxs-lookup"><span data-stu-id="7e670-148">This example shows how to add a link to the privacy policy page to a footer fragment.</span></span>

<span data-ttu-id="7e670-149">Para agregar un enlace a un fragmento de pie de página, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="7e670-149">To add a link to a footer fragment, follow these steps.</span></span>

1. <span data-ttu-id="7e670-150">Vaya a **Fragmentos** y después seleccione **Nuevo** para crear un fragmento de página.</span><span class="sxs-lookup"><span data-stu-id="7e670-150">Go to **Fragments**, and then select **New** to create a page fragment.</span></span>
1. <span data-ttu-id="7e670-151">En el cuadro de diálogo **Nuevo fragmento**, seleccione el módulo **Pie de página**.</span><span class="sxs-lookup"><span data-stu-id="7e670-151">In the **New fragment** dialog box, select the **Footer** module.</span></span>
1. <span data-ttu-id="7e670-152">En **Nombre del fragmento**, introduzca un nombre para el fragmento y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7e670-152">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="7e670-153">En la posición **Categoría de pie de página**, agregue un módulo **Elemento de pie de página**.</span><span class="sxs-lookup"><span data-stu-id="7e670-153">In the **Footer category** slot, add a **Footer item** module.</span></span>
1. <span data-ttu-id="7e670-154">En el panel de propiedades de la derecha, seleccione **Texto del enlace**.</span><span class="sxs-lookup"><span data-stu-id="7e670-154">In the properties pane on the right, select **Link text**.</span></span>
1. <span data-ttu-id="7e670-155">En el cuadro de diálogo **Texto del enlace**, introduzca el texto del enlace y el objetivo del enlace de la página de directiva de privacidad, y luego haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7e670-155">In the **Link text** dialog box, enter the link text and link target of the privacy policy page, and then click **OK**.</span></span>
1. <span data-ttu-id="7e670-156">Para obtener la URL de la página de directiva de privacidad, vaya a **Páginas**, vaya a la página de directiva de privacidad y copie la URL del panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="7e670-156">To get the URL of the privacy policy page, go to **Pages**, go to the privacy policy page, and copy the URL from the properties pane.</span></span>
1. <span data-ttu-id="7e670-157">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger el fragmento y luego seleccione **Publicar** para publicarlo.</span><span class="sxs-lookup"><span data-stu-id="7e670-157">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="7e670-158">Obtenga una vista previa del fragmento y pruebe el enlace a la página de directiva de privacidad.</span><span class="sxs-lookup"><span data-stu-id="7e670-158">Preview the fragment, and test the link to the privacy policy page.</span></span>

<span data-ttu-id="7e670-159">Ahora se puede hacer referencia al fragmento en la plantilla para otras páginas del sitio.</span><span class="sxs-lookup"><span data-stu-id="7e670-159">The fragment can now be referenced in the template for other site pages.</span></span> <span data-ttu-id="7e670-160">Cuando se hace referencia a este fragmento en el módulo **Pie de página** de una plantilla, la referencia del enlace aparecerá en cualquier página que se cree utilizando esa plantilla.</span><span class="sxs-lookup"><span data-stu-id="7e670-160">When this fragment is referenced in the **Footer** module of a template, the link reference will appear on any pages that are built by using that template.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7e670-161">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="7e670-161">Additional resources</span></span>

[<span data-ttu-id="7e670-162">Resumen de conformidad</span><span class="sxs-lookup"><span data-stu-id="7e670-162">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="7e670-163">Características y funcionalidades de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="7e670-163">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="7e670-164">Cumplimiento de cookies</span><span class="sxs-lookup"><span data-stu-id="7e670-164">Cookie compliance</span></span>](cookie-compliance.md)

[<span data-ttu-id="7e670-165">Reemplazar id. de usuario asociado con cambios de contenido con seguimiento</span><span class="sxs-lookup"><span data-stu-id="7e670-165">Replace user IDs associated with tracked content changes</span></span>](replace-IDs-tracked-changes.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]