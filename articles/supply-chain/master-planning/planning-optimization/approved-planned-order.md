---
title: Ver, administrar y aprobar pedidos planificados
description: Este tema proporciona información sobre cómo ver, administrar y aprobar pedidos planificados en Optimización de planificación.
author: ChristianRytt
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 3b9b5274481e693f9fa05eb084ec5505ce5bc2eb
ms.sourcegitcommit: 9283caad2d0636f98579c995784abec19fda2e3f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2021
ms.locfileid: "5935666"
---
# <a name="view-manage-and-approve-planned-orders"></a><span data-ttu-id="230a9-103">Ver, administrar y aprobar pedidos planificados</span><span class="sxs-lookup"><span data-stu-id="230a9-103">View, manage, and approve planned orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="230a9-104">Este tema proporciona información sobre cómo ver, administrar y aprobar pedidos planificados en Optimización de planificación.</span><span class="sxs-lookup"><span data-stu-id="230a9-104">This topic provides information about how to view, manage, and approve planned orders in Planning Optimization.</span></span>

## <a name="view-and-manage-planned-orders"></a><a name="view-planned-orders"></a><span data-ttu-id="230a9-105">Ver y administrar pedidos planificados</span><span class="sxs-lookup"><span data-stu-id="230a9-105">View and manage planned orders</span></span>

<span data-ttu-id="230a9-106">Puede ver y administrar los pedidos planificados en cualquier página de lista de pedidos planificados.</span><span class="sxs-lookup"><span data-stu-id="230a9-106">You can view and manage planned orders on any planned orders list page.</span></span> <span data-ttu-id="230a9-107">Vaya a uno de los siguientes lugares, según el tipo de pedidos planificados con los que desee trabajar:</span><span class="sxs-lookup"><span data-stu-id="230a9-107">Go to one of the following places, depending on the type of planned orders that you want to work with:</span></span>

- <span data-ttu-id="230a9-108">Planificacion maestra \> Espacios de trabajo \> Planificacion maestra</span><span class="sxs-lookup"><span data-stu-id="230a9-108">Master planning \> Workspaces \> Master planning</span></span>
- <span data-ttu-id="230a9-109">Planificación maestra \> Planificación maestra \> Pedidos planificados</span><span class="sxs-lookup"><span data-stu-id="230a9-109">Master planning \> Master planning \> Planned orders</span></span>
- <span data-ttu-id="230a9-110">Vaya a Control de producción \> Pedidos de producción \> Pedidos de producción planificados</span><span class="sxs-lookup"><span data-stu-id="230a9-110">Production control \> Production orders \> Planned production orders</span></span>
- <span data-ttu-id="230a9-111">Adquisición y abastecimiento \> Pedidos de compra \> Pedidos de producción planificados</span><span class="sxs-lookup"><span data-stu-id="230a9-111">Procurement and sourcing \> Purchase orders \> Planned purchase orders</span></span>
- <span data-ttu-id="230a9-112">Gestión del inventario \> Pedidos de entrada \> Transferencias planificadas</span><span class="sxs-lookup"><span data-stu-id="230a9-112">Inventory management \> Inbound orders \> Planned transfers</span></span>
- <span data-ttu-id="230a9-113">Gestión del inventario \> Pedidos de salida \> Transferencias planificadas</span><span class="sxs-lookup"><span data-stu-id="230a9-113">Inventory management \> Outbound orders \> Planned transfers</span></span>

## <a name="view-and-edit-the-status-of-planned-orders"></a><span data-ttu-id="230a9-114">Ver y editar el estado de los pedidos planificados</span><span class="sxs-lookup"><span data-stu-id="230a9-114">View and edit the status of planned orders</span></span>

<span data-ttu-id="230a9-115">Puede usar el campo **Estado** de cada orden planificada para ayudar a realizar un seguimiento de su progreso o cambiar la forma en que se procesará una orden planificada.</span><span class="sxs-lookup"><span data-stu-id="230a9-115">You can use the **Status** field of each planned order to help track your progress or change how a planned order will be processed.</span></span> <span data-ttu-id="230a9-116">Están disponibles los siguientes valores de **Estado**:</span><span class="sxs-lookup"><span data-stu-id="230a9-116">The following **Status** values are available:</span></span>

