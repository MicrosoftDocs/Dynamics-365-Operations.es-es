---
title: Crear un flujo de trabajo de solicitudes de compras y ventas de permisos y ausencias
description: Cree un flujo de trabajo de solicitudes de compras y ventas de permisos y ausencias para comprar y vende solicitudes de bajas de manera coherente en Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 08/20/2020
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
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 15cedc16fbdbb5d25daa262f094a56bb8fe2f5cc
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5892714"
---
# <a name="create-a-buy-and-sell-leave-request-workflow"></a><span data-ttu-id="a686f-103">Crear un flujo de trabajo de solicitudes de compras y ventas de permisos y ausencias</span><span class="sxs-lookup"><span data-stu-id="a686f-103">Create a buy and sell leave request workflow</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="a686f-104">Puede crear un flujo de trabajo en Dynamics 365 Human Resources para administrar las solicitudes de compras y ventas de bajas de forma coherente.</span><span class="sxs-lookup"><span data-stu-id="a686f-104">You can create a workflow in Dynamics 365 Human Resources to consistently manage your buy and sell leave requests.</span></span> <span data-ttu-id="a686f-105">Un flujo de trabajo de **Comprar y vender permisos y ausencias** le permite:</span><span class="sxs-lookup"><span data-stu-id="a686f-105">A **Buy and sell leave** workflow lets you:</span></span>

- <span data-ttu-id="a686f-106">Definir tareas</span><span class="sxs-lookup"><span data-stu-id="a686f-106">Define tasks</span></span>
- <span data-ttu-id="a686f-107">Determinar quién debe completar las tareas</span><span class="sxs-lookup"><span data-stu-id="a686f-107">Determine who must complete the tasks</span></span>
- <span data-ttu-id="a686f-108">Especificar quién puede aprobar o rechazar solicitudes</span><span class="sxs-lookup"><span data-stu-id="a686f-108">Specify who can approve or reject requests</span></span>

## <a name="create-a-buy-and-sell-leave-request-workflow"></a><span data-ttu-id="a686f-109">Crear un flujo de trabajo de solicitudes de compras y ventas de permisos y ausencias</span><span class="sxs-lookup"><span data-stu-id="a686f-109">Create a buy and sell leave request workflow</span></span>

1. <span data-ttu-id="a686f-110">En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="a686f-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="a686f-111">En **Configuración**, seleccione **Flujos de trabajo de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="a686f-111">Under **Setup**, select **Human resource workflows**.</span></span>

3. <span data-ttu-id="a686f-112">Seleccione **Nueva** y luego seleccione **Solicitud de compra y venta de bajas y ausencias**.</span><span class="sxs-lookup"><span data-stu-id="a686f-112">Select **New**, and then select **Buy and sell leave request**.</span></span> 

4. <span data-ttu-id="a686f-113">Cuando el aparezca el cuadro de mensaje **¿Abrir este archivo?**, seleccione **Abrir** e inicie sesión con las credenciales de su empresa.</span><span class="sxs-lookup"><span data-stu-id="a686f-113">When the **Open this file?** message box appears, select **Open** and sign in with your company credentials.</span></span>

5. <span data-ttu-id="a686f-114">Use el editor de flujo de trabajo para crear un flujo de trabajo para sus solicitudes de licencia.</span><span class="sxs-lookup"><span data-stu-id="a686f-114">Use the workflow editor to create a workflow for your leave requests.</span></span> <span data-ttu-id="a686f-115">Para obtener más información sobre cómo trabajar con flujos de trabajo, consulte [Visión general de la creación de flujos de trabajo](../fin-ops-core/fin-ops/organization-administration/create-workflow.md?toc=%2fdynamics365%2fcommerce%2ftoc.json.)</span><span class="sxs-lookup"><span data-stu-id="a686f-115">For more information about working with workflows, see [Create workflows overview](../fin-ops-core/fin-ops/organization-administration/create-workflow.md?toc=%2fdynamics365%2fcommerce%2ftoc.json.)</span></span>

## <a name="leave-and-absence-request-workflow-data-elements"></a><span data-ttu-id="a686f-116">Elementos de datos de flujo de trabajo de solicitudes de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="a686f-116">Leave and absence request workflow data elements</span></span>

<span data-ttu-id="a686f-117">Puede usar los siguientes elementos de datos para crear aprobaciones condicionales o automáticas en flujos de trabajo para solicitudes de compras y ventas de permisos y ausencias:</span><span class="sxs-lookup"><span data-stu-id="a686f-117">You can use the following data elements to create conditional or automatic approvals in workflows for buy and sell leave requests:</span></span>

