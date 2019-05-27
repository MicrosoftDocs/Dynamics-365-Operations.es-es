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
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544064"
---
# <a name="overhead-calculation"></a><span data-ttu-id="4b87f-103">Cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="4b87f-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4b87f-104">Este tema describe los procesos típicos para calcular y asignar costes generales.</span><span class="sxs-lookup"><span data-stu-id="4b87f-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="4b87f-105">Definición del término</span><span class="sxs-lookup"><span data-stu-id="4b87f-105">Term definition</span></span>
---------------

<span data-ttu-id="4b87f-106">Los costes generales son costes que se contraen para dirigir un negocio, pero que no pueden ser atribuidos directamente a ninguna actividad empresarial, productos, o servicio específicos.</span><span class="sxs-lookup"><span data-stu-id="4b87f-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="4b87f-107">Los costes generales proporcionan un soporte fundamental a la generación de actividades rentables.</span><span class="sxs-lookup"><span data-stu-id="4b87f-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="4b87f-108">Algunos ejemplos de costes generales son:</span><span class="sxs-lookup"><span data-stu-id="4b87f-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="4b87f-109">Alquiler</span><span class="sxs-lookup"><span data-stu-id="4b87f-109">Rent</span></span>
-   <span data-ttu-id="4b87f-110">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-110">Electricity</span></span>
-   <span data-ttu-id="4b87f-111">Sueldos administrativos</span><span class="sxs-lookup"><span data-stu-id="4b87f-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="4b87f-112">Visión general del cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="4b87f-112">Overhead calculation overview</span></span>
<span data-ttu-id="4b87f-113">El cálculo de costes generales ejecuta las directivas de contabilidad de costes en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="4b87f-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="4b87f-114">Puede calcular varias veces los costes generales del mismo período fiscal si se han cambiado las directivas de contabilidad de costes o se han detectado errores específicos.</span><span class="sxs-lookup"><span data-stu-id="4b87f-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="4b87f-115">Cada ejecución del cálculo de costes generales se almacena y recibe un identificador de versión único que permite comparar los cálculos de diferentes versiones.</span><span class="sxs-lookup"><span data-stu-id="4b87f-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="4b87f-116">Las entradas de costes que el cálculo de costes generales genera reciben una fecha de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="4b87f-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="4b87f-117">Esta fecha de contabilidad coincide con la fecha final del período fiscal que se usa en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="4b87f-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="4b87f-118">El identificador de versión único consiste en los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4b87f-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="4b87f-119">Tipo de versión</span><span class="sxs-lookup"><span data-stu-id="4b87f-119">Version type</span></span>
-   <span data-ttu-id="4b87f-120">Fecha y hora</span><span class="sxs-lookup"><span data-stu-id="4b87f-120">Date and time</span></span>
-   <span data-ttu-id="4b87f-121">Libro mayor de contabilidad de costes</span><span class="sxs-lookup"><span data-stu-id="4b87f-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="4b87f-122">Ejercicio</span><span class="sxs-lookup"><span data-stu-id="4b87f-122">Fiscal year</span></span>
-   <span data-ttu-id="4b87f-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="4b87f-123">Fiscal period</span></span>

<span data-ttu-id="4b87f-124">El cálculo de costes generales se ejecuta independientemente de la versión.</span><span class="sxs-lookup"><span data-stu-id="4b87f-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="4b87f-125">Por lo tanto, puede calcular la versión de presupuesto antes que la versión real.</span><span class="sxs-lookup"><span data-stu-id="4b87f-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="4b87f-126">El cálculo de costes generales consta de cuatro pasos, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="4b87f-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="4b87f-127">En cada paso, se crea una cabecera de diario que tiene entradas del diario.</span><span class="sxs-lookup"><span data-stu-id="4b87f-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="4b87f-128">Esta cabecera de diario guarda los datos de entrada para cada paso de cálculo.</span><span class="sxs-lookup"><span data-stu-id="4b87f-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="4b87f-129">Las directivas y las reglas se aplican a cada línea de diario, y las entradas de coste se generan como resultado.</span><span class="sxs-lookup"><span data-stu-id="4b87f-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="4b87f-130">Por tanto, siempre se tiene rastreabilidad completa.</span><span class="sxs-lookup"><span data-stu-id="4b87f-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="4b87f-131">[![Cálculo de costes generales](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="4b87f-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="4b87f-132">Calcular y asignar costes generales de electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="4b87f-133">En la contabilidad financiera, algunos costes, como la electricidad, se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="4b87f-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="4b87f-134">Por lo tanto, no se proporciona una visión de gestión detallada para la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="4b87f-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="4b87f-135">En contabilidad de costes, para proporcionar información de gestión correcta en todas las unidades y niveles organizativos, los costes deben fluir por las unidades organizativas.</span><span class="sxs-lookup"><span data-stu-id="4b87f-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="4b87f-136">Este flujo se debe basar en cualquier registro preciso de consumo o en una evaluación justa.</span><span class="sxs-lookup"><span data-stu-id="4b87f-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="4b87f-137">En la contabilidad general, un coste de la electricidad se puede registrar como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="4b87f-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4b87f-138">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="4b87f-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="4b87f-139">Centro de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="4b87f-140">Cuenta principal</span><span class="sxs-lookup"><span data-stu-id="4b87f-140">Main account</span></span></th>
<th><span data-ttu-id="4b87f-141">Importe en la divisa de contabilidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-142">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="4b87f-143">CC099</span><span class="sxs-lookup"><span data-stu-id="4b87f-143">CC099</span></span></td>
<td><span data-ttu-id="4b87f-144">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="4b87f-144">Default cost center</span></span></td>
<td><span data-ttu-id="4b87f-145">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-145">10001</span></span></td>
<td><span data-ttu-id="4b87f-146">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-146">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="4b87f-148">Paso 1: Procese el cálculo del comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="4b87f-149">De forma predeterminada, cuando las entradas de coste se importan de los datos de origen, reciben la clasificación de comportamiento del coste **Sin ordenar** en la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="4b87f-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="4b87f-150">Aplicando reglas de directivas de comportamiento de coste, puede reclasificar entradas de coste como **Coste fijo** o **Coste variable**.</span><span class="sxs-lookup"><span data-stu-id="4b87f-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="4b87f-151">Defina la regla de comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-151">Define the cost behavior rule</span></span>

<span data-ttu-id="4b87f-152">En algunos casos, parte del coste es una cuota fija, y el coste pendiente se basa en el consumo.</span><span class="sxs-lookup"><span data-stu-id="4b87f-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="4b87f-153">Las facturas de electricidad coinciden a menudo con esta definición.</span><span class="sxs-lookup"><span data-stu-id="4b87f-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="4b87f-154">Tras pagar una cuota fija específica, paga el consumo por kilovatio-hora (Kwh).</span><span class="sxs-lookup"><span data-stu-id="4b87f-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="4b87f-155">Por ejemplo, si la cuota de coste fijo es de 1.000,00, la regla de comportamiento del coste se define como sigue:</span><span class="sxs-lookup"><span data-stu-id="4b87f-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="4b87f-156">Importe fijo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="4b87f-157">0 &lt;= 1.000,00 = Fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="4b87f-158">1.000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="4b87f-159">Diario</span><span class="sxs-lookup"><span data-stu-id="4b87f-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4b87f-160">Diario</span><span class="sxs-lookup"><span data-stu-id="4b87f-160">Journal</span></span></th>
<th><span data-ttu-id="4b87f-161">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="4b87f-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="4b87f-162">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="4b87f-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="4b87f-163">Versión</span><span class="sxs-lookup"><span data-stu-id="4b87f-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-164">00001</span><span class="sxs-lookup"><span data-stu-id="4b87f-164">00001</span></span></td>
<td><span data-ttu-id="4b87f-165">Diario de cálculo de comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4b87f-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="4b87f-166">Fiscal</span><span class="sxs-lookup"><span data-stu-id="4b87f-166">Fiscal</span></span></td>
<td><span data-ttu-id="4b87f-167">2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-167">2017</span></span></td>
<td><span data-ttu-id="4b87f-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-168">Period 1</span></span></td>
<td><span data-ttu-id="4b87f-169">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="4b87f-170">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="4b87f-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4b87f-171">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="4b87f-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="4b87f-172">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4b87f-173">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-173">Cost element</span></span></th>
<th><span data-ttu-id="4b87f-174">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4b87f-174">Cost behavior</span></span></th>
<th><span data-ttu-id="4b87f-175">Importe</span><span class="sxs-lookup"><span data-stu-id="4b87f-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-176">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="4b87f-177">CC099</span><span class="sxs-lookup"><span data-stu-id="4b87f-177">CC099</span></span></td>
<td><span data-ttu-id="4b87f-178">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="4b87f-178">Default cost center</span></span></td>
<td><span data-ttu-id="4b87f-179">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-179">10001</span></span></td>
<td><span data-ttu-id="4b87f-180">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-180">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-181">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="4b87f-181">Unclassified</span></span></td>
<td><span data-ttu-id="4b87f-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="4b87f-183">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="4b87f-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b87f-184">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4b87f-185">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-185">Cost element</span></span></th>
<th><span data-ttu-id="4b87f-186">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4b87f-186">Cost behavior</span></span></th>
<th><span data-ttu-id="4b87f-187">Importe</span><span class="sxs-lookup"><span data-stu-id="4b87f-187">Amount</span></span></th>
<th><span data-ttu-id="4b87f-188">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="4b87f-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-189">CC099</span><span class="sxs-lookup"><span data-stu-id="4b87f-189">CC099</span></span></td>
<td><span data-ttu-id="4b87f-190">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="4b87f-190">Default cost center</span></span></td>
<td><span data-ttu-id="4b87f-191">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-191">10001</span></span></td>
<td><span data-ttu-id="4b87f-192">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-192">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-193">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="4b87f-193">Unclassified</span></span></td>
<td><span data-ttu-id="4b87f-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-194">10,000.00</span></span></td>
<td><span data-ttu-id="4b87f-195">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-196">CC099</span><span class="sxs-lookup"><span data-stu-id="4b87f-196">CC099</span></span></td>
<td><span data-ttu-id="4b87f-197">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="4b87f-197">Default cost center</span></span></td>
<td><span data-ttu-id="4b87f-198">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-198">10001</span></span></td>
<td><span data-ttu-id="4b87f-199">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-199">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-200">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="4b87f-200">Unclassified</span></span></td>
<td><span data-ttu-id="4b87f-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-201">-10,000.00</span></span></td>
<td><span data-ttu-id="4b87f-202">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-203">CC099</span><span class="sxs-lookup"><span data-stu-id="4b87f-203">CC099</span></span></td>
<td><span data-ttu-id="4b87f-204">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="4b87f-204">Default cost center</span></span></td>
<td><span data-ttu-id="4b87f-205">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-205">10001</span></span></td>
<td><span data-ttu-id="4b87f-206">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-206">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-207">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-207">Fixed cost</span></span></td>
<td><span data-ttu-id="4b87f-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-208">1,000.00</span></span></td>
<td><span data-ttu-id="4b87f-209">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-210">CC099</span><span class="sxs-lookup"><span data-stu-id="4b87f-210">CC099</span></span></td>
<td><span data-ttu-id="4b87f-211">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="4b87f-211">Default cost center</span></span></td>
<td><span data-ttu-id="4b87f-212">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-212">10001</span></span></td>
<td><span data-ttu-id="4b87f-213">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-213">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-214">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-214">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-215">9,000.00</span></span></td>
<td><span data-ttu-id="4b87f-216">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b87f-217">Para obtener más información, consulte [Crear y asignar una directiva de comportamiento de costes a una unidad de control de costes](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="4b87f-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="4b87f-218">Paso 2: Procese el cálculo de distribución de costes</span><span class="sxs-lookup"><span data-stu-id="4b87f-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="4b87f-219">La distribución de costes se usa para redistribuir costes desde un objeto de coste a uno o más objetos de coste aplicando una base relevante de la asignación.</span><span class="sxs-lookup"><span data-stu-id="4b87f-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="4b87f-220">La distribución de costes y la asignación de costes difieren en que la distribución de costes siempre se produce en el nivel de elemento de costes principal del coste original.</span><span class="sxs-lookup"><span data-stu-id="4b87f-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="4b87f-221">Defina la regla de distribución del coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-221">Define the cost distribution rule</span></span>

