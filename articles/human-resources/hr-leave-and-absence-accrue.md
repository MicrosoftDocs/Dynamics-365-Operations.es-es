---
title: Acumular planes de bajas y ausencias
description: Puede acumular permisos y ausencias en Dynamics 365 Human Resources para varios empleados o para un individuo.
author: andreabichsel
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: ddd4c55f6ebfbe91fb949a92cb379f51d826c465
ms.sourcegitcommit: cee7887282d372c756c5c11f76684315f249bba5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6303473"
---
# <a name="accrue-leave-and-absence-plans"></a><span data-ttu-id="a3003-103">Acumular planes de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="a3003-103">Accrue leave and absence plans</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="a3003-104">Puede acumular permisos y ausencias en Dynamics 365 Human Resources para varios empleados o para un individuo.</span><span class="sxs-lookup"><span data-stu-id="a3003-104">You can accrue leave and absence in Dynamics 365 Human Resources for multiple employees or for an individual.</span></span>

## <a name="accrue-leave-and-absence-for-multiple-employees"></a><span data-ttu-id="a3003-105">Acumular permisos y ausencias para varios empleados</span><span class="sxs-lookup"><span data-stu-id="a3003-105">Accrue leave and absence for multiple employees</span></span>

1. <span data-ttu-id="a3003-106">En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="a3003-106">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="a3003-107">Debajo de **Administrar bajas**, seleccione **Acumular planes de permisos y ausencias**.</span><span class="sxs-lookup"><span data-stu-id="a3003-107">Under **Manage leave**, select **Accrue leave and absence plans**.</span></span>

3. <span data-ttu-id="a3003-108">Apare el cuadro de diálogo **Acumular planes de permiso y ausencia**.</span><span class="sxs-lookup"><span data-stu-id="a3003-108">The **Accrue leave and absence plans** dialog box appears.</span></span> <span data-ttu-id="a3003-109">En **A partir de**, seleccione **Fecha de hoy** o seleccione **Fecha personalizada** e introduzca una fecha personalizada.</span><span class="sxs-lookup"><span data-stu-id="a3003-109">In **Accrue as of**, either select **Today's date** or select **Custom date** and enter a custom date.</span></span>

4. <span data-ttu-id="a3003-110">Si desea ejecutar acumulaciones para todas las empresas, seleccione **Todas las empresas**.</span><span class="sxs-lookup"><span data-stu-id="a3003-110">If you want to run accruals for all companies, select **All companies**.</span></span> <span data-ttu-id="a3003-111">Si desea procesar acumulaciones para un solo plan de vacaciones, seleccione **No** para **Todos los planes** y luego seleccione un **Plan de vacaciones**.</span><span class="sxs-lookup"><span data-stu-id="a3003-111">If you want to process accruals for a single leave plan, select **No** for **All plans**, and then select a **Leave plan**.</span></span> <span data-ttu-id="a3003-112">Si elige todas las empresas, no puede seleccionar planes de baja individuales.</span><span class="sxs-lookup"><span data-stu-id="a3003-112">If you select all companies, you can't select an individual leave plan.</span></span>

5. <span data-ttu-id="a3003-113">Si desea ejecutar el proceso de acumulación en segundo plano, seleccione **Ejecutar en segundo plano** y realice las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="a3003-113">If you want to run the accrual process in the background, select **Run in the background** and do the following tasks:</span></span>

    1. <span data-ttu-id="a3003-114">Escriba información para el proceso de acumulación.</span><span class="sxs-lookup"><span data-stu-id="a3003-114">Enter information for the accrual process.</span></span>
    2. <span data-ttu-id="a3003-115">Para configurar un trabajo periódico, seleccione **Periodicidad**, introduzca la información de periodicidad y después seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a3003-115">To set up a recurring job, select **Recurrence**, enter the recurrence information, and then select **OK**.</span></span>
    3. <span data-ttu-id="a3003-116">Para configurar una alerta de trabajo, seleccione **Alertas**, seleccione las alertas que quiera recibir y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a3003-116">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>
    4. <span data-ttu-id="a3003-117">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a3003-117">Select **OK**.</span></span> <span data-ttu-id="a3003-118">El proceso de acumulación se ejecutará con los parámetros que establezca.</span><span class="sxs-lookup"><span data-stu-id="a3003-118">The accrual process will run with the parameters you set.</span></span> 

