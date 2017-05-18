---
title: Entregas directas
description: "Este artículo proporciona información sobre las entregas directas. Las entregas directas son entregas que se envían directamente del proveedor al cliente."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PurchCreateFromSalesOrder, SalesTable
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 9704
ms.assetid: 64c51384-8a4e-45d0-83c1-12cea22902f9
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 7c51d5505ead8e18f17917a4a02c2e0ee8265516
ms.contentlocale: es-es
ms.lasthandoff: 04/25/2017


---

# <a name="direct-deliveries"></a>Entregas directas

[!include[banner](../includes/banner.md)]


Este artículo proporciona información sobre las entregas directas. Las entregas directas son entregas que se envían directamente del proveedor al cliente.

Las entrega directas reducen el tiempo de entrega y los costes asociados con la realización de inventario, puesto que se no retienen los productos en el almacén antes de enviarlos al cliente.  

Puede crear entregas directas desde la página **Pedido de ventas**. Primero, cree un pedido de ventas y líneas de pedido. A continuación, en el panel de acciones, en la ficha **Pedido de ventas**, seleccione **Entrega directa**. Por último, especifique las líneas que se deben gestionar como entrega directa. Se creará un vínculo entre las líneas del pedido de ventas para la entrega directa y las líneas correspondientes del pedido de compra.  

**Nota**: si una parte de la cantidad pedida ya se ha entregado, debe dividir la cantidad restante. Cree una nueva línea para la cantidad que se debe entregar directamente y reste esa cantidad de la cantidad de la línea original. Por ejemplo, si la cantidad original era de 15 y se han entregado cinco, debe crear una nueva línea para la cantidad restante, 10, y después reduzca la cantidad original en dicho importe.  

Una vez creado el vínculo de entrega directa entre las líneas del pedido de ventas y las del pedido de compra, se puede actualizar el pedido de ventas mediante un albarán. Permite ejecutar una actualización de albarán o de factura del pedido de compra. Se debe actualizar la factura del pedido de ventas desde la página **Pedido de ventas**. La actualización de una factura no puede hacer que la cantidad del pedido de ventas sobrepase la cantidad que se ha registrado como recibida. Por ejemplo, una línea de pedido de ventas tiene 10 piezas, pero solo cinco piezas de la línea de pedido de ventas se han actualizado mediante un albarán. Si selecciona **Todo** en la lista **Cantidad** al actualizar mediante factura un pedido de ventas, solo aquellos artículos que se han recibido físicamente, o se han actualizado mediante un albarán, se actualizarán mediante factura. No se actualizará la línea de pedido de ventas completa.

## <a name="delivery-date"></a>Fecha de entrega
Cuando se actualiza el campo **Fecha de recepción solicitada** de la línea del pedido de ventas, también se actualiza el campo **Fecha de entrega** de la línea del pedido de compra correspondiente. Asimismo, cuando se actualiza el campo **Confirmado** de la línea del pedido de compra, también se actualizan los campos **Fecha de recepción confirmada** y **Fecha de envío confirmada** de la línea del pedido de ventas correspondiente.

## <a name="delivery-address"></a>Dirección de entrega
Por lo general, la dirección de entrega de un pedido de compra es la dirección de la empresa. Sin embargo, cuando se crea una entrega directa, se indica la dirección del cliente como dirección de entrega. Si se modifica la dirección de entrega en una línea del pedido de compra que tiene una entrega de tipo **Entrega directa**, la dirección de entrega en la línea del pedido de ventas correspondiente también se actualiza. Del mismo modo, si se modifica la dirección de entrega de la línea del pedido de ventas, también se actualizará la dirección de entrega de la línea del pedido de compra con esta nueva dirección.

## <a name="deleting-order-lines"></a>Eliminar líneas del pedido
Si prueba a eliminar una línea de pedido de ventas que tenga un tipo de entrega **Entrega directa**, aparecerá un cuadro de mensaje que indica que las líneas de pedido de compra se han adjuntado a la línea. Si la línea del pedido de ventas se ha entregado parcialmente, no se puede eliminar la línea del pedido de ventas, ni las líneas correspondientes del pedido de compra.

## <a name="warehouse"></a>Almacén
Cuando crea una entrega directa, los artículos que vende nunca llegan físicamente a su almacén. Sin embargo, debe seguir especificando un almacén en la línea de pedido de ventas. Del mismo modo, los requisitos de picking se pueden especificar en el grupo de modelos de artículos para el artículo. Sin embargo, dado que los artículos nunca llegan físicamente a su almacén, se omiten estos requisitos cuando el pedido de ventas es una entrega directa.




