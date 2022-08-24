---
title: Función NUMBERFORMAT de ER
description: En este artículo se proporciona información sobre cómo usar la función NUMBERFORMAT de informes electrónicos (ER).
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
ms.openlocfilehash: 5519f549c10ba5c02e249592d040582c3f8dc44f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274807"
---
# <a name="numberformat-er-function"></a>Función NUMBERFORMAT de ER

[!include [banner](../includes/banner.md)]

La función `NUMBERFORMAT` devuelve un valor de tipo *Cadena* que presenta el número especificado en el formato especificado y en una [referencia cultural](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) especificada opcionalmente. Para obtener información acerca de los formatos admitidos, vea [estándar](/dotnet/standard/base-types/standard-numeric-format-strings) y [personalizado](/dotnet/standard/base-types/custom-numeric-format-strings).

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
