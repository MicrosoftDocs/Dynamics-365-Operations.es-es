---
title: Crear una factura de cliente
description: Una factura de cliente para un pedido de ventas es una factura en relación con una venta que una organización da a un cliente.
author: ShivamPandey-msft
ms.date: 03/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: twheeloc
ms.custom: 77772
ms.assetid: 00b4b40c-1576-4098-9aed-ac376fdeb8c5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a0d1221e07f6dc4a5a99aa205c4a7f6fb367f000
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780568"
---
# <a name="create-a-customer-invoice"></a>Crear una factura de cliente

[!include [banner](../includes/banner.md)]

Una **factura de cliente para un pedido de ventas** es una factura en relación con una venta que una organización da a un cliente. Este tipo de factura de cliente se crea basándose en un pedido de ventas, que incluye líneas de pedido y números de artículo. Los números de artículos se especifican y se registran en el libro mayor. Los asientos de subdiarios contables no están disponibles para facturas de cliente de pedidos de venta. Para obtener más información, consulte [Crear facturas de pedido de ventas](tasks/create-sales-order-invoices.md).

Las **facturas de servicios** no están relacionadas con los pedidos de ventas. Contienen líneas de pedido que incluyen cuentas contables, descripciones de texto libre y un importe de ventas que especifica el usuario. No puede especificar un número de artículo en este tipo de factura. Debe indicar la información de impuestos correspondiente. En cada línea de factura, se indica una cuenta principal para la venta, que se puede distribuir a varias cuentas contables si hace clic en **Distribuir importes** en la página **Factura de servicios**. Además, el saldo del cliente se registra en la cuenta de resumen del perfil de contabilización que se usa para la factura de servicios.

Para obtener más información, consulte:
 - [Crear facturas de servicios](../accounts-receivable/create-free-text-invoice-new.md)
 - [Crear una plantilla de factura de servicios](../accounts-receivable/create-free-text-invoice-template-new.md)
 - [Asignación de una plantilla de factura de texto libre a un cliente](tasks/assign-free-text-invoice-template-customer.md)
 - [Generación y registro de facturas de servicios](tasks/post-recurring-free-text-invoices.md)


Las **facturas proforma** son facturas que se preparan como estimación de los importes reales de la factura antes de registrar la factura. Puede imprimir una **factura proforma** para una factura de cliente de un pedido de ventas o de una factura de servicios. 

>[!NOTE]
> En el caso de una interrupción del sistema durante el proceso de facturación proforma de ventas, una factura proforma puede quedar huérfana. Una factura proforma huérfana se puede eliminar ejecutando el trabajo periódico **Eliminar facturas proforma manualmente**. Vaya a **Ventas y marketing > Tareas periódicas > Limpiar > Eliminar facturas pro forma manualmente**.

## <a name="using-sales-order-customer-invoice-data-entities"></a>Uso de entidades de datos de factura de cliente de pedido de ventas
Puede usar entidades de datos para importar y exportar información sobre una factura de cliente para un pedido de ventas. Hay diferentes entidades para la información sobre el encabezado de la factura de venta y las líneas de la factura de venta.

Las siguientes entidades están disponibles para la información en el encabezado de la factura de venta:

- **Encabezado del diario de facturas de ventas** entidad (SalesInvoiceJournalHeaderEntity)
- **Encabezados de facturas de venta V2** entidad (SalesInvoiceHeaderV2Entity)

Le recomendamos que utilice la entidad **Encabezado del diario de facturas de ventas**, porque proporciona una experiencia más eficaz para la importación y exportación de encabezados de ventas. Esta entidad no contiene el **Importe del impuesto sobre las ventas** (INVOICEHEADERTAXAMOUNT), que representa el valor del impuesto sobre las ventas en el encabezado de la factura de ventas. Si su escenario empresarial requiere esa información, utilice la entidad **Encabezados de facturas de venta V2** para importar y exportar la información del encabezado de la factura de venta.

Las siguientes entidades están disponibles para la información en las líneas de la factura de venta:

- Entidad **Líneas de factura del cliente** (BusinessDocumentSalesInvoiceLineItemEntity)
- **Líneas de factura de venta V3** entidad (SalesInvoiceLineV3Entity)

