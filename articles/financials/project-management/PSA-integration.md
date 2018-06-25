---
title: Project Service Automation
description: "Esta solución usa la función de integración de datos para sincronizar los datos a través de instancias de Microsoft Dynamics 365 for Finance and Operations y Microsoft Dynamics 365 for Project Service Automation a través de Common Data Service (CDS)."
author: KimANelson
manager: AnnBe
ms.date: 11/27/2017
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 0ad9e6ba7fe8dd915681da8e671ff210de887b1e
ms.contentlocale: es-es
ms.lasthandoff: 05/29/2018

---

# <a name="project-service-automation"></a><span data-ttu-id="b694f-103">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="b694f-103">Project Service Automation</span></span>

<span data-ttu-id="b694f-104">La solución de integración de Project Service Automation en Finance and Operations usa la función de integración de datos para sincronizar los datos a través de instancias de Microsoft Dynamics 365 for Finance and Operations y Microsoft Dynamics 365 for Project Service Automation a través de Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="b694f-104">The Project Service Automation to Finance and Operations integration solution uses the Data Integration feature to synchronize data across instances of Microsoft Dynamics 365 for Finance and Operations and Microsoft Dynamics 365 for Project Service Automation via the Common Data Service (CDS).</span></span> <span data-ttu-id="b694f-105">Las plantillas de integración que están disponibles con la característica de integración de datos habilitan el flujo de proyectos, los contratos de proyectos, las líneas de contratos de proyectos, los hitos de la línea del contrato, las tareas de proyecto, las categorías de transacciones de gastos, las estimaciones de horas y las estimaciones de gastos desde Project Service Automation hasta Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b694f-105">The integration templates that are available with the Data Integration feature enable the flow of projects, project contracts, project contract lines, project contract line milestones, project tasks, expense transaction categories, hour estimates, and expense estimates from Project Service Automation to Finance and Operations.</span></span>

> [!NOTE] 
> <span data-ttu-id="b694f-106">Si utiliza Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0 debe instalar KB 4074835.</span><span class="sxs-lookup"><span data-stu-id="b694f-106">If you are using Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, you must install KB 4074835.</span></span> <span data-ttu-id="b694f-107">Esto le permitirá integrar proyectos de precio fijo.</span><span class="sxs-lookup"><span data-stu-id="b694f-107">This will allow you to integrate fixed price projects.</span></span>
>
> <span data-ttu-id="b694f-108">Si usa Dynamics 365 for Finance and Operations versión 8.0 podrá usar la integración de tareas de proyectos, las categorías de transacción de gastos, las estimaciones de hora, las estimaciones de gastos y el bloqueo de función.</span><span class="sxs-lookup"><span data-stu-id="b694f-108">If you are using Dynamics 365 for Finance and Operations version 8.0, you will be able to use project tasks integration, expense transaction categories, hour estimates, expense estimates, and functionality locking.</span></span>
>
> <span data-ttu-id="b694f-109">Si utiliza Dynamics 365 for Finance and Operations versión 8.0.1 podrá sincronizar valores reales.</span><span class="sxs-lookup"><span data-stu-id="b694f-109">If you are using Dynamics 365 for Finance and Operations version 8.0.1, you will be able to synchronize actuals.</span></span>
>
> <span data-ttu-id="b694f-110">Si utiliza Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, después de instalar KB 4132657 y 4132660 KB, podrá usar plantillas para integrar tareas de proyecto, categorías de transacción de gastos, estimaciones de hora, estimaciones de gastos y valores reales, y para configurar el bloqueo de funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="b694f-110">If you are using Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="b694f-111">Si debe restablecer las distribuciones contables, se recomienda instalar también KB 4131710.</span><span class="sxs-lookup"><span data-stu-id="b694f-111">If you must reset the accounting distributions, we recommend that you also install KB 4131710.</span></span>

<span data-ttu-id="b694f-112">Para poder integrar Project Service Automation con Finance and Operations, debe configurar los parámetros de integración de Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="b694f-112">Before you can integrate Project Service Automation with Finance and Operations, you must configure the Project Service Automation integration parameters.</span></span> <span data-ttu-id="b694f-113">Para obtener más información consulte los parámetros de integración de Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="b694f-113">For more information, see Project Service Automation integration parameters.</span></span>

<span data-ttu-id="b694f-114">Esta solución de integración le permite una sincronización directa en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="b694f-114">This integration solution enables direct synchronization in the following scenarios:</span></span>

