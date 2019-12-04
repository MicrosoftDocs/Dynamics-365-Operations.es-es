---
title: Descripción de la liquidación
description: En este tema se proporciona información general sobre el proceso de liquidación. Describe los tipos de transacciones que se pueden liquidar, cuándo y cómo se pueden liquidar las transacciones y los resultados del proceso de liquidación.
author: kweekley
manager: AnnBe
ms.date: 05/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14551
ms.assetid: 0968fa71-5984-415b-8689-759a0136d5d1
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: b8b25575d5956e1345934512a7fe6503202b67a9
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179798"
---
# <a name="settlement-overview"></a><span data-ttu-id="b1b32-104">Descripción de la liquidación</span><span class="sxs-lookup"><span data-stu-id="b1b32-104">Settlement overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b1b32-105">En este tema se proporciona información general sobre el proceso de liquidación.</span><span class="sxs-lookup"><span data-stu-id="b1b32-105">This topic provides general information about the settlement process.</span></span> <span data-ttu-id="b1b32-106">Describe los tipos de transacciones que se pueden liquidar, cuándo y cómo se pueden liquidar las transacciones y los resultados del proceso de liquidación.</span><span class="sxs-lookup"><span data-stu-id="b1b32-106">It describes the types of transactions that can be settled, when and how transactions can be settled, and the results of the settlement process.</span></span>

<span data-ttu-id="b1b32-107">Durante la liquidación, las transacciones en un documento se aplican a las transacciones en otro documento para aumentar o reducir los saldos de cada documento.</span><span class="sxs-lookup"><span data-stu-id="b1b32-107">During settlement, the transactions on one document are applied to the transactions on another document to increase or decrease the balance of each document.</span></span> <span data-ttu-id="b1b32-108">Por ejemplo, un pago se puede aplicar a una factura.</span><span class="sxs-lookup"><span data-stu-id="b1b32-108">For example, a payment can be applied to an invoice.</span></span> <span data-ttu-id="b1b32-109">Los distintos tipos de transacción pueden liquidarse, en diferentes horas, y con distintos métodos.</span><span class="sxs-lookup"><span data-stu-id="b1b32-109">Various transaction types can be settled, at different times, and through various methods.</span></span> <span data-ttu-id="b1b32-110">La liquidación puede hacer que se generen nuevas transacciones.</span><span class="sxs-lookup"><span data-stu-id="b1b32-110">Settlement can also cause new transactions to be generated.</span></span>

## <a name="what-transactions-can-be-settled"></a><span data-ttu-id="b1b32-111">Qué transacciones se pueden liquidar</span><span class="sxs-lookup"><span data-stu-id="b1b32-111">What transactions can be settled</span></span>
<span data-ttu-id="b1b32-112">La liquidación dentro de Proveedores y Clientes puede tener lugar entre los tipos de transacción que afectan al saldo del proveedor o al saldo del cliente, como facturas, pagos, notas de crédito y cuotas.</span><span class="sxs-lookup"><span data-stu-id="b1b32-112">Settlement within Accounts payable and Account receivable can occur between any transaction types that affect the vendor balance or customer balance, such as invoices, payments, credit memos, and fees.</span></span> <span data-ttu-id="b1b32-113">Cualquier tipo de transacción puede liquidarse con cualquier otro tipo de transacción.</span><span class="sxs-lookup"><span data-stu-id="b1b32-113">Any transaction type can be settled against any other transaction type.</span></span> <span data-ttu-id="b1b32-114">Por ejemplo, puede liquidar un pago con una factura, una nota de crédito con una factura, una factura con una factura y un pago con un pago.</span><span class="sxs-lookup"><span data-stu-id="b1b32-114">For example, you can settle a payment against an invoice, a credit memo against an invoice, an invoice against an invoice, and a payment against a payment.</span></span> <span data-ttu-id="b1b32-115">Puede liquidar pagos con una transacción en la misma entidad jurídica o en otra entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="b1b32-115">You can settle payments against a transaction in the same legal entity or in a different legal entity.</span></span> <span data-ttu-id="b1b32-116">En las organizaciones que usan un modelo de pagos centralizados, las [pagos centralizados](set-up-centralized-payments.md) pueden ayudar a simplificar el proceso de pago.</span><span class="sxs-lookup"><span data-stu-id="b1b32-116">In organizations that use a centralized payment model, [centralized payments](set-up-centralized-payments.md) can help streamline the payment process.</span></span>

