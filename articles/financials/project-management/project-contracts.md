---
title: Contratos de proyecto
description: "Este tema describe y proporciona ejemplos de contratos de proyecto que puede crear para diversos tipos de proyectos y fuentes de financiación, y cómo puede administrar contratos y clientes de proyecto de facturación en Microsoft Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjProjectContractsListPage, ProjProjectsListPage
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23561
ms.assetid: bfd18d9b-d9a6-4e21-bc95-bf4af45f617f
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: e46393b9ac8797bf12cca12099d177980b75ba38
ms.contentlocale: es-es
ms.lasthandoff: 03/26/2018

---

# <a name="project-contracts"></a><span data-ttu-id="c62c7-103">Contratos de proyecto</span><span class="sxs-lookup"><span data-stu-id="c62c7-103">Project contracts</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="c62c7-104">Este artículo describe y proporciona ejemplos de contratos de proyecto que puede crear para diversos tipos de proyectos y fuentes de financiación, y cómo puede administrar contratos y clientes de proyecto de facturación en Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c62c7-104">This article provides examples of the project contracts that you can create for various types of projects and funding sources, and how you can manage contracts and invoice project customers in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="c62c7-105">El tipo de proyecto que cree para un contrato de proyecto determinará el método de facturación usado para los clientes del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-105">The type of project that you create for a project contract determines the method that is used to invoice project customers.</span></span> <span data-ttu-id="c62c7-106">Puede cambiar un contrato de proyecto y el proyecto relacionado, pero no puede cambiar el tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-106">You can change a project contract and the related project, but you can't change the project type.</span></span> 

<span data-ttu-id="c62c7-107">Al utilizar el contrato del proyecto, puede facturar uno o varios proyectos al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="c62c7-107">By using a project contract, you can invoice one or more projects at the same time.</span></span> <span data-ttu-id="c62c7-108">El contrato de proyecto también ayuda a garantizar un procedimiento de facturación coherente para cada subproyecto de una estructura de proyectos.</span><span class="sxs-lookup"><span data-stu-id="c62c7-108">The project contract also helps guarantee a consistent invoicing procedure for every subproject in a project structure.</span></span> 

<span data-ttu-id="c62c7-109">Cada proyecto que se facturará se debe asociar a un contrato de proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-109">Every project that will be invoiced must be associated with a project contract.</span></span> <span data-ttu-id="c62c7-110">La configuración para un contrato de proyecto se aplica a todos los proyectos y subproyectos asociados a ese contrato de proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-110">The settings for a project contract apply to all projects and subprojects that are associated with that project contract.</span></span> 

<span data-ttu-id="c62c7-111">En un contrato de proyecto se puede especificar una o más fuentes de financiación.</span><span class="sxs-lookup"><span data-stu-id="c62c7-111">A project contract can specify one or more sources of funding.</span></span> <span data-ttu-id="c62c7-112">Por tanto, puede dividir la facturación entre varios proveedores de fondos, configurar los límites de financiación para que la factura a las fuentes de financiación no incluyan importes superiores a los especificados y configurar reglas de financiación para el cargo de gastos.</span><span class="sxs-lookup"><span data-stu-id="c62c7-112">Therefore, you can split the billing among multiple funders, set up funding limits so that funding sources are not billed more than a specified amount, and configure funding rules for charging expenditures.</span></span>

## <a name="funding-for-project-contracts"></a><span data-ttu-id="c62c7-113">Financiación para contratos de proyecto</span><span class="sxs-lookup"><span data-stu-id="c62c7-113">Funding for project contracts</span></span>
<span data-ttu-id="c62c7-114">Algunos contratos de proyecto especifican que varias partes comparten las responsabilidad de la financiación de los costes del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-114">Some project contracts specify that multiple parties share the responsibility for funding the project costs.</span></span> <span data-ttu-id="c62c7-115">A continuación se incluyen algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="c62c7-115">Here are some examples:</span></span>

-   <span data-ttu-id="c62c7-116">Un cliente grande que tiene varias divisiones solicita que la financiación de un proyecto se divida por división.</span><span class="sxs-lookup"><span data-stu-id="c62c7-116">A large customer that has multiple divisions requests that funding of a project be split by division.</span></span>
-   <span data-ttu-id="c62c7-117">La empresa comparte los costes de un gran proyecto con una organización externa.</span><span class="sxs-lookup"><span data-stu-id="c62c7-117">Your company shares the costs of a large project with an external organization.</span></span>
-   <span data-ttu-id="c62c7-118">Un proyecto de carretera está cofinanciado por dos municipios.</span><span class="sxs-lookup"><span data-stu-id="c62c7-118">A  road project is co-funded by two municipalities.</span></span>
-   <span data-ttu-id="c62c7-119">Un proyecto de puente está financiado por una concesión del gobierno y una corporación privada.</span><span class="sxs-lookup"><span data-stu-id="c62c7-119">A bridge project is funded by a government grant and a private corporation.</span></span>

<span data-ttu-id="c62c7-120">En Finance and Operations, puede dividir la facturación de una sola transacción o un proyecto completo entre varios clientes, concesiones u organizaciones.</span><span class="sxs-lookup"><span data-stu-id="c62c7-120">In Finance and Operations, you can split the billing for a single transaction or an entire project among multiple customers, grants, or organizations.</span></span> 

<span data-ttu-id="c62c7-121">En proyectos con varios proveedores de fondos, todas las partes que contribuyen a la financiación de un proyecto de financiación avanzada se denominan fuentes de financiación.</span><span class="sxs-lookup"><span data-stu-id="c62c7-121">In projects that have multiple funders, all parties that contribute to the funding of an advanced funding project are called funding sources.</span></span> <span data-ttu-id="c62c7-122">Después de definir un cliente, organización o concesión como fuente de financiación, se puede asignar a una o varias reglas de financiación.</span><span class="sxs-lookup"><span data-stu-id="c62c7-122">After a customer, organization, or grant is defined as a funding source, it can be assigned to one or more funding rules.</span></span> <span data-ttu-id="c62c7-123">Las reglas de financiación contienen los criterios que determinan cómo se asignan gastos a las distintas fuentes de financiación de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-123">Funding rules contain the criteria that determines how charges are allocated to the various funding sources for a project.</span></span> 

<span data-ttu-id="c62c7-124">Dado que los artículos mantenidos en existencias, como los que aparecen en las solicitudes de compra y los pedidos de compra, no se pueden dividir, el importe del coste no se puede dividir entre varias fuentes de financiación en el momento de la distribución.</span><span class="sxs-lookup"><span data-stu-id="c62c7-124">Because stocked items, such as those that appear on purchase requisitions and purchase orders, can't be split, the cost amount can't be split among multiple funding sources at the time of distribution.</span></span> <span data-ttu-id="c62c7-125">Por lo tanto, el valor de la fuente de financiación es 0 (cero) hasta que se registra la emisión de inventario.</span><span class="sxs-lookup"><span data-stu-id="c62c7-125">Therefore, the funding source value remains 0 (zero) until the inventory issue is posted.</span></span> <span data-ttu-id="c62c7-126">Al registrarse, el importe de coste se distribuye de acuerdo con las reglas de distribución contable del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-126">When the inventory issue is posted, the cost amount is distributed according to the account distribution rules for the project.</span></span>

