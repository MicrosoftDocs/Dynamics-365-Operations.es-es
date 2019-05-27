---
title: Sincronizar las categorías de gastos de proyectos entre Finance and Operations y Project Service Automation
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar categorías de gastos de proyectos entre Microsoft Dynamics 365 for Finance and Operations y Microsoft Dynamics 365 for Project Service Automation.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: c4d09fde2cf4335553243c136590f9f3135db97a
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558251"
---
# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a><span data-ttu-id="fd0f3-103">Sincronizar las categorías de gastos de proyectos entre Finance and Operations y Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="fd0f3-103">Synchronize project expense categories between Finance and Operations and Project Service Automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="fd0f3-104">En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar categorías de gastos de proyectos entre Microsoft Dynamics 365 for Finance and Operations y Microsoft Dynamics 365 for Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-104">This topic describes the templates and underlying tasks that are used to synchronize project expense categories between Microsoft Dynamics 365 for Finance and Operations and Microsoft Dynamics 365 for Project Service Automation.</span></span>

> [!NOTE]
> - <span data-ttu-id="fd0f3-105">La integración de tareas de proyectos, las categorías de transacción de gastos, las estimaciones de hora, las estimaciones de gastos y el bloqueo de funciones están disponibles en Microsoft Dynamics 365 for Finance and Operations versión 8.0.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-105">Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking are available in Microsoft Dynamics 365 for Finance and Operations version 8.0.</span></span>
> - <span data-ttu-id="fd0f3-106">La integración de los reales está disponible en Microsoft Dynamics 365 for Finance and Operations versión 8.0.1 o posterior.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-106">Actuals integration is available in Microsoft Dynamics 365 for Finance and Operations version 8.0.1 or later.</span></span>
> - <span data-ttu-id="fd0f3-107">Si utiliza Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, después de instalar KB 4132657 y 4132660 KB, podrá usar plantillas para integrar tareas de proyecto, categorías de transacción de gastos, estimaciones de hora, estimaciones de gastos y valores reales, y para configurar el bloqueo de funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-107">If you're using Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="fd0f3-108">Si debe restablecer las distribuciones contables, se recomienda instalar también KB 4131710.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-108">If you must reset the accounting distributions, we recommend that you also install KB 4131710.</span></span>

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a><span data-ttu-id="fd0f3-109">Flujo de datos de Project Service Automation y Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="fd0f3-109">Data flow for Project Service Automation and Finance and Operations</span></span>

<span data-ttu-id="fd0f3-110">La solución de integración de Project Service Automation y Finance and Operations usa la característica de integración de datos para sincronizar datos a través de las instancias de Project Service Automation y de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-110">The Project Service Automation and Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance and Operations.</span></span> <span data-ttu-id="fd0f3-111">Las plantillas de integración disponibles con la función de integración de datos habilitan el flujo de datos de las categorías de transacciones de gastos de proyecto entre Project Service Automation y Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-111">The integration templates that are available with the Data integration feature enable the flow of data about project expense transaction categories between Finance and Operations and Project Service Automation.</span></span>

<span data-ttu-id="fd0f3-112">Si las categorías de gastos del proyecto se dominan en Finance and Operations, el flujo de integración se realiza primero desde Finance and Operations hasta Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-112">If the project expense categories are mastered in Finance and Operations, the integration flow is first from Finance and Operations to Project Service Automation.</span></span> <span data-ttu-id="fd0f3-113">Los identificadores de integración de las categorías de gastos de proyecto se actualizan mediante la sincronización de Project Service Automation a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-113">The integration IDs of the project expense categories are then updated through synchronization from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="fd0f3-114">Si las categorías de gastos del proyecto se dominan en Project Service Automation, el flujo de integración se realiza primero desde Project Service Automation hasta Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-114">If the project expense categories are mastered in Project Service Automation, the integration flow is first from Project Service Automation to Finance and Operations.</span></span> <span data-ttu-id="fd0f3-115">Las categorías de proyecto deben estar ya configuradas en Finance and Operations antes de sincronizar desde Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-115">The project categories must already be configured in Finance and Operations before the synchronization from Project Service Automation.</span></span> <span data-ttu-id="fd0f3-116">A continuación sincronice desde Finance and Operations hasta Project Service Automation y desde Project Service Automation hasta Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-116">Then synchronize from Finance and Operations back to Project Service Automation, and then from Project Service Automation to Finance and Operations again.</span></span> <span data-ttu-id="fd0f3-117">De este modo, ayuda a garantizar que las categorías estén vinculadas y que no se creen duplicados.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-117">In this way, you help guarantee that the categories are linked, and that no duplicates are created.</span></span>

