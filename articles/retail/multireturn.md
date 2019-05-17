---
title: Devolver artículos a través de múltiples pedidos y facturas de clientes
description: En este tema se describe la funcionalidad que permite devoluciones a través de múltiples pedidos y facturas de clientes en Microsoft Dynamics 365 for Retail.
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
ms.openlocfilehash: d410fde2cd127f8d644e6a385937b6bc98d74576
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517163"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a><span data-ttu-id="ca18d-103">Devolver artículos a través de múltiples pedidos y facturas de clientes</span><span class="sxs-lookup"><span data-stu-id="ca18d-103">Return items across multiple customer orders and invoices</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="ca18d-104">En la versión 10.0 de Dynamics 365 for Finance and Operations, se pueden hacer devoluciones a través de múltiples pedidos y facturas, mientras que en las versiones anteriores a la 10.0, las devoluciones solo se podían procesar mediante una única factura al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="ca18d-104">In Dynamics 365 for Finance and Operations version 10.0, returns can be made across multiple orders and invoices, whereas in releases prior to 10.0, returns could only be processed by a single invoice at a time.</span></span> 

## <a name="configure-retail-to-support-returns-across-multiple-customer-order-and-invoices"></a><span data-ttu-id="ca18d-105">Configure Retail para admitir devoluciones a través de múltiples pedidos y facturas de clientes</span><span class="sxs-lookup"><span data-stu-id="ca18d-105">Configure Retail to support returns across multiple customer order and invoices</span></span>

1. <span data-ttu-id="ca18d-106">Vaya a **Parámetros de Retail \> Pedidos de cliente**.</span><span class="sxs-lookup"><span data-stu-id="ca18d-106">Go to **Retail parameters \> Customer orders**.</span></span>
1. <span data-ttu-id="ca18d-107">Active el parámetro **Permitir devoluciones para múltiples pedidos**.</span><span class="sxs-lookup"><span data-stu-id="ca18d-107">Turn on the **Enable returns for multiple orders** parameter.</span></span> 

## <a name="process-returns"></a><span data-ttu-id="ca18d-108">Procesar devoluciones</span><span class="sxs-lookup"><span data-stu-id="ca18d-108">Process returns</span></span>

<span data-ttu-id="ca18d-109">Después de que el parámetro se active y los cambios se sincronicen en las tiendas, el cajero de la tienda puede seleccionar múltiples pedidos de ventas a un cliente para su devolución.</span><span class="sxs-lookup"><span data-stu-id="ca18d-109">After the parameter is turned on and the changes are synchronized to the stores, the cashier in the store can select multiple sales orders for a customer for their return.</span></span>

<span data-ttu-id="ca18d-110">Cuando se seleccionan los pedidos, se mostrará una lista de todos los productos que se pueden devolver en todas las facturas para los pedidos.</span><span class="sxs-lookup"><span data-stu-id="ca18d-110">When the orders are selected, a list of all the returnable products across all the invoices for the orders will display.</span></span> <span data-ttu-id="ca18d-111">El cajero puede seleccionar los productos que se van a devolver.</span><span class="sxs-lookup"><span data-stu-id="ca18d-111">The cashier can then select the products to return.</span></span> <span data-ttu-id="ca18d-112">Se creará un único pedido de devolución para todos los productos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="ca18d-112">A single return order will be created for all the selected products.</span></span>
