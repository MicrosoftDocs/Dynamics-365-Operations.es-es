---
title: Grupos de órdenes de trabajo
description: En este tema se describe cómo trabajar con grupos de órdenes de trabajo en administración de activos.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderTablePoolPart, EntAssetWorkOrderPoolReferenceInfoPart, EntAssetWorkOrderPool, EntAssetWorkOrderPoolPreviewPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: afea5b8d0f958c3ab53d6cef8c9a0e9030d7c67b
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "5017526"
---
# <a name="work-order-pools"></a><span data-ttu-id="bb545-103">Grupos de órdenes de trabajo</span><span class="sxs-lookup"><span data-stu-id="bb545-103">Work order pools</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="bb545-104">Puede usar conjuntos de órdenes de trabajo para agrupar órdenes de trabajo que tienen algo en común.</span><span class="sxs-lookup"><span data-stu-id="bb545-104">You can use work order pools to group work orders that have something in common.</span></span> <span data-ttu-id="bb545-105">A continuación se muestran algunos ejemplos para los que puede crear grupos de órdenes de trabajo:</span><span class="sxs-lookup"><span data-stu-id="bb545-105">Here are some examples of things that you can create  work order pools for:</span></span>

- <span data-ttu-id="bb545-106">Equipos de trabajo; por ejemplo, equipo de mantenimiento A, equipo de mantenimiento B</span><span class="sxs-lookup"><span data-stu-id="bb545-106">Work crews, for example, Maintenance Crew A or Maintenance Crew B</span></span>  

- <span data-ttu-id="bb545-107">Aptitudes profesionales, como electricistas o fontaneros</span><span class="sxs-lookup"><span data-stu-id="bb545-107">Professional skills, such as electricians or plumbers</span></span>  

- <span data-ttu-id="bb545-108">Ubicaciones físicas</span><span class="sxs-lookup"><span data-stu-id="bb545-108">Physical locations</span></span>  

- <span data-ttu-id="bb545-109">Programaciones horarias, como semanas u otros períodos</span><span class="sxs-lookup"><span data-stu-id="bb545-109">Time schedules, such as weeks or other periods</span></span>  

<span data-ttu-id="bb545-110">Según necesite, puede colocar una orden de trabajo en varios grupos de órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bb545-110">As you require, you can put one work order in multiple work order pools.</span></span>


## <a name="create-a-work-order-pool"></a><span data-ttu-id="bb545-111">Crear un grupo de órdenes de trabajo</span><span class="sxs-lookup"><span data-stu-id="bb545-111">Create a work order pool</span></span>

<span data-ttu-id="bb545-112">En la página de lista **Todos los grupos de órdenes de trabajo** o **Grupo de órdenes de trabajo activas**, puede obtener una visión general de los grupos de órdenes de trabajo y crear nuevos grupos.</span><span class="sxs-lookup"><span data-stu-id="bb545-112">On the **All work order pools** or **Active work order pools** list page, you can get an overview of your work order pools and create new pools.</span></span>

1. <span data-ttu-id="bb545-113">Seleccione **Administración de activos** > **Común** > **Grupos de órdenes de trabajo** > **Todos los grupos de órdenes de trabajo** o **Grupos de órdenes de trabajo activas**.</span><span class="sxs-lookup"><span data-stu-id="bb545-113">Select **Asset management** > **Common** > **Work order pools** > **All work order pools** or **Active work order pools**.</span></span>

2. <span data-ttu-id="bb545-114">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="bb545-114">Select **New**.</span></span>

3. <span data-ttu-id="bb545-115">En el campo **Conjunto**, especifique un id. para el grupo de órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bb545-115">In the **Pool** field, enter an ID for the work order pool.</span></span>

4. <span data-ttu-id="bb545-116">Escriba un nombre en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="bb545-116">the **Name** field, enter a name.</span></span>

5. <span data-ttu-id="bb545-117">Establezca la opción **Activo** en **Sí** para indicar que el grupo de órdenes de trabajo está activo.</span><span class="sxs-lookup"><span data-stu-id="bb545-117">Set the **Active** option to **Yes** to indicate that the work order pool is active.</span></span>

6. <span data-ttu-id="bb545-118">Establezca la opción **Eliminar relaciones de órdenes de trabajo** en **Sí** si desea que las órdenes de trabajo automáticamente se quiten del grupo de órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bb545-118">Set the **Delete work order relations** option to **Yes** if work orders should automatically be removed from the work order pool.</span></span>

7. <span data-ttu-id="bb545-119">En el campo **Eliminar estado de ciclo de vida**, seleccione el estado del ciclo de vida de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bb545-119">In the **Delete lifecycle state** field, select the work order lifecycle state.</span></span> <span data-ttu-id="bb545-120">Por ejemplo, el estado del ciclo de vida de pedido de trabajo para completar un pedido de trabajo se puede establecer para eliminar automáticamente relaciones con grupos de órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bb545-120">For example, the work order lifecycle state for completing a work order could be set to automatically delete relations to work order pools.</span></span>

    <span data-ttu-id="bb545-121">Puede empezar a agregar órdenes de trabajo a su grupo de órdenes de trabajo inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="bb545-121">You can start adding work orders to your work order pool right away.</span></span>

