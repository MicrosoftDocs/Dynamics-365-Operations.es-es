---
title: Función POWER de ER
description: En este artículo se proporciona información sobre cómo usar la función POWER de informes electrónicos (ER).
author: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 9b6693d7c1afebcf9c30d1bf8d72950053c305bd
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274008"
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
