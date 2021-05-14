---
title: Módulo de tarjeta de regalo
description: En este tema se tratan los módulos de tarjeta regalo y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8db7e597241f1fd552f6b960c2b57b0ba83da949
ms.sourcegitcommit: efde05c758b2e02960760d875569d780d77d5550
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2021
ms.locfileid: "5962772"
---
# <a name="gift-card-module"></a><span data-ttu-id="e1289-103">Módulo de tarjeta de regalo</span><span class="sxs-lookup"><span data-stu-id="e1289-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e1289-104">En este tema se tratan los módulos de tarjeta regalo y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e1289-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="e1289-105">Los módulos de tarjetas de regalo se pueden usar para en módulos de pago para aceptar tarjetas de pago, un método de pago habitual utilizado en transacciones de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="e1289-105">Gift card modules can be used in checkout modules to accept gift cards, a common form of payment used for e-Commerce transactions.</span></span> <span data-ttu-id="e1289-106">El módulo de tarjeta de regalo admite tarjetas de regalo Dynamics 365, SVS y Givex.</span><span class="sxs-lookup"><span data-stu-id="e1289-106">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="e1289-107">Las tarjetas de regalo SVS y Givex se canjean a través del proveedor de pagos Adyen.</span><span class="sxs-lookup"><span data-stu-id="e1289-107">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span> <span data-ttu-id="e1289-108">Para obtener más información sobre la compatibilidad con tarjetas de regalo externas como SVS y Givex, consulte [Soporte para tarjetas de regalo externas](./dev-itpro/gift-card.md).</span><span class="sxs-lookup"><span data-stu-id="e1289-108">For more information about support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e1289-109">El soporte para canjear tarjetas de regalo SVS y Givex durante el proceso de pago está disponible en Dynamics 365 Commerce 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="e1289-109">Support for redeeming SVS and Givex gift cards during checkout flow is available in the Dynamics 365 Commerce 10.0.11 release.</span></span> 

<span data-ttu-id="e1289-110">Hay dos módulos de tarjetas de regalo disponibles:</span><span class="sxs-lookup"><span data-stu-id="e1289-110">There are two gift card modules available:</span></span>

- <span data-ttu-id="e1289-111">**Tarjeta regalo**: este módulo se puede utilizar en una página de pago para canjear una tarjeta de regalo como oferta.</span><span class="sxs-lookup"><span data-stu-id="e1289-111">**Gift card** – This module can be used on a checkout page to redeem a gift card as tender.</span></span> 
- <span data-ttu-id="e1289-112">**Comprobación del saldo de la tarjeta regalo**: este módulo se puede utilizar en cualquier página para comprobar el saldo de una tarjeta regalo.</span><span class="sxs-lookup"><span data-stu-id="e1289-112">**Gift card balance check** – This module can be used on any page to check the balance on a gift card.</span></span> <span data-ttu-id="e1289-113">Este módulo está disponible en Commerce, versión 10.0.14 y posterior.</span><span class="sxs-lookup"><span data-stu-id="e1289-113">This module is available in Commerce release 10.0.14 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="e1289-114">La compatibilidad con el módulo de verificación de saldo de la tarjeta de regalo está disponible en Dynamics 365 Commerce 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="e1289-114">Support for the gift card balance check module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="e1289-115">La siguiente imagen muestra un ejemplo de un módulo de tarjeta regalo en una página de finalización de compra.</span><span class="sxs-lookup"><span data-stu-id="e1289-115">The following image shows an example of a gift card module on a checkout page.</span></span>

