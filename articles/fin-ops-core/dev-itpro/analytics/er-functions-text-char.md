---
title: Función CHAR de ER
description: En este artículo se proporciona información sobre cómo usar la función CHAR de informes electrónicos (ER).
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
ms.openlocfilehash: 1fb1d25c2624894e7bb0fa34b7bc48905a9289a6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8881501"
---
# <a name="char-er-function"></a>Función CHAR de ER

[!include [banner](../includes/banner.md)]

La función `CHAR` devuelve un valor de tipo *Cadena* que presenta un solo carácter al que hace referencia el código numérico de Unicode especificado.

## <a name="syntax"></a>Sintaxis

```vb
CHAR (number)
```

## <a name="arguments"></a>Argumentos

`number`: *Entero*

Un número que corresponde a un único carácter.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

La cadena que esta función devuelve depende de la codificación seleccionada en el elemento de formato **ARCHIVO** principal. Para ver una de lista de codificaciones admitidas, consulte [Clase de codificación](/dotnet/api/system.text.encoding).

## <a name="example"></a>Ejemplo

`CHAR (255)` devuelve **"ÿ"**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]