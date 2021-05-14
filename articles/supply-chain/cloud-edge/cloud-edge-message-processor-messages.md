---
title: Mensajes del procesador de mensajes
description: Este tema proporciona información sobre la función de mensajes del procesador de mensajes para las cargas de trabajo de la unidad de escalado.
author: perlynne
manager: tfehr
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysMessageProcessorMessage, BusinessEventsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: b1428e2e657e653874d4ec07605932a32bd803b2
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938259"
---
# <a name="message-processor-messages"></a><span data-ttu-id="2f4a9-103">Mensajes del procesador de mensajes</span><span class="sxs-lookup"><span data-stu-id="2f4a9-103">Message processor messages</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="2f4a9-104">Los mensajes del procesador de mensajes se utilizan cuando se ejecutan unidades de escala de borde y en la nube para [cargas de trabajo de fabricación](cloud-edge-workload-manufacturing.md) y [cargas de trabajo de gestión de almacenes](cloud-edge-workload-warehousing.md).</span><span class="sxs-lookup"><span data-stu-id="2f4a9-104">Message processor messages are used when running cloud and edge scale units for [manufacturing workloads](cloud-edge-workload-manufacturing.md) and [warehouse management workloads](cloud-edge-workload-warehousing.md).</span></span>

<span data-ttu-id="2f4a9-105">Se intercambia una gran cantidad de datos entre el concentrador y los entornos de implementación de la unidad de escalado para mantenerlos sincronizados, pero solo algunos de estos intercambios de datos serán procesados por el *procesador de mensajes*.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-105">A large amount of data is exchanged between the hub and scale unit deployment environments to keep them in sync, but only a few of these data exchanges will be processed by the *message processor*.</span></span> <span data-ttu-id="2f4a9-106">Puede ver los mensajes procesados por el procesador de mensajes yendo a **Administración del sistema > Procesador de mensajes > Mensajes del procesador de mensajes**.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-106">You can view the messages processed by the message processor by going to **System administration > Message processor > Message processor messages**.</span></span>

## <a name="message-grid-columns-and-filters"></a><span data-ttu-id="2f4a9-107">Columnas y filtros de la cuadrícula de mensajes</span><span class="sxs-lookup"><span data-stu-id="2f4a9-107">Message grid columns and filters</span></span>

<span data-ttu-id="2f4a9-108">Puede utilizar los campos en la parte superior de la página **Mensajes del procesador de mensajes** para ayudar a encontrar cualquier mensaje en particular que esté buscando.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-108">You can use the fields at the top of the **Message processor messages** page to help find any particular messages you are looking for.</span></span> <span data-ttu-id="2f4a9-109">La mayoría de estos filtros coinciden con los encabezados de columna de la cuadrícula de mensajes.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-109">Most of these filters match the column headings in the message grid.</span></span> <span data-ttu-id="2f4a9-110">Los siguientes títulos de filtros y columnas están disponibles:</span><span class="sxs-lookup"><span data-stu-id="2f4a9-110">The following filters and column headings are available:</span></span>

- <span data-ttu-id="2f4a9-111">**Tipo de mensaje**: especifica el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-111">**Message type** – Specifies the type of message.</span></span>
- <span data-ttu-id="2f4a9-112">**Cola de mensajes**: especifica el nombre de la cola en la que se procesará el mensaje.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-112">**Message queue** – Specifies the name of the queue in which the message is to be processed.</span></span> <span data-ttu-id="2f4a9-113">Se proporcionan las siguientes colas:</span><span class="sxs-lookup"><span data-stu-id="2f4a9-113">The following queues are provided:</span></span>
  - <span data-ttu-id="2f4a9-114">*Unidad de escalado a concentrador*</span><span class="sxs-lookup"><span data-stu-id="2f4a9-114">*Scale unit to hub*</span></span>
  - <span data-ttu-id="2f4a9-115">*Centro a unidad de escalado de ejecución de almacén*</span><span class="sxs-lookup"><span data-stu-id="2f4a9-115">*Hub to warehouse execution scale unit*</span></span>
  - <span data-ttu-id="2f4a9-116">*Centro a unidad de escalado de ejecución de fabricación*</span><span class="sxs-lookup"><span data-stu-id="2f4a9-116">*Hub to manufacturing execution scale unit*</span></span>
