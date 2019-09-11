---
title: Grupos de órdenes de trabajo
description: En este tema se describe cómo trabajar con grupos de órdenes de trabajo en administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 069fa02073808fd7bbaac9bc1603e49ce4d450eb
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875883"
---
# <a name="work-order-pools"></a><span data-ttu-id="fe102-103">Grupos de órdenes de trabajo</span><span class="sxs-lookup"><span data-stu-id="fe102-103">Work order pools</span></span>


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="fe102-104">Puede usar conjuntos de órdenes de trabajo para agrupar órdenes de trabajo que tienen algo en común.</span><span class="sxs-lookup"><span data-stu-id="fe102-104">You can use work order pools to group work orders that have something in common.</span></span> <span data-ttu-id="fe102-105">Por ejemplo, puede crear conjuntos de grupos de trabajo para</span><span class="sxs-lookup"><span data-stu-id="fe102-105">For example, you can create work order pools for</span></span>

- <span data-ttu-id="fe102-106">equipos de trabajo; por ejemplo, equipo de mantenimiento A, equipo de mantenimiento B</span><span class="sxs-lookup"><span data-stu-id="fe102-106">work crews, for example, Maintenance Crew A, Maintenance Crew B</span></span>  

- <span data-ttu-id="fe102-107">aptitudes profesionales, por ejemplo, electricistas o fontaneros</span><span class="sxs-lookup"><span data-stu-id="fe102-107">professional skills, for example, electricians or plumbers</span></span>  

- <span data-ttu-id="fe102-108">ubicaciones físicas</span><span class="sxs-lookup"><span data-stu-id="fe102-108">physical locations</span></span>  

- <span data-ttu-id="fe102-109">calendarios; por ejemplo, semanas u otros períodos</span><span class="sxs-lookup"><span data-stu-id="fe102-109">time schedules, for example, weeks or other periods</span></span>  


<span data-ttu-id="fe102-110">Si es necesario, un pedido de trabajo puede realizarse en varios conjuntos de órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe102-110">If required, one work order can be placed in many work order pools.</span></span>


## <a name="create-work-order-pool"></a><span data-ttu-id="fe102-111">Crear grupos de órdenes de trabajo</span><span class="sxs-lookup"><span data-stu-id="fe102-111">Create work order pool</span></span>

<span data-ttu-id="fe102-112">En **Todos los grupos de órdenes de trabajo** o **Grupo de órdenes de trabajo activas**, puede obtener una visión general de los grupos de órdenes de trabajo y crear nuevos grupos.</span><span class="sxs-lookup"><span data-stu-id="fe102-112">In **All work order pools** or **Active work order pools**, you can get an overview of your work order pools and create new pools.</span></span>

1. <span data-ttu-id="fe102-113">Haga clic en **Administración de activos** > **Común** > **Grupos de órdenes de trabajo** > **Todos los grupos de órdenes de trabajo** o **Grupos de órdenes de trabajo activas**.</span><span class="sxs-lookup"><span data-stu-id="fe102-113">Click **Asset management** > **Common** > **Work order pools** > **All work order pools** or **Active work order pools**.</span></span>

2. <span data-ttu-id="fe102-114">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="fe102-114">Click **New**.</span></span>

3. <span data-ttu-id="fe102-115">Inserte un identificador de grupo de órdenes de trabajo en el campo **Grupo** y un nombre en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="fe102-115">Insert a work order pool ID in the **Pool** field and a name in the **Name** field.</span></span>

4. <span data-ttu-id="fe102-116">Seleccione "Sí" en el botón de alternar **Activo** para indicar que el grupo de órdenes de trabajo está activo.</span><span class="sxs-lookup"><span data-stu-id="fe102-116">Select "Yes" on the **Active** toggle button to indicate that the work order pool is active.</span></span>

5. <span data-ttu-id="fe102-117">Seleccione "Sí" en el botón de alternar **Eliminar relaciones de órdenes de trabajo** si desea que las órdenes de trabajo automáticamente se quiten del grupo de órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe102-117">Select "Yes" on the **Delete work order relations** toggle button if you want work orders to be automatically removed from the work order pool.</span></span>

