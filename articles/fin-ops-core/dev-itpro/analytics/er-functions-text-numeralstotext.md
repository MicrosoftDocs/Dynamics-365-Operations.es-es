---
title: Función NUMERALSTOTEXT de ER
description: Este tema proporciona información general sobre cómo usar la función NUMERALSTOTEXT de informes electrónicos (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e4af3926998d128f8269ab9af46caeb8be896509
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680227"
---
# <a name="numeralstotext-er-function"></a>Función NUMERALSTOTEXT de ER

[!include [banner](../includes/banner.md)]

La función `NUMERALSTOTEXT` devuelve el número especificado como un valor de tipo *Cadena* después de que se haya deletreado (es decir, convertido a cadenas de texto) en el idioma especificado.

## <a name="syntax"></a>Sintaxis

```vb
NUMERALSTOTEXT (number, language, currency, print currency name flag, decimal points)
```

## <a name="arguments"></a>Argumentos

`number`: *Entero* o *Real*

Valor numérico que especifica el número que se debe deletrear.

`language`: *Cadena*

Valor de tipo *Cadena* que representa el código de idioma.

`currency`: *Cadena*

Valor de tipo *Cadena* que representa el código de divisa.

`print currency name flag`: *Booleano*

Valor de tipo *Booleano* que indica si se debe agregar un nombre de divisa al texto deletreado.

`decimal points`: *Entero*

Valor de tipo *Entero* que indica el número de decimales que debe tener el texto deletreado.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

El código de idioma es opcional. Cuando se define como una cadena vacía, se utiliza el código de idioma para el contexto en ejecución. El código de idioma predeterminado es **EN-US**. El código de idioma para el contexto en ejecución se define en un elemento **Carpeta** o **Archivo** del formato de informe electrónico (ER) que se está ejecutando.

El código de divisa es opcional. Cuando se define como una cadena vacía, se utiliza la divisa de empresa para el contexto en ejecución.

> [!NOTE] 
> Los argumentos `print currency name flag` y `decimal points` se analizan únicamente para los siguientes códigos de idioma: **CS**, **ET**, **HU**, **LT**, **LV**, **PL** y **RU**. Asimismo, el argumento `print currency name flag` solo se analiza para las empresas en las que el contexto del país o la región permite la declinación de nombres de divisa.

## <a name="example-1"></a>Ejemplo 1

`NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` devuelve **"One Thousand Two Hundred Thirty Four and 56"**.

## <a name="example-2"></a>Ejemplo 2

`NUMERALSTOTEXT (120, "PL", "", false, 0)` devuelve **"Sto dwadzieścia"**. 

## <a name="example-3"></a>Ejemplo 3

`NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` devuelve **"Сто двадцать евро 21 евроцент"**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]