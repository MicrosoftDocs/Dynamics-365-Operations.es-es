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
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3976484"
---
# <a name="overhead-calculation"></a><span data-ttu-id="3d6d5-103">Cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="3d6d5-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3d6d5-104">Este tema describe los procesos típicos para calcular y asignar costes generales.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="3d6d5-105">Definición del término</span><span class="sxs-lookup"><span data-stu-id="3d6d5-105">Term definition</span></span>
---------------

<span data-ttu-id="3d6d5-106">Los costes generales son costes que se contraen para dirigir un negocio, pero que no pueden ser atribuidos directamente a ninguna actividad empresarial, productos, o servicio específicos.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="3d6d5-107">Los costes generales proporcionan un soporte fundamental a la generación de actividades rentables.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="3d6d5-108">Algunos ejemplos de costes generales son:</span><span class="sxs-lookup"><span data-stu-id="3d6d5-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="3d6d5-109">Alquiler</span><span class="sxs-lookup"><span data-stu-id="3d6d5-109">Rent</span></span>
-   <span data-ttu-id="3d6d5-110">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-110">Electricity</span></span>
-   <span data-ttu-id="3d6d5-111">Sueldos administrativos</span><span class="sxs-lookup"><span data-stu-id="3d6d5-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="3d6d5-112">Visión general del cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="3d6d5-112">Overhead calculation overview</span></span>
<span data-ttu-id="3d6d5-113">El cálculo de costes generales ejecuta las directivas de contabilidad de costes en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="3d6d5-114">Puede calcular varias veces los costes generales del mismo período fiscal si se han cambiado las directivas de contabilidad de costes o se han detectado errores específicos.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="3d6d5-115">Cada ejecución del cálculo de costes generales se almacena y recibe un identificador de versión único que permite comparar los cálculos de diferentes versiones.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="3d6d5-116">Las entradas de costes que el cálculo de costes generales genera reciben una fecha de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="3d6d5-117">Esta fecha de contabilidad coincide con la fecha final del período fiscal que se usa en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="3d6d5-118">El identificador de versión único consiste en los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3d6d5-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="3d6d5-119">Tipo de versión</span><span class="sxs-lookup"><span data-stu-id="3d6d5-119">Version type</span></span>
-   <span data-ttu-id="3d6d5-120">Fecha y hora</span><span class="sxs-lookup"><span data-stu-id="3d6d5-120">Date and time</span></span>
-   <span data-ttu-id="3d6d5-121">Libro mayor de contabilidad de costes</span><span class="sxs-lookup"><span data-stu-id="3d6d5-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="3d6d5-122">Ejercicio</span><span class="sxs-lookup"><span data-stu-id="3d6d5-122">Fiscal year</span></span>
-   <span data-ttu-id="3d6d5-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="3d6d5-123">Fiscal period</span></span>

