---
title: Utilizar más que el descuento calculado para un pago de proveedor
description: Este artículo le guía por un escenario en el que se toma un descuento por pronto pago para un importe superior al descuento que estaba originalmente disponible en la factura. Este escenario podría surgir si una organización llega a un acuerdo con el proveedor para pagar un importe menor en la factura.
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 14281
ms.assetid: 7f0a4197-95dd-4969-ade9-154815cf659e
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 62f2088ff04a0ef5ffe6ffe47b85f47e6957264d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810255"
---
# <a name="take-more-than-the-calculated-discount-for-a-vendor-payment"></a><span data-ttu-id="8542e-104">Utilizar más que el descuento calculado para un pago de proveedor</span><span class="sxs-lookup"><span data-stu-id="8542e-104">Take more than the calculated discount for a vendor payment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8542e-105">Este artículo le guía por un escenario en el que se toma un descuento por pronto pago para un importe superior al descuento que estaba originalmente disponible en la factura.</span><span class="sxs-lookup"><span data-stu-id="8542e-105">This article walks you through a scenario where a cash discount is taken for an amount that is more than the discount that was originally available on the invoice.</span></span> <span data-ttu-id="8542e-106">Este escenario podría surgir si una organización llega a un acuerdo con el proveedor para pagar un importe menor en la factura.</span><span class="sxs-lookup"><span data-stu-id="8542e-106">This scenario might occur if an organization comes to an agreement with the vendor to pay a smaller amount on the invoice.</span></span> 

<span data-ttu-id="8542e-107">El proveedor 3.051 ofrece a Fabrikam un descuento por pronto pago del 4 por ciento si una factura se paga en siete días.</span><span class="sxs-lookup"><span data-stu-id="8542e-107">Vendor 3051 gives Fabrikam a cash discount of 4 percent if an invoice is paid in seven days.</span></span> <span data-ttu-id="8542e-108">El 29 de junio April introduce una factura de 1.000,00.</span><span class="sxs-lookup"><span data-stu-id="8542e-108">On June 29, April enters an invoice for 1,000.00.</span></span> <span data-ttu-id="8542e-109">El proveedor permite a April que aproveche un descuento de 60,00 en lugar del descuento predeterminado de 40,00 que está disponible para la factura.</span><span class="sxs-lookup"><span data-stu-id="8542e-109">The vendor lets April take a discount of 60.00 instead of the default discount of 40.00 that is available for the invoice.</span></span> <span data-ttu-id="8542e-110">April registra un pago único mediante el diario de pagos de proveedores.</span><span class="sxs-lookup"><span data-stu-id="8542e-110">April records a one-off payment by using the Accounts payable payment journal.</span></span> <span data-ttu-id="8542e-111">Especifica el proveedor para el pago y luego abre la página **Liquidar transacciones**.</span><span class="sxs-lookup"><span data-stu-id="8542e-111">She enters the vendor for the payment and then opens the **Settle transactions** page.</span></span> <span data-ttu-id="8542e-112">Marca la factura y cambia el valor del campo **Importe de descuento por pronto pago** a **60,00**.</span><span class="sxs-lookup"><span data-stu-id="8542e-112">She marks the invoice and changes the value in the **Cash discount amount** field to **60.00**.</span></span>

