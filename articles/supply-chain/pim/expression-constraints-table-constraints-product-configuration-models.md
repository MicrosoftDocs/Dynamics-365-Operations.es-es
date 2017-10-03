---
title: "Restricciones de expresión y tabla en modelos de configuración de productos"
description: "En este tema se describe el uso de las restricciones de expresión y las restricciones de tabla. Las restricciones controlan los valores de atributo que puede seleccionar al configurar los productos para un pedido de ventas, un presupuesto de ventas, un pedido de compra o un pedido de producción. Puede usar las restricciones de expresión o las restricciones de tablas, en función de cómo prefiere crear las restricciones."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCGlobalTableConstraintEdit, PCProductConfigurationModelDetails, PCTableConstraintAttachAttributeTree, PCTableConstraintDefinition
audience: Application User
ms.reviewer: YuyuScheller
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

# <a name="expression-constraints-and-table-constraints-in-product-configuration-models"></a>Restricciones de expresión y tabla en modelos de configuración de productos

[!include[banner](../includes/banner.md)]


En este tema se describe el uso de las restricciones de expresión y las restricciones de tabla. Las restricciones controlan los valores de atributo que puede seleccionar al configurar los productos para un pedido de ventas, un presupuesto de ventas, un pedido de compra o un pedido de producción. Puede usar las restricciones de expresión o las restricciones de tablas, en función de cómo prefiere crear las restricciones. 

Las restricciones se usan para controlar los valores de atributo que puede seleccionar al configurar los productos para un pedido de ventas, un presupuesto de ventas, un pedido de compra o un pedido de producción. Puede usar las restricciones de expresión o las restricciones de tablas, en función de cómo prefiere crear las restricciones.

## <a name="what-are-expression-constraints"></a>¿Qué son las restricciones de expresión?
Las restricciones de expresión se caracterizan por una expresión que utiliza operadores y funciones aritméticas y booleano. Una restricción de expresión para un componente concreto se escribe en un modelo de configuración de productos. No puede volver a utilizarse ni compartirse con otro componente. Sin embargo, las restricciones de expresión de un componente pueden hacer referencia a los atributos de los subcomponentes del componente.

## <a name="what-are-table-constraints"></a>¿Qué son las restricciones de tabla?
Las restricciones de tabla muestran las combinaciones de valores permitidas para los atributos cuando configura un producto. Las definiciones de la restricción de tabla se pueden usar genéricamente. Cuando se crea una restricción de tabla para un componente en un modelo de configuración de productos, selecciona una definición de restricción de tabla. Para crear las combinaciones permitidas, agrega atributos de tipos específicos a los componentes. Cada tipo de atributo tiene un valor específico.

### <a name="example-of-a-table-constraint"></a>Ejemplo de una restricción de tablas

Este ejemplo muestra cómo puede limitar la configuración de un altavoz según acabados de caja y frontales específicos. La primera tabla muestra los acabados de caja y frontales que suelen estar disponibles para la configuración. Hay valores definidos para los tipos de atributos **Acabado de la caja** y **Rejilla delantera**.

| Tipo de atributo | Valores                      |
|----------------|-----------------------------|
| Acabado de la caja | Negro, roble, palo de rosa y blanco |
| Rejilla delantera    | Negro, metálico y blanco         |

La tabla siguiente muestra las combinaciones definidas por la restricción de tabla **Color y acabado**. Con esta restricción de tabla puede configurar un altavoz que tenga un acabado de roble y una rejilla negra, un acabado de palisandro y una rejilla blanca, etc.

| Finalizar         | Rejilla                       |
|----------------|-----------------------------|
| Roble            | Negro                       |
| Palisandro       | Blanco                       |
| Blanco          | Negro                       |
| Blanco          | Blanco                       |
| Negro          | Negro                       |
| Negro          | Metálico                       | 

Puede crear restricciones de tablas definidas por el sistema y definidas por el usuario. Para obtener más información, consulte [Restricciones de tablas definidas por el usuario o definidas por el sistema](system-defined-user-defined-table-constraints.md).

## <a name="what-syntax-should-be-used-to-write-constraints"></a>¿Qué sintaxis debe usarse para resolver restricciones de escritura?
Debe utilizar la sintaxis del lenguaje de modelado de optimización (OML) para escribir las restricciones. El sistema utiliza Microsoft Microsoft Solver Foundation para solucionar las restricciones.

