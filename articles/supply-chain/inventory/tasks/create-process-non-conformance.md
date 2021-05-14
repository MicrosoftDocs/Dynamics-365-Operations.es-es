---
title: Crear y procesar disconformidades
description: Este tema describe cómo gestionar los casos de disconformidad, en función de un pedido de calidad existente.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 06a56a694f7a80d65cb46d08744e78d8361cee3b
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956215"
---
# <a name="create-and-process-nonconformances"></a><span data-ttu-id="999c8-103">Crear y procesar disconformidades</span><span class="sxs-lookup"><span data-stu-id="999c8-103">Create and process nonconformances</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="999c8-104">Este tema describe cómo gestionar los casos de disconformidad, en función de un pedido de calidad existente.</span><span class="sxs-lookup"><span data-stu-id="999c8-104">This topic describes how to perform nonconformance management based on an existing quality order.</span></span> <span data-ttu-id="999c8-105">Por lo general, la gestión de disconformidades la realiza un empleado de calidad.</span><span class="sxs-lookup"><span data-stu-id="999c8-105">Typically, nonconformance management is done by a quality clerk.</span></span> <span data-ttu-id="999c8-106">Como requisito previo, debe tener disponible un pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="999c8-106">As a prerequisite, you must have a quality order available.</span></span> <span data-ttu-id="999c8-107">(Para obtener información sobre cómo crear un pedido de calidad, consulte [Inspeccionar la calidad de los productos](inspect-quality-goods.md)).</span><span class="sxs-lookup"><span data-stu-id="999c8-107">(For information about how to create a quality order, see [Inspect the quality of goods](inspect-quality-goods.md).)</span></span>

<span data-ttu-id="999c8-108">Antes de que un usuario pueda procesar la aprobación de una disconformidad, se le debe asignar un trabajador en el campo **Persona** de la página **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="999c8-108">Before a user can process the approval of a nonconformance, a worker must be assigned to them in the **Person** field on the **Users** page.</span></span> <span data-ttu-id="999c8-109">Además, antes de que el usuario pueda utilizar las notas del documento, la opción **Habilitar el manejo de documentos** debe establecerse en *Sí* en sus opciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="999c8-109">Additionally, before the user can use the document notes, the **Enable document handling** option must be set to *Yes* in their user options.</span></span>

## <a name="create-a-nonconformance"></a><span data-ttu-id="999c8-110">Creación de una disconformidad</span><span class="sxs-lookup"><span data-stu-id="999c8-110">Create a nonconformance</span></span>

<span data-ttu-id="999c8-111">Para crear una disconformidad, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="999c8-111">To create a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="999c8-112">Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Disconformidades**.</span><span class="sxs-lookup"><span data-stu-id="999c8-112">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="999c8-113">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="999c8-113">On the Action pane, select **New**.</span></span>
1. <span data-ttu-id="999c8-114">En el cuadro de diálogo **Crear disconformidad**, en el campo **Tipo de problema**, seleccione el tipo de problema que se encontró durante el proceso de inspección.</span><span class="sxs-lookup"><span data-stu-id="999c8-114">In the **Create non conformance** dialog box, in **Problem type** field, select the type of problem that was found during the inspection process.</span></span>
1. <span data-ttu-id="999c8-115">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="999c8-115">Select **OK**.</span></span>

## <a name="approve-or-reject-a-nonconformance"></a><span data-ttu-id="999c8-116">Aprobación o rechazo de una disconformidad</span><span class="sxs-lookup"><span data-stu-id="999c8-116">Approve or reject a nonconformance</span></span>

<span data-ttu-id="999c8-117">Para aprobar o rechazar una disconformidad, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="999c8-117">To approve or reject a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="999c8-118">Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Disconformidades**.</span><span class="sxs-lookup"><span data-stu-id="999c8-118">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="999c8-119">En la lista, seleccione la disconformidad que desee actualizar.</span><span class="sxs-lookup"><span data-stu-id="999c8-119">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="999c8-120">Puede agregar una corrección solo a las disconformidades aprobadas.</span><span class="sxs-lookup"><span data-stu-id="999c8-120">You can add a correction only to nonconformances that are approved.</span></span>