| <span data-ttu-id="8542e-113">Marcar</span><span class="sxs-lookup"><span data-stu-id="8542e-113">Mark</span></span>     | <span data-ttu-id="8542e-114">Utilizar el descuento por pronto pago</span><span class="sxs-lookup"><span data-stu-id="8542e-114">Use cash discount</span></span> | <span data-ttu-id="8542e-115">Comprobante</span><span class="sxs-lookup"><span data-stu-id="8542e-115">Voucher</span></span>   | <span data-ttu-id="8542e-116">Cuenta</span><span class="sxs-lookup"><span data-stu-id="8542e-116">Account</span></span> | <span data-ttu-id="8542e-117">Fecha</span><span class="sxs-lookup"><span data-stu-id="8542e-117">Date</span></span>      | <span data-ttu-id="8542e-118">Fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="8542e-118">Due date</span></span>  | <span data-ttu-id="8542e-119">Factura</span><span class="sxs-lookup"><span data-stu-id="8542e-119">Invoice</span></span> | <span data-ttu-id="8542e-120">Importe en divisa de la transacción</span><span class="sxs-lookup"><span data-stu-id="8542e-120">Amount in transaction currency</span></span> | <span data-ttu-id="8542e-121">Divisa</span><span class="sxs-lookup"><span data-stu-id="8542e-121">Currency</span></span> | <span data-ttu-id="8542e-122">Importe para liquidar</span><span class="sxs-lookup"><span data-stu-id="8542e-122">Amount to settle</span></span> |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| <span data-ttu-id="8542e-123">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="8542e-123">Selected</span></span> | <span data-ttu-id="8542e-124">Normal</span><span class="sxs-lookup"><span data-stu-id="8542e-124">Normal</span></span>            | <span data-ttu-id="8542e-125">Inv-10040</span><span class="sxs-lookup"><span data-stu-id="8542e-125">Inv-10040</span></span> | <span data-ttu-id="8542e-126">3051</span><span class="sxs-lookup"><span data-stu-id="8542e-126">3051</span></span>    | <span data-ttu-id="8542e-127">29/6/2015</span><span class="sxs-lookup"><span data-stu-id="8542e-127">6/29/2015</span></span> | <span data-ttu-id="8542e-128">29/7/2015</span><span class="sxs-lookup"><span data-stu-id="8542e-128">7/29/2015</span></span> | <span data-ttu-id="8542e-129">10040</span><span class="sxs-lookup"><span data-stu-id="8542e-129">10040</span></span>   | <span data-ttu-id="8542e-130">1.000,00</span><span class="sxs-lookup"><span data-stu-id="8542e-130">1,000.00</span></span>                       | <span data-ttu-id="8542e-131">USD</span><span class="sxs-lookup"><span data-stu-id="8542e-131">USD</span></span>      | <span data-ttu-id="8542e-132">940,00</span><span class="sxs-lookup"><span data-stu-id="8542e-132">940.00</span></span>           |

<span data-ttu-id="8542e-133">La información de descuento aparece en la parte inferior de la página **Liquidar transacciones**.</span><span class="sxs-lookup"><span data-stu-id="8542e-133">Discount information appears at the bottom of the **Settle transactions** page.</span></span>

| <span data-ttu-id="8542e-134">Campo</span><span class="sxs-lookup"><span data-stu-id="8542e-134">Field</span></span>                        | <span data-ttu-id="8542e-135">Valor</span><span class="sxs-lookup"><span data-stu-id="8542e-135">Value</span></span>     |
|------------------------------|-----------|
| <span data-ttu-id="8542e-136">Fecha del descuento por pronto pago</span><span class="sxs-lookup"><span data-stu-id="8542e-136">Cash discount date</span></span>           | <span data-ttu-id="8542e-137">12/7/2015</span><span class="sxs-lookup"><span data-stu-id="8542e-137">7/12/2015</span></span> |
| <span data-ttu-id="8542e-138">Importe de descuento por pronto pago</span><span class="sxs-lookup"><span data-stu-id="8542e-138">Cash discount amount</span></span>         | <span data-ttu-id="8542e-139">60.00</span><span class="sxs-lookup"><span data-stu-id="8542e-139">60.00</span></span>     |
| <span data-ttu-id="8542e-140">Utilizar el descuento por pronto pago</span><span class="sxs-lookup"><span data-stu-id="8542e-140">Use cash discount</span></span>            | <span data-ttu-id="8542e-141">Normal</span><span class="sxs-lookup"><span data-stu-id="8542e-141">Normal</span></span>    |
| <span data-ttu-id="8542e-142">Descuento por pronto pago aplicado</span><span class="sxs-lookup"><span data-stu-id="8542e-142">Cash discount taken</span></span>          | <span data-ttu-id="8542e-143">0,00</span><span class="sxs-lookup"><span data-stu-id="8542e-143">0.00</span></span>      |
| <span data-ttu-id="8542e-144">Importe de descuento por pronto pago para aplicar</span><span class="sxs-lookup"><span data-stu-id="8542e-144">Cash discount amount to take</span></span> | <span data-ttu-id="8542e-145">60,00</span><span class="sxs-lookup"><span data-stu-id="8542e-145">60.00</span></span>     |

<span data-ttu-id="8542e-146">April registra el diario de pagos.</span><span class="sxs-lookup"><span data-stu-id="8542e-146">April posts the payment journal.</span></span> <span data-ttu-id="8542e-147">La factura se liquida con un pago de 940,00 y un descuento de 60,00.</span><span class="sxs-lookup"><span data-stu-id="8542e-147">The invoice is fully settled by using a payment of 940.00 and a discount of 60.00.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]