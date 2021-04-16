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
ms.openlocfilehash: a0ddb3ea3aa7f1941ff486d7a3e1db5846fac3eb
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5790557"
---
# <a name="create-a-buy-and-sell-leave-request-workflow"></a><span data-ttu-id="aed14-103">Crear un flujo de trabajo de solicitudes de compras y ventas de permisos y ausencias</span><span class="sxs-lookup"><span data-stu-id="aed14-103">Create a buy and sell leave request workflow</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="aed14-104">Puede crear un flujo de trabajo en Dynamics 365 Human Resources para administrar las solicitudes de compras y ventas de bajas de forma coherente.</span><span class="sxs-lookup"><span data-stu-id="aed14-104">You can create a workflow in Dynamics 365 Human Resources to consistently manage your buy and sell leave requests.</span></span> <span data-ttu-id="aed14-105">Un flujo de trabajo de **Comprar y vender permisos y ausencias** le permite:</span><span class="sxs-lookup"><span data-stu-id="aed14-105">A **Buy and sell leave** workflow lets you:</span></span>

- <span data-ttu-id="aed14-106">Definir tareas</span><span class="sxs-lookup"><span data-stu-id="aed14-106">Define tasks</span></span>
- <span data-ttu-id="aed14-107">Determinar quién debe completar las tareas</span><span class="sxs-lookup"><span data-stu-id="aed14-107">Determine who must complete the tasks</span></span>
- <span data-ttu-id="aed14-108">Especificar quién puede aprobar o rechazar solicitudes</span><span class="sxs-lookup"><span data-stu-id="aed14-108">Specify who can approve or reject requests</span></span>

## <a name="create-a-buy-and-sell-leave-request-workflow"></a><span data-ttu-id="aed14-109">Crear un flujo de trabajo de solicitudes de compras y ventas de permisos y ausencias</span><span class="sxs-lookup"><span data-stu-id="aed14-109">Create a buy and sell leave request workflow</span></span>

1. <span data-ttu-id="aed14-110">En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="aed14-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="aed14-111">En **Configuración**, seleccione **Flujos de trabajo de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="aed14-111">Under **Setup**, select **Human resource workflows**.</span></span>

3. <span data-ttu-id="aed14-112">Seleccione **Nueva** y luego seleccione **Solicitud de compra y venta de bajas y ausencias**.</span><span class="sxs-lookup"><span data-stu-id="aed14-112">Select **New**, and then select **Buy and sell leave request**.</span></span> 

4. <span data-ttu-id="aed14-113">Cuando el aparezca el cuadro de mensaje **¿Abrir este archivo?**, seleccione **Abrir** e inicie sesión con las credenciales de su empresa.</span><span class="sxs-lookup"><span data-stu-id="aed14-113">When the **Open this file?** message box appears, select **Open** and sign in with your company credentials.</span></span>

5. <span data-ttu-id="aed14-114">Use el editor de flujo de trabajo para crear un flujo de trabajo para sus solicitudes de licencia.</span><span class="sxs-lookup"><span data-stu-id="aed14-114">Use the workflow editor to create a workflow for your leave requests.</span></span> <span data-ttu-id="aed14-115">Para obtener más información sobre cómo trabajar con flujos de trabajo, consulte [Visión general de la creación de flujos de trabajo](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)</span><span class="sxs-lookup"><span data-stu-id="aed14-115">For more information about working with workflows, see [Create workflows overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)</span></span>

## <a name="leave-and-absence-request-workflow-data-elements"></a><span data-ttu-id="aed14-116">Elementos de datos de flujo de trabajo de solicitudes de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="aed14-116">Leave and absence request workflow data elements</span></span>

<span data-ttu-id="aed14-117">Puede usar los siguientes elementos de datos para crear aprobaciones condicionales o automáticas en flujos de trabajo para solicitudes de compras y ventas de permisos y ausencias:</span><span class="sxs-lookup"><span data-stu-id="aed14-117">You can use the following data elements to create conditional or automatic approvals in workflows for buy and sell leave requests:</span></span>

