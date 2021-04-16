---
title: Notificaciones de ejecución de oleadas
description: Este tema describe la ejecución de notificaciones de oleada y explica cómo configurarlas.
author: mirzaab
ms.date: 04/03/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WhsWaveNotificationPolicy, WHSParameters, WHSWaveTemplateTable, BusinessEventsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2022-04-01
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 0a61aff10234f40f14d603852be30fec3ba83647
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838091"
---
# <a name="wave-execution-notifications"></a><span data-ttu-id="6f2e3-103">Notificaciones de ejecución de oleadas</span><span class="sxs-lookup"><span data-stu-id="6f2e3-103">Wave execution notifications</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="6f2e3-104">La función *Notificaciones de ejecución de olas* utiliza eventos comerciales y el Centro de actividades para enviar notificaciones relacionadas con la ejecución de la oleada.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-104">The *Wave execution notifications* feature uses business events and the Action center to deliver notifications that are related to wave execution.</span></span> <span data-ttu-id="6f2e3-105">Le permite especificar los tipos de eventos que generan notificaciones, los almacenes que las generan y los usuarios que las reciben.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-105">It lets you specify the types of events that generate notifications, the warehouses that generate them, and the users who receive them.</span></span>

<span data-ttu-id="6f2e3-106">El botón **Mostrar mensajes** (símbolo de campana) en el lado derecho de la barra de navegación indica cuando un mensaje del Centro de actividades está disponible para el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-106">The **Show messages** button (bell symbol) on the right side of the navigation bar indicates when an Action center message is available for the current user.</span></span> <span data-ttu-id="6f2e3-107">El usuario puede seleccionar el botón **Mostrar mensajes** para abrir el Centro de actividades y revisar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-107">The user can select the **Show messages** button to open the Action center and review the messages.</span></span>

<span data-ttu-id="6f2e3-108">Los eventos comerciales ocurren cuando se ejecutan procesos comerciales.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-108">Business events occur when business processes are run.</span></span> <span data-ttu-id="6f2e3-109">Los procesos comerciales se componen de tareas.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-109">Business processes are made up of tasks.</span></span> <span data-ttu-id="6f2e3-110">Durante un proceso empresarial, los usuarios que participan en él realizan acciones empresariales para completar esas tareas.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-110">During a business process, the users who participate in it perform business actions to complete those tasks.</span></span> <span data-ttu-id="6f2e3-111">Los eventos empresariales proporcionan un mecanismo que permite que los sistemas externos reciban notificaciones de aplicaciones Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-111">Business events provide a mechanism that lets external systems receive notifications from Finance and Operations applications.</span></span> <span data-ttu-id="6f2e3-112">De esta manera, los sistemas pueden realizar acciones comerciales en respuesta a los eventos de negocio.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-112">In this way, the systems can perform business actions in response to the business events.</span></span> <span data-ttu-id="6f2e3-113">Para obtener más información, consulte [Resumen de eventos de negocio](../../fin-ops-core/dev-itpro/business-events/home-page.md).</span><span class="sxs-lookup"><span data-stu-id="6f2e3-113">For more information, see [Business events overview](../../fin-ops-core/dev-itpro/business-events/home-page.md).</span></span>

## <a name="turn-on-the-wave-execution-notifications-feature"></a><span data-ttu-id="6f2e3-114">Activar la característica Notificaciones de ejecución de oleada</span><span class="sxs-lookup"><span data-stu-id="6f2e3-114">Turn on the Wave execution notifications feature</span></span>

<span data-ttu-id="6f2e3-115">Antes de poder usar la característica *Notificaciones de ejecución de oleada*, esta debe estar activada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-115">Before you can use the *Wave execution notifications* feature, it must be turned on in your system.</span></span> <span data-ttu-id="6f2e3-116">Los administradores pueden usar el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-116">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="6f2e3-117">Allí, la característica se enumera de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6f2e3-117">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="6f2e3-118">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="6f2e3-118">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="6f2e3-119">**Nombre de característica:** *Notificaciones de ejecución de oleada*</span><span class="sxs-lookup"><span data-stu-id="6f2e3-119">**Feature name:** *Wave execution notifications*</span></span>

