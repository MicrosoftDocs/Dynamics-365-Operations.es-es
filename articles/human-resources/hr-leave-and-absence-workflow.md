---
title: Crear una solicitud de baja de flujo de trabajo
description: Cree un flujo de trabajo de solicitudes de bajas y ausencias para administrar solicitudes de bajas de manera coherente en Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 05/08/2020
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
ms.openlocfilehash: c985a0cb242fb6696b55a2514bd788ff4269f8ca
ms.sourcegitcommit: def66a9dc7feadd33411248af2545ee4a9e27c4f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "3385557"
---
# <a name="create-a-leave-request-workflow"></a><span data-ttu-id="90d8e-103">Crear una solicitud de baja de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="90d8e-103">Create a leave request workflow</span></span>

<span data-ttu-id="90d8e-104">Puede crear un flujo de trabajo en Dynamics 365 Human Resources para administrar solicitudes de bajas y ausencias de manera coherente.</span><span class="sxs-lookup"><span data-stu-id="90d8e-104">You can create a workflow in Dynamics 365 Human Resources to consistently manage your leave and absence requests.</span></span> <span data-ttu-id="90d8e-105">Un flujo de trabajo de **permisos y ausencias** le permite:</span><span class="sxs-lookup"><span data-stu-id="90d8e-105">A **Leave and absence** workflow lets you:</span></span>

- <span data-ttu-id="90d8e-106">Definir tareas</span><span class="sxs-lookup"><span data-stu-id="90d8e-106">Define tasks</span></span>
- <span data-ttu-id="90d8e-107">Determinar quién debe completar las tareas</span><span class="sxs-lookup"><span data-stu-id="90d8e-107">Determine who must complete the tasks</span></span>
- <span data-ttu-id="90d8e-108">Especificar quién puede aprobar o rechazar solicitudes</span><span class="sxs-lookup"><span data-stu-id="90d8e-108">Specify who can approve or reject requests</span></span>

## <a name="create-a-leave-and-absence-request-workflow"></a><span data-ttu-id="90d8e-109">Crear un flujo de trabajo de solicitudes de permisos y ausencias</span><span class="sxs-lookup"><span data-stu-id="90d8e-109">Create a Leave and absence request workflow</span></span>

1. <span data-ttu-id="90d8e-110">En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="90d8e-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="90d8e-111">En **Configuración**, seleccione **Flujos de trabajo de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="90d8e-111">Under **Setup**, select **Human resource workflows**.</span></span>

3. <span data-ttu-id="90d8e-112">Seleccione **Nueva** y luego seleccione **Solicitud de bajas y ausencias**.</span><span class="sxs-lookup"><span data-stu-id="90d8e-112">Select **New**, and then select **Leave and absence request**.</span></span> 

4. <span data-ttu-id="90d8e-113">Cuando el aparezca el cuadro de mensaje **¿Abrir este archivo?**, seleccione **Abrir** e inicie sesión con las credenciales de su empresa.</span><span class="sxs-lookup"><span data-stu-id="90d8e-113">When the **Open this file?** message box appears, select **Open** and sign in with your company credentials.</span></span>

5. <span data-ttu-id="90d8e-114">Use el editor de flujo de trabajo para crear un flujo de trabajo para sus solicitudes de licencia.</span><span class="sxs-lookup"><span data-stu-id="90d8e-114">Use the workflow editor to create a workflow for your leave requests.</span></span> <span data-ttu-id="90d8e-115">Para obtener más información sobre cómo trabajar con flujos de trabajo, consulte [Visión general de la creación de flujos de trabajo](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)</span><span class="sxs-lookup"><span data-stu-id="90d8e-115">For more information about working with workflows, see [Create workflows overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)</span></span>

## <a name="leave-and-absence-request-workflow-data-elements"></a><span data-ttu-id="90d8e-116">Elementos de datos de flujo de trabajo de solicitudes de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="90d8e-116">Leave and absence request workflow data elements</span></span>

<span data-ttu-id="90d8e-117">Puede usar los siguientes elementos de datos para crear aprobaciones condicionales o automáticas en flujos de trabajo para solicitudes de bajas y ausencias:</span><span class="sxs-lookup"><span data-stu-id="90d8e-117">You can use the following data elements to create conditional or automatic approvals in workflows for leave and absence requests:</span></span>

