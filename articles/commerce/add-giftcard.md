---
title: Módulo de tarjeta de regalo
description: En este tema se tratan los módulos de tarjeta regalo y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/31/2020
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
ms.openlocfilehash: 4cc947b9d6f3cfa51bce2155170c49e9529d0f7d
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761090"
---
# <a name="gift-card-module"></a><span data-ttu-id="be1e9-103">Módulo de tarjeta de regalo</span><span class="sxs-lookup"><span data-stu-id="be1e9-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="be1e9-104">En este tema se tratan los módulos de tarjeta regalo y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="be1e9-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="be1e9-105">Información general</span><span class="sxs-lookup"><span data-stu-id="be1e9-105">Overview</span></span>

<span data-ttu-id="be1e9-106">Los módulos de tarjetas de regalo se pueden usar para en módulos de pago para aceptar tarjetas de pago, un método de pago habitual utilizado en transacciones de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="be1e9-106">Gift card modules can be used in checkout modules to accept gift cards, a common form of payment used for e-Commerce transactions.</span></span> <span data-ttu-id="be1e9-107">El módulo de tarjeta de regalo admite tarjetas de regalo Dynamics 365, SVS y Givex.</span><span class="sxs-lookup"><span data-stu-id="be1e9-107">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="be1e9-108">Las tarjetas de regalo SVS y Givex se canjean a través del proveedor de pagos Adyen.</span><span class="sxs-lookup"><span data-stu-id="be1e9-108">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span> <span data-ttu-id="be1e9-109">Para obtener más información sobre la compatibilidad con tarjetas de regalo externas como SVS y Givex, consulte [Soporte para tarjetas de regalo externas](./dev-itpro/gift-card.md).</span><span class="sxs-lookup"><span data-stu-id="be1e9-109">For more information about support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md).</span></span>

<span data-ttu-id="be1e9-110">Hay dos módulos de tarjetas de regalo disponibles:</span><span class="sxs-lookup"><span data-stu-id="be1e9-110">There are two gift card modules available:</span></span>

- <span data-ttu-id="be1e9-111">**Tarjeta de regalo**: este módulo se puede utilizar en una página de pago para canjear una tarjeta de regalo como oferta.</span><span class="sxs-lookup"><span data-stu-id="be1e9-111">**Gift card** - This module can be used on a checkout page to redeem a gift card as tender.</span></span> 
- <span data-ttu-id="be1e9-112">**Comprobación del saldo de la tarjeta de regalo**: este módulo se puede utilizar en cualquier página para comprobar el saldo de una tarjeta regalo.</span><span class="sxs-lookup"><span data-stu-id="be1e9-112">**Gift card balance check** - This module can be used on any page to check the balance on a gift card.</span></span> <span data-ttu-id="be1e9-113">Este módulo está disponible en Commerce, versión 10.0.14 y posterior.</span><span class="sxs-lookup"><span data-stu-id="be1e9-113">This module is available in Commerce release 10.0.14 and later.</span></span>

<span data-ttu-id="be1e9-114">La siguiente imagen muestra un ejemplo de un módulo de tarjeta regalo en una página de finalización de compra.</span><span class="sxs-lookup"><span data-stu-id="be1e9-114">The following image shows an example of a gift card module on a checkout page.</span></span>

