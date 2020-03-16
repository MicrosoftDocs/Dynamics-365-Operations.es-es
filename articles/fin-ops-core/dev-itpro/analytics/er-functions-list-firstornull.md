---
title: Función FIRSTORNULL de ER
description: En este tema se explica cómo usar la función FIRSTORNULL de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 11/29/2019
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
ms.openlocfilehash: 86c8a0ae21ffeb6268efbbd198f7c709c2ad54f6
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042122"
---
# <a name="FIRSTORNULL">Función FIRSTORNULL de ER</a>

[!include [banner](../includes/banner.md)]

La función `FIRSTORNULL` devuelve el primer registro de la lista especificada como un valor *Contenedor (registro)*, si ese registro no está vacío. Si el registro está vacío, esta función devuelve un valor nulo *Contenedor (registro)*.

## <a name="syntax"></a>Sintaxis

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

La ruta válida de un origen de datos del tipo de datos *Lista de registros*.

## <a name="return-values"></a>Valores de retorno

*Contenedor (registro)*

El valor de registro resultante.

## <a name="example"></a>Ejemplo

La expresión `FIRSTORNULL(SPLIT("",1)).Value` devuelve una cadena vacía (**""**).

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)
