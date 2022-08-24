---
title: Función MID de ER
description: Este artículo proporciona información general sobre cómo usar la función MID de informes electrónicos (ER).
author: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: c53963876db92bb07ed5ac49f009ed4f9bc5e8c4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285921"
---
# <a name="mid-er-function"></a>Función MID de ER

[!include [banner](../includes/banner.md)]

La función `MID` devuelve un valor de tipo *Cadena* que presenta el número especificado de caracteres de la cadena especificada, empezando en la posición especificada.

## <a name="syntax"></a>Sintaxis

```vb
MID (text, starting position, number of characters)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadena*

Valor de tipo *Cadena* que especifica el texto del que se devuelven los caracteres.

`starting position`: *Entero*

Valor de tipo *Entero* que especifica la posición del primer carácter que se debe devolver del texto especificado.

`number of characters`: *Entero*

Valor de tipo *Entero* que especifica el número de caracteres que se deben devolver desde la posición de inicio especificada.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

Si el valor del argumento `starting position` es menor que 0 (cero), los caracteres que se devuelven se cuentan desde la primera posición en la cadena especificada.

Si el valor del argumento `starting position` supera la longitud de la cadena especificada, se devuelve una cadena vacía.

## <a name="example"></a>Ejemplo

`MID ("Sample", 2, 3)` devuelve **"amp"**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
