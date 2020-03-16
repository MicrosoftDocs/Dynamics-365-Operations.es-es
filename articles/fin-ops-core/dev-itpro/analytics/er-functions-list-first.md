---
title: Función FIRST de ER
description: Este tema proporciona información general sobre cómo usar la función FIRST de informes electrónicos (ER).
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
ms.openlocfilehash: 4d10abcf15b93961bd2ba4aec22914825d9ac38c
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042099"
---
# <a name="FIRST">Función FIRST de ER</a>

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
