---
title: Configurar tipos de permisos y ausencias
description: Configure los tipos de baja que los empleados pueden tomar en Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1748ec2a888a50af9b9260720dfd439adc4686f9
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010506"
---
# <a name="configure-leave-and-absence-types"></a><span data-ttu-id="5567f-103">Configurar tipos de permisos y ausencias</span><span class="sxs-lookup"><span data-stu-id="5567f-103">Configure leave and absence types</span></span>

<span data-ttu-id="5567f-104">Los tipos de permisos en Dynamics 365 Human Resources definen los distintos tipos de ausencias que los empleados puedan notificar.</span><span class="sxs-lookup"><span data-stu-id="5567f-104">Leave types in Dynamics 365 Human Resources define the types of absences that employees can report.</span></span> <span data-ttu-id="5567f-105">Puede adaptar los tipos de baja en función de las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="5567f-105">You can tailor leave types according to the needs of your organization.</span></span> <span data-ttu-id="5567f-106">Entre los tipos de baja se incluyen:</span><span class="sxs-lookup"><span data-stu-id="5567f-106">Examples of leave types include:</span></span>

- <span data-ttu-id="5567f-107">Tiempo libre remunerado (PTO)</span><span class="sxs-lookup"><span data-stu-id="5567f-107">Paid time off (PTO)</span></span>
- <span data-ttu-id="5567f-108">Ausencia no retribuida</span><span class="sxs-lookup"><span data-stu-id="5567f-108">Unpaid leave</span></span>
- <span data-ttu-id="5567f-109">Vacaciones pagadas</span><span class="sxs-lookup"><span data-stu-id="5567f-109">Paid vacation</span></span>
- <span data-ttu-id="5567f-110">Baja por enfermedad</span><span class="sxs-lookup"><span data-stu-id="5567f-110">Sick leave</span></span>
- <span data-ttu-id="5567f-111">Baja médica</span><span class="sxs-lookup"><span data-stu-id="5567f-111">Medical leave</span></span>
- <span data-ttu-id="5567f-112">Licencia familiar</span><span class="sxs-lookup"><span data-stu-id="5567f-112">Family leave</span></span>
- <span data-ttu-id="5567f-113">Incapacidad de corta duración</span><span class="sxs-lookup"><span data-stu-id="5567f-113">Short-term disability</span></span>
- <span data-ttu-id="5567f-114">Licencia por duelo</span><span class="sxs-lookup"><span data-stu-id="5567f-114">Bereavement leave</span></span>

## <a name="add-a-leave-type"></a><span data-ttu-id="5567f-115">Agregar un tipo de licencia</span><span class="sxs-lookup"><span data-stu-id="5567f-115">Add a leave type</span></span>

1. <span data-ttu-id="5567f-116">En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="5567f-116">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="5567f-117">En **Configuración**, seleccione **Tipos de permisos y ausencias**.</span><span class="sxs-lookup"><span data-stu-id="5567f-117">Under **Setup**, select **Leave and absence types**.</span></span>

3. <span data-ttu-id="5567f-118">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="5567f-118">Select **New**.</span></span>

4. <span data-ttu-id="5567f-119">Escriba un nombre para el tipo de baja debajo de **Tipo**, seleccione un flujo de trabajo en **Id. de flujo de trabajo** e introduzca una descripción debajo de **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="5567f-119">Enter a name for the leave type under **Type**, select a workflow from **Workflow ID**, and enter a description under **Description**.</span></span>

5. <span data-ttu-id="5567f-120">En **General**, seleccione **Ninguno**, **Programado**o **No programado** en el menú desplegable **Categoría**.</span><span class="sxs-lookup"><span data-stu-id="5567f-120">In **General**, select **None**, **Scheduled**, or **Unscheduled** from the **Category** dropdown.</span></span>

6. <span data-ttu-id="5567f-121">Seleccione un código de ganancia en el menú desplegable **Código de ganancias**.</span><span class="sxs-lookup"><span data-stu-id="5567f-121">Select an earning code from the **Earning code** dropdown.</span></span>

7. <span data-ttu-id="5567f-122">Debajo de **Código de motivo requerido**, elija si desea requerir un código de motivo.</span><span class="sxs-lookup"><span data-stu-id="5567f-122">Under **Reason code required**, choose whether you want to require a reason code.</span></span> <span data-ttu-id="5567f-123">Si desea requerir códigos de motivo, es posible que deba agregarlos.</span><span class="sxs-lookup"><span data-stu-id="5567f-123">If you want to require reason codes, you might need to add them.</span></span> <span data-ttu-id="5567f-124">Debajo de **Códigos de motivo**, seleccione **Agregar**, seleccione un código de motivo y luego seleccione la casilla **Habilitado** que se encuentra al lado.</span><span class="sxs-lookup"><span data-stu-id="5567f-124">Under **Reason codes**, select **Add**, select a reason code, and then select the **Enabled** checkbox next to it.</span></span>

