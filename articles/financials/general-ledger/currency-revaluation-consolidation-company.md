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
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: hminzner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b4c91399e96c54f7cf9968a15e3fff90c3a71ca6
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="currency-revaluation-in-a-consolidation-company"></a><span data-ttu-id="05620-103">Revalorización de divisa en una empresa de consolidación</span><span class="sxs-lookup"><span data-stu-id="05620-103">Currency revaluation in a consolidation company</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="05620-104">Cuando se consolidan datos desde una divisa de contabilidad a otra, debe seguir ejecutando la revalorización de divisa si hay un cambio en tipos de cambio, para revalorizar los saldos de cuenta correctamente.</span><span class="sxs-lookup"><span data-stu-id="05620-104">When you consolidate data from one accounting currency to another, you must still run currency revaluation if there is a change in exchange rates, so that your account balances  are correctly revalued.</span></span> <span data-ttu-id="05620-105">Al consolidar por primera vez los datos, use la pestaña **Traducción de divisas** para seleccionar los tipos de cambio iniciales para su traducción durante el proceso de consolidación.</span><span class="sxs-lookup"><span data-stu-id="05620-105">When you originally consolidate the data, use the **Currency translation** tab to select the initial exchange rates to for translation during the consolidation process.</span></span> <span data-ttu-id="05620-106">Después de que se introduzcan un nuevo tipo de cambio (por ejemplo, el mes próximo), debe revalorizar los saldos de cuenta.</span><span class="sxs-lookup"><span data-stu-id="05620-106">After a new exchange rate is entered (for example, in the next month), you must revalue the account balances.</span></span> <span data-ttu-id="05620-107">Después se actualizarán los beneficios no realizados o las pérdidas, en función de la fecha y los nuevos tipo de cambio.</span><span class="sxs-lookup"><span data-stu-id="05620-107">The unrealized gains or losses are then updated accordingly, based on the new exchange rate and date.</span></span> <span data-ttu-id="05620-108">En el ejemplo siguiente se muestran los asientos contables que se crean durante el proceso.</span><span class="sxs-lookup"><span data-stu-id="05620-108">The following example illustrates the accounting entries that are created during the process.</span></span>

## <a name="company-setup"></a><span data-ttu-id="05620-109">Configuración de empresa</span><span class="sxs-lookup"><span data-stu-id="05620-109">Company setup</span></span>
-   <span data-ttu-id="05620-110">**Empresa de origen u operadora (USMF):** se usan dólares americanos (USD) como la divisa de contabilidad y de notificación.</span><span class="sxs-lookup"><span data-stu-id="05620-110">**Source/operating company (USMF)** – US dollars (USD) are used as the accounting and reporting currency.</span></span>
-   <span data-ttu-id="05620-111">**Empresa consolidada (CON):** se usan euros (EUR) como la divisa de contabilidad y de notificación.</span><span class="sxs-lookup"><span data-stu-id="05620-111">**Consolidated company (CON)** – Euros (EUR) are used as the accounting and reporting currency.</span></span>
    -   <span data-ttu-id="05620-112">**Beneficio realizado**: cuenta contable 801500</span><span class="sxs-lookup"><span data-stu-id="05620-112">**Realized gain **– Ledger account 801500</span></span>
    -   <span data-ttu-id="05620-113">**Pérdida realizada:** cuenta contable 801600</span><span class="sxs-lookup"><span data-stu-id="05620-113">**Realized loss** – Ledger account 801600</span></span>
    -   <span data-ttu-id="05620-114">**Beneficio no realizado:** cuenta contable 801600</span><span class="sxs-lookup"><span data-stu-id="05620-114">**Unrealized gain** – Ledger account 801600</span></span>
    -   <span data-ttu-id="05620-115">**Pérdida no realizada:** cuenta contable 801400</span><span class="sxs-lookup"><span data-stu-id="05620-115">**Unrealized loss** – Ledger account 801400</span></span>

## <a name="original-transactions"></a><span data-ttu-id="05620-116">Transacciones originales</span><span class="sxs-lookup"><span data-stu-id="05620-116">Original transactions</span></span>
### <a name="cash-receipt-transactions-in-usmf"></a><span data-ttu-id="05620-117">Transacciones de recibo de cobro en USMF</span><span class="sxs-lookup"><span data-stu-id="05620-117">Cash receipt transactions in USMF</span></span>

