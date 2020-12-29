---
title: Visión general de la página de aterrizaje de categoría predeterminada y la página de resultados de la búsqueda
description: Este tema ofrece una visión general de la página de aterrizaje de categoría predeterminada y la página de resultados de la búsqueda en Dynamics 365 Commerce.
author: ashishmsft
manager: annbe
ms.date: 06/30/2020
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
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e85449c10fa4a768a144ce423a77bd1fc2c94352
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415501"
---
# <a name="default-category-landing-page-and-search-results-page-overview"></a><span data-ttu-id="2788b-103">Visión general de la página de aterrizaje de categoría predeterminada y la página de resultados de la búsqueda</span><span class="sxs-lookup"><span data-stu-id="2788b-103">Default category landing page and search results page overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2788b-104">Este tema ofrece una visión general de la página de aterrizaje de categoría predeterminada y la página de resultados de la búsqueda en comercio electrónico de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2788b-104">This topic provides an overview of the default category landing page and search results page in Microsoft Dynamics 365 Commerce e-Commerce.</span></span>

## <a name="default-category-landing-page"></a><span data-ttu-id="2788b-105">Página de aterrizaje de categoría predeterminada</span><span class="sxs-lookup"><span data-stu-id="2788b-105">Default category landing page</span></span>

<span data-ttu-id="2788b-106">La página de aterrizaje de categoría predeterminada es la página a la que se llevan normalmente a los usuarios de sitio web cuando seleccionan una categoría en la jerarquía de navegación.</span><span class="sxs-lookup"><span data-stu-id="2788b-106">The default category landing page is the page that website users typically are taken to when they select a category in the navigation hierarchy.</span></span> <span data-ttu-id="2788b-107">La página de categoría le permite examinar, y también puede limitar y ordenar los productos clasificados.</span><span class="sxs-lookup"><span data-stu-id="2788b-107">The category page lets you browse, and you can also sort and refine the categorized products.</span></span>

![Página de aterrizaje de categoría predeterminada](./media/SimpleCategoryLandingDressCategory.png)

<span data-ttu-id="2788b-109">En la parte superior de la página se encuentra un encabezado que muestra todas las categorías de producto y otras páginas que el administrador de comercialización ha clasificado.</span><span class="sxs-lookup"><span data-stu-id="2788b-109">At the top of the page is a header that shows all the product categories and other pages that the merchandising manager has categorized.</span></span> <span data-ttu-id="2788b-110">La configuración se realiza como parte de la configuración de la jerarquía de navegación de canal.</span><span class="sxs-lookup"><span data-stu-id="2788b-110">Configuration is done as part of the configuration of the channel navigation hierarchy.</span></span> <span data-ttu-id="2788b-111">En la parte inferior de la página hay un pie de página que incluye vínculos rápidos a diversos temas en los que un comprador puede estar interesado.</span><span class="sxs-lookup"><span data-stu-id="2788b-111">At the bottom of the page is a footer that includes quick links to various topics that a shopper might be interested in.</span></span>

<span data-ttu-id="2788b-112">Los siguientes componentes son esenciales para una categoría:</span><span class="sxs-lookup"><span data-stu-id="2788b-112">The following components are essential for a category:</span></span>

