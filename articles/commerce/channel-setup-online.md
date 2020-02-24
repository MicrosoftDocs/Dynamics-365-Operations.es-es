---
title: Configurar un canal en línea
description: En este tema se describe cómo crear un nuevo canal en línea en Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
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
ms.openlocfilehash: 9b7a2b8fd157df8b39e9e227d188a3802cacb4e3
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002436"
---
# <a name="set-up-an-online-channel"></a><span data-ttu-id="9d97f-103">Configurar un canal en línea</span><span class="sxs-lookup"><span data-stu-id="9d97f-103">Set up an online channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="9d97f-104">En este tema se describe cómo crear un nuevo canal en línea en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9d97f-104">This topic describes how to create a new online channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9d97f-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="9d97f-105">Overview</span></span>

<span data-ttu-id="9d97f-106">Dynamics 365 Commerce admite varios canales comerciales.</span><span class="sxs-lookup"><span data-stu-id="9d97f-106">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="9d97f-107">Estos canales de venta minorista incluyen tiendas en línea, centros de llamadas y tiendas minoristas (también conocidas como tiendas físicas).</span><span class="sxs-lookup"><span data-stu-id="9d97f-107">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="9d97f-108">Las tiendas en línea proporcionan a los clientes la opción de comprar productos de su tienda en línea además de en sus tiendas físicas.</span><span class="sxs-lookup"><span data-stu-id="9d97f-108">Online stores give customers the option of purchasing products from the retailer's online store in addition to its retail stores.</span></span>

<span data-ttu-id="9d97f-109">Para crear una tienda en línea en Commerce, primero debe crear un canal en línea.</span><span class="sxs-lookup"><span data-stu-id="9d97f-109">To create an online store in Commerce, you must first create an online channel.</span></span> 

