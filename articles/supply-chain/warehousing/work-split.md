---
title: División del trabajo
description: Este tema proporciona información sobre la funcionalidad de división de trabajo. Esta funcionalidad le permite dividir órdenes de trabajo grandes en varias órdenes de trabajo más pequeñas que luego puede asignar a varios trabajadores del almacén. De esta forma, el mismo trabajo puede ser recogido simultáneamente por varios trabajadores del almacén.
author: mirzaab
manager: tfehr
ms.date: 10/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: WHSWorkTableListPage
ms.author: mirzaab
ms.search.validFrom: 2020-10-15
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 6dbf0f6dd0c691db74eaad2174d8f9849b4cb26a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5245091"
---
# <a name="work-split"></a><span data-ttu-id="09ba6-105">División del trabajo</span><span class="sxs-lookup"><span data-stu-id="09ba6-105">Work split</span></span>

<span data-ttu-id="09ba6-106">La funcionalidad de división del trabajo le permite dividir las ID de trabajo grandes (es decir, las órdenes de trabajo que tienen varias líneas) en varias ID de trabajo más pequeñas que luego puede asignar a varios trabajadores del almacén.</span><span class="sxs-lookup"><span data-stu-id="09ba6-106">Work split functionality lets you split large work IDs (that is, work orders that have several lines) into several smaller work IDs that you can then assign to multiple warehouse workers.</span></span> <span data-ttu-id="09ba6-107">De esta forma, el mismo número de creación de trabajo puede ser recogido simultáneamente por varios trabajadores del almacén.</span><span class="sxs-lookup"><span data-stu-id="09ba6-107">In this way, the same work creation number can be picked simultaneously by several warehouse workers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="09ba6-108">Solo puede dividir las órdenes de trabajo que tienen un estado *Abierto* o *En progreso*.</span><span class="sxs-lookup"><span data-stu-id="09ba6-108">You can split only work orders that have a status of *Open* or *In-progress*.</span></span>

## <a name="turn-on-the-work-split-functionality"></a><span data-ttu-id="09ba6-109">Activar la función de división del trabajo</span><span class="sxs-lookup"><span data-stu-id="09ba6-109">Turn on the work split functionality</span></span>

<span data-ttu-id="09ba6-110">Antes de poder utilizar la función de división del trabajo, debe activar la función y su función de requisito previo en su sistema.</span><span class="sxs-lookup"><span data-stu-id="09ba6-110">Before you can use the work split functionality, you must turn on the feature and its prerequisite feature in your system.</span></span> <span data-ttu-id="09ba6-111">Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de las funciones y activarlas si es necesario.</span><span class="sxs-lookup"><span data-stu-id="09ba6-111">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the features and turn them on as required.</span></span>

<span data-ttu-id="09ba6-112">Primero, active el requisito previo de la función *Bloqueo de trabajo en toda la organización*, si aún no está activada.</span><span class="sxs-lookup"><span data-stu-id="09ba6-112">First, turn on the prerequisite *Organization-wide work blocking* feature if it isn't already turned on.</span></span> <span data-ttu-id="09ba6-113">En el espacio de trabajo **Administración de características**, esta característica aparece de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="09ba6-113">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="09ba6-114">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="09ba6-114">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="09ba6-115">**Nombre de la característica:** *Bloqueo de trabajo en toda la organización*</span><span class="sxs-lookup"><span data-stu-id="09ba6-115">**Feature name:** *Organization-wide work blocking*</span></span>

> [!NOTE]
> <span data-ttu-id="09ba6-116">Cuando esta función está activada, una actualización de datos se aplica automáticamente después de que la función se activa en todas las entidades legales.</span><span class="sxs-lookup"><span data-stu-id="09ba6-116">When this feature is activated, a data upgrade is automatically applied after the feature is turned on across all legal entities.</span></span>

<span data-ttu-id="09ba6-117">A continuación, active la característica *Trabajo dividido*, que se enumera de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="09ba6-117">Next, turn on the *Work split* feature, which is listed in the following way:</span></span>

- <span data-ttu-id="09ba6-118">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="09ba6-118">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="09ba6-119">**Nombre de la función:** *Trabajo dividido*</span><span class="sxs-lookup"><span data-stu-id="09ba6-119">**Feature name:** *Work split*</span></span>

