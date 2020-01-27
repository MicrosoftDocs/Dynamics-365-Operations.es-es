---
title: Función ADDDAYS ER
description: Este tema proporciona información general sobre cómo usar la función ADDDAYS de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/03/2019
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
ms.openlocfilehash: dd1290538c506cd0db6eb21a304ff9812c808f17
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916462"
---
# <a name="ADDDAYS">Función ADDDAYS ER</a>

[!include [banner](../includes/banner.md)]

La función `ADDDAYS` calcula un valor *Fecha y hora* que es el número especificado de días antes o después de una fecha de inicio especificada.

## <a name="syntax"></a>Sintaxis

```
ADDDAYS (datetime, days)
```

## <a name="arguments"></a>Argumentos

`datetime`: *Fecha y hora*

Un valor de fecha / hora que representa la fecha de inicio.

`days`: *Entero*

El número de días antes o después de `datetime`.

## <a name="return-values"></a>Valores de retorno

*DateTime*

El valor de fecha/hora resultante.

## <a name="usage-notes"></a>Notas de uso

Un valor positivo para `days` da una fecha futura. Un valor negativo produce una fecha pasada.

## <a name="example-1"></a>Ejemplo 1

`ADDDAYS (NOW(), 7)` devuelve la fecha y la hora siete días en el futuro.

## <a name="example-2"></a>Ejemplo 2

`ADDDAYS (NOW(), -3)` devuelve la fecha y la hora tres días en el pasado.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de fecha y de tiempo](er-functions-category-datetime.md)
