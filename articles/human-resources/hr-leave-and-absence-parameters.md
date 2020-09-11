---
title: Configurar parámetros de bajas y ausencias
description: Defina parámetros de recursos humanos para bajas y ausencias en Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 08/20/2020
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
ms.openlocfilehash: 196c3901b5bc19f73b882bac7d3361e5bcc37e07
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "3712385"
---
# <a name="configure-leave-and-absence-parameters"></a><span data-ttu-id="8a17f-103">Configurar parámetros de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="8a17f-103">Configure leave and absence parameters</span></span>

<span data-ttu-id="8a17f-104">Antes de configurar planes de bajas y ausencias en Dynamics 365 Human Resources, es una buena idea comprobar la configuración de todos los parámetros de recursos humanos relacionados, incluidos los siguientes:</span><span class="sxs-lookup"><span data-stu-id="8a17f-104">Before you set up leave and absence plans in Dynamics 365 Human Resources, it's a good idea to verify the settings for all related human resources parameters, including:</span></span>

- <span data-ttu-id="8a17f-105">Secuencia numérica para solicitudes de licencia</span><span class="sxs-lookup"><span data-stu-id="8a17f-105">Number sequence for leave requests</span></span>
- <span data-ttu-id="8a17f-106">Configuración de Ley de Ausencia Familiar y Médica</span><span class="sxs-lookup"><span data-stu-id="8a17f-106">Family Medical and Leave Act (FMLA) settings</span></span>
- <span data-ttu-id="8a17f-107">Configuración de autoservicio de empleados para solicitudes de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="8a17f-107">Employee self service settings for leave and absence requests</span></span>
- <span data-ttu-id="8a17f-108">Parámetros de permisos y ausencias</span><span class="sxs-lookup"><span data-stu-id="8a17f-108">Leave and absence parameters</span></span>

## <a name="view-and-change-human-resources-parameters"></a><span data-ttu-id="8a17f-109">Ver y cambiar parámetros de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="8a17f-109">View and change human resources parameters</span></span>

1. <span data-ttu-id="8a17f-110">En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="8a17f-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="8a17f-111">En **Configuración**, seleccione **Parámetros de Recursos Humanos**.</span><span class="sxs-lookup"><span data-stu-id="8a17f-111">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="8a17f-112">En la pestaña **Secuencias numéricas**, compruebe el **Código de secuencia numérica** para el **Id. de solicitud de baja** y cambie según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="8a17f-112">On the **Number sequences** tab, verify the **Number sequence code** for **Leave request ID** and change as necessary.</span></span> <span data-ttu-id="8a17f-113">Esta configuración determina la secuencia que se usa para asignar id. automáticamente a solicitudes de bajas.</span><span class="sxs-lookup"><span data-stu-id="8a17f-113">This setting determines the sequence used for automatically assigning IDs to leave requests.</span></span>

4. <span data-ttu-id="8a17f-114">En la pestaña **FMLA**, compruebe la configuración de FMLA y cambie según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="8a17f-114">On the **FMLA** tab, verify the FMLA settings and change as necessary.</span></span>

5. <span data-ttu-id="8a17f-115">En la pestaña **Autoservicio para empleados**, indique si los responsables pueden introducir solicitudes de bajas y ausencias en nombre de sus empleados.</span><span class="sxs-lookup"><span data-stu-id="8a17f-115">On the **Employee self service** tab, indicate whether managers can enter leave and absence requests on behalf of their employees.</span></span>

7. <span data-ttu-id="8a17f-116">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8a17f-116">Select **Save**.</span></span>

## <a name="view-and-change-leave-and-absence-parameters"></a><span data-ttu-id="8a17f-117">Ver y cambiar parámetros de permisos y ausencias</span><span class="sxs-lookup"><span data-stu-id="8a17f-117">View and change leave and absence parameters</span></span>

