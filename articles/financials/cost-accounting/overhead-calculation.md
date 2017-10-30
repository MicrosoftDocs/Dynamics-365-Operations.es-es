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
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: e57db8f4b692aa9c27916625897e268f63031782
ms.openlocfilehash: 285799d70a945c2dae1e3c65296282d5c432a243
ms.contentlocale: es-es
ms.lasthandoff: 10/30/2017

---

# <a name="overhead-calculation"></a><span data-ttu-id="4df34-103">Cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="4df34-103">Overhead calculation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="4df34-104">Este tema describe los procesos típicos para calcular y asignar costes generales.</span><span class="sxs-lookup"><span data-stu-id="4df34-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="4df34-105">Definición del término</span><span class="sxs-lookup"><span data-stu-id="4df34-105">Term definition</span></span>
---------------

<span data-ttu-id="4df34-106">Los costes generales son costes que se contraen para dirigir un negocio, pero que no pueden ser atribuidos directamente a ninguna actividad empresarial, productos, o servicio específicos.</span><span class="sxs-lookup"><span data-stu-id="4df34-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="4df34-107">Los costes generales proporcionan un soporte fundamental a la generación de actividades rentables.</span><span class="sxs-lookup"><span data-stu-id="4df34-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="4df34-108">Algunos ejemplos de costes generales son:</span><span class="sxs-lookup"><span data-stu-id="4df34-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="4df34-109">Alquiler</span><span class="sxs-lookup"><span data-stu-id="4df34-109">Rent</span></span>
-   <span data-ttu-id="4df34-110">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-110">Electricity</span></span>
-   <span data-ttu-id="4df34-111">Sueldos administrativos</span><span class="sxs-lookup"><span data-stu-id="4df34-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="4df34-112">Visión general del cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="4df34-112">Overhead calculation overview</span></span>
<span data-ttu-id="4df34-113">El cálculo de costes generales ejecuta las directivas de contabilidad de costes en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="4df34-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="4df34-114">Puede calcular varias veces los costes generales del mismo período fiscal si se han cambiado las directivas de contabilidad de costes o se han detectado errores específicos.</span><span class="sxs-lookup"><span data-stu-id="4df34-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="4df34-115">Cada ejecución del cálculo de costes generales se almacena y recibe un identificador de versión único que permite comparar los cálculos de diferentes versiones.</span><span class="sxs-lookup"><span data-stu-id="4df34-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="4df34-116">Las entradas de costes que el cálculo de costes generales genera reciben una fecha de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="4df34-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="4df34-117">Esta fecha de contabilidad coincide con la fecha final del período fiscal que se usa en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="4df34-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="4df34-118">El identificador de versión único consiste en los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4df34-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="4df34-119">Tipo de versión</span><span class="sxs-lookup"><span data-stu-id="4df34-119">Version type</span></span>
-   <span data-ttu-id="4df34-120">Fecha y hora</span><span class="sxs-lookup"><span data-stu-id="4df34-120">Date and time</span></span>
-   <span data-ttu-id="4df34-121">Libro mayor de contabilidad de costes</span><span class="sxs-lookup"><span data-stu-id="4df34-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="4df34-122">Ejercicio</span><span class="sxs-lookup"><span data-stu-id="4df34-122">Fiscal year</span></span>
-   <span data-ttu-id="4df34-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="4df34-123">Fiscal period</span></span>

<span data-ttu-id="4df34-124">El cálculo de costes generales se ejecuta independientemente de la versión.</span><span class="sxs-lookup"><span data-stu-id="4df34-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="4df34-125">Por lo tanto, puede calcular la versión de presupuesto antes que la versión real.</span><span class="sxs-lookup"><span data-stu-id="4df34-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="4df34-126">El cálculo de costes generales consta de cuatro pasos, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="4df34-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="4df34-127">En cada paso, se crea una cabecera de diario que tiene entradas del diario.</span><span class="sxs-lookup"><span data-stu-id="4df34-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="4df34-128">Esta cabecera de diario guarda los datos de entrada para cada paso de cálculo.</span><span class="sxs-lookup"><span data-stu-id="4df34-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="4df34-129">Las directivas y las reglas se aplican a cada línea de diario, y las entradas de coste se generan como resultado.</span><span class="sxs-lookup"><span data-stu-id="4df34-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="4df34-130">Por tanto, siempre se tiene rastreabilidad completa.</span><span class="sxs-lookup"><span data-stu-id="4df34-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="4df34-131">[![Cálculo de costes generales](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="4df34-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="4df34-132">Calcular y asignar costes generales de electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="4df34-133">En la contabilidad financiera, algunos costes, como la electricidad, se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="4df34-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="4df34-134">Por lo tanto, no se proporciona una visión de gestión detallada para la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="4df34-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="4df34-135">En contabilidad de costes, para proporcionar información de gestión correcta en todas las unidades y niveles organizativos, los costes deben fluir por las unidades organizativas.</span><span class="sxs-lookup"><span data-stu-id="4df34-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="4df34-136">Este flujo se debe basar en cualquier registro preciso de consumo o en una evaluación justa.</span><span class="sxs-lookup"><span data-stu-id="4df34-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="4df34-137">En la contabilidad general, un coste de la electricidad se puede registrar como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="4df34-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4df34-138">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="4df34-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="4df34-139">Centro de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="4df34-140">Cuenta principal</span><span class="sxs-lookup"><span data-stu-id="4df34-140">Main account</span></span></th>
<th><span data-ttu-id="4df34-141">Importe en la divisa de contabilidad</span><span class="sxs-lookup"><span data-stu-id="4df34-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-142">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="4df34-143">CC099</span><span class="sxs-lookup"><span data-stu-id="4df34-143">CC099</span></span></td>
<td><span data-ttu-id="4df34-144">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="4df34-144">Default cost center</span></span></td>
<td><span data-ttu-id="4df34-145">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-145">10001</span></span></td>
<td><span data-ttu-id="4df34-146">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-146">Electricity</span></span></td>
<td><span data-ttu-id="4df34-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="4df34-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="4df34-148">Paso 1: Procese el cálculo del comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="4df34-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="4df34-149">De forma predeterminada, cuando las entradas de coste se importan de los datos de origen, reciben la clasificación de comportamiento del coste **Sin ordenar** en la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="4df34-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="4df34-150">Aplicando reglas de directivas de comportamiento de coste, puede reclasificar entradas de coste como **Coste fijo** o **Coste variable**.</span><span class="sxs-lookup"><span data-stu-id="4df34-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="4df34-151">Defina la regla de comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="4df34-151">Define the cost behavior rule</span></span>

<span data-ttu-id="4df34-152">En algunos casos, parte del coste es una cuota fija, y el coste pendiente se basa en el consumo.</span><span class="sxs-lookup"><span data-stu-id="4df34-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="4df34-153">Las facturas de electricidad coinciden a menudo con esta definición.</span><span class="sxs-lookup"><span data-stu-id="4df34-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="4df34-154">Tras pagar una cuota fija específica, paga el consumo por kilovatio-hora (Kwh).</span><span class="sxs-lookup"><span data-stu-id="4df34-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="4df34-155">Por ejemplo, si la cuota de coste fijo es de 1.000,00, la regla de comportamiento del coste se define como sigue:</span><span class="sxs-lookup"><span data-stu-id="4df34-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="4df34-156">Importe fijo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="4df34-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="4df34-157">0 &lt;= 1.000,00 = Fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="4df34-158">1.000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="4df34-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="4df34-159">Diario</span><span class="sxs-lookup"><span data-stu-id="4df34-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4df34-160">Diario</span><span class="sxs-lookup"><span data-stu-id="4df34-160">Journal</span></span></th>
<th><span data-ttu-id="4df34-161">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="4df34-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="4df34-162">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="4df34-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="4df34-163">Versión</span><span class="sxs-lookup"><span data-stu-id="4df34-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-164">00001</span><span class="sxs-lookup"><span data-stu-id="4df34-164">00001</span></span></td>
<td><span data-ttu-id="4df34-165">Diario de cálculo de comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4df34-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="4df34-166">Fiscal</span><span class="sxs-lookup"><span data-stu-id="4df34-166">Fiscal</span></span></td>
<td><span data-ttu-id="4df34-167">2017</span><span class="sxs-lookup"><span data-stu-id="4df34-167">2017</span></span></td>
<td><span data-ttu-id="4df34-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="4df34-168">Period 1</span></span></td>
<td><span data-ttu-id="4df34-169">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="4df34-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="4df34-170">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="4df34-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4df34-171">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="4df34-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="4df34-172">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4df34-173">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-173">Cost element</span></span></th>
<th><span data-ttu-id="4df34-174">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4df34-174">Cost behavior</span></span></th>
<th><span data-ttu-id="4df34-175">Importe</span><span class="sxs-lookup"><span data-stu-id="4df34-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-176">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="4df34-177">CC099</span><span class="sxs-lookup"><span data-stu-id="4df34-177">CC099</span></span></td>
<td><span data-ttu-id="4df34-178">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="4df34-178">Default cost center</span></span></td>
<td><span data-ttu-id="4df34-179">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-179">10001</span></span></td>
<td><span data-ttu-id="4df34-180">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-180">Electricity</span></span></td>
<td><span data-ttu-id="4df34-181">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="4df34-181">Unclassified</span></span></td>
<td><span data-ttu-id="4df34-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="4df34-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="4df34-183">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="4df34-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4df34-184">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4df34-185">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-185">Cost element</span></span></th>
<th><span data-ttu-id="4df34-186">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4df34-186">Cost behavior</span></span></th>
<th><span data-ttu-id="4df34-187">Importe</span><span class="sxs-lookup"><span data-stu-id="4df34-187">Amount</span></span></th>
<th><span data-ttu-id="4df34-188">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="4df34-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-189">CC099</span><span class="sxs-lookup"><span data-stu-id="4df34-189">CC099</span></span></td>
<td><span data-ttu-id="4df34-190">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="4df34-190">Default cost center</span></span></td>
<td><span data-ttu-id="4df34-191">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-191">10001</span></span></td>
<td><span data-ttu-id="4df34-192">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-192">Electricity</span></span></td>
<td><span data-ttu-id="4df34-193">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="4df34-193">Unclassified</span></span></td>
<td><span data-ttu-id="4df34-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="4df34-194">10,000.00</span></span></td>
<td><span data-ttu-id="4df34-195">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-196">CC099</span><span class="sxs-lookup"><span data-stu-id="4df34-196">CC099</span></span></td>
<td><span data-ttu-id="4df34-197">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="4df34-197">Default cost center</span></span></td>
<td><span data-ttu-id="4df34-198">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-198">10001</span></span></td>
<td><span data-ttu-id="4df34-199">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-199">Electricity</span></span></td>
<td><span data-ttu-id="4df34-200">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="4df34-200">Unclassified</span></span></td>
<td><span data-ttu-id="4df34-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="4df34-201">-10,000.00</span></span></td>
<td><span data-ttu-id="4df34-202">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-203">CC099</span><span class="sxs-lookup"><span data-stu-id="4df34-203">CC099</span></span></td>
<td><span data-ttu-id="4df34-204">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="4df34-204">Default cost center</span></span></td>
<td><span data-ttu-id="4df34-205">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-205">10001</span></span></td>
<td><span data-ttu-id="4df34-206">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-206">Electricity</span></span></td>
<td><span data-ttu-id="4df34-207">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-207">Fixed cost</span></span></td>
<td><span data-ttu-id="4df34-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="4df34-208">1,000.00</span></span></td>
<td><span data-ttu-id="4df34-209">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-210">CC099</span><span class="sxs-lookup"><span data-stu-id="4df34-210">CC099</span></span></td>
<td><span data-ttu-id="4df34-211">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="4df34-211">Default cost center</span></span></td>
<td><span data-ttu-id="4df34-212">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-212">10001</span></span></td>
<td><span data-ttu-id="4df34-213">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-213">Electricity</span></span></td>
<td><span data-ttu-id="4df34-214">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-214">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="4df34-215">9,000.00</span></span></td>
<td><span data-ttu-id="4df34-216">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4df34-217">Para obtener información detallada sobre el comportamiento del coste, consulte Directiva de comportamiento de costes.</span><span class="sxs-lookup"><span data-stu-id="4df34-217">For detailed information about cost behavior, see Cost behavior policy.</span></span> <span data-ttu-id="4df34-218">(Tenga en cuenta que este tema no se ha completado aún, pero pronto se abordará).</span><span class="sxs-lookup"><span data-stu-id="4df34-218">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="4df34-219">Paso 2: Procese el cálculo de distribución de costes</span><span class="sxs-lookup"><span data-stu-id="4df34-219">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="4df34-220">La distribución de costes se usa para redistribuir costes desde un objeto de coste a uno o más objetos de coste aplicando una base relevante de la asignación.</span><span class="sxs-lookup"><span data-stu-id="4df34-220">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="4df34-221">La distribución de costes y la asignación de costes difieren en que la distribución de costes siempre se produce en el nivel de elemento de costes principal del coste original.</span><span class="sxs-lookup"><span data-stu-id="4df34-221">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="4df34-222">Defina la regla de distribución del coste</span><span class="sxs-lookup"><span data-stu-id="4df34-222">Define the cost distribution rule</span></span>

