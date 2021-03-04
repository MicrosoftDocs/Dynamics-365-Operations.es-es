---
title: Función COUNT ER
description: Este tema proporciona información general sobre cómo usar la función COUNT de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: b3a5bb33964c70c85c7d8571057060c1c2b9d433
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687729"
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