1. <span data-ttu-id="999c8-121">En el panel de acciones, seleccione **Funciones \> Aprobar disconformidad** para aprobar la disconformidad o **Funciones \> Rechazar la disconformidad** para rechazarla.</span><span class="sxs-lookup"><span data-stu-id="999c8-121">On the Action Pane, select **Functions \> Approve non conformance** to approve the nonconformance or **Functions \> Refuse non conformance** to reject it.</span></span> <span data-ttu-id="999c8-122">Puede asociar disconformidades aprobadas con [operaciones relacionadas](../quality-operations.md).</span><span class="sxs-lookup"><span data-stu-id="999c8-122">You can associate approved nonconformances with [related operations](../quality-operations.md).</span></span> <span data-ttu-id="999c8-123">De esta manera, puede registrar el trabajo que se realiza como parte del manejo de disconformidades y el procesamiento del manejo de correcciones.</span><span class="sxs-lookup"><span data-stu-id="999c8-123">In this way, you can record work that is done as part of the nonconformance handling and the processing of correction handling.</span></span>
1. <span data-ttu-id="999c8-124">Se le pedirá que confirme su selección.</span><span class="sxs-lookup"><span data-stu-id="999c8-124">You're prompted to confirm your selection.</span></span> <span data-ttu-id="999c8-125">Seleccione **Sí** para continuar.</span><span class="sxs-lookup"><span data-stu-id="999c8-125">Select **Yes** to continue.</span></span>

## <a name="add-operations-and-other-details-to-nonconformances"></a><span data-ttu-id="999c8-126">Agregar operaciones y otros detalles a las disconformidades</span><span class="sxs-lookup"><span data-stu-id="999c8-126">Add operations and other details to nonconformances</span></span>

<span data-ttu-id="999c8-127">Una vez que haya creado una disconformidad, puede comenzar a agregar operaciones relacionadas y especificar información adicional sobre esas operaciones.</span><span class="sxs-lookup"><span data-stu-id="999c8-127">After you've created a nonconformance, you can start to add related operations and specify additional information about those operations.</span></span> <span data-ttu-id="999c8-128">Puede agregar operaciones relacionadas solo a las disconformidades aprobadas.</span><span class="sxs-lookup"><span data-stu-id="999c8-128">You can add related operations only to nonconformances that are approved.</span></span>

<span data-ttu-id="999c8-129">Además de la información básica, puede agregar los siguientes detalles a una operación:</span><span class="sxs-lookup"><span data-stu-id="999c8-129">Besides the basic information, you can add the following details to an operation:</span></span>

- <span data-ttu-id="999c8-130">**Artículos**: puede crear una lista de elementos que se consumen para realizar la corrección.</span><span class="sxs-lookup"><span data-stu-id="999c8-130">**Items** – You can create a list of items that are consumed to perform the correction.</span></span> <span data-ttu-id="999c8-131">Por ejemplo, los artículos pueden ser productos necesarios para reparar equipos o ingredientes necesarios para reelaborar un producto terminado.</span><span class="sxs-lookup"><span data-stu-id="999c8-131">For example, the items might be products that are required to repair equipment or ingredients that are required to rework a finished product.</span></span>
- <span data-ttu-id="999c8-132">**Cargos por calidad**: puede crear una lista de cargos incurridos o facturados a fuentes externas.</span><span class="sxs-lookup"><span data-stu-id="999c8-132">**Quality charges** – You can create a list of charges that are incurred or billed out to external sources.</span></span>
- <span data-ttu-id="999c8-133">**Hoja de tiempos**: puede crear un registro del tiempo que cada trabajador dedica a la operación.</span><span class="sxs-lookup"><span data-stu-id="999c8-133">**Timesheet** – You can create a log of the time that each worker spends on the operation.</span></span>

<span data-ttu-id="999c8-134">Las opciones restantes son opcionales.</span><span class="sxs-lookup"><span data-stu-id="999c8-134">The remaining settings are optional.</span></span> <span data-ttu-id="999c8-135">El coste de cada artículo, los cargos por calidad y la hoja de tiempos se suman y se muestran en la operación.</span><span class="sxs-lookup"><span data-stu-id="999c8-135">The cost for each item, quality charges, and the timesheet are summed and shown on the operation.</span></span> <span data-ttu-id="999c8-136">No puede editar directamente el campo **Coste** en la operación.</span><span class="sxs-lookup"><span data-stu-id="999c8-136">You can't directly edit the **Cost** field on the operation.</span></span>