- <span data-ttu-id="2788b-113">**Iconos de colocación de producto** muestran los productos que el administrador de comercialización ha definido en una categoría como parte de la configuración de la jerarquía de navegación.</span><span class="sxs-lookup"><span data-stu-id="2788b-113">**Product placement tiles** show the products that the merchandising manager has defined in a category as part of the configuration of the navigation hierarchy.</span></span>
- <span data-ttu-id="2788b-114">**Refinadores y resumen de opciones** son filtros que proporcionan recuentos y que se pueden utilizar para limitar artículos.</span><span class="sxs-lookup"><span data-stu-id="2788b-114">**Refiners and choice summary** are filters that provide counts and that can be used to refine items.</span></span> <span data-ttu-id="2788b-115">El administrador de comercialización los configura como parte de la configuración de los metadatos relacionados con las categorías de canal y los atributos de producto.</span><span class="sxs-lookup"><span data-stu-id="2788b-115">The merchandising manager configures them as part of the configuration of the metadata related to channel categories and product attributes.</span></span>
- <span data-ttu-id="2788b-116">**Opciones de ordenación** se usan por los visitantes del sitio web para ordenar los productos.</span><span class="sxs-lookup"><span data-stu-id="2788b-116">**Sorting options** are used by website visitors to sort the products.</span></span> <span data-ttu-id="2788b-117">De forma predeterminada, están disponibles las siguientes opciones de ordenación:</span><span class="sxs-lookup"><span data-stu-id="2788b-117">By default, the following sorting options are available:</span></span>

    - <span data-ttu-id="2788b-118">Precio: de menor a mayor</span><span class="sxs-lookup"><span data-stu-id="2788b-118">Price – low to high</span></span>
    - <span data-ttu-id="2788b-119">Precio: de mayor a menor</span><span class="sxs-lookup"><span data-stu-id="2788b-119">Price – high to low</span></span>
    - <span data-ttu-id="2788b-120">Nombre de producto: \[A-Z\]</span><span class="sxs-lookup"><span data-stu-id="2788b-120">Product name – \[A-Z\]</span></span>
    - <span data-ttu-id="2788b-121">Nombre de producto: \[Z-A\]</span><span class="sxs-lookup"><span data-stu-id="2788b-121">Product name – \[Z-A\]</span></span>
    - <span data-ttu-id="2788b-122">Clasificaciones: de menor a mayor</span><span class="sxs-lookup"><span data-stu-id="2788b-122">Ratings – low to high</span></span>
    - <span data-ttu-id="2788b-123">Clasificaciones: de mayor a menor</span><span class="sxs-lookup"><span data-stu-id="2788b-123">Ratings – high to low</span></span>

- <span data-ttu-id="2788b-124">**Paginación** permite a los visitantes del sitio web pasar de una página de resultados de productos clasificados a otra página.</span><span class="sxs-lookup"><span data-stu-id="2788b-124">**Pagination** lets website visitors move from one page of categorized product results to another page.</span></span>
- <span data-ttu-id="2788b-125">**Recuento total** proporciona el número total de productos definidos en una categoría.</span><span class="sxs-lookup"><span data-stu-id="2788b-125">**Total count** provides the total number of products that are defined in a category.</span></span>

## <a name="enrich-a-category-landing-page"></a><span data-ttu-id="2788b-126">Enriquecer una página de aterrizaje de categoría</span><span class="sxs-lookup"><span data-stu-id="2788b-126">Enrich a category landing page</span></span>

<span data-ttu-id="2788b-127">Si desea que una página de aterrizaje de categoría tener una experiencia más adaptada para una categoría específica, puede “enriquecer” la página de aterrizaje de categoría para dicha categoría.</span><span class="sxs-lookup"><span data-stu-id="2788b-127">If you want a category landing page to have a more tailored experience for a specific category, you can "enrich" the category landing page for that category.</span></span> <span data-ttu-id="2788b-128">Por ejemplo, puede agregar un vídeo de marketing y alguna narración de la categoría para obtener la atención del comprador.</span><span class="sxs-lookup"><span data-stu-id="2788b-128">For example, you can add a marketing video and some category storytelling to get the shopper's attention.</span></span> <span data-ttu-id="2788b-129">Para obtener más información, consulte [Enriquecer una página de aterrizaje de categoría](enrich-category-page.md).</span><span class="sxs-lookup"><span data-stu-id="2788b-129">For more information, see [Enrich a category landing page](enrich-category-page.md).</span></span>

![Página de aterrizaje de categoría enriquecida](./media/CategoryLandingPages.png)

## <a name="auto-suggest-and-search-results-pages"></a><span data-ttu-id="2788b-131">Sugerencia automática y páginas de resultados de la búsqueda</span><span class="sxs-lookup"><span data-stu-id="2788b-131">Auto-suggest and search results pages</span></span>

<span data-ttu-id="2788b-132">Los usuarios del sitio web pueden explorar un sitio yendo a una categoría de la jerarquía de navegación o introduciendo un término de búsqueda en el campo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2788b-132">Website users can explore a site either by going to a category from the navigation hierarchy or by entering a search term in the search field.</span></span>

