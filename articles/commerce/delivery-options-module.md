---
title: Módulo de opciones de entrega
description: En este tema se tratan los módulos de opciones de entrega y se explica cómo configurarlos en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: d0e5fa731d4b808cda9863074d17d1917410f399
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213683"
---
# <a name="delivery-options-module"></a><span data-ttu-id="dcae7-103">Módulo de opciones de entrega</span><span class="sxs-lookup"><span data-stu-id="dcae7-103">Delivery options module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="dcae7-104">En este tema se tratan los módulos de opciones de entrega y se explica cómo configurarlos en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="dcae7-104">This topic covers delivery options modules and explains how to configure them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="dcae7-105">Los módulos de opciones de entrega permiten a los clientes seleccionar un modo de entrega, como envío o recogida, para su pedido en línea.</span><span class="sxs-lookup"><span data-stu-id="dcae7-105">Delivery options modules let customers select a mode of delivery such as shipping or pickup for their online order.</span></span> <span data-ttu-id="dcae7-106">Se requiere una dirección de envío para determinar el modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="dcae7-106">A shipping address is required to determine the mode of delivery.</span></span> <span data-ttu-id="dcae7-107">Si cambia la dirección de envío, las opciones de entrega se deben recuperar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="dcae7-107">If the shipping address changes, the delivery options must be retrieved again.</span></span> <span data-ttu-id="dcae7-108">Si el pedido solo incluye artículos que se recogerán en una tienda, este módulo se oculta automáticamente.</span><span class="sxs-lookup"><span data-stu-id="dcae7-108">If an order includes only items that will be picked up in a store, this module is automatically hidden.</span></span>

