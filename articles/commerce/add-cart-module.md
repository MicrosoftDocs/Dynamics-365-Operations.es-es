---
title: Módulo de carro
description: En este tema se tratan los módulos de carro y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
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
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f6dd8fb56f7342eb9c877eda503a92f4a31e5863
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025445"
---
# <a name="cart-module"></a><span data-ttu-id="24c83-103">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="24c83-103">Cart module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="24c83-104">En este tema se tratan los módulos de carro y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="24c83-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="24c83-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="24c83-105">Overview</span></span>

<span data-ttu-id="24c83-106">Se utiliza un módulo de carro para mostrar los artículos que se han agregado al carro antes de que el cliente finalice la compra.</span><span class="sxs-lookup"><span data-stu-id="24c83-106">A cart module is used to show the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="24c83-107">Por ejemplo, incluye todos los artículos que se han agregado al carro y un resumen del pedido.</span><span class="sxs-lookup"><span data-stu-id="24c83-107">For example, it includes all the items that have been added to the cart and an order summary.</span></span> <span data-ttu-id="24c83-108">También permite al cliente aplicar o quitar códigos promocionales.</span><span class="sxs-lookup"><span data-stu-id="24c83-108">It also lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="24c83-109">El módulo de carro permite finalizar la compra como usuario que ha iniciado sesión o como usuario invitado.</span><span class="sxs-lookup"><span data-stu-id="24c83-109">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="24c83-110">También admite un vínculo **Volver a la compra**.</span><span class="sxs-lookup"><span data-stu-id="24c83-110">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="24c83-111">Puede configurar la ruta para este vínculo en **Valores de configuración de sitio \> Extensiones \> Rutas**.</span><span class="sxs-lookup"><span data-stu-id="24c83-111">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="24c83-112">El módulo del carro representa datos a partir del id. del carro.</span><span class="sxs-lookup"><span data-stu-id="24c83-112">The cart module renders data based on the cart ID.</span></span> <span data-ttu-id="24c83-113">El id, del carro es una cookie de explorador que está disponible a través del sitio.</span><span class="sxs-lookup"><span data-stu-id="24c83-113">The cart ID is a browser cookie that is available throughout the site.</span></span>

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="24c83-114">Franjas y propiedades del módulo del carro</span><span class="sxs-lookup"><span data-stu-id="24c83-114">Cart module properties and slots</span></span>

<span data-ttu-id="24c83-115">El módulo de carro tiene una propiedad **Encabezado** que se puede establecer en valores como **Cesta de la compra** y **Artículos del carro**.</span><span class="sxs-lookup"><span data-stu-id="24c83-115">The cart module has a **Heading** property that can be set to values such as **Shopping bag** and **Items in your cart**.</span></span> 

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="24c83-116">Módulos que se pueden usar en un módulo de carro</span><span class="sxs-lookup"><span data-stu-id="24c83-116">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="24c83-117">**Bloque de texto**: este módulo admite mensajería personalizada en el módulo de carro.</span><span class="sxs-lookup"><span data-stu-id="24c83-117">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="24c83-118">Los mensajes se controlan mediante el sistema de gestión de contenidos (CMS).</span><span class="sxs-lookup"><span data-stu-id="24c83-118">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="24c83-119">Se puede agregar cualquier mensaje, como “Si hubiera algún problema con el pedido, póngase en contacto con 1-800-Fabrikam”.</span><span class="sxs-lookup"><span data-stu-id="24c83-119">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="24c83-120">**Selector de tienda**: este módulo muestra una lista de las tiendas cercanas en las que un artículo está disponible para su recogida.</span><span class="sxs-lookup"><span data-stu-id="24c83-120">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="24c83-121">Permite a los usuarios especificar una ubicación para encontrar tiendas cercanas.</span><span class="sxs-lookup"><span data-stu-id="24c83-121">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="24c83-122">El módulo selector de tienda se integra con la interfaz de programación de aplicaciones (API) de geocodificación de Bing Maps para convertir la ubicación que el cliente ha introducido en una latitud y una longitud.</span><span class="sxs-lookup"><span data-stu-id="24c83-122">The store selector module is integrated with the Bing Maps Geocoding application programming interface (API) to convert the location to a latitude and longitude.</span></span> <span data-ttu-id="24c83-123">Se requiere una clave de la API de Bing Maps, y debe agregarse a la página de parámetros compartidos de Retail en Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="24c83-123">A Bing Maps API key is required and must be added to the Retail shared parameters page in Dynamics 365 Retail.</span></span> <span data-ttu-id="24c83-124">Este módulo admite dos propiedades, **Radio de búsqueda** y **Vínculo a los términos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="24c83-124">This module supports two properties, **Search radius** and **Terms of service link**.</span></span> <span data-ttu-id="24c83-125">La propiedad **Radio de búsqueda** define el radio de búsqueda de las tiendas, en millas.</span><span class="sxs-lookup"><span data-stu-id="24c83-125">The **Search radius** property defines the search radius for stores, in miles.</span></span> <span data-ttu-id="24c83-126">Si no se especifica ningún valor, se utiliza el radio de búsqueda predeterminado: 50 millas.</span><span class="sxs-lookup"><span data-stu-id="24c83-126">If no value is specified, the default search radius, 50 miles, is used.</span></span> <span data-ttu-id="24c83-127">Si se utiliza Bings Maps o cualquier servicio externo, se puede usar la propiedad **Vínculo a los términos de servicio** para proporcionar un enlace a los términos del servicio.</span><span class="sxs-lookup"><span data-stu-id="24c83-127">If Bings Maps or any external service is used, the **Terms of service link** property can be used to provide a link to the terms of service.</span></span> <span data-ttu-id="24c83-128">Se requiere un vínculo a los términos de servicio para el servicio Bing Maps.</span><span class="sxs-lookup"><span data-stu-id="24c83-128">A terms of service link is required for the Bing Maps service.</span></span> 

