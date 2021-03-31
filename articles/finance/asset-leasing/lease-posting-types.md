---
title: Tipos de registro de arrendamientos
description: Este tema describe los tipos de registro que se utilizan para transacciones de arrendamiento de activos.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9b7d8c545c1addaa570d54855bbad6c576783007
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5229511"
---
# <a name="lease-posting-types"></a><span data-ttu-id="b2dea-103">Tipos de registro de arrendamientos</span><span class="sxs-lookup"><span data-stu-id="b2dea-103">Lease posting types</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b2dea-104">Este tema describe los tipos de registro que se utilizan para transacciones de arrendamiento de activos.</span><span class="sxs-lookup"><span data-stu-id="b2dea-104">This topic describes the posting types that are used for asset leasing transactions.</span></span>

## <a name="lease-asset"></a><span data-ttu-id="b2dea-105">Activo de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="b2dea-105">Lease asset</span></span>

<span data-ttu-id="b2dea-106">La cuenta está asociada con el activo por derecho de uso (ROU).</span><span class="sxs-lookup"><span data-stu-id="b2dea-106">The account is associated with the right-of-use (ROU) asset.</span></span> <span data-ttu-id="b2dea-107">Esta cuenta se carga cuando un arrendamiento se reconoce inicialmente según los nuevos estándares de contabilidad de arrendamientos, el Tema de codificación de normas de contabilidad 842 (ASC 842) y la Norma Internacional de Información Financiera 16 (IFRS 16).</span><span class="sxs-lookup"><span data-stu-id="b2dea-107">This account is debited when a lease is initially recognized under the new lease accounting standards, Accounting Standards Codification Topic 842 (ASC 842) and International Financial Reporting Standard 16 (IFRS 16).</span></span> <span data-ttu-id="b2dea-108">Para un arrendamiento modificado, esta cuenta puede ser adeudada o abonada, dependiendo de si la modificación aumenta o disminuye el pasivo por arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="b2dea-108">For a modified lease, this account might be either debited or credited, depending on whether the modification increases or decreases the lease liability.</span></span>

<span data-ttu-id="b2dea-109">**Movimientos de diario de ejemplo:** reconocimiento inicial</span><span class="sxs-lookup"><span data-stu-id="b2dea-109">**Example journal entries:** Initial recognition</span></span><br>
<span data-ttu-id="b2dea-110">**Débito:** activo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-110">**Debit:** Lease asset XXX</span></span><br>
<span data-ttu-id="b2dea-111">**Crédito:** pasivo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-111">**Credit:** Lease liability XXX</span></span>

## <a name="lease-liability"></a><span data-ttu-id="b2dea-112">Pasivo por arrendamiento</span><span class="sxs-lookup"><span data-stu-id="b2dea-112">Lease liability</span></span>

<span data-ttu-id="b2dea-113">La cuenta está asociada con el pasivo por arrendamiento que ocurre cuando los pagos se descuentan según las nuevas normas IFRS 16 y ASC 842.</span><span class="sxs-lookup"><span data-stu-id="b2dea-113">The account is associated with the lease liability that occurs when payments are discounted under the new IFRS 16 and ASC 842 standards.</span></span> <span data-ttu-id="b2dea-114">Esta cuenta se acredita cuando un arrendamiento se reconoce inicialmente bajo las nuevas normas.</span><span class="sxs-lookup"><span data-stu-id="b2dea-114">This account is credited when a lease is initially recognized under the new standards.</span></span> <span data-ttu-id="b2dea-115">Se adeuda para los pagos por arrendamiento y se abona para los intereses acumulados.</span><span class="sxs-lookup"><span data-stu-id="b2dea-115">It's debited for lease payments and credited for interest accruals.</span></span>

<span data-ttu-id="b2dea-116">**Movimientos de diario de ejemplo:** reconocimiento inicial</span><span class="sxs-lookup"><span data-stu-id="b2dea-116">**Example journal entries:** Initial recognition</span></span><br>
<span data-ttu-id="b2dea-117">**Débito:** activo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-117">**Debit:** Lease asset XXX</span></span><br>
<span data-ttu-id="b2dea-118">**Crédito:** pasivo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-118">**Credit:** Lease liability XXX</span></span>