### <a name="create-an-operation-for-a-nonconformance"></a><span data-ttu-id="999c8-137">Crear una operación para una disconformidad</span><span class="sxs-lookup"><span data-stu-id="999c8-137">Create an operation for a nonconformance</span></span>

<span data-ttu-id="999c8-138">Para crear una operación para una disconformidad, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="999c8-138">To create an operation for a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="999c8-139">Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Disconformidades**.</span><span class="sxs-lookup"><span data-stu-id="999c8-139">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="999c8-140">En la lista, seleccione la disconformidad que desee actualizar.</span><span class="sxs-lookup"><span data-stu-id="999c8-140">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="999c8-141">Puede agregar o actualizar operaciones solo para disconformidades aprobadas.</span><span class="sxs-lookup"><span data-stu-id="999c8-141">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="999c8-142">En el panel acciones, seleccione **Operaciones relacionadas**.</span><span class="sxs-lookup"><span data-stu-id="999c8-142">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="999c8-143">En la página **Operaciones relacionadas**, en el panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="999c8-143">On the **Related operations** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="999c8-144">Entonces establezca los siguientes campos para la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="999c8-144">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="999c8-145">**Operación**: seleccione el código de la operación que se realizará por la disconformidad.</span><span class="sxs-lookup"><span data-stu-id="999c8-145">**Operation** – Select the code of the operation that will be performed for the nonconformance.</span></span>
    - <span data-ttu-id="999c8-146">**Razón**: introduzca una descripción detallada que explique por qué se requiere la operación.</span><span class="sxs-lookup"><span data-stu-id="999c8-146">**Reason** – Enter a detailed description that explains why the operation is required.</span></span>
    - <span data-ttu-id="999c8-147">**Pedido de ventas**: si el código de operación seleccionado está relacionado con el tipo de pedido de ventas, seleccione el pedido de ventas al que está vinculando la operación.</span><span class="sxs-lookup"><span data-stu-id="999c8-147">**Sales order** – If the selected operation code is related to the sales order type, select the sales order that you're linking the operation to.</span></span>
    - <span data-ttu-id="999c8-148">**Pedido de compra**: si el código de operación seleccionado está relacionado con el tipo de pedido de compra, seleccione el pedido de compra al que está vinculando la operación.</span><span class="sxs-lookup"><span data-stu-id="999c8-148">**Purchase order** – If the selected operation code is related to the purchase order type, select the purchase order that you're linking the operation to.</span></span>

1. <span data-ttu-id="999c8-149">Cierre las páginas.</span><span class="sxs-lookup"><span data-stu-id="999c8-149">Close the pages.</span></span>

### <a name="add-items-to-an-operation"></a><span data-ttu-id="999c8-150">Agregar artículos a una operación</span><span class="sxs-lookup"><span data-stu-id="999c8-150">Add items to an operation</span></span>

<span data-ttu-id="999c8-151">Para agregar elementos a una operación, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="999c8-151">To add items to an operation, follow these steps.</span></span>

1. <span data-ttu-id="999c8-152">Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Disconformidades**.</span><span class="sxs-lookup"><span data-stu-id="999c8-152">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="999c8-153">En la lista, seleccione la disconformidad que desee actualizar.</span><span class="sxs-lookup"><span data-stu-id="999c8-153">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="999c8-154">Puede agregar o actualizar operaciones solo para disconformidades aprobadas.</span><span class="sxs-lookup"><span data-stu-id="999c8-154">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="999c8-155">En el panel acciones, seleccione **Operaciones relacionadas**.</span><span class="sxs-lookup"><span data-stu-id="999c8-155">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="999c8-156">En la página **Operaciones rellacionadas**, seleccione la operación a la que desea agregar artículos.</span><span class="sxs-lookup"><span data-stu-id="999c8-156">On the **Related operations** page, select the operation that you want to add items to.</span></span>
1. <span data-ttu-id="999c8-157">En el panel de acciones, haga clic en **Artículos**.</span><span class="sxs-lookup"><span data-stu-id="999c8-157">On the Action Pane, select **Items**.</span></span>
1. <span data-ttu-id="999c8-158">En la página **Operaciones relacionadas**, en el panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="999c8-158">On the **Related operations** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="999c8-159">Entonces establezca los siguientes campos para la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="999c8-159">Then set the following fields for new row:</span></span>

    - <span data-ttu-id="999c8-160">**Número de artículo**: seleccione el producto que se consumirá como parte de la operación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="999c8-160">**Item number** – Select the product that will be consumed as part of the selected operation.</span></span>
    - <span data-ttu-id="999c8-161">**Cantidad**: introduzca la cantidad de artículos que se consumirán.</span><span class="sxs-lookup"><span data-stu-id="999c8-161">**Quantity** – Enter the number of items that will be consumed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="999c8-162">Puede ver el coste del artículo en el campo **Coste** de la pestaña **General**. El coste que se muestra allí proviene del coste que se establece en la página **Producto liberado**.</span><span class="sxs-lookup"><span data-stu-id="999c8-162">You can view the cost for the item in the **Cost** field on the **General** tab. The cost that is shown there comes from the cost that is set up on the **Released product** page.</span></span> <span data-ttu-id="999c8-163">El coste no se puede actualizar directamente en la página **Artículo de operación relacionado**.</span><span class="sxs-lookup"><span data-stu-id="999c8-163">The cost can't be updated directly on the **Related operation item** page.</span></span> <span data-ttu-id="999c8-164">El coste de todos los elementos que se agregan en la página **Artículos de operación relacionados** se agrega automáticamente al campo **Coste** en la página **Operaciones relacionadas**.</span><span class="sxs-lookup"><span data-stu-id="999c8-164">The cost of all items that are added on the **Related operation items** page is automatically added to the **Cost** field on the **Related operations** page.</span></span>

