---
title: Visión general de la biblioteca de módulos
description: Este tema presenta una visión general de la biblioteca de módulos de Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4b3440c046ff055c8afa012c80c56aba741fef27
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985570"
---
# <a name="module-library-overview"></a><span data-ttu-id="f2099-103">Visión general de la biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="f2099-103">Module library overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f2099-104">Este tema presenta una visión general de la biblioteca de módulos de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f2099-104">This topic presents an overview of the Microsoft Dynamics 365 Commerce module library.</span></span>

## <a name="overview"></a><span data-ttu-id="f2099-105">Información general</span><span class="sxs-lookup"><span data-stu-id="f2099-105">Overview</span></span>

<span data-ttu-id="f2099-106">La biblioteca de módulos de Dynamics 365 Commerce es una colección de módulos que se pueden usar para crear un sitio web de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="f2099-106">The Dynamics 365 Commerce module library is a collection of modules that can be used to build an e-Commerce website.</span></span> <span data-ttu-id="f2099-107">Los módulos tienen tanto aspectos de la interfaz de usuario (IU) como aspectos de comportamiento funcional.</span><span class="sxs-lookup"><span data-stu-id="f2099-107">Modules have both user interface (UI) aspects and functional behavior aspects.</span></span>

<span data-ttu-id="f2099-108">Se pueden aplicar temas a los módulos de la biblioteca de módulos para cambiar su aspecto.</span><span class="sxs-lookup"><span data-stu-id="f2099-108">Themes can be applied to the modules in the module library to change their look and feel.</span></span> <span data-ttu-id="f2099-109">Los temas usan hojas de estilo CSS (CSS).</span><span class="sxs-lookup"><span data-stu-id="f2099-109">The themes use Cascading Style Sheets (CSS).</span></span> <span data-ttu-id="f2099-110">Se proporciona un tema para un sitio de comercio electrónico ficticio con el nombre “Fabrikam” como parte de la biblioteca de módulos y se puede utilizar como referencia.</span><span class="sxs-lookup"><span data-stu-id="f2099-110">A theme for a fictitious e-Commerce site that is named "Fabrikam" is provided as part of the module library and can be used as a reference.</span></span>

## <a name="module-library-modules"></a><span data-ttu-id="f2099-111">Módulos de la biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="f2099-111">Module library modules</span></span>

<span data-ttu-id="f2099-112">En la biblioteca de módulos se proporcionan los siguientes tipos de módulos:</span><span class="sxs-lookup"><span data-stu-id="f2099-112">The following types of modules are provided in the module library:</span></span>

