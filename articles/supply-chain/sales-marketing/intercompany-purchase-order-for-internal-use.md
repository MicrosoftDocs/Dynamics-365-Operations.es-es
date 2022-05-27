---
title: Crear y facturar un pedido de compra de empresas vinculadas para su uso interno
description: Este tema explica cómo crear y facturar un pedido de compra de empresas vinculadas para uso interno
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchLineOpenOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 52b58b2dcecd5d9a83a47b425d6fb13b36c40b60
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675890"
---
# <a name="create-and-invoice-an-intercompany-purchase-order-for-internal-use"></a>Crear y facturar un pedido de compra de empresas vinculadas para su uso interno

[!include [banner](../../includes/banner.md)]

Puede crear un pedido de compra de empresas vinculadas para un proveedor de empresas vinculadas. Esto crea automáticamente un pedido de ventas de empresas vinculadas en el proveedor de empresas vinculadas.

![Proceso de compra interna para empresas vinculadas](media/intercompanypurchaseprocess.png)

## <a name="create-an-intercompany-purchase-order-and-a-corresponding-intercompany-sales-order"></a>Crear un pedido de compra de empresas vinculadas y un pedido de ventas de empresas vinculadas correspondiente

Siga estos pasos en la entidad jurídica AAA, como se muestra en la ilustración.

1. Vaya a **Proveedores** \> **Pedidos de compra** \> **Todos los pedidos de compra**.
1. En la página de lista **Todos los pedidos de compras**, cree un pedido de compra para un proveedor de empresas vinculadas. Los valores del campo se copian de la cuenta de proveedor al pedido de compra.

    Dado que trabaja con un proveedor de empresas vinculadas, un pedido de ventas de empresas vinculadas se crea en la entidad jurídica que corresponde al proveedor. El número del pedido de ventas de empresas vinculadas puede ser el mismo que el número del pedido de compra de empresas vinculadas, y puede incluir el identificador de la entidad jurídica. La estructura numérica que se use dependerá de la selección en el campo **Numeración de pedido de compras** en la página **Empresas vinculadas**. Por ejemplo, si crea el pedido de compra 00029\_064 en la entidad jurídica AAA, el número de pedido de ventas en la entidad jurídica BBB es AAA00029\_64.

    Un mensaje de información le informa que se ha creado un pedido de compra de empresas vinculadas y un pedido de ventas de empresas vinculadas. El mensaje incluye el número de pedido de ventas de empresas vinculadas, para su información.

1. Agregue artículos de línea al pedido de compra. Los artículos de línea correspondientes se agregan automáticamente al pedido de ventas de empresas vinculadas. Si un artículo no existe en la otra entidad jurídica, se mostrará un mensaje y no podrá agregar el artículo al pedido de compra. Para solucionar el problema, cambie a la otra entidad jurídica y libere el producto a esa entidad jurídica. El artículo estará disponible para agregarlo a los pedidos de ventas en esa entidad jurídica. A continuación, vuelva a la entidad jurídica del pedido de compra y siga agregando artículos de línea.
1. Cuando haya terminado de especificar la información del pedido de compra, confírmelo.

## <a name="process-the-intercompany-packing-slip-and-customer-invoice"></a>Procesar el albarán y la factura de cliente de empresas vinculadas

Siga estos pasos en la entidad jurídica BBB, como se muestra en la ilustración.

1. Vaya a **Clientes \> Pedidos de ventas \> Todos los pedidos de venta**.
1. En la página de la lista **Todos los pedidos de venta**, seleccione el pedido de ventas de empresas vinculadas.
1. En el panel de acciones seleccione la pestaña **Seleccionar y empaquetar** y después **Albarán**.
1. Active la casilla **Contabilizar**.
1. Seleccione **Aceptar**. El albarán se registra en la entidad jurídica BBB.
1. En la página de la lista **Todos los pedidos de venta**, seleccione el pedido de ventas de empresas vinculadas.
1. En el panel de acciones, seleccione la pestaña **Factura** y, a continuación, vuelva a seleccionar **Factura**.
1. Active la casilla **Contabilizar**.
1. Seleccione **Aceptar**.

    La factura de cliente para el pedido de ventas de empresas vinculadas se registra en la entidad jurídica BBB.

## <a name="process-the-intercompany-product-receipt-and-vendor-invoice"></a>Procesar la recepción de producto y la factura de proveedor de empresas vinculadas

Siga estos pasos en la entidad jurídica AAA, como se muestra en la ilustración.

1. Vaya a **Proveedores \> Pedidos de compra \> Todos los pedidos de compra**.
1. En la página de la lista **Todos los pedidos de compras**, seleccione el pedido de compras de empresas vinculadas.
1. En el panel de acciones, seleccione **Recibo** y después seleccione **Recibo del producto**. Se crea la recepción de producto. El número de recepción de producto es el mismo que el número de albarán de empresas vinculadas.
1. Active la casilla **Contabilizar**.
1. Seleccione **Aceptar**.
1. En la página de la lista **Todos los pedidos de compras**, seleccione el pedido de compras de empresas vinculadas.
1. En el panel de acciones, seleccione **Factura** y, a continuación, **Factura**. Se crea la factura de proveedor. El número de la factura de proveedor es el mismo que el número de la factura de cliente de empresas vinculadas.
1. Termine de especificar la información de la factura de proveedor y regístrela.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