<span data-ttu-id="b2dea-119">**Entradas de diario de ejemplo:** intereses acumulados</span><span class="sxs-lookup"><span data-stu-id="b2dea-119">**Example journal entries:** Interest accrual</span></span><br>
<span data-ttu-id="b2dea-120">**Débito:** gasto por intereses XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-120">**Debit:** Interest expense XXX</span></span><br>
<span data-ttu-id="b2dea-121">**Crédito:** pasivo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-121">**Credit:** Lease liability XXX</span></span>

<span data-ttu-id="b2dea-122">**Entradas de diario de ejemplo:** pago por arrendamiento</span><span class="sxs-lookup"><span data-stu-id="b2dea-122">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="b2dea-123">**Débito:** pasivo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-123">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="b2dea-124">**Crédito:** pagable a proveedores/pago por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-124">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="short-term-lease-liability"></a><span data-ttu-id="b2dea-125">Pasivo por arrendamiento a corto plazo</span><span class="sxs-lookup"><span data-stu-id="b2dea-125">Short-term lease liability</span></span>

<span data-ttu-id="b2dea-126">La cuenta está asociada con el pasivo por arrendamiento a corto plazo cuando se contabiliza el asiento de diario de reclasificación del pasivo por arrendamiento a corto plazo.</span><span class="sxs-lookup"><span data-stu-id="b2dea-126">The account is associated with the short-term lease liability when the short-term lease liability reclass journal entry is posted.</span></span> <span data-ttu-id="b2dea-127">A esta cuenta se le abona el pasivo a corto plazo del programa de amortización el último día del mes.</span><span class="sxs-lookup"><span data-stu-id="b2dea-127">This account is credited for the short-term liability from the amortization schedule on the last day of the month.</span></span> <span data-ttu-id="b2dea-128">Sin embargo, la misma cantidad se carga el primer día del mes siguiente.</span><span class="sxs-lookup"><span data-stu-id="b2dea-128">However, the same amount is debited on the first day of the next month.</span></span>

<span data-ttu-id="b2dea-129">**Entradas de diario de ejemplo:** reclasificación del pasivo por arrendamiento a corto plazo</span><span class="sxs-lookup"><span data-stu-id="b2dea-129">**Example journal entries:** Short-term lease liability reclass</span></span><br>
<span data-ttu-id="b2dea-130">**Débito:** pasivo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-130">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="b2dea-131">**Crédito:** pasivo por arrendamiento a corto plazo XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-131">**Credit:** Short-term lease liability XXX</span></span><br>
<span data-ttu-id="b2dea-132">**Débito:** pasivo por arrendamiento a corto plazo XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-132">**Debit:** Short-term lease liability XXX</span></span><br>
<span data-ttu-id="b2dea-133">**Crédito:** pasivo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-133">**Credit:** Lease liability XXX</span></span>

## <a name="depreciation-expense"></a><span data-ttu-id="b2dea-134">Gasto de depreciación</span><span class="sxs-lookup"><span data-stu-id="b2dea-134">Depreciation expense</span></span>

<span data-ttu-id="b2dea-135">La cuenta está asociada con el gasto que está relacionado con la depreciación del activo por derecho de uso según IFRS 16, ASC 842 y arrendamientos financieros según IAS 17 y ASC 840.</span><span class="sxs-lookup"><span data-stu-id="b2dea-135">The account is associated with the expense that is related to the depreciation of the ROU asset under IFRS 16, ASC 842, and finance leases under IAS 17 and ASC 840.</span></span> <span data-ttu-id="b2dea-136">Esta cuenta se carga cuando un aactivo por derecho de uso se deprecia cada mes.</span><span class="sxs-lookup"><span data-stu-id="b2dea-136">This account is debited when an ROU asset is depreciated each month.</span></span>

<span data-ttu-id="b2dea-137">**Entradas de diario de ejemplo:** depreciación acumulada</span><span class="sxs-lookup"><span data-stu-id="b2dea-137">**Example journal entries:** Depreciation accrual</span></span><br>
<span data-ttu-id="b2dea-138">**Débito:** gasto de depreciación XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-138">**Debit:** Depreciation expense XXX</span></span><br>
<span data-ttu-id="b2dea-139">**Crédito** depreciación acumulada XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-139">**Credit:** Accumulated Depreciation XXX</span></span>

