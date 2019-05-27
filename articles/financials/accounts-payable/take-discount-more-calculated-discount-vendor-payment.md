---
title: Aprovechar un descuento superior al calculado para un pago de proveedor
description: Este artículo le guía por un escenario en el que se toma un descuento por pronto pago para un importe superior al descuento que estaba originalmente disponible en la factura. Este escenario podría surgir si una organización llega a un acuerdo con el proveedor para pagar un importe menor en la factura.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14281
ms.assetid: 7f0a4197-95dd-4969-ade9-154815cf659e
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 730ea9bb23368d24c5a09f98fbf6bbb41d685702
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1508537"
---
# <a name="take-a-discount-that-is-more-than-the-calculated-discount-for-a-vendor-payment"></a><span data-ttu-id="d9d0b-104">Aprovechar un descuento superior al calculado para un pago de proveedor</span><span class="sxs-lookup"><span data-stu-id="d9d0b-104">Take a discount that is more than the calculated discount for a vendor payment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d9d0b-105">Este artículo le guía por un escenario en el que se toma un descuento por pronto pago para un importe superior al descuento que estaba originalmente disponible en la factura.</span><span class="sxs-lookup"><span data-stu-id="d9d0b-105">This article walks you through a scenario where a cash discount is taken for an amount that is more than the discount that was originally available on the invoice.</span></span> <span data-ttu-id="d9d0b-106">Este escenario podría surgir si una organización llega a un acuerdo con el proveedor para pagar un importe menor en la factura.</span><span class="sxs-lookup"><span data-stu-id="d9d0b-106">This scenario might occur if an organization comes to an agreement with the vendor to pay a smaller amount on the invoice.</span></span> 

<span data-ttu-id="d9d0b-107">El proveedor 3.051 ofrece a Fabrikam un descuento por pronto pago del 4 por ciento si una factura se paga en siete días.</span><span class="sxs-lookup"><span data-stu-id="d9d0b-107">Vendor 3051 gives Fabrikam a cash discount of 4 percent if an invoice is paid in seven days.</span></span> <span data-ttu-id="d9d0b-108">El 29 de junio April introduce una factura de 1.000,00.</span><span class="sxs-lookup"><span data-stu-id="d9d0b-108">On June 29, April enters an invoice for 1,000.00.</span></span> <span data-ttu-id="d9d0b-109">El proveedor permite a April que aproveche un descuento de 60,00 en lugar del descuento predeterminado de 40,00 que está disponible para la factura.</span><span class="sxs-lookup"><span data-stu-id="d9d0b-109">The vendor lets April take a discount of 60.00 instead of the default discount of 40.00 that is available for the invoice.</span></span> <span data-ttu-id="d9d0b-110">April registra un pago único mediante el diario de pagos de proveedores.</span><span class="sxs-lookup"><span data-stu-id="d9d0b-110">April records a one-off payment by using the Accounts payable payment journal.</span></span> <span data-ttu-id="d9d0b-111">Especifica el proveedor para el pago y luego abre la página **Liquidar transacciones**.</span><span class="sxs-lookup"><span data-stu-id="d9d0b-111">She enters the vendor for the payment and then opens the **Settle transactions** page.</span></span> <span data-ttu-id="d9d0b-112">Marca la factura y cambia el valor del campo **Importe de descuento por pronto pago** a **60,00**.</span><span class="sxs-lookup"><span data-stu-id="d9d0b-112">She marks the invoice and changes the value in the **Cash discount amount** field to **60.00**.</span></span>

