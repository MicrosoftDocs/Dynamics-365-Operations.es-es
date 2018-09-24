---
title: "Contenido de Power BI sobre análisis de gastos de compra"
description: "Este tema describe lo que se incluye en el contenido de Power BI acerca de análisis de compras y gastos. Explica cómo tener acceso a los informes que se incluyen en el contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido."
author: FrankDahl
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: PurchaseSpendAnalysisPowerBI
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 821d8927211d7ac3e479848c7e7bef9f650d4340
ms.openlocfilehash: 069c4dc21959ab603ba6ca3da0ac68ef20325265
ms.contentlocale: es-es
ms.lasthandoff: 08/13/2018

---

# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="d9a2a-104">Contenido de Power BI sobre análisis de gastos de compra</span><span class="sxs-lookup"><span data-stu-id="d9a2a-104">Purchase spend analysis Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d9a2a-105">Este tema describe lo que se incluye en el contenido de Microsoft Power BI acerca de **Análisis de compras y gastos**.</span><span class="sxs-lookup"><span data-stu-id="d9a2a-105">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="d9a2a-106">Explica cómo obtener acceso a los informes de Power BI y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.</span><span class="sxs-lookup"><span data-stu-id="d9a2a-106">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="d9a2a-107">Información general</span><span class="sxs-lookup"><span data-stu-id="d9a2a-107">Overview</span></span>

<span data-ttu-id="d9a2a-108">El contenido de Power BI sobre **Análisis de compras y gastos** se ha diseñado para ayudar a directores de compras y los administradores responsables de presupuestos a vigilar los gastos en adquisiciones.</span><span class="sxs-lookup"><span data-stu-id="d9a2a-108">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep an eye on purchase spending.</span></span> <span data-ttu-id="d9a2a-109">Los directores pueden analizar su gasto en adquisiciones de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="d9a2a-109">Managers can analyze purchase spending in the following ways:</span></span>

