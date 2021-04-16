---
title: Operación de inventario saliente en PDV
description: Este tema describe las capacidades de la operación de inventario de salida del punto de venta (PDV).
author: hhaines
ms.date: 07/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 3cfe144f7bba2bbc4b25024b68155045271f6366
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795654"
---
# <a name="outbound-inventory-operation-in-pos"></a>Operación de inventario de salida en PDV

[!include [banner](includes/banner.md)]


En Microsoft Dynamics 365 Commerce, versión 10.0.10 y posteriores, las operaciones de entrada y salida en el punto de venta (PDV) reemplazan la operación de recogida y recepción.

> [!NOTE]
> En la versión 10.0.10 y posteriores, cualquier función nueva en la aplicación PDV relacionada con la recepción del inventario de la tienda contra órdenes de compra y órdenes de transferencia se agregará a la operación de operaciones de entrada. Si actualmente está utilizando la operación de recogida y recepción en PDV, le recomendamos que desarrolle una estrategia para pasar de esa operación a las nuevas operaciones de entrada y salida. Aunque la operación de selección y recepción no se eliminará del producto, no habrá más inversiones en él, desde una perspectiva funcional o de rendimiento, después de la versión 10.0.9.

## <a name="prerequisite-configure-an-asynchronous-document-framework"></a>Requisito previo: configurar un marco de documentos asíncrono

La operación de salida incluye mejoras de rendimiento para garantizar que los usuarios que tienen grandes volúmenes de contabilizaciones de recibos en muchas tiendas o compañías y grandes documentos de inventario, puedan procesar esos documentos a la sede de Commerce (HQ) sin experimentar tiempos de espera o errores. Estas mejoras requieren el uso de un marco de documentos asíncrono.

Cuando se utiliza un marco de documentos asíncrono, puede confirmar los cambios de documentos salientes de PDV a la sede de Commerce (HQ) y luego pasar a otras tareas mientras el procesamiento a la sede de Commerce (HQ) se produce en segundo plano. Puede verificar el estado del documento a través de **Operación de salida** página de lista de documentos en PDV para asegurarse de que la publicación se realizó correctamente. En la aplicación PDV, también puede usar la lista de documentos activos de la operación de salida para ver los documentos que no se pudieron publicar en la sede de Commerce (HQ). Si un documento falla, los usuarios de PDV pueden corregirlo y luego intentar nuevamente procesarlo en la sede de Commerce (HQ).

> [!IMPORTANT]
> El marco de documentos asíncrono debe configurarse antes de que una empresa intente utilizar la operación de salida en PDV.

Para configurar un marco de documentos asíncrono, complete los siguientes procedimientos.

### <a name="create-and-configure-a-number-sequence"></a>Crear y configurar una secuencia numérica

1. Vaya a **Administración de la organización \> Secuencias numéricas \> Secuencias numéricas**.
2. En la página **Secuencias numéricas** , cree una secuencia numérica.
3. En los campos **Código de secuencia numérica** y **Nombre**, introduzca valores definidos por el usuario.
4. En la ficha desplegable **Referencias**, seleccione **Agregar**.
5. En el campo **Área**, seleccione **Parámetros de Commerce**.
6. En el campo **Referencia**, seleccione **Identificador de operación de documento minorista**.
7. En la ficha desplegable **General**, en la sección **Configuración**, establezca la opción **Continuo** a **No** para garantizar que no haya problemas de rendimiento.

### <a name="create-and-schedule-two-batch-jobs-for-the-document-processing-and-monitoring-tasks"></a>Cree y programe dos trabajos por lotes para el procesamiento de documentos y las tareas de seguimiento

> [!NOTE]
> En la versión 10.0.13 y posteriores de Commerce, no tiene que configurar los trabajos por lotes a través del marco de trabajo por lotes. Los procesos por lotes se pueden configurar desde el menú **Retail y Commerce > TI de Retail y Commerce**. Utilice las opciones de menú **Supervisor de operación de documento minorista** y **Procesamiento de operación de documento minorista** para configurar los trabajos por lotes

