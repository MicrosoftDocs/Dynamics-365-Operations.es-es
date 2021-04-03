---
title: Acumular planes de bajas y ausencias
description: Puede acumular permisos y ausencias en Dynamics 365 Human Resources para varios empleados o para un individuo.
author: andreabichsel
manager: tfehr
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 348c8e5336854eb2a1c04a1f98a97a2c9dba7176
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464919"
---
# <a name="accrue-leave-and-absence-plans"></a><span data-ttu-id="cedbb-103">Acumular planes de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="cedbb-103">Accrue leave and absence plans</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="cedbb-104">Puede acumular permisos y ausencias en Dynamics 365 Human Resources para varios empleados o para un individuo.</span><span class="sxs-lookup"><span data-stu-id="cedbb-104">You can accrue leave and absence in Dynamics 365 Human Resources for multiple employees or for an individual.</span></span>

## <a name="accrue-leave-and-absence-for-multiple-employees"></a><span data-ttu-id="cedbb-105">Acumular permisos y ausencias para varios empleados</span><span class="sxs-lookup"><span data-stu-id="cedbb-105">Accrue leave and absence for multiple employees</span></span>

1. <span data-ttu-id="cedbb-106">En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-106">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="cedbb-107">Debajo de **Administrar bajas**, seleccione **Acumular planes de permisos y ausencias**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-107">Under **Manage leave**, select **Accrue leave and absence plans**.</span></span>

3. <span data-ttu-id="cedbb-108">Apare el cuadro de diálogo **Acumular planes de permiso y ausencia**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-108">The **Accrue leave and absence plans** dialog box appears.</span></span> <span data-ttu-id="cedbb-109">En **A partir de**, seleccione **Fecha de hoy** o seleccione **Fecha personalizada** e introduzca una fecha personalizada.</span><span class="sxs-lookup"><span data-stu-id="cedbb-109">In **Accrue as of**, either select **Today's date** or select **Custom date** and enter a custom date.</span></span>

4. <span data-ttu-id="cedbb-110">Si desea ejecutar acumulaciones para todas las empresas, seleccione **Todas las empresas**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-110">If you want to run accruals for all companies, select **All companies**.</span></span> <span data-ttu-id="cedbb-111">Si desea procesar acumulaciones para un solo plan de vacaciones, seleccione **No** para **Todos los planes** y luego seleccione un **Plan de vacaciones**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-111">If you want to process accruals for a single leave plan, select **No** for **All plans**, and then select a **Leave plan**.</span></span> <span data-ttu-id="cedbb-112">Si elige todas las empresas, no puede seleccionar planes de baja individuales.</span><span class="sxs-lookup"><span data-stu-id="cedbb-112">If you select all companies, you can't select an individual leave plan.</span></span> 

5. <span data-ttu-id="cedbb-113">Si desea ejecutar el proceso de acumulación en segundo plano, seleccione **Ejecutar en segundo plano** y realice las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="cedbb-113">If you want to run the accrual process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="cedbb-114">Escriba información para el proceso de acumulación.</span><span class="sxs-lookup"><span data-stu-id="cedbb-114">Enter information for the accrual process.</span></span>

   2. <span data-ttu-id="cedbb-115">Para configurar un trabajo periódico, seleccione **Periodicidad**, introduzca la información de periodicidad y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-115">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="cedbb-116">Para configurar una alerta de trabajo, seleccione **Alertas**, seleccione las alertas que quiera recibir y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-116">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="cedbb-117">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-117">Select **OK**.</span></span> <span data-ttu-id="cedbb-118">El proceso de acumulación se ejecutará con los parámetros que establezca.</span><span class="sxs-lookup"><span data-stu-id="cedbb-118">The accrual process will run with the parameters you set.</span></span>

## <a name="accrue-leave-and-absence-for-an-employee"></a><span data-ttu-id="cedbb-119">Acumular permisos y ausencias para un empleado</span><span class="sxs-lookup"><span data-stu-id="cedbb-119">Accrue leave and absence for an employee</span></span>

