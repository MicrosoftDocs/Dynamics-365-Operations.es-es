---
title: Configurar puestos
description: Los puestos son un aspecto importante del nivel inferior de una jerarquía organizativa.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, HcmWorkforceWorkspace, HcmWorkerActivityChart, HcmAllWorkersListPart, HcmPosition, HcmPositionNewPosition, HcmJobLookup, HcmPositionReportsToDialog, HcmPositionLookup, FinancialDimensionDefaultTemplatesLookup, DimensionLookup, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 88acf6325a0513d75a5ea0a6b463b93a1b9f56fe
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467394"
---
# <a name="set-up-positions"></a><span data-ttu-id="832c9-103">Configurar puestos</span><span class="sxs-lookup"><span data-stu-id="832c9-103">Set up positions</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



<span data-ttu-id="832c9-104">Los puestos son un aspecto importante del nivel inferior de una jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="832c9-104">Positions are an important element of the lower level of an organization hierarchy.</span></span> <span data-ttu-id="832c9-105">Un puesto es un caso individual de un trabajo.</span><span class="sxs-lookup"><span data-stu-id="832c9-105">A position is an individual instance of a job.</span></span> <span data-ttu-id="832c9-106">Por ejemplo, el puesto "Director de ventas (Este)" es uno de los puestos asociados al trabajo "Director de ventas".</span><span class="sxs-lookup"><span data-stu-id="832c9-106">For example, the position, “Sales manager (East),” is one of the positions that is associated with the job, “Sales manager.”</span></span> <span data-ttu-id="832c9-107">Un puesto existe en un departamento y sólo puede tener un trabajador asociado a ella.</span><span class="sxs-lookup"><span data-stu-id="832c9-107">A position exists in a department and may have only one worker associated with it.</span></span> <span data-ttu-id="832c9-108">En esta tarea nos desplazaremos por los pasos necesarios para crear un puesto.</span><span class="sxs-lookup"><span data-stu-id="832c9-108">In this task we will walk through the steps required to create a position.</span></span> <span data-ttu-id="832c9-109">Este procedimiento se va a utilizar para los especialistas de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="832c9-109">This procedure is intended for Human Resources Specialists.</span></span>

1. <span data-ttu-id="832c9-110">Haga clic en Administración de recursos.</span><span class="sxs-lookup"><span data-stu-id="832c9-110">Click Workforce management.</span></span>
2. <span data-ttu-id="832c9-111">Haga clic en Vacantes.</span><span class="sxs-lookup"><span data-stu-id="832c9-111">Click Open positions.</span></span>
3. <span data-ttu-id="832c9-112">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="832c9-112">Click New to open the drop dialog.</span></span>
4. <span data-ttu-id="832c9-113">En el campo Trabajo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="832c9-113">In the Job field, enter or select a value.</span></span>
    * <span data-ttu-id="832c9-114">La descripción del trabajo, el título y el factor de empleo equivalente a jornada completa se copian automáticamente del trabajo seleccionado al puesto.</span><span class="sxs-lookup"><span data-stu-id="832c9-114">The Job description, title, and full-time equivalent employment factor are automatically copied from the selected job into the position.</span></span>  
5. <span data-ttu-id="832c9-115">Resuelva los cambios en el trabajo.</span><span class="sxs-lookup"><span data-stu-id="832c9-115">ResolveChanges the Job.</span></span>
6. <span data-ttu-id="832c9-116">Haga clic en Crear puesto.</span><span class="sxs-lookup"><span data-stu-id="832c9-116">Click Create position.</span></span>
7. <span data-ttu-id="832c9-117">En el campo Departamento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="832c9-117">In the Department field, enter or select a value.</span></span>
8. <span data-ttu-id="832c9-118">En el campo Tipo de puesto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="832c9-118">In the Position type field, enter or select a value.</span></span>
9. <span data-ttu-id="832c9-119">En el campo Región de compensación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="832c9-119">In the Compensation region field, enter or select a value.</span></span>
    * <span data-ttu-id="832c9-120">El campo Región de compensación determina las reglas de idoneidad de compensación y los presupuestos de incremento fijo que se aplican a un empleado en ese puesto.</span><span class="sxs-lookup"><span data-stu-id="832c9-120">The Compensation region field determines the compensation eligibility rules and fixed increase budgets that apply to an employee in that position.</span></span>  
