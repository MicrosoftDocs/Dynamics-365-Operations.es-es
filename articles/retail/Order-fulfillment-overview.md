---
title: Cumplimiento de pedido de almacén
description: Este tema proporciona una visión general del cumplimiento de los pedidos de almacén.
author: rubencdelgado
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: rubencdelgado
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3b66369e57e006c9e2fe0a43e4b781c619a65c4a
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "2025872"
---
# <a name="store-order-fulfillment"></a>Cumplimiento de pedido de almacén

[!include [banner](includes/banner.md)]

Muchos minoristas quisieran optimizar el cumplimiento de pedidos habilitando almacenes para atender pedidos. El cumplimiento de pedidos a nivel del almacén puede facilitar las escenarios de sobreabastecimiento para un almacén específico, o puede ser necesario desde un punto de vista logístico en caso de que tenga un almacén de capacidad adicional o se encuentre dentro de una distancia más cercana de envío al cliente. Para dirigir esta necesidad, una operación unificada de cumplimiento de pedido está disponible en el punto de venta.

Los pedidos para el cumplimiento en un almacén específico tienen el almacén de tienda designado en la cabecera o líneas del pedido.

La operación de cumplimiento en el punto de venta ofrece una sola área de trabajo en el punto de venta que se puede usar para procesar pedidos. Esto incluye todo, desde aceptar el pedido, a marcarlo como enviado o iniciar la recogida del almacén.

## <a name="access-unified-order-fulfillment-in-the-point-of-sale"></a>Acceso al cumplimiento unificado de pedido en el punto de venta

El cumplimiento de pedido, [Operación ID 928](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-operations), puede usarse para tener acceso al área de trabajo de cumplimiento de pedido del almacén en el punto de venta.

La operación de cumplimiento de pedido no tiene su propio permiso listo para usar, pero en el futuro, los usuarios podrán utilizar el permiso **Permitir recuperar pedido** para invocar la operación desde el punto de venta.

A nivel de almacén, una opción de configuración está disponible para determinar si una línea de pedido se debe aceptar manualmente desde el punto de venta. Si dicha opción de configuración no se establece, las líneas de pedido serán aceptadas de forma predeterminada. Si está activada dicha opción de configuración, los usuarios en el punto de venta necesitarán seleccionar el permiso **Permitir aceptar pedido** para aceptar pedidos en el punto de venta.

Las líneas de pedido también se pueden rechazar desde el punto de venta. Rechazar una línea de pedido significa que no se completará en dicho almacén y envía de nuevo la línea de pedido para la reasignación a otro almacén. El permiso de rechazo de la línea de pedido se concede con el permiso **Permitir el rechazo del pedido**.

## <a name="order-fulfillment-operation-parameters"></a>Parámetros de la operación de cumplimiento de pedido

El cumplimiento de pedido proporciona parámetros listos para usar que se pueden aplicar a la operación cuando se llama en el punto de venta. Cuando se configura el parámetro **Todos los pedidos** , se muestran todos los pedidos cuando se usa la operación. El parámetro **Pedidos para enviar** sólo muestra los pedidos que se deben enviar desde el almacén y los **Pedidos para recogida** muestra pedidos que van a ser recogidos del almacén.

## <a name="orders-for-fulfillment"></a>Pedidos para cumplimiento

La operación de cumplimiento de pedidos muestra sólo los pedidos que van a ser recogidos o enviados desde el almacén actual. Los pedidos para otros almacenes no aparecen en la lista cuando se utiliza la operación de cumplimiento.

## <a name="line-selection"></a>Selección de línea

Las líneas se pueden seleccionar mediante la función **Seleccionar** en el panel de acciones. Cuando se habilita **Seleccionar**, varias líneas se pueden seleccionar para procesar. Puede eliminar las líneas seleccionadas haciendo clic de nuevo en la misma línea.

## <a name="line-details"></a>Detalles de línea

Los detalles de la línea se pueden mostrar mediante los detalles de la línea del menú flotante. Cuando se usa este menú, se proporcionan tres pestañas para mostrar información adicional para la línea seleccionada. La primera pestaña, **Detalles de la línea** muestra los detalles para la propia línea, como cantidad pedida y restante. Se proporcionan detalles adicionales, incluida la cantidad seleccionada, empaquetado y facturado, así como el modo y la dirección de entrega. La pestaña **Detalles de pedido** proporciona la información del encabezado del pedido del cliente, incluidos el identificador del cliente, el número de pedido, el total de pedido, y el balance. La pestaña **Inventario** muestra información de la línea seleccionada en cuanto a inventario disponible físico, inventario reservado e inventario pedido.