<span data-ttu-id="dcae7-109">Para obtener información sobre cómo configurar los modos de entrega, consulte [Configuración de canales en línea](channel-setup-online.md) y [Configurar modos de entrega](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span><span class="sxs-lookup"><span data-stu-id="dcae7-109">For information about how to configure modes of delivery, see [Online channel setup](channel-setup-online.md) and [Set up modes of delivery](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span></span>

<span data-ttu-id="dcae7-110">Cada modo de entrega puede tener un cargo asociado.</span><span class="sxs-lookup"><span data-stu-id="dcae7-110">Each delivery mode can have an associated charge.</span></span> <span data-ttu-id="dcae7-111">Para obtener más información sobre cómo configurar cargos para una tienda en línea, consulte [Cargos automáticos avanzados omnicanal](omni-auto-charges.md).</span><span class="sxs-lookup"><span data-stu-id="dcae7-111">For more information about how to configure charges for an online store, see [Omni-channel Advanced auto-charges](omni-auto-charges.md).</span></span>

<span data-ttu-id="dcae7-112">En la versión 10.0.13 de Commerce, el módulo de opciones de entrega se ha actualizado para admitir las características **Cargos de encabezado sin prorrateo** y **Envío como cargo de línea**.</span><span class="sxs-lookup"><span data-stu-id="dcae7-112">In Commerce version 10.0.13, the delivery options module has been updated to support the **Header charges without proration** and **Shipping as a line charge** features.</span></span> <span data-ttu-id="dcae7-113">Si el prorrateo está desactivado, se espera que el flujo de trabajo de comercio electrónico no permita un modo mixto de entrega para los artículos del carro (es decir, algunos artículos se seleccionan para envío, pero otros se seleccionan para recogida).</span><span class="sxs-lookup"><span data-stu-id="dcae7-113">If proration is turned off, the expectation is that the e-Commerce workflow won't allow a mixed mode of delivery for the items in the cart (that is, some items are selected for shipment, but others are selected for pickup).</span></span> <span data-ttu-id="dcae7-114">La característica **Cargos de encabezado sin prorrateo** requiere que se active la marca **Habilitar modo de entrega coherente en el canal** en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="dcae7-114">The **Header charges without proration** feature requires that the **Enable consistent delivery mode handling in channel** flag be turned on in Commerce headquarters.</span></span> <span data-ttu-id="dcae7-115">Cuando esa marca está activada, los cargos de envío se aplicarán en el nivel de encabezado o en el nivel de línea, según la configuración de la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="dcae7-115">When that flag is turned on, shipping charges will be applied at either the header level or the line level, depending on the configuration in Commerce headquarters.</span></span>

<span data-ttu-id="dcae7-116">El tema Fabrikam admite un modo de entrega mixto, en el que algunos artículos se seleccionan para envío y otros se seleccionan para recogida.</span><span class="sxs-lookup"><span data-stu-id="dcae7-116">The Fabrikam theme supports a mixed mode of delivery, where some items are selected for shipment but others are selected for pickup.</span></span> <span data-ttu-id="dcae7-117">En este modo, los cargos de envío se prorratearán para todos los artículos seleccionados para el modo de envío.</span><span class="sxs-lookup"><span data-stu-id="dcae7-117">In this mode, shipping charges will be prorated for all items that are selected for the shipping mode of delivery.</span></span> <span data-ttu-id="dcae7-118">Para que funcione un modo mixto de entrega, primero debe configurar la característica **Cargos de encabezado con prorrateo** en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="dcae7-118">For a mixed mode of delivery to work, you must first configure the **Header charges with proration** feature in Commerce headquarters.</span></span> <span data-ttu-id="dcae7-119">Para obtener más información sobre esta configuración, consulte [Prorratear los cargos de encabezado para que coincidan con las líneas de ventas](pro-rate-charges-matching-lines.md).</span><span class="sxs-lookup"><span data-stu-id="dcae7-119">For more information about this configuration, see [Prorate header charges to match sales lines](pro-rate-charges-matching-lines.md).</span></span>

<span data-ttu-id="dcae7-120">Si se aplican cargos de envío a los artículos de línea, se pueden mostrar en la línea del carro para cada artículo.</span><span class="sxs-lookup"><span data-stu-id="dcae7-120">If shipping charges apply to line items, they can be shown on the cart line for each item.</span></span> <span data-ttu-id="dcae7-121">Esta funcionalidad requiere que se active la propiedad **Mostrar los cargos de envío del artículo de línea** tanto para el módulo de carro como para el módulo de finalización de compra.</span><span class="sxs-lookup"><span data-stu-id="dcae7-121">This functionality requires that the **Show shipping charges on line item** property be turned on for both the cart module and the checkout module.</span></span> <span data-ttu-id="dcae7-122">Para obtener más información, consulte [Módulo de carro](add-cart-module.md) y [Módulo de finalización de compra](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="dcae7-122">For more information, see [Cart module](add-cart-module.md) and [Checkout module](add-checkout-module.md).</span></span>

<span data-ttu-id="dcae7-123">La siguiente ilustración muestra un ejemplo de un módulo de opciones de entrega en una página de finalización de compra.</span><span class="sxs-lookup"><span data-stu-id="dcae7-123">The following illustration shows an example of a delivery options module on a checkout page.</span></span>

![Ejemplo de módulo de opciones de entrega en una página de finalización de compra](./media/ecommerce-deliveryoptions.PNG)

## <a name="delivery-options-module-properties"></a><span data-ttu-id="dcae7-125">Propiedades del módulo de opciones de entrega</span><span class="sxs-lookup"><span data-stu-id="dcae7-125">Delivery options module properties</span></span>

| <span data-ttu-id="dcae7-126">Propiedad</span><span class="sxs-lookup"><span data-stu-id="dcae7-126">Property</span></span> | <span data-ttu-id="dcae7-127">Valores</span><span class="sxs-lookup"><span data-stu-id="dcae7-127">Values</span></span> | <span data-ttu-id="dcae7-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="dcae7-128">Description</span></span> |
|----------|--------|-------------|
| <span data-ttu-id="dcae7-129">Cabecera</span><span class="sxs-lookup"><span data-stu-id="dcae7-129">Heading</span></span> | <span data-ttu-id="dcae7-130">Texto de encabezado y etiqueta de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**)</span><span class="sxs-lookup"><span data-stu-id="dcae7-130">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="dcae7-131">Un encabezado opcional para el módulo de opciones de entrega.</span><span class="sxs-lookup"><span data-stu-id="dcae7-131">An optional heading for the delivery options module.</span></span> |
| <span data-ttu-id="dcae7-132">Nombre de clase CSS personalizado</span><span class="sxs-lookup"><span data-stu-id="dcae7-132">Custom CSS class name</span></span> | <span data-ttu-id="dcae7-133">Texto</span><span class="sxs-lookup"><span data-stu-id="dcae7-133">Text</span></span> | <span data-ttu-id="dcae7-134">Nombre de clase de hojas de estilo en cascada personalizadas (CSS) que se utilizará para representar este módulo, si corresponde.</span><span class="sxs-lookup"><span data-stu-id="dcae7-134">A custom Cascading Style Sheets (CSS) class name that will be used to render this module, if applicable.</span></span> |
| <span data-ttu-id="dcae7-135">Filtrar opción de modo de entrega</span><span class="sxs-lookup"><span data-stu-id="dcae7-135">Filter Delivery Mode Option</span></span> | <span data-ttu-id="dcae7-136">**No filtrar** o **Modos sin envío**</span><span class="sxs-lookup"><span data-stu-id="dcae7-136">**Do not filter** or **Non-shipping modes**</span></span> | <span data-ttu-id="dcae7-137">Un valor que especifica si el módulo de opciones de entrega debe filtrar todos los modos de entrega que no son de envío.</span><span class="sxs-lookup"><span data-stu-id="dcae7-137">A value that specifies whether the delivery options module should filter out all non-shipping delivery modes.</span></span> |

## <a name="add-a-delivery-options-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="dcae7-138">Agregar un módulo de opciones de entrega a una página de finalización de compra y establecer las propiedades necesarias</span><span class="sxs-lookup"><span data-stu-id="dcae7-138">Add a delivery options module to a checkout page and set the required properties</span></span>

<span data-ttu-id="dcae7-139">Un módulo de opciones de entrega solo se puede agregar a un módulo de finalización de compra.</span><span class="sxs-lookup"><span data-stu-id="dcae7-139">A delivery options module can be added only to a checkout module.</span></span> <span data-ttu-id="dcae7-140">Para obtener más información sobre cómo configurar el módulo de opciones de entrega y agregarlo a una página de finalización de compra, consulte [Módulo de finalización de compra](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="dcae7-140">For more information about how to configure the delivery options module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dcae7-141">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="dcae7-141">Additional resources</span></span>

[<span data-ttu-id="dcae7-142">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="dcae7-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="dcae7-143">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="dcae7-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="dcae7-144">Módulo de pago</span><span class="sxs-lookup"><span data-stu-id="dcae7-144">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="dcae7-145">Módulo de dirección de envío</span><span class="sxs-lookup"><span data-stu-id="dcae7-145">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="dcae7-146">Módulo de información de recogida</span><span class="sxs-lookup"><span data-stu-id="dcae7-146">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="dcae7-147">Módulo de detalles del pedido</span><span class="sxs-lookup"><span data-stu-id="dcae7-147">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="dcae7-148">Módulo de tarjeta de regalo</span><span class="sxs-lookup"><span data-stu-id="dcae7-148">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="dcae7-149">Configuración de canal en línea</span><span class="sxs-lookup"><span data-stu-id="dcae7-149">Online channel setup</span></span>](channel-setup-online.md)

[<span data-ttu-id="dcae7-150">Cargos automáticos avanzados omnicanal</span><span class="sxs-lookup"><span data-stu-id="dcae7-150">Omni-channel Advanced auto-charges</span></span>](omni-auto-charges.md)

[<span data-ttu-id="dcae7-151">Prorratear los cargos de encabezado para que coincidan con las líneas de ventas</span><span class="sxs-lookup"><span data-stu-id="dcae7-151">Prorate header charges to match sales lines</span></span>](pro-rate-charges-matching-lines.md)

[<span data-ttu-id="dcae7-152">Configurar modos de entrega</span><span class="sxs-lookup"><span data-stu-id="dcae7-152">Set up modes of delivery</span></span>](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)


[!INCLUDE[footer-include](../includes/footer-banner.md)]