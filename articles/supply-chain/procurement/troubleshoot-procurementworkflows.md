---
title: Solución de problemas de flujos de trabajo de adquisición y abastecimiento
description: Este tema describe cómo solucionar problemas que pueden surgir al trabajar con flujos de trabajo de adquisición y abastecimiento.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: e8274890c581fffc7330538430c9b2ba060041bc
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4999112"
---
# <a name="troubleshoot-procurement-and-sourcing-workflows"></a><span data-ttu-id="f9eb9-103">Solución de problemas de flujos de trabajo de adquisición y abastecimiento</span><span class="sxs-lookup"><span data-stu-id="f9eb9-103">Troubleshoot procurement and sourcing workflows</span></span>

<span data-ttu-id="f9eb9-104">Este tema describe cómo solucionar problemas que pueden surgir al trabajar con flujos de trabajo de adquisición y abastecimiento.</span><span class="sxs-lookup"><span data-stu-id="f9eb9-104">This topic describes how to fix issues that you might encounter while you work with procurement and sourcing workflows.</span></span>

## <a name="error-when-re-submitting-a-purchase-order-to-the-workflow-after-a-change-changes-to-purchase-order-x-are-allowed-only-in-a-draft-state-when-change-management-is-activated"></a><span data-ttu-id="f9eb9-105">Error al volver a enviar un pedido de compra al flujo de trabajo después de un cambio: "Los cambios en el pedido de compra X solo se permiten en un estado Borrador cuando la administración de cambios está activada".</span><span class="sxs-lookup"><span data-stu-id="f9eb9-105">Error when re-submitting a purchase order to the workflow after a change: "Changes to purchase order X are allowed only in a Draft state when change management is activated"</span></span>

<span data-ttu-id="f9eb9-106">Este problema solo se produce si el pedido de compra estaba en estado *Confirmado* antes de que se soliciten los cambios.</span><span class="sxs-lookup"><span data-stu-id="f9eb9-106">This issue occurs only if the purchase order was in a *Confirmed* state before you requested changes.</span></span> <span data-ttu-id="f9eb9-107">Si solicita cambios mientras el pedido de compra está en estado *Aprobado*, el flujo de trabajo se puede procesar correctamente.</span><span class="sxs-lookup"><span data-stu-id="f9eb9-107">If you request changes while the purchase order is in an *Approved* state, the workflow can be processed successfully.</span></span>

### <a name="error-description"></a><span data-ttu-id="f9eb9-108">Error de descripción</span><span class="sxs-lookup"><span data-stu-id="f9eb9-108">Error description</span></span>

<span data-ttu-id="f9eb9-109">El siguiente error se produce en el flujo de trabajo cuando se vuelve a enviar un pedido de compra después de un cambio:</span><span class="sxs-lookup"><span data-stu-id="f9eb9-109">The following error occurs in the workflow when a purchase order is resubmitted after a change:</span></span>

> <span data-ttu-id="f9eb9-110">Detenido (error): excepción de X++: Los cambios en el pedido de compra PO0000569 solo se permiten en el estado Borrador cuando la administración de cambios está activada en</span><span class="sxs-lookup"><span data-stu-id="f9eb9-110">Stopped (error): X++ Exception: Changes to purchase order PO0000569 are only allowed in state Draft when change management is activated at</span></span><br>
<span data-ttu-id="f9eb9-111">SysWorkflowParticipantProvider-resolve</span><span class="sxs-lookup"><span data-stu-id="f9eb9-111">SysWorkflowParticipantProvider-resolve</span></span><br>
<span data-ttu-id="f9eb9-112">SysWorkflowParticipantProvider-resolveParticipants</span><span class="sxs-lookup"><span data-stu-id="f9eb9-112">SysWorkflowParticipantProvider-resolveParticipants</span></span><br>
<span data-ttu-id="f9eb9-113">SysWorkflowServiceProvider-resolveParticipant</span><span class="sxs-lookup"><span data-stu-id="f9eb9-113">SysWorkflowServiceProvider-resolveParticipant</span></span><br>
<span data-ttu-id="f9eb9-114">SysWorkflowQueue-resume</span><span class="sxs-lookup"><span data-stu-id="f9eb9-114">SysWorkflowQueue-resume</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f9eb9-115">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="f9eb9-115">Issue resolution</span></span>

