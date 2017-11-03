---
title: Descuentos por pronto pago
description: "Los descuentos por pronto pago se configuran y se comparten para Proveedores y Clientes.  El descuento por pronto pago disponible se puede definir en la factura de cliente o la factura de proveedor, y se tomará si la factura se paga dentro de la fecha de descuento por pronto pago."
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CashDisc
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3741
ms.assetid: c25f9d85-2702-46aa-8e61-0b4886e069b3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 9960af8c4961a42e7e829077da40bcbbf3bc71c2
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="cash-discounts"></a><span data-ttu-id="cdba8-104">Descuentos por pronto pago</span><span class="sxs-lookup"><span data-stu-id="cdba8-104">Cash discounts</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="cdba8-105">Los descuentos por pronto pago se configuran y se comparten para Proveedores y Clientes.</span><span class="sxs-lookup"><span data-stu-id="cdba8-105">Cash discounts are setup and shared for Accounts payable and Accounts receivable.</span></span>  <span data-ttu-id="cdba8-106">El descuento por pronto pago disponible se puede definir en la factura de cliente o la factura de proveedor, y se tomará si la factura se paga dentro de la fecha de descuento por pronto pago.</span><span class="sxs-lookup"><span data-stu-id="cdba8-106">The cash discount available can be defined on the customer invoice or vendor invoice, and will be taken if the invoice is paid within the cash discount date.</span></span> 

<a name="cash-discounts"></a><span data-ttu-id="cdba8-107">Descuentos por pronto pago</span><span class="sxs-lookup"><span data-stu-id="cdba8-107">Cash discounts</span></span>
--------------

<span data-ttu-id="cdba8-108">Los descuentos por pronto pago para clientes o proveedores se pueden crear en la página Descuentos por pronto pago.</span><span class="sxs-lookup"><span data-stu-id="cdba8-108">Cash discounts for both customers or vendors can be created in the Cash discounts page.</span></span> <span data-ttu-id="cdba8-109">También puede definir, mediante el campo Código de descuento siguiente, una serie de descuentos por pronto pago que se sucederán uno tras otro cuando venzan las fechas de descuento por pronto pago anteriores.</span><span class="sxs-lookup"><span data-stu-id="cdba8-109">You can also define, by using the Next discount code field, a series of cash discounts that succeed each other as previous cash discount dates expire.</span></span> <span data-ttu-id="cdba8-110">Para obtener más información, consulte el apartado "Ejemplo: serie de descuentos por pronto pago" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="cdba8-110">For more information, see “Example: Series of cash discounts” later in this topic.</span></span> <span data-ttu-id="cdba8-111">Si la factura, la transacción de crédito (ya sea un pago o una nota de abono) o ambas se introducen en una divisa diferente a la divisa de contabilidad de la entidad jurídica, el descuento por pronto pago se calcula mediante el tipo de cambio basado en la fecha del pago o la nota de abono.</span><span class="sxs-lookup"><span data-stu-id="cdba8-111">If the invoice, credit transaction (either a payment or a credit note), or both are entered in a currency other than the accounting currency of the legal entity, the cash discount is calculated using the exchange rate based on the date of the payment or credit note.</span></span> <span data-ttu-id="cdba8-112">Si la factura y el documento de crédito se especifican en entidades jurídicas diferentes y las divisas de contabilidad de dichas entidades jurídicas son diferentes, el tipo de cambio se toma de la entidad jurídica de la factura, a partir de la fecha del documento de crédito.</span><span class="sxs-lookup"><span data-stu-id="cdba8-112">If the invoice and credit document are entered in different legal entities, and if the accounting currencies for the legal entities differ, the exchange rate is taken from the legal entity of the invoice, as of the date of the credit document.</span></span> <span data-ttu-id="cdba8-113">Para obtener más información, consulte el apartado "Ejemplo: tipos de cambio para los descuentos por pronto pago" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="cdba8-113">For more information, see “Example: Exchange rates for cash discounts” later in this topic.</span></span>
<span data-ttu-id="cdba8-114">Orden predeterminado de la cuenta principal del descuento por pronto pago</span><span class="sxs-lookup"><span data-stu-id="cdba8-114">Defaulting order of cash discount main account</span></span>
----------------------------------------------

