---
title: Rondas de mantenimiento
description: En este tema se explican las rondas de mantenimiento en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: eca732f245650c8e1f3dc976454536a0ab1ee117
ms.sourcegitcommit: 6476f27c8d3dced7c2e9a7344a4e378b51a1983e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "1922031"
---
# <a name="maintenance-rounds"></a><span data-ttu-id="b9ac3-103">Rondas de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="b9ac3-103">Maintenance rounds</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="b9ac3-104">En **Administración de activos**, puede crear rondas de mantenimiento para varios activos en los que tiene que realizar una tarea similar a intervalos periódicos.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-104">In **Asset Management**, you can create maintenance rounds for various assets, on which you need to carry out a similar task at regular intervals.</span></span> <span data-ttu-id="b9ac3-105">Por ejemplo, los trabajos de lubricación o de inspección de seguridad que tengan que llevarse a cabo en una serie de máquinas dentro de los mismos intervalos.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-105">For example, lubrication jobs or safety inspection jobs that need to be carried out on a number of machines within the same intervals.</span></span> <span data-ttu-id="b9ac3-106">El primer paso consiste en crear una ronda de mantenimiento, incluidos los activos que requieren el mismo formulario de trabajo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-106">First step is to create a maintenance round, including assets that require the same form of maintenance job.</span></span> <span data-ttu-id="b9ac3-107">A continuación, programe las rondas de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-107">Next, you schedule the maintenance rounds.</span></span> <span data-ttu-id="b9ac3-108">Cuando haya completado la programación de rondas de mantenimiento, puede ver todos los registros de trabajo relacionados con la ronda en **Todo el programa de mantenimiento** y en **Líneas del programa de mantenimiento abiertas**.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-108">When you have completed the maintenance rounds schedule, you can see all the job records relating to the round in the **All maintenance schedule** and **Open maintenance schedule lines**.</span></span>

>[!NOTE]
><span data-ttu-id="b9ac3-109">Las rondas de mantenimiento también se pueden configurar en las ubicaciones técnicas que se completarán en los activos instalados en la ubicación técnica en el momento de la creación de la orden de trabajo basada en rondas.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-109">Maintenance rounds can also be set up on functional locations to be completed on the assets installed on the functional location at the time of creation of the round-based work order.</span></span> <span data-ttu-id="b9ac3-110">Consulte [Crear ubicaciones técnicas](../functional-locations/create-functional-locations.md) para obtener más información sobre la configuración de rondas de mantenimiento en ubicaciones técnicas.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-110">Refer to [Create functional locations](../functional-locations/create-functional-locations.md) for more information on the setup of maintenance rounds on functional locations.</span></span>

## <a name="set-up-a-maintenance-round"></a><span data-ttu-id="b9ac3-111">Configurar una ronda de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="b9ac3-111">Set up a maintenance round</span></span>

1. <span data-ttu-id="b9ac3-112">Haga clic en **Administración de activos** > **Configuración** > **Mantenimiento preventivo** > **Rondas de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-112">Click **Asset management** > **Setup** > **Preventive maintenance** > **Maintenance rounds**.</span></span>

2. <span data-ttu-id="b9ac3-113">Haga clic en **Nueva** para crear una nueva ronda de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-113">Click **New** to create a new maintenance round.</span></span>

3. <span data-ttu-id="b9ac3-114">Inserte un id. en el campo **Ronda de mantenimiento** y un nombre para la ronda de mantenimiento en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-114">Insert and ID in the **Maintenance round** field, and a name for the maintenance round in the **Name** field.</span></span>

4. <span data-ttu-id="b9ac3-115">Seleccione una fecha de inicio para la ronda en el campo **Fecha de inicio**.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-115">Select a start date for the round in the **Start date** field.</span></span>

5. <span data-ttu-id="b9ac3-116">En los campos **Finalizar en días** y **Finalizar en horas**, puede insertar la fecha de finalización prevista en días u horas.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-116">In the **Finish within days** and **Finish within hours** fields, you can insert expected end date in days or hours.</span></span> <span data-ttu-id="b9ac3-117">La fecha de finalización prevista se calcula en relación con la fecha de inicio, que se calcula cuando se crean las líneas del programa de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-117">The expected end date is calculated relative to the start date, which is calculated when maintenance schedule lines are created.</span></span> <span data-ttu-id="b9ac3-118">Por ejemplo, puede insertar "7" en el campo **Finalizar en días** para indicar que el trabajo relacionado debe completarse en una semana desde la fecha de inicio.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-118">For example, you can insert "7" in the **Finish within days** field to indicate that the related job should be completed within a week from the start date.</span></span>

