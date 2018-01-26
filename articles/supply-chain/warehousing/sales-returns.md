---
title: Devoluciones de ventas
description: "Este tema ofrece información sobre los procesos para devolver pedidos. Incluye información sobre las devoluciones de clientes y su efecto en la gestión de costes y cantidades disponibles de inventario."
author: omulvad
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReturnTableListPage
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.assetid: 98a4b517-e606-4036-b55f-1ab248898bdf
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: fa56911c19e9b6514829084221ba03c7cd421c92
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="sales-returns"></a>Devoluciones de ventas

[!include[banner](../includes/banner.md)]


Este tema ofrece información sobre los procesos para devolver pedidos. Incluye información sobre las devoluciones de clientes y su efecto en la gestión de costes y cantidades disponibles de inventario.

Los clientes pueden devolver artículos por varios motivos. Por ejemplo, un artículo puede estar defectuoso o es posible que no cumpla las expectativas del cliente. El proceso de devolución comienza cuando un cliente emite una solicitud para devolver un artículo. Después de que se recibe la solicitud del cliente, se crea un pedido de devolución en Microsoft Dynamics 365 for Finance and Operations.

## <a name="return-order-process"></a>Proceso de pedido de devolución
La ilustración siguiente muestra una visión general del proceso de devolución de pedidos.  

[![Proceso de pedido de devolución](./media/salesreturns01.jpg)](./media/salesreturns01.jpg)  

Existen dos tipos de proceso del pedido de devolución: devolución y comprobar crédito solo.

-   **Devolución física:** el pedido de devolución autoriza la devolución física de productos.
-   **Solo a crédito**: el pedido de devolución autoriza un crédito de clientes pero no requiere que el cliente devuelva físicamente los productos.

### <a name="physical-return-order-process"></a>Proceso de devolución física de pedidos

1.  **Crear un pedido de devolución.** Documente formalmente la autorización para que el cliente devuelva cualquier producto defectuoso o no deseado. El pedido de devolución no requiere que la empresa acepte los productos devueltos o proporcione un crédito para el cliente. Si se aprueba la devolución, puede autorizar que se envíe la sustitución de un artículo antes de que se haya devuelto el artículo defectuoso.
2.  **Entrega en almacén para su inspección.** Complete una inspección inicial y una validación con respecto al documento de pedido de devolución. El pedido de devolución también admite la cuarentena de los artículos devueltos para una inspección adicional y control de calidad.
3.  **Determinar la disposición.** Finalice el proceso de inspección y decida qué se debe hacer con los productos devueltos. Como parte de este paso, decida si abonará la devolución al cliente, rechazará la devolución del producto o aceptará la devolución del producto, desechará el producto y enviará posteriormente un artículo de sustitución al cliente.
4.  **Generar un alabaran.** Genere un albarán y confirme la decisión de disposición del paso 3. Finalice los procesos de logística.
5.  **Generar una factura.** Cierre el pedido de devolución.

### <a name="credit-only-process"></a>Proceso de crédito solo

1.  **Crear un pedido de devolución.** Documente formalmente la autorización para que el cliente reciba un abono sin devolver el producto defectuoso o no deseado. El código de disposición de **Crédito sólo** autoriza la decisión de abonar al cliente sin que haya devolución física.
2.  **Generar una factura.** Generar la nota de crédito y cerrar el pedido de devolución.

## <a name="return-material-authorization"></a>Autorización de devolución de material
El proceso de la autorización de devolución de materiales (RMA) se re fundamenta en la funcionalidad de pedidos de venta. Una RMA se registra como un pedido de devolución, que se crea como un pedido de ventas, y puede tener otro pedido de ventas asociado a él, denominado un pedido de sustitución. Ambos pedidos de ventas se vinculan al número de RMA que los origina.