## <a name="accrue-leave-and-absence-for-an-employee"></a><span data-ttu-id="a3003-119">Acumular permisos y ausencias para un empleado</span><span class="sxs-lookup"><span data-stu-id="a3003-119">Accrue leave and absence for an employee</span></span>

1. <span data-ttu-id="a3003-120">En el registro del empleado, seleccione **Baja**.</span><span class="sxs-lookup"><span data-stu-id="a3003-120">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="a3003-121">Seleccione **Acumular planes de permisos y ausencias**.</span><span class="sxs-lookup"><span data-stu-id="a3003-121">Select **Accrue leave and absence**.</span></span>

3. <span data-ttu-id="a3003-122">Apare el cuadro de diálogo **Acumular planes de permiso y ausencia**.</span><span class="sxs-lookup"><span data-stu-id="a3003-122">The **Accrue leave and absence plans** dialog box appears.</span></span> <span data-ttu-id="a3003-123">En **A partir de**, seleccione **Fecha de hoy** o seleccione **Fecha personalizada** e introduzca una fecha personalizada.</span><span class="sxs-lookup"><span data-stu-id="a3003-123">In **Accrue as of**, either select **Today's date** or select **Custom date** and enter a custom date.</span></span>

4. <span data-ttu-id="a3003-124">Si desea ejecutar acumulaciones para todas las empresas, seleccione **Todas las empresas**.</span><span class="sxs-lookup"><span data-stu-id="a3003-124">If you want to run accruals for all companies, select **All companies**.</span></span> <span data-ttu-id="a3003-125">Si desea procesar acumulaciones para un solo plan de vacaciones, seleccione **No** para **Todos los planes** y luego seleccione un **Plan de vacaciones**.</span><span class="sxs-lookup"><span data-stu-id="a3003-125">If you want to process accruals for a single leave plan, select **No** for **All plans**, and then select a **Leave plan**.</span></span> <span data-ttu-id="a3003-126">Si elige todas las empresas, no puede seleccionar planes de baja individuales.</span><span class="sxs-lookup"><span data-stu-id="a3003-126">If you select all companies, you can't select an individual leave plan.</span></span>

5. <span data-ttu-id="a3003-127">Si desea ejecutar el proceso de acumulación en segundo plano, seleccione **Ejecutar en segundo plano** y realice las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="a3003-127">If you want to run the accrual process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="a3003-128">Escriba información para el proceso de acumulación.</span><span class="sxs-lookup"><span data-stu-id="a3003-128">Enter information for the accrual process.</span></span>

   2. <span data-ttu-id="a3003-129">Para configurar un trabajo periódico, seleccione **Periodicidad**, introduzca la información de periodicidad y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a3003-129">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="a3003-130">Para configurar una alerta de trabajo, seleccione **Alertas**, seleccione las alertas que quiera recibir y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a3003-130">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="a3003-131">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a3003-131">Select **OK**.</span></span> <span data-ttu-id="a3003-132">El proceso de acumulación se ejecutará con los parámetros que establezca.</span><span class="sxs-lookup"><span data-stu-id="a3003-132">The accrual process will run with the parameters you set.</span></span>

## <a name="delete-leave-and-absence-accruals-for-multiple-employees"></a><span data-ttu-id="a3003-133">Eliminar acumulaciones de permisos y ausencias para varios empleados</span><span class="sxs-lookup"><span data-stu-id="a3003-133">Delete leave and absence accruals for multiple employees</span></span>

<span data-ttu-id="a3003-134">Eliminar registros de acumulación para un plan e intervalo de fechas específico.</span><span class="sxs-lookup"><span data-stu-id="a3003-134">Delete accrual records for a specific plan and date range.</span></span> <span data-ttu-id="a3003-135">Las fechas de acumulación deben ser la de hoy o fechas en el futuro.</span><span class="sxs-lookup"><span data-stu-id="a3003-135">Accrual dates must be dated today or in the future.</span></span>