<span data-ttu-id="c62c7-127">A continuación se muestran algunos pasos que puede llevar a cabo para facilitar la división de la facturación entre varias fuentes de financiación:</span><span class="sxs-lookup"><span data-stu-id="c62c7-127">Here are some steps that you can take to make it easier to split the billing among multiple funding sources:</span></span>

-   <span data-ttu-id="c62c7-128">Especifique que todas las transacciones de un proyecto usen la misma divisa de ventas que el contrato de proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-128">Specify that all transactions that are entered for a project use the same sales currency as the project contract.</span></span>
-   <span data-ttu-id="c62c7-129">Defina los límites de financiación para que ninguna fuente de financiación reciba facturas por un importe superior al especificado para un proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-129">Set up funding limits, so that a funding source isn't invoiced more than a specified amount toward a project.</span></span>
-   <span data-ttu-id="c62c7-130">Configure reglas y límites de financiación para cada trabajador, artículo, categoría, grupo de categorías y tipos de transacción (o para todos los tipos de transacción).</span><span class="sxs-lookup"><span data-stu-id="c62c7-130">Configure funding rules and funding limits for each worker, item, category, category group, and transaction type (or for all transaction types).</span></span>
-   <span data-ttu-id="c62c7-131">Seleccione fechas de inicio y fin opcionales para definir el período en que es válida la regla de financiación.</span><span class="sxs-lookup"><span data-stu-id="c62c7-131">Select optional start and end dates to define the period when each funding rule is valid.</span></span>
-   <span data-ttu-id="c62c7-132">Especifique el porcentaje del que es responsable cada fuente de financiación.</span><span class="sxs-lookup"><span data-stu-id="c62c7-132">Specify the percentage that each funding source is responsible for.</span></span>
-   <span data-ttu-id="c62c7-133">Indique la fuente de financiación responsable de las diferencias de redondeo causadas por los cálculos de asignación de financiación.</span><span class="sxs-lookup"><span data-stu-id="c62c7-133">Specify which funding source is responsible for rounding differences that are caused by funding allocation calculations.</span></span>
-   <span data-ttu-id="c62c7-134">Configure reglas que determinen cómo se facturan los costes de proyecto a clientes externos y se cobran a organizaciones internas.</span><span class="sxs-lookup"><span data-stu-id="c62c7-134">Set up rules that determine how project costs are invoiced to external customers and charged to internal organizations.</span></span>
-   <span data-ttu-id="c62c7-135">Registre las transacciones en una cuenta de financiación en espera hasta que pueda obtener financiación adicional o hasta que decida asumir los costes internamente.</span><span class="sxs-lookup"><span data-stu-id="c62c7-135">Record transactions in an on-hold funding account until additional funding can be obtained, or until you decide to bear the costs internally.</span></span>

<span data-ttu-id="c62c7-136">Para determinar el grupo de impuestos que se asociará a una transacción, se busca el proyecto para una asignación de grupos de impuestos.</span><span class="sxs-lookup"><span data-stu-id="c62c7-136">To determine which tax group to associate with a transaction, the project is searched for a tax group assignment.</span></span> <span data-ttu-id="c62c7-137">Si no se han realizado asignaciones de grupos de impuestos a nivel de proyecto, se busca el contrato del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-137">If no tax group assignment has been made at the project level, the project contract is searched.</span></span>

### <a name="example-multiple-funding-sources-simple"></a><span data-ttu-id="c62c7-138">Ejemplo: Varias fuentes de financiación (simple)</span><span class="sxs-lookup"><span data-stu-id="c62c7-138">Example: Multiple funding sources (simple)</span></span>

<span data-ttu-id="c62c7-139">En la siguiente tabla encontrará escenarios para la administración de asignación de financiación entre fuentes de financiación múltiples.</span><span class="sxs-lookup"><span data-stu-id="c62c7-139">The following table provides scenarios for managing funding allocation among multiple funding sources.</span></span> <span data-ttu-id="c62c7-140">Estos escenarios se basan en las siguientes suposiciones:</span><span class="sxs-lookup"><span data-stu-id="c62c7-140">These scenarios are based on the following assumptions:</span></span>