## <a name="scenario-send-wave-batch-execution-notifications-to-the-action-center"></a><span data-ttu-id="6f2e3-120">Escenario: enviar notificaciones de ejecución por lotes de oleadas al centro de actividades</span><span class="sxs-lookup"><span data-stu-id="6f2e3-120">Scenario: Send wave batch execution notifications to the Action center</span></span>

<span data-ttu-id="6f2e3-121">Este escenario muestra el flujo de un extremo a otro para enviar notificaciones sobre errores de ejecución de lotes de oleadas a un rol específico a través del Centro de actividades.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-121">This scenario shows the end-to-end flow for sending notifications about wave batch execution errors to a specific role via the Action center.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="6f2e3-122">Hacer que los datos de demostración estén disponibles</span><span class="sxs-lookup"><span data-stu-id="6f2e3-122">Make demo data available</span></span>

<span data-ttu-id="6f2e3-123">Para seguir este escenario, los datos de demostración deben estar instalados y debe seleccionar la entidad jurídica **USMF**.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-123">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-waves-are-run-in-batch-mode"></a><span data-ttu-id="6f2e3-124">Asegúrese de que las oleadas se ejecuten en modo por lotes</span><span class="sxs-lookup"><span data-stu-id="6f2e3-124">Make sure that waves are run in batch mode</span></span>

1. <span data-ttu-id="6f2e3-125">Vaya a **Gestión de almacenes \> Configuración \> Parámetros de gestión de almacenes**.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-125">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="6f2e3-126">En la ficha desplegable **Procesar oleadas**, establezca la opción **Procesamiento por lotes** en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-126">On the **Wave processing** FastTab, set the **Process waves in batch** option to *Yes*.</span></span>

> [!NOTE]
> <span data-ttu-id="6f2e3-127">Si desea deshabilitar las notificaciones de ejecución por lotes de oleadas, configure la opción **Deshabilitar las notificaciones por lotes de procesamiento de oleadas** a *Sí*.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-127">If you want to disable wave batch execution notifications, set the **Disable wave processing batch notifications** option to *Yes*.</span></span>

### <a name="configure-a-wave-notification-policy"></a><span data-ttu-id="6f2e3-128">Configurar una directiva de notificación de oleadas</span><span class="sxs-lookup"><span data-stu-id="6f2e3-128">Configure a wave notification policy</span></span>

<span data-ttu-id="6f2e3-129">Las políticas de notificación de oleada definen los tipos de notificaciones que se envían y los usuarios a los que se notifica.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-129">Wave notification policies define the types of notifications that are sent and the users who are notified.</span></span>

1. <span data-ttu-id="6f2e3-130">Vaya a **Gestión de almacenes \> Configuración \> Oleadas \> Directivas de notificación de oleadas**.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-130">Go to **Warehouse management \> Setup \> Waves \> Wave notification policies**.</span></span>
1. <span data-ttu-id="6f2e3-131">Cree un registro que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="6f2e3-131">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="6f2e3-132">**Directiva de notificación de oleada:** *24BatchError*</span><span class="sxs-lookup"><span data-stu-id="6f2e3-132">**Wave notification policy:** *24BatchError*</span></span>
    - <span data-ttu-id="6f2e3-133">**Descripción:** *Error de lote de oleadas del almacén 24*</span><span class="sxs-lookup"><span data-stu-id="6f2e3-133">**Description:** *Warehouse 24 wave batch error*</span></span>
    - <span data-ttu-id="6f2e3-134">**Enviar notificación en:** *Solo error*</span><span class="sxs-lookup"><span data-stu-id="6f2e3-134">**Send notification on:** *Error only*</span></span>
    - <span data-ttu-id="6f2e3-135">**Al rol:** *Administrador del sistema*</span><span class="sxs-lookup"><span data-stu-id="6f2e3-135">**To role:** *System administrator*</span></span>

        > [!NOTE]
        > <span data-ttu-id="6f2e3-136">Dado que este escenario utiliza datos de demostración, el rol *Administrador de sistema* se selecciona en aras de la simplicidad.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-136">Because this scenario uses demo data, the *System administrator* role is selected for the sake of simplicity.</span></span> <span data-ttu-id="6f2e3-137">Por lo tanto, debido a que ha iniciado sesión como usuario administrador del sistema, recibirá las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-137">Therefore, because you're signed in as a system administrator user, you will receive the notifications.</span></span> <span data-ttu-id="6f2e3-138">Sin embargo, en la práctica, generalmente debe seleccionar un rol más específico para notificar acerca de los errores de ejecución de lotes de oleadas, como *Jefe de almacén*.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-138">However, in practice, you should usually select a more specific role to notify about wave batch execution errors, such as *Warehouse manager*.</span></span>

