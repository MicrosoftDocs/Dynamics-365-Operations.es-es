---
title: Función TRANSLATE de ER
description: Este artículo proporciona información general sobre cómo usar la función TRANSLATE de informes electrónicos (ER).
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
ms.openlocfilehash: cf44ad5518e2850d4d4e7fd34866ee2f8313c356
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894335"
---
# <a name="translate-er-function"></a>Función TRANSLATE de ER

[!include [banner](../includes/banner.md)]

La función `TRANSLATE` devuelve un valor *Cadena* que contiene el resultado del reemplazo de caracteres del texto especificado en caracteres de otro conjunto proporcionado.

## <a name="syntax"></a>Sintaxis

```vb
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadena*

La ruta válida de un origen de datos de tipo *Cadena*.

`pattern`: *Cadena*

El texto que se va a reemplazar.

`replacement`: *Cadena*

El texto que se va a usar como reemplazo.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

La función `TRANSLATE` reemplaza un carácter a la vez. La función reemplaza el primer carácter del argumento `text` con el primer personaje del argumento `pattern` y luego el segundo carácter y sigue el mismo flujo hasta que termine. Cuando un carácter de los argumentos `text` y `pattern` coincide, se reemplaza por un carácter del argumento `replacement` que se encuentra en la misma posición que el personaje del argumento `pattern`. Si un personaje aparece varias veces en el argumento `pattern`, el argumento `replacement` asignará el que corresponde a la primera aparición de este carácter.

## <a name="example-1"></a>Ejemplo 1

`TRANSLATE ("abcdef", "cd", "GH")` reemplaza el carácter **"c"** del texto especificado **"abcedef"** con el carácter **"G"** del texto `replacement` debido a lo siguiente:
-   El carácter **"c"** está presente en el texto `pattern` en la primera posición.
-   La primera posición del texto `replacement` contiene el carácter **"G"**.

## <a name="example-2"></a>Ejemplo 2

`TRANSLATE ("abcdef", "ccd", "GH")` devuelve **"abGdef"**.

## <a name="example-3"></a>Ejemplo 3

`TRANSLATE ("abccba", "abc", "123")` devuelve **"123321"**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]