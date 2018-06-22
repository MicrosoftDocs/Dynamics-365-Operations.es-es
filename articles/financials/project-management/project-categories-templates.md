---
title: "Sincronizar las categorías de gastos de proyectos de Project Service Automation"
description: "En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar las categorías de gastos de proyectos entre Microsoft Dynamics 365 for Finance and Operations y Dynamics 365 for Project Service Automation."
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
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: dcdb9b6ec296073d511c069cdceb1c61080b6d97
ms.contentlocale: es-es
ms.lasthandoff: 05/29/2018

---

# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a><span data-ttu-id="4f1ac-103">Sincronizar las categorías de gastos de proyectos entre Finance and Operations y Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="4f1ac-103">Synchronize project expense categories between Finance and Operations and Project Service Automation</span></span>

<span data-ttu-id="4f1ac-104">En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar las categorías de gastos de proyectos entre Microsoft Dynamics 365 for Finance and Operations y Dynamics 365 for Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-104">This topic describes the templates and underlying tasks that are used to synchronize project expense categories between Microsoft Dynamics 365 for Finance and Operations and Dynamics 365 for Project Service Automation.</span></span>

> [!NOTE]
> <span data-ttu-id="4f1ac-105">La integración de tareas de proyectos, las categorías de la transacción de gastos, las estimaciones de hora, las estimaciones de gastos y el bloqueo de la función están disponibles en Dynamics 365 for Finance and Operations versión 8.0.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-105">Project tasks integration, expense transaction categories, hour estimates, expense estimates, and functionality locking is available in Dynamics 365 for Finance and Operations version 8.0.</span></span>

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a><span data-ttu-id="4f1ac-106">Flujo de datos de Project Service Automation y Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4f1ac-106">Data flow for Project Service Automation and Finance and Operations</span></span>

<span data-ttu-id="4f1ac-107">La solución de integración de Project Service Automation y Finance and Operations usa la característica de integración de datos para sincronizar datos a través de las instancias de Project Service Automation y de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-107">The Project Service Automation and Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance and Operations.</span></span> <span data-ttu-id="4f1ac-108">Las plantillas de integración disponibles con la función de integración de datos habilitan el flujo de datos de las categorías de transacciones de gastos de proyecto entre Project Service Automation y Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-108">The integration templates that are available with the Data integration feature enables the flow of data about project expense transaction categories between Finance and Operations and Project Service Automation.</span></span>

<span data-ttu-id="4f1ac-109">Si las categorías de gastos de proyectos se dominan en Finance and Operations, el flujo de integración se realiza primero desde Finance and Operations hasta Project Service Automation y después se actualizan los id. de integración de las categorías de gastos de proyectos sincronizando desde Project Service Automation hasta Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-109">If the project expense categories are mastered in Finance and Operations, the integration flow is first from Finance and Operations to Project Service Automation, and then updating the project expense categories integration IDs by synchronizing from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="4f1ac-110">Si las categorías de gastos del proyecto se dominan en Project Service Automation, el flujo de integración se realiza primero desde Project Service Automation hasta Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-110">If the project expense categories are mastered in Project Service Automation, the integration flow is first from Project Service Automation to Finance and Operations.</span></span> <span data-ttu-id="4f1ac-111">Las categorías de proyecto deben estar ya configuradas en Finance and Operations antes de sincronizar desde Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-111">The project categories must already be configured in Finance and Operations prior to the synchronization from Project Service Automation.</span></span> <span data-ttu-id="4f1ac-112">A continuación sincronice desde Finance and Operations hasta Project Service Automation y desde Project Service Automation hasta Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-112">Then synchronize from Finance and Operations back to Project Service Automation and then from Project Service Automation to Finance and Operations again.</span></span> <span data-ttu-id="4f1ac-113">Esto garantiza que las categorías estén vinculadas y que no se creen duplicados.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-113">This ensures the categories are linked and duplicates are not created.</span></span>

> [!NOTE]
> <span data-ttu-id="4f1ac-114">Normalmente, las categorías de gastos del proyecto se dominan en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-114">Typically, the project expense categories will be mastered in Finance and Operations.</span></span> <span data-ttu-id="4f1ac-115">Si esta no es su situación o ya tiene categorías de gastos creadas en Project Service Automation, primero debe efectuar la sincronización usando las categorías de transacción de gastos del proyecto (de PSA a Fin and Ops) y después realizar la sincronización usando categorías de transacción de gastos del proyecto (de Fin and Ops a PSA).</span><span class="sxs-lookup"><span data-stu-id="4f1ac-115">If that is not your situation, or you already have expense categories created in Project Service Automation, you must first sync using the Project expense transaction categories (PSA to Fin and Ops) and then sync using Project expense transaction categories (Fin and Ops to PSA).</span></span> <span data-ttu-id="4f1ac-116">A continuación debe ejecutar la sincronización desde PSA a Fin and Ops una vez más.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-116">You should then run the sync from PSA to Fin and Ops one more time.</span></span>

