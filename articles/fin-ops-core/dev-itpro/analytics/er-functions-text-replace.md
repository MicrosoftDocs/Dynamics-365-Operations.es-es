---
title: Función REPLACE de ER
description: Este tema proporciona información general sobre cómo usar la función REPLACE de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9c66f4c96f35e3ad5fc92e7925b5cd07c956aac
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916876"
---
# <a name="REPLACE">Función REPLACE de ER</a>

[!include [banner](../includes/banner.md)]

La función `REPLACE` devuelve la cadena de texto especificada como un valor de tipo *Cadena* después de reemplazarla total o parcialmente por otra cadena.

## <a name="syntax"></a>Sintaxis

```
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

Si el argumento `regular expression flag`es **FALSE**, esta función se comporta como [TRANSLATE](er-functions-text-translate.md). Los caracteres que especifica el argumento `replacement` se usan para reemplazar los caracteres que se encuentran. 

## <a name="example-1"></a>Ejemplo 1

`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` aplica una expresión regular que quita todos los símbolos no numéricos y devuelve **"19234564971"**. 

## <a name="example-2"></a>Ejemplo 2

`REPLACE ("abcdef", "cd", "GH", false)` reemplaza el patrón **"cd"** por la cadena **"GH"** y devuelve **"abGHef"**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)
