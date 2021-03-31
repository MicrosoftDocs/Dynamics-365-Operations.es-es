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
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 882804141a6b520e2420343958c7a6b02a7e09ae
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208856"
---
# <a name="overhead-calculation"></a><span data-ttu-id="f989c-103">Cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="f989c-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f989c-104">Este tema describe los procesos típicos para calcular y asignar costes generales.</span><span class="sxs-lookup"><span data-stu-id="f989c-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="f989c-105">Definición del término</span><span class="sxs-lookup"><span data-stu-id="f989c-105">Term definition</span></span>
---------------

<span data-ttu-id="f989c-106">Los costes generales son costes que se contraen para dirigir un negocio, pero que no pueden ser atribuidos directamente a ninguna actividad empresarial, productos, o servicio específicos.</span><span class="sxs-lookup"><span data-stu-id="f989c-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="f989c-107">Los costes generales proporcionan un soporte fundamental a la generación de actividades rentables.</span><span class="sxs-lookup"><span data-stu-id="f989c-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="f989c-108">Algunos ejemplos de costes generales son:</span><span class="sxs-lookup"><span data-stu-id="f989c-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="f989c-109">Alquiler</span><span class="sxs-lookup"><span data-stu-id="f989c-109">Rent</span></span>
-   <span data-ttu-id="f989c-110">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-110">Electricity</span></span>
-   <span data-ttu-id="f989c-111">Sueldos administrativos</span><span class="sxs-lookup"><span data-stu-id="f989c-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="f989c-112">Visión general del cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="f989c-112">Overhead calculation overview</span></span>
<span data-ttu-id="f989c-113">El cálculo de costes generales ejecuta las directivas de contabilidad de costes en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="f989c-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="f989c-114">Puede calcular varias veces los costes generales del mismo período fiscal si se han cambiado las directivas de contabilidad de costes o se han detectado errores específicos.</span><span class="sxs-lookup"><span data-stu-id="f989c-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="f989c-115">Cada ejecución del cálculo de costes generales se almacena y recibe un identificador de versión único que permite comparar los cálculos de diferentes versiones.</span><span class="sxs-lookup"><span data-stu-id="f989c-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="f989c-116">Las entradas de costes que el cálculo de costes generales genera reciben una fecha de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="f989c-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="f989c-117">Esta fecha de contabilidad coincide con la fecha final del período fiscal que se usa en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="f989c-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="f989c-118">El identificador de versión único consiste en los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f989c-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="f989c-119">Tipo de versión</span><span class="sxs-lookup"><span data-stu-id="f989c-119">Version type</span></span>
-   <span data-ttu-id="f989c-120">Fecha y hora</span><span class="sxs-lookup"><span data-stu-id="f989c-120">Date and time</span></span>
-   <span data-ttu-id="f989c-121">Libro mayor de contabilidad de costes</span><span class="sxs-lookup"><span data-stu-id="f989c-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="f989c-122">Ejercicio</span><span class="sxs-lookup"><span data-stu-id="f989c-122">Fiscal year</span></span>
-   <span data-ttu-id="f989c-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="f989c-123">Fiscal period</span></span>

<span data-ttu-id="f989c-124">El cálculo de costes generales se ejecuta independientemente de la versión.</span><span class="sxs-lookup"><span data-stu-id="f989c-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="f989c-125">Por lo tanto, puede calcular la versión de presupuesto antes que la versión real.</span><span class="sxs-lookup"><span data-stu-id="f989c-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="f989c-126">El cálculo de costes generales consta de cuatro pasos, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="f989c-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="f989c-127">En cada paso, se crea una cabecera de diario que tiene entradas del diario.</span><span class="sxs-lookup"><span data-stu-id="f989c-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="f989c-128">Esta cabecera de diario guarda los datos de entrada para cada paso de cálculo.</span><span class="sxs-lookup"><span data-stu-id="f989c-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="f989c-129">Las directivas y las reglas se aplican a cada línea de diario, y las entradas de coste se generan como resultado.</span><span class="sxs-lookup"><span data-stu-id="f989c-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="f989c-130">Por tanto, siempre se tiene rastreabilidad completa.</span><span class="sxs-lookup"><span data-stu-id="f989c-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="f989c-131">[![Cálculo de costes generales](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="f989c-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="f989c-132">Calcular y asignar costes generales de electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="f989c-133">En la contabilidad financiera, algunos costes, como la electricidad, se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="f989c-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="f989c-134">Por lo tanto, no se proporciona una visión de gestión detallada para la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="f989c-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="f989c-135">En contabilidad de costes, para proporcionar información de gestión correcta en todas las unidades y niveles organizativos, los costes deben fluir por las unidades organizativas.</span><span class="sxs-lookup"><span data-stu-id="f989c-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="f989c-136">Este flujo se debe basar en cualquier registro preciso de consumo o en una evaluación justa.</span><span class="sxs-lookup"><span data-stu-id="f989c-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="f989c-137">En la contabilidad general, un coste de la electricidad se puede registrar como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="f989c-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="f989c-138">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="f989c-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="f989c-139">Centro de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="f989c-140">Cuenta principal</span><span class="sxs-lookup"><span data-stu-id="f989c-140">Main account</span></span></th>
<th><span data-ttu-id="f989c-141">Importe en la divisa de contabilidad</span><span class="sxs-lookup"><span data-stu-id="f989c-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-142">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="f989c-143">CC099</span><span class="sxs-lookup"><span data-stu-id="f989c-143">CC099</span></span></td>
<td><span data-ttu-id="f989c-144">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="f989c-144">Default cost center</span></span></td>
<td><span data-ttu-id="f989c-145">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-145">10001</span></span></td>
<td><span data-ttu-id="f989c-146">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-146">Electricity</span></span></td>
<td><span data-ttu-id="f989c-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="f989c-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="f989c-148">Paso 1: Procese el cálculo del comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="f989c-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="f989c-149">De forma predeterminada, cuando las entradas de coste se importan de los datos de origen, reciben la clasificación de comportamiento del coste **Sin ordenar** en la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="f989c-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="f989c-150">Aplicando reglas de directivas de comportamiento de coste, puede reclasificar entradas de coste como **Coste fijo** o **Coste variable**.</span><span class="sxs-lookup"><span data-stu-id="f989c-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="f989c-151">Defina la regla de comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="f989c-151">Define the cost behavior rule</span></span>

<span data-ttu-id="f989c-152">En algunos casos, parte del coste es una cuota fija, y el coste pendiente se basa en el consumo.</span><span class="sxs-lookup"><span data-stu-id="f989c-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="f989c-153">Las facturas de electricidad coinciden a menudo con esta definición.</span><span class="sxs-lookup"><span data-stu-id="f989c-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="f989c-154">Tras pagar una cuota fija específica, paga el consumo por kilovatio-hora (Kwh).</span><span class="sxs-lookup"><span data-stu-id="f989c-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="f989c-155">Por ejemplo, si la cuota de coste fijo es de 1.000,00, la regla de comportamiento del coste se define como sigue:</span><span class="sxs-lookup"><span data-stu-id="f989c-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="f989c-156">Importe fijo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="f989c-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="f989c-157">0 &lt;= 1.000,00 = Fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="f989c-158">1.000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="f989c-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="f989c-159">Diario</span><span class="sxs-lookup"><span data-stu-id="f989c-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="f989c-160">Diario</span><span class="sxs-lookup"><span data-stu-id="f989c-160">Journal</span></span></th>
<th><span data-ttu-id="f989c-161">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="f989c-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="f989c-162">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="f989c-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="f989c-163">Versión</span><span class="sxs-lookup"><span data-stu-id="f989c-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-164">00001</span><span class="sxs-lookup"><span data-stu-id="f989c-164">00001</span></span></td>
<td><span data-ttu-id="f989c-165">Diario de cálculo de comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="f989c-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="f989c-166">Fiscal</span><span class="sxs-lookup"><span data-stu-id="f989c-166">Fiscal</span></span></td>
<td><span data-ttu-id="f989c-167">2017</span><span class="sxs-lookup"><span data-stu-id="f989c-167">2017</span></span></td>
<td><span data-ttu-id="f989c-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="f989c-168">Period 1</span></span></td>
<td><span data-ttu-id="f989c-169">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="f989c-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="f989c-170">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="f989c-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="f989c-171">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="f989c-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="f989c-172">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="f989c-173">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-173">Cost element</span></span></th>
<th><span data-ttu-id="f989c-174">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="f989c-174">Cost behavior</span></span></th>
<th><span data-ttu-id="f989c-175">Importe</span><span class="sxs-lookup"><span data-stu-id="f989c-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-176">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="f989c-177">CC099</span><span class="sxs-lookup"><span data-stu-id="f989c-177">CC099</span></span></td>
<td><span data-ttu-id="f989c-178">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="f989c-178">Default cost center</span></span></td>
<td><span data-ttu-id="f989c-179">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-179">10001</span></span></td>
<td><span data-ttu-id="f989c-180">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-180">Electricity</span></span></td>
<td><span data-ttu-id="f989c-181">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="f989c-181">Unclassified</span></span></td>
<td><span data-ttu-id="f989c-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="f989c-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="f989c-183">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="f989c-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f989c-184">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="f989c-185">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-185">Cost element</span></span></th>
<th><span data-ttu-id="f989c-186">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="f989c-186">Cost behavior</span></span></th>
<th><span data-ttu-id="f989c-187">Importe</span><span class="sxs-lookup"><span data-stu-id="f989c-187">Amount</span></span></th>
<th><span data-ttu-id="f989c-188">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="f989c-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-189">CC099</span><span class="sxs-lookup"><span data-stu-id="f989c-189">CC099</span></span></td>
<td><span data-ttu-id="f989c-190">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="f989c-190">Default cost center</span></span></td>
<td><span data-ttu-id="f989c-191">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-191">10001</span></span></td>
<td><span data-ttu-id="f989c-192">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-192">Electricity</span></span></td>
<td><span data-ttu-id="f989c-193">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="f989c-193">Unclassified</span></span></td>
<td><span data-ttu-id="f989c-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="f989c-194">10,000.00</span></span></td>
<td><span data-ttu-id="f989c-195">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-196">CC099</span><span class="sxs-lookup"><span data-stu-id="f989c-196">CC099</span></span></td>
<td><span data-ttu-id="f989c-197">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="f989c-197">Default cost center</span></span></td>
<td><span data-ttu-id="f989c-198">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-198">10001</span></span></td>
<td><span data-ttu-id="f989c-199">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-199">Electricity</span></span></td>
<td><span data-ttu-id="f989c-200">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="f989c-200">Unclassified</span></span></td>
<td><span data-ttu-id="f989c-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="f989c-201">-10,000.00</span></span></td>
<td><span data-ttu-id="f989c-202">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-203">CC099</span><span class="sxs-lookup"><span data-stu-id="f989c-203">CC099</span></span></td>
<td><span data-ttu-id="f989c-204">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="f989c-204">Default cost center</span></span></td>
<td><span data-ttu-id="f989c-205">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-205">10001</span></span></td>
<td><span data-ttu-id="f989c-206">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-206">Electricity</span></span></td>
<td><span data-ttu-id="f989c-207">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-207">Fixed cost</span></span></td>
<td><span data-ttu-id="f989c-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="f989c-208">1,000.00</span></span></td>
<td><span data-ttu-id="f989c-209">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-210">CC099</span><span class="sxs-lookup"><span data-stu-id="f989c-210">CC099</span></span></td>
<td><span data-ttu-id="f989c-211">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="f989c-211">Default cost center</span></span></td>
<td><span data-ttu-id="f989c-212">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-212">10001</span></span></td>
<td><span data-ttu-id="f989c-213">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-213">Electricity</span></span></td>
<td><span data-ttu-id="f989c-214">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-214">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="f989c-215">9,000.00</span></span></td>
<td><span data-ttu-id="f989c-216">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f989c-217">Para obtener más información, consulte [Crear y asignar una directiva de comportamiento de costes a una unidad de control de costes](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="f989c-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="f989c-218">Paso 2: Procese el cálculo de distribución de costes</span><span class="sxs-lookup"><span data-stu-id="f989c-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="f989c-219">La distribución de costes se usa para redistribuir costes desde un objeto de coste a uno o más objetos de coste aplicando una base relevante de la asignación.</span><span class="sxs-lookup"><span data-stu-id="f989c-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="f989c-220">La distribución de costes y la asignación de costes difieren en que la distribución de costes siempre se produce en el nivel de elemento de costes principal del coste original.</span><span class="sxs-lookup"><span data-stu-id="f989c-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="f989c-221">Defina la regla de distribución del coste</span><span class="sxs-lookup"><span data-stu-id="f989c-221">Define the cost distribution rule</span></span>

