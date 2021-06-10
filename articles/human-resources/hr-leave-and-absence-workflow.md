---
title: Crear una solicitud de baja de flujo de trabajo
description: Cree un flujo de trabajo de solicitudes de bajas y ausencias para administrar solicitudes de bajas de manera coherente en Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 05/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5580b4b07b2d335ad9444a064c726bc4aca1db6a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6056549"
---
# <a name="create-a-leave-request-workflow"></a><span data-ttu-id="d33ec-103">Crear una solicitud de baja de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="d33ec-103">Create a leave request workflow</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="d33ec-104">Puede crear un flujo de trabajo en Dynamics 365 Human Resources para administrar solicitudes de bajas y ausencias de manera coherente.</span><span class="sxs-lookup"><span data-stu-id="d33ec-104">You can create a workflow in Dynamics 365 Human Resources to consistently manage your leave and absence requests.</span></span> <span data-ttu-id="d33ec-105">Un flujo de trabajo de **permisos y ausencias** le permite:</span><span class="sxs-lookup"><span data-stu-id="d33ec-105">A **Leave and absence** workflow lets you:</span></span>

- <span data-ttu-id="d33ec-106">Definir tareas</span><span class="sxs-lookup"><span data-stu-id="d33ec-106">Define tasks</span></span>
- <span data-ttu-id="d33ec-107">Determinar quién debe completar las tareas</span><span class="sxs-lookup"><span data-stu-id="d33ec-107">Determine who must complete the tasks</span></span>
- <span data-ttu-id="d33ec-108">Especificar quién puede aprobar o rechazar solicitudes</span><span class="sxs-lookup"><span data-stu-id="d33ec-108">Specify who can approve or reject requests</span></span>

## <a name="create-a-leave-and-absence-request-workflow"></a><span data-ttu-id="d33ec-109">Crear un flujo de trabajo de solicitudes de permisos y ausencias</span><span class="sxs-lookup"><span data-stu-id="d33ec-109">Create a Leave and absence request workflow</span></span>

1. <span data-ttu-id="d33ec-110">En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="d33ec-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="d33ec-111">En **Configuración**, seleccione **Flujos de trabajo de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="d33ec-111">Under **Setup**, select **Human resource workflows**.</span></span>

3. <span data-ttu-id="d33ec-112">Seleccione **Nueva** y luego seleccione **Solicitud de bajas y ausencias**.</span><span class="sxs-lookup"><span data-stu-id="d33ec-112">Select **New**, and then select **Leave and absence request**.</span></span> 

4. <span data-ttu-id="d33ec-113">Cuando el aparezca el cuadro de mensaje **¿Abrir este archivo?**, seleccione **Abrir** e inicie sesión con las credenciales de su empresa.</span><span class="sxs-lookup"><span data-stu-id="d33ec-113">When the **Open this file?** message box appears, select **Open** and sign in with your company credentials.</span></span>

5. <span data-ttu-id="d33ec-114">Use el editor de flujo de trabajo para crear un flujo de trabajo para sus solicitudes de licencia.</span><span class="sxs-lookup"><span data-stu-id="d33ec-114">Use the workflow editor to create a workflow for your leave requests.</span></span> <span data-ttu-id="d33ec-115">Para obtener más información sobre cómo trabajar con flujos de trabajo, consulte [Visión general de la creación de flujos de trabajo](../fin-ops-core/fin-ops/organization-administration/create-workflow.md?toc=%2fdynamics365%2fcommerce%2ftoc.json.)</span><span class="sxs-lookup"><span data-stu-id="d33ec-115">For more information about working with workflows, see [Create workflows overview](../fin-ops-core/fin-ops/organization-administration/create-workflow.md?toc=%2fdynamics365%2fcommerce%2ftoc.json.)</span></span>

## <a name="leave-and-absence-request-workflow-data-elements"></a><span data-ttu-id="d33ec-116">Elementos de datos de flujo de trabajo de solicitudes de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="d33ec-116">Leave and absence request workflow data elements</span></span>

<span data-ttu-id="d33ec-117">Puede usar los siguientes elementos de datos para crear aprobaciones condicionales o automáticas en flujos de trabajo para solicitudes de bajas y ausencias:</span><span class="sxs-lookup"><span data-stu-id="d33ec-117">You can use the following data elements to create conditional or automatic approvals in workflows for leave and absence requests:</span></span>