1. <span data-ttu-id="999c8-165">Repita el paso anterior para cada elemento adicional que deba agregar.</span><span class="sxs-lookup"><span data-stu-id="999c8-165">Repeat the previous step for each additional item that you must add.</span></span>
1. <span data-ttu-id="999c8-166">Cierre las páginas.</span><span class="sxs-lookup"><span data-stu-id="999c8-166">Close the pages.</span></span>

### <a name="add-quality-charges-to-an-operation"></a><span data-ttu-id="999c8-167">Agregar cargos de calidad a una operación</span><span class="sxs-lookup"><span data-stu-id="999c8-167">Add quality charges to an operation</span></span>

<span data-ttu-id="999c8-168">Para agregar cargos de calidad a una operación, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="999c8-168">To add quality charges to an operation, follow these steps.</span></span>

1. <span data-ttu-id="999c8-169">Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Disconformidades**.</span><span class="sxs-lookup"><span data-stu-id="999c8-169">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="999c8-170">En la lista, seleccione la disconformidad que desee actualizar.</span><span class="sxs-lookup"><span data-stu-id="999c8-170">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="999c8-171">Puede agregar o actualizar operaciones solo para disconformidades aprobadas.</span><span class="sxs-lookup"><span data-stu-id="999c8-171">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="999c8-172">En el panel acciones, seleccione **Operaciones relacionadas**.</span><span class="sxs-lookup"><span data-stu-id="999c8-172">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="999c8-173">En la página **Operaciones rellacionadas**, seleccione la operación a la que desea agregar cargos de calidad.</span><span class="sxs-lookup"><span data-stu-id="999c8-173">On the **Related operations** page, select the operation that you want to add quality charges to.</span></span>
1. <span data-ttu-id="999c8-174">En el panel acciones, seleccione **Cargos de calidad**.</span><span class="sxs-lookup"><span data-stu-id="999c8-174">On the Action Pane, select **Quality charges**.</span></span>
1. <span data-ttu-id="999c8-175">En la página **Cargos de operaciones relacionadas**, en el panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="999c8-175">On the **Related operation charges** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="999c8-176">Entonces establezca los siguientes campos para la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="999c8-176">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="999c8-177">**Código de cargos**: seleccione el cargo de calidad que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="999c8-177">**Charges code** – Select the quality charge that you want to add.</span></span>
    - <span data-ttu-id="999c8-178">**Descripción**: escriba una descripción detallada del cargo.</span><span class="sxs-lookup"><span data-stu-id="999c8-178">**Description** – Enter a detailed description of the charge.</span></span>
    - <span data-ttu-id="999c8-179">**Valor de cargos**: especifique el importe del cargo.</span><span class="sxs-lookup"><span data-stu-id="999c8-179">**Charges value** – Enter the amount of the charge.</span></span>

