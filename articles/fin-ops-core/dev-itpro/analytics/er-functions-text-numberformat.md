---
title: Función NUMBERFORMAT de ER
description: En este tema se proporciona información sobre cómo usar la función NUMBERFORMAT de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
ms.topic: article
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
ms.openlocfilehash: a05a1e1c4cdb050bff30ea4710da927a537da14c
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562718"
---
# <a name="numberformat-er-function"></a>Función NUMBERFORMAT de ER

[!include [banner](../includes/banner.md)]

La función `NUMBERFORMAT` devuelve un valor de tipo *Cadena* que presenta el número especificado en el formato especificado y en una [referencia cultural](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) especificada opcionalmente. Para obtener información acerca de los formatos admitidos, vea [estándar](https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx) y [personalizado](https://msdn.microsoft.com/library/0c899ak8(v=vs.110).aspx).

## <a name="syntax-1"></a>Sintaxis 1

```vb
NUMBERFORMAT (number, format)
```

## <a name="syntax-2"></a>Sintaxis 2

```vb
NUMBERFORMAT (number, format, culture)
```

## <a name="arguments"></a>Argumentos

`number`: *Entero* o *Real*

Valor numérico que especifica el número al que se debe aplicar formato.

`format`: *Cadena*

Valor de tipo *Cadena* que representa el formato.

`culture`: *Cadena*

Valor de tipo *Cadena* que representa la referencia cultural que se debe utilizar para aplicar formato.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

Si la referencia cultural no se define como un argumento de la función llamada, el contexto en el que se ejecuta esta función determina la cultura que se utiliza para aplicar formato a números.

## <a name="example-1"></a>Ejemplo 1

Para la referencia cultural **EN-US**, `NUMBERFORMAT (0.45, "p")` devuelve **"45.00 %"** y `NUMBERFORMAT (10.45, "#")` devuelve **"10"**.

## <a name="example-2"></a>Ejemplo 2

`NUMBERFORMAT (10/3, "F2", "de")` devuelve **3,33**, mientras que `NUMBERFORMAT (10/3, "F2", "en-us")` devuelve **3.33**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]