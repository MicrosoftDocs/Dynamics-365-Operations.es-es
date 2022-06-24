---
title: Compruebe las discrepancias del precio de pedido de empresas vinculadas
description: Este artículo explica cómo verificar las discrepancias en el precio de los pedidos de empresas vinculadas
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
ms.openlocfilehash: ca27e86545ba8179c595e55487dbbf49cd9ec528
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890694"
---
# <a name="check-intercompany-order-price-discrepancies"></a>Compruebe las discrepancias del precio de pedido de empresas vinculadas

[!include [banner](../../includes/banner.md)]

Puede utilizar este procedimiento para comprobar si existen discrepancias de precio en los de pedidos de empresas vinculadas.

1. Vaya a **Adquisiciones y abastecimiento \> Periódico \> Limpiar \> Verificar las discrepancias en el precio de los pedidos de empresas vinculadas**.
1. Configure un trabajo por lotes, si es necesario, y seleccione **Aceptar** para comprobar los precios y descuentos de los pedidos de ventas de empresas vinculadas y los pedidos de compra. De lo contrario, seleccione **Cancelar** para cerrar la página sin realizar la comprobación.

    > [!TIP]
    > Si hay problemas de sincronización o problemas con los precios, aparecerán en un mensaje de información. Puede imprimir el mensaje de información para su referencia.

1. En el mensaje de información, seleccione la línea correspondiente para abrir la entidad jurídica actual. Abra el pedido en la entidad jurídica relacionada seleccionando **Empresas vinculadas**, y luego **Pedido de compra de empresas vinculadas** o **Pedido de ventas de empresas vinculadas**.

    > [!NOTE]
    > Para permitir una actualización del pedido entre empresas vinculadas:
    >
    > 1. Vaya a **Clientes \> Clientes \> Todos los clientes**.
    > 1. En el panel de acciones, seleccione la pestaña **General** y, a continuación, vuelva a seleccionar **Empresas vinculadas**.
    > 1. En la página **Empresas vinculadas** página, seleccione **Directivas de pedidos de compra** o **Directivas de pedidos de venta**.
    > 1. Seleccione **Permitir editar el precio** y **Permitir edición de descuento** en ambas áreas.

1. Abra el pedido de empresa vinculada relevante donde desee mantener el precio.
1. Para cada línea de pedido, cambie el campo **Precio unitario** de la línea y, después, devuélvala a su valor original. Cambie el campo **Descuento** de la línea y devuélvala a su estado original y, a continuación, haga lo mismo con los campos **Cargos en compras** o **Cargos en ventas**. Al cambiar los valores, activará la sincronización de los precios, los descuentos y los gastos de esta línea de pedido de empresa vinculada a la línea de pedido de empresa vinculada a la que se hace referencia de manera que se alineen automáticamente.

    > [!NOTE]
    > Esta sincronización sólo es válida si el pedido de ventas de las empresas vinculadas no se ha facturado. Si este pedido se ha registrado en una factura y se ha creado un diario de facturas de cliente, los cambios se deberán realizar directamente en las líneas del pedido de compra de empresas vinculadas mediante el establecimiento de precios, descuentos y gastos varios iguales a los del diario de factura de cliente de empresas vinculadas. Si no se lleva a cabo, el pedido de compra de empresas vinculadas no se podrá registrar en la factura debido a que no coincidirán los totales del pedido.

1. Repita el procedimiento hasta que los pedidos de compra y ventas de empresas vinculadas se hayan sincronizado.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
