---
title: Establecer parámetros de administración de beneficios
description: Configure los parámetros para la administración de beneficios en Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
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
ms.openlocfilehash: 9d6d463df08b9ae68047f09316f19e98740a8441
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2020
ms.locfileid: "3229772"
---
# <a name="set-benefits-management-parameters"></a><span data-ttu-id="99a96-103">Establecer parámetros de administración de prestaciones</span><span class="sxs-lookup"><span data-stu-id="99a96-103">Set Benefits management parameters</span></span>

<span data-ttu-id="99a96-104">Para poder configurar planes de licencia en Microsoft Dynamics 365 Human Resources, debe configurar los parámetros de administración de beneficios.</span><span class="sxs-lookup"><span data-stu-id="99a96-104">Before you can set up leave plans in Microsoft Dynamics 365 Human Resources, you must configure Benefits management parameters.</span></span> <span data-ttu-id="99a96-105">Estos parámetros establecen valores predeterminados, códigos de motivo y otras opciones.</span><span class="sxs-lookup"><span data-stu-id="99a96-105">These parameters set default values, reason codes, and other options.</span></span>

## <a name="configure-general-parameters"></a><span data-ttu-id="99a96-106">Configurar parámetros generales</span><span class="sxs-lookup"><span data-stu-id="99a96-106">Configure general parameters</span></span>

1. <span data-ttu-id="99a96-107">En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Parámetros**.</span><span class="sxs-lookup"><span data-stu-id="99a96-107">In the **Benefits management** workspace, under **Setup**, select **Parameters**.</span></span>

2. <span data-ttu-id="99a96-108">En la pestaña **General**, especifique valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="99a96-108">In the **General** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="99a96-109">Campo</span><span class="sxs-lookup"><span data-stu-id="99a96-109">Field</span></span> | <span data-ttu-id="99a96-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="99a96-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="99a96-111">**País/región**</span><span class="sxs-lookup"><span data-stu-id="99a96-111">**Country/region**</span></span> | <span data-ttu-id="99a96-112">El campo **País/región** determina el orden de visualización de los códigos postales o estados.</span><span class="sxs-lookup"><span data-stu-id="99a96-112">The **Country/region** field determines the display order of ZIP codes/states.</span></span> <span data-ttu-id="99a96-113">El país seleccionado aparece primero en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="99a96-113">The selected country displays first in the dropdown list.</span></span> |
   | <span data-ttu-id="99a96-114">**Código de motivo de la inscripción**</span><span class="sxs-lookup"><span data-stu-id="99a96-114">**Enrollment reason code**</span></span> | <span data-ttu-id="99a96-115">Seleccione un código de motivo predeterminado para usarlo cuando se crean planes de empleados durante el proceso de inscripción abierta.</span><span class="sxs-lookup"><span data-stu-id="99a96-115">Select a default reason code to use when employee plans are created during open enrollment processing.</span></span> |
   | <span data-ttu-id="99a96-116">**Código de motivo de cancelación**</span><span class="sxs-lookup"><span data-stu-id="99a96-116">**Cancellation reason code**</span></span> | <span data-ttu-id="99a96-117">El código de motivo que se usará cuando se cancela un plan de beneficios para empleados.</span><span class="sxs-lookup"><span data-stu-id="99a96-117">The reason code to use when an employee benefit plan is canceled.</span></span> <span data-ttu-id="99a96-118">Se muestra en un cuadro de diálogo durante el proceso de cancelación.</span><span class="sxs-lookup"><span data-stu-id="99a96-118">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="99a96-119">Los usuarios pueden cambiarlo en el **Código de motivo de cancelación** si necesario.</span><span class="sxs-lookup"><span data-stu-id="99a96-119">Users can change it the **Cancellation reason code** if necessary.</span></span> |
   | <span data-ttu-id="99a96-120">**Código de motivo de reapertura**</span><span class="sxs-lookup"><span data-stu-id="99a96-120">**Reopen reason code**</span></span> | <span data-ttu-id="99a96-121">El código de motivo que se usará cuando se vuelve a abrir un plan de beneficios para empleados.</span><span class="sxs-lookup"><span data-stu-id="99a96-121">The reason code to use when an employee benefit plan is reopened.</span></span> <span data-ttu-id="99a96-122">Se muestra en un cuadro de diálogo durante el proceso de cancelación.</span><span class="sxs-lookup"><span data-stu-id="99a96-122">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="99a96-123">Los usuarios pueden cambiarlo en **Volver a abrir código de motivo** si necesario.</span><span class="sxs-lookup"><span data-stu-id="99a96-123">Users can change the **Reopen reason code** if necessary.</span></span> | 
   | <span data-ttu-id="99a96-124">**Código de motivo de evento de vida**</span><span class="sxs-lookup"><span data-stu-id="99a96-124">**Life event reason code**</span></span> | <span data-ttu-id="99a96-125">El código de motivo que se usará cuando se produce un evento de vida.</span><span class="sxs-lookup"><span data-stu-id="99a96-125">The reason code to use when a life event occurs.</span></span> |
   | <span data-ttu-id="99a96-126">**Código de motivo del cambio de tasa**</span><span class="sxs-lookup"><span data-stu-id="99a96-126">**Rate change reason code**</span></span> | <span data-ttu-id="99a96-127">El código de motivo que se usará al cancelar y volver a abrir un plan de beneficios para empleados durante el proceso de actualización de cambio de tasa.</span><span class="sxs-lookup"><span data-stu-id="99a96-127">The reason code to use when canceling and reopening an employee benefit plan during the rate change update process.</span></span> <span data-ttu-id="99a96-128">Indica qué registros se modificados por el proceso de actualización de cambio de tasa.</span><span class="sxs-lookup"><span data-stu-id="99a96-128">It indicates which records were changed by the rate change update process.</span></span> |
   | <span data-ttu-id="99a96-129">**Nueva contratación apta**</span><span class="sxs-lookup"><span data-stu-id="99a96-129">**New hire eligible**</span></span> | <span data-ttu-id="99a96-130">Especifica si los nuevos empleados son aptos.</span><span class="sxs-lookup"><span data-stu-id="99a96-130">Specifies whether new hires are eligible.</span></span> |
   | <span data-ttu-id="99a96-131">**Período de inscripción de nueva contratación**</span><span class="sxs-lookup"><span data-stu-id="99a96-131">**New hire enrollment period**</span></span> | <span data-ttu-id="99a96-132">El periodo de tiempo en que se permite la inscripción de nuevos empleados.</span><span class="sxs-lookup"><span data-stu-id="99a96-132">The period of time the new hire enrollment is allowed.</span></span></br></br><span data-ttu-id="99a96-133">**Nota**: Esta configuración anula cualquier período de inscripción de nuevas contrataciones que establezca en la regla de idoneidad de planes.</span><span class="sxs-lookup"><span data-stu-id="99a96-133">**Note**: This setting overrides any new hire enrollment period you set on the plan eligibility rule.</span></span> | 
   | <span data-ttu-id="99a96-134">**Eventos de vida habilitados**</span><span class="sxs-lookup"><span data-stu-id="99a96-134">**Life events enabled**</span></span> | <span data-ttu-id="99a96-135">Permite eventos de vida.</span><span class="sxs-lookup"><span data-stu-id="99a96-135">Enables life events.</span></span> |
   | <span data-ttu-id="99a96-136">**Ocultar formularios de prestaciones heredadas**</span><span class="sxs-lookup"><span data-stu-id="99a96-136">**Hide legacy benefit forms**</span></span> | <span data-ttu-id="99a96-137">Le permite ocultar formularios de beneficios heredados.</span><span class="sxs-lookup"><span data-stu-id="99a96-137">Allows you to hide legacy benefit forms.</span></span> |

