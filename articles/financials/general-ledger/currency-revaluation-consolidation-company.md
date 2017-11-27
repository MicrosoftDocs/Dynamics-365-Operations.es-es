---
title: "Revalorización de divisa en una empresa de consolidación"
description: "En este tema se describe cómo revalorizar la divisa en una empresa de consolidación."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: hminzner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 27059b0d2a781453a7594bdc430005df6ea5c167
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="currency-revaluation-in-a-consolidation-company"></a><span data-ttu-id="a623a-103">Revalorización de divisa en una empresa de consolidación</span><span class="sxs-lookup"><span data-stu-id="a623a-103">Currency revaluation in a consolidation company</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="a623a-104">Cuando se consolidan datos desde una divisa de contabilidad a otra, debe seguir ejecutando la revalorización de divisa si hay un cambio en tipos de cambio, para revalorizar los saldos de cuenta correctamente.</span><span class="sxs-lookup"><span data-stu-id="a623a-104">When you consolidate data from one accounting currency to another, you must still run currency revaluation if there is a change in exchange rates, so that your account balances  are correctly revalued.</span></span> <span data-ttu-id="a623a-105">Al consolidar por primera vez los datos, use la pestaña **Traducción de divisas** para seleccionar los tipos de cambio iniciales para su traducción durante el proceso de consolidación.</span><span class="sxs-lookup"><span data-stu-id="a623a-105">When you originally consolidate the data, use the **Currency translation** tab to select the initial exchange rates to for translation during the consolidation process.</span></span> <span data-ttu-id="a623a-106">Después de que se introduzcan un nuevo tipo de cambio (por ejemplo, el mes próximo), debe revalorizar los saldos de cuenta.</span><span class="sxs-lookup"><span data-stu-id="a623a-106">After a new exchange rate is entered (for example, in the next month), you must revalue the account balances.</span></span> <span data-ttu-id="a623a-107">Después se actualizarán los beneficios no realizados o las pérdidas, en función de la fecha y los nuevos tipo de cambio.</span><span class="sxs-lookup"><span data-stu-id="a623a-107">The unrealized gains or losses are then updated accordingly, based on the new exchange rate and date.</span></span> <span data-ttu-id="a623a-108">En el ejemplo siguiente se muestran los asientos contables que se crean durante el proceso.</span><span class="sxs-lookup"><span data-stu-id="a623a-108">The following example illustrates the accounting entries that are created during the process.</span></span>

## <a name="company-setup"></a><span data-ttu-id="a623a-109">Configuración de empresa</span><span class="sxs-lookup"><span data-stu-id="a623a-109">Company setup</span></span>
-   <span data-ttu-id="a623a-110">**Empresa de origen u operadora (USMF):** se usan dólares americanos (USD) como la divisa de contabilidad y de notificación.</span><span class="sxs-lookup"><span data-stu-id="a623a-110">**Source/operating company (USMF)** – US dollars (USD) are used as the accounting and reporting currency.</span></span>
-   <span data-ttu-id="a623a-111">**Empresa consolidada (CON):** se usan euros (EUR) como la divisa de contabilidad y de notificación.</span><span class="sxs-lookup"><span data-stu-id="a623a-111">**Consolidated company (CON)** – Euros (EUR) are used as the accounting and reporting currency.</span></span>
    -   <span data-ttu-id="a623a-112">**Beneficio realizado**: cuenta contable 801500</span><span class="sxs-lookup"><span data-stu-id="a623a-112">**Realized gain **– Ledger account 801500</span></span>
    -   <span data-ttu-id="a623a-113">**Pérdida realizada:** cuenta contable 801600</span><span class="sxs-lookup"><span data-stu-id="a623a-113">**Realized loss** – Ledger account 801600</span></span>
    -   <span data-ttu-id="a623a-114">**Beneficio no realizado:** cuenta contable 801600</span><span class="sxs-lookup"><span data-stu-id="a623a-114">**Unrealized gain** – Ledger account 801600</span></span>
    -   <span data-ttu-id="a623a-115">**Pérdida no realizada:** cuenta contable 801400</span><span class="sxs-lookup"><span data-stu-id="a623a-115">**Unrealized loss** – Ledger account 801400</span></span>

## <a name="original-transactions"></a><span data-ttu-id="a623a-116">Transacciones originales</span><span class="sxs-lookup"><span data-stu-id="a623a-116">Original transactions</span></span>
### <a name="cash-receipt-transactions-in-usmf"></a><span data-ttu-id="a623a-117">Transacciones de recibo de cobro en USMF</span><span class="sxs-lookup"><span data-stu-id="a623a-117">Cash receipt transactions in USMF</span></span>

