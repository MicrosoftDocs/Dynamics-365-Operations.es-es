---
title: "Contenido de Power BI sobre análisis de gastos de compra"
description: "Este tema describe lo que se incluye en el contenido de Power BI acerca de análisis de compras y gastos. Explica cómo tener acceso a los informes que se incluyen en el contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido."
author: FrankDahl
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3e42746329b1194c0ce0e2fb5c476742259a5b43
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="7b3ed-104">Contenido de Power BI sobre análisis de gastos de compra</span><span class="sxs-lookup"><span data-stu-id="7b3ed-104">Purchase spend analysis Power BI content</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="7b3ed-105">Este tema describe lo que se incluye en el contenido de Microsoft Power BI acerca de **Análisis de compras y gastos**.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-105">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="7b3ed-106">Explica cómo obtener acceso a los informes de Power BI y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-106">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="7b3ed-107">Información general</span><span class="sxs-lookup"><span data-stu-id="7b3ed-107">Overview</span></span>

<span data-ttu-id="7b3ed-108">El contenido de Power BI sobre **Análisis de compras y gastos** se ha diseñado para ayudar a directores de compras y los administradores responsables de presupuestos a vigilar los gastos en adquisiciones.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-108">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep an eye on purchase spending.</span></span> <span data-ttu-id="7b3ed-109">Los directores pueden analizar su gasto en adquisiciones de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="7b3ed-109">Managers can analyze purchase spending in the following ways:</span></span>

