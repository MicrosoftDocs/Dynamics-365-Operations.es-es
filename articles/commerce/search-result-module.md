---
title: Módulo de resultados de búsqueda
description: En este tema se tratan los módulos de resultados de búsqueda y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 5d852fe1a81b1e42484bc49ae136ef8613a2d3a5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254778"
---
# <a name="search-results-module"></a><span data-ttu-id="11334-103">Módulo de resultados de búsqueda</span><span class="sxs-lookup"><span data-stu-id="11334-103">Search results module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="11334-104">En este tema se tratan los módulos de resultados de búsqueda y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="11334-104">This topic covers search results modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="11334-105">El módulo de resultados de búsqueda devuelve resultados de búsqueda de productos y una lista de refinadores aplicables a los productos.</span><span class="sxs-lookup"><span data-stu-id="11334-105">The search results module returns product search results and a list of applicable refiners for the products.</span></span> <span data-ttu-id="11334-106">Los módulos de resultados de búsqueda en Dynamics 365 Commerce se pueden utilizar para representar páginas en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="11334-106">Search results modules on Dynamics 365 Commerce sites can be used to render pages for the following scenarios:</span></span>

- <span data-ttu-id="11334-107">Resultados de búsqueda iniciados por la búsqueda de un usuario</span><span class="sxs-lookup"><span data-stu-id="11334-107">Search results that are initiated by a user search</span></span>
- <span data-ttu-id="11334-108">Resultados de búsqueda que muestran un conjunto específico de productos, como "Comprar looks similares"</span><span class="sxs-lookup"><span data-stu-id="11334-108">Search results that show a specific set of products, such as "Shop similar looks"</span></span>
- <span data-ttu-id="11334-109">Listas de productos que pertenecen a una categoría</span><span class="sxs-lookup"><span data-stu-id="11334-109">Lists of products that belong to a category</span></span>

<span data-ttu-id="11334-110">Para obtener más información sobre las páginas de resultados de búsqueda y categorías, consulte [Página de aterrizaje de categoría predeterminada y descripción general de la página de resultados de búsqueda](category-search-page-overview.md).</span><span class="sxs-lookup"><span data-stu-id="11334-110">For more information about category and search results pages, see [Default category landing page and search results page overview](category-search-page-overview.md).</span></span>

<span data-ttu-id="11334-111">La siguiente ilustración muestra un ejemplo de una página de resultados de búsqueda para una categoría del sitio de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="11334-111">The following illustration shows an example of a search results page for a category on the Fabrikam site.</span></span>

![Ejemplo de página de resultados de búsqueda en el sitio de Fabrikam](./media/SimpleCategoryLandingDressCategory.png)

## <a name="search-results-module-properties"></a><span data-ttu-id="11334-113">Propiedades del módulo de resultados de búsqueda</span><span class="sxs-lookup"><span data-stu-id="11334-113">Search results module properties</span></span>

<span data-ttu-id="11334-114">La tabla siguiente enumera las propiedades de los módulos de resultados de búsqueda, junto con sus valores y descripciones.</span><span class="sxs-lookup"><span data-stu-id="11334-114">The following table lists the properties of search result modules, together with their values and descriptions.</span></span>

