---
title: Realización de ajustes manuales en la previsión de línea base
description: Este tema explica cómo puede realizar ajustes manuales a una previsión de línea base y ver los detalles de la previsión.
author: roxanadiaconu
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 72704
ms.assetid: e7c5d44e-07bc-40b1-a4b3-8ba46483ef9e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8897e0fe01e7ed5af9a8d5b99de6b9b4506554f1
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2019
ms.locfileid: "2815143"
---
# <a name="make-manual-adjustments-to-the-baseline-forecast"></a><span data-ttu-id="61fe1-103">Realización de ajustes manuales en la previsión de línea base</span><span class="sxs-lookup"><span data-stu-id="61fe1-103">Make manual adjustments to the baseline forecast</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="61fe1-104">Este tema explica cómo puede realizar ajustes manuales a una previsión de línea base y ver los detalles de la previsión.</span><span class="sxs-lookup"><span data-stu-id="61fe1-104">This topic explains how you can make manual adjustments to a baseline forecast and view details of the forecast.</span></span> 

<span data-ttu-id="61fe1-105">Antes de realizar ajustes manuales, es importante que entienda algunos conceptos en diversas páginas.</span><span class="sxs-lookup"><span data-stu-id="61fe1-105">Before you make manual adjustments, it's important that you understand a few concepts on various pages.</span></span>

## <a name="grid-on-the-adjusted-demand-forecast-page"></a><span data-ttu-id="61fe1-106">Cuadrícula en la página Previsión de la demanda ajustada</span><span class="sxs-lookup"><span data-stu-id="61fe1-106">Grid on the Adjusted demand forecast page</span></span>
<span data-ttu-id="61fe1-107">La página **Previsión de la demanda ajustada** incluye una cuadrícula con la estructura siguiente:</span><span class="sxs-lookup"><span data-stu-id="61fe1-107">The **Adjusted demand forecast** page includes a grid that has the following structure:</span></span>

-   <span data-ttu-id="61fe1-108">La primera columna muestra los artículos, las claves de asignación de artículos, empresas, etc., para los que se ha generado la previsión.</span><span class="sxs-lookup"><span data-stu-id="61fe1-108">The first column shows the items, item allocation keys, companies, and so on, that the forecast has been generated for.</span></span> <span data-ttu-id="61fe1-109">El subtítulo de la página ofrece una descripción de las dimensiones de previsión actuales que se muestran en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="61fe1-109">The subtitle of the page provides a description of the current forecast dimensions that are shown in the grid.</span></span> <span data-ttu-id="61fe1-110">Por ejemplo, si el subtítulo de la página es **Empresa / Sitio / Clave de asignación de artículos**, y uno de los encabezados de la fila en la cuadrícula es **USMF / 1 / D\_Alloc**, esa fila muestra la previsión para la empresa USMF, sitio 1 y clave de asignación de artículos **D\_Alloc**.</span><span class="sxs-lookup"><span data-stu-id="61fe1-110">For example, if the subtitle of the page is **Company / Site / Item allocation key**, and one of the row headers in the grid is **USMF / 1 / D\_Alloc**, that row shows the forecast for the USMF company, site 1, and the **D\_Alloc** item allocation key.</span></span>
-   <span data-ttu-id="61fe1-111">Las columnas siguientes representan los cubos de previsión para los que se ha generado la previsión.</span><span class="sxs-lookup"><span data-stu-id="61fe1-111">Subsequent columns represent the forecast buckets that the forecast has been generated for.</span></span> <span data-ttu-id="61fe1-112">Cada encabezado de columna es la primera fecha del cubo de previsión que la columna muestra.</span><span class="sxs-lookup"><span data-stu-id="61fe1-112">Each column header is the first date of the forecast bucket that the column shows.</span></span>
-   <span data-ttu-id="61fe1-113">Los valores de las celdas representan la previsión para un artículo, una clave de asignación de artículos, etc., para dicho cubo específico de previsión.</span><span class="sxs-lookup"><span data-stu-id="61fe1-113">The values in the cells represent the forecast for one item, item allocation key, and so on, for that specific forecast bucket.</span></span>