8. <span data-ttu-id="5567f-125">Debajo de **Restringir el acceso a los roles seleccionados**, elija si desea restringir el acceso.</span><span class="sxs-lookup"><span data-stu-id="5567f-125">Under **Restrict access to selected roles**, choose whether you want to restrict access.</span></span> <span data-ttu-id="5567f-126">Luego seleccione los roles de seguridad en **Roles de seguridad para este tipo de permiso**.</span><span class="sxs-lookup"><span data-stu-id="5567f-126">Then select the security roles under **Security roles for this leave type**.</span></span> <span data-ttu-id="5567f-127">Los roles de seguridad se definen en el flujo de trabajo que ha seleccionado en **Id. de flujo de trabajo** anteriormente en este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5567f-127">The security roles are defined in the workflow you selected under **Workflow ID** earlier in this procedure.</span></span>

9. <span data-ttu-id="5567f-128">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5567f-128">Select **Save**.</span></span>

## <a name="configure-preview-features"></a><span data-ttu-id="5567f-129">Configurar características de vista previa</span><span class="sxs-lookup"><span data-stu-id="5567f-129">Configure preview features</span></span>

<span data-ttu-id="5567f-130">Si ha habilitado las características de vista previa para Permisos y ausencias, también debe configurarlas.</span><span class="sxs-lookup"><span data-stu-id="5567f-130">If you've enabled preview features for Leave and absence, you need to configure settings for them, too.</span></span>

[!include [banner](includes/preview-feature-leave-absence.md)]

1. <span data-ttu-id="5567f-131">Establezca opciones de redondeo para el tipo de baja.</span><span class="sxs-lookup"><span data-stu-id="5567f-131">Set rounding options for the leave type.</span></span> <span data-ttu-id="5567f-132">Las opciones incluyen **Ninguno**, **Arriba**, **Abajo** y **Aproximación**.</span><span class="sxs-lookup"><span data-stu-id="5567f-132">Options include **None**, **Up**, **Down**, and **Nearest**.</span></span> <span data-ttu-id="5567f-133">También puede establecer la precisión de redondeo para el tipo de baja.</span><span class="sxs-lookup"><span data-stu-id="5567f-133">You can also set rounding precision for the leave type.</span></span>

2. <span data-ttu-id="5567f-134">Establezca **Corrección de día festivo** para el tipo de baja.</span><span class="sxs-lookup"><span data-stu-id="5567f-134">Set **Holiday correction** for the leave type.</span></span> <span data-ttu-id="5567f-135">Cuando selecciona esta opción, Human Resources usa el número de días festivos que caen en un día laboral para determinar cómo acumular tiempo libre para el tipo de baja.</span><span class="sxs-lookup"><span data-stu-id="5567f-135">When you select this option, Human Resources uses the number of holidays that fall on a work day to determine how to accrue time off for the leave type.</span></span> <span data-ttu-id="5567f-136">Por ejemplo, si el día de Navidad cae en lunes, Human Resources restará un día del tipo de baja al procesar las acumulaciones.</span><span class="sxs-lookup"><span data-stu-id="5567f-136">For example, if Christmas Day falls on a Monday, Human Resources will subtract one day from the leave type when processing accruals.</span></span>

   <span data-ttu-id="5567f-137">Puede establecer días festivos en el calendario de tiempo laborable.</span><span class="sxs-lookup"><span data-stu-id="5567f-137">You set holidays in the working time calendar.</span></span> <span data-ttu-id="5567f-138">Para obtener más información, consulte [Crear un calendario de horas de trabajo](hr-leave-and-absence-working-time-calendar.md).</span><span class="sxs-lookup"><span data-stu-id="5567f-138">For more information, see [Create a working time calendar](hr-leave-and-absence-working-time-calendar.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="5567f-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5567f-139">See also</span></span>

- [<span data-ttu-id="5567f-140">Visión general de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="5567f-140">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="5567f-141">Crear un plan de permisos y ausencias</span><span class="sxs-lookup"><span data-stu-id="5567f-141">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)
- [<span data-ttu-id="5567f-142">Crear un calendario de horas de trabajo</span><span class="sxs-lookup"><span data-stu-id="5567f-142">Create a working time calendar</span></span>](hr-leave-and-absence-working-time-calendar.md)