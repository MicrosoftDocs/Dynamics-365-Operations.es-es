---
title: Función ROUNDUP de ER
description: Este tema proporciona información general sobre cómo usar la función ROUNDUP de informes electrónicos (ER).
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
ms.openlocfilehash: 8ed86e2a848248dd8f2fc99401d12e0a162bf20a
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686843"
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