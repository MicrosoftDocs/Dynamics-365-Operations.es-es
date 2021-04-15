---
title: Función ISVALIDCHARACTERISO7064 de ER
description: Este tema proporciona información general sobre cómo usar la función ISVALIDCHARACTERISO7064 de informes electrónicos (ER).
author: NickSelin
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
ms.openlocfilehash: 1f102a6a3eafe3b066101370b94fa2f17ad3ad8b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748302"
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