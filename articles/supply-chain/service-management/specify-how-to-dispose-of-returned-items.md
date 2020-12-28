---
title: Especificar la disposición de artículos devueltos
description: Especificar la disposición de artículos devueltos.
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b2b1468328433a67253bafc21ac9c9b3a2398872
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436522"
---
# <a name="specify-how-to-dispose-of-returned-items"></a><span data-ttu-id="6c0ca-103">Especificar la disposición de artículos devueltos</span><span class="sxs-lookup"><span data-stu-id="6c0ca-103">Specify how to dispose of returned items</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="6c0ca-104">Al gestionar un pedido de devolución, debe especificar un código de motivo de devolución para identificar por qué se devuelve el producto.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-104">When you handle a return order, you must specify a reason return code to identify why the product is being returned.</span></span> <span data-ttu-id="6c0ca-105">También debe especificar un código de disposición y una acción de disposición de determinar qué se debe realizar con el producto devuelto en sí.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-105">You must also specify a disposition code and a disposition action to determine what should be done with the returned product itself.</span></span>

<span data-ttu-id="6c0ca-106">Un código de disposición se puede aplicar cuando se crea el pedido de devolución, se registra la llegada del artículo o el albarán, se actualiza una llegada de artículo o se finaliza una orden de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-106">A disposition code can be applied when you create the return order, register item arrival or packing-slip update an item arrival, and end a quarantine order.</span></span>