<span data-ttu-id="2788b-133">En cuanto los usuarios empiezan a escribir en el campo de búsqueda, experimentan la funcionalidad inmersiva de sugerencia automática que sugiere términos de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2788b-133">As soon as users start to type in the search field, they experience the immersive auto-suggest functionality that suggests search terms.</span></span>

<span data-ttu-id="2788b-134">A continuación se muestran algunos de los tipos de sugerencias que es posible que se muestren:</span><span class="sxs-lookup"><span data-stu-id="2788b-134">Here are some of the types of suggestions that might be shown:</span></span>

- <span data-ttu-id="2788b-135">**Palabras clave** se usan para buscar artículos en todos los productos surtidos al canal.</span><span class="sxs-lookup"><span data-stu-id="2788b-135">**Keywords** are used to find items across all products that are assorted to the channel.</span></span>
- <span data-ttu-id="2788b-136">**Productos** proporcionan vínculos directos a la página de detalles de productos.</span><span class="sxs-lookup"><span data-stu-id="2788b-136">**Products** provide direct links to the product details page.</span></span>
- <span data-ttu-id="2788b-137">**Sugerencias de búsqueda de categorías con ámbito** muestran diversas categorías y permiten a los usuarios la búsqueda de palabra clave en una categoría específica.</span><span class="sxs-lookup"><span data-stu-id="2788b-137">**Scoped category search suggestions** list various categories and let users search for the keyword in a specific category.</span></span>

![Sugerencia automática inmersiva](./media/ImmersiveAutoSuggestUX.png)

<span data-ttu-id="2788b-139">Cuando los usuarios seleccionan una de las sugerencias de búsqueda de categoría con ámbito o palabra clave, o cuando no hay sugerencias para el término de búsqueda que introducen, se redirigen a una página de resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2788b-139">When users select one of the keyword or scoped category search suggestions, or when there are no suggestions for the search term that they enter, they are redirected to a search results page.</span></span> <span data-ttu-id="2788b-140">A continuación, los usuarios pueden examinar, ordenar y limitar la lista de resultados de la búsqueda para encontrar el artículo deseado.</span><span class="sxs-lookup"><span data-stu-id="2788b-140">The users can then browse, sort, and refine the list of search results to find the desired item.</span></span>

![Aterrizaje de búsqueda](./media/SearchLanding.png)

<span data-ttu-id="2788b-142">Los siguientes componentes son esenciales para una página de resultados de la búsqueda:</span><span class="sxs-lookup"><span data-stu-id="2788b-142">The following components are essential for a search results page:</span></span>

- <span data-ttu-id="2788b-143">**Iconos de colocación de producto** muestran los productos para la búsqueda del usuario.</span><span class="sxs-lookup"><span data-stu-id="2788b-143">**Product placement tiles** show the products for the user's search.</span></span> <span data-ttu-id="2788b-144">De forma predeterminada, estos iconos se ordenan por la puntuación de relevancia de búsqueda con tecnología de nube para la búsqueda del usuario.</span><span class="sxs-lookup"><span data-stu-id="2788b-144">By default, these tiles are sorted by the cloud-powered search relevancy score for the user search.</span></span>
- <span data-ttu-id="2788b-145">**Refinadores y resumen de opciones** son filtros que proporcionan recuentos y que se pueden utilizar para limitar artículos.</span><span class="sxs-lookup"><span data-stu-id="2788b-145">**Refiners and choice summary** are filters that provide counts and that can be used to refine items.</span></span> <span data-ttu-id="2788b-146">El administrador de comercialización los configura como parte de la configuración de los metadatos de "categorías de canal y atributos de producto".</span><span class="sxs-lookup"><span data-stu-id="2788b-146">The merchandising manager configures them as part of the configuration of the "channel categories and product attributes" metadata.</span></span>
- <span data-ttu-id="2788b-147">**Opciones de ordenación** se usan por los visitantes del sitio web para ordenar los productos.</span><span class="sxs-lookup"><span data-stu-id="2788b-147">**Sorting options** are used by website visitors to sort the products.</span></span> <span data-ttu-id="2788b-148">De forma predeterminada, están disponibles las siguientes opciones de ordenación:</span><span class="sxs-lookup"><span data-stu-id="2788b-148">By default, the following sorting options are available:</span></span>

    - <span data-ttu-id="2788b-149">Precio: de menor a mayor</span><span class="sxs-lookup"><span data-stu-id="2788b-149">Price – low to high</span></span>
    - <span data-ttu-id="2788b-150">Precio: de mayor a menor</span><span class="sxs-lookup"><span data-stu-id="2788b-150">Price – high to low</span></span>
    - <span data-ttu-id="2788b-151">Nombre de producto: \[A-Z\]</span><span class="sxs-lookup"><span data-stu-id="2788b-151">Product name – \[A-Z\]</span></span>
    - <span data-ttu-id="2788b-152">Nombre de producto: \[Z-A\]</span><span class="sxs-lookup"><span data-stu-id="2788b-152">Product name – \[Z-A\]</span></span>
    - <span data-ttu-id="2788b-153">Clasificaciones: de menor a mayor</span><span class="sxs-lookup"><span data-stu-id="2788b-153">Ratings – low to high</span></span>
    - <span data-ttu-id="2788b-154">Clasificaciones: de mayor a menor</span><span class="sxs-lookup"><span data-stu-id="2788b-154">Ratings – high to low</span></span>
    - <span data-ttu-id="2788b-155">Predeterminada</span><span class="sxs-lookup"><span data-stu-id="2788b-155">Default</span></span>

