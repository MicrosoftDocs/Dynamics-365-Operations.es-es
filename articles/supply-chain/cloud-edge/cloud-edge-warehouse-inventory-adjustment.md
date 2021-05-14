---
title: Ajuste de inventario de almacén
description: Este tema proporciona información sobre el procesamiento y el diario de ajuste de inventario del almacén cuando utiliza unidades de escalado.
author: perlynne
manager: tfehr
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSInventoryAdjustmentJournal, InventJournalCount
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: be386539ea7addf20256ac2b1f8a2a72736fcbec
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938235"
---
# <a name="warehouse-inventory-adjustment"></a><span data-ttu-id="882c2-103">Ajuste de inventario de almacén</span><span class="sxs-lookup"><span data-stu-id="882c2-103">Warehouse inventory adjustment</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="882c2-104">La función de ajuste de inventario del almacén se utiliza cuando se ejecutan unidades de escalado de borde y en la nube para [cargas de trabajo de fabricación](cloud-edge-workload-manufacturing.md) y [cargas de trabajo de gestión de almacenes](cloud-edge-workload-warehousing.md).</span><span class="sxs-lookup"><span data-stu-id="882c2-104">The Warehouse inventory adjustment feature is used when running cloud and edge scale units for [manufacturing workloads](cloud-edge-workload-manufacturing.md) and [warehouse management workloads](cloud-edge-workload-warehousing.md).</span></span>

<span data-ttu-id="882c2-105">Cuando un trabajador hace un ajuste de inventario usando la aplicación de almacén contra una carga de trabajo de administración de almacén de unidad de escalado, la actualización física disponible debe procesarla el trabajo por lotes **Diario de ajuste de inventario de almacén**, que puede ejecutar y programar yendo a **Gestión de almacenes > Tareas periódicas > Diario de ajuste de inventario de almacén**.</span><span class="sxs-lookup"><span data-stu-id="882c2-105">When a worker does an inventory adjustment using the warehouse app against a scale unit warehouse management workload, the physical on-hand update must be processed by the **Warehouse inventory adjustment journal** batch job, which you run and schedule by going to **Warehouse management > Periodic tasks > Warehouse inventory adjustment journal**.</span></span>

<span data-ttu-id="882c2-106">Los siguientes procesos de trabajo de la aplicación de almacén utilizan actualmente el **Diario de ajuste de inventario de almacén** en las cargas de trabajo de unidad de escalado:</span><span class="sxs-lookup"><span data-stu-id="882c2-106">The following warehouse app work processes currently use the **Warehouse inventory adjustment journal** on scale unit workloads:</span></span>

- <span data-ttu-id="882c2-107">Entrada/salida de ajuste</span><span class="sxs-lookup"><span data-stu-id="882c2-107">Adjustment in/out</span></span>
- <span data-ttu-id="882c2-108">Recuento cíclico</span><span class="sxs-lookup"><span data-stu-id="882c2-108">Cycle counting</span></span>
- <span data-ttu-id="882c2-109">Carga de matrícula de entidad de almacén</span><span class="sxs-lookup"><span data-stu-id="882c2-109">License plate loading</span></span>

<span data-ttu-id="882c2-110">Varias transacciones de inventario se crean como parte de la nube y el borde de un proceso de ajuste de inventario porque las implementaciones de unidades de escala y centro de conectividad comparten los registros de inventario.</span><span class="sxs-lookup"><span data-stu-id="882c2-110">Several inventory transactions are created as part of cloud and edge an inventory adjustment process because the hub and scale unit deployments share the inventory records.</span></span>

## <a name="inventory-adjustment-example"></a><span data-ttu-id="882c2-111">Ejemplo de ajuste de inventario</span><span class="sxs-lookup"><span data-stu-id="882c2-111">Inventory adjustment example</span></span>

<span data-ttu-id="882c2-112">En este ejemplo, un trabajador del almacén ha utilizado la aplicación del almacén para registrar la adición de inventario disponible.</span><span class="sxs-lookup"><span data-stu-id="882c2-112">In this example, a warehouse worker has used the warehouse app to register the adding of on-hand inventory.</span></span>

