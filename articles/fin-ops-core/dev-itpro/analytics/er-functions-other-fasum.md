---
title: Función FA_SUM de ER
description: Este tema proporciona información general sobre cómo usar la función FA_SUM de informes electrónicos (ER).
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: d6f380e384e591e7417cfa40c73f9be6575fb0f6
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744304"
---
# <a name="fa_sum-er-function"></a>Función FA_SUM de ER

[!include [banner](../includes/banner.md)]

La función `FA_SUM` devuelve un valor *Contenedor (registro)* que consiste en datos para las cantidades del activo fijo para el elemento del activo fijo especificado, el código del modelo de valor y un período de fechas.

## <a name="syntax"></a>Sintaxis

```vb
FA_SUM (fixed asset code, value model code, start date, end date)
```

## <a name="arguments"></a>Argumentos

`fixed asset code`: *Cadena*

Un valor *Cadena* que representa el código de un elemento de activo fijo para el que se calcula el saldo.

`value model code`: *Cadena*

Un valor *Cadena* que representa el código de un modelo de valor para el que se calcula el saldo.

`start date`: *Fecha*

Un valor *Fecha* que representa la fecha de inicio de un período para el que se calculan los importes de los activos fijos.

`end date`: *Fecha*

Un valor *Fecha* que representa la fecha final de un período para el que se calculan los importes de los activos fijos.

## <a name="return-values"></a>Valores de retorno

*Contenedor (registro)*

El valor de registro resultante.

## <a name="example"></a>Ejemplo

`FA_SUM ("COMP-000001", "Current", Date1, Date2)` devuelve el contenedor de datos para activos fijos **COMP-000001** que se ha preparado para el modelo de valor **Actual** y por un período desde **Fecha1** a **Fecha2**.

## <a name="additional-resources"></a>Recursos adicionales

[Otras funciones (específicas de dominio empresarial)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]