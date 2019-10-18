---
title: Pedidos de compra para un proyecto
description: Este artículo describe los distintos métodos que puede usar para crear pedidos de compra para un proyecto. El método que use depende del propósito del pedido de compra y de la fecha de consumo y de cargo a un proyecto de los artículos comprados.
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a4975b9f9e20906fb1259e36a07d8ef3db4f4fee
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174567"
---
# <a name="purchase-orders-for-a-project"></a><span data-ttu-id="90593-104">Pedidos de compra para un proyecto</span><span class="sxs-lookup"><span data-stu-id="90593-104">Purchase orders for a project</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="90593-105">Este artículo describe los distintos métodos que puede usar para crear pedidos de compra para un proyecto.</span><span class="sxs-lookup"><span data-stu-id="90593-105">This article describes the various methods that you can use to create purchase orders for a project.</span></span> <span data-ttu-id="90593-106">El método que use depende del propósito del pedido de compra y de la fecha de consumo y de cargo a un proyecto de los artículos comprados.</span><span class="sxs-lookup"><span data-stu-id="90593-106">The method that you use depends on the purpose of the purchase order, and when the purchased items are consumed and charged to a project.</span></span>

### <a name="methods-for-creating-a-purchase-order"></a><span data-ttu-id="90593-107">Métodos de creación de un pedido de compra</span><span class="sxs-lookup"><span data-stu-id="90593-107">Methods for creating a purchase order</span></span>

<span data-ttu-id="90593-108">Puede usar uno de los siguientes métodos para crear un pedido de compra en Gestión de proyectos y contabilidad.</span><span class="sxs-lookup"><span data-stu-id="90593-108">You can use one of the following methods to create a purchase order in Project management and accounting.</span></span> <span data-ttu-id="90593-109">La finalidad del pedido de compra determina cuándo se consume el pedido de compra y, por tanto, cuándo se cargan los artículos a un proyecto.</span><span class="sxs-lookup"><span data-stu-id="90593-109">The purpose of the purchase order determines when the purchase order is consumed and, therefore, when items are charged to a project.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90593-110">Método</span><span class="sxs-lookup"><span data-stu-id="90593-110">Method</span></span></th>
<th><span data-ttu-id="90593-111">Propósito</span><span class="sxs-lookup"><span data-stu-id="90593-111">Purpose</span></span></th>
<th><span data-ttu-id="90593-112">Consumo de artículos</span><span class="sxs-lookup"><span data-stu-id="90593-112">Consumption of items</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="90593-113">Cree un pedido de compra directamente de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="90593-113">Create a purchase order directly from a project.</span></span></td>
<td><span data-ttu-id="90593-114">Use este método para comprar artículos de un proveedor externo para consumo en un proyecto.</span><span class="sxs-lookup"><span data-stu-id="90593-114">Use this method to purchase items from an external vendor for consumption on a project.</span></span> <span data-ttu-id="90593-115">Puede crear el pedido de compra de dos formas:</span><span class="sxs-lookup"><span data-stu-id="90593-115">You can create the purchase order in two ways:</span></span>
<ul>
<li><span data-ttu-id="90593-116">Desde el propio proyecto.</span><span class="sxs-lookup"><span data-stu-id="90593-116">From the project itself.</span></span> <span data-ttu-id="90593-117">En este caso, el proyecto ya está definido para el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="90593-117">In this case, the project is already defined for the purchase order.</span></span></li>
<li><span data-ttu-id="90593-118">Desplazándose hasta el pedido de compra del proyecto.</span><span class="sxs-lookup"><span data-stu-id="90593-118">By navigating to the project purchase order.</span></span> <span data-ttu-id="90593-119">Debe seleccionar tanto el proveedor como el proyecto para el que se creará el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="90593-119">You must select both the vendor and the project to create the purchase order for.</span></span></li>
</ul></td>
<td><span data-ttu-id="90593-120">Los artículos se consumen al actualizar la factura del proveedor.</span><span class="sxs-lookup"><span data-stu-id="90593-120">Items are consumed when the vendor invoice is updated.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="90593-121">Cree un pedido de venta a partir de un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="90593-121">Create a purchase order from a sales order.</span></span></td>
<td><span data-ttu-id="90593-122">Utilice este método para adquirir artículos al crear un pedido de ventas a partir de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="90593-122">Use this method to purchase items when you create a sales order from a project.</span></span></td>
<td><span data-ttu-id="90593-123">Los artículos se consumen al facturar el pedido de ventas al cliente.</span><span class="sxs-lookup"><span data-stu-id="90593-123">Items are consumed when the sales order is invoiced to the customer.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="90593-124">Cree un pedido de compra a partir de un artículo requerido.</span><span class="sxs-lookup"><span data-stu-id="90593-124">Create a purchase order from an item requirement.</span></span></td>
<td><span data-ttu-id="90593-125">Utilice este método para adquirir artículos al crear un artículo requerido a partir de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="90593-125">Use this method to purchase items when you create an item requirement from a project.</span></span></td>
<td><span data-ttu-id="90593-126">Los artículos se consumen al actualizar el requisito de artículo.</span><span class="sxs-lookup"><span data-stu-id="90593-126">Items are consumed when the item requirement packing slip is updated.</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE] 
> <span data-ttu-id="90593-127">Al actualizar la factura del proveedor o albarán, se solicita que actualice el albarán con el artículo requerido.</span><span class="sxs-lookup"><span data-stu-id="90593-127">When you update the vendor invoice or packing slip, you're prompted to update the packing slip on the item requirement.</span></span>

<span data-ttu-id="90593-128">Para obtener más información, consulte [Recibir artículos en pedido de compra de requisito de artículo](tasks/receive-items-purchase-order-item-requirement.md).</span><span class="sxs-lookup"><span data-stu-id="90593-128">For more information, see [Receive items on purchase order from item requirement](tasks/receive-items-purchase-order-item-requirement.md).</span></span>

