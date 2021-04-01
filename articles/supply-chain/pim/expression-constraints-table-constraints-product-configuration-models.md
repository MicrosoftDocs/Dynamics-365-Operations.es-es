---
title: Restricciones de expresión y tabla en modelos de configuración de productos
description: En este tema se describe el uso de las restricciones de expresión y las restricciones de tabla. Las restricciones controlan los valores de atributo que puede seleccionar al configurar los productos para un pedido de ventas, un presupuesto de ventas, un pedido de compra o un pedido de producción. Puede usar las restricciones de expresión o las restricciones de tablas, en función de cómo prefiere crear las restricciones.
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCGlobalTableConstraintEdit, PCProductConfigurationModelDetails, PCTableConstraintAttachAttributeTree, PCTableConstraintDefinition
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53111
ms.assetid: 5c12b1f2-eb89-4648-a755-de412f2eadd6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 989981e6ca8c1075367776ceafe5b88429e004d2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5243234"
---
# <a name="expression-constraints-and-table-constraints-in-product-configuration-models"></a><span data-ttu-id="935ad-105">Restricciones de expresión y tabla en modelos de configuración de productos</span><span class="sxs-lookup"><span data-stu-id="935ad-105">Expression constraints and table constraints in product configuration models</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="935ad-106">En este tema se describe el uso de las restricciones de expresión y las restricciones de tabla.</span><span class="sxs-lookup"><span data-stu-id="935ad-106">This topic describes the use of expression constraints and table constraints.</span></span> <span data-ttu-id="935ad-107">Las restricciones controlan los valores de atributo que puede seleccionar al configurar los productos para un pedido de ventas, un presupuesto de ventas, un pedido de compra o un pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="935ad-107">Constraints control the attribute values that you can select when you configure products for a sales order, sales quotation, purchase order, or production order.</span></span> <span data-ttu-id="935ad-108">Puede usar las restricciones de expresión o las restricciones de tablas, en función de cómo prefiere crear las restricciones.</span><span class="sxs-lookup"><span data-stu-id="935ad-108">You can use expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span> 

<span data-ttu-id="935ad-109">Las restricciones se usan para controlar los valores de atributo que puede seleccionar al configurar los productos para un pedido de ventas, un presupuesto de ventas, un pedido de compra o un pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="935ad-109">Constraints are used to control the attribute values that you can select when you configure products for a sales order, sales quotation, purchase order, or production order.</span></span> <span data-ttu-id="935ad-110">Puede usar las restricciones de expresión o las restricciones de tablas, en función de cómo prefiere crear las restricciones.</span><span class="sxs-lookup"><span data-stu-id="935ad-110">You can use expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span>

## <a name="what-are-expression-constraints"></a><span data-ttu-id="935ad-111">¿Qué son las restricciones de expresión?</span><span class="sxs-lookup"><span data-stu-id="935ad-111">What are expression constraints?</span></span>
<span data-ttu-id="935ad-112">Las restricciones de expresión se caracterizan por una expresión que utiliza operadores y funciones aritméticas y booleano.</span><span class="sxs-lookup"><span data-stu-id="935ad-112">Expression constraints are characterized by an expression that uses arithmetic and Boolean operators and functions.</span></span> <span data-ttu-id="935ad-113">Una restricción de expresión para un componente concreto se escribe en un modelo de configuración de productos.</span><span class="sxs-lookup"><span data-stu-id="935ad-113">An expression constraint is written for a specific component in a product configuration model.</span></span> <span data-ttu-id="935ad-114">No puede volver a utilizarse ni compartirse con otro componente.</span><span class="sxs-lookup"><span data-stu-id="935ad-114">It can't be reused by or shared with another component.</span></span> <span data-ttu-id="935ad-115">Sin embargo, las restricciones de expresión de un componente pueden hacer referencia a los atributos de los subcomponentes del componente.</span><span class="sxs-lookup"><span data-stu-id="935ad-115">However, the expression constraints for a component can reference attributes of the component's subcomponents.</span></span>

## <a name="what-are-table-constraints"></a><span data-ttu-id="935ad-116">¿Qué son las restricciones de tabla?</span><span class="sxs-lookup"><span data-stu-id="935ad-116">What are table constraints?</span></span>
<span data-ttu-id="935ad-117">Las restricciones de tabla muestran las combinaciones de valores permitidas para los atributos cuando configura un producto.</span><span class="sxs-lookup"><span data-stu-id="935ad-117">Table constraints list the combinations of values that are allowed for attributes when you configure a product.</span></span> <span data-ttu-id="935ad-118">Las definiciones de la restricción de tabla se pueden usar genéricamente.</span><span class="sxs-lookup"><span data-stu-id="935ad-118">Table constraint definitions can be used generically.</span></span> <span data-ttu-id="935ad-119">Cuando se crea una restricción de tabla para un componente en un modelo de configuración de productos, selecciona una definición de restricción de tabla.</span><span class="sxs-lookup"><span data-stu-id="935ad-119">When you create a table constraint for a component in a product configuration model, you select a table constraint definition.</span></span> <span data-ttu-id="935ad-120">Para crear las combinaciones permitidas, agrega atributos de tipos específicos a los componentes.</span><span class="sxs-lookup"><span data-stu-id="935ad-120">To create the combinations that are allowed, you add attributes of specific types to the components.</span></span> <span data-ttu-id="935ad-121">Cada tipo de atributo tiene un valor específico.</span><span class="sxs-lookup"><span data-stu-id="935ad-121">Each attribute type has a specific value.</span></span>

