---
title: Análisis de defectos de activos
description: Este tema explica el análisis de los defectos de activos en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 32cd8fb55cd9245a9a7c426a7c956bb40c3fdb0e
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383559"
---
# <a name="asset-fault-analysis"></a><span data-ttu-id="39004-103">Análisis de defectos de activos</span><span class="sxs-lookup"><span data-stu-id="39004-103">Asset fault analysis</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="39004-104">En Administración activos, puede analizar los registros de defectos del activo para obtener una visión general del número total de errores registrados durante un período específico.</span><span class="sxs-lookup"><span data-stu-id="39004-104">In Asset Management, you can analyze asset fault registrations to get an overview of the total number of faults registered during a specific period.</span></span> <span data-ttu-id="39004-105">Los registros de defectos se pueden analizar desde perspectivas diferentes, por ejemplo con el enfoque en los activos, los tipos de activos, las ubicaciones técnicas, los síntomas del error o los tipos de errores.</span><span class="sxs-lookup"><span data-stu-id="39004-105">Fault registrations can be analyzed from different perspectives, for example with focus on assets, asset types, functional locations, fault symptoms, or fault types.</span></span>

1. <span data-ttu-id="39004-106">Haga clic en **Administración de activos** > **Consultas** > **Defecto de activo** > **Análisis de los defectos de activos** para abrir la lista.</span><span class="sxs-lookup"><span data-stu-id="39004-106">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset fault analysis**.</span></span>

2. <span data-ttu-id="39004-107">En el diálogo **Cálculo del análisis de defectos de activos**, puede utilizar el campo **Nivel** para indicar el nivel de detalle que desea que tengan las líneas de defectos con respecto a las ubicaciones técnicas.</span><span class="sxs-lookup"><span data-stu-id="39004-107">In the **Asset fault analysis calculation** dialog, you can use the **Level** field to indicate how detailed you want the asset fault lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="39004-108">Por ejemplo, si especifica el número "1 "en el campo, y tiene una estructura de ubicación técnica de varios niveles, todas las líneas de defectos del activo para una ubicación técnica se mostrarán en el nivel superior, y por tanto, las horas en una línea se pueden agregar desde las ubicaciones técnicas ubicadas en un nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="39004-108">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all asset fault lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
        
    <span data-ttu-id="39004-109">Si especifica el número "0 "en el campo **Nivel** , verá un resultado detallado que muestra todas las líneas de defectos del activo en todo el nivel de la ubicación técnica con el que están relacionadas.</span><span class="sxs-lookup"><span data-stu-id="39004-109">If you insert the number "0" in the **Level** field, you will see a detailed result showing all asset fault lines on all the functional location level to which they are related.</span></span>

3. <span data-ttu-id="39004-110">Si desea limitar la búsqueda, puede seleccionar activos específicos, fechas de defectos, causas del defecto y soluciones para el defecto en la ficha desplegable **Registros a incluir**.</span><span class="sxs-lookup"><span data-stu-id="39004-110">If you want to limit the search, you can select specific assets, fault dates, fault causes, and fault remedies on the **Records to include** FastTab.</span></span>

4. <span data-ttu-id="39004-111">Haga clic en **Aceptar** para iniciar el cálculo.</span><span class="sxs-lookup"><span data-stu-id="39004-111">Click **OK** to start the calculation.</span></span>

5. <span data-ttu-id="39004-112">En la pestaña **Análisis de errores de activos**, haga clic en uno o más botones **Agrupar por…** para mostrar el nivel de detalle que desea ver.</span><span class="sxs-lookup"><span data-stu-id="39004-112">On the **Asset fault analysis** tab, click one or more **Group by** buttons to display the detail level you want to see.</span></span> <span data-ttu-id="39004-113">Se resaltarán los botones activados.</span><span class="sxs-lookup"><span data-stu-id="39004-113">Activated buttons are highlighted.</span></span> <span data-ttu-id="39004-114">Haga clic en los botones para activarlos o desactivarlos.</span><span class="sxs-lookup"><span data-stu-id="39004-114">Activate or deactivate buttons by clicking on them.</span></span>

6. <span data-ttu-id="39004-115">Haga clic en **Actualizar cálculos** para mostrar sus selecciones en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="39004-115">Click **Update calculations** to show your selections on the screen.</span></span> 

