---
title: Visión general de Project Service Automation
description: Este tema proporciona información acerca de la solución de integración de Dynamics 365 Project Service Automation a Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 07/25/2019
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
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 31d72591041f8d8cc327aa7c6578c15731ba13c5
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250562"
---
# <a name="project-service-automation-overview"></a><span data-ttu-id="1ac30-103">Visión general de Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="1ac30-103">Project Service Automation overview</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="1ac30-104">La solución de integración de Project Service Automation en Finance usa la característica de integración de datos para sincronizar datos a través de instancias de Dynamics 365 Finance y Dynamics 365 Project Service Automation mediante Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="1ac30-104">The Project Service Automation to Finance integration solution uses the Data integration feature to synchronize data across instances of Dynamics 365 Finance and Dynamics 365 Project Service Automation via Common Data Service.</span></span> <span data-ttu-id="1ac30-105">Las plantillas de integración que están disponibles con la característica de integración de datos habilitan el flujo de proyectos, los contratos de proyectos, las líneas de contratos de proyectos, los hitos de la línea del contrato, las tareas de proyecto, las categorías de transacciones de gastos, las estimaciones de horas y las estimaciones de gastos desde Project Service Automation hasta Finance.</span><span class="sxs-lookup"><span data-stu-id="1ac30-105">The integration templates that are available with the Data integration feature enable the flow of projects, project contracts, project contract lines, project contract line milestones, project tasks, expense transaction categories, hour estimates, and expense estimates from Project Service Automation to Finance.</span></span>

> [!NOTE]
> - <span data-ttu-id="1ac30-106">Si utiliza la versión 7.3.0, debe instalar KB 4074835.</span><span class="sxs-lookup"><span data-stu-id="1ac30-106">If you're using version 7.3.0, you must install KB 4074835.</span></span> <span data-ttu-id="1ac30-107">A continuación, podrá integrar proyectos de precio fijo.</span><span class="sxs-lookup"><span data-stu-id="1ac30-107">You will then be able to integrate fixed price projects.</span></span>
> - <span data-ttu-id="1ac30-108">Si está usando la versión 7.3.0 y trae transacciones de cuotas de Project Service Automation, debe instalar KB 4345320 para incluir esas cuotas en la factura del proyecto.</span><span class="sxs-lookup"><span data-stu-id="1ac30-108">If you're using version 7.3.0, and you are bringing fee transactions over from Project Service Automation, you must install KB 4345320 in order to include those fees in the project invoice.</span></span>
> - <span data-ttu-id="1ac30-109">Si usa la versión 8.0 podrá usar la integración de tareas de proyectos, las categorías de transacción de gastos, las estimaciones de hora, las estimaciones de gastos y el bloqueo de función.</span><span class="sxs-lookup"><span data-stu-id="1ac30-109">If you're using version 8.0, you will be able to use project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking.</span></span>
> - <span data-ttu-id="1ac30-110">Si utiliza la versión 8.0.1, o posterior, podrá sincronizar reales.</span><span class="sxs-lookup"><span data-stu-id="1ac30-110">If you're using version 8.0.1 or later, you will be able to synchronize actuals.</span></span>

