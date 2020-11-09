---
title: Configurar un canal en línea
description: En este tema se describe cómo crear un nuevo canal en línea en Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 07225d97af76ea665fa28362cc205c6e8dc4fdf4
ms.sourcegitcommit: 776758a0ff95c3c7398986095104d1d2b9814514
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "4107239"
---
# <a name="set-up-an-online-channel"></a><span data-ttu-id="9a82e-103">Configurar un canal en línea</span><span class="sxs-lookup"><span data-stu-id="9a82e-103">Set up an online channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="9a82e-104">En este tema se describe cómo crear un nuevo canal en línea en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9a82e-104">This topic describes how to create a new online channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9a82e-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="9a82e-105">Overview</span></span>

<span data-ttu-id="9a82e-106">Dynamics 365 Commerce admite varios canales comerciales.</span><span class="sxs-lookup"><span data-stu-id="9a82e-106">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="9a82e-107">Estos canales de venta minorista incluyen tiendas en línea, centros de llamadas y tiendas minoristas (también conocidas como tiendas físicas).</span><span class="sxs-lookup"><span data-stu-id="9a82e-107">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="9a82e-108">Las tiendas en línea proporcionan a los clientes la opción de comprar productos de su tienda en línea además de en sus tiendas físicas.</span><span class="sxs-lookup"><span data-stu-id="9a82e-108">Online stores give customers the option of purchasing products from the retailer's online store in addition to its retail stores.</span></span>

