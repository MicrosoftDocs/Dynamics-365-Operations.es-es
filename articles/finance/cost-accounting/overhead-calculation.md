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
ms.openlocfilehash: 2dddc22128621dc148a253cd568430587f294544
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822912"
---
# <a name="overhead-calculation"></a><span data-ttu-id="13b90-103">Cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="13b90-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="13b90-104">Este tema describe los procesos típicos para calcular y asignar costes generales.</span><span class="sxs-lookup"><span data-stu-id="13b90-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="13b90-105">Definición del término</span><span class="sxs-lookup"><span data-stu-id="13b90-105">Term definition</span></span>
---------------

<span data-ttu-id="13b90-106">Los costes generales son costes que se contraen para dirigir un negocio, pero que no pueden ser atribuidos directamente a ninguna actividad empresarial, productos, o servicio específicos.</span><span class="sxs-lookup"><span data-stu-id="13b90-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="13b90-107">Los costes generales proporcionan un soporte fundamental a la generación de actividades rentables.</span><span class="sxs-lookup"><span data-stu-id="13b90-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="13b90-108">Algunos ejemplos de costes generales son:</span><span class="sxs-lookup"><span data-stu-id="13b90-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="13b90-109">Alquiler</span><span class="sxs-lookup"><span data-stu-id="13b90-109">Rent</span></span>
-   <span data-ttu-id="13b90-110">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-110">Electricity</span></span>
-   <span data-ttu-id="13b90-111">Sueldos administrativos</span><span class="sxs-lookup"><span data-stu-id="13b90-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="13b90-112">Visión general del cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="13b90-112">Overhead calculation overview</span></span>
<span data-ttu-id="13b90-113">El cálculo de costes generales ejecuta las directivas de contabilidad de costes en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="13b90-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="13b90-114">Puede calcular varias veces los costes generales del mismo período fiscal si se han cambiado las directivas de contabilidad de costes o se han detectado errores específicos.</span><span class="sxs-lookup"><span data-stu-id="13b90-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="13b90-115">Cada ejecución del cálculo de costes generales se almacena y recibe un identificador de versión único que permite comparar los cálculos de diferentes versiones.</span><span class="sxs-lookup"><span data-stu-id="13b90-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="13b90-116">Las entradas de costes que el cálculo de costes generales genera reciben una fecha de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="13b90-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="13b90-117">Esta fecha de contabilidad coincide con la fecha final del período fiscal que se usa en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="13b90-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="13b90-118">El identificador de versión único consiste en los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="13b90-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="13b90-119">Tipo de versión</span><span class="sxs-lookup"><span data-stu-id="13b90-119">Version type</span></span>
-   <span data-ttu-id="13b90-120">Fecha y hora</span><span class="sxs-lookup"><span data-stu-id="13b90-120">Date and time</span></span>
-   <span data-ttu-id="13b90-121">Libro mayor de contabilidad de costes</span><span class="sxs-lookup"><span data-stu-id="13b90-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="13b90-122">Ejercicio</span><span class="sxs-lookup"><span data-stu-id="13b90-122">Fiscal year</span></span>
-   <span data-ttu-id="13b90-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="13b90-123">Fiscal period</span></span>

<span data-ttu-id="13b90-124">El cálculo de costes generales se ejecuta independientemente de la versión.</span><span class="sxs-lookup"><span data-stu-id="13b90-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="13b90-125">Por lo tanto, puede calcular la versión de presupuesto antes que la versión real.</span><span class="sxs-lookup"><span data-stu-id="13b90-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="13b90-126">El cálculo de costes generales consta de cuatro pasos, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="13b90-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="13b90-127">En cada paso, se crea una cabecera de diario que tiene entradas del diario.</span><span class="sxs-lookup"><span data-stu-id="13b90-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="13b90-128">Esta cabecera de diario guarda los datos de entrada para cada paso de cálculo.</span><span class="sxs-lookup"><span data-stu-id="13b90-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="13b90-129">Las directivas y las reglas se aplican a cada línea de diario, y las entradas de coste se generan como resultado.</span><span class="sxs-lookup"><span data-stu-id="13b90-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="13b90-130">Por tanto, siempre se tiene rastreabilidad completa.</span><span class="sxs-lookup"><span data-stu-id="13b90-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="13b90-131">[![Cálculo de costes generales](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="13b90-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="13b90-132">Calcular y asignar costes generales de electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="13b90-133">En la contabilidad financiera, algunos costes, como la electricidad, se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="13b90-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="13b90-134">Por lo tanto, no se proporciona una visión de gestión detallada para la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="13b90-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="13b90-135">En contabilidad de costes, para proporcionar información de gestión correcta en todas las unidades y niveles organizativos, los costes deben fluir por las unidades organizativas.</span><span class="sxs-lookup"><span data-stu-id="13b90-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="13b90-136">Este flujo se debe basar en cualquier registro preciso de consumo o en una evaluación justa.</span><span class="sxs-lookup"><span data-stu-id="13b90-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="13b90-137">En la contabilidad general, un coste de la electricidad se puede registrar como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="13b90-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="13b90-138">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="13b90-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="13b90-139">Centro de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="13b90-140">Cuenta principal</span><span class="sxs-lookup"><span data-stu-id="13b90-140">Main account</span></span></th>
<th><span data-ttu-id="13b90-141">Importe en la divisa de contabilidad</span><span class="sxs-lookup"><span data-stu-id="13b90-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-142">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="13b90-143">CC099</span><span class="sxs-lookup"><span data-stu-id="13b90-143">CC099</span></span></td>
<td><span data-ttu-id="13b90-144">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="13b90-144">Default cost center</span></span></td>
<td><span data-ttu-id="13b90-145">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-145">10001</span></span></td>
<td><span data-ttu-id="13b90-146">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-146">Electricity</span></span></td>
<td><span data-ttu-id="13b90-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="13b90-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="13b90-148">Paso 1: Procese el cálculo del comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="13b90-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="13b90-149">De forma predeterminada, cuando las entradas de coste se importan de los datos de origen, reciben la clasificación de comportamiento del coste **Sin ordenar** en la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="13b90-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="13b90-150">Aplicando reglas de directivas de comportamiento de coste, puede reclasificar entradas de coste como **Coste fijo** o **Coste variable**.</span><span class="sxs-lookup"><span data-stu-id="13b90-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="13b90-151">Defina la regla de comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="13b90-151">Define the cost behavior rule</span></span>

