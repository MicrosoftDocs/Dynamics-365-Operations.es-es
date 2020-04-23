---
title: Función LISTJOIN de ER
description: En este tema se proporciona información sobre cómo usar la función LISTJOIN de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3b5b82917e3083b5ffe4546a6a15fd14938383a
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "3249044"
---
# <a name=""></a><a name="LISTJOIN">Función LISTJOIN de ER</a>

[!include [banner](../includes/banner.md)]

La función `LISTJOIN` devuelve un valor *Lista de registros* que consiste en una lista de registros nueva unida creada a partir de los argumentos especificados.

## <a name="syntax"></a>Sintaxis

```vb
LIST (list 1 [, list 2, …, list N])
```

## <a name="arguments"></a>Argumentos

`list 1`: *Lista de registros*

Una referencia a un origen de datos de tipo de datos *Lista de registros*. Este argumento es obligatorio.

`list N`: *Lista de registros*

Una referencia a un origen de datos de tipo de datos *Lista de registros*. Estos argumentos adicionales son opcionales.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

La lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

La estructura de la lista que se crea contiene solo los campos que están presentes en la estructura de cada lista registro que se menciona en los argumentos.

## <a name="example"></a>Ejemplo

Especifica el origen de datos **Registro 1** del tipo `Container`. Esta fuente de datos contiene los siguientes campos anidados del tipo `Calculated field`:

- **Código**: este campo contiene una expresión que devuelve un valor de tipo `String`.
- **Cantidad**: este campo contiene una expresión que devuelve un valor de tipo `Real`.

Entonces especifique el origen de datos **Registro 2** del tipo `Container`. Esta fuente de datos contiene los siguientes campos anidados del tipo `Calculated field`:

- **Cantidad**: este campo contiene una expresión que devuelve un valor de tipo `Real`.
- **IsValid**: este campo contiene una expresión que devuelve un valor de tipo `Boolean`.

En este caso, la expresión `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` devuelve una nueva lista que contiene dos registros. La estructura de esta lista consta de un solo campo **Importe** del tipo `Real`, porque este campo es el único campo que se presenta en cada argumento de la función llamada.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)