## <a name="gainloss-on-lease-modification"></a><span data-ttu-id="b2dea-140">Ganancias y pérdidas en modificación de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="b2dea-140">Gain/loss on lease modification</span></span>

<span data-ttu-id="b2dea-141">La cuenta está asociada con cualquier ganancia o pérdida que surja de las modificaciones del arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="b2dea-141">The account is associated with any gains or losses that arise from lease modifications.</span></span> <span data-ttu-id="b2dea-142">Puede surgir una ganancia durante una modificación de arrendamiento si la modificación disminuye el pasivo por arrendamiento en una cantidad que exceda el valor en libros del activo por derecho de uso.</span><span class="sxs-lookup"><span data-stu-id="b2dea-142">A gain might arise during a lease modification if the modification decreases the lease liability by an amount that exceeds the carrying value of the ROU asset.</span></span>

<span data-ttu-id="b2dea-143">Por ejemplo, un arrendamiento tiene un valor en libros actual del pasivo por arrendamiento de 150.000 $ y un valor en libros del activo por derecho de uso de 100.000 $.</span><span class="sxs-lookup"><span data-stu-id="b2dea-143">For example, a lease has a current carrying value of the lease liability of $150,000 and a carrying value of the ROU asset of $100,000.</span></span> <span data-ttu-id="b2dea-144">El arrendamiento se modifica y esta modificación produce un nuevo valor presente de los pagos mínimos futuros del arrendamiento (PVFMLP) de 40.000 $.</span><span class="sxs-lookup"><span data-stu-id="b2dea-144">The lease is modified, and this modification produces a new present value of the future minimum lease payments (PVFMLP) of $40,000.</span></span> <span data-ttu-id="b2dea-145">Por lo tanto, el pasivo del arrendamiento se cargará con 110.000 $ (150.000 $ - 40.000 $).</span><span class="sxs-lookup"><span data-stu-id="b2dea-145">Therefore, the lease liability will be debited by $110,000 ($150,000 – $40,000).</span></span> <span data-ttu-id="b2dea-146">Dado que el activo por derecho de uso es de solo 100.000 $, la disminución de 110.000 $ disminuirá el activo más allá de 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="b2dea-146">Because the ROU asset is only $100,000, the decrease of $110,000 will decrease the asset past 0 (zero).</span></span> <span data-ttu-id="b2dea-147">Por lo tanto, la guía contable establece que el resto debe registrarse en una cuenta de ganancias.</span><span class="sxs-lookup"><span data-stu-id="b2dea-147">Therefore, the accounting guidance states that the remainder should be booked to a gain account.</span></span> <span data-ttu-id="b2dea-148">En este caso, el movimiento final del diario será un adeudo al pasivo por arrendamiento por 110.000 $, un abono al activo por arrendamiento por 100.000 $ y un abono a la cuenta de ganancias por 10.000 $.</span><span class="sxs-lookup"><span data-stu-id="b2dea-148">In this case, the final journal entry will be a debit to the lease liability for $110,000, a credit to the lease asset for $100,000, and a credit to the gain account for $10,000.</span></span>

<span data-ttu-id="b2dea-149">**Entradas de diario de ejemplo:** modificación de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="b2dea-149">**Example journal entries:** Lease modification</span></span><br>
<span data-ttu-id="b2dea-150">**Débito:** pasivo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-150">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="b2dea-151">**Crédito:** activo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-151">**Credit:** Lease Asset XXX</span></span><br>
<span data-ttu-id="b2dea-152">**Crédito:** ganancia XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-152">**Credit:** Gain XXX</span></span>

## <a name="accumulated-depreciation"></a><span data-ttu-id="b2dea-153">Depreciación acumulada</span><span class="sxs-lookup"><span data-stu-id="b2dea-153">Accumulated depreciation</span></span>

<span data-ttu-id="b2dea-154">La cuenta está asociada con la cuenta enfrentada al activo del activo por derecho de uso.</span><span class="sxs-lookup"><span data-stu-id="b2dea-154">The account is associated with the contra-asset account of the ROU asset.</span></span> <span data-ttu-id="b2dea-155">Se abonará en esta cuenta cuando se registre un gasto de depreciación.</span><span class="sxs-lookup"><span data-stu-id="b2dea-155">This account is credited when a depreciation expense is posted.</span></span>