1. <span data-ttu-id="999c8-180">Repita el paso anterior para cada cargo adicional que deba agregar.</span><span class="sxs-lookup"><span data-stu-id="999c8-180">Repeat the previous step for each additional charge that you must add.</span></span>
1. <span data-ttu-id="999c8-181">Cierre las páginas.</span><span class="sxs-lookup"><span data-stu-id="999c8-181">Close the pages.</span></span>

> [!NOTE]
> <span data-ttu-id="999c8-182">La cantidad en el campo **Valor de los cargos** se suma automáticamente para todos los cargos de calidad y se agrega a cualquier otra cantidad en el campo **Coste** de la página **Operaciones relacionadas**.</span><span class="sxs-lookup"><span data-stu-id="999c8-182">The amount in the **Charges value** field is automatically summed for all quality charges and added to any other amounts in the **Cost** field on the **Related operations** page.</span></span>

### <a name="create-a-timesheet-on-an-operation"></a><span data-ttu-id="999c8-183">Crear una hoja de tiempo en una operación</span><span class="sxs-lookup"><span data-stu-id="999c8-183">Create a timesheet on an operation</span></span>

<span data-ttu-id="999c8-184">Para agregar una hoja de tiempo a una operación, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="999c8-184">To add a timesheet to an operation, follow these steps.</span></span>

1. <span data-ttu-id="999c8-185">Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Disconformidades**.</span><span class="sxs-lookup"><span data-stu-id="999c8-185">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="999c8-186">En la lista, seleccione la disconformidad que desee actualizar.</span><span class="sxs-lookup"><span data-stu-id="999c8-186">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="999c8-187">Puede agregar o actualizar operaciones solo para disconformidades aprobadas.</span><span class="sxs-lookup"><span data-stu-id="999c8-187">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="999c8-188">En el panel acciones, seleccione **Operaciones relacionadas**.</span><span class="sxs-lookup"><span data-stu-id="999c8-188">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="999c8-189">En la página **Operaciones rellacionadas**, seleccione la operación a la que desea agregar una hoja de tiempo.</span><span class="sxs-lookup"><span data-stu-id="999c8-189">On the **Related operations** page, select the operation that you want to add a timesheet to.</span></span>
1. <span data-ttu-id="999c8-190">En el panel de acciones, seleccione **Hoja de tiempo**.</span><span class="sxs-lookup"><span data-stu-id="999c8-190">On the Action Pane, select **Timesheet**.</span></span>
1. <span data-ttu-id="999c8-191">En la página **Hojas de tiempo de operaciones relacionadas**, en el panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="999c8-191">On the **Related operation time sheets** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="999c8-192">Entonces establezca los siguientes campos para la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="999c8-192">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="999c8-193">**Fecha**: especifique la fecha en que se realizó el trabajo.</span><span class="sxs-lookup"><span data-stu-id="999c8-193">**Date** – Specify the date when work was done.</span></span> <span data-ttu-id="999c8-194">De forma predeterminada, este campo es la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="999c8-194">By default, this field is set to the current date.</span></span>
    - <span data-ttu-id="999c8-195">**Trabajador**: seleccione el trabajador que realizó el trabajo.</span><span class="sxs-lookup"><span data-stu-id="999c8-195">**Worker** – Select the worker who did the work.</span></span> <span data-ttu-id="999c8-196">De forma predeterminada, este campo está configurado para el trabajador que está asignado al usuario actual.</span><span class="sxs-lookup"><span data-stu-id="999c8-196">By default, this field is set to the worker that is assigned to the current user.</span></span>
    - <span data-ttu-id="999c8-197">**Horas de operación**: introduzca el número de horas que se trabajaron en la operación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="999c8-197">**Operation hours** – Enter the number of hours that were worked on the selected operation.</span></span>
    - <span data-ttu-id="999c8-198">**Facturado**: seleccione esta casilla de verificación si el tiempo se ha cargado a un cliente o proveedor en una factura.</span><span class="sxs-lookup"><span data-stu-id="999c8-198">**Invoiced** – Select this check box if the time has been charged to a customer or vendor on an invoice.</span></span>

    > [!NOTE]
    > <span data-ttu-id="999c8-199">Puede ver el coste en el campo **Coste** de la pestaña **General**. El coste se calcula utilizando la tarifa que defina en la página **Parámetros de gestión de inventario**.</span><span class="sxs-lookup"><span data-stu-id="999c8-199">You can view the cost in the **Cost** field on the **General** tab. The cost is calculated by using the rate that you define on the **Inventory management parameters** page.</span></span>

