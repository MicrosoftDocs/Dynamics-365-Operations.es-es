---
title: Solución de problemas de reservas en gestión de almacenes
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con reservas de almacenes en Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a1ea23059d56ebf387a95a1378e2a3cd47556d5f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993890"
---
# <a name="troubleshoot-reservations-in-warehouse-management"></a><span data-ttu-id="7faa8-103">Solución de problemas de reservas en gestión de almacenes</span><span class="sxs-lookup"><span data-stu-id="7faa8-103">Troubleshoot reservations in warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7faa8-104">Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con reservas de almacenes en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7faa8-104">This topic describes how to fix common issues that you might encounter while you work with warehouse reservations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations"></a><span data-ttu-id="7faa8-105">Aparece el mensaje de error: "No se pueden quitar las reservas porque se ha creado un trabajo que depende de ellas".</span><span class="sxs-lookup"><span data-stu-id="7faa8-105">I receive the following error message: "Reservations cannot be removed because there is work created which relies on the reservations."</span></span>

### <a name="issue-description"></a><span data-ttu-id="7faa8-106">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="7faa8-106">Issue description</span></span>

<span data-ttu-id="7faa8-107">No se puede anular la reserva de inventario en una línea de ventas, porque hay trabajo abierto contra la línea.</span><span class="sxs-lookup"><span data-stu-id="7faa8-107">You can't unreserve inventory on a sales line, because there is open work against the line.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="7faa8-108">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="7faa8-108">Issue resolution</span></span>

<span data-ttu-id="7faa8-109">Investigar si existe trabajo de grupo de empaque abierto para llevar el artículo de una estación de empaque a otra ubicación (como *Baydoor*).</span><span class="sxs-lookup"><span data-stu-id="7faa8-109">Investigate whether open packing group work exists to bring the item from a packing station to another location (such as *Baydoor*).</span></span> <span data-ttu-id="7faa8-110">Revise los registros en las páginas **Registro del historial de creación de trabajos** y **Detalles del trabajo** para determinar qué está reservando físicamente el inventario, y luego completar o eliminar el trabajo para liberar la reserva.</span><span class="sxs-lookup"><span data-stu-id="7faa8-110">Review the records on the **Work creation history log** and **Work details** pages to determine what is physically reserving the inventory, and then complete or delete the work to free up the reservation.</span></span>

## <a name="i-receive-the-following-error-message-inventory-quantity--1-could-not-be-updated-due-to-insufficient-inventory-transactions-for-item-2"></a><span data-ttu-id="7faa8-111">Recibo el siguiente mensaje de error: "Cantidad de inventario -%1 no se pudo actualizar debido a transacciones de inventario insuficientes para el artículo %2...."</span><span class="sxs-lookup"><span data-stu-id="7faa8-111">I receive the following error message: "Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2...."</span></span>

### <a name="issue-description"></a><span data-ttu-id="7faa8-112">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="7faa8-112">Issue description</span></span>

<span data-ttu-id="7faa8-113">Este problema puede ocurrir si el sistema no puede actualizar una cantidad de inventario porque no hay suficientes transacciones de inventario que tengan las dimensiones especificadas.</span><span class="sxs-lookup"><span data-stu-id="7faa8-113">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="7faa8-114">A continuación se muestra el texto completo del mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="7faa8-114">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="7faa8-115">Cantidad de inventario -%1 no se pudo actualizar debido a transacciones de inventario insuficientes para el artículo %2 con dimensiones Tamaño=%3, Color=%4, Adiciones=%5, Sitio=%6, Almacén=%7, Ubicación=%8, Estado de inventario=Disponible, Matrícula=%9, Número de lote=%10 para ID de referencia %11 en ID de lote %12.</span><span class="sxs-lookup"><span data-stu-id="7faa8-115">Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2 with dimensions Size=%3, Color=%4, Additions=%5, Site=%6, Warehouse=%7, Location=%8, Inventory status=Available, License plate=%9, Batch number=%10 for reference ID %11 on Lot ID %12.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="7faa8-116">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="7faa8-116">Issue resolution</span></span>

<span data-ttu-id="7faa8-117">Asegúrese de que ninguna transacción de inventario esté reservando físicamente la cantidad.</span><span class="sxs-lookup"><span data-stu-id="7faa8-117">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="7faa8-118">Por ejemplo, estas transacciones pueden abrir pedidos de calidad, registros de bloqueo de inventario o pedidos de salida.</span><span class="sxs-lookup"><span data-stu-id="7faa8-118">For example, these transactions might open quality orders, inventory blocking records, or output orders.</span></span>

## <a name="i-receive-the-following-error-message-physical-on-handcannot-be-reserved-because-only-000-are-available-in-the-inventory"></a><span data-ttu-id="7faa8-119">Recibo el siguiente mensaje de error: "Físico disponible ... no se puede reservar porque solo 0.00 están disponibles en el inventario".</span><span class="sxs-lookup"><span data-stu-id="7faa8-119">I receive the following error message: "Physical on-hand...cannot be reserved because only 0.00 are available in the inventory."</span></span>

### <a name="issue-description"></a><span data-ttu-id="7faa8-120">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="7faa8-120">Issue description</span></span>

