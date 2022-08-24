---
title: Hacer que los bienes terminados estén disponibles físicamente antes de registrarlos en los diarios
description: Cuando un artículo fabricado se notifica como terminado, se registra como disponible para procesamiento físico adicional y se contabilizan uno o más diarios. En este artículo se describe cómo aplazar las publicaciones de diario al permitir que un trabajo por lotes las procese en una cola de mensajes.
author: johanhoffmann
ms.date: 08/02/2022
ms.topic: article
ms.search.form: ProdParameters, JmgProdParameters, InventLocation, JmgMES3PMessageProcessorMessage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-08-02
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 7a8327552d9e6c38721fdac9ee1795e61f90f329
ms.sourcegitcommit: 8d072505f66f507aafbaae65bedf3b530eb6cb7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9266493"
---
# <a name="make-finished-goods-physically-available-before-posting-to-journals"></a>Hacer que los bienes terminados estén disponibles físicamente antes de registrarlos en los diarios

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Cuando un trabajador informa que un artículo fabricado está terminado, el sistema lo registra como disponible para su posterior procesamiento físico (como envío o almacenamiento). Durante este proceso, también se contabilizan uno o más diarios (como el informe como diario terminado, diario de lista de selección y diario de tarjeta de ruta). Si desea que sus artículos estén físicamente disponibles antes de que se hayan procesado todas las contabilizaciones, puede configurar el sistema para diferir las contabilizaciones del diario. Luego, las publicaciones diferidas son administradas por un trabajo por lotes que procesará las publicaciones según lo permitan los recursos del sistema.

La siguiente ilustración muestra cómo se invocan los procesos para contabilizar diarios con y sin contabilización diferida.

![El proceso de informar como finalizado con y sin registro de diario diferido.](media/deferred-posting-flowchart.png "El proceso de informar como finalizado con y sin registro de diario diferido")

## <a name="turn-on-deferred-journal-posting-for-your-system"></a>Active la publicación del diario diferido para su sistema

Antes de poder usar el registro de diario diferido, debe estar activado en su sistema. Los administradores pueden usar el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla. En el espacio de trabajo **Administración de características**, la función aparece de la siguiente forma:

- **Módulo:** *control de producción*
- **Nombre de la característica**: *(Versión preliminar) Hacer que los bienes terminados estén disponibles físicamente antes de registrarlos en los diarios*

## <a name="set-up-journal-posting-options-for-reporting-as-finished"></a>Configure las opciones de publicación de diario para informar como terminado

Los trabajadores pueden informar artículos como terminados utilizando cualquiera de los siguientes clientes:

- Cliente web
- Aplicación móvil Warehouse Management
- Interfaz de ejecución de la planta de producción

El cliente web utiliza la misma configuración de método de publicación que la aplicación móvil de gestión de almacenes. Sin embargo, el método de publicación que utiliza la interfaz de ejecución del piso de producción debe configurarse por separado.

### <a name="set-journal-posting-options-for-the-web-client-and-the-warehouse-management-mobile-app"></a>Establezca opciones de registro de diario para el cliente web y la aplicación móvil de gestión de almacenes

En la aplicación móvil, los trabajadores informan que los artículos están terminados al abrir un elemento del menú del dispositivo móvil donde el valor **Proceso de creación de trabajo** es *Reportar como terminado* o *Reportar como terminado y guardado*. En el cliente web, los trabajadores notifican los artículos como terminados desde la página de lista **Todas las órdenes de producción** o la página **Orden de producción (detalles)**. Puede configurar un método predeterminado para toda la empresa y también puede configurar anulaciones específicas del almacén según lo requiera.

Utilice el siguiente procedimiento para configurar el método de publicación predeterminado en toda la empresa para informar artículos como terminados desde el cliente web o la aplicación móvil de Gestión de almacenes.

1. Vaya a **Control de producción \> Configurar \> Parámetros de control de producción**.
1. En la pestaña **Diarios**, en la sección **Notificar como diario terminado**, configure el campo **Método de registro** en uno de los siguientes valores:

    - *Inmediato* – Cuando un artículo se notifica como terminado, el sistema procesa por completo todas las contabilizaciones de diario relacionadas antes de marcar el artículo terminado como físicamente disponible.
    - *Diferido* – Cuando un artículo se notifica como terminado, el sistema marca el artículo terminado como físicamente disponible y añade los registros del diario a una cola de mensajes. El sistema no espera hasta que las contabilizaciones estén completamente procesadas para marcar el artículo terminado como físicamente disponible.

