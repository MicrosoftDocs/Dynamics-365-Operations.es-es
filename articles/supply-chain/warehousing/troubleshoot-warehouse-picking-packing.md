---
title: Solucionar problemas de picking y embalaje
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al Seleccionar y empaquetar en Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 1a54fa9dc21fb1691d74905a1215f4dfea31f136
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828139"
---
# <a name="troubleshoot-picking-and-packing"></a><span data-ttu-id="a2fb4-103">Solucionar problemas de picking y embalaje</span><span class="sxs-lookup"><span data-stu-id="a2fb4-103">Troubleshoot picking and packing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a2fb4-104">Este tema describe cómo solucionar problemas comunes que pueden surgir al Seleccionar y empaquetar en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-104">This topic describes how to fix common issues that you might encounter while you pick and pack in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-dimension-location-cant-be-left-blank-if-dimension-serial-number-is-set"></a><span data-ttu-id="a2fb4-105">Recibo el siguiente mensaje de error: "La ubicación de la dimensión no se puede dejar en blanco si se establece el número de serie de la dimensión".</span><span class="sxs-lookup"><span data-stu-id="a2fb4-105">I receive the following error message: "Dimension location can't be left blank if dimension serial number is set."</span></span>

### <a name="issue-description"></a><span data-ttu-id="a2fb4-106">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="a2fb4-106">Issue description</span></span>

<span data-ttu-id="a2fb4-107">Recibirá este mensaje de error si crea una orden de transferencia para un elemento en serie utilizando un almacén que está habilitado para la administración avanzada de almacenes (WMS) y, luego, una vez completado el trabajo, intenta confirmar el envío.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-107">You receive this error message if you create a transfer order for a serial item by using a warehouse that is enabled for advanced warehouse management (WMS), and then, after the work is completed, you try to confirm the shipment.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a2fb4-108">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="a2fb4-108">Issue resolution</span></span>

<span data-ttu-id="a2fb4-109">El campo **Ubicación de recibo predeterminada** está en blanco para un almacén de tránsito del almacén "desde".</span><span class="sxs-lookup"><span data-stu-id="a2fb4-109">The **Default receipt location** field is blank for a transit warehouse of the "from" warehouse.</span></span> <span data-ttu-id="a2fb4-110">Para solucionar este problema, especifique una ubicación de recepción predeterminada en el almacén de tránsito.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-110">To fix this issue, specify a default receipt location in the transit warehouse.</span></span> <span data-ttu-id="a2fb4-111">Asegúrese de que esta ubicación esté controlada por matrículas.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-111">Make sure that this location is license plate–controlled.</span></span>

## <a name="i-receive-the-following-error-message-invalid-license-plate"></a><span data-ttu-id="a2fb4-112">Recibo el siguiente mensaje de error: "Matrícula no válida".</span><span class="sxs-lookup"><span data-stu-id="a2fb4-112">I receive the following error message: "Invalid license plate."</span></span>

### <a name="issue-description"></a><span data-ttu-id="a2fb4-113">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="a2fb4-113">Issue description</span></span>

<span data-ttu-id="a2fb4-114">Recibe este mensaje de error en la aplicación móvil Warehouse Management cuando escanea la identificación de una placa de matrícula.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-114">You receive this error message in the Warehouse Management mobile app when you scan a license plate ID.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a2fb4-115">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="a2fb4-115">Issue resolution</span></span>

