---
title: Aprobar y confirmar pedidos de compra
description: Este tema describe los estados por los que pasa un pedido de compra una vez que se ha creado y el efecto de habilitar la administración de cambios en los pedidos de compra.
author: Henrikan
ms.date: 04/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchOrderInReview, PurchOrderApproved, PurchOrderInDraft, PurchOrderAssignedToMe, VendPurchOrderJournalListPage, PurchTableWorkflowDropDialog, VendPurchOrderJournal
audience: Application User
ms.reviewer: kamaybac
ms.custom: 93143
ms.assetid: cd12a944-c52c-4579-a301-7abe1d237c72
ms.search.region: Global
ms.search.industry: ''
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7ae625950e62b2bf5ec092ccda414ee306c62d79
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570546"
---
# <a name="approve-and-confirm-purchase-orders"></a>Aprobar y confirmar pedidos de compra

[!include [banner](../includes/banner.md)]

Este tema describe los estados por los que pasa un pedido de compra (PO) una vez que se ha creado y el efecto de habilitar la administración de cambios en los pedidos de compra.

Una vez se ha creado un pedido de compra, puede que tenga que pasar por un proceso de aprobación. Después de que el proveedor haya aceptado el pedido, el pedido de compra se establece en un estado de **Confirmado**.

## <a name="approval-of-purchase-orders"></a>Aprobación de pedidos de compra
Los pedidos de compra que no utilizan la administración de cambios tienen un estado de **Aprobado** tan pronto como se crean, mientras que los pedidos de compra que usan la administración de cambios tienen un estado de **Borrador** cuando se crean por primera vez. Un pedido de compra que se ha creado consolidando un pedido planificado de la planificación maestra siempre se establece en un estado de **Aprobado**, independientemente de la configuración de la administración de cambios. Un pedido de compra crea transacciones de inventario solo cuando alcanza el estado **Aprobado**. Por tanto, ese inventario no aparece como disponible para reserva o marcado hasta que no se acepta el pedido.

Habilite la administración de cambios para pedidos de compra estableciendo la opción **Activar administración de cambios** en la página **Parámetros de adquisición y abastecimiento**. Cuando está habilitada la administración de cambios, los pedidos de compra pasan por un flujo de trabajo de aprobación después de que se hayan completado. Supply Chain Management tiene un editor de procesos de flujo de trabajo donde puede definir un flujo de trabajo para que represente el proceso de aprobación. Este flujo de trabajo puede incluir reglas de aprobación automática, reglas que determinan quién se asignará para aprobar pedidos de compra concretos y reglas para escalar un flujo de trabajo que ha estado esperando aprobación durante mucho tiempo. Puede habilitar el proceso de administración de cambios para todos los proveedores o para proveedores específicos. También puede configurar el proceso para que se puede anular para pedidos de compra individuales.

Cuando se habilita la administración de cambios, los pedidos de compra pasan por seis estados de aprobación, desde **Borrador** hasta **Finalizado**. Cuando se haya aprobado un pedido, los usuarios que deseen modificarlo deben usar la acción **Solicitar cambio**.

| Estado de aprobación | Descripción                                                                      | El cambio de solicitud está habilitado |
|-----------------|----------------------------------------------------------------------------------|---------------------------|
| Borrador           | El pedido de compra es un borrador y no se ha enviado para su aprobación en el flujo de trabajo del pedido de compra.     | No                        |
| En revisión       | El pedido de compra se envió para su aprobación en el flujo de trabajo del pedido de compra. La aprobación está pendiente.       | No                        |
| Rechazadas        | El pedido de compra se ha rechazado durante el proceso de aprobación.                                 | No                        |
| Aprobado        | El pedido de compra se ha aprobado.                                                             | Sí                       |
| Confirmado       | El pedido de compra se ha confirmado. Un pedido de compra no se puede confirmar hasta que se haya aprobado.        | Sí                       |
| Finalizada       | El pedido se ha finalizado. Está cerrado financieramente ahora y ya no se puede modificar. | No                        |

## <a name="confirming-purchase-orders"></a>Confirmación de pedidos de compra
POs que tienen un estado de aprobación de **aprobado** puede pasar por pasos adicionales antes de que se confirmaron. Por ejemplo, es posible que tenga que enviar una consulta de compra al proveedor para consultar precios, descuentos o fechas de entrega. En este caso, puede establecer el pedido de compra en el estado **En revisión externa** con la acción **Consulta de compra**.

Los proveedores que estén configurados para utilizar el portal de proveedores pueden revisar pedidos en el portal, y aprobarlos o rechazarlos. Durante este proceso de revisión, el pedido de compra tiene un estado de **En revisión externa**. El portal de proveedores se puede configurar de modo que una confirmación del proveedor confirma automáticamente el pedido en Supply Chain Management. De forma alternativa, puede confirmar un pedido de compra manualmente después de recibir la confirmación del proveedor. Si un proveedor rechaza un pedido de compra, el rechazo se recibe junto con el motivo del rechazo y sugerencias para cambios. En este caso, el estado del pedido de compra sigue siendo **En revisión externa**.

