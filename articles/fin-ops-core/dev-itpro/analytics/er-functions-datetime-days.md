---
title: Función DAYS ER
description: En este artículo se proporciona información sobre cómo usar la función DAYS de informes electrónicos (ER).
author: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: a0c50e36bbf0c2bd999a17631e3e00d2feb162fd
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268737"
---
# <a name="days-er-function"></a>Función DAYS ER

[!include [banner](../includes/banner.md)]

La función `DAYS` devuelve un valor *Entero* que representa el número de días entre una fecha especificada y una segunda fecha especificada.

## <a name="syntax"></a>Sintaxis

```vb
DAYS (date 1, date 2) as Integer
```

## <a name="arguments"></a>Argumentos

`date 1`: *Fecha*

Un valor de fecha que representa la fecha de inicio para el cálculo del número de días.

`date 2`: *Fecha*

Un valor de fecha que representa la fecha final para el cálculo del número de días.

## <a name="return-values"></a>Valores de retorno

*Entero*

El valor numérico resultante.

## <a name="usage-notes"></a>Notas de uso

La función `DAYS` devuelve un valor positivo cuando la primera fecha es posterior a la segunda fecha, devuelve **0** (cero) cuando la primera fecha es igual a la segunda fecha y devuelve un valor negativo cuando la primera fecha es anterior a la segunda fecha.

## <a name="example"></a>Ejemplo

`DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` devuelve **-1**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de fecha y de tiempo](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