<span data-ttu-id="cdba8-115">Si una factura se liquida a tiempo para obtener un descuento por pronto pago, el descuento por pronto pago se registra automáticamente en una cuenta principal de descuento para la siguiente prioridad predeterminada:</span><span class="sxs-lookup"><span data-stu-id="cdba8-115">If an invoice is settled in time to obtain a cash discount, the cash discount is automatically posted to a cash discount main account according to the following defaulting priority:</span></span>
1.  <span data-ttu-id="cdba8-116">La cuenta principal especificada en el campo Cuenta alternativa de descuento por pronto pago en la página Liquidar transacciones abiertas del cliente o la página Liquidar transacciones abiertas del proveedor.</span><span class="sxs-lookup"><span data-stu-id="cdba8-116">The main account specified in the Alternative cash discount account field on the customer Settle open transactions page or the vendor Settle open transactions page.</span></span>
2.  <span data-ttu-id="cdba8-117">La cuenta principal que se especifica en el campo Descuento por pronto pago del cliente o el campo Descuento por pronto pago del proveedor del grupo de registro contable que se asigna al grupo de impuestos de la factura.</span><span class="sxs-lookup"><span data-stu-id="cdba8-117">The main account specified in the Customer cash discount field or the Vendor cash discount field of the ledger posting group that is assigned to the sales tax code of the invoice.</span></span> <span data-ttu-id="cdba8-118">Configure grupos de registro de contabilidad en la página Grupos de registro y asígnelos a códigos de impuestos en la página Códigos de impuestos.</span><span class="sxs-lookup"><span data-stu-id="cdba8-118">Set up ledger posting groups on the Ledger posting groups page and assign them to sales tax codes in the Sales tax codes page.</span></span>
3.  <span data-ttu-id="cdba8-119">La cuenta de registro principal de la página Descuentos por pronto pago o la página Cuenta principal para descuentos de cliente para el código de descuento por pronto pago que se encuentra en la factura liquidada.</span><span class="sxs-lookup"><span data-stu-id="cdba8-119">The main posting account on the Cash discounts page in either the Main account for customer discounts field or the Main account for vendor discounts field for the cash discount code that is on the settled invoice.</span></span>
4.  <span data-ttu-id="cdba8-120">La cuenta principal para descuentos por pronto pago, como se define en la página de Cuentas para transacciones automáticas.</span><span class="sxs-lookup"><span data-stu-id="cdba8-120">The main account for cash discounts, as defined in the Accounts for automatic transactions page.</span></span>

## <a name="example-series-of-cash-discounts"></a><span data-ttu-id="cdba8-121"> Ejemplo: serie de descuentos por pronto pago</span><span class="sxs-lookup"><span data-stu-id="cdba8-121">Example: Series of cash discounts</span></span>
<span data-ttu-id="cdba8-122">Configure tres códigos de descuento por pronto pago de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="cdba8-122">Set up three cash discount codes as follows:</span></span>
-   <span data-ttu-id="cdba8-123">Código 5D10%: un descuento por pronto pago del 10% cuando el importe se paga en un período de 5 días.</span><span class="sxs-lookup"><span data-stu-id="cdba8-123">Code 5D10% – A cash discount of 10% when the amount is paid within 5 days.</span></span>
-   <span data-ttu-id="cdba8-124">Código 10D5%: un descuento por pronto pago del 5% cuando el importe se paga en un período de 10 días.</span><span class="sxs-lookup"><span data-stu-id="cdba8-124">Code 10D5% – A cash discount of 5% when the amount is paid within 10 days.</span></span>
-   <span data-ttu-id="cdba8-125">Código 14D2%: un descuento por pronto pago del 2% cuando el importe se paga en un período de 14 días.</span><span class="sxs-lookup"><span data-stu-id="cdba8-125">Code 14D2% – A cash discount of 2% when the amount is paid within 14 days.</span></span>

<span data-ttu-id="cdba8-126">En el campo Código de descuento siguiente:</span><span class="sxs-lookup"><span data-stu-id="cdba8-126">In the Next discount code field:</span></span>
-   <span data-ttu-id="cdba8-127">Para el código 5D10%, seleccione 10D5%.</span><span class="sxs-lookup"><span data-stu-id="cdba8-127">For the 5D10% code, select 10D5%.</span></span>
-   <span data-ttu-id="cdba8-128">Para el código 10D5%, seleccione 14D2%.</span><span class="sxs-lookup"><span data-stu-id="cdba8-128">For the 10D5% code, select 14D2%.</span></span>
-   <span data-ttu-id="cdba8-129">Para el código 14D2%, deje en blanco el campo Código de descuento siguiente.</span><span class="sxs-lookup"><span data-stu-id="cdba8-129">For the 14D2% code, leave the Next discount code field blank.</span></span>

