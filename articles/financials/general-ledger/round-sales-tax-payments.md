---
title: Pagos de impuestos y reglas de redondeo
description: En este artículo se explica cómo funciona la configuración de la regla de redondeo en las autoridades fiscales y el redondeo del saldo de impuestos durante el trabajo Liquidar y registrar impuestos.
author: ShylaThompson
manager: AnnBe
ms.date: 05/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: yijialuan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 168c2fb9edfc994617ef6764a5b9f5949d599882
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835007"
---
# <a name="sales-tax-payments-and-rounding-rules"></a><span data-ttu-id="d89f0-103">Pagos de impuestos y reglas de redondeo</span><span class="sxs-lookup"><span data-stu-id="d89f0-103">Sales tax payments and rounding rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d89f0-104">En este artículo se explica cómo funciona la configuración de la regla de redondeo en las autoridades fiscales y el redondeo del saldo de impuestos durante el trabajo Liquidar y registrar impuestos.</span><span class="sxs-lookup"><span data-stu-id="d89f0-104">This article explains how the rounding rule setup on the Sales tax authorities works and rounding the sales tax balance during the Settle and post sales tax job.</span></span>

<span data-ttu-id="d89f0-105">Periódicamente, los impuestos se deben notificar y pagar a las autoridades fiscales.</span><span class="sxs-lookup"><span data-stu-id="d89f0-105">Periodically, sales tax needs to be reported and paid to tax authorities.</span></span> <span data-ttu-id="d89f0-106">Esto puede hacerse ejecutando el proceso de liquidación y registro de impuestos en la página Impuestos.</span><span class="sxs-lookup"><span data-stu-id="d89f0-106">This can be done by running the settle and post sales tax process in the Sales tax page.</span></span> <span data-ttu-id="d89f0-107">Los impuestos para un período se liquidarán contra las cuentas de impuestos y el saldo de impuestos se registrará en la cuenta de liquidación Impuestos.</span><span class="sxs-lookup"><span data-stu-id="d89f0-107">Sales tax for a period will be settled against the sales tax accounts and the sales tax balance will be posted to the Sales tax settlement account.</span></span> <span data-ttu-id="d89f0-108">El saldo de impuestos, que se registra en la cuenta de liquidación Impuestos, se podrá redondear según exijan las autoridades fiscales configurando una regla de redondeo en la página Impuestos.</span><span class="sxs-lookup"><span data-stu-id="d89f0-108">The sales tax balance, which is posted on the Sales tax settlement account, can be rounded as required by tax authorities by setting up a rounding rule on the Sales tax page.</span></span> 

<span data-ttu-id="d89f0-109">La diferencia de redondeo se registra en la cuenta de redondeo de impuestos seleccionada en el campo Cuentas para transacciones automáticas de la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="d89f0-109">The rounding difference is posted to the Sales tax rounding account that is selected in the Accounts for automatic transactions field in the General ledger.</span></span>

<span data-ttu-id="d89f0-110">El ejemplo siguiente muestra cómo funciona la regla de redondeo en la autoridad fiscal.</span><span class="sxs-lookup"><span data-stu-id="d89f0-110">The below example illustrates how the rounding rule on Sales tax authority works.</span></span>

## <a name="examples"></a><span data-ttu-id="d89f0-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d89f0-111">Examples</span></span>

<span data-ttu-id="d89f0-112">El total de impuestos para un período muestra un saldo de crédito de -98.765,43.</span><span class="sxs-lookup"><span data-stu-id="d89f0-112">The total sales tax for a period shows a credit balance of -98,765.43.</span></span> <span data-ttu-id="d89f0-113">La entidad jurídica acumuló más impuestos de venta de los que canceló.</span><span class="sxs-lookup"><span data-stu-id="d89f0-113">The legal entity collected more sales taxes than it paid.</span></span> <span data-ttu-id="d89f0-114">Por lo tanto, la entidad debe dinero a la autoridad tributaria.</span><span class="sxs-lookup"><span data-stu-id="d89f0-114">Therefore, the legal entity owes money to the tax authority.</span></span> 

<span data-ttu-id="d89f0-115">La entidad jurídica desea utilizar un método de redondeo que redondee el saldo al 1,00 más cercano.</span><span class="sxs-lookup"><span data-stu-id="d89f0-115">The legal entity wants to use a rounding method that rounds the balance to the nearest 1.00.</span></span> <span data-ttu-id="d89f0-116">El usuario a cargo de contabilizar las cuentas de los impuestos sobre las ventas debe seguir los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="d89f0-116">The user who is responsible for sales tax accounting performs the following steps.</span></span>

