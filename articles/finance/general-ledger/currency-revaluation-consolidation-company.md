---
title: Revalorización de divisa en una empresa de consolidación
description: En este tema se describe cómo revalorizar la divisa en una empresa de consolidación.
author: ShylaThompson
manager: AnnBe
ms.date: 10/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerExchAdjHist
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: hminzner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9b7f0a18910cbaed382971e47eb688c075e7e6a5
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179743"
---
# <a name="currency-revaluation-in-a-consolidation-company"></a><span data-ttu-id="f79e9-103">Revalorización de divisa en una empresa de consolidación</span><span class="sxs-lookup"><span data-stu-id="f79e9-103">Currency revaluation in a consolidation company</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f79e9-104">Cuando se consolidan datos desde una divisa de contabilidad a otra, debe seguir ejecutando la revalorización de divisa si hay un cambio en tipos de cambio, para revalorizar los saldos de cuenta correctamente.</span><span class="sxs-lookup"><span data-stu-id="f79e9-104">When you consolidate data from one accounting currency to another, you must still run currency revaluation if there is a change in exchange rates, so that your account balances  are correctly revalued.</span></span> <span data-ttu-id="f79e9-105">Al consolidar por primera vez los datos, use la pestaña **Traducción de divisas** para seleccionar los tipos de cambio iniciales para su traducción durante el proceso de consolidación.</span><span class="sxs-lookup"><span data-stu-id="f79e9-105">When you originally consolidate the data, use the **Currency translation** tab to select the initial exchange rates to for translation during the consolidation process.</span></span> <span data-ttu-id="f79e9-106">Después de que se introduzcan un nuevo tipo de cambio (por ejemplo, el mes próximo), debe revalorizar los saldos de cuenta.</span><span class="sxs-lookup"><span data-stu-id="f79e9-106">After a new exchange rate is entered (for example, in the next month), you must revalue the account balances.</span></span> <span data-ttu-id="f79e9-107">Después se actualizarán los beneficios no realizados o las pérdidas, en función de la fecha y los nuevos tipo de cambio.</span><span class="sxs-lookup"><span data-stu-id="f79e9-107">The unrealized gains or losses are then updated accordingly, based on the new exchange rate and date.</span></span> <span data-ttu-id="f79e9-108">En el ejemplo siguiente se muestran los asientos contables que se crean durante el proceso.</span><span class="sxs-lookup"><span data-stu-id="f79e9-108">The following example illustrates the accounting entries that are created during the process.</span></span>

## <a name="company-setup"></a><span data-ttu-id="f79e9-109">Configuración de empresa</span><span class="sxs-lookup"><span data-stu-id="f79e9-109">Company setup</span></span>
-   <span data-ttu-id="f79e9-110">**Empresa de origen u operadora (USMF):** se usan dólares americanos (USD) como la divisa de contabilidad y de notificación.</span><span class="sxs-lookup"><span data-stu-id="f79e9-110">**Source/operating company (USMF)** – US dollars (USD) are used as the accounting and reporting currency.</span></span>
-   <span data-ttu-id="f79e9-111">**Empresa consolidada (CON):** se usan euros (EUR) como la divisa de contabilidad y de notificación.</span><span class="sxs-lookup"><span data-stu-id="f79e9-111">**Consolidated company (CON)** – Euros (EUR) are used as the accounting and reporting currency.</span></span>
    -   <span data-ttu-id="f79e9-112">**Beneficio realizado**: cuenta contable 801500</span><span class="sxs-lookup"><span data-stu-id="f79e9-112">**Realized gain**– Ledger account 801500</span></span>
    -   <span data-ttu-id="f79e9-113">**Pérdida realizada:** cuenta contable 801600</span><span class="sxs-lookup"><span data-stu-id="f79e9-113">**Realized loss** – Ledger account 801600</span></span>
    -   <span data-ttu-id="f79e9-114">**Beneficio no realizado:** cuenta contable 801600</span><span class="sxs-lookup"><span data-stu-id="f79e9-114">**Unrealized gain** – Ledger account 801600</span></span>
    -   <span data-ttu-id="f79e9-115">**Pérdida no realizada:** cuenta contable 801400</span><span class="sxs-lookup"><span data-stu-id="f79e9-115">**Unrealized loss** – Ledger account 801400</span></span>