1. <span data-ttu-id="6f2e3-139">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-139">On the Action Pane, select **Save**.</span></span>

### <a name="configure-a-wave-template"></a><span data-ttu-id="6f2e3-140">Configurar una plantilla de oleada</span><span class="sxs-lookup"><span data-stu-id="6f2e3-140">Configure a wave template</span></span>

<span data-ttu-id="6f2e3-141">Las plantillas de oleada le permiten vincular instancias específicas de métodos de oleada a unas plantillas de etiqueta de oleada correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-141">Wave templates let you link specific instances of wave methods to corresponding wave label templates.</span></span>

1. <span data-ttu-id="6f2e3-142">Vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-142">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="6f2e3-143">En el panel de lista, configure el campo **Tipo de plantilla de oleada** a *Transporte* y luego seleccione la plantilla de oleada *24 Envío predeterminado* para el almacén 24.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-143">In the list pane, set the **Wave template type** field to *Shipping*, and then select the *24 Shipping Default* wave template for warehouse 24.</span></span>
1. <span data-ttu-id="6f2e3-144">En la ficha desplegable **General**, establezca el campo **Directiva de notificación de oleada** en *24BatchError*.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-144">On the **General** FastTab, set the **Wave notification policy** field to *24BatchError*.</span></span>

### <a name="configure-a-work-template"></a><span data-ttu-id="6f2e3-145">Configurar una plantilla de trabajo</span><span class="sxs-lookup"><span data-stu-id="6f2e3-145">Configure a work template</span></span>

<span data-ttu-id="6f2e3-146">Las plantillas de trabajo se utilizan durante la ejecución de la oleada para generar trabajo.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-146">Work templates are used during wave execution to generate work.</span></span> <span data-ttu-id="6f2e3-147">Para este escenario, la ejecución de la oleada debería provocar un error.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-147">For this scenario, wave execution should trigger an error.</span></span> <span data-ttu-id="6f2e3-148">Al configurar la consulta de la plantilla de trabajo para usar un almacén inexistente, se asegurará de que la ejecución de la oleada falle y, por lo tanto, envíe una notificación.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-148">By setting the work template query to use a nonexistent warehouse, you will ensure that wave execution fails and therefore sends a notification.</span></span>

1. <span data-ttu-id="6f2e3-149">Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-149">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="6f2e3-150">En el panel de lista, configure el campo **Tipo de plantilla de trabajo** a *Pedidos de ventas* y luego seleccione la plantilla de oleada *24 Fase SO* para el almacén 24.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-150">In the list pane, set the **Work template type** field to *Sales orders* and then select the *24 SO Stage* work template for warehouse 24.</span></span>
1. <span data-ttu-id="6f2e3-151">En el panel Acciones, seleccione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-151">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="6f2e3-152">En el cuadro de diálogo del editor de consultas, en la pestaña **Rango** pestaña, edite la siguiente fila (o agréguela si no existe):</span><span class="sxs-lookup"><span data-stu-id="6f2e3-152">In the query editor dialog box, on the **Range** tab, edit the following row (or add it if it doesn't exist):</span></span>

    - <span data-ttu-id="6f2e3-153">**Tabla:** *Transacciones laborales temporales*</span><span class="sxs-lookup"><span data-stu-id="6f2e3-153">**Table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="6f2e3-154">**Tabla derivada:** *Transacciones laborales temporales*</span><span class="sxs-lookup"><span data-stu-id="6f2e3-154">**Derived table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="6f2e3-155">**Campo:** *Almacén*</span><span class="sxs-lookup"><span data-stu-id="6f2e3-155">**Field:** *Warehouse*</span></span>
    - <span data-ttu-id="6f2e3-156">**Criterios:** cambiar el valor de *24* a *Error*.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-156">**Criteria:** Change the value from *24* to *Error*.</span></span>

