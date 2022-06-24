---
title: Función REPLACE de ER
description: Este artículo proporciona información general sobre cómo usar la función REPLACE de informes electrónicos (ER).
author: NickSelin
ms.date: 04/02/2020
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
ms.openlocfilehash: 6c2b1ba82d61a3c163f1d657035b66ace9f15c77
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878382"
---
# <a name="replace-er-function"></a>Función REPLACE de ER

[!include [banner](../includes/banner.md)]

La función `REPLACE` devuelve la cadena de texto especificada como un valor de tipo *Cadena* después de reemplazarla total o parcialmente por otra cadena.

## <a name="syntax"></a>Sintaxis

```vb
REPLACE (text, pattern, replacement, regular expression flag)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadena*

La ruta válida de un origen de datos de tipo *Cadena*.

`pattern`: *Cadena*

Si el argumento `regular expression flag` es **FALSE**, este argumento contiene el texto que debe ser reemplazado.

Si el argumento `regular expression flag` es **TRUE**, este argumento contiene una expresión regular que define tanto un patrón de búsqueda como el texto de reemplazo.

`replacement`: *Cadena*

Si el argumento `regular expression flag` es **FALSE**, este argumento contiene el texto que debe usarse como reemplazo.

Si el argumento `regular expression flag` es **TRUE**, este argumento no se usa.

`regular expression flag`: *Booleano*

Valor de tipo *Booleano* que indica si se usa una expresión regular para hacer el reemplazo.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

Si el argumento de `regular expression flag` es **TRUE**, esta función devuelve la cadena especificada después de que haya sido modificada aplicando la expresión regular especificada por el argumento `pattern`. La expresión regular se usa para buscar los caracteres que hay que reemplazar.

Si el argumento `regular expression flag` es **FALSO**, esta función devuelve la cadena especificada después de que el conjunto de caracteres que se definen en el argumento `pattern` ha sido reemplazado por caracteres del argumento `replacement`. 

## <a name="example-1"></a>Ejemplo 1

`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` aplica una expresión regular que quita todos los símbolos no numéricos y devuelve **"19234564971"**. 

## <a name="example-2"></a>Ejemplo 2

`REPLACE ("abcdef", "cd", "GH", false)` reemplaza el patrón **"cd"** por la cadena **"GH"** y devuelve **"abGHef"**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]