-   <span data-ttu-id="c62c7-141">La configuración de prioridad se factoriza en la asignación de fondos antes de que se apliquen otros criterios de reglas de financiación.</span><span class="sxs-lookup"><span data-stu-id="c62c7-141">Priority settings are factored into the allocation of funds before other funding rule criteria are applied.</span></span>
-   <span data-ttu-id="c62c7-142">No se ha especificado ningún intervalo de fechas para definir el periodo d en que la regla de financiación es válida.</span><span class="sxs-lookup"><span data-stu-id="c62c7-142">No date range has been specified to define the period d when the funding rule is valid.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c62c7-143"><strong>Situación</strong></span><span class="sxs-lookup"><span data-stu-id="c62c7-143"><strong>Scenario</strong></span></span></td>
<td><span data-ttu-id="c62c7-144"><strong>Fuente de financiación </strong></span><span class="sxs-lookup"><span data-stu-id="c62c7-144"><strong>Funding source</strong></span></span></td>
<td><span data-ttu-id="c62c7-145"><strong>Porcentaje de asignación </strong></span><span class="sxs-lookup"><span data-stu-id="c62c7-145"><strong>Allocation percentage</strong></span></span></td>
<td><span data-ttu-id="c62c7-146"><strong>Prioridad de asignación </strong></span><span class="sxs-lookup"><span data-stu-id="c62c7-146"><strong>Allocation priority</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c62c7-147">Desea asignar los costes a una fuente de financiación hasta que se agoten los fondos, asignar los costes a una segunda fuente de financiación hasta que se agoten los fondos y, por último, asignar los costes pendientes a una tercera fuente de financiación.</span><span class="sxs-lookup"><span data-stu-id="c62c7-147">You want to allocate costs to one funding source until its funds are exhausted, allocate costs to a second funding source until its funds are exhausted, and finally allocate the remaining costs to a third funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="c62c7-148">Fuente de financiación 1</span><span class="sxs-lookup"><span data-stu-id="c62c7-148">Funding　source　1</span></span></li>
<li><span data-ttu-id="c62c7-149">Fuente de financiación 2</span><span class="sxs-lookup"><span data-stu-id="c62c7-149">Funding　source　2</span></span></li>
<li><span data-ttu-id="c62c7-150">Fuente de financiación 3</span><span class="sxs-lookup"><span data-stu-id="c62c7-150">Funding　source　3</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="c62c7-151">100 %</span><span class="sxs-lookup"><span data-stu-id="c62c7-151">100%</span></span></li>
<li><span data-ttu-id="c62c7-152">100 %</span><span class="sxs-lookup"><span data-stu-id="c62c7-152">100%</span></span></li>
<li><span data-ttu-id="c62c7-153">100 %</span><span class="sxs-lookup"><span data-stu-id="c62c7-153">100%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="c62c7-154">1</span><span class="sxs-lookup"><span data-stu-id="c62c7-154">1</span></span></li>
<li><span data-ttu-id="c62c7-155">2</span><span class="sxs-lookup"><span data-stu-id="c62c7-155">2</span></span></li>
<li><span data-ttu-id="c62c7-156">3</span><span class="sxs-lookup"><span data-stu-id="c62c7-156">3</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c62c7-157">Desea asignar el 75% de los costes a una fuente de financiación y el 25% a una segunda fuente de financiación.</span><span class="sxs-lookup"><span data-stu-id="c62c7-157">You want to allocate 75 percent of costs to one funding source and 25 percent to a second funding source.</span></span> <span data-ttu-id="c62c7-158">Cuando cualquiera de esas fuentes de financiación se agote, desea pagar los costes pendientes de una tercera fuente de financiación.</span><span class="sxs-lookup"><span data-stu-id="c62c7-158">When either of those funding sources is exhausted, you want to pay the remaining costs from a third funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="c62c7-159">Fuente de financiación 1</span><span class="sxs-lookup"><span data-stu-id="c62c7-159">Funding　source　1</span></span></li>
<li><span data-ttu-id="c62c7-160">Fuente de financiación 2</span><span class="sxs-lookup"><span data-stu-id="c62c7-160">Funding　source　2</span></span></li>
<li><span data-ttu-id="c62c7-161">Fuente de financiación 3</span><span class="sxs-lookup"><span data-stu-id="c62c7-161">Funding　source　3</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="c62c7-162">75 %</span><span class="sxs-lookup"><span data-stu-id="c62c7-162">75%</span></span></li>
<li><span data-ttu-id="c62c7-163">25 %</span><span class="sxs-lookup"><span data-stu-id="c62c7-163">25%</span></span></li>
<li><span data-ttu-id="c62c7-164">100 %</span><span class="sxs-lookup"><span data-stu-id="c62c7-164">100%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="c62c7-165">1</span><span class="sxs-lookup"><span data-stu-id="c62c7-165">1</span></span></li>
<li><span data-ttu-id="c62c7-166">1</span><span class="sxs-lookup"><span data-stu-id="c62c7-166">1</span></span></li>
<li><span data-ttu-id="c62c7-167">2</span><span class="sxs-lookup"><span data-stu-id="c62c7-167">2</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c62c7-168">Desea asignar el 75% de los costes a una fuente de financiación y el 25% a una segunda fuente de financiación.</span><span class="sxs-lookup"><span data-stu-id="c62c7-168">You want to allocate 75 percent of costs to one funding source and 25 percent to a second funding source.</span></span> <span data-ttu-id="c62c7-169">Cuando se agote cualquiera de esas fuentes de financiación, desea dividir los costes pendientes entre una tercera y una cuarta fuente de financiación.</span><span class="sxs-lookup"><span data-stu-id="c62c7-169">When either of those funding sources is exhausted, you want to split the remaining costs between a third funding source and a fourth funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="c62c7-170">Fuente de financiación 1</span><span class="sxs-lookup"><span data-stu-id="c62c7-170">Funding　source　1</span></span></li>
<li><span data-ttu-id="c62c7-171">Fuente de financiación 2</span><span class="sxs-lookup"><span data-stu-id="c62c7-171">Funding　source　2</span></span></li>
<li><span data-ttu-id="c62c7-172">Fuente de financiación 3</span><span class="sxs-lookup"><span data-stu-id="c62c7-172">Funding　source　3</span></span></li>
<li><span data-ttu-id="c62c7-173">Fuente de financiación 4</span><span class="sxs-lookup"><span data-stu-id="c62c7-173">Funding　source　4</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="c62c7-174">75 %</span><span class="sxs-lookup"><span data-stu-id="c62c7-174">75%</span></span></li>
<li><span data-ttu-id="c62c7-175">25%</span><span class="sxs-lookup"><span data-stu-id="c62c7-175">25%</span></span></li>
<li><span data-ttu-id="c62c7-176">50 %</span><span class="sxs-lookup"><span data-stu-id="c62c7-176">50%</span></span></li>
<li><span data-ttu-id="c62c7-177">50 %</span><span class="sxs-lookup"><span data-stu-id="c62c7-177">50%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="c62c7-178">1</span><span class="sxs-lookup"><span data-stu-id="c62c7-178">1</span></span></li>
<li><span data-ttu-id="c62c7-179">1</span><span class="sxs-lookup"><span data-stu-id="c62c7-179">1</span></span></li>
<li><span data-ttu-id="c62c7-180">2</span><span class="sxs-lookup"><span data-stu-id="c62c7-180">2</span></span></li>
<li><span data-ttu-id="c62c7-181">2</span><span class="sxs-lookup"><span data-stu-id="c62c7-181">2</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c62c7-182">Desea asignar el primer 25% de costes a una fuente de financiación y el resto a otra segunda fuente de financiación.</span><span class="sxs-lookup"><span data-stu-id="c62c7-182">You want to allocate the first 25 percent of costs to one funding source and the rest to a second funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="c62c7-183">Fuente de financiación 1</span><span class="sxs-lookup"><span data-stu-id="c62c7-183">Funding　source　1</span></span></li>
<li><span data-ttu-id="c62c7-184">Fuente de financiación 2</span><span class="sxs-lookup"><span data-stu-id="c62c7-184">Funding　source　2</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="c62c7-185">25 %</span><span class="sxs-lookup"><span data-stu-id="c62c7-185">25%</span></span></li>
<li><span data-ttu-id="c62c7-186">100 %</span><span class="sxs-lookup"><span data-stu-id="c62c7-186">100%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="c62c7-187">1</span><span class="sxs-lookup"><span data-stu-id="c62c7-187">1</span></span></li>
<li><span data-ttu-id="c62c7-188">2</span><span class="sxs-lookup"><span data-stu-id="c62c7-188">2</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="example-multiple-funding-sources-complex"></a><span data-ttu-id="c62c7-189">Ejemplo: Varias fuentes de financiación (complejo)</span><span class="sxs-lookup"><span data-stu-id="c62c7-189">Example: Multiple funding sources (complex)</span></span>

<span data-ttu-id="c62c7-190">Dispone de tres fuentes de financiación que desea usar en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="c62c7-190">You have three funding sources that you want to use in the following order:</span></span>

1.  <span data-ttu-id="c62c7-191">Use la fuente de financiación 2 y la fuente de financiación 3 de manera igualitaria hasta que se agote la fuente de financiación 2.</span><span class="sxs-lookup"><span data-stu-id="c62c7-191">Use funding source 2 and funding source 3 equally until funding source 2 is exhausted.</span></span>
2.  <span data-ttu-id="c62c7-192">Continúe usando la fuente de financiación 3 hasta que se agote.</span><span class="sxs-lookup"><span data-stu-id="c62c7-192">Continue to use funding source 3 until it is exhausted.</span></span>
3.  <span data-ttu-id="c62c7-193">Use la fuente de financiación 1 hasta que se agote la fuente de financiación 3.</span><span class="sxs-lookup"><span data-stu-id="c62c7-193">Use funding source 1 after funding source 3 is exhausted.</span></span>

<span data-ttu-id="c62c7-194">Para cumplir con este objetivo, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c62c7-194">To accomplish this goal, you must do the following:</span></span>

