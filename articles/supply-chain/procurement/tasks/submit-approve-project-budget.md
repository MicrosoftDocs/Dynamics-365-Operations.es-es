---
title: Enviar y aprobar un presupuesto de proyecto
description: Este procedimiento muestra cómo crear y mostrar el presupuesto para un proyecto.
author: mkirknel
manager: AnnBe
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, ProjBudget, WorkflowSubmitDialog
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7aa7c301946b92b956f4b1b0f92985451ffe917e
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149444"
---
# <a name="submit-and-approve-project-budget"></a><span data-ttu-id="01fc4-103">Enviar y aprobar un presupuesto de proyecto</span><span class="sxs-lookup"><span data-stu-id="01fc4-103">Submit and approve project budget</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="01fc4-104">Este procedimiento muestra cómo crear y mostrar el presupuesto para un proyecto.</span><span class="sxs-lookup"><span data-stu-id="01fc4-104">This procedure shows you how to create and submit the budget for a project.</span></span> 

<span data-ttu-id="01fc4-105">Cuando usted crea un presupuesto de proyecto, puede especificar los ingresos y los costes calculados para un proyecto y usarlos para controlar las transacciones de proyecto reales.</span><span class="sxs-lookup"><span data-stu-id="01fc4-105">When you create a project budget, you can enter estimated revenues and costs for a project, and then use those to control actual project transactions.</span></span> <span data-ttu-id="01fc4-106">Con el presupuesto de proyecto, es necesario enviar todos los presupuestos originales y las revisiones al flujo de trabajo del proyecto para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="01fc4-106">In project budgeting, all original budgets and revisions must be sent to project workflow for approval.</span></span> <span data-ttu-id="01fc4-107">El flujo de trabajo proporciona un mayor control sobre el proceso y crea un registro de historial de cambios.</span><span class="sxs-lookup"><span data-stu-id="01fc4-107">Workflow gives you increased control over the process and creates a change history record.</span></span>

<span data-ttu-id="01fc4-108">Esta tarea se creó con el conjunto de datos de demostración USSI.</span><span class="sxs-lookup"><span data-stu-id="01fc4-108">This task was created using the USSI data set.</span></span>

1. <span data-ttu-id="01fc4-109">En el **Panel de navegación**, vaya a **Módulos > Gestión y contabilidad de proyectos > Proyectos > Todos los proyectos**.</span><span class="sxs-lookup"><span data-stu-id="01fc4-109">In the **Navigation pane**, go to **Modules > Project management and accounting > Projects > All projects**.</span></span>
2. <span data-ttu-id="01fc4-110">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="01fc4-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="01fc4-111">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="01fc4-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="01fc4-112">En el **panel de acciones**, haga clic en **Plan**.</span><span class="sxs-lookup"><span data-stu-id="01fc4-112">On the **Action Pane**, click **Plan**.</span></span>
5. <span data-ttu-id="01fc4-113">Haga clic en **Presupuesto del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="01fc4-113">Click **Project budget**.</span></span>
6. <span data-ttu-id="01fc4-114">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="01fc4-114">In the **Description** field, type a value.</span></span>
7. <span data-ttu-id="01fc4-115">Expanda la ficha desplegable **Coste**.</span><span class="sxs-lookup"><span data-stu-id="01fc4-115">Expand the **Cost** fastTab.</span></span>
8. <span data-ttu-id="01fc4-116">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="01fc4-116">Click **New**.</span></span>
9. <span data-ttu-id="01fc4-117">En el campo **Tipo de Transacción**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="01fc4-117">In the **Transaction type** field, select an option.</span></span>
10. <span data-ttu-id="01fc4-118">En el campo **Categoría**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="01fc4-118">In the **Category** field, enter or select a value.</span></span>
11. <span data-ttu-id="01fc4-119">En el campo **Presupuesto original**, introduzca un número.</span><span class="sxs-lookup"><span data-stu-id="01fc4-119">In the **Original budget** field, enter a number.</span></span>
12. <span data-ttu-id="01fc4-120">Expanda la ficha desplegable **Ingresos**.</span><span class="sxs-lookup"><span data-stu-id="01fc4-120">Expand the **Revenues** fastTab.</span></span>
13. <span data-ttu-id="01fc4-121">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="01fc4-121">Click **New**.</span></span>
14. <span data-ttu-id="01fc4-122">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="01fc4-122">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="01fc4-123">En el campo **Tipo de Transacción**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="01fc4-123">In the **Transaction type** field, select an option.</span></span>
16. <span data-ttu-id="01fc4-124">En el campo **Categoría**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="01fc4-124">In the **Category** field, enter or select a value.</span></span>
17. <span data-ttu-id="01fc4-125">En el campo **Presupuesto original**, introduzca un número.</span><span class="sxs-lookup"><span data-stu-id="01fc4-125">In the **Original budget** field, enter a number.</span></span>
18. <span data-ttu-id="01fc4-126">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="01fc4-126">Click **Save**.</span></span>
19. <span data-ttu-id="01fc4-127">Haga clic en **Flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="01fc4-127">Click **Workflow**.</span></span>
20. <span data-ttu-id="01fc4-128">Haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="01fc4-128">Click **Submit**.</span></span>
21. <span data-ttu-id="01fc4-129">En el campo **Comentario**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="01fc4-129">In the **Comment** field, type a value.</span></span>
22. <span data-ttu-id="01fc4-130">Haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="01fc4-130">Click **Submit**.</span></span>

