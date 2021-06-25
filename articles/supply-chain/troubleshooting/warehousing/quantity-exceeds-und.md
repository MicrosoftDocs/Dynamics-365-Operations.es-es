---
title: No se puede confirmar un envío porque la cantidad supera el porcentaje de infraentrega
description: No se puede confirmar un envío porque la cantidad supera el porcentaje de infraentrega
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm,WHSContainerCloseDiag_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 625003731485329b93f5f9454ccece580c889613
ms.sourcegitcommit: c2c6d687a89bc1534c029109315c23e92865b63b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2021
ms.locfileid: "6123828"
---
# <a name="you-cant-confirm-a-shipment-because-the-quantity-exceeds-the-underdelivery-percentage"></a><span data-ttu-id="4ae10-103">No se puede confirmar un envío porque la cantidad supera el porcentaje de infraentrega</span><span class="sxs-lookup"><span data-stu-id="4ae10-103">You can't confirm a shipment because the quantity exceeds the underdelivery percentage</span></span>

<span data-ttu-id="4ae10-104">Código de error: WAX1686</span><span class="sxs-lookup"><span data-stu-id="4ae10-104">Error code: WAX1686</span></span>

## <a name="symptoms"></a><span data-ttu-id="4ae10-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="4ae10-105">Symptoms</span></span>

<span data-ttu-id="4ae10-106">Cuando intenta confirmar un envío, el sistema muestra el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="4ae10-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="4ae10-107">El envío para carga %1 no se pudo confirmar porque la cantidad del artículo %2 supera el porcentaje definido para la infraentrega.</span><span class="sxs-lookup"><span data-stu-id="4ae10-107">The shipment for load %1 could not be confirmed because the quantity for item %2 exceeds the percentage that is defined for underdelivery.</span></span>

<span data-ttu-id="4ae10-108">Por lo tanto, no puede confirmar el envío de la carga.</span><span class="sxs-lookup"><span data-stu-id="4ae10-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="4ae10-109">Causa</span><span class="sxs-lookup"><span data-stu-id="4ae10-109">Cause</span></span>

<span data-ttu-id="4ae10-110">La cantidad de carga o envío se ha recogido solo parcialmente.</span><span class="sxs-lookup"><span data-stu-id="4ae10-110">The quantity of the load or shipment has been only partially picked.</span></span> <span data-ttu-id="4ae10-111">La cantidad es actualmente inferior a la cantidad seleccionada en un porcentaje que está fuera del porcentaje de infraentrega permitido.</span><span class="sxs-lookup"><span data-stu-id="4ae10-111">The quantity is currently less than the picked quantity by a percentage that is outside the allowed underdelivery percentage.</span></span>

## <a name="resolution"></a><span data-ttu-id="4ae10-112">Resolución</span><span class="sxs-lookup"><span data-stu-id="4ae10-112">Resolution</span></span>

<span data-ttu-id="4ae10-113">Para solucionar este problema, complete una o más de las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="4ae10-113">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="4ae10-114">Establezca la cantidad de la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="4ae10-114">Set the load line quantity.</span></span>
- <span data-ttu-id="4ae10-115">Establezca el porcentaje de infraentrega.</span><span class="sxs-lookup"><span data-stu-id="4ae10-115">Set the underdelivery percentage.</span></span>

### <a name="set-the-load-line-quantity"></a><span data-ttu-id="4ae10-116">Establezcer la cantidad de línea de carga</span><span class="sxs-lookup"><span data-stu-id="4ae10-116">Set the load line quantity</span></span>

<span data-ttu-id="4ae10-117">Para definir la cantidad de línea de carga, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="4ae10-117">To set the load line quantity, follow these steps.</span></span>

1. <span data-ttu-id="4ae10-118">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="4ae10-118">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="4ae10-119">Seleccione la carga para la que el envío no se puede confirmar.</span><span class="sxs-lookup"><span data-stu-id="4ae10-119">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="4ae10-120">En la ficha desplegable **Líneas de carga**, seleccione la línea de carga del artículo que supera el porcentaje de entrega insuficiente.</span><span class="sxs-lookup"><span data-stu-id="4ae10-120">On the **Load lines** FastTab, select the load line for the item that exceeds the underdelivery percentage.</span></span>
1. <span data-ttu-id="4ae10-121">En la ficha desplegable **Detalles de línea**, seleccione **Pedido**.</span><span class="sxs-lookup"><span data-stu-id="4ae10-121">On the **Line details** FastTab, select **Order**.</span></span>
1. <span data-ttu-id="4ae10-122">En el campo **Cantidad**, establezca el valor en la cantidad recogida (es decir, en el valor **Cantidad creada por trabajo**), para que pueda ocurrir la confirmación del envío.</span><span class="sxs-lookup"><span data-stu-id="4ae10-122">In the **Quantity** field, set the value to the picked quantity (that is, to the **Work created quantity** value), so that shipment confirmation can occur.</span></span>

### <a name="set-the-underdelivery-percentage"></a><span data-ttu-id="4ae10-123">Establecer el porcentaje de infraentrega</span><span class="sxs-lookup"><span data-stu-id="4ae10-123">Set the underdelivery percentage</span></span>

<span data-ttu-id="4ae10-124">Para establecer el porcentaje de infraentrega, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="4ae10-124">To set the underdelivery percentage, follow these steps.</span></span>

1. <span data-ttu-id="4ae10-125">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="4ae10-125">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="4ae10-126">Seleccione la carga para la que el envío no se puede confirmar.</span><span class="sxs-lookup"><span data-stu-id="4ae10-126">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="4ae10-127">En la ficha desplegable **Líneas de carga**, seleccione la línea de carga del artículo que supera el porcentaje de entrega insuficiente.</span><span class="sxs-lookup"><span data-stu-id="4ae10-127">On the **Load lines** FastTab, select the load line for the item that exceeds the underdelivery percentage.</span></span>
1. <span data-ttu-id="4ae10-128">En la ficha desplegable **Detalles de línea**, seleccione **General**.</span><span class="sxs-lookup"><span data-stu-id="4ae10-128">On the **Line details** FastTab, select **General**.</span></span>
1. <span data-ttu-id="4ae10-129">En el campo **Infraentrega**, establezca el valor en un porcentaje mayor que se adapte a la cantidad que se ha recogido frente a la cantidad de carga, de modo que pueda producirse la confirmación del envío.</span><span class="sxs-lookup"><span data-stu-id="4ae10-129">In the **Underdelivery** field, set the value to a larger percentage that accommodates the quantity that has been picked against the load quantity, so that shipment confirmation can occur.</span></span>
