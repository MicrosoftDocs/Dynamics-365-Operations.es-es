---
title: Creación de órdenes de trabajo
description: En este tema se explica cómo crear órdenes de trabajo en Administración de activos.
author: johanhoffmann
manager: tfehr
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetMaintenancePlan, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePoolsOpen
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 76306fb31e7e5297e6a5d64b97b5bd09b64349ee
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500583"
---
# <a name="creating-work-orders"></a><span data-ttu-id="c5884-103">Creación de órdenes de trabajo</span><span class="sxs-lookup"><span data-stu-id="c5884-103">Creating work orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c5884-104">Después de programar trabajos de mantenimiento preventivo, el paso siguiente es crear las órdenes de trabajo para los trabajos.</span><span class="sxs-lookup"><span data-stu-id="c5884-104">After you've scheduled preventive maintenance jobs, the next step is to create work orders for them.</span></span> <span data-ttu-id="c5884-105">Puede completar este paso utilizando uno de los programas de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="c5884-105">You can complete this step by using one of the maintenance schedules.</span></span> <span data-ttu-id="c5884-106">Los trabajos programados en un programa de mantenimiento pueden tener distintos tipos de referencia, como se describe en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="c5884-106">The scheduled jobs in a maintenance schedule can have different reference types, as described in the following table.</span></span>

| <span data-ttu-id="c5884-107">Tipo de referencia</span><span class="sxs-lookup"><span data-stu-id="c5884-107">Reference type</span></span> | <span data-ttu-id="c5884-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5884-108">Description</span></span> |
|---|---|
| <span data-ttu-id="c5884-109">Planes de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="c5884-109">Maintenance plans</span></span> | <span data-ttu-id="c5884-110">Trabajos de mantenimiento preventivo basados en los tipos de programas de mantenimiento *Hora* o *Contador*.</span><span class="sxs-lookup"><span data-stu-id="c5884-110">Preventive maintenance jobs that are based on the *Time* or *Counter* maintenance plan type.</span></span> |
| <span data-ttu-id="c5884-111">Rondas de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="c5884-111">Maintenance rounds</span></span> | <span data-ttu-id="c5884-112">Trabajos de mantenimiento preventivo que contienen varios activos que requieren un tipo de mantenimiento similar.</span><span class="sxs-lookup"><span data-stu-id="c5884-112">Preventive maintenance jobs that contain several assets that require a similar type of maintenance.</span></span> |
| <span data-ttu-id="c5884-113">Solicitud de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="c5884-113">Maintenance request</span></span> | <span data-ttu-id="c5884-114">Una solicitud creada manualmente para el mantenimiento o reparación de un activo.</span><span class="sxs-lookup"><span data-stu-id="c5884-114">A manually created request for maintenance or repair of an asset.</span></span> <span data-ttu-id="c5884-115">Esta solicitud se puede convertir en una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c5884-115">This request can be converted to a work order.</span></span> |

## <a name="create-work-orders-based-on-your-maintenance-schedule"></a><span data-ttu-id="c5884-116">Crear órdenes de trabajo basadas en su programa de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="c5884-116">Create work orders based on your maintenance schedule</span></span>

<span data-ttu-id="c5884-117">Para crear órdenes de trabajo basadas en su programa de mantenimiento, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="c5884-117">To create work orders that are based on your maintenance schedule, follow these steps.</span></span>

1. <span data-ttu-id="c5884-118">Abra una de las siguientes páginas, según cómo desee seleccionar los artículos del programa para sus órdenes de trabajo:</span><span class="sxs-lookup"><span data-stu-id="c5884-118">Open one of the following pages, depending on how you want to select schedule items for your work orders:</span></span>

    - <span data-ttu-id="c5884-119">Todo el programa de mantenimiento (**Administración de activos \> Programa de administración \> Todo el programa de mantenimiento**)</span><span class="sxs-lookup"><span data-stu-id="c5884-119">All maintenance schedule (**Asset management \> Management schedule \> All maintenance schedule**)</span></span>
    - <span data-ttu-id="c5884-120">Abra las líneas del programa de mantenimiento (**Administración de activos \> Programa de administración \> Abrir líneas del programa de mantenimiento**)</span><span class="sxs-lookup"><span data-stu-id="c5884-120">Open maintenance schedule lines (**Asset management \> Management schedule \> Open maintenance schedule lines**)</span></span>
    - <span data-ttu-id="c5884-121">Abra los grupos del programa de mantenimiento (**Administración de activos \> Programa de administración \> Abrir grupos del programa de mantenimiento**)</span><span class="sxs-lookup"><span data-stu-id="c5884-121">Open maintenance schedule pools (**Asset management \> Management schedule \> Open maintenance schedule pools**)</span></span>

