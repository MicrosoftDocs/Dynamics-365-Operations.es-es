---
title: Visión general de alertas
description: Este tema proporciona información general acerca de alertas. Puede usar alertas para permanecer informado acerca de los eventos de los que desea realizar un seguimiento durante el día laborable.
author: tjvass
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: 12fadd8387054db3e19d4136555724c23548e05c
ms.sourcegitcommit: 4e62c22b53693c201baa646a8f047edb5a0a2747
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2020
ms.locfileid: "3031028"
---
# <a name="alerts-overview"></a><span data-ttu-id="4ba95-104">Información general de alertas</span><span class="sxs-lookup"><span data-stu-id="4ba95-104">Alerts overview</span></span>

[!include [banner](../includes/banner.md)]

## <a name="about-alerts"></a><span data-ttu-id="4ba95-105">Acerca de los avisos</span><span class="sxs-lookup"><span data-stu-id="4ba95-105">About alerts</span></span>
<span data-ttu-id="4ba95-106">Las alertas forman un sistema de notificaciones para eventos críticos en el sistema.</span><span class="sxs-lookup"><span data-stu-id="4ba95-106">Alerts form a notification system for critical events in the system.</span></span> <span data-ttu-id="4ba95-107">Puede usar alertas para permanecer informado acerca de los eventos de los que desea realizar un seguimiento durante el día laborable.</span><span class="sxs-lookup"><span data-stu-id="4ba95-107">You can use alerts to stay informed about events that you want to track during the workday.</span></span> <span data-ttu-id="4ba95-108">Puede crear con facilidad su propio conjunto de reglas de alertas para recibir alertas sobre las entregas vencidas, pedidos eliminados, precios que cambian u otros eventos a los que debe responder.</span><span class="sxs-lookup"><span data-stu-id="4ba95-108">You can easily create your own set of alert rules so that you're alerted about deliveries that are overdue, orders that are deleted, prices that change, or other events that you must respond to.</span></span>

<span data-ttu-id="4ba95-109">En (ERP) la planificación de recursos empresariales, hay varias situaciones habituales donde la función de avisos se puede usar.</span><span class="sxs-lookup"><span data-stu-id="4ba95-109">In enterprise resource planning (ERP), there are several typical scenarios where the alerts feature can be used.</span></span> <span data-ttu-id="4ba95-110">Aquí hay algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="4ba95-110">Here are some examples.</span></span>

### <a name="scenario-1-create-an-alert-rule-for-new-sales-orders"></a><span data-ttu-id="4ba95-111">Escenario 1: crear una regla de alerta para los pedidos de ventas nuevos.</span><span class="sxs-lookup"><span data-stu-id="4ba95-111">Scenario 1: Create an alert rule for new sales orders</span></span>

1. <span data-ttu-id="4ba95-112">Abra la página **Todos los pedidos de venta**.</span><span class="sxs-lookup"><span data-stu-id="4ba95-112">Open the **All sales orders** page.</span></span>
2. <span data-ttu-id="4ba95-113">En el Panel de acciones, en la ficha **Opciones**, en el grupo **Compartir**, seleccione **Crear una alerta personalizada**.</span><span class="sxs-lookup"><span data-stu-id="4ba95-113">On the Action Pane, on the **Options** tab, in the **Share** group, select **Create a custom alert**.</span></span>
3. <span data-ttu-id="4ba95-114">En el cuadro **Crear regla de alertas**, en la ficha desplegable **Avisarme cuando**, en el campo **evento**, seleccione **El registro se ha creado**.</span><span class="sxs-lookup"><span data-stu-id="4ba95-114">In the **Create alert rule** dialog box, on the **Alert me when** FastTab, in the **Event** field, select **Record has been created**.</span></span>

### <a name="scenario-2-create-an-alert-rule-for-postponement-of-a-delivery-date"></a><span data-ttu-id="4ba95-115">Escenario 2: crear una regla de alerta para posponer una fecha de entrega</span><span class="sxs-lookup"><span data-stu-id="4ba95-115">Scenario 2: Create an alert rule for postponement of a delivery date</span></span>

