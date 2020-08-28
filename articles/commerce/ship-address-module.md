---
title: Módulo de dirección de envío
description: En este tema se trata el modulo de dirección de envío y se explica la forma de configurarlo en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 380d268ec0ba64367f090c31408eac1c54d0ff17
ms.sourcegitcommit: ae0843763a8b6b232bb71db326fab28605ac6c53
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2020
ms.locfileid: "3661450"
---
# <a name="shipping-address-module"></a><span data-ttu-id="e3503-103">Módulo de dirección de envío</span><span class="sxs-lookup"><span data-stu-id="e3503-103">Shipping address module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="e3503-104">En este tema se describe el modulo de dirección de envío y se explica la forma de configurarlo en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e3503-104">This topic describes covers the shipping address module and explains how to configure it in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e3503-105">Información general</span><span class="sxs-lookup"><span data-stu-id="e3503-105">Overview</span></span>

<span data-ttu-id="e3503-106">El módulo de dirección de envío permite a los clientes agregar o seleccionar la dirección de envío para un pedido durante el flujo de finalización de compra.</span><span class="sxs-lookup"><span data-stu-id="e3503-106">The shipping address module lets customers add or select the shipping address for an order during the checkout flow.</span></span> <span data-ttu-id="e3503-107">Si un cliente inicia sesión, se muestran las direcciones que se guardaron anteriormente para ese cliente, de forma que las pueda seleccionar.</span><span class="sxs-lookup"><span data-stu-id="e3503-107">If a customer is signed in, any addresses that were previously saved for that customer are shown, and the customer can select among them.</span></span> <span data-ttu-id="e3503-108">El cliente también puede agregar una dirección nueva.</span><span class="sxs-lookup"><span data-stu-id="e3503-108">The customer can also add a new address.</span></span> <span data-ttu-id="e3503-109">El módulo de dirección de envío se usa para todos los artículos de un pedido que requieren envío.</span><span class="sxs-lookup"><span data-stu-id="e3503-109">The shipping address module is used for all items on an order that require shipping.</span></span>

<span data-ttu-id="e3503-110">Los formatos de dirección de envío se pueden definir en la sede de Commerce para cada país o región, y el módulo de dirección de envío aplica las reglas específicas del país o la región.</span><span class="sxs-lookup"><span data-stu-id="e3503-110">Shipping address formats can be defined in Commerce headquarters for each country or region, and the shipping address module then enforces country/region-specific rules.</span></span>

<span data-ttu-id="e3503-111">Cuando los clientes especifican una dirección de envío durante el proceso de finalización de compra, tienen la opción de guardar la dirección como una dirección principal.</span><span class="sxs-lookup"><span data-stu-id="e3503-111">When customers enter a shipping address during the checkout flow, they have the option to save the address as a primary address.</span></span> <span data-ttu-id="e3503-112">Esta opción solo se muestra si un cliente ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="e3503-112">This option is shown only if a customer is signed in.</span></span>

<span data-ttu-id="e3503-113">Aunque el módulo de dirección de envío no proporcione la validación de la dirección, esta funcionalidad se puede implementar a través de la personalización.</span><span class="sxs-lookup"><span data-stu-id="e3503-113">Although the shipping address module doesn't provide address validation, this functionality can be implemented through customization.</span></span>

<span data-ttu-id="e3503-114">La siguiente ilustración muestra un ejemplo de un nuevo módulo de dirección de envío en una página de finalización de compra.</span><span class="sxs-lookup"><span data-stu-id="e3503-114">The following illustration shows an example of a new shipping address module on a checkout page.</span></span>

![Ejemplo de módulo de dirección de envío en una página de finalización de compra](./media/ecommerce-shippingaddress.PNG)

## <a name="module-properties"></a><span data-ttu-id="e3503-116">Propiedades del módulo</span><span class="sxs-lookup"><span data-stu-id="e3503-116">Module properties</span></span>

| <span data-ttu-id="e3503-117">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="e3503-117">Property name</span></span> | <span data-ttu-id="e3503-118">Valores</span><span class="sxs-lookup"><span data-stu-id="e3503-118">Values</span></span> | <span data-ttu-id="e3503-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3503-119">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="e3503-120">Cabecera</span><span class="sxs-lookup"><span data-stu-id="e3503-120">Heading</span></span> | <span data-ttu-id="e3503-121">Texto de encabezado y etiqueta de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**)</span><span class="sxs-lookup"><span data-stu-id="e3503-121">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="e3503-122">Un encabezado opcional para el módulo de dirección de envío.</span><span class="sxs-lookup"><span data-stu-id="e3503-122">An optional heading for the shipping address module.</span></span> |
| <span data-ttu-id="e3503-123">Mostrar tipo de dirección</span><span class="sxs-lookup"><span data-stu-id="e3503-123">Show address type</span></span> | <span data-ttu-id="e3503-124">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="e3503-124">**True** or **False**</span></span> | <span data-ttu-id="e3503-125">Si esta propiedad opcional se establece en **Verdadero**, se mostrará un tipo de dirección, como **Domicilio** o **Empresa**.</span><span class="sxs-lookup"><span data-stu-id="e3503-125">If this optional property is set to **True**, an address type, such as **Home** or **Business**, will be shown.</span></span> <span data-ttu-id="e3503-126">Si no se especifica ningún tipo de dirección, la dirección se guardará automáticamente como de **Tipo**=**Otro**.</span><span class="sxs-lookup"><span data-stu-id="e3503-126">If no address type is specified, the address will automatically be saved as **Type**=**Other**.</span></span> |

## <a name="add-a-shipping-address-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="e3503-127">Agregar un módulo de dirección de envío a una página de finalización de compra y establecer las propiedades necesarias</span><span class="sxs-lookup"><span data-stu-id="e3503-127">Add a shipping address module to a checkout page and set the required properties</span></span>

<span data-ttu-id="e3503-128">Un módulo de dirección de envío solo se puede agregar a un módulo de finalización de compra.</span><span class="sxs-lookup"><span data-stu-id="e3503-128">A shipping address module can be added only to a checkout module.</span></span> <span data-ttu-id="e3503-129">Para obtener más información sobre cómo configurar el módulo de dirección de envío y agregarlo a una página de finalización de compra, consulte [Módulo de finalización de compra](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="e3503-129">For more information about how to configure the shipping address module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e3503-130">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e3503-130">Additional resources</span></span>

[<span data-ttu-id="e3503-131">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="e3503-131">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="e3503-132">Módulo de icono de carro</span><span class="sxs-lookup"><span data-stu-id="e3503-132">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="e3503-133">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="e3503-133">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="e3503-134">Módulo de pago</span><span class="sxs-lookup"><span data-stu-id="e3503-134">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="e3503-135">Módulo de opciones de entrega</span><span class="sxs-lookup"><span data-stu-id="e3503-135">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="e3503-136">Módulo de detalles del pedido</span><span class="sxs-lookup"><span data-stu-id="e3503-136">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="e3503-137">Módulo de tarjeta de regalo</span><span class="sxs-lookup"><span data-stu-id="e3503-137">Gift card module</span></span>](add-giftcard.md)