Si se seleccionan varias líneas, el menú flotante de los detalles de la línea del pedido sólo indicará que varias líneas están seleccionadas. Para mostrar los detalles para una única línea, desactive líneas hasta que quede sólo una.

## <a name="pending-order-lines"></a>Líneas de pedido pendientes

El cumplimiento unificado del pedido incluye la capacidad de aceptar pedidos manualmente. De forma predeterminada, los pedidos para el cumplimiento en el almacén ya están aceptados. Sin embargo, si los procesos de negocio dictan que un trabajador en el nivel del almacén debe aceptar pedidos, la aceptación manual se puede cambiar a un nivel de almacén minorista. Para habilitar la aceptación de pedido, vaya a **Retail** \> **Canales** \> **Almacenes al por menor** \> **Todos los almacenes al por menor**. Abra el almacén deseado y, en la pestaña **General**, ubique el encabezado secundario **Cumplimiento del pedido**. Este encabezado secundario tiene una opción **Aceptación manual** que está establecida en **No** de forma predeterminada. Al establecer esta opción en **Sí** y sincronizando los cambios en la base de datos del canal, las líneas de pedido pueden pasar por el proceso de aceptación.

Los trabajadores con el permiso **Permitir aceptación de pedido** pueden abrir cumplimiento de pedidos y seleccionar las líneas para la aceptación. Una vez que se hayan aceptado las líneas, cambian el estado de **Pendiente** a **Aceptado** y el resto del proceso de cumplimiento pueden puede continuar. Cuando está activado la **Aceptación manual**, los pedidos no serán procesadas hasta que se hayan aceptado.

Los pedidos para la recogida en almacén nunca tienen el estado **Pendiente**. Esto se hace para evitar un escenario en el que un cliente llegue al almacén y la línea de pedido no se pueda procesar porque un trabajador con el privilegio adecuado no esté disponible.

## <a name="accepted-order-lines"></a>Líneas de pedido aceptadas

Los pedidos con el estado **Aceptado** de la línea pueden continuar con el resto del proceso de cumplimiento de pedido en el punto de venta. Una vez aceptado un pedido, cualquier acción restante se puede realizar contra la línea de pedido.

Por ejemplo, una línea de pedido aceptada puede ser seleccionada y a continuación recogida directamente sin tener que pasar por el proceso de selección y de embalaje.

## <a name="line-actions"></a>Acciones de línea

### <a name="pick"></a>Seleccionar

La categoría de acciones **Seleccionar** se ofrece para ayudar en el proceso de selección de líneas de pedido de las estanterías. La acción de selección sólo se puede realizar en las líneas de pedido que se han aceptado anteriormente.

**Acción: Selección**

- **Estado resultante de PDV**: Seleccionado
- **Estado resultante de back-office:** Ningún cambio

Una vez aceptado un pedido, las líneas se pueden seleccionar y marcar como **Seleccionado**. Marcar una línea como **Seleccionado** es una forma de indicar que el trabajo de selección se está realizando ya en una línea. Esto impide que intenten dos trabajadores seleccionar las mismas líneas de pedido al mismo tiempo.

**Acción: Imprimir lista de selección**

- **Estado resultante**: Seleccionado
- **Estado resultante de back-office:** Ningún cambio

Las listas de selección se pueden imprimir en el punto de venta para ayudar a los trabajadores a realizar el proceso de selección. Una lista de selección impresa se puede llevar con el trabajador que realiza la selección y según se seleccionan los productos, el trabajador las marcaría manualmente como seleccionado en la lista de selección.

