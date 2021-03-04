---
title: Función ABS de ER
description: Este tema proporciona información general sobre cómo usar la función ABS de informes electrónicos (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3c7156b9990397822a6bea9ed8b3df8f65490572
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683290"
---
# <a name="abs-er-function"></a>Función ABS de ER

[!include [banner](../includes/banner.md)]

La función `ABS` devuelve el valor absoluto (módulo) de la cifra especificada como un número *Real*. Es decir, devuelve el número sin su signo.

## <a name="syntax"></a>Sintaxis

```vb
ABS (number)
```

## <a name="arguments"></a>Argumentos

`number`: *Real*

Un valor numérico del que desea el módulo.

## <a name="return-values"></a>Valores de retorno

*Real*

El valor numérico resultante.

## <a name="example"></a>Ejemplo

`ABS (-1)` devuelve **1**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones matemáticas](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]