---
title: Tipos de registro de arrendamientos
description: Este tema describe los tipos de registro que se utilizan para transacciones de arrendamiento de activos.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1d76c7ea72346c432db04bbe7947dea0c2911ea8
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881141"
---
# <a name="lease-posting-types"></a><span data-ttu-id="779fc-103">Tipos de registro de arrendamientos</span><span class="sxs-lookup"><span data-stu-id="779fc-103">Lease posting types</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="779fc-104">Este tema describe los tipos de registro que se utilizan para transacciones de arrendamiento de activos.</span><span class="sxs-lookup"><span data-stu-id="779fc-104">This topic describes the posting types that are used for asset leasing transactions.</span></span>

## <a name="lease-asset"></a><span data-ttu-id="779fc-105">Activo de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="779fc-105">Lease asset</span></span>

<span data-ttu-id="779fc-106">La cuenta está asociada con el activo por derecho de uso (ROU).</span><span class="sxs-lookup"><span data-stu-id="779fc-106">The account is associated with the right-of-use (ROU) asset.</span></span> <span data-ttu-id="779fc-107">Esta cuenta se carga cuando un arrendamiento se reconoce inicialmente según los nuevos estándares de contabilidad de arrendamientos, el Tema de codificación de normas de contabilidad 842 (ASC 842) y la Norma Internacional de Información Financiera 16 (IFRS 16).</span><span class="sxs-lookup"><span data-stu-id="779fc-107">This account is debited when a lease is initially recognized under the new lease accounting standards, Accounting Standards Codification Topic 842 (ASC 842) and International Financial Reporting Standard 16 (IFRS 16).</span></span> <span data-ttu-id="779fc-108">Para un arrendamiento modificado, esta cuenta puede ser adeudada o abonada, dependiendo de si la modificación aumenta o disminuye el pasivo por arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="779fc-108">For a modified lease, this account might be either debited or credited, depending on whether the modification increases or decreases the lease liability.</span></span>

<span data-ttu-id="779fc-109">**Movimientos de diario de ejemplo:** reconocimiento inicial</span><span class="sxs-lookup"><span data-stu-id="779fc-109">**Example journal entries:** Initial recognition</span></span><br>
<span data-ttu-id="779fc-110">**Débito:** activo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-110">**Debit:** Lease asset XXX</span></span><br>
<span data-ttu-id="779fc-111">**Crédito:** pasivo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-111">**Credit:** Lease liability XXX</span></span>

## <a name="lease-liability"></a><span data-ttu-id="779fc-112">Pasivo por arrendamiento</span><span class="sxs-lookup"><span data-stu-id="779fc-112">Lease liability</span></span>

<span data-ttu-id="779fc-113">La cuenta está asociada con el pasivo por arrendamiento que ocurre cuando los pagos se descuentan según las nuevas normas IFRS 16 y ASC 842.</span><span class="sxs-lookup"><span data-stu-id="779fc-113">The account is associated with the lease liability that occurs when payments are discounted under the new IFRS 16 and ASC 842 standards.</span></span> <span data-ttu-id="779fc-114">Esta cuenta se acredita cuando un arrendamiento se reconoce inicialmente bajo las nuevas normas.</span><span class="sxs-lookup"><span data-stu-id="779fc-114">This account is credited when a lease is initially recognized under the new standards.</span></span> <span data-ttu-id="779fc-115">Se adeuda para los pagos por arrendamiento y se abona para los intereses acumulados.</span><span class="sxs-lookup"><span data-stu-id="779fc-115">It's debited for lease payments and credited for interest accruals.</span></span>

<span data-ttu-id="779fc-116">**Movimientos de diario de ejemplo:** reconocimiento inicial</span><span class="sxs-lookup"><span data-stu-id="779fc-116">**Example journal entries:** Initial recognition</span></span><br>
<span data-ttu-id="779fc-117">**Débito:** activo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-117">**Debit:** Lease asset XXX</span></span><br>
<span data-ttu-id="779fc-118">**Crédito:** pasivo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-118">**Credit:** Lease liability XXX</span></span>

<span data-ttu-id="779fc-119">**Entradas de diario de ejemplo:** intereses acumulados</span><span class="sxs-lookup"><span data-stu-id="779fc-119">**Example journal entries:** Interest accrual</span></span><br>
<span data-ttu-id="779fc-120">**Débito:** gasto por intereses XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-120">**Debit:** Interest expense XXX</span></span><br>
<span data-ttu-id="779fc-121">**Crédito:** pasivo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-121">**Credit:** Lease liability XXX</span></span>

