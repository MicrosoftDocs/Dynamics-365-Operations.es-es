---
title: Pagos de impuestos y reglas de redondeo
description: En este artículo se explica cómo funciona la configuración de la regla de redondeo en las autoridades fiscales y el redondeo del saldo de impuestos durante el trabajo Liquidar y registrar impuestos.
author: ShylaThompson
manager: AnnBe
ms.date: 04/20/2020
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
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 998dbd01352d3fa5040187e81b564d14133464db
ms.sourcegitcommit: 49f3011b8a6d8cdd038e153d8cb3cf773be25ae4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4014968"
---
# <a name="sales-tax-payments-and-rounding-rules"></a><span data-ttu-id="54008-103">Pagos de impuestos y reglas de redondeo</span><span class="sxs-lookup"><span data-stu-id="54008-103">Sales tax payments and rounding rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="54008-104">En este artículo se explica cómo funciona la configuración de la regla de redondeo en las autoridades fiscales y el redondeo del saldo de impuestos durante el trabajo Liquidar y registrar impuestos.</span><span class="sxs-lookup"><span data-stu-id="54008-104">This article explains how the rounding rule setup on the Sales tax authorities works and rounding the sales tax balance during the Settle and post sales tax job.</span></span>

<span data-ttu-id="54008-105">Periódicamente, los impuestos se deben notificar y pagar a las autoridades fiscales.</span><span class="sxs-lookup"><span data-stu-id="54008-105">Periodically, sales tax needs to be reported and paid to tax authorities.</span></span> <span data-ttu-id="54008-106">Esto puede hacerse ejecutando el proceso de liquidación y registro de impuestos en la página Impuestos.</span><span class="sxs-lookup"><span data-stu-id="54008-106">This can be done by running the settle and post sales tax process in the Sales tax page.</span></span> <span data-ttu-id="54008-107">Los impuestos para un período se liquidarán contra las cuentas de impuestos y el saldo de impuestos se registrará en la cuenta de liquidación Impuestos.</span><span class="sxs-lookup"><span data-stu-id="54008-107">Sales tax for a period will be settled against the sales tax accounts and the sales tax balance will be posted to the Sales tax settlement account.</span></span> <span data-ttu-id="54008-108">El saldo de impuestos, que se registra en la cuenta de liquidación Impuestos, se podrá redondear según exijan las autoridades fiscales configurando una regla de redondeo en la página Impuestos.</span><span class="sxs-lookup"><span data-stu-id="54008-108">The sales tax balance, which is posted on the Sales tax settlement account, can be rounded as required by tax authorities by setting up a rounding rule on the Sales tax page.</span></span> 

<span data-ttu-id="54008-109">La diferencia de redondeo se registra en la cuenta de redondeo de impuestos seleccionada en el campo Cuentas para transacciones automáticas de la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="54008-109">The rounding difference is posted to the Sales tax rounding account that is selected in the Accounts for automatic transactions field in the General ledger.</span></span>

<span data-ttu-id="54008-110">El ejemplo siguiente muestra cómo funciona la regla de redondeo en la autoridad fiscal.</span><span class="sxs-lookup"><span data-stu-id="54008-110">The below example illustrates how the rounding rule on Sales tax authority works.</span></span>

## <a name="examples"></a><span data-ttu-id="54008-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="54008-111">Examples</span></span>

<span data-ttu-id="54008-112">El total de impuestos para un período muestra un saldo de crédito de -98.765,43.</span><span class="sxs-lookup"><span data-stu-id="54008-112">The total sales tax for a period shows a credit balance of -98,765.43.</span></span> <span data-ttu-id="54008-113">La entidad jurídica acumuló más impuestos de venta de los que canceló.</span><span class="sxs-lookup"><span data-stu-id="54008-113">The legal entity collected more sales taxes than it paid.</span></span> <span data-ttu-id="54008-114">Por lo tanto, la entidad debe dinero a la autoridad tributaria.</span><span class="sxs-lookup"><span data-stu-id="54008-114">Therefore, the legal entity owes money to the tax authority.</span></span> 

<span data-ttu-id="54008-115">La entidad jurídica desea utilizar un método de redondeo que redondee el saldo al 1,00 más cercano.</span><span class="sxs-lookup"><span data-stu-id="54008-115">The legal entity wants to use a rounding method that rounds the balance to the nearest 1.00.</span></span> <span data-ttu-id="54008-116">El usuario a cargo de contabilizar las cuentas de los impuestos sobre las ventas debe seguir los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="54008-116">The user who is responsible for sales tax accounting performs the following steps.</span></span>

