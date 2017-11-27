---
title: "Efectos de depreciación con inversiones"
description: "En este artículo se describen las implicaciones potenciales de invertir una transacción de activo fijo."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 2961
ms.assetid: 63a3ac92-c321-4379-a86a-b1b14915f340
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6672047cb3234e4432190d3afb20f46827ad5ef4
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="depreciation-effects-with-reversals"></a><span data-ttu-id="85de4-103">Efectos de depreciación con inversiones</span><span class="sxs-lookup"><span data-stu-id="85de4-103">Depreciation effects with reversals</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="85de4-104">En este artículo se describen las implicaciones potenciales de invertir una transacción de activo fijo.</span><span class="sxs-lookup"><span data-stu-id="85de4-104">This article discusses potential implications of reversing a fixed asset transaction.</span></span> 

<span data-ttu-id="85de4-105">Se pueden invertir las transacciones de activos fijos, así como las transacciones que están asociadas a un activo fijo.</span><span class="sxs-lookup"><span data-stu-id="85de4-105">You can reverse fixed asset transactions, and the transactions that are associated with a fixed asset.</span></span> <span data-ttu-id="85de4-106">También se puede revocar una transacción invertida.</span><span class="sxs-lookup"><span data-stu-id="85de4-106">You can also revoke a reversed transaction.</span></span> 

<span data-ttu-id="85de4-107">Puede invertir o revocar una transacción que no era la transacción más reciente registrada para el activo en el libro.</span><span class="sxs-lookup"><span data-stu-id="85de4-107">You can reverse or revoke a transaction that was not the most recent transaction posted to the book for the asset.</span></span> <span data-ttu-id="85de4-108">Para ello, se debe determinar primero si se ha registrado alguna transacción de depreciación después de la transacción que se desea invertir.</span><span class="sxs-lookup"><span data-stu-id="85de4-108">You should first determine whether any depreciation transactions were posted after the transaction that you are reversing.</span></span> <span data-ttu-id="85de4-109">El motivo de esta comprobación es que la depreciación no se calcula de nuevo al invertir una transacción,</span><span class="sxs-lookup"><span data-stu-id="85de4-109">This is because depreciation is not recalculated when you reverse a transaction.</span></span> <span data-ttu-id="85de4-110">por lo que a menudo la depreciación es excesiva o insuficiente después de la inversión, tal como se muestra en los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="85de4-110">Therefore, depreciation often is overstated or understated after the reversal, as shown in the examples.</span></span> 

<span data-ttu-id="85de4-111">Para garantizar que la depreciación es correcta al invertir una transacción, no continúe con la inversión si recibe un mensaje durante el proceso en el que se indica que no se calculará de nuevo la depreciación.</span><span class="sxs-lookup"><span data-stu-id="85de4-111">To make sure that depreciation is correct when you reverse a transaction, do not continue with the reversal if you receive a message that states that depreciation will not be recalculated.</span></span> <span data-ttu-id="85de4-112">En su lugar, invierta primero la transacción de depreciación registrada después de la transacción que desea invertir y, a continuación, proceda con la inversión.</span><span class="sxs-lookup"><span data-stu-id="85de4-112">Instead, first reverse the depreciation transaction that was posted after the transaction you tried to reverse, and then continue with the reversal.</span></span> <span data-ttu-id="85de4-113">No recibirá ningún mensaje sobre el nuevo cálculo de la depreciación y podrá continuar con la inversión.</span><span class="sxs-lookup"><span data-stu-id="85de4-113">You will not be warned about depreciation recalculations, and you can continue with the reversal.</span></span> 

<span data-ttu-id="85de4-114">Los ejemplos siguientes muestran los cálculos que se efectúan si continúa a pesar del mensaje de advertencia sin invertir primero las transacciones de depreciación.</span><span class="sxs-lookup"><span data-stu-id="85de4-114">The following examples show the calculations that occur if you continue beyond the message without first reversing the depreciation transactions.</span></span>