Utilice el siguiente procedimiento para configurar anulaciones específicas del almacén para el método de contabilización predeterminado que está configurado en la página **Parámetros de control de producción**.

1. Vaya a **Gestión del inventario \> Configuración \> Desglose del inventario \> Almacenes**.
1. Seleccione el almacén que desee configurar.
1. En el panel Acciones, seleccione **Editar**.
1. En la ficha **Almacén**, en la sección **Pedidos de producción**, configure el campo **Método de registro** en uno de los siguientes valores:

    - *Heredar* – El almacén seleccionado hereda la configuración de la página **Parámetros de control de producción**.
    - *Inmediato* – Cuando un artículo se notifica como terminado, el sistema procesa por completo todas las contabilizaciones de diario relacionadas antes de marcar el artículo terminado como físicamente disponible.
    - *Diferido* – Cuando un artículo se notifica como terminado, el sistema marca el artículo terminado como físicamente disponible y añade los registros del diario a una cola de mensajes. El sistema no espera hasta que las contabilizaciones estén completamente procesadas para marcar el artículo terminado como físicamente disponible.

### <a name="set-journal-posting-options-for-the-production-floor-execution-interface"></a>Establecer las opciones de registro del diario para la interfaz de ejecución de la planta de producción

Use el siguiente procedimiento para configurar el método de publicación que se usa cuando los artículos se notifican como terminados desde la interfaz de ejecución del piso de producción.

1. Vaya a **Control de producción \> Configuración \> Ejecución de fabricación \> Valores predeterminados de pedido de producción**.
1. En la pestaña **Notificar como diario terminado**, en la sección **Notificar como diario terminado**, configure el campo **Método de registro** en uno de los siguientes valores:

    - *Inmediato* – Cuando un artículo se notifica como terminado, el sistema procesa por completo todas las contabilizaciones de diario relacionadas antes de marcar el artículo terminado como físicamente disponible.
    - *Diferido* – Cuando un artículo se notifica como terminado, el sistema marca el artículo terminado como físicamente disponible y añade los registros del diario a una cola de mensajes. El sistema no espera hasta que las contabilizaciones estén completamente procesadas para marcar el artículo terminado como físicamente disponible.

## <a name="schedule-the-message-processor-batch-job-to-process-deferred-postings"></a>Programe el trabajo por lotes del procesador de mensajes para procesar publicaciones diferidas

El trabajo por lotes del procesador de mensajes es responsable de procesar las publicaciones de diario después de que se hayan puesto en cola. Para garantizar que se procesen las publicaciones de su diario, debe configurar este trabajo para que se ejecute a intervalos regulares. Utilice el siguiente procedimiento para configurar el trabajo por lotes.

1. Vaya a **Administracion del sistema \> Procesador de mensajes \> Procesador de mensajes**.
1. En la ficha **Parámetros**, establezca el campo **Cola de mensajes** en *Producción*.
1. En la ficha **Ejecutar en segundo plano**, establezca la opción **Procesamiento por lotes** en *Sí*. A continuación, configure un programa recurrente y configure otros ajustes según sea necesario. La configuración funciona igual que para otros tipos de [trabajos en segundo plano](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) en Microsoft Dynamics 365 Supply Chain Management.

## <a name="track-the-progress-of-your-deferred-postings"></a>Siga el progreso de sus publicaciones diferidas

Las publicaciones de diario diferidas se ponen en cola como *mensajes del procesador de mensajes* que esperan hasta que son procesados por el *procesador de mensajes*. El procesador de mensajes debe configurarse para ejecutarse como un trabajo por lotes programado. Para ver los mensajes de publicación diferida que han sido o serán procesados por el procesador de mensajes, vaya a **Control de producción \> Órdenes de producción \> Publicación diferida de órdenes de producción**.

### <a name="message-grid-columns-and-filters"></a>Columnas y filtros de la cuadrícula de mensajes