>[!NOTE]
><span data-ttu-id="39004-116">Cada vez que active o desactive un botón **Agrupar por**, recuerde hacer clic en el botón **Actualizar cálculos**.</span><span class="sxs-lookup"><span data-stu-id="39004-116">Every time you activate or deactivate a **Group by** button, remember to click the **Update calculations** button.</span></span> <span data-ttu-id="39004-117">Es obligatorio porque se procesan grandes cantidades de datos cuando se recalcula la probabilidad de defectos.</span><span class="sxs-lookup"><span data-stu-id="39004-117">This is required because a large amount of data is processed as you are recalculating fault probability.</span></span>

## <a name="examples"></a><span data-ttu-id="39004-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="39004-118">Examples</span></span>

<span data-ttu-id="39004-119">Existen varias maneras de analizar los registros de error.</span><span class="sxs-lookup"><span data-stu-id="39004-119">There are many ways to analyze fault registrations.</span></span> <span data-ttu-id="39004-120">Esta sección tiene cinco ejemplos de cómo distintas selecciones de datos pueden proporcionar más información y detalles al analizar los registros de errores de activos.</span><span class="sxs-lookup"><span data-stu-id="39004-120">This section has five examples of how different data selections can provide more insight and detail when analyzing asset fault registrations.</span></span>

### <a name="group-by-symptoms"></a><span data-ttu-id="39004-121">Agrupar por síntomas</span><span class="sxs-lookup"><span data-stu-id="39004-121">Group by symptoms</span></span>

<span data-ttu-id="39004-122">En el captura de pantalla abajo, solo se selecciona el botón **Síntoma**.</span><span class="sxs-lookup"><span data-stu-id="39004-122">In the screenshot below, only the **Symptom** button is selected.</span></span>

- <span data-ttu-id="39004-123">Los registros de defectos se han hecho sobre tres síntomas de defecto: "Escape de aire", "Fusible fundido", y "Equipo atascado".</span><span class="sxs-lookup"><span data-stu-id="39004-123">Fault registrations have been made on three fault symptoms: "Air leak", "Blown fuse", and "Equipment jammed".</span></span>  
- <span data-ttu-id="39004-124">En la columna **Porcentaje de probabilidad**, todos porcentajes suman 100 %.</span><span class="sxs-lookup"><span data-stu-id="39004-124">In the **Probability %** column, all percentages add up to 100%.</span></span> <span data-ttu-id="39004-125">La probabilidad se basa en todos los registros de **Síntoma** en este análisis de defectos.</span><span class="sxs-lookup"><span data-stu-id="39004-125">Probability is based on all **Symptom** registrations in this fault analysis.</span></span>

![Figura 1](media/06-controlling-and-reporting.png)

### <a name="group-by-symptoms-and-time-period"></a><span data-ttu-id="39004-127">Agrupar por síntomas y período de tiempo</span><span class="sxs-lookup"><span data-stu-id="39004-127">Group by symptoms and time period</span></span>

<span data-ttu-id="39004-128">En el captura de pantalla de abajo, **Año** y **Mes** se agregan para mostrar cómo puede ver los registros de defectos durante un período seleccionado.</span><span class="sxs-lookup"><span data-stu-id="39004-128">In the screenshot below, **Year** and **Month** are added to show how you can view fault registrations during a selected period.</span></span>

- <span data-ttu-id="39004-129">Los síntomas de los defectos ahora se mostrarán a modo de registros de año/mes.</span><span class="sxs-lookup"><span data-stu-id="39004-129">The fault symptoms are now shown as registrations per year/month.</span></span>  
- <span data-ttu-id="39004-130">En la columna **Porcentaje de probabilidad**, si agrega todos los porcentajes de cada mes, sumarán 100 %.</span><span class="sxs-lookup"><span data-stu-id="39004-130">In the **Probability %** column, if you add all percentages for each month, they add up to 100%.</span></span> <span data-ttu-id="39004-131">La probabilidad se basa en todos los registros de **Síntoma** en este análisis de defectos.</span><span class="sxs-lookup"><span data-stu-id="39004-131">Probability is based on the **Symptom** registrations in this fault analysis.</span></span> <span data-ttu-id="39004-132">Si tiene un gran número de líneas en un activo, pero resalta un gran porcentaje en una línea, sería una indicación de síntoma de defecto que se debe examinar con más detenimiento para encontrar una forma de limitar el número de registros para dicho síntoma del defecto.</span><span class="sxs-lookup"><span data-stu-id="39004-132">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault symptom to examine more closely to find a way to limit the number of registrations for that fault symptom.</span></span>

