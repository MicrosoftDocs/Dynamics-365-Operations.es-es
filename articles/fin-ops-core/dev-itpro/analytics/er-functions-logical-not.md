---
title: Función NOT de ER
description: Este tema proporciona información general sobre cómo usar la función NOT de informes electrónicos (ER).
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
ms.openlocfilehash: 2308ab4d222863312441b3f17559ac4d3afbfb29
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686963"
---
# <a name="not-er-function"></a>Función NOT de ER

[!include [banner](../includes/banner.md)]

La función `NOT` devuelve el valor lógico invertido de la condición especificada como un valor *Booleano*.

## <a name="syntax"></a>Sintaxis

```vb
NOT (condition)
```

## <a name="arguments"></a>Argumentos

`condition`: *Booleano*

Una expresión condicional válida que debe revertirse.

## <a name="return-values"></a>Valores de retorno

*Booleano*

El valor *Booleano* resultante.

## <a name="example"></a>Ejemplo

`NOT (TRUE)` devuelve **FALSE**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones lógicas](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]