---
title: Lista de funciones ER en la categoría de fecha y hora
description: Este artículo proporciona información sobre las funciones de fecha y hora que son compatibles con los informes electrónicos (ER).
author: kfend
ms.date: 09/09/2021
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
ms.openlocfilehash: d77f41e10d927a9aae06b9ba0fc58ca237c071cd
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291336"
---
# <a name="list-of-er-functions-in-the-date-and-time-category"></a>Lista de funciones ER en la categoría de fecha y hora

[!include [banner](../includes/banner.md)]

Las funciones de fecha y hora de informes electrónicos (ER) se pueden usar para extraer información de los valores de fecha y hora, y para realizar operaciones en ellos. Este artículo proporciona un resumen de estas funciones.

## <a name="list-of-supported-functions"></a>Lista de funciones permitidas.

| Función | Descripción |
|----------|-------------|
| [AddDays](er-functions-datetime-adddays.md) | Esta función devuelve un valor *[DateTime](er-formula-supported-data-types-primitive.md#datetime)* que es el número especificado de días antes o después de una fecha de inicio especificada. |
| [ChangeTimeZone](er-functions-datetime-changetimezone.md) | Esta función devuelve un valor *DateTime* que se convierte de un determinado valor de fecha/hora en una zona horaria a un valor de fecha/hora de otra zona horaria. |
| [DateFormat](er-functions-datetime-dateformat.md) | Esta función devuelve un valor *[Cadena](er-formula-supported-data-types-primitive.md#string)* que presenta un valor determinado de fecha como texto en el formato especificado y en una cultura opcional especificada. |
| [DateTimeFormat](er-functions-datetime-datetimeformat.md) | Esta función devuelve un valor *Cadena* que presenta un valor determinado de fecha/hora como texto en el formato especificado y en una cultura opcional especificada. |
| [DateTimeValue](er-functions-datetime-datetimevalue.md) | Esta función devuelve un valor *Fecha y hora* que se convierte de un determinado valor de texto en el formato especificado y en una cultura opcionalmente especificada a un valor de fecha / hora. |
| [DateToDateTime](er-functions-datetime-datetodatetime.md) | Esta función devuelve un valor *Fecha y hora* que se convierte de un determinado valor de datos a un valor de fecha / hora en hora universal coordinada (hora meridiano de Greenwich \[GMT\]). |
| [DateValue](er-functions-datetime-datevalue.md) | Esta función devuelve un valor *[Fecha](er-formula-supported-data-types-primitive.md#date)* que se convierte de un determinado valor de texto en el formato especificado y en una cultura opcionalmente especificada a un valor de fecha. |
| [DayOfYear](er-functions-datetime-dayofyear.md) | Esta función devuelve un valor *[Entero](er-formula-supported-data-types-primitive.md#integer)* que representa el número de días entre el 1 de enero y la fecha especificada. |
| [Días](er-functions-datetime-days.md) | Esta función devuelve un valor *Entero* que representa el número de días entre una fecha especificada y una segunda fecha especificada. |
| [Now](er-functions-datetime-now.md) | Esta función devuelve un valor *Fecha y hora* que representa la fecha y hora actuales del servidor de aplicaciones. |
| [NullDate](er-functions-datetime-nulldate.md) | Esta función devuelve un valor *Fecha* que representa la fecha **nulo** (1 de enero de 1900). |
| [NullDateTime](er-functions-datetime-nulldatetime.md) | Esta función devuelve un valor *Fecha y hora* que representa el valor **nulo** de fecha / hora (1 de enero de 1900) en hora universal coordinada. |
| [SessionNow](er-functions-datetime-sessionnow.md) | Esta función devuelve un valor *Fecha y hora* que representa la fecha y hora actuales de la sesión de la aplicación. |
| [SessionToday](er-functions-datetime-sessiontoday.md) | Esta función devuelve un valor *Fecha* que representa la fecha actual de la sesión de la aplicación. |
| [Hoy](er-functions-datetime-today.md) | Esta función devuelve un valor *Fecha* que representa la fecha actual del servidor de la aplicación. |
| [WeekNum](er-functions-datetime-weeknum.md) | Esta función devuelve un valor *Entero* que representa la semana del año. |

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de los informes electrónicos](general-electronic-reporting.md)

[Diseñador de fórmulas en los informes electrónicos](general-electronic-reporting-formula-designer.md)

[Idioma de fórmulas en los informes electrónicos](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
