---
title: Filtrar pedidos de empresas vinculadas para evitar sincronizar pedidos y líneas de pedido
description: Este tema describe cómo filtrar pedidos de empresas vinculadas para evitar sincronizar pedidos y líneas de pedido.
author: negudava
manager: tfehr
ms.date: 11/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: negudava
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 6c5e1e2467673badd20366d3bd8e1b93b8078b26
ms.sourcegitcommit: 0eb33909a419d526eb84b4e4b64d3595d01731ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "4701042"
---
# <a name="filter-intercompany-orders-to-avoid-synchronizing-orders-and-orderlines"></a>Filtrar pedidos de empresas vinculadas para evitar sincronizar pedidos y líneas de pedido

[!include [banner](../../includes/banner.md)]

Puede filtrar pedidos de empresas vinculadas para evitar sincronizar las entidades **Orders** y **OrderLines**. En algunos escenarios, los detalles del pedido de empresas vinculadas no son necesarios en la aplicación de interacción con el cliente.

Cada una de las entidades estándar de Common Data Service se amplía con referencias al campo **IntercompanyOrder**, y los mapas de escritura dual se modifican para hacer referencia a los campos adicionales en los filtros. El resultado es que los pedidos de empresas vinculadas ya no están sincronizados. Este proceso evita datos innecesarios en la aplicación de Customer Engagement.

1. Agregar una referencia a **IntercompanyOrder** a **Encabezados de órdenes de venta de CDS**. Se rellena solo en pedidos de empresas vinculadas. El campo **IntercompanyOrder** está disponible en **SalesTable**.

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Asignar la preparación al destino, SalesOrderHeader":::
    
2. Después de extender **Encabezados de órdenes de venta de CDS**, el campo **IntercompanyOrder** está disponible en la asignación. Aplicar un filtro con `INTERCOMPANYORDER == ""` como la cadena de consulta.

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="Encabezados de pedidos de venta, editar consulta":::

3. Agregar una referencia a **IntercompanyInventTransId** a **Líneas de pedidos de venta de CDS**.  Se rellena solo en pedidos de empresas vinculadas. El campo **InterCompanyInventTransID** está disponible en **SalesLine**.

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Asignar la preparación al destino, SalesOrderLine":::

4. Después de extender **Líneas de pedidos de venta de CDS**, el campo **IntercompanyInventTransId** está disponible en la asignación. Aplicar un filtro con `INTERCOMPANYINVENTTRANSID == ""` como la cadena de consulta.

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Líneas de pedido de ventas, editar consulta":::

5. Extienda **Encabezado de factura de ventas V2** y **Líneas de factura de venta V2** de la misma manera que extendió las entidades Common Data Service en los pasos 1 y 2. Luego agregue las consultas de filtro. La cadena de filtro para **Encabezado de factura de ventas V2** es `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")`. La cadena de filtro para **Líneas de factura de ventas V2** es `INTERCOMPANYINVENTTRANSID == ""`.

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Asignar la preparación al destino, Encabezados de factura de ventas":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="Encabezados de factura de venta, editar consulta":::

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Líneas de factura de venta, editar consulta":::

6. La entidad **Presupuestos** no tiene una relación entre empresas. Si alguien crea una cotización para uno de sus clientes de empresas vinculadas, puede poner a todos estos clientes en un grupo de clientes mediante el campo **CustGroup**.  El encabezado y las líneas se pueden extender para agregar el campo **CustGroup** y luego filtrar para no incluir este grupo.

    :::image type="content" source="media/filter-cust-group.png" alt-text="Asignar la preparación al destino, Encabezados de presupuesto de ventas":::

7. Después de extender la entidad **Presupuestos**, aplique un filtro con `CUSTGROUP !=  "<company>"` como la cadena de consulta.

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="Encabezado de presupuesto de ventas, editar consulta":::


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]