> <span data-ttu-id="4f1ac-117">Si sincroniza primero desde Project Service Automation, las categorías de proyecto deben estar ya configuradas en Finance and Operations y todas las categorías de proyecto que es necesario que se sincronicen con las categorías de transacción de Project Service Automation se deben configurar para ser **Activas en diarios**.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-117">If synchronizing first from Project Service Automation, the project categories must already be set up in Finance and Operations and any project categories that need to be synched with the Project Service Automation transaction categories must be set up to be **Active in journals**.</span></span>

<span data-ttu-id="4f1ac-118">La ilustración siguiente muestra cómo se sincronizan los datos entre Project Service Automation y Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-118">The following illustration shows how the data is synchronized between Project Service Automation and Finance and Operations.</span></span>

<span data-ttu-id="4f1ac-119">[![Flujo de datos para la integración de Project Service Automation con Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span><span class="sxs-lookup"><span data-stu-id="4f1ac-119">[![Data flow for Project Service Automation integration with Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span></span>


## <a name="templates-and-tasks"></a><span data-ttu-id="4f1ac-120">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="4f1ac-120">Templates and tasks</span></span>

<span data-ttu-id="4f1ac-121">Para obtener acceso a las plantillas disponibles, en el centro de administración de Microsoft PowerApps, seleccione **Proyectos** y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-121">To access available templates, in the Microsoft PowerApps Admin Center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="4f1ac-122">La plantilla y la tarea subyacente siguientes se usan para sincronizar las categorías de gastos del proyecto desde Finance and Operations hasta Project Service Automation:</span><span class="sxs-lookup"><span data-stu-id="4f1ac-122">The following template and underlying task is used to synchronize project expense categories from Finance and Operations to Project Service Automation:</span></span>

-  <span data-ttu-id="4f1ac-123">**Nombre de la plantilla en la integración de datos:** categorías de transacción de gastos del proyecto (de Fin and Ops a PSA)</span><span class="sxs-lookup"><span data-stu-id="4f1ac-123">**Name of the template in Data integration:** Project expense transaction categories (Fin and Ops to PSA)</span></span>
-  <span data-ttu-id="4f1ac-124">**Nombre de la tarea en el proyecto:** categorías sincronizadas a PSA</span><span class="sxs-lookup"><span data-stu-id="4f1ac-124">**Name of the task in the project:** Sync categories to PSA</span></span>

## <a name="entity-set"></a><span data-ttu-id="4f1ac-125">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="4f1ac-125">Entity set</span></span>

| <span data-ttu-id="4f1ac-126">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4f1ac-126">Finance and Operations</span></span>               | <span data-ttu-id="4f1ac-127">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="4f1ac-127">Project Service Automation</span></span>    |
|--------------------------------------|-------------------------------|
| <span data-ttu-id="4f1ac-128">Entidad de integración para categorías</span><span class="sxs-lookup"><span data-stu-id="4f1ac-128">Integration entity for categories</span></span>    | <span data-ttu-id="4f1ac-129">Categorías de transacciones</span><span class="sxs-lookup"><span data-stu-id="4f1ac-129">Transaction categories</span></span>        |

## <a name="entity-flow"></a><span data-ttu-id="4f1ac-130">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="4f1ac-130">Entity flow</span></span>

<span data-ttu-id="4f1ac-131">Las categorías de gastos del proyecto se administran en Finance and Operations y después se sincronizan con Project Service Automation como categorías de transacción.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-131">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span>

## <a name="power-query"></a><span data-ttu-id="4f1ac-132">Power Query</span><span class="sxs-lookup"><span data-stu-id="4f1ac-132">Power Query</span></span>

<span data-ttu-id="4f1ac-133">Debe usar Microsoft Power Query para establecer el tipo de facturación en la categoría de transacción al sincronizar a Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-133">You must use Microsoft Power Query to set the billing type on the transaction category when synchronizing to Project Service Automation.</span></span> <span data-ttu-id="4f1ac-134">La plantilla de las categorías de transacción de gastos del proyecto (Fin and Ops a PSA) tiene una columna predeterminada y una asignación ya proporcionada.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-134">The Project expense transaction categories (Fin and Ops to PSA) template has a default column and mapping already provided.</span></span> <span data-ttu-id="4f1ac-135">Si crea su propia plantilla, debe agregar una columna condicional en Power Query.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-135">If you create your own template, you must add a conditional column in Power Query.</span></span>
- <span data-ttu-id="4f1ac-136">Abra el formulario de consulta avanzada y filtrado desde dentro de la asignación de la tarea de categorías de gastos de proyectos.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-136">Open the Advance Query and Filtering form from within the mapping of project expense categories task.</span></span>
- <span data-ttu-id="4f1ac-137">Seleccione **Agregar columna condicional**.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-137">Select **Add Conditional Column**.</span></span>
- <span data-ttu-id="4f1ac-138">Dé a nueva columna un nombre, como BillingType.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-138">Give the new column a name, such as BillingType.</span></span>
- <span data-ttu-id="4f1ac-139">Especifique la siguiente condición: si **CATEGORYID not equal to null then 19235001, Otherwise null**.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-139">Enter the following condition: if **CATEGORYID not equal to null then 19235001, Otherwise null**.</span></span>
- <span data-ttu-id="4f1ac-140">En la columna, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-140">Click **OK** on the column.</span></span>
- <span data-ttu-id="4f1ac-141">Asegúrese de asignar esta nueva columna en la página de la asignación.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-141">Be sure to map this new column in the mapping page.</span></span>

<span data-ttu-id="4f1ac-142">La siguiente ilustración muestra un ejemplo de la asignación de tarea de plantilla en integración de datos.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-142">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="4f1ac-143">La asignación muestra la información de campo que se sincronizará de Finance and Operations a Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-143">The mapping shows the field information that will be synchronized from Finance and Operations to Project Service Automation.</span></span>

<span data-ttu-id="4f1ac-144">[![Asignación de la plantilla](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="4f1ac-144">[![Template mapping](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span></span>

<span data-ttu-id="4f1ac-145">La plantilla y la tarea subyacente siguientes se usan para sincronizar las categorías de gastos del proyecto desde Project Service Automation hasta Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="4f1ac-145">The following template and underlying task is used to synchronize project expense categories from Project Service Automation to Finance and Operations:</span></span>

<span data-ttu-id="4f1ac-146">-**Nombre de la plantilla en la integración de datos:** Categorías de transacción de gastos del proyecto (de PSA a Fin and Ops) -**Nombre de la tarea en el proyecto:** Sincronización de categorías a Fin and Ops</span><span class="sxs-lookup"><span data-stu-id="4f1ac-146">-**Name of the template in Data integration:** Project expense transaction categories (PSA to Fin and Ops) -**Name of the task in the project:** Sync categories to Fin Ops</span></span>

## <a name="entity-set"></a><span data-ttu-id="4f1ac-147">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="4f1ac-147">Entity set</span></span>

| <span data-ttu-id="4f1ac-148">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="4f1ac-148">Project Service Automation</span></span>      | <span data-ttu-id="4f1ac-149">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4f1ac-149">Finance and Operations</span></span>             |
|---------------------------------|------------------------------------|
| <span data-ttu-id="4f1ac-150">Categorías de transacciones</span><span class="sxs-lookup"><span data-stu-id="4f1ac-150">Transaction categories</span></span>          | <span data-ttu-id="4f1ac-151">Entidad de integración para categorías</span><span class="sxs-lookup"><span data-stu-id="4f1ac-151">Integration entity for categories</span></span>  | 

## <a name="entity-flow"></a><span data-ttu-id="4f1ac-152">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="4f1ac-152">Entity flow</span></span>

<span data-ttu-id="4f1ac-153">Las categorías de gastos del proyecto se administran en Finance and Operations y después se sincronizan con Project Service Automation como categorías de transacción.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-153">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span> <span data-ttu-id="4f1ac-154">La sincronice a Finance and Operations actutaliza el ID de integración desde Project Service Automation en la categoría de proyecto de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-154">The synchronization back to Finance and Operations updates the integration ID from Project Service Automation on the Finance and Operations project category.</span></span>

<span data-ttu-id="4f1ac-155">La siguiente ilustración muestra un ejemplo de la asignación de tarea de plantilla en integración de datos.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-155">The following illustration shows an example of the template task mapping in Data integration.</span></span>

> [!NOTE]
> <span data-ttu-id="4f1ac-156">La asignación muestra la información de campo que se sincronizará de Project Service Automation a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4f1ac-156">The mapping shows the field information that will be synchronized from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="4f1ac-157">[![Asignación de la plantilla](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="4f1ac-157">[![Template mapping](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span></span>

