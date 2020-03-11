---
title: Configurar un canal de centro de llamadas
description: En este tema se describe cómo crear un nuevo canal de centro de llamadas en Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 42448bd54c00b8642b158f422e17d2b46ee25579
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057888"
---
# <a name="set-up-a-call-center-channel"></a><span data-ttu-id="adff6-103">Configurar un canal de centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="adff6-103">Set up a call center channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="adff6-104">En este tema se describe cómo crear un nuevo canal de centro de llamadas en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="adff6-104">This topic describes how to create a new call center channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="adff6-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="adff6-105">Overview</span></span>

<span data-ttu-id="adff6-106">En Dynamics 365 Commerce, un centro de llamadas es un tipo de canal que se puede definir en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="adff6-106">In Dynamics 365 Commerce, a call center is a type of channel that can be defined in the application.</span></span> <span data-ttu-id="adff6-107">La definición de un canal para las entidades de su centro de llamadas permite que el sistema vincule datos específicos y valores predeterminados de procesamiento de pedidos a los pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="adff6-107">Defining a channel for your call center entities allows the system to tie specific data and order processing defaults to sales orders.</span></span> <span data-ttu-id="adff6-108">Una empresa puede definir varios canales de centro de llamadas en Commerce.</span><span class="sxs-lookup"><span data-stu-id="adff6-108">A company can define multiple call center channels in Commerce.</span></span> 

