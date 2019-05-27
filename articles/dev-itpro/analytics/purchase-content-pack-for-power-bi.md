---
title: Contenido de Power BI del análisis de compras y gastos
description: Este tema describe lo que se incluye en el contenido de Power BI acerca de análisis de compras y gastos. Explica cómo tener acceso a los informes que se incluyen en el contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.
author: FrankDahl
manager: AnnBe
ms.date: 04/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
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
ms.openlocfilehash: 3206573022c0f843b07a468987a112ca6ac435ef
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1527726"
---
# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="518e0-104">Contenido de Power BI del análisis de compras y gastos</span><span class="sxs-lookup"><span data-stu-id="518e0-104">Purchase spend analysis Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="518e0-105">Este tema describe lo que se incluye en el contenido de Microsoft Power BI acerca de **análisis de compras y gastos**.</span><span class="sxs-lookup"><span data-stu-id="518e0-105">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="518e0-106">Explica cómo obtener acceso a los informes de Power BI y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.</span><span class="sxs-lookup"><span data-stu-id="518e0-106">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="518e0-107">Información general</span><span class="sxs-lookup"><span data-stu-id="518e0-107">Overview</span></span>

<span data-ttu-id="518e0-108">El contenido de Power BI sobre **Análisis de compras y gastos** se ha diseñado para ayudar a directores de compras y los administradores responsables de presupuestos y seguir los gastos en adquisiciones.</span><span class="sxs-lookup"><span data-stu-id="518e0-108">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep track of purchase spending.</span></span> <span data-ttu-id="518e0-109">Los directores pueden analizar su gasto en adquisiciones de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="518e0-109">Managers can analyze purchase spending in the following ways:</span></span>

- <span data-ttu-id="518e0-110">Compras hasta la fecha (por grupo de proveedores y proveedores individuales, productos de la categoría de compras e individuales y ubicación del proveedor)</span><span class="sxs-lookup"><span data-stu-id="518e0-110">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
- <span data-ttu-id="518e0-111">Cambio de las compras año por año (por grupo de proveedores y categoría de compras)</span><span class="sxs-lookup"><span data-stu-id="518e0-111">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="518e0-112">El contenido usa datos transaccionales de compras y proporciona tanto una visión global de las cifras de compras en la empresa como un desglose de los gastos en compras por proveedor y producto.</span><span class="sxs-lookup"><span data-stu-id="518e0-112">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="518e0-113">Los informes resaltan cambios en los gastos de compra a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="518e0-113">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="518e0-114">Por lo tanto, los informes se pueden usar para notificar a los administradores las tendencias positivas y negativas de los gastos relativas a proveedores y productos individuales.</span><span class="sxs-lookup"><span data-stu-id="518e0-114">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="518e0-115">Además, los gráficos muestran los gastos de compra para las diversas categorías de compras y grupos de proveedores.</span><span class="sxs-lookup"><span data-stu-id="518e0-115">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="518e0-116">Por lo tanto, los administradores de categorías y regionales pueden utilizar los gráficos como ayuda para identificar los cambios en comportamiento del gasto.</span><span class="sxs-lookup"><span data-stu-id="518e0-116">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="518e0-117">Acceso al contenido de Power BI</span><span class="sxs-lookup"><span data-stu-id="518e0-117">Accessing the Power BI content</span></span>
<span data-ttu-id="518e0-118">El contenido de Power BI **Análisis de compras y gastos** se muestra en la página **Análisis de compras y gastos** (**Adquisición y abastecimiento** \> **Consultas e informes** \> **Análisis del rendimiento de compra** \> **Análisis de compras y gastos**).</span><span class="sxs-lookup"><span data-stu-id="518e0-118">The **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** \> **Inquiries and reports** \> **Purchase performance analysis** \> **Purchase and spend analysis**).</span></span>

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="518e0-119">Métricas que se incluyen en el contenido de Power BI</span><span class="sxs-lookup"><span data-stu-id="518e0-119">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="518e0-120">El contenido de Power BI de **análisis de los gastos de compra** incluye un informe compuesto por un conjunto de medidas.</span><span class="sxs-lookup"><span data-stu-id="518e0-120">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="518e0-121">Estas métricas se visualizan como gráficos, mosaicos y tablas.</span><span class="sxs-lookup"><span data-stu-id="518e0-121">These metrics are visualized as charts, tiles, and tables.</span></span> 