También hay una opción para generar una confirmación proforma para un pedido antes del procesamiento de la confirmación real. Esta opción solo crea un informe que puede compartir con el proveedor. No crea ninguna información de diario.

Una vez que el proveedor haya acordado el pedido, el siguiente paso será registrar el pedido de compra como confirmado. Puede completar este paso con la acción **Confirmación** o con la acción **Confirmar**. Ambas acciones establecen el estado de aprobación de la orden en **Confirmado**. La confirmación de un pedido inicia dos procesos adicionales:

-   Se crea un diario para almacenar una copia exacta de lo que se ha confirmado en el sistema. A veces, las órdenes requieren cambios y se crean diarios adicionales una vez se ha confirmado el pedido actualizado. Estos diarios le permiten ver el historial de las diversas versiones del pedido que se han confirmado.
-   Se crean distribuciones contables y se producen comprobaciones de pedidos y de presupuestos si se ha habilitado esta funcionalidad. Si se produce un error de cualquier comprobación, recibirá un mensaje de error indicando que se deben realizar cambios en el pedido de compra para que se pueda confirmar de nuevo.

Un proveedor podrá solicitar algún tipo de garantía de que se proporcionará el pago para una compra. Hay diversos métodos para proporcionar esta garantía dentro de los procesos de proveedores. Por ejemplo, la acción **Pago por adelantado** reserva fondos para el pedido de compra y este pago por adelantado se registra en el pedido de compra.

## <a name="changing-purchase-orders"></a>Cambio de pedidos de compra
En algunas situaciones, es posible que tenga que cambiar un pedido de compra una vez que alcance un estado de aprobación de **Aprobado** o **Confirmado**.

Si el pedido de compra se creó mediante un proceso de administración de cambios, puede realizar cambios recuperando el pedido o, si ya se ha aprobado el pedido, con la acción **Solicitar cambio**. En este caso, el estado de aprobación vuelve a ser **Borrador** y, a continuación, podrá modificar el pedido. Una vez que haya terminado de realizar cambios, es posible que tenga que enviar el pedido para la nueva aprobación. Puede configurar los tipos de cambios que requieren nueva aprobación mediante una regla de directivas **Regla de nueva aprobación para pedidos de compra** en la página **Directivas de compra**.

Si se ha entregado parte de la cantidad pedida para una línea de pedido de compra, no puede cambiar la cantidad pedida cuando el pedido de compra está en **Borrador**. Sin embargo, puede cambiar la cantidad **Entregar el resto** en la línea para la orden de compra que está en el estado **Borrador**.

Tras la confirmación de un pedido, ya no podrá eliminarlo. Sin embargo, puede cancelar la cantidad total o cualquier cantidad restante de un pedido, siempre que la cantidad no se haya recibido o facturado. A continuación, puede utilizar la acción **Finalizar** para evitar el procesamiento adicional. 


## <a name="canceling-purchase-orders"></a>Cancelar pedidos de compra

Un PO se puede cancelar mediante la acción **Cancelar** en el encabezado.

Si la cantidad se ha registrado, se ha recibido, o se ha facturado parcialmente, puede cancelar únicamente la cantidad restante que no se ha registrado, ni recibido, ni facturado. La cantidad de pedido se reduce como corresponda. Si la cantidad en la línea se actualiza, se actualizará el estado de línea también. Por ejemplo, la cantidad original en la línea es 5, y una cantidad de 3 se recibe. En este caso, sólo dos se pueden cancelar. La línea se actualizará al estado **Recibido**.

Si un resto de la entrega se agrega a la línea de pedido, y supera la cantidad de la línea de pedido, la acción **Cancelar** no cancela el excedente. En su lugar, la línea permanece en el estado **Pedido abierto**, porque tiene una cantidad restante. Por ejemplo, la cantidad original de la línea es 5, y el excedente de entrega es 7. Si el pedido se cancela, cinco se cancelan, y una cantidad de 2 queda, como puede ver en las transacciones de inventario.

Para cancelar toda la cantidad de una línea del PO, debe cancelar la cantidad del resto de la entrega de la línea. La línea se actualizará al estado **Cancelado**.

Si un PO se encuentra bajo gestión de cambios, todo cambio, como la cancelación del pedido o del resto de la entrega, debe ser enviado al sistema de flujo de trabajo y aprobado antes de poder finalizar el proceso y las transacciones de inventario se pueden actualizar como canceladas.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de los pedidos de compra](purchase-order-overview.md)

[Crear pedidos de compra](purchase-order-creation.md)

[Recepción de producto frente a pedidos de compra](product-receipt-against-purchase-orders.md)

[Visión general de facturas de proveedores](../../finance/accounts-payable/vendor-invoices-overview.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]