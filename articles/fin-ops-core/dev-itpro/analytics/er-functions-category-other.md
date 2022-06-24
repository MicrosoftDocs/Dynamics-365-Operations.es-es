---
title: Lista de funciones ER en la categoría de dominio de empresa específico
description: Este artículo proporciona información sobre las funciones de dominio de empresa específico que son compatibles con los informes electrónicos (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: d9df826dcc0b672977d4d8af1feb985ab9a0ab7d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879960"
---
# <a name="list-of-er-functions-in-the-business-domainspecific-category"></a>Lista de funciones ER en la categoría de dominio de empresa específico

[!include [banner](../includes/banner.md)]

Las funciones específicas de dominio de informes electrónicos (ER) se pueden usar para realizar cálculos y solicitudes de acceso a datos que son específicos para la implementación de Microsoft Dynamics 365 Finance. Este artículo proporciona un resumen de estas funciones.

## <a name="list-of-supported-functions"></a>Lista de funciones permitidas.

| Función| Descripción |
|---------|-------------|
| [CH_Bank_Mod_10](er-functions-other-chbankmode10.md) | Esta función devuelve un valor *Cadena* que representa una referencia de acreedor como una expresión MOD10, basada en los dígitos del número de factura especificado. |
| [CN_GBT_AdditionalDimensionID](er-functions-other-cngbtadditionaldimensionid.md) | Esta función devuelve un valor *Cadena* que representa un solo Id. de dimensión financiera que se toma de una cadena especificada. La cadena especificada presenta todas las dimensiones como una lista de ID separadas por comas. |
| [ConvertCurrency](er-functions-other-convertcurrency.md) | Esta función devuelve un valor *Real* que representa el resultado de convertir el importe monetario especificado de la divisa de origen especificada a la divisa de destino especificada con la configuración de la empresa especificada en la fecha especificada. |
| [CurCredRef](er-functions-other-curcredref.md) | Esta función devuelve un valor *Cadena* que representa una referencia de acreedor basada en los dígitos del número de factura especificado. |
| [FA_Balance](er-functions-other-fabalance.md) | Esta función devuelve un valor *Contenedor (registro)* que consiste en datos para el saldo del activo fijo para el elemento del activo fijo especificado, el código del modelo de valor, el año del informe y la fecha del informe. |
| [FA_Sum](er-functions-other-fasum.md) | Esta función devuelve un valor *Contenedor (registro)* que consiste en datos para las cantidades del activo fijo para el elemento del activo fijo especificado, el código del modelo de valor y un período de fechas. |
| [GetCurrentCompany](er-functions-other-getcurrentcompany.md) | Esta función devuelve un valor *Cadena* que representa el código para la entidad jurídica (empresa) con la que el usuario está registrado actualmente. |
| [ISOCredRef](er-functions-other-isocredref.md) | Esta función devuelve un valor *Cadena* que representa una referencia de acreedor de la Organización Internacional de Normalización (ISO), basada en los dígitos y los símbolos alfabéticos del número de factura especificado. |
| [IsValidCharacterISO7064](er-functions-other-isvalidchariso7064.md) | Esta función devuelve un valor *Booleano* de **TRUE** si la cadena especificada representa un número internacional de cuenta bancaria válido (IBAN). De lo contrario, la expresión devuelve un valor *Booleano* de **FALSE**. |
| [Mod_97](er-functions-other-mod97.md) | Esta función devuelve un valor *Cadena* que representa una referencia de acreedor como una expresión MOD97, basada en los dígitos del número de factura especificado. |
| [NumSeqValue](er-functions-other-numseqvalue.md) | Esta función devuelve un valor *Cadena* que representa el nuevo valor generado de una secuencia numérica, basado en la secuencia numérica especificada, el alcance y el ID de ámbito. El ID de ámbito es igual al código de la compañía que se proporciona según el contexto en el que se ejecuta el formato ER. |
| [RoundAmount](er-functions-other-roundamount.md) | Esta función devuelve un valor *Real* que representa el resultado de redondear la cantidad especificada al número especificado de lugares decimales de acuerdo con la regla de redondeo especificada. |
| [TableName2ID](er-functions-other-tablename2id.md) | Esta función devuelve una representación numérica de la ID de la tabla para el nombre de la tabla especificada como un valor *Entero*. |

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de los informes electrónicos](general-electronic-reporting.md)

[Diseñador de fórmulas en los informes electrónicos](general-electronic-reporting-formula-designer.md)

[Idioma de fórmulas en los informes electrónicos](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]