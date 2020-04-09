---
title: Módulo selector de tienda
description: En este tema se trata el modulo selector de tienda y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 03/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8efc2345ded52bfaee2d400815795906f326f4fd
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "3157349"
---
# <a name="store-selector-module"></a><span data-ttu-id="80100-103">Módulo selector de tienda</span><span class="sxs-lookup"><span data-stu-id="80100-103">Store selector module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="80100-104">En este tema se trata el modulo selector de tienda y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="80100-104">This topic covers the store selector module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="80100-105">Información general</span><span class="sxs-lookup"><span data-stu-id="80100-105">Overview</span></span>

<span data-ttu-id="80100-106">Se utiliza un módulo selector de tienda para el escenario de cliente "comprar en línea, recoger en la tienda" (BOPIS).</span><span class="sxs-lookup"><span data-stu-id="80100-106">A store selector module is used for the "buy online, pick up in store"" (BOPIS) customer scenario.</span></span> <span data-ttu-id="80100-107">Muestra una lista de tiendas donde un producto está disponible para recoger, así como el horario de la tienda y el inventario de productos para cada tienda.</span><span class="sxs-lookup"><span data-stu-id="80100-107">It displays a list of stores where a product is available for pickup, as well as store hours and product inventory for each store.</span></span>

<span data-ttu-id="80100-108">El módulo selector de tiendas requiere el contexto de un producto y una ubicación de búsqueda para encontrar tiendas.</span><span class="sxs-lookup"><span data-stu-id="80100-108">The store selector module requires the context of a product and a search location to find stores.</span></span> <span data-ttu-id="80100-109">En ausencia de una ubicación de búsqueda, el valor predeterminado es la ubicación del navegador del cliente, siempre que el cliente dé su consentimiento.</span><span class="sxs-lookup"><span data-stu-id="80100-109">In the absence of a search location, it defaults to the customer's browser location, provided that the customer gives consent.</span></span> <span data-ttu-id="80100-110">El módulo tiene un cuadro de entrada que permite al cliente ingresar una ubicación (código postal, o ciudad y estado) para encontrar tiendas cercanas.</span><span class="sxs-lookup"><span data-stu-id="80100-110">The module has an input box which allows the customer to enter a location (zipcode, or city and state) to find stores that are nearby.</span></span>

<span data-ttu-id="80100-111">El módulo selector de tienda se integra con la interfaz de programación de aplicaciones (API) de geocodificación de Bing Maps para convertir la ubicación que el cliente ha introducido en una latitud y una longitud.</span><span class="sxs-lookup"><span data-stu-id="80100-111">The store selector module is integrated with the Bing Maps Geocoding application programming interface (API) to convert the location to a latitude and longitude.</span></span> <span data-ttu-id="80100-112">Se requiere una clave de la API de Bing Maps, y debe agregarse a la página de parámetros compartidos de Commerce en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="80100-112">A Bing Maps API key is required and must be added to the Commerce shared parameters page in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="80100-113">El módulo selector de tiendas se puede agregar a un módulo de caja de compra en la página de detalles del producto (PDP) para mostrar las tiendas donde hay un producto disponible para su recogida.</span><span class="sxs-lookup"><span data-stu-id="80100-113">The store selector module can be added to a buy box module on the product details page (PDP) to display stores where a product is available for pickup.</span></span> <span data-ttu-id="80100-114">También se puede agregar a un módulo de carrito.</span><span class="sxs-lookup"><span data-stu-id="80100-114">It can also be added to a cart module.</span></span> <span data-ttu-id="80100-115">Cuando se agrega a un módulo de carrito, el módulo selector de tienda muestra opciones de recolección para cada artículo de línea de carrito.</span><span class="sxs-lookup"><span data-stu-id="80100-115">When added to a cart module, the store selector module displays pickup options for each cart line item.</span></span> <span data-ttu-id="80100-116">Además, con la codificación personalizada, este módulo se puede agregar a otras páginas o módulos a través de extensiones y personalizaciones.</span><span class="sxs-lookup"><span data-stu-id="80100-116">In addition, with custom coding this module can be added to other pages or modules via extensions and customizations.</span></span>

