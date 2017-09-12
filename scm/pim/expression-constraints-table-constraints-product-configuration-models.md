---
title: "Restricciones de expresión y tabla en modelos de configuración de productos"
description: "En este tema se describe el uso de las restricciones de expresión y las restricciones de tabla. Las restricciones controlan los valores de atributo que puede seleccionar al configurar los productos para un pedido de ventas, un presupuesto de ventas, un pedido de compra o un pedido de producción. Puede usar las restricciones de expresión o las restricciones de tablas, en función de cómo prefiere crear las restricciones."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCGlobalTableConstraintEdit, PCProductConfigurationModelDetails, PCTableConstraintAttachAttributeTree, PCTableConstraintDefinition
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 53111
ms.assetid: 5c12b1f2-eb89-4648-a755-de412f2eadd6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: dd6f993e5c5fe343c6484383ff097f87f5dbf894
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---

# <a name="expression-constraints-and-table-constraints-in-product-configuration-models"></a><span data-ttu-id="7bb99-105">Restricciones de expresión y tabla en modelos de configuración de productos</span><span class="sxs-lookup"><span data-stu-id="7bb99-105">Expression constraints and table constraints in product configuration models</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="7bb99-106">En este tema se describe el uso de las restricciones de expresión y las restricciones de tabla.</span><span class="sxs-lookup"><span data-stu-id="7bb99-106">This topic describes the use of expression constraints and table constraints.</span></span> <span data-ttu-id="7bb99-107">Las restricciones controlan los valores de atributo que puede seleccionar al configurar los productos para un pedido de ventas, un presupuesto de ventas, un pedido de compra o un pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="7bb99-107">Constraints control the attribute values that you can select when you configure products for a sales order, sales quotation, purchase order, or production order.</span></span> <span data-ttu-id="7bb99-108">Puede usar las restricciones de expresión o las restricciones de tablas, en función de cómo prefiere crear las restricciones.</span><span class="sxs-lookup"><span data-stu-id="7bb99-108">You can use expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span> 

<span data-ttu-id="7bb99-109">Las restricciones se usan para controlar los valores de atributo que puede seleccionar al configurar los productos para un pedido de ventas, un presupuesto de ventas, un pedido de compra o un pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="7bb99-109">Constraints are used to control the attribute values that you can select when you configure products for a sales order, sales quotation, purchase order, or production order.</span></span> <span data-ttu-id="7bb99-110">Puede usar las restricciones de expresión o las restricciones de tablas, en función de cómo prefiere crear las restricciones.</span><span class="sxs-lookup"><span data-stu-id="7bb99-110">You can use expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span>

## <a name="what-are-expression-constraints"></a><span data-ttu-id="7bb99-111">¿Qué son las restricciones de expresión?</span><span class="sxs-lookup"><span data-stu-id="7bb99-111">What are expression constraints?</span></span>
<span data-ttu-id="7bb99-112">Las restricciones de expresión se caracterizan por una expresión que utiliza operadores y funciones aritméticas y booleano.</span><span class="sxs-lookup"><span data-stu-id="7bb99-112">Expression constraints are characterized by an expression that uses arithmetic and Boolean operators and functions.</span></span> <span data-ttu-id="7bb99-113">Una restricción de expresión para un componente concreto se escribe en un modelo de configuración de productos.</span><span class="sxs-lookup"><span data-stu-id="7bb99-113">An expression constraint is written for a specific component in a product configuration model.</span></span> <span data-ttu-id="7bb99-114">No puede volver a utilizarse ni compartirse con otro componente.</span><span class="sxs-lookup"><span data-stu-id="7bb99-114">It can't be reused by or shared with another component.</span></span> <span data-ttu-id="7bb99-115">Sin embargo, las restricciones de expresión de un componente pueden hacer referencia a los atributos de los subcomponentes del componente.</span><span class="sxs-lookup"><span data-stu-id="7bb99-115">However, the expression constraints for a component can reference attributes of the component's subcomponents.</span></span>

## <a name="what-are-table-constraints"></a><span data-ttu-id="7bb99-116">¿Qué son las restricciones de tabla?</span><span class="sxs-lookup"><span data-stu-id="7bb99-116">What are table constraints?</span></span>
<span data-ttu-id="7bb99-117">Las restricciones de tabla muestran las combinaciones de valores permitidas para los atributos cuando configura un producto.</span><span class="sxs-lookup"><span data-stu-id="7bb99-117">Table constraints list the combinations of values that are allowed for attributes when you configure a product.</span></span> <span data-ttu-id="7bb99-118">Las definiciones de la restricción de tabla se pueden usar genéricamente.</span><span class="sxs-lookup"><span data-stu-id="7bb99-118">Table constraint definitions can be used generically.</span></span> <span data-ttu-id="7bb99-119">Cuando se crea una restricción de tabla para un componente en un modelo de configuración de productos, selecciona una definición de restricción de tabla.</span><span class="sxs-lookup"><span data-stu-id="7bb99-119">When you create a table constraint for a component in a product configuration model, you select a table constraint definition.</span></span> <span data-ttu-id="7bb99-120">Para crear las combinaciones permitidas, agrega atributos de tipos específicos a los componentes.</span><span class="sxs-lookup"><span data-stu-id="7bb99-120">To create the combinations that are allowed, you add attributes of specific types to the components.</span></span> <span data-ttu-id="7bb99-121">Cada tipo de atributo tiene un valor específico.</span><span class="sxs-lookup"><span data-stu-id="7bb99-121">Each attribute type has a specific value.</span></span>