-   <span data-ttu-id="c62c7-195">Configure los límites de financiación para la fuente de financiación 2 y la fuente de financiación 3, para los importes respectivos.</span><span class="sxs-lookup"><span data-stu-id="c62c7-195">Set up funding limits for funding source 2 and funding source 3, for their respective amounts.</span></span>
-   <span data-ttu-id="c62c7-196">Cree las siguientes reglas de financiación:</span><span class="sxs-lookup"><span data-stu-id="c62c7-196">Create the following funding rules:</span></span>
    -   <span data-ttu-id="c62c7-197">Regla 1 (prioridad 1): asigne el 50% de las transacciones a la fuente de financiación 2 y el 50% a la fuente de financiación 3.</span><span class="sxs-lookup"><span data-stu-id="c62c7-197">Rule 1 (Priority 1): Allocate 50 percent of transactions to funding source 2 and 50 percent to funding source 3.</span></span>
    -   <span data-ttu-id="c62c7-198">Regla 2 (prioridad 2): asigne el 100% de las transacciones a la fuente de financiación 3.</span><span class="sxs-lookup"><span data-stu-id="c62c7-198">Rule 2 (Priority 2): Allocate 100 percent of transactions to funding source 3.</span></span>
    -   <span data-ttu-id="c62c7-199">Regla 3 (prioridad 3): asigne el 100% de las transacciones a la fuente de financiación 1.</span><span class="sxs-lookup"><span data-stu-id="c62c7-199">Rule 3 (Priority 3): Allocate 100 percent of transactions to funding source 1.</span></span>

<span data-ttu-id="c62c7-200">Esta configuración funciona porque las transacciones se comprueban comparándolos con las reglas y los límites para determinar si cualquiera de ellos se aplican a la transacción.</span><span class="sxs-lookup"><span data-stu-id="c62c7-200">This setup works because transactions are checked against rules and limits to determine whether any of them apply to the transaction.</span></span> <span data-ttu-id="c62c7-201">Si no hay ninguna regla ni ningún límite específico que se aplique a la transacción, la regla Todas las transacciones se aplicará.</span><span class="sxs-lookup"><span data-stu-id="c62c7-201">If no specific rules or limits apply to the transaction, the All transactions rule applies.</span></span> <span data-ttu-id="c62c7-202">La regla Todas las transacciones coincide con todas las transacciones.</span><span class="sxs-lookup"><span data-stu-id="c62c7-202">The All transactions rule matches all transactions.</span></span> 

<span data-ttu-id="c62c7-203">Si se encuentra una regla que coincida con una transacción, se aplicará primero el porcentaje que se ha asignado en dicha regla, pero solo después de que se comprueben las coincidencias comparándolas con los límites configurados.</span><span class="sxs-lookup"><span data-stu-id="c62c7-203">If a rule is found that matches a transaction, the percentage that has been allocated in that rule is applied first, but only after the matches are checked against any limits that have been set up.</span></span> <span data-ttu-id="c62c7-204">Si se ha alcanzado un límite, y se han agotado los fondos de una fuente de financiación, se descarta la regla de financiación que está asociada con el límite de financiación, y el programa comprobará la siguiente regla que se aplicará.</span><span class="sxs-lookup"><span data-stu-id="c62c7-204">If a limit has been met, and a funding source’s funds are exhausted, the funding rule that is associated with the funding limit is disregarded, and the program checks for the next rule that applies.</span></span> 

<span data-ttu-id="c62c7-205">En algunos casos, solo se puede asignar una transacción bajo una regla.</span><span class="sxs-lookup"><span data-stu-id="c62c7-205">In some cases, only part of a transaction can be allocated under a rule.</span></span> <span data-ttu-id="c62c7-206">Esto puede suceder porque se ha alcanzado un límite cuando se asigna la transacción.</span><span class="sxs-lookup"><span data-stu-id="c62c7-206">This might happen because a limit is reached when the transaction is allocated.</span></span> <span data-ttu-id="c62c7-207">En este caso, solo se asigna una cantidad determinada según dicha regla, como el 50% a cada fuente de financiación.</span><span class="sxs-lookup"><span data-stu-id="c62c7-207">In this case, only a certain amount is allocated according to that rule, such as 50 percent to each funding source.</span></span> <span data-ttu-id="c62c7-208">Este es el caso de la regla 1, que se describe anteriormente en esta sección.</span><span class="sxs-lookup"><span data-stu-id="c62c7-208">This is the case in rule 1, which is described earlier in this section.</span></span> <span data-ttu-id="c62c7-209">El resto se asignará según la siguiente regla de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="c62c7-209">The remainder is allocated according to the next rule in the sequence.</span></span> 