<span data-ttu-id="518e0-122">Las secciones siguientes muestran una visión general de las visualizaciones.</span><span class="sxs-lookup"><span data-stu-id="518e0-122">The following sections provide an overview of the visualizations.</span></span>

### <a name="purchase-by-vendor-report-page"></a><span data-ttu-id="518e0-123">Compras por página del informe del proveedor</span><span class="sxs-lookup"><span data-stu-id="518e0-123">Purchase by vendor report page</span></span>
<span data-ttu-id="518e0-124">**Gráficos**</span><span class="sxs-lookup"><span data-stu-id="518e0-124">**Charts**</span></span>
- <span data-ttu-id="518e0-125">Los 10 principales proveedores por compra (gráfico de barras apiladas)</span><span class="sxs-lookup"><span data-stu-id="518e0-125">Top 10 vendors by purchase (stacked bar chart)</span></span>
- <span data-ttu-id="518e0-126">Compras totales por grupo de proveedores/país/nombre (gráfico circular)</span><span class="sxs-lookup"><span data-stu-id="518e0-126">Total purchase by vendor group / country / name (pie chart)</span></span>
- <span data-ttu-id="518e0-127">Compras por grupo de proveedores/país/nombre (gráfico de columnas)</span><span class="sxs-lookup"><span data-stu-id="518e0-127">Purchase by vendor group / country / name (column chart)</span></span>
- <span data-ttu-id="518e0-128">Promedio de compras por grupo de proveedores/país/nombre (gráfico de columnas)</span><span class="sxs-lookup"><span data-stu-id="518e0-128">Average purchase by vendor group / country / name (column chart)</span></span>

<span data-ttu-id="518e0-129">**Mosaicos**</span><span class="sxs-lookup"><span data-stu-id="518e0-129">**Tiles**</span></span>
- <span data-ttu-id="518e0-130">Total de la compra</span><span class="sxs-lookup"><span data-stu-id="518e0-130">Total purchase</span></span>
- <span data-ttu-id="518e0-131">Crecimiento de compras interanual</span><span class="sxs-lookup"><span data-stu-id="518e0-131">YOY purchase growth</span></span>
- <span data-ttu-id="518e0-132">N.º total de proveedores</span><span class="sxs-lookup"><span data-stu-id="518e0-132">Total # vendors</span></span>
- <span data-ttu-id="518e0-133">N.º total de proveedores activos</span><span class="sxs-lookup"><span data-stu-id="518e0-133">Total # of active vendors</span></span>

<span data-ttu-id="518e0-134">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="518e0-134">**Example**</span></span>
<img src="media/spend1.PNG" alt="Purchase by vendor">

### <a name="purchase-by-product-report-page"></a><span data-ttu-id="518e0-135">Compras por página del informe de producto</span><span class="sxs-lookup"><span data-stu-id="518e0-135">Purchase by product report page</span></span>

<span data-ttu-id="518e0-136">**Gráficos**</span><span class="sxs-lookup"><span data-stu-id="518e0-136">**Charts**</span></span>
- <span data-ttu-id="518e0-137">Compras por categoría de compras o nombre del producto (gráfico de columnas)</span><span class="sxs-lookup"><span data-stu-id="518e0-137">Purchase by procurement category / product name (column chart)</span></span>
- <span data-ttu-id="518e0-138">Compra total por categoría de compras o nombre del producto (gráfico circular)</span><span class="sxs-lookup"><span data-stu-id="518e0-138">Total purchase by procurement category / product name (pie chart)</span></span>
- <span data-ttu-id="518e0-139">Los 10 principales productos por compra (gráfico de barras apiladas)</span><span class="sxs-lookup"><span data-stu-id="518e0-139">Top 10 products by purchase (stacked bar chart)</span></span>

<span data-ttu-id="518e0-140">**Mosaicos**</span><span class="sxs-lookup"><span data-stu-id="518e0-140">**Tiles**</span></span>
- <span data-ttu-id="518e0-141">N.º total de productos</span><span class="sxs-lookup"><span data-stu-id="518e0-141">Total # of products</span></span></li>
- <span data-ttu-id="518e0-142">Porcentaje total de productos activos de n.º total de productos</span><span class="sxs-lookup"><span data-stu-id="518e0-142">Total active products percentage of total # of products</span></span>
- <span data-ttu-id="518e0-143">Número de productos que representan el 80 % de la compra</span><span class="sxs-lookup"><span data-stu-id="518e0-143">Number of products accounting for 80% purchase</span></span>