1. <span data-ttu-id="54008-117">Haga clic en **Impuestos** > **Impuestos indirectos** > **Impuestos** > **Autoridades fiscales**.</span><span class="sxs-lookup"><span data-stu-id="54008-117">Click **Tax** > **Indirect taxes** > **Sales tax** > **Sales tax authorities**.</span></span>
2. <span data-ttu-id="54008-118">En la ficha desplegable **General** , seleccione **Normal** en el campo **Forma de redondear**.</span><span class="sxs-lookup"><span data-stu-id="54008-118">On the **General** FastTab, in the **Rounding form** field, select **Normal**.</span></span>
3. <span data-ttu-id="54008-119">En el campo **Redondear** , escriba 1,00.</span><span class="sxs-lookup"><span data-stu-id="54008-119">In the **Round-off** field, enter 1.00.</span></span>
4. <span data-ttu-id="54008-120">A la hora de pagar impuestos a la autoridad fiscal, vaya a **Impuesto** > **Declaraciones** > **Impuestos** > **Liquidar y registrar impuestos**.</span><span class="sxs-lookup"><span data-stu-id="54008-120">When it is time to pay the sales taxes to the tax authority, go to **Tax** > **Declarations** > **Sales tax** > **Settle and post sale tax**.</span></span> <span data-ttu-id="54008-121">En la cuenta de liquidación de impuestos, puede ver que el monto de deuda tributaria **98 765,43** se redondea a **98 765**.</span><span class="sxs-lookup"><span data-stu-id="54008-121">On the sales tax settlement account, you can see that the tax liability amount of **98,765.43** is rounded to **98,765**.</span></span>

<span data-ttu-id="54008-122">La siguiente tabla muestra cómo el monto 98 765,43 se redondea mediante cada uno de los métodos de redondeo disponibles en el campo **Forma de redondeo** en la página **Autoridades fiscales**.</span><span class="sxs-lookup"><span data-stu-id="54008-122">The following table shows how an amount of 98,765.43 is rounded by using each rounding method that is available in the **Rounding form** field in the **Sales tax authorities** page.</span></span>

> [!NOTE]                                                                                  
> <span data-ttu-id="54008-123">Si el valor de redondeo se establece como 0,00, entonces:</span><span class="sxs-lookup"><span data-stu-id="54008-123">If the round-off value is set as 0.00, then:</span></span>
>
> - <span data-ttu-id="54008-124">Para el redondeo normal, el comportamiento de redondeo es el mismo que para **Redondeo = 0,01**.</span><span class="sxs-lookup"><span data-stu-id="54008-124">For normal rounding, the rounding behavior is the same as for **Round-off = 0.01**.</span></span>
> - <span data-ttu-id="54008-125">Para **Opciones de forma de redondeo** , **A la baja** , **Al alza** y **Ventaja propia** , el comportamiento es el mismo que para **Redondeo = 1,00**.</span><span class="sxs-lookup"><span data-stu-id="54008-125">For the **Rounding form options** , **Downward** , **Rounding-up** , and **Own advantage** , the behavior is the same as for **Round-off = 1.00**.</span></span>

