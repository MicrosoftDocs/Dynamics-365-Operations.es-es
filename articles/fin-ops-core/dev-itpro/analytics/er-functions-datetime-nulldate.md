---
title: Función ER NULLDATE
description: En este artículo se proporciona información sobre cómo usar la función NULLDATE de informes electrónicos (ER).
author: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 276ad99303a4e88ecb1c83e9518e06bfd7afaa45
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272664"
---
# <a name="nulldate-er-function"></a>Función ER NULLDATE

[!include [banner](../includes/banner.md)]

La función `NULLDATE` devuelve un valor *Fecha* que representa la fecha **nula** (1 de enero de 1900).

## <a name="syntax"></a>Sintaxis

```vb
NULLDATE () as 
```

## <a name="return-values"></a>Valores de retorno

*Fecha*

El valor de fecha resultante.

## <a name="example-1"></a>Ejemplo 1

`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` devuelve la fecha **nulo**, 1 de enero de 1900, como **"1900-01-01"**, según el formato personalizado especificado.

## <a name="example-2"></a>Ejemplo 2

La expresión `IF( Invoice.DocumentDate = NULLDATE(), true, false)` devuelve **Cierto** cuando el valor del campo **Fecha del documento** es igual a la fecha **nulo**. En este ejemplo, **Factura** es un origen de datos de informe electrónico (ER) del tipo **Registros Finance/Tabla** y hace referencia a la tabla CustInvoiceJour.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de fecha y de tiempo](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