- <span data-ttu-id="2f4a9-117">**Estado del mensaje**: especifica el estado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-117">**Message state** – Specifies the state of the message.</span></span> <span data-ttu-id="2f4a9-118">Existen los siguientes estados:</span><span class="sxs-lookup"><span data-stu-id="2f4a9-118">The following states exists:</span></span>
  - <span data-ttu-id="2f4a9-119">*Puesto en cola*: el mensaje está listo para ser procesado por el procesador de mensajes.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-119">*Queued* – The message is ready to be processed by the message processor.</span></span>
  - <span data-ttu-id="2f4a9-120">*Procesado*: el mensaje lo ha procesado correctamente el procesador de mensajes.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-120">*Processed* – The message was successfully processed by the message processor.</span></span>
  - <span data-ttu-id="2f4a9-121">*Cancelado*: el mensaje se procesó, pero el procesamiento falló.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-121">*Canceled* – The message was processed, but processing failed.</span></span>
- <span data-ttu-id="2f4a9-122">**Contenido del mensaje**: este filtro realiza una búsqueda de texto completa del contenido del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-122">**Message content** – This filter does a full-text search of message content.</span></span> <span data-ttu-id="2f4a9-123">(El contenido del mensaje no se muestra en la cuadrícula). El filtro trata la mayoría de los símbolos especiales (como "-") como espacios y trata todos los caracteres de espacio como operadores booleanos OR.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-123">(Message content is not shown in the grid.) The filter treats most special symbols (such as "-") as spaces, and treats all space characters as Boolean OR operators.</span></span> <span data-ttu-id="2f4a9-124">T = Por ejemplo, esto significa que si busca un valor de `journalid` igual a "USMF-123456", el sistema encontrará todos los mensajes que contengan "USMF" o "123456", lo que probablemente será una lista larga.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-124">T=For example, this means if you search for a specific `journalid` value equal "USMF-123456", the system will find all messages that contain "USMF" or "123456", which is likely to be a long list.</span></span> <span data-ttu-id="2f4a9-125">Por lo tanto, sería mejor introducir solo "123456" porque eso devolverá resultados más específicos.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-125">Therefore, it would be better to enter just "123456" alone because that will return more specific results.</span></span>

## <a name="example-message-type-request-inventory-adjustment-financial-update"></a><span data-ttu-id="2f4a9-126">Tipo de mensaje de ejemplo: solicitar actualización financiera de ajuste de inventario</span><span class="sxs-lookup"><span data-stu-id="2f4a9-126">Example message type: Request inventory adjustment financial update</span></span>

<span data-ttu-id="2f4a9-127">Por ejemplo, el **Tipo de mensaje** *Solicitar actualización financiera de ajuste de inventario* se utiliza para crear y registrar un diario de recuento en el centro de conectividad cuando un trabajador utiliza la aplicación de almacén para [registrar un ajuste de inventario](cloud-edge-warehouse-inventory-adjustment.md) en una carga de trabajo de gestión de almacén de unidades de escalado.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-127">For example, the **Message type** *Request inventory adjustment financial update* is used to create and post a counting journal on the hub when a worker uses the warehouse app to [register an inventory adjustment](cloud-edge-warehouse-inventory-adjustment.md) on a scale unit warehouse management workload.</span></span> <span data-ttu-id="2f4a9-128">Debido a que este proceso específico se origina en una unidad de escalado, el campo **Cola de mensajes** mostrará el valor *Unidad de escalado a centro de conectividad*.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-128">Because this specific process originates from a scale unit, the **Message queue** field will show the value *Scale unit to hub*.</span></span>

