---
title: Pagos de impuestos y reglas de redondeo
description: "En este artículo se explica cómo funciona la configuración de la regla de redondeo en las autoridades fiscales y el redondeo del saldo de impuestos durante el trabajo Liquidar y registrar impuestos."
author: twheeloc
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 51d514f2f98db0be2af1d8d76f717977dabf272f
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="sales-tax-payments-and-rounding-rules"></a><span data-ttu-id="c02d7-103">Pagos de impuestos y reglas de redondeo</span><span class="sxs-lookup"><span data-stu-id="c02d7-103">Sales tax payments and rounding rules</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="c02d7-104">En este artículo se explica cómo funciona la configuración de la regla de redondeo en las autoridades fiscales y el redondeo del saldo de impuestos durante el trabajo Liquidar y registrar impuestos.</span><span class="sxs-lookup"><span data-stu-id="c02d7-104">This article explains how the rounding rule setup on the Sales tax authorities works and rounding the sales tax balance during the Settle and post sales tax job.</span></span>

<span data-ttu-id="c02d7-105">Periódicamente, los impuestos se deben notificar y pagar a las autoridades fiscales.</span><span class="sxs-lookup"><span data-stu-id="c02d7-105">Periodically, sales tax needs to be reported and paid to tax authorities.</span></span> <span data-ttu-id="c02d7-106">Esto puede hacerse ejecutando el proceso de liquidación y registro de impuestos en la página Impuestos.</span><span class="sxs-lookup"><span data-stu-id="c02d7-106">This can be done by running the settle and post sales tax process in the Sales tax page.</span></span> <span data-ttu-id="c02d7-107">Los impuestos para un período se liquidarán contra las cuentas de impuestos y el saldo de impuestos se registrará en la cuenta de liquidación Impuestos.</span><span class="sxs-lookup"><span data-stu-id="c02d7-107">Sales tax for a period will be settled against the sales tax accounts and the sales tax balance will be posted to the Sales tax settlement account.</span></span> <span data-ttu-id="c02d7-108">El saldo de impuestos, que se registra en la cuenta de liquidación Impuestos, se podrá redondear según exijan las autoridades fiscales configurando una regla de redondeo en la página Impuestos.</span><span class="sxs-lookup"><span data-stu-id="c02d7-108">The sales tax balance, which is posted on the Sales tax settlement account, can be rounded as required by tax authorities by setting up a rounding rule on the Sales tax page.</span></span> 

<span data-ttu-id="c02d7-109">La diferencia de redondeo se registra en la cuenta de redondeo de impuestos seleccionada en el campo Cuentas para transacciones automáticas de la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="c02d7-109">The rounding difference is posted to the Sales tax rounding account that is selected in the Accounts for automatic transactions field in the General ledger.</span></span>

<span data-ttu-id="c02d7-110">El ejemplo siguiente muestra cómo funciona la regla de redondeo en la autoridad fiscal.</span><span class="sxs-lookup"><span data-stu-id="c02d7-110">The below example illustrates how the rounding rule on Sales tax authority works.</span></span>

### <a name="example"></a><span data-ttu-id="c02d7-111">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c02d7-111">Example:</span></span>

<span data-ttu-id="c02d7-112">El total de impuestos para un período muestra un saldo de crédito de -98.765,43.</span><span class="sxs-lookup"><span data-stu-id="c02d7-112">The total sales tax for a period shows a credit balance of -98,765.43.</span></span> <span data-ttu-id="c02d7-113">La entidad jurídica acumuló más impuestos de venta de los que canceló.</span><span class="sxs-lookup"><span data-stu-id="c02d7-113">The legal entity collected more sales taxes than it paid.</span></span> <span data-ttu-id="c02d7-114">Por lo tanto, la entidad debe dinero a la autoridad tributaria.</span><span class="sxs-lookup"><span data-stu-id="c02d7-114">Therefore, the legal entity owes money to the tax authority.</span></span> 

<span data-ttu-id="c02d7-115">La entidad jurídica desea utilizar un método de redondeo que redondee el saldo al 1,00 más cercano.</span><span class="sxs-lookup"><span data-stu-id="c02d7-115">The legal entity wants to use a rounding method that rounds the balance to the nearest 1.00.</span></span> <span data-ttu-id="c02d7-116">El usuario a cargo de contabilizar las cuentas de los impuestos sobre las ventas debe seguir los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="c02d7-116">The user who is responsible for sales tax accounting performs the following steps.</span></span>