| <span data-ttu-id="11334-115">Propiedad</span><span class="sxs-lookup"><span data-stu-id="11334-115">Property</span></span> | <span data-ttu-id="11334-116">Valores</span><span class="sxs-lookup"><span data-stu-id="11334-116">Values</span></span> | <span data-ttu-id="11334-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="11334-117">Description</span></span> |
|----------|--------|-------------|
| <span data-ttu-id="11334-118">Artículos por página</span><span class="sxs-lookup"><span data-stu-id="11334-118">Items per page</span></span> | <span data-ttu-id="11334-119">Entero</span><span class="sxs-lookup"><span data-stu-id="11334-119">Integer</span></span> | <span data-ttu-id="11334-120">Número de elementos que deben mostrarse en cada página.</span><span class="sxs-lookup"><span data-stu-id="11334-120">The number of items that should be shown on each page.</span></span> |
| <span data-ttu-id="11334-121">Volver a activar PDP</span><span class="sxs-lookup"><span data-stu-id="11334-121">Allow back on PDP</span></span> | <span data-ttu-id="11334-122">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="11334-122">**True** or **False**</span></span> | <span data-ttu-id="11334-123">Si esta propiedad se establece en **Verdadero**, cuando un usuario seleccione un producto en la página de resultados de búsqueda, la ruta de navegación de la página de detalles del producto (PDP) que se abre mostrará un vínculo "Volver a los resultados".</span><span class="sxs-lookup"><span data-stu-id="11334-123">If this property is set to **True**, when a user selects a product on the search results page, the breadcrumb navigation on the product details page (PDP) that is opened will show a "Back to results" link.</span></span> |
| <span data-ttu-id="11334-124">Expandir refinadores</span><span class="sxs-lookup"><span data-stu-id="11334-124">Expand Refiners</span></span> | <span data-ttu-id="11334-125">**Todos**, **1**, **2**, **3** o **4**</span><span class="sxs-lookup"><span data-stu-id="11334-125">**All**, **1**, **2**, **3**, or **4**</span></span> | <span data-ttu-id="11334-126">Número de refinadores principales que deben expandirse al cargar una página.</span><span class="sxs-lookup"><span data-stu-id="11334-126">The number of top refiners that should be expanded when a page is loaded.</span></span> <span data-ttu-id="11334-127">Por ejemplo, si esta propiedad se establece en **3**, se ampliarán los tres primeros refinadores de la página.</span><span class="sxs-lookup"><span data-stu-id="11334-127">For example, if this property is set to **3**, the first three refiners on the page will be expanded.</span></span> |
| <span data-ttu-id="11334-128">Ocultar visualización de jerarquía de categoría</span><span class="sxs-lookup"><span data-stu-id="11334-128">Hide category hierarchy display</span></span> | <span data-ttu-id="11334-129">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="11334-129">**True** or **False**</span></span> | <span data-ttu-id="11334-130">Si esta propiedad se establece en **Verdadero**, se ocultará la visualización de la jerarquía de categorías en la página.</span><span class="sxs-lookup"><span data-stu-id="11334-130">If this property is set to **True**, the category hierarchy display on the page will be hidden.</span></span> <span data-ttu-id="11334-131">Esta propiedad debe establecerse en **Verdadero** si se usa el [módulo de ruta de navegación](add-breadcrumb.md) para mostrar la jerarquía de categorías.</span><span class="sxs-lookup"><span data-stu-id="11334-131">This property should be set to **True** if you're using the [breadcrumb module](add-breadcrumb.md) to show the category hierarchy.</span></span>|
| <span data-ttu-id="11334-132">Incluir atributos del producto en los resultados de búsqueda</span><span class="sxs-lookup"><span data-stu-id="11334-132">Include product attributes in search results</span></span> | <span data-ttu-id="11334-133">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="11334-133">**True** or **False**</span></span> | <span data-ttu-id="11334-134">Si esta propiedad se establece en **Verdadero**, se devolverán atributos de los productos en los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="11334-134">If this property is set to **True**, attributes will be returned for the products in the search results.</span></span> <span data-ttu-id="11334-135">Aunque estos atributos se pueden mostrar en un sitio de Commerce, se requiere una extensión.</span><span class="sxs-lookup"><span data-stu-id="11334-135">Although these attributes can be shown on a Commerce site, an extension is required.</span></span>|
| <span data-ttu-id="11334-136">Mostrar precios de afiliación</span><span class="sxs-lookup"><span data-stu-id="11334-136">Show affiliation prices</span></span> | <span data-ttu-id="11334-137">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="11334-137">**True** or **False**</span></span> | <span data-ttu-id="11334-138">Si esta propiedad se establece en **Verdadero**, los precios de afiliación de los productos se mostrarán en los resultados de búsqueda cuando un usuario que haya iniciado sesión navegue por la página.</span><span class="sxs-lookup"><span data-stu-id="11334-138">If this property is set to **True**, affiliation prices for products will be shown in the search results when a signed-in user browses the page.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="11334-139">En Dynamics 365 Commerce versión 10.0.16 y posteriores, se puede usar la opción de configuración **Mostrar precios de afiliación** para mostrar los precios de afiliación en la página.</span><span class="sxs-lookup"><span data-stu-id="11334-139">In the Dynamics 365 Commerce 10.0.16 release and later, the **Show affiliation prices** configuration can be used to show affiliation prices on the page.</span></span>

## <a name="supported-modules"></a><span data-ttu-id="11334-140">Módulos admitidos</span><span class="sxs-lookup"><span data-stu-id="11334-140">Supported modules</span></span>

<span data-ttu-id="11334-141">El módulo de resultados de la búsqueda admite el [módulo de vista rápida](quick-view-module.md), que permite a los usuarios ver información de productos y agregar artículos al carro desde una página de resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="11334-141">The search results module supports the [quick view module](quick-view-module.md), which lets users view product information and add items to the cart from the search results page.</span></span>

