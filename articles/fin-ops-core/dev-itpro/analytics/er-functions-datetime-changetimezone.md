---
title: Función CHANGETIMEZONE ER
description: En este artículo se proporciona información sobre cómo usar la función CHANGETIMEZONE de informes electrónicos (ER).
author: NickSelin
ms.date: 09/09/2021
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: AX 10.0.23
ms.openlocfilehash: be94f57cfcb6115ea386a279c379662f7d401d11
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903596"
---
# <a name="changetimezone-er-function"></a>Función CHANGETIMEZONE ER

[!include [banner](../includes/banner.md)]

La función `CHANGETIMEZONE` devuelve un valor *[Fecha y hora](er-formula-supported-data-types-primitive.md#datetime)* que se convierte de un determinado valor de datos a un valor de fecha / hora en hora universal coordinada (hora meridiano de Greenwich \[GMT\]).

## <a name="syntax"></a>Sintaxis

```vb
CHANGETIMEZONE (datetime, base time zone, target time zone)
```

## <a name="arguments"></a>Argumentos

`datetime`: *Fecha y hora*

Un valor de fecha / hora en la zona horaria de la hora universal coordinada que representa el valor de fecha / hora que se va a convertir.

`base time zone`: *[String](er-formula-supported-data-types-primitive.md#string)*

El nombre de la zona horaria a la que se cambia un valor de fecha / hora determinado antes de la conversión.

`target time zone`: *Cadena*

El nombre de la zona horaria a la que se cambia un valor de fecha / hora convertido durante la conversión.

## <a name="return-values"></a>Valores de retorno

*Fecha y hora*

El valor de fecha / hora resultante en la zona horaria de la hora universal coordinada.

## <a name="usage-notes"></a>Notas de uso

Para especificar zonas horarias de origen y destino, puede utilizar nombres de zona horaria que se [proporcionen](https://data.iana.org/time-zones/releases/) por la [Autoridad de números asignados de Internet (IANA)](https://www.iana.org/) o que sean [admitidos](/windows-hardware/manufacture/desktop/default-time-zones) por Microsoft Windows.

En tiempo de ejecución, la excepción "Zona horaria" '\<time zone name\>' no existe" se lanza si el nombre proporcionado no se encuentra en la lista de IANA o en el registro de Windows.

Para las zonas horarias en las que se observa el horario de verano, la conversión considera la compensación del horario de verano del horario universal coordinado. La última información disponible sobre esta compensación se utiliza durante la conversión.

## <a name="example-1"></a>Ejemplo 1

En este ejemplo, se utilizan los nombres de las zonas horarias de Windows.

Configura el origen de datos **DSX** del tipo **Campo calculado**. Contiene la siguiente expresión.

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "E. Europe Standard Time", "Hawaiian Standard Time"), "O")
)
```

Si configura la expresión del origen de datos **DSY** del tipo **Campo calculado** como `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, el origen de datos **DSX** devuelve el texto **2021-06-01T12:55:00.0000000+00:00 -> 2021-05-31T23:55:00.0000000+00:00**. Este texto muestra que la diferencia horaria entre las dos zonas horarias proporcionadas el 1 de junio es más de 24 horas. Por lo tanto, el valor de fecha / hora convertido es un día antes que el valor de fecha / hora dado, porque la zona horaria base está por delante de la zona horaria objetivo.

Si configura la expresión del origen de datos **DSY** del tipo **Campo calculado** como `DATETIMEVALUE ("01-Dec-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, el origen de datos **DSX** devuelve el texto **2021-12-01T12:55:00.0000000+00:00 -> 2021-12-01T00:55:00.0000000+00:00**. Este texto muestra que la diferencia horaria entre las dos zonas horarias proporcionadas el 1 de diciembre es menos de 24 horas. Por lo tanto, el valor de fecha / hora convertido es igual al valor de fecha / hora dado.

> [!NOTE]
> La misma expresión devuelve una variación diferente entre los valores de fecha / hora proporcionados y convertidos para el mismo par de zonas horarias porque se observa una diferencia horaria de horario de verano de la hora universal coordinada diferente para las zonas horarias proporcionadas en una fecha / hora determinadas.

## <a name="example-2"></a>Ejemplo 2

En este ejemplo, se utilizan los nombres de las zonas horarias de IANA.

Configura el origen de datos **DSX** del tipo **Campo calculado**. Contiene la siguiente expresión.

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "Europe/Athens", "US/Hawaii"), "O")
)
```

