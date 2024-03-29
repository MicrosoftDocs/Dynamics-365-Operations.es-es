---
title: Operación de inventario entrante en PDV
description: Este artículo describe las capacidades de la operación de inventario de entrada del punto de venta (PDV).
author: hhainesms
ms.date: 11/16/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 7999c8409c71c7ccf9c1d44bd86ddca6f5e8f6ff
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785029"
---
# <a name="inbound-inventory-operation-in-pos"></a>Operación de inventario entrante en PDV

[!include [banner](includes/banner.md)]

En Microsoft Dynamics 365 Commerce, versión 10.0.10 y posteriores, las operaciones de entrada y salida en el punto de venta (PDV) reemplazan la operación de recogida y recepción.

> [!NOTE]
> En la versión 10.0.10 y posteriores de Commerce, cualquier característica nueva en la aplicación PDV relacionada con la recepción del inventario de la tienda contra órdenes de compra y órdenes de transferencia se agregará a la operación de **Operaciones de entrada** de PDV. Si actualmente está utilizando la operación de recogida y recepción en PDV, le recomendamos que desarrolle una estrategia para pasar de esa operación a las nuevas operaciones de entrada y salida. Aunque la operación de selección y recepción no se eliminará del producto, no habrá más inversiones en él, desde una perspectiva funcional o de rendimiento, después de la versión 10.0.9.

El siguiente video proporciona una descripción general de los procesos de negocio y las capacidades de inventario en tienda en Dynamics 365 Commerce.


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE5bMSx]

## <a name="prerequisite-configure-an-asynchronous-document-framework"></a>Requisito previo: configurar un marco de documentos asíncrono

La operación de entrada incluye mejoras de rendimiento para garantizar que los usuarios que tienen grandes volúmenes de contabilizaciones de recibos en muchas tiendas o compañías y grandes documentos de inventario, puedan procesar esos documentos a la sede de Comercio sin experimentar tiempos de espera o errores. Estas mejoras requieren el uso de un marco de documentos asíncrono.

Cuando se utiliza un marco de documentos asíncrono, puede confirmar los cambios de documentos entrantes de PDV a Commerce Headquarters y luego pasar a otras tareas mientras el procesamiento a Commerce Headquarters se produce en segundo plano. Puede verificar el estado de un documento a través de la página de lista de documentos **Operación de entrada** en PDV para asegurarse de que la publicación se realizó correctamente. En la aplicación PDV, también puede usar la lista de documentos activos de la operación de entrada para ver los documentos que no se pudieron publicar en Commerce Headquarters. Si un documento falla, los usuarios de PDV pueden corregirlo y luego intentar nuevamente procesarlo en la sede de Comercio.

> [!IMPORTANT]
> El marco de documentos asíncrono debe configurarse antes de que una empresa intente utilizar la operación de entrada en PDV.

Para configurar un marco de documentos asíncrono, complete los siguientes procedimientos.

### <a name="create-and-configure-a-number-sequence"></a>Crear y configurar una secuencia numérica

1. Vaya a **Administración de la organización \> Secuencias numéricas \> Secuencias numéricas**.
2. En la página **Secuencias numéricas** , cree una secuencia numérica.
3. En los campos **Código de secuencia numérica** y **Nombre**, introduzca valores definidos por el usuario.
4. En la ficha desplegable **Referencias**, seleccione **Agregar**.
5. En el campo **Área**, seleccione **Parámetros de Commerce**.
4. En el campo **Referencia**, seleccione **Identificador de operación de documento minorista**.
5. En la ficha desplegable **General**, en la sección **Configuración**, establezca la opción **Continuo** a **No** para garantizar que no haya problemas de rendimiento.

### <a name="create-and-schedule-two-batch-jobs-for-the-document-processing-and-monitoring-tasks"></a>Cree y programe dos trabajos por lotes para el procesamiento de documentos y las tareas de seguimiento

> [!NOTE]
> En la versión 10.0.13 y posteriores de Commerce, no tiene que configurar estos trabajos por lotes a través del marco de trabajo por lotes. Los procesos por lotes se pueden configurar desde el menú **Retail y Commerce > TI de Retail y Commerce**. Utilice las opciones de menú **Supervisor de operación de documento minorista** y **Procesamiento de operación de documento minorista** para configurar los trabajos por lotes.

