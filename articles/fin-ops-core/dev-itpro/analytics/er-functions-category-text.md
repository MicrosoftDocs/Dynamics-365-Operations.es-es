---
title: Lista de funciones ER de la categoría de texto.
description: Este artículo proporciona información sobre las funciones de texto que son compatibles con los informes electrónicos (ER).
author: NickSelin
ms.date: 02/28/2022
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
ms.openlocfilehash: 502a68d51705114adc096a1cd2217210f4e925bb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885554"
---
# <a name="list-of-er-functions-of-the-text-category"></a>Lista de funciones ER de la categoría de texto.

[!include [banner](../includes/banner.md)]

Las funciones de texto de informes electrónicos (ER) se pueden utilizar para realizar operaciones en las fuentes de datos del tipo de datos *Cadena*. Este artículo proporciona un resumen de estas funciones.

## <a name="list-of-supported-functions"></a>Lista de funciones permitidas.

| Función | Descripción |
|----------|-------------|
| [Char](er-functions-text-char.md) | Esta función devuelve un valor *String* que presenta un solo carácter al que hace referencia el número Unicode especificado. |
| [Concatenar](er-functions-text-concatenate.md) | Esta función devuelve todas las cadenas de texto especificadas como un valor *Cadena* después de que se hayan unido en una cadena. |
| [Formato](er-functions-text-format.md) | Esta función devuelve la cadena especificada un valor *Cadena* tras haber sido formateado sustituyendo cualquier aparición de **%N** con el argumento *N*. |
| [GetEnumValueByName](er-functions-text-getenumvaluebyname.md) | Esta función busca un valor específico *Enum* en el origen de datos de enumeración especificado utilizando el nombre de enumeración que se especifica como valor *Cadena*. Si el valor *Enum* se encuentra, la función lo devuelve. |
| [GetLabelText](er-functions-text-getlabeltext.md) | Esta función busca una etiqueta específica para devolver un valor de *[cadena](er-formula-supported-data-types-primitive.md#string)* que representa la traducción de la etiqueta especificada en el idioma especificado. |
| [GuidValue](er-functions-text-guidvalue.md) | Esta función convierte la entrada especificada del tipo *Cadena* a un elemento de datos del tipo *GUID*. |
| [JsonValue](er-functions-text-jsonvalue.md) | Esta función analiza los datos en formato JavaScript Object Notation (JSON) a los que se accede por la ruta especificada y extrae un valor scalar que se basa en el Id. especificado. Luego devuelve el valor escalar extraído como valor *Cadena*. |
| [Izquierdo](er-functions-text-left.md) | Esta función devuelve un valor *Cadena* que presenta el número especificado de caracteres desde el inicio de la cadena especificada. |
| [Len](er-functions-text-len.md) | Esta función devuelve un valor *Entero* que presenta el número de caracteres en la cadena especificada. |
| [Lower](er-functions-text-lower.md) | Esta función devuelve la cadena de texto especificada como un valor *Cadena* después de que se haya convertido a letras minúsculas. |
| [Mid](er-functions-text-mid.md) | Esta función devuelve un valor *[Cadena](er-formula-supported-data-types-primitive.md#string)* que presenta el número especificado de caracteres de la cadena especificada, empezando en la posición especificada. |
| [NewGUID](er-functions-text-newguid.md) | Esta función devuelve un valor de *[ GUID](er-formula-supported-data-types-primitive.md#guid)* generado recientemente. |
| [NumberFormat](er-functions-text-numberformat.md) | Esta función devuelve un valor *Cadena* que presenta el número especificado en el formato especificado y en una cultura opcional especificada. |
| [NumeralsToText](er-functions-text-numeralstotext.md) | Esta función devuelve el número especificado como un valor *Cadena* después de que se haya deletreado (es decir, convertido a cadenas de texto) en el idioma especificado. |
| [PadLeft](er-functions-text-padleft.md) | Esta función devuelve un valor *Cadena* del largo especificado, en el que el comienzo de la cadena especificada cuenta con uno o más casos de los caracteres especificados. |
| [QrCode](er-functions-text-qrcode.md) | Esta función devuelve un valor *Contenedor* que presenta la imagen del código de Respuesta rápida (código QR) para la cadena especificada en formato binario. |
| [Reemplazar](er-functions-text-replace.md) | Esta función devuelve la cadena de texto especificada como un valor *Cadena* después de que todo o parte de él haya sido reemplazado por otra cadena. |
| [Derecho](er-functions-text-right.md) | Esta función devuelve un valor *Cadena* que presenta el número especificado de caracteres desde el final de la cadena especificada. |
| [Texto](er-functions-text-text.md) | Esta función devuelve el número especificado como un valor *Cadena* después de que se haya convertido en una cadena de texto que se formatea según la configuración regional del servidor de la instancia actual de la aplicación. |
| [Traducir](er-functions-text-translate.md) | Esta función devuelve un valor *Cadena* que contiene el resultado del reemplazo de caracteres del texto especificado en caracteres de otro conjunto proporcionado de caracteres. |
| [Trim](er-functions-text-trim.md) | Esta función devuelve la cadena de texto especificada como un valor *Cadena* después de que los caracteres de tabulación, retorno de carro, salto de línea y salto de página hayan sido reemplazados por un solo carácter de espacio, después de que se hayan truncado los espacios iniciales y finales, y después de que se hayan eliminado varios espacios entre palabras. |
| [Upper](er-functions-text-upper.md) | Esta función devuelve la cadena de texto especificada como un valor *Cadena* después de que se haya convertido a letras mayúsculas. |

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de los informes electrónicos](general-electronic-reporting.md)

[Diseñador de fórmulas en los informes electrónicos](general-electronic-reporting-formula-designer.md)

[Idioma de fórmulas en los informes electrónicos](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