<span data-ttu-id="b2dea-156">**Entradas de diario de ejemplo:** depreciación acumulada</span><span class="sxs-lookup"><span data-stu-id="b2dea-156">**Example journal entries:** Depreciation accrual</span></span><br>
<span data-ttu-id="b2dea-157">**Débito:** gasto de depreciación XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-157">**Debit:** Depreciation expense XXX</span></span><br>
<span data-ttu-id="b2dea-158">**Crédito:** depreciación acumulada XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-158">**Credit:** Accumulated depreciation XXX</span></span>

## <a name="retained-earnings"></a><span data-ttu-id="b2dea-159">Ganancias retenidas</span><span class="sxs-lookup"><span data-stu-id="b2dea-159">Retained earnings</span></span>

<span data-ttu-id="b2dea-160">La cuenta que está asociada con los ingresos retenidos.</span><span class="sxs-lookup"><span data-stu-id="b2dea-160">The account is associated with retained earnings.</span></span> <span data-ttu-id="b2dea-161">Esta cuenta puede adeudarse o abonarse en un movimiento de diario de ajuste de transición utilizando el método retrospectivo completo o el método de opción A de recuperación acumulativa.</span><span class="sxs-lookup"><span data-stu-id="b2dea-161">This account might be either debited or credited in a transition adjustment journal entry by using the full retrospective method or the cumulative catch-up option A method.</span></span> <span data-ttu-id="b2dea-162">La diferencia entre el activo por derecho de uso inicial y el pasivo por arrendamiento se registra en los ingresos retenidos.</span><span class="sxs-lookup"><span data-stu-id="b2dea-162">The difference between the initial ROU asset and lease liability is booked to retained earnings.</span></span> <span data-ttu-id="b2dea-163">En casos raros, las ganancias retenidas también pueden verse afectadas durante la modificación del arrendamiento, si la clasificación de un arrendamiento se cambia de financiero a operativo para registrar un aumento o disminución del activo por derecho de uso para que sea igual al pasivo por arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="b2dea-163">In rare cases, the retained earnings might also be affected during lease modification, if the classification of a lease is changed from finance to operating to write the ROU asset up or down so that it equals the lease liability.</span></span>

<span data-ttu-id="b2dea-164">**Entradas de diario de ejemplo:** ajuste de transición (método de opción A de recuperación total retrospectiva o acumulativa)</span><span class="sxs-lookup"><span data-stu-id="b2dea-164">**Example journal entries:** Transition adjustment (full retrospective or cumulative catch-up option A method)</span></span><br>
<span data-ttu-id="b2dea-165">**Débito:** pasivo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-165">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="b2dea-166">**Crédito:** activo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-166">**Credit:** Lease asset XXX</span></span><br>
<span data-ttu-id="b2dea-167">**Crédito:** ingresos retenidos XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-167">**Credit:** Retained earnings XXX</span></span>

## <a name="variable-payment"></a><span data-ttu-id="b2dea-168">Pago variable</span><span class="sxs-lookup"><span data-stu-id="b2dea-168">Variable payment</span></span>

<span data-ttu-id="b2dea-169">La cuenta está asociada con los pagos de arrendamiento variables que se producen por una revalorización del índice en arrendamientos ASC 842, ASC 840 e IAS 17.</span><span class="sxs-lookup"><span data-stu-id="b2dea-169">The account is associated with variable lease payments that are produced by an index revaluation under ASC 842, ASC 840, and IAS 17 leases.</span></span> <span data-ttu-id="b2dea-170">En la programación de pagos de arrendamiento, los pagos variables se incluyen en la columna **Pago variable**.</span><span class="sxs-lookup"><span data-stu-id="b2dea-170">In the lease payment schedule, variable payments are included in the **Variable payment** column.</span></span> <span data-ttu-id="b2dea-171">Esta cuenta se carga cuando se crea una factura contra una línea de programación de pagos que contiene un pago variable.</span><span class="sxs-lookup"><span data-stu-id="b2dea-171">This account is debited when an invoice is created against a payment schedule line that contains a variable payment.</span></span>

