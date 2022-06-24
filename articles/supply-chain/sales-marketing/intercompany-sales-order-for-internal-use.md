---
title: Crear un pedido de ventas de empresas vinculadas para su uso interno
description: Este artículo explica cómo crear un pedido de ventas de empresas vinculadas para uso interno
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: a37b8ab1b3df10cdbd3bbb87410bc3dc70dc0ed0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873532"
---
# <a name="create-an-intercompany-sales-order-for-internal-use"></a>Crear un pedido de ventas de empresas vinculadas para su uso interno

[!include [banner](../../includes/banner.md)]

Normalmente, un pedido de ventas de empresa vinculada se crea automáticamente, en función de un pedido de compra de empresas vinculadas. También puede crear manualmente un pedido de venta de empresas vinculadas, que generará un pedido de compra de empresas vinculadas en la entidad jurídica del cliente de empresas vinculadas.

![Proceso de ventas internas entre empresas vinculadas](media/intercompanyinternalsalesprocess.png)

## <a name="create-an-intercompany-sales-order-manually"></a>Crear un pedido de ventas de empresas vinculadas de forma manual

Siga estos pasos en la entidad jurídica B, como se muestra en el ejemplo.

1. Vaya a **Clientes \> Pedidos de ventas \> Todos los pedidos de venta**.
1. En el panel de acciones, seleccione **Pedido de ventas** para crear un pedido de ventas.
1. En la página **Crear orden de venta**, seleccione una cuenta de cliente. En la ficha desplegable **General**, compruebe que esté activada la casilla de verificación **Empresas vinculadas**. Esto indica que el cliente seleccionado es un cliente de empresas vinculadas.
1. Especifique o modifique la información seleccione **Aceptar** y, a continuación, complete las líneas de pedido de la forma habitual.

    El valor del campo **Dirección de entrega** se copiará desde el encabezado del pedido de venta de empresas vinculadas al encabezado del pedido de compra de empresas vinculadas. El valor del campo **Número de artículo, incluidas las dimensiones del producto, y los valores de campo** **Fecha de entrega** y **Código de divisa** se copian de las líneas de pedido de venta de empresas vinculadas a las líneas de pedido de compra de empresas vinculadas.

1. En la cabecera del pedido, seleccione **Empresas vinculadas** para ver el pedido de compra de empresas vinculadas relacionado.
1. En las líneas de pedido, seleccione **Empresas vinculadas** para ver la información acerca del inventario disponible para el comercio entre empresas vinculadas.

> [!TIP]
> Puede ver los pedidos de ventas de empresas vinculadas en la página **Pedidos de empresas vinculadas**.

> [!NOTE]
> Cuando trabaje con empresas vinculadas, le recomendamos que desmarque la casilla **Eliminar pedido después de facturar** en la página **Parámetros de cuentas por cobrar**. Si no, se eliminará el pedido de compra relacionado. También le recomendamos que desmarque la casilla **Eliminar pedido después de facturar** en la página **Parámetros de proveedores**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