## <a name="cart-module-settings"></a><span data-ttu-id="24c83-129">Configuración de módulo de carro</span><span class="sxs-lookup"><span data-stu-id="24c83-129">Cart module settings</span></span>

<span data-ttu-id="24c83-130">Los módulos de carro tienen las siguientes opciones de configuración que se pueden establecer en **Valores de configuración de sitio \> Extensiones**:</span><span class="sxs-lookup"><span data-stu-id="24c83-130">Cart modules have the following settings that can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="24c83-131">**Cantidad máxima**: esta propiedad se usa para especificar el número máximo de cada artículo que se puede agregar al carro.</span><span class="sxs-lookup"><span data-stu-id="24c83-131">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="24c83-132">Por ejemplo, un minorista puede decidir si solo 10 de cada producto se pueden vender en una única transacción.</span><span class="sxs-lookup"><span data-stu-id="24c83-132">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="24c83-133">**Comprobación de inventario**: Cuando el valor se establece en **Verdadero**, se agrega un artículo al carro solo después de que el módulo del cuadro de compra se asegure de que está en existencias.</span><span class="sxs-lookup"><span data-stu-id="24c83-133">**Inventory check** – When the value is set to **True**, an item is added to the cart only after the buy box module makes sure that it's in stock.</span></span> <span data-ttu-id="24c83-134">Esta comprobación de inventario se realiza tanto para situaciones donde se enviará el artículo como para situaciones en la que se recogerá en la tienda.</span><span class="sxs-lookup"><span data-stu-id="24c83-134">This inventory check is done both for scenarios where the item will be shipped and for scenarios where it will be picked up in the store.</span></span> <span data-ttu-id="24c83-135">Si el valor se establece en **Falso**, no se realiza ninguna comprobación de inventario antes de agregar un artículo al carro y se realiza el pedido.</span><span class="sxs-lookup"><span data-stu-id="24c83-135">If the value is set to **False**, no inventory check is done before an item is added to the cart and the order is placed.</span></span>
- <span data-ttu-id="24c83-136">**Almacenaje de inventario**: esta propiedad se usa para especificar un número de almacenaje para el inventario.</span><span class="sxs-lookup"><span data-stu-id="24c83-136">**Inventory buffer** – This property is used to specify a buffer number for inventory.</span></span> <span data-ttu-id="24c83-137">El inventario se mantiene en tiempo real y, cuando muchos clientes realizan pedidos, puede ser difícil mantener un recuento de inventario preciso.</span><span class="sxs-lookup"><span data-stu-id="24c83-137">Inventory is maintained in real time, and when many customers place orders, it can be difficult to maintain an accurate inventory count.</span></span> <span data-ttu-id="24c83-138">Cuando se realiza una comprobación de inventario, si el inventario es inferior a la cantidad de almacenaje, el producto se tratará como sin existencias.</span><span class="sxs-lookup"><span data-stu-id="24c83-138">When an inventory check is done, if the inventory is less than the buffer amount, the product is treated as out of stock.</span></span> <span data-ttu-id="24c83-139">Por lo tanto, cuando las ventas se producen rápidamente entre varios canales, y el recuento de inventario no está completamente sincronizado, hay un riesgo menor de que se venda un artículo del que no hay existencias.</span><span class="sxs-lookup"><span data-stu-id="24c83-139">Therefore, when sales occur quickly through several channels, and the inventory count isn't fully synced, there is less risk that an item that is out of stock will be sold.</span></span>
- <span data-ttu-id="24c83-140">**Volver a la compra**: esta propiedad se utiliza para especificar la ruta para el vínculo **Volver a la compra**.</span><span class="sxs-lookup"><span data-stu-id="24c83-140">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="24c83-141">Esta ruta se puede configurar a nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="24c83-141">This route can be configured at the site level.</span></span> <span data-ttu-id="24c83-142">Esta configuración permite a los minoristas llevar al cliente a la página de inicio o a cualquier otra página del sitio.</span><span class="sxs-lookup"><span data-stu-id="24c83-142">This configuration lets retailers take the customer back to the home page or any other page on the site.</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="24c83-143">Interacción con Commerce Scale Unit</span><span class="sxs-lookup"><span data-stu-id="24c83-143">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="24c83-144">El módulo del carro recupera la información de producto mediante las API de Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="24c83-144">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="24c83-145">El id. del carro de la cookie del explorador se utiliza para recuperar toda la información de producto de Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="24c83-145">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="24c83-146">Agregar un módulo de carro a una página</span><span class="sxs-lookup"><span data-stu-id="24c83-146">Add a cart module to a page</span></span>

