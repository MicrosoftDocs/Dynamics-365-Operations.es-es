---
title: Programar la creación del trabajo durante la oleada
description: Este tema describe cómo configurar y utilizar el método de programación de procesamiento de oleada de creación de trabajos.
author: perlynne
manager: mirzaab
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 36a450f78695f617056875f8d236fe46bc66aaaf
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "5501231"
---
# <a name="schedule-work-creation-during-wave"></a><span data-ttu-id="5d17e-103">Programar la creación del trabajo durante la oleada</span><span class="sxs-lookup"><span data-stu-id="5d17e-103">Schedule work creation during wave</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="5d17e-104">Use la característica *Programar creación de trabajo* como parte de su proceso de oleada para ayudar a aumentar el rendimiento del procesamiento de oleadas al hacer que el sistema cree trabajo utilizando el procesamiento paralelo.</span><span class="sxs-lookup"><span data-stu-id="5d17e-104">Use the *Schedule work creation* feature as part of your waving process to help increase wave processing throughput by having the system create work using parallel processing.</span></span>

<span data-ttu-id="5d17e-105">Cuando la funcionalidad está habilitada, el trabajo planificado se creará automáticamente y el sistema lo procesará para crear el trabajo real.</span><span class="sxs-lookup"><span data-stu-id="5d17e-105">When the functionality is enabled, planned work will automatically get created, which the system will eventually process to create actual work.</span></span> <span data-ttu-id="5d17e-106">Si el número de líneas de carga de oleada alcanza un umbral predeterminado, el sistema creará trabajo real más rápidamente aplicando el procesamiento asincrónico paralelo.</span><span class="sxs-lookup"><span data-stu-id="5d17e-106">If the number of wave load lines reaches a predetermined threshold, the system will create actual work more quickly by applying parallel, asynchronous processing.</span></span>

## <a name="enable-the-schedule-work-creation-feature"></a><span data-ttu-id="5d17e-107">Habilitar la característica Programar creación de trabajo</span><span class="sxs-lookup"><span data-stu-id="5d17e-107">Enable the Schedule work creation feature</span></span>

### <a name="enable-the-feature-in-feature-management"></a><span data-ttu-id="5d17e-108">Habilitar la característica en la administración de características</span><span class="sxs-lookup"><span data-stu-id="5d17e-108">Enable the feature in feature management</span></span>

<span data-ttu-id="5d17e-109">Antes de poder usar la característica *Programar creación de trabajo* debe estar activada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="5d17e-109">Before you can use the *Schedule work creation* feature, it must be turned on in your system.</span></span> <span data-ttu-id="5d17e-110">Los administradores pueden usar el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="5d17e-110">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="5d17e-111">Allí, la característica se enumera de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="5d17e-111">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="5d17e-112">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="5d17e-112">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="5d17e-113">**Nombre de característica:** *Programar creación de trabajo*</span><span class="sxs-lookup"><span data-stu-id="5d17e-113">**Feature name:** *Schedule work creation*</span></span>

> [!NOTE]
> <span data-ttu-id="5d17e-114">La característica *Bloqueo de trabajo en toda la organización* debe estar habilitada antes de poder habilitar *Programar creación de trabajo*.</span><span class="sxs-lookup"><span data-stu-id="5d17e-114">The *Organization-wide work blocking* feature must be enabled before you can enable *Schedule work creation*.</span></span>

### <a name="manually-enable-batch-processing-of-waves"></a><span data-ttu-id="5d17e-115">Habilite manualmente el procesamiento por lotes de oleadas</span><span class="sxs-lookup"><span data-stu-id="5d17e-115">Manually enable batch processing of waves</span></span>

<span data-ttu-id="5d17e-116">Para aprovechar un método asincrónico paralelo para crear trabajo de almacén, su proceso de oleada debe ejecutarse por lotes.</span><span class="sxs-lookup"><span data-stu-id="5d17e-116">To take advantage of a parallel asynchronous method to create warehouse work, your wave process must be running in batch.</span></span> <span data-ttu-id="5d17e-117">Para configurar:</span><span class="sxs-lookup"><span data-stu-id="5d17e-117">To set this up:</span></span>

1. <span data-ttu-id="5d17e-118">Vaya a  **Gestión de almacenes \> Configurar \> Parámetros de gestión de inventario y almacenes**.</span><span class="sxs-lookup"><span data-stu-id="5d17e-118">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>