## <a name="example-1-depreciation-is-overstated"></a><span data-ttu-id="85de4-115">Ejemplo 1: la depreciación es excesiva</span><span class="sxs-lookup"><span data-stu-id="85de4-115">Example 1: Depreciation is overstated</span></span>
<span data-ttu-id="85de4-116">Un activo fijo se configura con un tiempo de vida de 5 años y un tipo de depreciación lineal (60 períodos de depreciación).</span><span class="sxs-lookup"><span data-stu-id="85de4-116">An asset is set up with a 5-year useful life and straight line depreciation (60 depreciation periods).</span></span> <span data-ttu-id="85de4-117">En este ejemplo, la depreciación es excesiva.</span><span class="sxs-lookup"><span data-stu-id="85de4-117">In this example, depreciation is overstated.</span></span>
#### <a name="asset-transaction-history"></a><span data-ttu-id="85de4-118">Historial de transacción del activo</span><span class="sxs-lookup"><span data-stu-id="85de4-118">Asset transaction history</span></span>

| <span data-ttu-id="85de4-119">Fecha</span><span class="sxs-lookup"><span data-stu-id="85de4-119">Date</span></span>       | <span data-ttu-id="85de4-120">Tipo de transacción</span><span class="sxs-lookup"><span data-stu-id="85de4-120">Transaction type</span></span>                                                          | <span data-ttu-id="85de4-121">Importe</span><span class="sxs-lookup"><span data-stu-id="85de4-121">Amount</span></span>                                    |
|------------|---------------------------------------------------------------------------|-------------------------------------------|
| <span data-ttu-id="85de4-122">1 de enero</span><span class="sxs-lookup"><span data-stu-id="85de4-122">January 1</span></span>  | <span data-ttu-id="85de4-123">Adquisición</span><span class="sxs-lookup"><span data-stu-id="85de4-123">Acquisition</span></span>                                                               | <span data-ttu-id="85de4-124">59.000,00</span><span class="sxs-lookup"><span data-stu-id="85de4-124">59,000.00</span></span>                                 |
| <span data-ttu-id="85de4-125">1 de enero</span><span class="sxs-lookup"><span data-stu-id="85de4-125">January 1</span></span>  | <span data-ttu-id="85de4-126">Ajuste de adquisición</span><span class="sxs-lookup"><span data-stu-id="85de4-126">Acquisition adjustment</span></span>                                                    | <span data-ttu-id="85de4-127">1.000,00</span><span class="sxs-lookup"><span data-stu-id="85de4-127">1,000.00</span></span>                                  |
| <span data-ttu-id="85de4-128">31 de enero</span><span class="sxs-lookup"><span data-stu-id="85de4-128">January 31</span></span> | <span data-ttu-id="85de4-129">Depreciación (creada mediante una propuesta para un período de depreciación)</span><span class="sxs-lookup"><span data-stu-id="85de4-129">Depreciation (created by using a proposal for one period of depreciation)</span></span> | <span data-ttu-id="85de4-130">1.000,00 Cálculo: valor neto (59.000 + 1.000) / Número de períodos de depreciación restantes (60)</span><span class="sxs-lookup"><span data-stu-id="85de4-130">1,000.00Calculation: Book value (59,000 + 1,000) / Number of depreciation periods remaining (60)</span></span> |

#### <a name="reversal-action"></a><span data-ttu-id="85de4-131">Acción de inversión</span><span class="sxs-lookup"><span data-stu-id="85de4-131">Reversal action</span></span>

| <span data-ttu-id="85de4-132">Fecha</span><span class="sxs-lookup"><span data-stu-id="85de4-132">Date</span></span>      | <span data-ttu-id="85de4-133">Tipo de transacción</span><span class="sxs-lookup"><span data-stu-id="85de4-133">Transaction type</span></span>                | <span data-ttu-id="85de4-134">Importe</span><span class="sxs-lookup"><span data-stu-id="85de4-134">Amount</span></span>    |
|-----------|---------------------------------|-----------|
| <span data-ttu-id="85de4-135">1 de enero</span><span class="sxs-lookup"><span data-stu-id="85de4-135">January 1</span></span> | <span data-ttu-id="85de4-136">Inversión del ajuste de adquisición</span><span class="sxs-lookup"><span data-stu-id="85de4-136">Acquisition adjustment reversal</span></span> | <span data-ttu-id="85de4-137">–1.000,00</span><span class="sxs-lookup"><span data-stu-id="85de4-137">–1,000.00</span></span> |

