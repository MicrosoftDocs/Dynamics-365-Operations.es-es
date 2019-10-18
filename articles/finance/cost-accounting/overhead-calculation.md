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
ms.openlocfilehash: 6c045f82f3288dba193721dd80c90e68750af9a7
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179793"
---
# <a name="overhead-calculation"></a><span data-ttu-id="230e2-103">Cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="230e2-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="230e2-104">Este tema describe los procesos típicos para calcular y asignar costes generales.</span><span class="sxs-lookup"><span data-stu-id="230e2-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="230e2-105">Definición del término</span><span class="sxs-lookup"><span data-stu-id="230e2-105">Term definition</span></span>
---------------

<span data-ttu-id="230e2-106">Los costes generales son costes que se contraen para dirigir un negocio, pero que no pueden ser atribuidos directamente a ninguna actividad empresarial, productos, o servicio específicos.</span><span class="sxs-lookup"><span data-stu-id="230e2-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="230e2-107">Los costes generales proporcionan un soporte fundamental a la generación de actividades rentables.</span><span class="sxs-lookup"><span data-stu-id="230e2-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="230e2-108">Algunos ejemplos de costes generales son:</span><span class="sxs-lookup"><span data-stu-id="230e2-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="230e2-109">Alquiler</span><span class="sxs-lookup"><span data-stu-id="230e2-109">Rent</span></span>
-   <span data-ttu-id="230e2-110">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-110">Electricity</span></span>
-   <span data-ttu-id="230e2-111">Sueldos administrativos</span><span class="sxs-lookup"><span data-stu-id="230e2-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="230e2-112">Visión general del cálculo de costes generales</span><span class="sxs-lookup"><span data-stu-id="230e2-112">Overhead calculation overview</span></span>
<span data-ttu-id="230e2-113">El cálculo de costes generales ejecuta las directivas de contabilidad de costes en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="230e2-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="230e2-114">Puede calcular varias veces los costes generales del mismo período fiscal si se han cambiado las directivas de contabilidad de costes o se han detectado errores específicos.</span><span class="sxs-lookup"><span data-stu-id="230e2-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="230e2-115">Cada ejecución del cálculo de costes generales se almacena y recibe un identificador de versión único que permite comparar los cálculos de diferentes versiones.</span><span class="sxs-lookup"><span data-stu-id="230e2-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="230e2-116">Las entradas de costes que el cálculo de costes generales genera reciben una fecha de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="230e2-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="230e2-117">Esta fecha de contabilidad coincide con la fecha final del período fiscal que se usa en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="230e2-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="230e2-118">El identificador de versión único consiste en los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="230e2-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="230e2-119">Tipo de versión</span><span class="sxs-lookup"><span data-stu-id="230e2-119">Version type</span></span>
-   <span data-ttu-id="230e2-120">Fecha y hora</span><span class="sxs-lookup"><span data-stu-id="230e2-120">Date and time</span></span>
-   <span data-ttu-id="230e2-121">Libro mayor de contabilidad de costes</span><span class="sxs-lookup"><span data-stu-id="230e2-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="230e2-122">Ejercicio</span><span class="sxs-lookup"><span data-stu-id="230e2-122">Fiscal year</span></span>
-   <span data-ttu-id="230e2-123">Período fiscal</span><span class="sxs-lookup"><span data-stu-id="230e2-123">Fiscal period</span></span>

<span data-ttu-id="230e2-124">El cálculo de costes generales se ejecuta independientemente de la versión.</span><span class="sxs-lookup"><span data-stu-id="230e2-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="230e2-125">Por lo tanto, puede calcular la versión de presupuesto antes que la versión real.</span><span class="sxs-lookup"><span data-stu-id="230e2-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="230e2-126">El cálculo de costes generales consta de cuatro pasos, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="230e2-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="230e2-127">En cada paso, se crea una cabecera de diario que tiene entradas del diario.</span><span class="sxs-lookup"><span data-stu-id="230e2-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="230e2-128">Esta cabecera de diario guarda los datos de entrada para cada paso de cálculo.</span><span class="sxs-lookup"><span data-stu-id="230e2-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="230e2-129">Las directivas y las reglas se aplican a cada línea de diario, y las entradas de coste se generan como resultado.</span><span class="sxs-lookup"><span data-stu-id="230e2-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="230e2-130">Por tanto, siempre se tiene rastreabilidad completa.</span><span class="sxs-lookup"><span data-stu-id="230e2-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="230e2-131">[![Cálculo de costes generales](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="230e2-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="230e2-132">Calcular y asignar costes generales de electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="230e2-133">En la contabilidad financiera, algunos costes, como la electricidad, se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="230e2-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="230e2-134">Por lo tanto, no se proporciona una visión de gestión detallada para la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="230e2-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="230e2-135">En contabilidad de costes, para proporcionar información de gestión correcta en todas las unidades y niveles organizativos, los costes deben fluir por las unidades organizativas.</span><span class="sxs-lookup"><span data-stu-id="230e2-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="230e2-136">Este flujo se debe basar en cualquier registro preciso de consumo o en una evaluación justa.</span><span class="sxs-lookup"><span data-stu-id="230e2-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="230e2-137">En la contabilidad general, un coste de la electricidad se puede registrar como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="230e2-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="230e2-138">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="230e2-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="230e2-139">Centro de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="230e2-140">Cuenta principal</span><span class="sxs-lookup"><span data-stu-id="230e2-140">Main account</span></span></th>
<th><span data-ttu-id="230e2-141">Importe en la divisa de contabilidad</span><span class="sxs-lookup"><span data-stu-id="230e2-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-142">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="230e2-143">CC099</span><span class="sxs-lookup"><span data-stu-id="230e2-143">CC099</span></span></td>
<td><span data-ttu-id="230e2-144">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="230e2-144">Default cost center</span></span></td>
<td><span data-ttu-id="230e2-145">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-145">10001</span></span></td>
<td><span data-ttu-id="230e2-146">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-146">Electricity</span></span></td>
<td><span data-ttu-id="230e2-147">10.000,00</span><span class="sxs-lookup"><span data-stu-id="230e2-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="230e2-148">Paso 1: Procese el cálculo del comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="230e2-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="230e2-149">De forma predeterminada, cuando las entradas de coste se importan de los datos de origen, reciben la clasificación de comportamiento del coste **Sin ordenar** en la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="230e2-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="230e2-150">Aplicando reglas de directivas de comportamiento de coste, puede reclasificar entradas de coste como **Coste fijo** o **Coste variable**.</span><span class="sxs-lookup"><span data-stu-id="230e2-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="230e2-151">Defina la regla de comportamiento del coste</span><span class="sxs-lookup"><span data-stu-id="230e2-151">Define the cost behavior rule</span></span>

