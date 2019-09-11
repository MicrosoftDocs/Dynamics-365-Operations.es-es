---
title: Análisis de defectos de activos
description: Este tema explica el análisis de los defectos de activos en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7c9330cc7b3a8839d94c8945418548033254786b
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918450"
---
# <a name="asset-fault-analysis"></a><span data-ttu-id="85f42-103">Análisis de defectos de activos</span><span class="sxs-lookup"><span data-stu-id="85f42-103">Asset fault analysis</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="85f42-104">En Administración activos, puede analizar los registros de defectos del activo para obtener una visión general del número total de errores registrados durante un período específico.</span><span class="sxs-lookup"><span data-stu-id="85f42-104">In Asset Management, you can analyze asset fault registrations to get an overview of the total number of faults registered during a specific period.</span></span> <span data-ttu-id="85f42-105">Los registros de defectos se pueden analizar desde perspectivas diferentes, por ejemplo con el enfoque en los activos, los tipos de activos, las ubicaciones técnicas, los síntomas del error o los tipos de errores.</span><span class="sxs-lookup"><span data-stu-id="85f42-105">Fault registrations can be analyzed from different perspectives, for example with focus on assets, asset types, functional locations, fault symptoms, or fault types.</span></span>

1. <span data-ttu-id="85f42-106">Haga clic en **Administración de activos** > **Consultas** > **Defecto de activo** > **Análisis de los defectos de activos** para abrir la lista.</span><span class="sxs-lookup"><span data-stu-id="85f42-106">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset fault analysis**.</span></span>

2. <span data-ttu-id="85f42-107">En el diálogo **Cálculo del análisis de defectos de activos**, puede utilizar el campo **Nivel** para indicar el nivel de detalle que desea que tengan las líneas de defectos con respecto a las ubicaciones técnicas.</span><span class="sxs-lookup"><span data-stu-id="85f42-107">In the **Asset fault analysis calculation** dialog, you can use the **Level** field to indicate how detailed you want the asset fault lines to be regarding functional locations.</span></span> <span data-ttu-id="85f42-108">Por ejemplo, si especifica el número "1 "en el campo, y tiene una estructura de ubicación técnica de varios niveles, todas las líneas de defectos del activo para una ubicación técnica se mostrarán en el nivel superior, y por tanto, las horas en una línea se pueden agregar desde las ubicaciones técnicas ubicadas en un nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="85f42-108">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all asset fault lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="85f42-109">Si especifica el número "0 "en el campo **Nivel** , verá un resultado detallado que muestra todas las líneas de defectos del activo en todo el nivel de la ubicación técnica con el que están relacionadas.</span><span class="sxs-lookup"><span data-stu-id="85f42-109">If you insert the number "0" in the **Level** field, you will see a detailed result showing all asset fault lines on all the functional location level to which they are related.</span></span>

3. <span data-ttu-id="85f42-110">Si desea limitar la búsqueda, puede seleccionar activos específicos, fechas de defectos, causas del defecto y soluciones para el defecto en la ficha desplegable **Registros a incluir**.</span><span class="sxs-lookup"><span data-stu-id="85f42-110">If you want to limit the search, you can select specific assets, fault dates, fault causes, and fault remedies on the **Records to include** FastTab.</span></span>

4. <span data-ttu-id="85f42-111">Haga clic en **Aceptar** para iniciar el cálculo.</span><span class="sxs-lookup"><span data-stu-id="85f42-111">Click **OK** to start the calculation.</span></span>

5. <span data-ttu-id="85f42-112">En la pestaña **Análisis de defectos de activos**, haga clic en uno o más botones de los grupos del panel de acciones **Agrupar por…** para mostrar el nivel de detalle que desea ver.</span><span class="sxs-lookup"><span data-stu-id="85f42-112">On the **Asset fault analysis** tab, click one or more buttons in the **Group by...** action pane groups to display the detail level you want to see.</span></span> <span data-ttu-id="85f42-113">Se resaltarán los botones activados.</span><span class="sxs-lookup"><span data-stu-id="85f42-113">Activated buttons are highlighted.</span></span> <span data-ttu-id="85f42-114">Haga clic en los botones para activarlos o desactivarlos.</span><span class="sxs-lookup"><span data-stu-id="85f42-114">Activate or deactivate buttons by clicking on them.</span></span>