- <span data-ttu-id="90d8e-118">**Importe**</span><span class="sxs-lookup"><span data-stu-id="90d8e-118">**Amount**</span></span>
- <span data-ttu-id="90d8e-119">**Comentar**</span><span class="sxs-lookup"><span data-stu-id="90d8e-119">**Comment**</span></span>
- <span data-ttu-id="90d8e-120">**Compañía**</span><span class="sxs-lookup"><span data-stu-id="90d8e-120">**Company**</span></span>
- <span data-ttu-id="90d8e-121">**Creado por**</span><span class="sxs-lookup"><span data-stu-id="90d8e-121">**Created by**</span></span>
- <span data-ttu-id="90d8e-122">**Fecha y hora de creación**</span><span class="sxs-lookup"><span data-stu-id="90d8e-122">**Created date and time**</span></span>
- <span data-ttu-id="90d8e-123">**Fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="90d8e-123">**End date**</span></span>
- <span data-ttu-id="90d8e-124">**Tipo de baja**</span><span class="sxs-lookup"><span data-stu-id="90d8e-124">**Leave type**</span></span>
- <span data-ttu-id="90d8e-125">**Modificado por**</span><span class="sxs-lookup"><span data-stu-id="90d8e-125">**Modified by**</span></span>
- <span data-ttu-id="90d8e-126">**Fecha y hora de modificación**</span><span class="sxs-lookup"><span data-stu-id="90d8e-126">**Modified date and time**</span></span>
- <span data-ttu-id="90d8e-127">**Código de motivo**</span><span class="sxs-lookup"><span data-stu-id="90d8e-127">**Reason code**</span></span>
- <span data-ttu-id="90d8e-128">**Id. de solicitud**</span><span class="sxs-lookup"><span data-stu-id="90d8e-128">**Request ID**</span></span>
- <span data-ttu-id="90d8e-129">**Fecha de inicio**</span><span class="sxs-lookup"><span data-stu-id="90d8e-129">**Start date**</span></span>
- <span data-ttu-id="90d8e-130">**Estado**</span><span class="sxs-lookup"><span data-stu-id="90d8e-130">**Status**</span></span> 
- <span data-ttu-id="90d8e-131">**Fecha de envío**</span><span class="sxs-lookup"><span data-stu-id="90d8e-131">**Submission date**</span></span>
- <span data-ttu-id="90d8e-132">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="90d8e-132">**Submitted by**</span></span>
- <span data-ttu-id="90d8e-133">**Enviado por Recursos Humanos**</span><span class="sxs-lookup"><span data-stu-id="90d8e-133">**Submitted by Human resources**</span></span>
- <span data-ttu-id="90d8e-134">**Enviado por el Administrador**</span><span class="sxs-lookup"><span data-stu-id="90d8e-134">**Submitted by Manager**</span></span>
- <span data-ttu-id="90d8e-135">**Enviado por delegación**</span><span class="sxs-lookup"><span data-stu-id="90d8e-135">**Submitted on behalf**</span></span>
- <span data-ttu-id="90d8e-136">**Trabajador**</span><span class="sxs-lookup"><span data-stu-id="90d8e-136">**Worker**</span></span>
- <span data-ttu-id="90d8e-137">**Tipo de trabajador**</span><span class="sxs-lookup"><span data-stu-id="90d8e-137">**Worker type**</span></span>

<span data-ttu-id="90d8e-138">Estos ejemplos muestran cómo puede crear diferentes tipos de condiciones de flujo de trabajo utilizando estos elementos de datos:</span><span class="sxs-lookup"><span data-stu-id="90d8e-138">These examples show how you can create different types of workflow conditions by using these data elements:</span></span>

- <span data-ttu-id="90d8e-139">Use **Código de razón** en una declaración condicional para enrutar solicitudes de baja por enfermedad con el código de razón **Cirugía** a RRHH para su aprobación, mientras encamina todos los demás códigos de razón al gerente.</span><span class="sxs-lookup"><span data-stu-id="90d8e-139">Use **Reason code** in a conditional statement to route sick leave requests with the reason code **Surgery** to HR for approval, while routing all other reason codes to the manager.</span></span> <span data-ttu-id="90d8e-140">Para obtener más información sobre las declaraciones condicionales, consulte [Configurar decisiones condicionales en un flujo de trabajo](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow).</span><span class="sxs-lookup"><span data-stu-id="90d8e-140">For more information about conditional statements, see [Configure conditional decisions in a workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow).</span></span> 

- <span data-ttu-id="90d8e-141">Utilizar **Enviado por Recursos humanos** y **Enviado por el gerente** en una acción automática para aprobar automáticamente las solicitudes de baja que estos roles envían en nombre de los empleados.</span><span class="sxs-lookup"><span data-stu-id="90d8e-141">Use **Submitted by Human resources** and **Submitted by manager** in an automatic action to automatically approve leave requests that these roles submit on behalf of employees.</span></span> <span data-ttu-id="90d8e-142">Para obtener más información sobre accciones automáticas, consulte [Configurar procesos de aprobación en un flujo de trabajo](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).</span><span class="sxs-lookup"><span data-stu-id="90d8e-142">For more information about automatic actions, see [Configure approval processes in a workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).</span></span>

- <span data-ttu-id="90d8e-143">User **Tipo de baja** en una declaración condicional o acción automática para controlar cómo el flujo de trabajo enruta las solicitudes con ciertos tipos de bajas.</span><span class="sxs-lookup"><span data-stu-id="90d8e-143">Use **Leave type** in a conditional statement or automatic action to control how the workflow routes requests with certain leave types.</span></span>

## <a name="see-also"></a><span data-ttu-id="90d8e-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="90d8e-144">See also</span></span>

- [<span data-ttu-id="90d8e-145">Visión general de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="90d8e-145">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