<span data-ttu-id="9d97f-110">Antes de crear un nuevo canal en línea, asegúrese de haber completado los [Requisitos previos de configuración de canales](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="9d97f-110">Before you create a new online channel, ensure that you have completed the [Channel set up prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-online-channel"></a><span data-ttu-id="9d97f-111">Crear y configurar un nuevo canal en línea</span><span class="sxs-lookup"><span data-stu-id="9d97f-111">Create and configure a new online channel</span></span>

<span data-ttu-id="9d97f-112">Para crear y configurar un nuevo canal en línea, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9d97f-112">To create and configure a new online channel, follow these steps.</span></span>

1. <span data-ttu-id="9d97f-113">En el panel de navegación, vaya a **Módulos \> Canales \> Tiendas en línea**.</span><span class="sxs-lookup"><span data-stu-id="9d97f-113">In the navigation pane, go to **Modules \> Channels \> Online Stores**.</span></span>
1. <span data-ttu-id="9d97f-114">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="9d97f-114">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="9d97f-115">En el campo **Nombre**, escriba un nombre para el nuevo canal.</span><span class="sxs-lookup"><span data-stu-id="9d97f-115">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="9d97f-116">En la lista desplegable **Entidad jurídica**, introduzca la entidad jurídica correspondiente.</span><span class="sxs-lookup"><span data-stu-id="9d97f-116">In the **Legal entity** drop-down, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="9d97f-117">En la lista desplegable **Almacén**, introduzca el almacén apropiado.</span><span class="sxs-lookup"><span data-stu-id="9d97f-117">In the **Warehouse** drop-down, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="9d97f-118">En el campo **Zona horaria de la tienda**, seleccione la zona horaria apropiada.</span><span class="sxs-lookup"><span data-stu-id="9d97f-118">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="9d97f-119">En el campo **Divisa**, seleccione la divisa apropiada.</span><span class="sxs-lookup"><span data-stu-id="9d97f-119">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="9d97f-120">En el campo **Cliente predeterminado**, especifique un cliente predeterminado válido.</span><span class="sxs-lookup"><span data-stu-id="9d97f-120">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="9d97f-121">En el campo **Libreta de direcciones de cliente**, especifique una libreta de direcciones válida.</span><span class="sxs-lookup"><span data-stu-id="9d97f-121">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="9d97f-122">En el campo **Perfil de funcionalidad**, seleccione un perfil de funcionalidad si corresponde.</span><span class="sxs-lookup"><span data-stu-id="9d97f-122">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="9d97f-123">En el campo **Perfil de notificación por correo electrónico**, proporcione un perfil de notificación de correo electrónico válido.</span><span class="sxs-lookup"><span data-stu-id="9d97f-123">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="9d97f-124">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9d97f-124">On the action pane, select **Save**.</span></span>

<span data-ttu-id="9d97f-125">La siguiente imagen muestra la creación de un nuevo canal en línea.</span><span class="sxs-lookup"><span data-stu-id="9d97f-125">The following image shows the creation of a new online channel.</span></span>

![Nuevo canal en línea](media/channel-setup-online-1.png)

<span data-ttu-id="9d97f-127">La siguiente imagen muestra un ejemplo de canal en línea.</span><span class="sxs-lookup"><span data-stu-id="9d97f-127">The following image shows an example online channel.</span></span>

![Ejemplo de canal en línea](media/channel-setup-online-2.png)

## <a name="set-up-languages"></a><span data-ttu-id="9d97f-129">Configurar idiomas</span><span class="sxs-lookup"><span data-stu-id="9d97f-129">Set up languages</span></span>

<span data-ttu-id="9d97f-130">Si su sitio de comercio electrónico admite varios idiomas, expanda la sección **Idiomas** y agregue idiomas adicionales según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9d97f-130">If your e-Commerce site will support multiple languages, expand the **Languages** section and add additional languages as needed.</span></span>

## <a name="set-up-payment-account"></a><span data-ttu-id="9d97f-131">Configurar una cuenta de pago</span><span class="sxs-lookup"><span data-stu-id="9d97f-131">Set up payment account</span></span>

<span data-ttu-id="9d97f-132">En la sección **Cuenta de pago** puede agregar un proveedor de pagos de terceros.</span><span class="sxs-lookup"><span data-stu-id="9d97f-132">From within the **Payment account** section, you can add a third-party payment provider.</span></span> <span data-ttu-id="9d97f-133">Para obtener información sobre cómo configurar un conector de pagos de Adyen, consulte [Conector de pagos de Dynamics 365 para Adyen](../retail/dev-itpro/adyen-connector.md).</span><span class="sxs-lookup"><span data-stu-id="9d97f-133">For information on settting up an Adyen payment connector, see [Dynamics 365 Payment Connector for Adyen](../retail/dev-itpro/adyen-connector.md).</span></span>

## <a name="additional-channel-set-up"></a><span data-ttu-id="9d97f-134">Configuración adicional de canal</span><span class="sxs-lookup"><span data-stu-id="9d97f-134">Additional channel set up</span></span>

<span data-ttu-id="9d97f-135">Las tareas adicionales requeridas para la configuración del canal en línea incluyen: configuración de métodos de pago, modos de entrega y asignación de grupo de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="9d97f-135">Additional tasks required for online channel setup include setting up payment methods, modes of delivery, and the fulfillment group assignment.</span></span>

<span data-ttu-id="9d97f-136">La siguiente imagen muestra las opciones de configuración **Modos de entrega**, **Métodos de pago** y **Asignación de grupo de cumplimiento** en la pestaña **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="9d97f-136">The following image shows **Modes of delivery**, **Payment methods**, and **Fulfillment group assignment** setup options on the **Set up** tab.</span></span>

![Acciones adicionales de configuración de canales en línea](media/channel-setup-online-3.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="9d97f-138">Configurar métodos de pago</span><span class="sxs-lookup"><span data-stu-id="9d97f-138">Set up payment methods</span></span>

<span data-ttu-id="9d97f-139">Para configurar métodos de pago, siga los pasos siguientes para cada tipo de pago admitido en este canal.</span><span class="sxs-lookup"><span data-stu-id="9d97f-139">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="9d97f-140">En el panel de acciones, seleccione la pestaña **Configurar** y, a continuación, seleccione **Métodos de pago**.</span><span class="sxs-lookup"><span data-stu-id="9d97f-140">On the action pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="9d97f-141">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="9d97f-141">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="9d97f-142">En el panel de navegación, seleccione el método de pago deseado.</span><span class="sxs-lookup"><span data-stu-id="9d97f-142">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="9d97f-143">En la sección **General**, proporcione un **Nombre de la operación** y configure las otras opciones de configuración que desee.</span><span class="sxs-lookup"><span data-stu-id="9d97f-143">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="9d97f-144">Configure opciones de configuración adicionales según sea necesario para el tipo de pago.</span><span class="sxs-lookup"><span data-stu-id="9d97f-144">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="9d97f-145">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9d97f-145">On the action pane, select **Save**.</span></span>

<span data-ttu-id="9d97f-146">En la imagen siguiente se muestra un ejemplo de método de pago en efectivo.</span><span class="sxs-lookup"><span data-stu-id="9d97f-146">The following image shows an example of a cash payment method.</span></span>

![Ejemplo de métodos de pago](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="9d97f-148">Configurar modos de entrega</span><span class="sxs-lookup"><span data-stu-id="9d97f-148">Set up modes of delivery</span></span>

<span data-ttu-id="9d97f-149">Para ver los modos de entrega configurados, seleccione **Modos de entrega** en la pestaña **Configurar** del **Panel de acciones**.</span><span class="sxs-lookup"><span data-stu-id="9d97f-149">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="9d97f-150">Para cambiar o agregar un modo de entrega, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9d97f-150">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="9d97f-151">En el panel de navegación, vaya a **Módulos \> Gestión de inventarios \> Modos de entrega**.</span><span class="sxs-lookup"><span data-stu-id="9d97f-151">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="9d97f-152">En el panel de acciones, seleccione **Nuevo** para crear un nuevo modo de entrega o seleccionar un modo existente.</span><span class="sxs-lookup"><span data-stu-id="9d97f-152">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="9d97f-153">En la sección **Canales comerciales**, seleccione **Agregar línea** para agregar el canal.</span><span class="sxs-lookup"><span data-stu-id="9d97f-153">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="9d97f-154">Agregar canales utilizando nodos de organización en lugar de agregar cada canal individualmente puede simplificar la adición de canales.</span><span class="sxs-lookup"><span data-stu-id="9d97f-154">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="9d97f-155">En la imagen siguiente se muestra un ejemplo de mode de entrega.</span><span class="sxs-lookup"><span data-stu-id="9d97f-155">The following image shows an example of a mode of delivery.</span></span>

![Configurar modos de entrega](media/channel-setup-retail-7.png)

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="9d97f-157">Configurar una asignación de grupo de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="9d97f-157">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="9d97f-158">Para configurar una asignación de grupo de cumplimiento, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9d97f-158">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="9d97f-159">En el panel de acciones, seleccione la pestaña **Configurar** y, a continuación, seleccione **Asignación de grupo de cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="9d97f-159">On the action pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="9d97f-160">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="9d97f-160">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="9d97f-161">En la lista desplegable **Grupo de cumplimiento**, seleccione un grupo de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="9d97f-161">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="9d97f-162">En la lista desplegable **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="9d97f-162">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="9d97f-163">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9d97f-163">On the action pane, select **Save**.</span></span>

<span data-ttu-id="9d97f-164">La siguiente imagen muestra un ejemplo de configuración de asignación de grupo de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="9d97f-164">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Configurar la asignación de grupo de cumplimiento](media/channel-setup-retail-9.png)

## <a name="additional-resources"></a><span data-ttu-id="9d97f-166">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9d97f-166">Additional resources</span></span>

[<span data-ttu-id="9d97f-167">Resumen de canales</span><span class="sxs-lookup"><span data-stu-id="9d97f-167">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="9d97f-168">Requisitos previos de configuración de canales</span><span class="sxs-lookup"><span data-stu-id="9d97f-168">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="9d97f-169">Configurar un canal comercial</span><span class="sxs-lookup"><span data-stu-id="9d97f-169">Set up a retail channel</span></span>](channel-setup-retail.md)

[<span data-ttu-id="9d97f-170">Configurar un canal de centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="9d97f-170">Set up a call center channel</span></span>](channel-setup-callcenter.md)

[<span data-ttu-id="9d97f-171">Conector de pago de Dynamics 365 para Adyen</span><span class="sxs-lookup"><span data-stu-id="9d97f-171">Dynamics 365 Payment Connector for Adyen</span></span>](../retail/dev-itpro/adyen-connector.md)
