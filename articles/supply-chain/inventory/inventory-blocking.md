---
title: Bloqueo del inventario
description: Este tema proporciona una visión general del bloqueo del inventario, que forma parte del proceso de inspección de calidad en Supply Chain Management. Puede usar el bloqueo del inventario para evitar que los artículos se procesen o se consuman.
author: perlynne
ms.date: 03/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventBlocking, InventQualityOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2094
ms.assetid: 1968e32f-eff9-4c17-8f7f-a870f0c38fbc
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 58dd5c5b3d7b2f077305fa4d420fc55702acbe7ebba049ae9ac78a1362ff2523
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6770297"
---
# <a name="inventory-blocking"></a>Bloqueo del inventario

[!include [banner](../includes/banner.md)]

Este tema proporciona una visión general del bloqueo del inventario, que forma parte del proceso de inspección de calidad en Supply Chain Management. Puede usar el bloqueo del inventario para evitar que los artículos se procesen o se consuman.

Puede bloquear artículos de inventario de las siguientes formas:

- Manualmente
- Mediante la creación de un pedido de calidad
- Mediante el uso de un proceso que genera un pedido de calidad
- Mediante el bloqueo del estado de inventario

## <a name="blocking-items-manually"></a>Bloqueo manual de artículos

Puede bloquear una cantidad de un artículo creando una transacción en la página **Bloqueo del inventario**. Solo se pueden bloquear manualmente artículos disponibles en el inventario. Para las cantidades bloqueadas manualmente, debe decidir si las actividades de planificación incluyen recepciones previstas como una cantidad disponible. Las recepciones previstas son artículos bloqueados que se espera que estén disponibles en el inventario tras completar la inspección. Puede mantener la fecha prevista. De forma predeterminada, la opción **Recepciones previstas** está seleccionada para artículos bloqueados mediante un pedido de calidad. Puede cancelar un bloqueo manual en una cantidad eliminando la transacción en la página **Bloqueo del inventario**.

## <a name="blocking-items-by-creating-a-quality-order"></a>Bloqueo de artículos creando un pedido de calidad

Puede especificar los artículos que se deben inspeccionar creando un pedido de calidad en la página **Pedidos de calidad**. Cuando crea el pedido de calidad, la cantidad de un artículo especificada se bloquea. El plan de muestreo asociado al pedido de calidad controla solo la cantidad de artículos que se debe inspeccionar, no la cantidad que se bloquea. La cantidad especificada en el pedido de calidad es la cantidad que se bloquea, independientemente de la cantidad que el plan de muestreo especifique como que se deben enviar a inspección.

> [!NOTE]
> La planificación maestra no admite el uso de la fecha de vencimiento del lote y el bloqueo del estado del inventario. Esto podría resultar en una doble exclusión del inventario disponible, que puede ocurrir durante la planificación maestra. Recomendamos que confíe en los códigos de disposición de lotes, en lugar del estado del inventario, para bloquear lotes caducados.

## <a name="blocking-items-by-using-a-process-that-generates-a-quality-order"></a>Bloqueo de artículos mediante un proceso que genera un pedido de calidad

Si un proceso de calidad especifica que se debe inspeccionar un artículo, se bloquea automáticamente una cantidad del artículo. Por tanto, cuando un pedido de calidad se genera automáticamente, el plan de muestreo del artículo asociado al pedido de calidad controla tanto la cantidad de artículos que se bloquea como la cantidad que debe inspeccionarse. Si la opción **Bloqueo completo** en la página **Muestreo de artículos** está seleccionada, la cantidad completa de, por ejemplo, una línea de pedido de compra, se bloquea durante la inspección, independientemente de la cantidad de muestreo del artículo.

### <a name="example"></a>Ejemplo

En el siguiente ejemplo, se generará un pedido de calidad al registrar un albarán de pedido de compra. En la página **Asociaciones de calidad** especificó que el registro de un albarán de pedido de compra es el proceso que activa un pedido de calidad.

|Instalación |Acción del usuario |Resultado |
|----|---|---|
| Una asociación de calidad especifica que debe generarse un pedido de calidad cuando se registre un albarán de pedido de compra. La configuración de muestreo del artículo del pedido de calidad especifica que se debe realizar una inspección del 10 por ciento de la cantidad en la línea del pedido de compra. Además, dado que la opción **Bloqueo completo** está seleccionada en la configuración de muestreo del artículo, la cantidad completa de la línea de pedido de compra debe bloquearse durante la inspección independientemente de la cantidad enviada para inspección. | Se imprimirá y registrará el albarán. | Se generará un pedido de calidad. Un diez por ciento de la cantidad del pedido de compra para el artículo se enviará para inspección. La cantidad completa de la línea del pedido de compra se bloqueará. |

## <a name="blocking-items-by-using-inventory-status-blocking"></a>Bloqueo de artículos mediante bloqueo del estado de inventario

Puede especificar qué estados de inventario son estados de bloqueo mediante el parámetro **Bloqueo de inventario** en la página **Estados de inventario**.  No puede usar los estados de inventario como estados de bloqueo para los pedidos de producción, los pedidos de ventas, los pedidos de transferencia, las transacciones de salida ni las integraciones de proyectos. Para el trabajo de salida, use artículos que tengan un estado de inventario de disponible. Si tiene artículos con estado **Roto** y la planificación maestra se ejecuta en estos artículos, se considera que faltan los artículos y el inventario se reabastece automáticamente.