#### <a name="depreciation-effect"></a><span data-ttu-id="85de4-138">Efecto de la depreciación</span><span class="sxs-lookup"><span data-stu-id="85de4-138">Depreciation effect</span></span>

| <span data-ttu-id="85de4-139">Fecha</span><span class="sxs-lookup"><span data-stu-id="85de4-139">Date</span></span>        | <span data-ttu-id="85de4-140">Tipo de transacción</span><span class="sxs-lookup"><span data-stu-id="85de4-140">Transaction type</span></span>        | <span data-ttu-id="85de4-141">Importe</span><span class="sxs-lookup"><span data-stu-id="85de4-141">Amount</span></span>                                                                                |
|-------------|-------------------------|---------------------------------------------------------------------------------------|
| <span data-ttu-id="85de4-142">28 de febrero</span><span class="sxs-lookup"><span data-stu-id="85de4-142">February 28</span></span> | <span data-ttu-id="85de4-143">Depreciación (propuesta)</span><span class="sxs-lookup"><span data-stu-id="85de4-143">Depreciation (proposal)</span></span> | <span data-ttu-id="85de4-144">983,05 Cálculo: valor neto (59.000 - 1.000 depreciación) / Número de períodos de depreciación restantes (59)</span><span class="sxs-lookup"><span data-stu-id="85de4-144">983.05Calculation: Book value (59,000 - 1,000 depreciation) / Number of depreciation periods remaining (59)</span></span> |

<span data-ttu-id="85de4-145">La depreciación se excede en 16,95 (1.000 - 983,05).</span><span class="sxs-lookup"><span data-stu-id="85de4-145">Depreciation is overstated by 16.95 (1,000 - 983.05).</span></span>

## <a name="example-2-depreciation-is-understated"></a><span data-ttu-id="85de4-146">Ejemplo 2: Depreciación insuficiente</span><span class="sxs-lookup"><span data-stu-id="85de4-146">Example 2: Depreciation is understated</span></span>
<span data-ttu-id="85de4-147">Un activo fijo se configura con un tiempo de vida de 5 años y un tipo de depreciación lineal (60 períodos de depreciación).</span><span class="sxs-lookup"><span data-stu-id="85de4-147">An asset is set up with a 5-year useful life and straight line depreciation (60 depreciation periods).</span></span> <span data-ttu-id="85de4-148">En este ejemplo, la depreciación es insuficiente.</span><span class="sxs-lookup"><span data-stu-id="85de4-148">In this example, depreciation is understated.</span></span>
#### <a name="asset-transaction-history"></a><span data-ttu-id="85de4-149">Historial de transacción del activo</span><span class="sxs-lookup"><span data-stu-id="85de4-149">Asset transaction history</span></span>

| <span data-ttu-id="85de4-150">Fecha</span><span class="sxs-lookup"><span data-stu-id="85de4-150">Date</span></span>       | <span data-ttu-id="85de4-151">Tipo de transacción</span><span class="sxs-lookup"><span data-stu-id="85de4-151">Transaction type</span></span>                                                          | <span data-ttu-id="85de4-152">Importe</span><span class="sxs-lookup"><span data-stu-id="85de4-152">Amount</span></span>                                      |
|------------|---------------------------------------------------------------------------|---------------------------------------------|
| <span data-ttu-id="85de4-153">1 de enero</span><span class="sxs-lookup"><span data-stu-id="85de4-153">January 1</span></span>  | <span data-ttu-id="85de4-154">Adquisición</span><span class="sxs-lookup"><span data-stu-id="85de4-154">Acquisition</span></span>                                                               | <span data-ttu-id="85de4-155">59.000,00</span><span class="sxs-lookup"><span data-stu-id="85de4-155">59,000.00</span></span>                                   |
| <span data-ttu-id="85de4-156">1 de enero</span><span class="sxs-lookup"><span data-stu-id="85de4-156">January 1</span></span>  | <span data-ttu-id="85de4-157">Ajuste de devaluación</span><span class="sxs-lookup"><span data-stu-id="85de4-157">Write-down adjustment</span></span>                                                     | <span data-ttu-id="85de4-158">1.000,00</span><span class="sxs-lookup"><span data-stu-id="85de4-158">1,000.00</span></span>                                    |
| <span data-ttu-id="85de4-159">31 de enero</span><span class="sxs-lookup"><span data-stu-id="85de4-159">January 31</span></span> | <span data-ttu-id="85de4-160">Depreciación (creada mediante una propuesta para un período de depreciación)</span><span class="sxs-lookup"><span data-stu-id="85de4-160">Depreciation (created by using a proposal for one period of depreciation)</span></span> | <span data-ttu-id="85de4-161">966,67 Cálculo: valor neto (59.000 - 1.000) / Número de períodos de depreciación restantes (60)</span><span class="sxs-lookup"><span data-stu-id="85de4-161">966.67Calculation: Book value (59,000 - 1,000) / Number of depreciation periods remaining (60)</span></span> |