| <span data-ttu-id="05620-118">Fecha</span><span class="sxs-lookup"><span data-stu-id="05620-118">Date</span></span>       | <span data-ttu-id="05620-119">Cuenta contable</span><span class="sxs-lookup"><span data-stu-id="05620-119">Ledger account</span></span>               | <span data-ttu-id="05620-120">Divisa</span><span class="sxs-lookup"><span data-stu-id="05620-120">Currency</span></span> | <span data-ttu-id="05620-121">Importe</span><span class="sxs-lookup"><span data-stu-id="05620-121">Amount</span></span> |
|------------|------------------------------|----------|--------|
| <span data-ttu-id="05620-122">11/10/2015</span><span class="sxs-lookup"><span data-stu-id="05620-122">10/11/2015</span></span> | <span data-ttu-id="05620-123">110110: efectivo</span><span class="sxs-lookup"><span data-stu-id="05620-123">110110 – Cash</span></span>                | <span data-ttu-id="05620-124">USD</span><span class="sxs-lookup"><span data-stu-id="05620-124">USD</span></span>      | <span data-ttu-id="05620-125">500</span><span class="sxs-lookup"><span data-stu-id="05620-125">500</span></span>    |
| <span data-ttu-id="05620-126">11/10/2015</span><span class="sxs-lookup"><span data-stu-id="05620-126">10/11/2015</span></span> | <span data-ttu-id="05620-127">130100: clientes</span><span class="sxs-lookup"><span data-stu-id="05620-127">130100 – Accounts Receivable</span></span> | <span data-ttu-id="05620-128">USD</span><span class="sxs-lookup"><span data-stu-id="05620-128">USD</span></span>      | <span data-ttu-id="05620-129">-500</span><span class="sxs-lookup"><span data-stu-id="05620-129">-500</span></span>   |

## <a name="exchange-rates"></a><span data-ttu-id="05620-130">Tipos de cambio</span><span class="sxs-lookup"><span data-stu-id="05620-130">Exchange rates</span></span>
| <span data-ttu-id="05620-131">Desde divisa</span><span class="sxs-lookup"><span data-stu-id="05620-131">From currency</span></span> | <span data-ttu-id="05620-132">A divisa</span><span class="sxs-lookup"><span data-stu-id="05620-132">To currency</span></span> | <span data-ttu-id="05620-133">Fecha inicial</span><span class="sxs-lookup"><span data-stu-id="05620-133">Start date</span></span> | <span data-ttu-id="05620-134">Tipo de cambio</span><span class="sxs-lookup"><span data-stu-id="05620-134">Exchange rate</span></span> |
|---------------|-------------|------------|---------------|
| <span data-ttu-id="05620-135">EUR</span><span class="sxs-lookup"><span data-stu-id="05620-135">EUR</span></span>           | <span data-ttu-id="05620-136">USD</span><span class="sxs-lookup"><span data-stu-id="05620-136">USD</span></span>         | <span data-ttu-id="05620-137">1/10/2015</span><span class="sxs-lookup"><span data-stu-id="05620-137">10/1/2015</span></span>  | <span data-ttu-id="05620-138">200</span><span class="sxs-lookup"><span data-stu-id="05620-138">200</span></span>           |
| <span data-ttu-id="05620-139">EUR</span><span class="sxs-lookup"><span data-stu-id="05620-139">EUR</span></span>           | <span data-ttu-id="05620-140">USD</span><span class="sxs-lookup"><span data-stu-id="05620-140">USD</span></span>         | <span data-ttu-id="05620-141">1/11/2015</span><span class="sxs-lookup"><span data-stu-id="05620-141">11/1/2015</span></span>  | <span data-ttu-id="05620-142">150</span><span class="sxs-lookup"><span data-stu-id="05620-142">150</span></span>           |
| <span data-ttu-id="05620-143">EUR</span><span class="sxs-lookup"><span data-stu-id="05620-143">EUR</span></span>           | <span data-ttu-id="05620-144">USD</span><span class="sxs-lookup"><span data-stu-id="05620-144">USD</span></span>         | <span data-ttu-id="05620-145">1/12/2012</span><span class="sxs-lookup"><span data-stu-id="05620-145">12/1/2012</span></span>  | <span data-ttu-id="05620-146">100</span><span class="sxs-lookup"><span data-stu-id="05620-146">100</span></span>           |

## <a name="perform-the-consolidation-for-october-2015"></a><span data-ttu-id="05620-147">Realizar la consolidación para octubre de 2015</span><span class="sxs-lookup"><span data-stu-id="05620-147">Perform the consolidation for October 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="05620-148">Saldos en la empresa de consolidación</span><span class="sxs-lookup"><span data-stu-id="05620-148">Balances in the consolidation company</span></span>

