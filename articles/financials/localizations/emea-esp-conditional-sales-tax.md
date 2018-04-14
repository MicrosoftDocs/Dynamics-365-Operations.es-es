---
title: "Impuesto condicional para pagarés o letras de cambio protestados"
description: "Este tema proporciona información acerca de los pagarés o letras de cambio para las entidades jurídicas en España."
author: ShylaThompson
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankBillOfExchangeTable, BankPromissoryNoteTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 271503
ms.search.region: Spain
ms.author: v-elgolu
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: dcd26110e72552ce5a067e919d3c4cb2f8d8cfb1
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="conditional-sales-tax-for-protested-promissory-notes-or-bills-of-exchange"></a><span data-ttu-id="e358f-103">Impuesto condicional para pagarés o letras de cambio protestados</span><span class="sxs-lookup"><span data-stu-id="e358f-103">Conditional sales tax for protested promissory notes or bills of exchange</span></span>
[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="e358f-104">Para las entidades jurídicas en España, si un pago de pagaré para un proveedor o un pago de letra de cambio para un cliente se liquida contra una factura que incluye impuestos condicionales, y se protesta el acuerdo, la cancelación del impuesto se registra con un comprobante relacionado con el asiento de la cancelación del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="e358f-104">For legal entities in Spain, if a promissory note payment for a vendor or a bill of exchange payment for a customer is settled against an invoice that includes conditional tax, and you protest the settlement, the cancellation of conditional tax is registered with a voucher that is related to the settlement cancellation voucher.</span></span>

<span data-ttu-id="e358f-105">El *impuesto condicional* es un impuesto que se paga de forma proporcional al importe real que se paga en una factura.</span><span class="sxs-lookup"><span data-stu-id="e358f-105">*Conditional sales tax* is sales tax that is paid proportionally to the actual amount that is paid on an invoice.</span></span> <span data-ttu-id="e358f-106">Para obtener más información acerca de un impuesto condicional, vea [Visión general de impuestos](../general-ledger/indirect-taxes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e358f-106">For more information about conditional tax, see [Sales tax overview](../general-ledger/indirect-taxes-overview.md).</span></span> <span data-ttu-id="e358f-107">Un *pagaré* es un acuerdo escrito en el que el emisor del pagaré promete pagar una cantidad concreta en un momento concreto.</span><span class="sxs-lookup"><span data-stu-id="e358f-107">A *promissory note* is a written agreement in which the maker of the note promises to pay a specific amount at a specific time.</span></span> <span data-ttu-id="e358f-108">Una *letra de cambio* es una orden escrita o electrónica de un cliente que especifica que otra parte (normalmente un banco) debe pagar un importe establecido a la empresa.</span><span class="sxs-lookup"><span data-stu-id="e358f-108">A *bill of exchange* is a written or electronic order from a customer that specifies that another party (usually a bank) should pay a stated amount to the company.</span></span> <span data-ttu-id="e358f-109">Para obtener más información acerca de letras de cambio, consulte [Configurar letras de cambio](../accounts-receivable/set-up-bills-exchange.md).</span><span class="sxs-lookup"><span data-stu-id="e358f-109">For more information about bills of exchange, see [Set up bills of exchange](../accounts-receivable/set-up-bills-exchange.md).</span></span>

## <a name="conditional-sales-tax-for-protested-promissory-notes"></a><span data-ttu-id="e358f-110">Impuesto condicional para los pagarés impagados</span><span class="sxs-lookup"><span data-stu-id="e358f-110">Conditional sales tax for protested promissory notes</span></span>
<span data-ttu-id="e358f-111">Cuando un usuario registra un diario de renegociación de pagarés, se anulan las transacciones registradas anteriormente si un pagaré se ha liquidado contra la factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="e358f-111">When a user posts a Redraw promissory note journal, transactions that were previously posted are reversed if a promissory note was settled against a vendor invoice.</span></span> <span data-ttu-id="e358f-112">Si la factura incluía impuestos condicionales cuando se liquidó con un pagaré, se registra una transacción de impuestos para los impuestos condicionales.</span><span class="sxs-lookup"><span data-stu-id="e358f-112">If the invoice included conditional tax when it was settled against a promissory note, a tax transaction for the conditional tax is posted.</span></span> <span data-ttu-id="e358f-113">Para las entidades jurídicas de España, si el pagaré se ha liquidado con una factura que incluye impuestos condicionales, se invierte la transacción de impuestos cuando se registra un diario de pagarés renegociados.</span><span class="sxs-lookup"><span data-stu-id="e358f-113">For legal entities in Spain, if the promissory note was settled against an invoice that includes conditional tax, the tax transaction is reversed when a Redraw promissory note journal is posted.</span></span> <span data-ttu-id="e358f-114">Para ver las transacciones invertidas, vaya a **Transacciones de asiento** &gt; **Asientos relacionados**.</span><span class="sxs-lookup"><span data-stu-id="e358f-114">To view reverse transactions, go to **Voucher transactions** &gt; **Related vouchers**.</span></span>

## <a name="conditional-sales-tax-for-protested-bills-of-exchange"></a><span data-ttu-id="e358f-115">Impuesto condicional para letras de cambio impagadas</span><span class="sxs-lookup"><span data-stu-id="e358f-115">Conditional sales tax for protested bills of exchange</span></span>
<span data-ttu-id="e358f-116">Cuando un usuario registra un diario de impago de letras de cambio, se anulan las transacciones registradas anteriormente si una letra de cambio se ha liquidado con la factura de cliente.</span><span class="sxs-lookup"><span data-stu-id="e358f-116">When a user posts a Protest bill of exchange journal, transactions that were previously posted are reversed if a bill of exchange was settled against a customer invoice.</span></span> <span data-ttu-id="e358f-117">Si la factura incluía impuestos condicionales cuando se liquidó con una letra de cambio, se registra una transacción de impuestos para los impuestos condicionales.</span><span class="sxs-lookup"><span data-stu-id="e358f-117">If the invoice included conditional tax when it was settled against a bill of exchange, a tax transaction for the conditional tax is posted.</span></span> <span data-ttu-id="e358f-118">Para las entidades jurídicas de España, si la letra de cambio se ha liquidado con una factura que incluye impuestos condicionales, se invierte la transacción de impuestos cuando se registra un diario de impago de letras de cambio.</span><span class="sxs-lookup"><span data-stu-id="e358f-118">For legal entities in Spain, if the bill of exchange was settled against an invoice that includes conditional tax, the tax transaction is reversed when a Protest bill of exchange journal is posted.</span></span> <span data-ttu-id="e358f-119">Para ver las transacciones invertidas, vaya a **Transacciones de asiento** &gt; **Asientos relacionados**.</span><span class="sxs-lookup"><span data-stu-id="e358f-119">To view reverse transactions, go to **Voucher transactions** &gt; **Related vouchers**.</span></span>



