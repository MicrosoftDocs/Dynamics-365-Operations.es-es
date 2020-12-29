---
title: Función EMPTYLIST ER
description: En este tema se proporciona información sobre cómo usar la función EMPTYLIST de informes electrónicos (ER).
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
ms.openlocfilehash: ccb52d7d88f292720360ae913ead5be239165193
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687679"
---
# <a name="emptylist-er-function"></a>Función EMPTYLIST ER

[!include [banner](../includes/banner.md)]

La función `EMPTYLIST` devuelve un valor *Lista de registros* vacío usando la lista especificada como origen para la estructura de la lista.

## <a name="syntax"></a>Sintaxis

```vb
EMPTYLIST (list)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

La ruta válida de un origen de datos del tipo de datos *Lista de registros*.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

La lista de registros resultante.

## <a name="example"></a>Ejemplo

`EMPTYLIST (SPLIT ("abc", 1))` devuelve una nueva lista vacía que tiene la misma estructura que la lista que se devuelve por la función `SPLIT` utilizada.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)