![Ejemplo de un módulo de tarjeta regalo](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="e1289-117">Propiedades del módulo</span><span class="sxs-lookup"><span data-stu-id="e1289-117">Module properties</span></span>

- <span data-ttu-id="e1289-118">**Mostrar campos adicionales**: esta propiedad define qué campos se deben mostrar para las tarjetas de regalo, además del número de la tarjeta regalo, que siempre se muestra de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e1289-118">**Show additional fields** – This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="e1289-119">Por ejemplo, algunas tarjetas de regalo admiten mostrar un número de identificación personal (PIN), y otras admiten mostrar un PIN y una fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="e1289-119">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="e1289-120">Alternativamente, esta propiedad podría establecerse en "Ninguno", que solo mostraría el número de la tarjeta de regalo y ningún campo adicional.</span><span class="sxs-lookup"><span data-stu-id="e1289-120">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="e1289-121">Valores admitidos:</span><span class="sxs-lookup"><span data-stu-id="e1289-121">Supported values:</span></span>
-   <span data-ttu-id="e1289-122">PIN</span><span class="sxs-lookup"><span data-stu-id="e1289-122">PIN</span></span>
-   <span data-ttu-id="e1289-123">Fecha de caducidad</span><span class="sxs-lookup"><span data-stu-id="e1289-123">Expiration date</span></span>
-   <span data-ttu-id="e1289-124">PIN y fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="e1289-124">PIN and expiration date</span></span> 
-   <span data-ttu-id="e1289-125">None</span><span class="sxs-lookup"><span data-stu-id="e1289-125">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="e1289-126">Configuración del sitio para módulos de tarjetas de regalo</span><span class="sxs-lookup"><span data-stu-id="e1289-126">Site settings for gift card modules</span></span>

<span data-ttu-id="e1289-127">En el creador de sitios de Commerce bajo **Configuraciones del sitio \> Extensiones**, hay una configuración de módulo de tarjeta de regalo llamada **Tipo de tarjeta de regalo compatible**.</span><span class="sxs-lookup"><span data-stu-id="e1289-127">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="e1289-128">Esta configuración admite tres valores:</span><span class="sxs-lookup"><span data-stu-id="e1289-128">This setting supports three values:</span></span>
- <span data-ttu-id="e1289-129">**Tarjeta de regalo de Dynamics 365**: cuando se aplica esta configuración, el módulo de tarjeta de regalo solo permite canjear tarjetas de regalo de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e1289-129">**Dynamics 365 gift card** – When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="e1289-130">Esta configuración solo se admite para usuarios que hayan iniciado sesión en el sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="e1289-130">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="e1289-131">**Tarjetas de regalo SVS y Givex**: cuando se aplica esta configuración, el módulo de tarjeta de regalo solo permite canjear tarjetas de regalo de Givex y SVS.</span><span class="sxs-lookup"><span data-stu-id="e1289-131">**SVS and Givex gift cards** – When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="e1289-132">Esta configuración se admite para usuarios anónimos y que hayan iniciado sesión en el sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="e1289-132">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="e1289-133">**Tarjetas de regalo Dynamics 365, SVS y Givex**: cuando se aplica esta configuración, el módulo de tarjeta de regalo permite canjear tarjetas de regalo de Dynamics 365, Givex y SVS.</span><span class="sxs-lookup"><span data-stu-id="e1289-133">**Dynamics 365, SVS, and Givex gift cards** – When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="e1289-134">Esta configuración solo se admite para usuarios que hayan iniciado sesión en el sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="e1289-134">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1289-135">Estos ajustes están disponibles en Dynamics 365 Commerce 10.0.11 y son necesarios solo si necesita soporte para tarjetas de regalo SVS o Givex.</span><span class="sxs-lookup"><span data-stu-id="e1289-135">These settings are available in the Dynamics 365 Commerce 10.0.11 release and are required only if you need support for SVS or Givex gift cards.</span></span> <span data-ttu-id="e1289-136">Si está actualizando desde una versión anterior de Dynamics 365 Commerce, debe actualizar manualmente el archivo appsettings.json.</span><span class="sxs-lookup"><span data-stu-id="e1289-136">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="e1289-137">Para obtener instrucciones sobre cómo actualizar el archivo appsettings.json, consulte [Actualizaciones de SDK y biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="e1289-137">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span> 

## <a name="extend-internal-gift-cards-for-use-in-e-commerce-storefronts"></a><span data-ttu-id="e1289-138">Ampliar las tarjetas regalo internas para su uso en tiendas de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="e1289-138">Extend internal gift cards for use in e-commerce storefronts</span></span>

<span data-ttu-id="e1289-139">De forma predeterminada, las tarjetas de regalo internas no están optimizadas para su uso en escaparates de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="e1289-139">By default, internal gift cards aren't optimized for use in e-commerce storefronts.</span></span> <span data-ttu-id="e1289-140">Por lo tanto, antes de permitir que se utilicen tarjetas de regalo internas para el pago, debe configurarlas con extensiones que ayuden a hacerlas más seguras.</span><span class="sxs-lookup"><span data-stu-id="e1289-140">Therefore, before you allow internal gift cards to be used for payment, you should configure them with extensions that help make them more secure.</span></span> <span data-ttu-id="e1289-141">Estas son las áreas de tarjetas de regalo que debe ampliar antes de permitir que las tarjetas de regalo internas se utilicen en producción:</span><span class="sxs-lookup"><span data-stu-id="e1289-141">Here are the gift card areas that you should extend before you allow internal gift cards to be used in production:</span></span>

- <span data-ttu-id="e1289-142">**Numero de tarjeta de regalo**: las secuencias de números se utilizan para generar números de tarjetas de regalo para tarjetas de regalo internas.</span><span class="sxs-lookup"><span data-stu-id="e1289-142">**Gift card number** – Number sequences are used to generate gift card numbers for internal gift cards.</span></span> <span data-ttu-id="e1289-143">Debido a que las secuencias de números se pueden predecir fácilmente, debe ampliar la generación de números de tarjetas regalo para que se utilicen cadenas aleatorias y criptográficamente seguras para los números de tarjetas regalo que se emiten.</span><span class="sxs-lookup"><span data-stu-id="e1289-143">Because number sequences can easily be predicted, you should extend the generation of gift card numbers so that random, cryptographically secure strings are used for the gift card numbers that are issued.</span></span>
- <span data-ttu-id="e1289-144">**GetBalance**: la API **GetBalance** se utiliza para buscar saldos de tarjetas de regalo.</span><span class="sxs-lookup"><span data-stu-id="e1289-144">**GetBalance** – The **GetBalance** API is used to look up gift card balances.</span></span> <span data-ttu-id="e1289-145">De forma predeterminada, esta API es pública.</span><span class="sxs-lookup"><span data-stu-id="e1289-145">By default, this API public.</span></span> <span data-ttu-id="e1289-146">Si no se requiere un PIN para buscar saldos de tarjetas regalo, existe el riesgo de que los ataques por fuerza bruta puedan usar la API **GetBalance** para intentar buscar números de tarjetas de regalo que tengan saldo.</span><span class="sxs-lookup"><span data-stu-id="e1289-146">If a PIN isn't required to look up gift card balances, there is a risk that brute force attacks could use the **GetBalance** API to try to look up gift card numbers that have balances.</span></span> <span data-ttu-id="e1289-147">Al implementar ambos requisitos de PIN para las tarjetas regalo y la limitación de API, se puede ayudar a mitigar el riesgo.</span><span class="sxs-lookup"><span data-stu-id="e1289-147">By implementing both PIN requirements for internal gift cards and API throttling, you can help mitigate the risk.</span></span>
- <span data-ttu-id="e1289-148">**PIN** de forma predeterminada, las tarjetas regalo internas no admiten los PIN.</span><span class="sxs-lookup"><span data-stu-id="e1289-148">**PIN** – By default, internal gift cards don't support PINs.</span></span> <span data-ttu-id="e1289-149">Debe extender las tarjetas de regalo internas para que se requiera un PIN para buscar saldos.</span><span class="sxs-lookup"><span data-stu-id="e1289-149">You should extend internal gift cards so that a PIN is required to look up balances.</span></span> <span data-ttu-id="e1289-150">Esta funcionalidad también se puede usar para bloquear tarjetas de regalo después de intentos consecutivos incorrectos de introducir el PIN.</span><span class="sxs-lookup"><span data-stu-id="e1289-150">This functionality can also be used to lock gift cards after consecutive incorrect attempts to enter the PIN.</span></span>

## <a name="enable-gift-card-payments-for-guest-checkout"></a><span data-ttu-id="e1289-151">Habilitar pagos con tarjeta regalo para la finalización de compra de invitados</span><span class="sxs-lookup"><span data-stu-id="e1289-151">Enable gift card payments for guest checkout</span></span>

<span data-ttu-id="e1289-152">De forma predeterminada, los pagos con tarjeta regalo no están habilitados para la finalización de compra de invitados (anónima).</span><span class="sxs-lookup"><span data-stu-id="e1289-152">By default, gift card payments aren't enabled for guest (anonymous) checkout.</span></span> <span data-ttu-id="e1289-153">Para habilitarlos, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e1289-153">To enable them, follow these steps.</span></span>

1. <span data-ttu-id="e1289-154">En la sede central de Commerce, vaya a **Minorista y comercio \> Configuración de canales \> Configuración de PDV \> PDV \> Operaciones de PDV**.</span><span class="sxs-lookup"><span data-stu-id="e1289-154">In Commerce headquarters, go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> POS Operations**.</span></span>
1. <span data-ttu-id="e1289-155">Seleccione y mantenga presionado (o haga clic con el botón derecho) el encabezado de la cuadrícula y luego seleccione **Insertar columnas**.</span><span class="sxs-lookup"><span data-stu-id="e1289-155">Select and hold (or right-click) the header of the grid, and then select **Insert columns**.</span></span>
1. <span data-ttu-id="e1289-156">En el cuadro de diálogo **Insertar columnas**, seleccione el cuadro de diálogo **AllowAnonymousAccess**.</span><span class="sxs-lookup"><span data-stu-id="e1289-156">In the **Insert columns** dialog box, select the **AllowAnonymousAccess** check box.</span></span>
1. <span data-ttu-id="e1289-157">Seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="e1289-157">Select **Update**.</span></span>
1. <span data-ttu-id="e1289-158">Para operaciones **520** (Saldo de tarjeta regalo) y **214**, seleccione el valor **AllowAnonymousAccess** en **1**.</span><span class="sxs-lookup"><span data-stu-id="e1289-158">For operations **520** (Gift card balance) and **214**, set the **AllowAnonymousAccess** value to **1**.</span></span>
1. <span data-ttu-id="e1289-159">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e1289-159">Select **Save**.</span></span>
1. <span data-ttu-id="e1289-160">Ejecute el trabajo de programador **1090** para sincronizar los cambios con la base de datos de canal.</span><span class="sxs-lookup"><span data-stu-id="e1289-160">Run the **1090** scheduler job to sync changes to the channel database.</span></span> 

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="e1289-161">Agregar un módulo de tarjeta regalo a una página</span><span class="sxs-lookup"><span data-stu-id="e1289-161">Add a gift card module to a page</span></span>

<span data-ttu-id="e1289-162">Para obtener instrucciones sobre cómo agregar un módulo de tarjeta de regalo a una página de pago y configurar las propiedades requeridas, consulte [Módulo de pago](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="e1289-162">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e1289-163">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e1289-163">Additional resources</span></span>

[<span data-ttu-id="e1289-164">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="e1289-164">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="e1289-165">Módulo de icono de carro</span><span class="sxs-lookup"><span data-stu-id="e1289-165">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="e1289-166">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="e1289-166">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="e1289-167">Módulo de pago</span><span class="sxs-lookup"><span data-stu-id="e1289-167">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="e1289-168">Módulo de dirección de envío</span><span class="sxs-lookup"><span data-stu-id="e1289-168">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="e1289-169">Módulo de opciones de entrega</span><span class="sxs-lookup"><span data-stu-id="e1289-169">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="e1289-170">Módulo de información de recogida</span><span class="sxs-lookup"><span data-stu-id="e1289-170">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="e1289-171">Módulo de detalles del pedido</span><span class="sxs-lookup"><span data-stu-id="e1289-171">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="e1289-172">Compatibilidad para tarjetas de regalo externas</span><span class="sxs-lookup"><span data-stu-id="e1289-172">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)

[<span data-ttu-id="e1289-173">Actualizaciones de SDK y biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="e1289-173">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