## <a name="forecast-aggregation-and-de-aggregation"></a><span data-ttu-id="61fe1-114">Agregación de inicio y agregación de previsión</span><span class="sxs-lookup"><span data-stu-id="61fe1-114">Forecast aggregation and de-aggregation</span></span>
<span data-ttu-id="61fe1-115">El subtítulo de la página muestra el nivel de agregación de previsión.</span><span class="sxs-lookup"><span data-stu-id="61fe1-115">The subtitle of the page shows the level of forecast aggregation.</span></span> 

<span data-ttu-id="61fe1-116">Por ejemplo, si el título de la página es **Empresa / Sitio / Clave de asignación / Número de artículo / Color / Tamaño / Configuración / Estilo**, no hay agregación de previsión, y la previsión se muestra en el nivel del artículo y sus dimensiones.</span><span class="sxs-lookup"><span data-stu-id="61fe1-116">For example, if the subtitle of the page is **Company / Site / Allocation key / Item number / Color / Size / Configuration / Style**, there is no forecast aggregation, and the forecast is shown at the level of the item and its dimensions.</span></span> <span data-ttu-id="61fe1-117">Para cambiar la agregación, use la página **Cambiar las dimensiones de previsión**, que puede abrir desde el menú de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="61fe1-117">To change the aggregation, use the **Change forecast dimensions** page, which you can open from the application menu.</span></span> 

<span data-ttu-id="61fe1-118">Para modificar la previsión, haga clic en una de las celdas disponibles, y especifique el valor ajustado de previsión.</span><span class="sxs-lookup"><span data-stu-id="61fe1-118">To modify the forecast, click in any of the cells that are available, and type the adjusted forecast value.</span></span> <span data-ttu-id="61fe1-119">La celda corregida pasa a estar en negrita inmediatamente para indicar que la previsión que muestra no es la previsión creada por el servicio de previsión de demanda, sino que se ha ajustado manualmente.</span><span class="sxs-lookup"><span data-stu-id="61fe1-119">The edited cell immediately becomes bold to indicate that the forecast that it shows isn't the forecast that the demand forecasting service created, but has been manually adjusted.</span></span> 

<span data-ttu-id="61fe1-120">Si cambia la agregación para hacer que la página muestre más datos agregados, puede usar la página **Líneas de previsión de la demanda** para ver las líneas de previsión individuales que constituyen la previsión agregada.</span><span class="sxs-lookup"><span data-stu-id="61fe1-120">If you change the aggregation to make the page show more aggregated data, you can use the **Demand forecast lines** page to see the individual forecast lines that make up the aggregated forecast.</span></span> 

<span data-ttu-id="61fe1-121">Por ejemplo, ha generado la previsión en el nivel de artículo, pero sabe que la demanda para este artículo aumentará en todos los sitios debido a una promoción u otro evento similar.</span><span class="sxs-lookup"><span data-stu-id="61fe1-121">For example, you've generated the forecast at the item level, but you know that the demand for this item will increase across all sites because of a promotion or another similar event.</span></span> <span data-ttu-id="61fe1-122">En este caso, puede establecer la agregación en **Empresa / Clave de asignación de artículos / Artículo** en la página **Cambiar las dimensiones de previsión**.</span><span class="sxs-lookup"><span data-stu-id="61fe1-122">In this case, you can set the aggregation to **Company / Item allocation key / Item** on the **Change forecast dimensions** page.</span></span> <span data-ttu-id="61fe1-123">Puede ajustar la previsión global para el artículo en todos los sitios en la cuadrícula **Previsión de la demanda ajustada**.</span><span class="sxs-lookup"><span data-stu-id="61fe1-123">You can adjust the global forecast for the item across all sites in the **Adjusted demand forecast** grid.</span></span> <span data-ttu-id="61fe1-124">Para ver el efecto del cambio a través de todos los sitios, abra la página **Líneas de previsión de la demanda**.</span><span class="sxs-lookup"><span data-stu-id="61fe1-124">To see the effect of your change across all sites, open the **Demand forecast lines** page.</span></span> <span data-ttu-id="61fe1-125">En esta página, verá una línea para el artículo para cada sitio, la cantidad ajustada de previsión y la cantidad original de la previsión.</span><span class="sxs-lookup"><span data-stu-id="61fe1-125">On this page, you will see one line for the item for each site, the adjusted forecast quantity, and the original forecast quantity.</span></span> 