<span data-ttu-id="6c0ca-107">Se pueden definir los códigos de disposición necesarios para los procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-107">You can define any disposition codes that you need in order to support the business processes.</span></span> <span data-ttu-id="6c0ca-108">La tabla siguiente proporciona un conjunto de códigos que se usan habitualmente para asignar la disposición del artículo devuelto.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-108">The following table provides a set of typically used codes to assign return-item disposition.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6c0ca-109">Tipo de disposición</span><span class="sxs-lookup"><span data-stu-id="6c0ca-109">Disposition type</span></span></p></th>
<th><p><span data-ttu-id="6c0ca-110">Código común</span><span class="sxs-lookup"><span data-stu-id="6c0ca-110">Common code</span></span></p></th>
<th><p><span data-ttu-id="6c0ca-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c0ca-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c0ca-112">Cancelación</span><span class="sxs-lookup"><span data-stu-id="6c0ca-112">Disposal</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-113">SC</span><span class="sxs-lookup"><span data-stu-id="6c0ca-113">SC</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-114">Desechar/Destruir</span><span class="sxs-lookup"><span data-stu-id="6c0ca-114">Scrap/Destroy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c0ca-115">Cancelación</span><span class="sxs-lookup"><span data-stu-id="6c0ca-115">Disposal</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-116">DC</span><span class="sxs-lookup"><span data-stu-id="6c0ca-116">DC</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-117">Donar a caridad</span><span class="sxs-lookup"><span data-stu-id="6c0ca-117">Donate to Charity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c0ca-118">Cancelación</span><span class="sxs-lookup"><span data-stu-id="6c0ca-118">Disposal</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-119">TD</span><span class="sxs-lookup"><span data-stu-id="6c0ca-119">TD</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-120">Cancelación de terceros</span><span class="sxs-lookup"><span data-stu-id="6c0ca-120">Third-Party Disposal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c0ca-121">Cancelación</span><span class="sxs-lookup"><span data-stu-id="6c0ca-121">Disposal</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-122">SL</span><span class="sxs-lookup"><span data-stu-id="6c0ca-122">SL</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-123">Rescatar</span><span class="sxs-lookup"><span data-stu-id="6c0ca-123">Salvage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c0ca-124">Cancelación</span><span class="sxs-lookup"><span data-stu-id="6c0ca-124">Disposal</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-125">TS</span><span class="sxs-lookup"><span data-stu-id="6c0ca-125">TS</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-126">Venta de terceros (mercados secundarios)</span><span class="sxs-lookup"><span data-stu-id="6c0ca-126">Third-Party Sale (Secondary Markets)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c0ca-127">Reparación/Modificación</span><span class="sxs-lookup"><span data-stu-id="6c0ca-127">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-128">RW</span><span class="sxs-lookup"><span data-stu-id="6c0ca-128">RW</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-129">Reprocesar</span><span class="sxs-lookup"><span data-stu-id="6c0ca-129">Rework</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c0ca-130">Reparación/Modificación</span><span class="sxs-lookup"><span data-stu-id="6c0ca-130">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-131">RF</span><span class="sxs-lookup"><span data-stu-id="6c0ca-131">RF</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-132">Volver a fabricar/Reacondicionar</span><span class="sxs-lookup"><span data-stu-id="6c0ca-132">Remanufacture/Refurbish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c0ca-133">Reparación/Modificación</span><span class="sxs-lookup"><span data-stu-id="6c0ca-133">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-134">MD</span><span class="sxs-lookup"><span data-stu-id="6c0ca-134">MD</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-135">Modificar</span><span class="sxs-lookup"><span data-stu-id="6c0ca-135">Modify</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c0ca-136">Reparación/Modificación</span><span class="sxs-lookup"><span data-stu-id="6c0ca-136">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-137">RP</span><span class="sxs-lookup"><span data-stu-id="6c0ca-137">RP</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-138">Reparar</span><span class="sxs-lookup"><span data-stu-id="6c0ca-138">Repair</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c0ca-139">Reparación/Modificación</span><span class="sxs-lookup"><span data-stu-id="6c0ca-139">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-140">RV</span><span class="sxs-lookup"><span data-stu-id="6c0ca-140">RV</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-141">Devolver al proveedor</span><span class="sxs-lookup"><span data-stu-id="6c0ca-141">Return to Vendor</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c0ca-142">Otros</span><span class="sxs-lookup"><span data-stu-id="6c0ca-142">Other</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-143">AI</span><span class="sxs-lookup"><span data-stu-id="6c0ca-143">AI</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-144">Usar tal como está</span><span class="sxs-lookup"><span data-stu-id="6c0ca-144">Use as is</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c0ca-145">Otro</span><span class="sxs-lookup"><span data-stu-id="6c0ca-145">Other</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-146">RS</span><span class="sxs-lookup"><span data-stu-id="6c0ca-146">RS</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-147">Volver a vender</span><span class="sxs-lookup"><span data-stu-id="6c0ca-147">Resale</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c0ca-148">Otro</span><span class="sxs-lookup"><span data-stu-id="6c0ca-148">Other</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-149">EX</span><span class="sxs-lookup"><span data-stu-id="6c0ca-149">EX</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-150">Cambio</span><span class="sxs-lookup"><span data-stu-id="6c0ca-150">Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c0ca-151">Otro</span><span class="sxs-lookup"><span data-stu-id="6c0ca-151">Other</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-152">MS</span><span class="sxs-lookup"><span data-stu-id="6c0ca-152">MS</span></span></p></td>
<td><p><span data-ttu-id="6c0ca-153">Varios</span><span class="sxs-lookup"><span data-stu-id="6c0ca-153">Miscellaneous</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6c0ca-154">Para cada código de disposición definido, debe seleccionar una acción de disposición.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-154">For each disposition code that you define, you must select a disposition action.</span></span> <span data-ttu-id="6c0ca-155">La acción de disposición determina las implicaciones físicas y financieras de los códigos de disposición.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-155">The disposition action determines the physical and financial implications of the disposition codes.</span></span> <span data-ttu-id="6c0ca-156">Por ejemplo, la acción de disposición determina la manipulación física del artículo devuelto, el efecto financiero del artículo devuelto y si un artículo de sustitución se debe enviar al cliente.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-156">For example, the disposition action determines the physical handling of the returned item, the financial effect of the returned item, and if a replacement item must be sent to the customer.</span></span> <span data-ttu-id="6c0ca-157">Puede definir un número ilimitado de códigos de disposición en función de las necesidades de la empresa, pero solo hay seis acciones predefinidas entre las que puede seleccionar.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-157">You can define an unlimited number of disposition codes according to your business needs, but there are only six predefined disposition actions that you can select from.</span></span> <span data-ttu-id="6c0ca-158">La tabla siguiente proporciona las acciones de disposición y sus definiciones.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-158">The following table provides the disposition actions and their definitions.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6c0ca-159">Acción de disposición</span><span class="sxs-lookup"><span data-stu-id="6c0ca-159">Disposition action</span></span></p></th>
<th><p><span data-ttu-id="6c0ca-160">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c0ca-160">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c0ca-161"><strong>Crédito</strong></span><span class="sxs-lookup"><span data-stu-id="6c0ca-161"><strong>Credit</strong></span></span></p></td>
<td><p><span data-ttu-id="6c0ca-162">Devolver el artículo al inventario y abonar al cliente.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-162">Return the item to inventory and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c0ca-163"><strong>Sólo abonar</strong></span><span class="sxs-lookup"><span data-stu-id="6c0ca-163"><strong>Credit only</strong></span></span></p></td>
<td><p><span data-ttu-id="6c0ca-164">Abonar al cliente sin requerir o esperar que el artículo se devuelva.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-164">Credit the customer without requiring or expecting the item to be returned.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c0ca-165"><strong>Residuo</strong></span><span class="sxs-lookup"><span data-stu-id="6c0ca-165"><strong>Scrap</strong></span></span></p></td>
<td><p><span data-ttu-id="6c0ca-166">Cancelar el artículo y abonar al cliente.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-166">Scrap the item and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c0ca-167"><strong>Reemplazar y abonar</strong></span><span class="sxs-lookup"><span data-stu-id="6c0ca-167"><strong>Replace and credit</strong></span></span></p></td>
<td><p><span data-ttu-id="6c0ca-168">Devolver el artículo al inventario, crear un pedido de sustitución y abonar al cliente.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-168">Return the item to inventory, create a replacement order, and credit the customer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c0ca-169"><strong>Reemplazar y cancelar</strong></span><span class="sxs-lookup"><span data-stu-id="6c0ca-169"><strong>Replace and scrap</strong></span></span></p></td>
<td><p><span data-ttu-id="6c0ca-170">Cancelar el artículo, crear un pedido de sustitución abonar al cliente.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-170">Scrap the item, create a replacement order, and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c0ca-171"><strong>Devolver al cliente</strong></span><span class="sxs-lookup"><span data-stu-id="6c0ca-171"><strong>Return to customer</strong></span></span></p></td>
<td><p><span data-ttu-id="6c0ca-172">Rechazar el artículo devuelto y devolverlo al cliente.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-172">Reject the returned item and return it to the customer.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="select-a-disposition-code-for-a-quarantine-order"></a><span data-ttu-id="6c0ca-173">Seleccione un código de disposición para una orden de cuarentena</span><span class="sxs-lookup"><span data-stu-id="6c0ca-173">Select a disposition code for a quarantine order</span></span>