1. <span data-ttu-id="cedbb-120">En el registro del empleado, seleccione **Baja**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-120">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="cedbb-121">Seleccione **Acumular planes de permisos y ausencias**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-121">Select **Accrue leave and absence**.</span></span>

3. <span data-ttu-id="cedbb-122">Apare el cuadro de diálogo **Acumular planes de permiso y ausencia**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-122">The **Accrue leave and absence plans** dialog box appears.</span></span> <span data-ttu-id="cedbb-123">En **A partir de**, seleccione **Fecha de hoy** o seleccione **Fecha personalizada** e introduzca una fecha personalizada.</span><span class="sxs-lookup"><span data-stu-id="cedbb-123">In **Accrue as of**, either select **Today's date** or select **Custom date** and enter a custom date.</span></span>

4. <span data-ttu-id="cedbb-124">Si desea ejecutar acumulaciones para todas las empresas, seleccione **Todas las empresas**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-124">If you want to run accruals for all companies, select **All companies**.</span></span> <span data-ttu-id="cedbb-125">Si desea procesar acumulaciones para un solo plan de vacaciones, seleccione **No** para **Todos los planes** y luego seleccione un **Plan de vacaciones**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-125">If you want to process accruals for a single leave plan, select **No** for **All plans**, and then select a **Leave plan**.</span></span> <span data-ttu-id="cedbb-126">Si elige todas las empresas, no puede seleccionar planes de baja individuales.</span><span class="sxs-lookup"><span data-stu-id="cedbb-126">If you select all companies, you can't select an individual leave plan.</span></span> 

5. <span data-ttu-id="cedbb-127">Si desea ejecutar el proceso de acumulación en segundo plano, seleccione **Ejecutar en segundo plano** y realice las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="cedbb-127">If you want to run the accrual process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="cedbb-128">Escriba información para el proceso de acumulación.</span><span class="sxs-lookup"><span data-stu-id="cedbb-128">Enter information for the accrual process.</span></span>

   2. <span data-ttu-id="cedbb-129">Para configurar un trabajo periódico, seleccione **Periodicidad**, introduzca la información de periodicidad y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-129">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="cedbb-130">Para configurar una alerta de trabajo, seleccione **Alertas**, seleccione las alertas que quiera recibir y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-130">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="cedbb-131">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-131">Select **OK**.</span></span> <span data-ttu-id="cedbb-132">El proceso de acumulación se ejecutará con los parámetros que establezca.</span><span class="sxs-lookup"><span data-stu-id="cedbb-132">The accrual process will run with the parameters you set.</span></span>

## <a name="delete-leave-and-absence-accruals-for-multiple-employees"></a><span data-ttu-id="cedbb-133">Eliminar acumulaciones de permisos y ausencias para varios empleados</span><span class="sxs-lookup"><span data-stu-id="cedbb-133">Delete leave and absence accruals for multiple employees</span></span>

<span data-ttu-id="cedbb-134">Eliminar registros de acumulación para un plan e intervalo de fechas específico.</span><span class="sxs-lookup"><span data-stu-id="cedbb-134">Delete accrual records for a specific plan and date range.</span></span> <span data-ttu-id="cedbb-135">Las fechas de acumulación deben ser la de hoy o fechas en el futuro.</span><span class="sxs-lookup"><span data-stu-id="cedbb-135">Accrual dates must be dated today or in the future.</span></span>

1. <span data-ttu-id="cedbb-136">En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-136">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="cedbb-137">Debajo de **Administrar bajas**, seleccione **Eliminar acumulaciones de permisos y ausencias**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-137">Under **Manage leave**, select **Delete leave and absence plan accruals**.</span></span>

3. <span data-ttu-id="cedbb-138">En el cuadro de diálogo **Eliminar acumulaciones de planes de permiso y ausencia**, seleccione **Dejar plan**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-138">In the **Delete leave and absence plan accruals** dialog box, select the **Leave plan**.</span></span> 

4. <span data-ttu-id="cedbb-139">Si corresponde, elija **Eliminar ajustes de saldo**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-139">If applicable, choose **Delete balance adjustments**.</span></span>

