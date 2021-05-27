---
title: Cálculo de TDS en transacciones de empresas vinculadas
description: Este tema describe el proceso que se utiliza para calcular los impuestos deducidos en el origen (TDS) en transacciones entre empresas vinculadas.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 0e304747cc93bfe0a39beababc3182ca14664b11
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023571"
---
# <a name="tds-calculation-on-intercompany-transactions"></a><span data-ttu-id="0392f-103">Cálculo de TDS en transacciones de empresas vinculadas</span><span class="sxs-lookup"><span data-stu-id="0392f-103">TDS calculation on intercompany transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0392f-104">Este tema describe el proceso que se utiliza para calcular los impuestos deducidos en el origen (TDS) en transacciones entre empresas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="0392f-104">This topic describes the process that is used to calculate Tax Deducted at Source (TDS) on intercompany transactions in phases.</span></span>

<span data-ttu-id="0392f-105">Cuando se crea un pedido de compra o pedido de venta entre empresas vinculadas, el grupo de TDS predeterminado que se define para el cliente o proveedor se utiliza para calcular el importe de TDS.</span><span class="sxs-lookup"><span data-stu-id="0392f-105">When an intercompany purchase order or sales order is created, the default TDS group that is defined for the customer or vendor is used to calculate the TDS amount.</span></span> <span data-ttu-id="0392f-106">El importe de TDS se registra en las cuentas recuperables o de proveedor después de que se registre la factura.</span><span class="sxs-lookup"><span data-stu-id="0392f-106">The TDS amount is posted to the recoverable or payable accounts after the invoice is posted.</span></span>

<span data-ttu-id="0392f-107">Se crea automáticamente un pedido de venta o un pedido de compra entre empresas vinculadas para el pedido de compra o el pedido de venta original.</span><span class="sxs-lookup"><span data-stu-id="0392f-107">An intercompany sales order or purchase order is automatically created for the original purchase order or sales order.</span></span> <span data-ttu-id="0392f-108">El grupo de TDS predeterminado se muestra en el pedido entre empresas vinculadas, de modo que se puedan calcular los TDS.</span><span class="sxs-lookup"><span data-stu-id="0392f-108">The default TDS group is shown on the intercompany order, so that TDS can be calculated.</span></span> <span data-ttu-id="0392f-109">Es posible cambiar el grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="0392f-109">You can change the TDS group.</span></span> <span data-ttu-id="0392f-110">La factura se puede registrar solo si el importe neto de la factura en el pedido de empresas vinculadas que se crea automáticamente coincide con el importe neto de la factura en el pedido original.</span><span class="sxs-lookup"><span data-stu-id="0392f-110">The invoice can be posted only if the net invoice amount on the intercompany order that is automatically created matches the net invoice amount on the original order.</span></span> <span data-ttu-id="0392f-111">(El importe neto es el importe de la factura después de deducir los TDS).</span><span class="sxs-lookup"><span data-stu-id="0392f-111">(The net amount is the invoice amount after TDS is deducted.)</span></span>

<span data-ttu-id="0392f-112">Por ejemplo, se crea una factura de venta por 50 000 y se adjunta el grupo de TDS del **10 %**.</span><span class="sxs-lookup"><span data-stu-id="0392f-112">For example, a sales invoice is created for 50,000, and the **10%** TDS group is attached to it.</span></span> <span data-ttu-id="0392f-113">El importe de la factura registrada es de 45 000 y el importe de TDS registrado para la factura de venta es de 5000.</span><span class="sxs-lookup"><span data-stu-id="0392f-113">The posted invoice amount is 45,000, and the posted TDS amount for the sales invoice is 5,000.</span></span> <span data-ttu-id="0392f-114">Se crea automáticamente un pedido de compra para el pedido de venta de empresas vinculadas y se adjunta el grupo de TDS del **10 %**.</span><span class="sxs-lookup"><span data-stu-id="0392f-114">A purchase order is automatically created for the intercompany sales order, and the  **10%** TDS group is attached to it.</span></span> <span data-ttu-id="0392f-115">Si cambia el grupo de TDS a **15 %**, no puede registrar la factura porque el importe neto de la factura del pedido de ventas de empresas vinculadas que se creó automáticamente no coincide con el importe neto de la factura del pedido de venta original.</span><span class="sxs-lookup"><span data-stu-id="0392f-115">If you change the TDS group to **15%**, you can't post the invoice, because the net invoice amount of the intercompany sales order that was automatically created doesn't match the net invoice amount of the original sales order.</span></span>

<span data-ttu-id="0392f-116">Un diario de pagos que se crea para una factura de empresas vinculadas se registra automáticamente.</span><span class="sxs-lookup"><span data-stu-id="0392f-116">A payment journal that is created for an intercompany invoice is automatically posted.</span></span> <span data-ttu-id="0392f-117">Ese diario de pagos se puede registrar solo si el importe del pago neto en él coincide con el importe del pago neto en el diario de pagos original.</span><span class="sxs-lookup"><span data-stu-id="0392f-117">That payment journal can be posted only if the net payment amount on it matches the net payment amount on the original payment journal.</span></span>
