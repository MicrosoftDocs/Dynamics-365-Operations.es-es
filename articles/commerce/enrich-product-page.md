---
title: Enriquecer una página de producto
description: En este tema se describe cómo enriquecer una página de producto en Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: f6c1a9474ed514426386b1d7b4a72b62129cdb8a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799062"
---
# <a name="enrich-a-product-page"></a><span data-ttu-id="0a6c1-103">Enriquecer una página de producto</span><span class="sxs-lookup"><span data-stu-id="0a6c1-103">Enrich a product page</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0a6c1-104">En este tema se describe cómo enriquecer una página de producto en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-104">This topic describes how to enrich a product page in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="0a6c1-105">De forma predeterminada, el sitio utiliza una página genérica para mostrar los datos del producto.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-105">By default, your site uses a generic page to show product data.</span></span> <span data-ttu-id="0a6c1-106">Esta página incluye la información básica acerca del producto y los controles que se requieren para venderlo.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-106">This page includes the basic information about the product and the controls that are required to sell it.</span></span> <span data-ttu-id="0a6c1-107">Sin embargo, puede complementar la información proveniente de Commerce Scale Unit con texto o imágenes adicionales para un producto específico.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-107">However, you can supplement the information that comes from the Commerce Scale Unit with additional images or text for a specific product.</span></span> <span data-ttu-id="0a6c1-108">Este proceso se conoce como enriquecimiento de la página del producto.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-108">This process is known as enriching the product page.</span></span>

<span data-ttu-id="0a6c1-109">En muchos casos, deseará usar contenido adicional específico para sus productos.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-109">In many cases, you will want to use specific additional content for your products.</span></span> <span data-ttu-id="0a6c1-110">Cuando vaya a **Retail y Commerce** en la herramienta de creación, verá una lista de productos del canal que se asigna al sitio.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-110">When you go to **Retail and Commerce** in the authoring tool, you will see a list of products from the channel that is assigned to the site.</span></span> <span data-ttu-id="0a6c1-111">En esta lista, la columna **Enriquecido** indica si se ha enriquecido la página del producto para un producto.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-111">In this list, the **Enriched** column indicates whether the product page for a product has been enriched.</span></span> <span data-ttu-id="0a6c1-112">Si aparece una marca de verificación en la columna, existe una página enriquecida del producto para el producto.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-112">If a check mark appears in the column, an enriched product page exists for the product.</span></span> <span data-ttu-id="0a6c1-113">Si aparece ninguna marca de verificación, la página y el contenido predeterminados del producto se usan para el producto.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-113">If no check mark appears, the default product page and content are used for the product.</span></span> <span data-ttu-id="0a6c1-114">Puede obtener una vista preliminar de las páginas tanto enriquecidas como no enriquecidas del producto seleccionando un nombre del producto en la lista.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-114">You can preview both enriched and non-enriched product pages by selecting a product name in the list.</span></span>

## <a name="enrich-a-product-page"></a><span data-ttu-id="0a6c1-115">Enriquecer una página de producto</span><span class="sxs-lookup"><span data-stu-id="0a6c1-115">Enrich a product page</span></span>

<span data-ttu-id="0a6c1-116">Para enriquecer un página del producto, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-116">To enrich a product page, follow these steps.</span></span>

1. <span data-ttu-id="0a6c1-117">En **Sitios**, seleccione **Fabrikam** (o el nombre del sitio).</span><span class="sxs-lookup"><span data-stu-id="0a6c1-117">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="0a6c1-118">En el panel de navegación de la izquierda, seleccione **Productos**.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-118">In the navigation pane on the left, select **Products**.</span></span>
1. <span data-ttu-id="0a6c1-119">Seleccione los productos que no tengan una página enriquecida del producto.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-119">Select any product that doesn't have an enriched product page.</span></span>
1. <span data-ttu-id="0a6c1-120">En el panel de acciones, seleccione **Enriquecer página de producto**.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-120">On the Action Pane, select **Enrich product page**.</span></span>
1. <span data-ttu-id="0a6c1-121">Seleccione **Plantilla de PDP** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-121">Select **PDP-template**, and then select **OK**.</span></span>
1. <span data-ttu-id="0a6c1-122">En el árbol del esquema de página de la izquierda, expanda la franja **Principal**.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-122">In the page outline tree on the left, expand the **Main** slot.</span></span>
1. <span data-ttu-id="0a6c1-123">Seleccione el botón de puntos suspensivos (**...**) para la franja **Principal** y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-123">Select the ellipsis button (**...**) for the **Main** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="0a6c1-124">Seleccione **Contenedor 2** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-124">Select **Container 2**, and then select **OK**.</span></span>
1. <span data-ttu-id="0a6c1-125">Seleccione el botón de puntos suspensivos para **Contenedor 2** y **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-125">Select the ellipsis button for **Container 2**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="0a6c1-126">Seleccione **Característica** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-126">Select **Feature**, and then select **OK**.</span></span>
1. <span data-ttu-id="0a6c1-127">En el panel de propiedades de la derecha, en el campo **Texto enriquecido**, escriba la descripción actualizada de producto.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-127">In the properties pane on the right, in the **Rich Text** field, enter the updated description of the product.</span></span>
1. <span data-ttu-id="0a6c1-128">En el campo **Encabezado**, inserte el texto del encabezado y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-128">In the **Heading** field, enter heading text, and then select **OK**.</span></span>
1. <span data-ttu-id="0a6c1-129">Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-129">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="0a6c1-130">En el campo **Comentarios**, especifique **Enriquecer** y, a continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-130">In the **Comments** field, enter **Enriched a product**, and then select **OK**.</span></span>
1. <span data-ttu-id="0a6c1-131">Seleccione **Vista previa** para obtener una vista previa de la página enriquecida del producto.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-131">Select **Preview** to preview the enriched product page.</span></span> <span data-ttu-id="0a6c1-132">Cuando haya terminado, cierre la pestaña de vista previa para volver a la herramienta de creación.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-132">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="0a6c1-133">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="0a6c1-133">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0a6c1-134">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="0a6c1-134">Additional resources</span></span>

[<span data-ttu-id="0a6c1-135">Modificar una página de sitio existente</span><span class="sxs-lookup"><span data-stu-id="0a6c1-135">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="0a6c1-136">Agregar una página de sitio nueva</span><span class="sxs-lookup"><span data-stu-id="0a6c1-136">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="0a6c1-137">Seleccionar diseños de página</span><span class="sxs-lookup"><span data-stu-id="0a6c1-137">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="0a6c1-138">Administrar metadatos de SEO</span><span class="sxs-lookup"><span data-stu-id="0a6c1-138">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="0a6c1-139">Guardar, obtener una vista previa y publicar una página</span><span class="sxs-lookup"><span data-stu-id="0a6c1-139">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="0a6c1-140">Enriquecer una página de aterrizaje de categoría</span><span class="sxs-lookup"><span data-stu-id="0a6c1-140">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="0a6c1-141">Verificar accesibilidad de contenido de página</span><span class="sxs-lookup"><span data-stu-id="0a6c1-141">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="0a6c1-142">Crear páginas de comercio electrónico dinámicas basadas en parámetros de URL</span><span class="sxs-lookup"><span data-stu-id="0a6c1-142">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
