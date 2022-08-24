---
title: Función LEFT de ER
description: Este artículo proporciona información general sobre cómo usar la función LEFT de informes electrónicos (ER).
author: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: 866c1b59fee9aa58afafbd82a83cff57e4cadeeb
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268008"
---
# <a name="left-er-function"></a>Función LEFT de ER

[!include [banner](../includes/banner.md)]

La función `LEFT` devuelve un valor de tipo *Cadena* que representa la cantidad de caracteres especificados desde el principio de la cadena especificada.

## <a name="syntax"></a>Sintaxis

```vb
LEFT (text, number)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadena*

Valor de tipo *Cadena* que representa el texto original.

`number`: *Entero*

El número de caracteres que se deben devolver desde el inicio del texto original.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="example"></a>Ejemplo

`LEFT ("Sample", 3)` devuelve **"Sam"**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
