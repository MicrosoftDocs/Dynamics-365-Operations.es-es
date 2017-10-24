---
title: "Directivas de trabajo de almacén"
description: "Control de las directivas de trabajo de almacén si el trabajo del almacén se crea mediante procesos de almacén en la fabricación, en función de tipo de pedido del trabajo, la ubicación de inventario y el producto."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSWorkPolicy
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 196561
ms.assetid: cbf48ec6-1836-48d5-ad66-a9b534af1786
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: ec7dd3b91851729e866bc90ca85a118839f9d71d
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="warehouse-work-policies"></a><span data-ttu-id="1fd5c-103">Directivas de trabajo de almacén</span><span class="sxs-lookup"><span data-stu-id="1fd5c-103">Warehouse work policies</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="1fd5c-104">El control de las directivas de trabajo de almacén en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition si el trabajo del almacén se crea mediante procesos de almacén en la fabricación, en función de tipo de pedido del trabajo, la ubicación de inventario y el producto.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-104">Warehouse work policies in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition control whether warehouse work is created by warehouse processes in manufacturing, based on work order type, inventory location, and product.</span></span>

<span data-ttu-id="1fd5c-105">Esta directiva de trabajo controla si el trabajo del almacén se ha creado para los procesos de almacén en la fabricación.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-105">This work policy controls whether warehouse work is created for warehouse processes in manufacturing.</span></span> <span data-ttu-id="1fd5c-106">Puede configurar la directiva de trabajo mediante una combinación de **tipos de pedido de trabajo**, la **ubicación del inventario**, y un **producto**.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-106">You can set up the work policy by using a combination of **work order types**, an **inventory location**, and a **product**.</span></span> <span data-ttu-id="1fd5c-107">Por ejemplo, se ha informado a la ubicación de salida 001 que el producto L0101 ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-107">For example, product L0101 is reported as finished to output location 001.</span></span> <span data-ttu-id="1fd5c-108">El producto terminado se consume más adelante en otro pedido de producción en la ubicación de salida 001.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-108">The finished good is later consumed in another production order at output location 001.</span></span> <span data-ttu-id="1fd5c-109">En este caso, puede configurar una directiva de trabajo para evitar que el trabajo para productos terminados se deseche por haberse creado cuando se informa a la ubicación de salida 001 que el producto L0101 ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-109">In this case, you can set up a work policy to prevent the work for finished goods put-away from being created when you report product L0101 as finished to output location 001.</span></span> <span data-ttu-id="1fd5c-110">La directiva de trabajo es una entidad individual que puede ser descrita mediante la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="1fd5c-110">The work policy is an individual entity that can be described through the following information:</span></span>

-   <span data-ttu-id="1fd5c-111">**Nombre de la directiva de trabajo**(el identificador único de la directiva de trabajo)</span><span class="sxs-lookup"><span data-stu-id="1fd5c-111">**Work policy name** (the unique identifier of the work policy)</span></span>
-   <span data-ttu-id="1fd5c-112">**Tipos de pedido de trabajo** y **Método de creación de trabajo**</span><span class="sxs-lookup"><span data-stu-id="1fd5c-112">**Work order types** and **Work creation method**</span></span>
-   <span data-ttu-id="1fd5c-113">**Ubicaciones del inventario**</span><span class="sxs-lookup"><span data-stu-id="1fd5c-113">**Inventory locations**</span></span>
-   <span data-ttu-id="1fd5c-114">**Productos**</span><span class="sxs-lookup"><span data-stu-id="1fd5c-114">**Products**</span></span>

## <a name="work-order-types"></a><span data-ttu-id="1fd5c-115">Tipos de pedido de trabajo</span><span class="sxs-lookup"><span data-stu-id="1fd5c-115">Work order types</span></span>
<span data-ttu-id="1fd5c-116">Puede seleccionar los siguientes tipos de pedido de trabajo:</span><span class="sxs-lookup"><span data-stu-id="1fd5c-116">You can select the following work order types:</span></span>