<span data-ttu-id="61fe1-126">Cuando el ajuste de la cantidad prevista se realiza en un nivel agregado, el sistema usa la asignación ponderada para distribuir el cambio entre las líneas que crean la agregación.</span><span class="sxs-lookup"><span data-stu-id="61fe1-126">When the adjustment of the forecasted quantity is made at an aggregated level, the system uses weighted allocation to distribute the change among the lines that create the aggregation.</span></span> 

<span data-ttu-id="61fe1-127">También puede realizar ajustes manuales en la página **Líneas de previsión de la demanda**, modificando el valor **Cantidad total** o las celdas de **Cantidad** en la cuadrícula de agregación.</span><span class="sxs-lookup"><span data-stu-id="61fe1-127">You can also make manual adjustments on the **Demand forecast lines** page, by modifying either the **Total quantity** value or the **Quantity** cells in the de-aggregation grid.</span></span>

## <a name="viewing-details-of-the-forecast"></a><span data-ttu-id="61fe1-128">Visualización de los detalles de la previsión</span><span class="sxs-lookup"><span data-stu-id="61fe1-128">Viewing details of the forecast</span></span>
<span data-ttu-id="61fe1-129">Puede abrir la página **Detalles de previsión de la demanda** para ver más información acerca de la previsión.</span><span class="sxs-lookup"><span data-stu-id="61fe1-129">You can open the **Demand forecast details** page to view more information about the forecast.</span></span> 

<span data-ttu-id="61fe1-130">La página **Detalles de previsión de la demanda** muestra la siguiente información en un formato gráfico y tabular:</span><span class="sxs-lookup"><span data-stu-id="61fe1-130">The **Demand forecast details** page shows the following information in graphical and tabular formats:</span></span>

-   <span data-ttu-id="61fe1-131">La demanda histórica en las que se basan las predicciones de previsión.</span><span class="sxs-lookup"><span data-stu-id="61fe1-131">The historical demand that the forecast predictions are based on.</span></span>
-   <span data-ttu-id="61fe1-132">La previsión actual que usa la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="61fe1-132">The current forecast that is used by Master planning.</span></span>
-   <span data-ttu-id="61fe1-133">Los nuevos valores e importes de previsión de la demanda por los que se han ajustado manualmente.</span><span class="sxs-lookup"><span data-stu-id="61fe1-133">The new demand forecast values and the amounts they have been manually adjusted by.</span></span>
-   <span data-ttu-id="61fe1-134">El intervalo de confianza para los valores de previsión.</span><span class="sxs-lookup"><span data-stu-id="61fe1-134">The confidence interval for the forecasted values.</span></span>
-   <span data-ttu-id="61fe1-135">El modelo de previsión que se usó para generar la previsión.</span><span class="sxs-lookup"><span data-stu-id="61fe1-135">The forecast model that was used to generate the forecast.</span></span> <span data-ttu-id="61fe1-136">Si está viendo datos agregados, verá la lista de todos los métodos que se usaron para toda la serie de tiempo agregada.</span><span class="sxs-lookup"><span data-stu-id="61fe1-136">If you're viewing aggregated data, you will see the list of all the methods that were used for all the aggregated time series.</span></span>
-   <span data-ttu-id="61fe1-137">La precisión de modelo interna (MAPE).</span><span class="sxs-lookup"><span data-stu-id="61fe1-137">The internal model accuracy (MAPE).</span></span> <span data-ttu-id="61fe1-138">Para obtener más información acerca de la precisión de previsión, consulte [Seguimiento de la precisión de previsión](monitor-forecast-accuracy.md).</span><span class="sxs-lookup"><span data-stu-id="61fe1-138">For more information about forecast accuracy, see [Monitor forecast accuracy](monitor-forecast-accuracy.md).</span></span>

