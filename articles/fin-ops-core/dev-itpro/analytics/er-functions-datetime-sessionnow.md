---
title: Función SESSIONNOW ER
description: En este tema se proporciona información sobre cómo usar la función SESSIONNOW de informes electrónicos (ER).
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: fc532a96c7e52e6a12877ae88d1a6183829a1282d43c7df52dd90e536a7e3d75
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6734825"
---
# <a name="sessionnow-er-function"></a>Función SESSIONNOW ER

[!include [banner](../includes/banner.md)]

La función `SESSIONNOW` devuelve un valor *Fecha y hora* que representa la fecha y hora actuales de la sesión de la aplicación.

## <a name="syntax"></a>Sintaxis

```vb
SESSIONNOW ()
```

## <a name="return-values"></a>Valores de retorno

*DateTime*

El valor de fecha/hora resultante.

## <a name="example"></a>Ejemplo

`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` devuelve la fecha/hora de sesión de la aplicación actual, 24 de diciembre de 2015, como la cadena **"24.12.2015"**, basado en la cultura alemana seleccionada y el formato especificado.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de fecha y de tiempo](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]