<span data-ttu-id="13b90-152">En algunos casos, parte del coste es una cuota fija, y el coste pendiente se basa en el consumo.</span><span class="sxs-lookup"><span data-stu-id="13b90-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="13b90-153">Las facturas de electricidad coinciden a menudo con esta definición.</span><span class="sxs-lookup"><span data-stu-id="13b90-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="13b90-154">Tras pagar una cuota fija específica, paga el consumo por kilovatio-hora (Kwh).</span><span class="sxs-lookup"><span data-stu-id="13b90-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="13b90-155">Por ejemplo, si la cuota de coste fijo es de 1.000,00, la regla de comportamiento del coste se define como sigue:</span><span class="sxs-lookup"><span data-stu-id="13b90-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="13b90-156">Importe fijo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="13b90-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="13b90-157">0 &lt;= 1.000,00 = Fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="13b90-158">1.000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="13b90-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="13b90-159">Diario</span><span class="sxs-lookup"><span data-stu-id="13b90-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="13b90-160">Diario</span><span class="sxs-lookup"><span data-stu-id="13b90-160">Journal</span></span></th>
<th><span data-ttu-id="13b90-161">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="13b90-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="13b90-162">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="13b90-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="13b90-163">Versión</span><span class="sxs-lookup"><span data-stu-id="13b90-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-164">00001</span><span class="sxs-lookup"><span data-stu-id="13b90-164">00001</span></span></td>
<td><span data-ttu-id="13b90-165">Diario de cálculo de comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="13b90-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="13b90-166">Fiscal</span><span class="sxs-lookup"><span data-stu-id="13b90-166">Fiscal</span></span></td>
<td><span data-ttu-id="13b90-167">2017</span><span class="sxs-lookup"><span data-stu-id="13b90-167">2017</span></span></td>
<td><span data-ttu-id="13b90-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="13b90-168">Period 1</span></span></td>
<td><span data-ttu-id="13b90-169">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="13b90-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="13b90-170">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="13b90-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="13b90-171">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="13b90-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="13b90-172">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="13b90-173">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-173">Cost element</span></span></th>
<th><span data-ttu-id="13b90-174">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="13b90-174">Cost behavior</span></span></th>
<th><span data-ttu-id="13b90-175">Importe</span><span class="sxs-lookup"><span data-stu-id="13b90-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-176">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="13b90-177">CC099</span><span class="sxs-lookup"><span data-stu-id="13b90-177">CC099</span></span></td>
<td><span data-ttu-id="13b90-178">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="13b90-178">Default cost center</span></span></td>
<td><span data-ttu-id="13b90-179">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-179">10001</span></span></td>
<td><span data-ttu-id="13b90-180">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-180">Electricity</span></span></td>
<td><span data-ttu-id="13b90-181">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="13b90-181">Unclassified</span></span></td>
<td><span data-ttu-id="13b90-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="13b90-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="13b90-183">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="13b90-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="13b90-184">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="13b90-185">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-185">Cost element</span></span></th>
<th><span data-ttu-id="13b90-186">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="13b90-186">Cost behavior</span></span></th>
<th><span data-ttu-id="13b90-187">Importe</span><span class="sxs-lookup"><span data-stu-id="13b90-187">Amount</span></span></th>
<th><span data-ttu-id="13b90-188">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="13b90-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-189">CC099</span><span class="sxs-lookup"><span data-stu-id="13b90-189">CC099</span></span></td>
<td><span data-ttu-id="13b90-190">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="13b90-190">Default cost center</span></span></td>
<td><span data-ttu-id="13b90-191">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-191">10001</span></span></td>
<td><span data-ttu-id="13b90-192">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-192">Electricity</span></span></td>
<td><span data-ttu-id="13b90-193">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="13b90-193">Unclassified</span></span></td>
<td><span data-ttu-id="13b90-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="13b90-194">10,000.00</span></span></td>
<td><span data-ttu-id="13b90-195">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-196">CC099</span><span class="sxs-lookup"><span data-stu-id="13b90-196">CC099</span></span></td>
<td><span data-ttu-id="13b90-197">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="13b90-197">Default cost center</span></span></td>
<td><span data-ttu-id="13b90-198">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-198">10001</span></span></td>
<td><span data-ttu-id="13b90-199">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-199">Electricity</span></span></td>
<td><span data-ttu-id="13b90-200">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="13b90-200">Unclassified</span></span></td>
<td><span data-ttu-id="13b90-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="13b90-201">-10,000.00</span></span></td>
<td><span data-ttu-id="13b90-202">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-203">CC099</span><span class="sxs-lookup"><span data-stu-id="13b90-203">CC099</span></span></td>
<td><span data-ttu-id="13b90-204">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="13b90-204">Default cost center</span></span></td>
<td><span data-ttu-id="13b90-205">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-205">10001</span></span></td>
<td><span data-ttu-id="13b90-206">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-206">Electricity</span></span></td>
<td><span data-ttu-id="13b90-207">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-207">Fixed cost</span></span></td>
<td><span data-ttu-id="13b90-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="13b90-208">1,000.00</span></span></td>
<td><span data-ttu-id="13b90-209">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-210">CC099</span><span class="sxs-lookup"><span data-stu-id="13b90-210">CC099</span></span></td>
<td><span data-ttu-id="13b90-211">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="13b90-211">Default cost center</span></span></td>
<td><span data-ttu-id="13b90-212">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-212">10001</span></span></td>
<td><span data-ttu-id="13b90-213">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-213">Electricity</span></span></td>
<td><span data-ttu-id="13b90-214">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-214">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="13b90-215">9,000.00</span></span></td>
<td><span data-ttu-id="13b90-216">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="13b90-217">Para obtener más información, consulte [Crear y asignar una directiva de comportamiento de costes a una unidad de control de costes](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="13b90-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="13b90-218">Paso 2: Procese el cálculo de distribución de costes</span><span class="sxs-lookup"><span data-stu-id="13b90-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="13b90-219">La distribución de costes se usa para redistribuir costes desde un objeto de coste a uno o más objetos de coste aplicando una base relevante de la asignación.</span><span class="sxs-lookup"><span data-stu-id="13b90-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="13b90-220">La distribución de costes y la asignación de costes difieren en que la distribución de costes siempre se produce en el nivel de elemento de costes principal del coste original.</span><span class="sxs-lookup"><span data-stu-id="13b90-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="13b90-221">Defina la regla de distribución del coste</span><span class="sxs-lookup"><span data-stu-id="13b90-221">Define the cost distribution rule</span></span>

<span data-ttu-id="13b90-222">En la contabilidad financiera, los costes de electricidad se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="13b90-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="13b90-223">En contabilidad de costes, este método no es suficientemente detallado.</span><span class="sxs-lookup"><span data-stu-id="13b90-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="13b90-224">El coste variable debe distribuirse a los objetos individuales de coste aplicando una base justa.</span><span class="sxs-lookup"><span data-stu-id="13b90-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="13b90-225">La base de asignación más lógica es el consumo de electricidad (Kwh).</span><span class="sxs-lookup"><span data-stu-id="13b90-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="13b90-226">Se crea un miembro de dimensión estadística que se denomina Electricity, y se registra el consumo de electricidad.</span><span class="sxs-lookup"><span data-stu-id="13b90-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="13b90-227">De forma predeterminada, todos los miembros de dimensión estadísticos estarán disponibles como bases de asignación.</span><span class="sxs-lookup"><span data-stu-id="13b90-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="13b90-228">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-228">Cost object</span></span></th>
<th><span data-ttu-id="13b90-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="13b90-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-230">CC001</span><span class="sxs-lookup"><span data-stu-id="13b90-230">CC001</span></span></td>
<td><span data-ttu-id="13b90-231">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="13b90-231">HR</span></span></td>
<td><span data-ttu-id="13b90-232">1.000</span><span class="sxs-lookup"><span data-stu-id="13b90-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-233">CC002</span><span class="sxs-lookup"><span data-stu-id="13b90-233">CC002</span></span></td>
<td><span data-ttu-id="13b90-234">Finanzas</span><span class="sxs-lookup"><span data-stu-id="13b90-234">Finance</span></span></td>
<td><span data-ttu-id="13b90-235">6.000</span><span class="sxs-lookup"><span data-stu-id="13b90-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-236">CC003</span><span class="sxs-lookup"><span data-stu-id="13b90-236">CC003</span></span></td>
<td><span data-ttu-id="13b90-237">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="13b90-237">Assembly</span></span></td>
<td><span data-ttu-id="13b90-238">0</span><span class="sxs-lookup"><span data-stu-id="13b90-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="13b90-239">La tabla siguiente muestra el resultado cuando se aplica el consumo de electricidad como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="13b90-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="13b90-240">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-240">Cost object</span></span></th>
<th><span data-ttu-id="13b90-241">Magnitud</span><span class="sxs-lookup"><span data-stu-id="13b90-241">Magnitude</span></span></th>
<th><span data-ttu-id="13b90-242">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="13b90-242">Allocation factor</span></span></th>
<th><span data-ttu-id="13b90-243">Importe</span><span class="sxs-lookup"><span data-stu-id="13b90-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-244">CC001</span><span class="sxs-lookup"><span data-stu-id="13b90-244">CC001</span></span></td>
<td><span data-ttu-id="13b90-245">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="13b90-245">HR</span></span></td>
<td><span data-ttu-id="13b90-246">1.000</span><span class="sxs-lookup"><span data-stu-id="13b90-246">1,000</span></span></td>
<td><span data-ttu-id="13b90-247">(1.000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="13b90-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="13b90-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="13b90-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-249">CC002</span><span class="sxs-lookup"><span data-stu-id="13b90-249">CC002</span></span></td>
<td><span data-ttu-id="13b90-250">Finanzas</span><span class="sxs-lookup"><span data-stu-id="13b90-250">Finance</span></span></td>
<td><span data-ttu-id="13b90-251">6.000</span><span class="sxs-lookup"><span data-stu-id="13b90-251">6,000</span></span></td>
<td><span data-ttu-id="13b90-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="13b90-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="13b90-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="13b90-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-254">CC003</span><span class="sxs-lookup"><span data-stu-id="13b90-254">CC003</span></span></td>
<td><span data-ttu-id="13b90-255">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="13b90-255">Assembly</span></span></td>
<td><span data-ttu-id="13b90-256">0</span><span class="sxs-lookup"><span data-stu-id="13b90-256">0</span></span></td>
<td><span data-ttu-id="13b90-257">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="13b90-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="13b90-258">0,00</span><span class="sxs-lookup"><span data-stu-id="13b90-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="13b90-259">El coste fijo debe distribuirse uniformemente a los objetos individuales de costes que han consumido electricidad.</span><span class="sxs-lookup"><span data-stu-id="13b90-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="13b90-260">Puede obtener este resultado usando el miembro de dimensión estadístico de electricidad en una base de asignación de la fórmula: (Electricidad &gt; 0,00) La tabla siguiente muestra el resultado cuando el consumo de electricidad se aplica como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="13b90-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="13b90-261">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-261">Cost object</span></span></th>
<th><span data-ttu-id="13b90-262">Fórmula</span><span class="sxs-lookup"><span data-stu-id="13b90-262">Formula</span></span></th>
<th><span data-ttu-id="13b90-263">Magnitud</span><span class="sxs-lookup"><span data-stu-id="13b90-263">Magnitude</span></span></th>
<th><span data-ttu-id="13b90-264">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="13b90-264">Allocation factor</span></span></th>
<th><span data-ttu-id="13b90-265">Importe</span><span class="sxs-lookup"><span data-stu-id="13b90-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-266">CC001</span><span class="sxs-lookup"><span data-stu-id="13b90-266">CC001</span></span></td>
<td><span data-ttu-id="13b90-267">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="13b90-267">HR</span></span></td>
<td><span data-ttu-id="13b90-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="13b90-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="13b90-269">1</span><span class="sxs-lookup"><span data-stu-id="13b90-269">1</span></span></td>
<td><span data-ttu-id="13b90-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="13b90-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="13b90-271">500,00</span><span class="sxs-lookup"><span data-stu-id="13b90-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-272">CC002</span><span class="sxs-lookup"><span data-stu-id="13b90-272">CC002</span></span></td>
<td><span data-ttu-id="13b90-273">Finanzas</span><span class="sxs-lookup"><span data-stu-id="13b90-273">Finance</span></span></td>
<td><span data-ttu-id="13b90-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="13b90-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="13b90-275">1</span><span class="sxs-lookup"><span data-stu-id="13b90-275">1</span></span></td>
<td><span data-ttu-id="13b90-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="13b90-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="13b90-277">500,00</span><span class="sxs-lookup"><span data-stu-id="13b90-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-278">CC003</span><span class="sxs-lookup"><span data-stu-id="13b90-278">CC003</span></span></td>
<td><span data-ttu-id="13b90-279">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="13b90-279">Assembly</span></span></td>
<td><span data-ttu-id="13b90-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="13b90-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="13b90-281">0</span><span class="sxs-lookup"><span data-stu-id="13b90-281">0</span></span></td>
<td><span data-ttu-id="13b90-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="13b90-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="13b90-283">0,00</span><span class="sxs-lookup"><span data-stu-id="13b90-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="13b90-284">Diario</span><span class="sxs-lookup"><span data-stu-id="13b90-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="13b90-285">Diario</span><span class="sxs-lookup"><span data-stu-id="13b90-285">Journal</span></span></th>
<th><span data-ttu-id="13b90-286">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="13b90-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="13b90-287">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="13b90-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="13b90-288">Versión</span><span class="sxs-lookup"><span data-stu-id="13b90-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-289">00002</span><span class="sxs-lookup"><span data-stu-id="13b90-289">00002</span></span></td>
<td><span data-ttu-id="13b90-290">Diario de cálculo de la distribución de costes</span><span class="sxs-lookup"><span data-stu-id="13b90-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="13b90-291">Fiscal</span><span class="sxs-lookup"><span data-stu-id="13b90-291">Fiscal</span></span></td>
<td><span data-ttu-id="13b90-292">2017</span><span class="sxs-lookup"><span data-stu-id="13b90-292">2017</span></span></td>
<td><span data-ttu-id="13b90-293">Período 1</span><span class="sxs-lookup"><span data-stu-id="13b90-293">Period 1</span></span></td>
<td><span data-ttu-id="13b90-294">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="13b90-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="13b90-295">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="13b90-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="13b90-296">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="13b90-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="13b90-297">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="13b90-298">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-298">Cost element</span></span></th>
<th><span data-ttu-id="13b90-299">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="13b90-299">Cost behavior</span></span></th>
<th><span data-ttu-id="13b90-300">Importe</span><span class="sxs-lookup"><span data-stu-id="13b90-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-301">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="13b90-302">CC099</span><span class="sxs-lookup"><span data-stu-id="13b90-302">CC099</span></span></td>
<td><span data-ttu-id="13b90-303">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="13b90-303">Default cost center</span></span></td>
<td><span data-ttu-id="13b90-304">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-304">10001</span></span></td>
<td><span data-ttu-id="13b90-305">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-305">Electricity</span></span></td>
<td><span data-ttu-id="13b90-306">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-306">Fixed cost</span></span></td>
<td><span data-ttu-id="13b90-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="13b90-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-308">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="13b90-309">CC099</span><span class="sxs-lookup"><span data-stu-id="13b90-309">CC099</span></span></td>
<td><span data-ttu-id="13b90-310">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="13b90-310">Default cost center</span></span></td>
<td><span data-ttu-id="13b90-311">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-311">10001</span></span></td>
<td><span data-ttu-id="13b90-312">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-312">Electricity</span></span></td>
<td><span data-ttu-id="13b90-313">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-313">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-314">9.000,00</span><span class="sxs-lookup"><span data-stu-id="13b90-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="13b90-315">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="13b90-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="13b90-316">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="13b90-317">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-317">Cost element</span></span></th>
<th><span data-ttu-id="13b90-318">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="13b90-318">Cost behavior</span></span></th>
<th><span data-ttu-id="13b90-319">Importe</span><span class="sxs-lookup"><span data-stu-id="13b90-319">Amount</span></span></th>
<th><span data-ttu-id="13b90-320">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="13b90-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-321">CC099</span><span class="sxs-lookup"><span data-stu-id="13b90-321">CC099</span></span></td>
<td><span data-ttu-id="13b90-322">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="13b90-322">Default cost center</span></span></td>
<td><span data-ttu-id="13b90-323">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-323">10001</span></span></td>
<td><span data-ttu-id="13b90-324">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-324">Electricity</span></span></td>
<td><span data-ttu-id="13b90-325">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-325">Fixed cost</span></span></td>
<td><span data-ttu-id="13b90-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="13b90-326">-1,000.00</span></span></td>
<td><span data-ttu-id="13b90-327">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-328">CC001</span><span class="sxs-lookup"><span data-stu-id="13b90-328">CC001</span></span></td>
<td><span data-ttu-id="13b90-329">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="13b90-329">HR</span></span></td>
<td><span data-ttu-id="13b90-330">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-330">10001</span></span></td>
<td><span data-ttu-id="13b90-331">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-331">Electricity</span></span></td>
<td><span data-ttu-id="13b90-332">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-332">Fixed cost</span></span></td>
<td><span data-ttu-id="13b90-333">500,00</span><span class="sxs-lookup"><span data-stu-id="13b90-333">500.00</span></span></td>
<td><span data-ttu-id="13b90-334">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-335">CC002</span><span class="sxs-lookup"><span data-stu-id="13b90-335">CC002</span></span></td>
<td><span data-ttu-id="13b90-336">Finanzas</span><span class="sxs-lookup"><span data-stu-id="13b90-336">Finance</span></span></td>
<td><span data-ttu-id="13b90-337">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-337">10001</span></span></td>
<td><span data-ttu-id="13b90-338">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-338">Electricity</span></span></td>
<td><span data-ttu-id="13b90-339">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-339">Fixed cost</span></span></td>
<td><span data-ttu-id="13b90-340">500,00</span><span class="sxs-lookup"><span data-stu-id="13b90-340">500.00</span></span></td>
<td><span data-ttu-id="13b90-341">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-342">CC099</span><span class="sxs-lookup"><span data-stu-id="13b90-342">CC099</span></span></td>
<td><span data-ttu-id="13b90-343">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="13b90-343">Default cost center</span></span></td>
<td><span data-ttu-id="13b90-344">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-344">10001</span></span></td>
<td><span data-ttu-id="13b90-345">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-345">Electricity</span></span></td>
<td><span data-ttu-id="13b90-346">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-346">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="13b90-347">-9,000.00</span></span></td>
<td><span data-ttu-id="13b90-348">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-349">CC001</span><span class="sxs-lookup"><span data-stu-id="13b90-349">CC001</span></span></td>
<td><span data-ttu-id="13b90-350">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="13b90-350">HR</span></span></td>
<td><span data-ttu-id="13b90-351">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-351">10001</span></span></td>
<td><span data-ttu-id="13b90-352">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-352">Electricity</span></span></td>
<td><span data-ttu-id="13b90-353">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-353">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="13b90-354">1,285.71</span></span></td>
<td><span data-ttu-id="13b90-355">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-356">CC002</span><span class="sxs-lookup"><span data-stu-id="13b90-356">CC002</span></span></td>
<td><span data-ttu-id="13b90-357">Finanzas</span><span class="sxs-lookup"><span data-stu-id="13b90-357">Finance</span></span></td>
<td><span data-ttu-id="13b90-358">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-358">10001</span></span></td>
<td><span data-ttu-id="13b90-359">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-359">Electricity</span></span></td>
<td><span data-ttu-id="13b90-360">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-360">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="13b90-361">7,714.29</span></span></td>
<td><span data-ttu-id="13b90-362">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="13b90-363">Para obtener más información, consulte [Crear y asignar una directiva de distribución de costes a una unidad de control de costes](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="13b90-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="13b90-364">Paso 3: Procese el cálculo de las tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="13b90-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="13b90-365">La tasa de costes generales se usa para cargar uno o varios objetos de coste específicos.</span><span class="sxs-lookup"><span data-stu-id="13b90-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="13b90-366">El cargo se basa en un índice de coste predeterminado y la magnitud de la base de asignación asignada.</span><span class="sxs-lookup"><span data-stu-id="13b90-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="13b90-367">Defina la tasa de costes generales</span><span class="sxs-lookup"><span data-stu-id="13b90-367">Define the overhead rate</span></span>

<span data-ttu-id="13b90-368">El objeto de coste CC001 HR contribuye a un conjunto de proyectos internos.</span><span class="sxs-lookup"><span data-stu-id="13b90-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="13b90-369">Se crea un miembro de dimensión estadística que se denomina proyectos HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="13b90-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="13b90-370">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-370">Cost object</span></span></th>
<th><span data-ttu-id="13b90-371">Horas</span><span class="sxs-lookup"><span data-stu-id="13b90-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-372">Proy 1</span><span class="sxs-lookup"><span data-stu-id="13b90-372">Proj 1</span></span></td>
<td><span data-ttu-id="13b90-373">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="13b90-373">Project 1</span></span></td>
<td><span data-ttu-id="13b90-374">3</span><span class="sxs-lookup"><span data-stu-id="13b90-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-375">Proy 2</span><span class="sxs-lookup"><span data-stu-id="13b90-375">Proj 2</span></span></td>
<td><span data-ttu-id="13b90-376">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="13b90-376">Project 2</span></span></td>
<td><span data-ttu-id="13b90-377">1</span><span class="sxs-lookup"><span data-stu-id="13b90-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="13b90-378">Una tasa de coste predeterminada para la contribución de los proyectos de coste se ha definido.</span><span class="sxs-lookup"><span data-stu-id="13b90-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="13b90-379">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-379">Cost object</span></span></th>
<th><span data-ttu-id="13b90-380">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-380">Cost element</span></span></th>
<th><span data-ttu-id="13b90-381">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="13b90-381">Cost behavior</span></span></th>
<th><span data-ttu-id="13b90-382">Unidades</span><span class="sxs-lookup"><span data-stu-id="13b90-382">Units</span></span></th>
<th><span data-ttu-id="13b90-383">Índice</span><span class="sxs-lookup"><span data-stu-id="13b90-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-384">CC001</span><span class="sxs-lookup"><span data-stu-id="13b90-384">CC001</span></span></td>
<td><span data-ttu-id="13b90-385">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="13b90-385">HR</span></span></td>
<td><span data-ttu-id="13b90-386">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-386">10001</span></span></td>
<td><span data-ttu-id="13b90-387">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-387">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-388">1</span><span class="sxs-lookup"><span data-stu-id="13b90-388">1</span></span></td>
<td><span data-ttu-id="13b90-389">10</span><span class="sxs-lookup"><span data-stu-id="13b90-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="13b90-390">La tabla siguiente muestra el resultado cuando los proyectos HR se aplican como base de la asignación.</span><span class="sxs-lookup"><span data-stu-id="13b90-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="13b90-391">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-391">Cost object</span></span></th>
<th><span data-ttu-id="13b90-392">Magnitud</span><span class="sxs-lookup"><span data-stu-id="13b90-392">Magnitude</span></span></th>
<th><span data-ttu-id="13b90-393">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-393">Cost element</span></span></th>
<th><span data-ttu-id="13b90-394">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="13b90-394">Allocation factor</span></span></th>
<th><span data-ttu-id="13b90-395">Importe</span><span class="sxs-lookup"><span data-stu-id="13b90-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-396">Proy 1</span><span class="sxs-lookup"><span data-stu-id="13b90-396">Proj 1</span></span></td>
<td><span data-ttu-id="13b90-397">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="13b90-397">Project 1</span></span></td>
<td><span data-ttu-id="13b90-398">3</span><span class="sxs-lookup"><span data-stu-id="13b90-398">3</span></span></td>
<td><span data-ttu-id="13b90-399">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-399">10001</span></span></td>
<td><span data-ttu-id="13b90-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="13b90-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="13b90-401">30,00</span><span class="sxs-lookup"><span data-stu-id="13b90-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-402">Proy 2</span><span class="sxs-lookup"><span data-stu-id="13b90-402">Proj 2</span></span></td>
<td><span data-ttu-id="13b90-403">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="13b90-403">Project 2</span></span></td>
<td><span data-ttu-id="13b90-404">1</span><span class="sxs-lookup"><span data-stu-id="13b90-404">1</span></span></td>
<td><span data-ttu-id="13b90-405">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-405">10001</span></span></td>
<td><span data-ttu-id="13b90-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="13b90-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="13b90-407">10,00</span><span class="sxs-lookup"><span data-stu-id="13b90-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="13b90-408">Diario</span><span class="sxs-lookup"><span data-stu-id="13b90-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="13b90-409">Diario</span><span class="sxs-lookup"><span data-stu-id="13b90-409">Journal</span></span></th>
<th><span data-ttu-id="13b90-410">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="13b90-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="13b90-411">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="13b90-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="13b90-412">Versión</span><span class="sxs-lookup"><span data-stu-id="13b90-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-413">00003</span><span class="sxs-lookup"><span data-stu-id="13b90-413">00003</span></span></td>
<td><span data-ttu-id="13b90-414">Diario de cálculo de tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="13b90-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="13b90-415">Fiscal</span><span class="sxs-lookup"><span data-stu-id="13b90-415">Fiscal</span></span></td>
<td><span data-ttu-id="13b90-416">2017</span><span class="sxs-lookup"><span data-stu-id="13b90-416">2017</span></span></td>
<td><span data-ttu-id="13b90-417">Período 1</span><span class="sxs-lookup"><span data-stu-id="13b90-417">Period 1</span></span></td>
<td><span data-ttu-id="13b90-418">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="13b90-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="13b90-419">Entradas de diario (entradas de diario para cálculo de tasas de costes generales)</span><span class="sxs-lookup"><span data-stu-id="13b90-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="13b90-420">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="13b90-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="13b90-421">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-421">Cost object</span></span></th>
<th><span data-ttu-id="13b90-422">Magnitud</span><span class="sxs-lookup"><span data-stu-id="13b90-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-423">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="13b90-424">Proy 1</span><span class="sxs-lookup"><span data-stu-id="13b90-424">Proj 1</span></span></td>
<td><span data-ttu-id="13b90-425">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="13b90-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="13b90-426">3,00</span><span class="sxs-lookup"><span data-stu-id="13b90-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-427">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="13b90-428">Proy 2</span><span class="sxs-lookup"><span data-stu-id="13b90-428">Proj 2</span></span></td>
<td><span data-ttu-id="13b90-429">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="13b90-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="13b90-430">1,00</span><span class="sxs-lookup"><span data-stu-id="13b90-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="13b90-431">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="13b90-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="13b90-432">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="13b90-433">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-433">Cost element</span></span></th>
<th><span data-ttu-id="13b90-434">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="13b90-434">Cost behavior</span></span></th>
<th><span data-ttu-id="13b90-435">Importe</span><span class="sxs-lookup"><span data-stu-id="13b90-435">Amount</span></span></th>
<th><span data-ttu-id="13b90-436">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="13b90-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="13b90-437">CC0001</span></span></td>
<td><span data-ttu-id="13b90-438">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="13b90-438">HR</span></span></td>
<td><span data-ttu-id="13b90-439">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-439">10001</span></span></td>
<td><span data-ttu-id="13b90-440">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-440">Electricity</span></span></td>
<td><span data-ttu-id="13b90-441">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-441">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="13b90-442">-30.00</span></span></td>
<td><span data-ttu-id="13b90-443">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-444">Proy 1</span><span class="sxs-lookup"><span data-stu-id="13b90-444">Proj 1</span></span></td>
<td><span data-ttu-id="13b90-445">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="13b90-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="13b90-446">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-446">10001</span></span></td>
<td><span data-ttu-id="13b90-447">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-447">Electricity</span></span></td>
<td><span data-ttu-id="13b90-448">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-448">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-449">30,00</span><span class="sxs-lookup"><span data-stu-id="13b90-449">30.00</span></span></td>
<td><span data-ttu-id="13b90-450">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-451">CC001</span><span class="sxs-lookup"><span data-stu-id="13b90-451">CC001</span></span></td>
<td><span data-ttu-id="13b90-452">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="13b90-452">HR</span></span></td>
<td><span data-ttu-id="13b90-453">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-453">10001</span></span></td>
<td><span data-ttu-id="13b90-454">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-454">Electricity</span></span></td>
<td><span data-ttu-id="13b90-455">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-455">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="13b90-456">-10.00</span></span></td>
<td><span data-ttu-id="13b90-457">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-458">Proy 2</span><span class="sxs-lookup"><span data-stu-id="13b90-458">Proj 2</span></span></td>
<td><span data-ttu-id="13b90-459">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="13b90-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="13b90-460">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-460">10001</span></span></td>
<td><span data-ttu-id="13b90-461">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-461">Electricity</span></span></td>
<td><span data-ttu-id="13b90-462">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-462">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-463">10,00</span><span class="sxs-lookup"><span data-stu-id="13b90-463">10.00</span></span></td>
<td><span data-ttu-id="13b90-464">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="13b90-465">Para obtener más información, consulte [Realizar cálculo de costes generales](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="13b90-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="13b90-466">Paso 4: Procese el cálculo de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="13b90-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="13b90-467">La asignación es utilizada para asignar el saldo de un objeto de coste a otros objetos de coste aplicando una base de asignación.</span><span class="sxs-lookup"><span data-stu-id="13b90-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="13b90-468">Finance admite el método de asignación recíproco.</span><span class="sxs-lookup"><span data-stu-id="13b90-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="13b90-469">En el método de asignación recíproco, se reconocen completamente los servicios mutuos que los objetos de coste auxiliar intercambian.</span><span class="sxs-lookup"><span data-stu-id="13b90-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="13b90-470">El sistema determina automáticamente el orden correcto para realizar las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="13b90-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="13b90-471">El saldo de un objeto de coste se asigna según una única base de asignación.</span><span class="sxs-lookup"><span data-stu-id="13b90-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="13b90-472">Las asignaciones entre dimensiones de objetos de coste y sus miembros respectivos se admiten.</span><span class="sxs-lookup"><span data-stu-id="13b90-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="13b90-473">El orden de asignación se controla por unidad de control de costes.</span><span class="sxs-lookup"><span data-stu-id="13b90-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="13b90-474">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="13b90-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="13b90-475">Defina la asignación de costes</span><span class="sxs-lookup"><span data-stu-id="13b90-475">Define the cost allocation</span></span>

<span data-ttu-id="13b90-476">A continuación se indica un ejemplo sencillo que explica cómo puede realizar el seguimiento del flujo de coste.</span><span class="sxs-lookup"><span data-stu-id="13b90-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="13b90-477">El objeto de coste CC001 HR contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="13b90-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="13b90-478">Se crea un miembro de dimensión estadística que se denomina servicios HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="13b90-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="13b90-479">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-479">Cost object</span></span></th>
<th><span data-ttu-id="13b90-480">Servicios HR</span><span class="sxs-lookup"><span data-stu-id="13b90-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-481">CC002</span><span class="sxs-lookup"><span data-stu-id="13b90-481">CC002</span></span></td>
<td><span data-ttu-id="13b90-482">Finanzas</span><span class="sxs-lookup"><span data-stu-id="13b90-482">Finance</span></span></td>
<td><span data-ttu-id="13b90-483">35</span><span class="sxs-lookup"><span data-stu-id="13b90-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-484">CC003</span><span class="sxs-lookup"><span data-stu-id="13b90-484">CC003</span></span></td>
<td><span data-ttu-id="13b90-485">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="13b90-485">Assembly</span></span></td>
<td><span data-ttu-id="13b90-486">55</span><span class="sxs-lookup"><span data-stu-id="13b90-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-487">CC004</span><span class="sxs-lookup"><span data-stu-id="13b90-487">CC004</span></span></td>
<td><span data-ttu-id="13b90-488">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="13b90-488">Packaging</span></span></td>
<td><span data-ttu-id="13b90-489">10</span><span class="sxs-lookup"><span data-stu-id="13b90-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="13b90-490">El objeto de coste CC002 Finanzas contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="13b90-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="13b90-491">Se crea un miembro de dimensión estadística que se denomina Finanzas para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="13b90-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="13b90-492">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-492">Cost object</span></span></th>
<th><span data-ttu-id="13b90-493">Servicios financieros</span><span class="sxs-lookup"><span data-stu-id="13b90-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-494">CC003</span><span class="sxs-lookup"><span data-stu-id="13b90-494">CC003</span></span></td>
<td><span data-ttu-id="13b90-495">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="13b90-495">Assembly</span></span></td>
<td><span data-ttu-id="13b90-496">65</span><span class="sxs-lookup"><span data-stu-id="13b90-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-497">CC004</span><span class="sxs-lookup"><span data-stu-id="13b90-497">CC004</span></span></td>
<td><span data-ttu-id="13b90-498">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="13b90-498">Packaging</span></span></td>
<td><span data-ttu-id="13b90-499">35</span><span class="sxs-lookup"><span data-stu-id="13b90-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="13b90-500">El objeto de coste CC003 Asamblea contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="13b90-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="13b90-501">Se crea un miembro de dimensión estadística que se denomina servicios de Asamblea para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="13b90-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="13b90-502">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-502">Cost object</span></span></th>
<th><span data-ttu-id="13b90-503">Servicios de la asamblea (horas)</span><span class="sxs-lookup"><span data-stu-id="13b90-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="13b90-504">Prod 1</span></span></td>
<td><span data-ttu-id="13b90-505">Producto 1</span><span class="sxs-lookup"><span data-stu-id="13b90-505">Product 1</span></span></td>
<td><span data-ttu-id="13b90-506">60</span><span class="sxs-lookup"><span data-stu-id="13b90-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="13b90-507">Prod 2</span></span></td>
<td><span data-ttu-id="13b90-508">Producto 2</span><span class="sxs-lookup"><span data-stu-id="13b90-508">Product 2</span></span></td>
<td><span data-ttu-id="13b90-509">20</span><span class="sxs-lookup"><span data-stu-id="13b90-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="13b90-510">El objeto de coste CC004 Embalaje contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="13b90-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="13b90-511">Se crea un miembro de dimensión estadística que se denomina servicios de Embalaje para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="13b90-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="13b90-512">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-512">Cost object</span></span></th>
<th><span data-ttu-id="13b90-513">Servicios de embalaje (horas)</span><span class="sxs-lookup"><span data-stu-id="13b90-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="13b90-514">Prod 1</span></span></td>
<td><span data-ttu-id="13b90-515">Producto 1</span><span class="sxs-lookup"><span data-stu-id="13b90-515">Product 1</span></span></td>
<td><span data-ttu-id="13b90-516">80</span><span class="sxs-lookup"><span data-stu-id="13b90-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="13b90-517">Prod 2</span></span></td>
<td><span data-ttu-id="13b90-518">Producto 2</span><span class="sxs-lookup"><span data-stu-id="13b90-518">Product 2</span></span></td>
<td><span data-ttu-id="13b90-519">15</span><span class="sxs-lookup"><span data-stu-id="13b90-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="13b90-520">Las medidas estadísticas como las horas de la producción que un producto consume se pueden deducir de los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="13b90-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="13b90-521">Para obtener más información, vea [Plantilla de proveedor de medidas estadísticas](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="13b90-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="13b90-522">La tabla siguiente muestra el resultado cuando se aplican los servicios de HR como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="13b90-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="13b90-523">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-523">Cost object</span></span></th>
<th><span data-ttu-id="13b90-524">Magnitud</span><span class="sxs-lookup"><span data-stu-id="13b90-524">Magnitude</span></span></th>
<th><span data-ttu-id="13b90-525">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="13b90-525">Allocation factor</span></span></th>
<th><span data-ttu-id="13b90-526">Importe</span><span class="sxs-lookup"><span data-stu-id="13b90-526">Amount</span></span></th>
<th><span data-ttu-id="13b90-527">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="13b90-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-528">CC002</span><span class="sxs-lookup"><span data-stu-id="13b90-528">CC002</span></span></td>
<td><span data-ttu-id="13b90-529">Finanzas</span><span class="sxs-lookup"><span data-stu-id="13b90-529">Finance</span></span></td>
<td><span data-ttu-id="13b90-530">35</span><span class="sxs-lookup"><span data-stu-id="13b90-530">35</span></span></td>
<td><span data-ttu-id="13b90-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="13b90-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="13b90-532">175.00</span><span class="sxs-lookup"><span data-stu-id="13b90-532">175.00</span></span></td>
<td><span data-ttu-id="13b90-533">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-534">CC003</span><span class="sxs-lookup"><span data-stu-id="13b90-534">CC003</span></span></td>
<td><span data-ttu-id="13b90-535">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="13b90-535">Assembly</span></span></td>
<td><span data-ttu-id="13b90-536">55</span><span class="sxs-lookup"><span data-stu-id="13b90-536">55</span></span></td>
<td><span data-ttu-id="13b90-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="13b90-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="13b90-538">275.00</span><span class="sxs-lookup"><span data-stu-id="13b90-538">275.00</span></span></td>
<td><span data-ttu-id="13b90-539">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-540">CC004</span><span class="sxs-lookup"><span data-stu-id="13b90-540">CC004</span></span></td>
<td><span data-ttu-id="13b90-541">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="13b90-541">Packaging</span></span></td>
<td><span data-ttu-id="13b90-542">10</span><span class="sxs-lookup"><span data-stu-id="13b90-542">10</span></span></td>
<td><span data-ttu-id="13b90-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="13b90-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="13b90-544">50,00</span><span class="sxs-lookup"><span data-stu-id="13b90-544">50.00</span></span></td>
<td><span data-ttu-id="13b90-545">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-546">CC002</span><span class="sxs-lookup"><span data-stu-id="13b90-546">CC002</span></span></td>
<td><span data-ttu-id="13b90-547">Finanzas</span><span class="sxs-lookup"><span data-stu-id="13b90-547">Finance</span></span></td>
<td><span data-ttu-id="13b90-548">35</span><span class="sxs-lookup"><span data-stu-id="13b90-548">35</span></span></td>
<td><span data-ttu-id="13b90-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="13b90-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="13b90-550">436.00</span><span class="sxs-lookup"><span data-stu-id="13b90-550">436.00</span></span></td>
<td><span data-ttu-id="13b90-551">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-552">CC003</span><span class="sxs-lookup"><span data-stu-id="13b90-552">CC003</span></span></td>
<td><span data-ttu-id="13b90-553">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="13b90-553">Assembly</span></span></td>
<td><span data-ttu-id="13b90-554">55</span><span class="sxs-lookup"><span data-stu-id="13b90-554">55</span></span></td>
<td><span data-ttu-id="13b90-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="13b90-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="13b90-556">685.14</span><span class="sxs-lookup"><span data-stu-id="13b90-556">685.14</span></span></td>
<td><span data-ttu-id="13b90-557">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-558">CC004</span><span class="sxs-lookup"><span data-stu-id="13b90-558">CC004</span></span></td>
<td><span data-ttu-id="13b90-559">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="13b90-559">Packaging</span></span></td>
<td><span data-ttu-id="13b90-560">10</span><span class="sxs-lookup"><span data-stu-id="13b90-560">10</span></span></td>
<td><span data-ttu-id="13b90-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="13b90-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="13b90-562">124.57</span><span class="sxs-lookup"><span data-stu-id="13b90-562">124.57</span></span></td>
<td><span data-ttu-id="13b90-563">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="13b90-564">La tabla siguiente muestra el resultado cuando se aplican los servicios de Finanzas como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="13b90-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="13b90-565">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-565">Cost object</span></span></th>
<th><span data-ttu-id="13b90-566">Magnitud</span><span class="sxs-lookup"><span data-stu-id="13b90-566">Magnitude</span></span></th>
<th><span data-ttu-id="13b90-567">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="13b90-567">Allocation factor</span></span></th>
<th><span data-ttu-id="13b90-568">Importe</span><span class="sxs-lookup"><span data-stu-id="13b90-568">Amount</span></span></th>
<th><span data-ttu-id="13b90-569">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="13b90-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-570">CC003</span><span class="sxs-lookup"><span data-stu-id="13b90-570">CC003</span></span></td>
<td><span data-ttu-id="13b90-571">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="13b90-571">Assembly</span></span></td>
<td><span data-ttu-id="13b90-572">65</span><span class="sxs-lookup"><span data-stu-id="13b90-572">65</span></span></td>
<td><span data-ttu-id="13b90-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="13b90-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="13b90-574">438.75</span><span class="sxs-lookup"><span data-stu-id="13b90-574">438.75</span></span></td>
<td><span data-ttu-id="13b90-575">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-576">CC004</span><span class="sxs-lookup"><span data-stu-id="13b90-576">CC004</span></span></td>
<td><span data-ttu-id="13b90-577">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="13b90-577">Packaging</span></span></td>
<td><span data-ttu-id="13b90-578">35</span><span class="sxs-lookup"><span data-stu-id="13b90-578">35</span></span></td>
<td><span data-ttu-id="13b90-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="13b90-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="13b90-580">236.25</span><span class="sxs-lookup"><span data-stu-id="13b90-580">236.25</span></span></td>
<td><span data-ttu-id="13b90-581">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-582">CC003</span><span class="sxs-lookup"><span data-stu-id="13b90-582">CC003</span></span></td>
<td><span data-ttu-id="13b90-583">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="13b90-583">Assembly</span></span></td>
<td><span data-ttu-id="13b90-584">65</span><span class="sxs-lookup"><span data-stu-id="13b90-584">65</span></span></td>
<td><span data-ttu-id="13b90-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="13b90-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="13b90-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="13b90-586">5,297.69</span></span></td>
<td><span data-ttu-id="13b90-587">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-588">CC004</span><span class="sxs-lookup"><span data-stu-id="13b90-588">CC004</span></span></td>
<td><span data-ttu-id="13b90-589">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="13b90-589">Packaging</span></span></td>
<td><span data-ttu-id="13b90-590">35</span><span class="sxs-lookup"><span data-stu-id="13b90-590">35</span></span></td>
<td><span data-ttu-id="13b90-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="13b90-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="13b90-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="13b90-592">2,852.60</span></span></td>
<td><span data-ttu-id="13b90-593">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="13b90-594">La tabla siguiente muestra el resultado cuando se aplican los servicios de Asamblea como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="13b90-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="13b90-595">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-595">Cost object</span></span></th>
<th><span data-ttu-id="13b90-596">Magnitud</span><span class="sxs-lookup"><span data-stu-id="13b90-596">Magnitude</span></span></th>
<th><span data-ttu-id="13b90-597">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="13b90-597">Allocation factor</span></span></th>
<th><span data-ttu-id="13b90-598">Importe</span><span class="sxs-lookup"><span data-stu-id="13b90-598">Amount</span></span></th>
<th><span data-ttu-id="13b90-599">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="13b90-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="13b90-600">Prod 1</span></span></td>
<td><span data-ttu-id="13b90-601">Producto 1</span><span class="sxs-lookup"><span data-stu-id="13b90-601">Product 1</span></span></td>
<td><span data-ttu-id="13b90-602">60</span><span class="sxs-lookup"><span data-stu-id="13b90-602">60</span></span></td>
<td><span data-ttu-id="13b90-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="13b90-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="13b90-604">535.31</span><span class="sxs-lookup"><span data-stu-id="13b90-604">535.31</span></span></td>
<td><span data-ttu-id="13b90-605">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="13b90-606">Prod 2</span></span></td>
<td><span data-ttu-id="13b90-607">Producto 2</span><span class="sxs-lookup"><span data-stu-id="13b90-607">Product 2</span></span></td>
<td><span data-ttu-id="13b90-608">20</span><span class="sxs-lookup"><span data-stu-id="13b90-608">20</span></span></td>
<td><span data-ttu-id="13b90-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="13b90-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="13b90-610">178.44</span><span class="sxs-lookup"><span data-stu-id="13b90-610">178.44</span></span></td>
<td><span data-ttu-id="13b90-611">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="13b90-612">Prod 1</span></span></td>
<td><span data-ttu-id="13b90-613">Producto 1</span><span class="sxs-lookup"><span data-stu-id="13b90-613">Product 1</span></span></td>
<td><span data-ttu-id="13b90-614">60</span><span class="sxs-lookup"><span data-stu-id="13b90-614">60</span></span></td>
<td><span data-ttu-id="13b90-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="13b90-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="13b90-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="13b90-616">4,487.12</span></span></td>
<td><span data-ttu-id="13b90-617">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="13b90-618">Prod 2</span></span></td>
<td><span data-ttu-id="13b90-619">Producto 2</span><span class="sxs-lookup"><span data-stu-id="13b90-619">Product 2</span></span></td>
<td><span data-ttu-id="13b90-620">20</span><span class="sxs-lookup"><span data-stu-id="13b90-620">20</span></span></td>
<td><span data-ttu-id="13b90-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="13b90-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="13b90-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="13b90-622">1,495.71</span></span></td>
<td><span data-ttu-id="13b90-623">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="13b90-624">La tabla siguiente muestra el resultado cuando se aplican los servicios de Embalaje como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="13b90-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="13b90-625">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-625">Cost object</span></span></th>
<th><span data-ttu-id="13b90-626">Magnitud</span><span class="sxs-lookup"><span data-stu-id="13b90-626">Magnitude</span></span></th>
<th><span data-ttu-id="13b90-627">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="13b90-627">Allocation factor</span></span></th>
<th><span data-ttu-id="13b90-628">Importe</span><span class="sxs-lookup"><span data-stu-id="13b90-628">Amount</span></span></th>
<th><span data-ttu-id="13b90-629">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="13b90-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="13b90-630">Prod 1</span></span></td>
<td><span data-ttu-id="13b90-631">Producto 1</span><span class="sxs-lookup"><span data-stu-id="13b90-631">Product 1</span></span></td>
<td><span data-ttu-id="13b90-632">80</span><span class="sxs-lookup"><span data-stu-id="13b90-632">80</span></span></td>
<td><span data-ttu-id="13b90-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="13b90-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="13b90-634">241.05</span><span class="sxs-lookup"><span data-stu-id="13b90-634">241.05</span></span></td>
<td><span data-ttu-id="13b90-635">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="13b90-636">Prod 2</span></span></td>
<td><span data-ttu-id="13b90-637">Producto 2</span><span class="sxs-lookup"><span data-stu-id="13b90-637">Product 2</span></span></td>
<td><span data-ttu-id="13b90-638">15</span><span class="sxs-lookup"><span data-stu-id="13b90-638">15</span></span></td>
<td><span data-ttu-id="13b90-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="13b90-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="13b90-640">45.20</span><span class="sxs-lookup"><span data-stu-id="13b90-640">45.20</span></span></td>
<td><span data-ttu-id="13b90-641">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="13b90-642">Prod 1</span></span></td>
<td><span data-ttu-id="13b90-643">Producto 1</span><span class="sxs-lookup"><span data-stu-id="13b90-643">Product 1</span></span></td>
<td><span data-ttu-id="13b90-644">80</span><span class="sxs-lookup"><span data-stu-id="13b90-644">80</span></span></td>
<td><span data-ttu-id="13b90-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="13b90-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="13b90-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="13b90-646">2,507.09</span></span></td>
<td><span data-ttu-id="13b90-647">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="13b90-648">Prod 2</span></span></td>
<td><span data-ttu-id="13b90-649">Producto 2</span><span class="sxs-lookup"><span data-stu-id="13b90-649">Product 2</span></span></td>
<td><span data-ttu-id="13b90-650">15</span><span class="sxs-lookup"><span data-stu-id="13b90-650">15</span></span></td>
<td><span data-ttu-id="13b90-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="13b90-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="13b90-652">470.08</span><span class="sxs-lookup"><span data-stu-id="13b90-652">470.08</span></span></td>
<td><span data-ttu-id="13b90-653">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="13b90-654">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="13b90-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="13b90-655">Diario</span><span class="sxs-lookup"><span data-stu-id="13b90-655">Journal</span></span></th>
<th><span data-ttu-id="13b90-656">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="13b90-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="13b90-657">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="13b90-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="13b90-658">Versión</span><span class="sxs-lookup"><span data-stu-id="13b90-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-659">00004</span><span class="sxs-lookup"><span data-stu-id="13b90-659">00004</span></span></td>
<td><span data-ttu-id="13b90-660">Diario de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="13b90-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="13b90-661">Fiscal</span><span class="sxs-lookup"><span data-stu-id="13b90-661">Fiscal</span></span></td>
<td><span data-ttu-id="13b90-662">2017</span><span class="sxs-lookup"><span data-stu-id="13b90-662">2017</span></span></td>
<td><span data-ttu-id="13b90-663">Período 1</span><span class="sxs-lookup"><span data-stu-id="13b90-663">Period 1</span></span></td>
<td><span data-ttu-id="13b90-664">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="13b90-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="13b90-665">Líneas de diario</span><span class="sxs-lookup"><span data-stu-id="13b90-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="13b90-666">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="13b90-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="13b90-667">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="13b90-668">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-668">Cost element</span></span></th>
<th><span data-ttu-id="13b90-669">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="13b90-669">Cost behavior</span></span></th>
<th><span data-ttu-id="13b90-670">Importe</span><span class="sxs-lookup"><span data-stu-id="13b90-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-671">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="13b90-672">CC001</span><span class="sxs-lookup"><span data-stu-id="13b90-672">CC001</span></span></td>
<td><span data-ttu-id="13b90-673">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="13b90-673">HR</span></span></td>
<td><span data-ttu-id="13b90-674">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-674">10001</span></span></td>
<td><span data-ttu-id="13b90-675">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-675">Electricity</span></span></td>
<td><span data-ttu-id="13b90-676">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-676">Fixed cost</span></span></td>
<td><span data-ttu-id="13b90-677">500,00</span><span class="sxs-lookup"><span data-stu-id="13b90-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-678">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="13b90-679">CC001</span><span class="sxs-lookup"><span data-stu-id="13b90-679">CC001</span></span></td>
<td><span data-ttu-id="13b90-680">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="13b90-680">HR</span></span></td>
<td><span data-ttu-id="13b90-681">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-681">10001</span></span></td>
<td><span data-ttu-id="13b90-682">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-682">Electricity</span></span></td>
<td><span data-ttu-id="13b90-683">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-683">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="13b90-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-685">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="13b90-686">CC002</span><span class="sxs-lookup"><span data-stu-id="13b90-686">CC002</span></span></td>
<td><span data-ttu-id="13b90-687">Finanzas</span><span class="sxs-lookup"><span data-stu-id="13b90-687">Finance</span></span></td>
<td><span data-ttu-id="13b90-688">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-688">10001</span></span></td>
<td><span data-ttu-id="13b90-689">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-689">Electricity</span></span></td>
<td><span data-ttu-id="13b90-690">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-690">Fixed cost</span></span></td>
<td><span data-ttu-id="13b90-691">675.00</span><span class="sxs-lookup"><span data-stu-id="13b90-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-692">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="13b90-693">CC002</span><span class="sxs-lookup"><span data-stu-id="13b90-693">CC002</span></span></td>
<td><span data-ttu-id="13b90-694">Finanzas</span><span class="sxs-lookup"><span data-stu-id="13b90-694">Finance</span></span></td>
<td><span data-ttu-id="13b90-695">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-695">10001</span></span></td>
<td><span data-ttu-id="13b90-696">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-696">Electricity</span></span></td>
<td><span data-ttu-id="13b90-697">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-697">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="13b90-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-699">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="13b90-700">CC003</span><span class="sxs-lookup"><span data-stu-id="13b90-700">CC003</span></span></td>
<td><span data-ttu-id="13b90-701">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="13b90-701">Assembly</span></span></td>
<td><span data-ttu-id="13b90-702">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-702">10001</span></span></td>
<td><span data-ttu-id="13b90-703">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-703">Electricity</span></span></td>
<td><span data-ttu-id="13b90-704">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-704">Fixed cost</span></span></td>
<td><span data-ttu-id="13b90-705">713.75</span><span class="sxs-lookup"><span data-stu-id="13b90-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-706">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="13b90-707">CC003</span><span class="sxs-lookup"><span data-stu-id="13b90-707">CC003</span></span></td>
<td><span data-ttu-id="13b90-708">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="13b90-708">Assembly</span></span></td>
<td><span data-ttu-id="13b90-709">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-709">10001</span></span></td>
<td><span data-ttu-id="13b90-710">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-710">Electricity</span></span></td>
<td><span data-ttu-id="13b90-711">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-711">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="13b90-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-713">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="13b90-714">CC003</span><span class="sxs-lookup"><span data-stu-id="13b90-714">CC003</span></span></td>
<td><span data-ttu-id="13b90-715">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="13b90-715">Packaging</span></span></td>
<td><span data-ttu-id="13b90-716">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-716">10001</span></span></td>
<td><span data-ttu-id="13b90-717">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-717">Electricity</span></span></td>
<td><span data-ttu-id="13b90-718">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-718">Fixed cost</span></span></td>
<td><span data-ttu-id="13b90-719">286.25</span><span class="sxs-lookup"><span data-stu-id="13b90-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-720">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="13b90-721">CC003</span><span class="sxs-lookup"><span data-stu-id="13b90-721">CC003</span></span></td>
<td><span data-ttu-id="13b90-722">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="13b90-722">Packaging</span></span></td>
<td><span data-ttu-id="13b90-723">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-723">10001</span></span></td>
<td><span data-ttu-id="13b90-724">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-724">Electricity</span></span></td>
<td><span data-ttu-id="13b90-725">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-725">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="13b90-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-727">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="13b90-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="13b90-728">Prod 1</span></span></td>
<td><span data-ttu-id="13b90-729">Producto 1</span><span class="sxs-lookup"><span data-stu-id="13b90-729">Product 1</span></span></td>
<td><span data-ttu-id="13b90-730">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-730">10001</span></span></td>
<td><span data-ttu-id="13b90-731">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-731">Electricity</span></span></td>
<td><span data-ttu-id="13b90-732">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-732">Fixed cost</span></span></td>
<td><span data-ttu-id="13b90-733">776.36</span><span class="sxs-lookup"><span data-stu-id="13b90-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-734">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="13b90-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="13b90-735">Prod 1</span></span></td>
<td><span data-ttu-id="13b90-736">Producto 1</span><span class="sxs-lookup"><span data-stu-id="13b90-736">Product 1</span></span></td>
<td><span data-ttu-id="13b90-737">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-737">10001</span></span></td>
<td><span data-ttu-id="13b90-738">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-738">Electricity</span></span></td>
<td><span data-ttu-id="13b90-739">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-739">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="13b90-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-741">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="13b90-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="13b90-742">Prod 2</span></span></td>
<td><span data-ttu-id="13b90-743">Producto 1</span><span class="sxs-lookup"><span data-stu-id="13b90-743">Product 1</span></span></td>
<td><span data-ttu-id="13b90-744">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-744">10001</span></span></td>
<td><span data-ttu-id="13b90-745">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-745">Electricity</span></span></td>
<td><span data-ttu-id="13b90-746">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-746">Fixed cost</span></span></td>
<td><span data-ttu-id="13b90-747">223.64</span><span class="sxs-lookup"><span data-stu-id="13b90-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-748">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="13b90-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="13b90-749">Prod 2</span></span></td>
<td><span data-ttu-id="13b90-750">Producto 1</span><span class="sxs-lookup"><span data-stu-id="13b90-750">Product 1</span></span></td>
<td><span data-ttu-id="13b90-751">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-751">10001</span></span></td>
<td><span data-ttu-id="13b90-752">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-752">Electricity</span></span></td>
<td><span data-ttu-id="13b90-753">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-753">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="13b90-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="13b90-755">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="13b90-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="13b90-756">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="13b90-757">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-757">Cost element</span></span></th>
<th><span data-ttu-id="13b90-758">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="13b90-758">Cost behavior</span></span></th>
<th><span data-ttu-id="13b90-759">Importe</span><span class="sxs-lookup"><span data-stu-id="13b90-759">Amount</span></span></th>
<th><span data-ttu-id="13b90-760">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="13b90-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="13b90-761">CC001</span><span class="sxs-lookup"><span data-stu-id="13b90-761">CC001</span></span></td>
<td><span data-ttu-id="13b90-762">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="13b90-762">HR</span></span></td>
<td><span data-ttu-id="13b90-763">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-763">10001</span></span></td>
<td><span data-ttu-id="13b90-764">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-764">Electricity</span></span></td>
<td><span data-ttu-id="13b90-765">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-765">Fixed cost</span></span></td>
<td><span data-ttu-id="13b90-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="13b90-766">-500.00</span></span></td>
<td><span data-ttu-id="13b90-767">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-768">CC002</span><span class="sxs-lookup"><span data-stu-id="13b90-768">CC002</span></span></td>
<td><span data-ttu-id="13b90-769">Finanzas</span><span class="sxs-lookup"><span data-stu-id="13b90-769">Finance</span></span></td>
<td><span data-ttu-id="13b90-770">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-770">10001</span></span></td>
<td><span data-ttu-id="13b90-771">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-771">Electricity</span></span></td>
<td><span data-ttu-id="13b90-772">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-772">Fixed cost</span></span></td>
<td><span data-ttu-id="13b90-773">175.00</span><span class="sxs-lookup"><span data-stu-id="13b90-773">175.00</span></span></td>
<td><span data-ttu-id="13b90-774">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-775">CC003</span><span class="sxs-lookup"><span data-stu-id="13b90-775">CC003</span></span></td>
<td><span data-ttu-id="13b90-776">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="13b90-776">Assembly</span></span></td>
<td><span data-ttu-id="13b90-777">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-777">10001</span></span></td>
<td><span data-ttu-id="13b90-778">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-778">Electricity</span></span></td>
<td><span data-ttu-id="13b90-779">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-779">Fixed cost</span></span></td>
<td><span data-ttu-id="13b90-780">275.00</span><span class="sxs-lookup"><span data-stu-id="13b90-780">275.00</span></span></td>
<td><span data-ttu-id="13b90-781">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-782">CC004</span><span class="sxs-lookup"><span data-stu-id="13b90-782">CC004</span></span></td>
<td><span data-ttu-id="13b90-783">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="13b90-783">Packaging</span></span></td>
<td><span data-ttu-id="13b90-784">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-784">10001</span></span></td>
<td><span data-ttu-id="13b90-785">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-785">Electricity</span></span></td>
<td><span data-ttu-id="13b90-786">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-786">Fixed cost</span></span></td>
<td><span data-ttu-id="13b90-787">50,00</span><span class="sxs-lookup"><span data-stu-id="13b90-787">50,00</span></span></td>
<td><span data-ttu-id="13b90-788">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-789">CC001</span><span class="sxs-lookup"><span data-stu-id="13b90-789">CC001</span></span></td>
<td><span data-ttu-id="13b90-790">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="13b90-790">HR</span></span></td>
<td><span data-ttu-id="13b90-791">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-791">10001</span></span></td>
<td><span data-ttu-id="13b90-792">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-792">Electricity</span></span></td>
<td><span data-ttu-id="13b90-793">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-793">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="13b90-794">-1,245.71</span></span></td>
<td><span data-ttu-id="13b90-795">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-796">CC002</span><span class="sxs-lookup"><span data-stu-id="13b90-796">CC002</span></span></td>
<td><span data-ttu-id="13b90-797">Finanzas</span><span class="sxs-lookup"><span data-stu-id="13b90-797">Finance</span></span></td>
<td><span data-ttu-id="13b90-798">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-798">10001</span></span></td>
<td><span data-ttu-id="13b90-799">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-799">Electricity</span></span></td>
<td><span data-ttu-id="13b90-800">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-800">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-801">436.00</span><span class="sxs-lookup"><span data-stu-id="13b90-801">436.00</span></span></td>
<td><span data-ttu-id="13b90-802">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-803">CC003</span><span class="sxs-lookup"><span data-stu-id="13b90-803">CC003</span></span></td>
<td><span data-ttu-id="13b90-804">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="13b90-804">Assembly</span></span></td>
<td><span data-ttu-id="13b90-805">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-805">10001</span></span></td>
<td><span data-ttu-id="13b90-806">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-806">Electricity</span></span></td>
<td><span data-ttu-id="13b90-807">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-807">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-808">685.14</span><span class="sxs-lookup"><span data-stu-id="13b90-808">685.14</span></span></td>
<td><span data-ttu-id="13b90-809">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-810">CC004</span><span class="sxs-lookup"><span data-stu-id="13b90-810">CC004</span></span></td>
<td><span data-ttu-id="13b90-811">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="13b90-811">Packaging</span></span></td>
<td><span data-ttu-id="13b90-812">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-812">10001</span></span></td>
<td><span data-ttu-id="13b90-813">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-813">Electricity</span></span></td>
<td><span data-ttu-id="13b90-814">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-814">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-815">124.57</span><span class="sxs-lookup"><span data-stu-id="13b90-815">124.57</span></span></td>
<td><span data-ttu-id="13b90-816">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-817">CC002</span><span class="sxs-lookup"><span data-stu-id="13b90-817">CC002</span></span></td>
<td><span data-ttu-id="13b90-818">Finanzas</span><span class="sxs-lookup"><span data-stu-id="13b90-818">Finance</span></span></td>
<td><span data-ttu-id="13b90-819">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-819">10001</span></span></td>
<td><span data-ttu-id="13b90-820">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-820">Electricity</span></span></td>
<td><span data-ttu-id="13b90-821">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-821">Fixed cost</span></span></td>
<td><span data-ttu-id="13b90-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="13b90-822">-675.00</span></span></td>
<td><span data-ttu-id="13b90-823">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-824">CC003</span><span class="sxs-lookup"><span data-stu-id="13b90-824">CC003</span></span></td>
<td><span data-ttu-id="13b90-825">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="13b90-825">Assembly</span></span></td>
<td><span data-ttu-id="13b90-826">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-826">10001</span></span></td>
<td><span data-ttu-id="13b90-827">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-827">Electricity</span></span></td>
<td><span data-ttu-id="13b90-828">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-828">Fixed cost</span></span></td>
<td><span data-ttu-id="13b90-829">438.75</span><span class="sxs-lookup"><span data-stu-id="13b90-829">438.75</span></span></td>
<td><span data-ttu-id="13b90-830">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-831">CC004</span><span class="sxs-lookup"><span data-stu-id="13b90-831">CC004</span></span></td>
<td><span data-ttu-id="13b90-832">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="13b90-832">Packaging</span></span></td>
<td><span data-ttu-id="13b90-833">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-833">10001</span></span></td>
<td><span data-ttu-id="13b90-834">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-834">Electricity</span></span></td>
<td><span data-ttu-id="13b90-835">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-835">Fixed cost</span></span></td>
<td><span data-ttu-id="13b90-836">236.25</span><span class="sxs-lookup"><span data-stu-id="13b90-836">236.25</span></span></td>
<td><span data-ttu-id="13b90-837">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-838">CC002</span><span class="sxs-lookup"><span data-stu-id="13b90-838">CC002</span></span></td>
<td><span data-ttu-id="13b90-839">Finanzas</span><span class="sxs-lookup"><span data-stu-id="13b90-839">Finance</span></span></td>
<td><span data-ttu-id="13b90-840">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-840">10001</span></span></td>
<td><span data-ttu-id="13b90-841">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-841">Electricity</span></span></td>
<td><span data-ttu-id="13b90-842">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-842">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="13b90-843">-8,150.29</span></span></td>
<td><span data-ttu-id="13b90-844">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-845">CC003</span><span class="sxs-lookup"><span data-stu-id="13b90-845">CC003</span></span></td>
<td><span data-ttu-id="13b90-846">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="13b90-846">Assembly</span></span></td>
<td><span data-ttu-id="13b90-847">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-847">10001</span></span></td>
<td><span data-ttu-id="13b90-848">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-848">Electricity</span></span></td>
<td><span data-ttu-id="13b90-849">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-849">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="13b90-850">5,297.69</span></span></td>
<td><span data-ttu-id="13b90-851">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-852">CC004</span><span class="sxs-lookup"><span data-stu-id="13b90-852">CC004</span></span></td>
<td><span data-ttu-id="13b90-853">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="13b90-853">Packaging</span></span></td>
<td><span data-ttu-id="13b90-854">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-854">10001</span></span></td>
<td><span data-ttu-id="13b90-855">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-855">Electricity</span></span></td>
<td><span data-ttu-id="13b90-856">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-856">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="13b90-857">2,852.60</span></span></td>
<td><span data-ttu-id="13b90-858">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-859">CC003</span><span class="sxs-lookup"><span data-stu-id="13b90-859">CC003</span></span></td>
<td><span data-ttu-id="13b90-860">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="13b90-860">Assembly</span></span></td>
<td><span data-ttu-id="13b90-861">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-861">10001</span></span></td>
<td><span data-ttu-id="13b90-862">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-862">Electricity</span></span></td>
<td><span data-ttu-id="13b90-863">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-863">Fixed cost</span></span></td>
<td><span data-ttu-id="13b90-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="13b90-864">-713.75</span></span></td>
<td><span data-ttu-id="13b90-865">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="13b90-866">Prod 1</span></span></td>
<td><span data-ttu-id="13b90-867">Producto 1</span><span class="sxs-lookup"><span data-stu-id="13b90-867">Product 1</span></span></td>
<td><span data-ttu-id="13b90-868">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-868">10001</span></span></td>
<td><span data-ttu-id="13b90-869">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-869">Electricity</span></span></td>
<td><span data-ttu-id="13b90-870">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-870">Fixed cost</span></span></td>
<td><span data-ttu-id="13b90-871">535.31</span><span class="sxs-lookup"><span data-stu-id="13b90-871">535.31</span></span></td>
<td><span data-ttu-id="13b90-872">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="13b90-873">Prod 2</span></span></td>
<td><span data-ttu-id="13b90-874">Producto 2</span><span class="sxs-lookup"><span data-stu-id="13b90-874">Product 2</span></span></td>
<td><span data-ttu-id="13b90-875">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-875">10001</span></span></td>
<td><span data-ttu-id="13b90-876">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-876">Electricity</span></span></td>
<td><span data-ttu-id="13b90-877">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-877">Fixed cost</span></span></td>
<td><span data-ttu-id="13b90-878">178.44</span><span class="sxs-lookup"><span data-stu-id="13b90-878">178.44</span></span></td>
<td><span data-ttu-id="13b90-879">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-880">CC003</span><span class="sxs-lookup"><span data-stu-id="13b90-880">CC003</span></span></td>
<td><span data-ttu-id="13b90-881">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="13b90-881">Assembly</span></span></td>
<td><span data-ttu-id="13b90-882">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-882">10001</span></span></td>
<td><span data-ttu-id="13b90-883">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-883">Electricity</span></span></td>
<td><span data-ttu-id="13b90-884">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-884">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="13b90-885">-5,982.83</span></span></td>
<td><span data-ttu-id="13b90-886">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="13b90-887">Prod 1</span></span></td>
<td><span data-ttu-id="13b90-888">Producto 1</span><span class="sxs-lookup"><span data-stu-id="13b90-888">Product 1</span></span></td>
<td><span data-ttu-id="13b90-889">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-889">10001</span></span></td>
<td><span data-ttu-id="13b90-890">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-890">Electricity</span></span></td>
<td><span data-ttu-id="13b90-891">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-891">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="13b90-892">4,487.12</span></span></td>
<td><span data-ttu-id="13b90-893">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="13b90-894">Prod 2</span></span></td>
<td><span data-ttu-id="13b90-895">Producto 2</span><span class="sxs-lookup"><span data-stu-id="13b90-895">Product 2</span></span></td>
<td><span data-ttu-id="13b90-896">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-896">10001</span></span></td>
<td><span data-ttu-id="13b90-897">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-897">Electricity</span></span></td>
<td><span data-ttu-id="13b90-898">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-898">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="13b90-899">1,495.71</span></span></td>
<td><span data-ttu-id="13b90-900">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-901">CC003</span><span class="sxs-lookup"><span data-stu-id="13b90-901">CC003</span></span></td>
<td><span data-ttu-id="13b90-902">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="13b90-902">Assembly</span></span></td>
<td><span data-ttu-id="13b90-903">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-903">10001</span></span></td>
<td><span data-ttu-id="13b90-904">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-904">Electricity</span></span></td>
<td><span data-ttu-id="13b90-905">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-905">Fixed cost</span></span></td>
<td><span data-ttu-id="13b90-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="13b90-906">-286.25</span></span></td>
<td><span data-ttu-id="13b90-907">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="13b90-908">Prod 1</span></span></td>
<td><span data-ttu-id="13b90-909">Producto 1</span><span class="sxs-lookup"><span data-stu-id="13b90-909">Product 1</span></span></td>
<td><span data-ttu-id="13b90-910">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-910">10001</span></span></td>
<td><span data-ttu-id="13b90-911">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-911">Electricity</span></span></td>
<td><span data-ttu-id="13b90-912">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-912">Fixed cost</span></span></td>
<td><span data-ttu-id="13b90-913">241.05</span><span class="sxs-lookup"><span data-stu-id="13b90-913">241.05</span></span></td>
<td><span data-ttu-id="13b90-914">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="13b90-915">Prod 2</span></span></td>
<td><span data-ttu-id="13b90-916">Producto 2</span><span class="sxs-lookup"><span data-stu-id="13b90-916">Product 2</span></span></td>
<td><span data-ttu-id="13b90-917">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-917">10001</span></span></td>
<td><span data-ttu-id="13b90-918">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-918">Electricity</span></span></td>
<td><span data-ttu-id="13b90-919">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-919">Fixed cost</span></span></td>
<td><span data-ttu-id="13b90-920">45.20</span><span class="sxs-lookup"><span data-stu-id="13b90-920">45.20</span></span></td>
<td><span data-ttu-id="13b90-921">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-922">CC003</span><span class="sxs-lookup"><span data-stu-id="13b90-922">CC003</span></span></td>
<td><span data-ttu-id="13b90-923">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="13b90-923">Assembly</span></span></td>
<td><span data-ttu-id="13b90-924">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-924">10001</span></span></td>
<td><span data-ttu-id="13b90-925">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-925">Electricity</span></span></td>
<td><span data-ttu-id="13b90-926">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-926">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="13b90-927">-2,977.17</span></span></td>
<td><span data-ttu-id="13b90-928">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="13b90-929">Prod 1</span></span></td>
<td><span data-ttu-id="13b90-930">Producto 1</span><span class="sxs-lookup"><span data-stu-id="13b90-930">Product 1</span></span></td>
<td><span data-ttu-id="13b90-931">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-931">10001</span></span></td>
<td><span data-ttu-id="13b90-932">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-932">Electricity</span></span></td>
<td><span data-ttu-id="13b90-933">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-933">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="13b90-934">2,507.09</span></span></td>
<td><span data-ttu-id="13b90-935">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="13b90-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="13b90-936">Prod 2</span></span></td>
<td><span data-ttu-id="13b90-937">Producto 2</span><span class="sxs-lookup"><span data-stu-id="13b90-937">Product 2</span></span></td>
<td><span data-ttu-id="13b90-938">10001</span><span class="sxs-lookup"><span data-stu-id="13b90-938">10001</span></span></td>
<td><span data-ttu-id="13b90-939">Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-939">Electricity</span></span></td>
<td><span data-ttu-id="13b90-940">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-940">Variable cost</span></span></td>
<td><span data-ttu-id="13b90-941">470.08</span><span class="sxs-lookup"><span data-stu-id="13b90-941">470.08</span></span></td>
<td><span data-ttu-id="13b90-942">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="13b90-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="13b90-943">Conclusión</span><span class="sxs-lookup"><span data-stu-id="13b90-943">Conclusion</span></span>
<span data-ttu-id="13b90-944">En la contabilidad financiera, un coste de 10.000,00 para electricidad se envía a un identificador ficticio de centro de coste.</span><span class="sxs-lookup"><span data-stu-id="13b90-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="13b90-945">Por lo tanto, los contables de coste sabrán que este coste se debe asignar.</span><span class="sxs-lookup"><span data-stu-id="13b90-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="13b90-946">En contabilidad de costes, los costes fluyen en las unidades organizativas y los niveles en función de las directivas y las reglas que se aplican.</span><span class="sxs-lookup"><span data-stu-id="13b90-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="13b90-947">Cada coste se ha asociado con una base de asignación que proporciona la mejor evaluación para la asignación de costes.</span><span class="sxs-lookup"><span data-stu-id="13b90-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="13b90-948">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="13b90-949">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="13b90-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="13b90-950">Total</span><span class="sxs-lookup"><span data-stu-id="13b90-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="13b90-951">CC099</span><span class="sxs-lookup"><span data-stu-id="13b90-951">CC099</span></span></th>
<th><span data-ttu-id="13b90-952">CC001</span><span class="sxs-lookup"><span data-stu-id="13b90-952">CC001</span></span></th>
<th><span data-ttu-id="13b90-953">CC002</span><span class="sxs-lookup"><span data-stu-id="13b90-953">CC002</span></span></th>
<th><span data-ttu-id="13b90-954">CC003</span><span class="sxs-lookup"><span data-stu-id="13b90-954">CC003</span></span></th>
<th><span data-ttu-id="13b90-955">CC004</span><span class="sxs-lookup"><span data-stu-id="13b90-955">CC004</span></span></th>
<th><span data-ttu-id="13b90-956">Proy 1</span><span class="sxs-lookup"><span data-stu-id="13b90-956">Proj 1</span></span></th>
<th><span data-ttu-id="13b90-957">Proy 2</span><span class="sxs-lookup"><span data-stu-id="13b90-957">Proj 2</span></span></th>
<th><span data-ttu-id="13b90-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="13b90-958">Prod 1</span></span></th>
<th><span data-ttu-id="13b90-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="13b90-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="13b90-960">10001 Electricidad</span><span class="sxs-lookup"><span data-stu-id="13b90-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="13b90-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="13b90-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="13b90-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="13b90-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="13b90-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="13b90-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="13b90-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="13b90-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="13b90-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="13b90-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="13b90-970">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="13b90-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-971">0,00</span><span class="sxs-lookup"><span data-stu-id="13b90-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="13b90-972">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="13b90-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-973">0,00</span><span class="sxs-lookup"><span data-stu-id="13b90-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-974">0,00</span><span class="sxs-lookup"><span data-stu-id="13b90-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-975">0,00</span><span class="sxs-lookup"><span data-stu-id="13b90-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-976">0,00</span><span class="sxs-lookup"><span data-stu-id="13b90-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-977">0,00</span><span class="sxs-lookup"><span data-stu-id="13b90-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="13b90-978">776.36</span><span class="sxs-lookup"><span data-stu-id="13b90-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-979">223.64</span><span class="sxs-lookup"><span data-stu-id="13b90-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="13b90-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="13b90-981">Coste variable</span><span class="sxs-lookup"><span data-stu-id="13b90-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-982">000</span><span class="sxs-lookup"><span data-stu-id="13b90-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-983">0,00</span><span class="sxs-lookup"><span data-stu-id="13b90-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-984">0,00</span><span class="sxs-lookup"><span data-stu-id="13b90-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-985">0,00</span><span class="sxs-lookup"><span data-stu-id="13b90-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-986">0,00</span><span class="sxs-lookup"><span data-stu-id="13b90-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-987">30,00</span><span class="sxs-lookup"><span data-stu-id="13b90-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-988">10,00</span><span class="sxs-lookup"><span data-stu-id="13b90-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="13b90-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="13b90-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="13b90-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="13b90-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="13b90-992">Este tema muestra cómo un artículo de costes principales, 10001 Electricidad, fluye por los objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="13b90-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="13b90-993">Por tanto, estos gastos generales se asignan al nivel más bajo de la organización.</span><span class="sxs-lookup"><span data-stu-id="13b90-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="13b90-994">Es decir, los objetos de coste del nivel más bajo son los que soportan el coste.</span><span class="sxs-lookup"><span data-stu-id="13b90-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="13b90-995">Si necesita un flujo visual del coste entre los objetos de coste, puede usar las reglas de directivas de acumulación de costes para visualizar el flujo del coste.</span><span class="sxs-lookup"><span data-stu-id="13b90-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="13b90-996">Para obtener más información, consulte [Directiva de acumulación de costes y cálculo de costes generales](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="13b90-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]