<span data-ttu-id="2f4a9-129">Para este tipo de mensaje, la carga de trabajo de una unidad de escalado registra el mensaje como parte de una operación de ajuste de inventario de la aplicación de almacén.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-129">For this message type, a scale unit workload records the message as part of a warehouse app inventory adjustment operation.</span></span> <span data-ttu-id="2f4a9-130">A continuación, los datos del mensaje se transfieren al centro de conectividad como parte del mismo proceso utilizado para [Arquitectura de Commerce Data Exchange](../../commerce/commerce-architecture.md).</span><span class="sxs-lookup"><span data-stu-id="2f4a9-130">The message data is then transferred to the hub as part of the same process used for the [Commerce data exchange architecture](../../commerce/commerce-architecture.md).</span></span> <span data-ttu-id="2f4a9-131">El mensaje se actualizará para mostrar el **Estado del mensaje** como *Puesto en cola*.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-131">The message will be updated to show **Message state** as *Queued*.</span></span> <span data-ttu-id="2f4a9-132">A continuación, el procesador de mensajes intenta procesar el mensaje y actualiza el **Estado del mensaje** a *Procesado* si hay éxito, o *Cancelado* en caso de errores.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-132">The message processor then attempts to process the message and updates the **Message state** to *Processed* on success, or *Canceled* on failure.</span></span>

## <a name="view-the-message-log-message-content-and-details"></a><span data-ttu-id="2f4a9-133">Ver el registro de mensajes, el contenido de los mensajes y detalles</span><span class="sxs-lookup"><span data-stu-id="2f4a9-133">View the message log, message content, and details</span></span>

<span data-ttu-id="2f4a9-134">Puede encontrar información detallada sobre un mensaje seleccionándolo en la cuadrícula y luego abriendo las pestañas **Registro** o **Contenido del mensaje** de la cuadrícula de mensajes, donde se muestra cada evento de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-134">You can find detailed information about a message by selecting it in the grid and then opening the **Log** or **Message content** tabs under the message grid, where each processing event is shown.</span></span>

<span data-ttu-id="2f4a9-135">El **Contenido del mensaje** depende del **Tipo de mensaje** y, por lo tanto, tendrá una longitud de texto diferente.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-135">The **Message content** depends on the **Message type** and will therefore have different text length.</span></span> <span data-ttu-id="2f4a9-136">El texto del contenido de un mensaje típico comenzará con un **{** y terminar con un **}** y en medio tiene nombres de campo como `journalId`, seguido por **:** y un valor como *USMF-123456*.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-136">A typical message content text will start with a **{** and end with a **}** and in between have field names such as `journalId` followed by a **:** and a value such as *USMF-123456*.</span></span>

<span data-ttu-id="2f4a9-137">La barra de herramientas de la pestaña **Registrar** incluye los siguientes botones:</span><span class="sxs-lookup"><span data-stu-id="2f4a9-137">The toolbar on the **Log** tab includes the following buttons:</span></span>

- <span data-ttu-id="2f4a9-138">**Registrar**: muestra los resultados del procesamiento.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-138">**Log** – Displays the processing results.</span></span> <span data-ttu-id="2f4a9-139">Esto es especialmente útil para comprender las razones de los errores de procesamiento de mensajes que tienen un **Resultado de procesamiento** de *Errores*.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-139">This is especially helpful for understanding the reasons for a processing failure for messages having a **Processing result** of *Failed*.</span></span>
- <span data-ttu-id="2f4a9-140">**Agrupación de trabajos**: se pueden ejecutar varias operaciones de procesamiento de mensajes como parte del mismo proceso por lotes.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-140">**Bundle** – Multiple message processing operations can run as part of the same batch process.</span></span> <span data-ttu-id="2f4a9-141">Seleccione este botón para ver estos datos detallados.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-141">Select this button to view this detailed data.</span></span> <span data-ttu-id="2f4a9-142">Por ejemplo, puede ver si existen dependencias que requieran que el sistema procese ciertos mensajes en una secuencia específica.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-142">For example, you can see whether dependencies exist that require the system to process certain messages in a specific sequence.</span></span>

