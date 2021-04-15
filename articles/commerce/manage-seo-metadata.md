---
title: Administrar metadatos de SEO
description: Este tema describe cómo administrar los metadatos de la optimización de motor de búsqueda (SEO) en Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1e03ef346df92a94b0a403f241d0f7d1f64fd210
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794220"
---
# <a name="manage-seo-metadata"></a><span data-ttu-id="0efe9-103">Administrar metadatos de SEO</span><span class="sxs-lookup"><span data-stu-id="0efe9-103">Manage SEO metadata</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0efe9-104">Este tema describe cómo administrar los metadatos de la optimización de motor de búsqueda (SEO) en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0efe9-104">This topic describes how to manage search engine optimization (SEO) metadata in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="0efe9-105">Los metadatos SEO para un sitio se pueden administrar mediante mapas de sitio y metadatos de página.</span><span class="sxs-lookup"><span data-stu-id="0efe9-105">SEO metadata for a site can be managed by using site maps and page metadata.</span></span>
    
## <a name="site-maps"></a><span data-ttu-id="0efe9-106">Mapas del sitio</span><span class="sxs-lookup"><span data-stu-id="0efe9-106">Site maps</span></span>

<span data-ttu-id="0efe9-107">Un mapa del sitio es una lista legible, en formato XML, de las páginas de su sitio web.</span><span class="sxs-lookup"><span data-stu-id="0efe9-107">A site map is a machine-readable list, in XML format, of the pages on your website.</span></span> <span data-ttu-id="0efe9-108">Se ha pensado para ser consumido por motores de búsqueda, de modo que puedan proporcionar mejores resultados de la búsqueda desde el sitio.</span><span class="sxs-lookup"><span data-stu-id="0efe9-108">It's intended to be consumed by search engines, so that they can provide better search results from your site.</span></span> <span data-ttu-id="0efe9-109">Los mapas del sitio se pueden ingerir manualmente por motores de búsqueda o publicarse en un archivo robots.txt.</span><span class="sxs-lookup"><span data-stu-id="0efe9-109">Site maps can be manually ingested by search engines or published in a robots.txt file.</span></span>

<span data-ttu-id="0efe9-110">Dynamics 365 Commerce admite la creación automática de mapas del sitio.</span><span class="sxs-lookup"><span data-stu-id="0efe9-110">Dynamics 365 Commerce supports automatic generation of site maps.</span></span> <span data-ttu-id="0efe9-111">Los mapas del sitio se actualizan automáticamente cuando las páginas se publican y se cancela su publicación.</span><span class="sxs-lookup"><span data-stu-id="0efe9-111">Site maps are automatically updated when pages are published and unpublished.</span></span>

### <a name="turn-on-site-map-generation"></a><span data-ttu-id="0efe9-112">Activar la generación de mapa del sitio</span><span class="sxs-lookup"><span data-stu-id="0efe9-112">Turn on site map generation</span></span>

1. <span data-ttu-id="0efe9-113">Inicie sesión en la herramienta de creación.</span><span class="sxs-lookup"><span data-stu-id="0efe9-113">Sign in to the authoring tool.</span></span>
1. <span data-ttu-id="0efe9-114">En **Sitios**, seleccione **Fabrikam** (o el nombre del sitio).</span><span class="sxs-lookup"><span data-stu-id="0efe9-114">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="0efe9-115">En el panel de navegación de la izquierda, seleccione **Administración de sitios**.</span><span class="sxs-lookup"><span data-stu-id="0efe9-115">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="0efe9-116">Asegúrese de que la opción **Mapas del sitio habilitados** está activada.</span><span class="sxs-lookup"><span data-stu-id="0efe9-116">Make sure that the **Site maps enabled** option is turned on.</span></span>

## <a name="page-metadata"></a><span data-ttu-id="0efe9-117">Metadatos de página</span><span class="sxs-lookup"><span data-stu-id="0efe9-117">Page metadata</span></span>

<span data-ttu-id="0efe9-118">Dynamics 365 Commerce le permite administrar metadatos SEO para páginas individuales.</span><span class="sxs-lookup"><span data-stu-id="0efe9-118">Dynamics 365 Commerce lets you manage SEO metadata for individual pages.</span></span> <span data-ttu-id="0efe9-119">Puede ver y modificar esta información en la sección **Propiedades de SEO** de un contenedor de página.</span><span class="sxs-lookup"><span data-stu-id="0efe9-119">You can view and modify this information in the **SEO Properties** section of a page container.</span></span> <span data-ttu-id="0efe9-120">Se admiten las siguientes propiedades de metadatos SEO:</span><span class="sxs-lookup"><span data-stu-id="0efe9-120">The following SEO metadata properties are supported:</span></span>

