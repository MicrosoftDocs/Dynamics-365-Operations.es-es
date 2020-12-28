---
title: Eventos de la aplicación de almacén
description: Este tema describe el procesamiento de eventos de la aplicación de almacén que se usa para procesar mensajes de eventos de la aplicación de almacén como parte de un trabajo por lotes.
author: perlynne
manager: tfehr
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileDeviceQueueEvent
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 210008c4a1366773f465c59b38eca30f11f0b38c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436714"
---
# <a name="warehouse-app-event-processing"></a><span data-ttu-id="63925-103">Procesamiento de eventos de la aplicación de almacén</span><span class="sxs-lookup"><span data-stu-id="63925-103">Warehouse app event processing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="63925-104">Los trabajos por lotes que se ejecutan en Supply Chain Management pueden usar datos de una cola para procesar eventos emitidos por la aplicación del almacén para reaccionar según sea necesario a los eventos señalados.</span><span class="sxs-lookup"><span data-stu-id="63925-104">Batch jobs running in Supply Chain Management can use data from a queue for processing events issued by the warehouse app to react as needed to the signaled events.</span></span> <span data-ttu-id="63925-105">Esta función agrega eventos relevantes a la cola en respuesta a ciertos tipos de acciones realizadas por los trabajadores que usan la aplicación.</span><span class="sxs-lookup"><span data-stu-id="63925-105">This feature add relevant events to the queue in response to certain types of actions taken by workers using the app.</span></span> <span data-ttu-id="63925-106">Un ejemplo es cuando se usa la característica **Crear y procesar pedidos de transferencia desde la aplicación de almacén**, el encabezado y las líneas de la orden de transferencia se crean y actualizan en el back-end cuando el sistema está ejecutando el trabajo por lotes **Procesar eventos de aplicaciones de almacén**.</span><span class="sxs-lookup"><span data-stu-id="63925-106">An example is when using the **Create and process transfer orders from the warehouse app** feature, the transfer order header and lines get created and updated in the back end when the system is running the **Process warehouse app events** batch job.</span></span>

## <a name="enable-the-process-warehouse-app-events-feature"></a><span data-ttu-id="63925-107">Habilitar la función Procesar eventos de aplicación de almacén</span><span class="sxs-lookup"><span data-stu-id="63925-107">Enable the Process warehouse app events feature</span></span>

<span data-ttu-id="63925-108">Antes de poder usar esta característica, debe estar habilitada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="63925-108">Before you can use this feature, it must be enabled on your system.</span></span> <span data-ttu-id="63925-109">Los administradores pueden usar la página [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y habilitarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="63925-109">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) page to check the feature status and enable it if needed.</span></span> <span data-ttu-id="63925-110">La característica Procesar eventos de aplicación de almacén se muestra como:</span><span class="sxs-lookup"><span data-stu-id="63925-110">The Process warehouse app events feature is listed as:</span></span>

- <span data-ttu-id="63925-111">**Módulo**: gestión de almacén</span><span class="sxs-lookup"><span data-stu-id="63925-111">**Module** - Warehouse management</span></span>
- <span data-ttu-id="63925-112">**Nombre de característica** - Procesar eventos de aplicación de almacén</span><span class="sxs-lookup"><span data-stu-id="63925-112">**Feature name** - Process warehouse app events</span></span>

## <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a><span data-ttu-id="63925-113">Configurar un trabajo por lotes para procesar eventos de aplicaciones de almacén</span><span class="sxs-lookup"><span data-stu-id="63925-113">Set up a batch job to process warehouse app events</span></span>

### <a name="process-warehouse-app-events"></a><span data-ttu-id="63925-114">Procesar eventos de la aplicación de almacén</span><span class="sxs-lookup"><span data-stu-id="63925-114">Process warehouse app events</span></span>

<span data-ttu-id="63925-115">Configure un trabajo por lotes programado para procesar los eventos de la aplicación del almacén para la creación de la orden de transferencia y las actualizaciones de línea.</span><span class="sxs-lookup"><span data-stu-id="63925-115">Set up a scheduled batch job to process the warehouse app events for the transfer order creation and line updates.</span></span>