<span data-ttu-id="24c83-147">Para agregar un módulo de carro a una página nueva y establecer las propiedades necesarias, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="24c83-147">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="24c83-148">Cree un fragmento que se llame **Fragmento de carro** y agréguele un módulo de carro.</span><span class="sxs-lookup"><span data-stu-id="24c83-148">Create a fragment that is named **Cart fragment**, and add a cart module to it.</span></span>
1. <span data-ttu-id="24c83-149">Agregue un encabezado al módulo de carro.</span><span class="sxs-lookup"><span data-stu-id="24c83-149">Add a heading to the cart module.</span></span>
1. <span data-ttu-id="24c83-150">Agregue un módulo selector de tienda al módulo del carro.</span><span class="sxs-lookup"><span data-stu-id="24c83-150">Add a store selector module to the cart module.</span></span>
1. <span data-ttu-id="24c83-151">Guarde el fragmento, termine de editarlo y publíquelo.</span><span class="sxs-lookup"><span data-stu-id="24c83-151">Save the fragment, finish editing it, and publish it.</span></span>
1. <span data-ttu-id="24c83-152">Cree una plantilla con el nombre **Plantilla de carro** y agréguele el fragmento del carro que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="24c83-152">Create a template that is named **Cart template**, and add the cart fragment that you just created to it.</span></span>
1. <span data-ttu-id="24c83-153">Guarde la plantilla, termine de editarla y publíquela.</span><span class="sxs-lookup"><span data-stu-id="24c83-153">Save the template, finish editing it, and publish it.</span></span>
1. <span data-ttu-id="24c83-154">Cree una página que use la nueva plantilla.</span><span class="sxs-lookup"><span data-stu-id="24c83-154">Create a page that uses the new template.</span></span>
1. <span data-ttu-id="24c83-155">Guarde la página y obtenga una vista previa de ella.</span><span class="sxs-lookup"><span data-stu-id="24c83-155">Save and preview the page.</span></span>
1. <span data-ttu-id="24c83-156">Termine de editar la página y publíquela.</span><span class="sxs-lookup"><span data-stu-id="24c83-156">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="24c83-157">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="24c83-157">Additional resources</span></span>

[<span data-ttu-id="24c83-158">Visión general de kit de inicio</span><span class="sxs-lookup"><span data-stu-id="24c83-158">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="24c83-159">Módulo Contenedor</span><span class="sxs-lookup"><span data-stu-id="24c83-159">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="24c83-160">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="24c83-160">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="24c83-161">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="24c83-161">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="24c83-162">Módulo de confirmación de pedido</span><span class="sxs-lookup"><span data-stu-id="24c83-162">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="24c83-163">Módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="24c83-163">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="24c83-164">Módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="24c83-164">Footer module</span></span>](author-footer-module.md)