6. <span data-ttu-id="fe102-118">En el campo **Eliminar estado de ciclo de vida**, seleccione el estado del ciclo de vida de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe102-118">In the **Delete lifecycle state** field, select the work order lifecycle state.</span></span> <span data-ttu-id="fe102-119">Por ejemplo, el estado del ciclo de vida de pedido de trabajo para completar un pedido de trabajo se puede establecer para eliminar automáticamente relaciones con grupos de órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe102-119">For example, the work order lifecycle state for completing a work order could be set to automatically delete relations to work order pools.</span></span>

7. <span data-ttu-id="fe102-120">Puede empezar a agregar órdenes de trabajo a su grupo de órdenes de trabajo inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="fe102-120">You can start adding work orders to your work order pool right away.</span></span> <span data-ttu-id="fe102-121">En la ficha desplegable **Órdenes de trabajo**, haga clic en **Agregar línea**.</span><span class="sxs-lookup"><span data-stu-id="fe102-121">On the **Work orders** FastTab, click **Add line**.</span></span>

8. <span data-ttu-id="fe102-122">Seleccione una orden de trabajo en el campo **orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="fe102-122">Select a work order in the **Work order** field.</span></span> <span data-ttu-id="fe102-123">Los campos relacionados se actualizarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="fe102-123">The related fields are automatically updated.</span></span>

9. <span data-ttu-id="fe102-124">Repita los pasos 7-8 si desea agregar más órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe102-124">Repeat steps 7-8 if you want to add more work orders.</span></span>

10. <span data-ttu-id="fe102-125">En el campo **Orden**, puede indicar si las órdenes de trabajo se realizan siguiendo un orden determinado.</span><span class="sxs-lookup"><span data-stu-id="fe102-125">In the **Sort order** field, you can indicate if the work orders should be carried out in a certain order.</span></span> <span data-ttu-id="fe102-126">Inserte los números 1, 2, 3, etc. para indicar una secuencia específica para las órdenes de trabajo seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="fe102-126">Insert numbers 1, 2, 3, and so on to indicate a specific sequence for the selected work orders.</span></span>

11. <span data-ttu-id="fe102-127">Haga clic en el botón **Órdenes de trabajo** para ver una lista de todos las órdenes de trabajo incluidas en el grupo de órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe102-127">Click the **Work orders** button to see a list of all the work orders included in the work order pool.</span></span>

12. <span data-ttu-id="fe102-128">Haga clic en el botón **Carga de capacidad** para abrir **Carga de capacidad** para calcular y ver la carga de capacidad de la programación del mantenimiento, las órdenes de trabajo no programadas y las órdenes de trabajo programadas.</span><span class="sxs-lookup"><span data-stu-id="fe102-128">Click the **Capacity load** button to open **Capacity load** to calculate and view capacity load for maintenance schedule, not-scheduled work orders, and scheduled work orders.</span></span>

13. <span data-ttu-id="fe102-129">Haga clic en el botón **Previsión de artículos** para abrir **Previsión de artículos** para calcular y ver las previsiones para artículos (piezas de repuesto y otros elementos obligatorios) relacionados con la programación del mantenimiento, las órdenes de trabajo no programadas y las órdenes de trabajo programadas.</span><span class="sxs-lookup"><span data-stu-id="fe102-129">Click the **Item forecast** button to open **Item forecast** to calculate and view forecasts for items (spare parts and other required items) related to maintenance schedule, not-scheduled work orders, and scheduled work orders.</span></span>

14. <span data-ttu-id="fe102-130">Haga clic en el botón **Solicitud de compra de orden de trabajo** para abrir la lista **Solicitud de compra de orden de trabajo** para abrir una lista de solicitudes de compra relacionadas con órdenes de compra del grupo de órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe102-130">Click the **Work order purchase requisition** button to open the **Work order purchase requisition** list to see a list of purchase requisitions related to the work orders in the work order pool.</span></span>

15. <span data-ttu-id="fe102-131">Haga clic en el botón **Compra de orden de trabajo** para abrir la lista **Compra de orden de trabajo** para abrir una lista de órdenes de compra relacionadas con órdenes de trabajo del grupo de órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe102-131">Click the **Work order purchase** button to open the **Work order purchase** list to see a list of purchase orders related to the work orders in the work order pool.</span></span>