## <a name="take-care-when-blocking-items-that-use-both-inventory-status-blocking-and-quality-order-blocking"></a>Tenga cuidado al bloquear artículos que utilicen tanto el bloqueo de estado de inventario como el bloqueo de pedidos de calidad

Puede crear un pedido de calidad asociado con el inventario que tiene un estado de inventario que tiene su parámetro **Bloqueo de inventario** habilitado. En este caso, la orden de calidad generará un registro de bloqueo de inventario adicional además del creado por el estado del inventario. Porque el bloqueo de inventario de pedidos de calidad tendrá el parámetro **Recibos esperados** habilitado, esto genera una transacción extra *Inventario ordenado* que también está bloqueada por su estado de inventario. Esta combinación puede generar dificultades para comprender el significado de las transacciones de inventario generadas, porque parecerá que la cantidad total bloqueada excede la cantidad total disponible. Examinemos las transacciones en un ejemplo de un recibo de 10 piezas del artículo A0001 con un pedido de calidad generado para muestrear 1 pieza. El comportamiento también dependerá de si la opción **Reservar artículos pedidos** está habilitada en la página **Parámetros de gestión de inventario y almacén**.

>[!NOTE]
>Si utiliza el bloqueo de estado de inventario y los pedidos de calidad juntos, le recomendamos encarecidamente que tenga la opción **Reservar artículos pedidos** habilitada.

### <a name="example-with-reserve-ordered-items-enabled"></a>Ejemplo con "Reservar artículos pedidos" habilitado

Cuando **Reservar artículos pedidos** está habilitado, todas las transacciones de bloqueo de inventario tendrán un estado de *Físico reservado* o *Reservado ordenado*.

| Referencia de transacciones de inventario | Recepción | Emitir | Cantidad | Sitio | Almacén | Estado de inventario | Ubicación | Matrícula de entidad de almacén | Comentario |
|---|---|---|---|---|---|---|---|---|---|
| Pedido de compra | Comprado | | 10 pcs. | 2 | 24 | Bloqueo | RECV | receiptLp1 | | 
| Bloqueo del inventario | | Física reservada | -9 pcs | 2 | 24 | Bloqueo | | | Transacción generada por el bloqueo del estado del inventario |
| Bloqueo del inventario | | Física reservada | -1 pcs | 2 | 24 | Bloqueo | RECV | receiptLp1 | Transacción generada por el bloqueo de muestreo de pedidos de calidad |
| Bloqueo del inventario | Pedido | | 1 pcs. | 2 | 24 | Bloqueo | RECV | receiptLp1 | Recibos esperados del bloqueo de muestreo de pedidos de calidad |
| Bloqueo del inventario | | Pedido reservado | 1 pcs. | 2 | 24 | Bloqueo | | | Transacción generada por el bloqueo del estado del inventario

### <a name="example-with-reserve-ordered-items-disabled"></a>Ejemplo con "Reservar artículos pedidos" deshabilitado

Cuando **Reservar artículos pedidos** está deshabilitado, los recibos esperados no se pueden reservar porque están en estado *Ordenado*, por lo que algunos bloqueos se dejarán en estado *En orden*.

| Referencia de transacciones de inventario | Recepción | Emitir | Cantidad | Sitio | Almacén | Estado de inventario | Ubicación | Matrícula de entidad de almacén | Comentario |
|---|---|---|---|---|---|---|---|---|---|
| Pedido de compra | Comprado | | 10 pcs. | 2 | 24 | Bloqueo | RECV | receiptLp1 | |
| Bloqueo del inventario | | Física reservada | -9 pcs | 2 | 24 | Bloqueo | | | Transacción generada por el bloqueo del estado del inventario |
| Bloqueo del inventario | | Física reservada | -1 pcs | 2 | 24 | Bloqueo | RECV | receiptLp1 | Transacción generada por el bloqueo de muestreo de pedidos de calidad |
| Bloqueo del inventario | Pedido | | 1 pcs. | 2 | 24 | Bloqueo | RECV | receiptLp1 | Recibos esperados del bloqueo de muestreo de pedidos de calidad |
| Bloqueo del inventario | | En pedido | 1 pcs. | 2 | 24 | Bloqueo | RECV | receiptLp1 | Transacción generada por el bloqueo del estado del inventario

Tenga en cuenta la diferencia en el estado y las dimensiones de la transacción entre los dos casos. Por este motivo, recomendamos habilitar la opción **Reservar artículos pedidos**.

<!-- KFM: (Enable this section when the feature leaves private preview)

### Disable expected receipts from quality orders that sample blocked inventory feature

To simplify the inventory transactions in the case of quality orders that sample inventory blocked as a consequence of inventory status, the system provides a feature that disables expected receipts from such quality orders. As the expected receipt is in any case immediately blocked by inventory status blocking, there is no reduction of on-hand inventory because of this change.

-->

## <a name="additional-resources"></a>Recursos adicionales

[Creación y mantenimiento de un bloqueo del inventario](tasks/create-maintain-inventory-blocking.md)

[Procesos de administración de la calidad](quality-management-processes.md)

[Inspección de la calidad de las mercancías](tasks/inspect-quality-goods.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]