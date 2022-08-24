---
title: Función TEXT de ER
description: Este artículo proporciona información general sobre cómo usar la función TEXT de informes electrónicos (ER).
author: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: a32da5588c5231b20bc8166d20888c1611ca273e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278868"
---
# <a name="text-er-function"></a>Función TEXT de ER

[!include [banner](../includes/banner.md)]

La función `TEXT` devuelve el número especificado como un valor de tipo *Cadena* después de que se haya convertido en una cadena de texto que se formatea según la configuración regional del servidor de la instancia actual de la aplicación.

## <a name="syntax"></a>Sintaxis

```vb
TEXT (number)
```

## <a name="arguments"></a>Argumentos

`number`: *Entero* o *Real*

Un valor numérico que debe convertirse en una cadena de texto.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

Para los valores del tipo *Real*, la conversión de la cadena está limitada a dos posiciones decimales.

## <a name="example"></a>Ejemplo

Si se define la configuración regional del servidor de la instancia de Microsoft Dynamics 365 Finance como **EN-US**, `TEXT (NOW ())` devuelve la fecha de la sesión de Finance actual, el 17 de diciembre de 2015, como la cadena de texto **"12/17/2015 07:59:23 AM"**. `TEXT (1/3)` devuelve **"0.33"**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