## <a name="should-i-use-table-constraints-or-expression-constraints"></a>¿Se deben usar restricciones de tablas o restricciones de expresión?
Puede usar restricciones de expresión o restricciones de tablas, en función de cómo prefiere crear las restricciones. Una restricción de tabla se crea como una matriz, mientras que una restricción de expresión es una sentencia individual. Si configura un producto, no importa qué tipo de restricción se usa. El ejemplo siguiente muestra en qué se diferencian los dos métodos.  

Si configura un producto mediante las configuraciones de restricciones siguientes, podrá hacer uso de estas combinaciones:

-   Un producto de color negro y de tamaño 30 o 50
-   Un producto de color rojo y de tamaño 20

### <a name="table-constraint-setup"></a>Configuración de restricciones de tabla

| Color | Tamaño |
|-------|------|
| Negro | 30   |
| Negro | 50   |
| Rojo   | 20   |

### <a name="expression-constraint-setup"></a>Configuración de restricciones de expresión

(Color == "Negro" & (size == "30" | size == "50")) | (color == "Rojo" & size = "20")

## <a name="should-i-use-operators-or-infix-notation-when-i-write-expression-constraints"></a>¿Se deben usar operadores o una notación de infijo al escribir las restricciones de expresión?
Se puede escribir una restricción de expresión mediante los operadores de prefijo disponibles, o bien mediante la notación de infijo. Para los operadores **Min**, **Max** y **Abs** no puede usar una notación de infijo. Estos operadores se incluyen como operadores estándar en la mayoría de los lenguajes de programación.

## <a name="what-operators-and-infix-notation-can-i-use-when-i-write-expression-constraints"></a>¿Qué operadores o notaciones de infijo se pueden usar al escribir restricciones de expresión?
En las tablas siguientes se enumeran los operadores y la notación de infijo que se pueden utilizar al escribir la restricción de expresión de un componente en un modelo de configuración de productos. Los ejemplos de la primera tabla muestran cómo escribir una expresión mediante la notación de infijo o los operadores.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Operador</th>
<th>Descripción</th>
<th>Sintaxis</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Implica</td>
<td>Se aplica si la primera condición es falsa, la segunda condición es verdadera, o se dan ambas condiciones.</td>
<td>Implies[a, b], infix: a -: b</td>
<td><ul>
<li><strong>Operador:</strong> Implies[x != 0, y &gt;= 0]</li>
<li><strong>Notación de infijo:</strong> x != 0 -: y &gt;= 0</li>
</ul></td>
</tr>
<tr class="even">
<td>Y</td>
<td>Se aplica solo si todas las condiciones son verdaderas. Si el número de condiciones es 0 (cero), da lugar a <strong>True</strong>.</td>
<td>And[args], infix: a &amp; b &amp; ... &amp; z</td>
<td><ul>
<li><strong>Operador:</strong> And[x == 2, y &lt;= 2]</li>
<li><strong>Notación de infijo:</strong> x == 2 &amp; y &lt;= 2</li>
</ul></td>
</tr>
<tr class="odd">
<td>O</td>
<td>Se aplica si cualquier condición es verdadera. Si el número de condiciones es 0 (cero), da lugar a <strong>False</strong>.</td>
<td>Or[args], infix: a | b | ... | z</td>
<td><ul>
<li><strong>Operador:</strong> Or[x == 2, y &lt;= 2]</li>
<li><strong>Notación de infijo:</strong> x == 2 | y &lt;= 2</li>
</ul></td>
</tr>
<tr class="even">
<td>Más</td>
<td>Esto suma sus condiciones. Si el número de condiciones es 0 (cero), da lugar a <strong>0</strong>.</td>
<td>Plus[args], infix: a + b + ... + z</td>
<td><ul>
<li><strong>Operador</strong>: Plus[x, y, 2] == z</li>
<li><strong>Notación de infijo</strong>: x + y + 2 == z</li>
</ul></td>
</tr>
<tr class="odd">
<td>Menos</td>
<td>Esto establece su argumento como negativo. Debe tener exactamente una condición.</td>
<td>Minus[expr], infix: -expr</td>
<td><ul>
<li><strong>Operador:</strong> Minus[x] == y</li>
<li><strong>Notación de infijo:</strong> -x == y</li>
</ul></td>
</tr>
<tr class="even">
<td>Abs</td>
<td>Toma el valor absoluto de la condición. Debe tener exactamente una condición.</td>
<td>Abs[expr]</td>
<td><strong>Operador</strong>: Abs[x]</td>
</tr>
<tr class="odd">
<td>Horas</td>
<td>Toma el producto de sus condiciones. Si el número de condiciones es 0 (cero), da lugar a <strong>1</strong>.</td>
<td>Times[args], infix: a * b * ... * z</td>
<td><ul>
<li><strong>Operador:</strong> Times[x, y, 2] == z</li>
<li><strong>Notación de infijo:</strong> x * y * 2 == z</li>
</ul></td>
</tr>
<tr class="even">
<td>Inicio/apagado</td>
<td>Toma un exponencial. Aplica la potencia de derecha a izquierda. (Es decir, es asociativo a la derecha). Por tanto, <strong>Power[a, b, c]</strong> es equivalente a <strong>Power[a, Power[b, c]]</strong>. <strong>Power</strong> solo se puede usar si el exponente es una constante positiva.</td>
<td>Power[args], infix: a ^ b ^ ... ^ z</td>
<td><ul>
<li><strong>Operador:</strong> Power[x, 2] == y</li>
<li><strong>Notación de infijo:</strong> x ^ 2 == y</li>
</ul></td>
</tr>
<tr class="odd">
<td>Máx.</td>
<td>Produce la condición mayor. Si el número de condiciones es 0 (cero), produce <strong>Infinity</strong>.</td>
<td>Max[args]</td>
<td><strong>Operador:</strong> Max[x, y, 2] == z</td>
</tr>
<tr class="even">
<td>Mín.</td>
<td>Produce la condición más pequeña. Si el número de condiciones es 0 (cero), produce <strong>Infinity</strong>.</td>
<td>Min[args]</td>
<td><strong>Operador:</strong> Min[x, y, 2] == z</td>
</tr>
<tr class="odd">
<td>No</td>
<td>Produce el contrario lógico de la condición. Debe tener exactamente una condición.</td>
<td>Not[expr], infix: !expr</td>
<td><ul>
<li><strong>Operador:</strong> Not[x] &amp; Not[y == 3]</li>
<li><strong>Notación de infijo:</strong> !x!(y == 3)</li>
</ul></td>
</tr>
</tbody>
</table>

