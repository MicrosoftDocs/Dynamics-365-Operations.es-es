---
title: Devolver artículos a través de múltiples pedidos y facturas de clientes
description: En este tema se describe la funcionalidad que permite realizar devoluciones a través de múltiples pedidos y facturas de clientes en Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 03/05/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 25a1081e5f903076e23089c41dda7437f8a70124
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "2017998"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a><span data-ttu-id="066f7-103">Devolver artículos a través de múltiples pedidos y facturas de clientes</span><span class="sxs-lookup"><span data-stu-id="066f7-103">Return items across multiple customer orders and invoices</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="066f7-104">Las devoluciones se pueden realizar a través de múltiples pedidos y facturas de clientes.</span><span class="sxs-lookup"><span data-stu-id="066f7-104">Returns can be made across multiple orders and invoices.</span></span> 

## <a name="configure-retail-to-support-returns-across-multiple-customer-order-and-invoices"></a><span data-ttu-id="066f7-105">Configure Retail para admitir devoluciones a través de múltiples pedidos y facturas de clientes</span><span class="sxs-lookup"><span data-stu-id="066f7-105">Configure Retail to support returns across multiple customer order and invoices</span></span>

1. <span data-ttu-id="066f7-106">Vaya a **Parámetros de Retail \> Pedidos de cliente**.</span><span class="sxs-lookup"><span data-stu-id="066f7-106">Go to **Retail parameters \> Customer orders**.</span></span>
1. <span data-ttu-id="066f7-107">Active el parámetro **Permitir devoluciones para múltiples pedidos**.</span><span class="sxs-lookup"><span data-stu-id="066f7-107">Turn on the **Enable returns for multiple orders** parameter.</span></span> 

## <a name="process-returns"></a><span data-ttu-id="066f7-108">Procesar devoluciones</span><span class="sxs-lookup"><span data-stu-id="066f7-108">Process returns</span></span>

<span data-ttu-id="066f7-109">Después de que el parámetro se active y los cambios se sincronicen en las tiendas, el cajero de la tienda puede seleccionar múltiples pedidos de ventas a un cliente para su devolución.</span><span class="sxs-lookup"><span data-stu-id="066f7-109">After the parameter is turned on and the changes are synchronized to the stores, the cashier in the store can select multiple sales orders for a customer for their return.</span></span>

<span data-ttu-id="066f7-110">Cuando se seleccionan los pedidos, se mostrará una lista de todos los productos que se pueden devolver en todas las facturas para los pedidos.</span><span class="sxs-lookup"><span data-stu-id="066f7-110">When the orders are selected, a list of all the returnable products across all the invoices for the orders will display.</span></span> <span data-ttu-id="066f7-111">El cajero puede seleccionar los productos que se van a devolver.</span><span class="sxs-lookup"><span data-stu-id="066f7-111">The cashier can then select the products to return.</span></span> <span data-ttu-id="066f7-112">Se creará un único pedido de devolución para todos los productos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="066f7-112">A single return order will be created for all the selected products.</span></span>
