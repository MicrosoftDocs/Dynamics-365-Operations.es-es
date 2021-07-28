---
title: Manejo de almacén de cargas entrantes para pedidos de compra
description: Este tema describe el proceso de manejo de almacén para cargas entrantes para pedidos de compra.
author: omulvad
ms.date: 03/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadTable, WHSLoadPlanningListPage, WHSLoadPlanningWorkbench, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-21
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: e0b0eb1466d962fb04566b936322db1e4c28f830
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6359796"
---
# <a name="warehouse-handling-of-inbound-loads-for-purchase-orders"></a>Manejo de almacén de cargas entrantes para pedidos de compra

Este tema describe el proceso de manejo de almacén para cargas entrantes para pedidos de compra.

Para cada carga entrante, su sistema ya debe incluir un pedido de ventas relacionado y también puede contener una especificación de carga relacionada y / o un plan de transporte. Para obtener más información sobre cómo crear y administrar cargas entrantes, vea [Proceso empresarial: planificación del transporte para cargas entrantes](/dynamicsax-2012/appuser-itpro/business-process-planning-transportation-for-inbound-loads).

## <a name="overview-how-inbound-loads-are-created-registered-and-received"></a>Descripción general: cómo se crean, registran y reciben las cargas entrantes

La siguiente ilustración muestra el flujo típico para manejar cargas entrantes que tienen cantidades de pedidos de compra cuando llegan a su almacén.

![El proceso de manejo de carga entrante.](media/inbound-process.png "El proceso de manejo de carga entrante")

1. **El proveedor confirma el pedido de compra.**

    El proceso comienza cuando se introduce un pedido de compra en el sistema y luego se entrega a un proveedor, que lo confirma. El pedido de compra debe existir antes de que pueda crear un registro de carga entrante. Sin embargo, puede crear la carga entrante incluso si el pedido no ha sido confirmado. Para obtener más información consulte [Aprobar y confirmar pedidos de compra](../procurement/purchase-order-approval-confirmation.md).

1. **Se crea un registro de carga entrante para planificar la llegada y su contenido.**

    El registro de carga entrante representa un envío de proveedor de uno o más pedidos de compra. Se espera que la carga llegue al almacén como una unidad de transporte física (como una carga de camión). El registro de carga entrante se utiliza con fines de planificación y permite al coordinador de logística realizar un seguimiento del progreso de la carga del proveedor. También se utiliza para registrar cantidades de línea de pedido y administrar el progreso a través de las operaciones de almacén, como el trabajo de llegada y su guardado. Las cargas se pueden crear de forma automática o manual y se pueden basar en un pedido de compra o en un aviso de envío avanzado (ASN) del proveedor. Para más información, consulte [Crear o modificar una carga entrante](/dynamicsax-2012/appuser-itpro/create-or-modify-an-inbound-load).

1. **El proveedor confirma el despacho de carga.**

    Cuando el proveedor despacha la carga, el coordinador de logística en el almacén receptor confirma el envío de la carga. Si la empresa receptora está utilizando el módulo **Gestión del transporte**, la confirmación del envío entrante activará otros procesos de gestión de carga que están asociados con las cargas entrantes. Para más información, consulte [Confirmar una carga para envío](/dynamicsax-2012/appuser-itpro/confirm-a-load-for-shipping).

