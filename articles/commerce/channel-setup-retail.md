---
title: Configurar un canal comercial
description: En este tema se describe cómo crear un nuevo canal comercial en Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 100822ecea03d03267f98654c66e74f2f5924bd9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4997734"
---
# <a name="set-up-a-retail-channel"></a><span data-ttu-id="8852f-103">Configurar un canal comercial</span><span class="sxs-lookup"><span data-stu-id="8852f-103">Set up a retail channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="8852f-104">En este tema se describe cómo crear un nuevo canal comercial en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8852f-104">This topic describes how to create a new retail channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="8852f-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="8852f-105">Overview</span></span>

<span data-ttu-id="8852f-106">Dynamics 365 Commerce admite varios canales comerciales.</span><span class="sxs-lookup"><span data-stu-id="8852f-106">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="8852f-107">Estos canales de venta minorista incluyen tiendas en línea, centros de llamadas y tiendas minoristas (también conocidas como tiendas físicas).</span><span class="sxs-lookup"><span data-stu-id="8852f-107">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="8852f-108">Cada canal de tienda puede tener sus propios métodos de pago, grupos de precios, registros de puntos de venta (PDV), cuentas de ingresos y gastos, o personal.</span><span class="sxs-lookup"><span data-stu-id="8852f-108">Each retail store channel can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="8852f-109">Debe configurar todos estos elementos antes de crear una canal de tienda.</span><span class="sxs-lookup"><span data-stu-id="8852f-109">You must set up all of these elements before you can create a retail store channel.</span></span> 

