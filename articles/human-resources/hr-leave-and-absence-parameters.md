---
title: Configurar parámetros de bajas y ausencias
description: Defina parámetros de recursos humanos para bajas y ausencias en Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 11/02/2020
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
ms.openlocfilehash: e1b2de94f9d9ac1ada16b6ef0e7628edbc9d683f
ms.sourcegitcommit: ffb5998e611b83c2e4f98323f39e3e8f6419c652
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2020
ms.locfileid: "4420505"
---
# <a name="configure-leave-and-absence-parameters"></a><span data-ttu-id="31032-103">Configurar parámetros de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="31032-103">Configure leave and absence parameters</span></span>

<span data-ttu-id="31032-104">Antes de configurar planes de bajas y ausencias en Dynamics 365 Human Resources, es una buena idea comprobar la configuración de todos los parámetros de recursos humanos relacionados, incluidos los siguientes:</span><span class="sxs-lookup"><span data-stu-id="31032-104">Before you set up leave and absence plans in Dynamics 365 Human Resources, it's a good idea to verify the settings for all related human resources parameters, including:</span></span>

- <span data-ttu-id="31032-105">Secuencia numérica para solicitudes de licencia</span><span class="sxs-lookup"><span data-stu-id="31032-105">Number sequence for leave requests</span></span>
- <span data-ttu-id="31032-106">Configuración de Ley de Ausencia Familiar y Médica</span><span class="sxs-lookup"><span data-stu-id="31032-106">Family Medical and Leave Act (FMLA) settings</span></span>
- <span data-ttu-id="31032-107">Configuración de autoservicio de empleados para solicitudes de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="31032-107">Employee self service settings for leave and absence requests</span></span>
- <span data-ttu-id="31032-108">Parámetros de permisos y ausencias</span><span class="sxs-lookup"><span data-stu-id="31032-108">Leave and absence parameters</span></span>

## <a name="view-and-change-human-resources-parameters"></a><span data-ttu-id="31032-109">Ver y cambiar parámetros de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="31032-109">View and change human resources parameters</span></span>

1. <span data-ttu-id="31032-110">En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="31032-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="31032-111">En **Configuración**, seleccione **Parámetros de Recursos Humanos**.</span><span class="sxs-lookup"><span data-stu-id="31032-111">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="31032-112">En la pestaña **Secuencias numéricas**, compruebe el **Código de secuencia numérica** para el **Id. de solicitud de baja** y cambie según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="31032-112">On the **Number sequences** tab, verify the **Number sequence code** for **Leave request ID** and change as necessary.</span></span> <span data-ttu-id="31032-113">Esta configuración determina la secuencia que se usa para asignar id. automáticamente a solicitudes de bajas.</span><span class="sxs-lookup"><span data-stu-id="31032-113">This setting determines the sequence used for automatically assigning IDs to leave requests.</span></span>

4. <span data-ttu-id="31032-114">En la pestaña **FMLA**, compruebe la configuración de FMLA y cambie según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="31032-114">On the **FMLA** tab, verify the FMLA settings and change as necessary.</span></span>

5. <span data-ttu-id="31032-115">En la pestaña **Autoservicio para empleados**, indique si los responsables pueden introducir solicitudes de bajas y ausencias en nombre de sus empleados.</span><span class="sxs-lookup"><span data-stu-id="31032-115">On the **Employee self service** tab, indicate whether managers can enter leave and absence requests on behalf of their employees.</span></span>

7. <span data-ttu-id="31032-116">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="31032-116">Select **Save**.</span></span>

>[!IMPORTANT]
><span data-ttu-id="31032-117">La visualización de permisos y ausencias en todas las empresas se encuentra actualmente en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="31032-117">Viewing leave and absence across companies is currently in preview.</span></span> <span data-ttu-id="31032-118">Tendrá que habilitarlo en su entorno de **Espacio aislado** para mostrar la opción de permisos y ausencias.</span><span class="sxs-lookup"><span data-stu-id="31032-118">You'll need to enable it in your **Sandbox** environment to display the option for leave and absence.</span></span> <span data-ttu-id="31032-119">Para obtener más información sobre cómo habilitar las características en versión preliminar, consulte [Administrar características](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="31032-119">For more information about enabling preview features, see [Manage features](hr-admin-manage-features.md).</span></span>

## <a name="view-and-change-human-resources-shared-parameters"></a><span data-ttu-id="31032-120">Ver y cambiar parámetros compartidos de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="31032-120">View and change Human resources shared parameters</span></span>

1. <span data-ttu-id="31032-121">En la página **Administración de personal**, seleccione la pestaña **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="31032-121">On the **Personnel management** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="31032-122">En **Configuración**, seleccione **Parámetros compartidos de Recursos Humanos**.</span><span class="sxs-lookup"><span data-stu-id="31032-122">Under **Setup**, select **Human resources shared parameters**.</span></span>