### <a name="example-of-a-table-constraint"></a><span data-ttu-id="7bb99-122">Ejemplo de una restricción de tablas</span><span class="sxs-lookup"><span data-stu-id="7bb99-122">Example of a table constraint</span></span>

<span data-ttu-id="7bb99-123">Este ejemplo muestra cómo puede limitar la configuración de un altavoz según acabados de caja y frontales específicos.</span><span class="sxs-lookup"><span data-stu-id="7bb99-123">This example shows how you can limit the configuration of a speaker to specific cabinet finishes and fronts.</span></span> <span data-ttu-id="7bb99-124">La primera tabla muestra los acabados de caja y frontales que suelen estar disponibles para la configuración.</span><span class="sxs-lookup"><span data-stu-id="7bb99-124">The first table shows the cabinet finishes and fronts that are generally available for configuration.</span></span> <span data-ttu-id="7bb99-125">Hay valores definidos para los tipos de atributos **Acabado de la caja** y **Rejilla delantera**.</span><span class="sxs-lookup"><span data-stu-id="7bb99-125">The values are defined for the **Cabinet finish** and **Front grill** attribute types.</span></span>

| <span data-ttu-id="7bb99-126">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="7bb99-126">Attribute type</span></span> | <span data-ttu-id="7bb99-127">Valores</span><span class="sxs-lookup"><span data-stu-id="7bb99-127">Values</span></span>                      |
|----------------|-----------------------------|
| <span data-ttu-id="7bb99-128">Acabado de la caja</span><span class="sxs-lookup"><span data-stu-id="7bb99-128">Cabinet finish</span></span> | <span data-ttu-id="7bb99-129">Negro, roble, palo de rosa y blanco</span><span class="sxs-lookup"><span data-stu-id="7bb99-129">Black, Oak, Rosewood, White</span></span> |
| <span data-ttu-id="7bb99-130">Rejilla delantera</span><span class="sxs-lookup"><span data-stu-id="7bb99-130">Front grill</span></span>    | <span data-ttu-id="7bb99-131">Negro, metálico y blanco</span><span class="sxs-lookup"><span data-stu-id="7bb99-131">Black, Metal, White</span></span>         |

<span data-ttu-id="7bb99-132">La tabla siguiente muestra las combinaciones definidas por la restricción de tabla **Color y acabado**.</span><span class="sxs-lookup"><span data-stu-id="7bb99-132">The next table shows the combinations that are defined by the **Color and finish** table constraint.</span></span> <span data-ttu-id="7bb99-133">Con esta restricción de tabla puede configurar un altavoz que tenga un acabado de roble y una rejilla negra, un acabado de palisandro y una rejilla blanca, etc.</span><span class="sxs-lookup"><span data-stu-id="7bb99-133">By using this table constraint, you can configure a speaker that has an oak finish and a black grill, a Rosewood finish and a white grill, and so on.</span></span>

| <span data-ttu-id="7bb99-134">Finalizar</span><span class="sxs-lookup"><span data-stu-id="7bb99-134">Finish</span></span>         | <span data-ttu-id="7bb99-135">Rejilla</span><span class="sxs-lookup"><span data-stu-id="7bb99-135">Grill</span></span>                       |
|----------------|-----------------------------|
| <span data-ttu-id="7bb99-136">Roble</span><span class="sxs-lookup"><span data-stu-id="7bb99-136">Oak</span></span>            | <span data-ttu-id="7bb99-137">Negro</span><span class="sxs-lookup"><span data-stu-id="7bb99-137">Black</span></span>                       |
| <span data-ttu-id="7bb99-138">Palisandro</span><span class="sxs-lookup"><span data-stu-id="7bb99-138">Rosewood</span></span>       | <span data-ttu-id="7bb99-139">Blanco</span><span class="sxs-lookup"><span data-stu-id="7bb99-139">White</span></span>                       |
| <span data-ttu-id="7bb99-140">Blanco</span><span class="sxs-lookup"><span data-stu-id="7bb99-140">White</span></span>          | <span data-ttu-id="7bb99-141">Negro</span><span class="sxs-lookup"><span data-stu-id="7bb99-141">Black</span></span>                       |
| <span data-ttu-id="7bb99-142">Blanco</span><span class="sxs-lookup"><span data-stu-id="7bb99-142">White</span></span>          | <span data-ttu-id="7bb99-143">Blanco</span><span class="sxs-lookup"><span data-stu-id="7bb99-143">White</span></span>                       |
| <span data-ttu-id="7bb99-144">Negro</span><span class="sxs-lookup"><span data-stu-id="7bb99-144">Black</span></span>          | <span data-ttu-id="7bb99-145">Negro</span><span class="sxs-lookup"><span data-stu-id="7bb99-145">Black</span></span>                       |
| <span data-ttu-id="7bb99-146">Negro</span><span class="sxs-lookup"><span data-stu-id="7bb99-146">Black</span></span>          | <span data-ttu-id="7bb99-147">Metálico</span><span class="sxs-lookup"><span data-stu-id="7bb99-147">Metal</span></span>                       | 

