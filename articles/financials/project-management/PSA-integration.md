---
title: Project Service Automation
description: "Este tema proporciona información sobre la solución de integración de Project Service Automation en Finance and Operations. Esta solución de integración usa la función de integración de datos para sincronizar los datos a través de instancias de Microsoft Dynamics 365 for Finance and Operations y Microsoft Dynamics 365 for Project Service Automation a través de Common Data Service."
author: KimANelson
manager: AnnBe
ms.date: 06/29/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 841ea53f754f61c2930e77fdafc85eac72f47d7a
ms.openlocfilehash: 4b1d2ae69899a2937d47f6547ee4ba72b2d1ece4
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---

# <a name="project-service-automation"></a><span data-ttu-id="0ca71-104">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="0ca71-104">Project Service Automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="0ca71-105">La solución de integración de Project Service Automation en Finance and Operations usa la función de integración de datos para sincronizar los datos a través de instancias de Microsoft Dynamics 365 for Finance and Operations y Microsoft Dynamics 365 for Project Service Automation a través de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="0ca71-105">The Project Service Automation to Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Microsoft Dynamics 365 for Finance and Operations and Microsoft Dynamics 365 for Project Service Automation via Common Data Service.</span></span> <span data-ttu-id="0ca71-106">Las plantillas de integración que están disponibles con la característica de integración de datos habilitan el flujo de proyectos, los contratos de proyectos, las líneas de contratos de proyectos, los hitos de la línea del contrato, las tareas de proyecto, las categorías de transacciones de gastos, las estimaciones de horas y las estimaciones de gastos desde Project Service Automation hasta Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0ca71-106">The integration templates that are available with the Data integration feature enable the flow of projects, project contracts, project contract lines, project contract line milestones, project tasks, expense transaction categories, hour estimates, and expense estimates from Project Service Automation to Finance and Operations.</span></span>

> [!NOTE]
> - <span data-ttu-id="0ca71-107">Si utiliza Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, después de instalar KB 4132657 y 4132660 KB, podrá usar plantillas para integrar tareas de proyecto, categorías de transacción de gastos, estimaciones de hora, estimaciones de gastos y valores reales, y para configurar el bloqueo de funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="0ca71-107">If you're using Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="0ca71-108">Si debe restablecer las distribuciones contables, se recomienda instalar también KB 4131710.</span><span class="sxs-lookup"><span data-stu-id="0ca71-108">If you must reset the accounting distributions, we recommend that you also install KB 4131710.</span></span>
> - <span data-ttu-id="0ca71-109">Si utiliza Finance and Operations 7.3.0, debe instalar 4074835 KB.</span><span class="sxs-lookup"><span data-stu-id="0ca71-109">If you're using Finance and Operations 7.3.0, you must install KB 4074835.</span></span> <span data-ttu-id="0ca71-110">A continuación, podrá integrar proyectos de precio fijo.</span><span class="sxs-lookup"><span data-stu-id="0ca71-110">You will then be able to integrate fixed price projects.</span></span>
> - <span data-ttu-id="0ca71-111">Si está usando Finance and Operations 7.3.0 y trae transacciones de cuotas de Project Service Automation, debe instalar KB 4345320 para incluir esas cuotas en la factura del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0ca71-111">If you're using Finance and Operations 7.3.0, and you are bringing fee transactions over from Project Service Automation, you must install KB 4345320 in order to include those fees in the project invoice.</span></span>
> - <span data-ttu-id="0ca71-112">Si usa Microsoft Dynamics 365 for Finance and Operations versión 8.0 podrá usar la integración de tareas de proyectos, las categorías de transacción de gastos, las estimaciones de hora, las estimaciones de gastos y el bloqueo de función.</span><span class="sxs-lookup"><span data-stu-id="0ca71-112">If you're using Microsoft Dynamics 365 for Finance and Operations version 8.0, you will be able to use project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking.</span></span>
> - <span data-ttu-id="0ca71-113">Si utiliza Microsoft Dynamics 365 for Finance and Operations versión 8.0.1 o posterior, podrá sincronizar valores reales.</span><span class="sxs-lookup"><span data-stu-id="0ca71-113">If you're using Microsoft Dynamics 365 for Finance and Operations version 8.0.1, or later, you will be able to synchronize actuals.</span></span>

