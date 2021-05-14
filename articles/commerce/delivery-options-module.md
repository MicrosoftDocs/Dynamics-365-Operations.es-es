---
title: Módulo de opciones de entrega
description: En este tema se tratan los módulos de opciones de entrega y se explica cómo configurarlos en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 12b0281a27dcf5f567bcd6be5530fa8e26a4ae99
ms.sourcegitcommit: 593438a145672c55ff6a910eabce2939300b40ad
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2021
ms.locfileid: "5937491"
---
# <a name="delivery-options-module"></a><span data-ttu-id="103f4-103">Módulo de opciones de entrega</span><span class="sxs-lookup"><span data-stu-id="103f4-103">Delivery options module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="103f4-104">En este tema se tratan los módulos de opciones de entrega y se explica cómo configurarlos en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="103f4-104">This topic covers delivery options modules and explains how to configure them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="103f4-105">Los módulos de opciones de entrega permiten a los clientes seleccionar un modo de entrega, como envío o recogida, para su pedido en línea.</span><span class="sxs-lookup"><span data-stu-id="103f4-105">Delivery options modules let customers select a mode of delivery such as shipping or pickup for their online order.</span></span> <span data-ttu-id="103f4-106">Se requiere una dirección de envío para determinar el modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="103f4-106">A shipping address is required to determine the mode of delivery.</span></span> <span data-ttu-id="103f4-107">Si cambia la dirección de envío, las opciones de entrega se deben recuperar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="103f4-107">If the shipping address changes, the delivery options must be retrieved again.</span></span> <span data-ttu-id="103f4-108">Si el pedido solo incluye artículos que se recogerán en una tienda, este módulo se oculta automáticamente.</span><span class="sxs-lookup"><span data-stu-id="103f4-108">If an order includes only items that will be picked up in a store, this module is automatically hidden.</span></span>

