---
title: Sincronizar las tareas de proyectos directamente desde Project Service Automation a Finance and Operations
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar tareas de proyectos directamente de Microsoft Dynamics 365 Project Service Automation a Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: ba475721b69e7c75dfd2197597b54050a3598d37
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770275"
---
# <a name="synchronize-project-tasks-directly-from-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="f3659-103">Sincronizar las tareas de proyectos directamente desde Project Service Automation a Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f3659-103">Synchronize project tasks directly from Project Service Automation to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="f3659-104">En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar tareas de proyectos directamente de Dynamics 365 Project Service Automation a Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="f3659-104">This topic describes the template and underlying task that are used to synchronize project tasks directly from Dynamics 365 Project Service Automation to Dynamics 365 Finance.</span></span>

> [!NOTE]
> - <span data-ttu-id="f3659-105">La integración de tareas de proyectos, las categorías de transacción de gastos, las estimaciones de hora, las estimaciones de gastos y el bloqueo de funciones están disponibles la versión 8.0.</span><span class="sxs-lookup"><span data-stu-id="f3659-105">Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking are available in version 8.0.</span></span>
> - <span data-ttu-id="f3659-106">Si utiliza Enterprise edition 7.3.0, después de instalar KB 4132657 y 4132660 KB, podrá usar plantillas para integrar tareas de proyecto, categorías de transacción de gastos, estimaciones de hora, estimaciones de gastos y valores reales, y para configurar el bloqueo de funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="f3659-106">If you're using Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="f3659-107">Si debe restablecer las distribuciones contables, se recomienda instalar también KB 4131710.</span><span class="sxs-lookup"><span data-stu-id="f3659-107">If you must reset the accounting distributions, we recommended that you also install KB 4131710.</span></span>
> - <span data-ttu-id="f3659-108">La integración de los reales está disponible en la versión 8.0.1 o posterior.</span><span class="sxs-lookup"><span data-stu-id="f3659-108">Actuals integration is available in version 8.0.1 or later.</span></span>

## <a name="data-flow-for-project-service-automation-to-finance"></a><span data-ttu-id="f3659-109">Flujo de datos de Project Service Automation a Finance</span><span class="sxs-lookup"><span data-stu-id="f3659-109">Data flow for Project Service Automation to Finance</span></span>

<span data-ttu-id="f3659-110">La solución de integración de Project Service Automation a Finance usa la característica de integración de datos para sincronizar datos a través de las instancias de Project Service Automation y de Finance.</span><span class="sxs-lookup"><span data-stu-id="f3659-110">The Project Service Automation to Finance integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance.</span></span> <span data-ttu-id="f3659-111">La plantilla de integración disponible con la función de integración de datos habilita el flujo de datos sobre las tareas de proyecto desde Project Service Automation a Finance.</span><span class="sxs-lookup"><span data-stu-id="f3659-111">The integration template that is available with the Data integration feature enables the flow of data about project tasks from Project Service Automation to Finance.</span></span>

<span data-ttu-id="f3659-112">La ilustración siguiente muestra cómo se sincronizan los datos entre Project Service Automation y Finance.</span><span class="sxs-lookup"><span data-stu-id="f3659-112">The following illustration shows how the data is synchronized between Project Service Automation and Finance.</span></span>