-   <span data-ttu-id="1fd5c-117">Ubicación de bienes terminados</span><span class="sxs-lookup"><span data-stu-id="1fd5c-117">Finished goods put away</span></span>
-   <span data-ttu-id="1fd5c-118">Ubicación de coproducto y producto derivado</span><span class="sxs-lookup"><span data-stu-id="1fd5c-118">Co-product and by-product put away</span></span>
-   <span data-ttu-id="1fd5c-119">Picking de materia prima</span><span class="sxs-lookup"><span data-stu-id="1fd5c-119">Raw material picking</span></span>

<span data-ttu-id="1fd5c-120">El campo de **Método de creación de trabajo** tiene el valor **Nunca**.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-120">The **Work creation method** field has the value **Never**.</span></span> <span data-ttu-id="1fd5c-121">Este valor indica que la directiva de trabajo evitará que se genere el trabajo del almacén para el tipo de pedido de trabajo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-121">This value indicates that the work policy will prevent warehouse work from being created for the selected work order type.</span></span>

## <a name="inventory-locations"></a><span data-ttu-id="1fd5c-122">Ubicaciones del inventario</span><span class="sxs-lookup"><span data-stu-id="1fd5c-122">Inventory locations</span></span>
<span data-ttu-id="1fd5c-123">Puede seleccionar una ubicación para la que se aplique la directiva de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-123">You can select a location that the work policy applies to.</span></span> <span data-ttu-id="1fd5c-124">Si no se asocia ninguna ubicación a una directiva de trabajo, la directiva de trabajo no se aplica a ningún proceso.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-124">If no location is associated with a work policy, the work policy doesn’t apply to any processes.</span></span> <span data-ttu-id="1fd5c-125">En la página **Ubicaciones**, puede activar o cancelar la selección de la directiva de trabajo para una ubicación concreta.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-125">On the **Locations** page, you can also select or cancel the selection of the work policy for a specific location.</span></span>

## <a name="products"></a><span data-ttu-id="1fd5c-126">Productos</span><span class="sxs-lookup"><span data-stu-id="1fd5c-126">Products</span></span>
<span data-ttu-id="1fd5c-127">Puede seleccionar un producto para el que se aplique la directiva de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-127">You can select a product that the work policy applies to.</span></span> <span data-ttu-id="1fd5c-128">Puede aplicar la directiva de trabajo a todos los productos o productos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-128">You can apply the work policy to either all products or selected products.</span></span>

## <a name="example"></a><span data-ttu-id="1fd5c-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1fd5c-129">Example</span></span>
<span data-ttu-id="1fd5c-130">En el siguiente ejemplo, hay dos pedidos de producción, PRD-001 y PRD-00*2*.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-130">In the following example, there are two production orders, PRD-001 and PRD-00*2*.</span></span> <span data-ttu-id="1fd5c-131">El pedido de producción PRD-001 tiene una operación llamada **Montaje**, en la que el producto SC1 se notifica a la ubicación O1 como terminado.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-131">Production order PRD-001 has an operation that is named **Assembly**, where product SC1 is being reported as finished to location O1.</span></span> <span data-ttu-id="1fd5c-132">El pedido de producción PRD-002 tiene una operación llamada **Pintura** y consume el producto SC1 de la ubicación O1.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-132">Production order PRD-002 has an operation that is named **Painting** and consumes product SC1 from location O1.</span></span> <span data-ttu-id="1fd5c-133">El pedido de producción PRD-002 también consume la materia prima RM1 de la ubicación O1.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-133">Production order PRD-002 also consumes raw material RM1 from location O1.</span></span> <span data-ttu-id="1fd5c-134">RM1 se almacena en la ubicación del almacén BULK-001 y el trabajo del almacén lo escogerá como recogida de materia prima a la ubicación O1.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-134">RM1 is stored in warehouse location BULK-001 and will be picked to location O1 by warehouse work for raw material picking.</span></span> <span data-ttu-id="1fd5c-135">El trabajo de recogida se genera cuando se lanza la producción PRD-002.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-135">The picking work is generated when production PRD-002 is released.</span></span> 

