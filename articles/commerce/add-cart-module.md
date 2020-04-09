---
title: Módulo de carro
description: En este tema se tratan los módulos de carro y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 03/19/2020
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
ms.openlocfilehash: 598b35b1bd365e761d8d4c5ef214935e60b971f4
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154026"
---
# <a name="cart-module"></a><span data-ttu-id="ddd4d-103">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="ddd4d-103">Cart module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ddd4d-104">En este tema se tratan los módulos de carro y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ddd4d-105">Información general</span><span class="sxs-lookup"><span data-stu-id="ddd4d-105">Overview</span></span>

<span data-ttu-id="ddd4d-106">Un módulo de carro muestra los artículos que se han agregado al carro antes de que el cliente finalice la compra.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-106">A cart module shows the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="ddd4d-107">El módulo también muestra un resumen del pedido y permite al cliente aplicar o quitar códigos promocionales.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-107">The module also shows an order summary and lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="ddd4d-108">El módulo de carro permite finalizar la compra como usuario que ha iniciado sesión o como usuario invitado.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-108">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="ddd4d-109">También admite un vínculo **Volver a la compra**.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-109">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="ddd4d-110">Puede configurar la ruta para este vínculo en **Valores de configuración de sitio \> Extensiones \> Rutas**.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-110">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="ddd4d-111">El módulo de carrito procesa los datos en función de la ID del carrito, que es una cookie del navegador disponible en todo el sitio.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-111">The cart module renders data based on the cart ID, which is a browser cookie available throughout the site.</span></span>

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="ddd4d-112">Franjas y propiedades del módulo del carro</span><span class="sxs-lookup"><span data-stu-id="ddd4d-112">Cart module properties and slots</span></span>

