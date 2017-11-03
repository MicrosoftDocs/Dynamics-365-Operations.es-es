---
title: Pagos de proveedor para un importe parcial
description: "En ocasiones, puede crear un pago a un proveedor inferior al importe de una factura. Este artículo describe las diferentes opciones para gestionar esta situación. Las opciones disponibles dependen de la configuración y de los requisitos empresariales."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14321
ms.assetid: 9a17075e-5325-4d55-a1e5-1791b8c460a0
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7acf791d9a04c618b9a238e5d16e676849792b65
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="vendor-payments-for-a-partial-amount"></a><span data-ttu-id="1b4f0-105">Pagos de proveedor para un importe parcial</span><span class="sxs-lookup"><span data-stu-id="1b4f0-105">Vendor payments for a partial amount</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="1b4f0-106">En ocasiones, puede crear un pago a un proveedor inferior al importe de una factura.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-106">Sometimes, you might make a payment to a vendor that is less than the amount of an invoice.</span></span> <span data-ttu-id="1b4f0-107">Este artículo describe las diferentes opciones para gestionar esta situación.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-107">This article describes the various options for handling this situation.</span></span> <span data-ttu-id="1b4f0-108">Las opciones disponibles dependen de la configuración y de los requisitos empresariales.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-108">The options that are available to you depend on your business requirements and configuration.</span></span> 

<a name="cash-discount-amounts"></a><span data-ttu-id="1b4f0-109">Importes de descuento por pronto pago</span><span class="sxs-lookup"><span data-stu-id="1b4f0-109">Cash discount amounts</span></span>
---------------------

<span data-ttu-id="1b4f0-110">Un proveedor puede ofrecerle un descuento por pronto pago por pagar una factura antes de la fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-110">A vendor can offer you a cash discount for paying an invoice before the due date.</span></span> <span data-ttu-id="1b4f0-111">Por ejemplo, introduce una factura de 100,00 que especifica un descuento por pronto pago del 2% si se paga en 10 días.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-111">For example, you enter an invoice for 100.00 that specifies a 2-percent cash discount if the invoice is paid within 10 days.</span></span> <span data-ttu-id="1b4f0-112">La fecha de vencimiento es 30 días.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-112">The due date terms are 30 days.</span></span> <span data-ttu-id="1b4f0-113">Si una propuesta de pago usa el descuento por pronto pago como criterio para seleccionar una factura, y si la propuesta se ejecuta en la fecha de descuento por pronto pago o antes, la factura se selecciona para su pago y se crea el pago de 98,00.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-113">If a payment proposal uses the cash discount as a criterion for selecting an invoice, and if the proposal is run on or before the cash discount date, the invoice is selected for payment, and the payment is created for 98.00.</span></span> <span data-ttu-id="1b4f0-114">También se puede obtener un descuento por pronto pago por un único pago que creado manualmente.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-114">A cash discount can also be taken for a one-off payment that was created manually.</span></span>

## <a name="partial-payments-with-cash-discounts"></a><span data-ttu-id="1b4f0-115">Pagos parciales con descuentos por pronto pago</span><span class="sxs-lookup"><span data-stu-id="1b4f0-115">Partial payments with cash discounts</span></span>
<span data-ttu-id="1b4f0-116">Cuando se realiza un pago parcial, se puede planificar realizar otro pago parcial adicional para liquidar por completo la factura.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-116">When you make a partial payment, you might plan to make an additional partial payment to fully settle the invoice.</span></span> <span data-ttu-id="1b4f0-117">Para obtener un descuento por pronto pago para un pago parcial, debe establecer la opción **Calcular descuento por pronto pago para pagos parciales** en **Sí** en la página **Parámetros de proveedores**.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-117">To take a cash discount for a partial payment, you must set the **Calculate cash discounts for partial payments **option to **Yes** on the **Account payable parameters** page.</span></span> 

<span data-ttu-id="1b4f0-118">Por ejemplo, recibe un descuento por pronto pago del 2% si la factura se paga en menos de 10 días tras su emisión.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-118">For example, you receive a 2-percent cash discount if the invoice is paid within 10 days after it's issued.</span></span> <span data-ttu-id="1b4f0-119">Se registra una factura de 100,00.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-119">An invoice is posted for 100.00.</span></span> <span data-ttu-id="1b4f0-120">Si hace un pago de 49,00 en 10 días, debe especificar un débito de 49,00 en el diario de pagos.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-120">If you make a payment of 49.00 within 10 days, you enter a debit of 49.00 in a payment journal.</span></span> <span data-ttu-id="1b4f0-121">Al liquidar el pago parcial en la página **Liquidar transacciones abiertas**, aparece **1,00** en el campo **Importe de descuento por pronto pago para aplicar**.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-121">When you settle the partial payment on the **Settle open transactions** page, **1.00** appears in the **Cash discount amount to take** field.</span></span> 