1. <span data-ttu-id="999c8-200">Repita el paso anterior para cada línea de hoja de tiempo adicional que deba agregar.</span><span class="sxs-lookup"><span data-stu-id="999c8-200">Repeat the previous step for each additional timesheet line that you must add.</span></span>
1. <span data-ttu-id="999c8-201">Cierre las páginas.</span><span class="sxs-lookup"><span data-stu-id="999c8-201">Close the pages.</span></span>

> [!NOTE]
> <span data-ttu-id="999c8-202">La cantidad del campo **Coste** se suma automáticamente para todas las líneas de hoja de tiempo y se agrega a cualquier otra cantidad en el campo **Coste** de la página **Operaciones relacionadas**.</span><span class="sxs-lookup"><span data-stu-id="999c8-202">The amount in the **Cost** field is summed for all timesheet lines and added to any other amounts in the **Cost** field on the **Related operations** page.</span></span>

## <a name="add-a-correction-to-a-nonconformance"></a><span data-ttu-id="999c8-203">Agregar una corrección a una disconformidad</span><span class="sxs-lookup"><span data-stu-id="999c8-203">Add a correction to a nonconformance</span></span>

<span data-ttu-id="999c8-204">Para agregar una corrección a una disconformidad, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="999c8-204">To add a correction to a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="999c8-205">Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Disconformidades**.</span><span class="sxs-lookup"><span data-stu-id="999c8-205">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="999c8-206">En la lista, seleccione la disconformidad que desee actualizar.</span><span class="sxs-lookup"><span data-stu-id="999c8-206">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="999c8-207">Puede agregar una corrección solo a las disconformidades aprobadas.</span><span class="sxs-lookup"><span data-stu-id="999c8-207">You can add a correction only to nonconformances that are approved.</span></span>

1. <span data-ttu-id="999c8-208">En el panel de acciones, seleccione **Correcciones**.</span><span class="sxs-lookup"><span data-stu-id="999c8-208">On the Action Pane, select **Corrections**.</span></span>
1. <span data-ttu-id="999c8-209">En la página **Correcciones**, en el panel de acciones, seleccione **Nueva** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="999c8-209">On the **Corrections** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="999c8-210">Entonces establezca los siguientes campos para la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="999c8-210">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="999c8-211">**Diagnóstico**: seleccione el tipo de diagnóstico que identifica el tipo de corrección que está creando.</span><span class="sxs-lookup"><span data-stu-id="999c8-211">**Diagnostic** – Select the diagnostic type that identifies the type of correction that you're creating.</span></span>
    - <span data-ttu-id="999c8-212">**Trabajador**: seleccione la persona responsable de la corrección.</span><span class="sxs-lookup"><span data-stu-id="999c8-212">**Worker** – Select the person who is responsible for the correction.</span></span>
    - <span data-ttu-id="999c8-213">**Prioridad de corrección**: seleccione una opción para indicar cómo se debe priorizar la corrección (*Baja*, *Normal* o *Elevada*).</span><span class="sxs-lookup"><span data-stu-id="999c8-213">**Correction priority** – Select an option to indicate how the correction should be prioritized (*Low*, *Normal*, or *High*).</span></span>
    - <span data-ttu-id="999c8-214">**Fecha solicitada**: introduzca la fecha en la que se solicitó la acción correctiva.</span><span class="sxs-lookup"><span data-stu-id="999c8-214">**Requested date** – Enter the date when the corrective action was requested.</span></span>
    - <span data-ttu-id="999c8-215">**Cita planeada**: introduzca la fecha en la que se espera que se complete la corrección.</span><span class="sxs-lookup"><span data-stu-id="999c8-215">**Planned date** – Enter the date when the correction is expected to be completed.</span></span>
    - <span data-ttu-id="999c8-216">**Solución a corto plazo**: seleccione esta casilla si la acción correctiva corrige la disconformidad solo por un período breve.</span><span class="sxs-lookup"><span data-stu-id="999c8-216">**Short term solution** – Select this check box if the corrective action corrects the nonconformance only for a short time.</span></span>

1. <span data-ttu-id="999c8-217">Cierre las páginas.</span><span class="sxs-lookup"><span data-stu-id="999c8-217">Close the pages.</span></span>