6. <span data-ttu-id="85f42-115">Haga clic en **Actualizar cálculos** para mostrar sus selecciones en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="85f42-115">Click **Update calculations** to show your selections on the screen.</span></span> 

>[!NOTE]
><span data-ttu-id="85f42-116">Cada vez que activa o desactiva los botones de los grupos del panel de acciones **Agrupar por…**, recuerde hacer clic en el botón **Actualizar cálculos** después de que haya cambiado las selecciones.</span><span class="sxs-lookup"><span data-stu-id="85f42-116">Every time you activate or deactivate buttons in the **Group by...** action pane groups, remember to click the **Update calculations** button after you changed the selections.</span></span> <span data-ttu-id="85f42-117">Es obligatorio porque se procesan grandes cantidades de datos cuando se recalcula la probabilidad de defectos.</span><span class="sxs-lookup"><span data-stu-id="85f42-117">This is required because a large amount of data is processed as you are recalculating fault probability.</span></span>

<span data-ttu-id="85f42-118">Existen varias maneras de analizar los registros de error.</span><span class="sxs-lookup"><span data-stu-id="85f42-118">There are many ways to analyze fault registrations.</span></span> <span data-ttu-id="85f42-119">A continuación, verá ejemplos en cinco capturas de pantalla sobre cómo las distintas selecciones de datos proporcionan diferentes fragmentos de información.</span><span class="sxs-lookup"><span data-stu-id="85f42-119">Below you see examples in five screenshots of how different data selections provide different pieces of information.</span></span> <span data-ttu-id="85f42-120">Verá cómo distintas selecciones proporcionan más información y detalles al analizar los registros de defectos de activos.</span><span class="sxs-lookup"><span data-stu-id="85f42-120">You will see how different selections provide more insight and detail when analyzing asset fault registrations.</span></span>

<span data-ttu-id="85f42-121">En el captura de pantalla abajo, solo se selecciona el botón **Síntoma**.</span><span class="sxs-lookup"><span data-stu-id="85f42-121">In the screenshot below, only the **Symptom** button is selected.</span></span>

- <span data-ttu-id="85f42-122">Los registros de defectos se han hecho sobre tres síntomas de defecto: "Escape de aire", "Fusible fundido", y "Equipo atascado".</span><span class="sxs-lookup"><span data-stu-id="85f42-122">Fault registrations have been made on three fault symptoms: "Air leak", "Blown fuse", and "Equipment jammed".</span></span>  
- <span data-ttu-id="85f42-123">En la columna **Porcentaje de probabilidad**, todos porcentajes suman 100 %.</span><span class="sxs-lookup"><span data-stu-id="85f42-123">In the **Probability %** column, all percentages add up to 100%.</span></span> <span data-ttu-id="85f42-124">La probabilidad se basa en todos los registros de **Síntoma** en este análisis de defectos.</span><span class="sxs-lookup"><span data-stu-id="85f42-124">Probability is based on all **Symptom** registrations in this fault analysis.</span></span>

![Figura 1](media/06-controlling-and-reporting.png)


<span data-ttu-id="85f42-126">En el captura de pantalla de abajo, **Año** y **Mes** se agregan para mostrar cómo puede ver los registros de defectos durante un período seleccionado.</span><span class="sxs-lookup"><span data-stu-id="85f42-126">In the screenshot below, **Year** and **Month** are added to show how you can view fault registrations during a selected period.</span></span>