<span data-ttu-id="adff6-109">Antes de crear un nuevo canal de centro de llamadas, asegúrese de haber completado los [Requisitos previos de configuración de canales](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="adff6-109">Before you create a new call center channel, ensure that you have completed the [Channel set up prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-call-center-channel"></a><span data-ttu-id="adff6-110">Crear y configurar un nuevo canal de centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="adff6-110">Create and configure a new call center channel</span></span>

<span data-ttu-id="adff6-111">Para crear y configurar un nuevo centro de llamadas, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="adff6-111">To create and configure a new call center channel, follow these steps.</span></span>

1. <span data-ttu-id="adff6-112">En el panel de navegación, vaya a **Módulos \> Canales \> Centros de llamadas \> Todos los centros de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="adff6-112">In the navigation pane, go to **Modules \> Channels \> Call centers \> All call centers**.</span></span>
1. <span data-ttu-id="adff6-113">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="adff6-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="adff6-114">En el campo **Nombre**, escriba un nombre para el nuevo canal.</span><span class="sxs-lookup"><span data-stu-id="adff6-114">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="adff6-115">Seleccione la **Entidad jurídica** apropiada en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="adff6-115">Select the appropriate **Legal entity** from the drop down.</span></span>
1. <span data-ttu-id="adff6-116">Seleccione la ubicación de **Almacén** apropiada en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="adff6-116">Select the appropriate **Warehouse** location from the drop down.</span></span>
1. <span data-ttu-id="adff6-117">En el campo **Cliente predeterminado**, especifique un cliente predeterminado válido.</span><span class="sxs-lookup"><span data-stu-id="adff6-117">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="adff6-118">En el campo **Perfil de notificación por correo electrónico**, proporcione un perfil de notificación de correo electrónico válido.</span><span class="sxs-lookup"><span data-stu-id="adff6-118">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="adff6-119">Proporcione un código de información de **Anulación del precio**.</span><span class="sxs-lookup"><span data-stu-id="adff6-119">Provide a **Price override** info code.</span></span> <span data-ttu-id="adff6-120">Tenga en cuenta que puede que tenga que crear antes un código de información para esto.</span><span class="sxs-lookup"><span data-stu-id="adff6-120">Note you may need to create an info code for this first.</span></span>
1. <span data-ttu-id="adff6-121">Proporcionar un código de información de **Código de retención**.</span><span class="sxs-lookup"><span data-stu-id="adff6-121">Provide a **Hold code** info code.</span></span> <span data-ttu-id="adff6-122">Tenga en cuenta que puede que tenga que crear antes un código de información para esto.</span><span class="sxs-lookup"><span data-stu-id="adff6-122">Note you may need to create an info code for this first.</span></span>
1. <span data-ttu-id="adff6-123">Proporcione un código de información de **Crédito**.</span><span class="sxs-lookup"><span data-stu-id="adff6-123">Provide a **Credit** info code.</span></span> <span data-ttu-id="adff6-124">Tenga en cuenta que puede que tenga que crear antes un código de información para esto.</span><span class="sxs-lookup"><span data-stu-id="adff6-124">Note you may need to create an info code for this first.</span></span>
1. <span data-ttu-id="adff6-125">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="adff6-125">Select **Save**.</span></span>

<span data-ttu-id="adff6-126">La siguiente imagen muestra la creación de un nuevo canal de centro de llamadas.</span><span class="sxs-lookup"><span data-stu-id="adff6-126">The following image shows the creation of a new call center channel.</span></span>

![Nuevo canal de centro de llamadas](media/channel-setup-callcenter-1.png)

<span data-ttu-id="adff6-128">La siguiente imagen muestra un ejemplo de canal de centro de llamadas.</span><span class="sxs-lookup"><span data-stu-id="adff6-128">The following image shows an example call center channel.</span></span>

![Ejemplo de canal de centro de llamadas](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a><span data-ttu-id="adff6-130">Configuración de canal adicional</span><span class="sxs-lookup"><span data-stu-id="adff6-130">Additional channel setup</span></span>

<span data-ttu-id="adff6-131">Las tareas adicionales requeridas para la configuración del canal de centro de llamadas incluyen: configuración de métodos de pago y modos de entrega.</span><span class="sxs-lookup"><span data-stu-id="adff6-131">Additional tasks required for call center channel setup include setting up payment methods and modes of delivery.</span></span>

<span data-ttu-id="adff6-132">La siguiente imagen muestra las opciones de configuración de **Modos de entrega** y **Métodos de pago** en la pestaña **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="adff6-132">The following image shows **Modes of delivery** and **Payment methods** set up options on the **Set up** tab.</span></span>

![Acciones adicionales de configuración de canales de centro de llamadas](media/channel-setup-callcenter-3.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="adff6-134">Configurar métodos de pago</span><span class="sxs-lookup"><span data-stu-id="adff6-134">Set up payment methods</span></span>

<span data-ttu-id="adff6-135">Para configurar métodos de pago, siga los pasos siguientes para cada tipo de pago admitido en este canal.</span><span class="sxs-lookup"><span data-stu-id="adff6-135">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="adff6-136">En el panel de acciones, seleccione la pestaña **Configurar** y, a continuación, seleccione **Métodos de pago**.</span><span class="sxs-lookup"><span data-stu-id="adff6-136">On the action pane, select the **Set up** tab, and then select **Payment methods**.</span></span>
1. <span data-ttu-id="adff6-137">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="adff6-137">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="adff6-138">En el panel de navegación, seleccione el método de pago deseado.</span><span class="sxs-lookup"><span data-stu-id="adff6-138">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="adff6-139">En la sección **General**, proporcione un **Nombre de la operación** y configure las otras opciones de configuración que desee.</span><span class="sxs-lookup"><span data-stu-id="adff6-139">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="adff6-140">Configure opciones de configuración adicionales según sea necesario para el tipo de pago.</span><span class="sxs-lookup"><span data-stu-id="adff6-140">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="adff6-141">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="adff6-141">On the action pane, select **Save**.</span></span>

<span data-ttu-id="adff6-142">En la imagen siguiente se muestra un ejemplo de método de pago en efectivo.</span><span class="sxs-lookup"><span data-stu-id="adff6-142">The following image shows an example of a cash payment method.</span></span>

![Ejemplo de métodos de pago](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="adff6-144">Configurar modos de entrega</span><span class="sxs-lookup"><span data-stu-id="adff6-144">Set up modes of delivery</span></span>

<span data-ttu-id="adff6-145">Para ver los modos de entrega configurados, seleccione **Modos de entrega** en la pestaña **Configurar** del **Panel de acciones**.</span><span class="sxs-lookup"><span data-stu-id="adff6-145">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="adff6-146">Para cambiar o agregar un modo de entrega, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="adff6-146">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="adff6-147">En el panel de navegación, vaya a **Módulos \> Gestión de inventarios \> Modos de entrega**.</span><span class="sxs-lookup"><span data-stu-id="adff6-147">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="adff6-148">En el panel de acciones, seleccione **Nuevo** para crear un nuevo modo de entrega o seleccionar un modo existente.</span><span class="sxs-lookup"><span data-stu-id="adff6-148">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="adff6-149">En la sección **Canales comerciales**, seleccione **Agregar línea** para agregar el canal.</span><span class="sxs-lookup"><span data-stu-id="adff6-149">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="adff6-150">Agregar canales utilizando nodos de organización en lugar de agregar cada canal individualmente puede simplificar la adición de canales.</span><span class="sxs-lookup"><span data-stu-id="adff6-150">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="adff6-151">En la imagen siguiente se muestra un ejemplo de mode de entrega.</span><span class="sxs-lookup"><span data-stu-id="adff6-151">The following image shows an example of a mode of delivery.</span></span>

![Configurar modos de entrega](media/channel-setup-retail-7.png)

## <a name="additional-resources"></a><span data-ttu-id="adff6-153">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="adff6-153">Additional resources</span></span>

[<span data-ttu-id="adff6-154">Requisitos previos de configuración de canales</span><span class="sxs-lookup"><span data-stu-id="adff6-154">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="adff6-155">Funcionalidad de ventas del centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="adff6-155">Call center sales functionality</span></span>](call-center-functionality.md)

[<span data-ttu-id="adff6-156">Configurar opciones de procesamiento de pedidos de centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="adff6-156">Set up call center order processing options</span></span>](set-up-order-processing-options.md)

[<span data-ttu-id="adff6-157">Catálogos del centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="adff6-157">Call center catalogs</span></span>](call-center-catalogs.md)

[<span data-ttu-id="adff6-158">Configurar y trabajar con alertas de fraude</span><span class="sxs-lookup"><span data-stu-id="adff6-158">Set up and work with fraud alerts</span></span>](set-up-fraud-alerts.md)

[<span data-ttu-id="adff6-159">Configurar programas de continuidad para centros de llamadas</span><span class="sxs-lookup"><span data-stu-id="adff6-159">Set up continuity programs for call centers</span></span>](set-up-continuity-program.md)