Los trabajos por lotes que cree se usarán para procesar documentos que fallan o que caducan. También se utilizarán cuando el número de documentos de inventario activos que se procesan desde el PDV excede un valor configurado por el sistema.

1. Vaya **Administración del sistema \> Consultas \> Trabajos por lotes**.
2. En la página **Trabajo por lotes**, cree dos trabajos por lotes:

    - Configure un trabajo para ejecutar la clase **RetailDocumentOperationMonitorBatch**.
    - Configure el otro trabajo para ejecutar la clase **RetailDocumentOperationMonitorBatch**.

3. Programe los nuevos trabajos por lotes para que se ejecuten de forma periódica. Por ejemplo, establezca la programación para que los trabajos se ejecuten cada cinco minutos.

## <a name="prerequisite-add-outbound-operation-to-the-pos-screen-layout"></a>Prerrequisito: agregar operación de salida al diseño de pantalla PDV

Antes de que su organización pueda usar la funcionalidad de operación de salida, debe configurar la operación de PDV **Operación de salida** en uno o más de sus [Diseños de pantalla de PDV](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts). Antes de implementar la nueva operación en un entorno de producción, asegúrese de probarla exhaustivamente y capacitar a sus usuarios para que la utilicen.

## <a name="overview"></a>Visión general

La operación de salida permite a los usuarios de PDV realizar las siguientes tareas:

- Contabilizar los envíos para los documentos de la orden de transferencia en los casos en que la tienda del usuario sea el almacén de salida designado.
- Ver información sobre envíos de pedidos de transferencia históricos que fueron publicados por la tienda.
- Crear nuevas solicitudes de órdenes de transferencia salientes.

Cuando se inicia la operación de salida desde la aplicación PDV, aparece una vista de página de lista. Esta vista muestra documentos de órdenes de transferencia abiertas que tienen líneas de inventario que la tienda actual del usuario está destinada a enviar y cumplir. Para encontrar un documento seleccionado, los usuarios pueden desplazarse por la lista o usar la función de búsqueda.

La lista de documentos de inventario de salida tiene tres pestañas.

- **Activo** - Esta pestaña muestra las órdenes de transferencia que tienen un estado de **Solicitado** o **Parcialmente Enviado**. Los pedidos contienen líneas o cantidades en líneas que deben ser enviadas por la tienda actual del usuario. Esta pestaña también muestra los pedidos que tienen un estado de **Procesamiento en HQ** (es decir, están esperando la confirmación de una publicación exitosa de la sede de Commerce (HQ)) o **Procesamiento fallido** (es decir, la publicación en la sede de Commere (HQ) no tuvo éxito y el usuario debe corregir los datos e intentar nuevamente enviar los pedidos).
- **Borrador** - Esta pestaña muestra las nuevas solicitudes de órdenes de transferencia salientes que creó la tienda del usuario. Sin embargo, los documentos solo se han guardado localmente. Todavía no se han enviado a la sede de Commerce (HQ) para su procesamiento.
- **Completar** - Esta pestaña muestra una lista de documentos de pedido de transferencia que la tienda ha enviado completamente durante los últimos siete días. La finalidad de esta pestaña es meramente informativa. Toda la información sobre los documentos son datos de solo lectura para la tienda.

Cuando ve documentos en cualquiera de las pestañas, el campo **Estado** puede ayudarlo a comprender la etapa en la que se encuentra el documento.

