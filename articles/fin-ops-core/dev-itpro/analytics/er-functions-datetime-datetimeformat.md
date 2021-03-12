---
title: Función DATETIMEFORMAT ER
description: En este tema se proporciona información sobre cómo usar la función DATETIMEFORMAT de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 01/04/2021
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
ms.openlocfilehash: 90bd2900434b1be509f72ec82375e52ea32bc424
ms.sourcegitcommit: 7cfe8931dd454e811a691f5118a4ecae7ba4b478
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/04/2021
ms.locfileid: "4825382"
---
# <a name="datetimeformat-er-function"></a>Función DATETIMEFORMAT ER

[!include [banner](../includes/banner.md)]

La función `DATETIMEFORMAT` devuelve un valor *Cadena* que presenta un valor determinado de fecha/hora como texto en el formato especificado y en una [cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcional especificada. Para obtener información acerca de los formatos admitidos, vea [estándar](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) y [personalizado](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).

## <a name="syntax-1"></a>Sintaxis 1

```vb
DATETIMEFORMAT (datetime, format)
```

## <a name="syntax-2"></a>Sintaxis 2

```vb
DATETIMEFORMAT (datetime, format, culture)
```

## <a name="arguments"></a>Argumentos

`datetime`: *Fecha y hora*

Un valor de fecha / hora que representa la fecha y la hora a formatear.

`format`: *Cadena*

El formato de la cadena de salida.

> [!NOTE]
> La cadena de formato distingue mayúsculas de minúsculas cuando utiliza un formato estándar o un formato personalizado. Por ejemplo, el especificador de formato "d" [estándar](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) devuelve la fecha utilizando el patrón de fecha corta, mientras que el especificador de formato estándar "D" devuelve la fecha utilizando el patrón de fecha larga. Además, el especificador de formato "M" [personalizado](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx) devuelve los meses del 1 al 12, mientras que el especificador de formato personalizado "m" devuelve los minutos del 0 al 59.

`culture`: *Cadena*

La cultura a utilizar para formatear.

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