## <a name="mark-a-correction-as-completed"></a><span data-ttu-id="999c8-218">Marcar una corrección como completada</span><span class="sxs-lookup"><span data-stu-id="999c8-218">Mark a correction as completed</span></span>

<span data-ttu-id="999c8-219">Para marcar una corrección a una disconformidad como completada, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="999c8-219">To mark a nonconformance correction as completed, follow these steps.</span></span>

1. <span data-ttu-id="999c8-220">Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Disconformidades**.</span><span class="sxs-lookup"><span data-stu-id="999c8-220">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="999c8-221">En la lista, seleccione la disconformidad que desee actualizar.</span><span class="sxs-lookup"><span data-stu-id="999c8-221">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="999c8-222">Puede agregar una corrección solo a las disconformidades aprobadas.</span><span class="sxs-lookup"><span data-stu-id="999c8-222">You can add a correction only to nonconformances that are approved.</span></span>

1. <span data-ttu-id="999c8-223">En el panel de acciones, seleccione **Correcciones**.</span><span class="sxs-lookup"><span data-stu-id="999c8-223">On the Action Pane, select **Corrections**.</span></span>
1. <span data-ttu-id="999c8-224">En la página **Correcciones**, en la cuadrícula, seleccione la corrección que desea marcar como completada.</span><span class="sxs-lookup"><span data-stu-id="999c8-224">On the **Corrections** page, in the grid, select the correction that you want to mark as completed.</span></span>
1. <span data-ttu-id="999c8-225">En el panel de acciones, seleccione **Marcar como completada**.</span><span class="sxs-lookup"><span data-stu-id="999c8-225">On the Action Pane, select **Mark complete**.</span></span>
1. <span data-ttu-id="999c8-226">Se le pedirá que confirme su selección.</span><span class="sxs-lookup"><span data-stu-id="999c8-226">You're prompted to confirm your selection.</span></span> <span data-ttu-id="999c8-227">Seleccione **Aceptar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="999c8-227">Select **OK** to continue.</span></span> <span data-ttu-id="999c8-228">El campo **Fecha y hora de finalización** se establece en la fecha y hora actuales, y se selecciona la casilla **Completado**.</span><span class="sxs-lookup"><span data-stu-id="999c8-228">The **Completion date and time** field is set to the current date and time, and the **Completed** check box is selected.</span></span>
1. <span data-ttu-id="999c8-229">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="999c8-229">Close the page.</span></span>

## <a name="reopen-a-completed-correction"></a><span data-ttu-id="999c8-230">Reabrir una corrección completada</span><span class="sxs-lookup"><span data-stu-id="999c8-230">Reopen a completed correction</span></span>

<span data-ttu-id="999c8-231">Para reabrir una corrección completada, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="999c8-231">To reopen a completed correction, follow these steps.</span></span>

1. <span data-ttu-id="999c8-232">Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Disconformidades**.</span><span class="sxs-lookup"><span data-stu-id="999c8-232">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="999c8-233">En la lista, seleccione la disconformidad que desee actualizar.</span><span class="sxs-lookup"><span data-stu-id="999c8-233">In the list, select the nonconformance that you want to update.</span></span>
1. <span data-ttu-id="999c8-234">En el panel de acciones, seleccione **Correcciones**.</span><span class="sxs-lookup"><span data-stu-id="999c8-234">On the Action pane, select **Corrections**.</span></span>
1. <span data-ttu-id="999c8-235">En la página **Correcciones**, en la cuadrícula, seleccione la corrección que desea reabrir.</span><span class="sxs-lookup"><span data-stu-id="999c8-235">On the **Corrections** page, in the grid, select the correction that you want to reopen.</span></span>
1. <span data-ttu-id="999c8-236">En el panel de acciones, haga clic en **Reabrir**.</span><span class="sxs-lookup"><span data-stu-id="999c8-236">On the Action Pane, select **Reopen**.</span></span>
1. <span data-ttu-id="999c8-237">Se le pedirá que confirme su selección.</span><span class="sxs-lookup"><span data-stu-id="999c8-237">You're prompted to confirm your selection.</span></span> <span data-ttu-id="999c8-238">Seleccione **Aceptar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="999c8-238">Select **OK** to continue.</span></span> <span data-ttu-id="999c8-239">El valor se borra del campo **Fecha y hora de finalización** y se desmarca la casilla **Completado**.</span><span class="sxs-lookup"><span data-stu-id="999c8-239">The value is cleared from the **Completion date and time** field, and the **Completed** check box is cleared.</span></span>
1. <span data-ttu-id="999c8-240">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="999c8-240">Close the page.</span></span>