1. <span data-ttu-id="8a17f-118">En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="8a17f-118">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="8a17f-119">En **Configuración**, seleccione **Parámetros de permisos y ausencias**.</span><span class="sxs-lookup"><span data-stu-id="8a17f-119">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="8a17f-120">En la pestaña **General**, establezca los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="8a17f-120">On the **General** tab, set the following parameters:</span></span>
 
    - <span data-ttu-id="8a17f-121">Establezca **Unidad de permiso y ausencia** a horas o días.</span><span class="sxs-lookup"><span data-stu-id="8a17f-121">Set **Unit for leave and absence** to either hours or days.</span></span> <span data-ttu-id="8a17f-122">Si es días, puede seleccionar **Habilitar definición de medio día** para permitir a los empleados elegir la primera o segunda mitad del día en sus solicitudes de tiempo libre.</span><span class="sxs-lookup"><span data-stu-id="8a17f-122">If days, you can select **Enable half day definition** to allow employees to choose either first or second half of day in their time-off requests.</span></span> 

    - <span data-ttu-id="8a17f-123">Seleccione **Meses de servicio fecha efectiva** para establecer cuándo entran en vigencia las tasas de acumulación para los planes de permisos que utilizan meses de servicio.</span><span class="sxs-lookup"><span data-stu-id="8a17f-123">Select **Months of service effective date** to set when the accrual rates take effect for leave plans using months of service.</span></span>

    - <span data-ttu-id="8a17f-124">Seleccione **Cálculo de saldo** para mostrar los saldos a partir de hoy o del período de acumulación.</span><span class="sxs-lookup"><span data-stu-id="8a17f-124">Select **Balance calculation** to display balances as of today or as of the accrual period.</span></span> <span data-ttu-id="8a17f-125">Si selecciona **Saldo a partir de hoy**, el saldo muestra el total de todas las acumulaciones, ajustes y solicitudes a partir de hoy.</span><span class="sxs-lookup"><span data-stu-id="8a17f-125">If you select **Balance as of today**, the balance displays the total of all accruals, adjustments, and requests as of today.</span></span> <span data-ttu-id="8a17f-126">Si selecciona **Saldo a partir del período de acumulación**, el saldo muestra el total de todas las acumulaciones, ajustes y solicitudes a partir del período de acumulación definido por la frecuencia en el plan de permisos.</span><span class="sxs-lookup"><span data-stu-id="8a17f-126">If you select **Balance as of accrual period**, the balance displays the total of all accruals, adjustments, and requests as of the accrual period defined by the frequency in the leave plan.</span></span> 

    - <span data-ttu-id="8a17f-127">Establezca la hora de inicio para el trabajo por lotes de vencimiento de transferencia.</span><span class="sxs-lookup"><span data-stu-id="8a17f-127">Set the start time for the carry forward expiration batch job.</span></span>  
    
    - <span data-ttu-id="8a17f-128">Seleccione **Sí** para **Permitir que los empleados compren bajas** y **Permitir que los empleados vendan bajas**.</span><span class="sxs-lookup"><span data-stu-id="8a17f-128">Select **Yes** for **Allow employees to buy leave** and **Allow employees to sell leave**.</span></span> <span data-ttu-id="8a17f-129">Si selecciona **Sí** para estas opciones, puede crear políticas de compra y venta de bajas y permitir que los empleados envíen solicitudes de compra y venta de bajas.</span><span class="sxs-lookup"><span data-stu-id="8a17f-129">If you select **Yes** for these options, you can create buy and sell leave policies and enable employees to submit buy and sell leave requests.</span></span>

## <a name="configure-calendar-parameters"></a><span data-ttu-id="8a17f-130">Configurar parámetros de calendario</span><span class="sxs-lookup"><span data-stu-id="8a17f-130">Configure calendar parameters</span></span>

1. <span data-ttu-id="8a17f-131">En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="8a17f-131">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="8a17f-132">En **Configuración**, seleccione **Parámetros de permisos y ausencias**.</span><span class="sxs-lookup"><span data-stu-id="8a17f-132">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="8a17f-133">En la pestaña **Calendario**, compruebe la configuración del calendario según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="8a17f-133">On the **Calendar** tab, change calendar settings as necessary.</span></span>

4. <span data-ttu-id="8a17f-134">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8a17f-134">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a17f-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8a17f-135">See also</span></span>

- [<span data-ttu-id="8a17f-136">Visión general de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="8a17f-136">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
