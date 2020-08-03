---
title: Establecer parámetros de administración de beneficios
description: Configure los parámetros para la administración de beneficios en Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 85bbe5d3b422f2f29f1d1fe8ee269b407da691c2
ms.sourcegitcommit: 9dc5c7dd5877cc6e7cd0059d173bcd8052ba13bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2020
ms.locfileid: "3599365"
---
# <a name="set-benefits-management-parameters"></a><span data-ttu-id="c5668-103">Establecer parámetros de administración de prestaciones</span><span class="sxs-lookup"><span data-stu-id="c5668-103">Set Benefits management parameters</span></span>

<span data-ttu-id="c5668-104">Para poder configurar planes de licencia en Microsoft Dynamics 365 Human Resources, debe configurar los parámetros de administración de beneficios.</span><span class="sxs-lookup"><span data-stu-id="c5668-104">Before you can set up leave plans in Microsoft Dynamics 365 Human Resources, you must configure Benefits management parameters.</span></span> <span data-ttu-id="c5668-105">Estos parámetros establecen valores predeterminados, códigos de motivo y otras opciones.</span><span class="sxs-lookup"><span data-stu-id="c5668-105">These parameters set default values, reason codes, and other options.</span></span>

## <a name="configure-general-parameters"></a><span data-ttu-id="c5668-106">Configurar parámetros generales</span><span class="sxs-lookup"><span data-stu-id="c5668-106">Configure general parameters</span></span>

1. <span data-ttu-id="c5668-107">En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Parámetros compartidos de Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="c5668-107">In the **Benefits management** workspace, under **Setup**, select **Human Resources Shared Parameters**.</span></span>

2. <span data-ttu-id="c5668-108">En la pestaña **General**, especifique valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="c5668-108">In the **General** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="c5668-109">Campo</span><span class="sxs-lookup"><span data-stu-id="c5668-109">Field</span></span> | <span data-ttu-id="c5668-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5668-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="c5668-111">**País/región**</span><span class="sxs-lookup"><span data-stu-id="c5668-111">**Country/region**</span></span> | <span data-ttu-id="c5668-112">El campo **País/región** determina el orden de visualización de los códigos postales o estados.</span><span class="sxs-lookup"><span data-stu-id="c5668-112">The **Country/region** field determines the display order of ZIP codes/states.</span></span> <span data-ttu-id="c5668-113">El país seleccionado aparece primero en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="c5668-113">The selected country displays first in the dropdown list.</span></span> |
   | <span data-ttu-id="c5668-114">**Código de motivo de la inscripción**</span><span class="sxs-lookup"><span data-stu-id="c5668-114">**Enrollment reason code**</span></span> | <span data-ttu-id="c5668-115">Seleccione un código de motivo predeterminado para usarlo cuando se crean planes de empleados durante el proceso de inscripción abierta.</span><span class="sxs-lookup"><span data-stu-id="c5668-115">Select a default reason code to use when employee plans are created during open enrollment processing.</span></span> |
   | <span data-ttu-id="c5668-116">**Código de motivo de cancelación**</span><span class="sxs-lookup"><span data-stu-id="c5668-116">**Cancellation reason code**</span></span> | <span data-ttu-id="c5668-117">El código de motivo que se usará cuando se cancela un plan de beneficios para empleados.</span><span class="sxs-lookup"><span data-stu-id="c5668-117">The reason code to use when an employee benefit plan is canceled.</span></span> <span data-ttu-id="c5668-118">Se muestra en un cuadro de diálogo durante el proceso de cancelación.</span><span class="sxs-lookup"><span data-stu-id="c5668-118">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="c5668-119">Los usuarios pueden cambiarlo en el **Código de motivo de cancelación** si necesario.</span><span class="sxs-lookup"><span data-stu-id="c5668-119">Users can change it the **Cancellation reason code** if necessary.</span></span> |
   | <span data-ttu-id="c5668-120">**Código de motivo de reapertura**</span><span class="sxs-lookup"><span data-stu-id="c5668-120">**Reopen reason code**</span></span> | <span data-ttu-id="c5668-121">El código de motivo que se usará cuando se vuelve a abrir un plan de beneficios para empleados.</span><span class="sxs-lookup"><span data-stu-id="c5668-121">The reason code to use when an employee benefit plan is reopened.</span></span> <span data-ttu-id="c5668-122">Se muestra en un cuadro de diálogo durante el proceso de cancelación.</span><span class="sxs-lookup"><span data-stu-id="c5668-122">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="c5668-123">Los usuarios pueden cambiarlo en **Volver a abrir código de motivo** si necesario.</span><span class="sxs-lookup"><span data-stu-id="c5668-123">Users can change the **Reopen reason code** if necessary.</span></span> | 
   | <span data-ttu-id="c5668-124">**Código de motivo de evento de vida**</span><span class="sxs-lookup"><span data-stu-id="c5668-124">**Life event reason code**</span></span> | <span data-ttu-id="c5668-125">El código de motivo que se usará cuando se produce un evento de vida.</span><span class="sxs-lookup"><span data-stu-id="c5668-125">The reason code to use when a life event occurs.</span></span> |
   | <span data-ttu-id="c5668-126">**Código de motivo del cambio de tasa**</span><span class="sxs-lookup"><span data-stu-id="c5668-126">**Rate change reason code**</span></span> | <span data-ttu-id="c5668-127">El código de motivo que se usará al cancelar y volver a abrir un plan de beneficios para empleados durante el proceso de actualización de cambio de tasa.</span><span class="sxs-lookup"><span data-stu-id="c5668-127">The reason code to use when canceling and reopening an employee benefit plan during the rate change update process.</span></span> <span data-ttu-id="c5668-128">Indica qué registros se modificados por el proceso de actualización de cambio de tasa.</span><span class="sxs-lookup"><span data-stu-id="c5668-128">It indicates which records were changed by the rate change update process.</span></span> |
   | <span data-ttu-id="c5668-129">**Salario anual de prestaciones**</span><span class="sxs-lookup"><span data-stu-id="c5668-129">**Benefits annual salary**</span></span> | <span data-ttu-id="c5668-130">Le permite establecer un importe de **Salario anual de prestaciones** para un empleado.</span><span class="sxs-lookup"><span data-stu-id="c5668-130">Enables you to set a **Benefits annual salary** amount for an employee.</span></span> <span data-ttu-id="c5668-131">Human Resources utilizará el importe **Salario anual de prestaciones** al determinar los importes de cobertura, en lugar del importe anual de compensación fija.</span><span class="sxs-lookup"><span data-stu-id="c5668-131">Human Resources will use the **Benefits annual salary** amount when determing coverage amounts, instead of the fixed compensation annual amount.</span></span> |
   | <span data-ttu-id="c5668-132">**Nueva contratación apta**</span><span class="sxs-lookup"><span data-stu-id="c5668-132">**New hire eligible**</span></span> | <span data-ttu-id="c5668-133">Especifica si los nuevos empleados son aptos.</span><span class="sxs-lookup"><span data-stu-id="c5668-133">Specifies whether new hires are eligible.</span></span> |
   | <span data-ttu-id="c5668-134">**Período de inscripción de nueva contratación**</span><span class="sxs-lookup"><span data-stu-id="c5668-134">**New hire enrollment period**</span></span> | <span data-ttu-id="c5668-135">El periodo de tiempo en que se permite la inscripción de nuevos empleados.</span><span class="sxs-lookup"><span data-stu-id="c5668-135">The period of time the new hire enrollment is allowed.</span></span></br></br><span data-ttu-id="c5668-136">**Nota**: Esta configuración anula cualquier período de inscripción de nuevas contrataciones que establezca en la regla de idoneidad de planes.</span><span class="sxs-lookup"><span data-stu-id="c5668-136">**Note**: This setting overrides any new hire enrollment period you set on the plan eligibility rule.</span></span> |
   | <span data-ttu-id="c5668-137">**Frecuencia de pago predeterminada**</span><span class="sxs-lookup"><span data-stu-id="c5668-137">**Default pay frequency**</span></span> | <span data-ttu-id="c5668-138">La frecuencia de pago predeterminada para usar cuando se agregan nuevos trabajadores.</span><span class="sxs-lookup"><span data-stu-id="c5668-138">The default pay frequency to use when new workers are added.</span></span> |
   | <span data-ttu-id="c5668-139">**Eventos de vida habilitados**</span><span class="sxs-lookup"><span data-stu-id="c5668-139">**Life events enabled**</span></span> | <span data-ttu-id="c5668-140">Permite eventos de vida.</span><span class="sxs-lookup"><span data-stu-id="c5668-140">Enables life events.</span></span> |
   | <span data-ttu-id="c5668-141">**Ocultar formularios de prestaciones heredadas**</span><span class="sxs-lookup"><span data-stu-id="c5668-141">**Hide legacy benefit forms**</span></span> | <span data-ttu-id="c5668-142">Le permite ocultar formularios de beneficios heredados.</span><span class="sxs-lookup"><span data-stu-id="c5668-142">Allows you to hide legacy benefit forms.</span></span> |