## <a name="when-to-settle-transactions"></a><span data-ttu-id="b1b32-117">Cuándo liquidar transacciones</span><span class="sxs-lookup"><span data-stu-id="b1b32-117">When to settle transactions</span></span>
<span data-ttu-id="b1b32-118">Las transacciones se pueden liquidar a la hora de entrada de pago.</span><span class="sxs-lookup"><span data-stu-id="b1b32-118">Transactions can be settled at the time of payment entry.</span></span> <span data-ttu-id="b1b32-119">Por ejemplo, si hace un pago a un proveedor, selecciona normalmente las facturas para pagar.</span><span class="sxs-lookup"><span data-stu-id="b1b32-119">For example, when you make a payment to a vendor, you typically select the invoices to pay.</span></span> <span data-ttu-id="b1b32-120">Al seleccionar facturas, se marcan para la liquidación contra el pago.</span><span class="sxs-lookup"><span data-stu-id="b1b32-120">By selecting invoices, you mark them for settlement against the payment.</span></span> <span data-ttu-id="b1b32-121">Cuando los vendedores de pago de clientes registran un pago de cliente, pueden marcar las facturas adecuadas para la liquidación, en función de la información que se incluye en el pago del cliente.</span><span class="sxs-lookup"><span data-stu-id="b1b32-121">When Accounts Receivable payment clerks record a customer payment, they can mark the appropriate invoices for settlement, based on the information that is included with the customer's payment.</span></span> <span data-ttu-id="b1b32-122">La página **Liquidar transacciones** se usa para marcar las transacciones para liquidación.</span><span class="sxs-lookup"><span data-stu-id="b1b32-122">The **Settle transactions** page is used to mark transactions for settlement.</span></span> <span data-ttu-id="b1b32-123">Esta página se puede abrir desde cualquier factura o pago sin registrar.</span><span class="sxs-lookup"><span data-stu-id="b1b32-123">This page can be opened from any unposted invoice or payment.</span></span> <span data-ttu-id="b1b32-124">Cuando se registra la transacción, también se registra la liquidación.</span><span class="sxs-lookup"><span data-stu-id="b1b32-124">When the transaction is posted, the settlement is also posted.</span></span> <span data-ttu-id="b1b32-125">Las transacciones también pueden liquidarse una vez registradas.</span><span class="sxs-lookup"><span data-stu-id="b1b32-125">Transactions can also be settled after they are posted.</span></span> <span data-ttu-id="b1b32-126">Puede especificar y registrar un pago de cliente sin liquidarlo con una factura.</span><span class="sxs-lookup"><span data-stu-id="b1b32-126">You can enter and post a customer payment without settling it against any invoices.</span></span> <span data-ttu-id="b1b32-127">Sin embargo, es posible que deba realizar una consulta en primer lugar para asegurarse de que el pago se liquida con la factura correcta.</span><span class="sxs-lookup"><span data-stu-id="b1b32-127">However, you might have to do research first, to make sure that the payment is settled against the correct invoice.</span></span> <span data-ttu-id="b1b32-128">La página **Liquidar transacciones** se puede abrir desde las páginas **Todos los clientes** o **Todos los proveedores**, o desde la página **Transacciones** para cualquier cliente o proveedor.</span><span class="sxs-lookup"><span data-stu-id="b1b32-128">The **Settle transactions** page can be opened from the **All customers** or **All vendors** page, or from the **Transactions** page for any customer or vendor.</span></span> <span data-ttu-id="b1b32-129">También puede reservar los anticipos registrados para una factura marcando el pago para la liquidación con un pedido de compra o un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="b1b32-129">You can also reserve posted prepayments for an invoice by marking the payment for settlement against a purchase order or sales order.</span></span> <span data-ttu-id="b1b32-130">En este caso, el pago todavía tendrá saldo de apertura, pero no se podrá liquidar con otra factura.</span><span class="sxs-lookup"><span data-stu-id="b1b32-130">In this case, the payment will still have an open balance, but it can't be settled against another invoice.</span></span> <span data-ttu-id="b1b32-131">El pago se liquidará automáticamente con la factura creada a partir del pedido de compra o el pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="b1b32-131">The payment will be automatically settled against the invoice that is created from the purchase order or sales order.</span></span>