1.  <span data-ttu-id="d89f0-117">Haga clic en Impuestos &gt; Impuestos indirectos &gt; Impuestos &gt; Autoridades fiscales.</span><span class="sxs-lookup"><span data-stu-id="d89f0-117">Click Tax &gt; Indirect taxes &gt; Sales tax &gt; Sales tax authorities</span></span>
2.  <span data-ttu-id="d89f0-118">En la ficha desplegable General, seleccione Normal en el campo Forma de redondear.</span><span class="sxs-lookup"><span data-stu-id="d89f0-118">On the General FastTab, select Normal in the Rounding form field.</span></span>
3.  <span data-ttu-id="d89f0-119">En el campo Redondear, escriba 1,00.</span><span class="sxs-lookup"><span data-stu-id="d89f0-119">In the Round-off field, enter 1.00.</span></span>
4.  <span data-ttu-id="d89f0-120">A la hora de pagar impuestos a la autoridad fiscal, abra la página Liquidar y registrar impuestos.</span><span class="sxs-lookup"><span data-stu-id="d89f0-120">When it is time to pay the sales taxes to the tax authority, open the Settle and post sales tax page.</span></span> <span data-ttu-id="d89f0-121">(Haga clic en Impuestos &gt; Declaraciones &gt; Impuestos &gt; Liquidar y registrar impuestos).</span><span class="sxs-lookup"><span data-stu-id="d89f0-121">(Click Tax &gt; Declarations &gt; Sales tax &gt; Settle and post sales tax.)</span></span>
5.  <span data-ttu-id="d89f0-122">En la cuenta de liquidación de impuestos, el monto de deuda tributaria 98.765,43 se redondea a 98.765.</span><span class="sxs-lookup"><span data-stu-id="d89f0-122">On the sales tax settlement account, the tax liability amount of 98,765.43 is rounded to 98,765.</span></span>

<span data-ttu-id="d89f0-123">La siguiente tabla muestra cómo el monto 98.765,43 se redondea mediante cada uno de los métodos de redondeo disponibles en el campo Forma de redondeo en la página Autoridades fiscales.</span><span class="sxs-lookup"><span data-stu-id="d89f0-123">The following table shows how an amount of 98,765.43 is rounded by using each rounding method that is available in the Rounding form field in the Sales tax authorities page.</span></span>

