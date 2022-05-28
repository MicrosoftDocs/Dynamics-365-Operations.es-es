---
title: Visión general de solicitud de compra
description: Este tema describe el flujo de trabajo de solicitudes de compra y los diferentes estados que puede tener una solicitud de compra.
author: GalynaFedorova
ms.date: 11/02/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: PurchReqConsolidation, PurchReqCreate, PurchReqCreatePurchDetails, PurchReqCreatePurchListPage, PurchReqTable, PurchReqTableListPage, PurchReqConsolidationPartByVendor, PurchReqConsolidationLineDetail, PurchReqConsolidationCreate, PurchReqConsolidationBulkEdit, PurchReqConsolidationAddLine
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "2174"
- intro-internal
ms.assetid: 77d07119-4d9f-4c0e-acbe-d319203571ab
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e6524229800233d1bfdf54a11afc122990eed9d3
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671179"
---
# <a name="purchase-requisition-overview"></a>Visión general de solicitud de compra

[!include [banner](../includes/banner.md)]

Este tema describe el flujo de trabajo de solicitudes de compra y los diferentes estados que puede tener una solicitud de compra.

En función de la configuración de la organización, podrá crear solicitudes de compra de productos que su organización usa. Una solicitud de compra es un documento interno que autoriza al departamento de compras a comprar artículos o servicios.  

Una vez aprobada una solicitud de compra, se puede usar para generar un pedido de compra. Los pedidos de compra son los documentos externos que el departamento de compras envía a los proveedores.

## <a name="creating-purchase-requisitions"></a>Creación de solicitudes de compra
Puede crear una solicitud de compra en la página **Mis solicitudes de compra**, y seleccionar los artículos y los servicios que sea necesario. Puede seleccionar artículos de un catálogo de compras creado por su organización, o bien solicitar artículos que no se encuentran en un catálogo seleccionando una categoría de compra y especificando los detalles del producto.  

Para poder enviar una solicitud de compra para revisarla, es preciso configurar flujos de trabajo. El proceso del flujo de trabajo se usa para mover una solicitud de compra por el proceso de revisión, desde un estado inicial de **Borrador** a un estado final de **Aprobado**.

### <a name="purchase-requisition-statuses"></a>Estados de solicitudes de compra

Al crear una solicitud de compra, se le asigna un estado. A cada una de las líneas que se agrega a la solicitud de compra se le asigna también un estado. Si envía una solicitud de compra al flujo de trabajo para su revisión, su estado y las líneas se actualizan a medida que las líneas pasan por el ciclo de vida del proceso de flujo de trabajo.  

Puede configurar el proceso del flujo de trabajo de la solicitud de compra para dirigir una solicitud de compra a través del proceso de revisión como un documento único. Otra opción es que las líneas de una solicitud de compra se pueden enrutar individualmente a los revisores adecuados. Si las líneas de la solicitud de compra se revisan de manera individual, el estado de cada línea de la solicitud de compra se puede actualizar a medida que la línea se mueve en el proceso de revisión. Cuando todas las líneas hayan completado el proceso de revisión y no queden pasos de revisión para la solicitud de compra, se actualizará el estado de la solicitud de compra completa.

### <a name="purchase-requisition-workflow"></a>Flujo de trabajo de solicitudes de compra

En el diagrama siguiente se muestran los estados que se han asignado a una solicitud de compra y una línea de solicitud de compra a medida que avanzan por el proceso del flujo de trabajo.  

[![Estados de encabezado y línea de solicitud de compra.](./media/purchasereq_headerline_statuses.jpg)](./media/purchasereq_headerline_statuses.jpg)

### <a name="purchase-requisition-header-and-line-status-relationships"></a>Relaciones de estados de encabezado y línea de solicitud de compra

El estado general de una solicitud de compra lo determina el estado de las líneas de solicitud de compra. Por lo tanto, el proceso de revisión se debe completar para todas las líneas de la solicitud de compra antes de que se pueda completar el proceso de revisión para la solicitud de compra en su totalidad. En la tabla siguiente se describen los estados asignados al encabezado y las líneas de una solicitud de compra a medida que la solicitud de compra pasa por el proceso del flujo de trabajo.