- <span data-ttu-id="230a9-117">**No procesado**: cuando la planificación maestra genera pedidos planificados, se les da este estado.</span><span class="sxs-lookup"><span data-stu-id="230a9-117">**Unprocessed** – When master planning generates planned orders, they are given this status.</span></span> <span data-ttu-id="230a9-118">Los pedidos planificados que tienen este estado se eliminarán durante la siguiente ejecución de planificación.</span><span class="sxs-lookup"><span data-stu-id="230a9-118">Planned orders that have this status will be deleted during the next planning run.</span></span>
- <span data-ttu-id="230a9-119">**Terminado**: este estado indica que la orden planificada se ha completado.</span><span class="sxs-lookup"><span data-stu-id="230a9-119">**Completed** – This status indicates that the planned order has been completed.</span></span> <span data-ttu-id="230a9-120">Si decide no poner en firme un pedido planificado, puede cambiar manualmente su estado a *Finalizado*.</span><span class="sxs-lookup"><span data-stu-id="230a9-120">If you decide not to firm a planned order, you can manually change its status to *Completed*.</span></span> <span data-ttu-id="230a9-121">Tenga en cuenta que el sistema trata los estados *No procesado* y *Completado* de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="230a9-121">Note that the system treats the *Unprocessed* and *Completed* statuses in the same way.</span></span>
- <span data-ttu-id="230a9-122">**Aprobado**: este estado indica que la orden planificada está aprobada para confirmación.</span><span class="sxs-lookup"><span data-stu-id="230a9-122">**Approved** – This status indicates that the planned order is approved for firming.</span></span> <span data-ttu-id="230a9-123">Si desea consolidar un pedido planificado, puede cambiar su estado a *Aprobado*.</span><span class="sxs-lookup"><span data-stu-id="230a9-123">If you want to firm a planned order, you can change its status to *Approved*.</span></span> <span data-ttu-id="230a9-124">Si desea conservar las ediciones que se han realizado en una orden planificada, o si está planeando confirmar una orden planificada, cambie su estado a *Aprobado*.</span><span class="sxs-lookup"><span data-stu-id="230a9-124">If you want to keep the edits that have been made to a planned order, or if you're planning to firm a planned order, change its status to *Approved*.</span></span> <span data-ttu-id="230a9-125">Las órdenes planificadas que tienen un estado de *Aprobado* se consideran suministros fijos y esperados por planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="230a9-125">Planned orders that have a status of *Approved* are considered fixed and expected supply by master planning.</span></span> <span data-ttu-id="230a9-126">Por lo tanto, no se modifican ni se eliminan durante las ejecuciones posteriores de la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="230a9-126">Therefore, they aren't modified or deleted during later master planning runs.</span></span> <span data-ttu-id="230a9-127">Para lograr este comportamiento, la lógica de planificación copia los pedidos planificados con estado *Aprobado* desde la versión anterior del plan a la nueva versión del plan durante la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="230a9-127">To achieve this behavior, the planning logic copies planned orders that have a status of *Approved* from the old plan version to the new plan version during master planning.</span></span> <span data-ttu-id="230a9-128">Tenga en cuenta que los pedidos planificados con estado *Aprobado*\* solo se consideran un suministro dentro del plan maestro específico.</span><span class="sxs-lookup"><span data-stu-id="230a9-128">Note that planned orders that have a status of *Approved*\* are considered supply only within the specific master plan.</span></span>