-   **Pedido de devolución:** para registrar una RMA, debe crear un pedido de devolución, que es un pedido de ventas que tiene el tipo asignado, **Pedido devuelto.** Los cambios que realice a la información de RMA se actualizan automáticamente en el pedido de ventas. Hasta que el pedido de devolución no tenga el estado **Abierto**, no aparecerá en la lista de pedidos de ventas. Use la RMA para gestionar la llegada y la recepción de los artículos devueltos, así como para autorizar acción de solo disposición de crédito (consulte la sección **Códigos de disposición y acciones de disposición**). El resto de los procesos de seguimiento se deben gestionar en el pedido de ventas.
-   **Pedido de sustitución:** cuando un pedido de sustitución se debe enviar al cliente, la RMA puede incluir un segundo pedido de ventas asociado. Puede crear manualmente el pedido de sustitución para la RMA para que admita un envío inmediato. De manera alternativa, el pedido de sustitución se puede crear automáticamente después de completar la llegada, la inspección y la recepción para el artículo de línea de RMA que tiene un código de disposición que indica la sustitución. El pedido de sustitución tiene la misma funcionalidad que está asociada a un pedido de ventas. Por ejemplo, puede utilizarlo para configurar un producto personalizado como el artículo de sustitución, crear un pedido de producción reparar de un artículo devuelto, crear un pedido de compra de entrega directa para enviar la sustitución desde un proveedor o para que admita otros propósitos.

## <a name="create-a-return-order"></a>Crear un pedido de devolución
El proceso de pedido de devolución comienza cuando un cliente contacta su organización para devolver un producto defectuoso o no deseado y/o para recibir el abono. Una vez que la organización acepte la devolución, la devolución se documenta a través de un pedido de devolución. Este pedido de devolución se convierte en el punto en el que se centra el procesamiento interno para el producto devuelto. La ilustración siguiente muestra el procedimiento para crear un pedido de devolución.  

[![Procedimiento para crear un pedido de devolución](./media/salesreturn02.png)](./media/salesreturn02.png)

### <a name="create-a-return-order-header"></a>Crear un encabezado de pedido de devolución

Al crear un pedido de devolución, es preciso incluir la información de la siguiente tabla.

| Campo              | Descripción                                              | Comentarios                                                                                                                                                                                                                                                                                                                                        |
|--------------------|----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Cuenta de cliente   | Una referencia a la tabla Clientes                       | Debe proporcionar una cuenta de cliente existente.                                                                                                                                                                                                                                                                                                  |
| Dirección de entrega   | La dirección a la que se devuelve el artículo.                 | De forma predeterminada, se usa la dirección de la organización. Si selecciona un almacén específico en el encabezado, cambia a la dirección de entrega a la dirección de entrega del almacén. Puede cambiar esta dirección en la página **Detalles de devolución del pedido**.                                                                                                  |
| Sitio/almacén     | El sitio o almacén que recibe el producto devuelto | La dirección de entrega del pedido de devolución se determina según la dirección de entrega del sitio o almacén.                                                                                                                                                                                                                                 |
| Número RMA         | El identificador que se asigna al pedido de devolución              | El número de RMA se usa como clave alternativa en el proceso del pedido de devolución. El número de RMA que se asigna en función de la secuencia numérica del RMA que se configura en la página **Parámetros de clientes**.                                                                                                                              |
| Fecha límite           | La última fecha en que se puede devolver el artículo.               | El valor predeterminado se calcula como la fecha actual más el periodo de validez. Por ejemplo, si una devolución es válida únicamente por 90 días a partir de la fecha en la que se creó el pedido de devolución, y se creó el pedido de devolución el 1 de mayo, el valor del campo es **30 de julio**. El período de validez se establece en la página **Parámetros de clientes**. |
| Código de motivo de devolución | El motivo del cliente para devolver el producto          | El código del motivo se selecciona en la lista de códigos de motivos definido por el usuario. Puede actualizar este campo en cualquier momento.                                                                                                                                                                                                                                    |

### <a name="create-return-order-lines"></a>Crear línea de pedido de devolución

Después de finalizar la encabezado de devolución, puede crear líneas de devolución mediante uno de los métodos siguientes:

-   Especifique manualmente los detalles del artículo, la cantidad, y otra información para cada línea de devolución.
-   Cree una línea de devolución mediante la función **Buscar pedido de ventas**. Se recomienda usar esta función al crear un pedido de devolución. La función **Buscar pedido de ventas** establece una referencia desde la línea de devolución a la línea del pedido de ventas facturado y recupera los detalles de línea como número de artículo, la cantidad, el precio, el descuento y los valores de coste de la línea de ventas. La referencia ayuda a garantizar que, cuando el producto se devuelve a la empresa, se ha valorado según el mismo coste unitario al que se vendió. La referencia también valida que los pedidos de devolución no están creados para una cantidad que excede la cantidad a la que se vendió en la factura.

