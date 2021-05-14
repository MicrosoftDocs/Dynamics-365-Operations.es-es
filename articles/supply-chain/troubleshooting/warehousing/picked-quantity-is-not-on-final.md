---
title: No puede confirmar un envío porque los artículos no se han recogido
description: No puede confirmar un envío porque los artículos no se han recogido
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 23a517e7769dc86ebec30e4f17c62172a6ad8801
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938546"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a><span data-ttu-id="e1eeb-103">No puede confirmar un envío porque los artículos no se han recogido</span><span class="sxs-lookup"><span data-stu-id="e1eeb-103">You can't confirm a shipment because items haven't been picked</span></span>

<span data-ttu-id="e1eeb-104">Código de error: LoadNotPickedAndMovedToFinalShippingLocation</span><span class="sxs-lookup"><span data-stu-id="e1eeb-104">Error code: LoadNotPickedAndMovedToFinalShippingLocation</span></span>

## <a name="symptoms"></a><span data-ttu-id="e1eeb-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="e1eeb-105">Symptoms</span></span>

<span data-ttu-id="e1eeb-106">Cuando intenta confirmar un envío, el sistema muestra el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="e1eeb-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="e1eeb-107">Algunos de los artículos necesarios para la carga %1 todavía no se han recogido y movido a la ubicación de envío final.</span><span class="sxs-lookup"><span data-stu-id="e1eeb-107">Some of the items that are needed for load %1 have not yet been picked and moved to the final shipping location.</span></span>

<span data-ttu-id="e1eeb-108">Por lo tanto, no puede confirmar el envío de la carga.</span><span class="sxs-lookup"><span data-stu-id="e1eeb-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="e1eeb-109">Causa</span><span class="sxs-lookup"><span data-stu-id="e1eeb-109">Cause</span></span>

<span data-ttu-id="e1eeb-110">La carga o el envío no se puede confirmar en su estado actual porque podría existir una de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="e1eeb-110">The load or shipment can't be confirmed in its current state because one of the following conditions might exist:</span></span>

- <span data-ttu-id="e1eeb-111">El trabajo relacionado aún no se ha seleccionado y trasladado a la ubicación de envío final.</span><span class="sxs-lookup"><span data-stu-id="e1eeb-111">The related work hasn't yet been picked and moved to the final shipping location.</span></span>
- <span data-ttu-id="e1eeb-112">La cantidad de trabajo escogido no coincide con la cantidad de trabajo creada en la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="e1eeb-112">The picked work quantity doesn't match the created work quantity on the load line.</span></span>

## <a name="resolution"></a><span data-ttu-id="e1eeb-113">Resolución</span><span class="sxs-lookup"><span data-stu-id="e1eeb-113">Resolution</span></span>

<span data-ttu-id="e1eeb-114">Compruebe los pedidos de ventas o pedidos de transferencia seleccionados para la carga o envío.</span><span class="sxs-lookup"><span data-stu-id="e1eeb-114">Check the related sales orders or transfer orders for the load or shipment.</span></span> <span data-ttu-id="e1eeb-115">Asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan.</span><span class="sxs-lookup"><span data-stu-id="e1eeb-115">Make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="e1eeb-116">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="e1eeb-116">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="e1eeb-117">Seleccione la carga para la que el envío no se puede confirmar.</span><span class="sxs-lookup"><span data-stu-id="e1eeb-117">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="e1eeb-118">En la ficha desplegable **Líneas de carga**, seleccione la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="e1eeb-118">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="e1eeb-119">Anote el valor del campo **Cantidad de trabajo creado**.</span><span class="sxs-lookup"><span data-stu-id="e1eeb-119">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="e1eeb-120">En el panel de acciones, en la pestaña **Cargas** del grupo **Información relacionada**, seleccione **Trabajo**.</span><span class="sxs-lookup"><span data-stu-id="e1eeb-120">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="e1eeb-121">Verifique que el trabajo se haya completado en la ubicación de envío final y que la cantidad de trabajo recogido coincida con la cantidad de trabajo creada en la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="e1eeb-121">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="e1eeb-122">Repita este procedimiento para todas las líneas de carga para asegurarse de que se cumplan todos los criterios.</span><span class="sxs-lookup"><span data-stu-id="e1eeb-122">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>
