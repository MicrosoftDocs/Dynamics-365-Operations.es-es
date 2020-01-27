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
ms.openlocfilehash: cb768b400e3ddb99e7c8b05905d7a2dd9e4392de
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915910"
---
# <a name="POWER">Función POWER de ER</a>

[!include [banner](../includes/banner.md)]

La función `POWER` devuelve un valor *Real* que representa el resultado de elevar el número positivo especificado a la potencia especificada.

## <a name="syntax"></a>Sintaxis

```
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
