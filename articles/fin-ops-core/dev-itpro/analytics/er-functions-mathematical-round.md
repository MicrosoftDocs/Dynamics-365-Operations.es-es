---
title: Función ROUND de ER
description: En este artículo se proporciona información sobre cómo usar la función ROUND de informes electrónicos (ER).
author: NickSelin
ms.date: 10/21/2020
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
ms.openlocfilehash: 5dce96077ab25f8e545bb99d4bed8fc5bba61e2a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905210"
---
# <a name="round-er-function"></a>Función ROUND de ER

[!include [banner](../includes/banner.md)]

La función `ROUND` devuelve el número especificado como un valor *Real* después de que se haya redondeado al número especificado de posiciones decimales.

## <a name="syntax"></a>Sintaxis

```vb
ROUND (number, decimals)
```

## <a name="arguments"></a>Argumentos

`number`: *Real*

Un valor numérico que debe redondearse.

`decimals`: *Entero*

Un valor numérico que representa el número de lugares decimales.

## <a name="return-values"></a>Valores de retorno

*Real*

El valor numérico resultante.

## <a name="usage-notes"></a>Notas de uso

Si el valor del argumento `decimals` es superior a 0 (cero), el número especificado se redondea a ese número de decimales.

Si el valor del argumento `decimals` es **0** (cero), el número especificado se redondea al número par entero más cercano.

Si el valor del argumento `decimals` es inferior a 0 (cero), el número especificado se redondea a la izquierda de la coma decimal.

## <a name="example-1"></a>Ejemplo 1

`ROUND (1200.767, 2)` redondea a dos lugares decimales y devuelve **1200,77**.

## <a name="example-2"></a>Ejemplo 2

`ROUND (1200.767, -3)` redondea al múltiplo más cercano de 1000 y devuelve **1000**.

## <a name="example-3"></a>Ejemplo 3

`ROUND (1200.5, 0)` redondea al entero par más cercano y devuelve **1200**, mientras `ROUND (1201.5, 0)` hace lo mismo y vuelve **1202**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones matemáticas](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]