Los trabajos por lotes que cree se usarán para procesar documentos que fallan o que caducan. También se utilizarán cuando el número de documentos de inventario activos que se procesan desde el PDV excede un valor configurado por el sistema.

1. Vaya **Administración del sistema \> Consultas \> Trabajos por lotes**.
2. En la página **Trabajo por lotes**, cree dos trabajos por lotes:

    - Configure un trabajo para ejecutar la clase **RetailDocumentOperationMonitorBatch**.
    - Configure el otro trabajo para ejecutar la clase **RetailDocumentOperationMonitorBatch**.

2. Programe los nuevos trabajos por lotes para que se ejecuten de forma periódica. Por ejemplo, establezca la programación para que los trabajos se ejecuten cada cinco minutos.

## <a name="prerequisite-add-inbound-operation-to-the-pos-screen-layout"></a>Prerrequisito: agregar operación de entrada al diseño de pantalla PDV

Antes de que su organización pueda usar la funcionalidad de operación de entrada, debe configurar la operación de PDV **Operación de entrada** en uno o más de sus [Diseños de pantalla de PDV](/dynamics365/unified-operations/retail/pos-screen-layouts). Antes de implementar la nueva operación en un entorno de producción, asegúrese de probarla exhaustivamente y capacitar a sus usuarios para que la utilicen.

## <a name="overview"></a>Visión general

La operación de entrada permite a los usuarios de PDV realizar las siguientes tareas:

- Recibir el inventario en el almacén de los documentos de pedido de compra confirmados o de los documentos de pedido de transferencia enviados.
- Ver información sobre recibos de inventario históricos durante un período de siete días después de que el documento se haya recibido por completo.
- Crear nuevas solicitudes de órdenes de transferencia entrantes.

Cuando se inicia la operación de entrada desde la aplicación PDV, aparece una vista de página de lista. Esta vista muestra documentos de órdenes de compra y transferencia abiertas que tienen líneas de inventario que están programadas para ser recibidas por la tienda actual. Para encontrar y seleccionar un documento específico, los usuarios pueden desplazarse por la lista o usar la función de búsqueda.

La lista de documentos de inventario de entrada tiene tres pestañas:

- **Activo** - Esta pestaña muestra documentos que están total o parcialmente abiertos y que contienen líneas o cantidades en líneas que aún deben recibirse.
- **Borrador** - Esta pestaña muestra las nuevas solicitudes de órdenes de transferencia entrantes que creó la tienda. Sin embargo, los documentos solo se han guardado localmente. Todavía no se han enviado a la sede de Comercio para su procesamiento.
- **Completar** - Esta pestaña muestra una lista de documentos de pedido de transferencia o de compra que la tienda ha recibido completamente durante los últimos siete días. La finalidad de esta pestaña es meramente informativa. Toda la información sobre los documentos son datos de solo lectura para la tienda.

Cuando ve documentos en cualquiera de las pestañas, el campo **Estado** puede ayudarlo a comprender la etapa en la que se encuentra el documento.