| <span data-ttu-id="54008-126">Opción Forma de redondeo</span><span class="sxs-lookup"><span data-stu-id="54008-126">Rounding form option</span></span>                | <span data-ttu-id="54008-127">Valor de redondeo = 0,01</span><span class="sxs-lookup"><span data-stu-id="54008-127">Round-off value = 0.01</span></span> | <span data-ttu-id="54008-128">Valor de redondeo = 0,10</span><span class="sxs-lookup"><span data-stu-id="54008-128">Round-off value = 0.10</span></span> | <span data-ttu-id="54008-129">Valor de redondeo = 1,00</span><span class="sxs-lookup"><span data-stu-id="54008-129">Round-off value = 1.00</span></span> | <span data-ttu-id="54008-130">Valor de redondeo = 100,00</span><span class="sxs-lookup"><span data-stu-id="54008-130">Round-off value = 100.00</span></span> | <span data-ttu-id="54008-131">Valor de redondeo = 0,00</span><span class="sxs-lookup"><span data-stu-id="54008-131">Round-off value = 0.00</span></span>   |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|--------------------------|
| <span data-ttu-id="54008-132">Normal</span><span class="sxs-lookup"><span data-stu-id="54008-132">Normal</span></span>                              | <span data-ttu-id="54008-133">98,765.43</span><span class="sxs-lookup"><span data-stu-id="54008-133">98,765.43</span></span>              | <span data-ttu-id="54008-134">98,765.40</span><span class="sxs-lookup"><span data-stu-id="54008-134">98,765.40</span></span>              | <span data-ttu-id="54008-135">98,765.00</span><span class="sxs-lookup"><span data-stu-id="54008-135">98,765.00</span></span>              | <span data-ttu-id="54008-136">98,800.00</span><span class="sxs-lookup"><span data-stu-id="54008-136">98,800.00</span></span>                | <span data-ttu-id="54008-137">98,765.43</span><span class="sxs-lookup"><span data-stu-id="54008-137">98,765.43</span></span>                |
| <span data-ttu-id="54008-138">Hacia abajo</span><span class="sxs-lookup"><span data-stu-id="54008-138">Downward</span></span>                            | <span data-ttu-id="54008-139">98,765.43</span><span class="sxs-lookup"><span data-stu-id="54008-139">98,765.43</span></span>              | <span data-ttu-id="54008-140">98,765.40</span><span class="sxs-lookup"><span data-stu-id="54008-140">98,765.40</span></span>              | <span data-ttu-id="54008-141">98,765.00</span><span class="sxs-lookup"><span data-stu-id="54008-141">98,765.00</span></span>              | <span data-ttu-id="54008-142">98,700.00</span><span class="sxs-lookup"><span data-stu-id="54008-142">98,700.00</span></span>                | <span data-ttu-id="54008-143">98,765.00</span><span class="sxs-lookup"><span data-stu-id="54008-143">98,765.00</span></span>                |
| <span data-ttu-id="54008-144">Redondeo al alza</span><span class="sxs-lookup"><span data-stu-id="54008-144">Rounding-up</span></span>                         | <span data-ttu-id="54008-145">98,765.43</span><span class="sxs-lookup"><span data-stu-id="54008-145">98,765.43</span></span>              | <span data-ttu-id="54008-146">98,765.50</span><span class="sxs-lookup"><span data-stu-id="54008-146">98,765.50</span></span>              | <span data-ttu-id="54008-147">98,766.00</span><span class="sxs-lookup"><span data-stu-id="54008-147">98,766.00</span></span>              | <span data-ttu-id="54008-148">98,800.00</span><span class="sxs-lookup"><span data-stu-id="54008-148">98,800.00</span></span>                | <span data-ttu-id="54008-149">98,766.00</span><span class="sxs-lookup"><span data-stu-id="54008-149">98,766.00</span></span>                |
| <span data-ttu-id="54008-150">Ventaja propia, para un saldo de crédito</span><span class="sxs-lookup"><span data-stu-id="54008-150">Own advantage, for a credit balance</span></span> | <span data-ttu-id="54008-151">98,765.43</span><span class="sxs-lookup"><span data-stu-id="54008-151">98,765.43</span></span>              | <span data-ttu-id="54008-152">98,765.40</span><span class="sxs-lookup"><span data-stu-id="54008-152">98,765.40</span></span>              | <span data-ttu-id="54008-153">98,765.00</span><span class="sxs-lookup"><span data-stu-id="54008-153">98,765.00</span></span>              | <span data-ttu-id="54008-154">98,700.00</span><span class="sxs-lookup"><span data-stu-id="54008-154">98,700.00</span></span>                | <span data-ttu-id="54008-155">98,765.00</span><span class="sxs-lookup"><span data-stu-id="54008-155">98,765.00</span></span>                |
| <span data-ttu-id="54008-156">Ventaja propia, para un saldo de débito</span><span class="sxs-lookup"><span data-stu-id="54008-156">Own advantage, for a debit balance</span></span>  | <span data-ttu-id="54008-157">98,765.43</span><span class="sxs-lookup"><span data-stu-id="54008-157">98,765.43</span></span>              | <span data-ttu-id="54008-158">98,765.50</span><span class="sxs-lookup"><span data-stu-id="54008-158">98,765.50</span></span>              | <span data-ttu-id="54008-159">98,766.00</span><span class="sxs-lookup"><span data-stu-id="54008-159">98,766.00</span></span>              | <span data-ttu-id="54008-160">98,800.00</span><span class="sxs-lookup"><span data-stu-id="54008-160">98,800.00</span></span>                | <span data-ttu-id="54008-161">98,766.00</span><span class="sxs-lookup"><span data-stu-id="54008-161">98,766.00</span></span>                |

### <a name="normal-round-and-round-precision-is-001"></a><span data-ttu-id="54008-162">Redondeo normal y precisión de redondeo de 0,01</span><span class="sxs-lookup"><span data-stu-id="54008-162">Normal round, and round precision is 0.01</span></span>

