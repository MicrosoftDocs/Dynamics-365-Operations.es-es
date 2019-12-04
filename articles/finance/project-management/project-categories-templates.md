---
title: Sincronizar las categorías de gastos de proyectos entre Finance and Operations y Project Service Automation
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar categorías de gastos de proyectos entre Microsoft Dynamics 365 Finance y Dynamics 365 Project Service Automation.
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
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 7b0b3721c3b0755218c834d2bf77ec976be3bdcc
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770321"
---
# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a><span data-ttu-id="33eaf-103">Sincronizar las categorías de gastos de proyectos entre Finance and Operations y Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="33eaf-103">Synchronize project expense categories between Finance and Operations and Project Service Automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="33eaf-104">En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar categorías de gastos de proyectos entre Dynamics 365 Finance y Dynamics 365 Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="33eaf-104">This topic describes the templates and underlying tasks that are used to synchronize project expense categories between Dynamics 365 Finance and Dynamics 365 Project Service Automation.</span></span>

> [!NOTE]
> - <span data-ttu-id="33eaf-105">La integración de tareas de proyectos, las categorías de transacción de gastos, las estimaciones de hora, las estimaciones de gastos y el bloqueo de funciones están disponibles la versión 8.0.</span><span class="sxs-lookup"><span data-stu-id="33eaf-105">Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking are available in version 8.0.</span></span>
> - <span data-ttu-id="33eaf-106">La integración de los reales está disponible en la versión 8.0.1 o posterior.</span><span class="sxs-lookup"><span data-stu-id="33eaf-106">Actuals integration is available in version 8.0.1 or later.</span></span>
> - <span data-ttu-id="33eaf-107">Si utiliza Enterprise edition 7.3.0, después de instalar KB 4132657 y 4132660 KB, podrá usar plantillas para integrar tareas de proyecto, categorías de transacción de gastos, estimaciones de hora, estimaciones de gastos y valores reales, y para configurar el bloqueo de funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="33eaf-107">If you're using Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="33eaf-108">Si debe restablecer las distribuciones contables, se recomienda instalar también KB 4131710.</span><span class="sxs-lookup"><span data-stu-id="33eaf-108">If you must reset the accounting distributions, we recommend that you also install KB 4131710.</span></span>

## <a name="data-flow-for-project-service-automation-and-finance"></a><span data-ttu-id="33eaf-109">Flujo de datos de Project Service Automation y Finance</span><span class="sxs-lookup"><span data-stu-id="33eaf-109">Data flow for Project Service Automation and Finance</span></span>

<span data-ttu-id="33eaf-110">La solución de integración de Project Service Automation y Finance usa la característica de integración de datos para sincronizar datos a través de las instancias de Project Service Automation y de Finance.</span><span class="sxs-lookup"><span data-stu-id="33eaf-110">The Project Service Automation and Finance integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance.</span></span> <span data-ttu-id="33eaf-111">Las plantillas de integración disponibles con la función de integración de datos habilitan el flujo de datos de las categorías de transacciones de gastos de proyecto entre Finance y Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="33eaf-111">The integration templates that are available with the Data integration feature enable the flow of data about project expense transaction categories between Finance and Project Service Automation.</span></span>

<span data-ttu-id="33eaf-112">Si las categorías de gastos del proyecto se dominan en Finance, el flujo de integración se realiza primero desde Finance hasta Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="33eaf-112">If the project expense categories are mastered in Finance, the integration flow is first from Finance to Project Service Automation.</span></span> <span data-ttu-id="33eaf-113">Los identificadores de integración de las categorías de gastos de proyecto se actualizan mediante la sincronización de Project Service Automation a Finance.</span><span class="sxs-lookup"><span data-stu-id="33eaf-113">The integration IDs of the project expense categories are then updated through synchronization from Project Service Automation to Finance.</span></span>