<span data-ttu-id="8852f-110">Antes de crear un canal comercial, asegúrese de cumplir los [requisitos previos del canal](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="8852f-110">Before a retail channel is created, ensure you follow the [channel prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-retail-channel"></a><span data-ttu-id="8852f-111">Crear y configurar un nuevo canal comercial</span><span class="sxs-lookup"><span data-stu-id="8852f-111">Create and configure a new retail channel</span></span>

1. <span data-ttu-id="8852f-112">En el panel de navegación, vaya a **Módulos \> Canales \> Tiendas \> Todas las tiendas**.</span><span class="sxs-lookup"><span data-stu-id="8852f-112">In the navigation pane, go to **Modules \> Channels \> Stores \> All stores**.</span></span>
1. <span data-ttu-id="8852f-113">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="8852f-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="8852f-114">En el campo **Nombre**, escriba un nombre para el nuevo canal.</span><span class="sxs-lookup"><span data-stu-id="8852f-114">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="8852f-115">En el campo **Número de tienda**, especifique un número de tienda único.</span><span class="sxs-lookup"><span data-stu-id="8852f-115">In the **Store number** field, provide a unique store number.</span></span> <span data-ttu-id="8852f-116">El número puede ser alfanumérico, con un máximo de 10 caracteres.</span><span class="sxs-lookup"><span data-stu-id="8852f-116">The number can be alphanumeric with a maximum of 10 characters.</span></span>
1. <span data-ttu-id="8852f-117">En la lista desplegable **Entidad jurídica**, introduzca la entidad jurídica correspondiente.</span><span class="sxs-lookup"><span data-stu-id="8852f-117">In the **Legal entity** drop-down list, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="8852f-118">En la lista desplegable **Almacén**, introduzca el almacén apropiado.</span><span class="sxs-lookup"><span data-stu-id="8852f-118">In the **Warehouse** drop-down list, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="8852f-119">En el campo **Zona horaria de la tienda**, seleccione la zona horaria apropiada.</span><span class="sxs-lookup"><span data-stu-id="8852f-119">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="8852f-120">En la lista desplegable **Grupo de impuestos sobre las ventas**, seleccione un grupo de impuestos sobre las ventas apropiado para la tienda.</span><span class="sxs-lookup"><span data-stu-id="8852f-120">In the **Sales tax group** drop-down list, select an appropriate sales tax group for the store.</span></span>
1. <span data-ttu-id="8852f-121">En el campo **Divisa**, seleccione la divisa apropiada.</span><span class="sxs-lookup"><span data-stu-id="8852f-121">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="8852f-122">En el campo **Libreta de direcciones de cliente**, especifique una libreta de direcciones válida.</span><span class="sxs-lookup"><span data-stu-id="8852f-122">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="8852f-123">En el campo **Cliente predeterminado**, especifique un cliente predeterminado válido.</span><span class="sxs-lookup"><span data-stu-id="8852f-123">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="8852f-124">En el campo **Perfil de funcionalidad**, seleccione un perfil de funcionalidad si corresponde.</span><span class="sxs-lookup"><span data-stu-id="8852f-124">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="8852f-125">En el campo **Perfil de notificación por correo electrónico**, proporcione un perfil de notificación de correo electrónico válido.</span><span class="sxs-lookup"><span data-stu-id="8852f-125">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="8852f-126">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8852f-126">On the action pane, select **Save**.</span></span>

<span data-ttu-id="8852f-127">La siguiente imagen muestra la creación de un nuevo canal comercial.</span><span class="sxs-lookup"><span data-stu-id="8852f-127">The following image shows the creation of a new retail channel.</span></span>

![Nuevo canal de comercial](media/channel-setup-retail-1.png)

<span data-ttu-id="8852f-129">La siguiente imagen muestra un canal comercial de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8852f-129">The following image shows an example retail channel.</span></span>

![Ejemplo de canal comercial](media/channel-setup-retail-2.png)

## <a name="other-settings"></a><span data-ttu-id="8852f-131">Otras opciones de configuración</span><span class="sxs-lookup"><span data-stu-id="8852f-131">Other settings</span></span>

<span data-ttu-id="8852f-132">Hay muchas otras configuraciones opcionales que se pueden configurar en las secciones **Extracto/cierre** y **Varios**, en función de las necesidades de la tienda.</span><span class="sxs-lookup"><span data-stu-id="8852f-132">There are numerous other optional settings that can be set in the **Statement/closing** and **Miscellaneous** sections, based on the needs of the retail store.</span></span>

<span data-ttu-id="8852f-133">Consulte también [Diseños de pantalla para el punto de venta (PDV)](pos-screen-layouts.md) para obtener información sobre cómo configurar el diseño de pantalla predeterminado en la sección **Diseño de pantalla** y [Instalar y configurar Retail Hardware Station](retail-hardware-station-configuration-installation.md) para obtener información de configuración sobre la sección **Estaciones de hardware**.</span><span class="sxs-lookup"><span data-stu-id="8852f-133">In addition, see [Screen layouts for the point of sale (POS)](pos-screen-layouts.md) for information on setting up the default screen layout in the **Screen layout** section and [Configure and install Retail hardware station](retail-hardware-station-configuration-installation.md) for setup information about the **Hardware stations** section.</span></span>

<span data-ttu-id="8852f-134">En la siguiente imagen se muestra un ejemplo de configuración de instalación de canal comercial.</span><span class="sxs-lookup"><span data-stu-id="8852f-134">The following image shows an example retail channel setup configuration.</span></span>

![Ejemplo de configuración de canal comercial](media/channel-setup-retail-3.png)

## <a name="additional-channel-set-up"></a><span data-ttu-id="8852f-136">Configuración adicional de canal</span><span class="sxs-lookup"><span data-stu-id="8852f-136">Additional channel set up</span></span>

<span data-ttu-id="8852f-137">Hay elementos adicionales que debe configurar para un canal que se pueden encontrar en el **Panel de acciones** bajo la sección **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="8852f-137">There are additional items that need to be set up for a channel that can be found on the **Action pane** under the **Set up** section.</span></span>

<span data-ttu-id="8852f-138">Las tareas adicionales requeridas para la configuración del canal en línea incluyen: configuración de métodos de pago, declaración de efectivo, modos de entrega, cuenta de ingresos/gastos, secciones, asignación de grupo de cumplimiento y cajas fuertes.</span><span class="sxs-lookup"><span data-stu-id="8852f-138">Additional tasks required for online channel setup include setting up payment methods, cash declaration, modes of delivery, income/expense account, sections, the fulfillment group assignment, and safes.</span></span>

<span data-ttu-id="8852f-139">En la imagen siguiente se muestran varias opciones adicionales de configuración de canales comerciales en la pestaña **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="8852f-139">The following image shows various additional retail channel setup options on the **Set up** tab.</span></span>

![Configurar canal](media/channel-setup-retail-4.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="8852f-141">Configurar métodos de pago</span><span class="sxs-lookup"><span data-stu-id="8852f-141">Set up payment methods</span></span>

<span data-ttu-id="8852f-142">Para configurar métodos de pago, siga los pasos siguientes para cada tipo de pago admitido en este canal.</span><span class="sxs-lookup"><span data-stu-id="8852f-142">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="8852f-143">En el panel de acciones, seleccione la pestaña **Configurar** y, a continuación, seleccione **Métodos de pago**.</span><span class="sxs-lookup"><span data-stu-id="8852f-143">On the action pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="8852f-144">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="8852f-144">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="8852f-145">En el panel de navegación, seleccione el método de pago deseado.</span><span class="sxs-lookup"><span data-stu-id="8852f-145">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="8852f-146">En la sección **General**, proporcione un **Nombre de la operación** y configure las otras opciones de configuración que desee.</span><span class="sxs-lookup"><span data-stu-id="8852f-146">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="8852f-147">Configure opciones de configuración adicionales según sea necesario para el tipo de pago.</span><span class="sxs-lookup"><span data-stu-id="8852f-147">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="8852f-148">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8852f-148">On the action pane, select **Save**.</span></span>

<span data-ttu-id="8852f-149">En la imagen siguiente se muestra un ejemplo de método de pago en efectivo.</span><span class="sxs-lookup"><span data-stu-id="8852f-149">The following image shows an example of a cash payment method.</span></span>

![Ejemplo de métodos de pago](media/channel-setup-retail-5.png)

### <a name="set-up-cash-declaration"></a><span data-ttu-id="8852f-151">Configurar declaración de efectivo</span><span class="sxs-lookup"><span data-stu-id="8852f-151">Set up cash declaration</span></span>

1. <span data-ttu-id="8852f-152">En el panel de acciones, seleccione la pestaña **Configurar** y, a continuación, seleccione **Declaración de efectivo**.</span><span class="sxs-lookup"><span data-stu-id="8852f-152">On the action pane, select the **Set Up** tab, and then select **Cash declaration**.</span></span>
1. <span data-ttu-id="8852f-153">En el panel de acciones, seleccione **Nuevo** y, a continuación, cree todas las denominaciones de **Moneda** y **Nota** que sean aplicables.</span><span class="sxs-lookup"><span data-stu-id="8852f-153">On the action pane, select **New**, and then create all **Coin** and **Note** denominations that are applicable.</span></span>

<span data-ttu-id="8852f-154">En la imagen siguiente se muestra un ejemplo de declaración de efectivo.</span><span class="sxs-lookup"><span data-stu-id="8852f-154">The following image shows an example of a cash declaration.</span></span>

![Configurar declaraciones de efectivo](media/channel-setup-retail-6.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="8852f-156">Configurar modos de entrega</span><span class="sxs-lookup"><span data-stu-id="8852f-156">Set up modes of delivery</span></span>

<span data-ttu-id="8852f-157">Para ver los modos de entrega configurados, seleccione **Modos de entrega** en la pestaña **Configurar** del **Panel de acciones**.</span><span class="sxs-lookup"><span data-stu-id="8852f-157">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="8852f-158">Para cambiar o agregar un modo de entrega, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8852f-158">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="8852f-159">En el panel de navegación, vaya a **Módulos \> Gestión de inventarios \> Modos de entrega**.</span><span class="sxs-lookup"><span data-stu-id="8852f-159">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="8852f-160">En el panel de acciones, seleccione **Nuevo** para crear un nuevo modo de entrega o seleccionar un modo existente.</span><span class="sxs-lookup"><span data-stu-id="8852f-160">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="8852f-161">En la sección **Canales comerciales**, seleccione **Agregar línea** para agregar el canal.</span><span class="sxs-lookup"><span data-stu-id="8852f-161">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="8852f-162">Agregar canales utilizando nodos de organización en lugar de agregar cada canal individualmente puede simplificar la adición de canales.</span><span class="sxs-lookup"><span data-stu-id="8852f-162">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="8852f-163">En la imagen siguiente se muestra un ejemplo de mode de entrega.</span><span class="sxs-lookup"><span data-stu-id="8852f-163">The following image shows an example of a mode of delivery.</span></span>

![Configurar modos de entrega](media/channel-setup-retail-7.png)

### <a name="set-up-incomeexpense-account"></a><span data-ttu-id="8852f-165">Configurar una cuenta de ingresos y gastos</span><span class="sxs-lookup"><span data-stu-id="8852f-165">Set up income/expense account</span></span>

<span data-ttu-id="8852f-166">Para configurar una cuenta de ingresos y gastos siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8852f-166">To set up income/expense account, follow these steps.</span></span>

1. <span data-ttu-id="8852f-167">En el panel de acciones, seleccione la pestaña **Configurar** y, a continuación, seleccione **Cuenta de ingresos y gastos**.</span><span class="sxs-lookup"><span data-stu-id="8852f-167">On the action pane, select the **Set Up** tab, and then select **Income/Expense account**.</span></span>
1. <span data-ttu-id="8852f-168">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="8852f-168">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="8852f-169">En **Nombre**, escriba un nombre.</span><span class="sxs-lookup"><span data-stu-id="8852f-169">Under **Name**, enter a name.</span></span>
1. <span data-ttu-id="8852f-170">En **Nombre de búsqueda**, escriba un nombre de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8852f-170">Under **Search name**, enter a search name.</span></span>
1. <span data-ttu-id="8852f-171">En **Tipo de cuenta**, especifique el tipo de cuenta.</span><span class="sxs-lookup"><span data-stu-id="8852f-171">Under **Account type**, enter the account type.</span></span>
1. <span data-ttu-id="8852f-172">Introduzca texto para **Línea de mensaje 1**, **Línea de mensaje 2**, **Texto de resguardo 1** y **Texto de resguardo 2** según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="8852f-172">Enter text for **Message line 1**, **Message line 2**, **Slip text 1**, and **Slip text 2** as needed.</span></span>
1. <span data-ttu-id="8852f-173">En **Registro**, introduzca la información de registro.</span><span class="sxs-lookup"><span data-stu-id="8852f-173">Under **Posting**, enter posting information.</span></span>
1. <span data-ttu-id="8852f-174">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8852f-174">On the action pane, select **Save**.</span></span>

<span data-ttu-id="8852f-175">La siguiente imagen muestra un ejemplo de cuenta de ingresos/gastos.</span><span class="sxs-lookup"><span data-stu-id="8852f-175">The following image shows an example of an income/expense account.</span></span>

![Configurar una cuenta de ingresos/gastos](media/channel-setup-retail-8.png)

### <a name="set-up-sections"></a><span data-ttu-id="8852f-177">Configurar secciones</span><span class="sxs-lookup"><span data-stu-id="8852f-177">Set up sections</span></span>

<span data-ttu-id="8852f-178">para configurar secciones, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8852f-178">To set up sections, follow these steps.</span></span>

1. <span data-ttu-id="8852f-179">En el panel de acciones, seleccione la pestaña **Configurar** y, a continuación, seleccione **Secciones**.</span><span class="sxs-lookup"><span data-stu-id="8852f-179">On the action pane, select the **Set Up** tab and click **Sections**.</span></span>
1. <span data-ttu-id="8852f-180">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="8852f-180">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="8852f-181">En **Numero de sección**, introduzca un número de sección.</span><span class="sxs-lookup"><span data-stu-id="8852f-181">Under **Section number**, enter a section number.</span></span>
1. <span data-ttu-id="8852f-182">En **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="8852f-182">Under **Description**, enter a description.</span></span>
1. <span data-ttu-id="8852f-183">En **Tamaño de sección**, introduzca un tamaño de sección.</span><span class="sxs-lookup"><span data-stu-id="8852f-183">Under **Section size**, enter a section size.</span></span>
1. <span data-ttu-id="8852f-184">Establezca opciones de configuración adicionales para **General** y **Estadísticas de ventas** según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="8852f-184">Configure additional settings for **General** and **Sales statistics** as needed.</span></span>
1. <span data-ttu-id="8852f-185">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8852f-185">On the action pane, select **Save**.</span></span>

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="8852f-186">Configurar una asignación de grupo de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="8852f-186">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="8852f-187">Para configurar una asignación de grupo de cumplimiento, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8852f-187">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="8852f-188">En el panel de acciones, seleccione la pestaña **Configurar** y, a continuación, seleccione **Asignación de grupo de cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="8852f-188">On the action pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="8852f-189">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="8852f-189">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="8852f-190">En la lista desplegable **Grupo de cumplimiento**, seleccione un grupo de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="8852f-190">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="8852f-191">En la lista desplegable **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="8852f-191">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="8852f-192">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8852f-192">On the action pane, select **Save**</span></span>

<span data-ttu-id="8852f-193">La siguiente imagen muestra un ejemplo de configuración de asignación de grupo de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="8852f-193">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Configurar asignaciones de grupo de cumplimiento](media/channel-setup-retail-9.png)

### <a name="set-up-safes"></a><span data-ttu-id="8852f-195">Configurar cajas fuertes</span><span class="sxs-lookup"><span data-stu-id="8852f-195">Set up safes</span></span>

<span data-ttu-id="8852f-196">para configurar cajas fuertes, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8852f-196">To set up safes, follow these steps.</span></span>

1. <span data-ttu-id="8852f-197">En el panel de acciones, seleccione la pestaña **Configurar** y, a continuación, seleccione **Cajas fuertes**.</span><span class="sxs-lookup"><span data-stu-id="8852f-197">On the action pane, select the **Set Up** tab and click **Safes**.</span></span>
1. <span data-ttu-id="8852f-198">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="8852f-198">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="8852f-199">Introduzca un nombre para la caja fuerte.</span><span class="sxs-lookup"><span data-stu-id="8852f-199">Enter a name for the safe.</span></span>
1. <span data-ttu-id="8852f-200">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8852f-200">On the action pane, select **Save**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8852f-201">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="8852f-201">Additional resources</span></span>

[<span data-ttu-id="8852f-202">Resumen de canales</span><span class="sxs-lookup"><span data-stu-id="8852f-202">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="8852f-203">Requisitos previos de configuración de canales</span><span class="sxs-lookup"><span data-stu-id="8852f-203">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="8852f-204">Configurar un canal en línea</span><span class="sxs-lookup"><span data-stu-id="8852f-204">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="8852f-205">Configurar un canal de centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="8852f-205">Set up a call center channel</span></span>](channel-setup-callcenter.md)