| <span data-ttu-id="05620-149">Cuenta contable</span><span class="sxs-lookup"><span data-stu-id="05620-149">Ledger account</span></span> | <span data-ttu-id="05620-150">Divisa</span><span class="sxs-lookup"><span data-stu-id="05620-150">Currency</span></span> | <span data-ttu-id="05620-151">Importe</span><span class="sxs-lookup"><span data-stu-id="05620-151">Amount</span></span> | <span data-ttu-id="05620-152">Cálculo</span><span class="sxs-lookup"><span data-stu-id="05620-152">Calculation</span></span>    |
|----------------|----------|--------|----------------|
| <span data-ttu-id="05620-153">110110</span><span class="sxs-lookup"><span data-stu-id="05620-153">110110</span></span>         | <span data-ttu-id="05620-154">EUR</span><span class="sxs-lookup"><span data-stu-id="05620-154">EUR</span></span>      | <span data-ttu-id="05620-155">250</span><span class="sxs-lookup"><span data-stu-id="05620-155">250</span></span>    | <span data-ttu-id="05620-156">500 USD × 50%</span><span class="sxs-lookup"><span data-stu-id="05620-156">500 USD × 50%</span></span>  |
| <span data-ttu-id="05620-157">130100</span><span class="sxs-lookup"><span data-stu-id="05620-157">130100</span></span>         | <span data-ttu-id="05620-158">EUR</span><span class="sxs-lookup"><span data-stu-id="05620-158">EUR</span></span>      | <span data-ttu-id="05620-159">-250</span><span class="sxs-lookup"><span data-stu-id="05620-159">-250</span></span>   | <span data-ttu-id="05620-160">-500 USD × 50%</span><span class="sxs-lookup"><span data-stu-id="05620-160">-500 USD × 50%</span></span> |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a><span data-ttu-id="05620-161">Realizar la revalorización de divisa para las cuentas a partir del 1 de octubre de 2015, hasta el 30 de noviembre de 2015</span><span class="sxs-lookup"><span data-stu-id="05620-161">Perform currency revaluation for the accounts from October 1, 2015, through November 30, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="05620-162">Saldos en la empresa de consolidación</span><span class="sxs-lookup"><span data-stu-id="05620-162">Balances in the consolidation company</span></span>

| <span data-ttu-id="05620-163">Cuenta contable</span><span class="sxs-lookup"><span data-stu-id="05620-163">Ledger account</span></span> | <span data-ttu-id="05620-164">Divisa</span><span class="sxs-lookup"><span data-stu-id="05620-164">Currency</span></span> | <span data-ttu-id="05620-165">Importe</span><span class="sxs-lookup"><span data-stu-id="05620-165">Amount</span></span>  | <span data-ttu-id="05620-166">Cálculo</span><span class="sxs-lookup"><span data-stu-id="05620-166">Calculation</span></span>                        |
|----------------|----------|---------|------------------------------------|
| <span data-ttu-id="05620-167">110110</span><span class="sxs-lookup"><span data-stu-id="05620-167">110110</span></span>         | <span data-ttu-id="05620-168">EUR</span><span class="sxs-lookup"><span data-stu-id="05620-168">EUR</span></span>      | <span data-ttu-id="05620-169">333.33</span><span class="sxs-lookup"><span data-stu-id="05620-169">333.33</span></span>  | <span data-ttu-id="05620-170">Importe original de 500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="05620-170">Original amount of 500 × 66.6667%</span></span>  |
| <span data-ttu-id="05620-171">130100</span><span class="sxs-lookup"><span data-stu-id="05620-171">130100</span></span>         | <span data-ttu-id="05620-172">EUR</span><span class="sxs-lookup"><span data-stu-id="05620-172">EUR</span></span>      | <span data-ttu-id="05620-173">-333.33</span><span class="sxs-lookup"><span data-stu-id="05620-173">-333.33</span></span> | <span data-ttu-id="05620-174">Importe original de -500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="05620-174">Original amount of -500 × 66.6667%</span></span> |
| <span data-ttu-id="05620-175">801400</span><span class="sxs-lookup"><span data-stu-id="05620-175">801400</span></span>         | <span data-ttu-id="05620-176">EUR</span><span class="sxs-lookup"><span data-stu-id="05620-176">EUR</span></span>      | <span data-ttu-id="05620-177">83,33</span><span class="sxs-lookup"><span data-stu-id="05620-177">83.33</span></span>   | <span data-ttu-id="05620-178">333,33 – 250</span><span class="sxs-lookup"><span data-stu-id="05620-178">333.33 – 250</span></span>                       |
| <span data-ttu-id="05620-179">801600</span><span class="sxs-lookup"><span data-stu-id="05620-179">801600</span></span>         | <span data-ttu-id="05620-180">EUR</span><span class="sxs-lookup"><span data-stu-id="05620-180">EUR</span></span>      | <span data-ttu-id="05620-181">-83.33</span><span class="sxs-lookup"><span data-stu-id="05620-181">-83.33</span></span>  | <span data-ttu-id="05620-182">-333,33 – (-250)</span><span class="sxs-lookup"><span data-stu-id="05620-182">-333.33 – (-250)</span></span>                   |