> [!NOTE] 
> <span data-ttu-id="1b4f0-122">Si especifica un pago parcial y deja el importe de la factura completo en el campo **Importe para liquidar**, el campo **Importe de descuento por pronto pago para aplicar** se vuelve a calcular automáticamente al registrar las transacciones.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-122">If you enter a partial payment and leave the full invoice amount in the **Amount to settle** field, the **Cash discount amount to take** field is automatically recalculated when you post the transactions.</span></span>

## <a name="credit-notes-with-cash-discounts"></a><span data-ttu-id="1b4f0-123">Notas de crédito con descuentos por pronto pago</span><span class="sxs-lookup"><span data-stu-id="1b4f0-123">Credit notes with cash discounts</span></span>
<span data-ttu-id="1b4f0-124">Puede devolver algunos de los artículos de una factura y recibir una nota de abono.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-124">You might return some of the items on an invoice and receive a credit note.</span></span> <span data-ttu-id="1b4f0-125">Si el descuento por pronto pago se ha tomado de la factura original, puede restar el valor del descuento y recibir una devolución por el importe correcto.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-125">If a cash discount was taken on the original invoice, you can subtract the value of the discount and receive a refund for the correct amount.</span></span> <span data-ttu-id="1b4f0-126">Si la opción **Calcular descuentos por pronto pago para notas de abono** está establecida en **Sí** en la página **Parámetros de proveedores**, se calcula automáticamente el descuento para la nota de abono.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-126">If the **Calculate cash discounts for credit notes **option is set to **Yes** on the **Accounts payable parameters** page, the discount is automatically calculated for the credit note.</span></span> 

<span data-ttu-id="1b4f0-127">Por ejemplo, recibe un descuento por pronto pago del 2% si la factura se paga en menos de 10 días tras su emisión.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-127">For example, you receive a 2-percent cash discount if the invoice is paid within 10 days after it's issued.</span></span> <span data-ttu-id="1b4f0-128">Se registra una factura de 100,00.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-128">An invoice for 100.00 is posted.</span></span> <span data-ttu-id="1b4f0-129">Si devuelve los artículos y recibe una nota de abono, puede especificar una nota de abono para el importe total de la factura original, 100,00, junto con el descuento por pronto pago del 2 por ciento que también está definido en la nota de abono.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-129">If you return the goods and receive a credit note, you can enter the credit note for the full amount of the original invoice, 100.00, together with the 2-percent cash discount that is also defined on the credit memo.</span></span>  <span data-ttu-id="1b4f0-130">Al ver la nota de abono en la página **Liquidar transacciones**, aparece **98,00** en el campo **Importe para liquidar** y **-2,00** en **Importe de descuento por pronto pago**.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-130">When you view the credit note on the **Settle transactions** page, **98.00** appears in the **Amount to settle** field, and **-2.00** appears in the **Cash discount amount** field.</span></span> <span data-ttu-id="1b4f0-131">El importe del descuento se registra en una cuenta de descuento por pronto pago.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-131">The discount amount is posted to a cash discount account.</span></span>

## <a name="overpaymentunderpayment-amounts"></a><span data-ttu-id="1b4f0-132">Importes de sobrepago/pago insuficiente</span><span class="sxs-lookup"><span data-stu-id="1b4f0-132">Overpayment/underpayment amounts</span></span>
<span data-ttu-id="1b4f0-133">Puede realizar un pago parcial donde el importe por liquidar sea muy pequeño.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-133">You might make a partial payment where the amount that must still be settled is very small.</span></span> <span data-ttu-id="1b4f0-134">Por ejemplo, la factura de proveedor es por 1.000,00 y paga 999,90.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-134">For example, the vendor invoice is for 1,000.00, and you pay 999.90.</span></span> <span data-ttu-id="1b4f0-135">Si el importe restante es inferior al especificado para sobrepagos o pagos insuficientes en la página **Parámetros de proveedores**, la diferencia se registra automáticamente en una cuenta contable de sobrepago o pago insuficiente.</span><span class="sxs-lookup"><span data-stu-id="1b4f0-135">If the remaining amount is less than the amount that is specified for overpayments or underpayments on the **Accounts payable parameters** page, the difference is automatically posted to an overpayment/underpayment ledger account.</span></span>


<span data-ttu-id="1b4f0-136">Para obtener más información, consulte [Resumen de pagos del proveedor](../cash-bank-management/tasks/vendor-payment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1b4f0-136">For more information, see [Vendor payment overview](../cash-bank-management/tasks/vendor-payment-overview.md).</span></span>

