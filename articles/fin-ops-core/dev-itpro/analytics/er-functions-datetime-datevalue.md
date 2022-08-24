---
title: Función DATEVALUE ER
description: En este artículo se proporciona información sobre cómo usar la función DATEVALUE de informes electrónicos (ER).
author: kfend
ms.date: 09/08/2021
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
ms.openlocfilehash: 290a4665d3527c0f0954c46cb0a0a14677b93218
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268710"
---
# <a name="datevalue-er-function"></a>Función DATEVALUE ER

[!include [banner](../includes/banner.md)]

La función `DATEVALUE` devuelve un valor *[Fecha](er-formula-supported-data-types-primitive.md#date)* que se convierte de un determinado valor de texto en el formato especificado y en una [cultura](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcionalmente especificada a un valor de fecha. Para obtener información acerca de los formatos admitidos, vea [estándar](/dotnet/standard/base-types/standard-date-and-time-format-strings) y [personalizado](/dotnet/standard/base-types/custom-date-and-time-format-strings).

## <a name="syntax-1"></a>Sintaxis 1

```vb
DATEVALUE (text, format)
```

## <a name="syntax-2"></a>Sintaxis 2

```vb
DATEVALUE (text, format, culture)
```

## <a name="arguments"></a>Argumentos

`text`: *[Cadena](er-formula-supported-data-types-primitive.md#string)*

Texto que representa el valor a formatear.

`format`: *Cadena*

El formato del texto proporcionado. Para obtener información acerca de los formatos admitidos, vea [estándar](/dotnet/standard/base-types/standard-date-and-time-format-strings) y [personalizado](/dotnet/standard/base-types/custom-date-and-time-format-strings).

`culture`: *Cadena*

La cultura que se utiliza para formatear el texto dado. Para obtener información sobre las culturas admitidas, consulte [cultura](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).

## <a name="return-values"></a>Valores de retorno

*Fecha*

El valor de fecha resultante.

## <a name="usage-notes"></a>Notas de uso

Cuando la cultura no se define como un argumento de la función llamada, el valor de `culture` está definido por el contexto de llamada. Por ejemplo, si la función `DATEVALUE` se llama mediante el uso de la sintaxis 1 en un formato de informe electrónico (ER) para un elemento **ARCHIVO** configurado para usar la cultura alemana, la conversión se realizará utilizando la cultura alemana. El valor de `culture` predeterminado es **EN-US**.

## <a name="example-1"></a>Ejemplo 1

`DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` devuelve la fecha **21 de diciembre de 2016** basada el formato especificado y la cultura predeterminada **EN-US** de la aplicación.

## <a name="example-2"></a>Ejemplo 2

`DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` devuelve el valor de la fecha **21 de enero de 2016**, según el formato y la cultura personalizados especificados.

Sin embargo, `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` lanza una excepción para informar al usuario de que la cadena especificada no se reconoce como fecha válida para la cultura especificada.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de fecha y de tiempo](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