<table>
<thead>
<tr class="header">
<th>Estado de la solicitud de compra</th>
<th>Estado de la línea de solicitud de compra</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Borrador</td>
<td>Borrador</td>
<td>La solicitud de compra y la línea de solicitud de compra se han creado, pero aún no se han enviado a revisión. Las solicitudes de compra y las líneas de solicitud de compra que tienen el estado <strong>Borrador</strong> se pueden modificar. Una solicitud de compra o una línea de solicitud de compra también tiene el estado <strong>Borrador</strong> si se han recuperado, pero no se han reenviado a revisión. <strong>Nota:</strong> Solo puede enviar o recuperar una solicitud de compra a nivel de documento. Sin embargo, no puede enviar o recuperar una única línea de solicitud de compra.</td>
</tr>
<tr class="even">
<td>En revisión</td>
<td><ul>
<li>En revisión</li>
<li>Rechazadas</li>
</ul></td>
<td>Si el flujo de trabajo se ha configurado para dirigir las líneas de solicitud de compra a revisores individuales, cada una de las líneas puede tener el estado <strong>En revisión</strong> o <strong>Rechazado</strong>. El estado de solicitud de compra se actualiza cuando se completa el proceso de revisión para todas las líneas de solicitud de compra y no quedan pasos de revisión para la solicitud de compra.
<ul>
<li><strong>En revisión</strong>: se han enviado las líneas de la solicitud de compra para revisión. Una vez completado el proceso de flujo de trabajo para una línea de solicitud de compra, se mantiene en un estado <strong>En revisión</strong> hasta que se hayan revisado todas las líneas de solicitud de compra.</li>
<li><strong>Rechazado</strong>: se ha rechazado una línea de la solicitud de compra. Las líneas de la solicitud de compra que se han rechazado se pueden modificar y volver a enviar.</li>
</ul>
Si reenvía una línea de solicitud de compra que se ha rechazado, el proceso de revisión se vuelve a iniciar para todas las líneas de solicitud de compra que todavía se estén revisando. </br><strong>Nota</strong>: puede recuperar una solicitud de compra que ya se ha enviado. Al recuperar una solicitud de compra, se recuperan todas las líneas de la solicitud de compra restantes. Las líneas de la solicitud de compra que se han recuperado se pueden eliminar.</td>
</tr>
<tr class="odd">
<td>Rechazadas</td>
<td>Rechazadas</td>
<td>La solicitud de compra y todas las líneas de solicitud de compra se han rechazado. Las solicitudes de compra y las líneas de solicitud de compra que se hayan rechazado se pueden volver a enviar.</td>
</tr>
<tr class="even">
<td>Aprobado</td>
<td><ul>
<li>Aprobado</li>
<li>Cancelado</li>
<li>Cerrado</li>
</ul></td>
<td>Todas las líneas de solicitud de compra han completado el proceso de revisión y no hay más pasos de revisión para la solicitud de compra.
<ul>
<li><strong>Aprobado</strong>: el proceso de revisión para una la línea de solicitud de compra se ha completado y la línea se ha aprobado.</li>
<li><strong>Cancelado</strong>: se ha aprobado la línea de la solicitud de compra, pero se ha cancelado porque ya no se necesita. Solo se pueden cancelar las líneas de las solicitudes de compra que se han aprobado.</li>
<li><strong>Cerrado</strong>: la línea de solicitud de compra se ha aprobado y los documentos se han generado en función del propósito del pedido.
<ul>
<li>Si el propósito de solicitud es consumo, se ha generado un pedido de compra para la línea de solicitud de compra.</li>
<li>Si el propósito de solicitud es reabastecimiento, se han generado uno o varios documentos de cumplimiento.</li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td>Cancelado</td>
<td>Cancelado</td>
<td>La solicitud de compra y todas las líneas de solicitud de compra se han cancelado.</br> <strong>Nota:</strong> Si ya no necesita un artículo que se encuentra en una línea de solicitud de compra, debe cancelar la línea de solicitud de compra si se ha aprobado. Solo se pueden cancelar las líneas de las solicitudes de compra que se han aprobado. Si se están revisando las líneas de solicitud de compra, la solicitud de compra tendrá también el estado <strong>En revisión</strong>. En este caso, puede recuperar la solicitud de compra y eliminar la línea de solicitud de compra correspondiente.</td>
</tr>
<tr class="even">
<td>Cerrado</td>
<td><ul>
<li>Cerrado</li>
<li>Cancelado</li>
</ul></td>
<td>La solicitud de compra está cerrada y se han generado uno o varios documentos de cumplimiento.
<ul>
<li><strong>Cerrado</strong>: la línea de solicitud de compra se ha aprobado y los documentos se han generado en función del propósito del pedido.
<ul>
<li>Si el propósito de solicitud es consumo, se ha generado un pedido de compra para la línea de solicitud de compra.</li>
<li>Si el propósito de solicitud es reabastecimiento, se han generado uno o varios documentos de cumplimiento.</li>
</ul></li>
<li><strong>Cancelado</strong>: se ha aprobado la línea de la solicitud de compra, pero se ha cancelado porque ya no se necesita. Solo se pueden cancelar las líneas de las solicitudes de compra que se han aprobado.</li>
</ul>
<strong>Nota</strong>: si ya no necesita un artículo en una línea de solicitud de compra que se ha cerrado, debe cancelar la línea en el documento de cumplimiento que se ha generado para la línea de solicitud de compra.</td>
</tr>
</tbody>
</table>

