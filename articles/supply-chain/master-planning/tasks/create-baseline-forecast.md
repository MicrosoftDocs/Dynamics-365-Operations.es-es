---
title: 'Guía: Crear una previsión de línea base'
description: Un planificador de producción puede crear una previsión de línea base usando modelos de previsión de series temporales o copiando la demanda histórica.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup, ReqIntercompanyPlanningGroupAllocKeys, ReqDemPlanForecastParameters, ReqDemPlanCreateForecastDialog, SysQueryForm, ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 95a20b30827c9096dd8d8f67d149305cf594ff05
ms.sourcegitcommit: 15aacd0e109b05c7281407b5bba4e6cd99116c28
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "6223971"
---
# <a name="guide-create-a-baseline-forecast"></a><span data-ttu-id="973bf-103">Guía: Crear una previsión de línea base</span><span class="sxs-lookup"><span data-stu-id="973bf-103">Guide: Create a baseline forecast</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="973bf-104">Un planificador de producción puede crear una previsión de línea base usando modelos de previsión de series temporales o copiando la demanda histórica.</span><span class="sxs-lookup"><span data-stu-id="973bf-104">A production planner can create a baseline forecast either by using time series forecast models or by copying the historical demand.</span></span> <span data-ttu-id="973bf-105">Este procedimiento muestra cómo copiar una demanda histórica para crear una previsión de línea base para todos los productos mediante una clave de asignación de artículos.</span><span class="sxs-lookup"><span data-stu-id="973bf-105">This procedure shows how to copy the historical demand to create a baseline forecast for all products using one item allocation key.</span></span>

## <a name="set-up-an-item-allocation-key"></a><span data-ttu-id="973bf-106">Configurar clave de asignación de artículos</span><span class="sxs-lookup"><span data-stu-id="973bf-106">Set up an item allocation key</span></span>

1. <span data-ttu-id="973bf-107">Vaya a **Planificación maestra > Configuración > Grupos de planificación de empresas vinculadas**.</span><span class="sxs-lookup"><span data-stu-id="973bf-107">Go to **Master planning > Setup > Intercompany planning groups**.</span></span>
2. <span data-ttu-id="973bf-108">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="973bf-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="973bf-109">Por ejemplo, aplique un filtro en el campo *Nombre* con un valor de *10*.</span><span class="sxs-lookup"><span data-stu-id="973bf-109">For example, filter on the *Name* field with a value of *10*.</span></span>
    * <span data-ttu-id="973bf-110">La previsión de demanda se aplica a distintas entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="973bf-110">Demand forecasting runs across legal entities.</span></span> <span data-ttu-id="973bf-111">Esta es la razón por la que necesita configurar todas las empresas para las que desea generar previsiones en un grupo de planificación de empresas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="973bf-111">That's why you need to set up all the companies for which you want to generate forecasts in one intercompany planning group.</span></span>  
3. <span data-ttu-id="973bf-112">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="973bf-112">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="973bf-113">Seleccionar **Clave de asignación de artículos**.</span><span class="sxs-lookup"><span data-stu-id="973bf-113">Select **Item allocation keys**.</span></span>
    * <span data-ttu-id="973bf-114">Seleccione todas las claves de asignación de artículos para las que desea crear previsiones.</span><span class="sxs-lookup"><span data-stu-id="973bf-114">Select all the item allocation keys for which you want to create forecasts.</span></span>  
5. <span data-ttu-id="973bf-115">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="973bf-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="973bf-116">Seleccione la clave de asignación de artículos D_Aloc.</span><span class="sxs-lookup"><span data-stu-id="973bf-116">Select D_Aloc item allocation key.</span></span>  
6. <span data-ttu-id="973bf-117">Seleccionar **>**.</span><span class="sxs-lookup"><span data-stu-id="973bf-117">Select **>**.</span></span>
7. <span data-ttu-id="973bf-118">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="973bf-118">Close the page.</span></span>
8. <span data-ttu-id="973bf-119">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="973bf-119">Close the page.</span></span>

## <a name="set-up-the-demand-forecasting-parameters"></a><span data-ttu-id="973bf-120">Configuración de parámetros de previsión de demanda</span><span class="sxs-lookup"><span data-stu-id="973bf-120">Set up the demand forecasting parameters</span></span>

