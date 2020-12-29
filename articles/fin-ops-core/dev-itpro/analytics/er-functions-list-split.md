---
title: Función SPLIT de ER
description: Este tema proporciona información general sobre cómo usar la función SPLIT de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: e1f11d68b697fdd363f429e60a79f1e1f97bab5b
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686401"
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

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)
