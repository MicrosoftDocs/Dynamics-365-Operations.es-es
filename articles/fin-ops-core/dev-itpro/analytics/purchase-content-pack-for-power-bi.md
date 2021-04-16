---
title: Contenido de Power BI del análisis de compras y gastos
description: Este tema describe lo que se incluye en el contenido de Power BI acerca de análisis de compras y gastos.
author: FrankDahl
ms.date: 04/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchaseSpendAnalysisPowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f9741b5f30f5e62b9e80000953113377fe016253
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749378"
---
# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="2b3f0-103">Contenido de Power BI del análisis de compras y gastos</span><span class="sxs-lookup"><span data-stu-id="2b3f0-103">Purchase spend analysis Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2b3f0-104">Este tema describe lo que se incluye en el contenido de **Análisis de gastos de compras** de Microsoft Power BI.</span><span class="sxs-lookup"><span data-stu-id="2b3f0-104">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="2b3f0-105">Explica cómo obtener acceso a los informes de Power BI y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.</span><span class="sxs-lookup"><span data-stu-id="2b3f0-105">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="2b3f0-106">Información general</span><span class="sxs-lookup"><span data-stu-id="2b3f0-106">Overview</span></span>

<span data-ttu-id="2b3f0-107">El contenido de Power BI sobre **Análisis de compras y gastos** se ha diseñado para ayudar a directores de compras y los administradores responsables de presupuestos y seguir los gastos en adquisiciones.</span><span class="sxs-lookup"><span data-stu-id="2b3f0-107">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep track of purchase spending.</span></span> <span data-ttu-id="2b3f0-108">Los directores pueden analizar su gasto en adquisiciones de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="2b3f0-108">Managers can analyze purchase spending in the following ways:</span></span>

- <span data-ttu-id="2b3f0-109">Compras hasta la fecha (por grupo de proveedores y proveedores individuales, productos de la categoría de compras e individuales y ubicación del proveedor)</span><span class="sxs-lookup"><span data-stu-id="2b3f0-109">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
- <span data-ttu-id="2b3f0-110">Cambio de las compras año por año (por grupo de proveedores y categoría de compras)</span><span class="sxs-lookup"><span data-stu-id="2b3f0-110">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="2b3f0-111">El contenido usa datos transaccionales de compras y proporciona tanto una visión global de las cifras de compras en la empresa como un desglose de los gastos en compras por proveedor y producto.</span><span class="sxs-lookup"><span data-stu-id="2b3f0-111">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="2b3f0-112">Los informes resaltan cambios en los gastos de compra a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="2b3f0-112">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="2b3f0-113">Por lo tanto, los informes se pueden usar para notificar a los administradores las tendencias positivas y negativas de los gastos relativas a proveedores y productos individuales.</span><span class="sxs-lookup"><span data-stu-id="2b3f0-113">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="2b3f0-114">Además, los gráficos muestran los gastos de compra para las diversas categorías de compras y grupos de proveedores.</span><span class="sxs-lookup"><span data-stu-id="2b3f0-114">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="2b3f0-115">Por lo tanto, los administradores de categorías y regionales pueden utilizar los gráficos como ayuda para identificar los cambios en comportamiento del gasto.</span><span class="sxs-lookup"><span data-stu-id="2b3f0-115">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="2b3f0-116">Acceso al contenido de Power BI</span><span class="sxs-lookup"><span data-stu-id="2b3f0-116">Accessing the Power BI content</span></span>
<span data-ttu-id="2b3f0-117">El contenido de Power BI **Análisis de compras y gastos** se muestra en la página **Análisis de compras y gastos** (**Adquisición y abastecimiento** \> **Consultas e informes** \> **Análisis del rendimiento de compra** \> **Análisis de compras y gastos**).</span><span class="sxs-lookup"><span data-stu-id="2b3f0-117">The **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** \> **Inquiries and reports** \> **Purchase performance analysis** \> **Purchase and spend analysis**).</span></span>

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="2b3f0-118">Métricas que se incluyen en el contenido de Power BI</span><span class="sxs-lookup"><span data-stu-id="2b3f0-118">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="2b3f0-119">El contenido de Power BI de **análisis de los gastos de compra** incluye un informe compuesto por un conjunto de medidas.</span><span class="sxs-lookup"><span data-stu-id="2b3f0-119">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="2b3f0-120">Estas métricas se visualizan como gráficos, mosaicos y tablas.</span><span class="sxs-lookup"><span data-stu-id="2b3f0-120">These metrics are visualized as charts, tiles, and tables.</span></span> 

