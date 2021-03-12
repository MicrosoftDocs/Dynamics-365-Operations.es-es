---
title: Solucionar problemas de pedidos de ventas
description: Este tema describe cómo solucionar problemas que pueden surgir al trabajar con pedidos de ventas.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: c9a5b7a5e8cac7f8816233dd2d7ff1a7f84ea480
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974794"
---
# <a name="troubleshoot-sales-orders"></a>Solucionar problemas de pedidos de ventas

Este tema describe cómo solucionar problemas que pueden surgir al trabajar con pedidos de ventas.

## <a name="the-tax-information-isnt-updated-if-i-change-the-location-on-a-sales-order-header"></a>La información fiscal no se actualiza si cambio la ubicación en el encabezado de un pedido de ventas.

### <a name="issue-description"></a>Descripción del problema

Si se cambia el sitio, el almacén o la dirección de entrega, ya sea en el encabezado de un pedido de ventas o en el nivel de línea, la información fiscal del caso no se actualiza automáticamente en las líneas.

### <a name="issue-resolution"></a>Solución del problema

Este comportamiento se debe al diseño. El problema se produce porque la dirección de entrega, el sitio y el almacén tampoco se cambian automáticamente en las líneas. Debe actualizarlos manualmente.

## <a name="if-there-are-two-trade-agreements-for-the-same-period-or-overlapping-periods-the-same-agreement-line-is-always-selected"></a>Si hay dos acuerdos comerciales para el mismo período o para períodos superpuestos, siempre se selecciona la misma línea de acuerdo.

### <a name="issue-description"></a>Descripción del problema

Si se definen dos acuerdos comerciales para el mismo período o para períodos superpuestos, parece que se selecciona el mismo acuerdo comercial cada vez que se crean líneas de pedido de ventas que contengan esos artículos.

### <a name="issue-resolution"></a>Solución del problema

Si hay más de un acuerdo comercial para una fecha determinada, siempre se selecciona el acuerdo comercial que tiene el precio más bajo. Para obtener más información, descargue las notas del producto siguientes: [Acuerdos comerciales en Microsoft Dynamics AX 2012](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).

## <a name="can-i-link-a-purchase-order-to-a-sales-order-to-fulfill-demand"></a>¿Puedo vincular un pedido de compra a un pedido de ventas para satisfacer la demanda?

Puede crear un pedido de compra desde un pedido de ventas. Para obtener más información, consulte [Crear un pedido de compra desde un pedido de ventas](tasks/create-purchase-order-sales-order.md).

## <a name="i-cant-cancel-or-delete-a-return-order-or-a-sales-order"></a>No puedo cancelar ni eliminar una orden de devolución o un pedido de ventas.

Puede cancelar solo pedidos de ventas y órdenes de devolución que estén en estado *Creado*. Para obtener más información, vea [Cancelar una orden de devolución](../service-management/cancel-return-order.md).

## <a name="when-i-try-to-cancel-a-sales-order-i-receive-a-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations-error"></a>Cuando intento cancelar un pedido de venta, aparece el error "No se pueden quitar las reservas porque se ha creado un trabajo que depende de ellas".

Código de error: WAX4661

Si el trabajo está asociado con un pedido de venta, no puede cancelar el pedido de venta hasta que el trabajo se cancele y se revierta. Este requisito se aplica incluso si el trabajo asociado con el pedido de ventas está cerrado.

Para arreglar este problema, siga estos pasos.

1. Cancele el trabajo y vuelva a colocar el inventario en la ubicación deseada. Vaya a la carga relevante del pedido de ventas y seleccione **Reducir cantidad seleccionada** en la línea de carga o **Invertir el trabajo** en el panel de acciones.

    Ahora el trabajo tiene el estado *Cancelado* y se crea y procesa automáticamente un nuevo trabajo de movimiento de inventario para volver a colocar el inventario en la ubicación que se describió en el momento de la reversión.

2. Elimina la carga. También se elimina el envío.
3. Ahora debería poder ir al pedido de ventas y cancelarlo.

## <a name="i-cant-cancel-an-intercompany-purchase-order-that-is-linked-to-a-sales-order"></a>No puedo cancelar un pedido de compra de empresas vinculadas que está vinculado a un pedido de ventas.

### <a name="issue-description"></a>Descripción del problema

Si intenta cancelar un pedido de compra de empresas vinculadas que esté vinculado a un pedido de ventas, es posible que aparezca el siguiente mensaje de error: "La cantidad no se puede reducir porque la cantidad de actualización restante cambia de signo".

### <a name="issue-resolution"></a>Solución del problema

Este problema se corrigió en Microsoft Dynamics 365 Supply Chain Management versión 10.0.13. Desde esa versión y las versiones posteriores podrá cancelar un pedido de compra de empresas vinculadas que esté vinculado a un pedido de ventas.

## <a name="can-i-restore-an-invoiced-sales-order-that-was-deleted"></a>¿Puedo restaurar un pedido de ventas facturado que se eliminó?

### <a name="issue-description"></a>Descripción del problema

Un pedido de ventas facturado se eliminó por error y desea restaurarlo o ver sus detalles.

### <a name="issue-resolution"></a>Solución del problema

Si el pedido de ventas eliminado ya se ha facturado, vaya a **Cuenta de cliente \> Transacciones \> Documento original \> Ver detalles**. Busque la factura que necesita y selecciónela para ver sus detalles. Estos detalles incluyen la referencia del pedido de ventas. También debería poder acceder a los detalles del pedido de ventas desde esa página.

## <a name="the-deadline-of-a-sales-order-header-cant-be-found-in-the-salesorderheaderv2entity-data-entity"></a>No se encuentra la fecha límite de un encabezado de pedido de ventas en la entidad de datos SalesOrderHeaderV2Entity.

El campo de fecha límite no existe en la entidad *SalesOrderHeaderV2Entity*.

## <a name="i-must-delete-orphaned-sales-order-records"></a>Debo eliminar los registros de pedido de ventas huérfanos.

Para limpiar los registros de pedido de ventas huérfanos, ejecute el trabajo periódico *Eliminación de pedido de ventas* desde alguno de los lugares siguientes:

- Ventas y marketing \> Tareas periódicas \> Limpiar \> Eliminar pedidos de ventas
- Venta minorista y comercio \> TI de Retail y Commerce \> Limpiar \> Eliminar pedidos de ventas

## <a name="is-there-a-way-to-calculate-commissions-on-invoices-that-have-already-been-posted"></a>¿Existe alguna forma de calcular las comisiones de las facturas que ya se han contabilizado?

Actualmente Supply Chain Management no admite el cálculo de comisiones para facturas contabilizadas.

## <a name="a-bundle-item-isnt-supported-in-an-intercompany-process"></a>Un proceso de empresas vinculadas no admite artículos de agrupación.

El artículo de agrupación no está disponible para el pedido de compra porque, si examina las líneas del pedido de ventas del artículo de la agrupación, notará que la cantidad es *0* (cero) y el estado es *Cancelado*. Este comportamiento se debe al diseño. El pedido de cliente compra solo los componentes del artículo de agrupación. No compra el artículo de agrupación en sí.

Si tiene que comprar una agrupación, considere si debe marcarlo como artículo de agrupación, ya que esta funcionalidad está diseñada para escenarios de reconocimiento de ingresos. Para obtener más información acerca de los artículos de agrupación, consulte [Agrupaciones](../../finance/accounts-receivable/revenue-recognition-setup.md#bundles).
