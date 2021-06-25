---
title: No puede confirmar un envío debido a trabajo incompleto o que falta
description: No puede confirmar un envío debido a trabajo incompleto o que falta
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm, WHSContainerCloseDiag_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: beef0909d41e69f3e7bcc1021527be35b7e6fd44
ms.sourcegitcommit: c2c6d687a89bc1534c029109315c23e92865b63b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2021
ms.locfileid: "6123852"
---
# <a name="you-cant-confirm-a-shipment-because-of-incomplete-or-missing-work"></a><span data-ttu-id="67925-103">No puede confirmar un envío debido a trabajo incompleto o que falta</span><span class="sxs-lookup"><span data-stu-id="67925-103">You can't confirm a shipment because of incomplete or missing work</span></span>

<span data-ttu-id="67925-104">Código de error: WAX515</span><span class="sxs-lookup"><span data-stu-id="67925-104">Error code: WAX515</span></span>

## <a name="symptoms"></a><span data-ttu-id="67925-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="67925-105">Symptoms</span></span>

<span data-ttu-id="67925-106">Cuando intenta confirmar un envío, el sistema muestra el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="67925-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="67925-107">El envío para la carga %1 no se pudo confirmar porque todos los trabajos de la carga deben estar completos.</span><span class="sxs-lookup"><span data-stu-id="67925-107">The shipment for load %1 could not be confirmed because all work for the load must be complete.</span></span>

<span data-ttu-id="67925-108">Por lo tanto, no puede confirmar el envío de la carga.</span><span class="sxs-lookup"><span data-stu-id="67925-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="67925-109">Causa</span><span class="sxs-lookup"><span data-stu-id="67925-109">Cause</span></span>

<span data-ttu-id="67925-110">La carga o el envío se encuentran actualmente en un estado en el que falla la confirmación del envío.</span><span class="sxs-lookup"><span data-stu-id="67925-110">The load or shipment is currently in a state where shipment confirmation fails.</span></span> <span data-ttu-id="67925-111">Antes de que pueda confirmar el envío, debe existir al menos algún trabajo para la carga, y todo ese trabajo debe tener un estado de *Cerrado* o *Cancelado*.</span><span class="sxs-lookup"><span data-stu-id="67925-111">Before you can confirm the shipment, at least some work must exist for the load, and all that work must have a status of *Closed* or *Canceled*.</span></span>

## <a name="resolution"></a><span data-ttu-id="67925-112">Resolución</span><span class="sxs-lookup"><span data-stu-id="67925-112">Resolution</span></span>

<span data-ttu-id="67925-113">Verifique las órdenes de venta o las órdenes de transferencia relacionadas para la carga o el envío, y asegúrese de que todo el trabajo relacionado se haya completado o cancelado.</span><span class="sxs-lookup"><span data-stu-id="67925-113">Check the related sales orders or transfer orders for the load or shipment, and make sure that all the related work has been completed or canceled.</span></span>

<span data-ttu-id="67925-114">Puede trabajar con envíos y cargas en varias páginas.</span><span class="sxs-lookup"><span data-stu-id="67925-114">You can work with shipments and loads on several pages.</span></span> <span data-ttu-id="67925-115">Las siguientes subsecciones proporcionan algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="67925-115">The following subsections provide a few examples.</span></span>

### <a name="all-loads-page"></a><span data-ttu-id="67925-116">Página Todas las cargas</span><span class="sxs-lookup"><span data-stu-id="67925-116">All loads page</span></span>

1. <span data-ttu-id="67925-117">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="67925-117">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="67925-118">Seleccione la carga para la que el envío no se puede confirmar.</span><span class="sxs-lookup"><span data-stu-id="67925-118">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="67925-119">En el panel de acciones, en la pestaña **Cargas** del grupo **Información relacionada**, seleccione **Trabajo**.</span><span class="sxs-lookup"><span data-stu-id="67925-119">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="67925-120">Inspeccione el estado de cada id. de trabajo.</span><span class="sxs-lookup"><span data-stu-id="67925-120">Inspect the status of each work ID.</span></span> <span data-ttu-id="67925-121">Haga un seguimiento de cada id. que no tenga un estado de *Cerrado* o *Cancelado*.</span><span class="sxs-lookup"><span data-stu-id="67925-121">Follow up on each work ID that doesn't have a status of *Closed* or *Canceled*.</span></span>
1. <span data-ttu-id="67925-122">Cuando cada id. de trabajo tiene un estado de *Cerrado* o *Cancelado*, intente nuevamente confirmar el envío.</span><span class="sxs-lookup"><span data-stu-id="67925-122">When every work ID has a status of *Closed* or *Canceled*, try again to confirm the shipment.</span></span>

