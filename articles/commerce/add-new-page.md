---
title: Agregar una página de sitio nueva
description: En este tema se describe cómo agregar una página de sitio nueva en Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 10/01/2019
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d5ab90343220e427a80cc4dde17c628ba64ac69e
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "2696747"
---
# <a name="add-a-new-site-page"></a><span data-ttu-id="cb0fb-103">Agregar una página de sitio nueva</span><span class="sxs-lookup"><span data-stu-id="cb0fb-103">Add a new site page</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="cb0fb-104">En este tema se describe cómo agregar una página de sitio nueva en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-104">This topic describes how to add a new site page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="cb0fb-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="cb0fb-105">Overview</span></span>

<span data-ttu-id="cb0fb-106">Una vez que ha creado las plantillas y los fragmentos para su sitio, el paso siguiente es empezar a crear las páginas que los usen.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-106">After you've created templates and fragments for your site, the next step is to start to create pages that use them.</span></span> <span data-ttu-id="cb0fb-107">Para empezar, debe seleccionar una plantilla o un diseño, un nombre de página y una dirección URL de página.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-107">To get started, you must select a template or layout, a page name, and a page URL.</span></span>

## <a name="template-or-layout"></a><span data-ttu-id="cb0fb-108">Plantilla o diseño</span><span class="sxs-lookup"><span data-stu-id="cb0fb-108">Template or layout</span></span>

<span data-ttu-id="cb0fb-109">Puede usar una plantilla o un diseño para su nueva página.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-109">You can use either a template or a layout for your new page.</span></span> <span data-ttu-id="cb0fb-110">Para obtener más información, consulte [Visión general de plantillas y diseños](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cb0fb-110">For more information, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

## <a name="page-name"></a><span data-ttu-id="cb0fb-111">Nombre de página</span><span class="sxs-lookup"><span data-stu-id="cb0fb-111">Page name</span></span>

<span data-ttu-id="cb0fb-112">El nombre de la página debe ser único para la página.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-112">The page name must be unique to your page.</span></span> <span data-ttu-id="cb0fb-113">Debe ser descriptivo, de modo que pueda encontrarlo fácilmente y otras entidades sepan para qué está pensada la página.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-113">It should be descriptive, so that you can easily find it and other people know what the page is intended for.</span></span> <span data-ttu-id="cb0fb-114">Elija el nombre de la página cuidadosamente porque no se podrá cambiar posteriormente.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-114">Choose the page name carefully, because it can't be changed later.</span></span>

## <a name="page-url"></a><span data-ttu-id="cb0fb-115">URL de página</span><span class="sxs-lookup"><span data-stu-id="cb0fb-115">Page URL</span></span>

<span data-ttu-id="cb0fb-116">Puede tener la opción de especificar una dirección URL para la nueva página.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-116">You can have the option to enter a URL for your new page.</span></span> <span data-ttu-id="cb0fb-117">Al crear una página, puede especificar una cadena que se usará para formar una dirección URL completa.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-117">When you create a page, you can enter a string that will be used to form a complete URL.</span></span> <span data-ttu-id="cb0fb-118">Esta cadena se conoce como dirección URL relativa o slug de URL.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-118">This string is known as a relative URL or a URL slug.</span></span> <span data-ttu-id="cb0fb-119">Una URL completa se genera entonces en función del slug de URL y se le asigna la nueva página.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-119">A complete URL is then generated based on the URL slug, and the new page is assigned to it.</span></span> <span data-ttu-id="cb0fb-120">Puede cambiar el slug de URL más tarde, antes de publicar la página.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-120">You can change the URL slug later, before you publish the page.</span></span> <span data-ttu-id="cb0fb-121">Para obtener más información, consulte [Crear una URL de página](create-page-URL.md).</span><span class="sxs-lookup"><span data-stu-id="cb0fb-121">For more information, see [Create a page URL](create-page-URL.md).</span></span>

> [!NOTE]
> <span data-ttu-id="cb0fb-122">Dynamics 365 Commerce desacopla direcciones URL y contenido.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-122">Dynamics 365 Commerce decouples URLs and content.</span></span> <span data-ttu-id="cb0fb-123">Es decir, se puede crear una página que no está asociada a una dirección URL, y se puede crear una dirección URL que no está asociada a una página.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-123">In other words, a page can be created that isn't associated with an URL, and a URL can be created that isn't associated with a page.</span></span> <span data-ttu-id="cb0fb-124">Por lo tanto, el intercambiar de contenido se puede hacer para una dirección URL y no requiere tiempo de inactividad, y las redirecciones son más fáciles de gestionar.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-124">Therefore, content swapping can be done for a URL and doesn't require downtime, and redirects are easier to manage.</span></span>

## <a name="add-a-new-page"></a><span data-ttu-id="cb0fb-125">Agregar una página nueva</span><span class="sxs-lookup"><span data-stu-id="cb0fb-125">Add a new page</span></span>

<span data-ttu-id="cb0fb-126">Para agregar una página de sitio nueva al sitio, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-126">To add a new site page to your site, follow these steps.</span></span>

