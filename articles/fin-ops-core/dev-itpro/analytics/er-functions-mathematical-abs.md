---
title: Función ABS de ER
description: En este artículo se proporciona información sobre cómo usar la función ABS de informes electrónicos (ER).
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 90fbff223be5c195feb66b9ea72ee0688e60697b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886889"
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