-   <span data-ttu-id="7b3ed-110">Compras hasta la fecha (por grupo de proveedores y proveedores individuales, productos de la categoría de compras e individuales y ubicación del proveedor)</span><span class="sxs-lookup"><span data-stu-id="7b3ed-110">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
-   <span data-ttu-id="7b3ed-111">Cambio de las compras año por año (por grupo de proveedores y categoría de compras)</span><span class="sxs-lookup"><span data-stu-id="7b3ed-111">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="7b3ed-112">El contenido usa datos transaccionales de compras y proporciona tanto una visión global de las cifras de compras en la empresa como un desglose de los gastos en compras por proveedor y producto.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-112">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="7b3ed-113">Los informes resaltan cambios en los gastos de compra a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-113">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="7b3ed-114">Por lo tanto, los informes se pueden usar para notificar a los administradores las tendencias positivas y negativas de los gastos relativas a proveedores y productos individuales.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-114">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="7b3ed-115">Además, los gráficos muestran los gastos de compra para las diversas categorías de compras y grupos de proveedores.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-115">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="7b3ed-116">Por lo tanto, los administradores de categorías y regionales pueden utilizar los gráficos como ayuda para identificar los cambios en comportamiento del gasto.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-116">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="7b3ed-117">Acceso al contenido de Power BI</span><span class="sxs-lookup"><span data-stu-id="7b3ed-117">Accessing the Power BI content</span></span>
<span data-ttu-id="7b3ed-118">Si usa Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (julio de 2017), el contenido de Power BI sobre **Análisis de compras y gastos** se muestra en la página **Análisis de compras y gastos** (**Adquisición y abastecimiento** > **Consultas e informes** > **Análisis del rendimiento de compra** > **Análisis de compras y gastos**).</span><span class="sxs-lookup"><span data-stu-id="7b3ed-118">If you're using Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017), the **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** > **Inquiries and reports** > **Purchase performance analysis** > **Purchase and spend analysis**).</span></span> 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="7b3ed-119">Métricas que se incluyen en el contenido de Power BI</span><span class="sxs-lookup"><span data-stu-id="7b3ed-119">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="7b3ed-120">El contenido de Power BI sobre **Análisis de compras y gastos** incluye un informe compuesto por un conjunto de métricas.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-120">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="7b3ed-121">Estas métricas se visualizan como gráficos, mosaicos y tablas.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-121">These metrics are visualized as charts, tiles, and tables.</span></span> <span data-ttu-id="7b3ed-122">La tabla siguiente muestra una visión general de las visualizaciones.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-122">The following table provides an overview of the visualizations.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b3ed-123">Página de informes</span><span class="sxs-lookup"><span data-stu-id="7b3ed-123">Report page</span></span></th>
<th><span data-ttu-id="7b3ed-124">Gráficos</span><span class="sxs-lookup"><span data-stu-id="7b3ed-124">Charts</span></span></th>
<th><span data-ttu-id="7b3ed-125">Mosaicos</span><span class="sxs-lookup"><span data-stu-id="7b3ed-125">Tiles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="7b3ed-126">Compras por proveedor</span><span class="sxs-lookup"><span data-stu-id="7b3ed-126">Purchase by vendor</span></span></td>
<td><ul>
<li><span data-ttu-id="7b3ed-127">Los 10 principales proveedores por compra (gráfico de barras apiladas)</span><span class="sxs-lookup"><span data-stu-id="7b3ed-127">Top 10 vendors by purchase (stacked bar chart)</span></span></li>
<li><span data-ttu-id="7b3ed-128">Compras totales por grupo de proveedores/país/nombre (gráfico circular)</span><span class="sxs-lookup"><span data-stu-id="7b3ed-128">Total purchase by vendor group / country / name (pie chart)</span></span></li>
<li><span data-ttu-id="7b3ed-129">Compras por grupo de proveedores/país/nombre (gráfico de columnas)</span><span class="sxs-lookup"><span data-stu-id="7b3ed-129">Purchase by vendor group / country / name (column chart)</span></span></li>
<li><span data-ttu-id="7b3ed-130">Promedio de compras por grupo de proveedores/país/nombre (gráfico de columnas)</span><span class="sxs-lookup"><span data-stu-id="7b3ed-130">Average purchase by vendor group / country / name (column chart)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="7b3ed-131">Total de la compra</span><span class="sxs-lookup"><span data-stu-id="7b3ed-131">Total purchase</span></span></li>
<li><span data-ttu-id="7b3ed-132">Crecimiento de compras interanual</span><span class="sxs-lookup"><span data-stu-id="7b3ed-132">YOY purchase growth</span></span></li>
<li><span data-ttu-id="7b3ed-133">N.º total de proveedores</span><span class="sxs-lookup"><span data-stu-id="7b3ed-133">Total # vendors</span></span></li>
<li><span data-ttu-id="7b3ed-134">N.º total de proveedores activos</span><span class="sxs-lookup"><span data-stu-id="7b3ed-134">Total # of active vendors</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7b3ed-135">Compras por producto</span><span class="sxs-lookup"><span data-stu-id="7b3ed-135">Purchase by product</span></span></td>
<td><ul>
<li><span data-ttu-id="7b3ed-136">Compras por categoría de compras o nombre del producto (gráfico de columnas)</span><span class="sxs-lookup"><span data-stu-id="7b3ed-136">Purchase by procurement category / product name (column chart)</span></span></li>
<li><span data-ttu-id="7b3ed-137">Compra total por categoría de compras o nombre del producto (gráfico circular)</span><span class="sxs-lookup"><span data-stu-id="7b3ed-137">Total purchase by procurement category / product name (pie chart)</span></span></li>
<li><span data-ttu-id="7b3ed-138">Los 10 principales productos por compra (gráfico de barras apiladas)</span><span class="sxs-lookup"><span data-stu-id="7b3ed-138">Top 10 products by purchase (stacked bar chart)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="7b3ed-139">N.º total de productos</span><span class="sxs-lookup"><span data-stu-id="7b3ed-139">Total # of products</span></span></li>
<li><span data-ttu-id="7b3ed-140">Porcentaje total de productos activos de n.º total de productos</span><span class="sxs-lookup"><span data-stu-id="7b3ed-140">Total active products percentage of total # of products</span></span></li>
<li><span data-ttu-id="7b3ed-141">Número de productos que representan el 80 % de la compra</span><span class="sxs-lookup"><span data-stu-id="7b3ed-141">Number of products accounting for 80% purchase</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7b3ed-142">Compras por período*</span><span class="sxs-lookup"><span data-stu-id="7b3ed-142">Purchase by period*</span></span></td>
<td><ul>
<li><span data-ttu-id="7b3ed-143">Compras por mes/día (gráfico de columnas)</span><span class="sxs-lookup"><span data-stu-id="7b3ed-143">Purchase by month / day (column chart)</span></span></li>
<li><span data-ttu-id="7b3ed-144">Desviación interanual de compras acumuladas (gráfico de cascada)</span><span class="sxs-lookup"><span data-stu-id="7b3ed-144">Cumulative purchase YOY variance (waterfall chart)</span></span></li>
<li><span data-ttu-id="7b3ed-145">Crecimiento total de la compra interanual (gráfico de columnas)</span><span class="sxs-lookup"><span data-stu-id="7b3ed-145">Total purchase YOY growth (column chart)</span></span></li>
<li><span data-ttu-id="7b3ed-146">Extracto de compras (matriz)</span><span class="sxs-lookup"><span data-stu-id="7b3ed-146">Procurement statement (matrix)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="7b3ed-147">Crecimiento de compras interanual</span><span class="sxs-lookup"><span data-stu-id="7b3ed-147">YOY purchase growth</span></span></li>
<li><span data-ttu-id="7b3ed-148">% de crecimiento de compras interanual</span><span class="sxs-lookup"><span data-stu-id="7b3ed-148">YOY purchase growth %</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7b3ed-149">Compras por ubicación de proveedor</span><span class="sxs-lookup"><span data-stu-id="7b3ed-149">Purchase by vendor location</span></span></td>
<td><ul>
<li><span data-ttu-id="7b3ed-150">Compras por ciudad</span><span class="sxs-lookup"><span data-stu-id="7b3ed-150">Purchase by city</span></span></li>
<li><span data-ttu-id="7b3ed-151">% de crecimiento de compras interanual</span><span class="sxs-lookup"><span data-stu-id="7b3ed-151">Purchase YOY growth %</span></span></li>
<li><span data-ttu-id="7b3ed-152">Compras por país</span><span class="sxs-lookup"><span data-stu-id="7b3ed-152">Purchase by country</span></span></li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7b3ed-153">Análisis de gasto de compras por hora</span><span class="sxs-lookup"><span data-stu-id="7b3ed-153">Purchase spend analysis by time</span></span></td>
<td><ul>
<li><span data-ttu-id="7b3ed-154">Compras de año actual por mes/día (gráfico de líneas)</span><span class="sxs-lookup"><span data-stu-id="7b3ed-154">Purchase current year by month / day (line chart)</span></span></li>
<li><span data-ttu-id="7b3ed-155">Compras este año y el año anterior (gráficos de líneas y columnas)</span><span class="sxs-lookup"><span data-stu-id="7b3ed-155">Purchase current and last year (line and column chart)</span></span></li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7b3ed-156">Análisis de gasto de compras por proveedor</span><span class="sxs-lookup"><span data-stu-id="7b3ed-156">Purchase spend analysis by vendor</span></span></td>
<td><ul>
<li><span data-ttu-id="7b3ed-157">% de compras de los 10 principales proveedores sobre el total de compras (embudo)</span><span class="sxs-lookup"><span data-stu-id="7b3ed-157">Top 10 vendor purchase % of purchase (funnel)</span></span></li>
<li><span data-ttu-id="7b3ed-158">10 principales proveedores con aumento de gastos interanual</span><span class="sxs-lookup"><span data-stu-id="7b3ed-158">Top 10 vendors with increased spending YOY</span></span></li>
<li><span data-ttu-id="7b3ed-159">10 principales proveedores con disminución de gastos interanual</span><span class="sxs-lookup"><span data-stu-id="7b3ed-159">Top 10 vendors with decreased spending YOY</span></span></li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7b3ed-160">\* Compras este año y el año anterior, y crecimiento por categoría de compras</span><span class="sxs-lookup"><span data-stu-id="7b3ed-160">\* Purchase this year and last year, and growth by procurement category</span></span>