> [!NOTE]
> <span data-ttu-id="fd0f3-118">Normalmente, las categorías de gastos del proyecto se dominan en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-118">Typically, the project expense categories are mastered in Finance and Operations.</span></span> <span data-ttu-id="fd0f3-119">Sin embargo, si no se dominan en Finance and Operations, o si ya se han creado categorías de gastos en Project Service Automation, primero debe realizar la sincronización utilizando la plantilla Categorías de transacción de gastos de proyecto (PSA a Fin and Ops).</span><span class="sxs-lookup"><span data-stu-id="fd0f3-119">However, if they aren't mastered in Finance and Operations, or if expense categories have already been created in Project Service Automation, you must first synchronize by using the Project expense transaction categories (PSA to Fin and Ops) template.</span></span> <span data-ttu-id="fd0f3-120">Se sincronizan mediante la plantilla de categorías de transacción de gastos de proyecto (de Fin and Ops a PSA).</span><span class="sxs-lookup"><span data-stu-id="fd0f3-120">Then synchronize by using the Project expense transaction categories (Fin and Ops to PSA) template.</span></span> <span data-ttu-id="fd0f3-121">A continuación, deberá ejecutar la sincronización desde Project Service Automation a Finance and Operations una vez más.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-121">You should then run the synchronization from Project Service Automation to Finance and Operations one more time.</span></span>
>
> <span data-ttu-id="fd0f3-122">Si sincroniza primero desde Project Service Automation, deben cumplirse los siguientes requisitos en Finance and Operations antes de que se ejecute la sincronización:</span><span class="sxs-lookup"><span data-stu-id="fd0f3-122">If you synchronize first from Project Service Automation, the following requirements must be met in Finance and Operations before the synchronization is run:</span></span>
>
> - <span data-ttu-id="fd0f3-123">Debe existir la categoría compartida que coincida con la categoría de proyecto establecida en Project Service Automation y debe estar habilitada tanto **Proyecto** como para **Gastos**.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-123">The shared category that matches the project category that is set up in Project Service Automation must exist, and it must be enabled for both **Project** and **Expense**.</span></span>
> - <span data-ttu-id="fd0f3-124">Para cada entidad jurídica de Finance and Operations con la que deba integrarse, deben existir las siguientes categorías de proyecto:</span><span class="sxs-lookup"><span data-stu-id="fd0f3-124">For each Finance and Operations legal entity that must be integrated with, the following project categories must exist:</span></span>
>
>     - <span data-ttu-id="fd0f3-125">**Categoría de proyecto** existe.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-125">**Project category** exists.</span></span> 
>     - <span data-ttu-id="fd0f3-126">**Usar en gasto** está habilitado.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-126">**Use in Expense** is enabled.</span></span>
>     - <span data-ttu-id="fd0f3-127">**Activo en el diario** está habilitado.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-127">**Active in journal** is enabled.</span></span>
>     - <span data-ttu-id="fd0f3-128">**Tipo de transacción** se ha configurado en **Gasto**.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-128">**Transaction type** is set to **Expense**.</span></span>

<span data-ttu-id="fd0f3-129">La ilustración siguiente muestra cómo se sincronizan los datos entre Project Service Automation y Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-129">The following illustration shows how the data is synchronized between Project Service Automation and Finance and Operations.</span></span>