<span data-ttu-id="779fc-122">**Entradas de diario de ejemplo:** pago por arrendamiento</span><span class="sxs-lookup"><span data-stu-id="779fc-122">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="779fc-123">**Débito:** pasivo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-123">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="779fc-124">**Crédito:** pagable a proveedores/pago por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-124">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="short-term-lease-liability"></a><span data-ttu-id="779fc-125">Pasivo por arrendamiento a corto plazo</span><span class="sxs-lookup"><span data-stu-id="779fc-125">Short-term lease liability</span></span>

<span data-ttu-id="779fc-126">La cuenta está asociada con el pasivo por arrendamiento a corto plazo cuando se contabiliza el asiento de diario de reclasificación del pasivo por arrendamiento a corto plazo.</span><span class="sxs-lookup"><span data-stu-id="779fc-126">The account is associated with the short-term lease liability when the short-term lease liability reclass journal entry is posted.</span></span> <span data-ttu-id="779fc-127">A esta cuenta se le abona el pasivo a corto plazo del programa de amortización el último día del mes.</span><span class="sxs-lookup"><span data-stu-id="779fc-127">This account is credited for the short-term liability from the amortization schedule on the last day of the month.</span></span> <span data-ttu-id="779fc-128">Sin embargo, la misma cantidad se carga el primer día del mes siguiente.</span><span class="sxs-lookup"><span data-stu-id="779fc-128">However, the same amount is debited on the first day of the next month.</span></span>

<span data-ttu-id="779fc-129">**Entradas de diario de ejemplo:** reclasificación del pasivo por arrendamiento a corto plazo</span><span class="sxs-lookup"><span data-stu-id="779fc-129">**Example journal entries:** Short-term lease liability reclass</span></span><br>
<span data-ttu-id="779fc-130">**Débito:** pasivo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-130">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="779fc-131">**Crédito:** pasivo por arrendamiento a corto plazo XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-131">**Credit:** Short-term lease liability XXX</span></span><br>
<span data-ttu-id="779fc-132">**Débito:** pasivo por arrendamiento a corto plazo XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-132">**Debit:** Short-term lease liability XXX</span></span><br>
<span data-ttu-id="779fc-133">**Crédito:** pasivo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-133">**Credit:** Lease liability XXX</span></span>

## <a name="depreciation-expense"></a><span data-ttu-id="779fc-134">Gasto de depreciación</span><span class="sxs-lookup"><span data-stu-id="779fc-134">Depreciation expense</span></span>

<span data-ttu-id="779fc-135">La cuenta está asociada con el gasto que está relacionado con la depreciación del activo por derecho de uso según IFRS 16, ASC 842 y arrendamientos financieros según IAS 17 y ASC 840.</span><span class="sxs-lookup"><span data-stu-id="779fc-135">The account is associated with the expense that is related to the depreciation of the ROU asset under IFRS 16, ASC 842, and finance leases under IAS 17 and ASC 840.</span></span> <span data-ttu-id="779fc-136">Esta cuenta se carga cuando un aactivo por derecho de uso se deprecia cada mes.</span><span class="sxs-lookup"><span data-stu-id="779fc-136">This account is debited when an ROU asset is depreciated each month.</span></span>

<span data-ttu-id="779fc-137">**Entradas de diario de ejemplo:** depreciación acumulada</span><span class="sxs-lookup"><span data-stu-id="779fc-137">**Example journal entries:** Depreciation accrual</span></span><br>
<span data-ttu-id="779fc-138">**Débito:** gasto de depreciación XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-138">**Debit:** Depreciation expense XXX</span></span><br>
<span data-ttu-id="779fc-139">**Crédito** depreciación acumulada XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-139">**Credit:** Accumulated Depreciation XXX</span></span>

## <a name="gainloss-on-lease-modification"></a><span data-ttu-id="779fc-140">Ganancias y pérdidas en modificación de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="779fc-140">Gain/loss on lease modification</span></span>

<span data-ttu-id="779fc-141">La cuenta está asociada con cualquier ganancia o pérdida que surja de las modificaciones del arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="779fc-141">The account is associated with any gains or losses that arise from lease modifications.</span></span> <span data-ttu-id="779fc-142">Puede surgir una ganancia durante una modificación de arrendamiento si la modificación disminuye el pasivo por arrendamiento en una cantidad que exceda el valor en libros del activo por derecho de uso.</span><span class="sxs-lookup"><span data-stu-id="779fc-142">A gain might arise during a lease modification if the modification decreases the lease liability by an amount that exceeds the carrying value of the ROU asset.</span></span>

