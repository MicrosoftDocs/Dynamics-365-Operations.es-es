---
title: Solucionar problemas de planificación de carga y envíos
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con creación de cargas y envíos en Microsoft Dynamics 365 Supply Chain Management.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 2933bcfd2cc526e39a4e1343cd472334a5b95607
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645341"
---
# <a name="troubleshoot-load-building-and-shipments"></a><span data-ttu-id="f4c2e-103">Solucionar problemas de planificación de carga y envíos</span><span class="sxs-lookup"><span data-stu-id="f4c2e-103">Troubleshoot load building and shipments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f4c2e-104">Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con creación de cargas y envíos en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-104">This topic describes how to fix common issues that you might encounter while you work with load building and shipments in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-you-cant-create-a-load-line-for-this-order-line-because-it-contains-inventory-dimensions-that-are-invalid"></a><span data-ttu-id="f4c2e-105">Recibo el siguiente mensaje de error: "No puede crear una línea de carga para esta línea de pedido porque contiene dimensiones de inventario que no son válidas ..."</span><span class="sxs-lookup"><span data-stu-id="f4c2e-105">I receive the following error message: "You can't create a load line for this order line because it contains inventory dimensions that are invalid..."</span></span>

### <a name="issue-description"></a><span data-ttu-id="f4c2e-106">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="f4c2e-106">Issue description</span></span>

<span data-ttu-id="f4c2e-107">Recibe el siguiente mensaje de error cuando intenta enviar un pedido de devolución al almacén:</span><span class="sxs-lookup"><span data-stu-id="f4c2e-107">You receive the following error message when you try to release a return sales order to the warehouse:</span></span>

> <span data-ttu-id="f4c2e-108">No puede crear una línea de carga para esta línea de pedido porque contiene dimensiones de inventario que no son válidas.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-108">You can't create a load line for this order line because it contains inventory dimensions that are invalid.</span></span> <span data-ttu-id="f4c2e-109">No puede hacer referencia a dimensiones de inventario que se encuentran debajo de la dimensión de ubicación en la jerarquía de reservas.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-109">You can't reference inventory dimensions that are located below the location dimension in the reservation hierarchy.</span></span> <span data-ttu-id="f4c2e-110">Elimine las dimensiones no válidas de la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-110">Remove the invalid dimensions from the order line.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f4c2e-111">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="f4c2e-111">Issue resolution</span></span>

<span data-ttu-id="f4c2e-112">Desafortunadamente, el producto no admite el procesamiento de carga para un proceso de devolución de ventas.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-112">Unfortunately, the product doesn't support load processing for a sales return process.</span></span> <span data-ttu-id="f4c2e-113">Por lo tanto, no puede enviar el pedido de devolución al almacén.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-113">Therefore, you can't release the return sales order to the warehouse.</span></span>

<span data-ttu-id="f4c2e-114">En las transacciones de pedido de venta, no puede hacer referencia a dimensiones de inventario que se encuentran debajo de la dimensión **Ubicación** en la jerarquía de reservas.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-114">On sales order transactions, you can't reference inventory dimensions that are located below the **Location** dimension in the reservation hierarchy.</span></span> <span data-ttu-id="f4c2e-115">La resolución es quitar las dimensiones no válidas de la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-115">The resolution is to remove the invalid dimensions from the order line.</span></span>

## <a name="i-receive-the-following-error-message-one-of-the-lines-is-already-on-a-load-unable-to-release-to-warehouse"></a><span data-ttu-id="f4c2e-116">Recibo el siguiente mensaje de error: "Una de las líneas ya está cargada.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-116">I receive the following error message: "One of the lines is already on a load.</span></span> <span data-ttu-id="f4c2e-117">No se puede liberar al almacén".</span><span class="sxs-lookup"><span data-stu-id="f4c2e-117">Unable to release to warehouse."</span></span>

### <a name="issue-description"></a><span data-ttu-id="f4c2e-118">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="f4c2e-118">Issue description</span></span>