<span data-ttu-id="c62c7-210">En la siguiente tabla se examina este escenario con más detalle.</span><span class="sxs-lookup"><span data-stu-id="c62c7-210">The following table examines this scenario in more detail.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c62c7-211"><strong>Foco </strong></span><span class="sxs-lookup"><span data-stu-id="c62c7-211"><strong>Focus</strong></span></span></td>
<td><span data-ttu-id="c62c7-212"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="c62c7-212"><strong>Details</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c62c7-213">Reglas de financiación</span><span class="sxs-lookup"><span data-stu-id="c62c7-213">Funding rules</span></span></td>
<td><ul>
<li><span data-ttu-id="c62c7-214">Regla 1 (prioridad 1): todas las transacciones.</span><span class="sxs-lookup"><span data-stu-id="c62c7-214">Rule 1 (Priority 1): All transactions.</span></span> <span data-ttu-id="c62c7-215">Asigne la fuente de financiación 2 al 50% y la fuente de financiación 3 al 50%.</span><span class="sxs-lookup"><span data-stu-id="c62c7-215">Allocate funding source 2 at 50% and funding source 3 at 50%.</span></span></li>
<li><span data-ttu-id="c62c7-216">Regla 2 (prioridad 2): todas las transacciones.</span><span class="sxs-lookup"><span data-stu-id="c62c7-216">Rule 2 (Priority 2): All transactions.</span></span> <span data-ttu-id="c62c7-217">Asigne la fuente de financiación 3 al 100%.</span><span class="sxs-lookup"><span data-stu-id="c62c7-217">Allocate funding source 3 at 100%.</span></span></li>
<li><span data-ttu-id="c62c7-218">Regla 3 (prioridad 2): todas las transacciones.</span><span class="sxs-lookup"><span data-stu-id="c62c7-218">Rule 3 (Priority 2): All transactions.</span></span> <span data-ttu-id="c62c7-219">Asigne la fuente de financiación 1 al 100%.</span><span class="sxs-lookup"><span data-stu-id="c62c7-219">Allocate funding source 1 at 100%.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c62c7-220">Límite de financiación</span><span class="sxs-lookup"><span data-stu-id="c62c7-220">Funding limits</span></span></td>
<td><ul>
<li><span data-ttu-id="c62c7-221">Límite de la fuente de financiación 1 = 10.000,00</span><span class="sxs-lookup"><span data-stu-id="c62c7-221">Funding source 1 limit = 10,000.00</span></span></li>
<li><span data-ttu-id="c62c7-222">Límite de la fuente de financiación 2 = 500,00</span><span class="sxs-lookup"><span data-stu-id="c62c7-222">Funding source 2 limit = 500.00</span></span></li>
<li><span data-ttu-id="c62c7-223">Límite de la fuente de financiación 3 = 750,00</span><span class="sxs-lookup"><span data-stu-id="c62c7-223">Funding source 3 limit = 750.00</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c62c7-224">Transacción 1</span><span class="sxs-lookup"><span data-stu-id="c62c7-224">Transaction 1</span></span></td>
<td><span data-ttu-id="c62c7-225"><strong>Importe de la transacción:</strong> 100,00<strong> Financiación:</strong> la transacción se paga según la regla 1 solo, porque la transacción se paga en su totalidad después de que se aplique la regla 1.</span><span class="sxs-lookup"><span data-stu-id="c62c7-225"><strong>Transaction amount:</strong> 100.00<strong>Funding:</strong> The transaction is paid according to rule 1 only, because the transaction is fully paid after rule 1 is applied.</span></span> <span data-ttu-id="c62c7-226">La transacción se financia de manera igualitaria entre la fuente de financiación 2 y la fuente de financiación 3.</span><span class="sxs-lookup"><span data-stu-id="c62c7-226">The transaction is funded equally between funding source 2 and funding source 3.</span></span>
<ul>
<li><span data-ttu-id="c62c7-227">Fuente de financiación 2: 50,00</span><span class="sxs-lookup"><span data-stu-id="c62c7-227">Funding source 2: 50.00</span></span></li>
<li><span data-ttu-id="c62c7-228">Fuente de financiación 3: 50,00</span><span class="sxs-lookup"><span data-stu-id="c62c7-228">Funding source 3: 50.00</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c62c7-229">Transacción 2</span><span class="sxs-lookup"><span data-stu-id="c62c7-229">Transaction 2</span></span></td>
<td><span data-ttu-id="c62c7-230"><strong>Importe de la transacción:</strong> 5,000.00<strong>Financiación:</strong> la transacción se paga en función de las tres reglas.</span><span class="sxs-lookup"><span data-stu-id="c62c7-230"><strong>Transaction amount:</strong> 5,000.00<strong>Funding:</strong> The transaction is paid according to all three rules.</span></span> <span data-ttu-id="c62c7-231"><strong>Regla 1</strong>
</span><span class="sxs-lookup"><span data-stu-id="c62c7-231"><strong>Rule 1</strong>
</span></span><ul>
<li><span data-ttu-id="c62c7-232">Fuente de financiación 2: 450,00</span><span class="sxs-lookup"><span data-stu-id="c62c7-232">Funding source 2: 450.00</span></span></li>
<li><span data-ttu-id="c62c7-233">Fuente de financiación 3: 450,00</span><span class="sxs-lookup"><span data-stu-id="c62c7-233">Funding source 3: 450.00</span></span></li>
</ul><span data-ttu-id="c62c7-234">
<strong>Regla 2</strong>
</span><span class="sxs-lookup"><span data-stu-id="c62c7-234">
<strong>Rule 2</strong>
</span></span><ul>
<li><span data-ttu-id="c62c7-235">Fuente de financiación 3: 250,00 (= 750,00 – 50,00 – 450,00)</span><span class="sxs-lookup"><span data-stu-id="c62c7-235">Funding source 3: 250.00 (= 750.00 – 50.00 – 450.00)</span></span></li>
</ul><span data-ttu-id="c62c7-236">
<strong>Regla 3</strong>
</span><span class="sxs-lookup"><span data-stu-id="c62c7-236">
<strong>Rule 3</strong>
</span></span><ul>
<li><span data-ttu-id="c62c7-237">Fuente de financiación 1: 3850,00 (= 5000,00 – 450,00 – 450,00 – 250,00)</span><span class="sxs-lookup"><span data-stu-id="c62c7-237">Funding source 1: 3,850.00 (= 5,000.00 – 450.00 – 450.00 – 250.00)</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c62c7-238">Fondos totales que se distribuyen para cada fuente de financiación</span><span class="sxs-lookup"><span data-stu-id="c62c7-238">Total funds that are distributed for each funding source</span></span></td>
<td><ul>
<li><span data-ttu-id="c62c7-239">Fuente de financiación 1: 3.850,00</span><span class="sxs-lookup"><span data-stu-id="c62c7-239">Funding source 1: 3,850.00</span></span></li>
<li><span data-ttu-id="c62c7-240">Fuente de financiación 2: 500,00</span><span class="sxs-lookup"><span data-stu-id="c62c7-240">Funding source 2: 500.00</span></span></li>
<li><span data-ttu-id="c62c7-241">Fuente de financiación 3: 750,00</span><span class="sxs-lookup"><span data-stu-id="c62c7-241">Funding source 3: 750.00</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="billing-rules"></a><span data-ttu-id="c62c7-242">Reglas de facturación</span><span class="sxs-lookup"><span data-stu-id="c62c7-242">Billing rules</span></span>
<span data-ttu-id="c62c7-243">En el contrato de un proyecto que se negocia con el cliente, se define cómo y cuándo se podrá facturar al cliente por el trabajo realizado en un proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-243">When you negotiate a project contract with a customer, you define how and when you can invoice the customer for work on a project.</span></span> <span data-ttu-id="c62c7-244">Una vez haya configurado el contrato de proyecto y el proyecto, podrá configurar las reglas de facturación para dicho proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-244">After you set up the project contract and the project, you can set up billing rules for the project.</span></span> <span data-ttu-id="c62c7-245">Las reglas de facturación se basan en los términos de proyecto que se especifican en el contrato de proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-245">Billing rules are based on the project terms that are specified in the project contract.</span></span> <span data-ttu-id="c62c7-246">Las reglas de facturación que puede crear dependen de las condiciones del contrato de proyecto y del tipo de proyecto, tal como el tiempo y el material o el precio fijo, que se asocia a la regla de facturación.</span><span class="sxs-lookup"><span data-stu-id="c62c7-246">The billing rules that you can create depend on the terms of the project contract and the project type, such as Time and material or Fixed-price, that you associate with the billing rule.</span></span> <span data-ttu-id="c62c7-247">Puede crear más de una regla de facturación para un contrato de proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-247">You can create more than one billing rule for a project contract.</span></span> <span data-ttu-id="c62c7-248">También puede asignar una regla de facturación a varios proyectos asociados al mismo contrato de proyecto y tener condiciones similares de facturación.</span><span class="sxs-lookup"><span data-stu-id="c62c7-248">You can also assign a billing rule to multiple projects that are associated with the same project contract and have similar billing terms.</span></span> 

<span data-ttu-id="c62c7-249">Puede configurar los tipos de reglas de facturación siguientes:</span><span class="sxs-lookup"><span data-stu-id="c62c7-249">You can set up the following types of billing rules:</span></span>

-   <span data-ttu-id="c62c7-250">**Unidad de entrega**: facturar al cliente una vez completada una unidad de entrega.</span><span class="sxs-lookup"><span data-stu-id="c62c7-250">**Unit of delivery** – Invoice a customer when you complete a unit of delivery.</span></span> <span data-ttu-id="c62c7-251">Defina las unidades de entrega en el contrato.</span><span class="sxs-lookup"><span data-stu-id="c62c7-251">You define the units of delivery in the contract.</span></span>
-   <span data-ttu-id="c62c7-252">**Progreso**: facturar al cliente una vez completado un porcentaje determinado del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-252">**Progress** – Invoice a customer when you complete a specified percentage of the project.</span></span> <span data-ttu-id="c62c7-253">Puede configurar una regla de facturación para calcular automáticamente el porcentaje de trabajo completado, o puede calcular manualmente el porcentaje de trabajo completado y el importe que se facturará al cliente.</span><span class="sxs-lookup"><span data-stu-id="c62c7-253">You can set up a billing rule to automatically calculate the percentage of work completed, or you can manually calculate the percentage of work completed and the amount to invoice the customer.</span></span>
-   <span data-ttu-id="c62c7-254">**Hito**: facturar a un cliente el importe completo de un hito de proyecto una vez se haya alcanzado el hito.</span><span class="sxs-lookup"><span data-stu-id="c62c7-254">**Milestone** – Invoice a customer for the full amount of a project milestone when the milestone is reached.</span></span>
-   <span data-ttu-id="c62c7-255">**Cuota**: facturar a un cliente por servicios más una cuota administrativa, que es normalmente un porcentaje del coste de los servicios.</span><span class="sxs-lookup"><span data-stu-id="c62c7-255">**Fee** – Invoice a customer for your services plus a management fee, which is typically a percentage of the cost of services.</span></span>
-   <span data-ttu-id="c62c7-256">**Tiempo y material**: facturar a un cliente el valor del tiempo y de los materiales que se usan en un proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-256">**Time and material** – Invoice a customer for the value of time and materials that are used on a project.</span></span>

