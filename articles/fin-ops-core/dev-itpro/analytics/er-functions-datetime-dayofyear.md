---
title: Función DAYOFYEAR ER
description: Este tema proporciona información general sobre cómo usar la función DATEOFYEAR de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: d24aabb582151b0b357b64a988cc932a9c9f3cea
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070676"
---
# <a name="DAYOFYEAR">Función DAYOFYEAR ER</a>

[!include [banner](../includes/banner.md)]

La función `DAYOFYEAR` devuelve un valor *Entero* que representa el número de días entre el 1 de enero y la fecha especificada.

## <a name="syntax"></a>Sintaxis

```vb
DAYOFYEAR (date) as Integer
```

## <a name="arguments"></a>Argumentos

`date`: *Fecha*

Un valor de fecha que representa la fecha a usar para el cálculo del número de días.

## <a name="return-values"></a>Valores de retorno

*Entero*

El valor numérico resultante.

## <a name="example-1"></a>Ejemplo 1

`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` devuelve **61**.

## <a name="example-2"></a>Ejemplo 2

`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` devuelve **1**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de fecha y de tiempo](er-functions-category-datetime.md)