- <span data-ttu-id="aed14-118">**Importe**</span><span class="sxs-lookup"><span data-stu-id="aed14-118">**Amount**</span></span>
- <span data-ttu-id="aed14-119">**Directiva de compra y venta de bajas**</span><span class="sxs-lookup"><span data-stu-id="aed14-119">**Buy and sell leave policy**</span></span>
- <span data-ttu-id="aed14-120">**Compañía**</span><span class="sxs-lookup"><span data-stu-id="aed14-120">**Company**</span></span>
- <span data-ttu-id="aed14-121">**Creado por**</span><span class="sxs-lookup"><span data-stu-id="aed14-121">**Created by**</span></span>
- <span data-ttu-id="aed14-122">**Fecha y hora de creación**</span><span class="sxs-lookup"><span data-stu-id="aed14-122">**Created date and time**</span></span>
- <span data-ttu-id="aed14-123">**Fecha final**</span><span class="sxs-lookup"><span data-stu-id="aed14-123">**End date**</span></span>
- <span data-ttu-id="aed14-124">**Tipo de baja**</span><span class="sxs-lookup"><span data-stu-id="aed14-124">**Leave type**</span></span>
- <span data-ttu-id="aed14-125">**Modificado por**</span><span class="sxs-lookup"><span data-stu-id="aed14-125">**Modified by**</span></span>
- <span data-ttu-id="aed14-126">**Fecha y hora de modificación**</span><span class="sxs-lookup"><span data-stu-id="aed14-126">**Modified date and time**</span></span>
- <span data-ttu-id="aed14-127">**Id. de solicitud**</span><span class="sxs-lookup"><span data-stu-id="aed14-127">**Request ID**</span></span>
- <span data-ttu-id="aed14-128">**Fecha inicial**</span><span class="sxs-lookup"><span data-stu-id="aed14-128">**Start date**</span></span>
- <span data-ttu-id="aed14-129">**Estado**</span><span class="sxs-lookup"><span data-stu-id="aed14-129">**Status**</span></span> 
- <span data-ttu-id="aed14-130">**Fecha de envío**</span><span class="sxs-lookup"><span data-stu-id="aed14-130">**Submission date**</span></span>
- <span data-ttu-id="aed14-131">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="aed14-131">**Submitted by**</span></span>
- <span data-ttu-id="aed14-132">**Enviado por Recursos Humanos**</span><span class="sxs-lookup"><span data-stu-id="aed14-132">**Submitted by Human resources**</span></span>
- <span data-ttu-id="aed14-133">**Enviado por el Administrador**</span><span class="sxs-lookup"><span data-stu-id="aed14-133">**Submitted by Manager**</span></span>
- <span data-ttu-id="aed14-134">**Enviado por delegación**</span><span class="sxs-lookup"><span data-stu-id="aed14-134">**Submitted on behalf**</span></span>
- <span data-ttu-id="aed14-135">**Trabajador**</span><span class="sxs-lookup"><span data-stu-id="aed14-135">**Worker**</span></span>

## <a name="workflow-examples"></a><span data-ttu-id="aed14-136">Ejemplos de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="aed14-136">Workflow examples</span></span>

<span data-ttu-id="aed14-137">Estos ejemplos muestran cómo puede crear diferentes tipos de condiciones de flujo de trabajo utilizando estos elementos de datos:</span><span class="sxs-lookup"><span data-stu-id="aed14-137">These examples show how you can create different types of workflow conditions by using these data elements:</span></span>

- <span data-ttu-id="aed14-138">Utilice **Enviado por Recursos humanos** y **Enviado por el gerente** en una acción automática para aprobar automáticamente las solicitudes de compra y venta de bajas que estos roles envían en nombre de los empleados.</span><span class="sxs-lookup"><span data-stu-id="aed14-138">Use **Submitted by Human resources** and **Submitted by manager** in an automatic action to automatically approve buy and sell leave requests that these roles submit on behalf of employees.</span></span> <span data-ttu-id="aed14-139">Para obtener más información sobre accciones automáticas, consulte [Configurar procesos de aprobación en un flujo de trabajo](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).</span><span class="sxs-lookup"><span data-stu-id="aed14-139">For more information about automatic actions, see [Configure approval processes in a workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).</span></span>

- <span data-ttu-id="aed14-140">User **Tipo de baja** en una declaración condicional o acción automática para controlar cómo el flujo de trabajo enruta las solicitudes con ciertos tipos de bajas.</span><span class="sxs-lookup"><span data-stu-id="aed14-140">Use **Leave type** in a conditional statement or automatic action to control how the workflow routes requests with certain leave types.</span></span>

## <a name="see-also"></a><span data-ttu-id="aed14-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aed14-141">See also</span></span>

[<span data-ttu-id="aed14-142">Visión general de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="aed14-142">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)<br>
[<span data-ttu-id="aed14-143">Gestionar directivas de compra y venta de bajas</span><span class="sxs-lookup"><span data-stu-id="aed14-143">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]