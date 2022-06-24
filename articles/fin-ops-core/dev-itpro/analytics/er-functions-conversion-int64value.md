---
title: Función INT64VALUE ER
description: En este artículo se proporciona información sobre cómo usar la función INT64VALUE de informes electrónicos (ER).
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 37fae9cdc5a833009b0ca1cbeb851e5e6e1b6608
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892175"
---
# <a name="int64value-er-function"></a>Función INT64VALUE ER

[!include [banner](../includes/banner.md)]

La función `INT64VALUE` devuelve un valor *Int64* que representa la cadena especificada.

## <a name="syntax-1"></a>Sintaxis 1

```vb
INT64VALUE (text)
```

## <a name="syntax-2"></a>Sintaxis 2

```vb
INT64VALUE (number)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadena*

Un valor de texto que debe convertirse en un número *Int64*.

`number`: *Real* o *Entero*

Un valor numérico *Real* o *Entero* que debe convertirse en un número *Int64*.

## <a name="return-values"></a>Valores de retorno

*Int64*

El valor numérico resultante.

## <a name="usage-notes"></a>Notas de uso

Se trunca cualquier posición decimal.

## <a name="example-1"></a>Ejemplo 1

`INT64VALUE ("22565422744")` devuelve el valor *Int64* **22565422744**.

## <a name="example-2"></a>Ejemplo 2

`INT64VALUE ( VALUE("22565422744.77"))` devuelve el valor *Int64* **22565422744**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de conversión de tipos](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]