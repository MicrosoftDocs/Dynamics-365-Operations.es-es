---
title: Función ROUNDUP de ER
description: En este artículo se proporciona información sobre cómo usar la función ROUNDUP de informes electrónicos (ER).
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: ec4fdce6f072c5c3d87b139c8f64bd63a8a3eccd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8855656"
---
# <a name="roundup-er-function"></a>Función ROUNDUP de ER

[!include [banner](../includes/banner.md)]

La función `ROUNDUP` devuelve el número especificado como un valor *Real* después de que se haya redondeado hacia arriba al número especificado de posiciones decimales.

## <a name="syntax"></a>Sintaxis

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a>Argumentos

`number`: *Real*

Un valor numérico que debe redondearse hacia arriba.

`decimals`: *Entero*

Un valor numérico que representa el número de lugares decimales.

## <a name="return-values"></a>Valores de retorno

*Real*

El valor numérico resultante.

## <a name="usage-notes"></a>Notas de uso

Esta función se comporta como [ROUND](er-functions-mathematical-round.md), pero siempre redondea hacia arriba el número especificado (lejos de cero).

## <a name="example-1"></a>Ejemplo 1

`ROUNDUP (1200.763, 2)` redondea hacia arriba a dos lugares decimales y devuelve **1200,77**.

## <a name="example-2"></a>Ejemplo 2

`ROUNDUP (1200.767, -3)` redondea hacia arriba al múltiplo más cercano de 1000 y devuelve **2000**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones matemáticas](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]