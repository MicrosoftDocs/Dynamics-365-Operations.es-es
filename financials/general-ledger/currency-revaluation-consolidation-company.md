---
title: "Revalorización de divisa en una empresa de consolidación"
description: 
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 643af8d771685fe8fd652b353d41f2679e0bef8b
ms.contentlocale: es-es
ms.lasthandoff: 07/18/2017

---

# <a name="currency-revaluation-in-a-consolidation-company"></a><span data-ttu-id="44b75-102">Revalorización de divisa en una empresa de consolidación</span><span class="sxs-lookup"><span data-stu-id="44b75-102">Currency revaluation in a consolidation company</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="44b75-103">Cuando se consolidan datos desde una divisa de contabilidad a otra, debe seguir ejecutando la revalorización de divisa si hay un cambio en tipos de cambio, para revalorizar los saldos de cuenta correctamente.</span><span class="sxs-lookup"><span data-stu-id="44b75-103">When you consolidate data from one accounting currency to another, you must still run currency revaluation if there is a change in exchange rates, so that your account balances  are correctly revalued.</span></span> <span data-ttu-id="44b75-104">Al consolidar por primera vez los datos, use la pestaña **Traducción de divisas** para seleccionar los tipos de cambio iniciales para su traducción durante el proceso de consolidación.</span><span class="sxs-lookup"><span data-stu-id="44b75-104">When you originally consolidate the data, use the **Currency translation** tab to select the initial exchange rates to for translation during the consolidation process.</span></span> <span data-ttu-id="44b75-105">Después de que se introduzcan un nuevo tipo de cambio (por ejemplo, el mes próximo), debe revalorizar los saldos de cuenta.</span><span class="sxs-lookup"><span data-stu-id="44b75-105">After a new exchange rate is entered (for example, in the next month), you must revalue the account balances.</span></span> <span data-ttu-id="44b75-106">Después se actualizarán los beneficios no realizados o las pérdidas, en función de la fecha y los nuevos tipo de cambio.</span><span class="sxs-lookup"><span data-stu-id="44b75-106">The unrealized gains or losses are then updated accordingly, based on the new exchange rate and date.</span></span> <span data-ttu-id="44b75-107">En el ejemplo siguiente se muestran los asientos contables que se crean durante el proceso.</span><span class="sxs-lookup"><span data-stu-id="44b75-107">The following example illustrates the accounting entries that are created during the process.</span></span>

## <a name="company-setup"></a><span data-ttu-id="44b75-108">Configuración de empresa</span><span class="sxs-lookup"><span data-stu-id="44b75-108">Company setup</span></span>
-   <span data-ttu-id="44b75-109">**Empresa de origen u operadora (USMF):** se usan dólares americanos (USD) como la divisa de contabilidad y de notificación.</span><span class="sxs-lookup"><span data-stu-id="44b75-109">**Source/operating company (USMF)** – US dollars (USD) are used as the accounting and reporting currency.</span></span>
-   <span data-ttu-id="44b75-110">**Empresa consolidada (CON):** se usan euros (EUR) como la divisa de contabilidad y de notificación.</span><span class="sxs-lookup"><span data-stu-id="44b75-110">**Consolidated company (CON)** – Euros (EUR) are used as the accounting and reporting currency.</span></span>
    -   <span data-ttu-id="44b75-111">**Beneficio realizado**: cuenta contable 801500</span><span class="sxs-lookup"><span data-stu-id="44b75-111">**Realized gain **– Ledger account 801500</span></span>
    -   <span data-ttu-id="44b75-112">**Pérdida realizada:** cuenta contable 801600</span><span class="sxs-lookup"><span data-stu-id="44b75-112">**Realized loss** – Ledger account 801600</span></span>
    -   <span data-ttu-id="44b75-113">**Beneficio no realizado:** cuenta contable 801600</span><span class="sxs-lookup"><span data-stu-id="44b75-113">**Unrealized gain** – Ledger account 801600</span></span>
    -   <span data-ttu-id="44b75-114">**Pérdida no realizada:** cuenta contable 801400</span><span class="sxs-lookup"><span data-stu-id="44b75-114">**Unrealized loss** – Ledger account 801400</span></span>

## <a name="original-transactions"></a><span data-ttu-id="44b75-115">Transacciones originales</span><span class="sxs-lookup"><span data-stu-id="44b75-115">Original transactions</span></span>
### <a name="cash-receipt-transactions-in-usmf"></a><span data-ttu-id="44b75-116">Transacciones de recibo de cobro en USMF</span><span class="sxs-lookup"><span data-stu-id="44b75-116">Cash receipt transactions in USMF</span></span>