<span data-ttu-id="f4c2e-119">Si crea cargas manualmente, o si configura el proceso de modo que las cargas ya estén creadas antes de que se produzca la entrada de la línea de la orden de venta, se supone que la liberación posterior se realizará manualmente y que se utilizarán la ruta y la clasificación de la carga. .</span><span class="sxs-lookup"><span data-stu-id="f4c2e-119">If you manually create loads, or if you set up the process so that loads are already created before sales order line entry occurs, the assumption is that the subsequent release will be done manually, and that the route and rating from the load will be used.</span></span>

<span data-ttu-id="f4c2e-120">En otro escenario posible, está intentando hacer una liberación automática al almacén, pero el proceso de oleada no pudo crear trabajo.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-120">In another possible scenario, you're trying to do an automatic release to the warehouse, but the wave process failed to create work.</span></span> <span data-ttu-id="f4c2e-121">Por lo tanto, se sigue creando un envío o carga abiertos.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-121">Therefore, an open shipment or load is still created.</span></span> <span data-ttu-id="f4c2e-122">Este envío o carga abiertos bloquea los intentos posteriores de liberar automáticamente el pedido hasta que elimine el envío o la carga abiertos, o reprocese manualmente la ola.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-122">This open shipment or load then blocks subsequent attempts to automatically release the order until you either delete the open shipment or load, or manually reprocess the wave.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f4c2e-123">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="f4c2e-123">Issue resolution</span></span>

<span data-ttu-id="f4c2e-124">Puede liberar desde la página de órdenes de venta, o la liberación automática puede realizarse desde la página de liberación de órdenes de venta, solo si no existe carga antes de la liberación al almacén.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-124">You can release from the sales order page, or automatic release can be done from the release sales order page, only if no load exists before the release to the warehouse.</span></span> <span data-ttu-id="f4c2e-125">La carga se creará automáticamente después de que se procese la ola.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-125">The load will automatically be created after the wave is processed.</span></span>

## <a name="i-receive-the-following-error-message-the-delivery-note-correction-cant-be-processed-the-delivery-note-only-contains-items-that-are-subject-to-warehouse-management-processes-as-these-are-not-supported-by-delivery-note-correction"></a><span data-ttu-id="f4c2e-126">Recibo el siguiente mensaje de error: "No se puede procesar la corrección del albarán de entrega.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-126">I receive the following error message: "The delivery note correction can't be processed.</span></span> <span data-ttu-id="f4c2e-127">La nota de entrega solo contiene artículos que están sujetos a procesos de gestión de almacén, ya que estos no son compatibles con la corrección de la nota de entrega ".</span><span class="sxs-lookup"><span data-stu-id="f4c2e-127">The delivery note only contains items that are subject to warehouse management processes, as these are not supported by Delivery Note correction."</span></span>

### <a name="issue-description"></a><span data-ttu-id="f4c2e-128">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="f4c2e-128">Issue description</span></span>

<span data-ttu-id="f4c2e-129">Después de publicar un albarán de entrega, no puede cancelarlo porque el botón **Cancelar** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-129">After you post a delivery note, you can't cancel it, because the **Cancel** button is unavailable.</span></span> <span data-ttu-id="f4c2e-130">Tampoco puede corregir el albarán de entrega.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-130">You also can't correct the delivery note.</span></span> <span data-ttu-id="f4c2e-131">Si lo intenta, recibirá este mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-131">If you try, you receive this error message.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f4c2e-132">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="f4c2e-132">Issue resolution</span></span>

<span data-ttu-id="f4c2e-133">Para corregir las notas de empaque publicadas para los artículos que están habilitados para gestión avanzada de almacenes (WMS), debe hacer la publicación desde la carga, no desde el pedido.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-133">To correct posted packing slips for items that are enabled for advanced warehouse management (WMS), you must do the posting from the load, not directly from the order.</span></span>