5. <span data-ttu-id="cedbb-140">introduzca o seleccione una **Fecha de abandono de acumulación**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-140">Enter or select a **Leave accrual date**.</span></span> <span data-ttu-id="cedbb-141">Esta fecha tiene que ser hoy o en el futuro.</span><span class="sxs-lookup"><span data-stu-id="cedbb-141">This date has to be either today or in the future.</span></span> 

6. <span data-ttu-id="cedbb-142">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-142">Select **OK**.</span></span> <span data-ttu-id="cedbb-143">El proceso de acumulación eliminará acumulaciones con los parámetros que establezca.</span><span class="sxs-lookup"><span data-stu-id="cedbb-143">The accrual process will delete accruals with the parameters you set.</span></span> 

## <a name="delete-leave-and-absence-accruals-for-a-single-employee"></a><span data-ttu-id="cedbb-144">Eliminar acumulaciones de permisos y ausencias para un empleado</span><span class="sxs-lookup"><span data-stu-id="cedbb-144">Delete leave and absence accruals for a single employee</span></span>

1. <span data-ttu-id="cedbb-145">En el registro del empleado, seleccione **Baja**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-145">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="cedbb-146">Seleccione **Eliminar acumulaciones de planes de permisos y ausencias**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-146">Select **Delete leave and absence plan accruals**.</span></span>

3. <span data-ttu-id="cedbb-147">En el cuadro de diálogo **Eliminar acumulaciones de planes de permiso y ausencia**, seleccione **Dejar plan**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-147">In the **Delete leave and absence plan accruals** dialog box, select **Leave plan**.</span></span> 

4. <span data-ttu-id="cedbb-148">Si corresponde, elija **Eliminar ajustes de saldo**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-148">If applicable, choose **Delete balance adjustments**.</span></span>

5. <span data-ttu-id="cedbb-149">introduzca o seleccione una **Fecha de abandono de acumulación**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-149">Enter or select a **Leave accrual date**.</span></span> <span data-ttu-id="cedbb-150">Esta fecha tiene que ser hoy o en el futuro.</span><span class="sxs-lookup"><span data-stu-id="cedbb-150">This date must be either today or in the future.</span></span> 

6. <span data-ttu-id="cedbb-151">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-151">Select **OK**.</span></span> <span data-ttu-id="cedbb-152">El proceso de acumulación eliminará acumulaciones con los parámetros que establezca.</span><span class="sxs-lookup"><span data-stu-id="cedbb-152">The accrual process will delete accruals with the parameters you set.</span></span> 

## <a name="review-leave-accrual-and-deletion-processes"></a><span data-ttu-id="cedbb-153">Revisar los procesos de acumulación y eliminación de permisos</span><span class="sxs-lookup"><span data-stu-id="cedbb-153">Review leave accrual and deletion processes</span></span>

<span data-ttu-id="cedbb-154">**Auditoría de acumulación de permisos** se muestra cada vez que ejecuta o elimina una acumulación para uno o todos los empleados.</span><span class="sxs-lookup"><span data-stu-id="cedbb-154">**Leave accrual audit** displays each time you run or delete an accrual for one or all employees.</span></span> <span data-ttu-id="cedbb-155">También se muestra la fecha y la persona que realizó la acción.</span><span class="sxs-lookup"><span data-stu-id="cedbb-155">The date and person who performed the action also displays.</span></span>

1. <span data-ttu-id="cedbb-156">En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-156">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="cedbb-157">Debajo de **Administrar bajas**, seleccione **Eliminar auditoría de acumulaciones de permisos**.</span><span class="sxs-lookup"><span data-stu-id="cedbb-157">Under **Manage leave**, select **Delete leave accrual audit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="cedbb-158">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cedbb-158">See also</span></span>

[<span data-ttu-id="cedbb-159">Visión general de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="cedbb-159">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="cedbb-160">Crear un plan de permisos y ausencias</span><span class="sxs-lookup"><span data-stu-id="cedbb-160">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]