1.  <span data-ttu-id="c02d7-117">Haga clic en Impuestos &gt; Impuestos indirectos &gt; Impuestos &gt; Autoridades fiscales.</span><span class="sxs-lookup"><span data-stu-id="c02d7-117">Click Tax &gt; Indirect taxes &gt; Sales tax &gt; Sales tax authorities</span></span>
2.  <span data-ttu-id="c02d7-118">En la ficha desplegable General, seleccione Normal en el campo Forma de redondear.</span><span class="sxs-lookup"><span data-stu-id="c02d7-118">On the General FastTab, select Normal in the Rounding form field.</span></span>
3.  <span data-ttu-id="c02d7-119">En el campo Redondear, escriba 1,00.</span><span class="sxs-lookup"><span data-stu-id="c02d7-119">In the Round-off field, enter 1.00.</span></span>
4.  <span data-ttu-id="c02d7-120">A la hora de pagar impuestos a la autoridad fiscal, abra la página Liquidar y registrar impuestos.</span><span class="sxs-lookup"><span data-stu-id="c02d7-120">When it is time to pay the sales taxes to the tax authority, open the Settle and post sales tax page.</span></span> <span data-ttu-id="c02d7-121">(Haga clic en Impuestos &gt; Declaraciones &gt; Impuestos &gt; Liquidar y registrar impuestos).</span><span class="sxs-lookup"><span data-stu-id="c02d7-121">(Click Tax &gt; Declarations &gt; Sales tax &gt; Settle and post sales tax.)</span></span>
5.  <span data-ttu-id="c02d7-122">En la cuenta de liquidación de impuestos, el monto de deuda tributaria 98.765,43 se redondea a 98.765.</span><span class="sxs-lookup"><span data-stu-id="c02d7-122">On the sales tax settlement account, the tax liability amount of 98,765.43 is rounded to 98,765.</span></span>

<span data-ttu-id="c02d7-123">La siguiente tabla muestra cómo el monto 98.765,43 se redondea mediante cada uno de los métodos de redondeo disponibles en el campo Forma de redondeo en la página Autoridades fiscales.</span><span class="sxs-lookup"><span data-stu-id="c02d7-123">The following table shows how an amount of 98,765.43 is rounded by using each rounding method that is available in the Rounding form field in the Sales tax authorities page.</span></span>

