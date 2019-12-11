---
title: Enriquecer una página de producto
description: En este tema se describe cómo enriquecer una página de producto en Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: ef9e65b2027a41ca152afaf20ac2fb9a69cd9b96
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698151"
---
# <a name="enrich-a-product-page"></a><span data-ttu-id="9c8f0-103">Enriquecer una página de producto</span><span class="sxs-lookup"><span data-stu-id="9c8f0-103">Enrich a product page</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="9c8f0-104">En este tema se describe cómo enriquecer una página de producto en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-104">This topic describes how to enrich a product page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9c8f0-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="9c8f0-105">Overview</span></span>

<span data-ttu-id="9c8f0-106">De forma predeterminada, el sitio utiliza una página genérica para mostrar los datos del producto.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-106">By default, your site uses a generic page to show product data.</span></span> <span data-ttu-id="9c8f0-107">Esta página incluye la información básica acerca del producto y los controles que se requieren para venderlo.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-107">This page includes the basic information about the product and the controls that are required to sell it.</span></span> <span data-ttu-id="9c8f0-108">Sin embargo, puede complementar la información proveniente de Retail Server con texto o imágenes adicionales para un producto específico.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-108">However, you can supplement the information that comes from the Retail Server with additional images or text for a specific product.</span></span> <span data-ttu-id="9c8f0-109">Este proceso se conoce como enriquecimiento de la página del producto.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-109">This process is known as enriching the product page.</span></span>

<span data-ttu-id="9c8f0-110">En muchos casos, deseará usar contenido adicional específico para sus productos.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-110">In many cases, you will want to use specific additional content for your products.</span></span> <span data-ttu-id="9c8f0-111">Cuando vaya a **Retail** en la herramienta de creación, verá una lista de productos del canal que se asigna al sitio.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-111">When you go to **Retail** in the authoring tool, you will see a list of products from the channel that is assigned to the site.</span></span> <span data-ttu-id="9c8f0-112">En esta lista, la columna **Enriquecido** indica si se ha enriquecido la página del producto para un producto.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-112">In this list, the **Enriched** column indicates whether the product page for a product has been enriched.</span></span> <span data-ttu-id="9c8f0-113">Si aparece una marca de verificación en la columna, existe una página enriquecida del producto para el producto.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-113">If a check mark appears in the column, an enriched product page exists for the product.</span></span> <span data-ttu-id="9c8f0-114">Si aparece ninguna marca de verificación, la página y el contenido predeterminados del producto se usan para el producto.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-114">If no check mark appears, the default product page and content are used for the product.</span></span> <span data-ttu-id="9c8f0-115">Puede obtener una vista preliminar de las páginas tanto enriquecidas como no enriquecidas del producto seleccionando un nombre del producto en la lista.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-115">You can preview both enriched and non-enriched product pages by selecting a product name in the list.</span></span>

## <a name="enrich-a-product-page"></a><span data-ttu-id="9c8f0-116">Enriquecer una página de producto</span><span class="sxs-lookup"><span data-stu-id="9c8f0-116">Enrich a product page</span></span>

<span data-ttu-id="9c8f0-117">Para enriquecer un página del producto, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-117">To enrich a product page, follow these steps.</span></span>

1. <span data-ttu-id="9c8f0-118">En **Sitios**, seleccione **Fabrikam** (o el nombre del sitio).</span><span class="sxs-lookup"><span data-stu-id="9c8f0-118">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="9c8f0-119">En el panel de navegación de la izquierda, seleccione **Productos**.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-119">In the navigation pane on the left, select **Products**.</span></span>
1. <span data-ttu-id="9c8f0-120">Seleccione los productos que no tengan una página enriquecida del producto.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-120">Select any product that doesn't have an enriched product page.</span></span>
1. <span data-ttu-id="9c8f0-121">En el panel de acciones, seleccione **Enriquecer página de producto**.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-121">On the Action Pane, select **Enrich product page**.</span></span>
1. <span data-ttu-id="9c8f0-122">Seleccione **Plantilla de PDP** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-122">Select **PDP-template**, and then select **OK**.</span></span>
1. <span data-ttu-id="9c8f0-123">En el árbol del esquema de página de la izquierda, expanda la franja **Principal**.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-123">In the page outline tree on the left, expand the **Main** slot.</span></span>
1. <span data-ttu-id="9c8f0-124">Seleccione el botón de puntos suspensivos (**...**) para la franja **Principal** y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-124">Select the ellipsis button (**...**) for the **Main** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="9c8f0-125">Seleccione **Contenedor 2** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-125">Select **Container 2**, and then select **OK**.</span></span>
1. <span data-ttu-id="9c8f0-126">Seleccione el botón de puntos suspensivos para **Contenedor 2** y **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-126">Select the ellipsis button for **Container 2**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="9c8f0-127">Seleccione **Característica** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-127">Select **Feature**, and then select **OK**.</span></span>
1. <span data-ttu-id="9c8f0-128">En el panel de propiedades de la derecha, en el campo **Texto enriquecido**, escriba la descripción actualizada de producto.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-128">In the properties pane on the right, in the **Rich Text** field, enter the updated description of the product.</span></span>
1. <span data-ttu-id="9c8f0-129">En el campo **Encabezado**, inserte el texto del encabezado y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-129">In the **Heading** field, enter heading text, and then select **OK**.</span></span>
1. <span data-ttu-id="9c8f0-130">Seleccione **Guardar** y, a continuación, seleccione **Proteger**.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-130">Select **Save**, and then select **Check In**.</span></span>
1. <span data-ttu-id="9c8f0-131">En el campo **Comentarios**, especifique **Enriquecer** y, a continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-131">In the **Comments** field, enter **Enriched a product**, and then select **OK**.</span></span>
1. <span data-ttu-id="9c8f0-132">Seleccione **Vista previa** para obtener una vista previa de la página enriquecida del producto.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-132">Select **Preview** to preview the enriched product page.</span></span> <span data-ttu-id="9c8f0-133">Cuando haya terminado, cierre la pestaña de vista previa para volver a la herramienta de creación.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-133">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="9c8f0-134">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="9c8f0-134">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9c8f0-135">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9c8f0-135">Additional resources</span></span>

[<span data-ttu-id="9c8f0-136">Modificar una página de sitio existente</span><span class="sxs-lookup"><span data-stu-id="9c8f0-136">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="9c8f0-137">Agregar una página de sitio nueva</span><span class="sxs-lookup"><span data-stu-id="9c8f0-137">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="9c8f0-138">Seleccionar diseños de página</span><span class="sxs-lookup"><span data-stu-id="9c8f0-138">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="9c8f0-139">Administrar metadatos de SEO</span><span class="sxs-lookup"><span data-stu-id="9c8f0-139">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="9c8f0-140">Guardar, obtener una vista previa y publicar una página</span><span class="sxs-lookup"><span data-stu-id="9c8f0-140">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="9c8f0-141">Enriquecer una página de aterrizaje de categoría</span><span class="sxs-lookup"><span data-stu-id="9c8f0-141">Enrich a category landing page</span></span>](enrich-category-page.md)

