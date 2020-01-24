---
title: Agregar una página de directivas de Privacidad
description: En este tema se describe cómo agregar una página de directiva de privacidad a su sitio en Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 01/08/2020
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
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: fd39ff5f8c5d97f2d524043b65627dc7e87fcf64
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "2946079"
---
# <a name="add-a-privacy-policy-page"></a><span data-ttu-id="28aba-103">Agregar una página de directivas de Privacidad</span><span class="sxs-lookup"><span data-stu-id="28aba-103">Add a privacy policy page</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="28aba-104">En este tema se describe cómo agregar una página de directiva de privacidad a su sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="28aba-104">This topic describes how to add a privacy policy page to your site in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="28aba-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="28aba-105">Overview</span></span>

<span data-ttu-id="28aba-106">El cumplimiento de la privacidad incluye medidas organizativas que informan a los usuarios del sitio sobre cómo se recopilan y manejan sus datos.</span><span class="sxs-lookup"><span data-stu-id="28aba-106">Privacy compliance includes organizational measures that inform site users about how their data is collected and handled.</span></span> <span data-ttu-id="28aba-107">Los usuarios pueden decidir cómo quieren que se manejen sus datos personales y pueden tomar las medidas adecuadas.</span><span class="sxs-lookup"><span data-stu-id="28aba-107">Users can then decide how they want their personal data to be handled and can take appropriate action.</span></span>

## <a name="review-the-microsoft-privacy-statement-in-dynamics-365-commerce"></a><span data-ttu-id="28aba-108">Revisar la declaración de privacidad de Microsoft en Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="28aba-108">Review the Microsoft privacy statement in Dynamics 365 Commerce</span></span>

<span data-ttu-id="28aba-109">Para revisar la declaración de privacidad de Microsoft mientras está conectado a las herramientas de creación de Dynamics 365 Commerce, seleccione el botón **Ayuda** ( **?**) en la esquina superior derecha y luego seleccione **Privacidad y cookies**.</span><span class="sxs-lookup"><span data-stu-id="28aba-109">To review the Microsoft privacy statement while you're signed in to the Dynamics 365 Commerce authoring tools, select the **Help** button (**?**) in the upper-right corner, and then select **Privacy and cookies**.</span></span> <span data-ttu-id="28aba-110">Se abre una nueva pestaña que tiene un enlace a la [Declaración de privacidad de Microsoft ](https://privacy.microsoft.com/privacystatement).</span><span class="sxs-lookup"><span data-stu-id="28aba-110">A new tab is opened that has a link to the [Microsoft privacy statement](https://privacy.microsoft.com/privacystatement).</span></span>

## <a name="build-a-privacy-policy-page-for-your-site"></a><span data-ttu-id="28aba-111">Crear una página de directiva de privacidad para su sitio</span><span class="sxs-lookup"><span data-stu-id="28aba-111">Build a privacy policy page for your site</span></span>

<span data-ttu-id="28aba-112">En Dynamics 365 Commerce, hay varias formas de dar a los usuarios de su sitio acceso a su directiva de privacidad.</span><span class="sxs-lookup"><span data-stu-id="28aba-112">In Dynamics 365 Commerce, there are several ways to give users of your site access to your privacy policy.</span></span> <span data-ttu-id="28aba-113">Esta sección muestra cómo crear una página de directiva de privacidad y luego hacer referencia a la página utilizando un fragmento de pie de página.</span><span class="sxs-lookup"><span data-stu-id="28aba-113">This section shows how to build a privacy policy page and then reference the page by using a footer fragment.</span></span>

<span data-ttu-id="28aba-114">La guía que sigue es un ejemplo que muestra cómo construir una página de directiva de privacidad genérica para un sitio de Commerce.</span><span class="sxs-lookup"><span data-stu-id="28aba-114">The guidance that follows is an example that shows how to build a generic privacy policy page for a Commerce site.</span></span> <span data-ttu-id="28aba-115">Usted es responsable de diseñar e implementar la solución de página de directiva de privacidad que mejor cumpla con los requisitos legales de su empresa.</span><span class="sxs-lookup"><span data-stu-id="28aba-115">You're responsible for designing and implementing a privacy policy page solution that best meets your company's legal requirements.</span></span>