<span data-ttu-id="9a82e-109">Para crear una tienda en línea en Commerce, primero debe crear un canal en línea.</span><span class="sxs-lookup"><span data-stu-id="9a82e-109">To create an online store in Commerce, you must first create an online channel.</span></span> <span data-ttu-id="9a82e-110">Antes de crear un nuevo canal en línea, asegúrese de haber completado los [Requisitos previos de configuración de canales](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="9a82e-110">Before you create a new online channel, ensure that you have completed the [Channel set up prerequisites](channels-prerequisites.md).</span></span>

<span data-ttu-id="9a82e-111">Para poder crear un sitio nuevo, se debe crear al menos una tienda en línea en Commerce.</span><span class="sxs-lookup"><span data-stu-id="9a82e-111">Before you can create a new site, at least one online store must be created in Commerce.</span></span> <span data-ttu-id="9a82e-112">Para más información, consulte [Crear un sitio de comercio electrónico](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="9a82e-112">For more information, see [Create an e-Commerce site](create-ecommerce-site.md).</span></span>

## <a name="create-and-configure-a-new-online-channel"></a><span data-ttu-id="9a82e-113">Crear y configurar un nuevo canal en línea</span><span class="sxs-lookup"><span data-stu-id="9a82e-113">Create and configure a new online channel</span></span>

<span data-ttu-id="9a82e-114">Para crear y configurar un nuevo canal en línea, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9a82e-114">To create and configure a new online channel, follow these steps.</span></span>

1. <span data-ttu-id="9a82e-115">En el panel de navegación, vaya a **Módulos \> Canales \> Tiendas en línea**.</span><span class="sxs-lookup"><span data-stu-id="9a82e-115">In the navigation pane, go to **Modules \> Channels \> Online Stores**.</span></span>
1. <span data-ttu-id="9a82e-116">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="9a82e-116">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="9a82e-117">En el campo **Nombre** , escriba un nombre para el nuevo canal.</span><span class="sxs-lookup"><span data-stu-id="9a82e-117">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="9a82e-118">En la lista desplegable **Entidad jurídica** , introduzca la entidad jurídica correspondiente.</span><span class="sxs-lookup"><span data-stu-id="9a82e-118">In the **Legal entity** drop-down, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="9a82e-119">En la lista desplegable **Almacén** , introduzca el almacén apropiado.</span><span class="sxs-lookup"><span data-stu-id="9a82e-119">In the **Warehouse** drop-down, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="9a82e-120">En el campo **Zona horaria de la tienda** , seleccione la zona horaria apropiada.</span><span class="sxs-lookup"><span data-stu-id="9a82e-120">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="9a82e-121">En el campo **Divisa** , seleccione la divisa apropiada.</span><span class="sxs-lookup"><span data-stu-id="9a82e-121">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="9a82e-122">En el campo **Cliente predeterminado** , especifique un cliente predeterminado válido.</span><span class="sxs-lookup"><span data-stu-id="9a82e-122">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="9a82e-123">En el campo **Libreta de direcciones de cliente** , especifique una libreta de direcciones válida.</span><span class="sxs-lookup"><span data-stu-id="9a82e-123">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="9a82e-124">En el campo **Perfil de funcionalidad** , seleccione un perfil de funcionalidad si corresponde.</span><span class="sxs-lookup"><span data-stu-id="9a82e-124">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="9a82e-125">En el campo **Perfil de notificación por correo electrónico** , proporcione un perfil de notificación de correo electrónico válido.</span><span class="sxs-lookup"><span data-stu-id="9a82e-125">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="9a82e-126">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9a82e-126">On the action pane, select **Save**.</span></span>

<span data-ttu-id="9a82e-127">La siguiente imagen muestra la creación de un nuevo canal en línea.</span><span class="sxs-lookup"><span data-stu-id="9a82e-127">The following image shows the creation of a new online channel.</span></span>

![Nuevo canal en línea](media/channel-setup-online-1.png)

<span data-ttu-id="9a82e-129">La siguiente imagen muestra un ejemplo de canal en línea.</span><span class="sxs-lookup"><span data-stu-id="9a82e-129">The following image shows an example online channel.</span></span>

![Ejemplo de canal en línea](media/channel-setup-online-2.png)

## <a name="set-up-languages"></a><span data-ttu-id="9a82e-131">Configurar idiomas</span><span class="sxs-lookup"><span data-stu-id="9a82e-131">Set up languages</span></span>

<span data-ttu-id="9a82e-132">Si su sitio de comercio electrónico admite varios idiomas, expanda la sección **Idiomas** y agregue idiomas adicionales según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9a82e-132">If your e-Commerce site will support multiple languages, expand the **Languages** section and add additional languages as needed.</span></span>

## <a name="set-up-payment-account"></a><span data-ttu-id="9a82e-133">Configurar una cuenta de pago</span><span class="sxs-lookup"><span data-stu-id="9a82e-133">Set up payment account</span></span>

<span data-ttu-id="9a82e-134">En la sección **Cuenta de pago** puede agregar un proveedor de pagos de terceros.</span><span class="sxs-lookup"><span data-stu-id="9a82e-134">From within the **Payment account** section, you can add a third-party payment provider.</span></span> <span data-ttu-id="9a82e-135">Para obtener información sobre cómo configurar un conector de pagos de Adyen, consulte [Conector de pagos de Dynamics 365 para Adyen](../retail/dev-itpro/adyen-connector.md).</span><span class="sxs-lookup"><span data-stu-id="9a82e-135">For information on setting up an Adyen payment connector, see [Dynamics 365 Payment Connector for Adyen](../retail/dev-itpro/adyen-connector.md).</span></span>

## <a name="additional-channel-setup"></a><span data-ttu-id="9a82e-136">Configuración de canal adicional</span><span class="sxs-lookup"><span data-stu-id="9a82e-136">Additional channel setup</span></span>

<span data-ttu-id="9a82e-137">Las tareas adicionales requeridas para la configuración del canal en línea incluyen: configuración de métodos de pago, modos de entrega y asignación de grupo de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="9a82e-137">Additional tasks that are required for online channel setup include setting up payment methods, modes of delivery, and the fulfillment group assignment.</span></span>

<span data-ttu-id="9a82e-138">La siguiente imagen muestra las opciones de configuración **Modos de entrega** , **Métodos de pago** y **Asignación de grupo de cumplimiento** en la pestaña **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="9a82e-138">The following image shows **Modes of delivery** , **Payment methods** , and **Fulfillment group assignment** setup options on the **Set up** tab.</span></span>

![Acciones adicionales de configuración de canales en línea](media/channel-setup-online-3.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="9a82e-140">Configurar métodos de pago</span><span class="sxs-lookup"><span data-stu-id="9a82e-140">Set up payment methods</span></span>

<span data-ttu-id="9a82e-141">Para configurar métodos de pago, siga los pasos siguientes para cada tipo de pago admitido en este canal.</span><span class="sxs-lookup"><span data-stu-id="9a82e-141">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="9a82e-142">En el panel de acciones, seleccione la pestaña **Configurar** y, a continuación, seleccione **Métodos de pago**.</span><span class="sxs-lookup"><span data-stu-id="9a82e-142">On the action pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="9a82e-143">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="9a82e-143">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="9a82e-144">En el panel de navegación, seleccione el método de pago deseado.</span><span class="sxs-lookup"><span data-stu-id="9a82e-144">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="9a82e-145">En la sección **General** , proporcione un **Nombre de la operación** y configure las otras opciones de configuración que desee.</span><span class="sxs-lookup"><span data-stu-id="9a82e-145">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="9a82e-146">Configure opciones de configuración adicionales según sea necesario para el tipo de pago.</span><span class="sxs-lookup"><span data-stu-id="9a82e-146">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="9a82e-147">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9a82e-147">On the action pane, select **Save**.</span></span>

<span data-ttu-id="9a82e-148">En la imagen siguiente se muestra un ejemplo de método de pago en efectivo.</span><span class="sxs-lookup"><span data-stu-id="9a82e-148">The following image shows an example of a cash payment method.</span></span>

![Ejemplo de métodos de pago](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="9a82e-150">Configurar modos de entrega</span><span class="sxs-lookup"><span data-stu-id="9a82e-150">Set up modes of delivery</span></span>

<span data-ttu-id="9a82e-151">Para ver los modos de entrega configurados, seleccione **Modos de entrega** en la pestaña **Configurar** del **Panel de acciones**.</span><span class="sxs-lookup"><span data-stu-id="9a82e-151">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="9a82e-152">Para cambiar o agregar un modo de entrega, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9a82e-152">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="9a82e-153">En el panel de navegación, vaya a **Módulos \> Gestión de inventarios \> Modos de entrega**.</span><span class="sxs-lookup"><span data-stu-id="9a82e-153">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="9a82e-154">En el panel de acciones, seleccione **Nuevo** para crear un nuevo modo de entrega o seleccionar un modo existente.</span><span class="sxs-lookup"><span data-stu-id="9a82e-154">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="9a82e-155">En la sección **Canales comerciales** , seleccione **Agregar línea** para agregar el canal.</span><span class="sxs-lookup"><span data-stu-id="9a82e-155">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="9a82e-156">Agregar canales utilizando nodos de organización en lugar de agregar cada canal individualmente puede simplificar la adición de canales.</span><span class="sxs-lookup"><span data-stu-id="9a82e-156">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="9a82e-157">En la imagen siguiente se muestra un ejemplo de mode de entrega.</span><span class="sxs-lookup"><span data-stu-id="9a82e-157">The following image shows an example of a mode of delivery.</span></span>

![Configurar modos de entrega](media/channel-setup-retail-7.png)

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="9a82e-159">Configurar una asignación de grupo de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="9a82e-159">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="9a82e-160">Para configurar una asignación de grupo de cumplimiento, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9a82e-160">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="9a82e-161">En el panel de acciones, seleccione la pestaña **Configurar** y, a continuación, seleccione **Asignación de grupo de cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="9a82e-161">On the action pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="9a82e-162">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="9a82e-162">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="9a82e-163">En la lista desplegable **Grupo de cumplimiento** , seleccione un grupo de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="9a82e-163">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="9a82e-164">En la lista desplegable **Descripción** , escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="9a82e-164">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="9a82e-165">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9a82e-165">On the action pane, select **Save**.</span></span>

<span data-ttu-id="9a82e-166">La siguiente imagen muestra un ejemplo de configuración de asignación de grupo de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="9a82e-166">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Configurar la asignación de grupo de cumplimiento](media/channel-setup-retail-9.png)

## <a name="additional-resources"></a><span data-ttu-id="9a82e-168">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9a82e-168">Additional resources</span></span>

[<span data-ttu-id="9a82e-169">Resumen de canales</span><span class="sxs-lookup"><span data-stu-id="9a82e-169">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="9a82e-170">Requisitos previos de configuración de canales</span><span class="sxs-lookup"><span data-stu-id="9a82e-170">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="9a82e-171">Configurar un canal comercial</span><span class="sxs-lookup"><span data-stu-id="9a82e-171">Set up a retail channel</span></span>](channel-setup-retail.md)

[<span data-ttu-id="9a82e-172">Configurar un canal de centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="9a82e-172">Set up a call center channel</span></span>](channel-setup-callcenter.md)

[<span data-ttu-id="9a82e-173">Conector de pago de Dynamics 365 para Adyen</span><span class="sxs-lookup"><span data-stu-id="9a82e-173">Dynamics 365 Payment Connector for Adyen</span></span>](../retail/dev-itpro/adyen-connector.md)