1.  <span data-ttu-id="6c0ca-174">Haga clic en **Gestión del inventario** \> **Periódico** \> **Administración de calidad** \> **Órdenes de cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-174">Click **Inventory management** \> **Periodic** \> **Quality management** \> **Quarantine orders**.</span></span>

2.  <span data-ttu-id="6c0ca-175">Para una orden de cuarentena existente, seleccione una acción del campo **Código de disposición**, en la ficha **Visión general**.</span><span class="sxs-lookup"><span data-stu-id="6c0ca-175">For an existing quarantine order, select an action from the **Disposition code** field on the **Overview** tab.</span></span>



## <a name="see-also"></a><span data-ttu-id="6c0ca-176">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6c0ca-176">See also</span></span>

<span data-ttu-id="6c0ca-177">[Orden de cuarentena (formulario)](https://technet.microsoft.com/library/aa554073(v=ax.60))</span><span class="sxs-lookup"><span data-stu-id="6c0ca-177">[Quarantine order (form)](https://technet.microsoft.com/library/aa554073(v=ax.60))</span></span>

<span data-ttu-id="6c0ca-178">[Códigos de disposición (formulario)](https://technet.microsoft.com/library/hh597113\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="6c0ca-178">[Disposition codes (form)](https://technet.microsoft.com/library/hh597113\(v=ax.60\))</span></span>

  