#### <a name="reversal-action"></a><span data-ttu-id="85de4-162">Acción de inversión</span><span class="sxs-lookup"><span data-stu-id="85de4-162">Reversal action</span></span>

| <span data-ttu-id="85de4-163">Fecha</span><span class="sxs-lookup"><span data-stu-id="85de4-163">Date</span></span>      | <span data-ttu-id="85de4-164">Tipo de transacción</span><span class="sxs-lookup"><span data-stu-id="85de4-164">Transaction type</span></span>               | <span data-ttu-id="85de4-165">Importe</span><span class="sxs-lookup"><span data-stu-id="85de4-165">Amount</span></span>    |
|-----------|--------------------------------|-----------|
| <span data-ttu-id="85de4-166">1 de enero</span><span class="sxs-lookup"><span data-stu-id="85de4-166">January 1</span></span> | <span data-ttu-id="85de4-167">Inversión de ajuste de devaluación</span><span class="sxs-lookup"><span data-stu-id="85de4-167">Write-down adjustment reversal</span></span> | <span data-ttu-id="85de4-168">–1.000,00</span><span class="sxs-lookup"><span data-stu-id="85de4-168">–1,000.00</span></span> |

#### <a name="depreciation-effect"></a><span data-ttu-id="85de4-169">Efecto de la depreciación</span><span class="sxs-lookup"><span data-stu-id="85de4-169">Depreciation effect</span></span>

| <span data-ttu-id="85de4-170">Fecha</span><span class="sxs-lookup"><span data-stu-id="85de4-170">Date</span></span>        | <span data-ttu-id="85de4-171">Tipo de transacción</span><span class="sxs-lookup"><span data-stu-id="85de4-171">Transaction type</span></span>        | <span data-ttu-id="85de4-172">Importe</span><span class="sxs-lookup"><span data-stu-id="85de4-172">Amount</span></span>                                                                                       |
|-------------|-------------------------|----------------------------------------------------------------------------------------------|
| <span data-ttu-id="85de4-173">28 de febrero</span><span class="sxs-lookup"><span data-stu-id="85de4-173">February 28</span></span> | <span data-ttu-id="85de4-174">Depreciación (propuesta)</span><span class="sxs-lookup"><span data-stu-id="85de4-174">Depreciation (proposal)</span></span> | <span data-ttu-id="85de4-175">983,62 Cálculo: valor neto (59.000 - 966,67 depreciación) / Número de períodos de depreciación restantes (59)</span><span class="sxs-lookup"><span data-stu-id="85de4-175">983.62Calculation: Book value (59,000 - 966.67 depreciation) / Number of depreciation periods remaining (59)</span></span> |

<span data-ttu-id="85de4-176">La depreciación es insuficiente por 16,95 (983,62 - 966,67).</span><span class="sxs-lookup"><span data-stu-id="85de4-176">Depreciation is understated by 16.95 (983.62 - 966.67).</span></span>



<a name="see-also"></a><span data-ttu-id="85de4-177">Consulte también</span><span class="sxs-lookup"><span data-stu-id="85de4-177">See also</span></span>
--------

[<span data-ttu-id="85de4-178">Depreciación de activos fijos</span><span class="sxs-lookup"><span data-stu-id="85de4-178">Fixed asset depreciation</span></span>](fixed-asset-depreciation.md)