| <span data-ttu-id="44b75-117">Fecha</span><span class="sxs-lookup"><span data-stu-id="44b75-117">Date</span></span>       | <span data-ttu-id="44b75-118">Cuenta contable</span><span class="sxs-lookup"><span data-stu-id="44b75-118">Ledger account</span></span>               | <span data-ttu-id="44b75-119">Divisa</span><span class="sxs-lookup"><span data-stu-id="44b75-119">Currency</span></span> | <span data-ttu-id="44b75-120">Importe</span><span class="sxs-lookup"><span data-stu-id="44b75-120">Amount</span></span> |
|------------|------------------------------|----------|--------|
| <span data-ttu-id="44b75-121">11/10/2015</span><span class="sxs-lookup"><span data-stu-id="44b75-121">10/11/2015</span></span> | <span data-ttu-id="44b75-122">110110: efectivo</span><span class="sxs-lookup"><span data-stu-id="44b75-122">110110 – Cash</span></span>                | <span data-ttu-id="44b75-123">USD</span><span class="sxs-lookup"><span data-stu-id="44b75-123">USD</span></span>      | <span data-ttu-id="44b75-124">500</span><span class="sxs-lookup"><span data-stu-id="44b75-124">500</span></span>    |
| <span data-ttu-id="44b75-125">11/10/2015</span><span class="sxs-lookup"><span data-stu-id="44b75-125">10/11/2015</span></span> | <span data-ttu-id="44b75-126">130100: clientes</span><span class="sxs-lookup"><span data-stu-id="44b75-126">130100 – Accounts Receivable</span></span> | <span data-ttu-id="44b75-127">USD</span><span class="sxs-lookup"><span data-stu-id="44b75-127">USD</span></span>      | <span data-ttu-id="44b75-128">-500</span><span class="sxs-lookup"><span data-stu-id="44b75-128">-500</span></span>   |

## <a name="exchange-rates"></a><span data-ttu-id="44b75-129">Tipos de cambio</span><span class="sxs-lookup"><span data-stu-id="44b75-129">Exchange rates</span></span>
| <span data-ttu-id="44b75-130">Desde divisa</span><span class="sxs-lookup"><span data-stu-id="44b75-130">From currency</span></span> | <span data-ttu-id="44b75-131">A divisa</span><span class="sxs-lookup"><span data-stu-id="44b75-131">To currency</span></span> | <span data-ttu-id="44b75-132">Fecha inicial</span><span class="sxs-lookup"><span data-stu-id="44b75-132">Start date</span></span> | <span data-ttu-id="44b75-133">Tipo de cambio</span><span class="sxs-lookup"><span data-stu-id="44b75-133">Exchange rate</span></span> |
|---------------|-------------|------------|---------------|
| <span data-ttu-id="44b75-134">EUR</span><span class="sxs-lookup"><span data-stu-id="44b75-134">EUR</span></span>           | <span data-ttu-id="44b75-135">USD</span><span class="sxs-lookup"><span data-stu-id="44b75-135">USD</span></span>         | <span data-ttu-id="44b75-136">1/10/2015</span><span class="sxs-lookup"><span data-stu-id="44b75-136">10/1/2015</span></span>  | <span data-ttu-id="44b75-137">200</span><span class="sxs-lookup"><span data-stu-id="44b75-137">200</span></span>           |
| <span data-ttu-id="44b75-138">EUR</span><span class="sxs-lookup"><span data-stu-id="44b75-138">EUR</span></span>           | <span data-ttu-id="44b75-139">USD</span><span class="sxs-lookup"><span data-stu-id="44b75-139">USD</span></span>         | <span data-ttu-id="44b75-140">1/11/2015</span><span class="sxs-lookup"><span data-stu-id="44b75-140">11/1/2015</span></span>  | <span data-ttu-id="44b75-141">150</span><span class="sxs-lookup"><span data-stu-id="44b75-141">150</span></span>           |
| <span data-ttu-id="44b75-142">EUR</span><span class="sxs-lookup"><span data-stu-id="44b75-142">EUR</span></span>           | <span data-ttu-id="44b75-143">USD</span><span class="sxs-lookup"><span data-stu-id="44b75-143">USD</span></span>         | <span data-ttu-id="44b75-144">1/12/2012</span><span class="sxs-lookup"><span data-stu-id="44b75-144">12/1/2012</span></span>  | <span data-ttu-id="44b75-145">100</span><span class="sxs-lookup"><span data-stu-id="44b75-145">100</span></span>           |

## <a name="perform-the-consolidation-for-october-2015"></a><span data-ttu-id="44b75-146">Realizar la consolidación para octubre de 2015</span><span class="sxs-lookup"><span data-stu-id="44b75-146">Perform the consolidation for October 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="44b75-147">Saldos en la empresa de consolidación</span><span class="sxs-lookup"><span data-stu-id="44b75-147">Balances in the consolidation company</span></span>