1. <span data-ttu-id="a3003-136">En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="a3003-136">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="a3003-137">Debajo de **Administrar bajas**, seleccione **Eliminar acumulaciones de permisos y ausencias**.</span><span class="sxs-lookup"><span data-stu-id="a3003-137">Under **Manage leave**, select **Delete leave and absence plan accruals**.</span></span>

3. <span data-ttu-id="a3003-138">En el cuadro de diálogo **Eliminar acumulaciones de planes de permiso y ausencia**, seleccione **Dejar plan**.</span><span class="sxs-lookup"><span data-stu-id="a3003-138">In the **Delete leave and absence plan accruals** dialog box, select the **Leave plan**.</span></span>

4. <span data-ttu-id="a3003-139">Si corresponde, elija **Eliminar ajustes de saldo**.</span><span class="sxs-lookup"><span data-stu-id="a3003-139">If applicable, choose **Delete balance adjustments**.</span></span>

5. <span data-ttu-id="a3003-140">introduzca o seleccione una **Fecha de abandono de acumulación**.</span><span class="sxs-lookup"><span data-stu-id="a3003-140">Enter or select a **Leave accrual date**.</span></span> <span data-ttu-id="a3003-141">Esta fecha tiene que ser hoy o en el futuro.</span><span class="sxs-lookup"><span data-stu-id="a3003-141">This date has to be either today or in the future.</span></span>

6. <span data-ttu-id="a3003-142">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a3003-142">Select **OK**.</span></span> <span data-ttu-id="a3003-143">El proceso de acumulación eliminará acumulaciones con los parámetros que establezca.</span><span class="sxs-lookup"><span data-stu-id="a3003-143">The accrual process will delete accruals with the parameters you set.</span></span>

## <a name="delete-leave-and-absence-accruals-for-a-single-employee"></a><span data-ttu-id="a3003-144">Eliminar acumulaciones de permisos y ausencias para un empleado</span><span class="sxs-lookup"><span data-stu-id="a3003-144">Delete leave and absence accruals for a single employee</span></span>

1. <span data-ttu-id="a3003-145">En el registro del empleado, seleccione **Baja**.</span><span class="sxs-lookup"><span data-stu-id="a3003-145">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="a3003-146">Seleccione **Eliminar acumulaciones de planes de permisos y ausencias**.</span><span class="sxs-lookup"><span data-stu-id="a3003-146">Select **Delete leave and absence plan accruals**.</span></span>

3. <span data-ttu-id="a3003-147">En el cuadro de diálogo **Eliminar acumulaciones de planes de permiso y ausencia**, seleccione **Dejar plan**.</span><span class="sxs-lookup"><span data-stu-id="a3003-147">In the **Delete leave and absence plan accruals** dialog box, select **Leave plan**.</span></span>

4. <span data-ttu-id="a3003-148">Si corresponde, elija **Eliminar ajustes de saldo**.</span><span class="sxs-lookup"><span data-stu-id="a3003-148">If applicable, choose **Delete balance adjustments**.</span></span>

5. <span data-ttu-id="a3003-149">introduzca o seleccione una **Fecha de abandono de acumulación**.</span><span class="sxs-lookup"><span data-stu-id="a3003-149">Enter or select a **Leave accrual date**.</span></span> <span data-ttu-id="a3003-150">Esta fecha tiene que ser hoy o en el futuro.</span><span class="sxs-lookup"><span data-stu-id="a3003-150">This date must be either today or in the future.</span></span>

6. <span data-ttu-id="a3003-151">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a3003-151">Select **OK**.</span></span> <span data-ttu-id="a3003-152">El proceso de acumulación eliminará acumulaciones con los parámetros que establezca.</span><span class="sxs-lookup"><span data-stu-id="a3003-152">The accrual process will delete accruals with the parameters you set.</span></span>

## <a name="review-leave-accrual-and-deletion-processes"></a><span data-ttu-id="a3003-153">Revisar los procesos de acumulación y eliminación de permisos</span><span class="sxs-lookup"><span data-stu-id="a3003-153">Review leave accrual and deletion processes</span></span>