- **Borrador** - El documento de orden de transferencia solo se ha guardado localmente en la base de datos de canales de la tienda. Aún no se ha enviado información sobre la solicitud de orden de transferencia a la sede de Commerce (HQ).
- **Solicitado**: la orden de compra u orden de transferencia se ha creado en la sede de Commerce (HQ) y está completamente abierta. La tienda actual del usuario aún ha procesado cualquier envío contra el documento.
- **Parcialmente Enviado** - El documento de orden de transferencia tiene una o más líneas o cantidades de líneas parciales que se registraron como enviadas por el almacén de salida. Estas líneas enviadas están disponibles para ser recibidas a través de la operación de entrada.
- **Completamente enviado** - La orden de transferencia ha tenido todas sus líneas y cantidades de líneas completas registradas como enviadas por el almacén de salida.
- **En progreso** - Este estado se utiliza para informar a los usuarios del dispositivo que otro usuario está trabajando activamente en el documento.
- **Pausado** - Este estado se muestra después de seleccionar **Pausar la recepción** para detener temporalmente el proceso de recepción.
- **Procesamiento en HQ**: el documento se envió a la sede de Commerce (HQ) desde la aplicación PDV, pero aún no se ha publicado con éxito en la sede de Commerce (HQ). El documento está pasando por el proceso de publicación de documentos asincrónicos. Después de que el documento se publique con éxito en la sede de Commerce (HQ), su estado debe actualizarse a **Totalmente recibido** o **Parcialmente recibido**.
- **Procesamiento fallido** - El documento fue publicado en la sede de Commerce (HQ) y rechazado. El panel **Detalles** muestra el motivo del error de publicación. El documento debe editarse para corregir problemas de datos y luego debe volver a enviarse a la sede de Commerce (HQ) para su procesamiento.

Cuando selecciona una línea de documento en la lista, aparece el panel **Detalles**. Este panel muestra información adicional sobre el documento, como información de envío y fecha. Una barra de progreso muestra cuántos elementos aún deben procesarse. Si el documento no se procesó correctamente en la sede de Commerce (HQ), el panel **Detalles** también muestra mensajes de error relacionados con el fallo.

En la vista de página de la lista de documentos, puede seleccionar **Detalles del pedido** en la barra de la aplicación para ver los detalles del documento. También puede activar el procesamiento de recibos en líneas de documentos elegibles.

En la vista de página de la lista de documentos, también puede crear un nuevo pedido de transferencia saliente para una tienda.

## <a name="transfer-order-shipping-process"></a>Proceso de envío de pedido de transferencia

Después de seleccionar un documento de orden de transferencia en la pestaña **Activo**, puede seleccionar **Detalles del pedido** para comenzar el proceso de cumplimiento. Aparece la vista **Lista completa de pedidos**. Esta página muestra todas las líneas de documento que contienen el elemento. También muestra detalles de la cantidad pedida.

Cada escaneo de un código de barras actualiza la cantidad en el campo **Enviando ahora** por una unidad. Alternativamente, puede introducir una cantidad de envío seleccionando **Enviar producto** en la barra de la aplicación, introduciendo un ID de artículo y luego introduciendo la cantidad. Si el artículo está controlado por la ubicación, puede confirmar o establecer la ubicación de envío para la línea de documentos.

En la vista **Lista completa de pedidos**, puede seleccionar manualmente una línea en la lista y luego actualizar la cantidad **Enviando ahora** para la línea seleccionada en el panel **Detalles**.

### <a name="over-delivery-shipping-validations"></a>Validaciones de envío en exceso

Las validaciones ocurren durante el proceso de recepción de las líneas del documento. Incluyen validaciones para sobre-entrega. Si un usuario intenta recibir más inventario del que se ordenó en un pedido de compra, pero la entrega en exceso no está configurada o la cantidad recibida excede la tolerancia de entrega en exceso configurada para la línea de pedido de compra, el usuario recibe un error y no se le permite recibir la cantidad en exceso.

### <a name="underdelivery-close-lines"></a>Líneas de cierre de entrega incompleta

En Commerce, versión 10.0.12, se agregó una funcionalidad que permite a los usuarios de POS cerrar o cancelar las cantidades restantes durante el envío del pedido de salida si el almacén de salida determina que no puede enviar la cantidad completa que se solicitó. Las cantidades también se pueden cerrar o cancelar más tarde. Para utilizar esta capacidad, la empresa debe estar configurada para permitir la entrega incompleta de órdenes de transferencia. Además, se debe definir un porcentaje de incompleto para la línea de pedido de transferencia.

