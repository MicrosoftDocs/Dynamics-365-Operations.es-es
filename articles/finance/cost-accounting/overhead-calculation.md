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
ms.author: shylaw
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: cc6ad48ef80aa01739129b59cc1133d0a1930f24
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759481"
---
# <a name="overhead-calculation"></a><span data-ttu-id="7fdba-103">Cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="7fdba-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7fdba-104">Este tema describe los procesos típicos para calcular y asignar costes generales.</span><span class="sxs-lookup"><span data-stu-id="7fdba-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="7fdba-105">Definición del término</span><span class="sxs-lookup"><span data-stu-id="7fdba-105">Term definition</span></span>
---------------

<span data-ttu-id="7fdba-106">Los costes generales son costes que se contraen para dirigir un negocio, pero que no pueden ser atribuidos directamente a ninguna actividad empresarial, productos, o servicio específicos.</span><span class="sxs-lookup"><span data-stu-id="7fdba-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="7fdba-107">Los costes generales proporcionan un soporte fundamental a la generación de actividades rentables.</span><span class="sxs-lookup"><span data-stu-id="7fdba-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="7fdba-108">Algunos ejemplos de costes generales son:</span><span class="sxs-lookup"><span data-stu-id="7fdba-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="7fdba-109">Alquiler</span><span class="sxs-lookup"><span data-stu-id="7fdba-109">Rent</span></span>
-   <span data-ttu-id="7fdba-110">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-110">Electricity</span></span>
-   <span data-ttu-id="7fdba-111">Sueldos administrativos</span><span class="sxs-lookup"><span data-stu-id="7fdba-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="7fdba-112">Visión general del cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="7fdba-112">Overhead calculation overview</span></span>
<span data-ttu-id="7fdba-113">El cálculo de costes generales ejecuta las directivas de contabilidad de costes en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="7fdba-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="7fdba-114">Puede calcular varias veces los costes generales del mismo período fiscal si se han cambiado las directivas de contabilidad de costes o se han detectado errores específicos.</span><span class="sxs-lookup"><span data-stu-id="7fdba-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="7fdba-115">Cada ejecución del cálculo de costes generales se almacena y recibe un identificador de versión único que permite comparar los cálculos de diferentes versiones.</span><span class="sxs-lookup"><span data-stu-id="7fdba-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="7fdba-116">Las entradas de costes que el cálculo de costes generales genera reciben una fecha de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="7fdba-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="7fdba-117">Esta fecha de contabilidad coincide con la fecha final del período fiscal que se usa en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="7fdba-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="7fdba-118">El identificador de versión único consiste en los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="7fdba-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="7fdba-119">Tipo de versión</span><span class="sxs-lookup"><span data-stu-id="7fdba-119">Version type</span></span>
-   <span data-ttu-id="7fdba-120">Fecha y hora</span><span class="sxs-lookup"><span data-stu-id="7fdba-120">Date and time</span></span>
-   <span data-ttu-id="7fdba-121">Libro mayor de contabilidad de costes</span><span class="sxs-lookup"><span data-stu-id="7fdba-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="7fdba-122">Ejercicio</span><span class="sxs-lookup"><span data-stu-id="7fdba-122">Fiscal year</span></span>
-   <span data-ttu-id="7fdba-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="7fdba-123">Fiscal period</span></span>

<span data-ttu-id="7fdba-124">El cálculo de costes generales se ejecuta independientemente de la versión.</span><span class="sxs-lookup"><span data-stu-id="7fdba-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="7fdba-125">Por lo tanto, puede calcular la versión de presupuesto antes que la versión real.</span><span class="sxs-lookup"><span data-stu-id="7fdba-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="7fdba-126">El cálculo de costes generales consta de cuatro pasos, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="7fdba-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="7fdba-127">En cada paso, se crea una cabecera de diario que tiene entradas del diario.</span><span class="sxs-lookup"><span data-stu-id="7fdba-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="7fdba-128">Esta cabecera de diario guarda los datos de entrada para cada paso de cálculo.</span><span class="sxs-lookup"><span data-stu-id="7fdba-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="7fdba-129">Las directivas y las reglas se aplican a cada línea de diario, y las entradas de coste se generan como resultado.</span><span class="sxs-lookup"><span data-stu-id="7fdba-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="7fdba-130">Por tanto, siempre se tiene rastreabilidad completa.</span><span class="sxs-lookup"><span data-stu-id="7fdba-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="7fdba-131">[![Cálculo de costes generales](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="7fdba-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="7fdba-132">Calcular y asignar costes generales de electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="7fdba-133">En la contabilidad financiera, algunos costes, como la electricidad, se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="7fdba-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="7fdba-134">Por lo tanto, no se proporciona una visión de gestión detallada para la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="7fdba-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="7fdba-135">En contabilidad de costes, para proporcionar información de gestión correcta en todas las unidades y niveles organizativos, los costes deben fluir por las unidades organizativas.</span><span class="sxs-lookup"><span data-stu-id="7fdba-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="7fdba-136">Este flujo se debe basar en cualquier registro preciso de consumo o en una evaluación justa.</span><span class="sxs-lookup"><span data-stu-id="7fdba-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="7fdba-137">En la contabilidad general, un coste de la electricidad se puede registrar como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="7fdba-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="7fdba-138">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="7fdba-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="7fdba-139">Centro de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="7fdba-140">Cuenta principal</span><span class="sxs-lookup"><span data-stu-id="7fdba-140">Main account</span></span></th>
<th><span data-ttu-id="7fdba-141">Importe en la divisa de contabilidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-142">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="7fdba-143">CC099</span><span class="sxs-lookup"><span data-stu-id="7fdba-143">CC099</span></span></td>
<td><span data-ttu-id="7fdba-144">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="7fdba-144">Default cost center</span></span></td>
<td><span data-ttu-id="7fdba-145">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-145">10001</span></span></td>
<td><span data-ttu-id="7fdba-146">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-146">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="7fdba-148">Paso 1: Procese el cálculo del comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="7fdba-149">De forma predeterminada, cuando las entradas de coste se importan de los datos de origen, reciben la clasificación de comportamiento del coste **Sin ordenar** en la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="7fdba-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="7fdba-150">Aplicando reglas de directivas de comportamiento de coste, puede reclasificar entradas de coste como **Coste fijo** o **Coste variable**.</span><span class="sxs-lookup"><span data-stu-id="7fdba-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="7fdba-151">Defina la regla de comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-151">Define the cost behavior rule</span></span>

<span data-ttu-id="7fdba-152">En algunos casos, parte del coste es una cuota fija, y el coste pendiente se basa en el consumo.</span><span class="sxs-lookup"><span data-stu-id="7fdba-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="7fdba-153">Las facturas de electricidad coinciden a menudo con esta definición.</span><span class="sxs-lookup"><span data-stu-id="7fdba-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="7fdba-154">Tras pagar una cuota fija específica, paga el consumo por kilovatio-hora (Kwh).</span><span class="sxs-lookup"><span data-stu-id="7fdba-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="7fdba-155">Por ejemplo, si la cuota de coste fijo es de 1.000,00, la regla de comportamiento del coste se define como sigue:</span><span class="sxs-lookup"><span data-stu-id="7fdba-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="7fdba-156">Importe fijo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="7fdba-157">0 &lt;= 1.000,00 = Fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="7fdba-158">1.000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="7fdba-159">Diario</span><span class="sxs-lookup"><span data-stu-id="7fdba-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="7fdba-160">Diario</span><span class="sxs-lookup"><span data-stu-id="7fdba-160">Journal</span></span></th>
<th><span data-ttu-id="7fdba-161">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="7fdba-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="7fdba-162">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="7fdba-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="7fdba-163">Versión</span><span class="sxs-lookup"><span data-stu-id="7fdba-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-164">00001</span><span class="sxs-lookup"><span data-stu-id="7fdba-164">00001</span></span></td>
<td><span data-ttu-id="7fdba-165">Diario de cálculo de comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="7fdba-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="7fdba-166">Fiscal</span><span class="sxs-lookup"><span data-stu-id="7fdba-166">Fiscal</span></span></td>
<td><span data-ttu-id="7fdba-167">2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-167">2017</span></span></td>
<td><span data-ttu-id="7fdba-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-168">Period 1</span></span></td>
<td><span data-ttu-id="7fdba-169">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="7fdba-170">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="7fdba-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="7fdba-171">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="7fdba-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="7fdba-172">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="7fdba-173">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-173">Cost element</span></span></th>
<th><span data-ttu-id="7fdba-174">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="7fdba-174">Cost behavior</span></span></th>
<th><span data-ttu-id="7fdba-175">Importe</span><span class="sxs-lookup"><span data-stu-id="7fdba-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-176">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="7fdba-177">CC099</span><span class="sxs-lookup"><span data-stu-id="7fdba-177">CC099</span></span></td>
<td><span data-ttu-id="7fdba-178">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="7fdba-178">Default cost center</span></span></td>
<td><span data-ttu-id="7fdba-179">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-179">10001</span></span></td>
<td><span data-ttu-id="7fdba-180">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-180">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-181">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="7fdba-181">Unclassified</span></span></td>
<td><span data-ttu-id="7fdba-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="7fdba-183">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="7fdba-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7fdba-184">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="7fdba-185">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-185">Cost element</span></span></th>
<th><span data-ttu-id="7fdba-186">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="7fdba-186">Cost behavior</span></span></th>
<th><span data-ttu-id="7fdba-187">Importe</span><span class="sxs-lookup"><span data-stu-id="7fdba-187">Amount</span></span></th>
<th><span data-ttu-id="7fdba-188">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="7fdba-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-189">CC099</span><span class="sxs-lookup"><span data-stu-id="7fdba-189">CC099</span></span></td>
<td><span data-ttu-id="7fdba-190">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="7fdba-190">Default cost center</span></span></td>
<td><span data-ttu-id="7fdba-191">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-191">10001</span></span></td>
<td><span data-ttu-id="7fdba-192">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-192">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-193">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="7fdba-193">Unclassified</span></span></td>
<td><span data-ttu-id="7fdba-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-194">10,000.00</span></span></td>
<td><span data-ttu-id="7fdba-195">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-196">CC099</span><span class="sxs-lookup"><span data-stu-id="7fdba-196">CC099</span></span></td>
<td><span data-ttu-id="7fdba-197">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="7fdba-197">Default cost center</span></span></td>
<td><span data-ttu-id="7fdba-198">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-198">10001</span></span></td>
<td><span data-ttu-id="7fdba-199">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-199">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-200">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="7fdba-200">Unclassified</span></span></td>
<td><span data-ttu-id="7fdba-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-201">-10,000.00</span></span></td>
<td><span data-ttu-id="7fdba-202">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-203">CC099</span><span class="sxs-lookup"><span data-stu-id="7fdba-203">CC099</span></span></td>
<td><span data-ttu-id="7fdba-204">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="7fdba-204">Default cost center</span></span></td>
<td><span data-ttu-id="7fdba-205">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-205">10001</span></span></td>
<td><span data-ttu-id="7fdba-206">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-206">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-207">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-207">Fixed cost</span></span></td>
<td><span data-ttu-id="7fdba-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-208">1,000.00</span></span></td>
<td><span data-ttu-id="7fdba-209">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-210">CC099</span><span class="sxs-lookup"><span data-stu-id="7fdba-210">CC099</span></span></td>
<td><span data-ttu-id="7fdba-211">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="7fdba-211">Default cost center</span></span></td>
<td><span data-ttu-id="7fdba-212">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-212">10001</span></span></td>
<td><span data-ttu-id="7fdba-213">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-213">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-214">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-214">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-215">9,000.00</span></span></td>
<td><span data-ttu-id="7fdba-216">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7fdba-217">Para obtener más información, consulte [Crear y asignar una directiva de comportamiento de costes a una unidad de control de costes](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="7fdba-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="7fdba-218">Paso 2: Procese el cálculo de distribución de costes</span><span class="sxs-lookup"><span data-stu-id="7fdba-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="7fdba-219">La distribución de costes se usa para redistribuir costes desde un objeto de coste a uno o más objetos de coste aplicando una base relevante de la asignación.</span><span class="sxs-lookup"><span data-stu-id="7fdba-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="7fdba-220">La distribución de costes y la asignación de costes difieren en que la distribución de costes siempre se produce en el nivel de elemento de costes principal del coste original.</span><span class="sxs-lookup"><span data-stu-id="7fdba-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="7fdba-221">Defina la regla de distribución del coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-221">Define the cost distribution rule</span></span>