<span data-ttu-id="230e2-152">En algunos casos, parte del coste es una cuota fija, y el coste pendiente se basa en el consumo.</span><span class="sxs-lookup"><span data-stu-id="230e2-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="230e2-153">Las facturas de electricidad coinciden a menudo con esta definición.</span><span class="sxs-lookup"><span data-stu-id="230e2-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="230e2-154">Tras pagar una cuota fija específica, paga el consumo por kilovatio-hora (Kwh).</span><span class="sxs-lookup"><span data-stu-id="230e2-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="230e2-155">Por ejemplo, si la cuota de coste fijo es de 1.000,00, la regla de comportamiento del coste se define como sigue:</span><span class="sxs-lookup"><span data-stu-id="230e2-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="230e2-156">Importe fijo 1.000,00</span><span class="sxs-lookup"><span data-stu-id="230e2-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="230e2-157">0 &lt;= 1.000,00 = Fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="230e2-158">1.000,01 &lt; N = Variable</span><span class="sxs-lookup"><span data-stu-id="230e2-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="230e2-159">Diario</span><span class="sxs-lookup"><span data-stu-id="230e2-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="230e2-160">Diario</span><span class="sxs-lookup"><span data-stu-id="230e2-160">Journal</span></span></th>
<th><span data-ttu-id="230e2-161">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="230e2-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="230e2-162">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="230e2-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="230e2-163">Versión</span><span class="sxs-lookup"><span data-stu-id="230e2-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-164">00001</span><span class="sxs-lookup"><span data-stu-id="230e2-164">00001</span></span></td>
<td><span data-ttu-id="230e2-165">Diario de cálculo de comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="230e2-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="230e2-166">Fiscal</span><span class="sxs-lookup"><span data-stu-id="230e2-166">Fiscal</span></span></td>
<td><span data-ttu-id="230e2-167">2017</span><span class="sxs-lookup"><span data-stu-id="230e2-167">2017</span></span></td>
<td><span data-ttu-id="230e2-168">Período 1</span><span class="sxs-lookup"><span data-stu-id="230e2-168">Period 1</span></span></td>
<td><span data-ttu-id="230e2-169">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="230e2-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="230e2-170">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="230e2-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="230e2-171">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="230e2-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="230e2-172">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="230e2-173">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-173">Cost element</span></span></th>
<th><span data-ttu-id="230e2-174">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="230e2-174">Cost behavior</span></span></th>
<th><span data-ttu-id="230e2-175">Importe</span><span class="sxs-lookup"><span data-stu-id="230e2-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-176">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="230e2-177">CC099</span><span class="sxs-lookup"><span data-stu-id="230e2-177">CC099</span></span></td>
<td><span data-ttu-id="230e2-178">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="230e2-178">Default cost center</span></span></td>
<td><span data-ttu-id="230e2-179">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-179">10001</span></span></td>
<td><span data-ttu-id="230e2-180">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-180">Electricity</span></span></td>
<td><span data-ttu-id="230e2-181">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="230e2-181">Unclassified</span></span></td>
<td><span data-ttu-id="230e2-182">10.000,00</span><span class="sxs-lookup"><span data-stu-id="230e2-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="230e2-183">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="230e2-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="230e2-184">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="230e2-185">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-185">Cost element</span></span></th>
<th><span data-ttu-id="230e2-186">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="230e2-186">Cost behavior</span></span></th>
<th><span data-ttu-id="230e2-187">Importe</span><span class="sxs-lookup"><span data-stu-id="230e2-187">Amount</span></span></th>
<th><span data-ttu-id="230e2-188">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="230e2-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-189">CC099</span><span class="sxs-lookup"><span data-stu-id="230e2-189">CC099</span></span></td>
<td><span data-ttu-id="230e2-190">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="230e2-190">Default cost center</span></span></td>
<td><span data-ttu-id="230e2-191">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-191">10001</span></span></td>
<td><span data-ttu-id="230e2-192">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-192">Electricity</span></span></td>
<td><span data-ttu-id="230e2-193">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="230e2-193">Unclassified</span></span></td>
<td><span data-ttu-id="230e2-194">10.000,00</span><span class="sxs-lookup"><span data-stu-id="230e2-194">10,000.00</span></span></td>
<td><span data-ttu-id="230e2-195">3 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-196">CC099</span><span class="sxs-lookup"><span data-stu-id="230e2-196">CC099</span></span></td>
<td><span data-ttu-id="230e2-197">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="230e2-197">Default cost center</span></span></td>
<td><span data-ttu-id="230e2-198">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-198">10001</span></span></td>
<td><span data-ttu-id="230e2-199">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-199">Electricity</span></span></td>
<td><span data-ttu-id="230e2-200">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="230e2-200">Unclassified</span></span></td>
<td><span data-ttu-id="230e2-201">-10 000,00</span><span class="sxs-lookup"><span data-stu-id="230e2-201">-10,000.00</span></span></td>
<td><span data-ttu-id="230e2-202">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-203">CC099</span><span class="sxs-lookup"><span data-stu-id="230e2-203">CC099</span></span></td>
<td><span data-ttu-id="230e2-204">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="230e2-204">Default cost center</span></span></td>
<td><span data-ttu-id="230e2-205">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-205">10001</span></span></td>
<td><span data-ttu-id="230e2-206">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-206">Electricity</span></span></td>
<td><span data-ttu-id="230e2-207">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-207">Fixed cost</span></span></td>
<td><span data-ttu-id="230e2-208">1.000,00</span><span class="sxs-lookup"><span data-stu-id="230e2-208">1,000.00</span></span></td>
<td><span data-ttu-id="230e2-209">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-210">CC099</span><span class="sxs-lookup"><span data-stu-id="230e2-210">CC099</span></span></td>
<td><span data-ttu-id="230e2-211">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="230e2-211">Default cost center</span></span></td>
<td><span data-ttu-id="230e2-212">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-212">10001</span></span></td>
<td><span data-ttu-id="230e2-213">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-213">Electricity</span></span></td>
<td><span data-ttu-id="230e2-214">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-214">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-215">9.000,00</span><span class="sxs-lookup"><span data-stu-id="230e2-215">9,000.00</span></span></td>
<td><span data-ttu-id="230e2-216">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="230e2-217">Para obtener más información, consulte [Crear y asignar una directiva de comportamiento de costes a una unidad de control de costes](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="230e2-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="230e2-218">Paso 2: Procese el cálculo de distribución de costes</span><span class="sxs-lookup"><span data-stu-id="230e2-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="230e2-219">La distribución de costes se usa para redistribuir costes desde un objeto de coste a uno o más objetos de coste aplicando una base relevante de la asignación.</span><span class="sxs-lookup"><span data-stu-id="230e2-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="230e2-220">La distribución de costes y la asignación de costes difieren en que la distribución de costes siempre se produce en el nivel de elemento de costes principal del coste original.</span><span class="sxs-lookup"><span data-stu-id="230e2-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="230e2-221">Defina la regla de distribución del coste</span><span class="sxs-lookup"><span data-stu-id="230e2-221">Define the cost distribution rule</span></span>

<span data-ttu-id="230e2-222">En la contabilidad financiera, los costes de electricidad se registran como suma total.</span><span class="sxs-lookup"><span data-stu-id="230e2-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="230e2-223">En contabilidad de costes, este método no es suficientemente detallado.</span><span class="sxs-lookup"><span data-stu-id="230e2-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="230e2-224">El coste variable debe distribuirse a los objetos individuales de coste aplicando una base justa.</span><span class="sxs-lookup"><span data-stu-id="230e2-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="230e2-225">La base de asignación más lógica es el consumo de electricidad (Kwh).</span><span class="sxs-lookup"><span data-stu-id="230e2-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="230e2-226">Se crea un miembro de dimensión estadística que se denomina Electricity, y se registra el consumo de electricidad.</span><span class="sxs-lookup"><span data-stu-id="230e2-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="230e2-227">De forma predeterminada, todos los miembros de dimensión estadísticos estarán disponibles como bases de asignación.</span><span class="sxs-lookup"><span data-stu-id="230e2-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="230e2-228">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-228">Cost object</span></span></th>
<th><span data-ttu-id="230e2-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="230e2-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-230">CC001</span><span class="sxs-lookup"><span data-stu-id="230e2-230">CC001</span></span></td>
<td><span data-ttu-id="230e2-231">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="230e2-231">HR</span></span></td>
<td><span data-ttu-id="230e2-232">1.000</span><span class="sxs-lookup"><span data-stu-id="230e2-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-233">CC002</span><span class="sxs-lookup"><span data-stu-id="230e2-233">CC002</span></span></td>
<td><span data-ttu-id="230e2-234">Finanzas</span><span class="sxs-lookup"><span data-stu-id="230e2-234">Finance</span></span></td>
<td><span data-ttu-id="230e2-235">6.000</span><span class="sxs-lookup"><span data-stu-id="230e2-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-236">CC003</span><span class="sxs-lookup"><span data-stu-id="230e2-236">CC003</span></span></td>
<td><span data-ttu-id="230e2-237">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="230e2-237">Assembly</span></span></td>
<td><span data-ttu-id="230e2-238">0</span><span class="sxs-lookup"><span data-stu-id="230e2-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="230e2-239">La tabla siguiente muestra el resultado cuando se aplica el consumo de electricidad como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="230e2-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="230e2-240">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-240">Cost object</span></span></th>
<th><span data-ttu-id="230e2-241">Magnitud</span><span class="sxs-lookup"><span data-stu-id="230e2-241">Magnitude</span></span></th>
<th><span data-ttu-id="230e2-242">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="230e2-242">Allocation factor</span></span></th>
<th><span data-ttu-id="230e2-243">Importe</span><span class="sxs-lookup"><span data-stu-id="230e2-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-244">CC001</span><span class="sxs-lookup"><span data-stu-id="230e2-244">CC001</span></span></td>
<td><span data-ttu-id="230e2-245">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="230e2-245">HR</span></span></td>
<td><span data-ttu-id="230e2-246">1.000</span><span class="sxs-lookup"><span data-stu-id="230e2-246">1,000</span></span></td>
<td><span data-ttu-id="230e2-247">(1.000 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="230e2-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="230e2-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="230e2-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-249">CC002</span><span class="sxs-lookup"><span data-stu-id="230e2-249">CC002</span></span></td>
<td><span data-ttu-id="230e2-250">Finanzas</span><span class="sxs-lookup"><span data-stu-id="230e2-250">Finance</span></span></td>
<td><span data-ttu-id="230e2-251">6.000</span><span class="sxs-lookup"><span data-stu-id="230e2-251">6,000</span></span></td>
<td><span data-ttu-id="230e2-252">(6.000 ÷ 7.000) × 9.000,00</span><span class="sxs-lookup"><span data-stu-id="230e2-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="230e2-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="230e2-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-254">CC003</span><span class="sxs-lookup"><span data-stu-id="230e2-254">CC003</span></span></td>
<td><span data-ttu-id="230e2-255">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="230e2-255">Assembly</span></span></td>
<td><span data-ttu-id="230e2-256">0</span><span class="sxs-lookup"><span data-stu-id="230e2-256">0</span></span></td>
<td><span data-ttu-id="230e2-257">(0 ÷ 7000) × 9000,00</span><span class="sxs-lookup"><span data-stu-id="230e2-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="230e2-258">0,00</span><span class="sxs-lookup"><span data-stu-id="230e2-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="230e2-259">El coste fijo debe distribuirse uniformemente a los objetos individuales de costes que han consumido electricidad.</span><span class="sxs-lookup"><span data-stu-id="230e2-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="230e2-260">Puede obtener este resultado usando el miembro de dimensión estadístico de electricidad en una base de asignación de la fórmula: (Electricidad &gt; 0,00) La tabla siguiente muestra el resultado cuando el consumo de electricidad se aplica como base de asignación para los costes variables.</span><span class="sxs-lookup"><span data-stu-id="230e2-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="230e2-261">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-261">Cost object</span></span></th>
<th><span data-ttu-id="230e2-262">Fórmula</span><span class="sxs-lookup"><span data-stu-id="230e2-262">Formula</span></span></th>
<th><span data-ttu-id="230e2-263">Magnitud</span><span class="sxs-lookup"><span data-stu-id="230e2-263">Magnitude</span></span></th>
<th><span data-ttu-id="230e2-264">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="230e2-264">Allocation factor</span></span></th>
<th><span data-ttu-id="230e2-265">Importe</span><span class="sxs-lookup"><span data-stu-id="230e2-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-266">CC001</span><span class="sxs-lookup"><span data-stu-id="230e2-266">CC001</span></span></td>
<td><span data-ttu-id="230e2-267">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="230e2-267">HR</span></span></td>
<td><span data-ttu-id="230e2-268">(1.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="230e2-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="230e2-269">1</span><span class="sxs-lookup"><span data-stu-id="230e2-269">1</span></span></td>
<td><span data-ttu-id="230e2-270">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="230e2-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="230e2-271">500,00</span><span class="sxs-lookup"><span data-stu-id="230e2-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-272">CC002</span><span class="sxs-lookup"><span data-stu-id="230e2-272">CC002</span></span></td>
<td><span data-ttu-id="230e2-273">Finanzas</span><span class="sxs-lookup"><span data-stu-id="230e2-273">Finance</span></span></td>
<td><span data-ttu-id="230e2-274">(6.000 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="230e2-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="230e2-275">1</span><span class="sxs-lookup"><span data-stu-id="230e2-275">1</span></span></td>
<td><span data-ttu-id="230e2-276">(1 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="230e2-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="230e2-277">500,00</span><span class="sxs-lookup"><span data-stu-id="230e2-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-278">CC003</span><span class="sxs-lookup"><span data-stu-id="230e2-278">CC003</span></span></td>
<td><span data-ttu-id="230e2-279">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="230e2-279">Assembly</span></span></td>
<td><span data-ttu-id="230e2-280">(0 &gt; 0,00)</span><span class="sxs-lookup"><span data-stu-id="230e2-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="230e2-281">0</span><span class="sxs-lookup"><span data-stu-id="230e2-281">0</span></span></td>
<td><span data-ttu-id="230e2-282">(0 ÷ 2) × 1.000,00</span><span class="sxs-lookup"><span data-stu-id="230e2-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="230e2-283">0,00</span><span class="sxs-lookup"><span data-stu-id="230e2-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="230e2-284">Diario</span><span class="sxs-lookup"><span data-stu-id="230e2-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="230e2-285">Diario</span><span class="sxs-lookup"><span data-stu-id="230e2-285">Journal</span></span></th>
<th><span data-ttu-id="230e2-286">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="230e2-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="230e2-287">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="230e2-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="230e2-288">Versión</span><span class="sxs-lookup"><span data-stu-id="230e2-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-289">00002</span><span class="sxs-lookup"><span data-stu-id="230e2-289">00002</span></span></td>
<td><span data-ttu-id="230e2-290">Diario de cálculo de la distribución de costes</span><span class="sxs-lookup"><span data-stu-id="230e2-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="230e2-291">Fiscal</span><span class="sxs-lookup"><span data-stu-id="230e2-291">Fiscal</span></span></td>
<td><span data-ttu-id="230e2-292">2017</span><span class="sxs-lookup"><span data-stu-id="230e2-292">2017</span></span></td>
<td><span data-ttu-id="230e2-293">Período 1</span><span class="sxs-lookup"><span data-stu-id="230e2-293">Period 1</span></span></td>
<td><span data-ttu-id="230e2-294">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="230e2-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="230e2-295">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="230e2-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="230e2-296">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="230e2-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="230e2-297">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="230e2-298">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-298">Cost element</span></span></th>
<th><span data-ttu-id="230e2-299">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="230e2-299">Cost behavior</span></span></th>
<th><span data-ttu-id="230e2-300">Importe</span><span class="sxs-lookup"><span data-stu-id="230e2-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-301">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="230e2-302">CC099</span><span class="sxs-lookup"><span data-stu-id="230e2-302">CC099</span></span></td>
<td><span data-ttu-id="230e2-303">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="230e2-303">Default cost center</span></span></td>
<td><span data-ttu-id="230e2-304">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-304">10001</span></span></td>
<td><span data-ttu-id="230e2-305">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-305">Electricity</span></span></td>
<td><span data-ttu-id="230e2-306">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-306">Fixed cost</span></span></td>
<td><span data-ttu-id="230e2-307">1.000,00</span><span class="sxs-lookup"><span data-stu-id="230e2-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-308">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="230e2-309">CC099</span><span class="sxs-lookup"><span data-stu-id="230e2-309">CC099</span></span></td>
<td><span data-ttu-id="230e2-310">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="230e2-310">Default cost center</span></span></td>
<td><span data-ttu-id="230e2-311">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-311">10001</span></span></td>
<td><span data-ttu-id="230e2-312">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-312">Electricity</span></span></td>
<td><span data-ttu-id="230e2-313">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-313">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-314">9.000,00</span><span class="sxs-lookup"><span data-stu-id="230e2-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="230e2-315">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="230e2-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="230e2-316">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="230e2-317">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-317">Cost element</span></span></th>
<th><span data-ttu-id="230e2-318">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="230e2-318">Cost behavior</span></span></th>
<th><span data-ttu-id="230e2-319">Importe</span><span class="sxs-lookup"><span data-stu-id="230e2-319">Amount</span></span></th>
<th><span data-ttu-id="230e2-320">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="230e2-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-321">CC099</span><span class="sxs-lookup"><span data-stu-id="230e2-321">CC099</span></span></td>
<td><span data-ttu-id="230e2-322">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="230e2-322">Default cost center</span></span></td>
<td><span data-ttu-id="230e2-323">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-323">10001</span></span></td>
<td><span data-ttu-id="230e2-324">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-324">Electricity</span></span></td>
<td><span data-ttu-id="230e2-325">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-325">Fixed cost</span></span></td>
<td><span data-ttu-id="230e2-326">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="230e2-326">-1,000.00</span></span></td>
<td><span data-ttu-id="230e2-327">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-328">CC001</span><span class="sxs-lookup"><span data-stu-id="230e2-328">CC001</span></span></td>
<td><span data-ttu-id="230e2-329">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="230e2-329">HR</span></span></td>
<td><span data-ttu-id="230e2-330">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-330">10001</span></span></td>
<td><span data-ttu-id="230e2-331">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-331">Electricity</span></span></td>
<td><span data-ttu-id="230e2-332">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-332">Fixed cost</span></span></td>
<td><span data-ttu-id="230e2-333">500,00</span><span class="sxs-lookup"><span data-stu-id="230e2-333">500.00</span></span></td>
<td><span data-ttu-id="230e2-334">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-335">CC002</span><span class="sxs-lookup"><span data-stu-id="230e2-335">CC002</span></span></td>
<td><span data-ttu-id="230e2-336">Finanzas</span><span class="sxs-lookup"><span data-stu-id="230e2-336">Finance</span></span></td>
<td><span data-ttu-id="230e2-337">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-337">10001</span></span></td>
<td><span data-ttu-id="230e2-338">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-338">Electricity</span></span></td>
<td><span data-ttu-id="230e2-339">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-339">Fixed cost</span></span></td>
<td><span data-ttu-id="230e2-340">500,00</span><span class="sxs-lookup"><span data-stu-id="230e2-340">500.00</span></span></td>
<td><span data-ttu-id="230e2-341">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-342">CC099</span><span class="sxs-lookup"><span data-stu-id="230e2-342">CC099</span></span></td>
<td><span data-ttu-id="230e2-343">Centro de coste predeterminado</span><span class="sxs-lookup"><span data-stu-id="230e2-343">Default cost center</span></span></td>
<td><span data-ttu-id="230e2-344">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-344">10001</span></span></td>
<td><span data-ttu-id="230e2-345">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-345">Electricity</span></span></td>
<td><span data-ttu-id="230e2-346">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-346">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-347">-9.000,00</span><span class="sxs-lookup"><span data-stu-id="230e2-347">-9,000.00</span></span></td>
<td><span data-ttu-id="230e2-348">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-349">CC001</span><span class="sxs-lookup"><span data-stu-id="230e2-349">CC001</span></span></td>
<td><span data-ttu-id="230e2-350">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="230e2-350">HR</span></span></td>
<td><span data-ttu-id="230e2-351">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-351">10001</span></span></td>
<td><span data-ttu-id="230e2-352">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-352">Electricity</span></span></td>
<td><span data-ttu-id="230e2-353">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-353">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="230e2-354">1,285.71</span></span></td>
<td><span data-ttu-id="230e2-355">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-356">CC002</span><span class="sxs-lookup"><span data-stu-id="230e2-356">CC002</span></span></td>
<td><span data-ttu-id="230e2-357">Finanzas</span><span class="sxs-lookup"><span data-stu-id="230e2-357">Finance</span></span></td>
<td><span data-ttu-id="230e2-358">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-358">10001</span></span></td>
<td><span data-ttu-id="230e2-359">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-359">Electricity</span></span></td>
<td><span data-ttu-id="230e2-360">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-360">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="230e2-361">7,714.29</span></span></td>
<td><span data-ttu-id="230e2-362">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="230e2-363">Para obtener más información, consulte [Crear y asignar una directiva de distribución de costes a una unidad de control de costes](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="230e2-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="230e2-364">Paso 3: Procese el cálculo de las tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="230e2-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="230e2-365">La tasa de costes generales se usa para cargar uno o varios objetos de coste específicos.</span><span class="sxs-lookup"><span data-stu-id="230e2-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="230e2-366">El cargo se basa en un índice de coste predeterminado y la magnitud de la base de asignación asignada.</span><span class="sxs-lookup"><span data-stu-id="230e2-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="230e2-367">Defina la tasa de costes generales</span><span class="sxs-lookup"><span data-stu-id="230e2-367">Define the overhead rate</span></span>

<span data-ttu-id="230e2-368">El objeto de coste CC001 HR contribuye a un conjunto de proyectos internos.</span><span class="sxs-lookup"><span data-stu-id="230e2-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="230e2-369">Se crea un miembro de dimensión estadística que se denomina proyectos HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="230e2-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="230e2-370">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-370">Cost object</span></span></th>
<th><span data-ttu-id="230e2-371">Horas</span><span class="sxs-lookup"><span data-stu-id="230e2-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-372">Proy 1</span><span class="sxs-lookup"><span data-stu-id="230e2-372">Proj 1</span></span></td>
<td><span data-ttu-id="230e2-373">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="230e2-373">Project 1</span></span></td>
<td><span data-ttu-id="230e2-374">3</span><span class="sxs-lookup"><span data-stu-id="230e2-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-375">Proy 2</span><span class="sxs-lookup"><span data-stu-id="230e2-375">Proj 2</span></span></td>
<td><span data-ttu-id="230e2-376">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="230e2-376">Project 2</span></span></td>
<td><span data-ttu-id="230e2-377">1</span><span class="sxs-lookup"><span data-stu-id="230e2-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="230e2-378">Una tasa de coste predeterminada para la contribución de los proyectos de coste se ha definido.</span><span class="sxs-lookup"><span data-stu-id="230e2-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="230e2-379">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-379">Cost object</span></span></th>
<th><span data-ttu-id="230e2-380">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-380">Cost element</span></span></th>
<th><span data-ttu-id="230e2-381">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="230e2-381">Cost behavior</span></span></th>
<th><span data-ttu-id="230e2-382">Unidades</span><span class="sxs-lookup"><span data-stu-id="230e2-382">Units</span></span></th>
<th><span data-ttu-id="230e2-383">Índice</span><span class="sxs-lookup"><span data-stu-id="230e2-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-384">CC001</span><span class="sxs-lookup"><span data-stu-id="230e2-384">CC001</span></span></td>
<td><span data-ttu-id="230e2-385">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="230e2-385">HR</span></span></td>
<td><span data-ttu-id="230e2-386">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-386">10001</span></span></td>
<td><span data-ttu-id="230e2-387">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-387">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-388">1</span><span class="sxs-lookup"><span data-stu-id="230e2-388">1</span></span></td>
<td><span data-ttu-id="230e2-389">10</span><span class="sxs-lookup"><span data-stu-id="230e2-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="230e2-390">La tabla siguiente muestra el resultado cuando los proyectos HR se aplican como base de la asignación.</span><span class="sxs-lookup"><span data-stu-id="230e2-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="230e2-391">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-391">Cost object</span></span></th>
<th><span data-ttu-id="230e2-392">Magnitud</span><span class="sxs-lookup"><span data-stu-id="230e2-392">Magnitude</span></span></th>
<th><span data-ttu-id="230e2-393">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-393">Cost element</span></span></th>
<th><span data-ttu-id="230e2-394">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="230e2-394">Allocation factor</span></span></th>
<th><span data-ttu-id="230e2-395">Importe</span><span class="sxs-lookup"><span data-stu-id="230e2-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-396">Proy 1</span><span class="sxs-lookup"><span data-stu-id="230e2-396">Proj 1</span></span></td>
<td><span data-ttu-id="230e2-397">Proyecto 1</span><span class="sxs-lookup"><span data-stu-id="230e2-397">Project 1</span></span></td>
<td><span data-ttu-id="230e2-398">3</span><span class="sxs-lookup"><span data-stu-id="230e2-398">3</span></span></td>
<td><span data-ttu-id="230e2-399">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-399">10001</span></span></td>
<td><span data-ttu-id="230e2-400">(3 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="230e2-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="230e2-401">30,00</span><span class="sxs-lookup"><span data-stu-id="230e2-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-402">Proy 2</span><span class="sxs-lookup"><span data-stu-id="230e2-402">Proj 2</span></span></td>
<td><span data-ttu-id="230e2-403">Proyecto 2</span><span class="sxs-lookup"><span data-stu-id="230e2-403">Project 2</span></span></td>
<td><span data-ttu-id="230e2-404">1</span><span class="sxs-lookup"><span data-stu-id="230e2-404">1</span></span></td>
<td><span data-ttu-id="230e2-405">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-405">10001</span></span></td>
<td><span data-ttu-id="230e2-406">(1 ÷ 1) × 10,00</span><span class="sxs-lookup"><span data-stu-id="230e2-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="230e2-407">10,00</span><span class="sxs-lookup"><span data-stu-id="230e2-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="230e2-408">Diario</span><span class="sxs-lookup"><span data-stu-id="230e2-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="230e2-409">Diario</span><span class="sxs-lookup"><span data-stu-id="230e2-409">Journal</span></span></th>
<th><span data-ttu-id="230e2-410">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="230e2-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="230e2-411">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="230e2-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="230e2-412">Versión</span><span class="sxs-lookup"><span data-stu-id="230e2-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-413">00003</span><span class="sxs-lookup"><span data-stu-id="230e2-413">00003</span></span></td>
<td><span data-ttu-id="230e2-414">Diario de cálculo de tasas de costes generales</span><span class="sxs-lookup"><span data-stu-id="230e2-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="230e2-415">Fiscal</span><span class="sxs-lookup"><span data-stu-id="230e2-415">Fiscal</span></span></td>
<td><span data-ttu-id="230e2-416">2017</span><span class="sxs-lookup"><span data-stu-id="230e2-416">2017</span></span></td>
<td><span data-ttu-id="230e2-417">Período 1</span><span class="sxs-lookup"><span data-stu-id="230e2-417">Period 1</span></span></td>
<td><span data-ttu-id="230e2-418">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="230e2-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="230e2-419">Entradas de diario (entradas de diario para cálculo de tasas de costes generales)</span><span class="sxs-lookup"><span data-stu-id="230e2-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="230e2-420">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="230e2-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="230e2-421">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-421">Cost object</span></span></th>
<th><span data-ttu-id="230e2-422">Magnitud</span><span class="sxs-lookup"><span data-stu-id="230e2-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-423">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="230e2-424">Proy 1</span><span class="sxs-lookup"><span data-stu-id="230e2-424">Proj 1</span></span></td>
<td><span data-ttu-id="230e2-425">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="230e2-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="230e2-426">3,00</span><span class="sxs-lookup"><span data-stu-id="230e2-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-427">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="230e2-428">Proy 2</span><span class="sxs-lookup"><span data-stu-id="230e2-428">Proj 2</span></span></td>
<td><span data-ttu-id="230e2-429">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="230e2-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="230e2-430">1,00</span><span class="sxs-lookup"><span data-stu-id="230e2-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="230e2-431">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="230e2-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="230e2-432">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="230e2-433">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-433">Cost element</span></span></th>
<th><span data-ttu-id="230e2-434">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="230e2-434">Cost behavior</span></span></th>
<th><span data-ttu-id="230e2-435">Importe</span><span class="sxs-lookup"><span data-stu-id="230e2-435">Amount</span></span></th>
<th><span data-ttu-id="230e2-436">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="230e2-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="230e2-437">CC0001</span></span></td>
<td><span data-ttu-id="230e2-438">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="230e2-438">HR</span></span></td>
<td><span data-ttu-id="230e2-439">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-439">10001</span></span></td>
<td><span data-ttu-id="230e2-440">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-440">Electricity</span></span></td>
<td><span data-ttu-id="230e2-441">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-441">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-442">-30,00</span><span class="sxs-lookup"><span data-stu-id="230e2-442">-30.00</span></span></td>
<td><span data-ttu-id="230e2-443">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-444">Proy 1</span><span class="sxs-lookup"><span data-stu-id="230e2-444">Proj 1</span></span></td>
<td><span data-ttu-id="230e2-445">Proyecto interno 1</span><span class="sxs-lookup"><span data-stu-id="230e2-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="230e2-446">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-446">10001</span></span></td>
<td><span data-ttu-id="230e2-447">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-447">Electricity</span></span></td>
<td><span data-ttu-id="230e2-448">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-448">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-449">30,00</span><span class="sxs-lookup"><span data-stu-id="230e2-449">30.00</span></span></td>
<td><span data-ttu-id="230e2-450">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-451">CC001</span><span class="sxs-lookup"><span data-stu-id="230e2-451">CC001</span></span></td>
<td><span data-ttu-id="230e2-452">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="230e2-452">HR</span></span></td>
<td><span data-ttu-id="230e2-453">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-453">10001</span></span></td>
<td><span data-ttu-id="230e2-454">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-454">Electricity</span></span></td>
<td><span data-ttu-id="230e2-455">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-455">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="230e2-456">-10.00</span></span></td>
<td><span data-ttu-id="230e2-457">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-458">Proy 2</span><span class="sxs-lookup"><span data-stu-id="230e2-458">Proj 2</span></span></td>
<td><span data-ttu-id="230e2-459">Proyecto interno 2</span><span class="sxs-lookup"><span data-stu-id="230e2-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="230e2-460">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-460">10001</span></span></td>
<td><span data-ttu-id="230e2-461">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-461">Electricity</span></span></td>
<td><span data-ttu-id="230e2-462">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-462">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-463">10,00</span><span class="sxs-lookup"><span data-stu-id="230e2-463">10.00</span></span></td>
<td><span data-ttu-id="230e2-464">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="230e2-465">Para obtener más información, consulte [Realizar cálculo de costes generales](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="230e2-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="230e2-466">Paso 4: Procese el cálculo de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="230e2-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="230e2-467">La asignación es utilizada para asignar el saldo de un objeto de coste a otros objetos de coste aplicando una base de asignación.</span><span class="sxs-lookup"><span data-stu-id="230e2-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="230e2-468">Finance admite el método de asignación recíproco.</span><span class="sxs-lookup"><span data-stu-id="230e2-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="230e2-469">En el método de asignación recíproco, se reconocen completamente los servicios mutuos que los objetos de coste auxiliar intercambian.</span><span class="sxs-lookup"><span data-stu-id="230e2-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="230e2-470">El sistema determina automáticamente el orden correcto para realizar las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="230e2-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="230e2-471">El saldo de un objeto de coste se asigna según una única base de asignación.</span><span class="sxs-lookup"><span data-stu-id="230e2-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="230e2-472">Las asignaciones entre dimensiones de objetos de coste y sus miembros respectivos se admiten.</span><span class="sxs-lookup"><span data-stu-id="230e2-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="230e2-473">El orden de asignación se controla por unidad de control de costes.</span><span class="sxs-lookup"><span data-stu-id="230e2-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="230e2-474">[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="230e2-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="230e2-475">Defina la asignación de costes</span><span class="sxs-lookup"><span data-stu-id="230e2-475">Define the cost allocation</span></span>

<span data-ttu-id="230e2-476">A continuación se indica un ejemplo sencillo que explica cómo puede realizar el seguimiento del flujo de coste.</span><span class="sxs-lookup"><span data-stu-id="230e2-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="230e2-477">El objeto de coste CC001 HR contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="230e2-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="230e2-478">Se crea un miembro de dimensión estadística que se denomina servicios HR para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="230e2-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="230e2-479">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-479">Cost object</span></span></th>
<th><span data-ttu-id="230e2-480">Servicios HR</span><span class="sxs-lookup"><span data-stu-id="230e2-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-481">CC002</span><span class="sxs-lookup"><span data-stu-id="230e2-481">CC002</span></span></td>
<td><span data-ttu-id="230e2-482">Finanzas</span><span class="sxs-lookup"><span data-stu-id="230e2-482">Finance</span></span></td>
<td><span data-ttu-id="230e2-483">35</span><span class="sxs-lookup"><span data-stu-id="230e2-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-484">CC003</span><span class="sxs-lookup"><span data-stu-id="230e2-484">CC003</span></span></td>
<td><span data-ttu-id="230e2-485">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="230e2-485">Assembly</span></span></td>
<td><span data-ttu-id="230e2-486">55</span><span class="sxs-lookup"><span data-stu-id="230e2-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-487">CC004</span><span class="sxs-lookup"><span data-stu-id="230e2-487">CC004</span></span></td>
<td><span data-ttu-id="230e2-488">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="230e2-488">Packaging</span></span></td>
<td><span data-ttu-id="230e2-489">10</span><span class="sxs-lookup"><span data-stu-id="230e2-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="230e2-490">El objeto de coste CC002 Finanzas contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="230e2-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="230e2-491">Se crea un miembro de dimensión estadística que se denomina Finanzas para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="230e2-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="230e2-492">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-492">Cost object</span></span></th>
<th><span data-ttu-id="230e2-493">Servicios financieros</span><span class="sxs-lookup"><span data-stu-id="230e2-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-494">CC003</span><span class="sxs-lookup"><span data-stu-id="230e2-494">CC003</span></span></td>
<td><span data-ttu-id="230e2-495">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="230e2-495">Assembly</span></span></td>
<td><span data-ttu-id="230e2-496">65</span><span class="sxs-lookup"><span data-stu-id="230e2-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-497">CC004</span><span class="sxs-lookup"><span data-stu-id="230e2-497">CC004</span></span></td>
<td><span data-ttu-id="230e2-498">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="230e2-498">Packaging</span></span></td>
<td><span data-ttu-id="230e2-499">35</span><span class="sxs-lookup"><span data-stu-id="230e2-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="230e2-500">El objeto de coste CC003 Asamblea contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="230e2-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="230e2-501">Se crea un miembro de dimensión estadística que se denomina servicios de Asamblea para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="230e2-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="230e2-502">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-502">Cost object</span></span></th>
<th><span data-ttu-id="230e2-503">Servicios de la asamblea (horas)</span><span class="sxs-lookup"><span data-stu-id="230e2-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-504">Prod 1</span><span class="sxs-lookup"><span data-stu-id="230e2-504">Prod 1</span></span></td>
<td><span data-ttu-id="230e2-505">Producto 1</span><span class="sxs-lookup"><span data-stu-id="230e2-505">Product 1</span></span></td>
<td><span data-ttu-id="230e2-506">60</span><span class="sxs-lookup"><span data-stu-id="230e2-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-507">Prod 2</span><span class="sxs-lookup"><span data-stu-id="230e2-507">Prod 2</span></span></td>
<td><span data-ttu-id="230e2-508">Producto 2</span><span class="sxs-lookup"><span data-stu-id="230e2-508">Product 2</span></span></td>
<td><span data-ttu-id="230e2-509">20</span><span class="sxs-lookup"><span data-stu-id="230e2-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="230e2-510">El objeto de coste CC004 Embalaje contribuye a varios objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="230e2-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="230e2-511">Se crea un miembro de dimensión estadística que se denomina servicios de Embalaje para medir la magnitud consumida.</span><span class="sxs-lookup"><span data-stu-id="230e2-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="230e2-512">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-512">Cost object</span></span></th>
<th><span data-ttu-id="230e2-513">Servicios de embalaje (horas)</span><span class="sxs-lookup"><span data-stu-id="230e2-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-514">Prod 1</span><span class="sxs-lookup"><span data-stu-id="230e2-514">Prod 1</span></span></td>
<td><span data-ttu-id="230e2-515">Producto 1</span><span class="sxs-lookup"><span data-stu-id="230e2-515">Product 1</span></span></td>
<td><span data-ttu-id="230e2-516">80</span><span class="sxs-lookup"><span data-stu-id="230e2-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-517">Prod 2</span><span class="sxs-lookup"><span data-stu-id="230e2-517">Prod 2</span></span></td>
<td><span data-ttu-id="230e2-518">Producto 2</span><span class="sxs-lookup"><span data-stu-id="230e2-518">Product 2</span></span></td>
<td><span data-ttu-id="230e2-519">15</span><span class="sxs-lookup"><span data-stu-id="230e2-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="230e2-520">Las medidas estadísticas como las horas de la producción que un producto consume se pueden deducir de los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="230e2-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="230e2-521">Para obtener más información, vea [Plantilla de proveedor de medidas estadísticas](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="230e2-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="230e2-522">La tabla siguiente muestra el resultado cuando se aplican los servicios de HR como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="230e2-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="230e2-523">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-523">Cost object</span></span></th>
<th><span data-ttu-id="230e2-524">Magnitud</span><span class="sxs-lookup"><span data-stu-id="230e2-524">Magnitude</span></span></th>
<th><span data-ttu-id="230e2-525">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="230e2-525">Allocation factor</span></span></th>
<th><span data-ttu-id="230e2-526">Importe</span><span class="sxs-lookup"><span data-stu-id="230e2-526">Amount</span></span></th>
<th><span data-ttu-id="230e2-527">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="230e2-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-528">CC002</span><span class="sxs-lookup"><span data-stu-id="230e2-528">CC002</span></span></td>
<td><span data-ttu-id="230e2-529">Finanzas</span><span class="sxs-lookup"><span data-stu-id="230e2-529">Finance</span></span></td>
<td><span data-ttu-id="230e2-530">35</span><span class="sxs-lookup"><span data-stu-id="230e2-530">35</span></span></td>
<td><span data-ttu-id="230e2-531">(35 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="230e2-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="230e2-532">175.00</span><span class="sxs-lookup"><span data-stu-id="230e2-532">175.00</span></span></td>
<td><span data-ttu-id="230e2-533">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-534">CC003</span><span class="sxs-lookup"><span data-stu-id="230e2-534">CC003</span></span></td>
<td><span data-ttu-id="230e2-535">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="230e2-535">Assembly</span></span></td>
<td><span data-ttu-id="230e2-536">55</span><span class="sxs-lookup"><span data-stu-id="230e2-536">55</span></span></td>
<td><span data-ttu-id="230e2-537">(55 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="230e2-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="230e2-538">275.00</span><span class="sxs-lookup"><span data-stu-id="230e2-538">275.00</span></span></td>
<td><span data-ttu-id="230e2-539">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-540">CC004</span><span class="sxs-lookup"><span data-stu-id="230e2-540">CC004</span></span></td>
<td><span data-ttu-id="230e2-541">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="230e2-541">Packaging</span></span></td>
<td><span data-ttu-id="230e2-542">10</span><span class="sxs-lookup"><span data-stu-id="230e2-542">10</span></span></td>
<td><span data-ttu-id="230e2-543">(10 ÷ 100) × 500,00</span><span class="sxs-lookup"><span data-stu-id="230e2-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="230e2-544">50,00</span><span class="sxs-lookup"><span data-stu-id="230e2-544">50.00</span></span></td>
<td><span data-ttu-id="230e2-545">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-546">CC002</span><span class="sxs-lookup"><span data-stu-id="230e2-546">CC002</span></span></td>
<td><span data-ttu-id="230e2-547">Finanzas</span><span class="sxs-lookup"><span data-stu-id="230e2-547">Finance</span></span></td>
<td><span data-ttu-id="230e2-548">35</span><span class="sxs-lookup"><span data-stu-id="230e2-548">35</span></span></td>
<td><span data-ttu-id="230e2-549">(35 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="230e2-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="230e2-550">436.00</span><span class="sxs-lookup"><span data-stu-id="230e2-550">436.00</span></span></td>
<td><span data-ttu-id="230e2-551">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-552">CC003</span><span class="sxs-lookup"><span data-stu-id="230e2-552">CC003</span></span></td>
<td><span data-ttu-id="230e2-553">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="230e2-553">Assembly</span></span></td>
<td><span data-ttu-id="230e2-554">55</span><span class="sxs-lookup"><span data-stu-id="230e2-554">55</span></span></td>
<td><span data-ttu-id="230e2-555">(55 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="230e2-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="230e2-556">685.14</span><span class="sxs-lookup"><span data-stu-id="230e2-556">685.14</span></span></td>
<td><span data-ttu-id="230e2-557">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-558">CC004</span><span class="sxs-lookup"><span data-stu-id="230e2-558">CC004</span></span></td>
<td><span data-ttu-id="230e2-559">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="230e2-559">Packaging</span></span></td>
<td><span data-ttu-id="230e2-560">10</span><span class="sxs-lookup"><span data-stu-id="230e2-560">10</span></span></td>
<td><span data-ttu-id="230e2-561">(10 ÷ 100) × 1.245,71</span><span class="sxs-lookup"><span data-stu-id="230e2-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="230e2-562">124.57</span><span class="sxs-lookup"><span data-stu-id="230e2-562">124.57</span></span></td>
<td><span data-ttu-id="230e2-563">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="230e2-564">La tabla siguiente muestra el resultado cuando se aplican los servicios de Finanzas como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="230e2-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="230e2-565">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-565">Cost object</span></span></th>
<th><span data-ttu-id="230e2-566">Magnitud</span><span class="sxs-lookup"><span data-stu-id="230e2-566">Magnitude</span></span></th>
<th><span data-ttu-id="230e2-567">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="230e2-567">Allocation factor</span></span></th>
<th><span data-ttu-id="230e2-568">Importe</span><span class="sxs-lookup"><span data-stu-id="230e2-568">Amount</span></span></th>
<th><span data-ttu-id="230e2-569">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="230e2-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-570">CC003</span><span class="sxs-lookup"><span data-stu-id="230e2-570">CC003</span></span></td>
<td><span data-ttu-id="230e2-571">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="230e2-571">Assembly</span></span></td>
<td><span data-ttu-id="230e2-572">65</span><span class="sxs-lookup"><span data-stu-id="230e2-572">65</span></span></td>
<td><span data-ttu-id="230e2-573">(65 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="230e2-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="230e2-574">438.75</span><span class="sxs-lookup"><span data-stu-id="230e2-574">438.75</span></span></td>
<td><span data-ttu-id="230e2-575">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-576">CC004</span><span class="sxs-lookup"><span data-stu-id="230e2-576">CC004</span></span></td>
<td><span data-ttu-id="230e2-577">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="230e2-577">Packaging</span></span></td>
<td><span data-ttu-id="230e2-578">35</span><span class="sxs-lookup"><span data-stu-id="230e2-578">35</span></span></td>
<td><span data-ttu-id="230e2-579">(35 ÷ 100) × (500,00 + 175,00)</span><span class="sxs-lookup"><span data-stu-id="230e2-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="230e2-580">236.25</span><span class="sxs-lookup"><span data-stu-id="230e2-580">236.25</span></span></td>
<td><span data-ttu-id="230e2-581">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-582">CC003</span><span class="sxs-lookup"><span data-stu-id="230e2-582">CC003</span></span></td>
<td><span data-ttu-id="230e2-583">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="230e2-583">Assembly</span></span></td>
<td><span data-ttu-id="230e2-584">65</span><span class="sxs-lookup"><span data-stu-id="230e2-584">65</span></span></td>
<td><span data-ttu-id="230e2-585">(65 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="230e2-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="230e2-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="230e2-586">5,297.69</span></span></td>
<td><span data-ttu-id="230e2-587">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-588">CC004</span><span class="sxs-lookup"><span data-stu-id="230e2-588">CC004</span></span></td>
<td><span data-ttu-id="230e2-589">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="230e2-589">Packaging</span></span></td>
<td><span data-ttu-id="230e2-590">35</span><span class="sxs-lookup"><span data-stu-id="230e2-590">35</span></span></td>
<td><span data-ttu-id="230e2-591">(35 ÷ 100) × (7.714,29 + 436,00)</span><span class="sxs-lookup"><span data-stu-id="230e2-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="230e2-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="230e2-592">2,852.60</span></span></td>
<td><span data-ttu-id="230e2-593">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="230e2-594">La tabla siguiente muestra el resultado cuando se aplican los servicios de Asamblea como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="230e2-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="230e2-595">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-595">Cost object</span></span></th>
<th><span data-ttu-id="230e2-596">Magnitud</span><span class="sxs-lookup"><span data-stu-id="230e2-596">Magnitude</span></span></th>
<th><span data-ttu-id="230e2-597">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="230e2-597">Allocation factor</span></span></th>
<th><span data-ttu-id="230e2-598">Importe</span><span class="sxs-lookup"><span data-stu-id="230e2-598">Amount</span></span></th>
<th><span data-ttu-id="230e2-599">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="230e2-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-600">Prod 1</span><span class="sxs-lookup"><span data-stu-id="230e2-600">Prod 1</span></span></td>
<td><span data-ttu-id="230e2-601">Producto 1</span><span class="sxs-lookup"><span data-stu-id="230e2-601">Product 1</span></span></td>
<td><span data-ttu-id="230e2-602">60</span><span class="sxs-lookup"><span data-stu-id="230e2-602">60</span></span></td>
<td><span data-ttu-id="230e2-603">(60 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="230e2-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="230e2-604">535.31</span><span class="sxs-lookup"><span data-stu-id="230e2-604">535.31</span></span></td>
<td><span data-ttu-id="230e2-605">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-606">Prod 2</span><span class="sxs-lookup"><span data-stu-id="230e2-606">Prod 2</span></span></td>
<td><span data-ttu-id="230e2-607">Producto 2</span><span class="sxs-lookup"><span data-stu-id="230e2-607">Product 2</span></span></td>
<td><span data-ttu-id="230e2-608">20</span><span class="sxs-lookup"><span data-stu-id="230e2-608">20</span></span></td>
<td><span data-ttu-id="230e2-609">(20 ÷ 80) × (275,00 + 438,75)</span><span class="sxs-lookup"><span data-stu-id="230e2-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="230e2-610">178.44</span><span class="sxs-lookup"><span data-stu-id="230e2-610">178.44</span></span></td>
<td><span data-ttu-id="230e2-611">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-612">Prod 1</span><span class="sxs-lookup"><span data-stu-id="230e2-612">Prod 1</span></span></td>
<td><span data-ttu-id="230e2-613">Producto 1</span><span class="sxs-lookup"><span data-stu-id="230e2-613">Product 1</span></span></td>
<td><span data-ttu-id="230e2-614">60</span><span class="sxs-lookup"><span data-stu-id="230e2-614">60</span></span></td>
<td><span data-ttu-id="230e2-615">(60 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="230e2-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="230e2-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="230e2-616">4,487.12</span></span></td>
<td><span data-ttu-id="230e2-617">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-618">Prod 2</span><span class="sxs-lookup"><span data-stu-id="230e2-618">Prod 2</span></span></td>
<td><span data-ttu-id="230e2-619">Producto 2</span><span class="sxs-lookup"><span data-stu-id="230e2-619">Product 2</span></span></td>
<td><span data-ttu-id="230e2-620">20</span><span class="sxs-lookup"><span data-stu-id="230e2-620">20</span></span></td>
<td><span data-ttu-id="230e2-621">(20 ÷ 80) × (5.297,69 + 685,14)</span><span class="sxs-lookup"><span data-stu-id="230e2-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="230e2-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="230e2-622">1,495.71</span></span></td>
<td><span data-ttu-id="230e2-623">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="230e2-624">La tabla siguiente muestra el resultado cuando se aplican los servicios de Embalaje como base de asignación para el coste total (coste fijo y coste variable).</span><span class="sxs-lookup"><span data-stu-id="230e2-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="230e2-625">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-625">Cost object</span></span></th>
<th><span data-ttu-id="230e2-626">Magnitud</span><span class="sxs-lookup"><span data-stu-id="230e2-626">Magnitude</span></span></th>
<th><span data-ttu-id="230e2-627">Factor de asignación</span><span class="sxs-lookup"><span data-stu-id="230e2-627">Allocation factor</span></span></th>
<th><span data-ttu-id="230e2-628">Importe</span><span class="sxs-lookup"><span data-stu-id="230e2-628">Amount</span></span></th>
<th><span data-ttu-id="230e2-629">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="230e2-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-630">Prod 1</span><span class="sxs-lookup"><span data-stu-id="230e2-630">Prod 1</span></span></td>
<td><span data-ttu-id="230e2-631">Producto 1</span><span class="sxs-lookup"><span data-stu-id="230e2-631">Product 1</span></span></td>
<td><span data-ttu-id="230e2-632">80</span><span class="sxs-lookup"><span data-stu-id="230e2-632">80</span></span></td>
<td><span data-ttu-id="230e2-633">(80 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="230e2-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="230e2-634">241.05</span><span class="sxs-lookup"><span data-stu-id="230e2-634">241.05</span></span></td>
<td><span data-ttu-id="230e2-635">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-636">Prod 2</span><span class="sxs-lookup"><span data-stu-id="230e2-636">Prod 2</span></span></td>
<td><span data-ttu-id="230e2-637">Producto 2</span><span class="sxs-lookup"><span data-stu-id="230e2-637">Product 2</span></span></td>
<td><span data-ttu-id="230e2-638">15</span><span class="sxs-lookup"><span data-stu-id="230e2-638">15</span></span></td>
<td><span data-ttu-id="230e2-639">(15 ÷ 95) × (50,00 + 236,25)</span><span class="sxs-lookup"><span data-stu-id="230e2-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="230e2-640">45.20</span><span class="sxs-lookup"><span data-stu-id="230e2-640">45.20</span></span></td>
<td><span data-ttu-id="230e2-641">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-642">Prod 1</span><span class="sxs-lookup"><span data-stu-id="230e2-642">Prod 1</span></span></td>
<td><span data-ttu-id="230e2-643">Producto 1</span><span class="sxs-lookup"><span data-stu-id="230e2-643">Product 1</span></span></td>
<td><span data-ttu-id="230e2-644">80</span><span class="sxs-lookup"><span data-stu-id="230e2-644">80</span></span></td>
<td><span data-ttu-id="230e2-645">(80 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="230e2-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="230e2-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="230e2-646">2,507.09</span></span></td>
<td><span data-ttu-id="230e2-647">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-648">Prod 2</span><span class="sxs-lookup"><span data-stu-id="230e2-648">Prod 2</span></span></td>
<td><span data-ttu-id="230e2-649">Producto 2</span><span class="sxs-lookup"><span data-stu-id="230e2-649">Product 2</span></span></td>
<td><span data-ttu-id="230e2-650">15</span><span class="sxs-lookup"><span data-stu-id="230e2-650">15</span></span></td>
<td><span data-ttu-id="230e2-651">(15 ÷ 95) × (2.852,60 + 124,57)</span><span class="sxs-lookup"><span data-stu-id="230e2-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="230e2-652">470.08</span><span class="sxs-lookup"><span data-stu-id="230e2-652">470.08</span></span></td>
<td><span data-ttu-id="230e2-653">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="230e2-654">Entradas del diario (entradas de diario para saldo de objeto de costes)</span><span class="sxs-lookup"><span data-stu-id="230e2-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="230e2-655">Diario</span><span class="sxs-lookup"><span data-stu-id="230e2-655">Journal</span></span></th>
<th><span data-ttu-id="230e2-656">Tipo de diario</span><span class="sxs-lookup"><span data-stu-id="230e2-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="230e2-657">Período de calendario fiscal</span><span class="sxs-lookup"><span data-stu-id="230e2-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="230e2-658">Versión</span><span class="sxs-lookup"><span data-stu-id="230e2-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-659">00004</span><span class="sxs-lookup"><span data-stu-id="230e2-659">00004</span></span></td>
<td><span data-ttu-id="230e2-660">Diario de asignación de costes</span><span class="sxs-lookup"><span data-stu-id="230e2-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="230e2-661">Fiscal</span><span class="sxs-lookup"><span data-stu-id="230e2-661">Fiscal</span></span></td>
<td><span data-ttu-id="230e2-662">2017</span><span class="sxs-lookup"><span data-stu-id="230e2-662">2017</span></span></td>
<td><span data-ttu-id="230e2-663">Período 1</span><span class="sxs-lookup"><span data-stu-id="230e2-663">Period 1</span></span></td>
<td><span data-ttu-id="230e2-664">Cálculo de costes generales/ 01-02-2017 11:51:00 PM/Contabilidad/2017/Período 1</span><span class="sxs-lookup"><span data-stu-id="230e2-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="230e2-665">Líneas de diario</span><span class="sxs-lookup"><span data-stu-id="230e2-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="230e2-666">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="230e2-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="230e2-667">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="230e2-668">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-668">Cost element</span></span></th>
<th><span data-ttu-id="230e2-669">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="230e2-669">Cost behavior</span></span></th>
<th><span data-ttu-id="230e2-670">Importe</span><span class="sxs-lookup"><span data-stu-id="230e2-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-671">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="230e2-672">CC001</span><span class="sxs-lookup"><span data-stu-id="230e2-672">CC001</span></span></td>
<td><span data-ttu-id="230e2-673">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="230e2-673">HR</span></span></td>
<td><span data-ttu-id="230e2-674">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-674">10001</span></span></td>
<td><span data-ttu-id="230e2-675">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-675">Electricity</span></span></td>
<td><span data-ttu-id="230e2-676">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-676">Fixed cost</span></span></td>
<td><span data-ttu-id="230e2-677">500,00</span><span class="sxs-lookup"><span data-stu-id="230e2-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-678">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="230e2-679">CC001</span><span class="sxs-lookup"><span data-stu-id="230e2-679">CC001</span></span></td>
<td><span data-ttu-id="230e2-680">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="230e2-680">HR</span></span></td>
<td><span data-ttu-id="230e2-681">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-681">10001</span></span></td>
<td><span data-ttu-id="230e2-682">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-682">Electricity</span></span></td>
<td><span data-ttu-id="230e2-683">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-683">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="230e2-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-685">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="230e2-686">CC002</span><span class="sxs-lookup"><span data-stu-id="230e2-686">CC002</span></span></td>
<td><span data-ttu-id="230e2-687">Finanzas</span><span class="sxs-lookup"><span data-stu-id="230e2-687">Finance</span></span></td>
<td><span data-ttu-id="230e2-688">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-688">10001</span></span></td>
<td><span data-ttu-id="230e2-689">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-689">Electricity</span></span></td>
<td><span data-ttu-id="230e2-690">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-690">Fixed cost</span></span></td>
<td><span data-ttu-id="230e2-691">675.00</span><span class="sxs-lookup"><span data-stu-id="230e2-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-692">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="230e2-693">CC002</span><span class="sxs-lookup"><span data-stu-id="230e2-693">CC002</span></span></td>
<td><span data-ttu-id="230e2-694">Finanzas</span><span class="sxs-lookup"><span data-stu-id="230e2-694">Finance</span></span></td>
<td><span data-ttu-id="230e2-695">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-695">10001</span></span></td>
<td><span data-ttu-id="230e2-696">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-696">Electricity</span></span></td>
<td><span data-ttu-id="230e2-697">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-697">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="230e2-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-699">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="230e2-700">CC003</span><span class="sxs-lookup"><span data-stu-id="230e2-700">CC003</span></span></td>
<td><span data-ttu-id="230e2-701">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="230e2-701">Assembly</span></span></td>
<td><span data-ttu-id="230e2-702">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-702">10001</span></span></td>
<td><span data-ttu-id="230e2-703">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-703">Electricity</span></span></td>
<td><span data-ttu-id="230e2-704">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-704">Fixed cost</span></span></td>
<td><span data-ttu-id="230e2-705">713.75</span><span class="sxs-lookup"><span data-stu-id="230e2-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-706">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="230e2-707">CC003</span><span class="sxs-lookup"><span data-stu-id="230e2-707">CC003</span></span></td>
<td><span data-ttu-id="230e2-708">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="230e2-708">Assembly</span></span></td>
<td><span data-ttu-id="230e2-709">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-709">10001</span></span></td>
<td><span data-ttu-id="230e2-710">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-710">Electricity</span></span></td>
<td><span data-ttu-id="230e2-711">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-711">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="230e2-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-713">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="230e2-714">CC003</span><span class="sxs-lookup"><span data-stu-id="230e2-714">CC003</span></span></td>
<td><span data-ttu-id="230e2-715">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="230e2-715">Packaging</span></span></td>
<td><span data-ttu-id="230e2-716">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-716">10001</span></span></td>
<td><span data-ttu-id="230e2-717">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-717">Electricity</span></span></td>
<td><span data-ttu-id="230e2-718">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-718">Fixed cost</span></span></td>
<td><span data-ttu-id="230e2-719">286.25</span><span class="sxs-lookup"><span data-stu-id="230e2-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-720">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="230e2-721">CC003</span><span class="sxs-lookup"><span data-stu-id="230e2-721">CC003</span></span></td>
<td><span data-ttu-id="230e2-722">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="230e2-722">Packaging</span></span></td>
<td><span data-ttu-id="230e2-723">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-723">10001</span></span></td>
<td><span data-ttu-id="230e2-724">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-724">Electricity</span></span></td>
<td><span data-ttu-id="230e2-725">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-725">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="230e2-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-727">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="230e2-728">Prod 1</span><span class="sxs-lookup"><span data-stu-id="230e2-728">Prod 1</span></span></td>
<td><span data-ttu-id="230e2-729">Producto 1</span><span class="sxs-lookup"><span data-stu-id="230e2-729">Product 1</span></span></td>
<td><span data-ttu-id="230e2-730">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-730">10001</span></span></td>
<td><span data-ttu-id="230e2-731">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-731">Electricity</span></span></td>
<td><span data-ttu-id="230e2-732">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-732">Fixed cost</span></span></td>
<td><span data-ttu-id="230e2-733">776.36</span><span class="sxs-lookup"><span data-stu-id="230e2-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-734">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="230e2-735">Prod 1</span><span class="sxs-lookup"><span data-stu-id="230e2-735">Prod 1</span></span></td>
<td><span data-ttu-id="230e2-736">Producto 1</span><span class="sxs-lookup"><span data-stu-id="230e2-736">Product 1</span></span></td>
<td><span data-ttu-id="230e2-737">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-737">10001</span></span></td>
<td><span data-ttu-id="230e2-738">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-738">Electricity</span></span></td>
<td><span data-ttu-id="230e2-739">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-739">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="230e2-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-741">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="230e2-742">Prod 2</span><span class="sxs-lookup"><span data-stu-id="230e2-742">Prod 2</span></span></td>
<td><span data-ttu-id="230e2-743">Producto 1</span><span class="sxs-lookup"><span data-stu-id="230e2-743">Product 1</span></span></td>
<td><span data-ttu-id="230e2-744">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-744">10001</span></span></td>
<td><span data-ttu-id="230e2-745">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-745">Electricity</span></span></td>
<td><span data-ttu-id="230e2-746">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-746">Fixed cost</span></span></td>
<td><span data-ttu-id="230e2-747">223.64</span><span class="sxs-lookup"><span data-stu-id="230e2-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-748">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="230e2-749">Prod 2</span><span class="sxs-lookup"><span data-stu-id="230e2-749">Prod 2</span></span></td>
<td><span data-ttu-id="230e2-750">Producto 1</span><span class="sxs-lookup"><span data-stu-id="230e2-750">Product 1</span></span></td>
<td><span data-ttu-id="230e2-751">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-751">10001</span></span></td>
<td><span data-ttu-id="230e2-752">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-752">Electricity</span></span></td>
<td><span data-ttu-id="230e2-753">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-753">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="230e2-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="230e2-755">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="230e2-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="230e2-756">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="230e2-757">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-757">Cost element</span></span></th>
<th><span data-ttu-id="230e2-758">Comportamiento de costes</span><span class="sxs-lookup"><span data-stu-id="230e2-758">Cost behavior</span></span></th>
<th><span data-ttu-id="230e2-759">Importe</span><span class="sxs-lookup"><span data-stu-id="230e2-759">Amount</span></span></th>
<th><span data-ttu-id="230e2-760">Fecha contable</span><span class="sxs-lookup"><span data-stu-id="230e2-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="230e2-761">CC001</span><span class="sxs-lookup"><span data-stu-id="230e2-761">CC001</span></span></td>
<td><span data-ttu-id="230e2-762">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="230e2-762">HR</span></span></td>
<td><span data-ttu-id="230e2-763">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-763">10001</span></span></td>
<td><span data-ttu-id="230e2-764">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-764">Electricity</span></span></td>
<td><span data-ttu-id="230e2-765">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-765">Fixed cost</span></span></td>
<td><span data-ttu-id="230e2-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="230e2-766">-500.00</span></span></td>
<td><span data-ttu-id="230e2-767">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-768">CC002</span><span class="sxs-lookup"><span data-stu-id="230e2-768">CC002</span></span></td>
<td><span data-ttu-id="230e2-769">Finanzas</span><span class="sxs-lookup"><span data-stu-id="230e2-769">Finance</span></span></td>
<td><span data-ttu-id="230e2-770">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-770">10001</span></span></td>
<td><span data-ttu-id="230e2-771">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-771">Electricity</span></span></td>
<td><span data-ttu-id="230e2-772">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-772">Fixed cost</span></span></td>
<td><span data-ttu-id="230e2-773">175.00</span><span class="sxs-lookup"><span data-stu-id="230e2-773">175.00</span></span></td>
<td><span data-ttu-id="230e2-774">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-775">CC003</span><span class="sxs-lookup"><span data-stu-id="230e2-775">CC003</span></span></td>
<td><span data-ttu-id="230e2-776">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="230e2-776">Assembly</span></span></td>
<td><span data-ttu-id="230e2-777">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-777">10001</span></span></td>
<td><span data-ttu-id="230e2-778">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-778">Electricity</span></span></td>
<td><span data-ttu-id="230e2-779">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-779">Fixed cost</span></span></td>
<td><span data-ttu-id="230e2-780">275.00</span><span class="sxs-lookup"><span data-stu-id="230e2-780">275.00</span></span></td>
<td><span data-ttu-id="230e2-781">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-782">CC004</span><span class="sxs-lookup"><span data-stu-id="230e2-782">CC004</span></span></td>
<td><span data-ttu-id="230e2-783">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="230e2-783">Packaging</span></span></td>
<td><span data-ttu-id="230e2-784">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-784">10001</span></span></td>
<td><span data-ttu-id="230e2-785">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-785">Electricity</span></span></td>
<td><span data-ttu-id="230e2-786">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-786">Fixed cost</span></span></td>
<td><span data-ttu-id="230e2-787">50,00</span><span class="sxs-lookup"><span data-stu-id="230e2-787">50,00</span></span></td>
<td><span data-ttu-id="230e2-788">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-789">CC001</span><span class="sxs-lookup"><span data-stu-id="230e2-789">CC001</span></span></td>
<td><span data-ttu-id="230e2-790">RR. HH.</span><span class="sxs-lookup"><span data-stu-id="230e2-790">HR</span></span></td>
<td><span data-ttu-id="230e2-791">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-791">10001</span></span></td>
<td><span data-ttu-id="230e2-792">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-792">Electricity</span></span></td>
<td><span data-ttu-id="230e2-793">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-793">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-794">-1.245,71</span><span class="sxs-lookup"><span data-stu-id="230e2-794">-1,245.71</span></span></td>
<td><span data-ttu-id="230e2-795">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-796">CC002</span><span class="sxs-lookup"><span data-stu-id="230e2-796">CC002</span></span></td>
<td><span data-ttu-id="230e2-797">Finanzas</span><span class="sxs-lookup"><span data-stu-id="230e2-797">Finance</span></span></td>
<td><span data-ttu-id="230e2-798">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-798">10001</span></span></td>
<td><span data-ttu-id="230e2-799">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-799">Electricity</span></span></td>
<td><span data-ttu-id="230e2-800">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-800">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-801">436.00</span><span class="sxs-lookup"><span data-stu-id="230e2-801">436.00</span></span></td>
<td><span data-ttu-id="230e2-802">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-803">CC003</span><span class="sxs-lookup"><span data-stu-id="230e2-803">CC003</span></span></td>
<td><span data-ttu-id="230e2-804">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="230e2-804">Assembly</span></span></td>
<td><span data-ttu-id="230e2-805">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-805">10001</span></span></td>
<td><span data-ttu-id="230e2-806">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-806">Electricity</span></span></td>
<td><span data-ttu-id="230e2-807">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-807">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-808">685.14</span><span class="sxs-lookup"><span data-stu-id="230e2-808">685.14</span></span></td>
<td><span data-ttu-id="230e2-809">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-810">CC004</span><span class="sxs-lookup"><span data-stu-id="230e2-810">CC004</span></span></td>
<td><span data-ttu-id="230e2-811">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="230e2-811">Packaging</span></span></td>
<td><span data-ttu-id="230e2-812">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-812">10001</span></span></td>
<td><span data-ttu-id="230e2-813">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-813">Electricity</span></span></td>
<td><span data-ttu-id="230e2-814">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-814">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-815">124.57</span><span class="sxs-lookup"><span data-stu-id="230e2-815">124.57</span></span></td>
<td><span data-ttu-id="230e2-816">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-817">CC002</span><span class="sxs-lookup"><span data-stu-id="230e2-817">CC002</span></span></td>
<td><span data-ttu-id="230e2-818">Finanzas</span><span class="sxs-lookup"><span data-stu-id="230e2-818">Finance</span></span></td>
<td><span data-ttu-id="230e2-819">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-819">10001</span></span></td>
<td><span data-ttu-id="230e2-820">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-820">Electricity</span></span></td>
<td><span data-ttu-id="230e2-821">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-821">Fixed cost</span></span></td>
<td><span data-ttu-id="230e2-822">-675,00</span><span class="sxs-lookup"><span data-stu-id="230e2-822">-675.00</span></span></td>
<td><span data-ttu-id="230e2-823">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-824">CC003</span><span class="sxs-lookup"><span data-stu-id="230e2-824">CC003</span></span></td>
<td><span data-ttu-id="230e2-825">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="230e2-825">Assembly</span></span></td>
<td><span data-ttu-id="230e2-826">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-826">10001</span></span></td>
<td><span data-ttu-id="230e2-827">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-827">Electricity</span></span></td>
<td><span data-ttu-id="230e2-828">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-828">Fixed cost</span></span></td>
<td><span data-ttu-id="230e2-829">438.75</span><span class="sxs-lookup"><span data-stu-id="230e2-829">438.75</span></span></td>
<td><span data-ttu-id="230e2-830">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-831">CC004</span><span class="sxs-lookup"><span data-stu-id="230e2-831">CC004</span></span></td>
<td><span data-ttu-id="230e2-832">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="230e2-832">Packaging</span></span></td>
<td><span data-ttu-id="230e2-833">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-833">10001</span></span></td>
<td><span data-ttu-id="230e2-834">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-834">Electricity</span></span></td>
<td><span data-ttu-id="230e2-835">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-835">Fixed cost</span></span></td>
<td><span data-ttu-id="230e2-836">236.25</span><span class="sxs-lookup"><span data-stu-id="230e2-836">236.25</span></span></td>
<td><span data-ttu-id="230e2-837">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-838">CC002</span><span class="sxs-lookup"><span data-stu-id="230e2-838">CC002</span></span></td>
<td><span data-ttu-id="230e2-839">Finanzas</span><span class="sxs-lookup"><span data-stu-id="230e2-839">Finance</span></span></td>
<td><span data-ttu-id="230e2-840">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-840">10001</span></span></td>
<td><span data-ttu-id="230e2-841">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-841">Electricity</span></span></td>
<td><span data-ttu-id="230e2-842">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-842">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-843">-8.150,29</span><span class="sxs-lookup"><span data-stu-id="230e2-843">-8,150.29</span></span></td>
<td><span data-ttu-id="230e2-844">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-845">CC003</span><span class="sxs-lookup"><span data-stu-id="230e2-845">CC003</span></span></td>
<td><span data-ttu-id="230e2-846">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="230e2-846">Assembly</span></span></td>
<td><span data-ttu-id="230e2-847">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-847">10001</span></span></td>
<td><span data-ttu-id="230e2-848">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-848">Electricity</span></span></td>
<td><span data-ttu-id="230e2-849">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-849">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="230e2-850">5,297.69</span></span></td>
<td><span data-ttu-id="230e2-851">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-852">CC004</span><span class="sxs-lookup"><span data-stu-id="230e2-852">CC004</span></span></td>
<td><span data-ttu-id="230e2-853">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="230e2-853">Packaging</span></span></td>
<td><span data-ttu-id="230e2-854">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-854">10001</span></span></td>
<td><span data-ttu-id="230e2-855">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-855">Electricity</span></span></td>
<td><span data-ttu-id="230e2-856">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-856">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="230e2-857">2,852.60</span></span></td>
<td><span data-ttu-id="230e2-858">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-859">CC003</span><span class="sxs-lookup"><span data-stu-id="230e2-859">CC003</span></span></td>
<td><span data-ttu-id="230e2-860">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="230e2-860">Assembly</span></span></td>
<td><span data-ttu-id="230e2-861">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-861">10001</span></span></td>
<td><span data-ttu-id="230e2-862">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-862">Electricity</span></span></td>
<td><span data-ttu-id="230e2-863">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-863">Fixed cost</span></span></td>
<td><span data-ttu-id="230e2-864">-713,75</span><span class="sxs-lookup"><span data-stu-id="230e2-864">-713.75</span></span></td>
<td><span data-ttu-id="230e2-865">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-866">Prod 1</span><span class="sxs-lookup"><span data-stu-id="230e2-866">Prod 1</span></span></td>
<td><span data-ttu-id="230e2-867">Producto 1</span><span class="sxs-lookup"><span data-stu-id="230e2-867">Product 1</span></span></td>
<td><span data-ttu-id="230e2-868">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-868">10001</span></span></td>
<td><span data-ttu-id="230e2-869">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-869">Electricity</span></span></td>
<td><span data-ttu-id="230e2-870">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-870">Fixed cost</span></span></td>
<td><span data-ttu-id="230e2-871">535.31</span><span class="sxs-lookup"><span data-stu-id="230e2-871">535.31</span></span></td>
<td><span data-ttu-id="230e2-872">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-873">Prod 2</span><span class="sxs-lookup"><span data-stu-id="230e2-873">Prod 2</span></span></td>
<td><span data-ttu-id="230e2-874">Producto 2</span><span class="sxs-lookup"><span data-stu-id="230e2-874">Product 2</span></span></td>
<td><span data-ttu-id="230e2-875">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-875">10001</span></span></td>
<td><span data-ttu-id="230e2-876">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-876">Electricity</span></span></td>
<td><span data-ttu-id="230e2-877">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-877">Fixed cost</span></span></td>
<td><span data-ttu-id="230e2-878">178.44</span><span class="sxs-lookup"><span data-stu-id="230e2-878">178.44</span></span></td>
<td><span data-ttu-id="230e2-879">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-880">CC003</span><span class="sxs-lookup"><span data-stu-id="230e2-880">CC003</span></span></td>
<td><span data-ttu-id="230e2-881">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="230e2-881">Assembly</span></span></td>
<td><span data-ttu-id="230e2-882">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-882">10001</span></span></td>
<td><span data-ttu-id="230e2-883">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-883">Electricity</span></span></td>
<td><span data-ttu-id="230e2-884">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-884">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-885">-5.982,83</span><span class="sxs-lookup"><span data-stu-id="230e2-885">-5,982.83</span></span></td>
<td><span data-ttu-id="230e2-886">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-887">Prod 1</span><span class="sxs-lookup"><span data-stu-id="230e2-887">Prod 1</span></span></td>
<td><span data-ttu-id="230e2-888">Producto 1</span><span class="sxs-lookup"><span data-stu-id="230e2-888">Product 1</span></span></td>
<td><span data-ttu-id="230e2-889">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-889">10001</span></span></td>
<td><span data-ttu-id="230e2-890">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-890">Electricity</span></span></td>
<td><span data-ttu-id="230e2-891">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-891">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="230e2-892">4,487.12</span></span></td>
<td><span data-ttu-id="230e2-893">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-894">Prod 2</span><span class="sxs-lookup"><span data-stu-id="230e2-894">Prod 2</span></span></td>
<td><span data-ttu-id="230e2-895">Producto 2</span><span class="sxs-lookup"><span data-stu-id="230e2-895">Product 2</span></span></td>
<td><span data-ttu-id="230e2-896">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-896">10001</span></span></td>
<td><span data-ttu-id="230e2-897">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-897">Electricity</span></span></td>
<td><span data-ttu-id="230e2-898">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-898">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="230e2-899">1,495.71</span></span></td>
<td><span data-ttu-id="230e2-900">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-901">CC003</span><span class="sxs-lookup"><span data-stu-id="230e2-901">CC003</span></span></td>
<td><span data-ttu-id="230e2-902">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="230e2-902">Assembly</span></span></td>
<td><span data-ttu-id="230e2-903">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-903">10001</span></span></td>
<td><span data-ttu-id="230e2-904">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-904">Electricity</span></span></td>
<td><span data-ttu-id="230e2-905">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-905">Fixed cost</span></span></td>
<td><span data-ttu-id="230e2-906">-286,25</span><span class="sxs-lookup"><span data-stu-id="230e2-906">-286.25</span></span></td>
<td><span data-ttu-id="230e2-907">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-908">Prod 1</span><span class="sxs-lookup"><span data-stu-id="230e2-908">Prod 1</span></span></td>
<td><span data-ttu-id="230e2-909">Producto 1</span><span class="sxs-lookup"><span data-stu-id="230e2-909">Product 1</span></span></td>
<td><span data-ttu-id="230e2-910">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-910">10001</span></span></td>
<td><span data-ttu-id="230e2-911">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-911">Electricity</span></span></td>
<td><span data-ttu-id="230e2-912">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-912">Fixed cost</span></span></td>
<td><span data-ttu-id="230e2-913">241.05</span><span class="sxs-lookup"><span data-stu-id="230e2-913">241.05</span></span></td>
<td><span data-ttu-id="230e2-914">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-915">Prod 2</span><span class="sxs-lookup"><span data-stu-id="230e2-915">Prod 2</span></span></td>
<td><span data-ttu-id="230e2-916">Producto 2</span><span class="sxs-lookup"><span data-stu-id="230e2-916">Product 2</span></span></td>
<td><span data-ttu-id="230e2-917">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-917">10001</span></span></td>
<td><span data-ttu-id="230e2-918">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-918">Electricity</span></span></td>
<td><span data-ttu-id="230e2-919">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-919">Fixed cost</span></span></td>
<td><span data-ttu-id="230e2-920">45.20</span><span class="sxs-lookup"><span data-stu-id="230e2-920">45.20</span></span></td>
<td><span data-ttu-id="230e2-921">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-922">CC003</span><span class="sxs-lookup"><span data-stu-id="230e2-922">CC003</span></span></td>
<td><span data-ttu-id="230e2-923">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="230e2-923">Assembly</span></span></td>
<td><span data-ttu-id="230e2-924">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-924">10001</span></span></td>
<td><span data-ttu-id="230e2-925">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-925">Electricity</span></span></td>
<td><span data-ttu-id="230e2-926">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-926">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-927">-2.977,17</span><span class="sxs-lookup"><span data-stu-id="230e2-927">-2,977.17</span></span></td>
<td><span data-ttu-id="230e2-928">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-929">Prod 1</span><span class="sxs-lookup"><span data-stu-id="230e2-929">Prod 1</span></span></td>
<td><span data-ttu-id="230e2-930">Producto 1</span><span class="sxs-lookup"><span data-stu-id="230e2-930">Product 1</span></span></td>
<td><span data-ttu-id="230e2-931">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-931">10001</span></span></td>
<td><span data-ttu-id="230e2-932">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-932">Electricity</span></span></td>
<td><span data-ttu-id="230e2-933">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-933">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="230e2-934">2,507.09</span></span></td>
<td><span data-ttu-id="230e2-935">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="230e2-936">Prod 2</span><span class="sxs-lookup"><span data-stu-id="230e2-936">Prod 2</span></span></td>
<td><span data-ttu-id="230e2-937">Producto 2</span><span class="sxs-lookup"><span data-stu-id="230e2-937">Product 2</span></span></td>
<td><span data-ttu-id="230e2-938">10001</span><span class="sxs-lookup"><span data-stu-id="230e2-938">10001</span></span></td>
<td><span data-ttu-id="230e2-939">Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-939">Electricity</span></span></td>
<td><span data-ttu-id="230e2-940">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-940">Variable cost</span></span></td>
<td><span data-ttu-id="230e2-941">470.08</span><span class="sxs-lookup"><span data-stu-id="230e2-941">470.08</span></span></td>
<td><span data-ttu-id="230e2-942">31 de enero de 2017</span><span class="sxs-lookup"><span data-stu-id="230e2-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="230e2-943">Conclusión</span><span class="sxs-lookup"><span data-stu-id="230e2-943">Conclusion</span></span>
<span data-ttu-id="230e2-944">En la contabilidad financiera, un coste de 10.000,00 para electricidad se envía a un identificador ficticio de centro de coste.</span><span class="sxs-lookup"><span data-stu-id="230e2-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="230e2-945">Por lo tanto, los contables de coste sabrán que este coste se debe asignar.</span><span class="sxs-lookup"><span data-stu-id="230e2-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="230e2-946">En contabilidad de costes, los costes fluyen en las unidades organizativas y los niveles en función de las directivas y las reglas que se aplican.</span><span class="sxs-lookup"><span data-stu-id="230e2-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="230e2-947">Cada coste se ha asociado con una base de asignación que proporciona la mejor evaluación para la asignación de costes.</span><span class="sxs-lookup"><span data-stu-id="230e2-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="230e2-948">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="230e2-949">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="230e2-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="230e2-950">Total</span><span class="sxs-lookup"><span data-stu-id="230e2-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="230e2-951">CC099</span><span class="sxs-lookup"><span data-stu-id="230e2-951">CC099</span></span></th>
<th><span data-ttu-id="230e2-952">CC001</span><span class="sxs-lookup"><span data-stu-id="230e2-952">CC001</span></span></th>
<th><span data-ttu-id="230e2-953">CC002</span><span class="sxs-lookup"><span data-stu-id="230e2-953">CC002</span></span></th>
<th><span data-ttu-id="230e2-954">CC003</span><span class="sxs-lookup"><span data-stu-id="230e2-954">CC003</span></span></th>
<th><span data-ttu-id="230e2-955">CC004</span><span class="sxs-lookup"><span data-stu-id="230e2-955">CC004</span></span></th>
<th><span data-ttu-id="230e2-956">Proy 1</span><span class="sxs-lookup"><span data-stu-id="230e2-956">Proj 1</span></span></th>
<th><span data-ttu-id="230e2-957">Proy 2</span><span class="sxs-lookup"><span data-stu-id="230e2-957">Proj 2</span></span></th>
<th><span data-ttu-id="230e2-958">Prod 1</span><span class="sxs-lookup"><span data-stu-id="230e2-958">Prod 1</span></span></th>
<th><span data-ttu-id="230e2-959">Prod 2</span><span class="sxs-lookup"><span data-stu-id="230e2-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="230e2-960">10001 Electricidad</span><span class="sxs-lookup"><span data-stu-id="230e2-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-961"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="230e2-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-962"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="230e2-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-963"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="230e2-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-964"><strong>0.00</strong></span><span class="sxs-lookup"><span data-stu-id="230e2-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="230e2-965"><strong>30.00</strong></span><span class="sxs-lookup"><span data-stu-id="230e2-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-966"><strong>10.00</strong></span><span class="sxs-lookup"><span data-stu-id="230e2-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-967"><strong>7,770.57</strong></span><span class="sxs-lookup"><span data-stu-id="230e2-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-968"><strong>2,189.43</strong></span><span class="sxs-lookup"><span data-stu-id="230e2-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-969"><strong>10,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="230e2-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="230e2-970">Sin clasificar</span><span class="sxs-lookup"><span data-stu-id="230e2-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-971">0,00</span><span class="sxs-lookup"><span data-stu-id="230e2-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="230e2-972">Coste fijo</span><span class="sxs-lookup"><span data-stu-id="230e2-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-973">0,00</span><span class="sxs-lookup"><span data-stu-id="230e2-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-974">0,00</span><span class="sxs-lookup"><span data-stu-id="230e2-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-975">0,00</span><span class="sxs-lookup"><span data-stu-id="230e2-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-976">0,00</span><span class="sxs-lookup"><span data-stu-id="230e2-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-977">0,00</span><span class="sxs-lookup"><span data-stu-id="230e2-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="230e2-978">776.36</span><span class="sxs-lookup"><span data-stu-id="230e2-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-979">223.64</span><span class="sxs-lookup"><span data-stu-id="230e2-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-980"><strong>1,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="230e2-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="230e2-981">Coste variable</span><span class="sxs-lookup"><span data-stu-id="230e2-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-982">000</span><span class="sxs-lookup"><span data-stu-id="230e2-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-983">0,00</span><span class="sxs-lookup"><span data-stu-id="230e2-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-984">0,00</span><span class="sxs-lookup"><span data-stu-id="230e2-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-985">0,00</span><span class="sxs-lookup"><span data-stu-id="230e2-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-986">0,00</span><span class="sxs-lookup"><span data-stu-id="230e2-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-987">30,00</span><span class="sxs-lookup"><span data-stu-id="230e2-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-988">10,00</span><span class="sxs-lookup"><span data-stu-id="230e2-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="230e2-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="230e2-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="230e2-991"><strong>9,000.00</strong></span><span class="sxs-lookup"><span data-stu-id="230e2-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="230e2-992">Este tema muestra cómo un artículo de costes principales, 10001 Electricidad, fluye por los objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="230e2-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="230e2-993">Por tanto, estos gastos generales se asignan al nivel más bajo de la organización.</span><span class="sxs-lookup"><span data-stu-id="230e2-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="230e2-994">Es decir, los objetos de coste del nivel más bajo son los que soportan el coste.</span><span class="sxs-lookup"><span data-stu-id="230e2-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="230e2-995">Si necesita un flujo visual del coste entre los objetos de coste, puede usar las reglas de directivas de acumulación de costes para visualizar el flujo del coste.</span><span class="sxs-lookup"><span data-stu-id="230e2-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="230e2-996">Para obtener más información, consulte [Acumulación de costes](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="230e2-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>



