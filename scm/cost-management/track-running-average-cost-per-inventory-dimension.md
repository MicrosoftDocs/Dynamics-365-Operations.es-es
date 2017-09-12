---
title: "Seguimiento del coste promedio móvil por dimensión de inventario"
description: "Un grupo de dimensiones de inventario está vinculado a cada artículo de inventario. Por lo tanto, el precio de coste promedio móvil de un artículo se calcula basándose en las dimensiones de inventario seleccionadas para las que se realiza un seguimiento financiero."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventOnhandItem
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 75053
ms.assetid: 68cc00f4-0f7a-4a7d-be90-8f2e0d0563d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: a88ec380810a9a2d7048d5a8773ebb5960e4cf86
ms.contentlocale: es-es
ms.lasthandoff: 07/18/2017

---

# <a name="tracking-running-average-cost-per-inventory-dimension"></a><span data-ttu-id="f27aa-104">Seguimiento del coste promedio móvil por dimensión de inventario</span><span class="sxs-lookup"><span data-stu-id="f27aa-104">Tracking running average cost per inventory dimension</span></span>

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


<span data-ttu-id="f27aa-105">Un grupo de dimensiones de inventario está vinculado a cada artículo de inventario.</span><span class="sxs-lookup"><span data-stu-id="f27aa-105">An inventory dimension group is attached to every inventory item.</span></span> <span data-ttu-id="f27aa-106">Por lo tanto, el precio de coste promedio móvil de un artículo se calcula basándose en las dimensiones de inventario seleccionadas para las que se realiza un seguimiento financiero.</span><span class="sxs-lookup"><span data-stu-id="f27aa-106">Therefore, the running average cost price of an item is calculated based on the selected inventory dimensions that are being tracked financially.</span></span>

<span data-ttu-id="f27aa-107">Hay tres tipos distintos de dimensiones de inventario: producto, almacenamiento y seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f27aa-107">There are three types of inventory dimensions: product, storage, and tracking.</span></span> <span data-ttu-id="f27aa-108">Las dimensiones de producto incluyen configuración, tamaño y color.</span><span class="sxs-lookup"><span data-stu-id="f27aa-108">Product dimensions include configuration, size, and color.</span></span> <span data-ttu-id="f27aa-109">Siempre se hace un seguimiento financiero de las dimensiones de producto.</span><span class="sxs-lookup"><span data-stu-id="f27aa-109">Product dimensions are always tracked financially.</span></span> <span data-ttu-id="f27aa-110">Las dimensiones de almacenamiento y seguimiento incluyen el sitio, el almacén, la ubicación, el estado de inventario, la matrícula de entidad de almacén, el número de lote y el número de serie.</span><span class="sxs-lookup"><span data-stu-id="f27aa-110">Storage and tracking dimensions include site, warehouse, location, inventory status, license plate, batch number, and serial number.</span></span> <span data-ttu-id="f27aa-111">Puede elegir las dimensiones de almacenamiento y seguimiento para las que se realizará un seguimiento financiero.</span><span class="sxs-lookup"><span data-stu-id="f27aa-111">You can decide which storage and tracking dimensions are tracked financially.</span></span> 

<span data-ttu-id="f27aa-112">**Ejemplo 1**</span><span class="sxs-lookup"><span data-stu-id="f27aa-112">**Example 1**</span></span> 

<span data-ttu-id="f27aa-113">Si se realiza un seguimiento financiero del grupo de dimensiones de almacenamiento vinculado al artículo por almacén, se calculará el precio de coste promedio móvil para cada almacén.</span><span class="sxs-lookup"><span data-stu-id="f27aa-113">If the storage dimension group that is attached to the item is financially tracked by warehouse, the running average cost price is calculated per warehouse.</span></span> <span data-ttu-id="f27aa-114">Se han facturado los siguientes pedidos de compra:</span><span class="sxs-lookup"><span data-stu-id="f27aa-114">The following purchase orders have been invoiced:</span></span>

-   <span data-ttu-id="f27aa-115">Para el almacén GW, se ha facturado un pedido de compra que incluye una cantidad de 2 a un precio de coste de 10,00 dólares.</span><span class="sxs-lookup"><span data-stu-id="f27aa-115">A purchase order for a quantity of 2 at a cost price of USD 10.00 has been invoiced for warehouse GW.</span></span>
-   <span data-ttu-id="f27aa-116">Para el almacén GW, se ha facturado un pedido de compra que incluye una cantidad de 3 a un precio de coste de 12,00 dólares.</span><span class="sxs-lookup"><span data-stu-id="f27aa-116">A purchase order for a quantity of 3 at a cost price of USD 12.00 has been invoiced for warehouse GW.</span></span>
-   <span data-ttu-id="f27aa-117">Para el almacén MW, se ha facturado un pedido de compra que incluye una cantidad de 5 a un precio de coste de 15,00 dólares.</span><span class="sxs-lookup"><span data-stu-id="f27aa-117">A purchase order for a quantity of 5 at a cost price of USD 15.00 has been invoiced for warehouse MW.</span></span>

