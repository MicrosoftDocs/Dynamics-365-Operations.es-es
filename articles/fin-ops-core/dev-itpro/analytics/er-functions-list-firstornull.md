---
title: Función FIRSTORNULL de ER
description: En este tema se explica cómo usar la función FIRSTORNULL de informes electrónicos (ER).
author: NickSelin
ms.date: 11/29/2019
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
ms.openlocfilehash: 1ccc094fc468470ffc857c729b6d8402796785d7
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753225"
---
# <a name="firstornull-er-function"></a>Función FIRSTORNULL de ER

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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]