<span data-ttu-id="779fc-143">Por ejemplo, un arrendamiento tiene un valor en libros actual del pasivo por arrendamiento de 150.000 $ y un valor en libros del activo por derecho de uso de 100.000 $.</span><span class="sxs-lookup"><span data-stu-id="779fc-143">For example, a lease has a current carrying value of the lease liability of $150,000 and a carrying value of the ROU asset of $100,000.</span></span> <span data-ttu-id="779fc-144">El arrendamiento se modifica y esta modificación produce un nuevo valor presente de los pagos mínimos futuros del arrendamiento (PVFMLP) de 40.000 $.</span><span class="sxs-lookup"><span data-stu-id="779fc-144">The lease is modified, and this modification produces a new present value of the future minimum lease payments (PVFMLP) of $40,000.</span></span> <span data-ttu-id="779fc-145">Por lo tanto, el pasivo del arrendamiento se cargará con 110.000 $ (150.000 $ - 40.000 $).</span><span class="sxs-lookup"><span data-stu-id="779fc-145">Therefore, the lease liability will be debited by $110,000 ($150,000 – $40,000).</span></span> <span data-ttu-id="779fc-146">Dado que el activo por derecho de uso es de solo 100.000 $, la disminución de 110.000 $ disminuirá el activo más allá de 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="779fc-146">Because the ROU asset is only $100,000, the decrease of $110,000 will decrease the asset past 0 (zero).</span></span> <span data-ttu-id="779fc-147">Por lo tanto, la guía contable establece que el resto debe registrarse en una cuenta de ganancias.</span><span class="sxs-lookup"><span data-stu-id="779fc-147">Therefore, the accounting guidance states that the remainder should be booked to a gain account.</span></span> <span data-ttu-id="779fc-148">En este caso, el movimiento final del diario será un adeudo al pasivo por arrendamiento por 110.000 $, un abono al activo por arrendamiento por 100.000 $ y un abono a la cuenta de ganancias por 10.000 $.</span><span class="sxs-lookup"><span data-stu-id="779fc-148">In this case, the final journal entry will be a debit to the lease liability for $110,000, a credit to the lease asset for $100,000, and a credit to the gain account for $10,000.</span></span>

<span data-ttu-id="779fc-149">**Entradas de diario de ejemplo:** modificación de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="779fc-149">**Example journal entries:** Lease modification</span></span><br>
<span data-ttu-id="779fc-150">**Débito:** pasivo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-150">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="779fc-151">**Crédito:** activo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-151">**Credit:** Lease Asset XXX</span></span><br>
<span data-ttu-id="779fc-152">**Crédito:** ganancia XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-152">**Credit:** Gain XXX</span></span>

## <a name="accumulated-depreciation"></a><span data-ttu-id="779fc-153">Depreciación acumulada</span><span class="sxs-lookup"><span data-stu-id="779fc-153">Accumulated depreciation</span></span>

<span data-ttu-id="779fc-154">La cuenta está asociada con la cuenta enfrentada al activo del activo por derecho de uso.</span><span class="sxs-lookup"><span data-stu-id="779fc-154">The account is associated with the contra-asset account of the ROU asset.</span></span> <span data-ttu-id="779fc-155">Se abonará en esta cuenta cuando se registre un gasto de depreciación.</span><span class="sxs-lookup"><span data-stu-id="779fc-155">This account is credited when a depreciation expense is posted.</span></span>

<span data-ttu-id="779fc-156">**Entradas de diario de ejemplo:** depreciación acumulada</span><span class="sxs-lookup"><span data-stu-id="779fc-156">**Example journal entries:** Depreciation accrual</span></span><br>
<span data-ttu-id="779fc-157">**Débito:** gasto de depreciación XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-157">**Debit:** Depreciation expense XXX</span></span><br>
<span data-ttu-id="779fc-158">**Crédito:** depreciación acumulada XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-158">**Credit:** Accumulated depreciation XXX</span></span>

## <a name="variable-payment"></a><span data-ttu-id="779fc-159">Pago variable</span><span class="sxs-lookup"><span data-stu-id="779fc-159">Variable payment</span></span>

