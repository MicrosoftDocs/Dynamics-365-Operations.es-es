---
title: Enviar y aprobar un presupuesto de proyecto
description: Este procedimiento muestra cómo crear y mostrar el presupuesto para un proyecto.
author: RichardLuan
manager: tfehr
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, ProjBudget, WorkflowSubmitDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Service industries
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b871a3fef3515d3a79fb4b55406a93fc16d02faa
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "5018737"
---
# <a name="submit-and-approve-project-budget"></a><span data-ttu-id="c2e4d-103">Enviar y aprobar un presupuesto de proyecto</span><span class="sxs-lookup"><span data-stu-id="c2e4d-103">Submit and approve project budget</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c2e4d-104">Este procedimiento muestra cómo crear y mostrar el presupuesto para un proyecto.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-104">This procedure shows you how to create and submit the budget for a project.</span></span> 

<span data-ttu-id="c2e4d-105">Cuando usted crea un presupuesto de proyecto, puede especificar los ingresos y los costes calculados para un proyecto y usarlos para controlar las transacciones de proyecto reales.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-105">When you create a project budget, you can enter estimated revenues and costs for a project, and then use those to control actual project transactions.</span></span> <span data-ttu-id="c2e4d-106">Con el presupuesto de proyecto, es necesario enviar todos los presupuestos originales y las revisiones al flujo de trabajo del proyecto para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-106">In project budgeting, all original budgets and revisions must be sent to project workflow for approval.</span></span> <span data-ttu-id="c2e4d-107">El flujo de trabajo proporciona un mayor control sobre el proceso y crea un registro de historial de cambios.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-107">Workflow gives you increased control over the process and creates a change history record.</span></span>

<span data-ttu-id="c2e4d-108">Esta tarea se creó con el conjunto de datos de demostración USSI.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-108">This task was created using the USSI data set.</span></span>

1. <span data-ttu-id="c2e4d-109">En el **Panel de navegación**, vaya a **Módulos > Gestión y contabilidad de proyectos > Proyectos > Todos los proyectos**.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-109">In the **Navigation pane**, go to **Modules > Project management and accounting > Projects > All projects**.</span></span>
2. <span data-ttu-id="c2e4d-110">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="c2e4d-111">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="c2e4d-112">En el **panel de acciones**, haga clic en **Plan**.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-112">On the **Action Pane**, click **Plan**.</span></span>
5. <span data-ttu-id="c2e4d-113">Haga clic en **Presupuesto del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-113">Click **Project budget**.</span></span>
6. <span data-ttu-id="c2e4d-114">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-114">In the **Description** field, type a value.</span></span>
7. <span data-ttu-id="c2e4d-115">Expanda la ficha desplegable **Coste**.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-115">Expand the **Cost** fastTab.</span></span>
8. <span data-ttu-id="c2e4d-116">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-116">Click **New**.</span></span>
9. <span data-ttu-id="c2e4d-117">En el campo **Tipo de Transacción**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-117">In the **Transaction type** field, select an option.</span></span>
10. <span data-ttu-id="c2e4d-118">En el campo **Categoría**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-118">In the **Category** field, enter or select a value.</span></span>
11. <span data-ttu-id="c2e4d-119">En el campo **Presupuesto original**, introduzca un número.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-119">In the **Original budget** field, enter a number.</span></span>
12. <span data-ttu-id="c2e4d-120">Expanda la ficha desplegable **Ingresos**.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-120">Expand the **Revenues** fastTab.</span></span>
13. <span data-ttu-id="c2e4d-121">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-121">Click **New**.</span></span>
14. <span data-ttu-id="c2e4d-122">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-122">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="c2e4d-123">En el campo **Tipo de Transacción**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-123">In the **Transaction type** field, select an option.</span></span>
16. <span data-ttu-id="c2e4d-124">En el campo **Categoría**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-124">In the **Category** field, enter or select a value.</span></span>
17. <span data-ttu-id="c2e4d-125">En el campo **Presupuesto original**, introduzca un número.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-125">In the **Original budget** field, enter a number.</span></span>
18. <span data-ttu-id="c2e4d-126">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-126">Click **Save**.</span></span>
19. <span data-ttu-id="c2e4d-127">Haga clic en **Flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-127">Click **Workflow**.</span></span>
20. <span data-ttu-id="c2e4d-128">Haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-128">Click **Submit**.</span></span>
21. <span data-ttu-id="c2e4d-129">En el campo **Comentario**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-129">In the **Comment** field, type a value.</span></span>
22. <span data-ttu-id="c2e4d-130">Haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="c2e4d-130">Click **Submit**.</span></span>

