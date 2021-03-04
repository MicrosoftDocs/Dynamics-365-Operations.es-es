---
title: Función OR de ER
description: Este tema proporciona información general sobre cómo usar la función OR de informes electrónicos (ER).
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
ms.openlocfilehash: 107241dbf9a5127d61343fc1cf42c3bab577adb3
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686987"
---
# <a name="or-er-function"></a>Función OR de ER

[!include [banner](../includes/banner.md)]

La función `OR` devuelve un valor *Booleano* de **FALSE** si todas las condiciones especificadas son falsas. Si cualquier condición especificada es cierta, esta función devuelve un valor *Booleano* de **TRUE**.

## <a name="syntax"></a>Sintaxis

```vb
OR (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a>Argumentos

`condition 1`: *Booleano*

Una expresión condicional válida que debe probarse. Este argumento es obligatorio.

`condition N`: *Booleano*

Una expresión condicional válida que debe probarse. Estos argumentos adicionales son opcionales.

## <a name="return-values"></a>Valores de retorno

*Booleano*

El valor *Booleano* resultante.

## <a name="example"></a>Ejemplo

`OR (1=2, "a"="a")` devuelve **TRUE**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones lógicas](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]