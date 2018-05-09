---
title: Retenciones de pedido
description: Este tema describe los pedidos en espera usando Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: MCRHoldCodeTable, MCRSalesTableOrderHistory, MCRHoldCodeTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 106ce40f93704e67e53db2e62ae481d271aed755
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="order-holds"></a><span data-ttu-id="59d33-103">Retenciones de pedido</span><span class="sxs-lookup"><span data-stu-id="59d33-103">Order holds</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="59d33-104">Este tema describe los pedidos en espera usando Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="59d33-104">This topic describes holds on orders using Dynamics 365 for Retail.</span></span>

<span data-ttu-id="59d33-105">Un pedido puede estar en espera por varios motivos.</span><span class="sxs-lookup"><span data-stu-id="59d33-105">An order can be put on hold for various reasons.</span></span> <span data-ttu-id="59d33-106">Por ejemplo, puede poner un pedido en espera hasta que la dirección o el método de pago de un cliente se pueda comprobar o hasta que un director pueda revisar el límite de crédito del cliente.</span><span class="sxs-lookup"><span data-stu-id="59d33-106">For example, you might put an order on hold until the customer address or payment method can be verified, or until a manager can review the customer’s credit limit.</span></span> <span data-ttu-id="59d33-107">Durante el proceso de ventas, hay veces en que los pedidos de ventas deben ponerse en espera.</span><span class="sxs-lookup"><span data-stu-id="59d33-107">During the sales process, there are times when sales orders must be put on hold.</span></span> <span data-ttu-id="59d33-108">Por ejemplo, un pedido de ventas podría ponerse en espera debido a problemas con el pago de un cliente, sospecha de fraude o porque un director debe revisar el pedido.</span><span class="sxs-lookup"><span data-stu-id="59d33-108">For example, a sales order might be put on hold because of issues with a customer payment, because of suspected fraud, or because a manager must review the order.</span></span> <span data-ttu-id="59d33-109">Cuando un pedido de ventas se pone en espera, un código de retención del pedido se asigna al pedido de ventas para indicar el motivo de la retención.</span><span class="sxs-lookup"><span data-stu-id="59d33-109">When a sales order is put on hold, an order hold code is assigned to the sales order to indicate the reason for the hold.</span></span> <span data-ttu-id="59d33-110">Los códigos de espera del pedido de ventas se configuran en **Ventas y marketing** &gt; **Configuración** &gt; **Pedidos de ventas** &gt; **Códigos de espera de pedidos**.</span><span class="sxs-lookup"><span data-stu-id="59d33-110">Sales order hold codes are configured at **Sales and marketing** &gt; **Setup** &gt; **Sales orders** &gt; **Order holds codes**.</span></span> <span data-ttu-id="59d33-111">Un pedido de ventas se puede poner en espera manualmente a la hora de creación del pedido o posteriormente.</span><span class="sxs-lookup"><span data-stu-id="59d33-111">A sales order can be put on hold manually at the time of order creation or later.</span></span> <span data-ttu-id="59d33-112">Además, un pedido se puede poner en espera automáticamente, en función de las reglas de fraudes.</span><span class="sxs-lookup"><span data-stu-id="59d33-112">Additionally, an order can be put on hold automatically, based on fraud rules.</span></span> <span data-ttu-id="59d33-113">Mientras que un pedido de ventas está en espera, puede que tenga que actualizarlo con más información.</span><span class="sxs-lookup"><span data-stu-id="59d33-113">While a sales order is on hold, you might have to update it with more information.</span></span> <span data-ttu-id="59d33-114">También puede que quiera desproteger el pedido de ventas a medida que continúa trabajando en él.</span><span class="sxs-lookup"><span data-stu-id="59d33-114">Alternatively, you might want to check out the sales order as you continue to work on it.</span></span> <span data-ttu-id="59d33-115">Puede desproteger un pedido de ventas, volver a protegerlo e incluso anular la desprotección de otro usuario mediante el banco de trabajo de espera del pedido (**Venta minorista** &gt; **Clientes** &gt; **Pedidos en espera**).</span><span class="sxs-lookup"><span data-stu-id="59d33-115">You can check out a sales order, check it back in, and even override the checkout of another user by using the order hold workbench (**Retail** &gt; **Customers** &gt; **Order holds**).</span></span> <span data-ttu-id="59d33-116">Cuando un pedido está listo para completar, debe quitar la retención antes de poder completar el proceso de pedido.</span><span class="sxs-lookup"><span data-stu-id="59d33-116">When an order is ready to be completed, you must remove the hold before you can complete the order process.</span></span>




