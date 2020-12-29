---
title: Módulo de icono de carro
description: En este tema se trata el modulo icono de carrito y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ebc5cfa490a4c8538fd081aced0844ed01d63a26
ms.sourcegitcommit: 12d271bb26c7490e7525d9b4bbf125cdc39fef43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2020
ms.locfileid: "4415694"
---
# <a name="cart-icon-module"></a><span data-ttu-id="c507a-103">Módulo de icono de carro</span><span class="sxs-lookup"><span data-stu-id="c507a-103">Cart icon module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c507a-104">En este tema se trata el modulo icono de carrito y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c507a-104">This topic covers the cart icon module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c507a-105">Información general</span><span class="sxs-lookup"><span data-stu-id="c507a-105">Overview</span></span>

<span data-ttu-id="c507a-106">El módulo de icono de carrito representa el carrito en el módulo de encabezado de la página y muestra la cantidad de artículos en el carrito.</span><span class="sxs-lookup"><span data-stu-id="c507a-106">The cart icon module represents the cart in the header module of the page, and shows the number of items in the cart.</span></span> <span data-ttu-id="c507a-107">El módulo del ícono del carrito también muestra un resumen del carrito (también conocido como mini carrito) cuando el ícono del carrito está suspendido.</span><span class="sxs-lookup"><span data-stu-id="c507a-107">The cart icon module also displays a cart summary (also known as a mini cart) when the cart icon is hovered over.</span></span> <span data-ttu-id="c507a-108">El mini carrito proporciona al usuario un resumen de los artículos en el carrito sin tener que navegar a la página del carrito.</span><span class="sxs-lookup"><span data-stu-id="c507a-108">The mini cart provides the user with a summary of the items in the cart without having to navigate to the cart page.</span></span> <span data-ttu-id="c507a-109">Además, también permite al usuario ir directamente a la página de pago si está satisfecho con el resumen.</span><span class="sxs-lookup"><span data-stu-id="c507a-109">In addition, it also allows the user to directly go to checkout page if they are happy with the summary.</span></span> <span data-ttu-id="c507a-110">Esto reduce la cantidad de navegaciones de la página y agiliza el pago.</span><span class="sxs-lookup"><span data-stu-id="c507a-110">This reduces the number of page navigations and makes checkout faster.</span></span> 

> [!NOTE]
> <span data-ttu-id="c507a-111">La compatibilidad con el módulo de icono de carro está disponible en Dynamics 365 Commerce 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="c507a-111">Support for the cart icon module is available in the Dynamics 365 Commerce 10.0.11 release.</span></span>

<span data-ttu-id="c507a-112">La siguiente imagen muestra un ejemplo de un módulo de icono de carro que muestra un mini carro en el encabezado Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="c507a-112">The following image shows an example of a cart icon module that displays a mini cart in the Fabrikam header.</span></span>

![Ejemplo de un módulo de icono de carro](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a><span data-ttu-id="c507a-114">Propiedades del módulo</span><span class="sxs-lookup"><span data-stu-id="c507a-114">Module properties</span></span>

- <span data-ttu-id="c507a-115">**Mostrar mini carrito** - Cuando es verdadera, esta propiedad permite que se muestre un resumen del carrito (mini carrito) cuando se pasa el icono del carrito.</span><span class="sxs-lookup"><span data-stu-id="c507a-115">**Show mini cart** – When true, this property enables a cart summary (mini cart) to be displayed when the cart icon is hovered over.</span></span> <span data-ttu-id="c507a-116">Esta funcionalidad solo es compatible con los puertos de vista de escritorio.</span><span class="sxs-lookup"><span data-stu-id="c507a-116">This functionality is only supported for desktop view ports.</span></span>

## <a name="add-a-cart-icon-module-to-a-page"></a><span data-ttu-id="c507a-117">Agregar un módulo de icono de carrito a una página</span><span class="sxs-lookup"><span data-stu-id="c507a-117">Add a cart icon module to a page</span></span>

<span data-ttu-id="c507a-118">Para agregar un módulo de icono de carrito, consulte [Módulo de encabezado](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="c507a-118">To add a cart icon module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c507a-119">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c507a-119">Additional resources</span></span>

[<span data-ttu-id="c507a-120">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="c507a-120">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="c507a-121">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="c507a-121">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="c507a-122">Módulo de pago</span><span class="sxs-lookup"><span data-stu-id="c507a-122">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="c507a-123">Módulo de dirección de envío</span><span class="sxs-lookup"><span data-stu-id="c507a-123">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="c507a-124">Módulo de opciones de entrega</span><span class="sxs-lookup"><span data-stu-id="c507a-124">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="c507a-125">Módulo de información de recogida</span><span class="sxs-lookup"><span data-stu-id="c507a-125">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="c507a-126">Módulo de detalles del pedido</span><span class="sxs-lookup"><span data-stu-id="c507a-126">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="c507a-127">Módulo de tarjeta de regalo</span><span class="sxs-lookup"><span data-stu-id="c507a-127">Gift card module</span></span>](add-giftcard.md)