<span data-ttu-id="7bb99-148">Puede crear restricciones de tablas definidas por el sistema y definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="7bb99-148">You can create system-defined and user-defined table constraints.</span></span> <span data-ttu-id="7bb99-149">Para obtener más información, consulte [Restricciones de tablas definidas por el usuario o definidas por el sistema](system-defined-user-defined-table-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="7bb99-149">For more information, see [System-defined and user-defined table constraints](system-defined-user-defined-table-constraints.md).</span></span>

## <a name="what-syntax-should-be-used-to-write-constraints"></a><span data-ttu-id="7bb99-150">¿Qué sintaxis debe usarse para resolver restricciones de escritura?</span><span class="sxs-lookup"><span data-stu-id="7bb99-150">What syntax should be used to write constraints?</span></span>
<span data-ttu-id="7bb99-151">Debe utilizar la sintaxis del lenguaje de modelado de optimización (OML) para escribir las restricciones.</span><span class="sxs-lookup"><span data-stu-id="7bb99-151">You must use Optimization Modeling Language (OML) syntax when you write constraints.</span></span> <span data-ttu-id="7bb99-152">El sistema utiliza Microsoft Microsoft Solver Foundation para solucionar las restricciones.</span><span class="sxs-lookup"><span data-stu-id="7bb99-152">The system uses Microsoft Solver Foundation constraint solver to solve the constraints.</span></span>

## <a name="should-i-use-table-constraints-or-expression-constraints"></a><span data-ttu-id="7bb99-153">¿Se deben usar restricciones de tablas o restricciones de expresión?</span><span class="sxs-lookup"><span data-stu-id="7bb99-153">Should I use table constraints or expression constraints?</span></span>
<span data-ttu-id="7bb99-154">Puede usar restricciones de expresión o restricciones de tablas, en función de cómo prefiere crear las restricciones.</span><span class="sxs-lookup"><span data-stu-id="7bb99-154">You can use either expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span> <span data-ttu-id="7bb99-155">Una restricción de tabla se crea como una matriz, mientras que una restricción de expresión es una sentencia individual.</span><span class="sxs-lookup"><span data-stu-id="7bb99-155">You build a table constraint as a matrix, whereas an expression constraint is an individual statement.</span></span> <span data-ttu-id="7bb99-156">Si configura un producto, no importa qué tipo de restricción se usa.</span><span class="sxs-lookup"><span data-stu-id="7bb99-156">When you configure a product, it doesn't matter what kind of constraint is used.</span></span> <span data-ttu-id="7bb99-157">El ejemplo siguiente muestra en qué se diferencian los dos métodos.</span><span class="sxs-lookup"><span data-stu-id="7bb99-157">The following example shows how the two methods differ.</span></span>  

<span data-ttu-id="7bb99-158">Si configura un producto mediante las configuraciones de restricciones siguientes, podrá hacer uso de estas combinaciones:</span><span class="sxs-lookup"><span data-stu-id="7bb99-158">When you configure a product by using the following constraint setups, these combinations are allowed:</span></span>

-   <span data-ttu-id="7bb99-159">Un producto de color negro y de tamaño 30 o 50</span><span class="sxs-lookup"><span data-stu-id="7bb99-159">A product in the color Black, and in size 30 or 50</span></span>
-   <span data-ttu-id="7bb99-160">Un producto de color rojo y de tamaño 20</span><span class="sxs-lookup"><span data-stu-id="7bb99-160">A product in the color Red and in size 20</span></span>

### <a name="table-constraint-setup"></a><span data-ttu-id="7bb99-161">Configuración de restricciones de tabla</span><span class="sxs-lookup"><span data-stu-id="7bb99-161">Table constraint setup</span></span>

| <span data-ttu-id="7bb99-162">Color</span><span class="sxs-lookup"><span data-stu-id="7bb99-162">Color</span></span> | <span data-ttu-id="7bb99-163">Tamaño</span><span class="sxs-lookup"><span data-stu-id="7bb99-163">Size</span></span> |
|-------|------|
| <span data-ttu-id="7bb99-164">Negro</span><span class="sxs-lookup"><span data-stu-id="7bb99-164">Black</span></span> | <span data-ttu-id="7bb99-165">30</span><span class="sxs-lookup"><span data-stu-id="7bb99-165">30</span></span>   |
| <span data-ttu-id="7bb99-166">Negro</span><span class="sxs-lookup"><span data-stu-id="7bb99-166">Black</span></span> | <span data-ttu-id="7bb99-167">50</span><span class="sxs-lookup"><span data-stu-id="7bb99-167">50</span></span>   |
| <span data-ttu-id="7bb99-168">Rojo</span><span class="sxs-lookup"><span data-stu-id="7bb99-168">Red</span></span>   | <span data-ttu-id="7bb99-169">20</span><span class="sxs-lookup"><span data-stu-id="7bb99-169">20</span></span>   |

### <a name="expression-constraint-setup"></a><span data-ttu-id="7bb99-170">Configuración de restricciones de expresión</span><span class="sxs-lookup"><span data-stu-id="7bb99-170">Expression constraint setup</span></span>

<span data-ttu-id="7bb99-171">(Color == "Negro" & (size == "30" | size == "50")) | (color == "Rojo" & size = "20")</span><span class="sxs-lookup"><span data-stu-id="7bb99-171">(Color == "Black" & (size == "30" | size == "50")) | (color == "Red" & size = "20")</span></span>

## <a name="should-i-use-operators-or-infix-notation-when-i-write-expression-constraints"></a><span data-ttu-id="7bb99-172">¿Se deben usar operadores o una notación de infijo al escribir las restricciones de expresión?</span><span class="sxs-lookup"><span data-stu-id="7bb99-172">Should I use operators or infix notation when I write expression constraints?</span></span>
<span data-ttu-id="7bb99-173">Se puede escribir una restricción de expresión mediante los operadores de prefijo disponibles, o bien mediante la notación de infijo.</span><span class="sxs-lookup"><span data-stu-id="7bb99-173">You can write an expression constraint by using either the available prefix operators or infix notation.</span></span> <span data-ttu-id="7bb99-174">Para los operadores **Min**, **Max** y **Abs** no puede usar una notación de infijo.</span><span class="sxs-lookup"><span data-stu-id="7bb99-174">For the **Min**, **Max**, and **Abs** operators, you can't use infix notation.</span></span> <span data-ttu-id="7bb99-175">Estos operadores se incluyen como operadores estándar en la mayoría de los lenguajes de programación.</span><span class="sxs-lookup"><span data-stu-id="7bb99-175">These operators are included as standard operators in most programming languages.</span></span>

## <a name="what-operators-and-infix-notation-can-i-use-when-i-write-expression-constraints"></a><span data-ttu-id="7bb99-176">¿Qué operadores o notaciones de infijo se pueden usar al escribir restricciones de expresión?</span><span class="sxs-lookup"><span data-stu-id="7bb99-176">What operators and infix notation can I use when I write expression constraints?</span></span>
<span data-ttu-id="7bb99-177">En las tablas siguientes se enumeran los operadores y la notación de infijo que se pueden utilizar al escribir la restricción de expresión de un componente en un modelo de configuración de productos.</span><span class="sxs-lookup"><span data-stu-id="7bb99-177">The following tables list the operators and infix notation that you can use when you write an expression constraint for a component in a product configuration model.</span></span> <span data-ttu-id="7bb99-178">Los ejemplos de la primera tabla muestran cómo escribir una expresión mediante la notación de infijo o los operadores.</span><span class="sxs-lookup"><span data-stu-id="7bb99-178">The examples in the first table show how to write an expression by using either infix notation or operators.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7bb99-179">Operador</span><span class="sxs-lookup"><span data-stu-id="7bb99-179">Operator</span></span></th>
<th><span data-ttu-id="7bb99-180">Descripción</span><span class="sxs-lookup"><span data-stu-id="7bb99-180">Description</span></span></th>
<th><span data-ttu-id="7bb99-181">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7bb99-181">Syntax</span></span></th>
<th><span data-ttu-id="7bb99-182">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7bb99-182">Examples</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="7bb99-183">Implica</span><span class="sxs-lookup"><span data-stu-id="7bb99-183">Implies</span></span></td>
<td><span data-ttu-id="7bb99-184">Se aplica si la primera condición es falsa, la segunda condición es verdadera, o se dan ambas condiciones.</span><span class="sxs-lookup"><span data-stu-id="7bb99-184">This is true if the first condition is false, the second condition is true, or both.</span></span></td>
<td><span data-ttu-id="7bb99-185">Implies[a, b], infix: a -: b</span><span class="sxs-lookup"><span data-stu-id="7bb99-185">Implies[a, b], infix: a -: b</span></span></td>
<td><ul>
<li><span data-ttu-id="7bb99-186"><strong>Operador:</strong> Implies[x != 0, y &gt;= 0]</span><span class="sxs-lookup"><span data-stu-id="7bb99-186"><strong>Operator:</strong> Implies[x != 0, y &gt;= 0]</span></span></li>
<li><span data-ttu-id="7bb99-187"><strong>Notación de infijo:</strong> x != 0 -: y &gt;= 0</span><span class="sxs-lookup"><span data-stu-id="7bb99-187"><strong>Infix notation:</strong> x != 0 -: y &gt;= 0</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7bb99-188">Y</span><span class="sxs-lookup"><span data-stu-id="7bb99-188">And</span></span></td>
<td><span data-ttu-id="7bb99-189">Se aplica solo si todas las condiciones son verdaderas.</span><span class="sxs-lookup"><span data-stu-id="7bb99-189">This is true only if all conditions are true.</span></span> <span data-ttu-id="7bb99-190">Si el número de condiciones es 0 (cero), da lugar a <strong>True</strong>.</span><span class="sxs-lookup"><span data-stu-id="7bb99-190">If the number of conditions is 0 (zero), it produces <strong>True</strong>.</span></span></td>
<td><span data-ttu-id="7bb99-191">And[args], infix: a &amp; b &amp; ... &amp; z</span><span class="sxs-lookup"><span data-stu-id="7bb99-191">And[args], infix: a &amp; b &amp; ... &amp; z</span></span></td>
<td><ul>
<li><span data-ttu-id="7bb99-192"><strong>Operador:</strong> And[x == 2, y &lt;= 2]</span><span class="sxs-lookup"><span data-stu-id="7bb99-192"><strong>Operator:</strong> And[x == 2, y &lt;= 2]</span></span></li>
<li><span data-ttu-id="7bb99-193"><strong>Notación de infijo:</strong> x == 2 &amp; y &lt;= 2</span><span class="sxs-lookup"><span data-stu-id="7bb99-193"><strong>Infix notation:</strong> x == 2 &amp; y &lt;= 2</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7bb99-194">O</span><span class="sxs-lookup"><span data-stu-id="7bb99-194">Or</span></span></td>
<td><span data-ttu-id="7bb99-195">Se aplica si cualquier condición es verdadera.</span><span class="sxs-lookup"><span data-stu-id="7bb99-195">This is true if any condition is true.</span></span> <span data-ttu-id="7bb99-196">Si el número de condiciones es 0 (cero), da lugar a <strong>False</strong>.</span><span class="sxs-lookup"><span data-stu-id="7bb99-196">If the number of conditions is 0 (zero), it produces <strong>False</strong>.</span></span></td>
<td><span data-ttu-id="7bb99-197">Or[args], infix: a | b | ... | z</span><span class="sxs-lookup"><span data-stu-id="7bb99-197">Or[args], infix: a | b | ... | z</span></span></td>
<td><ul>
<li><span data-ttu-id="7bb99-198"><strong>Operador:</strong> Or[x == 2, y &lt;= 2]</span><span class="sxs-lookup"><span data-stu-id="7bb99-198"><strong>Operator:</strong> Or[x == 2, y &lt;= 2]</span></span></li>
<li><span data-ttu-id="7bb99-199"><strong>Notación de infijo:</strong> x == 2 | y &lt;= 2</span><span class="sxs-lookup"><span data-stu-id="7bb99-199"><strong>Infix notation:</strong> x == 2 | y &lt;= 2</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7bb99-200">Más</span><span class="sxs-lookup"><span data-stu-id="7bb99-200">Plus</span></span></td>
<td><span data-ttu-id="7bb99-201">Esto suma sus condiciones.</span><span class="sxs-lookup"><span data-stu-id="7bb99-201">This sums its conditions.</span></span> <span data-ttu-id="7bb99-202">Si el número de condiciones es 0 (cero), da lugar a <strong>0</strong>.</span><span class="sxs-lookup"><span data-stu-id="7bb99-202">If the number of conditions is 0 (zero), it produces <strong>0</strong>.</span></span></td>
<td><span data-ttu-id="7bb99-203">Plus[args], infix: a + b + ... + z</span><span class="sxs-lookup"><span data-stu-id="7bb99-203">Plus[args], infix: a + b + ... + z</span></span></td>
<td><ul>
<li><span data-ttu-id="7bb99-204"><strong>Operador</strong>: Plus[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="7bb99-204"><strong>Operator:</strong> Plus[x, y, 2] == z</span></span></li>
<li><span data-ttu-id="7bb99-205"><strong>Notación de infijo</strong>: x + y + 2 == z</span><span class="sxs-lookup"><span data-stu-id="7bb99-205"><strong>Infix notation:</strong> x + y + 2 == z</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7bb99-206">Menos</span><span class="sxs-lookup"><span data-stu-id="7bb99-206">Minus</span></span></td>
<td><span data-ttu-id="7bb99-207">Esto establece su argumento como negativo.</span><span class="sxs-lookup"><span data-stu-id="7bb99-207">This negates its argument.</span></span> <span data-ttu-id="7bb99-208">Debe tener exactamente una condición.</span><span class="sxs-lookup"><span data-stu-id="7bb99-208">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="7bb99-209">Minus[expr], infix: -expr</span><span class="sxs-lookup"><span data-stu-id="7bb99-209">Minus[expr], infix: -expr</span></span></td>
<td><ul>
<li><span data-ttu-id="7bb99-210"><strong>Operador:</strong> Minus[x] == y</span><span class="sxs-lookup"><span data-stu-id="7bb99-210"><strong>Operator:</strong> Minus[x] == y</span></span></li>
<li><span data-ttu-id="7bb99-211"><strong>Notación de infijo:</strong> -x == y</span><span class="sxs-lookup"><span data-stu-id="7bb99-211"><strong>Infix notation:</strong> -x == y</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7bb99-212">Abs</span><span class="sxs-lookup"><span data-stu-id="7bb99-212">Abs</span></span></td>
<td><span data-ttu-id="7bb99-213">Toma el valor absoluto de la condición.</span><span class="sxs-lookup"><span data-stu-id="7bb99-213">This takes the absolute value of its condition.</span></span> <span data-ttu-id="7bb99-214">Debe tener exactamente una condición.</span><span class="sxs-lookup"><span data-stu-id="7bb99-214">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="7bb99-215">Abs[expr]</span><span class="sxs-lookup"><span data-stu-id="7bb99-215">Abs[expr]</span></span></td>
<td><span data-ttu-id="7bb99-216"><strong>Operador</strong>: Abs[x]</span><span class="sxs-lookup"><span data-stu-id="7bb99-216"><strong>Operator:</strong> Abs[x]</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7bb99-217">Horas</span><span class="sxs-lookup"><span data-stu-id="7bb99-217">Times</span></span></td>
<td><span data-ttu-id="7bb99-218">Toma el producto de sus condiciones.</span><span class="sxs-lookup"><span data-stu-id="7bb99-218">This takes the product of its conditions.</span></span> <span data-ttu-id="7bb99-219">Si el número de condiciones es 0 (cero), da lugar a <strong>1</strong>.</span><span class="sxs-lookup"><span data-stu-id="7bb99-219">If the number of conditions is 0 (zero), it produces <strong>1</strong>.</span></span></td>
<td><span data-ttu-id="7bb99-220">Times[args], infix: a * b * ... * z</span><span class="sxs-lookup"><span data-stu-id="7bb99-220">Times[args], infix: a * b * ... * z</span></span></td>
<td><ul>
<li><span data-ttu-id="7bb99-221"><strong>Operador:</strong> Times[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="7bb99-221"><strong>Operator:</strong> Times[x, y, 2] == z</span></span></li>
<li><span data-ttu-id="7bb99-222"><strong>Notación de infijo:</strong> x * y * 2 == z</span><span class="sxs-lookup"><span data-stu-id="7bb99-222"><strong>Infix notation:</strong> x * y * 2 == z</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7bb99-223">Inicio/apagado</span><span class="sxs-lookup"><span data-stu-id="7bb99-223">Power</span></span></td>
<td><span data-ttu-id="7bb99-224">Toma un exponencial.</span><span class="sxs-lookup"><span data-stu-id="7bb99-224">This takes an exponential.</span></span> <span data-ttu-id="7bb99-225">Aplica la potencia de derecha a izquierda.</span><span class="sxs-lookup"><span data-stu-id="7bb99-225">It applies exponentiation from right to left.</span></span> <span data-ttu-id="7bb99-226">(Es decir, es asociativo a la derecha). Por tanto, <strong>Power[a, b, c]</strong> es equivalente a <strong>Power[a, Power[b, c]]</strong>.</span><span class="sxs-lookup"><span data-stu-id="7bb99-226">(In other words, it's right-associative.) Therefore, <strong>Power[a, b, c]</strong> is equivalent to <strong>Power[a, Power[b, c]]</strong>.</span></span> <span data-ttu-id="7bb99-227"><strong>Power</strong> solo se puede usar si el exponente es una constante positiva.</span><span class="sxs-lookup"><span data-stu-id="7bb99-227"><strong>Power</strong> can be used only if the exponent is a positive constant.</span></span></td>
<td><span data-ttu-id="7bb99-228">Power[args], infix: a ^ b ^ ... ^ z</span><span class="sxs-lookup"><span data-stu-id="7bb99-228">Power[args], infix: a ^ b ^ ... ^ z</span></span></td>
<td><ul>
<li><span data-ttu-id="7bb99-229"><strong>Operador:</strong> Power[x, 2] == y</span><span class="sxs-lookup"><span data-stu-id="7bb99-229"><strong>Operator:</strong> Power[x, 2] == y</span></span></li>
<li><span data-ttu-id="7bb99-230"><strong>Notación de infijo:</strong> x ^ 2 == y</span><span class="sxs-lookup"><span data-stu-id="7bb99-230"><strong>Infix notation:</strong> x ^ 2 == y</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7bb99-231">Máx.</span><span class="sxs-lookup"><span data-stu-id="7bb99-231">Max</span></span></td>
<td><span data-ttu-id="7bb99-232">Produce la condición mayor.</span><span class="sxs-lookup"><span data-stu-id="7bb99-232">This produces the largest condition.</span></span> <span data-ttu-id="7bb99-233">Si el número de condiciones es 0 (cero), produce <strong>Infinity</strong>.</span><span class="sxs-lookup"><span data-stu-id="7bb99-233">If the number of conditions is 0 (zero), it produces <strong>Infinity</strong>.</span></span></td>
<td><span data-ttu-id="7bb99-234">Max[args]</span><span class="sxs-lookup"><span data-stu-id="7bb99-234">Max[args]</span></span></td>
<td><span data-ttu-id="7bb99-235"><strong>Operador:</strong> Max[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="7bb99-235"><strong>Operator:</strong> Max[x, y, 2] == z</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7bb99-236">Mín.</span><span class="sxs-lookup"><span data-stu-id="7bb99-236">Min</span></span></td>
<td><span data-ttu-id="7bb99-237">Produce la condición más pequeña.</span><span class="sxs-lookup"><span data-stu-id="7bb99-237">This produces the smallest condition.</span></span> <span data-ttu-id="7bb99-238">Si el número de condiciones es 0 (cero), produce <strong>Infinity</strong>.</span><span class="sxs-lookup"><span data-stu-id="7bb99-238">If the number of conditions is 0 (zero), it produces <strong>Infinity</strong>.</span></span></td>
<td><span data-ttu-id="7bb99-239">Min[args]</span><span class="sxs-lookup"><span data-stu-id="7bb99-239">Min[args]</span></span></td>
<td><span data-ttu-id="7bb99-240"><strong>Operador:</strong> Min[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="7bb99-240"><strong>Operator:</strong> Min[x, y, 2] == z</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7bb99-241">No</span><span class="sxs-lookup"><span data-stu-id="7bb99-241">Not</span></span></td>
<td><span data-ttu-id="7bb99-242">Produce el contrario lógico de la condición.</span><span class="sxs-lookup"><span data-stu-id="7bb99-242">This produces the logical inverse of its condition.</span></span> <span data-ttu-id="7bb99-243">Debe tener exactamente una condición.</span><span class="sxs-lookup"><span data-stu-id="7bb99-243">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="7bb99-244">Not[expr], infix: !expr</span><span class="sxs-lookup"><span data-stu-id="7bb99-244">Not[expr], infix: !expr</span></span></td>
<td><ul>
<li><span data-ttu-id="7bb99-245"><strong>Operador:</strong> Not[x] &amp; Not[y == 3]</span><span class="sxs-lookup"><span data-stu-id="7bb99-245"><strong>Operator:</strong> Not[x] &amp; Not[y == 3]</span></span></li>
<li><span data-ttu-id="7bb99-246"><strong>Notación de infijo:</strong> !x!(y == 3)</span><span class="sxs-lookup"><span data-stu-id="7bb99-246"><strong>Infix notation:</strong> !x!(y == 3)</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7bb99-247">Los ejemplos en la siguiente tabla muestran cómo escribir una notación de infijo.</span><span class="sxs-lookup"><span data-stu-id="7bb99-247">The examples in the next table show how to write infix notation.</span></span>

| <span data-ttu-id="7bb99-248">Notación de infijo</span><span class="sxs-lookup"><span data-stu-id="7bb99-248">Infix notation</span></span>    | <span data-ttu-id="7bb99-249">Descripción</span><span class="sxs-lookup"><span data-stu-id="7bb99-249">Description</span></span>                                                                                   |
|-------------------|-----------------------------------------------------------------------------------------------|
| <span data-ttu-id="7bb99-250">x + y + z</span><span class="sxs-lookup"><span data-stu-id="7bb99-250">x + y + z</span></span>         | <span data-ttu-id="7bb99-251">Adición</span><span class="sxs-lookup"><span data-stu-id="7bb99-251">Addition</span></span>                                                                                      |
| <span data-ttu-id="7bb99-252">x \* y \* z</span><span class="sxs-lookup"><span data-stu-id="7bb99-252">x \* y \* z</span></span>       | <span data-ttu-id="7bb99-253">Multiplicación</span><span class="sxs-lookup"><span data-stu-id="7bb99-253">Multiplication</span></span>                                                                                |
| <span data-ttu-id="7bb99-254">x - y</span><span class="sxs-lookup"><span data-stu-id="7bb99-254">x - y</span></span>             | <span data-ttu-id="7bb99-255">La resta binaria se traduce de la misma forma que la adición binaria donde hay un segundo negativo.</span><span class="sxs-lookup"><span data-stu-id="7bb99-255">Binary subtraction is translated the same as binary addition where there is a negated second.</span></span> |
| <span data-ttu-id="7bb99-256">x ^ y ^ z</span><span class="sxs-lookup"><span data-stu-id="7bb99-256">x ^ y ^ z</span></span>         | <span data-ttu-id="7bb99-257">Exponenciación con asociación a la derecha</span><span class="sxs-lookup"><span data-stu-id="7bb99-257">Exponentiation that has right associativity</span></span>                                                   |
| <span data-ttu-id="7bb99-258">!x</span><span class="sxs-lookup"><span data-stu-id="7bb99-258">!x</span></span>                | <span data-ttu-id="7bb99-259">No booleano</span><span class="sxs-lookup"><span data-stu-id="7bb99-259">Boolean not</span></span>                                                                                   |
| <span data-ttu-id="7bb99-260">x -: y</span><span class="sxs-lookup"><span data-stu-id="7bb99-260">x -: y</span></span>            | <span data-ttu-id="7bb99-261">Implicación booleano</span><span class="sxs-lookup"><span data-stu-id="7bb99-261">Boolean implication</span></span>                                                                           |
| <span data-ttu-id="7bb99-262">x</span><span class="sxs-lookup"><span data-stu-id="7bb99-262">x</span></span> | <span data-ttu-id="7bb99-263">y</span><span class="sxs-lookup"><span data-stu-id="7bb99-263">y</span></span> | <span data-ttu-id="7bb99-264">z</span><span class="sxs-lookup"><span data-stu-id="7bb99-264">z</span></span>         | <span data-ttu-id="7bb99-265">Booleano o</span><span class="sxs-lookup"><span data-stu-id="7bb99-265">Boolean or</span></span>                                                                                    |
| <span data-ttu-id="7bb99-266">x & y & z</span><span class="sxs-lookup"><span data-stu-id="7bb99-266">x & y & z</span></span>         | <span data-ttu-id="7bb99-267">Booleano y</span><span class="sxs-lookup"><span data-stu-id="7bb99-267">Boolean and</span></span>                                                                                   |
| <span data-ttu-id="7bb99-268">x == y == z</span><span class="sxs-lookup"><span data-stu-id="7bb99-268">x == y == z</span></span>       | <span data-ttu-id="7bb99-269">Igualdad</span><span class="sxs-lookup"><span data-stu-id="7bb99-269">Equality</span></span>                                                                                      |
| <span data-ttu-id="7bb99-270">x != y != z</span><span class="sxs-lookup"><span data-stu-id="7bb99-270">x != y != z</span></span>       | <span data-ttu-id="7bb99-271">Distinto</span><span class="sxs-lookup"><span data-stu-id="7bb99-271">Distinct</span></span>                                                                                      |
| <span data-ttu-id="7bb99-272">x &lt; y &lt; z</span><span class="sxs-lookup"><span data-stu-id="7bb99-272">x &lt; y &lt; z</span></span>   | <span data-ttu-id="7bb99-273">Menor que</span><span class="sxs-lookup"><span data-stu-id="7bb99-273">Less than</span></span>                                                                                     |
| <span data-ttu-id="7bb99-274">x &gt; y &gt; z</span><span class="sxs-lookup"><span data-stu-id="7bb99-274">x &gt; y &gt; z</span></span>   | <span data-ttu-id="7bb99-275">Mayor que</span><span class="sxs-lookup"><span data-stu-id="7bb99-275">Greater than</span></span>                                                                                  |
| <span data-ttu-id="7bb99-276">x &lt;= y &lt;= z</span><span class="sxs-lookup"><span data-stu-id="7bb99-276">x &lt;= y &lt;= z</span></span> | <span data-ttu-id="7bb99-277">Inferior a o igual a</span><span class="sxs-lookup"><span data-stu-id="7bb99-277">Less than or equal to</span></span>                                                                         |
| <span data-ttu-id="7bb99-278">x &gt;= y &gt;= z</span><span class="sxs-lookup"><span data-stu-id="7bb99-278">x &gt;= y &gt;= z</span></span> | <span data-ttu-id="7bb99-279">Superior a o igual a</span><span class="sxs-lookup"><span data-stu-id="7bb99-279">Greater than or equal to</span></span>                                                                      |
| <span data-ttu-id="7bb99-280">(x)</span><span class="sxs-lookup"><span data-stu-id="7bb99-280">(x)</span></span>               | <span data-ttu-id="7bb99-281">El paréntesis anula la prioridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7bb99-281">Parentheses override default precedence.</span></span>                                                      |

## <a name="why-arent-my-expression-constraints-validated-correctly"></a><span data-ttu-id="7bb99-282">¿Por qué las restricciones de expresión no se validan correctamente?</span><span class="sxs-lookup"><span data-stu-id="7bb99-282">Why aren't my expression constraints validated correctly?</span></span>
<span data-ttu-id="7bb99-283">No se pueden usar palabras clave reservadas como nombres del solucionador de atributos, componentes o subcomponentes en un modelo de configuración de productos.</span><span class="sxs-lookup"><span data-stu-id="7bb99-283">You can't use reserved keywords as solver names for attributes, components, or subcomponents in a product configuration model.</span></span> <span data-ttu-id="7bb99-284">A continuación se muestra una lista de palabras clave reservadas que no se pueden usar:</span><span class="sxs-lookup"><span data-stu-id="7bb99-284">Here is a list of the reserved keywords that you can't use:</span></span>

-   <span data-ttu-id="7bb99-285">Techo</span><span class="sxs-lookup"><span data-stu-id="7bb99-285">Ceiling</span></span>
-   <span data-ttu-id="7bb99-286">Elemento</span><span class="sxs-lookup"><span data-stu-id="7bb99-286">Element</span></span>
-   <span data-ttu-id="7bb99-287">Igual</span><span class="sxs-lookup"><span data-stu-id="7bb99-287">Equal</span></span>
-   <span data-ttu-id="7bb99-288">Piso</span><span class="sxs-lookup"><span data-stu-id="7bb99-288">Floor</span></span>
-   <span data-ttu-id="7bb99-289">Si</span><span class="sxs-lookup"><span data-stu-id="7bb99-289">If</span></span>
-   <span data-ttu-id="7bb99-290">Menor</span><span class="sxs-lookup"><span data-stu-id="7bb99-290">Less</span></span>
-   <span data-ttu-id="7bb99-291">Mayor</span><span class="sxs-lookup"><span data-stu-id="7bb99-291">Greater</span></span>
-   <span data-ttu-id="7bb99-292">Implica</span><span class="sxs-lookup"><span data-stu-id="7bb99-292">Implies</span></span>
-   <span data-ttu-id="7bb99-293">Registro</span><span class="sxs-lookup"><span data-stu-id="7bb99-293">Log</span></span>
-   <span data-ttu-id="7bb99-294">Máx.</span><span class="sxs-lookup"><span data-stu-id="7bb99-294">Max</span></span>
-   <span data-ttu-id="7bb99-295">Mín.</span><span class="sxs-lookup"><span data-stu-id="7bb99-295">Min</span></span>
-   <span data-ttu-id="7bb99-296">Menos</span><span class="sxs-lookup"><span data-stu-id="7bb99-296">Minus</span></span>
-   <span data-ttu-id="7bb99-297">Más</span><span class="sxs-lookup"><span data-stu-id="7bb99-297">Plus</span></span>
-   <span data-ttu-id="7bb99-298">Potencia</span><span class="sxs-lookup"><span data-stu-id="7bb99-298">Power</span></span>
-   <span data-ttu-id="7bb99-299">Tiempos</span><span class="sxs-lookup"><span data-stu-id="7bb99-299">Times</span></span>
-   <span data-ttu-id="7bb99-300">Ranura</span><span class="sxs-lookup"><span data-stu-id="7bb99-300">Slot</span></span>
-   <span data-ttu-id="7bb99-301">Modelo</span><span class="sxs-lookup"><span data-stu-id="7bb99-301">Model</span></span>
-   <span data-ttu-id="7bb99-302">Decisión</span><span class="sxs-lookup"><span data-stu-id="7bb99-302">Decision</span></span>
-   <span data-ttu-id="7bb99-303">Objetivo</span><span class="sxs-lookup"><span data-stu-id="7bb99-303">Goal</span></span>


<a name="see-also"></a><span data-ttu-id="7bb99-304">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7bb99-304">See also</span></span>
--------

<span data-ttu-id="7bb99-305">[Crear una restricción de expresión (guía de tareas)(/dynamics365/unified-operations/supply-chain/pim/tasks/add-expression-constraint-product-configuration-model)</span><span class="sxs-lookup"><span data-stu-id="7bb99-305">[Create an expression constraint (Task guide)(/dynamics365/unified-operations/supply-chain/pim/tasks/add-expression-constraint-product-configuration-model)</span></span>

[<span data-ttu-id="7bb99-306">Agregar un cálculo a un modelo de configuración de producto (guía de tareas)</span><span class="sxs-lookup"><span data-stu-id="7bb99-306">Add a calculation to a product configuration model (Task guide)</span></span>](/dynamics365/unified-operations/supply-chain/pim/tasks/add-calculation-product-configuration-model)