Si configura la expresión del origen de datos **DSY** del tipo **Campo calculado** como `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, el origen de datos **DSX** devuelve el texto **2021-06-01T12:55:00.0000000+00:00 -> 2021-05-31T23:55:00.0000000+00:00**. Este texto muestra que la diferencia horaria entre las dos zonas horarias proporcionadas el 1 de junio es más de 24 horas. Por lo tanto, el valor de fecha / hora convertido es un día antes que el valor de fecha / hora dado, porque la zona horaria base está por delante de la zona horaria objetivo.

Si configura la expresión del origen de datos **DSY** del tipo **Campo calculado** como `DATETIMEVALUE ("01-Dec-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, el origen de datos **DSX** devuelve el texto **2021-12-01T12:55:00.0000000+00:00 -> 2021-12-01T00:55:00.0000000+00:00**. Este texto muestra que la diferencia horaria entre las dos zonas horarias proporcionadas el 1 de diciembre es menos de 24 horas. Por lo tanto, el valor de fecha / hora convertido es igual al valor de fecha / hora dado.

## <a name="example-3"></a>Ejemplo 3

Configura el origen de datos **DSX** del tipo **Campo calculado**. Contiene la siguiente expresión.

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "US/Hawaii", "Europe/Athens"), "O")
)
```

Si configura la expresión del origen de datos **DSY** del tipo **Campo calculado** como `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, el origen de datos **DSX** devuelve el texto **2021-06-01T12:55:00.0000000+00:00 -> 2021-06-02T01:55:00.0000000+00:00'**. Este texto muestra que la diferencia horaria entre las dos zonas horarias proporcionadas el 1 de junio es más de 24 horas. Por lo tanto, el valor de fecha / hora convertido es un día después que el valor de fecha / hora dado, porque la zona horaria de destino está por delante de la zona horaria base.

## <a name="example-4"></a>Ejemplo 4

Es posible que reciba una marca de fecha / hora de una fuente externa como texto que no contiene información sobre la zona horaria. Sin embargo, es posible que conozca la zona horaria en la que opera la fuente. Por ejemplo, recibe el sello de fecha / hora **01/12 / 2021 12:55:00** de un servicio que se opera en España. Para guardar correctamente este valor de fecha / hora en la base de datos, complete la siguiente conversión:

- Configurar el origen de datos **DSY** del tipo **Campo calculado** para convertir una marca de fecha / hora de texto al valor de fecha / hora de Hora universal coordinada.

    `DATETIMEVALUE ("01/12/2021 12:55:00", "dd/MM/yyyy HH:mm:ss", "ES")`

- Configure el origen de datos **DSX** del tipo **Campo calculado** para cambiar el valor de fecha / hora convertido a Hora universal coordinada como el valor de fecha / hora de la zona horaria de la fuente externa.

    `CHANGETIMEZONE(DSY, "Romance Standard Time", "GMT Standard Time")`

> [!NOTE]
> Cuando usa la función `CHANGETIMEZONE` para la conversión de fecha / hora, tenga en cuenta que cualquier valor de fecha / hora se almacena en la base de datos como el valor en la zona horaria universal coordinada. Antes de que este valor se pueda presentar en las páginas de la aplicación, se transforma. La transformación considera la zona horaria que se [establece](../../fin-ops/organization-administration/tasks/set-users-preferred-time-zone.md) como zona preferida para el usuario de la aplicación que ha iniciado sesión actualmente.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de fecha y de tiempo](er-functions-category-datetime.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
