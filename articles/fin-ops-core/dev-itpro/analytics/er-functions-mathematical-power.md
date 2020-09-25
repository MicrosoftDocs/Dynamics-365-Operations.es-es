---
title: Función POWER de ER
description: Este tema proporciona información general sobre cómo usar la función POWER de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 080b2f9b1ada55209c9470386aceab2d3ef456af
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744584"
---
# <a name="power-er-function"></a>Función POWER de ER

[!include [banner](../includes/banner.md)]

La función `POWER` devuelve un valor *Real* que representa el resultado de elevar el número positivo especificado a la potencia especificada.

## <a name="syntax"></a>Sintaxis

```vb
POWER (number, power)
```

## <a name="arguments"></a>Argumentos

`number`: *Real* o *Entero*

Un valor numérico que debe elevarse a la potencia especificada.

`power`: *Real* o *Entero*

Un valor numérico que representa la potencia específica.

## <a name="return-values"></a>Valores de retorno

*Real*

El valor numérico resultante.

## <a name="example-1"></a>Ejemplo 1

`POWER (10, 2)` devuelve **100**.

## <a name="example-2"></a>Ejemplo 2

`POWER (4, 0.5)` devuelve **2**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones matemáticas](er-functions-category-mathematical.md)