<span data-ttu-id="0ca71-114">Para poder integrar Project Service Automation con Finance and Operations, debe configurar los parámetros de integración de Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="0ca71-114">Before you can integrate Project Service Automation with Finance and Operations, you must configure the Project Service Automation integration parameters.</span></span> <span data-ttu-id="0ca71-115">Para obtener más información consulte los [parámetros de integración de Project Service Automation](PSA-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="0ca71-115">For more information, see [Project Service Automation integration parameters](PSA-parameters.md).</span></span>

<span data-ttu-id="0ca71-116">Esta solución de integración le permite una sincronización directa en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="0ca71-116">This integration solution enables direct synchronization in the following scenarios:</span></span>

- <span data-ttu-id="0ca71-117">Mantener los contratos de proyectos en Project Service Automation y sincronizarlos directamente desde Project Service Automation hasta Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0ca71-117">Maintain project contracts in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="0ca71-118">Crear proyectos en Project Service Automation y sincronizarlos directamente desde Project Service Automation hasta Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0ca71-118">Create projects in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="0ca71-119">Mantener líneas de contratos de proyectos en Project Service Automation y sincronizarlos directamente desde Project Service Automation hasta Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0ca71-119">Maintain project contract lines in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="0ca71-120">Mantener hitos de líneas de contratos de proyectos en Project Service Automation y sincronizarlos directamente desde Project Service Automation hasta Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0ca71-120">Maintain project contract line milestones in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="0ca71-121">Mantener tareas de proyectos en Project Service Automation y sincronizarlos directamente desde Project Service Automation hasta Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0ca71-121">Maintain project tasks in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="0ca71-122">Mantener categorías de transacciones de gastos en Finance and Operations y sincronizarlas directamente desde Finance and Operations hasta Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="0ca71-122">Maintain expense transaction categories in Finance and Operations, and synchronize them directly from Finance and Operations to Project Service Automation.</span></span>
- <span data-ttu-id="0ca71-123">Crear estimaciones de horas proyectos en Project Service Automation y sincronizarlas directamente desde Project Service Automation hasta Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0ca71-123">Create project hour estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="0ca71-124">Crear estimaciones de gastos proyectos en Project Service Automation y sincronizarlas directamente desde Project Service Automation hasta Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0ca71-124">Create project expense estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="0ca71-125">Cree datos reales de tiempo, gastos y cuotas del proyecto en Project Service Automation y cree transacciones del proyecto en el diario de integración de Project Service Automation para que se puedan registrar en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0ca71-125">Create project time, expense, and fee actuals in Project Service Automation, and create project transactions in the Project Service Automation integration journal so that they can be posted in Finance and Operations.</span></span>

## <a name="data-synchronization"></a><span data-ttu-id="0ca71-126">Sincronización de datos</span><span class="sxs-lookup"><span data-stu-id="0ca71-126">Data synchronization</span></span>

<span data-ttu-id="0ca71-127">La ilustración siguiente muestra cómo se sincronizan los datos como parte de la integración entre Project Service Automation y Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0ca71-127">The following illustration shows how data is synchronized as part of the integration between Project Service Automation and Finance and Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="0ca71-128">No todas las plantillas están actualmente disponibles.</span><span class="sxs-lookup"><span data-stu-id="0ca71-128">Not all templates are currently available.</span></span> <span data-ttu-id="0ca71-129">Las plantillas se publicarán a medida que estén completadas.</span><span class="sxs-lookup"><span data-stu-id="0ca71-129">Templates will be released as they are completed.</span></span>

<span data-ttu-id="0ca71-130">[![Integración de Project Service Automation con Finance and Operations](./media/PSA-integration.png)](./media/PSA-integration.png)</span><span class="sxs-lookup"><span data-stu-id="0ca71-130">[![Project Service Automation integration with Finance and Operations](./media/PSA-integration.png)](./media/PSA-integration.png)</span></span>

## <a name="system-requirements-for-finance-and-operations"></a><span data-ttu-id="0ca71-131">Requisitos del sistema para Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0ca71-131">System requirements for Finance and Operations</span></span>

<span data-ttu-id="0ca71-132">Para usar la solución de integración de Project Service Automation en Finance and Operations, debe instalar Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 con la actualización de plataforma 12 o posterior.</span><span class="sxs-lookup"><span data-stu-id="0ca71-132">To use the Project Service Automation to Finance and Operations integration solution, you must install Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 with platform update 12 or later.</span></span>

## <a name="system-requirements-for-project-service-automation"></a><span data-ttu-id="0ca71-133">Requisitos del sistema para Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="0ca71-133">System requirements for Project Service Automation</span></span>

<span data-ttu-id="0ca71-134">Para usar la solución de integración de Project Service Automation en Finance and Operations, debe instalar los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="0ca71-134">To use the Project Service Automation to Finance and Operations integration solution, you must install the following components:</span></span>

- <span data-ttu-id="0ca71-135">Microsoft Dynamics 365 for Project Service Automation versión 9.0.0.0 o posterior</span><span class="sxs-lookup"><span data-stu-id="0ca71-135">Microsoft Dynamics 365 for Project Service Automation version 9.0.0.0 or later</span></span>
- <span data-ttu-id="0ca71-136">Solución Prospect to cash para Microsoft Dynamics 365 for Sales, versión 1.14.0.0 (v14) o posterior</span><span class="sxs-lookup"><span data-stu-id="0ca71-136">Prospect to cash solution for Microsoft Dynamics 365 for Sales, version 1.14.0.0 (v14) or later</span></span>
- <span data-ttu-id="0ca71-137">Project Service Automation en la solución Finance and Operations para Microsoft Dynamics 365 for Project Service Automation versión 1.0.0.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="0ca71-137">Project Service Automation to Finance and Operations solution for Microsoft Dynamics 365 for Project Service Automation version 1.0.0.0 or later</span></span>

## <a name="install-the-project-service-automation-to-finance-and-operations-integration-solution-in-your-project-service-automation-instance"></a><span data-ttu-id="0ca71-138">Instalar la solución de integración de Project Service Automation en Finance and Operations en su instancia de Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="0ca71-138">Install the Project Service Automation to Finance and Operations integration solution in your Project Service Automation instance</span></span>

<span data-ttu-id="0ca71-139">Descargue la solución de integración de Project Service Automation en Finance and Operations desde [Centro de descarga de Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=57016) y siga las instrucciones que se incluyen con la solución.</span><span class="sxs-lookup"><span data-stu-id="0ca71-139">Download the Project Service Automation to Finance and Operations integration solution from [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=57016), and follow the instructions that are included with the solution.</span></span>