6. <span data-ttu-id="b9ac3-119">Seleccione "Sí" en el botón de alternancia **Crear automáticamente** si deben crearse órdenes de trabajo automáticamente a partir de líneas del programa de mantenimiento que se crean desde esta ronda de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-119">Select "Yes" on the **Auto create** toggle button if work orders should automatically be created from maintenance schedule lines that are created from this maintenance round.</span></span>

7. <span data-ttu-id="b9ac3-120">En el campo **Tipo de orden de trabajo**, seleccione el tipo de orden de trabajo que se va a usar en las órdenes de trabajo creadas desde esta ronda de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-120">In the **Work order type** field, select the work order type to be used on work orders created from this maintenance round.</span></span>

8. <span data-ttu-id="b9ac3-121">En el campo **Nivel de servicio**, seleccione el nivel de servicio de la orden de trabajo que se va a usar en las órdenes de trabajo creadas desde esta ronda de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-121">In the **Service level** field, select the work order service level to be used on work orders created from this maintenance round.</span></span>

9. <span data-ttu-id="b9ac3-122">En la ficha desplegable **Líneas de activos**, haga clic en **Agregar** para agregar un activo a la ronda de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-122">On the **Asset lines** FastTab, click **Add** to add an asset to the maintenance round.</span></span>

10. <span data-ttu-id="b9ac3-123">Un número de línea se inserta automáticamente en el campo **Número de línea** para indicar la secuencia de los activos en la ronda de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-123">A line number is automatically inserted in the **Line number** field to indicate the sequence of the assets in maintenance round.</span></span>

11. <span data-ttu-id="b9ac3-124">Seleccione el activo en el campo **Activo**.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-124">Select the asset in the **Asset** field.</span></span>

12. <span data-ttu-id="b9ac3-125">Seleccione el tipo de trabajo de mantenimiento para el activo en el campo **Tipo de trabajo de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-125">Select the maintenance job type for the asset in the **Maintenance job type** field.</span></span>

13. <span data-ttu-id="b9ac3-126">Si es necesario, seleccione la **Variante de tipo de trabajo de mantenimiento** y el **Comercio** relacionados con el tipo de trabajo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-126">If required, select **Maintenance job typ variant** and **Trade** related to the maintenance job type.</span></span>

14. <span data-ttu-id="b9ac3-127">Seleccione la periodicidad (día, semana, etc) en el campo **Tipo de período**.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-127">Select the recurrence (day, week, etc.) in the **Period type** field.</span></span>

15. <span data-ttu-id="b9ac3-128">En el campo **Frecuencia de períodos**, inserte el número de periodicidades para la ronda de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-128">In the **Period frequency** field, insert the number of recurrences for the maintenance round.</span></span> <span data-ttu-id="b9ac3-129">Ejemplo: si ha seleccionado "Día" en el campo **Tipo de periodo** e inserta el número "7" en este campo, se crean nuevas líneas de la ronda de mantenimiento durante la programación de mantenimiento preventivo una vez a la semana.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-129">Example: If you have selected "Day" in the **Period type** field, and you insert the number "7" in this field, new maintenance round lines are created during preventive maintenance scheduling once a week.</span></span>

16. <span data-ttu-id="b9ac3-130">Seleccione una fecha de inicio para el activo que se va a incluir en la ronda de mantenimiento en el campo **Fecha de inicio**.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-130">Select a start date for the asset to be included in the maintenance round in the **Start date** field.</span></span> <span data-ttu-id="b9ac3-131">Esta fecha puede diferir de la fecha de inicio establecida en la ronda de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-131">This date may differ from the start date set on the maintenance round.</span></span>

17. <span data-ttu-id="b9ac3-132">Repita los pasos 9 a 16 para agregar más activos a la ronda de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-132">Repeat steps 9-16 to add more assets to the maintenance round.</span></span>

18. <span data-ttu-id="b9ac3-133">En la ficha desplegable **Líneas de ubicación técnica**, haga clic en **Agregar** para agregar una ubicación técnica a la ronda de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-133">On the **Functional location lines** FastTab, click **Add** to add a functional location to the maintenance round.</span></span> <span data-ttu-id="b9ac3-134">Consulte a continuación la descripción de los campos relacionados.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-134">Refer to the description of the related fields above.</span></span> <span data-ttu-id="b9ac3-135">Están disponibles los mismos campos que para la creación de una línea del activo, pero también puede seleccionar **Fabricante** y **Modelo** para una ubicación técnica, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-135">The same fields are available as for creating an asset line, but you can also select **Manufacturer** and **Model** for a functional location, if required.</span></span> <span data-ttu-id="b9ac3-136">Si selecciona solo una ubicación técnica en una línea, pero no hace ninguna selección en **Tipo de activo**, **Fabricante**, **Modelo**, **Tipo de trabajo de mantenimiento**, **Variante de tipo de trabajo de mantenimiento** y **Comercio**, todos los activos relacionados con esa ubicación técnica en el momento de la programación de mantenimiento se incluirán en la ronda de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-136">If you only select a functional location on a line, but make no selections in **Asset type**, **Manufacturer**, **Model**, **Maintenance job type**, **Maintenance job type variant** and **Trade**, all assets related to that functional location at the time of maintenance scheduling will be included in the maintenance round.</span></span>