1. **La carga llega al almacén y los trabajadores registran cantidades.**

    Cuando un camión llega al muelle de recepción del almacén, los trabajadores del almacén registran las cantidades de carga. Cuando se usa el módulo **Gestión de almacenes**, los trabajadores hacen el registro mediante dispositivos móviles. Para más información, ver [Recepción de producto contra pedidos de compra - registro](../procurement/product-receipt-against-purchase-orders.md#registration) y la sección [Registrar cantidades de artículos que llegan en una carga entrante](#register-item-quantities-arriving).

1. **Las cantidades de carga registradas se contabilizan en las órdenes de compra.**

    Después de que las cantidades de carga se hayan registrado como llegadas, esas cantidades deben ser recibidas en el producto, contabilizadas en el libro de inventario de la compañía para registrar el aumento de existencias físicas. Para más información, ver [Recibo de producto contra órdenes de compra - recibo de producto](../procurement/product-receipt-against-purchase-orders.md#product-receipt) y [Contabilice las cantidades de productos registrados en las órdenes de compra](#post-registered-quantities).

## <a name="register-item-quantities-that-arrive-on-an-inbound-load"></a><a name="register-item-quantities-arriving"></a>Registrar cantidades de artículos que llegan en una carga entrante

Microsoft Dynamics 365 Supply Chain Management admite varios enfoques operativos para registrar la llegada de los productos pedidos. Por lo tanto, puede configurar el sistema para que coincida con sus requisitos empresariales específicos. Esta sección describe cómo registrar las cantidades de artículos entrantes utilizando un dispositivo móvil cuando la gestión avanzada de almacenes está activada en el sistema. Sin embargo, existe un flujo alternativo que se basa en el uso del diario de llegada de artículos en lugar de un dispositivo móvil. Para más información sobre ese flujo, consulte [Registrar artículos para almacenamiento avanzado mediante un diario de recepción de artículos](tasks/register-items-advanced-warehousing.md).

Cuando una carga entrante llega por primera vez al almacén, los trabajadores del almacén deben registrar las cantidades de artículos que se incluyen en el envío. Por lo general, utilizan escáneres de mano. Este flujo de trabajo está disponible solo si los siguientes elementos están presentes en el sistema:

- **Un registro de carga entrante que describe las cantidades de artículos que se esperan en el envío**

    Por lo general, el proveedor confirma el registro de carga entrante antes de que el envío llegue al almacén. Por lo tanto, la carga tiene un estado de _Enviado_. Sin embargo, los trabajadores del almacén también pueden registrar cantidades de artículos para cargas que tienen un estado de _Abierto_ o _Recibido_.

- **Un menú de dispositivo móvil que está configurado para admitir la recepción de carga**

    La [aplicación móvil Warehouse Management](../warehousing/install-configure-warehouse-management-app.md) para dispositivos móviles es compatible con los siguientes procesos de creación de trabajo:

    - Recepción de artículo de carga
    - Recepción de artículo de carga y ubicación
    - Recepción de matrícula mixta, donde el campo **Método de identificación de línea del documento fuente** para el elemento de menú del dispositivo móvil se establece en _Carga de artículos recibidos_. Para más información, ver [Recepción de matrícula mixta](mixed-license-plate-receiving.md).
    - Recepción de matrícula mixta y ubicación, donde el campo **Método de identificación de línea del documento fuente** para el elemento de menú del dispositivo móvil se establece en _Carga de artículos recibidos_. Para más información, ver [Recepción de matrícula mixta](mixed-license-plate-receiving.md).

    > [!NOTE]
    > Independientemente del proceso, el sistema generará trabajo para tomar cantidades registradas en la ubicación de recepción y guardarlas en la ubicación de almacenamiento normal. Cuando se usa el proceso _Recepción y ubicación de carga de artículo_ o _Recepción y ubicación de matrícula de entidad mixta_, el trabajador que registró la cantidad de carga también será instruido por el dispositivo para hacer el trabajo de almacenamiento como parte de la tarea de registro. Por el contrario, para los procesos _Carga de artículos recibidos_ y _Recepción de matrícula mixta_, se supone que el trabajo de almacenamiento se realizará por separado de la tarea de registro.

- **Una plantilla de trabajo que define el trabajo de selección y colocación para las cargas entrantes**

    Este artículo está relacionado con los artículos anteriores. Debe tener al menos una plantilla de trabajo para el tipo de orden de trabajo _Pedido de compra_ y debe contener un conjunto de tipos de trabajo de selección / colocación.

El dispositivo móvil guía al empleado de recepción del almacén a través del flujo para el registro de la cantidad de carga. Como mínimo, este flujo incluye los siguientes pasos para cada Id. de carga:

1. Especifique el identificador de carga.
2. Introduzca una descripción para un artículo recibido.
3. Introduzca la cantidad de ese número de artículo que se recibe.
4. Introduzca la matrícula de entidad de almacén para la ubicación inicial del artículo, si el sistema no está configurado para generar este número automáticamente.
5. Pulse **Aceptar**.

Después de que el trabajador completa estos pasos, el sistema realiza las siguientes actualizaciones en las entidades apropiadas, siempre que la cantidad de la línea de orden de compra haya llegado en una carga y se hayan registrado todas las cantidades de carga:

| Entidad | Actualizaciones | Billete |
|---|---|---|
| Cargar | El campo **Cantidad de trabajo creada** en la línea de carga se actualiza para mostrar la cantidad registrada. | El valor **Estado de carga** permanece _Enviado_ o _Abierto_ si no se ha ejecutado la confirmación de envío para la carga. Si se ha iniciado al menos una línea de trabajo de almacenamiento, se cambia a _En proceso_. |
| Transacción de inventario de un pedido de compra para la que se han registrado cantidades de carga asociadas |<p>Los campos siguientes se actualizan:</p><ul><li>El campo <b>Recibo</b> se establece en <i>Registrado.</i></li><li>El campo <b>Ubicación</b> se actualiza con el código de ubicación del muelle receptor. (Este código se especifica en el campo <b>Ubicación de recibo predeterminada</b> para cada almacén).</li><li>El campo <b>Matrícula de entidad de almacén</b> se actualiza con el número de matrícula de entidad que se introdujo o generó durante el registro.</li><li>El campo <b>Id. de carga</b> se actualiza con el número de la carga con la que se ha registrado la cantidad. (Ver la nota.)</li></ul> | La capacidad de vincular entre la transacción de inventario de orden de compra y las cantidades que se registran contra la carga se introdujo en la versión 10.0.9 como una característica opcional que se denominó _Asociar transacciones de inventario de orden de compra con carga_. Esta característica es especialmente beneficiosa para los flujos operativos en los que un solo pedido de bienes comprados se entrega como múltiples cargas, o cuando una carga contiene cantidades para múltiples pedidos de compra. |
| Guardado en almacén | El trabajo se crea en base a una plantilla de trabajo, para indicarle al trabajador que mueva las cantidades registradas de la ubicación de recepción a una ubicación de almacenamiento normal. | La elección de la ubicación de almacenamiento está controlada por la directiva Ubicación de colocación. Si no se ha definido una directiva de ubicación, la ubicación de guardado en el trabajo está vacía. |

Tenga en cuenta que los trabajadores del almacén pueden registrar el recibo de un pedido de compra con una o más cargas asociadas sin utilizar el proceso _Carga de artículos recibidos_. Están disponibles los siguientes métodos:

- **En el dispositivo móvil:** use los procesos _Recepción de línea de pedido de compra_ y _Línea de pedido de compra que recibe y guarda_. (Si existe más de una carga para la cantidad de línea de orden de compra, el trabajador no puede usar el proceso _Recepción de línea de pedido de compra_. En cambio, se le indicará al trabajador que use la acción del dispositivo que está asociada con el proceso _Carga de artículos recibidos_.)
- **En el cliente:** use el diario de llegada de artículos.
- **En el cliente:** use la acción **Registro** a la que se puede acceder desde la línea de pedido de compra.

> [!NOTE]
> Si el recibo de la orden de compra se registra utilizando cualquiera de los métodos anteriores, no se crea ningún vínculo entre la transacción de inventario del pedido de compra y la carga, incluso cuando la función _Asociar transacciones de inventario de orden de compra con carga_ está activada. Una excepción a esta regla es cuando usa la opción **Recepción de línea de pedido de compra** y solo una carga tiene un estado distinto de _Recibido_ para la línea de orden.

### <a name="handle-discrepancies-during-registration-of-inbound-load-quantities"></a>Gestionar discrepancias durante el registro de cantidades de carga entrante

Los trabajadores del almacén pueden hacer un registro de recibo de cantidad de carga parcial. Cada recibo de cantidad de carga parcial crea una transacción de inventario separada que tiene un estado de recibo de _Registrado_ para la cantidad registrada, y el Id. del lote se refiere a la línea de orden de compra de origen.

#### <a name="load-under-receiving"></a>Carga por debajo de la recepción

Cuando llega una carga, si las cantidades de artículos son menores que las cantidades que se indican en el registro de carga, el personal de recepción del almacén puede trabajar directamente en el cliente para reconocer esta discrepancia al reducir la cantidad en la línea de carga para que coincida con la cantidad real que llegó y se registró.

#### <a name="load-over-receiving"></a><a name="load-over-receiving"></a>Carga por encima de la recepción

La sobre recepción ocurre cuando llega una carga y las cantidades de artículos exceden la cantidad de línea de carga esperada. Puede controlar si y en qué grado se permite la sobre recepción durante el registro de carga.

Use el campo **Sobre recepción de carga** para los elementos de menú relevantes del dispositivo móvil para controlar lo que ocurre cuando un trabajador del almacén intenta registrar una entrega excesiva. Este campo está disponible para los elementos de menú del dispositivo móvil que utilizan los siguientes tipos de procesos de creación de trabajo:

- Recepción de artículo de carga
- Recepción de artículo de carga y ubicación
- Recepción de matrícula mixta, (cuando el campo **Método de identificación de línea del documento fuente** se establece en _Carga de artículos recibidos_)
- Recepción de matrícula mixta y guardado, (cuando el campo **Método de identificación de línea del documento fuente** se establece en _Carga de artículos recibidos_)

En la siguiente tabla se explican las opciones disponibles para el campo **Sobre recepción de carga**.

| Valor | Descripción |
|---|---|
| Permitir | Los trabajadores pueden registrar el recibo de cantidades que exceden la cantidad no registrada restante para una carga seleccionada, pero solo si la cantidad registrada total no excede la cantidad de la línea de pedido de compra que está asociada con la carga (después del ajuste para el porcentaje de sobreentrega). |
| Bloquear | <p>Los trabajadores no pueden registrar la recepción de cantidades que exceden la cantidad restante no registrada para una carga seleccionada (después del ajuste para el porcentaje de exceso de entrega). Un trabajador que intente registrar los recibos recibirá un error y no podrá continuar hasta que registre una cantidad igual o menor que la cantidad de carga no registrada restante.</p><p>De forma predeterminada, el valor del porcentaje de entrega en exceso en una línea de carga se copia de la línea de orden de compra asociada. Cuando el campo <b>Carga sobre recibo</b> se establece en <i>Bloquear</i>, el sistema utiliza el valor de porcentaje de entrega en exceso para calcular la cantidad total que se puede registrar para una línea de carga. Sin embargo, ese valor puede sobrescribirse para cargas individuales según sea necesario. Este comportamiento se vuelve relevante durante la recepción de flujos donde parte o la totalidad de la cantidad en exceso que representa el porcentaje de entrega en exceso de la línea de pedido se distribuye de manera desproporcionada a través de múltiples cargas. Este es un escenario de ejemplo:</p><ul><li>Hay varias cargas para una línea de pedido de compra.</li><li>La línea de pedido de compra tiene un porcentaje de entrega en exceso superior a 0 (cero).</li><li>Las cantidades ya se han registrado para una o más cargas sin tener en cuenta el porcentaje de entrega en exceso.</li><li>La cantidad de entrega excesiva llega con la última carga.</li></ul><p>En este escenario, un dispositivo móvil puede usarse para registrar la cantidad en exceso para la última carga solo si el supervisor de almacén aumenta el porcentaje de entrega en exceso para la línea de carga relevante del valor predeterminado a un valor que es lo suficientemente grande como para que la entrega en exceso completa pueda estar registrado con la carga final.</p> |
| Bloquear solo para cargas cerradas | Los trabajadores pueden recibir cantidades excesivas de líneas de carga para cargas abiertas, pero no para cargas que tienen un estado de _Recibido_. |

> [!NOTE]
> El valor predeterminado del campo **Carga sobre recibo** es _Permitir_. Cuando se utiliza este valor, el comportamiento coincide con el comportamiento estándar que estaba disponible antes de que la característica _Sobre recepción de cantidades de carga_ se introdujera en la versión 10.0.11.

### <a name="put-away-the-registered-quantities"></a>Guardar las cantidades registradas

Cuando se completa el registro en el dispositivo móvil, la acción _Registro de recibo de cantidad_ actualiza los registros de inventario y almacén para indicar que las cantidades están ahora en la ubicación del muelle receptor y disponibles para reserva. Sin embargo, las operaciones de almacén de una empresa generalmente requieren que las cantidades se trasladen del muelle de recepción al almacenamiento de almacén regular, de modo que puedan ocurrir los procesos de picking posteriores. Las instrucciones para el almacenamiento se capturan en el trabajo de almacenamiento que se genera automáticamente cuando la carga entrante se registra como recibida.

Cuando el trabajador del almacén ha completado el trabajo de almacenamiento, el sistema registra y rastrea el resultado actualizando las actualizaciones de varias entidades, como se resume en la siguiente tabla.

| Entidad | Actualizaciones | Billete |
|---|---|---|
| Cargar | <p>Los campos siguientes se actualizan:</p><ul><li>El valor <b>Estado de carga</b> se cambia a <i>En proceso</i>.</li><li>El valor <b>Estado del trabajo</b> se cambia a <i>100,00% del trabajo completado</i>.</li></ul> | El valor **Estado de carga** se cambia a _En proceso_ cuando el trabajador comienza la tarea de guardar para al menos una línea de trabajo de guardar. |
| Inventario de transacciones de trabajo para los que se han guardado cantidades asociadas | Los campos **Recibo** y **Ubicación** y otros campos relevantes se actualizan para reflejar el movimiento desde la ubicación de recepción a la ubicación de almacenamiento. | El valor **Estado de recepción** de la transacción de inventario de orden de compra permanece _Registrado_. |
| Guardado en almacén | El valor **Estado del trabajo** se cambia a _Cerrado_. | |

## <a name="post-registered-product-quantities-against-purchase-orders"></a><a name="post-registered-quantities"></a>Cantidades de producto post registro contra pedidos de compra

Una vez que las cantidades de productos entrantes se registran en el sistema, quedan disponibles para reserva en relación con las ventas y otras operaciones salientes e internas. Sin embargo, el sistema aún no actualiza las cuentas de inventario (provisionales). Esta actualización solo puede ocurrir cuando el equipo de operaciones registra los recibos de productos registrados.

Para abrir una página donde pueden publicar un recibo de producto, los miembros del equipo de operaciones pueden seguir _uno_ de estos pasos:

- Abrir el registro de carga relevante y luego seleccionar la acción **Recibo del producto**.
- Ir a **Gestión de almacenes \> Tareas periódicas \> Actualizar recibos de productos**, y luego, en el campo **Id. de carga**, especifique la carga a registrar.
- Abrir el pedido de compra relevante y luego seleccionar la acción **Recibo del producto**.
- Ir a **Adquisición y abastecimiento \> Pedidos de compra \> Recepción de productos \> Registrar trabajo de recepción de producto**.

La acción **Recibo del producto** que está disponible en la página **Carga** (y en la página equivalente para el trabajo de actualización, la página **Actualizar recibos de productos**) puede actualizar cantidades de recibos de productos solo en cantidades de pedidos de compra que tienen un estado de _Registrado_. Sin embargo, la acción **Recibo del producto** que está disponible en la página **Pedido de compra** puede incluir cantidades en ambos estados de procesamiento (_Pedido_ y _Registrado_). También puede controlar el alcance de la recepción de recibos de productos a través de parámetros adicionales, como _Recibir cantidad ahora_ y _Cantidad registrada y servicios_.

Solo pedidos que tienen un estado de _Confirmado_ pueden registrarse como producto recibido. Para pedidos de compra no confirmados, la acción **Recibo del producto** aparecerá como no disponible.

### <a name="post-registered-quantities-from-the-load-page"></a>Contabilizar cantidades registradas desde la página Carga

Para las cantidades registradas de recepción de producto la página **Carga**, debe tener siguientes requisitos previos:

- La carga debe tener al menos una unidad de cantidad que tenga un estado de _Registrado_.
- El estado de carga debe ser _Enviado_.
- El pedido de compra asociado con la carga debe tener un estado de _Confirmado_.

> [!NOTE]
> Si el estado de carga no se ha establecido en _Enviado_, el sistema confirmará automáticamente la carga antes de ejecutar la actualización del recibo del producto. (El estado de carga se establece en _Enviado_ cuando un usuario registra el envío entrante de la carga).

Para registros de recibo de producto posteriores a la llegada que están asociados con una carga seleccionada, trabajador selecciona la acción **Recibo del producto** en la página **Carga**. La página que se abre tiene los siguientes detalles clave:

- El campo **Cantidad** en la sección **Parámetros** en la pestaña **Configuraciones** muestra la _cantidad registrada_. No hay otras opciones disponibles aquí.
- La cuadrícula en la ficha desplegable **Información general** enumera todos los pedidos de compra que se incluyen en la carga seleccionada.
- La cuadrícula en la ficha desplegable **Líneas** enumera todas las líneas de pedido que tienen una cantidad registrada.

> [!NOTE]
> Las cantidades para líneas de pedido que aparecen en la pestaña **Línea** se calculan de manera diferente, dependiendo de si la función _Permitir recibo de múltiples productos por carga_ está disponible y activada en su versión de Supply Chain Management.
>
> | Versión | Cálculo |
> |---|---|
> | Las versiones anteriores a la versión 10.0.10 y versiones más recientes donde la función _Permitir recibo de múltiples productos por carga_ no está activada | La cantidad de línea es el total de todas las cantidades registradas _para esa línea de orden de compra_, independientemente de si el registro se realizó en varias cargas, independientemente de la carga, desde un dispositivo móvil o desde el cliente. |
> | La versión 10.0.10 y posteriores donde la función _Permitir recibo de múltiples productos por carga_ está activada | La cantidad de línea es el total de todas las cantidades registradas _para el registro de carga_ desde el que se inició la acción **Contabilización de recibo de producto**. |

Cuando el usuario selecciona **Aceptar** para confirmar la recepción del recibo del producto, el sistema realiza las siguientes actualizaciones clave en las entidades apropiadas.

| Entidad | Actualizaciones |
|---|---|
| Transacción de inventario de la orden de compra para la cual se han incluido cantidades de línea en el alcance de contabilización | <p>Se actualizan los siguientes campos (pero tenga en cuenta que también hay muchas otras actualizaciones):</p><ul><li>El campo <b>Recibo</b> se establece en <i>Recibido</i>.</li><li>El campo <b>Fecha física</b> se actualiza con la fecha de publicación.</li></ul> |
| Carga desde la que el usuario publicó el recibo del producto | Las actualizaciones de las cargas dependerán de la versión que se use y la configuración del campo **Permitir recibo de múltiples productos por carga**. Las reglas se describen en la tabla que aparece más adelante en esta sección. |

El campo **Permitir recibo de múltiples productos por carga** permite a las compañías elegir una política de recepción de carga entrante. Dependiendo de sus flujos operativos, las compañías pueden optar por permitir o no permitir múltiples contabilizaciones de recibos de productos para la misma carga. Recomendamos que el gerente de logística establezca el campo **Permitir recibo de múltiples productos por carga** a uno de los siguientes valores:

- **No** - Seleccione este valor si los empleados de recepción del almacén siempre registran todas las cantidades de pedidos que llegan con cada carga dentro de un marco de tiempo designado. Si no se registran cantidades de carga, el sistema asume que no llegaron o que no estaban en la carga y, por lo tanto, no deberían considerarse parte de la carga. La contabilización del recibo del producto que se ejecuta desde una carga utiliza el mismo supuesto. Además de la recepción del producto, que actualiza todas las cantidades registradas (su función principal), declara la carga completa y cerrada para un procesamiento adicional. En este caso, todas las cantidades de línea de carga se actualizarán automáticamente a las cantidades registradas, las líneas de carga que no tengan cantidades registradas se eliminan y el estado de carga se cambia a _Recibido_.
- **Sí** - Seleccione este valor si los empleados de recepción de almacén requieren más tiempo para registrar todas las cantidades en la carga que llegó, pero, mientras tanto, debe registrar las cantidades de producto recibido que ya se han registrado. En este caso, el gerente de logística querrá mantener una carga abierta incluso después de que se ejecute el trabajo de contabilización del recibo del producto, de modo que las cantidades de carga restantes se puedan registrar y el recibo del producto se actualice al libro mayor de manera continua.
- **Preguntar** - Seleccione este valor si sus prácticas de recepción de carga son mixtas y se requiere una decisión cada vez que se ejecuta la contabilización del recibo del producto.

La siguiente tabla resume los efectos de la configuración **Permitir recibo de múltiples productos por carga**.

| Permitir recibo de múltiples productos por carga | Cantidad de carga | Estado de la carga | Billete |
|---|---|---|---|
| Cuando este campo no está disponible (versiones anteriores a 10.0.10) | <p>La cantidad de carga se establece para que sea igual a la cantidad registrada.</p><p>Si la cantidad de carga se actualiza a 0 (cero), lo que significa que no se ha realizado ningún registro, la línea de carga se elimina.</p><p>Si no hay líneas de carga en la carga, la carga se elimina.</p> | _Recibida_ | Si existen varias cargas para la cantidad registrada de la línea de pedido, solo el estado de la carga desde la que se registró el recibo se actualiza a _Recibido_. |
| Nº | <p>La cantidad de carga se establece de modo que sea igual a la cantidad registrada que está asociada con la ID de carga.</p><p>Si no se registra ninguna ID de carga para la transacción de inventario, el comportamiento coincide con el comportamiento en versiones anteriores a 10.0.10.</p> | _Recibida_ | |
| Sí | Sin actualizaciones | _Recibido_, si la cantidad de carga total registrada es igual o mayor que la cantidad de carga | |
| Sí | Sin actualizaciones | _Enviado_ o _En proceso_, si la cantidad de carga total registrada es menor que la cantidad de carga | |

Después de que el campo **Estado de carga** se establece en _Recibido_, no se pueden realizar más contabilizaciones de recibos de productos para esa carga. Sin embargo, el trabajador puede registrar la cantidad de pedido restante contra la carga recibida en las siguientes condiciones. (Para obtener más información, consulte la sección [Exceso de recepción de carga](#load-over-receiving) descrita anteriormente en este tema).

- La versión de Supply Chain Management es anterior a la versión 10.0.11.
- La función _Sobre recepción de cantidades de carga_ está activada y el campo **Cantidad de línea de carga sobre recibida** en el elemento de menú del dispositivo móvil para la acción de recepción del elemento de carga se establece en _Permitir_.

Para la recepción del producto contabilice cantidades de carga registradas adicionales en una carga que tenga un estado de _Recibido_, el usuario debe ejecutar la acción de publicación desde el pedido de compra asociado.

### <a name="post-registered-quantities-from-the-purchase-order-page"></a>Contabilizar cantidades registradas desde la página Pedido de compra

Al recibo del producto contabilice las cantidades registradas desde la página **Pedido de compra**, el usuario completa las siguientes tareas antes de seleccionar la acción **Recibo del producto**:

- Establezca el campo **Cantidad** en la sección **Parámetros** en la pestaña **Configuraciones** a _Cantidad registrada_.
- En el campo **Recibo del producto**, ingrese los números de los pedidos de compra que se incluyen en la contabilización.

> [!NOTE]
> La cantidad de línea que se incluirá en el ámbito de publicación es el total de todas las cantidades registradas para esa línea de pedido de compra, independientemente de si el registro de la cantidad se realizó en varias cargas, independientemente de la carga, desde un dispositivo móvil o desde el cliente. La misma regla se aplica cuando la contabilización del recibo del producto se ejecuta desde una carga, si se realiza donde el campo **Permitir recibo de múltiples productos por carga** no está disponible o no está habilitado.

Cuando el usuario selecciona **Aceptar** para confirmar la recepción del recibo del producto, el sistema realiza las siguientes actualizaciones clave en las entidades apropiadas.

| Entidad | Actualizaciones |
|---|---|
| Transacción de inventario de la orden de compra para la cual se han incluido cantidades de línea en el alcance de contabilización | <p>Se actualizan los siguientes campos (pero tenga en cuenta que también hay muchas otras actualizaciones):</p><ul><li>El campo <b>Recibo</b> se establece en <i>Recibido</i>.</li><li>El campo <b>Fecha física</b> se actualiza con la fecha de la acción de publicación de recepción de producto.</li></ul> |
| Cargar | Las actualizaciones de las cargas dependen de si el campo **Permitir recibo de múltiples productos por carga** está disponible y habilitado. Las reglas se describen en la tabla siguiente. |

La siguiente tabla resume los efectos de la configuración **Permitir recibo de múltiples productos por carga**.

| Permitir varias recepciones de productos por carga | Cantidad de carga | Estado de la carga | Billete |
|---|---|---|---|
| Cuando este campo está deshabilitado o no está disponible (en versiones anteriores a 10.0.10) | Sin actualizaciones | No se realizan actualizaciones. (El estado permanece _Abierto_, _Enviado_ o _En proceso_.) | Debido a que la contabilización del recibo del producto se inicia desde un pedido de compra, la lógica de actualización no tiene información sobre la asociación entre las cantidades registradas dentro de su alcance y las cargas con las que se registró el registro. Por lo tanto, no puede seleccionar la carga para la actualización de estado. |
| Habilitadas | Sin actualizaciones | <p>Se produce una de las acciones siguientes:</p><ul><li>El estado se cambia a <i>Recibido</i> si las cantidades totales recibidas y compradas de las transacciones de inventario de la orden de compra son mayores o iguales a la cantidad de la carga con la que están asociadas.</li><li>El estado permanece <i>Abierto</i>, <i>Enviado</i> o <i>En proceso</i> si no se cumple la condición anterior para todas las líneas en la carga.</li></ul> | |

### <a name="select-the-appropriate-product-receipt-posting-option-for-your-logistics-operations"></a>Seleccione la opción de registro de recibo de producto adecuada para sus operaciones logísticas

Como se describió anteriormente, el sistema ofrece dos opciones de registro de recibos de productos. Se puede acceder a las opciones en los siguientes lugares:

- En la página **Carga**, o desde el menú **Gestión de almacenes \> Tareas periódicas** menú como trabajo de actualización
- En la página **Pedido de compra**, o desde el menú **Adquisiciones y abastecimiento \> Pedidos de compra \> Recibiendo productos** como trabajo de actualización

Se recomienda a las empresas que utilizan cargas para planificar y gestionar el transporte y la gestión de almacén de sus pedidos entrantes utilicen las siguientes funciones, que están diseñadas para trabajar con cargas:

- **Carga de artículos recibidos** acciones en sus dispositivos móviles de almacén, para registrar la llegada de la cantidad del producto contra la carga
- **Contabilización de recibo de producto** acciones que se inician desde una carga, para actualizar el libro mayor de inventario

> [!NOTE]
> Se pueden usar otras funciones de registro de cantidad y registro de recibo de producto para soportar los procesos operativos entrantes correspondientes. Sin embargo, si los usa indistintamente con o en lugar de las funciones dedicadas centradas en la carga, puede comprometer la precisión de los datos de los registros de carga y, por lo tanto, la fluidez de los flujos de administración de carga.

## <a name="example-scenarios"></a>Escenarios de ejemplo

### <a name="prepare-your-system-to-run-the-sample-scenarios"></a>Prepare su sistema para ejecutar los escenarios de muestra

Para trabajar con los escenarios de muestra que se describen en esta sección, primero debe asegurarse de que todas las funciones requeridas estén activadas en su sistema. Los datos de demostración requeridos también deben estar disponibles en el sistema.

#### <a name="turn-on-the-required-features"></a>Active las funciones requeridas

Estos escenarios requieren la característica _Múltiples contabilizaciones de recibos de productos por carga_ y su característica de prerrequisito. Los administradores pueden activar esas funciones siguiendo estos pasos.

1. Abra el espacio de trabajo **Administración de características**. (Para obtener detalles completos sobre cómo encontrar y usar este espacio de trabajo, vea [Resumen de gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)).

1. Active la característica _Asociar transacciones de inventario de orden de compra con carga_, que se enumera de la siguiente manera:

    - **Módulo:** _Gestión de almacén_
    - **Nombre de la característica:** _Asociar transacciones de inventario de orden de compra con carga_

1. Active la característica _Múltiples contabilizaciones de recibos de productos por carga_, que se enumera de la siguiente manera:

    - **Módulo:** _Gestión de almacén_
    - **Nombre de la característica:** _Múltiples contabilizaciones de recibos de productos por carga_

#### <a name="enable-sample-data"></a>Habilitar datos de muestra

Para trabajar en estos escenarios mediante el uso de los registros y valores de muestra especificados, debe utilizar un sistema donde se instalen los datos de demostración estándar. También debe seleccionar la entidad legal **USMF** antes de comenzar.

#### <a name="add-a-menu-item-for-receiving-load-items-when-a-mobile-device-is-used"></a>Agregue un elemento de menú para recibir elementos de carga cuando se usa un dispositivo móvil

Antes de que los empleados de recepción del almacén puedan usar un dispositivo móvil para registrar el inventario entrante que está vinculado a una carga, debe crear un elemento de menú del dispositivo móvil para ese propósito.

En esta sección, creará un elemento de menú del dispositivo móvil y lo agregará a un menú existente. Un trabajador de almacén puede seleccionar el elemento del menú en la aplicación móvil Warehouse Management.

1. Vaya a **Gestión de almacenes \> Configurar \> Dispositivo móvil \> Elementos del menú del dispositivo móvil** y asegúrese de que el menú de su dispositivo móvil incluya un elemento de menú que tenga la siguiente configuración:

    - **Modo:** _Trabajo_
    - **Proceso de creación de trabajo:** _Carga de artículos recibidos_
    - **Generar matrícula de entidad de almacén:** _Sí_

    Puede dejar todas las demás configuraciones en sus valores predeterminados.

    ![Configuración del elemento de menú del dispositivo móvil.](media/inbound-mobile-menu-items.png "Configuración del elemento de menú del dispositivo móvil")

    Para obtener más información sobre cómo configurar los elementos del menú del dispositivo móvil, vea [Configurar dispositivos móviles para trabajos de almacén](configure-mobile-devices-warehouse.md).

2. Una vez haya terminado de configurar el elemento del menú, vaya a **Gestión de almacenes \> Configurar \> Dispositivo móvil \> Elementos del menú del dispositivo móvil** y agréguelo a la estructura de menú de sus dispositivos móviles.

### <a name="example-scenario-1-register-a-load-where-some-items-are-missing"></a>Escenario de ejemplo 1: registrar una carga donde faltan algunos elementos

Este escenario muestra cómo registrar cantidades para una carga entrante donde no todas las cantidades esperadas están presentes. Luego muestra cómo contabilizar el recibo del producto para el pedido de compra.

#### <a name="create-a-load-to-plan-receipt-of-a-purchase-order"></a>Crear una carga para planificar la recepción de un pedido de compra

En este procedimiento, creará manualmente un pedido de compra y una carga asociada. Luego actualizará la carga para simular que ha sido enviada desde el proveedor (que actualiza el estado de la carga). Los planificadores de almacén pueden filtrar las cargas por **Estado de carga** para encontrar las cargas entrantes esperadas.

1. Vaya a **Adquisición y abastecimiento \> Pedidos de compra \> Todos los pedidos de compra**.
1. Seleccione **Nuevo**.
1. En el cuadro de diálogo **Crear orden de compra**, establezca el campo **Cuenta de proveedor** en _1001_.
1. Seleccione **Aceptar** para cerrar el cuadro de diálogo y crear el pedido de compra.
1. El nuevo pedido de compra ya incluye una línea debajo de **Líneas de pedido de compra**. Establezca los siguientes valores para esta línea:

    - **Código de artículo:** _A0001_
    - **Almacén**: _24_
    - **Cantidad:** _10_

1. En el panel de acciones, en la pestaña **Compra,** seleccione **Acciones \> Confirmar**. El estado del pedido es ahora _Confirmado_.
1. En el panel de acciones, en la pestaña **Almacén** seleccione **Acciones \> Área de trabajo de planificación de la carga**.
1. En la página **Banco de trabajo de planificación de carga**, en el Panel de acciones, en la pestaña **Oferta y demanda**, seleccione **Agregar \> A nueva carga**.
1. En el cuadro de diálogo **Cargar plantilla de asignación**, establezca el campo **Cargar Id. de plantilla** en _Contenedor de 20 '_.
1. Seleccione **Aceptar** para cerrar el cuadro de diálogo y volver al área de trabajo.
1. En la sección **Cargas**, seleccione **Id. de carga** para abrir la carga recién creada.
1. Revise el encabezado de carga y los detalles de la línea y observe los siguientes puntos:

    - En la ficha desplegable **Carga**, el campo **Estado de carga** se establece en _Abierto_.
    - En la sección **Líneas de carga**, hay una sola línea donde el campo **Cantidad** se establece en _10_ y el campo **Cantidad de trabajo creado** se establece en _0_ (cero).

    ![Detalles de la carga.](media/inbound-load-details.png "Detalles de la carga")

1. En el panel de acciones, en la ficha **Enviar y recibir**, seleccione **Confirmar \> Envío entrante**. Tenga en cuenta que el **Estado de carga** ha cambiado a _Enviado_.
1. Tome nota del valor **Id. de carga**, para que pueda usarlo en el siguiente procedimiento.

#### <a name="register-receipt-of-the-quantities-that-arrived-on-the-load"></a>Registrar recibo de las cantidades que llegaron en la carga

Cuando la carga llega al muelle de recepción del almacén, un empleado receptor registra las cantidades de carga en un dispositivo móvil.

1. Use su dispositivo móvil para iniciar sesión en el almacén 24. (En los datos de demostración estándar, inicie sesión utilizando _24_ como el Id. de usuario y _1_ como la contraseña).
1. Seleccione el elemento de menú _Carga de artículos recibidos_ que creó para este escenario.
1. Siga las instrucciones de ingreso de datos en la pantalla para ingresar los siguientes valores. (El orden puede variar, dependiendo del dispositivo móvil o emulador que esté utilizando).

    - **Carga** - Introduzca el Id. de carga que creó en el procedimiento anterior.
    - **Articulo** - Introduzca _A0001_, que es el elemento que se espera para esta carga.
    - **Cantidad** - Introduzca _9_ como la cantidad real que está presente en la carga. Tenga en cuenta que esta cantidad es menor que la cantidad esperada.

1. Continúe avanzando por el flujo de trabajo, dejando todos los demás campos en blanco o configurados con sus valores predeterminados, hasta que su dispositivo le informe que el trabajo se ha completado.

La tarea de recepción de carga ahora se ha completado y el empleado receptor puede pasar a su próxima tarea. Sin embargo, el personal de recepción del almacén eventualmente revisará el registro de carga y podrá ver que la cantidad recibida fue menor que la cantidad esperada. Entonces completarán el siguiente procedimiento utilizando el cliente web.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. En la lista, encuentre la carga que acaba de recibir. (Puede que tenga que seleccionar la casilla de verificación **Mostrar cerrado** para incluir las cargas entrantes que tienen un estado de carga de _Enviado_). Luego seleccione el enlace en la columna **Id. de carga** para abrir la carga.
1. En el registro de carga, observe que el valor **Estado de carga** permanece _Enviado_, pero el valor **Cantidad de trabajo creado** en la línea de carga ha cambiado a _9_.
1. Vaya a **Adquisición y abastecimiento \> Pedidos de compra \> Todos los pedidos de compra**.
1. En la lista, busque la compra que acaba de recibir y luego seleccione el enlace en la columna **Pedido de compra** para abrir el pedido.
\
1. En la ficha desplegable **Líneas de pedido de compra**, seleccione **Inventario \> Ver \> Transacciones**.
1. Revise los detalles de las dos transacciones de orden de compra. (Puede que tenga que personalizar la página **Transacciones de inventario** para ver el campo **Id. de carga** en la cuadrícula). Debería ver dos transacciones:

    - La transacción que tiene un recibo en el estado _Registrado_ representa la cantidad de registro de _9_ que se ejecutó contra una carga específica mediante el uso del dispositivo móvil. El **Id. de carga** está asociado con la transacción en cuestión.
    - La transacción que tiene un recibo en el estado _Pedido_ representa la cantidad restante de línea de pedido no registrada de _1_.

#### <a name="product-receiptpost-the-registered-load-quantities-against-purchase-orders"></a>Registrar el producto recibido con las cantidades de carga registrada contra los pedidos de compra

En este procedimiento producir el inventario de registro de producto recibido que ha registrado para una carga. Como resultado, el inventario recibido y los costos relacionados se agregarán a la contabilidad general de la compañía.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. En la lista, encuentre la carga que ha recibido. (Puede que tenga que seleccionar la casilla de verificación **Mostrar cerrado** para incluir las cargas entrantes que tienen un estado de carga de _Enviado_). Luego seleccione el enlace en la columna **Id. de carga** para abrir la carga.
1. En el panel de acciones, en la ficha **Enviar y recibir**, seleccione **Recibir \> Producto recibido**. Haga clic en **Sí** si se le solicita que confirme la selección.
1. En el cuadro de diálogo **Registro de recepción de productos**, en la ficha desplegable **Líneas**, inspeccione la cuadrícula. Debería ver la línea de orden de compra para la cual se ha registrado la cantidad contra la carga seleccionada.

    > [!NOTE]
    > En versiones donde la función _Múltiples contabilizaciones de recibos de productos por carga_ no está disponible o no está habilitada, la cantidad predeterminada que se muestra en la cuadrícula **Líneas de carga** será la cantidad total que se ha registrado en todas las cargas asociadas con la línea de pedido de compra.

1. En la ficha desplegable **Resumen** inspeccione el campo **Recepción del producto** en la cuadrícula. Tenga en cuenta que se debe establecer en un número que incluya el Id. de la carga seleccionada.
1. Seleccione **Aceptar** para contabilizar el recibo del producto y cerrar el cuadro de diálogo **Contabilizar recibo de producto**.
1. Ha vuelto a los detalles de carga. Tenga en cuenta los aspectos siguientes:

    - El campo **Estado de carga** ahora está configurado en _Recibido_.
    - En la línea de carga, el valor **Cantidad** de la carga ha cambiado de _10_ a _9_ PC para que coincida con la cantidad registrada, pero el valor **Cnatidad de trabajo creado** permanece _9_.

Si el equipo de compras no espera que el proveedor entregue la cantidad de pedido restante de 1, puede cerrar el pedido actualizando el resto de la entrega de la línea a _0_. Sin embargo, si pronto se descubre que la pieza faltante llegó a la carga original, el personal del almacén puede realizar una de las siguientes acciones:

- Registrar la cantidad contra la misma carga. En este caso, el campo **Estado de carga** se restablecerá en _Enviado_ y el valor **Cantidad de trabajo creado** el valor se actualizará a _10_. Esta elección solo se encuentra disponible en las situaciones siguientes.

    - La función _Sobre recepción de cantidades de carga_ no está disponible o no está habilitada.
    - La función _Sobre recepción de cantidades de carga_ está disponible y habilitada, y el campo **Cantidad de línea de carga sobre recibo** está establecido en _Permitir_.

- Agregue la cantidad a una carga nueva o existente y procese de la manera habitual.
- Registre y / o reciba la cantidad de una manera que no implique manejo de carga.

### <a name="example-scenario-2-register-quantities-that-arrive-on-multiple-inbound-loads-where-some-items-are-missing"></a>Escenario de ejemplo 2: registrar cantidades que llegan en múltiples cargas entrantes donde faltan algunos artículos

En este escenario, un envío entrante relacionado con una sola línea de orden de compra se dividirá en dos cargas. Por ejemplo, una línea de orden de compra puede dividirse en múltiples cargas debido a restricciones físicas de carga en peso y / o volumen.

Este escenario también muestra cómo procesar contabilizaciones de recibos de múltiples productos para la misma carga. Registrará cantidades que lleguen en múltiples cargas entrantes, pero las cantidades no coincidirán con las cantidades esperadas. Las actualizaciones de costos que se producen a través de la contabilización del recibo del producto se realizarán varias veces para la misma carga.

#### <a name="set-up-load-receiving-policies"></a>Configurar políticas de recepción de carga

En este procedimiento, habilitará múltiples contabilizaciones de recibos de productos de la misma carga.

1. Vaya a **Gestión de almacenes \> Configuración \> Parámetros de gestión de almacenes**.
1. En la pestaña **Cargas**, configure el campo **Permitir recibo de múltiples productos por carga** a _Sí_.

#### <a name="create-two-loads-to-plan-receipt-of-a-purchase-order"></a>Crear dos cargas para planificar la recepción de un pedido de compra

En este procedimiento, creará manualmente un pedido de compra y dos cargas. Luego actualizará manualmente cada carga para simular que ha sido enviada por el proveedor (que actualiza el estado de la carga). Los planificadores de almacén pueden filtrar las cargas por **Estado de carga** para encontrar las cargas entrantes esperadas.

También aprenderá cómo establecer la línea de pedido de compra para que pueda recibir una cantidad que sea un 20 % más que la cantidad especificada para la línea.

1. Vaya a **Adquisición y abastecimiento \> Pedidos de compra \> Todos los pedidos de compra**.
1. Seleccione **Nuevo**.
1. En la ficha desplegable **Proveedor**, configure el campo **Cuenta de proveedor** a _1001_ y luego seleccione **Aceptar**.
1. Su pedido de compra nuevo se abre e incluye una línea en blanco en la cuadrícula **Líneas de pedido de compra**. Establezca los siguientes valores para esta línea de pedido:

    - **Código de artículo:** _A0001_
    - **Almacén**: _24_
    - **Cantidad:** _10_

1. Sobre la ficha desplegable **Detalles de línea**, en la pestaña **Entrega**, configure el campo **Entrega en exceso** a _20_.
1. En el panel de acciones, en la pestaña **Compra,** seleccione **Acciones \> Confirmar**. El estado del pedido es ahora _Confirmado_.
1. En el panel de acciones, en la pestaña **Almacén** seleccione **Acciones \> Área de trabajo de planificación de la carga**.
1. En la página **Banco de trabajo de planificación de carga**, en el Panel de acciones, en la pestaña **Oferta y demanda**, seleccione **Agregar \> A nueva carga**.
1. En el cuadro de diálogo **Cargar plantilla de asignación**, establezca el campo **Cargar Id. de plantilla** en _Contenedor de 20 '_. En la pestaña **Detalles**, cambie el valor **Cantidad** de _10_ a _5_ para agregar parcialmente la cantidad de línea de pedido de compra.
1. Seleccione **Aceptar** para aplicar su configuración y cerrar el cuadro de diálogo.
1. Repita los pasos del 8 al 10 para crear una segunda carga. Esta vez, el campo **Cantidad** ya debería estar configurado en _5_.
1. En la página **Área de trabajo de planificación de la carga**, en la cuadrícula **Cargas**, seleccione el valor **Id. de carga** para la primera carga que creó. La página **Detalles de carga** aparece y muestra la carga seleccionada. Siga estos pasos:

    1. En el panel de acciones, en la ficha **Enviar y recibir**, seleccione **Confirmar \> Envío entrante**.
    1. Tenga en cuenta que el valor **Estado de carga** ha cambiado a _Enviado_.
    1. Seleccione el botón cerrar para volver a la página **Área de trabajo de planificación de carga**.

1. Repita el paso anterior para la segunda carga que creó.
1. Tome nota de los dos valores **Id. de carga** que aparecen en la cuadrícula **Cargas**.

#### <a name="register-partial-receipt-of-the-quantities-that-arrived-on-the-first-load-and-post-the-registered-load-quantities"></a>Registre la recepción parcial de las cantidades que llegaron en la primera carga y contabilice las cantidades de carga registradas

Cuando las cargas llegan al muelle de recepción del almacén, un empleado receptor registra las cantidades de carga en un dispositivo móvil. El inventario registrado que está vinculado a una carga se actualiza luego en el libro de contabilidad general de la compañía contabilizando el recibo del producto de la orden de compra, en función de la carga.

Este procedimiento muestra cómo un empleado receptor registrará las cantidades de carga en un dispositivo móvil.

1. Use su dispositivo móvil para iniciar sesión en el almacén 24. (En los datos de demostración estándar, inicie sesión utilizando _24_ como el Id. de usuario y _1_ como la contraseña).
1. Seleccione el elemento de menú _Carga de artículos recibidos_ que creó para este escenario.
1. Siga las instrucciones de ingreso de datos en la pantalla para ingresar los siguientes valores. (El orden puede variar, dependiendo del dispositivo móvil o emulador que esté utilizando).

    - **Carga** - Introduzca el primer Id. de carga que creó en el procedimiento anterior.
    - **Articulo** - Introduzca _A0001_, que es el elemento que se espera para esta carga.
    - **Cantidad** - Introduzca _3_. Tenga en cuenta que esta cantidad es menor que la cantidad esperada. Para este escenario, imagine que usted, como empleado receptor, no tiene tiempo para registrar todas las cantidades para esta carga. Más adelante en este procedimiento, registrará las partes restantes repitiendo este paso y configurando el campo **Cantidad** a _2_.

1. Continúe avanzando por el flujo de trabajo, dejando todos los demás campos en blanco o configurados con sus valores predeterminados, hasta que su dispositivo le informe que el trabajo se ha completado.
1. En el cliente web, vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. En la lista, busque la carga que acaba de recibir y seleccione el valor **Id. de carga** para abrir la carga. Tenga en cuenta que el valor **Estado de carga** permanece _Enviado_, pero el valor **Cantidad de trabajo creado** en la línea de carga ha cambiado a _3_.
1. En el panel de acciones, en la ficha **Enviar y recibir**, seleccione **Recibir \> Producto recibido**. Haga clic en **Sí** si se le solicita que confirme la selección.
1. En el cuadro de diálogo **Contabilizar recibo de producto** de diálogo, revise pero no cambie los valores que se muestran, y luego seleccione **Aceptar**.
1. Ha vuelto a la página **Detalles de carga** para la carga seleccionada. Tenga en cuenta los aspectos siguientes:

    - El campo **Estado de carga** permanece configurado en _Enviado_.
    - En la línea de carga, el valor **Cantidad** para la carga permanece _5_ PC, que es la cantidad de carga original, y el valor **Cantidad de trabajo creado** permanece en _3_.

1. Complete el registro de la cantidad restante en esta carga repitiendo este procedimiento. Sin embargo, en el paso 3, establezca el campo **Cantidad** a _2_.

La tarea de recepción para la primera carga ahora está completa. Se han creado dos diarios de recibo de producto, uno para cada una de las dos actualizaciones de recibo de producto que ejecutó.

#### <a name="register-receipt-of-the-quantities-that-arrived-on-the-second-load-and-account-for-the-overdelivered-quantity"></a>Registre el recibo de las cantidades que llegaron en la segunda carga y contabilice la cantidad entregada en exceso

Para este escenario, el empleado receptor registrará una cantidad que exceda la cantidad que existe en la carga. Se permitirá una recepción excesiva porque el sistema está configurado para permitir la entrega excesiva.

1. Use su dispositivo móvil para iniciar sesión en el almacén 24. (En los datos de demostración estándar, inicie sesión utilizando _24_ como el Id. de usuario y _1_ como la contraseña).
1. Seleccione el elemento de menú _Carga de artículos recibidos_ que creó para este escenario.
1. Siga las instrucciones de ingreso de datos en la pantalla para ingresar los siguientes valores. (El orden puede variar, dependiendo del dispositivo móvil o emulador que esté utilizando).

    - **Carga** - Introduzca el segundo Id. de carga que creó anteriormente.
    - **Articulo** - Introduzca _A0001_, que es el elemento que se espera para esta carga.
    - **Cantidad** - Introduzca _7_, que es la cantidad restante que el proveedor está autorizado a entregar como parte de la cantidad total de pedido de compra de 12 (donde 10 es la cantidad de pedido original y 2 es la cantidad de entrega en exceso permitida del 20 %). Recuerde que ya se han registrado 5 unidades en la primera carga.

La segunda carga ahora se ha actualizado con una cantidad de 7 y puede actualizarse la recepción del producto basada en esta cantidad.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]