>[!NOTE]
><span data-ttu-id="fe102-132">Cuando un conjunto de órdenes de trabajo ya no es relevante para la planificación de trabajo, establezca la casilla de verificación **Activo** de dicho grupo en ”No” en la vista de lista **Grupo de órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="fe102-132">When a work order pool is no longer relevant for your work planning, set the **Active** check box for that pool to "No" in the **Work order pool** list view.</span></span>

<span data-ttu-id="fe102-133">Seleccione la casilla de verificación **Eliminar relaciones de órdenes de trabajo** si desea eliminar todas las líneas de pedido del trabajo, para por ejemplo, crear un conjunto vacío que pueda usar posteriormente para otros órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe102-133">Select the **Delete work order relations** check box if you want to delete all work order lines, for example to create an empty pool that you can later use for other work orders.</span></span> <span data-ttu-id="fe102-134">No se olvide de desactivar la casilla de verificación **Eliminar relaciones de órdenes de trabajo** si desea usar el conjunto de órdenes de trabajo para crear relaciones de órdenes de trabajo nuevas posteriormente.</span><span class="sxs-lookup"><span data-stu-id="fe102-134">Remember to clear the **Delete work order relations** check box if you want to use the work order pool to create new work order relations later.</span></span>


![Figura 1](media/22-work-orders.png)


## <a name="add-work-order-to-a-work-order-pool"></a><span data-ttu-id="fe102-136">Agregar un pedido de trabajo a un conjunto de órdenes de trabajo</span><span class="sxs-lookup"><span data-stu-id="fe102-136">Add work order to a work order pool</span></span>

<span data-ttu-id="fe102-137">Como se describe en la sección anterior, puede agregar órdenes de trabajo a un grupo de órdenes de trabajo al crear el grupo.</span><span class="sxs-lookup"><span data-stu-id="fe102-137">As described in the section above, you can add work orders to a work order pool when you create the pool.</span></span> <span data-ttu-id="fe102-138">También puede agregar un pedido de trabajo a un grupo de órdenes de trabajo desde una de las listas de **Todas las órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="fe102-138">You can also add a work order to a work order pool from one of the **All work orders** list.</span></span>

1. <span data-ttu-id="fe102-139">Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.</span><span class="sxs-lookup"><span data-stu-id="fe102-139">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="fe102-140">Seleccione la orden de trabajo en la lista y haga clic en **Grupo de órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="fe102-140">Select the work order in the list, and click **Work order pool**.</span></span>

3. <span data-ttu-id="fe102-141">Seleccione “Agregar” en el campo **Agregar o quitar**.</span><span class="sxs-lookup"><span data-stu-id="fe102-141">Select "Add" in the **Add/remove** field.</span></span>

4. <span data-ttu-id="fe102-142">En el campo **Grupo**, seleccione el grupo de órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe102-142">Select the work order pool in the **Pool** field.</span></span>

5. <span data-ttu-id="fe102-143">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fe102-143">Click **OK**.</span></span>

6. <span data-ttu-id="fe102-144">Una vez agregado un pedido de trabajo a un conjunto de órdenes de trabajo, si desea poner la orden de trabajo en una secuencia específica del conjunto: Abra una de las páginas de lista de los conjuntos de órdenes de trabajo, seleccione el conjunto y haga clic en **Editar** y ajuste el orden de las órdenes de trabajo incluidas en el conjunto en el formulario **Grupo de órdenes de trabajo** > ficha desplegable **Órdenes de trabajo** > campo **Orden**.</span><span class="sxs-lookup"><span data-stu-id="fe102-144">After you have added a work order to a work order pool, if you want to place the work order in a specific sequence in the pool: Open one of the work order pools list pages, select the pool and click **Edit**, and adjust the sort order of the work orders included in pool in the **Work order pool** form > **Work orders** FastTab > **Sort order** field.</span></span>

<span data-ttu-id="fe102-145">Si desea eliminar la orden de trabajo seleccionado de un conjunto de órdenes de trabajo, seleccione “Quitar” en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="fe102-145">If you want to remove the selected work order from a work order pool, select "Remove" in step 3.</span></span>

