---
title: Módulo de dirección de envío
description: En este tema se trata el modulo de dirección de envío y se explica la forma de configurarlo en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 02/11/2021
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
ms.openlocfilehash: e590c966ca6bd8111df5f91cbac0485afaa45c78
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234422"
---
# <a name="shipping-address-module"></a><span data-ttu-id="11a47-103">Módulo de dirección de envío</span><span class="sxs-lookup"><span data-stu-id="11a47-103">Shipping address module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="11a47-104">En este tema se describe el modulo de dirección de envío y se explica la forma de configurarlo en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="11a47-104">This topic describes covers the shipping address module and explains how to configure it in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="11a47-105">El módulo de dirección de envío permite a los clientes agregar o seleccionar la dirección de envío para un pedido durante el flujo de finalización de compra.</span><span class="sxs-lookup"><span data-stu-id="11a47-105">The shipping address module lets customers add or select the shipping address for an order during the checkout flow.</span></span> <span data-ttu-id="11a47-106">Si un cliente inicia sesión, se muestran las direcciones que se guardaron anteriormente para ese cliente, de forma que las pueda seleccionar.</span><span class="sxs-lookup"><span data-stu-id="11a47-106">If a customer is signed in, any addresses that were previously saved for that customer are shown, and the customer can select among them.</span></span> <span data-ttu-id="11a47-107">El cliente también puede agregar una dirección nueva.</span><span class="sxs-lookup"><span data-stu-id="11a47-107">The customer can also add a new address.</span></span> <span data-ttu-id="11a47-108">El módulo de dirección de envío se usa para todos los artículos de un pedido que requieren envío.</span><span class="sxs-lookup"><span data-stu-id="11a47-108">The shipping address module is used for all items on an order that require shipping.</span></span>

<span data-ttu-id="11a47-109">Los formatos de dirección de envío se pueden definir en la sede de Commerce para cada país o región, y el módulo de dirección de envío aplica las reglas específicas del país o la región.</span><span class="sxs-lookup"><span data-stu-id="11a47-109">Shipping address formats can be defined in Commerce headquarters for each country or region, and the shipping address module then enforces country/region-specific rules.</span></span>

<span data-ttu-id="11a47-110">Cuando los clientes especifican una dirección de envío durante el proceso de finalización de compra, tienen la opción de guardar la dirección como una dirección principal.</span><span class="sxs-lookup"><span data-stu-id="11a47-110">When customers enter a shipping address during the checkout flow, they have the option to save the address as a primary address.</span></span> <span data-ttu-id="11a47-111">Esta opción solo se muestra si un cliente ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="11a47-111">This option is shown only if a customer is signed in.</span></span>

<span data-ttu-id="11a47-112">Aunque el módulo de dirección de envío no proporcione la validación de la dirección, esta funcionalidad se puede implementar a través de la personalización.</span><span class="sxs-lookup"><span data-stu-id="11a47-112">Although the shipping address module doesn't provide address validation, this functionality can be implemented through customization.</span></span>

<span data-ttu-id="11a47-113">La siguiente ilustración muestra un ejemplo de un nuevo módulo de dirección de envío en una página de finalización de compra.</span><span class="sxs-lookup"><span data-stu-id="11a47-113">The following illustration shows an example of a new shipping address module on a checkout page.</span></span>

![Ejemplo de módulo de dirección de envío en una página de finalización de compra](./media/ecommerce-shippingaddress.PNG)

## <a name="module-properties"></a><span data-ttu-id="11a47-115">Propiedades del módulo</span><span class="sxs-lookup"><span data-stu-id="11a47-115">Module properties</span></span>

