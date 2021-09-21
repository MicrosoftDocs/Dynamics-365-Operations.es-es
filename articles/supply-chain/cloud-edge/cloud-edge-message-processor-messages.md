---
title: Mensajes del procesador de mensajes
description: Este tema proporciona información sobre la función de mensajes del procesador de mensajes para las cargas de trabajo de la unidad de escalado.
author: perlynne
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 685c8951b7c0d8524091cf06306388736d894f58
ms.sourcegitcommit: a21166da59675e37890786ebf7e0f198507f7c9b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2021
ms.locfileid: "7471653"
---
# <a name="message-processor-messages"></a>Mensajes del procesador de mensajes

[!include [banner](../includes/banner.md)]

Los mensajes del procesador de mensajes se utilizan cuando se ejecutan unidades de escala de borde y en la nube para [cargas de trabajo de fabricación](cloud-edge-workload-manufacturing.md) y [cargas de trabajo de gestión de almacenes](cloud-edge-workload-warehousing.md).

Se intercambia una gran cantidad de datos entre el concentrador y los entornos de implementación de la unidad de escalado para mantenerlos sincronizados, pero solo algunos de estos intercambios de datos serán procesados por el *procesador de mensajes*. Puede ver los mensajes procesados por el procesador de mensajes yendo a **Administración del sistema > Procesador de mensajes > Mensajes del procesador de mensajes**.

## <a name="message-grid-columns-and-filters"></a>Columnas y filtros de la cuadrícula de mensajes

Puede utilizar los campos en la parte superior de la página **Mensajes del procesador de mensajes** para ayudar a encontrar cualquier mensaje en particular que esté buscando. La mayoría de estos filtros coinciden con los encabezados de columna de la cuadrícula de mensajes. Los siguientes títulos de filtros y columnas están disponibles:

- **Tipo de mensaje**: especifica el tipo de mensaje.
- **Cola de mensajes**: especifica el nombre de la cola en la que se procesará el mensaje. Se proporcionan las siguientes colas:
  - *Unidad de escalado a concentrador*
  - *Centro a unidad de escalado de ejecución de almacén*
  - *Centro a unidad de escalado de ejecución de fabricación*
- **Estado del mensaje**: especifica el estado del mensaje. Existen los siguientes estados:
  - *Puesto en cola*: el mensaje está listo para ser procesado por el procesador de mensajes.
  - *Procesado*: el mensaje lo ha procesado correctamente el procesador de mensajes.
  - *Cancelado*: el mensaje se procesó, pero el procesamiento falló.
- **Contenido del mensaje**: este filtro realiza una búsqueda de texto completa del contenido del mensaje. (El contenido del mensaje no se muestra en la cuadrícula). El filtro trata la mayoría de los símbolos especiales (como "-") como espacios y trata todos los caracteres de espacio como operadores booleanos OR. Por ejemplo, esto significa que si busca un valor de `journalid` igual a "USMF-123456", el sistema encontrará todos los mensajes que contengan "USMF" o "123456", lo que probablemente será una lista larga. Por lo tanto, sería mejor introducir solo "123456" porque eso devolverá resultados más específicos.

## <a name="example-message-type-request-inventory-adjustment-financial-update"></a>Tipo de mensaje de ejemplo: solicitar actualización financiera de ajuste de inventario

Por ejemplo, el **Tipo de mensaje** *Solicitar actualización financiera de ajuste de inventario* se utiliza para crear y registrar un diario de recuento en el centro de conectividad cuando un trabajador utiliza la aplicación de almacén para [registrar un ajuste de inventario](cloud-edge-warehouse-inventory-adjustment.md) en una carga de trabajo de gestión de almacén de unidades de escalado. Debido a que este proceso específico se origina en una unidad de escalado, el campo **Cola de mensajes** mostrará el valor *Unidad de escalado a centro de conectividad*.

Para este tipo de mensaje, la carga de trabajo de una unidad de escalado registra el mensaje como parte de una operación de ajuste de inventario de la aplicación de almacén. A continuación, los datos del mensaje se transfieren al centro de conectividad como parte del mismo proceso utilizado para [Arquitectura de Commerce Data Exchange](../../commerce/commerce-architecture.md). El mensaje se actualizará para mostrar el **Estado del mensaje** como *Puesto en cola*. A continuación, el procesador de mensajes intenta procesar el mensaje y actualiza el **Estado del mensaje** a *Procesado* si hay éxito, o *Cancelado* en caso de errores.

## <a name="view-the-message-log-message-content-and-details"></a>Ver el registro de mensajes, el contenido de los mensajes y detalles

Puede encontrar información detallada sobre un mensaje seleccionándolo en la cuadrícula y luego abriendo las pestañas **Registro** o **Contenido del mensaje** de la cuadrícula de mensajes, donde se muestra cada evento de procesamiento.

El **Contenido del mensaje** depende del **Tipo de mensaje** y, por lo tanto, tendrá una longitud de texto diferente. El texto del contenido de un mensaje típico comenzará con un **{** y terminar con un **}** y en medio tiene nombres de campo como `journalId`, seguido por **:** y un valor como *USMF-123456*.

