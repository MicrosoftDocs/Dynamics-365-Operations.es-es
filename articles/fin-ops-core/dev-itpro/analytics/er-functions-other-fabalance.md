---
title: Función FA_BALANCE de ER
description: En este artículo se proporciona información sobre cómo usar la función FA_BALANCE de informes electrónicos (ER).
author: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: f9bb52643b60fd1b9423d798c08d731565c70f81
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285257"
---
# <a name="fa_balance-er-function"></a>Función FA_BALANCE de ER

[!include [banner](../includes/banner.md)]

La función `FA_BALANCE` devuelve un valor *Contenedor (registro)* que consiste en datos para el saldo del activo fijo para el elemento del activo fijo especificado, el código del modelo de valor, el año del informe y la fecha del informe.

## <a name="syntax"></a>Sintaxis

```vb
FA_BALANCE (fixed asset code, value model code, reporting year, reporting date)
```

## <a name="arguments"></a>Argumentos

`fixed asset code`: *Cadena*

Un valor *Cadena* que representa el código de un elemento de activo fijo para el que se calcula el saldo.

`value model code`: *Cadena*

Un valor *Cadena* que representa el código de un modelo de valor para el que se calcula el saldo.

`reporting year`: *Valor de enumeración*

Un valor de enumeración de la enumeración de aplicaciones **AssetYear** que define un período para el cálculo del saldo.

`reporting date`: *Fecha*

Un valor *Fecha* que define una fecha para el cálculo del saldo.

## <a name="return-values"></a>Valores de retorno

*Contenedor (registro)*

El valor de registro resultante.

## <a name="example"></a>Ejemplo

`FA_ BALANCE ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())` devuelve el contenedor preparado de los datos de los saldos del activo fijo **COMP-000001** que tiene el modelo de valor **Actual** en la fecha de la sesión actual de la aplicación.

## <a name="additional-resources"></a>Recursos adicionales

[Otras funciones (específicas de dominio empresarial)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
