---
title: Sincronizar las tareas de proyectos de Project Service Automation
description: En este tema se describen la plantilla y la tarea subyacente que se usa para sincronizar directamente las tareas de proyectos de Microsoft Dynamics 365 for Project Service Automation a Dynamics 365 for Finance and Operations.
author: KimANelson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: 399b519ab0da4de405aeb06f3e7f4bf29a6c5cc3
ms.openlocfilehash: 89df0d99d780441ad08cd6bff3e1fd203694eb8e
ms.contentlocale: es-es
ms.lasthandoff: 05/30/2018

---

# <a name="synchronize-project-tasks-from-project-service-automation-directly-to-project-activities-in-finance-and-operations"></a><span data-ttu-id="4f63b-103">Sincronizar las tareas de proyectos directamente desde Project Service Automation a actividades de proyectos de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4f63b-103">Synchronize project tasks from Project Service Automation directly to project activities in Finance and Operations</span></span>

<span data-ttu-id="4f63b-104">En este tema se describen la plantilla y la tarea subyacente que se usa para sincronizar directamente las tareas de proyectos de Microsoft Dynamics 365 for Project Service Automation a Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4f63b-104">This topic describes the template and underlying task that is used to synchronize project tasks directly from Microsoft Dynamics 365 for Project Service Automation to Dynamics 365 for Finance and Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="4f63b-105">La integración de tareas de proyectos, las categorías de la transacción de gastos, las estimaciones de hora, las estimaciones de gastos y el bloqueo de la función están disponibles en Dynamics 365 for Finance and Operations versión 8.0.</span><span class="sxs-lookup"><span data-stu-id="4f63b-105">Project tasks integration, expense transaction categories, hour estimates, expense estimates, and functionality locking is available in Dynamics 365 for Finance and Operations version 8.0.</span></span>

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="4f63b-106">Flujo de datos de Project Service Automation a Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4f63b-106">Data flow for Project Service Automation to Finance and Operations</span></span>

<span data-ttu-id="4f63b-107">La integración de Project Service Automation con Finance and Operations usa la característica de integración de datos para sincronizar datos a través de las instancias de Project Service Automation y de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4f63b-107">The Project Service Automation to Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance and Operations.</span></span> <span data-ttu-id="4f63b-108">La plantilla de integración disponible con la función de integración de datos habilita el flujo de datos sobre las tareas de proyecto desde Project Service Automation a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4f63b-108">The integration template that is available with the Data integration feature enables the flow of data about project tasks from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="4f63b-109">La ilustración siguiente muestra cómo se sincronizan los datos entre Project Service Automation y Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4f63b-109">The following illustration shows how the data is synchronized between Project Service Automation and Finance and Operations.</span></span>

