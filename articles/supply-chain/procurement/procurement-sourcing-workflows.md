---
title: Flujos de trabajo de adquisición y abastecimiento
description: Algunas organizaciones requieren que las solicitudes de compra y los pedidos de compra los apruebe un usuario distinto a la persona que especificó la transacción. Para configurar un proceso de aprobación, puede crear un flujo de trabajo.
author: kamaybac
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 126e9969f312ff7f6a6c64b733708754e7659214
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "5909240"
---
# <a name="procurement-and-sourcing-workflows"></a><span data-ttu-id="ffa4a-104">Flujos de trabajo de adquisición y abastecimiento</span><span class="sxs-lookup"><span data-stu-id="ffa4a-104">Procurement and sourcing workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ffa4a-105">Algunas organizaciones requieren que las solicitudes de compra y los pedidos de compra los apruebe un usuario distinto a la persona que especificó la transacción.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-105">Some organizations require that purchase requisitions and purchase orders are approved by a user other than the person who entered the transaction.</span></span> <span data-ttu-id="ffa4a-106">Para configurar un proceso de aprobación, puede crear un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-106">To set up an approval process, you can create a workflow.</span></span>

<span data-ttu-id="ffa4a-107">Un flujo de trabajo representa un proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-107">A workflow represents a business process.</span></span> <span data-ttu-id="ffa4a-108">El flujo de trabajo define cómo se gestiona un documento en el sistema e indica quién debe completar una tarea o aprobar un documento.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-108">It defines how a document flows through the system and indicates who must complete a task or approve a document.</span></span> <span data-ttu-id="ffa4a-109">El uso del sistema de flujo de trabajo en su organización le ofrece varias ventajas:</span><span class="sxs-lookup"><span data-stu-id="ffa4a-109">There are several benefits of using the workflow system in your organization:</span></span>

- <span data-ttu-id="ffa4a-110">**Procesos coherentes**: puede definir el proceso de aprobación para documentos específicos como, por ejemplo, solicitudes de compra e informes de gastos.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-110">**Consistent processes** — You can define the approval process for specific documents, such as purchase requisitions and expense reports.</span></span> <span data-ttu-id="ffa4a-111">El sistema de flujo de trabajo le ayuda a garantizar que los documentos se procesan y se aprueban de manera coherente y eficaz.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-111">Using the workflow system helps to ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
- <span data-ttu-id="ffa4a-112">**Visibilidad de procesos**: puede realizar el seguimiento del estado, el historial y las medidas de rendimiento de una instancia de flujo de trabajo determinada.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-112">**Process visibility** — You can track the status, history, and performance metrics of a specific workflow instance.</span></span> <span data-ttu-id="ffa4a-113">De este modo puede determinar si los cambios deben realizarse en el flujo de trabajo para mejorar la eficacia.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-113">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
- <span data-ttu-id="ffa4a-114">**Lista de trabajo centralizada**: los usuarios pueden ver una lista de trabajo centralizada para ver las tareas y las aprobaciones de flujo de trabajo que tienen asignadas en todos los flujos de trabajo en los que participan.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-114">**Centralized work list** — Users can view a centralized work list to view the workflow tasks and approvals assigned to them across all workflows they participate in.</span></span> <span data-ttu-id="ffa4a-115">Esta lista de trabajo está disponible en la página Elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-115">This is available in the Work items page.</span></span>

## <a name="the-types-of-workflows-that-you-can-create"></a><span data-ttu-id="ffa4a-116"> Tipos de flujo de trabajo que puede crear</span><span class="sxs-lookup"><span data-stu-id="ffa4a-116">The types of workflows that you can create</span></span>

<span data-ttu-id="ffa4a-117">Los siguientes tipos de flujo de trabajo están disponibles para Adquisición y abastecimiento.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-117">The following workflow types are available for Procurement and sourcing.</span></span>

