---
title: "Cálculo de costes generales"
description: "Este tema describe los procesos típicos para calcular y asignar costes generales."
author: AndersGirke
manager: AnnBe
ms.date: 10/04/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
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
ms.translationtype: HT
ms.sourcegitcommit: 12ae99c15bafcd9cc08b30903fe3f251f446b17d
ms.openlocfilehash: 4de705324ac497cfb11fae3dadc6f57d038fd0b5
ms.contentlocale: es-es
ms.lasthandoff: 10/05/2018

---

# <a name="overhead-calculation"></a><span data-ttu-id="77f8e-103">Cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="77f8e-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="77f8e-104">Este tema describe los procesos típicos para calcular y asignar costes generales.</span><span class="sxs-lookup"><span data-stu-id="77f8e-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="77f8e-105">Definición del término</span><span class="sxs-lookup"><span data-stu-id="77f8e-105">Term definition</span></span>
---------------

<span data-ttu-id="77f8e-106">Los costes generales son costes que se contraen para dirigir un negocio, pero que no pueden ser atribuidos directamente a ninguna actividad empresarial, productos, o servicio específicos.</span><span class="sxs-lookup"><span data-stu-id="77f8e-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="77f8e-107">Los costes generales proporcionan un soporte fundamental a la generación de actividades rentables.</span><span class="sxs-lookup"><span data-stu-id="77f8e-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="77f8e-108">Algunos ejemplos de costes generales son:</span><span class="sxs-lookup"><span data-stu-id="77f8e-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="77f8e-109">Alquiler</span><span class="sxs-lookup"><span data-stu-id="77f8e-109">Rent</span></span>
-   <span data-ttu-id="77f8e-110">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-110">Electricity</span></span>
-   <span data-ttu-id="77f8e-111">Sueldos administrativos</span><span class="sxs-lookup"><span data-stu-id="77f8e-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="77f8e-112">Visión general del cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="77f8e-112">Overhead calculation overview</span></span>
<span data-ttu-id="77f8e-113">El cálculo de costes generales ejecuta las directivas de contabilidad de costes en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="77f8e-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="77f8e-114">Puede calcular varias veces los costes generales del mismo período fiscal si se han cambiado las directivas de contabilidad de costes o se han detectado errores específicos.</span><span class="sxs-lookup"><span data-stu-id="77f8e-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="77f8e-115">Cada ejecución del cálculo de costes generales se almacena y recibe un identificador de versión único que permite comparar los cálculos de diferentes versiones.</span><span class="sxs-lookup"><span data-stu-id="77f8e-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="77f8e-116">Las entradas de costes que el cálculo de costes generales genera reciben una fecha de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="77f8e-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="77f8e-117">Esta fecha de contabilidad coincide con la fecha final del período fiscal que se usa en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="77f8e-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="77f8e-118">El identificador de versión único consiste en los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="77f8e-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="77f8e-119">Tipo de versión</span><span class="sxs-lookup"><span data-stu-id="77f8e-119">Version type</span></span>
-   <span data-ttu-id="77f8e-120">Fecha y hora</span><span class="sxs-lookup"><span data-stu-id="77f8e-120">Date and time</span></span>
-   <span data-ttu-id="77f8e-121">Libro mayor de contabilidad de costes</span><span class="sxs-lookup"><span data-stu-id="77f8e-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="77f8e-122">Ejercicio</span><span class="sxs-lookup"><span data-stu-id="77f8e-122">Fiscal year</span></span>
-   <span data-ttu-id="77f8e-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="77f8e-123">Fiscal period</span></span>

<span data-ttu-id="77f8e-124">El cálculo de costes generales se ejecuta independientemente de la versión.</span><span class="sxs-lookup"><span data-stu-id="77f8e-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="77f8e-125">Por lo tanto, puede calcular la versión de presupuesto antes que la versión real.</span><span class="sxs-lookup"><span data-stu-id="77f8e-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="77f8e-126">El cálculo de costes generales consta de cuatro pasos, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="77f8e-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="77f8e-127">En cada paso, se crea una cabecera de diario que tiene entradas del diario.</span><span class="sxs-lookup"><span data-stu-id="77f8e-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="77f8e-128">Esta cabecera de diario guarda los datos de entrada para cada paso de cálculo.</span><span class="sxs-lookup"><span data-stu-id="77f8e-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="77f8e-129">Las directivas y las reglas se aplican a cada línea de diario, y las entradas de coste se generan como resultado.</span><span class="sxs-lookup"><span data-stu-id="77f8e-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="77f8e-130">Por tanto, siempre se tiene rastreabilidad completa.</span><span class="sxs-lookup"><span data-stu-id="77f8e-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="77f8e-131">[![Cálculo de costes generales](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="77f8e-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="77f8e-132">Calcular y asignar costes generales de electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="77f8e-133">En la contabilidad financiera, algunos costes, como la electricidad, se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="77f8e-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="77f8e-134">Por lo tanto, no se proporciona una visión de gestión detallada para la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="77f8e-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="77f8e-135">En contabilidad de costes, para proporcionar información de gestión correcta en todas las unidades y niveles organizativos, los costes deben fluir por las unidades organizativas.</span><span class="sxs-lookup"><span data-stu-id="77f8e-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="77f8e-136">Este flujo se debe basar en cualquier registro preciso de consumo o en una evaluación justa.</span><span class="sxs-lookup"><span data-stu-id="77f8e-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="77f8e-137">En la contabilidad general, un coste de la electricidad se puede registrar como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="77f8e-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="77f8e-138">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="77f8e-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="77f8e-139">Centro de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="77f8e-140">Cuenta principal</span><span class="sxs-lookup"><span data-stu-id="77f8e-140">Main account</span></span></th>
<th><span data-ttu-id="77f8e-141">Importe en la divisa de contabilidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-142">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="77f8e-143">CC099</span><span class="sxs-lookup"><span data-stu-id="77f8e-143">CC099</span></span></td>
<td><span data-ttu-id="77f8e-144">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="77f8e-144">Default cost center</span></span></td>
<td><span data-ttu-id="77f8e-145">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-145">10001</span></span></td>
<td><span data-ttu-id="77f8e-146">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-146">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="77f8e-148">Paso 1: Procese el cálculo del comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="77f8e-149">De forma predeterminada, cuando las entradas de coste se importan de los datos de origen, reciben la clasificación de comportamiento del coste **Sin ordenar** en la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="77f8e-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="77f8e-150">Aplicando reglas de directivas de comportamiento de coste, puede reclasificar entradas de coste como **Coste fijo** o **Coste variable**.</span><span class="sxs-lookup"><span data-stu-id="77f8e-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="77f8e-151">Defina la regla de comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-151">Define the cost behavior rule</span></span>

