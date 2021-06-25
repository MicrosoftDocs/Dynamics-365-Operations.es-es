---
title: Visión general de pedidos de compra
description: Este artículo proporciona información general acerca de los pedidos de compra (PC) y vínculos a artículos adicionales relacionados con las distintas etapas por las que pasa un pedido de compra.
author: kamaybac
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchLineOpenOrder, PurchConfirmationRequestJournal
audience: Application User
ms.reviewer: kamaybac
ms.custom: 93083
ms.assetid: e9b7bc5b-1d7e-4ec2-97be-d655274b0613
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 77410fd131ecdcb05b682ac4660ec8c453b75218
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188230"
---
# <a name="purchase-order-overview"></a>Visión general de pedidos de compra

[!include [banner](../includes/banner.md)]

Este artículo proporciona información general acerca de los pedidos de compra (PC) y vínculos a artículos adicionales relacionados con las distintas etapas por las que pasa un pedido de compra.

Un pedido de compra (PC) es un documento que representa un acuerdo con un proveedor para comprar bienes o servicios. El documento también ayuda a realizar un seguimiento de las recepciones de producto que se realizan para el pedido y, posteriormente, la contabilidad de las facturas de proveedor que el proveedor factura para el pedido.  

La página **Pedidos de compra** contiene una descripción general de los pedidos disponibles y permite modificarlos. Al abrir un pedido de compra, puede seleccionar la vista **Encabezado**, que contiene información especificada solo una vez para cada pedido de compra, como los detalles del proveedor. De forma alternativa, puede seleccionar la vista **Líneas**, donde puede modificar las líneas de pedido. Normalmente, pasará de una vista a otra conforme modifique los pedidos de compra. Los gastos no se muestran directamente en la página **Pedidos de compra**, sino que se tiene acceso a ellos mediante menú en las líneas y encabezado de pedido.  

Hay muchos informes donde puede ver información acerca de los pedidos de compra, las recepciones de producto y las facturas de proveedor. Estos informes se encuentran en los módulos **Adquisición y abastecimiento** y **Proveedores**.  

Los espacios de trabajo **Preparación de pedidos de compra** y **Recepción y seguimiento de pedidos de compra** permiten ver listas de pedidos de compra en los diferentes estados a los que han progresado. También proporcionan un resumen de las acciones que se deben realizar. El espacio de trabajo **Preparación de pedidos de compra** se centra en la creación y revisión de pedidos de compra, el procesamiento del pedido hasta la aprobación y la confirmación con el proveedor. El espacio de trabajo **Recepción y seguimiento de pedidos de compra** se centra en el procesamiento de la recepción de bienes o servicios de pedidos de compra. Incluye listas que proporcionan información sobre las recepciones vencidas o que vencerán pronto para entregar por parte del proveedor. Estos espacios de trabajo no se utilizan para realizar las actividades de recepción relacionadas que se realizan en el almacén. Dichas actividades se realizan mediante las páginas de los módulos **Gestión de inventarios** y **Administración de almacenes**. El procesamiento de facturas de proveedor se debe realizar mediante el espacio de trabajo **Entrada de factura de proveedor** y los pagos se deben realizar mediante el espacio de trabajo **Pagos a proveedores**.  

Los siguientes artículos proporcionan una visión general de las distintas fases por las que pasa un pedido de compra:

-   [Crear pedidos de compra](purchase-order-creation.md)
-   [Aprobar y confirmar pedidos de compra](purchase-order-approval-confirmation.md)
-   [Recepción de producto frente a pedidos de compra](product-receipt-against-purchase-orders.md)
-   [Visión general de facturas de proveedores](../../finance/accounts-payable/vendor-invoices-overview.md)

## <a name="types-of-purchase-orders"></a>Tipos de pedidos de compra
Hay tres tipos de pedidos de compra. Al crear un pedido de compra, debe especificar el tipo. Puede configurar un tipo de pedido predeterminado para nuevos pedidos en la página **Parámetros de adquisición y abastecimiento**.

