---
title: Aplicar la configuración de unidades de medida
description: Este tema cubre las configuraciones de unidades de medida y describe cómo aplicarlas en Microsoft Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 7d338ba207c9a101f5e224ca66555b16a457bcbc
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271410"
---
# <a name="apply-unit-of-measure-settings"></a><span data-ttu-id="c3273-103">Aplicar la configuración de unidades de medida</span><span class="sxs-lookup"><span data-stu-id="c3273-103">Apply unit of measure settings</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c3273-104">Este tema cubre las configuraciones de unidades de medida y describe cómo aplicarlas en Microsoft Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c3273-104">This topic covers unit of measure settings and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="c3273-105">Un producto se puede vender en diferentes unidades, como "cada uno", "par" y "docena".</span><span class="sxs-lookup"><span data-stu-id="c3273-105">A product can be sold in different units, such as "each," "pair," and "dozen."</span></span> <span data-ttu-id="c3273-106">En la sede de Commerce, la unidad de medida de venta por unidad puede definirse para un producto y mostrarse en un sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="c3273-106">In Commerce headquarters, the sell-by unit of measure can be defined for a product and shown on an e-commerce site.</span></span> <span data-ttu-id="c3273-107">Por ejemplo, si un minorista vende un producto tanto individualmente como en docenas, las unidades de medida disponibles se pueden mostrar junto con otra información del producto.</span><span class="sxs-lookup"><span data-stu-id="c3273-107">For example, if a retailer sells a product both individually and in dozens, the available units of measure can be shown together with other product information.</span></span>

<span data-ttu-id="c3273-108">En el ejemplo de la siguiente ilustración, una unidad de medida de venta por **ea** (cada uno) se ha configurado para un producto en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="c3273-108">In the example in the following illustration, a sell-by unit of measure of **ea** (each) has been configured for a product in Commerce headquarters.</span></span>

![Ejemplo de un producto configurado con una unidad de medida en la sede de Commerce](./media/Productunit-headquarters.PNG)

> [!NOTE]
> <span data-ttu-id="c3273-110">El soporte para aplicar y mostrar la unidad de medida está disponible a partir de la versión 10.0.19 de Commerce.</span><span class="sxs-lookup"><span data-stu-id="c3273-110">Support for applying and showing the unit of measure is available as of the Commerce version 10.0.19 release.</span></span>

## <a name="unit-of-measure-settings"></a><span data-ttu-id="c3273-111">Configuración de unidades de medida</span><span class="sxs-lookup"><span data-stu-id="c3273-111">Unit of measure settings</span></span>

<span data-ttu-id="c3273-112">La configuración de visualización de unidades de medida se define en el creador de sitios de Commerce, en **Configuración del sitio \> Extensiones \> Mostrar unidad de medida para los productos**.</span><span class="sxs-lookup"><span data-stu-id="c3273-112">Unit of measure display settings are defined in Commerce site builder, at **Site settings \> Extensions \> Display unit of measure for products**.</span></span> <span data-ttu-id="c3273-113">Hay tres configuraciones compatibles:</span><span class="sxs-lookup"><span data-stu-id="c3273-113">There are three supported settings:</span></span>