- <span data-ttu-id="f2099-113">**Módulo de contenedor**: un módulo de contenedor es un módulo sencillo que actúa como host para otros módulos.</span><span class="sxs-lookup"><span data-stu-id="f2099-113">**Container module** – A container module is a simple module that acts as a host for other modules.</span></span> <span data-ttu-id="f2099-114">Controla el diseño de los módulos que se encuentran dentro.</span><span class="sxs-lookup"><span data-stu-id="f2099-114">It controls the layout of the modules that are inside it.</span></span>
- <span data-ttu-id="f2099-115">**Módulos de marketing**: los módulos de marketing incluyen módulos de carrusel, bloque de contenido, bloque de texto y reproductor de vídeo.</span><span class="sxs-lookup"><span data-stu-id="f2099-115">**Marketing modules** – Marketing modules include content block, text block, video player, and carousel modules.</span></span> <span data-ttu-id="f2099-116">Todos estos módulos se pueden usar para mostrar el contenido.</span><span class="sxs-lookup"><span data-stu-id="f2099-116">All these modules can be used to showcase content.</span></span> <span data-ttu-id="f2099-117">Se pueden colocar en cualquier página y se controlan por datos desde el sistema de gestión de contenidos (CMS).</span><span class="sxs-lookup"><span data-stu-id="f2099-117">They can be put on any page and are driven by data from the content management system (CMS).</span></span>
- <span data-ttu-id="f2099-118">**Módulos de encabezado y pie de página**: los módulos de encabezado y pie de página aparecen en el encabezado y el pie de página de todas las páginas del sitio.</span><span class="sxs-lookup"><span data-stu-id="f2099-118">**Header and footer modules** – Header and footer modules appear in the header and footer of all site pages.</span></span> <span data-ttu-id="f2099-119">Esos módulos se pueden configurar según sea necesario a través de las propiedades.</span><span class="sxs-lookup"><span data-stu-id="f2099-119">These modules can be configured as required through properties.</span></span>
- <span data-ttu-id="f2099-120">**Módulos de búsqueda**: los productos se pueden descubrir mediante el módulo de búsqueda en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="f2099-120">**Search modules** – Products can be discovered by using the search module in the header.</span></span> <span data-ttu-id="f2099-121">Los resultados de la búsqueda aparecen en la página de resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f2099-121">Search results appear on the search results page.</span></span> <span data-ttu-id="f2099-122">Los productos también se pueden descubrir en las páginas de categoría, que son páginas dedicadas para cada categoría que se admite en la jerarquía de navegación de canal.</span><span class="sxs-lookup"><span data-stu-id="f2099-122">Products can also be discovered on category pages, which are dedicated pages for each category that is supported in the channel navigation hierarchy.</span></span> <span data-ttu-id="f2099-123">Además, los módulos de refinador se pueden usar para filtrar aún más los resultados en los resultados de la búsqueda y páginas de categoría.</span><span class="sxs-lookup"><span data-stu-id="f2099-123">In addition, refiner modules can be used to further filter results on search results and category pages.</span></span>
- <span data-ttu-id="f2099-124">**Módulos de página de detalles de productos**: las páginas de detalles de producto utilizan varios módulos para mostrar la información del producto.</span><span class="sxs-lookup"><span data-stu-id="f2099-124">**Product details page modules** – Product details pages use several modules to show product information.</span></span> <span data-ttu-id="f2099-125">El módulo del cuadro de compra permite a los clientes ver productos y agregarlos al carro.</span><span class="sxs-lookup"><span data-stu-id="f2099-125">The buy box module lets customers view products and add them to the cart.</span></span> <span data-ttu-id="f2099-126">Otros módulos, como el módulo de especificaciones técnicas, muestran los detalles de productos.</span><span class="sxs-lookup"><span data-stu-id="f2099-126">Other modules, such as the tech specs module, show the product details.</span></span> <span data-ttu-id="f2099-127">El módulo de clasificaciones y revisiones se puede usar para ver y proporcionar revisiones.</span><span class="sxs-lookup"><span data-stu-id="f2099-127">The ratings and reviews module can used to view and provide reviews.</span></span>
- <span data-ttu-id="f2099-128">**Módulo de comprar en línea y recoger en una tienda**: el módulo de comprar en línea y recoger en una tienda se integra con Bing Maps.</span><span class="sxs-lookup"><span data-stu-id="f2099-128">**Buy online pick up in store module** – The buy online pick up in store module is integrated with Bing Maps.</span></span> <span data-ttu-id="f2099-129">Se puede utilizar para encontrar tiendas cercanas donde los clientes pueden recoger productos que han comprado.</span><span class="sxs-lookup"><span data-stu-id="f2099-129">It can be used to find nearby stores where customers can pick up products that they have purchased.</span></span>
- <span data-ttu-id="f2099-130">**Módulos de compra**: los módulos de compra incluyen el módulo de carro, que se puede usar para agregar artículos al carro.</span><span class="sxs-lookup"><span data-stu-id="f2099-130">**Purchase modules** – Purchase modules include the cart module, which can be used to add items to the cart.</span></span> <span data-ttu-id="f2099-131">El módulo de finalización de la compra captura la dirección de envío, las opciones de entrega, la tarjeta regalo, el programa de fidelización y la información de la tarjeta de crédito, para poder procesar un pedido.</span><span class="sxs-lookup"><span data-stu-id="f2099-131">The checkout module captures the shipping address, delivery options, and gift card, loyalty program, and credit card information, so that an order can be processed.</span></span> <span data-ttu-id="f2099-132">Una vez realizado un pedido, el módulo de confirmación de pedido se puede utilizar para mostrar los detalles de confirmación.</span><span class="sxs-lookup"><span data-stu-id="f2099-132">After an order is placed, the order confirmation module can be used to show the confirmation details.</span></span>
- <span data-ttu-id="f2099-133">**Módulos de página de gestión de cuentas**: el módulo de inicio de sesión permite a los clientes iniciar sesión en una cuenta existente y el módulo de suscripción les permite crear una cuenta nueva.</span><span class="sxs-lookup"><span data-stu-id="f2099-133">**Account management modules** – The sign-in module lets customers sign in to an existing account, and the sign-up module lets them create a new account.</span></span> <span data-ttu-id="f2099-134">Una vez creada una cuenta, el módulo de historial del pedido se puede usar para ver pedidos recientes y el módulo de detalles del pedido se puede usar para ver los detalles del pedido.</span><span class="sxs-lookup"><span data-stu-id="f2099-134">After an account is created, the order history module can be used to view recent orders, and the order details module can be used to view order details.</span></span>
- <span data-ttu-id="f2099-135">**Módulo de recomendaciones**: las recomendaciones se muestran a través del módulo de colocación de producto.</span><span class="sxs-lookup"><span data-stu-id="f2099-135">**Recommendations module** – Recommendations are shown by using the product placement module.</span></span> <span data-ttu-id="f2099-136">Este módulo admite listas algorítmicas y listas editoriales que se pueden mostrar en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="f2099-136">This module supports algorithmic and editorial lists that can be showcased on any page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f2099-137">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f2099-137">Additional resources</span></span>

[<span data-ttu-id="f2099-138">Módulo Contenedor</span><span class="sxs-lookup"><span data-stu-id="f2099-138">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="f2099-139">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="f2099-139">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="f2099-140">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="f2099-140">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="f2099-141">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="f2099-141">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="f2099-142">Módulo de confirmación de pedido</span><span class="sxs-lookup"><span data-stu-id="f2099-142">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="f2099-143">Módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="f2099-143">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="f2099-144">Módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="f2099-144">Footer module</span></span>](author-footer-module.md)