<span data-ttu-id="2b3f0-121">Las secciones siguientes muestran una visión general de las visualizaciones.</span><span class="sxs-lookup"><span data-stu-id="2b3f0-121">The following sections provide an overview of the visualizations.</span></span>

### <a name="purchase-by-vendor-report-page"></a><span data-ttu-id="2b3f0-122">Compras por página del informe del proveedor</span><span class="sxs-lookup"><span data-stu-id="2b3f0-122">Purchase by vendor report page</span></span>
<span data-ttu-id="2b3f0-123">**Gráficos**</span><span class="sxs-lookup"><span data-stu-id="2b3f0-123">**Charts**</span></span>
- <span data-ttu-id="2b3f0-124">Los 10 principales proveedores por compra (gráfico de barras apiladas)</span><span class="sxs-lookup"><span data-stu-id="2b3f0-124">Top 10 vendors by purchase (stacked bar chart)</span></span>
- <span data-ttu-id="2b3f0-125">Compras totales por grupo de proveedores/país/nombre (gráfico circular)</span><span class="sxs-lookup"><span data-stu-id="2b3f0-125">Total purchase by vendor group / country / name (pie chart)</span></span>
- <span data-ttu-id="2b3f0-126">Compras por grupo de proveedores/país/nombre (gráfico de columnas)</span><span class="sxs-lookup"><span data-stu-id="2b3f0-126">Purchase by vendor group / country / name (column chart)</span></span>
- <span data-ttu-id="2b3f0-127">Promedio de compras por grupo de proveedores/país/nombre (gráfico de columnas)</span><span class="sxs-lookup"><span data-stu-id="2b3f0-127">Average purchase by vendor group / country / name (column chart)</span></span>

<span data-ttu-id="2b3f0-128">**Mosaicos**</span><span class="sxs-lookup"><span data-stu-id="2b3f0-128">**Tiles**</span></span>
- <span data-ttu-id="2b3f0-129">Total de la compra</span><span class="sxs-lookup"><span data-stu-id="2b3f0-129">Total purchase</span></span>
- <span data-ttu-id="2b3f0-130">Crecimiento de compras interanual</span><span class="sxs-lookup"><span data-stu-id="2b3f0-130">YOY purchase growth</span></span>
- <span data-ttu-id="2b3f0-131">N.º total de proveedores</span><span class="sxs-lookup"><span data-stu-id="2b3f0-131">Total # vendors</span></span>
- <span data-ttu-id="2b3f0-132">N.º total de proveedores activos</span><span class="sxs-lookup"><span data-stu-id="2b3f0-132">Total # of active vendors</span></span>

<span data-ttu-id="2b3f0-133">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="2b3f0-133">**Example**</span></span>
<img src="media/spend1.png" alt="Purchase by vendor">

### <a name="purchase-by-product-report-page"></a><span data-ttu-id="2b3f0-134">Compras por página del informe de producto</span><span class="sxs-lookup"><span data-stu-id="2b3f0-134">Purchase by product report page</span></span>

<span data-ttu-id="2b3f0-135">**Gráficos**</span><span class="sxs-lookup"><span data-stu-id="2b3f0-135">**Charts**</span></span>
- <span data-ttu-id="2b3f0-136">Compras por categoría de compras o nombre del producto (gráfico de columnas)</span><span class="sxs-lookup"><span data-stu-id="2b3f0-136">Purchase by procurement category / product name (column chart)</span></span>
- <span data-ttu-id="2b3f0-137">Compra total por categoría de compras o nombre del producto (gráfico circular)</span><span class="sxs-lookup"><span data-stu-id="2b3f0-137">Total purchase by procurement category / product name (pie chart)</span></span>
- <span data-ttu-id="2b3f0-138">Los 10 principales productos por compra (gráfico de barras apiladas)</span><span class="sxs-lookup"><span data-stu-id="2b3f0-138">Top 10 products by purchase (stacked bar chart)</span></span>

<span data-ttu-id="2b3f0-139">**Mosaicos**</span><span class="sxs-lookup"><span data-stu-id="2b3f0-139">**Tiles**</span></span>
- <span data-ttu-id="2b3f0-140">N.º total de productos</span><span class="sxs-lookup"><span data-stu-id="2b3f0-140">Total # of products</span></span></li>
- <span data-ttu-id="2b3f0-141">Porcentaje total de productos activos de n.º total de productos</span><span class="sxs-lookup"><span data-stu-id="2b3f0-141">Total active products percentage of total # of products</span></span>
- <span data-ttu-id="2b3f0-142">Número de productos que representan el 80 % de la compra</span><span class="sxs-lookup"><span data-stu-id="2b3f0-142">Number of products accounting for 80% purchase</span></span>

