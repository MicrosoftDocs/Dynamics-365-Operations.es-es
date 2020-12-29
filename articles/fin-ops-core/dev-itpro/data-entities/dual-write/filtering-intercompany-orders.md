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
# <a name="filter-intercompany-orders-to-avoid-synchronizing-orders-and-orderlines"></a><span data-ttu-id="72f87-103">Filtrar pedidos de empresas vinculadas para evitar sincronizar pedidos y líneas de pedido</span><span class="sxs-lookup"><span data-stu-id="72f87-103">Filter intercompany orders to avoid synchronizing Orders and OrderLines</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="72f87-104">Puede filtrar pedidos de empresas vinculadas para evitar sincronizar las entidades **Orders** y **OrderLines**.</span><span class="sxs-lookup"><span data-stu-id="72f87-104">You can filter intercompany orders to avoid synchronizing the **Orders** and **OrderLines** entities.</span></span> <span data-ttu-id="72f87-105">En algunos escenarios, los detalles del pedido de empresas vinculadas no son necesarios en la aplicación de interacción con el cliente.</span><span class="sxs-lookup"><span data-stu-id="72f87-105">In some scenarios, the intercompany order details are not necessary in customer engagement app.</span></span>

<span data-ttu-id="72f87-106">Cada una de las entidades estándar de Common Data Service se amplía con referencias al campo **IntercompanyOrder**, y los mapas de escritura dual se modifican para hacer referencia a los campos adicionales en los filtros.</span><span class="sxs-lookup"><span data-stu-id="72f87-106">Each of the standard Common Data Service entities is extended with references to the **IntercompanyOrder** field, and the dual-write maps are modified to refer to the additional fields in the filters.</span></span> <span data-ttu-id="72f87-107">El resultado es que los pedidos de empresas vinculadas ya no están sincronizados.</span><span class="sxs-lookup"><span data-stu-id="72f87-107">The result is that the intercompany orders are no longer synchronized.</span></span> <span data-ttu-id="72f87-108">Este proceso evita datos innecesarios en la aplicación de Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="72f87-108">This process avoids unnecessary data in the customer engagement app.</span></span>

1. <span data-ttu-id="72f87-109">Agregar una referencia a **IntercompanyOrder** a **Encabezados de órdenes de venta de CDS**.</span><span class="sxs-lookup"><span data-stu-id="72f87-109">Add a reference to **IntercompanyOrder** to **CDS Sales Order Headers**.</span></span> <span data-ttu-id="72f87-110">Se rellena solo en pedidos de empresas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="72f87-110">It is populated on only intercompany orders.</span></span> <span data-ttu-id="72f87-111">El campo **IntercompanyOrder** está disponible en **SalesTable**.</span><span class="sxs-lookup"><span data-stu-id="72f87-111">The field **IntercompanyOrder** is available in **SalesTable**.</span></span>

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Asignar la preparación al destino, SalesOrderHeader":::
    
2. <span data-ttu-id="72f87-113">Después de extender **Encabezados de órdenes de venta de CDS**, el campo **IntercompanyOrder** está disponible en la asignación.</span><span class="sxs-lookup"><span data-stu-id="72f87-113">After **CDS Sales Order Headers** is extended, the **IntercompanyOrder** field is available in the mapping.</span></span> <span data-ttu-id="72f87-114">Aplicar un filtro con `INTERCOMPANYORDER == ""` como la cadena de consulta.</span><span class="sxs-lookup"><span data-stu-id="72f87-114">Apply a filter with `INTERCOMPANYORDER == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="Encabezados de pedidos de venta, editar consulta":::

3. <span data-ttu-id="72f87-116">Agregar una referencia a **IntercompanyInventTransId** a **Líneas de pedidos de venta de CDS**.</span><span class="sxs-lookup"><span data-stu-id="72f87-116">Add a reference to **IntercompanyInventTransId** to **CDS Sales Order Lines**.</span></span>  <span data-ttu-id="72f87-117">Se rellena solo en pedidos de empresas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="72f87-117">It is populated on only intercompany orders.</span></span> <span data-ttu-id="72f87-118">El campo **InterCompanyInventTransID** está disponible en **SalesLine**.</span><span class="sxs-lookup"><span data-stu-id="72f87-118">The field **InterCompanyInventTransID** is available in **SalesLine**.</span></span>

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Asignar la preparación al destino, SalesOrderLine":::

4. <span data-ttu-id="72f87-120">Después de extender **Líneas de pedidos de venta de CDS**, el campo **IntercompanyInventTransId** está disponible en la asignación.</span><span class="sxs-lookup"><span data-stu-id="72f87-120">After **CDS Sales Order Lines** is extended, the **IntercompanyInventTransId** field is available in the mapping.</span></span> <span data-ttu-id="72f87-121">Aplicar un filtro con `INTERCOMPANYINVENTTRANSID == ""` como la cadena de consulta.</span><span class="sxs-lookup"><span data-stu-id="72f87-121">Apply a filter with `INTERCOMPANYINVENTTRANSID == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Líneas de pedido de ventas, editar consulta":::