Para configurar la empresa para permitir la entrega incompleta de pedidos de transferencia, en la sede de Commerce (HQ), vaya a **Gestión de inventario \> Configurar \> Parámetros de gestión de inventario y almacén**. En la página **Parámetros de gestión de inventario y almacén**, en la pestaña **Pedidos de transferencia**, active el parámetro **Aceptar entrega incompleta**. Luego ejecuta el trabajo del planificador de distribución **1070** para sincronizar los cambios de parámetros a su canal de almacén.

Los porcentajes de suministro incompleto para una línea de pedido de transferencia pueden predefinirse en productos como parte de la configuración de producto en la Central de Commerce. Alternativamente, se pueden establecer o sobrescribir en una línea de orden de transferencia específica a través de la Central de Commerce (HQ).

Después de que una organización haya terminado de configurar la entrega incompleta de pedido de transferencia, los usuarios del PDV verán una nueva opción **Cerrar la cantidad restante** en el panel **Detalles** cuando seleccionan una línea de pedido de transferencia saliente a través de la función **Operación de salida** en el PDV. Cuando el usuario completa el envío utilizando la operación **Terminar cumplimiento**, pueden enviar una solicitud a la Central de Commerce (HQ) para cancelar la cantidad restante no enviada. Si el usuario cierra la cantidad restante, Commerce realiza una validación para verificar que la cantidad que se cancela está dentro de la tolerancia de porcentaje de entrega incompleta que se define en la línea de pedido de transferencia. Si se excede la tolerancia de incompleto, se muestra al usuario un mensaje de error y no puede cerrar la cantidad restante hasta que la cantidad previamente enviada y para "enviar ahora" cumpla o exceda la tolerancia de entrega incompleta.

Después de que el envío se sincronice con la Central de Commerce (HQ), las cantidades que se definen en el campo **Enviar ahora** para la línea de pedido de transferencia en POS se actualizan a un estado de enviado en la Central de Commerce (HQ). Las cantidades no enviadas que anteriormente se considerarían cantidades de "envío restante" (es decir, cantidades que se enviarán más tarde) se consideran, en lugar de ello, cantidades canceladas. La cantidad de "envío restante" para la línea de pedido de transferencia se establece en **0** y la línea se considera totalmente enviada.

### <a name="shipping-location-controlled-items"></a>Envío de artículos controlados por ubicación

Si los artículos que se envían están controlados por ubicación, los usuarios pueden elegir la ubicación desde la que desean emitir el inventario durante el proceso de envío. Le recomendamos que configure una ubicación de problema predeterminada para el almacén de su tienda, para que este proceso sea más eficiente. Incluso si se configura una ubicación predeterminada, los usuarios pueden anular la ubicación del problema en las líneas seleccionadas según lo requieran.

La operación respeta la configuración **Recibo en blanco permitido** en la dimensión de almacenamiento **Ubicación** y no requiere que se introduzca una dimensión de ubicación si se configura un recibo en blanco. Si no se permiten ubicaciones de recibos en blanco para un artículo, la aplicación PDV muestra un error y requiere que se introduzca una ubicación antes de que se pueda publicar el recibo.

### <a name="ship-all"></a>Enviar todo

Según lo requiera, puede seleccionar **Enviar todo** en la barra de la aplicación para actualizar rápidamente la cantidad **Enviando ahora** para todas las líneas del documento hasta el valor máximo que está disponible para cumplir con esas líneas.

### <a name="cancel-fulfillment"></a>Cancelar el cumplimiento

Use la función **Cancelar cumplimiento** en la barra de la aplicación solo si desea salir del documento y no desea guardar ningún cambio. Por ejemplo, inicialmente seleccionó el documento incorrecto y no desea guardar ninguno de los datos de envío anteriores.

