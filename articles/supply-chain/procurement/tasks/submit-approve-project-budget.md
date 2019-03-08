---
title: Enviar y aprobar un presupuesto de proyecto
description: Este procedimiento muestra cómo crear y mostrar el presupuesto para un proyecto.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, ProjBudget, WorkflowSubmitDialog
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f727e19d3f8c424b1c59e52602b7e907151f4492
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "328732"
---
# <a name="submit-and-approve-project-budget"></a><span data-ttu-id="a9e0d-103">Enviar y aprobar un presupuesto de proyecto</span><span class="sxs-lookup"><span data-stu-id="a9e0d-103">Submit and approve project budget</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a9e0d-104">Este procedimiento muestra cómo crear y mostrar el presupuesto para un proyecto.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-104">This procedure shows you how to create and submit the budget for a project.</span></span> 

<span data-ttu-id="a9e0d-105">Cuando usted crea un presupuesto de proyecto, puede especificar los ingresos y los costes calculados para un proyecto y usarlos para controlar las transacciones de proyecto reales.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-105">When you create a project budget, you can enter estimated revenues and costs for a project, and then use those to control actual project transactions.</span></span> <span data-ttu-id="a9e0d-106">Con el presupuesto de proyecto, es necesario enviar todos los presupuestos originales y las revisiones al flujo de trabajo del proyecto para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-106">In project budgeting, all original budgets and revisions must be sent to project workflow for approval.</span></span> <span data-ttu-id="a9e0d-107">El flujo de trabajo proporciona un mayor control sobre el proceso y crea un registro de historial de cambios.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-107">Workflow gives you increased control over the process and creates a change history record.</span></span>

<span data-ttu-id="a9e0d-108">Esta tarea se creó con el conjunto de datos de demostración USSI.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-108">This task was created using the USSI data set.</span></span>

1. <span data-ttu-id="a9e0d-109">Vaya a Gestión de proyectos y contabilidad > Proyectos > Todos los proyectos.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-109">Go to Project management and accounting > Projects > All projects.</span></span>
2. <span data-ttu-id="a9e0d-110">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="a9e0d-111">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="a9e0d-112">En el panel de acciones, haga clic en Plan.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-112">On the Action Pane, click Plan.</span></span>
5. <span data-ttu-id="a9e0d-113">Haga clic en Presupuesto del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-113">Click Project budget.</span></span>
6. <span data-ttu-id="a9e0d-114">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-114">In the Description field, type a value.</span></span>
7. <span data-ttu-id="a9e0d-115">Expandir la sección Costes</span><span class="sxs-lookup"><span data-stu-id="a9e0d-115">Expand the Cost section</span></span>
8. <span data-ttu-id="a9e0d-116">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-116">Click New.</span></span>
9. <span data-ttu-id="a9e0d-117">En el campo de tipo de Transacción, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-117">In the Transaction type field, select an option.</span></span>
10. <span data-ttu-id="a9e0d-118">En el campo Categoría, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-118">In the Category field, enter or select a value.</span></span>
11. <span data-ttu-id="a9e0d-119">En el campo de presupuesto Original, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-119">In the Original budget field, enter a number.</span></span>
12. <span data-ttu-id="a9e0d-120">Expanda la sección Ingresos.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-120">Expand the Revenues section.</span></span>
13. <span data-ttu-id="a9e0d-121">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-121">Click New.</span></span>
14. <span data-ttu-id="a9e0d-122">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-122">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="a9e0d-123">En el campo de tipo de Transacción, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-123">In the Transaction type field, select an option.</span></span>
16. <span data-ttu-id="a9e0d-124">En el campo Categoría, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-124">In the Category field, enter or select a value.</span></span>
17. <span data-ttu-id="a9e0d-125">En el campo de presupuesto Original, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-125">In the Original budget field, enter a number.</span></span>
18. <span data-ttu-id="a9e0d-126">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-126">Click Save.</span></span>
19. <span data-ttu-id="a9e0d-127">Haga clic en Flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-127">Click Workflow.</span></span>
20. <span data-ttu-id="a9e0d-128">Haga clic en Enviar.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-128">Click Submit.</span></span>
21. <span data-ttu-id="a9e0d-129">En el campo Comentario, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-129">In the Comment field, type a value.</span></span>
22. <span data-ttu-id="a9e0d-130">Haga clic en Enviar.</span><span class="sxs-lookup"><span data-stu-id="a9e0d-130">Click Submit.</span></span>