<span data-ttu-id="103f4-109">Para obtener información sobre cómo configurar los modos de entrega, consulte [Configuración de canales en línea](channel-setup-online.md) y [Configurar modos de entrega](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span><span class="sxs-lookup"><span data-stu-id="103f4-109">For information about how to configure modes of delivery, see [Online channel setup](channel-setup-online.md) and [Set up modes of delivery](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span></span>

<span data-ttu-id="103f4-110">Cada modo de entrega puede tener un cargo asociado.</span><span class="sxs-lookup"><span data-stu-id="103f4-110">Each delivery mode can have an associated charge.</span></span> <span data-ttu-id="103f4-111">Para obtener más información sobre cómo configurar cargos para una tienda en línea, consulte [Cargos automáticos avanzados omnicanal](omni-auto-charges.md).</span><span class="sxs-lookup"><span data-stu-id="103f4-111">For more information about how to configure charges for an online store, see [Omni-channel Advanced auto-charges](omni-auto-charges.md).</span></span>

<span data-ttu-id="103f4-112">En la versión 10.0.13 de Commerce, el módulo de opciones de entrega se ha actualizado para admitir las características **Cargos de encabezado sin prorrateo** y **Envío como cargo de línea**.</span><span class="sxs-lookup"><span data-stu-id="103f4-112">In Commerce version 10.0.13, the delivery options module has been updated to support the **Header charges without proration** and **Shipping as a line charge** features.</span></span> <span data-ttu-id="103f4-113">Si el prorrateo está desactivado, se espera que el flujo de trabajo de comercio electrónico no permita un modo mixto de entrega para los artículos del carro (es decir, algunos artículos se seleccionan para envío, pero otros se seleccionan para recogida).</span><span class="sxs-lookup"><span data-stu-id="103f4-113">If proration is turned off, the expectation is that the e-Commerce workflow won't allow a mixed mode of delivery for the items in the cart (that is, some items are selected for shipment, but others are selected for pickup).</span></span> <span data-ttu-id="103f4-114">La característica **Cargos de encabezado sin prorrateo** requiere que se active la marca **Habilitar modo de entrega coherente en el canal** en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="103f4-114">The **Header charges without proration** feature requires that the **Enable consistent delivery mode handling in channel** flag is turned on in Commerce headquarters.</span></span> <span data-ttu-id="103f4-115">Cuando la marca de característica está activada, los cargos de envío se aplicarán en el nivel de encabezado o en el nivel de línea, según la configuración de la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="103f4-115">When the feature flag is turned on, shipping charges will be applied at either the header level or the line level, depending on the configuration in Commerce headquarters.</span></span>

<span data-ttu-id="103f4-116">El tema Fabrikam admite un modo de entrega mixto, en el que algunos artículos se seleccionan para envío y otros se seleccionan para recogida.</span><span class="sxs-lookup"><span data-stu-id="103f4-116">The Fabrikam theme supports a mixed mode of delivery, where some items are selected for shipment but others are selected for pickup.</span></span> <span data-ttu-id="103f4-117">En este modo, los cargos de envío se prorratearán para todos los artículos seleccionados para el modo de envío.</span><span class="sxs-lookup"><span data-stu-id="103f4-117">In this mode, shipping charges will be prorated for all items that are selected for the shipping mode of delivery.</span></span> <span data-ttu-id="103f4-118">Para que funcione un modo mixto de entrega, primero debe configurar la característica **Cargos de encabezado con prorrateo** en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="103f4-118">For a mixed mode of delivery to work, you must first configure the **Header charges with proration** feature in Commerce headquarters.</span></span> <span data-ttu-id="103f4-119">Para obtener más información sobre esta configuración, consulte [Prorratear los cargos de encabezado para que coincidan con las líneas de ventas](pro-rate-charges-matching-lines.md).</span><span class="sxs-lookup"><span data-stu-id="103f4-119">For more information about this configuration, see [Prorate header charges to match sales lines](pro-rate-charges-matching-lines.md).</span></span>

<span data-ttu-id="103f4-120">Si se aplican cargos de envío a los artículos de línea, se pueden mostrar en la línea del carro para cada artículo.</span><span class="sxs-lookup"><span data-stu-id="103f4-120">If shipping charges apply to line items, they can be shown on the cart line for each item.</span></span> <span data-ttu-id="103f4-121">Esta funcionalidad requiere que se active la propiedad **Mostrar los cargos de envío del artículo de línea** tanto para el módulo de carro como para el módulo de finalización de compra.</span><span class="sxs-lookup"><span data-stu-id="103f4-121">This functionality requires that the **Show shipping charges on line item** property be turned on for both the cart module and the checkout module.</span></span> <span data-ttu-id="103f4-122">Para obtener más información, consulte [Módulo de carro](add-cart-module.md) y [Módulo de finalización de compra](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="103f4-122">For more information, see [Cart module](add-cart-module.md) and [Checkout module](add-checkout-module.md).</span></span>

<span data-ttu-id="103f4-123">La siguiente ilustración muestra un ejemplo de un módulo de opciones de entrega en una página de finalización de compra.</span><span class="sxs-lookup"><span data-stu-id="103f4-123">The following illustration shows an example of a delivery options module on a checkout page.</span></span>

![Ejemplo de módulo de opciones de entrega en una página de finalización de compra](./media/ecommerce-deliveryoptions.PNG)

## <a name="delivery-options-module-properties"></a><span data-ttu-id="103f4-125">Propiedades del módulo de opciones de entrega</span><span class="sxs-lookup"><span data-stu-id="103f4-125">Delivery options module properties</span></span>

| <span data-ttu-id="103f4-126">Propiedad</span><span class="sxs-lookup"><span data-stu-id="103f4-126">Property</span></span> | <span data-ttu-id="103f4-127">Valores</span><span class="sxs-lookup"><span data-stu-id="103f4-127">Values</span></span> | <span data-ttu-id="103f4-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="103f4-128">Description</span></span> |
|----------|--------|-------------|
| <span data-ttu-id="103f4-129">Cabecera</span><span class="sxs-lookup"><span data-stu-id="103f4-129">Heading</span></span> | <span data-ttu-id="103f4-130">Texto de encabezado y etiqueta de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**)</span><span class="sxs-lookup"><span data-stu-id="103f4-130">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="103f4-131">Un encabezado opcional para el módulo de opciones de entrega.</span><span class="sxs-lookup"><span data-stu-id="103f4-131">An optional heading for the delivery options module.</span></span> |
| <span data-ttu-id="103f4-132">Nombre de clase CSS personalizado</span><span class="sxs-lookup"><span data-stu-id="103f4-132">Custom CSS class name</span></span> | <span data-ttu-id="103f4-133">Texto</span><span class="sxs-lookup"><span data-stu-id="103f4-133">Text</span></span> | <span data-ttu-id="103f4-134">Nombre de clase de hojas de estilo en cascada personalizadas (CSS) que se utilizará para representar este módulo, si corresponde.</span><span class="sxs-lookup"><span data-stu-id="103f4-134">A custom Cascading Style Sheets (CSS) class name that will be used to render this module, if applicable.</span></span> |
| <span data-ttu-id="103f4-135">Filtrar opción de modo de entrega</span><span class="sxs-lookup"><span data-stu-id="103f4-135">Filter Delivery Mode Option</span></span> | <span data-ttu-id="103f4-136">**No filtrar** o **Modos sin envío**</span><span class="sxs-lookup"><span data-stu-id="103f4-136">**Do not filter** or **Non-shipping modes**</span></span> | <span data-ttu-id="103f4-137">Un valor que especifica si el módulo de opciones de entrega debe filtrar todos los modos de entrega que no son de envío.</span><span class="sxs-lookup"><span data-stu-id="103f4-137">A value that specifies whether the delivery options module should filter out all non-shipping delivery modes.</span></span> |
| <span data-ttu-id="103f4-138">Seleccionar automáticamente una opción de entrega</span><span class="sxs-lookup"><span data-stu-id="103f4-138">Auto select a delivery option</span></span> | <span data-ttu-id="103f4-139">**No filtrar**, **Seleccionar automáticamente la opción de entrega y mostrar el resumen** o **Seleccionar automáticamente la opción de entrega y no mostrar el resumen**</span><span class="sxs-lookup"><span data-stu-id="103f4-139">**Do not filter**, **Auto select delivery option and show summary**, or **Auto select delivery option and don't show summary**</span></span> | <span data-ttu-id="103f4-140">Esta propiedad aplica automáticamente la primera opción de entrega disponible a la finalización de la compra, sin necesidad de que el usuario la seleccione.</span><span class="sxs-lookup"><span data-stu-id="103f4-140">This property automatically applies the first available delivery option to checkout without requiring the user to select it.</span></span> <span data-ttu-id="103f4-141">Debe usarse solo si hay una opción de entrega disponible.</span><span class="sxs-lookup"><span data-stu-id="103f4-141">It should be used only if there is one available delivery option.</span></span> <span data-ttu-id="103f4-142">Esta propiedad se admite desde la versión 10.0.19 de Commerce.</span><span class="sxs-lookup"><span data-stu-id="103f4-142">This property is supported as of the Commerce version 10.0.19 release.</span></span> |

## <a name="add-a-delivery-options-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="103f4-143">Agregar un módulo de opciones de entrega a una página de finalización de compra y establecer las propiedades necesarias</span><span class="sxs-lookup"><span data-stu-id="103f4-143">Add a delivery options module to a checkout page and set the required properties</span></span>

<span data-ttu-id="103f4-144">Un módulo de opciones de entrega solo se puede agregar a un módulo de finalización de compra.</span><span class="sxs-lookup"><span data-stu-id="103f4-144">A delivery options module can be added only to a checkout module.</span></span> <span data-ttu-id="103f4-145">Para obtener más información sobre cómo configurar el módulo de opciones de entrega y agregarlo a una página de finalización de compra, consulte [Módulo de finalización de compra](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="103f4-145">For more information about how to configure the delivery options module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="103f4-146">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="103f4-146">Additional resources</span></span>

[<span data-ttu-id="103f4-147">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="103f4-147">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="103f4-148">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="103f4-148">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="103f4-149">Módulo de pago</span><span class="sxs-lookup"><span data-stu-id="103f4-149">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="103f4-150">Módulo de dirección de envío</span><span class="sxs-lookup"><span data-stu-id="103f4-150">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="103f4-151">Módulo de información de recogida</span><span class="sxs-lookup"><span data-stu-id="103f4-151">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="103f4-152">Módulo de detalles del pedido</span><span class="sxs-lookup"><span data-stu-id="103f4-152">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="103f4-153">Módulo de tarjeta de regalo</span><span class="sxs-lookup"><span data-stu-id="103f4-153">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="103f4-154">Configuración de canal en línea</span><span class="sxs-lookup"><span data-stu-id="103f4-154">Online channel setup</span></span>](channel-setup-online.md)

[<span data-ttu-id="103f4-155">Cargos automáticos avanzados omnicanal</span><span class="sxs-lookup"><span data-stu-id="103f4-155">Omni-channel Advanced auto-charges</span></span>](omni-auto-charges.md)

[<span data-ttu-id="103f4-156">Prorratear los cargos de encabezado para que coincidan con las líneas de ventas</span><span class="sxs-lookup"><span data-stu-id="103f4-156">Prorate header charges to match sales lines</span></span>](pro-rate-charges-matching-lines.md)

[<span data-ttu-id="103f4-157">Configurar modos de entrega</span><span class="sxs-lookup"><span data-stu-id="103f4-157">Set up modes of delivery</span></span>](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