## <a name="original-transactions"></a><span data-ttu-id="f79e9-116">Transacciones originales</span><span class="sxs-lookup"><span data-stu-id="f79e9-116">Original transactions</span></span>
### <a name="cash-receipt-transactions-in-usmf"></a><span data-ttu-id="f79e9-117">Transacciones de recibo de cobro en USMF</span><span class="sxs-lookup"><span data-stu-id="f79e9-117">Cash receipt transactions in USMF</span></span>

| <span data-ttu-id="f79e9-118">Fecha</span><span class="sxs-lookup"><span data-stu-id="f79e9-118">Date</span></span>       | <span data-ttu-id="f79e9-119">Cuenta contable</span><span class="sxs-lookup"><span data-stu-id="f79e9-119">Ledger account</span></span>               | <span data-ttu-id="f79e9-120">Divisa</span><span class="sxs-lookup"><span data-stu-id="f79e9-120">Currency</span></span> | <span data-ttu-id="f79e9-121">Importe</span><span class="sxs-lookup"><span data-stu-id="f79e9-121">Amount</span></span> |
|------------|------------------------------|----------|--------|
| <span data-ttu-id="f79e9-122">11/10/2015</span><span class="sxs-lookup"><span data-stu-id="f79e9-122">10/11/2015</span></span> | <span data-ttu-id="f79e9-123">110110: efectivo</span><span class="sxs-lookup"><span data-stu-id="f79e9-123">110110 – Cash</span></span>                | <span data-ttu-id="f79e9-124">USD</span><span class="sxs-lookup"><span data-stu-id="f79e9-124">USD</span></span>      | <span data-ttu-id="f79e9-125">500</span><span class="sxs-lookup"><span data-stu-id="f79e9-125">500</span></span>    |
| <span data-ttu-id="f79e9-126">11/10/2015</span><span class="sxs-lookup"><span data-stu-id="f79e9-126">10/11/2015</span></span> | <span data-ttu-id="f79e9-127">130100: clientes</span><span class="sxs-lookup"><span data-stu-id="f79e9-127">130100 – Accounts Receivable</span></span> | <span data-ttu-id="f79e9-128">USD</span><span class="sxs-lookup"><span data-stu-id="f79e9-128">USD</span></span>      | <span data-ttu-id="f79e9-129">-500</span><span class="sxs-lookup"><span data-stu-id="f79e9-129">-500</span></span>   |

## <a name="exchange-rates"></a><span data-ttu-id="f79e9-130">Tipos de cambio</span><span class="sxs-lookup"><span data-stu-id="f79e9-130">Exchange rates</span></span>