![Figura 2](media/07-controlling-and-reporting.png)

### <a name="group-by-multiple-symptoms-and-assets"></a><span data-ttu-id="39004-134">Agrupar por múltiples síntomas y activos</span><span class="sxs-lookup"><span data-stu-id="39004-134">Group by multiple symptoms and assets</span></span>

<span data-ttu-id="39004-135">La combinación de activos y un tipo de activo se usará como base para los cálculos mostrados en las tres capturas de pantalla de más abajo, que incrementarán el nivel de detalle.</span><span class="sxs-lookup"><span data-stu-id="39004-135">The combination of assets and an asset type is used as a basis for the calculations shown in the three screenshots below, which will increase in detail level.</span></span>  

<span data-ttu-id="39004-136">Normalmente, los botones en los grupos del panel Acciones **Agrupar por fecha**, **Agrupar por activo** y **Agrupar por ubicación técnica**, así como el botón **Error** (id. de error), contienen períodos o relaciones de activos.</span><span class="sxs-lookup"><span data-stu-id="39004-136">Generally, the buttons in the **Group by date**, **Group by asset**, **Group by functional location** Action Pane groups, as well as the **Fault** button (Fault ID), contain periods or asset relations.</span></span> <span data-ttu-id="39004-137">Los botones **Síntoma**, **Área**, **Tipo**, **Causa** y **Remedio** son clasificaciones utilizadas en la administración de defectos para analizar los registros de defectos del activo e identificar las áreas problemáticas.</span><span class="sxs-lookup"><span data-stu-id="39004-137">The **Symptom**, **Area**, **Type**, **Cause**, and **Remedy** buttons are categorizations used in fault management to analyze asset fault registrations and pinpoint problem areas.</span></span>  

<span data-ttu-id="39004-138">**Agrupar por síntoma, activo y tipo de activo**</span><span class="sxs-lookup"><span data-stu-id="39004-138">**Group by symptom, asset, and asset type**</span></span>

<span data-ttu-id="39004-139">En el captura de pantalla de abajo, **Activo** y **Tipo de activo** se han agregado para proporcionar más detalle en relación con los registros de defectos.</span><span class="sxs-lookup"><span data-stu-id="39004-139">In the screenshot below, **Asset** and **Asset type** were added to provide more detail regarding fault registrations.</span></span>

- <span data-ttu-id="39004-140">Los síntomas de error ahora se dividen en las combinaciones **Activo** / **Tipo de activo** / **Síntoma**.</span><span class="sxs-lookup"><span data-stu-id="39004-140">The fault symptoms are now split up in **Asset** / **Asset type** / **Symptom** combinations.</span></span>  
- <span data-ttu-id="39004-141">En la columna **Porcentaje de probabilidad**, si suma todos los porcentajes para la combinación **Activo** / **Tipo de activo** / **Síntoma** respectivamente, cada uno de ellos sumará 100 %.</span><span class="sxs-lookup"><span data-stu-id="39004-141">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** respectively, they each add up to 100%.</span></span> <span data-ttu-id="39004-142">La probabilidad se basa en todos los registros de **Síntoma** en este análisis de defectos.</span><span class="sxs-lookup"><span data-stu-id="39004-142">Probability is based on **Symptom** registrations in this fault analysis.</span></span> <span data-ttu-id="39004-143">Si tiene un gran número de líneas en un activo, pero resalta un gran porcentaje en una línea, sería una indicación de síntoma de defecto que se debe examinar con más detenimiento para encontrar una forma de limitar el número de registros para dicho síntoma del defecto.</span><span class="sxs-lookup"><span data-stu-id="39004-143">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault symptom to examine more closely to find a way to limit the number of registrations for that fault symptom.</span></span>

![Figura 3](media/08-controlling-and-reporting.png)

<span data-ttu-id="39004-145">**Agrupar por dos síntomas, activo y tipo de activo**</span><span class="sxs-lookup"><span data-stu-id="39004-145">**Group by two symptoms, asset, and asset type**</span></span>

