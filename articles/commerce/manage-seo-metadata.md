---
title: Administrar metadatos de SEO
description: Este tema describe cómo administrar los metadatos de la optimización de motor de búsqueda (SEO) en Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 1e7da7bf5c473746413e92babfa943f546b7724d
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3003473"
---
# <a name="manage-seo-metadata"></a><span data-ttu-id="0fe15-103">Administrar metadatos de SEO</span><span class="sxs-lookup"><span data-stu-id="0fe15-103">Manage SEO metadata</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="0fe15-104">Este tema describe cómo administrar los metadatos de la optimización de motor de búsqueda (SEO) en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0fe15-104">This topic describes how to manage search engine optimization (SEO) metadata in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="0fe15-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="0fe15-105">Overview</span></span>

<span data-ttu-id="0fe15-106">Los metadatos SEO para un sitio se pueden administrar mediante mapas de sitio y metadatos de página.</span><span class="sxs-lookup"><span data-stu-id="0fe15-106">SEO metadata for a site can be managed by using site maps and page metadata.</span></span>
    
## <a name="site-maps"></a><span data-ttu-id="0fe15-107">Mapas del sitio</span><span class="sxs-lookup"><span data-stu-id="0fe15-107">Site maps</span></span>

<span data-ttu-id="0fe15-108">Un mapa del sitio es una lista legible, en formato XML, de las páginas de su sitio web.</span><span class="sxs-lookup"><span data-stu-id="0fe15-108">A site map is a machine-readable list, in XML format, of the pages on your website.</span></span> <span data-ttu-id="0fe15-109">Se ha pensado para ser consumido por motores de búsqueda, de modo que puedan proporcionar mejores resultados de la búsqueda desde el sitio.</span><span class="sxs-lookup"><span data-stu-id="0fe15-109">It's intended to be consumed by search engines, so that they can provide better search results from your site.</span></span> <span data-ttu-id="0fe15-110">Los mapas del sitio se pueden ingerir manualmente por motores de búsqueda o publicarse en un archivo robots.txt.</span><span class="sxs-lookup"><span data-stu-id="0fe15-110">Site maps can be manually ingested by search engines or published in a robots.txt file.</span></span>

<span data-ttu-id="0fe15-111">Dynamics 365 Commerce admite la creación automática de mapas del sitio.</span><span class="sxs-lookup"><span data-stu-id="0fe15-111">Dynamics 365 Commerce supports automatic generation of site maps.</span></span> <span data-ttu-id="0fe15-112">Los mapas del sitio se actualizan automáticamente cuando las páginas se publican y se cancela su publicación.</span><span class="sxs-lookup"><span data-stu-id="0fe15-112">Site maps are automatically updated when pages are published and unpublished.</span></span>

### <a name="turn-on-site-map-generation"></a><span data-ttu-id="0fe15-113">Activar la generación de mapa del sitio</span><span class="sxs-lookup"><span data-stu-id="0fe15-113">Turn on site map generation</span></span>

1. <span data-ttu-id="0fe15-114">Inicie sesión en la herramienta de creación.</span><span class="sxs-lookup"><span data-stu-id="0fe15-114">Sign in to the authoring tool.</span></span>
1. <span data-ttu-id="0fe15-115">En **Sitios**, seleccione **Fabrikam** (o el nombre del sitio).</span><span class="sxs-lookup"><span data-stu-id="0fe15-115">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="0fe15-116">En el panel de navegación de la izquierda, seleccione **Administración de sitios**.</span><span class="sxs-lookup"><span data-stu-id="0fe15-116">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="0fe15-117">Asegúrese de que la opción **Mapas del sitio habilitados** está activada.</span><span class="sxs-lookup"><span data-stu-id="0fe15-117">Make sure that the **Site maps enabled** option is turned on.</span></span>

## <a name="page-metadata"></a><span data-ttu-id="0fe15-118">Metadatos de página</span><span class="sxs-lookup"><span data-stu-id="0fe15-118">Page metadata</span></span>

<span data-ttu-id="0fe15-119">Dynamics 365 Commerce le permite administrar metadatos SEO para páginas individuales.</span><span class="sxs-lookup"><span data-stu-id="0fe15-119">Dynamics 365 Commerce lets you manage SEO metadata for individual pages.</span></span> <span data-ttu-id="0fe15-120">Puede ver y modificar esta información en la sección **Propiedades de SEO** de un contenedor de página.</span><span class="sxs-lookup"><span data-stu-id="0fe15-120">You can view and modify this information in the **SEO Properties** section of a page container.</span></span> <span data-ttu-id="0fe15-121">Se admiten las siguientes propiedades de metadatos SEO:</span><span class="sxs-lookup"><span data-stu-id="0fe15-121">The following SEO metadata properties are supported:</span></span>

