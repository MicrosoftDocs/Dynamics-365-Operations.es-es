---
title: Función DAYOFYEAR ER
description: Este tema proporciona información general sobre cómo usar la función DATEOFYEAR de informes electrónicos (ER).
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 569e988db91ff992fb7db6e7fd6e8c6aa6a1a3e8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746924"
---
# <a name="dayofyear-er-function"></a>Función DAYOFYEAR ER

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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]