| <span data-ttu-id="44b75-148">Cuenta contable</span><span class="sxs-lookup"><span data-stu-id="44b75-148">Ledger account</span></span> | <span data-ttu-id="44b75-149">Divisa</span><span class="sxs-lookup"><span data-stu-id="44b75-149">Currency</span></span> | <span data-ttu-id="44b75-150">Importe</span><span class="sxs-lookup"><span data-stu-id="44b75-150">Amount</span></span> | <span data-ttu-id="44b75-151">Cálculo</span><span class="sxs-lookup"><span data-stu-id="44b75-151">Calculation</span></span>    |
|----------------|----------|--------|----------------|
| <span data-ttu-id="44b75-152">110110</span><span class="sxs-lookup"><span data-stu-id="44b75-152">110110</span></span>         | <span data-ttu-id="44b75-153">EUR</span><span class="sxs-lookup"><span data-stu-id="44b75-153">EUR</span></span>      | <span data-ttu-id="44b75-154">250</span><span class="sxs-lookup"><span data-stu-id="44b75-154">250</span></span>    | <span data-ttu-id="44b75-155">500 USD × 50%</span><span class="sxs-lookup"><span data-stu-id="44b75-155">500 USD × 50%</span></span>  |
| <span data-ttu-id="44b75-156">130100</span><span class="sxs-lookup"><span data-stu-id="44b75-156">130100</span></span>         | <span data-ttu-id="44b75-157">EUR</span><span class="sxs-lookup"><span data-stu-id="44b75-157">EUR</span></span>      | <span data-ttu-id="44b75-158">-250</span><span class="sxs-lookup"><span data-stu-id="44b75-158">-250</span></span>   | <span data-ttu-id="44b75-159">-500 USD × 50%</span><span class="sxs-lookup"><span data-stu-id="44b75-159">-500 USD × 50%</span></span> |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a><span data-ttu-id="44b75-160">Realizar la revalorización de divisa para las cuentas a partir del 1 de octubre de 2015, hasta el 30 de noviembre de 2015</span><span class="sxs-lookup"><span data-stu-id="44b75-160">Perform currency revaluation for the accounts from October 1, 2015, through November 30, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="44b75-161">Saldos en la empresa de consolidación</span><span class="sxs-lookup"><span data-stu-id="44b75-161">Balances in the consolidation company</span></span>

| <span data-ttu-id="44b75-162">Cuenta contable</span><span class="sxs-lookup"><span data-stu-id="44b75-162">Ledger account</span></span> | <span data-ttu-id="44b75-163">Divisa</span><span class="sxs-lookup"><span data-stu-id="44b75-163">Currency</span></span> | <span data-ttu-id="44b75-164">Importe</span><span class="sxs-lookup"><span data-stu-id="44b75-164">Amount</span></span>  | <span data-ttu-id="44b75-165">Cálculo</span><span class="sxs-lookup"><span data-stu-id="44b75-165">Calculation</span></span>                        |
|----------------|----------|---------|------------------------------------|
| <span data-ttu-id="44b75-166">110110</span><span class="sxs-lookup"><span data-stu-id="44b75-166">110110</span></span>         | <span data-ttu-id="44b75-167">EUR</span><span class="sxs-lookup"><span data-stu-id="44b75-167">EUR</span></span>      | <span data-ttu-id="44b75-168">333.33</span><span class="sxs-lookup"><span data-stu-id="44b75-168">333.33</span></span>  | <span data-ttu-id="44b75-169">Importe original de 500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="44b75-169">Original amount of 500 × 66.6667%</span></span>  |
| <span data-ttu-id="44b75-170">130100</span><span class="sxs-lookup"><span data-stu-id="44b75-170">130100</span></span>         | <span data-ttu-id="44b75-171">EUR</span><span class="sxs-lookup"><span data-stu-id="44b75-171">EUR</span></span>      | <span data-ttu-id="44b75-172">-333.33</span><span class="sxs-lookup"><span data-stu-id="44b75-172">-333.33</span></span> | <span data-ttu-id="44b75-173">Importe original de -500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="44b75-173">Original amount of -500 × 66.6667%</span></span> |
| <span data-ttu-id="44b75-174">801400</span><span class="sxs-lookup"><span data-stu-id="44b75-174">801400</span></span>         | <span data-ttu-id="44b75-175">EUR</span><span class="sxs-lookup"><span data-stu-id="44b75-175">EUR</span></span>      | <span data-ttu-id="44b75-176">83,33</span><span class="sxs-lookup"><span data-stu-id="44b75-176">83.33</span></span>   | <span data-ttu-id="44b75-177">333,33 – 250</span><span class="sxs-lookup"><span data-stu-id="44b75-177">333.33 – 250</span></span>                       |
| <span data-ttu-id="44b75-178">801600</span><span class="sxs-lookup"><span data-stu-id="44b75-178">801600</span></span>         | <span data-ttu-id="44b75-179">EUR</span><span class="sxs-lookup"><span data-stu-id="44b75-179">EUR</span></span>      | <span data-ttu-id="44b75-180">-83.33</span><span class="sxs-lookup"><span data-stu-id="44b75-180">-83.33</span></span>  | <span data-ttu-id="44b75-181">-333,33 – (-250)</span><span class="sxs-lookup"><span data-stu-id="44b75-181">-333.33 – (-250)</span></span>                   |