## <a name="how-to-settle-transactions"></a><span data-ttu-id="b1b32-132">Cómo liquidar transacciones</span><span class="sxs-lookup"><span data-stu-id="b1b32-132">How to settle transactions</span></span>
<span data-ttu-id="b1b32-133">Las transacciones se pueden liquidar manualmente, automáticamente o mediante una combinación de los dos métodos.</span><span class="sxs-lookup"><span data-stu-id="b1b32-133">Transactions can be settled manually, automatically, or by using a combination of the two methods.</span></span> <span data-ttu-id="b1b32-134">La opción de un método de liquidación depende de los procesos empresariales, que después se pueden implementar a través de la configuración de la liquidación en los parámetros de Proveedores y de Clientes.</span><span class="sxs-lookup"><span data-stu-id="b1b32-134">The choice of a settlement method depends on business processes, which can then be implemented through the setup of settlement in Accounts payable parameters and Accounts receivable parameters.</span></span> <span data-ttu-id="b1b32-135">Puede crear pagos de proveedor y pagos por domiciliación bancaria del cliente mediante una propuesta de pago, que se usa para seleccionar facturas para pagar.</span><span class="sxs-lookup"><span data-stu-id="b1b32-135">You can create vendor payments and customer direct debit payments by using a payment proposal, which is used to select invoices to pay.</span></span> <span data-ttu-id="b1b32-136">La propuesta de pago se inicia manualmente, y entonces Dynamics 365 Finance marcará automáticamente las facturas seleccionadas para la liquidación cuando se creen los pagos.</span><span class="sxs-lookup"><span data-stu-id="b1b32-136">The payment proposal is manually initiated, and then Dynamics 365 Finance automatically marks the selected invoices for settlement when the payments are created.</span></span> <span data-ttu-id="b1b32-137">Si los pagos se crean manualmente, puede usar la página **Liquidar transacciones** para seleccionar las facturas para la liquidación.</span><span class="sxs-lookup"><span data-stu-id="b1b32-137">If payments are created manually, you can use the **Settle transactions** page to select invoices for settlement.</span></span> <span data-ttu-id="b1b32-138">Puede seleccionar manualmente las facturas o puede usar la opción **Marcar por prioridad** para tener facturas automáticamente marcadas para liquidación.</span><span class="sxs-lookup"><span data-stu-id="b1b32-138">You can manually select the invoices, or you can use the **Mark by priority** option to have invoices automatically marked for settlement.</span></span> <span data-ttu-id="b1b32-139">La opción **Marcar por prioridad** solo está disponible para los clientes.</span><span class="sxs-lookup"><span data-stu-id="b1b32-139">The **Mark by priority** option is available only for Accounts receivable.</span></span> <span data-ttu-id="b1b32-140">Para habilitar esta opción, use la página **Prioridad liquidación** de parámetros de clientes.</span><span class="sxs-lookup"><span data-stu-id="b1b32-140">To enable this option, use the **Settlement priority** page in Accounts receivable parameters.</span></span> <span data-ttu-id="b1b32-141">Si un administrativo de pagos especifica un pago, pero no lo liquida antes de registrarlo, el pago se podrá liquidar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b1b32-141">If a payment clerk enters a payment but doesn’t settle that payment before it is posted, the payment can be automatically settled.</span></span> <span data-ttu-id="b1b32-142">Puede habilitar la liquidación automática en los parámetros de proveedores y de clientes.</span><span class="sxs-lookup"><span data-stu-id="b1b32-142">You can enable automatic settlement in Accounts receivable parameters and Accounts payable parameters.</span></span> <span data-ttu-id="b1b32-143">La liquidación automática liquida las transacciones dentro de la misma entidad jurídica y no se liquidan entre varias entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="b1b32-143">Automatic settlement settles transactions within the same legal entity and does not settle across multiple legal entities.</span></span> <span data-ttu-id="b1b32-144">Cuando usa la liquidación automática, puede usar el orden predefinido de liquidación o bien definir su propio orden de prioridad de liquidación en los parámetros de clientes.</span><span class="sxs-lookup"><span data-stu-id="b1b32-144">When you use automatic settlement, you can use the predefined settlement order, or you can define your own settlement priority order in Accounts receivable parameters.</span></span> <span data-ttu-id="b1b32-145">Esta funcionalidad solo está disponible para los clientes.</span><span class="sxs-lookup"><span data-stu-id="b1b32-145">This functionality is available only for Accounts receivable.</span></span>

