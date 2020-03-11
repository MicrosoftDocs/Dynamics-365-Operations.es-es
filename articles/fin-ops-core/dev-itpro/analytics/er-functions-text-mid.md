---
title: Función MID de ER
description: Este tema proporciona información general sobre cómo usar la función MID de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6fbaf5952222d90a855956fb93713e0f9ef81305
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041041"
---
# <a name="MID">Función MID de ER</a>

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