<span data-ttu-id="882c2-113">Primero, la carga de trabajo de la unidad de escalado crea una transacción de ajuste de inventario de almacén para el ajuste físico positivo, que luego se sincroniza con el centro de conectividad y da como resultado un aumento del inventario disponible en el centro de conectividad.</span><span class="sxs-lookup"><span data-stu-id="882c2-113">First, the scale unit workload creates a warehouse inventory adjustment transaction for the positive physical adjustment, which is then synchronized to the hub and results in an increase of the on-hand inventory on the hub.</span></span>

| <span data-ttu-id="882c2-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="882c2-114">Type</span></span>                                    | <span data-ttu-id="882c2-115">Unidad de escalado</span><span class="sxs-lookup"><span data-stu-id="882c2-115">Scale unit</span></span> | <span data-ttu-id="882c2-116">Dirección</span><span class="sxs-lookup"><span data-stu-id="882c2-116">Direction</span></span> | <span data-ttu-id="882c2-117">Concentrador</span><span class="sxs-lookup"><span data-stu-id="882c2-117">Hub</span></span> |
|-----------------------------------------|------------|-----------|-----|
| <span data-ttu-id="882c2-118">Ajuste de inventario de almacén</span><span class="sxs-lookup"><span data-stu-id="882c2-118">Warehouse inventory adjustment</span></span>          | <span data-ttu-id="882c2-119">+1</span><span class="sxs-lookup"><span data-stu-id="882c2-119">+1</span></span>         | ->        | <span data-ttu-id="882c2-120">+1</span><span class="sxs-lookup"><span data-stu-id="882c2-120">+1</span></span>  |

<span data-ttu-id="882c2-121">A continuación, el concentrador procesa un registro del diario de recuento, que se recibe a través de [mensajes del procesador de mensajes](cloud-edge-message-processor-messages.md).</span><span class="sxs-lookup"><span data-stu-id="882c2-121">The hub then processes a counting journal posting, which is received through [message processor messages](cloud-edge-message-processor-messages.md).</span></span> <span data-ttu-id="882c2-122">Esto actualiza el inventario adicional disponible.</span><span class="sxs-lookup"><span data-stu-id="882c2-122">This updates the additional inventory on hand.</span></span> <span data-ttu-id="882c2-123">Para evitar el doble inventario disponible, el centro crea una transacción de compensación como parte de este proceso y elimina el inventario disponible registrado anteriormente que está relacionado con el ajuste de inventario del almacén.</span><span class="sxs-lookup"><span data-stu-id="882c2-123">To prevent double inventory on hand, the hub creates an offset transaction as part of this process and removes the previously recorded on-hand inventory that is related to the warehouse inventory adjustment.</span></span>

| <span data-ttu-id="882c2-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="882c2-124">Type</span></span>                                    | <span data-ttu-id="882c2-125">Unidad de escalado</span><span class="sxs-lookup"><span data-stu-id="882c2-125">Scale unit</span></span> | <span data-ttu-id="882c2-126">Dirección</span><span class="sxs-lookup"><span data-stu-id="882c2-126">Direction</span></span> | <span data-ttu-id="882c2-127">Concentrador</span><span class="sxs-lookup"><span data-stu-id="882c2-127">Hub</span></span> |
|-----------------------------------------|------------|-----------|-----|
| <span data-ttu-id="882c2-128">Recuento</span><span class="sxs-lookup"><span data-stu-id="882c2-128">Counting</span></span>                                | <span data-ttu-id="882c2-129">+1</span><span class="sxs-lookup"><span data-stu-id="882c2-129">+1</span></span>         | <-        | <span data-ttu-id="882c2-130">+1</span><span class="sxs-lookup"><span data-stu-id="882c2-130">+1</span></span>  |
| <span data-ttu-id="882c2-131">Ajuste de inventario de almacén (compensación)</span><span class="sxs-lookup"><span data-stu-id="882c2-131">Warehouse inventory adjustment (Offset)</span></span> | <span data-ttu-id="882c2-132">-1</span><span class="sxs-lookup"><span data-stu-id="882c2-132">-1</span></span>         | <-        | <span data-ttu-id="882c2-133">-1</span><span class="sxs-lookup"><span data-stu-id="882c2-133">-1</span></span>  |

<span data-ttu-id="882c2-134">Una vez que una unidad de escalado ha creado un **Diario de ajuste de inventario de almacén** en el centro de conectividad, puede revisar el **Diario de recuento** y el **Diario de compensación**, que los crea el centro de conectividad como parte del proceso de ajuste.</span><span class="sxs-lookup"><span data-stu-id="882c2-134">After a scale unit has created a **Warehouse inventory adjustment journal** on the hub, you can review both the **Counting journal** and the **Offset journal**, which are created by the hub as part of the adjustment process.</span></span>

