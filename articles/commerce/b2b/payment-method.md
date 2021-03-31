---
title: Configurar el método de pago de la cuenta del cliente para sitios de comercio electrónico B2B
description: Este tema describe cómo configurar el método de pago de la cuenta del cliente para los sitios de comercio electrónico de empresa a empresa (B2B).
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 82dfd6ac7e97d838ef442fd6ded4a4f165fc795b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211210"
---
# <a name="configure-the-customer-account-payment-method-for-b2b-e-commerce-sites"></a><span data-ttu-id="69261-103">Configurar el método de pago de la cuenta del cliente para sitios de comercio electrónico B2B</span><span class="sxs-lookup"><span data-stu-id="69261-103">Configure the customer account payment method for B2B e-commerce sites</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="69261-104">Este tema describe cómo configurar el método de pago de la cuenta del cliente para los sitios de comercio electrónico de empresa a empresa (B2B).</span><span class="sxs-lookup"><span data-stu-id="69261-104">This topic describes how to configure the customer account payment method for business-to-business (B2B) e-commerce sites.</span></span>

<span data-ttu-id="69261-105">Los minoristas pueden aceptar distintos tipos de pago a cambio de los productos y los servicios que venden en un canal de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="69261-105">Retailers can accept various types of payment in exchange for the products and services that they sell in an e-commerce channel.</span></span> <span data-ttu-id="69261-106">Al configurar el sistema, se deben configurar en Microsoft Dynamics 365 Commerce todos los tipos de pago que acepte un minorista.</span><span class="sxs-lookup"><span data-stu-id="69261-106">Each payment type that a retailer accepts must be configured in Microsoft Dynamics 365 Commerce when the system is set up.</span></span> <span data-ttu-id="69261-107">El método de pago de la cuenta del cliente (o "a cuenta") debe ser compatible con los sitios de comercio electrónico B2B.</span><span class="sxs-lookup"><span data-stu-id="69261-107">The customer account (or "on account") payment method must be supported on B2B e-commerce sites.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="69261-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="69261-108">Prerequisites</span></span>

1. <span data-ttu-id="69261-109">Agregue el método de pago de la cuenta del cliente en la sede central de Commerce.</span><span class="sxs-lookup"><span data-stu-id="69261-109">Add the customer account payment method in Commerce headquarters.</span></span>
2. <span data-ttu-id="69261-110">Asocie el método de pago de la cuenta del cliente al canal de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="69261-110">Associate the customer account payment method with the e-commerce channel.</span></span>
3. <span data-ttu-id="69261-111">Asegúrese de que **Permitir a cuenta** está habilitado para el cliente en **Retail y Commerce \> Clientes \> Todos los clientes \> Valores predeterminados de pago** en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="69261-111">Make sure that **Allow on account** is enabled for the customer at **Retail and Commerce \> Customers \> All customers \> Payment defaults** in Commerce headquarters.</span></span> <span data-ttu-id="69261-112">Asegúrese también de que los parámetros **Límite de crédito** se establezcan de forma adecuada para el cliente en **Retail y Commerce \> Clientes \> Todos los clientes \> Crédito y cobros** en la sede central de Commerce.</span><span class="sxs-lookup"><span data-stu-id="69261-112">Also make sure that **Credit limit** parameters are set appropriately for the customer at **Retail and Commerce \> Customers \> All customers \> Credit and Collections** in Commerce headquarters.</span></span> 

## <a name="enable-the-customer-account-payment-method-in-commerce-site-builder"></a><span data-ttu-id="69261-113">Habilitar el método de pago de la cuenta del cliente en el generador de sitios de Commerce</span><span class="sxs-lookup"><span data-stu-id="69261-113">Enable the customer account payment method in Commerce site builder</span></span> 

<span data-ttu-id="69261-114">Para habilitar el método de pago de la cuenta del cliente en el generador de sitios de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="69261-114">To enable the customer account payment method in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="69261-115">Vaya a **Configuración del sitio \> Extensiones**.</span><span class="sxs-lookup"><span data-stu-id="69261-115">Go to **Site Settings \> Extensions**.</span></span>
1. <span data-ttu-id="69261-116">Establezca la propiedad **Habilitar pagos de cuenta de cliente** en **Habilitado para clientes de B2B**.</span><span class="sxs-lookup"><span data-stu-id="69261-116">Set the **Enable customer account payments** property to **Enabled for B2B customers**.</span></span> 
1. <span data-ttu-id="69261-117">Seleccione **Guardar y publicar**.</span><span class="sxs-lookup"><span data-stu-id="69261-117">Select **Save and Publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="69261-118">La nueva configuración de sitio solo surtirá efecto cuando se haya actualizado el archivo app.settings.json.</span><span class="sxs-lookup"><span data-stu-id="69261-118">The new site settings take effect only after the app.settings.json file is updated.</span></span> <span data-ttu-id="69261-119">Para obtener más información, consulte [Actualizaciones del SDK y la biblioteca de módulos](../e-commerce-extensibility/sdk-updates.md).</span><span class="sxs-lookup"><span data-stu-id="69261-119">For more information, see [SDK and Module library updates](../e-commerce-extensibility/sdk-updates.md).</span></span>

