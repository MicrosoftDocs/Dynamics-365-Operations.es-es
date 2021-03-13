---
title: Enriquecer una página de aterrizaje de categoría
description: Este tema aborda el enriquecimiento de páginas de categoría en Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 96fbd7c2ddfcd43e38e9572a60873d5f5930c94c
ms.sourcegitcommit: 872600103d2a444d78963867e5e0cdc62e68c3ec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2021
ms.locfileid: "5097238"
---
# <a name="enrich-a-category-landing-page"></a><span data-ttu-id="de738-103">Enriquecer una página de aterrizaje de categoría</span><span class="sxs-lookup"><span data-stu-id="de738-103">Enrich a category landing page</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="de738-104">Este tema aborda el enriquecimiento de páginas de categoría en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="de738-104">This topic covers the enrichment of category pages in Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="de738-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="de738-105">Overview</span></span>

<span data-ttu-id="de738-106">Commerce proporciona una página de aterrizaje de categoría predeterminada que se utiliza cuando se muestra los datos de categoría.</span><span class="sxs-lookup"><span data-stu-id="de738-106">Commerce provides a default category landing page that is used when category data is shown.</span></span> <span data-ttu-id="de738-107">Una página de categoría predeterminada contiene elementos necesarios, como refinadores, ubicación de producto categorizada, opciones de ordenación, resumen de opciones y controles de paginación.</span><span class="sxs-lookup"><span data-stu-id="de738-107">A default category page contains required elements, such as refiners, categorized product placement, sorting options, a choice summary, and pagination controls.</span></span> 

<span data-ttu-id="de738-108">Sin embargo, en lugar de usar la página de categoría predeterminada, es posible que desee usar una página de aterrizaje de categoría “enriquecida” que tenga más contenido y más elementos específicos.</span><span class="sxs-lookup"><span data-stu-id="de738-108">However, instead of using the default category page, you might want to use an "enriched" category landing page that has more content and more specific elements.</span></span> <span data-ttu-id="de738-109">Un enriquecimiento típico puede implicar la adición de contenido de marketing específico de categoría a la página de categoría.</span><span class="sxs-lookup"><span data-stu-id="de738-109">A typical enrichment might involve adding category-specific marketing content to the category page.</span></span> <span data-ttu-id="de738-110">Este contenido podría incluir la ubicación de productos entre categorías para fines de venta cruzada, listas editoriales, imágenes, vídeos y otro texto.</span><span class="sxs-lookup"><span data-stu-id="de738-110">This content might include cross-category product placement for cross-sell purposes, editorial lists, images, videos, and other text.</span></span> <span data-ttu-id="de738-111">Puede modificar la página de categoría predeterminada o definir una página de categoría diferente para una categoría específica.</span><span class="sxs-lookup"><span data-stu-id="de738-111">You can either modify the default category page or define a different category page for a specific category.</span></span>

![Página de aterrizaje de categoría enriquecida](./media/CategoryLandingPages.png)

<span data-ttu-id="de738-113">En el generador de sitios de Commerce, la página **Productos** incluye una lista de categorías del canal que se asignan al sitio.</span><span class="sxs-lookup"><span data-stu-id="de738-113">In Commerce site builder, the **Products** page includes a list of categories from the channel that are assigned to the site.</span></span> <span data-ttu-id="de738-114">Si el estado **Enriquecido** está seleccionado para una página de categoría, se ha enriquecido esa página de categoría.</span><span class="sxs-lookup"><span data-stu-id="de738-114">If the **Enriched** status is selected for a category page, that category page has been enriched.</span></span> <span data-ttu-id="de738-115">De lo contrario, la página de categoría predeterminada y el contenido se utilizan para la categoría.</span><span class="sxs-lookup"><span data-stu-id="de738-115">Otherwise, the default category page and content are used for the category.</span></span> <span data-ttu-id="de738-116">Puede obtener una vista preliminar de las páginas de categoría enriquecidas y no enriquecidas para una categoría seleccionando el nombre de la categoría.</span><span class="sxs-lookup"><span data-stu-id="de738-116">You can preview both the enriched and non-enriched category pages for a category by selecting the category name.</span></span>

