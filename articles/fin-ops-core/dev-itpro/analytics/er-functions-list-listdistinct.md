---
title: Función de ER LISTDISTINCT
description: En este tema se proporciona información sobre cómo usar la función LISTDISTINCT de informes electrónicos (ER).
author: NickSelin
ms.date: 7/30/2020
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 7cc51695d261a63521ae88e2a9362b6f30b9618ed89300bcaeb606b050c81350
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6735583"
---
# <a name="listdistinct-er-function"></a>Función de ER LISTDISTINCT

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

La función `LISTDISTINCT` calcula la expresión especificada como un selector para cada registro de la lista especificada. Devuelve un nuevo valor de *Lista de registros* que contiene un solo registro para cada valor único del selector.

## <a name="syntax"></a>Sintaxis

```
LISTDISTINCT (list, selector)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

La ruta válida de un origen de datos del tipo de datos *Lista de registros*.

`selector`: *Tipo de datos primitivo*

Una expresión válida que se usa para calcular un valor de selector para cada registro de la lista especificada.

Se admiten los siguientes tipos de datos para este parámetro:

- Booleano
- Fecha
- Fecha y hora
- GUID
- Entero
- Int64
- Real
- Cadena

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

La lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

La estructura de la lista que se crea coincide con la estructura de la lista especificada.

El mismo valor de selector se puede calcular para varios registros en la lista especificada. En este caso, los valores de campo del registro correspondiente en la lista creada son iguales a los valores del primer registro de la lista especificada para el que se calcula el valor del selector.

La ejecución de esta función se realiza en cualquier origen de datos de [Informes electrónicos (ER)](general-electronic-reporting.md) del tipo *Lista de registros* que está presente en la memoria.

El origen de datos **GROUPBY** también se puede utilizar para generar la lista de registros para la que se calcular el selector que tiene valores distintos. Sin embargo, desde una perspectiva de rendimiento y consumo de memoria, es mejor utilizar la función `LISTDISTINCT` que el origen de datos **GROUPBY**, ya que la ejecución de la función se realiza en memoria.

## <a name="example"></a>Ejemplo

El siguiente ejemplo muestra cómo puede obtener la lista de números de cuenta de cliente únicos para los que se ha emitido al menos una factura de venta o factura de proyecto durante un período específico.

1. Especifique el origen de datos **SalesInvoice** de tipo `Record list` que hace referencia a la tabla de aplicación **CustInvoiceJour** y filtra las facturas de venta para períodos específicos.

    El campo `InvoiceAccount` de este origen de datos devuelve el número de cuenta de un cliente facturado.

2. Especifique el origen de datos **ProjectInvoice** de tipo `Record list` que hace referencia a la tabla de aplicación **ProjInvoiceJour** y filtra las facturas de proyecto para períodos específicos.

    El campo `InvoiceAccount` de este origen de datos devuelve el número de cuenta de un cliente facturado.

3. Configure el origen de datos **AllInvoices** de tipo `Calculated field` que contiene la expression `LISTJOIN(SalesInvoice, ProjectInvoice)`.

    Este origen de datos devuelve la lista combinada de facturas de ventas y facturas de proyectos.

4. Configure el origen de datos **InvoicedCustomer** de tipo `Record list` que contiene la expression `LISTDISTINCT(AllInvoices, AllInvoices.InvoiceAccount)`.

    Este origen de datos devuelve una nueva lista que contiene un solo registro para cada cliente único que se ha facturado durante el período definido. El campo `InvoiceAccount` de esta lista contiene un número de cuenta de cliente.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]