**Nota:** Las líneas de devolución que tienen una referencia a un pedido de ventas se gestionan como correcciones o reversiones de la venta. Para obtener más información, consulte la sección sobre anotar asientos en el libro mayor más adelante en este tema.

### <a name="charges"></a>Gastos

Las cuotas y los gastos se pueden agregar al pedido de devolución a través de uno o más de los métodos siguientes:

-   Puede agregar manualmente gastos al encabezado del pedido de devolución, la línea de pedido de devolución o ambos.
-   Los gastos pueden agregarse automáticamente al encabezado del pedido de devolución en función del código de motivo de devolución.
-   Los gastos pueden agregarse automáticamente a la línea de pedido de devolución, en función del código de disposición de la línea.

Los gastos se agregan automáticamente después de que un código de motivo de devolución o un código de disposición se asigna a la línea. Si el código de motivo se cambia posteriormente, la entrada existente del gasto no se eliminará, pero es posible que se agregue una nueva entrada del gasto, en función del nuevo código de motivo. Al agregar gastos a las líneas de pedidos de devolución, los gastos se calculan como un porcentaje de la línea o el valor del pedido se convierte en negativo cuando la línea o el pedido de la línea es negativo, a menos que el porcentaje sea también un número negativo. Un cargo que tiene un valor negativo representa un abono al cliente.

### <a name="return-reason-codes"></a>Códigos de motivo de devolución

Al aplicar códigos de motivo a las devoluciones, puede ayudar a crear patrones de devolución más fáciles analizar. Los códigos de motivo proporcionan información sobre por qué un cliente desea devolver artículos. Algunas organizaciones tienen muchos códigos de motivo. Estas organizaciones pueden agrupar los códigos de motivo en grupos de códigos de motivo para obtener una mejor visión general y para los informes acumulados.

### <a name="disposition-codes-and-disposition-actions"></a>Códigos de disposición y acciones de disposición

Un paso importante en el proceso del pedido de devolución es la asignación de un código de disposición a la línea de pedido de devolución como parte de registro de llegada. El código de disposición determina la siguiente información:

-   **Implicaciones financieras:** ¿debe realizarse un abono al cliente por los artículos devueltos y deben aplicarse cargos a la línea de pedido de devolución?
-   **La disposición del artículo devuelto:** ¿debe agregarse de nuevo el artículo a inventario, se debe cancelar o debe devolverse al cliente?
-   **La logística del artículo devuelto:** ¿se debe enviar un artículo de sustitución al cliente?

Además de determinar qué se hace con las mercancías devueltas, los códigos de disposición pueden ocasionar gastos que se aplicarán a la línea de devolución. También se pueden usar para agrupar las devoluciones para realizar análisis estadísticos. Los códigos de disposición se definen como parte de la configuración de los pedidos de devolución. Sin embargo, cada código de disposición debe hacer referencia a una de las acciones de disposición integradas. La tabla siguiente proporciona una lista de los códigos de disposición y sus acciones. **Importante:** si no se va a devolver un artículo, pero el cliente debe recibir el abono, asigne el código de disposición **Solo abono** a la línea de devolución.

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
<li>Se abona al cliente el precio de venta menos las cuotas o gastos.</li>
<li>La pérdida por rechazar el artículo se registra en la contabilidad.</li>
</ul></td>
<td>No se deber devolver el artículo. Esta acción de disposición se usa para los casos siguientes:
<ul>
<li>Existen suficiente confianza entre las partes.</li>
<li>El coste para devolver el artículo defectuoso es prohibitivo.</li>
<li>Los artículos no se pueden volver a incluir en el inventario. Debido a otras condiciones, no se requiere una devolución física.</li>
</ul></td>
</tr>
<tr class="even">
<td>Crédito</td>
<td><ul>
<li>Se abona al cliente el precio de venta menos las cuotas o gastos.</li>
<li>El valor de inventario se incrementa según el coste del artículo devuelto.</li>
</ul></td>
<td>El artículo se devuelve y se agrega al inventario.</td>
</tr>
<tr class="odd">
<td>Reemplazar y abonar</td>
<td><ul>
<li>Se abona al cliente el precio de venta menos las cuotas o gastos.</li>
<li>El valor de inventario se incrementa según el coste del artículo devuelto.</li>
<li>Un pedido de ventas individual para una sustitución se crea y se gestiona por separado.</li>
</ul></td>
<td>El artículo se devuelve y se agrega al inventario.</td>
</tr>
<tr class="even">
<td>Reemplazar y cancelar</td>
<td><ul>
<li>Se abona al cliente el precio de venta menos las cuotas o gastos.</li>
<li>La pérdida por rechazar el artículo se registra en la contabilidad.</li>
<li>Un pedido de ventas individual para una sustitución se crea y se gestiona por separado.</li>
</ul></td>
<td>Se devuelve y se cancela el artículo.</td>
</tr>
<tr class="odd">
<td>Devolver al cliente</td>
<td>Ninguno, salvo cuotas o cargos.</td>
<td>Se devuelve el artículo, pero se envía de nuevo al cliente tras la inspección. Esta acción de disposición puede usarse si el artículo se ha dañado deliberadamente o si se ha anulado la garantía.</td>
</tr>
<tr class="even">
<td>Residuo</td>
<td><ul>
<li>Se abona al cliente el precio de venta menos las cuotas o gastos.</li>
<li>La pérdida por rechazar el artículo se registra en la contabilidad.</li>
</ul></td>
<td>Se devuelve o se cancela el artículo.</td>
</tr>
</tbody>
</table>