## <a name="enhancements-to-the-work-details-and-all-work-pages"></a><span data-ttu-id="09ba6-120">Mejoras en los detalles del trabajo y todas las páginas de trabajo</span><span class="sxs-lookup"><span data-stu-id="09ba6-120">Enhancements to the Work details and All work pages</span></span>

<span data-ttu-id="09ba6-121">La función *Trabajo dividido* añade los siguientes dos botones a la pestña **Trabajo** en el Panel de acciones de las páginas **Detalles del trabajo** y **Todo el trabajo**:</span><span class="sxs-lookup"><span data-stu-id="09ba6-121">The *Work split* feature adds the following two buttons to the **Work** tab on the Action Pane of the **Work details** and **All work** pages:</span></span>

- <span data-ttu-id="09ba6-122">**Dividir trabajo** – Dividir el identificador de trabajo actual en varios Id. más pequeños de trabajo para que se puedan procesar por trabajadores independientes.</span><span class="sxs-lookup"><span data-stu-id="09ba6-122">**Split work** – Split the current work ID into multiple smaller work IDs that can be processed by separate workers.</span></span>
- <span data-ttu-id="09ba6-123">**Cancelar sesión de trabajo dividido** - Cancelar la sesión de trabajo dividido y hacer que el trabajo esté disponible para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="09ba6-123">**Cancel work split session** – Cancel the work split session, and make the work available for processing.</span></span>