<span data-ttu-id="3d6d5-124">El cálculo de costes generales se ejecuta independientemente de la versión.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="3d6d5-125">Por lo tanto, puede calcular la versión de presupuesto antes que la versión real.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="3d6d5-126">El cálculo de costes generales consta de cuatro pasos, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="3d6d5-127">En cada paso, se crea una cabecera de diario que tiene entradas del diario.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="3d6d5-128">Esta cabecera de diario guarda los datos de entrada para cada paso de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="3d6d5-129">Las directivas y las reglas se aplican a cada línea de diario, y las entradas de coste se generan como resultado.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="3d6d5-130">Por tanto, siempre se tiene rastreabilidad completa.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="3d6d5-131">[![Cálculo de costes generales](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="3d6d5-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="3d6d5-132">Calcular y asignar costes generales de electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="3d6d5-133">En la contabilidad financiera, algunos costes, como la electricidad, se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="3d6d5-134">Por lo tanto, no se proporciona una visión de gestión detallada para la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="3d6d5-135">En contabilidad de costes, para proporcionar información de gestión correcta en todas las unidades y niveles organizativos, los costes deben fluir por las unidades organizativas.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="3d6d5-136">Este flujo se debe basar en cualquier registro preciso de consumo o en una evaluación justa.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="3d6d5-137">En la contabilidad general, un coste de la electricidad se puede registrar como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3d6d5-138">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="3d6d5-139">Centro de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="3d6d5-140">Cuenta principal</span><span class="sxs-lookup"><span data-stu-id="3d6d5-140">Main account</span></span></th>
<th><span data-ttu-id="3d6d5-141">Importe en la divisa de contabilidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-142">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="3d6d5-143">CC099</span><span class="sxs-lookup"><span data-stu-id="3d6d5-143">CC099</span></span></td>
<td><span data-ttu-id="3d6d5-144">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-144">Default cost center</span></span></td>
<td><span data-ttu-id="3d6d5-145">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-145">10001</span></span></td>
<td><span data-ttu-id="3d6d5-146">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-146">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="3d6d5-148">Paso 1: Procese el cálculo del comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="3d6d5-149">De forma predeterminada, cuando las entradas de coste se importan de los datos de origen, reciben la clasificación de comportamiento del coste **Sin ordenar** en la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="3d6d5-150">Aplicando reglas de directivas de comportamiento de coste, puede reclasificar entradas de coste como **Coste fijo** o **Coste variable**.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="3d6d5-151">Defina la regla de comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-151">Define the cost behavior rule</span></span>

<span data-ttu-id="3d6d5-152">En algunos casos, parte del coste es una cuota fija, y el coste pendiente se basa en el consumo.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="3d6d5-153">Las facturas de electricidad coinciden a menudo con esta definición.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="3d6d5-154">Tras pagar una cuota fija específica, paga el consumo por kilovatio-hora (Kwh).</span><span class="sxs-lookup"><span data-stu-id="3d6d5-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="3d6d5-155">Por ejemplo, si la cuota de coste fijo es de 1.000,00, la regla de comportamiento del coste se define como sigue:</span><span class="sxs-lookup"><span data-stu-id="3d6d5-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="3d6d5-156">Importe fijo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="3d6d5-157">0 &lt;= 1.000,00 = Fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="3d6d5-158">1.000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="3d6d5-159">Diario</span><span class="sxs-lookup"><span data-stu-id="3d6d5-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3d6d5-160">Diario</span><span class="sxs-lookup"><span data-stu-id="3d6d5-160">Journal</span></span></th>
<th><span data-ttu-id="3d6d5-161">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="3d6d5-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="3d6d5-162">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="3d6d5-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="3d6d5-163">Versión</span><span class="sxs-lookup"><span data-stu-id="3d6d5-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-164">00001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-164">00001</span></span></td>
<td><span data-ttu-id="3d6d5-165">Diario de cálculo de comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="3d6d5-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="3d6d5-166">Fiscal</span><span class="sxs-lookup"><span data-stu-id="3d6d5-166">Fiscal</span></span></td>
<td><span data-ttu-id="3d6d5-167">2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-167">2017</span></span></td>
<td><span data-ttu-id="3d6d5-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-168">Period 1</span></span></td>
<td><span data-ttu-id="3d6d5-169">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="3d6d5-170">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="3d6d5-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3d6d5-171">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="3d6d5-172">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="3d6d5-173">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-173">Cost element</span></span></th>
<th><span data-ttu-id="3d6d5-174">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="3d6d5-174">Cost behavior</span></span></th>
<th><span data-ttu-id="3d6d5-175">Importe</span><span class="sxs-lookup"><span data-stu-id="3d6d5-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-176">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="3d6d5-177">CC099</span><span class="sxs-lookup"><span data-stu-id="3d6d5-177">CC099</span></span></td>
<td><span data-ttu-id="3d6d5-178">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-178">Default cost center</span></span></td>
<td><span data-ttu-id="3d6d5-179">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-179">10001</span></span></td>
<td><span data-ttu-id="3d6d5-180">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-180">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-181">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="3d6d5-181">Unclassified</span></span></td>
<td><span data-ttu-id="3d6d5-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="3d6d5-183">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="3d6d5-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3d6d5-184">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="3d6d5-185">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-185">Cost element</span></span></th>
<th><span data-ttu-id="3d6d5-186">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="3d6d5-186">Cost behavior</span></span></th>
<th><span data-ttu-id="3d6d5-187">Importe</span><span class="sxs-lookup"><span data-stu-id="3d6d5-187">Amount</span></span></th>
<th><span data-ttu-id="3d6d5-188">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-189">CC099</span><span class="sxs-lookup"><span data-stu-id="3d6d5-189">CC099</span></span></td>
<td><span data-ttu-id="3d6d5-190">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-190">Default cost center</span></span></td>
<td><span data-ttu-id="3d6d5-191">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-191">10001</span></span></td>
<td><span data-ttu-id="3d6d5-192">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-192">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-193">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="3d6d5-193">Unclassified</span></span></td>
<td><span data-ttu-id="3d6d5-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-194">10,000.00</span></span></td>
<td><span data-ttu-id="3d6d5-195">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-196">CC099</span><span class="sxs-lookup"><span data-stu-id="3d6d5-196">CC099</span></span></td>
<td><span data-ttu-id="3d6d5-197">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-197">Default cost center</span></span></td>
<td><span data-ttu-id="3d6d5-198">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-198">10001</span></span></td>
<td><span data-ttu-id="3d6d5-199">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-199">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-200">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="3d6d5-200">Unclassified</span></span></td>
<td><span data-ttu-id="3d6d5-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-201">-10,000.00</span></span></td>
<td><span data-ttu-id="3d6d5-202">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-203">CC099</span><span class="sxs-lookup"><span data-stu-id="3d6d5-203">CC099</span></span></td>
<td><span data-ttu-id="3d6d5-204">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-204">Default cost center</span></span></td>
<td><span data-ttu-id="3d6d5-205">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-205">10001</span></span></td>
<td><span data-ttu-id="3d6d5-206">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-206">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-207">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-207">Fixed cost</span></span></td>
<td><span data-ttu-id="3d6d5-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-208">1,000.00</span></span></td>
<td><span data-ttu-id="3d6d5-209">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-210">CC099</span><span class="sxs-lookup"><span data-stu-id="3d6d5-210">CC099</span></span></td>
<td><span data-ttu-id="3d6d5-211">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-211">Default cost center</span></span></td>
<td><span data-ttu-id="3d6d5-212">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-212">10001</span></span></td>
<td><span data-ttu-id="3d6d5-213">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-213">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-214">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-214">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-215">9,000.00</span></span></td>
<td><span data-ttu-id="3d6d5-216">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3d6d5-217">Para obtener más información, consulte [Crear y asignar una directiva de comportamiento de costes a una unidad de control de costes](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="3d6d5-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="3d6d5-218">Paso 2: Procese el cálculo de distribución de costes</span><span class="sxs-lookup"><span data-stu-id="3d6d5-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="3d6d5-219">La distribución de costes se usa para redistribuir costes desde un objeto de coste a uno o más objetos de coste aplicando una base relevante de la asignación.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="3d6d5-220">La distribución de costes y la asignación de costes difieren en que la distribución de costes siempre se produce en el nivel de elemento de costes principal del coste original.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="3d6d5-221">Defina la regla de distribución del coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-221">Define the cost distribution rule</span></span>

<span data-ttu-id="3d6d5-222">En la contabilidad financiera, los costes de electricidad se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="3d6d5-223">En contabilidad de costes, este método no es suficientemente detallado.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="3d6d5-224">El coste variable debe distribuirse a los objetos individuales de coste aplicando una base justa.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="3d6d5-225">La base de asignación más lógica es el consumo de electricidad (Kwh).</span><span class="sxs-lookup"><span data-stu-id="3d6d5-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="3d6d5-226">Se crea un miembro de dimensión estadística que se denomina Electricity, y se registra el consumo de electricidad.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="3d6d5-227">De forma predeterminada, todos los miembros de dimensión estadísticos estarán disponibles como bases de asignación.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3d6d5-228">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-228">Cost object</span></span></th>
<th><span data-ttu-id="3d6d5-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="3d6d5-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-230">CC001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-230">CC001</span></span></td>
<td><span data-ttu-id="3d6d5-231">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-231">HR</span></span></td>
<td><span data-ttu-id="3d6d5-232">1.000</span><span class="sxs-lookup"><span data-stu-id="3d6d5-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-233">CC002</span><span class="sxs-lookup"><span data-stu-id="3d6d5-233">CC002</span></span></td>
<td><span data-ttu-id="3d6d5-234">Finanzas</span><span class="sxs-lookup"><span data-stu-id="3d6d5-234">Finance</span></span></td>
<td><span data-ttu-id="3d6d5-235">6.000</span><span class="sxs-lookup"><span data-stu-id="3d6d5-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-236">CC003</span><span class="sxs-lookup"><span data-stu-id="3d6d5-236">CC003</span></span></td>
<td><span data-ttu-id="3d6d5-237">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-237">Assembly</span></span></td>
<td><span data-ttu-id="3d6d5-238">0</span><span class="sxs-lookup"><span data-stu-id="3d6d5-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3d6d5-239">La tabla siguiente muestra el resultado cuando se aplica el consumo de electricidad como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3d6d5-240">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-240">Cost object</span></span></th>
<th><span data-ttu-id="3d6d5-241">Magnitud</span><span class="sxs-lookup"><span data-stu-id="3d6d5-241">Magnitude</span></span></th>
<th><span data-ttu-id="3d6d5-242">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="3d6d5-242">Allocation factor</span></span></th>
<th><span data-ttu-id="3d6d5-243">Importe</span><span class="sxs-lookup"><span data-stu-id="3d6d5-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-244">CC001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-244">CC001</span></span></td>
<td><span data-ttu-id="3d6d5-245">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-245">HR</span></span></td>
<td><span data-ttu-id="3d6d5-246">1.000</span><span class="sxs-lookup"><span data-stu-id="3d6d5-246">1,000</span></span></td>
<td><span data-ttu-id="3d6d5-247">(1.000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="3d6d5-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="3d6d5-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-249">CC002</span><span class="sxs-lookup"><span data-stu-id="3d6d5-249">CC002</span></span></td>
<td><span data-ttu-id="3d6d5-250">Finanzas</span><span class="sxs-lookup"><span data-stu-id="3d6d5-250">Finance</span></span></td>
<td><span data-ttu-id="3d6d5-251">6.000</span><span class="sxs-lookup"><span data-stu-id="3d6d5-251">6,000</span></span></td>
<td><span data-ttu-id="3d6d5-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="3d6d5-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="3d6d5-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-254">CC003</span><span class="sxs-lookup"><span data-stu-id="3d6d5-254">CC003</span></span></td>
<td><span data-ttu-id="3d6d5-255">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-255">Assembly</span></span></td>
<td><span data-ttu-id="3d6d5-256">0</span><span class="sxs-lookup"><span data-stu-id="3d6d5-256">0</span></span></td>
<td><span data-ttu-id="3d6d5-257">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="3d6d5-258">0,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3d6d5-259">El coste fijo debe distribuirse uniformemente a los objetos individuales de costes que han consumido electricidad.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="3d6d5-260">Puede obtener este resultado usando el miembro de dimensión estadístico de electricidad en una base de asignación de la fórmula: (Electricidad &gt; 0,00) La tabla siguiente muestra el resultado cuando el consumo de electricidad se aplica como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3d6d5-261">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-261">Cost object</span></span></th>
<th><span data-ttu-id="3d6d5-262">Fórmula</span><span class="sxs-lookup"><span data-stu-id="3d6d5-262">Formula</span></span></th>
<th><span data-ttu-id="3d6d5-263">Magnitud</span><span class="sxs-lookup"><span data-stu-id="3d6d5-263">Magnitude</span></span></th>
<th><span data-ttu-id="3d6d5-264">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="3d6d5-264">Allocation factor</span></span></th>
<th><span data-ttu-id="3d6d5-265">Importe</span><span class="sxs-lookup"><span data-stu-id="3d6d5-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-266">CC001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-266">CC001</span></span></td>
<td><span data-ttu-id="3d6d5-267">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-267">HR</span></span></td>
<td><span data-ttu-id="3d6d5-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="3d6d5-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="3d6d5-269">1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-269">1</span></span></td>
<td><span data-ttu-id="3d6d5-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="3d6d5-271">500,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-272">CC002</span><span class="sxs-lookup"><span data-stu-id="3d6d5-272">CC002</span></span></td>
<td><span data-ttu-id="3d6d5-273">Finanzas</span><span class="sxs-lookup"><span data-stu-id="3d6d5-273">Finance</span></span></td>
<td><span data-ttu-id="3d6d5-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="3d6d5-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="3d6d5-275">1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-275">1</span></span></td>
<td><span data-ttu-id="3d6d5-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="3d6d5-277">500,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-278">CC003</span><span class="sxs-lookup"><span data-stu-id="3d6d5-278">CC003</span></span></td>
<td><span data-ttu-id="3d6d5-279">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-279">Assembly</span></span></td>
<td><span data-ttu-id="3d6d5-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="3d6d5-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="3d6d5-281">0</span><span class="sxs-lookup"><span data-stu-id="3d6d5-281">0</span></span></td>
<td><span data-ttu-id="3d6d5-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="3d6d5-283">0,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="3d6d5-284">Diario</span><span class="sxs-lookup"><span data-stu-id="3d6d5-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3d6d5-285">Diario</span><span class="sxs-lookup"><span data-stu-id="3d6d5-285">Journal</span></span></th>
<th><span data-ttu-id="3d6d5-286">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="3d6d5-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="3d6d5-287">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="3d6d5-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="3d6d5-288">Versión</span><span class="sxs-lookup"><span data-stu-id="3d6d5-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-289">00002</span><span class="sxs-lookup"><span data-stu-id="3d6d5-289">00002</span></span></td>
<td><span data-ttu-id="3d6d5-290">Diario de cálculo de la distribución de costes</span><span class="sxs-lookup"><span data-stu-id="3d6d5-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="3d6d5-291">Fiscal</span><span class="sxs-lookup"><span data-stu-id="3d6d5-291">Fiscal</span></span></td>
<td><span data-ttu-id="3d6d5-292">2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-292">2017</span></span></td>
<td><span data-ttu-id="3d6d5-293">Período 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-293">Period 1</span></span></td>
<td><span data-ttu-id="3d6d5-294">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="3d6d5-295">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="3d6d5-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3d6d5-296">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="3d6d5-297">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="3d6d5-298">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-298">Cost element</span></span></th>
<th><span data-ttu-id="3d6d5-299">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="3d6d5-299">Cost behavior</span></span></th>
<th><span data-ttu-id="3d6d5-300">Importe</span><span class="sxs-lookup"><span data-stu-id="3d6d5-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-301">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="3d6d5-302">CC099</span><span class="sxs-lookup"><span data-stu-id="3d6d5-302">CC099</span></span></td>
<td><span data-ttu-id="3d6d5-303">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-303">Default cost center</span></span></td>
<td><span data-ttu-id="3d6d5-304">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-304">10001</span></span></td>
<td><span data-ttu-id="3d6d5-305">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-305">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-306">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-306">Fixed cost</span></span></td>
<td><span data-ttu-id="3d6d5-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-308">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="3d6d5-309">CC099</span><span class="sxs-lookup"><span data-stu-id="3d6d5-309">CC099</span></span></td>
<td><span data-ttu-id="3d6d5-310">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-310">Default cost center</span></span></td>
<td><span data-ttu-id="3d6d5-311">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-311">10001</span></span></td>
<td><span data-ttu-id="3d6d5-312">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-312">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-313">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-313">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-314">9.000,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="3d6d5-315">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="3d6d5-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3d6d5-316">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="3d6d5-317">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-317">Cost element</span></span></th>
<th><span data-ttu-id="3d6d5-318">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="3d6d5-318">Cost behavior</span></span></th>
<th><span data-ttu-id="3d6d5-319">Importe</span><span class="sxs-lookup"><span data-stu-id="3d6d5-319">Amount</span></span></th>
<th><span data-ttu-id="3d6d5-320">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-321">CC099</span><span class="sxs-lookup"><span data-stu-id="3d6d5-321">CC099</span></span></td>
<td><span data-ttu-id="3d6d5-322">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-322">Default cost center</span></span></td>
<td><span data-ttu-id="3d6d5-323">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-323">10001</span></span></td>
<td><span data-ttu-id="3d6d5-324">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-324">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-325">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-325">Fixed cost</span></span></td>
<td><span data-ttu-id="3d6d5-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-326">-1,000.00</span></span></td>
<td><span data-ttu-id="3d6d5-327">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-328">CC001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-328">CC001</span></span></td>
<td><span data-ttu-id="3d6d5-329">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-329">HR</span></span></td>
<td><span data-ttu-id="3d6d5-330">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-330">10001</span></span></td>
<td><span data-ttu-id="3d6d5-331">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-331">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-332">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-332">Fixed cost</span></span></td>
<td><span data-ttu-id="3d6d5-333">500,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-333">500.00</span></span></td>
<td><span data-ttu-id="3d6d5-334">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-335">CC002</span><span class="sxs-lookup"><span data-stu-id="3d6d5-335">CC002</span></span></td>
<td><span data-ttu-id="3d6d5-336">Finanzas</span><span class="sxs-lookup"><span data-stu-id="3d6d5-336">Finance</span></span></td>
<td><span data-ttu-id="3d6d5-337">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-337">10001</span></span></td>
<td><span data-ttu-id="3d6d5-338">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-338">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-339">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-339">Fixed cost</span></span></td>
<td><span data-ttu-id="3d6d5-340">500,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-340">500.00</span></span></td>
<td><span data-ttu-id="3d6d5-341">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-342">CC099</span><span class="sxs-lookup"><span data-stu-id="3d6d5-342">CC099</span></span></td>
<td><span data-ttu-id="3d6d5-343">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-343">Default cost center</span></span></td>
<td><span data-ttu-id="3d6d5-344">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-344">10001</span></span></td>
<td><span data-ttu-id="3d6d5-345">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-345">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-346">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-346">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-347">-9,000.00</span></span></td>
<td><span data-ttu-id="3d6d5-348">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-349">CC001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-349">CC001</span></span></td>
<td><span data-ttu-id="3d6d5-350">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-350">HR</span></span></td>
<td><span data-ttu-id="3d6d5-351">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-351">10001</span></span></td>
<td><span data-ttu-id="3d6d5-352">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-352">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-353">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-353">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="3d6d5-354">1,285.71</span></span></td>
<td><span data-ttu-id="3d6d5-355">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-356">CC002</span><span class="sxs-lookup"><span data-stu-id="3d6d5-356">CC002</span></span></td>
<td><span data-ttu-id="3d6d5-357">Finanzas</span><span class="sxs-lookup"><span data-stu-id="3d6d5-357">Finance</span></span></td>
<td><span data-ttu-id="3d6d5-358">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-358">10001</span></span></td>
<td><span data-ttu-id="3d6d5-359">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-359">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-360">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-360">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="3d6d5-361">7,714.29</span></span></td>
<td><span data-ttu-id="3d6d5-362">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3d6d5-363">Para obtener más información, consulte [Crear y asignar una directiva de distribución de costes a una unidad de control de costes](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="3d6d5-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="3d6d5-364">Paso 3: Procese el cálculo de las tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="3d6d5-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="3d6d5-365">La tasa de costes generales se usa para cargar uno o varios objetos de coste específicos.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="3d6d5-366">El cargo se basa en un índice de coste predeterminado y la magnitud de la base de asignación asignada.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="3d6d5-367">Defina la tasa de costes generales</span><span class="sxs-lookup"><span data-stu-id="3d6d5-367">Define the overhead rate</span></span>

<span data-ttu-id="3d6d5-368">El objeto de coste CC001 HR contribuye a un conjunto de proyectos internos.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="3d6d5-369">Se crea un miembro de dimensión estadística que se denomina proyectos HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3d6d5-370">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-370">Cost object</span></span></th>
<th><span data-ttu-id="3d6d5-371">Horas</span><span class="sxs-lookup"><span data-stu-id="3d6d5-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-372">Proy 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-372">Proj 1</span></span></td>
<td><span data-ttu-id="3d6d5-373">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-373">Project 1</span></span></td>
<td><span data-ttu-id="3d6d5-374">3</span><span class="sxs-lookup"><span data-stu-id="3d6d5-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-375">Proy 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-375">Proj 2</span></span></td>
<td><span data-ttu-id="3d6d5-376">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-376">Project 2</span></span></td>
<td><span data-ttu-id="3d6d5-377">1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3d6d5-378">Una tasa de coste predeterminada para la contribución de los proyectos de coste se ha definido.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3d6d5-379">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-379">Cost object</span></span></th>
<th><span data-ttu-id="3d6d5-380">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-380">Cost element</span></span></th>
<th><span data-ttu-id="3d6d5-381">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="3d6d5-381">Cost behavior</span></span></th>
<th><span data-ttu-id="3d6d5-382">Unidades</span><span class="sxs-lookup"><span data-stu-id="3d6d5-382">Units</span></span></th>
<th><span data-ttu-id="3d6d5-383">Índice</span><span class="sxs-lookup"><span data-stu-id="3d6d5-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-384">CC001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-384">CC001</span></span></td>
<td><span data-ttu-id="3d6d5-385">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-385">HR</span></span></td>
<td><span data-ttu-id="3d6d5-386">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-386">10001</span></span></td>
<td><span data-ttu-id="3d6d5-387">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-387">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-388">1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-388">1</span></span></td>
<td><span data-ttu-id="3d6d5-389">10</span><span class="sxs-lookup"><span data-stu-id="3d6d5-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3d6d5-390">La tabla siguiente muestra el resultado cuando los proyectos HR se aplican como base de la asignación.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3d6d5-391">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-391">Cost object</span></span></th>
<th><span data-ttu-id="3d6d5-392">Magnitud</span><span class="sxs-lookup"><span data-stu-id="3d6d5-392">Magnitude</span></span></th>
<th><span data-ttu-id="3d6d5-393">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-393">Cost element</span></span></th>
<th><span data-ttu-id="3d6d5-394">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="3d6d5-394">Allocation factor</span></span></th>
<th><span data-ttu-id="3d6d5-395">Importe</span><span class="sxs-lookup"><span data-stu-id="3d6d5-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-396">Proy 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-396">Proj 1</span></span></td>
<td><span data-ttu-id="3d6d5-397">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-397">Project 1</span></span></td>
<td><span data-ttu-id="3d6d5-398">3</span><span class="sxs-lookup"><span data-stu-id="3d6d5-398">3</span></span></td>
<td><span data-ttu-id="3d6d5-399">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-399">10001</span></span></td>
<td><span data-ttu-id="3d6d5-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="3d6d5-401">30,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-402">Proy 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-402">Proj 2</span></span></td>
<td><span data-ttu-id="3d6d5-403">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-403">Project 2</span></span></td>
<td><span data-ttu-id="3d6d5-404">1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-404">1</span></span></td>
<td><span data-ttu-id="3d6d5-405">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-405">10001</span></span></td>
<td><span data-ttu-id="3d6d5-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="3d6d5-407">10,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="3d6d5-408">Diario</span><span class="sxs-lookup"><span data-stu-id="3d6d5-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3d6d5-409">Diario</span><span class="sxs-lookup"><span data-stu-id="3d6d5-409">Journal</span></span></th>
<th><span data-ttu-id="3d6d5-410">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="3d6d5-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="3d6d5-411">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="3d6d5-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="3d6d5-412">Versión</span><span class="sxs-lookup"><span data-stu-id="3d6d5-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-413">00003</span><span class="sxs-lookup"><span data-stu-id="3d6d5-413">00003</span></span></td>
<td><span data-ttu-id="3d6d5-414">Diario de cálculo de tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="3d6d5-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="3d6d5-415">Fiscal</span><span class="sxs-lookup"><span data-stu-id="3d6d5-415">Fiscal</span></span></td>
<td><span data-ttu-id="3d6d5-416">2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-416">2017</span></span></td>
<td><span data-ttu-id="3d6d5-417">Período 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-417">Period 1</span></span></td>
<td><span data-ttu-id="3d6d5-418">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="3d6d5-419">Entradas de diario (entradas de diario para cálculo de tasas de costes generales)</span><span class="sxs-lookup"><span data-stu-id="3d6d5-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3d6d5-420">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="3d6d5-421">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-421">Cost object</span></span></th>
<th><span data-ttu-id="3d6d5-422">Magnitud</span><span class="sxs-lookup"><span data-stu-id="3d6d5-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-423">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="3d6d5-424">Proy 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-424">Proj 1</span></span></td>
<td><span data-ttu-id="3d6d5-425">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="3d6d5-426">3,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-427">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="3d6d5-428">Proy 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-428">Proj 2</span></span></td>
<td><span data-ttu-id="3d6d5-429">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="3d6d5-430">1,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="3d6d5-431">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="3d6d5-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3d6d5-432">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="3d6d5-433">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-433">Cost element</span></span></th>
<th><span data-ttu-id="3d6d5-434">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="3d6d5-434">Cost behavior</span></span></th>
<th><span data-ttu-id="3d6d5-435">Importe</span><span class="sxs-lookup"><span data-stu-id="3d6d5-435">Amount</span></span></th>
<th><span data-ttu-id="3d6d5-436">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-437">CC0001</span></span></td>
<td><span data-ttu-id="3d6d5-438">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-438">HR</span></span></td>
<td><span data-ttu-id="3d6d5-439">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-439">10001</span></span></td>
<td><span data-ttu-id="3d6d5-440">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-440">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-441">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-441">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-442">-30.00</span></span></td>
<td><span data-ttu-id="3d6d5-443">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-444">Proy 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-444">Proj 1</span></span></td>
<td><span data-ttu-id="3d6d5-445">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="3d6d5-446">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-446">10001</span></span></td>
<td><span data-ttu-id="3d6d5-447">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-447">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-448">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-448">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-449">30,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-449">30.00</span></span></td>
<td><span data-ttu-id="3d6d5-450">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-451">CC001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-451">CC001</span></span></td>
<td><span data-ttu-id="3d6d5-452">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-452">HR</span></span></td>
<td><span data-ttu-id="3d6d5-453">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-453">10001</span></span></td>
<td><span data-ttu-id="3d6d5-454">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-454">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-455">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-455">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-456">-10.00</span></span></td>
<td><span data-ttu-id="3d6d5-457">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-458">Proy 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-458">Proj 2</span></span></td>
<td><span data-ttu-id="3d6d5-459">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="3d6d5-460">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-460">10001</span></span></td>
<td><span data-ttu-id="3d6d5-461">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-461">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-462">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-462">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-463">10,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-463">10.00</span></span></td>
<td><span data-ttu-id="3d6d5-464">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3d6d5-465">Para obtener más información, consulte [Realizar cálculo de costes generales](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="3d6d5-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="3d6d5-466">Paso 4: Procese el cálculo de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="3d6d5-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="3d6d5-467">La asignación es utilizada para asignar el saldo de un objeto de coste a otros objetos de coste aplicando una base de asignación.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="3d6d5-468">Finance admite el método de asignación recíproco.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="3d6d5-469">En el método de asignación recíproco, se reconocen completamente los servicios mutuos que los objetos de coste auxiliar intercambian.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="3d6d5-470">El sistema determina automáticamente el orden correcto para realizar las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="3d6d5-471">El saldo de un objeto de coste se asigna según una única base de asignación.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="3d6d5-472">Las asignaciones entre dimensiones de objetos de coste y sus miembros respectivos se admiten.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="3d6d5-473">El orden de asignación se controla por unidad de control de costes.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="3d6d5-474">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="3d6d5-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="3d6d5-475">Defina la asignación de costes</span><span class="sxs-lookup"><span data-stu-id="3d6d5-475">Define the cost allocation</span></span>

<span data-ttu-id="3d6d5-476">A continuación se indica un ejemplo sencillo que explica cómo puede realizar el seguimiento del flujo de coste.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="3d6d5-477">El objeto de coste CC001 HR contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="3d6d5-478">Se crea un miembro de dimensión estadística que se denomina servicios HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3d6d5-479">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-479">Cost object</span></span></th>
<th><span data-ttu-id="3d6d5-480">Servicios HR</span><span class="sxs-lookup"><span data-stu-id="3d6d5-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-481">CC002</span><span class="sxs-lookup"><span data-stu-id="3d6d5-481">CC002</span></span></td>
<td><span data-ttu-id="3d6d5-482">Finanzas</span><span class="sxs-lookup"><span data-stu-id="3d6d5-482">Finance</span></span></td>
<td><span data-ttu-id="3d6d5-483">35</span><span class="sxs-lookup"><span data-stu-id="3d6d5-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-484">CC003</span><span class="sxs-lookup"><span data-stu-id="3d6d5-484">CC003</span></span></td>
<td><span data-ttu-id="3d6d5-485">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-485">Assembly</span></span></td>
<td><span data-ttu-id="3d6d5-486">55</span><span class="sxs-lookup"><span data-stu-id="3d6d5-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-487">CC004</span><span class="sxs-lookup"><span data-stu-id="3d6d5-487">CC004</span></span></td>
<td><span data-ttu-id="3d6d5-488">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-488">Packaging</span></span></td>
<td><span data-ttu-id="3d6d5-489">10</span><span class="sxs-lookup"><span data-stu-id="3d6d5-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3d6d5-490">El objeto de coste CC002 Finanzas contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="3d6d5-491">Se crea un miembro de dimensión estadística que se denomina Finanzas para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3d6d5-492">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-492">Cost object</span></span></th>
<th><span data-ttu-id="3d6d5-493">Servicios financieros</span><span class="sxs-lookup"><span data-stu-id="3d6d5-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-494">CC003</span><span class="sxs-lookup"><span data-stu-id="3d6d5-494">CC003</span></span></td>
<td><span data-ttu-id="3d6d5-495">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-495">Assembly</span></span></td>
<td><span data-ttu-id="3d6d5-496">65</span><span class="sxs-lookup"><span data-stu-id="3d6d5-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-497">CC004</span><span class="sxs-lookup"><span data-stu-id="3d6d5-497">CC004</span></span></td>
<td><span data-ttu-id="3d6d5-498">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-498">Packaging</span></span></td>
<td><span data-ttu-id="3d6d5-499">35</span><span class="sxs-lookup"><span data-stu-id="3d6d5-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3d6d5-500">El objeto de coste CC003 Asamblea contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="3d6d5-501">Se crea un miembro de dimensión estadística que se denomina servicios de Asamblea para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3d6d5-502">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-502">Cost object</span></span></th>
<th><span data-ttu-id="3d6d5-503">Servicios de la asamblea (horas)</span><span class="sxs-lookup"><span data-stu-id="3d6d5-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-504">Prod 1</span></span></td>
<td><span data-ttu-id="3d6d5-505">Producto 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-505">Product 1</span></span></td>
<td><span data-ttu-id="3d6d5-506">60</span><span class="sxs-lookup"><span data-stu-id="3d6d5-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-507">Prod 2</span></span></td>
<td><span data-ttu-id="3d6d5-508">Producto 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-508">Product 2</span></span></td>
<td><span data-ttu-id="3d6d5-509">20</span><span class="sxs-lookup"><span data-stu-id="3d6d5-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3d6d5-510">El objeto de coste CC004 Embalaje contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="3d6d5-511">Se crea un miembro de dimensión estadística que se denomina servicios de Embalaje para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3d6d5-512">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-512">Cost object</span></span></th>
<th><span data-ttu-id="3d6d5-513">Servicios de embalaje (horas)</span><span class="sxs-lookup"><span data-stu-id="3d6d5-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-514">Prod 1</span></span></td>
<td><span data-ttu-id="3d6d5-515">Producto 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-515">Product 1</span></span></td>
<td><span data-ttu-id="3d6d5-516">80</span><span class="sxs-lookup"><span data-stu-id="3d6d5-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-517">Prod 2</span></span></td>
<td><span data-ttu-id="3d6d5-518">Producto 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-518">Product 2</span></span></td>
<td><span data-ttu-id="3d6d5-519">15</span><span class="sxs-lookup"><span data-stu-id="3d6d5-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="3d6d5-520">Las medidas estadísticas como las horas de la producción que un producto consume se pueden deducir de los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="3d6d5-521">Para obtener más información, vea [Plantilla de proveedor de medidas estadísticas](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="3d6d5-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="3d6d5-522">La tabla siguiente muestra el resultado cuando se aplican los servicios de HR como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="3d6d5-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3d6d5-523">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-523">Cost object</span></span></th>
<th><span data-ttu-id="3d6d5-524">Magnitud</span><span class="sxs-lookup"><span data-stu-id="3d6d5-524">Magnitude</span></span></th>
<th><span data-ttu-id="3d6d5-525">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="3d6d5-525">Allocation factor</span></span></th>
<th><span data-ttu-id="3d6d5-526">Importe</span><span class="sxs-lookup"><span data-stu-id="3d6d5-526">Amount</span></span></th>
<th><span data-ttu-id="3d6d5-527">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="3d6d5-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-528">CC002</span><span class="sxs-lookup"><span data-stu-id="3d6d5-528">CC002</span></span></td>
<td><span data-ttu-id="3d6d5-529">Finanzas</span><span class="sxs-lookup"><span data-stu-id="3d6d5-529">Finance</span></span></td>
<td><span data-ttu-id="3d6d5-530">35</span><span class="sxs-lookup"><span data-stu-id="3d6d5-530">35</span></span></td>
<td><span data-ttu-id="3d6d5-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="3d6d5-532">175.00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-532">175.00</span></span></td>
<td><span data-ttu-id="3d6d5-533">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-534">CC003</span><span class="sxs-lookup"><span data-stu-id="3d6d5-534">CC003</span></span></td>
<td><span data-ttu-id="3d6d5-535">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-535">Assembly</span></span></td>
<td><span data-ttu-id="3d6d5-536">55</span><span class="sxs-lookup"><span data-stu-id="3d6d5-536">55</span></span></td>
<td><span data-ttu-id="3d6d5-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="3d6d5-538">275.00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-538">275.00</span></span></td>
<td><span data-ttu-id="3d6d5-539">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-540">CC004</span><span class="sxs-lookup"><span data-stu-id="3d6d5-540">CC004</span></span></td>
<td><span data-ttu-id="3d6d5-541">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-541">Packaging</span></span></td>
<td><span data-ttu-id="3d6d5-542">10</span><span class="sxs-lookup"><span data-stu-id="3d6d5-542">10</span></span></td>
<td><span data-ttu-id="3d6d5-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="3d6d5-544">50,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-544">50.00</span></span></td>
<td><span data-ttu-id="3d6d5-545">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-546">CC002</span><span class="sxs-lookup"><span data-stu-id="3d6d5-546">CC002</span></span></td>
<td><span data-ttu-id="3d6d5-547">Finanzas</span><span class="sxs-lookup"><span data-stu-id="3d6d5-547">Finance</span></span></td>
<td><span data-ttu-id="3d6d5-548">35</span><span class="sxs-lookup"><span data-stu-id="3d6d5-548">35</span></span></td>
<td><span data-ttu-id="3d6d5-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="3d6d5-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="3d6d5-550">436.00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-550">436.00</span></span></td>
<td><span data-ttu-id="3d6d5-551">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-552">CC003</span><span class="sxs-lookup"><span data-stu-id="3d6d5-552">CC003</span></span></td>
<td><span data-ttu-id="3d6d5-553">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-553">Assembly</span></span></td>
<td><span data-ttu-id="3d6d5-554">55</span><span class="sxs-lookup"><span data-stu-id="3d6d5-554">55</span></span></td>
<td><span data-ttu-id="3d6d5-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="3d6d5-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="3d6d5-556">685.14</span><span class="sxs-lookup"><span data-stu-id="3d6d5-556">685.14</span></span></td>
<td><span data-ttu-id="3d6d5-557">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-558">CC004</span><span class="sxs-lookup"><span data-stu-id="3d6d5-558">CC004</span></span></td>
<td><span data-ttu-id="3d6d5-559">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-559">Packaging</span></span></td>
<td><span data-ttu-id="3d6d5-560">10</span><span class="sxs-lookup"><span data-stu-id="3d6d5-560">10</span></span></td>
<td><span data-ttu-id="3d6d5-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="3d6d5-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="3d6d5-562">124.57</span><span class="sxs-lookup"><span data-stu-id="3d6d5-562">124.57</span></span></td>
<td><span data-ttu-id="3d6d5-563">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3d6d5-564">La tabla siguiente muestra el resultado cuando se aplican los servicios de Finanzas como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="3d6d5-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3d6d5-565">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-565">Cost object</span></span></th>
<th><span data-ttu-id="3d6d5-566">Magnitud</span><span class="sxs-lookup"><span data-stu-id="3d6d5-566">Magnitude</span></span></th>
<th><span data-ttu-id="3d6d5-567">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="3d6d5-567">Allocation factor</span></span></th>
<th><span data-ttu-id="3d6d5-568">Importe</span><span class="sxs-lookup"><span data-stu-id="3d6d5-568">Amount</span></span></th>
<th><span data-ttu-id="3d6d5-569">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="3d6d5-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-570">CC003</span><span class="sxs-lookup"><span data-stu-id="3d6d5-570">CC003</span></span></td>
<td><span data-ttu-id="3d6d5-571">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-571">Assembly</span></span></td>
<td><span data-ttu-id="3d6d5-572">65</span><span class="sxs-lookup"><span data-stu-id="3d6d5-572">65</span></span></td>
<td><span data-ttu-id="3d6d5-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="3d6d5-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="3d6d5-574">438.75</span><span class="sxs-lookup"><span data-stu-id="3d6d5-574">438.75</span></span></td>
<td><span data-ttu-id="3d6d5-575">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-576">CC004</span><span class="sxs-lookup"><span data-stu-id="3d6d5-576">CC004</span></span></td>
<td><span data-ttu-id="3d6d5-577">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-577">Packaging</span></span></td>
<td><span data-ttu-id="3d6d5-578">35</span><span class="sxs-lookup"><span data-stu-id="3d6d5-578">35</span></span></td>
<td><span data-ttu-id="3d6d5-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="3d6d5-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="3d6d5-580">236.25</span><span class="sxs-lookup"><span data-stu-id="3d6d5-580">236.25</span></span></td>
<td><span data-ttu-id="3d6d5-581">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-582">CC003</span><span class="sxs-lookup"><span data-stu-id="3d6d5-582">CC003</span></span></td>
<td><span data-ttu-id="3d6d5-583">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-583">Assembly</span></span></td>
<td><span data-ttu-id="3d6d5-584">65</span><span class="sxs-lookup"><span data-stu-id="3d6d5-584">65</span></span></td>
<td><span data-ttu-id="3d6d5-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="3d6d5-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="3d6d5-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="3d6d5-586">5,297.69</span></span></td>
<td><span data-ttu-id="3d6d5-587">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-588">CC004</span><span class="sxs-lookup"><span data-stu-id="3d6d5-588">CC004</span></span></td>
<td><span data-ttu-id="3d6d5-589">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-589">Packaging</span></span></td>
<td><span data-ttu-id="3d6d5-590">35</span><span class="sxs-lookup"><span data-stu-id="3d6d5-590">35</span></span></td>
<td><span data-ttu-id="3d6d5-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="3d6d5-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="3d6d5-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="3d6d5-592">2,852.60</span></span></td>
<td><span data-ttu-id="3d6d5-593">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3d6d5-594">La tabla siguiente muestra el resultado cuando se aplican los servicios de Asamblea como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="3d6d5-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3d6d5-595">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-595">Cost object</span></span></th>
<th><span data-ttu-id="3d6d5-596">Magnitud</span><span class="sxs-lookup"><span data-stu-id="3d6d5-596">Magnitude</span></span></th>
<th><span data-ttu-id="3d6d5-597">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="3d6d5-597">Allocation factor</span></span></th>
<th><span data-ttu-id="3d6d5-598">Importe</span><span class="sxs-lookup"><span data-stu-id="3d6d5-598">Amount</span></span></th>
<th><span data-ttu-id="3d6d5-599">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="3d6d5-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-600">Prod 1</span></span></td>
<td><span data-ttu-id="3d6d5-601">Producto 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-601">Product 1</span></span></td>
<td><span data-ttu-id="3d6d5-602">60</span><span class="sxs-lookup"><span data-stu-id="3d6d5-602">60</span></span></td>
<td><span data-ttu-id="3d6d5-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="3d6d5-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="3d6d5-604">535.31</span><span class="sxs-lookup"><span data-stu-id="3d6d5-604">535.31</span></span></td>
<td><span data-ttu-id="3d6d5-605">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-606">Prod 2</span></span></td>
<td><span data-ttu-id="3d6d5-607">Producto 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-607">Product 2</span></span></td>
<td><span data-ttu-id="3d6d5-608">20</span><span class="sxs-lookup"><span data-stu-id="3d6d5-608">20</span></span></td>
<td><span data-ttu-id="3d6d5-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="3d6d5-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="3d6d5-610">178.44</span><span class="sxs-lookup"><span data-stu-id="3d6d5-610">178.44</span></span></td>
<td><span data-ttu-id="3d6d5-611">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-612">Prod 1</span></span></td>
<td><span data-ttu-id="3d6d5-613">Producto 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-613">Product 1</span></span></td>
<td><span data-ttu-id="3d6d5-614">60</span><span class="sxs-lookup"><span data-stu-id="3d6d5-614">60</span></span></td>
<td><span data-ttu-id="3d6d5-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="3d6d5-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="3d6d5-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="3d6d5-616">4,487.12</span></span></td>
<td><span data-ttu-id="3d6d5-617">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-618">Prod 2</span></span></td>
<td><span data-ttu-id="3d6d5-619">Producto 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-619">Product 2</span></span></td>
<td><span data-ttu-id="3d6d5-620">20</span><span class="sxs-lookup"><span data-stu-id="3d6d5-620">20</span></span></td>
<td><span data-ttu-id="3d6d5-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="3d6d5-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="3d6d5-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="3d6d5-622">1,495.71</span></span></td>
<td><span data-ttu-id="3d6d5-623">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3d6d5-624">La tabla siguiente muestra el resultado cuando se aplican los servicios de Embalaje como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="3d6d5-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3d6d5-625">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-625">Cost object</span></span></th>
<th><span data-ttu-id="3d6d5-626">Magnitud</span><span class="sxs-lookup"><span data-stu-id="3d6d5-626">Magnitude</span></span></th>
<th><span data-ttu-id="3d6d5-627">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="3d6d5-627">Allocation factor</span></span></th>
<th><span data-ttu-id="3d6d5-628">Importe</span><span class="sxs-lookup"><span data-stu-id="3d6d5-628">Amount</span></span></th>
<th><span data-ttu-id="3d6d5-629">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="3d6d5-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-630">Prod 1</span></span></td>
<td><span data-ttu-id="3d6d5-631">Producto 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-631">Product 1</span></span></td>
<td><span data-ttu-id="3d6d5-632">80</span><span class="sxs-lookup"><span data-stu-id="3d6d5-632">80</span></span></td>
<td><span data-ttu-id="3d6d5-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="3d6d5-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="3d6d5-634">241.05</span><span class="sxs-lookup"><span data-stu-id="3d6d5-634">241.05</span></span></td>
<td><span data-ttu-id="3d6d5-635">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-636">Prod 2</span></span></td>
<td><span data-ttu-id="3d6d5-637">Producto 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-637">Product 2</span></span></td>
<td><span data-ttu-id="3d6d5-638">15</span><span class="sxs-lookup"><span data-stu-id="3d6d5-638">15</span></span></td>
<td><span data-ttu-id="3d6d5-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="3d6d5-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="3d6d5-640">45.20</span><span class="sxs-lookup"><span data-stu-id="3d6d5-640">45.20</span></span></td>
<td><span data-ttu-id="3d6d5-641">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-642">Prod 1</span></span></td>
<td><span data-ttu-id="3d6d5-643">Producto 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-643">Product 1</span></span></td>
<td><span data-ttu-id="3d6d5-644">80</span><span class="sxs-lookup"><span data-stu-id="3d6d5-644">80</span></span></td>
<td><span data-ttu-id="3d6d5-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="3d6d5-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="3d6d5-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="3d6d5-646">2,507.09</span></span></td>
<td><span data-ttu-id="3d6d5-647">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-648">Prod 2</span></span></td>
<td><span data-ttu-id="3d6d5-649">Producto 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-649">Product 2</span></span></td>
<td><span data-ttu-id="3d6d5-650">15</span><span class="sxs-lookup"><span data-stu-id="3d6d5-650">15</span></span></td>
<td><span data-ttu-id="3d6d5-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="3d6d5-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="3d6d5-652">470.08</span><span class="sxs-lookup"><span data-stu-id="3d6d5-652">470.08</span></span></td>
<td><span data-ttu-id="3d6d5-653">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="3d6d5-654">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="3d6d5-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3d6d5-655">Diario</span><span class="sxs-lookup"><span data-stu-id="3d6d5-655">Journal</span></span></th>
<th><span data-ttu-id="3d6d5-656">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="3d6d5-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="3d6d5-657">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="3d6d5-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="3d6d5-658">Versión</span><span class="sxs-lookup"><span data-stu-id="3d6d5-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-659">00004</span><span class="sxs-lookup"><span data-stu-id="3d6d5-659">00004</span></span></td>
<td><span data-ttu-id="3d6d5-660">Diario de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="3d6d5-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="3d6d5-661">Fiscal</span><span class="sxs-lookup"><span data-stu-id="3d6d5-661">Fiscal</span></span></td>
<td><span data-ttu-id="3d6d5-662">2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-662">2017</span></span></td>
<td><span data-ttu-id="3d6d5-663">Período 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-663">Period 1</span></span></td>
<td><span data-ttu-id="3d6d5-664">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="3d6d5-665">Líneas de diario</span><span class="sxs-lookup"><span data-stu-id="3d6d5-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3d6d5-666">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="3d6d5-667">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="3d6d5-668">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-668">Cost element</span></span></th>
<th><span data-ttu-id="3d6d5-669">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="3d6d5-669">Cost behavior</span></span></th>
<th><span data-ttu-id="3d6d5-670">Importe</span><span class="sxs-lookup"><span data-stu-id="3d6d5-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-671">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="3d6d5-672">CC001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-672">CC001</span></span></td>
<td><span data-ttu-id="3d6d5-673">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-673">HR</span></span></td>
<td><span data-ttu-id="3d6d5-674">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-674">10001</span></span></td>
<td><span data-ttu-id="3d6d5-675">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-675">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-676">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-676">Fixed cost</span></span></td>
<td><span data-ttu-id="3d6d5-677">500,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-678">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="3d6d5-679">CC001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-679">CC001</span></span></td>
<td><span data-ttu-id="3d6d5-680">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-680">HR</span></span></td>
<td><span data-ttu-id="3d6d5-681">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-681">10001</span></span></td>
<td><span data-ttu-id="3d6d5-682">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-682">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-683">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-683">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="3d6d5-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-685">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="3d6d5-686">CC002</span><span class="sxs-lookup"><span data-stu-id="3d6d5-686">CC002</span></span></td>
<td><span data-ttu-id="3d6d5-687">Finanzas</span><span class="sxs-lookup"><span data-stu-id="3d6d5-687">Finance</span></span></td>
<td><span data-ttu-id="3d6d5-688">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-688">10001</span></span></td>
<td><span data-ttu-id="3d6d5-689">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-689">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-690">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-690">Fixed cost</span></span></td>
<td><span data-ttu-id="3d6d5-691">675.00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-692">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="3d6d5-693">CC002</span><span class="sxs-lookup"><span data-stu-id="3d6d5-693">CC002</span></span></td>
<td><span data-ttu-id="3d6d5-694">Finanzas</span><span class="sxs-lookup"><span data-stu-id="3d6d5-694">Finance</span></span></td>
<td><span data-ttu-id="3d6d5-695">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-695">10001</span></span></td>
<td><span data-ttu-id="3d6d5-696">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-696">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-697">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-697">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="3d6d5-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-699">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="3d6d5-700">CC003</span><span class="sxs-lookup"><span data-stu-id="3d6d5-700">CC003</span></span></td>
<td><span data-ttu-id="3d6d5-701">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-701">Assembly</span></span></td>
<td><span data-ttu-id="3d6d5-702">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-702">10001</span></span></td>
<td><span data-ttu-id="3d6d5-703">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-703">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-704">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-704">Fixed cost</span></span></td>
<td><span data-ttu-id="3d6d5-705">713.75</span><span class="sxs-lookup"><span data-stu-id="3d6d5-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-706">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="3d6d5-707">CC003</span><span class="sxs-lookup"><span data-stu-id="3d6d5-707">CC003</span></span></td>
<td><span data-ttu-id="3d6d5-708">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-708">Assembly</span></span></td>
<td><span data-ttu-id="3d6d5-709">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-709">10001</span></span></td>
<td><span data-ttu-id="3d6d5-710">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-710">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-711">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-711">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="3d6d5-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-713">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="3d6d5-714">CC003</span><span class="sxs-lookup"><span data-stu-id="3d6d5-714">CC003</span></span></td>
<td><span data-ttu-id="3d6d5-715">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-715">Packaging</span></span></td>
<td><span data-ttu-id="3d6d5-716">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-716">10001</span></span></td>
<td><span data-ttu-id="3d6d5-717">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-717">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-718">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-718">Fixed cost</span></span></td>
<td><span data-ttu-id="3d6d5-719">286.25</span><span class="sxs-lookup"><span data-stu-id="3d6d5-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-720">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="3d6d5-721">CC003</span><span class="sxs-lookup"><span data-stu-id="3d6d5-721">CC003</span></span></td>
<td><span data-ttu-id="3d6d5-722">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-722">Packaging</span></span></td>
<td><span data-ttu-id="3d6d5-723">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-723">10001</span></span></td>
<td><span data-ttu-id="3d6d5-724">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-724">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-725">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-725">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="3d6d5-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-727">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="3d6d5-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-728">Prod 1</span></span></td>
<td><span data-ttu-id="3d6d5-729">Producto 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-729">Product 1</span></span></td>
<td><span data-ttu-id="3d6d5-730">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-730">10001</span></span></td>
<td><span data-ttu-id="3d6d5-731">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-731">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-732">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-732">Fixed cost</span></span></td>
<td><span data-ttu-id="3d6d5-733">776.36</span><span class="sxs-lookup"><span data-stu-id="3d6d5-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-734">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="3d6d5-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-735">Prod 1</span></span></td>
<td><span data-ttu-id="3d6d5-736">Producto 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-736">Product 1</span></span></td>
<td><span data-ttu-id="3d6d5-737">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-737">10001</span></span></td>
<td><span data-ttu-id="3d6d5-738">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-738">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-739">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-739">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="3d6d5-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-741">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="3d6d5-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-742">Prod 2</span></span></td>
<td><span data-ttu-id="3d6d5-743">Producto 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-743">Product 1</span></span></td>
<td><span data-ttu-id="3d6d5-744">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-744">10001</span></span></td>
<td><span data-ttu-id="3d6d5-745">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-745">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-746">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-746">Fixed cost</span></span></td>
<td><span data-ttu-id="3d6d5-747">223.64</span><span class="sxs-lookup"><span data-stu-id="3d6d5-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-748">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="3d6d5-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-749">Prod 2</span></span></td>
<td><span data-ttu-id="3d6d5-750">Producto 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-750">Product 1</span></span></td>
<td><span data-ttu-id="3d6d5-751">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-751">10001</span></span></td>
<td><span data-ttu-id="3d6d5-752">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-752">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-753">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-753">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="3d6d5-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="3d6d5-755">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="3d6d5-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="3d6d5-756">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="3d6d5-757">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-757">Cost element</span></span></th>
<th><span data-ttu-id="3d6d5-758">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="3d6d5-758">Cost behavior</span></span></th>
<th><span data-ttu-id="3d6d5-759">Importe</span><span class="sxs-lookup"><span data-stu-id="3d6d5-759">Amount</span></span></th>
<th><span data-ttu-id="3d6d5-760">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3d6d5-761">CC001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-761">CC001</span></span></td>
<td><span data-ttu-id="3d6d5-762">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-762">HR</span></span></td>
<td><span data-ttu-id="3d6d5-763">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-763">10001</span></span></td>
<td><span data-ttu-id="3d6d5-764">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-764">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-765">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-765">Fixed cost</span></span></td>
<td><span data-ttu-id="3d6d5-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-766">-500.00</span></span></td>
<td><span data-ttu-id="3d6d5-767">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-768">CC002</span><span class="sxs-lookup"><span data-stu-id="3d6d5-768">CC002</span></span></td>
<td><span data-ttu-id="3d6d5-769">Finanzas</span><span class="sxs-lookup"><span data-stu-id="3d6d5-769">Finance</span></span></td>
<td><span data-ttu-id="3d6d5-770">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-770">10001</span></span></td>
<td><span data-ttu-id="3d6d5-771">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-771">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-772">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-772">Fixed cost</span></span></td>
<td><span data-ttu-id="3d6d5-773">175.00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-773">175.00</span></span></td>
<td><span data-ttu-id="3d6d5-774">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-775">CC003</span><span class="sxs-lookup"><span data-stu-id="3d6d5-775">CC003</span></span></td>
<td><span data-ttu-id="3d6d5-776">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-776">Assembly</span></span></td>
<td><span data-ttu-id="3d6d5-777">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-777">10001</span></span></td>
<td><span data-ttu-id="3d6d5-778">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-778">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-779">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-779">Fixed cost</span></span></td>
<td><span data-ttu-id="3d6d5-780">275.00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-780">275.00</span></span></td>
<td><span data-ttu-id="3d6d5-781">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-782">CC004</span><span class="sxs-lookup"><span data-stu-id="3d6d5-782">CC004</span></span></td>
<td><span data-ttu-id="3d6d5-783">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-783">Packaging</span></span></td>
<td><span data-ttu-id="3d6d5-784">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-784">10001</span></span></td>
<td><span data-ttu-id="3d6d5-785">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-785">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-786">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-786">Fixed cost</span></span></td>
<td><span data-ttu-id="3d6d5-787">50,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-787">50,00</span></span></td>
<td><span data-ttu-id="3d6d5-788">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-789">CC001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-789">CC001</span></span></td>
<td><span data-ttu-id="3d6d5-790">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-790">HR</span></span></td>
<td><span data-ttu-id="3d6d5-791">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-791">10001</span></span></td>
<td><span data-ttu-id="3d6d5-792">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-792">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-793">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-793">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="3d6d5-794">-1,245.71</span></span></td>
<td><span data-ttu-id="3d6d5-795">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-796">CC002</span><span class="sxs-lookup"><span data-stu-id="3d6d5-796">CC002</span></span></td>
<td><span data-ttu-id="3d6d5-797">Finanzas</span><span class="sxs-lookup"><span data-stu-id="3d6d5-797">Finance</span></span></td>
<td><span data-ttu-id="3d6d5-798">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-798">10001</span></span></td>
<td><span data-ttu-id="3d6d5-799">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-799">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-800">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-800">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-801">436.00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-801">436.00</span></span></td>
<td><span data-ttu-id="3d6d5-802">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-803">CC003</span><span class="sxs-lookup"><span data-stu-id="3d6d5-803">CC003</span></span></td>
<td><span data-ttu-id="3d6d5-804">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-804">Assembly</span></span></td>
<td><span data-ttu-id="3d6d5-805">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-805">10001</span></span></td>
<td><span data-ttu-id="3d6d5-806">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-806">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-807">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-807">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-808">685.14</span><span class="sxs-lookup"><span data-stu-id="3d6d5-808">685.14</span></span></td>
<td><span data-ttu-id="3d6d5-809">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-810">CC004</span><span class="sxs-lookup"><span data-stu-id="3d6d5-810">CC004</span></span></td>
<td><span data-ttu-id="3d6d5-811">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-811">Packaging</span></span></td>
<td><span data-ttu-id="3d6d5-812">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-812">10001</span></span></td>
<td><span data-ttu-id="3d6d5-813">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-813">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-814">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-814">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-815">124.57</span><span class="sxs-lookup"><span data-stu-id="3d6d5-815">124.57</span></span></td>
<td><span data-ttu-id="3d6d5-816">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-817">CC002</span><span class="sxs-lookup"><span data-stu-id="3d6d5-817">CC002</span></span></td>
<td><span data-ttu-id="3d6d5-818">Finanzas</span><span class="sxs-lookup"><span data-stu-id="3d6d5-818">Finance</span></span></td>
<td><span data-ttu-id="3d6d5-819">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-819">10001</span></span></td>
<td><span data-ttu-id="3d6d5-820">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-820">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-821">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-821">Fixed cost</span></span></td>
<td><span data-ttu-id="3d6d5-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-822">-675.00</span></span></td>
<td><span data-ttu-id="3d6d5-823">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-824">CC003</span><span class="sxs-lookup"><span data-stu-id="3d6d5-824">CC003</span></span></td>
<td><span data-ttu-id="3d6d5-825">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-825">Assembly</span></span></td>
<td><span data-ttu-id="3d6d5-826">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-826">10001</span></span></td>
<td><span data-ttu-id="3d6d5-827">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-827">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-828">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-828">Fixed cost</span></span></td>
<td><span data-ttu-id="3d6d5-829">438.75</span><span class="sxs-lookup"><span data-stu-id="3d6d5-829">438.75</span></span></td>
<td><span data-ttu-id="3d6d5-830">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-831">CC004</span><span class="sxs-lookup"><span data-stu-id="3d6d5-831">CC004</span></span></td>
<td><span data-ttu-id="3d6d5-832">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-832">Packaging</span></span></td>
<td><span data-ttu-id="3d6d5-833">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-833">10001</span></span></td>
<td><span data-ttu-id="3d6d5-834">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-834">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-835">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-835">Fixed cost</span></span></td>
<td><span data-ttu-id="3d6d5-836">236.25</span><span class="sxs-lookup"><span data-stu-id="3d6d5-836">236.25</span></span></td>
<td><span data-ttu-id="3d6d5-837">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-838">CC002</span><span class="sxs-lookup"><span data-stu-id="3d6d5-838">CC002</span></span></td>
<td><span data-ttu-id="3d6d5-839">Finanzas</span><span class="sxs-lookup"><span data-stu-id="3d6d5-839">Finance</span></span></td>
<td><span data-ttu-id="3d6d5-840">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-840">10001</span></span></td>
<td><span data-ttu-id="3d6d5-841">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-841">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-842">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-842">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="3d6d5-843">-8,150.29</span></span></td>
<td><span data-ttu-id="3d6d5-844">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-845">CC003</span><span class="sxs-lookup"><span data-stu-id="3d6d5-845">CC003</span></span></td>
<td><span data-ttu-id="3d6d5-846">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-846">Assembly</span></span></td>
<td><span data-ttu-id="3d6d5-847">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-847">10001</span></span></td>
<td><span data-ttu-id="3d6d5-848">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-848">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-849">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-849">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="3d6d5-850">5,297.69</span></span></td>
<td><span data-ttu-id="3d6d5-851">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-852">CC004</span><span class="sxs-lookup"><span data-stu-id="3d6d5-852">CC004</span></span></td>
<td><span data-ttu-id="3d6d5-853">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-853">Packaging</span></span></td>
<td><span data-ttu-id="3d6d5-854">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-854">10001</span></span></td>
<td><span data-ttu-id="3d6d5-855">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-855">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-856">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-856">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="3d6d5-857">2,852.60</span></span></td>
<td><span data-ttu-id="3d6d5-858">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-859">CC003</span><span class="sxs-lookup"><span data-stu-id="3d6d5-859">CC003</span></span></td>
<td><span data-ttu-id="3d6d5-860">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-860">Assembly</span></span></td>
<td><span data-ttu-id="3d6d5-861">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-861">10001</span></span></td>
<td><span data-ttu-id="3d6d5-862">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-862">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-863">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-863">Fixed cost</span></span></td>
<td><span data-ttu-id="3d6d5-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="3d6d5-864">-713.75</span></span></td>
<td><span data-ttu-id="3d6d5-865">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-866">Prod 1</span></span></td>
<td><span data-ttu-id="3d6d5-867">Producto 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-867">Product 1</span></span></td>
<td><span data-ttu-id="3d6d5-868">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-868">10001</span></span></td>
<td><span data-ttu-id="3d6d5-869">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-869">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-870">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-870">Fixed cost</span></span></td>
<td><span data-ttu-id="3d6d5-871">535.31</span><span class="sxs-lookup"><span data-stu-id="3d6d5-871">535.31</span></span></td>
<td><span data-ttu-id="3d6d5-872">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-873">Prod 2</span></span></td>
<td><span data-ttu-id="3d6d5-874">Producto 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-874">Product 2</span></span></td>
<td><span data-ttu-id="3d6d5-875">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-875">10001</span></span></td>
<td><span data-ttu-id="3d6d5-876">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-876">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-877">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-877">Fixed cost</span></span></td>
<td><span data-ttu-id="3d6d5-878">178.44</span><span class="sxs-lookup"><span data-stu-id="3d6d5-878">178.44</span></span></td>
<td><span data-ttu-id="3d6d5-879">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-880">CC003</span><span class="sxs-lookup"><span data-stu-id="3d6d5-880">CC003</span></span></td>
<td><span data-ttu-id="3d6d5-881">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-881">Assembly</span></span></td>
<td><span data-ttu-id="3d6d5-882">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-882">10001</span></span></td>
<td><span data-ttu-id="3d6d5-883">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-883">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-884">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-884">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="3d6d5-885">-5,982.83</span></span></td>
<td><span data-ttu-id="3d6d5-886">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-887">Prod 1</span></span></td>
<td><span data-ttu-id="3d6d5-888">Producto 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-888">Product 1</span></span></td>
<td><span data-ttu-id="3d6d5-889">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-889">10001</span></span></td>
<td><span data-ttu-id="3d6d5-890">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-890">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-891">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-891">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="3d6d5-892">4,487.12</span></span></td>
<td><span data-ttu-id="3d6d5-893">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-894">Prod 2</span></span></td>
<td><span data-ttu-id="3d6d5-895">Producto 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-895">Product 2</span></span></td>
<td><span data-ttu-id="3d6d5-896">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-896">10001</span></span></td>
<td><span data-ttu-id="3d6d5-897">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-897">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-898">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-898">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="3d6d5-899">1,495.71</span></span></td>
<td><span data-ttu-id="3d6d5-900">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-901">CC003</span><span class="sxs-lookup"><span data-stu-id="3d6d5-901">CC003</span></span></td>
<td><span data-ttu-id="3d6d5-902">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-902">Assembly</span></span></td>
<td><span data-ttu-id="3d6d5-903">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-903">10001</span></span></td>
<td><span data-ttu-id="3d6d5-904">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-904">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-905">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-905">Fixed cost</span></span></td>
<td><span data-ttu-id="3d6d5-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="3d6d5-906">-286.25</span></span></td>
<td><span data-ttu-id="3d6d5-907">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-908">Prod 1</span></span></td>
<td><span data-ttu-id="3d6d5-909">Producto 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-909">Product 1</span></span></td>
<td><span data-ttu-id="3d6d5-910">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-910">10001</span></span></td>
<td><span data-ttu-id="3d6d5-911">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-911">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-912">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-912">Fixed cost</span></span></td>
<td><span data-ttu-id="3d6d5-913">241.05</span><span class="sxs-lookup"><span data-stu-id="3d6d5-913">241.05</span></span></td>
<td><span data-ttu-id="3d6d5-914">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-915">Prod 2</span></span></td>
<td><span data-ttu-id="3d6d5-916">Producto 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-916">Product 2</span></span></td>
<td><span data-ttu-id="3d6d5-917">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-917">10001</span></span></td>
<td><span data-ttu-id="3d6d5-918">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-918">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-919">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-919">Fixed cost</span></span></td>
<td><span data-ttu-id="3d6d5-920">45.20</span><span class="sxs-lookup"><span data-stu-id="3d6d5-920">45.20</span></span></td>
<td><span data-ttu-id="3d6d5-921">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-922">CC003</span><span class="sxs-lookup"><span data-stu-id="3d6d5-922">CC003</span></span></td>
<td><span data-ttu-id="3d6d5-923">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d6d5-923">Assembly</span></span></td>
<td><span data-ttu-id="3d6d5-924">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-924">10001</span></span></td>
<td><span data-ttu-id="3d6d5-925">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-925">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-926">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-926">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="3d6d5-927">-2,977.17</span></span></td>
<td><span data-ttu-id="3d6d5-928">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-929">Prod 1</span></span></td>
<td><span data-ttu-id="3d6d5-930">Producto 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-930">Product 1</span></span></td>
<td><span data-ttu-id="3d6d5-931">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-931">10001</span></span></td>
<td><span data-ttu-id="3d6d5-932">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-932">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-933">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-933">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="3d6d5-934">2,507.09</span></span></td>
<td><span data-ttu-id="3d6d5-935">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3d6d5-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-936">Prod 2</span></span></td>
<td><span data-ttu-id="3d6d5-937">Producto 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-937">Product 2</span></span></td>
<td><span data-ttu-id="3d6d5-938">10001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-938">10001</span></span></td>
<td><span data-ttu-id="3d6d5-939">Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-939">Electricity</span></span></td>
<td><span data-ttu-id="3d6d5-940">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-940">Variable cost</span></span></td>
<td><span data-ttu-id="3d6d5-941">470.08</span><span class="sxs-lookup"><span data-stu-id="3d6d5-941">470.08</span></span></td>
<td><span data-ttu-id="3d6d5-942">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="3d6d5-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="3d6d5-943">Conclusión</span><span class="sxs-lookup"><span data-stu-id="3d6d5-943">Conclusion</span></span>
<span data-ttu-id="3d6d5-944">En la contabilidad financiera, un coste de 10.000,00 para electricidad se envía a un identificador ficticio de centro de coste.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="3d6d5-945">Por lo tanto, los contables de coste sabrán que este coste se debe asignar.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="3d6d5-946">En contabilidad de costes, los costes fluyen en las unidades organizativas y los niveles en función de las directivas y las reglas que se aplican.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="3d6d5-947">Cada coste se ha asociado con una base de asignación que proporciona la mejor evaluación para la asignación de costes.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="3d6d5-948">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="3d6d5-949">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="3d6d5-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="3d6d5-950">Total</span><span class="sxs-lookup"><span data-stu-id="3d6d5-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="3d6d5-951">CC099</span><span class="sxs-lookup"><span data-stu-id="3d6d5-951">CC099</span></span></th>
<th><span data-ttu-id="3d6d5-952">CC001</span><span class="sxs-lookup"><span data-stu-id="3d6d5-952">CC001</span></span></th>
<th><span data-ttu-id="3d6d5-953">CC002</span><span class="sxs-lookup"><span data-stu-id="3d6d5-953">CC002</span></span></th>
<th><span data-ttu-id="3d6d5-954">CC003</span><span class="sxs-lookup"><span data-stu-id="3d6d5-954">CC003</span></span></th>
<th><span data-ttu-id="3d6d5-955">CC004</span><span class="sxs-lookup"><span data-stu-id="3d6d5-955">CC004</span></span></th>
<th><span data-ttu-id="3d6d5-956">Proy 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-956">Proj 1</span></span></th>
<th><span data-ttu-id="3d6d5-957">Proy 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-957">Proj 2</span></span></th>
<th><span data-ttu-id="3d6d5-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="3d6d5-958">Prod 1</span></span></th>
<th><span data-ttu-id="3d6d5-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="3d6d5-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="3d6d5-960">10001 Electricidad</span><span class="sxs-lookup"><span data-stu-id="3d6d5-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="3d6d5-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="3d6d5-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="3d6d5-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="3d6d5-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="3d6d5-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="3d6d5-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="3d6d5-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="3d6d5-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="3d6d5-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="3d6d5-970">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="3d6d5-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-971">0,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="3d6d5-972">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="3d6d5-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-973">0,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-974">0,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-975">0,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-976">0,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-977">0,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-978">776.36</span><span class="sxs-lookup"><span data-stu-id="3d6d5-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-979">223.64</span><span class="sxs-lookup"><span data-stu-id="3d6d5-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="3d6d5-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="3d6d5-981">Coste variable</span><span class="sxs-lookup"><span data-stu-id="3d6d5-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-982">000</span><span class="sxs-lookup"><span data-stu-id="3d6d5-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-983">0,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-984">0,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-985">0,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-986">0,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-987">30,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-988">10,00</span><span class="sxs-lookup"><span data-stu-id="3d6d5-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="3d6d5-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="3d6d5-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="3d6d5-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="3d6d5-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="3d6d5-992">Este tema muestra cómo un artículo de costes principales, 10001 Electricidad, fluye por los objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="3d6d5-993">Por tanto, estos gastos generales se asignan al nivel más bajo de la organización.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="3d6d5-994">Es decir, los objetos de coste del nivel más bajo son los que soportan el coste.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="3d6d5-995">Si necesita un flujo visual del coste entre los objetos de coste, puede usar las reglas de directivas de acumulación de costes para visualizar el flujo del coste.</span><span class="sxs-lookup"><span data-stu-id="3d6d5-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="3d6d5-996">Para obtener más información, consulte [Directiva de acumulación de costes y cálculo de costes generales](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="3d6d5-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