- <span data-ttu-id="85f42-127">Los síntomas de los defectos ahora se mostrarán a modo de registros de año/mes.</span><span class="sxs-lookup"><span data-stu-id="85f42-127">The fault symptoms are now shown as registrations per year/month.</span></span>  
- <span data-ttu-id="85f42-128">En la columna **Porcentaje de probabilidad**, si agrega todos los porcentajes de cada mes, sumarán 100 %.</span><span class="sxs-lookup"><span data-stu-id="85f42-128">In the **Probability %** column, if you add all percentages for each month, they add up to 100%.</span></span> <span data-ttu-id="85f42-129">La probabilidad se basa en todos los registros de **Síntoma** en este análisis de defectos.</span><span class="sxs-lookup"><span data-stu-id="85f42-129">Probability is based on the **Symptom** registrations in this fault analysis.</span></span> <span data-ttu-id="85f42-130">Si tiene un gran número de líneas en un activo, pero resalta un gran porcentaje en una línea, sería una indicación de síntoma de defecto que se debe examinar con más detenimiento para encontrar una forma de limitar el número de registros para dicho síntoma del defecto.</span><span class="sxs-lookup"><span data-stu-id="85f42-130">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault symptom to examine more closely to find a way to limit the number of registrations for that fault symptom.</span></span>

![Figura 2](media/07-controlling-and-reporting.png)


- <span data-ttu-id="85f42-132">La combinación de activos y un tipo de activo se usará como base para los cálculos mostrados en las tres capturas de pantalla de más abajo, que incrementarán el nivel de detalle.</span><span class="sxs-lookup"><span data-stu-id="85f42-132">The combination of assets and an asset type is used as a basis for the calculations shown in the three screenshots below, which will increase in detail level.</span></span>  
- <span data-ttu-id="85f42-133">Normalmente, los botones en los grupos del panel de acción **Agrupar por fecha**, **Agrupar por activo**, **Agrupar por ubicación técnica**, así como el botón **Defecto** (identificador del defecto), contienen períodos o relaciones de activo.</span><span class="sxs-lookup"><span data-stu-id="85f42-133">Generally, the buttons in the **Group by date**, **Group by asset**, **Group by functional location** action pane groups, as well as the **Fault** button (Fault ID), contain periods or asset relations.</span></span> <span data-ttu-id="85f42-134">Los botones **Síntoma**, **Área**, **Tipo**, **Causa** y **Remedio** son clasificaciones utilizadas en la administración de defectos para analizar los registros de defectos del activo e identificar las áreas problemáticas.</span><span class="sxs-lookup"><span data-stu-id="85f42-134">The **Symptom**, **Area**, **Type**, **Cause**, and **Remedy** buttons are categorizations used in fault management to analyze asset fault registrations and pinpoint problem areas.</span></span>  

<span data-ttu-id="85f42-135">En el captura de pantalla de abajo, **Activo** y **Tipo de activo** se han agregado para proporcionar más detalle en relación con los registros de defectos.</span><span class="sxs-lookup"><span data-stu-id="85f42-135">In the screenshot below, **Asset** and **Asset type** were added to provide more detail regarding fault registrations.</span></span>

- <span data-ttu-id="85f42-136">Los síntomas de error ahora se dividen en las combinaciones **Activo** / **Tipo de activo** / **Síntoma**.</span><span class="sxs-lookup"><span data-stu-id="85f42-136">The fault symptoms are now split up in **Asset** / **Asset type** / **Symptom** combinations.</span></span>  
- <span data-ttu-id="85f42-137">En la columna **Porcentaje de probabilidad**, si suma todos los porcentajes para la combinación **Activo** / **Tipo de activo** / **Síntoma** respectivamente, cada uno de ellos sumará 100 %.</span><span class="sxs-lookup"><span data-stu-id="85f42-137">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** respectively, they each add up to 100%.</span></span> <span data-ttu-id="85f42-138">La probabilidad se basa en todos los registros de **Síntoma** en este análisis de defectos.</span><span class="sxs-lookup"><span data-stu-id="85f42-138">Probability is based on **Symptom** registrations in this fault analysis.</span></span> <span data-ttu-id="85f42-139">Si tiene un gran número de líneas en un activo, pero resalta un gran porcentaje en una línea, sería una indicación de síntoma de defecto que se debe examinar con más detenimiento para encontrar una forma de limitar el número de registros para dicho síntoma del defecto.</span><span class="sxs-lookup"><span data-stu-id="85f42-139">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault symptom to examine more closely to find a way to limit the number of registrations for that fault symptom.</span></span>