<span data-ttu-id="518e0-144">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="518e0-144">**Example**</span></span>


<img src="media/purchaseByProduct.PNG" alt="Purchase by Product">

### <a name="purchase-by-period-report-page"></a><span data-ttu-id="518e0-145">Compras por página del informe de período</span><span class="sxs-lookup"><span data-stu-id="518e0-145">Purchase by period report page</span></span>
<span data-ttu-id="518e0-146">Esta página muestra compras este año y el año anterior, y crecimiento por categoría de compras.</span><span class="sxs-lookup"><span data-stu-id="518e0-146">This page shows purchases this year and last year, and growth by procurement category.</span></span>

<span data-ttu-id="518e0-147">**Gráficos**</span><span class="sxs-lookup"><span data-stu-id="518e0-147">**Charts**</span></span> 
- <span data-ttu-id="518e0-148">Compras por mes/día (gráfico de columnas)</span><span class="sxs-lookup"><span data-stu-id="518e0-148">Purchase by month / day (column chart)</span></span>
- <span data-ttu-id="518e0-149">Desviación interanual de compras acumuladas (gráfico de cascada)</span><span class="sxs-lookup"><span data-stu-id="518e0-149">Cumulative purchase YOY variance (waterfall chart)</span></span>
- <span data-ttu-id="518e0-150">Crecimiento total de la compra interanual (gráfico de columnas)</span><span class="sxs-lookup"><span data-stu-id="518e0-150">Total purchase YOY growth (column chart)</span></span>
- <span data-ttu-id="518e0-151">Extracto de compras (matriz)</span><span class="sxs-lookup"><span data-stu-id="518e0-151">Procurement statement (matrix)</span></span>

<span data-ttu-id="518e0-152">**Mosaicos**</span><span class="sxs-lookup"><span data-stu-id="518e0-152">**Tiles**</span></span>
- <span data-ttu-id="518e0-153">Crecimiento de compras interanual</span><span class="sxs-lookup"><span data-stu-id="518e0-153">YOY purchase growth</span></span>
- <span data-ttu-id="518e0-154">% de crecimiento de compras interanual</span><span class="sxs-lookup"><span data-stu-id="518e0-154">YOY purchase growth %</span></span>

<span data-ttu-id="518e0-155">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="518e0-155">**Example**</span></span>
<img src="media/purchaseByPeriod.PNG" alt="Purchase by Period">

### <a name="purchase-by-vendor-location-report-page"></a><span data-ttu-id="518e0-156">Compras por página del informe de ubicación</span><span class="sxs-lookup"><span data-stu-id="518e0-156">Purchase by vendor location report page</span></span>

<span data-ttu-id="518e0-157">**Gráficos**</span><span class="sxs-lookup"><span data-stu-id="518e0-157">**Charts**</span></span>
- <span data-ttu-id="518e0-158">Compras por ciudad</span><span class="sxs-lookup"><span data-stu-id="518e0-158">Purchase by city</span></span>
- <span data-ttu-id="518e0-159">% de crecimiento de compras interanual</span><span class="sxs-lookup"><span data-stu-id="518e0-159">Purchase YOY growth %</span></span>
- <span data-ttu-id="518e0-160">Compras por país</span><span class="sxs-lookup"><span data-stu-id="518e0-160">Purchase by country</span></span>

<span data-ttu-id="518e0-161">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="518e0-161">**Example**</span></span>
<img src="media/purchByVendorLocation.PNG" alt="Purchase by Vendor Location">

### <a name="purchase-spend-analysis-by-time-report-page"></a><span data-ttu-id="518e0-162">Análisis de gasto de compras por página de hora del informe</span><span class="sxs-lookup"><span data-stu-id="518e0-162">Purchase spend analysis by time report page</span></span>

<span data-ttu-id="518e0-163">**Gráficos**</span><span class="sxs-lookup"><span data-stu-id="518e0-163">**Charts**</span></span> 
- <span data-ttu-id="518e0-164">Compras de año actual por mes/día (gráfico de líneas)</span><span class="sxs-lookup"><span data-stu-id="518e0-164">Purchase current year by month / day (line chart)</span></span>
- <span data-ttu-id="518e0-165">Compras este año y el año anterior (gráficos de líneas y columnas)</span><span class="sxs-lookup"><span data-stu-id="518e0-165">Purchase current and last year (line and column chart)</span></span>

