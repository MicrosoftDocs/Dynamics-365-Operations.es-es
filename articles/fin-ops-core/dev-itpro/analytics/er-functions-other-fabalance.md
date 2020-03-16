---
title: Función FA_BALANCE de ER
description: Este tema proporciona información general sobre cómo usar la función FA_BALANCE de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 76a087157ae53e2c571654ade7383d7bd7a005c3
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041455"
---
# <a name="FA_BALANCE">Función FA_BALANCE de ER</a>

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
