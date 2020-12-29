---
title: Cálculo de costes generales
description: Este tema describe los procesos típicos para calcular y asignar costes generales.
author: AndersGirke
manager: AnnBe
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation, CAMOverheadRateCalculationJournalEntry, CAMFormulaAllocationBase
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 923e6e38a664e17ec3349d839c4b77ec903c5dc2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447715"
---
# <a name="overhead-calculation"></a><span data-ttu-id="402b1-103">Cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="402b1-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="402b1-104">Este tema describe los procesos típicos para calcular y asignar costes generales.</span><span class="sxs-lookup"><span data-stu-id="402b1-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="402b1-105">Definición del término</span><span class="sxs-lookup"><span data-stu-id="402b1-105">Term definition</span></span>
---------------

<span data-ttu-id="402b1-106">Los costes generales son costes que se contraen para dirigir un negocio, pero que no pueden ser atribuidos directamente a ninguna actividad empresarial, productos, o servicio específicos.</span><span class="sxs-lookup"><span data-stu-id="402b1-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="402b1-107">Los costes generales proporcionan un soporte fundamental a la generación de actividades rentables.</span><span class="sxs-lookup"><span data-stu-id="402b1-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="402b1-108">Algunos ejemplos de costes generales son:</span><span class="sxs-lookup"><span data-stu-id="402b1-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="402b1-109">Alquiler</span><span class="sxs-lookup"><span data-stu-id="402b1-109">Rent</span></span>
-   <span data-ttu-id="402b1-110">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-110">Electricity</span></span>
-   <span data-ttu-id="402b1-111">Sueldos administrativos</span><span class="sxs-lookup"><span data-stu-id="402b1-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="402b1-112">Visión general del cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="402b1-112">Overhead calculation overview</span></span>
<span data-ttu-id="402b1-113">El cálculo de costes generales ejecuta las directivas de contabilidad de costes en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="402b1-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="402b1-114">Puede calcular varias veces los costes generales del mismo período fiscal si se han cambiado las directivas de contabilidad de costes o se han detectado errores específicos.</span><span class="sxs-lookup"><span data-stu-id="402b1-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="402b1-115">Cada ejecución del cálculo de costes generales se almacena y recibe un identificador de versión único que permite comparar los cálculos de diferentes versiones.</span><span class="sxs-lookup"><span data-stu-id="402b1-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="402b1-116">Las entradas de costes que el cálculo de costes generales genera reciben una fecha de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="402b1-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="402b1-117">Esta fecha de contabilidad coincide con la fecha final del período fiscal que se usa en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="402b1-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="402b1-118">El identificador de versión único consiste en los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="402b1-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="402b1-119">Tipo de versión</span><span class="sxs-lookup"><span data-stu-id="402b1-119">Version type</span></span>
-   <span data-ttu-id="402b1-120">Fecha y hora</span><span class="sxs-lookup"><span data-stu-id="402b1-120">Date and time</span></span>
-   <span data-ttu-id="402b1-121">Libro mayor de contabilidad de costes</span><span class="sxs-lookup"><span data-stu-id="402b1-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="402b1-122">Ejercicio</span><span class="sxs-lookup"><span data-stu-id="402b1-122">Fiscal year</span></span>
-   <span data-ttu-id="402b1-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="402b1-123">Fiscal period</span></span>

<span data-ttu-id="402b1-124">El cálculo de costes generales se ejecuta independientemente de la versión.</span><span class="sxs-lookup"><span data-stu-id="402b1-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="402b1-125">Por lo tanto, puede calcular la versión de presupuesto antes que la versión real.</span><span class="sxs-lookup"><span data-stu-id="402b1-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="402b1-126">El cálculo de costes generales consta de cuatro pasos, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="402b1-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="402b1-127">En cada paso, se crea una cabecera de diario que tiene entradas del diario.</span><span class="sxs-lookup"><span data-stu-id="402b1-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="402b1-128">Esta cabecera de diario guarda los datos de entrada para cada paso de cálculo.</span><span class="sxs-lookup"><span data-stu-id="402b1-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="402b1-129">Las directivas y las reglas se aplican a cada línea de diario, y las entradas de coste se generan como resultado.</span><span class="sxs-lookup"><span data-stu-id="402b1-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="402b1-130">Por tanto, siempre se tiene rastreabilidad completa.</span><span class="sxs-lookup"><span data-stu-id="402b1-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="402b1-131">[![Cálculo de costes generales](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="402b1-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="402b1-132">Calcular y asignar costes generales de electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="402b1-133">En la contabilidad financiera, algunos costes, como la electricidad, se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="402b1-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="402b1-134">Por lo tanto, no se proporciona una visión de gestión detallada para la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="402b1-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="402b1-135">En contabilidad de costes, para proporcionar información de gestión correcta en todas las unidades y niveles organizativos, los costes deben fluir por las unidades organizativas.</span><span class="sxs-lookup"><span data-stu-id="402b1-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="402b1-136">Este flujo se debe basar en cualquier registro preciso de consumo o en una evaluación justa.</span><span class="sxs-lookup"><span data-stu-id="402b1-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="402b1-137">En la contabilidad general, un coste de la electricidad se puede registrar como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="402b1-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="402b1-138">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="402b1-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="402b1-139">Centro de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="402b1-140">Cuenta principal</span><span class="sxs-lookup"><span data-stu-id="402b1-140">Main account</span></span></th>
<th><span data-ttu-id="402b1-141">Importe en la divisa de contabilidad</span><span class="sxs-lookup"><span data-stu-id="402b1-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-142">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="402b1-143">CC099</span><span class="sxs-lookup"><span data-stu-id="402b1-143">CC099</span></span></td>
<td><span data-ttu-id="402b1-144">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="402b1-144">Default cost center</span></span></td>
<td><span data-ttu-id="402b1-145">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-145">10001</span></span></td>
<td><span data-ttu-id="402b1-146">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-146">Electricity</span></span></td>
<td><span data-ttu-id="402b1-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="402b1-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="402b1-148">Paso 1: Procese el cálculo del comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="402b1-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="402b1-149">De forma predeterminada, cuando las entradas de coste se importan de los datos de origen, reciben la clasificación de comportamiento del coste **Sin ordenar** en la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="402b1-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="402b1-150">Aplicando reglas de directivas de comportamiento de coste, puede reclasificar entradas de coste como **Coste fijo** o **Coste variable**.</span><span class="sxs-lookup"><span data-stu-id="402b1-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="402b1-151">Defina la regla de comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="402b1-151">Define the cost behavior rule</span></span>