| <span data-ttu-id="a623a-118">Fecha</span><span class="sxs-lookup"><span data-stu-id="a623a-118">Date</span></span>       | <span data-ttu-id="a623a-119">Cuenta contable</span><span class="sxs-lookup"><span data-stu-id="a623a-119">Ledger account</span></span>               | <span data-ttu-id="a623a-120">Divisa</span><span class="sxs-lookup"><span data-stu-id="a623a-120">Currency</span></span> | <span data-ttu-id="a623a-121">Importe</span><span class="sxs-lookup"><span data-stu-id="a623a-121">Amount</span></span> |
|------------|------------------------------|----------|--------|
| <span data-ttu-id="a623a-122">11/10/2015</span><span class="sxs-lookup"><span data-stu-id="a623a-122">10/11/2015</span></span> | <span data-ttu-id="a623a-123">110110: efectivo</span><span class="sxs-lookup"><span data-stu-id="a623a-123">110110 – Cash</span></span>                | <span data-ttu-id="a623a-124">USD</span><span class="sxs-lookup"><span data-stu-id="a623a-124">USD</span></span>      | <span data-ttu-id="a623a-125">500</span><span class="sxs-lookup"><span data-stu-id="a623a-125">500</span></span>    |
| <span data-ttu-id="a623a-126">11/10/2015</span><span class="sxs-lookup"><span data-stu-id="a623a-126">10/11/2015</span></span> | <span data-ttu-id="a623a-127">130100: clientes</span><span class="sxs-lookup"><span data-stu-id="a623a-127">130100 – Accounts Receivable</span></span> | <span data-ttu-id="a623a-128">USD</span><span class="sxs-lookup"><span data-stu-id="a623a-128">USD</span></span>      | <span data-ttu-id="a623a-129">-500</span><span class="sxs-lookup"><span data-stu-id="a623a-129">-500</span></span>   |

## <a name="exchange-rates"></a><span data-ttu-id="a623a-130">Tipos de cambio</span><span class="sxs-lookup"><span data-stu-id="a623a-130">Exchange rates</span></span>
| <span data-ttu-id="a623a-131">Desde divisa</span><span class="sxs-lookup"><span data-stu-id="a623a-131">From currency</span></span> | <span data-ttu-id="a623a-132">A divisa</span><span class="sxs-lookup"><span data-stu-id="a623a-132">To currency</span></span> | <span data-ttu-id="a623a-133">Fecha inicial</span><span class="sxs-lookup"><span data-stu-id="a623a-133">Start date</span></span> | <span data-ttu-id="a623a-134">Tipo de cambio</span><span class="sxs-lookup"><span data-stu-id="a623a-134">Exchange rate</span></span> |
|---------------|-------------|------------|---------------|
| <span data-ttu-id="a623a-135">EUR</span><span class="sxs-lookup"><span data-stu-id="a623a-135">EUR</span></span>           | <span data-ttu-id="a623a-136">USD</span><span class="sxs-lookup"><span data-stu-id="a623a-136">USD</span></span>         | <span data-ttu-id="a623a-137">1/10/2015</span><span class="sxs-lookup"><span data-stu-id="a623a-137">10/1/2015</span></span>  | <span data-ttu-id="a623a-138">200</span><span class="sxs-lookup"><span data-stu-id="a623a-138">200</span></span>           |
| <span data-ttu-id="a623a-139">EUR</span><span class="sxs-lookup"><span data-stu-id="a623a-139">EUR</span></span>           | <span data-ttu-id="a623a-140">USD</span><span class="sxs-lookup"><span data-stu-id="a623a-140">USD</span></span>         | <span data-ttu-id="a623a-141">1/11/2015</span><span class="sxs-lookup"><span data-stu-id="a623a-141">11/1/2015</span></span>  | <span data-ttu-id="a623a-142">150</span><span class="sxs-lookup"><span data-stu-id="a623a-142">150</span></span>           |
| <span data-ttu-id="a623a-143">EUR</span><span class="sxs-lookup"><span data-stu-id="a623a-143">EUR</span></span>           | <span data-ttu-id="a623a-144">USD</span><span class="sxs-lookup"><span data-stu-id="a623a-144">USD</span></span>         | <span data-ttu-id="a623a-145">1/12/2012</span><span class="sxs-lookup"><span data-stu-id="a623a-145">12/1/2012</span></span>  | <span data-ttu-id="a623a-146">100</span><span class="sxs-lookup"><span data-stu-id="a623a-146">100</span></span>           |

## <a name="perform-the-consolidation-for-october-2015"></a><span data-ttu-id="a623a-147">Realizar la consolidación para octubre de 2015</span><span class="sxs-lookup"><span data-stu-id="a623a-147">Perform the consolidation for October 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="a623a-148">Saldos en la empresa de consolidación</span><span class="sxs-lookup"><span data-stu-id="a623a-148">Balances in the consolidation company</span></span>

