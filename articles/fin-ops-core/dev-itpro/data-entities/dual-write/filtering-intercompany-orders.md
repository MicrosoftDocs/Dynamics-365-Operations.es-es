---
title: Filtrar pedidos de empresas vinculadas para evitar la sincronización de Orders y OrderLines
description: Este tema explica cómo filtrar los pedidos de empresas vinculadas para que las entidades Orders y OrderLines no estén sincronizadas.
author: negudava
ms.date: 11/09/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 123427db61782490d348489c23e0eaf5f8b513c9
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748650"
---
# <a name="filter-intercompany-orders-to-avoid-syncing-orders-and-orderlines"></a><span data-ttu-id="3792c-103">Filtrar pedidos de empresas vinculadas para evitar la sincronización de Orders y OrderLines</span><span class="sxs-lookup"><span data-stu-id="3792c-103">Filter intercompany orders to avoid syncing Orders and OrderLines</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3792c-104">Puede filtrar pedidos de empresas vinculadas para evitar sincronizar las tablas **Orders** y **OrderLines**.</span><span class="sxs-lookup"><span data-stu-id="3792c-104">You can filter intercompany orders so that the **Orders** and **OrderLines** tables aren't synced.</span></span> <span data-ttu-id="3792c-105">En algunos escenarios, los detalles del pedido de empresas vinculadas no son necesarios en una aplicación de interacción con el cliente.</span><span class="sxs-lookup"><span data-stu-id="3792c-105">In some scenarios, the intercompany order details aren't required in a customer engagement app.</span></span>

<span data-ttu-id="3792c-106">Cada una de las tablas estándar de Dataverse se amplía mediante referencias a la columna **IntercompanyOrder**, y los mapas de escritura dual se modifican para que hagan referencia a las columnas adicionales en los filtros.</span><span class="sxs-lookup"><span data-stu-id="3792c-106">Each standard Dataverse table is extended through references to the **IntercompanyOrder** column, and the dual-write maps are modified so that they refer to the additional columns in the filters.</span></span> <span data-ttu-id="3792c-107">Por lo tanto, los pedidos de empresas vinculadas ya no se sincronizan.</span><span class="sxs-lookup"><span data-stu-id="3792c-107">Therefore, the intercompany orders are no longer synced.</span></span> <span data-ttu-id="3792c-108">Este proceso ayuda a evitar datos innecesarios en la aplicación de interacción con el cliente.</span><span class="sxs-lookup"><span data-stu-id="3792c-108">This process helps prevent unnecessary data in the customer engagement app.</span></span>

1. <span data-ttu-id="3792c-109">Extienda la tabla **Encabezados de pedidos de venta de CDS** agregando una referencia a la columna **IntercompanyOrder**.</span><span class="sxs-lookup"><span data-stu-id="3792c-109">Extend the **CDS Sales Order Headers** table by adding a reference to the **IntercompanyOrder** column.</span></span> <span data-ttu-id="3792c-110">Esta columna se completa solo en pedidos de empresas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="3792c-110">This column is filled in only on intercompany orders.</span></span> <span data-ttu-id="3792c-111">La columna **IntercompanyOrder** está disponible en la tabla **SalesTable**.</span><span class="sxs-lookup"><span data-stu-id="3792c-111">The **IntercompanyOrder** column is available in the **SalesTable** table.</span></span>

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Asignar la preparación a la página de destino para los encabezados de pedidos de venta de CDS":::

