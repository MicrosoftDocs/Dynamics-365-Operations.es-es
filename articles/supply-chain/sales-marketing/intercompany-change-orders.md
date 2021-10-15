---
title: Cambiar pedidos de empresas vinculadas
description: Este tema explica cómo cambiar la funcionalidad de pedidos de empresas vinculadas
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 1129794bf0ac6513770f8b2a0eeb7fb6154d7942
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548526"
---
# <a name="change-intercompany-orders"></a>Cambiar pedidos de empresas vinculadas

[!include [banner](../../includes/banner.md)]

Al modificar un pedido de compra o de ventas de empresas vinculadas, el cambio también se refleja en el pedido de compra o de ventas de la empresa correspondiente.

## <a name="adding-new-lines"></a>Adición de líneas nuevas

Si el pedido de ventas original forma parte de la cadena de pedidos de empresas vinculadas, puede agregar líneas nuevas a un pedido de compra y de ventas de empresas vinculadas. También puede agregar líneas nuevas si el pedido de ventas original no es una entrega directa. Si el pedido de ventas original es una entrega directa, sólo podrá agregar nuevas líneas al pedido de compra y de ventas de empresas vinculadas si selecciona el campo **Permitir creación indirecta** en la ficha desplegable **Configuración de empresas vinculadas** del pedido de ventas original.

## <a name="changing-prices-and-discounts"></a>Cambio de precios y descuentos

Puede cambiar los precios y descuentos si las casillas **Permitir editar el precio** y **Permitir edición de descuento** están seleccionadas en la página **Empresas vinculadas**.

Si modifica el precio unitario de una de las líneas existentes de la línea de pedido de ventas de empresas vinculadas, también se modifica el precio unitario del pedido de compra de empresas vinculadas.

Si modifica algún campo de descuento de la línea de pedido de ventas de empresas vinculadas, los campos de descuento correspondientes del pedido de compra de empresas vinculadas se actualizan.

## <a name="changing-and-adding-new-charges"></a>Cambio y adición de gastos nuevos

Puede cambiar cargos si las casillas **Permitir editar el precio** y **Permitir edición de descuento** están seleccionadas en la página **Empresas vinculadas**.

Si agrega un gasto nuevo al encabezado del pedido de ventas de empresas vinculadas y otro a la línea de ventas de empresas vinculadas, ambos se copian en el pedido de compra de empresas vinculadas. Por tanto, el pedido de ventas y el pedido de compra de empresas vinculadas tienen el mismo importe total. Los gastos nunca se copian en el pedido de ventas original.

## <a name="copying-a-fee"></a>Copia de una cuota

Para copiar una cuota en el pedido de ventas original, créela como una línea de ventas nueva con un artículo del tipo **Servicio**.

## <a name="changing-quantities-and-deleting-intercompany-purchases-and-sales-order-lines"></a>Cambio de cantidades y eliminación de líneas de pedidos de compra y ventas de empresas vinculadas

Sólo puede modificar la cantidad o eliminar una línea de pedido de compra o de ventas de empresas vinculadas si la línea se ha creado directamente a partir del formulario **Pedido de ventas** o **Pedido de compra**. Este cambio convierte las líneas del pedido de compra o de ventas de empresas vinculadas en el origen.

## <a name="origins-of-orders-and-order-lines"></a>Orígenes de pedidos y líneas de pedidos

Los pedidos y las líneas de pedidos de empresas vinculadas pueden tener uno de los dos orígenes siguientes:

- **Derivado**: el pedido se creó automáticamente a partir de una cadena de pedidos de empresas vinculadas.
- **Fuente**: un usuario creó manualmente el pedido.

El origen se indica en el encabezado del pedido de los pedidos de compras de empresas vinculadas y pedidos de ventas en el campo **Origen**. Este campo se encuentra en la ficha desplegable **Configuración de empresas vinculadas** en el pedido de venta y en la ficha desplegable **Configuración** en el pedido de compra.

Los orígenes **Derivado** y **Fuente** sólo se aplican a pedidos de empresas vinculadas. El campo **Origen** estará en blanco para el resto de pedidos de venta, pedidos de compra y líneas de pedido. Este campo también estará en blanco en el pedido de ventas original.

## <a name="example-derived-origin"></a>Ejemplo: origen derivado

Supongamos que crea un pedido de ventas original para un cliente externo. Este pedido de ventas incluye una línea de pedido. El pedido de ventas original crea un pedido de compra de empresas vinculadas que incluye una línea de pedido, el cual a su vez crea un pedido de ventas de empresas vinculadas que también incluye una línea de pedido. El encabezado del pedido de compra de empresas vinculadas y la línea de pedido se crean automáticamente a partir del pedido de ventas original.

El valor del campo **Origen** de la ficha desplegable **Configuración** del pedido de compra de empresas vinculadas y la ficha desplegable **Configuración de empresas vinculadas** de los encabezados de pedidos de ventas de empresas vinculadas es **Derivado**. El valor del campo **Origen** de la ficha **Detalles de línea** de las líneas de pedido de ventas y de compra también es **Derivado**.

Si una línea de pedido tiene el origen **Derivado**, no se puede eliminar directamente. La línea de pedido sólo se puede eliminar desde el origen en el que se creó. Asimismo, sólo podrá modificar la cantidad solicitada desde el origen en el que se creó la línea del pedido.

Si un pedido de ventas y una línea de pedido de ventas originales forman parte de la cadena de pedidos de empresas vinculadas, podrá modificar las cantidades solicitadas desde el pedido de ventas original y eliminar las líneas de pedido del pedido de ventas original.

## <a name="example-source-origin"></a>Ejemplo: origen fuente

Supongamos que crea un pedido de compra para un proveedor de empresas vinculadas. La línea de pedido y el pedido de compra de empresas vinculadas tienen el **Origen**. Por lo tanto, este pedido de compra de empresas vinculadas será el controlador y el pedido de ventas de empresas vinculadas que se crea automáticamente en la empresa del proveedor tendrá el origen **Derivado**.

Además, las cantidades solicitadas de una línea de pedido creada en el pedido de compra de empresas vinculadas no se puede modificar en el pedido de ventas de empresas vinculadas. La línea de pedido sólo se puede eliminar desde el pedido de compra de empresas vinculadas. Si se agrega una nueva línea al pedido de ventas de empresas vinculadas, la línea del pedido de ventas de empresas vinculadas tendrá el origen **Origen**.

Si un pedido de ventas original forma parte de la cadena de pedidos de empresas vinculadas, puede controlar los pedidos y las líneas de pedidos de empresas vinculadas desde el pedido de ventas original.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