3. <span data-ttu-id="c5668-143">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c5668-143">Select **Save**.</span></span>

## <a name="configure-employee-self-service-parameters"></a><span data-ttu-id="c5668-144">Configura parámetros de autoservicio para empleados</span><span class="sxs-lookup"><span data-stu-id="c5668-144">Configure Employee self service parameters</span></span>

1. <span data-ttu-id="c5668-145">En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Parámetros de Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="c5668-145">In the **Benefits management** workspace, under **Setup**, select **Human Resources Parameters**.</span></span>

2. <span data-ttu-id="c5668-146">En la pestaña **Autoservicio para empleados**, especifique valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="c5668-146">In the **Employee self service** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="c5668-147">Campo</span><span class="sxs-lookup"><span data-stu-id="c5668-147">Field</span></span> | <span data-ttu-id="c5668-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5668-148">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="c5668-149">**Comprobación de prestación**</span><span class="sxs-lookup"><span data-stu-id="c5668-149">**Benefit verification**</span></span> | <span data-ttu-id="c5668-150">El texto de comprobación que se usará durante la comprobación de los beneficios de autoservicio.</span><span class="sxs-lookup"><span data-stu-id="c5668-150">The verification text to use during self-service benefits checkout.</span></span> |
   | <span data-ttu-id="c5668-151">**Seleccionar automáticamente personas designadas**</span><span class="sxs-lookup"><span data-stu-id="c5668-151">**Auto select designees**</span></span> | <span data-ttu-id="c5668-152">Especifica si desea seleccionar automáticamente dependientes y beneficiarios según su idoneidad para las opciones del plan.</span><span class="sxs-lookup"><span data-stu-id="c5668-152">Specifies whether to automatically select dependents and beneficiaries based on their eligibility for plan options.</span></span> |

3. <span data-ttu-id="c5668-153">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c5668-153">Select **Save**.</span></span>