1. <span data-ttu-id="4ba95-116">Abra la página **Todos los pedidos de compra**.</span><span class="sxs-lookup"><span data-stu-id="4ba95-116">Open the **All purchase orders** page.</span></span>
2. <span data-ttu-id="4ba95-117">Seleccione un identificador del pedido de compra para acceder a los detalles del pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="4ba95-117">Select a purchase order ID to access the purchase order details.</span></span>
3. <span data-ttu-id="4ba95-118">Expanda la ficha desplegable **Encabezado de pedido de compras**.</span><span class="sxs-lookup"><span data-stu-id="4ba95-118">Expand the **Purchase order header** FastTab.</span></span>
4. <span data-ttu-id="4ba95-119">En el Panel de acciones, en la ficha **Opciones**, en el grupo **Compartir**, seleccione **Crear una alerta personalizada**.</span><span class="sxs-lookup"><span data-stu-id="4ba95-119">On the Action Pane, on the **Options** tab, in the **Share** group, select **Create a custom alert**.</span></span>
5. <span data-ttu-id="4ba95-120">En el cuadro **Crear regla de alertas**, en la ficha desplegable **Avisarme cuando**, en el campo **Campo**, seleccione **Fecha de entrega**.</span><span class="sxs-lookup"><span data-stu-id="4ba95-120">In the **Create alert rule** dialog box, on the **Alert me when** FastTab, in the **Field** field, select **Delivery date**.</span></span>
6. <span data-ttu-id="4ba95-121">En el campo **evento**, seleccione **se ha aplazado**.</span><span class="sxs-lookup"><span data-stu-id="4ba95-121">In the **Event** field, select **has been postponed**.</span></span>
    
<span data-ttu-id="4ba95-122">Después de cerrar el cuadro de diálogo **Crear regla de alertas**, la regla aparece en la página **Administrar reglas de alertas**.</span><span class="sxs-lookup"><span data-stu-id="4ba95-122">After you close the **Create alert rule** dialog box, your rule appears on the **Manage alert rules** page.</span></span> <span data-ttu-id="4ba95-123">Puede usar la página **Administrar reglas de alertas** para actualizar sus reglas de alertas existentes.</span><span class="sxs-lookup"><span data-stu-id="4ba95-123">You can use the **Manage alert rules** page to update your existing alert rules.</span></span> <span data-ttu-id="4ba95-124">Por ejemplo, puede modificar los desencadenadores de eventos, actualizar notificaciones de eventos y actualizar las fechas de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="4ba95-124">For example, you can modify event triggers, update event notifications, and update expiration dates.</span></span> <span data-ttu-id="4ba95-125">Para abrir la página **Administrar reglas de alertas** , use el botón **Avisarme** en la pestaña **Opciones** del panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="4ba95-125">To open the **Manage alert rules** page, use the **Alert me** button on the **Options** tab of the Action Pane.</span></span>

## <a name="what-occurs-when-an-alert-rule-is-created"></a><span data-ttu-id="4ba95-126">¿Qué sucede cuando se crea una regla de alertas?</span><span class="sxs-lookup"><span data-stu-id="4ba95-126">What occurs when an alert rule is created?</span></span>

<span data-ttu-id="4ba95-127">Cuando crea reglas de alertas, puede asociar un evento predefinido a un campo específico.</span><span class="sxs-lookup"><span data-stu-id="4ba95-127">When you create alert rules, you can associate a predefined event with a specific field.</span></span> <span data-ttu-id="4ba95-128">Por ejemplo, cuando llega la fecha que se especifica en el campo o cuando cambia el contenido del campo.</span><span class="sxs-lookup"><span data-stu-id="4ba95-128">For example, the date that is specified in the field arrives, or the contents of the field change.</span></span> <span data-ttu-id="4ba95-129">Como alternativa, puede asociar un evento a los registros en una página específica.</span><span class="sxs-lookup"><span data-stu-id="4ba95-129">Alternatively, you can associate an event with the records on a specific page.</span></span> <span data-ttu-id="4ba95-130">Por ejemplo, se crea un registro o se elimina un registro.</span><span class="sxs-lookup"><span data-stu-id="4ba95-130">For example, a record is created, or a record is deleted.</span></span>

<span data-ttu-id="4ba95-131">Cuando se produce el evento seleccionado para el campo, o para un registro de la página, se le envía una alerta.</span><span class="sxs-lookup"><span data-stu-id="4ba95-131">When the selected event occurs for the field or for a record on the page, an alert is sent to you.</span></span> <span data-ttu-id="4ba95-132">Por ejemplo, crea una regla en la que asocia el campo **Fecha de entrega** a una línea de pedido de compras específica con el evento **ha vencido hace tiempo**.</span><span class="sxs-lookup"><span data-stu-id="4ba95-132">For example, you create a rule where you associate the **Delivery date** field on a specific purchase order line with the **was due this amount of time ago** event.</span></span> <span data-ttu-id="4ba95-133">Establece el período de tiempo en cinco días.</span><span class="sxs-lookup"><span data-stu-id="4ba95-133">You set the time frame to five days.</span></span> <span data-ttu-id="4ba95-134">En este caso se envía una alerta cinco días después de la fecha de entrega de dicha línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="4ba95-134">In this case, an alert is sent five days after the delivery date of that purchase order line.</span></span>