<span data-ttu-id="f9eb9-116">Este problema se puede producir debido a incoherencias en las distribuciones de pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="f9eb9-116">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="f9eb9-117">Para desbloquear este problema y restablecer el pedido de compra al estado *Borrador*, vaya a **Adquisiciones y abastecimiento \> Tareas periódicas \> Limpiar \> Restablecimiento de distribución de pedido de compra**.</span><span class="sxs-lookup"><span data-stu-id="f9eb9-117">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="f9eb9-118">Para obtener más información, consulte la siguiente publicación de blog: [Resolver errores de distribución de pedidos de compra en Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="f9eb9-118">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

<span data-ttu-id="f9eb9-119">El problema se solucionará con [este artículo de Microsoft Knowledge Base (KB)](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138).</span><span class="sxs-lookup"><span data-stu-id="f9eb9-119">The issue will be fixed through [this Microsoft Knowledge Base (KB) article](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138).</span></span>

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a><span data-ttu-id="f9eb9-120">Una o más distribuciones contables están distribuidas en exceso o en defecto.</span><span class="sxs-lookup"><span data-stu-id="f9eb9-120">One or more accounting distributions are either over-distributed or under-distributed.</span></span>

<span data-ttu-id="f9eb9-121">Este problema se puede producir debido a incoherencias en las distribuciones de pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="f9eb9-121">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="f9eb9-122">Para desbloquear este problema y restablecer el pedido de compra al estado *Borrador*, vaya a **Adquisiciones y abastecimiento \> Tareas periódicas \> Limpiar \> Restablecimiento de distribución de pedido de compra**.</span><span class="sxs-lookup"><span data-stu-id="f9eb9-122">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="f9eb9-123">Para obtener más información, consulte la siguiente publicación de blog: [Resolver errores de distribución de pedidos de compra en Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="f9eb9-123">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="if-a-delivery-remainder-is-canceled-on-a-purchase-order-where-change-management-is-turned-on-the-purchase-order-goes-to-a-confirmed-state"></a><span data-ttu-id="f9eb9-124">Si se cancela un remanente de entrega en un pedido de compra donde la administración de cambios está activada, el pedido de compra pasa a un estado Confirmado.</span><span class="sxs-lookup"><span data-stu-id="f9eb9-124">If a delivery remainder is canceled on a purchase order where change management is turned on, the purchase order goes to a Confirmed state.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f9eb9-125">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="f9eb9-125">Issue description</span></span>

<span data-ttu-id="f9eb9-126">Para un pedido de compra sujeto a la administración de cambios, si el único cambio que se solicita es la cancelación de un remanente de entrega en una o más de las líneas, el pedido de compra pasará directamente al estado *Confirmado* cuando se apruebe, y no se creará ningún diario.</span><span class="sxs-lookup"><span data-stu-id="f9eb9-126">For a purchase order that is subject to change management, if the only change that is requested is the cancellation of a delivery remainder on one or more of the lines, the purchase order will go directly to a *Confirmed* state when it's approved, and no journal will be created.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f9eb9-127">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="f9eb9-127">Issue resolution</span></span>

<span data-ttu-id="f9eb9-128">La cancelación de un remanente de entrega no afecta el contenido del diario de confirmación.</span><span class="sxs-lookup"><span data-stu-id="f9eb9-128">Cancellation of a delivery remainder doesn't affect the contents of the confirmation journal.</span></span> <span data-ttu-id="f9eb9-129">Esta funcionalidad debe usarse cuando la línea se ha recibido parcialmente y la calidad restante debe cancelarse en el paso del proceso después de que se haya confirmado el pedido de compra con el proveedor.</span><span class="sxs-lookup"><span data-stu-id="f9eb9-129">This functionality should be used when the line has been partially received, and the remainder quality should be canceled in the process step after the purchase order has been confirmed with the vendor.</span></span>

<span data-ttu-id="f9eb9-130">Si esto tuviera que reflejarse en la confirmación del pedido de compra, la cantidad debe ajustarse en la línea del pedido de compra para que se requiera la confirmación.</span><span class="sxs-lookup"><span data-stu-id="f9eb9-130">If this should be reflected on the purchase order confirmation, the quantity should be adjusted on the purchase order line so that the confirmation will be required.</span></span> <span data-ttu-id="f9eb9-131">Como alternativa, si no se ha recibido nada en la línea, se puede quitar la cantidad.</span><span class="sxs-lookup"><span data-stu-id="f9eb9-131">Alternatively, if nothing has been received on the line, the quantity can be removed.</span></span> <span data-ttu-id="f9eb9-132">En este caso, se requerirá una reconfirmación.</span><span class="sxs-lookup"><span data-stu-id="f9eb9-132">In this case, reconfirmation will be required.</span></span>

## <a name="canceled-purchase-orders-appear-in-the-draft-list-in-the-purchase-order-preparation-workspace"></a><span data-ttu-id="f9eb9-133">Los pedidos de compra cancelados aparecen en la lista de borradores en el espacio de trabajo Preparación del pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="f9eb9-133">Canceled purchase orders appear in the draft list in the Purchase order preparation workspace.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f9eb9-134">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="f9eb9-134">Issue description</span></span>

<span data-ttu-id="f9eb9-135">Después de cancelar pedidos de compra que estaban en estado *Confirmado*, los pedidos de compra cancelados todavía aparecen en la lista de borradores de pedidos de compra en el espacio de trabajo **Preparación del pedido de compra**.</span><span class="sxs-lookup"><span data-stu-id="f9eb9-135">After you cancel purchase orders that were in a *Confirmed* state, the canceled purchase orders still appear in the list of draft purchase orders in the **Purchase order preparation** workspace.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f9eb9-136">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="f9eb9-136">Issue resolution</span></span>

<span data-ttu-id="f9eb9-137">Este problema solo se produce para los pedidos de compra que están sujetos a la administración de cambios.</span><span class="sxs-lookup"><span data-stu-id="f9eb9-137">This issue occurs only for purchase orders that are subject to change management.</span></span> <span data-ttu-id="f9eb9-138">Se produce porque se considera que la cancelación es un cambio que debe ser aprobado.</span><span class="sxs-lookup"><span data-stu-id="f9eb9-138">It occurs because the cancellation is considered a change that must be approved.</span></span> <span data-ttu-id="f9eb9-139">La aprobación la puede realizar el sistema automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f9eb9-139">The approval can be done automatically by the system.</span></span> <span data-ttu-id="f9eb9-140">Por lo tanto, el proceso consiste en enviar el pedido de compra cancelado al flujo de trabajo de aprobación para que pueda pasar al estado *Aprobado*.</span><span class="sxs-lookup"><span data-stu-id="f9eb9-140">Therefore, the process is to submit the canceled purchase order to the approval workflow so that it can go to an *Approved* state.</span></span> <span data-ttu-id="f9eb9-141">En ese momento, el pedido de compra ya no aparecerá en la lista de borradores de pedido de compra en el espacio de trabajo **Preparación del pedido de compra**.</span><span class="sxs-lookup"><span data-stu-id="f9eb9-141">At that point, the purchase order will no longer appear in the list of draft purchase orders in the **Purchase order preparation** workspace.</span></span>