| <span data-ttu-id="f79e9-131">Desde divisa</span><span class="sxs-lookup"><span data-stu-id="f79e9-131">From currency</span></span> | <span data-ttu-id="f79e9-132">A divisa</span><span class="sxs-lookup"><span data-stu-id="f79e9-132">To currency</span></span> | <span data-ttu-id="f79e9-133">Fecha inicial</span><span class="sxs-lookup"><span data-stu-id="f79e9-133">Start date</span></span> | <span data-ttu-id="f79e9-134">Tipo de cambio</span><span class="sxs-lookup"><span data-stu-id="f79e9-134">Exchange rate</span></span> |
|---------------|-------------|------------|---------------|
| <span data-ttu-id="f79e9-135">EUR</span><span class="sxs-lookup"><span data-stu-id="f79e9-135">EUR</span></span>           | <span data-ttu-id="f79e9-136">USD</span><span class="sxs-lookup"><span data-stu-id="f79e9-136">USD</span></span>         | <span data-ttu-id="f79e9-137">1/10/2015</span><span class="sxs-lookup"><span data-stu-id="f79e9-137">10/1/2015</span></span>  | <span data-ttu-id="f79e9-138">200</span><span class="sxs-lookup"><span data-stu-id="f79e9-138">200</span></span>           |
| <span data-ttu-id="f79e9-139">EUR</span><span class="sxs-lookup"><span data-stu-id="f79e9-139">EUR</span></span>           | <span data-ttu-id="f79e9-140">USD</span><span class="sxs-lookup"><span data-stu-id="f79e9-140">USD</span></span>         | <span data-ttu-id="f79e9-141">1/11/2015</span><span class="sxs-lookup"><span data-stu-id="f79e9-141">11/1/2015</span></span>  | <span data-ttu-id="f79e9-142">150</span><span class="sxs-lookup"><span data-stu-id="f79e9-142">150</span></span>           |
| <span data-ttu-id="f79e9-143">EUR</span><span class="sxs-lookup"><span data-stu-id="f79e9-143">EUR</span></span>           | <span data-ttu-id="f79e9-144">USD</span><span class="sxs-lookup"><span data-stu-id="f79e9-144">USD</span></span>         | <span data-ttu-id="f79e9-145">1/12/2012</span><span class="sxs-lookup"><span data-stu-id="f79e9-145">12/1/2012</span></span>  | <span data-ttu-id="f79e9-146">100</span><span class="sxs-lookup"><span data-stu-id="f79e9-146">100</span></span>           |

## <a name="perform-the-consolidation-for-october-2015"></a><span data-ttu-id="f79e9-147">Realizar la consolidación para octubre de 2015</span><span class="sxs-lookup"><span data-stu-id="f79e9-147">Perform the consolidation for October 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="f79e9-148">Saldos en la empresa de consolidación</span><span class="sxs-lookup"><span data-stu-id="f79e9-148">Balances in the consolidation company</span></span>

| <span data-ttu-id="f79e9-149">Cuenta contable</span><span class="sxs-lookup"><span data-stu-id="f79e9-149">Ledger account</span></span> | <span data-ttu-id="f79e9-150">Divisa</span><span class="sxs-lookup"><span data-stu-id="f79e9-150">Currency</span></span> | <span data-ttu-id="f79e9-151">Importe</span><span class="sxs-lookup"><span data-stu-id="f79e9-151">Amount</span></span> | <span data-ttu-id="f79e9-152">Cálculo</span><span class="sxs-lookup"><span data-stu-id="f79e9-152">Calculation</span></span>    |
|----------------|----------|--------|----------------|
| <span data-ttu-id="f79e9-153">110110</span><span class="sxs-lookup"><span data-stu-id="f79e9-153">110110</span></span>         | <span data-ttu-id="f79e9-154">EUR</span><span class="sxs-lookup"><span data-stu-id="f79e9-154">EUR</span></span>      | <span data-ttu-id="f79e9-155">250</span><span class="sxs-lookup"><span data-stu-id="f79e9-155">250</span></span>    | <span data-ttu-id="f79e9-156">500 USD × 50%</span><span class="sxs-lookup"><span data-stu-id="f79e9-156">500 USD × 50%</span></span>  |
| <span data-ttu-id="f79e9-157">130100</span><span class="sxs-lookup"><span data-stu-id="f79e9-157">130100</span></span>         | <span data-ttu-id="f79e9-158">EUR</span><span class="sxs-lookup"><span data-stu-id="f79e9-158">EUR</span></span>      | <span data-ttu-id="f79e9-159">-250</span><span class="sxs-lookup"><span data-stu-id="f79e9-159">-250</span></span>   | <span data-ttu-id="f79e9-160">-500 USD × 50%</span><span class="sxs-lookup"><span data-stu-id="f79e9-160">-500 USD × 50%</span></span> |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a><span data-ttu-id="f79e9-161">Realizar la revalorización de divisa para las cuentas a partir del 1 de octubre de 2015, hasta el 30 de noviembre de 2015</span><span class="sxs-lookup"><span data-stu-id="f79e9-161">Perform currency revaluation for the accounts from October 1, 2015, through November 30, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="f79e9-162">Saldos en la empresa de consolidación</span><span class="sxs-lookup"><span data-stu-id="f79e9-162">Balances in the consolidation company</span></span>

