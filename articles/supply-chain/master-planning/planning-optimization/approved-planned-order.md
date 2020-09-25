---
title: Aprobar pedidos planificados
description: Este tema describe la aprobación de pedidos planificados que se admiten en Planning Optimization.
author: ChristianRytt
manager: tfehr
ms.date: 08/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: b7975088be898ccecceb1f7be009cecff107f6e6
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759697"
---
# <a name="approve-planned-orders"></a><span data-ttu-id="6419f-103">Aprobar pedidos planificados</span><span class="sxs-lookup"><span data-stu-id="6419f-103">Approve planned orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6419f-104">Este tema proporciona información sobre cómo actualizar el estado de los pedidos planificados en Planning Optimization.</span><span class="sxs-lookup"><span data-stu-id="6419f-104">This topic provides information about how to update the status of planned orders in Planning Optimization.</span></span>

<span data-ttu-id="6419f-105">Tenga en cuenta que la aprobación de pedidos planificados es un paso opcional, en el proceso para crear un pedido en firme a partir de un pedido planificado.</span><span class="sxs-lookup"><span data-stu-id="6419f-105">Note that approval of planned orders is an optional step, on the way to create a firmed order from a planned order.</span></span> <span data-ttu-id="6419f-106">Se recomienda aprobar los pedidos planificados modificados; de lo contrario, las ediciones se ignorarán y se sobrescribirán en la siguiente ejecución de planificación.</span><span class="sxs-lookup"><span data-stu-id="6419f-106">It is recommended to approve modified planned orders, otherwise the edits will be ignored and overwritten by the next planning run.</span></span>

![Flujo de pedido planificado](media/approved-planned-orders-1.png)

<span data-ttu-id="6419f-108">El campo **Estado** le ayuda a seguir su progreso utilizando los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="6419f-108">The **Status** field helps you tack your progress using the following values:</span></span>

- <span data-ttu-id="6419f-109">**No procesado**: cuando la planificación maestra genera pedidos planificados, estos tienen un estado *No procesado*.</span><span class="sxs-lookup"><span data-stu-id="6419f-109">**Unprocessed:** When master planning generates planned orders, the planned orders have a status of *Unprocessed*.</span></span> <span data-ttu-id="6419f-110">Los pedidos planificados con este estado se eliminarán durante la siguiente ejecución de planificación.</span><span class="sxs-lookup"><span data-stu-id="6419f-110">Planned orders with this status will be deleted during the next planning run.</span></span>
- <span data-ttu-id="6419f-111">**Completado**: si decide no firmar un pedido planificado, puede cambiar el estado a *Completado* para indicar que completó la evaluación de este pedido planificado.</span><span class="sxs-lookup"><span data-stu-id="6419f-111">**Completed:** If you decide not to firm a planned order, you can change the status to *Completed* to indicate that you completed evaluating this planned order.</span></span> <span data-ttu-id="6419f-112">Tenga en cuenta que un estado de *No procesado* y *Completado* se tratan de la misma manera por el sistema.</span><span class="sxs-lookup"><span data-stu-id="6419f-112">Note that a status of *Unprocessed* and *Completed* are treated the same by the system.</span></span>
- <span data-ttu-id="6419f-113">**Aprobado**: si desea mantener las ediciones o tiene previsto poner en firme un pedido planificado, cambie el estado a *Aprobado*.</span><span class="sxs-lookup"><span data-stu-id="6419f-113">**Approved:** If you want to keep edits or are planning to firm a planned order, change the status to *Approved*.</span></span> <span data-ttu-id="6419f-114">Los pedidos planificados con estado *Aprobado* se consideran un suministro fijo y esperado por la planificación maestra, por lo que no se modifican ni se eliminan durante una ejecución de planificación maestra posterior.</span><span class="sxs-lookup"><span data-stu-id="6419f-114">Planned orders with *Approved* status are considered as fixed and expected supply by master planning, so they are not modified or deleted during later master planning runs.</span></span> <span data-ttu-id="6419f-115">Para lograr esto, la lógica de planificación copia los pedidos planificados *Aprobados* desde la versión anterior del plan a la nueva versión del plan durante la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="6419f-115">To achieve this, the planning logic copies the *Approved* planned orders from the old plan version to the new plan version during master planning.</span></span> <span data-ttu-id="6419f-116">Tenga en cuenta los pedidos planificados con estado *Aprobado* solo se consideran un suministro dentro del plan maestro específico.</span><span class="sxs-lookup"><span data-stu-id="6419f-116">Note that *Approved* planned orders are only considered supply within the specific master plan.</span></span>

<span data-ttu-id="6419f-117">Puede gestionar pedidos planificados desde el espacio de trabajo **Planificación maestra**, la lista **Pedido planificado** o las listas **Pedidos de producción planificados**, **Pedidos de compra planificados** y **Transferencia planificada**.</span><span class="sxs-lookup"><span data-stu-id="6419f-117">You can manage planned orders from the  **Master planning**  workspace, the  **Planned order**  list, or the  **Planned production orders**,  **Planned purchase orders**, and  **Planned transfer**  lists.</span></span>
