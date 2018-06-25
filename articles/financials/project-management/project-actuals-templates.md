---
title: "Permite sincronizar los valores reales del Project Service Automation directamente al diario de integración del proyecto para el registro en Finance and Operations"
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar directamente los valores reales de Microsoft Dynamics 365 for Project Service Automation a Dynamics 365 for Finance and Operations.
author: KimANelson
manager: AnnBe
ms.date: 05/21/2018
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
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 85ff049852e0b00623f47a12fb66e2c9bb9c4151
ms.contentlocale: es-es
ms.lasthandoff: 05/29/2018

---
# <a name="synchronize-project-actuals-from-project-service-automation-directly-to-the-project-integration-journal-for-posting-in-finance-and-operations"></a><span data-ttu-id="0a252-103">Permite sincronizar los valores reales del Project Service Automation directamente al diario de integración del proyecto para el registro en Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0a252-103">Synchronize project actuals from Project Service Automation directly to the project integration journal for posting in Finance and Operations</span></span>

<span data-ttu-id="0a252-104">En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar directamente los valores reales de Microsoft Dynamics 365 for Project Service Automation a Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0a252-104">This topic describes the templates and underlying tasks that are used to synchronize project actuals directly from Microsoft Dynamics 365 for Project Service Automation to Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="0a252-105">Las transacciones de sincronización de plantillas de Project Service Automation a una tabla de ensayo en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0a252-105">The template syncs transactions from Project Service Automation into a staging table in Finance and Operations.</span></span> <span data-ttu-id="0a252-106">Una vez completada la sincronización, debe importar desde la tabla de ensayo al diario de integración.</span><span class="sxs-lookup"><span data-stu-id="0a252-106">After synchronization is complete, you must import from the staging table to the integration journal.</span></span>

> [!NOTE]
> <span data-ttu-id="0a252-107">La integración de los valores reales del proyecto está disponible en Dynamics 365 para Finance and Operations versión 8.01.</span><span class="sxs-lookup"><span data-stu-id="0a252-107">Project actuals integration is available in Dynamics 365 for Finance and Operations version 8.01.</span></span>

> [!NOTE]
> <span data-ttu-id="0a252-108">Si especifica importes de impuestos a tiempo o las transacciones de gastos en Project Service Automation, debe instalar la actualización 7 de Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="0a252-108">If you are entering sales tax amounts on time or expense transactions in Project Service Automation, you must install the Project Service Automation Update 7.</span></span> <span data-ttu-id="0a252-109">Si esta actualización no está instalada, los valores reales de impuestos no se vincularán a los valores reales asociados al tiempo o a los gastos y no se sincronizarán con Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0a252-109">If this update is not installed, the tax actuals will not be linked to the associated time or expense actuals and will not be synced to Finance and Operations.</span></span> <span data-ttu-id="0a252-110">Póngase en contacto con el servicio de atención al cliente para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0a252-110">Contact Support for more information.</span></span>


## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="0a252-111">Flujo de datos de Project Service Automation a Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0a252-111">Data flow for Project Service Automation to Finance and Operations</span></span>

<span data-ttu-id="0a252-112">La integración de Project Service Automation con Finance and Operations usa la característica de integración de datos para sincronizar datos a través de las instancias de Project Service Automation y de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0a252-112">The Project Service Automation to Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance and Operations.</span></span> <span data-ttu-id="0a252-113">Las plantillas de integración disponibles con la función de integración de datos habilitan el flujo de datos sobre los valores reales de proyecto desde Project Service Automation a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0a252-113">The integration templates that are available with the Data integration feature enable the flow of data about project actuals from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="0a252-114">La ilustración siguiente muestra cómo se sincronizan los datos entre Project Service Automation y Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0a252-114">The following illustration shows how the data is synchronized between Project Service Automation and Finance and Operations.</span></span>