## <a name="arrival-at-the-warehouse-for-inspection"></a>Entrega en almacén para su inspección.
Antes de que pueda recibir físicamente artículos devueltos en el inventario mediante la creación de un albarán, los artículos deben pasar el registro de llegada y una inspección opcional. La ilustración siguiente muestra una visión general del proceso de solicitud de entrada. Las secciones siguientes describen cada paso que se muestra en la ilustración.  

[![Proceso de entrada](./media/salesreturn03.png)](./media/salesreturn03.png)  

El proceso tiene otras variantes que no se abordan en este tema. Estas son algunas de estas variaciones:

-   No use la lista **Visión general de entradas** para crear un diario de entradas. En su lugar, cree manualmente el diario de entradas. Los pedidos de devolución tendrán **Pedido de ventas** como referencia.
-   Si utiliza la gestión de almacenes, genere los transportes de pallet La línea de devolución tendrá un estado **Entregado** durante el transporte de pallet.
-   Registre la llegada del artículo devuelto directamente desde la línea de pedido de devolución, mediante la función **Registro**.

Durante el proceso de llegada, las devoluciones se integran con el proceso general para entradas en almacén. El proceso de entrada también admite la creación de órdenes de cuarentena para los artículos devueltos deben pasar por una inspección independiente.

### <a name="identify-products-in-the-arrival-overview-list"></a>Identificar los productos de la lista de la Visión general de entradas

La **Visión general de entradas** muestra todas las entradas planificadas. **Nota:** Las llegadas de pedidos de devolución se deben procesar por separado de otros tipos de transacciones de entrada. Una vez haya identificado un paquete de entrada en la página **Visión general de entradas** (por ejemplo, con el documento de RMA asociado), en el panel de acciones, haga clic en **Iniciar entrada** para crear y inicializar a un diario de entradas que coincida con la llegada.

### <a name="edit-the-arrival-journal"></a>Editar el diario de entradas

Si establece la opción **Gestión de cuarentena** en **Sí**, puede crear un pedido de cuarentena para la línea de devolución. Si una línea se ha enviado a cuarentena para inspección, no puede especificar un código de disposición. **Nota:** Si establece la opción **Gestión de cuarentena** en **Sí** en el grupo de modelos de inventario de artículos, la opción **Gestión de cuarentena** en la página **Líneas de diario** se marcará para la línea del diario de entradas y no se podrá modificar. Si la línea se envía a cuarentena, debe especificar el almacén de cuarentena adecuado. Si la línea de entrada no se envía para inspección, el encargado de las llegadas en el almacén debe especificar el código de disposición directamente en la línea del diario de entradas y anotarlo en el diario de recepción. Si el mismo código de disposición no se va a asignar a toda la cantidad de la línea de devolución o si la cantidad total de la línea no se ha recibido, debe dividir la línea. Al dividir una línea del diario de entrada, también divide la línea de devolución (**SalesLine**) y crea un nuevo identificador del lote. Puede dividir la línea reduciendo la cantidad de la línea del diario de entradas. Cuando se registra el diario, se crea una nueva línea de devolución que tiene un estado **Esperado** para la cantidad restante. También puede dividir la línea si hace clic en **Funciones** &gt; **Dividir**.

