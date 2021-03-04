---
title: Devolver artículos a través de múltiples pedidos y facturas de clientes
description: En este tema se describe la funcionalidad que permite realizar devoluciones a través de múltiples pedidos y facturas de clientes en Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 08/27/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: ee4c863e617b9351e55e1fc652ea8905f17c8346
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976672"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a><span data-ttu-id="700f0-103">Devolver artículos a través de múltiples pedidos y facturas de clientes</span><span class="sxs-lookup"><span data-stu-id="700f0-103">Return items across multiple customer orders and invoices</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="700f0-104">En este artículo se describen dos características que optimizan las devoluciones de pedidos de clientes en varias facturas.</span><span class="sxs-lookup"><span data-stu-id="700f0-104">This article describes two features that optimize customer order returns over multiple invoices.</span></span> 

## <a name="enable-refunds-over-multiple-captures"></a><span data-ttu-id="700f0-105">Habilitar devoluciones en varias capturas</span><span class="sxs-lookup"><span data-stu-id="700f0-105">Enable refunds over multiple captures</span></span>

<span data-ttu-id="700f0-106">Esta característica permite varias devoluciones vinculadas con el mismo pedido de cliente.</span><span class="sxs-lookup"><span data-stu-id="700f0-106">This feature enables multiple linked refunds against the same customer order.</span></span> 

1. <span data-ttu-id="700f0-107">Vaya al espacio de trabajo **Administración de características** y busque **Habilitar devoluciones en varias capturas**.</span><span class="sxs-lookup"><span data-stu-id="700f0-107">Go to the **Feature management** workspace and search for **Enable refunds over multiple captures**.</span></span>
2. <span data-ttu-id="700f0-108">Seleccione **Habilitar devoluciones en varios pedidos** y luego haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="700f0-108">Select **Enable refunds over multiple orders** and then click **Enable**.</span></span> 

## <a name="enable-proper-tax-calculation-for-returns-with-partial-quantity"></a><span data-ttu-id="700f0-109">Habilitar el cálculo de impuestos correcto para devoluciones con cantidad parcial</span><span class="sxs-lookup"><span data-stu-id="700f0-109">Enable proper tax calculation for returns with partial quantity</span></span>

<span data-ttu-id="700f0-110">Esta característica garantiza que cuando se devuelve un pedido con varias facturas, los impuestos serán, finalmente, iguales al importe de impuestos cargado originalmente.</span><span class="sxs-lookup"><span data-stu-id="700f0-110">This feature ensures that when an order is returned using multiple invoices, the taxes will ultimately be equal to the tax amount originally charged.</span></span> 

1. <span data-ttu-id="700f0-111">Vaya al espacio de trabajo **Administración de características** y busque **Habilitar el cálculo de impuestos correcto para devoluciones con cantidad parcial**.</span><span class="sxs-lookup"><span data-stu-id="700f0-111">Go to the **Feature management** workspace and search for **Enable proper tax calculation for returns with partial quantity**.</span></span>
2. <span data-ttu-id="700f0-112">Seleccione **Habilitar el cálculo de impuestos correcto para devoluciones con cantidad parcial** y luego haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="700f0-112">Select **Enable proper tax calculation for returns with partial quantity** and then click **Enable**.</span></span> 


## <a name="process-returns"></a><span data-ttu-id="700f0-113">Procesar devoluciones</span><span class="sxs-lookup"><span data-stu-id="700f0-113">Process returns</span></span>

<span data-ttu-id="700f0-114">Después de que estas características se activen y los cambios se sincronicen en las tiendas, el cajero de la tienda puede seleccionar múltiples pedidos de ventas a un cliente para su devolución.</span><span class="sxs-lookup"><span data-stu-id="700f0-114">After these features are turned on and the changes are synchronized to the stores, the cashier in the store can select multiple sales orders for a customer for their return.</span></span>

<span data-ttu-id="700f0-115">Cuando se seleccionan los pedidos, se mostrará una lista de todos los productos que se pueden devolver en todas las facturas para los pedidos.</span><span class="sxs-lookup"><span data-stu-id="700f0-115">When the orders are selected, a list of all the returnable products across all the invoices for the orders will display.</span></span> <span data-ttu-id="700f0-116">El cajero puede seleccionar los productos que se van a devolver.</span><span class="sxs-lookup"><span data-stu-id="700f0-116">The cashier can then select the products to return.</span></span> <span data-ttu-id="700f0-117">Se creará un único pedido de devolución para todos los productos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="700f0-117">A single return order will be created for all the selected products.</span></span>

<span data-ttu-id="700f0-118">Si el pedido se devuelve en su totalidad, la cantidad de impuestos devueltos al cliente será igual a la cantidad de impuestos cargada originalmente.</span><span class="sxs-lookup"><span data-stu-id="700f0-118">If the order is fully returned, the amount of taxes returned to the customer will be equal to the amount of tax originally charged.</span></span>