### <a name="pause-fulfillment"></a>Pausar el cumplimiento

Si está cumpliendo el pedido de transferencia, puede usar la función **Pausar cumplimiento** si desea hacer un descanso del proceso. Por ejemplo, es posible que desee realizar otra operación desde el PDV, como cancelar la venta de un cliente o retrasar la publicación del envío a la Central de Commerce (HQ).

Cuando selecciona **Pausar cumplimiento**, el estado del documento cambia a **Pausado**. Por lo tanto, el usuario sabrá que los datos se han introducido en el documento, pero el documento aún no se ha confirmado. Cuando esté listo para reanudar el proceso de cumplimiento, seleccione el documento en pausa y luego seleccione **Detalles del pedido**. Ninguna cantidad de **Enviando ahora** que se guardaron previamente se conservarán y se pueden ver desde la vista **Lista completa de pedidos**.

### <a name="review"></a>Revisar

Antes del compromiso final de la finalización para la Central de Commerce (HQ), puede usar la funcionalidad **Revisión** para validar el documento entrante. Esta función lo alertará sobre los datos que falten o sean incorrectos que puedan causar una error en el procesamiento y le brindará la oportunidad de corregir problemas antes de enviar la solicitud de finalización. Para habilitar la función **Revisión** en la barra de aplicaciones, habilite la característica **Habilitar validación en las operaciones de inventario de entrada y salida del PDV** a través del espacio de trabajo Administración de características en la Central de Commerce (HQ).

La función **Revisión** valida los siguientes problemas en un documento saliente:
- **Envío en exceso**: la cantidad de envío en un momento determinado es mayor que la cantidad pedida. La gravedad de este problema está determinada por la configuración de sobreentrega en la Central de Commerce (HQ).
- **Envío en defecto**: la cantidad de envío en un momento determinado es menor que la cantidad pedida. La gravedad de este problema está determinada por la configuración de entrega en defecto en la Central de Commerce (HQ).
- **Número de serie**: el número de serie no se proporciona o no está disponible para un artículo serializado que requiere que el número de serie se registre en el inventario.
- **Ubicación no establecida**: la ubicación no se especifica para un elemento controlado por ubicación donde no se permite la ubicación en blanco.
- **Líneas eliminadas**: el pedido tiene líneas eliminadas por un usuario de la Central de Commerce (HQ) que la aplicación de PDV no conoce.

Si establece el parámetro **Habilitar validación automática** en **Sí** en **Parámetros de Commerce** > **Inventario** > **Almacenar operaciones de inventario** para ejecutar la validación automáticamente cuando se selecciona la función **Finalizar cumplimiento**.

### <a name="finish-fulfillment"></a>Finalizar el cumplimiento

Cuando haya terminado de introducir todas las cantidades de **Enviando ahora** para productos, debe seleccionar **Terminar cumplimiento** en la barra de aplicaciones.

Cuando se utiliza el procesamiento de documentos asíncrono, el recibo se envía a través de un marco de documentos asíncrono. El tiempo que lleva publicar el documento depende del tamaño del documento (el número de líneas) y el tráfico de procesamiento general que se produce en el servidor. Por lo general, este proceso ocurre en cuestión de segundos. Si la publicación de documentos falla, se notifica al usuario a través de la lista del documento **Operación de salida** en la pestaña **Activa**, donde el estado del documento se actualizará a **Procesamiento fallido**. El usuario puede seleccionar el documento fallido en PDV para ver los mensajes de error y la razón de la falla en el panel **Detalles**. Un documento fallido permanece sin publicar y requiere que el usuario regrese a las líneas del documento seleccionando **Detalles del pedido** en PDV. El usuario debe actualizar el documento con correcciones, en función de los errores. Después de corregir un documento, el usuario puede intentar procesarlo de nuevo seleccionando **Terminar cumplimiento** en la barra de aplicaciones.