| <span data-ttu-id="a623a-149">Cuenta contable</span><span class="sxs-lookup"><span data-stu-id="a623a-149">Ledger account</span></span> | <span data-ttu-id="a623a-150">Divisa</span><span class="sxs-lookup"><span data-stu-id="a623a-150">Currency</span></span> | <span data-ttu-id="a623a-151">Importe</span><span class="sxs-lookup"><span data-stu-id="a623a-151">Amount</span></span> | <span data-ttu-id="a623a-152">Cálculo</span><span class="sxs-lookup"><span data-stu-id="a623a-152">Calculation</span></span>    |
|----------------|----------|--------|----------------|
| <span data-ttu-id="a623a-153">110110</span><span class="sxs-lookup"><span data-stu-id="a623a-153">110110</span></span>         | <span data-ttu-id="a623a-154">EUR</span><span class="sxs-lookup"><span data-stu-id="a623a-154">EUR</span></span>      | <span data-ttu-id="a623a-155">250</span><span class="sxs-lookup"><span data-stu-id="a623a-155">250</span></span>    | <span data-ttu-id="a623a-156">500 USD × 50%</span><span class="sxs-lookup"><span data-stu-id="a623a-156">500 USD × 50%</span></span>  |
| <span data-ttu-id="a623a-157">130100</span><span class="sxs-lookup"><span data-stu-id="a623a-157">130100</span></span>         | <span data-ttu-id="a623a-158">EUR</span><span class="sxs-lookup"><span data-stu-id="a623a-158">EUR</span></span>      | <span data-ttu-id="a623a-159">-250</span><span class="sxs-lookup"><span data-stu-id="a623a-159">-250</span></span>   | <span data-ttu-id="a623a-160">-500 USD × 50%</span><span class="sxs-lookup"><span data-stu-id="a623a-160">-500 USD × 50%</span></span> |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a><span data-ttu-id="a623a-161">Realizar la revalorización de divisa para las cuentas a partir del 1 de octubre de 2015, hasta el 30 de noviembre de 2015</span><span class="sxs-lookup"><span data-stu-id="a623a-161">Perform currency revaluation for the accounts from October 1, 2015, through November 30, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="a623a-162">Saldos en la empresa de consolidación</span><span class="sxs-lookup"><span data-stu-id="a623a-162">Balances in the consolidation company</span></span>

| <span data-ttu-id="a623a-163">Cuenta contable</span><span class="sxs-lookup"><span data-stu-id="a623a-163">Ledger account</span></span> | <span data-ttu-id="a623a-164">Divisa</span><span class="sxs-lookup"><span data-stu-id="a623a-164">Currency</span></span> | <span data-ttu-id="a623a-165">Importe</span><span class="sxs-lookup"><span data-stu-id="a623a-165">Amount</span></span>  | <span data-ttu-id="a623a-166">Cálculo</span><span class="sxs-lookup"><span data-stu-id="a623a-166">Calculation</span></span>                        |
|----------------|----------|---------|------------------------------------|
| <span data-ttu-id="a623a-167">110110</span><span class="sxs-lookup"><span data-stu-id="a623a-167">110110</span></span>         | <span data-ttu-id="a623a-168">EUR</span><span class="sxs-lookup"><span data-stu-id="a623a-168">EUR</span></span>      | <span data-ttu-id="a623a-169">333.33</span><span class="sxs-lookup"><span data-stu-id="a623a-169">333.33</span></span>  | <span data-ttu-id="a623a-170">Importe original de 500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="a623a-170">Original amount of 500 × 66.6667%</span></span>  |
| <span data-ttu-id="a623a-171">130100</span><span class="sxs-lookup"><span data-stu-id="a623a-171">130100</span></span>         | <span data-ttu-id="a623a-172">EUR</span><span class="sxs-lookup"><span data-stu-id="a623a-172">EUR</span></span>      | <span data-ttu-id="a623a-173">-333.33</span><span class="sxs-lookup"><span data-stu-id="a623a-173">-333.33</span></span> | <span data-ttu-id="a623a-174">Importe original de -500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="a623a-174">Original amount of -500 × 66.6667%</span></span> |
| <span data-ttu-id="a623a-175">801400</span><span class="sxs-lookup"><span data-stu-id="a623a-175">801400</span></span>         | <span data-ttu-id="a623a-176">EUR</span><span class="sxs-lookup"><span data-stu-id="a623a-176">EUR</span></span>      | <span data-ttu-id="a623a-177">83,33</span><span class="sxs-lookup"><span data-stu-id="a623a-177">83.33</span></span>   | <span data-ttu-id="a623a-178">333,33 – 250</span><span class="sxs-lookup"><span data-stu-id="a623a-178">333.33 – 250</span></span>                       |
| <span data-ttu-id="a623a-179">801600</span><span class="sxs-lookup"><span data-stu-id="a623a-179">801600</span></span>         | <span data-ttu-id="a623a-180">EUR</span><span class="sxs-lookup"><span data-stu-id="a623a-180">EUR</span></span>      | <span data-ttu-id="a623a-181">-83.33</span><span class="sxs-lookup"><span data-stu-id="a623a-181">-83.33</span></span>  | <span data-ttu-id="a623a-182">-333,33 – (-250)</span><span class="sxs-lookup"><span data-stu-id="a623a-182">-333.33 – (-250)</span></span>                   |