Cuando esté determinando qué entidad de línea usar para las exportaciones, considere si se usará una inserción completa o incremental. Además, tenga en cuenta la composición de los datos. La entidad **Líneas de factura de venta V3** admite escenarios más complejos (por ejemplo, asignación a los campos de inventario). También es compatible con escenarios de exportación de inserción completa. Para las inserciones incrementales, le recomendamos que utilice la entidad **Líneas de factura del cliente**. Esta entidad contiene una composición de datos mucho más simple que la entidad **Líneas de factura de venta V3** y se prefiere, especialmente si no se requiere la integración del campo de inventario. Debido a las diferencias en el soporte de mapeo entre las entidades de línea, la entidad **Líneas de factura del cliente** normalmente tiene un rendimiento más rápido que la entidad **Líneas de factura de venta V3**.

## <a name="post-and-print-individual-customer-invoices-that-are-based-on-sales-orders"></a>Registro e impresión de facturas de cliente individuales basadas en pedidos de ventas
Use este proceso para crear una factura basada en un pedido de ventas. Puede hacerlo si decide facturar al cliente antes de entregar los bienes o servicios. 

Al registrar una factura, la cantidad **Recordatorio de factura** de cada artículo se actualiza con el total de las cantidades facturadas del pedido de ventas seleccionado. Si las cantidades tanto de **Recordatorio de factura** como de **Pendiente de entrega** para todos los artículos de un pedido de ventas son 0 (cero), el estado del pedido de ventas cambia a **Facturado**. Si la cantidad de **Recordatorio de factura** no es 0 (cero), el estado del pedido de ventas no cambia y se podrán entrar facturas adicionales para este.

Puede ver el estado de los pedidos de ventas en la página de lista **Todos los pedidos de venta**. Use la página de lista **Facturas de cliente abiertas** para ver las facturas que ha registrado.

## <a name="post-and-print-individual-customer-invoices-that-are-based-on-packing-slips-and-the-date"></a>Registro e impresión de facturas de cliente basadas en albaranes y fechas
Use este proceso cuando uno o varios albaranes se han registrado para el pedido de ventas. La factura de cliente se basa en estos albaranes y refleja sus cantidades. La información financiera de la factura se basa en la información especificada al registrar la factura. 

Puede crear una factura de cliente basada en los artículos de línea de albarán enviados hasta la fecha, incluso si no se han enviado todos los artículos de un pedido de ventas en particular. Puede hacerlo, por ejemplo, si la entidad jurídica emite una factura por cliente al mes que cubre todas las entregas que se envían durante el mes. Cada albarán representa una entrega parcial o completa de los artículos del pedido de ventas. 

Al registrar la factura, la cantidad de **Recordatorio de factura** de cada artículo se actualiza con el total de cantidades entregadas de los albaranes seleccionados. Si las cantidades tanto de **Recordatorio de factura** como de **Pendiente de entrega** para todos los artículos de un pedido de ventas son 0 (cero), el estado del pedido de ventas cambia a **Facturado**. Si la cantidad de **Recordatorio de factura** no es 0 (cero), el estado del pedido de ventas no cambia y se podrán entrar facturas adicionales para este. 

Las transacciones de inventario se actualizan con el número de factura y el estado del campo **Estado de línea** del pedido de ventas cambia a **Facturado**. 

Vea el estado de los pedidos de ventas en la página de lista **Todos los pedidos de venta**.

## <a name="consolidate-sales-orders-or-packing-slips-for-posting"></a>Consolidar los pedidos de ventas o los albaranes para registrar
Use este proceso cuando uno o varios pedidos de ventas están listos para su facturación y desea consolidarlos en una única factura. 

Puede seleccionar varias facturas en la página de lista **Pedido de ventas** y, después, usar **Generar facturas** para consolidarlas. En la página **Registro de factura**, puede cambiar la opción **Pedido de resumen** para resumir por el número de pedido (donde hay varios albaranes para un único pedido de ventas) o por cuenta de facturación (donde hay varios pedidos de ventas para una única cuenta de facturación). Use el botón **Organizar** para consolidar pedidos de ventas en facturas únicas, en función de los ajustes de **Pedido de resumen**.

## <a name="split-sales-order-invoices-by-site-and-delivery-information"></a>Dividir facturas de pedidos de venta por sitio e información de entrega
Puede configurar la división de facturas de clientes de pedidos de ventas por sitio o por dirección de entrega en la pestaña **Actualización conjunta** de la página **Parámetros de clientes**. 
 - Active la opción **Dividir según el sitio de factura** para crear una factura por cada sitio al registrar. 
 - Active la opción **Dividir según la información de la entrega de factura** para crear una factura por cada dirección de entrega de línea de pedido de ventas al registrar. 

## <a name="post-to-revenue-account-for-sales-order-lines-that-have-no-price-and-no-cost"></a>Registrar en la cuenta de ingresos para líneas de factura de pedido de ventas que no tienen precio ni coste
Tendrá la opción de actualizar la cuenta **Ingresos** cuenta en la **Contabilidad general** para líneas de pedido de ventas que no tienen precio ni coste. 

