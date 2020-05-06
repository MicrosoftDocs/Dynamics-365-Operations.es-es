---
title: Enriquecer una página de producto
description: En este tema se describe cómo enriquecer una página de producto en Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 04/14/2020
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
ms.openlocfilehash: 12508a80c440894ec6e2073b5e550846480e6c45
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269829"
---
# <a name="enrich-a-product-page"></a><span data-ttu-id="f7f5c-103">Enriquecer una página de producto</span><span class="sxs-lookup"><span data-stu-id="f7f5c-103">Enrich a product page</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="f7f5c-104">En este tema se describe cómo enriquecer una página de producto en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-104">This topic describes how to enrich a product page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f7f5c-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="f7f5c-105">Overview</span></span>

<span data-ttu-id="f7f5c-106">De forma predeterminada, el sitio utiliza una página genérica para mostrar los datos del producto.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-106">By default, your site uses a generic page to show product data.</span></span> <span data-ttu-id="f7f5c-107">Esta página incluye la información básica acerca del producto y los controles que se requieren para venderlo.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-107">This page includes the basic information about the product and the controls that are required to sell it.</span></span> <span data-ttu-id="f7f5c-108">Sin embargo, puede complementar la información proveniente de Commerce Scale Unit con texto o imágenes adicionales para un producto específico.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-108">However, you can supplement the information that comes from the Commerce Scale Unit with additional images or text for a specific product.</span></span> <span data-ttu-id="f7f5c-109">Este proceso se conoce como enriquecimiento de la página del producto.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-109">This process is known as enriching the product page.</span></span>

<span data-ttu-id="f7f5c-110">En muchos casos, deseará usar contenido adicional específico para sus productos.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-110">In many cases, you will want to use specific additional content for your products.</span></span> <span data-ttu-id="f7f5c-111">Cuando vaya a **Retail y Commerce** en la herramienta de creación, verá una lista de productos del canal que se asigna al sitio.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-111">When you go to **Retail and Commerce** in the authoring tool, you will see a list of products from the channel that is assigned to the site.</span></span> <span data-ttu-id="f7f5c-112">En esta lista, la columna **Enriquecido** indica si se ha enriquecido la página del producto para un producto.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-112">In this list, the **Enriched** column indicates whether the product page for a product has been enriched.</span></span> <span data-ttu-id="f7f5c-113">Si aparece una marca de verificación en la columna, existe una página enriquecida del producto para el producto.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-113">If a check mark appears in the column, an enriched product page exists for the product.</span></span> <span data-ttu-id="f7f5c-114">Si aparece ninguna marca de verificación, la página y el contenido predeterminados del producto se usan para el producto.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-114">If no check mark appears, the default product page and content are used for the product.</span></span> <span data-ttu-id="f7f5c-115">Puede obtener una vista preliminar de las páginas tanto enriquecidas como no enriquecidas del producto seleccionando un nombre del producto en la lista.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-115">You can preview both enriched and non-enriched product pages by selecting a product name in the list.</span></span>

## <a name="enrich-a-product-page"></a><span data-ttu-id="f7f5c-116">Enriquecer una página de producto</span><span class="sxs-lookup"><span data-stu-id="f7f5c-116">Enrich a product page</span></span>

<span data-ttu-id="f7f5c-117">Para enriquecer un página del producto, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-117">To enrich a product page, follow these steps.</span></span>

1. <span data-ttu-id="f7f5c-118">En **Sitios**, seleccione **Fabrikam** (o el nombre del sitio).</span><span class="sxs-lookup"><span data-stu-id="f7f5c-118">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="f7f5c-119">En el panel de navegación de la izquierda, seleccione **Productos**.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-119">In the navigation pane on the left, select **Products**.</span></span>
1. <span data-ttu-id="f7f5c-120">Seleccione los productos que no tengan una página enriquecida del producto.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-120">Select any product that doesn't have an enriched product page.</span></span>
1. <span data-ttu-id="f7f5c-121">En el panel de acciones, seleccione **Enriquecer página de producto**.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-121">On the Action Pane, select **Enrich product page**.</span></span>
1. <span data-ttu-id="f7f5c-122">Seleccione **Plantilla de PDP** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-122">Select **PDP-template**, and then select **OK**.</span></span>
1. <span data-ttu-id="f7f5c-123">En el árbol del esquema de página de la izquierda, expanda la franja **Principal**.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-123">In the page outline tree on the left, expand the **Main** slot.</span></span>
1. <span data-ttu-id="f7f5c-124">Seleccione el botón de puntos suspensivos (**...**) para la franja **Principal** y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-124">Select the ellipsis button (**...**) for the **Main** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="f7f5c-125">Seleccione **Contenedor 2** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-125">Select **Container 2**, and then select **OK**.</span></span>
1. <span data-ttu-id="f7f5c-126">Seleccione el botón de puntos suspensivos para **Contenedor 2** y **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-126">Select the ellipsis button for **Container 2**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="f7f5c-127">Seleccione **Característica** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-127">Select **Feature**, and then select **OK**.</span></span>
1. <span data-ttu-id="f7f5c-128">En el panel de propiedades de la derecha, en el campo **Texto enriquecido**, escriba la descripción actualizada de producto.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-128">In the properties pane on the right, in the **Rich Text** field, enter the updated description of the product.</span></span>
1. <span data-ttu-id="f7f5c-129">En el campo **Encabezado**, inserte el texto del encabezado y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-129">In the **Heading** field, enter heading text, and then select **OK**.</span></span>
1. <span data-ttu-id="f7f5c-130">Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-130">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="f7f5c-131">En el campo **Comentarios**, especifique **Enriquecer** y, a continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-131">In the **Comments** field, enter **Enriched a product**, and then select **OK**.</span></span>
1. <span data-ttu-id="f7f5c-132">Seleccione **Vista previa** para obtener una vista previa de la página enriquecida del producto.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-132">Select **Preview** to preview the enriched product page.</span></span> <span data-ttu-id="f7f5c-133">Cuando haya terminado, cierre la pestaña de vista previa para volver a la herramienta de creación.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-133">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="f7f5c-134">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="f7f5c-134">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f7f5c-135">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f7f5c-135">Additional resources</span></span>

[<span data-ttu-id="f7f5c-136">Modificar una página de sitio existente</span><span class="sxs-lookup"><span data-stu-id="f7f5c-136">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="f7f5c-137">Agregar una página de sitio nueva</span><span class="sxs-lookup"><span data-stu-id="f7f5c-137">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="f7f5c-138">Seleccionar diseños de página</span><span class="sxs-lookup"><span data-stu-id="f7f5c-138">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="f7f5c-139">Administrar metadatos de SEO</span><span class="sxs-lookup"><span data-stu-id="f7f5c-139">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="f7f5c-140">Guardar, obtener una vista previa y publicar una página</span><span class="sxs-lookup"><span data-stu-id="f7f5c-140">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="f7f5c-141">Enriquecer una página de aterrizaje de categoría</span><span class="sxs-lookup"><span data-stu-id="f7f5c-141">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="f7f5c-142">Verificar accesibilidad de contenido de página</span><span class="sxs-lookup"><span data-stu-id="f7f5c-142">Verify page content accessibility</span></span>](verify-accessibility.md)