- <span data-ttu-id="d9a2a-110">Compras hasta la fecha (por grupo de proveedores y proveedores individuales, productos de la categoría de compras e individuales y ubicación del proveedor)</span><span class="sxs-lookup"><span data-stu-id="d9a2a-110">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
- <span data-ttu-id="d9a2a-111">Cambio de las compras año por año (por grupo de proveedores y categoría de compras)</span><span class="sxs-lookup"><span data-stu-id="d9a2a-111">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="d9a2a-112">El contenido usa datos transaccionales de compras y proporciona tanto una visión global de las cifras de compras en la empresa como un desglose de los gastos en compras por proveedor y producto.</span><span class="sxs-lookup"><span data-stu-id="d9a2a-112">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="d9a2a-113">Los informes resaltan cambios en los gastos de compra a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="d9a2a-113">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="d9a2a-114">Por lo tanto, los informes se pueden usar para notificar a los administradores las tendencias positivas y negativas de los gastos relativas a proveedores y productos individuales.</span><span class="sxs-lookup"><span data-stu-id="d9a2a-114">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="d9a2a-115">Además, los gráficos muestran los gastos de compra para las diversas categorías de compras y grupos de proveedores.</span><span class="sxs-lookup"><span data-stu-id="d9a2a-115">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="d9a2a-116">Por lo tanto, los administradores de categorías y regionales pueden utilizar los gráficos como ayuda para identificar los cambios en comportamiento del gasto.</span><span class="sxs-lookup"><span data-stu-id="d9a2a-116">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="d9a2a-117">Acceso al contenido de Power BI</span><span class="sxs-lookup"><span data-stu-id="d9a2a-117">Accessing the Power BI content</span></span>
<span data-ttu-id="d9a2a-118">El contenido de Power BI **Análisis de compras y gastos** se muestra en la página **Análisis de compras y gastos** (**Adquisición y abastecimiento** \> **Consultas e informes** \> **Análisis del rendimiento de compra** \> **Análisis de compras y gastos**).</span><span class="sxs-lookup"><span data-stu-id="d9a2a-118">The **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** \> **Inquiries and reports** \> **Purchase performance analysis** \> **Purchase and spend analysis**).</span></span>

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="d9a2a-119">Métricas que se incluyen en el contenido de Power BI</span><span class="sxs-lookup"><span data-stu-id="d9a2a-119">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="d9a2a-120">El contenido de Power BI sobre **Análisis de compras y gastos** incluye un informe compuesto por un conjunto de métricas.</span><span class="sxs-lookup"><span data-stu-id="d9a2a-120">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="d9a2a-121">Estas métricas se visualizan como gráficos, mosaicos y tablas.</span><span class="sxs-lookup"><span data-stu-id="d9a2a-121">These metrics are visualized as charts, tiles, and tables.</span></span> <span data-ttu-id="d9a2a-122">La tabla siguiente muestra una visión general de las visualizaciones.</span><span class="sxs-lookup"><span data-stu-id="d9a2a-122">The following table provides an overview of the visualizations.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d9a2a-123">Página de informes</span><span class="sxs-lookup"><span data-stu-id="d9a2a-123">Report page</span></span></th>
<th><span data-ttu-id="d9a2a-124">Gráficos</span><span class="sxs-lookup"><span data-stu-id="d9a2a-124">Charts</span></span></th>
<th><span data-ttu-id="d9a2a-125">Mosaicos</span><span class="sxs-lookup"><span data-stu-id="d9a2a-125">Tiles</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d9a2a-126">Compras por proveedor</span><span class="sxs-lookup"><span data-stu-id="d9a2a-126">Purchase by vendor</span></span></td>
<td><ul>
<li><span data-ttu-id="d9a2a-127">Los 10 principales proveedores por compra (gráfico de barras apiladas)</span><span class="sxs-lookup"><span data-stu-id="d9a2a-127">Top 10 vendors by purchase (stacked bar chart)</span></span></li>
<li><span data-ttu-id="d9a2a-128">Compras totales por grupo de proveedores/país/nombre (gráfico circular)</span><span class="sxs-lookup"><span data-stu-id="d9a2a-128">Total purchase by vendor group / country / name (pie chart)</span></span></li>
<li><span data-ttu-id="d9a2a-129">Compras por grupo de proveedores/país/nombre (gráfico de columnas)</span><span class="sxs-lookup"><span data-stu-id="d9a2a-129">Purchase by vendor group / country / name (column chart)</span></span></li>
<li><span data-ttu-id="d9a2a-130">Promedio de compras por grupo de proveedores/país/nombre (gráfico de columnas)</span><span class="sxs-lookup"><span data-stu-id="d9a2a-130">Average purchase by vendor group / country / name (column chart)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="d9a2a-131">Total de la compra</span><span class="sxs-lookup"><span data-stu-id="d9a2a-131">Total purchase</span></span></li>
<li><span data-ttu-id="d9a2a-132">Crecimiento de compras interanual</span><span class="sxs-lookup"><span data-stu-id="d9a2a-132">YOY purchase growth</span></span></li>
<li><span data-ttu-id="d9a2a-133">N.º total de proveedores</span><span class="sxs-lookup"><span data-stu-id="d9a2a-133">Total # vendors</span></span></li>
<li><span data-ttu-id="d9a2a-134">N.º total de proveedores activos</span><span class="sxs-lookup"><span data-stu-id="d9a2a-134">Total # of active vendors</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="d9a2a-135">Compras por producto</span><span class="sxs-lookup"><span data-stu-id="d9a2a-135">Purchase by product</span></span></td>
<td><ul>
<li><span data-ttu-id="d9a2a-136">Compras por categoría de compras o nombre del producto (gráfico de columnas)</span><span class="sxs-lookup"><span data-stu-id="d9a2a-136">Purchase by procurement category / product name (column chart)</span></span></li>
<li><span data-ttu-id="d9a2a-137">Compra total por categoría de compras o nombre del producto (gráfico circular)</span><span class="sxs-lookup"><span data-stu-id="d9a2a-137">Total purchase by procurement category / product name (pie chart)</span></span></li>
<li><span data-ttu-id="d9a2a-138">Los 10 principales productos por compra (gráfico de barras apiladas)</span><span class="sxs-lookup"><span data-stu-id="d9a2a-138">Top 10 products by purchase (stacked bar chart)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="d9a2a-139">N.º total de productos</span><span class="sxs-lookup"><span data-stu-id="d9a2a-139">Total # of products</span></span></li>
<li><span data-ttu-id="d9a2a-140">Porcentaje total de productos activos de n.º total de productos</span><span class="sxs-lookup"><span data-stu-id="d9a2a-140">Total active products percentage of total # of products</span></span></li>
<li><span data-ttu-id="d9a2a-141">Número de productos que representan el 80 % de la compra</span><span class="sxs-lookup"><span data-stu-id="d9a2a-141">Number of products accounting for 80% purchase</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="d9a2a-142">Compras por período\*</span><span class="sxs-lookup"><span data-stu-id="d9a2a-142">Purchase by period\*</span></span></td>
<td><ul>
<li><span data-ttu-id="d9a2a-143">Compras por mes/día (gráfico de columnas)</span><span class="sxs-lookup"><span data-stu-id="d9a2a-143">Purchase by month / day (column chart)</span></span></li>
<li><span data-ttu-id="d9a2a-144">Desviación interanual de compras acumuladas (gráfico de cascada)</span><span class="sxs-lookup"><span data-stu-id="d9a2a-144">Cumulative purchase YOY variance (waterfall chart)</span></span></li>
<li><span data-ttu-id="d9a2a-145">Crecimiento total de la compra interanual (gráfico de columnas)</span><span class="sxs-lookup"><span data-stu-id="d9a2a-145">Total purchase YOY growth (column chart)</span></span></li>
<li><span data-ttu-id="d9a2a-146">Extracto de compras (matriz)</span><span class="sxs-lookup"><span data-stu-id="d9a2a-146">Procurement statement (matrix)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="d9a2a-147">Crecimiento de compras interanual</span><span class="sxs-lookup"><span data-stu-id="d9a2a-147">YOY purchase growth</span></span></li>
<li><span data-ttu-id="d9a2a-148">% de crecimiento de compras interanual</span><span class="sxs-lookup"><span data-stu-id="d9a2a-148">YOY purchase growth %</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="d9a2a-149">Compras por ubicación de proveedor</span><span class="sxs-lookup"><span data-stu-id="d9a2a-149">Purchase by vendor location</span></span></td>
<td><ul>
<li><span data-ttu-id="d9a2a-150">Compras por ciudad</span><span class="sxs-lookup"><span data-stu-id="d9a2a-150">Purchase by city</span></span></li>
<li><span data-ttu-id="d9a2a-151">% de crecimiento de compras interanual</span><span class="sxs-lookup"><span data-stu-id="d9a2a-151">Purchase YOY growth %</span></span></li>
<li><span data-ttu-id="d9a2a-152">Compras por país</span><span class="sxs-lookup"><span data-stu-id="d9a2a-152">Purchase by country</span></span></li>
</ul></td>
<td></td>
</tr>
<tr>
<td><span data-ttu-id="d9a2a-153">Análisis de gasto de compras por hora</span><span class="sxs-lookup"><span data-stu-id="d9a2a-153">Purchase spend analysis by time</span></span></td>
<td><ul>
<li><span data-ttu-id="d9a2a-154">Compras de año actual por mes/día (gráfico de líneas)</span><span class="sxs-lookup"><span data-stu-id="d9a2a-154">Purchase current year by month / day (line chart)</span></span></li>
<li><span data-ttu-id="d9a2a-155">Compras este año y el año anterior (gráficos de líneas y columnas)</span><span class="sxs-lookup"><span data-stu-id="d9a2a-155">Purchase current and last year (line and column chart)</span></span></li>
</ul></td>
<td></td>
</tr>
<tr>
<td><span data-ttu-id="d9a2a-156">Análisis de gasto de compras por proveedor</span><span class="sxs-lookup"><span data-stu-id="d9a2a-156">Purchase spend analysis by vendor</span></span></td>
<td><ul>
<li><span data-ttu-id="d9a2a-157">% de compras de los 10 principales proveedores sobre el total de compras (embudo)</span><span class="sxs-lookup"><span data-stu-id="d9a2a-157">Top 10 vendor purchase % of purchase (funnel)</span></span></li>
<li><span data-ttu-id="d9a2a-158">10 principales proveedores con aumento de gastos interanual</span><span class="sxs-lookup"><span data-stu-id="d9a2a-158">Top 10 vendors with increased spending YOY</span></span></li>
<li><span data-ttu-id="d9a2a-159">10 principales proveedores con disminución de gastos interanual</span><span class="sxs-lookup"><span data-stu-id="d9a2a-159">Top 10 vendors with decreased spending YOY</span></span></li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d9a2a-160">\* Compras este año y el año anterior, y crecimiento por categoría de compras</span><span class="sxs-lookup"><span data-stu-id="d9a2a-160">\* Purchase this year and last year, and growth by procurement category</span></span>

