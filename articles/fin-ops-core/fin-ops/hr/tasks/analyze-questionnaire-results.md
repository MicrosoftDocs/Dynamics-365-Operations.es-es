---
title: Analizando los resultados del cuestionario
description: Las estadísticas de cuestionario se pueden usar para calcular promedios, totales y porcentajes basados en un sistema de datos demográficos.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMQuestionnaireStatistics, KMQuestionnaireStatisticsLine
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2d8f9c2fcf0be117f8fcde5113c0d42f11786679
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179893"
---
# <a name="analyzing-questionnaire-results"></a><span data-ttu-id="67928-103">Analizando los resultados del cuestionario</span><span class="sxs-lookup"><span data-stu-id="67928-103">Analyzing questionnaire results</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="67928-104">Las estadísticas de cuestionario se pueden usar para calcular promedios, totales y porcentajes basados en un sistema de datos demográficos.</span><span class="sxs-lookup"><span data-stu-id="67928-104">Questionnaire statistics can be used to calculate averages, totals, and percentages based on a set of demographic data.</span></span> <span data-ttu-id="67928-105">Para iniciar este procedimiento, vaya a Cuestionario > Ver y analizar resultados > Estadísticas de los cuestionarios.</span><span class="sxs-lookup"><span data-stu-id="67928-105">To begin this procedure, go to Questionnaire > View and analyze results > Questionnaire statistics.</span></span> <span data-ttu-id="67928-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="67928-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-questionnaire-statistics-record"></a><span data-ttu-id="67928-107">Creación de un registro de estadísticas de cuestionario</span><span class="sxs-lookup"><span data-stu-id="67928-107">Create a Questionnaire statistics record</span></span>
1. <span data-ttu-id="67928-108">Vaya a Estadísticas de los cuestionarios.</span><span class="sxs-lookup"><span data-stu-id="67928-108">Go to Questionnaire statistics.</span></span>
2. <span data-ttu-id="67928-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="67928-109">Click New.</span></span>
3. <span data-ttu-id="67928-110">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="67928-110">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="67928-111">En el campo Estadísticas, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="67928-111">In the Statistics field, type a value.</span></span>
5. <span data-ttu-id="67928-112">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="67928-112">In the Description field, type a value.</span></span>
6. <span data-ttu-id="67928-113">En el campo Cuestionario, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="67928-113">In the Questionnaire field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="67928-114">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="67928-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="67928-115">Haga clic en la pestaña General.</span><span class="sxs-lookup"><span data-stu-id="67928-115">Click the General tab.</span></span>
    * <span data-ttu-id="67928-116">Seleccione si desea incluir resultados anónimos o resultados de trabajadores, contactos y candidatos.</span><span class="sxs-lookup"><span data-stu-id="67928-116">Select if you want to include anonymous results or results from workers, contacts, and applicants.</span></span>  
9. <span data-ttu-id="67928-117">Active o desactive la casilla Trabajador.</span><span class="sxs-lookup"><span data-stu-id="67928-117">Select or clear the Worker check box.</span></span>
    * <span data-ttu-id="67928-118">Si va a ver los resultados por antigüedad o por edad, especifique los intervalos que desea usar para agrupar los resultados.</span><span class="sxs-lookup"><span data-stu-id="67928-118">If you will be viewing the results by seniority or age, specify the intervals that you would like to use for grouping the results.</span></span>  
    * <span data-ttu-id="67928-119">Al especificar un 5 como intervalo de vencimiento, se agruparán los resultados en intervalos de cinco años de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="67928-119">Entering a 5 for the age interval will group the results based on five-year age intervals.</span></span>  