<span data-ttu-id="09ba6-124">![Botones dividir trabajo y cancelar trabajo dividido sesión](media/Work_split_buttons.png "Botones dividir trabajo y cancelar trabajo dividido sesión")</span><span class="sxs-lookup"><span data-stu-id="09ba6-124">![Split work and Cancel work split session buttons](media/Work_split_buttons.png "Split work and Cancel work split session buttons")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="09ba6-125">El botón **Trabajo dividido** no estará disponible si se cumple alguna de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="09ba6-125">The **Split work** button won't be available if any of the following conditions are met:</span></span>
>
> - <span data-ttu-id="09ba6-126">El estado del trabajo es algo diferente a *Abierto* o *En progreso*.</span><span class="sxs-lookup"><span data-stu-id="09ba6-126">The work status is something other than *Open* or *In progress*.</span></span>
> - <span data-ttu-id="09ba6-127">Un ID de contenedor está asociado con el ID de trabajo.</span><span class="sxs-lookup"><span data-stu-id="09ba6-127">A container ID is associated with the work ID.</span></span> <span data-ttu-id="09ba6-128">(Un contenedor no se puede dividir sistemáticamente porque requiere acciones físicas).</span><span class="sxs-lookup"><span data-stu-id="09ba6-128">(A container can't be systematically split, because it requires physical actions.)</span></span>
> - <span data-ttu-id="09ba6-129">El trabajo está asociado a un clúster.</span><span class="sxs-lookup"><span data-stu-id="09ba6-129">The work is associated with a cluster.</span></span>
> - <span data-ttu-id="09ba6-130">El tipo de orden de trabajo es diferente a uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="09ba6-130">The work order type is something other than one of the following types:</span></span>
>
>    - <span data-ttu-id="09ba6-131">Pedidos de ventas</span><span class="sxs-lookup"><span data-stu-id="09ba6-131">Sales orders</span></span>
>    - <span data-ttu-id="09ba6-132">Picking de materia prima</span><span class="sxs-lookup"><span data-stu-id="09ba6-132">Raw material picking</span></span>
>    - <span data-ttu-id="09ba6-133">Emisión de transferencia</span><span class="sxs-lookup"><span data-stu-id="09ba6-133">Transfer issue</span></span>
>
> - <span data-ttu-id="09ba6-134">Actualmente, otro usuario está dividiendo el trabajo.</span><span class="sxs-lookup"><span data-stu-id="09ba6-134">The work is currently being split by another user.</span></span> <span data-ttu-id="09ba6-135">Si intenta abrir la página de división para un trabajo que ya está siendo dividido por otro usuario, recibirá el siguiente mensaje de error: "El trabajo con ID \#\#\#\# actualmente se está dividiendo.</span><span class="sxs-lookup"><span data-stu-id="09ba6-135">If you try to open the splitting page for work that is already being split by another user, you receive the following error message: "The work with ID \#\#\#\# is currently being split.</span></span> <span data-ttu-id="09ba6-136">Vuelva a intentarlo en unos minutos.</span><span class="sxs-lookup"><span data-stu-id="09ba6-136">Retry in a few minutes.</span></span> <span data-ttu-id="09ba6-137">Si continúa recibiendo este mensaje, comuníquese con un supervisor ".</span><span class="sxs-lookup"><span data-stu-id="09ba6-137">If you continue to receive this message, contact a supervisor."</span></span>

<span data-ttu-id="09ba6-138">Una nueva razón para bloquear el trabajo, *Trabajo dividido*, indica cuando el ID de trabajo está en proceso de ser dividido.</span><span class="sxs-lookup"><span data-stu-id="09ba6-138">A new work blocking reason, *Split work*, indicates when the work ID is in the process of being split.</span></span> <span data-ttu-id="09ba6-139">Se muestra tanto en la página **Trabajo dividido** como en la aplicación del almacén si un usuario intenta ejecutar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="09ba6-139">It's shown both on the **Split work** page and in the warehouse app if a user tries to run the work.</span></span> <span data-ttu-id="09ba6-140">Cuando se utilizan motivos de bloqueo, el nombre del campo **Ola bloqueada** del ID de trabajo se cambia a **Bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="09ba6-140">When blocking reasons are used, the name of the **Blocked wave** field from the work ID is changed to **Blocked**.</span></span>

## <a name="initiate-a-work-split"></a><span data-ttu-id="09ba6-141">Iniciar una división de trabajo</span><span class="sxs-lookup"><span data-stu-id="09ba6-141">Initiate a work split</span></span>

<span data-ttu-id="09ba6-142">La función agrega una nueva página **Trabajo dividido** que permite a los usuarios dividir las líneas de trabajo de la identificación del trabajo.</span><span class="sxs-lookup"><span data-stu-id="09ba6-142">The feature adds a new **Split work** page that lets users split work lines from the work ID.</span></span> <span data-ttu-id="09ba6-143">Cuando la página se abre por primera vez, muestra líneas que tienen un estado de trabajo *Abierto* y que están disponibles para dividirse.</span><span class="sxs-lookup"><span data-stu-id="09ba6-143">When the page is first opened, it shows lines that have a work status of *Open* and that are available to be split.</span></span> <span data-ttu-id="09ba6-144">En el panel de acciones, seleccione **Trabajo dividido** para procesar la obra seleccionada.</span><span class="sxs-lookup"><span data-stu-id="09ba6-144">On the Action Pane, select **Split work** to process the selected work.</span></span>

<span data-ttu-id="09ba6-145">Para dividir el trabajo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="09ba6-145">To split work, follow these steps.</span></span>

1. <span data-ttu-id="09ba6-146">Abra una de las páginas de trabajo siguientes:</span><span class="sxs-lookup"><span data-stu-id="09ba6-146">Open one of the following work pages:</span></span>

    - <span data-ttu-id="09ba6-147">**Detalles de trabajo** (**Gestión de almacenes \> Trabajo \> Detalles de trabajo**)</span><span class="sxs-lookup"><span data-stu-id="09ba6-147">**Work details** (**Warehouse management \> Work \> Work details**)</span></span>
    - <span data-ttu-id="09ba6-148">**Todo el trabajo** (**Gestión de almacenes \> Trabajo \> Todo el trabajo**)</span><span class="sxs-lookup"><span data-stu-id="09ba6-148">**All work** (**Warehouse management \> Work \> All work**)</span></span>

1. <span data-ttu-id="09ba6-149">En la cuadrícula, seleccione una ID de trabajo para dividir.</span><span class="sxs-lookup"><span data-stu-id="09ba6-149">In the grid, select a work ID to split.</span></span> <span data-ttu-id="09ba6-150">El campo **Tipo de orden de trabajo** debe establecerse en uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="09ba6-150">The **Work order type** field must be set to one of the following values:</span></span>

    - <span data-ttu-id="09ba6-151">Pedidos de ventas</span><span class="sxs-lookup"><span data-stu-id="09ba6-151">Sales orders</span></span>
    - <span data-ttu-id="09ba6-152">Picking de materia prima</span><span class="sxs-lookup"><span data-stu-id="09ba6-152">Raw material picking</span></span>
    - <span data-ttu-id="09ba6-153">Emisión de transferencia</span><span class="sxs-lookup"><span data-stu-id="09ba6-153">Transfer issue</span></span>

1. <span data-ttu-id="09ba6-154">En el panel de acciones, en la pestaña **Trabajo**, en el grupo **Trabajo**, seleccione **Trabajo dividido**.</span><span class="sxs-lookup"><span data-stu-id="09ba6-154">On the Action Pane, on the **Work** tab, in the **Work** group, select **Split work**.</span></span>

    <span data-ttu-id="09ba6-155">La página **Trabajo dividido** aparece la página y muestra las líneas de trabajo que están abiertas y disponibles para dividirse.</span><span class="sxs-lookup"><span data-stu-id="09ba6-155">The **Split work** page appears and shows the work lines that are open and available to be split.</span></span> <span data-ttu-id="09ba6-156">De forma predeterminada, solo se muestran las líneas de trabajo disponibles.</span><span class="sxs-lookup"><span data-stu-id="09ba6-156">By default, only available work lines are shown.</span></span> <span data-ttu-id="09ba6-157">Para ver todas las líneas para el ID de trabajo (por ejemplo, líneas que tienen un tipo de trabajo de *Ubicación*), seleccione la casilla **Mostrar todas las líneas** sobre la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="09ba6-157">To view all lines for the work ID (for example, lines that have a work type of *Put*), select the **Show all lines** check box above the grid.</span></span>

    <span data-ttu-id="09ba6-158">Se muestra el siguiente mensaje: "Los usuarios no pueden procesar líneas del trabajo hasta que termine de dividir y cierre esta página".</span><span class="sxs-lookup"><span data-stu-id="09ba6-158">The following message is shown: "Users can't process lines of the work until you finish splitting and close this page."</span></span>

    <span data-ttu-id="09ba6-159">El campo **Motivo de bloqueo del trabajo** para el trabajo actual se establecerá en *Trabajo dividido* y el trabajo se bloqueará.</span><span class="sxs-lookup"><span data-stu-id="09ba6-159">The **Work blocking reason** field for the current work will be set to *Split work*, and the work will be blocked.</span></span>

    <span data-ttu-id="09ba6-160">![Razón de bloqueo](media/Blocking_reason.png "Razón de bloqueo")</span><span class="sxs-lookup"><span data-stu-id="09ba6-160">![Blocking reason](media/Blocking_reason.png "Blocking reason")</span></span>

1. <span data-ttu-id="09ba6-161">Seleccione las líneas para eliminar de la identificación de trabajo actual y agregar a una nueva identificación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="09ba6-161">Select the lines to remove from the current work ID and add to a new work ID.</span></span> <span data-ttu-id="09ba6-162">Se producen los eventos siguientes:</span><span class="sxs-lookup"><span data-stu-id="09ba6-162">The following events occur:</span></span>

    - <span data-ttu-id="09ba6-163">Cuando divide el trabajo, la línea o líneas seleccionadas del ID de trabajo original se cancelan y luego se copian en un nuevo ID de trabajo.</span><span class="sxs-lookup"><span data-stu-id="09ba6-163">When you split the work, the selected line or lines from the original work ID are canceled and then copied to a new work ID.</span></span>
    - <span data-ttu-id="09ba6-164">Se conservan la estructura de la plantilla de trabajo existente y la ubicación de la opción put (y también los pares pick / put futuros).</span><span class="sxs-lookup"><span data-stu-id="09ba6-164">The existing work template structure and the location of the put (and also future pick/put pairs) are preserved.</span></span> <span data-ttu-id="09ba6-165">Los valores de los siguientes campos de ID de trabajo se copian del trabajo original al nuevo trabajo:</span><span class="sxs-lookup"><span data-stu-id="09ba6-165">Values for the following work ID fields are copied from the original work to the new work:</span></span>

        - <span data-ttu-id="09ba6-166">Id. de la carga</span><span class="sxs-lookup"><span data-stu-id="09ba6-166">Load ID</span></span>
        - <span data-ttu-id="09ba6-167">Id. del envío</span><span class="sxs-lookup"><span data-stu-id="09ba6-167">Shipment ID</span></span>
        - <span data-ttu-id="09ba6-168">Tipo de orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="09ba6-168">Work order type</span></span>
        - <span data-ttu-id="09ba6-169">Número de pedido</span><span class="sxs-lookup"><span data-stu-id="09ba6-169">Order number</span></span>
        - <span data-ttu-id="09ba6-170">Sitio</span><span class="sxs-lookup"><span data-stu-id="09ba6-170">Site</span></span>
        - <span data-ttu-id="09ba6-171">Almacén</span><span class="sxs-lookup"><span data-stu-id="09ba6-171">Warehouse</span></span>
        - <span data-ttu-id="09ba6-172">Prioridad de trabajo</span><span class="sxs-lookup"><span data-stu-id="09ba6-172">Work priority</span></span>
        - <span data-ttu-id="09ba6-173">Id. del grupo de trabajo</span><span class="sxs-lookup"><span data-stu-id="09ba6-173">Work pool ID</span></span>
        - <span data-ttu-id="09ba6-174">Id. de oleada</span><span class="sxs-lookup"><span data-stu-id="09ba6-174">Wave ID</span></span>
        - <span data-ttu-id="09ba6-175">Número de creación de trabajo</span><span class="sxs-lookup"><span data-stu-id="09ba6-175">Work creation number</span></span>

    - <span data-ttu-id="09ba6-176">Los siguientes campos no se copian en el nuevo ID de trabajo:</span><span class="sxs-lookup"><span data-stu-id="09ba6-176">The following fields aren't copied to the new work ID:</span></span>

        - <span data-ttu-id="09ba6-177">**ID de trabajo** - Se genera un nuevo ID de trabajo a partir de la secuencia numérica adecuada.</span><span class="sxs-lookup"><span data-stu-id="09ba6-177">**Work ID** – A new work ID is generated from the appropriate number sequence.</span></span>
        - <span data-ttu-id="09ba6-178">**Situación laboral** - Este campo se establece en *Abierto*.</span><span class="sxs-lookup"><span data-stu-id="09ba6-178">**Work status** – This field is set to *Open*.</span></span>
        - <span data-ttu-id="09ba6-179">**Bloqueado por** - Este campo se establece inicialmente en blanco.</span><span class="sxs-lookup"><span data-stu-id="09ba6-179">**Locked by** – This field is initially set to blank.</span></span>
        - <span data-ttu-id="09ba6-180">**ID de matrícula de destino** - Este campo se deja en blanco.</span><span class="sxs-lookup"><span data-stu-id="09ba6-180">**Target license plate ID** – This field is left blank.</span></span>
        - <span data-ttu-id="09ba6-181">**Fecha y hora de creación** - Este campo se establece en la fecha y hora actuales.</span><span class="sxs-lookup"><span data-stu-id="09ba6-181">**Created date and time** – This field is set to the current date and time.</span></span>
        - <span data-ttu-id="09ba6-182">**Ola bloqueada/congelada** - Este campo se vuelve a calcular para el ID de trabajo original y el nuevo ID de trabajo.</span><span class="sxs-lookup"><span data-stu-id="09ba6-182">**Blocked wave/frozen** – This field is recomputed for the original work ID and the new work ID.</span></span>

1. <span data-ttu-id="09ba6-183">En el panel de acciones, seleccione **Trabajo dividido**.</span><span class="sxs-lookup"><span data-stu-id="09ba6-183">On the Action Pane, select **Split work**.</span></span>

<span data-ttu-id="09ba6-184">Mientras se divide el trabajo, se muestra el siguiente mensaje: "Operación de procesamiento - Trabajo dividido".</span><span class="sxs-lookup"><span data-stu-id="09ba6-184">While the work is being split, the following message is shown: "Processing operation - Split work".</span></span> <span data-ttu-id="09ba6-185">Mientras este mensaje está visible, puede cancelar la operación seleccionando **Cancelar** en el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="09ba6-185">While this message is visible, you can cancel the operation by selecting **Cancel** in the message box.</span></span>

<span data-ttu-id="09ba6-186">Si la casilla **Mostrar todas las líneas** está desactivada, la línea que se separó y canceló ya no aparecerá en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="09ba6-186">If the **Show all lines** check box is cleared, the line that was split off and canceled will no longer appear in the grid.</span></span> <span data-ttu-id="09ba6-187">Si la casilla de verificación está seleccionada, debería ver que el valor del campo **Situación laboral** de esa línea ha cambiado a *Cancelado*.</span><span class="sxs-lookup"><span data-stu-id="09ba6-187">If the check box is selected, you should see that the value of the **Work status** field for that line has changed to *Canceled*.</span></span>

<span data-ttu-id="09ba6-188">Se muestra la siguiente notificación para indicar que se ha creado el nuevo ID de trabajo: "El trabajo \#\#\#\# se ha creado separándolo del trabajo original \#\#\#\#".</span><span class="sxs-lookup"><span data-stu-id="09ba6-188">The following notification is shown to indicate that the new work ID has been created: "Work \#\#\#\# has been created by splitting off from original work \#\#\#\#."</span></span>

<span data-ttu-id="09ba6-189">Otras líneas de trabajo del ID de trabajo original (como líneas de *Ubicación*) se ajustarán según sea necesario para reflejar las líneas de trabajo que se han cancelado.</span><span class="sxs-lookup"><span data-stu-id="09ba6-189">Other work lines from the original work ID (such as *Put* lines) will be adjusted as required to reflect the lines of work that have been canceled.</span></span> <span data-ttu-id="09ba6-190">Por ejemplo, si el ID de trabajo original tenía una línea de *Ubicación* para una cantidad de 15 y se cancelaron líneas de *Selección* que tienen una cantidad total de 10, la nueva cantidad de *Ubicación* en el ID de trabajo original ahora será 5.</span><span class="sxs-lookup"><span data-stu-id="09ba6-190">For example, if the original work ID had a *Put* line for a quantity of 15, and *Pick* lines that have a total quantity of 10 were canceled, the new *Put* quantity on the original work ID will now be 5.</span></span>

<span data-ttu-id="09ba6-191">El nuevo trabajo no se asignará inmediatamente a ningún usuario.</span><span class="sxs-lookup"><span data-stu-id="09ba6-191">The new work won't immediately be assigned to any user.</span></span> <span data-ttu-id="09ba6-192">Sin embargo, ahora puede asignarlo a un usuario, según sea necesario, utilizando la funcionalidad estándar de la página **Detalles del trabajo**.</span><span class="sxs-lookup"><span data-stu-id="09ba6-192">However, you can assign it to a user now, as required, by using the standard functionality of the **Work details** page.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="09ba6-193">Puede dividir solo las ID de trabajo que contengan dos o más líneas de trabajo disponibles.</span><span class="sxs-lookup"><span data-stu-id="09ba6-193">You can split only work IDs that contain two or more available work lines.</span></span> <span data-ttu-id="09ba6-194">Si selecciona **Trabajo dividido** cuando solo hay una línea de trabajo, recibirá el siguiente mensaje de error: "Al menos una línea de trabajo debe permanecer en el trabajo inicial".</span><span class="sxs-lookup"><span data-stu-id="09ba6-194">If you select **Split work** when there is only one work line, you will receive the following error message: "At least one work line must remain on initial work."</span></span> <span data-ttu-id="09ba6-195">En este caso, no se producirá ninguna división.</span><span class="sxs-lookup"><span data-stu-id="09ba6-195">In this case, no splitting will occur.</span></span>

## <a name="finish-a-work-split"></a><span data-ttu-id="09ba6-196">Finalizar una división de trabajo</span><span class="sxs-lookup"><span data-stu-id="09ba6-196">Finish a work split</span></span>

<span data-ttu-id="09ba6-197">Para terminar de dividir el trabajo, debe eliminarse el motivo de bloqueo de *Trabajo dividido*.</span><span class="sxs-lookup"><span data-stu-id="09ba6-197">To finish splitting work, the *Split work* blocking reason must be removed.</span></span> <span data-ttu-id="09ba6-198">Hay dos maneras para completar este paso:</span><span class="sxs-lookup"><span data-stu-id="09ba6-198">There are two ways to complete this step:</span></span>

- <span data-ttu-id="09ba6-199">El usuario que está dividiendo el trabajo cierra la página **Trabajo dividido** seleccionando el botón **Cerrar** (**X**) en la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="09ba6-199">The user who is splitting the work closes the **Split work** page by selecting the **Close** button (**X**) in the upper-right corner.</span></span> <span data-ttu-id="09ba6-200">Cuando se cierra la página, se eliminará el motivo de bloqueo de *Trabajo dividido*.</span><span class="sxs-lookup"><span data-stu-id="09ba6-200">When the page is closed, the *Split Work* blocking reason will be removed.</span></span> <span data-ttu-id="09ba6-201">Se volverá a calcular el estado de *Bloqueo* de este trabajo y, si no quedan razones de bloqueo para este trabajo, se desbloqueará el trabajo.</span><span class="sxs-lookup"><span data-stu-id="09ba6-201">The *Blocked* state of this work will be recomputed and, if there are no remaining blocking reasons for this work, the work will be unblocked.</span></span>
- <span data-ttu-id="09ba6-202">Cualquier usuario abre el ID de trabajo y selecciona el botón **Cancelar sesión de trabajo dividido** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="09ba6-202">Any user opens the work ID and selects the **Cancel work split session** button on the Action Pane.</span></span> <span data-ttu-id="09ba6-203">El motivo de bloqueo de *Trabajo dividido* se eliminará y se volverá a calcular el estado *Bloqueado* de este trabajo, al igual que cuando se cierra la página **Trabajo dividido**.</span><span class="sxs-lookup"><span data-stu-id="09ba6-203">The *Split work* blocking reason will be removed, and the *Blocked* state of this work will be recomputed, just as when the **Split work** page is closed.</span></span>

<span data-ttu-id="09ba6-204">Después de que se elimina la razón de bloqueo de *Trabajo dividido*, el trabajo se puede ejecutar en el dispositivo móvil, siempre que el estado **Bloqueado** esté configurado en *No* en la identificación del trabajo.</span><span class="sxs-lookup"><span data-stu-id="09ba6-204">After the *Split work* blocking reason is removed, the work can be run on the mobile device, provided that the **Blocked** state is set to *No* on the work ID.</span></span>

## <a name="user-blocking-on-the-warehouse-app"></a><span data-ttu-id="09ba6-205">Bloqueo de usuarios en la aplicación del almacén</span><span class="sxs-lookup"><span data-stu-id="09ba6-205">User blocking on the warehouse app</span></span>

<span data-ttu-id="09ba6-206">Si intenta utilizar la aplicación del almacén para ejecutar el trabajo de picking con un ID de trabajo que se está dividiendo, recibirá el siguiente mensaje de error: "El trabajo con ID \#\#\#\# se está dividiendo actualmente".</span><span class="sxs-lookup"><span data-stu-id="09ba6-206">If you try to use the warehouse app to run picking work against a work ID that is being split, you will receive the following error message: "The work with ID \#\#\#\# is currently being split."</span></span> <span data-ttu-id="09ba6-207">Si recibe este mensaje, seleccione **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="09ba6-207">If you receive this message, select **Cancel**.</span></span> <span data-ttu-id="09ba6-208">Luego puede continuar procesando otro trabajo.</span><span class="sxs-lookup"><span data-stu-id="09ba6-208">You can then continue to process other work.</span></span>

## <a name="other-blocked-operations"></a><span data-ttu-id="09ba6-209">Otras operaciones bloqueadas</span><span class="sxs-lookup"><span data-stu-id="09ba6-209">Other blocked operations</span></span>

<span data-ttu-id="09ba6-210">Cualquier operación que modifique líneas de trabajo, transacciones de inventario de trabajo o enlaces de reabastecimiento que estén relacionados con el trabajo que se está dividiendo fallará y se mostrará el siguiente mensaje de error: "El trabajo con ID \#\#\#\# se está dividiendo actualmente".</span><span class="sxs-lookup"><span data-stu-id="09ba6-210">Any operations that modify work lines, work inventory transactions, or replenishment links that are related to work that is being split will fail, and the following error message will be shown: "The work with ID \#\#\#\# is currently being split."</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]