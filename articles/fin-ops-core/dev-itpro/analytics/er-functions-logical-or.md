---
title: Función OR de ER
description: En este artículo se proporciona información sobre cómo usar la función OR de informes electrónicos (ER).
author: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 99b5ee37af1ea1a69985fb79b762b31561334fd6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268098"
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