1. <span data-ttu-id="c5884-122">En la cuadrícula, seleccione la casilla de verificación para cada trabajo de mantenimiento programado para el que desee crear una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c5884-122">In the grid, select the check box for every scheduled maintenance job that you want to create a work order for.</span></span> <span data-ttu-id="c5884-123">Después, en el panel Acciones, seleccione **Orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="c5884-123">Then, on the Action Pane, select **Work order**.</span></span>

    <span data-ttu-id="c5884-124">Aparecerá el cuadro de diálogo **Crear órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="c5884-124">The **Create work orders** dialog box appears.</span></span> <span data-ttu-id="c5884-125">El campo **Horas de previsión de mantenimiento** muestra el número total de horas previstas para las líneas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="c5884-125">The **Maintenance forecast hours** field shows the total number of forecast hours for the selected lines.</span></span>

    ![Cuadro de diálogo Crear órdenes de trabajo](media/18-preventive-maintenance.png)

1. <span data-ttu-id="c5884-127">En la sección **Parámetros**, especifique el número de órdenes de trabajo que se deben crear.</span><span class="sxs-lookup"><span data-stu-id="c5884-127">In the **Parameters** section, specify the number of work orders that should be created.</span></span> <span data-ttu-id="c5884-128">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="c5884-128">Select one of the following options:</span></span>

    - <span data-ttu-id="c5884-129">**Una orden de trabajo por línea**: cree una orden de trabajo por línea de programación de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="c5884-129">**One work order per line** – Create one work order per maintenance schedule line.</span></span>
    - <span data-ttu-id="c5884-130">**Una orden de trabajo por**: cree órdenes de trabajo que se agrupan de acuerdo con la configuración de las otras opciones que están disponibles cuando selecciona esta opción.</span><span class="sxs-lookup"><span data-stu-id="c5884-130">**One work order per** – Create work orders that are grouped according to the settings of the other options that become available when you select this option.</span></span>

1. <span data-ttu-id="c5884-131">En el campo **Tipo de orden de trabajo**, seleccione el tipo de orden de trabajo que se utilizará para todas las órdenes de trabajo que cree.</span><span class="sxs-lookup"><span data-stu-id="c5884-131">In the **Work order type** field, select the work order type to use for all the work orders that you create.</span></span>
1. <span data-ttu-id="c5884-132">Seleccione **Aceptar** para crear las órdenes de trabajo según su configuración.</span><span class="sxs-lookup"><span data-stu-id="c5884-132">Select **OK** to create the work orders according to your settings.</span></span>

## <a name="group-work-order-lines-that-are-automatically-created-while-a-maintenance-plan-runs"></a><span data-ttu-id="c5884-133">Líneas de orden de trabajo grupales que se crean automáticamente mientras se ejecuta un plan de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="c5884-133">Group work order lines that are automatically created while a maintenance plan runs</span></span>

[!INCLUDE [preview-banner-section](../../../includes/preview-banner-section.md)]

<span data-ttu-id="c5884-134">Esta función le permite definir reglas para agrupar líneas de órdenes de trabajo bajo una sola orden de trabajo cuando el sistema está configurado para generar órdenes de trabajo automáticamente, en base a un plan de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="c5884-134">This feature lets you define rules for grouping work order lines under a single work order when the system is set up to generate work orders automatically, based on a maintenance plan.</span></span> <span data-ttu-id="c5884-135">Anteriormente, las órdenes de trabajo generadas automáticamente podían contener solo una línea.</span><span class="sxs-lookup"><span data-stu-id="c5884-135">Previously, automatically generated work orders could contain only one line.</span></span> <span data-ttu-id="c5884-136">Sin embargo, ahora puede agrupar las órdenes de trabajo por, por ejemplo, activo, tipo de activo o ubicación técnica.</span><span class="sxs-lookup"><span data-stu-id="c5884-136">However, you can now group work orders by, for example, asset, asset type, or functional location.</span></span> <span data-ttu-id="c5884-137">(Las órdenes de trabajo generadas manualmente ya se podían agrupar de esta manera, como se describe en la sección anterior de este tema).</span><span class="sxs-lookup"><span data-stu-id="c5884-137">(Manually generated work orders could already be grouped in this way, as described in the previous section of this topic.)</span></span>

### <a name="enable-grouping-for-automatically-generated-work-orders"></a><span data-ttu-id="c5884-138">Habilitar la agrupación para órdenes de trabajo generadas automáticamente</span><span class="sxs-lookup"><span data-stu-id="c5884-138">Enable grouping for automatically generated work orders</span></span>

