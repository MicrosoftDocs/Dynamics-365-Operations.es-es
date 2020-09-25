---
title: Función ER NULLDATE
description: Este tema proporciona información general sobre cómo usar la función NULLDATE de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: edf43cc19636f51387504a7d9da73d757d96e558
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744296"
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
