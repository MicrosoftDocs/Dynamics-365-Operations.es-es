---
title: Pedidos de compra para un proyecto
description: "Este artículo describe los distintos métodos que puede usar para crear pedidos de compra para un proyecto. El método que use depende del propósito del pedido de compra y de la fecha de consumo y de cargo a un proyecto de los artículos comprados."
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 767a1805e7a2609c5c28bed891b42f7c8c3aaffc
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---

# <a name="purchase-orders-for-a-project"></a><span data-ttu-id="223e6-104">Pedidos de compra para un proyecto</span><span class="sxs-lookup"><span data-stu-id="223e6-104">Purchase orders for a project</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="223e6-105">Este artículo describe los distintos métodos que puede usar para crear pedidos de compra para un proyecto.</span><span class="sxs-lookup"><span data-stu-id="223e6-105">This article describes the various methods that you can use to create purchase orders for a project.</span></span> <span data-ttu-id="223e6-106">El método que use depende del propósito del pedido de compra y de la fecha de consumo y de cargo a un proyecto de los artículos comprados.</span><span class="sxs-lookup"><span data-stu-id="223e6-106">The method that you use depends on the purpose of the purchase order, and when the purchased items are consumed and charged to a project.</span></span>

<span data-ttu-id="223e6-107">En Microsoft Dynamics 365 for Finance and Operations, puede usar varios métodos para crear pedidos de compra para un proyecto.</span><span class="sxs-lookup"><span data-stu-id="223e6-107">In Microsoft Dynamics 365 for Finance and Operations, you can use multiple methods to create purchase orders for a project.</span></span> <span data-ttu-id="223e6-108">El método que use depende del propósito del pedido de compra, de la fecha de consumo de los artículos comprados y de la fecha de cargo de los artículos comprados a un proyecto.</span><span class="sxs-lookup"><span data-stu-id="223e6-108">The method that you use depends on the purpose of the purchase order, when the purchased items are consumed, and when the purchased items are charged to a project.</span></span>

### <a name="methods-for-creating-a-purchase-order"></a><span data-ttu-id="223e6-109">Métodos de creación de un pedido de compra</span><span class="sxs-lookup"><span data-stu-id="223e6-109">Methods for creating a purchase order</span></span>

<span data-ttu-id="223e6-110">Puede usar uno de los siguientes métodos para crear un pedido de compra en Gestión de proyectos y contabilidad.</span><span class="sxs-lookup"><span data-stu-id="223e6-110">You can use one of the following methods to create a purchase order in Project management and accounting.</span></span> <span data-ttu-id="223e6-111">La finalidad del pedido de compra determina cuándo se consume el pedido de compra y, por tanto, cuándo se cargan los artículos a un proyecto.</span><span class="sxs-lookup"><span data-stu-id="223e6-111">The purpose of the purchase order determines when the purchase order is consumed and, therefore, when items are charged to a project.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="223e6-112">Método</span><span class="sxs-lookup"><span data-stu-id="223e6-112">Method</span></span></th>
<th><span data-ttu-id="223e6-113">Propósito</span><span class="sxs-lookup"><span data-stu-id="223e6-113">Purpose</span></span></th>
<th><span data-ttu-id="223e6-114">Consumo de artículos</span><span class="sxs-lookup"><span data-stu-id="223e6-114">Consumption of items</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="223e6-115">Cree un pedido de compra directamente de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="223e6-115">Create a purchase order directly from a project.</span></span></td>
<td><span data-ttu-id="223e6-116">Use este método para comprar artículos de un proveedor externo para consumo en un proyecto.</span><span class="sxs-lookup"><span data-stu-id="223e6-116">Use this method to purchase items from an external vendor for consumption on a project.</span></span> <span data-ttu-id="223e6-117">Puede crear el pedido de compra de dos formas:</span><span class="sxs-lookup"><span data-stu-id="223e6-117">You can create the purchase order in two ways:</span></span>
<ul>
<li><span data-ttu-id="223e6-118">Desde el propio proyecto.</span><span class="sxs-lookup"><span data-stu-id="223e6-118">From the project itself.</span></span> <span data-ttu-id="223e6-119">En este caso, el proyecto ya está definido para el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="223e6-119">In this case, the project is already defined for the purchase order.</span></span></li>
<li><span data-ttu-id="223e6-120">Desplazándose hasta el pedido de compra del proyecto.</span><span class="sxs-lookup"><span data-stu-id="223e6-120">By navigating to the project purchase order.</span></span> <span data-ttu-id="223e6-121">Debe seleccionar tanto el proveedor como el proyecto para el que se creará el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="223e6-121">You must select both the vendor and the project to create the purchase order for.</span></span></li>
</ul></td>
<td><span data-ttu-id="223e6-122">Los artículos se consumen al actualizar la factura del proveedor.</span><span class="sxs-lookup"><span data-stu-id="223e6-122">Items are consumed when the vendor invoice is updated.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="223e6-123">Cree un pedido de venta a partir de un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="223e6-123">Create a purchase order from a sales order.</span></span></td>
<td><span data-ttu-id="223e6-124">Utilice este método para adquirir artículos al crear un pedido de ventas a partir de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="223e6-124">Use this method to purchase items when you create a sales order from a project.</span></span></td>
<td><span data-ttu-id="223e6-125">Los artículos se consumen al facturar el pedido de ventas al cliente.</span><span class="sxs-lookup"><span data-stu-id="223e6-125">Items are consumed when the sales order is invoiced to the customer.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="223e6-126">Cree un pedido de compra a partir de un artículo requerido.</span><span class="sxs-lookup"><span data-stu-id="223e6-126">Create a purchase order from an item requirement.</span></span></td>
<td><span data-ttu-id="223e6-127">Utilice este método para adquirir artículos al crear un artículo requerido a partir de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="223e6-127">Use this method to purchase items when you create an item requirement from a project.</span></span></td>
<td><span data-ttu-id="223e6-128">Los artículos se consumen al actualizar el requisito de artículo.</span><span class="sxs-lookup"><span data-stu-id="223e6-128">Items are consumed when the item requirement packing slip is updated.</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE] 
> <span data-ttu-id="223e6-129">Al actualizar la factura del proveedor o albarán, se solicita que actualice el albarán con el artículo requerido.</span><span class="sxs-lookup"><span data-stu-id="223e6-129">When you update the vendor invoice or packing slip, you're prompted to update the packing slip on the item requirement.</span></span>

<span data-ttu-id="223e6-130">Para obtener más información, consulte [Recibir artículos en pedido de compra de requisito de artículo](tasks/receive-items-purchase-order-item-requirement.md).</span><span class="sxs-lookup"><span data-stu-id="223e6-130">For more information, see [Receive items on purchase order from item requirement](tasks/receive-items-purchase-order-item-requirement.md).</span></span>


