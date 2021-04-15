---
title: Función NUMBERVALUE ER
description: En este tema se proporciona información sobre cómo usar la función NUMBERVALUE de informes electrónicos (ER).
author: NickSelin
ms.date: 12/05/2019
ms.topic: article
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
ms.openlocfilehash: 84d7f17f37a83547522cf09047b72100f6f5b859
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755357"
---
# <a name="numbervalue-er-function"></a>Función NUMBERVALUE ER

[!include [banner](../includes/banner.md)]

La función `NUMBERVALUE` devuelve un valor *Real* que se convierte del valor *Cadena* especificado. Durante la conversión, se consideran los separadores de agrupación decimal y de dígitos especificados.

## <a name="syntax"></a>Sintaxis

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadena*

Un valor de texto que debe convertirse en un número *Real*.

`decimal separator`: Cadena

Un separador decimal. Se utiliza para separar las partes enteras y fraccionarias de un número decimal.

`digit grouping separator`: *Cadena*

Un separador de agrupación de dígitos. Se usa como el separador de miles.

## <a name="return-values"></a>Valores de retorno

*Real*

El valor numérico resultante.

## <a name="example"></a>Ejemplo

`NUMBERVALUE( "1 234,56", ",", " ")` devuelve **1234,56**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de conversión de tipos](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]