## <a name="extending-the-power-bi-content"></a><span data-ttu-id="7b3ed-161">Ampliar el contenido de Power BI</span><span class="sxs-lookup"><span data-stu-id="7b3ed-161">Extending the Power BI content</span></span>
<span data-ttu-id="7b3ed-162">Mediante los paquetes de contenido disponibles en Microsoft Dynamics Lifecycle Services (LCS), puede ofrecer análisis muy buenos a las personas que no inician sesión en Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-162">By using the content packs that are available in Microsoft Dynamics Lifecycle Services (LCS), you can provide great analytics to people who don't sign in to Microsoft Dynamics 365.</span></span> <span data-ttu-id="7b3ed-163">Puede modificar estos paquetes de contenido para que incluyan otros informes o representaciones visuales y, a continuación, publicar los paquetes de contenidos en el inquilino de Power BI.com para su análisis.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-163">You can modify these content packs so that they include other reports or visuals, and then publish the content packs to your Power BI.com tenant for analysis.</span></span> 

<span data-ttu-id="7b3ed-164">Puede encontrar el contenido de Power BI sobre **Análisis de compras y gastos** en la biblioteca de activos compartidos de LCS.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-164">You can find the **Purchase spend analysis** Power BI content in the Shared assets library in LCS.</span></span> <span data-ttu-id="7b3ed-165">Para obtener información sobre cómo descargar contenido e implementarlo en su organización, consulte [Contenido de Power BI en LCS en Microsoft y sus socios](power-bi-content-microsoft-partners.md).</span><span class="sxs-lookup"><span data-stu-id="7b3ed-165">For more information about how to download the content and implement it in your organization, see [Power BI content in LCS from Microsoft and your partners](power-bi-content-microsoft-partners.md).</span></span> <span data-ttu-id="7b3ed-166">Para ver una demostración que muestra cómo implementar el contenido de Power BI, consulte [Contenido de Power BI de Microsoft y sus socios en Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) (Office Mix).</span><span class="sxs-lookup"><span data-stu-id="7b3ed-166">To watch a demo that shows how to implement the Power BI content, see the [Power BI content from Microsoft and your partners in Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office Mix.</span></span>

