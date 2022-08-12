---
title: Función DATETODATETIME ER
description: En este artículo se proporciona información sobre cómo usar la función DATETODATETIME de informes electrónicos (ER).
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 519932854dfd3e872433b0fb304e683c57cea1cb
ms.sourcegitcommit: 3289478a05040910f356baf1995ce0523d347368
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2022
ms.locfileid: "9108509"
---
# <a name="datetodatetime-er-function"></a>Función DATETODATETIME ER

[!include [banner](../includes/banner.md)]

La función `DATETODATETIME` devuelve un valor *Fecha y hora* que se convierte de un determinado valor de datos a un valor de fecha / hora en hora universal coordinada (hora meridiano de Greenwich \[GMT\]).

## <a name="syntax"></a>Sintaxis

```vb
DATETODATETIME (date)
```

## <a name="arguments"></a>Argumentos

`date`: *Fecha*

Un valor de fecha / hora que representa la fecha a convertir.

## <a name="return-values"></a>Valores de retorno

*DateTime*

El valor de fecha/hora resultante.

## <a name="example-1"></a>Ejemplo 1

`DATETODATETIME (CompInfo. 'getCurrentDate()')` devuelve la fecha de la sesión actual de Microsoft Dynamics 365 Finance, 24 de diciembre de 2015, como **12/24 / 2015 12:00:00 AM**. En este ejemplo, **CompInfo** es un origen de datos de informe electrónico (ER) del tipo **finanzas y operaciones/Tabla** y hace referencia a la tabla CompanyInfo.

## <a name="example-2"></a>Ejemplo 2

`DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` devuelve el valor de fecha / hora **11/12 / 2019 12:00:00 AM**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de fecha y de tiempo](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
