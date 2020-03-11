---
title: Función ISVALIDCHARACTERISO7064 de ER
description: Este tema proporciona información general sobre cómo usar la función ISVALIDCHARACTERISO7064 de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c858ad72db7afe63baca8288f312548c4fc37d5c
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041409"
---
# <a name="ISVALIDCHARACTERISO7064">Función ISVALIDCHARACTERISO7064 de ER</a>

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
