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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 747b661d0dee4e9c27741e167c89f9ef7eefa470
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745330"
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