<span data-ttu-id="b2dea-172">**Entradas de diario de ejemplo:** pago por arrendamiento</span><span class="sxs-lookup"><span data-stu-id="b2dea-172">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="b2dea-173">**Débito:** pasivo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-173">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="b2dea-174">**Débito:** pago variable XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-174">**Debit:** Variable payment XXX</span></span><br>
<span data-ttu-id="b2dea-175">**Crédito:** pagable a proveedores/pago por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-175">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="deferred-rent-asset-liability"></a><span data-ttu-id="b2dea-176">Activo de arrendamiento diferido (pasivo)</span><span class="sxs-lookup"><span data-stu-id="b2dea-176">Deferred rent asset (liability)</span></span>

<span data-ttu-id="b2dea-177">La cuenta está asociada con el activo o pasivo por arrendamiento diferido que se produce por un arrendamiento con tratamiento de arrendamiento diferido.</span><span class="sxs-lookup"><span data-stu-id="b2dea-177">The account is associated with the deferred rent asset or liability that is produced by a deferred rent treatment lease.</span></span> <span data-ttu-id="b2dea-178">Esta cuenta se adeuda cuando se contabiliza una factura contra un arrendamiento con tratamiento de arrendamiento diferido, si el importe del pago del arrendamiento es mayor que el gasto de alquiler lineal del período.</span><span class="sxs-lookup"><span data-stu-id="b2dea-178">This account is debited when an invoice is posted against a deferred rent treatment lease, if the lease payment amount is more than the period's straight-line rent expense.</span></span> <span data-ttu-id="b2dea-179">Se abona si el pago del arrendamiento es menor que el gasto de alquiler lineal del período.</span><span class="sxs-lookup"><span data-stu-id="b2dea-179">It's credited if the lease payment is less than the period's straight-line rent expense.</span></span>

<span data-ttu-id="b2dea-180">**Entradas de diario de ejemplo:** pago de arrendamiento (arrendamiento con tratamiento de arrendamiento diferido)</span><span class="sxs-lookup"><span data-stu-id="b2dea-180">**Example journal entries:** Lease payment (deferred rent treatment lease)</span></span><br>
<span data-ttu-id="b2dea-181">**Débito:** gastos de arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-181">**Debit:** Lease expense XXX</span></span><br>
<span data-ttu-id="b2dea-182">**Crédito** pasivo de arrendamiento diferido XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-182">**Credit:** Deferred rent liability XXX</span></span><br>
<span data-ttu-id="b2dea-183">**Crédito:** pagable a proveedores/pago por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-183">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="lease-expense"></a><span data-ttu-id="b2dea-184">Gasto de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="b2dea-184">Lease expense</span></span>

<span data-ttu-id="b2dea-185">La cuenta se asocia con el gasto por arrendamiento si el arrendamiento se clasifica como arrendamiento con tratamiento de arrendamiento diferido.</span><span class="sxs-lookup"><span data-stu-id="b2dea-185">The account is associated with the lease expense if the lease is classified as a deferred rent treatment lease.</span></span> <span data-ttu-id="b2dea-186">Esta cuenta se adeuda cuando se contabiliza una factura contra un contrato de arrendamiento con tratamiento de arrendamiento diferido.</span><span class="sxs-lookup"><span data-stu-id="b2dea-186">This account is debited when an invoice is posted against a deferred rent treatment lease.</span></span>

<span data-ttu-id="b2dea-187">**Entradas de diario de ejemplo:** pago de arrendamiento (arrendamiento con tratamiento de arrendamiento diferido)</span><span class="sxs-lookup"><span data-stu-id="b2dea-187">**Example journal entries:** Lease payment (deferred rent treatment lease)</span></span><br>
<span data-ttu-id="b2dea-188">**Débito:** gastos de arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-188">**Debit:** Lease expense XXX</span></span><br>
<span data-ttu-id="b2dea-189">**Crédito** pasivo de arrendamiento diferido XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-189">**Credit:** Deferred rent liability XXX</span></span><br>
<span data-ttu-id="b2dea-190">**Crédito:** pagable a proveedores/pago por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-190">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="impairment-expense"></a><span data-ttu-id="b2dea-191">Gasto de deterioro</span><span class="sxs-lookup"><span data-stu-id="b2dea-191">Impairment expense</span></span>