- <span data-ttu-id="0efe9-121">Cargo</span><span class="sxs-lookup"><span data-stu-id="0efe9-121">Title</span></span>
- <span data-ttu-id="0efe9-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="0efe9-122">Description</span></span>
- <span data-ttu-id="0efe9-123">Palabras clave SEO</span><span class="sxs-lookup"><span data-stu-id="0efe9-123">SEO keywords</span></span>
- <span data-ttu-id="0efe9-124">Etiquetas de aria</span><span class="sxs-lookup"><span data-stu-id="0efe9-124">Aria labels</span></span>
- <span data-ttu-id="0efe9-125">noindex</span><span class="sxs-lookup"><span data-stu-id="0efe9-125">noindex</span></span>
- <span data-ttu-id="0efe9-126">nofollow</span><span class="sxs-lookup"><span data-stu-id="0efe9-126">nofollow</span></span>
- <span data-ttu-id="0efe9-127">noarchive</span><span class="sxs-lookup"><span data-stu-id="0efe9-127">noarchive</span></span>
- <span data-ttu-id="0efe9-128">nocache</span><span class="sxs-lookup"><span data-stu-id="0efe9-128">nocache</span></span>
- <span data-ttu-id="0efe9-129">noOpenDirectoryProject</span><span class="sxs-lookup"><span data-stu-id="0efe9-129">noOpenDirectoryProject</span></span>
- <span data-ttu-id="0efe9-130">nosnippet</span><span class="sxs-lookup"><span data-stu-id="0efe9-130">nosnippet</span></span>
- <span data-ttu-id="0efe9-131">noImageIndex</span><span class="sxs-lookup"><span data-stu-id="0efe9-131">noImageIndex</span></span>
- <span data-ttu-id="0efe9-132">unavailableAfter</span><span class="sxs-lookup"><span data-stu-id="0efe9-132">unavailableAfter</span></span>

### <a name="modify-page-metadata"></a><span data-ttu-id="0efe9-133">Modificar metadatos de página</span><span class="sxs-lookup"><span data-stu-id="0efe9-133">Modify page metadata</span></span>

<span data-ttu-id="0efe9-134">Para modificar metadatos de página, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0efe9-134">To modify page metadata, follow these steps.</span></span>

1. <span data-ttu-id="0efe9-135">En **Sitios**, seleccione **Fabrikam** (o el nombre del sitio).</span><span class="sxs-lookup"><span data-stu-id="0efe9-135">Under **Sites**, select the **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="0efe9-136">En el panel de navegación de la izquierda, seleccione **Páginas**.</span><span class="sxs-lookup"><span data-stu-id="0efe9-136">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="0efe9-137">Seleccione la página principal para abrirla en el editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="0efe9-137">Select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="0efe9-138">En la barra de comandos, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0efe9-138">On the command bar, select **Edit**.</span></span>
1. <span data-ttu-id="0efe9-139">En el panel de propiedades de la derecha, expanda **Etiquetas META predeterminadas**.</span><span class="sxs-lookup"><span data-stu-id="0efe9-139">In the properties pane on the right, expand **Default metatags**.</span></span>
1. <span data-ttu-id="0efe9-140">Para agregar una nueva etiqueta META, seleccione **Agregar** y después introduzca la etiqueta en el campo.</span><span class="sxs-lookup"><span data-stu-id="0efe9-140">To add a new metatag, select **Add**, and then enter the tag in the field.</span></span> <span data-ttu-id="0efe9-141">Para quitar un etiqueta META existente, seleccione el símbolo de papelera que se encuentra a su derecha.</span><span class="sxs-lookup"><span data-stu-id="0efe9-141">To remove an existing metatag, select the trash can symbol to the right of it.</span></span>
1. <span data-ttu-id="0efe9-142">Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.</span><span class="sxs-lookup"><span data-stu-id="0efe9-142">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="0efe9-143">En el campo **Comentarios**, especifique **Etiquetas META actualizadas** y, a continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0efe9-143">In the **Comments** field, enter **Updated metatags**, and then select **OK**.</span></span>
1. <span data-ttu-id="0efe9-144">Seleccione **Vista previa** para obtener una vista previa de la página.</span><span class="sxs-lookup"><span data-stu-id="0efe9-144">Select **Preview** to preview your page.</span></span> <span data-ttu-id="0efe9-145">Cuando haya terminado, cierre la pestaña de vista previa para volver a la herramienta de creación.</span><span class="sxs-lookup"><span data-stu-id="0efe9-145">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="0efe9-146">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="0efe9-146">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0efe9-147">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="0efe9-147">Additional resources</span></span>

[<span data-ttu-id="0efe9-148">Modificar una página de sitio existente</span><span class="sxs-lookup"><span data-stu-id="0efe9-148">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="0efe9-149">Agregar una página de sitio nueva</span><span class="sxs-lookup"><span data-stu-id="0efe9-149">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="0efe9-150">Seleccionar diseños de página</span><span class="sxs-lookup"><span data-stu-id="0efe9-150">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="0efe9-151">Guardar, obtener una vista previa y publicar una página</span><span class="sxs-lookup"><span data-stu-id="0efe9-151">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="0efe9-152">Enriquecer una página de producto</span><span class="sxs-lookup"><span data-stu-id="0efe9-152">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="0efe9-153">Enriquecer una página de aterrizaje de categoría</span><span class="sxs-lookup"><span data-stu-id="0efe9-153">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="0efe9-154">Verificar accesibilidad de contenido de página</span><span class="sxs-lookup"><span data-stu-id="0efe9-154">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="0efe9-155">Crear páginas de comercio electrónico dinámicas basadas en parámetros de URL</span><span class="sxs-lookup"><span data-stu-id="0efe9-155">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