### <a name="example-of-a-table-constraint"></a><span data-ttu-id="935ad-122">Ejemplo de una restricción de tablas</span><span class="sxs-lookup"><span data-stu-id="935ad-122">Example of a table constraint</span></span>

<span data-ttu-id="935ad-123">Este ejemplo muestra cómo puede limitar la configuración de un altavoz según acabados de caja y frontales específicos.</span><span class="sxs-lookup"><span data-stu-id="935ad-123">This example shows how you can limit the configuration of a speaker to specific cabinet finishes and fronts.</span></span> <span data-ttu-id="935ad-124">La primera tabla muestra los acabados de caja y frontales que suelen estar disponibles para la configuración.</span><span class="sxs-lookup"><span data-stu-id="935ad-124">The first table shows the cabinet finishes and fronts that are generally available for configuration.</span></span> <span data-ttu-id="935ad-125">Hay valores definidos para los tipos de atributos **Acabado de la caja** y **Rejilla delantera**.</span><span class="sxs-lookup"><span data-stu-id="935ad-125">The values are defined for the **Cabinet finish** and **Front grill** attribute types.</span></span>

| <span data-ttu-id="935ad-126">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="935ad-126">Attribute type</span></span> | <span data-ttu-id="935ad-127">Valores</span><span class="sxs-lookup"><span data-stu-id="935ad-127">Values</span></span>                      |
|----------------|-----------------------------|
| <span data-ttu-id="935ad-128">Acabado de la caja</span><span class="sxs-lookup"><span data-stu-id="935ad-128">Cabinet finish</span></span> | <span data-ttu-id="935ad-129">Negro, roble, palo de rosa y blanco</span><span class="sxs-lookup"><span data-stu-id="935ad-129">Black, Oak, Rosewood, White</span></span> |
| <span data-ttu-id="935ad-130">Rejilla delantera</span><span class="sxs-lookup"><span data-stu-id="935ad-130">Front grill</span></span>    | <span data-ttu-id="935ad-131">Negro, metálico y blanco</span><span class="sxs-lookup"><span data-stu-id="935ad-131">Black, Metal, White</span></span>         |

<span data-ttu-id="935ad-132">La tabla siguiente muestra las combinaciones definidas por la restricción de tabla **Color y acabado**.</span><span class="sxs-lookup"><span data-stu-id="935ad-132">The next table shows the combinations that are defined by the **Color and finish** table constraint.</span></span> <span data-ttu-id="935ad-133">Con esta restricción de tabla puede configurar un altavoz que tenga un acabado de roble y una rejilla negra, un acabado de palisandro y una rejilla blanca, etc.</span><span class="sxs-lookup"><span data-stu-id="935ad-133">By using this table constraint, you can configure a speaker that has an oak finish and a black grill, a Rosewood finish and a white grill, and so on.</span></span>

| <span data-ttu-id="935ad-134">Finalizar</span><span class="sxs-lookup"><span data-stu-id="935ad-134">Finish</span></span>         | <span data-ttu-id="935ad-135">Rejilla</span><span class="sxs-lookup"><span data-stu-id="935ad-135">Grill</span></span>                       |
|----------------|-----------------------------|
| <span data-ttu-id="935ad-136">Roble</span><span class="sxs-lookup"><span data-stu-id="935ad-136">Oak</span></span>            | <span data-ttu-id="935ad-137">Negro</span><span class="sxs-lookup"><span data-stu-id="935ad-137">Black</span></span>                       |
| <span data-ttu-id="935ad-138">Palisandro</span><span class="sxs-lookup"><span data-stu-id="935ad-138">Rosewood</span></span>       | <span data-ttu-id="935ad-139">Blanco</span><span class="sxs-lookup"><span data-stu-id="935ad-139">White</span></span>                       |
| <span data-ttu-id="935ad-140">Blanco</span><span class="sxs-lookup"><span data-stu-id="935ad-140">White</span></span>          | <span data-ttu-id="935ad-141">Negro</span><span class="sxs-lookup"><span data-stu-id="935ad-141">Black</span></span>                       |
| <span data-ttu-id="935ad-142">Blanco</span><span class="sxs-lookup"><span data-stu-id="935ad-142">White</span></span>          | <span data-ttu-id="935ad-143">Blanco</span><span class="sxs-lookup"><span data-stu-id="935ad-143">White</span></span>                       |
| <span data-ttu-id="935ad-144">Negro</span><span class="sxs-lookup"><span data-stu-id="935ad-144">Black</span></span>          | <span data-ttu-id="935ad-145">Negro</span><span class="sxs-lookup"><span data-stu-id="935ad-145">Black</span></span>                       |
| <span data-ttu-id="935ad-146">Negro</span><span class="sxs-lookup"><span data-stu-id="935ad-146">Black</span></span>          | <span data-ttu-id="935ad-147">Metálico</span><span class="sxs-lookup"><span data-stu-id="935ad-147">Metal</span></span>                       | 