<span data-ttu-id="402b1-152">En algunos casos, parte del coste es una cuota fija, y el coste pendiente se basa en el consumo.</span><span class="sxs-lookup"><span data-stu-id="402b1-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="402b1-153">Las facturas de electricidad coinciden a menudo con esta definición.</span><span class="sxs-lookup"><span data-stu-id="402b1-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="402b1-154">Tras pagar una cuota fija específica, paga el consumo por kilovatio-hora (Kwh).</span><span class="sxs-lookup"><span data-stu-id="402b1-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="402b1-155">Por ejemplo, si la cuota de coste fijo es de 1.000,00, la regla de comportamiento del coste se define como sigue:</span><span class="sxs-lookup"><span data-stu-id="402b1-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="402b1-156">Importe fijo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="402b1-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="402b1-157">0 &lt;= 1.000,00 = Fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="402b1-158">1.000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="402b1-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="402b1-159">Diario</span><span class="sxs-lookup"><span data-stu-id="402b1-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="402b1-160">Diario</span><span class="sxs-lookup"><span data-stu-id="402b1-160">Journal</span></span></th>
<th><span data-ttu-id="402b1-161">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="402b1-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="402b1-162">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="402b1-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="402b1-163">Versión</span><span class="sxs-lookup"><span data-stu-id="402b1-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-164">00001</span><span class="sxs-lookup"><span data-stu-id="402b1-164">00001</span></span></td>
<td><span data-ttu-id="402b1-165">Diario de cálculo de comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="402b1-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="402b1-166">Fiscal</span><span class="sxs-lookup"><span data-stu-id="402b1-166">Fiscal</span></span></td>
<td><span data-ttu-id="402b1-167">2017</span><span class="sxs-lookup"><span data-stu-id="402b1-167">2017</span></span></td>
<td><span data-ttu-id="402b1-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="402b1-168">Period 1</span></span></td>
<td><span data-ttu-id="402b1-169">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="402b1-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="402b1-170">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="402b1-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="402b1-171">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="402b1-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="402b1-172">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="402b1-173">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-173">Cost element</span></span></th>
<th><span data-ttu-id="402b1-174">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="402b1-174">Cost behavior</span></span></th>
<th><span data-ttu-id="402b1-175">Importe</span><span class="sxs-lookup"><span data-stu-id="402b1-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-176">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="402b1-177">CC099</span><span class="sxs-lookup"><span data-stu-id="402b1-177">CC099</span></span></td>
<td><span data-ttu-id="402b1-178">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="402b1-178">Default cost center</span></span></td>
<td><span data-ttu-id="402b1-179">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-179">10001</span></span></td>
<td><span data-ttu-id="402b1-180">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-180">Electricity</span></span></td>
<td><span data-ttu-id="402b1-181">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="402b1-181">Unclassified</span></span></td>
<td><span data-ttu-id="402b1-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="402b1-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="402b1-183">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="402b1-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="402b1-184">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="402b1-185">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-185">Cost element</span></span></th>
<th><span data-ttu-id="402b1-186">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="402b1-186">Cost behavior</span></span></th>
<th><span data-ttu-id="402b1-187">Importe</span><span class="sxs-lookup"><span data-stu-id="402b1-187">Amount</span></span></th>
<th><span data-ttu-id="402b1-188">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="402b1-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-189">CC099</span><span class="sxs-lookup"><span data-stu-id="402b1-189">CC099</span></span></td>
<td><span data-ttu-id="402b1-190">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="402b1-190">Default cost center</span></span></td>
<td><span data-ttu-id="402b1-191">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-191">10001</span></span></td>
<td><span data-ttu-id="402b1-192">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-192">Electricity</span></span></td>
<td><span data-ttu-id="402b1-193">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="402b1-193">Unclassified</span></span></td>
<td><span data-ttu-id="402b1-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="402b1-194">10,000.00</span></span></td>
<td><span data-ttu-id="402b1-195">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-196">CC099</span><span class="sxs-lookup"><span data-stu-id="402b1-196">CC099</span></span></td>
<td><span data-ttu-id="402b1-197">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="402b1-197">Default cost center</span></span></td>
<td><span data-ttu-id="402b1-198">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-198">10001</span></span></td>
<td><span data-ttu-id="402b1-199">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-199">Electricity</span></span></td>
<td><span data-ttu-id="402b1-200">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="402b1-200">Unclassified</span></span></td>
<td><span data-ttu-id="402b1-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="402b1-201">-10,000.00</span></span></td>
<td><span data-ttu-id="402b1-202">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-203">CC099</span><span class="sxs-lookup"><span data-stu-id="402b1-203">CC099</span></span></td>
<td><span data-ttu-id="402b1-204">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="402b1-204">Default cost center</span></span></td>
<td><span data-ttu-id="402b1-205">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-205">10001</span></span></td>
<td><span data-ttu-id="402b1-206">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-206">Electricity</span></span></td>
<td><span data-ttu-id="402b1-207">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-207">Fixed cost</span></span></td>
<td><span data-ttu-id="402b1-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="402b1-208">1,000.00</span></span></td>
<td><span data-ttu-id="402b1-209">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-210">CC099</span><span class="sxs-lookup"><span data-stu-id="402b1-210">CC099</span></span></td>
<td><span data-ttu-id="402b1-211">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="402b1-211">Default cost center</span></span></td>
<td><span data-ttu-id="402b1-212">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-212">10001</span></span></td>
<td><span data-ttu-id="402b1-213">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-213">Electricity</span></span></td>
<td><span data-ttu-id="402b1-214">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-214">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="402b1-215">9,000.00</span></span></td>
<td><span data-ttu-id="402b1-216">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="402b1-217">Para obtener más información, consulte [Crear y asignar una directiva de comportamiento de costes a una unidad de control de costes](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="402b1-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="402b1-218">Paso 2: Procese el cálculo de distribución de costes</span><span class="sxs-lookup"><span data-stu-id="402b1-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="402b1-219">La distribución de costes se usa para redistribuir costes desde un objeto de coste a uno o más objetos de coste aplicando una base relevante de la asignación.</span><span class="sxs-lookup"><span data-stu-id="402b1-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="402b1-220">La distribución de costes y la asignación de costes difieren en que la distribución de costes siempre se produce en el nivel de elemento de costes principal del coste original.</span><span class="sxs-lookup"><span data-stu-id="402b1-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="402b1-221">Defina la regla de distribución del coste</span><span class="sxs-lookup"><span data-stu-id="402b1-221">Define the cost distribution rule</span></span>

<span data-ttu-id="402b1-222">En la contabilidad financiera, los costes de electricidad se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="402b1-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="402b1-223">En contabilidad de costes, este método no es suficientemente detallado.</span><span class="sxs-lookup"><span data-stu-id="402b1-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="402b1-224">El coste variable debe distribuirse a los objetos individuales de coste aplicando una base justa.</span><span class="sxs-lookup"><span data-stu-id="402b1-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="402b1-225">La base de asignación más lógica es el consumo de electricidad (Kwh).</span><span class="sxs-lookup"><span data-stu-id="402b1-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="402b1-226">Se crea un miembro de dimensión estadística que se denomina Electricity, y se registra el consumo de electricidad.</span><span class="sxs-lookup"><span data-stu-id="402b1-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="402b1-227">De forma predeterminada, todos los miembros de dimensión estadísticos estarán disponibles como bases de asignación.</span><span class="sxs-lookup"><span data-stu-id="402b1-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="402b1-228">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-228">Cost object</span></span></th>
<th><span data-ttu-id="402b1-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="402b1-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-230">CC001</span><span class="sxs-lookup"><span data-stu-id="402b1-230">CC001</span></span></td>
<td><span data-ttu-id="402b1-231">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="402b1-231">HR</span></span></td>
<td><span data-ttu-id="402b1-232">1.000</span><span class="sxs-lookup"><span data-stu-id="402b1-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-233">CC002</span><span class="sxs-lookup"><span data-stu-id="402b1-233">CC002</span></span></td>
<td><span data-ttu-id="402b1-234">Finanzas</span><span class="sxs-lookup"><span data-stu-id="402b1-234">Finance</span></span></td>
<td><span data-ttu-id="402b1-235">6.000</span><span class="sxs-lookup"><span data-stu-id="402b1-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-236">CC003</span><span class="sxs-lookup"><span data-stu-id="402b1-236">CC003</span></span></td>
<td><span data-ttu-id="402b1-237">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="402b1-237">Assembly</span></span></td>
<td><span data-ttu-id="402b1-238">0</span><span class="sxs-lookup"><span data-stu-id="402b1-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="402b1-239">La tabla siguiente muestra el resultado cuando se aplica el consumo de electricidad como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="402b1-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="402b1-240">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-240">Cost object</span></span></th>
<th><span data-ttu-id="402b1-241">Magnitud</span><span class="sxs-lookup"><span data-stu-id="402b1-241">Magnitude</span></span></th>
<th><span data-ttu-id="402b1-242">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="402b1-242">Allocation factor</span></span></th>
<th><span data-ttu-id="402b1-243">Importe</span><span class="sxs-lookup"><span data-stu-id="402b1-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-244">CC001</span><span class="sxs-lookup"><span data-stu-id="402b1-244">CC001</span></span></td>
<td><span data-ttu-id="402b1-245">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="402b1-245">HR</span></span></td>
<td><span data-ttu-id="402b1-246">1.000</span><span class="sxs-lookup"><span data-stu-id="402b1-246">1,000</span></span></td>
<td><span data-ttu-id="402b1-247">(1.000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="402b1-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="402b1-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="402b1-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-249">CC002</span><span class="sxs-lookup"><span data-stu-id="402b1-249">CC002</span></span></td>
<td><span data-ttu-id="402b1-250">Finanzas</span><span class="sxs-lookup"><span data-stu-id="402b1-250">Finance</span></span></td>
<td><span data-ttu-id="402b1-251">6.000</span><span class="sxs-lookup"><span data-stu-id="402b1-251">6,000</span></span></td>
<td><span data-ttu-id="402b1-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="402b1-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="402b1-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="402b1-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-254">CC003</span><span class="sxs-lookup"><span data-stu-id="402b1-254">CC003</span></span></td>
<td><span data-ttu-id="402b1-255">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="402b1-255">Assembly</span></span></td>
<td><span data-ttu-id="402b1-256">0</span><span class="sxs-lookup"><span data-stu-id="402b1-256">0</span></span></td>
<td><span data-ttu-id="402b1-257">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="402b1-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="402b1-258">0,00</span><span class="sxs-lookup"><span data-stu-id="402b1-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="402b1-259">El coste fijo debe distribuirse uniformemente a los objetos individuales de costes que han consumido electricidad.</span><span class="sxs-lookup"><span data-stu-id="402b1-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="402b1-260">Puede obtener este resultado usando el miembro de dimensión estadístico de electricidad en una base de asignación de la fórmula: (Electricidad &gt; 0,00) La tabla siguiente muestra el resultado cuando el consumo de electricidad se aplica como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="402b1-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="402b1-261">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-261">Cost object</span></span></th>
<th><span data-ttu-id="402b1-262">Fórmula</span><span class="sxs-lookup"><span data-stu-id="402b1-262">Formula</span></span></th>
<th><span data-ttu-id="402b1-263">Magnitud</span><span class="sxs-lookup"><span data-stu-id="402b1-263">Magnitude</span></span></th>
<th><span data-ttu-id="402b1-264">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="402b1-264">Allocation factor</span></span></th>
<th><span data-ttu-id="402b1-265">Importe</span><span class="sxs-lookup"><span data-stu-id="402b1-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-266">CC001</span><span class="sxs-lookup"><span data-stu-id="402b1-266">CC001</span></span></td>
<td><span data-ttu-id="402b1-267">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="402b1-267">HR</span></span></td>
<td><span data-ttu-id="402b1-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="402b1-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="402b1-269">1</span><span class="sxs-lookup"><span data-stu-id="402b1-269">1</span></span></td>
<td><span data-ttu-id="402b1-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="402b1-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="402b1-271">500,00</span><span class="sxs-lookup"><span data-stu-id="402b1-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-272">CC002</span><span class="sxs-lookup"><span data-stu-id="402b1-272">CC002</span></span></td>
<td><span data-ttu-id="402b1-273">Finanzas</span><span class="sxs-lookup"><span data-stu-id="402b1-273">Finance</span></span></td>
<td><span data-ttu-id="402b1-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="402b1-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="402b1-275">1</span><span class="sxs-lookup"><span data-stu-id="402b1-275">1</span></span></td>
<td><span data-ttu-id="402b1-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="402b1-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="402b1-277">500,00</span><span class="sxs-lookup"><span data-stu-id="402b1-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-278">CC003</span><span class="sxs-lookup"><span data-stu-id="402b1-278">CC003</span></span></td>
<td><span data-ttu-id="402b1-279">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="402b1-279">Assembly</span></span></td>
<td><span data-ttu-id="402b1-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="402b1-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="402b1-281">0</span><span class="sxs-lookup"><span data-stu-id="402b1-281">0</span></span></td>
<td><span data-ttu-id="402b1-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="402b1-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="402b1-283">0,00</span><span class="sxs-lookup"><span data-stu-id="402b1-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="402b1-284">Diario</span><span class="sxs-lookup"><span data-stu-id="402b1-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="402b1-285">Diario</span><span class="sxs-lookup"><span data-stu-id="402b1-285">Journal</span></span></th>
<th><span data-ttu-id="402b1-286">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="402b1-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="402b1-287">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="402b1-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="402b1-288">Versión</span><span class="sxs-lookup"><span data-stu-id="402b1-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-289">00002</span><span class="sxs-lookup"><span data-stu-id="402b1-289">00002</span></span></td>
<td><span data-ttu-id="402b1-290">Diario de cálculo de la distribución de costes</span><span class="sxs-lookup"><span data-stu-id="402b1-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="402b1-291">Fiscal</span><span class="sxs-lookup"><span data-stu-id="402b1-291">Fiscal</span></span></td>
<td><span data-ttu-id="402b1-292">2017</span><span class="sxs-lookup"><span data-stu-id="402b1-292">2017</span></span></td>
<td><span data-ttu-id="402b1-293">Período 1</span><span class="sxs-lookup"><span data-stu-id="402b1-293">Period 1</span></span></td>
<td><span data-ttu-id="402b1-294">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="402b1-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="402b1-295">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="402b1-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="402b1-296">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="402b1-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="402b1-297">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="402b1-298">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-298">Cost element</span></span></th>
<th><span data-ttu-id="402b1-299">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="402b1-299">Cost behavior</span></span></th>
<th><span data-ttu-id="402b1-300">Importe</span><span class="sxs-lookup"><span data-stu-id="402b1-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-301">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="402b1-302">CC099</span><span class="sxs-lookup"><span data-stu-id="402b1-302">CC099</span></span></td>
<td><span data-ttu-id="402b1-303">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="402b1-303">Default cost center</span></span></td>
<td><span data-ttu-id="402b1-304">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-304">10001</span></span></td>
<td><span data-ttu-id="402b1-305">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-305">Electricity</span></span></td>
<td><span data-ttu-id="402b1-306">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-306">Fixed cost</span></span></td>
<td><span data-ttu-id="402b1-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="402b1-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-308">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="402b1-309">CC099</span><span class="sxs-lookup"><span data-stu-id="402b1-309">CC099</span></span></td>
<td><span data-ttu-id="402b1-310">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="402b1-310">Default cost center</span></span></td>
<td><span data-ttu-id="402b1-311">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-311">10001</span></span></td>
<td><span data-ttu-id="402b1-312">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-312">Electricity</span></span></td>
<td><span data-ttu-id="402b1-313">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-313">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-314">9.000,00</span><span class="sxs-lookup"><span data-stu-id="402b1-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="402b1-315">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="402b1-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="402b1-316">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="402b1-317">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-317">Cost element</span></span></th>
<th><span data-ttu-id="402b1-318">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="402b1-318">Cost behavior</span></span></th>
<th><span data-ttu-id="402b1-319">Importe</span><span class="sxs-lookup"><span data-stu-id="402b1-319">Amount</span></span></th>
<th><span data-ttu-id="402b1-320">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="402b1-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-321">CC099</span><span class="sxs-lookup"><span data-stu-id="402b1-321">CC099</span></span></td>
<td><span data-ttu-id="402b1-322">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="402b1-322">Default cost center</span></span></td>
<td><span data-ttu-id="402b1-323">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-323">10001</span></span></td>
<td><span data-ttu-id="402b1-324">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-324">Electricity</span></span></td>
<td><span data-ttu-id="402b1-325">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-325">Fixed cost</span></span></td>
<td><span data-ttu-id="402b1-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="402b1-326">-1,000.00</span></span></td>
<td><span data-ttu-id="402b1-327">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-328">CC001</span><span class="sxs-lookup"><span data-stu-id="402b1-328">CC001</span></span></td>
<td><span data-ttu-id="402b1-329">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="402b1-329">HR</span></span></td>
<td><span data-ttu-id="402b1-330">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-330">10001</span></span></td>
<td><span data-ttu-id="402b1-331">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-331">Electricity</span></span></td>
<td><span data-ttu-id="402b1-332">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-332">Fixed cost</span></span></td>
<td><span data-ttu-id="402b1-333">500,00</span><span class="sxs-lookup"><span data-stu-id="402b1-333">500.00</span></span></td>
<td><span data-ttu-id="402b1-334">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-335">CC002</span><span class="sxs-lookup"><span data-stu-id="402b1-335">CC002</span></span></td>
<td><span data-ttu-id="402b1-336">Finanzas</span><span class="sxs-lookup"><span data-stu-id="402b1-336">Finance</span></span></td>
<td><span data-ttu-id="402b1-337">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-337">10001</span></span></td>
<td><span data-ttu-id="402b1-338">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-338">Electricity</span></span></td>
<td><span data-ttu-id="402b1-339">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-339">Fixed cost</span></span></td>
<td><span data-ttu-id="402b1-340">500,00</span><span class="sxs-lookup"><span data-stu-id="402b1-340">500.00</span></span></td>
<td><span data-ttu-id="402b1-341">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-342">CC099</span><span class="sxs-lookup"><span data-stu-id="402b1-342">CC099</span></span></td>
<td><span data-ttu-id="402b1-343">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="402b1-343">Default cost center</span></span></td>
<td><span data-ttu-id="402b1-344">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-344">10001</span></span></td>
<td><span data-ttu-id="402b1-345">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-345">Electricity</span></span></td>
<td><span data-ttu-id="402b1-346">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-346">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="402b1-347">-9,000.00</span></span></td>
<td><span data-ttu-id="402b1-348">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-349">CC001</span><span class="sxs-lookup"><span data-stu-id="402b1-349">CC001</span></span></td>
<td><span data-ttu-id="402b1-350">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="402b1-350">HR</span></span></td>
<td><span data-ttu-id="402b1-351">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-351">10001</span></span></td>
<td><span data-ttu-id="402b1-352">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-352">Electricity</span></span></td>
<td><span data-ttu-id="402b1-353">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-353">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="402b1-354">1,285.71</span></span></td>
<td><span data-ttu-id="402b1-355">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-356">CC002</span><span class="sxs-lookup"><span data-stu-id="402b1-356">CC002</span></span></td>
<td><span data-ttu-id="402b1-357">Finanzas</span><span class="sxs-lookup"><span data-stu-id="402b1-357">Finance</span></span></td>
<td><span data-ttu-id="402b1-358">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-358">10001</span></span></td>
<td><span data-ttu-id="402b1-359">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-359">Electricity</span></span></td>
<td><span data-ttu-id="402b1-360">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-360">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="402b1-361">7,714.29</span></span></td>
<td><span data-ttu-id="402b1-362">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="402b1-363">Para obtener más información, consulte [Crear y asignar una directiva de distribución de costes a una unidad de control de costes](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="402b1-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="402b1-364">Paso 3: Procese el cálculo de las tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="402b1-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="402b1-365">La tasa de costes generales se usa para cargar uno o varios objetos de coste específicos.</span><span class="sxs-lookup"><span data-stu-id="402b1-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="402b1-366">El cargo se basa en un índice de coste predeterminado y la magnitud de la base de asignación asignada.</span><span class="sxs-lookup"><span data-stu-id="402b1-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="402b1-367">Defina la tasa de costes generales</span><span class="sxs-lookup"><span data-stu-id="402b1-367">Define the overhead rate</span></span>

<span data-ttu-id="402b1-368">El objeto de coste CC001 HR contribuye a un conjunto de proyectos internos.</span><span class="sxs-lookup"><span data-stu-id="402b1-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="402b1-369">Se crea un miembro de dimensión estadística que se denomina proyectos HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="402b1-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="402b1-370">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-370">Cost object</span></span></th>
<th><span data-ttu-id="402b1-371">Horas</span><span class="sxs-lookup"><span data-stu-id="402b1-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-372">Proy 1</span><span class="sxs-lookup"><span data-stu-id="402b1-372">Proj 1</span></span></td>
<td><span data-ttu-id="402b1-373">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="402b1-373">Project 1</span></span></td>
<td><span data-ttu-id="402b1-374">3</span><span class="sxs-lookup"><span data-stu-id="402b1-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-375">Proy 2</span><span class="sxs-lookup"><span data-stu-id="402b1-375">Proj 2</span></span></td>
<td><span data-ttu-id="402b1-376">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="402b1-376">Project 2</span></span></td>
<td><span data-ttu-id="402b1-377">1</span><span class="sxs-lookup"><span data-stu-id="402b1-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="402b1-378">Una tasa de coste predeterminada para la contribución de los proyectos de coste se ha definido.</span><span class="sxs-lookup"><span data-stu-id="402b1-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="402b1-379">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-379">Cost object</span></span></th>
<th><span data-ttu-id="402b1-380">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-380">Cost element</span></span></th>
<th><span data-ttu-id="402b1-381">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="402b1-381">Cost behavior</span></span></th>
<th><span data-ttu-id="402b1-382">Unidades</span><span class="sxs-lookup"><span data-stu-id="402b1-382">Units</span></span></th>
<th><span data-ttu-id="402b1-383">Índice</span><span class="sxs-lookup"><span data-stu-id="402b1-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-384">CC001</span><span class="sxs-lookup"><span data-stu-id="402b1-384">CC001</span></span></td>
<td><span data-ttu-id="402b1-385">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="402b1-385">HR</span></span></td>
<td><span data-ttu-id="402b1-386">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-386">10001</span></span></td>
<td><span data-ttu-id="402b1-387">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-387">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-388">1</span><span class="sxs-lookup"><span data-stu-id="402b1-388">1</span></span></td>
<td><span data-ttu-id="402b1-389">10</span><span class="sxs-lookup"><span data-stu-id="402b1-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="402b1-390">La tabla siguiente muestra el resultado cuando los proyectos HR se aplican como base de la asignación.</span><span class="sxs-lookup"><span data-stu-id="402b1-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="402b1-391">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-391">Cost object</span></span></th>
<th><span data-ttu-id="402b1-392">Magnitud</span><span class="sxs-lookup"><span data-stu-id="402b1-392">Magnitude</span></span></th>
<th><span data-ttu-id="402b1-393">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-393">Cost element</span></span></th>
<th><span data-ttu-id="402b1-394">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="402b1-394">Allocation factor</span></span></th>
<th><span data-ttu-id="402b1-395">Importe</span><span class="sxs-lookup"><span data-stu-id="402b1-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-396">Proy 1</span><span class="sxs-lookup"><span data-stu-id="402b1-396">Proj 1</span></span></td>
<td><span data-ttu-id="402b1-397">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="402b1-397">Project 1</span></span></td>
<td><span data-ttu-id="402b1-398">3</span><span class="sxs-lookup"><span data-stu-id="402b1-398">3</span></span></td>
<td><span data-ttu-id="402b1-399">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-399">10001</span></span></td>
<td><span data-ttu-id="402b1-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="402b1-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="402b1-401">30,00</span><span class="sxs-lookup"><span data-stu-id="402b1-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-402">Proy 2</span><span class="sxs-lookup"><span data-stu-id="402b1-402">Proj 2</span></span></td>
<td><span data-ttu-id="402b1-403">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="402b1-403">Project 2</span></span></td>
<td><span data-ttu-id="402b1-404">1</span><span class="sxs-lookup"><span data-stu-id="402b1-404">1</span></span></td>
<td><span data-ttu-id="402b1-405">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-405">10001</span></span></td>
<td><span data-ttu-id="402b1-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="402b1-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="402b1-407">10,00</span><span class="sxs-lookup"><span data-stu-id="402b1-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="402b1-408">Diario</span><span class="sxs-lookup"><span data-stu-id="402b1-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="402b1-409">Diario</span><span class="sxs-lookup"><span data-stu-id="402b1-409">Journal</span></span></th>
<th><span data-ttu-id="402b1-410">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="402b1-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="402b1-411">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="402b1-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="402b1-412">Versión</span><span class="sxs-lookup"><span data-stu-id="402b1-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-413">00003</span><span class="sxs-lookup"><span data-stu-id="402b1-413">00003</span></span></td>
<td><span data-ttu-id="402b1-414">Diario de cálculo de tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="402b1-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="402b1-415">Fiscal</span><span class="sxs-lookup"><span data-stu-id="402b1-415">Fiscal</span></span></td>
<td><span data-ttu-id="402b1-416">2017</span><span class="sxs-lookup"><span data-stu-id="402b1-416">2017</span></span></td>
<td><span data-ttu-id="402b1-417">Período 1</span><span class="sxs-lookup"><span data-stu-id="402b1-417">Period 1</span></span></td>
<td><span data-ttu-id="402b1-418">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="402b1-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="402b1-419">Entradas de diario (entradas de diario para cálculo de tasas de costes generales)</span><span class="sxs-lookup"><span data-stu-id="402b1-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="402b1-420">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="402b1-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="402b1-421">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-421">Cost object</span></span></th>
<th><span data-ttu-id="402b1-422">Magnitud</span><span class="sxs-lookup"><span data-stu-id="402b1-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-423">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="402b1-424">Proy 1</span><span class="sxs-lookup"><span data-stu-id="402b1-424">Proj 1</span></span></td>
<td><span data-ttu-id="402b1-425">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="402b1-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="402b1-426">3,00</span><span class="sxs-lookup"><span data-stu-id="402b1-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-427">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="402b1-428">Proy 2</span><span class="sxs-lookup"><span data-stu-id="402b1-428">Proj 2</span></span></td>
<td><span data-ttu-id="402b1-429">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="402b1-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="402b1-430">1,00</span><span class="sxs-lookup"><span data-stu-id="402b1-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="402b1-431">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="402b1-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="402b1-432">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="402b1-433">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-433">Cost element</span></span></th>
<th><span data-ttu-id="402b1-434">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="402b1-434">Cost behavior</span></span></th>
<th><span data-ttu-id="402b1-435">Importe</span><span class="sxs-lookup"><span data-stu-id="402b1-435">Amount</span></span></th>
<th><span data-ttu-id="402b1-436">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="402b1-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="402b1-437">CC0001</span></span></td>
<td><span data-ttu-id="402b1-438">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="402b1-438">HR</span></span></td>
<td><span data-ttu-id="402b1-439">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-439">10001</span></span></td>
<td><span data-ttu-id="402b1-440">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-440">Electricity</span></span></td>
<td><span data-ttu-id="402b1-441">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-441">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="402b1-442">-30.00</span></span></td>
<td><span data-ttu-id="402b1-443">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-444">Proy 1</span><span class="sxs-lookup"><span data-stu-id="402b1-444">Proj 1</span></span></td>
<td><span data-ttu-id="402b1-445">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="402b1-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="402b1-446">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-446">10001</span></span></td>
<td><span data-ttu-id="402b1-447">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-447">Electricity</span></span></td>
<td><span data-ttu-id="402b1-448">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-448">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-449">30,00</span><span class="sxs-lookup"><span data-stu-id="402b1-449">30.00</span></span></td>
<td><span data-ttu-id="402b1-450">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-451">CC001</span><span class="sxs-lookup"><span data-stu-id="402b1-451">CC001</span></span></td>
<td><span data-ttu-id="402b1-452">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="402b1-452">HR</span></span></td>
<td><span data-ttu-id="402b1-453">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-453">10001</span></span></td>
<td><span data-ttu-id="402b1-454">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-454">Electricity</span></span></td>
<td><span data-ttu-id="402b1-455">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-455">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="402b1-456">-10.00</span></span></td>
<td><span data-ttu-id="402b1-457">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-458">Proy 2</span><span class="sxs-lookup"><span data-stu-id="402b1-458">Proj 2</span></span></td>
<td><span data-ttu-id="402b1-459">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="402b1-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="402b1-460">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-460">10001</span></span></td>
<td><span data-ttu-id="402b1-461">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-461">Electricity</span></span></td>
<td><span data-ttu-id="402b1-462">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-462">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-463">10,00</span><span class="sxs-lookup"><span data-stu-id="402b1-463">10.00</span></span></td>
<td><span data-ttu-id="402b1-464">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="402b1-465">Para obtener más información, consulte [Realizar cálculo de costes generales](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="402b1-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="402b1-466">Paso 4: Procese el cálculo de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="402b1-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="402b1-467">La asignación es utilizada para asignar el saldo de un objeto de coste a otros objetos de coste aplicando una base de asignación.</span><span class="sxs-lookup"><span data-stu-id="402b1-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="402b1-468">Finance admite el método de asignación recíproco.</span><span class="sxs-lookup"><span data-stu-id="402b1-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="402b1-469">En el método de asignación recíproco, se reconocen completamente los servicios mutuos que los objetos de coste auxiliar intercambian.</span><span class="sxs-lookup"><span data-stu-id="402b1-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="402b1-470">El sistema determina automáticamente el orden correcto para realizar las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="402b1-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="402b1-471">El saldo de un objeto de coste se asigna según una única base de asignación.</span><span class="sxs-lookup"><span data-stu-id="402b1-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="402b1-472">Las asignaciones entre dimensiones de objetos de coste y sus miembros respectivos se admiten.</span><span class="sxs-lookup"><span data-stu-id="402b1-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="402b1-473">El orden de asignación se controla por unidad de control de costes.</span><span class="sxs-lookup"><span data-stu-id="402b1-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="402b1-474">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="402b1-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="402b1-475">Defina la asignación de costes</span><span class="sxs-lookup"><span data-stu-id="402b1-475">Define the cost allocation</span></span>

<span data-ttu-id="402b1-476">A continuación se indica un ejemplo sencillo que explica cómo puede realizar el seguimiento del flujo de coste.</span><span class="sxs-lookup"><span data-stu-id="402b1-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="402b1-477">El objeto de coste CC001 HR contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="402b1-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="402b1-478">Se crea un miembro de dimensión estadística que se denomina servicios HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="402b1-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="402b1-479">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-479">Cost object</span></span></th>
<th><span data-ttu-id="402b1-480">Servicios HR</span><span class="sxs-lookup"><span data-stu-id="402b1-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-481">CC002</span><span class="sxs-lookup"><span data-stu-id="402b1-481">CC002</span></span></td>
<td><span data-ttu-id="402b1-482">Finanzas</span><span class="sxs-lookup"><span data-stu-id="402b1-482">Finance</span></span></td>
<td><span data-ttu-id="402b1-483">35</span><span class="sxs-lookup"><span data-stu-id="402b1-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-484">CC003</span><span class="sxs-lookup"><span data-stu-id="402b1-484">CC003</span></span></td>
<td><span data-ttu-id="402b1-485">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="402b1-485">Assembly</span></span></td>
<td><span data-ttu-id="402b1-486">55</span><span class="sxs-lookup"><span data-stu-id="402b1-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-487">CC004</span><span class="sxs-lookup"><span data-stu-id="402b1-487">CC004</span></span></td>
<td><span data-ttu-id="402b1-488">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="402b1-488">Packaging</span></span></td>
<td><span data-ttu-id="402b1-489">10</span><span class="sxs-lookup"><span data-stu-id="402b1-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="402b1-490">El objeto de coste CC002 Finanzas contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="402b1-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="402b1-491">Se crea un miembro de dimensión estadística que se denomina Finanzas para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="402b1-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="402b1-492">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-492">Cost object</span></span></th>
<th><span data-ttu-id="402b1-493">Servicios financieros</span><span class="sxs-lookup"><span data-stu-id="402b1-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-494">CC003</span><span class="sxs-lookup"><span data-stu-id="402b1-494">CC003</span></span></td>
<td><span data-ttu-id="402b1-495">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="402b1-495">Assembly</span></span></td>
<td><span data-ttu-id="402b1-496">65</span><span class="sxs-lookup"><span data-stu-id="402b1-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-497">CC004</span><span class="sxs-lookup"><span data-stu-id="402b1-497">CC004</span></span></td>
<td><span data-ttu-id="402b1-498">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="402b1-498">Packaging</span></span></td>
<td><span data-ttu-id="402b1-499">35</span><span class="sxs-lookup"><span data-stu-id="402b1-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="402b1-500">El objeto de coste CC003 Asamblea contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="402b1-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="402b1-501">Se crea un miembro de dimensión estadística que se denomina servicios de Asamblea para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="402b1-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="402b1-502">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-502">Cost object</span></span></th>
<th><span data-ttu-id="402b1-503">Servicios de la asamblea (horas)</span><span class="sxs-lookup"><span data-stu-id="402b1-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="402b1-504">Prod 1</span></span></td>
<td><span data-ttu-id="402b1-505">Producto 1</span><span class="sxs-lookup"><span data-stu-id="402b1-505">Product 1</span></span></td>
<td><span data-ttu-id="402b1-506">60</span><span class="sxs-lookup"><span data-stu-id="402b1-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="402b1-507">Prod 2</span></span></td>
<td><span data-ttu-id="402b1-508">Producto 2</span><span class="sxs-lookup"><span data-stu-id="402b1-508">Product 2</span></span></td>
<td><span data-ttu-id="402b1-509">20</span><span class="sxs-lookup"><span data-stu-id="402b1-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="402b1-510">El objeto de coste CC004 Embalaje contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="402b1-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="402b1-511">Se crea un miembro de dimensión estadística que se denomina servicios de Embalaje para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="402b1-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="402b1-512">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-512">Cost object</span></span></th>
<th><span data-ttu-id="402b1-513">Servicios de embalaje (horas)</span><span class="sxs-lookup"><span data-stu-id="402b1-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="402b1-514">Prod 1</span></span></td>
<td><span data-ttu-id="402b1-515">Producto 1</span><span class="sxs-lookup"><span data-stu-id="402b1-515">Product 1</span></span></td>
<td><span data-ttu-id="402b1-516">80</span><span class="sxs-lookup"><span data-stu-id="402b1-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="402b1-517">Prod 2</span></span></td>
<td><span data-ttu-id="402b1-518">Producto 2</span><span class="sxs-lookup"><span data-stu-id="402b1-518">Product 2</span></span></td>
<td><span data-ttu-id="402b1-519">15</span><span class="sxs-lookup"><span data-stu-id="402b1-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="402b1-520">Las medidas estadísticas como las horas de la producción que un producto consume se pueden deducir de los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="402b1-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="402b1-521">Para obtener más información, vea [Plantilla de proveedor de medidas estadísticas](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="402b1-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="402b1-522">La tabla siguiente muestra el resultado cuando se aplican los servicios de HR como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="402b1-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="402b1-523">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-523">Cost object</span></span></th>
<th><span data-ttu-id="402b1-524">Magnitud</span><span class="sxs-lookup"><span data-stu-id="402b1-524">Magnitude</span></span></th>
<th><span data-ttu-id="402b1-525">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="402b1-525">Allocation factor</span></span></th>
<th><span data-ttu-id="402b1-526">Importe</span><span class="sxs-lookup"><span data-stu-id="402b1-526">Amount</span></span></th>
<th><span data-ttu-id="402b1-527">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="402b1-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-528">CC002</span><span class="sxs-lookup"><span data-stu-id="402b1-528">CC002</span></span></td>
<td><span data-ttu-id="402b1-529">Finanzas</span><span class="sxs-lookup"><span data-stu-id="402b1-529">Finance</span></span></td>
<td><span data-ttu-id="402b1-530">35</span><span class="sxs-lookup"><span data-stu-id="402b1-530">35</span></span></td>
<td><span data-ttu-id="402b1-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="402b1-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="402b1-532">175.00</span><span class="sxs-lookup"><span data-stu-id="402b1-532">175.00</span></span></td>
<td><span data-ttu-id="402b1-533">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-534">CC003</span><span class="sxs-lookup"><span data-stu-id="402b1-534">CC003</span></span></td>
<td><span data-ttu-id="402b1-535">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="402b1-535">Assembly</span></span></td>
<td><span data-ttu-id="402b1-536">55</span><span class="sxs-lookup"><span data-stu-id="402b1-536">55</span></span></td>
<td><span data-ttu-id="402b1-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="402b1-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="402b1-538">275.00</span><span class="sxs-lookup"><span data-stu-id="402b1-538">275.00</span></span></td>
<td><span data-ttu-id="402b1-539">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-540">CC004</span><span class="sxs-lookup"><span data-stu-id="402b1-540">CC004</span></span></td>
<td><span data-ttu-id="402b1-541">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="402b1-541">Packaging</span></span></td>
<td><span data-ttu-id="402b1-542">10</span><span class="sxs-lookup"><span data-stu-id="402b1-542">10</span></span></td>
<td><span data-ttu-id="402b1-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="402b1-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="402b1-544">50,00</span><span class="sxs-lookup"><span data-stu-id="402b1-544">50.00</span></span></td>
<td><span data-ttu-id="402b1-545">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-546">CC002</span><span class="sxs-lookup"><span data-stu-id="402b1-546">CC002</span></span></td>
<td><span data-ttu-id="402b1-547">Finanzas</span><span class="sxs-lookup"><span data-stu-id="402b1-547">Finance</span></span></td>
<td><span data-ttu-id="402b1-548">35</span><span class="sxs-lookup"><span data-stu-id="402b1-548">35</span></span></td>
<td><span data-ttu-id="402b1-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="402b1-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="402b1-550">436.00</span><span class="sxs-lookup"><span data-stu-id="402b1-550">436.00</span></span></td>
<td><span data-ttu-id="402b1-551">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-552">CC003</span><span class="sxs-lookup"><span data-stu-id="402b1-552">CC003</span></span></td>
<td><span data-ttu-id="402b1-553">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="402b1-553">Assembly</span></span></td>
<td><span data-ttu-id="402b1-554">55</span><span class="sxs-lookup"><span data-stu-id="402b1-554">55</span></span></td>
<td><span data-ttu-id="402b1-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="402b1-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="402b1-556">685.14</span><span class="sxs-lookup"><span data-stu-id="402b1-556">685.14</span></span></td>
<td><span data-ttu-id="402b1-557">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-558">CC004</span><span class="sxs-lookup"><span data-stu-id="402b1-558">CC004</span></span></td>
<td><span data-ttu-id="402b1-559">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="402b1-559">Packaging</span></span></td>
<td><span data-ttu-id="402b1-560">10</span><span class="sxs-lookup"><span data-stu-id="402b1-560">10</span></span></td>
<td><span data-ttu-id="402b1-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="402b1-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="402b1-562">124.57</span><span class="sxs-lookup"><span data-stu-id="402b1-562">124.57</span></span></td>
<td><span data-ttu-id="402b1-563">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="402b1-564">La tabla siguiente muestra el resultado cuando se aplican los servicios de Finanzas como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="402b1-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="402b1-565">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-565">Cost object</span></span></th>
<th><span data-ttu-id="402b1-566">Magnitud</span><span class="sxs-lookup"><span data-stu-id="402b1-566">Magnitude</span></span></th>
<th><span data-ttu-id="402b1-567">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="402b1-567">Allocation factor</span></span></th>
<th><span data-ttu-id="402b1-568">Importe</span><span class="sxs-lookup"><span data-stu-id="402b1-568">Amount</span></span></th>
<th><span data-ttu-id="402b1-569">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="402b1-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-570">CC003</span><span class="sxs-lookup"><span data-stu-id="402b1-570">CC003</span></span></td>
<td><span data-ttu-id="402b1-571">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="402b1-571">Assembly</span></span></td>
<td><span data-ttu-id="402b1-572">65</span><span class="sxs-lookup"><span data-stu-id="402b1-572">65</span></span></td>
<td><span data-ttu-id="402b1-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="402b1-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="402b1-574">438.75</span><span class="sxs-lookup"><span data-stu-id="402b1-574">438.75</span></span></td>
<td><span data-ttu-id="402b1-575">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-576">CC004</span><span class="sxs-lookup"><span data-stu-id="402b1-576">CC004</span></span></td>
<td><span data-ttu-id="402b1-577">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="402b1-577">Packaging</span></span></td>
<td><span data-ttu-id="402b1-578">35</span><span class="sxs-lookup"><span data-stu-id="402b1-578">35</span></span></td>
<td><span data-ttu-id="402b1-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="402b1-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="402b1-580">236.25</span><span class="sxs-lookup"><span data-stu-id="402b1-580">236.25</span></span></td>
<td><span data-ttu-id="402b1-581">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-582">CC003</span><span class="sxs-lookup"><span data-stu-id="402b1-582">CC003</span></span></td>
<td><span data-ttu-id="402b1-583">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="402b1-583">Assembly</span></span></td>
<td><span data-ttu-id="402b1-584">65</span><span class="sxs-lookup"><span data-stu-id="402b1-584">65</span></span></td>
<td><span data-ttu-id="402b1-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="402b1-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="402b1-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="402b1-586">5,297.69</span></span></td>
<td><span data-ttu-id="402b1-587">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-588">CC004</span><span class="sxs-lookup"><span data-stu-id="402b1-588">CC004</span></span></td>
<td><span data-ttu-id="402b1-589">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="402b1-589">Packaging</span></span></td>
<td><span data-ttu-id="402b1-590">35</span><span class="sxs-lookup"><span data-stu-id="402b1-590">35</span></span></td>
<td><span data-ttu-id="402b1-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="402b1-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="402b1-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="402b1-592">2,852.60</span></span></td>
<td><span data-ttu-id="402b1-593">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="402b1-594">La tabla siguiente muestra el resultado cuando se aplican los servicios de Asamblea como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="402b1-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="402b1-595">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-595">Cost object</span></span></th>
<th><span data-ttu-id="402b1-596">Magnitud</span><span class="sxs-lookup"><span data-stu-id="402b1-596">Magnitude</span></span></th>
<th><span data-ttu-id="402b1-597">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="402b1-597">Allocation factor</span></span></th>
<th><span data-ttu-id="402b1-598">Importe</span><span class="sxs-lookup"><span data-stu-id="402b1-598">Amount</span></span></th>
<th><span data-ttu-id="402b1-599">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="402b1-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="402b1-600">Prod 1</span></span></td>
<td><span data-ttu-id="402b1-601">Producto 1</span><span class="sxs-lookup"><span data-stu-id="402b1-601">Product 1</span></span></td>
<td><span data-ttu-id="402b1-602">60</span><span class="sxs-lookup"><span data-stu-id="402b1-602">60</span></span></td>
<td><span data-ttu-id="402b1-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="402b1-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="402b1-604">535.31</span><span class="sxs-lookup"><span data-stu-id="402b1-604">535.31</span></span></td>
<td><span data-ttu-id="402b1-605">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="402b1-606">Prod 2</span></span></td>
<td><span data-ttu-id="402b1-607">Producto 2</span><span class="sxs-lookup"><span data-stu-id="402b1-607">Product 2</span></span></td>
<td><span data-ttu-id="402b1-608">20</span><span class="sxs-lookup"><span data-stu-id="402b1-608">20</span></span></td>
<td><span data-ttu-id="402b1-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="402b1-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="402b1-610">178.44</span><span class="sxs-lookup"><span data-stu-id="402b1-610">178.44</span></span></td>
<td><span data-ttu-id="402b1-611">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="402b1-612">Prod 1</span></span></td>
<td><span data-ttu-id="402b1-613">Producto 1</span><span class="sxs-lookup"><span data-stu-id="402b1-613">Product 1</span></span></td>
<td><span data-ttu-id="402b1-614">60</span><span class="sxs-lookup"><span data-stu-id="402b1-614">60</span></span></td>
<td><span data-ttu-id="402b1-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="402b1-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="402b1-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="402b1-616">4,487.12</span></span></td>
<td><span data-ttu-id="402b1-617">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="402b1-618">Prod 2</span></span></td>
<td><span data-ttu-id="402b1-619">Producto 2</span><span class="sxs-lookup"><span data-stu-id="402b1-619">Product 2</span></span></td>
<td><span data-ttu-id="402b1-620">20</span><span class="sxs-lookup"><span data-stu-id="402b1-620">20</span></span></td>
<td><span data-ttu-id="402b1-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="402b1-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="402b1-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="402b1-622">1,495.71</span></span></td>
<td><span data-ttu-id="402b1-623">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="402b1-624">La tabla siguiente muestra el resultado cuando se aplican los servicios de Embalaje como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="402b1-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="402b1-625">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-625">Cost object</span></span></th>
<th><span data-ttu-id="402b1-626">Magnitud</span><span class="sxs-lookup"><span data-stu-id="402b1-626">Magnitude</span></span></th>
<th><span data-ttu-id="402b1-627">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="402b1-627">Allocation factor</span></span></th>
<th><span data-ttu-id="402b1-628">Importe</span><span class="sxs-lookup"><span data-stu-id="402b1-628">Amount</span></span></th>
<th><span data-ttu-id="402b1-629">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="402b1-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="402b1-630">Prod 1</span></span></td>
<td><span data-ttu-id="402b1-631">Producto 1</span><span class="sxs-lookup"><span data-stu-id="402b1-631">Product 1</span></span></td>
<td><span data-ttu-id="402b1-632">80</span><span class="sxs-lookup"><span data-stu-id="402b1-632">80</span></span></td>
<td><span data-ttu-id="402b1-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="402b1-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="402b1-634">241.05</span><span class="sxs-lookup"><span data-stu-id="402b1-634">241.05</span></span></td>
<td><span data-ttu-id="402b1-635">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="402b1-636">Prod 2</span></span></td>
<td><span data-ttu-id="402b1-637">Producto 2</span><span class="sxs-lookup"><span data-stu-id="402b1-637">Product 2</span></span></td>
<td><span data-ttu-id="402b1-638">15</span><span class="sxs-lookup"><span data-stu-id="402b1-638">15</span></span></td>
<td><span data-ttu-id="402b1-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="402b1-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="402b1-640">45.20</span><span class="sxs-lookup"><span data-stu-id="402b1-640">45.20</span></span></td>
<td><span data-ttu-id="402b1-641">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="402b1-642">Prod 1</span></span></td>
<td><span data-ttu-id="402b1-643">Producto 1</span><span class="sxs-lookup"><span data-stu-id="402b1-643">Product 1</span></span></td>
<td><span data-ttu-id="402b1-644">80</span><span class="sxs-lookup"><span data-stu-id="402b1-644">80</span></span></td>
<td><span data-ttu-id="402b1-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="402b1-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="402b1-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="402b1-646">2,507.09</span></span></td>
<td><span data-ttu-id="402b1-647">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="402b1-648">Prod 2</span></span></td>
<td><span data-ttu-id="402b1-649">Producto 2</span><span class="sxs-lookup"><span data-stu-id="402b1-649">Product 2</span></span></td>
<td><span data-ttu-id="402b1-650">15</span><span class="sxs-lookup"><span data-stu-id="402b1-650">15</span></span></td>
<td><span data-ttu-id="402b1-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="402b1-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="402b1-652">470.08</span><span class="sxs-lookup"><span data-stu-id="402b1-652">470.08</span></span></td>
<td><span data-ttu-id="402b1-653">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="402b1-654">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="402b1-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="402b1-655">Diario</span><span class="sxs-lookup"><span data-stu-id="402b1-655">Journal</span></span></th>
<th><span data-ttu-id="402b1-656">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="402b1-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="402b1-657">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="402b1-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="402b1-658">Versión</span><span class="sxs-lookup"><span data-stu-id="402b1-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-659">00004</span><span class="sxs-lookup"><span data-stu-id="402b1-659">00004</span></span></td>
<td><span data-ttu-id="402b1-660">Diario de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="402b1-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="402b1-661">Fiscal</span><span class="sxs-lookup"><span data-stu-id="402b1-661">Fiscal</span></span></td>
<td><span data-ttu-id="402b1-662">2017</span><span class="sxs-lookup"><span data-stu-id="402b1-662">2017</span></span></td>
<td><span data-ttu-id="402b1-663">Período 1</span><span class="sxs-lookup"><span data-stu-id="402b1-663">Period 1</span></span></td>
<td><span data-ttu-id="402b1-664">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="402b1-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="402b1-665">Líneas de diario</span><span class="sxs-lookup"><span data-stu-id="402b1-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="402b1-666">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="402b1-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="402b1-667">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="402b1-668">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-668">Cost element</span></span></th>
<th><span data-ttu-id="402b1-669">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="402b1-669">Cost behavior</span></span></th>
<th><span data-ttu-id="402b1-670">Importe</span><span class="sxs-lookup"><span data-stu-id="402b1-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-671">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="402b1-672">CC001</span><span class="sxs-lookup"><span data-stu-id="402b1-672">CC001</span></span></td>
<td><span data-ttu-id="402b1-673">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="402b1-673">HR</span></span></td>
<td><span data-ttu-id="402b1-674">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-674">10001</span></span></td>
<td><span data-ttu-id="402b1-675">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-675">Electricity</span></span></td>
<td><span data-ttu-id="402b1-676">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-676">Fixed cost</span></span></td>
<td><span data-ttu-id="402b1-677">500,00</span><span class="sxs-lookup"><span data-stu-id="402b1-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-678">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="402b1-679">CC001</span><span class="sxs-lookup"><span data-stu-id="402b1-679">CC001</span></span></td>
<td><span data-ttu-id="402b1-680">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="402b1-680">HR</span></span></td>
<td><span data-ttu-id="402b1-681">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-681">10001</span></span></td>
<td><span data-ttu-id="402b1-682">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-682">Electricity</span></span></td>
<td><span data-ttu-id="402b1-683">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-683">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="402b1-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-685">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="402b1-686">CC002</span><span class="sxs-lookup"><span data-stu-id="402b1-686">CC002</span></span></td>
<td><span data-ttu-id="402b1-687">Finanzas</span><span class="sxs-lookup"><span data-stu-id="402b1-687">Finance</span></span></td>
<td><span data-ttu-id="402b1-688">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-688">10001</span></span></td>
<td><span data-ttu-id="402b1-689">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-689">Electricity</span></span></td>
<td><span data-ttu-id="402b1-690">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-690">Fixed cost</span></span></td>
<td><span data-ttu-id="402b1-691">675.00</span><span class="sxs-lookup"><span data-stu-id="402b1-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-692">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="402b1-693">CC002</span><span class="sxs-lookup"><span data-stu-id="402b1-693">CC002</span></span></td>
<td><span data-ttu-id="402b1-694">Finanzas</span><span class="sxs-lookup"><span data-stu-id="402b1-694">Finance</span></span></td>
<td><span data-ttu-id="402b1-695">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-695">10001</span></span></td>
<td><span data-ttu-id="402b1-696">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-696">Electricity</span></span></td>
<td><span data-ttu-id="402b1-697">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-697">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="402b1-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-699">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="402b1-700">CC003</span><span class="sxs-lookup"><span data-stu-id="402b1-700">CC003</span></span></td>
<td><span data-ttu-id="402b1-701">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="402b1-701">Assembly</span></span></td>
<td><span data-ttu-id="402b1-702">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-702">10001</span></span></td>
<td><span data-ttu-id="402b1-703">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-703">Electricity</span></span></td>
<td><span data-ttu-id="402b1-704">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-704">Fixed cost</span></span></td>
<td><span data-ttu-id="402b1-705">713.75</span><span class="sxs-lookup"><span data-stu-id="402b1-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-706">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="402b1-707">CC003</span><span class="sxs-lookup"><span data-stu-id="402b1-707">CC003</span></span></td>
<td><span data-ttu-id="402b1-708">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="402b1-708">Assembly</span></span></td>
<td><span data-ttu-id="402b1-709">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-709">10001</span></span></td>
<td><span data-ttu-id="402b1-710">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-710">Electricity</span></span></td>
<td><span data-ttu-id="402b1-711">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-711">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="402b1-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-713">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="402b1-714">CC003</span><span class="sxs-lookup"><span data-stu-id="402b1-714">CC003</span></span></td>
<td><span data-ttu-id="402b1-715">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="402b1-715">Packaging</span></span></td>
<td><span data-ttu-id="402b1-716">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-716">10001</span></span></td>
<td><span data-ttu-id="402b1-717">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-717">Electricity</span></span></td>
<td><span data-ttu-id="402b1-718">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-718">Fixed cost</span></span></td>
<td><span data-ttu-id="402b1-719">286.25</span><span class="sxs-lookup"><span data-stu-id="402b1-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-720">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="402b1-721">CC003</span><span class="sxs-lookup"><span data-stu-id="402b1-721">CC003</span></span></td>
<td><span data-ttu-id="402b1-722">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="402b1-722">Packaging</span></span></td>
<td><span data-ttu-id="402b1-723">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-723">10001</span></span></td>
<td><span data-ttu-id="402b1-724">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-724">Electricity</span></span></td>
<td><span data-ttu-id="402b1-725">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-725">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="402b1-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-727">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="402b1-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="402b1-728">Prod 1</span></span></td>
<td><span data-ttu-id="402b1-729">Producto 1</span><span class="sxs-lookup"><span data-stu-id="402b1-729">Product 1</span></span></td>
<td><span data-ttu-id="402b1-730">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-730">10001</span></span></td>
<td><span data-ttu-id="402b1-731">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-731">Electricity</span></span></td>
<td><span data-ttu-id="402b1-732">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-732">Fixed cost</span></span></td>
<td><span data-ttu-id="402b1-733">776.36</span><span class="sxs-lookup"><span data-stu-id="402b1-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-734">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="402b1-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="402b1-735">Prod 1</span></span></td>
<td><span data-ttu-id="402b1-736">Producto 1</span><span class="sxs-lookup"><span data-stu-id="402b1-736">Product 1</span></span></td>
<td><span data-ttu-id="402b1-737">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-737">10001</span></span></td>
<td><span data-ttu-id="402b1-738">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-738">Electricity</span></span></td>
<td><span data-ttu-id="402b1-739">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-739">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="402b1-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-741">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="402b1-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="402b1-742">Prod 2</span></span></td>
<td><span data-ttu-id="402b1-743">Producto 1</span><span class="sxs-lookup"><span data-stu-id="402b1-743">Product 1</span></span></td>
<td><span data-ttu-id="402b1-744">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-744">10001</span></span></td>
<td><span data-ttu-id="402b1-745">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-745">Electricity</span></span></td>
<td><span data-ttu-id="402b1-746">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-746">Fixed cost</span></span></td>
<td><span data-ttu-id="402b1-747">223.64</span><span class="sxs-lookup"><span data-stu-id="402b1-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-748">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="402b1-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="402b1-749">Prod 2</span></span></td>
<td><span data-ttu-id="402b1-750">Producto 1</span><span class="sxs-lookup"><span data-stu-id="402b1-750">Product 1</span></span></td>
<td><span data-ttu-id="402b1-751">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-751">10001</span></span></td>
<td><span data-ttu-id="402b1-752">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-752">Electricity</span></span></td>
<td><span data-ttu-id="402b1-753">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-753">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="402b1-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="402b1-755">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="402b1-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="402b1-756">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="402b1-757">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-757">Cost element</span></span></th>
<th><span data-ttu-id="402b1-758">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="402b1-758">Cost behavior</span></span></th>
<th><span data-ttu-id="402b1-759">Importe</span><span class="sxs-lookup"><span data-stu-id="402b1-759">Amount</span></span></th>
<th><span data-ttu-id="402b1-760">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="402b1-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="402b1-761">CC001</span><span class="sxs-lookup"><span data-stu-id="402b1-761">CC001</span></span></td>
<td><span data-ttu-id="402b1-762">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="402b1-762">HR</span></span></td>
<td><span data-ttu-id="402b1-763">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-763">10001</span></span></td>
<td><span data-ttu-id="402b1-764">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-764">Electricity</span></span></td>
<td><span data-ttu-id="402b1-765">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-765">Fixed cost</span></span></td>
<td><span data-ttu-id="402b1-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="402b1-766">-500.00</span></span></td>
<td><span data-ttu-id="402b1-767">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-768">CC002</span><span class="sxs-lookup"><span data-stu-id="402b1-768">CC002</span></span></td>
<td><span data-ttu-id="402b1-769">Finanzas</span><span class="sxs-lookup"><span data-stu-id="402b1-769">Finance</span></span></td>
<td><span data-ttu-id="402b1-770">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-770">10001</span></span></td>
<td><span data-ttu-id="402b1-771">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-771">Electricity</span></span></td>
<td><span data-ttu-id="402b1-772">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-772">Fixed cost</span></span></td>
<td><span data-ttu-id="402b1-773">175.00</span><span class="sxs-lookup"><span data-stu-id="402b1-773">175.00</span></span></td>
<td><span data-ttu-id="402b1-774">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-775">CC003</span><span class="sxs-lookup"><span data-stu-id="402b1-775">CC003</span></span></td>
<td><span data-ttu-id="402b1-776">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="402b1-776">Assembly</span></span></td>
<td><span data-ttu-id="402b1-777">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-777">10001</span></span></td>
<td><span data-ttu-id="402b1-778">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-778">Electricity</span></span></td>
<td><span data-ttu-id="402b1-779">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-779">Fixed cost</span></span></td>
<td><span data-ttu-id="402b1-780">275.00</span><span class="sxs-lookup"><span data-stu-id="402b1-780">275.00</span></span></td>
<td><span data-ttu-id="402b1-781">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-782">CC004</span><span class="sxs-lookup"><span data-stu-id="402b1-782">CC004</span></span></td>
<td><span data-ttu-id="402b1-783">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="402b1-783">Packaging</span></span></td>
<td><span data-ttu-id="402b1-784">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-784">10001</span></span></td>
<td><span data-ttu-id="402b1-785">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-785">Electricity</span></span></td>
<td><span data-ttu-id="402b1-786">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-786">Fixed cost</span></span></td>
<td><span data-ttu-id="402b1-787">50,00</span><span class="sxs-lookup"><span data-stu-id="402b1-787">50,00</span></span></td>
<td><span data-ttu-id="402b1-788">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-789">CC001</span><span class="sxs-lookup"><span data-stu-id="402b1-789">CC001</span></span></td>
<td><span data-ttu-id="402b1-790">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="402b1-790">HR</span></span></td>
<td><span data-ttu-id="402b1-791">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-791">10001</span></span></td>
<td><span data-ttu-id="402b1-792">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-792">Electricity</span></span></td>
<td><span data-ttu-id="402b1-793">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-793">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="402b1-794">-1,245.71</span></span></td>
<td><span data-ttu-id="402b1-795">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-796">CC002</span><span class="sxs-lookup"><span data-stu-id="402b1-796">CC002</span></span></td>
<td><span data-ttu-id="402b1-797">Finanzas</span><span class="sxs-lookup"><span data-stu-id="402b1-797">Finance</span></span></td>
<td><span data-ttu-id="402b1-798">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-798">10001</span></span></td>
<td><span data-ttu-id="402b1-799">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-799">Electricity</span></span></td>
<td><span data-ttu-id="402b1-800">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-800">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-801">436.00</span><span class="sxs-lookup"><span data-stu-id="402b1-801">436.00</span></span></td>
<td><span data-ttu-id="402b1-802">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-803">CC003</span><span class="sxs-lookup"><span data-stu-id="402b1-803">CC003</span></span></td>
<td><span data-ttu-id="402b1-804">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="402b1-804">Assembly</span></span></td>
<td><span data-ttu-id="402b1-805">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-805">10001</span></span></td>
<td><span data-ttu-id="402b1-806">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-806">Electricity</span></span></td>
<td><span data-ttu-id="402b1-807">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-807">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-808">685.14</span><span class="sxs-lookup"><span data-stu-id="402b1-808">685.14</span></span></td>
<td><span data-ttu-id="402b1-809">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-810">CC004</span><span class="sxs-lookup"><span data-stu-id="402b1-810">CC004</span></span></td>
<td><span data-ttu-id="402b1-811">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="402b1-811">Packaging</span></span></td>
<td><span data-ttu-id="402b1-812">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-812">10001</span></span></td>
<td><span data-ttu-id="402b1-813">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-813">Electricity</span></span></td>
<td><span data-ttu-id="402b1-814">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-814">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-815">124.57</span><span class="sxs-lookup"><span data-stu-id="402b1-815">124.57</span></span></td>
<td><span data-ttu-id="402b1-816">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-817">CC002</span><span class="sxs-lookup"><span data-stu-id="402b1-817">CC002</span></span></td>
<td><span data-ttu-id="402b1-818">Finanzas</span><span class="sxs-lookup"><span data-stu-id="402b1-818">Finance</span></span></td>
<td><span data-ttu-id="402b1-819">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-819">10001</span></span></td>
<td><span data-ttu-id="402b1-820">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-820">Electricity</span></span></td>
<td><span data-ttu-id="402b1-821">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-821">Fixed cost</span></span></td>
<td><span data-ttu-id="402b1-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="402b1-822">-675.00</span></span></td>
<td><span data-ttu-id="402b1-823">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-824">CC003</span><span class="sxs-lookup"><span data-stu-id="402b1-824">CC003</span></span></td>
<td><span data-ttu-id="402b1-825">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="402b1-825">Assembly</span></span></td>
<td><span data-ttu-id="402b1-826">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-826">10001</span></span></td>
<td><span data-ttu-id="402b1-827">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-827">Electricity</span></span></td>
<td><span data-ttu-id="402b1-828">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-828">Fixed cost</span></span></td>
<td><span data-ttu-id="402b1-829">438.75</span><span class="sxs-lookup"><span data-stu-id="402b1-829">438.75</span></span></td>
<td><span data-ttu-id="402b1-830">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-831">CC004</span><span class="sxs-lookup"><span data-stu-id="402b1-831">CC004</span></span></td>
<td><span data-ttu-id="402b1-832">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="402b1-832">Packaging</span></span></td>
<td><span data-ttu-id="402b1-833">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-833">10001</span></span></td>
<td><span data-ttu-id="402b1-834">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-834">Electricity</span></span></td>
<td><span data-ttu-id="402b1-835">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-835">Fixed cost</span></span></td>
<td><span data-ttu-id="402b1-836">236.25</span><span class="sxs-lookup"><span data-stu-id="402b1-836">236.25</span></span></td>
<td><span data-ttu-id="402b1-837">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-838">CC002</span><span class="sxs-lookup"><span data-stu-id="402b1-838">CC002</span></span></td>
<td><span data-ttu-id="402b1-839">Finanzas</span><span class="sxs-lookup"><span data-stu-id="402b1-839">Finance</span></span></td>
<td><span data-ttu-id="402b1-840">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-840">10001</span></span></td>
<td><span data-ttu-id="402b1-841">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-841">Electricity</span></span></td>
<td><span data-ttu-id="402b1-842">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-842">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="402b1-843">-8,150.29</span></span></td>
<td><span data-ttu-id="402b1-844">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-845">CC003</span><span class="sxs-lookup"><span data-stu-id="402b1-845">CC003</span></span></td>
<td><span data-ttu-id="402b1-846">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="402b1-846">Assembly</span></span></td>
<td><span data-ttu-id="402b1-847">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-847">10001</span></span></td>
<td><span data-ttu-id="402b1-848">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-848">Electricity</span></span></td>
<td><span data-ttu-id="402b1-849">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-849">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="402b1-850">5,297.69</span></span></td>
<td><span data-ttu-id="402b1-851">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-852">CC004</span><span class="sxs-lookup"><span data-stu-id="402b1-852">CC004</span></span></td>
<td><span data-ttu-id="402b1-853">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="402b1-853">Packaging</span></span></td>
<td><span data-ttu-id="402b1-854">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-854">10001</span></span></td>
<td><span data-ttu-id="402b1-855">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-855">Electricity</span></span></td>
<td><span data-ttu-id="402b1-856">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-856">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="402b1-857">2,852.60</span></span></td>
<td><span data-ttu-id="402b1-858">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-859">CC003</span><span class="sxs-lookup"><span data-stu-id="402b1-859">CC003</span></span></td>
<td><span data-ttu-id="402b1-860">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="402b1-860">Assembly</span></span></td>
<td><span data-ttu-id="402b1-861">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-861">10001</span></span></td>
<td><span data-ttu-id="402b1-862">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-862">Electricity</span></span></td>
<td><span data-ttu-id="402b1-863">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-863">Fixed cost</span></span></td>
<td><span data-ttu-id="402b1-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="402b1-864">-713.75</span></span></td>
<td><span data-ttu-id="402b1-865">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="402b1-866">Prod 1</span></span></td>
<td><span data-ttu-id="402b1-867">Producto 1</span><span class="sxs-lookup"><span data-stu-id="402b1-867">Product 1</span></span></td>
<td><span data-ttu-id="402b1-868">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-868">10001</span></span></td>
<td><span data-ttu-id="402b1-869">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-869">Electricity</span></span></td>
<td><span data-ttu-id="402b1-870">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-870">Fixed cost</span></span></td>
<td><span data-ttu-id="402b1-871">535.31</span><span class="sxs-lookup"><span data-stu-id="402b1-871">535.31</span></span></td>
<td><span data-ttu-id="402b1-872">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="402b1-873">Prod 2</span></span></td>
<td><span data-ttu-id="402b1-874">Producto 2</span><span class="sxs-lookup"><span data-stu-id="402b1-874">Product 2</span></span></td>
<td><span data-ttu-id="402b1-875">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-875">10001</span></span></td>
<td><span data-ttu-id="402b1-876">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-876">Electricity</span></span></td>
<td><span data-ttu-id="402b1-877">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-877">Fixed cost</span></span></td>
<td><span data-ttu-id="402b1-878">178.44</span><span class="sxs-lookup"><span data-stu-id="402b1-878">178.44</span></span></td>
<td><span data-ttu-id="402b1-879">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-880">CC003</span><span class="sxs-lookup"><span data-stu-id="402b1-880">CC003</span></span></td>
<td><span data-ttu-id="402b1-881">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="402b1-881">Assembly</span></span></td>
<td><span data-ttu-id="402b1-882">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-882">10001</span></span></td>
<td><span data-ttu-id="402b1-883">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-883">Electricity</span></span></td>
<td><span data-ttu-id="402b1-884">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-884">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="402b1-885">-5,982.83</span></span></td>
<td><span data-ttu-id="402b1-886">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="402b1-887">Prod 1</span></span></td>
<td><span data-ttu-id="402b1-888">Producto 1</span><span class="sxs-lookup"><span data-stu-id="402b1-888">Product 1</span></span></td>
<td><span data-ttu-id="402b1-889">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-889">10001</span></span></td>
<td><span data-ttu-id="402b1-890">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-890">Electricity</span></span></td>
<td><span data-ttu-id="402b1-891">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-891">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="402b1-892">4,487.12</span></span></td>
<td><span data-ttu-id="402b1-893">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="402b1-894">Prod 2</span></span></td>
<td><span data-ttu-id="402b1-895">Producto 2</span><span class="sxs-lookup"><span data-stu-id="402b1-895">Product 2</span></span></td>
<td><span data-ttu-id="402b1-896">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-896">10001</span></span></td>
<td><span data-ttu-id="402b1-897">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-897">Electricity</span></span></td>
<td><span data-ttu-id="402b1-898">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-898">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="402b1-899">1,495.71</span></span></td>
<td><span data-ttu-id="402b1-900">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-901">CC003</span><span class="sxs-lookup"><span data-stu-id="402b1-901">CC003</span></span></td>
<td><span data-ttu-id="402b1-902">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="402b1-902">Assembly</span></span></td>
<td><span data-ttu-id="402b1-903">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-903">10001</span></span></td>
<td><span data-ttu-id="402b1-904">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-904">Electricity</span></span></td>
<td><span data-ttu-id="402b1-905">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-905">Fixed cost</span></span></td>
<td><span data-ttu-id="402b1-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="402b1-906">-286.25</span></span></td>
<td><span data-ttu-id="402b1-907">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="402b1-908">Prod 1</span></span></td>
<td><span data-ttu-id="402b1-909">Producto 1</span><span class="sxs-lookup"><span data-stu-id="402b1-909">Product 1</span></span></td>
<td><span data-ttu-id="402b1-910">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-910">10001</span></span></td>
<td><span data-ttu-id="402b1-911">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-911">Electricity</span></span></td>
<td><span data-ttu-id="402b1-912">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-912">Fixed cost</span></span></td>
<td><span data-ttu-id="402b1-913">241.05</span><span class="sxs-lookup"><span data-stu-id="402b1-913">241.05</span></span></td>
<td><span data-ttu-id="402b1-914">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="402b1-915">Prod 2</span></span></td>
<td><span data-ttu-id="402b1-916">Producto 2</span><span class="sxs-lookup"><span data-stu-id="402b1-916">Product 2</span></span></td>
<td><span data-ttu-id="402b1-917">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-917">10001</span></span></td>
<td><span data-ttu-id="402b1-918">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-918">Electricity</span></span></td>
<td><span data-ttu-id="402b1-919">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-919">Fixed cost</span></span></td>
<td><span data-ttu-id="402b1-920">45.20</span><span class="sxs-lookup"><span data-stu-id="402b1-920">45.20</span></span></td>
<td><span data-ttu-id="402b1-921">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-922">CC003</span><span class="sxs-lookup"><span data-stu-id="402b1-922">CC003</span></span></td>
<td><span data-ttu-id="402b1-923">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="402b1-923">Assembly</span></span></td>
<td><span data-ttu-id="402b1-924">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-924">10001</span></span></td>
<td><span data-ttu-id="402b1-925">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-925">Electricity</span></span></td>
<td><span data-ttu-id="402b1-926">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-926">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="402b1-927">-2,977.17</span></span></td>
<td><span data-ttu-id="402b1-928">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="402b1-929">Prod 1</span></span></td>
<td><span data-ttu-id="402b1-930">Producto 1</span><span class="sxs-lookup"><span data-stu-id="402b1-930">Product 1</span></span></td>
<td><span data-ttu-id="402b1-931">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-931">10001</span></span></td>
<td><span data-ttu-id="402b1-932">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-932">Electricity</span></span></td>
<td><span data-ttu-id="402b1-933">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-933">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="402b1-934">2,507.09</span></span></td>
<td><span data-ttu-id="402b1-935">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="402b1-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="402b1-936">Prod 2</span></span></td>
<td><span data-ttu-id="402b1-937">Producto 2</span><span class="sxs-lookup"><span data-stu-id="402b1-937">Product 2</span></span></td>
<td><span data-ttu-id="402b1-938">10001</span><span class="sxs-lookup"><span data-stu-id="402b1-938">10001</span></span></td>
<td><span data-ttu-id="402b1-939">Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-939">Electricity</span></span></td>
<td><span data-ttu-id="402b1-940">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-940">Variable cost</span></span></td>
<td><span data-ttu-id="402b1-941">470.08</span><span class="sxs-lookup"><span data-stu-id="402b1-941">470.08</span></span></td>
<td><span data-ttu-id="402b1-942">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="402b1-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="402b1-943">Conclusión</span><span class="sxs-lookup"><span data-stu-id="402b1-943">Conclusion</span></span>
<span data-ttu-id="402b1-944">En la contabilidad financiera, un coste de 10.000,00 para electricidad se envía a un identificador ficticio de centro de coste.</span><span class="sxs-lookup"><span data-stu-id="402b1-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="402b1-945">Por lo tanto, los contables de coste sabrán que este coste se debe asignar.</span><span class="sxs-lookup"><span data-stu-id="402b1-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="402b1-946">En contabilidad de costes, los costes fluyen en las unidades organizativas y los niveles en función de las directivas y las reglas que se aplican.</span><span class="sxs-lookup"><span data-stu-id="402b1-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="402b1-947">Cada coste se ha asociado con una base de asignación que proporciona la mejor evaluación para la asignación de costes.</span><span class="sxs-lookup"><span data-stu-id="402b1-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="402b1-948">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="402b1-949">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="402b1-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="402b1-950">Total</span><span class="sxs-lookup"><span data-stu-id="402b1-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="402b1-951">CC099</span><span class="sxs-lookup"><span data-stu-id="402b1-951">CC099</span></span></th>
<th><span data-ttu-id="402b1-952">CC001</span><span class="sxs-lookup"><span data-stu-id="402b1-952">CC001</span></span></th>
<th><span data-ttu-id="402b1-953">CC002</span><span class="sxs-lookup"><span data-stu-id="402b1-953">CC002</span></span></th>
<th><span data-ttu-id="402b1-954">CC003</span><span class="sxs-lookup"><span data-stu-id="402b1-954">CC003</span></span></th>
<th><span data-ttu-id="402b1-955">CC004</span><span class="sxs-lookup"><span data-stu-id="402b1-955">CC004</span></span></th>
<th><span data-ttu-id="402b1-956">Proy 1</span><span class="sxs-lookup"><span data-stu-id="402b1-956">Proj 1</span></span></th>
<th><span data-ttu-id="402b1-957">Proy 2</span><span class="sxs-lookup"><span data-stu-id="402b1-957">Proj 2</span></span></th>
<th><span data-ttu-id="402b1-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="402b1-958">Prod 1</span></span></th>
<th><span data-ttu-id="402b1-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="402b1-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="402b1-960">10001 Electricidad</span><span class="sxs-lookup"><span data-stu-id="402b1-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="402b1-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="402b1-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="402b1-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="402b1-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="402b1-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="402b1-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="402b1-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="402b1-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="402b1-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="402b1-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="402b1-970">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="402b1-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-971">0,00</span><span class="sxs-lookup"><span data-stu-id="402b1-971">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="402b1-972">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="402b1-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-973">0,00</span><span class="sxs-lookup"><span data-stu-id="402b1-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-974">0,00</span><span class="sxs-lookup"><span data-stu-id="402b1-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-975">0,00</span><span class="sxs-lookup"><span data-stu-id="402b1-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-976">0,00</span><span class="sxs-lookup"><span data-stu-id="402b1-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-977">0,00</span><span class="sxs-lookup"><span data-stu-id="402b1-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="402b1-978">776.36</span><span class="sxs-lookup"><span data-stu-id="402b1-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-979">223.64</span><span class="sxs-lookup"><span data-stu-id="402b1-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="402b1-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="402b1-981">Coste variable</span><span class="sxs-lookup"><span data-stu-id="402b1-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-982">000</span><span class="sxs-lookup"><span data-stu-id="402b1-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-983">0,00</span><span class="sxs-lookup"><span data-stu-id="402b1-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-984">0,00</span><span class="sxs-lookup"><span data-stu-id="402b1-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-985">0,00</span><span class="sxs-lookup"><span data-stu-id="402b1-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-986">0,00</span><span class="sxs-lookup"><span data-stu-id="402b1-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-987">30,00</span><span class="sxs-lookup"><span data-stu-id="402b1-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-988">10,00</span><span class="sxs-lookup"><span data-stu-id="402b1-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="402b1-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="402b1-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="402b1-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="402b1-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="402b1-992">Este tema muestra cómo un artículo de costes principales, 10001 Electricidad, fluye por los objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="402b1-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="402b1-993">Por tanto, estos gastos generales se asignan al nivel más bajo de la organización.</span><span class="sxs-lookup"><span data-stu-id="402b1-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="402b1-994">Es decir, los objetos de coste del nivel más bajo son los que soportan el coste.</span><span class="sxs-lookup"><span data-stu-id="402b1-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="402b1-995">Si necesita un flujo visual del coste entre los objetos de coste, puede usar las reglas de directivas de acumulación de costes para visualizar el flujo del coste.</span><span class="sxs-lookup"><span data-stu-id="402b1-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="402b1-996">Para obtener más información, consulte [Directiva de acumulación de costes y cálculo de costes generales](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="402b1-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