Para configurar o ver esta información:
1. Vaya al parámetro **Registrar en cuenta de ingresos para líneas de factura de pedido de venta de precio y coste cero** en la pestaña **Libro mayor e impuesto sobre las ventas** de la **Parámetros de clientes** página. (**Clientes > Configuración >Parámetros de clientes**). 
2. Seleccione **Sí** para actualizar la cuenta **Ingresos** para las líneas de factura de pedidos de ventas que no tienen precio ni coste. 
 - Si se selecciona esta opción, el comprobante contendrá movimientos de 0,00 para los tipos de registro **Saldo del cliente** e **Ingresos**. Se define una cuenta de ingresos en la página de parámetros **Publicación de inventario**, en la pestaña de definición de cuenta **Órdenes de venta**. 
 - Si esta opción no está seleccionada, las líneas que no tienen información de precios o costos no se contabilizarán en la cuenta **Ingresos**. En cambio, el comprobante contendrá un movimiento de 0,00 para el tipo de registro **Saldo del cliente**.

## <a name="line-creation-sequence-number-information"></a>Información del número de secuencia de creación de línea
Cuando registre líneas de factura de cliente, tendrá la opción de crear números de secuencia de creación de líneas secuenciales. Los números de secuencia de creación de línea se asignan durante el proceso de registro. Al permitir una numeración no secuencial, puede ayudar a mejorar el rendimiento de registro de facturas de clientes. Los números de secuencia de creación de línea pueden ser utilizados por integraciones de terceros que esperan un orden secuencial. Consulte a su departamento de TI sobre cualquier extensión que pueda integrarse con los números de secuencia de creación de línea.

Para configurar o ver esta información, en la página **Parámetros de clientes**, en la pestaña **Actualizaciones**, configure la opción **Asignar números de línea secuenciales al registrar líneas de facturas de cliente**:

- Establezca la opción en **No** para utilizar la numeración no secuencial para los números de secuencia de creación de línea.
- Establezca la opción en **Sí** para utilizar numeración secuencial. Debe configurar la opción en **Sí** para personas jurídicas que tienen una dirección principal en Italia. También debe establecerla en **Sí** si el vuelo **CustInvoiceTransRandLineCreationSeqNumFlight** está deshabilitado.

