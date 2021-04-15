---
title: Visión general del sistema de flujo de trabajo
description: Este tema describe el sistema de flujo de trabajo.
author: ChrisGarty
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dbcab469e1dc8c139d180abdb7ed0bd8fba488a5
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747744"
---
# <a name="workflow-system-overview"></a><span data-ttu-id="5f25c-103">Visión general del sistema de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5f25c-103">Workflow system overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5f25c-104">Este tema describe el sistema de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5f25c-104">This topic describes the workflow system.</span></span>

## <a name="what-is-workflow"></a><span data-ttu-id="5f25c-105">¿Qué significa flujo de trabajo?</span><span class="sxs-lookup"><span data-stu-id="5f25c-105">What is workflow?</span></span>

<span data-ttu-id="5f25c-106">El término *flujo de trabajo* se puede definir de dos maneras: como sistema y como proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="5f25c-106">The term *workflow* can be defined in two ways: as a system and as a business process.</span></span>

### <a name="workflow-is-a-system"></a><span data-ttu-id="5f25c-107">Flujo de trabajo es un sistema</span><span class="sxs-lookup"><span data-stu-id="5f25c-107">Workflow is a system</span></span>

<span data-ttu-id="5f25c-108">El flujo de trabajo es un sistema que se ejecuta en Application Object Server (AOS).</span><span class="sxs-lookup"><span data-stu-id="5f25c-108">Workflow is a system that runs on the Application Object Server (AOS).</span></span> <span data-ttu-id="5f25c-109">El sistema de flujo de trabajo proporciona funciones que se pueden usar para crear flujos de trabajo individuales, o procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="5f25c-109">The workflow system provides functionality that you can use to create individual workflows, or business processes.</span></span>

### <a name="workflow-is-a-business-process"></a><span data-ttu-id="5f25c-110">Flujo de trabajo es un proceso empresarial</span><span class="sxs-lookup"><span data-stu-id="5f25c-110">Workflow is a business process</span></span>

<span data-ttu-id="5f25c-111">Un flujo de trabajo representa un proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="5f25c-111">A workflow represents a business process.</span></span> <span data-ttu-id="5f25c-112">El flujo de trabajo define el flujo o movimiento de un documento en el sistema al mostrar quién debe completar una tarea, tomar una decisión o aprobar un documento.</span><span class="sxs-lookup"><span data-stu-id="5f25c-112">It defines how a document flows, or moves, through the system by showing who must complete a task, make a decision, or approve a document.</span></span> <span data-ttu-id="5f25c-113">Por ejemplo, en la siguiente ilustración se muestra un flujo de trabajo de informes de gastos.</span><span class="sxs-lookup"><span data-stu-id="5f25c-113">For example, the following illustration shows a workflow for expense reports.</span></span>

![Flujo de trabajo con elementos que están asignados a usuarios](./media/workflow_user.gif)

<span data-ttu-id="5f25c-115">Para comprender mejor este flujo de trabajo, supongamos que Sam envía un informe de gastos por un total de 7.000 USD.</span><span class="sxs-lookup"><span data-stu-id="5f25c-115">To better understand this workflow, suppose that Sam submits an expense report for USD 7,000.</span></span> <span data-ttu-id="5f25c-116">En esta situación, Ivan debe revisar los recibos que Sam le envía.</span><span class="sxs-lookup"><span data-stu-id="5f25c-116">In this scenario, Ivan must review the receipts that Sam routes to him.</span></span> <span data-ttu-id="5f25c-117">A continuación, Frank y Sue deben aprobar el informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="5f25c-117">Then Frank and Sue must approve the expense report.</span></span> <span data-ttu-id="5f25c-118">Ahora supongamos que Sam envía un informe de gastos por un total de 11.000 USD.</span><span class="sxs-lookup"><span data-stu-id="5f25c-118">Now suppose that Sam submits an expense report for USD 11,000.</span></span> <span data-ttu-id="5f25c-119">En esa situación, Ivan debe revisar los recibos y Frank, Sue y Ann deben aprobar el informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="5f25c-119">In this scenario, Ivan must review the receipts, and Frank, Sue, and Ann must approve the expense report.</span></span>

## <a name="benefits-of-using-the-workflow-system"></a><span data-ttu-id="5f25c-120">Ventajas del uso del sistema de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5f25c-120">Benefits of using the workflow system</span></span>

<span data-ttu-id="5f25c-121">El uso del sistema de flujo de trabajo en una organización ofrece varias ventajas:</span><span class="sxs-lookup"><span data-stu-id="5f25c-121">There are several benefits of using the workflow system in your organization:</span></span>