Los ejemplos en la siguiente tabla muestran cómo escribir una notación de infijo.

| Notación de infijo    | Descripción                                                                                   |
|-------------------|-----------------------------------------------------------------------------------------------|
| x + y + z         | Adición                                                                                      |
| x \* y \* z       | Multiplicación                                                                                |
| x - y             | La resta binaria se traduce de la misma forma que la adición binaria donde hay un segundo negativo. |
| x ^ y ^ z         | Exponenciación con asociación a la derecha                                                   |
| !x                | No booleano                                                                                   |
| x -: y            | Implicación booleano                                                                           |
| x | y | z         | Booleano o                                                                                    |
| x & y & z         | Booleano y                                                                                   |
| x == y == z       | Igualdad                                                                                      |
| x != y != z       | Distinto                                                                                      |
| x &lt; y &lt; z   | Menor que                                                                                     |
| x &gt; y &gt; z   | Mayor que                                                                                  |
| x &lt;= y &lt;= z | Inferior a o igual a                                                                         |
| x &gt;= y &gt;= z | Superior a o igual a                                                                      |
| (x)               | El paréntesis anula la prioridad predeterminada.                                                      |

## <a name="why-arent-my-expression-constraints-validated-correctly"></a>¿Por qué las restricciones de expresión no se validan correctamente?
No se pueden usar palabras clave reservadas como nombres del solucionador de atributos, componentes o subcomponentes en un modelo de configuración de productos. A continuación se muestra una lista de palabras clave reservadas que no se pueden usar:

-   Techo
-   Elemento
-   Igual
-   Piso
-   Si
-   Menor
-   Mayor
-   Implica
-   Registro
-   Máx.
-   Mín.
-   Menos
-   Más
-   Potencia
-   Tiempos
-   Ranura
-   Modelo
-   Decisión
-   Objetivo


<a name="see-also"></a>Consulte también
--------

[Crear una restricción de expresión (guía de tareas)(/dynamics365/unified-operations/supply-chain/pim/tasks/add-expression-constraint-product-configuration-model)

[Agregar un cálculo a un modelo de configuración de producto (guía de tareas)](/dynamics365/unified-operations/supply-chain/pim/tasks/add-calculation-product-configuration-model)




