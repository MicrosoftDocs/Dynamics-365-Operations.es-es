---
title: Elementos del flujo de trabajo
description: Este tema describe los diversos elementos que componen un flujo de trabajo.
author: sericks007
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 56441
ms.assetid: de740262-6ffd-42b9-a325-540eae5cec94
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6df767c2db6d5d9addce5f91544686628ab064dd
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179860"
---
# <a name="workflow-elements"></a><span data-ttu-id="86ad6-103">Elementos del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="86ad6-103">Workflow elements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="86ad6-104">Este tema describe los diversos elementos que componen un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="86ad6-104">This topic describes the various elements that make up a workflow.</span></span>

<span data-ttu-id="86ad6-105">Un flujo de trabajo está compuesto por elementos.</span><span class="sxs-lookup"><span data-stu-id="86ad6-105">A workflow consists of elements.</span></span> <span data-ttu-id="86ad6-106">Las secciones que siguen describen cada tipo de elemento.</span><span class="sxs-lookup"><span data-stu-id="86ad6-106">The sections that follow describe each type of element.</span></span>

## <a name="tasks"></a><span data-ttu-id="86ad6-107">Tareas</span><span class="sxs-lookup"><span data-stu-id="86ad6-107">Tasks</span></span>

<span data-ttu-id="86ad6-108">Una *tarea* es una unidad de trabajo que se debe llevar a cabo.</span><span class="sxs-lookup"><span data-stu-id="86ad6-108">A *task* is a unit of work that must be performed.</span></span> <span data-ttu-id="86ad6-109">A un flujo de trabajo se le pueden agregar dos tipos de tareas: tareas manuales o tareas automatizadas.</span><span class="sxs-lookup"><span data-stu-id="86ad6-109">Two types of tasks can be added to a workflow: manual tasks and automated tasks.</span></span>

### <a name="manual-task"></a><span data-ttu-id="86ad6-110">Tarea manual</span><span class="sxs-lookup"><span data-stu-id="86ad6-110">Manual task</span></span>

<span data-ttu-id="86ad6-111">Una *tarea manual* es una unidad de trabajo que debe llevar a cabo un usuario.</span><span class="sxs-lookup"><span data-stu-id="86ad6-111">A *manual task* is a unit of work that must be performed by a user.</span></span> <span data-ttu-id="86ad6-112">Por ejemplo, un flujo de trabajo de informe de gastos podría incluir tareas manuales que requieran que los usuarios asignados realicen las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="86ad6-112">For example, an expense report workflow can have manual tasks that require the assigned users to complete the following actions:</span></span>

- <span data-ttu-id="86ad6-113">Revisar los recibos que se envían junto con los informes de gastos.</span><span class="sxs-lookup"><span data-stu-id="86ad6-113">Review the receipts that are submitted together with an expense report.</span></span>
- <span data-ttu-id="86ad6-114">Llamar al director de un empleado.</span><span class="sxs-lookup"><span data-stu-id="86ad6-114">Call an employee's manager.</span></span>

### <a name="automated-task"></a><span data-ttu-id="86ad6-115">Tarea automatizada</span><span class="sxs-lookup"><span data-stu-id="86ad6-115">Automated task</span></span>

<span data-ttu-id="86ad6-116">Una *tarea automatizada* es una unidad de trabajo que debe llevar a cabo el sistema.</span><span class="sxs-lookup"><span data-stu-id="86ad6-116">An *automated task* is a unit of work that must be performed by the system.</span></span> <span data-ttu-id="86ad6-117">No se requiere la intervención del usuario.</span><span class="sxs-lookup"><span data-stu-id="86ad6-117">No human interaction is required.</span></span> <span data-ttu-id="86ad6-118">Por ejemplo, un flujo de trabajo de pedidos de ventas puede incluir tareas automatizadas que requieran que el sistema realice las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="86ad6-118">For example, a sales order workflow can have automated tasks that require the system to complete the following actions:</span></span>