| <span data-ttu-id="ffa4a-118">Tipo</span><span class="sxs-lookup"><span data-stu-id="ffa4a-118">Type</span></span> | <span data-ttu-id="ffa4a-119">Use este tipo para</span><span class="sxs-lookup"><span data-stu-id="ffa4a-119">Use this type to</span></span> |
|---|---|
| <span data-ttu-id="ffa4a-120">Revisión de solicitudes de compra</span><span class="sxs-lookup"><span data-stu-id="ffa4a-120">Purchase requisition review</span></span> | <span data-ttu-id="ffa4a-121">Crear flujos de trabajo de aprobación y revisión para solicitudes de compra.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-121">Create review and approval workflows for purchase requisitions.</span></span> |
| <span data-ttu-id="ffa4a-122">Revisión de líneas de solicitud de compra</span><span class="sxs-lookup"><span data-stu-id="ffa4a-122">Purchase requisition line review</span></span> | <span data-ttu-id="ffa4a-123">Crear flujos de trabajo de aprobación y revisión para líneas de solicitudes de compra.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-123">Create review and approval workflows for purchase requisition lines.</span></span> |
| <span data-ttu-id="ffa4a-124">Flujo de trabajo del pedido de compra</span><span class="sxs-lookup"><span data-stu-id="ffa4a-124">Purchase order workflow</span></span> | <span data-ttu-id="ffa4a-125">Crear flujos de trabajo de aprobación y revisión para pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-125">Create review and approval workflows for purchase orders.</span></span> |
| <span data-ttu-id="ffa4a-126">Flujo de trabajo de línea del pedido de compra</span><span class="sxs-lookup"><span data-stu-id="ffa4a-126">Purchase order line workflow</span></span> | <span data-ttu-id="ffa4a-127">Crear flujos de trabajo de aprobación y revisión para líneas de pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-127">Create review and approve workflows for purchase order lines.</span></span> |
| <span data-ttu-id="ffa4a-128">Flujo de trabajo de solicitud de adición de proveedor</span><span class="sxs-lookup"><span data-stu-id="ffa4a-128">Vendor add application workflow</span></span> | <span data-ttu-id="ffa4a-129">Cree su revisión y flujos de trabajo de aprobación para agregar nuevos proveedores mediante solicitudes de proveedor.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-129">Create review and approval workflows for adding new vendors via vendor requests.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="ffa4a-130">Cuando agrega un nuevo flujo de trabajo, también puede ver los siguientes flujos de trabajo obsoletos enumerados en el cuadro de diálogo **Crear flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-130">When you are adding a new workflow, you might also see the following obsolete workflows listed in the **Create workflow** dialog box.</span></span> <span data-ttu-id="ffa4a-131">Estos están relacionados con la funcionalidad *Acuse de recibo* que estaba disponible en [Dynamics AX 2012](/dynamicsax-2012/appuser-itpro/set-up-procurement-and-sourcing-workflows), pero que ahora ha quedado obsoleto.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-131">These are related to the *confirmation of receipt* functionality that was available in [Dynamics AX 2012](/dynamicsax-2012/appuser-itpro/set-up-procurement-and-sourcing-workflows), but which has now been deprecated.</span></span> <span data-ttu-id="ffa4a-132">Actualmente, estos flujos de trabajo no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-132">These workflows are currently unsupported.</span></span>
> 
> - <span data-ttu-id="ffa4a-133">Flujo de trabajo de notificación de fecha de vencimiento de entrega</span><span class="sxs-lookup"><span data-stu-id="ffa4a-133">Delivery due date notification workflow</span></span>
> - <span data-ttu-id="ffa4a-134">Flujo de trabajo de notificación de factura recibida</span><span class="sxs-lookup"><span data-stu-id="ffa4a-134">Invoice received notification workflow</span></span>
> - <span data-ttu-id="ffa4a-135">Flujo de trabajo de notificación con error de albarán</span><span class="sxs-lookup"><span data-stu-id="ffa4a-135">Product receipt failed notification workflow</span></span>
> - <span data-ttu-id="ffa4a-136">Flujo de trabajo de notificación de rechazo de albarán sin confirmar</span><span class="sxs-lookup"><span data-stu-id="ffa4a-136">Unconfirmed product receipt rejection notification workflow</span></span>

## <a name="creating-a-workflow"></a><span data-ttu-id="ffa4a-137">Creación de un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="ffa4a-137">Creating a workflow</span></span>