| <span data-ttu-id="11a47-116">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="11a47-116">Property name</span></span> | <span data-ttu-id="11a47-117">Valores</span><span class="sxs-lookup"><span data-stu-id="11a47-117">Values</span></span> | <span data-ttu-id="11a47-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="11a47-118">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="11a47-119">Cabecera</span><span class="sxs-lookup"><span data-stu-id="11a47-119">Heading</span></span> | <span data-ttu-id="11a47-120">Texto de encabezado y etiqueta de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**)</span><span class="sxs-lookup"><span data-stu-id="11a47-120">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="11a47-121">Un encabezado opcional para el módulo de dirección de envío.</span><span class="sxs-lookup"><span data-stu-id="11a47-121">An optional heading for the shipping address module.</span></span> |
| <span data-ttu-id="11a47-122">Mostrar tipo de dirección</span><span class="sxs-lookup"><span data-stu-id="11a47-122">Show address type</span></span> | <span data-ttu-id="11a47-123">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="11a47-123">**True** or **False**</span></span> | <span data-ttu-id="11a47-124">Si esta propiedad opcional se establece en **Verdadero**, se mostrará un tipo de dirección, como **Domicilio** o **Empresa**.</span><span class="sxs-lookup"><span data-stu-id="11a47-124">If this optional property is set to **True**, an address type, such as **Home** or **Business**, will be shown.</span></span> <span data-ttu-id="11a47-125">Si no se especifica ningún tipo de dirección, la dirección se guardará automáticamente como de **Tipo**=**Otro**.</span><span class="sxs-lookup"><span data-stu-id="11a47-125">If no address type is specified, the address will automatically be saved as **Type**=**Other**.</span></span> |
| <span data-ttu-id="11a47-126">Habilitar la sugerencia automática</span><span class="sxs-lookup"><span data-stu-id="11a47-126">Enable auto suggestion</span></span>| <span data-ttu-id="11a47-127">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="11a47-127">**True** or **False**</span></span> | <span data-ttu-id="11a47-128">Si esta propiedad opcional se establece en **Verdadero**, se proporcionarán sugerencias de direcciones automáticas.</span><span class="sxs-lookup"><span data-stu-id="11a47-128">If this optional property is set to **True**, automatic address suggestions will be provided.</span></span> <span data-ttu-id="11a47-129">Estas sugerencias llevan tecnología de Bing Maps.</span><span class="sxs-lookup"><span data-stu-id="11a47-129">These suggestions are powered by Bing Maps.</span></span> <span data-ttu-id="11a47-130">Para obtener información sobre cómo configurar la integración de Bing Maps para su sitio, consulte [Módulo selector de tienda](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="11a47-130">For information about how to set up Bing Maps integration for your site, see [Store selector module](store-selector.md).</span></span> <span data-ttu-id="11a47-131">Esta característica está disponible en la versión 10.0.15 de Commerce.</span><span class="sxs-lookup"><span data-stu-id="11a47-131">This feature is available as of the Commerce version 10.0.15 release.</span></span>|
|<span data-ttu-id="11a47-132">Opciones de sugerencias automáticas</span><span class="sxs-lookup"><span data-stu-id="11a47-132">Auto suggest options</span></span>| <span data-ttu-id="11a47-133">Un número</span><span class="sxs-lookup"><span data-stu-id="11a47-133">A number</span></span>| <span data-ttu-id="11a47-134">Si las sugerencias de direcciones automáticas están habilitadas, puede especificar opciones adicionales, como el número máximo de sugerencias que se deben proporcionar.</span><span class="sxs-lookup"><span data-stu-id="11a47-134">If automatic address suggestions are enabled, you can specify additional options, such as the maximum number of suggestions that should be provided.</span></span>|

## <a name="add-a-shipping-address-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="11a47-135">Agregar un módulo de dirección de envío a una página de finalización de compra y establecer las propiedades necesarias</span><span class="sxs-lookup"><span data-stu-id="11a47-135">Add a shipping address module to a checkout page and set the required properties</span></span>

<span data-ttu-id="11a47-136">Un módulo de dirección de envío solo se puede agregar a un módulo de finalización de compra.</span><span class="sxs-lookup"><span data-stu-id="11a47-136">A shipping address module can be added only to a checkout module.</span></span> <span data-ttu-id="11a47-137">Para obtener más información sobre cómo configurar el módulo de dirección de envío y agregarlo a una página de finalización de compra, consulte [Módulo de finalización de compra](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="11a47-137">For more information about how to configure the shipping address module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="11a47-138">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="11a47-138">Additional resources</span></span>

[<span data-ttu-id="11a47-139">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="11a47-139">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="11a47-140">Módulo de icono de carro</span><span class="sxs-lookup"><span data-stu-id="11a47-140">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="11a47-141">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="11a47-141">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="11a47-142">Módulo de pago</span><span class="sxs-lookup"><span data-stu-id="11a47-142">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="11a47-143">Módulo de opciones de entrega</span><span class="sxs-lookup"><span data-stu-id="11a47-143">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="11a47-144">Módulo de información de recogida</span><span class="sxs-lookup"><span data-stu-id="11a47-144">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="11a47-145">Módulo de detalles del pedido</span><span class="sxs-lookup"><span data-stu-id="11a47-145">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="11a47-146">Módulo de tarjeta de regalo</span><span class="sxs-lookup"><span data-stu-id="11a47-146">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="11a47-147">Módulo de selector de tienda</span><span class="sxs-lookup"><span data-stu-id="11a47-147">Store selector module</span></span>](store-selector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]