<span data-ttu-id="a623a-183">Verá transacciones adicionales para los importes de divisa de notificación.</span><span class="sxs-lookup"><span data-stu-id="a623a-183">You will see additional transactions for the reporting currency amounts.</span></span>

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a><span data-ttu-id="a623a-184">Realizar la revalorización de divisa para las cuentas a partir del 1 de octubre de 2015, hasta el 31 de diciembre de 2015</span><span class="sxs-lookup"><span data-stu-id="a623a-184">Perform currency revaluation for the accounts from October 1, 2015, through December 31, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="a623a-185">Saldos en la empresa de consolidación</span><span class="sxs-lookup"><span data-stu-id="a623a-185">Balances in the consolidation company</span></span>

| <span data-ttu-id="a623a-186">Cuenta contable</span><span class="sxs-lookup"><span data-stu-id="a623a-186">Ledger account</span></span> | <span data-ttu-id="a623a-187">Divisa</span><span class="sxs-lookup"><span data-stu-id="a623a-187">Currency</span></span> | <span data-ttu-id="a623a-188">Importe</span><span class="sxs-lookup"><span data-stu-id="a623a-188">Amount</span></span>  | <span data-ttu-id="a623a-189">Cálculo</span><span class="sxs-lookup"><span data-stu-id="a623a-189">Calculation</span></span>                                          |
|----------------|----------|---------|------------------------------------------------------|
| <span data-ttu-id="a623a-190">110110</span><span class="sxs-lookup"><span data-stu-id="a623a-190">110110</span></span>         | <span data-ttu-id="a623a-191">EUR</span><span class="sxs-lookup"><span data-stu-id="a623a-191">EUR</span></span>      | <span data-ttu-id="a623a-192">500,00</span><span class="sxs-lookup"><span data-stu-id="a623a-192">500.00</span></span>  | <span data-ttu-id="a623a-193">Importe original de 500 × 1</span><span class="sxs-lookup"><span data-stu-id="a623a-193">Original amount of 500 × 1</span></span>                           |
| <span data-ttu-id="a623a-194">130100</span><span class="sxs-lookup"><span data-stu-id="a623a-194">130100</span></span>         | <span data-ttu-id="a623a-195">EUR</span><span class="sxs-lookup"><span data-stu-id="a623a-195">EUR</span></span>      | <span data-ttu-id="a623a-196">-500,00</span><span class="sxs-lookup"><span data-stu-id="a623a-196">-500.00</span></span> | <span data-ttu-id="a623a-197">Importe original de -500 × 1</span><span class="sxs-lookup"><span data-stu-id="a623a-197">Original amount of -500 × 1</span></span>                          |
| <span data-ttu-id="a623a-198">801400</span><span class="sxs-lookup"><span data-stu-id="a623a-198">801400</span></span>         | <span data-ttu-id="a623a-199">EUR</span><span class="sxs-lookup"><span data-stu-id="a623a-199">EUR</span></span>      | <span data-ttu-id="a623a-200">250</span><span class="sxs-lookup"><span data-stu-id="a623a-200">250</span></span>     | <span data-ttu-id="a623a-201">500 – 333,33 = 166,67 166,67 + 83,33 = 250</span><span class="sxs-lookup"><span data-stu-id="a623a-201">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span></span>           |
| <span data-ttu-id="a623a-202">801600</span><span class="sxs-lookup"><span data-stu-id="a623a-202">801600</span></span>         | <span data-ttu-id="a623a-203">EUR</span><span class="sxs-lookup"><span data-stu-id="a623a-203">EUR</span></span>      | <span data-ttu-id="a623a-204">-250</span><span class="sxs-lookup"><span data-stu-id="a623a-204">-250</span></span>    | <span data-ttu-id="a623a-205">-500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250</span><span class="sxs-lookup"><span data-stu-id="a623a-205">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span></span> |