- <span data-ttu-id="b694f-115">Mantener los contratos de proyectos en Project Service Automation y sincronizarlos directamente desde Project Service Automation hasta Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b694f-115">Maintain project contracts in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="b694f-116">Crear proyectos en Project Service Automation y sincronizarlos directamente desde Project Service Automation hasta Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b694f-116">Create projects in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="b694f-117">Mantener líneas de contratos de proyectos en Project Service Automation y sincronizarlos directamente desde Project Service Automation hasta Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b694f-117">Maintain project contract lines in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="b694f-118">Mantener hitos de líneas de contratos de proyectos en Project Service Automation y sincronizarlos directamente desde Project Service Automation hasta Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b694f-118">Maintain project contract line milestones in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="b694f-119">Mantener tareas de proyectos en Project Service Automation y sincronizarlos directamente desde Project Service Automation hasta Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b694f-119">Maintain project tasks in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="b694f-120">Mantener categorías de transacciones de gastos en Finance and Operations y sincronizarlas directamente desde Finance and Operations hasta Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="b694f-120">Maintain expense transaction categories in Finance and Operations, and synchronize them directly from Finance and Operations to Project Service Automation.</span></span>
- <span data-ttu-id="b694f-121">Crear estimaciones de horas proyectos en Project Service Automation y sincronizarlas directamente desde Project Service Automation hasta Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b694f-121">Create project hour estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="b694f-122">Crear estimaciones de gastos proyectos en Project Service Automation y sincronizarlas directamente desde Project Service Automation hasta Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b694f-122">Create project expense estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>

## <a name="data-synchronization"></a><span data-ttu-id="b694f-123">Sincronización de datos</span><span class="sxs-lookup"><span data-stu-id="b694f-123">Data synchronization</span></span>
<span data-ttu-id="b694f-124">La ilustración siguiente muestra cómo se sincronizan los datos como parte de la integración entre Project Service Automation y Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b694f-124">The following illustration shows how data is synchronized as part of the integration between Project Service Automation and Finance and Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="b694f-125">No todas las plantillas están actualmente disponibles.</span><span class="sxs-lookup"><span data-stu-id="b694f-125">Not all templates are currently available.</span></span> <span data-ttu-id="b694f-126">Las plantillas se publicarán a medida que estén completadas.</span><span class="sxs-lookup"><span data-stu-id="b694f-126">Templates will be released as they are completed.</span></span>

<span data-ttu-id="b694f-127">[![Integración de Project Service Automation con Finance and Operations](./media/PSA-integration.png)](./media/PSA-integration.png)</span><span class="sxs-lookup"><span data-stu-id="b694f-127">[![Project Service Automation integration with Finance and Operations](./media/PSA-integration.png)](./media/PSA-integration.png)</span></span>

## <a name="system-requirements-for-finance-and-operations"></a><span data-ttu-id="b694f-128">Requisitos del sistema para Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b694f-128">System requirements for Finance and Operations</span></span>

<span data-ttu-id="b694f-129">Para usar la solución de integración de Project Service Automation en Finance and Operations, debe instalar Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 con la actualización de plataforma 12 o posterior.</span><span class="sxs-lookup"><span data-stu-id="b694f-129">To use the Project Service Automation to Finance and Operations integration solution, you must install Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 with platform update 12 or later.</span></span>

## <a name="system-requirements-for-project-service-automation"></a><span data-ttu-id="b694f-130">Requisitos del sistema para Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="b694f-130">System requirements for Project Service Automation</span></span>

<span data-ttu-id="b694f-131">Para usar la solución de integración de Project Service Automation en Finance and Operations, debe instalar los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="b694f-131">To use the Project Service Automation to Finance and Operations integration solution, you must install the following components:</span></span>

- <span data-ttu-id="b694f-132">Microsoft Dynamics 365 for Project Service Automation versión 9.0.0.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="b694f-132">Microsoft Dynamics 365 for Project Service Automation version 9.0.0.0 or later.</span></span>
- <span data-ttu-id="b694f-133">Solución Prospect to cash para Dynamics 365 for Sales, versión 1.14.0.0 (v14) o posterior.</span><span class="sxs-lookup"><span data-stu-id="b694f-133">Prospect to cash solution for Dynamics 365 for Sales, version 1.14.0.0 (v14) or later.</span></span>
- <span data-ttu-id="b694f-134">Project Service Automation en la solución Operations for Dynamics 365 for Project Service Automation versión 1.0.0.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="b694f-134">Project Service Automation to Operations solution for Dynamics 365 for Project Service Automation version 1.0.0.0 or later.</span></span>

## <a name="install-the-project-service-automation-to-finance-and-operations-integration-solution-in-your-project-service-automation-instance"></a><span data-ttu-id="b694f-135">Instalar la solución de integración de Project Service Automation en Finance and Operations en su instancia de Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="b694f-135">Install the Project Service Automation to Finance and Operations integration solution in your Project Service Automation instance</span></span>