- <span data-ttu-id="86ad6-119">Realizar una comprobación de crédito.</span><span class="sxs-lookup"><span data-stu-id="86ad6-119">Perform a credit check.</span></span>
- <span data-ttu-id="86ad6-120">Crear un registro de cliente para el cliente si no existe ya un registro.</span><span class="sxs-lookup"><span data-stu-id="86ad6-120">Create a customer record for the customer, if a record doesn't already exist.</span></span>

## <a name="approval-processes"></a><span data-ttu-id="86ad6-121">Procesos de aprobación</span><span class="sxs-lookup"><span data-stu-id="86ad6-121">Approval processes</span></span>

<span data-ttu-id="86ad6-122">Un *proceso de aprobación* es un proceso que consta de pasos individuales.</span><span class="sxs-lookup"><span data-stu-id="86ad6-122">An *approval process* is a process that consists of separate steps.</span></span> <span data-ttu-id="86ad6-123">En cada paso de aprobación, el usuario puede realizar las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="86ad6-123">At each approval step, the user can perform the following actions:</span></span>

- <span data-ttu-id="86ad6-124">Aprobar el documento.</span><span class="sxs-lookup"><span data-stu-id="86ad6-124">Approve the document.</span></span>
- <span data-ttu-id="86ad6-125">Rechazar el documento.</span><span class="sxs-lookup"><span data-stu-id="86ad6-125">Reject the document.</span></span>
- <span data-ttu-id="86ad6-126">Solicitar que se realice un cambio en el documento.</span><span class="sxs-lookup"><span data-stu-id="86ad6-126">Request a change to the document.</span></span>
- <span data-ttu-id="86ad6-127">Asignar el documento a otro usuario para que lo apruebe.</span><span class="sxs-lookup"><span data-stu-id="86ad6-127">Assign the document to another user for approval.</span></span>

## <a name="line-item-workflow-elements"></a><span data-ttu-id="86ad6-128">Elementos de flujo de trabajo de elementos</span><span class="sxs-lookup"><span data-stu-id="86ad6-128">Line-item workflow elements</span></span>

<span data-ttu-id="86ad6-129">Se puede crear un flujo de trabajo para procesar documentos o los artículos de línea de un documento.</span><span class="sxs-lookup"><span data-stu-id="86ad6-129">A workflow can be created to process either documents or the line items on a document.</span></span> <span data-ttu-id="86ad6-130">Por ejemplo, ha creado un flujo de trabajo de aprobación para las hojas de horas</span><span class="sxs-lookup"><span data-stu-id="86ad6-130">For example, you've created an approval workflow for timesheets.</span></span> <span data-ttu-id="86ad6-131">(Nos referiremos a este flujo de trabajo por el nombre de *flujo de trabajo de documento*). Puede agregar un *flujo de trabajo de artículos de línea* a dicho flujo de trabajo de documento.</span><span class="sxs-lookup"><span data-stu-id="86ad6-131">(We will refer to this workflow as the *document workflow*.) You can add a *line-item workflow* element to that document workflow.</span></span> <span data-ttu-id="86ad6-132">Cuando se ejecuta el artículo de cada línea en el documento, este se envía para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="86ad6-132">When the line-item element is run, each line item on the document is submitted for processing.</span></span> <span data-ttu-id="86ad6-133">Quizás desee que el mismo flujo de trabajo de elementos procese todos los artículos de línea o, por lo contrario, tal vez prefiera que distintos flujos de trabajo de elementos procesen cada artículo de línea diferente.</span><span class="sxs-lookup"><span data-stu-id="86ad6-133">You might want all the line items to be processed by the same line-item workflow, or you might want each line item to be processed by a different line-item workflow.</span></span> <span data-ttu-id="86ad6-134">Imaginemos que un empleado ha enviado una hoja de horas que se asemeja a la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="86ad6-134">Imagine that an employee has submitted a timesheet that resembles the following figure.</span></span>

![Flujo de trabajo con artículos de línea](./media/workflow_lineitemworkflow.gif)

<span data-ttu-id="86ad6-136">En esta situación, podría crear los siguientes flujos de trabajo de elementos:</span><span class="sxs-lookup"><span data-stu-id="86ad6-136">In this scenario, you might want to create the following line-item workflows:</span></span>

