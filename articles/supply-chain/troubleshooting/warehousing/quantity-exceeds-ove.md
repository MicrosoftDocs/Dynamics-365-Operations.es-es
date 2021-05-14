---
title: No se puede confirmar un envío porque la cantidad supera el porcentaje de sobreentrega
description: No se puede confirmar un envío porque la cantidad supera el porcentaje de sobreentrega
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
ms.openlocfilehash: c9b5ba8dedb927ee049d7e53e9a666902f563f49
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938549"
---
# <a name="you-cant-confirm-a-shipment-because-the-quantity-exceeds-the-overdelivery-percentage"></a><span data-ttu-id="e4f2b-103">No se puede confirmar un envío porque la cantidad supera el porcentaje de sobreentrega</span><span class="sxs-lookup"><span data-stu-id="e4f2b-103">You can't confirm a shipment because the quantity exceeds the overdelivery percentage</span></span>

<span data-ttu-id="e4f2b-104">Código de error: WAX1687</span><span class="sxs-lookup"><span data-stu-id="e4f2b-104">Error code: WAX1687</span></span>

## <a name="symptoms"></a><span data-ttu-id="e4f2b-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="e4f2b-105">Symptoms</span></span>

<span data-ttu-id="e4f2b-106">Cuando intenta confirmar un envío, el sistema muestra el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="e4f2b-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="e4f2b-107">El envío para carga %1 no se pudo confirmar porque la cantidad del artículo %2 supera el porcentaje definido para la sobreentrega.</span><span class="sxs-lookup"><span data-stu-id="e4f2b-107">The shipment for load %1 could not be confirmed because the quantity for item %2 exceeds the percentage that is defined for overdelivery.</span></span>

<span data-ttu-id="e4f2b-108">Por lo tanto, no puede confirmar el envío de la carga.</span><span class="sxs-lookup"><span data-stu-id="e4f2b-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="e4f2b-109">Causa</span><span class="sxs-lookup"><span data-stu-id="e4f2b-109">Cause</span></span>

<span data-ttu-id="e4f2b-110">La cantidad de carga o envío se ha recogido solo parcialmente.</span><span class="sxs-lookup"><span data-stu-id="e4f2b-110">The quantity of the load or shipment has been only partially picked.</span></span> <span data-ttu-id="e4f2b-111">La cantidad actualmente excede la cantidad seleccionada en un porcentaje que está fuera del porcentaje de sobreentrega permitido.</span><span class="sxs-lookup"><span data-stu-id="e4f2b-111">The quantity currently exceeds the picked quantity by a percentage that is outside the allowed overdelivery percentage.</span></span>

## <a name="resolution"></a><span data-ttu-id="e4f2b-112">Resolución</span><span class="sxs-lookup"><span data-stu-id="e4f2b-112">Resolution</span></span>

<span data-ttu-id="e4f2b-113">Para solucionar este problema, complete una o más de las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="e4f2b-113">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="e4f2b-114">Establezca la cantidad de la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="e4f2b-114">Set the load line quantity.</span></span>
- <span data-ttu-id="e4f2b-115">Establezca el porcentaje de sobreentrega.</span><span class="sxs-lookup"><span data-stu-id="e4f2b-115">Set the overdelivery percentage.</span></span>

### <a name="set-the-load-line-quantity"></a><span data-ttu-id="e4f2b-116">Establezcer la cantidad de línea de carga</span><span class="sxs-lookup"><span data-stu-id="e4f2b-116">Set the load line quantity</span></span>

<span data-ttu-id="e4f2b-117">Para definir la cantidad de línea de carga, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e4f2b-117">To set the load line quantity, follow these steps.</span></span>

1. <span data-ttu-id="e4f2b-118">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="e4f2b-118">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="e4f2b-119">Seleccione la carga para la que el envío no se puede confirmar.</span><span class="sxs-lookup"><span data-stu-id="e4f2b-119">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="e4f2b-120">En la ficha desplegable **Líneas de carga**, seleccione la línea de carga del artículo que supera el porcentaje de sobreentrega.</span><span class="sxs-lookup"><span data-stu-id="e4f2b-120">On the **Load lines** FastTab, select the load line for the item that exceeds the overdelivery percentage.</span></span>
1. <span data-ttu-id="e4f2b-121">En la ficha desplegable **Detalles de línea**, seleccione **Pedido**.</span><span class="sxs-lookup"><span data-stu-id="e4f2b-121">On the **Line details** FastTab, select **Order**.</span></span>
1. <span data-ttu-id="e4f2b-122">En el campo **Cantidad**, establezca el valor en la cantidad recogida (es decir, en el valor **Cantidad creada por trabajo**), para que pueda ocurrir la confirmación del envío.</span><span class="sxs-lookup"><span data-stu-id="e4f2b-122">In the **Quantity** field, set the value to the picked quantity (that is, to the **Work created quantity** value), so that shipment confirmation can occur.</span></span>

### <a name="set-the-overdelivery-percentage"></a><span data-ttu-id="e4f2b-123">Establezcer el porcentaje de sobreentrega</span><span class="sxs-lookup"><span data-stu-id="e4f2b-123">Set the overdelivery percentage</span></span>

<span data-ttu-id="e4f2b-124">Para establecer el porcentaje de infraentrega, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e4f2b-124">To set the underdelivery percentage, follow these steps.</span></span>

1. <span data-ttu-id="e4f2b-125">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="e4f2b-125">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="e4f2b-126">Seleccione la carga para la que el envío no se puede confirmar.</span><span class="sxs-lookup"><span data-stu-id="e4f2b-126">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="e4f2b-127">En la ficha desplegable **Líneas de carga**, seleccione la línea de carga del artículo que supera el porcentaje de sobreentrega.</span><span class="sxs-lookup"><span data-stu-id="e4f2b-127">On the **Load lines** FastTab, select the load line for the item that exceeds the overdelivery percentage.</span></span>
1. <span data-ttu-id="e4f2b-128">En la ficha desplegable **Detalles de línea**, seleccione **General**.</span><span class="sxs-lookup"><span data-stu-id="e4f2b-128">On the **Line details** FastTab, select **General**.</span></span>
1. <span data-ttu-id="e4f2b-129">En el campo **Sobreentrega**, establezca el valor en un porcentaje mayor que se adapte a la cantidad que se ha recogido frente a la cantidad de carga, de modo que pueda producirse la confirmación del envío.</span><span class="sxs-lookup"><span data-stu-id="e4f2b-129">In the **Overdelivery** field, set the value to a larger percentage that accommodates the quantity that has been picked against the load quantity, so that shipment confirmation can occur.</span></span>