| <span data-ttu-id="d89f0-124">Opción Forma de redondeo</span><span class="sxs-lookup"><span data-stu-id="d89f0-124">Rounding form option</span></span>                | <span data-ttu-id="d89f0-125">Valor de redondeo = 0,01</span><span class="sxs-lookup"><span data-stu-id="d89f0-125">Round-off value = 0.01</span></span> | <span data-ttu-id="d89f0-126">Valor de redondeo = 0,10</span><span class="sxs-lookup"><span data-stu-id="d89f0-126">Round-off value = 0.10</span></span> | <span data-ttu-id="d89f0-127">Valor de redondeo = 1,00</span><span class="sxs-lookup"><span data-stu-id="d89f0-127">Round-off value = 1.00</span></span> | <span data-ttu-id="d89f0-128">Valor de redondeo = 100,00</span><span class="sxs-lookup"><span data-stu-id="d89f0-128">Round-off value = 100.00</span></span> |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|
| <span data-ttu-id="d89f0-129">Normal</span><span class="sxs-lookup"><span data-stu-id="d89f0-129">Normal</span></span>                              | <span data-ttu-id="d89f0-130">98.765,43</span><span class="sxs-lookup"><span data-stu-id="d89f0-130">98,765.43</span></span>              | <span data-ttu-id="d89f0-131">98,765,40</span><span class="sxs-lookup"><span data-stu-id="d89f0-131">98,765.40</span></span>              | <span data-ttu-id="d89f0-132">98.765,00</span><span class="sxs-lookup"><span data-stu-id="d89f0-132">98,765.00</span></span>              | <span data-ttu-id="d89f0-133">98.800,00</span><span class="sxs-lookup"><span data-stu-id="d89f0-133">98,800.00</span></span>                |
| <span data-ttu-id="d89f0-134">Hacia abajo</span><span class="sxs-lookup"><span data-stu-id="d89f0-134">Downward</span></span>                            | <span data-ttu-id="d89f0-135">98.765,43</span><span class="sxs-lookup"><span data-stu-id="d89f0-135">98,765.43</span></span>              | <span data-ttu-id="d89f0-136">98.765,40</span><span class="sxs-lookup"><span data-stu-id="d89f0-136">98,765.40</span></span>              | <span data-ttu-id="d89f0-137">98.765,00</span><span class="sxs-lookup"><span data-stu-id="d89f0-137">98,765.00</span></span>              | <span data-ttu-id="d89f0-138">98.700,00</span><span class="sxs-lookup"><span data-stu-id="d89f0-138">98,700.00</span></span>                |
| <span data-ttu-id="d89f0-139">Redondeo por arriba</span><span class="sxs-lookup"><span data-stu-id="d89f0-139">Rounding-up</span></span>                         | <span data-ttu-id="d89f0-140">98.765,43</span><span class="sxs-lookup"><span data-stu-id="d89f0-140">98,765.43</span></span>              | <span data-ttu-id="d89f0-141">98.765,50</span><span class="sxs-lookup"><span data-stu-id="d89f0-141">98,765.50</span></span>              | <span data-ttu-id="d89f0-142">98.766,00</span><span class="sxs-lookup"><span data-stu-id="d89f0-142">98,766.00</span></span>              | <span data-ttu-id="d89f0-143">98,800.00</span><span class="sxs-lookup"><span data-stu-id="d89f0-143">98,800.00</span></span>                |
| <span data-ttu-id="d89f0-144">Ventaja propia, para un saldo de crédito</span><span class="sxs-lookup"><span data-stu-id="d89f0-144">Own advantage, for a credit balance</span></span> | <span data-ttu-id="d89f0-145">98.765,43</span><span class="sxs-lookup"><span data-stu-id="d89f0-145">98,765.43</span></span>              | <span data-ttu-id="d89f0-146">98.765,40</span><span class="sxs-lookup"><span data-stu-id="d89f0-146">98,765.40</span></span>              | <span data-ttu-id="d89f0-147">98.765,00</span><span class="sxs-lookup"><span data-stu-id="d89f0-147">98,765.00</span></span>              | <span data-ttu-id="d89f0-148">98.700,00</span><span class="sxs-lookup"><span data-stu-id="d89f0-148">98,700.00</span></span>                |
| <span data-ttu-id="d89f0-149">Ventaja propia, para un saldo de débito</span><span class="sxs-lookup"><span data-stu-id="d89f0-149">Own advantage, for a debit balance</span></span>  | <span data-ttu-id="d89f0-150">98,765.43</span><span class="sxs-lookup"><span data-stu-id="d89f0-150">98,765.43</span></span>              | <span data-ttu-id="d89f0-151">98,765.50</span><span class="sxs-lookup"><span data-stu-id="d89f0-151">98,765.50</span></span>              | <span data-ttu-id="d89f0-152">98,766.00</span><span class="sxs-lookup"><span data-stu-id="d89f0-152">98,766.00</span></span>              | <span data-ttu-id="d89f0-153">98,800.00</span><span class="sxs-lookup"><span data-stu-id="d89f0-153">98,800.00</span></span>                |


### <a name="no-rounding-at-all-since-the-round-off-is-000"></a><span data-ttu-id="d89f0-154">No se redondea en absoluto, ya que el redondeo es 0,00</span><span class="sxs-lookup"><span data-stu-id="d89f0-154">No rounding at all, since the round-off is 0.00</span></span>

<span data-ttu-id="d89f0-155">round(1,0151, 0,00) = 1,0151 round(1,0149, 0,00) = 1,0149</span><span class="sxs-lookup"><span data-stu-id="d89f0-155">round(1.0151, 0.00) = 1.0151 round(1.0149, 0.00) = 1.0149</span></span>

### <a name="normal-round-and-round-precision-is-001"></a><span data-ttu-id="d89f0-156">Redondeo normal y precisión de redondeo de 0,01</span><span class="sxs-lookup"><span data-stu-id="d89f0-156">Normal round, and round precision is 0.01</span></span>