<span data-ttu-id="1fd5c-136">[![Directivas de trabajo de almacén](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png)</span><span class="sxs-lookup"><span data-stu-id="1fd5c-136">[![Warehouse work policies](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png)</span></span> 

<span data-ttu-id="1fd5c-137">Cuando desee configurar una directiva de trabajo del almacén para este escenario, debe tener en cuenta la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="1fd5c-137">When you plan to configure a warehouse work policy for this scenario, you should consider the following information:</span></span>

-   <span data-ttu-id="1fd5c-138">El trabajo del almacén para el almacenaje del producto terminado no es necesario cuando informa de que el producto SC1 se ha completado del pedido de producción PRD-001 a la ubicación O1.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-138">Warehouse work for finished goods put-away isn’t required when you report product SC1 as finished from production order PRD-001 to location O1.</span></span> <span data-ttu-id="1fd5c-139">Esto sucede porque la operación **Pintura** del pedido de producción PRD-002 consume el SC1 en la misma ubicación.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-139">This is because the **Painting** operation for production order PRD-002 consumes SC1 at the same location.</span></span>
-   <span data-ttu-id="1fd5c-140">El trabajo de almacén para la recogida de la materia prima se requiere para mover la materia prima RM1 de la ubicación del almacén BULK-001 a la ubicación O1.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-140">Warehouse work for raw material picking is required in order to move raw material RM1 from warehouse location BULK-001 to location O1.</span></span>

<span data-ttu-id="1fd5c-141">A continuación se muestra un ejemplo de una directiva de trabajo que puede configurar, en función de estas cuestiones.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-141">Here is an example of the work policy that you can set up, based on these considerations.</span></span>

|                                         |                                                       |
|-----------------------------------------|-------------------------------------------------------|
|<span data-ttu-id="1fd5c-142">**Nombre de directiva de trabajo**</span><span class="sxs-lookup"><span data-stu-id="1fd5c-142">**Work policy name**</span></span><br>                 |<span data-ttu-id="1fd5c-143">**Tipos de pedido de trabajo**</span><span class="sxs-lookup"><span data-stu-id="1fd5c-143">**Work order types**</span></span><br>                               |
| <span data-ttu-id="1fd5c-144">Sin almacenaje 01     \`</span><span class="sxs-lookup"><span data-stu-id="1fd5c-144">No put away 01     \`</span></span>                    |<span data-ttu-id="1fd5c-145">- Almacenaje de bienes terminados</span><span class="sxs-lookup"><span data-stu-id="1fd5c-145">- Finished good put away</span></span><br>                           |
|                                         |<span data-ttu-id="1fd5c-146">**Ubicaciones**</span><span class="sxs-lookup"><span data-stu-id="1fd5c-146">**Locations**</span></span><br>                                      |
|                                         |<span data-ttu-id="1fd5c-147">- O1</span><span class="sxs-lookup"><span data-stu-id="1fd5c-147">- O1</span></span>   |                                               |
|                                         |<span data-ttu-id="1fd5c-148">**Productos**</span><span class="sxs-lookup"><span data-stu-id="1fd5c-148">**Products**</span></span> <br>                                      |
|                                         |<span data-ttu-id="1fd5c-149">- SC1</span><span class="sxs-lookup"><span data-stu-id="1fd5c-149">- SC1</span></span>                                                  |

<span data-ttu-id="1fd5c-150">Los siguientes procedimientos proporcionan instrucciones detalladas sobre cómo configurar la directiva de trabajo del almacén para esta situación.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-150">The following procedures provide step-by-step instructions about how to set up the warehouse work policy for this scenario.</span></span> <span data-ttu-id="1fd5c-151">También describe un ejemplo de la configuración que muestra cómo informar de un pedido de producción que se ha completado a una ubicación no controlada por matrícula.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-151">A sample setup showing how to report a production order as finished to a location that isn’t license plate–controlled is also described.</span></span>

## <a name="set-up-a-warehouse-work-policy"></a><span data-ttu-id="1fd5c-152">Configurar una directiva de trabajo de almacén</span><span class="sxs-lookup"><span data-stu-id="1fd5c-152">Set up a warehouse work policy</span></span>
<span data-ttu-id="1fd5c-153">Los procesos de almacén no siempre incluyen trabajo de almacén.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-153">Warehouse processes don’t always include warehouse work.</span></span> <span data-ttu-id="1fd5c-154">Al definir una directiva de trabajo, puede evitar la creación de trabajo para picking de materia prima y ubicación de bienes terminados para un conjunto de productos en ubicaciones específicas.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-154">By defining a work policy, you can prevent the creation of work for raw material picking and put-away of finished goods for a set of products at specific locations.</span></span> <span data-ttu-id="1fd5c-155">Para crear este procedimiento se utiliza la empresa de datos de prueba USMF.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-155">The USMF demo data company was used to create this procedure.</span></span> 

<span data-ttu-id="1fd5c-156">PASOS (21)</span><span class="sxs-lookup"><span data-stu-id="1fd5c-156">STEPS (21)</span></span>

|     |                                                                            |
|-----|----------------------------------------------------------------------------|
| <span data-ttu-id="1fd5c-157">1.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-157">1.</span></span>  | <span data-ttu-id="1fd5c-158">Vaya a Gestión de almacenes &gt; Configurar &gt; Trabajo &gt; Directivas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-158">Go to Warehouse management &gt; Setup &gt; Work &gt; Work policies.</span></span>        |
| <span data-ttu-id="1fd5c-159">2.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-159">2.</span></span>  | <span data-ttu-id="1fd5c-160">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-160">Click New.</span></span>                                                                 |
| <span data-ttu-id="1fd5c-161">3.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-161">3.</span></span>  | <span data-ttu-id="1fd5c-162">En el campo Nombre de directiva de trabajo, escriba "Ningún trabajo de ubicación".</span><span class="sxs-lookup"><span data-stu-id="1fd5c-162">In the Work policy name field, type 'No put-away work'.</span></span>                    |
| <span data-ttu-id="1fd5c-163">4.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-163">4.</span></span>  | <span data-ttu-id="1fd5c-164">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-164">Click Save.</span></span>                                                                |
| <span data-ttu-id="1fd5c-165">5.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-165">5.</span></span>  | <span data-ttu-id="1fd5c-166">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-166">Click Add.</span></span>                                                                 |
| <span data-ttu-id="1fd5c-167">6.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-167">6.</span></span>  | <span data-ttu-id="1fd5c-168">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-168">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="1fd5c-169">7.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-169">7.</span></span>  | <span data-ttu-id="1fd5c-170">En el campo Tipo de pedido de trabajo, seleccione "Ubicación de bienes terminados".</span><span class="sxs-lookup"><span data-stu-id="1fd5c-170">In the Work order type field, select 'Finished goods put away'.</span></span>            |
| <span data-ttu-id="1fd5c-171">8.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-171">8.</span></span>  | <span data-ttu-id="1fd5c-172">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-172">Click Add.</span></span>                                                                 |
| <span data-ttu-id="1fd5c-173">9.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-173">9.</span></span>  | <span data-ttu-id="1fd5c-174">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-174">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="1fd5c-175">10.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-175">10.</span></span> | <span data-ttu-id="1fd5c-176">En el campo Tipo de pedido de trabajo, seleccione "Ubicación de coproducto y producto derivado".</span><span class="sxs-lookup"><span data-stu-id="1fd5c-176">In the Work order type field, select 'Co-product and by-product put away'.</span></span> |
| <span data-ttu-id="1fd5c-177">11.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-177">11.</span></span> | <span data-ttu-id="1fd5c-178">Expanda la sección Ubicaciones del inventario.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-178">Expand the Inventory locations section.</span></span>                                    |
| <span data-ttu-id="1fd5c-179">12.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-179">12.</span></span> | <span data-ttu-id="1fd5c-180">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-180">Click Add.</span></span>                                                                 |
| <span data-ttu-id="1fd5c-181">13.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-181">13.</span></span> | <span data-ttu-id="1fd5c-182">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-182">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="1fd5c-183">14.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-183">14.</span></span> | <span data-ttu-id="1fd5c-184">En la lista Almacén, especifique “51".</span><span class="sxs-lookup"><span data-stu-id="1fd5c-184">In the Warehouse list, enter '51'.</span></span>                                         |
| <span data-ttu-id="1fd5c-185">15.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-185">15.</span></span> | <span data-ttu-id="1fd5c-186">En el campo Ubicación, especifique o seleccione ·"001".</span><span class="sxs-lookup"><span data-stu-id="1fd5c-186">In the Location field, enter or select '001'.</span></span>                              |
| <span data-ttu-id="1fd5c-187">16.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-187">16.</span></span> | <span data-ttu-id="1fd5c-188">Expanda la sección Productos.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-188">Expand the Products section.</span></span>                                               |
| <span data-ttu-id="1fd5c-189">17.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-189">17.</span></span> | <span data-ttu-id="1fd5c-190">En el campo Selección de productos, seleccione "Seleccionado".</span><span class="sxs-lookup"><span data-stu-id="1fd5c-190">In the Product selection field, select 'Selected'.</span></span>                         |
| <span data-ttu-id="1fd5c-191">18.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-191">18.</span></span> | <span data-ttu-id="1fd5c-192">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-192">Click Add.</span></span>                                                                 |
| <span data-ttu-id="1fd5c-193">19.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-193">19.</span></span> | <span data-ttu-id="1fd5c-194">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-194">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="1fd5c-195">20.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-195">20.</span></span> | <span data-ttu-id="1fd5c-196">En el campo Número de artículo, especifique o seleccione "L0101".</span><span class="sxs-lookup"><span data-stu-id="1fd5c-196">In the Item number field, enter or select 'L0101'.</span></span>                         |
| <span data-ttu-id="1fd5c-197">21.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-197">21.</span></span> | <span data-ttu-id="1fd5c-198">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-198">Click Save.</span></span>                                                                |

## <a name="report-a-production-order-as-finished-to-a-location-that-isnt-license-platecontrolled"></a><span data-ttu-id="1fd5c-199">Informar de una orden de producción como terminada a una ubicación no controlada por matrícula.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-199">Report a production order as finished to a location that isn’t license plate–controlled</span></span>
<span data-ttu-id="1fd5c-200">Este procedimiento muestra un ejemplo de notificación de producto finalizado a una ubicación no controlada por matrícula.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-200">This procedure shows an example of reporting as finished to a location that isn't license plate–controlled.</span></span> <span data-ttu-id="1fd5c-201">Una directiva aplicable de trabajo es el requisito previo para esta tarea.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-201">An applicable work policy is the prerequisite for this task.</span></span> <span data-ttu-id="1fd5c-202">El procedimiento anterior muestra la configuración de la directiva de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-202">The previous procedure shows the setup of the work policy.</span></span> 

<span data-ttu-id="1fd5c-203">PASOS (25)</span><span class="sxs-lookup"><span data-stu-id="1fd5c-203">STEPS (25)</span></span>

<table>
<tbody>
<tr>
<td colspan="3"><span data-ttu-id="1fd5c-204"><strong>Subtarea: configurar una ubicación de salida.</strong></span><span class="sxs-lookup"><span data-stu-id="1fd5c-204"><strong>Sub-task: Set up an output location.</strong></span></span></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td><span data-ttu-id="1fd5c-205">Vaya a Administración de la organización &gt; Recursos &gt; Grupos de recursos.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-205">Go to Organization administration &gt; Resources &gt; Resource groups.</span></span></td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td><span data-ttu-id="1fd5c-206">En la lista, seleccione el grupo de recursos "5102".</span><span class="sxs-lookup"><span data-stu-id="1fd5c-206">In the list, select resource group '5102'.</span></span></td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td><span data-ttu-id="1fd5c-207">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-207">Click Edit.</span></span></td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td><span data-ttu-id="1fd5c-208">En el campo Almacén de salida, especifique "51".</span><span class="sxs-lookup"><span data-stu-id="1fd5c-208">In the Output warehouse field, enter '51'.</span></span></td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td><span data-ttu-id="1fd5c-209">En el campo Ubicación de salida, especifique "001".</span><span class="sxs-lookup"><span data-stu-id="1fd5c-209">In the Output location field, enter '001'.</span></span></td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td><span data-ttu-id="1fd5c-210">La ubicación 001 no es una ubicación controlada mediante matrículas de entidad de almacén.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-210">Location 001 isn't a license plate–controlled location.</span></span> <span data-ttu-id="1fd5c-211">Puede configurar una ubicación de salida que no sea de matrículas de entidad de almacén si existe una directiva aplicable de trabajo para la ubicación.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-211">You can set up a non–license plate output location only if an applicable work policy exists for the location.</span></span></td>
</tr>
<tr>
<td colspan="3"><span data-ttu-id="1fd5c-212"><strong>Subtarea: crear un pedido de producción y notificarlo como terminado.</strong></span><span class="sxs-lookup"><span data-stu-id="1fd5c-212"><strong>Sub-task: Create a production order and report it as finished.</strong></span></span></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td><span data-ttu-id="1fd5c-213">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-213">Close the page.</span></span></td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td><span data-ttu-id="1fd5c-214">Vaya a Control de producción &gt; Pedidos de producción &gt; Todos los pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-214">Go to Production control &gt; Production orders &gt; All production orders.</span></span></td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td><span data-ttu-id="1fd5c-215">Haga clic en Nuevo pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-215">Click New production order.</span></span></td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td><span data-ttu-id="1fd5c-216">En el campo Número de artículo, especifique "L0101".</span><span class="sxs-lookup"><span data-stu-id="1fd5c-216">In the Item number field, enter 'L0101'.</span></span></td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td><span data-ttu-id="1fd5c-217">Haga clic en Crear.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-217">Click Create.</span></span></td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td><span data-ttu-id="1fd5c-218">En el panel de acciones, haga clic en Pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-218">On the Action Pane, click Production order.</span></span></td>
</tr>
<tr>
<td></td>
<td>7.</td>
<td><span data-ttu-id="1fd5c-219">Haga clic en Estimación.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-219">Click Estimate.</span></span></td>
</tr>
<tr>
<td></td>
<td>8.</td>
<td><span data-ttu-id="1fd5c-220">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="1fd5c-220">Click OK.</span></span></td>
</tr>
<tr>
<td></td>
<td>9.</td>
<td><span data-ttu-id="1fd5c-221">Haga clic en Inicio.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-221">Click Start.</span></span></td>
</tr>
<tr>
<td></td>
<td>10.</td>
<td><span data-ttu-id="1fd5c-222">Haga clic en la ficha General.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-222">Click the General tab.</span></span></td>
</tr>
<tr>
<td></td>
<td>11.</td>
<td><span data-ttu-id="1fd5c-223">En el campo Consumo automático de L. MAT, seleccione "Nunca".</span><span class="sxs-lookup"><span data-stu-id="1fd5c-223">In the Automatic BOM consumption field, select 'Never'.</span></span></td>
</tr>
<tr>
<td></td>
<td>12.</td>
<td><span data-ttu-id="1fd5c-224">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="1fd5c-224">Click OK.</span></span></td>
</tr>
<tr>
<td></td>
<td>13.</td>
<td><span data-ttu-id="1fd5c-225">Haga clic en Notificar como terminado.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-225">Click Report as finished.</span></span></td>
</tr>
<tr>
<td></td>
<td>14.</td>
<td><span data-ttu-id="1fd5c-226">Haga clic en la ficha General.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-226">Click the General tab.</span></span></td>
</tr>
<tr>
<td></td>
<td>15.</td>
<td><span data-ttu-id="1fd5c-227">Seleccione Sí en el campo Aceptar error.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-227">Select Yes in the Accept error field.</span></span></td>
</tr>
<tr>
<td></td>
<td>16.</td>
<td><span data-ttu-id="1fd5c-228">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="1fd5c-228">Click OK.</span></span></td>
</tr>
<tr>
<td></td>
<td>17.</td>
<td><span data-ttu-id="1fd5c-229">En el panel de acciones, haga clic en Almacén.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-229">On the Action Pane, click Warehouse.</span></span></td>
</tr>
<tr>
<td></td>
<td>18.</td>
<td><span data-ttu-id="1fd5c-230">Haga clic en Detalles del trabajo.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-230">Click Work details.</span></span></td>
</tr>
<tr>
<td></td>
<td>19.</td>
<td><span data-ttu-id="1fd5c-231">Cuando el pedido de producción se ha notificado como finalizado, no se ha generado ningún trabajo para ubicación.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-231">When the production order was reported as finished, no work was generated for put-away.</span></span> <span data-ttu-id="1fd5c-232">Esto ocurre porque se define una directiva de trabajo que impide que el trabajo se genere cuando el producto L0101 se notifique como finalizado para la ubicación 001.</span><span class="sxs-lookup"><span data-stu-id="1fd5c-232">This occurs because a work policy is defined that prevents work from being generated when product L0101 is reported as finished to location 001.</span></span></td>
</tr>
</tbody>
</table>




