--- 
title: "Supervisar una ejecución de planificación maestra"
description: "El planificador de producción desea ver si una ejecución de planificación maestra está en curso."
author: YuyuScheller
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 1e08d9fd3388561563e6fb982416186a652b4ce2
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="monitor-a-master-planning-run"></a><span data-ttu-id="dea0a-103">Supervisar una ejecución de planificación maestra</span><span class="sxs-lookup"><span data-stu-id="dea0a-103">Monitor a master planning run</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dea0a-104">El planificador de producción desea ver si una ejecución de planificación maestra está en curso.</span><span class="sxs-lookup"><span data-stu-id="dea0a-104">The production planner wants to see if a master planning run is in progress.</span></span> <span data-ttu-id="dea0a-105">Use la empresa de datos de demostración USMF para completar este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="dea0a-105">Use the demo data company USMF to complete this procedure.</span></span>


## <a name="run-master-planning"></a><span data-ttu-id="dea0a-106">Ejecutar planificación maestra</span><span class="sxs-lookup"><span data-stu-id="dea0a-106">Run master planning</span></span>
1. <span data-ttu-id="dea0a-107">Haga clic en Planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="dea0a-107">Click Master planning.</span></span>
    * <span data-ttu-id="dea0a-108">Encontrará esto en el panel de predeterminado.</span><span class="sxs-lookup"><span data-stu-id="dea0a-108">You'll find this on the default dashboard.</span></span>  
2. <span data-ttu-id="dea0a-109">En el campo Plan, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="dea0a-109">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="dea0a-110">Ejemplo: StaticPlan</span><span class="sxs-lookup"><span data-stu-id="dea0a-110">Example: StaticPlan</span></span>  
3. <span data-ttu-id="dea0a-111">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="dea0a-111">Click Run.</span></span>
4. <span data-ttu-id="dea0a-112">Seleccione Sí en el campo Realizar seguimiento de tiempo procesamiento.</span><span class="sxs-lookup"><span data-stu-id="dea0a-112">Select Yes in the Track processing time field.</span></span>
    * <span data-ttu-id="dea0a-113">Si el campo ya está seleccionado, omita este paso.</span><span class="sxs-lookup"><span data-stu-id="dea0a-113">If the field is already selected, skip this step.</span></span>  
5. <span data-ttu-id="dea0a-114">En el campo Número de subprocesos, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="dea0a-114">In the Number of threads field, enter a number.</span></span>
6. <span data-ttu-id="dea0a-115">Expanda la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="dea0a-115">Expand the Records to include section.</span></span>
7. <span data-ttu-id="dea0a-116">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="dea0a-116">Click Filter.</span></span>
8. <span data-ttu-id="dea0a-117">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="dea0a-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="dea0a-118">Marque la fila donde Campo = Número de artículo.</span><span class="sxs-lookup"><span data-stu-id="dea0a-118">Mark the row where Field = Item number.</span></span>  
9. <span data-ttu-id="dea0a-119">En el campo Criterios, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="dea0a-119">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="dea0a-120">Ejemplo: T0001</span><span class="sxs-lookup"><span data-stu-id="dea0a-120">Example: T0001</span></span>  
10. <span data-ttu-id="dea0a-121">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="dea0a-121">Click OK.</span></span>
11. <span data-ttu-id="dea0a-122">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="dea0a-122">Click OK.</span></span>

## <a name="monitor-the-master-planning-run"></a><span data-ttu-id="dea0a-123">Supervisar la ejecución de planificación maestra</span><span class="sxs-lookup"><span data-stu-id="dea0a-123">Monitor the master planning run</span></span>
1. <span data-ttu-id="dea0a-124">Haga clic en Historial.</span><span class="sxs-lookup"><span data-stu-id="dea0a-124">Click History.</span></span>
2. <span data-ttu-id="dea0a-125">Haga clic en Consultas.</span><span class="sxs-lookup"><span data-stu-id="dea0a-125">Click Inquiries.</span></span>
3. <span data-ttu-id="dea0a-126">Haga clic en Duración de la tarea de proceso.</span><span class="sxs-lookup"><span data-stu-id="dea0a-126">Click Process task duration.</span></span>
4. <span data-ttu-id="dea0a-127">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="dea0a-127">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="dea0a-128">Para cada artículo puede obtener una visión general de cuánto tiempo se tardó en completar cada paso de planificación.</span><span class="sxs-lookup"><span data-stu-id="dea0a-128">For each item you can get an overview of how long it took to complete each planning step.</span></span>  