8. <span data-ttu-id="bb545-122">En la ficha desplegable **Órdenes de trabajo**, seleccione **Agregar línea**.</span><span class="sxs-lookup"><span data-stu-id="bb545-122">On the **Work orders** FastTab, select **Add line**.</span></span>

9. <span data-ttu-id="bb545-123">Seleccione una orden de trabajo en el campo **Orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="bb545-123">In the **Work order** field, select a work order.</span></span> <span data-ttu-id="bb545-124">Los campos relacionados se actualizarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="bb545-124">The related fields are automatically updated.</span></span>

10. <span data-ttu-id="bb545-125">Repita los pasos del 8 al 9 para agregar más órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bb545-125">Repeat steps 8 through 9 to add more work orders.</span></span>

11. <span data-ttu-id="bb545-126">Si las órdenes de trabajo que agregó deben realizarse en un orden específico, en el campo **Orden**, puede escribir los números **1**, **2**, **3**, etc., para especificar ese orden.</span><span class="sxs-lookup"><span data-stu-id="bb545-126">If the work orders that you added should be done in a specific order, in the **Sort order** field, you can enter the numbers **1**, **2**, **3**, and so on, to specify that order.</span></span>

12. <span data-ttu-id="bb545-127">Para ver una lista de todas las órdenes de trabajo que se incluyen en el grupo de órdenes de trabajo, en el panel de acciones, en la pestaña **Grupo de órdenes de trabajo**, en el grupo de **ver grupo de órdenes de trabajo relacionado**, seleccione **Órdenes de trabajo** para abrir la página de lista **Todas las órdenes de trabajo** .</span><span class="sxs-lookup"><span data-stu-id="bb545-127">To view a list of all the work orders that are included in the work order pool, on the Action Pane, on the **Work order pool** tab, in the **View work order pool related** group, select **Work orders** to open the **All work orders** list page.</span></span>

13. <span data-ttu-id="bb545-128">Para calcular y ver la carga de capacidad para el programa de mantenimiento, las órdenes de trabajo no programadas y las órdenes de trabajo programadas, en el panel de acciones, en la pestaña **Grupo de órdenes de trabajo**, en el grupo de **ver grupo de órdenes de trabajo relacionado**, seleccione **Carga de capacidad** para abrir el diálogo **Calcular carga de capacidad** .</span><span class="sxs-lookup"><span data-stu-id="bb545-128">To calculate and view capacity load for the maintenance schedule, unscheduled work orders, and scheduled work orders, on the Action Pane, on the **Work order pool** tab, in the **View work order pool related** group, select **Capacity load** to open the **Calculate capacity load** dialog.</span></span>

14. <span data-ttu-id="bb545-129">Para calcular y ver las previsiones para artículos (piezas de repuesto y otros artículos requeridos) que son necesarios para el programa de mantenimiento, las órdenes de trabajo no programadas y las órdenes de trabajo programadas, en el panel de acciones, en la pestaña **Grupo de órdenes de trabajo**, en el grupo de **ver grupo de órdenes de trabajo relacionado**, seleccione **Previsión de artículos** para abrir el diálogo **Calcular previsión de artículo**.</span><span class="sxs-lookup"><span data-stu-id="bb545-129">To calculate and view forecasts for items (spare parts and other required items) that are related to maintenance schedule, unscheduled work orders, and scheduled work orders, on the Action Pane, on the **Work order pool** tab, in the **View work order pool related** group, select **Item forecast** to open the **Calculate item forecast** dialog.</span></span>

15. <span data-ttu-id="bb545-130">Para ver una lista de las solicitudes de compra que están relacionadas con las órdenes de trabajo del grupo de órdenes de trabajo, en el panel de acciones, en la pestaña **Grupo de órdenes de trabajo**, en el grupo **Adquisición**, seleccione **Solicitud de compra de orden de trabajo** para abrir la página de lista **Solicitud de compra de orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="bb545-130">To view a list of purchase requisitions that are related to the work orders in the work order pool, on the Action Pane, on the **Work order pool** tab, in the **Procurement** group, select **Work order purchase requisition** to open the **Work order purchase requisition** list page.</span></span>

16. <span data-ttu-id="bb545-131">Para ver una lista de las órdenes de compra que están relacionadas con las órdenes de trabajo del grupo de órdenes de trabajo, en el panel de acciones, en la pestaña **Grupo de órdenes de trabajo**, en el grupo **Adquisición**, seleccione **Compra de orden de trabajo** para abrir la página de lista **Compra de orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="bb545-131">To view a list of purchase orders that are related to the work orders in the work order pool, on the Action Pane, on the **Work order pool** tab, in the **Procurement** group, select **Work order purchase** to open the **Work order purchase** list page.</span></span>

