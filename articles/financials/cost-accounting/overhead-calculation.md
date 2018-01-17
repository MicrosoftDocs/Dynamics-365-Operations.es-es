---
title: "Cálculo de costes generales"
description: "Este tema describe los procesos típicos para calcular y asignar costes generales."
author: AndersGirke
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 936e54c0ef1de449afda2392cd1fbb304eed631b
ms.contentlocale: es-es
ms.lasthandoff: 01/17/2018

---

# <a name="overhead-calculation"></a><span data-ttu-id="133ee-103">Cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="133ee-103">Overhead calculation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="133ee-104">Este tema describe los procesos típicos para calcular y asignar costes generales.</span><span class="sxs-lookup"><span data-stu-id="133ee-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="133ee-105">Definición del término</span><span class="sxs-lookup"><span data-stu-id="133ee-105">Term definition</span></span>
---------------

<span data-ttu-id="133ee-106">Los costes generales son costes que se contraen para dirigir un negocio, pero que no pueden ser atribuidos directamente a ninguna actividad empresarial, productos, o servicio específicos.</span><span class="sxs-lookup"><span data-stu-id="133ee-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="133ee-107">Los costes generales proporcionan un soporte fundamental a la generación de actividades rentables.</span><span class="sxs-lookup"><span data-stu-id="133ee-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="133ee-108">Algunos ejemplos de costes generales son:</span><span class="sxs-lookup"><span data-stu-id="133ee-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="133ee-109">Alquiler</span><span class="sxs-lookup"><span data-stu-id="133ee-109">Rent</span></span>
-   <span data-ttu-id="133ee-110">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-110">Electricity</span></span>
-   <span data-ttu-id="133ee-111">Sueldos administrativos</span><span class="sxs-lookup"><span data-stu-id="133ee-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="133ee-112">Visión general del cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="133ee-112">Overhead calculation overview</span></span>
<span data-ttu-id="133ee-113">El cálculo de costes generales ejecuta las directivas de contabilidad de costes en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="133ee-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="133ee-114">Puede calcular varias veces los costes generales del mismo período fiscal si se han cambiado las directivas de contabilidad de costes o se han detectado errores específicos.</span><span class="sxs-lookup"><span data-stu-id="133ee-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="133ee-115">Cada ejecución del cálculo de costes generales se almacena y recibe un identificador de versión único que permite comparar los cálculos de diferentes versiones.</span><span class="sxs-lookup"><span data-stu-id="133ee-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="133ee-116">Las entradas de costes que el cálculo de costes generales genera reciben una fecha de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="133ee-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="133ee-117">Esta fecha de contabilidad coincide con la fecha final del período fiscal que se usa en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="133ee-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="133ee-118">El identificador de versión único consiste en los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="133ee-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="133ee-119">Tipo de versión</span><span class="sxs-lookup"><span data-stu-id="133ee-119">Version type</span></span>
-   <span data-ttu-id="133ee-120">Fecha y hora</span><span class="sxs-lookup"><span data-stu-id="133ee-120">Date and time</span></span>
-   <span data-ttu-id="133ee-121">Libro mayor de contabilidad de costes</span><span class="sxs-lookup"><span data-stu-id="133ee-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="133ee-122">Ejercicio</span><span class="sxs-lookup"><span data-stu-id="133ee-122">Fiscal year</span></span>
-   <span data-ttu-id="133ee-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="133ee-123">Fiscal period</span></span>

<span data-ttu-id="133ee-124">El cálculo de costes generales se ejecuta independientemente de la versión.</span><span class="sxs-lookup"><span data-stu-id="133ee-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="133ee-125">Por lo tanto, puede calcular la versión de presupuesto antes que la versión real.</span><span class="sxs-lookup"><span data-stu-id="133ee-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="133ee-126">El cálculo de costes generales consta de cuatro pasos, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="133ee-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="133ee-127">En cada paso, se crea una cabecera de diario que tiene entradas del diario.</span><span class="sxs-lookup"><span data-stu-id="133ee-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="133ee-128">Esta cabecera de diario guarda los datos de entrada para cada paso de cálculo.</span><span class="sxs-lookup"><span data-stu-id="133ee-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="133ee-129">Las directivas y las reglas se aplican a cada línea de diario, y las entradas de coste se generan como resultado.</span><span class="sxs-lookup"><span data-stu-id="133ee-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="133ee-130">Por tanto, siempre se tiene rastreabilidad completa.</span><span class="sxs-lookup"><span data-stu-id="133ee-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="133ee-131">[![Cálculo de costes generales](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="133ee-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="133ee-132">Calcular y asignar costes generales de electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="133ee-133">En la contabilidad financiera, algunos costes, como la electricidad, se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="133ee-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="133ee-134">Por lo tanto, no se proporciona una visión de gestión detallada para la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="133ee-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="133ee-135">En contabilidad de costes, para proporcionar información de gestión correcta en todas las unidades y niveles organizativos, los costes deben fluir por las unidades organizativas.</span><span class="sxs-lookup"><span data-stu-id="133ee-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="133ee-136">Este flujo se debe basar en cualquier registro preciso de consumo o en una evaluación justa.</span><span class="sxs-lookup"><span data-stu-id="133ee-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="133ee-137">En la contabilidad general, un coste de la electricidad se puede registrar como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="133ee-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="133ee-138">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="133ee-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="133ee-139">Centro de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="133ee-140">Cuenta principal</span><span class="sxs-lookup"><span data-stu-id="133ee-140">Main account</span></span></th>
<th><span data-ttu-id="133ee-141">Importe en la divisa de contabilidad</span><span class="sxs-lookup"><span data-stu-id="133ee-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-142">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="133ee-143">CC099</span><span class="sxs-lookup"><span data-stu-id="133ee-143">CC099</span></span></td>
<td><span data-ttu-id="133ee-144">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="133ee-144">Default cost center</span></span></td>
<td><span data-ttu-id="133ee-145">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-145">10001</span></span></td>
<td><span data-ttu-id="133ee-146">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-146">Electricity</span></span></td>
<td><span data-ttu-id="133ee-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="133ee-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="133ee-148">Paso 1: Procese el cálculo del comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="133ee-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="133ee-149">De forma predeterminada, cuando las entradas de coste se importan de los datos de origen, reciben la clasificación de comportamiento del coste **Sin ordenar** en la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="133ee-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="133ee-150">Aplicando reglas de directivas de comportamiento de coste, puede reclasificar entradas de coste como **Coste fijo** o **Coste variable**.</span><span class="sxs-lookup"><span data-stu-id="133ee-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="133ee-151">Defina la regla de comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="133ee-151">Define the cost behavior rule</span></span>

<span data-ttu-id="133ee-152">En algunos casos, parte del coste es una cuota fija, y el coste pendiente se basa en el consumo.</span><span class="sxs-lookup"><span data-stu-id="133ee-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="133ee-153">Las facturas de electricidad coinciden a menudo con esta definición.</span><span class="sxs-lookup"><span data-stu-id="133ee-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="133ee-154">Tras pagar una cuota fija específica, paga el consumo por kilovatio-hora (Kwh).</span><span class="sxs-lookup"><span data-stu-id="133ee-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="133ee-155">Por ejemplo, si la cuota de coste fijo es de 1.000,00, la regla de comportamiento del coste se define como sigue:</span><span class="sxs-lookup"><span data-stu-id="133ee-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="133ee-156">Importe fijo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="133ee-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="133ee-157">0 &lt;= 1.000,00 = Fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="133ee-158">1.000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="133ee-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="133ee-159">Diario</span><span class="sxs-lookup"><span data-stu-id="133ee-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="133ee-160">Diario</span><span class="sxs-lookup"><span data-stu-id="133ee-160">Journal</span></span></th>
<th><span data-ttu-id="133ee-161">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="133ee-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="133ee-162">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="133ee-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="133ee-163">Versión</span><span class="sxs-lookup"><span data-stu-id="133ee-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-164">00001</span><span class="sxs-lookup"><span data-stu-id="133ee-164">00001</span></span></td>
<td><span data-ttu-id="133ee-165">Diario de cálculo de comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="133ee-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="133ee-166">Fiscal</span><span class="sxs-lookup"><span data-stu-id="133ee-166">Fiscal</span></span></td>
<td><span data-ttu-id="133ee-167">2017</span><span class="sxs-lookup"><span data-stu-id="133ee-167">2017</span></span></td>
<td><span data-ttu-id="133ee-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="133ee-168">Period 1</span></span></td>
<td><span data-ttu-id="133ee-169">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="133ee-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="133ee-170">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="133ee-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="133ee-171">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="133ee-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="133ee-172">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="133ee-173">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-173">Cost element</span></span></th>
<th><span data-ttu-id="133ee-174">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="133ee-174">Cost behavior</span></span></th>
<th><span data-ttu-id="133ee-175">Importe</span><span class="sxs-lookup"><span data-stu-id="133ee-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-176">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="133ee-177">CC099</span><span class="sxs-lookup"><span data-stu-id="133ee-177">CC099</span></span></td>
<td><span data-ttu-id="133ee-178">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="133ee-178">Default cost center</span></span></td>
<td><span data-ttu-id="133ee-179">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-179">10001</span></span></td>
<td><span data-ttu-id="133ee-180">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-180">Electricity</span></span></td>
<td><span data-ttu-id="133ee-181">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="133ee-181">Unclassified</span></span></td>
<td><span data-ttu-id="133ee-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="133ee-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="133ee-183">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="133ee-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="133ee-184">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="133ee-185">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-185">Cost element</span></span></th>
<th><span data-ttu-id="133ee-186">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="133ee-186">Cost behavior</span></span></th>
<th><span data-ttu-id="133ee-187">Importe</span><span class="sxs-lookup"><span data-stu-id="133ee-187">Amount</span></span></th>
<th><span data-ttu-id="133ee-188">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="133ee-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-189">CC099</span><span class="sxs-lookup"><span data-stu-id="133ee-189">CC099</span></span></td>
<td><span data-ttu-id="133ee-190">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="133ee-190">Default cost center</span></span></td>
<td><span data-ttu-id="133ee-191">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-191">10001</span></span></td>
<td><span data-ttu-id="133ee-192">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-192">Electricity</span></span></td>
<td><span data-ttu-id="133ee-193">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="133ee-193">Unclassified</span></span></td>
<td><span data-ttu-id="133ee-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="133ee-194">10,000.00</span></span></td>
<td><span data-ttu-id="133ee-195">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-196">CC099</span><span class="sxs-lookup"><span data-stu-id="133ee-196">CC099</span></span></td>
<td><span data-ttu-id="133ee-197">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="133ee-197">Default cost center</span></span></td>
<td><span data-ttu-id="133ee-198">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-198">10001</span></span></td>
<td><span data-ttu-id="133ee-199">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-199">Electricity</span></span></td>
<td><span data-ttu-id="133ee-200">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="133ee-200">Unclassified</span></span></td>
<td><span data-ttu-id="133ee-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="133ee-201">-10,000.00</span></span></td>
<td><span data-ttu-id="133ee-202">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-203">CC099</span><span class="sxs-lookup"><span data-stu-id="133ee-203">CC099</span></span></td>
<td><span data-ttu-id="133ee-204">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="133ee-204">Default cost center</span></span></td>
<td><span data-ttu-id="133ee-205">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-205">10001</span></span></td>
<td><span data-ttu-id="133ee-206">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-206">Electricity</span></span></td>
<td><span data-ttu-id="133ee-207">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-207">Fixed cost</span></span></td>
<td><span data-ttu-id="133ee-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="133ee-208">1,000.00</span></span></td>
<td><span data-ttu-id="133ee-209">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-210">CC099</span><span class="sxs-lookup"><span data-stu-id="133ee-210">CC099</span></span></td>
<td><span data-ttu-id="133ee-211">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="133ee-211">Default cost center</span></span></td>
<td><span data-ttu-id="133ee-212">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-212">10001</span></span></td>
<td><span data-ttu-id="133ee-213">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-213">Electricity</span></span></td>
<td><span data-ttu-id="133ee-214">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-214">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="133ee-215">9,000.00</span></span></td>
<td><span data-ttu-id="133ee-216">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="133ee-217">Para obtener información detallada sobre el comportamiento del coste, consulte Directiva de comportamiento de costes.</span><span class="sxs-lookup"><span data-stu-id="133ee-217">For detailed information about cost behavior, see Cost behavior policy.</span></span> <span data-ttu-id="133ee-218">(Tenga en cuenta que este tema no se ha completado aún, pero pronto se abordará).</span><span class="sxs-lookup"><span data-stu-id="133ee-218">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="133ee-219">Paso 2: Procese el cálculo de distribución de costes</span><span class="sxs-lookup"><span data-stu-id="133ee-219">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="133ee-220">La distribución de costes se usa para redistribuir costes desde un objeto de coste a uno o más objetos de coste aplicando una base relevante de la asignación.</span><span class="sxs-lookup"><span data-stu-id="133ee-220">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="133ee-221">La distribución de costes y la asignación de costes difieren en que la distribución de costes siempre se produce en el nivel de elemento de costes principal del coste original.</span><span class="sxs-lookup"><span data-stu-id="133ee-221">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="133ee-222">Defina la regla de distribución del coste</span><span class="sxs-lookup"><span data-stu-id="133ee-222">Define the cost distribution rule</span></span>