<span data-ttu-id="7b3ed-167">Asegúrese de descargar el contenido **Análisis de compras y gastos** que se aplica a la versión de Dynamics 365 que esté usando.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-167">Be sure to download the **Purchase spend analysis** content that applies to the version of Dynamics 365 that you're using.</span></span>

> [!NOTE]
> <span data-ttu-id="7b3ed-168">Si utiliza Microsoft Dynamics 365 for Operations, versión 1611, KB 4011327 es un requisito para este contenido de Power BI.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-168">If you're using Microsoft Dynamics 365 for Operations version 1611, KB 4011327 is a prerequisite for this Power BI content.</span></span> <span data-ttu-id="7b3ed-169">Tras iniciar sesión en LCS, puede acceder a KB en https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-169">After you sign in to LCS, you can access the KB at https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.</span></span>

## <a name="data-model-and-entities"></a><span data-ttu-id="7b3ed-170">Modelo de datos y entidades</span><span class="sxs-lookup"><span data-stu-id="7b3ed-170">Data model and entities</span></span>
<span data-ttu-id="7b3ed-171">Los datos siguientes se usan para rellenar las páginas de informes en el contenido de Power BI sobre **Análisis de compras y gastos**.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-171">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="7b3ed-172">Estos datos se representan como medidas agregadas que se realizan en el almacén de la entidad.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-172">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="7b3ed-173">El almacén de la entidad es una base de datos de Microsoft SQL Server que se optimiza para el análisis.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-173">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="7b3ed-174">Para obtener más información, consulte [Visión general de la integración de Power BI con el almacén de entidades](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="7b3ed-174">For more information, see [Overview of Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="7b3ed-175">Las medidas agregadas en este contenido son el subconjunto de las medidas agregadas que estaban disponibles en el cubo de compra en Microsoft Dynamics AX 2012 y Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-175">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="7b3ed-176">Para realizar las medidas globales del cubo en el almacén de entidades debe hacer que sean desplegables.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-176">To stage the cube’s aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="7b3ed-177">Para obtener más información, consulte el procedimiento relativo a cómo realizar mediciones globales en el almacén de entidades en [Visión general de la integración de Power BI con el almacén de entidades](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="7b3ed-177">For more information, see the procedure for staging aggregate measurements in the Entity store in [Overview of Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="7b3ed-178">Las siguientes medidas agregadas clave están directamente disponibles en la entidad de líneas de factura y se usan como base del contenido.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-178">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="7b3ed-179">Entidad</span><span class="sxs-lookup"><span data-stu-id="7b3ed-179">Entity</span></span>        | <span data-ttu-id="7b3ed-180">Medidas agregadas clave</span><span class="sxs-lookup"><span data-stu-id="7b3ed-180">Key aggregate measurements</span></span> | <span data-ttu-id="7b3ed-181">Origen de datos</span><span class="sxs-lookup"><span data-stu-id="7b3ed-181">Data source</span></span>                                 | <span data-ttu-id="7b3ed-182">Campo</span><span class="sxs-lookup"><span data-stu-id="7b3ed-182">Field</span></span>              | <span data-ttu-id="7b3ed-183">Descripción</span><span class="sxs-lookup"><span data-stu-id="7b3ed-183">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="7b3ed-184">Líneas de factura</span><span class="sxs-lookup"><span data-stu-id="7b3ed-184">Invoice lines</span></span> | <span data-ttu-id="7b3ed-185">Compra</span><span class="sxs-lookup"><span data-stu-id="7b3ed-185">Purchase</span></span>                   | <span data-ttu-id="7b3ed-186">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="7b3ed-186">VendInvoiceTrans</span></span>                            | <span data-ttu-id="7b3ed-187">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="7b3ed-187">SUM(LineAmountMST)</span></span> | <span data-ttu-id="7b3ed-188">El importe en la divisa de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-188">The amount in the accounting currency.</span></span> |