1. <span data-ttu-id="5d17e-119">En la pestaña **General**, establezca **Procesar oleadas en lote** a *Sí*.</span><span class="sxs-lookup"><span data-stu-id="5d17e-119">On the **General** tab, set **Process waves in batch** to *Yes*.</span></span> <span data-ttu-id="5d17e-120">Opcionalmente, también puede seleccionar **Grupo de lotes de procesamiento de oleadas** para evitar que el procesamiento de la cola por lotes se ejecute al mismo tiempo que otros procesos.</span><span class="sxs-lookup"><span data-stu-id="5d17e-120">Optionally, you can also select a dedicated **Wave processing batch group** to prevent your batch queue processing from running at the same time as other processes.</span></span>

1. <span data-ttu-id="5d17e-121">Elija la **hora de Esperar bloqueo (ms)**, que se aplica cuando el sistema está procesando varias oleadas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="5d17e-121">Set the **Wait for lock (ms) time**, which applies when the system is processing several waves at the same time.</span></span> <span data-ttu-id="5d17e-122">Para la mayoría de los procesos de creación de oleadas más grandes, recomendamos un valor de *60 000*.</span><span class="sxs-lookup"><span data-stu-id="5d17e-122">For most larger waving processes, we recommend a value of *60000*.</span></span>

### <a name="manually-enable-the-new-wave-step-method-for-existing-wave-templates"></a><span data-ttu-id="5d17e-123">Habilitar manualmente el nuevo método de paso de oleada para plantillas de oleada existentes</span><span class="sxs-lookup"><span data-stu-id="5d17e-123">Manually enable the new wave step method for existing wave templates</span></span>

<span data-ttu-id="5d17e-124">Comience creando el nuevo método de paso de oleada y habilitándolo para el procesamiento de tareas asincrónicas en paralelo.</span><span class="sxs-lookup"><span data-stu-id="5d17e-124">Start by creating the new wave step method and enabling it for parallel asynchronous task processing.</span></span>

1. <span data-ttu-id="5d17e-125">Vaya a  **Gestión de almacenes \> Configuración \> Oleadas \> Métodos de proceso de oleadas**.</span><span class="sxs-lookup"><span data-stu-id="5d17e-125">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>

1. <span data-ttu-id="5d17e-126">Seleccione  **Regenerar métodos** y vea que se ha agregado *WHSScheduleWorkCreationWaveStepMethod* a la lista de métodos de proceso de oleada que puede utilizar en sus plantillas de oleada de envío.</span><span class="sxs-lookup"><span data-stu-id="5d17e-126">Select  **Regenerate method** and note that *WHSScheduleWorkCreationWaveStepMethod* has been added to the list of wave process methods you can use in your shipping wave templates.</span></span>

1. <span data-ttu-id="5d17e-127">Seleccione el registro con el **Nombre del método** *WHSScheduleWorkCreationWaveStepMethod* y seleccione **Configuración de tareas**.</span><span class="sxs-lookup"><span data-stu-id="5d17e-127">Select the record with the **Method name** *WHSScheduleWorkCreationWaveStepMethod* and select **Task configuration**.</span></span>

1. <span data-ttu-id="5d17e-128">Para agregar una nueva fila a la cuadrícula, seleccione **Nuevo** en el panel de acciones y use los siguientes ajustes:</span><span class="sxs-lookup"><span data-stu-id="5d17e-128">To add a new row to the grid, select **New** on the Action Pane and use the following settings:</span></span>

    - <span data-ttu-id="5d17e-129">**Almacén**: seleccione el almacén que utilizará para programar el procesamiento de creación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5d17e-129">**Warehouse** - Select the warehouse you will use to schedule work creation processing.</span></span>

    - <span data-ttu-id="5d17e-130">**Número máximo de tareas por lotes**: especifique un número máximo de tareas por lotes.</span><span class="sxs-lookup"><span data-stu-id="5d17e-130">**Maximum number of batch tasks** - Specify a maximum number of batch tasks.</span></span> <span data-ttu-id="5d17e-131">En la mayoría de los casos, este valor debe estar entre 8 y 16; sin embargo, le recomendamos que experimente con la configuración óptima según sus escenarios.</span><span class="sxs-lookup"><span data-stu-id="5d17e-131">In most cases, this value should be in the range from 8-16, however we recommend that you experiment with the optimal setting based on your scenarios.</span></span>

    - <span data-ttu-id="5d17e-132">**Grupo de lotes de procesamiento de oleadas**: seleccione un grupo de lotes de procesamiento de oleadas dedicado para optimizar el procesamiento de la cola de lotes.</span><span class="sxs-lookup"><span data-stu-id="5d17e-132">**Wave processing batch group** - Select a dedicated wave processing batch group to optimize your batch queue processing.</span></span>