## <a name="results-of-settlement"></a><span data-ttu-id="b1b32-146">Resultados de liquidación</span><span class="sxs-lookup"><span data-stu-id="b1b32-146">Results of settlement</span></span>
<span data-ttu-id="b1b32-147">A medida que se liquidan las transacciones, el saldo pendiente de cada transacción se actualizan o se reduce como corresponda.</span><span class="sxs-lookup"><span data-stu-id="b1b32-147">As transactions are settled, the outstanding balance of each transaction is increased or decreased as appropriate.</span></span> <span data-ttu-id="b1b32-148">En un escenario típico en el que se liquidan una factura y un pago, el estado y el saldo de cada transacción se actualiza según las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b1b32-148">In a typical scenario, where an invoice and payment are settled, the status and balance of each transaction is updated according to the following rules:</span></span>

-   <span data-ttu-id="b1b32-149">Si el importe del pago es superior al importe de la factura, el saldo de la factura se reduce a 0,00 y la factura se cerrará.</span><span class="sxs-lookup"><span data-stu-id="b1b32-149">If the payment amount is more than the invoice amount, the invoice balance is reduced to 0.00, and the invoice is closed.</span></span> <span data-ttu-id="b1b32-150">El pago permanece abierto y el saldo es el importe en el que el pago excede el importe de la factura.</span><span class="sxs-lookup"><span data-stu-id="b1b32-150">The payment remains open, and the balance is the amount by which the payment exceeds the invoice amount.</span></span>
-   <span data-ttu-id="b1b32-151">Si el importe del pago es inferior al importe de la factura, el saldo del pago se reduce a 0,00 y el pago se cerrará.</span><span class="sxs-lookup"><span data-stu-id="b1b32-151">If the payment amount is less than the invoice amount, the payment balance is reduced to 0.00, and the payment is closed.</span></span> <span data-ttu-id="b1b32-152">La factura permanece abierta y el saldo es el importe en el que se pagó una parte de la factura.</span><span class="sxs-lookup"><span data-stu-id="b1b32-152">The invoice remains open, and the balance is the amount by which the payment underpaid the invoice.</span></span>
-   <span data-ttu-id="b1b32-153">Si el importe del pago es igual al importe de la factura, el pago y la factura se cerrarán y el saldo de ambos es 0,00.</span><span class="sxs-lookup"><span data-stu-id="b1b32-153">If the payment amount equals the invoice amount, both the payment and the invoice are closed, and the balance of both is 0.00.</span></span>

<span data-ttu-id="b1b32-154">Si un [pago es inferior al importe de la factura](../accounts-payable/vendor-payments-partial-amount.md) debido a un descuento por pronto pago, una cancelación o un pago insuficiente, la factura y el pago pueden seguir cerrados, en función de la configuración de la liquidación en los parámetros de proveedores y de clientes.</span><span class="sxs-lookup"><span data-stu-id="b1b32-154">If a [payment is less than the invoice amount](../accounts-payable/vendor-payments-partial-amount.md) because of a cash discount, write-off, or underpayment, the invoice and payment might still be closed, depending on the setup of settlement in Accounts payable parameters and Accounts receivable parameters.</span></span> <span data-ttu-id="b1b32-155">La liquidación también puede generar transacciones.</span><span class="sxs-lookup"><span data-stu-id="b1b32-155">Settlement can also generate transactions.</span></span> <span data-ttu-id="b1b32-156">Por ejemplo, la liquidación de una factura y un pago puede producir un descuento por pronto pago, una pérdida o un beneficio realizados, ajustes de los impuestos, cancelaciones o diferencias de decimales.</span><span class="sxs-lookup"><span data-stu-id="b1b32-156">For example, the settlement of an invoice and payment might produce a cash discount, realized gain or loss, sales tax adjustments, write-offs, or penny differences.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="b1b32-157">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b1b32-157">Additional resources</span></span>
- [<span data-ttu-id="b1b32-158">Resto de liquidación</span><span class="sxs-lookup"><span data-stu-id="b1b32-158">Settle remainder</span></span>](settle-remainder.md)
