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
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 954e0669c3d24bcc20fe667c22b7dcc367aba1e7
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770813"
---
# <a name="overhead-calculation"></a><span data-ttu-id="1b358-103">Cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="1b358-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1b358-104">Este tema describe los procesos típicos para calcular y asignar costes generales.</span><span class="sxs-lookup"><span data-stu-id="1b358-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="1b358-105">Definición del término</span><span class="sxs-lookup"><span data-stu-id="1b358-105">Term definition</span></span>
---------------

<span data-ttu-id="1b358-106">Los costes generales son costes que se contraen para dirigir un negocio, pero que no pueden ser atribuidos directamente a ninguna actividad empresarial, productos, o servicio específicos.</span><span class="sxs-lookup"><span data-stu-id="1b358-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="1b358-107">Los costes generales proporcionan un soporte fundamental a la generación de actividades rentables.</span><span class="sxs-lookup"><span data-stu-id="1b358-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="1b358-108">Algunos ejemplos de costes generales son:</span><span class="sxs-lookup"><span data-stu-id="1b358-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="1b358-109">Alquiler</span><span class="sxs-lookup"><span data-stu-id="1b358-109">Rent</span></span>
-   <span data-ttu-id="1b358-110">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-110">Electricity</span></span>
-   <span data-ttu-id="1b358-111">Sueldos administrativos</span><span class="sxs-lookup"><span data-stu-id="1b358-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="1b358-112">Visión general del cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="1b358-112">Overhead calculation overview</span></span>
<span data-ttu-id="1b358-113">El cálculo de costes generales ejecuta las directivas de contabilidad de costes en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="1b358-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="1b358-114">Puede calcular varias veces los costes generales del mismo período fiscal si se han cambiado las directivas de contabilidad de costes o se han detectado errores específicos.</span><span class="sxs-lookup"><span data-stu-id="1b358-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="1b358-115">Cada ejecución del cálculo de costes generales se almacena y recibe un identificador de versión único que permite comparar los cálculos de diferentes versiones.</span><span class="sxs-lookup"><span data-stu-id="1b358-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="1b358-116">Las entradas de costes que el cálculo de costes generales genera reciben una fecha de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="1b358-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="1b358-117">Esta fecha de contabilidad coincide con la fecha final del período fiscal que se usa en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="1b358-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="1b358-118">El identificador de versión único consiste en los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1b358-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="1b358-119">Tipo de versión</span><span class="sxs-lookup"><span data-stu-id="1b358-119">Version type</span></span>
-   <span data-ttu-id="1b358-120">Fecha y hora</span><span class="sxs-lookup"><span data-stu-id="1b358-120">Date and time</span></span>
-   <span data-ttu-id="1b358-121">Libro mayor de contabilidad de costes</span><span class="sxs-lookup"><span data-stu-id="1b358-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="1b358-122">Ejercicio</span><span class="sxs-lookup"><span data-stu-id="1b358-122">Fiscal year</span></span>
-   <span data-ttu-id="1b358-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="1b358-123">Fiscal period</span></span>

<span data-ttu-id="1b358-124">El cálculo de costes generales se ejecuta independientemente de la versión.</span><span class="sxs-lookup"><span data-stu-id="1b358-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="1b358-125">Por lo tanto, puede calcular la versión de presupuesto antes que la versión real.</span><span class="sxs-lookup"><span data-stu-id="1b358-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="1b358-126">El cálculo de costes generales consta de cuatro pasos, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="1b358-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="1b358-127">En cada paso, se crea una cabecera de diario que tiene entradas del diario.</span><span class="sxs-lookup"><span data-stu-id="1b358-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="1b358-128">Esta cabecera de diario guarda los datos de entrada para cada paso de cálculo.</span><span class="sxs-lookup"><span data-stu-id="1b358-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="1b358-129">Las directivas y las reglas se aplican a cada línea de diario, y las entradas de coste se generan como resultado.</span><span class="sxs-lookup"><span data-stu-id="1b358-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="1b358-130">Por tanto, siempre se tiene rastreabilidad completa.</span><span class="sxs-lookup"><span data-stu-id="1b358-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="1b358-131">[![Cálculo de costes generales](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="1b358-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="1b358-132">Calcular y asignar costes generales de electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="1b358-133">En la contabilidad financiera, algunos costes, como la electricidad, se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="1b358-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="1b358-134">Por lo tanto, no se proporciona una visión de gestión detallada para la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="1b358-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="1b358-135">En contabilidad de costes, para proporcionar información de gestión correcta en todas las unidades y niveles organizativos, los costes deben fluir por las unidades organizativas.</span><span class="sxs-lookup"><span data-stu-id="1b358-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="1b358-136">Este flujo se debe basar en cualquier registro preciso de consumo o en una evaluación justa.</span><span class="sxs-lookup"><span data-stu-id="1b358-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="1b358-137">En la contabilidad general, un coste de la electricidad se puede registrar como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="1b358-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1b358-138">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="1b358-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="1b358-139">Centro de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="1b358-140">Cuenta principal</span><span class="sxs-lookup"><span data-stu-id="1b358-140">Main account</span></span></th>
<th><span data-ttu-id="1b358-141">Importe en la divisa de contabilidad</span><span class="sxs-lookup"><span data-stu-id="1b358-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-142">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="1b358-143">CC099</span><span class="sxs-lookup"><span data-stu-id="1b358-143">CC099</span></span></td>
<td><span data-ttu-id="1b358-144">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="1b358-144">Default cost center</span></span></td>
<td><span data-ttu-id="1b358-145">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-145">10001</span></span></td>
<td><span data-ttu-id="1b358-146">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-146">Electricity</span></span></td>
<td><span data-ttu-id="1b358-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="1b358-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="1b358-148">Paso 1: Procese el cálculo del comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="1b358-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="1b358-149">De forma predeterminada, cuando las entradas de coste se importan de los datos de origen, reciben la clasificación de comportamiento del coste **Sin ordenar** en la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="1b358-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="1b358-150">Aplicando reglas de directivas de comportamiento de coste, puede reclasificar entradas de coste como **Coste fijo** o **Coste variable**.</span><span class="sxs-lookup"><span data-stu-id="1b358-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="1b358-151">Defina la regla de comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="1b358-151">Define the cost behavior rule</span></span>

<span data-ttu-id="1b358-152">En algunos casos, parte del coste es una cuota fija, y el coste pendiente se basa en el consumo.</span><span class="sxs-lookup"><span data-stu-id="1b358-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="1b358-153">Las facturas de electricidad coinciden a menudo con esta definición.</span><span class="sxs-lookup"><span data-stu-id="1b358-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="1b358-154">Tras pagar una cuota fija específica, paga el consumo por kilovatio-hora (Kwh).</span><span class="sxs-lookup"><span data-stu-id="1b358-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="1b358-155">Por ejemplo, si la cuota de coste fijo es de 1.000,00, la regla de comportamiento del coste se define como sigue:</span><span class="sxs-lookup"><span data-stu-id="1b358-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="1b358-156">Importe fijo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="1b358-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="1b358-157">0 &lt;= 1.000,00 = Fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="1b358-158">1.000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="1b358-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="1b358-159">Diario</span><span class="sxs-lookup"><span data-stu-id="1b358-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1b358-160">Diario</span><span class="sxs-lookup"><span data-stu-id="1b358-160">Journal</span></span></th>
<th><span data-ttu-id="1b358-161">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="1b358-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="1b358-162">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="1b358-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="1b358-163">Versión</span><span class="sxs-lookup"><span data-stu-id="1b358-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-164">00001</span><span class="sxs-lookup"><span data-stu-id="1b358-164">00001</span></span></td>
<td><span data-ttu-id="1b358-165">Diario de cálculo de comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="1b358-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="1b358-166">Fiscal</span><span class="sxs-lookup"><span data-stu-id="1b358-166">Fiscal</span></span></td>
<td><span data-ttu-id="1b358-167">2017</span><span class="sxs-lookup"><span data-stu-id="1b358-167">2017</span></span></td>
<td><span data-ttu-id="1b358-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="1b358-168">Period 1</span></span></td>
<td><span data-ttu-id="1b358-169">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="1b358-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="1b358-170">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="1b358-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1b358-171">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="1b358-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="1b358-172">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="1b358-173">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-173">Cost element</span></span></th>
<th><span data-ttu-id="1b358-174">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="1b358-174">Cost behavior</span></span></th>
<th><span data-ttu-id="1b358-175">Importe</span><span class="sxs-lookup"><span data-stu-id="1b358-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-176">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="1b358-177">CC099</span><span class="sxs-lookup"><span data-stu-id="1b358-177">CC099</span></span></td>
<td><span data-ttu-id="1b358-178">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="1b358-178">Default cost center</span></span></td>
<td><span data-ttu-id="1b358-179">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-179">10001</span></span></td>
<td><span data-ttu-id="1b358-180">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-180">Electricity</span></span></td>
<td><span data-ttu-id="1b358-181">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="1b358-181">Unclassified</span></span></td>
<td><span data-ttu-id="1b358-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="1b358-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="1b358-183">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="1b358-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1b358-184">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="1b358-185">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-185">Cost element</span></span></th>
<th><span data-ttu-id="1b358-186">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="1b358-186">Cost behavior</span></span></th>
<th><span data-ttu-id="1b358-187">Importe</span><span class="sxs-lookup"><span data-stu-id="1b358-187">Amount</span></span></th>
<th><span data-ttu-id="1b358-188">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="1b358-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-189">CC099</span><span class="sxs-lookup"><span data-stu-id="1b358-189">CC099</span></span></td>
<td><span data-ttu-id="1b358-190">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="1b358-190">Default cost center</span></span></td>
<td><span data-ttu-id="1b358-191">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-191">10001</span></span></td>
<td><span data-ttu-id="1b358-192">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-192">Electricity</span></span></td>
<td><span data-ttu-id="1b358-193">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="1b358-193">Unclassified</span></span></td>
<td><span data-ttu-id="1b358-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="1b358-194">10,000.00</span></span></td>
<td><span data-ttu-id="1b358-195">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-196">CC099</span><span class="sxs-lookup"><span data-stu-id="1b358-196">CC099</span></span></td>
<td><span data-ttu-id="1b358-197">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="1b358-197">Default cost center</span></span></td>
<td><span data-ttu-id="1b358-198">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-198">10001</span></span></td>
<td><span data-ttu-id="1b358-199">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-199">Electricity</span></span></td>
<td><span data-ttu-id="1b358-200">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="1b358-200">Unclassified</span></span></td>
<td><span data-ttu-id="1b358-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="1b358-201">-10,000.00</span></span></td>
<td><span data-ttu-id="1b358-202">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-203">CC099</span><span class="sxs-lookup"><span data-stu-id="1b358-203">CC099</span></span></td>
<td><span data-ttu-id="1b358-204">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="1b358-204">Default cost center</span></span></td>
<td><span data-ttu-id="1b358-205">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-205">10001</span></span></td>
<td><span data-ttu-id="1b358-206">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-206">Electricity</span></span></td>
<td><span data-ttu-id="1b358-207">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-207">Fixed cost</span></span></td>
<td><span data-ttu-id="1b358-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="1b358-208">1,000.00</span></span></td>
<td><span data-ttu-id="1b358-209">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-210">CC099</span><span class="sxs-lookup"><span data-stu-id="1b358-210">CC099</span></span></td>
<td><span data-ttu-id="1b358-211">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="1b358-211">Default cost center</span></span></td>
<td><span data-ttu-id="1b358-212">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-212">10001</span></span></td>
<td><span data-ttu-id="1b358-213">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-213">Electricity</span></span></td>
<td><span data-ttu-id="1b358-214">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-214">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="1b358-215">9,000.00</span></span></td>
<td><span data-ttu-id="1b358-216">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1b358-217">Para obtener más información, consulte [Crear y asignar una directiva de comportamiento de costes a una unidad de control de costes](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="1b358-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="1b358-218">Paso 2: Procese el cálculo de distribución de costes</span><span class="sxs-lookup"><span data-stu-id="1b358-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="1b358-219">La distribución de costes se usa para redistribuir costes desde un objeto de coste a uno o más objetos de coste aplicando una base relevante de la asignación.</span><span class="sxs-lookup"><span data-stu-id="1b358-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="1b358-220">La distribución de costes y la asignación de costes difieren en que la distribución de costes siempre se produce en el nivel de elemento de costes principal del coste original.</span><span class="sxs-lookup"><span data-stu-id="1b358-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="1b358-221">Defina la regla de distribución del coste</span><span class="sxs-lookup"><span data-stu-id="1b358-221">Define the cost distribution rule</span></span>