<span data-ttu-id="de738-117">Para enriquecer una página de categoría, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="de738-117">To enrich a category page, do the following.</span></span>

1. <span data-ttu-id="de738-118">En la página **Productos**, seleccione el nombre de la categoría para la que desea enriquecer la página de categoría.</span><span class="sxs-lookup"><span data-stu-id="de738-118">On the **Products** page, select the name of the category for which you want to enrich the category page.</span></span> <span data-ttu-id="de738-119">La página de categoría predeterminada para la categoría seleccionada se abre en el editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="de738-119">The default category page for the selected category is opened in the page editor.</span></span>
2. <span data-ttu-id="de738-120">Seleccione **Enriquecer una página de categoría**.</span><span class="sxs-lookup"><span data-stu-id="de738-120">Select **Enrich category page**.</span></span>
3. <span data-ttu-id="de738-121">Seleccione una plantilla para la página de categoría enriquecida.</span><span class="sxs-lookup"><span data-stu-id="de738-121">Select a template for the enriched category page.</span></span> <span data-ttu-id="de738-122">Si está realizando solo cambios de menor importancia, puede seleccionar la página de categoría predeterminada.</span><span class="sxs-lookup"><span data-stu-id="de738-122">If you're making only minor changes, you can select the default category page.</span></span> <span data-ttu-id="de738-123">También, puede seleccionar una plantilla específica de página de categoría.</span><span class="sxs-lookup"><span data-stu-id="de738-123">Alternatively, you can select a specific category page template.</span></span> <span data-ttu-id="de738-124">Al seleccionar la plantilla, se abre el editor de páginas y la plantilla seleccionada se utiliza para crear una nueva página de categoría para la categoría seleccionada.</span><span class="sxs-lookup"><span data-stu-id="de738-124">When you select the template, the page editor is opened, and the selected template is used to create a new category page for the selected category.</span></span> <span data-ttu-id="de738-125">La página se desprotege para usted y podrá realizar los cambios.</span><span class="sxs-lookup"><span data-stu-id="de738-125">The page is checked out to you, and you can now make your changes.</span></span>

> [!NOTE]
> <span data-ttu-id="de738-126">Los módulos que usan datos de especificación de categoría usan los datos de su categoría seleccionada.</span><span class="sxs-lookup"><span data-stu-id="de738-126">Modules that use category specification data use the data from your selected category.</span></span> <span data-ttu-id="de738-127">La configuración de la plantilla que seleccione determina los cambios que puede realizar.</span><span class="sxs-lookup"><span data-stu-id="de738-127">The settings of the template that you select determine the changes that you can make.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="de738-128">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="de738-128">Additional resources</span></span>

[<span data-ttu-id="de738-129">Modificar una página de sitio existente</span><span class="sxs-lookup"><span data-stu-id="de738-129">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="de738-130">Agregar una página de sitio nueva</span><span class="sxs-lookup"><span data-stu-id="de738-130">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="de738-131">Seleccionar diseños de página</span><span class="sxs-lookup"><span data-stu-id="de738-131">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="de738-132">Administrar metadatos de SEO</span><span class="sxs-lookup"><span data-stu-id="de738-132">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="de738-133">Guardar, obtener una vista previa y publicar una página</span><span class="sxs-lookup"><span data-stu-id="de738-133">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="de738-134">Enriquecer una página de producto</span><span class="sxs-lookup"><span data-stu-id="de738-134">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="de738-135">Verificar accesibilidad de contenido de página</span><span class="sxs-lookup"><span data-stu-id="de738-135">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="de738-136">Crear páginas de comercio electrónico dinámicas basadas en parámetros de URL</span><span class="sxs-lookup"><span data-stu-id="de738-136">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)