<span data-ttu-id="518e0-166">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="518e0-166">**Example**</span></span>
<img src="media/PurchByTIme.PNG" alt="Purchase by Time">

### <a name="purchase-spend-analysis-by-vendor-report-page"></a><span data-ttu-id="518e0-167">Análisis de gasto de compras por página de proveedor del informe</span><span class="sxs-lookup"><span data-stu-id="518e0-167">Purchase spend analysis by vendor report page</span></span>

<span data-ttu-id="518e0-168">**Gráficos**</span><span class="sxs-lookup"><span data-stu-id="518e0-168">**Charts**</span></span> 
- <span data-ttu-id="518e0-169">% de compras de los 10 principales proveedores sobre el total de compras (embudo)</span><span class="sxs-lookup"><span data-stu-id="518e0-169">Top 10 vendor purchase % of purchase (funnel)</span></span>
- <span data-ttu-id="518e0-170">10 principales proveedores con aumento de gastos interanual</span><span class="sxs-lookup"><span data-stu-id="518e0-170">Top 10 vendors with increased spending YOY</span></span>
- <span data-ttu-id="518e0-171">10 principales proveedores con disminución de gastos interanual</span><span class="sxs-lookup"><span data-stu-id="518e0-171">Top 10 vendors with decreased spending YOY</span></span>

<span data-ttu-id="518e0-172">**Ejemplo** 
</span><span class="sxs-lookup"><span data-stu-id="518e0-172">**Example** 
</span></span><img src="media/PurchSpendAnalysisByVendor.PNG" alt="Purchase spend by vendor">


