---
title: "Cálculo de costes generales"
description: "Este tema describe los procesos típicos para calcular y asignar costes generales."
author: YuyuScheller
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 1eb5560ba795ab6df61b5af889049810dd00d79e
ms.contentlocale: es-es
ms.lasthandoff: 06/29/2017


---

# <a name="overhead-calculation"></a><span data-ttu-id="d6400-103">Cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="d6400-103">Overhead calculation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="d6400-104">Este tema describe los procesos típicos para calcular y asignar costes generales.</span><span class="sxs-lookup"><span data-stu-id="d6400-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="d6400-105">Definición del término</span><span class="sxs-lookup"><span data-stu-id="d6400-105">Term definition</span></span>
---------------

<span data-ttu-id="d6400-106">Los costes generales son costes que se contraen para dirigir un negocio, pero que no pueden ser atribuidos directamente a ninguna actividad empresarial, productos, o servicio específicos.</span><span class="sxs-lookup"><span data-stu-id="d6400-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="d6400-107">Los costes generales proporcionan un soporte fundamental a la generación de actividades rentables.</span><span class="sxs-lookup"><span data-stu-id="d6400-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="d6400-108">Algunos ejemplos de costes generales son:</span><span class="sxs-lookup"><span data-stu-id="d6400-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="d6400-109">Alquiler</span><span class="sxs-lookup"><span data-stu-id="d6400-109">Rent</span></span>
-   <span data-ttu-id="d6400-110">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-110">Electricity</span></span>
-   <span data-ttu-id="d6400-111">Sueldos administrativos</span><span class="sxs-lookup"><span data-stu-id="d6400-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="d6400-112">Visión general del cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="d6400-112">Overhead calculation overview</span></span>
<span data-ttu-id="d6400-113">El cálculo de costes generales ejecuta las directivas de contabilidad de costes en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="d6400-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="d6400-114">Puede calcular varias veces los costes generales del mismo período fiscal si se han cambiado las directivas de contabilidad de costes o se han detectado errores específicos.</span><span class="sxs-lookup"><span data-stu-id="d6400-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="d6400-115">Cada ejecución del cálculo de costes generales se almacena y recibe un identificador de versión único que permite comparar los cálculos de diferentes versiones.</span><span class="sxs-lookup"><span data-stu-id="d6400-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="d6400-116">Las entradas de costes que el cálculo de costes generales genera reciben una fecha de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="d6400-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="d6400-117">Esta fecha de contabilidad coincide con la fecha final del período fiscal que se usa en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="d6400-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="d6400-118">El identificador de versión único consiste en los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d6400-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="d6400-119">Tipo de versión</span><span class="sxs-lookup"><span data-stu-id="d6400-119">Version type</span></span>
-   <span data-ttu-id="d6400-120">Fecha y hora</span><span class="sxs-lookup"><span data-stu-id="d6400-120">Date and time</span></span>
-   <span data-ttu-id="d6400-121">Libro mayor de contabilidad de costes</span><span class="sxs-lookup"><span data-stu-id="d6400-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="d6400-122">Ejercicio</span><span class="sxs-lookup"><span data-stu-id="d6400-122">Fiscal year</span></span>
-   <span data-ttu-id="d6400-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="d6400-123">Fiscal period</span></span>

