---
title: Visión general de las páginas de detalles de producto
description: Este tema proporciona una visión general de las páginas de detalles de producto (PDP) en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 020c2a72515eb112adb33c6b58e3a5084339d040
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5243849"
---
# <a name="product-details-pages-overview"></a><span data-ttu-id="dbcf6-103">Visión general de las páginas de detalles de producto</span><span class="sxs-lookup"><span data-stu-id="dbcf6-103">Product details pages overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="dbcf6-104">Este tema proporciona una visión general de las páginas de detalles de producto (PDP) en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-104">This topic provides an overview of product details pages (PDPs) in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="dbcf6-105">Información general</span><span class="sxs-lookup"><span data-stu-id="dbcf6-105">Overview</span></span>

<span data-ttu-id="dbcf6-106">Una PDP proporciona información detallada sobre un producto y permite a los clientes seleccionar opciones de productos como un tamaño, un estilo y un color.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-106">A PDP provides detailed information about a product, and lets customers select product options such as a size, style, and color.</span></span> <span data-ttu-id="dbcf6-107">Una PDP debe mostrar toda la información de producto que un cliente necesita para tomar una decisión de compra.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-107">A PDP should showcase all the product information that a customer requires to make a purchase decision.</span></span>

<span data-ttu-id="dbcf6-108">En la ilustración siguiente se muestra un ejemplo de una PDP.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-108">The following illustration shows an example of a PDP.</span></span>

![Ejemplo de una página de detalles de productos](./media/pdp.PNG)

## <a name="header-and-footer-modules"></a><span data-ttu-id="dbcf6-110">Módulos de encabezado y pie de página</span><span class="sxs-lookup"><span data-stu-id="dbcf6-110">Header and footer modules</span></span>

<span data-ttu-id="dbcf6-111">La parte superior de una PDP tiene un encabezado que muestra todas las categorías de producto y otras páginas que el minorista desea que los clientes exploren.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-111">The top of a PDP has a header that shows all the product categories and other pages that the retailer wants customers to browse.</span></span> <span data-ttu-id="dbcf6-112">La parte inferior de la página tiene un pie de página que contiene vínculos rápidos a diversos temas que pueden interesar a clientes.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-112">The bottom of the page has a footer that contains quick links to various topics that might interest customers.</span></span>

## <a name="buy-box-module"></a><span data-ttu-id="dbcf6-113">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="dbcf6-113">Buy box module</span></span>

<span data-ttu-id="dbcf6-114">El módulo más importante en un PDP es el módulo de cuadro de compra, que aparece como el primer elemento en la sección principal de la página.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-114">The most important module on a PDP is the buy box module, which appears as the first item in the main section of the page.</span></span> <span data-ttu-id="dbcf6-115">Un módulo de cuadro de compra muestra información importante del producto, como el nombre del producto, la descripción del producto, el precio del producto, las imágenes del producto y las clasificaciones del producto.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-115">A buy box module shows important product information, such as the product name, the product description, the product price, product images, and product ratings.</span></span>

<span data-ttu-id="dbcf6-116">El módulo de cuadro de compra permite al cliente seleccionar opciones de productos (por ejemplo, un tamaño, un estilo y un color) y agregar el producto al carro.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-116">The buy box module lets the customer select product options (for example, a size, style, and color) and add the product to the cart.</span></span> <span data-ttu-id="dbcf6-117">También permite al cliente comprar el producto en línea y recogerlo en una tienda.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-117">It also lets the customer buy the product online and pick it up in a store.</span></span> <span data-ttu-id="dbcf6-118">El módulo de compra en línea y recogida en tienda usa la integración con las interfaces de programación de aplicaciones (API) de Bing Maps para encontrar tiendas cercanas o tiendas en otra ubicación que el cliente especifique.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-118">The buy online and pick up in store module uses integration with Bing Maps application programming interfaces (APIs) to find nearby stores or stores in another location that the customer specifies.</span></span>

<span data-ttu-id="dbcf6-119">Un módulo de cuadro de compra requiere un id. de producto.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-119">A buy box module requires a product ID.</span></span> <span data-ttu-id="dbcf6-120">Este id. se deriva del contexto de la página.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-120">This ID is derived from the page context.</span></span> <span data-ttu-id="dbcf6-121">Si se agrega un módulo de cuadro de compra a una página en la que el contexto de la página no incluye un id. de producto, no representará la información correctamente.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-121">If a buy box module is added to a page where the page context doesn't include a product ID, it won't render the information correctly.</span></span>

## <a name="product-specifications-module"></a><span data-ttu-id="dbcf6-122">Módulo de especificaciones del producto</span><span class="sxs-lookup"><span data-stu-id="dbcf6-122">Product specifications module</span></span>