<span data-ttu-id="f27aa-118">El precio de coste promedio móvil para el almacén GW es de 11,20 dólares y el precio de coste promedio móvil del almacén MW es de 15,00 dólares.</span><span class="sxs-lookup"><span data-stu-id="f27aa-118">The running average cost price for warehouse GW is USD 11.20, and the running average cost price for warehouse MW is USD 15.00.</span></span> <span data-ttu-id="f27aa-119">Se ha registrado una factura de pedido de ventas para el almacén GW.</span><span class="sxs-lookup"><span data-stu-id="f27aa-119">A sales order invoice is posted for warehouse GW.</span></span> <span data-ttu-id="f27aa-120">El valor del inventario y el coste de los bienes vendidos (antes de que se ejecute el cierre de inventario y sin marcar) será de 11,20 dólares.</span><span class="sxs-lookup"><span data-stu-id="f27aa-120">The value of the inventory and the cost of goods sold (before inventory close is run and without marking) is USD 11.20.</span></span> <span data-ttu-id="f27aa-121">Se ha registrado otra factura de pedido de ventas para el almacén MW.</span><span class="sxs-lookup"><span data-stu-id="f27aa-121">Another sales order is posted for warehouse MW.</span></span> <span data-ttu-id="f27aa-122">El valor del inventario y el coste de los bienes vendidos (antes de que se ejecute el cierre de inventario y sin marcar) será de 15,00 dólares.</span><span class="sxs-lookup"><span data-stu-id="f27aa-122">The value of the inventory and the cost of goods sold (before inventory close is run and without marking) is USD 15.00.</span></span> 

<span data-ttu-id="f27aa-123">**Ejemplo 2** Si se realiza un seguimiento financiero del grupo de dimensiones de almacenamiento vinculado al artículo por almacén y se realiza un seguimiento financiero del grupo de dimensiones de seguimiento por número de lote, se calcula el precio de coste promedio móvil para cada lote.</span><span class="sxs-lookup"><span data-stu-id="f27aa-123">**Example 2** If the storage dimension group that is attached to the item is financially tracked by warehouse, and the tracking dimension group is financially tracked by batch number, the running average cost price is calculated for each batch.</span></span> 

<span data-ttu-id="f27aa-124">**Nota:** es recomendable que siempre vea el precio de coste para todas las dimensiones financieras para las que se realiza el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f27aa-124">**Note:** We recommend that you always view the cost price for all financial dimensions that are being tracked.</span></span> <span data-ttu-id="f27aa-125">Se han facturado los siguientes pedidos de compra:</span><span class="sxs-lookup"><span data-stu-id="f27aa-125">The following purchase orders have been invoiced:</span></span>

-   <span data-ttu-id="f27aa-126">Se ha facturado para el almacén GW y el lote AAA un pedido de compra que incluye una cantidad de 2 a un precio de coste de 10,00 dólares.</span><span class="sxs-lookup"><span data-stu-id="f27aa-126">A purchase order for a quantity of 2 at a cost price of USD 10.00 has been invoiced for warehouse GW and batch AAA.</span></span>
-   <span data-ttu-id="f27aa-127">Se ha facturado para el almacén GW y el lote AAA un pedido de compra que incluye una cantidad de 3 a un precio de coste de 12,00 dólares.</span><span class="sxs-lookup"><span data-stu-id="f27aa-127">A purchase order for a quantity of 3 at a cost price of USD 12.00 has been invoiced for warehouse GW and batch AAA.</span></span>
-   <span data-ttu-id="f27aa-128">Se ha facturado para el almacén GW y el lote BBB un pedido de compra que incluye una cantidad de 2 a un precio de coste de 15,00 dólares.</span><span class="sxs-lookup"><span data-stu-id="f27aa-128">A purchase order for a quantity of 2 at a cost price of USD 15.00 has been invoiced for warehouse GW and batch BBB.</span></span>

<span data-ttu-id="f27aa-129">El precio de coste promedio móvil para el almacén GW y el lote AAA es de 11,20 dólares y el precio de coste promedio móvil del almacén GW y el lote BBB es de 15,00 dólares.</span><span class="sxs-lookup"><span data-stu-id="f27aa-129">The running average cost price for warehouse GW and batch AAA is USD 11.20, and the running average cost price for warehouse GW and batch BBB is USD 15.00.</span></span>