<span data-ttu-id="28aba-116">Para comenzar, en las herramientas de creación, vaya al sitio para el que desea crear una página de directiva de privacidad.</span><span class="sxs-lookup"><span data-stu-id="28aba-116">To start, in the authoring tools, go to the site that you want to build a privacy policy page for.</span></span>

### <a name="create-a-template"></a><span data-ttu-id="28aba-117">Crear una plantilla</span><span class="sxs-lookup"><span data-stu-id="28aba-117">Create a template</span></span>

> [!NOTE]
> <span data-ttu-id="28aba-118">Si ya se ha creado una plantilla que se puede utilizar para la página de directiva de privacidad, salte a la sección [Crea una página de directiva de privacidad ](#build-a-privacy-policy-page).</span><span class="sxs-lookup"><span data-stu-id="28aba-118">If a template that can be used for the privacy policy page has already been created, skip ahead to the [Build a privacy policy page](#build-a-privacy-policy-page) section.</span></span>

<span data-ttu-id="28aba-119">Para crear una plantilla, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="28aba-119">To create a template, follow these steps.</span></span>

1. <span data-ttu-id="28aba-120">Vaya a **Plantillas \> Nueva plantilla**.</span><span class="sxs-lookup"><span data-stu-id="28aba-120">Go to **Templates \> New Template**.</span></span>
1. <span data-ttu-id="28aba-121">Especifique el nombre de la plantilla y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="28aba-121">Enter the template name, and then select **OK**.</span></span>
1. <span data-ttu-id="28aba-122">En la plantilla, agregue los módulos necesarios a los espacios de página requeridos.</span><span class="sxs-lookup"><span data-stu-id="28aba-122">In the template, add any required modules to the required page slots.</span></span> <span data-ttu-id="28aba-123">Para orientarse, pase el cursor sobre los signos de exclamación rojos.</span><span class="sxs-lookup"><span data-stu-id="28aba-123">For guidance, hover over the red exclamation marks.</span></span>

    <span data-ttu-id="28aba-124">Por ejemplo, el espacio **Encabezado HTML** puede requerir un módulo **Script externo predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="28aba-124">For example, the **HTML Head** slot might require a **Default External Script** module.</span></span>

1. <span data-ttu-id="28aba-125">En el espacio **Cuerpo**, agregue un módulo de **Página por defecto**.</span><span class="sxs-lookup"><span data-stu-id="28aba-125">In the **Body** slot, add a **Default Page** module.</span></span>
1. <span data-ttu-id="28aba-126">En el módulo **Página predeterminada**, en el espacio **Principal** agregue un módulo **Bloque de contenido enriquecido**.</span><span class="sxs-lookup"><span data-stu-id="28aba-126">In the **Default Page** module, in the **Main** slot, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="28aba-127">En el módulo **Bloque de contenido enriquecido** módulo, agregue un módulo **Elemento de bloque de contenido enriquecido**.</span><span class="sxs-lookup"><span data-stu-id="28aba-127">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="28aba-128">Proteja la plantilla y publíquela.</span><span class="sxs-lookup"><span data-stu-id="28aba-128">Check the template in, and publish it.</span></span>

### <a name="build-a-privacy-policy-page"></a><span data-ttu-id="28aba-129">Crear una página de directivas de Privacidad</span><span class="sxs-lookup"><span data-stu-id="28aba-129">Build a privacy policy page</span></span>

<span data-ttu-id="28aba-130">Para crear una página de directiva de privacidad, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="28aba-130">To build a privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="28aba-131">Vaya a **Páginas \> Nueva página**.</span><span class="sxs-lookup"><span data-stu-id="28aba-131">Go to **Pages \> New Page**.</span></span>
1. <span data-ttu-id="28aba-132">Seleccione la plantilla para la página de directiva de privacidad.</span><span class="sxs-lookup"><span data-stu-id="28aba-132">Select the template for the privacy policy page.</span></span>
1. <span data-ttu-id="28aba-133">Introduzca un nombre y URL de página y después seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="28aba-133">Enter a page name and URL, and then select **OK**.</span></span> 
1. <span data-ttu-id="28aba-134">En el espacio **Principal** de la nueva página, agregue un módulo de **Bloque de enriquecimiento de contenido**.</span><span class="sxs-lookup"><span data-stu-id="28aba-134">In the **Main** slot of the page, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="28aba-135">En el módulo **Bloque de contenido enriquecido** módulo, agregue un módulo **Elemento de bloque de contenido enriquecido**.</span><span class="sxs-lookup"><span data-stu-id="28aba-135">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="28aba-136">En el panel de propiedades para el módulo **Bloque de contenido enriquecido**, seleccione **Agregar fuente de datos** y luego seleccione **Contenido de texto enriquecido**.</span><span class="sxs-lookup"><span data-stu-id="28aba-136">In the properties pane for the **Content Rich Block** module, select **Add Data Source**, and then select **Rich Text Content**.</span></span>
1. <span data-ttu-id="28aba-137">En el editor de texto enriquecido, introduzca el contenido de la página de política de privacidad.</span><span class="sxs-lookup"><span data-stu-id="28aba-137">In the rich text editor, enter the content for the privacy policy page.</span></span> <span data-ttu-id="28aba-138">Expanda el editor de texto enriquecido al modo de pantalla completa según lo requiera.</span><span class="sxs-lookup"><span data-stu-id="28aba-138">Expand the rich text editor to full-screen mode as you require.</span></span>
1. <span data-ttu-id="28aba-139">Cuando haya terminado de introducir contenido, seleccione **Vista previa** para obtener una vista previa de la página en el navegador web.</span><span class="sxs-lookup"><span data-stu-id="28aba-139">When you've finished entering content, select **Preview** to preview the page in the web browser.</span></span>
1. <span data-ttu-id="28aba-140">Complete las adiciones restantes a las propiedades de página y módulo.</span><span class="sxs-lookup"><span data-stu-id="28aba-140">Complete any remaining additions to the page and module properties.</span></span>
1. <span data-ttu-id="28aba-141">Proteja la página de directiva de privacidad y publíquela.</span><span class="sxs-lookup"><span data-stu-id="28aba-141">Check the privacy policy page in, and publish it.</span></span>

<span data-ttu-id="28aba-142">Para publicar la URL de la página de directiva de privacidad, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="28aba-142">To publish the URL for the privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="28aba-143">Vaya a **Direcciones URL** y seleccione la URL de la página de directiva de privacidad.</span><span class="sxs-lookup"><span data-stu-id="28aba-143">Go to **URLs**, and select the URL for the privacy policy page.</span></span>
1. <span data-ttu-id="28aba-144">Publique la URL seleccionada.</span><span class="sxs-lookup"><span data-stu-id="28aba-144">Publish the selected URL.</span></span>

### <a name="create-a-link-to-the-privacy-policy-page-in-a-footer"></a><span data-ttu-id="28aba-145">Crear un enlace a la página de directiva de privacidad en un pie de página</span><span class="sxs-lookup"><span data-stu-id="28aba-145">Create a link to the privacy policy page in a footer</span></span>

<span data-ttu-id="28aba-146">Puede agregar un enlace a la página de directiva de privacidad a un fragmento.</span><span class="sxs-lookup"><span data-stu-id="28aba-146">You can add a link to the privacy policy page to a fragment.</span></span> <span data-ttu-id="28aba-147">De esta manera, puede compartir el enlace y actualizarlo en varias páginas del sitio haciendo referencia al fragmento.</span><span class="sxs-lookup"><span data-stu-id="28aba-147">In this way, you can share the link and update it across multiple site pages by referencing the fragment.</span></span> <span data-ttu-id="28aba-148">Este ejemplo muestra cómo agregar un enlace a la página de directiva de privacidad a un fragmento de pie de página.</span><span class="sxs-lookup"><span data-stu-id="28aba-148">This example shows how to add a link to the privacy policy page to a footer fragment.</span></span>

<span data-ttu-id="28aba-149">Para agregar un enlace a un fragmento de pie de página, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="28aba-149">To add a link to a footer fragment, follow these steps.</span></span>

1. <span data-ttu-id="28aba-150">Vaya a **Fragmentos de página \> Nuevo fragmento de página**.</span><span class="sxs-lookup"><span data-stu-id="28aba-150">Go to **Page Fragments \> New Page Fragment**.</span></span>
1. <span data-ttu-id="28aba-151">Seleccione el módulo **Pie de página** módulo, y luego ingrese un nombre en el campo **Nombre del fragmento de página**.</span><span class="sxs-lookup"><span data-stu-id="28aba-151">Select the **Footer** module, and then enter a name in the **Page Fragment Name** field.</span></span>
1. <span data-ttu-id="28aba-152">En la posición **Categoría de pie de página**, agregue un módulo **Elemento de pie de página**.</span><span class="sxs-lookup"><span data-stu-id="28aba-152">In the **Footer category** slot, add a **Footer item** module.</span></span>
1. <span data-ttu-id="28aba-153">En el panel de propiedades de la derecha, seleccione **Texto del enlace**.</span><span class="sxs-lookup"><span data-stu-id="28aba-153">In the properties pane on the right, select **Link text**.</span></span>
1. <span data-ttu-id="28aba-154">En el cuadro de diálogo **Texto del enlace**, introduzca el texto del enlace y el objetivo del enlace de la página de directiva de privacidad, y luego haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="28aba-154">In the **Link text** dialog box, enter the link text and link target of the privacy policy page, and then click **OK**.</span></span>

    <span data-ttu-id="28aba-155">Para obtener la URL de la página de directiva de privacidad, vaya a **Páginas**, vaya a la página de directiva de privacidad y copie la URL del panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="28aba-155">To get the URL of the privacy policy page, go to **Pages**, go to the privacy policy page, and copy the URL from the properties pane.</span></span>

1. <span data-ttu-id="28aba-156">Guarde el fragmento, protéjalo y publíquelo.</span><span class="sxs-lookup"><span data-stu-id="28aba-156">Save the fragment, check it in, and publish it.</span></span>
1. <span data-ttu-id="28aba-157">Obtenga una vista previa del fragmento y pruebe el enlace a la página de directiva de privacidad.</span><span class="sxs-lookup"><span data-stu-id="28aba-157">Preview the fragment, and test the link to the privacy policy page.</span></span>

<span data-ttu-id="28aba-158">Ahora se puede hacer referencia al fragmento en la plantilla para otras páginas del sitio.</span><span class="sxs-lookup"><span data-stu-id="28aba-158">The fragment can now be referenced in the template for other site pages.</span></span> <span data-ttu-id="28aba-159">Cuando se hace referencia a este fragmento en el módulo **Pie de página** de una plantilla, la referencia del enlace aparecerá en cualquier página que se cree utilizando esa plantilla.</span><span class="sxs-lookup"><span data-stu-id="28aba-159">When this fragment is referenced in the **Footer** module of a template, the link reference will appear on any pages that are built by using that template.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="28aba-160">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="28aba-160">Additional resources</span></span>

[<span data-ttu-id="28aba-161">Resumen de conformidad</span><span class="sxs-lookup"><span data-stu-id="28aba-161">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="28aba-162">Características y funcionalidades de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="28aba-162">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="28aba-163">Cookie de conformidad</span><span class="sxs-lookup"><span data-stu-id="28aba-163">Cookie compliance</span></span>](cookie-compliance.md)