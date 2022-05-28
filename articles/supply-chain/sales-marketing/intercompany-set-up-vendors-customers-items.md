---
title: Configurar proveedores, clientes y artículos para el comercio entre empresas vinculadas
description: Este tema explica cómo configurar proveedores, clientes y artículos para el comercio entre empresas
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 3e1eb7b8673f3af682204b65b33a1d8b61742721
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675048"
---
# <a name="set-up-vendors-customers-and-items-for-intercompany-trade"></a>Configurar proveedores, clientes y artículos para el comercio entre empresas vinculadas

[!include [banner](../../includes/banner.md)]

Si desea preparar a la organización para el comercio entre empresas vinculadas, debe definir los proveedores y los clientes con los que comerciará internamente. Tendrá que asociar estos proveedores y clientes con los artículos que comprará o venderá.

1. Vaya a **Adquisición y abastecimiento \> Proveedores \> Todos los proveedores**.
1. Seleccione el proveedor para definirlo como proveedor de empresa vinculada.
1. En el panel de acciones, en la pestaña **General**, seleccione **Empresas vinculadas**.
1. Especifique los parámetros de configuración de empresas vinculadas para la cuenta de proveedor. Estos parámetros incluyen la entidad jurídica y la cuenta del cliente, las directivas de los pedidos de ventas, las directivas de los pedidos de compras, la asignación de valores, así como las directivas de los acuerdos de compras y de ventas. También especificará si desea utilizar los valores de los datos base de la cuenta del proveedor o de la cuenta del cliente en la otra entidad jurídica.
1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. En la página de lista **Productos emitidos** , seleccione los artículos que desea asignar al proveedor, de manera que los artículos estén disponibles para el comercio entre empresas vinculadas. Para cada artículo, abra la página **Detalles de producto emitido**. En la pestaña **Compra**, en el campo **Proveedor**, escriba el número de proveedor.
1. Vaya a **Clientes \> Clientes \> Todos los clientes**.
1. Seleccione el cliente para definirlo como cliente de empresa vinculada.
1. En el panel de acciones, en la pestaña **General**, seleccione **Empresas vinculadas**.
1. Especifique los parámetros de configuración de empresas vinculadas para la cuenta de cliente. Estos parámetros incluyen la entidad jurídica y la cuenta del proveedor, las directivas de los pedidos de compras, las directivas de los pedidos de ventas, la asignación de valores, así como las directivas de los acuerdos de ventas y de compras. También especificará si desea utilizar los valores de los datos base de la cuenta del cliente o de la cuenta del proveedor en la otra entidad jurídica.
1. En la página **Clientes**, en la ficha desplegable **Factura y entrega**, seleccione la casilla de verificación **Crear pedidos de empresas vinculadas**. Si desea que los pedidos se entreguen directamente a los clientes, active la casilla de verificación **Entrega directa**.

    > [!NOTE]
    > Si hay algunos artículos que la organización almacena y entrega a los clientes, es posible que no desee crear pedidos de empresas vinculadas de forma automática, incluso si tiene el artículo en existencias. Para desactivar la creación automática de pedidos de artículos que pueda tener en algún momento en existencias, desactive la casilla de verificación **Crear pedidos de empresas vinculadas**.

1. Si desea permitir la creación indirecta de líneas adicionales en un pedido de ventas, active la casilla de verificación **Crear líneas de pedido indirectas**. Un usuario,por lo tanto, puede agregar líneas al pedido de ventas original a partir del pedido de ventas de empresas vinculadas.

> [!WARNING]
> Si permite la creación indirecta de líneas de pedido, está permitiendo todas las adiciones al pedido de ventas original desde el pedido de ventas de empresas vinculadas. Cada adición se procesa a continuación a través del cliente y se agrega al pedido y a la factura. Además, cada documento implicado en la venta se imprime y registra automáticamente. No se avisará a los usuarios sobre la adición.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