- <span data-ttu-id="86ad6-137">**Flujo de trabajo de elementos 1**: este flujo de trabajo se usa para procesar los artículos de línea cuando el id. de proyecto es 1111.</span><span class="sxs-lookup"><span data-stu-id="86ad6-137">**Line-item workflow 1** – This workflow is used to process line items where the project ID is 1111.</span></span>
- <span data-ttu-id="86ad6-138">**Flujo de trabajo de elementos 2**: este flujo de trabajo se usa para procesar los artículos de línea cuando el id. de proyecto es 2222.</span><span class="sxs-lookup"><span data-stu-id="86ad6-138">**Line-item workflow 2** – This workflow is used to process line items where the project ID is 2222.</span></span>
- <span data-ttu-id="86ad6-139">**Flujo de trabajo de elementos 3**: este flujo de trabajo se usa para procesar los artículos de línea cuando el id. de proyecto es 3333.</span><span class="sxs-lookup"><span data-stu-id="86ad6-139">**Line-item workflow 3** – This workflow is used to process line items where the project ID is 3333.</span></span>

## <a name="flow-control-elements"></a><span data-ttu-id="86ad6-140">Elementos de control de flujo</span><span class="sxs-lookup"><span data-stu-id="86ad6-140">Flow-control elements</span></span>

<span data-ttu-id="86ad6-141">Los siguientes elementos permiten diseñar flujos de trabajo con ramas alternativas o ramas que se ejecutan al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="86ad6-141">The following elements let you design workflows that have alternate branches or branches that run at the same time.</span></span>

### <a name="manual-decision"></a><span data-ttu-id="86ad6-142">Decisión manual</span><span class="sxs-lookup"><span data-stu-id="86ad6-142">Manual decision</span></span>

<span data-ttu-id="86ad6-143">Una *decisión manual* se encuentra en el punto en el que el flujo de trabajo se divide en dos ramas.</span><span class="sxs-lookup"><span data-stu-id="86ad6-143">A *manual decision* is a point where a workflow divides into two branches.</span></span> <span data-ttu-id="86ad6-144">Un usuario debe tomar una decisión, y es esta decisión la que determina la rama que se usa para procesar el documento enviado.</span><span class="sxs-lookup"><span data-stu-id="86ad6-144">A user must make a decision, and this decision determines which branch is used to process the document that was submitted.</span></span>

### <a name="conditional-decision"></a><span data-ttu-id="86ad6-145">Decisión condicional</span><span class="sxs-lookup"><span data-stu-id="86ad6-145">Conditional decision</span></span>

<span data-ttu-id="86ad6-146">Una *decisión condicional* se encuentra también en el punto en el que el flujo de trabajo se divide en dos ramas.</span><span class="sxs-lookup"><span data-stu-id="86ad6-146">A *conditional decision* is also a point where a workflow divides into two branches.</span></span> <span data-ttu-id="86ad6-147">Sin embargo, el sistema decide la rama que se usa para procesar el documento enviado.</span><span class="sxs-lookup"><span data-stu-id="86ad6-147">However, the system decides which branch is used to process the document that was submitted.</span></span> <span data-ttu-id="86ad6-148">Para tomar esta decisión, el sistema evalúa el documento para determinar si reúne las condiciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="86ad6-148">To make this decision, the system evaluates the document to determine whether it meets specified conditions.</span></span>

### <a name="parallel-activity"></a><span data-ttu-id="86ad6-149">Actividad paralela</span><span class="sxs-lookup"><span data-stu-id="86ad6-149">Parallel activity</span></span>

<span data-ttu-id="86ad6-150">Una *actividad paralela* es un elemento de flujo de trabajo que incluye dos o más ramas de flujo de trabajo que se ejecutan al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="86ad6-150">A *parallel activity* is a workflow element that includes two or more workflow branches that run at the same time.</span></span>

### <a name="subworkflow"></a><span data-ttu-id="86ad6-151">Subflujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="86ad6-151">Subworkflow</span></span>

<span data-ttu-id="86ad6-152">Un *subflujo de trabajo* es un flujo de trabajo que se ejecuta en el contexto de otro flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="86ad6-152">A *subworkflow* is a workflow that runs in the context of another workflow.</span></span>
