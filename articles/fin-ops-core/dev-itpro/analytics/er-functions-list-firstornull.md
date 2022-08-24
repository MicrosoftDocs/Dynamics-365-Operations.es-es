---
title: Función FIRSTORNULL de ER
description: En este artículo se explica cómo usar la función FIRSTORNULL de informes electrónicos (ER)
author: kfend
ms.date: 11/29/2019
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
ms.openlocfilehash: 7ee1a5c1b6ac13581608f9adbda42fae0706d225
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273200"
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