- <span data-ttu-id="c3273-114">**No mostrar**: cuando se selecciona esta configuración, el sitio de comercio electrónico no mostrará la unidad de medida del producto.</span><span class="sxs-lookup"><span data-stu-id="c3273-114">**Do not display** – When this setting is selected, the e-commerce site won't show the unit of measure for the product.</span></span> <span data-ttu-id="c3273-115">Este comportamiento es el predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c3273-115">This behavior is the default behavior.</span></span>
- <span data-ttu-id="c3273-116">**Mostrar en la experiencia de compra de productos**: cuando se selecciona esta configuración, la unidad de medida se muestra en las páginas de detalles del producto, el carrito, la finalización de compra, el historial de pedidos y detalles de pedidos.</span><span class="sxs-lookup"><span data-stu-id="c3273-116">**Display in the product buying experience** – When this setting is selected, the unit of measure is shown on product details, cart, checkout, order history, and order details pages.</span></span>
- <span data-ttu-id="c3273-117">**Mostrar en la experiencia de navegación y compra de productos**: cuando se selecciona esta configuración, la unidad de medida se muestra en las páginas de experiencia de compra de productos y también durante la experiencia de navegación de productos.</span><span class="sxs-lookup"><span data-stu-id="c3273-117">**Display in the product browsing and buying experience** – When this setting is selected, the unit of measure is shown on the product buying experience pages and also during the product browsing experience.</span></span> <span data-ttu-id="c3273-118">Como parte de este comportamiento, las unidades de medida se muestran en los resultados de búsqueda y en los módulos de recopilación de productos.</span><span class="sxs-lookup"><span data-stu-id="c3273-118">As part of this behavior, units of measure are shown in search results and product collection modules.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3273-119">La configuración de visualización de unidades de medida está disponible a partir de la versión 10.0.19 de Commerce.</span><span class="sxs-lookup"><span data-stu-id="c3273-119">Unit of measure display settings are available as of the Commerce version 10.0.19 release.</span></span> <span data-ttu-id="c3273-120">Si está actualizando desde una versión anterior de Commerce, debe actualizar manualmente el archivo appsettings.json.</span><span class="sxs-lookup"><span data-stu-id="c3273-120">If you're updating from an older version of Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="c3273-121">Para obtener instrucciones, consulte [Actualizaciones del SDK y la biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="c3273-121">For instructions, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span>

## <a name="modules-that-use-unit-of-measure-settings"></a><span data-ttu-id="c3273-122">Módulos que usan configuraciones de unidades de medida</span><span class="sxs-lookup"><span data-stu-id="c3273-122">Modules that use unit of measure settings</span></span>

<span data-ttu-id="c3273-123">Los módulos que utilizan la configuración de unidades de medida incluyen el cuadro de compra, la lista de deseos, el carrito, el icono del carrito, el contenedor de resultados de búsqueda, la colección de productos, la finalización de compra y los módulos de detalles del pedido.</span><span class="sxs-lookup"><span data-stu-id="c3273-123">Modules that use the unit of measure settings include the buy box, wishlist, cart, cart icon, search results container, product collection, checkout, and order details modules.</span></span>

<span data-ttu-id="c3273-124">En el ejemplo de la siguiente ilustración, una página de detalles del producto (PDP) muestra la unidad de medida (**ea**) para un producto.</span><span class="sxs-lookup"><span data-stu-id="c3273-124">In the example in the following illustration, a product details page (PDP) shows the unit of measure (**ea**) for a product.</span></span>

![Ejemplo de un PDP que muestra la unidad de medida](./media/Productunit-PDP.png)

<span data-ttu-id="c3273-126">En el ejemplo de la siguiente ilustración, un módulo de colección de productos muestra la unidad de medida (**ea**) para un producto.</span><span class="sxs-lookup"><span data-stu-id="c3273-126">In the example in the following illustration, a product collection module shows the unit of measure (**ea**) for a product.</span></span>

![Ejemplo de un módulo de colección de productos que muestra la unidad de medida](./media/Productunit-productcollection.png)

## <a name="additional-resources"></a><span data-ttu-id="c3273-128">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c3273-128">Additional resources</span></span>

[<span data-ttu-id="c3273-129">Descripción general de la biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="c3273-129">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="c3273-130">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="c3273-130">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="c3273-131">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="c3273-131">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="c3273-132">Módulos y páginas de gestión de cuentas</span><span class="sxs-lookup"><span data-stu-id="c3273-132">Account management pages and modules</span></span>](account-management.md)

[<span data-ttu-id="c3273-133">Actualizaciones de SDK y bibliotecas de módulos</span><span class="sxs-lookup"><span data-stu-id="c3273-133">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