<span data-ttu-id="5d17e-133">Ahora puede actualizar una plantilla de oleada existente (o crear una nueva) para usar el método de procesamiento de oleadas *Programar creación de trabajo*.</span><span class="sxs-lookup"><span data-stu-id="5d17e-133">Now you are ready to update an existing wave template (or create a new one) to use the *Schedule work creation* wave processing method.</span></span>

1. <span data-ttu-id="5d17e-134">Vaya a  **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**.</span><span class="sxs-lookup"><span data-stu-id="5d17e-134">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>

1. <span data-ttu-id="5d17e-135">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5d17e-135">Select **Edit** on the Action Pane.</span></span>

1. <span data-ttu-id="5d17e-136">En el panel de lista, seleccione la plantilla de oleada que le gustaría actualizar (si está probando con datos de demostración, entonces podría usar *Envío predeterminado 24*).</span><span class="sxs-lookup"><span data-stu-id="5d17e-136">In the list pane, select the wave template you would like to update (if you are testing using demo data, then you could use *24 Shipping default*).</span></span>

1. <span data-ttu-id="5d17e-137">Amplíe la ficha desplegable **Métodos** y seleccione la fila con el **Nombre** *Programar creación de trabajo* en la cuadrícula **Métodos restantes**.</span><span class="sxs-lookup"><span data-stu-id="5d17e-137">Expand the **Methods** FastTab and select the row with the **Name** *Schedule work creation* in the **Remaining methods** grid.</span></span>

1. <span data-ttu-id="5d17e-138">Seleccione la flecha que apunta a la columna **Métodos seleccionados** para mover la fila seleccionada a esa columna.</span><span class="sxs-lookup"><span data-stu-id="5d17e-138">Select the arrow pointing to the **Selected methods** column to move the selected row to that column.</span></span> <span data-ttu-id="5d17e-139">(Solo puede seleccionar un método a la vez que utilice *WHSScheduleWorkCreationWaveStepMethod* o *createWork* y así la fila existente con **Nombre del método** *createWork* se mueve automáticamente a la cuadrícula **Métodos restantes**).</span><span class="sxs-lookup"><span data-stu-id="5d17e-139">(You can only have one selected method at a time that uses either *WHSScheduleWorkCreationWaveStepMethod* or *createWork*, so the existing row with **Method name** *createWork* is automatically moved to the **Remaining methods** grid.)</span></span>

## <a name="set-wave-task-processing-threshold-data"></a><span data-ttu-id="5d17e-140">Establecer datos de umbral de procesamiento de tareas de oleadas</span><span class="sxs-lookup"><span data-stu-id="5d17e-140">Set wave task processing threshold data</span></span>

<span data-ttu-id="5d17e-141">El sistema creará datos de umbral de procesamiento de tareas de oleada predeterminados la primera vez que se ejecute un proceso de oleada utilizando cualquier procesamiento basado en tareas.</span><span class="sxs-lookup"><span data-stu-id="5d17e-141">The system will create default wave task processing threshold data the first time a wave process runs using any task-based processing.</span></span> <span data-ttu-id="5d17e-142">Los datos se utilizan para controlar cuándo el procesamiento de oleadas se ejecutará de forma asincrónica y se basará en tareas, lo que le permite procesar y crear trabajo en paralelo.</span><span class="sxs-lookup"><span data-stu-id="5d17e-142">The data is used to control when wave processing will run asynchronously and be task-based, which enables it to process and create work in parallel.</span></span>

<span data-ttu-id="5d17e-143">Los datos predeterminados utilizarán inicialmente un valor de umbral de 15 para el número mínimo de líneas de carga (MINIMUMWAVELOADLINES).</span><span class="sxs-lookup"><span data-stu-id="5d17e-143">The default data will initially use a threshold value of 15 for the minimum number of load lines (MINIMUMWAVELOADLINES).</span></span> <span data-ttu-id="5d17e-144">Esto significa que cuando el sistema procesa una oleada con más de 15 líneas de carga, utilizará el procesamiento de tareas asincrónico.</span><span class="sxs-lookup"><span data-stu-id="5d17e-144">This means that when the system processes a wave with more than 15 loads lines, it will use asynchronous task processing.</span></span> <span data-ttu-id="5d17e-145">Puede insertar o actualizar manualmente estos datos en la tabla **WHSWaveTaskProcessingThresholdParameters** en sus entornos de prueba, pero si necesita cambiar esta configuración en un entorno de producción, debe comunicarse con el Soporte técnico de Microsoft para solicitar la actualización.</span><span class="sxs-lookup"><span data-stu-id="5d17e-145">You can manually insert/update this data in the **WHSWaveTaskProcessingThresholdParameters** table in your test environments, but if you need to change this setting in a production environment, you must contact Microsoft Support to request the update.</span></span>