## <a name="additional-settings-that-change-the-posting-behavior"></a>Opciones adicionales que modifican el comportamiento de registro
Los siguientes campos cambian el comportamiento del proceso de registro.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Campo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Cantidad</td>
<td>Seleccione las cantidades en las que se basarán los registros del documento. Las opciones que están disponibles varían en función del tipo de documento que vaya a registrar, como un albarán o una factura.
<ul>
<li><strong>Entregar ahora</strong>: permite seleccionar todas las cantidades que se especifican en el campo <strong>Entregar ahora</strong>. Utilice esta opción para confirmar o entregar un pedido parcial.</li>
<li><strong>Seleccionado</strong>: elija todas las cantidades se han seleccionado.</li>
<li><strong>Todo</strong>: seleccione todas las cantidades del pedido de ventas que el tipo de documento actual aún no ha actualizado.</li>
<li><strong>Albarán</strong>: seleccione todas las cantidades que se han actualizado en un albarán.</li>
<li><strong>Cantidad seleccionada y productos sin existencias</strong>: seleccione todas las cantidades que se han seleccionado y todas las cantidades de producto que no están en existencias.</li>
</ul></td>
</tr>
<tr class="even">
<td>Registro</td>
<td><ul>
<li>Active esta opción para registrar en el diario el pedido de ventas.</li>
<li>Desactive esta opción para imprimir un pedido de ventas proforma. <strong>Nota</strong>: si ha realizado un acuerdo para una programación de pago, esta no se mostrará en el pedido de ventas proforma. Las programaciones de pago sólo se mostrará en pedidos de ventas reales.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Selección posterior</td>
<td>Seleccione esta opción para aplicar más tarde la consulta seleccionada. Esta opción es la que se usa para trabajos por lotes. El trabajo por lotes se ejecuta al registrar pedidos de ventas.</td>
</tr>
<tr class="even">
<td>Reducir cantidad</td>
<td>Active esta opción para reducir automáticamente la cantidad entregada cuando se registra el documento, de modo que la cantidad entregada sea igual que el inventario disponible.</td>
</tr>
<tr class="odd">
<td>Imprimir</td>
<td>Seleccione cuándo desea imprimir documentos:
<ul>
<li><strong>Actual</strong>: imprime los documentos después de actualizar cada factura.</li>
<li><strong>Posterior</strong>: los documentos se imprimen cuando todas las facturas estén actualizadas.</li>
</ul>
<strong>Nota</strong>: el campo <strong>Imprimir</strong> sólo está disponible si activa las opciones <strong>Imprimir factura</strong>, <strong>Imprimir confirmación</strong>, <strong>Imprimir lista de selección</strong> o <strong>Imprimir albarán</strong>. Por ejemplo, en la página <strong>Ordenación del formulario</strong>, ha configurado el sistema para que ordene la información por cuenta de facturación. Puede seleccionar <strong>Después</strong> para imprimir los documentos en un lote que está ordenado por cuenta de facturación. De lo contrario, los documentos se imprimen antes de que el proceso haya finalizado y los documentos no se clasifican en el orden que se especifica en la página <strong>Ordenación del formulario</strong>.</td>
</tr>
<tr class="even">
<td>Imprimir factura</td>
<td>Seleccione esta opción para imprimir la factura. Si se desactiva esta opción, puede registrar una factura sin imprimirla.</td>
</tr>
<tr class="odd">
<td>Enviar correo electrónico</td>
<td>Seleccione esta opción para enviar a la factura de un pedido de ventas al cliente como archivos adjuntos al correo electrónico una vez registrada la factura. Los adjuntos se envían como archivos PDF y XML. Esta opción solo está disponible si selecciona la opción <strong>Habilitar CFD (facturas electrónicas)</strong> en la página <strong>Parámetros de facturas electrónicas</strong>. <strong>Nota</strong>: (MEX) este control solo está disponible para entidades jurídicas cuya dirección principal se encuentra en México.</td>
</tr>
<tr class="even">
<td>Utilizar destino de gestión de impresora</td>
<td>Seleccione esta opción para usar las opciones de impresión que se especifican para la transacción, el documento o el módulo en la página <strong>Configuración de la gestión de impresiones</strong>.</td>
</tr>
<tr class="odd">
<td>Comprobar límite de crédito</td>
<td>Seleccione la información que se debe analizar cuando se realice la comprobación del límite de crédito.
<ul>
<li><strong>Ninguno</strong>: no hay requisitos para la comprobación del límite de crédito.</li>
<li><strong>Saldo</strong>: el límite de crédito se comprueba con respecto al saldo del cliente.</li>
<li><strong>Saldo + albarán o recepción de producto</strong>: el límite de crédito se comprueba con respecto al saldo del cliente y las entregas.</li>
<li><strong>Saldo+Todo</strong>: el límite de crédito se comprueba con respecto al saldo del cliente, las entregas y los pedidos abiertos.</li>
</ul></td>
</tr>
<tr class="even">
<td>Corrección de crédito</td>
<td>Active esta opción para mostrar la nota de abono como débito en las transacciones de asiento.</td>
</tr>
<tr class="odd">
<td>Cantidad restante en Haber</td>
<td>Si se está registrando una nota de abono, active esta opción para mantener la cantidad restante en el pedido. Si se activa esta opción, la cantidad restante queda establecida en 0 (cero).</td>
</tr>
<tr class="even">
<td>Actualización conjunta para</td>
<td>Seleccione cómo se deben resumir varios pedidos de ventas:
<ul>
<li><strong>Ninguno</strong>: no se resumen los pedidos de ventas. Por ejemplo, se creará una factura individual para cada pedido de ventas.</li>
<li><strong>Cuenta de facturación</strong>: se resumen todos los pedidos seleccionados en función de los criterios especificados en la página <strong>Parámetros de actualización conjunta</strong>.</li>
<li><strong>Pedido</strong>: se resume el intervalo de pedidos seleccionado en el pedido especificado. Los pedidos se resumen en función de los criterios seleccionados en el formulario <strong>Parámetros de actualización conjunta</strong>. Si selecciona esta opción, debe seleccionar un valor en el campo <strong>Pedido de ventas</strong>.</li>
<li><strong>Actualización conjunta automática</strong>: si se han especificado actualizaciones conjuntas en la página <strong>Actualización conjunta</strong>, se resumen todos los pedidos seleccionados en función de los criterios configurados den la página <strong>Parámetros de actualización conjunta</strong>. Si las actualizaciones conjuntas no se han especificado, el pedido se registrará por separado.</li>
<li><strong>Albarán</strong>: se resume un intervalo de pedidos seleccionado en una factura por cada albarán. Esta opción sólo está disponible si se ha seleccionado <strong>Albarán</strong> en el campo <strong>Cantidad</strong>.</li>
</ul></td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