<span data-ttu-id="61fe1-139">**Notas:**</span><span class="sxs-lookup"><span data-stu-id="61fe1-139">**Notes:**</span></span>

-   <span data-ttu-id="61fe1-140">El intervalo de confianza que aparece en la sección **Previsión** de la página representa la diferencia entre el límite superior del intervalo de confianza y el límite inferior del intervalo de confianza.</span><span class="sxs-lookup"><span data-stu-id="61fe1-140">The confidence interval that appears in the **Forecast** section of the page represents the difference between the confidence interval upper limit and the confidence interval lower limit.</span></span> <span data-ttu-id="61fe1-141">Para ver los valores de los límites máximo y mínimo, pase el ratón por encima del gráfico en la sección **Demanda y previsión históricas gráficamente**.</span><span class="sxs-lookup"><span data-stu-id="61fe1-141">To see the values for the upper and lower limits, hover over the chart in the **Historical demand and forecast graphically** section.</span></span>
-   <span data-ttu-id="61fe1-142">Si utiliza el servicio de aprendizaje automático de Microsoft Azure Machine de previsión de demanda, puede especificar el porcentaje del nivel de confianza que debe tener la previsión que se genera.</span><span class="sxs-lookup"><span data-stu-id="61fe1-142">If you use the Demand forecasting Microsoft Azure Machine Learning service, you can specify the confidence level percentage that the forecast that is generated should have.</span></span> <span data-ttu-id="61fe1-143">Un intervalo de confianza consta de un intervalo de valores que actúan como estimaciones para la previsión de la demanda.</span><span class="sxs-lookup"><span data-stu-id="61fe1-143">A confidence interval consists of a range of values that act as good estimates for the demand forecast.</span></span> <span data-ttu-id="61fe1-144">Un porcentaje de nivel de confianza del 95 por ciento indica que hay un 5 por ciento de riesgo de que la previsión de la demanda se encuentre fuera del intervalo de confianza.</span><span class="sxs-lookup"><span data-stu-id="61fe1-144">A 95-percent confidence level percentage indicates that there is a 5-percent risk that the demand forecast falls outside the confidence interval range.</span></span>

<span data-ttu-id="61fe1-145">También puede realizar ajustes manuales en la previsión en la página **Detalles de previsión de la demanda**, modificando los valores en la fila **Previsión** en la sección **Previsión**.</span><span class="sxs-lookup"><span data-stu-id="61fe1-145">You can also make manual adjustments to the forecast on the **Demand forecast details** page, by modifying the values in the **Forecast** row in the **Forecast** section.</span></span>

<a name="additional-resources"></a><span data-ttu-id="61fe1-146">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="61fe1-146">Additional resources</span></span>
--------

[<span data-ttu-id="61fe1-147">Supervisión de la precisión de previsión</span><span class="sxs-lookup"><span data-stu-id="61fe1-147">Monitor forecast accuracy</span></span>](monitor-forecast-accuracy.md)

[<span data-ttu-id="61fe1-148">Generar previsión estadística de línea base</span><span class="sxs-lookup"><span data-stu-id="61fe1-148">Generate a statistical baseline forecast</span></span>](generate-statistical-baseline-forecast.md)