| <span data-ttu-id="f79e9-163">Cuenta contable</span><span class="sxs-lookup"><span data-stu-id="f79e9-163">Ledger account</span></span> | <span data-ttu-id="f79e9-164">Divisa</span><span class="sxs-lookup"><span data-stu-id="f79e9-164">Currency</span></span> | <span data-ttu-id="f79e9-165">Importe</span><span class="sxs-lookup"><span data-stu-id="f79e9-165">Amount</span></span>  | <span data-ttu-id="f79e9-166">Cálculo</span><span class="sxs-lookup"><span data-stu-id="f79e9-166">Calculation</span></span>                        |
|----------------|----------|---------|------------------------------------|
| <span data-ttu-id="f79e9-167">110110</span><span class="sxs-lookup"><span data-stu-id="f79e9-167">110110</span></span>         | <span data-ttu-id="f79e9-168">EUR</span><span class="sxs-lookup"><span data-stu-id="f79e9-168">EUR</span></span>      | <span data-ttu-id="f79e9-169">333.33</span><span class="sxs-lookup"><span data-stu-id="f79e9-169">333.33</span></span>  | <span data-ttu-id="f79e9-170">Importe original de 500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="f79e9-170">Original amount of 500 × 66.6667%</span></span>  |
| <span data-ttu-id="f79e9-171">130100</span><span class="sxs-lookup"><span data-stu-id="f79e9-171">130100</span></span>         | <span data-ttu-id="f79e9-172">EUR</span><span class="sxs-lookup"><span data-stu-id="f79e9-172">EUR</span></span>      | <span data-ttu-id="f79e9-173">-333.33</span><span class="sxs-lookup"><span data-stu-id="f79e9-173">-333.33</span></span> | <span data-ttu-id="f79e9-174">Importe original de -500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="f79e9-174">Original amount of -500 × 66.6667%</span></span> |
| <span data-ttu-id="f79e9-175">801400</span><span class="sxs-lookup"><span data-stu-id="f79e9-175">801400</span></span>         | <span data-ttu-id="f79e9-176">EUR</span><span class="sxs-lookup"><span data-stu-id="f79e9-176">EUR</span></span>      | <span data-ttu-id="f79e9-177">83,33</span><span class="sxs-lookup"><span data-stu-id="f79e9-177">83.33</span></span>   | <span data-ttu-id="f79e9-178">333,33 – 250</span><span class="sxs-lookup"><span data-stu-id="f79e9-178">333.33 – 250</span></span>                       |
| <span data-ttu-id="f79e9-179">801600</span><span class="sxs-lookup"><span data-stu-id="f79e9-179">801600</span></span>         | <span data-ttu-id="f79e9-180">EUR</span><span class="sxs-lookup"><span data-stu-id="f79e9-180">EUR</span></span>      | <span data-ttu-id="f79e9-181">-83.33</span><span class="sxs-lookup"><span data-stu-id="f79e9-181">-83.33</span></span>  | <span data-ttu-id="f79e9-182">-333,33 – (-250)</span><span class="sxs-lookup"><span data-stu-id="f79e9-182">-333.33 – (-250)</span></span>                   |