<span data-ttu-id="ddd4d-113">El módulo de carro tiene una propiedad **Encabezado** que se puede establecer en valores como **Cesta de la compra** y **Artículos del carro**.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-113">The cart module has a **Heading** property that can be set to values such as **Shopping bag** and **Items in your cart**.</span></span> 

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="ddd4d-114">Módulos que se pueden usar en un módulo de carro</span><span class="sxs-lookup"><span data-stu-id="ddd4d-114">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="ddd4d-115">**Bloque de texto**: este módulo admite mensajería personalizada en el módulo de carro.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-115">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="ddd4d-116">Los mensajes se controlan mediante el sistema de gestión de contenidos (CMS).</span><span class="sxs-lookup"><span data-stu-id="ddd4d-116">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="ddd4d-117">Se puede agregar cualquier mensaje, como “Si hubiera algún problema con el pedido, póngase en contacto con 1-800-Fabrikam”.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-117">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="ddd4d-118">**Selector de tienda**: este módulo muestra una lista de las tiendas cercanas en las que un artículo está disponible para su recogida.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-118">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="ddd4d-119">Permite a los usuarios especificar una ubicación para encontrar tiendas cercanas.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-119">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="ddd4d-120">Para obtener más información sobre este módulo, vea [Módulo selector de tienda](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="ddd4d-120">For more information on this module, see [Store Selector module](store-selector.md).</span></span>

## <a name="cart-module-settings"></a><span data-ttu-id="ddd4d-121">Configuración de módulo de carro</span><span class="sxs-lookup"><span data-stu-id="ddd4d-121">Cart module settings</span></span>

<span data-ttu-id="ddd4d-122">Los módulos de carro tienen las siguientes opciones de configuración que se pueden establecer en **Valores de configuración de sitio \> Extensiones**:</span><span class="sxs-lookup"><span data-stu-id="ddd4d-122">Cart modules have the following settings that can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="ddd4d-123">**Cantidad máxima**: esta propiedad se usa para especificar el número máximo de cada artículo que se puede agregar al carro.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-123">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="ddd4d-124">Por ejemplo, un minorista puede decidir si solo 10 de cada producto se pueden vender en una única transacción.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-124">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="ddd4d-125">**Comprobación de inventario**: Cuando el valor se establece en **Verdadero**, se agrega un artículo al carro solo después de que el módulo del cuadro de compra se asegure de que está en existencias.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-125">**Inventory check** – When the value is set to **True**, an item is added to the cart only after the buy box module makes sure that it's in stock.</span></span> <span data-ttu-id="ddd4d-126">Esta comprobación de inventario se realiza para situaciones donde se enviará el artículo y para situaciones en la que se recogerá en la tienda.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-126">This inventory check is done for scenarios where the item will be shipped and for scenarios where it will be picked up in the store.</span></span> <span data-ttu-id="ddd4d-127">Si el valor se establece en **Falso**, no se realiza ninguna comprobación de inventario antes de agregar un artículo al carro y se realiza el pedido.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-127">If the value is set to **False**, no inventory check is done before an item is added to the cart and the order is placed.</span></span>
- <span data-ttu-id="ddd4d-128">**Almacenaje de inventario**: esta propiedad se usa para especificar un número de almacenaje para el inventario.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-128">**Inventory buffer** – This property is used to specify a buffer number for inventory.</span></span> <span data-ttu-id="ddd4d-129">El inventario se mantiene en tiempo real y, cuando muchos clientes realizan pedidos, puede ser difícil mantener un recuento de inventario preciso.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-129">Inventory is maintained in real time, and when many customers place orders, it can be difficult to maintain an accurate inventory count.</span></span> <span data-ttu-id="ddd4d-130">Cuando se realiza una comprobación de inventario, si el inventario es inferior a la cantidad de almacenaje, el producto se tratará como sin existencias.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-130">When an inventory check is done, if the inventory is less than the buffer amount, the product is treated as out of stock.</span></span> <span data-ttu-id="ddd4d-131">Por lo tanto, cuando las ventas se producen rápidamente entre varios canales, y el recuento de inventario no está completamente sincronizado, hay un riesgo menor de que se venda un artículo del que no hay existencias.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-131">Therefore, when sales occur quickly through several channels, and the inventory count isn't fully synced, there is less risk that an item that is out of stock will be sold.</span></span>
- <span data-ttu-id="ddd4d-132">**Volver a la compra**: esta propiedad se utiliza para especificar la ruta para el vínculo **Volver a la compra**.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-132">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="ddd4d-133">La ruta se puede configurar a nivel de sitio, lo que permite a los minoristas llevar al cliente de vuelta a la página de inicio o cualquier otra página del sitio.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-133">The route can be configured at the site level, allowing retailers to take the customer back to the home page or any other page on the site.</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="ddd4d-134">Interacción con Commerce Scale Unit</span><span class="sxs-lookup"><span data-stu-id="ddd4d-134">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="ddd4d-135">El módulo del carro recupera la información de producto mediante las API de Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-135">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="ddd4d-136">El id. del carro de la cookie del explorador se utiliza para recuperar toda la información de producto de Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-136">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="ddd4d-137">Agregar un módulo de carro a una página</span><span class="sxs-lookup"><span data-stu-id="ddd4d-137">Add a cart module to a page</span></span>

<span data-ttu-id="ddd4d-138">Para agregar un módulo de carro a una página nueva y establecer las propiedades necesarias, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-138">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="ddd4d-139">Cree un fragmento que se llame **Fragmento de carro** y agregue un módulo de carro al nuevo fragmento.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-139">Create a fragment named **Cart fragment**, and add a cart module to the new fragment.</span></span>
1. <span data-ttu-id="ddd4d-140">Agregue un encabezado al módulo de carro.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-140">Add a heading to the cart module.</span></span>
1. <span data-ttu-id="ddd4d-141">Agregue un módulo selector de tienda al módulo del carro.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-141">Add a store selector module to the cart module.</span></span>
1. <span data-ttu-id="ddd4d-142">Guarde el fragmento, termine de editarlo y después publique el fragmento.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-142">Save the fragment, finish editing, and then publish the fragment.</span></span>
1. <span data-ttu-id="ddd4d-143">Cree una plantilla con el nombre **Plantilla de carro** y agréguele el fragmento del carro que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-143">Create a template named **Cart template**, and add the cart fragment that you just created.</span></span>
1. <span data-ttu-id="ddd4d-144">Guarde la plantilla, termine de editarlo y después publique la plantilla.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-144">Save the template, finish editing, and then publish the template.</span></span>
1. <span data-ttu-id="ddd4d-145">Cree una página que use la nueva plantilla.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-145">Create a page that uses the new template.</span></span>
1. <span data-ttu-id="ddd4d-146">Guarde la página y obtenga una vista previa de ella.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-146">Save and preview the page.</span></span>
1. <span data-ttu-id="ddd4d-147">Termine de editar la página y publíquela.</span><span class="sxs-lookup"><span data-stu-id="ddd4d-147">Finish editing the page, and then publish the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ddd4d-148">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ddd4d-148">Additional resources</span></span>

[<span data-ttu-id="ddd4d-149">Visión general de kit de inicio</span><span class="sxs-lookup"><span data-stu-id="ddd4d-149">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="ddd4d-150">Módulo Contenedor</span><span class="sxs-lookup"><span data-stu-id="ddd4d-150">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="ddd4d-151">Módulo de selector de tienda</span><span class="sxs-lookup"><span data-stu-id="ddd4d-151">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="ddd4d-152">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="ddd4d-152">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="ddd4d-153">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="ddd4d-153">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="ddd4d-154">Módulo de confirmación de pedido</span><span class="sxs-lookup"><span data-stu-id="ddd4d-154">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="ddd4d-155">Módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="ddd4d-155">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="ddd4d-156">Módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="ddd4d-156">Footer module</span></span>](author-footer-module.md)
