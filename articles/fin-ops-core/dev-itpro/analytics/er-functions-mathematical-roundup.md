---
title: Función ROUNDUP de ER
description: Este tema proporciona información general sobre cómo usar la función ROUNDUP de informes electrónicos (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: d23a984bd59c4d2d37c407e3fcfed9c7017dcc7f
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569344"
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