1. <span data-ttu-id="973bf-121">Vaya a **Planificación maestra > Configuración > Previsión de demanda > Parámetros de previsión de la demanda**.</span><span class="sxs-lookup"><span data-stu-id="973bf-121">Go to **Master planning > Setup > Demand forecasting > Demand forecasting parameters**.</span></span>
2. <span data-ttu-id="973bf-122">Expanda la sección **Parámetros de algoritmo de previsión**.</span><span class="sxs-lookup"><span data-stu-id="973bf-122">Expand the **Forecast algorithm parameters** section.</span></span>
3. <span data-ttu-id="973bf-123">En el campo **Estrategia de generación de previsión**, seleccione **Copiar sobre demanda histórica**.</span><span class="sxs-lookup"><span data-stu-id="973bf-123">In the **Forecast generation strategy** field, select **Copy over historical demand**.</span></span>
4. <span data-ttu-id="973bf-124">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="973bf-124">Select **Save**.</span></span>

## <a name="create-a-baseline-forecast"></a><span data-ttu-id="973bf-125">Crear una previsión de línea base</span><span class="sxs-lookup"><span data-stu-id="973bf-125">Create a baseline forecast</span></span>

1. <span data-ttu-id="973bf-126">Vaya a **Planificación maestra > Previsión > Previsión de demanda > Generar previsión estadística de línea base**.</span><span class="sxs-lookup"><span data-stu-id="973bf-126">Go to **Master planning > Forecasting > Demand forecasting > Generate statistical baseline forecast**.</span></span>
2. <span data-ttu-id="973bf-127">En el campo **Fecha inicial**, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="973bf-127">In the **From date** field, enter a date.</span></span>
    * <span data-ttu-id="973bf-128">Si tiene pedidos de ventas que comiencen a partir del 1 de enero de 2015, especifique esta fecha.</span><span class="sxs-lookup"><span data-stu-id="973bf-128">If you have sales orders starting from January 1, 2015, enter this date.</span></span> <span data-ttu-id="973bf-129">Si no, especifique la fecha más temprana de sus pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="973bf-129">If you don't, enter the earliest date of your sales orders.</span></span>  
3. <span data-ttu-id="973bf-130">En el campo **Fecha final**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="973bf-130">In the **To date** field, enter a date.</span></span>
    * <span data-ttu-id="973bf-131">Escriba la última fecha de sus pedidos de ventas, por ejemplo, *31-03-2015*.</span><span class="sxs-lookup"><span data-stu-id="973bf-131">Enter the last date of your sales orders, for example *2015-03-31*.</span></span>  
4. <span data-ttu-id="973bf-132">En el campo **Fecha inicial**, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="973bf-132">In the **From date** field, enter a date.</span></span>
    * <span data-ttu-id="973bf-133">Especifique *01-04-2015*.</span><span class="sxs-lookup"><span data-stu-id="973bf-133">Enter *2015-04-01*.</span></span> <span data-ttu-id="973bf-134">Esta fecha se calcula automáticamente como la fecha inicial del siguiente de depósito de previsión.</span><span class="sxs-lookup"><span data-stu-id="973bf-134">This date will be automatically calculated as the start date of the next forecasting bucket.</span></span>  
5. <span data-ttu-id="973bf-135">Expanda la sección **Registros que incluir**.</span><span class="sxs-lookup"><span data-stu-id="973bf-135">Expand the **Records to include** section.</span></span>
6. <span data-ttu-id="973bf-136">Seleccione **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="973bf-136">Select **Filter**.</span></span>
7. <span data-ttu-id="973bf-137">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="973bf-137">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="973bf-138">Marque la fila en la que **Campo** = *Grupo de planificación de empresas vinculadas*.</span><span class="sxs-lookup"><span data-stu-id="973bf-138">Mark the row where **Field** = *Intercompany planning group*.</span></span>  
8. <span data-ttu-id="973bf-139">En el campo **Criterios**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="973bf-139">In the **Criteria** field, type a value.</span></span>
    * <span data-ttu-id="973bf-140">Escriba el grupo de planificación de empresas vinculadas (por ejemplo, *10*), que usó en la primera tarea.</span><span class="sxs-lookup"><span data-stu-id="973bf-140">Type the intercompany planning group (for example, *10*) that you used in the first task.</span></span>  