- <span data-ttu-id="2788b-156">**Paginación** permite a los visitantes del sitio web pasar de una página de resultados de productos clasificados a otra página.</span><span class="sxs-lookup"><span data-stu-id="2788b-156">**Pagination** lets website visitors move from one page of categorized product results to another page.</span></span>
- <span data-ttu-id="2788b-157">**Recuento total** proporciona el número total de productos definidos en una categoría y que coinciden con los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2788b-157">**Total count** provides the total number of products that are defined in a category and that match the search criteria.</span></span>

>[!NOTE]
><span data-ttu-id="2788b-158">Estas capacidades de búsqueda basadas en la nube están disponibles a partir de la versión 10.0.8.</span><span class="sxs-lookup"><span data-stu-id="2788b-158">These cloud-powered search capabilities are available starting in version 10.0.8.</span></span> <span data-ttu-id="2788b-159">Asegúrese de que en **Parámetros de Commerce > Parámetros de configuración** hay una entrada para "ProductSearch.UseAzureSearch establecido en 'true'".</span><span class="sxs-lookup"><span data-stu-id="2788b-159">Ensure that under **Commerce Parameters > Configuration Parameters** there is an entry for "ProductSearch.UseAzureSearch set to 'true'".</span></span> 
<span data-ttu-id="2788b-160">![Parámetros de configuración para búsqueda en la nube](./media/CloudPoweredSearchConfigurationParameters.png)</span><span class="sxs-lookup"><span data-stu-id="2788b-160">![Configuration parameters for cloud-powered search](./media/CloudPoweredSearchConfigurationParameters.png)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2788b-161">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2788b-161">Additional resources</span></span>

[<span data-ttu-id="2788b-162">Visión general de la búsqueda con tecnología de nube</span><span class="sxs-lookup"><span data-stu-id="2788b-162">Cloud-powered search overview</span></span>](cloud-powered-search-overview.md)

[<span data-ttu-id="2788b-163">Visión general de la página principal</span><span class="sxs-lookup"><span data-stu-id="2788b-163">Home page overview</span></span>](quick-tour-home-page.md)

[<span data-ttu-id="2788b-164">Visión general de las páginas de detalles de producto</span><span class="sxs-lookup"><span data-stu-id="2788b-164">Product details pages overview</span></span>](quick-tour-pdp.md)

[<span data-ttu-id="2788b-165">Visión general de las páginas del carro y de la finalización de la compra</span><span class="sxs-lookup"><span data-stu-id="2788b-165">Cart and checkout pages overview</span></span>](quick-tour-cart-checkout.md)

[<span data-ttu-id="2788b-166">Visión general de las páginas de la gestión de cuentas</span><span class="sxs-lookup"><span data-stu-id="2788b-166">Account management pages overview</span></span>](quick-tour-account-management.md)