<span data-ttu-id="4b87f-222">En la contabilidad financiera, los costes de electricidad se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="4b87f-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="4b87f-223">En contabilidad de costes, este método no es suficientemente detallado.</span><span class="sxs-lookup"><span data-stu-id="4b87f-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="4b87f-224">El coste variable debe distribuirse a los objetos individuales de coste aplicando una base justa.</span><span class="sxs-lookup"><span data-stu-id="4b87f-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="4b87f-225">La base de asignación más lógica es el consumo de electricidad (Kwh).</span><span class="sxs-lookup"><span data-stu-id="4b87f-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="4b87f-226">Se crea un miembro de dimensión estadística que se denomina Electricity, y se registra el consumo de electricidad.</span><span class="sxs-lookup"><span data-stu-id="4b87f-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="4b87f-227">De forma predeterminada, todos los miembros de dimensión estadísticos estarán disponibles como bases de asignación.</span><span class="sxs-lookup"><span data-stu-id="4b87f-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b87f-228">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-228">Cost object</span></span></th>
<th><span data-ttu-id="4b87f-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="4b87f-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-230">CC001</span><span class="sxs-lookup"><span data-stu-id="4b87f-230">CC001</span></span></td>
<td><span data-ttu-id="4b87f-231">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="4b87f-231">HR</span></span></td>
<td><span data-ttu-id="4b87f-232">1.000</span><span class="sxs-lookup"><span data-stu-id="4b87f-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-233">CC002</span><span class="sxs-lookup"><span data-stu-id="4b87f-233">CC002</span></span></td>
<td><span data-ttu-id="4b87f-234">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4b87f-234">Finance</span></span></td>
<td><span data-ttu-id="4b87f-235">6.000</span><span class="sxs-lookup"><span data-stu-id="4b87f-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-236">CC003</span><span class="sxs-lookup"><span data-stu-id="4b87f-236">CC003</span></span></td>
<td><span data-ttu-id="4b87f-237">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4b87f-237">Assembly</span></span></td>
<td><span data-ttu-id="4b87f-238">0</span><span class="sxs-lookup"><span data-stu-id="4b87f-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b87f-239">La tabla siguiente muestra el resultado cuando se aplica el consumo de electricidad como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="4b87f-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b87f-240">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-240">Cost object</span></span></th>
<th><span data-ttu-id="4b87f-241">Magnitud</span><span class="sxs-lookup"><span data-stu-id="4b87f-241">Magnitude</span></span></th>
<th><span data-ttu-id="4b87f-242">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="4b87f-242">Allocation factor</span></span></th>
<th><span data-ttu-id="4b87f-243">Importe</span><span class="sxs-lookup"><span data-stu-id="4b87f-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-244">CC001</span><span class="sxs-lookup"><span data-stu-id="4b87f-244">CC001</span></span></td>
<td><span data-ttu-id="4b87f-245">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="4b87f-245">HR</span></span></td>
<td><span data-ttu-id="4b87f-246">1.000</span><span class="sxs-lookup"><span data-stu-id="4b87f-246">1,000</span></span></td>
<td><span data-ttu-id="4b87f-247">(1.000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="4b87f-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="4b87f-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-249">CC002</span><span class="sxs-lookup"><span data-stu-id="4b87f-249">CC002</span></span></td>
<td><span data-ttu-id="4b87f-250">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4b87f-250">Finance</span></span></td>
<td><span data-ttu-id="4b87f-251">6.000</span><span class="sxs-lookup"><span data-stu-id="4b87f-251">6,000</span></span></td>
<td><span data-ttu-id="4b87f-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="4b87f-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="4b87f-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-254">CC003</span><span class="sxs-lookup"><span data-stu-id="4b87f-254">CC003</span></span></td>
<td><span data-ttu-id="4b87f-255">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4b87f-255">Assembly</span></span></td>
<td><span data-ttu-id="4b87f-256">0</span><span class="sxs-lookup"><span data-stu-id="4b87f-256">0</span></span></td>
<td><span data-ttu-id="4b87f-257">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="4b87f-258">0,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b87f-259">El coste fijo debe distribuirse uniformemente a los objetos individuales de costes que han consumido electricidad.</span><span class="sxs-lookup"><span data-stu-id="4b87f-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="4b87f-260">Puede obtener este resultado usando el miembro de dimensión estadístico de electricidad en una base de asignación de la fórmula: (Electricidad &gt; 0,00) La tabla siguiente muestra el resultado cuando el consumo de electricidad se aplica como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="4b87f-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b87f-261">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-261">Cost object</span></span></th>
<th><span data-ttu-id="4b87f-262">Fórmula</span><span class="sxs-lookup"><span data-stu-id="4b87f-262">Formula</span></span></th>
<th><span data-ttu-id="4b87f-263">Magnitud</span><span class="sxs-lookup"><span data-stu-id="4b87f-263">Magnitude</span></span></th>
<th><span data-ttu-id="4b87f-264">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="4b87f-264">Allocation factor</span></span></th>
<th><span data-ttu-id="4b87f-265">Importe</span><span class="sxs-lookup"><span data-stu-id="4b87f-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-266">CC001</span><span class="sxs-lookup"><span data-stu-id="4b87f-266">CC001</span></span></td>
<td><span data-ttu-id="4b87f-267">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="4b87f-267">HR</span></span></td>
<td><span data-ttu-id="4b87f-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="4b87f-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="4b87f-269">1</span><span class="sxs-lookup"><span data-stu-id="4b87f-269">1</span></span></td>
<td><span data-ttu-id="4b87f-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="4b87f-271">500,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-272">CC002</span><span class="sxs-lookup"><span data-stu-id="4b87f-272">CC002</span></span></td>
<td><span data-ttu-id="4b87f-273">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4b87f-273">Finance</span></span></td>
<td><span data-ttu-id="4b87f-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="4b87f-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="4b87f-275">1</span><span class="sxs-lookup"><span data-stu-id="4b87f-275">1</span></span></td>
<td><span data-ttu-id="4b87f-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="4b87f-277">500,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-278">CC003</span><span class="sxs-lookup"><span data-stu-id="4b87f-278">CC003</span></span></td>
<td><span data-ttu-id="4b87f-279">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4b87f-279">Assembly</span></span></td>
<td><span data-ttu-id="4b87f-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="4b87f-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="4b87f-281">0</span><span class="sxs-lookup"><span data-stu-id="4b87f-281">0</span></span></td>
<td><span data-ttu-id="4b87f-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="4b87f-283">0,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="4b87f-284">Diario</span><span class="sxs-lookup"><span data-stu-id="4b87f-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4b87f-285">Diario</span><span class="sxs-lookup"><span data-stu-id="4b87f-285">Journal</span></span></th>
<th><span data-ttu-id="4b87f-286">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="4b87f-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="4b87f-287">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="4b87f-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="4b87f-288">Versión</span><span class="sxs-lookup"><span data-stu-id="4b87f-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-289">00002</span><span class="sxs-lookup"><span data-stu-id="4b87f-289">00002</span></span></td>
<td><span data-ttu-id="4b87f-290">Diario de cálculo de la distribución de costes</span><span class="sxs-lookup"><span data-stu-id="4b87f-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="4b87f-291">Fiscal</span><span class="sxs-lookup"><span data-stu-id="4b87f-291">Fiscal</span></span></td>
<td><span data-ttu-id="4b87f-292">2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-292">2017</span></span></td>
<td><span data-ttu-id="4b87f-293">Período 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-293">Period 1</span></span></td>
<td><span data-ttu-id="4b87f-294">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="4b87f-295">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="4b87f-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4b87f-296">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="4b87f-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="4b87f-297">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4b87f-298">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-298">Cost element</span></span></th>
<th><span data-ttu-id="4b87f-299">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4b87f-299">Cost behavior</span></span></th>
<th><span data-ttu-id="4b87f-300">Importe</span><span class="sxs-lookup"><span data-stu-id="4b87f-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-301">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b87f-302">CC099</span><span class="sxs-lookup"><span data-stu-id="4b87f-302">CC099</span></span></td>
<td><span data-ttu-id="4b87f-303">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="4b87f-303">Default cost center</span></span></td>
<td><span data-ttu-id="4b87f-304">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-304">10001</span></span></td>
<td><span data-ttu-id="4b87f-305">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-305">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-306">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-306">Fixed cost</span></span></td>
<td><span data-ttu-id="4b87f-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-308">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b87f-309">CC099</span><span class="sxs-lookup"><span data-stu-id="4b87f-309">CC099</span></span></td>
<td><span data-ttu-id="4b87f-310">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="4b87f-310">Default cost center</span></span></td>
<td><span data-ttu-id="4b87f-311">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-311">10001</span></span></td>
<td><span data-ttu-id="4b87f-312">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-312">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-313">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-313">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-314">9.000,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="4b87f-315">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="4b87f-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b87f-316">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4b87f-317">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-317">Cost element</span></span></th>
<th><span data-ttu-id="4b87f-318">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4b87f-318">Cost behavior</span></span></th>
<th><span data-ttu-id="4b87f-319">Importe</span><span class="sxs-lookup"><span data-stu-id="4b87f-319">Amount</span></span></th>
<th><span data-ttu-id="4b87f-320">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="4b87f-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-321">CC099</span><span class="sxs-lookup"><span data-stu-id="4b87f-321">CC099</span></span></td>
<td><span data-ttu-id="4b87f-322">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="4b87f-322">Default cost center</span></span></td>
<td><span data-ttu-id="4b87f-323">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-323">10001</span></span></td>
<td><span data-ttu-id="4b87f-324">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-324">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-325">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-325">Fixed cost</span></span></td>
<td><span data-ttu-id="4b87f-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-326">-1,000.00</span></span></td>
<td><span data-ttu-id="4b87f-327">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-328">CC001</span><span class="sxs-lookup"><span data-stu-id="4b87f-328">CC001</span></span></td>
<td><span data-ttu-id="4b87f-329">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="4b87f-329">HR</span></span></td>
<td><span data-ttu-id="4b87f-330">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-330">10001</span></span></td>
<td><span data-ttu-id="4b87f-331">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-331">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-332">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-332">Fixed cost</span></span></td>
<td><span data-ttu-id="4b87f-333">500,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-333">500.00</span></span></td>
<td><span data-ttu-id="4b87f-334">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-335">CC002</span><span class="sxs-lookup"><span data-stu-id="4b87f-335">CC002</span></span></td>
<td><span data-ttu-id="4b87f-336">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4b87f-336">Finance</span></span></td>
<td><span data-ttu-id="4b87f-337">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-337">10001</span></span></td>
<td><span data-ttu-id="4b87f-338">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-338">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-339">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-339">Fixed cost</span></span></td>
<td><span data-ttu-id="4b87f-340">500,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-340">500.00</span></span></td>
<td><span data-ttu-id="4b87f-341">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-342">CC099</span><span class="sxs-lookup"><span data-stu-id="4b87f-342">CC099</span></span></td>
<td><span data-ttu-id="4b87f-343">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="4b87f-343">Default cost center</span></span></td>
<td><span data-ttu-id="4b87f-344">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-344">10001</span></span></td>
<td><span data-ttu-id="4b87f-345">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-345">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-346">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-346">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-347">-9,000.00</span></span></td>
<td><span data-ttu-id="4b87f-348">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-349">CC001</span><span class="sxs-lookup"><span data-stu-id="4b87f-349">CC001</span></span></td>
<td><span data-ttu-id="4b87f-350">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="4b87f-350">HR</span></span></td>
<td><span data-ttu-id="4b87f-351">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-351">10001</span></span></td>
<td><span data-ttu-id="4b87f-352">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-352">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-353">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-353">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="4b87f-354">1,285.71</span></span></td>
<td><span data-ttu-id="4b87f-355">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-356">CC002</span><span class="sxs-lookup"><span data-stu-id="4b87f-356">CC002</span></span></td>
<td><span data-ttu-id="4b87f-357">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4b87f-357">Finance</span></span></td>
<td><span data-ttu-id="4b87f-358">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-358">10001</span></span></td>
<td><span data-ttu-id="4b87f-359">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-359">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-360">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-360">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="4b87f-361">7,714.29</span></span></td>
<td><span data-ttu-id="4b87f-362">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b87f-363">Para obtener más información, consulte [Crear y asignar una directiva de distribución de costes a una unidad de control de costes](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="4b87f-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="4b87f-364">Paso 3: Procese el cálculo de las tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="4b87f-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="4b87f-365">La tasa de costes generales se usa para cargar uno o varios objetos de coste específicos.</span><span class="sxs-lookup"><span data-stu-id="4b87f-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="4b87f-366">El cargo se basa en un índice de coste predeterminado y la magnitud de la base de asignación asignada.</span><span class="sxs-lookup"><span data-stu-id="4b87f-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="4b87f-367">Defina la tasa de costes generales</span><span class="sxs-lookup"><span data-stu-id="4b87f-367">Define the overhead rate</span></span>

<span data-ttu-id="4b87f-368">El objeto de coste CC001 HR contribuye a un conjunto de proyectos internos.</span><span class="sxs-lookup"><span data-stu-id="4b87f-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="4b87f-369">Se crea un miembro de dimensión estadística que se denomina proyectos HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="4b87f-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b87f-370">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-370">Cost object</span></span></th>
<th><span data-ttu-id="4b87f-371">Horas</span><span class="sxs-lookup"><span data-stu-id="4b87f-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-372">Proy 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-372">Proj 1</span></span></td>
<td><span data-ttu-id="4b87f-373">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-373">Project 1</span></span></td>
<td><span data-ttu-id="4b87f-374">3</span><span class="sxs-lookup"><span data-stu-id="4b87f-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-375">Proy 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-375">Proj 2</span></span></td>
<td><span data-ttu-id="4b87f-376">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-376">Project 2</span></span></td>
<td><span data-ttu-id="4b87f-377">1</span><span class="sxs-lookup"><span data-stu-id="4b87f-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b87f-378">Una tasa de coste predeterminada para la contribución de los proyectos de coste se ha definido.</span><span class="sxs-lookup"><span data-stu-id="4b87f-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b87f-379">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-379">Cost object</span></span></th>
<th><span data-ttu-id="4b87f-380">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-380">Cost element</span></span></th>
<th><span data-ttu-id="4b87f-381">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4b87f-381">Cost behavior</span></span></th>
<th><span data-ttu-id="4b87f-382">Unidades</span><span class="sxs-lookup"><span data-stu-id="4b87f-382">Units</span></span></th>
<th><span data-ttu-id="4b87f-383">Índice</span><span class="sxs-lookup"><span data-stu-id="4b87f-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-384">CC001</span><span class="sxs-lookup"><span data-stu-id="4b87f-384">CC001</span></span></td>
<td><span data-ttu-id="4b87f-385">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="4b87f-385">HR</span></span></td>
<td><span data-ttu-id="4b87f-386">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-386">10001</span></span></td>
<td><span data-ttu-id="4b87f-387">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-387">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-388">1</span><span class="sxs-lookup"><span data-stu-id="4b87f-388">1</span></span></td>
<td><span data-ttu-id="4b87f-389">10</span><span class="sxs-lookup"><span data-stu-id="4b87f-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b87f-390">La tabla siguiente muestra el resultado cuando los proyectos HR se aplican como base de la asignación.</span><span class="sxs-lookup"><span data-stu-id="4b87f-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b87f-391">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-391">Cost object</span></span></th>
<th><span data-ttu-id="4b87f-392">Magnitud</span><span class="sxs-lookup"><span data-stu-id="4b87f-392">Magnitude</span></span></th>
<th><span data-ttu-id="4b87f-393">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-393">Cost element</span></span></th>
<th><span data-ttu-id="4b87f-394">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="4b87f-394">Allocation factor</span></span></th>
<th><span data-ttu-id="4b87f-395">Importe</span><span class="sxs-lookup"><span data-stu-id="4b87f-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-396">Proy 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-396">Proj 1</span></span></td>
<td><span data-ttu-id="4b87f-397">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-397">Project 1</span></span></td>
<td><span data-ttu-id="4b87f-398">3</span><span class="sxs-lookup"><span data-stu-id="4b87f-398">3</span></span></td>
<td><span data-ttu-id="4b87f-399">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-399">10001</span></span></td>
<td><span data-ttu-id="4b87f-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="4b87f-401">30,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-402">Proy 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-402">Proj 2</span></span></td>
<td><span data-ttu-id="4b87f-403">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-403">Project 2</span></span></td>
<td><span data-ttu-id="4b87f-404">1</span><span class="sxs-lookup"><span data-stu-id="4b87f-404">1</span></span></td>
<td><span data-ttu-id="4b87f-405">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-405">10001</span></span></td>
<td><span data-ttu-id="4b87f-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="4b87f-407">10,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="4b87f-408">Diario</span><span class="sxs-lookup"><span data-stu-id="4b87f-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4b87f-409">Diario</span><span class="sxs-lookup"><span data-stu-id="4b87f-409">Journal</span></span></th>
<th><span data-ttu-id="4b87f-410">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="4b87f-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="4b87f-411">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="4b87f-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="4b87f-412">Versión</span><span class="sxs-lookup"><span data-stu-id="4b87f-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-413">00003</span><span class="sxs-lookup"><span data-stu-id="4b87f-413">00003</span></span></td>
<td><span data-ttu-id="4b87f-414">Diario de cálculo de tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="4b87f-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="4b87f-415">Fiscal</span><span class="sxs-lookup"><span data-stu-id="4b87f-415">Fiscal</span></span></td>
<td><span data-ttu-id="4b87f-416">2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-416">2017</span></span></td>
<td><span data-ttu-id="4b87f-417">Período 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-417">Period 1</span></span></td>
<td><span data-ttu-id="4b87f-418">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="4b87f-419">Entradas de diario (entradas de diario para cálculo de tasas de costes generales)</span><span class="sxs-lookup"><span data-stu-id="4b87f-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4b87f-420">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="4b87f-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="4b87f-421">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-421">Cost object</span></span></th>
<th><span data-ttu-id="4b87f-422">Magnitud</span><span class="sxs-lookup"><span data-stu-id="4b87f-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-423">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b87f-424">Proy 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-424">Proj 1</span></span></td>
<td><span data-ttu-id="4b87f-425">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="4b87f-426">3,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-427">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b87f-428">Proy 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-428">Proj 2</span></span></td>
<td><span data-ttu-id="4b87f-429">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="4b87f-430">1,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="4b87f-431">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="4b87f-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b87f-432">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4b87f-433">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-433">Cost element</span></span></th>
<th><span data-ttu-id="4b87f-434">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4b87f-434">Cost behavior</span></span></th>
<th><span data-ttu-id="4b87f-435">Importe</span><span class="sxs-lookup"><span data-stu-id="4b87f-435">Amount</span></span></th>
<th><span data-ttu-id="4b87f-436">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="4b87f-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="4b87f-437">CC0001</span></span></td>
<td><span data-ttu-id="4b87f-438">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="4b87f-438">HR</span></span></td>
<td><span data-ttu-id="4b87f-439">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-439">10001</span></span></td>
<td><span data-ttu-id="4b87f-440">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-440">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-441">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-441">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-442">-30.00</span></span></td>
<td><span data-ttu-id="4b87f-443">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-444">Proy 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-444">Proj 1</span></span></td>
<td><span data-ttu-id="4b87f-445">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="4b87f-446">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-446">10001</span></span></td>
<td><span data-ttu-id="4b87f-447">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-447">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-448">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-448">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-449">30,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-449">30.00</span></span></td>
<td><span data-ttu-id="4b87f-450">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-451">CC001</span><span class="sxs-lookup"><span data-stu-id="4b87f-451">CC001</span></span></td>
<td><span data-ttu-id="4b87f-452">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="4b87f-452">HR</span></span></td>
<td><span data-ttu-id="4b87f-453">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-453">10001</span></span></td>
<td><span data-ttu-id="4b87f-454">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-454">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-455">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-455">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-456">-10.00</span></span></td>
<td><span data-ttu-id="4b87f-457">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-458">Proy 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-458">Proj 2</span></span></td>
<td><span data-ttu-id="4b87f-459">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="4b87f-460">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-460">10001</span></span></td>
<td><span data-ttu-id="4b87f-461">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-461">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-462">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-462">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-463">10,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-463">10.00</span></span></td>
<td><span data-ttu-id="4b87f-464">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b87f-465">Para obtener más información, consulte [Realizar cálculo de costes generales](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="4b87f-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="4b87f-466">Paso 4: Procese el cálculo de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="4b87f-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="4b87f-467">La asignación es utilizada para asignar el saldo de un objeto de coste a otros objetos de coste aplicando una base de asignación.</span><span class="sxs-lookup"><span data-stu-id="4b87f-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="4b87f-468">Finance and Operations admite el método de asignación recíproco.</span><span class="sxs-lookup"><span data-stu-id="4b87f-468">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="4b87f-469">En el método de asignación recíproco, se reconocen completamente los servicios mutuos que los objetos de coste auxiliar intercambian.</span><span class="sxs-lookup"><span data-stu-id="4b87f-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="4b87f-470">El sistema determina automáticamente el orden correcto para realizar las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="4b87f-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="4b87f-471">El saldo de un objeto de coste se asigna según una única base de asignación.</span><span class="sxs-lookup"><span data-stu-id="4b87f-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="4b87f-472">Las asignaciones entre dimensiones de objetos de coste y sus miembros respectivos se admiten.</span><span class="sxs-lookup"><span data-stu-id="4b87f-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="4b87f-473">El orden de asignación se controla por unidad de control de costes.</span><span class="sxs-lookup"><span data-stu-id="4b87f-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="4b87f-474">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="4b87f-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="4b87f-475">Defina la asignación de costes</span><span class="sxs-lookup"><span data-stu-id="4b87f-475">Define the cost allocation</span></span>

<span data-ttu-id="4b87f-476">A continuación se indica un ejemplo sencillo que explica cómo puede realizar el seguimiento del flujo de coste.</span><span class="sxs-lookup"><span data-stu-id="4b87f-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="4b87f-477">El objeto de coste CC001 HR contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="4b87f-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="4b87f-478">Se crea un miembro de dimensión estadística que se denomina servicios HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="4b87f-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b87f-479">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-479">Cost object</span></span></th>
<th><span data-ttu-id="4b87f-480">Servicios HR</span><span class="sxs-lookup"><span data-stu-id="4b87f-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-481">CC002</span><span class="sxs-lookup"><span data-stu-id="4b87f-481">CC002</span></span></td>
<td><span data-ttu-id="4b87f-482">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4b87f-482">Finance</span></span></td>
<td><span data-ttu-id="4b87f-483">35</span><span class="sxs-lookup"><span data-stu-id="4b87f-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-484">CC003</span><span class="sxs-lookup"><span data-stu-id="4b87f-484">CC003</span></span></td>
<td><span data-ttu-id="4b87f-485">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4b87f-485">Assembly</span></span></td>
<td><span data-ttu-id="4b87f-486">55</span><span class="sxs-lookup"><span data-stu-id="4b87f-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-487">CC004</span><span class="sxs-lookup"><span data-stu-id="4b87f-487">CC004</span></span></td>
<td><span data-ttu-id="4b87f-488">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="4b87f-488">Packaging</span></span></td>
<td><span data-ttu-id="4b87f-489">10</span><span class="sxs-lookup"><span data-stu-id="4b87f-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b87f-490">El objeto de coste CC002 Finanzas contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="4b87f-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="4b87f-491">Se crea un miembro de dimensión estadística que se denomina Finanzas para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="4b87f-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b87f-492">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-492">Cost object</span></span></th>
<th><span data-ttu-id="4b87f-493">Servicios financieros</span><span class="sxs-lookup"><span data-stu-id="4b87f-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-494">CC003</span><span class="sxs-lookup"><span data-stu-id="4b87f-494">CC003</span></span></td>
<td><span data-ttu-id="4b87f-495">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4b87f-495">Assembly</span></span></td>
<td><span data-ttu-id="4b87f-496">65</span><span class="sxs-lookup"><span data-stu-id="4b87f-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-497">CC004</span><span class="sxs-lookup"><span data-stu-id="4b87f-497">CC004</span></span></td>
<td><span data-ttu-id="4b87f-498">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="4b87f-498">Packaging</span></span></td>
<td><span data-ttu-id="4b87f-499">35</span><span class="sxs-lookup"><span data-stu-id="4b87f-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b87f-500">El objeto de coste CC003 Asamblea contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="4b87f-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="4b87f-501">Se crea un miembro de dimensión estadística que se denomina servicios de Asamblea para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="4b87f-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b87f-502">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-502">Cost object</span></span></th>
<th><span data-ttu-id="4b87f-503">Servicios de la asamblea (horas)</span><span class="sxs-lookup"><span data-stu-id="4b87f-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-504">Prod 1</span></span></td>
<td><span data-ttu-id="4b87f-505">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-505">Product 1</span></span></td>
<td><span data-ttu-id="4b87f-506">60</span><span class="sxs-lookup"><span data-stu-id="4b87f-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-507">Prod 2</span></span></td>
<td><span data-ttu-id="4b87f-508">Producto 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-508">Product 2</span></span></td>
<td><span data-ttu-id="4b87f-509">20</span><span class="sxs-lookup"><span data-stu-id="4b87f-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b87f-510">El objeto de coste CC004 Embalaje contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="4b87f-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="4b87f-511">Se crea un miembro de dimensión estadística que se denomina servicios de Embalaje para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="4b87f-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b87f-512">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-512">Cost object</span></span></th>
<th><span data-ttu-id="4b87f-513">Servicios de embalaje (horas)</span><span class="sxs-lookup"><span data-stu-id="4b87f-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-514">Prod 1</span></span></td>
<td><span data-ttu-id="4b87f-515">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-515">Product 1</span></span></td>
<td><span data-ttu-id="4b87f-516">80</span><span class="sxs-lookup"><span data-stu-id="4b87f-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-517">Prod 2</span></span></td>
<td><span data-ttu-id="4b87f-518">Producto 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-518">Product 2</span></span></td>
<td><span data-ttu-id="4b87f-519">15</span><span class="sxs-lookup"><span data-stu-id="4b87f-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="4b87f-520">En Finance and Operations, las medidas estadísticas como las horas de la producción que un producto consume se pueden deducir de los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="4b87f-520">In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="4b87f-521">Para obtener más información, vea [Plantilla de proveedor de medidas estadísticas](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="4b87f-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="4b87f-522">La tabla siguiente muestra el resultado cuando se aplican los servicios de HR como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="4b87f-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b87f-523">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-523">Cost object</span></span></th>
<th><span data-ttu-id="4b87f-524">Magnitud</span><span class="sxs-lookup"><span data-stu-id="4b87f-524">Magnitude</span></span></th>
<th><span data-ttu-id="4b87f-525">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="4b87f-525">Allocation factor</span></span></th>
<th><span data-ttu-id="4b87f-526">Importe</span><span class="sxs-lookup"><span data-stu-id="4b87f-526">Amount</span></span></th>
<th><span data-ttu-id="4b87f-527">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4b87f-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-528">CC002</span><span class="sxs-lookup"><span data-stu-id="4b87f-528">CC002</span></span></td>
<td><span data-ttu-id="4b87f-529">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4b87f-529">Finance</span></span></td>
<td><span data-ttu-id="4b87f-530">35</span><span class="sxs-lookup"><span data-stu-id="4b87f-530">35</span></span></td>
<td><span data-ttu-id="4b87f-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="4b87f-532">175.00</span><span class="sxs-lookup"><span data-stu-id="4b87f-532">175.00</span></span></td>
<td><span data-ttu-id="4b87f-533">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-534">CC003</span><span class="sxs-lookup"><span data-stu-id="4b87f-534">CC003</span></span></td>
<td><span data-ttu-id="4b87f-535">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4b87f-535">Assembly</span></span></td>
<td><span data-ttu-id="4b87f-536">55</span><span class="sxs-lookup"><span data-stu-id="4b87f-536">55</span></span></td>
<td><span data-ttu-id="4b87f-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="4b87f-538">275.00</span><span class="sxs-lookup"><span data-stu-id="4b87f-538">275.00</span></span></td>
<td><span data-ttu-id="4b87f-539">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-540">CC004</span><span class="sxs-lookup"><span data-stu-id="4b87f-540">CC004</span></span></td>
<td><span data-ttu-id="4b87f-541">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="4b87f-541">Packaging</span></span></td>
<td><span data-ttu-id="4b87f-542">10</span><span class="sxs-lookup"><span data-stu-id="4b87f-542">10</span></span></td>
<td><span data-ttu-id="4b87f-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="4b87f-544">50,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-544">50.00</span></span></td>
<td><span data-ttu-id="4b87f-545">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-546">CC002</span><span class="sxs-lookup"><span data-stu-id="4b87f-546">CC002</span></span></td>
<td><span data-ttu-id="4b87f-547">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4b87f-547">Finance</span></span></td>
<td><span data-ttu-id="4b87f-548">35</span><span class="sxs-lookup"><span data-stu-id="4b87f-548">35</span></span></td>
<td><span data-ttu-id="4b87f-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="4b87f-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="4b87f-550">436.00</span><span class="sxs-lookup"><span data-stu-id="4b87f-550">436.00</span></span></td>
<td><span data-ttu-id="4b87f-551">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-552">CC003</span><span class="sxs-lookup"><span data-stu-id="4b87f-552">CC003</span></span></td>
<td><span data-ttu-id="4b87f-553">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4b87f-553">Assembly</span></span></td>
<td><span data-ttu-id="4b87f-554">55</span><span class="sxs-lookup"><span data-stu-id="4b87f-554">55</span></span></td>
<td><span data-ttu-id="4b87f-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="4b87f-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="4b87f-556">685.14</span><span class="sxs-lookup"><span data-stu-id="4b87f-556">685.14</span></span></td>
<td><span data-ttu-id="4b87f-557">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-558">CC004</span><span class="sxs-lookup"><span data-stu-id="4b87f-558">CC004</span></span></td>
<td><span data-ttu-id="4b87f-559">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="4b87f-559">Packaging</span></span></td>
<td><span data-ttu-id="4b87f-560">10</span><span class="sxs-lookup"><span data-stu-id="4b87f-560">10</span></span></td>
<td><span data-ttu-id="4b87f-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="4b87f-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="4b87f-562">124.57</span><span class="sxs-lookup"><span data-stu-id="4b87f-562">124.57</span></span></td>
<td><span data-ttu-id="4b87f-563">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b87f-564">La tabla siguiente muestra el resultado cuando se aplican los servicios de Finanzas como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="4b87f-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b87f-565">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-565">Cost object</span></span></th>
<th><span data-ttu-id="4b87f-566">Magnitud</span><span class="sxs-lookup"><span data-stu-id="4b87f-566">Magnitude</span></span></th>
<th><span data-ttu-id="4b87f-567">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="4b87f-567">Allocation factor</span></span></th>
<th><span data-ttu-id="4b87f-568">Importe</span><span class="sxs-lookup"><span data-stu-id="4b87f-568">Amount</span></span></th>
<th><span data-ttu-id="4b87f-569">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4b87f-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-570">CC003</span><span class="sxs-lookup"><span data-stu-id="4b87f-570">CC003</span></span></td>
<td><span data-ttu-id="4b87f-571">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4b87f-571">Assembly</span></span></td>
<td><span data-ttu-id="4b87f-572">65</span><span class="sxs-lookup"><span data-stu-id="4b87f-572">65</span></span></td>
<td><span data-ttu-id="4b87f-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="4b87f-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="4b87f-574">438.75</span><span class="sxs-lookup"><span data-stu-id="4b87f-574">438.75</span></span></td>
<td><span data-ttu-id="4b87f-575">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-576">CC004</span><span class="sxs-lookup"><span data-stu-id="4b87f-576">CC004</span></span></td>
<td><span data-ttu-id="4b87f-577">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="4b87f-577">Packaging</span></span></td>
<td><span data-ttu-id="4b87f-578">35</span><span class="sxs-lookup"><span data-stu-id="4b87f-578">35</span></span></td>
<td><span data-ttu-id="4b87f-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="4b87f-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="4b87f-580">236.25</span><span class="sxs-lookup"><span data-stu-id="4b87f-580">236.25</span></span></td>
<td><span data-ttu-id="4b87f-581">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-582">CC003</span><span class="sxs-lookup"><span data-stu-id="4b87f-582">CC003</span></span></td>
<td><span data-ttu-id="4b87f-583">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4b87f-583">Assembly</span></span></td>
<td><span data-ttu-id="4b87f-584">65</span><span class="sxs-lookup"><span data-stu-id="4b87f-584">65</span></span></td>
<td><span data-ttu-id="4b87f-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="4b87f-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="4b87f-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="4b87f-586">5,297.69</span></span></td>
<td><span data-ttu-id="4b87f-587">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-588">CC004</span><span class="sxs-lookup"><span data-stu-id="4b87f-588">CC004</span></span></td>
<td><span data-ttu-id="4b87f-589">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="4b87f-589">Packaging</span></span></td>
<td><span data-ttu-id="4b87f-590">35</span><span class="sxs-lookup"><span data-stu-id="4b87f-590">35</span></span></td>
<td><span data-ttu-id="4b87f-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="4b87f-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="4b87f-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="4b87f-592">2,852.60</span></span></td>
<td><span data-ttu-id="4b87f-593">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b87f-594">La tabla siguiente muestra el resultado cuando se aplican los servicios de Asamblea como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="4b87f-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b87f-595">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-595">Cost object</span></span></th>
<th><span data-ttu-id="4b87f-596">Magnitud</span><span class="sxs-lookup"><span data-stu-id="4b87f-596">Magnitude</span></span></th>
<th><span data-ttu-id="4b87f-597">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="4b87f-597">Allocation factor</span></span></th>
<th><span data-ttu-id="4b87f-598">Importe</span><span class="sxs-lookup"><span data-stu-id="4b87f-598">Amount</span></span></th>
<th><span data-ttu-id="4b87f-599">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4b87f-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-600">Prod 1</span></span></td>
<td><span data-ttu-id="4b87f-601">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-601">Product 1</span></span></td>
<td><span data-ttu-id="4b87f-602">60</span><span class="sxs-lookup"><span data-stu-id="4b87f-602">60</span></span></td>
<td><span data-ttu-id="4b87f-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="4b87f-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="4b87f-604">535.31</span><span class="sxs-lookup"><span data-stu-id="4b87f-604">535.31</span></span></td>
<td><span data-ttu-id="4b87f-605">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-606">Prod 2</span></span></td>
<td><span data-ttu-id="4b87f-607">Producto 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-607">Product 2</span></span></td>
<td><span data-ttu-id="4b87f-608">20</span><span class="sxs-lookup"><span data-stu-id="4b87f-608">20</span></span></td>
<td><span data-ttu-id="4b87f-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="4b87f-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="4b87f-610">178.44</span><span class="sxs-lookup"><span data-stu-id="4b87f-610">178.44</span></span></td>
<td><span data-ttu-id="4b87f-611">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-612">Prod 1</span></span></td>
<td><span data-ttu-id="4b87f-613">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-613">Product 1</span></span></td>
<td><span data-ttu-id="4b87f-614">60</span><span class="sxs-lookup"><span data-stu-id="4b87f-614">60</span></span></td>
<td><span data-ttu-id="4b87f-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="4b87f-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="4b87f-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="4b87f-616">4,487.12</span></span></td>
<td><span data-ttu-id="4b87f-617">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-618">Prod 2</span></span></td>
<td><span data-ttu-id="4b87f-619">Producto 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-619">Product 2</span></span></td>
<td><span data-ttu-id="4b87f-620">20</span><span class="sxs-lookup"><span data-stu-id="4b87f-620">20</span></span></td>
<td><span data-ttu-id="4b87f-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="4b87f-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="4b87f-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="4b87f-622">1,495.71</span></span></td>
<td><span data-ttu-id="4b87f-623">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4b87f-624">La tabla siguiente muestra el resultado cuando se aplican los servicios de Embalaje como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="4b87f-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b87f-625">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-625">Cost object</span></span></th>
<th><span data-ttu-id="4b87f-626">Magnitud</span><span class="sxs-lookup"><span data-stu-id="4b87f-626">Magnitude</span></span></th>
<th><span data-ttu-id="4b87f-627">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="4b87f-627">Allocation factor</span></span></th>
<th><span data-ttu-id="4b87f-628">Importe</span><span class="sxs-lookup"><span data-stu-id="4b87f-628">Amount</span></span></th>
<th><span data-ttu-id="4b87f-629">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4b87f-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-630">Prod 1</span></span></td>
<td><span data-ttu-id="4b87f-631">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-631">Product 1</span></span></td>
<td><span data-ttu-id="4b87f-632">80</span><span class="sxs-lookup"><span data-stu-id="4b87f-632">80</span></span></td>
<td><span data-ttu-id="4b87f-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="4b87f-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="4b87f-634">241.05</span><span class="sxs-lookup"><span data-stu-id="4b87f-634">241.05</span></span></td>
<td><span data-ttu-id="4b87f-635">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-636">Prod 2</span></span></td>
<td><span data-ttu-id="4b87f-637">Producto 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-637">Product 2</span></span></td>
<td><span data-ttu-id="4b87f-638">15</span><span class="sxs-lookup"><span data-stu-id="4b87f-638">15</span></span></td>
<td><span data-ttu-id="4b87f-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="4b87f-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="4b87f-640">45.20</span><span class="sxs-lookup"><span data-stu-id="4b87f-640">45.20</span></span></td>
<td><span data-ttu-id="4b87f-641">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-642">Prod 1</span></span></td>
<td><span data-ttu-id="4b87f-643">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-643">Product 1</span></span></td>
<td><span data-ttu-id="4b87f-644">80</span><span class="sxs-lookup"><span data-stu-id="4b87f-644">80</span></span></td>
<td><span data-ttu-id="4b87f-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="4b87f-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="4b87f-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="4b87f-646">2,507.09</span></span></td>
<td><span data-ttu-id="4b87f-647">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-648">Prod 2</span></span></td>
<td><span data-ttu-id="4b87f-649">Producto 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-649">Product 2</span></span></td>
<td><span data-ttu-id="4b87f-650">15</span><span class="sxs-lookup"><span data-stu-id="4b87f-650">15</span></span></td>
<td><span data-ttu-id="4b87f-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="4b87f-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="4b87f-652">470.08</span><span class="sxs-lookup"><span data-stu-id="4b87f-652">470.08</span></span></td>
<td><span data-ttu-id="4b87f-653">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="4b87f-654">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="4b87f-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4b87f-655">Diario</span><span class="sxs-lookup"><span data-stu-id="4b87f-655">Journal</span></span></th>
<th><span data-ttu-id="4b87f-656">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="4b87f-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="4b87f-657">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="4b87f-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="4b87f-658">Versión</span><span class="sxs-lookup"><span data-stu-id="4b87f-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-659">00004</span><span class="sxs-lookup"><span data-stu-id="4b87f-659">00004</span></span></td>
<td><span data-ttu-id="4b87f-660">Diario de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="4b87f-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="4b87f-661">Fiscal</span><span class="sxs-lookup"><span data-stu-id="4b87f-661">Fiscal</span></span></td>
<td><span data-ttu-id="4b87f-662">2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-662">2017</span></span></td>
<td><span data-ttu-id="4b87f-663">Período 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-663">Period 1</span></span></td>
<td><span data-ttu-id="4b87f-664">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="4b87f-665">Líneas de diario</span><span class="sxs-lookup"><span data-stu-id="4b87f-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4b87f-666">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="4b87f-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="4b87f-667">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4b87f-668">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-668">Cost element</span></span></th>
<th><span data-ttu-id="4b87f-669">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4b87f-669">Cost behavior</span></span></th>
<th><span data-ttu-id="4b87f-670">Importe</span><span class="sxs-lookup"><span data-stu-id="4b87f-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-671">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b87f-672">CC001</span><span class="sxs-lookup"><span data-stu-id="4b87f-672">CC001</span></span></td>
<td><span data-ttu-id="4b87f-673">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="4b87f-673">HR</span></span></td>
<td><span data-ttu-id="4b87f-674">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-674">10001</span></span></td>
<td><span data-ttu-id="4b87f-675">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-675">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-676">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-676">Fixed cost</span></span></td>
<td><span data-ttu-id="4b87f-677">500,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-678">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b87f-679">CC001</span><span class="sxs-lookup"><span data-stu-id="4b87f-679">CC001</span></span></td>
<td><span data-ttu-id="4b87f-680">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="4b87f-680">HR</span></span></td>
<td><span data-ttu-id="4b87f-681">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-681">10001</span></span></td>
<td><span data-ttu-id="4b87f-682">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-682">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-683">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-683">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="4b87f-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-685">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b87f-686">CC002</span><span class="sxs-lookup"><span data-stu-id="4b87f-686">CC002</span></span></td>
<td><span data-ttu-id="4b87f-687">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4b87f-687">Finance</span></span></td>
<td><span data-ttu-id="4b87f-688">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-688">10001</span></span></td>
<td><span data-ttu-id="4b87f-689">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-689">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-690">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-690">Fixed cost</span></span></td>
<td><span data-ttu-id="4b87f-691">675.00</span><span class="sxs-lookup"><span data-stu-id="4b87f-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-692">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b87f-693">CC002</span><span class="sxs-lookup"><span data-stu-id="4b87f-693">CC002</span></span></td>
<td><span data-ttu-id="4b87f-694">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4b87f-694">Finance</span></span></td>
<td><span data-ttu-id="4b87f-695">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-695">10001</span></span></td>
<td><span data-ttu-id="4b87f-696">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-696">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-697">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-697">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="4b87f-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-699">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b87f-700">CC003</span><span class="sxs-lookup"><span data-stu-id="4b87f-700">CC003</span></span></td>
<td><span data-ttu-id="4b87f-701">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4b87f-701">Assembly</span></span></td>
<td><span data-ttu-id="4b87f-702">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-702">10001</span></span></td>
<td><span data-ttu-id="4b87f-703">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-703">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-704">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-704">Fixed cost</span></span></td>
<td><span data-ttu-id="4b87f-705">713.75</span><span class="sxs-lookup"><span data-stu-id="4b87f-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-706">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b87f-707">CC003</span><span class="sxs-lookup"><span data-stu-id="4b87f-707">CC003</span></span></td>
<td><span data-ttu-id="4b87f-708">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4b87f-708">Assembly</span></span></td>
<td><span data-ttu-id="4b87f-709">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-709">10001</span></span></td>
<td><span data-ttu-id="4b87f-710">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-710">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-711">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-711">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="4b87f-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-713">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b87f-714">CC003</span><span class="sxs-lookup"><span data-stu-id="4b87f-714">CC003</span></span></td>
<td><span data-ttu-id="4b87f-715">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="4b87f-715">Packaging</span></span></td>
<td><span data-ttu-id="4b87f-716">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-716">10001</span></span></td>
<td><span data-ttu-id="4b87f-717">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-717">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-718">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-718">Fixed cost</span></span></td>
<td><span data-ttu-id="4b87f-719">286.25</span><span class="sxs-lookup"><span data-stu-id="4b87f-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-720">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b87f-721">CC003</span><span class="sxs-lookup"><span data-stu-id="4b87f-721">CC003</span></span></td>
<td><span data-ttu-id="4b87f-722">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="4b87f-722">Packaging</span></span></td>
<td><span data-ttu-id="4b87f-723">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-723">10001</span></span></td>
<td><span data-ttu-id="4b87f-724">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-724">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-725">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-725">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="4b87f-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-727">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b87f-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-728">Prod 1</span></span></td>
<td><span data-ttu-id="4b87f-729">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-729">Product 1</span></span></td>
<td><span data-ttu-id="4b87f-730">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-730">10001</span></span></td>
<td><span data-ttu-id="4b87f-731">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-731">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-732">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-732">Fixed cost</span></span></td>
<td><span data-ttu-id="4b87f-733">776.36</span><span class="sxs-lookup"><span data-stu-id="4b87f-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-734">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b87f-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-735">Prod 1</span></span></td>
<td><span data-ttu-id="4b87f-736">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-736">Product 1</span></span></td>
<td><span data-ttu-id="4b87f-737">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-737">10001</span></span></td>
<td><span data-ttu-id="4b87f-738">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-738">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-739">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-739">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="4b87f-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-741">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b87f-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-742">Prod 2</span></span></td>
<td><span data-ttu-id="4b87f-743">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-743">Product 1</span></span></td>
<td><span data-ttu-id="4b87f-744">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-744">10001</span></span></td>
<td><span data-ttu-id="4b87f-745">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-745">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-746">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-746">Fixed cost</span></span></td>
<td><span data-ttu-id="4b87f-747">223.64</span><span class="sxs-lookup"><span data-stu-id="4b87f-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-748">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="4b87f-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-749">Prod 2</span></span></td>
<td><span data-ttu-id="4b87f-750">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-750">Product 1</span></span></td>
<td><span data-ttu-id="4b87f-751">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-751">10001</span></span></td>
<td><span data-ttu-id="4b87f-752">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-752">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-753">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-753">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="4b87f-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="4b87f-755">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="4b87f-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="4b87f-756">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="4b87f-757">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-757">Cost element</span></span></th>
<th><span data-ttu-id="4b87f-758">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="4b87f-758">Cost behavior</span></span></th>
<th><span data-ttu-id="4b87f-759">Importe</span><span class="sxs-lookup"><span data-stu-id="4b87f-759">Amount</span></span></th>
<th><span data-ttu-id="4b87f-760">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="4b87f-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4b87f-761">CC001</span><span class="sxs-lookup"><span data-stu-id="4b87f-761">CC001</span></span></td>
<td><span data-ttu-id="4b87f-762">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="4b87f-762">HR</span></span></td>
<td><span data-ttu-id="4b87f-763">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-763">10001</span></span></td>
<td><span data-ttu-id="4b87f-764">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-764">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-765">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-765">Fixed cost</span></span></td>
<td><span data-ttu-id="4b87f-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-766">-500.00</span></span></td>
<td><span data-ttu-id="4b87f-767">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-768">CC002</span><span class="sxs-lookup"><span data-stu-id="4b87f-768">CC002</span></span></td>
<td><span data-ttu-id="4b87f-769">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4b87f-769">Finance</span></span></td>
<td><span data-ttu-id="4b87f-770">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-770">10001</span></span></td>
<td><span data-ttu-id="4b87f-771">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-771">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-772">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-772">Fixed cost</span></span></td>
<td><span data-ttu-id="4b87f-773">175.00</span><span class="sxs-lookup"><span data-stu-id="4b87f-773">175.00</span></span></td>
<td><span data-ttu-id="4b87f-774">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-775">CC003</span><span class="sxs-lookup"><span data-stu-id="4b87f-775">CC003</span></span></td>
<td><span data-ttu-id="4b87f-776">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4b87f-776">Assembly</span></span></td>
<td><span data-ttu-id="4b87f-777">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-777">10001</span></span></td>
<td><span data-ttu-id="4b87f-778">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-778">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-779">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-779">Fixed cost</span></span></td>
<td><span data-ttu-id="4b87f-780">275.00</span><span class="sxs-lookup"><span data-stu-id="4b87f-780">275.00</span></span></td>
<td><span data-ttu-id="4b87f-781">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-782">CC004</span><span class="sxs-lookup"><span data-stu-id="4b87f-782">CC004</span></span></td>
<td><span data-ttu-id="4b87f-783">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="4b87f-783">Packaging</span></span></td>
<td><span data-ttu-id="4b87f-784">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-784">10001</span></span></td>
<td><span data-ttu-id="4b87f-785">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-785">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-786">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-786">Fixed cost</span></span></td>
<td><span data-ttu-id="4b87f-787">50,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-787">50,00</span></span></td>
<td><span data-ttu-id="4b87f-788">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-789">CC001</span><span class="sxs-lookup"><span data-stu-id="4b87f-789">CC001</span></span></td>
<td><span data-ttu-id="4b87f-790">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="4b87f-790">HR</span></span></td>
<td><span data-ttu-id="4b87f-791">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-791">10001</span></span></td>
<td><span data-ttu-id="4b87f-792">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-792">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-793">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-793">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="4b87f-794">-1,245.71</span></span></td>
<td><span data-ttu-id="4b87f-795">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-796">CC002</span><span class="sxs-lookup"><span data-stu-id="4b87f-796">CC002</span></span></td>
<td><span data-ttu-id="4b87f-797">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4b87f-797">Finance</span></span></td>
<td><span data-ttu-id="4b87f-798">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-798">10001</span></span></td>
<td><span data-ttu-id="4b87f-799">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-799">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-800">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-800">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-801">436.00</span><span class="sxs-lookup"><span data-stu-id="4b87f-801">436.00</span></span></td>
<td><span data-ttu-id="4b87f-802">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-803">CC003</span><span class="sxs-lookup"><span data-stu-id="4b87f-803">CC003</span></span></td>
<td><span data-ttu-id="4b87f-804">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4b87f-804">Assembly</span></span></td>
<td><span data-ttu-id="4b87f-805">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-805">10001</span></span></td>
<td><span data-ttu-id="4b87f-806">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-806">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-807">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-807">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-808">685.14</span><span class="sxs-lookup"><span data-stu-id="4b87f-808">685.14</span></span></td>
<td><span data-ttu-id="4b87f-809">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-810">CC004</span><span class="sxs-lookup"><span data-stu-id="4b87f-810">CC004</span></span></td>
<td><span data-ttu-id="4b87f-811">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="4b87f-811">Packaging</span></span></td>
<td><span data-ttu-id="4b87f-812">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-812">10001</span></span></td>
<td><span data-ttu-id="4b87f-813">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-813">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-814">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-814">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-815">124.57</span><span class="sxs-lookup"><span data-stu-id="4b87f-815">124.57</span></span></td>
<td><span data-ttu-id="4b87f-816">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-817">CC002</span><span class="sxs-lookup"><span data-stu-id="4b87f-817">CC002</span></span></td>
<td><span data-ttu-id="4b87f-818">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4b87f-818">Finance</span></span></td>
<td><span data-ttu-id="4b87f-819">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-819">10001</span></span></td>
<td><span data-ttu-id="4b87f-820">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-820">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-821">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-821">Fixed cost</span></span></td>
<td><span data-ttu-id="4b87f-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-822">-675.00</span></span></td>
<td><span data-ttu-id="4b87f-823">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-824">CC003</span><span class="sxs-lookup"><span data-stu-id="4b87f-824">CC003</span></span></td>
<td><span data-ttu-id="4b87f-825">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4b87f-825">Assembly</span></span></td>
<td><span data-ttu-id="4b87f-826">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-826">10001</span></span></td>
<td><span data-ttu-id="4b87f-827">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-827">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-828">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-828">Fixed cost</span></span></td>
<td><span data-ttu-id="4b87f-829">438.75</span><span class="sxs-lookup"><span data-stu-id="4b87f-829">438.75</span></span></td>
<td><span data-ttu-id="4b87f-830">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-831">CC004</span><span class="sxs-lookup"><span data-stu-id="4b87f-831">CC004</span></span></td>
<td><span data-ttu-id="4b87f-832">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="4b87f-832">Packaging</span></span></td>
<td><span data-ttu-id="4b87f-833">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-833">10001</span></span></td>
<td><span data-ttu-id="4b87f-834">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-834">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-835">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-835">Fixed cost</span></span></td>
<td><span data-ttu-id="4b87f-836">236.25</span><span class="sxs-lookup"><span data-stu-id="4b87f-836">236.25</span></span></td>
<td><span data-ttu-id="4b87f-837">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-838">CC002</span><span class="sxs-lookup"><span data-stu-id="4b87f-838">CC002</span></span></td>
<td><span data-ttu-id="4b87f-839">Finanzas</span><span class="sxs-lookup"><span data-stu-id="4b87f-839">Finance</span></span></td>
<td><span data-ttu-id="4b87f-840">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-840">10001</span></span></td>
<td><span data-ttu-id="4b87f-841">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-841">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-842">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-842">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="4b87f-843">-8,150.29</span></span></td>
<td><span data-ttu-id="4b87f-844">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-845">CC003</span><span class="sxs-lookup"><span data-stu-id="4b87f-845">CC003</span></span></td>
<td><span data-ttu-id="4b87f-846">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4b87f-846">Assembly</span></span></td>
<td><span data-ttu-id="4b87f-847">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-847">10001</span></span></td>
<td><span data-ttu-id="4b87f-848">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-848">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-849">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-849">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="4b87f-850">5,297.69</span></span></td>
<td><span data-ttu-id="4b87f-851">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-852">CC004</span><span class="sxs-lookup"><span data-stu-id="4b87f-852">CC004</span></span></td>
<td><span data-ttu-id="4b87f-853">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="4b87f-853">Packaging</span></span></td>
<td><span data-ttu-id="4b87f-854">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-854">10001</span></span></td>
<td><span data-ttu-id="4b87f-855">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-855">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-856">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-856">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="4b87f-857">2,852.60</span></span></td>
<td><span data-ttu-id="4b87f-858">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-859">CC003</span><span class="sxs-lookup"><span data-stu-id="4b87f-859">CC003</span></span></td>
<td><span data-ttu-id="4b87f-860">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4b87f-860">Assembly</span></span></td>
<td><span data-ttu-id="4b87f-861">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-861">10001</span></span></td>
<td><span data-ttu-id="4b87f-862">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-862">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-863">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-863">Fixed cost</span></span></td>
<td><span data-ttu-id="4b87f-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="4b87f-864">-713.75</span></span></td>
<td><span data-ttu-id="4b87f-865">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-866">Prod 1</span></span></td>
<td><span data-ttu-id="4b87f-867">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-867">Product 1</span></span></td>
<td><span data-ttu-id="4b87f-868">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-868">10001</span></span></td>
<td><span data-ttu-id="4b87f-869">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-869">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-870">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-870">Fixed cost</span></span></td>
<td><span data-ttu-id="4b87f-871">535.31</span><span class="sxs-lookup"><span data-stu-id="4b87f-871">535.31</span></span></td>
<td><span data-ttu-id="4b87f-872">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-873">Prod 2</span></span></td>
<td><span data-ttu-id="4b87f-874">Producto 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-874">Product 2</span></span></td>
<td><span data-ttu-id="4b87f-875">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-875">10001</span></span></td>
<td><span data-ttu-id="4b87f-876">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-876">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-877">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-877">Fixed cost</span></span></td>
<td><span data-ttu-id="4b87f-878">178.44</span><span class="sxs-lookup"><span data-stu-id="4b87f-878">178.44</span></span></td>
<td><span data-ttu-id="4b87f-879">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-880">CC003</span><span class="sxs-lookup"><span data-stu-id="4b87f-880">CC003</span></span></td>
<td><span data-ttu-id="4b87f-881">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4b87f-881">Assembly</span></span></td>
<td><span data-ttu-id="4b87f-882">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-882">10001</span></span></td>
<td><span data-ttu-id="4b87f-883">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-883">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-884">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-884">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="4b87f-885">-5,982.83</span></span></td>
<td><span data-ttu-id="4b87f-886">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-887">Prod 1</span></span></td>
<td><span data-ttu-id="4b87f-888">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-888">Product 1</span></span></td>
<td><span data-ttu-id="4b87f-889">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-889">10001</span></span></td>
<td><span data-ttu-id="4b87f-890">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-890">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-891">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-891">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="4b87f-892">4,487.12</span></span></td>
<td><span data-ttu-id="4b87f-893">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-894">Prod 2</span></span></td>
<td><span data-ttu-id="4b87f-895">Producto 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-895">Product 2</span></span></td>
<td><span data-ttu-id="4b87f-896">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-896">10001</span></span></td>
<td><span data-ttu-id="4b87f-897">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-897">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-898">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-898">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="4b87f-899">1,495.71</span></span></td>
<td><span data-ttu-id="4b87f-900">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-901">CC003</span><span class="sxs-lookup"><span data-stu-id="4b87f-901">CC003</span></span></td>
<td><span data-ttu-id="4b87f-902">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4b87f-902">Assembly</span></span></td>
<td><span data-ttu-id="4b87f-903">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-903">10001</span></span></td>
<td><span data-ttu-id="4b87f-904">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-904">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-905">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-905">Fixed cost</span></span></td>
<td><span data-ttu-id="4b87f-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="4b87f-906">-286.25</span></span></td>
<td><span data-ttu-id="4b87f-907">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-908">Prod 1</span></span></td>
<td><span data-ttu-id="4b87f-909">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-909">Product 1</span></span></td>
<td><span data-ttu-id="4b87f-910">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-910">10001</span></span></td>
<td><span data-ttu-id="4b87f-911">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-911">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-912">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-912">Fixed cost</span></span></td>
<td><span data-ttu-id="4b87f-913">241.05</span><span class="sxs-lookup"><span data-stu-id="4b87f-913">241.05</span></span></td>
<td><span data-ttu-id="4b87f-914">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-915">Prod 2</span></span></td>
<td><span data-ttu-id="4b87f-916">Producto 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-916">Product 2</span></span></td>
<td><span data-ttu-id="4b87f-917">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-917">10001</span></span></td>
<td><span data-ttu-id="4b87f-918">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-918">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-919">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-919">Fixed cost</span></span></td>
<td><span data-ttu-id="4b87f-920">45.20</span><span class="sxs-lookup"><span data-stu-id="4b87f-920">45.20</span></span></td>
<td><span data-ttu-id="4b87f-921">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-922">CC003</span><span class="sxs-lookup"><span data-stu-id="4b87f-922">CC003</span></span></td>
<td><span data-ttu-id="4b87f-923">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="4b87f-923">Assembly</span></span></td>
<td><span data-ttu-id="4b87f-924">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-924">10001</span></span></td>
<td><span data-ttu-id="4b87f-925">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-925">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-926">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-926">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="4b87f-927">-2,977.17</span></span></td>
<td><span data-ttu-id="4b87f-928">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-929">Prod 1</span></span></td>
<td><span data-ttu-id="4b87f-930">Producto 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-930">Product 1</span></span></td>
<td><span data-ttu-id="4b87f-931">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-931">10001</span></span></td>
<td><span data-ttu-id="4b87f-932">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-932">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-933">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-933">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="4b87f-934">2,507.09</span></span></td>
<td><span data-ttu-id="4b87f-935">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4b87f-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-936">Prod 2</span></span></td>
<td><span data-ttu-id="4b87f-937">Producto 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-937">Product 2</span></span></td>
<td><span data-ttu-id="4b87f-938">10001</span><span class="sxs-lookup"><span data-stu-id="4b87f-938">10001</span></span></td>
<td><span data-ttu-id="4b87f-939">Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-939">Electricity</span></span></td>
<td><span data-ttu-id="4b87f-940">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-940">Variable cost</span></span></td>
<td><span data-ttu-id="4b87f-941">470.08</span><span class="sxs-lookup"><span data-stu-id="4b87f-941">470.08</span></span></td>
<td><span data-ttu-id="4b87f-942">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="4b87f-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="4b87f-943">Conclusión</span><span class="sxs-lookup"><span data-stu-id="4b87f-943">Conclusion</span></span>
<span data-ttu-id="4b87f-944">En la contabilidad financiera, un coste de 10.000,00 para electricidad se envía a un identificador ficticio de centro de coste.</span><span class="sxs-lookup"><span data-stu-id="4b87f-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="4b87f-945">Por lo tanto, los contables de coste sabrán que este coste se debe asignar.</span><span class="sxs-lookup"><span data-stu-id="4b87f-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="4b87f-946">En contabilidad de costes, los costes fluyen en las unidades organizativas y los niveles en función de las directivas y las reglas que se aplican.</span><span class="sxs-lookup"><span data-stu-id="4b87f-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="4b87f-947">Cada coste se ha asociado con una base de asignación que proporciona la mejor evaluación para la asignación de costes.</span><span class="sxs-lookup"><span data-stu-id="4b87f-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="4b87f-948">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="4b87f-949">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="4b87f-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="4b87f-950">Total</span><span class="sxs-lookup"><span data-stu-id="4b87f-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="4b87f-951">CC099</span><span class="sxs-lookup"><span data-stu-id="4b87f-951">CC099</span></span></th>
<th><span data-ttu-id="4b87f-952">CC001</span><span class="sxs-lookup"><span data-stu-id="4b87f-952">CC001</span></span></th>
<th><span data-ttu-id="4b87f-953">CC002</span><span class="sxs-lookup"><span data-stu-id="4b87f-953">CC002</span></span></th>
<th><span data-ttu-id="4b87f-954">CC003</span><span class="sxs-lookup"><span data-stu-id="4b87f-954">CC003</span></span></th>
<th><span data-ttu-id="4b87f-955">CC004</span><span class="sxs-lookup"><span data-stu-id="4b87f-955">CC004</span></span></th>
<th><span data-ttu-id="4b87f-956">Proy 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-956">Proj 1</span></span></th>
<th><span data-ttu-id="4b87f-957">Proy 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-957">Proj 2</span></span></th>
<th><span data-ttu-id="4b87f-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="4b87f-958">Prod 1</span></span></th>
<th><span data-ttu-id="4b87f-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="4b87f-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="4b87f-960">10001 Electricidad</span><span class="sxs-lookup"><span data-stu-id="4b87f-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="4b87f-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="4b87f-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="4b87f-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="4b87f-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="4b87f-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="4b87f-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="4b87f-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="4b87f-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="4b87f-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="4b87f-970">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="4b87f-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-971">0,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="4b87f-972">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="4b87f-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-973">0,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-974">0,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-975">0,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-976">0,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-977">0,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-978">776.36</span><span class="sxs-lookup"><span data-stu-id="4b87f-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-979">223.64</span><span class="sxs-lookup"><span data-stu-id="4b87f-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="4b87f-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="4b87f-981">Coste variable</span><span class="sxs-lookup"><span data-stu-id="4b87f-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-982">000</span><span class="sxs-lookup"><span data-stu-id="4b87f-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-983">0,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-984">0,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-985">0,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-986">0,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-987">30,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-988">10,00</span><span class="sxs-lookup"><span data-stu-id="4b87f-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="4b87f-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="4b87f-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="4b87f-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="4b87f-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="4b87f-992">Este tema muestra cómo un artículo de costes principales, 10001 Electricidad, fluye por los objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="4b87f-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="4b87f-993">Por tanto, estos gastos generales se asignan al nivel más bajo de la organización.</span><span class="sxs-lookup"><span data-stu-id="4b87f-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="4b87f-994">Es decir, los objetos de coste del nivel más bajo son los que soportan el coste.</span><span class="sxs-lookup"><span data-stu-id="4b87f-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="4b87f-995">Si necesita un flujo visual del coste entre los objetos de coste, puede usar las reglas de directivas de acumulación de costes para visualizar el flujo del coste.</span><span class="sxs-lookup"><span data-stu-id="4b87f-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="4b87f-996">Para obtener más información, consulte [Acumulación de costes](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="4b87f-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>