## <a name="distributing-costs-to-multiple-financial-accounts"></a>Distribución de costes a varias cuentas financieras
Es posible distribuir el coste de un producto incluido en una solicitud de compra a varias cuentas financieras. Si la organización usa dimensiones, tales como departamentos o centros de coste, puede distribuir los costes de un producto a las dimensiones de las cuentas financieras.

## <a name="requisition-purposes"></a>Propósitos de pedido
Los propósitos de pedido realizan el proceso de satisfacer las demandas de solicitud de manera más flexible. Cuando se crea una solicitud, puede asignarle uno de los dos propósitos: consumo o reabastecimiento. En función del propósito de solicitud y la configuración de la organización, la demanda de solicitud la puede cumplir un pedido de compra, un pedido de transferencia, un pedido de producción o un kanban.  

En las directivas de compra, puede controlar los propósitos de solicitud disponibles al crear una solicitud para la organización.

### <a name="requisitions-that-have-a-purpose-of-consumption"></a>Solicitudes con el propósito de consumo

Una solicitud con un propósito de consumo representa una demanda para los artículos o servicios que se usarán internamente en la organización. La demanda que se crea mediante este tipo de solicitud siempre la cumple un pedido de compra. Si Supply Chain Management se ha configurado para generar pedidos de compra automáticamente, los pedidos de compra se crean automáticamente tras la aprobación de la solicitud de compra.

### <a name="requisitions-that-have-a-purpose-of-replenishment"></a>Solicitudes con el propósito de reabastecimiento

Una solicitud que tiene un propósito de reabastecimiento representa una demanda para reabastecer el inventario. Por ejemplo, crea una solicitud para reabastecer los artículos de modo que se puedan vender en una ubicación comercial específica en un plazo específico. La demanda que crea este tipo de solicitud se puede cumplir mediante un pedido de compra, un pedido de transferencia, un pedido de producción o un kanban.  

Cuando el propósito de solicitud es reabastecimiento, la demanda se expresa como una cantidad en lugar de un importe monetario. Por lo tanto, no se aplica la contabilidad de reserva de gasto, el control presupuestario, las reglas de negocios para la determinación de activos fijos (BRAD), la contabilidad de proyectos ni las reglas relacionadas. Solo los productos que se encuentran en existencias y liberados a la entidad jurídica especificada pueden cumplir la demanda de la solicitud de reabastecimiento. Para definir los productos que están disponibles cuando el propósito de la solicitud es el de reabastecimiento, use la página **Regla de directivas de acceso de categorías de reabastecimiento**.  

Para usar las solicitudes de compra con un propósito de reabastecimiento, debe configurar una programación maestra para incluir la demanda de la solicitud. El método de cumplimiento de la demanda que se crea mediante este tipo de solicitud se determina automáticamente según las directivas de suministro configuradas para los artículos de la organización y planificadas mediante la programación maestra.