<span data-ttu-id="999c8-241">Ahora puede realizar modificaciones o actualizaciones adicionales a la corrección.</span><span class="sxs-lookup"><span data-stu-id="999c8-241">You can now make additional edits or updates to the correction.</span></span> <span data-ttu-id="999c8-242">Cuando haya terminado, puede volver a marcar la corrección como completada.</span><span class="sxs-lookup"><span data-stu-id="999c8-242">When you've finished, you can mark the correction as completed again.</span></span>

## <a name="close-a-nonconformance"></a><span data-ttu-id="999c8-243">Cierre de una disconformidad</span><span class="sxs-lookup"><span data-stu-id="999c8-243">Close a nonconformance</span></span>

<span data-ttu-id="999c8-244">Para cerrar una disconformidad, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="999c8-244">To close a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="999c8-245">Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Pedidos de calidad**.</span><span class="sxs-lookup"><span data-stu-id="999c8-245">Go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>
1. <span data-ttu-id="999c8-246">Seleccione un pedido de calidad en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="999c8-246">Select a quality order in the grid.</span></span>
1. <span data-ttu-id="999c8-247">En el panel de acciones, seleccione **Consultas \> Disconformidades**.</span><span class="sxs-lookup"><span data-stu-id="999c8-247">On the Action Pane, select **Inquiries \> Non conformances**.</span></span>
1. <span data-ttu-id="999c8-248">En la página **Disconformidades**, seleccione la disconformidad del objetivo en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="999c8-248">On the **Non conformances** page, select the target nonconformance in the grid.</span></span>
1. <span data-ttu-id="999c8-249">En el panel de acciones, seleccione **Funciones \> Cerrar disconformidad**.</span><span class="sxs-lookup"><span data-stu-id="999c8-249">On the Action Pane, select **Functions \> Close non conformance**.</span></span>
1. <span data-ttu-id="999c8-250">Se le pedirá que confirme su selección.</span><span class="sxs-lookup"><span data-stu-id="999c8-250">You're prompted to confirm your selection.</span></span> <span data-ttu-id="999c8-251">Seleccione **Sí** para continuar.</span><span class="sxs-lookup"><span data-stu-id="999c8-251">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="999c8-252">Cierre las páginas.</span><span class="sxs-lookup"><span data-stu-id="999c8-252">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="999c8-253">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="999c8-253">Additional resources</span></span>

- [<span data-ttu-id="999c8-254">Información general de la administración de la calidad</span><span class="sxs-lookup"><span data-stu-id="999c8-254">Quality management overview</span></span>](../quality-management-processes.md)
- [<span data-ttu-id="999c8-255">Habilitar la gestión de la calidad y las disconformidades</span><span class="sxs-lookup"><span data-stu-id="999c8-255">Enable quality and nonconformance management</span></span>](../enable-quality-management.md)
- [<span data-ttu-id="999c8-256">Trabajadores responsables de aprobar disconformidades</span><span class="sxs-lookup"><span data-stu-id="999c8-256">Workers responsible for approving nonconformances</span></span>](../quality-responsible-workers.md)
- [<span data-ttu-id="999c8-257">Zonas de cuarentena para disconformidades</span><span class="sxs-lookup"><span data-stu-id="999c8-257">Quarantine zones for nonconformances</span></span>](../quality-quarantine-zones.md)
- [<span data-ttu-id="999c8-258">Tipos de diagnóstico de disconformidades</span><span class="sxs-lookup"><span data-stu-id="999c8-258">Diagnostic types for nonconformances</span></span>](../quality-diagnostic-types.md)
- [<span data-ttu-id="999c8-259">Cargos de calidad para disconformidades</span><span class="sxs-lookup"><span data-stu-id="999c8-259">Quality charges for nonconformances</span></span>](../quality-charges.md)
- [<span data-ttu-id="999c8-260">Operaciones para disconformidades</span><span class="sxs-lookup"><span data-stu-id="999c8-260">Operations for nonconformances</span></span>](../quality-operations.md)
- [<span data-ttu-id="999c8-261">Administración de la calidad para procesos de almacén</span><span class="sxs-lookup"><span data-stu-id="999c8-261">Quality management for warehouse processes</span></span>](../quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
