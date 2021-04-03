---
title: Función POWER de ER
description: Este tema proporciona información general sobre cómo usar la función POWER de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 9c45e7f9b47a3f0ff4445b1dd160def0ada3a56e
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570431"
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