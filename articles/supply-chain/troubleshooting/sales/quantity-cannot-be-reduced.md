---
title: La cantidad no se puede reducir cuando se cancela un pedido de cliente.
description: La cantidad no se puede reducir cuando se cancela un pedido de ventas.
author: hja-ms
ms.date: 5/17/2021
ms.topic: troubleshooting
ms.search.form: SalesTable_SalesCancelOrder, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: hja
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1a2cc9c9fd3d085508fc652bc9ee0a352d869dee
ms.sourcegitcommit: a02d3d64c899f8554b74342d5a1856d824bf1abe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2021
ms.locfileid: "6230845"
---
# <a name="the-quantity-cant-be-reduced-when-a-sales-order-is-canceled"></a>La cantidad no se puede reducir cuando se cancela un pedido de cliente.

Código de error: SYS138831

## <a name="symptoms"></a>Síntomas

El sistema muestra el siguiente mensaje de error:

> La cantidad no se puede reducir. El número de transacciones de inventario en el pedido es demasiado bajo porque la cantidad o parte de ella está referenciada por una orden de salida o una orden de producción o está marcada con otras transacciones.

## <a name="cause"></a>Causa

Si el trabajo está asociado con un pedido de venta, no puede cancelar el pedido de venta hasta que el trabajo se cancele y se revierta. Este requisito se aplica incluso si el trabajo asociado con el pedido de ventas está cerrado.

## <a name="resolution"></a>Resolución

Para solucionar este problema, complete las siguientes tareas:

1. Cancele el trabajo abierto.
1. Elimina la carga.
1. Reduzca la cantidad seleccionada.

### <a name="cancel-open-work"></a>Cancele el trabajo abierto

Para cancelar el trabajo abierto, siga estos pasos.

1. Vaya a **Gestion de almacenes \> Tareas periódicas \> Limpiar \> Cancelar trabajo**.
1. En el campo **Id. de trabajo**, especifique el id. del trabajo que desea cancelar, y que actualmente tiene un valor de **Estado del trabajo** de *Abierto*, *En curso*, *Cancelado*, *Combinado* o *Cerrado*.
1. Seleccione **Aceptar**.
1. Seleccione **Sí** para confirmar que desea cancelar el trabajo.

### <a name="delete-the-load"></a>Eliminar la carga

Para eliminar una carga, siga estos pasos.

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. Abra el pedido de ventas pertinente.
1. En la ficha desplegable **Líneas de pedido de venta**, seleccione **Almacén \> Detalles del trabajo**.
1. En la página **Trabajo**, en el panel de acciones, en la pestaña **Trabajo**, en el grupo **Trabajo**, seleccione **Cancelar trabajo**.
1. Confirme que el campo **Situación de trabajo** está configurado en *Cancelado*.
1. Cierre la página **Trabajo**.
1. En la página de detalles del pedido de venta, en la ficha desplegable **Líneas de pedido de ventas**, seleccione **Almacén \> Detalles de carga**.
1. En el panel de acciones, seleccione **Eliminar**.
1. Seleccione **Sí** para confirmar que desea eliminar la carga.
1. Cierre la página **Carga**.

### <a name="reduce-the-picked-quantity"></a>Reduzca la cantidad seleccionada

Una vez cancelado todo el trabajo, siga estos pasos para reducir la cantidad recogida.

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. Abra el pedido de ventas pertinente.
1. En la ficha desplegable **Líneas de pedido de ventas**, seleccione **Línea de actualización \> Seleccionar** desde la barra de herramientas.
1. En la página **Seleccionar**, en la sección **Transacciones**, seleccione la línea donde el campo **Estado de incidencia** está configurado en *Seleccionado*.
1. En la sección **Transacciones**, seleccione **Agregar línea de selección** desde la barra de herramientas.
1. En la sección **Líneas de selección**, seleccione **Confirmar la selección de todo** desde la barra de herramientas.
1. Cierre la página **Selección**.
1. En la página de detalles del pedido de ventas, en el panel de acciones, en la pestaña Pedido **de ventas**, en el grupo **Mantener**, seleccione **Cancelar**.
1. Seleccione **Sí** para confirmar que desea cancelar el pedido de ventas.