<span data-ttu-id="c62c7-257">Para todos los tipos de reglas de facturación, puede especificar un porcentaje de retención que se deduce de las facturas de cliente hasta que el proyecto alcance una etapa acordada.</span><span class="sxs-lookup"><span data-stu-id="c62c7-257">For all types of billing rules, you can specify a retention percentage that is deducted from customer invoices until a project reaches an agreed-upon stage.</span></span> <span data-ttu-id="c62c7-258">El porcentaje de retención del pago se especifica en el contrato de proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-258">The payment retention percentage is specified in the project contract.</span></span> <span data-ttu-id="c62c7-259">El importe se calcula basándose en, y se resta del, el valor total de las líneas en una factura de cliente.</span><span class="sxs-lookup"><span data-stu-id="c62c7-259">The amount is calculated based on, and subtracted from, the total value of the lines in a customer invoice.</span></span> 

<span data-ttu-id="c62c7-260">Para las reglas de facturación **Tiempo y material** y **Progreso**, puede asignar categorías imputables.</span><span class="sxs-lookup"><span data-stu-id="c62c7-260">For **Time and material** and **Progress** billing rules, you can assign chargeable categories.</span></span> <span data-ttu-id="c62c7-261">Las categorías imputables indican las transacciones que se deben incluir en las facturas de cliente.</span><span class="sxs-lookup"><span data-stu-id="c62c7-261">Chargeable categories indicate the transactions that should be included in customer invoices.</span></span> 

<span data-ttu-id="c62c7-262">Cuando esté preparado para facturar al cliente, el importe que se facturará del proyecto se calcula en función de las reglas de facturación y se genera una propuesta de factura de proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-262">When you are ready to invoice the customer, the amount to invoice for the project is calculated based on the billing rules, and a project invoice proposal is generated.</span></span> 

<span data-ttu-id="c62c7-263">En las secciones siguientes se proporcionan ejemplos que muestran cómo configurar y gestionar reglas de facturación para un proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-263">The following sections provide examples that show how to set up and manage billing rules for a project.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-the-number-of-units-delivered"></a><span data-ttu-id="c62c7-264">Ejemplo: Creación de una regla de facturación que se basa en el número de unidades entregadas</span><span class="sxs-lookup"><span data-stu-id="c62c7-264">Example: Create a billing rule that is based on the number of units delivered</span></span>

<span data-ttu-id="c62c7-265">Su organización llega a un acuerdo para proporcionar un total de cinco sesiones de formación a los empleados de un cliente a un coste de 10.000 por sesión de formación.</span><span class="sxs-lookup"><span data-stu-id="c62c7-265">Your organization enters into an agreement to provide a total of five training sessions to a customer’s employees at a cost of 10,000 per training session.</span></span> <span data-ttu-id="c62c7-266">Su organización factura al cliente tras cada sesión de formación.</span><span class="sxs-lookup"><span data-stu-id="c62c7-266">You invoice the customer after each training session.</span></span> 

<span data-ttu-id="c62c7-267">Al configurar las reglas de facturación para el contrato, usa los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="c62c7-267">When you set up the billing rules for the contract, you use the following values:</span></span>

-   <span data-ttu-id="c62c7-268">La unidad de entrega es una sesión de formación.</span><span class="sxs-lookup"><span data-stu-id="c62c7-268">The unit of delivery is one training session.</span></span>
-   <span data-ttu-id="c62c7-269">El precio unitario es de 10.000 USD por sesión.</span><span class="sxs-lookup"><span data-stu-id="c62c7-269">The unit price is 10,000 per training session.</span></span>
-   <span data-ttu-id="c62c7-270">El número total de unidades es de cinco sesiones de formación.</span><span class="sxs-lookup"><span data-stu-id="c62c7-270">The total number of units is five training sessions.</span></span>

<span data-ttu-id="c62c7-271">Una vez completada una sesión de formación, puede crear una factura de 10.000 € por la primera unidad entregada y enviar la factura al cliente.</span><span class="sxs-lookup"><span data-stu-id="c62c7-271">When you have completed one training session, you can create an invoice for 10,000, for the first unit that was delivered, and send the invoice to the customer.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-manual-calculation"></a><span data-ttu-id="c62c7-272">Ejemplo: Creación de una regla de facturación que se basa en un porcentaje específico de finalización del proyecto (cálculo manual)</span><span class="sxs-lookup"><span data-stu-id="c62c7-272">Example: Create a billing rule that is based on a specified percentage of project completion (manual calculation)</span></span>

<span data-ttu-id="c62c7-273">Su organización, una empresa de asesoría de software, llega a un acuerdo con un cliente para encargarse de parte del desarrollo de un producto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-273">Your organization, a software consulting firm, enters into an agreement with a customer to develop part of a product that the customer is developing.</span></span> <span data-ttu-id="c62c7-274">Su organización acepta entregar el código de software durante un período de seis meses.</span><span class="sxs-lookup"><span data-stu-id="c62c7-274">Your organization agrees to deliver the software code over a period of six months.</span></span> <span data-ttu-id="c62c7-275">El cliente acepta pagar a su organización un total de 100.000 USD por el trabajo.</span><span class="sxs-lookup"><span data-stu-id="c62c7-275">The customer agrees to pay your organization a total of 100,000 for the work.</span></span> <span data-ttu-id="c62c7-276">Puede crear una regla de facturación para facturar al cliente según el porcentaje de trabajo completado del proyecto según se especifica en el contrato.</span><span class="sxs-lookup"><span data-stu-id="c62c7-276">You create a billing rule to invoice the customer based on the percentage of work that is completed on the project, as specified in the contract.</span></span>

-   <span data-ttu-id="c62c7-277">Al final del primer mes, se reúne con el cliente para determinar el porcentaje de trabajo completado.</span><span class="sxs-lookup"><span data-stu-id="c62c7-277">At the end of the first month, you meet with the customer to determine the percentage of work completed.</span></span> <span data-ttu-id="c62c7-278">Una vez que su empresa y el cliente revisen el proyecto, su empresa decide que el proyecto está completado en un 15 %.</span><span class="sxs-lookup"><span data-stu-id="c62c7-278">After you and the customer review the project, you decide that the project is 15 percent completed.</span></span>
-   <span data-ttu-id="c62c7-279">Crea una factura por 15.000 (15 % de 100.000) y se la envía al cliente.</span><span class="sxs-lookup"><span data-stu-id="c62c7-279">You create an invoice for 15,000 (15 percent of 100,000) and send it to the customer.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-automatic-calculation"></a><span data-ttu-id="c62c7-280">Ejemplo: Creación de una regla de facturación que se basa en un porcentaje específico de finalización del proyecto (cálculo automático)</span><span class="sxs-lookup"><span data-stu-id="c62c7-280">Example: Create a billing rule that is based on a specified percentage of project completion (automatic calculation)</span></span>