## <a name="purchase-requisitions-and-requests-for-quotation"></a>Solicitudes de compra y solicitudes de presupuesto
En algunos casos, debe comenzar un proceso de solicitud de presupuesto para identificar el proveedor y el precio para los productos que se piden en una solicitud de compra. Se puede generar una solicitud de presupuesto cuando la solicitud de compra se encuentra en revisión. Al aceptar una oferta, la información acerca del proveedor, precio, etc., se transfiere a la solicitud.  

Puede poner una solicitud de compra en espera seleccionando la casilla **En espera** en la página **Detalles de la solicitud de compra**. El procesamiento de la solicitud de compra puede continuar solo después de eliminar la espera desactivando la casilla.  

> [!NOTE]
> En la adquisición electrónica, la solicitud de presupuesto para su solicitud de compra puede permitir a los proveedores agregar líneas alternativas. En este caso, las alternativas se reflejarán en la solicitud de compra.

## <a name="demand-consolidation"></a>Consolidación de la demanda
Al consolidar las líneas de solicitudes de compra de varias solicitudes de compra, puede aumentar su poder de negociación con sus proveedores para alcanzar un mejor precio, costes de envío y tramitación más bajos, así como menores costes generales.  

Las líneas de solicitudes de compras aprobadas se pueden elegir para la consolidación de demanda solo en el caso de que se cumplan las siguientes afirmaciones:

-   La solicitud de compra se ha aprobado.
-   La solicitud de compra cumple con los criterios de la regla de la directiva de compra para el proceso manual y la consolidación de demanda.

Las líneas de solicitud de compra aprobadas que cumplan con los criterios para su procesamiento manual se incluyen en la página **Liberar solicitudes de compra aprobadas**. Si una línea de solicitud de compra también cumple los criterios para la consolidación de demanda, la línea se puede agregar a una oportunidad de consolidación.  

Una oportunidad de consolidación es un conjunto de líneas de solicitud de compra que se agrupan de modo que el profesional de compras pueda negociar el mejor acuerdo con los proveedores. Las líneas de solicitud de compra que se selecciona para una oportunidad de consolidación aparecen en la página **Consolidación de solicitudes de compra**. Puede modificar las líneas en esta página, si hacen falta cambios. También puede agregar líneas nuevas o quitar las existentes de la oportunidad de consolidación.  

Después de agregar líneas de solicitud a una oportunidad de consolidación y realizar los cambios oportunos, puede crear un pedido de compra para las líneas de solicitud de compra consolidadas.  

> [!NOTE]
> Los cambios que realice en una línea de solicitud de compra en la página **Consolidación de solicitudes de compra** quedan reflejados en el pedido de compra que se cree. No obstante, en la solicitud de compra, se mantiene la línea sin cambiar para preservar el historial.  

Para crear un pedido de compra para líneas de solicitud de compra que no sean aptas para la consolidación de la demanda o que no estén seleccionadas para una oportunidad de consolidación, las líneas deben procesarse manualmente.

### <a name="consolidating-purchase-requisition-lines"></a>Consolidar líneas de solicitudes de compra

El proceso para la consolidación de la demanda comienza cuando una solicitud de compra se aprueba en un flujo de trabajo y se han registrado las reservas de presupuesto y las pre-reservas de gastos, si se ha configurado control presupuestario para su organización. En el siguiente diagrama se muestra el flujo de proceso para la consolidación de la demanda.  

[![Flujo de proceso de consolidación de demanda.](./media/demand-consolidation.gif)](./media/demand-consolidation.gif)  

Para consolidar las líneas de solicitud de compra aprobadas, siga estos pasos:

1.  Revise las líneas de solicitud aprobadas que se han mantenido para el procesamiento manual y que son aptas para la consolidación de la demanda.
2.  Seleccione las líneas que agregar a una oportunidad de consolidación.
3.  Cree una nueva oportunidad de consolidación o agregue las líneas de solicitud a una oportunidad de consolidación existente.
4.  Aplique los cambios oportunos a las líneas de solicitud y quite los artículos de línea de solicitud que ya no desee incluir en la oportunidad de consolidación.
5.  Cree pedidos de compra para las líneas de solicitud consolidadas o para las líneas de solicitud de compra en una oportunidad de consolidación.


## <a name="additional-resources"></a>Recursos adicionales

[Crear una solicitud para consumo](tasks/create-requisition-consumption.md)

[Flujo de trabajo de solicitudes de compra](purchase-requisitions-workflow.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]