19. <span data-ttu-id="b9ac3-137">En la ficha desplegable **Grupos**, haga clic en **Agregar** para seleccionar un grupo de órdenes de trabajo que se van a incluir en la ronda de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-137">On the **Pools** FastTab, click **Add** to select a work order pool to be included in the maintenance round.</span></span> <span data-ttu-id="b9ac3-138">Se pueden conectar varios grupos de órdenes de trabajo a una ronda de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-138">Several work order pools can be connected to one maintenance round.</span></span>

20. <span data-ttu-id="b9ac3-139">Guarde su configuración.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-139">Save your setup.</span></span>

>[!NOTE]
><span data-ttu-id="b9ac3-140">Los campos **Activos** y **Líneas** que se encuentran en el grupo **Detalles** en la ficha desplegable **Encabezado** muestran el número total de activos y líneas relacionados con la ronda de mantenimiento seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-140">The **Assets** and **Lines** fields located in the **Details** group on the **Header** FastTab show the total number of assets and lines related to the selected maintenance round.</span></span>

<span data-ttu-id="b9ac3-141">La ilustración siguiente muestra un ejemplo de una ronda de mantenimiento con tres activos.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-141">The illustration below shows and example of a maintenance round containing three assets.</span></span>

![Figura 1](media/13-preventive-maintenance.png)


## <a name="schedule-maintenance-rounds"></a><span data-ttu-id="b9ac3-143">Programar rondas de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="b9ac3-143">Schedule maintenance rounds</span></span>

<span data-ttu-id="b9ac3-144">Cuando haya configurado una ronda de mantenimiento, ejecute un trabajo de programación para programar todos los trabajos relacionados con la ronda de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-144">When you've set up a maintenance round, you run a schedule job to schedule all the jobs related to the maintenance round.</span></span>

1. <span data-ttu-id="b9ac3-145">Haga clic en **Administración de activos** > **Periódico** > **Mantenimiento preventivo** > **Programar rondas de mantenimiento**, o **Administración de activos** > **Común** > **Programa de mantenimiento** > **Todo el programa de mantenimiento** o **Línea del programa de mantenimiento abiertas** o **Grupos del programa de mantenimiento abiertos** > seleccione una línea del programa de mantenimiento en la lista > botón **Rondas de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-145">Click **Asset management** > **Periodic** > **Preventive maintenance** > **Schedule maintenance rounds**, or **Asset management** > **Common** > **Maintenance schedule** > **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools** > select maintenance schedule line in the list > **Maintenance rounds** button.</span></span>

2. <span data-ttu-id="b9ac3-146">En el campo **Período**, seleccione el tipo de período que se va a utilizar para el trabajo de programación.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-146">In the **Period** field, select the period type to be used for the scheduling job.</span></span>

3. <span data-ttu-id="b9ac3-147">En el campo **Frecuencia de períodos**, inserte el número de períodos que se van a incluir en el trabajo de programación.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-147">In the **Period frequency** field, insert the number of periods to be included in the scheduling job.</span></span> <span data-ttu-id="b9ac3-148">El inicio de la programación es la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-148">The start of the scheduling is the current date.</span></span>

4. <span data-ttu-id="b9ac3-149">Seleccione "Sí" en el botón de alternancia **Crear automáticamente** si una orden de trabajo debe crearse automáticamente en función una ronda de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-149">Select "Yes" on the **Auto create** toggle button if a work order should automatically be created on the basis of a maintenance round.</span></span>