<span data-ttu-id="d6400-124">El cálculo de costes generales se ejecuta independientemente de la versión.</span><span class="sxs-lookup"><span data-stu-id="d6400-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="d6400-125">Por lo tanto, puede calcular la versión de presupuesto antes que la versión real.</span><span class="sxs-lookup"><span data-stu-id="d6400-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="d6400-126">El cálculo de costes generales consta de cuatro pasos, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="d6400-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="d6400-127">En cada paso, se crea una cabecera de diario que tiene entradas del diario.</span><span class="sxs-lookup"><span data-stu-id="d6400-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="d6400-128">Esta cabecera de diario guarda los datos de entrada para cada paso de cálculo.</span><span class="sxs-lookup"><span data-stu-id="d6400-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="d6400-129">Las directivas y las reglas se aplican a cada línea de diario, y las entradas de coste se generan como resultado.</span><span class="sxs-lookup"><span data-stu-id="d6400-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="d6400-130">Por tanto, siempre se tiene rastreabilidad completa.</span><span class="sxs-lookup"><span data-stu-id="d6400-130">Therefore, you always have full traceability.</span></span> 
<span data-ttu-id="d6400-131">[![Cálculo de costes generales](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="d6400-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="d6400-132">Calcular y asignar costes generales de electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="d6400-133">En la contabilidad financiera, algunos costes, como la electricidad, se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="d6400-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="d6400-134">Por lo tanto, no se proporciona una visión de gestión detallada para la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="d6400-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="d6400-135">En contabilidad de costes, para proporcionar información de gestión correcta en todas las unidades y niveles organizativos, los costes deben fluir por las unidades organizativas.</span><span class="sxs-lookup"><span data-stu-id="d6400-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="d6400-136">Este flujo se debe basar en cualquier registro preciso de consumo o en una evaluación justa.</span><span class="sxs-lookup"><span data-stu-id="d6400-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="d6400-137">En la contabilidad general, un coste de la electricidad se puede registrar como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="d6400-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d6400-138">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="d6400-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="d6400-139">Centro de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="d6400-140">Cuenta principal</span><span class="sxs-lookup"><span data-stu-id="d6400-140">Main account</span></span></th>
<th><span data-ttu-id="d6400-141">Importe en la divisa de contabilidad</span><span class="sxs-lookup"><span data-stu-id="d6400-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-142">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="d6400-143">CC099</span><span class="sxs-lookup"><span data-stu-id="d6400-143">CC099</span></span></td>
<td><span data-ttu-id="d6400-144">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="d6400-144">Default cost center</span></span></td>
<td><span data-ttu-id="d6400-145">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-145">10001</span></span></td>
<td><span data-ttu-id="d6400-146">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-146">Electricity</span></span></td>
<td><span data-ttu-id="d6400-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="d6400-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="d6400-148">Paso 1: Procese el cálculo del comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="d6400-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="d6400-149">De forma predeterminada, cuando las entradas de coste se importan de los datos de origen, reciben la clasificación de comportamiento del coste **Sin ordenar** en la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="d6400-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="d6400-150">Aplicando reglas de directivas de comportamiento de coste, puede reclasificar entradas de coste como **Coste fijo** o **Coste variable**.</span><span class="sxs-lookup"><span data-stu-id="d6400-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="d6400-151">Defina la regla de comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="d6400-151">Define the cost behavior rule</span></span>

<span data-ttu-id="d6400-152">En algunos casos, parte del coste es una cuota fija, y el coste pendiente se basa en el consumo.</span><span class="sxs-lookup"><span data-stu-id="d6400-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="d6400-153">Las facturas de electricidad coinciden a menudo con esta definición.</span><span class="sxs-lookup"><span data-stu-id="d6400-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="d6400-154">Tras pagar una cuota fija específica, paga el consumo por kilovatio-hora (Kwh).</span><span class="sxs-lookup"><span data-stu-id="d6400-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="d6400-155">Por ejemplo, si la cuota de coste fijo es de 1.000,00, la regla de comportamiento del coste se define como sigue:</span><span class="sxs-lookup"><span data-stu-id="d6400-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="d6400-156">Importe fijo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="d6400-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="d6400-157">0 &lt;= 1.000,00 = Fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="d6400-158">1.000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="d6400-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="d6400-159">Diario</span><span class="sxs-lookup"><span data-stu-id="d6400-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d6400-160">Diario</span><span class="sxs-lookup"><span data-stu-id="d6400-160">Journal</span></span></th>
<th><span data-ttu-id="d6400-161">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="d6400-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="d6400-162">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="d6400-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="d6400-163">Versión</span><span class="sxs-lookup"><span data-stu-id="d6400-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-164">00001</span><span class="sxs-lookup"><span data-stu-id="d6400-164">00001</span></span></td>
<td><span data-ttu-id="d6400-165">Diario de cálculo de comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="d6400-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="d6400-166">Fiscal</span><span class="sxs-lookup"><span data-stu-id="d6400-166">Fiscal</span></span></td>
<td><span data-ttu-id="d6400-167">2017</span><span class="sxs-lookup"><span data-stu-id="d6400-167">2017</span></span></td>
<td><span data-ttu-id="d6400-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="d6400-168">Period 1</span></span></td>
<td><span data-ttu-id="d6400-169">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="d6400-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="d6400-170">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="d6400-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d6400-171">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="d6400-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="d6400-172">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d6400-173">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-173">Cost element</span></span></th>
<th><span data-ttu-id="d6400-174">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="d6400-174">Cost behavior</span></span></th>
<th><span data-ttu-id="d6400-175">Importe</span><span class="sxs-lookup"><span data-stu-id="d6400-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-176">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="d6400-177">CC099</span><span class="sxs-lookup"><span data-stu-id="d6400-177">CC099</span></span></td>
<td><span data-ttu-id="d6400-178">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="d6400-178">Default cost center</span></span></td>
<td><span data-ttu-id="d6400-179">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-179">10001</span></span></td>
<td><span data-ttu-id="d6400-180">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-180">Electricity</span></span></td>
<td><span data-ttu-id="d6400-181">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="d6400-181">Unclassified</span></span></td>
<td><span data-ttu-id="d6400-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="d6400-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="d6400-183">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="d6400-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6400-184">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d6400-185">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-185">Cost element</span></span></th>
<th><span data-ttu-id="d6400-186">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="d6400-186">Cost behavior</span></span></th>
<th><span data-ttu-id="d6400-187">Importe</span><span class="sxs-lookup"><span data-stu-id="d6400-187">Amount</span></span></th>
<th><span data-ttu-id="d6400-188">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="d6400-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-189">CC099</span><span class="sxs-lookup"><span data-stu-id="d6400-189">CC099</span></span></td>
<td><span data-ttu-id="d6400-190">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="d6400-190">Default cost center</span></span></td>
<td><span data-ttu-id="d6400-191">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-191">10001</span></span></td>
<td><span data-ttu-id="d6400-192">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-192">Electricity</span></span></td>
<td><span data-ttu-id="d6400-193">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="d6400-193">Unclassified</span></span></td>
<td><span data-ttu-id="d6400-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="d6400-194">10,000.00</span></span></td>
<td><span data-ttu-id="d6400-195">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-196">CC099</span><span class="sxs-lookup"><span data-stu-id="d6400-196">CC099</span></span></td>
<td><span data-ttu-id="d6400-197">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="d6400-197">Default cost center</span></span></td>
<td><span data-ttu-id="d6400-198">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-198">10001</span></span></td>
<td><span data-ttu-id="d6400-199">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-199">Electricity</span></span></td>
<td><span data-ttu-id="d6400-200">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="d6400-200">Unclassified</span></span></td>
<td><span data-ttu-id="d6400-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="d6400-201">-10,000.00</span></span></td>
<td><span data-ttu-id="d6400-202">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-203">CC099</span><span class="sxs-lookup"><span data-stu-id="d6400-203">CC099</span></span></td>
<td><span data-ttu-id="d6400-204">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="d6400-204">Default cost center</span></span></td>
<td><span data-ttu-id="d6400-205">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-205">10001</span></span></td>
<td><span data-ttu-id="d6400-206">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-206">Electricity</span></span></td>
<td><span data-ttu-id="d6400-207">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-207">Fixed cost</span></span></td>
<td><span data-ttu-id="d6400-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="d6400-208">1,000.00</span></span></td>
<td><span data-ttu-id="d6400-209">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-210">CC099</span><span class="sxs-lookup"><span data-stu-id="d6400-210">CC099</span></span></td>
<td><span data-ttu-id="d6400-211">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="d6400-211">Default cost center</span></span></td>
<td><span data-ttu-id="d6400-212">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-212">10001</span></span></td>
<td><span data-ttu-id="d6400-213">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-213">Electricity</span></span></td>
<td><span data-ttu-id="d6400-214">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-214">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="d6400-215">9,000.00</span></span></td>
<td><span data-ttu-id="d6400-216">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6400-217">Para obtener información detallada sobre el comportamiento del coste, consulte Directiva de comportamiento de costes.</span><span class="sxs-lookup"><span data-stu-id="d6400-217">For detailed information about cost behavior, see Cost behavior policy.</span></span> <span data-ttu-id="d6400-218">(Tenga en cuenta que este tema no se ha completado aún, pero pronto se abordará).</span><span class="sxs-lookup"><span data-stu-id="d6400-218">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="d6400-219">Paso 2: Procese el cálculo de distribución de costes</span><span class="sxs-lookup"><span data-stu-id="d6400-219">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="d6400-220">La distribución de costes se usa para redistribuir costes desde un objeto de coste a uno o más objetos de coste aplicando una base relevante de la asignación.</span><span class="sxs-lookup"><span data-stu-id="d6400-220">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="d6400-221">La distribución de costes y la asignación de costes difieren en que la distribución de costes siempre se produce en el nivel de elemento de costes principal del coste original.</span><span class="sxs-lookup"><span data-stu-id="d6400-221">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="d6400-222">Defina la regla de distribución del coste</span><span class="sxs-lookup"><span data-stu-id="d6400-222">Define the cost distribution rule</span></span>

<span data-ttu-id="d6400-223">En la contabilidad financiera, los costes de electricidad se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="d6400-223">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="d6400-224">En contabilidad de costes, este método no es suficientemente detallado.</span><span class="sxs-lookup"><span data-stu-id="d6400-224">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="d6400-225">El coste variable debe distribuirse a los objetos individuales de coste aplicando una base justa.</span><span class="sxs-lookup"><span data-stu-id="d6400-225">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="d6400-226">La base de asignación más lógica es el consumo de electricidad (Kwh).</span><span class="sxs-lookup"><span data-stu-id="d6400-226">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="d6400-227">Se crea un miembro de dimensión estadística que se denomina Electricity, y se registra el consumo de electricidad.</span><span class="sxs-lookup"><span data-stu-id="d6400-227">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="d6400-228">De forma predeterminada, todos los miembros de dimensión estadísticos estarán disponibles como bases de asignación.</span><span class="sxs-lookup"><span data-stu-id="d6400-228">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6400-229">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-229">Cost object</span></span></th>
<th><span data-ttu-id="d6400-230">Kwh</span><span class="sxs-lookup"><span data-stu-id="d6400-230">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-231">CC001</span><span class="sxs-lookup"><span data-stu-id="d6400-231">CC001</span></span></td>
<td><span data-ttu-id="d6400-232">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="d6400-232">HR</span></span></td>
<td><span data-ttu-id="d6400-233">1.000</span><span class="sxs-lookup"><span data-stu-id="d6400-233">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-234">CC002</span><span class="sxs-lookup"><span data-stu-id="d6400-234">CC002</span></span></td>
<td><span data-ttu-id="d6400-235">Finanzas</span><span class="sxs-lookup"><span data-stu-id="d6400-235">Finance</span></span></td>
<td><span data-ttu-id="d6400-236">6.000</span><span class="sxs-lookup"><span data-stu-id="d6400-236">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-237">CC003</span><span class="sxs-lookup"><span data-stu-id="d6400-237">CC003</span></span></td>
<td><span data-ttu-id="d6400-238">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="d6400-238">Assembly</span></span></td>
<td><span data-ttu-id="d6400-239">0</span><span class="sxs-lookup"><span data-stu-id="d6400-239">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6400-240">La tabla siguiente muestra el resultado cuando se aplica el consumo de electricidad como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="d6400-240">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6400-241">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-241">Cost object</span></span></th>
<th><span data-ttu-id="d6400-242">Magnitud</span><span class="sxs-lookup"><span data-stu-id="d6400-242">Magnitude</span></span></th>
<th><span data-ttu-id="d6400-243">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="d6400-243">Allocation factor</span></span></th>
<th><span data-ttu-id="d6400-244">Importe</span><span class="sxs-lookup"><span data-stu-id="d6400-244">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-245">CC001</span><span class="sxs-lookup"><span data-stu-id="d6400-245">CC001</span></span></td>
<td><span data-ttu-id="d6400-246">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="d6400-246">HR</span></span></td>
<td><span data-ttu-id="d6400-247">1.000</span><span class="sxs-lookup"><span data-stu-id="d6400-247">1,000</span></span></td>
<td><span data-ttu-id="d6400-248">(1.000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="d6400-248">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="d6400-249">1,285.71</span><span class="sxs-lookup"><span data-stu-id="d6400-249">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-250">CC002</span><span class="sxs-lookup"><span data-stu-id="d6400-250">CC002</span></span></td>
<td><span data-ttu-id="d6400-251">Finanzas</span><span class="sxs-lookup"><span data-stu-id="d6400-251">Finance</span></span></td>
<td><span data-ttu-id="d6400-252">6.000</span><span class="sxs-lookup"><span data-stu-id="d6400-252">6,000</span></span></td>
<td><span data-ttu-id="d6400-253">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="d6400-253">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="d6400-254">7,714.29</span><span class="sxs-lookup"><span data-stu-id="d6400-254">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-255">CC003</span><span class="sxs-lookup"><span data-stu-id="d6400-255">CC003</span></span></td>
<td><span data-ttu-id="d6400-256">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="d6400-256">Assembly</span></span></td>
<td><span data-ttu-id="d6400-257">0</span><span class="sxs-lookup"><span data-stu-id="d6400-257">0</span></span></td>
<td><span data-ttu-id="d6400-258">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="d6400-258">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="d6400-259">0,00</span><span class="sxs-lookup"><span data-stu-id="d6400-259">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6400-260">El coste fijo debe distribuirse uniformemente a los objetos individuales de costes que han consumido electricidad.</span><span class="sxs-lookup"><span data-stu-id="d6400-260">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="d6400-261">Puede obtener este resultado usando el miembro de dimensión estadístico de electricidad en una base de asignación de la fórmula: (Electricidad &gt; 0,00) La tabla siguiente muestra el resultado cuando el consumo de electricidad se aplica como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="d6400-261">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6400-262">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-262">Cost object</span></span></th>
<th><span data-ttu-id="d6400-263">Fórmula</span><span class="sxs-lookup"><span data-stu-id="d6400-263">Formula</span></span></th>
<th><span data-ttu-id="d6400-264">Magnitud</span><span class="sxs-lookup"><span data-stu-id="d6400-264">Magnitude</span></span></th>
<th><span data-ttu-id="d6400-265">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="d6400-265">Allocation factor</span></span></th>
<th><span data-ttu-id="d6400-266">Importe</span><span class="sxs-lookup"><span data-stu-id="d6400-266">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-267">CC001</span><span class="sxs-lookup"><span data-stu-id="d6400-267">CC001</span></span></td>
<td><span data-ttu-id="d6400-268">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="d6400-268">HR</span></span></td>
<td><span data-ttu-id="d6400-269">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="d6400-269">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="d6400-270">1</span><span class="sxs-lookup"><span data-stu-id="d6400-270">1</span></span></td>
<td><span data-ttu-id="d6400-271">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="d6400-271">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="d6400-272">500,00</span><span class="sxs-lookup"><span data-stu-id="d6400-272">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-273">CC002</span><span class="sxs-lookup"><span data-stu-id="d6400-273">CC002</span></span></td>
<td><span data-ttu-id="d6400-274">Finanzas</span><span class="sxs-lookup"><span data-stu-id="d6400-274">Finance</span></span></td>
<td><span data-ttu-id="d6400-275">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="d6400-275">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="d6400-276">1</span><span class="sxs-lookup"><span data-stu-id="d6400-276">1</span></span></td>
<td><span data-ttu-id="d6400-277">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="d6400-277">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="d6400-278">500,00</span><span class="sxs-lookup"><span data-stu-id="d6400-278">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-279">CC003</span><span class="sxs-lookup"><span data-stu-id="d6400-279">CC003</span></span></td>
<td><span data-ttu-id="d6400-280">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="d6400-280">Assembly</span></span></td>
<td><span data-ttu-id="d6400-281">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="d6400-281">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="d6400-282">0</span><span class="sxs-lookup"><span data-stu-id="d6400-282">0</span></span></td>
<td><span data-ttu-id="d6400-283">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="d6400-283">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="d6400-284">0,00</span><span class="sxs-lookup"><span data-stu-id="d6400-284">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="d6400-285">Diario</span><span class="sxs-lookup"><span data-stu-id="d6400-285">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d6400-286">Diario</span><span class="sxs-lookup"><span data-stu-id="d6400-286">Journal</span></span></th>
<th><span data-ttu-id="d6400-287">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="d6400-287">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="d6400-288">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="d6400-288">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="d6400-289">Versión</span><span class="sxs-lookup"><span data-stu-id="d6400-289">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-290">00002</span><span class="sxs-lookup"><span data-stu-id="d6400-290">00002</span></span></td>
<td><span data-ttu-id="d6400-291">Diario de cálculo de la distribución de costes</span><span class="sxs-lookup"><span data-stu-id="d6400-291">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="d6400-292">Fiscal</span><span class="sxs-lookup"><span data-stu-id="d6400-292">Fiscal</span></span></td>
<td><span data-ttu-id="d6400-293">2017</span><span class="sxs-lookup"><span data-stu-id="d6400-293">2017</span></span></td>
<td><span data-ttu-id="d6400-294">Período 1</span><span class="sxs-lookup"><span data-stu-id="d6400-294">Period 1</span></span></td>
<td><span data-ttu-id="d6400-295">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="d6400-295">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="d6400-296">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="d6400-296">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d6400-297">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="d6400-297">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="d6400-298">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-298">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d6400-299">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-299">Cost element</span></span></th>
<th><span data-ttu-id="d6400-300">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="d6400-300">Cost behavior</span></span></th>
<th><span data-ttu-id="d6400-301">Importe</span><span class="sxs-lookup"><span data-stu-id="d6400-301">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-302">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-302">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6400-303">CC099</span><span class="sxs-lookup"><span data-stu-id="d6400-303">CC099</span></span></td>
<td><span data-ttu-id="d6400-304">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="d6400-304">Default cost center</span></span></td>
<td><span data-ttu-id="d6400-305">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-305">10001</span></span></td>
<td><span data-ttu-id="d6400-306">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-306">Electricity</span></span></td>
<td><span data-ttu-id="d6400-307">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-307">Fixed cost</span></span></td>
<td><span data-ttu-id="d6400-308">1.000,00</span><span class="sxs-lookup"><span data-stu-id="d6400-308">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-309">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-309">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6400-310">CC099</span><span class="sxs-lookup"><span data-stu-id="d6400-310">CC099</span></span></td>
<td><span data-ttu-id="d6400-311">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="d6400-311">Default cost center</span></span></td>
<td><span data-ttu-id="d6400-312">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-312">10001</span></span></td>
<td><span data-ttu-id="d6400-313">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-313">Electricity</span></span></td>
<td><span data-ttu-id="d6400-314">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-314">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-315">9.000,00</span><span class="sxs-lookup"><span data-stu-id="d6400-315">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="d6400-316">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="d6400-316">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6400-317">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-317">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d6400-318">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-318">Cost element</span></span></th>
<th><span data-ttu-id="d6400-319">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="d6400-319">Cost behavior</span></span></th>
<th><span data-ttu-id="d6400-320">Importe</span><span class="sxs-lookup"><span data-stu-id="d6400-320">Amount</span></span></th>
<th><span data-ttu-id="d6400-321">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="d6400-321">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-322">CC099</span><span class="sxs-lookup"><span data-stu-id="d6400-322">CC099</span></span></td>
<td><span data-ttu-id="d6400-323">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="d6400-323">Default cost center</span></span></td>
<td><span data-ttu-id="d6400-324">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-324">10001</span></span></td>
<td><span data-ttu-id="d6400-325">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-325">Electricity</span></span></td>
<td><span data-ttu-id="d6400-326">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-326">Fixed cost</span></span></td>
<td><span data-ttu-id="d6400-327">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="d6400-327">-1,000.00</span></span></td>
<td><span data-ttu-id="d6400-328">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-328">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-329">CC001</span><span class="sxs-lookup"><span data-stu-id="d6400-329">CC001</span></span></td>
<td><span data-ttu-id="d6400-330">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="d6400-330">HR</span></span></td>
<td><span data-ttu-id="d6400-331">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-331">10001</span></span></td>
<td><span data-ttu-id="d6400-332">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-332">Electricity</span></span></td>
<td><span data-ttu-id="d6400-333">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-333">Fixed cost</span></span></td>
<td><span data-ttu-id="d6400-334">500,00</span><span class="sxs-lookup"><span data-stu-id="d6400-334">500.00</span></span></td>
<td><span data-ttu-id="d6400-335">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-335">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-336">CC002</span><span class="sxs-lookup"><span data-stu-id="d6400-336">CC002</span></span></td>
<td><span data-ttu-id="d6400-337">Finanzas</span><span class="sxs-lookup"><span data-stu-id="d6400-337">Finance</span></span></td>
<td><span data-ttu-id="d6400-338">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-338">10001</span></span></td>
<td><span data-ttu-id="d6400-339">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-339">Electricity</span></span></td>
<td><span data-ttu-id="d6400-340">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-340">Fixed cost</span></span></td>
<td><span data-ttu-id="d6400-341">500,00</span><span class="sxs-lookup"><span data-stu-id="d6400-341">500.00</span></span></td>
<td><span data-ttu-id="d6400-342">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-342">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-343">CC099</span><span class="sxs-lookup"><span data-stu-id="d6400-343">CC099</span></span></td>
<td><span data-ttu-id="d6400-344">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="d6400-344">Default cost center</span></span></td>
<td><span data-ttu-id="d6400-345">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-345">10001</span></span></td>
<td><span data-ttu-id="d6400-346">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-346">Electricity</span></span></td>
<td><span data-ttu-id="d6400-347">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-347">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-348">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="d6400-348">-9,000.00</span></span></td>
<td><span data-ttu-id="d6400-349">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-349">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-350">CC001</span><span class="sxs-lookup"><span data-stu-id="d6400-350">CC001</span></span></td>
<td><span data-ttu-id="d6400-351">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="d6400-351">HR</span></span></td>
<td><span data-ttu-id="d6400-352">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-352">10001</span></span></td>
<td><span data-ttu-id="d6400-353">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-353">Electricity</span></span></td>
<td><span data-ttu-id="d6400-354">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-354">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-355">1,285.71</span><span class="sxs-lookup"><span data-stu-id="d6400-355">1,285.71</span></span></td>
<td><span data-ttu-id="d6400-356">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-356">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-357">CC002</span><span class="sxs-lookup"><span data-stu-id="d6400-357">CC002</span></span></td>
<td><span data-ttu-id="d6400-358">Finanzas</span><span class="sxs-lookup"><span data-stu-id="d6400-358">Finance</span></span></td>
<td><span data-ttu-id="d6400-359">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-359">10001</span></span></td>
<td><span data-ttu-id="d6400-360">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-360">Electricity</span></span></td>
<td><span data-ttu-id="d6400-361">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-361">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-362">7,714.29</span><span class="sxs-lookup"><span data-stu-id="d6400-362">7,714.29</span></span></td>
<td><span data-ttu-id="d6400-363">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-363">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6400-364">Para obtener información detallada sobre la distribución de costes y las bases de asignación, consulte la directiva de distribución de costes y las bases de asignación.</span><span class="sxs-lookup"><span data-stu-id="d6400-364">For detailed information about cost distribution and allocation bases, see Cost distribution policy and Allocation bases.</span></span> <span data-ttu-id="d6400-365">(Tenga en cuenta que este tema no se ha completado aún, pero pronto se abordará).</span><span class="sxs-lookup"><span data-stu-id="d6400-365">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="d6400-366">Paso 3: Procese el cálculo de las tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="d6400-366">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="d6400-367">La tasa de costes generales se usa para cargar uno o varios objetos de coste específicos.</span><span class="sxs-lookup"><span data-stu-id="d6400-367">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="d6400-368">El cargo se basa en un índice de coste predeterminado y la magnitud de la base de asignación asignada.</span><span class="sxs-lookup"><span data-stu-id="d6400-368">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="d6400-369">Defina la tasa de costes generales</span><span class="sxs-lookup"><span data-stu-id="d6400-369">Define the overhead rate</span></span>

<span data-ttu-id="d6400-370">El objeto de coste CC001 HR contribuye a un conjunto de proyectos internos.</span><span class="sxs-lookup"><span data-stu-id="d6400-370">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="d6400-371">Se crea un miembro de dimensión estadística que se denomina proyectos HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="d6400-371">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6400-372">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-372">Cost object</span></span></th>
<th><span data-ttu-id="d6400-373">Horas</span><span class="sxs-lookup"><span data-stu-id="d6400-373">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-374">Proy 1</span><span class="sxs-lookup"><span data-stu-id="d6400-374">Proj 1</span></span></td>
<td><span data-ttu-id="d6400-375">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="d6400-375">Project 1</span></span></td>
<td><span data-ttu-id="d6400-376">3</span><span class="sxs-lookup"><span data-stu-id="d6400-376">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-377">Proy 2</span><span class="sxs-lookup"><span data-stu-id="d6400-377">Proj 2</span></span></td>
<td><span data-ttu-id="d6400-378">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="d6400-378">Project 2</span></span></td>
<td><span data-ttu-id="d6400-379">1</span><span class="sxs-lookup"><span data-stu-id="d6400-379">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6400-380">Una tasa de coste predeterminada para la contribución de los proyectos de coste se ha definido.</span><span class="sxs-lookup"><span data-stu-id="d6400-380">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6400-381">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-381">Cost object</span></span></th>
<th><span data-ttu-id="d6400-382">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-382">Cost element</span></span></th>
<th><span data-ttu-id="d6400-383">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="d6400-383">Cost behavior</span></span></th>
<th><span data-ttu-id="d6400-384">Unidades</span><span class="sxs-lookup"><span data-stu-id="d6400-384">Units</span></span></th>
<th><span data-ttu-id="d6400-385">Índice</span><span class="sxs-lookup"><span data-stu-id="d6400-385">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-386">CC001</span><span class="sxs-lookup"><span data-stu-id="d6400-386">CC001</span></span></td>
<td><span data-ttu-id="d6400-387">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="d6400-387">HR</span></span></td>
<td><span data-ttu-id="d6400-388">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-388">10001</span></span></td>
<td><span data-ttu-id="d6400-389">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-389">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-390">1</span><span class="sxs-lookup"><span data-stu-id="d6400-390">1</span></span></td>
<td><span data-ttu-id="d6400-391">10</span><span class="sxs-lookup"><span data-stu-id="d6400-391">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6400-392">La tabla siguiente muestra el resultado cuando los proyectos HR se aplican como base de la asignación.</span><span class="sxs-lookup"><span data-stu-id="d6400-392">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6400-393">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-393">Cost object</span></span></th>
<th><span data-ttu-id="d6400-394">Magnitud</span><span class="sxs-lookup"><span data-stu-id="d6400-394">Magnitude</span></span></th>
<th><span data-ttu-id="d6400-395">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-395">Cost element</span></span></th>
<th><span data-ttu-id="d6400-396">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="d6400-396">Allocation factor</span></span></th>
<th><span data-ttu-id="d6400-397">Importe</span><span class="sxs-lookup"><span data-stu-id="d6400-397">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-398">Proy 1</span><span class="sxs-lookup"><span data-stu-id="d6400-398">Proj 1</span></span></td>
<td><span data-ttu-id="d6400-399">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="d6400-399">Project 1</span></span></td>
<td><span data-ttu-id="d6400-400">3</span><span class="sxs-lookup"><span data-stu-id="d6400-400">3</span></span></td>
<td><span data-ttu-id="d6400-401">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-401">10001</span></span></td>
<td><span data-ttu-id="d6400-402">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="d6400-402">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="d6400-403">30,00</span><span class="sxs-lookup"><span data-stu-id="d6400-403">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-404">Proy 2</span><span class="sxs-lookup"><span data-stu-id="d6400-404">Proj 2</span></span></td>
<td><span data-ttu-id="d6400-405">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="d6400-405">Project 2</span></span></td>
<td><span data-ttu-id="d6400-406">1</span><span class="sxs-lookup"><span data-stu-id="d6400-406">1</span></span></td>
<td><span data-ttu-id="d6400-407">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-407">10001</span></span></td>
<td><span data-ttu-id="d6400-408">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="d6400-408">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="d6400-409">10,00</span><span class="sxs-lookup"><span data-stu-id="d6400-409">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="d6400-410">Diario</span><span class="sxs-lookup"><span data-stu-id="d6400-410">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d6400-411">Diario</span><span class="sxs-lookup"><span data-stu-id="d6400-411">Journal</span></span></th>
<th><span data-ttu-id="d6400-412">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="d6400-412">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="d6400-413">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="d6400-413">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="d6400-414">Versión</span><span class="sxs-lookup"><span data-stu-id="d6400-414">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-415">00003</span><span class="sxs-lookup"><span data-stu-id="d6400-415">00003</span></span></td>
<td><span data-ttu-id="d6400-416">Diario de cálculo de tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="d6400-416">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="d6400-417">Fiscal</span><span class="sxs-lookup"><span data-stu-id="d6400-417">Fiscal</span></span></td>
<td><span data-ttu-id="d6400-418">2017</span><span class="sxs-lookup"><span data-stu-id="d6400-418">2017</span></span></td>
<td><span data-ttu-id="d6400-419">Período 1</span><span class="sxs-lookup"><span data-stu-id="d6400-419">Period 1</span></span></td>
<td><span data-ttu-id="d6400-420">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="d6400-420">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="d6400-421">Entradas de diario (entradas de diario para cálculo de tasas de costes generales)</span><span class="sxs-lookup"><span data-stu-id="d6400-421">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d6400-422">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="d6400-422">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="d6400-423">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-423">Cost object</span></span></th>
<th><span data-ttu-id="d6400-424">Magnitud</span><span class="sxs-lookup"><span data-stu-id="d6400-424">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-425">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-425">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6400-426">Proy 1</span><span class="sxs-lookup"><span data-stu-id="d6400-426">Proj 1</span></span></td>
<td><span data-ttu-id="d6400-427">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="d6400-427">Internal Proj 1</span></span></td>
<td><span data-ttu-id="d6400-428">3,00</span><span class="sxs-lookup"><span data-stu-id="d6400-428">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-429">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-429">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6400-430">Proy 2</span><span class="sxs-lookup"><span data-stu-id="d6400-430">Proj 2</span></span></td>
<td><span data-ttu-id="d6400-431">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="d6400-431">Internal Proj 2</span></span></td>
<td><span data-ttu-id="d6400-432">1,00</span><span class="sxs-lookup"><span data-stu-id="d6400-432">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="d6400-433">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="d6400-433">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6400-434">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-434">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d6400-435">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-435">Cost element</span></span></th>
<th><span data-ttu-id="d6400-436">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="d6400-436">Cost behavior</span></span></th>
<th><span data-ttu-id="d6400-437">Importe</span><span class="sxs-lookup"><span data-stu-id="d6400-437">Amount</span></span></th>
<th><span data-ttu-id="d6400-438">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="d6400-438">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-439">CC0001</span><span class="sxs-lookup"><span data-stu-id="d6400-439">CC0001</span></span></td>
<td><span data-ttu-id="d6400-440">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="d6400-440">HR</span></span></td>
<td><span data-ttu-id="d6400-441">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-441">10001</span></span></td>
<td><span data-ttu-id="d6400-442">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-442">Electricity</span></span></td>
<td><span data-ttu-id="d6400-443">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-443">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-444">-30,00</span><span class="sxs-lookup"><span data-stu-id="d6400-444">-30.00</span></span></td>
<td><span data-ttu-id="d6400-445">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-445">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-446">Proy 1</span><span class="sxs-lookup"><span data-stu-id="d6400-446">Proj 1</span></span></td>
<td><span data-ttu-id="d6400-447">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="d6400-447">Internal Proj 1</span></span></td>
<td><span data-ttu-id="d6400-448">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-448">10001</span></span></td>
<td><span data-ttu-id="d6400-449">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-449">Electricity</span></span></td>
<td><span data-ttu-id="d6400-450">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-450">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-451">30,00</span><span class="sxs-lookup"><span data-stu-id="d6400-451">30.00</span></span></td>
<td><span data-ttu-id="d6400-452">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-452">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-453">CC001</span><span class="sxs-lookup"><span data-stu-id="d6400-453">CC001</span></span></td>
<td><span data-ttu-id="d6400-454">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="d6400-454">HR</span></span></td>
<td><span data-ttu-id="d6400-455">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-455">10001</span></span></td>
<td><span data-ttu-id="d6400-456">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-456">Electricity</span></span></td>
<td><span data-ttu-id="d6400-457">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-457">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-458">-10,00</span><span class="sxs-lookup"><span data-stu-id="d6400-458">-10.00</span></span></td>
<td><span data-ttu-id="d6400-459">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-459">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-460">Proy 2</span><span class="sxs-lookup"><span data-stu-id="d6400-460">Proj 2</span></span></td>
<td><span data-ttu-id="d6400-461">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="d6400-461">Internal Proj 2</span></span></td>
<td><span data-ttu-id="d6400-462">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-462">10001</span></span></td>
<td><span data-ttu-id="d6400-463">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-463">Electricity</span></span></td>
<td><span data-ttu-id="d6400-464">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-464">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-465">10,00</span><span class="sxs-lookup"><span data-stu-id="d6400-465">10.00</span></span></td>
<td><span data-ttu-id="d6400-466">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-466">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6400-467">Para obtener información detallada acerca de la directiva de tasa de costes generales, consulte la directiva de tasas de costes generales y las bases de asignación.</span><span class="sxs-lookup"><span data-stu-id="d6400-467">For detailed information about overhead rate policy, see Overhead rate policy and Allocation bases.</span></span> <span data-ttu-id="d6400-468">(Tenga en cuenta que este tema no se ha completado aún, pero pronto se abordará).</span><span class="sxs-lookup"><span data-stu-id="d6400-468">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="d6400-469">Paso 4: Procese el cálculo de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="d6400-469">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="d6400-470">La asignación es utilizada para asignar el saldo de un objeto de coste a otros objetos de coste aplicando una base de asignación.</span><span class="sxs-lookup"><span data-stu-id="d6400-470">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="d6400-471">Finance and Operations admite el método de asignación recíproco.</span><span class="sxs-lookup"><span data-stu-id="d6400-471">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="d6400-472">En el método de asignación recíproco, se reconocen completamente los servicios mutuos que los objetos de coste auxiliar intercambian.</span><span class="sxs-lookup"><span data-stu-id="d6400-472">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="d6400-473">El sistema determina automáticamente el orden correcto para realizar las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="d6400-473">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="d6400-474">El saldo de un objeto de coste se asigna según una única base de asignación.</span><span class="sxs-lookup"><span data-stu-id="d6400-474">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="d6400-475">Las asignaciones entre dimensiones de objetos de coste y sus miembros respectivos se admiten.</span><span class="sxs-lookup"><span data-stu-id="d6400-475">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="d6400-476">El orden de asignación se controla por unidad de control de costes.</span><span class="sxs-lookup"><span data-stu-id="d6400-476">The allocation order is controlled by the cost control unit.</span></span> <span data-ttu-id="d6400-477">[![Método recíproco](./media/reciprocal-method.png)]</span><span class="sxs-lookup"><span data-stu-id="d6400-477">[![Reciprocal method](./media/reciprocal-method.png)]</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="d6400-478">Defina la asignación de costes</span><span class="sxs-lookup"><span data-stu-id="d6400-478">Define the cost allocation</span></span>

<span data-ttu-id="d6400-479">A continuación se indica un ejemplo sencillo que explica cómo puede realizar el seguimiento del flujo de coste.</span><span class="sxs-lookup"><span data-stu-id="d6400-479">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="d6400-480">El objeto de coste CC001 HR contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="d6400-480">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="d6400-481">Se crea un miembro de dimensión estadística que se denomina servicios HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="d6400-481">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6400-482">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-482">Cost object</span></span></th>
<th><span data-ttu-id="d6400-483">Servicios HR</span><span class="sxs-lookup"><span data-stu-id="d6400-483">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-484">CC002</span><span class="sxs-lookup"><span data-stu-id="d6400-484">CC002</span></span></td>
<td><span data-ttu-id="d6400-485">Finanzas</span><span class="sxs-lookup"><span data-stu-id="d6400-485">Finance</span></span></td>
<td><span data-ttu-id="d6400-486">35</span><span class="sxs-lookup"><span data-stu-id="d6400-486">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-487">CC003</span><span class="sxs-lookup"><span data-stu-id="d6400-487">CC003</span></span></td>
<td><span data-ttu-id="d6400-488">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="d6400-488">Assembly</span></span></td>
<td><span data-ttu-id="d6400-489">55</span><span class="sxs-lookup"><span data-stu-id="d6400-489">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-490">CC004</span><span class="sxs-lookup"><span data-stu-id="d6400-490">CC004</span></span></td>
<td><span data-ttu-id="d6400-491">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="d6400-491">Packaging</span></span></td>
<td><span data-ttu-id="d6400-492">10</span><span class="sxs-lookup"><span data-stu-id="d6400-492">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6400-493">El objeto de coste CC002 Finanzas contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="d6400-493">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="d6400-494">Se crea un miembro de dimensión estadística que se denomina Finanzas para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="d6400-494">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6400-495">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-495">Cost object</span></span></th>
<th><span data-ttu-id="d6400-496">Servicios financieros</span><span class="sxs-lookup"><span data-stu-id="d6400-496">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-497">CC003</span><span class="sxs-lookup"><span data-stu-id="d6400-497">CC003</span></span></td>
<td><span data-ttu-id="d6400-498">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="d6400-498">Assembly</span></span></td>
<td><span data-ttu-id="d6400-499">65</span><span class="sxs-lookup"><span data-stu-id="d6400-499">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-500">CC004</span><span class="sxs-lookup"><span data-stu-id="d6400-500">CC004</span></span></td>
<td><span data-ttu-id="d6400-501">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="d6400-501">Packaging</span></span></td>
<td><span data-ttu-id="d6400-502">35</span><span class="sxs-lookup"><span data-stu-id="d6400-502">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6400-503">El objeto de coste CC003 Asamblea contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="d6400-503">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="d6400-504">Se crea un miembro de dimensión estadística que se denomina servicios de Asamblea para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="d6400-504">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6400-505">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-505">Cost object</span></span></th>
<th><span data-ttu-id="d6400-506">Servicios de la asamblea (horas)</span><span class="sxs-lookup"><span data-stu-id="d6400-506">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-507">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6400-507">Prod 1</span></span></td>
<td><span data-ttu-id="d6400-508">Producto 1</span><span class="sxs-lookup"><span data-stu-id="d6400-508">Product 1</span></span></td>
<td><span data-ttu-id="d6400-509">60</span><span class="sxs-lookup"><span data-stu-id="d6400-509">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-510">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6400-510">Prod 2</span></span></td>
<td><span data-ttu-id="d6400-511">Producto 2</span><span class="sxs-lookup"><span data-stu-id="d6400-511">Product 2</span></span></td>
<td><span data-ttu-id="d6400-512">20</span><span class="sxs-lookup"><span data-stu-id="d6400-512">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6400-513">El objeto de coste CC004 Embalaje contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="d6400-513">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="d6400-514">Se crea un miembro de dimensión estadística que se denomina servicios de Embalaje para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="d6400-514">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6400-515">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-515">Cost object</span></span></th>
<th><span data-ttu-id="d6400-516">Servicios de embalaje (horas)</span><span class="sxs-lookup"><span data-stu-id="d6400-516">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-517">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6400-517">Prod 1</span></span></td>
<td><span data-ttu-id="d6400-518">Producto 1</span><span class="sxs-lookup"><span data-stu-id="d6400-518">Product 1</span></span></td>
<td><span data-ttu-id="d6400-519">80</span><span class="sxs-lookup"><span data-stu-id="d6400-519">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-520">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6400-520">Prod 2</span></span></td>
<td><span data-ttu-id="d6400-521">Producto 2</span><span class="sxs-lookup"><span data-stu-id="d6400-521">Product 2</span></span></td>
<td><span data-ttu-id="d6400-522">15</span><span class="sxs-lookup"><span data-stu-id="d6400-522">15</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6400-523">**Nota:** En Finance and Operations, las medidas estadísticas como las horas de la producción que un producto consume se pueden deducir de los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="d6400-523">**Note:** In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="d6400-524">Para obtener información más detallada acerca de los proveedores de medidas estadísticas, consulte la plantilla de proveedor de estadísticas de medidas.</span><span class="sxs-lookup"><span data-stu-id="d6400-524">For more detailed information about statistical measure providers, see Statistical measure provider template.</span></span> <span data-ttu-id="d6400-525">(Tenga en cuenta que este tema todavía no está completado, pero que pronto lo estará). La tabla siguiente muestra el resultado cuando se aplican los servicios HR como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="d6400-525">(Note that this topic isn't completed yet but is coming soon.) The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6400-526">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-526">Cost object</span></span></th>
<th><span data-ttu-id="d6400-527">Magnitud</span><span class="sxs-lookup"><span data-stu-id="d6400-527">Magnitude</span></span></th>
<th><span data-ttu-id="d6400-528">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="d6400-528">Allocation factor</span></span></th>
<th><span data-ttu-id="d6400-529">Importe</span><span class="sxs-lookup"><span data-stu-id="d6400-529">Amount</span></span></th>
<th><span data-ttu-id="d6400-530">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="d6400-530">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-531">CC002</span><span class="sxs-lookup"><span data-stu-id="d6400-531">CC002</span></span></td>
<td><span data-ttu-id="d6400-532">Finanzas</span><span class="sxs-lookup"><span data-stu-id="d6400-532">Finance</span></span></td>
<td><span data-ttu-id="d6400-533">35</span><span class="sxs-lookup"><span data-stu-id="d6400-533">35</span></span></td>
<td><span data-ttu-id="d6400-534">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="d6400-534">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="d6400-535">175.00</span><span class="sxs-lookup"><span data-stu-id="d6400-535">175.00</span></span></td>
<td><span data-ttu-id="d6400-536">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-536">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-537">CC003</span><span class="sxs-lookup"><span data-stu-id="d6400-537">CC003</span></span></td>
<td><span data-ttu-id="d6400-538">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="d6400-538">Assembly</span></span></td>
<td><span data-ttu-id="d6400-539">55</span><span class="sxs-lookup"><span data-stu-id="d6400-539">55</span></span></td>
<td><span data-ttu-id="d6400-540">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="d6400-540">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="d6400-541">275.00</span><span class="sxs-lookup"><span data-stu-id="d6400-541">275.00</span></span></td>
<td><span data-ttu-id="d6400-542">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-542">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-543">CC004</span><span class="sxs-lookup"><span data-stu-id="d6400-543">CC004</span></span></td>
<td><span data-ttu-id="d6400-544">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="d6400-544">Packaging</span></span></td>
<td><span data-ttu-id="d6400-545">10</span><span class="sxs-lookup"><span data-stu-id="d6400-545">10</span></span></td>
<td><span data-ttu-id="d6400-546">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="d6400-546">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="d6400-547">50,00</span><span class="sxs-lookup"><span data-stu-id="d6400-547">50.00</span></span></td>
<td><span data-ttu-id="d6400-548">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-548">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-549">CC002</span><span class="sxs-lookup"><span data-stu-id="d6400-549">CC002</span></span></td>
<td><span data-ttu-id="d6400-550">Finanzas</span><span class="sxs-lookup"><span data-stu-id="d6400-550">Finance</span></span></td>
<td><span data-ttu-id="d6400-551">35</span><span class="sxs-lookup"><span data-stu-id="d6400-551">35</span></span></td>
<td><span data-ttu-id="d6400-552">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="d6400-552">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="d6400-553">436.00</span><span class="sxs-lookup"><span data-stu-id="d6400-553">436.00</span></span></td>
<td><span data-ttu-id="d6400-554">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-554">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-555">CC003</span><span class="sxs-lookup"><span data-stu-id="d6400-555">CC003</span></span></td>
<td><span data-ttu-id="d6400-556">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="d6400-556">Assembly</span></span></td>
<td><span data-ttu-id="d6400-557">55</span><span class="sxs-lookup"><span data-stu-id="d6400-557">55</span></span></td>
<td><span data-ttu-id="d6400-558">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="d6400-558">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="d6400-559">685.14</span><span class="sxs-lookup"><span data-stu-id="d6400-559">685.14</span></span></td>
<td><span data-ttu-id="d6400-560">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-560">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-561">CC004</span><span class="sxs-lookup"><span data-stu-id="d6400-561">CC004</span></span></td>
<td><span data-ttu-id="d6400-562">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="d6400-562">Packaging</span></span></td>
<td><span data-ttu-id="d6400-563">10</span><span class="sxs-lookup"><span data-stu-id="d6400-563">10</span></span></td>
<td><span data-ttu-id="d6400-564">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="d6400-564">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="d6400-565">124.57</span><span class="sxs-lookup"><span data-stu-id="d6400-565">124.57</span></span></td>
<td><span data-ttu-id="d6400-566">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-566">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6400-567">La tabla siguiente muestra el resultado cuando se aplican los servicios de Finanzas como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="d6400-567">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6400-568">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-568">Cost object</span></span></th>
<th><span data-ttu-id="d6400-569">Magnitud</span><span class="sxs-lookup"><span data-stu-id="d6400-569">Magnitude</span></span></th>
<th><span data-ttu-id="d6400-570">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="d6400-570">Allocation factor</span></span></th>
<th><span data-ttu-id="d6400-571">Importe</span><span class="sxs-lookup"><span data-stu-id="d6400-571">Amount</span></span></th>
<th><span data-ttu-id="d6400-572">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="d6400-572">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-573">CC003</span><span class="sxs-lookup"><span data-stu-id="d6400-573">CC003</span></span></td>
<td><span data-ttu-id="d6400-574">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="d6400-574">Assembly</span></span></td>
<td><span data-ttu-id="d6400-575">65</span><span class="sxs-lookup"><span data-stu-id="d6400-575">65</span></span></td>
<td><span data-ttu-id="d6400-576">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="d6400-576">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="d6400-577">438.75</span><span class="sxs-lookup"><span data-stu-id="d6400-577">438.75</span></span></td>
<td><span data-ttu-id="d6400-578">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-578">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-579">CC004</span><span class="sxs-lookup"><span data-stu-id="d6400-579">CC004</span></span></td>
<td><span data-ttu-id="d6400-580">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="d6400-580">Packaging</span></span></td>
<td><span data-ttu-id="d6400-581">35</span><span class="sxs-lookup"><span data-stu-id="d6400-581">35</span></span></td>
<td><span data-ttu-id="d6400-582">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="d6400-582">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="d6400-583">236.25</span><span class="sxs-lookup"><span data-stu-id="d6400-583">236.25</span></span></td>
<td><span data-ttu-id="d6400-584">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-584">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-585">CC003</span><span class="sxs-lookup"><span data-stu-id="d6400-585">CC003</span></span></td>
<td><span data-ttu-id="d6400-586">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="d6400-586">Assembly</span></span></td>
<td><span data-ttu-id="d6400-587">65</span><span class="sxs-lookup"><span data-stu-id="d6400-587">65</span></span></td>
<td><span data-ttu-id="d6400-588">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="d6400-588">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="d6400-589">5,297.69</span><span class="sxs-lookup"><span data-stu-id="d6400-589">5,297.69</span></span></td>
<td><span data-ttu-id="d6400-590">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-590">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-591">CC004</span><span class="sxs-lookup"><span data-stu-id="d6400-591">CC004</span></span></td>
<td><span data-ttu-id="d6400-592">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="d6400-592">Packaging</span></span></td>
<td><span data-ttu-id="d6400-593">35</span><span class="sxs-lookup"><span data-stu-id="d6400-593">35</span></span></td>
<td><span data-ttu-id="d6400-594">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="d6400-594">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="d6400-595">2,852.60</span><span class="sxs-lookup"><span data-stu-id="d6400-595">2,852.60</span></span></td>
<td><span data-ttu-id="d6400-596">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-596">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6400-597">La tabla siguiente muestra el resultado cuando se aplican los servicios de Asamblea como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="d6400-597">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6400-598">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-598">Cost object</span></span></th>
<th><span data-ttu-id="d6400-599">Magnitud</span><span class="sxs-lookup"><span data-stu-id="d6400-599">Magnitude</span></span></th>
<th><span data-ttu-id="d6400-600">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="d6400-600">Allocation factor</span></span></th>
<th><span data-ttu-id="d6400-601">Importe</span><span class="sxs-lookup"><span data-stu-id="d6400-601">Amount</span></span></th>
<th><span data-ttu-id="d6400-602">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="d6400-602">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-603">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6400-603">Prod 1</span></span></td>
<td><span data-ttu-id="d6400-604">Producto 1</span><span class="sxs-lookup"><span data-stu-id="d6400-604">Product 1</span></span></td>
<td><span data-ttu-id="d6400-605">60</span><span class="sxs-lookup"><span data-stu-id="d6400-605">60</span></span></td>
<td><span data-ttu-id="d6400-606">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="d6400-606">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="d6400-607">535.31</span><span class="sxs-lookup"><span data-stu-id="d6400-607">535.31</span></span></td>
<td><span data-ttu-id="d6400-608">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-608">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-609">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6400-609">Prod 2</span></span></td>
<td><span data-ttu-id="d6400-610">Producto 2</span><span class="sxs-lookup"><span data-stu-id="d6400-610">Product 2</span></span></td>
<td><span data-ttu-id="d6400-611">20</span><span class="sxs-lookup"><span data-stu-id="d6400-611">20</span></span></td>
<td><span data-ttu-id="d6400-612">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="d6400-612">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="d6400-613">178.44</span><span class="sxs-lookup"><span data-stu-id="d6400-613">178.44</span></span></td>
<td><span data-ttu-id="d6400-614">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-614">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-615">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6400-615">Prod 1</span></span></td>
<td><span data-ttu-id="d6400-616">Producto 1</span><span class="sxs-lookup"><span data-stu-id="d6400-616">Product 1</span></span></td>
<td><span data-ttu-id="d6400-617">60</span><span class="sxs-lookup"><span data-stu-id="d6400-617">60</span></span></td>
<td><span data-ttu-id="d6400-618">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="d6400-618">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="d6400-619">4,487.12</span><span class="sxs-lookup"><span data-stu-id="d6400-619">4,487.12</span></span></td>
<td><span data-ttu-id="d6400-620">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-620">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-621">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6400-621">Prod 2</span></span></td>
<td><span data-ttu-id="d6400-622">Producto 2</span><span class="sxs-lookup"><span data-stu-id="d6400-622">Product 2</span></span></td>
<td><span data-ttu-id="d6400-623">20</span><span class="sxs-lookup"><span data-stu-id="d6400-623">20</span></span></td>
<td><span data-ttu-id="d6400-624">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="d6400-624">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="d6400-625">1,495.71</span><span class="sxs-lookup"><span data-stu-id="d6400-625">1,495.71</span></span></td>
<td><span data-ttu-id="d6400-626">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-626">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d6400-627">La tabla siguiente muestra el resultado cuando se aplican los servicios de Embalaje como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="d6400-627">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6400-628">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-628">Cost object</span></span></th>
<th><span data-ttu-id="d6400-629">Magnitud</span><span class="sxs-lookup"><span data-stu-id="d6400-629">Magnitude</span></span></th>
<th><span data-ttu-id="d6400-630">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="d6400-630">Allocation factor</span></span></th>
<th><span data-ttu-id="d6400-631">Importe</span><span class="sxs-lookup"><span data-stu-id="d6400-631">Amount</span></span></th>
<th><span data-ttu-id="d6400-632">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="d6400-632">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-633">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6400-633">Prod 1</span></span></td>
<td><span data-ttu-id="d6400-634">Producto 1</span><span class="sxs-lookup"><span data-stu-id="d6400-634">Product 1</span></span></td>
<td><span data-ttu-id="d6400-635">80</span><span class="sxs-lookup"><span data-stu-id="d6400-635">80</span></span></td>
<td><span data-ttu-id="d6400-636">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="d6400-636">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="d6400-637">241.05</span><span class="sxs-lookup"><span data-stu-id="d6400-637">241.05</span></span></td>
<td><span data-ttu-id="d6400-638">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-638">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-639">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6400-639">Prod 2</span></span></td>
<td><span data-ttu-id="d6400-640">Producto 2</span><span class="sxs-lookup"><span data-stu-id="d6400-640">Product 2</span></span></td>
<td><span data-ttu-id="d6400-641">15</span><span class="sxs-lookup"><span data-stu-id="d6400-641">15</span></span></td>
<td><span data-ttu-id="d6400-642">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="d6400-642">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="d6400-643">45.20</span><span class="sxs-lookup"><span data-stu-id="d6400-643">45.20</span></span></td>
<td><span data-ttu-id="d6400-644">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-644">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-645">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6400-645">Prod 1</span></span></td>
<td><span data-ttu-id="d6400-646">Producto 1</span><span class="sxs-lookup"><span data-stu-id="d6400-646">Product 1</span></span></td>
<td><span data-ttu-id="d6400-647">80</span><span class="sxs-lookup"><span data-stu-id="d6400-647">80</span></span></td>
<td><span data-ttu-id="d6400-648">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="d6400-648">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="d6400-649">2,507.09</span><span class="sxs-lookup"><span data-stu-id="d6400-649">2,507.09</span></span></td>
<td><span data-ttu-id="d6400-650">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-650">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-651">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6400-651">Prod 2</span></span></td>
<td><span data-ttu-id="d6400-652">Producto 2</span><span class="sxs-lookup"><span data-stu-id="d6400-652">Product 2</span></span></td>
<td><span data-ttu-id="d6400-653">15</span><span class="sxs-lookup"><span data-stu-id="d6400-653">15</span></span></td>
<td><span data-ttu-id="d6400-654">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="d6400-654">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="d6400-655">470.08</span><span class="sxs-lookup"><span data-stu-id="d6400-655">470.08</span></span></td>
<td><span data-ttu-id="d6400-656">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-656">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="d6400-657">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="d6400-657">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d6400-658">Diario</span><span class="sxs-lookup"><span data-stu-id="d6400-658">Journal</span></span></th>
<th><span data-ttu-id="d6400-659">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="d6400-659">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="d6400-660">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="d6400-660">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="d6400-661">Versión</span><span class="sxs-lookup"><span data-stu-id="d6400-661">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-662">00004</span><span class="sxs-lookup"><span data-stu-id="d6400-662">00004</span></span></td>
<td><span data-ttu-id="d6400-663">Diario de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="d6400-663">Cost allocation journal</span></span></td>
<td><span data-ttu-id="d6400-664">Fiscal</span><span class="sxs-lookup"><span data-stu-id="d6400-664">Fiscal</span></span></td>
<td><span data-ttu-id="d6400-665">2017</span><span class="sxs-lookup"><span data-stu-id="d6400-665">2017</span></span></td>
<td><span data-ttu-id="d6400-666">Período 1</span><span class="sxs-lookup"><span data-stu-id="d6400-666">Period 1</span></span></td>
<td><span data-ttu-id="d6400-667">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="d6400-667">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="d6400-668">Líneas de diario</span><span class="sxs-lookup"><span data-stu-id="d6400-668">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d6400-669">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="d6400-669">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="d6400-670">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-670">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d6400-671">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-671">Cost element</span></span></th>
<th><span data-ttu-id="d6400-672">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="d6400-672">Cost behavior</span></span></th>
<th><span data-ttu-id="d6400-673">Importe</span><span class="sxs-lookup"><span data-stu-id="d6400-673">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-674">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-674">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6400-675">CC001</span><span class="sxs-lookup"><span data-stu-id="d6400-675">CC001</span></span></td>
<td><span data-ttu-id="d6400-676">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="d6400-676">HR</span></span></td>
<td><span data-ttu-id="d6400-677">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-677">10001</span></span></td>
<td><span data-ttu-id="d6400-678">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-678">Electricity</span></span></td>
<td><span data-ttu-id="d6400-679">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-679">Fixed cost</span></span></td>
<td><span data-ttu-id="d6400-680">500,00</span><span class="sxs-lookup"><span data-stu-id="d6400-680">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-681">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-681">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6400-682">CC001</span><span class="sxs-lookup"><span data-stu-id="d6400-682">CC001</span></span></td>
<td><span data-ttu-id="d6400-683">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="d6400-683">HR</span></span></td>
<td><span data-ttu-id="d6400-684">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-684">10001</span></span></td>
<td><span data-ttu-id="d6400-685">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-685">Electricity</span></span></td>
<td><span data-ttu-id="d6400-686">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-686">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-687">1,245.71</span><span class="sxs-lookup"><span data-stu-id="d6400-687">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-688">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-688">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6400-689">CC002</span><span class="sxs-lookup"><span data-stu-id="d6400-689">CC002</span></span></td>
<td><span data-ttu-id="d6400-690">Finanzas</span><span class="sxs-lookup"><span data-stu-id="d6400-690">Finance</span></span></td>
<td><span data-ttu-id="d6400-691">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-691">10001</span></span></td>
<td><span data-ttu-id="d6400-692">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-692">Electricity</span></span></td>
<td><span data-ttu-id="d6400-693">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-693">Fixed cost</span></span></td>
<td><span data-ttu-id="d6400-694">675.00</span><span class="sxs-lookup"><span data-stu-id="d6400-694">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-695">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-695">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6400-696">CC002</span><span class="sxs-lookup"><span data-stu-id="d6400-696">CC002</span></span></td>
<td><span data-ttu-id="d6400-697">Finanzas</span><span class="sxs-lookup"><span data-stu-id="d6400-697">Finance</span></span></td>
<td><span data-ttu-id="d6400-698">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-698">10001</span></span></td>
<td><span data-ttu-id="d6400-699">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-699">Electricity</span></span></td>
<td><span data-ttu-id="d6400-700">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-700">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-701">8,150.29</span><span class="sxs-lookup"><span data-stu-id="d6400-701">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-702">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-702">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6400-703">CC003</span><span class="sxs-lookup"><span data-stu-id="d6400-703">CC003</span></span></td>
<td><span data-ttu-id="d6400-704">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="d6400-704">Assembly</span></span></td>
<td><span data-ttu-id="d6400-705">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-705">10001</span></span></td>
<td><span data-ttu-id="d6400-706">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-706">Electricity</span></span></td>
<td><span data-ttu-id="d6400-707">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-707">Fixed cost</span></span></td>
<td><span data-ttu-id="d6400-708">713.75</span><span class="sxs-lookup"><span data-stu-id="d6400-708">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-709">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-709">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6400-710">CC003</span><span class="sxs-lookup"><span data-stu-id="d6400-710">CC003</span></span></td>
<td><span data-ttu-id="d6400-711">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="d6400-711">Assembly</span></span></td>
<td><span data-ttu-id="d6400-712">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-712">10001</span></span></td>
<td><span data-ttu-id="d6400-713">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-713">Electricity</span></span></td>
<td><span data-ttu-id="d6400-714">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-714">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-715">5,982.83</span><span class="sxs-lookup"><span data-stu-id="d6400-715">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-716">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-716">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6400-717">CC003</span><span class="sxs-lookup"><span data-stu-id="d6400-717">CC003</span></span></td>
<td><span data-ttu-id="d6400-718">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="d6400-718">Packaging</span></span></td>
<td><span data-ttu-id="d6400-719">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-719">10001</span></span></td>
<td><span data-ttu-id="d6400-720">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-720">Electricity</span></span></td>
<td><span data-ttu-id="d6400-721">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-721">Fixed cost</span></span></td>
<td><span data-ttu-id="d6400-722">286.25</span><span class="sxs-lookup"><span data-stu-id="d6400-722">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-723">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-723">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6400-724">CC003</span><span class="sxs-lookup"><span data-stu-id="d6400-724">CC003</span></span></td>
<td><span data-ttu-id="d6400-725">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="d6400-725">Packaging</span></span></td>
<td><span data-ttu-id="d6400-726">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-726">10001</span></span></td>
<td><span data-ttu-id="d6400-727">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-727">Electricity</span></span></td>
<td><span data-ttu-id="d6400-728">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-728">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-729">2,977.17</span><span class="sxs-lookup"><span data-stu-id="d6400-729">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-730">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-730">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6400-731">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6400-731">Prod 1</span></span></td>
<td><span data-ttu-id="d6400-732">Producto 1</span><span class="sxs-lookup"><span data-stu-id="d6400-732">Product 1</span></span></td>
<td><span data-ttu-id="d6400-733">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-733">10001</span></span></td>
<td><span data-ttu-id="d6400-734">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-734">Electricity</span></span></td>
<td><span data-ttu-id="d6400-735">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-735">Fixed cost</span></span></td>
<td><span data-ttu-id="d6400-736">776.36</span><span class="sxs-lookup"><span data-stu-id="d6400-736">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-737">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-737">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6400-738">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6400-738">Prod 1</span></span></td>
<td><span data-ttu-id="d6400-739">Producto 1</span><span class="sxs-lookup"><span data-stu-id="d6400-739">Product 1</span></span></td>
<td><span data-ttu-id="d6400-740">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-740">10001</span></span></td>
<td><span data-ttu-id="d6400-741">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-741">Electricity</span></span></td>
<td><span data-ttu-id="d6400-742">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-742">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-743">6,994.21</span><span class="sxs-lookup"><span data-stu-id="d6400-743">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-744">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-744">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6400-745">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6400-745">Prod 2</span></span></td>
<td><span data-ttu-id="d6400-746">Producto 1</span><span class="sxs-lookup"><span data-stu-id="d6400-746">Product 1</span></span></td>
<td><span data-ttu-id="d6400-747">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-747">10001</span></span></td>
<td><span data-ttu-id="d6400-748">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-748">Electricity</span></span></td>
<td><span data-ttu-id="d6400-749">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-749">Fixed cost</span></span></td>
<td><span data-ttu-id="d6400-750">223.64</span><span class="sxs-lookup"><span data-stu-id="d6400-750">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-751">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-751">January 31, 2017</span></span></td>
<td><span data-ttu-id="d6400-752">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6400-752">Prod 2</span></span></td>
<td><span data-ttu-id="d6400-753">Producto 1</span><span class="sxs-lookup"><span data-stu-id="d6400-753">Product 1</span></span></td>
<td><span data-ttu-id="d6400-754">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-754">10001</span></span></td>
<td><span data-ttu-id="d6400-755">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-755">Electricity</span></span></td>
<td><span data-ttu-id="d6400-756">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-756">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-757">1,965.79</span><span class="sxs-lookup"><span data-stu-id="d6400-757">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="d6400-758">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="d6400-758">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d6400-759">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-759">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d6400-760">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-760">Cost element</span></span></th>
<th><span data-ttu-id="d6400-761">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="d6400-761">Cost behavior</span></span></th>
<th><span data-ttu-id="d6400-762">Importe</span><span class="sxs-lookup"><span data-stu-id="d6400-762">Amount</span></span></th>
<th><span data-ttu-id="d6400-763">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="d6400-763">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d6400-764">CC001</span><span class="sxs-lookup"><span data-stu-id="d6400-764">CC001</span></span></td>
<td><span data-ttu-id="d6400-765">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="d6400-765">HR</span></span></td>
<td><span data-ttu-id="d6400-766">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-766">10001</span></span></td>
<td><span data-ttu-id="d6400-767">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-767">Electricity</span></span></td>
<td><span data-ttu-id="d6400-768">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-768">Fixed cost</span></span></td>
<td><span data-ttu-id="d6400-769">-500,00</span><span class="sxs-lookup"><span data-stu-id="d6400-769">-500.00</span></span></td>
<td><span data-ttu-id="d6400-770">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-770">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-771">CC002</span><span class="sxs-lookup"><span data-stu-id="d6400-771">CC002</span></span></td>
<td><span data-ttu-id="d6400-772">Finanzas</span><span class="sxs-lookup"><span data-stu-id="d6400-772">Finance</span></span></td>
<td><span data-ttu-id="d6400-773">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-773">10001</span></span></td>
<td><span data-ttu-id="d6400-774">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-774">Electricity</span></span></td>
<td><span data-ttu-id="d6400-775">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-775">Fixed cost</span></span></td>
<td><span data-ttu-id="d6400-776">175.00</span><span class="sxs-lookup"><span data-stu-id="d6400-776">175.00</span></span></td>
<td><span data-ttu-id="d6400-777">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-777">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-778">CC003</span><span class="sxs-lookup"><span data-stu-id="d6400-778">CC003</span></span></td>
<td><span data-ttu-id="d6400-779">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="d6400-779">Assembly</span></span></td>
<td><span data-ttu-id="d6400-780">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-780">10001</span></span></td>
<td><span data-ttu-id="d6400-781">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-781">Electricity</span></span></td>
<td><span data-ttu-id="d6400-782">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-782">Fixed cost</span></span></td>
<td><span data-ttu-id="d6400-783">275.00</span><span class="sxs-lookup"><span data-stu-id="d6400-783">275.00</span></span></td>
<td><span data-ttu-id="d6400-784">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-784">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-785">CC004</span><span class="sxs-lookup"><span data-stu-id="d6400-785">CC004</span></span></td>
<td><span data-ttu-id="d6400-786">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="d6400-786">Packaging</span></span></td>
<td><span data-ttu-id="d6400-787">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-787">10001</span></span></td>
<td><span data-ttu-id="d6400-788">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-788">Electricity</span></span></td>
<td><span data-ttu-id="d6400-789">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-789">Fixed cost</span></span></td>
<td><span data-ttu-id="d6400-790">50,00</span><span class="sxs-lookup"><span data-stu-id="d6400-790">50,00</span></span></td>
<td><span data-ttu-id="d6400-791">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-791">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-792">CC001</span><span class="sxs-lookup"><span data-stu-id="d6400-792">CC001</span></span></td>
<td><span data-ttu-id="d6400-793">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="d6400-793">HR</span></span></td>
<td><span data-ttu-id="d6400-794">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-794">10001</span></span></td>
<td><span data-ttu-id="d6400-795">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-795">Electricity</span></span></td>
<td><span data-ttu-id="d6400-796">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-796">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-797">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="d6400-797">-1,245.71</span></span></td>
<td><span data-ttu-id="d6400-798">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-798">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-799">CC002</span><span class="sxs-lookup"><span data-stu-id="d6400-799">CC002</span></span></td>
<td><span data-ttu-id="d6400-800">Finanzas</span><span class="sxs-lookup"><span data-stu-id="d6400-800">Finance</span></span></td>
<td><span data-ttu-id="d6400-801">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-801">10001</span></span></td>
<td><span data-ttu-id="d6400-802">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-802">Electricity</span></span></td>
<td><span data-ttu-id="d6400-803">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-803">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-804">436.00</span><span class="sxs-lookup"><span data-stu-id="d6400-804">436.00</span></span></td>
<td><span data-ttu-id="d6400-805">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-805">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-806">CC003</span><span class="sxs-lookup"><span data-stu-id="d6400-806">CC003</span></span></td>
<td><span data-ttu-id="d6400-807">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="d6400-807">Assembly</span></span></td>
<td><span data-ttu-id="d6400-808">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-808">10001</span></span></td>
<td><span data-ttu-id="d6400-809">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-809">Electricity</span></span></td>
<td><span data-ttu-id="d6400-810">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-810">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-811">685.14</span><span class="sxs-lookup"><span data-stu-id="d6400-811">685.14</span></span></td>
<td><span data-ttu-id="d6400-812">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-812">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-813">CC004</span><span class="sxs-lookup"><span data-stu-id="d6400-813">CC004</span></span></td>
<td><span data-ttu-id="d6400-814">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="d6400-814">Packaging</span></span></td>
<td><span data-ttu-id="d6400-815">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-815">10001</span></span></td>
<td><span data-ttu-id="d6400-816">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-816">Electricity</span></span></td>
<td><span data-ttu-id="d6400-817">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-817">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-818">124.57</span><span class="sxs-lookup"><span data-stu-id="d6400-818">124.57</span></span></td>
<td><span data-ttu-id="d6400-819">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-819">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-820">CC002</span><span class="sxs-lookup"><span data-stu-id="d6400-820">CC002</span></span></td>
<td><span data-ttu-id="d6400-821">Finanzas</span><span class="sxs-lookup"><span data-stu-id="d6400-821">Finance</span></span></td>
<td><span data-ttu-id="d6400-822">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-822">10001</span></span></td>
<td><span data-ttu-id="d6400-823">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-823">Electricity</span></span></td>
<td><span data-ttu-id="d6400-824">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-824">Fixed cost</span></span></td>
<td><span data-ttu-id="d6400-825">-675,00</span><span class="sxs-lookup"><span data-stu-id="d6400-825">-675.00</span></span></td>
<td><span data-ttu-id="d6400-826">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-826">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-827">CC003</span><span class="sxs-lookup"><span data-stu-id="d6400-827">CC003</span></span></td>
<td><span data-ttu-id="d6400-828">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="d6400-828">Assembly</span></span></td>
<td><span data-ttu-id="d6400-829">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-829">10001</span></span></td>
<td><span data-ttu-id="d6400-830">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-830">Electricity</span></span></td>
<td><span data-ttu-id="d6400-831">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-831">Fixed cost</span></span></td>
<td><span data-ttu-id="d6400-832">438.75</span><span class="sxs-lookup"><span data-stu-id="d6400-832">438.75</span></span></td>
<td><span data-ttu-id="d6400-833">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-833">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-834">CC004</span><span class="sxs-lookup"><span data-stu-id="d6400-834">CC004</span></span></td>
<td><span data-ttu-id="d6400-835">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="d6400-835">Packaging</span></span></td>
<td><span data-ttu-id="d6400-836">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-836">10001</span></span></td>
<td><span data-ttu-id="d6400-837">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-837">Electricity</span></span></td>
<td><span data-ttu-id="d6400-838">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-838">Fixed cost</span></span></td>
<td><span data-ttu-id="d6400-839">236.25</span><span class="sxs-lookup"><span data-stu-id="d6400-839">236.25</span></span></td>
<td><span data-ttu-id="d6400-840">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-840">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-841">CC002</span><span class="sxs-lookup"><span data-stu-id="d6400-841">CC002</span></span></td>
<td><span data-ttu-id="d6400-842">Finanzas</span><span class="sxs-lookup"><span data-stu-id="d6400-842">Finance</span></span></td>
<td><span data-ttu-id="d6400-843">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-843">10001</span></span></td>
<td><span data-ttu-id="d6400-844">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-844">Electricity</span></span></td>
<td><span data-ttu-id="d6400-845">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-845">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-846">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="d6400-846">-8,150.29</span></span></td>
<td><span data-ttu-id="d6400-847">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-847">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-848">CC003</span><span class="sxs-lookup"><span data-stu-id="d6400-848">CC003</span></span></td>
<td><span data-ttu-id="d6400-849">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="d6400-849">Assembly</span></span></td>
<td><span data-ttu-id="d6400-850">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-850">10001</span></span></td>
<td><span data-ttu-id="d6400-851">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-851">Electricity</span></span></td>
<td><span data-ttu-id="d6400-852">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-852">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-853">5,297.69</span><span class="sxs-lookup"><span data-stu-id="d6400-853">5,297.69</span></span></td>
<td><span data-ttu-id="d6400-854">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-854">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-855">CC004</span><span class="sxs-lookup"><span data-stu-id="d6400-855">CC004</span></span></td>
<td><span data-ttu-id="d6400-856">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="d6400-856">Packaging</span></span></td>
<td><span data-ttu-id="d6400-857">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-857">10001</span></span></td>
<td><span data-ttu-id="d6400-858">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-858">Electricity</span></span></td>
<td><span data-ttu-id="d6400-859">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-859">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-860">2,852.60</span><span class="sxs-lookup"><span data-stu-id="d6400-860">2,852.60</span></span></td>
<td><span data-ttu-id="d6400-861">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-861">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-862">CC003</span><span class="sxs-lookup"><span data-stu-id="d6400-862">CC003</span></span></td>
<td><span data-ttu-id="d6400-863">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="d6400-863">Assembly</span></span></td>
<td><span data-ttu-id="d6400-864">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-864">10001</span></span></td>
<td><span data-ttu-id="d6400-865">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-865">Electricity</span></span></td>
<td><span data-ttu-id="d6400-866">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-866">Fixed cost</span></span></td>
<td><span data-ttu-id="d6400-867">-713,75</span><span class="sxs-lookup"><span data-stu-id="d6400-867">-713.75</span></span></td>
<td><span data-ttu-id="d6400-868">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-868">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-869">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6400-869">Prod 1</span></span></td>
<td><span data-ttu-id="d6400-870">Producto 1</span><span class="sxs-lookup"><span data-stu-id="d6400-870">Product 1</span></span></td>
<td><span data-ttu-id="d6400-871">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-871">10001</span></span></td>
<td><span data-ttu-id="d6400-872">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-872">Electricity</span></span></td>
<td><span data-ttu-id="d6400-873">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-873">Fixed cost</span></span></td>
<td><span data-ttu-id="d6400-874">535.31</span><span class="sxs-lookup"><span data-stu-id="d6400-874">535.31</span></span></td>
<td><span data-ttu-id="d6400-875">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-875">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-876">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6400-876">Prod 2</span></span></td>
<td><span data-ttu-id="d6400-877">Producto 2</span><span class="sxs-lookup"><span data-stu-id="d6400-877">Product 2</span></span></td>
<td><span data-ttu-id="d6400-878">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-878">10001</span></span></td>
<td><span data-ttu-id="d6400-879">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-879">Electricity</span></span></td>
<td><span data-ttu-id="d6400-880">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-880">Fixed cost</span></span></td>
<td><span data-ttu-id="d6400-881">178.44</span><span class="sxs-lookup"><span data-stu-id="d6400-881">178.44</span></span></td>
<td><span data-ttu-id="d6400-882">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-882">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-883">CC003</span><span class="sxs-lookup"><span data-stu-id="d6400-883">CC003</span></span></td>
<td><span data-ttu-id="d6400-884">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="d6400-884">Assembly</span></span></td>
<td><span data-ttu-id="d6400-885">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-885">10001</span></span></td>
<td><span data-ttu-id="d6400-886">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-886">Electricity</span></span></td>
<td><span data-ttu-id="d6400-887">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-887">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-888">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="d6400-888">-5,982.83</span></span></td>
<td><span data-ttu-id="d6400-889">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-889">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-890">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6400-890">Prod 1</span></span></td>
<td><span data-ttu-id="d6400-891">Producto 1</span><span class="sxs-lookup"><span data-stu-id="d6400-891">Product 1</span></span></td>
<td><span data-ttu-id="d6400-892">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-892">10001</span></span></td>
<td><span data-ttu-id="d6400-893">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-893">Electricity</span></span></td>
<td><span data-ttu-id="d6400-894">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-894">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-895">4,487.12</span><span class="sxs-lookup"><span data-stu-id="d6400-895">4,487.12</span></span></td>
<td><span data-ttu-id="d6400-896">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-896">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-897">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6400-897">Prod 2</span></span></td>
<td><span data-ttu-id="d6400-898">Producto 2</span><span class="sxs-lookup"><span data-stu-id="d6400-898">Product 2</span></span></td>
<td><span data-ttu-id="d6400-899">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-899">10001</span></span></td>
<td><span data-ttu-id="d6400-900">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-900">Electricity</span></span></td>
<td><span data-ttu-id="d6400-901">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-901">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-902">1,495.71</span><span class="sxs-lookup"><span data-stu-id="d6400-902">1,495.71</span></span></td>
<td><span data-ttu-id="d6400-903">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-903">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-904">CC003</span><span class="sxs-lookup"><span data-stu-id="d6400-904">CC003</span></span></td>
<td><span data-ttu-id="d6400-905">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="d6400-905">Assembly</span></span></td>
<td><span data-ttu-id="d6400-906">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-906">10001</span></span></td>
<td><span data-ttu-id="d6400-907">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-907">Electricity</span></span></td>
<td><span data-ttu-id="d6400-908">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-908">Fixed cost</span></span></td>
<td><span data-ttu-id="d6400-909">-286,25</span><span class="sxs-lookup"><span data-stu-id="d6400-909">-286.25</span></span></td>
<td><span data-ttu-id="d6400-910">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-910">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-911">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6400-911">Prod 1</span></span></td>
<td><span data-ttu-id="d6400-912">Producto 1</span><span class="sxs-lookup"><span data-stu-id="d6400-912">Product 1</span></span></td>
<td><span data-ttu-id="d6400-913">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-913">10001</span></span></td>
<td><span data-ttu-id="d6400-914">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-914">Electricity</span></span></td>
<td><span data-ttu-id="d6400-915">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-915">Fixed cost</span></span></td>
<td><span data-ttu-id="d6400-916">241.05</span><span class="sxs-lookup"><span data-stu-id="d6400-916">241.05</span></span></td>
<td><span data-ttu-id="d6400-917">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-917">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-918">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6400-918">Prod 2</span></span></td>
<td><span data-ttu-id="d6400-919">Producto 2</span><span class="sxs-lookup"><span data-stu-id="d6400-919">Product 2</span></span></td>
<td><span data-ttu-id="d6400-920">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-920">10001</span></span></td>
<td><span data-ttu-id="d6400-921">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-921">Electricity</span></span></td>
<td><span data-ttu-id="d6400-922">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-922">Fixed cost</span></span></td>
<td><span data-ttu-id="d6400-923">45.20</span><span class="sxs-lookup"><span data-stu-id="d6400-923">45.20</span></span></td>
<td><span data-ttu-id="d6400-924">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-924">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-925">CC003</span><span class="sxs-lookup"><span data-stu-id="d6400-925">CC003</span></span></td>
<td><span data-ttu-id="d6400-926">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="d6400-926">Assembly</span></span></td>
<td><span data-ttu-id="d6400-927">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-927">10001</span></span></td>
<td><span data-ttu-id="d6400-928">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-928">Electricity</span></span></td>
<td><span data-ttu-id="d6400-929">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-929">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-930">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="d6400-930">-2,977.17</span></span></td>
<td><span data-ttu-id="d6400-931">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-931">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-932">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6400-932">Prod 1</span></span></td>
<td><span data-ttu-id="d6400-933">Producto 1</span><span class="sxs-lookup"><span data-stu-id="d6400-933">Product 1</span></span></td>
<td><span data-ttu-id="d6400-934">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-934">10001</span></span></td>
<td><span data-ttu-id="d6400-935">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-935">Electricity</span></span></td>
<td><span data-ttu-id="d6400-936">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-936">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-937">2,507.09</span><span class="sxs-lookup"><span data-stu-id="d6400-937">2,507.09</span></span></td>
<td><span data-ttu-id="d6400-938">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-938">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d6400-939">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6400-939">Prod 2</span></span></td>
<td><span data-ttu-id="d6400-940">Producto 2</span><span class="sxs-lookup"><span data-stu-id="d6400-940">Product 2</span></span></td>
<td><span data-ttu-id="d6400-941">10001</span><span class="sxs-lookup"><span data-stu-id="d6400-941">10001</span></span></td>
<td><span data-ttu-id="d6400-942">Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-942">Electricity</span></span></td>
<td><span data-ttu-id="d6400-943">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-943">Variable cost</span></span></td>
<td><span data-ttu-id="d6400-944">470.08</span><span class="sxs-lookup"><span data-stu-id="d6400-944">470.08</span></span></td>
<td><span data-ttu-id="d6400-945">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="d6400-945">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="d6400-946">Conclusión</span><span class="sxs-lookup"><span data-stu-id="d6400-946">Conclusion</span></span>
<span data-ttu-id="d6400-947">En la contabilidad financiera, un coste de 10.000,00 para electricidad se envía a un identificador ficticio de centro de coste.</span><span class="sxs-lookup"><span data-stu-id="d6400-947">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="d6400-948">Por lo tanto, los contables de coste sabrán que este coste se debe asignar.</span><span class="sxs-lookup"><span data-stu-id="d6400-948">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="d6400-949">En contabilidad de costes, los costes fluyen en las unidades organizativas y los niveles en función de las directivas y las reglas que se aplican.</span><span class="sxs-lookup"><span data-stu-id="d6400-949">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="d6400-950">Cada coste se ha asociado con una base de asignación que proporciona la mejor evaluación para la asignación de costes.</span><span class="sxs-lookup"><span data-stu-id="d6400-950">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="d6400-951">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-951">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="d6400-952">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="d6400-952">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="d6400-953">Total</span><span class="sxs-lookup"><span data-stu-id="d6400-953">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="d6400-954">CC099</span><span class="sxs-lookup"><span data-stu-id="d6400-954">CC099</span></span></th>
<th><span data-ttu-id="d6400-955">CC001</span><span class="sxs-lookup"><span data-stu-id="d6400-955">CC001</span></span></th>
<th><span data-ttu-id="d6400-956">CC002</span><span class="sxs-lookup"><span data-stu-id="d6400-956">CC002</span></span></th>
<th><span data-ttu-id="d6400-957">CC003</span><span class="sxs-lookup"><span data-stu-id="d6400-957">CC003</span></span></th>
<th><span data-ttu-id="d6400-958">CC004</span><span class="sxs-lookup"><span data-stu-id="d6400-958">CC004</span></span></th>
<th><span data-ttu-id="d6400-959">Proy 1</span><span class="sxs-lookup"><span data-stu-id="d6400-959">Proj 1</span></span></th>
<th><span data-ttu-id="d6400-960">Proy 2</span><span class="sxs-lookup"><span data-stu-id="d6400-960">Proj 2</span></span></th>
<th><span data-ttu-id="d6400-961">Prod 1</span><span class="sxs-lookup"><span data-stu-id="d6400-961">Prod 1</span></span></th>
<th><span data-ttu-id="d6400-962">Prod 2</span><span class="sxs-lookup"><span data-stu-id="d6400-962">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="d6400-963">10001 Electricidad</span><span class="sxs-lookup"><span data-stu-id="d6400-963">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="d6400-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-965"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="d6400-965"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-966"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="d6400-966"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-967"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="d6400-967"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="d6400-968"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="d6400-968"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-969"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="d6400-969"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-970"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="d6400-970"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-971"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="d6400-971"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-972"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="d6400-972"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="d6400-973">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="d6400-973">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-974">0,00</span><span class="sxs-lookup"><span data-stu-id="d6400-974">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="d6400-975">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="d6400-975">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-976">0,00</span><span class="sxs-lookup"><span data-stu-id="d6400-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-977">0,00</span><span class="sxs-lookup"><span data-stu-id="d6400-977">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-978">0,00</span><span class="sxs-lookup"><span data-stu-id="d6400-978">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-979">0,00</span><span class="sxs-lookup"><span data-stu-id="d6400-979">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-980">0,00</span><span class="sxs-lookup"><span data-stu-id="d6400-980">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="d6400-981">776.36</span><span class="sxs-lookup"><span data-stu-id="d6400-981">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-982">223.64</span><span class="sxs-lookup"><span data-stu-id="d6400-982">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-983"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="d6400-983"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="d6400-984">Coste variable</span><span class="sxs-lookup"><span data-stu-id="d6400-984">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-985">000</span><span class="sxs-lookup"><span data-stu-id="d6400-985">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-986">0,00</span><span class="sxs-lookup"><span data-stu-id="d6400-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-987">0,00</span><span class="sxs-lookup"><span data-stu-id="d6400-987">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-988">0,00</span><span class="sxs-lookup"><span data-stu-id="d6400-988">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-989">0,00</span><span class="sxs-lookup"><span data-stu-id="d6400-989">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-990">30,00</span><span class="sxs-lookup"><span data-stu-id="d6400-990">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-991">10,00</span><span class="sxs-lookup"><span data-stu-id="d6400-991">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-992">6,994.21</span><span class="sxs-lookup"><span data-stu-id="d6400-992">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-993">1,965.79</span><span class="sxs-lookup"><span data-stu-id="d6400-993">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d6400-994"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="d6400-994"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="d6400-995">Este tema muestra cómo un artículo de costes principales, 10001 Electricidad, fluye por los objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="d6400-995">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="d6400-996">Por tanto, estos gastos generales se asignan al nivel más bajo de la organización.</span><span class="sxs-lookup"><span data-stu-id="d6400-996">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="d6400-997">Es decir, los objetos de coste del nivel más bajo son los que soportan el coste.</span><span class="sxs-lookup"><span data-stu-id="d6400-997">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="d6400-998">Si necesita un flujo visual del coste entre los objetos de coste, puede usar las reglas de directivas de acumulación de costes para visualizar el flujo del coste.</span><span class="sxs-lookup"><span data-stu-id="d6400-998">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="d6400-999">Para obtener información detallada, consulte la política de acumulación de costes.</span><span class="sxs-lookup"><span data-stu-id="d6400-999">For more detailed information, see Cost roll-up policy.</span></span> <span data-ttu-id="d6400-1000">(Tenga en cuenta que este tema no se ha completado aún, pero pronto se abordará).</span><span class="sxs-lookup"><span data-stu-id="d6400-1000">(Note that this topic isn't competed yet but is coming soon.)</span></span>