- <span data-ttu-id="d33ec-118">**Importe**</span><span class="sxs-lookup"><span data-stu-id="d33ec-118">**Amount**</span></span>
- <span data-ttu-id="d33ec-119">**Comentar**</span><span class="sxs-lookup"><span data-stu-id="d33ec-119">**Comment**</span></span>
- <span data-ttu-id="d33ec-120">**Compañía**</span><span class="sxs-lookup"><span data-stu-id="d33ec-120">**Company**</span></span>
- <span data-ttu-id="d33ec-121">**Creado por**</span><span class="sxs-lookup"><span data-stu-id="d33ec-121">**Created by**</span></span>
- <span data-ttu-id="d33ec-122">**Fecha y hora de creación**</span><span class="sxs-lookup"><span data-stu-id="d33ec-122">**Created date and time**</span></span>
- <span data-ttu-id="d33ec-123">**Fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="d33ec-123">**End date**</span></span>
- <span data-ttu-id="d33ec-124">**Tipo de baja**</span><span class="sxs-lookup"><span data-stu-id="d33ec-124">**Leave type**</span></span>
- <span data-ttu-id="d33ec-125">**Modificado por**</span><span class="sxs-lookup"><span data-stu-id="d33ec-125">**Modified by**</span></span>
- <span data-ttu-id="d33ec-126">**Fecha y hora de modificación**</span><span class="sxs-lookup"><span data-stu-id="d33ec-126">**Modified date and time**</span></span>
- <span data-ttu-id="d33ec-127">**Código de motivo**</span><span class="sxs-lookup"><span data-stu-id="d33ec-127">**Reason code**</span></span>
- <span data-ttu-id="d33ec-128">**Id. de solicitud**</span><span class="sxs-lookup"><span data-stu-id="d33ec-128">**Request ID**</span></span>
- <span data-ttu-id="d33ec-129">**Fecha de inicio**</span><span class="sxs-lookup"><span data-stu-id="d33ec-129">**Start date**</span></span>
- <span data-ttu-id="d33ec-130">**Estado**</span><span class="sxs-lookup"><span data-stu-id="d33ec-130">**Status**</span></span> 
- <span data-ttu-id="d33ec-131">**Fecha de envío**</span><span class="sxs-lookup"><span data-stu-id="d33ec-131">**Submission date**</span></span>
- <span data-ttu-id="d33ec-132">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="d33ec-132">**Submitted by**</span></span>
- <span data-ttu-id="d33ec-133">**Enviado por Recursos Humanos**</span><span class="sxs-lookup"><span data-stu-id="d33ec-133">**Submitted by Human resources**</span></span>
- <span data-ttu-id="d33ec-134">**Enviado por el Administrador**</span><span class="sxs-lookup"><span data-stu-id="d33ec-134">**Submitted by Manager**</span></span>
- <span data-ttu-id="d33ec-135">**Enviado por delegación**</span><span class="sxs-lookup"><span data-stu-id="d33ec-135">**Submitted on behalf**</span></span>
- <span data-ttu-id="d33ec-136">**Trabajador**</span><span class="sxs-lookup"><span data-stu-id="d33ec-136">**Worker**</span></span>
- <span data-ttu-id="d33ec-137">**Tipo de trabajador**</span><span class="sxs-lookup"><span data-stu-id="d33ec-137">**Worker type**</span></span>

<span data-ttu-id="d33ec-138">Estos ejemplos muestran cómo puede crear diferentes tipos de condiciones de flujo de trabajo utilizando estos elementos de datos:</span><span class="sxs-lookup"><span data-stu-id="d33ec-138">These examples show how you can create different types of workflow conditions by using these data elements:</span></span>

- <span data-ttu-id="d33ec-139">Use **Código de razón** en una declaración condicional para enrutar solicitudes de baja por enfermedad con el código de razón **Cirugía** a RRHH para su aprobación, mientras encamina todos los demás códigos de razón al gerente.</span><span class="sxs-lookup"><span data-stu-id="d33ec-139">Use **Reason code** in a conditional statement to route sick leave requests with the reason code **Surgery** to HR for approval, while routing all other reason codes to the manager.</span></span> <span data-ttu-id="d33ec-140">Para obtener más información sobre las declaraciones condicionales, consulte [Configurar decisiones condicionales en un flujo de trabajo](../fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="d33ec-140">For more information about conditional statements, see [Configure conditional decisions in a workflow](../fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow.md).</span></span> 

- <span data-ttu-id="d33ec-141">Utilizar **Enviado por Recursos humanos** y **Enviado por el gerente** en una acción automática para aprobar automáticamente las solicitudes de baja que estos roles envían en nombre de los empleados.</span><span class="sxs-lookup"><span data-stu-id="d33ec-141">Use **Submitted by Human resources** and **Submitted by manager** in an automatic action to automatically approve leave requests that these roles submit on behalf of employees.</span></span> <span data-ttu-id="d33ec-142">Para obtener más información sobre accciones automáticas, consulte [Configurar procesos de aprobación en un flujo de trabajo](../fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="d33ec-142">For more information about automatic actions, see [Configure approval processes in a workflow](../fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow.md).</span></span>

- <span data-ttu-id="d33ec-143">User **Tipo de baja** en una declaración condicional o acción automática para controlar cómo el flujo de trabajo enruta las solicitudes con ciertos tipos de bajas.</span><span class="sxs-lookup"><span data-stu-id="d33ec-143">Use **Leave type** in a conditional statement or automatic action to control how the workflow routes requests with certain leave types.</span></span>

## <a name="see-also"></a><span data-ttu-id="d33ec-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d33ec-144">See also</span></span>

- [<span data-ttu-id="d33ec-145">Visión general de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="d33ec-145">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]