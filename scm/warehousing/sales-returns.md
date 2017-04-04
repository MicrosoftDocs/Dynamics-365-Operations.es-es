---
title: Devoluciones de ventas
description: "Este tema proporciona información acerca del proceso para los pedidos de devolución. Incluye información sobre las devoluciones de cliente y su efecto en la gestión de costes y cantidades disponibles de inventario."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 269384
ms.assetid: 98a4b517-e606-4036-b55f-1ab248898bdf
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3d02a15387231160f5b8a237aa11008b91ef1223
ms.openlocfilehash: b265a20a271230de5dba6df93900a24aad642885
ms.lasthandoff: 03/31/2017


---

# <a name="sales-returns"></a>Devoluciones de ventas

Este tema proporciona información acerca del proceso para los pedidos de devolución. Incluye información sobre las devoluciones de cliente y su efecto en la gestión de costes y cantidades disponibles de inventario.

Los clientes pueden los artículos devueltos por varios motivos. Por ejemplo, un artículo puede ser defectuoso, o posible que no resuelva las expectativas del cliente. El proceso de devolución comienza cuando un cliente emite una solicitud para devolver un artículo. Después de que se recibe la solicitud del cliente, un pedido de devolución se crea en Microsoft Dynamics 365 para las operaciones.

## <a name="return-order-process"></a>Proceso de pedido de devolución
La ilustración siguiente proporciona información general del proceso del pedido de devolución.  

![salesreturns01 [] (. /media/salesreturns01.jpg])(. /media/salesreturns01.jpg)  

Existen dos tipos de proceso del pedido de devolución: devolución y comprobar crédito sólo.

-   ** Devolución de la comprobación – ** el pedido de devolución autoriza la devolución físico de productos.
-   ** El crédito sólo – ** el pedido de devolución autoriza un crédito del cliente pero no requiere que la devolución del cliente físicamente los productos.

### <a name="physical-return-order-process"></a>Proceso físico del pedido de devolución

1.  ** Crear un pedido de devolución. ** Conclusiones formalmente la autorización para que el cliente devuelva cualquier producto defectuoso o no deseados. El pedido de devolución no requiere la empresa que acepte los productos devueltos o proporcione un crédito para el cliente. Si se aprueba su devolución, puede autorizar un artículo de sustitución que se va a entregar antes de que se haya devuelto el artículo defectuoso.
2.  ** Llegue el almacén para su inspección. ** Realice una inspección inicial y una validación en relación con el documento de pedido de devolución. El pedido de devolución también admite la cuarentena de los artículos devueltos para inspección adicional y el control de calidad.
3.  ** Determine la disposición. ** Finaliza el proceso de inspección, y decida qué se debe hacer con los productos devueltos. Como parte de este paso, decida si se abonará el cliente, rechazará la devolución del producto, o aceptará la devolución del producto, deseche el producto, y envíe un artículo de sustitución al cliente.
4.  ** Generar un albarán. ** Generar un albarán, y confirmar la decisión de disposición que realizó en el paso 3. Finalizar los procesos de logística.
5.  ** Generar una factura. ** Cierre el pedido de devolución.

### <a name="credit-only-process"></a>Abone sólo el proceso

1.  ** Crear un pedido de devolución. ** Conclusiones formalmente Aceptar para que el cliente reciba un crédito sin devolver los productos defectuosos o no deseados. ** Crédito sólo ** el código de disposición autoriza la decisión para abonar al cliente sin devolución del cheque.
2.  ** Generar una factura. ** Generar la nota de crédito, y cierre el pedido de devolución.

