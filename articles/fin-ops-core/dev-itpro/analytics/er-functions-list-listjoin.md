---
title: Función LISTJOIN de ER
description: En este artículo se proporciona información sobre cómo usar la función LISTJOIN de informes electrónicos (ER).
author: kfend
ms.date: 04/01/2020
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: ec8a5985277de8036ec8ad51b947a8bab098a1c3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291216"
---
# <a name="listjoin-er-function"></a>Función LISTJOIN de ER

[!include [banner](../includes/banner.md)]

La función `LISTJOIN` devuelve un valor *Lista de registros* que consiste en una lista de registros nueva unida creada a partir de los argumentos especificados.

## <a name="syntax"></a>Sintaxis

```vb
LISTJOIN (list 1 [, list 2, …, list N])
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

![Página de diseñador de asignación de modelos de ER.](./media/er-functions-list-listjoin-image1.gif)

En este caso, la expresión `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` devuelve una nueva lista que contiene dos registros.

![Página del diseñador de asignación de modelos de ER con dos registros.](./media/er-functions-list-listjoin-image2.gif)

La estructura de esta lista consta de un solo campo **Importe** del tipo `Real`, porque este campo es el único campo que se presenta en cada argumento de la función llamada.

![Campo de cantidad de la página de diseñador de asignación de modelos de ER.](./media/er-functions-list-listjoin-image3.gif)

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)

[Depurar las fuentes de datos de un formato ER ejecutado para analizar el flujo de datos y la transformación](er-debug-data-sources.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