2. <span data-ttu-id="3792c-113">Después de extender **Encabezados de pedidos de venta de CDS**, la columna **IntercompanyOrder** está disponible en la asignación.</span><span class="sxs-lookup"><span data-stu-id="3792c-113">After **CDS Sales Order Headers** is extended, the **IntercompanyOrder** column is available in the mapping.</span></span> <span data-ttu-id="3792c-114">Aplicar un filtro que tenga `INTERCOMPANYORDER == ""` como la cadena de consulta.</span><span class="sxs-lookup"><span data-stu-id="3792c-114">Apply a filter that has `INTERCOMPANYORDER == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="Cuadro de diálogo Editar consulta para encabezados de pedidos de venta de CDS":::

3. <span data-ttu-id="3792c-116">Extienda la tabla **Líneas de pedidos de venta de CDS** agregando una referencia a la columna **IntercompanyInventTransId**.</span><span class="sxs-lookup"><span data-stu-id="3792c-116">Extend the **CDS Sales Order Lines** table by adding a reference to the **IntercompanyInventTransId** column.</span></span> <span data-ttu-id="3792c-117">Esta columna se completa solo en pedidos de empresas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="3792c-117">This column is filled in only on intercompany orders.</span></span> <span data-ttu-id="3792c-118">La columna **InterCompanyInventTransId** está disponible en la tabla **SalesLine**.</span><span class="sxs-lookup"><span data-stu-id="3792c-118">The **InterCompanyInventTransId** column is available in the **SalesLine** table.</span></span>

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Asignar la preparación a la página de destino para las líneas de pedidos de venta de CDS":::

4. <span data-ttu-id="3792c-120">Después de extender **Líneas de pedidos de venta de CDS**, la columna **IntercompanyInventTransId** está disponible en la asignación.</span><span class="sxs-lookup"><span data-stu-id="3792c-120">After **CDS Sales Order Lines** is extended, the **IntercompanyInventTransId** column is available in the mapping.</span></span> <span data-ttu-id="3792c-121">Aplicar un filtro que tenga `INTERCOMPANYINVENTTRANSID == ""` como la cadena de consulta.</span><span class="sxs-lookup"><span data-stu-id="3792c-121">Apply a filter that has `INTERCOMPANYINVENTTRANSID == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Cuadro de diálogo Editar consulta para líneas de pedidos de venta de CDS":::

5. <span data-ttu-id="3792c-123">Repita los pasos 1 y 2 para extender la tabla **Encabezado de factura de ventas V2** y agregue una consulta de filtro.</span><span class="sxs-lookup"><span data-stu-id="3792c-123">Repeat steps 1 and 2 to extend the **Sales Invoice Header V2** table and add a filter query.</span></span> <span data-ttu-id="3792c-124">En este caso, utilice `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")` como la cadena de consulta para el filtro.</span><span class="sxs-lookup"><span data-stu-id="3792c-124">In this case, use `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")` as the query string for the filter.</span></span>

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Asignar la preparación a la página de destino para los encabezados de facturas de ventas V2":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="Cuadro de diálogo Editar consulta para encabezados de pedidos de ventas V2":::

6. <span data-ttu-id="3792c-127">Repita los pasos 3 y 4 para extender la tabla **Líneas de factura de ventas V2** y agregue una consulta de filtro.</span><span class="sxs-lookup"><span data-stu-id="3792c-127">Repeat steps 3 and 4 to extend the **Sales Invoice Lines V2** table and add a filter query.</span></span> <span data-ttu-id="3792c-128">En este caso, utilice `INTERCOMPANYINVENTTRANSID == ""` como la cadena de consulta para el filtro.</span><span class="sxs-lookup"><span data-stu-id="3792c-128">In this case, use `INTERCOMPANYINVENTTRANSID == ""` as the query string for the filter.</span></span>

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Cuadro de diálogo Editar consulta para líneas de pedidos de ventas V2":::

7. <span data-ttu-id="3792c-130">La tabla **Presupuestos** no tiene una relación entre empresas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="3792c-130">The **Quotations** table doesn't have an intercompany relationship.</span></span> <span data-ttu-id="3792c-131">Si alguien crea un presupuesto para uno de sus clientes de empresas vinculadas, puede usar la columna **CustGroup** para colocar a todos esos clientes en un solo grupo de clientes.</span><span class="sxs-lookup"><span data-stu-id="3792c-131">If someone creates a quotation for one of your intercompany customers, you can use the **CustGroup** column to put all those customers into one customer group.</span></span> <span data-ttu-id="3792c-132">Puede extender el encabezado y las líneas agregando la columna **CustGroup** y luego filtre para que el grupo no se incluya.</span><span class="sxs-lookup"><span data-stu-id="3792c-132">You can extend the header and lines by adding the **CustGroup** column, and then filter so that the group isn't included.</span></span>

    :::image type="content" source="media/filter-cust-group.png" alt-text="Asignar la preparación a la página de destino para los encabezados de presupuestos de ventas de CDS":::

8. <span data-ttu-id="3792c-134">Después de extender **Presupuestos**, aplique un filtro que tenga `CUSTGROUP != "<company>"` como cadena de consulta.</span><span class="sxs-lookup"><span data-stu-id="3792c-134">After **Quotations** is extended, apply a filter that has `CUSTGROUP != "<company>"` as the query string.</span></span>

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="Cuadro de diálogo Editar consulta para encabezados de presupuestos de ventas de CDS":::


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]