5. <span data-ttu-id="72f87-123">Extienda **Encabezado de factura de ventas V2** y **Líneas de factura de venta V2** de la misma manera que extendió las entidades Common Data Service en los pasos 1 y 2.</span><span class="sxs-lookup"><span data-stu-id="72f87-123">Extend **Sales Invoice Header V2** and **Sales Invoice Lines V2** in the same way you extended the Common Data Service entities in steps 1 and 2.</span></span> <span data-ttu-id="72f87-124">Luego agregue las consultas de filtro.</span><span class="sxs-lookup"><span data-stu-id="72f87-124">Then add the filter queries.</span></span> <span data-ttu-id="72f87-125">La cadena de filtro para **Encabezado de factura de ventas V2** es `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")`.</span><span class="sxs-lookup"><span data-stu-id="72f87-125">The filter string for **Sales Invoice Header V2** is `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")`.</span></span> <span data-ttu-id="72f87-126">La cadena de filtro para **Líneas de factura de ventas V2** es `INTERCOMPANYINVENTTRANSID == ""`.</span><span class="sxs-lookup"><span data-stu-id="72f87-126">The filter string for **Sales Invoice Lines V2** is `INTERCOMPANYINVENTTRANSID == ""`.</span></span>

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Asignar la preparación al destino, Encabezados de factura de ventas":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="Encabezados de factura de venta, editar consulta":::

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Líneas de factura de venta, editar consulta":::

6. <span data-ttu-id="72f87-130">La entidad **Presupuestos** no tiene una relación entre empresas.</span><span class="sxs-lookup"><span data-stu-id="72f87-130">The **Quotations** entity doesn't have an intercompany relationship.</span></span> <span data-ttu-id="72f87-131">Si alguien crea una cotización para uno de sus clientes de empresas vinculadas, puede poner a todos estos clientes en un grupo de clientes mediante el campo **CustGroup**.</span><span class="sxs-lookup"><span data-stu-id="72f87-131">If someone creates a quote for one of your intercompany customers, you can put all of these customers in one customer group by using the **CustGroup** field.</span></span>  <span data-ttu-id="72f87-132">El encabezado y las líneas se pueden extender para agregar el campo **CustGroup** y luego filtrar para no incluir este grupo.</span><span class="sxs-lookup"><span data-stu-id="72f87-132">Header and lines can be extended to add the **CustGroup** field and then filter to not include this group.</span></span>

    :::image type="content" source="media/filter-cust-group.png" alt-text="Asignar la preparación al destino, Encabezados de presupuesto de ventas":::

7. <span data-ttu-id="72f87-134">Después de extender la entidad **Presupuestos**, aplique un filtro con `CUSTGROUP !=  "<company>"` como la cadena de consulta.</span><span class="sxs-lookup"><span data-stu-id="72f87-134">After you extent the **Quotations** entity, apply a filter with `CUSTGROUP !=  "<company>"` as the query string.</span></span>

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="Encabezado de presupuesto de ventas, editar consulta":::