<span data-ttu-id="f3659-113">[![Flujo de datos para la integración de Project Service Automation con Finance](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span><span class="sxs-lookup"><span data-stu-id="f3659-113">[![Data flow for Project Service Automation integration with Finance](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span></span>

## <a name="template-and-task"></a><span data-ttu-id="f3659-114">Plantilla y tarea</span><span class="sxs-lookup"><span data-stu-id="f3659-114">Template and task</span></span>

<span data-ttu-id="f3659-115">Para obtener acceso a la plantilla, en el centro de administración de Microsoft Power Apps, seleccione **Proyectos** y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.</span><span class="sxs-lookup"><span data-stu-id="f3659-115">To access the template, in the Microsoft Power Apps admin center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="f3659-116">La plantilla y la tarea subyacente siguientes se usan para sincronizar las tareas del proyecto desde Project Service Automation a Finance:</span><span class="sxs-lookup"><span data-stu-id="f3659-116">The following template and underlying task are used to synchronize project tasks from Project Service Automation to Finance:</span></span>

- <span data-ttu-id="f3659-117">**Nombre de la plantilla en la integración de datos:** tareas del proyecto (PSA a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="f3659-117">**Name of the template in Data integration:** Project tasks (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="f3659-118">**Nombre de la tarea en el proyecto:** tareas de proyecto</span><span class="sxs-lookup"><span data-stu-id="f3659-118">**Name of the task in the project:** Project tasks</span></span>

<span data-ttu-id="f3659-119">Antes de que se produzca la sincronización de tareas de proyectos, debe sincronizar los contratos de proyecto y los proyectos.</span><span class="sxs-lookup"><span data-stu-id="f3659-119">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="entity-set"></a><span data-ttu-id="f3659-120">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="f3659-120">Entity set</span></span>

| <span data-ttu-id="f3659-121">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="f3659-121">Project Service Automation</span></span> | <span data-ttu-id="f3659-122">Finanzas</span><span class="sxs-lookup"><span data-stu-id="f3659-122">Finance</span></span>                             |
|----------------------------|-------------------------------------|
| <span data-ttu-id="f3659-123">Tareas de proyecto</span><span class="sxs-lookup"><span data-stu-id="f3659-123">Project Tasks</span></span>              | <span data-ttu-id="f3659-124">Entidad de integración para tarea de proyecto</span><span class="sxs-lookup"><span data-stu-id="f3659-124">Integration entity for project task</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="f3659-125">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="f3659-125">Entity flow</span></span>

<span data-ttu-id="f3659-126">Las tareas de proyectos se administran en Project Service Automation y se sincronizan con Finance como actividades de proyectos.</span><span class="sxs-lookup"><span data-stu-id="f3659-126">Project tasks are managed in Project Service Automation, and they are synchronized to Finance as project activities.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="f3659-127">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="f3659-127">Prerequisites and mapping setup</span></span>

<span data-ttu-id="f3659-128">Antes de que se produzca la sincronización de tareas de proyectos, debe sincronizar los contratos de proyecto y los proyectos.</span><span class="sxs-lookup"><span data-stu-id="f3659-128">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="power-query"></a><span data-ttu-id="f3659-129">Power Query</span><span class="sxs-lookup"><span data-stu-id="f3659-129">Power Query</span></span>

<span data-ttu-id="f3659-130">Debe usar Microsoft Power Query for Excel para filtrar los datos si se cumple esta condición:</span><span class="sxs-lookup"><span data-stu-id="f3659-130">You must use Microsoft Power Query for Excel to filter data if this condition is met:</span></span>

- <span data-ttu-id="f3659-131">Tiene registros específicos de recursos en una tarea de proyecto.</span><span class="sxs-lookup"><span data-stu-id="f3659-131">You have resource-specific records in a project task.</span></span>

<span data-ttu-id="f3659-132">Si debe usar Power Query, siga esta instrucción:</span><span class="sxs-lookup"><span data-stu-id="f3659-132">If you must use Power Query, follow this guideline:</span></span>

- <span data-ttu-id="f3659-133">La plantilla de las tareas de proyecto (PSA a Fin and Ops) tiene un filtro predeterminado que excluye registros específicos de recursos de una tarea de proyecto estableciendo el filtro de **IsLineTask** en **Falso**.</span><span class="sxs-lookup"><span data-stu-id="f3659-133">The Project tasks (PSA to Fin and Ops) template has a default filter that excludes resource-specific records from a project task by setting the filter on **IsLineTask** to **False**.</span></span> <span data-ttu-id="f3659-134">Si crea su propia plantilla, debe agregar este filtro.</span><span class="sxs-lookup"><span data-stu-id="f3659-134">If you create your own template, you must add this filter.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="f3659-135">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="f3659-135">Template mapping in Data integration</span></span>

<span data-ttu-id="f3659-136">La siguiente ilustración muestra un ejemplo de las asignaciones de tarea de plantilla en integración de datos.</span><span class="sxs-lookup"><span data-stu-id="f3659-136">The following illustration shows an example of the template task mappings in Data integration.</span></span> <span data-ttu-id="f3659-137">La asignación muestra la información de campo que se sincronizará de Project Service Automation a Finance.</span><span class="sxs-lookup"><span data-stu-id="f3659-137">The mapping shows the field information that will be synchronized from Project Service Automation to Finance.</span></span>

<span data-ttu-id="f3659-138">[![Asignación de la plantilla](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span><span class="sxs-lookup"><span data-stu-id="f3659-138">[![Template mapping](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span></span>
