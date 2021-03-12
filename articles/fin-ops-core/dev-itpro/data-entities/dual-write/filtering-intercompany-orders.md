---
title: Filtrar pedidos de empresas vinculadas para evitar la sincronización de Orders y OrderLines
description: Este tema explica cómo filtrar los pedidos de empresas vinculadas para que las entidades Orders y OrderLines no estén sincronizadas.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: negudava
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 342db8c1b4337145bfd61f5698ff6de25434a400
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "4796615"
---
# <a name="filter-intercompany-orders-to-avoid-syncing-orders-and-orderlines"></a>Filtrar pedidos de empresas vinculadas para evitar la sincronización de Orders y OrderLines

[!include [banner](../../includes/banner.md)]

Puede filtrar pedidos de empresas vinculadas para evitar sincronizar las tablas **Orders** y **OrderLines**. En algunos escenarios, los detalles del pedido de empresas vinculadas no son necesarios en una aplicación de interacción con el cliente.

Cada una de las tablas estándar de Dataverse se amplía mediante referencias a la columna **IntercompanyOrder**, y los mapas de escritura dual se modifican para que hagan referencia a las columnas adicionales en los filtros. Por lo tanto, los pedidos de empresas vinculadas ya no se sincronizan. Este proceso ayuda a evitar datos innecesarios en la aplicación de interacción con el cliente.

1. Extienda la tabla **Encabezados de pedidos de venta de CDS** agregando una referencia a la columna **IntercompanyOrder**. Esta columna se completa solo en pedidos de empresas vinculadas. La columna **IntercompanyOrder** está disponible en la tabla **SalesTable**.

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Asignar la preparación a la página de destino para los encabezados de pedidos de venta de CDS":::

2. Después de extender **Encabezados de pedidos de venta de CDS**, la columna **IntercompanyOrder** está disponible en la asignación. Aplicar un filtro que tenga `INTERCOMPANYORDER == ""` como la cadena de consulta.

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="Cuadro de diálogo Editar consulta para encabezados de pedidos de venta de CDS":::

3. Extienda la tabla **Líneas de pedidos de venta de CDS** agregando una referencia a la columna **IntercompanyInventTransId**. Esta columna se completa solo en pedidos de empresas vinculadas. La columna **InterCompanyInventTransId** está disponible en la tabla **SalesLine**.

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Asignar la preparación a la página de destino para las líneas de pedidos de venta de CDS":::

4. Después de extender **Líneas de pedidos de venta de CDS**, la columna **IntercompanyInventTransId** está disponible en la asignación. Aplicar un filtro que tenga `INTERCOMPANYINVENTTRANSID == ""` como la cadena de consulta.

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Cuadro de diálogo Editar consulta para líneas de pedidos de venta de CDS":::

5. Repita los pasos 1 y 2 para extender la tabla **Encabezado de factura de ventas V2** y agregue una consulta de filtro. En este caso, utilice `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")` como la cadena de consulta para el filtro.

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Asignar la preparación a la página de destino para los encabezados de facturas de ventas V2":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="Cuadro de diálogo Editar consulta para encabezados de pedidos de ventas V2":::

6. Repita los pasos 3 y 4 para extender la tabla **Líneas de factura de ventas V2** y agregue una consulta de filtro. En este caso, utilice `INTERCOMPANYINVENTTRANSID == ""` como la cadena de consulta para el filtro.

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Cuadro de diálogo Editar consulta para líneas de pedidos de ventas V2":::

7. La tabla **Presupuestos** no tiene una relación entre empresas vinculadas. Si alguien crea un presupuesto para uno de sus clientes de empresas vinculadas, puede usar la columna **CustGroup** para colocar a todos esos clientes en un solo grupo de clientes. Puede extender el encabezado y las líneas agregando la columna **CustGroup** y luego filtre para que el grupo no se incluya.

    :::image type="content" source="media/filter-cust-group.png" alt-text="Asignar la preparación a la página de destino para los encabezados de presupuestos de ventas de CDS":::

8. Después de extender **Presupuestos**, aplique un filtro que tenga `CUSTGROUP != "<company>"` como cadena de consulta.

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="Cuadro de diálogo Editar consulta para encabezados de presupuestos de ventas de CDS":::