<span data-ttu-id="ffa4a-138">Para crear un flujo de trabajo, vaya a Adquisición y abastecimiento &gt; Configuración &gt; Flujos de trabajo de adquisición y abastecimiento, y cree un nuevo flujo de trabajo seleccionando el tipo de flujo de trabajo que desee crear.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-138">To create a workflow, go to Procurement and sourcing &gt; Setup &gt; Procurement and sourcing workflows and create a new workflow by selecting the type of workflow you want to create.</span></span> 

<span data-ttu-id="ffa4a-139">En el lienzo del flujo de trabajo puede arrastrar elementos de flujo de trabajo al diseñador y vincular los elementos en un flujo.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-139">In the workflow canvas you can drag workflow elements into the designer and link the elements into a flow.</span></span> <span data-ttu-id="ffa4a-140">Se deben configurar los elementos del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-140">The workflow elements should be configured.</span></span> <span data-ttu-id="ffa4a-141">Para los elementos de flujo de trabajo de aprobación y de tarea puede configurar qué participante debe actuar.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-141">For approval and task workflow elements you can configure which participant should take action.</span></span>

## <a name="types-of-participants"></a><span data-ttu-id="ffa4a-142">Tipos de participantes</span><span class="sxs-lookup"><span data-stu-id="ffa4a-142">Types of participants</span></span>

<span data-ttu-id="ffa4a-143">Puede asignar un paso de aprobación a los siguientes grupos de participantes.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-143">You can assign an approval step to the following groups of participants.</span></span>

| <span data-ttu-id="ffa4a-144">Grupo de usuarios</span><span class="sxs-lookup"><span data-stu-id="ffa4a-144">User group</span></span> | <span data-ttu-id="ffa4a-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="ffa4a-145">Description</span></span> |
|---|---|
| <span data-ttu-id="ffa4a-146">Participante</span><span class="sxs-lookup"><span data-stu-id="ffa4a-146">Participant</span></span> | <span data-ttu-id="ffa4a-147">Asignar el paso de aprobación a los miembros de un grupo o rol.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-147">Assign the approval step to members of a group or role.</span></span> |
| <span data-ttu-id="ffa4a-148">Jerarquía</span><span class="sxs-lookup"><span data-stu-id="ffa4a-148">Hierarchy</span></span> | <span data-ttu-id="ffa4a-149">Asignar el paso de aprobación a los usuarios de una jerarquía organizativa específica.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-149">Assign the approval step to users in a specific organizational hierarchy.</span></span> |
| <span data-ttu-id="ffa4a-150">Usuario del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="ffa4a-150">Workflow user</span></span> | <span data-ttu-id="ffa4a-151">Asignar el paso de aprobación a los usuarios de este flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-151">Assign the approval step to users of this workflow.</span></span> |
| <span data-ttu-id="ffa4a-152">Cola</span><span class="sxs-lookup"><span data-stu-id="ffa4a-152">Queue</span></span> | <span data-ttu-id="ffa4a-153">Asignar el paso de aprobación a una cola de elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-153">Assign the approval step to a work item queue.</span></span> |
| <span data-ttu-id="ffa4a-154">Usuario</span><span class="sxs-lookup"><span data-stu-id="ffa4a-154">User</span></span> | <span data-ttu-id="ffa4a-155">Asigne el paso de aprobación a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-155">Assign the approval step to specific users.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="ffa4a-156">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ffa4a-156">Additional resources</span></span>

- [<span data-ttu-id="ffa4a-157">Definición de flujos de trabajo de procesos empresariales para solicitudes de compra</span><span class="sxs-lookup"><span data-stu-id="ffa4a-157">Defining business process workflows for purchase requisitions</span></span>](https://www.microsoft.com/download/details.aspx?id=101821)
- [<span data-ttu-id="ffa4a-158">Flujo de trabajo de solicitudes de compra</span><span class="sxs-lookup"><span data-stu-id="ffa4a-158">Purchase requisition workflow</span></span>](purchase-requisitions-workflow.md)
- [<span data-ttu-id="ffa4a-159">Incorporación de proveedores</span><span class="sxs-lookup"><span data-stu-id="ffa4a-159">Onboard vendors</span></span>](vendor-onboarding.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]