---
title: Función SPLIT de ER
description: En este artículo se proporciona información sobre cómo usar la función SPLIT de informes electrónicos (ER).
author: NickSelin
ms.date: 04/01/2021
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
ms.openlocfilehash: 2acd93b645121b577d516d3ce29a3d05069b8de9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906840"
---
# <a name="split-er-function"></a>Función SPLIT de ER

[!include [banner](../includes/banner.md)]

La función `SPLIT` divide la cadena de entrada especificada en subcadenas y devuelve el resultado como un valor *Lista de registros* nuevo.

## <a name="syntax-1"></a>Sintaxis 1

```vb
SPLIT (input, length)
```

La sintaxis se usa para dividir la cadena de entrada especificada en subcadenas y cada una de las cuales tiene la duración especificada.

## <a name="syntax-2"></a>Sintaxis 2

```vb
SPLIT (input, delimiter)
```

La sintaxis se usa para dividir la cadena de entrada especificada en subcadenas, basadas en el delimitador especificado.

## <a name="arguments"></a>Argumentos

`input`: *Cadena*

Texto a dividir.

`length`: *Entero*

La longitud máxima de una sola subcadena.

`delimiter`: *Cadena*

Un delimitador que se utiliza para separar subcadenas.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

La lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

La estructura de registro de la lista que se devuelve consta del campo **Valor** del tipo *Cadena*. Cada registro de la lista que se devuelve contiene subcadenas generadas en este campo.

Si el argumento `delimiter` está vacío, la nueva lista que se devuelve consiste en un registro que tiene un campo **Valor** del tipo *Cadena*. Este campo contiene el texto de entrada.

Si el argumento `input` está vacío, se devuelve una nueva lista vacía. Si el argumento `input` o `delimiter` están sin especificar (null), se emite una excepción de la aplicación.

## <a name="example-1"></a>Ejemplo 1

`SPLIT ("abcd", 3)` devuelve una nueva lista que consta de dos registros que tienen el campo **Valor** del tipo *Cadena*. El campo **Valor** del primer registro contiene el texto **“abc”** y el campo **Valor** del segundo registro contiene el texto **“d”**.

## <a name="example-2"></a>Ejemplo 2

`SPLIT ("XAb aBy", "aB")` devuelve una nueva lista que consta de tres registros que tienen el campo **Valor** del tipo *Cadena*. El campo **Valor** del primer registro contiene el texto **"X"**, el campo **Valor** del segundo registro contiene texto **"&nbsp;"**, y el campo **Valor** del tercer registro contiene el texto **"y"**. 

## <a name="example-3"></a>Ejemplo 3

Puede usar la función [ÍNDICE](er-functions-list-index.md) para acceder a elementos individuales de la cadena de entrada especificada. Si especifica el origen de datos **MyList** del tipo **Campo calculado** y configura para él la expresión `SPLIT("abc", 1)`, la expresión `INDEX(MyList,2).Value` devuelve el valor de texto **"b"**.

## <a name="example-4"></a>Ejemplo 4

La función [ENUMERATE](er-functions-list-enumerate.md) también puede ayudarle a acceder a elementos individuales de la cadena de entrada especificada. Si primero ingresa la fuente de datos **MyList** del tipo **Campo calculado** y configura para ello la expresión `SPLIT("abc", 1)` y luego ingresa la fuente de datos **EnumeratedList** del **Campo calculado**, escriba y configure para ello la expresión `ENUMERATE(MyList)`, la expresión `FIRSTORNULL(WHERE(EnumeratedList, EnumeratedList.Number=2)).Value` devuelve el texto **"b"**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