10. <span data-ttu-id="67928-120">En el campo Edad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="67928-120">In the Age field, enter a number.</span></span>
    * <span data-ttu-id="67928-121">Seleccione si desea ejecutar el cálculo en el cuestionario completo, para cada grupo de resultados, para cada pregunta o para cada fila de pregunta.</span><span class="sxs-lookup"><span data-stu-id="67928-121">Select if you want to run the calculation against the entire questionnaire, for each result group, for each question, or for each question row.</span></span>  
    * <span data-ttu-id="67928-122">Seleccione cómo desea agrupar los resultados.</span><span class="sxs-lookup"><span data-stu-id="67928-122">Select how you would like to group the results.</span></span>  
    * <span data-ttu-id="67928-123">Por ejemplo, si se calculan los puntos promedio por pregunta, puede que le interese ver las preguntas agrupadas por grupo de resultados.</span><span class="sxs-lookup"><span data-stu-id="67928-123">For example, if you calculate the average points per question, you may want to see the questions grouped by Result group.</span></span>  
    * <span data-ttu-id="67928-124">Seleccione los datos en los que basar el cálculo.</span><span class="sxs-lookup"><span data-stu-id="67928-124">Select the data to base the calculation on.</span></span>  
    * <span data-ttu-id="67928-125">Por ejemplo, si desea ver el porcentaje promedio en el cuestionario entre los trabajadores frente al promedio en puntos.</span><span class="sxs-lookup"><span data-stu-id="67928-125">For example, if you want to see the average percent received on the questionnaire across your workers versus the average number of points achieved across your workers.</span></span>  
11. <span data-ttu-id="67928-126">Haga clic en la ficha Intervalo.</span><span class="sxs-lookup"><span data-stu-id="67928-126">Click the Range tab.</span></span>
    * <span data-ttu-id="67928-127">Use los intervalos para limitar su conjunto de resultados a solo los que cumplan con los criterios del intervalo.</span><span class="sxs-lookup"><span data-stu-id="67928-127">Use ranges to limit your result set to only those meeting the Range criteria.</span></span>  
12. <span data-ttu-id="67928-128">Haga clic en la ficha Agrupación por.</span><span class="sxs-lookup"><span data-stu-id="67928-128">Click the Grouping by tab.</span></span>
    * <span data-ttu-id="67928-129">Use Agrupaciones para determinar cómo se deben visualizar los resultados.</span><span class="sxs-lookup"><span data-stu-id="67928-129">Use Groupings to determine how the results should be displayed.</span></span>  
    * <span data-ttu-id="67928-130">Por ejemplo, agrupe los resultados primero por sexo y, a continuación, por edad.</span><span class="sxs-lookup"><span data-stu-id="67928-130">For example, group the results first by gender, then by age.</span></span>  
13. <span data-ttu-id="67928-131">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="67928-131">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="67928-132">Mueva las agrupaciones al lado Seleccionadas y póngalas en el orden deseado.</span><span class="sxs-lookup"><span data-stu-id="67928-132">Move the groupings into the Selected side and place them in the desired order.</span></span>  

## <a name="execute-the-statistics-calculation"></a><span data-ttu-id="67928-133">Ejecución del cálculo de estadísticas</span><span class="sxs-lookup"><span data-stu-id="67928-133">Execute the statistics calculation</span></span>
1. <span data-ttu-id="67928-134">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="67928-134">Click Execute.</span></span>
    * <span data-ttu-id="67928-135">Seleccione qué función de cálculo desea aplicar a los resultados.</span><span class="sxs-lookup"><span data-stu-id="67928-135">Select which calculation function you would like to perform on the results.</span></span>  
    * <span data-ttu-id="67928-136">Por ejemplo, calcule los porcentajes promedio en el cuestionario para las agrupaciones seleccionadas o calcule el total de puntos en los grupos de resultados para las agrupaciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="67928-136">For example, calculate the average percentages across the questionnaire for the selected groupings or total the points across the result groups for the selected groupings.</span></span>  
2. <span data-ttu-id="67928-137">Active o desactive la casilla de verificación Eliminar búsquedas anteriores.</span><span class="sxs-lookup"><span data-stu-id="67928-137">Select or clear the Delete previous searches check box.</span></span>
3. <span data-ttu-id="67928-138">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="67928-138">Click OK.</span></span>

## <a name="view-the-results-of-the-questionnaire-statistics-run"></a><span data-ttu-id="67928-139">Consulte los resultados de la ejecución de estadísticas del cuestionario.</span><span class="sxs-lookup"><span data-stu-id="67928-139">View the results of the questionnaire statistics run.</span></span>
1. <span data-ttu-id="67928-140">Haga clic en Resultado.</span><span class="sxs-lookup"><span data-stu-id="67928-140">Click Result.</span></span>
2. <span data-ttu-id="67928-141">Haga clic en Resultado.</span><span class="sxs-lookup"><span data-stu-id="67928-141">Click Result.</span></span>
3. <span data-ttu-id="67928-142">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="67928-142">Close the page.</span></span>
