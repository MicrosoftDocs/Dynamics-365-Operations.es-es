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
ms.openlocfilehash: cef4a80aa12927fdbffea4bb6bcb108ad81494a6
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841498"
---
# <a name="overhead-calculation"></a><span data-ttu-id="fd9ff-103">Cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="fd9ff-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fd9ff-104">Este tema describe los procesos típicos para calcular y asignar costes generales.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="fd9ff-105">Definición del término</span><span class="sxs-lookup"><span data-stu-id="fd9ff-105">Term definition</span></span>
---------------

<span data-ttu-id="fd9ff-106">Los costes generales son costes que se contraen para dirigir un negocio, pero que no pueden ser atribuidos directamente a ninguna actividad empresarial, productos, o servicio específicos.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="fd9ff-107">Los costes generales proporcionan un soporte fundamental a la generación de actividades rentables.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="fd9ff-108">Algunos ejemplos de costes generales son:</span><span class="sxs-lookup"><span data-stu-id="fd9ff-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="fd9ff-109">Alquiler</span><span class="sxs-lookup"><span data-stu-id="fd9ff-109">Rent</span></span>
-   <span data-ttu-id="fd9ff-110">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-110">Electricity</span></span>
-   <span data-ttu-id="fd9ff-111">Sueldos administrativos</span><span class="sxs-lookup"><span data-stu-id="fd9ff-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="fd9ff-112">Visión general del cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="fd9ff-112">Overhead calculation overview</span></span>
<span data-ttu-id="fd9ff-113">El cálculo de costes generales ejecuta las directivas de contabilidad de costes en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="fd9ff-114">Puede calcular varias veces los costes generales del mismo período fiscal si se han cambiado las directivas de contabilidad de costes o se han detectado errores específicos.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="fd9ff-115">Cada ejecución del cálculo de costes generales se almacena y recibe un identificador de versión único que permite comparar los cálculos de diferentes versiones.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="fd9ff-116">Las entradas de costes que el cálculo de costes generales genera reciben una fecha de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="fd9ff-117">Esta fecha de contabilidad coincide con la fecha final del período fiscal que se usa en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="fd9ff-118">El identificador de versión único consiste en los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="fd9ff-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="fd9ff-119">Tipo de versión</span><span class="sxs-lookup"><span data-stu-id="fd9ff-119">Version type</span></span>
-   <span data-ttu-id="fd9ff-120">Fecha y hora</span><span class="sxs-lookup"><span data-stu-id="fd9ff-120">Date and time</span></span>
-   <span data-ttu-id="fd9ff-121">Libro mayor de contabilidad de costes</span><span class="sxs-lookup"><span data-stu-id="fd9ff-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="fd9ff-122">Ejercicio</span><span class="sxs-lookup"><span data-stu-id="fd9ff-122">Fiscal year</span></span>
-   <span data-ttu-id="fd9ff-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="fd9ff-123">Fiscal period</span></span>

