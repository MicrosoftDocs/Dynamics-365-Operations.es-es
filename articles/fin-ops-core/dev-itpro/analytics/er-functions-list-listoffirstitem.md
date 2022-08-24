---
title: Función LISTOFFIRSTITEM de ER
description: En este artículo se proporciona información sobre cómo usar la función LISTOFFIRSTITEM de informes electrónicos (ER).
author: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: dede32c58ef8dc67028ea17b8a26189f62f73593
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275597"
---
# <a name="listoffirstitem-er-function"></a>Función LISTOFFIRSTITEM de ER

[!include [banner](../includes/banner.md)]

La función `LISTOFFIRSTITEM` devuelve un valor *Lista de registros* que consiste en solo el primer registro de la lista especificada.

## <a name="syntax"></a>Sintaxis

```vb
LISTOFFIRSTITEM (list)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

La ruta válida de un origen de datos del tipo de datos *Lista de registros*.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

La lista de registros resultante.

## <a name="example"></a>Ejemplo

La expresión `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` devuelve el valor del texto **"A"**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