## <a name="add-a-search-results-module-to-a-category-page"></a><span data-ttu-id="11334-142">Agregar un módulo de resultados de la búsqueda a una página de categoría</span><span class="sxs-lookup"><span data-stu-id="11334-142">Add a search results module to a category page</span></span>

<span data-ttu-id="11334-143">Para agregar un módulo de resultados de la búsqueda a una página de categoría, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="11334-143">To add a search results module to a category page, follow these steps.</span></span>

1. <span data-ttu-id="11334-144">Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.</span><span class="sxs-lookup"><span data-stu-id="11334-144">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="11334-145">En el cuadro de diálogo **Nueva plantilla**, escriba el nombre **Resultados de la búsqueda** y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="11334-145">In the **New template** dialog box, enter the name **Search results**, and then select **OK**.</span></span>
1. <span data-ttu-id="11334-146">En la entrada **Cuerpo**, seleccione los puntos suspensivos (...) y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="11334-146">In the **Body** slot, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="11334-147">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Página predeterminada** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="11334-147">In the **Add Module** dialog box, select the **Default Page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="11334-148">En la entrada **Principal** del módulo **Página predeterminada**, seleccione los puntos suspensivos (...) y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="11334-148">In the **Main** slot of the **Default Page** module, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="11334-149">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="11334-149">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="11334-150">En el espacio **Contenedor**, seleccione los puntos suspensivos (...) y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="11334-150">In the **Container** slot, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="11334-151">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Navegación** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="11334-151">In the **Add Module** dialog box, select the **Breadcrumb** module, and then select **OK**.</span></span>
1. <span data-ttu-id="11334-152">En el panel de propiedades **Ruta de navegación**, introduzca el valor **1** para **Ocurre lo mín.**.</span><span class="sxs-lookup"><span data-stu-id="11334-152">In the **Breadcrumb** properties pane, enter the value **1** for **Min Occurs**.</span></span>
1. <span data-ttu-id="11334-153">En el espacio **Contenedor**, seleccione los puntos suspensivos (...) y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="11334-153">In the **Container** slot, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="11334-154">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Resultados de la búsqueda** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="11334-154">In the **Add Module** dialog box, select the **Search results** module, and then select **OK**.</span></span>
1. <span data-ttu-id="11334-155">En el panel de propiedades **Resultados de la búsqueda**, introduzca el valor **1** para **Ocurre lo mín.** y establezca los valores de las demás propiedad necesarias para el módulo de resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="11334-155">In the **Search results** properties pane, enter the value **1** for **Min Occurs**, and then set any other required properties for the search results module.</span></span> <span data-ttu-id="11334-156">Al establecer estas propiedades en la plantilla, se asegura de que cualquier personalización de una página de categoría específica incluirá automáticamente esta configuración.</span><span class="sxs-lookup"><span data-stu-id="11334-156">By setting these properties in the template, you ensure that any customizations to a specific category page will automatically include these settings.</span></span>
1. <span data-ttu-id="11334-157">Seleccione **Finalizar edición** y luego seleccione **Publicar** para publicar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="11334-157">Select **Finish editing**, and then select **Publish** to publish the template.</span></span>
1. <span data-ttu-id="11334-158">Vaya a **Páginas** y seleccione **Nuevo** para crear una nueva página.</span><span class="sxs-lookup"><span data-stu-id="11334-158">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="11334-159">En el cuadro de diálogo **Elegir una plantilla**, seleccione la plantilla **Resultados de la búsqueda** creada anteriormente, escriba **Página de categoría** para **Nombre de página** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="11334-159">In the **Choose a template** dialog box, select the **Search results** template that you created, enter **Category page** for **Page name**, and then select **OK**.</span></span> <span data-ttu-id="11334-160">Puesto que todos los valores se establecen en la plantilla, la página está lista para publicarse.</span><span class="sxs-lookup"><span data-stu-id="11334-160">Because all the values are set in the template, the page is ready to be published.</span></span>
1. <span data-ttu-id="11334-161">Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="11334-161">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="11334-162">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="11334-162">Additional resources</span></span>

[<span data-ttu-id="11334-163">Visión general de la página de aterrizaje de la categoría predeterminada y la página de resultados de la búsqueda</span><span class="sxs-lookup"><span data-stu-id="11334-163">Default category landing page and search results page overview</span></span>](category-search-page-overview.md)

[<span data-ttu-id="11334-164">Descripción general de la biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="11334-164">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="11334-165">Módulo de vista rápida</span><span class="sxs-lookup"><span data-stu-id="11334-165">Quick view module</span></span>](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]