## <a name="create-an-outbound-transfer-order"></a>Crear un pedido de transferencia saliente

Desde PDV, los usuarios pueden crear nuevos documentos de orden de transferencia. Para comenzar el proceso, seleccione **Nuevo** en la barra de aplicaciones mientras está en la lista de documento principal **Operación de salida**. Luego se le pedirá que seleccione un almacén o tienda al que **Transferir a** y al que su tienda actual enviará el inventario. Los valores se limitan a la selección que se define en la configuración del grupo de cumplimiento de la tienda. En una solicitud de transferencia saliente, su tienda actual siempre será el almacén **Transferido de** para la orden de transferencia. No se puede cambiar el valor.

Puede introducir valores en los campos **Fecha de envío**, **Fecha de recepción** y **Modo de entrega** según lo requiera. También puede agregar una nota que se almacenará junto con el encabezado de la orden de transferencia, como un archivo adjunto al documento en la Central de Commerce (HQ).

Después de crear la información del encabezado, puede agregar productos a la orden de transferencia. Para comenzar el proceso de agregar artículos y cantidades solicitadas, escanee códigos de barras o seleccione **Agregar Producto**.

Tras introducir las líneas en la orden de transferencia de salida, debe seleccionar **Guardar** para guardar los cambios del documento localmente o **Enviar petición** para enviar los detalles del pedido a la Central de Commerce (HQ) para su posterior procesamiento. Si selecciona **Guardar**, el borrador del documento se almacena en la base de datos del canal y el almacén de salida no puede ejecutar el documento hasta que se haya procesado correctamente a través de **Enviar petición**. Seleccione **Guardar** solo si no está listo para enviar la solicitud a la Central de Commerce (HQ) para su procesamiento.

Si un documento se guarda localmente, se puede encontrar en la pestaña **Borradores** de la lista de documentos **Operación entrante**. Mientras un documento está en el estado **Borrador**, puede editarlo seleccionando **Editar**. Puede actualizar, agregar o eliminar líneas según lo requiera. También puede eliminar todo el documento mientras está en el estado **Borrador** estado, seleccionando **Eliminar** en la pestaña **Borradores**.

Después de que el borrador del documento se envíe con éxito a la Central de Commerce (HQ), aparecerá en la pestaña **Activo** y tiene un estado de **Solicitado**. En este punto, solo los usuarios del almacén de salida pueden editar el documento seleccionando **Operación de salida** en la aplicación PDV. Los usuarios en el almacén entrante pueden ver la orden de transferencia en la pestaña **Activo** de la lista de documentos **Operación entrante**, pero no pueden editarla ni eliminarla. El bloqueo de edición asegura que no ocurran conflictos porque un solicitante entrante cambia la orden de transferencia al mismo tiempo que el remitente saliente está recogiendo y enviando la orden de forma activa. Si se requieren cambios en la tienda o almacén de entrada después de que se haya enviado la orden de transferencia, se debe contactar al remitente de salida y solicitarle que introduzca los cambios.

Después de que el documento esté en el estado **Pedido**, está listo para el procesamiento de cumplimiento por parte del almacén de salida. A medida que el envío se procesa utilizando la operación de salida, el estado de los documentos de la orden de transferencia se actualiza desde **Pedido** a **Completamente enviado** o **Parcialmente Enviado**. Después de que los documentos estén en el estado **Completamente enviado** o **Parcialmente Enviado**, la tienda entrante o el almacén pueden contabilizar recibos contra ellos mediante el proceso de recepción de operaciones entrantes.

Las órdenes de transferencia enviadas completamente se trasladan a la pestaña **Completado** de la lista de documentos **Operación de salida**. Allí, permanecen visibles para los usuarios en la tienda o almacén de salida, en modo de solo lectura, durante siete días.

## <a name="related-topics"></a>Temas relacionados

[Operación de inventario entrante en PDV](pos-inbound-inventory-operation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]