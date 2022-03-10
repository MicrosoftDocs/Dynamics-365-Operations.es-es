---
title: Función VALUE ER
description: Este tema proporciona información general sobre cómo usar la función VALUE de informes electrónicos (ER).
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 04d3320276bc1e23436bd9baa7a84da36314d6c3bf7f84694aa2e01e31230a0b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6713951"
---
# <a name="value-er-function"></a>Función VALUE ER

[!include [banner](../includes/banner.md)]

La función `VALUE` devuelve un valor *Real* que se convierte de la cadena especificada.

## <a name="syntax"></a>Sintaxis

```vb
VALUE (text)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadena*

Un valor de cadena que debe convertirse en un valor numérico.

## <a name="return-values"></a>Valores de retorno

*Real*

El valor numérico resultante.

## <a name="usage-notes"></a>Notas de uso

Las comas y los caracteres de punto (.) se consideran separadores decimales y los guiones iniciales (-) se usan como signo negativo. Se generará una excepción en el tiempo de ejecución si la cadena especificada contiene otros caracteres no numéricos.

## <a name="example-1"></a>Ejemplo 1

`VALUE ("1 234,56")` genera una excepción.

## <a name="example-2"></a>Ejemplo 2

`VALUE ("1234,56")` devuelve **1234,56**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de conversión de tipos](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]