<span data-ttu-id="779fc-160">La cuenta está asociada con los pagos de arrendamiento variables que se producen por una revalorización del índice en arrendamientos ASC 842, ASC 840 e IAS 17.</span><span class="sxs-lookup"><span data-stu-id="779fc-160">The account is associated with variable lease payments that are produced by an index revaluation under ASC 842, ASC 840, and IAS 17 leases.</span></span> <span data-ttu-id="779fc-161">En la programación de pagos de arrendamiento, los pagos variables se incluyen en la columna **Pago variable**.</span><span class="sxs-lookup"><span data-stu-id="779fc-161">In the lease payment schedule, variable payments are included in the **Variable payment** column.</span></span> <span data-ttu-id="779fc-162">Esta cuenta se carga cuando se crea una factura contra una línea de programación de pagos que contiene un pago variable.</span><span class="sxs-lookup"><span data-stu-id="779fc-162">This account is debited when an invoice is created against a payment schedule line that contains a variable payment.</span></span>

<span data-ttu-id="779fc-163">**Entradas de diario de ejemplo:** pago por arrendamiento</span><span class="sxs-lookup"><span data-stu-id="779fc-163">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="779fc-164">**Débito:** pasivo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-164">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="779fc-165">**Débito:** pago variable XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-165">**Debit:** Variable payment XXX</span></span><br>
<span data-ttu-id="779fc-166">**Crédito:** pagable a proveedores/pago por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-166">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="deferred-rent-asset-liability"></a><span data-ttu-id="779fc-167">Activo de arrendamiento diferido (pasivo)</span><span class="sxs-lookup"><span data-stu-id="779fc-167">Deferred rent asset (liability)</span></span>

<span data-ttu-id="779fc-168">La cuenta está asociada con el activo o pasivo por arrendamiento diferido que se produce por un arrendamiento con tratamiento de arrendamiento diferido.</span><span class="sxs-lookup"><span data-stu-id="779fc-168">The account is associated with the deferred rent asset or liability that is produced by a deferred rent treatment lease.</span></span> <span data-ttu-id="779fc-169">Esta cuenta se adeuda cuando se contabiliza una factura contra un arrendamiento con tratamiento de arrendamiento diferido, si el importe del pago del arrendamiento es mayor que el gasto de alquiler lineal del período.</span><span class="sxs-lookup"><span data-stu-id="779fc-169">This account is debited when an invoice is posted against a deferred rent treatment lease, if the lease payment amount is more than the period's straight-line rent expense.</span></span> <span data-ttu-id="779fc-170">Se abona si el pago del arrendamiento es menor que el gasto de alquiler lineal del período.</span><span class="sxs-lookup"><span data-stu-id="779fc-170">It's credited if the lease payment is less than the period's straight-line rent expense.</span></span>

<span data-ttu-id="779fc-171">**Entradas de diario de ejemplo:** pago de arrendamiento (arrendamiento con tratamiento de arrendamiento diferido)</span><span class="sxs-lookup"><span data-stu-id="779fc-171">**Example journal entries:** Lease payment (deferred rent treatment lease)</span></span><br>
<span data-ttu-id="779fc-172">**Débito:** gastos de arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-172">**Debit:** Lease expense XXX</span></span><br>
<span data-ttu-id="779fc-173">**Crédito** pasivo de arrendamiento diferido XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-173">**Credit:** Deferred rent liability XXX</span></span><br>
<span data-ttu-id="779fc-174">**Crédito:** pagable a proveedores/pago por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-174">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="lease-expense"></a><span data-ttu-id="779fc-175">Gasto de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="779fc-175">Lease expense</span></span>

<span data-ttu-id="779fc-176">La cuenta se asocia con el gasto por arrendamiento si el arrendamiento se clasifica como arrendamiento con tratamiento de arrendamiento diferido.</span><span class="sxs-lookup"><span data-stu-id="779fc-176">The account is associated with the lease expense if the lease is classified as a deferred rent treatment lease.</span></span> <span data-ttu-id="779fc-177">Esta cuenta se adeuda cuando se contabiliza una factura contra un contrato de arrendamiento con tratamiento de arrendamiento diferido.</span><span class="sxs-lookup"><span data-stu-id="779fc-177">This account is debited when an invoice is posted against a deferred rent treatment lease.</span></span>

<span data-ttu-id="779fc-178">**Entradas de diario de ejemplo:** pago de arrendamiento (arrendamiento con tratamiento de arrendamiento diferido)</span><span class="sxs-lookup"><span data-stu-id="779fc-178">**Example journal entries:** Lease payment (deferred rent treatment lease)</span></span><br>
<span data-ttu-id="779fc-179">**Débito:** gastos de arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-179">**Debit:** Lease expense XXX</span></span><br>
<span data-ttu-id="779fc-180">**Crédito** pasivo de arrendamiento diferido XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-180">**Credit:** Deferred rent liability XXX</span></span><br>
<span data-ttu-id="779fc-181">**Crédito:** pagable a proveedores/pago por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-181">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="impairment-expense"></a><span data-ttu-id="779fc-182">Gasto de deterioro</span><span class="sxs-lookup"><span data-stu-id="779fc-182">Impairment expense</span></span>

