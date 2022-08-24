---
title: Función RIGHT de ER
description: Este artículo proporciona información general sobre cómo usar la función RIGHT de informes electrónicos (ER).
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
ms.openlocfilehash: fc3e5fed67ecc67bf0673f7d8322b7c151c4d50c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287166"
---
# <a name="right-er-function"></a>Función RIGHT de ER

[!include [banner](../includes/banner.md)]

La función `RIGHT` devuelve un valor de tipo *Cadena* que presenta el número especificado de caracteres desde el final de la cadena especificada.

## <a name="syntax"></a>Sintaxis

```vb
RIGHT (text, number)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadena*

Valor de tipo *Cadena* que representa el texto original.

`number`: *Entero*

El número de caracteres que se deben devolver desde el final del texto original.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="example"></a>Ejemplo

`RIGHT ("Sample", 3)` devuelve **"ple"**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
