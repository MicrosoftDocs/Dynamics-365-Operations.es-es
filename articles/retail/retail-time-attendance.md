---
title: Gestión del tiempo y la asistencia en Retail
description: Este tema describe los escenarios que se admiten para la gestión del tiempo y la asistencia en Dynamics 365 Retail.
author: aamirallaqaband
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: JMGParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 62813
ms.assetid: 821994a6-cd29-45a3-a526-ce204064f080
ms.search.region: global
ms.search.industry: Retail
ms.author: aamiral
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: d541de550df41b7d4616492960bd4f2aae46d45e
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024992"
---
# <a name="time-and-attendance-management-in-retail"></a><span data-ttu-id="c9b1d-103">Gestión del tiempo y la asistencia en Retail</span><span class="sxs-lookup"><span data-stu-id="c9b1d-103">Time and attendance management in Retail</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c9b1d-104">Este tema describe los escenarios que se admiten para la gestión del tiempo y la asistencia en Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="c9b1d-104">This topic describes the scenarios that are supported for time and attendance management in Dynamics 365 Retail.</span></span>

## <a name="manage-worker-setup-and-scheduling"></a><span data-ttu-id="c9b1d-105">Gestionar la configuración y la programación de trabajadores</span><span class="sxs-lookup"><span data-stu-id="c9b1d-105">Manage worker setup and scheduling</span></span>

### <a name="initial-configuration"></a><span data-ttu-id="c9b1d-106">Configuración inicial</span><span class="sxs-lookup"><span data-stu-id="c9b1d-106">Initial configuration</span></span>

- <span data-ttu-id="c9b1d-107">Ejecutar el asistente para la configuración.</span><span class="sxs-lookup"><span data-stu-id="c9b1d-107">Run the configuration wizard.</span></span>
- <span data-ttu-id="c9b1d-108">Registrar a los trabajadores como trabajadores con registro de horas.</span><span class="sxs-lookup"><span data-stu-id="c9b1d-108">Register workers as time registration workers.</span></span>

### <a name="plan-worker-schedules"></a><span data-ttu-id="c9b1d-109">Planificar las programaciones de los trabajadores</span><span class="sxs-lookup"><span data-stu-id="c9b1d-109">Plan worker schedules</span></span>

- <span data-ttu-id="c9b1d-110">Aplicar perfiles mediante el planificador de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c9b1d-110">Apply profiles by using the work planner.</span></span> <span data-ttu-id="c9b1d-111">Para obtener más información, vea [Aplicar perfiles mediante el planificador de trabajo](https://technet.microsoft.com/library/aa551234.aspx).</span><span class="sxs-lookup"><span data-stu-id="c9b1d-111">For more information, see [Apply profiles using work planner](https://technet.microsoft.com/library/aa551234.aspx).</span></span>

