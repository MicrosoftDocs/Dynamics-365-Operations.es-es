---
title: Función TEXT de ER
description: Este tema proporciona información general sobre cómo usar la función TEXT de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 5da7375020be827f432ba97740da37abe48962fc
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560070"
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