<span data-ttu-id="33eaf-114">Si las categorías de gastos del proyecto se dominan en Project Service Automation, el flujo de integración se realiza primero desde Project Service Automation hasta Finance.</span><span class="sxs-lookup"><span data-stu-id="33eaf-114">If the project expense categories are mastered in Project Service Automation, the integration flow is first from Project Service Automation to Finance.</span></span> <span data-ttu-id="33eaf-115">Las categorías de proyecto deben estar ya configuradas en Finance antes de sincronizar desde Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="33eaf-115">The project categories must already be configured in Finance before the synchronization from Project Service Automation.</span></span> <span data-ttu-id="33eaf-116">A continuación sincronice desde Finance hasta Project Service Automation y desde Project Service Automation hasta Finance.</span><span class="sxs-lookup"><span data-stu-id="33eaf-116">Then synchronize from Finance back to Project Service Automation, and then from Project Service Automation to Finance again.</span></span> <span data-ttu-id="33eaf-117">De este modo, ayuda a garantizar que las categorías estén vinculadas y que no se creen duplicados.</span><span class="sxs-lookup"><span data-stu-id="33eaf-117">In this way, you help guarantee that the categories are linked, and that no duplicates are created.</span></span>

> [!NOTE]
> <span data-ttu-id="33eaf-118">Normalmente, las categorías de gastos del proyecto se dominan en Finance.</span><span class="sxs-lookup"><span data-stu-id="33eaf-118">Typically, the project expense categories are mastered in Finance.</span></span> <span data-ttu-id="33eaf-119">Sin embargo, si no se han creado o si ya se han creado categorías de gastos en Project Service Automation, primero debe realizar la sincronización utilizando la plantilla Categorías de transacción de gastos de proyecto (PSA a Fin and Ops).</span><span class="sxs-lookup"><span data-stu-id="33eaf-119">However, if they aren't, or if expense categories have already been created in Project Service Automation, you must first synchronize by using the Project expense transaction categories (PSA to Fin and Ops) template.</span></span> <span data-ttu-id="33eaf-120">Se sincronizan mediante la plantilla de categorías de transacción de gastos de proyecto (de Fin and Ops a PSA).</span><span class="sxs-lookup"><span data-stu-id="33eaf-120">Then synchronize by using the Project expense transaction categories (Fin and Ops to PSA) template.</span></span> <span data-ttu-id="33eaf-121">A continuación, deberá ejecutar la sincronización desde Project Service Automation a Finance una vez más.</span><span class="sxs-lookup"><span data-stu-id="33eaf-121">You should then run the synchronization from Project Service Automation to Finance one more time.</span></span>
>
> <span data-ttu-id="33eaf-122">Si sincroniza primero desde Project Service Automation, deben cumplirse los siguientes requisitos en Finance antes de que se ejecute la sincronización:</span><span class="sxs-lookup"><span data-stu-id="33eaf-122">If you synchronize first from Project Service Automation, the following requirements must be met in Finance before the synchronization is run:</span></span>
>
> - <span data-ttu-id="33eaf-123">Debe existir la categoría compartida que coincida con la categoría de proyecto establecida en Project Service Automation y debe estar habilitada tanto **Proyecto** como para **Gastos**.</span><span class="sxs-lookup"><span data-stu-id="33eaf-123">The shared category that matches the project category that is set up in Project Service Automation must exist, and it must be enabled for both **Project** and **Expense**.</span></span>
> - <span data-ttu-id="33eaf-124">Para cada entidad jurídica de Finance con la que deba integrarse, deben existir las siguientes categorías de proyecto:</span><span class="sxs-lookup"><span data-stu-id="33eaf-124">For each Finance legal entity that must be integrated with, the following project categories must exist:</span></span>
>
>     - <span data-ttu-id="33eaf-125">**Categoría de proyecto** existe.</span><span class="sxs-lookup"><span data-stu-id="33eaf-125">**Project category** exists.</span></span> 
>     - <span data-ttu-id="33eaf-126">**Usar en gasto** está habilitado.</span><span class="sxs-lookup"><span data-stu-id="33eaf-126">**Use in Expense** is enabled.</span></span>
>     - <span data-ttu-id="33eaf-127">**Activo en el diario** está habilitado.</span><span class="sxs-lookup"><span data-stu-id="33eaf-127">**Active in journal** is enabled.</span></span>
>     - <span data-ttu-id="33eaf-128">**Tipo de transacción** se ha configurado en **Gasto**.</span><span class="sxs-lookup"><span data-stu-id="33eaf-128">**Transaction type** is set to **Expense**.</span></span>