<span data-ttu-id="882c2-135">Puede revisar cada uno de estos asientos de diario y la transacción en Supply Chain Management, realizando los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="882c2-135">You can review each of these journal entries and transaction in Supply Chain Management by doing the following steps:</span></span>

1. <span data-ttu-id="882c2-136">Inicie sesión en la unidad de escalado.</span><span class="sxs-lookup"><span data-stu-id="882c2-136">Sign in on the scale unit.</span></span>
1. <span data-ttu-id="882c2-137">Vaya a **Gestión de almacenes \> Tareas periódicas \> Diario de ajuste de inventario de almacén**.</span><span class="sxs-lookup"><span data-stu-id="882c2-137">Go to **Warehouse management \> Periodic tasks \> Warehouse inventory adjustment journal**.</span></span>
1. <span data-ttu-id="882c2-138">En la página **Diario de ajuste de inventario de almacén**, busque y abra el diario que registró el cambio de inventario disponible.</span><span class="sxs-lookup"><span data-stu-id="882c2-138">On the **Warehouse inventory adjustment journal** page, find and open the journal that recorded the on-hand inventory change.</span></span> <span data-ttu-id="882c2-139">La sección **Líneas de diario** muestra cada ajuste registrado por este diario.</span><span class="sxs-lookup"><span data-stu-id="882c2-139">The **Journal lines** section shows each adjustment recorded by this journal.</span></span>
1. <span data-ttu-id="882c2-140">Inicie sesión en el centro de conectividad.</span><span class="sxs-lookup"><span data-stu-id="882c2-140">Sign in on the hub.</span></span>
1. <span data-ttu-id="882c2-141">Vaya a **Gestión de almacenes \> Tareas periódicas \> Diario de ajuste de inventario de almacén**.</span><span class="sxs-lookup"><span data-stu-id="882c2-141">Go to **Warehouse management \> Periodic tasks \> Warehouse inventory adjustment journal**.</span></span>
1. <span data-ttu-id="882c2-142">En la página **Diario de ajuste de inventario de almacén**, debería ver el mismo diario enumerado si el centro de conectividad y la unidad de escalado se han sincronizado.</span><span class="sxs-lookup"><span data-stu-id="882c2-142">On the **Warehouse inventory adjustment journal** page, you should see the same journal listed if the hub and scale unit have synced.</span></span>
1. <span data-ttu-id="882c2-143">Abra el diario.</span><span class="sxs-lookup"><span data-stu-id="882c2-143">Open the journal.</span></span> <span data-ttu-id="882c2-144">Si los [mensajes del procesador de mensajes](cloud-edge-message-processor-messages.md) se han procesado, verá enlaces al **Diario de recuento** y el **Diario de compensación** en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="882c2-144">If the [message processor messages](cloud-edge-message-processor-messages.md) have been processed, you will see links to the **Counting journal** and the **Offset journal** in the header.</span></span>
    - <span data-ttu-id="882c2-145">El **Diario de recuento** debe mostrar los mismos valores de dimensión que las líneas del diario.</span><span class="sxs-lookup"><span data-stu-id="882c2-145">The **Counting journal** should show the same dimension values as the journal lines.</span></span>
    - <span data-ttu-id="882c2-146">El **Diario de compensación** debe mostrar la compensación, que elimina el doble ajuste de inventario.</span><span class="sxs-lookup"><span data-stu-id="882c2-146">The **Offset journal** should show the offset, which removes the double inventory adjustment.</span></span>
    > [!NOTE]
    > <span data-ttu-id="882c2-147">Cuando se completa toda la sincronización y el procesamiento, el **Diario de recuento** y el **Diario de compensación** se vueven a sincronizar con la unidad de escalado.</span><span class="sxs-lookup"><span data-stu-id="882c2-147">When all syncing and processing is complete, the **Counting journal** and the **Offset journal** are synced back to the scale unit.</span></span> <span data-ttu-id="882c2-148">Estos también se pueden ver en la página **Diario de ajuste de inventario de almacén** correspondiente.</span><span class="sxs-lookup"><span data-stu-id="882c2-148">These can also be viewed from the relevant **Warehouse inventory adjustment journal** page.</span></span>
