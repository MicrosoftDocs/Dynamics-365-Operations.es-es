---
title: Función IF de ER
description: Este tema proporciona información general sobre cómo usar la función IF de informes electrónicos (ER).
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
ms.openlocfilehash: b8733022b44f3460e34a610140fd6d584ab990c2
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687011"
---
# <a name="if-er-function"></a>Función IF de ER

[!include [banner](../includes/banner.md)]

La función `IF` devuelve el primer valor especificado si se cumple la condición especificada. De lo contrario, devuelve el segundo valor especificado. El valor que se devuelve puede ser un valor de cualquiera de los tipos de datos admitidos.

## <a name="syntax"></a>Sintaxis

```vb
IF (condition, first value, second value) as any of the supported data types
```

## <a name="arguments"></a>Argumentos

`condition`: *Booleano*

Una expresión condicional válida que debe probarse.

`first value`: *Cualquiera de los tipos de datos admitidos*

El resultado que se devuelve si se cumple la condición.

`second value`: *Cualquiera de los tipos de datos admitidos*

El resultado que se devuelve si no se cumple la condición.

## <a name="return-values"></a>Valores de retorno

*Cualquiera de los tipos de datos admitidos*

El valor resultante de cualquiera de los tipos de datos admitidos.

## <a name="usage-notes"></a>Notas de uso

Los argumentos `first value` y `second value` deben especificarse utilizando el mismo tipo de datos. Se produce una excepción en tiempo de diseño si los tipos de datos de los valores configurados no coinciden.

Si el primer valor y el segundo valor son valores del tipo de datos *Contenedor (registro)* o *Lista de registros*, el resultado solo tiene los campos que existen en ambos valores.

## <a name="example"></a>Ejemplo

`IF (1=2, "condition is met", "condition is not met")` devuelve la cadena **"no se cumple la condición"**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones lógicas](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]