<span data-ttu-id="2b3f0-143">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="2b3f0-143">**Example**</span></span>


<img src="media/purchaseByProduct.png" alt="Purchase by Product">

### <a name="purchase-by-period-report-page"></a><span data-ttu-id="2b3f0-144">Compras por página del informe de período</span><span class="sxs-lookup"><span data-stu-id="2b3f0-144">Purchase by period report page</span></span>
<span data-ttu-id="2b3f0-145">Esta página muestra compras este año y el año anterior, y crecimiento por categoría de compras.</span><span class="sxs-lookup"><span data-stu-id="2b3f0-145">This page shows purchases this year and last year, and growth by procurement category.</span></span>

<span data-ttu-id="2b3f0-146">**Gráficos**</span><span class="sxs-lookup"><span data-stu-id="2b3f0-146">**Charts**</span></span> 
- <span data-ttu-id="2b3f0-147">Compras por mes/día (gráfico de columnas)</span><span class="sxs-lookup"><span data-stu-id="2b3f0-147">Purchase by month / day (column chart)</span></span>
- <span data-ttu-id="2b3f0-148">Desviación interanual de compras acumuladas (gráfico de cascada)</span><span class="sxs-lookup"><span data-stu-id="2b3f0-148">Cumulative purchase YOY variance (waterfall chart)</span></span>
- <span data-ttu-id="2b3f0-149">Crecimiento total de la compra interanual (gráfico de columnas)</span><span class="sxs-lookup"><span data-stu-id="2b3f0-149">Total purchase YOY growth (column chart)</span></span>
- <span data-ttu-id="2b3f0-150">Extracto de compras (matriz)</span><span class="sxs-lookup"><span data-stu-id="2b3f0-150">Procurement statement (matrix)</span></span>

<span data-ttu-id="2b3f0-151">**Mosaicos**</span><span class="sxs-lookup"><span data-stu-id="2b3f0-151">**Tiles**</span></span>
- <span data-ttu-id="2b3f0-152">Crecimiento de compras interanual</span><span class="sxs-lookup"><span data-stu-id="2b3f0-152">YOY purchase growth</span></span>
- <span data-ttu-id="2b3f0-153">% de crecimiento de compras interanual</span><span class="sxs-lookup"><span data-stu-id="2b3f0-153">YOY purchase growth %</span></span>

<span data-ttu-id="2b3f0-154">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="2b3f0-154">**Example**</span></span>
<img src="media/purchaseByPeriod.png" alt="Purchase by Period">

### <a name="purchase-by-vendor-location-report-page"></a><span data-ttu-id="2b3f0-155">Compras por página del informe de ubicación</span><span class="sxs-lookup"><span data-stu-id="2b3f0-155">Purchase by vendor location report page</span></span>

<span data-ttu-id="2b3f0-156">**Gráficos**</span><span class="sxs-lookup"><span data-stu-id="2b3f0-156">**Charts**</span></span>
- <span data-ttu-id="2b3f0-157">Compras por ciudad</span><span class="sxs-lookup"><span data-stu-id="2b3f0-157">Purchase by city</span></span>
- <span data-ttu-id="2b3f0-158">% de crecimiento de compras interanual</span><span class="sxs-lookup"><span data-stu-id="2b3f0-158">Purchase YOY growth %</span></span>
- <span data-ttu-id="2b3f0-159">Compras por país</span><span class="sxs-lookup"><span data-stu-id="2b3f0-159">Purchase by country</span></span>

<span data-ttu-id="2b3f0-160">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="2b3f0-160">**Example**</span></span>
<img src="media/purchByVendorLocation.png" alt="Purchase by Vendor Location">

### <a name="purchase-spend-analysis-by-time-report-page"></a><span data-ttu-id="2b3f0-161">Análisis de gasto de compras por página de hora del informe</span><span class="sxs-lookup"><span data-stu-id="2b3f0-161">Purchase spend analysis by time report page</span></span>

<span data-ttu-id="2b3f0-162">**Gráficos**</span><span class="sxs-lookup"><span data-stu-id="2b3f0-162">**Charts**</span></span> 
- <span data-ttu-id="2b3f0-163">Compras de año actual por mes/día (gráfico de líneas)</span><span class="sxs-lookup"><span data-stu-id="2b3f0-163">Purchase current year by month / day (line chart)</span></span>
- <span data-ttu-id="2b3f0-164">Compras este año y el año anterior (gráficos de líneas y columnas)</span><span class="sxs-lookup"><span data-stu-id="2b3f0-164">Purchase current and last year (line and column chart)</span></span>

