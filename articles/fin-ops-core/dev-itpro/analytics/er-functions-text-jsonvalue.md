---
title: Función JSONVALUE de ER
description: Este tema proporciona información general sobre cómo usar la función JSONVALUE de informes electrónicos (ER).
author: NickSelin
ms.date: 12/11/2019
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
ms.openlocfilehash: e8336e43a236e3f3b875fb3cb81bc139507673c2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746372"
---
# <a name="jsonvalue-er-function"></a>Función JSONVALUE de ER

[!include [banner](../includes/banner.md)]

La función `JSONVALUE` analiza los datos en formato JavaScript Object Notation (JSON) a los que se accede por la ruta especificada y extrae un valor escalar que se basa en el id. especificado. Luego devuelve el valor escalar extraído como valor *Cadena*.

## <a name="syntax"></a>Sintaxis

```vb
JSONVALUE (input, path)
```

## <a name="arguments"></a>Argumentos

`input`: *Cadena*

La ruta válida de un origen de datos de tipo *Cadena* que contiene datos JSON.

`path`: *Cadena*

El identificador de un valor escalar de datos JSON.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="example"></a>Ejemplo

El origen de datos **JsonField** contiene los siguientes datos en formato JSON: **{BuildNumber:7.3.1234.1", "KeyThumbprint":"7366E"}**. En este caso, la expresión `JSONVALUE (JsonField, "BuildNumber")` devuelve el siguiente valor de tipo *Cadena*: **"7.3.1234.1"**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]