9. <span data-ttu-id="973bf-141">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="973bf-141">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="973bf-142">Seleccione la fila en la que **Campo** = *Clave de asignación de artículos*.</span><span class="sxs-lookup"><span data-stu-id="973bf-142">Select the row where **Field** = *Item allocation key*.</span></span>  
10. <span data-ttu-id="973bf-143">En el campo **Criterios**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="973bf-143">In the **Criteria** field, type a value.</span></span>
11. <span data-ttu-id="973bf-144">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="973bf-144">Select **OK**.</span></span>
12. <span data-ttu-id="973bf-145">Expanda la sección **Parámetros avanzados**.</span><span class="sxs-lookup"><span data-stu-id="973bf-145">Expand the **Advanced parameters** section.</span></span>
13. <span data-ttu-id="973bf-146">En el campo **Depósito de previsión**, seleccione *Mes*.</span><span class="sxs-lookup"><span data-stu-id="973bf-146">In the **Forecast bucket** field, select *Month*.</span></span>
14. <span data-ttu-id="973bf-147">En el campo **Horizonte de previsión**, indique *3*.</span><span class="sxs-lookup"><span data-stu-id="973bf-147">In the **Forecast horizon** field, enter *3*.</span></span>
15. <span data-ttu-id="973bf-148">En el campo **Congelar límite de tiempo**, indique *1*.</span><span class="sxs-lookup"><span data-stu-id="973bf-148">In the **Freeze time fence** field, enter *1*.</span></span>
16. <span data-ttu-id="973bf-149">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="973bf-149">Select **OK**.</span></span>

## <a name="visualize-the-demand-forecast"></a><span data-ttu-id="973bf-150">Visualización de la previsión de demanda</span><span class="sxs-lookup"><span data-stu-id="973bf-150">Visualize the demand forecast</span></span>

1. <span data-ttu-id="973bf-151">Vaya a **Planificación maestra > Previsión > Previsión de demanda > Previsión de la demanda ajustada**.</span><span class="sxs-lookup"><span data-stu-id="973bf-151">Go to **Master planning > Forecasting > Demand forecasting > Adjusted demand forecast**.</span></span>
2. <span data-ttu-id="973bf-152">En la tabla de vista agregada, seleccione la celda de la fila 1, columna 2.</span><span class="sxs-lookup"><span data-stu-id="973bf-152">In the aggregated view table, select the cell in row 1, column 2.</span></span> <span data-ttu-id="973bf-153">Este es el segundo mes para el que ha creado previsión.</span><span class="sxs-lookup"><span data-stu-id="973bf-153">This is the second month for which you have created forecast.</span></span>
3. <span data-ttu-id="973bf-154">Defina **QtyCell** en *400*.</span><span class="sxs-lookup"><span data-stu-id="973bf-154">Set **QtyCell** to *400*.</span></span>
    * <span data-ttu-id="973bf-155">En la celda, especifique un número distinto al previsto, por ejemplo, 400.</span><span class="sxs-lookup"><span data-stu-id="973bf-155">In the cell, enter a different number than the one that was forecasted, for example, 400.</span></span>  
4. <span data-ttu-id="973bf-156">Ha realizado un ajuste manual en la previsión.</span><span class="sxs-lookup"><span data-stu-id="973bf-156">You have made a manual adjustment to the forecast.</span></span> <span data-ttu-id="973bf-157">Observe la indicación gráfica en el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="973bf-157">Notice the graphical indication in the next step.</span></span>
5. <span data-ttu-id="973bf-158">Seleccione **Detalles de línea de previsión**.</span><span class="sxs-lookup"><span data-stu-id="973bf-158">Select **Forecast line details**.</span></span>
    * <span data-ttu-id="973bf-159">En esta página puede ver los valores de precisión, la demanda histórica y la previsión.</span><span class="sxs-lookup"><span data-stu-id="973bf-159">In this page, you can see the accuracy values, historical demand, and forecast.</span></span> <span data-ttu-id="973bf-160">También puede modificar la previsión.</span><span class="sxs-lookup"><span data-stu-id="973bf-160">You can make changes to the forecast as well.</span></span>  

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]