<span data-ttu-id="f79e9-183">Verá transacciones adicionales para los importes de divisa de notificación.</span><span class="sxs-lookup"><span data-stu-id="f79e9-183">You will see additional transactions for the reporting currency amounts.</span></span>

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a><span data-ttu-id="f79e9-184">Realizar la revalorización de divisa para las cuentas a partir del 1 de octubre de 2015, hasta el 31 de diciembre de 2015</span><span class="sxs-lookup"><span data-stu-id="f79e9-184">Perform currency revaluation for the accounts from October 1, 2015, through December 31, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="f79e9-185">Saldos en la empresa de consolidación</span><span class="sxs-lookup"><span data-stu-id="f79e9-185">Balances in the consolidation company</span></span>

| <span data-ttu-id="f79e9-186">Cuenta contable</span><span class="sxs-lookup"><span data-stu-id="f79e9-186">Ledger account</span></span> | <span data-ttu-id="f79e9-187">Divisa</span><span class="sxs-lookup"><span data-stu-id="f79e9-187">Currency</span></span> | <span data-ttu-id="f79e9-188">Importe</span><span class="sxs-lookup"><span data-stu-id="f79e9-188">Amount</span></span>  | <span data-ttu-id="f79e9-189">Cálculo</span><span class="sxs-lookup"><span data-stu-id="f79e9-189">Calculation</span></span>                                          |
|----------------|----------|---------|------------------------------------------------------|
| <span data-ttu-id="f79e9-190">110110</span><span class="sxs-lookup"><span data-stu-id="f79e9-190">110110</span></span>         | <span data-ttu-id="f79e9-191">EUR</span><span class="sxs-lookup"><span data-stu-id="f79e9-191">EUR</span></span>      | <span data-ttu-id="f79e9-192">500,00</span><span class="sxs-lookup"><span data-stu-id="f79e9-192">500.00</span></span>  | <span data-ttu-id="f79e9-193">Importe original de 500 × 1</span><span class="sxs-lookup"><span data-stu-id="f79e9-193">Original amount of 500 × 1</span></span>                           |
| <span data-ttu-id="f79e9-194">130100</span><span class="sxs-lookup"><span data-stu-id="f79e9-194">130100</span></span>         | <span data-ttu-id="f79e9-195">EUR</span><span class="sxs-lookup"><span data-stu-id="f79e9-195">EUR</span></span>      | <span data-ttu-id="f79e9-196">-500,00</span><span class="sxs-lookup"><span data-stu-id="f79e9-196">-500.00</span></span> | <span data-ttu-id="f79e9-197">Importe original de -500 × 1</span><span class="sxs-lookup"><span data-stu-id="f79e9-197">Original amount of -500 × 1</span></span>                          |
| <span data-ttu-id="f79e9-198">801400</span><span class="sxs-lookup"><span data-stu-id="f79e9-198">801400</span></span>         | <span data-ttu-id="f79e9-199">EUR</span><span class="sxs-lookup"><span data-stu-id="f79e9-199">EUR</span></span>      | <span data-ttu-id="f79e9-200">250</span><span class="sxs-lookup"><span data-stu-id="f79e9-200">250</span></span>     | <span data-ttu-id="f79e9-201">500 – 333,33 = 166,67 166,67 + 83,33 = 250</span><span class="sxs-lookup"><span data-stu-id="f79e9-201">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span></span>           |
| <span data-ttu-id="f79e9-202">801600</span><span class="sxs-lookup"><span data-stu-id="f79e9-202">801600</span></span>         | <span data-ttu-id="f79e9-203">EUR</span><span class="sxs-lookup"><span data-stu-id="f79e9-203">EUR</span></span>      | <span data-ttu-id="f79e9-204">-250</span><span class="sxs-lookup"><span data-stu-id="f79e9-204">-250</span></span>    | <span data-ttu-id="f79e9-205">-500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250</span><span class="sxs-lookup"><span data-stu-id="f79e9-205">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span></span> |




