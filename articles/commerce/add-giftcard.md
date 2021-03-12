---
title: Módulo de tarjeta de regalo
description: En este tema se tratan los módulos de tarjeta regalo y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d9626f33ced0433bc96ed58429e95d4f75af6508
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980391"
---
# <a name="gift-card-module"></a><span data-ttu-id="01bef-103">Módulo de tarjeta de regalo</span><span class="sxs-lookup"><span data-stu-id="01bef-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="01bef-104">En este tema se tratan los módulos de tarjeta regalo y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="01bef-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="01bef-105">Información general</span><span class="sxs-lookup"><span data-stu-id="01bef-105">Overview</span></span>

<span data-ttu-id="01bef-106">Los módulos de tarjetas de regalo se pueden usar para en módulos de pago para aceptar tarjetas de pago, un método de pago habitual utilizado en transacciones de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="01bef-106">Gift card modules can be used in checkout modules to accept gift cards, a common form of payment used for e-Commerce transactions.</span></span> <span data-ttu-id="01bef-107">El módulo de tarjeta de regalo admite tarjetas de regalo Dynamics 365, SVS y Givex.</span><span class="sxs-lookup"><span data-stu-id="01bef-107">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="01bef-108">Las tarjetas de regalo SVS y Givex se canjean a través del proveedor de pagos Adyen.</span><span class="sxs-lookup"><span data-stu-id="01bef-108">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span> <span data-ttu-id="01bef-109">Para obtener más información sobre la compatibilidad con tarjetas de regalo externas como SVS y Givex, consulte [Soporte para tarjetas de regalo externas](./dev-itpro/gift-card.md).</span><span class="sxs-lookup"><span data-stu-id="01bef-109">For more information about support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md).</span></span>

> [!NOTE]
> <span data-ttu-id="01bef-110">El soporte para canjear tarjetas de regalo SVS y Givex durante el proceso de pago está disponible en Dynamics 365 Commerce 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="01bef-110">Support for redeeming SVS and Givex gift cards during checkout flow is available in the Dynamics 365 Commerce 10.0.11 release.</span></span> 

<span data-ttu-id="01bef-111">Hay dos módulos de tarjetas de regalo disponibles:</span><span class="sxs-lookup"><span data-stu-id="01bef-111">There are two gift card modules available:</span></span>

- <span data-ttu-id="01bef-112">**Tarjeta de regalo**: este módulo se puede utilizar en una página de pago para canjear una tarjeta de regalo como oferta.</span><span class="sxs-lookup"><span data-stu-id="01bef-112">**Gift card** - This module can be used on a checkout page to redeem a gift card as tender.</span></span> 
- <span data-ttu-id="01bef-113">**Comprobación del saldo de la tarjeta de regalo**: este módulo se puede utilizar en cualquier página para comprobar el saldo de una tarjeta regalo.</span><span class="sxs-lookup"><span data-stu-id="01bef-113">**Gift card balance check** - This module can be used on any page to check the balance on a gift card.</span></span> <span data-ttu-id="01bef-114">Este módulo está disponible en Commerce, versión 10.0.14 y posterior.</span><span class="sxs-lookup"><span data-stu-id="01bef-114">This module is available in Commerce release 10.0.14 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="01bef-115">La compatibilidad con el módulo de verificación de saldo de la tarjeta de regalo está disponible en Dynamics 365 Commerce 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="01bef-115">Support for the gift card balance check module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="01bef-116">La siguiente imagen muestra un ejemplo de un módulo de tarjeta regalo en una página de finalización de compra.</span><span class="sxs-lookup"><span data-stu-id="01bef-116">The following image shows an example of a gift card module on a checkout page.</span></span>