<span data-ttu-id="4df34-223">En la contabilidad financiera, los costes de electricidad se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="4df34-223">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="4df34-224">En contabilidad de costes, este método no es suficientemente detallado.</span><span class="sxs-lookup"><span data-stu-id="4df34-224">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="4df34-225">El coste variable debe distribuirse a los objetos individuales de coste aplicando una base justa.</span><span class="sxs-lookup"><span data-stu-id="4df34-225">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="4df34-226">La base de asignación más lógica es el consumo de electricidad (Kwh).</span><span class="sxs-lookup"><span data-stu-id="4df34-226">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="4df34-227">Se crea un miembro de dimensión estadística que se denomina Electricity, y se registra el consumo de electricidad.</span><span class="sxs-lookup"><span data-stu-id="4df34-227">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="4df34-228">De forma predeterminada, todos los miembros de dimensión estadísticos estarán disponibles como bases de asignación.</span><span class="sxs-lookup"><span data-stu-id="4df34-228">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4df34-229">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-229">Cost object</span></span></th>
<th><span data-ttu-id="4df34-230">Kwh</span><span class="sxs-lookup"><span data-stu-id="4df34-230">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-231">CC001</span><span class="sxs-lookup"><span data-stu-id="4df34-231">CC001</span></span></td>
<td><span data-ttu-id="4df34-232">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="4df34-232">HR</span></span></td>
<td><span data-ttu-id="4df34-233">1.000</span><span class="sxs-lookup"><span data-stu-id="4df34-233">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-234">CC002</span><span class="sxs-lookup"><span data-stu-id="4df34-234">CC002</span></span></td>
<td><span data-ttu-id="4df34-235">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4df34-235">Finance</span></span></td>
<td><span data-ttu-id="4df34-236">6.000</span><span class="sxs-lookup"><span data-stu-id="4df34-236">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-237">CC003</span><span class="sxs-lookup"><span data-stu-id="4df34-237">CC003</span></span></td>
<td><span data-ttu-id="4df34-238">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4df34-238">Assembly</span></span></td>
<td><span data-ttu-id="4df34-239">0</span><span class="sxs-lookup"><span data-stu-id="4df34-239">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4df34-240">La tabla siguiente muestra el resultado cuando se aplica el consumo de electricidad como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="4df34-240">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4df34-241">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-241">Cost object</span></span></th>
<th><span data-ttu-id="4df34-242">Magnitud</span><span class="sxs-lookup"><span data-stu-id="4df34-242">Magnitude</span></span></th>
<th><span data-ttu-id="4df34-243">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="4df34-243">Allocation factor</span></span></th>
<th><span data-ttu-id="4df34-244">Importe</span><span class="sxs-lookup"><span data-stu-id="4df34-244">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-245">CC001</span><span class="sxs-lookup"><span data-stu-id="4df34-245">CC001</span></span></td>
<td><span data-ttu-id="4df34-246">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="4df34-246">HR</span></span></td>
<td><span data-ttu-id="4df34-247">1.000</span><span class="sxs-lookup"><span data-stu-id="4df34-247">1,000</span></span></td>
<td><span data-ttu-id="4df34-248">(1.000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="4df34-248">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="4df34-249">1,285.71</span><span class="sxs-lookup"><span data-stu-id="4df34-249">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-250">CC002</span><span class="sxs-lookup"><span data-stu-id="4df34-250">CC002</span></span></td>
<td><span data-ttu-id="4df34-251">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4df34-251">Finance</span></span></td>
<td><span data-ttu-id="4df34-252">6.000</span><span class="sxs-lookup"><span data-stu-id="4df34-252">6,000</span></span></td>
<td><span data-ttu-id="4df34-253">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="4df34-253">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="4df34-254">7,714.29</span><span class="sxs-lookup"><span data-stu-id="4df34-254">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-255">CC003</span><span class="sxs-lookup"><span data-stu-id="4df34-255">CC003</span></span></td>
<td><span data-ttu-id="4df34-256">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4df34-256">Assembly</span></span></td>
<td><span data-ttu-id="4df34-257">0</span><span class="sxs-lookup"><span data-stu-id="4df34-257">0</span></span></td>
<td><span data-ttu-id="4df34-258">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="4df34-258">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="4df34-259">0,00</span><span class="sxs-lookup"><span data-stu-id="4df34-259">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4df34-260">El coste fijo debe distribuirse uniformemente a los objetos individuales de costes que han consumido electricidad.</span><span class="sxs-lookup"><span data-stu-id="4df34-260">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="4df34-261">Puede obtener este resultado usando el miembro de dimensión estadístico de electricidad en una base de asignación de la fórmula: (Electricidad &gt; 0,00) La tabla siguiente muestra el resultado cuando el consumo de electricidad se aplica como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="4df34-261">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4df34-262">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-262">Cost object</span></span></th>
<th><span data-ttu-id="4df34-263">Fórmula</span><span class="sxs-lookup"><span data-stu-id="4df34-263">Formula</span></span></th>
<th><span data-ttu-id="4df34-264">Magnitud</span><span class="sxs-lookup"><span data-stu-id="4df34-264">Magnitude</span></span></th>
<th><span data-ttu-id="4df34-265">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="4df34-265">Allocation factor</span></span></th>
<th><span data-ttu-id="4df34-266">Importe</span><span class="sxs-lookup"><span data-stu-id="4df34-266">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-267">CC001</span><span class="sxs-lookup"><span data-stu-id="4df34-267">CC001</span></span></td>
<td><span data-ttu-id="4df34-268">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="4df34-268">HR</span></span></td>
<td><span data-ttu-id="4df34-269">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="4df34-269">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="4df34-270">1</span><span class="sxs-lookup"><span data-stu-id="4df34-270">1</span></span></td>
<td><span data-ttu-id="4df34-271">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="4df34-271">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="4df34-272">500,00</span><span class="sxs-lookup"><span data-stu-id="4df34-272">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-273">CC002</span><span class="sxs-lookup"><span data-stu-id="4df34-273">CC002</span></span></td>
<td><span data-ttu-id="4df34-274">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4df34-274">Finance</span></span></td>
<td><span data-ttu-id="4df34-275">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="4df34-275">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="4df34-276">1</span><span class="sxs-lookup"><span data-stu-id="4df34-276">1</span></span></td>
<td><span data-ttu-id="4df34-277">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="4df34-277">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="4df34-278">500,00</span><span class="sxs-lookup"><span data-stu-id="4df34-278">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-279">CC003</span><span class="sxs-lookup"><span data-stu-id="4df34-279">CC003</span></span></td>
<td><span data-ttu-id="4df34-280">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4df34-280">Assembly</span></span></td>
<td><span data-ttu-id="4df34-281">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="4df34-281">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="4df34-282">0</span><span class="sxs-lookup"><span data-stu-id="4df34-282">0</span></span></td>
<td><span data-ttu-id="4df34-283">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="4df34-283">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="4df34-284">0,00</span><span class="sxs-lookup"><span data-stu-id="4df34-284">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="4df34-285">Diario</span><span class="sxs-lookup"><span data-stu-id="4df34-285">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4df34-286">Diario</span><span class="sxs-lookup"><span data-stu-id="4df34-286">Journal</span></span></th>
<th><span data-ttu-id="4df34-287">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="4df34-287">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="4df34-288">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="4df34-288">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="4df34-289">Versión</span><span class="sxs-lookup"><span data-stu-id="4df34-289">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-290">00002</span><span class="sxs-lookup"><span data-stu-id="4df34-290">00002</span></span></td>
<td><span data-ttu-id="4df34-291">Diario de cálculo de la distribución de costes</span><span class="sxs-lookup"><span data-stu-id="4df34-291">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="4df34-292">Fiscal</span><span class="sxs-lookup"><span data-stu-id="4df34-292">Fiscal</span></span></td>
<td><span data-ttu-id="4df34-293">2017</span><span class="sxs-lookup"><span data-stu-id="4df34-293">2017</span></span></td>
<td><span data-ttu-id="4df34-294">Período 1</span><span class="sxs-lookup"><span data-stu-id="4df34-294">Period 1</span></span></td>
<td><span data-ttu-id="4df34-295">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="4df34-295">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="4df34-296">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="4df34-296">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4df34-297">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="4df34-297">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="4df34-298">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-298">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4df34-299">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-299">Cost element</span></span></th>
<th><span data-ttu-id="4df34-300">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4df34-300">Cost behavior</span></span></th>
<th><span data-ttu-id="4df34-301">Importe</span><span class="sxs-lookup"><span data-stu-id="4df34-301">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-302">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-302">January 31, 2017</span></span></td>
<td><span data-ttu-id="4df34-303">CC099</span><span class="sxs-lookup"><span data-stu-id="4df34-303">CC099</span></span></td>
<td><span data-ttu-id="4df34-304">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="4df34-304">Default cost center</span></span></td>
<td><span data-ttu-id="4df34-305">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-305">10001</span></span></td>
<td><span data-ttu-id="4df34-306">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-306">Electricity</span></span></td>
<td><span data-ttu-id="4df34-307">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-307">Fixed cost</span></span></td>
<td><span data-ttu-id="4df34-308">1.000,00</span><span class="sxs-lookup"><span data-stu-id="4df34-308">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-309">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-309">January 31, 2017</span></span></td>
<td><span data-ttu-id="4df34-310">CC099</span><span class="sxs-lookup"><span data-stu-id="4df34-310">CC099</span></span></td>
<td><span data-ttu-id="4df34-311">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="4df34-311">Default cost center</span></span></td>
<td><span data-ttu-id="4df34-312">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-312">10001</span></span></td>
<td><span data-ttu-id="4df34-313">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-313">Electricity</span></span></td>
<td><span data-ttu-id="4df34-314">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-314">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-315">9.000,00</span><span class="sxs-lookup"><span data-stu-id="4df34-315">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="4df34-316">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="4df34-316">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4df34-317">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-317">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4df34-318">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-318">Cost element</span></span></th>
<th><span data-ttu-id="4df34-319">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4df34-319">Cost behavior</span></span></th>
<th><span data-ttu-id="4df34-320">Importe</span><span class="sxs-lookup"><span data-stu-id="4df34-320">Amount</span></span></th>
<th><span data-ttu-id="4df34-321">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="4df34-321">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-322">CC099</span><span class="sxs-lookup"><span data-stu-id="4df34-322">CC099</span></span></td>
<td><span data-ttu-id="4df34-323">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="4df34-323">Default cost center</span></span></td>
<td><span data-ttu-id="4df34-324">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-324">10001</span></span></td>
<td><span data-ttu-id="4df34-325">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-325">Electricity</span></span></td>
<td><span data-ttu-id="4df34-326">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-326">Fixed cost</span></span></td>
<td><span data-ttu-id="4df34-327">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="4df34-327">-1,000.00</span></span></td>
<td><span data-ttu-id="4df34-328">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-328">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-329">CC001</span><span class="sxs-lookup"><span data-stu-id="4df34-329">CC001</span></span></td>
<td><span data-ttu-id="4df34-330">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="4df34-330">HR</span></span></td>
<td><span data-ttu-id="4df34-331">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-331">10001</span></span></td>
<td><span data-ttu-id="4df34-332">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-332">Electricity</span></span></td>
<td><span data-ttu-id="4df34-333">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-333">Fixed cost</span></span></td>
<td><span data-ttu-id="4df34-334">500,00</span><span class="sxs-lookup"><span data-stu-id="4df34-334">500.00</span></span></td>
<td><span data-ttu-id="4df34-335">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-335">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-336">CC002</span><span class="sxs-lookup"><span data-stu-id="4df34-336">CC002</span></span></td>
<td><span data-ttu-id="4df34-337">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4df34-337">Finance</span></span></td>
<td><span data-ttu-id="4df34-338">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-338">10001</span></span></td>
<td><span data-ttu-id="4df34-339">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-339">Electricity</span></span></td>
<td><span data-ttu-id="4df34-340">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-340">Fixed cost</span></span></td>
<td><span data-ttu-id="4df34-341">500,00</span><span class="sxs-lookup"><span data-stu-id="4df34-341">500.00</span></span></td>
<td><span data-ttu-id="4df34-342">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-342">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-343">CC099</span><span class="sxs-lookup"><span data-stu-id="4df34-343">CC099</span></span></td>
<td><span data-ttu-id="4df34-344">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="4df34-344">Default cost center</span></span></td>
<td><span data-ttu-id="4df34-345">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-345">10001</span></span></td>
<td><span data-ttu-id="4df34-346">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-346">Electricity</span></span></td>
<td><span data-ttu-id="4df34-347">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-347">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-348">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="4df34-348">-9,000.00</span></span></td>
<td><span data-ttu-id="4df34-349">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-349">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-350">CC001</span><span class="sxs-lookup"><span data-stu-id="4df34-350">CC001</span></span></td>
<td><span data-ttu-id="4df34-351">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="4df34-351">HR</span></span></td>
<td><span data-ttu-id="4df34-352">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-352">10001</span></span></td>
<td><span data-ttu-id="4df34-353">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-353">Electricity</span></span></td>
<td><span data-ttu-id="4df34-354">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-354">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-355">1,285.71</span><span class="sxs-lookup"><span data-stu-id="4df34-355">1,285.71</span></span></td>
<td><span data-ttu-id="4df34-356">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-356">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-357">CC002</span><span class="sxs-lookup"><span data-stu-id="4df34-357">CC002</span></span></td>
<td><span data-ttu-id="4df34-358">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4df34-358">Finance</span></span></td>
<td><span data-ttu-id="4df34-359">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-359">10001</span></span></td>
<td><span data-ttu-id="4df34-360">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-360">Electricity</span></span></td>
<td><span data-ttu-id="4df34-361">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-361">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-362">7,714.29</span><span class="sxs-lookup"><span data-stu-id="4df34-362">7,714.29</span></span></td>
<td><span data-ttu-id="4df34-363">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-363">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4df34-364">Para obtener información detallada sobre la distribución de costes y las bases de asignación, consulte la directiva de distribución de costes y las bases de asignación.</span><span class="sxs-lookup"><span data-stu-id="4df34-364">For detailed information about cost distribution and allocation bases, see Cost distribution policy and Allocation bases.</span></span> <span data-ttu-id="4df34-365">(Tenga en cuenta que este tema no se ha completado aún, pero pronto se abordará).</span><span class="sxs-lookup"><span data-stu-id="4df34-365">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="4df34-366">Paso 3: Procese el cálculo de las tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="4df34-366">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="4df34-367">La tasa de costes generales se usa para cargar uno o varios objetos de coste específicos.</span><span class="sxs-lookup"><span data-stu-id="4df34-367">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="4df34-368">El cargo se basa en un índice de coste predeterminado y la magnitud de la base de asignación asignada.</span><span class="sxs-lookup"><span data-stu-id="4df34-368">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="4df34-369">Defina la tasa de costes generales</span><span class="sxs-lookup"><span data-stu-id="4df34-369">Define the overhead rate</span></span>

<span data-ttu-id="4df34-370">El objeto de coste CC001 HR contribuye a un conjunto de proyectos internos.</span><span class="sxs-lookup"><span data-stu-id="4df34-370">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="4df34-371">Se crea un miembro de dimensión estadística que se denomina proyectos HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="4df34-371">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4df34-372">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-372">Cost object</span></span></th>
<th><span data-ttu-id="4df34-373">Horas</span><span class="sxs-lookup"><span data-stu-id="4df34-373">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-374">Proy 1</span><span class="sxs-lookup"><span data-stu-id="4df34-374">Proj 1</span></span></td>
<td><span data-ttu-id="4df34-375">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="4df34-375">Project 1</span></span></td>
<td><span data-ttu-id="4df34-376">3</span><span class="sxs-lookup"><span data-stu-id="4df34-376">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-377">Proy 2</span><span class="sxs-lookup"><span data-stu-id="4df34-377">Proj 2</span></span></td>
<td><span data-ttu-id="4df34-378">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="4df34-378">Project 2</span></span></td>
<td><span data-ttu-id="4df34-379">1</span><span class="sxs-lookup"><span data-stu-id="4df34-379">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4df34-380">Una tasa de coste predeterminada para la contribución de los proyectos de coste se ha definido.</span><span class="sxs-lookup"><span data-stu-id="4df34-380">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4df34-381">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-381">Cost object</span></span></th>
<th><span data-ttu-id="4df34-382">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-382">Cost element</span></span></th>
<th><span data-ttu-id="4df34-383">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4df34-383">Cost behavior</span></span></th>
<th><span data-ttu-id="4df34-384">Unidades</span><span class="sxs-lookup"><span data-stu-id="4df34-384">Units</span></span></th>
<th><span data-ttu-id="4df34-385">Índice</span><span class="sxs-lookup"><span data-stu-id="4df34-385">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-386">CC001</span><span class="sxs-lookup"><span data-stu-id="4df34-386">CC001</span></span></td>
<td><span data-ttu-id="4df34-387">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="4df34-387">HR</span></span></td>
<td><span data-ttu-id="4df34-388">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-388">10001</span></span></td>
<td><span data-ttu-id="4df34-389">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-389">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-390">1</span><span class="sxs-lookup"><span data-stu-id="4df34-390">1</span></span></td>
<td><span data-ttu-id="4df34-391">10</span><span class="sxs-lookup"><span data-stu-id="4df34-391">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4df34-392">La tabla siguiente muestra el resultado cuando los proyectos HR se aplican como base de la asignación.</span><span class="sxs-lookup"><span data-stu-id="4df34-392">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4df34-393">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-393">Cost object</span></span></th>
<th><span data-ttu-id="4df34-394">Magnitud</span><span class="sxs-lookup"><span data-stu-id="4df34-394">Magnitude</span></span></th>
<th><span data-ttu-id="4df34-395">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-395">Cost element</span></span></th>
<th><span data-ttu-id="4df34-396">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="4df34-396">Allocation factor</span></span></th>
<th><span data-ttu-id="4df34-397">Importe</span><span class="sxs-lookup"><span data-stu-id="4df34-397">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-398">Proy 1</span><span class="sxs-lookup"><span data-stu-id="4df34-398">Proj 1</span></span></td>
<td><span data-ttu-id="4df34-399">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="4df34-399">Project 1</span></span></td>
<td><span data-ttu-id="4df34-400">3</span><span class="sxs-lookup"><span data-stu-id="4df34-400">3</span></span></td>
<td><span data-ttu-id="4df34-401">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-401">10001</span></span></td>
<td><span data-ttu-id="4df34-402">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="4df34-402">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="4df34-403">30,00</span><span class="sxs-lookup"><span data-stu-id="4df34-403">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-404">Proy 2</span><span class="sxs-lookup"><span data-stu-id="4df34-404">Proj 2</span></span></td>
<td><span data-ttu-id="4df34-405">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="4df34-405">Project 2</span></span></td>
<td><span data-ttu-id="4df34-406">1</span><span class="sxs-lookup"><span data-stu-id="4df34-406">1</span></span></td>
<td><span data-ttu-id="4df34-407">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-407">10001</span></span></td>
<td><span data-ttu-id="4df34-408">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="4df34-408">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="4df34-409">10,00</span><span class="sxs-lookup"><span data-stu-id="4df34-409">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="4df34-410">Diario</span><span class="sxs-lookup"><span data-stu-id="4df34-410">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4df34-411">Diario</span><span class="sxs-lookup"><span data-stu-id="4df34-411">Journal</span></span></th>
<th><span data-ttu-id="4df34-412">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="4df34-412">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="4df34-413">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="4df34-413">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="4df34-414">Versión</span><span class="sxs-lookup"><span data-stu-id="4df34-414">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-415">00003</span><span class="sxs-lookup"><span data-stu-id="4df34-415">00003</span></span></td>
<td><span data-ttu-id="4df34-416">Diario de cálculo de tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="4df34-416">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="4df34-417">Fiscal</span><span class="sxs-lookup"><span data-stu-id="4df34-417">Fiscal</span></span></td>
<td><span data-ttu-id="4df34-418">2017</span><span class="sxs-lookup"><span data-stu-id="4df34-418">2017</span></span></td>
<td><span data-ttu-id="4df34-419">Período 1</span><span class="sxs-lookup"><span data-stu-id="4df34-419">Period 1</span></span></td>
<td><span data-ttu-id="4df34-420">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="4df34-420">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="4df34-421">Entradas de diario (entradas de diario para cálculo de tasas de costes generales)</span><span class="sxs-lookup"><span data-stu-id="4df34-421">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4df34-422">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="4df34-422">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="4df34-423">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-423">Cost object</span></span></th>
<th><span data-ttu-id="4df34-424">Magnitud</span><span class="sxs-lookup"><span data-stu-id="4df34-424">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-425">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-425">January 31, 2017</span></span></td>
<td><span data-ttu-id="4df34-426">Proy 1</span><span class="sxs-lookup"><span data-stu-id="4df34-426">Proj 1</span></span></td>
<td><span data-ttu-id="4df34-427">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="4df34-427">Internal Proj 1</span></span></td>
<td><span data-ttu-id="4df34-428">3,00</span><span class="sxs-lookup"><span data-stu-id="4df34-428">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-429">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-429">January 31, 2017</span></span></td>
<td><span data-ttu-id="4df34-430">Proy 2</span><span class="sxs-lookup"><span data-stu-id="4df34-430">Proj 2</span></span></td>
<td><span data-ttu-id="4df34-431">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="4df34-431">Internal Proj 2</span></span></td>
<td><span data-ttu-id="4df34-432">1,00</span><span class="sxs-lookup"><span data-stu-id="4df34-432">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="4df34-433">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="4df34-433">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4df34-434">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-434">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4df34-435">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-435">Cost element</span></span></th>
<th><span data-ttu-id="4df34-436">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4df34-436">Cost behavior</span></span></th>
<th><span data-ttu-id="4df34-437">Importe</span><span class="sxs-lookup"><span data-stu-id="4df34-437">Amount</span></span></th>
<th><span data-ttu-id="4df34-438">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="4df34-438">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-439">CC0001</span><span class="sxs-lookup"><span data-stu-id="4df34-439">CC0001</span></span></td>
<td><span data-ttu-id="4df34-440">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="4df34-440">HR</span></span></td>
<td><span data-ttu-id="4df34-441">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-441">10001</span></span></td>
<td><span data-ttu-id="4df34-442">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-442">Electricity</span></span></td>
<td><span data-ttu-id="4df34-443">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-443">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-444">-30,00</span><span class="sxs-lookup"><span data-stu-id="4df34-444">-30.00</span></span></td>
<td><span data-ttu-id="4df34-445">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-445">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-446">Proy 1</span><span class="sxs-lookup"><span data-stu-id="4df34-446">Proj 1</span></span></td>
<td><span data-ttu-id="4df34-447">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="4df34-447">Internal Proj 1</span></span></td>
<td><span data-ttu-id="4df34-448">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-448">10001</span></span></td>
<td><span data-ttu-id="4df34-449">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-449">Electricity</span></span></td>
<td><span data-ttu-id="4df34-450">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-450">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-451">30,00</span><span class="sxs-lookup"><span data-stu-id="4df34-451">30.00</span></span></td>
<td><span data-ttu-id="4df34-452">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-452">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-453">CC001</span><span class="sxs-lookup"><span data-stu-id="4df34-453">CC001</span></span></td>
<td><span data-ttu-id="4df34-454">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="4df34-454">HR</span></span></td>
<td><span data-ttu-id="4df34-455">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-455">10001</span></span></td>
<td><span data-ttu-id="4df34-456">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-456">Electricity</span></span></td>
<td><span data-ttu-id="4df34-457">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-457">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-458">-10,00</span><span class="sxs-lookup"><span data-stu-id="4df34-458">-10.00</span></span></td>
<td><span data-ttu-id="4df34-459">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-459">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-460">Proy 2</span><span class="sxs-lookup"><span data-stu-id="4df34-460">Proj 2</span></span></td>
<td><span data-ttu-id="4df34-461">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="4df34-461">Internal Proj 2</span></span></td>
<td><span data-ttu-id="4df34-462">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-462">10001</span></span></td>
<td><span data-ttu-id="4df34-463">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-463">Electricity</span></span></td>
<td><span data-ttu-id="4df34-464">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-464">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-465">10,00</span><span class="sxs-lookup"><span data-stu-id="4df34-465">10.00</span></span></td>
<td><span data-ttu-id="4df34-466">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-466">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4df34-467">Para obtener información detallada acerca de la directiva de tasa de costes generales, consulte la directiva de tasas de costes generales y las bases de asignación.</span><span class="sxs-lookup"><span data-stu-id="4df34-467">For detailed information about overhead rate policy, see Overhead rate policy and Allocation bases.</span></span> <span data-ttu-id="4df34-468">(Tenga en cuenta que este tema no se ha completado aún, pero pronto se abordará).</span><span class="sxs-lookup"><span data-stu-id="4df34-468">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="4df34-469">Paso 4: Procese el cálculo de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="4df34-469">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="4df34-470">La asignación es utilizada para asignar el saldo de un objeto de coste a otros objetos de coste aplicando una base de asignación.</span><span class="sxs-lookup"><span data-stu-id="4df34-470">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="4df34-471">Finance and Operations admite el método de asignación recíproco.</span><span class="sxs-lookup"><span data-stu-id="4df34-471">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="4df34-472">En el método de asignación recíproco, se reconocen completamente los servicios mutuos que los objetos de coste auxiliar intercambian.</span><span class="sxs-lookup"><span data-stu-id="4df34-472">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="4df34-473">El sistema determina automáticamente el orden correcto para realizar las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="4df34-473">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="4df34-474">El saldo de un objeto de coste se asigna según una única base de asignación.</span><span class="sxs-lookup"><span data-stu-id="4df34-474">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="4df34-475">Las asignaciones entre dimensiones de objetos de coste y sus miembros respectivos se admiten.</span><span class="sxs-lookup"><span data-stu-id="4df34-475">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="4df34-476">El orden de asignación se controla por unidad de control de costes.</span><span class="sxs-lookup"><span data-stu-id="4df34-476">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="4df34-477">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="4df34-477">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="4df34-478">Defina la asignación de costes</span><span class="sxs-lookup"><span data-stu-id="4df34-478">Define the cost allocation</span></span>

<span data-ttu-id="4df34-479">A continuación se indica un ejemplo sencillo que explica cómo puede realizar el seguimiento del flujo de coste.</span><span class="sxs-lookup"><span data-stu-id="4df34-479">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="4df34-480">El objeto de coste CC001 HR contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="4df34-480">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="4df34-481">Se crea un miembro de dimensión estadística que se denomina servicios HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="4df34-481">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4df34-482">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-482">Cost object</span></span></th>
<th><span data-ttu-id="4df34-483">Servicios HR</span><span class="sxs-lookup"><span data-stu-id="4df34-483">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-484">CC002</span><span class="sxs-lookup"><span data-stu-id="4df34-484">CC002</span></span></td>
<td><span data-ttu-id="4df34-485">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4df34-485">Finance</span></span></td>
<td><span data-ttu-id="4df34-486">35</span><span class="sxs-lookup"><span data-stu-id="4df34-486">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-487">CC003</span><span class="sxs-lookup"><span data-stu-id="4df34-487">CC003</span></span></td>
<td><span data-ttu-id="4df34-488">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4df34-488">Assembly</span></span></td>
<td><span data-ttu-id="4df34-489">55</span><span class="sxs-lookup"><span data-stu-id="4df34-489">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-490">CC004</span><span class="sxs-lookup"><span data-stu-id="4df34-490">CC004</span></span></td>
<td><span data-ttu-id="4df34-491">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="4df34-491">Packaging</span></span></td>
<td><span data-ttu-id="4df34-492">10</span><span class="sxs-lookup"><span data-stu-id="4df34-492">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4df34-493">El objeto de coste CC002 Finanzas contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="4df34-493">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="4df34-494">Se crea un miembro de dimensión estadística que se denomina Finanzas para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="4df34-494">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4df34-495">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-495">Cost object</span></span></th>
<th><span data-ttu-id="4df34-496">Servicios financieros</span><span class="sxs-lookup"><span data-stu-id="4df34-496">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-497">CC003</span><span class="sxs-lookup"><span data-stu-id="4df34-497">CC003</span></span></td>
<td><span data-ttu-id="4df34-498">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4df34-498">Assembly</span></span></td>
<td><span data-ttu-id="4df34-499">65</span><span class="sxs-lookup"><span data-stu-id="4df34-499">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-500">CC004</span><span class="sxs-lookup"><span data-stu-id="4df34-500">CC004</span></span></td>
<td><span data-ttu-id="4df34-501">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="4df34-501">Packaging</span></span></td>
<td><span data-ttu-id="4df34-502">35</span><span class="sxs-lookup"><span data-stu-id="4df34-502">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4df34-503">El objeto de coste CC003 Asamblea contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="4df34-503">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="4df34-504">Se crea un miembro de dimensión estadística que se denomina servicios de Asamblea para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="4df34-504">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4df34-505">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-505">Cost object</span></span></th>
<th><span data-ttu-id="4df34-506">Servicios de la asamblea (horas)</span><span class="sxs-lookup"><span data-stu-id="4df34-506">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-507">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4df34-507">Prod 1</span></span></td>
<td><span data-ttu-id="4df34-508">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4df34-508">Product 1</span></span></td>
<td><span data-ttu-id="4df34-509">60</span><span class="sxs-lookup"><span data-stu-id="4df34-509">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-510">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4df34-510">Prod 2</span></span></td>
<td><span data-ttu-id="4df34-511">Producto 2</span><span class="sxs-lookup"><span data-stu-id="4df34-511">Product 2</span></span></td>
<td><span data-ttu-id="4df34-512">20</span><span class="sxs-lookup"><span data-stu-id="4df34-512">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4df34-513">El objeto de coste CC004 Embalaje contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="4df34-513">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="4df34-514">Se crea un miembro de dimensión estadística que se denomina servicios de Embalaje para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="4df34-514">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4df34-515">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-515">Cost object</span></span></th>
<th><span data-ttu-id="4df34-516">Servicios de embalaje (horas)</span><span class="sxs-lookup"><span data-stu-id="4df34-516">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-517">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4df34-517">Prod 1</span></span></td>
<td><span data-ttu-id="4df34-518">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4df34-518">Product 1</span></span></td>
<td><span data-ttu-id="4df34-519">80</span><span class="sxs-lookup"><span data-stu-id="4df34-519">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-520">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4df34-520">Prod 2</span></span></td>
<td><span data-ttu-id="4df34-521">Producto 2</span><span class="sxs-lookup"><span data-stu-id="4df34-521">Product 2</span></span></td>
<td><span data-ttu-id="4df34-522">15</span><span class="sxs-lookup"><span data-stu-id="4df34-522">15</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4df34-523">**Nota:** En Finance and Operations, las medidas estadísticas como las horas de la producción que un producto consume se pueden deducir de los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="4df34-523">**Note:** In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="4df34-524">Para obtener información más detallada acerca de los proveedores de medidas estadísticas, consulte la plantilla de proveedor de estadísticas de medidas.</span><span class="sxs-lookup"><span data-stu-id="4df34-524">For more detailed information about statistical measure providers, see Statistical measure provider template.</span></span> <span data-ttu-id="4df34-525">(Tenga en cuenta que este tema todavía no está completado, pero que pronto lo estará). La tabla siguiente muestra el resultado cuando se aplican los servicios HR como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="4df34-525">(Note that this topic isn't completed yet but is coming soon.) The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4df34-526">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-526">Cost object</span></span></th>
<th><span data-ttu-id="4df34-527">Magnitud</span><span class="sxs-lookup"><span data-stu-id="4df34-527">Magnitude</span></span></th>
<th><span data-ttu-id="4df34-528">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="4df34-528">Allocation factor</span></span></th>
<th><span data-ttu-id="4df34-529">Importe</span><span class="sxs-lookup"><span data-stu-id="4df34-529">Amount</span></span></th>
<th><span data-ttu-id="4df34-530">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4df34-530">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-531">CC002</span><span class="sxs-lookup"><span data-stu-id="4df34-531">CC002</span></span></td>
<td><span data-ttu-id="4df34-532">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4df34-532">Finance</span></span></td>
<td><span data-ttu-id="4df34-533">35</span><span class="sxs-lookup"><span data-stu-id="4df34-533">35</span></span></td>
<td><span data-ttu-id="4df34-534">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="4df34-534">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="4df34-535">175.00</span><span class="sxs-lookup"><span data-stu-id="4df34-535">175.00</span></span></td>
<td><span data-ttu-id="4df34-536">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-536">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-537">CC003</span><span class="sxs-lookup"><span data-stu-id="4df34-537">CC003</span></span></td>
<td><span data-ttu-id="4df34-538">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4df34-538">Assembly</span></span></td>
<td><span data-ttu-id="4df34-539">55</span><span class="sxs-lookup"><span data-stu-id="4df34-539">55</span></span></td>
<td><span data-ttu-id="4df34-540">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="4df34-540">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="4df34-541">275.00</span><span class="sxs-lookup"><span data-stu-id="4df34-541">275.00</span></span></td>
<td><span data-ttu-id="4df34-542">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-542">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-543">CC004</span><span class="sxs-lookup"><span data-stu-id="4df34-543">CC004</span></span></td>
<td><span data-ttu-id="4df34-544">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="4df34-544">Packaging</span></span></td>
<td><span data-ttu-id="4df34-545">10</span><span class="sxs-lookup"><span data-stu-id="4df34-545">10</span></span></td>
<td><span data-ttu-id="4df34-546">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="4df34-546">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="4df34-547">50,00</span><span class="sxs-lookup"><span data-stu-id="4df34-547">50.00</span></span></td>
<td><span data-ttu-id="4df34-548">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-548">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-549">CC002</span><span class="sxs-lookup"><span data-stu-id="4df34-549">CC002</span></span></td>
<td><span data-ttu-id="4df34-550">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4df34-550">Finance</span></span></td>
<td><span data-ttu-id="4df34-551">35</span><span class="sxs-lookup"><span data-stu-id="4df34-551">35</span></span></td>
<td><span data-ttu-id="4df34-552">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="4df34-552">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="4df34-553">436.00</span><span class="sxs-lookup"><span data-stu-id="4df34-553">436.00</span></span></td>
<td><span data-ttu-id="4df34-554">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-554">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-555">CC003</span><span class="sxs-lookup"><span data-stu-id="4df34-555">CC003</span></span></td>
<td><span data-ttu-id="4df34-556">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4df34-556">Assembly</span></span></td>
<td><span data-ttu-id="4df34-557">55</span><span class="sxs-lookup"><span data-stu-id="4df34-557">55</span></span></td>
<td><span data-ttu-id="4df34-558">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="4df34-558">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="4df34-559">685.14</span><span class="sxs-lookup"><span data-stu-id="4df34-559">685.14</span></span></td>
<td><span data-ttu-id="4df34-560">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-560">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-561">CC004</span><span class="sxs-lookup"><span data-stu-id="4df34-561">CC004</span></span></td>
<td><span data-ttu-id="4df34-562">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="4df34-562">Packaging</span></span></td>
<td><span data-ttu-id="4df34-563">10</span><span class="sxs-lookup"><span data-stu-id="4df34-563">10</span></span></td>
<td><span data-ttu-id="4df34-564">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="4df34-564">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="4df34-565">124.57</span><span class="sxs-lookup"><span data-stu-id="4df34-565">124.57</span></span></td>
<td><span data-ttu-id="4df34-566">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-566">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4df34-567">La tabla siguiente muestra el resultado cuando se aplican los servicios de Finanzas como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="4df34-567">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4df34-568">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-568">Cost object</span></span></th>
<th><span data-ttu-id="4df34-569">Magnitud</span><span class="sxs-lookup"><span data-stu-id="4df34-569">Magnitude</span></span></th>
<th><span data-ttu-id="4df34-570">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="4df34-570">Allocation factor</span></span></th>
<th><span data-ttu-id="4df34-571">Importe</span><span class="sxs-lookup"><span data-stu-id="4df34-571">Amount</span></span></th>
<th><span data-ttu-id="4df34-572">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4df34-572">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-573">CC003</span><span class="sxs-lookup"><span data-stu-id="4df34-573">CC003</span></span></td>
<td><span data-ttu-id="4df34-574">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4df34-574">Assembly</span></span></td>
<td><span data-ttu-id="4df34-575">65</span><span class="sxs-lookup"><span data-stu-id="4df34-575">65</span></span></td>
<td><span data-ttu-id="4df34-576">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="4df34-576">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="4df34-577">438.75</span><span class="sxs-lookup"><span data-stu-id="4df34-577">438.75</span></span></td>
<td><span data-ttu-id="4df34-578">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-578">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-579">CC004</span><span class="sxs-lookup"><span data-stu-id="4df34-579">CC004</span></span></td>
<td><span data-ttu-id="4df34-580">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="4df34-580">Packaging</span></span></td>
<td><span data-ttu-id="4df34-581">35</span><span class="sxs-lookup"><span data-stu-id="4df34-581">35</span></span></td>
<td><span data-ttu-id="4df34-582">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="4df34-582">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="4df34-583">236.25</span><span class="sxs-lookup"><span data-stu-id="4df34-583">236.25</span></span></td>
<td><span data-ttu-id="4df34-584">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-584">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-585">CC003</span><span class="sxs-lookup"><span data-stu-id="4df34-585">CC003</span></span></td>
<td><span data-ttu-id="4df34-586">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4df34-586">Assembly</span></span></td>
<td><span data-ttu-id="4df34-587">65</span><span class="sxs-lookup"><span data-stu-id="4df34-587">65</span></span></td>
<td><span data-ttu-id="4df34-588">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="4df34-588">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="4df34-589">5,297.69</span><span class="sxs-lookup"><span data-stu-id="4df34-589">5,297.69</span></span></td>
<td><span data-ttu-id="4df34-590">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-590">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-591">CC004</span><span class="sxs-lookup"><span data-stu-id="4df34-591">CC004</span></span></td>
<td><span data-ttu-id="4df34-592">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="4df34-592">Packaging</span></span></td>
<td><span data-ttu-id="4df34-593">35</span><span class="sxs-lookup"><span data-stu-id="4df34-593">35</span></span></td>
<td><span data-ttu-id="4df34-594">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="4df34-594">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="4df34-595">2,852.60</span><span class="sxs-lookup"><span data-stu-id="4df34-595">2,852.60</span></span></td>
<td><span data-ttu-id="4df34-596">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-596">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4df34-597">La tabla siguiente muestra el resultado cuando se aplican los servicios de Asamblea como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="4df34-597">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4df34-598">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-598">Cost object</span></span></th>
<th><span data-ttu-id="4df34-599">Magnitud</span><span class="sxs-lookup"><span data-stu-id="4df34-599">Magnitude</span></span></th>
<th><span data-ttu-id="4df34-600">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="4df34-600">Allocation factor</span></span></th>
<th><span data-ttu-id="4df34-601">Importe</span><span class="sxs-lookup"><span data-stu-id="4df34-601">Amount</span></span></th>
<th><span data-ttu-id="4df34-602">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4df34-602">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-603">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4df34-603">Prod 1</span></span></td>
<td><span data-ttu-id="4df34-604">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4df34-604">Product 1</span></span></td>
<td><span data-ttu-id="4df34-605">60</span><span class="sxs-lookup"><span data-stu-id="4df34-605">60</span></span></td>
<td><span data-ttu-id="4df34-606">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="4df34-606">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="4df34-607">535.31</span><span class="sxs-lookup"><span data-stu-id="4df34-607">535.31</span></span></td>
<td><span data-ttu-id="4df34-608">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-608">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-609">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4df34-609">Prod 2</span></span></td>
<td><span data-ttu-id="4df34-610">Producto 2</span><span class="sxs-lookup"><span data-stu-id="4df34-610">Product 2</span></span></td>
<td><span data-ttu-id="4df34-611">20</span><span class="sxs-lookup"><span data-stu-id="4df34-611">20</span></span></td>
<td><span data-ttu-id="4df34-612">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="4df34-612">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="4df34-613">178.44</span><span class="sxs-lookup"><span data-stu-id="4df34-613">178.44</span></span></td>
<td><span data-ttu-id="4df34-614">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-614">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-615">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4df34-615">Prod 1</span></span></td>
<td><span data-ttu-id="4df34-616">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4df34-616">Product 1</span></span></td>
<td><span data-ttu-id="4df34-617">60</span><span class="sxs-lookup"><span data-stu-id="4df34-617">60</span></span></td>
<td><span data-ttu-id="4df34-618">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="4df34-618">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="4df34-619">4,487.12</span><span class="sxs-lookup"><span data-stu-id="4df34-619">4,487.12</span></span></td>
<td><span data-ttu-id="4df34-620">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-620">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-621">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4df34-621">Prod 2</span></span></td>
<td><span data-ttu-id="4df34-622">Producto 2</span><span class="sxs-lookup"><span data-stu-id="4df34-622">Product 2</span></span></td>
<td><span data-ttu-id="4df34-623">20</span><span class="sxs-lookup"><span data-stu-id="4df34-623">20</span></span></td>
<td><span data-ttu-id="4df34-624">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="4df34-624">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="4df34-625">1,495.71</span><span class="sxs-lookup"><span data-stu-id="4df34-625">1,495.71</span></span></td>
<td><span data-ttu-id="4df34-626">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-626">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4df34-627">La tabla siguiente muestra el resultado cuando se aplican los servicios de Embalaje como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="4df34-627">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4df34-628">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-628">Cost object</span></span></th>
<th><span data-ttu-id="4df34-629">Magnitud</span><span class="sxs-lookup"><span data-stu-id="4df34-629">Magnitude</span></span></th>
<th><span data-ttu-id="4df34-630">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="4df34-630">Allocation factor</span></span></th>
<th><span data-ttu-id="4df34-631">Importe</span><span class="sxs-lookup"><span data-stu-id="4df34-631">Amount</span></span></th>
<th><span data-ttu-id="4df34-632">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4df34-632">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-633">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4df34-633">Prod 1</span></span></td>
<td><span data-ttu-id="4df34-634">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4df34-634">Product 1</span></span></td>
<td><span data-ttu-id="4df34-635">80</span><span class="sxs-lookup"><span data-stu-id="4df34-635">80</span></span></td>
<td><span data-ttu-id="4df34-636">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="4df34-636">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="4df34-637">241.05</span><span class="sxs-lookup"><span data-stu-id="4df34-637">241.05</span></span></td>
<td><span data-ttu-id="4df34-638">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-638">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-639">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4df34-639">Prod 2</span></span></td>
<td><span data-ttu-id="4df34-640">Producto 2</span><span class="sxs-lookup"><span data-stu-id="4df34-640">Product 2</span></span></td>
<td><span data-ttu-id="4df34-641">15</span><span class="sxs-lookup"><span data-stu-id="4df34-641">15</span></span></td>
<td><span data-ttu-id="4df34-642">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="4df34-642">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="4df34-643">45.20</span><span class="sxs-lookup"><span data-stu-id="4df34-643">45.20</span></span></td>
<td><span data-ttu-id="4df34-644">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-644">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-645">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4df34-645">Prod 1</span></span></td>
<td><span data-ttu-id="4df34-646">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4df34-646">Product 1</span></span></td>
<td><span data-ttu-id="4df34-647">80</span><span class="sxs-lookup"><span data-stu-id="4df34-647">80</span></span></td>
<td><span data-ttu-id="4df34-648">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="4df34-648">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="4df34-649">2,507.09</span><span class="sxs-lookup"><span data-stu-id="4df34-649">2,507.09</span></span></td>
<td><span data-ttu-id="4df34-650">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-650">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-651">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4df34-651">Prod 2</span></span></td>
<td><span data-ttu-id="4df34-652">Producto 2</span><span class="sxs-lookup"><span data-stu-id="4df34-652">Product 2</span></span></td>
<td><span data-ttu-id="4df34-653">15</span><span class="sxs-lookup"><span data-stu-id="4df34-653">15</span></span></td>
<td><span data-ttu-id="4df34-654">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="4df34-654">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="4df34-655">470.08</span><span class="sxs-lookup"><span data-stu-id="4df34-655">470.08</span></span></td>
<td><span data-ttu-id="4df34-656">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-656">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="4df34-657">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="4df34-657">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4df34-658">Diario</span><span class="sxs-lookup"><span data-stu-id="4df34-658">Journal</span></span></th>
<th><span data-ttu-id="4df34-659">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="4df34-659">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="4df34-660">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="4df34-660">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="4df34-661">Versión</span><span class="sxs-lookup"><span data-stu-id="4df34-661">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-662">00004</span><span class="sxs-lookup"><span data-stu-id="4df34-662">00004</span></span></td>
<td><span data-ttu-id="4df34-663">Diario de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="4df34-663">Cost allocation journal</span></span></td>
<td><span data-ttu-id="4df34-664">Fiscal</span><span class="sxs-lookup"><span data-stu-id="4df34-664">Fiscal</span></span></td>
<td><span data-ttu-id="4df34-665">2017</span><span class="sxs-lookup"><span data-stu-id="4df34-665">2017</span></span></td>
<td><span data-ttu-id="4df34-666">Período 1</span><span class="sxs-lookup"><span data-stu-id="4df34-666">Period 1</span></span></td>
<td><span data-ttu-id="4df34-667">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="4df34-667">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="4df34-668">Líneas de diario</span><span class="sxs-lookup"><span data-stu-id="4df34-668">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4df34-669">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="4df34-669">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="4df34-670">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-670">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4df34-671">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-671">Cost element</span></span></th>
<th><span data-ttu-id="4df34-672">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4df34-672">Cost behavior</span></span></th>
<th><span data-ttu-id="4df34-673">Importe</span><span class="sxs-lookup"><span data-stu-id="4df34-673">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-674">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-674">January 31, 2017</span></span></td>
<td><span data-ttu-id="4df34-675">CC001</span><span class="sxs-lookup"><span data-stu-id="4df34-675">CC001</span></span></td>
<td><span data-ttu-id="4df34-676">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="4df34-676">HR</span></span></td>
<td><span data-ttu-id="4df34-677">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-677">10001</span></span></td>
<td><span data-ttu-id="4df34-678">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-678">Electricity</span></span></td>
<td><span data-ttu-id="4df34-679">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-679">Fixed cost</span></span></td>
<td><span data-ttu-id="4df34-680">500,00</span><span class="sxs-lookup"><span data-stu-id="4df34-680">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-681">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-681">January 31, 2017</span></span></td>
<td><span data-ttu-id="4df34-682">CC001</span><span class="sxs-lookup"><span data-stu-id="4df34-682">CC001</span></span></td>
<td><span data-ttu-id="4df34-683">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="4df34-683">HR</span></span></td>
<td><span data-ttu-id="4df34-684">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-684">10001</span></span></td>
<td><span data-ttu-id="4df34-685">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-685">Electricity</span></span></td>
<td><span data-ttu-id="4df34-686">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-686">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-687">1,245.71</span><span class="sxs-lookup"><span data-stu-id="4df34-687">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-688">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-688">January 31, 2017</span></span></td>
<td><span data-ttu-id="4df34-689">CC002</span><span class="sxs-lookup"><span data-stu-id="4df34-689">CC002</span></span></td>
<td><span data-ttu-id="4df34-690">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4df34-690">Finance</span></span></td>
<td><span data-ttu-id="4df34-691">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-691">10001</span></span></td>
<td><span data-ttu-id="4df34-692">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-692">Electricity</span></span></td>
<td><span data-ttu-id="4df34-693">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-693">Fixed cost</span></span></td>
<td><span data-ttu-id="4df34-694">675.00</span><span class="sxs-lookup"><span data-stu-id="4df34-694">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-695">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-695">January 31, 2017</span></span></td>
<td><span data-ttu-id="4df34-696">CC002</span><span class="sxs-lookup"><span data-stu-id="4df34-696">CC002</span></span></td>
<td><span data-ttu-id="4df34-697">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4df34-697">Finance</span></span></td>
<td><span data-ttu-id="4df34-698">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-698">10001</span></span></td>
<td><span data-ttu-id="4df34-699">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-699">Electricity</span></span></td>
<td><span data-ttu-id="4df34-700">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-700">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-701">8,150.29</span><span class="sxs-lookup"><span data-stu-id="4df34-701">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-702">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-702">January 31, 2017</span></span></td>
<td><span data-ttu-id="4df34-703">CC003</span><span class="sxs-lookup"><span data-stu-id="4df34-703">CC003</span></span></td>
<td><span data-ttu-id="4df34-704">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4df34-704">Assembly</span></span></td>
<td><span data-ttu-id="4df34-705">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-705">10001</span></span></td>
<td><span data-ttu-id="4df34-706">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-706">Electricity</span></span></td>
<td><span data-ttu-id="4df34-707">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-707">Fixed cost</span></span></td>
<td><span data-ttu-id="4df34-708">713.75</span><span class="sxs-lookup"><span data-stu-id="4df34-708">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-709">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-709">January 31, 2017</span></span></td>
<td><span data-ttu-id="4df34-710">CC003</span><span class="sxs-lookup"><span data-stu-id="4df34-710">CC003</span></span></td>
<td><span data-ttu-id="4df34-711">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4df34-711">Assembly</span></span></td>
<td><span data-ttu-id="4df34-712">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-712">10001</span></span></td>
<td><span data-ttu-id="4df34-713">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-713">Electricity</span></span></td>
<td><span data-ttu-id="4df34-714">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-714">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-715">5,982.83</span><span class="sxs-lookup"><span data-stu-id="4df34-715">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-716">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-716">January 31, 2017</span></span></td>
<td><span data-ttu-id="4df34-717">CC003</span><span class="sxs-lookup"><span data-stu-id="4df34-717">CC003</span></span></td>
<td><span data-ttu-id="4df34-718">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="4df34-718">Packaging</span></span></td>
<td><span data-ttu-id="4df34-719">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-719">10001</span></span></td>
<td><span data-ttu-id="4df34-720">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-720">Electricity</span></span></td>
<td><span data-ttu-id="4df34-721">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-721">Fixed cost</span></span></td>
<td><span data-ttu-id="4df34-722">286.25</span><span class="sxs-lookup"><span data-stu-id="4df34-722">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-723">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-723">January 31, 2017</span></span></td>
<td><span data-ttu-id="4df34-724">CC003</span><span class="sxs-lookup"><span data-stu-id="4df34-724">CC003</span></span></td>
<td><span data-ttu-id="4df34-725">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="4df34-725">Packaging</span></span></td>
<td><span data-ttu-id="4df34-726">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-726">10001</span></span></td>
<td><span data-ttu-id="4df34-727">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-727">Electricity</span></span></td>
<td><span data-ttu-id="4df34-728">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-728">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-729">2,977.17</span><span class="sxs-lookup"><span data-stu-id="4df34-729">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-730">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-730">January 31, 2017</span></span></td>
<td><span data-ttu-id="4df34-731">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4df34-731">Prod 1</span></span></td>
<td><span data-ttu-id="4df34-732">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4df34-732">Product 1</span></span></td>
<td><span data-ttu-id="4df34-733">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-733">10001</span></span></td>
<td><span data-ttu-id="4df34-734">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-734">Electricity</span></span></td>
<td><span data-ttu-id="4df34-735">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-735">Fixed cost</span></span></td>
<td><span data-ttu-id="4df34-736">776.36</span><span class="sxs-lookup"><span data-stu-id="4df34-736">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-737">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-737">January 31, 2017</span></span></td>
<td><span data-ttu-id="4df34-738">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4df34-738">Prod 1</span></span></td>
<td><span data-ttu-id="4df34-739">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4df34-739">Product 1</span></span></td>
<td><span data-ttu-id="4df34-740">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-740">10001</span></span></td>
<td><span data-ttu-id="4df34-741">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-741">Electricity</span></span></td>
<td><span data-ttu-id="4df34-742">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-742">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-743">6,994.21</span><span class="sxs-lookup"><span data-stu-id="4df34-743">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-744">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-744">January 31, 2017</span></span></td>
<td><span data-ttu-id="4df34-745">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4df34-745">Prod 2</span></span></td>
<td><span data-ttu-id="4df34-746">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4df34-746">Product 1</span></span></td>
<td><span data-ttu-id="4df34-747">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-747">10001</span></span></td>
<td><span data-ttu-id="4df34-748">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-748">Electricity</span></span></td>
<td><span data-ttu-id="4df34-749">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-749">Fixed cost</span></span></td>
<td><span data-ttu-id="4df34-750">223.64</span><span class="sxs-lookup"><span data-stu-id="4df34-750">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-751">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-751">January 31, 2017</span></span></td>
<td><span data-ttu-id="4df34-752">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4df34-752">Prod 2</span></span></td>
<td><span data-ttu-id="4df34-753">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4df34-753">Product 1</span></span></td>
<td><span data-ttu-id="4df34-754">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-754">10001</span></span></td>
<td><span data-ttu-id="4df34-755">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-755">Electricity</span></span></td>
<td><span data-ttu-id="4df34-756">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-756">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-757">1,965.79</span><span class="sxs-lookup"><span data-stu-id="4df34-757">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="4df34-758">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="4df34-758">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4df34-759">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-759">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4df34-760">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-760">Cost element</span></span></th>
<th><span data-ttu-id="4df34-761">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4df34-761">Cost behavior</span></span></th>
<th><span data-ttu-id="4df34-762">Importe</span><span class="sxs-lookup"><span data-stu-id="4df34-762">Amount</span></span></th>
<th><span data-ttu-id="4df34-763">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="4df34-763">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4df34-764">CC001</span><span class="sxs-lookup"><span data-stu-id="4df34-764">CC001</span></span></td>
<td><span data-ttu-id="4df34-765">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="4df34-765">HR</span></span></td>
<td><span data-ttu-id="4df34-766">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-766">10001</span></span></td>
<td><span data-ttu-id="4df34-767">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-767">Electricity</span></span></td>
<td><span data-ttu-id="4df34-768">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-768">Fixed cost</span></span></td>
<td><span data-ttu-id="4df34-769">-500,00</span><span class="sxs-lookup"><span data-stu-id="4df34-769">-500.00</span></span></td>
<td><span data-ttu-id="4df34-770">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-770">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-771">CC002</span><span class="sxs-lookup"><span data-stu-id="4df34-771">CC002</span></span></td>
<td><span data-ttu-id="4df34-772">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4df34-772">Finance</span></span></td>
<td><span data-ttu-id="4df34-773">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-773">10001</span></span></td>
<td><span data-ttu-id="4df34-774">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-774">Electricity</span></span></td>
<td><span data-ttu-id="4df34-775">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-775">Fixed cost</span></span></td>
<td><span data-ttu-id="4df34-776">175.00</span><span class="sxs-lookup"><span data-stu-id="4df34-776">175.00</span></span></td>
<td><span data-ttu-id="4df34-777">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-777">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-778">CC003</span><span class="sxs-lookup"><span data-stu-id="4df34-778">CC003</span></span></td>
<td><span data-ttu-id="4df34-779">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4df34-779">Assembly</span></span></td>
<td><span data-ttu-id="4df34-780">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-780">10001</span></span></td>
<td><span data-ttu-id="4df34-781">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-781">Electricity</span></span></td>
<td><span data-ttu-id="4df34-782">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-782">Fixed cost</span></span></td>
<td><span data-ttu-id="4df34-783">275.00</span><span class="sxs-lookup"><span data-stu-id="4df34-783">275.00</span></span></td>
<td><span data-ttu-id="4df34-784">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-784">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-785">CC004</span><span class="sxs-lookup"><span data-stu-id="4df34-785">CC004</span></span></td>
<td><span data-ttu-id="4df34-786">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="4df34-786">Packaging</span></span></td>
<td><span data-ttu-id="4df34-787">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-787">10001</span></span></td>
<td><span data-ttu-id="4df34-788">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-788">Electricity</span></span></td>
<td><span data-ttu-id="4df34-789">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-789">Fixed cost</span></span></td>
<td><span data-ttu-id="4df34-790">50,00</span><span class="sxs-lookup"><span data-stu-id="4df34-790">50,00</span></span></td>
<td><span data-ttu-id="4df34-791">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-791">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-792">CC001</span><span class="sxs-lookup"><span data-stu-id="4df34-792">CC001</span></span></td>
<td><span data-ttu-id="4df34-793">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="4df34-793">HR</span></span></td>
<td><span data-ttu-id="4df34-794">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-794">10001</span></span></td>
<td><span data-ttu-id="4df34-795">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-795">Electricity</span></span></td>
<td><span data-ttu-id="4df34-796">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-796">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-797">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="4df34-797">-1,245.71</span></span></td>
<td><span data-ttu-id="4df34-798">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-798">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-799">CC002</span><span class="sxs-lookup"><span data-stu-id="4df34-799">CC002</span></span></td>
<td><span data-ttu-id="4df34-800">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4df34-800">Finance</span></span></td>
<td><span data-ttu-id="4df34-801">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-801">10001</span></span></td>
<td><span data-ttu-id="4df34-802">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-802">Electricity</span></span></td>
<td><span data-ttu-id="4df34-803">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-803">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-804">436.00</span><span class="sxs-lookup"><span data-stu-id="4df34-804">436.00</span></span></td>
<td><span data-ttu-id="4df34-805">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-805">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-806">CC003</span><span class="sxs-lookup"><span data-stu-id="4df34-806">CC003</span></span></td>
<td><span data-ttu-id="4df34-807">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4df34-807">Assembly</span></span></td>
<td><span data-ttu-id="4df34-808">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-808">10001</span></span></td>
<td><span data-ttu-id="4df34-809">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-809">Electricity</span></span></td>
<td><span data-ttu-id="4df34-810">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-810">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-811">685.14</span><span class="sxs-lookup"><span data-stu-id="4df34-811">685.14</span></span></td>
<td><span data-ttu-id="4df34-812">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-812">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-813">CC004</span><span class="sxs-lookup"><span data-stu-id="4df34-813">CC004</span></span></td>
<td><span data-ttu-id="4df34-814">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="4df34-814">Packaging</span></span></td>
<td><span data-ttu-id="4df34-815">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-815">10001</span></span></td>
<td><span data-ttu-id="4df34-816">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-816">Electricity</span></span></td>
<td><span data-ttu-id="4df34-817">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-817">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-818">124.57</span><span class="sxs-lookup"><span data-stu-id="4df34-818">124.57</span></span></td>
<td><span data-ttu-id="4df34-819">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-819">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-820">CC002</span><span class="sxs-lookup"><span data-stu-id="4df34-820">CC002</span></span></td>
<td><span data-ttu-id="4df34-821">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4df34-821">Finance</span></span></td>
<td><span data-ttu-id="4df34-822">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-822">10001</span></span></td>
<td><span data-ttu-id="4df34-823">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-823">Electricity</span></span></td>
<td><span data-ttu-id="4df34-824">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-824">Fixed cost</span></span></td>
<td><span data-ttu-id="4df34-825">-675,00</span><span class="sxs-lookup"><span data-stu-id="4df34-825">-675.00</span></span></td>
<td><span data-ttu-id="4df34-826">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-826">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-827">CC003</span><span class="sxs-lookup"><span data-stu-id="4df34-827">CC003</span></span></td>
<td><span data-ttu-id="4df34-828">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4df34-828">Assembly</span></span></td>
<td><span data-ttu-id="4df34-829">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-829">10001</span></span></td>
<td><span data-ttu-id="4df34-830">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-830">Electricity</span></span></td>
<td><span data-ttu-id="4df34-831">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-831">Fixed cost</span></span></td>
<td><span data-ttu-id="4df34-832">438.75</span><span class="sxs-lookup"><span data-stu-id="4df34-832">438.75</span></span></td>
<td><span data-ttu-id="4df34-833">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-833">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-834">CC004</span><span class="sxs-lookup"><span data-stu-id="4df34-834">CC004</span></span></td>
<td><span data-ttu-id="4df34-835">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="4df34-835">Packaging</span></span></td>
<td><span data-ttu-id="4df34-836">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-836">10001</span></span></td>
<td><span data-ttu-id="4df34-837">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-837">Electricity</span></span></td>
<td><span data-ttu-id="4df34-838">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-838">Fixed cost</span></span></td>
<td><span data-ttu-id="4df34-839">236.25</span><span class="sxs-lookup"><span data-stu-id="4df34-839">236.25</span></span></td>
<td><span data-ttu-id="4df34-840">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-840">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-841">CC002</span><span class="sxs-lookup"><span data-stu-id="4df34-841">CC002</span></span></td>
<td><span data-ttu-id="4df34-842">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4df34-842">Finance</span></span></td>
<td><span data-ttu-id="4df34-843">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-843">10001</span></span></td>
<td><span data-ttu-id="4df34-844">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-844">Electricity</span></span></td>
<td><span data-ttu-id="4df34-845">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-845">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-846">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="4df34-846">-8,150.29</span></span></td>
<td><span data-ttu-id="4df34-847">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-847">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-848">CC003</span><span class="sxs-lookup"><span data-stu-id="4df34-848">CC003</span></span></td>
<td><span data-ttu-id="4df34-849">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4df34-849">Assembly</span></span></td>
<td><span data-ttu-id="4df34-850">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-850">10001</span></span></td>
<td><span data-ttu-id="4df34-851">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-851">Electricity</span></span></td>
<td><span data-ttu-id="4df34-852">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-852">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-853">5,297.69</span><span class="sxs-lookup"><span data-stu-id="4df34-853">5,297.69</span></span></td>
<td><span data-ttu-id="4df34-854">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-854">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-855">CC004</span><span class="sxs-lookup"><span data-stu-id="4df34-855">CC004</span></span></td>
<td><span data-ttu-id="4df34-856">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="4df34-856">Packaging</span></span></td>
<td><span data-ttu-id="4df34-857">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-857">10001</span></span></td>
<td><span data-ttu-id="4df34-858">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-858">Electricity</span></span></td>
<td><span data-ttu-id="4df34-859">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-859">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-860">2,852.60</span><span class="sxs-lookup"><span data-stu-id="4df34-860">2,852.60</span></span></td>
<td><span data-ttu-id="4df34-861">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-861">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-862">CC003</span><span class="sxs-lookup"><span data-stu-id="4df34-862">CC003</span></span></td>
<td><span data-ttu-id="4df34-863">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4df34-863">Assembly</span></span></td>
<td><span data-ttu-id="4df34-864">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-864">10001</span></span></td>
<td><span data-ttu-id="4df34-865">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-865">Electricity</span></span></td>
<td><span data-ttu-id="4df34-866">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-866">Fixed cost</span></span></td>
<td><span data-ttu-id="4df34-867">-713,75</span><span class="sxs-lookup"><span data-stu-id="4df34-867">-713.75</span></span></td>
<td><span data-ttu-id="4df34-868">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-868">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-869">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4df34-869">Prod 1</span></span></td>
<td><span data-ttu-id="4df34-870">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4df34-870">Product 1</span></span></td>
<td><span data-ttu-id="4df34-871">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-871">10001</span></span></td>
<td><span data-ttu-id="4df34-872">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-872">Electricity</span></span></td>
<td><span data-ttu-id="4df34-873">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-873">Fixed cost</span></span></td>
<td><span data-ttu-id="4df34-874">535.31</span><span class="sxs-lookup"><span data-stu-id="4df34-874">535.31</span></span></td>
<td><span data-ttu-id="4df34-875">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-875">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-876">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4df34-876">Prod 2</span></span></td>
<td><span data-ttu-id="4df34-877">Producto 2</span><span class="sxs-lookup"><span data-stu-id="4df34-877">Product 2</span></span></td>
<td><span data-ttu-id="4df34-878">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-878">10001</span></span></td>
<td><span data-ttu-id="4df34-879">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-879">Electricity</span></span></td>
<td><span data-ttu-id="4df34-880">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-880">Fixed cost</span></span></td>
<td><span data-ttu-id="4df34-881">178.44</span><span class="sxs-lookup"><span data-stu-id="4df34-881">178.44</span></span></td>
<td><span data-ttu-id="4df34-882">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-882">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-883">CC003</span><span class="sxs-lookup"><span data-stu-id="4df34-883">CC003</span></span></td>
<td><span data-ttu-id="4df34-884">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4df34-884">Assembly</span></span></td>
<td><span data-ttu-id="4df34-885">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-885">10001</span></span></td>
<td><span data-ttu-id="4df34-886">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-886">Electricity</span></span></td>
<td><span data-ttu-id="4df34-887">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-887">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-888">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="4df34-888">-5,982.83</span></span></td>
<td><span data-ttu-id="4df34-889">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-889">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-890">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4df34-890">Prod 1</span></span></td>
<td><span data-ttu-id="4df34-891">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4df34-891">Product 1</span></span></td>
<td><span data-ttu-id="4df34-892">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-892">10001</span></span></td>
<td><span data-ttu-id="4df34-893">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-893">Electricity</span></span></td>
<td><span data-ttu-id="4df34-894">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-894">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-895">4,487.12</span><span class="sxs-lookup"><span data-stu-id="4df34-895">4,487.12</span></span></td>
<td><span data-ttu-id="4df34-896">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-896">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-897">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4df34-897">Prod 2</span></span></td>
<td><span data-ttu-id="4df34-898">Producto 2</span><span class="sxs-lookup"><span data-stu-id="4df34-898">Product 2</span></span></td>
<td><span data-ttu-id="4df34-899">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-899">10001</span></span></td>
<td><span data-ttu-id="4df34-900">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-900">Electricity</span></span></td>
<td><span data-ttu-id="4df34-901">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-901">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-902">1,495.71</span><span class="sxs-lookup"><span data-stu-id="4df34-902">1,495.71</span></span></td>
<td><span data-ttu-id="4df34-903">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-903">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-904">CC003</span><span class="sxs-lookup"><span data-stu-id="4df34-904">CC003</span></span></td>
<td><span data-ttu-id="4df34-905">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4df34-905">Assembly</span></span></td>
<td><span data-ttu-id="4df34-906">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-906">10001</span></span></td>
<td><span data-ttu-id="4df34-907">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-907">Electricity</span></span></td>
<td><span data-ttu-id="4df34-908">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-908">Fixed cost</span></span></td>
<td><span data-ttu-id="4df34-909">-286,25</span><span class="sxs-lookup"><span data-stu-id="4df34-909">-286.25</span></span></td>
<td><span data-ttu-id="4df34-910">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-910">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-911">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4df34-911">Prod 1</span></span></td>
<td><span data-ttu-id="4df34-912">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4df34-912">Product 1</span></span></td>
<td><span data-ttu-id="4df34-913">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-913">10001</span></span></td>
<td><span data-ttu-id="4df34-914">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-914">Electricity</span></span></td>
<td><span data-ttu-id="4df34-915">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-915">Fixed cost</span></span></td>
<td><span data-ttu-id="4df34-916">241.05</span><span class="sxs-lookup"><span data-stu-id="4df34-916">241.05</span></span></td>
<td><span data-ttu-id="4df34-917">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-917">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-918">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4df34-918">Prod 2</span></span></td>
<td><span data-ttu-id="4df34-919">Producto 2</span><span class="sxs-lookup"><span data-stu-id="4df34-919">Product 2</span></span></td>
<td><span data-ttu-id="4df34-920">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-920">10001</span></span></td>
<td><span data-ttu-id="4df34-921">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-921">Electricity</span></span></td>
<td><span data-ttu-id="4df34-922">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-922">Fixed cost</span></span></td>
<td><span data-ttu-id="4df34-923">45.20</span><span class="sxs-lookup"><span data-stu-id="4df34-923">45.20</span></span></td>
<td><span data-ttu-id="4df34-924">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-924">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-925">CC003</span><span class="sxs-lookup"><span data-stu-id="4df34-925">CC003</span></span></td>
<td><span data-ttu-id="4df34-926">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4df34-926">Assembly</span></span></td>
<td><span data-ttu-id="4df34-927">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-927">10001</span></span></td>
<td><span data-ttu-id="4df34-928">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-928">Electricity</span></span></td>
<td><span data-ttu-id="4df34-929">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-929">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-930">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="4df34-930">-2,977.17</span></span></td>
<td><span data-ttu-id="4df34-931">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-931">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-932">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4df34-932">Prod 1</span></span></td>
<td><span data-ttu-id="4df34-933">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4df34-933">Product 1</span></span></td>
<td><span data-ttu-id="4df34-934">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-934">10001</span></span></td>
<td><span data-ttu-id="4df34-935">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-935">Electricity</span></span></td>
<td><span data-ttu-id="4df34-936">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-936">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-937">2,507.09</span><span class="sxs-lookup"><span data-stu-id="4df34-937">2,507.09</span></span></td>
<td><span data-ttu-id="4df34-938">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-938">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4df34-939">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4df34-939">Prod 2</span></span></td>
<td><span data-ttu-id="4df34-940">Producto 2</span><span class="sxs-lookup"><span data-stu-id="4df34-940">Product 2</span></span></td>
<td><span data-ttu-id="4df34-941">10001</span><span class="sxs-lookup"><span data-stu-id="4df34-941">10001</span></span></td>
<td><span data-ttu-id="4df34-942">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-942">Electricity</span></span></td>
<td><span data-ttu-id="4df34-943">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-943">Variable cost</span></span></td>
<td><span data-ttu-id="4df34-944">470.08</span><span class="sxs-lookup"><span data-stu-id="4df34-944">470.08</span></span></td>
<td><span data-ttu-id="4df34-945">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4df34-945">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="4df34-946">Conclusión</span><span class="sxs-lookup"><span data-stu-id="4df34-946">Conclusion</span></span>
<span data-ttu-id="4df34-947">En la contabilidad financiera, un coste de 10.000,00 para electricidad se envía a un identificador ficticio de centro de coste.</span><span class="sxs-lookup"><span data-stu-id="4df34-947">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="4df34-948">Por lo tanto, los contables de coste sabrán que este coste se debe asignar.</span><span class="sxs-lookup"><span data-stu-id="4df34-948">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="4df34-949">En contabilidad de costes, los costes fluyen en las unidades organizativas y los niveles en función de las directivas y las reglas que se aplican.</span><span class="sxs-lookup"><span data-stu-id="4df34-949">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="4df34-950">Cada coste se ha asociado con una base de asignación que proporciona la mejor evaluación para la asignación de costes.</span><span class="sxs-lookup"><span data-stu-id="4df34-950">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="4df34-951">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-951">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="4df34-952">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4df34-952">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="4df34-953">Total</span><span class="sxs-lookup"><span data-stu-id="4df34-953">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="4df34-954">CC099</span><span class="sxs-lookup"><span data-stu-id="4df34-954">CC099</span></span></th>
<th><span data-ttu-id="4df34-955">CC001</span><span class="sxs-lookup"><span data-stu-id="4df34-955">CC001</span></span></th>
<th><span data-ttu-id="4df34-956">CC002</span><span class="sxs-lookup"><span data-stu-id="4df34-956">CC002</span></span></th>
<th><span data-ttu-id="4df34-957">CC003</span><span class="sxs-lookup"><span data-stu-id="4df34-957">CC003</span></span></th>
<th><span data-ttu-id="4df34-958">CC004</span><span class="sxs-lookup"><span data-stu-id="4df34-958">CC004</span></span></th>
<th><span data-ttu-id="4df34-959">Proy 1</span><span class="sxs-lookup"><span data-stu-id="4df34-959">Proj 1</span></span></th>
<th><span data-ttu-id="4df34-960">Proy 2</span><span class="sxs-lookup"><span data-stu-id="4df34-960">Proj 2</span></span></th>
<th><span data-ttu-id="4df34-961">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4df34-961">Prod 1</span></span></th>
<th><span data-ttu-id="4df34-962">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4df34-962">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="4df34-963">10001 Electricidad</span><span class="sxs-lookup"><span data-stu-id="4df34-963">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="4df34-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-965"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="4df34-965"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-966"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="4df34-966"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-967"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="4df34-967"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="4df34-968"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="4df34-968"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-969"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="4df34-969"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-970"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="4df34-970"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-971"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="4df34-971"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-972"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="4df34-972"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="4df34-973">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="4df34-973">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-974">0,00</span><span class="sxs-lookup"><span data-stu-id="4df34-974">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="4df34-975">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4df34-975">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-976">0,00</span><span class="sxs-lookup"><span data-stu-id="4df34-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-977">0,00</span><span class="sxs-lookup"><span data-stu-id="4df34-977">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-978">0,00</span><span class="sxs-lookup"><span data-stu-id="4df34-978">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-979">0,00</span><span class="sxs-lookup"><span data-stu-id="4df34-979">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-980">0,00</span><span class="sxs-lookup"><span data-stu-id="4df34-980">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="4df34-981">776.36</span><span class="sxs-lookup"><span data-stu-id="4df34-981">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-982">223.64</span><span class="sxs-lookup"><span data-stu-id="4df34-982">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-983"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="4df34-983"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="4df34-984">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4df34-984">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-985">000</span><span class="sxs-lookup"><span data-stu-id="4df34-985">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-986">0,00</span><span class="sxs-lookup"><span data-stu-id="4df34-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-987">0,00</span><span class="sxs-lookup"><span data-stu-id="4df34-987">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-988">0,00</span><span class="sxs-lookup"><span data-stu-id="4df34-988">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-989">0,00</span><span class="sxs-lookup"><span data-stu-id="4df34-989">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-990">30,00</span><span class="sxs-lookup"><span data-stu-id="4df34-990">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-991">10,00</span><span class="sxs-lookup"><span data-stu-id="4df34-991">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-992">6,994.21</span><span class="sxs-lookup"><span data-stu-id="4df34-992">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-993">1,965.79</span><span class="sxs-lookup"><span data-stu-id="4df34-993">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4df34-994"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="4df34-994"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="4df34-995">Este tema muestra cómo un artículo de costes principales, 10001 Electricidad, fluye por los objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="4df34-995">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="4df34-996">Por tanto, estos gastos generales se asignan al nivel más bajo de la organización.</span><span class="sxs-lookup"><span data-stu-id="4df34-996">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="4df34-997">Es decir, los objetos de coste del nivel más bajo son los que soportan el coste.</span><span class="sxs-lookup"><span data-stu-id="4df34-997">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="4df34-998">Si necesita un flujo visual del coste entre los objetos de coste, puede usar las reglas de directivas de acumulación de costes para visualizar el flujo del coste.</span><span class="sxs-lookup"><span data-stu-id="4df34-998">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="4df34-999">Para obtener información detallada, consulte la política de acumulación de costes.</span><span class="sxs-lookup"><span data-stu-id="4df34-999">For more detailed information, see Cost roll-up policy.</span></span> <span data-ttu-id="4df34-1000">(Tenga en cuenta que este tema no se ha completado aún, pero pronto se abordará).</span><span class="sxs-lookup"><span data-stu-id="4df34-1000">(Note that this topic isn't competed yet but is coming soon.)</span></span>