<span data-ttu-id="c62c7-281">Su organización, una empresa de desarrollo de software, acuerda desarrollar un paquete de contabilidad de nóminas para un cliente por 30.000.</span><span class="sxs-lookup"><span data-stu-id="c62c7-281">Your organization, a software development firm, agrees to develop a payroll accounting package for a customer for 30,000.</span></span> <span data-ttu-id="c62c7-282">El cliente acepta pagar a su organización según el porcentaje de trabajo completado.</span><span class="sxs-lookup"><span data-stu-id="c62c7-282">The customer agrees to pay your organization based on the percentage of work completed.</span></span> <span data-ttu-id="c62c7-283">Se estima que los costes del proyecto son de 20.000 USD.</span><span class="sxs-lookup"><span data-stu-id="c62c7-283">You estimate that the project costs are 20,000.</span></span> <span data-ttu-id="c62c7-284">El contrato del proyecto determina las categorías de trabajo para que su empresa usa en el proceso de facturación.</span><span class="sxs-lookup"><span data-stu-id="c62c7-284">The project contract specifies the categories of work that you use in the billing process.</span></span> <span data-ttu-id="c62c7-285">Se configuran reglas de facturación que calculan automáticamente los importes de las facturas por el porcentaje de trabajo completado en cada categoría.</span><span class="sxs-lookup"><span data-stu-id="c62c7-285">You set up billing rules that automatically calculate the invoice amounts for the percentage of work that is completed for each category.</span></span> <span data-ttu-id="c62c7-286">Configura un presupuesto para cada categoría:</span><span class="sxs-lookup"><span data-stu-id="c62c7-286">You set up a budget for each category:</span></span>

-   <span data-ttu-id="c62c7-287">**Desarrollo**: coste de 15.000 e ingresos de 20.000.</span><span class="sxs-lookup"><span data-stu-id="c62c7-287">**Development** – Cost of 15,000 and revenue of 20,000</span></span>
-   <span data-ttu-id="c62c7-288">**Instalación**: coste de 5.000 e ingresos de 10.000.</span><span class="sxs-lookup"><span data-stu-id="c62c7-288">**Installation** – Cost of 5,000 and revenue of 10,000</span></span>

<span data-ttu-id="c62c7-289">Al facturar al cliente por primera vez, el importe de la factura se calcula automáticamente según la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="c62c7-289">When you create a customer invoice for the first time, the invoice amount is automatically calculated based on the following information:</span></span>

-   <span data-ttu-id="c62c7-290">Después de un mes, el trabajador del proyecto envía una hoja de horas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-290">After a month, the worker on the project submits a timesheet for the project.</span></span> <span data-ttu-id="c62c7-291">El coste de las horas del trabajador es de 5.000 USD por el desarrollo y de 1.000 USD por la instalación.</span><span class="sxs-lookup"><span data-stu-id="c62c7-291">The cost of the worker’s hours is 5,000 for development and 1,000 for installation.</span></span> <span data-ttu-id="c62c7-292">El trabajo de desarrollo está completado en un 33 % (5.000 del coste real/15.000 del coste presupuestario) y el trabajo de instalación está completado en un 20 % (1.000 del coste real/5.000 USD del coste presupuestario).</span><span class="sxs-lookup"><span data-stu-id="c62c7-292">The development work is 33 percent completed (5,000 actual cost/15,000 budget cost), and the installation work is 20 percent completed (1,000 actual cost/5,000 budget cost).</span></span>
-   <span data-ttu-id="c62c7-293">El importe de la factura de 8.667 se calcula automáticamente (33 de 20.000 más el 20 por ciento de 10.000).</span><span class="sxs-lookup"><span data-stu-id="c62c7-293">The invoice amount of 8,667 is automatically calculated (33 percent of 20,000 + 20 percent of 10,000).</span></span>
-   <span data-ttu-id="c62c7-294">Crea una factura por 8.667 y se la envía al cliente.</span><span class="sxs-lookup"><span data-stu-id="c62c7-294">You create an invoice for 8,667 and send it to the customer.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-agreed-upon-milestones"></a><span data-ttu-id="c62c7-295">Ejemplo: Creación de una regla de facturación que se basa en hitos acordados</span><span class="sxs-lookup"><span data-stu-id="c62c7-295">Example: Create a billing rule that is based on agreed-upon milestones</span></span>

<span data-ttu-id="c62c7-296">Su organización, una empresa de asesoría administrativa, acuerda llevar a cabo una investigación de mercado para un producto de consumo que el cliente quiere vender.</span><span class="sxs-lookup"><span data-stu-id="c62c7-296">Your organization, a management consulting firm, agrees to conduct market research for a consumer product that the customer plans to sell.</span></span> <span data-ttu-id="c62c7-297">El cliente acepta usar sus servicios durante tres meses, comenzando en marzo, y acuerda pagar a su organización 50.000 USD.</span><span class="sxs-lookup"><span data-stu-id="c62c7-297">The customer agrees to use your services for a period of three months, starting in March, and agrees to pay your organization 50,000.</span></span> <span data-ttu-id="c62c7-298">El proyecto tiene tres hitos:</span><span class="sxs-lookup"><span data-stu-id="c62c7-298">The project has three milestones:</span></span>

-   <span data-ttu-id="c62c7-299">Hito 1: recopilar datos de consumidores, 31 de marzo</span><span class="sxs-lookup"><span data-stu-id="c62c7-299">Milestone 1: Collect consumer data – March 31</span></span>
-   <span data-ttu-id="c62c7-300">Hito 2: analizar datos de consumidores, 30 de abril</span><span class="sxs-lookup"><span data-stu-id="c62c7-300">Milestone 2: Analyze consumer data – April 30</span></span>
-   <span data-ttu-id="c62c7-301">Hito 3: presentar una propuesta de viabilidad del producto, 31 de mayo.</span><span class="sxs-lookup"><span data-stu-id="c62c7-301">Milestone 3: Present a product viability proposal – May 31</span></span>

<span data-ttu-id="c62c7-302">El cliente acepta pagar a su organización 10.000 por el primer hito y 20.000 por el segundo hito y 20.000 por el tercer hito.</span><span class="sxs-lookup"><span data-stu-id="c62c7-302">The customer agrees to pay your organization 10,000 for the first milestone, 20,000 for the second milestone, and 20,000 for the third milestone.</span></span> 

<span data-ttu-id="c62c7-303">Al configurar el contrato de proyecto, acepta facturar al cliente según los hitos completados.</span><span class="sxs-lookup"><span data-stu-id="c62c7-303">When you set up the project contract, you agree to bill the customer based on the milestone that has been completed.</span></span> <span data-ttu-id="c62c7-304">La configuración de las reglas de facturación incluye los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c62c7-304">The billing rule setup includes the following steps:</span></span>

-   <span data-ttu-id="c62c7-305">Definir los hitos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-305">Define the project milestones.</span></span>
-   <span data-ttu-id="c62c7-306">Defina el importe que se debe facturar al cliente cuando se complete cada hito.</span><span class="sxs-lookup"><span data-stu-id="c62c7-306">Define the amount to invoice the customer when each milestone is completed.</span></span>