- **Borrador** - El documento de orden de transferencia solo se ha guardado localmente en la base de datos de canales de la tienda. Aún no se ha enviado información sobre la solicitud de orden de transferencia a la sede de Comercio.
- **Solicitado** - La orden de compra u orden de transferencia se ha creado en Commerce Headquarters y está completamente abierta. Aún no se han procesado recibos contra el documento. Para documentos del tipo de documento de orden de compra, la recepción puede comenzar en cualquier momento mientras el estado sea **Pedido**.
- **Parcialmente Enviado** - El documento de orden de transferencia tiene una o más líneas o cantidades de líneas parciales que se registraron como enviadas por el almacén de salida. Estas líneas enviadas están disponibles para ser recibidas a través de la operación de entrada.
- **Completamente enviado** - La orden de transferencia ha tenido todas sus líneas y cantidades de líneas completas registradas como enviadas por el almacén de salida. Todo el documento está disponible para ser recibido a través de la operación de entrada.
- **Parcialmente recibido** - Algunas de las líneas o cantidades de líneas en el pedido o documento de pedido de transferencia han sido recibidas por la tienda, pero algunas líneas permanecen abiertas.
- **Totalmente recibido** - Todas las líneas y cantidades en la orden de compra o el documento de la orden de transferencia se han recibido por completo. Los documentos son accesibles solo en la pestaña **Completo** y son de solo lectura por los usuarios de la tienda.
- **En progreso** - Este estado se utiliza para informar a los usuarios del dispositivo que otro usuario está trabajando activamente en el documento.
- **Pausado** - Este estado se muestra después de seleccionar **Pausar la recepción** para detener temporalmente el proceso de recepción.
- **Procesamiento en HQ** - El documento se envió a la sede de Comercio desde la aplicación PDV, pero aún no se ha publicado con éxito en la sede de Comercio. El documento está pasando por el proceso de publicación de documentos asincrónicos. Después de que el documento se publique con éxito en la sede de Comercio, su estado debe actualizarse a **Totalmente recibido** o **Parcialmente recibido**.
- **Procesamiento fallido** - El documento fue publicado en la sede de Comercio y rechazado. El panel **Detalles** muestra el motivo del error de publicación. El documento debe editarse para corregir problemas de datos y luego debe volver a enviarse a la sede de Comercio para su procesamiento.

Cuando selecciona una línea de documento en la lista, aparece el panel **Detalles**. Este panel muestra información adicional sobre el documento, como información de envío y fecha. Una barra de progreso muestra cuántos elementos aún deben procesarse. Si el documento no se procesó correctamente en la sede de Comercio, el panel **Detalles** también muestra mensajes de error relacionados con el fallo.

En la vista de página de la lista de documentos, puede seleccionar **Detalles del pedido** en la barra de la aplicación para ver los detalles del documento. También puede activar el procesamiento de recibos en líneas de documentos elegibles.

En la vista de página de la lista de documentos, también puede crear un nuevo pedido de transferencia entrante para una solicitud de una tienda. Los documentos permanecen en el estado **Borrador** y se pueden ajustar o eliminar hasta que se envíen a la sede de Commerce para su procesamiento. Después de que se envían a la sede de Commerce, las líneas de orden de transferencia ya no se pueden cambiar desde la aplicación PDV.

## <a name="receiving-process"></a>Proceso de recepción

Después de seleccionar un documento de orden de transferencia o de compra en la pestaña **Activo**, puede seleccionar **Detalles del pedido** para comenzar el proceso de recepción.

Por defecto se muestra la vista **Recibiendo ahora**. Esta vista está optimizada para el escaneo de códigos de barras. Se puede utilizar para crear una lista de los elementos que se han escaneado, de modo que se puedan recibir esos elementos. Para comenzar el proceso de recepción, puede comenzar a escanear códigos de barras de artículos.

A medida que los códigos de barras de los artículos se escanean en la vista **Recibiendo ahora**, la aplicación valida los artículos contra el documento de pedido de compra o transferencia seleccionado, para asegurarse de que cada artículo escaneado coincida con un artículo válido en el documento. En la vista **Recibiendo ahora** se supone que cada escaneo de un código de barras representa la recepción de una cantidad de una unidad, a menos que se incluya una cantidad en el código de barras. Puede escanear repetidamente códigos de barras en esta vista para crear una lista de todos los artículos y cantidades para el recibo.

### <a name="example-scenario"></a>Supuesto de ejemplo

Un usuario recibe una orden de compra que contiene 10 unidades con el código de barras 5657900266. El usuario puede escanear ese código de barras 10 veces para actualizar el campo **Recibiendo ahora** por unidad por escaneo. Cuando el usuario ha completado los escaneos, el campo **Recibiendo ahora** para la línea del artículo mostrará que se recibió una cantidad de 10.