Puede utilizar los campos en la parte superior de la página **Registro de pedidos de producción aplazados** para ayudar a encontrar cualquier mensaje específico que esté buscando.

Están disponibles los siguientes filtros:

- **Tipo de mensaje** – Especificar el tipo de mensajes que se muestran en la cuadrícula.
- **Estado de mensaje** – Especificar el estado de los mensajes que se muestran en la cuadrícula. Existen los siguientes estados:

    - *Puesto en cola*: el mensaje está listo para ser procesado por el procesador de mensajes.
    - *Procesado*: el mensaje lo ha procesado correctamente el procesador de mensajes.
    - *Cancelado* – El mensaje no se pudo procesar durante el intento final y luego el usuario lo canceló.
    - *Ha fallado* – El mensaje no se pudo procesar durante el último intento. El sistema volverá a intentar los mensajes fallidos tres veces. Entonces se dará por vencido y dejará el mensaje en el estado *Ha fallado*. Tenga en cuenta que no puede cancelar o editar manualmente un mensaje hasta después del último de estos tres intentos.

- **Contenido del mensaje**: este filtro realiza una búsqueda de texto completa del contenido del mensaje. (El contenido del mensaje no se muestra en la cuadrícula). El filtro trata la mayoría de los símbolos especiales (como guiones) como caracteres de espacio y trata todos los caracteres de espacio como operadores booleanos OR. Por ejemplo, si busca un valor `journalid` específico igual a *USMF-123456*, el sistema buscará todos los mensajes que contengan "USMF" o "123456". En este caso, es probable que la lista de resultados sea larga. Por lo tanto, sería mejor introducir solo *123456* porque eso devolverá resultados más específicos.

También puede ordenar y filtrar la lista seleccionando cualquiera de los encabezados de columna e ingresando criterios en el cuadro de diálogo desplegable.

### <a name="view-the-message-log-message-content-and-details"></a>Ver el registro de mensajes, el contenido de los mensajes y detalles

Puede encontrar información detallada sobre un mensaje seleccionándolo en la cuadrícula y luego seleccionando la pestaña **Registro** o **Contenido sin procesar** de la cuadrícula de mensajes, donde se muestra cada evento de procesamiento.

La barra de herramientas de la pestaña **Registrar** incluye los siguientes botones:

- **Registro** – Seleccione este botón para mostrar los resultados del procesamiento. Este botón es especialmente útil cuando los mensajes tienen un valor **Resultado del procesamiento** de *Ha fallado* y desea conocer los motivos del error de procesamiento.
- **Agrupación de trabajos**: se pueden ejecutar varias operaciones de procesamiento de mensajes como parte del mismo proceso por lotes. Seleccione este botón para ver estos datos detallados. Por ejemplo, puede ver si existen dependencias que requieran un orden de procesamiento específico para algunos mensajes.

### <a name="manually-process-or-cancel-a-message"></a>Procesar o cancelar manualmente un mensaje

Puede procesar o cancelar manualmente un mensaje, según sea necesario, dependiendo de su estado actual. Seleccione el mensaje en la cuadrícula y luego seleccione **Procesar** o **Cancelar** en el panel de acciones.

### <a name="set-up-business-events-to-deliver-alerts-for-failed-processing-results"></a>Configurar eventos de negocios para enviar alertas por resultados de procesamiento fallidos

Puede configurar [eventos de negocios](../../fin-ops-core/dev-itpro/business-events/home-page.md) que le aleretn sobre resultados de procesamiento fallidos. Vaya a **Administración del sistema \> Configuración \> Eventos empresariales \> Catálogo de eventos empresariales** y active el evento empresarial denominado *Mensaje procesado del procesador de mensajes*.

Como parte del proceso de activación, se le solicita que especifique si el evento es específico de una entidad legal o se aplica a todas las entidades legales. También se le pedirá que proporcione un valor **Nombre del punto final**. Este valor debe definirse primero.

> [!NOTE]
> Si el campo **Cuando ocurre un evento empresarial** se establece en *Microsoft Power Automate* (en vez de *HTTPS*, por ejemplo), el valor **Nombre del punto de conexión** se creará automáticamente en Supply Chain Management en función de l configuración de *Microsoft Power Automate*.
