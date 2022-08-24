---
title: Función ABS de ER
description: En este artículo se proporciona información sobre cómo usar la función ABS de informes electrónicos (ER).
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
ms.openlocfilehash: a8d0fe68232d9dd27d9ba0cc6b81c7708d22711e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272570"
---
# <a name="abs-er-function"></a>Función ABS de ER

[!include [banner](../includes/banner.md)]

La función `ABS` devuelve el valor absoluto (módulo) de la cifra especificada como un número *Real*. Es decir, devuelve el número sin su signo.

## <a name="syntax"></a>Sintaxis

```vb
ABS (number)
```

## <a name="arguments"></a>Argumentos

`number`: *Real*

Un valor numérico del que desea el módulo.

## <a name="return-values"></a>Valores de retorno

*Real*

El valor numérico resultante.

## <a name="example"></a>Ejemplo

`ABS (-1)` devuelve **1**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones matemáticas](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