3. <span data-ttu-id="99a96-138">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="99a96-138">Select **Save**.</span></span>

## <a name="configure-employee-self-service-parameters"></a><span data-ttu-id="99a96-139">Configura parámetros de autoservicio para empleados</span><span class="sxs-lookup"><span data-stu-id="99a96-139">Configure Employee self service parameters</span></span>

1. <span data-ttu-id="99a96-140">En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Parámetros**.</span><span class="sxs-lookup"><span data-stu-id="99a96-140">In the **Benefits management** workspace, under **Setup**, select **Parameters**.</span></span>

2. <span data-ttu-id="99a96-141">En la pestaña **Autoservicio para empleados**, especifique valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="99a96-141">In the **Employee self service** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="99a96-142">Campo</span><span class="sxs-lookup"><span data-stu-id="99a96-142">Field</span></span> | <span data-ttu-id="99a96-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="99a96-143">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="99a96-144">**Comprobación de prestación**</span><span class="sxs-lookup"><span data-stu-id="99a96-144">**Benefit verification**</span></span> | <span data-ttu-id="99a96-145">El texto de comprobación que se usará durante la comprobación de los beneficios de autoservicio.</span><span class="sxs-lookup"><span data-stu-id="99a96-145">The verification text to use during self-service benefits checkout.</span></span> |
   | <span data-ttu-id="99a96-146">**Seleccionar automáticamente personas designadas**</span><span class="sxs-lookup"><span data-stu-id="99a96-146">**Auto select designees**</span></span> | <span data-ttu-id="99a96-147">Especifica si desea seleccionar automáticamente dependientes y beneficiarios según su idoneidad para las opciones del plan.</span><span class="sxs-lookup"><span data-stu-id="99a96-147">Specifies whether to automatically select dependents and beneficiaries based on their eligibility for plan options.</span></span> |

3. <span data-ttu-id="99a96-148">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="99a96-148">Select **Save**.</span></span>
