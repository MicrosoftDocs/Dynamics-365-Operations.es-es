---
title: Cálculo de costes generales
description: Este tema describe los procesos típicos para calcular y asignar costes generales.
author: AndersGirke
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation, CAMOverheadRateCalculationJournalEntry, CAMFormulaAllocationBase
audience: Application User
ms.reviewer: roschlom
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 8dc312e66dc666ac6c23bac6b705ffc7893fd06b
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188006"
---
# <a name="overhead-calculation"></a><span data-ttu-id="2365a-103">Cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="2365a-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2365a-104">Este tema describe los procesos típicos para calcular y asignar costes generales.</span><span class="sxs-lookup"><span data-stu-id="2365a-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

## <a name="term-definition"></a><span data-ttu-id="2365a-105">Definición del término</span><span class="sxs-lookup"><span data-stu-id="2365a-105">Term definition</span></span>

<span data-ttu-id="2365a-106">Los costes generales son costes que se contraen para dirigir un negocio, pero que no pueden ser atribuidos directamente a ninguna actividad empresarial, productos, o servicio específicos.</span><span class="sxs-lookup"><span data-stu-id="2365a-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="2365a-107">Los costes generales proporcionan un soporte fundamental a la generación de actividades rentables.</span><span class="sxs-lookup"><span data-stu-id="2365a-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="2365a-108">Algunos ejemplos de costes generales son:</span><span class="sxs-lookup"><span data-stu-id="2365a-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="2365a-109">Alquiler</span><span class="sxs-lookup"><span data-stu-id="2365a-109">Rent</span></span>
-   <span data-ttu-id="2365a-110">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-110">Electricity</span></span>
-   <span data-ttu-id="2365a-111">Sueldos administrativos</span><span class="sxs-lookup"><span data-stu-id="2365a-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="2365a-112">Visión general del cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="2365a-112">Overhead calculation overview</span></span>
<span data-ttu-id="2365a-113">El cálculo de costes generales ejecuta las directivas de contabilidad de costes en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="2365a-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="2365a-114">Puede calcular varias veces los costes generales del mismo período fiscal si se han cambiado las directivas de contabilidad de costes o se han detectado errores específicos.</span><span class="sxs-lookup"><span data-stu-id="2365a-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="2365a-115">Cada ejecución del cálculo de costes generales se almacena y recibe un identificador de versión único que permite comparar los cálculos de diferentes versiones.</span><span class="sxs-lookup"><span data-stu-id="2365a-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="2365a-116">Las entradas de costes que el cálculo de costes generales genera reciben una fecha de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="2365a-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="2365a-117">Esta fecha de contabilidad coincide con la fecha final del período fiscal que se usa en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="2365a-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="2365a-118">El identificador de versión único consiste en los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2365a-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="2365a-119">Tipo de versión</span><span class="sxs-lookup"><span data-stu-id="2365a-119">Version type</span></span>
-   <span data-ttu-id="2365a-120">Fecha y hora</span><span class="sxs-lookup"><span data-stu-id="2365a-120">Date and time</span></span>
-   <span data-ttu-id="2365a-121">Libro mayor de contabilidad de costes</span><span class="sxs-lookup"><span data-stu-id="2365a-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="2365a-122">Ejercicio</span><span class="sxs-lookup"><span data-stu-id="2365a-122">Fiscal year</span></span>
-   <span data-ttu-id="2365a-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="2365a-123">Fiscal period</span></span>

<span data-ttu-id="2365a-124">El cálculo de costes generales se ejecuta independientemente de la versión.</span><span class="sxs-lookup"><span data-stu-id="2365a-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="2365a-125">Por lo tanto, puede calcular la versión de presupuesto antes que la versión real.</span><span class="sxs-lookup"><span data-stu-id="2365a-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="2365a-126">El cálculo de costes generales consta de cuatro pasos, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="2365a-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="2365a-127">En cada paso, se crea una cabecera de diario que tiene entradas del diario.</span><span class="sxs-lookup"><span data-stu-id="2365a-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="2365a-128">Esta cabecera de diario guarda los datos de entrada para cada paso de cálculo.</span><span class="sxs-lookup"><span data-stu-id="2365a-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="2365a-129">Las directivas y las reglas se aplican a cada línea de diario, y las entradas de coste se generan como resultado.</span><span class="sxs-lookup"><span data-stu-id="2365a-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="2365a-130">Por tanto, siempre se tiene rastreabilidad completa.</span><span class="sxs-lookup"><span data-stu-id="2365a-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="2365a-131">[![Cálculo de costes generales](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="2365a-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="2365a-132">Calcular y asignar costes generales de electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="2365a-133">En la contabilidad financiera, algunos costes, como la electricidad, se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="2365a-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="2365a-134">Por lo tanto, no se proporciona una visión de gestión detallada para la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="2365a-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="2365a-135">En contabilidad de costes, para proporcionar información de gestión correcta en todas las unidades y niveles organizativos, los costes deben fluir por las unidades organizativas.</span><span class="sxs-lookup"><span data-stu-id="2365a-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="2365a-136">Este flujo se debe basar en cualquier registro preciso de consumo o en una evaluación justa.</span><span class="sxs-lookup"><span data-stu-id="2365a-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="2365a-137">En la contabilidad general, un coste de la electricidad se puede registrar como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="2365a-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2365a-138">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="2365a-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="2365a-139">Centro de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="2365a-140">Cuenta principal</span><span class="sxs-lookup"><span data-stu-id="2365a-140">Main account</span></span></th>
<th><span data-ttu-id="2365a-141">Importe en la divisa de contabilidad</span><span class="sxs-lookup"><span data-stu-id="2365a-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-142">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="2365a-143">CC099</span><span class="sxs-lookup"><span data-stu-id="2365a-143">CC099</span></span></td>
<td><span data-ttu-id="2365a-144">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="2365a-144">Default cost center</span></span></td>
<td><span data-ttu-id="2365a-145">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-145">10001</span></span></td>
<td><span data-ttu-id="2365a-146">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-146">Electricity</span></span></td>
<td><span data-ttu-id="2365a-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="2365a-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="2365a-148">Paso 1: Procese el cálculo del comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="2365a-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="2365a-149">De forma predeterminada, cuando las entradas de coste se importan de los datos de origen, reciben la clasificación de comportamiento del coste **Sin ordenar** en la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="2365a-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="2365a-150">Aplicando reglas de directivas de comportamiento de coste, puede reclasificar entradas de coste como **Coste fijo** o **Coste variable**.</span><span class="sxs-lookup"><span data-stu-id="2365a-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="2365a-151">Defina la regla de comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="2365a-151">Define the cost behavior rule</span></span>

<span data-ttu-id="2365a-152">En algunos casos, parte del coste es una cuota fija, y el coste pendiente se basa en el consumo.</span><span class="sxs-lookup"><span data-stu-id="2365a-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="2365a-153">Las facturas de electricidad coinciden a menudo con esta definición.</span><span class="sxs-lookup"><span data-stu-id="2365a-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="2365a-154">Tras pagar una cuota fija específica, paga el consumo por kilovatio-hora (Kwh).</span><span class="sxs-lookup"><span data-stu-id="2365a-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="2365a-155">Por ejemplo, si la cuota de coste fijo es de 1.000,00, la regla de comportamiento del coste se define como sigue:</span><span class="sxs-lookup"><span data-stu-id="2365a-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="2365a-156">Importe fijo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="2365a-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="2365a-157">0 &lt;= 1.000,00 = Fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="2365a-158">1.000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="2365a-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="2365a-159">Diario</span><span class="sxs-lookup"><span data-stu-id="2365a-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2365a-160">Diario</span><span class="sxs-lookup"><span data-stu-id="2365a-160">Journal</span></span></th>
<th><span data-ttu-id="2365a-161">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="2365a-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="2365a-162">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="2365a-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="2365a-163">Versión</span><span class="sxs-lookup"><span data-stu-id="2365a-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-164">00001</span><span class="sxs-lookup"><span data-stu-id="2365a-164">00001</span></span></td>
<td><span data-ttu-id="2365a-165">Diario de cálculo de comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="2365a-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="2365a-166">Fiscal</span><span class="sxs-lookup"><span data-stu-id="2365a-166">Fiscal</span></span></td>
<td><span data-ttu-id="2365a-167">2017</span><span class="sxs-lookup"><span data-stu-id="2365a-167">2017</span></span></td>
<td><span data-ttu-id="2365a-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="2365a-168">Period 1</span></span></td>
<td><span data-ttu-id="2365a-169">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="2365a-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="2365a-170">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="2365a-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2365a-171">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="2365a-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="2365a-172">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2365a-173">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-173">Cost element</span></span></th>
<th><span data-ttu-id="2365a-174">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="2365a-174">Cost behavior</span></span></th>
<th><span data-ttu-id="2365a-175">Importe</span><span class="sxs-lookup"><span data-stu-id="2365a-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-176">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="2365a-177">CC099</span><span class="sxs-lookup"><span data-stu-id="2365a-177">CC099</span></span></td>
<td><span data-ttu-id="2365a-178">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="2365a-178">Default cost center</span></span></td>
<td><span data-ttu-id="2365a-179">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-179">10001</span></span></td>
<td><span data-ttu-id="2365a-180">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-180">Electricity</span></span></td>
<td><span data-ttu-id="2365a-181">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="2365a-181">Unclassified</span></span></td>
<td><span data-ttu-id="2365a-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="2365a-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="2365a-183">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="2365a-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2365a-184">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2365a-185">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-185">Cost element</span></span></th>
<th><span data-ttu-id="2365a-186">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="2365a-186">Cost behavior</span></span></th>
<th><span data-ttu-id="2365a-187">Importe</span><span class="sxs-lookup"><span data-stu-id="2365a-187">Amount</span></span></th>
<th><span data-ttu-id="2365a-188">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="2365a-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-189">CC099</span><span class="sxs-lookup"><span data-stu-id="2365a-189">CC099</span></span></td>
<td><span data-ttu-id="2365a-190">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="2365a-190">Default cost center</span></span></td>
<td><span data-ttu-id="2365a-191">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-191">10001</span></span></td>
<td><span data-ttu-id="2365a-192">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-192">Electricity</span></span></td>
<td><span data-ttu-id="2365a-193">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="2365a-193">Unclassified</span></span></td>
<td><span data-ttu-id="2365a-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="2365a-194">10,000.00</span></span></td>
<td><span data-ttu-id="2365a-195">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-196">CC099</span><span class="sxs-lookup"><span data-stu-id="2365a-196">CC099</span></span></td>
<td><span data-ttu-id="2365a-197">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="2365a-197">Default cost center</span></span></td>
<td><span data-ttu-id="2365a-198">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-198">10001</span></span></td>
<td><span data-ttu-id="2365a-199">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-199">Electricity</span></span></td>
<td><span data-ttu-id="2365a-200">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="2365a-200">Unclassified</span></span></td>
<td><span data-ttu-id="2365a-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="2365a-201">-10,000.00</span></span></td>
<td><span data-ttu-id="2365a-202">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-203">CC099</span><span class="sxs-lookup"><span data-stu-id="2365a-203">CC099</span></span></td>
<td><span data-ttu-id="2365a-204">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="2365a-204">Default cost center</span></span></td>
<td><span data-ttu-id="2365a-205">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-205">10001</span></span></td>
<td><span data-ttu-id="2365a-206">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-206">Electricity</span></span></td>
<td><span data-ttu-id="2365a-207">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-207">Fixed cost</span></span></td>
<td><span data-ttu-id="2365a-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="2365a-208">1,000.00</span></span></td>
<td><span data-ttu-id="2365a-209">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-210">CC099</span><span class="sxs-lookup"><span data-stu-id="2365a-210">CC099</span></span></td>
<td><span data-ttu-id="2365a-211">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="2365a-211">Default cost center</span></span></td>
<td><span data-ttu-id="2365a-212">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-212">10001</span></span></td>
<td><span data-ttu-id="2365a-213">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-213">Electricity</span></span></td>
<td><span data-ttu-id="2365a-214">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-214">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="2365a-215">9,000.00</span></span></td>
<td><span data-ttu-id="2365a-216">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2365a-217">Para obtener más información, consulte [Crear y asignar una directiva de comportamiento de costes a una unidad de control de costes](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="2365a-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="2365a-218">Paso 2: Procese el cálculo de distribución de costes</span><span class="sxs-lookup"><span data-stu-id="2365a-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="2365a-219">La distribución de costes se usa para redistribuir costes desde un objeto de coste a uno o más objetos de coste aplicando una base relevante de la asignación.</span><span class="sxs-lookup"><span data-stu-id="2365a-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="2365a-220">La distribución de costes y la asignación de costes difieren en que la distribución de costes siempre se produce en el nivel de elemento de costes principal del coste original.</span><span class="sxs-lookup"><span data-stu-id="2365a-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="2365a-221">Defina la regla de distribución del coste</span><span class="sxs-lookup"><span data-stu-id="2365a-221">Define the cost distribution rule</span></span>