>[!NOTE]
><span data-ttu-id="bb545-132">Cuando un conjunto de órdenes de trabajo ya no es relevante para la planificación de trabajo, establezca la opción **Activo** de dicho grupo en **No** en la vista de lista de la página **Grupo de órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="bb545-132">When a work order pool is no longer relevant to your work planning, set the **Active** option for that pool to **No** in the list view of the **Work order pool** page.</span></span>

<span data-ttu-id="bb545-133">Para eliminar todas las líneas de orden de trabajo, establezca la opción **Eliminar relaciones de órdenes de trabajo** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="bb545-133">To delete all worker order lines, set the **Delete work order relations** option to **Yes**.</span></span> <span data-ttu-id="bb545-134">Esta opción resulta útil si, por ejemplo, desea crear un grupo vacío que pueda usar posteriormente en otras órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bb545-134">This option is useful if, for example, you want to create an empty pool that you can use later for other work orders.</span></span> <span data-ttu-id="bb545-135">Cuando esté preparado para usar el grupo de órdenes de trabajo para crear relaciones de órdenes de trabajo nuevas posteriormente, recuerde establecer la opción **Eliminar relaciones de órdenes de trabajo** en **No**.</span><span class="sxs-lookup"><span data-stu-id="bb545-135">When you're ready to use the work order pool to create new work order relations later, remember to set the **Delete work order relations** option to **No**.</span></span>

<span data-ttu-id="bb545-136">La ilustración siguiente muestra un ejemplo de la página de lista **Grupo de órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="bb545-136">The illustration below shows an example of the **Work order pool** list page.</span></span>

![Figura 1](media/22-work-orders.png)


## <a name="add-a-work-order-to-a-work-order-pool"></a><span data-ttu-id="bb545-138">Agregar una orden de trabajo a un grupo de órdenes de trabajo</span><span class="sxs-lookup"><span data-stu-id="bb545-138">Add a work order to a work order pool</span></span>

<span data-ttu-id="bb545-139">Como se describe en la sección anterior, puede agregar órdenes de trabajo a un grupo de órdenes de trabajo al crear ese grupo.</span><span class="sxs-lookup"><span data-stu-id="bb545-139">As described in the previous section, you can add work orders to a work order pool when you create that pool.</span></span> <span data-ttu-id="bb545-140">También puede agregar órdenes de trabajo a un grupo de órdenes de trabajo en la página de lista **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.</span><span class="sxs-lookup"><span data-stu-id="bb545-140">You can also add work orders to a work order pool on the **All work orders** or **Active work orders** list page.</span></span>

1. <span data-ttu-id="bb545-141">Seleccione la orden de trabajo y, a continuación, en el panel de acciones, en la pestaña **Orden de trabajo**, en el grupo **Mantener**, seleccione **Grupo de órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="bb545-141">Select the work order, and then, on the Action Pane, on the **Work order** tab, in the **Maintain** group, select **Work order pool**.</span></span>

2. <span data-ttu-id="bb545-142">Seleccione la orden de trabajo en la lista y haga clic en **Grupo de órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="bb545-142">Select the work order in the list, and click **Work order pool**.</span></span>

3. <span data-ttu-id="bb545-143">En el diálogo **Mantener grupo de órdenes de trabajo**, en el campo **Agregar o quitar**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="bb545-143">In the **Maintain work order pool** dialog, in the **Add/remove** field, select **Add**.</span></span>

4. <span data-ttu-id="bb545-144">En el campo **Grupo**, seleccione el grupo de órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bb545-144">In the **Pool** field, select the work order pool.</span></span>

5. <span data-ttu-id="bb545-145">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bb545-145">Select **OK**.</span></span>

6. <span data-ttu-id="bb545-146">Para poner la orden de trabajo que ha agregado en un orden determinado en el grupo de órdenes de trabajo, en la página de lista **Todos los conjuntos del pedido de trabajo** o **Conjuntos activo de pedidos de trabajo**, seleccione el grupo y, a continuación, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="bb545-146">To put the work order that you added in a specific order in the work order pool, on the **All work order pools** or **Active work order pools** list page, select the pool, and then select **Edit**.</span></span> <span data-ttu-id="bb545-147">A continuación, en la página **Grupo de órdenes de trabajo**, en la ficha desplegable **Órdenes de trabajo**, utilice el campo **Orden** para ajustar el orden de las órdenes de trabajo que se incluyen en el grupo.</span><span class="sxs-lookup"><span data-stu-id="bb545-147">Then, on the **Work order pool** page, on the **Work orders** FastTab, use the **Sort order** field to adjust the sort order of the work orders that are included in pool.</span></span>

<span data-ttu-id="bb545-148">Para eliminar una orden de trabajo de un grupo de órdenes de trabajo, repita estos pasos pero seleccione **Quitar** en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="bb545-148">To remove a work order from a work order pool, repeat these steps, but select **Remove** in step 3.</span></span>