<span data-ttu-id="7b3ed-189">En la tabla siguiente se muestran las medidas clave del contenido que se calculan a partir de la entidad de las líneas de factura.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-189">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="7b3ed-190">Medida</span><span class="sxs-lookup"><span data-stu-id="7b3ed-190">Measure</span></span>               | <span data-ttu-id="7b3ed-191">Cálculo</span><span class="sxs-lookup"><span data-stu-id="7b3ed-191">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="7b3ed-192">Año actual de compra</span><span class="sxs-lookup"><span data-stu-id="7b3ed-192">Purchase current year</span></span> | <span data-ttu-id="7b3ed-193">Año actual de compra = SUM('Líneas de factura'\[Compra\])</span><span class="sxs-lookup"><span data-stu-id="7b3ed-193">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="7b3ed-194">Compra el año pasado</span><span class="sxs-lookup"><span data-stu-id="7b3ed-194">Purchase last year</span></span>    | <span data-ttu-id="7b3ed-195">Compra el año pasado = CALCULATE(SUM('Líneas factura'\[Compra\]), SAMEPERIODLASTYEAR(Fechas\[Fecha\])</span><span class="sxs-lookup"><span data-stu-id="7b3ed-195">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="7b3ed-196">Crecimiento de compras interanual</span><span class="sxs-lookup"><span data-stu-id="7b3ed-196">YOY purchase growth</span></span>   | <span data-ttu-id="7b3ed-197">Crecimiento de compras interanual = \[Compra año actual\] – \[Compra el año pasado\]</span><span class="sxs-lookup"><span data-stu-id="7b3ed-197">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="7b3ed-198">Las dimensiones clave siguientes del contenido se utilizan como filtros para cortar las medidas globales para lograr mayor granularidad y profundizar en la visión analítica.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-198">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="7b3ed-199">Entidad</span><span class="sxs-lookup"><span data-stu-id="7b3ed-199">Entity</span></span>                 | <span data-ttu-id="7b3ed-200">Ejemplos de atributos</span><span class="sxs-lookup"><span data-stu-id="7b3ed-200">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="7b3ed-201">Empresas proveedoras</span><span class="sxs-lookup"><span data-stu-id="7b3ed-201">Vendors</span></span>                | <span data-ttu-id="7b3ed-202">Grupos de proveedores, países o regiones de proveedores, nombre del proveedor</span><span class="sxs-lookup"><span data-stu-id="7b3ed-202">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="7b3ed-203">Productos</span><span class="sxs-lookup"><span data-stu-id="7b3ed-203">Products</span></span>               | <span data-ttu-id="7b3ed-204">Número de producto, nombre de producto, nombre de grupos de artículos</span><span class="sxs-lookup"><span data-stu-id="7b3ed-204">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="7b3ed-205">Categorías de adquisición</span><span class="sxs-lookup"><span data-stu-id="7b3ed-205">Procurement categories</span></span> | <span data-ttu-id="7b3ed-206">Categoría de compras, nombres de la categoría de compras</span><span class="sxs-lookup"><span data-stu-id="7b3ed-206">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="7b3ed-207">Entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="7b3ed-207">Legal entities</span></span>         | <span data-ttu-id="7b3ed-208">Nombre de la entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="7b3ed-208">Legal entity name</span></span>                                     |
| <span data-ttu-id="7b3ed-209">Fechas</span><span class="sxs-lookup"><span data-stu-id="7b3ed-209">Dates</span></span>                  | <span data-ttu-id="7b3ed-210">Fechas, contrapartida anual</span><span class="sxs-lookup"><span data-stu-id="7b3ed-210">Dates, Year offset</span></span>                                    |

<span data-ttu-id="7b3ed-211">De forma predeterminada, el contenido muestra los datos del año natural actual.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-211">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="7b3ed-212">Sin embargo, puede cambiar el filtro de la fecha en la sección de filtros de informe.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-212">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="7b3ed-213">También puede cambiar el filtro de empresa.</span><span class="sxs-lookup"><span data-stu-id="7b3ed-213">You can also change the company filter.</span></span>

