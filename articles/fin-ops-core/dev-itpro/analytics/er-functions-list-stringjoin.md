---
title: Función STRINGJOIN de ER
description: En este artículo se proporciona información sobre cómo usar la función STRINGJOIN de informes electrónicos (ER).
author: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 6510c271ac5e01d841722fdf2c5fd8c7deaf8caf
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9271655"
---
# <a name="stringjoin-er-function"></a>Función STRINGJOIN de ER

[!include [banner](../includes/banner.md)]

La función `STRINGJOIN` devuelve una valor *Cadena* que consta de valores concatenados del campo especificado de la lista especificada. Los valores pueden estar separados por el delimitador especificado.

## <a name="syntax"></a>Sintaxis

```vb
STRINGJOIN (list, field, delimiter)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

La ruta válida de un origen de datos del tipo de datos *Lista de registros*.

`field`: *Campo*

La ruta válida de un campo del tipo de datos *Cadena* en la lista especificada.

`delimiter`: *Cadena*

Un delimitador que se utiliza para separar subcadenas.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="example"></a>Ejemplo

Si introduce `SPLIT("abc" , 1)` como fuente de datos **DS**, la expresión `STRINGJOIN (DS, DS.Value, "-")` devuelve **"a-b-c"**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