- <span data-ttu-id="0fe15-122">Cargo</span><span class="sxs-lookup"><span data-stu-id="0fe15-122">Title</span></span>
- <span data-ttu-id="0fe15-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="0fe15-123">Description</span></span>
- <span data-ttu-id="0fe15-124">Palabras clave SEO</span><span class="sxs-lookup"><span data-stu-id="0fe15-124">SEO keywords</span></span>
- <span data-ttu-id="0fe15-125">Etiquetas de aria</span><span class="sxs-lookup"><span data-stu-id="0fe15-125">Aria labels</span></span>
- <span data-ttu-id="0fe15-126">noindex</span><span class="sxs-lookup"><span data-stu-id="0fe15-126">noindex</span></span>
- <span data-ttu-id="0fe15-127">nofollow</span><span class="sxs-lookup"><span data-stu-id="0fe15-127">nofollow</span></span>
- <span data-ttu-id="0fe15-128">noarchive</span><span class="sxs-lookup"><span data-stu-id="0fe15-128">noarchive</span></span>
- <span data-ttu-id="0fe15-129">nocache</span><span class="sxs-lookup"><span data-stu-id="0fe15-129">nocache</span></span>
- <span data-ttu-id="0fe15-130">noOpenDirectoryProject</span><span class="sxs-lookup"><span data-stu-id="0fe15-130">noOpenDirectoryProject</span></span>
- <span data-ttu-id="0fe15-131">nosnippet</span><span class="sxs-lookup"><span data-stu-id="0fe15-131">nosnippet</span></span>
- <span data-ttu-id="0fe15-132">noImageIndex</span><span class="sxs-lookup"><span data-stu-id="0fe15-132">noImageIndex</span></span>
- <span data-ttu-id="0fe15-133">unavailableAfter</span><span class="sxs-lookup"><span data-stu-id="0fe15-133">unavailableAfter</span></span>

### <a name="modify-page-metadata"></a><span data-ttu-id="0fe15-134">Modificar metadatos de página</span><span class="sxs-lookup"><span data-stu-id="0fe15-134">Modify page metadata</span></span>

<span data-ttu-id="0fe15-135">Para modificar metadatos de página, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0fe15-135">To modify page metadata, follow these steps.</span></span>

1. <span data-ttu-id="0fe15-136">En **Sitios**, seleccione **Fabrikam** (o el nombre del sitio).</span><span class="sxs-lookup"><span data-stu-id="0fe15-136">Under **Sites**, select the **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="0fe15-137">En el panel de navegación de la izquierda, seleccione **Páginas**.</span><span class="sxs-lookup"><span data-stu-id="0fe15-137">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="0fe15-138">Seleccione la página principal para abrirla en el editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="0fe15-138">Select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="0fe15-139">En el panel de acciones, seleccione **Desproteger**.</span><span class="sxs-lookup"><span data-stu-id="0fe15-139">On the Action Pane, select **Check Out**.</span></span>
1. <span data-ttu-id="0fe15-140">En el panel de propiedades de la derecha, expanda **Etiquetas META predeterminadas**.</span><span class="sxs-lookup"><span data-stu-id="0fe15-140">In the properties pane on the right, expand **Default metatags**.</span></span>
1. <span data-ttu-id="0fe15-141">Para agregar una nueva etiqueta META, seleccione **Agregar** y después introduzca la etiqueta en el campo.</span><span class="sxs-lookup"><span data-stu-id="0fe15-141">To add a new metatag, select **Add**, and then enter the tag in the field.</span></span>

    <span data-ttu-id="0fe15-142">Para quitar un etiqueta META existente, seleccione el símbolo de papelera que se encuentra a su derecha.</span><span class="sxs-lookup"><span data-stu-id="0fe15-142">To remove an existing metatag, select the trash can symbol to the right of it.</span></span>

1. <span data-ttu-id="0fe15-143">Seleccione **Guardar** y, a continuación, seleccione **Proteger**.</span><span class="sxs-lookup"><span data-stu-id="0fe15-143">Select **Save**, and then select **Check In**.</span></span>
1. <span data-ttu-id="0fe15-144">En el campo **Comentarios**, especifique **Etiquetas META actualizadas** y, a continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0fe15-144">In the **Comments** field, enter **Updated metatags**, and then select **OK**.</span></span>
1. <span data-ttu-id="0fe15-145">Seleccione **Vista previa** para obtener una vista previa de la página.</span><span class="sxs-lookup"><span data-stu-id="0fe15-145">Select **Preview** to preview your page.</span></span> <span data-ttu-id="0fe15-146">Cuando haya terminado, cierre la pestaña de vista previa para volver a la herramienta de creación.</span><span class="sxs-lookup"><span data-stu-id="0fe15-146">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="0fe15-147">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="0fe15-147">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0fe15-148">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="0fe15-148">Additional resources</span></span>

[<span data-ttu-id="0fe15-149">Modificar una página de sitio existente</span><span class="sxs-lookup"><span data-stu-id="0fe15-149">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="0fe15-150">Agregar una página de sitio nueva</span><span class="sxs-lookup"><span data-stu-id="0fe15-150">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="0fe15-151">Seleccionar diseños de página</span><span class="sxs-lookup"><span data-stu-id="0fe15-151">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="0fe15-152">Guardar, obtener una vista previa y publicar una página</span><span class="sxs-lookup"><span data-stu-id="0fe15-152">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="0fe15-153">Enriquecer una página de producto</span><span class="sxs-lookup"><span data-stu-id="0fe15-153">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="0fe15-154">Enriquecer una página de aterrizaje de categoría</span><span class="sxs-lookup"><span data-stu-id="0fe15-154">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="0fe15-155">Verificar accesibilidad de contenido de página</span><span class="sxs-lookup"><span data-stu-id="0fe15-155">Verify page content accessibility</span></span>](verify-accessibility.md)