<span data-ttu-id="77f8e-152">En algunos casos, parte del coste es una cuota fija, y el coste pendiente se basa en el consumo.</span><span class="sxs-lookup"><span data-stu-id="77f8e-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="77f8e-153">Las facturas de electricidad coinciden a menudo con esta definición.</span><span class="sxs-lookup"><span data-stu-id="77f8e-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="77f8e-154">Tras pagar una cuota fija específica, paga el consumo por kilovatio-hora (Kwh).</span><span class="sxs-lookup"><span data-stu-id="77f8e-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="77f8e-155">Por ejemplo, si la cuota de coste fijo es de 1.000,00, la regla de comportamiento del coste se define como sigue:</span><span class="sxs-lookup"><span data-stu-id="77f8e-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="77f8e-156">Importe fijo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="77f8e-157">0 &lt;= 1.000,00 = Fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="77f8e-158">1.000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="77f8e-159">Diario</span><span class="sxs-lookup"><span data-stu-id="77f8e-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="77f8e-160">Diario</span><span class="sxs-lookup"><span data-stu-id="77f8e-160">Journal</span></span></th>
<th><span data-ttu-id="77f8e-161">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="77f8e-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="77f8e-162">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="77f8e-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="77f8e-163">Versión</span><span class="sxs-lookup"><span data-stu-id="77f8e-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-164">00001</span><span class="sxs-lookup"><span data-stu-id="77f8e-164">00001</span></span></td>
<td><span data-ttu-id="77f8e-165">Diario de cálculo de comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="77f8e-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="77f8e-166">Fiscal</span><span class="sxs-lookup"><span data-stu-id="77f8e-166">Fiscal</span></span></td>
<td><span data-ttu-id="77f8e-167">2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-167">2017</span></span></td>
<td><span data-ttu-id="77f8e-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-168">Period 1</span></span></td>
<td><span data-ttu-id="77f8e-169">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="77f8e-170">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="77f8e-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="77f8e-171">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="77f8e-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="77f8e-172">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="77f8e-173">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-173">Cost element</span></span></th>
<th><span data-ttu-id="77f8e-174">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="77f8e-174">Cost behavior</span></span></th>
<th><span data-ttu-id="77f8e-175">Importe</span><span class="sxs-lookup"><span data-stu-id="77f8e-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-176">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="77f8e-177">CC099</span><span class="sxs-lookup"><span data-stu-id="77f8e-177">CC099</span></span></td>
<td><span data-ttu-id="77f8e-178">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="77f8e-178">Default cost center</span></span></td>
<td><span data-ttu-id="77f8e-179">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-179">10001</span></span></td>
<td><span data-ttu-id="77f8e-180">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-180">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-181">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="77f8e-181">Unclassified</span></span></td>
<td><span data-ttu-id="77f8e-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="77f8e-183">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="77f8e-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="77f8e-184">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="77f8e-185">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-185">Cost element</span></span></th>
<th><span data-ttu-id="77f8e-186">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="77f8e-186">Cost behavior</span></span></th>
<th><span data-ttu-id="77f8e-187">Importe</span><span class="sxs-lookup"><span data-stu-id="77f8e-187">Amount</span></span></th>
<th><span data-ttu-id="77f8e-188">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="77f8e-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-189">CC099</span><span class="sxs-lookup"><span data-stu-id="77f8e-189">CC099</span></span></td>
<td><span data-ttu-id="77f8e-190">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="77f8e-190">Default cost center</span></span></td>
<td><span data-ttu-id="77f8e-191">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-191">10001</span></span></td>
<td><span data-ttu-id="77f8e-192">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-192">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-193">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="77f8e-193">Unclassified</span></span></td>
<td><span data-ttu-id="77f8e-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-194">10,000.00</span></span></td>
<td><span data-ttu-id="77f8e-195">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-196">CC099</span><span class="sxs-lookup"><span data-stu-id="77f8e-196">CC099</span></span></td>
<td><span data-ttu-id="77f8e-197">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="77f8e-197">Default cost center</span></span></td>
<td><span data-ttu-id="77f8e-198">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-198">10001</span></span></td>
<td><span data-ttu-id="77f8e-199">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-199">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-200">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="77f8e-200">Unclassified</span></span></td>
<td><span data-ttu-id="77f8e-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-201">-10,000.00</span></span></td>
<td><span data-ttu-id="77f8e-202">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-203">CC099</span><span class="sxs-lookup"><span data-stu-id="77f8e-203">CC099</span></span></td>
<td><span data-ttu-id="77f8e-204">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="77f8e-204">Default cost center</span></span></td>
<td><span data-ttu-id="77f8e-205">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-205">10001</span></span></td>
<td><span data-ttu-id="77f8e-206">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-206">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-207">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-207">Fixed cost</span></span></td>
<td><span data-ttu-id="77f8e-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-208">1,000.00</span></span></td>
<td><span data-ttu-id="77f8e-209">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-210">CC099</span><span class="sxs-lookup"><span data-stu-id="77f8e-210">CC099</span></span></td>
<td><span data-ttu-id="77f8e-211">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="77f8e-211">Default cost center</span></span></td>
<td><span data-ttu-id="77f8e-212">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-212">10001</span></span></td>
<td><span data-ttu-id="77f8e-213">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-213">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-214">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-214">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-215">9,000.00</span></span></td>
<td><span data-ttu-id="77f8e-216">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="77f8e-217">Para obtener más información, consulte [Crear y asignar una directiva de comportamiento de costes a una unidad de control de costes](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="77f8e-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="77f8e-218">Paso 2: Procese el cálculo de distribución de costes</span><span class="sxs-lookup"><span data-stu-id="77f8e-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="77f8e-219">La distribución de costes se usa para redistribuir costes desde un objeto de coste a uno o más objetos de coste aplicando una base relevante de la asignación.</span><span class="sxs-lookup"><span data-stu-id="77f8e-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="77f8e-220">La distribución de costes y la asignación de costes difieren en que la distribución de costes siempre se produce en el nivel de elemento de costes principal del coste original.</span><span class="sxs-lookup"><span data-stu-id="77f8e-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="77f8e-221">Defina la regla de distribución del coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-221">Define the cost distribution rule</span></span>

<span data-ttu-id="77f8e-222">En la contabilidad financiera, los costes de electricidad se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="77f8e-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="77f8e-223">En contabilidad de costes, este método no es suficientemente detallado.</span><span class="sxs-lookup"><span data-stu-id="77f8e-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="77f8e-224">El coste variable debe distribuirse a los objetos individuales de coste aplicando una base justa.</span><span class="sxs-lookup"><span data-stu-id="77f8e-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="77f8e-225">La base de asignación más lógica es el consumo de electricidad (Kwh).</span><span class="sxs-lookup"><span data-stu-id="77f8e-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="77f8e-226">Se crea un miembro de dimensión estadística que se denomina Electricity, y se registra el consumo de electricidad.</span><span class="sxs-lookup"><span data-stu-id="77f8e-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="77f8e-227">De forma predeterminada, todos los miembros de dimensión estadísticos estarán disponibles como bases de asignación.</span><span class="sxs-lookup"><span data-stu-id="77f8e-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="77f8e-228">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-228">Cost object</span></span></th>
<th><span data-ttu-id="77f8e-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="77f8e-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-230">CC001</span><span class="sxs-lookup"><span data-stu-id="77f8e-230">CC001</span></span></td>
<td><span data-ttu-id="77f8e-231">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="77f8e-231">HR</span></span></td>
<td><span data-ttu-id="77f8e-232">1.000</span><span class="sxs-lookup"><span data-stu-id="77f8e-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-233">CC002</span><span class="sxs-lookup"><span data-stu-id="77f8e-233">CC002</span></span></td>
<td><span data-ttu-id="77f8e-234">Finanzas</span><span class="sxs-lookup"><span data-stu-id="77f8e-234">Finance</span></span></td>
<td><span data-ttu-id="77f8e-235">6.000</span><span class="sxs-lookup"><span data-stu-id="77f8e-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-236">CC003</span><span class="sxs-lookup"><span data-stu-id="77f8e-236">CC003</span></span></td>
<td><span data-ttu-id="77f8e-237">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="77f8e-237">Assembly</span></span></td>
<td><span data-ttu-id="77f8e-238">0</span><span class="sxs-lookup"><span data-stu-id="77f8e-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="77f8e-239">La tabla siguiente muestra el resultado cuando se aplica el consumo de electricidad como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="77f8e-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="77f8e-240">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-240">Cost object</span></span></th>
<th><span data-ttu-id="77f8e-241">Magnitud</span><span class="sxs-lookup"><span data-stu-id="77f8e-241">Magnitude</span></span></th>
<th><span data-ttu-id="77f8e-242">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="77f8e-242">Allocation factor</span></span></th>
<th><span data-ttu-id="77f8e-243">Importe</span><span class="sxs-lookup"><span data-stu-id="77f8e-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-244">CC001</span><span class="sxs-lookup"><span data-stu-id="77f8e-244">CC001</span></span></td>
<td><span data-ttu-id="77f8e-245">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="77f8e-245">HR</span></span></td>
<td><span data-ttu-id="77f8e-246">1.000</span><span class="sxs-lookup"><span data-stu-id="77f8e-246">1,000</span></span></td>
<td><span data-ttu-id="77f8e-247">(1.000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="77f8e-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="77f8e-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-249">CC002</span><span class="sxs-lookup"><span data-stu-id="77f8e-249">CC002</span></span></td>
<td><span data-ttu-id="77f8e-250">Finanzas</span><span class="sxs-lookup"><span data-stu-id="77f8e-250">Finance</span></span></td>
<td><span data-ttu-id="77f8e-251">6.000</span><span class="sxs-lookup"><span data-stu-id="77f8e-251">6,000</span></span></td>
<td><span data-ttu-id="77f8e-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="77f8e-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="77f8e-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-254">CC003</span><span class="sxs-lookup"><span data-stu-id="77f8e-254">CC003</span></span></td>
<td><span data-ttu-id="77f8e-255">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="77f8e-255">Assembly</span></span></td>
<td><span data-ttu-id="77f8e-256">0</span><span class="sxs-lookup"><span data-stu-id="77f8e-256">0</span></span></td>
<td><span data-ttu-id="77f8e-257">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="77f8e-258">0,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="77f8e-259">El coste fijo debe distribuirse uniformemente a los objetos individuales de costes que han consumido electricidad.</span><span class="sxs-lookup"><span data-stu-id="77f8e-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="77f8e-260">Puede obtener este resultado usando el miembro de dimensión estadístico de electricidad en una base de asignación de la fórmula: (Electricidad &gt; 0,00) La tabla siguiente muestra el resultado cuando el consumo de electricidad se aplica como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="77f8e-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="77f8e-261">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-261">Cost object</span></span></th>
<th><span data-ttu-id="77f8e-262">Fórmula</span><span class="sxs-lookup"><span data-stu-id="77f8e-262">Formula</span></span></th>
<th><span data-ttu-id="77f8e-263">Magnitud</span><span class="sxs-lookup"><span data-stu-id="77f8e-263">Magnitude</span></span></th>
<th><span data-ttu-id="77f8e-264">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="77f8e-264">Allocation factor</span></span></th>
<th><span data-ttu-id="77f8e-265">Importe</span><span class="sxs-lookup"><span data-stu-id="77f8e-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-266">CC001</span><span class="sxs-lookup"><span data-stu-id="77f8e-266">CC001</span></span></td>
<td><span data-ttu-id="77f8e-267">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="77f8e-267">HR</span></span></td>
<td><span data-ttu-id="77f8e-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="77f8e-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="77f8e-269">1</span><span class="sxs-lookup"><span data-stu-id="77f8e-269">1</span></span></td>
<td><span data-ttu-id="77f8e-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="77f8e-271">500,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-272">CC002</span><span class="sxs-lookup"><span data-stu-id="77f8e-272">CC002</span></span></td>
<td><span data-ttu-id="77f8e-273">Finanzas</span><span class="sxs-lookup"><span data-stu-id="77f8e-273">Finance</span></span></td>
<td><span data-ttu-id="77f8e-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="77f8e-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="77f8e-275">1</span><span class="sxs-lookup"><span data-stu-id="77f8e-275">1</span></span></td>
<td><span data-ttu-id="77f8e-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="77f8e-277">500,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-278">CC003</span><span class="sxs-lookup"><span data-stu-id="77f8e-278">CC003</span></span></td>
<td><span data-ttu-id="77f8e-279">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="77f8e-279">Assembly</span></span></td>
<td><span data-ttu-id="77f8e-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="77f8e-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="77f8e-281">0</span><span class="sxs-lookup"><span data-stu-id="77f8e-281">0</span></span></td>
<td><span data-ttu-id="77f8e-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="77f8e-283">0,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="77f8e-284">Diario</span><span class="sxs-lookup"><span data-stu-id="77f8e-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="77f8e-285">Diario</span><span class="sxs-lookup"><span data-stu-id="77f8e-285">Journal</span></span></th>
<th><span data-ttu-id="77f8e-286">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="77f8e-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="77f8e-287">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="77f8e-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="77f8e-288">Versión</span><span class="sxs-lookup"><span data-stu-id="77f8e-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-289">00002</span><span class="sxs-lookup"><span data-stu-id="77f8e-289">00002</span></span></td>
<td><span data-ttu-id="77f8e-290">Diario de cálculo de la distribución de costes</span><span class="sxs-lookup"><span data-stu-id="77f8e-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="77f8e-291">Fiscal</span><span class="sxs-lookup"><span data-stu-id="77f8e-291">Fiscal</span></span></td>
<td><span data-ttu-id="77f8e-292">2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-292">2017</span></span></td>
<td><span data-ttu-id="77f8e-293">Período 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-293">Period 1</span></span></td>
<td><span data-ttu-id="77f8e-294">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="77f8e-295">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="77f8e-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="77f8e-296">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="77f8e-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="77f8e-297">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="77f8e-298">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-298">Cost element</span></span></th>
<th><span data-ttu-id="77f8e-299">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="77f8e-299">Cost behavior</span></span></th>
<th><span data-ttu-id="77f8e-300">Importe</span><span class="sxs-lookup"><span data-stu-id="77f8e-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-301">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="77f8e-302">CC099</span><span class="sxs-lookup"><span data-stu-id="77f8e-302">CC099</span></span></td>
<td><span data-ttu-id="77f8e-303">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="77f8e-303">Default cost center</span></span></td>
<td><span data-ttu-id="77f8e-304">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-304">10001</span></span></td>
<td><span data-ttu-id="77f8e-305">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-305">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-306">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-306">Fixed cost</span></span></td>
<td><span data-ttu-id="77f8e-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-308">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="77f8e-309">CC099</span><span class="sxs-lookup"><span data-stu-id="77f8e-309">CC099</span></span></td>
<td><span data-ttu-id="77f8e-310">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="77f8e-310">Default cost center</span></span></td>
<td><span data-ttu-id="77f8e-311">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-311">10001</span></span></td>
<td><span data-ttu-id="77f8e-312">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-312">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-313">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-313">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-314">9.000,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="77f8e-315">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="77f8e-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="77f8e-316">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="77f8e-317">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-317">Cost element</span></span></th>
<th><span data-ttu-id="77f8e-318">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="77f8e-318">Cost behavior</span></span></th>
<th><span data-ttu-id="77f8e-319">Importe</span><span class="sxs-lookup"><span data-stu-id="77f8e-319">Amount</span></span></th>
<th><span data-ttu-id="77f8e-320">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="77f8e-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-321">CC099</span><span class="sxs-lookup"><span data-stu-id="77f8e-321">CC099</span></span></td>
<td><span data-ttu-id="77f8e-322">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="77f8e-322">Default cost center</span></span></td>
<td><span data-ttu-id="77f8e-323">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-323">10001</span></span></td>
<td><span data-ttu-id="77f8e-324">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-324">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-325">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-325">Fixed cost</span></span></td>
<td><span data-ttu-id="77f8e-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-326">-1,000.00</span></span></td>
<td><span data-ttu-id="77f8e-327">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-328">CC001</span><span class="sxs-lookup"><span data-stu-id="77f8e-328">CC001</span></span></td>
<td><span data-ttu-id="77f8e-329">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="77f8e-329">HR</span></span></td>
<td><span data-ttu-id="77f8e-330">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-330">10001</span></span></td>
<td><span data-ttu-id="77f8e-331">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-331">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-332">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-332">Fixed cost</span></span></td>
<td><span data-ttu-id="77f8e-333">500,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-333">500.00</span></span></td>
<td><span data-ttu-id="77f8e-334">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-335">CC002</span><span class="sxs-lookup"><span data-stu-id="77f8e-335">CC002</span></span></td>
<td><span data-ttu-id="77f8e-336">Finanzas</span><span class="sxs-lookup"><span data-stu-id="77f8e-336">Finance</span></span></td>
<td><span data-ttu-id="77f8e-337">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-337">10001</span></span></td>
<td><span data-ttu-id="77f8e-338">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-338">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-339">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-339">Fixed cost</span></span></td>
<td><span data-ttu-id="77f8e-340">500,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-340">500.00</span></span></td>
<td><span data-ttu-id="77f8e-341">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-342">CC099</span><span class="sxs-lookup"><span data-stu-id="77f8e-342">CC099</span></span></td>
<td><span data-ttu-id="77f8e-343">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="77f8e-343">Default cost center</span></span></td>
<td><span data-ttu-id="77f8e-344">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-344">10001</span></span></td>
<td><span data-ttu-id="77f8e-345">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-345">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-346">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-346">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-347">-9,000.00</span></span></td>
<td><span data-ttu-id="77f8e-348">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-349">CC001</span><span class="sxs-lookup"><span data-stu-id="77f8e-349">CC001</span></span></td>
<td><span data-ttu-id="77f8e-350">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="77f8e-350">HR</span></span></td>
<td><span data-ttu-id="77f8e-351">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-351">10001</span></span></td>
<td><span data-ttu-id="77f8e-352">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-352">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-353">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-353">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="77f8e-354">1,285.71</span></span></td>
<td><span data-ttu-id="77f8e-355">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-356">CC002</span><span class="sxs-lookup"><span data-stu-id="77f8e-356">CC002</span></span></td>
<td><span data-ttu-id="77f8e-357">Finanzas</span><span class="sxs-lookup"><span data-stu-id="77f8e-357">Finance</span></span></td>
<td><span data-ttu-id="77f8e-358">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-358">10001</span></span></td>
<td><span data-ttu-id="77f8e-359">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-359">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-360">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-360">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="77f8e-361">7,714.29</span></span></td>
<td><span data-ttu-id="77f8e-362">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="77f8e-363">Para obtener más información, consulte [Crear y asignar una directiva de distribución de costes a una unidad de control de costes](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="77f8e-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="77f8e-364">Paso 3: Procese el cálculo de las tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="77f8e-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="77f8e-365">La tasa de costes generales se usa para cargar uno o varios objetos de coste específicos.</span><span class="sxs-lookup"><span data-stu-id="77f8e-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="77f8e-366">El cargo se basa en un índice de coste predeterminado y la magnitud de la base de asignación asignada.</span><span class="sxs-lookup"><span data-stu-id="77f8e-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="77f8e-367">Defina la tasa de costes generales</span><span class="sxs-lookup"><span data-stu-id="77f8e-367">Define the overhead rate</span></span>

<span data-ttu-id="77f8e-368">El objeto de coste CC001 HR contribuye a un conjunto de proyectos internos.</span><span class="sxs-lookup"><span data-stu-id="77f8e-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="77f8e-369">Se crea un miembro de dimensión estadística que se denomina proyectos HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="77f8e-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="77f8e-370">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-370">Cost object</span></span></th>
<th><span data-ttu-id="77f8e-371">Horas</span><span class="sxs-lookup"><span data-stu-id="77f8e-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-372">Proy 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-372">Proj 1</span></span></td>
<td><span data-ttu-id="77f8e-373">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-373">Project 1</span></span></td>
<td><span data-ttu-id="77f8e-374">3</span><span class="sxs-lookup"><span data-stu-id="77f8e-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-375">Proy 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-375">Proj 2</span></span></td>
<td><span data-ttu-id="77f8e-376">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-376">Project 2</span></span></td>
<td><span data-ttu-id="77f8e-377">1</span><span class="sxs-lookup"><span data-stu-id="77f8e-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="77f8e-378">Una tasa de coste predeterminada para la contribución de los proyectos de coste se ha definido.</span><span class="sxs-lookup"><span data-stu-id="77f8e-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="77f8e-379">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-379">Cost object</span></span></th>
<th><span data-ttu-id="77f8e-380">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-380">Cost element</span></span></th>
<th><span data-ttu-id="77f8e-381">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="77f8e-381">Cost behavior</span></span></th>
<th><span data-ttu-id="77f8e-382">Unidades</span><span class="sxs-lookup"><span data-stu-id="77f8e-382">Units</span></span></th>
<th><span data-ttu-id="77f8e-383">Índice</span><span class="sxs-lookup"><span data-stu-id="77f8e-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-384">CC001</span><span class="sxs-lookup"><span data-stu-id="77f8e-384">CC001</span></span></td>
<td><span data-ttu-id="77f8e-385">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="77f8e-385">HR</span></span></td>
<td><span data-ttu-id="77f8e-386">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-386">10001</span></span></td>
<td><span data-ttu-id="77f8e-387">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-387">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-388">1</span><span class="sxs-lookup"><span data-stu-id="77f8e-388">1</span></span></td>
<td><span data-ttu-id="77f8e-389">10</span><span class="sxs-lookup"><span data-stu-id="77f8e-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="77f8e-390">La tabla siguiente muestra el resultado cuando los proyectos HR se aplican como base de la asignación.</span><span class="sxs-lookup"><span data-stu-id="77f8e-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="77f8e-391">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-391">Cost object</span></span></th>
<th><span data-ttu-id="77f8e-392">Magnitud</span><span class="sxs-lookup"><span data-stu-id="77f8e-392">Magnitude</span></span></th>
<th><span data-ttu-id="77f8e-393">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-393">Cost element</span></span></th>
<th><span data-ttu-id="77f8e-394">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="77f8e-394">Allocation factor</span></span></th>
<th><span data-ttu-id="77f8e-395">Importe</span><span class="sxs-lookup"><span data-stu-id="77f8e-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-396">Proy 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-396">Proj 1</span></span></td>
<td><span data-ttu-id="77f8e-397">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-397">Project 1</span></span></td>
<td><span data-ttu-id="77f8e-398">3</span><span class="sxs-lookup"><span data-stu-id="77f8e-398">3</span></span></td>
<td><span data-ttu-id="77f8e-399">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-399">10001</span></span></td>
<td><span data-ttu-id="77f8e-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="77f8e-401">30,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-402">Proy 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-402">Proj 2</span></span></td>
<td><span data-ttu-id="77f8e-403">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-403">Project 2</span></span></td>
<td><span data-ttu-id="77f8e-404">1</span><span class="sxs-lookup"><span data-stu-id="77f8e-404">1</span></span></td>
<td><span data-ttu-id="77f8e-405">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-405">10001</span></span></td>
<td><span data-ttu-id="77f8e-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="77f8e-407">10,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="77f8e-408">Diario</span><span class="sxs-lookup"><span data-stu-id="77f8e-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="77f8e-409">Diario</span><span class="sxs-lookup"><span data-stu-id="77f8e-409">Journal</span></span></th>
<th><span data-ttu-id="77f8e-410">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="77f8e-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="77f8e-411">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="77f8e-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="77f8e-412">Versión</span><span class="sxs-lookup"><span data-stu-id="77f8e-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-413">00003</span><span class="sxs-lookup"><span data-stu-id="77f8e-413">00003</span></span></td>
<td><span data-ttu-id="77f8e-414">Diario de cálculo de tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="77f8e-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="77f8e-415">Fiscal</span><span class="sxs-lookup"><span data-stu-id="77f8e-415">Fiscal</span></span></td>
<td><span data-ttu-id="77f8e-416">2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-416">2017</span></span></td>
<td><span data-ttu-id="77f8e-417">Período 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-417">Period 1</span></span></td>
<td><span data-ttu-id="77f8e-418">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="77f8e-419">Entradas de diario (entradas de diario para cálculo de tasas de costes generales)</span><span class="sxs-lookup"><span data-stu-id="77f8e-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="77f8e-420">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="77f8e-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="77f8e-421">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-421">Cost object</span></span></th>
<th><span data-ttu-id="77f8e-422">Magnitud</span><span class="sxs-lookup"><span data-stu-id="77f8e-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-423">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="77f8e-424">Proy 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-424">Proj 1</span></span></td>
<td><span data-ttu-id="77f8e-425">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="77f8e-426">3,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-427">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="77f8e-428">Proy 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-428">Proj 2</span></span></td>
<td><span data-ttu-id="77f8e-429">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="77f8e-430">1,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="77f8e-431">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="77f8e-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="77f8e-432">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="77f8e-433">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-433">Cost element</span></span></th>
<th><span data-ttu-id="77f8e-434">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="77f8e-434">Cost behavior</span></span></th>
<th><span data-ttu-id="77f8e-435">Importe</span><span class="sxs-lookup"><span data-stu-id="77f8e-435">Amount</span></span></th>
<th><span data-ttu-id="77f8e-436">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="77f8e-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="77f8e-437">CC0001</span></span></td>
<td><span data-ttu-id="77f8e-438">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="77f8e-438">HR</span></span></td>
<td><span data-ttu-id="77f8e-439">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-439">10001</span></span></td>
<td><span data-ttu-id="77f8e-440">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-440">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-441">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-441">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-442">-30.00</span></span></td>
<td><span data-ttu-id="77f8e-443">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-444">Proy 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-444">Proj 1</span></span></td>
<td><span data-ttu-id="77f8e-445">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="77f8e-446">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-446">10001</span></span></td>
<td><span data-ttu-id="77f8e-447">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-447">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-448">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-448">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-449">30,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-449">30.00</span></span></td>
<td><span data-ttu-id="77f8e-450">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-451">CC001</span><span class="sxs-lookup"><span data-stu-id="77f8e-451">CC001</span></span></td>
<td><span data-ttu-id="77f8e-452">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="77f8e-452">HR</span></span></td>
<td><span data-ttu-id="77f8e-453">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-453">10001</span></span></td>
<td><span data-ttu-id="77f8e-454">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-454">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-455">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-455">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-456">-10.00</span></span></td>
<td><span data-ttu-id="77f8e-457">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-458">Proy 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-458">Proj 2</span></span></td>
<td><span data-ttu-id="77f8e-459">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="77f8e-460">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-460">10001</span></span></td>
<td><span data-ttu-id="77f8e-461">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-461">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-462">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-462">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-463">10,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-463">10.00</span></span></td>
<td><span data-ttu-id="77f8e-464">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="77f8e-465">Para obtener más información, consulte [Realizar cálculo de costes generales](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="77f8e-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="77f8e-466">Paso 4: Procese el cálculo de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="77f8e-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="77f8e-467">La asignación es utilizada para asignar el saldo de un objeto de coste a otros objetos de coste aplicando una base de asignación.</span><span class="sxs-lookup"><span data-stu-id="77f8e-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="77f8e-468">Finance and Operations admite el método de asignación recíproco.</span><span class="sxs-lookup"><span data-stu-id="77f8e-468">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="77f8e-469">En el método de asignación recíproco, se reconocen completamente los servicios mutuos que los objetos de coste auxiliar intercambian.</span><span class="sxs-lookup"><span data-stu-id="77f8e-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="77f8e-470">El sistema determina automáticamente el orden correcto para realizar las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="77f8e-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="77f8e-471">El saldo de un objeto de coste se asigna según una única base de asignación.</span><span class="sxs-lookup"><span data-stu-id="77f8e-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="77f8e-472">Las asignaciones entre dimensiones de objetos de coste y sus miembros respectivos se admiten.</span><span class="sxs-lookup"><span data-stu-id="77f8e-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="77f8e-473">El orden de asignación se controla por unidad de control de costes.</span><span class="sxs-lookup"><span data-stu-id="77f8e-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="77f8e-474">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="77f8e-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="77f8e-475">Defina la asignación de costes</span><span class="sxs-lookup"><span data-stu-id="77f8e-475">Define the cost allocation</span></span>

<span data-ttu-id="77f8e-476">A continuación se indica un ejemplo sencillo que explica cómo puede realizar el seguimiento del flujo de coste.</span><span class="sxs-lookup"><span data-stu-id="77f8e-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="77f8e-477">El objeto de coste CC001 HR contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="77f8e-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="77f8e-478">Se crea un miembro de dimensión estadística que se denomina servicios HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="77f8e-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="77f8e-479">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-479">Cost object</span></span></th>
<th><span data-ttu-id="77f8e-480">Servicios HR</span><span class="sxs-lookup"><span data-stu-id="77f8e-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-481">CC002</span><span class="sxs-lookup"><span data-stu-id="77f8e-481">CC002</span></span></td>
<td><span data-ttu-id="77f8e-482">Finanzas</span><span class="sxs-lookup"><span data-stu-id="77f8e-482">Finance</span></span></td>
<td><span data-ttu-id="77f8e-483">35</span><span class="sxs-lookup"><span data-stu-id="77f8e-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-484">CC003</span><span class="sxs-lookup"><span data-stu-id="77f8e-484">CC003</span></span></td>
<td><span data-ttu-id="77f8e-485">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="77f8e-485">Assembly</span></span></td>
<td><span data-ttu-id="77f8e-486">55</span><span class="sxs-lookup"><span data-stu-id="77f8e-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-487">CC004</span><span class="sxs-lookup"><span data-stu-id="77f8e-487">CC004</span></span></td>
<td><span data-ttu-id="77f8e-488">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="77f8e-488">Packaging</span></span></td>
<td><span data-ttu-id="77f8e-489">10</span><span class="sxs-lookup"><span data-stu-id="77f8e-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="77f8e-490">El objeto de coste CC002 Finanzas contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="77f8e-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="77f8e-491">Se crea un miembro de dimensión estadística que se denomina Finanzas para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="77f8e-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="77f8e-492">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-492">Cost object</span></span></th>
<th><span data-ttu-id="77f8e-493">Servicios financieros</span><span class="sxs-lookup"><span data-stu-id="77f8e-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-494">CC003</span><span class="sxs-lookup"><span data-stu-id="77f8e-494">CC003</span></span></td>
<td><span data-ttu-id="77f8e-495">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="77f8e-495">Assembly</span></span></td>
<td><span data-ttu-id="77f8e-496">65</span><span class="sxs-lookup"><span data-stu-id="77f8e-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-497">CC004</span><span class="sxs-lookup"><span data-stu-id="77f8e-497">CC004</span></span></td>
<td><span data-ttu-id="77f8e-498">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="77f8e-498">Packaging</span></span></td>
<td><span data-ttu-id="77f8e-499">35</span><span class="sxs-lookup"><span data-stu-id="77f8e-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="77f8e-500">El objeto de coste CC003 Asamblea contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="77f8e-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="77f8e-501">Se crea un miembro de dimensión estadística que se denomina servicios de Asamblea para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="77f8e-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="77f8e-502">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-502">Cost object</span></span></th>
<th><span data-ttu-id="77f8e-503">Servicios de la asamblea (horas)</span><span class="sxs-lookup"><span data-stu-id="77f8e-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-504">Prod 1</span></span></td>
<td><span data-ttu-id="77f8e-505">Producto 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-505">Product 1</span></span></td>
<td><span data-ttu-id="77f8e-506">60</span><span class="sxs-lookup"><span data-stu-id="77f8e-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-507">Prod 2</span></span></td>
<td><span data-ttu-id="77f8e-508">Producto 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-508">Product 2</span></span></td>
<td><span data-ttu-id="77f8e-509">20</span><span class="sxs-lookup"><span data-stu-id="77f8e-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="77f8e-510">El objeto de coste CC004 Embalaje contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="77f8e-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="77f8e-511">Se crea un miembro de dimensión estadística que se denomina servicios de Embalaje para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="77f8e-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="77f8e-512">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-512">Cost object</span></span></th>
<th><span data-ttu-id="77f8e-513">Servicios de embalaje (horas)</span><span class="sxs-lookup"><span data-stu-id="77f8e-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-514">Prod 1</span></span></td>
<td><span data-ttu-id="77f8e-515">Producto 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-515">Product 1</span></span></td>
<td><span data-ttu-id="77f8e-516">80</span><span class="sxs-lookup"><span data-stu-id="77f8e-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-517">Prod 2</span></span></td>
<td><span data-ttu-id="77f8e-518">Producto 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-518">Product 2</span></span></td>
<td><span data-ttu-id="77f8e-519">15</span><span class="sxs-lookup"><span data-stu-id="77f8e-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="77f8e-520">En Finance and Operations, las medidas estadísticas como las horas de la producción que un producto consume se pueden deducir de los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="77f8e-520">In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="77f8e-521">Para obtener más información, vea [Plantilla de proveedor de medidas estadísticas](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="77f8e-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="77f8e-522">La tabla siguiente muestra el resultado cuando se aplican los servicios de HR como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="77f8e-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="77f8e-523">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-523">Cost object</span></span></th>
<th><span data-ttu-id="77f8e-524">Magnitud</span><span class="sxs-lookup"><span data-stu-id="77f8e-524">Magnitude</span></span></th>
<th><span data-ttu-id="77f8e-525">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="77f8e-525">Allocation factor</span></span></th>
<th><span data-ttu-id="77f8e-526">Importe</span><span class="sxs-lookup"><span data-stu-id="77f8e-526">Amount</span></span></th>
<th><span data-ttu-id="77f8e-527">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="77f8e-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-528">CC002</span><span class="sxs-lookup"><span data-stu-id="77f8e-528">CC002</span></span></td>
<td><span data-ttu-id="77f8e-529">Finanzas</span><span class="sxs-lookup"><span data-stu-id="77f8e-529">Finance</span></span></td>
<td><span data-ttu-id="77f8e-530">35</span><span class="sxs-lookup"><span data-stu-id="77f8e-530">35</span></span></td>
<td><span data-ttu-id="77f8e-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="77f8e-532">175.00</span><span class="sxs-lookup"><span data-stu-id="77f8e-532">175.00</span></span></td>
<td><span data-ttu-id="77f8e-533">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-534">CC003</span><span class="sxs-lookup"><span data-stu-id="77f8e-534">CC003</span></span></td>
<td><span data-ttu-id="77f8e-535">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="77f8e-535">Assembly</span></span></td>
<td><span data-ttu-id="77f8e-536">55</span><span class="sxs-lookup"><span data-stu-id="77f8e-536">55</span></span></td>
<td><span data-ttu-id="77f8e-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="77f8e-538">275.00</span><span class="sxs-lookup"><span data-stu-id="77f8e-538">275.00</span></span></td>
<td><span data-ttu-id="77f8e-539">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-540">CC004</span><span class="sxs-lookup"><span data-stu-id="77f8e-540">CC004</span></span></td>
<td><span data-ttu-id="77f8e-541">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="77f8e-541">Packaging</span></span></td>
<td><span data-ttu-id="77f8e-542">10</span><span class="sxs-lookup"><span data-stu-id="77f8e-542">10</span></span></td>
<td><span data-ttu-id="77f8e-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="77f8e-544">50,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-544">50.00</span></span></td>
<td><span data-ttu-id="77f8e-545">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-546">CC002</span><span class="sxs-lookup"><span data-stu-id="77f8e-546">CC002</span></span></td>
<td><span data-ttu-id="77f8e-547">Finanzas</span><span class="sxs-lookup"><span data-stu-id="77f8e-547">Finance</span></span></td>
<td><span data-ttu-id="77f8e-548">35</span><span class="sxs-lookup"><span data-stu-id="77f8e-548">35</span></span></td>
<td><span data-ttu-id="77f8e-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="77f8e-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="77f8e-550">436.00</span><span class="sxs-lookup"><span data-stu-id="77f8e-550">436.00</span></span></td>
<td><span data-ttu-id="77f8e-551">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-552">CC003</span><span class="sxs-lookup"><span data-stu-id="77f8e-552">CC003</span></span></td>
<td><span data-ttu-id="77f8e-553">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="77f8e-553">Assembly</span></span></td>
<td><span data-ttu-id="77f8e-554">55</span><span class="sxs-lookup"><span data-stu-id="77f8e-554">55</span></span></td>
<td><span data-ttu-id="77f8e-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="77f8e-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="77f8e-556">685.14</span><span class="sxs-lookup"><span data-stu-id="77f8e-556">685.14</span></span></td>
<td><span data-ttu-id="77f8e-557">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-558">CC004</span><span class="sxs-lookup"><span data-stu-id="77f8e-558">CC004</span></span></td>
<td><span data-ttu-id="77f8e-559">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="77f8e-559">Packaging</span></span></td>
<td><span data-ttu-id="77f8e-560">10</span><span class="sxs-lookup"><span data-stu-id="77f8e-560">10</span></span></td>
<td><span data-ttu-id="77f8e-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="77f8e-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="77f8e-562">124.57</span><span class="sxs-lookup"><span data-stu-id="77f8e-562">124.57</span></span></td>
<td><span data-ttu-id="77f8e-563">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="77f8e-564">La tabla siguiente muestra el resultado cuando se aplican los servicios de Finanzas como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="77f8e-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="77f8e-565">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-565">Cost object</span></span></th>
<th><span data-ttu-id="77f8e-566">Magnitud</span><span class="sxs-lookup"><span data-stu-id="77f8e-566">Magnitude</span></span></th>
<th><span data-ttu-id="77f8e-567">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="77f8e-567">Allocation factor</span></span></th>
<th><span data-ttu-id="77f8e-568">Importe</span><span class="sxs-lookup"><span data-stu-id="77f8e-568">Amount</span></span></th>
<th><span data-ttu-id="77f8e-569">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="77f8e-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-570">CC003</span><span class="sxs-lookup"><span data-stu-id="77f8e-570">CC003</span></span></td>
<td><span data-ttu-id="77f8e-571">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="77f8e-571">Assembly</span></span></td>
<td><span data-ttu-id="77f8e-572">65</span><span class="sxs-lookup"><span data-stu-id="77f8e-572">65</span></span></td>
<td><span data-ttu-id="77f8e-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="77f8e-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="77f8e-574">438.75</span><span class="sxs-lookup"><span data-stu-id="77f8e-574">438.75</span></span></td>
<td><span data-ttu-id="77f8e-575">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-576">CC004</span><span class="sxs-lookup"><span data-stu-id="77f8e-576">CC004</span></span></td>
<td><span data-ttu-id="77f8e-577">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="77f8e-577">Packaging</span></span></td>
<td><span data-ttu-id="77f8e-578">35</span><span class="sxs-lookup"><span data-stu-id="77f8e-578">35</span></span></td>
<td><span data-ttu-id="77f8e-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="77f8e-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="77f8e-580">236.25</span><span class="sxs-lookup"><span data-stu-id="77f8e-580">236.25</span></span></td>
<td><span data-ttu-id="77f8e-581">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-582">CC003</span><span class="sxs-lookup"><span data-stu-id="77f8e-582">CC003</span></span></td>
<td><span data-ttu-id="77f8e-583">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="77f8e-583">Assembly</span></span></td>
<td><span data-ttu-id="77f8e-584">65</span><span class="sxs-lookup"><span data-stu-id="77f8e-584">65</span></span></td>
<td><span data-ttu-id="77f8e-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="77f8e-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="77f8e-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="77f8e-586">5,297.69</span></span></td>
<td><span data-ttu-id="77f8e-587">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-588">CC004</span><span class="sxs-lookup"><span data-stu-id="77f8e-588">CC004</span></span></td>
<td><span data-ttu-id="77f8e-589">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="77f8e-589">Packaging</span></span></td>
<td><span data-ttu-id="77f8e-590">35</span><span class="sxs-lookup"><span data-stu-id="77f8e-590">35</span></span></td>
<td><span data-ttu-id="77f8e-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="77f8e-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="77f8e-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="77f8e-592">2,852.60</span></span></td>
<td><span data-ttu-id="77f8e-593">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="77f8e-594">La tabla siguiente muestra el resultado cuando se aplican los servicios de Asamblea como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="77f8e-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="77f8e-595">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-595">Cost object</span></span></th>
<th><span data-ttu-id="77f8e-596">Magnitud</span><span class="sxs-lookup"><span data-stu-id="77f8e-596">Magnitude</span></span></th>
<th><span data-ttu-id="77f8e-597">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="77f8e-597">Allocation factor</span></span></th>
<th><span data-ttu-id="77f8e-598">Importe</span><span class="sxs-lookup"><span data-stu-id="77f8e-598">Amount</span></span></th>
<th><span data-ttu-id="77f8e-599">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="77f8e-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-600">Prod 1</span></span></td>
<td><span data-ttu-id="77f8e-601">Producto 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-601">Product 1</span></span></td>
<td><span data-ttu-id="77f8e-602">60</span><span class="sxs-lookup"><span data-stu-id="77f8e-602">60</span></span></td>
<td><span data-ttu-id="77f8e-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="77f8e-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="77f8e-604">535.31</span><span class="sxs-lookup"><span data-stu-id="77f8e-604">535.31</span></span></td>
<td><span data-ttu-id="77f8e-605">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-606">Prod 2</span></span></td>
<td><span data-ttu-id="77f8e-607">Producto 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-607">Product 2</span></span></td>
<td><span data-ttu-id="77f8e-608">20</span><span class="sxs-lookup"><span data-stu-id="77f8e-608">20</span></span></td>
<td><span data-ttu-id="77f8e-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="77f8e-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="77f8e-610">178.44</span><span class="sxs-lookup"><span data-stu-id="77f8e-610">178.44</span></span></td>
<td><span data-ttu-id="77f8e-611">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-612">Prod 1</span></span></td>
<td><span data-ttu-id="77f8e-613">Producto 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-613">Product 1</span></span></td>
<td><span data-ttu-id="77f8e-614">60</span><span class="sxs-lookup"><span data-stu-id="77f8e-614">60</span></span></td>
<td><span data-ttu-id="77f8e-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="77f8e-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="77f8e-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="77f8e-616">4,487.12</span></span></td>
<td><span data-ttu-id="77f8e-617">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-618">Prod 2</span></span></td>
<td><span data-ttu-id="77f8e-619">Producto 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-619">Product 2</span></span></td>
<td><span data-ttu-id="77f8e-620">20</span><span class="sxs-lookup"><span data-stu-id="77f8e-620">20</span></span></td>
<td><span data-ttu-id="77f8e-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="77f8e-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="77f8e-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="77f8e-622">1,495.71</span></span></td>
<td><span data-ttu-id="77f8e-623">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="77f8e-624">La tabla siguiente muestra el resultado cuando se aplican los servicios de Embalaje como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="77f8e-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="77f8e-625">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-625">Cost object</span></span></th>
<th><span data-ttu-id="77f8e-626">Magnitud</span><span class="sxs-lookup"><span data-stu-id="77f8e-626">Magnitude</span></span></th>
<th><span data-ttu-id="77f8e-627">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="77f8e-627">Allocation factor</span></span></th>
<th><span data-ttu-id="77f8e-628">Importe</span><span class="sxs-lookup"><span data-stu-id="77f8e-628">Amount</span></span></th>
<th><span data-ttu-id="77f8e-629">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="77f8e-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-630">Prod 1</span></span></td>
<td><span data-ttu-id="77f8e-631">Producto 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-631">Product 1</span></span></td>
<td><span data-ttu-id="77f8e-632">80</span><span class="sxs-lookup"><span data-stu-id="77f8e-632">80</span></span></td>
<td><span data-ttu-id="77f8e-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="77f8e-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="77f8e-634">241.05</span><span class="sxs-lookup"><span data-stu-id="77f8e-634">241.05</span></span></td>
<td><span data-ttu-id="77f8e-635">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-636">Prod 2</span></span></td>
<td><span data-ttu-id="77f8e-637">Producto 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-637">Product 2</span></span></td>
<td><span data-ttu-id="77f8e-638">15</span><span class="sxs-lookup"><span data-stu-id="77f8e-638">15</span></span></td>
<td><span data-ttu-id="77f8e-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="77f8e-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="77f8e-640">45.20</span><span class="sxs-lookup"><span data-stu-id="77f8e-640">45.20</span></span></td>
<td><span data-ttu-id="77f8e-641">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-642">Prod 1</span></span></td>
<td><span data-ttu-id="77f8e-643">Producto 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-643">Product 1</span></span></td>
<td><span data-ttu-id="77f8e-644">80</span><span class="sxs-lookup"><span data-stu-id="77f8e-644">80</span></span></td>
<td><span data-ttu-id="77f8e-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="77f8e-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="77f8e-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="77f8e-646">2,507.09</span></span></td>
<td><span data-ttu-id="77f8e-647">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-648">Prod 2</span></span></td>
<td><span data-ttu-id="77f8e-649">Producto 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-649">Product 2</span></span></td>
<td><span data-ttu-id="77f8e-650">15</span><span class="sxs-lookup"><span data-stu-id="77f8e-650">15</span></span></td>
<td><span data-ttu-id="77f8e-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="77f8e-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="77f8e-652">470.08</span><span class="sxs-lookup"><span data-stu-id="77f8e-652">470.08</span></span></td>
<td><span data-ttu-id="77f8e-653">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="77f8e-654">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="77f8e-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="77f8e-655">Diario</span><span class="sxs-lookup"><span data-stu-id="77f8e-655">Journal</span></span></th>
<th><span data-ttu-id="77f8e-656">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="77f8e-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="77f8e-657">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="77f8e-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="77f8e-658">Versión</span><span class="sxs-lookup"><span data-stu-id="77f8e-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-659">00004</span><span class="sxs-lookup"><span data-stu-id="77f8e-659">00004</span></span></td>
<td><span data-ttu-id="77f8e-660">Diario de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="77f8e-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="77f8e-661">Fiscal</span><span class="sxs-lookup"><span data-stu-id="77f8e-661">Fiscal</span></span></td>
<td><span data-ttu-id="77f8e-662">2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-662">2017</span></span></td>
<td><span data-ttu-id="77f8e-663">Período 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-663">Period 1</span></span></td>
<td><span data-ttu-id="77f8e-664">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="77f8e-665">Líneas de diario</span><span class="sxs-lookup"><span data-stu-id="77f8e-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="77f8e-666">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="77f8e-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="77f8e-667">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="77f8e-668">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-668">Cost element</span></span></th>
<th><span data-ttu-id="77f8e-669">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="77f8e-669">Cost behavior</span></span></th>
<th><span data-ttu-id="77f8e-670">Importe</span><span class="sxs-lookup"><span data-stu-id="77f8e-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-671">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="77f8e-672">CC001</span><span class="sxs-lookup"><span data-stu-id="77f8e-672">CC001</span></span></td>
<td><span data-ttu-id="77f8e-673">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="77f8e-673">HR</span></span></td>
<td><span data-ttu-id="77f8e-674">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-674">10001</span></span></td>
<td><span data-ttu-id="77f8e-675">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-675">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-676">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-676">Fixed cost</span></span></td>
<td><span data-ttu-id="77f8e-677">500,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-678">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="77f8e-679">CC001</span><span class="sxs-lookup"><span data-stu-id="77f8e-679">CC001</span></span></td>
<td><span data-ttu-id="77f8e-680">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="77f8e-680">HR</span></span></td>
<td><span data-ttu-id="77f8e-681">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-681">10001</span></span></td>
<td><span data-ttu-id="77f8e-682">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-682">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-683">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-683">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="77f8e-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-685">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="77f8e-686">CC002</span><span class="sxs-lookup"><span data-stu-id="77f8e-686">CC002</span></span></td>
<td><span data-ttu-id="77f8e-687">Finanzas</span><span class="sxs-lookup"><span data-stu-id="77f8e-687">Finance</span></span></td>
<td><span data-ttu-id="77f8e-688">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-688">10001</span></span></td>
<td><span data-ttu-id="77f8e-689">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-689">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-690">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-690">Fixed cost</span></span></td>
<td><span data-ttu-id="77f8e-691">675.00</span><span class="sxs-lookup"><span data-stu-id="77f8e-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-692">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="77f8e-693">CC002</span><span class="sxs-lookup"><span data-stu-id="77f8e-693">CC002</span></span></td>
<td><span data-ttu-id="77f8e-694">Finanzas</span><span class="sxs-lookup"><span data-stu-id="77f8e-694">Finance</span></span></td>
<td><span data-ttu-id="77f8e-695">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-695">10001</span></span></td>
<td><span data-ttu-id="77f8e-696">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-696">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-697">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-697">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="77f8e-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-699">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="77f8e-700">CC003</span><span class="sxs-lookup"><span data-stu-id="77f8e-700">CC003</span></span></td>
<td><span data-ttu-id="77f8e-701">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="77f8e-701">Assembly</span></span></td>
<td><span data-ttu-id="77f8e-702">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-702">10001</span></span></td>
<td><span data-ttu-id="77f8e-703">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-703">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-704">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-704">Fixed cost</span></span></td>
<td><span data-ttu-id="77f8e-705">713.75</span><span class="sxs-lookup"><span data-stu-id="77f8e-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-706">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="77f8e-707">CC003</span><span class="sxs-lookup"><span data-stu-id="77f8e-707">CC003</span></span></td>
<td><span data-ttu-id="77f8e-708">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="77f8e-708">Assembly</span></span></td>
<td><span data-ttu-id="77f8e-709">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-709">10001</span></span></td>
<td><span data-ttu-id="77f8e-710">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-710">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-711">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-711">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="77f8e-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-713">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="77f8e-714">CC003</span><span class="sxs-lookup"><span data-stu-id="77f8e-714">CC003</span></span></td>
<td><span data-ttu-id="77f8e-715">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="77f8e-715">Packaging</span></span></td>
<td><span data-ttu-id="77f8e-716">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-716">10001</span></span></td>
<td><span data-ttu-id="77f8e-717">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-717">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-718">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-718">Fixed cost</span></span></td>
<td><span data-ttu-id="77f8e-719">286.25</span><span class="sxs-lookup"><span data-stu-id="77f8e-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-720">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="77f8e-721">CC003</span><span class="sxs-lookup"><span data-stu-id="77f8e-721">CC003</span></span></td>
<td><span data-ttu-id="77f8e-722">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="77f8e-722">Packaging</span></span></td>
<td><span data-ttu-id="77f8e-723">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-723">10001</span></span></td>
<td><span data-ttu-id="77f8e-724">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-724">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-725">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-725">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="77f8e-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-727">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="77f8e-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-728">Prod 1</span></span></td>
<td><span data-ttu-id="77f8e-729">Producto 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-729">Product 1</span></span></td>
<td><span data-ttu-id="77f8e-730">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-730">10001</span></span></td>
<td><span data-ttu-id="77f8e-731">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-731">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-732">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-732">Fixed cost</span></span></td>
<td><span data-ttu-id="77f8e-733">776.36</span><span class="sxs-lookup"><span data-stu-id="77f8e-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-734">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="77f8e-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-735">Prod 1</span></span></td>
<td><span data-ttu-id="77f8e-736">Producto 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-736">Product 1</span></span></td>
<td><span data-ttu-id="77f8e-737">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-737">10001</span></span></td>
<td><span data-ttu-id="77f8e-738">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-738">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-739">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-739">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="77f8e-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-741">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="77f8e-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-742">Prod 2</span></span></td>
<td><span data-ttu-id="77f8e-743">Producto 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-743">Product 1</span></span></td>
<td><span data-ttu-id="77f8e-744">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-744">10001</span></span></td>
<td><span data-ttu-id="77f8e-745">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-745">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-746">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-746">Fixed cost</span></span></td>
<td><span data-ttu-id="77f8e-747">223.64</span><span class="sxs-lookup"><span data-stu-id="77f8e-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-748">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="77f8e-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-749">Prod 2</span></span></td>
<td><span data-ttu-id="77f8e-750">Producto 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-750">Product 1</span></span></td>
<td><span data-ttu-id="77f8e-751">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-751">10001</span></span></td>
<td><span data-ttu-id="77f8e-752">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-752">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-753">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-753">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="77f8e-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="77f8e-755">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="77f8e-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="77f8e-756">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="77f8e-757">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-757">Cost element</span></span></th>
<th><span data-ttu-id="77f8e-758">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="77f8e-758">Cost behavior</span></span></th>
<th><span data-ttu-id="77f8e-759">Importe</span><span class="sxs-lookup"><span data-stu-id="77f8e-759">Amount</span></span></th>
<th><span data-ttu-id="77f8e-760">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="77f8e-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="77f8e-761">CC001</span><span class="sxs-lookup"><span data-stu-id="77f8e-761">CC001</span></span></td>
<td><span data-ttu-id="77f8e-762">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="77f8e-762">HR</span></span></td>
<td><span data-ttu-id="77f8e-763">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-763">10001</span></span></td>
<td><span data-ttu-id="77f8e-764">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-764">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-765">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-765">Fixed cost</span></span></td>
<td><span data-ttu-id="77f8e-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-766">-500.00</span></span></td>
<td><span data-ttu-id="77f8e-767">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-768">CC002</span><span class="sxs-lookup"><span data-stu-id="77f8e-768">CC002</span></span></td>
<td><span data-ttu-id="77f8e-769">Finanzas</span><span class="sxs-lookup"><span data-stu-id="77f8e-769">Finance</span></span></td>
<td><span data-ttu-id="77f8e-770">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-770">10001</span></span></td>
<td><span data-ttu-id="77f8e-771">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-771">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-772">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-772">Fixed cost</span></span></td>
<td><span data-ttu-id="77f8e-773">175.00</span><span class="sxs-lookup"><span data-stu-id="77f8e-773">175.00</span></span></td>
<td><span data-ttu-id="77f8e-774">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-775">CC003</span><span class="sxs-lookup"><span data-stu-id="77f8e-775">CC003</span></span></td>
<td><span data-ttu-id="77f8e-776">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="77f8e-776">Assembly</span></span></td>
<td><span data-ttu-id="77f8e-777">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-777">10001</span></span></td>
<td><span data-ttu-id="77f8e-778">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-778">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-779">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-779">Fixed cost</span></span></td>
<td><span data-ttu-id="77f8e-780">275.00</span><span class="sxs-lookup"><span data-stu-id="77f8e-780">275.00</span></span></td>
<td><span data-ttu-id="77f8e-781">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-782">CC004</span><span class="sxs-lookup"><span data-stu-id="77f8e-782">CC004</span></span></td>
<td><span data-ttu-id="77f8e-783">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="77f8e-783">Packaging</span></span></td>
<td><span data-ttu-id="77f8e-784">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-784">10001</span></span></td>
<td><span data-ttu-id="77f8e-785">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-785">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-786">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-786">Fixed cost</span></span></td>
<td><span data-ttu-id="77f8e-787">50,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-787">50,00</span></span></td>
<td><span data-ttu-id="77f8e-788">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-789">CC001</span><span class="sxs-lookup"><span data-stu-id="77f8e-789">CC001</span></span></td>
<td><span data-ttu-id="77f8e-790">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="77f8e-790">HR</span></span></td>
<td><span data-ttu-id="77f8e-791">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-791">10001</span></span></td>
<td><span data-ttu-id="77f8e-792">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-792">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-793">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-793">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="77f8e-794">-1,245.71</span></span></td>
<td><span data-ttu-id="77f8e-795">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-796">CC002</span><span class="sxs-lookup"><span data-stu-id="77f8e-796">CC002</span></span></td>
<td><span data-ttu-id="77f8e-797">Finanzas</span><span class="sxs-lookup"><span data-stu-id="77f8e-797">Finance</span></span></td>
<td><span data-ttu-id="77f8e-798">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-798">10001</span></span></td>
<td><span data-ttu-id="77f8e-799">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-799">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-800">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-800">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-801">436.00</span><span class="sxs-lookup"><span data-stu-id="77f8e-801">436.00</span></span></td>
<td><span data-ttu-id="77f8e-802">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-803">CC003</span><span class="sxs-lookup"><span data-stu-id="77f8e-803">CC003</span></span></td>
<td><span data-ttu-id="77f8e-804">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="77f8e-804">Assembly</span></span></td>
<td><span data-ttu-id="77f8e-805">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-805">10001</span></span></td>
<td><span data-ttu-id="77f8e-806">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-806">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-807">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-807">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-808">685.14</span><span class="sxs-lookup"><span data-stu-id="77f8e-808">685.14</span></span></td>
<td><span data-ttu-id="77f8e-809">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-810">CC004</span><span class="sxs-lookup"><span data-stu-id="77f8e-810">CC004</span></span></td>
<td><span data-ttu-id="77f8e-811">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="77f8e-811">Packaging</span></span></td>
<td><span data-ttu-id="77f8e-812">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-812">10001</span></span></td>
<td><span data-ttu-id="77f8e-813">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-813">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-814">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-814">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-815">124.57</span><span class="sxs-lookup"><span data-stu-id="77f8e-815">124.57</span></span></td>
<td><span data-ttu-id="77f8e-816">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-817">CC002</span><span class="sxs-lookup"><span data-stu-id="77f8e-817">CC002</span></span></td>
<td><span data-ttu-id="77f8e-818">Finanzas</span><span class="sxs-lookup"><span data-stu-id="77f8e-818">Finance</span></span></td>
<td><span data-ttu-id="77f8e-819">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-819">10001</span></span></td>
<td><span data-ttu-id="77f8e-820">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-820">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-821">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-821">Fixed cost</span></span></td>
<td><span data-ttu-id="77f8e-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-822">-675.00</span></span></td>
<td><span data-ttu-id="77f8e-823">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-824">CC003</span><span class="sxs-lookup"><span data-stu-id="77f8e-824">CC003</span></span></td>
<td><span data-ttu-id="77f8e-825">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="77f8e-825">Assembly</span></span></td>
<td><span data-ttu-id="77f8e-826">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-826">10001</span></span></td>
<td><span data-ttu-id="77f8e-827">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-827">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-828">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-828">Fixed cost</span></span></td>
<td><span data-ttu-id="77f8e-829">438.75</span><span class="sxs-lookup"><span data-stu-id="77f8e-829">438.75</span></span></td>
<td><span data-ttu-id="77f8e-830">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-831">CC004</span><span class="sxs-lookup"><span data-stu-id="77f8e-831">CC004</span></span></td>
<td><span data-ttu-id="77f8e-832">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="77f8e-832">Packaging</span></span></td>
<td><span data-ttu-id="77f8e-833">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-833">10001</span></span></td>
<td><span data-ttu-id="77f8e-834">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-834">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-835">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-835">Fixed cost</span></span></td>
<td><span data-ttu-id="77f8e-836">236.25</span><span class="sxs-lookup"><span data-stu-id="77f8e-836">236.25</span></span></td>
<td><span data-ttu-id="77f8e-837">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-838">CC002</span><span class="sxs-lookup"><span data-stu-id="77f8e-838">CC002</span></span></td>
<td><span data-ttu-id="77f8e-839">Finanzas</span><span class="sxs-lookup"><span data-stu-id="77f8e-839">Finance</span></span></td>
<td><span data-ttu-id="77f8e-840">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-840">10001</span></span></td>
<td><span data-ttu-id="77f8e-841">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-841">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-842">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-842">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="77f8e-843">-8,150.29</span></span></td>
<td><span data-ttu-id="77f8e-844">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-845">CC003</span><span class="sxs-lookup"><span data-stu-id="77f8e-845">CC003</span></span></td>
<td><span data-ttu-id="77f8e-846">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="77f8e-846">Assembly</span></span></td>
<td><span data-ttu-id="77f8e-847">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-847">10001</span></span></td>
<td><span data-ttu-id="77f8e-848">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-848">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-849">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-849">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="77f8e-850">5,297.69</span></span></td>
<td><span data-ttu-id="77f8e-851">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-852">CC004</span><span class="sxs-lookup"><span data-stu-id="77f8e-852">CC004</span></span></td>
<td><span data-ttu-id="77f8e-853">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="77f8e-853">Packaging</span></span></td>
<td><span data-ttu-id="77f8e-854">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-854">10001</span></span></td>
<td><span data-ttu-id="77f8e-855">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-855">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-856">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-856">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="77f8e-857">2,852.60</span></span></td>
<td><span data-ttu-id="77f8e-858">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-859">CC003</span><span class="sxs-lookup"><span data-stu-id="77f8e-859">CC003</span></span></td>
<td><span data-ttu-id="77f8e-860">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="77f8e-860">Assembly</span></span></td>
<td><span data-ttu-id="77f8e-861">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-861">10001</span></span></td>
<td><span data-ttu-id="77f8e-862">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-862">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-863">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-863">Fixed cost</span></span></td>
<td><span data-ttu-id="77f8e-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="77f8e-864">-713.75</span></span></td>
<td><span data-ttu-id="77f8e-865">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-866">Prod 1</span></span></td>
<td><span data-ttu-id="77f8e-867">Producto 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-867">Product 1</span></span></td>
<td><span data-ttu-id="77f8e-868">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-868">10001</span></span></td>
<td><span data-ttu-id="77f8e-869">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-869">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-870">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-870">Fixed cost</span></span></td>
<td><span data-ttu-id="77f8e-871">535.31</span><span class="sxs-lookup"><span data-stu-id="77f8e-871">535.31</span></span></td>
<td><span data-ttu-id="77f8e-872">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-873">Prod 2</span></span></td>
<td><span data-ttu-id="77f8e-874">Producto 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-874">Product 2</span></span></td>
<td><span data-ttu-id="77f8e-875">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-875">10001</span></span></td>
<td><span data-ttu-id="77f8e-876">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-876">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-877">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-877">Fixed cost</span></span></td>
<td><span data-ttu-id="77f8e-878">178.44</span><span class="sxs-lookup"><span data-stu-id="77f8e-878">178.44</span></span></td>
<td><span data-ttu-id="77f8e-879">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-880">CC003</span><span class="sxs-lookup"><span data-stu-id="77f8e-880">CC003</span></span></td>
<td><span data-ttu-id="77f8e-881">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="77f8e-881">Assembly</span></span></td>
<td><span data-ttu-id="77f8e-882">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-882">10001</span></span></td>
<td><span data-ttu-id="77f8e-883">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-883">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-884">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-884">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="77f8e-885">-5,982.83</span></span></td>
<td><span data-ttu-id="77f8e-886">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-887">Prod 1</span></span></td>
<td><span data-ttu-id="77f8e-888">Producto 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-888">Product 1</span></span></td>
<td><span data-ttu-id="77f8e-889">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-889">10001</span></span></td>
<td><span data-ttu-id="77f8e-890">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-890">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-891">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-891">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="77f8e-892">4,487.12</span></span></td>
<td><span data-ttu-id="77f8e-893">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-894">Prod 2</span></span></td>
<td><span data-ttu-id="77f8e-895">Producto 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-895">Product 2</span></span></td>
<td><span data-ttu-id="77f8e-896">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-896">10001</span></span></td>
<td><span data-ttu-id="77f8e-897">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-897">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-898">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-898">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="77f8e-899">1,495.71</span></span></td>
<td><span data-ttu-id="77f8e-900">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-901">CC003</span><span class="sxs-lookup"><span data-stu-id="77f8e-901">CC003</span></span></td>
<td><span data-ttu-id="77f8e-902">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="77f8e-902">Assembly</span></span></td>
<td><span data-ttu-id="77f8e-903">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-903">10001</span></span></td>
<td><span data-ttu-id="77f8e-904">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-904">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-905">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-905">Fixed cost</span></span></td>
<td><span data-ttu-id="77f8e-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="77f8e-906">-286.25</span></span></td>
<td><span data-ttu-id="77f8e-907">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-908">Prod 1</span></span></td>
<td><span data-ttu-id="77f8e-909">Producto 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-909">Product 1</span></span></td>
<td><span data-ttu-id="77f8e-910">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-910">10001</span></span></td>
<td><span data-ttu-id="77f8e-911">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-911">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-912">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-912">Fixed cost</span></span></td>
<td><span data-ttu-id="77f8e-913">241.05</span><span class="sxs-lookup"><span data-stu-id="77f8e-913">241.05</span></span></td>
<td><span data-ttu-id="77f8e-914">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-915">Prod 2</span></span></td>
<td><span data-ttu-id="77f8e-916">Producto 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-916">Product 2</span></span></td>
<td><span data-ttu-id="77f8e-917">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-917">10001</span></span></td>
<td><span data-ttu-id="77f8e-918">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-918">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-919">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-919">Fixed cost</span></span></td>
<td><span data-ttu-id="77f8e-920">45.20</span><span class="sxs-lookup"><span data-stu-id="77f8e-920">45.20</span></span></td>
<td><span data-ttu-id="77f8e-921">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-922">CC003</span><span class="sxs-lookup"><span data-stu-id="77f8e-922">CC003</span></span></td>
<td><span data-ttu-id="77f8e-923">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="77f8e-923">Assembly</span></span></td>
<td><span data-ttu-id="77f8e-924">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-924">10001</span></span></td>
<td><span data-ttu-id="77f8e-925">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-925">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-926">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-926">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="77f8e-927">-2,977.17</span></span></td>
<td><span data-ttu-id="77f8e-928">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-929">Prod 1</span></span></td>
<td><span data-ttu-id="77f8e-930">Producto 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-930">Product 1</span></span></td>
<td><span data-ttu-id="77f8e-931">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-931">10001</span></span></td>
<td><span data-ttu-id="77f8e-932">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-932">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-933">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-933">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="77f8e-934">2,507.09</span></span></td>
<td><span data-ttu-id="77f8e-935">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="77f8e-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-936">Prod 2</span></span></td>
<td><span data-ttu-id="77f8e-937">Producto 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-937">Product 2</span></span></td>
<td><span data-ttu-id="77f8e-938">10001</span><span class="sxs-lookup"><span data-stu-id="77f8e-938">10001</span></span></td>
<td><span data-ttu-id="77f8e-939">Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-939">Electricity</span></span></td>
<td><span data-ttu-id="77f8e-940">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-940">Variable cost</span></span></td>
<td><span data-ttu-id="77f8e-941">470.08</span><span class="sxs-lookup"><span data-stu-id="77f8e-941">470.08</span></span></td>
<td><span data-ttu-id="77f8e-942">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="77f8e-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="77f8e-943">Conclusión</span><span class="sxs-lookup"><span data-stu-id="77f8e-943">Conclusion</span></span>
<span data-ttu-id="77f8e-944">En la contabilidad financiera, un coste de 10.000,00 para electricidad se envía a un identificador ficticio de centro de coste.</span><span class="sxs-lookup"><span data-stu-id="77f8e-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="77f8e-945">Por lo tanto, los contables de coste sabrán que este coste se debe asignar.</span><span class="sxs-lookup"><span data-stu-id="77f8e-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="77f8e-946">En contabilidad de costes, los costes fluyen en las unidades organizativas y los niveles en función de las directivas y las reglas que se aplican.</span><span class="sxs-lookup"><span data-stu-id="77f8e-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="77f8e-947">Cada coste se ha asociado con una base de asignación que proporciona la mejor evaluación para la asignación de costes.</span><span class="sxs-lookup"><span data-stu-id="77f8e-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="77f8e-948">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="77f8e-949">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="77f8e-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="77f8e-950">Total</span><span class="sxs-lookup"><span data-stu-id="77f8e-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="77f8e-951">CC099</span><span class="sxs-lookup"><span data-stu-id="77f8e-951">CC099</span></span></th>
<th><span data-ttu-id="77f8e-952">CC001</span><span class="sxs-lookup"><span data-stu-id="77f8e-952">CC001</span></span></th>
<th><span data-ttu-id="77f8e-953">CC002</span><span class="sxs-lookup"><span data-stu-id="77f8e-953">CC002</span></span></th>
<th><span data-ttu-id="77f8e-954">CC003</span><span class="sxs-lookup"><span data-stu-id="77f8e-954">CC003</span></span></th>
<th><span data-ttu-id="77f8e-955">CC004</span><span class="sxs-lookup"><span data-stu-id="77f8e-955">CC004</span></span></th>
<th><span data-ttu-id="77f8e-956">Proy 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-956">Proj 1</span></span></th>
<th><span data-ttu-id="77f8e-957">Proy 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-957">Proj 2</span></span></th>
<th><span data-ttu-id="77f8e-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="77f8e-958">Prod 1</span></span></th>
<th><span data-ttu-id="77f8e-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="77f8e-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="77f8e-960">10001 Electricidad</span><span class="sxs-lookup"><span data-stu-id="77f8e-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="77f8e-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="77f8e-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="77f8e-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="77f8e-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="77f8e-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="77f8e-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="77f8e-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="77f8e-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="77f8e-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="77f8e-970">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="77f8e-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-971">0,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="77f8e-972">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="77f8e-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-973">0,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-974">0,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-975">0,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-976">0,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-977">0,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-978">776.36</span><span class="sxs-lookup"><span data-stu-id="77f8e-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-979">223.64</span><span class="sxs-lookup"><span data-stu-id="77f8e-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="77f8e-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="77f8e-981">Coste variable</span><span class="sxs-lookup"><span data-stu-id="77f8e-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-982">000</span><span class="sxs-lookup"><span data-stu-id="77f8e-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-983">0,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-984">0,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-985">0,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-986">0,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-987">30,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-988">10,00</span><span class="sxs-lookup"><span data-stu-id="77f8e-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="77f8e-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="77f8e-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="77f8e-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="77f8e-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="77f8e-992">Este tema muestra cómo un artículo de costes principales, 10001 Electricidad, fluye por los objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="77f8e-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="77f8e-993">Por tanto, estos gastos generales se asignan al nivel más bajo de la organización.</span><span class="sxs-lookup"><span data-stu-id="77f8e-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="77f8e-994">Es decir, los objetos de coste del nivel más bajo son los que soportan el coste.</span><span class="sxs-lookup"><span data-stu-id="77f8e-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="77f8e-995">Si necesita un flujo visual del coste entre los objetos de coste, puede usar las reglas de directivas de acumulación de costes para visualizar el flujo del coste.</span><span class="sxs-lookup"><span data-stu-id="77f8e-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="77f8e-996">Para obtener más información, consulte [Acumulación de costes](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="77f8e-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>