<span data-ttu-id="c62c7-307">Al completar el primer hito el 31 de marzo, márquelo como completado y, a continuación, cree una factura por 10.000 y envíela al cliente.</span><span class="sxs-lookup"><span data-stu-id="c62c7-307">When the first milestone is completed on March 31, you mark the milestone as completed, and then create an invoice for 10,000 and send it to the customer.</span></span> <span data-ttu-id="c62c7-308">No se puede crear una factura para un hito hasta que haya marcado el hito como completado.</span><span class="sxs-lookup"><span data-stu-id="c62c7-308">You can’t create an invoice for a milestone until you have marked the milestone as completed.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-services-plus-a-management-fee"></a><span data-ttu-id="c62c7-309">Ejemplo: Creación de una regla de facturación basada en servicios más una cuota administrativa</span><span class="sxs-lookup"><span data-stu-id="c62c7-309">Example: Create a billing rule that is based on services plus a management fee</span></span>

<span data-ttu-id="c62c7-310">Su organización, una empresa de asesoría administrativa, acuerda llevar a cabo una investigación de mercado para evaluar la viabilidad que el cliente, una empresa minorista, está desarrollando.</span><span class="sxs-lookup"><span data-stu-id="c62c7-310">Your organization, a management consulting firm, agrees to conduct market research to evaluate the viability of a product that the customer, a retail company, is developing.</span></span> <span data-ttu-id="c62c7-311">Las condiciones del acuerdo especifican que proporcionará los servicios de sus tres mejores asesores administrativos, que llevará a cabo la investigación según tiempo y material.</span><span class="sxs-lookup"><span data-stu-id="c62c7-311">The terms of the agreement specify that you will provide the services of your top three management consultants, who will conduct the research on a time-and-materials basis.</span></span> <span data-ttu-id="c62c7-312">El cliente acepta pagar 100 USD por hora por los asesores, más un 10% adicional de cuota administrativa por las horas de asesoría que se cargan al proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-312">The customer agrees to pay 100 per hour, plus a 10 percent management fee for the consulting hours that are charged to the project.</span></span> 

<span data-ttu-id="c62c7-313">Cuando configure el contrato de proyecto, cree una regla de facturación para agregar un 10% en concepto de cuota de administración por las horas de asesoría que se carguen al proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-313">When you set up the project contract, create a billing rule to add a 10 percent management fee to the consulting hours that are charged to the project.</span></span> 

<span data-ttu-id="c62c7-314">Al crear una factura para el cliente, se factura un 10% de cuota administrativa más el coste de las horas de asesoría.</span><span class="sxs-lookup"><span data-stu-id="c62c7-314">When you create an invoice for the customer, the customer is billed a 10 percent management fee plus the cost of the consulting hours.</span></span> <span data-ttu-id="c62c7-315">Por ejemplo, si los tres asesores trabajaron un total de 200 horas en el proyecto, se crea una factura por 22.000 basada en el siguiente cálculo:</span><span class="sxs-lookup"><span data-stu-id="c62c7-315">For example, if the three consultants worked a total of 200 hours on the project, an invoice for 22,000 is created based on the following calculation:</span></span>

-   <span data-ttu-id="c62c7-316">200 horas a 100 USD por hora = 20.000 USD</span><span class="sxs-lookup"><span data-stu-id="c62c7-316">200 hours at 100 per hour = 20,000</span></span>
-   <span data-ttu-id="c62c7-317">Comisión de gestión del 10 por ciento = 2.000</span><span class="sxs-lookup"><span data-stu-id="c62c7-317">10 percent management fee = 2,000</span></span>
-   <span data-ttu-id="c62c7-318">Importe total de la factura = 22.000</span><span class="sxs-lookup"><span data-stu-id="c62c7-318">Total invoice amount = 22,000</span></span>

<span data-ttu-id="c62c7-319">Si las cuotas son gravables a un cliente y selecciona un grupo de impuestos en el contrato del proyecto, el grupo de impuestos se especificará automáticamente en una regla de facturación de cuotas.</span><span class="sxs-lookup"><span data-stu-id="c62c7-319">If fees are taxable to a customer, and you select a sales tax group in the project contract, the sales tax group is automatically entered in a billing rule for fees.</span></span>

### <a name="example-create-a-billing-rule-for-the-value-of-time-and-materials"></a><span data-ttu-id="c62c7-320">Ejemplo: Creación de una regla de facturación para el valor del tiempo y el material</span><span class="sxs-lookup"><span data-stu-id="c62c7-320">Example: Create a billing rule for the value of time and materials</span></span>

<span data-ttu-id="c62c7-321">Su organización, una empresa de consultoría de software, acuerda proporcionar cinco asesores técnicos para trabajar en un proyecto de desarrollo de software para un cliente durante los próximos seis meses.</span><span class="sxs-lookup"><span data-stu-id="c62c7-321">Your organization, a software consulting firm, agrees to provide five technical consultants to work on a software development project for a customer for the next six months.</span></span> <span data-ttu-id="c62c7-322">El cliente acepta pagar 150 por cada hora de asesoría, además del coste de los suministros de oficina.</span><span class="sxs-lookup"><span data-stu-id="c62c7-322">The customer agrees to pay 150 for each consulting hour, plus the cost of office supplies.</span></span> <span data-ttu-id="c62c7-323">Su organización envía una factura al cliente al final de cada mes.</span><span class="sxs-lookup"><span data-stu-id="c62c7-323">Your organization sends an invoice to the customer at the end of each month.</span></span> 

<span data-ttu-id="c62c7-324">Al configurar el contrato de proyecto, acepta cobrar cada vez del cliente por el tiempo y el material dedicado al proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-324">When you set up the project contract, you agree to bill the customer each month for time and materials on the project.</span></span> <span data-ttu-id="c62c7-325">Cree una regla de facturación que incluya la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="c62c7-325">You create a billing rule that includes the following information:</span></span>

-   <span data-ttu-id="c62c7-326">El período de del contrato es de seis meses.</span><span class="sxs-lookup"><span data-stu-id="c62c7-326">The contract period is six months.</span></span>
-   <span data-ttu-id="c62c7-327">El tiempo de asesoría se calcula con una tasa de 150 por hora.</span><span class="sxs-lookup"><span data-stu-id="c62c7-327">Consulting time is calculated at a rate of 150 per hour.</span></span>
-   <span data-ttu-id="c62c7-328">Los suministros de oficina se facturan al precio de coste y el coste total del proyecto no debe superar la cantidad de 10.000.</span><span class="sxs-lookup"><span data-stu-id="c62c7-328">Office supplies are invoiced at cost, and the total cost for the project must not exceed 10,000.</span></span>
-   <span data-ttu-id="c62c7-329">Su empresa crea una factura de cliente al final de cada mes natural durante el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-329">You create a customer invoice at the end of each calendar month during the project.</span></span>

<span data-ttu-id="c62c7-330">Durante el primer mes, los asesores registran un total de 800 horas dedicadas al proyecto.</span><span class="sxs-lookup"><span data-stu-id="c62c7-330">During the first month, a total of 800 hours are recorded by the consultants on the project.</span></span> <span data-ttu-id="c62c7-331">El coste de los suministros de oficina que se cargan al proyecto es 2.000.</span><span class="sxs-lookup"><span data-stu-id="c62c7-331">The cost of office supplies that are charged to the project is 2,000.</span></span> <span data-ttu-id="c62c7-332">Por tanto, al final del mes, se crea una factura de 122.000, calculada en base a 800 horas a 150 por hora más 2.000 en suministros de oficina.</span><span class="sxs-lookup"><span data-stu-id="c62c7-332">Therefore, at the end of the month, you create an invoice for 122,000, which is calculated as 800 hours at 150 per hour, plus 2,000 for office supplies.</span></span>