<span data-ttu-id="4ba95-135">Además, puede limitar las reglas de alertas estableciendo condiciones.</span><span class="sxs-lookup"><span data-stu-id="4ba95-135">Additionally, you can refine alert rules by setting conditions.</span></span> <span data-ttu-id="4ba95-136">Por ejemplo, puede recibir una alerta acerca de los nuevos pedidos de compra que se crean para las cuentas de proveedor específicas.</span><span class="sxs-lookup"><span data-stu-id="4ba95-136">For example, you can be alerted about new purchase orders that are created for specific vendor accounts.</span></span>

## <a name="preparing-for-an-alert"></a><span data-ttu-id="4ba95-137">Preparación para una alerta</span><span class="sxs-lookup"><span data-stu-id="4ba95-137">Preparing for an alert</span></span>

<span data-ttu-id="4ba95-138">Antes de configurar una regla de alerta, decida cuándo o en qué situaciones desea recibir las alertas.</span><span class="sxs-lookup"><span data-stu-id="4ba95-138">Before you set up an alert rule, decide when or in what situations you want to receive alerts.</span></span> <span data-ttu-id="4ba95-139">Cuando sepa acerca de qué evento desea que se le avise, encuentre la página en donde aparecen los datos que provocan la aparición del evento.</span><span class="sxs-lookup"><span data-stu-id="4ba95-139">When you know which event you want to be notified about, find the page where the data that causes that event appears.</span></span> <span data-ttu-id="4ba95-140">El evento puede ser una fecha que llega o un cambio específico que se produce.</span><span class="sxs-lookup"><span data-stu-id="4ba95-140">The event can be a date that arrives or a specific change that occurs.</span></span> <span data-ttu-id="4ba95-141">Por tanto, debe buscar la página donde se especifica la fecha o donde se muestra el campo que cambia o el registro nuevo.</span><span class="sxs-lookup"><span data-stu-id="4ba95-141">Therefore, you must find the page where the date is specified, or where the field that changes or the new record that is created appears.</span></span> <span data-ttu-id="4ba95-142">Cuando tenga esta información, puede crear la regla de alerta.</span><span class="sxs-lookup"><span data-stu-id="4ba95-142">After you have this information, you can create the alert rule.</span></span>

## <a name="components-of-an-alert-rule"></a><span data-ttu-id="4ba95-143">Componentes de una regla de alertas</span><span class="sxs-lookup"><span data-stu-id="4ba95-143">Components of an alert rule</span></span>

<span data-ttu-id="4ba95-144">Una regla de alertas tiene cinco componentes:</span><span class="sxs-lookup"><span data-stu-id="4ba95-144">An alert rule has five components:</span></span>