<span data-ttu-id="0a252-115">[![Flujo de datos para la integración de Project Service Automation con Finance and Operations](./media/ProjectActualsFlow.jpg)](./media/ProjectActualsFlow.jpg)</span><span class="sxs-lookup"><span data-stu-id="0a252-115">[![Data flow for Project Service Automation integration with Finance and Operations](./media/ProjectActualsFlow.jpg)](./media/ProjectActualsFlow.jpg)</span></span>


## <a name="templates-and-tasks"></a><span data-ttu-id="0a252-116">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="0a252-116">Templates and tasks</span></span>

<span data-ttu-id="0a252-117">Para obtener acceso a las plantillas disponibles, en el centro de administración de Microsoft PowerApps, seleccione **Proyectos**y, a continuación, en la esquina superior derecha, seleccione **Nuevo proyecto** para seleccionar plantillas públicas.</span><span class="sxs-lookup"><span data-stu-id="0a252-117">To access the available templates, in the Microsoft PowerApps Admin Center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="0a252-118">La plantilla y las tareas subyacentes siguientes se usan para sincronizar los valores reales desde Project Service Automation hasta Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="0a252-118">The following template and underlying tasks are used to synchronize project actuals from Project Service Automation to Finance and Operations:</span></span>

-  <span data-ttu-id="0a252-119">**Nombre de la plantilla en la integración de datos:** valores reales del proyecto (PSA a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="0a252-119">**Name of the template in Data integration:** Project actuals (PSA to Fin and Ops)</span></span>

-  <span data-ttu-id="0a252-120">**Nombre de las tareas en el proyecto:**</span><span class="sxs-lookup"><span data-stu-id="0a252-120">**Name of the tasks in the project:**</span></span> 
    - <span data-ttu-id="0a252-121">Reales</span><span class="sxs-lookup"><span data-stu-id="0a252-121">Actuals</span></span> 
    - <span data-ttu-id="0a252-122">TransactionConnections</span><span class="sxs-lookup"><span data-stu-id="0a252-122">TransactionConnections</span></span>

## <a name="entity-set"></a><span data-ttu-id="0a252-123">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="0a252-123">Entity set</span></span>

| <span data-ttu-id="0a252-124">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="0a252-124">Project Service Automation</span></span>      | <span data-ttu-id="0a252-125">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0a252-125">Finance and Operations</span></span>                                      |
|---------------------------------|-------------------------------------------------------------|
| <span data-ttu-id="0a252-126">Reales</span><span class="sxs-lookup"><span data-stu-id="0a252-126">Actuals</span></span>                         | <span data-ttu-id="0a252-127">Entidad de integración para valores reales de proyecto</span><span class="sxs-lookup"><span data-stu-id="0a252-127">Integration entity for project actuals</span></span>                      |
| <span data-ttu-id="0a252-128">Conexiones de transacción</span><span class="sxs-lookup"><span data-stu-id="0a252-128">Transaction Connections</span></span>         | <span data-ttu-id="0a252-129">Entidad de integración para relaciones de transacción de proyecto</span><span class="sxs-lookup"><span data-stu-id="0a252-129">Integration entity for project transaction relationships</span></span>    |

## <a name="entity-flow"></a><span data-ttu-id="0a252-130">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="0a252-130">Entity flow</span></span>

<span data-ttu-id="0a252-131">Los valores reales del proyecto se administran en Project Service Automation y se sincronizan con Finance and Operations en el diario de integración del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0a252-131">Project actuals are managed in Project Service Automation, and they are synchronized to Finance and Operations to the project ingetration journal.</span></span> <span data-ttu-id="0a252-132">Las contabilidad se aplicará según dimensiones financieras predeterminadas y la configuración de registro.</span><span class="sxs-lookup"><span data-stu-id="0a252-132">The accounting will be applied based on default financial dimensions and posting setup.</span></span>

## <a name="preconditions"></a><span data-ttu-id="0a252-133">Condiciones previas</span><span class="sxs-lookup"><span data-stu-id="0a252-133">Preconditions</span></span>

<span data-ttu-id="0a252-134">Antes de que la sincronización de valores reales pueda producirse, debe configurar los parámetros de integración de Project Service Automation y sincronizar proyectos, tareas de proyecto y categorías de transacción de gastos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0a252-134">Before synchronization of actuals can occur, you must configure the Project Service Automation integration parameters and synchronize projects, project tasks, and project expense transaction categories.</span></span>

## <a name="power-query"></a><span data-ttu-id="0a252-135">Power Query</span><span class="sxs-lookup"><span data-stu-id="0a252-135">Power Query</span></span>

<span data-ttu-id="0a252-136">Debe usar Microsoft Power Query en la plantilla de los valores reales de proyecto para:</span><span class="sxs-lookup"><span data-stu-id="0a252-136">You must use Microsoft Power Query in the project actuals template to:</span></span>
- <span data-ttu-id="0a252-137">Transformar el **tipo de transacción** de Project Service Automation en el **tipo de transacción** correcto de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0a252-137">Transform the Project Service Automation **transaction type** to the correct **transaction type** in Finance and Operations.</span></span> <span data-ttu-id="0a252-138">La plantilla de valores reales de proyecto (PSA a Fin and Ops) tiene esta transformación definida.</span><span class="sxs-lookup"><span data-stu-id="0a252-138">The Project actuals (PSA to Fin and Ops) template already has this transformation defined.</span></span>
- <span data-ttu-id="0a252-139">Transformar el **tipo de facturación** de Project Service Automation en el **tipo de facturación** correcto de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0a252-139">Transform the Project Service Automation **billing type** to the correct **billing type** in Finance and Operations.</span></span> <span data-ttu-id="0a252-140">La plantilla de valores reales de proyecto (PSA a Fin and Ops) tiene esta transformación definida.</span><span class="sxs-lookup"><span data-stu-id="0a252-140">The Project actuals (PSA to Fin and Ops) template already has this transformation defined.</span></span> <span data-ttu-id="0a252-141">El tipo de facturación se asigna a la **propiedad de línea** basándose en la configuración indicada en el formulario de integración de Dynamics 365 for Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="0a252-141">The billing type is then mapped to the **line property** based on the configuration in the Dynamics 365 for Project Service Automation integration parameters form.</span></span>
- <span data-ttu-id="0a252-142">Filtrar en **Unidades organizativas de recursos** determinadas que deben sincronizarse con esta plantilla.</span><span class="sxs-lookup"><span data-stu-id="0a252-142">Filter to specific **Resource organizational units** that are to be synced with this template.</span></span>
- <span data-ttu-id="0a252-143">Si **los valores reales de gastos de empresas vinculadas o de tiempo de empresas vinculadas** se van a sincronizar con Finance and Operations, debe transformar la **unidad organizativa del contrato** en la **entidad jurídica** correcta en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0a252-143">If **intercompany time or intercompany expense actuals** will be synced to Finance and Operations, you must transform the **contract organizational unit** to the correct **legal entity** in Finance and Operations.</span></span> <span data-ttu-id="0a252-144">La plantilla de los valores reales del proyecto (PSA a Fin and Ops) tiene una columna condicional definida basada en datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="0a252-144">The Project actuals (PSA to Fin and Ops) template has a conditional column defined based on demo data.</span></span> <span data-ttu-id="0a252-145">Debe actualizar la columna insertada en último lugar con las entidades jurídicas correctas.</span><span class="sxs-lookup"><span data-stu-id="0a252-145">You must update the last inserted condition column to the correct legal entities.</span></span> <span data-ttu-id="0a252-146">Si no lo hace puede provocar un error de integración o que se importen transacciones reales incorrectas a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0a252-146">Failure to do this may result in either an integration error or incorrect actual transactions imported into Finance and Operations.</span></span>
- <span data-ttu-id="0a252-147">Si **los valores reales de tiempo de empresas vinculadas o de gastos de empresas vinculadas** no se sincroniza con Finance and Operations, debe eliminar de la plantilla la columna de condición insertada en último lugar.</span><span class="sxs-lookup"><span data-stu-id="0a252-147">If **intercompany time or intercompany expense actuals** will not be synced to Finance and operations, you must delete the last inserted condition column from your template.</span></span> <span data-ttu-id="0a252-148">Si no lo hace puede provocar un error de integración o que se importen transacciones reales incorrectas a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0a252-148">Failure to do this may result in either an integration error or incorrect actual transactions imported into Finance and Operations.</span></span>

### <a name="contract-organizational-unit"></a><span data-ttu-id="0a252-149">Unidad organizativa de contrato</span><span class="sxs-lookup"><span data-stu-id="0a252-149">Contract Organizational Unit</span></span>
<span data-ttu-id="0a252-150">Para actualizar la columna de condición insertada en la plantilla, haga clic en la flecha **Mapa** para abrir la asignación.</span><span class="sxs-lookup"><span data-stu-id="0a252-150">To update the inserted condition column in the template, click the **Map** arrow to open the mapping.</span></span> <span data-ttu-id="0a252-151">Seleccione para abrir la consulta y el filtrado avanzados.</span><span class="sxs-lookup"><span data-stu-id="0a252-151">Select to open the Advanced Query and Filtering.</span></span>
- <span data-ttu-id="0a252-152">Si utiliza los valores reales predeterminados de Microsoft Project (PSA a Fin and Ops), seleccione la última **Condición insertada** en la sección **Pasos aplicados**.</span><span class="sxs-lookup"><span data-stu-id="0a252-152">If you are using the default Microsoft Project actuals (PSA to Fin and Ops) template, select the lasat **Inserted Condition** in the **Applied Steps** section.</span></span> <span data-ttu-id="0a252-153">En la entrada **Función**, reemplace **USSI** con el nombre de la **Entidad jurídica** que se debe usar con la integración.</span><span class="sxs-lookup"><span data-stu-id="0a252-153">In the **Function** entry, replace **USSI** with the name of the **Legal entity** that should be used with the integration.</span></span> <span data-ttu-id="0a252-154">Agregue condiciones adicionales según las necesidades a la entrada **Función** y actualice la condición **else** de **USMF** por la **Entidad jurídica** correcta.</span><span class="sxs-lookup"><span data-stu-id="0a252-154">Add additional conditions as needed to the **Function** entry and update the **else** condition from **USMF** to the correct **Legal entity**.</span></span>
- <span data-ttu-id="0a252-155">Si crea una nueva plantilla, debe agregar esta columna para dar soporte a los gatos y el tiempo de las empresas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="0a252-155">If you are creating a new template, you must add this column to support intercompany time and expenses.</span></span> <span data-ttu-id="0a252-156">Seleccione **Agregar columna condicional** y dé a la columna un nombre, como LegalEntity.</span><span class="sxs-lookup"><span data-stu-id="0a252-156">Select **Add Conditional Column** and give the column a name, such as LegalEntity.</span></span> <span data-ttu-id="0a252-157">Especifique la condición para la columna donde si es msdyn_contractorganizationalunitid.msdyn_name es <organizational unit>, entonces <enter the Legal entity> es nulo.</span><span class="sxs-lookup"><span data-stu-id="0a252-157">Enter the condition for the column where if msdyn_contractorganizationalunitid.msdyn_name is <organizational unit>, then <enter the Legal entity>; else null.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="0a252-158">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="0a252-158">Template mapping in Data integration</span></span>

<span data-ttu-id="0a252-159">La siguiente ilustración muestra un ejemplo de la asignación de tarea de plantilla en integración de datos.</span><span class="sxs-lookup"><span data-stu-id="0a252-159">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="0a252-160">La asignación muestra la información de campo que se sincronizará de Project Service Automation a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0a252-160">The mapping shows the field information that will be synchronized from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="0a252-161">[![Asignación de la plantilla](./media/ActualsMapping.jpg)](./media/ActualsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="0a252-161">[![Template mapping](./media/ActualsMapping.jpg)](./media/ActualsMapping.jpg)</span></span>

<span data-ttu-id="0a252-162">[![Asignación de la plantilla](./media/TransactionConnections.jpg)](./media/TransactionConnections.jpg)</span><span class="sxs-lookup"><span data-stu-id="0a252-162">[![Template mapping](./media/TransactionConnections.jpg)](./media/TransactionConnections.jpg)</span></span>

## <a name="import-from-staging-table"></a><span data-ttu-id="0a252-163">Importar desde tabla de almacenamiento provisional</span><span class="sxs-lookup"><span data-stu-id="0a252-163">Import from staging table</span></span>

<span data-ttu-id="0a252-164">El proceso de importación del proceso periódico de la tabla de prueba se debe ejecutar después de la sincronización de los valores reales desde Project Service Automation a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0a252-164">The Import from staging table perioidic process must be run after the sychronization of actuals from Project Service Automation to Finance and Operations.</span></span> <span data-ttu-id="0a252-165">Este proceso importará las transacciones de proyecto de la tabla de ensayo al diario de integración de Project Service Automation, donde se aplica la contabilidad y se pueden registrar las transacciones importadas.</span><span class="sxs-lookup"><span data-stu-id="0a252-165">This process will import the project transactions from the staging table into the Project Service Automation integration journal, where the accounting is applied and the imported transactions can be posted.</span></span> <span data-ttu-id="0a252-166">Se recomienda que ejecute este proceso en modo de lotes y se puede configurar opcionalmente para ejecutarlo como lote periódico.</span><span class="sxs-lookup"><span data-stu-id="0a252-166">It is recommended that you run this process in batch mode and optionally can be set up to run as a recurring batch.</span></span>

## <a name="update-actuals"></a><span data-ttu-id="0a252-167">Actualización de valores reales</span><span class="sxs-lookup"><span data-stu-id="0a252-167">Update Actuals</span></span>

<span data-ttu-id="0a252-168">La plantilla y las tareas subyacentes siguientes se usan para sincronizar el número de asiento y los impuestos de las transacciones de proyecto registradas desde Finance and Operations hasta Project Service Automation:</span><span class="sxs-lookup"><span data-stu-id="0a252-168">The following template and underlying tasks are used to synchronize the voucher number and sales taxes for posted project transactions from Finance and Operations to Project Service Automation:</span></span>

-  <span data-ttu-id="0a252-169">**Nombre de la plantilla en la integración de datos:** actualización de los valores reales del proyecto (de Fin Ops a PSA)</span><span class="sxs-lookup"><span data-stu-id="0a252-169">**Name of the template in Data integration:** Project actuals update (Fin Ops to PSA)</span></span>
-  <span data-ttu-id="0a252-170">**Nombre de las tareas en el proyecto:**</span><span class="sxs-lookup"><span data-stu-id="0a252-170">**Name of the tasks in the project:**</span></span> 
     - <span data-ttu-id="0a252-171">Reales</span><span class="sxs-lookup"><span data-stu-id="0a252-171">Actuals</span></span> 
     - <span data-ttu-id="0a252-172">TransactionConnections</span><span class="sxs-lookup"><span data-stu-id="0a252-172">TransactionConnections</span></span>

## <a name="entity-set"></a><span data-ttu-id="0a252-173">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="0a252-173">Entity set</span></span>

| <span data-ttu-id="0a252-174">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0a252-174">Finance and Operations</span></span>                                         | <span data-ttu-id="0a252-175">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="0a252-175">Project Service Automation</span></span>        |
|----------------------------------------------------------------|-----------------------------------|
| <span data-ttu-id="0a252-176">Entidad de integración para valores reales de proyecto</span><span class="sxs-lookup"><span data-stu-id="0a252-176">Integration entity for project actuals</span></span>                         | <span data-ttu-id="0a252-177">Reales</span><span class="sxs-lookup"><span data-stu-id="0a252-177">Actuals</span></span>                           |
| <span data-ttu-id="0a252-178">Entidad de integración para relaciones de transacción de proyecto</span><span class="sxs-lookup"><span data-stu-id="0a252-178">Integration entity for project transaction relationships</span></span>       | <span data-ttu-id="0a252-179">Conexiones de transacción</span><span class="sxs-lookup"><span data-stu-id="0a252-179">Transaction Connections</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="0a252-180">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="0a252-180">Entity flow</span></span>

<span data-ttu-id="0a252-181">Los valores reales del proyecto se administran en Project Service Automation y se sincronizan con Finance and Operations en el diario de integración del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0a252-181">Project actuals are managed in Project Service Automation, and they are synchronized to Finance and Operations to the project integration journal.</span></span> <span data-ttu-id="0a252-182">Una vez contabilizados en Finance and Operations, los valores reales se actualizan en Project Service Automation con el número de asiento de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0a252-182">Once posted in Finance and Operations, actuals are updated in Project Service Automation with the voucher number from Finance and Operations.</span></span> <span data-ttu-id="0a252-183">Si los impuestos se han agregado en Finance and Operations, los nuevos valores reales se crearán en Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="0a252-183">If sales taxes were added in Finance and Operations, new tax actuals will be created in PRoject Service Automation.</span></span>

## <a name="power-query"></a><span data-ttu-id="0a252-184">Power Query</span><span class="sxs-lookup"><span data-stu-id="0a252-184">Power Query</span></span>

<span data-ttu-id="0a252-185">Debe usar Microsoft Power Query en la plantilla de actualización de los valores reales de proyecto para:</span><span class="sxs-lookup"><span data-stu-id="0a252-185">You must use Microsoft Power Query in the project actuals update template to:</span></span>
- <span data-ttu-id="0a252-186">Transformar el **tipo de transacción** de Finance and Operations al **tipo de transacción** correcto de Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="0a252-186">Transform the Finance and Operations **transaction type** to the correct **transaction type** in Project Service Automation.</span></span> <span data-ttu-id="0a252-187">La actualización de valores reales de proyecto (de Fin Ops a PSA) ya tiene esta transformación definida.</span><span class="sxs-lookup"><span data-stu-id="0a252-187">The Project actuals update (Fin Ops to PSA) template already has this transformation defined.</span></span>
- <span data-ttu-id="0a252-188">Transformar el **tipo de facturación** de Finance and Operations en el **tipo de facturación** correcto en Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="0a252-188">Transform the Finance and Operations **billing type** to the correct **billing type** in Project Service Automation.</span></span> <span data-ttu-id="0a252-189">La actualización de valores reales de proyecto (de Fin Ops a PSA) ya tiene esta transformación definida.</span><span class="sxs-lookup"><span data-stu-id="0a252-189">The Project actuals update (Fin Ops to PSA) template already has this transformation defined.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="0a252-190">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="0a252-190">Template mapping in Data integration</span></span>

<span data-ttu-id="0a252-191">Las siguientes ilustraciones muestran ejemplos de asignaciones de tareas de plantillas en la integración de datos.</span><span class="sxs-lookup"><span data-stu-id="0a252-191">The following illustrations show examples of the template task mappings in Data integration.</span></span> <span data-ttu-id="0a252-192">La asignación muestra la información de campo que se sincronizará de Finance and Operations a Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="0a252-192">The mapping shows the field information that will be synchronized from Finance and Operations to Project Service Automation.</span></span>

<span data-ttu-id="0a252-193">[![Asignación de la plantilla](./media/ActualsUpdateMapping.jpg)](./media/ActualsUpdateMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="0a252-193">[![Template mapping](./media/ActualsUpdateMapping.jpg)](./media/ActualsUpdateMapping.jpg)</span></span>

<span data-ttu-id="0a252-194">[![Asignación de la plantilla](./media/TransactionConnectionsUpdate.jpg)](./media/TransactionConnectionsUpdate.jpg)</span><span class="sxs-lookup"><span data-stu-id="0a252-194">[![Template mapping](./media/TransactionConnectionsUpdate.jpg)](./media/TransactionConnectionsUpdate.jpg)</span></span>