Alternativamente, en un escenario donde la cantidad del artículo es grande, el usuario podría preferir introducir manualmente la cantidad en lugar de escanear el código de barras para cada artículo que se recibe. En este caso, el usuario puede escanear el código de barras una vez para agregar el elemento a la lista **Recibiendo ahora**. El usuario puede seleccionar la línea asociada en la vista **Recibiendo ahora** y luego, en el panel **Detalles** que aparece en el lado derecho de la página, actualizar el campo **Cantidad de recepción** para el artículo.

Aunque la vista **Recibiendo ahora** está optimizada para el escaneo de códigos de barras, los usuarios también pueden seleccionar **Recibir producto** en la barra de la aplicación y luego introducir la ID del elemento o los datos del código de barras a través de un cuadro de diálogo. Después de validar el artículo que se introdujo, se le solicita al usuario que añada la cantidad del recibo.

La vista **Recibiendo ahora** proporciona una forma centrada para que los usuarios vean qué productos están recibiendo. Alternativamente puede usar la vista **Lista completa de pedidos**. Esta vista muestra la lista completa de líneas de documentos para el documento de pedido de compra o transferencia seleccionado. Los usuarios pueden seleccionar líneas manualmente en la lista y luego, en el panel **Detalles**, actualizar el campo **Cantidad de recepción** para la línea seleccionada. En la vista **Lista completa de pedidos**, los usuarios pueden escanear códigos de barras o pueden usar la función **Recibir producto** para introducir la ID del artículo o el código de barras y los datos sobre la cantidad recibida, sin tener que seleccionar primero la línea del artículo correspondiente en la lista.

### <a name="over-receiving-validations"></a>Sobre-recepción de validaciones

Las validaciones ocurren durante el proceso de recepción de las líneas del documento. Incluyen validaciones para sobre-entrega. Si un usuario intenta recibir más inventario del que se ordenó en un pedido de compra, pero la entrega en exceso no está configurada o la cantidad recibida excede la tolerancia de entrega en exceso configurada para la línea de pedido de compra, el usuario recibe un error y no se le permite recibir la cantidad en exceso.

La sobre recepción no está permitida para los documentos de la orden de transferencia. Los usuarios siempre recibirán errores si intentan recibir más de lo que se envió para la línea de pedido de transferencia.

### <a name="close-purchase-order-lines"></a>Cerrar líneas de pedido de compra

Puede cerrar la cantidad restante en una orden de compra entrante durante el proceso de recepción si el remitente ha confirmado que no puede enviar la cantidad completa solicitada. Para ello, la empresa debe estar configurada para permitir la entrega incompleta de órdenes de compra. Además, se debe definir un porcentaje de tolerancia incompleto para la línea de pedido de compra.

Para configurar la empresa para permitir la entrega deficiente de órdenes de compra, en la sede de Commerce, vaya a **Adquisiciones y abastecimiento** > **Configuración** > **Parámetros de adquisición y abastecimiento**. En la pestaña **Entrega**, active el parámetro **Aceptar entrega deficiente**. A continuación, ejecute el trabajo de programación de distribución **1070** (**Configuración global**) para sincronizar los cambios de configuración en los canales.

Los porcentajes de tolerancia de suministro incompleto para una línea de pedido de compra pueden predefinirse en productos como parte de la configuración de producto en Commerce Headquarters. Alternativamente, se pueden establecer o sobrescribir en un pedido de compra específico en Commerce Headquarters.

Después de que una organización haya terminado las configuraciones de la entrega incompleta del pedido de compra, los usuarios del PDV verán una nueva opción **Cerrar la cantidad restante** en el panel **Detalles** cuando se selecciona una línea de pedido de compra entrante en la operación **Inventario entrante**. Si el usuario cierra la cantidad restante, el PDV realiza una validación para verificar si la cantidad que se cierra está dentro del porcentaje de tolerancia de porcentaje de entrega incompleta que se define en la línea de pedido de compra. Si se excede la tolerancia de entrega insuficiente, se muestra un mensaje de error y el usuario no podrá cerrar la cantidad restante hasta que la cantidad recibida anteriormente más la cantidad de **Recibiendo ahora** alcance o exceda la cantidad mínima que debe recibirse en función del porcentaje de tolerancia de entrega insuficiente. 