## <a name="enable-the-customer-account-payment-method-on-the-checkout-page-for-the-b2b-e-commerce-site"></a><span data-ttu-id="69261-120">Habilite el método de pago de la cuenta del cliente en la página de finalización de compra del sitio de comercio electrónico B2B</span><span class="sxs-lookup"><span data-stu-id="69261-120">Enable the customer account payment method on the checkout page for the B2B e-commerce site</span></span>

<span data-ttu-id="69261-121">Para habilitar el método de pago de la cuenta del cliente en la página de finalización de compra del sitio de comercio electrónico B2B, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="69261-121">To enable the customer account payment method on the checkout page for the B2B e-commerce site, follow these steps.</span></span>

1. <span data-ttu-id="69261-122">En el generador de sitios de Commerce, busque y edite la página de pago o el fragmento que contiene el módulo de pago para el sitio de comercio electrónico B2B.</span><span class="sxs-lookup"><span data-stu-id="69261-122">In Commerce site builder, find and edit the checkout page or fragment that contains the checkout module for the B2B e-commerce site.</span></span>
1. <span data-ttu-id="69261-123">En la entrada **Contenedor de la sección de finalización de compra**, seleccione **Agregar módulo** y, a continuación, agregue un módulo **Pago de cuenta de cliente**.</span><span class="sxs-lookup"><span data-stu-id="69261-123">In the **Checkout section container** slot, select **Add Module**, and then add a **Customer account payment** module.</span></span>
1. <span data-ttu-id="69261-124">Coloque el módulo **Pago de cuenta de cliente** seleccionando los puntos suspensivos (**...**) y seleccionando a continuación **Subir** o **Bajar** según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="69261-124">Position the **Customer account payment** module by selecting the ellipsis (**...**), and then selecting **Move Up** or **Move Down** as required.</span></span>
1. <span data-ttu-id="69261-125">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="69261-125">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="confirm-that-the-customer-account-payment-method-has-been-enabled-and-published"></a><span data-ttu-id="69261-126">Confirmar que el método de pago de la cuenta del cliente se haya habilitado y publicado</span><span class="sxs-lookup"><span data-stu-id="69261-126">Confirm that the customer account payment method has been enabled and published</span></span>

<span data-ttu-id="69261-127">Para confirmar que el método de pago de la cuenta del cliente se ha habilitado y publicado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="69261-127">To confirm that the customer account payment method has been enabled, follow these steps.</span></span>

1. <span data-ttu-id="69261-128">Inicie sesión en el sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="69261-128">Sign in to the e-commerce site.</span></span>
1. <span data-ttu-id="69261-129">Agregue un producto al carro.</span><span class="sxs-lookup"><span data-stu-id="69261-129">Add a product to the cart.</span></span>
1. <span data-ttu-id="69261-130">Vaya a la página de finalización de compra.</span><span class="sxs-lookup"><span data-stu-id="69261-130">Go to the checkout page.</span></span> <span data-ttu-id="69261-131">Verá el nuevo método de pago de **Cuenta de cliente**.</span><span class="sxs-lookup"><span data-stu-id="69261-131">You should see the new **Customer Account** payment method.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="69261-132">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="69261-132">Additional resources</span></span>

[<span data-ttu-id="69261-133">Configurar un sitio de comercio electrónico B2B</span><span class="sxs-lookup"><span data-stu-id="69261-133">Set up a B2B e-commerce site</span></span>](set-up-b2b-site.md)

[<span data-ttu-id="69261-134">Crear jerarquías de modelado de organización para organizaciones B2B</span><span class="sxs-lookup"><span data-stu-id="69261-134">Create org modeling hierarchies for B2B organizations</span></span>](org-model.md)

[<span data-ttu-id="69261-135">Administrar usuarios socios comerciales en sitios de comercio electrónico B2B</span><span class="sxs-lookup"><span data-stu-id="69261-135">Manage business partner users on B2B e-commerce sites</span></span>](manage-b2b-users.md)

[<span data-ttu-id="69261-136">Establecer límites de cantidad de productos para sitios de comercio electrónico B2B</span><span class="sxs-lookup"><span data-stu-id="69261-136">Set product quantity limits for B2B e-commerce sites</span></span>](quantity-limits.md)

[<span data-ttu-id="69261-137">Actualizaciones del SDK y la biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="69261-137">SDK and Module library updates</span></span>](../e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]