<span data-ttu-id="230a9-129">Para cambiar el estado de una sola orden planificada, [abra cualquier página de lista de pedidos planificados](#view-planned-orders), abra el pedido y luego siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="230a9-129">To change the status of a single planned order, [open any planned orders list page](#view-planned-orders), open the order, and then follow one of these steps:</span></span>

- <span data-ttu-id="230a9-130">En la ficha desplegable **General**, cambie el valor del campo **Estado**.</span><span class="sxs-lookup"><span data-stu-id="230a9-130">On the **General** FastTab, change the value of the **Status** field.</span></span>
- <span data-ttu-id="230a9-131">En el panel de acciones, en la pestaña **Pedido planificado**, en el grupo **Proceso**, seleccione **Cambiar estado**.</span><span class="sxs-lookup"><span data-stu-id="230a9-131">On the Action Pane, on the **Planned order** tab, in the **Process** group, select **Change status**.</span></span>
- <span data-ttu-id="230a9-132">En el panel de acciones, seleccione **Aprobar** para marcar el pedido como aprobado.</span><span class="sxs-lookup"><span data-stu-id="230a9-132">On the Action Pane, select **Approve** to mark the order as approved.</span></span>

<span data-ttu-id="230a9-133">Para cambiar el estado de varias órdenes planificadas al mismo tiempo, [abra cualquier página de lista de pedidos planificados](#view-planned-orders), seleccione la casilla para cada pedido que desee cambiar y luego siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="230a9-133">To change the status of several planned orders at the same time, [open any planned orders list page](#view-planned-orders), select the check box for each order that you want to change, and then follow one of these steps:</span></span>

- <span data-ttu-id="230a9-134">En el panel de acciones, en la pestaña **Pedido planificado**, en el grupo **Proceso**, seleccione **Cambiar estado**.</span><span class="sxs-lookup"><span data-stu-id="230a9-134">On the Action Pane, on the **Planned order** tab, in the **Process** group, select **Change status**.</span></span>
- <span data-ttu-id="230a9-135">En el panel de acciones, seleccione **Aprobar** para marcar los pedidos como aprobados.</span><span class="sxs-lookup"><span data-stu-id="230a9-135">On the Action Pane, select **Approve** to mark the orders as approved.</span></span>

## <a name="approve-planned-orders"></a><span data-ttu-id="230a9-136">Aprobar pedidos planificados</span><span class="sxs-lookup"><span data-stu-id="230a9-136">Approve planned orders</span></span>

<span data-ttu-id="230a9-137">La aprobación de pedidos planificados es un paso opcional en el proceso de crear un pedido confirmado a partir de un pedido planificado.</span><span class="sxs-lookup"><span data-stu-id="230a9-137">Approval of planned orders is an optional step in the process of creating a firmed order from a planned order.</span></span>

<span data-ttu-id="230a9-138">La siguiente ilustración muestra cómo puede utilizar el valor **Estado** que se asigna a cada orden planificada para implementar un flujo de trabajo de aprobación.</span><span class="sxs-lookup"><span data-stu-id="230a9-138">The following illustration shows how you can use the **Status** value that is assigned to each planned order to implement an approval workflow.</span></span> <span data-ttu-id="230a9-139">Para implementar un proceso de aprobación, ajuste manualmente el valor **Estado** para cada orden planificada, como se describe en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="230a9-139">To implement an approval process, manually adjust the **Status** value for each planned order as described in the previous section.</span></span>

![Flujo de pedido planificado](media/approved-planned-orders-1.png)

> [!TIP]
> <span data-ttu-id="230a9-141">Le recomendamos que apruebe cualquier pedido planificado modificado.</span><span class="sxs-lookup"><span data-stu-id="230a9-141">We recommend that you approve any modified planned orders.</span></span> <span data-ttu-id="230a9-142">De lo contrario, las ediciones se ignorarán y se sobrescribirán en la siguiente ejecución de planificación.</span><span class="sxs-lookup"><span data-stu-id="230a9-142">Otherwise, the edits will be ignored and overwritten by the next planning run.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="230a9-143">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="230a9-143">Additional resources</span></span>

- [<span data-ttu-id="230a9-144">Poner en firme pedidos planificados</span><span class="sxs-lookup"><span data-stu-id="230a9-144">Firm planned orders</span></span>](planned-order-firming.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