### <a name="process-the-quarantine-order"></a>Proceso de la orden de cuarentena

Si los productos devueltos se envían para inspección en el almacén de cuarentena, cualquier procesamiento adicional se completa en una orden de cuarentena. Las órdenes de cuarentena se crean para cada línea de entrada que se envía a cuarentena. El código de disposición indica el resultado del proceso de inspección. Puede dividir un pedido de cuarentena, igual que puede dividir el diario de entrada. Si divide el pedido de cuarentena, puede producirse una división consecuente de la línea de devolución. Después de que se especifica el código de disposición, complete el pedido de cuarentena la función **Finalizar** o la función **Notificar como terminado**. Si selecciona **Notificar como finalizado**, se crea una nueva entrada en el almacén designado. A continuación, puede procesar esta llegada mediante la página **Visión general de las entradas**. Si la entras se origina desde un pedido de cuarentena, no podrá cambiar el código de disposición que se asigna durante la inspección. Si completa el orden de cuarentena mediante la función **Finalizar**, el lote se registra automáticamente. En ocasiones, un artículo se puede volver a enviar desde cuarentena al departamento de envíos y recepciones. Por ejemplo, el inspector de cuarentena es posible que no sepa dónde almacenar el artículo en el inventario. En este caso, es necesario actualizar el albarán para hacer el registro correctamente y actuar sobre el código de disposición que se especifica debido a la cuarentena. Se puede enviar la confirmación de recepción al cliente cuando se registra la línea de devolución. El informe **Confirmación de devolución** es similar al documento de pedido de devolución. El informe **Confirmación de devolución** no se registra en el diario ni de otro modo en el sistema, y no es un paso obligatorio en el proceso del pedido de devolución.

## <a name="replace-a-product"></a>Sustituir un producto
Existen dos métodos para gestionar la sustitución del producto:

-   **Sustitución creada anteriormente:** se sustituye un producto antes de que el producto devuelto se reciba del cliente.
-   **Sustitución por código de disposición**: crea automáticamente una nueva línea del pedido de devolución.

### <a name="up-front-replacement"></a>Sustitución creada anteriormente

En la sustitución creada anteriormente, el artículo de sustitución se puede entregar al cliente antes de que se devuelva el artículo. Este método resulta útil si, por ejemplo, el artículo es parte de una máquina que no se puede quitar a menos que un recambio esté disponible para tomar su lugar o bien si solo desea que su cliente tenga el artículo de sustitución lo más rápidamente posible. El pedido de sustitución creado anteriormente es un pedido de ventas independiente. La información del encabezado se inicializa desde el cliente, y información de línea se inicializa desde el pedido de devolución. Puede editar, procesar, y eliminar el pedido de sustitución independientemente del pedido de devolución. Al eliminar un pedido de sustitución, recibirá un mensaje indicando la creación del pedido como un pedido de sustitución. La ilustración siguiente muestra el proceso para la sustitución creada anteriormente.  

![Proceso de sustitución creado anteriormente](./media/SalesReturn04.png)

El pedido de devolución incluye una referencia al pedido de sustitución. Si un pedido de sustitución creado anteriormente se crea para un pedido de devolución antes de que se devuelva el artículo defectuoso, no puede seleccionar los códigos de disposición para la sustitución después de que se haya devuelto el artículo defectuoso.

### <a name="replacement-by-disposition-code"></a>Sustitución por código de disposición

Si envía un artículo de sustitución al cliente y utiliza la acción de disposición **Reemplazar y cancelar** o **Reemplazar y abonar** en el pedido de devolución, use el proceso que se muestra en la siguiente ilustración.  

![Proceso de sustitución cuando se usa un código de disposición](./media/SalesReturn05.png)