>[!NOTE]
><span data-ttu-id="b9ac3-150">Si tanto este botón de alternancia como el de **Crear automáticamente** se establecen en "Sí" en la ronda de mantenimiento del formulario **Rondas de mantenimiento**, se crean órdenes de trabajo en función de las líneas de la ronda de mantenimiento, así como líneas del programa de mantenimiento con el estado "Orden de trabajo creada".</span><span class="sxs-lookup"><span data-stu-id="b9ac3-150">If this toggle button is set to "Yes", and the **Auto create** toggle button is also set to "Yes" on the maintenance round in **Maintenance rounds** form, work orders are created based on the maintenance round lines, and maintenance schedule lines with status "Work order created" are also created.</span></span> <span data-ttu-id="b9ac3-151">Si se establece en "Sí" solo uno de los botones de alternancia **Crear automáticamente**, en este desplegable o en **Rondas de mantenimiento**, solo se crean las líneas del programa de mantenimiento con el estado "Creada".</span><span class="sxs-lookup"><span data-stu-id="b9ac3-151">If only one of the **Auto create** toggle buttons is set to "Yes", in this drop-down or in **Maintenance rounds**, only maintenance schedule lines are created with status "Created".</span></span> <span data-ttu-id="b9ac3-152">En ese caso, no se crean órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-152">In that case, no work orders are created.</span></span>

5. <span data-ttu-id="b9ac3-153">Si es necesario, puede seleccionar rondas concretas u otra fecha de inicio para el trabajo de programación.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-153">If required, you can select specific rounds or another start date for the schedule job.</span></span> <span data-ttu-id="b9ac3-154">Haga clic en **Filtrar** y agregue las rondas que se van a incluir.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-154">Click **Filter**, and add the rounds to be included.</span></span>

6. <span data-ttu-id="b9ac3-155">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-155">Click **OK**.</span></span>

7. <span data-ttu-id="b9ac3-156">Ahora puede ver los trabajos de las rondas de mantenimiento en **Administración de activos** > **Común** > **Programa de mantenimiento** > **Todo el programa de mantenimiento** o **Líneas del programa de mantenimiento abiertas**.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-156">You are now able to see the maintenance rounds jobs in **Asset management** > **Common** > **Maintenance schedule** > **All maintenance schedule** or **Open maintenance schedule lines**.</span></span> <span data-ttu-id="b9ac3-157">Si las rondas programadas están conectadas a un grupo de órdenes de trabajo, verá las líneas del programa de mantenimiento en **Grupos del programa de mantenimiento abiertos**.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-157">If the scheduled rounds are connected to a work order pool, you also see maintenance schedule lines in **Open maintenance schedule pools**.</span></span> <span data-ttu-id="b9ac3-158">Las líneas del programa de mantenimiento creada desde una ronda tienen el tipo de referencia "Rondas de mantenimiento".</span><span class="sxs-lookup"><span data-stu-id="b9ac3-158">Maintenance schedule lines created from a round have the reference type "Maintenance rounds".</span></span>

<span data-ttu-id="b9ac3-159">Las dos siguientes ilustraciones siguientes muestran un trabajo de programación en el cuadro de diálogo **Rondas de mantenimiento de programación** y las líneas del programa de mantenimiento creadas en **Todo el programa de mantenimiento** basándose en ese trabajo de programación.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-159">The two illustrations below show a schedule job in the **Schedule maintenance rounds** dialog, and the maintenance schedule lines created in **All maintenance schedule** based on that schedule job.</span></span>

![Figura 2](media/14-preventive-maintenance.png)

![Figura 3](media/15-preventive-maintenance.png)

- <span data-ttu-id="b9ac3-162">Cuando se crean órdenes de trabajo manualmente en activos que son cubiertos por la garantía de un proveedor, se muestra un cuadro de diálogo para que el usuario reconozca la garantía.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-162">When work orders are manually created on assets that are covered by a vendor warranty, a dialog box is shown to make the user aware of the warranty.</span></span> <span data-ttu-id="b9ac3-163">La creación de la orden de trabajo se puede cancelar.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-163">The creation of the work order can then be canceled.</span></span> <span data-ttu-id="b9ac3-164">La comprobación de una relación de garantía se omite para órdenes de trabajo que se crean automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-164">The check for a warranty relation is omitted for work orders that are automatically created.</span></span>  
- <span data-ttu-id="b9ac3-165">Puede configurar un trabajo por lotes en la ficha desplegable **Ejecutar en segundo plano** para programar rondas a intervalos periódicos.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-165">You can set up a batch job on the **Run in the background** FastTab to schedule rounds at regular intervals.</span></span>  
- <span data-ttu-id="b9ac3-166">Si una ronda se incluye en varios grupos de órdenes de trabajo (consulte [Grupos de órdenes de trabajo](../work-orders/work-order-pools.md)), se muestra un registro para cada grupo en **Grupos del programa de mantenimiento abiertos**.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-166">If a round is included in several work order pools (refer to [Work order pools](../work-orders/work-order-pools.md)), one record is shown for each pool in **Open maintenance schedule pools**.</span></span> <span data-ttu-id="b9ac3-167">Esto se hace para optimizar las opciones de filtrado para grupos de órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-167">This is done to optimize the filtering options for work order pools.</span></span>