<table>
  <tr>
    <td><span data-ttu-id="54008-163">Redondeo</span><span class="sxs-lookup"><span data-stu-id="54008-163">Rounding</span></span>
    </td>
    <td><span data-ttu-id="54008-164">Proceso de cálculo</span><span class="sxs-lookup"><span data-stu-id="54008-164">Calculation process</span></span>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="54008-165">round(1,015, 0,01) = 1,02</span><span class="sxs-lookup"><span data-stu-id="54008-165">round(1.015, 0.01) = 1.02</span></span>
    </td>
    <td>
      <ol>
        <li><span data-ttu-id="54008-166">round(1,015 / 0,01, 0) = round(101,5, 0) = 102</span><span class="sxs-lookup"><span data-stu-id="54008-166">round(1.015 / 0.01, 0) = round(101.5, 0) = 102</span></span>
        </li>
        <li><span data-ttu-id="54008-167">102 \* 0,01 = 1,02</span><span class="sxs-lookup"><span data-stu-id="54008-167">102 \* 0.01 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="54008-168">round(1,014, 0,01) = 1,01</span><span class="sxs-lookup"><span data-stu-id="54008-168">round(1.014, 0.01) = 1.01</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="54008-169">round(1,014 / 0,01, 0) = round(101,4, 0) = 101</span><span class="sxs-lookup"><span data-stu-id="54008-169">round(1.014 / 0.01, 0) = round(101.4, 0) = 101</span></span>
        </li>
        <li><span data-ttu-id="54008-170">101 \* 0,01 = 1,01</span><span class="sxs-lookup"><span data-stu-id="54008-170">101 \* 0.01 = 1.01</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="54008-171">round(1,011, 0,02) = 1,02</span><span class="sxs-lookup"><span data-stu-id="54008-171">round(1.011, 0.02) = 1.02</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="54008-172">round(1,011 / 0,02, 0) = round(50,55, 0) = 51</span><span class="sxs-lookup"><span data-stu-id="54008-172">round(1.011 / 0.02, 0) = round(50.55, 0) = 51</span></span>
        </li>
        <li><span data-ttu-id="54008-173">51 \* 0,02 = 1,02</span><span class="sxs-lookup"><span data-stu-id="54008-173">51 \* 0.02 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="54008-174">round(1,009, 0,02) = 1,00</span><span class="sxs-lookup"><span data-stu-id="54008-174">round(1.009, 0.02) = 1.00</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="54008-175">round(1,009 / 0,02, 0) = round(50,45, 0) = 50</span><span class="sxs-lookup"><span data-stu-id="54008-175">round(1.009 / 0.02, 0) = round(50.45, 0) = 50</span></span>
        </li>
        <li><span data-ttu-id="54008-176">50 \* 0,02 = 1,00</span><span class="sxs-lookup"><span data-stu-id="54008-176">50 \* 0.02 = 1.00</span></span>
        </li>
      </ol>
    </td>
  </tr>
</table>

> [!NOTE]                                                                                  
> <span data-ttu-id="54008-177">Si selecciona Ventaja propia, el redondeo siempre se realizará a favor de la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="54008-177">If you select Own advantage, the rounding is always to the advantage of the legal entity.</span></span> 

<span data-ttu-id="54008-178">Para obtener más información, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="54008-178">For more information, see the following topics:</span></span>
- [<span data-ttu-id="54008-179">Visión general de impuestos</span><span class="sxs-lookup"><span data-stu-id="54008-179">Sales tax overview</span></span>](indirect-taxes-overview.md)
- [<span data-ttu-id="54008-180">Crear un pago de impuestos</span><span class="sxs-lookup"><span data-stu-id="54008-180">Create a sales tax payment</span></span>](tasks/create-sales-tax-payment.md)
- [<span data-ttu-id="54008-181">Crear transacciones de impuestos en documentos</span><span class="sxs-lookup"><span data-stu-id="54008-181">Create sales tax transactions on documents</span></span>](tasks/create-sales-tax-transactions-documents.md)
- [<span data-ttu-id="54008-182">Ver transacciones de impuestos registradas</span><span class="sxs-lookup"><span data-stu-id="54008-182">View posted sales tax transactions</span></span>](tasks/view-posted-sales-tax-transactions.md)
- [<span data-ttu-id="54008-183">Función round</span><span class="sxs-lookup"><span data-stu-id="54008-183">round Function</span></span>](https://msdn.microsoft.com/library/aa850656.aspx)