<span data-ttu-id="dbcf6-123">El módulo de especificaciones del producto se puede utilizar para mostrar detalles adicionales sobre el producto.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-123">The product specifications module can be used to showcase additional details about the product.</span></span> <span data-ttu-id="dbcf6-124">Estos detalles se toman de atributos del producto en Commerce.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-124">These details are taken from product attributes in Commerce.</span></span> <span data-ttu-id="dbcf6-125">El módulo de especificaciones del producto muestra todos los atributos donde la propiedad **visible** se establece en **verdadero**.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-125">The product specifications module shows every attribute where the **visible** property is set to **true**.</span></span> <span data-ttu-id="dbcf6-126">Requiere un id. de producto para recuperar los atributos del producto.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-126">It requires a product ID to retrieve the product attributes.</span></span>

## <a name="recommendations-module"></a><span data-ttu-id="dbcf6-127">Módulo de recomendaciones</span><span class="sxs-lookup"><span data-stu-id="dbcf6-127">Recommendations module</span></span>

<span data-ttu-id="dbcf6-128">El módulo de recomendaciones es un módulo importante en una PDP.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-128">The recommendations module is an important module on a PDP.</span></span> <span data-ttu-id="dbcf6-129">Mientras los clientes exploran productos, se le deben presentar más opciones de productos, de manera que puedan encontrar el producto correcto y realizar una compra.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-129">While customers browse for products, more product options should be presented to them, so that they can find the correct product and make a purchase.</span></span> <span data-ttu-id="dbcf6-130">Las recomendaciones ayudan a los clientes a detectar con facilidad contenido relacionado y a continuar comprando.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-130">Recommendations help customers easily discover related content and continue to shop.</span></span>

<span data-ttu-id="dbcf6-131">Hay diferentes tipos de listas de recomendaciones disponibles:</span><span class="sxs-lookup"><span data-stu-id="dbcf6-131">Different types of recommendation lists are available:</span></span>

- <span data-ttu-id="dbcf6-132">El lista **A la gente también le gustó** se basa en el aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-132">The **People also like** list is based on machine learning.</span></span> <span data-ttu-id="dbcf6-133">Usa el historial de transacciones de otros clientes para proporcionar recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-133">It uses the transaction history of other customers to provide recommendations.</span></span> <span data-ttu-id="dbcf6-134">Esta lista se genera con el servicio de recomendaciones y se parece a las listas “Los clientes que compraron el producto, compraron…”.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-134">This list is generated by the recommendations service and resembles "Customers who bought this also bought..." lists.</span></span> <span data-ttu-id="dbcf6-135">Se requiere un id. de producto para generar esta lista.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-135">A product ID is required to generate this list.</span></span>
- <span data-ttu-id="dbcf6-136">Se puede generar una lista **Relacionado** para un producto en Commerce.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-136">A **Related** list can be configured for a product in Commerce.</span></span> <span data-ttu-id="dbcf6-137">Por ejemplo, para un bolso de viaje de cuero marrón, se pueden configurar para la lista relacionada más bolsos que sean de cuero o estén diseñados para viaje.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-137">For example, for a brown leather travel handbag, more handbags that are leather-based or designed for travel purposes can be configured for the related list.</span></span> <span data-ttu-id="dbcf6-138">En Commerce se pueden configurar otros tipos de listas relacionadas, como **Accesorios** y **Más como esto**.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-138">Other types of related lists, such as **Accessories** and **More like this**, can also be configured in Commerce.</span></span> <span data-ttu-id="dbcf6-139">Se requiere un id. de producto para generar esta lista.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-139">A product ID is required to generate this list.</span></span> <span data-ttu-id="dbcf6-140">Por lo tanto, si se ha agregado a una página principal, donde el contexto de la página no incluye un id. de producto, la lista estará vacía.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-140">Therefore, if it's added to a home page, where the page context doesn't include a product ID, the list will be empty.</span></span>
- <span data-ttu-id="dbcf6-141">En las PDF se pueden usar listas de recomendaciones generadas de manera algorítmica, como **Tendencias**, **Más vendidos** y **Nuevos**.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-141">Algorithmically generated recommendation lists, such as **Trending**, **Best Selling**, and **New**, can be used on PDPs.</span></span> <span data-ttu-id="dbcf6-142">Aunque es posible que estas listas no estén directamente relacionadas con el producto en la PDP, son otra manera de ayudar a los clientes a encontrar productos que puedan interesarles.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-142">Although these lists might not be directly related to the product on the PDP, they are another way to help customers find products that might interest them.</span></span> <span data-ttu-id="dbcf6-143">Estos tipos de listas no requieren un id. de producto.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-143">These types of lists don't require a product ID.</span></span> <span data-ttu-id="dbcf6-144">Son listas genéricas que se generan en función de patrones de compra en todo el sitio.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-144">They are generic lists that are generated based on shopping patterns across the site.</span></span>
- <span data-ttu-id="dbcf6-145">Las listas editoriales son listas mantenidas manualmente.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-145">Editorial lists are manually curated lists.</span></span> <span data-ttu-id="dbcf6-146">Por ejemplo, un minorista puede decidir mantener manualmente listas de productos que desea mostrar.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-146">For example, a retailer might decide to manually curate lists of products that it wants to showcase.</span></span>

