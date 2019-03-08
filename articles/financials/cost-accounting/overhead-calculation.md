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
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 4de705324ac497cfb11fae3dadc6f57d038fd0b5
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "335126"
---
# <a name="overhead-calculation"></a><span data-ttu-id="ed9eb-103">Cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="ed9eb-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ed9eb-104">Este tema describe los procesos típicos para calcular y asignar costes generales.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="ed9eb-105">Definición del término</span><span class="sxs-lookup"><span data-stu-id="ed9eb-105">Term definition</span></span>
---------------

<span data-ttu-id="ed9eb-106">Los costes generales son costes que se contraen para dirigir un negocio, pero que no pueden ser atribuidos directamente a ninguna actividad empresarial, productos, o servicio específicos.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="ed9eb-107">Los costes generales proporcionan un soporte fundamental a la generación de actividades rentables.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="ed9eb-108">Algunos ejemplos de costes generales son:</span><span class="sxs-lookup"><span data-stu-id="ed9eb-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="ed9eb-109">Alquiler</span><span class="sxs-lookup"><span data-stu-id="ed9eb-109">Rent</span></span>
-   <span data-ttu-id="ed9eb-110">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-110">Electricity</span></span>
-   <span data-ttu-id="ed9eb-111">Sueldos administrativos</span><span class="sxs-lookup"><span data-stu-id="ed9eb-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="ed9eb-112">Visión general del cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="ed9eb-112">Overhead calculation overview</span></span>
<span data-ttu-id="ed9eb-113">El cálculo de costes generales ejecuta las directivas de contabilidad de costes en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="ed9eb-114">Puede calcular varias veces los costes generales del mismo período fiscal si se han cambiado las directivas de contabilidad de costes o se han detectado errores específicos.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="ed9eb-115">Cada ejecución del cálculo de costes generales se almacena y recibe un identificador de versión único que permite comparar los cálculos de diferentes versiones.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="ed9eb-116">Las entradas de costes que el cálculo de costes generales genera reciben una fecha de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="ed9eb-117">Esta fecha de contabilidad coincide con la fecha final del período fiscal que se usa en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="ed9eb-118">El identificador de versión único consiste en los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ed9eb-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="ed9eb-119">Tipo de versión</span><span class="sxs-lookup"><span data-stu-id="ed9eb-119">Version type</span></span>
-   <span data-ttu-id="ed9eb-120">Fecha y hora</span><span class="sxs-lookup"><span data-stu-id="ed9eb-120">Date and time</span></span>
-   <span data-ttu-id="ed9eb-121">Libro mayor de contabilidad de costes</span><span class="sxs-lookup"><span data-stu-id="ed9eb-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="ed9eb-122">Ejercicio</span><span class="sxs-lookup"><span data-stu-id="ed9eb-122">Fiscal year</span></span>
-   <span data-ttu-id="ed9eb-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="ed9eb-123">Fiscal period</span></span>