El artículo de sustitución se entregará mediante un pedido de ventas independiente, el pedido de ventas de sustitución. Se crea este pedido de ventas cuando se genera el albarán para el pedido de devolución. El encabezado del pedido utiliza información del cliente a la que se hace referencia en el encabezado del pedido de devolución. La información de línea se obtiene de la información que se especifica en la página **Artículo de sustitución**. La página **Artículo de sustitución** se debe completar para las líneas con acciones de disposición que comienzan por la palabra “sustitución". Sin embargo, ni la cantidad ni la identidad del artículo de sustitución se valida o limita. Este comportamiento permite casos en los que el cliente desea recibir el mismo artículo, pero en una configuración o tamaño diferentes y también los casos en los que los clientes desean un artículo completamente diferente. De forma predeterminada, los artículos idénticos se especifican en la página **Artículo de sustitución**. Sin embargo, puede seleccionar un artículo diferente, siempre que la función se haya configurado. **Nota:** Puede editar y eliminar el pedido de ventas de sustitución después de que se haya creado.

## <a name="generate-a-packing-slip"></a>Generar un albarán
Antes de recibir los artículos devueltos en el inventario, es preciso que actualice el albarán para el pedido al que pertenecen los artículos. Del mismo modo que el proceso de actualización de facturas es la actualización de la transacción financiera, el proceso de actualización de albaranes es la actualización física del registro de inventario. es decir, este proceso envía los cambios al inventario. En el caso de las devoluciones, los pasos que se asignan a la acción de disposición se implementan durante la actualización del albarán. Cuando se genera el albarán, se producen los eventos siguientes:

-   En el almacén, el proceso estándar se usa para realizar una recepción física. Se generan los registros contables si el grupo del modelo de inventario (**Registrar inventario físico**) y los parámetros de clientes (**Registrar el albarán**) se establecen debidamente.
-   Los artículos que se han marcado con una acción de disposición que contiene la palabra "cancelar“ se cancelan y la pérdida del inventario se registra en la contabilidad.
-   Los artículos que se han marcado con la acción de disposición **Devolver al cliente** se reciben y se entregan al cliente. Estos artículos no tienen efecto neto en el inventario.
-   Se ha creado el reemplazo de pedido de ventas. Este pedido de ventas se basa en la información de la página **Artículo de sustitución**.

Puede generar el albarán solo para las líneas de las que tengan el estado de devolución **Registrado** y solo para toda la cantidad en la línea de devolución. Si varias líneas del pedido de devolución tienen el estado **Registrado**, puede generar el albarán para un subconjunto de las líneas eliminando las otras líneas de la página **Registrar albarán**. Las devoluciones parciales se definen en términos de líneas de pedidos de devolución, no de envíos de pedidos de devolución. Por lo tanto, esto significa que si recibe la cantidad completa que se indica en una línea del pedido de devolución pero no recibe ninguna cantidad de las demás líneas del pedido de devolución, ésta no es una entrega parcial. Sin embargo, si en una línea del pedido de devolución se solicitan 10 unidades de un artículo que se va a devolver, pero se reciben sólo cuatro unidades, la entrega es una entrega parcial. Si no llegan todos los artículos de la devolución que se esperaban, puede apartar el envío y esperar a que llegue el resto de la cantidad a devolver. Como alternativa, puede registrar la cantidad parcial. Como parte del proceso de registro de albaranes, puede asociar el número de referencia del albarán de los documentos de envío del cliente también a las líneas de pedido. Esta asociación es opcional y tiene una finalidad informativa. No crea ninguna actualización transaccional. Por lo general, puede omitir el proceso de albarán y cambiar directamente a la facturación. En este caso, los pasos que se habrá efectuado durante la generación del albarán se completan durante la facturación.

## <a name="generate-an-invoice"></a>Generar factura
Aunque la página **Pedido de devolución** contenga la información y las acciones que se requieren para gestionar los aspectos logísticos especiales del pedido de devolución, debe usar la página **Pedido de ventas** para completar el proceso de facturación. Su organización podrá después facturar pedidos de devolución y pedidos de ventas a la vez y la misma persona puede completar el proceso de facturación, según convenga. Para ver el pedido de devolución de la página **Pedido de ventas**, haga clic en el vínculo para que el número de pedido de venta abra el pedido de ventas asociado. También puede encontrar el pedido de devolución en la página **Todos los pedidos de ventas**. Los pedidos de devolución son los pedidos de ventas que tienen un tipo de pedido de **Pedido devuelto**.

### <a name="credit-correction"></a>Corrección de crédito

