---
title: Módulo de tarjeta de regalo
description: En este tema se tratan los módulos de tarjeta regalo y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: a8428963e105e422dcd048863c17df0926a409ac
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411121"
---
# <a name="gift-card-module"></a><span data-ttu-id="3321f-103">Módulo de tarjeta de regalo</span><span class="sxs-lookup"><span data-stu-id="3321f-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3321f-104">En este tema se tratan los módulos de tarjeta regalo y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3321f-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="3321f-105">Información general</span><span class="sxs-lookup"><span data-stu-id="3321f-105">Overview</span></span>

<span data-ttu-id="3321f-106">Las tarjetas de regalo son una forma común de pago y el módulo de tarjeta de regalo se puede usar en un módulo de pago para aceptar tarjetas de regalo.</span><span class="sxs-lookup"><span data-stu-id="3321f-106">Gift cards are a common form of payment, and the gift card module can be used in a checkout module to accept gift cards.</span></span> <span data-ttu-id="3321f-107">El módulo de tarjeta de regalo admite tarjetas de regalo Dynamics 365, SVS y Givex.</span><span class="sxs-lookup"><span data-stu-id="3321f-107">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="3321f-108">Las tarjetas de regalo SVS y Givex se canjean a través del proveedor de pagos Adyen.</span><span class="sxs-lookup"><span data-stu-id="3321f-108">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span>

<span data-ttu-id="3321f-109">Para obtener más información sobre la compatibilidad con tarjetas de regalo externas como SVS y Givex, consulte [Soporte para tarjetas de regalo externas](./dev-itpro/gift-card.md)</span><span class="sxs-lookup"><span data-stu-id="3321f-109">For more information on support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md)</span></span>

<span data-ttu-id="3321f-110">La siguiente imagen muestra un ejemplo de un módulo de tarjeta regalo en una página de finalización de compra.</span><span class="sxs-lookup"><span data-stu-id="3321f-110">The following image shows an example of a gift card module on a checkout page.</span></span>

![Ejemplo de un módulo de tarjeta regalo](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="3321f-112">Propiedades del módulo</span><span class="sxs-lookup"><span data-stu-id="3321f-112">Module properties</span></span>

- <span data-ttu-id="3321f-113">**Mostrar campos adicionales** - Esta propiedad define qué campos se deben mostrar para las tarjetas de regalo además del número de la tarjeta de regalo, que siempre se muestra de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3321f-113">**Show additional fields** - This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="3321f-114">Por ejemplo, algunas tarjetas de regalo admiten mostrar un número de identificación personal (PIN), y otras admiten mostrar un PIN y una fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="3321f-114">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="3321f-115">Alternativamente, esta propiedad podría establecerse en "Ninguno", que solo mostraría el número de la tarjeta de regalo y ningún campo adicional.</span><span class="sxs-lookup"><span data-stu-id="3321f-115">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="3321f-116">Valores admitidos:</span><span class="sxs-lookup"><span data-stu-id="3321f-116">Supported values:</span></span>
-   <span data-ttu-id="3321f-117">PIN</span><span class="sxs-lookup"><span data-stu-id="3321f-117">PIN</span></span>
-   <span data-ttu-id="3321f-118">Fecha de caducidad</span><span class="sxs-lookup"><span data-stu-id="3321f-118">Expiration date</span></span>
-   <span data-ttu-id="3321f-119">PIN y fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="3321f-119">PIN and expiration date</span></span> 
-   <span data-ttu-id="3321f-120">None</span><span class="sxs-lookup"><span data-stu-id="3321f-120">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="3321f-121">Configuración del sitio para módulos de tarjetas de regalo</span><span class="sxs-lookup"><span data-stu-id="3321f-121">Site settings for gift card modules</span></span>

<span data-ttu-id="3321f-122">En el creador de sitios de Commerce bajo **Configuraciones del sitio \> Extensiones**, hay una configuración de módulo de tarjeta de regalo llamada **Tipo de tarjeta de regalo compatible**.</span><span class="sxs-lookup"><span data-stu-id="3321f-122">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="3321f-123">Esta configuración admite tres valores:</span><span class="sxs-lookup"><span data-stu-id="3321f-123">This setting supports three values:</span></span>
- <span data-ttu-id="3321f-124">**Tarjeta de regalo de Dynamics 365** - Cuando se aplica esta configuración, el módulo de tarjeta de regalo solo permite canjear tarjetas de regalo de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="3321f-124">**Dynamics 365 gift card** - When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="3321f-125">Esta configuración solo se admite para usuarios que hayan iniciado sesión en el sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="3321f-125">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="3321f-126">**Tarjetas de regalo SVS y Givex** - Cuando se aplica esta configuración, el módulo de tarjeta de regalo solo permite canjear tarjetas de regalo de Givex y SVS.</span><span class="sxs-lookup"><span data-stu-id="3321f-126">**SVS and Givex gift cards** - When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="3321f-127">Esta configuración se admite para usuarios anónimos y que hayan iniciado sesión en el sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="3321f-127">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="3321f-128">**Tarjetas de regalo Dynamics 365, SVS y Givex** - Cuando se aplica esta configuración, el módulo de tarjeta de regalo permite canjear tarjetas de regalo de Dynamics 365, Givex y SVS.</span><span class="sxs-lookup"><span data-stu-id="3321f-128">**Dynamics 365, SVS, and Givex gift cards** - When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="3321f-129">Esta configuración solo se admite para usuarios que hayan iniciado sesión en el sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="3321f-129">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="3321f-130">Agregar un módulo de tarjeta regalo a una página</span><span class="sxs-lookup"><span data-stu-id="3321f-130">Add a gift card module to a page</span></span>

<span data-ttu-id="3321f-131">Para obtener instrucciones sobre cómo agregar un módulo de tarjeta de regalo a una página de pago y configurar las propiedades requeridas, consulte [Módulo de pago](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="3321f-131">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3321f-132">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="3321f-132">Additional resources</span></span>

[<span data-ttu-id="3321f-133">Visión general de kit de inicio</span><span class="sxs-lookup"><span data-stu-id="3321f-133">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="3321f-134">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="3321f-134">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="3321f-135">Compatibilidad para tarjetas de regalo externas</span><span class="sxs-lookup"><span data-stu-id="3321f-135">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)