Con la opción **Cerrar cantidad restante** activada para una línea de orden de compra, cuando el usuario completa el recibo usando la acción **Terminar de recibir**, también se envía una solicitud de cierre a Commerce Headquarters, y se cancelará cualquier cantidad no recibida de esta línea de pedido. En ese momento, la línea se considera completamente recibida. 

### <a name="receiving-location-controlled-items"></a>Recepción de artículos controlados por ubicación

Si los artículos que se reciben están controlados por ubicación, los usuarios pueden seleccionar la ubicación donde quieren recibir los artículos durante el proceso de recepción. Le recomendamos que configure una ubicación de recepción predeterminada para el almacén de su tienda, para que este proceso sea más eficiente. Incluso si se configura una ubicación predeterminada, los usuarios pueden anular la ubicación de recepción en las líneas seleccionadas según lo requieran.

La operación respeta la configuración **Recibo en blanco permitido** en la dimensión de almacenamiento **Ubicación** y no requiere que se introduzca una dimensión de ubicación si se configura un recibo en blanco. Si no se permiten ubicaciones de recibos en blanco para un artículo, la aplicación PDV muestra un error y requiere que se introduzca una ubicación antes de que se pueda publicar el recibo.

### <a name="receive-all"></a>Recibir todo

Según lo requiera, puede seleccionar **Recibir todo** en la barra de la aplicación para actualizar rápidamente la cantidad **Recibiendo ahora** para todas las líneas del documento hasta el valor máximo que está disponible para recibir con esas líneas.

### <a name="receipt-of-unplanned-items-on-purchase-orders"></a>Recepción de artículos no planificados en pedidos de compra

En Commerce, versión 10.0.14 y posteriores, los usuarios pueden recibir un producto que no estaba originalmente en el pedido de compra. Esta función solo funciona para recibir pedidos de compra. No es posible recibir artículos contra pedidos de transferencia cuando los artículos no fueron pedidos y enviados previamente desde el almacén de salida.

Los usuarios no pueden agregar nuevos productos al pedido de compra durante la recepción de PDV si el pedido de compra [flujo de trabajo de gestión de cambios](../supply-chain/procurement/purchase-order-approval-confirmation.md) está habilitado en la sede de Commerce (HQ). Para habilitar la gestión de cambios, todos los cambios de un pedido de compra deben aprobarse antes de permitir la recepción. Debido a que este proceso permite que un receptor agregue nuevas líneas al pedido de compra, la recepción fallará si el flujo de trabajo de administración de cambios está habilitado. Si la gestión de cambios está habilitada para todos los pedidos de compra o para el proveedor vinculado a la orden de compra que se recibe activamente en PDV, el usuario no puede agregar nuevos productos al pedido de compra durante la recepción en PDV.