Como parte del proceso de facturación, compruebe los gastos varios son correctos. Para hacer que registros contables pasen a ser correcciones (Storno), piense en usar la opción **Corrección del crédito** en otra ficha **Otros** de la página **Registrando factura** al registrar la factura o la nota de abono. **Nota:** De forma predeterminada, la opción **Corrección de crédito** se activa la opción **Nota de abono como corrección** en la página **Parámetros de clientes** se ha habilitado. Sin embargo, se recomienda no registrar devoluciones con Storno.

## <a name="create-intercompany-return-orders"></a>Crear pedidos de devolución de empresas vinculadas
Los pedidos de devolución se pueden completar entre dos empresas de la organización. Se admiten los siguientes escenarios:

-   Devoluciones sencillas de empresas vinculadas entre dos empresas que participan en una relación de empresas vinculadas
-   Una cadena de empresas vinculadas que se establece cuando un pedido de devolución del cliente se crea en la empresa vendedora
-   Una cadena de empresas vinculadas que se establece cuando un pedido de devolución del proveedor se crea en la empresa compradora
-   Devoluciones directas envío de entrega entre un cliente externo y dos empresas que participan en una relación de empresas vinculadas

### <a name="setup"></a>Configuración

La ilustración siguiente muestra la configuración mínima que se requiere para que dos empresas participen en una relación de empresas vinculadas y aprovechen el comercio entre empresas vinculadas.  

![Configuración mínima](./media/SalesReturn06.png)

En el escenario siguiente, CompBuy es la empresa compradora y CompSell es la empresa vendedora. Normalmente, la empresa vendedora envía los artículos a la empresa compradora o, en escenarios de envíos de entrega directos, directamente al cliente final. En CompBuy, se ha definido el proveedor IC\_CompSell como un extremo de empresas vinculadas que está asociado a la empresa CompSell. Al mismo tiempo, en CompSell, se ha definido el cliente IC\_CompBuy como un extremo de empresas vinculadas que está asociado a la empresa CompBuy. Los detalles de políticas de acción apropiados y las asignaciones de valores deben definirse en ambas empresas. En un escenario de envío de la entrega directa, un pedido de devolución de empresas vinculadas, que es también un pedido de ventas de empresas vinculadas, se crea en la empresa vendedora. El número RMA del pedido de devolución de empresas vinculadas se puede escoger a partir de la secuencia del número RMA en CompSell o se puede copiar del número RMA asignado al pedido de devolución original en CompBuy. Los valores de número RMA la directiva de acciones **PurchaseRequisition** de CompBuy determinan estas acciones. Si se sincroniza el número RMA, debe planificar mitigar el riesgo de conflictos de números si las dos empresas usan la misma secuencia numérica.

### <a name="simple-intercompany-returns"></a>Devoluciones de empresas vinculadas simples

Esta situación implica a dos empresas de la misma organización, como se muestra en la siguiente ilustración.  

![Devolución de empresas vinculadas simple](./media/SalesReturn07.png)

La cadena de pedidos puede establecerse cuando se crea un pedido de devolución de un proveedor en la empresa compradora o un pedido de devolución del cliente en la empresa vendedora. Finance and Operations crea el pedido correspondiente en la otra empresa y garantiza que el encabezado y la información de línea en el pedido de devolución del proveedor reflejan los valores en el pedido de la devolución del cliente. El pedido de devolución que se establece puede incluir o excluir la referencia (**Buscar pedido de ventas**) a una factura de cliente existente. Los albaranes y las facturas de los dos pedidos se pueden procesar individualmente. Por ejemplo, no es necesario generar un albarán para el pedido de devolución del proveedor antes de generar el albarán para el pedido de devolución de cliente.

### <a name="direct-delivery-shipment-returns-among-three-parties"></a>Devoluciones de envío de entrega directo entre tres partes

Este escenario se puede establecer si una venta anterior del tipo **Entrega directa** se ha completado y si una factura con el cliente existe en la empresa que interactúa con el cliente. En la siguiente ilustración, la empresa CompBuy ha vendido y facturado anteriormente los productos al cliente Extern. Los productos se enviaron directamente desde la empresa CompSell al cliente mediante una cadena de pedidos de empresas vinculadas.  

![Devoluciones de envío directo de entrega entre tres partes](./media/SalesReturn08.png)

