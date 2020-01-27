---
title: Función INTVALUE ER
description: Este tema proporciona información general sobre cómo usar la función INTVALUE de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 2b279de39cf91c3919145735518034fc60cd3341
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917727"
---
# <a name="INTVALUE">Función INTVALUE ER</a>

[!include [banner](../includes/banner.md)]

La función `INTVALUE` devuelve un valor *Int* que representa la cadena especificada.

## <a name="syntax-1"></a>Sintaxis 1

```
INTVALUE (text)
```

## <a name="syntax-2"></a>Sintaxis 2

```
INTVALUE (number)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadena*

Un valor de texto que debe convertirse en un número *Int*.

`number`: *Real* o *Entero*

Un valor numérico *Real* o *Entero* que debe convertirse en un número *Int*.

## <a name="return-values"></a>Valores de retorno

*Int*

El valor numérico resultante.

## <a name="usage-notes"></a>Notas de uso

Se trunca cualquier posición decimal.

## <a name="example-1"></a>Ejemplo 1

`INTVALUE ("100.77")` devuelve el valor *Int* **100**.

## <a name="example-2"></a>Ejemplo 2

`INTVALUE (-100.77)` devuelve el valor *Int* **-100**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de conversión de tipos](er-functions-category-type-conversion.md)