- <span data-ttu-id="5f25c-122">**Procesos coherentes**: puede definir cómo determinados documentos —por ejemplo, solicitudes de compra e informes de gastos— se procesan.</span><span class="sxs-lookup"><span data-stu-id="5f25c-122">**Consistent processes** – You can define how specific documents, such as purchase requisitions and expense reports, are processed.</span></span> <span data-ttu-id="5f25c-123">Al usar el sistema de flujo de trabajo, puede asegurarse de que los documentos se procesarán y aprobarán de manera coherente y eficiente.</span><span class="sxs-lookup"><span data-stu-id="5f25c-123">By using the workflow system, you ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
- <span data-ttu-id="5f25c-124">**Visibilidad de procesos**: puede realizar el seguimiento del estado, el historial y las medidas de rendimiento de las instancias de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5f25c-124">**Process visibility** – You can track the status, history, and performance metrics of workflow instances.</span></span> <span data-ttu-id="5f25c-125">De este modo, puede determinar si se deben realizar cambios en el flujo de trabajo para mejorar la eficiencia.</span><span class="sxs-lookup"><span data-stu-id="5f25c-125">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
- <span data-ttu-id="5f25c-126">**Lista de trabajo centralizada**: los usuarios pueden ver una lista de trabajo centralizada con las tareas y aprobaciones de flujo de trabajo que tienen asignadas.</span><span class="sxs-lookup"><span data-stu-id="5f25c-126">**Centralized work list** – Users can view a centralized work list that displays the workflow tasks and approvals that are assigned to them.</span></span>


## <a name="workflow-content"></a><span data-ttu-id="5f25c-127">Contenido del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5f25c-127">Workflow content</span></span>

+ [<span data-ttu-id="5f25c-128">Arquitectura del sistema de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5f25c-128">Workflow system architecture</span></span>](workflow-system-architecture.md)
+ [<span data-ttu-id="5f25c-129">Elementos del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5f25c-129">Workflow elements</span></span>](workflow-elements.md)
+ [<span data-ttu-id="5f25c-130">Acciones en los procesos de aprobación de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5f25c-130">Actions in workflow approval processes</span></span>](workflow-actions.md)
+ [<span data-ttu-id="5f25c-131">Visión general de la creación de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="5f25c-131">Create workflows overview</span></span>](create-workflow.md)
+ [<span data-ttu-id="5f25c-132">Configurar propiedades del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5f25c-132">Configure workflow properties</span></span>](configure-workflow-properties.md)
+ [<span data-ttu-id="5f25c-133">Configurar tareas manuales en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5f25c-133">Configure manual tasks in a workflow</span></span>](configure-manual-task-workflow.md)
+ [<span data-ttu-id="5f25c-134">Configurar tareas automatizadas en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5f25c-134">Configure automated tasks in a workflow</span></span>](configure-automated-task-workflow.md)
+ [<span data-ttu-id="5f25c-135">Configurar los procesos de aprobación en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5f25c-135">Configure approval processes in a workflow</span></span>](configure-approval-process-workflow.md)
+ [<span data-ttu-id="5f25c-136">Configurar los pasos de aprobación en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5f25c-136">Configure approval steps in a workflow</span></span>](configure-approval-step-workflow.md)
+ [<span data-ttu-id="5f25c-137">Configurar decisiones manuales en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5f25c-137">Configure manual decisions in a workflow</span></span>](configure-manual-decision-workflow.md)
+ [<span data-ttu-id="5f25c-138">Configurar decisiones condicionales en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5f25c-138">Configure conditional decisions in a workflow</span></span>](configure-conditional-decision-workflow.md)
+ [<span data-ttu-id="5f25c-139">Configurar actividades paralelas en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5f25c-139">Configure parallel activities in a workflow</span></span>](configure-parallel-activity-workflow.md)
+ [<span data-ttu-id="5f25c-140">Configurar ramas paralelas en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5f25c-140">Configure parallel branches in a workflow</span></span>](configure-parallel-branch-workflow.md)
+ [<span data-ttu-id="5f25c-141">Configurar flujos de trabajo de elementos</span><span class="sxs-lookup"><span data-stu-id="5f25c-141">Configure line-item workflows</span></span>](configure-line-item-workflow.md)
+ [<span data-ttu-id="5f25c-142">Preguntas frecuentes sobre flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="5f25c-142">Workflow FAQ</span></span>](workflow-FAQ.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]