<span data-ttu-id="39004-146">En el captura de pantalla de abajo, **Área** se agregó a **Síntoma**, **Activo** y **Tipo de activo** para proporcionar más detalle en relación con los registros de defectos.</span><span class="sxs-lookup"><span data-stu-id="39004-146">In the screenshot below, **Area** was added to **Symptom**, **Asset**, and **Asset type** to provide more detail regarding fault registrations.</span></span>

- <span data-ttu-id="39004-147">En la columna **Porcentaje de probabilidad**, si suma todos los porcentajes para la combinación **Activo** / **Tipo de activo** / **Síntoma** en un activo, cada uno de ellos sumará 100 %.</span><span class="sxs-lookup"><span data-stu-id="39004-147">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** on an asset, they each add up to 100%.</span></span> <span data-ttu-id="39004-148">La probabilidad se basa en la combinación de **Síntoma** y **Área** en este análisis de defectos.</span><span class="sxs-lookup"><span data-stu-id="39004-148">Probability is based on the combination of **Symptom** and **Area** in this fault analysis.</span></span> <span data-ttu-id="39004-149">Si tiene un gran número de líneas en un activo, pero resalta un gran porcentaje en una línea, sería una indicación de área de defecto que se debe examinar con más detenimiento para encontrar una forma de limitar el número de registros para dicha área del defecto.</span><span class="sxs-lookup"><span data-stu-id="39004-149">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault area to examine more closely to find a way to limit the number of registrations for that fault area.</span></span>  

![Figura 4](media/09-controlling-and-reporting.png)

<span data-ttu-id="39004-151">**Agrupar por tres síntomas, activo y tipo de activo**</span><span class="sxs-lookup"><span data-stu-id="39004-151">**Group by three symptom, asset, and asset type**</span></span>

<span data-ttu-id="39004-152">En el captura de pantalla de abajo, **Tipo** se ha agregado y se muestra el cálculo más detallados de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="39004-152">In the screenshot below, **Type** was added, and the most detailed calculation in this example is shown.</span></span>
 
- <span data-ttu-id="39004-153">En la columna **Porcentaje de probabilidad**, si suma todos los porcentajes para la combinación **Activo** / **Tipo de activo** / **Síntoma** en un activo, cada uno de ellos sumará 100 %.</span><span class="sxs-lookup"><span data-stu-id="39004-153">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** on an asset, they each add up to 100%.</span></span> <span data-ttu-id="39004-154">La probabilidad se basa en la combinación de **Síntoma**, **Área** y **Tipo** en este análisis de defectos.</span><span class="sxs-lookup"><span data-stu-id="39004-154">Probability is based on the combination of **Symptom**, **Area**, and **Type** in this fault analysis.</span></span> <span data-ttu-id="39004-155">Si tiene un gran número de líneas en un activo, pero resalta un gran porcentaje en una línea, sería una indicación de tipo de defecto que se debe examinar con más detenimiento para encontrar una forma de limitar el número de registros para dicho tipo del defecto.</span><span class="sxs-lookup"><span data-stu-id="39004-155">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault type to examine more closely to find a way to limit the number of registrations on that fault type.</span></span>

![Figura 5](media/10-controlling-and-reporting.png)


>[!NOTE]
><span data-ttu-id="39004-157">Para obtener una visión general de todos los registros de defecto creados en las órdenes de trabajo y solicitudes de mantenimiento, haga clic en **Administración de activos** > **Consultas** > **Defecto de activo** > **Defectos de activos**.</span><span class="sxs-lookup"><span data-stu-id="39004-157">For an overview of all fault registrations created on work orders and maintenance requests, click **Asset management** > **Inquiries** > **Asset fault** > **Asset faults**.</span></span> <span data-ttu-id="39004-158">En la página **Defectos activo** , seleccione un registro de defectos de activo y expanda el panel **Información relacionada** para ver la información relativa a la orden de trabajo o a la solicitud de mantenimiento relacionadas.</span><span class="sxs-lookup"><span data-stu-id="39004-158">On the **Asset faults** page, select an asset fault registration and expand the **Related information** pane to see information regarding the related work order or maintenance request.</span></span>