<span data-ttu-id="33eaf-129">La ilustración siguiente muestra cómo se sincronizan los datos entre Project Service Automation y Finance.</span><span class="sxs-lookup"><span data-stu-id="33eaf-129">The following illustration shows how the data is synchronized between Project Service Automation and Finance.</span></span>

<span data-ttu-id="33eaf-130">[![Flujo de datos para la integración de Project Service Automation con Finance](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span><span class="sxs-lookup"><span data-stu-id="33eaf-130">[![Data flow for Project Service Automation integration with Finance](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span></span>

## <a name="project-expense-category-synchronization-from-finance-to-project-service-automation"></a><span data-ttu-id="33eaf-131">Sincronización de categorías de gastos de proyecto de Finance a Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="33eaf-131">Project expense category synchronization from Finance to Project Service Automation</span></span>

### <a name="template-and-task"></a><span data-ttu-id="33eaf-132">Plantilla y tarea</span><span class="sxs-lookup"><span data-stu-id="33eaf-132">Template and task</span></span>

<span data-ttu-id="33eaf-133">Para obtener acceso a la plantilla, en el centro de administración de Microsoft Power Apps, seleccione **Proyectos** y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.</span><span class="sxs-lookup"><span data-stu-id="33eaf-133">To access the template, in the Microsoft Power Apps admin center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="33eaf-134">La plantilla y la tarea subyacente siguientes se usan para sincronizar las categorías de gastos del proyecto desde Finance hasta Project Service Automation:</span><span class="sxs-lookup"><span data-stu-id="33eaf-134">The following template and underlying task are used to synchronize project expense categories from Finance to Project Service Automation:</span></span>

- <span data-ttu-id="33eaf-135">**Nombre de la plantilla en la integración de datos:** categorías de transacción de gastos del proyecto (de Fin and Ops a PSA)</span><span class="sxs-lookup"><span data-stu-id="33eaf-135">**Name of the template in Data integration:** Project expense transaction categories (Fin and Ops to PSA)</span></span>
- <span data-ttu-id="33eaf-136">**Nombre de la tarea en el proyecto:** categorías sincronizadas a PSA</span><span class="sxs-lookup"><span data-stu-id="33eaf-136">**Name of the task in the project:** Sync categories to PSA</span></span>

### <a name="entity-set"></a><span data-ttu-id="33eaf-137">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="33eaf-137">Entity set</span></span>

| <span data-ttu-id="33eaf-138">Finanzas</span><span class="sxs-lookup"><span data-stu-id="33eaf-138">Finance</span></span>                           | <span data-ttu-id="33eaf-139">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="33eaf-139">Project Service Automation</span></span> |
|-----------------------------------|----------------------------|
| <span data-ttu-id="33eaf-140">Entidad de integración para categorías</span><span class="sxs-lookup"><span data-stu-id="33eaf-140">Integration entity for categories</span></span> | <span data-ttu-id="33eaf-141">Categorías de transacciones</span><span class="sxs-lookup"><span data-stu-id="33eaf-141">Transaction categories</span></span>     |

### <a name="entity-flow"></a><span data-ttu-id="33eaf-142">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="33eaf-142">Entity flow</span></span>

<span data-ttu-id="33eaf-143">Las categorías de gastos del proyecto se administran en Finance y después se sincronizan con Project Service Automation como categorías de transacción.</span><span class="sxs-lookup"><span data-stu-id="33eaf-143">Project expense categories are managed in Finance, and they are synchronized to Project Service Automation as transaction categories.</span></span>

### <a name="power-query"></a><span data-ttu-id="33eaf-144">Power Query</span><span class="sxs-lookup"><span data-stu-id="33eaf-144">Power Query</span></span>

<span data-ttu-id="33eaf-145">Al sincronizar a Project Service Automation, debe usar Microsoft Power Query for Excel para establecer el tipo de facturación en la categoría de transacción.</span><span class="sxs-lookup"><span data-stu-id="33eaf-145">When you're synchronizing to Project Service Automation, you must use Microsoft Power Query for Excel to set the billing type on the transaction category.</span></span> <span data-ttu-id="33eaf-146">La plantilla de las categorías de transacción de gastos del proyecto (Fin and Ops a PSA) proporciona una columna predeterminada y una asignación.</span><span class="sxs-lookup"><span data-stu-id="33eaf-146">The Project expense transaction categories (Fin and Ops to PSA) template provides a default column and mapping.</span></span> <span data-ttu-id="33eaf-147">Si crea su propia plantilla, debe agregar una columna condicional en Power Query.</span><span class="sxs-lookup"><span data-stu-id="33eaf-147">If you create your own template, you must add a conditional column in Power Query.</span></span> <span data-ttu-id="33eaf-148">Siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="33eaf-148">Follow these steps.</span></span>

1. <span data-ttu-id="33eaf-149">Haga clic en la flecha para abrir la asignación de la tarea de categorías de gastos de proyecto en la plantilla de categorías de transacción de gastos de proyecto (de Fin and Ops a PSA).</span><span class="sxs-lookup"><span data-stu-id="33eaf-149">Click the arrow to open the mapping of the project expense categories task in the Project expense transaction categories (Fin and Ops to PSA) template.</span></span>
2. <span data-ttu-id="33eaf-150">Haga clic en el vínculo **Consulta y filtrado avanzados** para abrir Power Query.</span><span class="sxs-lookup"><span data-stu-id="33eaf-150">Click the **Advance Query and Filtering** link to open Power Query.</span></span>
2. <span data-ttu-id="33eaf-151">Seleccione **Agregar columna condicional**.</span><span class="sxs-lookup"><span data-stu-id="33eaf-151">Select **Add Conditional Column**.</span></span>
3. <span data-ttu-id="33eaf-152">Especifique un nombre para la nueva columna, como **BillingType**.</span><span class="sxs-lookup"><span data-stu-id="33eaf-152">Enter a name for the new column, such as **BillingType**.</span></span>
4. <span data-ttu-id="33eaf-153">Especifique la siguiente condición: **if CATEGORYID not equal to null then 19235001, Otherwise null**.</span><span class="sxs-lookup"><span data-stu-id="33eaf-153">Enter the following condition: **if CATEGORYID not equal to null then 19235001, Otherwise null**.</span></span>
5. <span data-ttu-id="33eaf-154">En la columna, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="33eaf-154">Click **OK** on the column.</span></span>
6. <span data-ttu-id="33eaf-155">Asegúrese de asignar esta nueva columna en la página de la asignación.</span><span class="sxs-lookup"><span data-stu-id="33eaf-155">Be sure to map this new column on the mapping page.</span></span>

<span data-ttu-id="33eaf-156">La siguiente ilustración muestra un ejemplo de la asignación de tarea de plantilla en integración de datos.</span><span class="sxs-lookup"><span data-stu-id="33eaf-156">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="33eaf-157">La asignación muestra la información de campo que se sincronizará de Finance a Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="33eaf-157">The mapping shows the field information that will be synchronized from Finance to Project Service Automation.</span></span>

<span data-ttu-id="33eaf-158">[![Asignación de la plantilla](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="33eaf-158">[![Template mapping](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span></span>

## <a name="project-expense-category-synchronization-from-project-service-automation-to-finance"></a><span data-ttu-id="33eaf-159">Sincronización de categorías de gastos de proyecto de Project Service Automation a Finance</span><span class="sxs-lookup"><span data-stu-id="33eaf-159">Project expense category synchronization from Project Service Automation to Finance</span></span>

### <a name="template-and-task"></a><span data-ttu-id="33eaf-160">Plantilla y tarea</span><span class="sxs-lookup"><span data-stu-id="33eaf-160">Template and task</span></span>

<span data-ttu-id="33eaf-161">La plantilla y la tarea subyacente siguientes se usan para sincronizar las categorías de gastos del proyecto de Project Service Automation a Finance:</span><span class="sxs-lookup"><span data-stu-id="33eaf-161">The following template and underlying task are used to synchronize project expense categories from Project Service Automation to Finance:</span></span>

- <span data-ttu-id="33eaf-162">**Nombre de la plantilla en la integración de datos:** categorías de transacción de gastos del proyecto (de PSA a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="33eaf-162">**Name of the template in Data integration:** Project expense transaction categories (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="33eaf-163">**Nombre de la tarea en el proyecto:** sincronizar categorías con Fin Ops</span><span class="sxs-lookup"><span data-stu-id="33eaf-163">**Name of the task in the project:** Sync categories to Fin Ops</span></span>

### <a name="entity-set"></a><span data-ttu-id="33eaf-164">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="33eaf-164">Entity set</span></span>

| <span data-ttu-id="33eaf-165">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="33eaf-165">Project Service Automation</span></span> | <span data-ttu-id="33eaf-166">Finanzas</span><span class="sxs-lookup"><span data-stu-id="33eaf-166">Finance</span></span>                           |
|----------------------------|-----------------------------------|
| <span data-ttu-id="33eaf-167">Categorías de transacciones</span><span class="sxs-lookup"><span data-stu-id="33eaf-167">Transaction categories</span></span>     | <span data-ttu-id="33eaf-168">Entidad de integración para categorías</span><span class="sxs-lookup"><span data-stu-id="33eaf-168">Integration entity for categories</span></span> |

### <a name="entity-flow"></a><span data-ttu-id="33eaf-169">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="33eaf-169">Entity flow</span></span>

<span data-ttu-id="33eaf-170">Las categorías de gastos del proyecto se administran en Finance y después se sincronizan con Project Service Automation como categorías de transacción.</span><span class="sxs-lookup"><span data-stu-id="33eaf-170">Project expense categories are managed in Finance, and they are synchronized to Project Service Automation as transaction categories.</span></span> <span data-ttu-id="33eaf-171">La sincronización con Finance actualiza la categoría de proyectos en Finance con el identificador de integración de Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="33eaf-171">The synchronization back to Finance updates the project category in Finance with the integration ID from Project Service Automation.</span></span>

### <a name="template-mapping-in-data-integration"></a><span data-ttu-id="33eaf-172">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="33eaf-172">Template mapping in Data integration</span></span>

<span data-ttu-id="33eaf-173">La siguiente ilustración muestra un ejemplo de la asignación de tarea de plantilla en integración de datos.</span><span class="sxs-lookup"><span data-stu-id="33eaf-173">The following illustration shows an example of the template task mapping in Data integration.</span></span>

> [!NOTE]
> <span data-ttu-id="33eaf-174">La asignación muestra la información de campo que se sincronizará de Project Service Automation a Finance.</span><span class="sxs-lookup"><span data-stu-id="33eaf-174">The mapping shows the field information that will be synchronized from Project Service Automation to Finance.</span></span>

<span data-ttu-id="33eaf-175">[![Asignación de la plantilla](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="33eaf-175">[![Template mapping](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span></span>
