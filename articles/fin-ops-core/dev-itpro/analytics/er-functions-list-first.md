---
title: Función FIRST de ER
description: Este tema proporciona información general sobre cómo usar la función FIRST de informes electrónicos (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: d30c8481866ccf3f7080197b37586a0460a4ad2c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746588"
---
# <a name="first-er-function"></a>Función FIRST de ER

[!include [banner](../includes/banner.md)]

La función `FIRST` devuelve el primer registro de la lista especificada como un valor *Contenedor (registro)*, si esa lista no está vacía. Si la lista está vacía, esta función genera una excepción.

## <a name="syntax"></a>Sintaxis

```vb
FIRST (list)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

La ruta válida de un origen de datos del tipo de datos *Lista de registros*.

## <a name="return-values"></a>Valores de retorno

*Contenedor (registro)*

El valor de registro resultante.

## <a name="example-1"></a>Ejemplo 1

La expresión `FIRST(SPLIT("ABC",1)).Value` devuelve el valor del texto **"A"**.

## <a name="example-2"></a>Ejemplo 2

La expresión `FIRST(SPLIT("",1)).Value` lanza una excepción en tiempo de ejecución.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]