<span data-ttu-id="05620-183">Verá transacciones adicionales para los importes de divisa de notificación.</span><span class="sxs-lookup"><span data-stu-id="05620-183">You will see additional transactions for the reporting currency amounts.</span></span>

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a><span data-ttu-id="05620-184">Realizar la revalorización de divisa para las cuentas a partir del 1 de octubre de 2015, hasta el 31 de diciembre de 2015</span><span class="sxs-lookup"><span data-stu-id="05620-184">Perform currency revaluation for the accounts from October 1, 2015, through December 31, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="05620-185">Saldos en la empresa de consolidación</span><span class="sxs-lookup"><span data-stu-id="05620-185">Balances in the consolidation company</span></span>

| <span data-ttu-id="05620-186">Cuenta contable</span><span class="sxs-lookup"><span data-stu-id="05620-186">Ledger account</span></span> | <span data-ttu-id="05620-187">Divisa</span><span class="sxs-lookup"><span data-stu-id="05620-187">Currency</span></span> | <span data-ttu-id="05620-188">Importe</span><span class="sxs-lookup"><span data-stu-id="05620-188">Amount</span></span>  | <span data-ttu-id="05620-189">Cálculo</span><span class="sxs-lookup"><span data-stu-id="05620-189">Calculation</span></span>                                          |
|----------------|----------|---------|------------------------------------------------------|
| <span data-ttu-id="05620-190">110110</span><span class="sxs-lookup"><span data-stu-id="05620-190">110110</span></span>         | <span data-ttu-id="05620-191">EUR</span><span class="sxs-lookup"><span data-stu-id="05620-191">EUR</span></span>      | <span data-ttu-id="05620-192">500,00</span><span class="sxs-lookup"><span data-stu-id="05620-192">500.00</span></span>  | <span data-ttu-id="05620-193">Importe original de 500 × 1</span><span class="sxs-lookup"><span data-stu-id="05620-193">Original amount of 500 × 1</span></span>                           |
| <span data-ttu-id="05620-194">130100</span><span class="sxs-lookup"><span data-stu-id="05620-194">130100</span></span>         | <span data-ttu-id="05620-195">EUR</span><span class="sxs-lookup"><span data-stu-id="05620-195">EUR</span></span>      | <span data-ttu-id="05620-196">-500,00</span><span class="sxs-lookup"><span data-stu-id="05620-196">-500.00</span></span> | <span data-ttu-id="05620-197">Importe original de -500 × 1</span><span class="sxs-lookup"><span data-stu-id="05620-197">Original amount of -500 × 1</span></span>                          |
| <span data-ttu-id="05620-198">801400</span><span class="sxs-lookup"><span data-stu-id="05620-198">801400</span></span>         | <span data-ttu-id="05620-199">EUR</span><span class="sxs-lookup"><span data-stu-id="05620-199">EUR</span></span>      | <span data-ttu-id="05620-200">250</span><span class="sxs-lookup"><span data-stu-id="05620-200">250</span></span>     | <span data-ttu-id="05620-201">500 – 333,33 = 166,67 166,67 + 83,33 = 250</span><span class="sxs-lookup"><span data-stu-id="05620-201">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span></span>           |
| <span data-ttu-id="05620-202">801600</span><span class="sxs-lookup"><span data-stu-id="05620-202">801600</span></span>         | <span data-ttu-id="05620-203">EUR</span><span class="sxs-lookup"><span data-stu-id="05620-203">EUR</span></span>      | <span data-ttu-id="05620-204">-250</span><span class="sxs-lookup"><span data-stu-id="05620-204">-250</span></span>    | <span data-ttu-id="05620-205">-500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250</span><span class="sxs-lookup"><span data-stu-id="05620-205">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span></span> |






