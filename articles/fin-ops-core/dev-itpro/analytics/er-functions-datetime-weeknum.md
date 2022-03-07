---
title: Función ER WEEKNUM
description: En este tema se proporciona información sobre cómo usar la función WEEKNUM de informes electrónicos (ER).
author: NickSelin
ms.date: 12/03/2021
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: fe36d4142b6e4922e2cbca09bb0ca9f68f6680a0
ms.sourcegitcommit: c85eac17fbfbd311288b50664f9e2bae101c1fe6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2021
ms.locfileid: "7891348"
---
# <a name="weeknum-er-function"></a>Función ER WEEKNUM

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

La función `WEEKNUM` devuelve un valor *[Entero](er-formula-supported-data-types-primitive.md#integer)* que representa la semana del año que incluye una *[fecha](er-formula-supported-data-types-primitive.md#date)* específica. El cálculo se basa en reglas dependientes de la cultura que definen una semana y el primer día de la misma.

## <a name="syntax"></a>Sintaxis

```vb
WEEKNUM (date, culture) as Integer
```

## <a name=""></a><a name="arguments">Argumentos</a>

`date`: *Fecha*

Un valor de fecha que representa la fecha a usar para calcular la semana del año.

`culture`: *[cadena](er-formula-supported-data-types-primitive.md#string)*

La cultura a utilizar para el cálculo. Puede utilizar códigos de cultura compatibles con [normas](/dotnet/api/system.globalization.cultureinfo.getcultures?view=net-5.0) de .NET.

## <a name="return-values"></a>Valores de retorno

*Entero*

El valor numérico resultante.

## <a name="usage-notes"></a>Notas de uso

La semana del año se calcula en base al estándar [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html), si este estándar ha sido adoptado por un país o región para el que se proporciona la configuración regional en tiempo de ejecución. De lo contrario, el cálculo se basa en estándares nacionales específicos del país o región.

Si se proporciona un código de [cultura](#arguments) incompatible como un argumento de la función `WEEKNUM` en tiempo de ejecución, se lanza una excepción. Si la cadena en blanco se proporciona como un código de cultura, se utiliza el calendario neutral del país inglés para calcular el número de la semana.

## <a name="examples"></a>Ejemplo

`WEEKNUM (DATEVALUE ("01-01-2020", "de"))` devuelve **1**.

`WEEKNUM (DATEVALUE ("01-01-2021", "de"))` devuelve **53**.

`WEEKNUM (DATEVALUE ("01-01-2022", "de"))` devuelve **52**.

`WEEKNUM (DATEVALUE ("01-01-2022", "ar"))` devuelve **21**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de fecha y de tiempo](er-functions-category-datetime.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