| Tipo de pedido de compra        | Descripción                                                                                                                                                                                                                                                                           |
|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Diario        | Utilice este tipo para crear un pedido borrador. Este tipo no afecta a las cantidades en existencias ni genera transacciones de inventario. Las líneas de diario de pedido de compra no se incluyen en la programación maestra.                                                                                                       |
| Pedido de compra | Use este tipo para crear pedidos de compra cuando los pedidos se confirmen con un proveedor y conforme se procesen los pedidos a través de la recepción y la facturación antes de efectuar el pago al proveedor. Este tipo de pedido de compra es el más común.                                                                          |
| Pedido devuelto | Utilice este tipo cuando se devuelvan mercancías al proveedor. Este tipo de pedido requiere que especifique el número de autorización de devolución de material (RMA) que le proporciona el proveedor. Especifique el número RMA en la pestaña **General** del pedido de compra. Las líneas de pedido deben tener cantidades negativas. |

## <a name="purchase-order-statuses"></a>Estados de pedidos de compra
Los pedidos de compra incluyen varios campos de estado que indican el progreso del pedido. Todos estos campos son visibles en la vista **Encabezado** del pedido y algunos de ellos también son visibles en la visión general de cuadrícula de todos los pedidos. En el campo **Estado** se muestra el estado de las cantidades en el pedido. Los siguientes valores están disponibles:

-   **Pedido abierto**: se han creado pedidos y las cantidades están en el pedido.
-   **Recibido**: se han recibido algunas de las cantidades, pero que no se han facturado todavía.
-   **Facturado**: se ha facturado la cantidad completa del pedido. **Nota:** Si un pedido se ha facturado *parcialmente*, ni el estado **Recibido** ni **Facturado** es adecuado. Por tanto, el pedido todavía tendrá un estado de **Pedido abierto**.
-   **Cancelado**: se confirmó un pedido pero se canceló posteriormente. Por tanto, este estado indica que ya no existen cantidades abiertas en el pedido.

El campo **Estado del documento** le ayuda a revisar rápidamente el progreso del pedido en cuanto a los documentos que se han procesado. Muestra el estado del documento más reciente que se ha completado para el pedido. Los siguientes valores están disponibles:

-   **Ninguno**: no se ha procesado ningún documento para el pedido todavía.
-   **Consulta de compra**: se ha generado una consulta de compra y el pedido está en espera de comentarios por parte el proveedor.
-   **Pedido de compra**: se ha procesado la confirmación en el pedido.
-   **Recepción de producto**: se ha procesado la recepción de producto en el pedido.
-   **Factura**: se ha contabilizado una factura con el pedido.

El campo **Estado de aprobación** se utiliza cuando un pedido de compra pasa por un flujo de trabajo o proceso de revisión. Los siguientes valores están disponibles:

-   **Borrador**, **En revisión** y **Rechazado**: estos estados solo se utilizan cuando se utiliza un flujo de trabajo de aprobación para el pedido de compra.
-   **Aprobado**: este estado se asigna a los pedidos que han completado la aprobación del flujo de trabajo. Los pedidos creados sin utilizar un flujo de trabajo de aprobación reciben un estado de **Aprobado** inmediatamente.
-   **En revisión externa** : este estado se usa en escenarios donde se envía una consulta de compra al proveedor, para que el proveedor pueda confirmar las condiciones del pedido de compra. Este estado también se utiliza en el proceso iniciado por la acción **Solicitud de confirmación**. Para este proceso, al proveedor se le pide que confirme las condiciones de este pedido de compra conectándose a su sistema y registrando si confirma o rechaza el pedido.
-   **Confirmado**: este estado se asigna una vez se ha confirmado el pedido. Normalmente, este estado es el último estado de aprobación que se asigna a un pedido.


## <a name="additional-resources"></a>Recursos adicionales

[Crear pedidos de compra](purchase-order-creation.md)

[Aprobar y confirmar pedidos de compra](purchase-order-approval-confirmation.md)

[Recepción de producto frente a pedidos de compra](product-receipt-against-purchase-orders.md)

[Visión general de facturas de proveedores](../../finance/accounts-payable/vendor-invoices-overview.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]