<span data-ttu-id="44b75-182">Verá transacciones adicionales para los importes de divisa de notificación.</span><span class="sxs-lookup"><span data-stu-id="44b75-182">You will see additional transactions for the reporting currency amounts.</span></span>

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a><span data-ttu-id="44b75-183">Realizar la revalorización de divisa para las cuentas a partir del 1 de octubre de 2015, hasta el 31 de diciembre de 2015</span><span class="sxs-lookup"><span data-stu-id="44b75-183">Perform currency revaluation for the accounts from October 1, 2015, through December 31, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="44b75-184">Saldos en la empresa de consolidación</span><span class="sxs-lookup"><span data-stu-id="44b75-184">Balances in the consolidation company</span></span>

| <span data-ttu-id="44b75-185">Cuenta contable</span><span class="sxs-lookup"><span data-stu-id="44b75-185">Ledger account</span></span> | <span data-ttu-id="44b75-186">Divisa</span><span class="sxs-lookup"><span data-stu-id="44b75-186">Currency</span></span> | <span data-ttu-id="44b75-187">Importe</span><span class="sxs-lookup"><span data-stu-id="44b75-187">Amount</span></span>  | <span data-ttu-id="44b75-188">Cálculo</span><span class="sxs-lookup"><span data-stu-id="44b75-188">Calculation</span></span>                                          |
|----------------|----------|---------|------------------------------------------------------|
| <span data-ttu-id="44b75-189">110110</span><span class="sxs-lookup"><span data-stu-id="44b75-189">110110</span></span>         | <span data-ttu-id="44b75-190">EUR</span><span class="sxs-lookup"><span data-stu-id="44b75-190">EUR</span></span>      | <span data-ttu-id="44b75-191">500,00</span><span class="sxs-lookup"><span data-stu-id="44b75-191">500.00</span></span>  | <span data-ttu-id="44b75-192">Importe original de 500 × 1</span><span class="sxs-lookup"><span data-stu-id="44b75-192">Original amount of 500 × 1</span></span>                           |
| <span data-ttu-id="44b75-193">130100</span><span class="sxs-lookup"><span data-stu-id="44b75-193">130100</span></span>         | <span data-ttu-id="44b75-194">EUR</span><span class="sxs-lookup"><span data-stu-id="44b75-194">EUR</span></span>      | <span data-ttu-id="44b75-195">-500,00</span><span class="sxs-lookup"><span data-stu-id="44b75-195">-500.00</span></span> | <span data-ttu-id="44b75-196">Importe original de -500 × 1</span><span class="sxs-lookup"><span data-stu-id="44b75-196">Original amount of -500 × 1</span></span>                          |
| <span data-ttu-id="44b75-197">801400</span><span class="sxs-lookup"><span data-stu-id="44b75-197">801400</span></span>         | <span data-ttu-id="44b75-198">EUR</span><span class="sxs-lookup"><span data-stu-id="44b75-198">EUR</span></span>      | <span data-ttu-id="44b75-199">250</span><span class="sxs-lookup"><span data-stu-id="44b75-199">250</span></span>     | <span data-ttu-id="44b75-200">500 – 333,33 = 166,67 166,67 + 83,33 = 250</span><span class="sxs-lookup"><span data-stu-id="44b75-200">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span></span>           |
| <span data-ttu-id="44b75-201">801600</span><span class="sxs-lookup"><span data-stu-id="44b75-201">801600</span></span>         | <span data-ttu-id="44b75-202">EUR</span><span class="sxs-lookup"><span data-stu-id="44b75-202">EUR</span></span>      | <span data-ttu-id="44b75-203">-250</span><span class="sxs-lookup"><span data-stu-id="44b75-203">-250</span></span>    | <span data-ttu-id="44b75-204">-500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250</span><span class="sxs-lookup"><span data-stu-id="44b75-204">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span></span> |