<span data-ttu-id="2365a-222">En la contabilidad financiera, los costes de electricidad se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="2365a-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="2365a-223">En contabilidad de costes, este método no es suficientemente detallado.</span><span class="sxs-lookup"><span data-stu-id="2365a-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="2365a-224">El coste variable debe distribuirse a los objetos individuales de coste aplicando una base justa.</span><span class="sxs-lookup"><span data-stu-id="2365a-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="2365a-225">La base de asignación más lógica es el consumo de electricidad (Kwh).</span><span class="sxs-lookup"><span data-stu-id="2365a-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="2365a-226">Se crea un miembro de dimensión estadística que se denomina Electricity, y se registra el consumo de electricidad.</span><span class="sxs-lookup"><span data-stu-id="2365a-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="2365a-227">De forma predeterminada, todos los miembros de dimensión estadísticos estarán disponibles como bases de asignación.</span><span class="sxs-lookup"><span data-stu-id="2365a-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2365a-228">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-228">Cost object</span></span></th>
<th><span data-ttu-id="2365a-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="2365a-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-230">CC001</span><span class="sxs-lookup"><span data-stu-id="2365a-230">CC001</span></span></td>
<td><span data-ttu-id="2365a-231">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="2365a-231">HR</span></span></td>
<td><span data-ttu-id="2365a-232">1.000</span><span class="sxs-lookup"><span data-stu-id="2365a-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-233">CC002</span><span class="sxs-lookup"><span data-stu-id="2365a-233">CC002</span></span></td>
<td><span data-ttu-id="2365a-234">Finanzas</span><span class="sxs-lookup"><span data-stu-id="2365a-234">Finance</span></span></td>
<td><span data-ttu-id="2365a-235">6.000</span><span class="sxs-lookup"><span data-stu-id="2365a-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-236">CC003</span><span class="sxs-lookup"><span data-stu-id="2365a-236">CC003</span></span></td>
<td><span data-ttu-id="2365a-237">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="2365a-237">Assembly</span></span></td>
<td><span data-ttu-id="2365a-238">0</span><span class="sxs-lookup"><span data-stu-id="2365a-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2365a-239">La tabla siguiente muestra el resultado cuando se aplica el consumo de electricidad como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="2365a-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2365a-240">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-240">Cost object</span></span></th>
<th><span data-ttu-id="2365a-241">Magnitud</span><span class="sxs-lookup"><span data-stu-id="2365a-241">Magnitude</span></span></th>
<th><span data-ttu-id="2365a-242">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="2365a-242">Allocation factor</span></span></th>
<th><span data-ttu-id="2365a-243">Importe</span><span class="sxs-lookup"><span data-stu-id="2365a-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-244">CC001</span><span class="sxs-lookup"><span data-stu-id="2365a-244">CC001</span></span></td>
<td><span data-ttu-id="2365a-245">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="2365a-245">HR</span></span></td>
<td><span data-ttu-id="2365a-246">1.000</span><span class="sxs-lookup"><span data-stu-id="2365a-246">1,000</span></span></td>
<td><span data-ttu-id="2365a-247">(1.000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="2365a-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="2365a-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="2365a-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-249">CC002</span><span class="sxs-lookup"><span data-stu-id="2365a-249">CC002</span></span></td>
<td><span data-ttu-id="2365a-250">Finanzas</span><span class="sxs-lookup"><span data-stu-id="2365a-250">Finance</span></span></td>
<td><span data-ttu-id="2365a-251">6.000</span><span class="sxs-lookup"><span data-stu-id="2365a-251">6,000</span></span></td>
<td><span data-ttu-id="2365a-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="2365a-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="2365a-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="2365a-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-254">CC003</span><span class="sxs-lookup"><span data-stu-id="2365a-254">CC003</span></span></td>
<td><span data-ttu-id="2365a-255">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="2365a-255">Assembly</span></span></td>
<td><span data-ttu-id="2365a-256">0</span><span class="sxs-lookup"><span data-stu-id="2365a-256">0</span></span></td>
<td><span data-ttu-id="2365a-257">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="2365a-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="2365a-258">0,00</span><span class="sxs-lookup"><span data-stu-id="2365a-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2365a-259">El coste fijo debe distribuirse uniformemente a los objetos individuales de costes que han consumido electricidad.</span><span class="sxs-lookup"><span data-stu-id="2365a-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="2365a-260">Puede obtener este resultado usando el miembro de dimensión estadístico de electricidad en una base de asignación de la fórmula: (Electricidad &gt; 0,00) La tabla siguiente muestra el resultado cuando el consumo de electricidad se aplica como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="2365a-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2365a-261">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-261">Cost object</span></span></th>
<th><span data-ttu-id="2365a-262">Fórmula</span><span class="sxs-lookup"><span data-stu-id="2365a-262">Formula</span></span></th>
<th><span data-ttu-id="2365a-263">Magnitud</span><span class="sxs-lookup"><span data-stu-id="2365a-263">Magnitude</span></span></th>
<th><span data-ttu-id="2365a-264">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="2365a-264">Allocation factor</span></span></th>
<th><span data-ttu-id="2365a-265">Importe</span><span class="sxs-lookup"><span data-stu-id="2365a-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-266">CC001</span><span class="sxs-lookup"><span data-stu-id="2365a-266">CC001</span></span></td>
<td><span data-ttu-id="2365a-267">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="2365a-267">HR</span></span></td>
<td><span data-ttu-id="2365a-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="2365a-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="2365a-269">1</span><span class="sxs-lookup"><span data-stu-id="2365a-269">1</span></span></td>
<td><span data-ttu-id="2365a-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="2365a-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="2365a-271">500,00</span><span class="sxs-lookup"><span data-stu-id="2365a-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-272">CC002</span><span class="sxs-lookup"><span data-stu-id="2365a-272">CC002</span></span></td>
<td><span data-ttu-id="2365a-273">Finanzas</span><span class="sxs-lookup"><span data-stu-id="2365a-273">Finance</span></span></td>
<td><span data-ttu-id="2365a-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="2365a-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="2365a-275">1</span><span class="sxs-lookup"><span data-stu-id="2365a-275">1</span></span></td>
<td><span data-ttu-id="2365a-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="2365a-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="2365a-277">500,00</span><span class="sxs-lookup"><span data-stu-id="2365a-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-278">CC003</span><span class="sxs-lookup"><span data-stu-id="2365a-278">CC003</span></span></td>
<td><span data-ttu-id="2365a-279">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="2365a-279">Assembly</span></span></td>
<td><span data-ttu-id="2365a-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="2365a-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="2365a-281">0</span><span class="sxs-lookup"><span data-stu-id="2365a-281">0</span></span></td>
<td><span data-ttu-id="2365a-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="2365a-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="2365a-283">0,00</span><span class="sxs-lookup"><span data-stu-id="2365a-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="2365a-284">Diario</span><span class="sxs-lookup"><span data-stu-id="2365a-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2365a-285">Diario</span><span class="sxs-lookup"><span data-stu-id="2365a-285">Journal</span></span></th>
<th><span data-ttu-id="2365a-286">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="2365a-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="2365a-287">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="2365a-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="2365a-288">Versión</span><span class="sxs-lookup"><span data-stu-id="2365a-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-289">00002</span><span class="sxs-lookup"><span data-stu-id="2365a-289">00002</span></span></td>
<td><span data-ttu-id="2365a-290">Diario de cálculo de la distribución de costes</span><span class="sxs-lookup"><span data-stu-id="2365a-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="2365a-291">Fiscal</span><span class="sxs-lookup"><span data-stu-id="2365a-291">Fiscal</span></span></td>
<td><span data-ttu-id="2365a-292">2017</span><span class="sxs-lookup"><span data-stu-id="2365a-292">2017</span></span></td>
<td><span data-ttu-id="2365a-293">Período 1</span><span class="sxs-lookup"><span data-stu-id="2365a-293">Period 1</span></span></td>
<td><span data-ttu-id="2365a-294">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="2365a-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="2365a-295">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="2365a-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2365a-296">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="2365a-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="2365a-297">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2365a-298">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-298">Cost element</span></span></th>
<th><span data-ttu-id="2365a-299">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="2365a-299">Cost behavior</span></span></th>
<th><span data-ttu-id="2365a-300">Importe</span><span class="sxs-lookup"><span data-stu-id="2365a-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-301">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="2365a-302">CC099</span><span class="sxs-lookup"><span data-stu-id="2365a-302">CC099</span></span></td>
<td><span data-ttu-id="2365a-303">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="2365a-303">Default cost center</span></span></td>
<td><span data-ttu-id="2365a-304">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-304">10001</span></span></td>
<td><span data-ttu-id="2365a-305">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-305">Electricity</span></span></td>
<td><span data-ttu-id="2365a-306">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-306">Fixed cost</span></span></td>
<td><span data-ttu-id="2365a-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="2365a-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-308">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="2365a-309">CC099</span><span class="sxs-lookup"><span data-stu-id="2365a-309">CC099</span></span></td>
<td><span data-ttu-id="2365a-310">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="2365a-310">Default cost center</span></span></td>
<td><span data-ttu-id="2365a-311">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-311">10001</span></span></td>
<td><span data-ttu-id="2365a-312">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-312">Electricity</span></span></td>
<td><span data-ttu-id="2365a-313">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-313">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-314">9.000,00</span><span class="sxs-lookup"><span data-stu-id="2365a-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="2365a-315">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="2365a-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2365a-316">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2365a-317">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-317">Cost element</span></span></th>
<th><span data-ttu-id="2365a-318">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="2365a-318">Cost behavior</span></span></th>
<th><span data-ttu-id="2365a-319">Importe</span><span class="sxs-lookup"><span data-stu-id="2365a-319">Amount</span></span></th>
<th><span data-ttu-id="2365a-320">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="2365a-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-321">CC099</span><span class="sxs-lookup"><span data-stu-id="2365a-321">CC099</span></span></td>
<td><span data-ttu-id="2365a-322">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="2365a-322">Default cost center</span></span></td>
<td><span data-ttu-id="2365a-323">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-323">10001</span></span></td>
<td><span data-ttu-id="2365a-324">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-324">Electricity</span></span></td>
<td><span data-ttu-id="2365a-325">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-325">Fixed cost</span></span></td>
<td><span data-ttu-id="2365a-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="2365a-326">-1,000.00</span></span></td>
<td><span data-ttu-id="2365a-327">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-328">CC001</span><span class="sxs-lookup"><span data-stu-id="2365a-328">CC001</span></span></td>
<td><span data-ttu-id="2365a-329">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="2365a-329">HR</span></span></td>
<td><span data-ttu-id="2365a-330">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-330">10001</span></span></td>
<td><span data-ttu-id="2365a-331">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-331">Electricity</span></span></td>
<td><span data-ttu-id="2365a-332">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-332">Fixed cost</span></span></td>
<td><span data-ttu-id="2365a-333">500,00</span><span class="sxs-lookup"><span data-stu-id="2365a-333">500.00</span></span></td>
<td><span data-ttu-id="2365a-334">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-335">CC002</span><span class="sxs-lookup"><span data-stu-id="2365a-335">CC002</span></span></td>
<td><span data-ttu-id="2365a-336">Finanzas</span><span class="sxs-lookup"><span data-stu-id="2365a-336">Finance</span></span></td>
<td><span data-ttu-id="2365a-337">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-337">10001</span></span></td>
<td><span data-ttu-id="2365a-338">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-338">Electricity</span></span></td>
<td><span data-ttu-id="2365a-339">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-339">Fixed cost</span></span></td>
<td><span data-ttu-id="2365a-340">500,00</span><span class="sxs-lookup"><span data-stu-id="2365a-340">500.00</span></span></td>
<td><span data-ttu-id="2365a-341">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-342">CC099</span><span class="sxs-lookup"><span data-stu-id="2365a-342">CC099</span></span></td>
<td><span data-ttu-id="2365a-343">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="2365a-343">Default cost center</span></span></td>
<td><span data-ttu-id="2365a-344">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-344">10001</span></span></td>
<td><span data-ttu-id="2365a-345">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-345">Electricity</span></span></td>
<td><span data-ttu-id="2365a-346">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-346">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="2365a-347">-9,000.00</span></span></td>
<td><span data-ttu-id="2365a-348">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-349">CC001</span><span class="sxs-lookup"><span data-stu-id="2365a-349">CC001</span></span></td>
<td><span data-ttu-id="2365a-350">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="2365a-350">HR</span></span></td>
<td><span data-ttu-id="2365a-351">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-351">10001</span></span></td>
<td><span data-ttu-id="2365a-352">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-352">Electricity</span></span></td>
<td><span data-ttu-id="2365a-353">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-353">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="2365a-354">1,285.71</span></span></td>
<td><span data-ttu-id="2365a-355">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-356">CC002</span><span class="sxs-lookup"><span data-stu-id="2365a-356">CC002</span></span></td>
<td><span data-ttu-id="2365a-357">Finanzas</span><span class="sxs-lookup"><span data-stu-id="2365a-357">Finance</span></span></td>
<td><span data-ttu-id="2365a-358">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-358">10001</span></span></td>
<td><span data-ttu-id="2365a-359">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-359">Electricity</span></span></td>
<td><span data-ttu-id="2365a-360">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-360">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="2365a-361">7,714.29</span></span></td>
<td><span data-ttu-id="2365a-362">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2365a-363">Para obtener más información, consulte [Crear y asignar una directiva de distribución de costes a una unidad de control de costes](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="2365a-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="2365a-364">Paso 3: Procese el cálculo de las tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="2365a-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="2365a-365">La tasa de costes generales se usa para cargar uno o varios objetos de coste específicos.</span><span class="sxs-lookup"><span data-stu-id="2365a-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="2365a-366">El cargo se basa en un índice de coste predeterminado y la magnitud de la base de asignación asignada.</span><span class="sxs-lookup"><span data-stu-id="2365a-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="2365a-367">Defina la tasa de costes generales</span><span class="sxs-lookup"><span data-stu-id="2365a-367">Define the overhead rate</span></span>

<span data-ttu-id="2365a-368">El objeto de coste CC001 HR contribuye a un conjunto de proyectos internos.</span><span class="sxs-lookup"><span data-stu-id="2365a-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="2365a-369">Se crea un miembro de dimensión estadística que se denomina proyectos HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="2365a-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2365a-370">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-370">Cost object</span></span></th>
<th><span data-ttu-id="2365a-371">Horas</span><span class="sxs-lookup"><span data-stu-id="2365a-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-372">Proy 1</span><span class="sxs-lookup"><span data-stu-id="2365a-372">Proj 1</span></span></td>
<td><span data-ttu-id="2365a-373">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="2365a-373">Project 1</span></span></td>
<td><span data-ttu-id="2365a-374">3</span><span class="sxs-lookup"><span data-stu-id="2365a-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-375">Proy 2</span><span class="sxs-lookup"><span data-stu-id="2365a-375">Proj 2</span></span></td>
<td><span data-ttu-id="2365a-376">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="2365a-376">Project 2</span></span></td>
<td><span data-ttu-id="2365a-377">1</span><span class="sxs-lookup"><span data-stu-id="2365a-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2365a-378">Una tasa de coste predeterminada para la contribución de los proyectos de coste se ha definido.</span><span class="sxs-lookup"><span data-stu-id="2365a-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2365a-379">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-379">Cost object</span></span></th>
<th><span data-ttu-id="2365a-380">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-380">Cost element</span></span></th>
<th><span data-ttu-id="2365a-381">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="2365a-381">Cost behavior</span></span></th>
<th><span data-ttu-id="2365a-382">Unidades</span><span class="sxs-lookup"><span data-stu-id="2365a-382">Units</span></span></th>
<th><span data-ttu-id="2365a-383">Índice</span><span class="sxs-lookup"><span data-stu-id="2365a-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-384">CC001</span><span class="sxs-lookup"><span data-stu-id="2365a-384">CC001</span></span></td>
<td><span data-ttu-id="2365a-385">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="2365a-385">HR</span></span></td>
<td><span data-ttu-id="2365a-386">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-386">10001</span></span></td>
<td><span data-ttu-id="2365a-387">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-387">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-388">1</span><span class="sxs-lookup"><span data-stu-id="2365a-388">1</span></span></td>
<td><span data-ttu-id="2365a-389">10</span><span class="sxs-lookup"><span data-stu-id="2365a-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2365a-390">La tabla siguiente muestra el resultado cuando los proyectos HR se aplican como base de la asignación.</span><span class="sxs-lookup"><span data-stu-id="2365a-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2365a-391">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-391">Cost object</span></span></th>
<th><span data-ttu-id="2365a-392">Magnitud</span><span class="sxs-lookup"><span data-stu-id="2365a-392">Magnitude</span></span></th>
<th><span data-ttu-id="2365a-393">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-393">Cost element</span></span></th>
<th><span data-ttu-id="2365a-394">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="2365a-394">Allocation factor</span></span></th>
<th><span data-ttu-id="2365a-395">Importe</span><span class="sxs-lookup"><span data-stu-id="2365a-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-396">Proy 1</span><span class="sxs-lookup"><span data-stu-id="2365a-396">Proj 1</span></span></td>
<td><span data-ttu-id="2365a-397">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="2365a-397">Project 1</span></span></td>
<td><span data-ttu-id="2365a-398">3</span><span class="sxs-lookup"><span data-stu-id="2365a-398">3</span></span></td>
<td><span data-ttu-id="2365a-399">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-399">10001</span></span></td>
<td><span data-ttu-id="2365a-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="2365a-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="2365a-401">30,00</span><span class="sxs-lookup"><span data-stu-id="2365a-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-402">Proy 2</span><span class="sxs-lookup"><span data-stu-id="2365a-402">Proj 2</span></span></td>
<td><span data-ttu-id="2365a-403">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="2365a-403">Project 2</span></span></td>
<td><span data-ttu-id="2365a-404">1</span><span class="sxs-lookup"><span data-stu-id="2365a-404">1</span></span></td>
<td><span data-ttu-id="2365a-405">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-405">10001</span></span></td>
<td><span data-ttu-id="2365a-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="2365a-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="2365a-407">10,00</span><span class="sxs-lookup"><span data-stu-id="2365a-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="2365a-408">Diario</span><span class="sxs-lookup"><span data-stu-id="2365a-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2365a-409">Diario</span><span class="sxs-lookup"><span data-stu-id="2365a-409">Journal</span></span></th>
<th><span data-ttu-id="2365a-410">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="2365a-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="2365a-411">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="2365a-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="2365a-412">Versión</span><span class="sxs-lookup"><span data-stu-id="2365a-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-413">00003</span><span class="sxs-lookup"><span data-stu-id="2365a-413">00003</span></span></td>
<td><span data-ttu-id="2365a-414">Diario de cálculo de tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="2365a-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="2365a-415">Fiscal</span><span class="sxs-lookup"><span data-stu-id="2365a-415">Fiscal</span></span></td>
<td><span data-ttu-id="2365a-416">2017</span><span class="sxs-lookup"><span data-stu-id="2365a-416">2017</span></span></td>
<td><span data-ttu-id="2365a-417">Período 1</span><span class="sxs-lookup"><span data-stu-id="2365a-417">Period 1</span></span></td>
<td><span data-ttu-id="2365a-418">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="2365a-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="2365a-419">Entradas de diario (entradas de diario para cálculo de tasas de costes generales)</span><span class="sxs-lookup"><span data-stu-id="2365a-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2365a-420">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="2365a-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="2365a-421">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-421">Cost object</span></span></th>
<th><span data-ttu-id="2365a-422">Magnitud</span><span class="sxs-lookup"><span data-stu-id="2365a-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-423">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="2365a-424">Proy 1</span><span class="sxs-lookup"><span data-stu-id="2365a-424">Proj 1</span></span></td>
<td><span data-ttu-id="2365a-425">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="2365a-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="2365a-426">3,00</span><span class="sxs-lookup"><span data-stu-id="2365a-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-427">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="2365a-428">Proy 2</span><span class="sxs-lookup"><span data-stu-id="2365a-428">Proj 2</span></span></td>
<td><span data-ttu-id="2365a-429">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="2365a-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="2365a-430">1,00</span><span class="sxs-lookup"><span data-stu-id="2365a-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="2365a-431">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="2365a-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2365a-432">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2365a-433">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-433">Cost element</span></span></th>
<th><span data-ttu-id="2365a-434">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="2365a-434">Cost behavior</span></span></th>
<th><span data-ttu-id="2365a-435">Importe</span><span class="sxs-lookup"><span data-stu-id="2365a-435">Amount</span></span></th>
<th><span data-ttu-id="2365a-436">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="2365a-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="2365a-437">CC0001</span></span></td>
<td><span data-ttu-id="2365a-438">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="2365a-438">HR</span></span></td>
<td><span data-ttu-id="2365a-439">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-439">10001</span></span></td>
<td><span data-ttu-id="2365a-440">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-440">Electricity</span></span></td>
<td><span data-ttu-id="2365a-441">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-441">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="2365a-442">-30.00</span></span></td>
<td><span data-ttu-id="2365a-443">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-444">Proy 1</span><span class="sxs-lookup"><span data-stu-id="2365a-444">Proj 1</span></span></td>
<td><span data-ttu-id="2365a-445">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="2365a-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="2365a-446">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-446">10001</span></span></td>
<td><span data-ttu-id="2365a-447">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-447">Electricity</span></span></td>
<td><span data-ttu-id="2365a-448">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-448">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-449">30,00</span><span class="sxs-lookup"><span data-stu-id="2365a-449">30.00</span></span></td>
<td><span data-ttu-id="2365a-450">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-451">CC001</span><span class="sxs-lookup"><span data-stu-id="2365a-451">CC001</span></span></td>
<td><span data-ttu-id="2365a-452">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="2365a-452">HR</span></span></td>
<td><span data-ttu-id="2365a-453">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-453">10001</span></span></td>
<td><span data-ttu-id="2365a-454">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-454">Electricity</span></span></td>
<td><span data-ttu-id="2365a-455">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-455">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="2365a-456">-10.00</span></span></td>
<td><span data-ttu-id="2365a-457">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-458">Proy 2</span><span class="sxs-lookup"><span data-stu-id="2365a-458">Proj 2</span></span></td>
<td><span data-ttu-id="2365a-459">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="2365a-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="2365a-460">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-460">10001</span></span></td>
<td><span data-ttu-id="2365a-461">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-461">Electricity</span></span></td>
<td><span data-ttu-id="2365a-462">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-462">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-463">10,00</span><span class="sxs-lookup"><span data-stu-id="2365a-463">10.00</span></span></td>
<td><span data-ttu-id="2365a-464">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2365a-465">Para obtener más información, consulte [Realizar cálculo de costes generales](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="2365a-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="2365a-466">Paso 4: Procese el cálculo de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="2365a-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="2365a-467">La asignación es utilizada para asignar el saldo de un objeto de coste a otros objetos de coste aplicando una base de asignación.</span><span class="sxs-lookup"><span data-stu-id="2365a-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="2365a-468">Finance admite el método de asignación recíproco.</span><span class="sxs-lookup"><span data-stu-id="2365a-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="2365a-469">En el método de asignación recíproco, se reconocen completamente los servicios mutuos que los objetos de coste auxiliar intercambian.</span><span class="sxs-lookup"><span data-stu-id="2365a-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="2365a-470">El sistema determina automáticamente el orden correcto para realizar las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="2365a-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="2365a-471">El saldo de un objeto de coste se asigna según una única base de asignación.</span><span class="sxs-lookup"><span data-stu-id="2365a-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="2365a-472">Las asignaciones entre dimensiones de objetos de coste y sus miembros respectivos se admiten.</span><span class="sxs-lookup"><span data-stu-id="2365a-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="2365a-473">El orden de asignación se controla por unidad de control de costes.</span><span class="sxs-lookup"><span data-stu-id="2365a-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="2365a-474">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="2365a-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="2365a-475">Defina la asignación de costes</span><span class="sxs-lookup"><span data-stu-id="2365a-475">Define the cost allocation</span></span>

<span data-ttu-id="2365a-476">A continuación se indica un ejemplo sencillo que explica cómo puede realizar el seguimiento del flujo de coste.</span><span class="sxs-lookup"><span data-stu-id="2365a-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="2365a-477">El objeto de coste CC001 HR contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="2365a-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="2365a-478">Se crea un miembro de dimensión estadística que se denomina servicios HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="2365a-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2365a-479">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-479">Cost object</span></span></th>
<th><span data-ttu-id="2365a-480">Servicios HR</span><span class="sxs-lookup"><span data-stu-id="2365a-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-481">CC002</span><span class="sxs-lookup"><span data-stu-id="2365a-481">CC002</span></span></td>
<td><span data-ttu-id="2365a-482">Finanzas</span><span class="sxs-lookup"><span data-stu-id="2365a-482">Finance</span></span></td>
<td><span data-ttu-id="2365a-483">35</span><span class="sxs-lookup"><span data-stu-id="2365a-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-484">CC003</span><span class="sxs-lookup"><span data-stu-id="2365a-484">CC003</span></span></td>
<td><span data-ttu-id="2365a-485">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="2365a-485">Assembly</span></span></td>
<td><span data-ttu-id="2365a-486">55</span><span class="sxs-lookup"><span data-stu-id="2365a-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-487">CC004</span><span class="sxs-lookup"><span data-stu-id="2365a-487">CC004</span></span></td>
<td><span data-ttu-id="2365a-488">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="2365a-488">Packaging</span></span></td>
<td><span data-ttu-id="2365a-489">10</span><span class="sxs-lookup"><span data-stu-id="2365a-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2365a-490">El objeto de coste CC002 Finanzas contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="2365a-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="2365a-491">Se crea un miembro de dimensión estadística que se denomina Finanzas para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="2365a-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2365a-492">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-492">Cost object</span></span></th>
<th><span data-ttu-id="2365a-493">Servicios financieros</span><span class="sxs-lookup"><span data-stu-id="2365a-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-494">CC003</span><span class="sxs-lookup"><span data-stu-id="2365a-494">CC003</span></span></td>
<td><span data-ttu-id="2365a-495">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="2365a-495">Assembly</span></span></td>
<td><span data-ttu-id="2365a-496">65</span><span class="sxs-lookup"><span data-stu-id="2365a-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-497">CC004</span><span class="sxs-lookup"><span data-stu-id="2365a-497">CC004</span></span></td>
<td><span data-ttu-id="2365a-498">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="2365a-498">Packaging</span></span></td>
<td><span data-ttu-id="2365a-499">35</span><span class="sxs-lookup"><span data-stu-id="2365a-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2365a-500">El objeto de coste CC003 Asamblea contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="2365a-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="2365a-501">Se crea un miembro de dimensión estadística que se denomina servicios de Asamblea para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="2365a-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2365a-502">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-502">Cost object</span></span></th>
<th><span data-ttu-id="2365a-503">Servicios de la asamblea (horas)</span><span class="sxs-lookup"><span data-stu-id="2365a-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2365a-504">Prod 1</span></span></td>
<td><span data-ttu-id="2365a-505">Producto 1</span><span class="sxs-lookup"><span data-stu-id="2365a-505">Product 1</span></span></td>
<td><span data-ttu-id="2365a-506">60</span><span class="sxs-lookup"><span data-stu-id="2365a-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2365a-507">Prod 2</span></span></td>
<td><span data-ttu-id="2365a-508">Producto 2</span><span class="sxs-lookup"><span data-stu-id="2365a-508">Product 2</span></span></td>
<td><span data-ttu-id="2365a-509">20</span><span class="sxs-lookup"><span data-stu-id="2365a-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2365a-510">El objeto de coste CC004 Embalaje contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="2365a-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="2365a-511">Se crea un miembro de dimensión estadística que se denomina servicios de Embalaje para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="2365a-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2365a-512">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-512">Cost object</span></span></th>
<th><span data-ttu-id="2365a-513">Servicios de embalaje (horas)</span><span class="sxs-lookup"><span data-stu-id="2365a-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2365a-514">Prod 1</span></span></td>
<td><span data-ttu-id="2365a-515">Producto 1</span><span class="sxs-lookup"><span data-stu-id="2365a-515">Product 1</span></span></td>
<td><span data-ttu-id="2365a-516">80</span><span class="sxs-lookup"><span data-stu-id="2365a-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2365a-517">Prod 2</span></span></td>
<td><span data-ttu-id="2365a-518">Producto 2</span><span class="sxs-lookup"><span data-stu-id="2365a-518">Product 2</span></span></td>
<td><span data-ttu-id="2365a-519">15</span><span class="sxs-lookup"><span data-stu-id="2365a-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="2365a-520">Las medidas estadísticas como las horas de la producción que un producto consume se pueden deducir de los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="2365a-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="2365a-521">Para obtener más información, vea [Plantilla de proveedor de medidas estadísticas](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="2365a-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="2365a-522">La tabla siguiente muestra el resultado cuando se aplican los servicios de HR como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="2365a-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2365a-523">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-523">Cost object</span></span></th>
<th><span data-ttu-id="2365a-524">Magnitud</span><span class="sxs-lookup"><span data-stu-id="2365a-524">Magnitude</span></span></th>
<th><span data-ttu-id="2365a-525">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="2365a-525">Allocation factor</span></span></th>
<th><span data-ttu-id="2365a-526">Importe</span><span class="sxs-lookup"><span data-stu-id="2365a-526">Amount</span></span></th>
<th><span data-ttu-id="2365a-527">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="2365a-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-528">CC002</span><span class="sxs-lookup"><span data-stu-id="2365a-528">CC002</span></span></td>
<td><span data-ttu-id="2365a-529">Finanzas</span><span class="sxs-lookup"><span data-stu-id="2365a-529">Finance</span></span></td>
<td><span data-ttu-id="2365a-530">35</span><span class="sxs-lookup"><span data-stu-id="2365a-530">35</span></span></td>
<td><span data-ttu-id="2365a-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="2365a-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="2365a-532">175.00</span><span class="sxs-lookup"><span data-stu-id="2365a-532">175.00</span></span></td>
<td><span data-ttu-id="2365a-533">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-534">CC003</span><span class="sxs-lookup"><span data-stu-id="2365a-534">CC003</span></span></td>
<td><span data-ttu-id="2365a-535">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="2365a-535">Assembly</span></span></td>
<td><span data-ttu-id="2365a-536">55</span><span class="sxs-lookup"><span data-stu-id="2365a-536">55</span></span></td>
<td><span data-ttu-id="2365a-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="2365a-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="2365a-538">275.00</span><span class="sxs-lookup"><span data-stu-id="2365a-538">275.00</span></span></td>
<td><span data-ttu-id="2365a-539">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-540">CC004</span><span class="sxs-lookup"><span data-stu-id="2365a-540">CC004</span></span></td>
<td><span data-ttu-id="2365a-541">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="2365a-541">Packaging</span></span></td>
<td><span data-ttu-id="2365a-542">10</span><span class="sxs-lookup"><span data-stu-id="2365a-542">10</span></span></td>
<td><span data-ttu-id="2365a-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="2365a-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="2365a-544">50,00</span><span class="sxs-lookup"><span data-stu-id="2365a-544">50.00</span></span></td>
<td><span data-ttu-id="2365a-545">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-546">CC002</span><span class="sxs-lookup"><span data-stu-id="2365a-546">CC002</span></span></td>
<td><span data-ttu-id="2365a-547">Finanzas</span><span class="sxs-lookup"><span data-stu-id="2365a-547">Finance</span></span></td>
<td><span data-ttu-id="2365a-548">35</span><span class="sxs-lookup"><span data-stu-id="2365a-548">35</span></span></td>
<td><span data-ttu-id="2365a-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="2365a-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="2365a-550">436.00</span><span class="sxs-lookup"><span data-stu-id="2365a-550">436.00</span></span></td>
<td><span data-ttu-id="2365a-551">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-552">CC003</span><span class="sxs-lookup"><span data-stu-id="2365a-552">CC003</span></span></td>
<td><span data-ttu-id="2365a-553">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="2365a-553">Assembly</span></span></td>
<td><span data-ttu-id="2365a-554">55</span><span class="sxs-lookup"><span data-stu-id="2365a-554">55</span></span></td>
<td><span data-ttu-id="2365a-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="2365a-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="2365a-556">685.14</span><span class="sxs-lookup"><span data-stu-id="2365a-556">685.14</span></span></td>
<td><span data-ttu-id="2365a-557">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-558">CC004</span><span class="sxs-lookup"><span data-stu-id="2365a-558">CC004</span></span></td>
<td><span data-ttu-id="2365a-559">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="2365a-559">Packaging</span></span></td>
<td><span data-ttu-id="2365a-560">10</span><span class="sxs-lookup"><span data-stu-id="2365a-560">10</span></span></td>
<td><span data-ttu-id="2365a-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="2365a-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="2365a-562">124.57</span><span class="sxs-lookup"><span data-stu-id="2365a-562">124.57</span></span></td>
<td><span data-ttu-id="2365a-563">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2365a-564">La tabla siguiente muestra el resultado cuando se aplican los servicios de Finanzas como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="2365a-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2365a-565">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-565">Cost object</span></span></th>
<th><span data-ttu-id="2365a-566">Magnitud</span><span class="sxs-lookup"><span data-stu-id="2365a-566">Magnitude</span></span></th>
<th><span data-ttu-id="2365a-567">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="2365a-567">Allocation factor</span></span></th>
<th><span data-ttu-id="2365a-568">Importe</span><span class="sxs-lookup"><span data-stu-id="2365a-568">Amount</span></span></th>
<th><span data-ttu-id="2365a-569">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="2365a-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-570">CC003</span><span class="sxs-lookup"><span data-stu-id="2365a-570">CC003</span></span></td>
<td><span data-ttu-id="2365a-571">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="2365a-571">Assembly</span></span></td>
<td><span data-ttu-id="2365a-572">65</span><span class="sxs-lookup"><span data-stu-id="2365a-572">65</span></span></td>
<td><span data-ttu-id="2365a-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="2365a-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="2365a-574">438.75</span><span class="sxs-lookup"><span data-stu-id="2365a-574">438.75</span></span></td>
<td><span data-ttu-id="2365a-575">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-576">CC004</span><span class="sxs-lookup"><span data-stu-id="2365a-576">CC004</span></span></td>
<td><span data-ttu-id="2365a-577">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="2365a-577">Packaging</span></span></td>
<td><span data-ttu-id="2365a-578">35</span><span class="sxs-lookup"><span data-stu-id="2365a-578">35</span></span></td>
<td><span data-ttu-id="2365a-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="2365a-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="2365a-580">236.25</span><span class="sxs-lookup"><span data-stu-id="2365a-580">236.25</span></span></td>
<td><span data-ttu-id="2365a-581">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-582">CC003</span><span class="sxs-lookup"><span data-stu-id="2365a-582">CC003</span></span></td>
<td><span data-ttu-id="2365a-583">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="2365a-583">Assembly</span></span></td>
<td><span data-ttu-id="2365a-584">65</span><span class="sxs-lookup"><span data-stu-id="2365a-584">65</span></span></td>
<td><span data-ttu-id="2365a-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="2365a-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="2365a-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="2365a-586">5,297.69</span></span></td>
<td><span data-ttu-id="2365a-587">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-588">CC004</span><span class="sxs-lookup"><span data-stu-id="2365a-588">CC004</span></span></td>
<td><span data-ttu-id="2365a-589">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="2365a-589">Packaging</span></span></td>
<td><span data-ttu-id="2365a-590">35</span><span class="sxs-lookup"><span data-stu-id="2365a-590">35</span></span></td>
<td><span data-ttu-id="2365a-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="2365a-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="2365a-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="2365a-592">2,852.60</span></span></td>
<td><span data-ttu-id="2365a-593">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2365a-594">La tabla siguiente muestra el resultado cuando se aplican los servicios de Asamblea como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="2365a-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2365a-595">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-595">Cost object</span></span></th>
<th><span data-ttu-id="2365a-596">Magnitud</span><span class="sxs-lookup"><span data-stu-id="2365a-596">Magnitude</span></span></th>
<th><span data-ttu-id="2365a-597">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="2365a-597">Allocation factor</span></span></th>
<th><span data-ttu-id="2365a-598">Importe</span><span class="sxs-lookup"><span data-stu-id="2365a-598">Amount</span></span></th>
<th><span data-ttu-id="2365a-599">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="2365a-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2365a-600">Prod 1</span></span></td>
<td><span data-ttu-id="2365a-601">Producto 1</span><span class="sxs-lookup"><span data-stu-id="2365a-601">Product 1</span></span></td>
<td><span data-ttu-id="2365a-602">60</span><span class="sxs-lookup"><span data-stu-id="2365a-602">60</span></span></td>
<td><span data-ttu-id="2365a-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="2365a-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="2365a-604">535.31</span><span class="sxs-lookup"><span data-stu-id="2365a-604">535.31</span></span></td>
<td><span data-ttu-id="2365a-605">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2365a-606">Prod 2</span></span></td>
<td><span data-ttu-id="2365a-607">Producto 2</span><span class="sxs-lookup"><span data-stu-id="2365a-607">Product 2</span></span></td>
<td><span data-ttu-id="2365a-608">20</span><span class="sxs-lookup"><span data-stu-id="2365a-608">20</span></span></td>
<td><span data-ttu-id="2365a-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="2365a-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="2365a-610">178.44</span><span class="sxs-lookup"><span data-stu-id="2365a-610">178.44</span></span></td>
<td><span data-ttu-id="2365a-611">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2365a-612">Prod 1</span></span></td>
<td><span data-ttu-id="2365a-613">Producto 1</span><span class="sxs-lookup"><span data-stu-id="2365a-613">Product 1</span></span></td>
<td><span data-ttu-id="2365a-614">60</span><span class="sxs-lookup"><span data-stu-id="2365a-614">60</span></span></td>
<td><span data-ttu-id="2365a-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="2365a-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="2365a-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="2365a-616">4,487.12</span></span></td>
<td><span data-ttu-id="2365a-617">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2365a-618">Prod 2</span></span></td>
<td><span data-ttu-id="2365a-619">Producto 2</span><span class="sxs-lookup"><span data-stu-id="2365a-619">Product 2</span></span></td>
<td><span data-ttu-id="2365a-620">20</span><span class="sxs-lookup"><span data-stu-id="2365a-620">20</span></span></td>
<td><span data-ttu-id="2365a-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="2365a-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="2365a-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="2365a-622">1,495.71</span></span></td>
<td><span data-ttu-id="2365a-623">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2365a-624">La tabla siguiente muestra el resultado cuando se aplican los servicios de Embalaje como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="2365a-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2365a-625">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-625">Cost object</span></span></th>
<th><span data-ttu-id="2365a-626">Magnitud</span><span class="sxs-lookup"><span data-stu-id="2365a-626">Magnitude</span></span></th>
<th><span data-ttu-id="2365a-627">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="2365a-627">Allocation factor</span></span></th>
<th><span data-ttu-id="2365a-628">Importe</span><span class="sxs-lookup"><span data-stu-id="2365a-628">Amount</span></span></th>
<th><span data-ttu-id="2365a-629">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="2365a-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2365a-630">Prod 1</span></span></td>
<td><span data-ttu-id="2365a-631">Producto 1</span><span class="sxs-lookup"><span data-stu-id="2365a-631">Product 1</span></span></td>
<td><span data-ttu-id="2365a-632">80</span><span class="sxs-lookup"><span data-stu-id="2365a-632">80</span></span></td>
<td><span data-ttu-id="2365a-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="2365a-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="2365a-634">241.05</span><span class="sxs-lookup"><span data-stu-id="2365a-634">241.05</span></span></td>
<td><span data-ttu-id="2365a-635">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2365a-636">Prod 2</span></span></td>
<td><span data-ttu-id="2365a-637">Producto 2</span><span class="sxs-lookup"><span data-stu-id="2365a-637">Product 2</span></span></td>
<td><span data-ttu-id="2365a-638">15</span><span class="sxs-lookup"><span data-stu-id="2365a-638">15</span></span></td>
<td><span data-ttu-id="2365a-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="2365a-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="2365a-640">45.20</span><span class="sxs-lookup"><span data-stu-id="2365a-640">45.20</span></span></td>
<td><span data-ttu-id="2365a-641">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2365a-642">Prod 1</span></span></td>
<td><span data-ttu-id="2365a-643">Producto 1</span><span class="sxs-lookup"><span data-stu-id="2365a-643">Product 1</span></span></td>
<td><span data-ttu-id="2365a-644">80</span><span class="sxs-lookup"><span data-stu-id="2365a-644">80</span></span></td>
<td><span data-ttu-id="2365a-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="2365a-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="2365a-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="2365a-646">2,507.09</span></span></td>
<td><span data-ttu-id="2365a-647">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2365a-648">Prod 2</span></span></td>
<td><span data-ttu-id="2365a-649">Producto 2</span><span class="sxs-lookup"><span data-stu-id="2365a-649">Product 2</span></span></td>
<td><span data-ttu-id="2365a-650">15</span><span class="sxs-lookup"><span data-stu-id="2365a-650">15</span></span></td>
<td><span data-ttu-id="2365a-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="2365a-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="2365a-652">470.08</span><span class="sxs-lookup"><span data-stu-id="2365a-652">470.08</span></span></td>
<td><span data-ttu-id="2365a-653">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="2365a-654">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="2365a-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2365a-655">Diario</span><span class="sxs-lookup"><span data-stu-id="2365a-655">Journal</span></span></th>
<th><span data-ttu-id="2365a-656">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="2365a-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="2365a-657">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="2365a-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="2365a-658">Versión</span><span class="sxs-lookup"><span data-stu-id="2365a-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-659">00004</span><span class="sxs-lookup"><span data-stu-id="2365a-659">00004</span></span></td>
<td><span data-ttu-id="2365a-660">Diario de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="2365a-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="2365a-661">Fiscal</span><span class="sxs-lookup"><span data-stu-id="2365a-661">Fiscal</span></span></td>
<td><span data-ttu-id="2365a-662">2017</span><span class="sxs-lookup"><span data-stu-id="2365a-662">2017</span></span></td>
<td><span data-ttu-id="2365a-663">Período 1</span><span class="sxs-lookup"><span data-stu-id="2365a-663">Period 1</span></span></td>
<td><span data-ttu-id="2365a-664">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="2365a-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="2365a-665">Líneas de diario</span><span class="sxs-lookup"><span data-stu-id="2365a-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2365a-666">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="2365a-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="2365a-667">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2365a-668">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-668">Cost element</span></span></th>
<th><span data-ttu-id="2365a-669">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="2365a-669">Cost behavior</span></span></th>
<th><span data-ttu-id="2365a-670">Importe</span><span class="sxs-lookup"><span data-stu-id="2365a-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-671">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="2365a-672">CC001</span><span class="sxs-lookup"><span data-stu-id="2365a-672">CC001</span></span></td>
<td><span data-ttu-id="2365a-673">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="2365a-673">HR</span></span></td>
<td><span data-ttu-id="2365a-674">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-674">10001</span></span></td>
<td><span data-ttu-id="2365a-675">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-675">Electricity</span></span></td>
<td><span data-ttu-id="2365a-676">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-676">Fixed cost</span></span></td>
<td><span data-ttu-id="2365a-677">500,00</span><span class="sxs-lookup"><span data-stu-id="2365a-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-678">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="2365a-679">CC001</span><span class="sxs-lookup"><span data-stu-id="2365a-679">CC001</span></span></td>
<td><span data-ttu-id="2365a-680">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="2365a-680">HR</span></span></td>
<td><span data-ttu-id="2365a-681">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-681">10001</span></span></td>
<td><span data-ttu-id="2365a-682">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-682">Electricity</span></span></td>
<td><span data-ttu-id="2365a-683">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-683">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="2365a-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-685">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="2365a-686">CC002</span><span class="sxs-lookup"><span data-stu-id="2365a-686">CC002</span></span></td>
<td><span data-ttu-id="2365a-687">Finanzas</span><span class="sxs-lookup"><span data-stu-id="2365a-687">Finance</span></span></td>
<td><span data-ttu-id="2365a-688">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-688">10001</span></span></td>
<td><span data-ttu-id="2365a-689">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-689">Electricity</span></span></td>
<td><span data-ttu-id="2365a-690">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-690">Fixed cost</span></span></td>
<td><span data-ttu-id="2365a-691">675.00</span><span class="sxs-lookup"><span data-stu-id="2365a-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-692">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="2365a-693">CC002</span><span class="sxs-lookup"><span data-stu-id="2365a-693">CC002</span></span></td>
<td><span data-ttu-id="2365a-694">Finanzas</span><span class="sxs-lookup"><span data-stu-id="2365a-694">Finance</span></span></td>
<td><span data-ttu-id="2365a-695">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-695">10001</span></span></td>
<td><span data-ttu-id="2365a-696">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-696">Electricity</span></span></td>
<td><span data-ttu-id="2365a-697">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-697">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="2365a-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-699">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="2365a-700">CC003</span><span class="sxs-lookup"><span data-stu-id="2365a-700">CC003</span></span></td>
<td><span data-ttu-id="2365a-701">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="2365a-701">Assembly</span></span></td>
<td><span data-ttu-id="2365a-702">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-702">10001</span></span></td>
<td><span data-ttu-id="2365a-703">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-703">Electricity</span></span></td>
<td><span data-ttu-id="2365a-704">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-704">Fixed cost</span></span></td>
<td><span data-ttu-id="2365a-705">713.75</span><span class="sxs-lookup"><span data-stu-id="2365a-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-706">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="2365a-707">CC003</span><span class="sxs-lookup"><span data-stu-id="2365a-707">CC003</span></span></td>
<td><span data-ttu-id="2365a-708">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="2365a-708">Assembly</span></span></td>
<td><span data-ttu-id="2365a-709">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-709">10001</span></span></td>
<td><span data-ttu-id="2365a-710">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-710">Electricity</span></span></td>
<td><span data-ttu-id="2365a-711">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-711">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="2365a-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-713">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="2365a-714">CC003</span><span class="sxs-lookup"><span data-stu-id="2365a-714">CC003</span></span></td>
<td><span data-ttu-id="2365a-715">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="2365a-715">Packaging</span></span></td>
<td><span data-ttu-id="2365a-716">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-716">10001</span></span></td>
<td><span data-ttu-id="2365a-717">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-717">Electricity</span></span></td>
<td><span data-ttu-id="2365a-718">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-718">Fixed cost</span></span></td>
<td><span data-ttu-id="2365a-719">286.25</span><span class="sxs-lookup"><span data-stu-id="2365a-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-720">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="2365a-721">CC003</span><span class="sxs-lookup"><span data-stu-id="2365a-721">CC003</span></span></td>
<td><span data-ttu-id="2365a-722">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="2365a-722">Packaging</span></span></td>
<td><span data-ttu-id="2365a-723">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-723">10001</span></span></td>
<td><span data-ttu-id="2365a-724">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-724">Electricity</span></span></td>
<td><span data-ttu-id="2365a-725">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-725">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="2365a-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-727">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="2365a-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2365a-728">Prod 1</span></span></td>
<td><span data-ttu-id="2365a-729">Producto 1</span><span class="sxs-lookup"><span data-stu-id="2365a-729">Product 1</span></span></td>
<td><span data-ttu-id="2365a-730">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-730">10001</span></span></td>
<td><span data-ttu-id="2365a-731">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-731">Electricity</span></span></td>
<td><span data-ttu-id="2365a-732">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-732">Fixed cost</span></span></td>
<td><span data-ttu-id="2365a-733">776.36</span><span class="sxs-lookup"><span data-stu-id="2365a-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-734">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="2365a-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2365a-735">Prod 1</span></span></td>
<td><span data-ttu-id="2365a-736">Producto 1</span><span class="sxs-lookup"><span data-stu-id="2365a-736">Product 1</span></span></td>
<td><span data-ttu-id="2365a-737">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-737">10001</span></span></td>
<td><span data-ttu-id="2365a-738">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-738">Electricity</span></span></td>
<td><span data-ttu-id="2365a-739">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-739">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="2365a-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-741">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="2365a-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2365a-742">Prod 2</span></span></td>
<td><span data-ttu-id="2365a-743">Producto 1</span><span class="sxs-lookup"><span data-stu-id="2365a-743">Product 1</span></span></td>
<td><span data-ttu-id="2365a-744">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-744">10001</span></span></td>
<td><span data-ttu-id="2365a-745">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-745">Electricity</span></span></td>
<td><span data-ttu-id="2365a-746">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-746">Fixed cost</span></span></td>
<td><span data-ttu-id="2365a-747">223.64</span><span class="sxs-lookup"><span data-stu-id="2365a-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-748">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="2365a-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2365a-749">Prod 2</span></span></td>
<td><span data-ttu-id="2365a-750">Producto 1</span><span class="sxs-lookup"><span data-stu-id="2365a-750">Product 1</span></span></td>
<td><span data-ttu-id="2365a-751">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-751">10001</span></span></td>
<td><span data-ttu-id="2365a-752">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-752">Electricity</span></span></td>
<td><span data-ttu-id="2365a-753">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-753">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="2365a-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="2365a-755">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="2365a-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2365a-756">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2365a-757">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-757">Cost element</span></span></th>
<th><span data-ttu-id="2365a-758">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="2365a-758">Cost behavior</span></span></th>
<th><span data-ttu-id="2365a-759">Importe</span><span class="sxs-lookup"><span data-stu-id="2365a-759">Amount</span></span></th>
<th><span data-ttu-id="2365a-760">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="2365a-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2365a-761">CC001</span><span class="sxs-lookup"><span data-stu-id="2365a-761">CC001</span></span></td>
<td><span data-ttu-id="2365a-762">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="2365a-762">HR</span></span></td>
<td><span data-ttu-id="2365a-763">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-763">10001</span></span></td>
<td><span data-ttu-id="2365a-764">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-764">Electricity</span></span></td>
<td><span data-ttu-id="2365a-765">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-765">Fixed cost</span></span></td>
<td><span data-ttu-id="2365a-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="2365a-766">-500.00</span></span></td>
<td><span data-ttu-id="2365a-767">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-768">CC002</span><span class="sxs-lookup"><span data-stu-id="2365a-768">CC002</span></span></td>
<td><span data-ttu-id="2365a-769">Finanzas</span><span class="sxs-lookup"><span data-stu-id="2365a-769">Finance</span></span></td>
<td><span data-ttu-id="2365a-770">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-770">10001</span></span></td>
<td><span data-ttu-id="2365a-771">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-771">Electricity</span></span></td>
<td><span data-ttu-id="2365a-772">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-772">Fixed cost</span></span></td>
<td><span data-ttu-id="2365a-773">175.00</span><span class="sxs-lookup"><span data-stu-id="2365a-773">175.00</span></span></td>
<td><span data-ttu-id="2365a-774">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-775">CC003</span><span class="sxs-lookup"><span data-stu-id="2365a-775">CC003</span></span></td>
<td><span data-ttu-id="2365a-776">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="2365a-776">Assembly</span></span></td>
<td><span data-ttu-id="2365a-777">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-777">10001</span></span></td>
<td><span data-ttu-id="2365a-778">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-778">Electricity</span></span></td>
<td><span data-ttu-id="2365a-779">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-779">Fixed cost</span></span></td>
<td><span data-ttu-id="2365a-780">275.00</span><span class="sxs-lookup"><span data-stu-id="2365a-780">275.00</span></span></td>
<td><span data-ttu-id="2365a-781">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-782">CC004</span><span class="sxs-lookup"><span data-stu-id="2365a-782">CC004</span></span></td>
<td><span data-ttu-id="2365a-783">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="2365a-783">Packaging</span></span></td>
<td><span data-ttu-id="2365a-784">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-784">10001</span></span></td>
<td><span data-ttu-id="2365a-785">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-785">Electricity</span></span></td>
<td><span data-ttu-id="2365a-786">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-786">Fixed cost</span></span></td>
<td><span data-ttu-id="2365a-787">50,00</span><span class="sxs-lookup"><span data-stu-id="2365a-787">50,00</span></span></td>
<td><span data-ttu-id="2365a-788">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-789">CC001</span><span class="sxs-lookup"><span data-stu-id="2365a-789">CC001</span></span></td>
<td><span data-ttu-id="2365a-790">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="2365a-790">HR</span></span></td>
<td><span data-ttu-id="2365a-791">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-791">10001</span></span></td>
<td><span data-ttu-id="2365a-792">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-792">Electricity</span></span></td>
<td><span data-ttu-id="2365a-793">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-793">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="2365a-794">-1,245.71</span></span></td>
<td><span data-ttu-id="2365a-795">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-796">CC002</span><span class="sxs-lookup"><span data-stu-id="2365a-796">CC002</span></span></td>
<td><span data-ttu-id="2365a-797">Finanzas</span><span class="sxs-lookup"><span data-stu-id="2365a-797">Finance</span></span></td>
<td><span data-ttu-id="2365a-798">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-798">10001</span></span></td>
<td><span data-ttu-id="2365a-799">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-799">Electricity</span></span></td>
<td><span data-ttu-id="2365a-800">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-800">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-801">436.00</span><span class="sxs-lookup"><span data-stu-id="2365a-801">436.00</span></span></td>
<td><span data-ttu-id="2365a-802">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-803">CC003</span><span class="sxs-lookup"><span data-stu-id="2365a-803">CC003</span></span></td>
<td><span data-ttu-id="2365a-804">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="2365a-804">Assembly</span></span></td>
<td><span data-ttu-id="2365a-805">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-805">10001</span></span></td>
<td><span data-ttu-id="2365a-806">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-806">Electricity</span></span></td>
<td><span data-ttu-id="2365a-807">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-807">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-808">685.14</span><span class="sxs-lookup"><span data-stu-id="2365a-808">685.14</span></span></td>
<td><span data-ttu-id="2365a-809">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-810">CC004</span><span class="sxs-lookup"><span data-stu-id="2365a-810">CC004</span></span></td>
<td><span data-ttu-id="2365a-811">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="2365a-811">Packaging</span></span></td>
<td><span data-ttu-id="2365a-812">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-812">10001</span></span></td>
<td><span data-ttu-id="2365a-813">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-813">Electricity</span></span></td>
<td><span data-ttu-id="2365a-814">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-814">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-815">124.57</span><span class="sxs-lookup"><span data-stu-id="2365a-815">124.57</span></span></td>
<td><span data-ttu-id="2365a-816">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-817">CC002</span><span class="sxs-lookup"><span data-stu-id="2365a-817">CC002</span></span></td>
<td><span data-ttu-id="2365a-818">Finanzas</span><span class="sxs-lookup"><span data-stu-id="2365a-818">Finance</span></span></td>
<td><span data-ttu-id="2365a-819">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-819">10001</span></span></td>
<td><span data-ttu-id="2365a-820">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-820">Electricity</span></span></td>
<td><span data-ttu-id="2365a-821">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-821">Fixed cost</span></span></td>
<td><span data-ttu-id="2365a-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="2365a-822">-675.00</span></span></td>
<td><span data-ttu-id="2365a-823">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-824">CC003</span><span class="sxs-lookup"><span data-stu-id="2365a-824">CC003</span></span></td>
<td><span data-ttu-id="2365a-825">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="2365a-825">Assembly</span></span></td>
<td><span data-ttu-id="2365a-826">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-826">10001</span></span></td>
<td><span data-ttu-id="2365a-827">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-827">Electricity</span></span></td>
<td><span data-ttu-id="2365a-828">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-828">Fixed cost</span></span></td>
<td><span data-ttu-id="2365a-829">438.75</span><span class="sxs-lookup"><span data-stu-id="2365a-829">438.75</span></span></td>
<td><span data-ttu-id="2365a-830">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-831">CC004</span><span class="sxs-lookup"><span data-stu-id="2365a-831">CC004</span></span></td>
<td><span data-ttu-id="2365a-832">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="2365a-832">Packaging</span></span></td>
<td><span data-ttu-id="2365a-833">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-833">10001</span></span></td>
<td><span data-ttu-id="2365a-834">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-834">Electricity</span></span></td>
<td><span data-ttu-id="2365a-835">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-835">Fixed cost</span></span></td>
<td><span data-ttu-id="2365a-836">236.25</span><span class="sxs-lookup"><span data-stu-id="2365a-836">236.25</span></span></td>
<td><span data-ttu-id="2365a-837">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-838">CC002</span><span class="sxs-lookup"><span data-stu-id="2365a-838">CC002</span></span></td>
<td><span data-ttu-id="2365a-839">Finanzas</span><span class="sxs-lookup"><span data-stu-id="2365a-839">Finance</span></span></td>
<td><span data-ttu-id="2365a-840">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-840">10001</span></span></td>
<td><span data-ttu-id="2365a-841">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-841">Electricity</span></span></td>
<td><span data-ttu-id="2365a-842">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-842">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="2365a-843">-8,150.29</span></span></td>
<td><span data-ttu-id="2365a-844">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-845">CC003</span><span class="sxs-lookup"><span data-stu-id="2365a-845">CC003</span></span></td>
<td><span data-ttu-id="2365a-846">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="2365a-846">Assembly</span></span></td>
<td><span data-ttu-id="2365a-847">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-847">10001</span></span></td>
<td><span data-ttu-id="2365a-848">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-848">Electricity</span></span></td>
<td><span data-ttu-id="2365a-849">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-849">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="2365a-850">5,297.69</span></span></td>
<td><span data-ttu-id="2365a-851">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-852">CC004</span><span class="sxs-lookup"><span data-stu-id="2365a-852">CC004</span></span></td>
<td><span data-ttu-id="2365a-853">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="2365a-853">Packaging</span></span></td>
<td><span data-ttu-id="2365a-854">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-854">10001</span></span></td>
<td><span data-ttu-id="2365a-855">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-855">Electricity</span></span></td>
<td><span data-ttu-id="2365a-856">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-856">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="2365a-857">2,852.60</span></span></td>
<td><span data-ttu-id="2365a-858">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-859">CC003</span><span class="sxs-lookup"><span data-stu-id="2365a-859">CC003</span></span></td>
<td><span data-ttu-id="2365a-860">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="2365a-860">Assembly</span></span></td>
<td><span data-ttu-id="2365a-861">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-861">10001</span></span></td>
<td><span data-ttu-id="2365a-862">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-862">Electricity</span></span></td>
<td><span data-ttu-id="2365a-863">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-863">Fixed cost</span></span></td>
<td><span data-ttu-id="2365a-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="2365a-864">-713.75</span></span></td>
<td><span data-ttu-id="2365a-865">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2365a-866">Prod 1</span></span></td>
<td><span data-ttu-id="2365a-867">Producto 1</span><span class="sxs-lookup"><span data-stu-id="2365a-867">Product 1</span></span></td>
<td><span data-ttu-id="2365a-868">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-868">10001</span></span></td>
<td><span data-ttu-id="2365a-869">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-869">Electricity</span></span></td>
<td><span data-ttu-id="2365a-870">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-870">Fixed cost</span></span></td>
<td><span data-ttu-id="2365a-871">535.31</span><span class="sxs-lookup"><span data-stu-id="2365a-871">535.31</span></span></td>
<td><span data-ttu-id="2365a-872">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2365a-873">Prod 2</span></span></td>
<td><span data-ttu-id="2365a-874">Producto 2</span><span class="sxs-lookup"><span data-stu-id="2365a-874">Product 2</span></span></td>
<td><span data-ttu-id="2365a-875">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-875">10001</span></span></td>
<td><span data-ttu-id="2365a-876">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-876">Electricity</span></span></td>
<td><span data-ttu-id="2365a-877">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-877">Fixed cost</span></span></td>
<td><span data-ttu-id="2365a-878">178.44</span><span class="sxs-lookup"><span data-stu-id="2365a-878">178.44</span></span></td>
<td><span data-ttu-id="2365a-879">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-880">CC003</span><span class="sxs-lookup"><span data-stu-id="2365a-880">CC003</span></span></td>
<td><span data-ttu-id="2365a-881">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="2365a-881">Assembly</span></span></td>
<td><span data-ttu-id="2365a-882">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-882">10001</span></span></td>
<td><span data-ttu-id="2365a-883">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-883">Electricity</span></span></td>
<td><span data-ttu-id="2365a-884">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-884">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="2365a-885">-5,982.83</span></span></td>
<td><span data-ttu-id="2365a-886">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2365a-887">Prod 1</span></span></td>
<td><span data-ttu-id="2365a-888">Producto 1</span><span class="sxs-lookup"><span data-stu-id="2365a-888">Product 1</span></span></td>
<td><span data-ttu-id="2365a-889">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-889">10001</span></span></td>
<td><span data-ttu-id="2365a-890">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-890">Electricity</span></span></td>
<td><span data-ttu-id="2365a-891">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-891">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="2365a-892">4,487.12</span></span></td>
<td><span data-ttu-id="2365a-893">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2365a-894">Prod 2</span></span></td>
<td><span data-ttu-id="2365a-895">Producto 2</span><span class="sxs-lookup"><span data-stu-id="2365a-895">Product 2</span></span></td>
<td><span data-ttu-id="2365a-896">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-896">10001</span></span></td>
<td><span data-ttu-id="2365a-897">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-897">Electricity</span></span></td>
<td><span data-ttu-id="2365a-898">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-898">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="2365a-899">1,495.71</span></span></td>
<td><span data-ttu-id="2365a-900">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-901">CC003</span><span class="sxs-lookup"><span data-stu-id="2365a-901">CC003</span></span></td>
<td><span data-ttu-id="2365a-902">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="2365a-902">Assembly</span></span></td>
<td><span data-ttu-id="2365a-903">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-903">10001</span></span></td>
<td><span data-ttu-id="2365a-904">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-904">Electricity</span></span></td>
<td><span data-ttu-id="2365a-905">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-905">Fixed cost</span></span></td>
<td><span data-ttu-id="2365a-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="2365a-906">-286.25</span></span></td>
<td><span data-ttu-id="2365a-907">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2365a-908">Prod 1</span></span></td>
<td><span data-ttu-id="2365a-909">Producto 1</span><span class="sxs-lookup"><span data-stu-id="2365a-909">Product 1</span></span></td>
<td><span data-ttu-id="2365a-910">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-910">10001</span></span></td>
<td><span data-ttu-id="2365a-911">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-911">Electricity</span></span></td>
<td><span data-ttu-id="2365a-912">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-912">Fixed cost</span></span></td>
<td><span data-ttu-id="2365a-913">241.05</span><span class="sxs-lookup"><span data-stu-id="2365a-913">241.05</span></span></td>
<td><span data-ttu-id="2365a-914">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2365a-915">Prod 2</span></span></td>
<td><span data-ttu-id="2365a-916">Producto 2</span><span class="sxs-lookup"><span data-stu-id="2365a-916">Product 2</span></span></td>
<td><span data-ttu-id="2365a-917">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-917">10001</span></span></td>
<td><span data-ttu-id="2365a-918">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-918">Electricity</span></span></td>
<td><span data-ttu-id="2365a-919">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-919">Fixed cost</span></span></td>
<td><span data-ttu-id="2365a-920">45.20</span><span class="sxs-lookup"><span data-stu-id="2365a-920">45.20</span></span></td>
<td><span data-ttu-id="2365a-921">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-922">CC003</span><span class="sxs-lookup"><span data-stu-id="2365a-922">CC003</span></span></td>
<td><span data-ttu-id="2365a-923">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="2365a-923">Assembly</span></span></td>
<td><span data-ttu-id="2365a-924">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-924">10001</span></span></td>
<td><span data-ttu-id="2365a-925">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-925">Electricity</span></span></td>
<td><span data-ttu-id="2365a-926">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-926">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="2365a-927">-2,977.17</span></span></td>
<td><span data-ttu-id="2365a-928">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2365a-929">Prod 1</span></span></td>
<td><span data-ttu-id="2365a-930">Producto 1</span><span class="sxs-lookup"><span data-stu-id="2365a-930">Product 1</span></span></td>
<td><span data-ttu-id="2365a-931">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-931">10001</span></span></td>
<td><span data-ttu-id="2365a-932">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-932">Electricity</span></span></td>
<td><span data-ttu-id="2365a-933">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-933">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="2365a-934">2,507.09</span></span></td>
<td><span data-ttu-id="2365a-935">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2365a-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2365a-936">Prod 2</span></span></td>
<td><span data-ttu-id="2365a-937">Producto 2</span><span class="sxs-lookup"><span data-stu-id="2365a-937">Product 2</span></span></td>
<td><span data-ttu-id="2365a-938">10001</span><span class="sxs-lookup"><span data-stu-id="2365a-938">10001</span></span></td>
<td><span data-ttu-id="2365a-939">Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-939">Electricity</span></span></td>
<td><span data-ttu-id="2365a-940">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-940">Variable cost</span></span></td>
<td><span data-ttu-id="2365a-941">470.08</span><span class="sxs-lookup"><span data-stu-id="2365a-941">470.08</span></span></td>
<td><span data-ttu-id="2365a-942">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="2365a-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="2365a-943">Conclusión</span><span class="sxs-lookup"><span data-stu-id="2365a-943">Conclusion</span></span>
<span data-ttu-id="2365a-944">En la contabilidad financiera, un coste de 10.000,00 para electricidad se envía a un identificador ficticio de centro de coste.</span><span class="sxs-lookup"><span data-stu-id="2365a-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="2365a-945">Por lo tanto, los contables de coste sabrán que este coste se debe asignar.</span><span class="sxs-lookup"><span data-stu-id="2365a-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="2365a-946">En contabilidad de costes, los costes fluyen en las unidades organizativas y los niveles en función de las directivas y las reglas que se aplican.</span><span class="sxs-lookup"><span data-stu-id="2365a-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="2365a-947">Cada coste se ha asociado con una base de asignación que proporciona la mejor evaluación para la asignación de costes.</span><span class="sxs-lookup"><span data-stu-id="2365a-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="2365a-948">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="2365a-949">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="2365a-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="2365a-950">Total</span><span class="sxs-lookup"><span data-stu-id="2365a-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="2365a-951">CC099</span><span class="sxs-lookup"><span data-stu-id="2365a-951">CC099</span></span></th>
<th><span data-ttu-id="2365a-952">CC001</span><span class="sxs-lookup"><span data-stu-id="2365a-952">CC001</span></span></th>
<th><span data-ttu-id="2365a-953">CC002</span><span class="sxs-lookup"><span data-stu-id="2365a-953">CC002</span></span></th>
<th><span data-ttu-id="2365a-954">CC003</span><span class="sxs-lookup"><span data-stu-id="2365a-954">CC003</span></span></th>
<th><span data-ttu-id="2365a-955">CC004</span><span class="sxs-lookup"><span data-stu-id="2365a-955">CC004</span></span></th>
<th><span data-ttu-id="2365a-956">Proy 1</span><span class="sxs-lookup"><span data-stu-id="2365a-956">Proj 1</span></span></th>
<th><span data-ttu-id="2365a-957">Proy 2</span><span class="sxs-lookup"><span data-stu-id="2365a-957">Proj 2</span></span></th>
<th><span data-ttu-id="2365a-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="2365a-958">Prod 1</span></span></th>
<th><span data-ttu-id="2365a-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="2365a-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="2365a-960">10001 Electricidad</span><span class="sxs-lookup"><span data-stu-id="2365a-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="2365a-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="2365a-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="2365a-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="2365a-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="2365a-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="2365a-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="2365a-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="2365a-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="2365a-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="2365a-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="2365a-970">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="2365a-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-971">0,00</span><span class="sxs-lookup"><span data-stu-id="2365a-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="2365a-972">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="2365a-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-973">0,00</span><span class="sxs-lookup"><span data-stu-id="2365a-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-974">0,00</span><span class="sxs-lookup"><span data-stu-id="2365a-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-975">0,00</span><span class="sxs-lookup"><span data-stu-id="2365a-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-976">0,00</span><span class="sxs-lookup"><span data-stu-id="2365a-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-977">0,00</span><span class="sxs-lookup"><span data-stu-id="2365a-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="2365a-978">776.36</span><span class="sxs-lookup"><span data-stu-id="2365a-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-979">223.64</span><span class="sxs-lookup"><span data-stu-id="2365a-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="2365a-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="2365a-981">Coste variable</span><span class="sxs-lookup"><span data-stu-id="2365a-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-982">000</span><span class="sxs-lookup"><span data-stu-id="2365a-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-983">0,00</span><span class="sxs-lookup"><span data-stu-id="2365a-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-984">0,00</span><span class="sxs-lookup"><span data-stu-id="2365a-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-985">0,00</span><span class="sxs-lookup"><span data-stu-id="2365a-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-986">0,00</span><span class="sxs-lookup"><span data-stu-id="2365a-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-987">30,00</span><span class="sxs-lookup"><span data-stu-id="2365a-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-988">10,00</span><span class="sxs-lookup"><span data-stu-id="2365a-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="2365a-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="2365a-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2365a-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="2365a-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="2365a-992">Este tema muestra cómo un artículo de costes principales, 10001 Electricidad, fluye por los objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="2365a-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="2365a-993">Por tanto, estos gastos generales se asignan al nivel más bajo de la organización.</span><span class="sxs-lookup"><span data-stu-id="2365a-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="2365a-994">Es decir, los objetos de coste del nivel más bajo son los que soportan el coste.</span><span class="sxs-lookup"><span data-stu-id="2365a-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="2365a-995">Si necesita un flujo visual del coste entre los objetos de coste, puede usar las reglas de directivas de acumulación de costes para visualizar el flujo del coste.</span><span class="sxs-lookup"><span data-stu-id="2365a-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="2365a-996">Para obtener más información, consulte [Directiva de acumulación de costes y cálculo de costes generales](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="2365a-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]