<span data-ttu-id="cdba8-130">Los tres descuentos por pronto pago se suceden uno tras otro a medida que la fecha de pago sobrepasa la fecha de descuento por pronto pago en la factura.</span><span class="sxs-lookup"><span data-stu-id="cdba8-130">The three cash discounts succeed each other as the payment date exceeds the previous cash discount date on the invoice.</span></span> <span data-ttu-id="cdba8-131">Solo se concede un descuento por pronto pago cuando se paga la factura, en función de cuál es la fecha de descuento por pronto pago satisfecha en la secuencia de descuentos por pronto pago.</span><span class="sxs-lookup"><span data-stu-id="cdba8-131">Only one cash discount is granted when the invoice is paid, based on which cash discount date is meet in the sequence of cash discounts.</span></span>

## <a name="example-exchange-rates-for-cash-discounts"></a><span data-ttu-id="cdba8-132"> Ejemplo: tipos de cambio para los descuentos por pronto pago</span><span class="sxs-lookup"><span data-stu-id="cdba8-132">Example: Exchange rates for cash discounts</span></span>
<span data-ttu-id="cdba8-133">La divisa de contabilidad de su entidad jurídica es el euro y se especifican los siguientes tipos de cambio para el dólar estadounidense:</span><span class="sxs-lookup"><span data-stu-id="cdba8-133">Your legal entity’s accounting currency is EUR and the following exchange rates are specified for USD:</span></span>
-   <span data-ttu-id="cdba8-134">1 de febrero = 110</span><span class="sxs-lookup"><span data-stu-id="cdba8-134">February 1 = 110</span></span>
-   <span data-ttu-id="cdba8-135">1 de marzo = 80</span><span class="sxs-lookup"><span data-stu-id="cdba8-135">March 1 = 80</span></span>

<span data-ttu-id="cdba8-136">El 15 de febrero se registra una factura de 1000 dólares con términos de descuento por pronto pago de 20D2%.</span><span class="sxs-lookup"><span data-stu-id="cdba8-136">An invoice for 1000 USD with cash discount terms of 20D2% is posted on February 15.</span></span> <span data-ttu-id="cdba8-137">El importe en la divisa de contabilidad de la factura es de 1100 euros.</span><span class="sxs-lookup"><span data-stu-id="cdba8-137">The accounting currency amount of the invoice is 1100 EUR.</span></span> <span data-ttu-id="cdba8-138">Se liquida un pago de 980 dólares con la factura el día 1 de marzo.</span><span class="sxs-lookup"><span data-stu-id="cdba8-138">A payment for 980 USD is settled with the invoice on March 1.</span></span> <span data-ttu-id="cdba8-139">El importe del descuento por pronto pago es de 20 dólares.</span><span class="sxs-lookup"><span data-stu-id="cdba8-139">The cash discount amount is 20 USD.</span></span> <span data-ttu-id="cdba8-140">El importe en la divisa de contabilidad del pago es de 784 euros.</span><span class="sxs-lookup"><span data-stu-id="cdba8-140">The accounting currency amount of the payment is 784 EUR.</span></span> <span data-ttu-id="cdba8-141">El importe en la divisa de contabilidad del descuento por pronto pago se calcula mediante el tipo de cambio del 1 de marzo: 20 \* 80 / 100 = 16 EUR.</span><span class="sxs-lookup"><span data-stu-id="cdba8-141">The accounting currency amount of the cash discount is calculated by using the exchange rate as of March 1: 20 \* 80 / 100 = 16 EUR.</span></span>
| <span data-ttu-id="cdba8-142">**Nota**</span><span class="sxs-lookup"><span data-stu-id="cdba8-142">**Note**</span></span>                                                                                                                                                                                                                             |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="cdba8-143">Si está seleccionada la opción Calcular descuento por pronto pago para pagos parciales en la página Parámetros de clientes o Parámetros de proveedores, se usa el tipo de cambio que esté en vigor en la fecha de cada pago parcial.</span><span class="sxs-lookup"><span data-stu-id="cdba8-143">If the Calculate cash discounts for partial payments option is selected in the Accounts receivable parameters or Accounts payable parameters pages, the exchange rate that is in effect on the date of each partial payment is used.</span></span> |

 
=

 




