---
title: Función PADLEFT de ER
description: En este tema se proporciona información sobre cómo usar la función PADLEFT de informes electrónicos (ER).
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: a45333b8160a42063de8000ab27ea23136eb75ee7b55162b4602a5f3c52550de
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6770053"
---
# <a name="padleft-er-function"></a>Función PADLEFT de ER

[!include [banner](../includes/banner.md)]

La función `PADLEFT` devuelve un valor de tipo *Cadena* de la longitud especificada en la que el inicio de la cadena especificada se rellena con los caracteres especificados.

## <a name="syntax"></a>Sintaxis

```vb
PADLEFT (text, length, padding chars)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadena*

Valor de tipo *Cadena* que representa el texto original.

`length`: *Entero*

Un valor de tipo *Entero* que representa el número final de caracteres en la cadena rellenada.

`padding chars`: *Cadena*

Los caracteres que se van a utilizar para el relleno.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="example"></a>Ejemplo

`PADLEFT ("1234", 10, "`&nbsp;`")` devuelve la cadena de texto **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]