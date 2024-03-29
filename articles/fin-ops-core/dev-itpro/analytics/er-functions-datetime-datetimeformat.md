---
title: Función DATETIMEFORMAT ER
description: En este artículo se proporciona información sobre cómo usar la función DATETIMEFORMAT de informes electrónicos (ER).
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
ms.openlocfilehash: e21b676046b6279826a728657fcc0d2a00a38b76
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287380"
---
# <a name="datetimeformat-er-function"></a>Función DATETIMEFORMAT ER

[!include [banner](../includes/banner.md)]

La función `DATETIMEFORMAT` devuelve un valor *[Cadena](er-formula-supported-data-types-primitive.md#string)* que presenta un valor determinado de fecha/hora como texto en el formato especificado y en una [cultura](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcional especificada. Para obtener información acerca de los formatos admitidos, vea [estándar](/dotnet/standard/base-types/standard-date-and-time-format-strings) y [personalizado](/dotnet/standard/base-types/custom-date-and-time-format-strings).

## <a name="syntax-1"></a>Sintaxis 1

```vb
DATETIMEFORMAT (datetime, format)
```

## <a name="syntax-2"></a>Sintaxis 2

```vb
DATETIMEFORMAT (datetime, format, culture)
```

## <a name="arguments"></a>Argumentos

`datetime`: *[DateTime](er-formula-supported-data-types-primitive.md#datetime)*

Un valor de fecha / hora que representa la fecha y la hora a formatear.

`format`: *Cadena*

El formato de la cadena de salida. Para obtener información acerca de los formatos admitidos, vea [estándar](/dotnet/standard/base-types/standard-date-and-time-format-strings) y [personalizado](/dotnet/standard/base-types/custom-date-and-time-format-strings).

> [!NOTE]
> La cadena de formato distingue mayúsculas de minúsculas cuando utiliza un formato estándar o un formato personalizado. Por ejemplo, el especificador de formato "d" [estándar](/dotnet/standard/base-types/standard-date-and-time-format-strings) devuelve la fecha utilizando el patrón de fecha corta, mientras que el especificador de formato estándar "D" devuelve la fecha utilizando el patrón de fecha larga. Además, el especificador de formato "M" [personalizado](/dotnet/standard/base-types/custom-date-and-time-format-strings) devuelve los meses del 1 al 12, mientras que el especificador de formato personalizado "m" devuelve los minutos del 0 al 59.

`culture`: *Cadena*

La cultura a utilizar para formatear. Para obtener información sobre las culturas admitidas, consulte [cultura](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de cadena resultante.

## <a name="usage-notes"></a>Notas de uso

Si la cultura no se define como un argumento de la función llamada, el valor de `culture` está definido por el contexto de llamada. Por ejemplo, si la función `DATETIMEFORMAT` se llama mediante el uso de la sintaxis 1 en un formato de informe electrónico (ER) para un elemento **ARCHIVO** configurado para usar la cultura alemana, la conversión se realizará utilizando la cultura alemana. El valor de `culture` predeterminado es **EN-US**.

Cuando la función `DATETIMEFORMAT` convierte un valor de fecha / hora dado, considera la configuración de zona horaria del usuario de la aplicación que ejecuta el formato ER al que se llama la función en el contexto.

## <a name="example-1"></a>Ejemplo 1

`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` devuelve la fecha/hora del servidor actual, 24 de diciembre de 2015, como **“24-12-2015”**, basado en el formato personalizado especificado.

## <a name="example-2"></a>Ejemplo 2

`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` devuelve la fecha/hora de sesión de la aplicación actual, 24 de diciembre de 2015, como la cadena **"24.12.2015"**, basado en la cultura alemana seleccionada y el formato especificado.

## <a name="example-3"></a>Ejemplo 3

`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` devuelve el valor de la cadena **2019-11-12T08:00:00.0000000-08:00** cuando se llama a la función durante un proceso iniciado por un usuario de la aplicación que tiene el valor de zona horaria **(GMT-08: 00) Hora del Pacífico (EE. UU. y Canadá)** en la sección **Preferencias de idioma y país / región**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de fecha y de tiempo](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