<span data-ttu-id="ed9eb-124">El cálculo de costes generales se ejecuta independientemente de la versión.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="ed9eb-125">Por lo tanto, puede calcular la versión de presupuesto antes que la versión real.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="ed9eb-126">El cálculo de costes generales consta de cuatro pasos, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="ed9eb-127">En cada paso, se crea una cabecera de diario que tiene entradas del diario.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="ed9eb-128">Esta cabecera de diario guarda los datos de entrada para cada paso de cálculo.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="ed9eb-129">Las directivas y las reglas se aplican a cada línea de diario, y las entradas de coste se generan como resultado.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="ed9eb-130">Por tanto, siempre se tiene rastreabilidad completa.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="ed9eb-131">[![Cálculo de costes generales](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="ed9eb-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="ed9eb-132">Calcular y asignar costes generales de electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="ed9eb-133">En la contabilidad financiera, algunos costes, como la electricidad, se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="ed9eb-134">Por lo tanto, no se proporciona una visión de gestión detallada para la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="ed9eb-135">En contabilidad de costes, para proporcionar información de gestión correcta en todas las unidades y niveles organizativos, los costes deben fluir por las unidades organizativas.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="ed9eb-136">Este flujo se debe basar en cualquier registro preciso de consumo o en una evaluación justa.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="ed9eb-137">En la contabilidad general, un coste de la electricidad se puede registrar como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ed9eb-138">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ed9eb-139">Centro de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="ed9eb-140">Cuenta principal</span><span class="sxs-lookup"><span data-stu-id="ed9eb-140">Main account</span></span></th>
<th><span data-ttu-id="ed9eb-141">Importe en la divisa de contabilidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-142">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="ed9eb-143">CC099</span><span class="sxs-lookup"><span data-stu-id="ed9eb-143">CC099</span></span></td>
<td><span data-ttu-id="ed9eb-144">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-144">Default cost center</span></span></td>
<td><span data-ttu-id="ed9eb-145">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-145">10001</span></span></td>
<td><span data-ttu-id="ed9eb-146">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-146">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="ed9eb-148">Paso 1: Procese el cálculo del comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="ed9eb-149">De forma predeterminada, cuando las entradas de coste se importan de los datos de origen, reciben la clasificación de comportamiento del coste **Sin ordenar** en la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="ed9eb-150">Aplicando reglas de directivas de comportamiento de coste, puede reclasificar entradas de coste como **Coste fijo** o **Coste variable**.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="ed9eb-151">Defina la regla de comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-151">Define the cost behavior rule</span></span>

<span data-ttu-id="ed9eb-152">En algunos casos, parte del coste es una cuota fija, y el coste pendiente se basa en el consumo.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="ed9eb-153">Las facturas de electricidad coinciden a menudo con esta definición.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="ed9eb-154">Tras pagar una cuota fija específica, paga el consumo por kilovatio-hora (Kwh).</span><span class="sxs-lookup"><span data-stu-id="ed9eb-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="ed9eb-155">Por ejemplo, si la cuota de coste fijo es de 1.000,00, la regla de comportamiento del coste se define como sigue:</span><span class="sxs-lookup"><span data-stu-id="ed9eb-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="ed9eb-156">Importe fijo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="ed9eb-157">0 &lt;= 1.000,00 = Fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="ed9eb-158">1.000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="ed9eb-159">Diario</span><span class="sxs-lookup"><span data-stu-id="ed9eb-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ed9eb-160">Diario</span><span class="sxs-lookup"><span data-stu-id="ed9eb-160">Journal</span></span></th>
<th><span data-ttu-id="ed9eb-161">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="ed9eb-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ed9eb-162">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="ed9eb-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ed9eb-163">Versión</span><span class="sxs-lookup"><span data-stu-id="ed9eb-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-164">00001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-164">00001</span></span></td>
<td><span data-ttu-id="ed9eb-165">Diario de cálculo de comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="ed9eb-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="ed9eb-166">Fiscal</span><span class="sxs-lookup"><span data-stu-id="ed9eb-166">Fiscal</span></span></td>
<td><span data-ttu-id="ed9eb-167">2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-167">2017</span></span></td>
<td><span data-ttu-id="ed9eb-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-168">Period 1</span></span></td>
<td><span data-ttu-id="ed9eb-169">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="ed9eb-170">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="ed9eb-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ed9eb-171">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ed9eb-172">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ed9eb-173">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-173">Cost element</span></span></th>
<th><span data-ttu-id="ed9eb-174">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="ed9eb-174">Cost behavior</span></span></th>
<th><span data-ttu-id="ed9eb-175">Importe</span><span class="sxs-lookup"><span data-stu-id="ed9eb-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-176">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="ed9eb-177">CC099</span><span class="sxs-lookup"><span data-stu-id="ed9eb-177">CC099</span></span></td>
<td><span data-ttu-id="ed9eb-178">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-178">Default cost center</span></span></td>
<td><span data-ttu-id="ed9eb-179">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-179">10001</span></span></td>
<td><span data-ttu-id="ed9eb-180">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-180">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-181">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="ed9eb-181">Unclassified</span></span></td>
<td><span data-ttu-id="ed9eb-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ed9eb-183">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="ed9eb-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ed9eb-184">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ed9eb-185">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-185">Cost element</span></span></th>
<th><span data-ttu-id="ed9eb-186">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="ed9eb-186">Cost behavior</span></span></th>
<th><span data-ttu-id="ed9eb-187">Importe</span><span class="sxs-lookup"><span data-stu-id="ed9eb-187">Amount</span></span></th>
<th><span data-ttu-id="ed9eb-188">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-189">CC099</span><span class="sxs-lookup"><span data-stu-id="ed9eb-189">CC099</span></span></td>
<td><span data-ttu-id="ed9eb-190">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-190">Default cost center</span></span></td>
<td><span data-ttu-id="ed9eb-191">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-191">10001</span></span></td>
<td><span data-ttu-id="ed9eb-192">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-192">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-193">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="ed9eb-193">Unclassified</span></span></td>
<td><span data-ttu-id="ed9eb-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-194">10,000.00</span></span></td>
<td><span data-ttu-id="ed9eb-195">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-196">CC099</span><span class="sxs-lookup"><span data-stu-id="ed9eb-196">CC099</span></span></td>
<td><span data-ttu-id="ed9eb-197">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-197">Default cost center</span></span></td>
<td><span data-ttu-id="ed9eb-198">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-198">10001</span></span></td>
<td><span data-ttu-id="ed9eb-199">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-199">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-200">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="ed9eb-200">Unclassified</span></span></td>
<td><span data-ttu-id="ed9eb-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-201">-10,000.00</span></span></td>
<td><span data-ttu-id="ed9eb-202">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-203">CC099</span><span class="sxs-lookup"><span data-stu-id="ed9eb-203">CC099</span></span></td>
<td><span data-ttu-id="ed9eb-204">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-204">Default cost center</span></span></td>
<td><span data-ttu-id="ed9eb-205">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-205">10001</span></span></td>
<td><span data-ttu-id="ed9eb-206">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-206">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-207">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-207">Fixed cost</span></span></td>
<td><span data-ttu-id="ed9eb-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-208">1,000.00</span></span></td>
<td><span data-ttu-id="ed9eb-209">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-210">CC099</span><span class="sxs-lookup"><span data-stu-id="ed9eb-210">CC099</span></span></td>
<td><span data-ttu-id="ed9eb-211">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-211">Default cost center</span></span></td>
<td><span data-ttu-id="ed9eb-212">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-212">10001</span></span></td>
<td><span data-ttu-id="ed9eb-213">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-213">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-214">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-214">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-215">9,000.00</span></span></td>
<td><span data-ttu-id="ed9eb-216">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ed9eb-217">Para obtener más información, consulte [Crear y asignar una directiva de comportamiento de costes a una unidad de control de costes](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="ed9eb-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="ed9eb-218">Paso 2: Procese el cálculo de distribución de costes</span><span class="sxs-lookup"><span data-stu-id="ed9eb-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="ed9eb-219">La distribución de costes se usa para redistribuir costes desde un objeto de coste a uno o más objetos de coste aplicando una base relevante de la asignación.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="ed9eb-220">La distribución de costes y la asignación de costes difieren en que la distribución de costes siempre se produce en el nivel de elemento de costes principal del coste original.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="ed9eb-221">Defina la regla de distribución del coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-221">Define the cost distribution rule</span></span>

<span data-ttu-id="ed9eb-222">En la contabilidad financiera, los costes de electricidad se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="ed9eb-223">En contabilidad de costes, este método no es suficientemente detallado.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="ed9eb-224">El coste variable debe distribuirse a los objetos individuales de coste aplicando una base justa.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="ed9eb-225">La base de asignación más lógica es el consumo de electricidad (Kwh).</span><span class="sxs-lookup"><span data-stu-id="ed9eb-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="ed9eb-226">Se crea un miembro de dimensión estadística que se denomina Electricity, y se registra el consumo de electricidad.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="ed9eb-227">De forma predeterminada, todos los miembros de dimensión estadísticos estarán disponibles como bases de asignación.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ed9eb-228">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-228">Cost object</span></span></th>
<th><span data-ttu-id="ed9eb-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="ed9eb-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-230">CC001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-230">CC001</span></span></td>
<td><span data-ttu-id="ed9eb-231">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-231">HR</span></span></td>
<td><span data-ttu-id="ed9eb-232">1.000</span><span class="sxs-lookup"><span data-stu-id="ed9eb-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-233">CC002</span><span class="sxs-lookup"><span data-stu-id="ed9eb-233">CC002</span></span></td>
<td><span data-ttu-id="ed9eb-234">Finanzas</span><span class="sxs-lookup"><span data-stu-id="ed9eb-234">Finance</span></span></td>
<td><span data-ttu-id="ed9eb-235">6.000</span><span class="sxs-lookup"><span data-stu-id="ed9eb-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-236">CC003</span><span class="sxs-lookup"><span data-stu-id="ed9eb-236">CC003</span></span></td>
<td><span data-ttu-id="ed9eb-237">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-237">Assembly</span></span></td>
<td><span data-ttu-id="ed9eb-238">0</span><span class="sxs-lookup"><span data-stu-id="ed9eb-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ed9eb-239">La tabla siguiente muestra el resultado cuando se aplica el consumo de electricidad como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ed9eb-240">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-240">Cost object</span></span></th>
<th><span data-ttu-id="ed9eb-241">Magnitud</span><span class="sxs-lookup"><span data-stu-id="ed9eb-241">Magnitude</span></span></th>
<th><span data-ttu-id="ed9eb-242">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="ed9eb-242">Allocation factor</span></span></th>
<th><span data-ttu-id="ed9eb-243">Importe</span><span class="sxs-lookup"><span data-stu-id="ed9eb-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-244">CC001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-244">CC001</span></span></td>
<td><span data-ttu-id="ed9eb-245">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-245">HR</span></span></td>
<td><span data-ttu-id="ed9eb-246">1.000</span><span class="sxs-lookup"><span data-stu-id="ed9eb-246">1,000</span></span></td>
<td><span data-ttu-id="ed9eb-247">(1.000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="ed9eb-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="ed9eb-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-249">CC002</span><span class="sxs-lookup"><span data-stu-id="ed9eb-249">CC002</span></span></td>
<td><span data-ttu-id="ed9eb-250">Finanzas</span><span class="sxs-lookup"><span data-stu-id="ed9eb-250">Finance</span></span></td>
<td><span data-ttu-id="ed9eb-251">6.000</span><span class="sxs-lookup"><span data-stu-id="ed9eb-251">6,000</span></span></td>
<td><span data-ttu-id="ed9eb-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="ed9eb-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="ed9eb-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-254">CC003</span><span class="sxs-lookup"><span data-stu-id="ed9eb-254">CC003</span></span></td>
<td><span data-ttu-id="ed9eb-255">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-255">Assembly</span></span></td>
<td><span data-ttu-id="ed9eb-256">0</span><span class="sxs-lookup"><span data-stu-id="ed9eb-256">0</span></span></td>
<td><span data-ttu-id="ed9eb-257">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="ed9eb-258">0,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ed9eb-259">El coste fijo debe distribuirse uniformemente a los objetos individuales de costes que han consumido electricidad.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="ed9eb-260">Puede obtener este resultado usando el miembro de dimensión estadístico de electricidad en una base de asignación de la fórmula: (Electricidad &gt; 0,00) La tabla siguiente muestra el resultado cuando el consumo de electricidad se aplica como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ed9eb-261">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-261">Cost object</span></span></th>
<th><span data-ttu-id="ed9eb-262">Fórmula</span><span class="sxs-lookup"><span data-stu-id="ed9eb-262">Formula</span></span></th>
<th><span data-ttu-id="ed9eb-263">Magnitud</span><span class="sxs-lookup"><span data-stu-id="ed9eb-263">Magnitude</span></span></th>
<th><span data-ttu-id="ed9eb-264">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="ed9eb-264">Allocation factor</span></span></th>
<th><span data-ttu-id="ed9eb-265">Importe</span><span class="sxs-lookup"><span data-stu-id="ed9eb-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-266">CC001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-266">CC001</span></span></td>
<td><span data-ttu-id="ed9eb-267">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-267">HR</span></span></td>
<td><span data-ttu-id="ed9eb-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="ed9eb-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="ed9eb-269">1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-269">1</span></span></td>
<td><span data-ttu-id="ed9eb-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="ed9eb-271">500,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-272">CC002</span><span class="sxs-lookup"><span data-stu-id="ed9eb-272">CC002</span></span></td>
<td><span data-ttu-id="ed9eb-273">Finanzas</span><span class="sxs-lookup"><span data-stu-id="ed9eb-273">Finance</span></span></td>
<td><span data-ttu-id="ed9eb-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="ed9eb-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="ed9eb-275">1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-275">1</span></span></td>
<td><span data-ttu-id="ed9eb-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="ed9eb-277">500,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-278">CC003</span><span class="sxs-lookup"><span data-stu-id="ed9eb-278">CC003</span></span></td>
<td><span data-ttu-id="ed9eb-279">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-279">Assembly</span></span></td>
<td><span data-ttu-id="ed9eb-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="ed9eb-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="ed9eb-281">0</span><span class="sxs-lookup"><span data-stu-id="ed9eb-281">0</span></span></td>
<td><span data-ttu-id="ed9eb-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="ed9eb-283">0,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="ed9eb-284">Diario</span><span class="sxs-lookup"><span data-stu-id="ed9eb-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ed9eb-285">Diario</span><span class="sxs-lookup"><span data-stu-id="ed9eb-285">Journal</span></span></th>
<th><span data-ttu-id="ed9eb-286">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="ed9eb-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ed9eb-287">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="ed9eb-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ed9eb-288">Versión</span><span class="sxs-lookup"><span data-stu-id="ed9eb-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-289">00002</span><span class="sxs-lookup"><span data-stu-id="ed9eb-289">00002</span></span></td>
<td><span data-ttu-id="ed9eb-290">Diario de cálculo de la distribución de costes</span><span class="sxs-lookup"><span data-stu-id="ed9eb-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="ed9eb-291">Fiscal</span><span class="sxs-lookup"><span data-stu-id="ed9eb-291">Fiscal</span></span></td>
<td><span data-ttu-id="ed9eb-292">2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-292">2017</span></span></td>
<td><span data-ttu-id="ed9eb-293">Período 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-293">Period 1</span></span></td>
<td><span data-ttu-id="ed9eb-294">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="ed9eb-295">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="ed9eb-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ed9eb-296">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ed9eb-297">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ed9eb-298">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-298">Cost element</span></span></th>
<th><span data-ttu-id="ed9eb-299">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="ed9eb-299">Cost behavior</span></span></th>
<th><span data-ttu-id="ed9eb-300">Importe</span><span class="sxs-lookup"><span data-stu-id="ed9eb-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-301">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="ed9eb-302">CC099</span><span class="sxs-lookup"><span data-stu-id="ed9eb-302">CC099</span></span></td>
<td><span data-ttu-id="ed9eb-303">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-303">Default cost center</span></span></td>
<td><span data-ttu-id="ed9eb-304">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-304">10001</span></span></td>
<td><span data-ttu-id="ed9eb-305">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-305">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-306">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-306">Fixed cost</span></span></td>
<td><span data-ttu-id="ed9eb-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-308">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="ed9eb-309">CC099</span><span class="sxs-lookup"><span data-stu-id="ed9eb-309">CC099</span></span></td>
<td><span data-ttu-id="ed9eb-310">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-310">Default cost center</span></span></td>
<td><span data-ttu-id="ed9eb-311">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-311">10001</span></span></td>
<td><span data-ttu-id="ed9eb-312">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-312">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-313">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-313">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-314">9.000,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ed9eb-315">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="ed9eb-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ed9eb-316">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ed9eb-317">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-317">Cost element</span></span></th>
<th><span data-ttu-id="ed9eb-318">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="ed9eb-318">Cost behavior</span></span></th>
<th><span data-ttu-id="ed9eb-319">Importe</span><span class="sxs-lookup"><span data-stu-id="ed9eb-319">Amount</span></span></th>
<th><span data-ttu-id="ed9eb-320">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-321">CC099</span><span class="sxs-lookup"><span data-stu-id="ed9eb-321">CC099</span></span></td>
<td><span data-ttu-id="ed9eb-322">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-322">Default cost center</span></span></td>
<td><span data-ttu-id="ed9eb-323">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-323">10001</span></span></td>
<td><span data-ttu-id="ed9eb-324">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-324">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-325">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-325">Fixed cost</span></span></td>
<td><span data-ttu-id="ed9eb-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-326">-1,000.00</span></span></td>
<td><span data-ttu-id="ed9eb-327">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-328">CC001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-328">CC001</span></span></td>
<td><span data-ttu-id="ed9eb-329">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-329">HR</span></span></td>
<td><span data-ttu-id="ed9eb-330">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-330">10001</span></span></td>
<td><span data-ttu-id="ed9eb-331">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-331">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-332">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-332">Fixed cost</span></span></td>
<td><span data-ttu-id="ed9eb-333">500,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-333">500.00</span></span></td>
<td><span data-ttu-id="ed9eb-334">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-335">CC002</span><span class="sxs-lookup"><span data-stu-id="ed9eb-335">CC002</span></span></td>
<td><span data-ttu-id="ed9eb-336">Finanzas</span><span class="sxs-lookup"><span data-stu-id="ed9eb-336">Finance</span></span></td>
<td><span data-ttu-id="ed9eb-337">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-337">10001</span></span></td>
<td><span data-ttu-id="ed9eb-338">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-338">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-339">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-339">Fixed cost</span></span></td>
<td><span data-ttu-id="ed9eb-340">500,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-340">500.00</span></span></td>
<td><span data-ttu-id="ed9eb-341">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-342">CC099</span><span class="sxs-lookup"><span data-stu-id="ed9eb-342">CC099</span></span></td>
<td><span data-ttu-id="ed9eb-343">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-343">Default cost center</span></span></td>
<td><span data-ttu-id="ed9eb-344">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-344">10001</span></span></td>
<td><span data-ttu-id="ed9eb-345">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-345">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-346">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-346">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-347">-9,000.00</span></span></td>
<td><span data-ttu-id="ed9eb-348">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-349">CC001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-349">CC001</span></span></td>
<td><span data-ttu-id="ed9eb-350">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-350">HR</span></span></td>
<td><span data-ttu-id="ed9eb-351">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-351">10001</span></span></td>
<td><span data-ttu-id="ed9eb-352">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-352">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-353">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-353">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="ed9eb-354">1,285.71</span></span></td>
<td><span data-ttu-id="ed9eb-355">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-356">CC002</span><span class="sxs-lookup"><span data-stu-id="ed9eb-356">CC002</span></span></td>
<td><span data-ttu-id="ed9eb-357">Finanzas</span><span class="sxs-lookup"><span data-stu-id="ed9eb-357">Finance</span></span></td>
<td><span data-ttu-id="ed9eb-358">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-358">10001</span></span></td>
<td><span data-ttu-id="ed9eb-359">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-359">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-360">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-360">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="ed9eb-361">7,714.29</span></span></td>
<td><span data-ttu-id="ed9eb-362">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ed9eb-363">Para obtener más información, consulte [Crear y asignar una directiva de distribución de costes a una unidad de control de costes](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="ed9eb-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="ed9eb-364">Paso 3: Procese el cálculo de las tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="ed9eb-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="ed9eb-365">La tasa de costes generales se usa para cargar uno o varios objetos de coste específicos.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="ed9eb-366">El cargo se basa en un índice de coste predeterminado y la magnitud de la base de asignación asignada.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="ed9eb-367">Defina la tasa de costes generales</span><span class="sxs-lookup"><span data-stu-id="ed9eb-367">Define the overhead rate</span></span>

<span data-ttu-id="ed9eb-368">El objeto de coste CC001 HR contribuye a un conjunto de proyectos internos.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="ed9eb-369">Se crea un miembro de dimensión estadística que se denomina proyectos HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ed9eb-370">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-370">Cost object</span></span></th>
<th><span data-ttu-id="ed9eb-371">Horas</span><span class="sxs-lookup"><span data-stu-id="ed9eb-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-372">Proy 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-372">Proj 1</span></span></td>
<td><span data-ttu-id="ed9eb-373">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-373">Project 1</span></span></td>
<td><span data-ttu-id="ed9eb-374">3</span><span class="sxs-lookup"><span data-stu-id="ed9eb-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-375">Proy 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-375">Proj 2</span></span></td>
<td><span data-ttu-id="ed9eb-376">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-376">Project 2</span></span></td>
<td><span data-ttu-id="ed9eb-377">1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ed9eb-378">Una tasa de coste predeterminada para la contribución de los proyectos de coste se ha definido.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ed9eb-379">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-379">Cost object</span></span></th>
<th><span data-ttu-id="ed9eb-380">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-380">Cost element</span></span></th>
<th><span data-ttu-id="ed9eb-381">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="ed9eb-381">Cost behavior</span></span></th>
<th><span data-ttu-id="ed9eb-382">Unidades</span><span class="sxs-lookup"><span data-stu-id="ed9eb-382">Units</span></span></th>
<th><span data-ttu-id="ed9eb-383">Índice</span><span class="sxs-lookup"><span data-stu-id="ed9eb-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-384">CC001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-384">CC001</span></span></td>
<td><span data-ttu-id="ed9eb-385">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-385">HR</span></span></td>
<td><span data-ttu-id="ed9eb-386">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-386">10001</span></span></td>
<td><span data-ttu-id="ed9eb-387">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-387">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-388">1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-388">1</span></span></td>
<td><span data-ttu-id="ed9eb-389">10</span><span class="sxs-lookup"><span data-stu-id="ed9eb-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ed9eb-390">La tabla siguiente muestra el resultado cuando los proyectos HR se aplican como base de la asignación.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ed9eb-391">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-391">Cost object</span></span></th>
<th><span data-ttu-id="ed9eb-392">Magnitud</span><span class="sxs-lookup"><span data-stu-id="ed9eb-392">Magnitude</span></span></th>
<th><span data-ttu-id="ed9eb-393">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-393">Cost element</span></span></th>
<th><span data-ttu-id="ed9eb-394">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="ed9eb-394">Allocation factor</span></span></th>
<th><span data-ttu-id="ed9eb-395">Importe</span><span class="sxs-lookup"><span data-stu-id="ed9eb-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-396">Proy 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-396">Proj 1</span></span></td>
<td><span data-ttu-id="ed9eb-397">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-397">Project 1</span></span></td>
<td><span data-ttu-id="ed9eb-398">3</span><span class="sxs-lookup"><span data-stu-id="ed9eb-398">3</span></span></td>
<td><span data-ttu-id="ed9eb-399">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-399">10001</span></span></td>
<td><span data-ttu-id="ed9eb-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="ed9eb-401">30,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-402">Proy 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-402">Proj 2</span></span></td>
<td><span data-ttu-id="ed9eb-403">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-403">Project 2</span></span></td>
<td><span data-ttu-id="ed9eb-404">1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-404">1</span></span></td>
<td><span data-ttu-id="ed9eb-405">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-405">10001</span></span></td>
<td><span data-ttu-id="ed9eb-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="ed9eb-407">10,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="ed9eb-408">Diario</span><span class="sxs-lookup"><span data-stu-id="ed9eb-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ed9eb-409">Diario</span><span class="sxs-lookup"><span data-stu-id="ed9eb-409">Journal</span></span></th>
<th><span data-ttu-id="ed9eb-410">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="ed9eb-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ed9eb-411">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="ed9eb-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ed9eb-412">Versión</span><span class="sxs-lookup"><span data-stu-id="ed9eb-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-413">00003</span><span class="sxs-lookup"><span data-stu-id="ed9eb-413">00003</span></span></td>
<td><span data-ttu-id="ed9eb-414">Diario de cálculo de tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="ed9eb-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="ed9eb-415">Fiscal</span><span class="sxs-lookup"><span data-stu-id="ed9eb-415">Fiscal</span></span></td>
<td><span data-ttu-id="ed9eb-416">2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-416">2017</span></span></td>
<td><span data-ttu-id="ed9eb-417">Período 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-417">Period 1</span></span></td>
<td><span data-ttu-id="ed9eb-418">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="ed9eb-419">Entradas de diario (entradas de diario para cálculo de tasas de costes generales)</span><span class="sxs-lookup"><span data-stu-id="ed9eb-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ed9eb-420">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ed9eb-421">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-421">Cost object</span></span></th>
<th><span data-ttu-id="ed9eb-422">Magnitud</span><span class="sxs-lookup"><span data-stu-id="ed9eb-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-423">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="ed9eb-424">Proy 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-424">Proj 1</span></span></td>
<td><span data-ttu-id="ed9eb-425">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="ed9eb-426">3,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-427">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="ed9eb-428">Proy 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-428">Proj 2</span></span></td>
<td><span data-ttu-id="ed9eb-429">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="ed9eb-430">1,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ed9eb-431">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="ed9eb-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ed9eb-432">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ed9eb-433">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-433">Cost element</span></span></th>
<th><span data-ttu-id="ed9eb-434">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="ed9eb-434">Cost behavior</span></span></th>
<th><span data-ttu-id="ed9eb-435">Importe</span><span class="sxs-lookup"><span data-stu-id="ed9eb-435">Amount</span></span></th>
<th><span data-ttu-id="ed9eb-436">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-437">CC0001</span></span></td>
<td><span data-ttu-id="ed9eb-438">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-438">HR</span></span></td>
<td><span data-ttu-id="ed9eb-439">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-439">10001</span></span></td>
<td><span data-ttu-id="ed9eb-440">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-440">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-441">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-441">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-442">-30.00</span></span></td>
<td><span data-ttu-id="ed9eb-443">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-444">Proy 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-444">Proj 1</span></span></td>
<td><span data-ttu-id="ed9eb-445">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="ed9eb-446">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-446">10001</span></span></td>
<td><span data-ttu-id="ed9eb-447">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-447">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-448">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-448">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-449">30,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-449">30.00</span></span></td>
<td><span data-ttu-id="ed9eb-450">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-451">CC001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-451">CC001</span></span></td>
<td><span data-ttu-id="ed9eb-452">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-452">HR</span></span></td>
<td><span data-ttu-id="ed9eb-453">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-453">10001</span></span></td>
<td><span data-ttu-id="ed9eb-454">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-454">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-455">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-455">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-456">-10.00</span></span></td>
<td><span data-ttu-id="ed9eb-457">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-458">Proy 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-458">Proj 2</span></span></td>
<td><span data-ttu-id="ed9eb-459">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="ed9eb-460">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-460">10001</span></span></td>
<td><span data-ttu-id="ed9eb-461">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-461">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-462">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-462">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-463">10,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-463">10.00</span></span></td>
<td><span data-ttu-id="ed9eb-464">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ed9eb-465">Para obtener más información, consulte [Realizar cálculo de costes generales](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="ed9eb-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="ed9eb-466">Paso 4: Procese el cálculo de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="ed9eb-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="ed9eb-467">La asignación es utilizada para asignar el saldo de un objeto de coste a otros objetos de coste aplicando una base de asignación.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="ed9eb-468">Finance and Operations admite el método de asignación recíproco.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-468">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="ed9eb-469">En el método de asignación recíproco, se reconocen completamente los servicios mutuos que los objetos de coste auxiliar intercambian.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="ed9eb-470">El sistema determina automáticamente el orden correcto para realizar las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="ed9eb-471">El saldo de un objeto de coste se asigna según una única base de asignación.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="ed9eb-472">Las asignaciones entre dimensiones de objetos de coste y sus miembros respectivos se admiten.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="ed9eb-473">El orden de asignación se controla por unidad de control de costes.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="ed9eb-474">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="ed9eb-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="ed9eb-475">Defina la asignación de costes</span><span class="sxs-lookup"><span data-stu-id="ed9eb-475">Define the cost allocation</span></span>

<span data-ttu-id="ed9eb-476">A continuación se indica un ejemplo sencillo que explica cómo puede realizar el seguimiento del flujo de coste.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="ed9eb-477">El objeto de coste CC001 HR contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="ed9eb-478">Se crea un miembro de dimensión estadística que se denomina servicios HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ed9eb-479">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-479">Cost object</span></span></th>
<th><span data-ttu-id="ed9eb-480">Servicios HR</span><span class="sxs-lookup"><span data-stu-id="ed9eb-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-481">CC002</span><span class="sxs-lookup"><span data-stu-id="ed9eb-481">CC002</span></span></td>
<td><span data-ttu-id="ed9eb-482">Finanzas</span><span class="sxs-lookup"><span data-stu-id="ed9eb-482">Finance</span></span></td>
<td><span data-ttu-id="ed9eb-483">35</span><span class="sxs-lookup"><span data-stu-id="ed9eb-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-484">CC003</span><span class="sxs-lookup"><span data-stu-id="ed9eb-484">CC003</span></span></td>
<td><span data-ttu-id="ed9eb-485">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-485">Assembly</span></span></td>
<td><span data-ttu-id="ed9eb-486">55</span><span class="sxs-lookup"><span data-stu-id="ed9eb-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-487">CC004</span><span class="sxs-lookup"><span data-stu-id="ed9eb-487">CC004</span></span></td>
<td><span data-ttu-id="ed9eb-488">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-488">Packaging</span></span></td>
<td><span data-ttu-id="ed9eb-489">10</span><span class="sxs-lookup"><span data-stu-id="ed9eb-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ed9eb-490">El objeto de coste CC002 Finanzas contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="ed9eb-491">Se crea un miembro de dimensión estadística que se denomina Finanzas para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ed9eb-492">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-492">Cost object</span></span></th>
<th><span data-ttu-id="ed9eb-493">Servicios financieros</span><span class="sxs-lookup"><span data-stu-id="ed9eb-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-494">CC003</span><span class="sxs-lookup"><span data-stu-id="ed9eb-494">CC003</span></span></td>
<td><span data-ttu-id="ed9eb-495">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-495">Assembly</span></span></td>
<td><span data-ttu-id="ed9eb-496">65</span><span class="sxs-lookup"><span data-stu-id="ed9eb-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-497">CC004</span><span class="sxs-lookup"><span data-stu-id="ed9eb-497">CC004</span></span></td>
<td><span data-ttu-id="ed9eb-498">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-498">Packaging</span></span></td>
<td><span data-ttu-id="ed9eb-499">35</span><span class="sxs-lookup"><span data-stu-id="ed9eb-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ed9eb-500">El objeto de coste CC003 Asamblea contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="ed9eb-501">Se crea un miembro de dimensión estadística que se denomina servicios de Asamblea para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ed9eb-502">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-502">Cost object</span></span></th>
<th><span data-ttu-id="ed9eb-503">Servicios de la asamblea (horas)</span><span class="sxs-lookup"><span data-stu-id="ed9eb-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-504">Prod 1</span></span></td>
<td><span data-ttu-id="ed9eb-505">Producto 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-505">Product 1</span></span></td>
<td><span data-ttu-id="ed9eb-506">60</span><span class="sxs-lookup"><span data-stu-id="ed9eb-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-507">Prod 2</span></span></td>
<td><span data-ttu-id="ed9eb-508">Producto 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-508">Product 2</span></span></td>
<td><span data-ttu-id="ed9eb-509">20</span><span class="sxs-lookup"><span data-stu-id="ed9eb-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ed9eb-510">El objeto de coste CC004 Embalaje contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="ed9eb-511">Se crea un miembro de dimensión estadística que se denomina servicios de Embalaje para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ed9eb-512">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-512">Cost object</span></span></th>
<th><span data-ttu-id="ed9eb-513">Servicios de embalaje (horas)</span><span class="sxs-lookup"><span data-stu-id="ed9eb-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-514">Prod 1</span></span></td>
<td><span data-ttu-id="ed9eb-515">Producto 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-515">Product 1</span></span></td>
<td><span data-ttu-id="ed9eb-516">80</span><span class="sxs-lookup"><span data-stu-id="ed9eb-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-517">Prod 2</span></span></td>
<td><span data-ttu-id="ed9eb-518">Producto 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-518">Product 2</span></span></td>
<td><span data-ttu-id="ed9eb-519">15</span><span class="sxs-lookup"><span data-stu-id="ed9eb-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="ed9eb-520">En Finance and Operations, las medidas estadísticas como las horas de la producción que un producto consume se pueden deducir de los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-520">In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="ed9eb-521">Para obtener más información, vea [Plantilla de proveedor de medidas estadísticas](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="ed9eb-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="ed9eb-522">La tabla siguiente muestra el resultado cuando se aplican los servicios de HR como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="ed9eb-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ed9eb-523">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-523">Cost object</span></span></th>
<th><span data-ttu-id="ed9eb-524">Magnitud</span><span class="sxs-lookup"><span data-stu-id="ed9eb-524">Magnitude</span></span></th>
<th><span data-ttu-id="ed9eb-525">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="ed9eb-525">Allocation factor</span></span></th>
<th><span data-ttu-id="ed9eb-526">Importe</span><span class="sxs-lookup"><span data-stu-id="ed9eb-526">Amount</span></span></th>
<th><span data-ttu-id="ed9eb-527">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="ed9eb-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-528">CC002</span><span class="sxs-lookup"><span data-stu-id="ed9eb-528">CC002</span></span></td>
<td><span data-ttu-id="ed9eb-529">Finanzas</span><span class="sxs-lookup"><span data-stu-id="ed9eb-529">Finance</span></span></td>
<td><span data-ttu-id="ed9eb-530">35</span><span class="sxs-lookup"><span data-stu-id="ed9eb-530">35</span></span></td>
<td><span data-ttu-id="ed9eb-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="ed9eb-532">175.00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-532">175.00</span></span></td>
<td><span data-ttu-id="ed9eb-533">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-534">CC003</span><span class="sxs-lookup"><span data-stu-id="ed9eb-534">CC003</span></span></td>
<td><span data-ttu-id="ed9eb-535">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-535">Assembly</span></span></td>
<td><span data-ttu-id="ed9eb-536">55</span><span class="sxs-lookup"><span data-stu-id="ed9eb-536">55</span></span></td>
<td><span data-ttu-id="ed9eb-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="ed9eb-538">275.00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-538">275.00</span></span></td>
<td><span data-ttu-id="ed9eb-539">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-540">CC004</span><span class="sxs-lookup"><span data-stu-id="ed9eb-540">CC004</span></span></td>
<td><span data-ttu-id="ed9eb-541">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-541">Packaging</span></span></td>
<td><span data-ttu-id="ed9eb-542">10</span><span class="sxs-lookup"><span data-stu-id="ed9eb-542">10</span></span></td>
<td><span data-ttu-id="ed9eb-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="ed9eb-544">50,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-544">50.00</span></span></td>
<td><span data-ttu-id="ed9eb-545">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-546">CC002</span><span class="sxs-lookup"><span data-stu-id="ed9eb-546">CC002</span></span></td>
<td><span data-ttu-id="ed9eb-547">Finanzas</span><span class="sxs-lookup"><span data-stu-id="ed9eb-547">Finance</span></span></td>
<td><span data-ttu-id="ed9eb-548">35</span><span class="sxs-lookup"><span data-stu-id="ed9eb-548">35</span></span></td>
<td><span data-ttu-id="ed9eb-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="ed9eb-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="ed9eb-550">436.00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-550">436.00</span></span></td>
<td><span data-ttu-id="ed9eb-551">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-552">CC003</span><span class="sxs-lookup"><span data-stu-id="ed9eb-552">CC003</span></span></td>
<td><span data-ttu-id="ed9eb-553">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-553">Assembly</span></span></td>
<td><span data-ttu-id="ed9eb-554">55</span><span class="sxs-lookup"><span data-stu-id="ed9eb-554">55</span></span></td>
<td><span data-ttu-id="ed9eb-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="ed9eb-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="ed9eb-556">685.14</span><span class="sxs-lookup"><span data-stu-id="ed9eb-556">685.14</span></span></td>
<td><span data-ttu-id="ed9eb-557">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-558">CC004</span><span class="sxs-lookup"><span data-stu-id="ed9eb-558">CC004</span></span></td>
<td><span data-ttu-id="ed9eb-559">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-559">Packaging</span></span></td>
<td><span data-ttu-id="ed9eb-560">10</span><span class="sxs-lookup"><span data-stu-id="ed9eb-560">10</span></span></td>
<td><span data-ttu-id="ed9eb-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="ed9eb-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="ed9eb-562">124.57</span><span class="sxs-lookup"><span data-stu-id="ed9eb-562">124.57</span></span></td>
<td><span data-ttu-id="ed9eb-563">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ed9eb-564">La tabla siguiente muestra el resultado cuando se aplican los servicios de Finanzas como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="ed9eb-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ed9eb-565">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-565">Cost object</span></span></th>
<th><span data-ttu-id="ed9eb-566">Magnitud</span><span class="sxs-lookup"><span data-stu-id="ed9eb-566">Magnitude</span></span></th>
<th><span data-ttu-id="ed9eb-567">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="ed9eb-567">Allocation factor</span></span></th>
<th><span data-ttu-id="ed9eb-568">Importe</span><span class="sxs-lookup"><span data-stu-id="ed9eb-568">Amount</span></span></th>
<th><span data-ttu-id="ed9eb-569">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="ed9eb-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-570">CC003</span><span class="sxs-lookup"><span data-stu-id="ed9eb-570">CC003</span></span></td>
<td><span data-ttu-id="ed9eb-571">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-571">Assembly</span></span></td>
<td><span data-ttu-id="ed9eb-572">65</span><span class="sxs-lookup"><span data-stu-id="ed9eb-572">65</span></span></td>
<td><span data-ttu-id="ed9eb-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="ed9eb-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="ed9eb-574">438.75</span><span class="sxs-lookup"><span data-stu-id="ed9eb-574">438.75</span></span></td>
<td><span data-ttu-id="ed9eb-575">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-576">CC004</span><span class="sxs-lookup"><span data-stu-id="ed9eb-576">CC004</span></span></td>
<td><span data-ttu-id="ed9eb-577">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-577">Packaging</span></span></td>
<td><span data-ttu-id="ed9eb-578">35</span><span class="sxs-lookup"><span data-stu-id="ed9eb-578">35</span></span></td>
<td><span data-ttu-id="ed9eb-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="ed9eb-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="ed9eb-580">236.25</span><span class="sxs-lookup"><span data-stu-id="ed9eb-580">236.25</span></span></td>
<td><span data-ttu-id="ed9eb-581">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-582">CC003</span><span class="sxs-lookup"><span data-stu-id="ed9eb-582">CC003</span></span></td>
<td><span data-ttu-id="ed9eb-583">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-583">Assembly</span></span></td>
<td><span data-ttu-id="ed9eb-584">65</span><span class="sxs-lookup"><span data-stu-id="ed9eb-584">65</span></span></td>
<td><span data-ttu-id="ed9eb-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="ed9eb-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="ed9eb-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="ed9eb-586">5,297.69</span></span></td>
<td><span data-ttu-id="ed9eb-587">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-588">CC004</span><span class="sxs-lookup"><span data-stu-id="ed9eb-588">CC004</span></span></td>
<td><span data-ttu-id="ed9eb-589">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-589">Packaging</span></span></td>
<td><span data-ttu-id="ed9eb-590">35</span><span class="sxs-lookup"><span data-stu-id="ed9eb-590">35</span></span></td>
<td><span data-ttu-id="ed9eb-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="ed9eb-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="ed9eb-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="ed9eb-592">2,852.60</span></span></td>
<td><span data-ttu-id="ed9eb-593">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ed9eb-594">La tabla siguiente muestra el resultado cuando se aplican los servicios de Asamblea como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="ed9eb-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ed9eb-595">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-595">Cost object</span></span></th>
<th><span data-ttu-id="ed9eb-596">Magnitud</span><span class="sxs-lookup"><span data-stu-id="ed9eb-596">Magnitude</span></span></th>
<th><span data-ttu-id="ed9eb-597">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="ed9eb-597">Allocation factor</span></span></th>
<th><span data-ttu-id="ed9eb-598">Importe</span><span class="sxs-lookup"><span data-stu-id="ed9eb-598">Amount</span></span></th>
<th><span data-ttu-id="ed9eb-599">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="ed9eb-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-600">Prod 1</span></span></td>
<td><span data-ttu-id="ed9eb-601">Producto 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-601">Product 1</span></span></td>
<td><span data-ttu-id="ed9eb-602">60</span><span class="sxs-lookup"><span data-stu-id="ed9eb-602">60</span></span></td>
<td><span data-ttu-id="ed9eb-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="ed9eb-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="ed9eb-604">535.31</span><span class="sxs-lookup"><span data-stu-id="ed9eb-604">535.31</span></span></td>
<td><span data-ttu-id="ed9eb-605">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-606">Prod 2</span></span></td>
<td><span data-ttu-id="ed9eb-607">Producto 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-607">Product 2</span></span></td>
<td><span data-ttu-id="ed9eb-608">20</span><span class="sxs-lookup"><span data-stu-id="ed9eb-608">20</span></span></td>
<td><span data-ttu-id="ed9eb-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="ed9eb-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="ed9eb-610">178.44</span><span class="sxs-lookup"><span data-stu-id="ed9eb-610">178.44</span></span></td>
<td><span data-ttu-id="ed9eb-611">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-612">Prod 1</span></span></td>
<td><span data-ttu-id="ed9eb-613">Producto 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-613">Product 1</span></span></td>
<td><span data-ttu-id="ed9eb-614">60</span><span class="sxs-lookup"><span data-stu-id="ed9eb-614">60</span></span></td>
<td><span data-ttu-id="ed9eb-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="ed9eb-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="ed9eb-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="ed9eb-616">4,487.12</span></span></td>
<td><span data-ttu-id="ed9eb-617">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-618">Prod 2</span></span></td>
<td><span data-ttu-id="ed9eb-619">Producto 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-619">Product 2</span></span></td>
<td><span data-ttu-id="ed9eb-620">20</span><span class="sxs-lookup"><span data-stu-id="ed9eb-620">20</span></span></td>
<td><span data-ttu-id="ed9eb-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="ed9eb-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="ed9eb-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="ed9eb-622">1,495.71</span></span></td>
<td><span data-ttu-id="ed9eb-623">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ed9eb-624">La tabla siguiente muestra el resultado cuando se aplican los servicios de Embalaje como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="ed9eb-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ed9eb-625">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-625">Cost object</span></span></th>
<th><span data-ttu-id="ed9eb-626">Magnitud</span><span class="sxs-lookup"><span data-stu-id="ed9eb-626">Magnitude</span></span></th>
<th><span data-ttu-id="ed9eb-627">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="ed9eb-627">Allocation factor</span></span></th>
<th><span data-ttu-id="ed9eb-628">Importe</span><span class="sxs-lookup"><span data-stu-id="ed9eb-628">Amount</span></span></th>
<th><span data-ttu-id="ed9eb-629">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="ed9eb-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-630">Prod 1</span></span></td>
<td><span data-ttu-id="ed9eb-631">Producto 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-631">Product 1</span></span></td>
<td><span data-ttu-id="ed9eb-632">80</span><span class="sxs-lookup"><span data-stu-id="ed9eb-632">80</span></span></td>
<td><span data-ttu-id="ed9eb-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="ed9eb-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="ed9eb-634">241.05</span><span class="sxs-lookup"><span data-stu-id="ed9eb-634">241.05</span></span></td>
<td><span data-ttu-id="ed9eb-635">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-636">Prod 2</span></span></td>
<td><span data-ttu-id="ed9eb-637">Producto 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-637">Product 2</span></span></td>
<td><span data-ttu-id="ed9eb-638">15</span><span class="sxs-lookup"><span data-stu-id="ed9eb-638">15</span></span></td>
<td><span data-ttu-id="ed9eb-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="ed9eb-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="ed9eb-640">45.20</span><span class="sxs-lookup"><span data-stu-id="ed9eb-640">45.20</span></span></td>
<td><span data-ttu-id="ed9eb-641">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-642">Prod 1</span></span></td>
<td><span data-ttu-id="ed9eb-643">Producto 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-643">Product 1</span></span></td>
<td><span data-ttu-id="ed9eb-644">80</span><span class="sxs-lookup"><span data-stu-id="ed9eb-644">80</span></span></td>
<td><span data-ttu-id="ed9eb-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="ed9eb-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="ed9eb-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="ed9eb-646">2,507.09</span></span></td>
<td><span data-ttu-id="ed9eb-647">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-648">Prod 2</span></span></td>
<td><span data-ttu-id="ed9eb-649">Producto 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-649">Product 2</span></span></td>
<td><span data-ttu-id="ed9eb-650">15</span><span class="sxs-lookup"><span data-stu-id="ed9eb-650">15</span></span></td>
<td><span data-ttu-id="ed9eb-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="ed9eb-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="ed9eb-652">470.08</span><span class="sxs-lookup"><span data-stu-id="ed9eb-652">470.08</span></span></td>
<td><span data-ttu-id="ed9eb-653">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="ed9eb-654">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="ed9eb-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ed9eb-655">Diario</span><span class="sxs-lookup"><span data-stu-id="ed9eb-655">Journal</span></span></th>
<th><span data-ttu-id="ed9eb-656">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="ed9eb-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ed9eb-657">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="ed9eb-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ed9eb-658">Versión</span><span class="sxs-lookup"><span data-stu-id="ed9eb-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-659">00004</span><span class="sxs-lookup"><span data-stu-id="ed9eb-659">00004</span></span></td>
<td><span data-ttu-id="ed9eb-660">Diario de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="ed9eb-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="ed9eb-661">Fiscal</span><span class="sxs-lookup"><span data-stu-id="ed9eb-661">Fiscal</span></span></td>
<td><span data-ttu-id="ed9eb-662">2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-662">2017</span></span></td>
<td><span data-ttu-id="ed9eb-663">Período 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-663">Period 1</span></span></td>
<td><span data-ttu-id="ed9eb-664">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="ed9eb-665">Líneas de diario</span><span class="sxs-lookup"><span data-stu-id="ed9eb-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ed9eb-666">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ed9eb-667">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ed9eb-668">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-668">Cost element</span></span></th>
<th><span data-ttu-id="ed9eb-669">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="ed9eb-669">Cost behavior</span></span></th>
<th><span data-ttu-id="ed9eb-670">Importe</span><span class="sxs-lookup"><span data-stu-id="ed9eb-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-671">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="ed9eb-672">CC001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-672">CC001</span></span></td>
<td><span data-ttu-id="ed9eb-673">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-673">HR</span></span></td>
<td><span data-ttu-id="ed9eb-674">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-674">10001</span></span></td>
<td><span data-ttu-id="ed9eb-675">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-675">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-676">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-676">Fixed cost</span></span></td>
<td><span data-ttu-id="ed9eb-677">500,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-678">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="ed9eb-679">CC001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-679">CC001</span></span></td>
<td><span data-ttu-id="ed9eb-680">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-680">HR</span></span></td>
<td><span data-ttu-id="ed9eb-681">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-681">10001</span></span></td>
<td><span data-ttu-id="ed9eb-682">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-682">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-683">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-683">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="ed9eb-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-685">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="ed9eb-686">CC002</span><span class="sxs-lookup"><span data-stu-id="ed9eb-686">CC002</span></span></td>
<td><span data-ttu-id="ed9eb-687">Finanzas</span><span class="sxs-lookup"><span data-stu-id="ed9eb-687">Finance</span></span></td>
<td><span data-ttu-id="ed9eb-688">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-688">10001</span></span></td>
<td><span data-ttu-id="ed9eb-689">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-689">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-690">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-690">Fixed cost</span></span></td>
<td><span data-ttu-id="ed9eb-691">675.00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-692">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="ed9eb-693">CC002</span><span class="sxs-lookup"><span data-stu-id="ed9eb-693">CC002</span></span></td>
<td><span data-ttu-id="ed9eb-694">Finanzas</span><span class="sxs-lookup"><span data-stu-id="ed9eb-694">Finance</span></span></td>
<td><span data-ttu-id="ed9eb-695">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-695">10001</span></span></td>
<td><span data-ttu-id="ed9eb-696">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-696">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-697">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-697">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="ed9eb-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-699">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="ed9eb-700">CC003</span><span class="sxs-lookup"><span data-stu-id="ed9eb-700">CC003</span></span></td>
<td><span data-ttu-id="ed9eb-701">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-701">Assembly</span></span></td>
<td><span data-ttu-id="ed9eb-702">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-702">10001</span></span></td>
<td><span data-ttu-id="ed9eb-703">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-703">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-704">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-704">Fixed cost</span></span></td>
<td><span data-ttu-id="ed9eb-705">713.75</span><span class="sxs-lookup"><span data-stu-id="ed9eb-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-706">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="ed9eb-707">CC003</span><span class="sxs-lookup"><span data-stu-id="ed9eb-707">CC003</span></span></td>
<td><span data-ttu-id="ed9eb-708">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-708">Assembly</span></span></td>
<td><span data-ttu-id="ed9eb-709">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-709">10001</span></span></td>
<td><span data-ttu-id="ed9eb-710">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-710">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-711">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-711">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="ed9eb-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-713">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="ed9eb-714">CC003</span><span class="sxs-lookup"><span data-stu-id="ed9eb-714">CC003</span></span></td>
<td><span data-ttu-id="ed9eb-715">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-715">Packaging</span></span></td>
<td><span data-ttu-id="ed9eb-716">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-716">10001</span></span></td>
<td><span data-ttu-id="ed9eb-717">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-717">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-718">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-718">Fixed cost</span></span></td>
<td><span data-ttu-id="ed9eb-719">286.25</span><span class="sxs-lookup"><span data-stu-id="ed9eb-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-720">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="ed9eb-721">CC003</span><span class="sxs-lookup"><span data-stu-id="ed9eb-721">CC003</span></span></td>
<td><span data-ttu-id="ed9eb-722">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-722">Packaging</span></span></td>
<td><span data-ttu-id="ed9eb-723">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-723">10001</span></span></td>
<td><span data-ttu-id="ed9eb-724">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-724">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-725">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-725">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="ed9eb-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-727">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="ed9eb-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-728">Prod 1</span></span></td>
<td><span data-ttu-id="ed9eb-729">Producto 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-729">Product 1</span></span></td>
<td><span data-ttu-id="ed9eb-730">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-730">10001</span></span></td>
<td><span data-ttu-id="ed9eb-731">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-731">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-732">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-732">Fixed cost</span></span></td>
<td><span data-ttu-id="ed9eb-733">776.36</span><span class="sxs-lookup"><span data-stu-id="ed9eb-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-734">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="ed9eb-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-735">Prod 1</span></span></td>
<td><span data-ttu-id="ed9eb-736">Producto 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-736">Product 1</span></span></td>
<td><span data-ttu-id="ed9eb-737">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-737">10001</span></span></td>
<td><span data-ttu-id="ed9eb-738">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-738">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-739">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-739">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="ed9eb-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-741">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="ed9eb-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-742">Prod 2</span></span></td>
<td><span data-ttu-id="ed9eb-743">Producto 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-743">Product 1</span></span></td>
<td><span data-ttu-id="ed9eb-744">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-744">10001</span></span></td>
<td><span data-ttu-id="ed9eb-745">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-745">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-746">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-746">Fixed cost</span></span></td>
<td><span data-ttu-id="ed9eb-747">223.64</span><span class="sxs-lookup"><span data-stu-id="ed9eb-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-748">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="ed9eb-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-749">Prod 2</span></span></td>
<td><span data-ttu-id="ed9eb-750">Producto 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-750">Product 1</span></span></td>
<td><span data-ttu-id="ed9eb-751">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-751">10001</span></span></td>
<td><span data-ttu-id="ed9eb-752">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-752">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-753">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-753">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="ed9eb-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ed9eb-755">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="ed9eb-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ed9eb-756">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ed9eb-757">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-757">Cost element</span></span></th>
<th><span data-ttu-id="ed9eb-758">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="ed9eb-758">Cost behavior</span></span></th>
<th><span data-ttu-id="ed9eb-759">Importe</span><span class="sxs-lookup"><span data-stu-id="ed9eb-759">Amount</span></span></th>
<th><span data-ttu-id="ed9eb-760">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ed9eb-761">CC001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-761">CC001</span></span></td>
<td><span data-ttu-id="ed9eb-762">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-762">HR</span></span></td>
<td><span data-ttu-id="ed9eb-763">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-763">10001</span></span></td>
<td><span data-ttu-id="ed9eb-764">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-764">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-765">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-765">Fixed cost</span></span></td>
<td><span data-ttu-id="ed9eb-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-766">-500.00</span></span></td>
<td><span data-ttu-id="ed9eb-767">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-768">CC002</span><span class="sxs-lookup"><span data-stu-id="ed9eb-768">CC002</span></span></td>
<td><span data-ttu-id="ed9eb-769">Finanzas</span><span class="sxs-lookup"><span data-stu-id="ed9eb-769">Finance</span></span></td>
<td><span data-ttu-id="ed9eb-770">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-770">10001</span></span></td>
<td><span data-ttu-id="ed9eb-771">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-771">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-772">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-772">Fixed cost</span></span></td>
<td><span data-ttu-id="ed9eb-773">175.00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-773">175.00</span></span></td>
<td><span data-ttu-id="ed9eb-774">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-775">CC003</span><span class="sxs-lookup"><span data-stu-id="ed9eb-775">CC003</span></span></td>
<td><span data-ttu-id="ed9eb-776">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-776">Assembly</span></span></td>
<td><span data-ttu-id="ed9eb-777">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-777">10001</span></span></td>
<td><span data-ttu-id="ed9eb-778">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-778">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-779">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-779">Fixed cost</span></span></td>
<td><span data-ttu-id="ed9eb-780">275.00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-780">275.00</span></span></td>
<td><span data-ttu-id="ed9eb-781">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-782">CC004</span><span class="sxs-lookup"><span data-stu-id="ed9eb-782">CC004</span></span></td>
<td><span data-ttu-id="ed9eb-783">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-783">Packaging</span></span></td>
<td><span data-ttu-id="ed9eb-784">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-784">10001</span></span></td>
<td><span data-ttu-id="ed9eb-785">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-785">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-786">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-786">Fixed cost</span></span></td>
<td><span data-ttu-id="ed9eb-787">50,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-787">50,00</span></span></td>
<td><span data-ttu-id="ed9eb-788">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-789">CC001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-789">CC001</span></span></td>
<td><span data-ttu-id="ed9eb-790">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-790">HR</span></span></td>
<td><span data-ttu-id="ed9eb-791">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-791">10001</span></span></td>
<td><span data-ttu-id="ed9eb-792">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-792">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-793">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-793">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="ed9eb-794">-1,245.71</span></span></td>
<td><span data-ttu-id="ed9eb-795">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-796">CC002</span><span class="sxs-lookup"><span data-stu-id="ed9eb-796">CC002</span></span></td>
<td><span data-ttu-id="ed9eb-797">Finanzas</span><span class="sxs-lookup"><span data-stu-id="ed9eb-797">Finance</span></span></td>
<td><span data-ttu-id="ed9eb-798">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-798">10001</span></span></td>
<td><span data-ttu-id="ed9eb-799">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-799">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-800">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-800">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-801">436.00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-801">436.00</span></span></td>
<td><span data-ttu-id="ed9eb-802">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-803">CC003</span><span class="sxs-lookup"><span data-stu-id="ed9eb-803">CC003</span></span></td>
<td><span data-ttu-id="ed9eb-804">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-804">Assembly</span></span></td>
<td><span data-ttu-id="ed9eb-805">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-805">10001</span></span></td>
<td><span data-ttu-id="ed9eb-806">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-806">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-807">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-807">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-808">685.14</span><span class="sxs-lookup"><span data-stu-id="ed9eb-808">685.14</span></span></td>
<td><span data-ttu-id="ed9eb-809">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-810">CC004</span><span class="sxs-lookup"><span data-stu-id="ed9eb-810">CC004</span></span></td>
<td><span data-ttu-id="ed9eb-811">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-811">Packaging</span></span></td>
<td><span data-ttu-id="ed9eb-812">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-812">10001</span></span></td>
<td><span data-ttu-id="ed9eb-813">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-813">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-814">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-814">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-815">124.57</span><span class="sxs-lookup"><span data-stu-id="ed9eb-815">124.57</span></span></td>
<td><span data-ttu-id="ed9eb-816">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-817">CC002</span><span class="sxs-lookup"><span data-stu-id="ed9eb-817">CC002</span></span></td>
<td><span data-ttu-id="ed9eb-818">Finanzas</span><span class="sxs-lookup"><span data-stu-id="ed9eb-818">Finance</span></span></td>
<td><span data-ttu-id="ed9eb-819">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-819">10001</span></span></td>
<td><span data-ttu-id="ed9eb-820">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-820">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-821">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-821">Fixed cost</span></span></td>
<td><span data-ttu-id="ed9eb-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-822">-675.00</span></span></td>
<td><span data-ttu-id="ed9eb-823">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-824">CC003</span><span class="sxs-lookup"><span data-stu-id="ed9eb-824">CC003</span></span></td>
<td><span data-ttu-id="ed9eb-825">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-825">Assembly</span></span></td>
<td><span data-ttu-id="ed9eb-826">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-826">10001</span></span></td>
<td><span data-ttu-id="ed9eb-827">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-827">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-828">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-828">Fixed cost</span></span></td>
<td><span data-ttu-id="ed9eb-829">438.75</span><span class="sxs-lookup"><span data-stu-id="ed9eb-829">438.75</span></span></td>
<td><span data-ttu-id="ed9eb-830">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-831">CC004</span><span class="sxs-lookup"><span data-stu-id="ed9eb-831">CC004</span></span></td>
<td><span data-ttu-id="ed9eb-832">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-832">Packaging</span></span></td>
<td><span data-ttu-id="ed9eb-833">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-833">10001</span></span></td>
<td><span data-ttu-id="ed9eb-834">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-834">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-835">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-835">Fixed cost</span></span></td>
<td><span data-ttu-id="ed9eb-836">236.25</span><span class="sxs-lookup"><span data-stu-id="ed9eb-836">236.25</span></span></td>
<td><span data-ttu-id="ed9eb-837">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-838">CC002</span><span class="sxs-lookup"><span data-stu-id="ed9eb-838">CC002</span></span></td>
<td><span data-ttu-id="ed9eb-839">Finanzas</span><span class="sxs-lookup"><span data-stu-id="ed9eb-839">Finance</span></span></td>
<td><span data-ttu-id="ed9eb-840">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-840">10001</span></span></td>
<td><span data-ttu-id="ed9eb-841">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-841">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-842">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-842">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="ed9eb-843">-8,150.29</span></span></td>
<td><span data-ttu-id="ed9eb-844">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-845">CC003</span><span class="sxs-lookup"><span data-stu-id="ed9eb-845">CC003</span></span></td>
<td><span data-ttu-id="ed9eb-846">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-846">Assembly</span></span></td>
<td><span data-ttu-id="ed9eb-847">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-847">10001</span></span></td>
<td><span data-ttu-id="ed9eb-848">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-848">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-849">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-849">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="ed9eb-850">5,297.69</span></span></td>
<td><span data-ttu-id="ed9eb-851">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-852">CC004</span><span class="sxs-lookup"><span data-stu-id="ed9eb-852">CC004</span></span></td>
<td><span data-ttu-id="ed9eb-853">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-853">Packaging</span></span></td>
<td><span data-ttu-id="ed9eb-854">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-854">10001</span></span></td>
<td><span data-ttu-id="ed9eb-855">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-855">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-856">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-856">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="ed9eb-857">2,852.60</span></span></td>
<td><span data-ttu-id="ed9eb-858">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-859">CC003</span><span class="sxs-lookup"><span data-stu-id="ed9eb-859">CC003</span></span></td>
<td><span data-ttu-id="ed9eb-860">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-860">Assembly</span></span></td>
<td><span data-ttu-id="ed9eb-861">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-861">10001</span></span></td>
<td><span data-ttu-id="ed9eb-862">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-862">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-863">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-863">Fixed cost</span></span></td>
<td><span data-ttu-id="ed9eb-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="ed9eb-864">-713.75</span></span></td>
<td><span data-ttu-id="ed9eb-865">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-866">Prod 1</span></span></td>
<td><span data-ttu-id="ed9eb-867">Producto 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-867">Product 1</span></span></td>
<td><span data-ttu-id="ed9eb-868">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-868">10001</span></span></td>
<td><span data-ttu-id="ed9eb-869">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-869">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-870">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-870">Fixed cost</span></span></td>
<td><span data-ttu-id="ed9eb-871">535.31</span><span class="sxs-lookup"><span data-stu-id="ed9eb-871">535.31</span></span></td>
<td><span data-ttu-id="ed9eb-872">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-873">Prod 2</span></span></td>
<td><span data-ttu-id="ed9eb-874">Producto 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-874">Product 2</span></span></td>
<td><span data-ttu-id="ed9eb-875">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-875">10001</span></span></td>
<td><span data-ttu-id="ed9eb-876">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-876">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-877">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-877">Fixed cost</span></span></td>
<td><span data-ttu-id="ed9eb-878">178.44</span><span class="sxs-lookup"><span data-stu-id="ed9eb-878">178.44</span></span></td>
<td><span data-ttu-id="ed9eb-879">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-880">CC003</span><span class="sxs-lookup"><span data-stu-id="ed9eb-880">CC003</span></span></td>
<td><span data-ttu-id="ed9eb-881">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-881">Assembly</span></span></td>
<td><span data-ttu-id="ed9eb-882">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-882">10001</span></span></td>
<td><span data-ttu-id="ed9eb-883">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-883">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-884">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-884">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="ed9eb-885">-5,982.83</span></span></td>
<td><span data-ttu-id="ed9eb-886">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-887">Prod 1</span></span></td>
<td><span data-ttu-id="ed9eb-888">Producto 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-888">Product 1</span></span></td>
<td><span data-ttu-id="ed9eb-889">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-889">10001</span></span></td>
<td><span data-ttu-id="ed9eb-890">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-890">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-891">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-891">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="ed9eb-892">4,487.12</span></span></td>
<td><span data-ttu-id="ed9eb-893">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-894">Prod 2</span></span></td>
<td><span data-ttu-id="ed9eb-895">Producto 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-895">Product 2</span></span></td>
<td><span data-ttu-id="ed9eb-896">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-896">10001</span></span></td>
<td><span data-ttu-id="ed9eb-897">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-897">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-898">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-898">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="ed9eb-899">1,495.71</span></span></td>
<td><span data-ttu-id="ed9eb-900">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-901">CC003</span><span class="sxs-lookup"><span data-stu-id="ed9eb-901">CC003</span></span></td>
<td><span data-ttu-id="ed9eb-902">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-902">Assembly</span></span></td>
<td><span data-ttu-id="ed9eb-903">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-903">10001</span></span></td>
<td><span data-ttu-id="ed9eb-904">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-904">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-905">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-905">Fixed cost</span></span></td>
<td><span data-ttu-id="ed9eb-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="ed9eb-906">-286.25</span></span></td>
<td><span data-ttu-id="ed9eb-907">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-908">Prod 1</span></span></td>
<td><span data-ttu-id="ed9eb-909">Producto 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-909">Product 1</span></span></td>
<td><span data-ttu-id="ed9eb-910">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-910">10001</span></span></td>
<td><span data-ttu-id="ed9eb-911">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-911">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-912">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-912">Fixed cost</span></span></td>
<td><span data-ttu-id="ed9eb-913">241.05</span><span class="sxs-lookup"><span data-stu-id="ed9eb-913">241.05</span></span></td>
<td><span data-ttu-id="ed9eb-914">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-915">Prod 2</span></span></td>
<td><span data-ttu-id="ed9eb-916">Producto 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-916">Product 2</span></span></td>
<td><span data-ttu-id="ed9eb-917">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-917">10001</span></span></td>
<td><span data-ttu-id="ed9eb-918">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-918">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-919">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-919">Fixed cost</span></span></td>
<td><span data-ttu-id="ed9eb-920">45.20</span><span class="sxs-lookup"><span data-stu-id="ed9eb-920">45.20</span></span></td>
<td><span data-ttu-id="ed9eb-921">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-922">CC003</span><span class="sxs-lookup"><span data-stu-id="ed9eb-922">CC003</span></span></td>
<td><span data-ttu-id="ed9eb-923">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="ed9eb-923">Assembly</span></span></td>
<td><span data-ttu-id="ed9eb-924">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-924">10001</span></span></td>
<td><span data-ttu-id="ed9eb-925">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-925">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-926">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-926">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="ed9eb-927">-2,977.17</span></span></td>
<td><span data-ttu-id="ed9eb-928">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-929">Prod 1</span></span></td>
<td><span data-ttu-id="ed9eb-930">Producto 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-930">Product 1</span></span></td>
<td><span data-ttu-id="ed9eb-931">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-931">10001</span></span></td>
<td><span data-ttu-id="ed9eb-932">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-932">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-933">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-933">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="ed9eb-934">2,507.09</span></span></td>
<td><span data-ttu-id="ed9eb-935">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ed9eb-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-936">Prod 2</span></span></td>
<td><span data-ttu-id="ed9eb-937">Producto 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-937">Product 2</span></span></td>
<td><span data-ttu-id="ed9eb-938">10001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-938">10001</span></span></td>
<td><span data-ttu-id="ed9eb-939">Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-939">Electricity</span></span></td>
<td><span data-ttu-id="ed9eb-940">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-940">Variable cost</span></span></td>
<td><span data-ttu-id="ed9eb-941">470.08</span><span class="sxs-lookup"><span data-stu-id="ed9eb-941">470.08</span></span></td>
<td><span data-ttu-id="ed9eb-942">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="ed9eb-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="ed9eb-943">Conclusión</span><span class="sxs-lookup"><span data-stu-id="ed9eb-943">Conclusion</span></span>
<span data-ttu-id="ed9eb-944">En la contabilidad financiera, un coste de 10.000,00 para electricidad se envía a un identificador ficticio de centro de coste.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="ed9eb-945">Por lo tanto, los contables de coste sabrán que este coste se debe asignar.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="ed9eb-946">En contabilidad de costes, los costes fluyen en las unidades organizativas y los niveles en función de las directivas y las reglas que se aplican.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="ed9eb-947">Cada coste se ha asociado con una base de asignación que proporciona la mejor evaluación para la asignación de costes.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="ed9eb-948">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="ed9eb-949">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="ed9eb-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="ed9eb-950">Total</span><span class="sxs-lookup"><span data-stu-id="ed9eb-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="ed9eb-951">CC099</span><span class="sxs-lookup"><span data-stu-id="ed9eb-951">CC099</span></span></th>
<th><span data-ttu-id="ed9eb-952">CC001</span><span class="sxs-lookup"><span data-stu-id="ed9eb-952">CC001</span></span></th>
<th><span data-ttu-id="ed9eb-953">CC002</span><span class="sxs-lookup"><span data-stu-id="ed9eb-953">CC002</span></span></th>
<th><span data-ttu-id="ed9eb-954">CC003</span><span class="sxs-lookup"><span data-stu-id="ed9eb-954">CC003</span></span></th>
<th><span data-ttu-id="ed9eb-955">CC004</span><span class="sxs-lookup"><span data-stu-id="ed9eb-955">CC004</span></span></th>
<th><span data-ttu-id="ed9eb-956">Proy 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-956">Proj 1</span></span></th>
<th><span data-ttu-id="ed9eb-957">Proy 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-957">Proj 2</span></span></th>
<th><span data-ttu-id="ed9eb-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="ed9eb-958">Prod 1</span></span></th>
<th><span data-ttu-id="ed9eb-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="ed9eb-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="ed9eb-960">10001 Electricidad</span><span class="sxs-lookup"><span data-stu-id="ed9eb-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="ed9eb-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="ed9eb-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="ed9eb-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="ed9eb-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="ed9eb-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="ed9eb-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="ed9eb-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="ed9eb-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="ed9eb-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="ed9eb-970">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="ed9eb-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-971">0,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="ed9eb-972">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="ed9eb-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-973">0,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-974">0,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-975">0,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-976">0,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-977">0,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-978">776.36</span><span class="sxs-lookup"><span data-stu-id="ed9eb-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-979">223.64</span><span class="sxs-lookup"><span data-stu-id="ed9eb-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="ed9eb-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="ed9eb-981">Coste variable</span><span class="sxs-lookup"><span data-stu-id="ed9eb-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-982">000</span><span class="sxs-lookup"><span data-stu-id="ed9eb-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-983">0,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-984">0,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-985">0,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-986">0,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-987">30,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-988">10,00</span><span class="sxs-lookup"><span data-stu-id="ed9eb-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="ed9eb-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="ed9eb-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ed9eb-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="ed9eb-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="ed9eb-992">Este tema muestra cómo un artículo de costes principales, 10001 Electricidad, fluye por los objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="ed9eb-993">Por tanto, estos gastos generales se asignan al nivel más bajo de la organización.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="ed9eb-994">Es decir, los objetos de coste del nivel más bajo son los que soportan el coste.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="ed9eb-995">Si necesita un flujo visual del coste entre los objetos de coste, puede usar las reglas de directivas de acumulación de costes para visualizar el flujo del coste.</span><span class="sxs-lookup"><span data-stu-id="ed9eb-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="ed9eb-996">Para obtener más información, consulte [Acumulación de costes](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="ed9eb-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>



