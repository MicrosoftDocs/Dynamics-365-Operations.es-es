---
title: Restringir métodos de pago para devoluciones sin un recibo
description: Este tema describe cómo determinados tipos de pago se pueden limitar para la devolución si las devoluciones se crean sin un recibo.
author: rapraj
manager: AnnBe
ms.date: 01/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2019-02-01
ms.dyn365.ops.version: AX 10.0.0, Retail Feb 2019 update
ms.openlocfilehash: 1f84a6382453c0ba7540e618ad90ae1d3c684a2b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "315921"
---
# <a name="restrict-payment-methods-for-returns-without-a-receipt"></a><span data-ttu-id="81c20-103">Restringir métodos de pago para devoluciones sin un recibo</span><span class="sxs-lookup"><span data-stu-id="81c20-103">Restrict payment methods for returns without a receipt</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="81c20-104">Al configurar el sistema, se deben configurar todos los tipos de pago que acepte un minorista.</span><span class="sxs-lookup"><span data-stu-id="81c20-104">Each payment type that a retailer accepts must be configured when the system is set up.</span></span> <span data-ttu-id="81c20-105">Este tema describe cómo determinados tipos de pago se pueden limitar para la devolución si las devoluciones se crean sin un recibo.</span><span class="sxs-lookup"><span data-stu-id="81c20-105">This topic describes how certain payment types can be restricted for refund if the returns are made without a receipt.</span></span>

## <a name="set-up-payment-methods"></a><span data-ttu-id="81c20-106">Configurar métodos de pago</span><span class="sxs-lookup"><span data-stu-id="81c20-106">Set up payment methods</span></span>

<span data-ttu-id="81c20-107">Para configurar los métodos de pago, debe completar las tareas siguientes.</span><span class="sxs-lookup"><span data-stu-id="81c20-107">To set up payment methods, the following tasks must be completed.</span></span>
1. <span data-ttu-id="81c20-108">Cree métodos de pago aceptados en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="81c20-108">Create the payment methods that are accepted by the entire organization.</span></span>
2. <span data-ttu-id="81c20-109">Creación de tipos y números de tarjeta de la organización.</span><span class="sxs-lookup"><span data-stu-id="81c20-109">Create organization-wide card types and card numbers.</span></span> <span data-ttu-id="81c20-110">Si desea aceptar tarjetas de crédito o de débito, debe crear un método de pago para tarjetas y, a continuación, los tipos y números de tarjeta de la organización.</span><span class="sxs-lookup"><span data-stu-id="81c20-110">If credit cards or debit cards are accepted, you must create one payment method for cards, and then create the organization-wide card types and card numbers.</span></span>
3. <span data-ttu-id="81c20-111">Configurar métodos de pago en tienda.</span><span class="sxs-lookup"><span data-stu-id="81c20-111">Set up store payment methods.</span></span> <span data-ttu-id="81c20-112">Asocie métodos de pago a cada tienda e indique la configuración específica de la tienda para cada método de pago.</span><span class="sxs-lookup"><span data-stu-id="81c20-112">Associate payment methods with each store, and then enter the store-specific settings for each payment method.</span></span>
4. <span data-ttu-id="81c20-113">Configurar tipos de pago con tarjeta para tiendas.</span><span class="sxs-lookup"><span data-stu-id="81c20-113">Set up card payment methods for stores.</span></span> <span data-ttu-id="81c20-114">Complete la configuración de tarjeta para todos los métodos de pago con tarjeta que acepte la tienda.</span><span class="sxs-lookup"><span data-stu-id="81c20-114">For any card payment methods that the store accepts, complete the card setup.</span></span>

<span data-ttu-id="81c20-115">![Configuración de tienda al por menor](media/NoReceiptReturns1.png "Configuración de tienda al por menor")</span><span class="sxs-lookup"><span data-stu-id="81c20-115">![Retail Store Setup](media/NoReceiptReturns1.png "Retail Store Setup")</span></span> 


## <a name="restrict-payment-methods-for-returns-without-a-receipt"></a><span data-ttu-id="81c20-116">Restringir métodos de pago para devoluciones sin un recibo</span><span class="sxs-lookup"><span data-stu-id="81c20-116">Restrict payment methods for returns without a receipt</span></span>

<span data-ttu-id="81c20-117">Para cada método de pago de tienda, en la página **Administración de tienda minorista** , en **Devoluciones sin recibo**, establezca **Limitar las devoluciones sin recibo** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="81c20-117">For each store payment method, on the **Retail store management** page, under **Non receipt returns**, set **Restrict for refunds without receipt** to **Yes**.</span></span> 

<span data-ttu-id="81c20-118">El valor predeterminado es **No**, que garantiza que el método de pago se tiene en cuenta para devoluciones.</span><span class="sxs-lookup"><span data-stu-id="81c20-118">The default value of the toggle is **No**, which ensures that the payment method is allowed for refunds.</span></span> 

<span data-ttu-id="81c20-119">Cuando **Limitar devoluciones sin recibo** se establece en **Sí**, el método de pago seleccionado no se permitirá para las devoluciones.</span><span class="sxs-lookup"><span data-stu-id="81c20-119">When **Restrict for refunds without receipt** is set to **Yes**, the selected payment method will not be allowed for refunds.</span></span> 

<span data-ttu-id="81c20-120">![Método de pago en tienda minorista](media/NoReceiptReturns3.png "Método de pago en tienda minorista")</span><span class="sxs-lookup"><span data-stu-id="81c20-120">![Retail Store payment method](media/NoReceiptReturns3.png "Retail Store Payment Method")</span></span> 

> [!NOTE]
> <span data-ttu-id="81c20-121">Si un cajero selecciona un método de pago limitado para la devolución sin un recibo, aparece un mensaje para comprobar los métodos de los pagos aceptables.</span><span class="sxs-lookup"><span data-stu-id="81c20-121">When a cashier selects a payment method that is restricted for refund without a receipt, a message displays to verify the acceptable payment methods.</span></span>

<span data-ttu-id="81c20-122">![Métodos de pago aceptables](media/NoReceiptReturns4.png "Métodos de pago aceptables")</span><span class="sxs-lookup"><span data-stu-id="81c20-122">![Acceptable payment methods](media/NoReceiptReturns4.png "Acceptable payment methods")</span></span> 

<span data-ttu-id="81c20-123">Si una transacción tiene una devolución con recibo como sin él, las condiciones de la restricción no se aplicarán porque la transacción será un flujo de trabajo de devolución con un recibo.</span><span class="sxs-lookup"><span data-stu-id="81c20-123">If a transaction has both a receipted return and a return without a receipt, the restriction conditions will not be enforced because the transaction will be a return workflow with a receipt.</span></span> 

