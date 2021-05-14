---
title: No puede confirmar un envío porque no la cantidad es cero
description: No puede confirmar un envío porque no la cantidad es cero
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
ms.openlocfilehash: 7a06f0651db741a867e1e9fe7dbab841a928c22b
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938545"
---
# <a name="you-cant-confirm-a-shipment-because-there-is-zero-quantity"></a><span data-ttu-id="6265d-103">No puede confirmar un envío porque no la cantidad es cero</span><span class="sxs-lookup"><span data-stu-id="6265d-103">You can't confirm a shipment because there is zero quantity</span></span>

<span data-ttu-id="6265d-104">Código de error: LoadLineWarningUpdatedToZero</span><span class="sxs-lookup"><span data-stu-id="6265d-104">Error code: LoadLineWarningUpdatedToZero</span></span>

## <a name="symptoms"></a><span data-ttu-id="6265d-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="6265d-105">Symptoms</span></span>

<span data-ttu-id="6265d-106">Cuando intenta confirmar un envío, el sistema muestra el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="6265d-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="6265d-107">La línea de carga para el artículo %1 y el envío %2 se ha actualizado para que tenga una cantidad cero debido a la configuración de entrega incompleta que permite no enviar cantidades para este artículo.</span><span class="sxs-lookup"><span data-stu-id="6265d-107">Load line for item %1 and shipment %2 has been updated to have zero quantity due to underdelivery setup allowing not to ship any quantities for this item.</span></span>

<span data-ttu-id="6265d-108">Por lo tanto, no puede confirmar el envío de la carga.</span><span class="sxs-lookup"><span data-stu-id="6265d-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="6265d-109">Causa</span><span class="sxs-lookup"><span data-stu-id="6265d-109">Cause</span></span>

<span data-ttu-id="6265d-110">El sistema evalúa si la cantidad seleccionada se encuentra dentro de los límites esperados, en función de la cantidad seleccionada, la cantidad de la línea de carga y el porcentaje de entrega insuficiente.</span><span class="sxs-lookup"><span data-stu-id="6265d-110">The system evaluates whether the picked quantity is within the expected limits, based on the picked quantity, load line quantity, and underdelivery percentage.</span></span> <span data-ttu-id="6265d-111">Si el sistema encuentra que la cantidad seleccionada en la línea de carga es 0 (cero), no se puede confirmar el envío.</span><span class="sxs-lookup"><span data-stu-id="6265d-111">If the system finds that the picked quantity on the load line is 0 (zero), you can't confirm the shipment.</span></span> <span data-ttu-id="6265d-112">Por ejemplo, este problema puede ocurrir si se canceló el trabajo y el porcentaje de entrega insuficiente en la línea de carga es del 100 por cien.</span><span class="sxs-lookup"><span data-stu-id="6265d-112">For example, this issue might occur if work has been canceled, and the underdelivery percentage on the load line is 100 percent.</span></span>

## <a name="resolution"></a><span data-ttu-id="6265d-113">Resolución</span><span class="sxs-lookup"><span data-stu-id="6265d-113">Resolution</span></span>

<span data-ttu-id="6265d-114">Compruebe que sus líneas de carga para asegurarse de que el porcentaje de entrega insuficiente y las cantidades estén alineadas con el trabajo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="6265d-114">Check your load lines to make sure that the underdelivery percentage and quantities are aligned with the picked work.</span></span>

1. <span data-ttu-id="6265d-115">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="6265d-115">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="6265d-116">Seleccione la carga para la que el envío no se puede confirmar.</span><span class="sxs-lookup"><span data-stu-id="6265d-116">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="6265d-117">En la ficha desplegable **Líneas de carga**, seleccione la línea de carga del artículo que supera el porcentaje de entrega insuficiente.</span><span class="sxs-lookup"><span data-stu-id="6265d-117">On the **Load lines** FastTab, select the load line for the item that exceeds the underdelivery percentage.</span></span>
1. <span data-ttu-id="6265d-118">Ajuste el valor del campo **Entrega insuficiente** o el campo **Cantidad** según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="6265d-118">Adjust the value of the **Underdelivery** field or the **Quantity** field as required.</span></span>

> [!TIP]
> <span data-ttu-id="6265d-119">Si el problema aún no se soluciona, es posible que deba completar más trabajo de selección para los pedidos de ventas o los pedidos de transferencia relacionados hasta que la cantidad disponible esté alineada con la carga o el envío.</span><span class="sxs-lookup"><span data-stu-id="6265d-119">If the issue still isn't fixed, you might have to complete more picking work for the related sales orders or transfer orders until the available quantity is aligned with the load or shipment.</span></span>