- <span data-ttu-id="4ba95-145">**Evento**: El evento que desencadena una regla de alertas puede ser una fecha que llega o un cambio específico que se produce.</span><span class="sxs-lookup"><span data-stu-id="4ba95-145">**Event** – The event that triggers an alert rule can be a date that arrives or a specific change that occurs.</span></span> <span data-ttu-id="4ba95-146">Defina eventos en la ficha desplegable **Enviar alertas de correo electrónico para los cambios de estado de los trabajos** del cuadro **Crear regla de alertas**.</span><span class="sxs-lookup"><span data-stu-id="4ba95-146">You define events on the **Send email alerts for job status changes** FastTab of the **Create alert rule** dialog box.</span></span>
- <span data-ttu-id="4ba95-147">**Condición** En la ficha desplegable **Avisar para** del cuadro de diálogo **Crear regla de alertas**, puede seleccionar el ámbito de la condición, para controlar cuándo desea que se le avise sobre eventos.</span><span class="sxs-lookup"><span data-stu-id="4ba95-147">**Condition** – On the **Alert me for** FastTab of the **Create alert rule** dialog box, you can select the scope of the condition, to control when you're alerted about events.</span></span> <span data-ttu-id="4ba95-148">Puede aplicar la regla al registro actual solamente o a todos los registros visibles de la página.</span><span class="sxs-lookup"><span data-stu-id="4ba95-148">You can apply the rule either to the current record only or to all visible records on the page.</span></span> <span data-ttu-id="4ba95-149">Si la regla se aplica a todas las entidades jurídicas, puede establecer la opción **En toda la organización** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="4ba95-149">If the rule applies across legal entities, you can set the **Organization-wide** option to **Yes**.</span></span>
- <span data-ttu-id="4ba95-150">**Vencimiento de la regla** En la ficha desplegable **Avisar hasta** del cuadro de diálogo **Crear regla de alertas**, puede especificar el tiempo que la regla de alerta debe estar activa.</span><span class="sxs-lookup"><span data-stu-id="4ba95-150">**Expiry of rule** – On the **Alert me until** FastTab of the **Create alert rule** dialog box, you can specify how long the alert rule should be active.</span></span>
- <span data-ttu-id="4ba95-151">**Contenido** En la ficha desplegable **Avisar con** del cuadro de diálogo **Crear regla de alertas**, puede especificar el texto del asunto y del mensaje que deben usar las alertas.</span><span class="sxs-lookup"><span data-stu-id="4ba95-151">**Contents** – On the **Alert me with** FastTab of the **Create alert rule** dialog box, you can specify the subject text and message text that the alert messages should use.</span></span>
- <span data-ttu-id="4ba95-152">**Usuario** En la ficha desplegable **Avisar a** del cuadro de diálogo **Crear regla de alertas**, puede especificar qué usuario debe recibir los mensajes de alerta.</span><span class="sxs-lookup"><span data-stu-id="4ba95-152">**User** – On the **Alert who** FastTab of the **Create alert rule** dialog box, you can specify which user should receive the alert messages.</span></span> <span data-ttu-id="4ba95-153">De forma predeterminada, se selecciona el id. de usuario.</span><span class="sxs-lookup"><span data-stu-id="4ba95-153">By default, your user ID is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4ba95-154">Esta opción se limita a los administradores de la organización.</span><span class="sxs-lookup"><span data-stu-id="4ba95-154">This option is restricted to organization administrators.</span></span>

## <a name="email-notifications-from-alerts"></a><span data-ttu-id="4ba95-155">Notificaciones por correo electrónico de alertas</span><span class="sxs-lookup"><span data-stu-id="4ba95-155">Email notifications from alerts</span></span>

<span data-ttu-id="4ba95-156">Las notificaciones por correo electrónico de alertas aún no están habilitadas.</span><span class="sxs-lookup"><span data-stu-id="4ba95-156">Email notifications from alerts are not yet enabled.</span></span> <span data-ttu-id="4ba95-157">Esto se habilitará en una actualización futura.</span><span class="sxs-lookup"><span data-stu-id="4ba95-157">This will be enabled in a future update.</span></span>

## <a name="videos"></a><span data-ttu-id="4ba95-158">Vídeos</span><span class="sxs-lookup"><span data-stu-id="4ba95-158">Videos</span></span>

### <a name="how-to-use-alerts-to-monitor-filtered-data"></a><span data-ttu-id="4ba95-159">Cómo utilizar Alertas para controlar datos filtrados</span><span class="sxs-lookup"><span data-stu-id="4ba95-159">How to use alerts to monitor filtered data</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3DWZ3]

<span data-ttu-id="4ba95-160">El vídeo [Cómo utilizar Alertas para controlar datos filtrados](https://youtu.be/ZYKMcv6kl9s) (ver arriba) se incluye en la [Lista de reproducción de Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible en YouTube.</span><span class="sxs-lookup"><span data-stu-id="4ba95-160">The [How to use alerts to monitor filtered data](https://youtu.be/ZYKMcv6kl9s) video (shown above) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

### <a name="alert-rule-options"></a><span data-ttu-id="4ba95-161">Opciones de reglas de alertas</span><span class="sxs-lookup"><span data-stu-id="4ba95-161">Alert rule options</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3E4PV]

<span data-ttu-id="4ba95-162">El vídeo [Opciones de reglas de alertas](https://youtu.be/cpzimwOjicM) (aparece más arriba) está incluido en la [Lista de reproducción de Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible en YouTube.</span><span class="sxs-lookup"><span data-stu-id="4ba95-162">The [Alert rule options](https://youtu.be/cpzimwOjicM) video (shown above) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>