<span data-ttu-id="2b3f0-165">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="2b3f0-165">**Example**</span></span>
<img src="media/PurchByTIme.png" alt="Purchase by Time">

### <a name="purchase-spend-analysis-by-vendor-report-page"></a><span data-ttu-id="2b3f0-166">Análisis de gasto de compras por página de proveedor del informe</span><span class="sxs-lookup"><span data-stu-id="2b3f0-166">Purchase spend analysis by vendor report page</span></span>

<span data-ttu-id="2b3f0-167">**Gráficos**</span><span class="sxs-lookup"><span data-stu-id="2b3f0-167">**Charts**</span></span> 
- <span data-ttu-id="2b3f0-168">% de compras de los 10 principales proveedores sobre el total de compras (embudo)</span><span class="sxs-lookup"><span data-stu-id="2b3f0-168">Top 10 vendor purchase % of purchase (funnel)</span></span>
- <span data-ttu-id="2b3f0-169">10 principales proveedores con aumento de gastos interanual</span><span class="sxs-lookup"><span data-stu-id="2b3f0-169">Top 10 vendors with increased spending YOY</span></span>
- <span data-ttu-id="2b3f0-170">10 principales proveedores con disminución de gastos interanual</span><span class="sxs-lookup"><span data-stu-id="2b3f0-170">Top 10 vendors with decreased spending YOY</span></span>

<span data-ttu-id="2b3f0-171">**Ejemplo** 
</span><span class="sxs-lookup"><span data-stu-id="2b3f0-171">**Example** 
</span></span><img src="media/PurchSpendAnalysisByVendor.png" alt="Purchase spend by vendor">