<span data-ttu-id="fd9ff-124">El cálculo de costes generales se ejecuta independientemente de la versión.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="fd9ff-125">Por lo tanto, puede calcular la versión de presupuesto antes que la versión real.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="fd9ff-126">El cálculo de costes generales consta de cuatro pasos, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="fd9ff-127">En cada paso, se crea una cabecera de diario que tiene entradas del diario.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="fd9ff-128">Esta cabecera de diario guarda los datos de entrada para cada paso de cálculo.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="fd9ff-129">Las directivas y las reglas se aplican a cada línea de diario, y las entradas de coste se generan como resultado.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="fd9ff-130">Por tanto, siempre se tiene rastreabilidad completa.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="fd9ff-131">[![Cálculo de costes generales](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="fd9ff-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="fd9ff-132">Calcular y asignar costes generales de electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="fd9ff-133">En la contabilidad financiera, algunos costes, como la electricidad, se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="fd9ff-134">Por lo tanto, no se proporciona una visión de gestión detallada para la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="fd9ff-135">En contabilidad de costes, para proporcionar información de gestión correcta en todas las unidades y niveles organizativos, los costes deben fluir por las unidades organizativas.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="fd9ff-136">Este flujo se debe basar en cualquier registro preciso de consumo o en una evaluación justa.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="fd9ff-137">En la contabilidad general, un coste de la electricidad se puede registrar como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fd9ff-138">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="fd9ff-139">Centro de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="fd9ff-140">Cuenta principal</span><span class="sxs-lookup"><span data-stu-id="fd9ff-140">Main account</span></span></th>
<th><span data-ttu-id="fd9ff-141">Importe en la divisa de contabilidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-142">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="fd9ff-143">CC099</span><span class="sxs-lookup"><span data-stu-id="fd9ff-143">CC099</span></span></td>
<td><span data-ttu-id="fd9ff-144">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-144">Default cost center</span></span></td>
<td><span data-ttu-id="fd9ff-145">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-145">10001</span></span></td>
<td><span data-ttu-id="fd9ff-146">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-146">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="fd9ff-148">Paso 1: Procese el cálculo del comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="fd9ff-149">De forma predeterminada, cuando las entradas de coste se importan de los datos de origen, reciben la clasificación de comportamiento del coste **Sin ordenar** en la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="fd9ff-150">Aplicando reglas de directivas de comportamiento de coste, puede reclasificar entradas de coste como **Coste fijo** o **Coste variable**.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="fd9ff-151">Defina la regla de comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-151">Define the cost behavior rule</span></span>

<span data-ttu-id="fd9ff-152">En algunos casos, parte del coste es una cuota fija, y el coste pendiente se basa en el consumo.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="fd9ff-153">Las facturas de electricidad coinciden a menudo con esta definición.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="fd9ff-154">Tras pagar una cuota fija específica, paga el consumo por kilovatio-hora (Kwh).</span><span class="sxs-lookup"><span data-stu-id="fd9ff-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="fd9ff-155">Por ejemplo, si la cuota de coste fijo es de 1.000,00, la regla de comportamiento del coste se define como sigue:</span><span class="sxs-lookup"><span data-stu-id="fd9ff-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="fd9ff-156">Importe fijo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="fd9ff-157">0 &lt;= 1.000,00 = Fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="fd9ff-158">1.000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="fd9ff-159">Diario</span><span class="sxs-lookup"><span data-stu-id="fd9ff-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fd9ff-160">Diario</span><span class="sxs-lookup"><span data-stu-id="fd9ff-160">Journal</span></span></th>
<th><span data-ttu-id="fd9ff-161">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="fd9ff-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="fd9ff-162">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="fd9ff-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="fd9ff-163">Versión</span><span class="sxs-lookup"><span data-stu-id="fd9ff-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-164">00001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-164">00001</span></span></td>
<td><span data-ttu-id="fd9ff-165">Diario de cálculo de comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="fd9ff-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="fd9ff-166">Fiscal</span><span class="sxs-lookup"><span data-stu-id="fd9ff-166">Fiscal</span></span></td>
<td><span data-ttu-id="fd9ff-167">2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-167">2017</span></span></td>
<td><span data-ttu-id="fd9ff-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-168">Period 1</span></span></td>
<td><span data-ttu-id="fd9ff-169">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="fd9ff-170">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="fd9ff-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fd9ff-171">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="fd9ff-172">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="fd9ff-173">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-173">Cost element</span></span></th>
<th><span data-ttu-id="fd9ff-174">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="fd9ff-174">Cost behavior</span></span></th>
<th><span data-ttu-id="fd9ff-175">Importe</span><span class="sxs-lookup"><span data-stu-id="fd9ff-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-176">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="fd9ff-177">CC099</span><span class="sxs-lookup"><span data-stu-id="fd9ff-177">CC099</span></span></td>
<td><span data-ttu-id="fd9ff-178">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-178">Default cost center</span></span></td>
<td><span data-ttu-id="fd9ff-179">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-179">10001</span></span></td>
<td><span data-ttu-id="fd9ff-180">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-180">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-181">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="fd9ff-181">Unclassified</span></span></td>
<td><span data-ttu-id="fd9ff-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="fd9ff-183">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="fd9ff-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fd9ff-184">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="fd9ff-185">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-185">Cost element</span></span></th>
<th><span data-ttu-id="fd9ff-186">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="fd9ff-186">Cost behavior</span></span></th>
<th><span data-ttu-id="fd9ff-187">Importe</span><span class="sxs-lookup"><span data-stu-id="fd9ff-187">Amount</span></span></th>
<th><span data-ttu-id="fd9ff-188">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-189">CC099</span><span class="sxs-lookup"><span data-stu-id="fd9ff-189">CC099</span></span></td>
<td><span data-ttu-id="fd9ff-190">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-190">Default cost center</span></span></td>
<td><span data-ttu-id="fd9ff-191">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-191">10001</span></span></td>
<td><span data-ttu-id="fd9ff-192">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-192">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-193">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="fd9ff-193">Unclassified</span></span></td>
<td><span data-ttu-id="fd9ff-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-194">10,000.00</span></span></td>
<td><span data-ttu-id="fd9ff-195">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-196">CC099</span><span class="sxs-lookup"><span data-stu-id="fd9ff-196">CC099</span></span></td>
<td><span data-ttu-id="fd9ff-197">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-197">Default cost center</span></span></td>
<td><span data-ttu-id="fd9ff-198">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-198">10001</span></span></td>
<td><span data-ttu-id="fd9ff-199">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-199">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-200">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="fd9ff-200">Unclassified</span></span></td>
<td><span data-ttu-id="fd9ff-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-201">-10,000.00</span></span></td>
<td><span data-ttu-id="fd9ff-202">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-203">CC099</span><span class="sxs-lookup"><span data-stu-id="fd9ff-203">CC099</span></span></td>
<td><span data-ttu-id="fd9ff-204">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-204">Default cost center</span></span></td>
<td><span data-ttu-id="fd9ff-205">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-205">10001</span></span></td>
<td><span data-ttu-id="fd9ff-206">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-206">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-207">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-207">Fixed cost</span></span></td>
<td><span data-ttu-id="fd9ff-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-208">1,000.00</span></span></td>
<td><span data-ttu-id="fd9ff-209">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-210">CC099</span><span class="sxs-lookup"><span data-stu-id="fd9ff-210">CC099</span></span></td>
<td><span data-ttu-id="fd9ff-211">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-211">Default cost center</span></span></td>
<td><span data-ttu-id="fd9ff-212">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-212">10001</span></span></td>
<td><span data-ttu-id="fd9ff-213">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-213">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-214">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-214">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-215">9,000.00</span></span></td>
<td><span data-ttu-id="fd9ff-216">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fd9ff-217">Para obtener más información, consulte [Crear y asignar una directiva de comportamiento de costes a una unidad de control de costes](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="fd9ff-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="fd9ff-218">Paso 2: Procese el cálculo de distribución de costes</span><span class="sxs-lookup"><span data-stu-id="fd9ff-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="fd9ff-219">La distribución de costes se usa para redistribuir costes desde un objeto de coste a uno o más objetos de coste aplicando una base relevante de la asignación.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="fd9ff-220">La distribución de costes y la asignación de costes difieren en que la distribución de costes siempre se produce en el nivel de elemento de costes principal del coste original.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="fd9ff-221">Defina la regla de distribución del coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-221">Define the cost distribution rule</span></span>

<span data-ttu-id="fd9ff-222">En la contabilidad financiera, los costes de electricidad se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="fd9ff-223">En contabilidad de costes, este método no es suficientemente detallado.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="fd9ff-224">El coste variable debe distribuirse a los objetos individuales de coste aplicando una base justa.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="fd9ff-225">La base de asignación más lógica es el consumo de electricidad (Kwh).</span><span class="sxs-lookup"><span data-stu-id="fd9ff-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="fd9ff-226">Se crea un miembro de dimensión estadística que se denomina Electricity, y se registra el consumo de electricidad.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="fd9ff-227">De forma predeterminada, todos los miembros de dimensión estadísticos estarán disponibles como bases de asignación.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fd9ff-228">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-228">Cost object</span></span></th>
<th><span data-ttu-id="fd9ff-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="fd9ff-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-230">CC001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-230">CC001</span></span></td>
<td><span data-ttu-id="fd9ff-231">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-231">HR</span></span></td>
<td><span data-ttu-id="fd9ff-232">1.000</span><span class="sxs-lookup"><span data-stu-id="fd9ff-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-233">CC002</span><span class="sxs-lookup"><span data-stu-id="fd9ff-233">CC002</span></span></td>
<td><span data-ttu-id="fd9ff-234">Finanzas</span><span class="sxs-lookup"><span data-stu-id="fd9ff-234">Finance</span></span></td>
<td><span data-ttu-id="fd9ff-235">6.000</span><span class="sxs-lookup"><span data-stu-id="fd9ff-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-236">CC003</span><span class="sxs-lookup"><span data-stu-id="fd9ff-236">CC003</span></span></td>
<td><span data-ttu-id="fd9ff-237">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-237">Assembly</span></span></td>
<td><span data-ttu-id="fd9ff-238">0</span><span class="sxs-lookup"><span data-stu-id="fd9ff-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fd9ff-239">La tabla siguiente muestra el resultado cuando se aplica el consumo de electricidad como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fd9ff-240">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-240">Cost object</span></span></th>
<th><span data-ttu-id="fd9ff-241">Magnitud</span><span class="sxs-lookup"><span data-stu-id="fd9ff-241">Magnitude</span></span></th>
<th><span data-ttu-id="fd9ff-242">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="fd9ff-242">Allocation factor</span></span></th>
<th><span data-ttu-id="fd9ff-243">Importe</span><span class="sxs-lookup"><span data-stu-id="fd9ff-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-244">CC001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-244">CC001</span></span></td>
<td><span data-ttu-id="fd9ff-245">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-245">HR</span></span></td>
<td><span data-ttu-id="fd9ff-246">1.000</span><span class="sxs-lookup"><span data-stu-id="fd9ff-246">1,000</span></span></td>
<td><span data-ttu-id="fd9ff-247">(1.000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="fd9ff-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="fd9ff-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-249">CC002</span><span class="sxs-lookup"><span data-stu-id="fd9ff-249">CC002</span></span></td>
<td><span data-ttu-id="fd9ff-250">Finanzas</span><span class="sxs-lookup"><span data-stu-id="fd9ff-250">Finance</span></span></td>
<td><span data-ttu-id="fd9ff-251">6.000</span><span class="sxs-lookup"><span data-stu-id="fd9ff-251">6,000</span></span></td>
<td><span data-ttu-id="fd9ff-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="fd9ff-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="fd9ff-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-254">CC003</span><span class="sxs-lookup"><span data-stu-id="fd9ff-254">CC003</span></span></td>
<td><span data-ttu-id="fd9ff-255">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-255">Assembly</span></span></td>
<td><span data-ttu-id="fd9ff-256">0</span><span class="sxs-lookup"><span data-stu-id="fd9ff-256">0</span></span></td>
<td><span data-ttu-id="fd9ff-257">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="fd9ff-258">0,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fd9ff-259">El coste fijo debe distribuirse uniformemente a los objetos individuales de costes que han consumido electricidad.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="fd9ff-260">Puede obtener este resultado usando el miembro de dimensión estadístico de electricidad en una base de asignación de la fórmula: (Electricidad &gt; 0,00) La tabla siguiente muestra el resultado cuando el consumo de electricidad se aplica como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fd9ff-261">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-261">Cost object</span></span></th>
<th><span data-ttu-id="fd9ff-262">Fórmula</span><span class="sxs-lookup"><span data-stu-id="fd9ff-262">Formula</span></span></th>
<th><span data-ttu-id="fd9ff-263">Magnitud</span><span class="sxs-lookup"><span data-stu-id="fd9ff-263">Magnitude</span></span></th>
<th><span data-ttu-id="fd9ff-264">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="fd9ff-264">Allocation factor</span></span></th>
<th><span data-ttu-id="fd9ff-265">Importe</span><span class="sxs-lookup"><span data-stu-id="fd9ff-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-266">CC001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-266">CC001</span></span></td>
<td><span data-ttu-id="fd9ff-267">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-267">HR</span></span></td>
<td><span data-ttu-id="fd9ff-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="fd9ff-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="fd9ff-269">1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-269">1</span></span></td>
<td><span data-ttu-id="fd9ff-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="fd9ff-271">500,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-272">CC002</span><span class="sxs-lookup"><span data-stu-id="fd9ff-272">CC002</span></span></td>
<td><span data-ttu-id="fd9ff-273">Finanzas</span><span class="sxs-lookup"><span data-stu-id="fd9ff-273">Finance</span></span></td>
<td><span data-ttu-id="fd9ff-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="fd9ff-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="fd9ff-275">1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-275">1</span></span></td>
<td><span data-ttu-id="fd9ff-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="fd9ff-277">500,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-278">CC003</span><span class="sxs-lookup"><span data-stu-id="fd9ff-278">CC003</span></span></td>
<td><span data-ttu-id="fd9ff-279">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-279">Assembly</span></span></td>
<td><span data-ttu-id="fd9ff-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="fd9ff-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="fd9ff-281">0</span><span class="sxs-lookup"><span data-stu-id="fd9ff-281">0</span></span></td>
<td><span data-ttu-id="fd9ff-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="fd9ff-283">0,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="fd9ff-284">Diario</span><span class="sxs-lookup"><span data-stu-id="fd9ff-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fd9ff-285">Diario</span><span class="sxs-lookup"><span data-stu-id="fd9ff-285">Journal</span></span></th>
<th><span data-ttu-id="fd9ff-286">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="fd9ff-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="fd9ff-287">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="fd9ff-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="fd9ff-288">Versión</span><span class="sxs-lookup"><span data-stu-id="fd9ff-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-289">00002</span><span class="sxs-lookup"><span data-stu-id="fd9ff-289">00002</span></span></td>
<td><span data-ttu-id="fd9ff-290">Diario de cálculo de la distribución de costes</span><span class="sxs-lookup"><span data-stu-id="fd9ff-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="fd9ff-291">Fiscal</span><span class="sxs-lookup"><span data-stu-id="fd9ff-291">Fiscal</span></span></td>
<td><span data-ttu-id="fd9ff-292">2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-292">2017</span></span></td>
<td><span data-ttu-id="fd9ff-293">Período 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-293">Period 1</span></span></td>
<td><span data-ttu-id="fd9ff-294">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="fd9ff-295">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="fd9ff-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fd9ff-296">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="fd9ff-297">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="fd9ff-298">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-298">Cost element</span></span></th>
<th><span data-ttu-id="fd9ff-299">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="fd9ff-299">Cost behavior</span></span></th>
<th><span data-ttu-id="fd9ff-300">Importe</span><span class="sxs-lookup"><span data-stu-id="fd9ff-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-301">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="fd9ff-302">CC099</span><span class="sxs-lookup"><span data-stu-id="fd9ff-302">CC099</span></span></td>
<td><span data-ttu-id="fd9ff-303">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-303">Default cost center</span></span></td>
<td><span data-ttu-id="fd9ff-304">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-304">10001</span></span></td>
<td><span data-ttu-id="fd9ff-305">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-305">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-306">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-306">Fixed cost</span></span></td>
<td><span data-ttu-id="fd9ff-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-308">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="fd9ff-309">CC099</span><span class="sxs-lookup"><span data-stu-id="fd9ff-309">CC099</span></span></td>
<td><span data-ttu-id="fd9ff-310">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-310">Default cost center</span></span></td>
<td><span data-ttu-id="fd9ff-311">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-311">10001</span></span></td>
<td><span data-ttu-id="fd9ff-312">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-312">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-313">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-313">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-314">9.000,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="fd9ff-315">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="fd9ff-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fd9ff-316">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="fd9ff-317">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-317">Cost element</span></span></th>
<th><span data-ttu-id="fd9ff-318">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="fd9ff-318">Cost behavior</span></span></th>
<th><span data-ttu-id="fd9ff-319">Importe</span><span class="sxs-lookup"><span data-stu-id="fd9ff-319">Amount</span></span></th>
<th><span data-ttu-id="fd9ff-320">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-321">CC099</span><span class="sxs-lookup"><span data-stu-id="fd9ff-321">CC099</span></span></td>
<td><span data-ttu-id="fd9ff-322">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-322">Default cost center</span></span></td>
<td><span data-ttu-id="fd9ff-323">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-323">10001</span></span></td>
<td><span data-ttu-id="fd9ff-324">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-324">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-325">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-325">Fixed cost</span></span></td>
<td><span data-ttu-id="fd9ff-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-326">-1,000.00</span></span></td>
<td><span data-ttu-id="fd9ff-327">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-328">CC001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-328">CC001</span></span></td>
<td><span data-ttu-id="fd9ff-329">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-329">HR</span></span></td>
<td><span data-ttu-id="fd9ff-330">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-330">10001</span></span></td>
<td><span data-ttu-id="fd9ff-331">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-331">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-332">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-332">Fixed cost</span></span></td>
<td><span data-ttu-id="fd9ff-333">500,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-333">500.00</span></span></td>
<td><span data-ttu-id="fd9ff-334">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-335">CC002</span><span class="sxs-lookup"><span data-stu-id="fd9ff-335">CC002</span></span></td>
<td><span data-ttu-id="fd9ff-336">Finanzas</span><span class="sxs-lookup"><span data-stu-id="fd9ff-336">Finance</span></span></td>
<td><span data-ttu-id="fd9ff-337">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-337">10001</span></span></td>
<td><span data-ttu-id="fd9ff-338">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-338">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-339">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-339">Fixed cost</span></span></td>
<td><span data-ttu-id="fd9ff-340">500,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-340">500.00</span></span></td>
<td><span data-ttu-id="fd9ff-341">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-342">CC099</span><span class="sxs-lookup"><span data-stu-id="fd9ff-342">CC099</span></span></td>
<td><span data-ttu-id="fd9ff-343">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-343">Default cost center</span></span></td>
<td><span data-ttu-id="fd9ff-344">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-344">10001</span></span></td>
<td><span data-ttu-id="fd9ff-345">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-345">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-346">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-346">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-347">-9,000.00</span></span></td>
<td><span data-ttu-id="fd9ff-348">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-349">CC001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-349">CC001</span></span></td>
<td><span data-ttu-id="fd9ff-350">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-350">HR</span></span></td>
<td><span data-ttu-id="fd9ff-351">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-351">10001</span></span></td>
<td><span data-ttu-id="fd9ff-352">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-352">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-353">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-353">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="fd9ff-354">1,285.71</span></span></td>
<td><span data-ttu-id="fd9ff-355">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-356">CC002</span><span class="sxs-lookup"><span data-stu-id="fd9ff-356">CC002</span></span></td>
<td><span data-ttu-id="fd9ff-357">Finanzas</span><span class="sxs-lookup"><span data-stu-id="fd9ff-357">Finance</span></span></td>
<td><span data-ttu-id="fd9ff-358">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-358">10001</span></span></td>
<td><span data-ttu-id="fd9ff-359">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-359">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-360">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-360">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="fd9ff-361">7,714.29</span></span></td>
<td><span data-ttu-id="fd9ff-362">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fd9ff-363">Para obtener más información, consulte [Crear y asignar una directiva de distribución de costes a una unidad de control de costes](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="fd9ff-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="fd9ff-364">Paso 3: Procese el cálculo de las tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="fd9ff-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="fd9ff-365">La tasa de costes generales se usa para cargar uno o varios objetos de coste específicos.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="fd9ff-366">El cargo se basa en un índice de coste predeterminado y la magnitud de la base de asignación asignada.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="fd9ff-367">Defina la tasa de costes generales</span><span class="sxs-lookup"><span data-stu-id="fd9ff-367">Define the overhead rate</span></span>

<span data-ttu-id="fd9ff-368">El objeto de coste CC001 HR contribuye a un conjunto de proyectos internos.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="fd9ff-369">Se crea un miembro de dimensión estadística que se denomina proyectos HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fd9ff-370">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-370">Cost object</span></span></th>
<th><span data-ttu-id="fd9ff-371">Horas</span><span class="sxs-lookup"><span data-stu-id="fd9ff-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-372">Proy 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-372">Proj 1</span></span></td>
<td><span data-ttu-id="fd9ff-373">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-373">Project 1</span></span></td>
<td><span data-ttu-id="fd9ff-374">3</span><span class="sxs-lookup"><span data-stu-id="fd9ff-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-375">Proy 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-375">Proj 2</span></span></td>
<td><span data-ttu-id="fd9ff-376">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-376">Project 2</span></span></td>
<td><span data-ttu-id="fd9ff-377">1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fd9ff-378">Una tasa de coste predeterminada para la contribución de los proyectos de coste se ha definido.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fd9ff-379">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-379">Cost object</span></span></th>
<th><span data-ttu-id="fd9ff-380">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-380">Cost element</span></span></th>
<th><span data-ttu-id="fd9ff-381">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="fd9ff-381">Cost behavior</span></span></th>
<th><span data-ttu-id="fd9ff-382">Unidades</span><span class="sxs-lookup"><span data-stu-id="fd9ff-382">Units</span></span></th>
<th><span data-ttu-id="fd9ff-383">Índice</span><span class="sxs-lookup"><span data-stu-id="fd9ff-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-384">CC001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-384">CC001</span></span></td>
<td><span data-ttu-id="fd9ff-385">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-385">HR</span></span></td>
<td><span data-ttu-id="fd9ff-386">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-386">10001</span></span></td>
<td><span data-ttu-id="fd9ff-387">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-387">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-388">1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-388">1</span></span></td>
<td><span data-ttu-id="fd9ff-389">10</span><span class="sxs-lookup"><span data-stu-id="fd9ff-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fd9ff-390">La tabla siguiente muestra el resultado cuando los proyectos HR se aplican como base de la asignación.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fd9ff-391">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-391">Cost object</span></span></th>
<th><span data-ttu-id="fd9ff-392">Magnitud</span><span class="sxs-lookup"><span data-stu-id="fd9ff-392">Magnitude</span></span></th>
<th><span data-ttu-id="fd9ff-393">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-393">Cost element</span></span></th>
<th><span data-ttu-id="fd9ff-394">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="fd9ff-394">Allocation factor</span></span></th>
<th><span data-ttu-id="fd9ff-395">Importe</span><span class="sxs-lookup"><span data-stu-id="fd9ff-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-396">Proy 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-396">Proj 1</span></span></td>
<td><span data-ttu-id="fd9ff-397">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-397">Project 1</span></span></td>
<td><span data-ttu-id="fd9ff-398">3</span><span class="sxs-lookup"><span data-stu-id="fd9ff-398">3</span></span></td>
<td><span data-ttu-id="fd9ff-399">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-399">10001</span></span></td>
<td><span data-ttu-id="fd9ff-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="fd9ff-401">30,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-402">Proy 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-402">Proj 2</span></span></td>
<td><span data-ttu-id="fd9ff-403">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-403">Project 2</span></span></td>
<td><span data-ttu-id="fd9ff-404">1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-404">1</span></span></td>
<td><span data-ttu-id="fd9ff-405">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-405">10001</span></span></td>
<td><span data-ttu-id="fd9ff-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="fd9ff-407">10,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="fd9ff-408">Diario</span><span class="sxs-lookup"><span data-stu-id="fd9ff-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fd9ff-409">Diario</span><span class="sxs-lookup"><span data-stu-id="fd9ff-409">Journal</span></span></th>
<th><span data-ttu-id="fd9ff-410">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="fd9ff-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="fd9ff-411">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="fd9ff-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="fd9ff-412">Versión</span><span class="sxs-lookup"><span data-stu-id="fd9ff-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-413">00003</span><span class="sxs-lookup"><span data-stu-id="fd9ff-413">00003</span></span></td>
<td><span data-ttu-id="fd9ff-414">Diario de cálculo de tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="fd9ff-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="fd9ff-415">Fiscal</span><span class="sxs-lookup"><span data-stu-id="fd9ff-415">Fiscal</span></span></td>
<td><span data-ttu-id="fd9ff-416">2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-416">2017</span></span></td>
<td><span data-ttu-id="fd9ff-417">Período 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-417">Period 1</span></span></td>
<td><span data-ttu-id="fd9ff-418">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="fd9ff-419">Entradas de diario (entradas de diario para cálculo de tasas de costes generales)</span><span class="sxs-lookup"><span data-stu-id="fd9ff-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fd9ff-420">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="fd9ff-421">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-421">Cost object</span></span></th>
<th><span data-ttu-id="fd9ff-422">Magnitud</span><span class="sxs-lookup"><span data-stu-id="fd9ff-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-423">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="fd9ff-424">Proy 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-424">Proj 1</span></span></td>
<td><span data-ttu-id="fd9ff-425">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="fd9ff-426">3,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-427">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="fd9ff-428">Proy 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-428">Proj 2</span></span></td>
<td><span data-ttu-id="fd9ff-429">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="fd9ff-430">1,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="fd9ff-431">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="fd9ff-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fd9ff-432">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="fd9ff-433">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-433">Cost element</span></span></th>
<th><span data-ttu-id="fd9ff-434">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="fd9ff-434">Cost behavior</span></span></th>
<th><span data-ttu-id="fd9ff-435">Importe</span><span class="sxs-lookup"><span data-stu-id="fd9ff-435">Amount</span></span></th>
<th><span data-ttu-id="fd9ff-436">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-437">CC0001</span></span></td>
<td><span data-ttu-id="fd9ff-438">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-438">HR</span></span></td>
<td><span data-ttu-id="fd9ff-439">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-439">10001</span></span></td>
<td><span data-ttu-id="fd9ff-440">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-440">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-441">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-441">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-442">-30.00</span></span></td>
<td><span data-ttu-id="fd9ff-443">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-444">Proy 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-444">Proj 1</span></span></td>
<td><span data-ttu-id="fd9ff-445">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="fd9ff-446">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-446">10001</span></span></td>
<td><span data-ttu-id="fd9ff-447">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-447">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-448">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-448">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-449">30,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-449">30.00</span></span></td>
<td><span data-ttu-id="fd9ff-450">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-451">CC001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-451">CC001</span></span></td>
<td><span data-ttu-id="fd9ff-452">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-452">HR</span></span></td>
<td><span data-ttu-id="fd9ff-453">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-453">10001</span></span></td>
<td><span data-ttu-id="fd9ff-454">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-454">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-455">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-455">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-456">-10.00</span></span></td>
<td><span data-ttu-id="fd9ff-457">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-458">Proy 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-458">Proj 2</span></span></td>
<td><span data-ttu-id="fd9ff-459">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="fd9ff-460">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-460">10001</span></span></td>
<td><span data-ttu-id="fd9ff-461">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-461">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-462">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-462">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-463">10,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-463">10.00</span></span></td>
<td><span data-ttu-id="fd9ff-464">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fd9ff-465">Para obtener más información, consulte [Realizar cálculo de costes generales](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="fd9ff-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="fd9ff-466">Paso 4: Procese el cálculo de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="fd9ff-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="fd9ff-467">La asignación es utilizada para asignar el saldo de un objeto de coste a otros objetos de coste aplicando una base de asignación.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="fd9ff-468">Finance and Operations admite el método de asignación recíproco.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-468">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="fd9ff-469">En el método de asignación recíproco, se reconocen completamente los servicios mutuos que los objetos de coste auxiliar intercambian.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="fd9ff-470">El sistema determina automáticamente el orden correcto para realizar las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="fd9ff-471">El saldo de un objeto de coste se asigna según una única base de asignación.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="fd9ff-472">Las asignaciones entre dimensiones de objetos de coste y sus miembros respectivos se admiten.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="fd9ff-473">El orden de asignación se controla por unidad de control de costes.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="fd9ff-474">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="fd9ff-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="fd9ff-475">Defina la asignación de costes</span><span class="sxs-lookup"><span data-stu-id="fd9ff-475">Define the cost allocation</span></span>

<span data-ttu-id="fd9ff-476">A continuación se indica un ejemplo sencillo que explica cómo puede realizar el seguimiento del flujo de coste.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="fd9ff-477">El objeto de coste CC001 HR contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="fd9ff-478">Se crea un miembro de dimensión estadística que se denomina servicios HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fd9ff-479">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-479">Cost object</span></span></th>
<th><span data-ttu-id="fd9ff-480">Servicios HR</span><span class="sxs-lookup"><span data-stu-id="fd9ff-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-481">CC002</span><span class="sxs-lookup"><span data-stu-id="fd9ff-481">CC002</span></span></td>
<td><span data-ttu-id="fd9ff-482">Finanzas</span><span class="sxs-lookup"><span data-stu-id="fd9ff-482">Finance</span></span></td>
<td><span data-ttu-id="fd9ff-483">35</span><span class="sxs-lookup"><span data-stu-id="fd9ff-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-484">CC003</span><span class="sxs-lookup"><span data-stu-id="fd9ff-484">CC003</span></span></td>
<td><span data-ttu-id="fd9ff-485">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-485">Assembly</span></span></td>
<td><span data-ttu-id="fd9ff-486">55</span><span class="sxs-lookup"><span data-stu-id="fd9ff-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-487">CC004</span><span class="sxs-lookup"><span data-stu-id="fd9ff-487">CC004</span></span></td>
<td><span data-ttu-id="fd9ff-488">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-488">Packaging</span></span></td>
<td><span data-ttu-id="fd9ff-489">10</span><span class="sxs-lookup"><span data-stu-id="fd9ff-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fd9ff-490">El objeto de coste CC002 Finanzas contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="fd9ff-491">Se crea un miembro de dimensión estadística que se denomina Finanzas para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fd9ff-492">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-492">Cost object</span></span></th>
<th><span data-ttu-id="fd9ff-493">Servicios financieros</span><span class="sxs-lookup"><span data-stu-id="fd9ff-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-494">CC003</span><span class="sxs-lookup"><span data-stu-id="fd9ff-494">CC003</span></span></td>
<td><span data-ttu-id="fd9ff-495">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-495">Assembly</span></span></td>
<td><span data-ttu-id="fd9ff-496">65</span><span class="sxs-lookup"><span data-stu-id="fd9ff-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-497">CC004</span><span class="sxs-lookup"><span data-stu-id="fd9ff-497">CC004</span></span></td>
<td><span data-ttu-id="fd9ff-498">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-498">Packaging</span></span></td>
<td><span data-ttu-id="fd9ff-499">35</span><span class="sxs-lookup"><span data-stu-id="fd9ff-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fd9ff-500">El objeto de coste CC003 Asamblea contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="fd9ff-501">Se crea un miembro de dimensión estadística que se denomina servicios de Asamblea para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fd9ff-502">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-502">Cost object</span></span></th>
<th><span data-ttu-id="fd9ff-503">Servicios de la asamblea (horas)</span><span class="sxs-lookup"><span data-stu-id="fd9ff-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-504">Prod 1</span></span></td>
<td><span data-ttu-id="fd9ff-505">Producto 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-505">Product 1</span></span></td>
<td><span data-ttu-id="fd9ff-506">60</span><span class="sxs-lookup"><span data-stu-id="fd9ff-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-507">Prod 2</span></span></td>
<td><span data-ttu-id="fd9ff-508">Producto 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-508">Product 2</span></span></td>
<td><span data-ttu-id="fd9ff-509">20</span><span class="sxs-lookup"><span data-stu-id="fd9ff-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fd9ff-510">El objeto de coste CC004 Embalaje contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="fd9ff-511">Se crea un miembro de dimensión estadística que se denomina servicios de Embalaje para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fd9ff-512">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-512">Cost object</span></span></th>
<th><span data-ttu-id="fd9ff-513">Servicios de embalaje (horas)</span><span class="sxs-lookup"><span data-stu-id="fd9ff-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-514">Prod 1</span></span></td>
<td><span data-ttu-id="fd9ff-515">Producto 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-515">Product 1</span></span></td>
<td><span data-ttu-id="fd9ff-516">80</span><span class="sxs-lookup"><span data-stu-id="fd9ff-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-517">Prod 2</span></span></td>
<td><span data-ttu-id="fd9ff-518">Producto 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-518">Product 2</span></span></td>
<td><span data-ttu-id="fd9ff-519">15</span><span class="sxs-lookup"><span data-stu-id="fd9ff-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="fd9ff-520">En Finance and Operations, las medidas estadísticas como las horas de la producción que un producto consume se pueden deducir de los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-520">In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="fd9ff-521">Para obtener más información, vea [Plantilla de proveedor de medidas estadísticas](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="fd9ff-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="fd9ff-522">La tabla siguiente muestra el resultado cuando se aplican los servicios de HR como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="fd9ff-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fd9ff-523">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-523">Cost object</span></span></th>
<th><span data-ttu-id="fd9ff-524">Magnitud</span><span class="sxs-lookup"><span data-stu-id="fd9ff-524">Magnitude</span></span></th>
<th><span data-ttu-id="fd9ff-525">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="fd9ff-525">Allocation factor</span></span></th>
<th><span data-ttu-id="fd9ff-526">Importe</span><span class="sxs-lookup"><span data-stu-id="fd9ff-526">Amount</span></span></th>
<th><span data-ttu-id="fd9ff-527">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="fd9ff-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-528">CC002</span><span class="sxs-lookup"><span data-stu-id="fd9ff-528">CC002</span></span></td>
<td><span data-ttu-id="fd9ff-529">Finanzas</span><span class="sxs-lookup"><span data-stu-id="fd9ff-529">Finance</span></span></td>
<td><span data-ttu-id="fd9ff-530">35</span><span class="sxs-lookup"><span data-stu-id="fd9ff-530">35</span></span></td>
<td><span data-ttu-id="fd9ff-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="fd9ff-532">175.00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-532">175.00</span></span></td>
<td><span data-ttu-id="fd9ff-533">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-534">CC003</span><span class="sxs-lookup"><span data-stu-id="fd9ff-534">CC003</span></span></td>
<td><span data-ttu-id="fd9ff-535">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-535">Assembly</span></span></td>
<td><span data-ttu-id="fd9ff-536">55</span><span class="sxs-lookup"><span data-stu-id="fd9ff-536">55</span></span></td>
<td><span data-ttu-id="fd9ff-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="fd9ff-538">275.00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-538">275.00</span></span></td>
<td><span data-ttu-id="fd9ff-539">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-540">CC004</span><span class="sxs-lookup"><span data-stu-id="fd9ff-540">CC004</span></span></td>
<td><span data-ttu-id="fd9ff-541">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-541">Packaging</span></span></td>
<td><span data-ttu-id="fd9ff-542">10</span><span class="sxs-lookup"><span data-stu-id="fd9ff-542">10</span></span></td>
<td><span data-ttu-id="fd9ff-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="fd9ff-544">50,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-544">50.00</span></span></td>
<td><span data-ttu-id="fd9ff-545">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-546">CC002</span><span class="sxs-lookup"><span data-stu-id="fd9ff-546">CC002</span></span></td>
<td><span data-ttu-id="fd9ff-547">Finanzas</span><span class="sxs-lookup"><span data-stu-id="fd9ff-547">Finance</span></span></td>
<td><span data-ttu-id="fd9ff-548">35</span><span class="sxs-lookup"><span data-stu-id="fd9ff-548">35</span></span></td>
<td><span data-ttu-id="fd9ff-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="fd9ff-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="fd9ff-550">436.00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-550">436.00</span></span></td>
<td><span data-ttu-id="fd9ff-551">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-552">CC003</span><span class="sxs-lookup"><span data-stu-id="fd9ff-552">CC003</span></span></td>
<td><span data-ttu-id="fd9ff-553">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-553">Assembly</span></span></td>
<td><span data-ttu-id="fd9ff-554">55</span><span class="sxs-lookup"><span data-stu-id="fd9ff-554">55</span></span></td>
<td><span data-ttu-id="fd9ff-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="fd9ff-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="fd9ff-556">685.14</span><span class="sxs-lookup"><span data-stu-id="fd9ff-556">685.14</span></span></td>
<td><span data-ttu-id="fd9ff-557">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-558">CC004</span><span class="sxs-lookup"><span data-stu-id="fd9ff-558">CC004</span></span></td>
<td><span data-ttu-id="fd9ff-559">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-559">Packaging</span></span></td>
<td><span data-ttu-id="fd9ff-560">10</span><span class="sxs-lookup"><span data-stu-id="fd9ff-560">10</span></span></td>
<td><span data-ttu-id="fd9ff-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="fd9ff-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="fd9ff-562">124.57</span><span class="sxs-lookup"><span data-stu-id="fd9ff-562">124.57</span></span></td>
<td><span data-ttu-id="fd9ff-563">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fd9ff-564">La tabla siguiente muestra el resultado cuando se aplican los servicios de Finanzas como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="fd9ff-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fd9ff-565">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-565">Cost object</span></span></th>
<th><span data-ttu-id="fd9ff-566">Magnitud</span><span class="sxs-lookup"><span data-stu-id="fd9ff-566">Magnitude</span></span></th>
<th><span data-ttu-id="fd9ff-567">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="fd9ff-567">Allocation factor</span></span></th>
<th><span data-ttu-id="fd9ff-568">Importe</span><span class="sxs-lookup"><span data-stu-id="fd9ff-568">Amount</span></span></th>
<th><span data-ttu-id="fd9ff-569">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="fd9ff-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-570">CC003</span><span class="sxs-lookup"><span data-stu-id="fd9ff-570">CC003</span></span></td>
<td><span data-ttu-id="fd9ff-571">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-571">Assembly</span></span></td>
<td><span data-ttu-id="fd9ff-572">65</span><span class="sxs-lookup"><span data-stu-id="fd9ff-572">65</span></span></td>
<td><span data-ttu-id="fd9ff-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="fd9ff-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="fd9ff-574">438.75</span><span class="sxs-lookup"><span data-stu-id="fd9ff-574">438.75</span></span></td>
<td><span data-ttu-id="fd9ff-575">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-576">CC004</span><span class="sxs-lookup"><span data-stu-id="fd9ff-576">CC004</span></span></td>
<td><span data-ttu-id="fd9ff-577">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-577">Packaging</span></span></td>
<td><span data-ttu-id="fd9ff-578">35</span><span class="sxs-lookup"><span data-stu-id="fd9ff-578">35</span></span></td>
<td><span data-ttu-id="fd9ff-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="fd9ff-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="fd9ff-580">236.25</span><span class="sxs-lookup"><span data-stu-id="fd9ff-580">236.25</span></span></td>
<td><span data-ttu-id="fd9ff-581">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-582">CC003</span><span class="sxs-lookup"><span data-stu-id="fd9ff-582">CC003</span></span></td>
<td><span data-ttu-id="fd9ff-583">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-583">Assembly</span></span></td>
<td><span data-ttu-id="fd9ff-584">65</span><span class="sxs-lookup"><span data-stu-id="fd9ff-584">65</span></span></td>
<td><span data-ttu-id="fd9ff-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="fd9ff-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="fd9ff-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="fd9ff-586">5,297.69</span></span></td>
<td><span data-ttu-id="fd9ff-587">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-588">CC004</span><span class="sxs-lookup"><span data-stu-id="fd9ff-588">CC004</span></span></td>
<td><span data-ttu-id="fd9ff-589">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-589">Packaging</span></span></td>
<td><span data-ttu-id="fd9ff-590">35</span><span class="sxs-lookup"><span data-stu-id="fd9ff-590">35</span></span></td>
<td><span data-ttu-id="fd9ff-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="fd9ff-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="fd9ff-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="fd9ff-592">2,852.60</span></span></td>
<td><span data-ttu-id="fd9ff-593">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fd9ff-594">La tabla siguiente muestra el resultado cuando se aplican los servicios de Asamblea como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="fd9ff-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fd9ff-595">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-595">Cost object</span></span></th>
<th><span data-ttu-id="fd9ff-596">Magnitud</span><span class="sxs-lookup"><span data-stu-id="fd9ff-596">Magnitude</span></span></th>
<th><span data-ttu-id="fd9ff-597">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="fd9ff-597">Allocation factor</span></span></th>
<th><span data-ttu-id="fd9ff-598">Importe</span><span class="sxs-lookup"><span data-stu-id="fd9ff-598">Amount</span></span></th>
<th><span data-ttu-id="fd9ff-599">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="fd9ff-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-600">Prod 1</span></span></td>
<td><span data-ttu-id="fd9ff-601">Producto 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-601">Product 1</span></span></td>
<td><span data-ttu-id="fd9ff-602">60</span><span class="sxs-lookup"><span data-stu-id="fd9ff-602">60</span></span></td>
<td><span data-ttu-id="fd9ff-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="fd9ff-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="fd9ff-604">535.31</span><span class="sxs-lookup"><span data-stu-id="fd9ff-604">535.31</span></span></td>
<td><span data-ttu-id="fd9ff-605">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-606">Prod 2</span></span></td>
<td><span data-ttu-id="fd9ff-607">Producto 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-607">Product 2</span></span></td>
<td><span data-ttu-id="fd9ff-608">20</span><span class="sxs-lookup"><span data-stu-id="fd9ff-608">20</span></span></td>
<td><span data-ttu-id="fd9ff-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="fd9ff-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="fd9ff-610">178.44</span><span class="sxs-lookup"><span data-stu-id="fd9ff-610">178.44</span></span></td>
<td><span data-ttu-id="fd9ff-611">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-612">Prod 1</span></span></td>
<td><span data-ttu-id="fd9ff-613">Producto 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-613">Product 1</span></span></td>
<td><span data-ttu-id="fd9ff-614">60</span><span class="sxs-lookup"><span data-stu-id="fd9ff-614">60</span></span></td>
<td><span data-ttu-id="fd9ff-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="fd9ff-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="fd9ff-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="fd9ff-616">4,487.12</span></span></td>
<td><span data-ttu-id="fd9ff-617">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-618">Prod 2</span></span></td>
<td><span data-ttu-id="fd9ff-619">Producto 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-619">Product 2</span></span></td>
<td><span data-ttu-id="fd9ff-620">20</span><span class="sxs-lookup"><span data-stu-id="fd9ff-620">20</span></span></td>
<td><span data-ttu-id="fd9ff-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="fd9ff-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="fd9ff-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="fd9ff-622">1,495.71</span></span></td>
<td><span data-ttu-id="fd9ff-623">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fd9ff-624">La tabla siguiente muestra el resultado cuando se aplican los servicios de Embalaje como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="fd9ff-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fd9ff-625">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-625">Cost object</span></span></th>
<th><span data-ttu-id="fd9ff-626">Magnitud</span><span class="sxs-lookup"><span data-stu-id="fd9ff-626">Magnitude</span></span></th>
<th><span data-ttu-id="fd9ff-627">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="fd9ff-627">Allocation factor</span></span></th>
<th><span data-ttu-id="fd9ff-628">Importe</span><span class="sxs-lookup"><span data-stu-id="fd9ff-628">Amount</span></span></th>
<th><span data-ttu-id="fd9ff-629">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="fd9ff-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-630">Prod 1</span></span></td>
<td><span data-ttu-id="fd9ff-631">Producto 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-631">Product 1</span></span></td>
<td><span data-ttu-id="fd9ff-632">80</span><span class="sxs-lookup"><span data-stu-id="fd9ff-632">80</span></span></td>
<td><span data-ttu-id="fd9ff-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="fd9ff-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="fd9ff-634">241.05</span><span class="sxs-lookup"><span data-stu-id="fd9ff-634">241.05</span></span></td>
<td><span data-ttu-id="fd9ff-635">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-636">Prod 2</span></span></td>
<td><span data-ttu-id="fd9ff-637">Producto 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-637">Product 2</span></span></td>
<td><span data-ttu-id="fd9ff-638">15</span><span class="sxs-lookup"><span data-stu-id="fd9ff-638">15</span></span></td>
<td><span data-ttu-id="fd9ff-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="fd9ff-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="fd9ff-640">45.20</span><span class="sxs-lookup"><span data-stu-id="fd9ff-640">45.20</span></span></td>
<td><span data-ttu-id="fd9ff-641">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-642">Prod 1</span></span></td>
<td><span data-ttu-id="fd9ff-643">Producto 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-643">Product 1</span></span></td>
<td><span data-ttu-id="fd9ff-644">80</span><span class="sxs-lookup"><span data-stu-id="fd9ff-644">80</span></span></td>
<td><span data-ttu-id="fd9ff-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="fd9ff-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="fd9ff-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="fd9ff-646">2,507.09</span></span></td>
<td><span data-ttu-id="fd9ff-647">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-648">Prod 2</span></span></td>
<td><span data-ttu-id="fd9ff-649">Producto 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-649">Product 2</span></span></td>
<td><span data-ttu-id="fd9ff-650">15</span><span class="sxs-lookup"><span data-stu-id="fd9ff-650">15</span></span></td>
<td><span data-ttu-id="fd9ff-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="fd9ff-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="fd9ff-652">470.08</span><span class="sxs-lookup"><span data-stu-id="fd9ff-652">470.08</span></span></td>
<td><span data-ttu-id="fd9ff-653">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="fd9ff-654">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="fd9ff-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fd9ff-655">Diario</span><span class="sxs-lookup"><span data-stu-id="fd9ff-655">Journal</span></span></th>
<th><span data-ttu-id="fd9ff-656">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="fd9ff-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="fd9ff-657">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="fd9ff-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="fd9ff-658">Versión</span><span class="sxs-lookup"><span data-stu-id="fd9ff-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-659">00004</span><span class="sxs-lookup"><span data-stu-id="fd9ff-659">00004</span></span></td>
<td><span data-ttu-id="fd9ff-660">Diario de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="fd9ff-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="fd9ff-661">Fiscal</span><span class="sxs-lookup"><span data-stu-id="fd9ff-661">Fiscal</span></span></td>
<td><span data-ttu-id="fd9ff-662">2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-662">2017</span></span></td>
<td><span data-ttu-id="fd9ff-663">Período 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-663">Period 1</span></span></td>
<td><span data-ttu-id="fd9ff-664">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="fd9ff-665">Líneas de diario</span><span class="sxs-lookup"><span data-stu-id="fd9ff-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="fd9ff-666">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="fd9ff-667">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="fd9ff-668">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-668">Cost element</span></span></th>
<th><span data-ttu-id="fd9ff-669">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="fd9ff-669">Cost behavior</span></span></th>
<th><span data-ttu-id="fd9ff-670">Importe</span><span class="sxs-lookup"><span data-stu-id="fd9ff-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-671">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="fd9ff-672">CC001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-672">CC001</span></span></td>
<td><span data-ttu-id="fd9ff-673">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-673">HR</span></span></td>
<td><span data-ttu-id="fd9ff-674">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-674">10001</span></span></td>
<td><span data-ttu-id="fd9ff-675">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-675">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-676">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-676">Fixed cost</span></span></td>
<td><span data-ttu-id="fd9ff-677">500,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-678">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="fd9ff-679">CC001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-679">CC001</span></span></td>
<td><span data-ttu-id="fd9ff-680">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-680">HR</span></span></td>
<td><span data-ttu-id="fd9ff-681">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-681">10001</span></span></td>
<td><span data-ttu-id="fd9ff-682">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-682">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-683">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-683">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="fd9ff-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-685">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="fd9ff-686">CC002</span><span class="sxs-lookup"><span data-stu-id="fd9ff-686">CC002</span></span></td>
<td><span data-ttu-id="fd9ff-687">Finanzas</span><span class="sxs-lookup"><span data-stu-id="fd9ff-687">Finance</span></span></td>
<td><span data-ttu-id="fd9ff-688">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-688">10001</span></span></td>
<td><span data-ttu-id="fd9ff-689">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-689">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-690">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-690">Fixed cost</span></span></td>
<td><span data-ttu-id="fd9ff-691">675.00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-692">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="fd9ff-693">CC002</span><span class="sxs-lookup"><span data-stu-id="fd9ff-693">CC002</span></span></td>
<td><span data-ttu-id="fd9ff-694">Finanzas</span><span class="sxs-lookup"><span data-stu-id="fd9ff-694">Finance</span></span></td>
<td><span data-ttu-id="fd9ff-695">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-695">10001</span></span></td>
<td><span data-ttu-id="fd9ff-696">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-696">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-697">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-697">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="fd9ff-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-699">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="fd9ff-700">CC003</span><span class="sxs-lookup"><span data-stu-id="fd9ff-700">CC003</span></span></td>
<td><span data-ttu-id="fd9ff-701">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-701">Assembly</span></span></td>
<td><span data-ttu-id="fd9ff-702">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-702">10001</span></span></td>
<td><span data-ttu-id="fd9ff-703">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-703">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-704">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-704">Fixed cost</span></span></td>
<td><span data-ttu-id="fd9ff-705">713.75</span><span class="sxs-lookup"><span data-stu-id="fd9ff-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-706">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="fd9ff-707">CC003</span><span class="sxs-lookup"><span data-stu-id="fd9ff-707">CC003</span></span></td>
<td><span data-ttu-id="fd9ff-708">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-708">Assembly</span></span></td>
<td><span data-ttu-id="fd9ff-709">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-709">10001</span></span></td>
<td><span data-ttu-id="fd9ff-710">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-710">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-711">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-711">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="fd9ff-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-713">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="fd9ff-714">CC003</span><span class="sxs-lookup"><span data-stu-id="fd9ff-714">CC003</span></span></td>
<td><span data-ttu-id="fd9ff-715">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-715">Packaging</span></span></td>
<td><span data-ttu-id="fd9ff-716">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-716">10001</span></span></td>
<td><span data-ttu-id="fd9ff-717">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-717">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-718">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-718">Fixed cost</span></span></td>
<td><span data-ttu-id="fd9ff-719">286.25</span><span class="sxs-lookup"><span data-stu-id="fd9ff-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-720">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="fd9ff-721">CC003</span><span class="sxs-lookup"><span data-stu-id="fd9ff-721">CC003</span></span></td>
<td><span data-ttu-id="fd9ff-722">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-722">Packaging</span></span></td>
<td><span data-ttu-id="fd9ff-723">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-723">10001</span></span></td>
<td><span data-ttu-id="fd9ff-724">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-724">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-725">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-725">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="fd9ff-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-727">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="fd9ff-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-728">Prod 1</span></span></td>
<td><span data-ttu-id="fd9ff-729">Producto 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-729">Product 1</span></span></td>
<td><span data-ttu-id="fd9ff-730">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-730">10001</span></span></td>
<td><span data-ttu-id="fd9ff-731">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-731">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-732">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-732">Fixed cost</span></span></td>
<td><span data-ttu-id="fd9ff-733">776.36</span><span class="sxs-lookup"><span data-stu-id="fd9ff-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-734">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="fd9ff-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-735">Prod 1</span></span></td>
<td><span data-ttu-id="fd9ff-736">Producto 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-736">Product 1</span></span></td>
<td><span data-ttu-id="fd9ff-737">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-737">10001</span></span></td>
<td><span data-ttu-id="fd9ff-738">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-738">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-739">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-739">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="fd9ff-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-741">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="fd9ff-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-742">Prod 2</span></span></td>
<td><span data-ttu-id="fd9ff-743">Producto 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-743">Product 1</span></span></td>
<td><span data-ttu-id="fd9ff-744">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-744">10001</span></span></td>
<td><span data-ttu-id="fd9ff-745">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-745">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-746">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-746">Fixed cost</span></span></td>
<td><span data-ttu-id="fd9ff-747">223.64</span><span class="sxs-lookup"><span data-stu-id="fd9ff-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-748">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="fd9ff-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-749">Prod 2</span></span></td>
<td><span data-ttu-id="fd9ff-750">Producto 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-750">Product 1</span></span></td>
<td><span data-ttu-id="fd9ff-751">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-751">10001</span></span></td>
<td><span data-ttu-id="fd9ff-752">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-752">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-753">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-753">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="fd9ff-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="fd9ff-755">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="fd9ff-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="fd9ff-756">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="fd9ff-757">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-757">Cost element</span></span></th>
<th><span data-ttu-id="fd9ff-758">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="fd9ff-758">Cost behavior</span></span></th>
<th><span data-ttu-id="fd9ff-759">Importe</span><span class="sxs-lookup"><span data-stu-id="fd9ff-759">Amount</span></span></th>
<th><span data-ttu-id="fd9ff-760">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="fd9ff-761">CC001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-761">CC001</span></span></td>
<td><span data-ttu-id="fd9ff-762">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-762">HR</span></span></td>
<td><span data-ttu-id="fd9ff-763">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-763">10001</span></span></td>
<td><span data-ttu-id="fd9ff-764">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-764">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-765">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-765">Fixed cost</span></span></td>
<td><span data-ttu-id="fd9ff-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-766">-500.00</span></span></td>
<td><span data-ttu-id="fd9ff-767">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-768">CC002</span><span class="sxs-lookup"><span data-stu-id="fd9ff-768">CC002</span></span></td>
<td><span data-ttu-id="fd9ff-769">Finanzas</span><span class="sxs-lookup"><span data-stu-id="fd9ff-769">Finance</span></span></td>
<td><span data-ttu-id="fd9ff-770">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-770">10001</span></span></td>
<td><span data-ttu-id="fd9ff-771">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-771">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-772">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-772">Fixed cost</span></span></td>
<td><span data-ttu-id="fd9ff-773">175.00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-773">175.00</span></span></td>
<td><span data-ttu-id="fd9ff-774">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-775">CC003</span><span class="sxs-lookup"><span data-stu-id="fd9ff-775">CC003</span></span></td>
<td><span data-ttu-id="fd9ff-776">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-776">Assembly</span></span></td>
<td><span data-ttu-id="fd9ff-777">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-777">10001</span></span></td>
<td><span data-ttu-id="fd9ff-778">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-778">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-779">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-779">Fixed cost</span></span></td>
<td><span data-ttu-id="fd9ff-780">275.00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-780">275.00</span></span></td>
<td><span data-ttu-id="fd9ff-781">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-782">CC004</span><span class="sxs-lookup"><span data-stu-id="fd9ff-782">CC004</span></span></td>
<td><span data-ttu-id="fd9ff-783">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-783">Packaging</span></span></td>
<td><span data-ttu-id="fd9ff-784">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-784">10001</span></span></td>
<td><span data-ttu-id="fd9ff-785">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-785">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-786">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-786">Fixed cost</span></span></td>
<td><span data-ttu-id="fd9ff-787">50,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-787">50,00</span></span></td>
<td><span data-ttu-id="fd9ff-788">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-789">CC001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-789">CC001</span></span></td>
<td><span data-ttu-id="fd9ff-790">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-790">HR</span></span></td>
<td><span data-ttu-id="fd9ff-791">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-791">10001</span></span></td>
<td><span data-ttu-id="fd9ff-792">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-792">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-793">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-793">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="fd9ff-794">-1,245.71</span></span></td>
<td><span data-ttu-id="fd9ff-795">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-796">CC002</span><span class="sxs-lookup"><span data-stu-id="fd9ff-796">CC002</span></span></td>
<td><span data-ttu-id="fd9ff-797">Finanzas</span><span class="sxs-lookup"><span data-stu-id="fd9ff-797">Finance</span></span></td>
<td><span data-ttu-id="fd9ff-798">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-798">10001</span></span></td>
<td><span data-ttu-id="fd9ff-799">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-799">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-800">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-800">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-801">436.00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-801">436.00</span></span></td>
<td><span data-ttu-id="fd9ff-802">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-803">CC003</span><span class="sxs-lookup"><span data-stu-id="fd9ff-803">CC003</span></span></td>
<td><span data-ttu-id="fd9ff-804">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-804">Assembly</span></span></td>
<td><span data-ttu-id="fd9ff-805">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-805">10001</span></span></td>
<td><span data-ttu-id="fd9ff-806">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-806">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-807">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-807">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-808">685.14</span><span class="sxs-lookup"><span data-stu-id="fd9ff-808">685.14</span></span></td>
<td><span data-ttu-id="fd9ff-809">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-810">CC004</span><span class="sxs-lookup"><span data-stu-id="fd9ff-810">CC004</span></span></td>
<td><span data-ttu-id="fd9ff-811">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-811">Packaging</span></span></td>
<td><span data-ttu-id="fd9ff-812">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-812">10001</span></span></td>
<td><span data-ttu-id="fd9ff-813">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-813">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-814">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-814">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-815">124.57</span><span class="sxs-lookup"><span data-stu-id="fd9ff-815">124.57</span></span></td>
<td><span data-ttu-id="fd9ff-816">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-817">CC002</span><span class="sxs-lookup"><span data-stu-id="fd9ff-817">CC002</span></span></td>
<td><span data-ttu-id="fd9ff-818">Finanzas</span><span class="sxs-lookup"><span data-stu-id="fd9ff-818">Finance</span></span></td>
<td><span data-ttu-id="fd9ff-819">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-819">10001</span></span></td>
<td><span data-ttu-id="fd9ff-820">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-820">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-821">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-821">Fixed cost</span></span></td>
<td><span data-ttu-id="fd9ff-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-822">-675.00</span></span></td>
<td><span data-ttu-id="fd9ff-823">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-824">CC003</span><span class="sxs-lookup"><span data-stu-id="fd9ff-824">CC003</span></span></td>
<td><span data-ttu-id="fd9ff-825">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-825">Assembly</span></span></td>
<td><span data-ttu-id="fd9ff-826">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-826">10001</span></span></td>
<td><span data-ttu-id="fd9ff-827">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-827">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-828">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-828">Fixed cost</span></span></td>
<td><span data-ttu-id="fd9ff-829">438.75</span><span class="sxs-lookup"><span data-stu-id="fd9ff-829">438.75</span></span></td>
<td><span data-ttu-id="fd9ff-830">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-831">CC004</span><span class="sxs-lookup"><span data-stu-id="fd9ff-831">CC004</span></span></td>
<td><span data-ttu-id="fd9ff-832">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-832">Packaging</span></span></td>
<td><span data-ttu-id="fd9ff-833">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-833">10001</span></span></td>
<td><span data-ttu-id="fd9ff-834">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-834">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-835">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-835">Fixed cost</span></span></td>
<td><span data-ttu-id="fd9ff-836">236.25</span><span class="sxs-lookup"><span data-stu-id="fd9ff-836">236.25</span></span></td>
<td><span data-ttu-id="fd9ff-837">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-838">CC002</span><span class="sxs-lookup"><span data-stu-id="fd9ff-838">CC002</span></span></td>
<td><span data-ttu-id="fd9ff-839">Finanzas</span><span class="sxs-lookup"><span data-stu-id="fd9ff-839">Finance</span></span></td>
<td><span data-ttu-id="fd9ff-840">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-840">10001</span></span></td>
<td><span data-ttu-id="fd9ff-841">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-841">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-842">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-842">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="fd9ff-843">-8,150.29</span></span></td>
<td><span data-ttu-id="fd9ff-844">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-845">CC003</span><span class="sxs-lookup"><span data-stu-id="fd9ff-845">CC003</span></span></td>
<td><span data-ttu-id="fd9ff-846">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-846">Assembly</span></span></td>
<td><span data-ttu-id="fd9ff-847">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-847">10001</span></span></td>
<td><span data-ttu-id="fd9ff-848">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-848">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-849">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-849">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="fd9ff-850">5,297.69</span></span></td>
<td><span data-ttu-id="fd9ff-851">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-852">CC004</span><span class="sxs-lookup"><span data-stu-id="fd9ff-852">CC004</span></span></td>
<td><span data-ttu-id="fd9ff-853">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-853">Packaging</span></span></td>
<td><span data-ttu-id="fd9ff-854">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-854">10001</span></span></td>
<td><span data-ttu-id="fd9ff-855">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-855">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-856">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-856">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="fd9ff-857">2,852.60</span></span></td>
<td><span data-ttu-id="fd9ff-858">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-859">CC003</span><span class="sxs-lookup"><span data-stu-id="fd9ff-859">CC003</span></span></td>
<td><span data-ttu-id="fd9ff-860">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-860">Assembly</span></span></td>
<td><span data-ttu-id="fd9ff-861">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-861">10001</span></span></td>
<td><span data-ttu-id="fd9ff-862">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-862">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-863">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-863">Fixed cost</span></span></td>
<td><span data-ttu-id="fd9ff-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="fd9ff-864">-713.75</span></span></td>
<td><span data-ttu-id="fd9ff-865">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-866">Prod 1</span></span></td>
<td><span data-ttu-id="fd9ff-867">Producto 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-867">Product 1</span></span></td>
<td><span data-ttu-id="fd9ff-868">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-868">10001</span></span></td>
<td><span data-ttu-id="fd9ff-869">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-869">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-870">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-870">Fixed cost</span></span></td>
<td><span data-ttu-id="fd9ff-871">535.31</span><span class="sxs-lookup"><span data-stu-id="fd9ff-871">535.31</span></span></td>
<td><span data-ttu-id="fd9ff-872">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-873">Prod 2</span></span></td>
<td><span data-ttu-id="fd9ff-874">Producto 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-874">Product 2</span></span></td>
<td><span data-ttu-id="fd9ff-875">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-875">10001</span></span></td>
<td><span data-ttu-id="fd9ff-876">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-876">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-877">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-877">Fixed cost</span></span></td>
<td><span data-ttu-id="fd9ff-878">178.44</span><span class="sxs-lookup"><span data-stu-id="fd9ff-878">178.44</span></span></td>
<td><span data-ttu-id="fd9ff-879">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-880">CC003</span><span class="sxs-lookup"><span data-stu-id="fd9ff-880">CC003</span></span></td>
<td><span data-ttu-id="fd9ff-881">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-881">Assembly</span></span></td>
<td><span data-ttu-id="fd9ff-882">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-882">10001</span></span></td>
<td><span data-ttu-id="fd9ff-883">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-883">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-884">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-884">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="fd9ff-885">-5,982.83</span></span></td>
<td><span data-ttu-id="fd9ff-886">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-887">Prod 1</span></span></td>
<td><span data-ttu-id="fd9ff-888">Producto 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-888">Product 1</span></span></td>
<td><span data-ttu-id="fd9ff-889">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-889">10001</span></span></td>
<td><span data-ttu-id="fd9ff-890">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-890">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-891">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-891">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="fd9ff-892">4,487.12</span></span></td>
<td><span data-ttu-id="fd9ff-893">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-894">Prod 2</span></span></td>
<td><span data-ttu-id="fd9ff-895">Producto 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-895">Product 2</span></span></td>
<td><span data-ttu-id="fd9ff-896">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-896">10001</span></span></td>
<td><span data-ttu-id="fd9ff-897">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-897">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-898">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-898">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="fd9ff-899">1,495.71</span></span></td>
<td><span data-ttu-id="fd9ff-900">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-901">CC003</span><span class="sxs-lookup"><span data-stu-id="fd9ff-901">CC003</span></span></td>
<td><span data-ttu-id="fd9ff-902">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-902">Assembly</span></span></td>
<td><span data-ttu-id="fd9ff-903">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-903">10001</span></span></td>
<td><span data-ttu-id="fd9ff-904">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-904">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-905">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-905">Fixed cost</span></span></td>
<td><span data-ttu-id="fd9ff-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="fd9ff-906">-286.25</span></span></td>
<td><span data-ttu-id="fd9ff-907">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-908">Prod 1</span></span></td>
<td><span data-ttu-id="fd9ff-909">Producto 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-909">Product 1</span></span></td>
<td><span data-ttu-id="fd9ff-910">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-910">10001</span></span></td>
<td><span data-ttu-id="fd9ff-911">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-911">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-912">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-912">Fixed cost</span></span></td>
<td><span data-ttu-id="fd9ff-913">241.05</span><span class="sxs-lookup"><span data-stu-id="fd9ff-913">241.05</span></span></td>
<td><span data-ttu-id="fd9ff-914">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-915">Prod 2</span></span></td>
<td><span data-ttu-id="fd9ff-916">Producto 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-916">Product 2</span></span></td>
<td><span data-ttu-id="fd9ff-917">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-917">10001</span></span></td>
<td><span data-ttu-id="fd9ff-918">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-918">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-919">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-919">Fixed cost</span></span></td>
<td><span data-ttu-id="fd9ff-920">45.20</span><span class="sxs-lookup"><span data-stu-id="fd9ff-920">45.20</span></span></td>
<td><span data-ttu-id="fd9ff-921">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-922">CC003</span><span class="sxs-lookup"><span data-stu-id="fd9ff-922">CC003</span></span></td>
<td><span data-ttu-id="fd9ff-923">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="fd9ff-923">Assembly</span></span></td>
<td><span data-ttu-id="fd9ff-924">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-924">10001</span></span></td>
<td><span data-ttu-id="fd9ff-925">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-925">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-926">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-926">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="fd9ff-927">-2,977.17</span></span></td>
<td><span data-ttu-id="fd9ff-928">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-929">Prod 1</span></span></td>
<td><span data-ttu-id="fd9ff-930">Producto 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-930">Product 1</span></span></td>
<td><span data-ttu-id="fd9ff-931">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-931">10001</span></span></td>
<td><span data-ttu-id="fd9ff-932">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-932">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-933">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-933">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="fd9ff-934">2,507.09</span></span></td>
<td><span data-ttu-id="fd9ff-935">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="fd9ff-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-936">Prod 2</span></span></td>
<td><span data-ttu-id="fd9ff-937">Producto 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-937">Product 2</span></span></td>
<td><span data-ttu-id="fd9ff-938">10001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-938">10001</span></span></td>
<td><span data-ttu-id="fd9ff-939">Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-939">Electricity</span></span></td>
<td><span data-ttu-id="fd9ff-940">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-940">Variable cost</span></span></td>
<td><span data-ttu-id="fd9ff-941">470.08</span><span class="sxs-lookup"><span data-stu-id="fd9ff-941">470.08</span></span></td>
<td><span data-ttu-id="fd9ff-942">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="fd9ff-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="fd9ff-943">Conclusión</span><span class="sxs-lookup"><span data-stu-id="fd9ff-943">Conclusion</span></span>
<span data-ttu-id="fd9ff-944">En la contabilidad financiera, un coste de 10.000,00 para electricidad se envía a un identificador ficticio de centro de coste.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="fd9ff-945">Por lo tanto, los contables de coste sabrán que este coste se debe asignar.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="fd9ff-946">En contabilidad de costes, los costes fluyen en las unidades organizativas y los niveles en función de las directivas y las reglas que se aplican.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="fd9ff-947">Cada coste se ha asociado con una base de asignación que proporciona la mejor evaluación para la asignación de costes.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="fd9ff-948">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="fd9ff-949">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="fd9ff-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="fd9ff-950">Total</span><span class="sxs-lookup"><span data-stu-id="fd9ff-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="fd9ff-951">CC099</span><span class="sxs-lookup"><span data-stu-id="fd9ff-951">CC099</span></span></th>
<th><span data-ttu-id="fd9ff-952">CC001</span><span class="sxs-lookup"><span data-stu-id="fd9ff-952">CC001</span></span></th>
<th><span data-ttu-id="fd9ff-953">CC002</span><span class="sxs-lookup"><span data-stu-id="fd9ff-953">CC002</span></span></th>
<th><span data-ttu-id="fd9ff-954">CC003</span><span class="sxs-lookup"><span data-stu-id="fd9ff-954">CC003</span></span></th>
<th><span data-ttu-id="fd9ff-955">CC004</span><span class="sxs-lookup"><span data-stu-id="fd9ff-955">CC004</span></span></th>
<th><span data-ttu-id="fd9ff-956">Proy 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-956">Proj 1</span></span></th>
<th><span data-ttu-id="fd9ff-957">Proy 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-957">Proj 2</span></span></th>
<th><span data-ttu-id="fd9ff-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="fd9ff-958">Prod 1</span></span></th>
<th><span data-ttu-id="fd9ff-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="fd9ff-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="fd9ff-960">10001 Electricidad</span><span class="sxs-lookup"><span data-stu-id="fd9ff-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="fd9ff-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="fd9ff-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="fd9ff-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="fd9ff-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="fd9ff-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="fd9ff-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="fd9ff-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="fd9ff-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="fd9ff-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="fd9ff-970">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="fd9ff-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-971">0,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="fd9ff-972">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="fd9ff-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-973">0,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-974">0,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-975">0,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-976">0,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-977">0,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-978">776.36</span><span class="sxs-lookup"><span data-stu-id="fd9ff-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-979">223.64</span><span class="sxs-lookup"><span data-stu-id="fd9ff-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="fd9ff-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="fd9ff-981">Coste variable</span><span class="sxs-lookup"><span data-stu-id="fd9ff-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-982">000</span><span class="sxs-lookup"><span data-stu-id="fd9ff-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-983">0,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-984">0,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-985">0,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-986">0,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-987">30,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-988">10,00</span><span class="sxs-lookup"><span data-stu-id="fd9ff-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="fd9ff-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="fd9ff-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="fd9ff-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="fd9ff-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="fd9ff-992">Este tema muestra cómo un artículo de costes principales, 10001 Electricidad, fluye por los objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="fd9ff-993">Por tanto, estos gastos generales se asignan al nivel más bajo de la organización.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="fd9ff-994">Es decir, los objetos de coste del nivel más bajo son los que soportan el coste.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="fd9ff-995">Si necesita un flujo visual del coste entre los objetos de coste, puede usar las reglas de directivas de acumulación de costes para visualizar el flujo del coste.</span><span class="sxs-lookup"><span data-stu-id="fd9ff-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="fd9ff-996">Para obtener más información, consulte [Acumulación de costes](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="fd9ff-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>