<span data-ttu-id="fd0f3-130">[![Flujo de datos para la integración de Project Service Automation con Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span><span class="sxs-lookup"><span data-stu-id="fd0f3-130">[![Data flow for Project Service Automation integration with Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span></span>

## <a name="project-expense-category-synchronization-from-finance-and-operations-to-project-service-automation"></a><span data-ttu-id="fd0f3-131">Sincronización de categorías de gastos de proyecto de Finance and Operations a Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="fd0f3-131">Project expense category synchronization from Finance and Operations to Project Service Automation</span></span>

### <a name="template-and-task"></a><span data-ttu-id="fd0f3-132">Plantilla y tarea</span><span class="sxs-lookup"><span data-stu-id="fd0f3-132">Template and task</span></span>

<span data-ttu-id="fd0f3-133">Para obtener acceso a la plantilla, en el centro de administración de Microsoft PowerApps, seleccione **Proyectos** y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-133">To access the template, in the Microsoft PowerApps admin center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="fd0f3-134">La plantilla y la tarea subyacente siguientes se usan para sincronizar las categorías de gastos del proyecto desde Finance and Operations hasta Project Service Automation:</span><span class="sxs-lookup"><span data-stu-id="fd0f3-134">The following template and underlying task are used to synchronize project expense categories from Finance and Operations to Project Service Automation:</span></span>

- <span data-ttu-id="fd0f3-135">**Nombre de la plantilla en la integración de datos:** categorías de transacción de gastos del proyecto (de Fin and Ops a PSA)</span><span class="sxs-lookup"><span data-stu-id="fd0f3-135">**Name of the template in Data integration:** Project expense transaction categories (Fin and Ops to PSA)</span></span>
- <span data-ttu-id="fd0f3-136">**Nombre de la tarea en el proyecto:** categorías sincronizadas a PSA</span><span class="sxs-lookup"><span data-stu-id="fd0f3-136">**Name of the task in the project:** Sync categories to PSA</span></span>

### <a name="entity-set"></a><span data-ttu-id="fd0f3-137">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="fd0f3-137">Entity set</span></span>

| <span data-ttu-id="fd0f3-138">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="fd0f3-138">Finance and Operations</span></span>            | <span data-ttu-id="fd0f3-139">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="fd0f3-139">Project Service Automation</span></span> |
|-----------------------------------|----------------------------|
| <span data-ttu-id="fd0f3-140">Entidad de integración para categorías</span><span class="sxs-lookup"><span data-stu-id="fd0f3-140">Integration entity for categories</span></span> | <span data-ttu-id="fd0f3-141">Categorías de transacciones</span><span class="sxs-lookup"><span data-stu-id="fd0f3-141">Transaction categories</span></span>     |

### <a name="entity-flow"></a><span data-ttu-id="fd0f3-142">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="fd0f3-142">Entity flow</span></span>

<span data-ttu-id="fd0f3-143">Las categorías de gastos del proyecto se administran en Finance and Operations y después se sincronizan con Project Service Automation como categorías de transacción.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-143">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span>

### <a name="power-query"></a><span data-ttu-id="fd0f3-144">Power Query</span><span class="sxs-lookup"><span data-stu-id="fd0f3-144">Power Query</span></span>

<span data-ttu-id="fd0f3-145">Al sincronizar a Project Service Automation, debe usar Microsoft Power Query for Excel para establecer el tipo de facturación en la categoría de transacción.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-145">When you're synchronizing to Project Service Automation, you must use Microsoft Power Query for Excel to set the billing type on the transaction category.</span></span> <span data-ttu-id="fd0f3-146">La plantilla de las categorías de transacción de gastos del proyecto (Fin and Ops a PSA) proporciona una columna predeterminada y una asignación.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-146">The Project expense transaction categories (Fin and Ops to PSA) template provides a default column and mapping.</span></span> <span data-ttu-id="fd0f3-147">Si crea su propia plantilla, debe agregar una columna condicional en Power Query.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-147">If you create your own template, you must add a conditional column in Power Query.</span></span> <span data-ttu-id="fd0f3-148">Siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="fd0f3-148">Follow these steps.</span></span>

1. <span data-ttu-id="fd0f3-149">Haga clic en la flecha para abrir la asignación de la tarea de categorías de gastos de proyecto en la plantilla de categorías de transacción de gastos de proyecto (de Fin and Ops a PSA).</span><span class="sxs-lookup"><span data-stu-id="fd0f3-149">Click the arrow to open the mapping of the project expense categories task in the Project expense transaction categories (Fin and Ops to PSA) template.</span></span>
2. <span data-ttu-id="fd0f3-150">Haga clic en el vínculo **Consulta y filtrado avanzados** para abrir Power Query.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-150">Click the **Advance Query and Filtering** link to open Power Query.</span></span>
2. <span data-ttu-id="fd0f3-151">Seleccione **Agregar columna condicional**.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-151">Select **Add Conditional Column**.</span></span>
3. <span data-ttu-id="fd0f3-152">Especifique un nombre para la nueva columna, como **BillingType**.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-152">Enter a name for the new column, such as **BillingType**.</span></span>
4. <span data-ttu-id="fd0f3-153">Especifique la siguiente condición: **if CATEGORYID not equal to null then 19235001, Otherwise null**.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-153">Enter the following condition: **if CATEGORYID not equal to null then 19235001, Otherwise null**.</span></span>
5. <span data-ttu-id="fd0f3-154">En la columna, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-154">Click **OK** on the column.</span></span>
6. <span data-ttu-id="fd0f3-155">Asegúrese de asignar esta nueva columna en la página de la asignación.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-155">Be sure to map this new column on the mapping page.</span></span>

<span data-ttu-id="fd0f3-156">La siguiente ilustración muestra un ejemplo de la asignación de tarea de plantilla en integración de datos.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-156">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="fd0f3-157">La asignación muestra la información de campo que se sincronizará de Finance and Operations a Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-157">The mapping shows the field information that will be synchronized from Finance and Operations to Project Service Automation.</span></span>

<span data-ttu-id="fd0f3-158">[![Asignación de la plantilla](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="fd0f3-158">[![Template mapping](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span></span>

## <a name="project-expense-category-synchronization-from-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="fd0f3-159">Sincronización de categorías de gastos de proyecto de Project Service Automation a Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="fd0f3-159">Project expense category synchronization from Project Service Automation to Finance and Operations</span></span>

### <a name="template-and-task"></a><span data-ttu-id="fd0f3-160">Plantilla y tarea</span><span class="sxs-lookup"><span data-stu-id="fd0f3-160">Template and task</span></span>

<span data-ttu-id="fd0f3-161">La plantilla y la tarea subyacente siguientes se usan para sincronizar las categorías de gastos del proyecto de Project Service Automation a Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="fd0f3-161">The following template and underlying task are used to synchronize project expense categories from Project Service Automation to Finance and Operations:</span></span>

- <span data-ttu-id="fd0f3-162">**Nombre de la plantilla en la integración de datos:** categorías de transacción de gastos del proyecto (de PSA a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="fd0f3-162">**Name of the template in Data integration:** Project expense transaction categories (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="fd0f3-163">**Nombre de la tarea en el proyecto:** sincronizar categorías con Fin Ops</span><span class="sxs-lookup"><span data-stu-id="fd0f3-163">**Name of the task in the project:** Sync categories to Fin Ops</span></span>

### <a name="entity-set"></a><span data-ttu-id="fd0f3-164">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="fd0f3-164">Entity set</span></span>

| <span data-ttu-id="fd0f3-165">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="fd0f3-165">Project Service Automation</span></span> | <span data-ttu-id="fd0f3-166">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="fd0f3-166">Finance and Operations</span></span>            |
|----------------------------|-----------------------------------|
| <span data-ttu-id="fd0f3-167">Categorías de transacciones</span><span class="sxs-lookup"><span data-stu-id="fd0f3-167">Transaction categories</span></span>     | <span data-ttu-id="fd0f3-168">Entidad de integración para categorías</span><span class="sxs-lookup"><span data-stu-id="fd0f3-168">Integration entity for categories</span></span> |

### <a name="entity-flow"></a><span data-ttu-id="fd0f3-169">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="fd0f3-169">Entity flow</span></span>

<span data-ttu-id="fd0f3-170">Las categorías de gastos del proyecto se administran en Finance and Operations y después se sincronizan con Project Service Automation como categorías de transacción.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-170">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span> <span data-ttu-id="fd0f3-171">La sincronización con Finance and Operations actualiza la categoría de proyectos en Finance and Operations con el identificador de integración de Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-171">The synchronization back to Finance and Operations updates the project category in Finance and Operations with the integration ID from Project Service Automation.</span></span>

### <a name="template-mapping-in-data-integration"></a><span data-ttu-id="fd0f3-172">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="fd0f3-172">Template mapping in Data integration</span></span>

<span data-ttu-id="fd0f3-173">La siguiente ilustración muestra un ejemplo de la asignación de tarea de plantilla en integración de datos.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-173">The following illustration shows an example of the template task mapping in Data integration.</span></span>

> [!NOTE]
> <span data-ttu-id="fd0f3-174">La asignación muestra la información de campo que se sincronizará de Project Service Automation a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fd0f3-174">The mapping shows the field information that will be synchronized from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="fd0f3-175">[![Asignación de la plantilla](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="fd0f3-175">[![Template mapping](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span></span>