## <a name="message-processor-batch-job"></a><span data-ttu-id="2f4a9-143">Trabajo por lotes del procesador de mensajes</span><span class="sxs-lookup"><span data-stu-id="2f4a9-143">Message processor batch job</span></span>

<span data-ttu-id="2f4a9-144">Al ejecutar una implementación de borde en la nube, el trabajo por lotes del *Procesador de mensajes* se activará automáticamente cuando se cree un nuevo mensaje para su procesamiento, por lo que no debería necesitar programar este trabajo manualmente.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-144">When running a cloud and edge deployment, the *Message processor* batch job will automatically be evoked when a new message is created for processing, so you should not need to schedule this job manually.</span></span>

<span data-ttu-id="2f4a9-145">Si es necesario, puede acceder al trabajo por lotes yendo a **Administración del sistema > Procesador de mensajes > Procesador de mensajes**.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-145">If necessary, you can access the batch job by going to **System administration > Message  processor > Message processor**.</span></span>

## <a name="manually-process-or-cancel-a-message"></a><span data-ttu-id="2f4a9-146">Procesar o cancelar manualmente un mensaje</span><span class="sxs-lookup"><span data-stu-id="2f4a9-146">Manually process or cancel a message</span></span>

<span data-ttu-id="2f4a9-147">Si es necesario, puede procesar o cancelar manualmente un mensaje, según su estado actual.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-147">If needed, you can manually process or cancel a message, depending on its current state.</span></span> <span data-ttu-id="2f4a9-148">Para hacerlo, seleccione el mensaje en la cuadrícula y luego seleccione **Procesar** o **Cancelar** en el panel de acciones</span><span class="sxs-lookup"><span data-stu-id="2f4a9-148">To do so, select the message in the grid and then select **Process** or **Cancel** on the Action Pane</span></span>

## <a name="set-up-business-events-to-deliver-alerts-for-failed-processing-results"></a><span data-ttu-id="2f4a9-149">Configurar eventos de negocios para enviar alertas por resultados de procesamiento fallidos</span><span class="sxs-lookup"><span data-stu-id="2f4a9-149">Set up business events to deliver alerts for failed processing results</span></span>

<span data-ttu-id="2f4a9-150">Además de filtrar en el valor de **Estado del mensaje** *Cancelado* para consultar mensajes fallidos, puede configurar [Eventos empresariales](../../fin-ops-core/dev-itpro/business-events/home-page.md) en el centro de conectividad para alertarle sobre los resultados de procesamiento fallidos.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-150">In addition to filtering on the **Message state** value *Canceled* to inquire for failed messages, you can set up [Business events](../../fin-ops-core/dev-itpro/business-events/home-page.md) on the hub to alert you to failed processing results.</span></span> <span data-ttu-id="2f4a9-151">Para hacerlo, active el evento empresarial denominado *Mensaje procesado del procesador de mensajes* en la página **Catálogo de eventos empresariales** (**Administración del sistema > Configuración > Eventos empresariales > Catálogo de eventos empresariales**).</span><span class="sxs-lookup"><span data-stu-id="2f4a9-151">To do so, activate the business event named *Message processor message processed*  on the **Business events catalog** page (**System administration > Setup > Business events > Business events catalog**).</span></span>

<span data-ttu-id="2f4a9-152">Como parte del proceso de activación, se le guiará para especificar si el evento es específico para una o todas las entidades legales y proporcionar un **Nombre de punto de conexión**, que debe definirse primero.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-152">As part of the activation process, you will be guided to specify whether the event is specific to one or all legal entities and provide an **Endpoint name**, which must be defined first.</span></span>

