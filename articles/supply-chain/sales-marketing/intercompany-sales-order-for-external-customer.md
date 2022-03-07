---
title: Crear y facturar un pedido de venta de empresas vinculadas para un cliente externo
description: Este tema explica cómo crear y facturar un pedido de venta de empresas vinculadas para un cliente externo
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
ms.openlocfilehash: 72273a125da2e6c4a2fc16b449cd5077f3d767df
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548510"
---
# <a name="create-and-invoice-an-intercompany-sales-order-for-an-external-customer"></a>Crear y facturar un pedido de venta de empresas vinculadas para un cliente externo

[!include [banner](../../includes/banner.md)]

Puede usar el comercio entre empresas vinculadas para registrar la venta de un producto a partir de una entidad jurídica a otra entidad jurídica que se encuentre en la misma organización.

Al crear un pedido de ventas original, puede crear automáticamente un pedido de compra de empresas vinculadas para el proveedor de empresas vinculadas. Esto crea automáticamente un pedido de ventas de empresas vinculadas en la entidad jurídica del proveedor de empresas vinculadas.

En el ejemplo siguiente se muestra el flujo de las transacciones al crear un pedido de ventas para un cliente externo, pero el producto se debe solicitar de una entidad jurídica diferente en su organización antes de que pueda entregar el producto al cliente. En este caso, un pedido de compra de empresas vinculadas se crea para la cuenta de proveedor que representa la otra entidad jurídica. A su vez, un pedido de ventas de empresas vinculadas se crea en otra entidad jurídica para la cuenta de cliente que representa la entidad jurídica. Cuando un pedido de compra de empresas vinculadas se registra mediante factura, la factura para el pedido de ventas original se registra automáticamente si es una entrega directa.

![Proceso de ventas externas entre empresas vinculadas](media/intercompanyexternalsalesprocess.png)

Si usa la entrega directa y selecciona **Albarán** en el campo **Cantidad** de la página **Factura de envío** , la factura de proveedor de empresas vinculadas se basará en la recepción de producto de empresas vinculadas registrada anteriormente.

## <a name="prerequisites"></a>Requisitos previos

Antes de empezar, asegúrese de que los siguientes requisitos previos se cumplen para registrar e imprimir automáticamente las facturas de empresas vinculadas.

1. Vaya a **Ventas y marketing \> Clientes \> Todos los clientes**.
1. En el panel de acciones, en la pestaña **General**, seleccione **Empresas vinculadas**.
1. Vaya a **Adquisición y abastecimiento \> Proveedores \> Todos los proveedores**.
1. En el panel de acciones, en la pestaña **General**, seleccione **Empresas vinculadas**.
1. En la página **Empresas vinculadas** para el proveedor o el cliente, en la zona **Directivas de pedidos de compra**, en el grupo de campo **Pedido de compra de empresas vinculadas (entrega directa)**, seleccione la casilla **Contabilizar la factura automáticamente**.
1. En la zona **Directivas de pedidos de compra**, en el grupo de campo **Pedido de venta original (entrega directa)**, seleccione la casilla **Contabilizar la factura automáticamente**. Seleccione la casilla si desea que la factura del pedido de ventas original se imprima automáticamente al registrar la factura de proveedor de empresas vinculadas.

> [!NOTE]
> La configuración de impresión para la factura se determina por la configuración del módulo, documento o la transacción en la página **Imprimir configuración de administración** .

## <a name="create-an-original-sales-order-for-an-external-customer"></a>Cree un pedido de ventas original para un cliente externo

Siga estos pasos en la entidad jurídica A. Este procedimiento corresponde al cuatro con la etiqueta 1 en la ilustración.

1. Vaya a **Clientes \> Pedidos de ventas \> Todos los pedidos de venta**.
1. Desde la página de la lista **Todos los pedidos de venta**, crea el pedido de ventas original. Los valores de campo se copian desde la cuenta del cliente al pedido de ventas.
1. En la página **Pedidos de ventas**, seleccione **Vista de encabezado** en el panel de acciones.
1. En la ficha desplegable **Configuración de empresas vinculadas**, seleccione la casilla **Crear automáticamente pedidos de empresas vinculadas**.
1. Si desea que su proveedor de empresas vinculadas entregue directamente el artículo al cliente externo, seleccione la casilla de verificación **Entrega directa**.
1. Cuando haya terminado de especificar el pedido de ventas, cierre la página **Pedidos de ventas**.

El pedido de compra de empresas vinculadas se crea de forma automática para todos los artículos que se han asignado a un proveedor de empresas vinculadas y, a continuación, se crea el pedido de ventas de empresas vinculadas. Un mensaje de información le informa que se ha creado un pedido de compra de empresas vinculadas y un pedido de ventas de empresas vinculadas. El mensaje también contiene vínculos a dichos pedidos. Si no se encontró un artículo, se muestra una advertencia roja que significa que el proceso de creación del pedido no se completó.

> [!NOTE]
> Si va a crear varios pedidos con distintas entidades jurídicas y los artículos no se encontraron en una de ellas, el proceso de creación de pedidos se detiene incluso para las entidades jurídicas que podían cumplir sus pedidos.

## <a name="invoice-an-intercompany-sales-order"></a>Facturar el pedido de ventas de empresas vinculadas

Cuando se facturan los pedidos de ventas de empresas vinculadas, el pedido de compra de empresas vinculadas correspondiente se registra en una factura automáticamente si se trata de una entrega directa. A continuación, si el pedido de ventas original es un pedido de entrega directa, se factura automáticamente.

Siga estos pasos en la entidad jurídica B. Este procedimiento corresponde al cuatro con la etiqueta 2 en la ilustración.

1. Vaya a **Clientes \> Pedidos de ventas \> Todos los pedidos de venta**.
1. En la página de la lista **Todos los pedidos de venta**, seleccione el pedido de ventas de empresas vinculadas.
1. En el panel de acciones, seleccione la pestaña **Factura** y, a continuación, vuelva a seleccionar **Factura**.
1. Active la casilla **Contabilizar**.
1. Seleccione el pedido de ventas y seleccione **Aceptar**.

La factura de cliente para el pedido de ventas de empresas vinculadas se registra automáticamente en la entidad jurídica B. La factura de proveedor de empresas vinculadas se crea y se registra automáticamente en la entidad jurídica A. Si el pedido de ventas original se configura como entrega directa, la factura de cliente se crea para el pedido de ventas original en la entidad jurídica A.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
