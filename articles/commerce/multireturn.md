---
title: Devolver artículos a través de múltiples pedidos y facturas de clientes
description: En este tema se describe la funcionalidad que permite realizar devoluciones a través de múltiples pedidos y facturas de clientes en Dynamics 365 Commerce.
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
ms.openlocfilehash: c5f17424f0837344030f9ce2d2d037cde08c4e49
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004467"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a><span data-ttu-id="bc1ab-103">Devolver artículos a través de múltiples pedidos y facturas de clientes</span><span class="sxs-lookup"><span data-stu-id="bc1ab-103">Return items across multiple customer orders and invoices</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="bc1ab-104">Las devoluciones se pueden realizar a través de múltiples pedidos y facturas de clientes.</span><span class="sxs-lookup"><span data-stu-id="bc1ab-104">Returns can be made across multiple orders and invoices.</span></span> 

## <a name="configure-commerce-to-support-returns-across-multiple-customer-order-and-invoices"></a><span data-ttu-id="bc1ab-105">Configure Commerce para admitir devoluciones a través de múltiples pedidos y facturas de clientes</span><span class="sxs-lookup"><span data-stu-id="bc1ab-105">Configure Commerce to support returns across multiple customer order and invoices</span></span>

1. <span data-ttu-id="bc1ab-106">Vaya a **Parámetros de Commerce \> Pedidos de cliente**.</span><span class="sxs-lookup"><span data-stu-id="bc1ab-106">Go to **Commerce parameters \> Customer orders**.</span></span>
1. <span data-ttu-id="bc1ab-107">Active el parámetro **Permitir devoluciones para múltiples pedidos**.</span><span class="sxs-lookup"><span data-stu-id="bc1ab-107">Turn on the **Enable returns for multiple orders** parameter.</span></span> 

## <a name="process-returns"></a><span data-ttu-id="bc1ab-108">Procesar devoluciones</span><span class="sxs-lookup"><span data-stu-id="bc1ab-108">Process returns</span></span>

<span data-ttu-id="bc1ab-109">Después de que el parámetro se active y los cambios se sincronicen en las tiendas, el cajero de la tienda puede seleccionar múltiples pedidos de ventas a un cliente para su devolución.</span><span class="sxs-lookup"><span data-stu-id="bc1ab-109">After the parameter is turned on and the changes are synchronized to the stores, the cashier in the store can select multiple sales orders for a customer for their return.</span></span>

<span data-ttu-id="bc1ab-110">Cuando se seleccionan los pedidos, se mostrará una lista de todos los productos que se pueden devolver en todas las facturas para los pedidos.</span><span class="sxs-lookup"><span data-stu-id="bc1ab-110">When the orders are selected, a list of all the returnable products across all the invoices for the orders will display.</span></span> <span data-ttu-id="bc1ab-111">El cajero puede seleccionar los productos que se van a devolver.</span><span class="sxs-lookup"><span data-stu-id="bc1ab-111">The cashier can then select the products to return.</span></span> <span data-ttu-id="bc1ab-112">Se creará un único pedido de devolución para todos los productos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="bc1ab-112">A single return order will be created for all the selected products.</span></span>