>[!NOTE]
> <span data-ttu-id="2f4a9-153">Si **Cuando ocurre un evento empresarial** se establece en *Microsoft Power Automate* (en vez de *HTTPS*, por ejemplo), el **Nombre del punto de conexión** se creará automáticamente en Supply Chain Management en función de l configuración de *Microsoft Power Automate*.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-153">If **When a Business Event occurs** is set to *Microsoft Power Automate* (rather than *HTTPS*, for example), the **Endpoint name** will automatically be created in Supply Chain Management based on the *Microsoft Power Automate* setup.</span></span>

### <a name="microsoft-power-automate-example"></a><span data-ttu-id="2f4a9-154">Ejemplo de Microsoft Power Automate</span><span class="sxs-lookup"><span data-stu-id="2f4a9-154">Microsoft Power Automate example</span></span>

<span data-ttu-id="2f4a9-155">En este ejemplo, usar **Cuando ocurre un evento empresarial** con *Microsoft Power Automate* envía correos electrónicos que contienen mensajes de InfoLog e hipervínculos para abrir la página **Mensajes del procesador de mensajes** para un mensaje de error específico en la implementación del concentrador.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-155">In this example, use **When a Business Event occurs** with *Microsoft Power Automate* sends emails containing InfoLog messages and hyperlinks to open the **Message processor messages** page for a specific failed message on the hub deployment.</span></span> <span data-ttu-id="2f4a9-156">Si es necesario, puede agregar lógica adicional para enviar las notificaciones en paralelo utilizando diferentes canales y controlar los destinatarios en función de los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-156">If needed, you can add extra logic to send the notifications in parallel using different channels and control the recipients based on the event data.</span></span>