<span data-ttu-id="7fdba-222">En la contabilidad financiera, los costes de electricidad se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="7fdba-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="7fdba-223">En contabilidad de costes, este método no es suficientemente detallado.</span><span class="sxs-lookup"><span data-stu-id="7fdba-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="7fdba-224">El coste variable debe distribuirse a los objetos individuales de coste aplicando una base justa.</span><span class="sxs-lookup"><span data-stu-id="7fdba-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="7fdba-225">La base de asignación más lógica es el consumo de electricidad (Kwh).</span><span class="sxs-lookup"><span data-stu-id="7fdba-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="7fdba-226">Se crea un miembro de dimensión estadística que se denomina Electricity, y se registra el consumo de electricidad.</span><span class="sxs-lookup"><span data-stu-id="7fdba-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="7fdba-227">De forma predeterminada, todos los miembros de dimensión estadísticos estarán disponibles como bases de asignación.</span><span class="sxs-lookup"><span data-stu-id="7fdba-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7fdba-228">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-228">Cost object</span></span></th>
<th><span data-ttu-id="7fdba-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="7fdba-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-230">CC001</span><span class="sxs-lookup"><span data-stu-id="7fdba-230">CC001</span></span></td>
<td><span data-ttu-id="7fdba-231">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="7fdba-231">HR</span></span></td>
<td><span data-ttu-id="7fdba-232">1.000</span><span class="sxs-lookup"><span data-stu-id="7fdba-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-233">CC002</span><span class="sxs-lookup"><span data-stu-id="7fdba-233">CC002</span></span></td>
<td><span data-ttu-id="7fdba-234">Finanzas</span><span class="sxs-lookup"><span data-stu-id="7fdba-234">Finance</span></span></td>
<td><span data-ttu-id="7fdba-235">6.000</span><span class="sxs-lookup"><span data-stu-id="7fdba-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-236">CC003</span><span class="sxs-lookup"><span data-stu-id="7fdba-236">CC003</span></span></td>
<td><span data-ttu-id="7fdba-237">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="7fdba-237">Assembly</span></span></td>
<td><span data-ttu-id="7fdba-238">0</span><span class="sxs-lookup"><span data-stu-id="7fdba-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7fdba-239">La tabla siguiente muestra el resultado cuando se aplica el consumo de electricidad como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="7fdba-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7fdba-240">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-240">Cost object</span></span></th>
<th><span data-ttu-id="7fdba-241">Magnitud</span><span class="sxs-lookup"><span data-stu-id="7fdba-241">Magnitude</span></span></th>
<th><span data-ttu-id="7fdba-242">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="7fdba-242">Allocation factor</span></span></th>
<th><span data-ttu-id="7fdba-243">Importe</span><span class="sxs-lookup"><span data-stu-id="7fdba-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-244">CC001</span><span class="sxs-lookup"><span data-stu-id="7fdba-244">CC001</span></span></td>
<td><span data-ttu-id="7fdba-245">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="7fdba-245">HR</span></span></td>
<td><span data-ttu-id="7fdba-246">1.000</span><span class="sxs-lookup"><span data-stu-id="7fdba-246">1,000</span></span></td>
<td><span data-ttu-id="7fdba-247">(1.000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="7fdba-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="7fdba-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-249">CC002</span><span class="sxs-lookup"><span data-stu-id="7fdba-249">CC002</span></span></td>
<td><span data-ttu-id="7fdba-250">Finanzas</span><span class="sxs-lookup"><span data-stu-id="7fdba-250">Finance</span></span></td>
<td><span data-ttu-id="7fdba-251">6.000</span><span class="sxs-lookup"><span data-stu-id="7fdba-251">6,000</span></span></td>
<td><span data-ttu-id="7fdba-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="7fdba-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="7fdba-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-254">CC003</span><span class="sxs-lookup"><span data-stu-id="7fdba-254">CC003</span></span></td>
<td><span data-ttu-id="7fdba-255">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="7fdba-255">Assembly</span></span></td>
<td><span data-ttu-id="7fdba-256">0</span><span class="sxs-lookup"><span data-stu-id="7fdba-256">0</span></span></td>
<td><span data-ttu-id="7fdba-257">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="7fdba-258">0,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7fdba-259">El coste fijo debe distribuirse uniformemente a los objetos individuales de costes que han consumido electricidad.</span><span class="sxs-lookup"><span data-stu-id="7fdba-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="7fdba-260">Puede obtener este resultado usando el miembro de dimensión estadístico de electricidad en una base de asignación de la fórmula: (Electricidad &gt; 0,00) La tabla siguiente muestra el resultado cuando el consumo de electricidad se aplica como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="7fdba-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7fdba-261">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-261">Cost object</span></span></th>
<th><span data-ttu-id="7fdba-262">Fórmula</span><span class="sxs-lookup"><span data-stu-id="7fdba-262">Formula</span></span></th>
<th><span data-ttu-id="7fdba-263">Magnitud</span><span class="sxs-lookup"><span data-stu-id="7fdba-263">Magnitude</span></span></th>
<th><span data-ttu-id="7fdba-264">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="7fdba-264">Allocation factor</span></span></th>
<th><span data-ttu-id="7fdba-265">Importe</span><span class="sxs-lookup"><span data-stu-id="7fdba-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-266">CC001</span><span class="sxs-lookup"><span data-stu-id="7fdba-266">CC001</span></span></td>
<td><span data-ttu-id="7fdba-267">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="7fdba-267">HR</span></span></td>
<td><span data-ttu-id="7fdba-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="7fdba-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="7fdba-269">1</span><span class="sxs-lookup"><span data-stu-id="7fdba-269">1</span></span></td>
<td><span data-ttu-id="7fdba-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="7fdba-271">500,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-272">CC002</span><span class="sxs-lookup"><span data-stu-id="7fdba-272">CC002</span></span></td>
<td><span data-ttu-id="7fdba-273">Finanzas</span><span class="sxs-lookup"><span data-stu-id="7fdba-273">Finance</span></span></td>
<td><span data-ttu-id="7fdba-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="7fdba-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="7fdba-275">1</span><span class="sxs-lookup"><span data-stu-id="7fdba-275">1</span></span></td>
<td><span data-ttu-id="7fdba-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="7fdba-277">500,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-278">CC003</span><span class="sxs-lookup"><span data-stu-id="7fdba-278">CC003</span></span></td>
<td><span data-ttu-id="7fdba-279">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="7fdba-279">Assembly</span></span></td>
<td><span data-ttu-id="7fdba-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="7fdba-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="7fdba-281">0</span><span class="sxs-lookup"><span data-stu-id="7fdba-281">0</span></span></td>
<td><span data-ttu-id="7fdba-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="7fdba-283">0,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="7fdba-284">Diario</span><span class="sxs-lookup"><span data-stu-id="7fdba-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="7fdba-285">Diario</span><span class="sxs-lookup"><span data-stu-id="7fdba-285">Journal</span></span></th>
<th><span data-ttu-id="7fdba-286">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="7fdba-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="7fdba-287">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="7fdba-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="7fdba-288">Versión</span><span class="sxs-lookup"><span data-stu-id="7fdba-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-289">00002</span><span class="sxs-lookup"><span data-stu-id="7fdba-289">00002</span></span></td>
<td><span data-ttu-id="7fdba-290">Diario de cálculo de la distribución de costes</span><span class="sxs-lookup"><span data-stu-id="7fdba-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="7fdba-291">Fiscal</span><span class="sxs-lookup"><span data-stu-id="7fdba-291">Fiscal</span></span></td>
<td><span data-ttu-id="7fdba-292">2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-292">2017</span></span></td>
<td><span data-ttu-id="7fdba-293">Período 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-293">Period 1</span></span></td>
<td><span data-ttu-id="7fdba-294">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="7fdba-295">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="7fdba-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="7fdba-296">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="7fdba-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="7fdba-297">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="7fdba-298">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-298">Cost element</span></span></th>
<th><span data-ttu-id="7fdba-299">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="7fdba-299">Cost behavior</span></span></th>
<th><span data-ttu-id="7fdba-300">Importe</span><span class="sxs-lookup"><span data-stu-id="7fdba-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-301">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="7fdba-302">CC099</span><span class="sxs-lookup"><span data-stu-id="7fdba-302">CC099</span></span></td>
<td><span data-ttu-id="7fdba-303">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="7fdba-303">Default cost center</span></span></td>
<td><span data-ttu-id="7fdba-304">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-304">10001</span></span></td>
<td><span data-ttu-id="7fdba-305">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-305">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-306">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-306">Fixed cost</span></span></td>
<td><span data-ttu-id="7fdba-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-308">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="7fdba-309">CC099</span><span class="sxs-lookup"><span data-stu-id="7fdba-309">CC099</span></span></td>
<td><span data-ttu-id="7fdba-310">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="7fdba-310">Default cost center</span></span></td>
<td><span data-ttu-id="7fdba-311">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-311">10001</span></span></td>
<td><span data-ttu-id="7fdba-312">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-312">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-313">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-313">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-314">9.000,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="7fdba-315">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="7fdba-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7fdba-316">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="7fdba-317">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-317">Cost element</span></span></th>
<th><span data-ttu-id="7fdba-318">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="7fdba-318">Cost behavior</span></span></th>
<th><span data-ttu-id="7fdba-319">Importe</span><span class="sxs-lookup"><span data-stu-id="7fdba-319">Amount</span></span></th>
<th><span data-ttu-id="7fdba-320">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="7fdba-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-321">CC099</span><span class="sxs-lookup"><span data-stu-id="7fdba-321">CC099</span></span></td>
<td><span data-ttu-id="7fdba-322">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="7fdba-322">Default cost center</span></span></td>
<td><span data-ttu-id="7fdba-323">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-323">10001</span></span></td>
<td><span data-ttu-id="7fdba-324">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-324">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-325">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-325">Fixed cost</span></span></td>
<td><span data-ttu-id="7fdba-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-326">-1,000.00</span></span></td>
<td><span data-ttu-id="7fdba-327">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-328">CC001</span><span class="sxs-lookup"><span data-stu-id="7fdba-328">CC001</span></span></td>
<td><span data-ttu-id="7fdba-329">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="7fdba-329">HR</span></span></td>
<td><span data-ttu-id="7fdba-330">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-330">10001</span></span></td>
<td><span data-ttu-id="7fdba-331">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-331">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-332">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-332">Fixed cost</span></span></td>
<td><span data-ttu-id="7fdba-333">500,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-333">500.00</span></span></td>
<td><span data-ttu-id="7fdba-334">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-335">CC002</span><span class="sxs-lookup"><span data-stu-id="7fdba-335">CC002</span></span></td>
<td><span data-ttu-id="7fdba-336">Finanzas</span><span class="sxs-lookup"><span data-stu-id="7fdba-336">Finance</span></span></td>
<td><span data-ttu-id="7fdba-337">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-337">10001</span></span></td>
<td><span data-ttu-id="7fdba-338">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-338">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-339">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-339">Fixed cost</span></span></td>
<td><span data-ttu-id="7fdba-340">500,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-340">500.00</span></span></td>
<td><span data-ttu-id="7fdba-341">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-342">CC099</span><span class="sxs-lookup"><span data-stu-id="7fdba-342">CC099</span></span></td>
<td><span data-ttu-id="7fdba-343">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="7fdba-343">Default cost center</span></span></td>
<td><span data-ttu-id="7fdba-344">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-344">10001</span></span></td>
<td><span data-ttu-id="7fdba-345">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-345">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-346">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-346">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-347">-9,000.00</span></span></td>
<td><span data-ttu-id="7fdba-348">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-349">CC001</span><span class="sxs-lookup"><span data-stu-id="7fdba-349">CC001</span></span></td>
<td><span data-ttu-id="7fdba-350">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="7fdba-350">HR</span></span></td>
<td><span data-ttu-id="7fdba-351">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-351">10001</span></span></td>
<td><span data-ttu-id="7fdba-352">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-352">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-353">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-353">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="7fdba-354">1,285.71</span></span></td>
<td><span data-ttu-id="7fdba-355">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-356">CC002</span><span class="sxs-lookup"><span data-stu-id="7fdba-356">CC002</span></span></td>
<td><span data-ttu-id="7fdba-357">Finanzas</span><span class="sxs-lookup"><span data-stu-id="7fdba-357">Finance</span></span></td>
<td><span data-ttu-id="7fdba-358">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-358">10001</span></span></td>
<td><span data-ttu-id="7fdba-359">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-359">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-360">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-360">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="7fdba-361">7,714.29</span></span></td>
<td><span data-ttu-id="7fdba-362">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7fdba-363">Para obtener más información, consulte [Crear y asignar una directiva de distribución de costes a una unidad de control de costes](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="7fdba-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="7fdba-364">Paso 3: Procese el cálculo de las tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="7fdba-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="7fdba-365">La tasa de costes generales se usa para cargar uno o varios objetos de coste específicos.</span><span class="sxs-lookup"><span data-stu-id="7fdba-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="7fdba-366">El cargo se basa en un índice de coste predeterminado y la magnitud de la base de asignación asignada.</span><span class="sxs-lookup"><span data-stu-id="7fdba-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="7fdba-367">Defina la tasa de costes generales</span><span class="sxs-lookup"><span data-stu-id="7fdba-367">Define the overhead rate</span></span>

<span data-ttu-id="7fdba-368">El objeto de coste CC001 HR contribuye a un conjunto de proyectos internos.</span><span class="sxs-lookup"><span data-stu-id="7fdba-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="7fdba-369">Se crea un miembro de dimensión estadística que se denomina proyectos HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="7fdba-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7fdba-370">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-370">Cost object</span></span></th>
<th><span data-ttu-id="7fdba-371">Horas</span><span class="sxs-lookup"><span data-stu-id="7fdba-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-372">Proy 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-372">Proj 1</span></span></td>
<td><span data-ttu-id="7fdba-373">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-373">Project 1</span></span></td>
<td><span data-ttu-id="7fdba-374">3</span><span class="sxs-lookup"><span data-stu-id="7fdba-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-375">Proy 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-375">Proj 2</span></span></td>
<td><span data-ttu-id="7fdba-376">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-376">Project 2</span></span></td>
<td><span data-ttu-id="7fdba-377">1</span><span class="sxs-lookup"><span data-stu-id="7fdba-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7fdba-378">Una tasa de coste predeterminada para la contribución de los proyectos de coste se ha definido.</span><span class="sxs-lookup"><span data-stu-id="7fdba-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7fdba-379">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-379">Cost object</span></span></th>
<th><span data-ttu-id="7fdba-380">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-380">Cost element</span></span></th>
<th><span data-ttu-id="7fdba-381">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="7fdba-381">Cost behavior</span></span></th>
<th><span data-ttu-id="7fdba-382">Unidades</span><span class="sxs-lookup"><span data-stu-id="7fdba-382">Units</span></span></th>
<th><span data-ttu-id="7fdba-383">Índice</span><span class="sxs-lookup"><span data-stu-id="7fdba-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-384">CC001</span><span class="sxs-lookup"><span data-stu-id="7fdba-384">CC001</span></span></td>
<td><span data-ttu-id="7fdba-385">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="7fdba-385">HR</span></span></td>
<td><span data-ttu-id="7fdba-386">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-386">10001</span></span></td>
<td><span data-ttu-id="7fdba-387">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-387">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-388">1</span><span class="sxs-lookup"><span data-stu-id="7fdba-388">1</span></span></td>
<td><span data-ttu-id="7fdba-389">10</span><span class="sxs-lookup"><span data-stu-id="7fdba-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7fdba-390">La tabla siguiente muestra el resultado cuando los proyectos HR se aplican como base de la asignación.</span><span class="sxs-lookup"><span data-stu-id="7fdba-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7fdba-391">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-391">Cost object</span></span></th>
<th><span data-ttu-id="7fdba-392">Magnitud</span><span class="sxs-lookup"><span data-stu-id="7fdba-392">Magnitude</span></span></th>
<th><span data-ttu-id="7fdba-393">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-393">Cost element</span></span></th>
<th><span data-ttu-id="7fdba-394">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="7fdba-394">Allocation factor</span></span></th>
<th><span data-ttu-id="7fdba-395">Importe</span><span class="sxs-lookup"><span data-stu-id="7fdba-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-396">Proy 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-396">Proj 1</span></span></td>
<td><span data-ttu-id="7fdba-397">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-397">Project 1</span></span></td>
<td><span data-ttu-id="7fdba-398">3</span><span class="sxs-lookup"><span data-stu-id="7fdba-398">3</span></span></td>
<td><span data-ttu-id="7fdba-399">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-399">10001</span></span></td>
<td><span data-ttu-id="7fdba-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="7fdba-401">30,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-402">Proy 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-402">Proj 2</span></span></td>
<td><span data-ttu-id="7fdba-403">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-403">Project 2</span></span></td>
<td><span data-ttu-id="7fdba-404">1</span><span class="sxs-lookup"><span data-stu-id="7fdba-404">1</span></span></td>
<td><span data-ttu-id="7fdba-405">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-405">10001</span></span></td>
<td><span data-ttu-id="7fdba-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="7fdba-407">10,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="7fdba-408">Diario</span><span class="sxs-lookup"><span data-stu-id="7fdba-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="7fdba-409">Diario</span><span class="sxs-lookup"><span data-stu-id="7fdba-409">Journal</span></span></th>
<th><span data-ttu-id="7fdba-410">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="7fdba-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="7fdba-411">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="7fdba-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="7fdba-412">Versión</span><span class="sxs-lookup"><span data-stu-id="7fdba-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-413">00003</span><span class="sxs-lookup"><span data-stu-id="7fdba-413">00003</span></span></td>
<td><span data-ttu-id="7fdba-414">Diario de cálculo de tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="7fdba-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="7fdba-415">Fiscal</span><span class="sxs-lookup"><span data-stu-id="7fdba-415">Fiscal</span></span></td>
<td><span data-ttu-id="7fdba-416">2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-416">2017</span></span></td>
<td><span data-ttu-id="7fdba-417">Período 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-417">Period 1</span></span></td>
<td><span data-ttu-id="7fdba-418">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="7fdba-419">Entradas de diario (entradas de diario para cálculo de tasas de costes generales)</span><span class="sxs-lookup"><span data-stu-id="7fdba-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="7fdba-420">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="7fdba-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="7fdba-421">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-421">Cost object</span></span></th>
<th><span data-ttu-id="7fdba-422">Magnitud</span><span class="sxs-lookup"><span data-stu-id="7fdba-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-423">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="7fdba-424">Proy 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-424">Proj 1</span></span></td>
<td><span data-ttu-id="7fdba-425">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="7fdba-426">3,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-427">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="7fdba-428">Proy 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-428">Proj 2</span></span></td>
<td><span data-ttu-id="7fdba-429">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="7fdba-430">1,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="7fdba-431">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="7fdba-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7fdba-432">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="7fdba-433">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-433">Cost element</span></span></th>
<th><span data-ttu-id="7fdba-434">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="7fdba-434">Cost behavior</span></span></th>
<th><span data-ttu-id="7fdba-435">Importe</span><span class="sxs-lookup"><span data-stu-id="7fdba-435">Amount</span></span></th>
<th><span data-ttu-id="7fdba-436">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="7fdba-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="7fdba-437">CC0001</span></span></td>
<td><span data-ttu-id="7fdba-438">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="7fdba-438">HR</span></span></td>
<td><span data-ttu-id="7fdba-439">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-439">10001</span></span></td>
<td><span data-ttu-id="7fdba-440">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-440">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-441">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-441">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-442">-30.00</span></span></td>
<td><span data-ttu-id="7fdba-443">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-444">Proy 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-444">Proj 1</span></span></td>
<td><span data-ttu-id="7fdba-445">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="7fdba-446">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-446">10001</span></span></td>
<td><span data-ttu-id="7fdba-447">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-447">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-448">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-448">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-449">30,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-449">30.00</span></span></td>
<td><span data-ttu-id="7fdba-450">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-451">CC001</span><span class="sxs-lookup"><span data-stu-id="7fdba-451">CC001</span></span></td>
<td><span data-ttu-id="7fdba-452">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="7fdba-452">HR</span></span></td>
<td><span data-ttu-id="7fdba-453">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-453">10001</span></span></td>
<td><span data-ttu-id="7fdba-454">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-454">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-455">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-455">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-456">-10.00</span></span></td>
<td><span data-ttu-id="7fdba-457">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-458">Proy 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-458">Proj 2</span></span></td>
<td><span data-ttu-id="7fdba-459">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="7fdba-460">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-460">10001</span></span></td>
<td><span data-ttu-id="7fdba-461">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-461">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-462">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-462">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-463">10,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-463">10.00</span></span></td>
<td><span data-ttu-id="7fdba-464">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7fdba-465">Para obtener más información, consulte [Realizar cálculo de costes generales](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="7fdba-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="7fdba-466">Paso 4: Procese el cálculo de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="7fdba-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="7fdba-467">La asignación es utilizada para asignar el saldo de un objeto de coste a otros objetos de coste aplicando una base de asignación.</span><span class="sxs-lookup"><span data-stu-id="7fdba-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="7fdba-468">Finance admite el método de asignación recíproco.</span><span class="sxs-lookup"><span data-stu-id="7fdba-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="7fdba-469">En el método de asignación recíproco, se reconocen completamente los servicios mutuos que los objetos de coste auxiliar intercambian.</span><span class="sxs-lookup"><span data-stu-id="7fdba-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="7fdba-470">El sistema determina automáticamente el orden correcto para realizar las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="7fdba-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="7fdba-471">El saldo de un objeto de coste se asigna según una única base de asignación.</span><span class="sxs-lookup"><span data-stu-id="7fdba-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="7fdba-472">Las asignaciones entre dimensiones de objetos de coste y sus miembros respectivos se admiten.</span><span class="sxs-lookup"><span data-stu-id="7fdba-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="7fdba-473">El orden de asignación se controla por unidad de control de costes.</span><span class="sxs-lookup"><span data-stu-id="7fdba-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="7fdba-474">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="7fdba-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="7fdba-475">Defina la asignación de costes</span><span class="sxs-lookup"><span data-stu-id="7fdba-475">Define the cost allocation</span></span>

<span data-ttu-id="7fdba-476">A continuación se indica un ejemplo sencillo que explica cómo puede realizar el seguimiento del flujo de coste.</span><span class="sxs-lookup"><span data-stu-id="7fdba-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="7fdba-477">El objeto de coste CC001 HR contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="7fdba-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="7fdba-478">Se crea un miembro de dimensión estadística que se denomina servicios HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="7fdba-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7fdba-479">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-479">Cost object</span></span></th>
<th><span data-ttu-id="7fdba-480">Servicios HR</span><span class="sxs-lookup"><span data-stu-id="7fdba-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-481">CC002</span><span class="sxs-lookup"><span data-stu-id="7fdba-481">CC002</span></span></td>
<td><span data-ttu-id="7fdba-482">Finanzas</span><span class="sxs-lookup"><span data-stu-id="7fdba-482">Finance</span></span></td>
<td><span data-ttu-id="7fdba-483">35</span><span class="sxs-lookup"><span data-stu-id="7fdba-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-484">CC003</span><span class="sxs-lookup"><span data-stu-id="7fdba-484">CC003</span></span></td>
<td><span data-ttu-id="7fdba-485">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="7fdba-485">Assembly</span></span></td>
<td><span data-ttu-id="7fdba-486">55</span><span class="sxs-lookup"><span data-stu-id="7fdba-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-487">CC004</span><span class="sxs-lookup"><span data-stu-id="7fdba-487">CC004</span></span></td>
<td><span data-ttu-id="7fdba-488">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="7fdba-488">Packaging</span></span></td>
<td><span data-ttu-id="7fdba-489">10</span><span class="sxs-lookup"><span data-stu-id="7fdba-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7fdba-490">El objeto de coste CC002 Finanzas contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="7fdba-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="7fdba-491">Se crea un miembro de dimensión estadística que se denomina Finanzas para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="7fdba-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7fdba-492">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-492">Cost object</span></span></th>
<th><span data-ttu-id="7fdba-493">Servicios financieros</span><span class="sxs-lookup"><span data-stu-id="7fdba-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-494">CC003</span><span class="sxs-lookup"><span data-stu-id="7fdba-494">CC003</span></span></td>
<td><span data-ttu-id="7fdba-495">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="7fdba-495">Assembly</span></span></td>
<td><span data-ttu-id="7fdba-496">65</span><span class="sxs-lookup"><span data-stu-id="7fdba-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-497">CC004</span><span class="sxs-lookup"><span data-stu-id="7fdba-497">CC004</span></span></td>
<td><span data-ttu-id="7fdba-498">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="7fdba-498">Packaging</span></span></td>
<td><span data-ttu-id="7fdba-499">35</span><span class="sxs-lookup"><span data-stu-id="7fdba-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7fdba-500">El objeto de coste CC003 Asamblea contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="7fdba-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="7fdba-501">Se crea un miembro de dimensión estadística que se denomina servicios de Asamblea para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="7fdba-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7fdba-502">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-502">Cost object</span></span></th>
<th><span data-ttu-id="7fdba-503">Servicios de la asamblea (horas)</span><span class="sxs-lookup"><span data-stu-id="7fdba-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-504">Prod 1</span></span></td>
<td><span data-ttu-id="7fdba-505">Producto 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-505">Product 1</span></span></td>
<td><span data-ttu-id="7fdba-506">60</span><span class="sxs-lookup"><span data-stu-id="7fdba-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-507">Prod 2</span></span></td>
<td><span data-ttu-id="7fdba-508">Producto 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-508">Product 2</span></span></td>
<td><span data-ttu-id="7fdba-509">20</span><span class="sxs-lookup"><span data-stu-id="7fdba-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7fdba-510">El objeto de coste CC004 Embalaje contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="7fdba-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="7fdba-511">Se crea un miembro de dimensión estadística que se denomina servicios de Embalaje para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="7fdba-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7fdba-512">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-512">Cost object</span></span></th>
<th><span data-ttu-id="7fdba-513">Servicios de embalaje (horas)</span><span class="sxs-lookup"><span data-stu-id="7fdba-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-514">Prod 1</span></span></td>
<td><span data-ttu-id="7fdba-515">Producto 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-515">Product 1</span></span></td>
<td><span data-ttu-id="7fdba-516">80</span><span class="sxs-lookup"><span data-stu-id="7fdba-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-517">Prod 2</span></span></td>
<td><span data-ttu-id="7fdba-518">Producto 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-518">Product 2</span></span></td>
<td><span data-ttu-id="7fdba-519">15</span><span class="sxs-lookup"><span data-stu-id="7fdba-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="7fdba-520">Las medidas estadísticas como las horas de la producción que un producto consume se pueden deducir de los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="7fdba-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="7fdba-521">Para obtener más información, vea [Plantilla de proveedor de medidas estadísticas](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="7fdba-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="7fdba-522">La tabla siguiente muestra el resultado cuando se aplican los servicios de HR como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="7fdba-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7fdba-523">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-523">Cost object</span></span></th>
<th><span data-ttu-id="7fdba-524">Magnitud</span><span class="sxs-lookup"><span data-stu-id="7fdba-524">Magnitude</span></span></th>
<th><span data-ttu-id="7fdba-525">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="7fdba-525">Allocation factor</span></span></th>
<th><span data-ttu-id="7fdba-526">Importe</span><span class="sxs-lookup"><span data-stu-id="7fdba-526">Amount</span></span></th>
<th><span data-ttu-id="7fdba-527">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="7fdba-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-528">CC002</span><span class="sxs-lookup"><span data-stu-id="7fdba-528">CC002</span></span></td>
<td><span data-ttu-id="7fdba-529">Finanzas</span><span class="sxs-lookup"><span data-stu-id="7fdba-529">Finance</span></span></td>
<td><span data-ttu-id="7fdba-530">35</span><span class="sxs-lookup"><span data-stu-id="7fdba-530">35</span></span></td>
<td><span data-ttu-id="7fdba-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="7fdba-532">175.00</span><span class="sxs-lookup"><span data-stu-id="7fdba-532">175.00</span></span></td>
<td><span data-ttu-id="7fdba-533">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-534">CC003</span><span class="sxs-lookup"><span data-stu-id="7fdba-534">CC003</span></span></td>
<td><span data-ttu-id="7fdba-535">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="7fdba-535">Assembly</span></span></td>
<td><span data-ttu-id="7fdba-536">55</span><span class="sxs-lookup"><span data-stu-id="7fdba-536">55</span></span></td>
<td><span data-ttu-id="7fdba-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="7fdba-538">275.00</span><span class="sxs-lookup"><span data-stu-id="7fdba-538">275.00</span></span></td>
<td><span data-ttu-id="7fdba-539">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-540">CC004</span><span class="sxs-lookup"><span data-stu-id="7fdba-540">CC004</span></span></td>
<td><span data-ttu-id="7fdba-541">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="7fdba-541">Packaging</span></span></td>
<td><span data-ttu-id="7fdba-542">10</span><span class="sxs-lookup"><span data-stu-id="7fdba-542">10</span></span></td>
<td><span data-ttu-id="7fdba-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="7fdba-544">50,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-544">50.00</span></span></td>
<td><span data-ttu-id="7fdba-545">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-546">CC002</span><span class="sxs-lookup"><span data-stu-id="7fdba-546">CC002</span></span></td>
<td><span data-ttu-id="7fdba-547">Finanzas</span><span class="sxs-lookup"><span data-stu-id="7fdba-547">Finance</span></span></td>
<td><span data-ttu-id="7fdba-548">35</span><span class="sxs-lookup"><span data-stu-id="7fdba-548">35</span></span></td>
<td><span data-ttu-id="7fdba-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="7fdba-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="7fdba-550">436.00</span><span class="sxs-lookup"><span data-stu-id="7fdba-550">436.00</span></span></td>
<td><span data-ttu-id="7fdba-551">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-552">CC003</span><span class="sxs-lookup"><span data-stu-id="7fdba-552">CC003</span></span></td>
<td><span data-ttu-id="7fdba-553">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="7fdba-553">Assembly</span></span></td>
<td><span data-ttu-id="7fdba-554">55</span><span class="sxs-lookup"><span data-stu-id="7fdba-554">55</span></span></td>
<td><span data-ttu-id="7fdba-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="7fdba-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="7fdba-556">685.14</span><span class="sxs-lookup"><span data-stu-id="7fdba-556">685.14</span></span></td>
<td><span data-ttu-id="7fdba-557">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-558">CC004</span><span class="sxs-lookup"><span data-stu-id="7fdba-558">CC004</span></span></td>
<td><span data-ttu-id="7fdba-559">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="7fdba-559">Packaging</span></span></td>
<td><span data-ttu-id="7fdba-560">10</span><span class="sxs-lookup"><span data-stu-id="7fdba-560">10</span></span></td>
<td><span data-ttu-id="7fdba-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="7fdba-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="7fdba-562">124.57</span><span class="sxs-lookup"><span data-stu-id="7fdba-562">124.57</span></span></td>
<td><span data-ttu-id="7fdba-563">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7fdba-564">La tabla siguiente muestra el resultado cuando se aplican los servicios de Finanzas como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="7fdba-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7fdba-565">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-565">Cost object</span></span></th>
<th><span data-ttu-id="7fdba-566">Magnitud</span><span class="sxs-lookup"><span data-stu-id="7fdba-566">Magnitude</span></span></th>
<th><span data-ttu-id="7fdba-567">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="7fdba-567">Allocation factor</span></span></th>
<th><span data-ttu-id="7fdba-568">Importe</span><span class="sxs-lookup"><span data-stu-id="7fdba-568">Amount</span></span></th>
<th><span data-ttu-id="7fdba-569">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="7fdba-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-570">CC003</span><span class="sxs-lookup"><span data-stu-id="7fdba-570">CC003</span></span></td>
<td><span data-ttu-id="7fdba-571">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="7fdba-571">Assembly</span></span></td>
<td><span data-ttu-id="7fdba-572">65</span><span class="sxs-lookup"><span data-stu-id="7fdba-572">65</span></span></td>
<td><span data-ttu-id="7fdba-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="7fdba-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="7fdba-574">438.75</span><span class="sxs-lookup"><span data-stu-id="7fdba-574">438.75</span></span></td>
<td><span data-ttu-id="7fdba-575">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-576">CC004</span><span class="sxs-lookup"><span data-stu-id="7fdba-576">CC004</span></span></td>
<td><span data-ttu-id="7fdba-577">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="7fdba-577">Packaging</span></span></td>
<td><span data-ttu-id="7fdba-578">35</span><span class="sxs-lookup"><span data-stu-id="7fdba-578">35</span></span></td>
<td><span data-ttu-id="7fdba-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="7fdba-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="7fdba-580">236.25</span><span class="sxs-lookup"><span data-stu-id="7fdba-580">236.25</span></span></td>
<td><span data-ttu-id="7fdba-581">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-582">CC003</span><span class="sxs-lookup"><span data-stu-id="7fdba-582">CC003</span></span></td>
<td><span data-ttu-id="7fdba-583">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="7fdba-583">Assembly</span></span></td>
<td><span data-ttu-id="7fdba-584">65</span><span class="sxs-lookup"><span data-stu-id="7fdba-584">65</span></span></td>
<td><span data-ttu-id="7fdba-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="7fdba-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="7fdba-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="7fdba-586">5,297.69</span></span></td>
<td><span data-ttu-id="7fdba-587">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-588">CC004</span><span class="sxs-lookup"><span data-stu-id="7fdba-588">CC004</span></span></td>
<td><span data-ttu-id="7fdba-589">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="7fdba-589">Packaging</span></span></td>
<td><span data-ttu-id="7fdba-590">35</span><span class="sxs-lookup"><span data-stu-id="7fdba-590">35</span></span></td>
<td><span data-ttu-id="7fdba-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="7fdba-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="7fdba-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="7fdba-592">2,852.60</span></span></td>
<td><span data-ttu-id="7fdba-593">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7fdba-594">La tabla siguiente muestra el resultado cuando se aplican los servicios de Asamblea como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="7fdba-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7fdba-595">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-595">Cost object</span></span></th>
<th><span data-ttu-id="7fdba-596">Magnitud</span><span class="sxs-lookup"><span data-stu-id="7fdba-596">Magnitude</span></span></th>
<th><span data-ttu-id="7fdba-597">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="7fdba-597">Allocation factor</span></span></th>
<th><span data-ttu-id="7fdba-598">Importe</span><span class="sxs-lookup"><span data-stu-id="7fdba-598">Amount</span></span></th>
<th><span data-ttu-id="7fdba-599">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="7fdba-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-600">Prod 1</span></span></td>
<td><span data-ttu-id="7fdba-601">Producto 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-601">Product 1</span></span></td>
<td><span data-ttu-id="7fdba-602">60</span><span class="sxs-lookup"><span data-stu-id="7fdba-602">60</span></span></td>
<td><span data-ttu-id="7fdba-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="7fdba-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="7fdba-604">535.31</span><span class="sxs-lookup"><span data-stu-id="7fdba-604">535.31</span></span></td>
<td><span data-ttu-id="7fdba-605">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-606">Prod 2</span></span></td>
<td><span data-ttu-id="7fdba-607">Producto 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-607">Product 2</span></span></td>
<td><span data-ttu-id="7fdba-608">20</span><span class="sxs-lookup"><span data-stu-id="7fdba-608">20</span></span></td>
<td><span data-ttu-id="7fdba-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="7fdba-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="7fdba-610">178.44</span><span class="sxs-lookup"><span data-stu-id="7fdba-610">178.44</span></span></td>
<td><span data-ttu-id="7fdba-611">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-612">Prod 1</span></span></td>
<td><span data-ttu-id="7fdba-613">Producto 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-613">Product 1</span></span></td>
<td><span data-ttu-id="7fdba-614">60</span><span class="sxs-lookup"><span data-stu-id="7fdba-614">60</span></span></td>
<td><span data-ttu-id="7fdba-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="7fdba-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="7fdba-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="7fdba-616">4,487.12</span></span></td>
<td><span data-ttu-id="7fdba-617">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-618">Prod 2</span></span></td>
<td><span data-ttu-id="7fdba-619">Producto 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-619">Product 2</span></span></td>
<td><span data-ttu-id="7fdba-620">20</span><span class="sxs-lookup"><span data-stu-id="7fdba-620">20</span></span></td>
<td><span data-ttu-id="7fdba-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="7fdba-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="7fdba-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="7fdba-622">1,495.71</span></span></td>
<td><span data-ttu-id="7fdba-623">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7fdba-624">La tabla siguiente muestra el resultado cuando se aplican los servicios de Embalaje como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="7fdba-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7fdba-625">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-625">Cost object</span></span></th>
<th><span data-ttu-id="7fdba-626">Magnitud</span><span class="sxs-lookup"><span data-stu-id="7fdba-626">Magnitude</span></span></th>
<th><span data-ttu-id="7fdba-627">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="7fdba-627">Allocation factor</span></span></th>
<th><span data-ttu-id="7fdba-628">Importe</span><span class="sxs-lookup"><span data-stu-id="7fdba-628">Amount</span></span></th>
<th><span data-ttu-id="7fdba-629">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="7fdba-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-630">Prod 1</span></span></td>
<td><span data-ttu-id="7fdba-631">Producto 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-631">Product 1</span></span></td>
<td><span data-ttu-id="7fdba-632">80</span><span class="sxs-lookup"><span data-stu-id="7fdba-632">80</span></span></td>
<td><span data-ttu-id="7fdba-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="7fdba-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="7fdba-634">241.05</span><span class="sxs-lookup"><span data-stu-id="7fdba-634">241.05</span></span></td>
<td><span data-ttu-id="7fdba-635">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-636">Prod 2</span></span></td>
<td><span data-ttu-id="7fdba-637">Producto 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-637">Product 2</span></span></td>
<td><span data-ttu-id="7fdba-638">15</span><span class="sxs-lookup"><span data-stu-id="7fdba-638">15</span></span></td>
<td><span data-ttu-id="7fdba-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="7fdba-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="7fdba-640">45.20</span><span class="sxs-lookup"><span data-stu-id="7fdba-640">45.20</span></span></td>
<td><span data-ttu-id="7fdba-641">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-642">Prod 1</span></span></td>
<td><span data-ttu-id="7fdba-643">Producto 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-643">Product 1</span></span></td>
<td><span data-ttu-id="7fdba-644">80</span><span class="sxs-lookup"><span data-stu-id="7fdba-644">80</span></span></td>
<td><span data-ttu-id="7fdba-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="7fdba-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="7fdba-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="7fdba-646">2,507.09</span></span></td>
<td><span data-ttu-id="7fdba-647">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-648">Prod 2</span></span></td>
<td><span data-ttu-id="7fdba-649">Producto 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-649">Product 2</span></span></td>
<td><span data-ttu-id="7fdba-650">15</span><span class="sxs-lookup"><span data-stu-id="7fdba-650">15</span></span></td>
<td><span data-ttu-id="7fdba-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="7fdba-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="7fdba-652">470.08</span><span class="sxs-lookup"><span data-stu-id="7fdba-652">470.08</span></span></td>
<td><span data-ttu-id="7fdba-653">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="7fdba-654">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="7fdba-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="7fdba-655">Diario</span><span class="sxs-lookup"><span data-stu-id="7fdba-655">Journal</span></span></th>
<th><span data-ttu-id="7fdba-656">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="7fdba-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="7fdba-657">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="7fdba-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="7fdba-658">Versión</span><span class="sxs-lookup"><span data-stu-id="7fdba-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-659">00004</span><span class="sxs-lookup"><span data-stu-id="7fdba-659">00004</span></span></td>
<td><span data-ttu-id="7fdba-660">Diario de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="7fdba-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="7fdba-661">Fiscal</span><span class="sxs-lookup"><span data-stu-id="7fdba-661">Fiscal</span></span></td>
<td><span data-ttu-id="7fdba-662">2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-662">2017</span></span></td>
<td><span data-ttu-id="7fdba-663">Período 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-663">Period 1</span></span></td>
<td><span data-ttu-id="7fdba-664">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="7fdba-665">Líneas de diario</span><span class="sxs-lookup"><span data-stu-id="7fdba-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="7fdba-666">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="7fdba-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="7fdba-667">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="7fdba-668">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-668">Cost element</span></span></th>
<th><span data-ttu-id="7fdba-669">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="7fdba-669">Cost behavior</span></span></th>
<th><span data-ttu-id="7fdba-670">Importe</span><span class="sxs-lookup"><span data-stu-id="7fdba-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-671">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="7fdba-672">CC001</span><span class="sxs-lookup"><span data-stu-id="7fdba-672">CC001</span></span></td>
<td><span data-ttu-id="7fdba-673">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="7fdba-673">HR</span></span></td>
<td><span data-ttu-id="7fdba-674">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-674">10001</span></span></td>
<td><span data-ttu-id="7fdba-675">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-675">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-676">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-676">Fixed cost</span></span></td>
<td><span data-ttu-id="7fdba-677">500,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-678">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="7fdba-679">CC001</span><span class="sxs-lookup"><span data-stu-id="7fdba-679">CC001</span></span></td>
<td><span data-ttu-id="7fdba-680">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="7fdba-680">HR</span></span></td>
<td><span data-ttu-id="7fdba-681">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-681">10001</span></span></td>
<td><span data-ttu-id="7fdba-682">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-682">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-683">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-683">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="7fdba-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-685">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="7fdba-686">CC002</span><span class="sxs-lookup"><span data-stu-id="7fdba-686">CC002</span></span></td>
<td><span data-ttu-id="7fdba-687">Finanzas</span><span class="sxs-lookup"><span data-stu-id="7fdba-687">Finance</span></span></td>
<td><span data-ttu-id="7fdba-688">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-688">10001</span></span></td>
<td><span data-ttu-id="7fdba-689">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-689">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-690">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-690">Fixed cost</span></span></td>
<td><span data-ttu-id="7fdba-691">675.00</span><span class="sxs-lookup"><span data-stu-id="7fdba-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-692">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="7fdba-693">CC002</span><span class="sxs-lookup"><span data-stu-id="7fdba-693">CC002</span></span></td>
<td><span data-ttu-id="7fdba-694">Finanzas</span><span class="sxs-lookup"><span data-stu-id="7fdba-694">Finance</span></span></td>
<td><span data-ttu-id="7fdba-695">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-695">10001</span></span></td>
<td><span data-ttu-id="7fdba-696">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-696">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-697">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-697">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="7fdba-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-699">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="7fdba-700">CC003</span><span class="sxs-lookup"><span data-stu-id="7fdba-700">CC003</span></span></td>
<td><span data-ttu-id="7fdba-701">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="7fdba-701">Assembly</span></span></td>
<td><span data-ttu-id="7fdba-702">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-702">10001</span></span></td>
<td><span data-ttu-id="7fdba-703">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-703">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-704">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-704">Fixed cost</span></span></td>
<td><span data-ttu-id="7fdba-705">713.75</span><span class="sxs-lookup"><span data-stu-id="7fdba-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-706">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="7fdba-707">CC003</span><span class="sxs-lookup"><span data-stu-id="7fdba-707">CC003</span></span></td>
<td><span data-ttu-id="7fdba-708">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="7fdba-708">Assembly</span></span></td>
<td><span data-ttu-id="7fdba-709">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-709">10001</span></span></td>
<td><span data-ttu-id="7fdba-710">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-710">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-711">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-711">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="7fdba-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-713">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="7fdba-714">CC003</span><span class="sxs-lookup"><span data-stu-id="7fdba-714">CC003</span></span></td>
<td><span data-ttu-id="7fdba-715">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="7fdba-715">Packaging</span></span></td>
<td><span data-ttu-id="7fdba-716">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-716">10001</span></span></td>
<td><span data-ttu-id="7fdba-717">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-717">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-718">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-718">Fixed cost</span></span></td>
<td><span data-ttu-id="7fdba-719">286.25</span><span class="sxs-lookup"><span data-stu-id="7fdba-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-720">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="7fdba-721">CC003</span><span class="sxs-lookup"><span data-stu-id="7fdba-721">CC003</span></span></td>
<td><span data-ttu-id="7fdba-722">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="7fdba-722">Packaging</span></span></td>
<td><span data-ttu-id="7fdba-723">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-723">10001</span></span></td>
<td><span data-ttu-id="7fdba-724">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-724">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-725">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-725">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="7fdba-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-727">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="7fdba-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-728">Prod 1</span></span></td>
<td><span data-ttu-id="7fdba-729">Producto 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-729">Product 1</span></span></td>
<td><span data-ttu-id="7fdba-730">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-730">10001</span></span></td>
<td><span data-ttu-id="7fdba-731">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-731">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-732">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-732">Fixed cost</span></span></td>
<td><span data-ttu-id="7fdba-733">776.36</span><span class="sxs-lookup"><span data-stu-id="7fdba-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-734">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="7fdba-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-735">Prod 1</span></span></td>
<td><span data-ttu-id="7fdba-736">Producto 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-736">Product 1</span></span></td>
<td><span data-ttu-id="7fdba-737">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-737">10001</span></span></td>
<td><span data-ttu-id="7fdba-738">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-738">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-739">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-739">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="7fdba-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-741">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="7fdba-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-742">Prod 2</span></span></td>
<td><span data-ttu-id="7fdba-743">Producto 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-743">Product 1</span></span></td>
<td><span data-ttu-id="7fdba-744">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-744">10001</span></span></td>
<td><span data-ttu-id="7fdba-745">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-745">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-746">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-746">Fixed cost</span></span></td>
<td><span data-ttu-id="7fdba-747">223.64</span><span class="sxs-lookup"><span data-stu-id="7fdba-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-748">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="7fdba-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-749">Prod 2</span></span></td>
<td><span data-ttu-id="7fdba-750">Producto 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-750">Product 1</span></span></td>
<td><span data-ttu-id="7fdba-751">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-751">10001</span></span></td>
<td><span data-ttu-id="7fdba-752">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-752">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-753">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-753">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="7fdba-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="7fdba-755">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="7fdba-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="7fdba-756">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="7fdba-757">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-757">Cost element</span></span></th>
<th><span data-ttu-id="7fdba-758">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="7fdba-758">Cost behavior</span></span></th>
<th><span data-ttu-id="7fdba-759">Importe</span><span class="sxs-lookup"><span data-stu-id="7fdba-759">Amount</span></span></th>
<th><span data-ttu-id="7fdba-760">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="7fdba-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7fdba-761">CC001</span><span class="sxs-lookup"><span data-stu-id="7fdba-761">CC001</span></span></td>
<td><span data-ttu-id="7fdba-762">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="7fdba-762">HR</span></span></td>
<td><span data-ttu-id="7fdba-763">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-763">10001</span></span></td>
<td><span data-ttu-id="7fdba-764">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-764">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-765">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-765">Fixed cost</span></span></td>
<td><span data-ttu-id="7fdba-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-766">-500.00</span></span></td>
<td><span data-ttu-id="7fdba-767">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-768">CC002</span><span class="sxs-lookup"><span data-stu-id="7fdba-768">CC002</span></span></td>
<td><span data-ttu-id="7fdba-769">Finanzas</span><span class="sxs-lookup"><span data-stu-id="7fdba-769">Finance</span></span></td>
<td><span data-ttu-id="7fdba-770">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-770">10001</span></span></td>
<td><span data-ttu-id="7fdba-771">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-771">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-772">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-772">Fixed cost</span></span></td>
<td><span data-ttu-id="7fdba-773">175.00</span><span class="sxs-lookup"><span data-stu-id="7fdba-773">175.00</span></span></td>
<td><span data-ttu-id="7fdba-774">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-775">CC003</span><span class="sxs-lookup"><span data-stu-id="7fdba-775">CC003</span></span></td>
<td><span data-ttu-id="7fdba-776">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="7fdba-776">Assembly</span></span></td>
<td><span data-ttu-id="7fdba-777">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-777">10001</span></span></td>
<td><span data-ttu-id="7fdba-778">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-778">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-779">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-779">Fixed cost</span></span></td>
<td><span data-ttu-id="7fdba-780">275.00</span><span class="sxs-lookup"><span data-stu-id="7fdba-780">275.00</span></span></td>
<td><span data-ttu-id="7fdba-781">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-782">CC004</span><span class="sxs-lookup"><span data-stu-id="7fdba-782">CC004</span></span></td>
<td><span data-ttu-id="7fdba-783">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="7fdba-783">Packaging</span></span></td>
<td><span data-ttu-id="7fdba-784">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-784">10001</span></span></td>
<td><span data-ttu-id="7fdba-785">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-785">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-786">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-786">Fixed cost</span></span></td>
<td><span data-ttu-id="7fdba-787">50,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-787">50,00</span></span></td>
<td><span data-ttu-id="7fdba-788">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-789">CC001</span><span class="sxs-lookup"><span data-stu-id="7fdba-789">CC001</span></span></td>
<td><span data-ttu-id="7fdba-790">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="7fdba-790">HR</span></span></td>
<td><span data-ttu-id="7fdba-791">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-791">10001</span></span></td>
<td><span data-ttu-id="7fdba-792">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-792">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-793">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-793">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="7fdba-794">-1,245.71</span></span></td>
<td><span data-ttu-id="7fdba-795">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-796">CC002</span><span class="sxs-lookup"><span data-stu-id="7fdba-796">CC002</span></span></td>
<td><span data-ttu-id="7fdba-797">Finanzas</span><span class="sxs-lookup"><span data-stu-id="7fdba-797">Finance</span></span></td>
<td><span data-ttu-id="7fdba-798">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-798">10001</span></span></td>
<td><span data-ttu-id="7fdba-799">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-799">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-800">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-800">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-801">436.00</span><span class="sxs-lookup"><span data-stu-id="7fdba-801">436.00</span></span></td>
<td><span data-ttu-id="7fdba-802">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-803">CC003</span><span class="sxs-lookup"><span data-stu-id="7fdba-803">CC003</span></span></td>
<td><span data-ttu-id="7fdba-804">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="7fdba-804">Assembly</span></span></td>
<td><span data-ttu-id="7fdba-805">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-805">10001</span></span></td>
<td><span data-ttu-id="7fdba-806">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-806">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-807">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-807">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-808">685.14</span><span class="sxs-lookup"><span data-stu-id="7fdba-808">685.14</span></span></td>
<td><span data-ttu-id="7fdba-809">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-810">CC004</span><span class="sxs-lookup"><span data-stu-id="7fdba-810">CC004</span></span></td>
<td><span data-ttu-id="7fdba-811">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="7fdba-811">Packaging</span></span></td>
<td><span data-ttu-id="7fdba-812">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-812">10001</span></span></td>
<td><span data-ttu-id="7fdba-813">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-813">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-814">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-814">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-815">124.57</span><span class="sxs-lookup"><span data-stu-id="7fdba-815">124.57</span></span></td>
<td><span data-ttu-id="7fdba-816">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-817">CC002</span><span class="sxs-lookup"><span data-stu-id="7fdba-817">CC002</span></span></td>
<td><span data-ttu-id="7fdba-818">Finanzas</span><span class="sxs-lookup"><span data-stu-id="7fdba-818">Finance</span></span></td>
<td><span data-ttu-id="7fdba-819">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-819">10001</span></span></td>
<td><span data-ttu-id="7fdba-820">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-820">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-821">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-821">Fixed cost</span></span></td>
<td><span data-ttu-id="7fdba-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-822">-675.00</span></span></td>
<td><span data-ttu-id="7fdba-823">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-824">CC003</span><span class="sxs-lookup"><span data-stu-id="7fdba-824">CC003</span></span></td>
<td><span data-ttu-id="7fdba-825">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="7fdba-825">Assembly</span></span></td>
<td><span data-ttu-id="7fdba-826">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-826">10001</span></span></td>
<td><span data-ttu-id="7fdba-827">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-827">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-828">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-828">Fixed cost</span></span></td>
<td><span data-ttu-id="7fdba-829">438.75</span><span class="sxs-lookup"><span data-stu-id="7fdba-829">438.75</span></span></td>
<td><span data-ttu-id="7fdba-830">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-831">CC004</span><span class="sxs-lookup"><span data-stu-id="7fdba-831">CC004</span></span></td>
<td><span data-ttu-id="7fdba-832">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="7fdba-832">Packaging</span></span></td>
<td><span data-ttu-id="7fdba-833">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-833">10001</span></span></td>
<td><span data-ttu-id="7fdba-834">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-834">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-835">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-835">Fixed cost</span></span></td>
<td><span data-ttu-id="7fdba-836">236.25</span><span class="sxs-lookup"><span data-stu-id="7fdba-836">236.25</span></span></td>
<td><span data-ttu-id="7fdba-837">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-838">CC002</span><span class="sxs-lookup"><span data-stu-id="7fdba-838">CC002</span></span></td>
<td><span data-ttu-id="7fdba-839">Finanzas</span><span class="sxs-lookup"><span data-stu-id="7fdba-839">Finance</span></span></td>
<td><span data-ttu-id="7fdba-840">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-840">10001</span></span></td>
<td><span data-ttu-id="7fdba-841">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-841">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-842">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-842">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="7fdba-843">-8,150.29</span></span></td>
<td><span data-ttu-id="7fdba-844">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-845">CC003</span><span class="sxs-lookup"><span data-stu-id="7fdba-845">CC003</span></span></td>
<td><span data-ttu-id="7fdba-846">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="7fdba-846">Assembly</span></span></td>
<td><span data-ttu-id="7fdba-847">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-847">10001</span></span></td>
<td><span data-ttu-id="7fdba-848">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-848">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-849">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-849">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="7fdba-850">5,297.69</span></span></td>
<td><span data-ttu-id="7fdba-851">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-852">CC004</span><span class="sxs-lookup"><span data-stu-id="7fdba-852">CC004</span></span></td>
<td><span data-ttu-id="7fdba-853">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="7fdba-853">Packaging</span></span></td>
<td><span data-ttu-id="7fdba-854">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-854">10001</span></span></td>
<td><span data-ttu-id="7fdba-855">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-855">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-856">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-856">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="7fdba-857">2,852.60</span></span></td>
<td><span data-ttu-id="7fdba-858">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-859">CC003</span><span class="sxs-lookup"><span data-stu-id="7fdba-859">CC003</span></span></td>
<td><span data-ttu-id="7fdba-860">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="7fdba-860">Assembly</span></span></td>
<td><span data-ttu-id="7fdba-861">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-861">10001</span></span></td>
<td><span data-ttu-id="7fdba-862">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-862">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-863">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-863">Fixed cost</span></span></td>
<td><span data-ttu-id="7fdba-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="7fdba-864">-713.75</span></span></td>
<td><span data-ttu-id="7fdba-865">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-866">Prod 1</span></span></td>
<td><span data-ttu-id="7fdba-867">Producto 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-867">Product 1</span></span></td>
<td><span data-ttu-id="7fdba-868">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-868">10001</span></span></td>
<td><span data-ttu-id="7fdba-869">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-869">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-870">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-870">Fixed cost</span></span></td>
<td><span data-ttu-id="7fdba-871">535.31</span><span class="sxs-lookup"><span data-stu-id="7fdba-871">535.31</span></span></td>
<td><span data-ttu-id="7fdba-872">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-873">Prod 2</span></span></td>
<td><span data-ttu-id="7fdba-874">Producto 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-874">Product 2</span></span></td>
<td><span data-ttu-id="7fdba-875">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-875">10001</span></span></td>
<td><span data-ttu-id="7fdba-876">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-876">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-877">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-877">Fixed cost</span></span></td>
<td><span data-ttu-id="7fdba-878">178.44</span><span class="sxs-lookup"><span data-stu-id="7fdba-878">178.44</span></span></td>
<td><span data-ttu-id="7fdba-879">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-880">CC003</span><span class="sxs-lookup"><span data-stu-id="7fdba-880">CC003</span></span></td>
<td><span data-ttu-id="7fdba-881">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="7fdba-881">Assembly</span></span></td>
<td><span data-ttu-id="7fdba-882">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-882">10001</span></span></td>
<td><span data-ttu-id="7fdba-883">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-883">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-884">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-884">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="7fdba-885">-5,982.83</span></span></td>
<td><span data-ttu-id="7fdba-886">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-887">Prod 1</span></span></td>
<td><span data-ttu-id="7fdba-888">Producto 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-888">Product 1</span></span></td>
<td><span data-ttu-id="7fdba-889">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-889">10001</span></span></td>
<td><span data-ttu-id="7fdba-890">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-890">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-891">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-891">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="7fdba-892">4,487.12</span></span></td>
<td><span data-ttu-id="7fdba-893">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-894">Prod 2</span></span></td>
<td><span data-ttu-id="7fdba-895">Producto 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-895">Product 2</span></span></td>
<td><span data-ttu-id="7fdba-896">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-896">10001</span></span></td>
<td><span data-ttu-id="7fdba-897">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-897">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-898">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-898">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="7fdba-899">1,495.71</span></span></td>
<td><span data-ttu-id="7fdba-900">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-901">CC003</span><span class="sxs-lookup"><span data-stu-id="7fdba-901">CC003</span></span></td>
<td><span data-ttu-id="7fdba-902">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="7fdba-902">Assembly</span></span></td>
<td><span data-ttu-id="7fdba-903">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-903">10001</span></span></td>
<td><span data-ttu-id="7fdba-904">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-904">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-905">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-905">Fixed cost</span></span></td>
<td><span data-ttu-id="7fdba-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="7fdba-906">-286.25</span></span></td>
<td><span data-ttu-id="7fdba-907">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-908">Prod 1</span></span></td>
<td><span data-ttu-id="7fdba-909">Producto 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-909">Product 1</span></span></td>
<td><span data-ttu-id="7fdba-910">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-910">10001</span></span></td>
<td><span data-ttu-id="7fdba-911">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-911">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-912">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-912">Fixed cost</span></span></td>
<td><span data-ttu-id="7fdba-913">241.05</span><span class="sxs-lookup"><span data-stu-id="7fdba-913">241.05</span></span></td>
<td><span data-ttu-id="7fdba-914">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-915">Prod 2</span></span></td>
<td><span data-ttu-id="7fdba-916">Producto 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-916">Product 2</span></span></td>
<td><span data-ttu-id="7fdba-917">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-917">10001</span></span></td>
<td><span data-ttu-id="7fdba-918">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-918">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-919">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-919">Fixed cost</span></span></td>
<td><span data-ttu-id="7fdba-920">45.20</span><span class="sxs-lookup"><span data-stu-id="7fdba-920">45.20</span></span></td>
<td><span data-ttu-id="7fdba-921">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-922">CC003</span><span class="sxs-lookup"><span data-stu-id="7fdba-922">CC003</span></span></td>
<td><span data-ttu-id="7fdba-923">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="7fdba-923">Assembly</span></span></td>
<td><span data-ttu-id="7fdba-924">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-924">10001</span></span></td>
<td><span data-ttu-id="7fdba-925">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-925">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-926">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-926">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="7fdba-927">-2,977.17</span></span></td>
<td><span data-ttu-id="7fdba-928">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-929">Prod 1</span></span></td>
<td><span data-ttu-id="7fdba-930">Producto 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-930">Product 1</span></span></td>
<td><span data-ttu-id="7fdba-931">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-931">10001</span></span></td>
<td><span data-ttu-id="7fdba-932">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-932">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-933">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-933">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="7fdba-934">2,507.09</span></span></td>
<td><span data-ttu-id="7fdba-935">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7fdba-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-936">Prod 2</span></span></td>
<td><span data-ttu-id="7fdba-937">Producto 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-937">Product 2</span></span></td>
<td><span data-ttu-id="7fdba-938">10001</span><span class="sxs-lookup"><span data-stu-id="7fdba-938">10001</span></span></td>
<td><span data-ttu-id="7fdba-939">Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-939">Electricity</span></span></td>
<td><span data-ttu-id="7fdba-940">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-940">Variable cost</span></span></td>
<td><span data-ttu-id="7fdba-941">470.08</span><span class="sxs-lookup"><span data-stu-id="7fdba-941">470.08</span></span></td>
<td><span data-ttu-id="7fdba-942">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="7fdba-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="7fdba-943">Conclusión</span><span class="sxs-lookup"><span data-stu-id="7fdba-943">Conclusion</span></span>
<span data-ttu-id="7fdba-944">En la contabilidad financiera, un coste de 10.000,00 para electricidad se envía a un identificador ficticio de centro de coste.</span><span class="sxs-lookup"><span data-stu-id="7fdba-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="7fdba-945">Por lo tanto, los contables de coste sabrán que este coste se debe asignar.</span><span class="sxs-lookup"><span data-stu-id="7fdba-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="7fdba-946">En contabilidad de costes, los costes fluyen en las unidades organizativas y los niveles en función de las directivas y las reglas que se aplican.</span><span class="sxs-lookup"><span data-stu-id="7fdba-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="7fdba-947">Cada coste se ha asociado con una base de asignación que proporciona la mejor evaluación para la asignación de costes.</span><span class="sxs-lookup"><span data-stu-id="7fdba-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="7fdba-948">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="7fdba-949">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="7fdba-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="7fdba-950">Total</span><span class="sxs-lookup"><span data-stu-id="7fdba-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="7fdba-951">CC099</span><span class="sxs-lookup"><span data-stu-id="7fdba-951">CC099</span></span></th>
<th><span data-ttu-id="7fdba-952">CC001</span><span class="sxs-lookup"><span data-stu-id="7fdba-952">CC001</span></span></th>
<th><span data-ttu-id="7fdba-953">CC002</span><span class="sxs-lookup"><span data-stu-id="7fdba-953">CC002</span></span></th>
<th><span data-ttu-id="7fdba-954">CC003</span><span class="sxs-lookup"><span data-stu-id="7fdba-954">CC003</span></span></th>
<th><span data-ttu-id="7fdba-955">CC004</span><span class="sxs-lookup"><span data-stu-id="7fdba-955">CC004</span></span></th>
<th><span data-ttu-id="7fdba-956">Proy 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-956">Proj 1</span></span></th>
<th><span data-ttu-id="7fdba-957">Proy 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-957">Proj 2</span></span></th>
<th><span data-ttu-id="7fdba-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="7fdba-958">Prod 1</span></span></th>
<th><span data-ttu-id="7fdba-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="7fdba-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="7fdba-960">10001 Electricidad</span><span class="sxs-lookup"><span data-stu-id="7fdba-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="7fdba-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="7fdba-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="7fdba-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="7fdba-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="7fdba-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="7fdba-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="7fdba-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="7fdba-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="7fdba-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="7fdba-970">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="7fdba-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-971">0,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="7fdba-972">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="7fdba-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-973">0,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-974">0,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-975">0,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-976">0,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-977">0,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-978">776.36</span><span class="sxs-lookup"><span data-stu-id="7fdba-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-979">223.64</span><span class="sxs-lookup"><span data-stu-id="7fdba-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="7fdba-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="7fdba-981">Coste variable</span><span class="sxs-lookup"><span data-stu-id="7fdba-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-982">000</span><span class="sxs-lookup"><span data-stu-id="7fdba-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-983">0,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-984">0,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-985">0,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-986">0,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-987">30,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-988">10,00</span><span class="sxs-lookup"><span data-stu-id="7fdba-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="7fdba-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="7fdba-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="7fdba-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="7fdba-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="7fdba-992">Este tema muestra cómo un artículo de costes principales, 10001 Electricidad, fluye por los objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="7fdba-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="7fdba-993">Por tanto, estos gastos generales se asignan al nivel más bajo de la organización.</span><span class="sxs-lookup"><span data-stu-id="7fdba-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="7fdba-994">Es decir, los objetos de coste del nivel más bajo son los que soportan el coste.</span><span class="sxs-lookup"><span data-stu-id="7fdba-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="7fdba-995">Si necesita un flujo visual del coste entre los objetos de coste, puede usar las reglas de directivas de acumulación de costes para visualizar el flujo del coste.</span><span class="sxs-lookup"><span data-stu-id="7fdba-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="7fdba-996">Para obtener más información, consulte [Directiva de acumulación de costes y cálculo de costes generales](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="7fdba-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



