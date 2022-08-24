---
title: Función TRIM de ER
description: Este artículo proporciona información general sobre cómo usar la función TRIM de informes electrónicos (ER).
author: kfend
ms.date: 02/28/2022
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
ms.openlocfilehash: 95b8d2989d705c4998da0af8e683adf567edfe92
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273110"
---
# <a name="trim-er-function"></a>Función TRIM de ER

[!include [banner](../includes/banner.md)]

La función `TRIM` devuelve la cadena de texto especificada como un valor *Cadena* después de que los caracteres de tabulación, retorno de carro, salto de línea y salto de página hayan sido reemplazados por un solo carácter de espacio, después de que se hayan truncado los espacios iniciales y finales, y después de que se hayan eliminado varios espacios entre palabras.

## <a name="syntax"></a>Sintaxis

```vb
TRIM (text)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadena*

La ruta válida de un origen de datos de tipo *Cadena*.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

En algunos casos, es posible que desee truncar los espacios iniciales y finales, pero prefiere mantener el formato del texto especificado. Por ejemplo, cuando este texto representa una dirección que podría ingresarse en el cuadro de texto de varias líneas y podría contener formato de salto de línea y retorno de carro. En este caso, utilice la siguiente expresión: `REPLACE(text,"^[ \t]+|[ \t]+$","", true)` donde `text` es el argumento que hace referencia a la cadena de texto especificada.

## <a name="example-1"></a>Ejemplo 1

`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` devuelve **"Sample text"**.

## <a name="example-2"></a>Ejemplo 2

`TRIM (CONCATENATE (CHAR(10), "`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`", CHAR(9),"`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`", CHAR(13)))` devuelve **"Sample text"**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)

[Función REPLACE de ER](er-functions-text-replace.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
