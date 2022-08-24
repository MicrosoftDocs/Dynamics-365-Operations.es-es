---
title: Función ISVALIDCHARACTERISO7064 de ER
description: En este artículo se proporciona información sobre cómo usar la función ISVALIDCHARACTERISO7064 de informes electrónicos (ER).
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
ms.openlocfilehash: 26ee54d1c3cd5673ec573e2df688780d3902b69d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275387"
---
# <a name="isvalidcharacteriso7064-er-function"></a>Función ISVALIDCHARACTERISO7064 de ER

[!include [banner](../includes/banner.md)]

La función `ISVALIDCHARACTERISO7064` devuelve un valor *Booleano* de **TRUE** si la cadena especificada representa un número internacional de cuenta bancaria válido (IBAN). De lo contrario, la expresión devuelve un valor *Booleano* de **FALSE**.

## <a name="syntax"></a>Sintaxis

```vb
ISVALIDCHARACTERISO7064 (text)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadena*

Un valor de texto que representa un IBAN.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="example"></a>Ejemplo

`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` devuelve **TRUE**. 

`ISVALIDCHARACTERISO7064 ("AT61")` devuelve **FALSE**.

## <a name="additional-resources"></a>Recursos adicionales

[Otras funciones (específicas de dominio empresarial)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