<span data-ttu-id="b2dea-192">La cuenta se registra en contra cuando se deteriora un contrato de arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="b2dea-192">The account is posted against when a lease is impaired.</span></span> <span data-ttu-id="b2dea-193">Esta cuenta se adeuda, mientras que la cuenta de activos por derecho de uso se abona directamente.</span><span class="sxs-lookup"><span data-stu-id="b2dea-193">This account is debited, whereas the ROU asset account is directly credited.</span></span>

<span data-ttu-id="b2dea-194">**Entradas de diario de ejemplo:** pago por arrendamiento</span><span class="sxs-lookup"><span data-stu-id="b2dea-194">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="b2dea-195">**Débito:** gasto de deterioro XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-195">**Debit:** Impairment expense XXX</span></span><br>
<span data-ttu-id="b2dea-196">**Crédito:** activo por derecho de uso XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-196">**Credit:** ROU asset XXX</span></span>

## <a name="lease-payment"></a><span data-ttu-id="b2dea-197">Pago por arrendamiento</span><span class="sxs-lookup"><span data-stu-id="b2dea-197">Lease payment</span></span>

<span data-ttu-id="b2dea-198">La cuenta se registra en contra si el parámetro **Pagar al proveedor** está desactivado.</span><span class="sxs-lookup"><span data-stu-id="b2dea-198">The account is posted against if the **Pay to Vendor** parameter is turned off.</span></span> <span data-ttu-id="b2dea-199">Esta cuenta se abona contra la de pagadero al proveedor si el parámetro está desactivado.</span><span class="sxs-lookup"><span data-stu-id="b2dea-199">This account is credited instead of the vendor payable if the parameter is turned off.</span></span>

<span data-ttu-id="b2dea-200">**Entradas de diario de ejemplo:** pago por arrendamiento</span><span class="sxs-lookup"><span data-stu-id="b2dea-200">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="b2dea-201">**Débito:** pasivo por arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-201">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="b2dea-202">**Crédito:** pago de arrendamiento XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-202">**Credit:** Lease payment XXX</span></span>

## <a name="expense-type-postings"></a><span data-ttu-id="b2dea-203">Registros de tipo de gasto</span><span class="sxs-lookup"><span data-stu-id="b2dea-203">Expense type postings</span></span>

<span data-ttu-id="b2dea-204">La cuenta que se selecciona para cada tipo de gasto se adeuda cuando se genera un pago para ese tipo de gasto.</span><span class="sxs-lookup"><span data-stu-id="b2dea-204">The account that is selected for each expense type is debited when a payment for that expense type is generated.</span></span> <span data-ttu-id="b2dea-205">Por ejemplo, la cuenta que se especifica para el tipo de gasto **Seguro** se carga cada vez que se crea una factura o un asiento de diario de pagos a partir de la programación de gastos a cargo del arrendatario en un arrendamiento de capital para gastos de seguro.</span><span class="sxs-lookup"><span data-stu-id="b2dea-205">For example, the account that is specified for the **Insurance** expense type is debited whenever an invoice or payment journal entry is created from the executory cost schedule for insurance expense.</span></span>

<span data-ttu-id="b2dea-206">**Entradas de diario de ejemplo:** pago por seguro</span><span class="sxs-lookup"><span data-stu-id="b2dea-206">**Example journal entries:** Insurance payment</span></span><br>
<span data-ttu-id="b2dea-207">**Débito:** cuenta de tipo de gasto de seguro XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-207">**Debit:** Insurance expense type account XXX</span></span><br>
<span data-ttu-id="b2dea-208">**Crédito:** Cuenta de contrapartida XXX</span><span class="sxs-lookup"><span data-stu-id="b2dea-208">**Credit:** Offset account XXX</span></span>

> [!NOTE]
> <span data-ttu-id="b2dea-209">La cuenta de contrapartida se selecciona a nivel de arrendamiento en las líneas para el programa de pago de gastos a cargo del arrendatario en un arrendamiento de capital.</span><span class="sxs-lookup"><span data-stu-id="b2dea-209">The offset account is selected at the lease level on the lines for the executory cost payment schedule.</span></span> <span data-ttu-id="b2dea-210">Esta cuenta de contrapartida se puede asociar con el proveedor o con una cuenta contable.</span><span class="sxs-lookup"><span data-stu-id="b2dea-210">This offset account can associated with the vendor, or with a ledger account.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]