## <a name="data-model-and-entities"></a><span data-ttu-id="2b3f0-172">Modelo de datos y entidades</span><span class="sxs-lookup"><span data-stu-id="2b3f0-172">Data model and entities</span></span>
<span data-ttu-id="2b3f0-173">Los datos siguientes se usan para rellenar las páginas de informes en el contenido de Power BI sobre **Análisis de compras y gastos**.</span><span class="sxs-lookup"><span data-stu-id="2b3f0-173">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="2b3f0-174">Estos datos se representan como medidas agregadas que se realizan en el almacén de la entidad.</span><span class="sxs-lookup"><span data-stu-id="2b3f0-174">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="2b3f0-175">El almacén de la entidad es una base de datos de Microsoft SQL Server que se optimiza para el análisis.</span><span class="sxs-lookup"><span data-stu-id="2b3f0-175">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="2b3f0-176">Para obtener más información, consulte [Integración de Power BI con el almacén de entidades](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="2b3f0-176">For more information, see [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="2b3f0-177">Las medidas globales de este paquete de contenido son el subconjunto de las medidas globales que estaban disponibles en el cubo de compra en Microsoft Dynamics AX 2012 y Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="2b3f0-177">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="2b3f0-178">Para realizar las medidas globales del cubo en el almacén de entidades debe hacer que sean desplegables.</span><span class="sxs-lookup"><span data-stu-id="2b3f0-178">To stage the cube's aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="2b3f0-179">Para obtener más información, consulte el procedimiento relativo a cómo realizar mediciones globales en el almacén de entidades en [Visión general de la integración de Power BI con el almacén de entidades](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="2b3f0-179">For more information, see the procedure for staging aggregate measurements in the Entity store in [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="2b3f0-180">Las siguientes medidas agregadas clave están directamente disponibles en la entidad de líneas de factura y se usan como base del contenido.</span><span class="sxs-lookup"><span data-stu-id="2b3f0-180">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="2b3f0-181">Entidad</span><span class="sxs-lookup"><span data-stu-id="2b3f0-181">Entity</span></span>        | <span data-ttu-id="2b3f0-182">Medidas agregadas clave</span><span class="sxs-lookup"><span data-stu-id="2b3f0-182">Key aggregate measurements</span></span> | <span data-ttu-id="2b3f0-183">Origen de datos</span><span class="sxs-lookup"><span data-stu-id="2b3f0-183">Data source</span></span>                                 | <span data-ttu-id="2b3f0-184">Campo</span><span class="sxs-lookup"><span data-stu-id="2b3f0-184">Field</span></span>              | <span data-ttu-id="2b3f0-185">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b3f0-185">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="2b3f0-186">Líneas de factura</span><span class="sxs-lookup"><span data-stu-id="2b3f0-186">Invoice lines</span></span> | <span data-ttu-id="2b3f0-187">Compra</span><span class="sxs-lookup"><span data-stu-id="2b3f0-187">Purchase</span></span>                   | <span data-ttu-id="2b3f0-188">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="2b3f0-188">VendInvoiceTrans</span></span>                            | <span data-ttu-id="2b3f0-189">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="2b3f0-189">SUM(LineAmountMST)</span></span> | <span data-ttu-id="2b3f0-190">El importe en la divisa de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="2b3f0-190">The amount in the accounting currency.</span></span> |

<span data-ttu-id="2b3f0-191">En la tabla siguiente se muestran las medidas clave del contenido que se calculan a partir de la entidad de las líneas de factura.</span><span class="sxs-lookup"><span data-stu-id="2b3f0-191">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="2b3f0-192">Medida</span><span class="sxs-lookup"><span data-stu-id="2b3f0-192">Measure</span></span>               | <span data-ttu-id="2b3f0-193">Cálculo</span><span class="sxs-lookup"><span data-stu-id="2b3f0-193">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="2b3f0-194">Año actual de compra</span><span class="sxs-lookup"><span data-stu-id="2b3f0-194">Purchase current year</span></span> | <span data-ttu-id="2b3f0-195">Año actual de compra = SUM('Líneas de factura'\[Compra\])</span><span class="sxs-lookup"><span data-stu-id="2b3f0-195">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="2b3f0-196">Compra el año pasado</span><span class="sxs-lookup"><span data-stu-id="2b3f0-196">Purchase last year</span></span>    | <span data-ttu-id="2b3f0-197">Compra el año pasado = CALCULATE(SUM('Líneas factura'\[Compra\]), SAMEPERIODLASTYEAR(Fechas\[Fecha\]))</span><span class="sxs-lookup"><span data-stu-id="2b3f0-197">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="2b3f0-198">Crecimiento de compras interanual</span><span class="sxs-lookup"><span data-stu-id="2b3f0-198">YOY purchase growth</span></span>   | <span data-ttu-id="2b3f0-199">Crecimiento de compras interanual = \[Compra año actual\] – \[Compra el año pasado\]</span><span class="sxs-lookup"><span data-stu-id="2b3f0-199">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="2b3f0-200">Las dimensiones clave siguientes del contenido se utilizan como filtros para cortar las medidas globales para lograr mayor granularidad y profundizar en la visión analítica.</span><span class="sxs-lookup"><span data-stu-id="2b3f0-200">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="2b3f0-201">Entidad</span><span class="sxs-lookup"><span data-stu-id="2b3f0-201">Entity</span></span>                 | <span data-ttu-id="2b3f0-202">Ejemplos de atributos</span><span class="sxs-lookup"><span data-stu-id="2b3f0-202">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="2b3f0-203">Empresas proveedoras</span><span class="sxs-lookup"><span data-stu-id="2b3f0-203">Vendors</span></span>                | <span data-ttu-id="2b3f0-204">Grupos de proveedores, países o regiones de proveedores, nombre del proveedor</span><span class="sxs-lookup"><span data-stu-id="2b3f0-204">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="2b3f0-205">Productos</span><span class="sxs-lookup"><span data-stu-id="2b3f0-205">Products</span></span>               | <span data-ttu-id="2b3f0-206">Número de producto, nombre de producto, nombre de grupos de artículos</span><span class="sxs-lookup"><span data-stu-id="2b3f0-206">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="2b3f0-207">Categorías de adquisición</span><span class="sxs-lookup"><span data-stu-id="2b3f0-207">Procurement categories</span></span> | <span data-ttu-id="2b3f0-208">Categoría de compras, nombres de la categoría de compras</span><span class="sxs-lookup"><span data-stu-id="2b3f0-208">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="2b3f0-209">Entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="2b3f0-209">Legal entities</span></span>         | <span data-ttu-id="2b3f0-210">Nombre de la entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="2b3f0-210">Legal entity name</span></span>                                     |
| <span data-ttu-id="2b3f0-211">Fechas</span><span class="sxs-lookup"><span data-stu-id="2b3f0-211">Dates</span></span>                  | <span data-ttu-id="2b3f0-212">Fechas, contrapartida anual</span><span class="sxs-lookup"><span data-stu-id="2b3f0-212">Dates, Year offset</span></span>                                    |

<span data-ttu-id="2b3f0-213">De forma predeterminada, el contenido muestra los datos del año natural actual.</span><span class="sxs-lookup"><span data-stu-id="2b3f0-213">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="2b3f0-214">Sin embargo, puede cambiar el filtro de la fecha en la sección de filtros de informe.</span><span class="sxs-lookup"><span data-stu-id="2b3f0-214">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="2b3f0-215">También puede cambiar el filtro de empresa.</span><span class="sxs-lookup"><span data-stu-id="2b3f0-215">You can also change the company filter.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]