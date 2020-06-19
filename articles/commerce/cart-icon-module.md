---
title: Módulo de icono de carro
description: En este tema se trata el modulo icono de carrito y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: 6771a84118504cd5c8e44302380eb970e4658902
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411098"
---
# <a name="cart-icon-module"></a><span data-ttu-id="464a8-103">Módulo de icono de carro</span><span class="sxs-lookup"><span data-stu-id="464a8-103">Cart icon module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="464a8-104">En este tema se trata el modulo icono de carrito y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="464a8-104">This topic covers the cart icon module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="464a8-105">Información general</span><span class="sxs-lookup"><span data-stu-id="464a8-105">Overview</span></span>

<span data-ttu-id="464a8-106">El módulo de icono de carrito representa el carrito en el módulo de encabezado de la página y muestra la cantidad de artículos en el carrito.</span><span class="sxs-lookup"><span data-stu-id="464a8-106">The cart icon module represents the cart in the header module of the page, and shows the number of items in the cart.</span></span> <span data-ttu-id="464a8-107">El módulo del ícono del carrito también muestra un resumen del carrito (también conocido como mini carrito) cuando el ícono del carrito está suspendido.</span><span class="sxs-lookup"><span data-stu-id="464a8-107">The cart icon module also displays a cart summary (also known as a mini cart) when the cart icon is hovered over.</span></span> <span data-ttu-id="464a8-108">El mini carrito proporciona al usuario un resumen de los artículos en el carrito sin tener que navegar a la página del carrito.</span><span class="sxs-lookup"><span data-stu-id="464a8-108">The mini cart provides the user with a summary of the items in the cart without having to navigate to the cart page.</span></span> <span data-ttu-id="464a8-109">Además, también permite al usuario ir directamente a la página de pago si está satisfecho con el resumen.</span><span class="sxs-lookup"><span data-stu-id="464a8-109">In addition, it also allows the user to directly go to checkout page if they are happy with the summary.</span></span> <span data-ttu-id="464a8-110">Esto reduce la cantidad de navegaciones de la página y agiliza el pago.</span><span class="sxs-lookup"><span data-stu-id="464a8-110">This reduces the number of page navigations and makes checkout faster.</span></span> 

<span data-ttu-id="464a8-111">La siguiente imagen muestra un ejemplo de un módulo de icono de carro que muestra un mini carro en el encabezado Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="464a8-111">The following image shows an example of a cart icon module that displays a mini cart in the Fabrikam header.</span></span>

![Ejemplo de un módulo de icono de carro](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a><span data-ttu-id="464a8-113">Propiedades del módulo</span><span class="sxs-lookup"><span data-stu-id="464a8-113">Module properties</span></span>

- <span data-ttu-id="464a8-114">**Mostrar mini carrito** - Cuando es verdadera, esta propiedad permite que se muestre un resumen del carrito (mini carrito) cuando se pasa el icono del carrito.</span><span class="sxs-lookup"><span data-stu-id="464a8-114">**Show mini cart** – When true, this property enables a cart summary (mini cart) to be displayed when the cart icon is hovered over.</span></span> <span data-ttu-id="464a8-115">Esta funcionalidad solo es compatible con los puertos de vista de escritorio.</span><span class="sxs-lookup"><span data-stu-id="464a8-115">This functionality is only supported for desktop view ports.</span></span>


## <a name="add-a-cart-icon-module-to-a-page"></a><span data-ttu-id="464a8-116">Agregar un módulo de icono de carrito a una página</span><span class="sxs-lookup"><span data-stu-id="464a8-116">Add a cart icon module to a page</span></span>

<span data-ttu-id="464a8-117">Para agregar un módulo de icono de carrito, consulte [Módulo de encabezado](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="464a8-117">To add a cart icon module, see [Header module](author-header-module.md).</span></span>


## <a name="additional-resources"></a><span data-ttu-id="464a8-118">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="464a8-118">Additional resources</span></span>

[<span data-ttu-id="464a8-119">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="464a8-119">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="464a8-120">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="464a8-120">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="464a8-121">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="464a8-121">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="464a8-122">Módulo de confirmación de pedido</span><span class="sxs-lookup"><span data-stu-id="464a8-122">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="464a8-123">Módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="464a8-123">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="464a8-124">Módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="464a8-124">Footer module</span></span>](author-footer-module.md)