<span data-ttu-id="133ee-223">En la contabilidad financiera, los costes de electricidad se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="133ee-223">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="133ee-224">En contabilidad de costes, este método no es suficientemente detallado.</span><span class="sxs-lookup"><span data-stu-id="133ee-224">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="133ee-225">El coste variable debe distribuirse a los objetos individuales de coste aplicando una base justa.</span><span class="sxs-lookup"><span data-stu-id="133ee-225">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="133ee-226">La base de asignación más lógica es el consumo de electricidad (Kwh).</span><span class="sxs-lookup"><span data-stu-id="133ee-226">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="133ee-227">Se crea un miembro de dimensión estadística que se denomina Electricity, y se registra el consumo de electricidad.</span><span class="sxs-lookup"><span data-stu-id="133ee-227">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="133ee-228">De forma predeterminada, todos los miembros de dimensión estadísticos estarán disponibles como bases de asignación.</span><span class="sxs-lookup"><span data-stu-id="133ee-228">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="133ee-229">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-229">Cost object</span></span></th>
<th><span data-ttu-id="133ee-230">Kwh</span><span class="sxs-lookup"><span data-stu-id="133ee-230">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-231">CC001</span><span class="sxs-lookup"><span data-stu-id="133ee-231">CC001</span></span></td>
<td><span data-ttu-id="133ee-232">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="133ee-232">HR</span></span></td>
<td><span data-ttu-id="133ee-233">1.000</span><span class="sxs-lookup"><span data-stu-id="133ee-233">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-234">CC002</span><span class="sxs-lookup"><span data-stu-id="133ee-234">CC002</span></span></td>
<td><span data-ttu-id="133ee-235">Finanzas</span><span class="sxs-lookup"><span data-stu-id="133ee-235">Finance</span></span></td>
<td><span data-ttu-id="133ee-236">6.000</span><span class="sxs-lookup"><span data-stu-id="133ee-236">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-237">CC003</span><span class="sxs-lookup"><span data-stu-id="133ee-237">CC003</span></span></td>
<td><span data-ttu-id="133ee-238">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="133ee-238">Assembly</span></span></td>
<td><span data-ttu-id="133ee-239">0</span><span class="sxs-lookup"><span data-stu-id="133ee-239">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="133ee-240">La tabla siguiente muestra el resultado cuando se aplica el consumo de electricidad como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="133ee-240">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="133ee-241">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-241">Cost object</span></span></th>
<th><span data-ttu-id="133ee-242">Magnitud</span><span class="sxs-lookup"><span data-stu-id="133ee-242">Magnitude</span></span></th>
<th><span data-ttu-id="133ee-243">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="133ee-243">Allocation factor</span></span></th>
<th><span data-ttu-id="133ee-244">Importe</span><span class="sxs-lookup"><span data-stu-id="133ee-244">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-245">CC001</span><span class="sxs-lookup"><span data-stu-id="133ee-245">CC001</span></span></td>
<td><span data-ttu-id="133ee-246">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="133ee-246">HR</span></span></td>
<td><span data-ttu-id="133ee-247">1.000</span><span class="sxs-lookup"><span data-stu-id="133ee-247">1,000</span></span></td>
<td><span data-ttu-id="133ee-248">(1.000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="133ee-248">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="133ee-249">1,285.71</span><span class="sxs-lookup"><span data-stu-id="133ee-249">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-250">CC002</span><span class="sxs-lookup"><span data-stu-id="133ee-250">CC002</span></span></td>
<td><span data-ttu-id="133ee-251">Finanzas</span><span class="sxs-lookup"><span data-stu-id="133ee-251">Finance</span></span></td>
<td><span data-ttu-id="133ee-252">6.000</span><span class="sxs-lookup"><span data-stu-id="133ee-252">6,000</span></span></td>
<td><span data-ttu-id="133ee-253">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="133ee-253">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="133ee-254">7,714.29</span><span class="sxs-lookup"><span data-stu-id="133ee-254">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-255">CC003</span><span class="sxs-lookup"><span data-stu-id="133ee-255">CC003</span></span></td>
<td><span data-ttu-id="133ee-256">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="133ee-256">Assembly</span></span></td>
<td><span data-ttu-id="133ee-257">0</span><span class="sxs-lookup"><span data-stu-id="133ee-257">0</span></span></td>
<td><span data-ttu-id="133ee-258">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="133ee-258">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="133ee-259">0,00</span><span class="sxs-lookup"><span data-stu-id="133ee-259">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="133ee-260">El coste fijo debe distribuirse uniformemente a los objetos individuales de costes que han consumido electricidad.</span><span class="sxs-lookup"><span data-stu-id="133ee-260">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="133ee-261">Puede obtener este resultado usando el miembro de dimensión estadístico de electricidad en una base de asignación de la fórmula: (Electricidad &gt; 0,00) La tabla siguiente muestra el resultado cuando el consumo de electricidad se aplica como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="133ee-261">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="133ee-262">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-262">Cost object</span></span></th>
<th><span data-ttu-id="133ee-263">Fórmula</span><span class="sxs-lookup"><span data-stu-id="133ee-263">Formula</span></span></th>
<th><span data-ttu-id="133ee-264">Magnitud</span><span class="sxs-lookup"><span data-stu-id="133ee-264">Magnitude</span></span></th>
<th><span data-ttu-id="133ee-265">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="133ee-265">Allocation factor</span></span></th>
<th><span data-ttu-id="133ee-266">Importe</span><span class="sxs-lookup"><span data-stu-id="133ee-266">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-267">CC001</span><span class="sxs-lookup"><span data-stu-id="133ee-267">CC001</span></span></td>
<td><span data-ttu-id="133ee-268">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="133ee-268">HR</span></span></td>
<td><span data-ttu-id="133ee-269">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="133ee-269">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="133ee-270">1</span><span class="sxs-lookup"><span data-stu-id="133ee-270">1</span></span></td>
<td><span data-ttu-id="133ee-271">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="133ee-271">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="133ee-272">500,00</span><span class="sxs-lookup"><span data-stu-id="133ee-272">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-273">CC002</span><span class="sxs-lookup"><span data-stu-id="133ee-273">CC002</span></span></td>
<td><span data-ttu-id="133ee-274">Finanzas</span><span class="sxs-lookup"><span data-stu-id="133ee-274">Finance</span></span></td>
<td><span data-ttu-id="133ee-275">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="133ee-275">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="133ee-276">1</span><span class="sxs-lookup"><span data-stu-id="133ee-276">1</span></span></td>
<td><span data-ttu-id="133ee-277">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="133ee-277">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="133ee-278">500,00</span><span class="sxs-lookup"><span data-stu-id="133ee-278">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-279">CC003</span><span class="sxs-lookup"><span data-stu-id="133ee-279">CC003</span></span></td>
<td><span data-ttu-id="133ee-280">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="133ee-280">Assembly</span></span></td>
<td><span data-ttu-id="133ee-281">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="133ee-281">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="133ee-282">0</span><span class="sxs-lookup"><span data-stu-id="133ee-282">0</span></span></td>
<td><span data-ttu-id="133ee-283">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="133ee-283">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="133ee-284">0,00</span><span class="sxs-lookup"><span data-stu-id="133ee-284">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="133ee-285">Diario</span><span class="sxs-lookup"><span data-stu-id="133ee-285">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="133ee-286">Diario</span><span class="sxs-lookup"><span data-stu-id="133ee-286">Journal</span></span></th>
<th><span data-ttu-id="133ee-287">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="133ee-287">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="133ee-288">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="133ee-288">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="133ee-289">Versión</span><span class="sxs-lookup"><span data-stu-id="133ee-289">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-290">00002</span><span class="sxs-lookup"><span data-stu-id="133ee-290">00002</span></span></td>
<td><span data-ttu-id="133ee-291">Diario de cálculo de la distribución de costes</span><span class="sxs-lookup"><span data-stu-id="133ee-291">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="133ee-292">Fiscal</span><span class="sxs-lookup"><span data-stu-id="133ee-292">Fiscal</span></span></td>
<td><span data-ttu-id="133ee-293">2017</span><span class="sxs-lookup"><span data-stu-id="133ee-293">2017</span></span></td>
<td><span data-ttu-id="133ee-294">Período 1</span><span class="sxs-lookup"><span data-stu-id="133ee-294">Period 1</span></span></td>
<td><span data-ttu-id="133ee-295">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="133ee-295">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="133ee-296">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="133ee-296">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="133ee-297">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="133ee-297">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="133ee-298">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-298">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="133ee-299">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-299">Cost element</span></span></th>
<th><span data-ttu-id="133ee-300">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="133ee-300">Cost behavior</span></span></th>
<th><span data-ttu-id="133ee-301">Importe</span><span class="sxs-lookup"><span data-stu-id="133ee-301">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-302">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-302">January 31, 2017</span></span></td>
<td><span data-ttu-id="133ee-303">CC099</span><span class="sxs-lookup"><span data-stu-id="133ee-303">CC099</span></span></td>
<td><span data-ttu-id="133ee-304">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="133ee-304">Default cost center</span></span></td>
<td><span data-ttu-id="133ee-305">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-305">10001</span></span></td>
<td><span data-ttu-id="133ee-306">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-306">Electricity</span></span></td>
<td><span data-ttu-id="133ee-307">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-307">Fixed cost</span></span></td>
<td><span data-ttu-id="133ee-308">1.000,00</span><span class="sxs-lookup"><span data-stu-id="133ee-308">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-309">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-309">January 31, 2017</span></span></td>
<td><span data-ttu-id="133ee-310">CC099</span><span class="sxs-lookup"><span data-stu-id="133ee-310">CC099</span></span></td>
<td><span data-ttu-id="133ee-311">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="133ee-311">Default cost center</span></span></td>
<td><span data-ttu-id="133ee-312">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-312">10001</span></span></td>
<td><span data-ttu-id="133ee-313">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-313">Electricity</span></span></td>
<td><span data-ttu-id="133ee-314">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-314">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-315">9.000,00</span><span class="sxs-lookup"><span data-stu-id="133ee-315">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="133ee-316">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="133ee-316">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="133ee-317">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-317">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="133ee-318">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-318">Cost element</span></span></th>
<th><span data-ttu-id="133ee-319">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="133ee-319">Cost behavior</span></span></th>
<th><span data-ttu-id="133ee-320">Importe</span><span class="sxs-lookup"><span data-stu-id="133ee-320">Amount</span></span></th>
<th><span data-ttu-id="133ee-321">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="133ee-321">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-322">CC099</span><span class="sxs-lookup"><span data-stu-id="133ee-322">CC099</span></span></td>
<td><span data-ttu-id="133ee-323">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="133ee-323">Default cost center</span></span></td>
<td><span data-ttu-id="133ee-324">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-324">10001</span></span></td>
<td><span data-ttu-id="133ee-325">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-325">Electricity</span></span></td>
<td><span data-ttu-id="133ee-326">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-326">Fixed cost</span></span></td>
<td><span data-ttu-id="133ee-327">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="133ee-327">-1,000.00</span></span></td>
<td><span data-ttu-id="133ee-328">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-328">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-329">CC001</span><span class="sxs-lookup"><span data-stu-id="133ee-329">CC001</span></span></td>
<td><span data-ttu-id="133ee-330">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="133ee-330">HR</span></span></td>
<td><span data-ttu-id="133ee-331">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-331">10001</span></span></td>
<td><span data-ttu-id="133ee-332">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-332">Electricity</span></span></td>
<td><span data-ttu-id="133ee-333">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-333">Fixed cost</span></span></td>
<td><span data-ttu-id="133ee-334">500,00</span><span class="sxs-lookup"><span data-stu-id="133ee-334">500.00</span></span></td>
<td><span data-ttu-id="133ee-335">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-335">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-336">CC002</span><span class="sxs-lookup"><span data-stu-id="133ee-336">CC002</span></span></td>
<td><span data-ttu-id="133ee-337">Finanzas</span><span class="sxs-lookup"><span data-stu-id="133ee-337">Finance</span></span></td>
<td><span data-ttu-id="133ee-338">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-338">10001</span></span></td>
<td><span data-ttu-id="133ee-339">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-339">Electricity</span></span></td>
<td><span data-ttu-id="133ee-340">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-340">Fixed cost</span></span></td>
<td><span data-ttu-id="133ee-341">500,00</span><span class="sxs-lookup"><span data-stu-id="133ee-341">500.00</span></span></td>
<td><span data-ttu-id="133ee-342">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-342">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-343">CC099</span><span class="sxs-lookup"><span data-stu-id="133ee-343">CC099</span></span></td>
<td><span data-ttu-id="133ee-344">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="133ee-344">Default cost center</span></span></td>
<td><span data-ttu-id="133ee-345">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-345">10001</span></span></td>
<td><span data-ttu-id="133ee-346">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-346">Electricity</span></span></td>
<td><span data-ttu-id="133ee-347">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-347">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-348">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="133ee-348">-9,000.00</span></span></td>
<td><span data-ttu-id="133ee-349">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-349">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-350">CC001</span><span class="sxs-lookup"><span data-stu-id="133ee-350">CC001</span></span></td>
<td><span data-ttu-id="133ee-351">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="133ee-351">HR</span></span></td>
<td><span data-ttu-id="133ee-352">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-352">10001</span></span></td>
<td><span data-ttu-id="133ee-353">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-353">Electricity</span></span></td>
<td><span data-ttu-id="133ee-354">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-354">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-355">1,285.71</span><span class="sxs-lookup"><span data-stu-id="133ee-355">1,285.71</span></span></td>
<td><span data-ttu-id="133ee-356">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-356">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-357">CC002</span><span class="sxs-lookup"><span data-stu-id="133ee-357">CC002</span></span></td>
<td><span data-ttu-id="133ee-358">Finanzas</span><span class="sxs-lookup"><span data-stu-id="133ee-358">Finance</span></span></td>
<td><span data-ttu-id="133ee-359">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-359">10001</span></span></td>
<td><span data-ttu-id="133ee-360">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-360">Electricity</span></span></td>
<td><span data-ttu-id="133ee-361">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-361">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-362">7,714.29</span><span class="sxs-lookup"><span data-stu-id="133ee-362">7,714.29</span></span></td>
<td><span data-ttu-id="133ee-363">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-363">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="133ee-364">Para obtener información detallada sobre la distribución de costes y las bases de asignación, consulte la directiva de distribución de costes y las bases de asignación.</span><span class="sxs-lookup"><span data-stu-id="133ee-364">For detailed information about cost distribution and allocation bases, see Cost distribution policy and Allocation bases.</span></span> <span data-ttu-id="133ee-365">(Tenga en cuenta que este tema no se ha completado aún, pero pronto se abordará).</span><span class="sxs-lookup"><span data-stu-id="133ee-365">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="133ee-366">Paso 3: Procese el cálculo de las tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="133ee-366">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="133ee-367">La tasa de costes generales se usa para cargar uno o varios objetos de coste específicos.</span><span class="sxs-lookup"><span data-stu-id="133ee-367">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="133ee-368">El cargo se basa en un índice de coste predeterminado y la magnitud de la base de asignación asignada.</span><span class="sxs-lookup"><span data-stu-id="133ee-368">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="133ee-369">Defina la tasa de costes generales</span><span class="sxs-lookup"><span data-stu-id="133ee-369">Define the overhead rate</span></span>

<span data-ttu-id="133ee-370">El objeto de coste CC001 HR contribuye a un conjunto de proyectos internos.</span><span class="sxs-lookup"><span data-stu-id="133ee-370">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="133ee-371">Se crea un miembro de dimensión estadística que se denomina proyectos HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="133ee-371">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="133ee-372">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-372">Cost object</span></span></th>
<th><span data-ttu-id="133ee-373">Horas</span><span class="sxs-lookup"><span data-stu-id="133ee-373">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-374">Proy 1</span><span class="sxs-lookup"><span data-stu-id="133ee-374">Proj 1</span></span></td>
<td><span data-ttu-id="133ee-375">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="133ee-375">Project 1</span></span></td>
<td><span data-ttu-id="133ee-376">3</span><span class="sxs-lookup"><span data-stu-id="133ee-376">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-377">Proy 2</span><span class="sxs-lookup"><span data-stu-id="133ee-377">Proj 2</span></span></td>
<td><span data-ttu-id="133ee-378">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="133ee-378">Project 2</span></span></td>
<td><span data-ttu-id="133ee-379">1</span><span class="sxs-lookup"><span data-stu-id="133ee-379">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="133ee-380">Una tasa de coste predeterminada para la contribución de los proyectos de coste se ha definido.</span><span class="sxs-lookup"><span data-stu-id="133ee-380">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="133ee-381">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-381">Cost object</span></span></th>
<th><span data-ttu-id="133ee-382">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-382">Cost element</span></span></th>
<th><span data-ttu-id="133ee-383">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="133ee-383">Cost behavior</span></span></th>
<th><span data-ttu-id="133ee-384">Unidades</span><span class="sxs-lookup"><span data-stu-id="133ee-384">Units</span></span></th>
<th><span data-ttu-id="133ee-385">Índice</span><span class="sxs-lookup"><span data-stu-id="133ee-385">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-386">CC001</span><span class="sxs-lookup"><span data-stu-id="133ee-386">CC001</span></span></td>
<td><span data-ttu-id="133ee-387">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="133ee-387">HR</span></span></td>
<td><span data-ttu-id="133ee-388">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-388">10001</span></span></td>
<td><span data-ttu-id="133ee-389">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-389">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-390">1</span><span class="sxs-lookup"><span data-stu-id="133ee-390">1</span></span></td>
<td><span data-ttu-id="133ee-391">10</span><span class="sxs-lookup"><span data-stu-id="133ee-391">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="133ee-392">La tabla siguiente muestra el resultado cuando los proyectos HR se aplican como base de la asignación.</span><span class="sxs-lookup"><span data-stu-id="133ee-392">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="133ee-393">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-393">Cost object</span></span></th>
<th><span data-ttu-id="133ee-394">Magnitud</span><span class="sxs-lookup"><span data-stu-id="133ee-394">Magnitude</span></span></th>
<th><span data-ttu-id="133ee-395">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-395">Cost element</span></span></th>
<th><span data-ttu-id="133ee-396">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="133ee-396">Allocation factor</span></span></th>
<th><span data-ttu-id="133ee-397">Importe</span><span class="sxs-lookup"><span data-stu-id="133ee-397">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-398">Proy 1</span><span class="sxs-lookup"><span data-stu-id="133ee-398">Proj 1</span></span></td>
<td><span data-ttu-id="133ee-399">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="133ee-399">Project 1</span></span></td>
<td><span data-ttu-id="133ee-400">3</span><span class="sxs-lookup"><span data-stu-id="133ee-400">3</span></span></td>
<td><span data-ttu-id="133ee-401">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-401">10001</span></span></td>
<td><span data-ttu-id="133ee-402">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="133ee-402">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="133ee-403">30,00</span><span class="sxs-lookup"><span data-stu-id="133ee-403">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-404">Proy 2</span><span class="sxs-lookup"><span data-stu-id="133ee-404">Proj 2</span></span></td>
<td><span data-ttu-id="133ee-405">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="133ee-405">Project 2</span></span></td>
<td><span data-ttu-id="133ee-406">1</span><span class="sxs-lookup"><span data-stu-id="133ee-406">1</span></span></td>
<td><span data-ttu-id="133ee-407">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-407">10001</span></span></td>
<td><span data-ttu-id="133ee-408">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="133ee-408">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="133ee-409">10,00</span><span class="sxs-lookup"><span data-stu-id="133ee-409">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="133ee-410">Diario</span><span class="sxs-lookup"><span data-stu-id="133ee-410">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="133ee-411">Diario</span><span class="sxs-lookup"><span data-stu-id="133ee-411">Journal</span></span></th>
<th><span data-ttu-id="133ee-412">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="133ee-412">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="133ee-413">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="133ee-413">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="133ee-414">Versión</span><span class="sxs-lookup"><span data-stu-id="133ee-414">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-415">00003</span><span class="sxs-lookup"><span data-stu-id="133ee-415">00003</span></span></td>
<td><span data-ttu-id="133ee-416">Diario de cálculo de tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="133ee-416">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="133ee-417">Fiscal</span><span class="sxs-lookup"><span data-stu-id="133ee-417">Fiscal</span></span></td>
<td><span data-ttu-id="133ee-418">2017</span><span class="sxs-lookup"><span data-stu-id="133ee-418">2017</span></span></td>
<td><span data-ttu-id="133ee-419">Período 1</span><span class="sxs-lookup"><span data-stu-id="133ee-419">Period 1</span></span></td>
<td><span data-ttu-id="133ee-420">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="133ee-420">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="133ee-421">Entradas de diario (entradas de diario para cálculo de tasas de costes generales)</span><span class="sxs-lookup"><span data-stu-id="133ee-421">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="133ee-422">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="133ee-422">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="133ee-423">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-423">Cost object</span></span></th>
<th><span data-ttu-id="133ee-424">Magnitud</span><span class="sxs-lookup"><span data-stu-id="133ee-424">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-425">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-425">January 31, 2017</span></span></td>
<td><span data-ttu-id="133ee-426">Proy 1</span><span class="sxs-lookup"><span data-stu-id="133ee-426">Proj 1</span></span></td>
<td><span data-ttu-id="133ee-427">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="133ee-427">Internal Proj 1</span></span></td>
<td><span data-ttu-id="133ee-428">3,00</span><span class="sxs-lookup"><span data-stu-id="133ee-428">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-429">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-429">January 31, 2017</span></span></td>
<td><span data-ttu-id="133ee-430">Proy 2</span><span class="sxs-lookup"><span data-stu-id="133ee-430">Proj 2</span></span></td>
<td><span data-ttu-id="133ee-431">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="133ee-431">Internal Proj 2</span></span></td>
<td><span data-ttu-id="133ee-432">1,00</span><span class="sxs-lookup"><span data-stu-id="133ee-432">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="133ee-433">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="133ee-433">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="133ee-434">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-434">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="133ee-435">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-435">Cost element</span></span></th>
<th><span data-ttu-id="133ee-436">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="133ee-436">Cost behavior</span></span></th>
<th><span data-ttu-id="133ee-437">Importe</span><span class="sxs-lookup"><span data-stu-id="133ee-437">Amount</span></span></th>
<th><span data-ttu-id="133ee-438">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="133ee-438">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-439">CC0001</span><span class="sxs-lookup"><span data-stu-id="133ee-439">CC0001</span></span></td>
<td><span data-ttu-id="133ee-440">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="133ee-440">HR</span></span></td>
<td><span data-ttu-id="133ee-441">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-441">10001</span></span></td>
<td><span data-ttu-id="133ee-442">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-442">Electricity</span></span></td>
<td><span data-ttu-id="133ee-443">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-443">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-444">-30,00</span><span class="sxs-lookup"><span data-stu-id="133ee-444">-30.00</span></span></td>
<td><span data-ttu-id="133ee-445">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-445">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-446">Proy 1</span><span class="sxs-lookup"><span data-stu-id="133ee-446">Proj 1</span></span></td>
<td><span data-ttu-id="133ee-447">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="133ee-447">Internal Proj 1</span></span></td>
<td><span data-ttu-id="133ee-448">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-448">10001</span></span></td>
<td><span data-ttu-id="133ee-449">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-449">Electricity</span></span></td>
<td><span data-ttu-id="133ee-450">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-450">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-451">30,00</span><span class="sxs-lookup"><span data-stu-id="133ee-451">30.00</span></span></td>
<td><span data-ttu-id="133ee-452">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-452">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-453">CC001</span><span class="sxs-lookup"><span data-stu-id="133ee-453">CC001</span></span></td>
<td><span data-ttu-id="133ee-454">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="133ee-454">HR</span></span></td>
<td><span data-ttu-id="133ee-455">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-455">10001</span></span></td>
<td><span data-ttu-id="133ee-456">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-456">Electricity</span></span></td>
<td><span data-ttu-id="133ee-457">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-457">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-458">-10,00</span><span class="sxs-lookup"><span data-stu-id="133ee-458">-10.00</span></span></td>
<td><span data-ttu-id="133ee-459">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-459">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-460">Proy 2</span><span class="sxs-lookup"><span data-stu-id="133ee-460">Proj 2</span></span></td>
<td><span data-ttu-id="133ee-461">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="133ee-461">Internal Proj 2</span></span></td>
<td><span data-ttu-id="133ee-462">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-462">10001</span></span></td>
<td><span data-ttu-id="133ee-463">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-463">Electricity</span></span></td>
<td><span data-ttu-id="133ee-464">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-464">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-465">10,00</span><span class="sxs-lookup"><span data-stu-id="133ee-465">10.00</span></span></td>
<td><span data-ttu-id="133ee-466">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-466">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="133ee-467">Para obtener información detallada acerca de la directiva de tasa de costes generales, consulte la directiva de tasas de costes generales y las bases de asignación.</span><span class="sxs-lookup"><span data-stu-id="133ee-467">For detailed information about overhead rate policy, see Overhead rate policy and Allocation bases.</span></span> <span data-ttu-id="133ee-468">(Tenga en cuenta que este tema no se ha completado aún, pero pronto se abordará).</span><span class="sxs-lookup"><span data-stu-id="133ee-468">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="133ee-469">Paso 4: Procese el cálculo de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="133ee-469">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="133ee-470">La asignación es utilizada para asignar el saldo de un objeto de coste a otros objetos de coste aplicando una base de asignación.</span><span class="sxs-lookup"><span data-stu-id="133ee-470">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="133ee-471">Finance and Operations admite el método de asignación recíproco.</span><span class="sxs-lookup"><span data-stu-id="133ee-471">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="133ee-472">En el método de asignación recíproco, se reconocen completamente los servicios mutuos que los objetos de coste auxiliar intercambian.</span><span class="sxs-lookup"><span data-stu-id="133ee-472">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="133ee-473">El sistema determina automáticamente el orden correcto para realizar las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="133ee-473">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="133ee-474">El saldo de un objeto de coste se asigna según una única base de asignación.</span><span class="sxs-lookup"><span data-stu-id="133ee-474">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="133ee-475">Las asignaciones entre dimensiones de objetos de coste y sus miembros respectivos se admiten.</span><span class="sxs-lookup"><span data-stu-id="133ee-475">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="133ee-476">El orden de asignación se controla por unidad de control de costes.</span><span class="sxs-lookup"><span data-stu-id="133ee-476">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="133ee-477">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="133ee-477">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="133ee-478">Defina la asignación de costes</span><span class="sxs-lookup"><span data-stu-id="133ee-478">Define the cost allocation</span></span>

<span data-ttu-id="133ee-479">A continuación se indica un ejemplo sencillo que explica cómo puede realizar el seguimiento del flujo de coste.</span><span class="sxs-lookup"><span data-stu-id="133ee-479">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="133ee-480">El objeto de coste CC001 HR contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="133ee-480">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="133ee-481">Se crea un miembro de dimensión estadística que se denomina servicios HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="133ee-481">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="133ee-482">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-482">Cost object</span></span></th>
<th><span data-ttu-id="133ee-483">Servicios HR</span><span class="sxs-lookup"><span data-stu-id="133ee-483">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-484">CC002</span><span class="sxs-lookup"><span data-stu-id="133ee-484">CC002</span></span></td>
<td><span data-ttu-id="133ee-485">Finanzas</span><span class="sxs-lookup"><span data-stu-id="133ee-485">Finance</span></span></td>
<td><span data-ttu-id="133ee-486">35</span><span class="sxs-lookup"><span data-stu-id="133ee-486">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-487">CC003</span><span class="sxs-lookup"><span data-stu-id="133ee-487">CC003</span></span></td>
<td><span data-ttu-id="133ee-488">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="133ee-488">Assembly</span></span></td>
<td><span data-ttu-id="133ee-489">55</span><span class="sxs-lookup"><span data-stu-id="133ee-489">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-490">CC004</span><span class="sxs-lookup"><span data-stu-id="133ee-490">CC004</span></span></td>
<td><span data-ttu-id="133ee-491">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="133ee-491">Packaging</span></span></td>
<td><span data-ttu-id="133ee-492">10</span><span class="sxs-lookup"><span data-stu-id="133ee-492">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="133ee-493">El objeto de coste CC002 Finanzas contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="133ee-493">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="133ee-494">Se crea un miembro de dimensión estadística que se denomina Finanzas para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="133ee-494">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="133ee-495">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-495">Cost object</span></span></th>
<th><span data-ttu-id="133ee-496">Servicios financieros</span><span class="sxs-lookup"><span data-stu-id="133ee-496">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-497">CC003</span><span class="sxs-lookup"><span data-stu-id="133ee-497">CC003</span></span></td>
<td><span data-ttu-id="133ee-498">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="133ee-498">Assembly</span></span></td>
<td><span data-ttu-id="133ee-499">65</span><span class="sxs-lookup"><span data-stu-id="133ee-499">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-500">CC004</span><span class="sxs-lookup"><span data-stu-id="133ee-500">CC004</span></span></td>
<td><span data-ttu-id="133ee-501">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="133ee-501">Packaging</span></span></td>
<td><span data-ttu-id="133ee-502">35</span><span class="sxs-lookup"><span data-stu-id="133ee-502">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="133ee-503">El objeto de coste CC003 Asamblea contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="133ee-503">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="133ee-504">Se crea un miembro de dimensión estadística que se denomina servicios de Asamblea para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="133ee-504">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="133ee-505">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-505">Cost object</span></span></th>
<th><span data-ttu-id="133ee-506">Servicios de la asamblea (horas)</span><span class="sxs-lookup"><span data-stu-id="133ee-506">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-507">Prod 1</span><span class="sxs-lookup"><span data-stu-id="133ee-507">Prod 1</span></span></td>
<td><span data-ttu-id="133ee-508">Producto 1</span><span class="sxs-lookup"><span data-stu-id="133ee-508">Product 1</span></span></td>
<td><span data-ttu-id="133ee-509">60</span><span class="sxs-lookup"><span data-stu-id="133ee-509">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-510">Prod 2</span><span class="sxs-lookup"><span data-stu-id="133ee-510">Prod 2</span></span></td>
<td><span data-ttu-id="133ee-511">Producto 2</span><span class="sxs-lookup"><span data-stu-id="133ee-511">Product 2</span></span></td>
<td><span data-ttu-id="133ee-512">20</span><span class="sxs-lookup"><span data-stu-id="133ee-512">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="133ee-513">El objeto de coste CC004 Embalaje contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="133ee-513">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="133ee-514">Se crea un miembro de dimensión estadística que se denomina servicios de Embalaje para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="133ee-514">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="133ee-515">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-515">Cost object</span></span></th>
<th><span data-ttu-id="133ee-516">Servicios de embalaje (horas)</span><span class="sxs-lookup"><span data-stu-id="133ee-516">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-517">Prod 1</span><span class="sxs-lookup"><span data-stu-id="133ee-517">Prod 1</span></span></td>
<td><span data-ttu-id="133ee-518">Producto 1</span><span class="sxs-lookup"><span data-stu-id="133ee-518">Product 1</span></span></td>
<td><span data-ttu-id="133ee-519">80</span><span class="sxs-lookup"><span data-stu-id="133ee-519">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-520">Prod 2</span><span class="sxs-lookup"><span data-stu-id="133ee-520">Prod 2</span></span></td>
<td><span data-ttu-id="133ee-521">Producto 2</span><span class="sxs-lookup"><span data-stu-id="133ee-521">Product 2</span></span></td>
<td><span data-ttu-id="133ee-522">15</span><span class="sxs-lookup"><span data-stu-id="133ee-522">15</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="133ee-523">**Nota:** En Finance and Operations, las medidas estadísticas como las horas de la producción que un producto consume se pueden deducir de los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="133ee-523">**Note:** In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="133ee-524">Para obtener información más detallada acerca de los proveedores de medidas estadísticas, consulte la plantilla de proveedor de estadísticas de medidas.</span><span class="sxs-lookup"><span data-stu-id="133ee-524">For more detailed information about statistical measure providers, see Statistical measure provider template.</span></span> <span data-ttu-id="133ee-525">(Tenga en cuenta que este tema todavía no está completado, pero que pronto lo estará). La tabla siguiente muestra el resultado cuando se aplican los servicios HR como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="133ee-525">(Note that this topic isn't completed yet but is coming soon.) The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="133ee-526">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-526">Cost object</span></span></th>
<th><span data-ttu-id="133ee-527">Magnitud</span><span class="sxs-lookup"><span data-stu-id="133ee-527">Magnitude</span></span></th>
<th><span data-ttu-id="133ee-528">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="133ee-528">Allocation factor</span></span></th>
<th><span data-ttu-id="133ee-529">Importe</span><span class="sxs-lookup"><span data-stu-id="133ee-529">Amount</span></span></th>
<th><span data-ttu-id="133ee-530">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="133ee-530">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-531">CC002</span><span class="sxs-lookup"><span data-stu-id="133ee-531">CC002</span></span></td>
<td><span data-ttu-id="133ee-532">Finanzas</span><span class="sxs-lookup"><span data-stu-id="133ee-532">Finance</span></span></td>
<td><span data-ttu-id="133ee-533">35</span><span class="sxs-lookup"><span data-stu-id="133ee-533">35</span></span></td>
<td><span data-ttu-id="133ee-534">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="133ee-534">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="133ee-535">175.00</span><span class="sxs-lookup"><span data-stu-id="133ee-535">175.00</span></span></td>
<td><span data-ttu-id="133ee-536">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-536">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-537">CC003</span><span class="sxs-lookup"><span data-stu-id="133ee-537">CC003</span></span></td>
<td><span data-ttu-id="133ee-538">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="133ee-538">Assembly</span></span></td>
<td><span data-ttu-id="133ee-539">55</span><span class="sxs-lookup"><span data-stu-id="133ee-539">55</span></span></td>
<td><span data-ttu-id="133ee-540">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="133ee-540">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="133ee-541">275.00</span><span class="sxs-lookup"><span data-stu-id="133ee-541">275.00</span></span></td>
<td><span data-ttu-id="133ee-542">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-542">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-543">CC004</span><span class="sxs-lookup"><span data-stu-id="133ee-543">CC004</span></span></td>
<td><span data-ttu-id="133ee-544">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="133ee-544">Packaging</span></span></td>
<td><span data-ttu-id="133ee-545">10</span><span class="sxs-lookup"><span data-stu-id="133ee-545">10</span></span></td>
<td><span data-ttu-id="133ee-546">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="133ee-546">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="133ee-547">50,00</span><span class="sxs-lookup"><span data-stu-id="133ee-547">50.00</span></span></td>
<td><span data-ttu-id="133ee-548">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-548">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-549">CC002</span><span class="sxs-lookup"><span data-stu-id="133ee-549">CC002</span></span></td>
<td><span data-ttu-id="133ee-550">Finanzas</span><span class="sxs-lookup"><span data-stu-id="133ee-550">Finance</span></span></td>
<td><span data-ttu-id="133ee-551">35</span><span class="sxs-lookup"><span data-stu-id="133ee-551">35</span></span></td>
<td><span data-ttu-id="133ee-552">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="133ee-552">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="133ee-553">436.00</span><span class="sxs-lookup"><span data-stu-id="133ee-553">436.00</span></span></td>
<td><span data-ttu-id="133ee-554">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-554">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-555">CC003</span><span class="sxs-lookup"><span data-stu-id="133ee-555">CC003</span></span></td>
<td><span data-ttu-id="133ee-556">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="133ee-556">Assembly</span></span></td>
<td><span data-ttu-id="133ee-557">55</span><span class="sxs-lookup"><span data-stu-id="133ee-557">55</span></span></td>
<td><span data-ttu-id="133ee-558">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="133ee-558">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="133ee-559">685.14</span><span class="sxs-lookup"><span data-stu-id="133ee-559">685.14</span></span></td>
<td><span data-ttu-id="133ee-560">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-560">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-561">CC004</span><span class="sxs-lookup"><span data-stu-id="133ee-561">CC004</span></span></td>
<td><span data-ttu-id="133ee-562">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="133ee-562">Packaging</span></span></td>
<td><span data-ttu-id="133ee-563">10</span><span class="sxs-lookup"><span data-stu-id="133ee-563">10</span></span></td>
<td><span data-ttu-id="133ee-564">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="133ee-564">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="133ee-565">124.57</span><span class="sxs-lookup"><span data-stu-id="133ee-565">124.57</span></span></td>
<td><span data-ttu-id="133ee-566">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-566">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="133ee-567">La tabla siguiente muestra el resultado cuando se aplican los servicios de Finanzas como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="133ee-567">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="133ee-568">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-568">Cost object</span></span></th>
<th><span data-ttu-id="133ee-569">Magnitud</span><span class="sxs-lookup"><span data-stu-id="133ee-569">Magnitude</span></span></th>
<th><span data-ttu-id="133ee-570">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="133ee-570">Allocation factor</span></span></th>
<th><span data-ttu-id="133ee-571">Importe</span><span class="sxs-lookup"><span data-stu-id="133ee-571">Amount</span></span></th>
<th><span data-ttu-id="133ee-572">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="133ee-572">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-573">CC003</span><span class="sxs-lookup"><span data-stu-id="133ee-573">CC003</span></span></td>
<td><span data-ttu-id="133ee-574">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="133ee-574">Assembly</span></span></td>
<td><span data-ttu-id="133ee-575">65</span><span class="sxs-lookup"><span data-stu-id="133ee-575">65</span></span></td>
<td><span data-ttu-id="133ee-576">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="133ee-576">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="133ee-577">438.75</span><span class="sxs-lookup"><span data-stu-id="133ee-577">438.75</span></span></td>
<td><span data-ttu-id="133ee-578">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-578">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-579">CC004</span><span class="sxs-lookup"><span data-stu-id="133ee-579">CC004</span></span></td>
<td><span data-ttu-id="133ee-580">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="133ee-580">Packaging</span></span></td>
<td><span data-ttu-id="133ee-581">35</span><span class="sxs-lookup"><span data-stu-id="133ee-581">35</span></span></td>
<td><span data-ttu-id="133ee-582">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="133ee-582">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="133ee-583">236.25</span><span class="sxs-lookup"><span data-stu-id="133ee-583">236.25</span></span></td>
<td><span data-ttu-id="133ee-584">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-584">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-585">CC003</span><span class="sxs-lookup"><span data-stu-id="133ee-585">CC003</span></span></td>
<td><span data-ttu-id="133ee-586">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="133ee-586">Assembly</span></span></td>
<td><span data-ttu-id="133ee-587">65</span><span class="sxs-lookup"><span data-stu-id="133ee-587">65</span></span></td>
<td><span data-ttu-id="133ee-588">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="133ee-588">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="133ee-589">5,297.69</span><span class="sxs-lookup"><span data-stu-id="133ee-589">5,297.69</span></span></td>
<td><span data-ttu-id="133ee-590">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-590">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-591">CC004</span><span class="sxs-lookup"><span data-stu-id="133ee-591">CC004</span></span></td>
<td><span data-ttu-id="133ee-592">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="133ee-592">Packaging</span></span></td>
<td><span data-ttu-id="133ee-593">35</span><span class="sxs-lookup"><span data-stu-id="133ee-593">35</span></span></td>
<td><span data-ttu-id="133ee-594">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="133ee-594">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="133ee-595">2,852.60</span><span class="sxs-lookup"><span data-stu-id="133ee-595">2,852.60</span></span></td>
<td><span data-ttu-id="133ee-596">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-596">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="133ee-597">La tabla siguiente muestra el resultado cuando se aplican los servicios de Asamblea como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="133ee-597">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="133ee-598">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-598">Cost object</span></span></th>
<th><span data-ttu-id="133ee-599">Magnitud</span><span class="sxs-lookup"><span data-stu-id="133ee-599">Magnitude</span></span></th>
<th><span data-ttu-id="133ee-600">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="133ee-600">Allocation factor</span></span></th>
<th><span data-ttu-id="133ee-601">Importe</span><span class="sxs-lookup"><span data-stu-id="133ee-601">Amount</span></span></th>
<th><span data-ttu-id="133ee-602">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="133ee-602">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-603">Prod 1</span><span class="sxs-lookup"><span data-stu-id="133ee-603">Prod 1</span></span></td>
<td><span data-ttu-id="133ee-604">Producto 1</span><span class="sxs-lookup"><span data-stu-id="133ee-604">Product 1</span></span></td>
<td><span data-ttu-id="133ee-605">60</span><span class="sxs-lookup"><span data-stu-id="133ee-605">60</span></span></td>
<td><span data-ttu-id="133ee-606">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="133ee-606">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="133ee-607">535.31</span><span class="sxs-lookup"><span data-stu-id="133ee-607">535.31</span></span></td>
<td><span data-ttu-id="133ee-608">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-608">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-609">Prod 2</span><span class="sxs-lookup"><span data-stu-id="133ee-609">Prod 2</span></span></td>
<td><span data-ttu-id="133ee-610">Producto 2</span><span class="sxs-lookup"><span data-stu-id="133ee-610">Product 2</span></span></td>
<td><span data-ttu-id="133ee-611">20</span><span class="sxs-lookup"><span data-stu-id="133ee-611">20</span></span></td>
<td><span data-ttu-id="133ee-612">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="133ee-612">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="133ee-613">178.44</span><span class="sxs-lookup"><span data-stu-id="133ee-613">178.44</span></span></td>
<td><span data-ttu-id="133ee-614">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-614">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-615">Prod 1</span><span class="sxs-lookup"><span data-stu-id="133ee-615">Prod 1</span></span></td>
<td><span data-ttu-id="133ee-616">Producto 1</span><span class="sxs-lookup"><span data-stu-id="133ee-616">Product 1</span></span></td>
<td><span data-ttu-id="133ee-617">60</span><span class="sxs-lookup"><span data-stu-id="133ee-617">60</span></span></td>
<td><span data-ttu-id="133ee-618">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="133ee-618">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="133ee-619">4,487.12</span><span class="sxs-lookup"><span data-stu-id="133ee-619">4,487.12</span></span></td>
<td><span data-ttu-id="133ee-620">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-620">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-621">Prod 2</span><span class="sxs-lookup"><span data-stu-id="133ee-621">Prod 2</span></span></td>
<td><span data-ttu-id="133ee-622">Producto 2</span><span class="sxs-lookup"><span data-stu-id="133ee-622">Product 2</span></span></td>
<td><span data-ttu-id="133ee-623">20</span><span class="sxs-lookup"><span data-stu-id="133ee-623">20</span></span></td>
<td><span data-ttu-id="133ee-624">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="133ee-624">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="133ee-625">1,495.71</span><span class="sxs-lookup"><span data-stu-id="133ee-625">1,495.71</span></span></td>
<td><span data-ttu-id="133ee-626">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-626">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="133ee-627">La tabla siguiente muestra el resultado cuando se aplican los servicios de Embalaje como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="133ee-627">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="133ee-628">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-628">Cost object</span></span></th>
<th><span data-ttu-id="133ee-629">Magnitud</span><span class="sxs-lookup"><span data-stu-id="133ee-629">Magnitude</span></span></th>
<th><span data-ttu-id="133ee-630">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="133ee-630">Allocation factor</span></span></th>
<th><span data-ttu-id="133ee-631">Importe</span><span class="sxs-lookup"><span data-stu-id="133ee-631">Amount</span></span></th>
<th><span data-ttu-id="133ee-632">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="133ee-632">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-633">Prod 1</span><span class="sxs-lookup"><span data-stu-id="133ee-633">Prod 1</span></span></td>
<td><span data-ttu-id="133ee-634">Producto 1</span><span class="sxs-lookup"><span data-stu-id="133ee-634">Product 1</span></span></td>
<td><span data-ttu-id="133ee-635">80</span><span class="sxs-lookup"><span data-stu-id="133ee-635">80</span></span></td>
<td><span data-ttu-id="133ee-636">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="133ee-636">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="133ee-637">241.05</span><span class="sxs-lookup"><span data-stu-id="133ee-637">241.05</span></span></td>
<td><span data-ttu-id="133ee-638">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-638">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-639">Prod 2</span><span class="sxs-lookup"><span data-stu-id="133ee-639">Prod 2</span></span></td>
<td><span data-ttu-id="133ee-640">Producto 2</span><span class="sxs-lookup"><span data-stu-id="133ee-640">Product 2</span></span></td>
<td><span data-ttu-id="133ee-641">15</span><span class="sxs-lookup"><span data-stu-id="133ee-641">15</span></span></td>
<td><span data-ttu-id="133ee-642">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="133ee-642">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="133ee-643">45.20</span><span class="sxs-lookup"><span data-stu-id="133ee-643">45.20</span></span></td>
<td><span data-ttu-id="133ee-644">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-644">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-645">Prod 1</span><span class="sxs-lookup"><span data-stu-id="133ee-645">Prod 1</span></span></td>
<td><span data-ttu-id="133ee-646">Producto 1</span><span class="sxs-lookup"><span data-stu-id="133ee-646">Product 1</span></span></td>
<td><span data-ttu-id="133ee-647">80</span><span class="sxs-lookup"><span data-stu-id="133ee-647">80</span></span></td>
<td><span data-ttu-id="133ee-648">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="133ee-648">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="133ee-649">2,507.09</span><span class="sxs-lookup"><span data-stu-id="133ee-649">2,507.09</span></span></td>
<td><span data-ttu-id="133ee-650">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-650">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-651">Prod 2</span><span class="sxs-lookup"><span data-stu-id="133ee-651">Prod 2</span></span></td>
<td><span data-ttu-id="133ee-652">Producto 2</span><span class="sxs-lookup"><span data-stu-id="133ee-652">Product 2</span></span></td>
<td><span data-ttu-id="133ee-653">15</span><span class="sxs-lookup"><span data-stu-id="133ee-653">15</span></span></td>
<td><span data-ttu-id="133ee-654">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="133ee-654">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="133ee-655">470.08</span><span class="sxs-lookup"><span data-stu-id="133ee-655">470.08</span></span></td>
<td><span data-ttu-id="133ee-656">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-656">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="133ee-657">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="133ee-657">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="133ee-658">Diario</span><span class="sxs-lookup"><span data-stu-id="133ee-658">Journal</span></span></th>
<th><span data-ttu-id="133ee-659">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="133ee-659">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="133ee-660">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="133ee-660">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="133ee-661">Versión</span><span class="sxs-lookup"><span data-stu-id="133ee-661">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-662">00004</span><span class="sxs-lookup"><span data-stu-id="133ee-662">00004</span></span></td>
<td><span data-ttu-id="133ee-663">Diario de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="133ee-663">Cost allocation journal</span></span></td>
<td><span data-ttu-id="133ee-664">Fiscal</span><span class="sxs-lookup"><span data-stu-id="133ee-664">Fiscal</span></span></td>
<td><span data-ttu-id="133ee-665">2017</span><span class="sxs-lookup"><span data-stu-id="133ee-665">2017</span></span></td>
<td><span data-ttu-id="133ee-666">Período 1</span><span class="sxs-lookup"><span data-stu-id="133ee-666">Period 1</span></span></td>
<td><span data-ttu-id="133ee-667">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="133ee-667">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="133ee-668">Líneas de diario</span><span class="sxs-lookup"><span data-stu-id="133ee-668">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="133ee-669">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="133ee-669">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="133ee-670">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-670">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="133ee-671">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-671">Cost element</span></span></th>
<th><span data-ttu-id="133ee-672">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="133ee-672">Cost behavior</span></span></th>
<th><span data-ttu-id="133ee-673">Importe</span><span class="sxs-lookup"><span data-stu-id="133ee-673">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-674">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-674">January 31, 2017</span></span></td>
<td><span data-ttu-id="133ee-675">CC001</span><span class="sxs-lookup"><span data-stu-id="133ee-675">CC001</span></span></td>
<td><span data-ttu-id="133ee-676">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="133ee-676">HR</span></span></td>
<td><span data-ttu-id="133ee-677">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-677">10001</span></span></td>
<td><span data-ttu-id="133ee-678">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-678">Electricity</span></span></td>
<td><span data-ttu-id="133ee-679">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-679">Fixed cost</span></span></td>
<td><span data-ttu-id="133ee-680">500,00</span><span class="sxs-lookup"><span data-stu-id="133ee-680">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-681">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-681">January 31, 2017</span></span></td>
<td><span data-ttu-id="133ee-682">CC001</span><span class="sxs-lookup"><span data-stu-id="133ee-682">CC001</span></span></td>
<td><span data-ttu-id="133ee-683">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="133ee-683">HR</span></span></td>
<td><span data-ttu-id="133ee-684">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-684">10001</span></span></td>
<td><span data-ttu-id="133ee-685">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-685">Electricity</span></span></td>
<td><span data-ttu-id="133ee-686">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-686">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-687">1,245.71</span><span class="sxs-lookup"><span data-stu-id="133ee-687">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-688">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-688">January 31, 2017</span></span></td>
<td><span data-ttu-id="133ee-689">CC002</span><span class="sxs-lookup"><span data-stu-id="133ee-689">CC002</span></span></td>
<td><span data-ttu-id="133ee-690">Finanzas</span><span class="sxs-lookup"><span data-stu-id="133ee-690">Finance</span></span></td>
<td><span data-ttu-id="133ee-691">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-691">10001</span></span></td>
<td><span data-ttu-id="133ee-692">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-692">Electricity</span></span></td>
<td><span data-ttu-id="133ee-693">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-693">Fixed cost</span></span></td>
<td><span data-ttu-id="133ee-694">675.00</span><span class="sxs-lookup"><span data-stu-id="133ee-694">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-695">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-695">January 31, 2017</span></span></td>
<td><span data-ttu-id="133ee-696">CC002</span><span class="sxs-lookup"><span data-stu-id="133ee-696">CC002</span></span></td>
<td><span data-ttu-id="133ee-697">Finanzas</span><span class="sxs-lookup"><span data-stu-id="133ee-697">Finance</span></span></td>
<td><span data-ttu-id="133ee-698">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-698">10001</span></span></td>
<td><span data-ttu-id="133ee-699">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-699">Electricity</span></span></td>
<td><span data-ttu-id="133ee-700">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-700">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-701">8,150.29</span><span class="sxs-lookup"><span data-stu-id="133ee-701">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-702">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-702">January 31, 2017</span></span></td>
<td><span data-ttu-id="133ee-703">CC003</span><span class="sxs-lookup"><span data-stu-id="133ee-703">CC003</span></span></td>
<td><span data-ttu-id="133ee-704">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="133ee-704">Assembly</span></span></td>
<td><span data-ttu-id="133ee-705">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-705">10001</span></span></td>
<td><span data-ttu-id="133ee-706">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-706">Electricity</span></span></td>
<td><span data-ttu-id="133ee-707">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-707">Fixed cost</span></span></td>
<td><span data-ttu-id="133ee-708">713.75</span><span class="sxs-lookup"><span data-stu-id="133ee-708">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-709">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-709">January 31, 2017</span></span></td>
<td><span data-ttu-id="133ee-710">CC003</span><span class="sxs-lookup"><span data-stu-id="133ee-710">CC003</span></span></td>
<td><span data-ttu-id="133ee-711">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="133ee-711">Assembly</span></span></td>
<td><span data-ttu-id="133ee-712">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-712">10001</span></span></td>
<td><span data-ttu-id="133ee-713">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-713">Electricity</span></span></td>
<td><span data-ttu-id="133ee-714">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-714">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-715">5,982.83</span><span class="sxs-lookup"><span data-stu-id="133ee-715">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-716">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-716">January 31, 2017</span></span></td>
<td><span data-ttu-id="133ee-717">CC003</span><span class="sxs-lookup"><span data-stu-id="133ee-717">CC003</span></span></td>
<td><span data-ttu-id="133ee-718">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="133ee-718">Packaging</span></span></td>
<td><span data-ttu-id="133ee-719">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-719">10001</span></span></td>
<td><span data-ttu-id="133ee-720">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-720">Electricity</span></span></td>
<td><span data-ttu-id="133ee-721">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-721">Fixed cost</span></span></td>
<td><span data-ttu-id="133ee-722">286.25</span><span class="sxs-lookup"><span data-stu-id="133ee-722">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-723">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-723">January 31, 2017</span></span></td>
<td><span data-ttu-id="133ee-724">CC003</span><span class="sxs-lookup"><span data-stu-id="133ee-724">CC003</span></span></td>
<td><span data-ttu-id="133ee-725">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="133ee-725">Packaging</span></span></td>
<td><span data-ttu-id="133ee-726">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-726">10001</span></span></td>
<td><span data-ttu-id="133ee-727">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-727">Electricity</span></span></td>
<td><span data-ttu-id="133ee-728">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-728">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-729">2,977.17</span><span class="sxs-lookup"><span data-stu-id="133ee-729">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-730">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-730">January 31, 2017</span></span></td>
<td><span data-ttu-id="133ee-731">Prod 1</span><span class="sxs-lookup"><span data-stu-id="133ee-731">Prod 1</span></span></td>
<td><span data-ttu-id="133ee-732">Producto 1</span><span class="sxs-lookup"><span data-stu-id="133ee-732">Product 1</span></span></td>
<td><span data-ttu-id="133ee-733">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-733">10001</span></span></td>
<td><span data-ttu-id="133ee-734">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-734">Electricity</span></span></td>
<td><span data-ttu-id="133ee-735">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-735">Fixed cost</span></span></td>
<td><span data-ttu-id="133ee-736">776.36</span><span class="sxs-lookup"><span data-stu-id="133ee-736">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-737">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-737">January 31, 2017</span></span></td>
<td><span data-ttu-id="133ee-738">Prod 1</span><span class="sxs-lookup"><span data-stu-id="133ee-738">Prod 1</span></span></td>
<td><span data-ttu-id="133ee-739">Producto 1</span><span class="sxs-lookup"><span data-stu-id="133ee-739">Product 1</span></span></td>
<td><span data-ttu-id="133ee-740">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-740">10001</span></span></td>
<td><span data-ttu-id="133ee-741">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-741">Electricity</span></span></td>
<td><span data-ttu-id="133ee-742">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-742">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-743">6,994.21</span><span class="sxs-lookup"><span data-stu-id="133ee-743">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-744">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-744">January 31, 2017</span></span></td>
<td><span data-ttu-id="133ee-745">Prod 2</span><span class="sxs-lookup"><span data-stu-id="133ee-745">Prod 2</span></span></td>
<td><span data-ttu-id="133ee-746">Producto 1</span><span class="sxs-lookup"><span data-stu-id="133ee-746">Product 1</span></span></td>
<td><span data-ttu-id="133ee-747">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-747">10001</span></span></td>
<td><span data-ttu-id="133ee-748">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-748">Electricity</span></span></td>
<td><span data-ttu-id="133ee-749">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-749">Fixed cost</span></span></td>
<td><span data-ttu-id="133ee-750">223.64</span><span class="sxs-lookup"><span data-stu-id="133ee-750">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-751">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-751">January 31, 2017</span></span></td>
<td><span data-ttu-id="133ee-752">Prod 2</span><span class="sxs-lookup"><span data-stu-id="133ee-752">Prod 2</span></span></td>
<td><span data-ttu-id="133ee-753">Producto 1</span><span class="sxs-lookup"><span data-stu-id="133ee-753">Product 1</span></span></td>
<td><span data-ttu-id="133ee-754">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-754">10001</span></span></td>
<td><span data-ttu-id="133ee-755">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-755">Electricity</span></span></td>
<td><span data-ttu-id="133ee-756">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-756">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-757">1,965.79</span><span class="sxs-lookup"><span data-stu-id="133ee-757">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="133ee-758">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="133ee-758">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="133ee-759">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-759">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="133ee-760">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-760">Cost element</span></span></th>
<th><span data-ttu-id="133ee-761">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="133ee-761">Cost behavior</span></span></th>
<th><span data-ttu-id="133ee-762">Importe</span><span class="sxs-lookup"><span data-stu-id="133ee-762">Amount</span></span></th>
<th><span data-ttu-id="133ee-763">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="133ee-763">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="133ee-764">CC001</span><span class="sxs-lookup"><span data-stu-id="133ee-764">CC001</span></span></td>
<td><span data-ttu-id="133ee-765">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="133ee-765">HR</span></span></td>
<td><span data-ttu-id="133ee-766">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-766">10001</span></span></td>
<td><span data-ttu-id="133ee-767">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-767">Electricity</span></span></td>
<td><span data-ttu-id="133ee-768">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-768">Fixed cost</span></span></td>
<td><span data-ttu-id="133ee-769">-500,00</span><span class="sxs-lookup"><span data-stu-id="133ee-769">-500.00</span></span></td>
<td><span data-ttu-id="133ee-770">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-770">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-771">CC002</span><span class="sxs-lookup"><span data-stu-id="133ee-771">CC002</span></span></td>
<td><span data-ttu-id="133ee-772">Finanzas</span><span class="sxs-lookup"><span data-stu-id="133ee-772">Finance</span></span></td>
<td><span data-ttu-id="133ee-773">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-773">10001</span></span></td>
<td><span data-ttu-id="133ee-774">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-774">Electricity</span></span></td>
<td><span data-ttu-id="133ee-775">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-775">Fixed cost</span></span></td>
<td><span data-ttu-id="133ee-776">175.00</span><span class="sxs-lookup"><span data-stu-id="133ee-776">175.00</span></span></td>
<td><span data-ttu-id="133ee-777">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-777">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-778">CC003</span><span class="sxs-lookup"><span data-stu-id="133ee-778">CC003</span></span></td>
<td><span data-ttu-id="133ee-779">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="133ee-779">Assembly</span></span></td>
<td><span data-ttu-id="133ee-780">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-780">10001</span></span></td>
<td><span data-ttu-id="133ee-781">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-781">Electricity</span></span></td>
<td><span data-ttu-id="133ee-782">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-782">Fixed cost</span></span></td>
<td><span data-ttu-id="133ee-783">275.00</span><span class="sxs-lookup"><span data-stu-id="133ee-783">275.00</span></span></td>
<td><span data-ttu-id="133ee-784">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-784">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-785">CC004</span><span class="sxs-lookup"><span data-stu-id="133ee-785">CC004</span></span></td>
<td><span data-ttu-id="133ee-786">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="133ee-786">Packaging</span></span></td>
<td><span data-ttu-id="133ee-787">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-787">10001</span></span></td>
<td><span data-ttu-id="133ee-788">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-788">Electricity</span></span></td>
<td><span data-ttu-id="133ee-789">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-789">Fixed cost</span></span></td>
<td><span data-ttu-id="133ee-790">50,00</span><span class="sxs-lookup"><span data-stu-id="133ee-790">50,00</span></span></td>
<td><span data-ttu-id="133ee-791">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-791">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-792">CC001</span><span class="sxs-lookup"><span data-stu-id="133ee-792">CC001</span></span></td>
<td><span data-ttu-id="133ee-793">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="133ee-793">HR</span></span></td>
<td><span data-ttu-id="133ee-794">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-794">10001</span></span></td>
<td><span data-ttu-id="133ee-795">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-795">Electricity</span></span></td>
<td><span data-ttu-id="133ee-796">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-796">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-797">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="133ee-797">-1,245.71</span></span></td>
<td><span data-ttu-id="133ee-798">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-798">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-799">CC002</span><span class="sxs-lookup"><span data-stu-id="133ee-799">CC002</span></span></td>
<td><span data-ttu-id="133ee-800">Finanzas</span><span class="sxs-lookup"><span data-stu-id="133ee-800">Finance</span></span></td>
<td><span data-ttu-id="133ee-801">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-801">10001</span></span></td>
<td><span data-ttu-id="133ee-802">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-802">Electricity</span></span></td>
<td><span data-ttu-id="133ee-803">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-803">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-804">436.00</span><span class="sxs-lookup"><span data-stu-id="133ee-804">436.00</span></span></td>
<td><span data-ttu-id="133ee-805">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-805">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-806">CC003</span><span class="sxs-lookup"><span data-stu-id="133ee-806">CC003</span></span></td>
<td><span data-ttu-id="133ee-807">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="133ee-807">Assembly</span></span></td>
<td><span data-ttu-id="133ee-808">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-808">10001</span></span></td>
<td><span data-ttu-id="133ee-809">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-809">Electricity</span></span></td>
<td><span data-ttu-id="133ee-810">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-810">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-811">685.14</span><span class="sxs-lookup"><span data-stu-id="133ee-811">685.14</span></span></td>
<td><span data-ttu-id="133ee-812">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-812">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-813">CC004</span><span class="sxs-lookup"><span data-stu-id="133ee-813">CC004</span></span></td>
<td><span data-ttu-id="133ee-814">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="133ee-814">Packaging</span></span></td>
<td><span data-ttu-id="133ee-815">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-815">10001</span></span></td>
<td><span data-ttu-id="133ee-816">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-816">Electricity</span></span></td>
<td><span data-ttu-id="133ee-817">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-817">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-818">124.57</span><span class="sxs-lookup"><span data-stu-id="133ee-818">124.57</span></span></td>
<td><span data-ttu-id="133ee-819">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-819">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-820">CC002</span><span class="sxs-lookup"><span data-stu-id="133ee-820">CC002</span></span></td>
<td><span data-ttu-id="133ee-821">Finanzas</span><span class="sxs-lookup"><span data-stu-id="133ee-821">Finance</span></span></td>
<td><span data-ttu-id="133ee-822">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-822">10001</span></span></td>
<td><span data-ttu-id="133ee-823">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-823">Electricity</span></span></td>
<td><span data-ttu-id="133ee-824">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-824">Fixed cost</span></span></td>
<td><span data-ttu-id="133ee-825">-675,00</span><span class="sxs-lookup"><span data-stu-id="133ee-825">-675.00</span></span></td>
<td><span data-ttu-id="133ee-826">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-826">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-827">CC003</span><span class="sxs-lookup"><span data-stu-id="133ee-827">CC003</span></span></td>
<td><span data-ttu-id="133ee-828">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="133ee-828">Assembly</span></span></td>
<td><span data-ttu-id="133ee-829">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-829">10001</span></span></td>
<td><span data-ttu-id="133ee-830">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-830">Electricity</span></span></td>
<td><span data-ttu-id="133ee-831">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-831">Fixed cost</span></span></td>
<td><span data-ttu-id="133ee-832">438.75</span><span class="sxs-lookup"><span data-stu-id="133ee-832">438.75</span></span></td>
<td><span data-ttu-id="133ee-833">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-833">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-834">CC004</span><span class="sxs-lookup"><span data-stu-id="133ee-834">CC004</span></span></td>
<td><span data-ttu-id="133ee-835">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="133ee-835">Packaging</span></span></td>
<td><span data-ttu-id="133ee-836">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-836">10001</span></span></td>
<td><span data-ttu-id="133ee-837">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-837">Electricity</span></span></td>
<td><span data-ttu-id="133ee-838">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-838">Fixed cost</span></span></td>
<td><span data-ttu-id="133ee-839">236.25</span><span class="sxs-lookup"><span data-stu-id="133ee-839">236.25</span></span></td>
<td><span data-ttu-id="133ee-840">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-840">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-841">CC002</span><span class="sxs-lookup"><span data-stu-id="133ee-841">CC002</span></span></td>
<td><span data-ttu-id="133ee-842">Finanzas</span><span class="sxs-lookup"><span data-stu-id="133ee-842">Finance</span></span></td>
<td><span data-ttu-id="133ee-843">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-843">10001</span></span></td>
<td><span data-ttu-id="133ee-844">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-844">Electricity</span></span></td>
<td><span data-ttu-id="133ee-845">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-845">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-846">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="133ee-846">-8,150.29</span></span></td>
<td><span data-ttu-id="133ee-847">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-847">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-848">CC003</span><span class="sxs-lookup"><span data-stu-id="133ee-848">CC003</span></span></td>
<td><span data-ttu-id="133ee-849">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="133ee-849">Assembly</span></span></td>
<td><span data-ttu-id="133ee-850">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-850">10001</span></span></td>
<td><span data-ttu-id="133ee-851">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-851">Electricity</span></span></td>
<td><span data-ttu-id="133ee-852">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-852">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-853">5,297.69</span><span class="sxs-lookup"><span data-stu-id="133ee-853">5,297.69</span></span></td>
<td><span data-ttu-id="133ee-854">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-854">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-855">CC004</span><span class="sxs-lookup"><span data-stu-id="133ee-855">CC004</span></span></td>
<td><span data-ttu-id="133ee-856">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="133ee-856">Packaging</span></span></td>
<td><span data-ttu-id="133ee-857">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-857">10001</span></span></td>
<td><span data-ttu-id="133ee-858">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-858">Electricity</span></span></td>
<td><span data-ttu-id="133ee-859">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-859">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-860">2,852.60</span><span class="sxs-lookup"><span data-stu-id="133ee-860">2,852.60</span></span></td>
<td><span data-ttu-id="133ee-861">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-861">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-862">CC003</span><span class="sxs-lookup"><span data-stu-id="133ee-862">CC003</span></span></td>
<td><span data-ttu-id="133ee-863">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="133ee-863">Assembly</span></span></td>
<td><span data-ttu-id="133ee-864">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-864">10001</span></span></td>
<td><span data-ttu-id="133ee-865">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-865">Electricity</span></span></td>
<td><span data-ttu-id="133ee-866">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-866">Fixed cost</span></span></td>
<td><span data-ttu-id="133ee-867">-713,75</span><span class="sxs-lookup"><span data-stu-id="133ee-867">-713.75</span></span></td>
<td><span data-ttu-id="133ee-868">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-868">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-869">Prod 1</span><span class="sxs-lookup"><span data-stu-id="133ee-869">Prod 1</span></span></td>
<td><span data-ttu-id="133ee-870">Producto 1</span><span class="sxs-lookup"><span data-stu-id="133ee-870">Product 1</span></span></td>
<td><span data-ttu-id="133ee-871">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-871">10001</span></span></td>
<td><span data-ttu-id="133ee-872">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-872">Electricity</span></span></td>
<td><span data-ttu-id="133ee-873">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-873">Fixed cost</span></span></td>
<td><span data-ttu-id="133ee-874">535.31</span><span class="sxs-lookup"><span data-stu-id="133ee-874">535.31</span></span></td>
<td><span data-ttu-id="133ee-875">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-875">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-876">Prod 2</span><span class="sxs-lookup"><span data-stu-id="133ee-876">Prod 2</span></span></td>
<td><span data-ttu-id="133ee-877">Producto 2</span><span class="sxs-lookup"><span data-stu-id="133ee-877">Product 2</span></span></td>
<td><span data-ttu-id="133ee-878">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-878">10001</span></span></td>
<td><span data-ttu-id="133ee-879">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-879">Electricity</span></span></td>
<td><span data-ttu-id="133ee-880">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-880">Fixed cost</span></span></td>
<td><span data-ttu-id="133ee-881">178.44</span><span class="sxs-lookup"><span data-stu-id="133ee-881">178.44</span></span></td>
<td><span data-ttu-id="133ee-882">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-882">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-883">CC003</span><span class="sxs-lookup"><span data-stu-id="133ee-883">CC003</span></span></td>
<td><span data-ttu-id="133ee-884">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="133ee-884">Assembly</span></span></td>
<td><span data-ttu-id="133ee-885">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-885">10001</span></span></td>
<td><span data-ttu-id="133ee-886">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-886">Electricity</span></span></td>
<td><span data-ttu-id="133ee-887">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-887">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-888">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="133ee-888">-5,982.83</span></span></td>
<td><span data-ttu-id="133ee-889">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-889">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-890">Prod 1</span><span class="sxs-lookup"><span data-stu-id="133ee-890">Prod 1</span></span></td>
<td><span data-ttu-id="133ee-891">Producto 1</span><span class="sxs-lookup"><span data-stu-id="133ee-891">Product 1</span></span></td>
<td><span data-ttu-id="133ee-892">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-892">10001</span></span></td>
<td><span data-ttu-id="133ee-893">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-893">Electricity</span></span></td>
<td><span data-ttu-id="133ee-894">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-894">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-895">4,487.12</span><span class="sxs-lookup"><span data-stu-id="133ee-895">4,487.12</span></span></td>
<td><span data-ttu-id="133ee-896">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-896">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-897">Prod 2</span><span class="sxs-lookup"><span data-stu-id="133ee-897">Prod 2</span></span></td>
<td><span data-ttu-id="133ee-898">Producto 2</span><span class="sxs-lookup"><span data-stu-id="133ee-898">Product 2</span></span></td>
<td><span data-ttu-id="133ee-899">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-899">10001</span></span></td>
<td><span data-ttu-id="133ee-900">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-900">Electricity</span></span></td>
<td><span data-ttu-id="133ee-901">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-901">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-902">1,495.71</span><span class="sxs-lookup"><span data-stu-id="133ee-902">1,495.71</span></span></td>
<td><span data-ttu-id="133ee-903">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-903">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-904">CC003</span><span class="sxs-lookup"><span data-stu-id="133ee-904">CC003</span></span></td>
<td><span data-ttu-id="133ee-905">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="133ee-905">Assembly</span></span></td>
<td><span data-ttu-id="133ee-906">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-906">10001</span></span></td>
<td><span data-ttu-id="133ee-907">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-907">Electricity</span></span></td>
<td><span data-ttu-id="133ee-908">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-908">Fixed cost</span></span></td>
<td><span data-ttu-id="133ee-909">-286,25</span><span class="sxs-lookup"><span data-stu-id="133ee-909">-286.25</span></span></td>
<td><span data-ttu-id="133ee-910">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-910">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-911">Prod 1</span><span class="sxs-lookup"><span data-stu-id="133ee-911">Prod 1</span></span></td>
<td><span data-ttu-id="133ee-912">Producto 1</span><span class="sxs-lookup"><span data-stu-id="133ee-912">Product 1</span></span></td>
<td><span data-ttu-id="133ee-913">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-913">10001</span></span></td>
<td><span data-ttu-id="133ee-914">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-914">Electricity</span></span></td>
<td><span data-ttu-id="133ee-915">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-915">Fixed cost</span></span></td>
<td><span data-ttu-id="133ee-916">241.05</span><span class="sxs-lookup"><span data-stu-id="133ee-916">241.05</span></span></td>
<td><span data-ttu-id="133ee-917">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-917">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-918">Prod 2</span><span class="sxs-lookup"><span data-stu-id="133ee-918">Prod 2</span></span></td>
<td><span data-ttu-id="133ee-919">Producto 2</span><span class="sxs-lookup"><span data-stu-id="133ee-919">Product 2</span></span></td>
<td><span data-ttu-id="133ee-920">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-920">10001</span></span></td>
<td><span data-ttu-id="133ee-921">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-921">Electricity</span></span></td>
<td><span data-ttu-id="133ee-922">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-922">Fixed cost</span></span></td>
<td><span data-ttu-id="133ee-923">45.20</span><span class="sxs-lookup"><span data-stu-id="133ee-923">45.20</span></span></td>
<td><span data-ttu-id="133ee-924">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-924">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-925">CC003</span><span class="sxs-lookup"><span data-stu-id="133ee-925">CC003</span></span></td>
<td><span data-ttu-id="133ee-926">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="133ee-926">Assembly</span></span></td>
<td><span data-ttu-id="133ee-927">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-927">10001</span></span></td>
<td><span data-ttu-id="133ee-928">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-928">Electricity</span></span></td>
<td><span data-ttu-id="133ee-929">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-929">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-930">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="133ee-930">-2,977.17</span></span></td>
<td><span data-ttu-id="133ee-931">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-931">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-932">Prod 1</span><span class="sxs-lookup"><span data-stu-id="133ee-932">Prod 1</span></span></td>
<td><span data-ttu-id="133ee-933">Producto 1</span><span class="sxs-lookup"><span data-stu-id="133ee-933">Product 1</span></span></td>
<td><span data-ttu-id="133ee-934">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-934">10001</span></span></td>
<td><span data-ttu-id="133ee-935">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-935">Electricity</span></span></td>
<td><span data-ttu-id="133ee-936">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-936">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-937">2,507.09</span><span class="sxs-lookup"><span data-stu-id="133ee-937">2,507.09</span></span></td>
<td><span data-ttu-id="133ee-938">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-938">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="133ee-939">Prod 2</span><span class="sxs-lookup"><span data-stu-id="133ee-939">Prod 2</span></span></td>
<td><span data-ttu-id="133ee-940">Producto 2</span><span class="sxs-lookup"><span data-stu-id="133ee-940">Product 2</span></span></td>
<td><span data-ttu-id="133ee-941">10001</span><span class="sxs-lookup"><span data-stu-id="133ee-941">10001</span></span></td>
<td><span data-ttu-id="133ee-942">Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-942">Electricity</span></span></td>
<td><span data-ttu-id="133ee-943">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-943">Variable cost</span></span></td>
<td><span data-ttu-id="133ee-944">470.08</span><span class="sxs-lookup"><span data-stu-id="133ee-944">470.08</span></span></td>
<td><span data-ttu-id="133ee-945">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="133ee-945">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="133ee-946">Conclusión</span><span class="sxs-lookup"><span data-stu-id="133ee-946">Conclusion</span></span>
<span data-ttu-id="133ee-947">En la contabilidad financiera, un coste de 10.000,00 para electricidad se envía a un identificador ficticio de centro de coste.</span><span class="sxs-lookup"><span data-stu-id="133ee-947">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="133ee-948">Por lo tanto, los contables de coste sabrán que este coste se debe asignar.</span><span class="sxs-lookup"><span data-stu-id="133ee-948">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="133ee-949">En contabilidad de costes, los costes fluyen en las unidades organizativas y los niveles en función de las directivas y las reglas que se aplican.</span><span class="sxs-lookup"><span data-stu-id="133ee-949">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="133ee-950">Cada coste se ha asociado con una base de asignación que proporciona la mejor evaluación para la asignación de costes.</span><span class="sxs-lookup"><span data-stu-id="133ee-950">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="133ee-951">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-951">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="133ee-952">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="133ee-952">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="133ee-953">Total</span><span class="sxs-lookup"><span data-stu-id="133ee-953">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="133ee-954">CC099</span><span class="sxs-lookup"><span data-stu-id="133ee-954">CC099</span></span></th>
<th><span data-ttu-id="133ee-955">CC001</span><span class="sxs-lookup"><span data-stu-id="133ee-955">CC001</span></span></th>
<th><span data-ttu-id="133ee-956">CC002</span><span class="sxs-lookup"><span data-stu-id="133ee-956">CC002</span></span></th>
<th><span data-ttu-id="133ee-957">CC003</span><span class="sxs-lookup"><span data-stu-id="133ee-957">CC003</span></span></th>
<th><span data-ttu-id="133ee-958">CC004</span><span class="sxs-lookup"><span data-stu-id="133ee-958">CC004</span></span></th>
<th><span data-ttu-id="133ee-959">Proy 1</span><span class="sxs-lookup"><span data-stu-id="133ee-959">Proj 1</span></span></th>
<th><span data-ttu-id="133ee-960">Proy 2</span><span class="sxs-lookup"><span data-stu-id="133ee-960">Proj 2</span></span></th>
<th><span data-ttu-id="133ee-961">Prod 1</span><span class="sxs-lookup"><span data-stu-id="133ee-961">Prod 1</span></span></th>
<th><span data-ttu-id="133ee-962">Prod 2</span><span class="sxs-lookup"><span data-stu-id="133ee-962">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="133ee-963">10001 Electricidad</span><span class="sxs-lookup"><span data-stu-id="133ee-963">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="133ee-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-965"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="133ee-965"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-966"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="133ee-966"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-967"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="133ee-967"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="133ee-968"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="133ee-968"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-969"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="133ee-969"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-970"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="133ee-970"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-971"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="133ee-971"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-972"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="133ee-972"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="133ee-973">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="133ee-973">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-974">0,00</span><span class="sxs-lookup"><span data-stu-id="133ee-974">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="133ee-975">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="133ee-975">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-976">0,00</span><span class="sxs-lookup"><span data-stu-id="133ee-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-977">0,00</span><span class="sxs-lookup"><span data-stu-id="133ee-977">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-978">0,00</span><span class="sxs-lookup"><span data-stu-id="133ee-978">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-979">0,00</span><span class="sxs-lookup"><span data-stu-id="133ee-979">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-980">0,00</span><span class="sxs-lookup"><span data-stu-id="133ee-980">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="133ee-981">776.36</span><span class="sxs-lookup"><span data-stu-id="133ee-981">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-982">223.64</span><span class="sxs-lookup"><span data-stu-id="133ee-982">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-983"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="133ee-983"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="133ee-984">Coste variable</span><span class="sxs-lookup"><span data-stu-id="133ee-984">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-985">000</span><span class="sxs-lookup"><span data-stu-id="133ee-985">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-986">0,00</span><span class="sxs-lookup"><span data-stu-id="133ee-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-987">0,00</span><span class="sxs-lookup"><span data-stu-id="133ee-987">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-988">0,00</span><span class="sxs-lookup"><span data-stu-id="133ee-988">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-989">0,00</span><span class="sxs-lookup"><span data-stu-id="133ee-989">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-990">30,00</span><span class="sxs-lookup"><span data-stu-id="133ee-990">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-991">10,00</span><span class="sxs-lookup"><span data-stu-id="133ee-991">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-992">6,994.21</span><span class="sxs-lookup"><span data-stu-id="133ee-992">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-993">1,965.79</span><span class="sxs-lookup"><span data-stu-id="133ee-993">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="133ee-994"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="133ee-994"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="133ee-995">Este tema muestra cómo un artículo de costes principales, 10001 Electricidad, fluye por los objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="133ee-995">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="133ee-996">Por tanto, estos gastos generales se asignan al nivel más bajo de la organización.</span><span class="sxs-lookup"><span data-stu-id="133ee-996">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="133ee-997">Es decir, los objetos de coste del nivel más bajo son los que soportan el coste.</span><span class="sxs-lookup"><span data-stu-id="133ee-997">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="133ee-998">Si necesita un flujo visual del coste entre los objetos de coste, puede usar las reglas de directivas de acumulación de costes para visualizar el flujo del coste.</span><span class="sxs-lookup"><span data-stu-id="133ee-998">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="133ee-999">Para obtener información detallada, consulte la política de acumulación de costes.</span><span class="sxs-lookup"><span data-stu-id="133ee-999">For more detailed information, see Cost roll-up policy.</span></span> <span data-ttu-id="133ee-1000">(Tenga en cuenta que este tema no se ha completado aún, pero pronto se abordará).</span><span class="sxs-lookup"><span data-stu-id="133ee-1000">(Note that this topic isn't competed yet but is coming soon.)</span></span>