![Ejemplo de un módulo de tarjeta regalo](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="be1e9-116">Propiedades del módulo</span><span class="sxs-lookup"><span data-stu-id="be1e9-116">Module properties</span></span>

- <span data-ttu-id="be1e9-117">**Mostrar campos adicionales** - Esta propiedad define qué campos se deben mostrar para las tarjetas de regalo además del número de la tarjeta de regalo, que siempre se muestra de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="be1e9-117">**Show additional fields** - This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="be1e9-118">Por ejemplo, algunas tarjetas de regalo admiten mostrar un número de identificación personal (PIN), y otras admiten mostrar un PIN y una fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="be1e9-118">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="be1e9-119">Alternativamente, esta propiedad podría establecerse en "Ninguno", que solo mostraría el número de la tarjeta de regalo y ningún campo adicional.</span><span class="sxs-lookup"><span data-stu-id="be1e9-119">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="be1e9-120">Valores admitidos:</span><span class="sxs-lookup"><span data-stu-id="be1e9-120">Supported values:</span></span>
-   <span data-ttu-id="be1e9-121">PIN</span><span class="sxs-lookup"><span data-stu-id="be1e9-121">PIN</span></span>
-   <span data-ttu-id="be1e9-122">Fecha de caducidad</span><span class="sxs-lookup"><span data-stu-id="be1e9-122">Expiration date</span></span>
-   <span data-ttu-id="be1e9-123">PIN y fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="be1e9-123">PIN and expiration date</span></span> 
-   <span data-ttu-id="be1e9-124">None</span><span class="sxs-lookup"><span data-stu-id="be1e9-124">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="be1e9-125">Configuración del sitio para módulos de tarjetas de regalo</span><span class="sxs-lookup"><span data-stu-id="be1e9-125">Site settings for gift card modules</span></span>

<span data-ttu-id="be1e9-126">En el creador de sitios de Commerce bajo **Configuraciones del sitio \> Extensiones**, hay una configuración de módulo de tarjeta de regalo llamada **Tipo de tarjeta de regalo compatible**.</span><span class="sxs-lookup"><span data-stu-id="be1e9-126">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="be1e9-127">Esta configuración admite tres valores:</span><span class="sxs-lookup"><span data-stu-id="be1e9-127">This setting supports three values:</span></span>
- <span data-ttu-id="be1e9-128">**Tarjeta de regalo de Dynamics 365** - Cuando se aplica esta configuración, el módulo de tarjeta de regalo solo permite canjear tarjetas de regalo de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="be1e9-128">**Dynamics 365 gift card** - When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="be1e9-129">Esta configuración solo se admite para usuarios que hayan iniciado sesión en el sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="be1e9-129">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="be1e9-130">**Tarjetas de regalo SVS y Givex** - Cuando se aplica esta configuración, el módulo de tarjeta de regalo solo permite canjear tarjetas de regalo de Givex y SVS.</span><span class="sxs-lookup"><span data-stu-id="be1e9-130">**SVS and Givex gift cards** - When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="be1e9-131">Esta configuración se admite para usuarios anónimos y que hayan iniciado sesión en el sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="be1e9-131">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="be1e9-132">**Tarjetas de regalo Dynamics 365, SVS y Givex** - Cuando se aplica esta configuración, el módulo de tarjeta de regalo permite canjear tarjetas de regalo de Dynamics 365, Givex y SVS.</span><span class="sxs-lookup"><span data-stu-id="be1e9-132">**Dynamics 365, SVS, and Givex gift cards** - When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="be1e9-133">Esta configuración solo se admite para usuarios que hayan iniciado sesión en el sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="be1e9-133">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="be1e9-134">Agregar un módulo de tarjeta regalo a una página</span><span class="sxs-lookup"><span data-stu-id="be1e9-134">Add a gift card module to a page</span></span>

<span data-ttu-id="be1e9-135">Para obtener instrucciones sobre cómo agregar un módulo de tarjeta de regalo a una página de pago y configurar las propiedades requeridas, consulte [Módulo de pago](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="be1e9-135">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="be1e9-136">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="be1e9-136">Additional resources</span></span>

[<span data-ttu-id="be1e9-137">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="be1e9-137">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="be1e9-138">Módulo de icono de carro</span><span class="sxs-lookup"><span data-stu-id="be1e9-138">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="be1e9-139">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="be1e9-139">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="be1e9-140">Módulo de pago</span><span class="sxs-lookup"><span data-stu-id="be1e9-140">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="be1e9-141">Módulo de dirección de envío</span><span class="sxs-lookup"><span data-stu-id="be1e9-141">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="be1e9-142">Módulo de opciones de entrega</span><span class="sxs-lookup"><span data-stu-id="be1e9-142">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="be1e9-143">Módulo de detalles del pedido</span><span class="sxs-lookup"><span data-stu-id="be1e9-143">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="be1e9-144">Compatibilidad para tarjetas de regalo externas</span><span class="sxs-lookup"><span data-stu-id="be1e9-144">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)
