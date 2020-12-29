---
title: Función ROUNDDOWN de ER
description: Este tema proporciona información general sobre cómo usar la función ROUNDDOWN de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 9221476c1c12a7cc3fe2367cdee3ad44e5cbe381
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686891"
---
# <a name="rounddown-er-function"></a>Función ROUNDDOWN de ER

[!include [banner](../includes/banner.md)]

La función `ROUNDDOWN` devuelve el número especificado como un valor *Real* después de que se haya redondeado hacia abajo al número especificado de posiciones decimales.

## <a name="syntax"></a>Sintaxis

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a>Argumentos

`number`: *Real*

Un valor numérico que debe redondearse hacia abajo.

`decimals`: *Entero*

Un valor numérico que representa el número de lugares decimales.

## <a name="return-values"></a>Valores de retorno

*Real*

El valor numérico resultante.

## <a name="usage-notes"></a>Notas de uso

Esta función se comporta como [ROUND](er-functions-mathematical-round.md), pero siempre redondea hacia abajo del número especificado (hacia cero).

## <a name="example-1"></a>Ejemplo 1

`ROUNDDOWN (1200.767, 2)` redondea hacia abajo a dos lugares decimales y devuelve **1200,76**. 

## <a name="example-2"></a>Ejemplo 2

`ROUNDDOWN (1700.767, -3)` redondea hacia abajo al múltiplo más cercano de 1000 y devuelve **1000**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones matemáticas](er-functions-category-mathematical.md)