![Ejemplo de un módulo de tarjeta regalo](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="01bef-118">Propiedades del módulo</span><span class="sxs-lookup"><span data-stu-id="01bef-118">Module properties</span></span>

- <span data-ttu-id="01bef-119">**Mostrar campos adicionales** - Esta propiedad define qué campos se deben mostrar para las tarjetas de regalo además del número de la tarjeta de regalo, que siempre se muestra de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="01bef-119">**Show additional fields** - This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="01bef-120">Por ejemplo, algunas tarjetas de regalo admiten mostrar un número de identificación personal (PIN), y otras admiten mostrar un PIN y una fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="01bef-120">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="01bef-121">Alternativamente, esta propiedad podría establecerse en "Ninguno", que solo mostraría el número de la tarjeta de regalo y ningún campo adicional.</span><span class="sxs-lookup"><span data-stu-id="01bef-121">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="01bef-122">Valores admitidos:</span><span class="sxs-lookup"><span data-stu-id="01bef-122">Supported values:</span></span>
-   <span data-ttu-id="01bef-123">PIN</span><span class="sxs-lookup"><span data-stu-id="01bef-123">PIN</span></span>
-   <span data-ttu-id="01bef-124">Fecha de caducidad</span><span class="sxs-lookup"><span data-stu-id="01bef-124">Expiration date</span></span>
-   <span data-ttu-id="01bef-125">PIN y fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="01bef-125">PIN and expiration date</span></span> 
-   <span data-ttu-id="01bef-126">None</span><span class="sxs-lookup"><span data-stu-id="01bef-126">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="01bef-127">Configuración del sitio para módulos de tarjetas de regalo</span><span class="sxs-lookup"><span data-stu-id="01bef-127">Site settings for gift card modules</span></span>

<span data-ttu-id="01bef-128">En el creador de sitios de Commerce bajo **Configuraciones del sitio \> Extensiones**, hay una configuración de módulo de tarjeta de regalo llamada **Tipo de tarjeta de regalo compatible**.</span><span class="sxs-lookup"><span data-stu-id="01bef-128">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="01bef-129">Esta configuración admite tres valores:</span><span class="sxs-lookup"><span data-stu-id="01bef-129">This setting supports three values:</span></span>
- <span data-ttu-id="01bef-130">**Tarjeta de regalo de Dynamics 365** - Cuando se aplica esta configuración, el módulo de tarjeta de regalo solo permite canjear tarjetas de regalo de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="01bef-130">**Dynamics 365 gift card** - When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="01bef-131">Esta configuración solo se admite para usuarios que hayan iniciado sesión en el sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="01bef-131">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="01bef-132">**Tarjetas de regalo SVS y Givex** - Cuando se aplica esta configuración, el módulo de tarjeta de regalo solo permite canjear tarjetas de regalo de Givex y SVS.</span><span class="sxs-lookup"><span data-stu-id="01bef-132">**SVS and Givex gift cards** - When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="01bef-133">Esta configuración se admite para usuarios anónimos y que hayan iniciado sesión en el sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="01bef-133">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="01bef-134">**Tarjetas de regalo Dynamics 365, SVS y Givex** - Cuando se aplica esta configuración, el módulo de tarjeta de regalo permite canjear tarjetas de regalo de Dynamics 365, Givex y SVS.</span><span class="sxs-lookup"><span data-stu-id="01bef-134">**Dynamics 365, SVS, and Givex gift cards** - When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="01bef-135">Esta configuración solo se admite para usuarios que hayan iniciado sesión en el sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="01bef-135">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01bef-136">Estos ajustes están disponibles en Dynamics 365 Commerce 10.0.11 y son necesarios solo si necesita soporte para tarjetas de regalo SVS o Givex.</span><span class="sxs-lookup"><span data-stu-id="01bef-136">These settings are available in the Dynamics 365 Commerce 10.0.11 release and are required only if you need support for SVS or Givex gift cards.</span></span> <span data-ttu-id="01bef-137">Si está actualizando desde una versión anterior de Dynamics 365 Commerce, debe actualizar manualmente el archivo appsettings.json.</span><span class="sxs-lookup"><span data-stu-id="01bef-137">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="01bef-138">Para obtener instrucciones sobre cómo actualizar el archivo appsettings.json, consulte [Actualizaciones de SDK y biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="01bef-138">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span> 

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="01bef-139">Agregar un módulo de tarjeta regalo a una página</span><span class="sxs-lookup"><span data-stu-id="01bef-139">Add a gift card module to a page</span></span>

<span data-ttu-id="01bef-140">Para obtener instrucciones sobre cómo agregar un módulo de tarjeta de regalo a una página de pago y configurar las propiedades requeridas, consulte [Módulo de pago](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="01bef-140">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="01bef-141">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="01bef-141">Additional resources</span></span>

[<span data-ttu-id="01bef-142">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="01bef-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="01bef-143">Módulo de icono de carro</span><span class="sxs-lookup"><span data-stu-id="01bef-143">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="01bef-144">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="01bef-144">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="01bef-145">Módulo de pago</span><span class="sxs-lookup"><span data-stu-id="01bef-145">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="01bef-146">Módulo de dirección de envío</span><span class="sxs-lookup"><span data-stu-id="01bef-146">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="01bef-147">Módulo de opciones de entrega</span><span class="sxs-lookup"><span data-stu-id="01bef-147">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="01bef-148">Módulo de información de recogida</span><span class="sxs-lookup"><span data-stu-id="01bef-148">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="01bef-149">Módulo de detalles del pedido</span><span class="sxs-lookup"><span data-stu-id="01bef-149">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="01bef-150">Compatibilidad para tarjetas de regalo externas</span><span class="sxs-lookup"><span data-stu-id="01bef-150">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)

[<span data-ttu-id="01bef-151">Actualizaciones de SDK y biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="01bef-151">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)