## <a name="ratings-and-reviews-modules"></a><span data-ttu-id="dbcf6-147">Módulos de clasificaciones y opiniones</span><span class="sxs-lookup"><span data-stu-id="dbcf6-147">Ratings and reviews modules</span></span>

<span data-ttu-id="dbcf6-148">Se pueden usar tres módulos para mostrar y agregar opiniones:</span><span class="sxs-lookup"><span data-stu-id="dbcf6-148">Three modules can be used to show and add reviews:</span></span>

- <span data-ttu-id="dbcf6-149">**Revisiones**: este módulo muestra clasificaciones y revisiones que han proporcionado otros clientes.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-149">**Reviews** – This module lists ratings and reviews that have been provided by other customers.</span></span> <span data-ttu-id="dbcf6-150">Los clientes pueden ordenar y filtrar las reseñas.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-150">Customers can sort and filter the reviews.</span></span> <span data-ttu-id="dbcf6-151">Este módulo también permite que los clientes puedan indicar que les gusta o no las reseñas e informar de problemas.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-151">This module also lets customers like or dislike reviews, and report issues.</span></span>
- <span data-ttu-id="dbcf6-152">**Escribir opinión**: este módulo permite a los clientes escribir sus propias opiniones de un producto.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-152">**Write review** – This module lets customers write their own reviews of a product.</span></span>
- <span data-ttu-id="dbcf6-153">**Histograma de clasificaciones**: este módulo incluye un histograma que muestra la tendencia de las clasificaciones de un producto.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-153">**Ratings histogram** – This module includes a histogram that shows the ratings trend for a product.</span></span>

<span data-ttu-id="dbcf6-154">Para obtener más información, consulte [Visión general de clasificaciones y revisiones](ratings-reviews-overview.md).</span><span class="sxs-lookup"><span data-stu-id="dbcf6-154">For more details, see [Ratings and reviews overview](ratings-reviews-overview.md).</span></span>

## <a name="marketing-modules"></a><span data-ttu-id="dbcf6-155">Módulos de marketing</span><span class="sxs-lookup"><span data-stu-id="dbcf6-155">Marketing modules</span></span>

<span data-ttu-id="dbcf6-156">Si el contenido de marketing es exclusivo de un producto específico, cualquier módulo de marketing puede agregarse a la PDP.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-156">If marketing content is unique to a specific product, any marketing module can be added to the PDP.</span></span> <span data-ttu-id="dbcf6-157">Puede agregar módulos de marketing a una PDP “enriqueciendo” la página.</span><span class="sxs-lookup"><span data-stu-id="dbcf6-157">You can add marketing modules to a PDP by "enriching" the page.</span></span> <span data-ttu-id="dbcf6-158">Para más detalles, consulte [Enriquecer una página de producto](enrich-product-page.md).</span><span class="sxs-lookup"><span data-stu-id="dbcf6-158">For more details, see [Enrich a product page](enrich-product-page.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dbcf6-159">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="dbcf6-159">Additional resources</span></span>

[<span data-ttu-id="dbcf6-160">Visión general de la página principal</span><span class="sxs-lookup"><span data-stu-id="dbcf6-160">Home page overview</span></span>](quick-tour-home-page.md)

[<span data-ttu-id="dbcf6-161">Visión general de las páginas del carro y de la finalización de la compra</span><span class="sxs-lookup"><span data-stu-id="dbcf6-161">Cart and checkout pages overview</span></span>](quick-tour-cart-checkout.md)

[<span data-ttu-id="dbcf6-162">Visión general de las páginas de la gestión de cuentas</span><span class="sxs-lookup"><span data-stu-id="dbcf6-162">Account management pages overview</span></span>](quick-tour-account-management.md)

[<span data-ttu-id="dbcf6-163">Enriquecer una página de detalles de producto</span><span class="sxs-lookup"><span data-stu-id="dbcf6-163">Enrich a product details page</span></span>](enrich-product-page.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]