---
title: Función COUNT ER
description: En este artículo se proporciona información sobre cómo usar la función COUNT de informes electrónicos (ER).
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
ms.openlocfilehash: 64c8be659b564d612f3127d46e54535c73ae21ce
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287260"
---
# <a name="count-er-function"></a>Función COUNT ER

[!include [banner](../includes/banner.md)]

La función `COUNT` devuelve un valor *Entero* que representa el número de registros en la lista especificada, si la lista no está vacía. Si la lista está vacía, esta función devuelve **0** (cero).

## <a name="syntax"></a>Sintaxis

```vb
COUNT (list)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

La ruta válida de un origen de datos del tipo de datos *Lista de registros*.

## <a name="return-values"></a>Valores de retorno

*Entero*

El valor numérico resultante.

## <a name="example"></a>Ejemplo

`COUNT (SPLIT("abcd" , 3))` devuelve **2**, porque la función `SPLIT` que se utiliza en este ejemplo crea una lista que consta de dos registros.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
