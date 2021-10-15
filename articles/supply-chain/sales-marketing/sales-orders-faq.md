---
title: Preguntas frecuentes sobre pedidos de venta
description: Esta página trata las preguntas frecuentes que surgen cuando se trabaja con pedidos de ventas en Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 3cee75b1d740e7cb414c674157dde0146e8faa50
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571626"
---
# <a name="sales-order-faqs"></a>Preguntas frecuentes sobre pedidos de ventas

Esta página trata las preguntas frecuentes que surgen cuando se trabaja con pedidos de ventas en Dynamics 365 Supply Chain Management.

## <a name="can-i-link-a-purchase-order-to-a-sales-order-to-fulfill-demand"></a>¿Puedo vincular un pedido de compra a un pedido de ventas para satisfacer la demanda?

Puede crear un pedido de compra desde un pedido de ventas. Para obtener más información, consulte [Crear un pedido de compra desde un pedido de ventas](/dynamics365/supply-chain/sales-marketing/tasks/create-purchase-order-sales-order).

## <a name="can-i-cancel-or-delete-a-sales-order-or-return-order"></a>¿Puedo cancelar ni eliminar una orden de devolución o un pedido de ventas?

Puede cancelar solo pedidos de ventas y órdenes de devolución que estén en estado *Creado*. Para obtener más información, vea [Cancelar una orden de devolución](/dynamics365/supply-chain/service-management/cancel-return-order).

## <a name="can-i-restore-an-invoiced-sales-order-that-was-deleted"></a>¿Puedo restaurar un pedido de ventas facturado que se eliminó?

Si un pedido de ventas facturado se eliminó por error, puede restaurarlo o ver sus detalles.

Vaya a **Cuenta de cliente \> Transacciones \> Documento original \> Ver detalles**. Busque la factura que necesita y selecciónela para ver sus detalles. Estos detalles incluyen la referencia del pedido de ventas. También debería poder acceder a los detalles del pedido de ventas desde esa página.

## <a name="how-do-i-delete-orphaned-sales-order-records"></a>¿Como puedo eliminar los registros de pedido de ventas huérfanos?

Para limpiar los registros de pedido de ventas huérfanos, ejecute el trabajo periódico *Eliminación de pedido de ventas* desde alguno de los lugares siguientes:

- Ventas y marketing \> Tareas periódicas \> Limpiar \> Eliminar pedidos de ventas
- Venta minorista y comercio \> TI de Retail y Commerce \> Limpiar \> Eliminar pedidos de ventas

## <a name="is-there-a-way-to-calculate-commissions-on-invoices-that-have-already-been-posted"></a>¿Existe alguna forma de calcular las comisiones de las facturas que ya se han contabilizado?

Actualmente Supply Chain Management no admite el cálculo de comisiones para facturas contabilizadas.