- <span data-ttu-id="a686f-118">**Importe**</span><span class="sxs-lookup"><span data-stu-id="a686f-118">**Amount**</span></span>
- <span data-ttu-id="a686f-119">**Directiva de compra y venta de bajas**</span><span class="sxs-lookup"><span data-stu-id="a686f-119">**Buy and sell leave policy**</span></span>
- <span data-ttu-id="a686f-120">**Compañía**</span><span class="sxs-lookup"><span data-stu-id="a686f-120">**Company**</span></span>
- <span data-ttu-id="a686f-121">**Creado por**</span><span class="sxs-lookup"><span data-stu-id="a686f-121">**Created by**</span></span>
- <span data-ttu-id="a686f-122">**Fecha y hora de creación**</span><span class="sxs-lookup"><span data-stu-id="a686f-122">**Created date and time**</span></span>
- <span data-ttu-id="a686f-123">**Fecha final**</span><span class="sxs-lookup"><span data-stu-id="a686f-123">**End date**</span></span>
- <span data-ttu-id="a686f-124">**Tipo de baja**</span><span class="sxs-lookup"><span data-stu-id="a686f-124">**Leave type**</span></span>
- <span data-ttu-id="a686f-125">**Modificado por**</span><span class="sxs-lookup"><span data-stu-id="a686f-125">**Modified by**</span></span>
- <span data-ttu-id="a686f-126">**Fecha y hora de modificación**</span><span class="sxs-lookup"><span data-stu-id="a686f-126">**Modified date and time**</span></span>
- <span data-ttu-id="a686f-127">**Id. de solicitud**</span><span class="sxs-lookup"><span data-stu-id="a686f-127">**Request ID**</span></span>
- <span data-ttu-id="a686f-128">**Fecha inicial**</span><span class="sxs-lookup"><span data-stu-id="a686f-128">**Start date**</span></span>
- <span data-ttu-id="a686f-129">**Estado**</span><span class="sxs-lookup"><span data-stu-id="a686f-129">**Status**</span></span> 
- <span data-ttu-id="a686f-130">**Fecha de envío**</span><span class="sxs-lookup"><span data-stu-id="a686f-130">**Submission date**</span></span>
- <span data-ttu-id="a686f-131">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="a686f-131">**Submitted by**</span></span>
- <span data-ttu-id="a686f-132">**Enviado por Recursos Humanos**</span><span class="sxs-lookup"><span data-stu-id="a686f-132">**Submitted by Human resources**</span></span>
- <span data-ttu-id="a686f-133">**Enviado por el Administrador**</span><span class="sxs-lookup"><span data-stu-id="a686f-133">**Submitted by Manager**</span></span>
- <span data-ttu-id="a686f-134">**Enviado por delegación**</span><span class="sxs-lookup"><span data-stu-id="a686f-134">**Submitted on behalf**</span></span>
- <span data-ttu-id="a686f-135">**Trabajador**</span><span class="sxs-lookup"><span data-stu-id="a686f-135">**Worker**</span></span>

## <a name="workflow-examples"></a><span data-ttu-id="a686f-136">Ejemplos de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="a686f-136">Workflow examples</span></span>

<span data-ttu-id="a686f-137">Estos ejemplos muestran cómo puede crear diferentes tipos de condiciones de flujo de trabajo utilizando estos elementos de datos:</span><span class="sxs-lookup"><span data-stu-id="a686f-137">These examples show how you can create different types of workflow conditions by using these data elements:</span></span>

- <span data-ttu-id="a686f-138">Utilice **Enviado por Recursos humanos** y **Enviado por el gerente** en una acción automática para aprobar automáticamente las solicitudes de compra y venta de bajas que estos roles envían en nombre de los empleados.</span><span class="sxs-lookup"><span data-stu-id="a686f-138">Use **Submitted by Human resources** and **Submitted by manager** in an automatic action to automatically approve buy and sell leave requests that these roles submit on behalf of employees.</span></span> <span data-ttu-id="a686f-139">Para obtener más información sobre accciones automáticas, consulte [Configurar procesos de aprobación en un flujo de trabajo](../fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="a686f-139">For more information about automatic actions, see [Configure approval processes in a workflow](../fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow.md).</span></span>

- <span data-ttu-id="a686f-140">User **Tipo de baja** en una declaración condicional o acción automática para controlar cómo el flujo de trabajo enruta las solicitudes con ciertos tipos de bajas.</span><span class="sxs-lookup"><span data-stu-id="a686f-140">Use **Leave type** in a conditional statement or automatic action to control how the workflow routes requests with certain leave types.</span></span>

## <a name="see-also"></a><span data-ttu-id="a686f-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a686f-141">See also</span></span>

[<span data-ttu-id="a686f-142">Visión general de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="a686f-142">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)<br>
[<span data-ttu-id="a686f-143">Gestionar directivas de compra y venta de bajas</span><span class="sxs-lookup"><span data-stu-id="a686f-143">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]