3. <span data-ttu-id="31032-123">En la pestaña **Acceso avanzado**, seleccione **Sí** para **Habilitar la vista de permisos entre empresas**, para permitir que la licencia se vea en toda la empresa.</span><span class="sxs-lookup"><span data-stu-id="31032-123">On the **Advance access** tab, select **Yes** for **Enable cross company leave view** to allow leave to be viewed across company.</span></span>

4. <span data-ttu-id="31032-124">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="31032-124">Select **Save**.</span></span>

## <a name="view-and-change-leave-and-absence-parameters"></a><span data-ttu-id="31032-125">Ver y cambiar parámetros de permisos y ausencias</span><span class="sxs-lookup"><span data-stu-id="31032-125">View and change leave and absence parameters</span></span>

1. <span data-ttu-id="31032-126">En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="31032-126">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="31032-127">En **Configuración**, seleccione **Parámetros de permisos y ausencias**.</span><span class="sxs-lookup"><span data-stu-id="31032-127">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="31032-128">En la pestaña **General**, establezca los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="31032-128">On the **General** tab, set the following parameters:</span></span>
 
    - <span data-ttu-id="31032-129">Establezca **Unidad de permiso y ausencia** a horas o días.</span><span class="sxs-lookup"><span data-stu-id="31032-129">Set **Unit for leave and absence** to either hours or days.</span></span> <span data-ttu-id="31032-130">Si es días, puede seleccionar **Habilitar definición de medio día** para permitir a los empleados elegir la primera o segunda mitad del día en sus solicitudes de tiempo libre.</span><span class="sxs-lookup"><span data-stu-id="31032-130">If days, you can select **Enable half day definition** to allow employees to choose either first or second half of day in their time-off requests.</span></span> 

    - <span data-ttu-id="31032-131">Seleccione **Meses de servicio fecha efectiva** para establecer cuándo entran en vigencia las tasas de acumulación para los planes de permisos que utilizan meses de servicio.</span><span class="sxs-lookup"><span data-stu-id="31032-131">Select **Months of service effective date** to set when the accrual rates take effect for leave plans using months of service.</span></span>

    - <span data-ttu-id="31032-132">Seleccione **Cálculo de saldo** para mostrar los saldos a partir de hoy o del período de acumulación.</span><span class="sxs-lookup"><span data-stu-id="31032-132">Select **Balance calculation** to display balances as of today or as of the accrual period.</span></span> <span data-ttu-id="31032-133">Si selecciona **Saldo a partir de hoy**, el saldo muestra el total de todas las acumulaciones, ajustes y solicitudes a partir de hoy.</span><span class="sxs-lookup"><span data-stu-id="31032-133">If you select **Balance as of today**, the balance displays the total of all accruals, adjustments, and requests as of today.</span></span> <span data-ttu-id="31032-134">Si selecciona **Saldo a partir del período de acumulación**, el saldo muestra el total de todas las acumulaciones, ajustes y solicitudes a partir del período de acumulación definido por la frecuencia en el plan de permisos.</span><span class="sxs-lookup"><span data-stu-id="31032-134">If you select **Balance as of accrual period**, the balance displays the total of all accruals, adjustments, and requests as of the accrual period defined by the frequency in the leave plan.</span></span> 

    - <span data-ttu-id="31032-135">Establezca la hora de inicio para el trabajo por lotes de vencimiento de transferencia.</span><span class="sxs-lookup"><span data-stu-id="31032-135">Set the start time for the carry forward expiration batch job.</span></span>  
    
    - <span data-ttu-id="31032-136">Seleccione **Sí** para **Permitir que los empleados compren bajas** y **Permitir que los empleados vendan bajas**.</span><span class="sxs-lookup"><span data-stu-id="31032-136">Select **Yes** for **Allow employees to buy leave** and **Allow employees to sell leave**.</span></span> <span data-ttu-id="31032-137">Si selecciona **Sí** para estas opciones, puede crear políticas de compra y venta de bajas y permitir que los empleados envíen solicitudes de compra y venta de bajas.</span><span class="sxs-lookup"><span data-stu-id="31032-137">If you select **Yes** for these options, you can create buy and sell leave policies and enable employees to submit buy and sell leave requests.</span></span>

## <a name="configure-calendar-parameters"></a><span data-ttu-id="31032-138">Configurar parámetros de calendario</span><span class="sxs-lookup"><span data-stu-id="31032-138">Configure calendar parameters</span></span>

1. <span data-ttu-id="31032-139">En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="31032-139">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="31032-140">En **Configuración**, seleccione **Parámetros de permisos y ausencias**.</span><span class="sxs-lookup"><span data-stu-id="31032-140">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="31032-141">En la pestaña **Calendario**, compruebe la configuración del calendario según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="31032-141">On the **Calendar** tab, change calendar settings as necessary.</span></span>

4. <span data-ttu-id="31032-142">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="31032-142">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="31032-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="31032-143">See also</span></span>

- [<span data-ttu-id="31032-144">Visión general de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="31032-144">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
