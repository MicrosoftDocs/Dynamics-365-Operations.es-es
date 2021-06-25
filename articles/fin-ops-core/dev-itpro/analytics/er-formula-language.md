---
title: Idioma de fórmulas en los informes electrónicos
description: Este tema proporciona información general sobre cómo usar el idioma de fórmulas en los informes electrónicos (ER).
author: NickSelin
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 470b4fa1c8b15ae4a9e9ebef81af9e4ca107422d
ms.sourcegitcommit: 15aacd0e109b05c7281407b5bba4e6cd99116c28
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "6223995"
---
# <a name="electronic-reporting-formula-language"></a>Idioma de fórmulas en los informes electrónicos

[!include [banner](../includes/banner.md)]

Los informes electrónicos (ER) proporcionan una potente experiencia de transformación de datos. El lenguaje que se usa para expresar las manipulaciones de datos requeridas en el [diseñador de fórmulas ER](general-electronic-reporting-formula-designer.md) se asemeja al lenguaje de fórmulas en Microsoft Excel.

## <a name="basic-syntax"></a>Sintaxis básica

Las expresiones de ER pueden contener todo los elementos siguientes o cualquiera de ellos:

- [Constantes](#Constants)
- [Operadores](#Operators)
- [Referencias](#References)
- [Rutas](#Paths)
- [Funciones](#Functions)

## <a name="constants"></a><a name="Constants"></a>Constantes

Cuando diseñe expresiones, puede usar constantes de texto y numéricas (es decir, valores que no se calculan). Por ejemplo, la expresión `VALUE ("100") + 20` usa la constante numérica **20** y la constante de cadena **“100”** y devuelve el valor numérico **120**.

El diseñador de fórmulas de ER admite secuencias de escape. Por lo tanto, puede especificar una cadena de expresión que debe gestionarse de forma diferente. Por ejemplo, la expresión `"Leo Tolstoy ""War and Peace"" Volume 1"` devuelve la cadena de texto **Leo Tolstoi "Guerra y paz" Volumen 1**.

## <a name="operators"></a><a name="Operators"></a>Operadores

La tabla siguiente muestra los operadores aritméticos que puede usar para realizar operaciones matemáticas básicas, como suma, resta, multiplicación y división.

| Operador | Significado               | Ejemplo     |
|----------|-----------------------|-------------|
| +        | Adición              | `1+2`       |
| -        | Resta, negación | `5-2`, `-1` |
| \*       | Multiplicación        | `7\*8`      |
| /        | División              | `9/3`       |

La tabla siguiente muestra los operadores de comparación que se admiten. Puede utilizar estos operadores para comparar dos valores.

| Operador | Significado                  | Ejemplo      |
|----------|--------------------------|--------------|
| =        | Igual                    | `X=Y`        |
| &gt;     | Mayor que             | `X>Y`        |
| &lt;     | Menor que                | `X<Y`        |
| &gt;=    | Mayor a o igual a | `X>=Y`       |
| &lt;=    | Menor o igual a    | `X<=Y`       |
| &lt;&gt; | No igual que             | `X<>Y`       |

Además, puede usar un signo (&) como operador de concatenación de texto. De esta manera, puede unir, o concatenar, una o más cadenas de texto en una única pieza de texto.

| Operador | Significado     | Ejemplo                                               |
|----------|-------------|-------------------------------------------------------|
| &        | Concatenar | `"Nothing to print:" & " " & "no records found"`      |

### <a name="operator-precedence"></a>Prevalencia del operador

El orden en el que se evalúan las partes de una expresión compuesta es importante. Por ejemplo, el resultado de la expresión `1 + 4 / 2` varía en función de si la operación de adición o la división se realiza primero. Puede usar paréntesis para definir explícitamente la manera en que se evalúa una expresión. Por ejemplo, para indicar que la operación de adición debe realizarse primero, puede cambiar la expresión precedente a `(1 + 4) / 2`. Si no indica explícitamente el orden de las operaciones en una expresión, el orden se basa en la prioridad predeterminada que se asigna a los operadores admitidos. En la siguiente tabla se muestra la prioridad que se asigna a cada operador. Los operadores que tienen una mayor prioridad (por ejemplo, 7) se evalúan antes que los operadores que tienen una prioridad más baja (por ejemplo, 1).

| Precedencia | Operadores      | Sintaxis                                                                  |
|------------|----------------|-------------------------------------------------------------------------|
| 7          | Agrupación       | ( … )                                                                   |
| 6          | Acceso a miembros  | … . …                                                                   |
| 5          | Llamada de función  | … ( … )                                                                 |
| 4          | Multiplicativa | … \* …<br>… / …                                                         |
| 3          | Aditivo       | … + …<br>… - …                                                          |
| 2          | Comparación     | … &lt; …<br>… &lt;= …<br>… =&gt; …<br>… &gt; …<br>… = …<br>… &lt;&gt; … |
| 1          | Separación     | … , …                                                                   |

Si una expresión incluye múltiples operadores consecutivos que tienen la misma prioridad, dichas operaciones se evalúan de izquierda a derecha. Por ejemplo, la expresión `1 + 6 / 2 \* 3 > 5` devuelve **true**. Se recomienda usar paréntesis para indicar explícitamente el orden deseado de operaciones en las expresiones, de manera que las expresiones resulten más sencills de leer y mantener.

## <a name="references"></a><a name="References"></a>Referencias

Todos los orígenes de datos del componente del ER actual que están disponibles durante el diseño de una expresión se pueden usar como referencias con nombre. El componente ER actual puede ser un mapeo de modelo o un formato. Por ejemplo, el modelo de asignación actual de ER contiene el origen de datos **ReportingDate**, que devuelve el valor del tipo de datos [*DateTime*](er-formula-supported-data-types-primitive.md#datetime). Para dar formato correctamente a ese valor en el documento que lo genera, puede hacer referencia el origen de datos en la expresión `DATETIMEFORMAT (ReportingDate, "dd-MM-yyyy")`.

Todos los caracteres en el nombre de un origen de datos de referencia que no representan una letra del alfabeto deben venir precedidos de una comilla simple ('). Si el nombre de un origen de datos de referencia incluye al menos un símbolo que no representa una letra del alfabeto, el nombre debe estar entre comillas simples. Por ejemplo, estos símbolos no alfabéticos pueden ser signos de puntuación u otros símbolos escritos. A continuación se incluyen algunos ejemplos:

- Se debe hacer referencia al origen de datos **Hora y día hoy** en una expresión de ER de la siguiente manera: `'Today''s date & time'`
- Debe hacerse referencia al método **name()** del origen de datos **Clientes** en una expresión de ER de la siguiente manera: `Customers.'name()'`.

Si los métodos de orígenes de datos de la aplicación tienen parámetros, la siguiente sintaxis se utiliza para asignar un nombre a dichos métodos:

- Si el método **isLanguageRTL** del origen de datos **Sistema** tiene un parámetro **EN-US** del tipo de datos [*Cadena*](er-formula-supported-data-types-primitive.md#string), este método debe hacer referencia a una expresión de ER como `System.isLanguageRTL("EN-US")`.
- Las comillas no son necesarias cuando un nombre del método solo contiene símbolos alfanuméricos. Sin embargo, se requieren para un método de una tabla si el nombre incluye corchetes.

Cuando se agrega el origen de datos **Sistema** a la asignación de ER que hace referencia a la clase de aplicación **Global**, la expresión `System.isLanguageRTL("EN-US ")` devuelve el valor *booleano* **FALSE**. La expresión modificada `System.isLanguageRTL("AR")` devuelve el valor *Booleano* **TRUE**.

Puede limitar la forma en que los valores se pasan a los parámetros de este tipo de método:

- Únicamente las constantes se pueden pasar a los métodos de este tipo. Los valores de las constantes se definen en el tiempo de diseño.
- Solo se admiten tipos de datos [primitivos](er-formula-supported-data-types-primitive.md) (básicos) para los parámetros de este tipo. Los tipos de datos primitivos incluyen *entero*, *real*, *booleano* y *cadena*.

## <a name="paths"></a><a name="Paths"></a>Rutas

Cuando una expresión hace referencia a un origen de datos estructurado, puede usar la definición de ruta para seleccionar un elemento primitivo específico de ese origen de datos. Un carácter de punto (.) se usa para separar elementos individuales de un origen de datos estructurado. Por ejemplo, el modelo de mapeado actual de ER contiene el origen de datos **InvoiceTransactions**, y este origen de datos devuelve una lista de registros. La estructura de registros **InvoiceTransactions** contiene los campos **AmountDebit** y **AmountCredit**, y estos campos devuelven valores numéricos. Por lo tanto, puede diseñar la siguiente expresión para calcular el importe facturado: `InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit`. La construcción `InvoiceTransactions.AmountDebit` en esta expresión es la ruta que se utiliza para acceder al campo **Monto Débito** de la fuente de datos **FacturaTransacciones** del tipo *Lista de registros*.

### <a name="relative-path"></a>Ruta de acceso relativa

Si la ruta de un origen de datos estructurado comienza con un signo "at" (@), es una ruta relativa. Se muestra el signo "at" en lugar de la parte restante de la ruta absoluta de la estructura de árbol jerárquica que se utiliza. En la ilustración siguiente se muestra un ejemplo. Aquí, la ruta absoluta `Ledger.'accountingCurrency()'` indica que el valor contable de la moneda de la fuente de datos **Libro mayor** se ingresa en el campo **DivisadeContabilidad** del modelo de datos.

![Ejemplo de una ruta absoluta en la página del diseñador de mapeo de modelos ER](./media/ER-FormulaLanguage-AbsolutePath.png)

El ejemplo en la siguiente ilustración muestra cómo se usa una ruta relativa. La ruta relativa `@.AccountNum` indica que el campo **AccountNum** de la fuente de datos **Intrastat** (que aparece un nivel por encima del campo **AccountNum** en el árbol jerárquico del modelo de datos) se utiliza para ingresar el número de cuenta del cliente o proveedor en el campo **AccountNum** del modelo de datos.

![Ejemplo de una ruta relativa en la página del diseñador de mapeo de modelos ER](./media/ER-FormulaLanguage-RelativePath1.png)

La parte restante de la ruta absoluta también se muestra en el [Editor de fórmulas ER](general-electronic-reporting-formula-designer.md).

![Parte restante de la ruta absoluta en la página del diseñador de fórmulas ER](./media/ER-FormulaLanguage-RelativePath2.png)

Para obtener más información, consulte [Utilizar una ruta relativa en vínculos de datos de modelos y formatos de ER](relative-path-data-bindings-er-models-format.md).

## <a name="functions"></a><a name="Functions"></a>Funciones

Las funciones integradas de ER se pueden usar en expresiones de ER. Todos los orígenes de datos del contexto de la expresión (estos es, el mapeado de modelo de ER o formato actual de ER) pueden usarse como parámetros de funciones de llamada de acuerdo con la lista de argumentos de las funciones de llamada. Las constantes también se pueden usar como parámetros de las funciones de llamada. Por ejemplo, el modelo de mapeado actual de ER contiene el origen de datos **InvoiceTransactions**, y este origen de datos devuelve una lista de registros. La estructura de registros **InvoiceTransactions** contiene los campos **AmountDebit** y **AmountCredit**, y estos campos devuelven valores numéricos. Por tanto, para calcular el importe facturado, puede diseñar la siguiente expresión que usa la función de redondeo incorporada de ER: `ROUND (InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit, 2)`.

Cuando diseñe mapeos de modelos ER e informes ER, puede usar las funciones ER de las siguientes categorías:

- [Funciones de fecha y de tiempo](er-functions-category-datetime.md)
- [Funciones de lista](er-functions-category-list.md)
- [Funciones lógicas](er-functions-category-logical.md)
- [Funciones matemáticas](er-functions-category-mathematical.md)
- [Funciones de registro](er-functions-category-record.md)
- [Funciones de texto](er-functions-category-text.md)
- [Funciones de recopilación de datos](er-functions-category-data-collection.md)
- [Otras funciones (específicas de dominio empresarial)](er-functions-category-other.md)
- [Tipos de funciones de conversión](er-functions-category-type-conversion.md)

## <a name="functions-list-extension"></a>Extensión de la lista de funciones

ER le permite ampliar la lista de funciones que se usan en las expresiones de ER. Son necesarios algunos esfuerzos de ingeniería. Para obtener información detallada, vea [Ampliar la lista de funciones de informes electrónicos (ER)](general-electronic-reporting-formulas-list-extension.md).

## <a name="compound-expressions"></a>Expresiones compuestas

Puede crear expresiones compuestas que utilicen funciones de diferentes categorías, siempre que los tipos de datos coincidan. Cuando use funciones juntas, haga coincidir el tipo de datos de la salida de una función con el tipo de datos de entrada que requiere otra función. Por ejemplo, para evitar un posible error "list-is-empty" en un enlace de un campo a un elemento de formato ER, combine funciones de la categoría [Lista](er-functions-category-list.md) con una función de la categoría [Lógico](er-functions-category-logical.md), como muestra el siguiente ejemplo. Aquí, la fórmula usa la función [IF](er-functions-logical-if.md) para probar si la lista **IntrastatTotals** está vacía antes de que devuelva el valor de la agregación requerida de esa lista. Si la lista **IntrastatTotals** está vacía, la fórmula devuelve **0** (cero).

```vb
IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded') 
```

## <a name="multiple-solutions"></a>Soluciones múltiples

A menudo, puede obtener el mismo resultado de transformación de datos de múltiples maneras, utilizando funciones de diferentes categorías o diferentes funciones de la misma categoría. Por ejemplo, la expresión anterior también se puede configurar mediante el uso de la función [COUNT](er-functions-list-count.md) desde la categoría [Lista](er-functions-category-list.md).

```vb
IF(COUNT (IntrastatTotals)=0, 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded') 
```

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de los informes electrónicos](general-electronic-reporting.md)

[Diseñador de fórmulas en los informes electrónicos](general-electronic-reporting-formula-designer.md)

[Ampliar la lista de funciones de informes electrónicos](general-electronic-reporting-formulas-list-extension.md)

[Tipos de datos primitivos admitidos](er-formula-supported-data-types-primitive.md)

[Tipos de datos compuestos admitidos](er-formula-supported-data-types-composite.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