<table>
  <tr>
    <td><span data-ttu-id="d89f0-157">Redondeo</span><span class="sxs-lookup"><span data-stu-id="d89f0-157">Rounding</span></span>
    </td>
    <td><span data-ttu-id="d89f0-158">Proceso de cálculo</span><span class="sxs-lookup"><span data-stu-id="d89f0-158">Calculation process</span></span>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="d89f0-159">round(1,015, 0,01) = 1,02</span><span class="sxs-lookup"><span data-stu-id="d89f0-159">round(1.015, 0.01) = 1.02</span></span>
    </td>
    <td>
      <ol>
        <li><span data-ttu-id="d89f0-160">round(1,015 / 0,01, 0) = round(101,5, 0) = 102</span><span class="sxs-lookup"><span data-stu-id="d89f0-160">round(1.015 / 0.01, 0) = round(101.5, 0) = 102</span></span>
        </li>
        <li><span data-ttu-id="d89f0-161">102 \* 0,01 = 1,02</span><span class="sxs-lookup"><span data-stu-id="d89f0-161">102 \* 0.01 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="d89f0-162">round(1,014, 0,01) = 1,01</span><span class="sxs-lookup"><span data-stu-id="d89f0-162">round(1.014, 0.01) = 1.01</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="d89f0-163">round(1,014 / 0,01, 0) = round(101,4, 0) = 101</span><span class="sxs-lookup"><span data-stu-id="d89f0-163">round(1.014 / 0.01, 0) = round(101.4, 0) = 101</span></span>
        </li>
        <li><span data-ttu-id="d89f0-164">101 \* 0,01 = 1,01</span><span class="sxs-lookup"><span data-stu-id="d89f0-164">101 \* 0.01 = 1.01</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="d89f0-165">round(1,011, 0,02) = 1,02</span><span class="sxs-lookup"><span data-stu-id="d89f0-165">round(1.011, 0.02) = 1.02</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="d89f0-166">round(1,011 / 0,02, 0) = round(50,55, 0) = 51</span><span class="sxs-lookup"><span data-stu-id="d89f0-166">round(1.011 / 0.02, 0) = round(50.55, 0) = 51</span></span>
        </li>
        <li><span data-ttu-id="d89f0-167">51 \* 0,02 = 1,02</span><span class="sxs-lookup"><span data-stu-id="d89f0-167">51 \* 0.02 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="d89f0-168">round(1,009, 0,02) = 1,00</span><span class="sxs-lookup"><span data-stu-id="d89f0-168">round(1.009, 0.02) = 1.00</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="d89f0-169">round(1,009 / 0,02, 0) = round(50,45, 0) = 50</span><span class="sxs-lookup"><span data-stu-id="d89f0-169">round(1.009 / 0.02, 0) = round(50.45, 0) = 50</span></span>
        </li>
        <li><span data-ttu-id="d89f0-170">50 \* 0,02 = 1,00</span><span class="sxs-lookup"><span data-stu-id="d89f0-170">50 \* 0.02 = 1.00</span></span>
        </li>
      </ol>
    </td>
  </tr>
</table>

> [!NOTE]                                                                                  
> <span data-ttu-id="d89f0-171">Si selecciona Ventaja propia, el redondeo siempre se realizará a favor de la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="d89f0-171">If you select Own advantage, the rounding is always to the advantage of the legal entity.</span></span> 

<span data-ttu-id="d89f0-172">Para obtener más información, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="d89f0-172">For more information, see the following topics:</span></span>
- [<span data-ttu-id="d89f0-173">Visión general de impuestos</span><span class="sxs-lookup"><span data-stu-id="d89f0-173">Sales tax overview</span></span>](indirect-taxes-overview.md)
- [<span data-ttu-id="d89f0-174">Crear un pago de impuestos</span><span class="sxs-lookup"><span data-stu-id="d89f0-174">Create a sales tax payment</span></span>](tasks/create-sales-tax-payment.md)
- [<span data-ttu-id="d89f0-175">Crear transacciones de impuestos en documentos</span><span class="sxs-lookup"><span data-stu-id="d89f0-175">Create sales transactions on documents</span></span>](tasks/create-sales-tax-transactions-documents.md)
- [<span data-ttu-id="d89f0-176">Ver transacciones de impuestos registradas</span><span class="sxs-lookup"><span data-stu-id="d89f0-176">View posted sales tax transactions</span></span>](tasks/view-posted-sales-tax-transactions.md)
- [<span data-ttu-id="d89f0-177">Función round</span><span class="sxs-lookup"><span data-stu-id="d89f0-177">round Function</span></span>](https://msdn.microsoft.com/library/aa850656.aspx)