10. <span data-ttu-id="832c9-121">En el campo Disponible para la asignación, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="832c9-121">In the Available for assignment field, enter a date and time.</span></span>
11. <span data-ttu-id="832c9-122">Expanda la sección Duración del puesto.</span><span class="sxs-lookup"><span data-stu-id="832c9-122">Expand the Position duration section.</span></span>
    * <span data-ttu-id="832c9-123">La duración del puesto se especifica de forma predeterminada en función de las fechas de activación y de jubilación especificadas anteriormente</span><span class="sxs-lookup"><span data-stu-id="832c9-123">Position duration is entered by default based on activation and retirement dates entered earlier</span></span>  
12. <span data-ttu-id="832c9-124">Expanda la sección Notifica al puesto.</span><span class="sxs-lookup"><span data-stu-id="832c9-124">Expand the Reports to position section.</span></span>
    * <span data-ttu-id="832c9-125">Al asignar un trabajador a un puesto que es subordinado de otro puesto, crea una relación jerárquica directa entre los trabajadores asignados a los dos puestos.</span><span class="sxs-lookup"><span data-stu-id="832c9-125">When you assign a worker to a position that reports to another position, you create a direct reporting relationship between the workers who are assigned to the two positions.</span></span>  
13. <span data-ttu-id="832c9-126">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="832c9-126">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="832c9-127">En el campo Informa a, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="832c9-127">In the Reports to field, enter or select a value.</span></span>
15. <span data-ttu-id="832c9-128">Haga clic en Crear.</span><span class="sxs-lookup"><span data-stu-id="832c9-128">Click Create.</span></span>
16. <span data-ttu-id="832c9-129">Expanda la sección Asignación de trabajadores.</span><span class="sxs-lookup"><span data-stu-id="832c9-129">Expand the Worker assignment section.</span></span>
17. <span data-ttu-id="832c9-130">Expanda la sección Relaciones.</span><span class="sxs-lookup"><span data-stu-id="832c9-130">Expand the Relationships section.</span></span>
    * <span data-ttu-id="832c9-131">Si la organización usa una jerarquía de matriz u otra jerarquía personalizada, puede configurar tipos de jerarquía de puestos y agregar relaciones jerárquicas a los puestos para cada tipo de jerarquía que configure.</span><span class="sxs-lookup"><span data-stu-id="832c9-131">If your organization uses a matrix hierarchy or another custom hierarchy, you can set up position hierarchy types and then add reporting relationships to positions for each hierarchy type that you set up.</span></span>  
18. <span data-ttu-id="832c9-132">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="832c9-132">Click Add.</span></span>
19. <span data-ttu-id="832c9-133">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="832c9-133">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="832c9-134">En el campo Nombre de jerarquía, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="832c9-134">In the Hierarchy name field, enter or select a value.</span></span>
21. <span data-ttu-id="832c9-135">En el campo Notifica al puesto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="832c9-135">In the Reports to position field, enter or select a value.</span></span>
22. <span data-ttu-id="832c9-136">Expanda la sección Nómina.</span><span class="sxs-lookup"><span data-stu-id="832c9-136">Expand the Payroll section.</span></span>
23. <span data-ttu-id="832c9-137">En el campo Ciclo de pago, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="832c9-137">In the Pay cycle field, enter or select a value.</span></span>
24. <span data-ttu-id="832c9-138">En el campo Pagado por, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="832c9-138">In the Paid by field, enter or select a value.</span></span>
25. <span data-ttu-id="832c9-139">En el campo Horas ordinarias anuales, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="832c9-139">In the Annual regular hours field, enter a number.</span></span>
    * <span data-ttu-id="832c9-140">Este es el número de horas pagadas con regularidad que está previsto que el trabajador en este puesto trabaje cada año.</span><span class="sxs-lookup"><span data-stu-id="832c9-140">This is the number of regularly paid hours that the worker in this position is expected to work each year.</span></span>  
26. <span data-ttu-id="832c9-141">Expanda la sección Sindicato.</span><span class="sxs-lookup"><span data-stu-id="832c9-141">Expand the Labor union section.</span></span>
27. <span data-ttu-id="832c9-142">Contraiga la sección Sindicato.</span><span class="sxs-lookup"><span data-stu-id="832c9-142">Collapse the Labor union section.</span></span>
28. <span data-ttu-id="832c9-143">Expanda la sección Dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="832c9-143">Expand the Financial dimensions section.</span></span>
29. <span data-ttu-id="832c9-144">En el campo Plantilla de distribución, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="832c9-144">In the Distribution template field, enter or select a value.</span></span>
30. <span data-ttu-id="832c9-145">En el campo Departamento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="832c9-145">In the Department field, enter or select a value.</span></span>
31. <span data-ttu-id="832c9-146">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="832c9-146">Click Save.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]