### <a name="all-shipments-page"></a><span data-ttu-id="67925-123">Página Todos los envíos</span><span class="sxs-lookup"><span data-stu-id="67925-123">All shipments page</span></span>

1. <span data-ttu-id="67925-124">Vaya a **Gestión de almacenes \> Envíos \> Todos los envíos**.</span><span class="sxs-lookup"><span data-stu-id="67925-124">Go to **Warehouse management \> Shipments\> All shipments**.</span></span>
1. <span data-ttu-id="67925-125">Seleccione el envío que no se puede confirmar.</span><span class="sxs-lookup"><span data-stu-id="67925-125">Select the shipment that can't be confirmed.</span></span>
1. <span data-ttu-id="67925-126">En el panel de acciones, en la pestaña **Envíos**, en el grupo **Trabajo**, seleccione **Detalles de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="67925-126">On the Action Pane, on the **Shipments** tab, in the **Work** group, select **Work details**.</span></span>
1. <span data-ttu-id="67925-127">Inspeccione el estado de cada id. de trabajo.</span><span class="sxs-lookup"><span data-stu-id="67925-127">Inspect the status of each work ID.</span></span> <span data-ttu-id="67925-128">Haga un seguimiento de cada id. que no tenga un estado de *Cerrado* o *Cancelado*.</span><span class="sxs-lookup"><span data-stu-id="67925-128">Follow up on each work ID that doesn't have a status of *Closed* or *Canceled*.</span></span>
1. <span data-ttu-id="67925-129">Cuando cada id. de trabajo tiene un estado de *Cerrado* o *Cancelado*, intente nuevamente confirmar el envío.</span><span class="sxs-lookup"><span data-stu-id="67925-129">When every work ID has a status of *Closed* or *Canceled*, try again to confirm the shipment.</span></span>

### <a name="all-work-page"></a><span data-ttu-id="67925-130">Página Todos los trabajos</span><span class="sxs-lookup"><span data-stu-id="67925-130">All work page</span></span>

1. <span data-ttu-id="67925-131">Vaya a **Gestión de almacenes \> Trabajo\> Todos los trabajos**.</span><span class="sxs-lookup"><span data-stu-id="67925-131">Go to **Warehouse management \> Work\> All work**.</span></span>
1. <span data-ttu-id="67925-132">Seleccione el trabajo para el número de pedido para el que no se puede confirmar el envío.</span><span class="sxs-lookup"><span data-stu-id="67925-132">Select the work for the order number that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="67925-133">En el panel de acciones, en la ficha **Envío**, en el grupo **Envío**, seleccione **Confirmar envío**.</span><span class="sxs-lookup"><span data-stu-id="67925-133">On the Action Pane, on the **Shipment** tab, in the **Shipment** group, select **Confirm shipment**.</span></span>
1. <span data-ttu-id="67925-134">Inspeccione el estado de cada id. de trabajo.</span><span class="sxs-lookup"><span data-stu-id="67925-134">Inspect the status of each work ID.</span></span> <span data-ttu-id="67925-135">Haga un seguimiento de cada id. que no tenga un estado de *Cerrado* o *Cancelado*.</span><span class="sxs-lookup"><span data-stu-id="67925-135">Follow up on each work ID that doesn't have a status of *Closed* or *Canceled*.</span></span>
1. <span data-ttu-id="67925-136">Cuando cada id. de trabajo tiene un estado de *Cerrado* o *Cancelado*, intente nuevamente confirmar el envío.</span><span class="sxs-lookup"><span data-stu-id="67925-136">When every work ID has a status of *Closed* or *Canceled*, try again to confirm the shipment.</span></span>