![Figura 3](media/08-controlling-and-reporting.png)


<span data-ttu-id="85f42-141">En el captura de pantalla de abajo, **Área** se agregó a **Síntoma**, **Activo** y **Tipo de activo** para proporcionar más detalle en relación con los registros de defectos.</span><span class="sxs-lookup"><span data-stu-id="85f42-141">In the screenshot below, **Area** was added to **Symptom**, **Asset**, and **Asset type** to provide more detail regarding fault registrations.</span></span>

- <span data-ttu-id="85f42-142">En la columna **Porcentaje de probabilidad**, si suma todos los porcentajes para la combinación **Activo** / **Tipo de activo** / **Síntoma** en un activo, cada uno de ellos sumará 100 %.</span><span class="sxs-lookup"><span data-stu-id="85f42-142">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** on an asset, they each add up to 100%.</span></span> <span data-ttu-id="85f42-143">La probabilidad se basa en la combinación de **Síntoma** y **Área** en este análisis de defectos.</span><span class="sxs-lookup"><span data-stu-id="85f42-143">Probability is based on the combination of **Symptom** and **Area** in this fault analysis.</span></span> <span data-ttu-id="85f42-144">Si tiene un gran número de líneas en un activo, pero resalta un gran porcentaje en una línea, sería una indicación de área de defecto que se debe examinar con más detenimiento para encontrar una forma de limitar el número de registros para dicha área del defecto.</span><span class="sxs-lookup"><span data-stu-id="85f42-144">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault area to examine more closely to find a way to limit the number of registrations for that fault area.</span></span>  

![Figura 4](media/09-controlling-and-reporting.png)


<span data-ttu-id="85f42-146">En el captura de pantalla de abajo, **Tipo** se ha agregado y se muestra el cálculo más detallados de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="85f42-146">In the screenshot below, **Type** was added, and the most detailed calculation in this example is shown.</span></span>
 
- <span data-ttu-id="85f42-147">En la columna **Porcentaje de probabilidad**, si suma todos los porcentajes para la combinación **Activo** / **Tipo de activo** / **Síntoma** en un activo, cada uno de ellos sumará 100 %.</span><span class="sxs-lookup"><span data-stu-id="85f42-147">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** on an asset, they each add up to 100%.</span></span> <span data-ttu-id="85f42-148">La probabilidad se basa en la combinación de **Síntoma**, **Área** y **Tipo** en este análisis de defectos.</span><span class="sxs-lookup"><span data-stu-id="85f42-148">Probability is based on the combination of **Symptom**, **Area**, and **Type** in this fault analysis.</span></span> <span data-ttu-id="85f42-149">Si tiene un gran número de líneas en un activo, pero resalta un gran porcentaje en una línea, sería una indicación de tipo de defecto que se debe examinar con más detenimiento para encontrar una forma de limitar el número de registros para dicho tipo del defecto.</span><span class="sxs-lookup"><span data-stu-id="85f42-149">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault type to examine more closely to find a way to limit the number of registrations on that fault type.</span></span>

![Figura 5](media/10-controlling-and-reporting.png)


>[!NOTE]
><span data-ttu-id="85f42-151">Para obtener una visión general de todos los registros de defecto creados en las órdenes de trabajo y solicitudes de mantenimiento, haga clic en **Administración de activos** > **Consultas** > **Defecto de activo** > **Defectos de activos**.</span><span class="sxs-lookup"><span data-stu-id="85f42-151">For an overview of all fault registrations created on work orders and maintenance requests, click **Asset management** > **Inquiries** > **Asset fault** > **Asset faults**.</span></span> <span data-ttu-id="85f42-152">En la página **Defectos activo** , seleccione un registro de defectos de activo y expanda el panel **Información relacionada** para ver la información relativa a la orden de trabajo o a la solicitud de mantenimiento relacionadas.</span><span class="sxs-lookup"><span data-stu-id="85f42-152">On the **Asset faults** page, select an asset fault registration and expand the **Related information** pane to see information regarding the related work order or maintenance request.</span></span>