<span data-ttu-id="4f63b-110">[![Flujo de datos para la integración de Project Service Automation con Finance and Operations](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span><span class="sxs-lookup"><span data-stu-id="4f63b-110">[![Data flow for Project Service Automation integration with Finance and Operations](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span></span>

## <a name="template-and-task"></a><span data-ttu-id="4f63b-111">Plantilla y tarea</span><span class="sxs-lookup"><span data-stu-id="4f63b-111">Template and task</span></span>

<span data-ttu-id="4f63b-112">Para obtener acceso a la plantilla, en el centro de administración de Microsoft PowerApps, seleccione **Proyectos** y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.</span><span class="sxs-lookup"><span data-stu-id="4f63b-112">To access the template, in the Microsoft PowerApps Admin Center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="4f63b-113">La plantilla y la tarea subyacente siguientes se usan para sincronizar las tareas del proyecto desde Project Service Automation hasta Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="4f63b-113">The following template and underlying task is used to synchronize project tasks from Project Service Automation to Finance and Operations:</span></span>

<span data-ttu-id="4f63b-114">-**Nombre de la plantilla en la integración de datos:** Tareas del proyecto (de PSA a Fin and Ops) -**Nombre de la tarea en el proyecto:** Tareas del proyecto</span><span class="sxs-lookup"><span data-stu-id="4f63b-114">-**Name of the template in Data integration:** Project tasks (PSA to Fin and Ops) -**Name of the task in the project:** Project tasks</span></span>

<span data-ttu-id="4f63b-115">Antes de que se produzca la sincronización de tareas de proyectos, debe sincronizar los contratos de proyecto y los proyectos.</span><span class="sxs-lookup"><span data-stu-id="4f63b-115">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="entity-set"></a><span data-ttu-id="4f63b-116">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="4f63b-116">Entity set</span></span>

|<span data-ttu-id="4f63b-117">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="4f63b-117">Project Service Automation</span></span>               | <span data-ttu-id="4f63b-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4f63b-118">Finance and Operations</span></span>                |
|-----------------------------------------|---------------------------------------|
| <span data-ttu-id="4f63b-119">Tareas de proyecto</span><span class="sxs-lookup"><span data-stu-id="4f63b-119">Project Tasks</span></span>                           | <span data-ttu-id="4f63b-120">Entidad de integración para tarea de proyecto.</span><span class="sxs-lookup"><span data-stu-id="4f63b-120">Integration entity for project task.</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="4f63b-121">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="4f63b-121">Entity flow</span></span>

<span data-ttu-id="4f63b-122">Las tareas de proyectos se administran en Project Service Automation y se sincronizan con Finance and Operations como actividades de proyectos.</span><span class="sxs-lookup"><span data-stu-id="4f63b-122">Project tasks are managed in Project Service Automation, and they are synchronized to Finance and Operations as project activities.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="4f63b-123">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="4f63b-123">Prerequisites and mapping setup</span></span>

<span data-ttu-id="4f63b-124">Antes de que se produzca la sincronización de tareas de proyectos, debe sincronizar los contratos de proyecto y los proyectos.</span><span class="sxs-lookup"><span data-stu-id="4f63b-124">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="power-query"></a><span data-ttu-id="4f63b-125">Power Query</span><span class="sxs-lookup"><span data-stu-id="4f63b-125">Power Query</span></span>

<span data-ttu-id="4f63b-126">Debe usar Microsoft Power Query para filtrar los datos si se cumplen estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="4f63b-126">You must use Microsoft Power Query to filter data if these conditions are met:</span></span>

- <span data-ttu-id="4f63b-127">Tiene registros específicos de recursos dentro de una tarea de proyecto.</span><span class="sxs-lookup"><span data-stu-id="4f63b-127">You have resource specific records within a project task.</span></span>

<span data-ttu-id="4f63b-128">Si debe usar Power Query, siga estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="4f63b-128">If you must use Power Query, follow these guidelines:</span></span>

- <span data-ttu-id="4f63b-129">La plantilla de las tareas de proyecto (PSA a Fin and Ops) tiene un filtro predeterminado para excluir registros específicos de recursos de dentro de una tarea de proyecto estableciendo el filtro de **IsLineTask** en **Falso**.</span><span class="sxs-lookup"><span data-stu-id="4f63b-129">The Project tasks (PSA to Fin and Ops) template has a default filter to exclude resource specific records from within a project task by setting the filter on the **IsLineTask** to **False**.</span></span> <span data-ttu-id="4f63b-130">Si crea su propia plantilla, debe agregar este filtro.</span><span class="sxs-lookup"><span data-stu-id="4f63b-130">If you create your own template, you must add this filter.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="4f63b-131">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="4f63b-131">Template mapping in Data integration</span></span>

<span data-ttu-id="4f63b-132">La siguiente ilustración muestra un ejemplo de las asignaciones de tarea de plantilla en integración de datos.</span><span class="sxs-lookup"><span data-stu-id="4f63b-132">The following illustration shows an example of the template task mappings in Data integration.</span></span> <span data-ttu-id="4f63b-133">La asignación muestra la información de campo que se sincronizará de Project Service Automation a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4f63b-133">The mapping shows the field information that will be synchronized from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="4f63b-134">[![Asignación de la plantilla](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span><span class="sxs-lookup"><span data-stu-id="4f63b-134">[![Template mapping](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span></span>