## <a name="work-with-the-feature"></a><span data-ttu-id="5d17e-146">Trabajar con la característica</span><span class="sxs-lookup"><span data-stu-id="5d17e-146">Work with the feature</span></span>

<span data-ttu-id="5d17e-147">Cuando la función *Programar creación de trabajo* está habilitada, el procesamiento de oleadas creará el trabajo planificado, que al final será utilizado por el proceso de creación de un nuevo trabajo.</span><span class="sxs-lookup"><span data-stu-id="5d17e-147">When the *Schedule work creation* functionality is enabled, wave processing will create planned work, which will eventually be used by the new work creation process.</span></span> <span data-ttu-id="5d17e-148">Durante la creación del trabajo, este se bloqueará mediante la característica *Bloqueo de trabajo en toda la organización*.</span><span class="sxs-lookup"><span data-stu-id="5d17e-148">During work creation, the work will be blocked using the *Organization-wide work blocking* feature.</span></span>

<span data-ttu-id="5d17e-149">El siguiente diagrama de flujo muestra cómo se crea el trabajo planificado durante el procesamiento de oleadas.</span><span class="sxs-lookup"><span data-stu-id="5d17e-149">The following flowchart shows how planned work is created during wave processing.</span></span>

![Programar la creación del trabajo](media/schedule-work-creation-process.png)

### <a name="planned-work"></a><span data-ttu-id="5d17e-151">Trabajo planificado</span><span class="sxs-lookup"><span data-stu-id="5d17e-151">Planned work</span></span>

<span data-ttu-id="5d17e-152">La página **Detalles del trabajo planificado** (**Gestión de almacenes \> Trabajo \> Detalles del trabajo planificado**) muestra información sobre el trabajo planificado, que se crea inicialmente durante el procesamiento de oleadas.</span><span class="sxs-lookup"><span data-stu-id="5d17e-152">The **Planned work details** page (**Warehouse management \> Work \> Planned work details**) shows information about the planned work, which is initially created during wave processing.</span></span> <span data-ttu-id="5d17e-153">Están disponibles los siguientes valores de **Estado de progreso**:</span><span class="sxs-lookup"><span data-stu-id="5d17e-153">The following **Process status** values are available:</span></span>

- <span data-ttu-id="5d17e-154">**Puesto en cola**: El trabajo planificado está a la espera de ser utilizada para crear trabajo.</span><span class="sxs-lookup"><span data-stu-id="5d17e-154">**Queued** - The planned work is waiting to be used to create work.</span></span>
- <span data-ttu-id="5d17e-155">**Completado**: el trabajo planificado se ha utilizado para crear trabajo.</span><span class="sxs-lookup"><span data-stu-id="5d17e-155">**Completed** - The planned work has been used to create work.</span></span>
- <span data-ttu-id="5d17e-156">**Error**: el procesamiento de la oleada ha fallado.</span><span class="sxs-lookup"><span data-stu-id="5d17e-156">**Failed** – The wave processing has failed.</span></span> <span data-ttu-id="5d17e-157">Tenga en cuenta que el trabajo planificado puede estar en estado de **Error** con o sin trabajo real relacionado.</span><span class="sxs-lookup"><span data-stu-id="5d17e-157">Note that the planned work can be in a **Failed** state with or without related actual work.</span></span> <span data-ttu-id="5d17e-158">Cuando falla el proceso de creación del trabajo real, el trabajo real permanece en estado *Cancelado*.</span><span class="sxs-lookup"><span data-stu-id="5d17e-158">When the actual work creation process fails, the actual work remains in status *Cancelled*.</span></span>

### <a name="batch-job-for-the-work-creation-process"></a><span data-ttu-id="5d17e-159">Trabajo por lotes para el proceso de creación de trabajo</span><span class="sxs-lookup"><span data-stu-id="5d17e-159">Batch job for the work creation process</span></span>

<span data-ttu-id="5d17e-160">Para ver los trabajos por lotes para procesar oleadas, seleccione **Trabajos por lotes** en el panel de Acción en la página **Todas las oleadas**.</span><span class="sxs-lookup"><span data-stu-id="5d17e-160">To view the batch jobs for processing waves, select **Batch jobs** on the Action Pane on the **All waves** page.</span></span>

<span data-ttu-id="5d17e-161">Desde aquí, puede ver todos los detalles de la tarea por lotes para cada uno de los Id. de trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="5d17e-161">From here, you can view all the batch task details for each of the batch job IDs.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]