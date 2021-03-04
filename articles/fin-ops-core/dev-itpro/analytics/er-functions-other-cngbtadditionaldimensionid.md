---
title: Función CN_GBT_ADDITIONALDIMENSIONID de ER
description: Este tema proporciona información general sobre cómo usar la función CN_GBT_ADDITIONALDIMENSIONID de informes electrónicos (ER).
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
ms.openlocfilehash: 38908c63c35465747505479bc983ada891f9e2bf
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686819"
---
# <a name="cn_gbt_additionaldimensionid-er-function"></a>Función CN_GBT_ADDITIONALDIMENSIONID de ER

[!include [banner](../includes/banner.md)]

La función `CN_GBT_ADDITIONALDIMENSIONID` devuelve un valor *Cadena* que representa un solo Id. de dimensión financiera que se toma de una cadena especificada. La cadena especificada presenta todas las dimensiones como una lista de ID separadas por comas.

## <a name="syntax"></a>Sintaxis

```vb
CN_GBT_ADDITIONALDIMENSIONID (text, number)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadena*

El valor de *Cadena* que presenta todas las dimensiones como una lista de identificadores separadas por comas.

`number`: Entero

Un valor *Entero* que define el código de la secuencia de la dimensión solicitada en la cadena especificada.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="example"></a>Ejemplo

`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` devuelve **"CC"**.

## <a name="additional-resources"></a>Recursos adicionales

[Otras funciones (específicas de dominio empresarial)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]