<span data-ttu-id="a3003-154">**Auditoría de acumulación de permisos** se muestra cada vez que ejecuta o elimina una acumulación para uno o todos los empleados.</span><span class="sxs-lookup"><span data-stu-id="a3003-154">**Leave accrual audit** displays each time you run or delete an accrual for one or all employees.</span></span> <span data-ttu-id="a3003-155">También se muestra la fecha y la persona que realizó la acción.</span><span class="sxs-lookup"><span data-stu-id="a3003-155">The date and person who performed the action also displays.</span></span>

1. <span data-ttu-id="a3003-156">En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="a3003-156">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="a3003-157">Debajo de **Administrar bajas**, seleccione **Eliminar auditoría de acumulaciones de permisos**.</span><span class="sxs-lookup"><span data-stu-id="a3003-157">Under **Manage leave**, select **Delete leave accrual audit**.</span></span>

## <a name="leave-accrual-transaction-auditing"></a><span data-ttu-id="a3003-158">Auditoría de transacciones de acumulación de bajas</span><span class="sxs-lookup"><span data-stu-id="a3003-158">Leave accrual transaction auditing</span></span>

<span data-ttu-id="a3003-159">Esta función ayuda a los administradores de bajas y ausencias a comprender las transacciones de acumulación de bajas y ausencias relacionadas con los saldos de tiempo libre de un empleado para un tipo de baja específico.</span><span class="sxs-lookup"><span data-stu-id="a3003-159">This feature helps leave and absence managers understand the leave and absence accrual transactions related to an employee’s time off balances for a specific leave type.</span></span>

<span data-ttu-id="a3003-160">Para ver los detalles de la transacción:</span><span class="sxs-lookup"><span data-stu-id="a3003-160">To view transaction details:</span></span>

1. <span data-ttu-id="a3003-161">En el registro del empleado, seleccione **Baja**.</span><span class="sxs-lookup"><span data-stu-id="a3003-161">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="a3003-162">Seleccione **Ver tiempo libre** y luego seleccione la pestaña **Saldos**.</span><span class="sxs-lookup"><span data-stu-id="a3003-162">Select **View time off**, and then select the **Balances** tab.</span></span>

<span data-ttu-id="a3003-163">Para ver las transacciones de acumulación relacionadas con un tipo de licencia específico, seleccione el valor numérico en la columna **Saldo actual**.</span><span class="sxs-lookup"><span data-stu-id="a3003-163">To view the accrual transactions related to a specific leave type, select the numerical value in the **Current balance** column.</span></span>

<span data-ttu-id="a3003-164">Para ver los detalles de la transacción para un monto de acumulación específico, seleccione una fila de acumulación, abra el panel **Información relacionada** de la derecha y, a continuación, abra la sección **Detalles de la transacción**.</span><span class="sxs-lookup"><span data-stu-id="a3003-164">To view the transaction details for a specific accrual amount, select an accrual row, open the **Related information** panel on the right, and then open the **Transaction details** section.</span></span> <span data-ttu-id="a3003-165">Se muestra la sección Detalles de la transacción:</span><span class="sxs-lookup"><span data-stu-id="a3003-165">The Transaction details section displays:</span></span>

- <span data-ttu-id="a3003-166">Cambios en el saldo del tipo de baja del empleado</span><span class="sxs-lookup"><span data-stu-id="a3003-166">Changes to the employee’s leave type balance</span></span>
- <span data-ttu-id="a3003-167">Detalles de empleo para ese período de acumulación especificado</span><span class="sxs-lookup"><span data-stu-id="a3003-167">Employment details for that specified accrual period</span></span>
- <span data-ttu-id="a3003-168">Detalles sobre el período de acumulación y las tarifas</span><span class="sxs-lookup"><span data-stu-id="a3003-168">Details about the accrual period and rates</span></span>
- <span data-ttu-id="a3003-169">Cualquier cambio realizado para dejar las configuraciones del plan</span><span class="sxs-lookup"><span data-stu-id="a3003-169">Any changes made to leave plan configurations</span></span>

![Mostrar auditoría de transacciones de acumulación de bajas](media/hr-leave-and-absence-accrue-audit.png)

## <a name="see-also"></a><span data-ttu-id="a3003-171">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a3003-171">See also</span></span>

[<span data-ttu-id="a3003-172">Visión general de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="a3003-172">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="a3003-173">Crear un plan de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="a3003-173">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