1. <span data-ttu-id="cb0fb-127">En **Sitios**, seleccione **Fabrikam** (o el nombre del sitio).</span><span class="sxs-lookup"><span data-stu-id="cb0fb-127">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="cb0fb-128">Seleccione **Página nueva**.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-128">Select **New Page**.</span></span>
1. <span data-ttu-id="cb0fb-129">En el cuadro de diálogo **Página nueva**, seleccione una plantilla y **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-129">In the **New Page** dialog box, select a template, and then select **OK**.</span></span>
1. <span data-ttu-id="cb0fb-130">En el campo **Nombre de página**, especifique un nombre de página (por ejemplo, **Mi página nueva**).</span><span class="sxs-lookup"><span data-stu-id="cb0fb-130">In the **Page Name** field, enter a page name (for example, **My New Page**).</span></span>
1. <span data-ttu-id="cb0fb-131">En el campo **URL**, especifique una cadena (slug de URL) para completar la dirección URL (por ejemplo, **mynewpage**).</span><span class="sxs-lookup"><span data-stu-id="cb0fb-131">In the **URL** field, enter a string (URL slug) to complete the URL (for example, **mynewpage**).</span></span>
1. <span data-ttu-id="cb0fb-132">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-132">Select **OK**.</span></span> <span data-ttu-id="cb0fb-133">Aparece el editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-133">The page editor appears.</span></span> <span data-ttu-id="cb0fb-134">Observe que un encabezado y un pie de página se agregan automáticamente a la página, en función de la plantilla que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-134">Notice that a header and a footer are automatically added to the page, based on the template that you selected.</span></span>
1. <span data-ttu-id="cb0fb-135">En la página Esquema, seleccione el espacio **Principal**, los puntos suspensivos (**...**) y, a continuación, **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-135">In the page outline, select the **Main** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="cb0fb-136">Seleccione **Contenedor** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-136">Select **Container**, and then select **OK**</span></span>
1. <span data-ttu-id="cb0fb-137">Seleccione **Contenedor de fluido**, el botón de puntos suspensivos y **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-137">Select **Fluid Container**, select the ellipsis button, and then select **Add Module**.</span></span>
1. <span data-ttu-id="cb0fb-138">Seleccione **Bloque de enriquecimiento de contenido** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-138">Select **Content Rich block**, and then select **OK**.</span></span>
1. <span data-ttu-id="cb0fb-139">Seleccione **Bloque de enriquecimiento de contenido**, el botón de puntos suspensivos y **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-139">Select **Content Rich Block**, select the ellipsis button, and then select **Add Module**.</span></span>
1. <span data-ttu-id="cb0fb-140">Seleccione **Elemento de bloque de enriquecimiento de contenido** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-140">Select **Content rich block item**, and then select **OK**.</span></span>
1. <span data-ttu-id="cb0fb-141">En el panel de las propiedades de la derecha, seleccione **Párrafo** y, a continuación, en el campo, escriba **Mi texto de prueba**.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-141">In the properties pane on the right, select **Paragraph**, and then, in the field, enter **My test text**.</span></span>
1. <span data-ttu-id="cb0fb-142">Seleccione **Guardar** y, a continuación, seleccione **Proteger**.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-142">Select **Save**, and then select **Check In**.</span></span>
1. <span data-ttu-id="cb0fb-143">En el campo **Comentarios**, especifique **Nueva página agregada** y, a continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-143">In the **Comments** field, enter **Added new page**, and then select **OK**.</span></span>
1. <span data-ttu-id="cb0fb-144">Seleccione **Vista previa** para obtener una vista previa de la página.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-144">Select **Preview** to preview your page.</span></span> <span data-ttu-id="cb0fb-145">Cuando haya terminado, cierre la pestaña de vista previa para volver a la herramienta de creación.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-145">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="cb0fb-146">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-146">Select **Publish**.</span></span>
1. <span data-ttu-id="cb0fb-147">En la ruta de navegación, seleccione **Fabrikam** (o el nombre del sitio).</span><span class="sxs-lookup"><span data-stu-id="cb0fb-147">In the navigation path (breadcrumbs), select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="cb0fb-148">En el panel de navegación de la izquierda, seleccione **Direcciones URL**.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-148">In the navigation pane on the left, select **URLs**.</span></span>
1. <span data-ttu-id="cb0fb-149">Busque y seleccione su dirección URL (**minuevapágina**) en la lista.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-149">Find and select your URL (**mynewpage**) in the list.</span></span>
1. <span data-ttu-id="cb0fb-150">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="cb0fb-150">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cb0fb-151">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="cb0fb-151">Additional resources</span></span>

[<span data-ttu-id="cb0fb-152">Modificar una página de sitio existente</span><span class="sxs-lookup"><span data-stu-id="cb0fb-152">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="cb0fb-153">Seleccionar diseños de página</span><span class="sxs-lookup"><span data-stu-id="cb0fb-153">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="cb0fb-154">Administrar metadatos de SEO</span><span class="sxs-lookup"><span data-stu-id="cb0fb-154">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="cb0fb-155">Guardar, obtener una vista previa y publicar una página</span><span class="sxs-lookup"><span data-stu-id="cb0fb-155">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="cb0fb-156">Enriquecer una página de producto</span><span class="sxs-lookup"><span data-stu-id="cb0fb-156">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="cb0fb-157">Enriquecer una página de aterrizaje de categoría</span><span class="sxs-lookup"><span data-stu-id="cb0fb-157">Enrich a category landing page</span></span>](enrich-category-page.md)