1. <span data-ttu-id="6f2e3-157">Seleccione **Aceptar** y confirme los cambios.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-157">Select **OK**, and confirm the change.</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="6f2e3-158">Crear un pedido de ventas y liberarlo en el almacén</span><span class="sxs-lookup"><span data-stu-id="6f2e3-158">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="6f2e3-159">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-159">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="6f2e3-160">Cree un pedido de ventas con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="6f2e3-160">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="6f2e3-161">**Cuenta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="6f2e3-161">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="6f2e3-162">**Almacén**: *24*</span><span class="sxs-lookup"><span data-stu-id="6f2e3-162">**Warehouse:** *24*</span></span>

1. <span data-ttu-id="6f2e3-163">En la ficha desplegable **Líneas de pedido de venta**, agregue una línea de pedido de ventas que tenga los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="6f2e3-163">On the **Sales order lines** FastTab, add a sales order line that has the following settings:</span></span>

    - <span data-ttu-id="6f2e3-164">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="6f2e3-164">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="6f2e3-165">**Cantidad:** *10*</span><span class="sxs-lookup"><span data-stu-id="6f2e3-165">**Quantity:** *10*</span></span>

    > [!NOTE]
    > <span data-ttu-id="6f2e3-166">Estos artículos y cantidades son solo ejemplos.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-166">These items and quantities are only examples.</span></span> <span data-ttu-id="6f2e3-167">El almacén especificado debe tener existencias suficientes.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-167">The specified warehouse must contain enough stock.</span></span>

1. <span data-ttu-id="6f2e3-168">Con la nueva línea seleccionada en la ficha desplegable **Líneas de pedido de ventas**, seleccione **Inventario \> Reserva** en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-168">While the new line is still selected on the **Sales order lines** FastTab, select **Inventory \> Reservation** on the toolbar.</span></span>
1. <span data-ttu-id="6f2e3-169">En la página **Reserva**, en el Panel de acciones, seleccione **Reservar lote**.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-169">On the **Reservation** page, on the Action Pane, select **Reserve lot**.</span></span> <span data-ttu-id="6f2e3-170">A continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-170">Then close the page.</span></span>
1. <span data-ttu-id="6f2e3-171">En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-171">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

### <a name="notifications-from-wave-batch-job-execution"></a><span data-ttu-id="6f2e3-172">Notificaciones de la ejecución de trabajos por lotes de oleadas</span><span class="sxs-lookup"><span data-stu-id="6f2e3-172">Notifications from wave batch job execution</span></span>

<span data-ttu-id="6f2e3-173">Dependiendo de la configuración de sus eventos de negocio, eventualmente recibirá una notificación sobre el fallo de ejecución de la oleada.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-173">Depending on the setup of your business events, you will eventually receive a notification about wave execution failure.</span></span> <span data-ttu-id="6f2e3-174">El mensaje del Centro de actividades se parecerá al siguiente ejemplo e incluirá un enlace a la oleada que falló.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-174">The Action center message will resemble the following example and will include a link to the wave that failed.</span></span>

> <span data-ttu-id="6f2e3-175">**Error durante la ejecución de la oleada**</span><span class="sxs-lookup"><span data-stu-id="6f2e3-175">**Error during wave execution**</span></span>  
> <span data-ttu-id="6f2e3-176">Se produjo un error al ejecutar la oleada USMF-000000001.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-176">An error occurred while executing wave USMF-000000001.</span></span>  
> <span data-ttu-id="6f2e3-177">Últimos mensajes: No se creó ningún trabajo para Oleada USMF-000000001.</span><span class="sxs-lookup"><span data-stu-id="6f2e3-177">Last messages: No Work was created for Wave USMF-000000001.</span></span>
>
> <span data-ttu-id="6f2e3-178">**ESTADO**</span><span class="sxs-lookup"><span data-stu-id="6f2e3-178">**STATUS**</span></span>  
> <span data-ttu-id="6f2e3-179">Activa</span><span class="sxs-lookup"><span data-stu-id="6f2e3-179">Active</span></span>
>
> <span data-ttu-id="6f2e3-180">Abrir detalles de la oleada</span><span class="sxs-lookup"><span data-stu-id="6f2e3-180">Open wave details</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