<span data-ttu-id="c5884-139">Antes de poder usar esta característica debe estar activada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="c5884-139">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="c5884-140">Los administradores pueden usar la configuración de [gestión de funciones](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla.</span><span class="sxs-lookup"><span data-stu-id="c5884-140">Admins can use the [feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="c5884-141">En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="c5884-141">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="c5884-142">**Módulo:** *Administración de activos*</span><span class="sxs-lookup"><span data-stu-id="c5884-142">**Module:** *Asset Management*</span></span>
- <span data-ttu-id="c5884-143">**Nombre de la característica:** *(versión preliminar) aplicar reglas para agrupar órdenes de trabajo mientras ejecuta un plan de mantenimiento*</span><span class="sxs-lookup"><span data-stu-id="c5884-143">**Feature name:** *(Preview) Apply rules for grouping work orders while running a maintenance plan*</span></span>

### <a name="set-up-grouping-for-automatically-generated-work-orders"></a><span data-ttu-id="c5884-144">Configurar la agrupación para órdenes de trabajo generadas automáticamente</span><span class="sxs-lookup"><span data-stu-id="c5884-144">Set up grouping for automatically generated work orders</span></span>

<span data-ttu-id="c5884-145">Para configurar la agrupación para órdenes de trabajo generadas automáticamente, siga los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="c5884-145">To set up grouping for automatically generated work orders, follow these steps.</span></span>

1. <span data-ttu-id="c5884-146">Vaya a **Administración de activos \> Configuración \> Mantenimiento preventivo \> Planes de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="c5884-146">Go to **Asset management \> Setup \> Preventative maintenance \> Maintenance plans**.</span></span>
1. <span data-ttu-id="c5884-147">Para cada plan en el que desee generar órdenes de trabajo agrupadas, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c5884-147">For each plan where you want to generate grouped work orders, follow these steps:</span></span>

    1. <span data-ttu-id="c5884-148">Seleccione el plan en el panel de la lista.</span><span class="sxs-lookup"><span data-stu-id="c5884-148">Select the plan in the list pane.</span></span>
    1. <span data-ttu-id="c5884-149">En la ficha desplegable **Líneas**, asegúrese de que la casilla **Crear automáticamente** está seleccionada en cada línea.</span><span class="sxs-lookup"><span data-stu-id="c5884-149">On the **Lines** FastTab, make sure that the **Auto create** check box is selected on every line.</span></span>

1. <span data-ttu-id="c5884-150">Vaya a **Administración de activos \> Periódico \> Mantenimiento preventivo \> Programar planes de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="c5884-150">Go to **Asset management \> Periodic \> Preventive maintenance \> Schedule maintenance plans**.</span></span>
1. <span data-ttu-id="c5884-151">En el cuadro de diálogo **Programar planes de mantenimiento**, en la sección **Período**, especifique el horizonte de tiempo para el plan (lo lejos que desea anticipar a la hora de encontrar trabajos de mantenimiento programado para los que generar trabajo).</span><span class="sxs-lookup"><span data-stu-id="c5884-151">In the **Schedule maintenance plans** dialog box, in the **Period** section, specify the time horizon for the plan (how far to look ahead when finding scheduled maintenance jobs to generate work for).</span></span>
1. <span data-ttu-id="c5884-152">Establezca la opción **Crear automáticamente una orden de trabajo a partir del programa** a *Sí*.</span><span class="sxs-lookup"><span data-stu-id="c5884-152">Set the **Automatically create work order from schedule** option to *Yes*.</span></span>
1. <span data-ttu-id="c5884-153">En la sección **Orden de trabajo**, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="c5884-153">In the **Work order** section, select one of the following options:</span></span>

    - <span data-ttu-id="c5884-154">**Una orden de trabajo por línea**: cree una orden de trabajo por línea de programación de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="c5884-154">**One work order per line** – Create one work order per maintenance schedule line.</span></span> <span data-ttu-id="c5884-155">(Esta opción proporciona la misma funcionalidad que está disponible cuando la característica *aplicar reglas para agrupar órdenes de trabajo mientras ejecuta un plan de mantenimiento* está desactivada).</span><span class="sxs-lookup"><span data-stu-id="c5884-155">(This option provides the same functionality that is available when the *Apply rules for grouping work orders while running a maintenance plan* feature is turned off.)</span></span>
    - <span data-ttu-id="c5884-156">**Una orden de trabajo por**: cree órdenes de trabajo que se agrupan de acuerdo con la configuración de las otras opciones que están disponibles cuando selecciona esta opción.</span><span class="sxs-lookup"><span data-stu-id="c5884-156">**One work order per** – Create work orders that are grouped according to the settings of the other options that become available when you select this option.</span></span>

1. <span data-ttu-id="c5884-157">Si desea que las opciones se apliquen cuando ejecuta solo algunos de sus planes de mantenimiento, en la ficha desplegable **Registros que incluir**, agregue los filtros que necesite, tal como lo haría con otros trabajos por lotes en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c5884-157">If you want the options to apply when you run only some of your maintenance plans, on the **Records to include** FastTab, add filters as you require, just as you might do for other batch jobs in Microsoft Dynamics 365 Supply Chain Management.</span></span>
1. <span data-ttu-id="c5884-158">En la ficha desplegable **Ejecutar en segundo plano**, configure las opciones de programación y por lotes según lo requiera, tal como lo haría para otros trabajos por lotes en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c5884-158">On the **Run in the background** FastTab, set up batch and scheduling options as you require, just as you might do for other batch jobs in Supply Chain Management.</span></span>
1. <span data-ttu-id="c5884-159">Seleccione **Aceptar** para ejecutar o programar los planes de mantenimiento seleccionados.</span><span class="sxs-lookup"><span data-stu-id="c5884-159">Select **OK** to run and/or schedule the selected maintenance plans.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]