<span data-ttu-id="80100-117">Para que funcione el escenario BOPIS, los productos deben configurarse con el modo de entrega "recogida del cliente".</span><span class="sxs-lookup"><span data-stu-id="80100-117">For the BOPIS scenario to work, products should be configured with the "customer pickup" delivery mode.</span></span> <span data-ttu-id="80100-118">De lo contrario, el módulo no se mostrará en las páginas respectivas.</span><span class="sxs-lookup"><span data-stu-id="80100-118">Otherwise, the module will not be shown on the respective pages.</span></span> <span data-ttu-id="80100-119">Para obtener detalles sobre cómo configurar el modo de entrega, consulte [Configurar modos de entrega](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span><span class="sxs-lookup"><span data-stu-id="80100-119">For details on how to configure the delivery mode, see [Set up modes of delivery](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span></span>

<span data-ttu-id="80100-120">La siguiente imagen muestra un ejemplo de un módulo selector de tienda utilizado en un PDP.</span><span class="sxs-lookup"><span data-stu-id="80100-120">The following image shows an example of a store selector module used on a PDP.</span></span>

![Ejemplo de un módulo selector de tienda](./media/BOPIS.PNG)

## <a name="store-selector-module-usage-in-e-commerce"></a><span data-ttu-id="80100-122">Uso del módulo selector de tienda en comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="80100-122">Store selector module usage in e-Commerce</span></span>

- <span data-ttu-id="80100-123">Un módulo selector de tiendas se puede usar en la página de detalles del producto (PDP) para mostrar las tiendas cercanas donde hay un producto disponible para su recogida.</span><span class="sxs-lookup"><span data-stu-id="80100-123">A store selector module can be used on a product details page (PDP) to find nearby stores where a product is available for pickup.</span></span>
- <span data-ttu-id="80100-124">Un módulo selector de tiendas se puede usar en la página de carrito para mostrar las tiendas cercanas donde hay un producto en el carrito disponible para su recogida.</span><span class="sxs-lookup"><span data-stu-id="80100-124">A store selector module can be used on a cart page to find nearby stores where a product in the cart is available for pickup.</span></span>

## <a name="store-selector-module-properties"></a><span data-ttu-id="80100-125">Propiedades del módulo selector de tienda</span><span class="sxs-lookup"><span data-stu-id="80100-125">Store selector module properties</span></span>

| <span data-ttu-id="80100-126">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="80100-126">Property name</span></span>             | <span data-ttu-id="80100-127">Valor</span><span class="sxs-lookup"><span data-stu-id="80100-127">Value</span></span>                 | <span data-ttu-id="80100-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="80100-128">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="80100-129">Radio de búsqueda</span><span class="sxs-lookup"><span data-stu-id="80100-129">Search radius</span></span> | <span data-ttu-id="80100-130">Número</span><span class="sxs-lookup"><span data-stu-id="80100-130">Number</span></span> | <span data-ttu-id="80100-131">Define el radio de búsqueda de tiendas, en millas.</span><span class="sxs-lookup"><span data-stu-id="80100-131">Defines the search radius for stores, in miles.</span></span> <span data-ttu-id="80100-132">Si no se especifica ningún valor, se utiliza el radio de búsqueda predeterminado: 50 millas.</span><span class="sxs-lookup"><span data-stu-id="80100-132">If no value is specified, the default search radius of 50 miles is used.</span></span>|
|<span data-ttu-id="80100-133">Términos de servicio</span><span class="sxs-lookup"><span data-stu-id="80100-133">Terms of Service</span></span> | <span data-ttu-id="80100-134">Dirección URL</span><span class="sxs-lookup"><span data-stu-id="80100-134">URL</span></span>    |  <span data-ttu-id="80100-135">La URL de los términos de servicio que se requiere para el servicio Bing Maps.</span><span class="sxs-lookup"><span data-stu-id="80100-135">The terms of service URL that is required for the Bing Maps service.</span></span> |

## <a name="add-a-store-selector-module-to-a-page"></a><span data-ttu-id="80100-136">Agregar un módulo de selector de tienda a una página</span><span class="sxs-lookup"><span data-stu-id="80100-136">Add a store selector module to a page</span></span>

<span data-ttu-id="80100-137">Un módulo selector de tienda necesita el contexto de un producto, por lo que solo se puede usar dentro de los módulos de compra y carrito.</span><span class="sxs-lookup"><span data-stu-id="80100-137">A store selector module needs the context of a product, so it can only be used within buy box and cart modules.</span></span> <span data-ttu-id="80100-138">Los módulos de selector de tienda no funcionan fuera de estos módulos.</span><span class="sxs-lookup"><span data-stu-id="80100-138">Store selector modules do not function outside these modules.</span></span>

- <span data-ttu-id="80100-139">Para obtener información sobre cómo agregar un módulo selector de tienda a un módulo de caja de compra, vea [Módulo de caja de compra](add-buy-box.md).</span><span class="sxs-lookup"><span data-stu-id="80100-139">For information on how to add a store selector module to a buy box module, see [Buy box module](add-buy-box.md).</span></span> 
- <span data-ttu-id="80100-140">Para obtener información sobre cómo agregar un módulo selector de tienda a un módulo de carrito, vea [Módulo de carrito](add-cart-module.md)</span><span class="sxs-lookup"><span data-stu-id="80100-140">For information on how to add a store selector module to a cart module, see [Cart module](add-cart-module.md)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="80100-141">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="80100-141">Additional resources</span></span>

[<span data-ttu-id="80100-142">Visión general de kit de inicio</span><span class="sxs-lookup"><span data-stu-id="80100-142">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="80100-143">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="80100-143">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="80100-144">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="80100-144">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="80100-145">Visita rápida de PDP</span><span class="sxs-lookup"><span data-stu-id="80100-145">Quick tour of PDP</span></span>](quick-tour-pdp.md)

[<span data-ttu-id="80100-146">Paseo rápido por el carro y la finalización de la compra</span><span class="sxs-lookup"><span data-stu-id="80100-146">Quick tour of Cart and checkout</span></span>](quick-tour-cart-checkout.md)

[<span data-ttu-id="80100-147">Configurar modos de entrega</span><span class="sxs-lookup"><span data-stu-id="80100-147">Set up modes of delivery</span></span>](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)