El formato de lista de selección se configura en Retail y se agrega al perfil de recibo. Para obtener más información sobre la configuración de perfiles de recibo, consulte [Plantillas e impresión de recibos](https://docs.microsoft.com/dynamics365/unified-operations/retail/receipt-templates-printing).

Si se seleccionan las líneas y se imprime una lista de selección para esas líneas, se actualizan automáticamente con el estado **Seleccionado**.

**Acción: Marcar como seleccionado**

- **Estado resultante:** Seleccionado o seleccionado parcialmente
- **Estado back-office resultante:** Seleccionado o seleccionado parcialmente

Una vez que se haya efectuado el proceso físico de selección, las líneas se pueden marcar como **Seleccionado**. Al seleccionar una línea y marcarla como **Seleccionada** realiza una llamada en tiempo real para actualizar la línea de pedido. Una vez que la línea se haya marcado como **Seleccionado** en el punto de venta, se actualizará el estado en back-office también como **Seleccionado** y las transacciones de inventario reflejarán que se ha disminuido la cantidad especificada.

Cuando los pedidos se procesan en el tiempo, las cantidades parciales se pueden procesar para una línea específica. Si se selecciona una línea y se realiza la acción **Marcar como seleccionado** y la cantidad es mayor que uno, se le pedirá al usuario la cantidad. La cantidad restante a seleccionar se rellena automáticamente. Si se especifica una cantidad inferior a la restante, el estado de la línea se cambia a **Seleccionado parcialmente**. Cuando la línea de pedido se actualiza en back-office, reflejará también el estado parcialmente seleccionado y la cantidad especificada por el usuario se usa para la actualización de inventario.

Si una línea de pedido se selecciona por error, el proceso de deshacer se debe realizar en la línea de pedido en back-office. No existen actualmente ninguna acción de deshacer en el punto de venta.

Las líneas de pedido de diferentes pedidos se pueden seleccionar y marcar como **Seleccionado**, imprimir en la misma lista de selección, o marcar como **Seleccionado**.

### <a name="pack"></a>Paquete

Las líneas de pedido se pueden empaquetar en cualquier momento después de que se haya aceptado la línea de pedido.

**Acción: Imprimir el albarán**

- **Estado resultante:** Empaquetado o empaquetado parcialmente
- **Estado back-office resultante:** Entregado o entregado parcialmente

Esta acción marca las líneas como empaquetadas o empaquetadas parcialmente e imprime un albarán. Un albarán se puede imprimir para validar los productos que se han empaquetado conjuntamente. El formato del albarán se configura en Retail y se agrega al perfil de recibo. Para obtener más información sobre la configuración de perfiles de recibo, consulte [Plantillas e impresión de recibos](https://docs.microsoft.com/dynamics365/unified-operations/retail/receipt-templates-printing).

**Acción: Marcar como empaquetado**

- **Estado resultante:** Empaquetado o empaquetado parcialmente
- **Estado back-office resultante:** Entregado o entregado parcialmente

La acción **Marcar como empaquetado** se puede usar para indicar que las líneas están empaquetadas sin imprimir un albarán. **Imprimir albarán** Y **Marcar como empaquetado** originan transacciones de inventario en back-office. Las líneas de embalaje en el punto de venta darán lugar a los diarios de albaranes que se están produciendo en back-office.

Si una línea de pedido se empaqueta por error, el diario de albaranes se debe corregir en back-office.

Sólo las líneas en el mismo pedido y con el mismo modo de entrega se pueden empaquetar al mismo tiempo.

Actualmente, la opción para marcar la recogida líneas de almacén como **Empaquetado** está deshabilita. Esta capacidad se agregará en una versión futura. El proceso de creación del albarán se ampliará para admitir la inyección de la información de envío de terceros en el proceso de albarán.

### <a name="pick-up"></a>Elegir

Los pedidos para la recogida de almacén se pueden seleccionar directamente una vez que se recuperan en el punto de venta. Los pedidos seleccionados del almacén no están sujetos a aceptación.

**Acción: Recogida**

- **Estado resultante:** Facturado o facturado parcialmente
- **Estado back-office resultante:** Facturado o facturado parcialmente

Si una línea se selecciona para recogida desde cumplimiento unificado del pedido, el pedido completo se carga en el punto de venta y la cantidad total para la línea seleccionada se marca. Otras líneas del pedido también se cargan en la vista de transacción del punto de venta, pero con la cantidad marcada como cero.

Una vez que las líneas para la recogida se hayan cargado en la vista de transacción, la transacción se puede realizar como de costumbre.

Las líneas que se han facturado completamente a través de la recogida no aparecerán en el procesamiento del pedido unificado. Las líneas que han sido recogidas parcialmente seguirán apareciendo en el cumplimiento unificado del pedido hasta que se hayan recogido completamente.

Si una línea se recoge en error, se debe realizar una devolución para corregir el error.

Sólo las líneas en el mismo pedido y con el mismo modo de entrega se pueden recoger al mismo tiempo.

### <a name="shipping"></a>Envío

Las líneas de pedido para enviar desde el almacén se pueden procesar con el cumplimiento unificado de pedido mediante la acción **Enviar**. Si la aceptación manual de la línea de pedido se configura en el nivel del canal, los pedidos se deben aceptar antes del envío. Una vez que una línea de pedido se haya aceptado y tenga el estado **Pendiente** u otro estado, las líneas se pueden enviar.

**Acción: Envío**

- **Estado resultante:** Facturado o facturado parcialmente
- **Estado back-office resultante:** Facturado o facturado parcialmente

Las líneas registradas de cumplimiento unificado del pedido se facturan desde back-office al igual que si el pedido se factura directamente desde back-office. Las líneas que se envían desde cumplimiento unificado del pedido no se cargan en la vista de transacción y no se realiza ningún ofrecimiento cuando se envían las líneas.

Las líneas de pedido que se han enviado completamente no aparecen más en el cumplimiento unificado del pedido. Las líneas que han sido enviadas parcialmente seguirán apareciendo en el cumplimiento unificado del pedido hasta que se hayan enviado completamente.

Sólo las líneas del mismo pedido se pueden enviar al mismo tiempo. Si las líneas del mismo pedido tienen distintos modos de entregar, aún se pueden seleccionar para enviarse al mismo tiempo.

### <a name="reject"></a>Rechazar

Las líneas o las líneas parciales se pueden rechazar. Esto permite que se reasignen desde back-office a otro almacén. Las líneas solo se pueden rechazar si aún no se han seleccionado ni empaquetado. Para rechazar una línea que ya se ha seleccionado o se ha empaquetado, dicha línea se debe quitar o desempaquetar desde back-office.

**Acción: Rechazar**

- **Estado resultante:** Rechazado
- **Estado resultante de back-office:** Ningún cambio

Las líneas de pedido rechazadas se pueden ver en el área de trabajo **Procesamiento y consulta de pedido de ventas**. Borrar el filtro de la persona en el área de trabajo para ver todas las líneas de pedido rechazadas a través de los almacenes. La pestaña **Líneas de pedido rechazadas** en la sección **Pedidos y favoritos** muestra los detalles de la línea de pedido. Además, los usuarios pueden hacer clic en el botón **Líneas de pedido rechazadas** en la sección **Resumen** para navegar a una vista de pedido de ventas. Esto muestra todos los pedidos que tengan una o más líneas de pedido rechazadas. Si se habilita la administración distribuida del pedido (DOM), esos pedidos rechazados se reasignan automáticamente a los almacenes apropiados para el cumplimiento, sin embargo, estas líneas de pedido pueden asignarse manualmente también. Para ello, seleccione la línea que muestra el **Estado de cumplimiento** como **Rechazado** y modifique el sitio/almacén según sea necesario. Haga clic en el menú **Actualizar líneas** y haga click en **Restablecer estado de cumplimiento** para cambiar el estado de cumplimiento de **Rechazado** **Aceptado** o **Pendiente**, en función de la configuración de cumplimiento. Una vez que restablezca el estado de cumplimiento, los trabajadores del almacén podrán ver las líneas de pedido en PDV.

## <a name="line-quantity-tracking"></a>Seguimiento de la cantidad de las líneas

Una única línea de pedido de cantidad mayor que uno se puede procesar en el tiempo, resultando en múltiples subestados para las líneas de pedido. Por ejemplo, si un creador tiene un proyecto que requería 500 tablas, pero sólo selecionará o enviará unas cuantas al mismo tiempo durante todo el proyecto, podría haber cantidades que se seleccionen, empaqueten y se envíen al mismo tiempo.

Cada vez que se selecciona una línea, la cantidad restante de la línea se rellenará automáticamente para asumir que se está procesando la cantidad restante. Usando el ejemplo anterior, si se han seleccionado 200 tablas y la línea para las tablas está seleccionada, la cantidad restante de 300 se rellenará automáticamente en la cantidad. Lo mismo ocurre si se han facturado 200 tablas. En ese caso, sólo la cantidad restante se rellenará automáticamente.

Si se sigue el ejemplo anterior, si marcan 200 tablas como empaquetadas y se selecciona el envío, la cantidad completa de 500 se rellenará automáticamente. Si registran solo 200 tablas, el sistema asumirá que las tablas empaquetadas anteriormente se están enviando y la cantidad empaquetada disminuirá. Si se envían 201 tablas, disminuye primero la cantidad de tablas empaquetadas con la tabla restante que es disminuida de la cantidad restante.

## <a name="line-statuses"></a>Estados de las líneas

Las líneas de pedido en el punto de venta tienen varios estados para reflejar el estado de la línea de pedido. Los estados en el punto de venta y en back-office no coinciden en todos los casos. El estado de la línea de pedido se puede visualizar a través del punto de venta mediante las operaciones de cumplimiento de pedido. En el back-office, las líneas de pedido se pueden ver desde los detalles del pedido. Se puede acceder a los detalles del pedido a través de **Retail** \> **Clientes** \> **Todos los pedidos de cliente**. Seleccione **Identificador de pedido** para ver los detalles del pedido. Desde los detalles de pedido seleccione la pestaña **Pedido de ventas**, a continuación seleccione **Estado detallado** bajo el subtítulo **Ver**.

- Las líneas de pedido**Pendiente** que se han asignado a un almacén, pero aún no se han aceptado tienen el estado **Pendiente** cuando se visualizan en el punto de venta. Las líneas pendientes de aceptación en el punto de venta tendrán el estado **Procesamiento de pedido** en back-office.
- Las líneas de pedido**Aceptado** que se han aceptado manual o automáticamente tendrán el estado **Aceptado** cuando se visualicen en el punto de venta. Las líneas con el estado **Aceptado** se muestren como **Procesamiento de pedido** en back-office.
- Las líneas **Seleccionado** que se están seleccionando actualmente a nivel del almacén tienen el estado **Seleccionado**. Estas mismas líneas, cuando se ven en back office, se muestren como **Procesamiento de pedido**.
- **Seleccionado** y **Seleccionado parcialmente** Las líneas que se han seleccionado o se hayan seleccionado parcialmente en el punto de venta tendrán el estado **Seleccionado** o **Seleccionado parcialmente**. Las mismas líneas en back-office se muestren también como **Seleccionado** o **Seleccionado parcialmente**.
- **Empaquetado** y **Empaquetado parcialmente** Las líneas que se han empaquetado o se hayan empaquetado parcialmente en el punto de venta tendrán el estado **Empaquetado** o **Empaquetado parcialmente**. Las mismas líneas en back-office se muestren también como **Enviado** o **Enviado parcialmente**.
- **Facturado parcialmente** Las líneas que se han recogido parcialmente o se han enviado parcialmente tendrán el estado **Facturado parcialmente** en el punto de venta y en back-office.
- **Facturado** Las líneas que se han facturado completamente en el punto de venta no aparecerán más para cumplimiento. En back-office el estado de estas líneas es **Facturado**.

## <a name="order-fulfillment-filtering"></a>Filtrado de cumplimiento de pedido

El cumplimiento de pedido en el punto de venta incluye un filtrado para ayudar al usuario a buscar fácilmente lo que necesite. Los filtros se pueden cambiar a través del panel de acciones de la parte inferior de la pantalla de **Punto de venta**. De forma predeterminada, un filtro **Tipo de entrega** se aplica, en función de cómo se haya configurado la operación. Si la operación está configurada con el parámetro **Todos los pedidos**, se aplica dicho filtro al acceder al cumplimiento de pedido. Lo mismo aplica a los parámetros **Recogida de almacén** y **Envío desde almacén**. Otros filtros que se pueden aplicar a la vista de cumplimiento de pedido incluye:

- Número de cliente
- Nombre de cliente
- Correo electrónico del cliente
- Número de pedido
- Modo de entrega
- Número de recibo
- Id. de referencia del canal
- Número de tienda de origen
- Estado de línea
- Fecha de creación
- Fecha de entrega
- Fecha de recepción