1. <span data-ttu-id="63925-116">Vaya a **Gestión de almacenes \> Tareas periódicas \> Procesar eventos de aplicación de almacén**.</span><span class="sxs-lookup"><span data-stu-id="63925-116">Go to **Warehouse management \> Periodic tasks \> Process warehouse app events**.</span></span>
1. <span data-ttu-id="63925-117">Se abre el cuadro de diálogo Eventos de la aplicación Process warehouse.</span><span class="sxs-lookup"><span data-stu-id="63925-117">The Process warehouse app events dialog box opens.</span></span> <span data-ttu-id="63925-118">Expanda la ficha desplegable **Ejecutar en segundo plano** y establezca **Procesamiento por lotes** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="63925-118">Expand the **Run in background** FastTab and set **Batch processing** to **Yes**.</span></span>
1. <span data-ttu-id="63925-119">En la ficha desplegable **Ejecutar en segundo plano**, seleccione **Periodicidad**.</span><span class="sxs-lookup"><span data-stu-id="63925-119">On the **Run in the background** FastTab, select **Recurrence**.</span></span>
1. <span data-ttu-id="63925-120">Se abre el cuadro de diálogo **Definir recurrencia**.</span><span class="sxs-lookup"><span data-stu-id="63925-120">The **Define recurrence** dialog box opens.</span></span> <span data-ttu-id="63925-121">Establezca el programa de ejecución según sea necesario para su empresa.</span><span class="sxs-lookup"><span data-stu-id="63925-121">Set the run schedule as needed for your business.</span></span>
1. <span data-ttu-id="63925-122">Seleccione **Aceptar** para volver al cuadro de diálogo **Procesar eventos de aplicaciones de almacén**.</span><span class="sxs-lookup"><span data-stu-id="63925-122">Select **OK** to return to the **Process warehouse app events** dialog box.</span></span>
1. <span data-ttu-id="63925-123">Seleccione **Aceptar** en el cuadro de diálogo **Procesar eventos de aplicación de almacén** para agregar el trabajo por lotes a la cola de trabajos por lotes.</span><span class="sxs-lookup"><span data-stu-id="63925-123">Select **OK** in the **Process warehouse app events** dialog box to add the batch job to the batch queue.</span></span>

## <a name="query-warehouse-app-events"></a><span data-ttu-id="63925-124">Eventos de la aplicación de almacén de consultas</span><span class="sxs-lookup"><span data-stu-id="63925-124">Query warehouse app events</span></span>

<span data-ttu-id="63925-125">Puede ver la cola de eventos y los mensajes de eventos generados por la aplicación del almacén yendo a **Gestión de almacenes \> Consultas e informes \> Registros de dispositivos móviles \> Eventos de la aplicación de almacén**.</span><span class="sxs-lookup"><span data-stu-id="63925-125">You can view the event queue and events messages generated by the warehouse app by going to **Warehouse management \> Inquiries and reports \> Mobile device logs \> Warehouse app events**.</span></span>

## <a name="the-standard-event-queue-process"></a><span data-ttu-id="63925-126">El proceso de cola de eventos estándar</span><span class="sxs-lookup"><span data-stu-id="63925-126">The standard event queue process</span></span>

<span data-ttu-id="63925-127">La cola de eventos de aplicaciones de almacén se utilizará normalmente con el siguiente flujo descrito:</span><span class="sxs-lookup"><span data-stu-id="63925-127">The warehouse apps events queue will typically be used with the following described flow:</span></span>