## <a name="data-model-and-entities"></a><span data-ttu-id="518e0-173">Modelo de datos y entidades</span><span class="sxs-lookup"><span data-stu-id="518e0-173">Data model and entities</span></span>
<span data-ttu-id="518e0-174">Los datos siguientes se usan para rellenar las páginas de informes en el contenido de Power BI sobre **Análisis de compras y gastos**.</span><span class="sxs-lookup"><span data-stu-id="518e0-174">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="518e0-175">Estos datos se representan como medidas agregadas que se realizan en el almacén de la entidad.</span><span class="sxs-lookup"><span data-stu-id="518e0-175">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="518e0-176">El almacén de la entidad es una base de datos de Microsoft SQL Server que se optimiza para el análisis.</span><span class="sxs-lookup"><span data-stu-id="518e0-176">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="518e0-177">Para obtener más información, consulte [Visión general de la integración de Power BI con el almacén de entidades](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="518e0-177">For more information, see [Overview of Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="518e0-178">Las medidas globales de este paquete de contenido son el subconjunto de las medidas globales que estaban disponibles en el cubo de compra en Microsoft Dynamics AX 2012 y Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="518e0-178">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="518e0-179">Para realizar las medidas globales del cubo en el almacén de entidades debe hacer que sean desplegables.</span><span class="sxs-lookup"><span data-stu-id="518e0-179">To stage the cube's aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="518e0-180">Para obtener más información, consulte el procedimiento relativo a cómo realizar mediciones globales en el almacén de entidades en [Visión general de la integración de Power BI con el almacén de entidades](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="518e0-180">For more information, see the procedure for staging aggregate measurements in the Entity store in [Overview of Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="518e0-181">Las siguientes medidas agregadas clave están directamente disponibles en la entidad de líneas de factura y se usan como base del contenido.</span><span class="sxs-lookup"><span data-stu-id="518e0-181">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="518e0-182">Entidad</span><span class="sxs-lookup"><span data-stu-id="518e0-182">Entity</span></span>        | <span data-ttu-id="518e0-183">Medidas agregadas clave</span><span class="sxs-lookup"><span data-stu-id="518e0-183">Key aggregate measurements</span></span> | <span data-ttu-id="518e0-184">Origen de datos</span><span class="sxs-lookup"><span data-stu-id="518e0-184">Data source</span></span>                                 | <span data-ttu-id="518e0-185">Campo</span><span class="sxs-lookup"><span data-stu-id="518e0-185">Field</span></span>              | <span data-ttu-id="518e0-186">Descripción</span><span class="sxs-lookup"><span data-stu-id="518e0-186">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="518e0-187">Líneas de factura</span><span class="sxs-lookup"><span data-stu-id="518e0-187">Invoice lines</span></span> | <span data-ttu-id="518e0-188">Compra</span><span class="sxs-lookup"><span data-stu-id="518e0-188">Purchase</span></span>                   | <span data-ttu-id="518e0-189">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="518e0-189">VendInvoiceTrans</span></span>                            | <span data-ttu-id="518e0-190">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="518e0-190">SUM(LineAmountMST)</span></span> | <span data-ttu-id="518e0-191">El importe en la divisa de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="518e0-191">The amount in the accounting currency.</span></span> |

<span data-ttu-id="518e0-192">En la tabla siguiente se muestran las medidas clave del contenido que se calculan a partir de la entidad de las líneas de factura.</span><span class="sxs-lookup"><span data-stu-id="518e0-192">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="518e0-193">Medida</span><span class="sxs-lookup"><span data-stu-id="518e0-193">Measure</span></span>               | <span data-ttu-id="518e0-194">Cálculo</span><span class="sxs-lookup"><span data-stu-id="518e0-194">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="518e0-195">Año actual de compra</span><span class="sxs-lookup"><span data-stu-id="518e0-195">Purchase current year</span></span> | <span data-ttu-id="518e0-196">Año actual de compra = SUM('Líneas de factura'\[Compra\])</span><span class="sxs-lookup"><span data-stu-id="518e0-196">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="518e0-197">Compra el año pasado</span><span class="sxs-lookup"><span data-stu-id="518e0-197">Purchase last year</span></span>    | <span data-ttu-id="518e0-198">Compra el año pasado = CALCULATE(SUM('Líneas factura'\[Compra\]), SAMEPERIODLASTYEAR(Fechas\[Fecha\])</span><span class="sxs-lookup"><span data-stu-id="518e0-198">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="518e0-199">Crecimiento de compras interanual</span><span class="sxs-lookup"><span data-stu-id="518e0-199">YOY purchase growth</span></span>   | <span data-ttu-id="518e0-200">Crecimiento de compras interanual = \[Compra año actual\] – \[Compra el año pasado\]</span><span class="sxs-lookup"><span data-stu-id="518e0-200">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="518e0-201">Las dimensiones clave siguientes del contenido se utilizan como filtros para cortar las medidas globales para lograr mayor granularidad y profundizar en la visión analítica.</span><span class="sxs-lookup"><span data-stu-id="518e0-201">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="518e0-202">Entidad</span><span class="sxs-lookup"><span data-stu-id="518e0-202">Entity</span></span>                 | <span data-ttu-id="518e0-203">Ejemplos de atributos</span><span class="sxs-lookup"><span data-stu-id="518e0-203">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="518e0-204">Empresas proveedoras</span><span class="sxs-lookup"><span data-stu-id="518e0-204">Vendors</span></span>                | <span data-ttu-id="518e0-205">Grupos de proveedores, países o regiones de proveedores, nombre del proveedor</span><span class="sxs-lookup"><span data-stu-id="518e0-205">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="518e0-206">Productos</span><span class="sxs-lookup"><span data-stu-id="518e0-206">Products</span></span>               | <span data-ttu-id="518e0-207">Número de producto, nombre de producto, nombre de grupos de artículos</span><span class="sxs-lookup"><span data-stu-id="518e0-207">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="518e0-208">Categorías de adquisición</span><span class="sxs-lookup"><span data-stu-id="518e0-208">Procurement categories</span></span> | <span data-ttu-id="518e0-209">Categoría de compras, nombres de la categoría de compras</span><span class="sxs-lookup"><span data-stu-id="518e0-209">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="518e0-210">Entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="518e0-210">Legal entities</span></span>         | <span data-ttu-id="518e0-211">Nombre de la entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="518e0-211">Legal entity name</span></span>                                     |
| <span data-ttu-id="518e0-212">Fechas</span><span class="sxs-lookup"><span data-stu-id="518e0-212">Dates</span></span>                  | <span data-ttu-id="518e0-213">Fechas, contrapartida anual</span><span class="sxs-lookup"><span data-stu-id="518e0-213">Dates, Year offset</span></span>                                    |

<span data-ttu-id="518e0-214">De forma predeterminada, el contenido muestra los datos del año natural actual.</span><span class="sxs-lookup"><span data-stu-id="518e0-214">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="518e0-215">Sin embargo, puede cambiar el filtro de la fecha en la sección de filtros de informe.</span><span class="sxs-lookup"><span data-stu-id="518e0-215">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="518e0-216">También puede cambiar el filtro de empresa.</span><span class="sxs-lookup"><span data-stu-id="518e0-216">You can also change the company filter.</span></span>