<span data-ttu-id="7faa8-121">Este problema puede ocurrir si el sistema no puede actualizar una cantidad de inventario porque no hay suficientes transacciones de inventario que tengan las dimensiones especificadas.</span><span class="sxs-lookup"><span data-stu-id="7faa8-121">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="7faa8-122">A continuación se muestra el texto completo del mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="7faa8-122">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="7faa8-123">Sitio físico disponible=%1, Almacén=%2, Estado de inventario=Disponible, Número de lote=%3, Propietario=%4: %5 no se puede reservar porque solo 0.00 están disponibles en el inventario.</span><span class="sxs-lookup"><span data-stu-id="7faa8-123">Physical on-hand Site=%1, Warehouse=%2, Inventory status=Available, Batch number=%3, Owner=%4: %5 cannot be reserved because only 0.00 are available in the inventory.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="7faa8-124">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="7faa8-124">Issue resolution</span></span>

<span data-ttu-id="7faa8-125">Este problema probablemente se deba al trabajo abierto.</span><span class="sxs-lookup"><span data-stu-id="7faa8-125">This issue is probably caused by open work.</span></span> <span data-ttu-id="7faa8-126">Completar el trabajo o recibir sin creación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7faa8-126">Either complete the work or receive without work creation.</span></span> <span data-ttu-id="7faa8-127">Asegúrese de que ninguna transacción de inventario esté reservando físicamente la cantidad.</span><span class="sxs-lookup"><span data-stu-id="7faa8-127">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="7faa8-128">Por ejemplo, estas transacciones pueden ser pedidos de calidad, registros de bloqueo de inventario o pedidos de salida abiertos.</span><span class="sxs-lookup"><span data-stu-id="7faa8-128">For example, these transactions might be open quality orders, inventory blocking records, or output orders.</span></span>

## <a name="i-receive-the-following-error-message-to-be-assigned-to-wave-load-lines-must-specify-the-dimensions-above-the-location-to-assign-these-dimensions-reserve-and-recreate-the-load-line"></a><span data-ttu-id="7faa8-129">Recibo el siguiente mensaje de error: "Para ser asignado a la ola, las líneas de carga deben especificar las dimensiones por encima de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="7faa8-129">I receive the following error message: "To be assigned to wave, load lines must specify the dimensions above the location.</span></span> <span data-ttu-id="7faa8-130">Para asignar estas dimensiones, reserve y vuelva a crear la línea de carga ".</span><span class="sxs-lookup"><span data-stu-id="7faa8-130">To assign these dimensions, reserve and recreate the load line."</span></span>

### <a name="issue-description"></a><span data-ttu-id="7faa8-131">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="7faa8-131">Issue description</span></span>

<span data-ttu-id="7faa8-132">Cuando utiliza un artículo que tiene una jerarquía de reserva "lote por encima" (con la dimensión **Número de lote** colocada *sobre* la dimensión **Ubicación**), el comando **Liberar al almacén** en la página **Banco de trabajo de planificación de carga** para una cantidad parcial no funciona.</span><span class="sxs-lookup"><span data-stu-id="7faa8-132">When you use an item that has a "batch above" reservation hierarchy (with the **Batch number** dimension placed *above* the **Location** dimension), the **Release to warehouse** command on the **Load planning workbench** page for a partial quantity doesn't work.</span></span> <span data-ttu-id="7faa8-133">Recibe este mensaje de error y no se crea ningún trabajo para la cantidad parcial.</span><span class="sxs-lookup"><span data-stu-id="7faa8-133">You receive this error message, and no work is created for the partial quantity.</span></span>

<span data-ttu-id="7faa8-134">Sin embargo, si utiliza un artículo que tiene una jerarquía de reserva "lote por debajo" (con la dimensión **Número de lote** colocada *bajo* la dimensión **Ubicación**), puede liberar una carga desde la página **Banco de trabajo de planificación de carga** para una cantidad parcial.</span><span class="sxs-lookup"><span data-stu-id="7faa8-134">However, if you use an item that has a "batch below" reservation hierarchy (with the **Batch number** dimension placed *below* the **Location** dimension), you can release a load from the **Load planning workbench** page for a partial quantity.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="7faa8-135">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="7faa8-135">Issue resolution</span></span>

<span data-ttu-id="7faa8-136">Este comportamiento se debe al diseño.</span><span class="sxs-lookup"><span data-stu-id="7faa8-136">This behavior is by design.</span></span> <span data-ttu-id="7faa8-137">Si pone una dimensión por encima de la dimensión **Ubicación** en la jerarquía de reservas, debe especificarse antes del lanzamiento al almacén.</span><span class="sxs-lookup"><span data-stu-id="7faa8-137">If you put a dimension above the **Location** dimension in the reservation hierarchy, it must be specified before the release to the warehouse.</span></span> <span data-ttu-id="7faa8-138">Microsoft ha evaluado este problema y ha determinado que es una limitación de funciones durante las versiones al almacén desde el entorno de trabajo de planificación de carga.</span><span class="sxs-lookup"><span data-stu-id="7faa8-138">Microsoft has evaluated this issue and has determined that it's a feature limitation during releases to the warehouse from the load planning workbench.</span></span> <span data-ttu-id="7faa8-139">Las cantidades parciales no se pueden liberar si no se especifican una o más dimensiones sobre **Ubicación**.</span><span class="sxs-lookup"><span data-stu-id="7faa8-139">Partial quantities can't be released if one or more dimensions above **Location** aren't specified.</span></span>

<span data-ttu-id="7faa8-140">Para obtener más información, consulte [Directiva de reserva de dimensión de nivel de almacén flexible](flexible-warehouse-level-dimension-reservation.md).</span><span class="sxs-lookup"><span data-stu-id="7faa8-140">For more information, see [Flexible warehouse-level dimension reservation policy](flexible-warehouse-level-dimension-reservation.md).</span></span>
