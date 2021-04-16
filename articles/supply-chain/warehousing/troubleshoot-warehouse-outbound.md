---
title: Solucionar problemas de operaciones de almacén de salida
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con operaciones de almacén de salida en Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 919b6f433db47f24adc9a474942557a1467d1f71
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828187"
---
# <a name="troubleshoot-outbound-warehouse-operations"></a><span data-ttu-id="9d12e-103">Solucionar problemas de operaciones de almacén de salida</span><span class="sxs-lookup"><span data-stu-id="9d12e-103">Troubleshoot outbound warehouse operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9d12e-104">Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con operaciones de almacén de salida en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9d12e-104">This topic describes how to fix common issues that you might encounter while you work with outbound warehouse operations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-sales-order-could-not-be-released"></a><span data-ttu-id="9d12e-105">Recibo el siguiente mensaje de error: "No se pudo liberar el pedido de venta".</span><span class="sxs-lookup"><span data-stu-id="9d12e-105">I receive the following error message: "Sales order could not be released."</span></span>

### <a name="issue-description"></a><span data-ttu-id="9d12e-106">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="9d12e-106">Issue description</span></span>

<span data-ttu-id="9d12e-107">Este problema puede ocurrir por varias razones.</span><span class="sxs-lookup"><span data-stu-id="9d12e-107">This issue can occur for several reasons.</span></span> <span data-ttu-id="9d12e-108">Por ejemplo, el pedido está en espera de gestión de crédito y no se pueden crear envíos hasta que se ingrese una dirección postal válida para todas las líneas de ventas asociadas con un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="9d12e-108">For example, the order is on credit management hold, and no shipments can be created until a valid postal address is entered for all sales lines that are associated with a sales order.</span></span> <span data-ttu-id="9d12e-109">Alternativamente, existe una retención de pedido que debe abordarse antes de que el pedido pueda enviarse al almacén.</span><span class="sxs-lookup"><span data-stu-id="9d12e-109">Alternatively, there is an order hold that must be addressed before the order can be released to the warehouse.</span></span> <span data-ttu-id="9d12e-110">Esta retención puede ser específica de un pedido o puede estar en la cuenta del cliente.</span><span class="sxs-lookup"><span data-stu-id="9d12e-110">This hold might be order-specific, or it might be on the customer account.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="9d12e-111">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="9d12e-111">Issue resolution</span></span>

<span data-ttu-id="9d12e-112">Agregue o actualice la dirección en la orden de venta y las líneas de orden y luego libere la orden en el almacén.</span><span class="sxs-lookup"><span data-stu-id="9d12e-112">Add or update the address on the sales order and order lines, and then release the order to the warehouse.</span></span> <span data-ttu-id="9d12e-113">Los pedidos se pueden enviar al almacén solo si tienen una dirección de entrega válida (según la configuración del formato de dirección en el módulo **Administración de la organización**).</span><span class="sxs-lookup"><span data-stu-id="9d12e-113">Orders can be released to the warehouse only if they have a valid delivery address (per the address format setup in the **Organization administration** module).</span></span>

<span data-ttu-id="9d12e-114">Investigue la orden retenida y resuelva los problemas.</span><span class="sxs-lookup"><span data-stu-id="9d12e-114">Investigate the order hold, and address the issues.</span></span> <span data-ttu-id="9d12e-115">Luego elimine la retención del pedido o del cliente y libere el pedido al almacén.</span><span class="sxs-lookup"><span data-stu-id="9d12e-115">Then remove the hold from the order or customer, and release the order to the warehouse.</span></span>

## <a name="i-receive-the-following-message-the-shipment-for-load-1-has-been-confirmed-however-no-lines-are-posted"></a><span data-ttu-id="9d12e-116">Recibo el siguiente mensaje: "El envío de carga 1% ha sido confirmado".</span><span class="sxs-lookup"><span data-stu-id="9d12e-116">I receive the following message: "The shipment for load 1% has been confirmed."</span></span> <span data-ttu-id="9d12e-117">Sin embargo, no se publican líneas.</span><span class="sxs-lookup"><span data-stu-id="9d12e-117">However, no lines are posted.</span></span>

### <a name="issue-description"></a><span data-ttu-id="9d12e-118">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="9d12e-118">Issue description</span></span>

<span data-ttu-id="9d12e-119">Se confirmó un envío en una carga, pero no se realizaron más envíos.</span><span class="sxs-lookup"><span data-stu-id="9d12e-119">A shipment on a load was confirmed, but no further posting occurred.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="9d12e-120">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="9d12e-120">Issue resolution</span></span>

<span data-ttu-id="9d12e-121">La confirmación del envío no afecta la publicación.</span><span class="sxs-lookup"><span data-stu-id="9d12e-121">Shipment confirmation doesn't affect posting.</span></span> <span data-ttu-id="9d12e-122">Solo actualiza el estado del envío y la carga.</span><span class="sxs-lookup"><span data-stu-id="9d12e-122">It just updates the shipment and load status.</span></span> <span data-ttu-id="9d12e-123">La publicación debe ocurrir en un proceso separado.</span><span class="sxs-lookup"><span data-stu-id="9d12e-123">Posting must occur in a separate process.</span></span>

## <a name="i-receive-the-following-error-message-direct-delivery-is-not-able-to-process-for-warehouse-1-as-it-has-warehouse-management-enabled-please-specify-another-warehouse-that-is-not-enabled-for-warehouse-management"></a><span data-ttu-id="9d12e-124">Recibo el siguiente mensaje de error: "La entrega directa no se puede procesar para el 1% del almacén porque tiene habilitada la gestión del almacén.</span><span class="sxs-lookup"><span data-stu-id="9d12e-124">I receive the following error message: "Direct delivery is not able to process for warehouse 1% as it has warehouse management enabled.</span></span> <span data-ttu-id="9d12e-125">Especifique otro almacén que no esté habilitado para la gestión de almacenes ".</span><span class="sxs-lookup"><span data-stu-id="9d12e-125">Please specify another warehouse that is not enabled for warehouse management."</span></span>

### <a name="issue-description"></a><span data-ttu-id="9d12e-126">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="9d12e-126">Issue description</span></span>

<span data-ttu-id="9d12e-127">Se agrega un artículo a una línea de ventas para entrega directa desde un almacén que está habilitado para la gestión de almacenes (WMS).</span><span class="sxs-lookup"><span data-stu-id="9d12e-127">An item is added to a sales line for direct delivery from a warehouse that is enabled for warehouse management (WMS).</span></span> <span data-ttu-id="9d12e-128">Recibe este mensaje de error cuando se actualiza la línea de ventas.</span><span class="sxs-lookup"><span data-stu-id="9d12e-128">You receive this error message when the sales line is updated.</span></span> 

### <a name="issue-resolution"></a><span data-ttu-id="9d12e-129">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="9d12e-129">Issue resolution</span></span>

<span data-ttu-id="9d12e-130">Microsoft ha evaluado este problema y ha determinado que es una limitación de funciones.</span><span class="sxs-lookup"><span data-stu-id="9d12e-130">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="9d12e-131">Actualmente, WMS no admite la entrega directa.</span><span class="sxs-lookup"><span data-stu-id="9d12e-131">Currently, WMS doesn't support direct delivery.</span></span> <span data-ttu-id="9d12e-132">Por lo tanto, para utilizar la entrega directa, debe seleccionar un artículo y un almacén que no sea WMS.</span><span class="sxs-lookup"><span data-stu-id="9d12e-132">Therefore, to use direct delivery, you must select a non-WMS item and warehouse.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]