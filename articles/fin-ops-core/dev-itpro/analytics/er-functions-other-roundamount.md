---
title: Función ROUNDAMOUNT de ER
description: En este tema se proporciona información sobre cómo usar la función ROUNDAMOUNT de informes electrónicos (ER).
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: cce35a33ca179ad85bbde879122d3afbeefe5ee7
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745672"
---
# <a name="roundamount-er-function"></a>Función ROUNDAMOUNT de ER

[!include [banner](../includes/banner.md)]

La función `ROUNDAMOUNT` devuelve un valor de tipo *Real* que representa el resultado de redondear la cantidad especificada al múltiplo más cercano de otro número, de acuerdo con la regla de redondeo especificada.

## <a name="syntax"></a>Sintaxis

```vb
ROUNDAMOUNT (number, decimals, round rule)
```

## <a name="arguments"></a>Argumentos

`number`: *Entero* o *Real*

Un valor numérico que debe redondearse.

`decimals`: *Entero* o *Real*

El número a cuyo múltiplo se debe redondear el valor del parámetro `number`.

`round rule`: *Valor de enumeración*

Un valor de enumeración de la enumeración **RoundOffType** que define la regla de redondeo. Esta enumeración ofrece los siguientes valores:

- Normal (ordinario)
- Hacia abajo (RoundDown)
- Hacia arriba (RoundUp)

## <a name="return-values"></a>Valores de retorno

*Real*

El valor numérico resultante es un múltiplo del valor especificado por el parámetro `decimals` y es el más cercano al valor especificado por el parámetro `number`.

## <a name="usage-notes"></a>Notas de uso

Cuando el valor del parámetro `number` es cero, esta función siempre devuelve cero.

Cuando el valor del parámetro `decimals` es cero, esta función se redondea al valor de redondeo predeterminado. Cuando el parámetro `round rule` se establece en **RoundOffType.Ordinary**, el valor de redondeo predeterminado es **0.01**. De lo contrario, el valor de redondeo predeterminado es **1.0**.

Cuando el parámetro `round rule` se establece en **RoundOffType.Ordinary**, esta función redondea a la cantidad de redondeo más cercana.

Cuando el parámetro `round rule` se establece en **RoundOffType.RoundDown**, esta función redondea hacia abajo a la cantidad de redondeo más cercana.

Cuando el parámetro `round rule` se establece en **RoundOffType.RoundUp**, esta función redondea hacia arriba a la cantidad de redondeo más cercana.

Cuando el parámetro `round rule` se establece en **RoundOffType.Ordinary**, esta función se comporta como la función de Excel [MROUND](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) y la función de X++ [ROUND](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/dev-ref/xpp-math-run-time-functions#round).

## <a name="remarks"></a>Comentarios

Para redondear un valor numérico a un número específico de posiciones decimales, use la función [ROUND](er-functions-mathematical-round.md).

## <a name="example"></a>Ejemplo

Si el parámetro **model.RoundOff** se establece en **RoundOffType.Ordinary**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` devuelve 7.35. 

Si el parámetro **model.RoundOff** se establece en **RoundOffType.RoundDown**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` devuelve 7.35. 

Si el parámetro **model.RoundOff** se establece en **RoundOffType.RoundUp**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` devuelve 8.4.

## <a name="additional-resources"></a>Recursos adicionales

[Otras funciones (específicas de dominio empresarial)](er-functions-category-other.md)

[Funciones matemáticas](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]