1. <span data-ttu-id="2f4a9-157">En [Power Automate](https://preview.flow.microsoft.com), cree un nuevo flujo de nube automatizado para el desencadenador de flujo **Cuando ocurre un evento empresarial: aplicación Fin & Ops (Dynamics 365)** seguido por los pasos **Analizar JSON** y **Enviar un correo electrónico**, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-157">In [Power Automate](https://preview.flow.microsoft.com), create a new automated cloud flow for the flow trigger **When a Business Event occurs - Fin & Ops App (Dynamics 365)** followed by the **Parse JSON** and **Send an email** steps, as shown in the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example1.png" alt-text="Flujo de nube automatizado de Power Automate":::

1. <span data-ttu-id="2f4a9-159">En el paso **Cuando ocurre un evento empresarial**, puede buscar el centro de conectividad **Instancia** o entrar en él, siguiendo la **Categoría** y luego el **Evento empresarial** *Mensaje procesado del procesador de mensajes*, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-159">In the **When a Business Event occurs** step, you can look up or enter the hub **Instance** following the **Category** and then the **Business event** *Message processor message processed*, as shown in the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example2.png" alt-text="Paso de Power Automate Cuando ocurre un evento empresarial":::

1. <span data-ttu-id="2f4a9-161">Para el paso **Analizar JSON**, introduzca un **Esquema** que defina los campos extendidos.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-161">For the **Parse JSON** step, enter a **Schema** that defines the extended fields.</span></span> <span data-ttu-id="2f4a9-162">Puede usar la opción *Descargar esquema* en la página **Catálogo de eventos empresariales** en Supply Chain Management o comience pegando el texto del esquema de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-162">You can use the *Download schema* option on the **Business events catalog** page in Supply Chain Management or start by pasting in the example schema text.</span></span> <span data-ttu-id="2f4a9-163">Este texto de ejemplo se proporciona después de la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-163">This example text is provided after the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example3.png" alt-text="Paso de Power Automate de analizar JSON":::

    ```json
    {
        "properties": {
            "BusinessEventId": {
                "type": "string"
            },
            "ControlNumber": {
                "type": "integer"
            },
            "EventId": {
                "type": "string"
            },
            "EventTime": {
                "type": "string"
            },
            "MajorVersion": {
                "type": "integer"
            },
            "MessageContent": {
                "type": "string"
            },
            "MessageDestinationCompanyId": {
                "type": "string"
            },
            "MessageDestinationOperationalSiteId": {
                "type": "string"
            },
            "MessageDestinationWarehouseId": {
                "type": "string"
            },
            "MessageDestinationWorkloadName": {
                "type": "string"
            },
            "MessageInfolog": {
                "type": "string"
            },
            "MessageProcessingResult": {
                "type": "string"
            },
            "MessageProcessingResultLabel": {
                "type": "string"
            },
            "MessageProcessorMessagePageUrl": {
                "type": "string"
            },
            "MessageQueue": {
                "type": "string"
            },
            "MessageQueueLabel": {
                "type": "string"
            },
            "MessageSourceCompanyId": {
                "type": "string"
            },
            "MessageSourceOperationalSiteId": {
                "type": "string"
            },
            "MessageSourceWarehouseId": {
                "type": "string"
            },
            "MessageSourceWorkloadName": {
                "type": "string"
            },
            "MessageState": {
                "type": "string"
            },
            "MessageStateLabel": {
                "type": "string"
            },
            "MessageType": {
                "type": "string"
            },
            "MessageTypeLabel": {
                "type": "string"
            },
            "MinorVersion": {
                "type": "integer"
            }
        },
        "type": "object"
    }
    ```

1. <span data-ttu-id="2f4a9-165">En el paso **Enviar un correo electrónico**, puede seleccionar los campos individuales o comenzar pegando el ejemplo del cuerpo del correo electrónico en el campo **Cuerpo**.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-165">In the **Send an email** step, you can select the individual fields or start by pasting the email body example into the **Body** field.</span></span> <span data-ttu-id="2f4a9-166">Este ejemplo se proporciona después de la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-166">This example is provided after the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example4.png" alt-text="Paso de Power Automate de enviar un mensaje de correo electrónico":::

    ```plaintext
    Message queue: @{body('Parse_JSON')?['MessageQueue']}
    Message queue label: @{body('Parse_JSON')?['MessageQueueLabel']}
    Message type: @{body('Parse_JSON')?['MessageQueueType']}
    Message type label: @{body('Parse_JSON')?['MessageQueueTypeLabel']}
    Message content: @{body('Parse_JSON')?['MessageContent']}
    Message state: @{body('Parse_JSON')?['MessageState']}
    Message state label: @{body('Parse_JSON')?['MessageStateLabel']}
    Message processing result: @{body('Parse_JSON')?['MessageProcessingResult']}
    Message processing result label: @{body('Parse_JSON')?['MessageProcessingResultLabel']}
    Message infolog: @{body('Parse_JSON')?['MessageInfolog']}
    Message source company ID: @{body('Parse_JSON')?['MessageSourceCompanyId']}
    Message source workload name: @{body('Parse_JSON')?['MessageSourceWorkloadName']}
    Message source site ID: @{body('Parse_JSON')?['MessageSourceOperationalSiteId']}
    Message source warehouse ID: @{body('Parse_JSON')?['MessageSourceWarehouseId']}
    Message destination company ID: @{body('Parse_JSON')?['MessageDestinationCompanyId']}
    Message destination workload name: @{body('Parse_JSON')?['MessageDestinationWorkloadName']}
    Message destination site ID: @{body('Parse_JSON')?['MessageDestinationOperationalSiteId']}
    Message destination warehouse ID: @{body('Parse_JSON')?['MessageDestinationWarehouseId']}
    Message processor message page URL: @{body('Parse_JSON')?['MessageProcessorMessagePageUrl']}
    ```

1. <span data-ttu-id="2f4a9-168">Cuando guarde el evento de negocio, se activará automáticamente y estará listo para usar como parte de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2f4a9-168">When you save the business event, it will automatically be activated and ready to use as part of Supply Chain Management.</span></span>