<span data-ttu-id="c9b1d-112">Para obtener información sobre los pasos de configuración, consulte [Configuración del tiempo y la asistencia](https://technet.microsoft.com/library/aa496971.aspx).</span><span class="sxs-lookup"><span data-stu-id="c9b1d-112">For information about the configuration steps, see [Setting up time and attendance](https://technet.microsoft.com/library/aa496971.aspx).</span></span>

### <a name="retail-specific-configuration"></a><span data-ttu-id="c9b1d-113">Configuración específica a la venta minorista</span><span class="sxs-lookup"><span data-stu-id="c9b1d-113">Retail-specific configuration</span></span>

- <span data-ttu-id="c9b1d-114">Habilitar un perfil de funcionalidad para reloj de tiempo, para los trabajadores a los que desee habilitar registros de horas.</span><span class="sxs-lookup"><span data-stu-id="c9b1d-114">Enable a functionality profile for Time Clock, for workers that you want to enable time registrations for.</span></span> <span data-ttu-id="c9b1d-115">Haga clic en **Perfiles de la funcionalidad del PDV** &gt; **Funciones** &gt; **Registros de hora del PDV** &gt; **Habilitar registros de horas**.</span><span class="sxs-lookup"><span data-stu-id="c9b1d-115">Click **POS functionality profiles** &gt; **Functions** &gt; **POS time registrations** &gt; **Enable time registrations**.</span></span>
- <span data-ttu-id="c9b1d-116">Configure grupos de permisos del punto de venta (PDV) para habilitar el permiso de las entradas de Visualizar reloj de tiempo.</span><span class="sxs-lookup"><span data-stu-id="c9b1d-116">Configure point of sale (POS) permissions groups to enable the View timeclock entries permission.</span></span> <span data-ttu-id="c9b1d-117">Este permiso permite que un usuario vea los registros del reloj de tiempo de otros trabajadores en la tienda (y de cualquier otra tienda a la que esté asociado el usuario, a través de la libreta de direcciones).</span><span class="sxs-lookup"><span data-stu-id="c9b1d-117">This permission lets a user view the time clock registrations of other workers in the store (and from any other store that the user is associated with, via the address book).</span></span> <span data-ttu-id="c9b1d-118">Es posible que desee habilitar este permiso para un rol de administrador pero no para un rol de cajero.</span><span class="sxs-lookup"><span data-stu-id="c9b1d-118">You might want to enable this permission for a manager role but not for a cashier role.</span></span> <span data-ttu-id="c9b1d-119">Haga clc en **Grupos de permiso del PDV** &gt; **Ver entradas del reloj de tiempo**.</span><span class="sxs-lookup"><span data-stu-id="c9b1d-119">Click **POS permission groups** &gt; **View time clock entries**.</span></span>

## <a name="register-time"></a><span data-ttu-id="c9b1d-120">Hora de registro</span><span class="sxs-lookup"><span data-stu-id="c9b1d-120">Register time</span></span>

### <a name="cashier-and-non-cashier-time-registrations"></a><span data-ttu-id="c9b1d-121">Registros de tiempo del cajero y fuera del cajero</span><span class="sxs-lookup"><span data-stu-id="c9b1d-121">Cashier and non-cashier time registrations</span></span>

- <span data-ttu-id="c9b1d-122">En PDV:</span><span class="sxs-lookup"><span data-stu-id="c9b1d-122">On POS:</span></span>

    - <span data-ttu-id="c9b1d-123">Operaciones de entrada:</span><span class="sxs-lookup"><span data-stu-id="c9b1d-123">Clock-in operations:</span></span>

        - <span data-ttu-id="c9b1d-124">Inicie sesión con una operación que no sea del cajón o Turno nuevo</span><span class="sxs-lookup"><span data-stu-id="c9b1d-124">Log on with a non-drawer operation or New shift.</span></span>
        - <span data-ttu-id="c9b1d-125">Seleccione una operación del reloj de tiempo</span><span class="sxs-lookup"><span data-stu-id="c9b1d-125">Select a Time Clock operation.</span></span>
        - <span data-ttu-id="c9b1d-126">Seleccione la operación que desee:</span><span class="sxs-lookup"><span data-stu-id="c9b1d-126">Select a desired operation:</span></span>

            - <span data-ttu-id="c9b1d-127">Registrar la hora de entrada</span><span class="sxs-lookup"><span data-stu-id="c9b1d-127">Clock-in</span></span>
            - <span data-ttu-id="c9b1d-128">Descanso de trabajo</span><span class="sxs-lookup"><span data-stu-id="c9b1d-128">Break for Work</span></span>
            - <span data-ttu-id="c9b1d-129">Descanso para el almuerzo</span><span class="sxs-lookup"><span data-stu-id="c9b1d-129">Break for Lunch</span></span>
            - <span data-ttu-id="c9b1d-130">Registrar la hora de salida</span><span class="sxs-lookup"><span data-stu-id="c9b1d-130">Clock-out</span></span>

        <table>
        <thead>
        <tr>
        <th><span data-ttu-id="c9b1d-131">Estado actual</span><span class="sxs-lookup"><span data-stu-id="c9b1d-131">Current state</span></span></th>
        <th><span data-ttu-id="c9b1d-132">Operaciones disponibles</span><span class="sxs-lookup"><span data-stu-id="c9b1d-132">Available operations</span></span></th>
        </tr>
        </thead>
        <tbody>
        <tr>
        <td><span data-ttu-id="c9b1d-133">Registrar la hora de entrada</span><span class="sxs-lookup"><span data-stu-id="c9b1d-133">Clock-in</span></span></td>
        <td>
        <ul>
        <li><span data-ttu-id="c9b1d-134">Descanso de trabajo</span><span class="sxs-lookup"><span data-stu-id="c9b1d-134">Break for Work</span></span></li>
        <li><span data-ttu-id="c9b1d-135">Descanso para el almuerzo</span><span class="sxs-lookup"><span data-stu-id="c9b1d-135">Break for Lunch</span></span></li>
        <li><span data-ttu-id="c9b1d-136">Registrar la hora de salida</span><span class="sxs-lookup"><span data-stu-id="c9b1d-136">Clock-out</span></span></li>
        </ul>
        </td>
        </tr>
        <tr>
        <td><span data-ttu-id="c9b1d-137">Descanso de trabajo</span><span class="sxs-lookup"><span data-stu-id="c9b1d-137">Break for Work</span></span></td>
        <td><span data-ttu-id="c9b1d-138">Registrar la hora de entrada</span><span class="sxs-lookup"><span data-stu-id="c9b1d-138">Clock-in</span></span></td>
        </tr>
        <tr>
        <td><span data-ttu-id="c9b1d-139">Descanso para el almuerzo</span><span class="sxs-lookup"><span data-stu-id="c9b1d-139">Break for Lunch</span></span></td>
        <td><span data-ttu-id="c9b1d-140">Registrar la hora de entrada</span><span class="sxs-lookup"><span data-stu-id="c9b1d-140">Clock-in</span></span></td>
        </tr>
        <tr>
        <td><span data-ttu-id="c9b1d-141">Registrar la hora de salida</span><span class="sxs-lookup"><span data-stu-id="c9b1d-141">Clock-out</span></span></td>
        <td><span data-ttu-id="c9b1d-142">Registrar la hora de entrada</span><span class="sxs-lookup"><span data-stu-id="c9b1d-142">Clock-in</span></span></td>
        </tr>
        </tbody>
        </table>

        <span data-ttu-id="c9b1d-143">[![TimeClockStates](./media/timeclockstates.png)](./media/timeclockstates.png)</span><span class="sxs-lookup"><span data-stu-id="c9b1d-143">[![TimeClockStates](./media/timeclockstates.png)](./media/timeclockstates.png)</span></span>

- <span data-ttu-id="c9b1d-144">Vea el mensaje de confirmación y compruebe que el tiempo de la actividad actual es correcto.</span><span class="sxs-lookup"><span data-stu-id="c9b1d-144">View the confirmation message, and validate that the current activity time is correct.</span></span>
- <span data-ttu-id="c9b1d-145">Libro de registros:</span><span class="sxs-lookup"><span data-stu-id="c9b1d-145">Logbook:</span></span>

    - <span data-ttu-id="c9b1d-146">Haga clic en **Libro de registros** para ver la actividad del reloj de tiempo.</span><span class="sxs-lookup"><span data-stu-id="c9b1d-146">Click **Logbook** to view time clock activity.</span></span>
    - <span data-ttu-id="c9b1d-147">Use los filtros de tiempo para seleccionar diferentes ventanas de tiempo.</span><span class="sxs-lookup"><span data-stu-id="c9b1d-147">Use time filters to select different time windows.</span></span>
    - <span data-ttu-id="c9b1d-148">Si trabaja en varias ubicaciones de tienda, verá los registros de tiempo de todas las tiendas en las que ha registrado el tiempo.</span><span class="sxs-lookup"><span data-stu-id="c9b1d-148">If you work at multiple store locations, you see your time registrations from all the stores where you recorded time.</span></span> <span data-ttu-id="c9b1d-149">Puede usar el filtro de tienda para ver los registros de tiendas de una tienda seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c9b1d-149">You can use the store filter to view time registrations from a selected store.</span></span>

- <span data-ttu-id="c9b1d-150">Diferentes zonas horarias:</span><span class="sxs-lookup"><span data-stu-id="c9b1d-150">Different time zones:</span></span>

    - <span data-ttu-id="c9b1d-151">Si ve el tiempo desde otra ubicación (para el registro de cajero, o mediante **Ver entradas de reloj de tiempo** para una situación de gerente), y esa ubicación se encuentra en una zona horaria diferente, los registros de tiempo que ve se convierten a su zona horaria local.</span><span class="sxs-lookup"><span data-stu-id="c9b1d-151">If you view time from a different location (for the cashier logbook, or by using **View timeclock entries** for a manager scenario), and that location is in a different time zone, the time records that you see are converted to your local time zone.</span></span> <span data-ttu-id="c9b1d-152">Por ejemplo, usted es el gerente de dos tiendas, una en Barcelona y otra en Londres.</span><span class="sxs-lookup"><span data-stu-id="c9b1d-152">For example, you are a manager for two stores, one in Arizona and the other in Nevada.</span></span> <span data-ttu-id="c9b1d-153">Un cajero registra la hora de entrada a las 9:00 de la mañana</span><span class="sxs-lookup"><span data-stu-id="c9b1d-153">A cashier registers a clock-in at 9:00 A.M.</span></span> <span data-ttu-id="c9b1d-154">en Barcelona.</span><span class="sxs-lookup"><span data-stu-id="c9b1d-154">in Arizona.</span></span> <span data-ttu-id="c9b1d-155">En ese momento, en Londres son las 8:00 de la mañana.</span><span class="sxs-lookup"><span data-stu-id="c9b1d-155">At that moment, the time in Nevada is 8:00 A.M.</span></span> <span data-ttu-id="c9b1d-156">Por lo tanto, si está en la tienda de Londres y mira los registros de horas, el registro de hora se marca como 8 de la mañana.</span><span class="sxs-lookup"><span data-stu-id="c9b1d-156">Therefore, if you are in the Nevada store and look at time registration records, the time registration is marked as 8 A.M.</span></span>

## <a name="view-worker-time-registrations"></a><span data-ttu-id="c9b1d-157">Ver registros de horas del trabajador</span><span class="sxs-lookup"><span data-stu-id="c9b1d-157">View worker time registrations</span></span>

### <a name="view-worker-time-registrations-and-filter-by-store-or-activity-type"></a><span data-ttu-id="c9b1d-158">Ver los registros de horas del trabajador y filtrar por tipo de tienda o de actividad</span><span class="sxs-lookup"><span data-stu-id="c9b1d-158">View worker time registrations, and filter by store or activity type</span></span>

<span data-ttu-id="c9b1d-159">En PDV:</span><span class="sxs-lookup"><span data-stu-id="c9b1d-159">On POS:</span></span>

- <span data-ttu-id="c9b1d-160">Seleccione **Ver entradas de reloj de tiempo**.</span><span class="sxs-lookup"><span data-stu-id="c9b1d-160">Select **View timeclock entries**.</span></span>
- <span data-ttu-id="c9b1d-161">Verá actividades de registro del reloj de tiempo de todos los trabajadores asignados a las mismas tiendas a las que usted está asignado.</span><span class="sxs-lookup"><span data-stu-id="c9b1d-161">You see time clock registration activities from all workers that are assigned to the same stores that you're assigned to.</span></span>
- <span data-ttu-id="c9b1d-162">Puede usar los filtros de tipo de actividad y de tienda para filtrar los registros de hora.</span><span class="sxs-lookup"><span data-stu-id="c9b1d-162">You can use the activity type and store filters to filter on time registrations.</span></span>

## <a name="process-and-manage-time-registrations"></a><span data-ttu-id="c9b1d-163">Procesar y gestionar registros de tiempo</span><span class="sxs-lookup"><span data-stu-id="c9b1d-163">Process and manage time registrations</span></span>

<span data-ttu-id="c9b1d-164">Un usuario de Retail sigue al flujo de trabajo para calcular, aprobar y transferir registros de tiempo a las nóminas.</span><span class="sxs-lookup"><span data-stu-id="c9b1d-164">A Retail user follows the workflow to calculate, approve, and transfer time registrations to payroll.</span></span>

### <a name="primary-operations"></a><span data-ttu-id="c9b1d-165">Operaciones primarias</span><span class="sxs-lookup"><span data-stu-id="c9b1d-165">Primary operations</span></span>

- <span data-ttu-id="c9b1d-166">Calcular</span><span class="sxs-lookup"><span data-stu-id="c9b1d-166">Calculate</span></span>
- <span data-ttu-id="c9b1d-167">Aprobar</span><span class="sxs-lookup"><span data-stu-id="c9b1d-167">Approve</span></span>
- <span data-ttu-id="c9b1d-168">Enviar a nóminas</span><span class="sxs-lookup"><span data-stu-id="c9b1d-168">Submit to payroll</span></span>

### <a name="other-common-operations"></a><span data-ttu-id="c9b1d-169">Otras operaciones comunes</span><span class="sxs-lookup"><span data-stu-id="c9b1d-169">Other common operations</span></span>

- <span data-ttu-id="c9b1d-170">Hora de salida en masa</span><span class="sxs-lookup"><span data-stu-id="c9b1d-170">Bulk Clock-out</span></span>
- <span data-ttu-id="c9b1d-171">Registrar ausencias</span><span class="sxs-lookup"><span data-stu-id="c9b1d-171">Register Absence</span></span>

<span data-ttu-id="c9b1d-172">Para obtener más información sobre cómo procesar los registros de tiempo y asistencia, consulte [Procesar registros de tiempo y asistencia](https://technet.microsoft.com/library/aa573180.aspx).</span><span class="sxs-lookup"><span data-stu-id="c9b1d-172">For more information about how to process time and attendance registrations, see [Process time and attendance registrations](https://technet.microsoft.com/library/aa573180.aspx).</span></span>