## <a name="return-material-authorization"></a>Autorización de devolución de materiales
Un de procesamiento (RMA) de devolución de material (RMA funcionalidad del pedido de ventas. Un RMA se registra como un pedido de devolución, que se crea como pedido de ventas, y puede tener otro pedido de ventas asociado a él, denominado un pedido de sustitución. Vínculo de ambos pedidos de ventas al número RMA de origen.

-   ** Pedido de devolución – ** de registrar un RMA, crea un pedido de devolución, que es un pedido de ventas que tiene el tipo asignado, ** pedido devuelto. ** Los cambios que realice a la información de RMA se actualiza automáticamente en el pedido de ventas. Hasta que el pedido de devolución con el estado ** Abrir **, no aparecerá en la lista de pedidos de ventas. Use RMA para gestionar la llegada y la recepción de los artículos devueltos, así como para autorizar acción de disposición de crédito sólo (consulte la sección ** los códigos de disposición y las acciones de disposición **). El resto de los procesos de seguimiento se deben gestionar en el pedido de ventas.
-   ** El pedido de sustitución ** – cuando un pedido de sustitución se debe enviar al cliente, el RMA puede incluir un segundo pedido de ventas asociado. Puede crear manualmente el pedido de sustitución para el RMA que admita el envío inmediato. De manera alternativa, el pedido de sustitución se puede crear automáticamente tras la inspección llegada, y la recepción se completa para el artículo de línea de RMA que tiene un código de disposición que indica la sustitución. El pedido de sustitución tiene la misma funcionalidad que está asociada a un pedido de ventas. Por ejemplo, puede utilizarlo para configurar un producto personalizado como el artículo de sustitución, crear un pedido de producción reparar de un artículo devuelto, de crear un pedido de compra de entrega directa de registrar el sustitución de un proveedor, o que admita otros propósitos.

## <a name="create-a-return-order"></a>Crear un pedido de devolución
El proceso de pedido de devolución comienza cuando los contactos de un cliente su organización para devolver un producto defectuoso o no deseados y/o que se van a abonar. Una vez que la organización acepte la devolución, la devolución es documentado por un pedido de devolución. Este pedido de devolución se convierte en el punto focal de procesamiento interno de producto devuelto. La ilustración siguiente muestra el procedimiento para crear un pedido de devolución.  

[procedimiento de![para crear un pedido de devolución] (. /media/salesreturn02.png])(. /media/salesreturn02.png)

### <a name="create-a-return-order-header"></a>Crean un encabezado del pedido de devolución

Al crear un pedido de devolución, la información de la siguiente tabla se va a incluir.

| Campo              | Descripción                                              | Comentarios                                                                                                                                                                                                                                                                                                                                        |
|--------------------|----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Cuenta de cliente   | Una referencia a la tabla Customers                       | Debe proporcionar una cuenta de cliente existente.                                                                                                                                                                                                                                                                                                  |
| Dirección de entrega   | La dirección en la que el artículo está devuelto a                 | De forma predeterminada, se usa la dirección de la organización. Si selecciona un almacén específico en el encabezado, cambia a la dirección de entrega a la dirección de entrega desde el almacén. Puede cambiar esta dirección en ** los detalles del pedido de devolución ** la página.                                                                                                  |
| Relaciones sitio/almacén     | El sitio o almacén que recibe el producto devuelto | Determinan a la dirección de entrega del pedido de devolución en función de la dirección de entrega del sitio o almacén.                                                                                                                                                                                                                                 |
| Número RMA         | El identificador asignado al pedido de devolución              | El número RMA se usa como clave alternativa en el proceso del pedido de devolución. El número RMA se ha asignado se basa en la secuencia del número RMA que se configuran en ** los parámetros de clientes ** la página.                                                                                                                              |
| Fecha límite           | La última fecha en que un artículo puede ser devuelto               | El valor predeterminado se calcula como la fecha actual más el período de validez. Por ejemplo, si una devolución es válido únicamente por 90 días a partir de la fecha en la que se creó el pedido de devolución, y se creó el pedido de devolución el 1 de mayo, el valor del campo es ** 30-July **. El período de validez se establece en ** los parámetros de clientes ** la página. |
| Código de motivo de devolución | El motivo del cliente para devolver el producto          | El código de motivo se selecciona en la lista de códigos de motivo definido por el usuario. Puede actualizar este campo en cualquier momento.                                                                                                                                                                                                                                    |

### <a name="create-return-order-lines"></a>Crear líneas de pedidos de devolución

Después de finalizar la cabecera de devolución, puede crear líneas de devolución mediante uno de los métodos siguientes:

-   Especifique manualmente los detalles del artículo, la cantidad, y otra información para cada línea de devolución.
-   Crear una línea de devolución mediante ** pedido de ventas de la búsqueda ** la función. Se recomienda usar esta función al crear un pedido de devolución. ** Pedido de ventas de la búsqueda ** la función establece una referencia de la línea de devolución a la línea del pedido de ventas facturado, y recupera los detalles de línea como número de artículo, cantidad, precio, descuento, y valores de coste de la línea de ventas. Las ayudas de referencia garantizan que, cuando el producto se devuelve a la empresa, ha valorado en el mismo coste unitario que se vendida en. La referencia también comprueba que los pedidos de devolución no están creados para una cantidad que excede la cantidad que se vendida en la factura.

** Nota: ** Las líneas de devolución que tienen una referencia a un pedido de ventas se gestionan como correcciones, o, inversiones de la venta. Para obtener más información, consulte “Registrar la sección en la contabilidad,” más adelante en este tema.

### <a name="charges"></a>Gastos

Las cuotas y los gastos se pueden agregar al pedido de devolución con uno o más de los métodos siguientes:

-   Puede agregar manualmente gastos al encabezado del pedido de devolución, a la línea de pedido de devolución, o a ambos.
-   Los gastos pueden agregarse automáticamente al encabezado del pedido de devolución en función del código de motivo de devolución.
-   Los gastos pueden agregarse automáticamente a la línea de pedido de devolución, en función del código de disposición de la línea.

Agrega automáticamente los gastos después de que un código de motivo de devolución o un código de disposición está asignado a la línea. Si el código de motivo se cambia posteriormente, la entrada existente del gasto no se eliminará, pero una nueva entrada del gasto se puede agregar, en función del nuevo código de motivo. Al agregar gastos a las líneas de pedidos de devolución, los gastos se calculan como un porcentaje de la línea o el valor del pedido se convierte en negativo cuando la línea o el orden de la línea es negativo, a menos que el porcentaje sea también un número negativo. Cargo que tiene un valor negativo representa un abono al cliente.

### <a name="return-reason-codes"></a>Códigos de motivo de devolución

Por códigos de motivo que se aplican a las devoluciones, puede ayudar a crear patrones de devolución más fáciles analizar. Los códigos de motivo proporcionan información acerca de por qué un cliente desea que los artículos devueltos. Algunas organizaciones tienen muchos códigos de motivo. Este la organización puede agrupar los códigos de motivo en los grupos de códigos de motivo para obtener una mejor visión general y para el informe de errores acumulado.

### <a name="disposition-codes-and-disposition-actions"></a>Códigos de disposición y acciones de disposición

Paso importante en el proceso del pedido de devolución es la asignación de un código de disposición a la línea de pedido de devolución como parte de registro de llegada. El código de disposición determina la siguiente información:

-   ¿** Las consecuencias financieras ** – debe el cliente que se va a abonar para los artículos devueltos, y cargos debe ser agregado a la línea de pedido de devolución?
-   ¿La ** disposición del artículo devuelto ** – debe el artículo es posible agregar de nuevo a inventario, se debe dar de baja, o éste debe ser devolución al cliente?
-   ** ¿La logística del artículo devuelto ** – se debe un artículo de sustitución emitir al cliente?

Además de determinar cómo se desechan las mercancías devueltas, códigos de disposición pueden producir los gastos que se aplicarán a la línea de devolución. También pueden usar para agrupar las devoluciones para realizar análisis estadísticos. Los códigos de disposición se definen como parte de la configuración de pedidos de devolución. Sin embargo, cada código de disposición debe hacer referencia a una de las acciones integrados de cancelación. La tabla siguiente muestra los códigos de disposición integrados y sus acciones. ** Importante: ** Si se devuelve un artículo, sólo el cliente se debe asignar abonar, ** abono solo ** el código de disposición a la línea de devolución.

<table>
<thead>
<tr class="header">
<th>Código de disposición</th>
<th>Implicaciones financieras</th>
<th>Implicaciones para la logística</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Sólo abonar</td>
<td><ul>
<li>Acreditan el cliente el precio de venta menos las cuotas o gasto.</li>
<li>Pérdida de dar de baja el artículo se registra en la contabilidad.</li>
</ul></td>
<td>El artículo no se debe devuelto. Esta acción de disposición se usa para los casos siguientes:
<ul>
<li>Existen suficiente confianza entre las partes.</li>
<li>El coste para devolver el artículo es prohibitivo defectuoso.</li>
<li>Los artículos no se pueden permitir al inventario. Debido a otras condiciones, una devolución físico no se requiere.</li>
</ul></td>
</tr>
<tr class="even">
<td>Crédito</td>
<td><ul>
<li>Acreditan el cliente el precio de venta menos las cuotas o gasto.</li>
<li>El valor de inventario es aumentado por el coste del artículo devuelto.</li>
</ul></td>
<td>El artículo se devuelve y se agrega al inventario.</td>
</tr>
<tr class="odd">
<td>Reemplazar y abonar</td>
<td><ul>
<li>Acreditan el cliente el precio de venta menos las cuotas o gasto.</li>
<li>El valor de inventario es aumentado por el coste del artículo devuelto.</li>
<li>Un pedido de ventas individual para una sustitución se crea y se gestiona por separado.</li>
</ul></td>
<td>El artículo se devuelve y se agrega al inventario.</td>
</tr>
<tr class="even">
<td>Reemplazar y cancelar</td>
<td><ul>
<li>Acreditan el cliente el precio de venta, menos los cuota o gastos.</li>
<li>Pérdida de dar de baja el artículo se registra en la contabilidad.</li>
<li>Un pedido de ventas individual para una sustitución se crea y se gestiona por separado.</li>
</ul></td>
<td>Se devuelve y se da de baja el artículo.</td>
</tr>
<tr class="odd">
<td>Devolver al cliente</td>
<td>Ninguno, a menos que cualquier cuotas o cargos.</td>
<td>Se devuelve pero se registra el artículo al cliente tras la inspección. Esta acción de disposición puede usarse si el artículo se ha dañado deliberadamente, o si se ha anulado la garantía.</td>
</tr>
<tr class="even">
<td>Residuo</td>
<td><ul>
<li>Acreditan el cliente el precio de venta menos las cuotas o gasto.</li>
<li>Pérdida de dar de baja el artículo se registra en la contabilidad.</li>
</ul></td>
<td>Se devuelve o se dé de baja el artículo.</td>
</tr>
</tbody>
</table>

## <a name="arrival-at-the-warehouse-for-inspection"></a>Iniciar llegada en el almacén para inspección
Antes de que pueda recibir físicamente artículos devueltos en el inventario enviando un albarán, los artículos deben pasar el registro de llegada y una inspección opcional. La ilustración siguiente proporciona información general del proceso de llegada. Las siguientes secciones describen cada paso que se muestra en la ilustración.  

[proceso![llegada![] (. /media/salesreturn03.png])(. /media/salesreturn03.png)  

El proceso tiene varias variaciones que otras no se cubran en este tema. Aquí hay algunas de estas variantes:

-   No use ** visión general de llegadas ** la lista para crear un diario de recepción. En su lugar, cree manualmente el diario de recepción. Los pedidos de devolución tendrán ** pedido de ventas ** como la referencia.
-   Si utiliza la gestión de almacenes, genere los transportes de pallet. La línea de devolución tendrá un estado de ** llegado ** durante el transporte de pallet.
-   Registre la llegada del artículo devuelto directamente de la línea de pedido de devolución, mediante ** registro ** la función.

Durante el proceso de llegada, las devoluciones se integran con el proceso general para llegadas de almacén. El proceso de llegada también admite la creación de órdenes de cuarentena para los artículos devueltos deben probar una inspección separado.

### <a name="identify-products-in-the-arrival-overview-list"></a>Identifique los productos de la lista de la visión general de llegadas

** Visión general de llegadas ** la página muestra todas las llegadas de entrada planificadas. ** Nota: ** Las llegadas de pedidos de devolución se deben procesar por separado de otros tipos de transacciones de llegada. Una vez haya identificado un paquete de entrada en ** visión general de llegadas ** pagine (por ejemplo, con el documento que acompañan de RMA), en el panel de acciones, haga clic en ** llegada de inicio ** a crear y inicializar a un diario de recepción que coincida llegada.

### <a name="edit-the-arrival-journal"></a>Edite el diario de recepción

Estableciendo Sí ** gestión de cuarentena ** de la opción ** **, puede crear una orden de cuarentena para la línea de devolución. Si una línea se ha enviado a cuarentena para inspección, no puede especificar un código de disposición. ** Nota: ** Si establece Sí ** gestión de cuarentena ** de la opción ** ** en el grupo de modelos de inventario, ** gestión de cuarentena ** la opción ** en las líneas de diario ** la página marcadas para la línea del diario de recepción y no se puede modificar. Si la línea se registra a cuarentena, debe especificar el almacén de cuarentena adecuado. Si la línea de llegada no se registra para inspección, el vendedor de la llegada de almacén debe especificar el código de disposición directamente en la línea del diario de recepción y enviar el diario de recepción. Si el mismo código de disposición se asigna a toda la cantidad de la línea de devolución, o si la cantidad completa de la línea no se ha recibido, debe dividir la línea. Al dividir una línea del diario de recepción, también divide la línea de devolución (SalesLine ** **) y cree un nuevo identificador del lote. Puede dividir la línea reduciendo la cantidad de la línea del diario de recepción. Cuando se registra el diario, se crea una nueva línea de devolución de la que tiene un estado ** ** esperado para la cantidad restante. También puede dividir la línea si hace clic en ** las funciones ** &gt; ** la división **.

### <a name="process-the-quarantine-order"></a>Procese el orden de cuarentena

Si productos devueltos se registran para inspección en el almacén de cuarentena, cualquier procesamiento adicional se completa en una orden de cuarentena. Las órdenes de cuarentena se crea para cada línea de llegada que se envía a cuarentena. El código de disposición indica el resultado del proceso de inspección. Puede dividir un pedido de cuarentena, igual que puede dividir el diario de recepción. Si ha dividido el orden de cuarentena, se produce una división que corresponde de la línea de devolución. Después de que se escriba el código de disposición, complete el orden de cuarentena mediante ** extremo ** la función o ** notificación como terminado ** la función. Si selecciona ** notificación como terminado, ** una nueva llegada se crea en el almacén designado. A continuación puede procesar esta llegada mediante ** visión general de llegadas ** la página. Si la llegada se origina de una orden de cuarentena, no puede cambiar el código de disposición que se asigna durante la inspección. Si completa el orden de cuarentena mediante ** extremo ** la función, el lote se registra automáticamente. A veces, un artículo se puede registrar posterior de cuarentena al departamento de envíos y recepciones. Por ejemplo, el inspector de cuarentena no puede sabe dónde almacenar el artículo en el inventario. En este caso, es necesario actualizar el albarán para registrar correctamente y actuar en el código de disposición que se especifica debido a la cuarentena. El confirmación se puede enviar al cliente cuando se registra la línea de devolución. ** Confirmación de devolución ** el informe es similar al documento de pedido de devolución. ** Confirmación de devolución ** el informe no se registra en el diario ni se registra lo contrario en el sistema, y no es un paso obligatorio en el proceso del pedido de devolución.

## <a name="replace-a-product"></a>Sustituir un producto
Existen dos métodos para administrar sustitución del producto:

-   ** Sustitución creada anteriormente ** – Replace un producto antes de que el producto devuelto se reciba del cliente.
-   ** El sustitución por código de disposición ** – crea automáticamente una nueva línea del pedido de devolución.

### <a name="up-front-replacement"></a>Sustitución creada anteriormente

En el sustitución inicial, el artículo de sustitución se puede entregar al cliente antes de que se devuelva el artículo. Este método resulta útil si, por ejemplo, el artículo es parte del equipo que no puede quitar a menos que un recambio esté disponible tomar su lugar, o bien si sólo desea que su cliente tengan el artículo de sustitución lo más rápidamente posible. El pedido de sustitución inicial es un pedido de ventas independiente. La información de encabezado inicializa del cliente, y la información de línea se inicializa del pedido de devolución. Puede editar, procesar, y eliminar el pedido de sustitución independientemente del pedido de devolución. Al eliminar un pedido de sustitución, recibirá un mensaje indicando que la creación del pedido como un pedido de sustitución. La ilustración siguiente muestra el proceso para la sustitución inicial.  

[] proceso inicial de sustitución![(https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn04.png) (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn04.png)]  

El pedido de devolución incluye una referencia al pedido de sustitución. Si un pedido de sustitución inicial se crea para un pedido de devolución antes de que se devuelva el artículo defectuoso, no puede seleccionar los códigos de disposición para la sustitución después de que se haya devuelto el artículo defectuoso.

### <a name="replacement-by-disposition-code"></a>Sustitución por código de disposición

Si envía un artículo de sustitución al cliente, y utiliza ** reemplace y deseche ** o ** reemplace ** crédito y la acción de disposición del pedido de devolución, use el proceso que se muestra en la siguiente ilustración.  

[proceso de sustitución![Cuando se utiliza un código de disposición (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn05.png)] (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn05.png)]  

El artículo de sustitución se entregará mediante un pedido de ventas independiente, el pedido de ventas de sustitución. Se crea este pedido de ventas cuando el albarán para el pedido de devolución se genera. El encabezado del pedido utiliza información del cliente a la que se hace referencia en el encabezado del pedido de devolución. La información de línea se obtiene de la información especificada en ** artículo de sustitución ** la página. ** Artículo de sustitución ** la página se debe completar para las líneas con acciones de disposición que comienzan por la palabra “de”. Sin embargo, no la cantidad ni la identidad del artículo de sustitución se valida o está limitado. Este comportamiento permite casos en los que el cliente desea recibir el mismo artículo pero en una configuración diferente o un tamaño, y también los casos en los que los clientes desean completamente un artículo diferente. De forma predeterminada, un mismo artículo se especifica en ** artículo de sustitución ** la página. Sin embargo, puede seleccionar un artículo diferente, siempre que se ha configurado la función. ** Nota: ** Puede editar y eliminar el pedido de ventas de sustitución después de que haya creado.

## <a name="generate-a-packing-slip"></a>Generar un albarán
Antes de que se puedan recibir los artículos devueltos en el inventario, debe actualizar el albarán del pedido que los artículos pertenecen. Del mismo modo que el proceso de actualización de facturas es la actualización de la transacción financiera, el proceso de actualización de albaranes es la actualización física del registro de inventario. Es decir este proceso envía los cambios al inventario. En el caso de las devoluciones, los pasos que se asignan a la acción de disposición se implementan durante la actualización del albarán. Cuando se genera el albarán, los eventos siguientes:

-   En el almacén, el proceso estándar se usa para realizar una recepción física. Se generan los registros contables si el grupo de modelos de inventario (** envíe el inventario físico **) y los parámetros de clientes (** albarán en la contabilidad **) se configuran como corresponda.
-   Se dados los artículos que se han marcado con una acción de disposición que contiene la palabra “,” residuos y la pérdida del inventario están registradas en la contabilidad.
-   Los artículos que se han marcado con ** Devolución al cliente ** la acción de disposición se reciben y se entregan al cliente. Estos artículos no tienen efecto neto en inventario.
-   Se crea un pedido de ventas de sustitución. Este pedido de ventas se basa en la información de ** artículo de sustitución ** la página.

Puede generar el albarán sólo para las líneas de las que tengan el estado Restablecer ** registrado **, y sólo para toda la cantidad en la línea de devolución. Si varias líneas del pedido de devolución tienen ** registrado ** el estado, puede generar el albarán para un subconjunto de las líneas eliminando las otras líneas ** albarán Registrar ** de la página. Los devoluciones parciales se definen en términos de líneas de pedido de devolución, no en términos de envíos al pedido de devolución. Por lo tanto, si recibe la cantidad completa que se indica en una línea de pedido de devolución, pero no recibe ninguna cantidad de las demás líneas del pedido de devolución, ésta no es una entrega parcial. Sin embargo, si en una línea de pedido de devolución requiere que 10 unidades de un artículo estén devueltas, pero se las cuatro unidades, RO entrega es una entrega parcial. Si no llegan todos los artículos de la devolución que se esperaban, puede establecer el envío en una ubicación y esperar el resto de la cantidad devuelta para su llegada. Como alternativa, puede registrar y registrar la cantidad parcial. Como parte del proceso de registro de albaranes, puede asociar el número de referencia del albarán de los documentos de envío del cliente con las líneas de pedido. Esta asociación es opcional y tiene una finalidad informativa. No crea ninguna actualización transaccional. Puede omitir normalmente el proceso de albarán y cambie directamente a la facturación. En este caso, los pasos que se habría efectuado durante la generación del albarán se completan durante la facturación.

## <a name="generate-an-invoice"></a>Generar factura
Aunque ** pedido de devolución ** la página contenga la información y las acciones que se requieren para gestionar los aspectos logísticos especiales del pedido de devolución, debe usar ** pedido de ventas ** la página para completar el proceso de facturación. Su organización continuación puede facturar pedidos de devolución y pedidos de ventas a la vez, y la misma persona puede completar el proceso de facturación, según convenga. Para ver el pedido de devolución ** pedido de ventas ** de la página, haga clic en el vínculo para que el número de pedido de venta abra el pedido de ventas asociado. También puede encontrar el pedido de devolución ** en todos los pedidos de ventas ** la página. Los pedidos de devolución son los pedidos de ventas desde los que tiene un tipo de pedido ** pedido devuelto **.

### <a name="credit-correction"></a>Corrección de crédito

Como parte del proceso de facturación, compruebe que los gastos varios es correcto. Para hacer registros contables para hacer correcciones (Storno), considere usar ** corrección de crédito ** la opción en otra ** ** la ficha ** registro de factura ** de la página al registrar la factura o la nota de abono. ** Nota: ** De forma predeterminada, ** corrección de crédito ** se activa la opción si ** nota de abono como corrección ** la opción en ** los parámetros de clientes ** la página se ha habilitado. Sin embargo, se recomienda no registra devoluciones a Storno.

## <a name="create-intercompany-return-orders"></a>Crear pedidos de devolución de empresas vinculadas
Los pedidos de devolución se pueden completar entre dos empresas de la organización. Se admiten los siguientes escenarios:

-   Las empresas vinculadas simples vuelven entre dos empresas que participan en una relación de empresas vinculadas
-   Una cadena de empresas vinculadas se establece cuando un pedido de devolución de cliente se crea en la empresa vendedora
-   Una cadena de empresas vinculadas se establece cuando un pedido de devolución del proveedor se crea en la empresa compradora
-   El envío de entrega directa vuelve entre un cliente externo y dos empresas que participan en una relación de empresas vinculadas

### <a name="setup"></a>Configuración

La ilustración siguiente la configuración mínima que se requiere para dos empresas participen en una relación de empresas vinculadas y se aprovechen de comercio entre empresas vinculadas.  

[![Minimum setup](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn06.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn06.png)  

En el escenario siguiente, CompBuy es la empresa compradora y, a CompSell es la empresa vendedora. Normalmente, la empresa vendedora envían los artículos a la empresa compradora o, en escenarios directas de envío de la entrega, directamente al cliente final. En CompBuy, el proveedor se ha definido IC\_CompSell como extremo de empresas vinculadas que esté asociada a la empresa CompSell. Al mismo tiempo, en CompSell, se define el cliente\_IC CompBuy como extremo de empresas vinculadas que esté asociada a la empresa CompBuy. Los detalles y las asignaciones de valores de la directiva de la acción adecuada se deben definir en ambas empresas. En un escenario directa de envío de la entrega, un pedido de devolución de empresas vinculadas, que es también un pedido de ventas de empresas vinculadas, se crea en la empresa vendedora. El número RMA desde el pedido de devolución de empresas vinculadas se puede escoger de la secuencia del número RMA en CompSell, o puede ser copiado del número RMA asignado al pedido de devolución original en CompBuy. Los valores de número RMA en ** PurchaseRequisition ** la directiva de acciones CompBuy determinan en estas acciones. Si se sincroniza el número RMA, debe planificar para mitigar el riesgo de conflictos del número si las dos empresas usan la misma secuencia numérica.

### <a name="simple-intercompany-returns"></a>Devoluciones simples de empresas vinculadas

Esta situación implica dos empresas de la misma organización, como se muestra en la siguiente ilustración.  

[] simple devolución de empresas vinculadas![(https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn07.png) (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn07.png)]  

La cadena del pedido se puede liquidar cuando un pedido de devolución del proveedor se crea en la empresa compradora o un pedido de devolución de cliente se crea en la empresa vendedora. La Dynamics 365 para las operaciones crea corresponder pedido en la otra empresa y asegúrese de que el encabezado y la información de línea en el pedido de devolución del proveedor refleja los valores en el orden de la devolución del cliente. El pedido de devolución se establece que puede incluir o excluir la referencia (** pedido de ventas de la búsqueda **) a una factura de cliente existente. Los albaranes y las facturas de los dos pedidos se pueden procesar individualmente. Por ejemplo, no es necesario generar un albarán para el pedido de devolución del proveedor antes de generar el albarán para el pedido de devolución de cliente.

### <a name="direct-delivery-shipment-returns-among-three-parties"></a>Devoluciones directos de envío de entrega entre tres partes

Este escenario se puede liquidar si una venta anterior ** entrega directa ** del tipo se ha completado y, si una factura con el cliente existe en la empresa que interactúa con el cliente. En la siguiente ilustración, la empresa CompBuy haya vendido anteriormente y los productos facturados al cliente Extern. Los productos se registraron directamente de la empresa CompSell al cliente mediante una cadena de pedidos de empresas vinculadas.  

[devoluciones directas de envío de la entrega![entre tres partes (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn08.png)] (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn08.png)]  

Si el cliente Extern desea devolver los productos, un pedido de devolución (RMA02) se crea para el cliente en la empresa CompBuy. Para establecer la cadena de empresas vinculadas, el pedido de devolución se debe marcar para entrega directa. Cuando usa ** pedido de ventas de la búsqueda ** trabaja para seleccionar la factura de cliente para volver, una cadena de pedidos de empresas vinculadas se establece que consiste en los siguientes documentos:

-   ** Pedido de devolución original: ** RMA02 (empresa CompBuy)
-   ** Pedido de compra: ** PO02 (empresa CompBuy)
-   ** Pedido de devolución de empresas vinculadas: ** RMA\_00032 (empresa CompSell)

Una vez creada la cadena de empresas vinculadas de entrega directa, toda la comprobación que gestiona y que procesa de las devoluciones debe aparecer en el contexto del pedido de devolución de empresas vinculadas, RMA\_00032 en la empresa CompSell. Los productos no se pueden recibir en la empresa CompBuy. Cuando un código de disposición se asigna al pedido de devolución de empresas vinculadas, ha sincronizado con el pedido de devolución original de permitir la facturación adecuada del pedido original.

## <a name="post-to-the-ledger"></a>Registrar en la contabilidad
Los registros contables que se generan cuando se factura el pedido de devolución se de influidas por algunas opciones y parámetros importantes:

-   ** El precio de coste de devolución ** – para modelos de inventario distinto de coste estándar ** ** **, el precio de coste de devolución ** el parámetro determina el coste del artículo si ha aceptado al inventario o baja. Para calcular una evaluación de inventario correcta, es importante establecer ** el precio de coste de devolución ** el parámetro correctamente. Si usa ** pedido de ventas de la búsqueda ** funciona para crear una línea de pedido de devolución que tenga una referencia a una factura de cliente, ** el precio de coste de devolución ** el valor es igual al precio de coste del artículo vendidos. Si no, el valor del precio de coste procede del artículo configurar o se puede especificar manualmente.
-   ** La/Storno corrección de crédito ** – ** corrección de crédito ** el parámetro en ** registro de factura ** la página determina si los registros se deben registrar como entradas DR/CR positivas () o como corrigiendo, las entradas negativas.

En los ejemplos siguientes, el precio de coste de devolución se representa como ** Inv. Precio de coste **.

### <a name="example-1-the-return-order-doesnt-reference-a-customer-invoice"></a>Ejemplo 1: El pedido de devolución no hace referencia una factura de cliente

El pedido de devolución no hace referencia una factura de cliente. Se abona el artículo devuelto. ** Corrección de crédito ** el parámetro no se activa cuando se genera la factura del pedido de devolución, o la nota de abono.  

[el pedido de devolución![no hace referencia a un cliente invoic (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn09.png)] (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn09.png)]  

** Nota: ** El precio del artículo maestro se usa como el valor predeterminado para ** el precio de coste de devolución ** el parámetro. El precio predeterminado difiere del precio de coste en el momento de la emisión de inventario. Por lo tanto, la implicación que es una pérdida de 3 se ha incurrido. Además, el pedido de devolución no incluye el descuento que se ha concedido al cliente en el pedido de ventas. Por lo tanto, un crédito excesivo aparece.

### <a name="example-2-credit-correction-is-selected-for-the-return-order"></a>Ejemplo 2: La corrección de crédito se selecciona para el pedido de devolución

El ejemplo 2 es el mismo que el ejemplo 1, pero ** corrección de crédito ** se selecciona el parámetro cuando se genera la factura del pedido de devolución.  

[pedido de devolución![en la que la corrección de crédito (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn10.png)] (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn10.png)]  

** Nota: ** Los registros contables se especifican como correcciones negativas.

### <a name="example-3-the-return-order-line-is-created-by-using-the-find-sales-order-function"></a>Ejemplo 3: La línea de pedido de devolución se crea mediante la función del pedido de ventas de la búsqueda

En este ejemplo, la línea de pedido de devolución se crea mediante ** pedido de ventas de la búsqueda ** la función. ** Corrección de crédito ** el parámetro no se activa cuando se crea la factura.  

[línea de pedido de devolución![que se crea mediante el pedido de ventas] de la búsqueda (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn11.png) (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn11.png)]  

** Nota: ** ** Descuento ** ** y el precio de coste de devolución ** se han configurado correctamente. Por lo tanto, una inversión precisa de la factura de cliente aparece.