| <span data-ttu-id="d9d0b-113">Marcar</span><span class="sxs-lookup"><span data-stu-id="d9d0b-113">Mark</span></span>     | <span data-ttu-id="d9d0b-114">Utilizar el descuento por pronto pago</span><span class="sxs-lookup"><span data-stu-id="d9d0b-114">Use cash discount</span></span> | <span data-ttu-id="d9d0b-115">Comprobante</span><span class="sxs-lookup"><span data-stu-id="d9d0b-115">Voucher</span></span>   | <span data-ttu-id="d9d0b-116">Cuenta</span><span class="sxs-lookup"><span data-stu-id="d9d0b-116">Account</span></span> | <span data-ttu-id="d9d0b-117">Fecha</span><span class="sxs-lookup"><span data-stu-id="d9d0b-117">Date</span></span>      | <span data-ttu-id="d9d0b-118">Fecha de vencimiento</span><span class="sxs-lookup"><span data-stu-id="d9d0b-118">Due date</span></span>  | <span data-ttu-id="d9d0b-119">Factura</span><span class="sxs-lookup"><span data-stu-id="d9d0b-119">Invoice</span></span> | <span data-ttu-id="d9d0b-120">Importe en divisa de la transacción</span><span class="sxs-lookup"><span data-stu-id="d9d0b-120">Amount in transaction currency</span></span> | <span data-ttu-id="d9d0b-121">Divisa</span><span class="sxs-lookup"><span data-stu-id="d9d0b-121">Currency</span></span> | <span data-ttu-id="d9d0b-122">Importe para liquidar</span><span class="sxs-lookup"><span data-stu-id="d9d0b-122">Amount to settle</span></span> |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| <span data-ttu-id="d9d0b-123">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="d9d0b-123">Selected</span></span> | <span data-ttu-id="d9d0b-124">Normal</span><span class="sxs-lookup"><span data-stu-id="d9d0b-124">Normal</span></span>            | <span data-ttu-id="d9d0b-125">Inv-10040</span><span class="sxs-lookup"><span data-stu-id="d9d0b-125">Inv-10040</span></span> | <span data-ttu-id="d9d0b-126">3051</span><span class="sxs-lookup"><span data-stu-id="d9d0b-126">3051</span></span>    | <span data-ttu-id="d9d0b-127">29/6/2015</span><span class="sxs-lookup"><span data-stu-id="d9d0b-127">6/29/2015</span></span> | <span data-ttu-id="d9d0b-128">29/7/2015</span><span class="sxs-lookup"><span data-stu-id="d9d0b-128">7/29/2015</span></span> | <span data-ttu-id="d9d0b-129">10040</span><span class="sxs-lookup"><span data-stu-id="d9d0b-129">10040</span></span>   | <span data-ttu-id="d9d0b-130">1.000,00</span><span class="sxs-lookup"><span data-stu-id="d9d0b-130">1,000.00</span></span>                       | <span data-ttu-id="d9d0b-131">USD</span><span class="sxs-lookup"><span data-stu-id="d9d0b-131">USD</span></span>      | <span data-ttu-id="d9d0b-132">940,00</span><span class="sxs-lookup"><span data-stu-id="d9d0b-132">940.00</span></span>           |

<span data-ttu-id="d9d0b-133">La información de descuento aparece en la parte inferior de la página **Liquidar transacciones**.</span><span class="sxs-lookup"><span data-stu-id="d9d0b-133">Discount information appears at the bottom of the **Settle transactions** page.</span></span>

|                              |           |
|------------------------------|-----------|
| <span data-ttu-id="d9d0b-134">Fecha del descuento por pronto pago</span><span class="sxs-lookup"><span data-stu-id="d9d0b-134">Cash discount date</span></span>           | <span data-ttu-id="d9d0b-135">12/7/2015</span><span class="sxs-lookup"><span data-stu-id="d9d0b-135">7/12/2015</span></span> |
| <span data-ttu-id="d9d0b-136">Importe de descuento por pronto pago</span><span class="sxs-lookup"><span data-stu-id="d9d0b-136">Cash discount amount</span></span>         | <span data-ttu-id="d9d0b-137">60,00</span><span class="sxs-lookup"><span data-stu-id="d9d0b-137">60.00</span></span>     |
| <span data-ttu-id="d9d0b-138">Utilizar el descuento por pronto pago</span><span class="sxs-lookup"><span data-stu-id="d9d0b-138">Use cash discount</span></span>            | <span data-ttu-id="d9d0b-139">Normal</span><span class="sxs-lookup"><span data-stu-id="d9d0b-139">Normal</span></span>    |
| <span data-ttu-id="d9d0b-140">Descuento por pronto pago aplicado</span><span class="sxs-lookup"><span data-stu-id="d9d0b-140">Cash discount taken</span></span>          | <span data-ttu-id="d9d0b-141">0,00</span><span class="sxs-lookup"><span data-stu-id="d9d0b-141">0.00</span></span>      |
| <span data-ttu-id="d9d0b-142">Importe de descuento por pronto pago para aplicar</span><span class="sxs-lookup"><span data-stu-id="d9d0b-142">Cash discount amount to take</span></span> | <span data-ttu-id="d9d0b-143">60,00</span><span class="sxs-lookup"><span data-stu-id="d9d0b-143">60.00</span></span>     |

<span data-ttu-id="d9d0b-144">April registra el diario de pagos.</span><span class="sxs-lookup"><span data-stu-id="d9d0b-144">April posts the payment journal.</span></span> <span data-ttu-id="d9d0b-145">La factura se liquida con un pago de 940,00 y un descuento de 60,00.</span><span class="sxs-lookup"><span data-stu-id="d9d0b-145">The invoice is fully settled by using a payment of 940.00 and a discount of 60.00.</span></span>