<span data-ttu-id="935ad-148">Puede crear restricciones de tablas definidas por el sistema y definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="935ad-148">You can create system-defined and user-defined table constraints.</span></span> <span data-ttu-id="935ad-149">Para obtener más información, consulte [Restricciones de tablas definidas por el usuario o definidas por el sistema](system-defined-user-defined-table-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="935ad-149">For more information, see [System-defined and user-defined table constraints](system-defined-user-defined-table-constraints.md).</span></span>

## <a name="what-syntax-should-be-used-to-write-constraints"></a><span data-ttu-id="935ad-150">¿Qué sintaxis debe usarse para resolver restricciones de escritura?</span><span class="sxs-lookup"><span data-stu-id="935ad-150">What syntax should be used to write constraints?</span></span>
<span data-ttu-id="935ad-151">Debe utilizar la sintaxis del lenguaje de modelado de optimización (OML) para escribir las restricciones.</span><span class="sxs-lookup"><span data-stu-id="935ad-151">You must use Optimization Modeling Language (OML) syntax when you write constraints.</span></span> <span data-ttu-id="935ad-152">El sistema utiliza Microsoft Solver Foundation para solucionar las restricciones.</span><span class="sxs-lookup"><span data-stu-id="935ad-152">The system uses Microsoft Solver Foundation constraint solver to solve the constraints.</span></span>

## <a name="should-i-use-table-constraints-or-expression-constraints"></a><span data-ttu-id="935ad-153">¿Se deben usar restricciones de tablas o restricciones de expresión?</span><span class="sxs-lookup"><span data-stu-id="935ad-153">Should I use table constraints or expression constraints?</span></span>
<span data-ttu-id="935ad-154">Puede usar restricciones de expresión o restricciones de tablas, en función de cómo prefiere crear las restricciones.</span><span class="sxs-lookup"><span data-stu-id="935ad-154">You can use either expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span> <span data-ttu-id="935ad-155">Una restricción de tabla se crea como una matriz, mientras que una restricción de expresión es una sentencia individual.</span><span class="sxs-lookup"><span data-stu-id="935ad-155">You build a table constraint as a matrix, whereas an expression constraint is an individual statement.</span></span> <span data-ttu-id="935ad-156">Si configura un producto, no importa qué tipo de restricción se usa.</span><span class="sxs-lookup"><span data-stu-id="935ad-156">When you configure a product, it doesn't matter what kind of constraint is used.</span></span> <span data-ttu-id="935ad-157">El ejemplo siguiente muestra en qué se diferencian los dos métodos.</span><span class="sxs-lookup"><span data-stu-id="935ad-157">The following example shows how the two methods differ.</span></span>  

<span data-ttu-id="935ad-158">Si configura un producto mediante las configuraciones de restricciones siguientes, podrá hacer uso de estas combinaciones:</span><span class="sxs-lookup"><span data-stu-id="935ad-158">When you configure a product by using the following constraint setups, these combinations are allowed:</span></span>

-   <span data-ttu-id="935ad-159">Un producto de color negro y de tamaño 30 o 50</span><span class="sxs-lookup"><span data-stu-id="935ad-159">A product in the color Black, and in size 30 or 50</span></span>
-   <span data-ttu-id="935ad-160">Un producto de color rojo y de tamaño 20</span><span class="sxs-lookup"><span data-stu-id="935ad-160">A product in the color Red and in size 20</span></span>

### <a name="table-constraint-setup"></a><span data-ttu-id="935ad-161">Configuración de restricciones de tabla</span><span class="sxs-lookup"><span data-stu-id="935ad-161">Table constraint setup</span></span>

| <span data-ttu-id="935ad-162">Color</span><span class="sxs-lookup"><span data-stu-id="935ad-162">Color</span></span> | <span data-ttu-id="935ad-163">Tamaño</span><span class="sxs-lookup"><span data-stu-id="935ad-163">Size</span></span> |
|-------|------|
| <span data-ttu-id="935ad-164">Negro</span><span class="sxs-lookup"><span data-stu-id="935ad-164">Black</span></span> | <span data-ttu-id="935ad-165">30</span><span class="sxs-lookup"><span data-stu-id="935ad-165">30</span></span>   |
| <span data-ttu-id="935ad-166">Negro</span><span class="sxs-lookup"><span data-stu-id="935ad-166">Black</span></span> | <span data-ttu-id="935ad-167">50</span><span class="sxs-lookup"><span data-stu-id="935ad-167">50</span></span>   |
| <span data-ttu-id="935ad-168">Rojo</span><span class="sxs-lookup"><span data-stu-id="935ad-168">Red</span></span>   | <span data-ttu-id="935ad-169">20</span><span class="sxs-lookup"><span data-stu-id="935ad-169">20</span></span>   |

### <a name="expression-constraint-setup"></a><span data-ttu-id="935ad-170">Configuración de restricciones de expresión</span><span class="sxs-lookup"><span data-stu-id="935ad-170">Expression constraint setup</span></span>

<span data-ttu-id="935ad-171">(Color == "Negro" & (size == "30" | size == "50")) | (color == "Rojo" & size = "20")</span><span class="sxs-lookup"><span data-stu-id="935ad-171">(Color == "Black" & (size == "30" | size == "50")) | (color == "Red" & size = "20")</span></span>

## <a name="should-i-use-operators-or-infix-notation-when-i-write-expression-constraints"></a><span data-ttu-id="935ad-172">¿Se deben usar operadores o una notación de infijo al escribir las restricciones de expresión?</span><span class="sxs-lookup"><span data-stu-id="935ad-172">Should I use operators or infix notation when I write expression constraints?</span></span>
<span data-ttu-id="935ad-173">Se puede escribir una restricción de expresión mediante los operadores de prefijo disponibles, o bien mediante la notación de infijo.</span><span class="sxs-lookup"><span data-stu-id="935ad-173">You can write an expression constraint by using either the available prefix operators or infix notation.</span></span> <span data-ttu-id="935ad-174">Para los operadores **Min**, **Max** y **Abs** no puede usar una notación de infijo.</span><span class="sxs-lookup"><span data-stu-id="935ad-174">For the **Min**, **Max**, and **Abs** operators, you can't use infix notation.</span></span> <span data-ttu-id="935ad-175">Estos operadores se incluyen como operadores estándar en la mayoría de los lenguajes de programación.</span><span class="sxs-lookup"><span data-stu-id="935ad-175">These operators are included as standard operators in most programming languages.</span></span>

## <a name="what-operators-and-infix-notation-can-i-use-when-i-write-expression-constraints"></a><span data-ttu-id="935ad-176">¿Qué operadores o notaciones de infijo se pueden usar al escribir restricciones de expresión?</span><span class="sxs-lookup"><span data-stu-id="935ad-176">What operators and infix notation can I use when I write expression constraints?</span></span>
<span data-ttu-id="935ad-177">En las tablas siguientes se enumeran los operadores y la notación de infijo que se pueden utilizar al escribir la restricción de expresión de un componente en un modelo de configuración de productos.</span><span class="sxs-lookup"><span data-stu-id="935ad-177">The following tables list the operators and infix notation that you can use when you write an expression constraint for a component in a product configuration model.</span></span> <span data-ttu-id="935ad-178">Los ejemplos de la primera tabla muestran cómo escribir una expresión mediante la notación de infijo o los operadores.</span><span class="sxs-lookup"><span data-stu-id="935ad-178">The examples in the first table show how to write an expression by using either infix notation or operators.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="935ad-179">Operador</span><span class="sxs-lookup"><span data-stu-id="935ad-179">Operator</span></span></th>
<th><span data-ttu-id="935ad-180">Descripción</span><span class="sxs-lookup"><span data-stu-id="935ad-180">Description</span></span></th>
<th><span data-ttu-id="935ad-181">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="935ad-181">Syntax</span></span></th>
<th><span data-ttu-id="935ad-182">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="935ad-182">Examples</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="935ad-183">Implica</span><span class="sxs-lookup"><span data-stu-id="935ad-183">Implies</span></span></td>
<td><span data-ttu-id="935ad-184">Se aplica si la primera condición es falsa, la segunda condición es verdadera, o se dan ambas condiciones.</span><span class="sxs-lookup"><span data-stu-id="935ad-184">This is true if the first condition is false, the second condition is true, or both.</span></span></td>
<td><span data-ttu-id="935ad-185">Implies[a, b], infix: a -: b</span><span class="sxs-lookup"><span data-stu-id="935ad-185">Implies[a, b], infix: a -: b</span></span></td>
<td><ul>
<li><span data-ttu-id="935ad-186"><strong>Operador:</strong> Implies[x != 0, y &gt;= 0]</span><span class="sxs-lookup"><span data-stu-id="935ad-186"><strong>Operator:</strong> Implies[x != 0, y &gt;= 0]</span></span></li>
<li><span data-ttu-id="935ad-187"><strong>Notación de infijo:</strong> x != 0 -: y &gt;= 0</span><span class="sxs-lookup"><span data-stu-id="935ad-187"><strong>Infix notation:</strong> x != 0 -: y &gt;= 0</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="935ad-188">Y</span><span class="sxs-lookup"><span data-stu-id="935ad-188">And</span></span></td>
<td><span data-ttu-id="935ad-189">Se aplica solo si todas las condiciones son verdaderas.</span><span class="sxs-lookup"><span data-stu-id="935ad-189">This is true only if all conditions are true.</span></span> <span data-ttu-id="935ad-190">Si el número de condiciones es 0 (cero), da lugar a <strong>True</strong>.</span><span class="sxs-lookup"><span data-stu-id="935ad-190">If the number of conditions is 0 (zero), it produces <strong>True</strong>.</span></span></td>
<td><span data-ttu-id="935ad-191">And[args], infix: a &amp; b &amp; ... &amp; z</span><span class="sxs-lookup"><span data-stu-id="935ad-191">And[args], infix: a &amp; b &amp; ... &amp; z</span></span></td>
<td><ul>
<li><span data-ttu-id="935ad-192"><strong>Operador:</strong> And[x == 2, y &lt;= 2]</span><span class="sxs-lookup"><span data-stu-id="935ad-192"><strong>Operator:</strong> And[x == 2, y &lt;= 2]</span></span></li>
<li><span data-ttu-id="935ad-193"><strong>Notación de infijo:</strong> x == 2 &amp; y &lt;= 2</span><span class="sxs-lookup"><span data-stu-id="935ad-193"><strong>Infix notation:</strong> x == 2 &amp; y &lt;= 2</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="935ad-194">O</span><span class="sxs-lookup"><span data-stu-id="935ad-194">Or</span></span></td>
<td><span data-ttu-id="935ad-195">Se aplica si cualquier condición es verdadera.</span><span class="sxs-lookup"><span data-stu-id="935ad-195">This is true if any condition is true.</span></span> <span data-ttu-id="935ad-196">Si el número de condiciones es 0 (cero), da lugar a <strong>False</strong>.</span><span class="sxs-lookup"><span data-stu-id="935ad-196">If the number of conditions is 0 (zero), it produces <strong>False</strong>.</span></span></td>
<td><span data-ttu-id="935ad-197">Or[args], infix: a | b | ... | z</span><span class="sxs-lookup"><span data-stu-id="935ad-197">Or[args], infix: a | b | ... | z</span></span></td>
<td><ul>
<li><span data-ttu-id="935ad-198"><strong>Operador:</strong> Or[x == 2, y &lt;= 2]</span><span class="sxs-lookup"><span data-stu-id="935ad-198"><strong>Operator:</strong> Or[x == 2, y &lt;= 2]</span></span></li>
<li><span data-ttu-id="935ad-199"><strong>Notación de infijo:</strong> x == 2 | y &lt;= 2</span><span class="sxs-lookup"><span data-stu-id="935ad-199"><strong>Infix notation:</strong> x == 2 | y &lt;= 2</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="935ad-200">Más</span><span class="sxs-lookup"><span data-stu-id="935ad-200">Plus</span></span></td>
<td><span data-ttu-id="935ad-201">Esto suma sus condiciones.</span><span class="sxs-lookup"><span data-stu-id="935ad-201">This sums its conditions.</span></span> <span data-ttu-id="935ad-202">Si el número de condiciones es 0 (cero), da lugar a <strong>0</strong>.</span><span class="sxs-lookup"><span data-stu-id="935ad-202">If the number of conditions is 0 (zero), it produces <strong>0</strong>.</span></span></td>
<td><span data-ttu-id="935ad-203">Plus[args], infix: a + b + ... + z</span><span class="sxs-lookup"><span data-stu-id="935ad-203">Plus[args], infix: a + b + ... + z</span></span></td>
<td><ul>
<li><span data-ttu-id="935ad-204"><strong>Operador</strong>: Plus[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="935ad-204"><strong>Operator:</strong> Plus[x, y, 2] == z</span></span></li>
<li><span data-ttu-id="935ad-205"><strong>Notación de infijo</strong>: x + y + 2 == z</span><span class="sxs-lookup"><span data-stu-id="935ad-205"><strong>Infix notation:</strong> x + y + 2 == z</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="935ad-206">Menos</span><span class="sxs-lookup"><span data-stu-id="935ad-206">Minus</span></span></td>
<td><span data-ttu-id="935ad-207">Esto establece su argumento como negativo.</span><span class="sxs-lookup"><span data-stu-id="935ad-207">This negates its argument.</span></span> <span data-ttu-id="935ad-208">Debe tener exactamente una condición.</span><span class="sxs-lookup"><span data-stu-id="935ad-208">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="935ad-209">Minus[expr], infix: -expr</span><span class="sxs-lookup"><span data-stu-id="935ad-209">Minus[expr], infix: -expr</span></span></td>
<td><ul>
<li><span data-ttu-id="935ad-210"><strong>Operador:</strong> Minus[x] == y</span><span class="sxs-lookup"><span data-stu-id="935ad-210"><strong>Operator:</strong> Minus[x] == y</span></span></li>
<li><span data-ttu-id="935ad-211"><strong>Notación de infijo:</strong> -x == y</span><span class="sxs-lookup"><span data-stu-id="935ad-211"><strong>Infix notation:</strong> -x == y</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="935ad-212">Abs</span><span class="sxs-lookup"><span data-stu-id="935ad-212">Abs</span></span></td>
<td><span data-ttu-id="935ad-213">Toma el valor absoluto de la condición.</span><span class="sxs-lookup"><span data-stu-id="935ad-213">This takes the absolute value of its condition.</span></span> <span data-ttu-id="935ad-214">Debe tener exactamente una condición.</span><span class="sxs-lookup"><span data-stu-id="935ad-214">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="935ad-215">Abs[expr]</span><span class="sxs-lookup"><span data-stu-id="935ad-215">Abs[expr]</span></span></td>
<td><span data-ttu-id="935ad-216"><strong>Operador</strong>: Abs[x]</span><span class="sxs-lookup"><span data-stu-id="935ad-216"><strong>Operator:</strong> Abs[x]</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="935ad-217">Horas</span><span class="sxs-lookup"><span data-stu-id="935ad-217">Times</span></span></td>
<td><span data-ttu-id="935ad-218">Toma el producto de sus condiciones.</span><span class="sxs-lookup"><span data-stu-id="935ad-218">This takes the product of its conditions.</span></span> <span data-ttu-id="935ad-219">Si el número de condiciones es 0 (cero), da lugar a <strong>1</strong>.</span><span class="sxs-lookup"><span data-stu-id="935ad-219">If the number of conditions is 0 (zero), it produces <strong>1</strong>.</span></span></td>
<td><span data-ttu-id="935ad-220">Times[args], infix: a \* b \* ... \* z</span><span class="sxs-lookup"><span data-stu-id="935ad-220">Times[args], infix: a \* b \* ... \* z</span></span></td>
<td><ul>
<li><span data-ttu-id="935ad-221"><strong>Operador:</strong> Times[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="935ad-221"><strong>Operator:</strong> Times[x, y, 2] == z</span></span></li>
<li><span data-ttu-id="935ad-222"><strong>Notación de infijo:</strong> x \* y \* 2 == z</span><span class="sxs-lookup"><span data-stu-id="935ad-222"><strong>Infix notation:</strong> x \* y \* 2 == z</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="935ad-223">Inicio/apagado</span><span class="sxs-lookup"><span data-stu-id="935ad-223">Power</span></span></td>
<td><span data-ttu-id="935ad-224">Toma un exponencial.</span><span class="sxs-lookup"><span data-stu-id="935ad-224">This takes an exponential.</span></span> <span data-ttu-id="935ad-225">Aplica la potencia de derecha a izquierda.</span><span class="sxs-lookup"><span data-stu-id="935ad-225">It applies exponentiation from right to left.</span></span> <span data-ttu-id="935ad-226">(Es decir, es asociativo a la derecha). Por tanto, <strong>Power[a, b, c]</strong> es equivalente a <strong>Power[a, Power[b, c]]</strong>.</span><span class="sxs-lookup"><span data-stu-id="935ad-226">(In other words, it&#39;s right-associative.) Therefore, <strong>Power[a, b, c]</strong> is equivalent to <strong>Power[a, Power[b, c]]</strong>.</span></span> <span data-ttu-id="935ad-227"><strong>Power</strong> solo se puede usar si el exponente es una constante positiva.</span><span class="sxs-lookup"><span data-stu-id="935ad-227"><strong>Power</strong> can be used only if the exponent is a positive constant.</span></span></td>
<td><span data-ttu-id="935ad-228">Power[args], infix: a ^ b ^ ... ^ z</span><span class="sxs-lookup"><span data-stu-id="935ad-228">Power[args], infix: a ^ b ^ ... ^ z</span></span></td>
<td><ul>
<li><span data-ttu-id="935ad-229"><strong>Operador:</strong> Power[x, 2] == y</span><span class="sxs-lookup"><span data-stu-id="935ad-229"><strong>Operator:</strong> Power[x, 2] == y</span></span></li>
<li><span data-ttu-id="935ad-230"><strong>Notación de infijo:</strong> x ^ 2 == y</span><span class="sxs-lookup"><span data-stu-id="935ad-230"><strong>Infix notation:</strong> x ^ 2 == y</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="935ad-231">Máx.</span><span class="sxs-lookup"><span data-stu-id="935ad-231">Max</span></span></td>
<td><span data-ttu-id="935ad-232">Produce la condición mayor.</span><span class="sxs-lookup"><span data-stu-id="935ad-232">This produces the largest condition.</span></span> <span data-ttu-id="935ad-233">Si el número de condiciones es 0 (cero), produce <strong>Infinity</strong>.</span><span class="sxs-lookup"><span data-stu-id="935ad-233">If the number of conditions is 0 (zero), it produces <strong>Infinity</strong>.</span></span></td>
<td><span data-ttu-id="935ad-234">Max[args]</span><span class="sxs-lookup"><span data-stu-id="935ad-234">Max[args]</span></span></td>
<td><span data-ttu-id="935ad-235"><strong>Operador:</strong> Max[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="935ad-235"><strong>Operator:</strong> Max[x, y, 2] == z</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="935ad-236">Mín.</span><span class="sxs-lookup"><span data-stu-id="935ad-236">Min</span></span></td>
<td><span data-ttu-id="935ad-237">Produce la condición más pequeña.</span><span class="sxs-lookup"><span data-stu-id="935ad-237">This produces the smallest condition.</span></span> <span data-ttu-id="935ad-238">Si el número de condiciones es 0 (cero), produce <strong>Infinity</strong>.</span><span class="sxs-lookup"><span data-stu-id="935ad-238">If the number of conditions is 0 (zero), it produces <strong>Infinity</strong>.</span></span></td>
<td><span data-ttu-id="935ad-239">Min[args]</span><span class="sxs-lookup"><span data-stu-id="935ad-239">Min[args]</span></span></td>
<td><span data-ttu-id="935ad-240"><strong>Operador:</strong> Min[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="935ad-240"><strong>Operator:</strong> Min[x, y, 2] == z</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="935ad-241">No</span><span class="sxs-lookup"><span data-stu-id="935ad-241">Not</span></span></td>
<td><span data-ttu-id="935ad-242">Produce el contrario lógico de la condición.</span><span class="sxs-lookup"><span data-stu-id="935ad-242">This produces the logical inverse of its condition.</span></span> <span data-ttu-id="935ad-243">Debe tener exactamente una condición.</span><span class="sxs-lookup"><span data-stu-id="935ad-243">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="935ad-244">Not[expr], infix: !expr</span><span class="sxs-lookup"><span data-stu-id="935ad-244">Not[expr], infix: !expr</span></span></td>
<td><ul>
<li><span data-ttu-id="935ad-245"><strong>Operador:</strong> Not[x] &amp; Not[y == 3]</span><span class="sxs-lookup"><span data-stu-id="935ad-245"><strong>Operator:</strong> Not[x] &amp; Not[y == 3]</span></span></li>
<li><span data-ttu-id="935ad-246"><strong>Notación de infijo:</strong> !x!(y == 3)</span><span class="sxs-lookup"><span data-stu-id="935ad-246"><strong>Infix notation:</strong> !x!(y == 3)</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="935ad-247">Los ejemplos en la siguiente tabla muestran cómo escribir una notación de infijo.</span><span class="sxs-lookup"><span data-stu-id="935ad-247">The examples in the next table show how to write infix notation.</span></span>


|  <span data-ttu-id="935ad-248">Notación de infijo</span><span class="sxs-lookup"><span data-stu-id="935ad-248">Infix notation</span></span>   |                                          <span data-ttu-id="935ad-249">Descripción</span><span class="sxs-lookup"><span data-stu-id="935ad-249">Description</span></span>                                          |
|-------------------|-----------------------------------------------------------------------------------------------|
|     <span data-ttu-id="935ad-250">x + y + z</span><span class="sxs-lookup"><span data-stu-id="935ad-250">x + y + z</span></span>     |                                           <span data-ttu-id="935ad-251">Adición</span><span class="sxs-lookup"><span data-stu-id="935ad-251">Addition</span></span>                                            |
|    <span data-ttu-id="935ad-252">x \* y \* z</span><span class="sxs-lookup"><span data-stu-id="935ad-252">x \* y \* z</span></span>    |                                        <span data-ttu-id="935ad-253">Multiplicación</span><span class="sxs-lookup"><span data-stu-id="935ad-253">Multiplication</span></span>                                         |
|       <span data-ttu-id="935ad-254">x - y</span><span class="sxs-lookup"><span data-stu-id="935ad-254">x - y</span></span>       | <span data-ttu-id="935ad-255">La resta binaria se traduce de la misma forma que la adición binaria donde hay un segundo negativo.</span><span class="sxs-lookup"><span data-stu-id="935ad-255">Binary subtraction is translated the same as binary addition where there is a negated second.</span></span> |
|     <span data-ttu-id="935ad-256">x ^ y ^ z</span><span class="sxs-lookup"><span data-stu-id="935ad-256">x ^ y ^ z</span></span>     |                          <span data-ttu-id="935ad-257">Exponenciación con asociación a la derecha</span><span class="sxs-lookup"><span data-stu-id="935ad-257">Exponentiation that has right associativity</span></span>                          |
|        <span data-ttu-id="935ad-258">!x</span><span class="sxs-lookup"><span data-stu-id="935ad-258">!x</span></span>         |                                          <span data-ttu-id="935ad-259">No booleano</span><span class="sxs-lookup"><span data-stu-id="935ad-259">Boolean not</span></span>                                          |
|      <span data-ttu-id="935ad-260">x -: y</span><span class="sxs-lookup"><span data-stu-id="935ad-260">x -: y</span></span>       |                                      <span data-ttu-id="935ad-261">Implicación booleano</span><span class="sxs-lookup"><span data-stu-id="935ad-261">Boolean implication</span></span>                                      |
|         <span data-ttu-id="935ad-262">x</span><span class="sxs-lookup"><span data-stu-id="935ad-262">x</span></span>         |                                               <span data-ttu-id="935ad-263">y</span><span class="sxs-lookup"><span data-stu-id="935ad-263">y</span></span>                                               |
|     <span data-ttu-id="935ad-264">x & y & z</span><span class="sxs-lookup"><span data-stu-id="935ad-264">x & y & z</span></span>     |                                          <span data-ttu-id="935ad-265">Booleano y</span><span class="sxs-lookup"><span data-stu-id="935ad-265">Boolean and</span></span>                                          |
|    <span data-ttu-id="935ad-266">x == y == z</span><span class="sxs-lookup"><span data-stu-id="935ad-266">x == y == z</span></span>    |                                           <span data-ttu-id="935ad-267">Igualdad</span><span class="sxs-lookup"><span data-stu-id="935ad-267">Equality</span></span>                                            |
|    <span data-ttu-id="935ad-268">x != y != z</span><span class="sxs-lookup"><span data-stu-id="935ad-268">x != y != z</span></span>    |                                           <span data-ttu-id="935ad-269">Distinto</span><span class="sxs-lookup"><span data-stu-id="935ad-269">Distinct</span></span>                                            |
|  <span data-ttu-id="935ad-270">x &lt; y &lt; z</span><span class="sxs-lookup"><span data-stu-id="935ad-270">x &lt; y &lt; z</span></span>  |                                           <span data-ttu-id="935ad-271">Menor que</span><span class="sxs-lookup"><span data-stu-id="935ad-271">Less than</span></span>                                           |
|  <span data-ttu-id="935ad-272">x &gt; y &gt; z</span><span class="sxs-lookup"><span data-stu-id="935ad-272">x &gt; y &gt; z</span></span>  |                                         <span data-ttu-id="935ad-273">Mayor que</span><span class="sxs-lookup"><span data-stu-id="935ad-273">Greater than</span></span>                                          |
| <span data-ttu-id="935ad-274">x &lt;= y &lt;= z</span><span class="sxs-lookup"><span data-stu-id="935ad-274">x &lt;= y &lt;= z</span></span> |                                     <span data-ttu-id="935ad-275">Inferior a o igual a</span><span class="sxs-lookup"><span data-stu-id="935ad-275">Less than or equal to</span></span>                                     |
| <span data-ttu-id="935ad-276">x &gt;= y &gt;= z</span><span class="sxs-lookup"><span data-stu-id="935ad-276">x &gt;= y &gt;= z</span></span> |                                   <span data-ttu-id="935ad-277">Superior a o igual a</span><span class="sxs-lookup"><span data-stu-id="935ad-277">Greater than or equal to</span></span>                                    |
|        <span data-ttu-id="935ad-278">(x)</span><span class="sxs-lookup"><span data-stu-id="935ad-278">(x)</span></span>        |                           <span data-ttu-id="935ad-279">El paréntesis anula la prioridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="935ad-279">Parentheses override default precedence.</span></span>                            |

## <a name="why-arent-my-expression-constraints-validated-correctly"></a><span data-ttu-id="935ad-280">¿Por qué las restricciones de expresión no se validan correctamente?</span><span class="sxs-lookup"><span data-stu-id="935ad-280">Why aren't my expression constraints validated correctly?</span></span>
<span data-ttu-id="935ad-281">No se pueden usar palabras clave reservadas como nombres del solucionador de atributos, componentes o subcomponentes en un modelo de configuración de productos.</span><span class="sxs-lookup"><span data-stu-id="935ad-281">You can't use reserved keywords as solver names for attributes, components, or subcomponents in a product configuration model.</span></span> <span data-ttu-id="935ad-282">A continuación se muestra una lista de palabras clave reservadas que no se pueden usar:</span><span class="sxs-lookup"><span data-stu-id="935ad-282">Here is a list of the reserved keywords that you can't use:</span></span>

-   <span data-ttu-id="935ad-283">Techo</span><span class="sxs-lookup"><span data-stu-id="935ad-283">Ceiling</span></span>
-   <span data-ttu-id="935ad-284">Elemento</span><span class="sxs-lookup"><span data-stu-id="935ad-284">Element</span></span>
-   <span data-ttu-id="935ad-285">Igual</span><span class="sxs-lookup"><span data-stu-id="935ad-285">Equal</span></span>
-   <span data-ttu-id="935ad-286">Piso</span><span class="sxs-lookup"><span data-stu-id="935ad-286">Floor</span></span>
-   <span data-ttu-id="935ad-287">Si</span><span class="sxs-lookup"><span data-stu-id="935ad-287">If</span></span>
-   <span data-ttu-id="935ad-288">Menor</span><span class="sxs-lookup"><span data-stu-id="935ad-288">Less</span></span>
-   <span data-ttu-id="935ad-289">Mayor</span><span class="sxs-lookup"><span data-stu-id="935ad-289">Greater</span></span>
-   <span data-ttu-id="935ad-290">Implica</span><span class="sxs-lookup"><span data-stu-id="935ad-290">Implies</span></span>
-   <span data-ttu-id="935ad-291">Registro</span><span class="sxs-lookup"><span data-stu-id="935ad-291">Log</span></span>
-   <span data-ttu-id="935ad-292">Máx.</span><span class="sxs-lookup"><span data-stu-id="935ad-292">Max</span></span>
-   <span data-ttu-id="935ad-293">Mín.</span><span class="sxs-lookup"><span data-stu-id="935ad-293">Min</span></span>
-   <span data-ttu-id="935ad-294">Menos</span><span class="sxs-lookup"><span data-stu-id="935ad-294">Minus</span></span>
-   <span data-ttu-id="935ad-295">Más</span><span class="sxs-lookup"><span data-stu-id="935ad-295">Plus</span></span>
-   <span data-ttu-id="935ad-296">Potencia</span><span class="sxs-lookup"><span data-stu-id="935ad-296">Power</span></span>
-   <span data-ttu-id="935ad-297">Tiempos</span><span class="sxs-lookup"><span data-stu-id="935ad-297">Times</span></span>
-   <span data-ttu-id="935ad-298">Ranura</span><span class="sxs-lookup"><span data-stu-id="935ad-298">Slot</span></span>
-   <span data-ttu-id="935ad-299">Modelo</span><span class="sxs-lookup"><span data-stu-id="935ad-299">Model</span></span>
-   <span data-ttu-id="935ad-300">Decisión</span><span class="sxs-lookup"><span data-stu-id="935ad-300">Decision</span></span>
-   <span data-ttu-id="935ad-301">Objetivo</span><span class="sxs-lookup"><span data-stu-id="935ad-301">Goal</span></span>


<a name="additional-resources"></a><span data-ttu-id="935ad-302">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="935ad-302">Additional resources</span></span>
--------

[<span data-ttu-id="935ad-303">Crear una restricción de expresión</span><span class="sxs-lookup"><span data-stu-id="935ad-303">Create an expression constraint</span></span>](tasks/add-expression-constraint-product-configuration-model.md)

[<span data-ttu-id="935ad-304">Agregar un cálculo a un modelo de configuración de producto</span><span class="sxs-lookup"><span data-stu-id="935ad-304">Add a calculation to a product configuration model</span></span>](tasks/add-calculation-product-configuration-model.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]