La funcionalidad que permite agregar líneas no se puede utilizar como una solución para recibir cantidades adicionales de productos que ya están en el pedido de compra. La sobrerecepción se gestiona mediante la configuración estándar de [sobrerecepción](#over-receiving-validations) para la línea de producto en el pedido de compra.

Cuando un usuario está recibiendo con la **Operación entrante** en el PDV, si el usuario escanea o teclea un código de barras de producto o un número de producto que se reconoce como un artículo válido pero no se reconoce como un artículo en el pedido de compra actual, el usuario recibe un mensaje que le pide que agregue el artículo al pedido de compra. Si el usuario agrega el artículo al pedido de compra, la cantidad introducida en **Recibiendo ahora** se considera la cantidad solicitada para la línea del pedido de compra.

Cuando el recibo del pedido de compra está completo y se envía a la sede para su procesamiento, las líneas agregadas se crean en el documento maestro del pedido de compra. En la línea del pedido de compra en la sede, habrá un indicador **Agregado mediante PDV** en la pestaña **General** del pedido de la orden de compra. El indicador **Agregado mediante PDV** indica que la línea del pedido de compra se agregó mediante el proceso de recepción de PDV y no era una línea que estaba en el pedido de compra antes de recibirlo.

### <a name="cancel-receiving"></a>Cancelar recepción

Debería usar la función **Cancelar recepción** en la barra de la aplicación solo si desea salir del documento y no desea guardar ningún cambio. Por ejemplo, inicialmente seleccionó el documento incorrecto y no desea guardar ninguno de los datos de recepción anteriores.

### <a name="pause-receiving"></a>Pausar recepción

Si está recibiendo inventario, puede usar la función **Pausar recepción** si desea hacer un descanso en el proceso de recepción. Por ejemplo, es posible que desee realizar otra operación desde el PDV, como cancelar la venta de un cliente o retrasar la publicación del recibo.

Cuando selecciona **Pausar recepción**, el estado del documento cambia a **Pausado**. Por lo tanto, el usuario sabrá que los datos se han introducido para el documento, pero el documento aún no se ha confirmado. Cuando esté listo para reanudar el proceso de recepción, seleccione el documento en pausa y luego seleccione **Detalles del pedido**. Cualquier cantidad de **Recibiendo ahora** que se guardaron previamente se conservarán y se pueden ver desde la vista **Lista completa de pedidos**.

### <a name="review"></a>Revisar

Antes del compromiso final de la recepción para la Central de Commerce (HQ), puede usar la funcionalidad de revisión para validar el documento entrante. La revisión lo alertará sobre los datos que falte o sean incorrectos que puedan causar una error en el procesamiento y le brindará la oportunidad de corregir problemas antes de enviar la solicitud de recepción. Para habilitar la función **Revisión** en la barra de aplicaciones, habilite la característica **Habilitar validación en las operaciones de inventario de entrada y salida del PDV** a través del espacio de trabajo **Administración de características** en la Central de Commerce (HQ).

La función **Revisión** valida los siguientes problemas en un documento entrante:

- **Recepción en exceso**: la cantidad de recepción en un momento determinado es mayor que la cantidad pedida. La gravedad de este problema está determinada por la configuración de sobreentrega en la Central de Commerce (HQ).
- **Recepción en defecto**: la cantidad de recepción en un momento determinado es menor que la cantidad pedida. La gravedad de este problema está determinada por la configuración de entrega en defecto en la Central de Commerce (HQ).
- **Número de serie**: el número de serie no se proporciona o valida para un artículo serializado que requiere que el número de serie se registre en el inventario.
- **Ubicación no establecida**: la ubicación no se especifica para un elemento controlado por ubicación donde no se permite la ubicación en blanco.
- **Líneas eliminadas**: el pedido tiene líneas eliminadas por un usuario de la Central de Commerce (HQ) que la aplicación de PDV no conoce.

Seleccione el parámetro **Habilitar validación automática** en **Sí** en **Parámetros de Commerce** > **Inventario** > **Almacenar inventario** para ejecutar la validación automáticamente cuando se selecciona **Terminar de recibir**.

### <a name="finish-receiving"></a>Finalizar la recepción

Cuando haya terminado de introducir todas las cantidades de **Recibiendo ahora** para productos, debe seleccionar **Terminar recepción** en la barra de aplicaciones para procesar el recibo.

Cuando los usuarios completan un recibo de pedido de compra, se les solicita que introduzcan un valor en el campo **Número de recibo**, si esta funcionalidad está configurada. Normalmente, este valor es equivalente al identificador del albarán del proveedor. Los datos del **Número de recibo** se almacenarán en el diario de recepción de productos en Commerce Headquarters. Los números de recibo no se capturan para los recibos de órdenes de transferencia.

Cuando se utiliza el procesamiento de documentos asíncrono, el recibo se envía a través de un marco de documentos asíncrono. El tiempo que lleva publicar el documento depende del tamaño del documento (el número de líneas) y el tráfico de procesamiento general que se produce en el servidor. Por lo general, este proceso ocurre en cuestión de segundos. Si la publicación de documentos falla, se notifica al usuario a través de la lista del documento **Operación de entrada**, donde el estado del documento se actualizará a **Procesamiento fallido**. El usuario puede seleccionar el documento fallido en PDV para ver los mensajes de error y la razón de la falla en el panel **Detalles**. Un documento fallido permanece sin publicar y requiere que el usuario regrese a las líneas del documento seleccionando **Detalles del pedido** en PDV. El usuario debe actualizar el documento con correcciones, en función de los errores. Después de corregir un documento, el usuario puede intentar procesarlo de nuevo seleccionando **Terminar cumplimiento** en la barra de aplicaciones.

## <a name="create-an-inbound-transfer-order"></a>Crear un pedido de transferencia entrante

Desde PDV, los usuarios pueden crear nuevos documentos de orden de transferencia. Para comenzar el proceso, seleccione **Nuevo** en la barra de aplicaciones mientras está en la lista de documento principal **Operación de entrada**. Luego se le pedirá que seleccione un almacén o tienda para **Transferir de** que proporcionará el inventario a la ubicación de su tienda. Los valores se limitan a la selección que se define en la configuración del grupo de cumplimiento de la tienda. En una solicitud de transferencia entrante, su tienda actual siempre será el almacén **Transferir a** para la orden de transferencia. No se puede cambiar el valor.

Puede introducir valores en los campos **Fecha de envío**, **Fecha de recepción** y **Modo de entrega** según lo requiera. También puede agregar una nota que se almacenará junto con el encabezado de la orden de transferencia, como un archivo adjunto al documento en la sede de Commerce.

Después de crear la información del encabezado, puede agregar productos a la orden de transferencia. Para comenzar el proceso de agregar artículos y cantidades solicitadas, seleccione **Agregar Producto**. En el panel **Detalles**, también puede agregar una nota específica de línea a las líneas del diario. Estas notas se almacenarán como un archivo adjunto de línea.

Tras introducir las líneas en la orden de transferencia de entrada, debe seleccionar **Guardar** para guardar los cambios del documento localmente o **Enviar petición** para enviar los detalles del pedido a la sede de Commerce para su posterior procesamiento. Si selecciona **Guardar**, el borrador del documento se almacena en la base de datos del canal y el almacén de salida no puede ejecutar el documento hasta que se haya procesado correctamente a través de **Enviar petición**. Debería seleccionar **Guardar** solo si no está listo para enviar la solicitud a la sede de Commerce para su procesamiento.

Si un documento se guarda localmente, se puede encontrar en la pestaña **Borradores** de la lista de documentos **Operación entrante**. Mientras un documento está en el estado **Borrador**, puede editarlo seleccionando **Editar**. Puede actualizar, agregar o eliminar líneas según lo requiera. También puede eliminar todo el documento mientras está en el estado **Borrador** estado, seleccionando **Eliminar** en la pestaña **Borradores**.

Después de que el borrador del documento se envíe con éxito a la sede de Commerce, aparecerá en la pestaña **Activo** y tiene un estado de **Solicitado**. En este punto, los usuarios en la tienda o almacén entrante ya no pueden editar el documento de pedido de transferencia entrante solicitado. Solo los usuarios del almacén de salida pueden editar el documento seleccionando **Operación de salida** en la aplicación PDV. El bloqueo de edición asegura que no ocurran conflictos porque un solicitante entrante cambia la orden de transferencia al mismo tiempo que el remitente saliente está recogiendo y enviando la orden de forma activa. Si se requieren cambios en la tienda o almacén de entrada después de que se haya enviado la orden de transferencia, se debe contactar al remitente de salida y solicitarle que introduzca los cambios.

Después de que el documento esté en el estado **Pedido**, es visible en la pestaña **Activo**. Sin embargo, aún no puede ser recibido por la tienda entrante o el almacén. Después de que el almacén de salida ha enviado parte o la totalidad de la orden de transferencia, la tienda o almacén de entrada puede registrar recibos en PDV. Cuando la parte de salida procesa los documentos de orden de transferencia, su estado se actualiza de **Solicitado** a **Enviado** o **Parcialmente enviado**. Después de que los documentos estén en el estado **Enviado** o **Parcialmente Enviado**, la tienda entrante o el almacén pueden contabilizar recibos contra ellos mediante el proceso de recepción de operaciones entrantes.

## <a name="related-articles"></a>Artículos relacionados

[Operación de inventario saliente en PDV](pos-outbound-inventory-operation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