<span data-ttu-id="779fc-183">La cuenta se registra en contra cuando se deteriora un contrato de arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="779fc-183">The account is posted against when a lease is impaired.</span></span> <span data-ttu-id="779fc-184">Esta cuenta se adeuda, mientras que la cuenta de activos por derecho de uso se abona directamente.</span><span class="sxs-lookup"><span data-stu-id="779fc-184">This account is debited, whereas the ROU asset account is directly credited.</span></span>

<span data-ttu-id="779fc-185">**Entradas de diario de ejemplo:** pago por arrendamiento</span><span class="sxs-lookup"><span data-stu-id="779fc-185">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="779fc-186">**Débito:** gasto de deterioro XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-186">**Debit:** Impairment expense XXX</span></span><br>
<span data-ttu-id="779fc-187">**Crédito:** activo por derecho de uso XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-187">**Credit:** ROU asset XXX</span></span>

## <a name="lease-payment"></a><span data-ttu-id="779fc-188">Pago por arrendamiento</span><span class="sxs-lookup"><span data-stu-id="779fc-188">Lease payment</span></span>

<span data-ttu-id="779fc-189">La cuenta se registra en contra si el parámetro **Pagar al proveedor** está desactivado.</span><span class="sxs-lookup"><span data-stu-id="779fc-189">The account is posted against if the **Pay to Vendor** parameter is turned off.</span></span> <span data-ttu-id="779fc-190">Esta cuenta se abona contra la de pagadero al proveedor si el parámetro está desactivado.</span><span class="sxs-lookup"><span data-stu-id="779fc-190">This account is credited instead of the vendor payable if the parameter is turned off.</span></span>

<span data-ttu-id="779fc-191">**Entradas de diario de ejemplo:** pago por arrendamiento</span><span class="sxs-lookup"><span data-stu-id="779fc-191">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="779fc-192">**Débito:** pasivo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-192">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="779fc-193">**Crédito:** pago de arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-193">**Credit:** Lease payment XXX</span></span>

## <a name="expense-type-postings"></a><span data-ttu-id="779fc-194">Registros de tipo de gasto</span><span class="sxs-lookup"><span data-stu-id="779fc-194">Expense type postings</span></span>

<span data-ttu-id="779fc-195">La cuenta que se selecciona para cada tipo de gasto se adeuda cuando se genera un pago para ese tipo de gasto.</span><span class="sxs-lookup"><span data-stu-id="779fc-195">The account that is selected for each expense type is debited when a payment for that expense type is generated.</span></span> <span data-ttu-id="779fc-196">Por ejemplo, la cuenta que se especifica para el tipo de gasto **Seguro** se carga cada vez que se crea una factura o un asiento de diario de pagos a partir de la programación de gastos a cargo del arrendatario en un arrendamiento de capital para gastos de seguro.</span><span class="sxs-lookup"><span data-stu-id="779fc-196">For example, the account that is specified for the **Insurance** expense type is debited whenever an invoice or payment journal entry is created from the executory cost schedule for insurance expense.</span></span>

<span data-ttu-id="779fc-197">**Entradas de diario de ejemplo:** pago por seguro</span><span class="sxs-lookup"><span data-stu-id="779fc-197">**Example journal entries:** Insurance payment</span></span><br>
<span data-ttu-id="779fc-198">**Débito:** cuenta de tipo de gasto de seguro XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-198">**Debit:** Insurance expense type account XXX</span></span><br>
<span data-ttu-id="779fc-199">**Crédito:** Cuenta de contrapartida XXX</span><span class="sxs-lookup"><span data-stu-id="779fc-199">**Credit:** Offset account XXX</span></span>

> [!NOTE]
> <span data-ttu-id="779fc-200">La cuenta de contrapartida se selecciona a nivel de arrendamiento en las líneas para el programa de pago de gastos a cargo del arrendatario en un arrendamiento de capital.</span><span class="sxs-lookup"><span data-stu-id="779fc-200">The offset account is selected at the lease level on the lines for the executory cost payment schedule.</span></span> <span data-ttu-id="779fc-201">Esta cuenta de contrapartida se puede asociar con el proveedor o con una cuenta contable.</span><span class="sxs-lookup"><span data-stu-id="779fc-201">This offset account can associated with the vendor, or with a ledger account.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