<span data-ttu-id="a2fb4-116">Asegúrese de que la identificación de la placa de matrícula exista en la tabla de matrículas y que los artículos y las cantidades en la matrícula estén disponibles (en otras palabras, no estén bloqueados).</span><span class="sxs-lookup"><span data-stu-id="a2fb4-116">Make sure that the license plate ID exists in the license plates table, and that the items and quantities on the license plate are available (in other words, they aren't blocked).</span></span>

## <a name="i-receive-the-following-error-message-field-load-weight-1-can-only-contain-positive-numbers-update-has-been-canceled"></a><span data-ttu-id="a2fb4-117">Recibo el siguiente mensaje de error: "El campo 'Peso de carga'(=-%1) solo puede contener números positivos.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-117">I receive the following error message: "Field 'Load weight'(=-%1) can only contain positive numbers.</span></span> <span data-ttu-id="a2fb4-118">Se ha cancelado la actualización".</span><span class="sxs-lookup"><span data-stu-id="a2fb4-118">Update has been canceled."</span></span>

### <a name="issue-description"></a><span data-ttu-id="a2fb4-119">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="a2fb4-119">Issue description</span></span>

<span data-ttu-id="a2fb4-120">Recibirá este mensaje de error si hay trabajo abierto cuando procesa el trabajo desde las ubicaciones de embalaje a las ubicaciones de preparación, o desde las ubicaciones de preparación a las ubicaciones de muelle.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-120">You receive this error message if there is open work when you process work from packing locations to staging locations, or from staging locations to dock locations.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a2fb4-121">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="a2fb4-121">Issue resolution</span></span>

<span data-ttu-id="a2fb4-122">Para solucionar este problema, vaya a **Administración del sistema \> Tareas periódicas \> Base de datos \> Verificación de consistencia** y ejecute el proceso para **Comprobación de la coherencia del peso de la carga del almacén**.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-122">To fix this issue, go to **System administration \> Periodic tasks \> Database \> Consistency check**, and run the process for **Warehouse load weight consistency check**.</span></span>

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a><span data-ttu-id="a2fb4-123">Recibo el siguiente mensaje de error: "La cantidad no es válida para la unidad %1".</span><span class="sxs-lookup"><span data-stu-id="a2fb4-123">I receive the following error message: "The quantity is not valid for unit %1."</span></span>

### <a name="issue-description"></a><span data-ttu-id="a2fb4-124">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="a2fb4-124">Issue description</span></span>

<span data-ttu-id="a2fb4-125">Recibe este mensaje de error cuando intenta realizar una *selección dividida* en varios lotes.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-125">You receive this error message when you try to perform a *split pick* across multiple batches.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a2fb4-126">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="a2fb4-126">Issue resolution</span></span>

<span data-ttu-id="a2fb4-127">El trabajador del almacén debe utilizar el proceso de *picking corto* en la aplicación móvil Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-127">The warehouse worker must use the *Short picking* process in the Warehouse Management mobile app.</span></span> <span data-ttu-id="a2fb4-128">Si está intentando elegir varios lotes de la misma ubicación, también puede utilizar la opción **Lleno** en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-128">If you're trying to pick multiple batches from the same location, you can also use the **Full** option in the app.</span></span>

## <a name="i-cant-move-inventory-to-a-location-that-is-license-platecontrolled"></a><span data-ttu-id="a2fb4-129">No puedo mover el inventario a una ubicación que esté controlada por matrículas.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-129">I can't move inventory to a location that is license plate–controlled.</span></span>

### <a name="issue-description"></a><span data-ttu-id="a2fb4-130">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="a2fb4-130">Issue description</span></span>

<span data-ttu-id="a2fb4-131">No puede reducir las cantidades recogidas en una carga.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-131">You can't reduce picked quantities on a load.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a2fb4-132">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="a2fb4-132">Issue resolution</span></span>

<span data-ttu-id="a2fb4-133">En versiones anteriores, no puede reducir las cantidades recogidas en una carga.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-133">In earlier versions, you can't reduce picked quantities on a load.</span></span> <span data-ttu-id="a2fb4-134">Sin embargo, ahora puede anular la selección a una ubicación controlada por matrícula.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-134">However, you can now unpick to a license plate–controlled location.</span></span> <span data-ttu-id="a2fb4-135">Debe especificar tanto un valor de **Ubicación** como un valor de **Matrícula** para la línea de carga en la página **Reducir la cantidad recogida**.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-135">You must specify both a **Location** value and a **License plate** value for the load line on the **Reduce picked quantity** page.</span></span>

## <a name="can-i-print-a-delivery-note-or-packing-content-by-warehouse"></a><span data-ttu-id="a2fb4-136">¿Puedo imprimir un albarán de entrega o el contenido del embalaje por almacén?</span><span class="sxs-lookup"><span data-stu-id="a2fb4-136">Can I print a delivery note or packing content by warehouse?</span></span>

### <a name="issue-description"></a><span data-ttu-id="a2fb4-137">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="a2fb4-137">Issue description</span></span>

<span data-ttu-id="a2fb4-138">Quiere imprimir una nota de entrega o el contenido del embalaje por almacén o sitio en la página **Actualización de línea de plantilla de auditoría de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-138">You want to print a delivery note or packing content by warehouse or site on the **Work audit template line update** page.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a2fb4-139">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="a2fb4-139">Issue resolution</span></span>

<span data-ttu-id="a2fb4-140">Cuando imprime un documento utilizando la configuración de administración de impresión, limite el alcance (sitio/almacén) a través de la administración de impresión en lugar de seleccionar **Editar la configuración de impresión** en la página **Actualización de línea de plantilla de auditoría de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-140">When you print a document by using Print management settings, limit the scope (site/warehouse) through Print management instead of by selecting **Edit print settings** on the **Work audit template line update** page.</span></span>

## <a name="i-cant-cancel-a-packing-slip-after-its-posted-from-a-sales-order"></a><span data-ttu-id="a2fb4-141">No puedo cancelar un albarán después de que se haya registrado en un pedido de cliente.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-141">I can't cancel a packing slip after it's posted from a sales order.</span></span>

### <a name="issue-description"></a><span data-ttu-id="a2fb4-142">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="a2fb4-142">Issue description</span></span>

<span data-ttu-id="a2fb4-143">Cuando los procesos de recolección y envío están habilitados para WMS, no puede cancelar un albarán después de que se haya publicado desde un pedido de cliente.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-143">When picking and shipping processes are enabled for WMS, you can't cancel a packing slip after it's posted from a sales order.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a2fb4-144">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="a2fb4-144">Issue resolution</span></span>

<span data-ttu-id="a2fb4-145">Para corregir las notas de empaque publicadas para los artículos que están habilitados para WMS, la publicación debe ocurrir desde la carga, no desde el pedido.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-145">To correct posted packing slips for items that are enabled for WMS, the posting must occur from the load, not from the order.</span></span> <span data-ttu-id="a2fb4-146">Microsoft ha evaluado este problema y ha determinado que es una limitación de funciones.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-146">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="a2fb4-147">En general, una orden de venta que se ha seleccionado y enviado a través de los procesos de gestión de almacén puede actualizarse con un albarán de la carga o envío y el documento de la orden de venta en sí.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-147">In general, a sales order that has been picked and shipped through warehouse management processes can be packing slip–updated from the load or shipment and the sales order document itself.</span></span> <span data-ttu-id="a2fb4-148">Sin embargo, si actualiza el albarán, la orden de venta desde el documento de la orden de venta, la reversión del albarán aún no se puede realizar desde la carga o la orden de venta.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-148">However, if you packing slip–update the sales order from the sales order document, packing slip reversal still can't be done from the load or sales order.</span></span> <span data-ttu-id="a2fb4-149">Por lo tanto, le recomendamos que utilice la publicación del albarán de la carga.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-149">Therefore, we recommend that you use the packing slip posting from the load.</span></span> <span data-ttu-id="a2fb4-150">En este caso, se habilitará la inversión que se debe hacer desde la carga.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-150">In this case, the reversal that must be done from the load will be enabled.</span></span>

## <a name="i-receive-the-following-error-message-not-enough-work-can-be-found-for-cluster"></a><span data-ttu-id="a2fb4-151">Recibo el mensaje de error siguiente: "No se encuentra trabajo suficiente para el clúster".</span><span class="sxs-lookup"><span data-stu-id="a2fb4-151">I receive the following error message: "Not enough work can be found for cluster."</span></span>

### <a name="issue-description"></a><span data-ttu-id="a2fb4-152">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="a2fb4-152">Issue description</span></span>

<span data-ttu-id="a2fb4-153">Cuando usa el proceso *Selección de grupos dirigida por el sistema*, si configura un perfil de clúster donde, por ejemplo, se pueden seleccionar 10 posiciones, el proceso funciona según lo planificado cuando hay suficiente trabajo para seleccionar 10 posiciones.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-153">When you use the *System directed cluster picking* process, if you configure a cluster profile where, for example, 10 positions can be picked, the process works as planned when there is enough work to pick to 10 positions.</span></span> <span data-ttu-id="a2fb4-154">Sin embargo, si solo hay ocho posiciones para elegir, recibirá este mensaje de error porque no hay suficiente trabajo para un grupo.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-154">However, if there are only eight positions to pick, you receive this error message, because there isn't enough work for one cluster.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a2fb4-155">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="a2fb4-155">Issue resolution</span></span>

<span data-ttu-id="a2fb4-156">Para solucionar este problema, edite el perfil del clúster y configure la opción **Activar posiciones** como *No*.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-156">To fix this issue, edit the cluster profile, and set the **Activate positions** option to *No*.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]