## <a name="data-model-and-entities"></a><span data-ttu-id="d9a2a-161">Modelo de datos y entidades</span><span class="sxs-lookup"><span data-stu-id="d9a2a-161">Data model and entities</span></span>
<span data-ttu-id="d9a2a-162">Los datos siguientes se usan para rellenar las páginas de informes en el contenido de Power BI sobre **Análisis de compras y gastos**.</span><span class="sxs-lookup"><span data-stu-id="d9a2a-162">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="d9a2a-163">Estos datos se representan como medidas agregadas que se realizan en el almacén de la entidad.</span><span class="sxs-lookup"><span data-stu-id="d9a2a-163">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="d9a2a-164">El almacén de la entidad es una base de datos de Microsoft SQL Server que se optimiza para el análisis.</span><span class="sxs-lookup"><span data-stu-id="d9a2a-164">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="d9a2a-165">Para obtener más información, consulte [Visión general de la integración de Power BI con el almacén de entidades](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="d9a2a-165">For more information, see [Overview of Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="d9a2a-166">Las medidas agregadas en este contenido son el subconjunto de las medidas agregadas que estaban disponibles en el cubo de compra en Microsoft Dynamics AX 2012 y Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="d9a2a-166">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="d9a2a-167">Para realizar las medidas globales del cubo en el almacén de entidades debe hacer que sean desplegables.</span><span class="sxs-lookup"><span data-stu-id="d9a2a-167">To stage the cube's aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="d9a2a-168">Para obtener más información, consulte el procedimiento relativo a cómo realizar mediciones globales en el almacén de entidades en [Visión general de la integración de Power BI con el almacén de entidades](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="d9a2a-168">For more information, see the procedure for staging aggregate measurements in the Entity store in [Overview of Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="d9a2a-169">Las siguientes medidas agregadas clave están directamente disponibles en la entidad de líneas de factura y se usan como base del contenido.</span><span class="sxs-lookup"><span data-stu-id="d9a2a-169">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="d9a2a-170">Entidad</span><span class="sxs-lookup"><span data-stu-id="d9a2a-170">Entity</span></span>        | <span data-ttu-id="d9a2a-171">Medidas agregadas clave</span><span class="sxs-lookup"><span data-stu-id="d9a2a-171">Key aggregate measurements</span></span> | <span data-ttu-id="d9a2a-172">Origen de datos</span><span class="sxs-lookup"><span data-stu-id="d9a2a-172">Data source</span></span>                                 | <span data-ttu-id="d9a2a-173">Campo</span><span class="sxs-lookup"><span data-stu-id="d9a2a-173">Field</span></span>              | <span data-ttu-id="d9a2a-174">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9a2a-174">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="d9a2a-175">Líneas de factura</span><span class="sxs-lookup"><span data-stu-id="d9a2a-175">Invoice lines</span></span> | <span data-ttu-id="d9a2a-176">Compra</span><span class="sxs-lookup"><span data-stu-id="d9a2a-176">Purchase</span></span>                   | <span data-ttu-id="d9a2a-177">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="d9a2a-177">VendInvoiceTrans</span></span>                            | <span data-ttu-id="d9a2a-178">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="d9a2a-178">SUM(LineAmountMST)</span></span> | <span data-ttu-id="d9a2a-179">El importe en la divisa de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="d9a2a-179">The amount in the accounting currency.</span></span> |

<span data-ttu-id="d9a2a-180">En la tabla siguiente se muestran las medidas clave del contenido que se calculan a partir de la entidad de las líneas de factura.</span><span class="sxs-lookup"><span data-stu-id="d9a2a-180">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="d9a2a-181">Medida</span><span class="sxs-lookup"><span data-stu-id="d9a2a-181">Measure</span></span>               | <span data-ttu-id="d9a2a-182">Cálculo</span><span class="sxs-lookup"><span data-stu-id="d9a2a-182">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="d9a2a-183">Año actual de compra</span><span class="sxs-lookup"><span data-stu-id="d9a2a-183">Purchase current year</span></span> | <span data-ttu-id="d9a2a-184">Año actual de compra = SUM('Líneas de factura'\[Compra\])</span><span class="sxs-lookup"><span data-stu-id="d9a2a-184">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="d9a2a-185">Compra el año pasado</span><span class="sxs-lookup"><span data-stu-id="d9a2a-185">Purchase last year</span></span>    | <span data-ttu-id="d9a2a-186">Compra el año pasado = CALCULATE(SUM('Líneas factura'\[Compra\]), SAMEPERIODLASTYEAR(Fechas\[Fecha\])</span><span class="sxs-lookup"><span data-stu-id="d9a2a-186">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="d9a2a-187">Crecimiento de compras interanual</span><span class="sxs-lookup"><span data-stu-id="d9a2a-187">YOY purchase growth</span></span>   | <span data-ttu-id="d9a2a-188">Crecimiento de compras interanual = \[Compra año actual\] – \[Compra el año pasado\]</span><span class="sxs-lookup"><span data-stu-id="d9a2a-188">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="d9a2a-189">Las dimensiones clave siguientes del contenido se utilizan como filtros para cortar las medidas globales para lograr mayor granularidad y profundizar en la visión analítica.</span><span class="sxs-lookup"><span data-stu-id="d9a2a-189">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="d9a2a-190">Entidad</span><span class="sxs-lookup"><span data-stu-id="d9a2a-190">Entity</span></span>                 | <span data-ttu-id="d9a2a-191">Ejemplos de atributos</span><span class="sxs-lookup"><span data-stu-id="d9a2a-191">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="d9a2a-192">Empresas proveedoras</span><span class="sxs-lookup"><span data-stu-id="d9a2a-192">Vendors</span></span>                | <span data-ttu-id="d9a2a-193">Grupos de proveedores, países o regiones de proveedores, nombre del proveedor</span><span class="sxs-lookup"><span data-stu-id="d9a2a-193">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="d9a2a-194">Productos</span><span class="sxs-lookup"><span data-stu-id="d9a2a-194">Products</span></span>               | <span data-ttu-id="d9a2a-195">Número de producto, nombre de producto, nombre de grupos de artículos</span><span class="sxs-lookup"><span data-stu-id="d9a2a-195">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="d9a2a-196">Categorías de adquisición</span><span class="sxs-lookup"><span data-stu-id="d9a2a-196">Procurement categories</span></span> | <span data-ttu-id="d9a2a-197">Categoría de compras, nombres de la categoría de compras</span><span class="sxs-lookup"><span data-stu-id="d9a2a-197">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="d9a2a-198">Entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="d9a2a-198">Legal entities</span></span>         | <span data-ttu-id="d9a2a-199">Nombre de la entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="d9a2a-199">Legal entity name</span></span>                                     |
| <span data-ttu-id="d9a2a-200">Fechas</span><span class="sxs-lookup"><span data-stu-id="d9a2a-200">Dates</span></span>                  | <span data-ttu-id="d9a2a-201">Fechas, contrapartida anual</span><span class="sxs-lookup"><span data-stu-id="d9a2a-201">Dates, Year offset</span></span>                                    |

<span data-ttu-id="d9a2a-202">De forma predeterminada, el contenido muestra los datos del año natural actual.</span><span class="sxs-lookup"><span data-stu-id="d9a2a-202">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="d9a2a-203">Sin embargo, puede cambiar el filtro de la fecha en la sección de filtros de informe.</span><span class="sxs-lookup"><span data-stu-id="d9a2a-203">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="d9a2a-204">También puede cambiar el filtro de empresa.</span><span class="sxs-lookup"><span data-stu-id="d9a2a-204">You can also change the company filter.</span></span>

