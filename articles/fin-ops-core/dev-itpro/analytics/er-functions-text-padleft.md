---
title: Función PADLEFT de ER
description: En este artículo se proporciona información sobre cómo usar la función PADLEFT de informes electrónicos (ER).
author: kfend
ms.date: 12/10/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: dac1f9142a381238bf116c4bce65958da8afc4db
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278900"
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