La barra de herramientas de la pestaña **Registrar** incluye los siguientes botones:

- **Registrar**: muestra los resultados del procesamiento. Esto es especialmente útil para comprender las razones de los errores de procesamiento de mensajes que tienen un **Resultado de procesamiento** de *Errores*.
- **Agrupación de trabajos**: se pueden ejecutar varias operaciones de procesamiento de mensajes como parte del mismo proceso por lotes. Seleccione este botón para ver estos datos detallados. Por ejemplo, puede ver si existen dependencias que requieran que el sistema procese ciertos mensajes en una secuencia específica.

## <a name="message-processor-batch-job"></a>Trabajo por lotes del procesador de mensajes

Al ejecutar una topología híbrida distribuida con unidades de escalado, el trabajo por lotes del *Procesador de mensajes* se activará automáticamente cuando se cree un nuevo mensaje para su procesamiento, por lo que no debería necesitar programar este trabajo manualmente.

Si es necesario, puede acceder al trabajo por lotes yendo a **Administración del sistema > Procesador de mensajes > Procesador de mensajes**.

## <a name="manually-process-or-cancel-a-message"></a>Procesar o cancelar manualmente un mensaje

Si es necesario, puede procesar o cancelar manualmente un mensaje, según su estado actual. Para hacerlo, seleccione el mensaje en la cuadrícula y luego seleccione **Procesar** o **Cancelar** en el panel de acciones

## <a name="set-up-business-events-to-deliver-alerts-for-failed-processing-results"></a>Configurar eventos de negocios para enviar alertas por resultados de procesamiento fallidos

Además de filtrar en el valor de **Estado del mensaje** *Cancelado* para consultar mensajes fallidos, puede configurar [Eventos empresariales](../../fin-ops-core/dev-itpro/business-events/home-page.md) en el centro de conectividad para alertarle sobre los resultados de procesamiento fallidos. Para hacerlo, active el evento empresarial denominado *Mensaje procesado del procesador de mensajes* en la página **Catálogo de eventos empresariales** (**Administración del sistema > Configuración > Eventos empresariales > Catálogo de eventos empresariales**).

Como parte del proceso de activación, se le guiará para especificar si el evento es específico para una o todas las entidades legales y proporcionar un **Nombre de punto de conexión**, que debe definirse primero.

>[!NOTE]
> Si **Cuando ocurre un evento empresarial** se establece en *Microsoft Power Automate* (en vez de *HTTPS*, por ejemplo), el **Nombre del punto de conexión** se creará automáticamente en Supply Chain Management en función de l configuración de *Microsoft Power Automate*.

### <a name="microsoft-power-automate-example"></a>Ejemplo de Microsoft Power Automate

En este ejemplo, usar **Cuando ocurre un evento empresarial** con *Microsoft Power Automate* envía correos electrónicos que contienen mensajes de InfoLog e hipervínculos para abrir la página **Mensajes del procesador de mensajes** para un mensaje de error específico en la implementación del concentrador. Si es necesario, puede agregar lógica adicional para enviar las notificaciones en paralelo utilizando diferentes canales y controlar los destinatarios en función de los datos del evento.

1. En [Power Automate](https://preview.flow.microsoft.com), cree un nuevo flujo de nube automatizado para el desencadenador de flujo **Cuando ocurre un evento empresarial: aplicación Fin & Ops (Dynamics 365)** seguido por los pasos **Analizar JSON** y **Enviar un correo electrónico**, como se muestra en la siguiente ilustración.

    :::image type="content" source="./media/cloud-edge-power-automate-example1.png" alt-text="Flujo de nube automatizado de Power Automate.":::

1. En el paso **Cuando ocurre un evento empresarial**, puede buscar el centro de conectividad **Instancia** o entrar en él, siguiendo la **Categoría** y luego el **Evento empresarial** *Mensaje procesado del procesador de mensajes*, como se muestra en la siguiente ilustración.

    :::image type="content" source="./media/cloud-edge-power-automate-example2.png" alt-text="Paso de Power Automate Cuando ocurre un evento empresarial.":::

1. Para el paso **Analizar JSON**, introduzca un **Esquema** que defina los campos extendidos. Puede usar la opción *Descargar esquema* en la página **Catálogo de eventos empresariales** en Supply Chain Management o comience pegando el texto del esquema de ejemplo. Este texto de ejemplo se proporciona después de la siguiente ilustración.

    :::image type="content" source="./media/cloud-edge-power-automate-example3.png" alt-text="Paso de Power Automate de analizar JSON.":::

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

1. En el paso **Enviar un correo electrónico**, puede seleccionar los campos individuales o comenzar pegando el ejemplo del cuerpo del correo electrónico en el campo **Cuerpo**. Este ejemplo se proporciona después de la siguiente ilustración.

    :::image type="content" source="./media/cloud-edge-power-automate-example4.png" alt-text="Paso de Power Automate de enviar un mensaje de correo electrónico.":::

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

1. Cuando guarde el evento de negocio, se activará automáticamente y estará listo para usar como parte de Supply Chain Management.
