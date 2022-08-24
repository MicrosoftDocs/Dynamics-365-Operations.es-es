---
title: Función CN_GBT_ADDITIONALDIMENSIONID de ER
description: Este artículo proporciona información general sobre cómo usar la función CN_GBT_ADDITIONALDIMENSIONID de informes electrónicos (ER).
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
ms.openlocfilehash: 0ed2593f865a4764b1c6172722d701a0a10ba5f8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281764"
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