1. <span data-ttu-id="63925-128">Un evento se agrega a la cola con un mensaje de evento.</span><span class="sxs-lookup"><span data-stu-id="63925-128">An event gets added to the queue  with an event message.</span></span> <span data-ttu-id="63925-129">El nuevo mensaje tiene inicialmente un estado de evento de **Esperando**, lo que significa que el trabajo por lotes **Procesar eventos de aplicaciones de almacén** no recogerá ni procesará este mensaje.</span><span class="sxs-lookup"><span data-stu-id="63925-129">The new message initially has an Event state of **Waiting**, which means that the **Process warehouse app events** batch job will not pick up and process this message.</span></span>
1. <span data-ttu-id="63925-130">Tan pronto como el estado del mensaje se actualice a **Puesto en cola**, el trabajo por lotes de eventos **Aplicación de almacén de procesos** recogerá y procesará el evento.</span><span class="sxs-lookup"><span data-stu-id="63925-130">As soon as the message state is updated to **Queued**, the **Process warehouse app** events batch job will pick up and process the event.</span></span>
1. <span data-ttu-id="63925-131">El trabajo por lotes actualiza los estados del evento a **Terminado** o **Error**, dependiendo de si el proceso solicitado fue posible.</span><span class="sxs-lookup"><span data-stu-id="63925-131">The batch job updates the event states to either **Completed** or **Failed**, depending on whether the requested process was possible.</span></span>
1. <span data-ttu-id="63925-132">Cuando todos los mensajes de eventos relacionados están **completados**, el evento se elimina de la cola.</span><span class="sxs-lookup"><span data-stu-id="63925-132">When all the related event messages are **Completed**, the event is deleted from the queue.</span></span>

 <span data-ttu-id="63925-133">Para un ejemplo detallado, vea [Crear orden de transporte desde la aplicación de almacén](create-transfer-order-from-warehouse-app.md).</span><span class="sxs-lookup"><span data-stu-id="63925-133">For a detailed example, see [Create transfer order from warehouse app process](create-transfer-order-from-warehouse-app.md).</span></span>

## <a name="handle-event-errors"></a><span data-ttu-id="63925-134">Manejar errores de eventos</span><span class="sxs-lookup"><span data-stu-id="63925-134">Handle event errors</span></span>

<span data-ttu-id="63925-135">Como parte del procesamiento de eventos de almacén, es posible que la actividad de mensaje solicitada no reciba procesos del trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="63925-135">As part of the warehouse event processing, the requested message activity may not receive processes from the batch job.</span></span> <span data-ttu-id="63925-136">En este caso, el mensaje del evento cambiará a **Error**.</span><span class="sxs-lookup"><span data-stu-id="63925-136">In this case, the event message will change to **Failed**.</span></span> <span data-ttu-id="63925-137">Puede usar la información de **Registro de lotes** para saber por qué y tomar las medidas necesarias para corregir cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="63925-137">You can use the **Batch log** information to learn why and take needed action to correct any problems.</span></span>

<span data-ttu-id="63925-138">Para un ejemplo detallado, vea [Crear orden de transporte desde la aplicación de almacén](create-transfer-order-from-warehouse-app.md).</span><span class="sxs-lookup"><span data-stu-id="63925-138">For a detailed example, see [Create transfer order from warehouse app](create-transfer-order-from-warehouse-app.md).</span></span>

<span data-ttu-id="63925-139">Para restablecer un mensaje de evento de aplicación de almacén fallido:</span><span class="sxs-lookup"><span data-stu-id="63925-139">To reset a failed warehouse app event message:</span></span>

1. <span data-ttu-id="63925-140">Vaya a **Gestion de almacenes \> Consultas e informes \> Registros de dispositivos móviles \> Eventos de aplicaciones de almacén**.</span><span class="sxs-lookup"><span data-stu-id="63925-140">Go to **Warehouse management \> Inquiries and reports \> Mobile device logs \> Warehouse app events**.</span></span>
1. <span data-ttu-id="63925-141">En la ficha desplegable **Mensajes de eventos de la aplicación de almacén**, busque y seleccione un evento relevante que muestra **Error** en la columna **Estado del evento**.</span><span class="sxs-lookup"><span data-stu-id="63925-141">On the **Warehouse app event messages** FastTab, find and select a relevant event that is showing **Failed** in the **Event state** column.</span></span>
1. <span data-ttu-id="63925-142">Seleccione **Reiniciar** en la barra de herramientas **Mensajes de eventos de la aplicación de almacén**.</span><span class="sxs-lookup"><span data-stu-id="63925-142">Select **Reset** from the **Warehouse app event messages** toolbar.</span></span>
1. <span data-ttu-id="63925-143">Continúe trabajando hasta que se restablezcan todos los mensajes relevantes.</span><span class="sxs-lookup"><span data-stu-id="63925-143">Continue working until all relevant messages are reset.</span></span>

<span data-ttu-id="63925-144">También puede eliminar un mensaje de evento **Error** utilizando la opción **Eliminar** en la barra de herramientas **Mensajes de eventos de la aplicación de almacén**.</span><span class="sxs-lookup"><span data-stu-id="63925-144">You can also remove a **Failed** event message by using the **Delete** option on the **Warehouse app event messages** toolbar.</span></span>
