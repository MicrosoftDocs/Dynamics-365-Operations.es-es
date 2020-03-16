---
title: Función DAYS ER
description: Este tema proporciona información general sobre cómo usar la función DAYS de informes electrónicos (ER).
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
ms.openlocfilehash: 62e34628712066d92a244676123ce928a468ea9e
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042398"
---
# <a name="DAYS">Función DAYS ER</a>

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