<span data-ttu-id="1ac30-111">Para poder integrar Project Service Automation Finance, debe configurar los parámetros de integración de Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="1ac30-111">Before you can integrate Project Service Automation Finance, you must configure the Project Service Automation integration parameters.</span></span> <span data-ttu-id="1ac30-112">Para obtener más información consulte los [parámetros de integración de Project Service Automation](PSA-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="1ac30-112">For more information, see [Project Service Automation integration parameters](PSA-parameters.md).</span></span>

<span data-ttu-id="1ac30-113">Esta solución de integración le permite una sincronización directa en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="1ac30-113">This integration solution enables direct synchronization in the following scenarios:</span></span>

- <span data-ttu-id="1ac30-114">Mantener los contratos de proyectos en Project Service Automation y sincronizarlos directamente desde Project Service Automation hasta Finance.</span><span class="sxs-lookup"><span data-stu-id="1ac30-114">Maintain project contracts in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="1ac30-115">Crear proyectos en Project Service Automation y sincronizarlos directamente desde Project Service Automation hasta Finance.</span><span class="sxs-lookup"><span data-stu-id="1ac30-115">Create projects in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="1ac30-116">Mantener las líneas de contrato de proyecto en Project Service Automation y sincronizarlas directamente desde Project Service Automation hasta Finance.</span><span class="sxs-lookup"><span data-stu-id="1ac30-116">Maintain project contract lines in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="1ac30-117">Mantener los hitos de líneas de contrato de proyecto en Project Service Automation y sincronizarlos directamente desde Project Service Automation hasta Finance.</span><span class="sxs-lookup"><span data-stu-id="1ac30-117">Maintain project contract line milestones in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="1ac30-118">Mantener las tareas de proyectos en Project Service Automation y sincronizarlas directamente desde Project Service Automation hasta Finance.</span><span class="sxs-lookup"><span data-stu-id="1ac30-118">Maintain project tasks in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="1ac30-119">Mantener categorías de transacciones de gastos en Finance y sincronizarlas directamente desde Finance hasta Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="1ac30-119">Maintain expense transaction categories in Finance, and synchronize them directly from Finance to Project Service Automation.</span></span>
- <span data-ttu-id="1ac30-120">Crear estimaciones de horas proyectos en Project Service Automation y sincronizarlas directamente desde Project Service Automation hasta Finance.</span><span class="sxs-lookup"><span data-stu-id="1ac30-120">Create project hour estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="1ac30-121">Crear estimaciones de gastos de proyectos en Project Service Automation y sincronizarlos directamente desde Project Service Automation hasta Finance.</span><span class="sxs-lookup"><span data-stu-id="1ac30-121">Create project expense estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="1ac30-122">Cree datos reales de tiempo, gastos y cuotas del proyecto en Project Service Automation y cree transacciones del proyecto en el diario de integración de Project Service Automation para que se puedan registrar en Finance.</span><span class="sxs-lookup"><span data-stu-id="1ac30-122">Create project time, expense, and fee actuals in Project Service Automation, and create project transactions in the Project Service Automation integration journal so that they can be posted in Finance.</span></span>

## <a name="data-synchronization"></a><span data-ttu-id="1ac30-123">Sincronización de datos</span><span class="sxs-lookup"><span data-stu-id="1ac30-123">Data synchronization</span></span>

<span data-ttu-id="1ac30-124">La ilustración siguiente muestra cómo se sincronizan los datos como parte de la integración entre Project Service Automation y Finance.</span><span class="sxs-lookup"><span data-stu-id="1ac30-124">The following illustration shows how data is synchronized as part of the integration between Project Service Automation and Finance.</span></span>

> [!NOTE]
> <span data-ttu-id="1ac30-125">No todas las plantillas están actualmente disponibles.</span><span class="sxs-lookup"><span data-stu-id="1ac30-125">Not all templates are currently available.</span></span> <span data-ttu-id="1ac30-126">Las plantillas se publicarán a medida que estén completadas.</span><span class="sxs-lookup"><span data-stu-id="1ac30-126">Templates will be released as they are completed.</span></span>

<span data-ttu-id="1ac30-127">[![Integración de Project Service Automation con Finance](./media/PSA-integration.png)](./media/PSA-integration.png)</span><span class="sxs-lookup"><span data-stu-id="1ac30-127">[![Project Service Automation integration with Finance](./media/PSA-integration.png)](./media/PSA-integration.png)</span></span>

## <a name="system-requirements-for-finance"></a><span data-ttu-id="1ac30-128">Requisitos del sistema para Finance</span><span class="sxs-lookup"><span data-stu-id="1ac30-128">System requirements for Finance</span></span>

<span data-ttu-id="1ac30-129">Para usar la solución de integración de Project Service Automation en Finance, debe instalar , Enterprise Edition 7.3 con la Platform update 12 o posterior.</span><span class="sxs-lookup"><span data-stu-id="1ac30-129">To use the Project Service Automation to Finance integration solution, you must install Enterprise edition 7.3 with Platform update 12 or later.</span></span>

## <a name="system-requirements-for-project-service-automation"></a><span data-ttu-id="1ac30-130">Requisitos del sistema para Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="1ac30-130">System requirements for Project Service Automation</span></span>

<span data-ttu-id="1ac30-131">Para usar la solución de integración de Project Service Automation en Finance, debe instalar los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="1ac30-131">To use the Project Service Automation to Finance integration solution, you must install the following components:</span></span>

- <span data-ttu-id="1ac30-132">Dynamics 365 Project Service Automation versión 9.0.0.0 o posterior</span><span class="sxs-lookup"><span data-stu-id="1ac30-132">Dynamics 365 Project Service Automation version 9.0.0.0 or later</span></span>
- <span data-ttu-id="1ac30-133">Solución Prospect to cash para Dynamics 365 Sales, versión 1.14.0.0 (v14) o posterior</span><span class="sxs-lookup"><span data-stu-id="1ac30-133">Prospect to cash solution for Dynamics 365 Sales, version 1.14.0.0 (v14) or later</span></span>
- <span data-ttu-id="1ac30-134">Solución de integración de Project Service Automation con Finance para Dynamics 365 Project Service Automation versión 1.0.0.0. o posterior</span><span class="sxs-lookup"><span data-stu-id="1ac30-134">Project Service Automation to Finance solution for Dynamics 365 Project Service Automation version 1.0.0.0 or later</span></span>

## <a name="install-the-project-service-automation-to-finance-integration-solution-in-your-project-service-automation-instance"></a><span data-ttu-id="1ac30-135">Instalar la solución de integración de Project Service Automation en Finance en su instancia de Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="1ac30-135">Install the Project Service Automation to Finance integration solution in your Project Service Automation instance</span></span>

<span data-ttu-id="1ac30-136">Descargue la solución de integración de Project Service Automation en Finance desde [Centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=57016) y siga las instrucciones que se incluyen con la solución.</span><span class="sxs-lookup"><span data-stu-id="1ac30-136">Download the Project Service Automation to Finance integration solution from [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=57016), and follow the instructions that are included with the solution.</span></span>