<span data-ttu-id="f989c-222">En la contabilidad financiera, los costes de electricidad se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="f989c-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="f989c-223">En contabilidad de costes, este método no es suficientemente detallado.</span><span class="sxs-lookup"><span data-stu-id="f989c-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="f989c-224">El coste variable debe distribuirse a los objetos individuales de coste aplicando una base justa.</span><span class="sxs-lookup"><span data-stu-id="f989c-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="f989c-225">La base de asignación más lógica es el consumo de electricidad (Kwh).</span><span class="sxs-lookup"><span data-stu-id="f989c-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="f989c-226">Se crea un miembro de dimensión estadística que se denomina Electricity, y se registra el consumo de electricidad.</span><span class="sxs-lookup"><span data-stu-id="f989c-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="f989c-227">De forma predeterminada, todos los miembros de dimensión estadísticos estarán disponibles como bases de asignación.</span><span class="sxs-lookup"><span data-stu-id="f989c-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f989c-228">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-228">Cost object</span></span></th>
<th><span data-ttu-id="f989c-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="f989c-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-230">CC001</span><span class="sxs-lookup"><span data-stu-id="f989c-230">CC001</span></span></td>
<td><span data-ttu-id="f989c-231">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="f989c-231">HR</span></span></td>
<td><span data-ttu-id="f989c-232">1.000</span><span class="sxs-lookup"><span data-stu-id="f989c-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-233">CC002</span><span class="sxs-lookup"><span data-stu-id="f989c-233">CC002</span></span></td>
<td><span data-ttu-id="f989c-234">Finanzas</span><span class="sxs-lookup"><span data-stu-id="f989c-234">Finance</span></span></td>
<td><span data-ttu-id="f989c-235">6.000</span><span class="sxs-lookup"><span data-stu-id="f989c-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-236">CC003</span><span class="sxs-lookup"><span data-stu-id="f989c-236">CC003</span></span></td>
<td><span data-ttu-id="f989c-237">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="f989c-237">Assembly</span></span></td>
<td><span data-ttu-id="f989c-238">0</span><span class="sxs-lookup"><span data-stu-id="f989c-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f989c-239">La tabla siguiente muestra el resultado cuando se aplica el consumo de electricidad como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="f989c-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f989c-240">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-240">Cost object</span></span></th>
<th><span data-ttu-id="f989c-241">Magnitud</span><span class="sxs-lookup"><span data-stu-id="f989c-241">Magnitude</span></span></th>
<th><span data-ttu-id="f989c-242">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="f989c-242">Allocation factor</span></span></th>
<th><span data-ttu-id="f989c-243">Importe</span><span class="sxs-lookup"><span data-stu-id="f989c-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-244">CC001</span><span class="sxs-lookup"><span data-stu-id="f989c-244">CC001</span></span></td>
<td><span data-ttu-id="f989c-245">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="f989c-245">HR</span></span></td>
<td><span data-ttu-id="f989c-246">1.000</span><span class="sxs-lookup"><span data-stu-id="f989c-246">1,000</span></span></td>
<td><span data-ttu-id="f989c-247">(1.000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="f989c-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="f989c-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="f989c-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-249">CC002</span><span class="sxs-lookup"><span data-stu-id="f989c-249">CC002</span></span></td>
<td><span data-ttu-id="f989c-250">Finanzas</span><span class="sxs-lookup"><span data-stu-id="f989c-250">Finance</span></span></td>
<td><span data-ttu-id="f989c-251">6.000</span><span class="sxs-lookup"><span data-stu-id="f989c-251">6,000</span></span></td>
<td><span data-ttu-id="f989c-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="f989c-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="f989c-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="f989c-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-254">CC003</span><span class="sxs-lookup"><span data-stu-id="f989c-254">CC003</span></span></td>
<td><span data-ttu-id="f989c-255">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="f989c-255">Assembly</span></span></td>
<td><span data-ttu-id="f989c-256">0</span><span class="sxs-lookup"><span data-stu-id="f989c-256">0</span></span></td>
<td><span data-ttu-id="f989c-257">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="f989c-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="f989c-258">0,00</span><span class="sxs-lookup"><span data-stu-id="f989c-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f989c-259">El coste fijo debe distribuirse uniformemente a los objetos individuales de costes que han consumido electricidad.</span><span class="sxs-lookup"><span data-stu-id="f989c-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="f989c-260">Puede obtener este resultado usando el miembro de dimensión estadístico de electricidad en una base de asignación de la fórmula: (Electricidad &gt; 0,00) La tabla siguiente muestra el resultado cuando el consumo de electricidad se aplica como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="f989c-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f989c-261">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-261">Cost object</span></span></th>
<th><span data-ttu-id="f989c-262">Fórmula</span><span class="sxs-lookup"><span data-stu-id="f989c-262">Formula</span></span></th>
<th><span data-ttu-id="f989c-263">Magnitud</span><span class="sxs-lookup"><span data-stu-id="f989c-263">Magnitude</span></span></th>
<th><span data-ttu-id="f989c-264">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="f989c-264">Allocation factor</span></span></th>
<th><span data-ttu-id="f989c-265">Importe</span><span class="sxs-lookup"><span data-stu-id="f989c-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-266">CC001</span><span class="sxs-lookup"><span data-stu-id="f989c-266">CC001</span></span></td>
<td><span data-ttu-id="f989c-267">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="f989c-267">HR</span></span></td>
<td><span data-ttu-id="f989c-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="f989c-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="f989c-269">1</span><span class="sxs-lookup"><span data-stu-id="f989c-269">1</span></span></td>
<td><span data-ttu-id="f989c-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="f989c-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="f989c-271">500,00</span><span class="sxs-lookup"><span data-stu-id="f989c-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-272">CC002</span><span class="sxs-lookup"><span data-stu-id="f989c-272">CC002</span></span></td>
<td><span data-ttu-id="f989c-273">Finanzas</span><span class="sxs-lookup"><span data-stu-id="f989c-273">Finance</span></span></td>
<td><span data-ttu-id="f989c-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="f989c-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="f989c-275">1</span><span class="sxs-lookup"><span data-stu-id="f989c-275">1</span></span></td>
<td><span data-ttu-id="f989c-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="f989c-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="f989c-277">500,00</span><span class="sxs-lookup"><span data-stu-id="f989c-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-278">CC003</span><span class="sxs-lookup"><span data-stu-id="f989c-278">CC003</span></span></td>
<td><span data-ttu-id="f989c-279">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="f989c-279">Assembly</span></span></td>
<td><span data-ttu-id="f989c-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="f989c-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="f989c-281">0</span><span class="sxs-lookup"><span data-stu-id="f989c-281">0</span></span></td>
<td><span data-ttu-id="f989c-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="f989c-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="f989c-283">0,00</span><span class="sxs-lookup"><span data-stu-id="f989c-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="f989c-284">Diario</span><span class="sxs-lookup"><span data-stu-id="f989c-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="f989c-285">Diario</span><span class="sxs-lookup"><span data-stu-id="f989c-285">Journal</span></span></th>
<th><span data-ttu-id="f989c-286">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="f989c-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="f989c-287">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="f989c-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="f989c-288">Versión</span><span class="sxs-lookup"><span data-stu-id="f989c-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-289">00002</span><span class="sxs-lookup"><span data-stu-id="f989c-289">00002</span></span></td>
<td><span data-ttu-id="f989c-290">Diario de cálculo de la distribución de costes</span><span class="sxs-lookup"><span data-stu-id="f989c-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="f989c-291">Fiscal</span><span class="sxs-lookup"><span data-stu-id="f989c-291">Fiscal</span></span></td>
<td><span data-ttu-id="f989c-292">2017</span><span class="sxs-lookup"><span data-stu-id="f989c-292">2017</span></span></td>
<td><span data-ttu-id="f989c-293">Período 1</span><span class="sxs-lookup"><span data-stu-id="f989c-293">Period 1</span></span></td>
<td><span data-ttu-id="f989c-294">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="f989c-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="f989c-295">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="f989c-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="f989c-296">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="f989c-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="f989c-297">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="f989c-298">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-298">Cost element</span></span></th>
<th><span data-ttu-id="f989c-299">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="f989c-299">Cost behavior</span></span></th>
<th><span data-ttu-id="f989c-300">Importe</span><span class="sxs-lookup"><span data-stu-id="f989c-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-301">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="f989c-302">CC099</span><span class="sxs-lookup"><span data-stu-id="f989c-302">CC099</span></span></td>
<td><span data-ttu-id="f989c-303">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="f989c-303">Default cost center</span></span></td>
<td><span data-ttu-id="f989c-304">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-304">10001</span></span></td>
<td><span data-ttu-id="f989c-305">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-305">Electricity</span></span></td>
<td><span data-ttu-id="f989c-306">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-306">Fixed cost</span></span></td>
<td><span data-ttu-id="f989c-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="f989c-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-308">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="f989c-309">CC099</span><span class="sxs-lookup"><span data-stu-id="f989c-309">CC099</span></span></td>
<td><span data-ttu-id="f989c-310">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="f989c-310">Default cost center</span></span></td>
<td><span data-ttu-id="f989c-311">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-311">10001</span></span></td>
<td><span data-ttu-id="f989c-312">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-312">Electricity</span></span></td>
<td><span data-ttu-id="f989c-313">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-313">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-314">9.000,00</span><span class="sxs-lookup"><span data-stu-id="f989c-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="f989c-315">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="f989c-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f989c-316">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="f989c-317">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-317">Cost element</span></span></th>
<th><span data-ttu-id="f989c-318">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="f989c-318">Cost behavior</span></span></th>
<th><span data-ttu-id="f989c-319">Importe</span><span class="sxs-lookup"><span data-stu-id="f989c-319">Amount</span></span></th>
<th><span data-ttu-id="f989c-320">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="f989c-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-321">CC099</span><span class="sxs-lookup"><span data-stu-id="f989c-321">CC099</span></span></td>
<td><span data-ttu-id="f989c-322">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="f989c-322">Default cost center</span></span></td>
<td><span data-ttu-id="f989c-323">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-323">10001</span></span></td>
<td><span data-ttu-id="f989c-324">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-324">Electricity</span></span></td>
<td><span data-ttu-id="f989c-325">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-325">Fixed cost</span></span></td>
<td><span data-ttu-id="f989c-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="f989c-326">-1,000.00</span></span></td>
<td><span data-ttu-id="f989c-327">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-328">CC001</span><span class="sxs-lookup"><span data-stu-id="f989c-328">CC001</span></span></td>
<td><span data-ttu-id="f989c-329">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="f989c-329">HR</span></span></td>
<td><span data-ttu-id="f989c-330">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-330">10001</span></span></td>
<td><span data-ttu-id="f989c-331">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-331">Electricity</span></span></td>
<td><span data-ttu-id="f989c-332">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-332">Fixed cost</span></span></td>
<td><span data-ttu-id="f989c-333">500,00</span><span class="sxs-lookup"><span data-stu-id="f989c-333">500.00</span></span></td>
<td><span data-ttu-id="f989c-334">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-335">CC002</span><span class="sxs-lookup"><span data-stu-id="f989c-335">CC002</span></span></td>
<td><span data-ttu-id="f989c-336">Finanzas</span><span class="sxs-lookup"><span data-stu-id="f989c-336">Finance</span></span></td>
<td><span data-ttu-id="f989c-337">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-337">10001</span></span></td>
<td><span data-ttu-id="f989c-338">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-338">Electricity</span></span></td>
<td><span data-ttu-id="f989c-339">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-339">Fixed cost</span></span></td>
<td><span data-ttu-id="f989c-340">500,00</span><span class="sxs-lookup"><span data-stu-id="f989c-340">500.00</span></span></td>
<td><span data-ttu-id="f989c-341">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-342">CC099</span><span class="sxs-lookup"><span data-stu-id="f989c-342">CC099</span></span></td>
<td><span data-ttu-id="f989c-343">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="f989c-343">Default cost center</span></span></td>
<td><span data-ttu-id="f989c-344">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-344">10001</span></span></td>
<td><span data-ttu-id="f989c-345">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-345">Electricity</span></span></td>
<td><span data-ttu-id="f989c-346">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-346">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="f989c-347">-9,000.00</span></span></td>
<td><span data-ttu-id="f989c-348">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-349">CC001</span><span class="sxs-lookup"><span data-stu-id="f989c-349">CC001</span></span></td>
<td><span data-ttu-id="f989c-350">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="f989c-350">HR</span></span></td>
<td><span data-ttu-id="f989c-351">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-351">10001</span></span></td>
<td><span data-ttu-id="f989c-352">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-352">Electricity</span></span></td>
<td><span data-ttu-id="f989c-353">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-353">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="f989c-354">1,285.71</span></span></td>
<td><span data-ttu-id="f989c-355">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-356">CC002</span><span class="sxs-lookup"><span data-stu-id="f989c-356">CC002</span></span></td>
<td><span data-ttu-id="f989c-357">Finanzas</span><span class="sxs-lookup"><span data-stu-id="f989c-357">Finance</span></span></td>
<td><span data-ttu-id="f989c-358">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-358">10001</span></span></td>
<td><span data-ttu-id="f989c-359">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-359">Electricity</span></span></td>
<td><span data-ttu-id="f989c-360">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-360">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="f989c-361">7,714.29</span></span></td>
<td><span data-ttu-id="f989c-362">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f989c-363">Para obtener más información, consulte [Crear y asignar una directiva de distribución de costes a una unidad de control de costes](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="f989c-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="f989c-364">Paso 3: Procese el cálculo de las tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="f989c-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="f989c-365">La tasa de costes generales se usa para cargar uno o varios objetos de coste específicos.</span><span class="sxs-lookup"><span data-stu-id="f989c-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="f989c-366">El cargo se basa en un índice de coste predeterminado y la magnitud de la base de asignación asignada.</span><span class="sxs-lookup"><span data-stu-id="f989c-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="f989c-367">Defina la tasa de costes generales</span><span class="sxs-lookup"><span data-stu-id="f989c-367">Define the overhead rate</span></span>

<span data-ttu-id="f989c-368">El objeto de coste CC001 HR contribuye a un conjunto de proyectos internos.</span><span class="sxs-lookup"><span data-stu-id="f989c-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="f989c-369">Se crea un miembro de dimensión estadística que se denomina proyectos HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="f989c-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f989c-370">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-370">Cost object</span></span></th>
<th><span data-ttu-id="f989c-371">Horas</span><span class="sxs-lookup"><span data-stu-id="f989c-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-372">Proy 1</span><span class="sxs-lookup"><span data-stu-id="f989c-372">Proj 1</span></span></td>
<td><span data-ttu-id="f989c-373">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="f989c-373">Project 1</span></span></td>
<td><span data-ttu-id="f989c-374">3</span><span class="sxs-lookup"><span data-stu-id="f989c-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-375">Proy 2</span><span class="sxs-lookup"><span data-stu-id="f989c-375">Proj 2</span></span></td>
<td><span data-ttu-id="f989c-376">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="f989c-376">Project 2</span></span></td>
<td><span data-ttu-id="f989c-377">1</span><span class="sxs-lookup"><span data-stu-id="f989c-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f989c-378">Una tasa de coste predeterminada para la contribución de los proyectos de coste se ha definido.</span><span class="sxs-lookup"><span data-stu-id="f989c-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f989c-379">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-379">Cost object</span></span></th>
<th><span data-ttu-id="f989c-380">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-380">Cost element</span></span></th>
<th><span data-ttu-id="f989c-381">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="f989c-381">Cost behavior</span></span></th>
<th><span data-ttu-id="f989c-382">Unidades</span><span class="sxs-lookup"><span data-stu-id="f989c-382">Units</span></span></th>
<th><span data-ttu-id="f989c-383">Índice</span><span class="sxs-lookup"><span data-stu-id="f989c-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-384">CC001</span><span class="sxs-lookup"><span data-stu-id="f989c-384">CC001</span></span></td>
<td><span data-ttu-id="f989c-385">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="f989c-385">HR</span></span></td>
<td><span data-ttu-id="f989c-386">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-386">10001</span></span></td>
<td><span data-ttu-id="f989c-387">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-387">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-388">1</span><span class="sxs-lookup"><span data-stu-id="f989c-388">1</span></span></td>
<td><span data-ttu-id="f989c-389">10</span><span class="sxs-lookup"><span data-stu-id="f989c-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f989c-390">La tabla siguiente muestra el resultado cuando los proyectos HR se aplican como base de la asignación.</span><span class="sxs-lookup"><span data-stu-id="f989c-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f989c-391">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-391">Cost object</span></span></th>
<th><span data-ttu-id="f989c-392">Magnitud</span><span class="sxs-lookup"><span data-stu-id="f989c-392">Magnitude</span></span></th>
<th><span data-ttu-id="f989c-393">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-393">Cost element</span></span></th>
<th><span data-ttu-id="f989c-394">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="f989c-394">Allocation factor</span></span></th>
<th><span data-ttu-id="f989c-395">Importe</span><span class="sxs-lookup"><span data-stu-id="f989c-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-396">Proy 1</span><span class="sxs-lookup"><span data-stu-id="f989c-396">Proj 1</span></span></td>
<td><span data-ttu-id="f989c-397">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="f989c-397">Project 1</span></span></td>
<td><span data-ttu-id="f989c-398">3</span><span class="sxs-lookup"><span data-stu-id="f989c-398">3</span></span></td>
<td><span data-ttu-id="f989c-399">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-399">10001</span></span></td>
<td><span data-ttu-id="f989c-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="f989c-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="f989c-401">30,00</span><span class="sxs-lookup"><span data-stu-id="f989c-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-402">Proy 2</span><span class="sxs-lookup"><span data-stu-id="f989c-402">Proj 2</span></span></td>
<td><span data-ttu-id="f989c-403">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="f989c-403">Project 2</span></span></td>
<td><span data-ttu-id="f989c-404">1</span><span class="sxs-lookup"><span data-stu-id="f989c-404">1</span></span></td>
<td><span data-ttu-id="f989c-405">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-405">10001</span></span></td>
<td><span data-ttu-id="f989c-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="f989c-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="f989c-407">10,00</span><span class="sxs-lookup"><span data-stu-id="f989c-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="f989c-408">Diario</span><span class="sxs-lookup"><span data-stu-id="f989c-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="f989c-409">Diario</span><span class="sxs-lookup"><span data-stu-id="f989c-409">Journal</span></span></th>
<th><span data-ttu-id="f989c-410">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="f989c-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="f989c-411">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="f989c-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="f989c-412">Versión</span><span class="sxs-lookup"><span data-stu-id="f989c-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-413">00003</span><span class="sxs-lookup"><span data-stu-id="f989c-413">00003</span></span></td>
<td><span data-ttu-id="f989c-414">Diario de cálculo de tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="f989c-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="f989c-415">Fiscal</span><span class="sxs-lookup"><span data-stu-id="f989c-415">Fiscal</span></span></td>
<td><span data-ttu-id="f989c-416">2017</span><span class="sxs-lookup"><span data-stu-id="f989c-416">2017</span></span></td>
<td><span data-ttu-id="f989c-417">Período 1</span><span class="sxs-lookup"><span data-stu-id="f989c-417">Period 1</span></span></td>
<td><span data-ttu-id="f989c-418">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="f989c-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="f989c-419">Entradas de diario (entradas de diario para cálculo de tasas de costes generales)</span><span class="sxs-lookup"><span data-stu-id="f989c-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="f989c-420">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="f989c-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="f989c-421">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-421">Cost object</span></span></th>
<th><span data-ttu-id="f989c-422">Magnitud</span><span class="sxs-lookup"><span data-stu-id="f989c-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-423">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="f989c-424">Proy 1</span><span class="sxs-lookup"><span data-stu-id="f989c-424">Proj 1</span></span></td>
<td><span data-ttu-id="f989c-425">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="f989c-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="f989c-426">3,00</span><span class="sxs-lookup"><span data-stu-id="f989c-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-427">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="f989c-428">Proy 2</span><span class="sxs-lookup"><span data-stu-id="f989c-428">Proj 2</span></span></td>
<td><span data-ttu-id="f989c-429">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="f989c-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="f989c-430">1,00</span><span class="sxs-lookup"><span data-stu-id="f989c-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="f989c-431">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="f989c-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f989c-432">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="f989c-433">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-433">Cost element</span></span></th>
<th><span data-ttu-id="f989c-434">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="f989c-434">Cost behavior</span></span></th>
<th><span data-ttu-id="f989c-435">Importe</span><span class="sxs-lookup"><span data-stu-id="f989c-435">Amount</span></span></th>
<th><span data-ttu-id="f989c-436">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="f989c-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="f989c-437">CC0001</span></span></td>
<td><span data-ttu-id="f989c-438">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="f989c-438">HR</span></span></td>
<td><span data-ttu-id="f989c-439">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-439">10001</span></span></td>
<td><span data-ttu-id="f989c-440">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-440">Electricity</span></span></td>
<td><span data-ttu-id="f989c-441">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-441">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="f989c-442">-30.00</span></span></td>
<td><span data-ttu-id="f989c-443">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-444">Proy 1</span><span class="sxs-lookup"><span data-stu-id="f989c-444">Proj 1</span></span></td>
<td><span data-ttu-id="f989c-445">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="f989c-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="f989c-446">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-446">10001</span></span></td>
<td><span data-ttu-id="f989c-447">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-447">Electricity</span></span></td>
<td><span data-ttu-id="f989c-448">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-448">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-449">30,00</span><span class="sxs-lookup"><span data-stu-id="f989c-449">30.00</span></span></td>
<td><span data-ttu-id="f989c-450">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-451">CC001</span><span class="sxs-lookup"><span data-stu-id="f989c-451">CC001</span></span></td>
<td><span data-ttu-id="f989c-452">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="f989c-452">HR</span></span></td>
<td><span data-ttu-id="f989c-453">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-453">10001</span></span></td>
<td><span data-ttu-id="f989c-454">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-454">Electricity</span></span></td>
<td><span data-ttu-id="f989c-455">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-455">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="f989c-456">-10.00</span></span></td>
<td><span data-ttu-id="f989c-457">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-458">Proy 2</span><span class="sxs-lookup"><span data-stu-id="f989c-458">Proj 2</span></span></td>
<td><span data-ttu-id="f989c-459">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="f989c-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="f989c-460">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-460">10001</span></span></td>
<td><span data-ttu-id="f989c-461">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-461">Electricity</span></span></td>
<td><span data-ttu-id="f989c-462">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-462">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-463">10,00</span><span class="sxs-lookup"><span data-stu-id="f989c-463">10.00</span></span></td>
<td><span data-ttu-id="f989c-464">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f989c-465">Para obtener más información, consulte [Realizar cálculo de costes generales](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="f989c-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="f989c-466">Paso 4: Procese el cálculo de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="f989c-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="f989c-467">La asignación es utilizada para asignar el saldo de un objeto de coste a otros objetos de coste aplicando una base de asignación.</span><span class="sxs-lookup"><span data-stu-id="f989c-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="f989c-468">Finance admite el método de asignación recíproco.</span><span class="sxs-lookup"><span data-stu-id="f989c-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="f989c-469">En el método de asignación recíproco, se reconocen completamente los servicios mutuos que los objetos de coste auxiliar intercambian.</span><span class="sxs-lookup"><span data-stu-id="f989c-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="f989c-470">El sistema determina automáticamente el orden correcto para realizar las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="f989c-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="f989c-471">El saldo de un objeto de coste se asigna según una única base de asignación.</span><span class="sxs-lookup"><span data-stu-id="f989c-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="f989c-472">Las asignaciones entre dimensiones de objetos de coste y sus miembros respectivos se admiten.</span><span class="sxs-lookup"><span data-stu-id="f989c-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="f989c-473">El orden de asignación se controla por unidad de control de costes.</span><span class="sxs-lookup"><span data-stu-id="f989c-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="f989c-474">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="f989c-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="f989c-475">Defina la asignación de costes</span><span class="sxs-lookup"><span data-stu-id="f989c-475">Define the cost allocation</span></span>

<span data-ttu-id="f989c-476">A continuación se indica un ejemplo sencillo que explica cómo puede realizar el seguimiento del flujo de coste.</span><span class="sxs-lookup"><span data-stu-id="f989c-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="f989c-477">El objeto de coste CC001 HR contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="f989c-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="f989c-478">Se crea un miembro de dimensión estadística que se denomina servicios HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="f989c-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f989c-479">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-479">Cost object</span></span></th>
<th><span data-ttu-id="f989c-480">Servicios HR</span><span class="sxs-lookup"><span data-stu-id="f989c-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-481">CC002</span><span class="sxs-lookup"><span data-stu-id="f989c-481">CC002</span></span></td>
<td><span data-ttu-id="f989c-482">Finanzas</span><span class="sxs-lookup"><span data-stu-id="f989c-482">Finance</span></span></td>
<td><span data-ttu-id="f989c-483">35</span><span class="sxs-lookup"><span data-stu-id="f989c-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-484">CC003</span><span class="sxs-lookup"><span data-stu-id="f989c-484">CC003</span></span></td>
<td><span data-ttu-id="f989c-485">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="f989c-485">Assembly</span></span></td>
<td><span data-ttu-id="f989c-486">55</span><span class="sxs-lookup"><span data-stu-id="f989c-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-487">CC004</span><span class="sxs-lookup"><span data-stu-id="f989c-487">CC004</span></span></td>
<td><span data-ttu-id="f989c-488">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="f989c-488">Packaging</span></span></td>
<td><span data-ttu-id="f989c-489">10</span><span class="sxs-lookup"><span data-stu-id="f989c-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f989c-490">El objeto de coste CC002 Finanzas contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="f989c-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="f989c-491">Se crea un miembro de dimensión estadística que se denomina Finanzas para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="f989c-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f989c-492">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-492">Cost object</span></span></th>
<th><span data-ttu-id="f989c-493">Servicios financieros</span><span class="sxs-lookup"><span data-stu-id="f989c-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-494">CC003</span><span class="sxs-lookup"><span data-stu-id="f989c-494">CC003</span></span></td>
<td><span data-ttu-id="f989c-495">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="f989c-495">Assembly</span></span></td>
<td><span data-ttu-id="f989c-496">65</span><span class="sxs-lookup"><span data-stu-id="f989c-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-497">CC004</span><span class="sxs-lookup"><span data-stu-id="f989c-497">CC004</span></span></td>
<td><span data-ttu-id="f989c-498">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="f989c-498">Packaging</span></span></td>
<td><span data-ttu-id="f989c-499">35</span><span class="sxs-lookup"><span data-stu-id="f989c-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f989c-500">El objeto de coste CC003 Asamblea contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="f989c-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="f989c-501">Se crea un miembro de dimensión estadística que se denomina servicios de Asamblea para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="f989c-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f989c-502">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-502">Cost object</span></span></th>
<th><span data-ttu-id="f989c-503">Servicios de la asamblea (horas)</span><span class="sxs-lookup"><span data-stu-id="f989c-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f989c-504">Prod 1</span></span></td>
<td><span data-ttu-id="f989c-505">Producto 1</span><span class="sxs-lookup"><span data-stu-id="f989c-505">Product 1</span></span></td>
<td><span data-ttu-id="f989c-506">60</span><span class="sxs-lookup"><span data-stu-id="f989c-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f989c-507">Prod 2</span></span></td>
<td><span data-ttu-id="f989c-508">Producto 2</span><span class="sxs-lookup"><span data-stu-id="f989c-508">Product 2</span></span></td>
<td><span data-ttu-id="f989c-509">20</span><span class="sxs-lookup"><span data-stu-id="f989c-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f989c-510">El objeto de coste CC004 Embalaje contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="f989c-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="f989c-511">Se crea un miembro de dimensión estadística que se denomina servicios de Embalaje para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="f989c-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f989c-512">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-512">Cost object</span></span></th>
<th><span data-ttu-id="f989c-513">Servicios de embalaje (horas)</span><span class="sxs-lookup"><span data-stu-id="f989c-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f989c-514">Prod 1</span></span></td>
<td><span data-ttu-id="f989c-515">Producto 1</span><span class="sxs-lookup"><span data-stu-id="f989c-515">Product 1</span></span></td>
<td><span data-ttu-id="f989c-516">80</span><span class="sxs-lookup"><span data-stu-id="f989c-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f989c-517">Prod 2</span></span></td>
<td><span data-ttu-id="f989c-518">Producto 2</span><span class="sxs-lookup"><span data-stu-id="f989c-518">Product 2</span></span></td>
<td><span data-ttu-id="f989c-519">15</span><span class="sxs-lookup"><span data-stu-id="f989c-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="f989c-520">Las medidas estadísticas como las horas de la producción que un producto consume se pueden deducir de los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="f989c-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="f989c-521">Para obtener más información, vea [Plantilla de proveedor de medidas estadísticas](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="f989c-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="f989c-522">La tabla siguiente muestra el resultado cuando se aplican los servicios de HR como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="f989c-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f989c-523">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-523">Cost object</span></span></th>
<th><span data-ttu-id="f989c-524">Magnitud</span><span class="sxs-lookup"><span data-stu-id="f989c-524">Magnitude</span></span></th>
<th><span data-ttu-id="f989c-525">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="f989c-525">Allocation factor</span></span></th>
<th><span data-ttu-id="f989c-526">Importe</span><span class="sxs-lookup"><span data-stu-id="f989c-526">Amount</span></span></th>
<th><span data-ttu-id="f989c-527">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="f989c-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-528">CC002</span><span class="sxs-lookup"><span data-stu-id="f989c-528">CC002</span></span></td>
<td><span data-ttu-id="f989c-529">Finanzas</span><span class="sxs-lookup"><span data-stu-id="f989c-529">Finance</span></span></td>
<td><span data-ttu-id="f989c-530">35</span><span class="sxs-lookup"><span data-stu-id="f989c-530">35</span></span></td>
<td><span data-ttu-id="f989c-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="f989c-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="f989c-532">175.00</span><span class="sxs-lookup"><span data-stu-id="f989c-532">175.00</span></span></td>
<td><span data-ttu-id="f989c-533">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-534">CC003</span><span class="sxs-lookup"><span data-stu-id="f989c-534">CC003</span></span></td>
<td><span data-ttu-id="f989c-535">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="f989c-535">Assembly</span></span></td>
<td><span data-ttu-id="f989c-536">55</span><span class="sxs-lookup"><span data-stu-id="f989c-536">55</span></span></td>
<td><span data-ttu-id="f989c-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="f989c-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="f989c-538">275.00</span><span class="sxs-lookup"><span data-stu-id="f989c-538">275.00</span></span></td>
<td><span data-ttu-id="f989c-539">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-540">CC004</span><span class="sxs-lookup"><span data-stu-id="f989c-540">CC004</span></span></td>
<td><span data-ttu-id="f989c-541">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="f989c-541">Packaging</span></span></td>
<td><span data-ttu-id="f989c-542">10</span><span class="sxs-lookup"><span data-stu-id="f989c-542">10</span></span></td>
<td><span data-ttu-id="f989c-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="f989c-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="f989c-544">50,00</span><span class="sxs-lookup"><span data-stu-id="f989c-544">50.00</span></span></td>
<td><span data-ttu-id="f989c-545">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-546">CC002</span><span class="sxs-lookup"><span data-stu-id="f989c-546">CC002</span></span></td>
<td><span data-ttu-id="f989c-547">Finanzas</span><span class="sxs-lookup"><span data-stu-id="f989c-547">Finance</span></span></td>
<td><span data-ttu-id="f989c-548">35</span><span class="sxs-lookup"><span data-stu-id="f989c-548">35</span></span></td>
<td><span data-ttu-id="f989c-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="f989c-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="f989c-550">436.00</span><span class="sxs-lookup"><span data-stu-id="f989c-550">436.00</span></span></td>
<td><span data-ttu-id="f989c-551">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-552">CC003</span><span class="sxs-lookup"><span data-stu-id="f989c-552">CC003</span></span></td>
<td><span data-ttu-id="f989c-553">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="f989c-553">Assembly</span></span></td>
<td><span data-ttu-id="f989c-554">55</span><span class="sxs-lookup"><span data-stu-id="f989c-554">55</span></span></td>
<td><span data-ttu-id="f989c-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="f989c-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="f989c-556">685.14</span><span class="sxs-lookup"><span data-stu-id="f989c-556">685.14</span></span></td>
<td><span data-ttu-id="f989c-557">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-558">CC004</span><span class="sxs-lookup"><span data-stu-id="f989c-558">CC004</span></span></td>
<td><span data-ttu-id="f989c-559">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="f989c-559">Packaging</span></span></td>
<td><span data-ttu-id="f989c-560">10</span><span class="sxs-lookup"><span data-stu-id="f989c-560">10</span></span></td>
<td><span data-ttu-id="f989c-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="f989c-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="f989c-562">124.57</span><span class="sxs-lookup"><span data-stu-id="f989c-562">124.57</span></span></td>
<td><span data-ttu-id="f989c-563">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f989c-564">La tabla siguiente muestra el resultado cuando se aplican los servicios de Finanzas como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="f989c-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f989c-565">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-565">Cost object</span></span></th>
<th><span data-ttu-id="f989c-566">Magnitud</span><span class="sxs-lookup"><span data-stu-id="f989c-566">Magnitude</span></span></th>
<th><span data-ttu-id="f989c-567">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="f989c-567">Allocation factor</span></span></th>
<th><span data-ttu-id="f989c-568">Importe</span><span class="sxs-lookup"><span data-stu-id="f989c-568">Amount</span></span></th>
<th><span data-ttu-id="f989c-569">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="f989c-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-570">CC003</span><span class="sxs-lookup"><span data-stu-id="f989c-570">CC003</span></span></td>
<td><span data-ttu-id="f989c-571">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="f989c-571">Assembly</span></span></td>
<td><span data-ttu-id="f989c-572">65</span><span class="sxs-lookup"><span data-stu-id="f989c-572">65</span></span></td>
<td><span data-ttu-id="f989c-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="f989c-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="f989c-574">438.75</span><span class="sxs-lookup"><span data-stu-id="f989c-574">438.75</span></span></td>
<td><span data-ttu-id="f989c-575">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-576">CC004</span><span class="sxs-lookup"><span data-stu-id="f989c-576">CC004</span></span></td>
<td><span data-ttu-id="f989c-577">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="f989c-577">Packaging</span></span></td>
<td><span data-ttu-id="f989c-578">35</span><span class="sxs-lookup"><span data-stu-id="f989c-578">35</span></span></td>
<td><span data-ttu-id="f989c-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="f989c-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="f989c-580">236.25</span><span class="sxs-lookup"><span data-stu-id="f989c-580">236.25</span></span></td>
<td><span data-ttu-id="f989c-581">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-582">CC003</span><span class="sxs-lookup"><span data-stu-id="f989c-582">CC003</span></span></td>
<td><span data-ttu-id="f989c-583">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="f989c-583">Assembly</span></span></td>
<td><span data-ttu-id="f989c-584">65</span><span class="sxs-lookup"><span data-stu-id="f989c-584">65</span></span></td>
<td><span data-ttu-id="f989c-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="f989c-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="f989c-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="f989c-586">5,297.69</span></span></td>
<td><span data-ttu-id="f989c-587">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-588">CC004</span><span class="sxs-lookup"><span data-stu-id="f989c-588">CC004</span></span></td>
<td><span data-ttu-id="f989c-589">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="f989c-589">Packaging</span></span></td>
<td><span data-ttu-id="f989c-590">35</span><span class="sxs-lookup"><span data-stu-id="f989c-590">35</span></span></td>
<td><span data-ttu-id="f989c-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="f989c-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="f989c-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="f989c-592">2,852.60</span></span></td>
<td><span data-ttu-id="f989c-593">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f989c-594">La tabla siguiente muestra el resultado cuando se aplican los servicios de Asamblea como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="f989c-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f989c-595">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-595">Cost object</span></span></th>
<th><span data-ttu-id="f989c-596">Magnitud</span><span class="sxs-lookup"><span data-stu-id="f989c-596">Magnitude</span></span></th>
<th><span data-ttu-id="f989c-597">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="f989c-597">Allocation factor</span></span></th>
<th><span data-ttu-id="f989c-598">Importe</span><span class="sxs-lookup"><span data-stu-id="f989c-598">Amount</span></span></th>
<th><span data-ttu-id="f989c-599">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="f989c-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f989c-600">Prod 1</span></span></td>
<td><span data-ttu-id="f989c-601">Producto 1</span><span class="sxs-lookup"><span data-stu-id="f989c-601">Product 1</span></span></td>
<td><span data-ttu-id="f989c-602">60</span><span class="sxs-lookup"><span data-stu-id="f989c-602">60</span></span></td>
<td><span data-ttu-id="f989c-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="f989c-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="f989c-604">535.31</span><span class="sxs-lookup"><span data-stu-id="f989c-604">535.31</span></span></td>
<td><span data-ttu-id="f989c-605">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f989c-606">Prod 2</span></span></td>
<td><span data-ttu-id="f989c-607">Producto 2</span><span class="sxs-lookup"><span data-stu-id="f989c-607">Product 2</span></span></td>
<td><span data-ttu-id="f989c-608">20</span><span class="sxs-lookup"><span data-stu-id="f989c-608">20</span></span></td>
<td><span data-ttu-id="f989c-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="f989c-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="f989c-610">178.44</span><span class="sxs-lookup"><span data-stu-id="f989c-610">178.44</span></span></td>
<td><span data-ttu-id="f989c-611">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f989c-612">Prod 1</span></span></td>
<td><span data-ttu-id="f989c-613">Producto 1</span><span class="sxs-lookup"><span data-stu-id="f989c-613">Product 1</span></span></td>
<td><span data-ttu-id="f989c-614">60</span><span class="sxs-lookup"><span data-stu-id="f989c-614">60</span></span></td>
<td><span data-ttu-id="f989c-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="f989c-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="f989c-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="f989c-616">4,487.12</span></span></td>
<td><span data-ttu-id="f989c-617">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f989c-618">Prod 2</span></span></td>
<td><span data-ttu-id="f989c-619">Producto 2</span><span class="sxs-lookup"><span data-stu-id="f989c-619">Product 2</span></span></td>
<td><span data-ttu-id="f989c-620">20</span><span class="sxs-lookup"><span data-stu-id="f989c-620">20</span></span></td>
<td><span data-ttu-id="f989c-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="f989c-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="f989c-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="f989c-622">1,495.71</span></span></td>
<td><span data-ttu-id="f989c-623">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f989c-624">La tabla siguiente muestra el resultado cuando se aplican los servicios de Embalaje como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="f989c-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f989c-625">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-625">Cost object</span></span></th>
<th><span data-ttu-id="f989c-626">Magnitud</span><span class="sxs-lookup"><span data-stu-id="f989c-626">Magnitude</span></span></th>
<th><span data-ttu-id="f989c-627">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="f989c-627">Allocation factor</span></span></th>
<th><span data-ttu-id="f989c-628">Importe</span><span class="sxs-lookup"><span data-stu-id="f989c-628">Amount</span></span></th>
<th><span data-ttu-id="f989c-629">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="f989c-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f989c-630">Prod 1</span></span></td>
<td><span data-ttu-id="f989c-631">Producto 1</span><span class="sxs-lookup"><span data-stu-id="f989c-631">Product 1</span></span></td>
<td><span data-ttu-id="f989c-632">80</span><span class="sxs-lookup"><span data-stu-id="f989c-632">80</span></span></td>
<td><span data-ttu-id="f989c-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="f989c-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="f989c-634">241.05</span><span class="sxs-lookup"><span data-stu-id="f989c-634">241.05</span></span></td>
<td><span data-ttu-id="f989c-635">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f989c-636">Prod 2</span></span></td>
<td><span data-ttu-id="f989c-637">Producto 2</span><span class="sxs-lookup"><span data-stu-id="f989c-637">Product 2</span></span></td>
<td><span data-ttu-id="f989c-638">15</span><span class="sxs-lookup"><span data-stu-id="f989c-638">15</span></span></td>
<td><span data-ttu-id="f989c-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="f989c-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="f989c-640">45.20</span><span class="sxs-lookup"><span data-stu-id="f989c-640">45.20</span></span></td>
<td><span data-ttu-id="f989c-641">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f989c-642">Prod 1</span></span></td>
<td><span data-ttu-id="f989c-643">Producto 1</span><span class="sxs-lookup"><span data-stu-id="f989c-643">Product 1</span></span></td>
<td><span data-ttu-id="f989c-644">80</span><span class="sxs-lookup"><span data-stu-id="f989c-644">80</span></span></td>
<td><span data-ttu-id="f989c-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="f989c-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="f989c-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="f989c-646">2,507.09</span></span></td>
<td><span data-ttu-id="f989c-647">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f989c-648">Prod 2</span></span></td>
<td><span data-ttu-id="f989c-649">Producto 2</span><span class="sxs-lookup"><span data-stu-id="f989c-649">Product 2</span></span></td>
<td><span data-ttu-id="f989c-650">15</span><span class="sxs-lookup"><span data-stu-id="f989c-650">15</span></span></td>
<td><span data-ttu-id="f989c-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="f989c-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="f989c-652">470.08</span><span class="sxs-lookup"><span data-stu-id="f989c-652">470.08</span></span></td>
<td><span data-ttu-id="f989c-653">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="f989c-654">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="f989c-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="f989c-655">Diario</span><span class="sxs-lookup"><span data-stu-id="f989c-655">Journal</span></span></th>
<th><span data-ttu-id="f989c-656">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="f989c-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="f989c-657">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="f989c-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="f989c-658">Versión</span><span class="sxs-lookup"><span data-stu-id="f989c-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-659">00004</span><span class="sxs-lookup"><span data-stu-id="f989c-659">00004</span></span></td>
<td><span data-ttu-id="f989c-660">Diario de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="f989c-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="f989c-661">Fiscal</span><span class="sxs-lookup"><span data-stu-id="f989c-661">Fiscal</span></span></td>
<td><span data-ttu-id="f989c-662">2017</span><span class="sxs-lookup"><span data-stu-id="f989c-662">2017</span></span></td>
<td><span data-ttu-id="f989c-663">Período 1</span><span class="sxs-lookup"><span data-stu-id="f989c-663">Period 1</span></span></td>
<td><span data-ttu-id="f989c-664">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="f989c-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="f989c-665">Líneas de diario</span><span class="sxs-lookup"><span data-stu-id="f989c-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="f989c-666">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="f989c-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="f989c-667">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="f989c-668">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-668">Cost element</span></span></th>
<th><span data-ttu-id="f989c-669">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="f989c-669">Cost behavior</span></span></th>
<th><span data-ttu-id="f989c-670">Importe</span><span class="sxs-lookup"><span data-stu-id="f989c-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-671">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="f989c-672">CC001</span><span class="sxs-lookup"><span data-stu-id="f989c-672">CC001</span></span></td>
<td><span data-ttu-id="f989c-673">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="f989c-673">HR</span></span></td>
<td><span data-ttu-id="f989c-674">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-674">10001</span></span></td>
<td><span data-ttu-id="f989c-675">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-675">Electricity</span></span></td>
<td><span data-ttu-id="f989c-676">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-676">Fixed cost</span></span></td>
<td><span data-ttu-id="f989c-677">500,00</span><span class="sxs-lookup"><span data-stu-id="f989c-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-678">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="f989c-679">CC001</span><span class="sxs-lookup"><span data-stu-id="f989c-679">CC001</span></span></td>
<td><span data-ttu-id="f989c-680">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="f989c-680">HR</span></span></td>
<td><span data-ttu-id="f989c-681">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-681">10001</span></span></td>
<td><span data-ttu-id="f989c-682">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-682">Electricity</span></span></td>
<td><span data-ttu-id="f989c-683">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-683">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="f989c-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-685">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="f989c-686">CC002</span><span class="sxs-lookup"><span data-stu-id="f989c-686">CC002</span></span></td>
<td><span data-ttu-id="f989c-687">Finanzas</span><span class="sxs-lookup"><span data-stu-id="f989c-687">Finance</span></span></td>
<td><span data-ttu-id="f989c-688">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-688">10001</span></span></td>
<td><span data-ttu-id="f989c-689">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-689">Electricity</span></span></td>
<td><span data-ttu-id="f989c-690">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-690">Fixed cost</span></span></td>
<td><span data-ttu-id="f989c-691">675.00</span><span class="sxs-lookup"><span data-stu-id="f989c-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-692">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="f989c-693">CC002</span><span class="sxs-lookup"><span data-stu-id="f989c-693">CC002</span></span></td>
<td><span data-ttu-id="f989c-694">Finanzas</span><span class="sxs-lookup"><span data-stu-id="f989c-694">Finance</span></span></td>
<td><span data-ttu-id="f989c-695">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-695">10001</span></span></td>
<td><span data-ttu-id="f989c-696">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-696">Electricity</span></span></td>
<td><span data-ttu-id="f989c-697">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-697">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="f989c-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-699">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="f989c-700">CC003</span><span class="sxs-lookup"><span data-stu-id="f989c-700">CC003</span></span></td>
<td><span data-ttu-id="f989c-701">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="f989c-701">Assembly</span></span></td>
<td><span data-ttu-id="f989c-702">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-702">10001</span></span></td>
<td><span data-ttu-id="f989c-703">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-703">Electricity</span></span></td>
<td><span data-ttu-id="f989c-704">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-704">Fixed cost</span></span></td>
<td><span data-ttu-id="f989c-705">713.75</span><span class="sxs-lookup"><span data-stu-id="f989c-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-706">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="f989c-707">CC003</span><span class="sxs-lookup"><span data-stu-id="f989c-707">CC003</span></span></td>
<td><span data-ttu-id="f989c-708">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="f989c-708">Assembly</span></span></td>
<td><span data-ttu-id="f989c-709">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-709">10001</span></span></td>
<td><span data-ttu-id="f989c-710">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-710">Electricity</span></span></td>
<td><span data-ttu-id="f989c-711">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-711">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="f989c-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-713">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="f989c-714">CC003</span><span class="sxs-lookup"><span data-stu-id="f989c-714">CC003</span></span></td>
<td><span data-ttu-id="f989c-715">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="f989c-715">Packaging</span></span></td>
<td><span data-ttu-id="f989c-716">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-716">10001</span></span></td>
<td><span data-ttu-id="f989c-717">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-717">Electricity</span></span></td>
<td><span data-ttu-id="f989c-718">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-718">Fixed cost</span></span></td>
<td><span data-ttu-id="f989c-719">286.25</span><span class="sxs-lookup"><span data-stu-id="f989c-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-720">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="f989c-721">CC003</span><span class="sxs-lookup"><span data-stu-id="f989c-721">CC003</span></span></td>
<td><span data-ttu-id="f989c-722">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="f989c-722">Packaging</span></span></td>
<td><span data-ttu-id="f989c-723">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-723">10001</span></span></td>
<td><span data-ttu-id="f989c-724">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-724">Electricity</span></span></td>
<td><span data-ttu-id="f989c-725">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-725">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="f989c-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-727">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="f989c-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f989c-728">Prod 1</span></span></td>
<td><span data-ttu-id="f989c-729">Producto 1</span><span class="sxs-lookup"><span data-stu-id="f989c-729">Product 1</span></span></td>
<td><span data-ttu-id="f989c-730">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-730">10001</span></span></td>
<td><span data-ttu-id="f989c-731">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-731">Electricity</span></span></td>
<td><span data-ttu-id="f989c-732">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-732">Fixed cost</span></span></td>
<td><span data-ttu-id="f989c-733">776.36</span><span class="sxs-lookup"><span data-stu-id="f989c-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-734">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="f989c-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f989c-735">Prod 1</span></span></td>
<td><span data-ttu-id="f989c-736">Producto 1</span><span class="sxs-lookup"><span data-stu-id="f989c-736">Product 1</span></span></td>
<td><span data-ttu-id="f989c-737">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-737">10001</span></span></td>
<td><span data-ttu-id="f989c-738">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-738">Electricity</span></span></td>
<td><span data-ttu-id="f989c-739">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-739">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="f989c-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-741">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="f989c-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f989c-742">Prod 2</span></span></td>
<td><span data-ttu-id="f989c-743">Producto 1</span><span class="sxs-lookup"><span data-stu-id="f989c-743">Product 1</span></span></td>
<td><span data-ttu-id="f989c-744">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-744">10001</span></span></td>
<td><span data-ttu-id="f989c-745">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-745">Electricity</span></span></td>
<td><span data-ttu-id="f989c-746">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-746">Fixed cost</span></span></td>
<td><span data-ttu-id="f989c-747">223.64</span><span class="sxs-lookup"><span data-stu-id="f989c-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-748">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="f989c-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f989c-749">Prod 2</span></span></td>
<td><span data-ttu-id="f989c-750">Producto 1</span><span class="sxs-lookup"><span data-stu-id="f989c-750">Product 1</span></span></td>
<td><span data-ttu-id="f989c-751">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-751">10001</span></span></td>
<td><span data-ttu-id="f989c-752">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-752">Electricity</span></span></td>
<td><span data-ttu-id="f989c-753">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-753">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="f989c-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="f989c-755">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="f989c-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="f989c-756">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="f989c-757">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-757">Cost element</span></span></th>
<th><span data-ttu-id="f989c-758">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="f989c-758">Cost behavior</span></span></th>
<th><span data-ttu-id="f989c-759">Importe</span><span class="sxs-lookup"><span data-stu-id="f989c-759">Amount</span></span></th>
<th><span data-ttu-id="f989c-760">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="f989c-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f989c-761">CC001</span><span class="sxs-lookup"><span data-stu-id="f989c-761">CC001</span></span></td>
<td><span data-ttu-id="f989c-762">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="f989c-762">HR</span></span></td>
<td><span data-ttu-id="f989c-763">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-763">10001</span></span></td>
<td><span data-ttu-id="f989c-764">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-764">Electricity</span></span></td>
<td><span data-ttu-id="f989c-765">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-765">Fixed cost</span></span></td>
<td><span data-ttu-id="f989c-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="f989c-766">-500.00</span></span></td>
<td><span data-ttu-id="f989c-767">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-768">CC002</span><span class="sxs-lookup"><span data-stu-id="f989c-768">CC002</span></span></td>
<td><span data-ttu-id="f989c-769">Finanzas</span><span class="sxs-lookup"><span data-stu-id="f989c-769">Finance</span></span></td>
<td><span data-ttu-id="f989c-770">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-770">10001</span></span></td>
<td><span data-ttu-id="f989c-771">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-771">Electricity</span></span></td>
<td><span data-ttu-id="f989c-772">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-772">Fixed cost</span></span></td>
<td><span data-ttu-id="f989c-773">175.00</span><span class="sxs-lookup"><span data-stu-id="f989c-773">175.00</span></span></td>
<td><span data-ttu-id="f989c-774">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-775">CC003</span><span class="sxs-lookup"><span data-stu-id="f989c-775">CC003</span></span></td>
<td><span data-ttu-id="f989c-776">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="f989c-776">Assembly</span></span></td>
<td><span data-ttu-id="f989c-777">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-777">10001</span></span></td>
<td><span data-ttu-id="f989c-778">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-778">Electricity</span></span></td>
<td><span data-ttu-id="f989c-779">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-779">Fixed cost</span></span></td>
<td><span data-ttu-id="f989c-780">275.00</span><span class="sxs-lookup"><span data-stu-id="f989c-780">275.00</span></span></td>
<td><span data-ttu-id="f989c-781">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-782">CC004</span><span class="sxs-lookup"><span data-stu-id="f989c-782">CC004</span></span></td>
<td><span data-ttu-id="f989c-783">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="f989c-783">Packaging</span></span></td>
<td><span data-ttu-id="f989c-784">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-784">10001</span></span></td>
<td><span data-ttu-id="f989c-785">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-785">Electricity</span></span></td>
<td><span data-ttu-id="f989c-786">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-786">Fixed cost</span></span></td>
<td><span data-ttu-id="f989c-787">50,00</span><span class="sxs-lookup"><span data-stu-id="f989c-787">50,00</span></span></td>
<td><span data-ttu-id="f989c-788">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-789">CC001</span><span class="sxs-lookup"><span data-stu-id="f989c-789">CC001</span></span></td>
<td><span data-ttu-id="f989c-790">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="f989c-790">HR</span></span></td>
<td><span data-ttu-id="f989c-791">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-791">10001</span></span></td>
<td><span data-ttu-id="f989c-792">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-792">Electricity</span></span></td>
<td><span data-ttu-id="f989c-793">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-793">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="f989c-794">-1,245.71</span></span></td>
<td><span data-ttu-id="f989c-795">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-796">CC002</span><span class="sxs-lookup"><span data-stu-id="f989c-796">CC002</span></span></td>
<td><span data-ttu-id="f989c-797">Finanzas</span><span class="sxs-lookup"><span data-stu-id="f989c-797">Finance</span></span></td>
<td><span data-ttu-id="f989c-798">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-798">10001</span></span></td>
<td><span data-ttu-id="f989c-799">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-799">Electricity</span></span></td>
<td><span data-ttu-id="f989c-800">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-800">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-801">436.00</span><span class="sxs-lookup"><span data-stu-id="f989c-801">436.00</span></span></td>
<td><span data-ttu-id="f989c-802">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-803">CC003</span><span class="sxs-lookup"><span data-stu-id="f989c-803">CC003</span></span></td>
<td><span data-ttu-id="f989c-804">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="f989c-804">Assembly</span></span></td>
<td><span data-ttu-id="f989c-805">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-805">10001</span></span></td>
<td><span data-ttu-id="f989c-806">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-806">Electricity</span></span></td>
<td><span data-ttu-id="f989c-807">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-807">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-808">685.14</span><span class="sxs-lookup"><span data-stu-id="f989c-808">685.14</span></span></td>
<td><span data-ttu-id="f989c-809">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-810">CC004</span><span class="sxs-lookup"><span data-stu-id="f989c-810">CC004</span></span></td>
<td><span data-ttu-id="f989c-811">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="f989c-811">Packaging</span></span></td>
<td><span data-ttu-id="f989c-812">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-812">10001</span></span></td>
<td><span data-ttu-id="f989c-813">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-813">Electricity</span></span></td>
<td><span data-ttu-id="f989c-814">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-814">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-815">124.57</span><span class="sxs-lookup"><span data-stu-id="f989c-815">124.57</span></span></td>
<td><span data-ttu-id="f989c-816">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-817">CC002</span><span class="sxs-lookup"><span data-stu-id="f989c-817">CC002</span></span></td>
<td><span data-ttu-id="f989c-818">Finanzas</span><span class="sxs-lookup"><span data-stu-id="f989c-818">Finance</span></span></td>
<td><span data-ttu-id="f989c-819">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-819">10001</span></span></td>
<td><span data-ttu-id="f989c-820">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-820">Electricity</span></span></td>
<td><span data-ttu-id="f989c-821">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-821">Fixed cost</span></span></td>
<td><span data-ttu-id="f989c-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="f989c-822">-675.00</span></span></td>
<td><span data-ttu-id="f989c-823">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-824">CC003</span><span class="sxs-lookup"><span data-stu-id="f989c-824">CC003</span></span></td>
<td><span data-ttu-id="f989c-825">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="f989c-825">Assembly</span></span></td>
<td><span data-ttu-id="f989c-826">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-826">10001</span></span></td>
<td><span data-ttu-id="f989c-827">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-827">Electricity</span></span></td>
<td><span data-ttu-id="f989c-828">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-828">Fixed cost</span></span></td>
<td><span data-ttu-id="f989c-829">438.75</span><span class="sxs-lookup"><span data-stu-id="f989c-829">438.75</span></span></td>
<td><span data-ttu-id="f989c-830">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-831">CC004</span><span class="sxs-lookup"><span data-stu-id="f989c-831">CC004</span></span></td>
<td><span data-ttu-id="f989c-832">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="f989c-832">Packaging</span></span></td>
<td><span data-ttu-id="f989c-833">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-833">10001</span></span></td>
<td><span data-ttu-id="f989c-834">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-834">Electricity</span></span></td>
<td><span data-ttu-id="f989c-835">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-835">Fixed cost</span></span></td>
<td><span data-ttu-id="f989c-836">236.25</span><span class="sxs-lookup"><span data-stu-id="f989c-836">236.25</span></span></td>
<td><span data-ttu-id="f989c-837">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-838">CC002</span><span class="sxs-lookup"><span data-stu-id="f989c-838">CC002</span></span></td>
<td><span data-ttu-id="f989c-839">Finanzas</span><span class="sxs-lookup"><span data-stu-id="f989c-839">Finance</span></span></td>
<td><span data-ttu-id="f989c-840">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-840">10001</span></span></td>
<td><span data-ttu-id="f989c-841">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-841">Electricity</span></span></td>
<td><span data-ttu-id="f989c-842">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-842">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="f989c-843">-8,150.29</span></span></td>
<td><span data-ttu-id="f989c-844">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-845">CC003</span><span class="sxs-lookup"><span data-stu-id="f989c-845">CC003</span></span></td>
<td><span data-ttu-id="f989c-846">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="f989c-846">Assembly</span></span></td>
<td><span data-ttu-id="f989c-847">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-847">10001</span></span></td>
<td><span data-ttu-id="f989c-848">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-848">Electricity</span></span></td>
<td><span data-ttu-id="f989c-849">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-849">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="f989c-850">5,297.69</span></span></td>
<td><span data-ttu-id="f989c-851">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-852">CC004</span><span class="sxs-lookup"><span data-stu-id="f989c-852">CC004</span></span></td>
<td><span data-ttu-id="f989c-853">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="f989c-853">Packaging</span></span></td>
<td><span data-ttu-id="f989c-854">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-854">10001</span></span></td>
<td><span data-ttu-id="f989c-855">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-855">Electricity</span></span></td>
<td><span data-ttu-id="f989c-856">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-856">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="f989c-857">2,852.60</span></span></td>
<td><span data-ttu-id="f989c-858">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-859">CC003</span><span class="sxs-lookup"><span data-stu-id="f989c-859">CC003</span></span></td>
<td><span data-ttu-id="f989c-860">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="f989c-860">Assembly</span></span></td>
<td><span data-ttu-id="f989c-861">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-861">10001</span></span></td>
<td><span data-ttu-id="f989c-862">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-862">Electricity</span></span></td>
<td><span data-ttu-id="f989c-863">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-863">Fixed cost</span></span></td>
<td><span data-ttu-id="f989c-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="f989c-864">-713.75</span></span></td>
<td><span data-ttu-id="f989c-865">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f989c-866">Prod 1</span></span></td>
<td><span data-ttu-id="f989c-867">Producto 1</span><span class="sxs-lookup"><span data-stu-id="f989c-867">Product 1</span></span></td>
<td><span data-ttu-id="f989c-868">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-868">10001</span></span></td>
<td><span data-ttu-id="f989c-869">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-869">Electricity</span></span></td>
<td><span data-ttu-id="f989c-870">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-870">Fixed cost</span></span></td>
<td><span data-ttu-id="f989c-871">535.31</span><span class="sxs-lookup"><span data-stu-id="f989c-871">535.31</span></span></td>
<td><span data-ttu-id="f989c-872">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f989c-873">Prod 2</span></span></td>
<td><span data-ttu-id="f989c-874">Producto 2</span><span class="sxs-lookup"><span data-stu-id="f989c-874">Product 2</span></span></td>
<td><span data-ttu-id="f989c-875">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-875">10001</span></span></td>
<td><span data-ttu-id="f989c-876">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-876">Electricity</span></span></td>
<td><span data-ttu-id="f989c-877">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-877">Fixed cost</span></span></td>
<td><span data-ttu-id="f989c-878">178.44</span><span class="sxs-lookup"><span data-stu-id="f989c-878">178.44</span></span></td>
<td><span data-ttu-id="f989c-879">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-880">CC003</span><span class="sxs-lookup"><span data-stu-id="f989c-880">CC003</span></span></td>
<td><span data-ttu-id="f989c-881">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="f989c-881">Assembly</span></span></td>
<td><span data-ttu-id="f989c-882">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-882">10001</span></span></td>
<td><span data-ttu-id="f989c-883">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-883">Electricity</span></span></td>
<td><span data-ttu-id="f989c-884">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-884">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="f989c-885">-5,982.83</span></span></td>
<td><span data-ttu-id="f989c-886">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f989c-887">Prod 1</span></span></td>
<td><span data-ttu-id="f989c-888">Producto 1</span><span class="sxs-lookup"><span data-stu-id="f989c-888">Product 1</span></span></td>
<td><span data-ttu-id="f989c-889">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-889">10001</span></span></td>
<td><span data-ttu-id="f989c-890">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-890">Electricity</span></span></td>
<td><span data-ttu-id="f989c-891">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-891">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="f989c-892">4,487.12</span></span></td>
<td><span data-ttu-id="f989c-893">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f989c-894">Prod 2</span></span></td>
<td><span data-ttu-id="f989c-895">Producto 2</span><span class="sxs-lookup"><span data-stu-id="f989c-895">Product 2</span></span></td>
<td><span data-ttu-id="f989c-896">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-896">10001</span></span></td>
<td><span data-ttu-id="f989c-897">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-897">Electricity</span></span></td>
<td><span data-ttu-id="f989c-898">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-898">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="f989c-899">1,495.71</span></span></td>
<td><span data-ttu-id="f989c-900">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-901">CC003</span><span class="sxs-lookup"><span data-stu-id="f989c-901">CC003</span></span></td>
<td><span data-ttu-id="f989c-902">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="f989c-902">Assembly</span></span></td>
<td><span data-ttu-id="f989c-903">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-903">10001</span></span></td>
<td><span data-ttu-id="f989c-904">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-904">Electricity</span></span></td>
<td><span data-ttu-id="f989c-905">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-905">Fixed cost</span></span></td>
<td><span data-ttu-id="f989c-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="f989c-906">-286.25</span></span></td>
<td><span data-ttu-id="f989c-907">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f989c-908">Prod 1</span></span></td>
<td><span data-ttu-id="f989c-909">Producto 1</span><span class="sxs-lookup"><span data-stu-id="f989c-909">Product 1</span></span></td>
<td><span data-ttu-id="f989c-910">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-910">10001</span></span></td>
<td><span data-ttu-id="f989c-911">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-911">Electricity</span></span></td>
<td><span data-ttu-id="f989c-912">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-912">Fixed cost</span></span></td>
<td><span data-ttu-id="f989c-913">241.05</span><span class="sxs-lookup"><span data-stu-id="f989c-913">241.05</span></span></td>
<td><span data-ttu-id="f989c-914">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f989c-915">Prod 2</span></span></td>
<td><span data-ttu-id="f989c-916">Producto 2</span><span class="sxs-lookup"><span data-stu-id="f989c-916">Product 2</span></span></td>
<td><span data-ttu-id="f989c-917">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-917">10001</span></span></td>
<td><span data-ttu-id="f989c-918">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-918">Electricity</span></span></td>
<td><span data-ttu-id="f989c-919">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-919">Fixed cost</span></span></td>
<td><span data-ttu-id="f989c-920">45.20</span><span class="sxs-lookup"><span data-stu-id="f989c-920">45.20</span></span></td>
<td><span data-ttu-id="f989c-921">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-922">CC003</span><span class="sxs-lookup"><span data-stu-id="f989c-922">CC003</span></span></td>
<td><span data-ttu-id="f989c-923">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="f989c-923">Assembly</span></span></td>
<td><span data-ttu-id="f989c-924">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-924">10001</span></span></td>
<td><span data-ttu-id="f989c-925">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-925">Electricity</span></span></td>
<td><span data-ttu-id="f989c-926">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-926">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="f989c-927">-2,977.17</span></span></td>
<td><span data-ttu-id="f989c-928">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f989c-929">Prod 1</span></span></td>
<td><span data-ttu-id="f989c-930">Producto 1</span><span class="sxs-lookup"><span data-stu-id="f989c-930">Product 1</span></span></td>
<td><span data-ttu-id="f989c-931">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-931">10001</span></span></td>
<td><span data-ttu-id="f989c-932">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-932">Electricity</span></span></td>
<td><span data-ttu-id="f989c-933">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-933">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="f989c-934">2,507.09</span></span></td>
<td><span data-ttu-id="f989c-935">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f989c-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f989c-936">Prod 2</span></span></td>
<td><span data-ttu-id="f989c-937">Producto 2</span><span class="sxs-lookup"><span data-stu-id="f989c-937">Product 2</span></span></td>
<td><span data-ttu-id="f989c-938">10001</span><span class="sxs-lookup"><span data-stu-id="f989c-938">10001</span></span></td>
<td><span data-ttu-id="f989c-939">Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-939">Electricity</span></span></td>
<td><span data-ttu-id="f989c-940">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-940">Variable cost</span></span></td>
<td><span data-ttu-id="f989c-941">470.08</span><span class="sxs-lookup"><span data-stu-id="f989c-941">470.08</span></span></td>
<td><span data-ttu-id="f989c-942">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="f989c-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="f989c-943">Conclusión</span><span class="sxs-lookup"><span data-stu-id="f989c-943">Conclusion</span></span>
<span data-ttu-id="f989c-944">En la contabilidad financiera, un coste de 10.000,00 para electricidad se envía a un identificador ficticio de centro de coste.</span><span class="sxs-lookup"><span data-stu-id="f989c-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="f989c-945">Por lo tanto, los contables de coste sabrán que este coste se debe asignar.</span><span class="sxs-lookup"><span data-stu-id="f989c-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="f989c-946">En contabilidad de costes, los costes fluyen en las unidades organizativas y los niveles en función de las directivas y las reglas que se aplican.</span><span class="sxs-lookup"><span data-stu-id="f989c-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="f989c-947">Cada coste se ha asociado con una base de asignación que proporciona la mejor evaluación para la asignación de costes.</span><span class="sxs-lookup"><span data-stu-id="f989c-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="f989c-948">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="f989c-949">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="f989c-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="f989c-950">Total</span><span class="sxs-lookup"><span data-stu-id="f989c-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="f989c-951">CC099</span><span class="sxs-lookup"><span data-stu-id="f989c-951">CC099</span></span></th>
<th><span data-ttu-id="f989c-952">CC001</span><span class="sxs-lookup"><span data-stu-id="f989c-952">CC001</span></span></th>
<th><span data-ttu-id="f989c-953">CC002</span><span class="sxs-lookup"><span data-stu-id="f989c-953">CC002</span></span></th>
<th><span data-ttu-id="f989c-954">CC003</span><span class="sxs-lookup"><span data-stu-id="f989c-954">CC003</span></span></th>
<th><span data-ttu-id="f989c-955">CC004</span><span class="sxs-lookup"><span data-stu-id="f989c-955">CC004</span></span></th>
<th><span data-ttu-id="f989c-956">Proy 1</span><span class="sxs-lookup"><span data-stu-id="f989c-956">Proj 1</span></span></th>
<th><span data-ttu-id="f989c-957">Proy 2</span><span class="sxs-lookup"><span data-stu-id="f989c-957">Proj 2</span></span></th>
<th><span data-ttu-id="f989c-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="f989c-958">Prod 1</span></span></th>
<th><span data-ttu-id="f989c-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="f989c-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="f989c-960">10001 Electricidad</span><span class="sxs-lookup"><span data-stu-id="f989c-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="f989c-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="f989c-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="f989c-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="f989c-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="f989c-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="f989c-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="f989c-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="f989c-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="f989c-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="f989c-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="f989c-970">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="f989c-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-971">0,00</span><span class="sxs-lookup"><span data-stu-id="f989c-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="f989c-972">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="f989c-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-973">0,00</span><span class="sxs-lookup"><span data-stu-id="f989c-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-974">0,00</span><span class="sxs-lookup"><span data-stu-id="f989c-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-975">0,00</span><span class="sxs-lookup"><span data-stu-id="f989c-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-976">0,00</span><span class="sxs-lookup"><span data-stu-id="f989c-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-977">0,00</span><span class="sxs-lookup"><span data-stu-id="f989c-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="f989c-978">776.36</span><span class="sxs-lookup"><span data-stu-id="f989c-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-979">223.64</span><span class="sxs-lookup"><span data-stu-id="f989c-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="f989c-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="f989c-981">Coste variable</span><span class="sxs-lookup"><span data-stu-id="f989c-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-982">000</span><span class="sxs-lookup"><span data-stu-id="f989c-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-983">0,00</span><span class="sxs-lookup"><span data-stu-id="f989c-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-984">0,00</span><span class="sxs-lookup"><span data-stu-id="f989c-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-985">0,00</span><span class="sxs-lookup"><span data-stu-id="f989c-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-986">0,00</span><span class="sxs-lookup"><span data-stu-id="f989c-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-987">30,00</span><span class="sxs-lookup"><span data-stu-id="f989c-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-988">10,00</span><span class="sxs-lookup"><span data-stu-id="f989c-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="f989c-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="f989c-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="f989c-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="f989c-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="f989c-992">Este tema muestra cómo un artículo de costes principales, 10001 Electricidad, fluye por los objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="f989c-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="f989c-993">Por tanto, estos gastos generales se asignan al nivel más bajo de la organización.</span><span class="sxs-lookup"><span data-stu-id="f989c-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="f989c-994">Es decir, los objetos de coste del nivel más bajo son los que soportan el coste.</span><span class="sxs-lookup"><span data-stu-id="f989c-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="f989c-995">Si necesita un flujo visual del coste entre los objetos de coste, puede usar las reglas de directivas de acumulación de costes para visualizar el flujo del coste.</span><span class="sxs-lookup"><span data-stu-id="f989c-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="f989c-996">Para obtener más información, consulte [Directiva de acumulación de costes y cálculo de costes generales](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="f989c-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]