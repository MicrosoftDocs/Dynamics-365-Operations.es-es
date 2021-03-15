---
title: Lista de funciones ER en la categoría de conversión de tipo
description: Este tema proporciona información sobre las funciones de conversión que son compatibles con los informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: eb2d4ab3434a563e907f6540809888cd3f671c1a
ms.sourcegitcommit: fcc4596eeadac5dfe9a3242afa49b9b1c0c96575
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "4740817"
---
# <a name="list-of-er-functions-in-the-type-conversion-category"></a>Lista de funciones ER en la categoría de conversión de tipo

[!include [banner](../includes/banner.md)]

Las funciones de conversión de tipo de informe electrónico (ER) se pueden usar para convertir valores entre tipos. Este tema proporciona un resumen de estas funciones.

## <a name="type-conversion-functions"></a>Funciones de conversión de tipos

| Función | Descripción |
|----------|-------------|
| [Int64Value](er-functions-conversion-int64value.md)   | Esta función devuelve un valor *Int64* que representa la cadena especificada. |
| [IntValue](er-functions-conversion-intvalue.md)       | Esta función devuelve un valor *Int* que representa la cadena especificada. |
| [NumberValue](er-functions-conversion-numbervalue.md) | Esta función devuelve un valor *Real* que se convierte del valor *Cadena* especificado. Durante la conversión, se consideran los separadores de agrupación decimal y de dígitos especificados. |
| [Valor](er-functions-conversion-value.md)             | Esta función devuelve un valor *Real* que se convierte del valor *Cadena* especificado. |

## <a name="type-conversion-functions-in-the-container-category"></a>Funciones de conversión de tipo en la categoría de contenedor

La siguiente tabla describe las funciones de conversión de tipos en la categoría de [contenedor](er-functions-category-container.md).

| Función | Descripción |
|----------|-------------|
| [Base64StringToContainer](er-functions-container-base64stringtocontainer.md) | Esta función convierte la entrada especificada del tipo *Cadena* a un elemento de datos del tipo *Contenedor*. |

## <a name="type-conversion-functions-in-the-date-and-time-category"></a>Funciones de conversión de tipo en la categoría hora y fecha

La siguiente tabla describe las funciones de conversión de tipos en la [categoría de fecha y hora](er-functions-category-datetime.md).

| Función | Descripción |
|----------|-------------|
| [DateTimeValue](er-functions-datetime-datetimevalue.md)   | Esta función devuelve un valor *Fecha y hora* que se convierte de un determinado valor *Cadena* en el formato especificado y en una cultura opcionalmente especificada a un valor de fecha / hora. |
| [DateToDateTime](er-functions-datetime-datetodatetime.md) | Esta función devuelve un valor *Fecha y hora* que se convierte de un determinado valor *Fecha* a un valor de fecha / hora en hora universal coordinada (hora meridiano de Greenwich \[GMT \]). |
| [DateValue](er-functions-datetime-datevalue.md)           | Esta función devuelve un valor *Fecha* que se convierte de un determinado valor *Cadena* en el formato especificado y en una cultura opcionalmente especificada a un valor de fecha / hora. |

## <a name="type-conversion-functions-in-the-list-category"></a>Funciones de conversión de tipo en la categoría lista

La siguiente tabla describe las funciones de conversión de tipos en la [categoría lista](er-functions-category-list.md).

| Función | Descripción |
|----------|-------------|
| [Lista](er-functions-list-list.md)                 | Esta función devuelve un valor *Lista de registros* como una lista nueva creada a partir de los argumentos especificados del tipo *Contenedor (registro)*. |
| [ListOfFields](er-functions-list-listoffields.md) | Esta función devuelve un valor *Lista de registros* que se crea en función de la estructura del argumento determinado del tipo *Enumeración* o *Contenedor (registro)*. |
| [Dividir](er-functions-list-split.md)               | Esta función divide el valor *Cadena* especificado en subcadenas y devuelve el resultado como un valor *Lista de registros* nuevo. |
| [StringJoin](er-functions-list-stringjoin.md)     | Esta función devuelve un valor *Cadena* que consta de valores concatenados del campo especificado del valor *Lista de registros* especificado. Los valores pueden estar separados por el delimitador especificado. |

## <a name="type-conversion-functions-in-the-text-category"></a>Funciones de conversión de tipo en la categoría texto

La siguiente tabla describe las funciones de conversión de tipos en la [categoría texto](er-functions-category-text.md).

| Función | Descripción |
|----------|-------------|
| [Char](er-functions-text-char.md)                 | Esta función devuelve un valor *String* que representa un solo carácter al que hace referencia el número Unicode especificado. |
| [GuidValue](er-functions-text-guidvalue.md)       | Esta función convierte la entrada especificada del tipo *Cadena* a un elemento de datos del tipo *GUID*. |
| [NumberFormat](er-functions-text-numberformat.md) | Esta función devuelve un valor *Cadena* que representa el número especificado en el formato especificado y en una cultura opcional especificada. |
| [QrCode](er-functions-text-qrcode.md)             | Esta función devuelve un valor *Contenedor* que presenta la imagen del código de Respuesta rápida (código QR) para la cadena especificada en formato binario. |
| [Texto](er-functions-text-text.md)                 | Esta función devuelve un valor *Cadena* que representa al número especificado después de que se haya convertido en una cadena de texto que se formatea según la configuración regional del servidor de la instancia actual de la aplicación. |

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de los informes electrónicos](general-electronic-reporting.md)

[Diseñador de fórmulas en los informes electrónicos](general-electronic-reporting-formula-designer.md)

[Idioma de fórmulas en los informes electrónicos](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]