<span data-ttu-id="1b358-222">En la contabilidad financiera, los costes de electricidad se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="1b358-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="1b358-223">En contabilidad de costes, este método no es suficientemente detallado.</span><span class="sxs-lookup"><span data-stu-id="1b358-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="1b358-224">El coste variable debe distribuirse a los objetos individuales de coste aplicando una base justa.</span><span class="sxs-lookup"><span data-stu-id="1b358-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="1b358-225">La base de asignación más lógica es el consumo de electricidad (Kwh).</span><span class="sxs-lookup"><span data-stu-id="1b358-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="1b358-226">Se crea un miembro de dimensión estadística que se denomina Electricity, y se registra el consumo de electricidad.</span><span class="sxs-lookup"><span data-stu-id="1b358-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="1b358-227">De forma predeterminada, todos los miembros de dimensión estadísticos estarán disponibles como bases de asignación.</span><span class="sxs-lookup"><span data-stu-id="1b358-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1b358-228">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-228">Cost object</span></span></th>
<th><span data-ttu-id="1b358-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="1b358-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-230">CC001</span><span class="sxs-lookup"><span data-stu-id="1b358-230">CC001</span></span></td>
<td><span data-ttu-id="1b358-231">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="1b358-231">HR</span></span></td>
<td><span data-ttu-id="1b358-232">1.000</span><span class="sxs-lookup"><span data-stu-id="1b358-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-233">CC002</span><span class="sxs-lookup"><span data-stu-id="1b358-233">CC002</span></span></td>
<td><span data-ttu-id="1b358-234">Finanzas</span><span class="sxs-lookup"><span data-stu-id="1b358-234">Finance</span></span></td>
<td><span data-ttu-id="1b358-235">6.000</span><span class="sxs-lookup"><span data-stu-id="1b358-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-236">CC003</span><span class="sxs-lookup"><span data-stu-id="1b358-236">CC003</span></span></td>
<td><span data-ttu-id="1b358-237">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="1b358-237">Assembly</span></span></td>
<td><span data-ttu-id="1b358-238">0</span><span class="sxs-lookup"><span data-stu-id="1b358-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1b358-239">La tabla siguiente muestra el resultado cuando se aplica el consumo de electricidad como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="1b358-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1b358-240">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-240">Cost object</span></span></th>
<th><span data-ttu-id="1b358-241">Magnitud</span><span class="sxs-lookup"><span data-stu-id="1b358-241">Magnitude</span></span></th>
<th><span data-ttu-id="1b358-242">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="1b358-242">Allocation factor</span></span></th>
<th><span data-ttu-id="1b358-243">Importe</span><span class="sxs-lookup"><span data-stu-id="1b358-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-244">CC001</span><span class="sxs-lookup"><span data-stu-id="1b358-244">CC001</span></span></td>
<td><span data-ttu-id="1b358-245">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="1b358-245">HR</span></span></td>
<td><span data-ttu-id="1b358-246">1.000</span><span class="sxs-lookup"><span data-stu-id="1b358-246">1,000</span></span></td>
<td><span data-ttu-id="1b358-247">(1.000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="1b358-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="1b358-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="1b358-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-249">CC002</span><span class="sxs-lookup"><span data-stu-id="1b358-249">CC002</span></span></td>
<td><span data-ttu-id="1b358-250">Finanzas</span><span class="sxs-lookup"><span data-stu-id="1b358-250">Finance</span></span></td>
<td><span data-ttu-id="1b358-251">6.000</span><span class="sxs-lookup"><span data-stu-id="1b358-251">6,000</span></span></td>
<td><span data-ttu-id="1b358-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="1b358-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="1b358-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="1b358-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-254">CC003</span><span class="sxs-lookup"><span data-stu-id="1b358-254">CC003</span></span></td>
<td><span data-ttu-id="1b358-255">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="1b358-255">Assembly</span></span></td>
<td><span data-ttu-id="1b358-256">0</span><span class="sxs-lookup"><span data-stu-id="1b358-256">0</span></span></td>
<td><span data-ttu-id="1b358-257">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="1b358-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="1b358-258">0,00</span><span class="sxs-lookup"><span data-stu-id="1b358-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1b358-259">El coste fijo debe distribuirse uniformemente a los objetos individuales de costes que han consumido electricidad.</span><span class="sxs-lookup"><span data-stu-id="1b358-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="1b358-260">Puede obtener este resultado usando el miembro de dimensión estadístico de electricidad en una base de asignación de la fórmula: (Electricidad &gt; 0,00) La tabla siguiente muestra el resultado cuando el consumo de electricidad se aplica como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="1b358-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1b358-261">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-261">Cost object</span></span></th>
<th><span data-ttu-id="1b358-262">Fórmula</span><span class="sxs-lookup"><span data-stu-id="1b358-262">Formula</span></span></th>
<th><span data-ttu-id="1b358-263">Magnitud</span><span class="sxs-lookup"><span data-stu-id="1b358-263">Magnitude</span></span></th>
<th><span data-ttu-id="1b358-264">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="1b358-264">Allocation factor</span></span></th>
<th><span data-ttu-id="1b358-265">Importe</span><span class="sxs-lookup"><span data-stu-id="1b358-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-266">CC001</span><span class="sxs-lookup"><span data-stu-id="1b358-266">CC001</span></span></td>
<td><span data-ttu-id="1b358-267">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="1b358-267">HR</span></span></td>
<td><span data-ttu-id="1b358-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="1b358-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="1b358-269">1</span><span class="sxs-lookup"><span data-stu-id="1b358-269">1</span></span></td>
<td><span data-ttu-id="1b358-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="1b358-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="1b358-271">500,00</span><span class="sxs-lookup"><span data-stu-id="1b358-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-272">CC002</span><span class="sxs-lookup"><span data-stu-id="1b358-272">CC002</span></span></td>
<td><span data-ttu-id="1b358-273">Finanzas</span><span class="sxs-lookup"><span data-stu-id="1b358-273">Finance</span></span></td>
<td><span data-ttu-id="1b358-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="1b358-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="1b358-275">1</span><span class="sxs-lookup"><span data-stu-id="1b358-275">1</span></span></td>
<td><span data-ttu-id="1b358-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="1b358-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="1b358-277">500,00</span><span class="sxs-lookup"><span data-stu-id="1b358-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-278">CC003</span><span class="sxs-lookup"><span data-stu-id="1b358-278">CC003</span></span></td>
<td><span data-ttu-id="1b358-279">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="1b358-279">Assembly</span></span></td>
<td><span data-ttu-id="1b358-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="1b358-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="1b358-281">0</span><span class="sxs-lookup"><span data-stu-id="1b358-281">0</span></span></td>
<td><span data-ttu-id="1b358-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="1b358-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="1b358-283">0,00</span><span class="sxs-lookup"><span data-stu-id="1b358-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="1b358-284">Diario</span><span class="sxs-lookup"><span data-stu-id="1b358-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1b358-285">Diario</span><span class="sxs-lookup"><span data-stu-id="1b358-285">Journal</span></span></th>
<th><span data-ttu-id="1b358-286">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="1b358-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="1b358-287">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="1b358-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="1b358-288">Versión</span><span class="sxs-lookup"><span data-stu-id="1b358-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-289">00002</span><span class="sxs-lookup"><span data-stu-id="1b358-289">00002</span></span></td>
<td><span data-ttu-id="1b358-290">Diario de cálculo de la distribución de costes</span><span class="sxs-lookup"><span data-stu-id="1b358-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="1b358-291">Fiscal</span><span class="sxs-lookup"><span data-stu-id="1b358-291">Fiscal</span></span></td>
<td><span data-ttu-id="1b358-292">2017</span><span class="sxs-lookup"><span data-stu-id="1b358-292">2017</span></span></td>
<td><span data-ttu-id="1b358-293">Período 1</span><span class="sxs-lookup"><span data-stu-id="1b358-293">Period 1</span></span></td>
<td><span data-ttu-id="1b358-294">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="1b358-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="1b358-295">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="1b358-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1b358-296">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="1b358-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="1b358-297">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="1b358-298">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-298">Cost element</span></span></th>
<th><span data-ttu-id="1b358-299">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="1b358-299">Cost behavior</span></span></th>
<th><span data-ttu-id="1b358-300">Importe</span><span class="sxs-lookup"><span data-stu-id="1b358-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-301">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="1b358-302">CC099</span><span class="sxs-lookup"><span data-stu-id="1b358-302">CC099</span></span></td>
<td><span data-ttu-id="1b358-303">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="1b358-303">Default cost center</span></span></td>
<td><span data-ttu-id="1b358-304">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-304">10001</span></span></td>
<td><span data-ttu-id="1b358-305">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-305">Electricity</span></span></td>
<td><span data-ttu-id="1b358-306">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-306">Fixed cost</span></span></td>
<td><span data-ttu-id="1b358-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="1b358-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-308">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="1b358-309">CC099</span><span class="sxs-lookup"><span data-stu-id="1b358-309">CC099</span></span></td>
<td><span data-ttu-id="1b358-310">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="1b358-310">Default cost center</span></span></td>
<td><span data-ttu-id="1b358-311">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-311">10001</span></span></td>
<td><span data-ttu-id="1b358-312">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-312">Electricity</span></span></td>
<td><span data-ttu-id="1b358-313">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-313">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-314">9.000,00</span><span class="sxs-lookup"><span data-stu-id="1b358-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="1b358-315">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="1b358-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1b358-316">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="1b358-317">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-317">Cost element</span></span></th>
<th><span data-ttu-id="1b358-318">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="1b358-318">Cost behavior</span></span></th>
<th><span data-ttu-id="1b358-319">Importe</span><span class="sxs-lookup"><span data-stu-id="1b358-319">Amount</span></span></th>
<th><span data-ttu-id="1b358-320">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="1b358-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-321">CC099</span><span class="sxs-lookup"><span data-stu-id="1b358-321">CC099</span></span></td>
<td><span data-ttu-id="1b358-322">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="1b358-322">Default cost center</span></span></td>
<td><span data-ttu-id="1b358-323">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-323">10001</span></span></td>
<td><span data-ttu-id="1b358-324">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-324">Electricity</span></span></td>
<td><span data-ttu-id="1b358-325">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-325">Fixed cost</span></span></td>
<td><span data-ttu-id="1b358-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="1b358-326">-1,000.00</span></span></td>
<td><span data-ttu-id="1b358-327">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-328">CC001</span><span class="sxs-lookup"><span data-stu-id="1b358-328">CC001</span></span></td>
<td><span data-ttu-id="1b358-329">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="1b358-329">HR</span></span></td>
<td><span data-ttu-id="1b358-330">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-330">10001</span></span></td>
<td><span data-ttu-id="1b358-331">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-331">Electricity</span></span></td>
<td><span data-ttu-id="1b358-332">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-332">Fixed cost</span></span></td>
<td><span data-ttu-id="1b358-333">500,00</span><span class="sxs-lookup"><span data-stu-id="1b358-333">500.00</span></span></td>
<td><span data-ttu-id="1b358-334">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-335">CC002</span><span class="sxs-lookup"><span data-stu-id="1b358-335">CC002</span></span></td>
<td><span data-ttu-id="1b358-336">Finanzas</span><span class="sxs-lookup"><span data-stu-id="1b358-336">Finance</span></span></td>
<td><span data-ttu-id="1b358-337">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-337">10001</span></span></td>
<td><span data-ttu-id="1b358-338">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-338">Electricity</span></span></td>
<td><span data-ttu-id="1b358-339">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-339">Fixed cost</span></span></td>
<td><span data-ttu-id="1b358-340">500,00</span><span class="sxs-lookup"><span data-stu-id="1b358-340">500.00</span></span></td>
<td><span data-ttu-id="1b358-341">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-342">CC099</span><span class="sxs-lookup"><span data-stu-id="1b358-342">CC099</span></span></td>
<td><span data-ttu-id="1b358-343">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="1b358-343">Default cost center</span></span></td>
<td><span data-ttu-id="1b358-344">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-344">10001</span></span></td>
<td><span data-ttu-id="1b358-345">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-345">Electricity</span></span></td>
<td><span data-ttu-id="1b358-346">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-346">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="1b358-347">-9,000.00</span></span></td>
<td><span data-ttu-id="1b358-348">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-349">CC001</span><span class="sxs-lookup"><span data-stu-id="1b358-349">CC001</span></span></td>
<td><span data-ttu-id="1b358-350">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="1b358-350">HR</span></span></td>
<td><span data-ttu-id="1b358-351">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-351">10001</span></span></td>
<td><span data-ttu-id="1b358-352">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-352">Electricity</span></span></td>
<td><span data-ttu-id="1b358-353">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-353">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="1b358-354">1,285.71</span></span></td>
<td><span data-ttu-id="1b358-355">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-356">CC002</span><span class="sxs-lookup"><span data-stu-id="1b358-356">CC002</span></span></td>
<td><span data-ttu-id="1b358-357">Finanzas</span><span class="sxs-lookup"><span data-stu-id="1b358-357">Finance</span></span></td>
<td><span data-ttu-id="1b358-358">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-358">10001</span></span></td>
<td><span data-ttu-id="1b358-359">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-359">Electricity</span></span></td>
<td><span data-ttu-id="1b358-360">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-360">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="1b358-361">7,714.29</span></span></td>
<td><span data-ttu-id="1b358-362">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1b358-363">Para obtener más información, consulte [Crear y asignar una directiva de distribución de costes a una unidad de control de costes](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="1b358-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="1b358-364">Paso 3: Procese el cálculo de las tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="1b358-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="1b358-365">La tasa de costes generales se usa para cargar uno o varios objetos de coste específicos.</span><span class="sxs-lookup"><span data-stu-id="1b358-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="1b358-366">El cargo se basa en un índice de coste predeterminado y la magnitud de la base de asignación asignada.</span><span class="sxs-lookup"><span data-stu-id="1b358-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="1b358-367">Defina la tasa de costes generales</span><span class="sxs-lookup"><span data-stu-id="1b358-367">Define the overhead rate</span></span>

<span data-ttu-id="1b358-368">El objeto de coste CC001 HR contribuye a un conjunto de proyectos internos.</span><span class="sxs-lookup"><span data-stu-id="1b358-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="1b358-369">Se crea un miembro de dimensión estadística que se denomina proyectos HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="1b358-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1b358-370">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-370">Cost object</span></span></th>
<th><span data-ttu-id="1b358-371">Horas</span><span class="sxs-lookup"><span data-stu-id="1b358-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-372">Proy 1</span><span class="sxs-lookup"><span data-stu-id="1b358-372">Proj 1</span></span></td>
<td><span data-ttu-id="1b358-373">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="1b358-373">Project 1</span></span></td>
<td><span data-ttu-id="1b358-374">3</span><span class="sxs-lookup"><span data-stu-id="1b358-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-375">Proy 2</span><span class="sxs-lookup"><span data-stu-id="1b358-375">Proj 2</span></span></td>
<td><span data-ttu-id="1b358-376">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="1b358-376">Project 2</span></span></td>
<td><span data-ttu-id="1b358-377">1</span><span class="sxs-lookup"><span data-stu-id="1b358-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1b358-378">Una tasa de coste predeterminada para la contribución de los proyectos de coste se ha definido.</span><span class="sxs-lookup"><span data-stu-id="1b358-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1b358-379">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-379">Cost object</span></span></th>
<th><span data-ttu-id="1b358-380">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-380">Cost element</span></span></th>
<th><span data-ttu-id="1b358-381">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="1b358-381">Cost behavior</span></span></th>
<th><span data-ttu-id="1b358-382">Unidades</span><span class="sxs-lookup"><span data-stu-id="1b358-382">Units</span></span></th>
<th><span data-ttu-id="1b358-383">Índice</span><span class="sxs-lookup"><span data-stu-id="1b358-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-384">CC001</span><span class="sxs-lookup"><span data-stu-id="1b358-384">CC001</span></span></td>
<td><span data-ttu-id="1b358-385">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="1b358-385">HR</span></span></td>
<td><span data-ttu-id="1b358-386">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-386">10001</span></span></td>
<td><span data-ttu-id="1b358-387">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-387">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-388">1</span><span class="sxs-lookup"><span data-stu-id="1b358-388">1</span></span></td>
<td><span data-ttu-id="1b358-389">10</span><span class="sxs-lookup"><span data-stu-id="1b358-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1b358-390">La tabla siguiente muestra el resultado cuando los proyectos HR se aplican como base de la asignación.</span><span class="sxs-lookup"><span data-stu-id="1b358-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1b358-391">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-391">Cost object</span></span></th>
<th><span data-ttu-id="1b358-392">Magnitud</span><span class="sxs-lookup"><span data-stu-id="1b358-392">Magnitude</span></span></th>
<th><span data-ttu-id="1b358-393">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-393">Cost element</span></span></th>
<th><span data-ttu-id="1b358-394">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="1b358-394">Allocation factor</span></span></th>
<th><span data-ttu-id="1b358-395">Importe</span><span class="sxs-lookup"><span data-stu-id="1b358-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-396">Proy 1</span><span class="sxs-lookup"><span data-stu-id="1b358-396">Proj 1</span></span></td>
<td><span data-ttu-id="1b358-397">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="1b358-397">Project 1</span></span></td>
<td><span data-ttu-id="1b358-398">3</span><span class="sxs-lookup"><span data-stu-id="1b358-398">3</span></span></td>
<td><span data-ttu-id="1b358-399">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-399">10001</span></span></td>
<td><span data-ttu-id="1b358-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="1b358-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="1b358-401">30,00</span><span class="sxs-lookup"><span data-stu-id="1b358-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-402">Proy 2</span><span class="sxs-lookup"><span data-stu-id="1b358-402">Proj 2</span></span></td>
<td><span data-ttu-id="1b358-403">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="1b358-403">Project 2</span></span></td>
<td><span data-ttu-id="1b358-404">1</span><span class="sxs-lookup"><span data-stu-id="1b358-404">1</span></span></td>
<td><span data-ttu-id="1b358-405">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-405">10001</span></span></td>
<td><span data-ttu-id="1b358-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="1b358-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="1b358-407">10,00</span><span class="sxs-lookup"><span data-stu-id="1b358-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="1b358-408">Diario</span><span class="sxs-lookup"><span data-stu-id="1b358-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1b358-409">Diario</span><span class="sxs-lookup"><span data-stu-id="1b358-409">Journal</span></span></th>
<th><span data-ttu-id="1b358-410">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="1b358-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="1b358-411">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="1b358-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="1b358-412">Versión</span><span class="sxs-lookup"><span data-stu-id="1b358-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-413">00003</span><span class="sxs-lookup"><span data-stu-id="1b358-413">00003</span></span></td>
<td><span data-ttu-id="1b358-414">Diario de cálculo de tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="1b358-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="1b358-415">Fiscal</span><span class="sxs-lookup"><span data-stu-id="1b358-415">Fiscal</span></span></td>
<td><span data-ttu-id="1b358-416">2017</span><span class="sxs-lookup"><span data-stu-id="1b358-416">2017</span></span></td>
<td><span data-ttu-id="1b358-417">Período 1</span><span class="sxs-lookup"><span data-stu-id="1b358-417">Period 1</span></span></td>
<td><span data-ttu-id="1b358-418">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="1b358-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="1b358-419">Entradas de diario (entradas de diario para cálculo de tasas de costes generales)</span><span class="sxs-lookup"><span data-stu-id="1b358-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1b358-420">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="1b358-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="1b358-421">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-421">Cost object</span></span></th>
<th><span data-ttu-id="1b358-422">Magnitud</span><span class="sxs-lookup"><span data-stu-id="1b358-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-423">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="1b358-424">Proy 1</span><span class="sxs-lookup"><span data-stu-id="1b358-424">Proj 1</span></span></td>
<td><span data-ttu-id="1b358-425">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="1b358-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="1b358-426">3,00</span><span class="sxs-lookup"><span data-stu-id="1b358-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-427">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="1b358-428">Proy 2</span><span class="sxs-lookup"><span data-stu-id="1b358-428">Proj 2</span></span></td>
<td><span data-ttu-id="1b358-429">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="1b358-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="1b358-430">1,00</span><span class="sxs-lookup"><span data-stu-id="1b358-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="1b358-431">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="1b358-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1b358-432">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="1b358-433">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-433">Cost element</span></span></th>
<th><span data-ttu-id="1b358-434">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="1b358-434">Cost behavior</span></span></th>
<th><span data-ttu-id="1b358-435">Importe</span><span class="sxs-lookup"><span data-stu-id="1b358-435">Amount</span></span></th>
<th><span data-ttu-id="1b358-436">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="1b358-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="1b358-437">CC0001</span></span></td>
<td><span data-ttu-id="1b358-438">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="1b358-438">HR</span></span></td>
<td><span data-ttu-id="1b358-439">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-439">10001</span></span></td>
<td><span data-ttu-id="1b358-440">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-440">Electricity</span></span></td>
<td><span data-ttu-id="1b358-441">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-441">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="1b358-442">-30.00</span></span></td>
<td><span data-ttu-id="1b358-443">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-444">Proy 1</span><span class="sxs-lookup"><span data-stu-id="1b358-444">Proj 1</span></span></td>
<td><span data-ttu-id="1b358-445">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="1b358-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="1b358-446">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-446">10001</span></span></td>
<td><span data-ttu-id="1b358-447">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-447">Electricity</span></span></td>
<td><span data-ttu-id="1b358-448">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-448">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-449">30,00</span><span class="sxs-lookup"><span data-stu-id="1b358-449">30.00</span></span></td>
<td><span data-ttu-id="1b358-450">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-451">CC001</span><span class="sxs-lookup"><span data-stu-id="1b358-451">CC001</span></span></td>
<td><span data-ttu-id="1b358-452">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="1b358-452">HR</span></span></td>
<td><span data-ttu-id="1b358-453">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-453">10001</span></span></td>
<td><span data-ttu-id="1b358-454">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-454">Electricity</span></span></td>
<td><span data-ttu-id="1b358-455">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-455">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="1b358-456">-10.00</span></span></td>
<td><span data-ttu-id="1b358-457">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-458">Proy 2</span><span class="sxs-lookup"><span data-stu-id="1b358-458">Proj 2</span></span></td>
<td><span data-ttu-id="1b358-459">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="1b358-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="1b358-460">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-460">10001</span></span></td>
<td><span data-ttu-id="1b358-461">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-461">Electricity</span></span></td>
<td><span data-ttu-id="1b358-462">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-462">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-463">10,00</span><span class="sxs-lookup"><span data-stu-id="1b358-463">10.00</span></span></td>
<td><span data-ttu-id="1b358-464">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1b358-465">Para obtener más información, consulte [Realizar cálculo de costes generales](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="1b358-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="1b358-466">Paso 4: Procese el cálculo de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="1b358-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="1b358-467">La asignación es utilizada para asignar el saldo de un objeto de coste a otros objetos de coste aplicando una base de asignación.</span><span class="sxs-lookup"><span data-stu-id="1b358-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="1b358-468">Finance admite el método de asignación recíproco.</span><span class="sxs-lookup"><span data-stu-id="1b358-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="1b358-469">En el método de asignación recíproco, se reconocen completamente los servicios mutuos que los objetos de coste auxiliar intercambian.</span><span class="sxs-lookup"><span data-stu-id="1b358-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="1b358-470">El sistema determina automáticamente el orden correcto para realizar las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="1b358-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="1b358-471">El saldo de un objeto de coste se asigna según una única base de asignación.</span><span class="sxs-lookup"><span data-stu-id="1b358-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="1b358-472">Las asignaciones entre dimensiones de objetos de coste y sus miembros respectivos se admiten.</span><span class="sxs-lookup"><span data-stu-id="1b358-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="1b358-473">El orden de asignación se controla por unidad de control de costes.</span><span class="sxs-lookup"><span data-stu-id="1b358-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="1b358-474">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="1b358-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="1b358-475">Defina la asignación de costes</span><span class="sxs-lookup"><span data-stu-id="1b358-475">Define the cost allocation</span></span>

<span data-ttu-id="1b358-476">A continuación se indica un ejemplo sencillo que explica cómo puede realizar el seguimiento del flujo de coste.</span><span class="sxs-lookup"><span data-stu-id="1b358-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="1b358-477">El objeto de coste CC001 HR contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="1b358-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="1b358-478">Se crea un miembro de dimensión estadística que se denomina servicios HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="1b358-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1b358-479">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-479">Cost object</span></span></th>
<th><span data-ttu-id="1b358-480">Servicios HR</span><span class="sxs-lookup"><span data-stu-id="1b358-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-481">CC002</span><span class="sxs-lookup"><span data-stu-id="1b358-481">CC002</span></span></td>
<td><span data-ttu-id="1b358-482">Finanzas</span><span class="sxs-lookup"><span data-stu-id="1b358-482">Finance</span></span></td>
<td><span data-ttu-id="1b358-483">35</span><span class="sxs-lookup"><span data-stu-id="1b358-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-484">CC003</span><span class="sxs-lookup"><span data-stu-id="1b358-484">CC003</span></span></td>
<td><span data-ttu-id="1b358-485">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="1b358-485">Assembly</span></span></td>
<td><span data-ttu-id="1b358-486">55</span><span class="sxs-lookup"><span data-stu-id="1b358-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-487">CC004</span><span class="sxs-lookup"><span data-stu-id="1b358-487">CC004</span></span></td>
<td><span data-ttu-id="1b358-488">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="1b358-488">Packaging</span></span></td>
<td><span data-ttu-id="1b358-489">10</span><span class="sxs-lookup"><span data-stu-id="1b358-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1b358-490">El objeto de coste CC002 Finanzas contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="1b358-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="1b358-491">Se crea un miembro de dimensión estadística que se denomina Finanzas para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="1b358-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1b358-492">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-492">Cost object</span></span></th>
<th><span data-ttu-id="1b358-493">Servicios financieros</span><span class="sxs-lookup"><span data-stu-id="1b358-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-494">CC003</span><span class="sxs-lookup"><span data-stu-id="1b358-494">CC003</span></span></td>
<td><span data-ttu-id="1b358-495">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="1b358-495">Assembly</span></span></td>
<td><span data-ttu-id="1b358-496">65</span><span class="sxs-lookup"><span data-stu-id="1b358-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-497">CC004</span><span class="sxs-lookup"><span data-stu-id="1b358-497">CC004</span></span></td>
<td><span data-ttu-id="1b358-498">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="1b358-498">Packaging</span></span></td>
<td><span data-ttu-id="1b358-499">35</span><span class="sxs-lookup"><span data-stu-id="1b358-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1b358-500">El objeto de coste CC003 Asamblea contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="1b358-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="1b358-501">Se crea un miembro de dimensión estadística que se denomina servicios de Asamblea para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="1b358-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1b358-502">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-502">Cost object</span></span></th>
<th><span data-ttu-id="1b358-503">Servicios de la asamblea (horas)</span><span class="sxs-lookup"><span data-stu-id="1b358-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1b358-504">Prod 1</span></span></td>
<td><span data-ttu-id="1b358-505">Producto 1</span><span class="sxs-lookup"><span data-stu-id="1b358-505">Product 1</span></span></td>
<td><span data-ttu-id="1b358-506">60</span><span class="sxs-lookup"><span data-stu-id="1b358-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1b358-507">Prod 2</span></span></td>
<td><span data-ttu-id="1b358-508">Producto 2</span><span class="sxs-lookup"><span data-stu-id="1b358-508">Product 2</span></span></td>
<td><span data-ttu-id="1b358-509">20</span><span class="sxs-lookup"><span data-stu-id="1b358-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1b358-510">El objeto de coste CC004 Embalaje contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="1b358-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="1b358-511">Se crea un miembro de dimensión estadística que se denomina servicios de Embalaje para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="1b358-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1b358-512">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-512">Cost object</span></span></th>
<th><span data-ttu-id="1b358-513">Servicios de embalaje (horas)</span><span class="sxs-lookup"><span data-stu-id="1b358-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1b358-514">Prod 1</span></span></td>
<td><span data-ttu-id="1b358-515">Producto 1</span><span class="sxs-lookup"><span data-stu-id="1b358-515">Product 1</span></span></td>
<td><span data-ttu-id="1b358-516">80</span><span class="sxs-lookup"><span data-stu-id="1b358-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1b358-517">Prod 2</span></span></td>
<td><span data-ttu-id="1b358-518">Producto 2</span><span class="sxs-lookup"><span data-stu-id="1b358-518">Product 2</span></span></td>
<td><span data-ttu-id="1b358-519">15</span><span class="sxs-lookup"><span data-stu-id="1b358-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="1b358-520">Las medidas estadísticas como las horas de la producción que un producto consume se pueden deducir de los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="1b358-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="1b358-521">Para obtener más información, vea [Plantilla de proveedor de medidas estadísticas](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="1b358-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="1b358-522">La tabla siguiente muestra el resultado cuando se aplican los servicios de HR como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="1b358-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1b358-523">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-523">Cost object</span></span></th>
<th><span data-ttu-id="1b358-524">Magnitud</span><span class="sxs-lookup"><span data-stu-id="1b358-524">Magnitude</span></span></th>
<th><span data-ttu-id="1b358-525">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="1b358-525">Allocation factor</span></span></th>
<th><span data-ttu-id="1b358-526">Importe</span><span class="sxs-lookup"><span data-stu-id="1b358-526">Amount</span></span></th>
<th><span data-ttu-id="1b358-527">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="1b358-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-528">CC002</span><span class="sxs-lookup"><span data-stu-id="1b358-528">CC002</span></span></td>
<td><span data-ttu-id="1b358-529">Finanzas</span><span class="sxs-lookup"><span data-stu-id="1b358-529">Finance</span></span></td>
<td><span data-ttu-id="1b358-530">35</span><span class="sxs-lookup"><span data-stu-id="1b358-530">35</span></span></td>
<td><span data-ttu-id="1b358-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="1b358-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="1b358-532">175.00</span><span class="sxs-lookup"><span data-stu-id="1b358-532">175.00</span></span></td>
<td><span data-ttu-id="1b358-533">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-534">CC003</span><span class="sxs-lookup"><span data-stu-id="1b358-534">CC003</span></span></td>
<td><span data-ttu-id="1b358-535">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="1b358-535">Assembly</span></span></td>
<td><span data-ttu-id="1b358-536">55</span><span class="sxs-lookup"><span data-stu-id="1b358-536">55</span></span></td>
<td><span data-ttu-id="1b358-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="1b358-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="1b358-538">275.00</span><span class="sxs-lookup"><span data-stu-id="1b358-538">275.00</span></span></td>
<td><span data-ttu-id="1b358-539">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-540">CC004</span><span class="sxs-lookup"><span data-stu-id="1b358-540">CC004</span></span></td>
<td><span data-ttu-id="1b358-541">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="1b358-541">Packaging</span></span></td>
<td><span data-ttu-id="1b358-542">10</span><span class="sxs-lookup"><span data-stu-id="1b358-542">10</span></span></td>
<td><span data-ttu-id="1b358-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="1b358-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="1b358-544">50,00</span><span class="sxs-lookup"><span data-stu-id="1b358-544">50.00</span></span></td>
<td><span data-ttu-id="1b358-545">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-546">CC002</span><span class="sxs-lookup"><span data-stu-id="1b358-546">CC002</span></span></td>
<td><span data-ttu-id="1b358-547">Finanzas</span><span class="sxs-lookup"><span data-stu-id="1b358-547">Finance</span></span></td>
<td><span data-ttu-id="1b358-548">35</span><span class="sxs-lookup"><span data-stu-id="1b358-548">35</span></span></td>
<td><span data-ttu-id="1b358-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="1b358-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="1b358-550">436.00</span><span class="sxs-lookup"><span data-stu-id="1b358-550">436.00</span></span></td>
<td><span data-ttu-id="1b358-551">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-552">CC003</span><span class="sxs-lookup"><span data-stu-id="1b358-552">CC003</span></span></td>
<td><span data-ttu-id="1b358-553">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="1b358-553">Assembly</span></span></td>
<td><span data-ttu-id="1b358-554">55</span><span class="sxs-lookup"><span data-stu-id="1b358-554">55</span></span></td>
<td><span data-ttu-id="1b358-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="1b358-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="1b358-556">685.14</span><span class="sxs-lookup"><span data-stu-id="1b358-556">685.14</span></span></td>
<td><span data-ttu-id="1b358-557">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-558">CC004</span><span class="sxs-lookup"><span data-stu-id="1b358-558">CC004</span></span></td>
<td><span data-ttu-id="1b358-559">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="1b358-559">Packaging</span></span></td>
<td><span data-ttu-id="1b358-560">10</span><span class="sxs-lookup"><span data-stu-id="1b358-560">10</span></span></td>
<td><span data-ttu-id="1b358-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="1b358-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="1b358-562">124.57</span><span class="sxs-lookup"><span data-stu-id="1b358-562">124.57</span></span></td>
<td><span data-ttu-id="1b358-563">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1b358-564">La tabla siguiente muestra el resultado cuando se aplican los servicios de Finanzas como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="1b358-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1b358-565">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-565">Cost object</span></span></th>
<th><span data-ttu-id="1b358-566">Magnitud</span><span class="sxs-lookup"><span data-stu-id="1b358-566">Magnitude</span></span></th>
<th><span data-ttu-id="1b358-567">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="1b358-567">Allocation factor</span></span></th>
<th><span data-ttu-id="1b358-568">Importe</span><span class="sxs-lookup"><span data-stu-id="1b358-568">Amount</span></span></th>
<th><span data-ttu-id="1b358-569">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="1b358-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-570">CC003</span><span class="sxs-lookup"><span data-stu-id="1b358-570">CC003</span></span></td>
<td><span data-ttu-id="1b358-571">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="1b358-571">Assembly</span></span></td>
<td><span data-ttu-id="1b358-572">65</span><span class="sxs-lookup"><span data-stu-id="1b358-572">65</span></span></td>
<td><span data-ttu-id="1b358-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="1b358-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="1b358-574">438.75</span><span class="sxs-lookup"><span data-stu-id="1b358-574">438.75</span></span></td>
<td><span data-ttu-id="1b358-575">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-576">CC004</span><span class="sxs-lookup"><span data-stu-id="1b358-576">CC004</span></span></td>
<td><span data-ttu-id="1b358-577">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="1b358-577">Packaging</span></span></td>
<td><span data-ttu-id="1b358-578">35</span><span class="sxs-lookup"><span data-stu-id="1b358-578">35</span></span></td>
<td><span data-ttu-id="1b358-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="1b358-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="1b358-580">236.25</span><span class="sxs-lookup"><span data-stu-id="1b358-580">236.25</span></span></td>
<td><span data-ttu-id="1b358-581">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-582">CC003</span><span class="sxs-lookup"><span data-stu-id="1b358-582">CC003</span></span></td>
<td><span data-ttu-id="1b358-583">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="1b358-583">Assembly</span></span></td>
<td><span data-ttu-id="1b358-584">65</span><span class="sxs-lookup"><span data-stu-id="1b358-584">65</span></span></td>
<td><span data-ttu-id="1b358-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="1b358-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="1b358-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="1b358-586">5,297.69</span></span></td>
<td><span data-ttu-id="1b358-587">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-588">CC004</span><span class="sxs-lookup"><span data-stu-id="1b358-588">CC004</span></span></td>
<td><span data-ttu-id="1b358-589">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="1b358-589">Packaging</span></span></td>
<td><span data-ttu-id="1b358-590">35</span><span class="sxs-lookup"><span data-stu-id="1b358-590">35</span></span></td>
<td><span data-ttu-id="1b358-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="1b358-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="1b358-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="1b358-592">2,852.60</span></span></td>
<td><span data-ttu-id="1b358-593">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1b358-594">La tabla siguiente muestra el resultado cuando se aplican los servicios de Asamblea como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="1b358-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1b358-595">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-595">Cost object</span></span></th>
<th><span data-ttu-id="1b358-596">Magnitud</span><span class="sxs-lookup"><span data-stu-id="1b358-596">Magnitude</span></span></th>
<th><span data-ttu-id="1b358-597">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="1b358-597">Allocation factor</span></span></th>
<th><span data-ttu-id="1b358-598">Importe</span><span class="sxs-lookup"><span data-stu-id="1b358-598">Amount</span></span></th>
<th><span data-ttu-id="1b358-599">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="1b358-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1b358-600">Prod 1</span></span></td>
<td><span data-ttu-id="1b358-601">Producto 1</span><span class="sxs-lookup"><span data-stu-id="1b358-601">Product 1</span></span></td>
<td><span data-ttu-id="1b358-602">60</span><span class="sxs-lookup"><span data-stu-id="1b358-602">60</span></span></td>
<td><span data-ttu-id="1b358-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="1b358-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="1b358-604">535.31</span><span class="sxs-lookup"><span data-stu-id="1b358-604">535.31</span></span></td>
<td><span data-ttu-id="1b358-605">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1b358-606">Prod 2</span></span></td>
<td><span data-ttu-id="1b358-607">Producto 2</span><span class="sxs-lookup"><span data-stu-id="1b358-607">Product 2</span></span></td>
<td><span data-ttu-id="1b358-608">20</span><span class="sxs-lookup"><span data-stu-id="1b358-608">20</span></span></td>
<td><span data-ttu-id="1b358-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="1b358-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="1b358-610">178.44</span><span class="sxs-lookup"><span data-stu-id="1b358-610">178.44</span></span></td>
<td><span data-ttu-id="1b358-611">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1b358-612">Prod 1</span></span></td>
<td><span data-ttu-id="1b358-613">Producto 1</span><span class="sxs-lookup"><span data-stu-id="1b358-613">Product 1</span></span></td>
<td><span data-ttu-id="1b358-614">60</span><span class="sxs-lookup"><span data-stu-id="1b358-614">60</span></span></td>
<td><span data-ttu-id="1b358-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="1b358-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="1b358-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="1b358-616">4,487.12</span></span></td>
<td><span data-ttu-id="1b358-617">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1b358-618">Prod 2</span></span></td>
<td><span data-ttu-id="1b358-619">Producto 2</span><span class="sxs-lookup"><span data-stu-id="1b358-619">Product 2</span></span></td>
<td><span data-ttu-id="1b358-620">20</span><span class="sxs-lookup"><span data-stu-id="1b358-620">20</span></span></td>
<td><span data-ttu-id="1b358-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="1b358-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="1b358-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="1b358-622">1,495.71</span></span></td>
<td><span data-ttu-id="1b358-623">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="1b358-624">La tabla siguiente muestra el resultado cuando se aplican los servicios de Embalaje como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="1b358-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1b358-625">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-625">Cost object</span></span></th>
<th><span data-ttu-id="1b358-626">Magnitud</span><span class="sxs-lookup"><span data-stu-id="1b358-626">Magnitude</span></span></th>
<th><span data-ttu-id="1b358-627">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="1b358-627">Allocation factor</span></span></th>
<th><span data-ttu-id="1b358-628">Importe</span><span class="sxs-lookup"><span data-stu-id="1b358-628">Amount</span></span></th>
<th><span data-ttu-id="1b358-629">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="1b358-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1b358-630">Prod 1</span></span></td>
<td><span data-ttu-id="1b358-631">Producto 1</span><span class="sxs-lookup"><span data-stu-id="1b358-631">Product 1</span></span></td>
<td><span data-ttu-id="1b358-632">80</span><span class="sxs-lookup"><span data-stu-id="1b358-632">80</span></span></td>
<td><span data-ttu-id="1b358-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="1b358-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="1b358-634">241.05</span><span class="sxs-lookup"><span data-stu-id="1b358-634">241.05</span></span></td>
<td><span data-ttu-id="1b358-635">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1b358-636">Prod 2</span></span></td>
<td><span data-ttu-id="1b358-637">Producto 2</span><span class="sxs-lookup"><span data-stu-id="1b358-637">Product 2</span></span></td>
<td><span data-ttu-id="1b358-638">15</span><span class="sxs-lookup"><span data-stu-id="1b358-638">15</span></span></td>
<td><span data-ttu-id="1b358-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="1b358-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="1b358-640">45.20</span><span class="sxs-lookup"><span data-stu-id="1b358-640">45.20</span></span></td>
<td><span data-ttu-id="1b358-641">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1b358-642">Prod 1</span></span></td>
<td><span data-ttu-id="1b358-643">Producto 1</span><span class="sxs-lookup"><span data-stu-id="1b358-643">Product 1</span></span></td>
<td><span data-ttu-id="1b358-644">80</span><span class="sxs-lookup"><span data-stu-id="1b358-644">80</span></span></td>
<td><span data-ttu-id="1b358-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="1b358-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="1b358-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="1b358-646">2,507.09</span></span></td>
<td><span data-ttu-id="1b358-647">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1b358-648">Prod 2</span></span></td>
<td><span data-ttu-id="1b358-649">Producto 2</span><span class="sxs-lookup"><span data-stu-id="1b358-649">Product 2</span></span></td>
<td><span data-ttu-id="1b358-650">15</span><span class="sxs-lookup"><span data-stu-id="1b358-650">15</span></span></td>
<td><span data-ttu-id="1b358-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="1b358-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="1b358-652">470.08</span><span class="sxs-lookup"><span data-stu-id="1b358-652">470.08</span></span></td>
<td><span data-ttu-id="1b358-653">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="1b358-654">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="1b358-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1b358-655">Diario</span><span class="sxs-lookup"><span data-stu-id="1b358-655">Journal</span></span></th>
<th><span data-ttu-id="1b358-656">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="1b358-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="1b358-657">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="1b358-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="1b358-658">Versión</span><span class="sxs-lookup"><span data-stu-id="1b358-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-659">00004</span><span class="sxs-lookup"><span data-stu-id="1b358-659">00004</span></span></td>
<td><span data-ttu-id="1b358-660">Diario de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="1b358-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="1b358-661">Fiscal</span><span class="sxs-lookup"><span data-stu-id="1b358-661">Fiscal</span></span></td>
<td><span data-ttu-id="1b358-662">2017</span><span class="sxs-lookup"><span data-stu-id="1b358-662">2017</span></span></td>
<td><span data-ttu-id="1b358-663">Período 1</span><span class="sxs-lookup"><span data-stu-id="1b358-663">Period 1</span></span></td>
<td><span data-ttu-id="1b358-664">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="1b358-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="1b358-665">Líneas de diario</span><span class="sxs-lookup"><span data-stu-id="1b358-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1b358-666">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="1b358-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="1b358-667">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="1b358-668">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-668">Cost element</span></span></th>
<th><span data-ttu-id="1b358-669">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="1b358-669">Cost behavior</span></span></th>
<th><span data-ttu-id="1b358-670">Importe</span><span class="sxs-lookup"><span data-stu-id="1b358-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-671">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="1b358-672">CC001</span><span class="sxs-lookup"><span data-stu-id="1b358-672">CC001</span></span></td>
<td><span data-ttu-id="1b358-673">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="1b358-673">HR</span></span></td>
<td><span data-ttu-id="1b358-674">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-674">10001</span></span></td>
<td><span data-ttu-id="1b358-675">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-675">Electricity</span></span></td>
<td><span data-ttu-id="1b358-676">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-676">Fixed cost</span></span></td>
<td><span data-ttu-id="1b358-677">500,00</span><span class="sxs-lookup"><span data-stu-id="1b358-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-678">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="1b358-679">CC001</span><span class="sxs-lookup"><span data-stu-id="1b358-679">CC001</span></span></td>
<td><span data-ttu-id="1b358-680">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="1b358-680">HR</span></span></td>
<td><span data-ttu-id="1b358-681">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-681">10001</span></span></td>
<td><span data-ttu-id="1b358-682">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-682">Electricity</span></span></td>
<td><span data-ttu-id="1b358-683">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-683">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="1b358-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-685">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="1b358-686">CC002</span><span class="sxs-lookup"><span data-stu-id="1b358-686">CC002</span></span></td>
<td><span data-ttu-id="1b358-687">Finanzas</span><span class="sxs-lookup"><span data-stu-id="1b358-687">Finance</span></span></td>
<td><span data-ttu-id="1b358-688">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-688">10001</span></span></td>
<td><span data-ttu-id="1b358-689">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-689">Electricity</span></span></td>
<td><span data-ttu-id="1b358-690">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-690">Fixed cost</span></span></td>
<td><span data-ttu-id="1b358-691">675.00</span><span class="sxs-lookup"><span data-stu-id="1b358-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-692">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="1b358-693">CC002</span><span class="sxs-lookup"><span data-stu-id="1b358-693">CC002</span></span></td>
<td><span data-ttu-id="1b358-694">Finanzas</span><span class="sxs-lookup"><span data-stu-id="1b358-694">Finance</span></span></td>
<td><span data-ttu-id="1b358-695">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-695">10001</span></span></td>
<td><span data-ttu-id="1b358-696">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-696">Electricity</span></span></td>
<td><span data-ttu-id="1b358-697">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-697">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="1b358-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-699">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="1b358-700">CC003</span><span class="sxs-lookup"><span data-stu-id="1b358-700">CC003</span></span></td>
<td><span data-ttu-id="1b358-701">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="1b358-701">Assembly</span></span></td>
<td><span data-ttu-id="1b358-702">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-702">10001</span></span></td>
<td><span data-ttu-id="1b358-703">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-703">Electricity</span></span></td>
<td><span data-ttu-id="1b358-704">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-704">Fixed cost</span></span></td>
<td><span data-ttu-id="1b358-705">713.75</span><span class="sxs-lookup"><span data-stu-id="1b358-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-706">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="1b358-707">CC003</span><span class="sxs-lookup"><span data-stu-id="1b358-707">CC003</span></span></td>
<td><span data-ttu-id="1b358-708">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="1b358-708">Assembly</span></span></td>
<td><span data-ttu-id="1b358-709">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-709">10001</span></span></td>
<td><span data-ttu-id="1b358-710">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-710">Electricity</span></span></td>
<td><span data-ttu-id="1b358-711">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-711">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="1b358-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-713">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="1b358-714">CC003</span><span class="sxs-lookup"><span data-stu-id="1b358-714">CC003</span></span></td>
<td><span data-ttu-id="1b358-715">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="1b358-715">Packaging</span></span></td>
<td><span data-ttu-id="1b358-716">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-716">10001</span></span></td>
<td><span data-ttu-id="1b358-717">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-717">Electricity</span></span></td>
<td><span data-ttu-id="1b358-718">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-718">Fixed cost</span></span></td>
<td><span data-ttu-id="1b358-719">286.25</span><span class="sxs-lookup"><span data-stu-id="1b358-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-720">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="1b358-721">CC003</span><span class="sxs-lookup"><span data-stu-id="1b358-721">CC003</span></span></td>
<td><span data-ttu-id="1b358-722">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="1b358-722">Packaging</span></span></td>
<td><span data-ttu-id="1b358-723">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-723">10001</span></span></td>
<td><span data-ttu-id="1b358-724">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-724">Electricity</span></span></td>
<td><span data-ttu-id="1b358-725">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-725">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="1b358-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-727">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="1b358-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1b358-728">Prod 1</span></span></td>
<td><span data-ttu-id="1b358-729">Producto 1</span><span class="sxs-lookup"><span data-stu-id="1b358-729">Product 1</span></span></td>
<td><span data-ttu-id="1b358-730">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-730">10001</span></span></td>
<td><span data-ttu-id="1b358-731">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-731">Electricity</span></span></td>
<td><span data-ttu-id="1b358-732">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-732">Fixed cost</span></span></td>
<td><span data-ttu-id="1b358-733">776.36</span><span class="sxs-lookup"><span data-stu-id="1b358-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-734">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="1b358-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1b358-735">Prod 1</span></span></td>
<td><span data-ttu-id="1b358-736">Producto 1</span><span class="sxs-lookup"><span data-stu-id="1b358-736">Product 1</span></span></td>
<td><span data-ttu-id="1b358-737">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-737">10001</span></span></td>
<td><span data-ttu-id="1b358-738">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-738">Electricity</span></span></td>
<td><span data-ttu-id="1b358-739">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-739">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="1b358-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-741">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="1b358-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1b358-742">Prod 2</span></span></td>
<td><span data-ttu-id="1b358-743">Producto 1</span><span class="sxs-lookup"><span data-stu-id="1b358-743">Product 1</span></span></td>
<td><span data-ttu-id="1b358-744">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-744">10001</span></span></td>
<td><span data-ttu-id="1b358-745">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-745">Electricity</span></span></td>
<td><span data-ttu-id="1b358-746">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-746">Fixed cost</span></span></td>
<td><span data-ttu-id="1b358-747">223.64</span><span class="sxs-lookup"><span data-stu-id="1b358-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-748">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="1b358-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1b358-749">Prod 2</span></span></td>
<td><span data-ttu-id="1b358-750">Producto 1</span><span class="sxs-lookup"><span data-stu-id="1b358-750">Product 1</span></span></td>
<td><span data-ttu-id="1b358-751">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-751">10001</span></span></td>
<td><span data-ttu-id="1b358-752">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-752">Electricity</span></span></td>
<td><span data-ttu-id="1b358-753">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-753">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="1b358-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="1b358-755">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="1b358-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="1b358-756">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="1b358-757">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-757">Cost element</span></span></th>
<th><span data-ttu-id="1b358-758">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="1b358-758">Cost behavior</span></span></th>
<th><span data-ttu-id="1b358-759">Importe</span><span class="sxs-lookup"><span data-stu-id="1b358-759">Amount</span></span></th>
<th><span data-ttu-id="1b358-760">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="1b358-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b358-761">CC001</span><span class="sxs-lookup"><span data-stu-id="1b358-761">CC001</span></span></td>
<td><span data-ttu-id="1b358-762">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="1b358-762">HR</span></span></td>
<td><span data-ttu-id="1b358-763">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-763">10001</span></span></td>
<td><span data-ttu-id="1b358-764">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-764">Electricity</span></span></td>
<td><span data-ttu-id="1b358-765">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-765">Fixed cost</span></span></td>
<td><span data-ttu-id="1b358-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="1b358-766">-500.00</span></span></td>
<td><span data-ttu-id="1b358-767">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-768">CC002</span><span class="sxs-lookup"><span data-stu-id="1b358-768">CC002</span></span></td>
<td><span data-ttu-id="1b358-769">Finanzas</span><span class="sxs-lookup"><span data-stu-id="1b358-769">Finance</span></span></td>
<td><span data-ttu-id="1b358-770">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-770">10001</span></span></td>
<td><span data-ttu-id="1b358-771">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-771">Electricity</span></span></td>
<td><span data-ttu-id="1b358-772">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-772">Fixed cost</span></span></td>
<td><span data-ttu-id="1b358-773">175.00</span><span class="sxs-lookup"><span data-stu-id="1b358-773">175.00</span></span></td>
<td><span data-ttu-id="1b358-774">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-775">CC003</span><span class="sxs-lookup"><span data-stu-id="1b358-775">CC003</span></span></td>
<td><span data-ttu-id="1b358-776">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="1b358-776">Assembly</span></span></td>
<td><span data-ttu-id="1b358-777">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-777">10001</span></span></td>
<td><span data-ttu-id="1b358-778">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-778">Electricity</span></span></td>
<td><span data-ttu-id="1b358-779">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-779">Fixed cost</span></span></td>
<td><span data-ttu-id="1b358-780">275.00</span><span class="sxs-lookup"><span data-stu-id="1b358-780">275.00</span></span></td>
<td><span data-ttu-id="1b358-781">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-782">CC004</span><span class="sxs-lookup"><span data-stu-id="1b358-782">CC004</span></span></td>
<td><span data-ttu-id="1b358-783">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="1b358-783">Packaging</span></span></td>
<td><span data-ttu-id="1b358-784">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-784">10001</span></span></td>
<td><span data-ttu-id="1b358-785">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-785">Electricity</span></span></td>
<td><span data-ttu-id="1b358-786">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-786">Fixed cost</span></span></td>
<td><span data-ttu-id="1b358-787">50,00</span><span class="sxs-lookup"><span data-stu-id="1b358-787">50,00</span></span></td>
<td><span data-ttu-id="1b358-788">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-789">CC001</span><span class="sxs-lookup"><span data-stu-id="1b358-789">CC001</span></span></td>
<td><span data-ttu-id="1b358-790">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="1b358-790">HR</span></span></td>
<td><span data-ttu-id="1b358-791">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-791">10001</span></span></td>
<td><span data-ttu-id="1b358-792">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-792">Electricity</span></span></td>
<td><span data-ttu-id="1b358-793">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-793">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="1b358-794">-1,245.71</span></span></td>
<td><span data-ttu-id="1b358-795">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-796">CC002</span><span class="sxs-lookup"><span data-stu-id="1b358-796">CC002</span></span></td>
<td><span data-ttu-id="1b358-797">Finanzas</span><span class="sxs-lookup"><span data-stu-id="1b358-797">Finance</span></span></td>
<td><span data-ttu-id="1b358-798">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-798">10001</span></span></td>
<td><span data-ttu-id="1b358-799">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-799">Electricity</span></span></td>
<td><span data-ttu-id="1b358-800">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-800">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-801">436.00</span><span class="sxs-lookup"><span data-stu-id="1b358-801">436.00</span></span></td>
<td><span data-ttu-id="1b358-802">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-803">CC003</span><span class="sxs-lookup"><span data-stu-id="1b358-803">CC003</span></span></td>
<td><span data-ttu-id="1b358-804">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="1b358-804">Assembly</span></span></td>
<td><span data-ttu-id="1b358-805">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-805">10001</span></span></td>
<td><span data-ttu-id="1b358-806">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-806">Electricity</span></span></td>
<td><span data-ttu-id="1b358-807">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-807">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-808">685.14</span><span class="sxs-lookup"><span data-stu-id="1b358-808">685.14</span></span></td>
<td><span data-ttu-id="1b358-809">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-810">CC004</span><span class="sxs-lookup"><span data-stu-id="1b358-810">CC004</span></span></td>
<td><span data-ttu-id="1b358-811">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="1b358-811">Packaging</span></span></td>
<td><span data-ttu-id="1b358-812">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-812">10001</span></span></td>
<td><span data-ttu-id="1b358-813">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-813">Electricity</span></span></td>
<td><span data-ttu-id="1b358-814">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-814">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-815">124.57</span><span class="sxs-lookup"><span data-stu-id="1b358-815">124.57</span></span></td>
<td><span data-ttu-id="1b358-816">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-817">CC002</span><span class="sxs-lookup"><span data-stu-id="1b358-817">CC002</span></span></td>
<td><span data-ttu-id="1b358-818">Finanzas</span><span class="sxs-lookup"><span data-stu-id="1b358-818">Finance</span></span></td>
<td><span data-ttu-id="1b358-819">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-819">10001</span></span></td>
<td><span data-ttu-id="1b358-820">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-820">Electricity</span></span></td>
<td><span data-ttu-id="1b358-821">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-821">Fixed cost</span></span></td>
<td><span data-ttu-id="1b358-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="1b358-822">-675.00</span></span></td>
<td><span data-ttu-id="1b358-823">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-824">CC003</span><span class="sxs-lookup"><span data-stu-id="1b358-824">CC003</span></span></td>
<td><span data-ttu-id="1b358-825">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="1b358-825">Assembly</span></span></td>
<td><span data-ttu-id="1b358-826">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-826">10001</span></span></td>
<td><span data-ttu-id="1b358-827">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-827">Electricity</span></span></td>
<td><span data-ttu-id="1b358-828">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-828">Fixed cost</span></span></td>
<td><span data-ttu-id="1b358-829">438.75</span><span class="sxs-lookup"><span data-stu-id="1b358-829">438.75</span></span></td>
<td><span data-ttu-id="1b358-830">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-831">CC004</span><span class="sxs-lookup"><span data-stu-id="1b358-831">CC004</span></span></td>
<td><span data-ttu-id="1b358-832">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="1b358-832">Packaging</span></span></td>
<td><span data-ttu-id="1b358-833">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-833">10001</span></span></td>
<td><span data-ttu-id="1b358-834">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-834">Electricity</span></span></td>
<td><span data-ttu-id="1b358-835">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-835">Fixed cost</span></span></td>
<td><span data-ttu-id="1b358-836">236.25</span><span class="sxs-lookup"><span data-stu-id="1b358-836">236.25</span></span></td>
<td><span data-ttu-id="1b358-837">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-838">CC002</span><span class="sxs-lookup"><span data-stu-id="1b358-838">CC002</span></span></td>
<td><span data-ttu-id="1b358-839">Finanzas</span><span class="sxs-lookup"><span data-stu-id="1b358-839">Finance</span></span></td>
<td><span data-ttu-id="1b358-840">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-840">10001</span></span></td>
<td><span data-ttu-id="1b358-841">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-841">Electricity</span></span></td>
<td><span data-ttu-id="1b358-842">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-842">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="1b358-843">-8,150.29</span></span></td>
<td><span data-ttu-id="1b358-844">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-845">CC003</span><span class="sxs-lookup"><span data-stu-id="1b358-845">CC003</span></span></td>
<td><span data-ttu-id="1b358-846">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="1b358-846">Assembly</span></span></td>
<td><span data-ttu-id="1b358-847">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-847">10001</span></span></td>
<td><span data-ttu-id="1b358-848">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-848">Electricity</span></span></td>
<td><span data-ttu-id="1b358-849">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-849">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="1b358-850">5,297.69</span></span></td>
<td><span data-ttu-id="1b358-851">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-852">CC004</span><span class="sxs-lookup"><span data-stu-id="1b358-852">CC004</span></span></td>
<td><span data-ttu-id="1b358-853">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="1b358-853">Packaging</span></span></td>
<td><span data-ttu-id="1b358-854">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-854">10001</span></span></td>
<td><span data-ttu-id="1b358-855">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-855">Electricity</span></span></td>
<td><span data-ttu-id="1b358-856">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-856">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="1b358-857">2,852.60</span></span></td>
<td><span data-ttu-id="1b358-858">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-859">CC003</span><span class="sxs-lookup"><span data-stu-id="1b358-859">CC003</span></span></td>
<td><span data-ttu-id="1b358-860">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="1b358-860">Assembly</span></span></td>
<td><span data-ttu-id="1b358-861">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-861">10001</span></span></td>
<td><span data-ttu-id="1b358-862">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-862">Electricity</span></span></td>
<td><span data-ttu-id="1b358-863">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-863">Fixed cost</span></span></td>
<td><span data-ttu-id="1b358-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="1b358-864">-713.75</span></span></td>
<td><span data-ttu-id="1b358-865">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1b358-866">Prod 1</span></span></td>
<td><span data-ttu-id="1b358-867">Producto 1</span><span class="sxs-lookup"><span data-stu-id="1b358-867">Product 1</span></span></td>
<td><span data-ttu-id="1b358-868">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-868">10001</span></span></td>
<td><span data-ttu-id="1b358-869">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-869">Electricity</span></span></td>
<td><span data-ttu-id="1b358-870">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-870">Fixed cost</span></span></td>
<td><span data-ttu-id="1b358-871">535.31</span><span class="sxs-lookup"><span data-stu-id="1b358-871">535.31</span></span></td>
<td><span data-ttu-id="1b358-872">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1b358-873">Prod 2</span></span></td>
<td><span data-ttu-id="1b358-874">Producto 2</span><span class="sxs-lookup"><span data-stu-id="1b358-874">Product 2</span></span></td>
<td><span data-ttu-id="1b358-875">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-875">10001</span></span></td>
<td><span data-ttu-id="1b358-876">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-876">Electricity</span></span></td>
<td><span data-ttu-id="1b358-877">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-877">Fixed cost</span></span></td>
<td><span data-ttu-id="1b358-878">178.44</span><span class="sxs-lookup"><span data-stu-id="1b358-878">178.44</span></span></td>
<td><span data-ttu-id="1b358-879">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-880">CC003</span><span class="sxs-lookup"><span data-stu-id="1b358-880">CC003</span></span></td>
<td><span data-ttu-id="1b358-881">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="1b358-881">Assembly</span></span></td>
<td><span data-ttu-id="1b358-882">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-882">10001</span></span></td>
<td><span data-ttu-id="1b358-883">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-883">Electricity</span></span></td>
<td><span data-ttu-id="1b358-884">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-884">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="1b358-885">-5,982.83</span></span></td>
<td><span data-ttu-id="1b358-886">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1b358-887">Prod 1</span></span></td>
<td><span data-ttu-id="1b358-888">Producto 1</span><span class="sxs-lookup"><span data-stu-id="1b358-888">Product 1</span></span></td>
<td><span data-ttu-id="1b358-889">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-889">10001</span></span></td>
<td><span data-ttu-id="1b358-890">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-890">Electricity</span></span></td>
<td><span data-ttu-id="1b358-891">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-891">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="1b358-892">4,487.12</span></span></td>
<td><span data-ttu-id="1b358-893">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1b358-894">Prod 2</span></span></td>
<td><span data-ttu-id="1b358-895">Producto 2</span><span class="sxs-lookup"><span data-stu-id="1b358-895">Product 2</span></span></td>
<td><span data-ttu-id="1b358-896">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-896">10001</span></span></td>
<td><span data-ttu-id="1b358-897">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-897">Electricity</span></span></td>
<td><span data-ttu-id="1b358-898">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-898">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="1b358-899">1,495.71</span></span></td>
<td><span data-ttu-id="1b358-900">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-901">CC003</span><span class="sxs-lookup"><span data-stu-id="1b358-901">CC003</span></span></td>
<td><span data-ttu-id="1b358-902">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="1b358-902">Assembly</span></span></td>
<td><span data-ttu-id="1b358-903">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-903">10001</span></span></td>
<td><span data-ttu-id="1b358-904">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-904">Electricity</span></span></td>
<td><span data-ttu-id="1b358-905">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-905">Fixed cost</span></span></td>
<td><span data-ttu-id="1b358-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="1b358-906">-286.25</span></span></td>
<td><span data-ttu-id="1b358-907">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1b358-908">Prod 1</span></span></td>
<td><span data-ttu-id="1b358-909">Producto 1</span><span class="sxs-lookup"><span data-stu-id="1b358-909">Product 1</span></span></td>
<td><span data-ttu-id="1b358-910">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-910">10001</span></span></td>
<td><span data-ttu-id="1b358-911">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-911">Electricity</span></span></td>
<td><span data-ttu-id="1b358-912">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-912">Fixed cost</span></span></td>
<td><span data-ttu-id="1b358-913">241.05</span><span class="sxs-lookup"><span data-stu-id="1b358-913">241.05</span></span></td>
<td><span data-ttu-id="1b358-914">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1b358-915">Prod 2</span></span></td>
<td><span data-ttu-id="1b358-916">Producto 2</span><span class="sxs-lookup"><span data-stu-id="1b358-916">Product 2</span></span></td>
<td><span data-ttu-id="1b358-917">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-917">10001</span></span></td>
<td><span data-ttu-id="1b358-918">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-918">Electricity</span></span></td>
<td><span data-ttu-id="1b358-919">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-919">Fixed cost</span></span></td>
<td><span data-ttu-id="1b358-920">45.20</span><span class="sxs-lookup"><span data-stu-id="1b358-920">45.20</span></span></td>
<td><span data-ttu-id="1b358-921">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-922">CC003</span><span class="sxs-lookup"><span data-stu-id="1b358-922">CC003</span></span></td>
<td><span data-ttu-id="1b358-923">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="1b358-923">Assembly</span></span></td>
<td><span data-ttu-id="1b358-924">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-924">10001</span></span></td>
<td><span data-ttu-id="1b358-925">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-925">Electricity</span></span></td>
<td><span data-ttu-id="1b358-926">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-926">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="1b358-927">-2,977.17</span></span></td>
<td><span data-ttu-id="1b358-928">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1b358-929">Prod 1</span></span></td>
<td><span data-ttu-id="1b358-930">Producto 1</span><span class="sxs-lookup"><span data-stu-id="1b358-930">Product 1</span></span></td>
<td><span data-ttu-id="1b358-931">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-931">10001</span></span></td>
<td><span data-ttu-id="1b358-932">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-932">Electricity</span></span></td>
<td><span data-ttu-id="1b358-933">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-933">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="1b358-934">2,507.09</span></span></td>
<td><span data-ttu-id="1b358-935">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b358-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1b358-936">Prod 2</span></span></td>
<td><span data-ttu-id="1b358-937">Producto 2</span><span class="sxs-lookup"><span data-stu-id="1b358-937">Product 2</span></span></td>
<td><span data-ttu-id="1b358-938">10001</span><span class="sxs-lookup"><span data-stu-id="1b358-938">10001</span></span></td>
<td><span data-ttu-id="1b358-939">Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-939">Electricity</span></span></td>
<td><span data-ttu-id="1b358-940">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-940">Variable cost</span></span></td>
<td><span data-ttu-id="1b358-941">470.08</span><span class="sxs-lookup"><span data-stu-id="1b358-941">470.08</span></span></td>
<td><span data-ttu-id="1b358-942">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="1b358-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="1b358-943">Conclusión</span><span class="sxs-lookup"><span data-stu-id="1b358-943">Conclusion</span></span>
<span data-ttu-id="1b358-944">En la contabilidad financiera, un coste de 10.000,00 para electricidad se envía a un identificador ficticio de centro de coste.</span><span class="sxs-lookup"><span data-stu-id="1b358-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="1b358-945">Por lo tanto, los contables de coste sabrán que este coste se debe asignar.</span><span class="sxs-lookup"><span data-stu-id="1b358-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="1b358-946">En contabilidad de costes, los costes fluyen en las unidades organizativas y los niveles en función de las directivas y las reglas que se aplican.</span><span class="sxs-lookup"><span data-stu-id="1b358-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="1b358-947">Cada coste se ha asociado con una base de asignación que proporciona la mejor evaluación para la asignación de costes.</span><span class="sxs-lookup"><span data-stu-id="1b358-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="1b358-948">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="1b358-949">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="1b358-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="1b358-950">Total</span><span class="sxs-lookup"><span data-stu-id="1b358-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="1b358-951">CC099</span><span class="sxs-lookup"><span data-stu-id="1b358-951">CC099</span></span></th>
<th><span data-ttu-id="1b358-952">CC001</span><span class="sxs-lookup"><span data-stu-id="1b358-952">CC001</span></span></th>
<th><span data-ttu-id="1b358-953">CC002</span><span class="sxs-lookup"><span data-stu-id="1b358-953">CC002</span></span></th>
<th><span data-ttu-id="1b358-954">CC003</span><span class="sxs-lookup"><span data-stu-id="1b358-954">CC003</span></span></th>
<th><span data-ttu-id="1b358-955">CC004</span><span class="sxs-lookup"><span data-stu-id="1b358-955">CC004</span></span></th>
<th><span data-ttu-id="1b358-956">Proy 1</span><span class="sxs-lookup"><span data-stu-id="1b358-956">Proj 1</span></span></th>
<th><span data-ttu-id="1b358-957">Proy 2</span><span class="sxs-lookup"><span data-stu-id="1b358-957">Proj 2</span></span></th>
<th><span data-ttu-id="1b358-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="1b358-958">Prod 1</span></span></th>
<th><span data-ttu-id="1b358-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="1b358-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="1b358-960">10001 Electricidad</span><span class="sxs-lookup"><span data-stu-id="1b358-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="1b358-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="1b358-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="1b358-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="1b358-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="1b358-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="1b358-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="1b358-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="1b358-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="1b358-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="1b358-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="1b358-970">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="1b358-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-971">0,00</span><span class="sxs-lookup"><span data-stu-id="1b358-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="1b358-972">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="1b358-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-973">0,00</span><span class="sxs-lookup"><span data-stu-id="1b358-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-974">0,00</span><span class="sxs-lookup"><span data-stu-id="1b358-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-975">0,00</span><span class="sxs-lookup"><span data-stu-id="1b358-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-976">0,00</span><span class="sxs-lookup"><span data-stu-id="1b358-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-977">0,00</span><span class="sxs-lookup"><span data-stu-id="1b358-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="1b358-978">776.36</span><span class="sxs-lookup"><span data-stu-id="1b358-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-979">223.64</span><span class="sxs-lookup"><span data-stu-id="1b358-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="1b358-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="1b358-981">Coste variable</span><span class="sxs-lookup"><span data-stu-id="1b358-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-982">000</span><span class="sxs-lookup"><span data-stu-id="1b358-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-983">0,00</span><span class="sxs-lookup"><span data-stu-id="1b358-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-984">0,00</span><span class="sxs-lookup"><span data-stu-id="1b358-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-985">0,00</span><span class="sxs-lookup"><span data-stu-id="1b358-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-986">0,00</span><span class="sxs-lookup"><span data-stu-id="1b358-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-987">30,00</span><span class="sxs-lookup"><span data-stu-id="1b358-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-988">10,00</span><span class="sxs-lookup"><span data-stu-id="1b358-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="1b358-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="1b358-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="1b358-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="1b358-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="1b358-992">Este tema muestra cómo un artículo de costes principales, 10001 Electricidad, fluye por los objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="1b358-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="1b358-993">Por tanto, estos gastos generales se asignan al nivel más bajo de la organización.</span><span class="sxs-lookup"><span data-stu-id="1b358-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="1b358-994">Es decir, los objetos de coste del nivel más bajo son los que soportan el coste.</span><span class="sxs-lookup"><span data-stu-id="1b358-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="1b358-995">Si necesita un flujo visual del coste entre los objetos de coste, puede usar las reglas de directivas de acumulación de costes para visualizar el flujo del coste.</span><span class="sxs-lookup"><span data-stu-id="1b358-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="1b358-996">Para obtener más información, consulte [Directiva de acumulación de costes y cálculo de costes generales](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="1b358-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