| <span data-ttu-id="c02d7-124">Opción Forma de redondeo</span><span class="sxs-lookup"><span data-stu-id="c02d7-124">Rounding form option</span></span>                | <span data-ttu-id="c02d7-125">Valor de redondeo = 0,01</span><span class="sxs-lookup"><span data-stu-id="c02d7-125">Round-off value = 0.01</span></span> | <span data-ttu-id="c02d7-126">Valor de redondeo = 0,10</span><span class="sxs-lookup"><span data-stu-id="c02d7-126">Round-off value = 0.10</span></span> | <span data-ttu-id="c02d7-127">Valor de redondeo = 1,00</span><span class="sxs-lookup"><span data-stu-id="c02d7-127">Round-off value = 1.00</span></span> | <span data-ttu-id="c02d7-128">Valor de redondeo = 100,00</span><span class="sxs-lookup"><span data-stu-id="c02d7-128">Round-off value = 100.00</span></span> |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|
| <span data-ttu-id="c02d7-129">Normal</span><span class="sxs-lookup"><span data-stu-id="c02d7-129">Normal</span></span>                              | <span data-ttu-id="c02d7-130">98.765,43</span><span class="sxs-lookup"><span data-stu-id="c02d7-130">98,765.43</span></span>              | <span data-ttu-id="c02d7-131">98,765,40</span><span class="sxs-lookup"><span data-stu-id="c02d7-131">98,765.40</span></span>              | <span data-ttu-id="c02d7-132">98.765,00</span><span class="sxs-lookup"><span data-stu-id="c02d7-132">98,765.00</span></span>              | <span data-ttu-id="c02d7-133">98.800,00</span><span class="sxs-lookup"><span data-stu-id="c02d7-133">98,800.00</span></span>                |
| <span data-ttu-id="c02d7-134">Hacia abajo</span><span class="sxs-lookup"><span data-stu-id="c02d7-134">Downward</span></span>                            | <span data-ttu-id="c02d7-135">98.765,43</span><span class="sxs-lookup"><span data-stu-id="c02d7-135">98,765.43</span></span>              | <span data-ttu-id="c02d7-136">98.765,40</span><span class="sxs-lookup"><span data-stu-id="c02d7-136">98,765.40</span></span>              | <span data-ttu-id="c02d7-137">98.765,00</span><span class="sxs-lookup"><span data-stu-id="c02d7-137">98,765.00</span></span>              | <span data-ttu-id="c02d7-138">98.700,00</span><span class="sxs-lookup"><span data-stu-id="c02d7-138">98,700.00</span></span>                |
| <span data-ttu-id="c02d7-139">Redondeo por arriba</span><span class="sxs-lookup"><span data-stu-id="c02d7-139">Rounding-up</span></span>                         | <span data-ttu-id="c02d7-140">98.765,43</span><span class="sxs-lookup"><span data-stu-id="c02d7-140">98,765.43</span></span>              | <span data-ttu-id="c02d7-141">98.765,50</span><span class="sxs-lookup"><span data-stu-id="c02d7-141">98,765.50</span></span>              | <span data-ttu-id="c02d7-142">98.766,00</span><span class="sxs-lookup"><span data-stu-id="c02d7-142">98,766.00</span></span>              | <span data-ttu-id="c02d7-143">98,800.00</span><span class="sxs-lookup"><span data-stu-id="c02d7-143">98,800.00</span></span>                |
| <span data-ttu-id="c02d7-144">Ventaja propia, para un saldo de crédito</span><span class="sxs-lookup"><span data-stu-id="c02d7-144">Own advantage, for a credit balance</span></span> | <span data-ttu-id="c02d7-145">98.765,43</span><span class="sxs-lookup"><span data-stu-id="c02d7-145">98,765.43</span></span>              | <span data-ttu-id="c02d7-146">98.765,40</span><span class="sxs-lookup"><span data-stu-id="c02d7-146">98,765.40</span></span>              | <span data-ttu-id="c02d7-147">98.765,00</span><span class="sxs-lookup"><span data-stu-id="c02d7-147">98,765.00</span></span>              | <span data-ttu-id="c02d7-148">98.700,00</span><span class="sxs-lookup"><span data-stu-id="c02d7-148">98,700.00</span></span>                |
| <span data-ttu-id="c02d7-149">Ventaja propia, para un saldo de débito</span><span class="sxs-lookup"><span data-stu-id="c02d7-149">Own advantage, for a debit balance</span></span>  | <span data-ttu-id="c02d7-150">98.765,43</span><span class="sxs-lookup"><span data-stu-id="c02d7-150">98,765.43</span></span>              | <span data-ttu-id="c02d7-151">98.765,50</span><span class="sxs-lookup"><span data-stu-id="c02d7-151">98,765.50</span></span>              | <span data-ttu-id="c02d7-152">98.766,00</span><span class="sxs-lookup"><span data-stu-id="c02d7-152">98,766.00</span></span>              | <span data-ttu-id="c02d7-153">98.800,00</span><span class="sxs-lookup"><span data-stu-id="c02d7-153">98,800.00</span></span>                |

> [!NOTE]                                                                                  
> <span data-ttu-id="c02d7-154">Si selecciona Ventaja propia, el redondeo siempre se realizará a favor de la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="c02d7-154">If you select Own advantage, the rounding is always to the advantage of the legal entity.</span></span> 

<span data-ttu-id="c02d7-155">Para obtener más información, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="c02d7-155">For more information, see the following topics:</span></span>
- [<span data-ttu-id="c02d7-156">Visión general de impuestos</span><span class="sxs-lookup"><span data-stu-id="c02d7-156">Sales tax overview</span></span>](indirect-taxes-overview.md)
- [<span data-ttu-id="c02d7-157">Crear un pago de impuestos</span><span class="sxs-lookup"><span data-stu-id="c02d7-157">Create a sales tax payment</span></span>](tasks/create-sales-tax-payment.md)
- [<span data-ttu-id="c02d7-158">Crear transacciones de impuestos en documentos</span><span class="sxs-lookup"><span data-stu-id="c02d7-158">Create sales transactions on documents</span></span>](tasks/create-sales-tax-transactions-documents.md)
- [<span data-ttu-id="c02d7-159">Ver transacciones de impuestos registradas</span><span class="sxs-lookup"><span data-stu-id="c02d7-159">View posted sales tax transactions</span></span>](tasks/view-posted-sales-tax-transactions.md)



