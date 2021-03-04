---
title: Función AND de ER
description: Este tema proporciona información general sobre cómo usar la función AND de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 8ccb7feb1d0f6836e7e8001870034900f6a1f598
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687083"
---
# <a name="and-er-function"></a>Función AND de ER

[!include [banner](../includes/banner.md)]

La función `AND` devuelve un valor *Booleano* de **TRUE** si todas las condiciones especificadas son ciertas. De lo contrario, la expresión devuelve un valor *Booleano* de **FALSE**.

## <a name="syntax"></a>Sintaxis

```vb
AND (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a>Argumentos

`condition 1`: *Booleano*

Una expresión condicional válida que debe probarse. Este argumento es obligatorio.

`condition N`: *Booleano*

Una expresión condicional válida que debe probarse. Estos argumentos adicionales son opcionales.

## <a name="return-values"></a>Valores de retorno

*Booleano*

El valor *Booleano* resultante.

## <a name="usage-notes"></a>Notas de uso

En los argumentos de las funciones lógicas, puede utilizar referencias de orígenes de datos, valores numéricos y de texto, valores booleanos, operadores de comparación y otras funciones de informes electrónicos (ER). Sin embargo, todos los argumentos deben evaluarse según un valor *Booleano* de **TRUE** o **FALSE**.

## <a name="example"></a>Ejemplo

`AND (1=1, "a"="a")` devuelve **TRUE**.

`AND (1=2, "a"="a")` devuelve **FALSE**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones lógicas](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]