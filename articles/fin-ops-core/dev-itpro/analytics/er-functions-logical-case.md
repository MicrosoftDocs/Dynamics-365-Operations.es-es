---
title: Función CASE de ER
description: Este tema proporciona información general sobre cómo usar la función CASE de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
ms.topic: article
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
ms.openlocfilehash: f466e3ffe368bf30236060d820621e723106fc1d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562478"
---
# <a name="case-er-function"></a>Función CASE de ER

[!include [banner](../includes/banner.md)]

La función `CASE` evalúa el valor de la expresión especificada frente a las opciones alternativas especificadas y devuelve el resultado de la primera opción que es igual al valor de la expresión especificada. De lo contrario, devuelve el resultado predeterminado opcional, si se especifica un resultado predeterminado como el último argumento de la función llamada que no está precedida por una opción. El valor que se devuelve puede ser un valor de cualquiera de los tipos de datos admitidos.

## <a name="syntax"></a>Sintaxis

```vb
CASE (expression, option 1, result 1[, option 2, result 2, …, option N, result N, default result])
```

## <a name="arguments"></a>Argumentos

`expression`: *Tipo de datos primitivo* (Booleano, numérico o texto)

Una expresión válida que devuelve un valor del tipo de datos primitivo.

`option 1`: *Tipo de datos primitivo* (Booleano, numérico o texto)

Una expresión válida que devuelve un valor del mismo tipo de datos primitivos que el argumento `expression` de la función llamada. Este argumento es obligatorio.

`result 1`: *Cualquiera de los tipos de datos admitidos*

El resultado devuelto que corresponde con la opción anterior. Este argumento es obligatorio.

`option N`: *Tipo de datos primitivo* (Booleano, numérico o texto)

Una expresión válida que devuelve un valor del mismo tipo de datos primitivos que el argumento `expression` de la función llamada. Este argumento es opcional.

`result N`: *Cualquiera de los tipos de datos admitidos*

El resultado devuelto que corresponde con la opción anterior. Este argumento es opcional.

`default result`: *Cualquiera de los tipos de datos admitidos*

El resultado que debe devolverse si no hay coincidencia. Este argumento es opcional.

## <a name="return-values"></a>Valores de retorno

*Cualquiera de los tipos de datos admitidos*

El valor resultante de cualquiera de los tipos de datos admitidos.

## <a name="usage-notes"></a>Notas de uso

Se lanza una excepción en tiempo de ejecución si no hay coincidencia y no se define un resultado predeterminado opcional.

Todos los resultados deben especificarse utilizando el mismo tipo de datos. Se produce una excepción en tiempo de diseño si los tipos de datos de los resultados configurados no coinciden.

Si el primer valor del resultado y el resultado número *N* son valores del tipo de datos *Contenedor (registro)* o *Lista de registros*, el resultado solo tiene los campos que existen en ambos valores.

## <a name="example"></a>Ejemplo

`CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")` devuelve la cadena **"INVIERNO"** si la fecha de la sesión de solicitud actual es entre octubre y diciembre. En caso contrario, devuelve una cadena en blanco.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones lógicas](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]