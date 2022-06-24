---
title: Función CONCATENATE de ER
description: En este artículo se proporciona información sobre cómo usar la función CONCATENATE de informes electrónicos (ER)
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 926c3acf92fc8017c3c4a7814855a6871c1cacc4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863275"
---
# <a name="concatenate-er-function"></a>Función CONCATENATE de ER

[!include [banner](../includes/banner.md)]

La función `CONCATENATE` devuelve todas las cadenas de texto especificadas como un valor de tipo *Cadena* después de unirlas en una sola cadena.

## <a name="syntax"></a>Sintaxis

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a>Argumentos

`text 1`: *Cadena*

Una referencia a un origen de datos del tipo de datos *Cadena*. Este argumento es obligatorio.

`text N`: *Cadena*

Una referencia a un origen de datos del tipo de datos *Cadena*. Estos argumentos adicionales son opcionales.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="example"></a>Ejemplo

`CONCATENATE ("abc", "def")` devuelve **"abcdef"**.

## <a name="usage-notes"></a>Notas de uso

La expresión `"abc" & "def"` también devuelve **"abcdef"**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]