Si el cliente Extern desea devolver los productos, se crea un pedido de devolución (RMA02) para el cliente de la empresa CompBuy. Para establecer la cadena de empresas vinculadas, el pedido de devolución se debe marcar para entrega directa. Cuando usa la función **Buscar pedidos de ventas** para seleccionar la factura de cliente a devolver, se establece una cadena de pedidos de empresas vinculadas que consta de los siguientes documentos:

-   **Pedido de devolución original:** RMA02 (empresa CompBuy)
-   **Pedido de compra:** PO02 (empresa CompBuy)
-   **Pedido de devolución de empresas vinculadas:** RMA\_00032 (empresa CompSell)

Una vez creada la cadena de empresas vinculadas de entrega directa, toda la gestión y procesos físicos de las devoluciones debe producirse en el contexto del pedido de devolución de empresas vinculadas, RMA\_00032 en la empresa CompSell. Los productos no se pueden recibir en la empresa CompBuy. Cuando un código de disposición se asigna al pedido de devolución de empresas vinculadas, se sincroniza con el pedido de devolución original para permitir la facturación adecuada del pedido original.

## <a name="post-to-the-ledger"></a>Registrar en el libro mayor
Los registros en el libro mayor que se generan cuando se factura el pedido de devolución se ven afectados por algunas opciones y parámetros importantes:

-   **Precio de coste de la devolución:** para modelos de inventario distintos de **Coste estándar**, el parámetro **Precio de coste de la devolución** determina el coste del artículo si ha aceptado al inventario o cancelación. Para calcular una evaluación de inventario correcta, es importante establecer el parámetro **Precio de coste de la devolución** correctamente. Si usa la función **Buscar pedidos de ventas** para crear una línea de pedido de devolución que tenga una referencia a una factura de cliente, el valor **Devolver el precio de coste** es igual al precio de coste del artículo vendido. De lo contrario, el valor del precio del coste procede de la configuración del artículo o se puede especificar manualmente.
-   **Corrección de abono/Storno**: el parámetro **Corrección de crédito** la página **Registrando factura** determina si los registros se deben registrar como entradas positivas (DR/CR) o como corrección de las entradas negativas.

En los ejemplos siguientes, el precio de coste de devolución se representa como **Precio de coste de inventario**.

### <a name="example-1-the-return-order-doesnt-reference-a-customer-invoice"></a>Ejemplo 1: el pedido de devolución no hace referencia una factura de cliente

El pedido de devolución no hace referencia una factura de cliente. Se abona el artículo devuelto. El parámetro **Corrección de abono** no se selecciona cuando se genera la factura del pedido de devolución, o la nota de abono.  

![Pedido de devolución no hace referencia a una factura del cliente](./media/SalesReturn09.png)  

**Nota:** el precio del artículo maestro se usa como el valor predeterminado para el parámetro **Precio de coste de la devolución**. El precio predeterminado difiere del precio de coste en el momento de la emisión de inventario. Por lo tanto, la implicación que se ha incurrido en una pérdida de 3. Además, el pedido de devolución no incluye el descuento que se ha concedido al cliente en el pedido de ventas. Por lo tanto, aparece un crédito excesivo.

### <a name="example-2-credit-correction-is-selected-for-the-return-order"></a>Ejemplo 2: La corrección de crédito se selecciona para el pedido de devolución

El ejemplo 2 es lo mismo que el ejemplo 1, se selecciona el parámetro **Corrección de crédito** cuando se genera la factura del pedido de devolución.  

![Pedido de devolución donde se selecciona la corrección del crédito ](./media/SalesReturn10.png)  

**Nota:** Los registros contables se especifican como correcciones negativas.

### <a name="example-3-the-return-order-line-is-created-by-using-the-find-sales-order-function"></a>Ejemplo 3: La línea de pedido de devolución se crea mediante la función Buscar pedido de ventas

En este ejemplo, la línea de pedido de devolución se crea mediante la función **Buscar pedido de ventas**. El parámetro **Corrección de crédito** no se activa cuando se crea la factura.  

![Línea de pedido de devolución que se crea mediante Buscar pedido de ventas ](./media/SalesReturn11.png)  

**Nota:** **Descuento** y **Precio de coste de la devolución** se han configurado correctamente. Por lo tanto, se produce una inversión exacta de la factura de cliente.