## <a name="how-can-i-create-work-from-outbound-loads-instead-of-waves"></a><span data-ttu-id="f4c2e-134">¿Cómo puedo crear trabajo a partir de cargas salientes en lugar de oleadas?</span><span class="sxs-lookup"><span data-stu-id="f4c2e-134">How can I create work from outbound loads instead of waves?</span></span>

### <a name="issue-description"></a><span data-ttu-id="f4c2e-135">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="f4c2e-135">Issue description</span></span>

<span data-ttu-id="f4c2e-136">A continuación se muestra una forma de reproducir este problema.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-136">Here is one way to reproduce this issue.</span></span>

1. <span data-ttu-id="f4c2e-137">Crear una carga de salida mediante una orden de ventas o una orden de transferencia</span><span class="sxs-lookup"><span data-stu-id="f4c2e-137">Create an outbound load by using a sales order or transfer order.</span></span>
2. <span data-ttu-id="f4c2e-138">Liberar la carga al almacén.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-138">Release the load to the warehouse.</span></span>
3. <span data-ttu-id="f4c2e-139">Observe que aún no se ha generado ningún trabajo de picking.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-139">Notice that no picking work has yet been generated.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f4c2e-140">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="f4c2e-140">Issue resolution</span></span>

<span data-ttu-id="f4c2e-141">Si se debe generar trabajo inmediatamente cuando se libera la carga, debe configurar la plantilla de onda en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-141">If work must be generated immediately when the load is released, you must configure the wave template accordingly.</span></span> <span data-ttu-id="f4c2e-142">En la plantilla de oleada, configure las siguientes opciones para *Sí*:</span><span class="sxs-lookup"><span data-stu-id="f4c2e-142">On the wave template, set the following options to *Yes*:</span></span>

- <span data-ttu-id="f4c2e-143">Automatizar la creación de oleadas</span><span class="sxs-lookup"><span data-stu-id="f4c2e-143">Automate wave creation</span></span>
- <span data-ttu-id="f4c2e-144">Procesar oleada para su liberación al almacén</span><span class="sxs-lookup"><span data-stu-id="f4c2e-144">Process wave at release to warehouse</span></span>
- <span data-ttu-id="f4c2e-145">Liberación automática de oleada</span><span class="sxs-lookup"><span data-stu-id="f4c2e-145">Automate wave release</span></span>

## <a name="i-cant-re-release-a-partially-shipped-load"></a><span data-ttu-id="f4c2e-146">No puedo volver a liberar una carga enviada parcialmente.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-146">I can't re-release a partially shipped load.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f4c2e-147">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="f4c2e-147">Issue description</span></span>

<span data-ttu-id="f4c2e-148">No puede liberar una carga enviada parcialmente al almacén.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-148">You can't release a partially shipped load to the warehouse.</span></span> <span data-ttu-id="f4c2e-149">Cuando realiza la liberación al almacén, aparece el mensaje "Operación completada", pero no ocurre nada y no se crea ningún trabajo para la cantidad restante.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-149">When you do the release to the warehouse, an "Operation complete" message appears, but nothing happens, and no work is created for the remaining quantity.</span></span> <span data-ttu-id="f4c2e-150">Este problema se produce cuando utiliza la función de carga de transporte y hay una reserva incompleta.</span><span class="sxs-lookup"><span data-stu-id="f4c2e-150">This issue occurs when you use transport load functionality and there is an incomplete reservation.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f4c2e-151">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="f4c2e-151">Issue resolution</span></span>

<span data-ttu-id="f4c2e-152">[Problema de KB 470069](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) ("Las cargas enviadas parcialmente se pueden volver a agitar y volver a procesar") se corrige en la [versión 10.0.15](../get-started/whats-new-scm-10-0-15.md).</span><span class="sxs-lookup"><span data-stu-id="f4c2e-152">[KB issue 470069](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) ("Partially shipped loads can be re-waved and re-processed") is fixed in [release 10.0.15](../get-started/whats-new-scm-10-0-15.md).</span></span>
