---
title: Función ORDERBY de ER
description: En este artículo se proporciona información sobre cómo usar la función ORDERBY de informes electrónicos (ER).
author: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 23ace859bf75b2adb6ef8604475519a015486948
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282573"
---
# <a name="orderby-er-function"></a>Función ORDERBY de ER

[!include [banner](../includes/banner.md)]

La función `ORDERBY` devuelve la lista especificada como un valor *Lista de registros* después de que se haya ordenado de acuerdo con los argumentos especificados. Estos argumentos se pueden definir como expresiones.

## <a name="syntax-1"></a><a name="syntax-1"></a>Sintaxis 1

```vb
ORDERBY (list, expression 1[, expression 2, …, expression N])
```

## <a name="syntax-2"></a><a name="syntax-2"></a>Sintaxis 2

```vb
ORDERBY (location, list, expression 1[, expression 2, …, expression N])
```

> [!NOTE]
> Esta sintaxis se admite en Microsoft Dynamics 365 Finance versión 10.0.25 y posteriores.

## <a name="arguments"></a>Argumentos

`location`: *[Cadena](er-formula-supported-data-types-primitive.md#string)*

La ubicación donde se debe ejecutar la clasificación. Las siguientes opciones son válidas:

- "Consulta"
- "InMemory"

`list`: *[Lista de registros](er-formula-supported-data-types-composite.md#record-list)*

La ruta válida de un origen de datos del tipo de datos *Lista de registros*.

`expression 1`: *Campo*

La ruta válida de un campo del origen de datos al que hace referencia el argumento `list` de la función llamada. El campo referenciado debe ser un campo del tipo de datos primitivo. Este argumento es obligatorio.

`expression N`: *Campo*

La ruta válida de un campo del origen de datos al que hace referencia el argumento `list` de la función llamada. El campo referenciado debe ser un campo del tipo de datos primitivo. Estos argumentos adicionales son opcionales.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

La lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

### <a name="syntax-1"></a>Sintaxis 1

La clasificación de datos siempre se realiza en la memoria del servidor de aplicaciones. Para obtener más información, consulte [ejemplo 1](#example-1).

### <a name="syntax-2"></a>Sintaxis 2

### <a name="sorting-in-memory"></a>Clasificación en memoria

Cuando el argumento `location` se especifica como **InMemory**, la clasificación de datos se realiza en la memoria de un servidor de aplicaciones. Para obtener más información, consulte [ejemplo 2](#example-2).

### <a name="sorting-in-database"></a>Clasificación en la base de datos

Cuando el argumento `location` se especifica como **Consulta**, la clasificación de datos se realiza en el nivel de base de datos. En este caso, el argumento `list` debe apuntar a uno de los siguientes orígenes de datos de [informes electrónicos (ER)](general-electronic-reporting.md) que especifique el origen de la aplicación para el que se puede establecer una consulta directa a la base de datos:

- Origen de datos del tipo *Registros de tabla*.
- Relación de un origen de datos del tipo *Registros de tabla*.
- Origen de datos del tipo *Campo calculado*.

Los argumentos `expression 1` y `expression N` deben apuntar a los campos de un origen de datos de ER que especifique los campos relevantes del origen de la aplicación para el que se puede establecer también una consulta directa a la base de datos:

Si no se puede establecer una consulta directa, se produce un [error](er-components-inspections.md#i18) de validación en el diseñador de asignación de modelos ER. El mensaje que recibe indica que la expresión ER que incluye la función `ORDERBY` no se puede ejecutar en runtime.

Para un mejor rendimiento, le recomendamos que utilice la opción **Consulta** opción cuando la ordenación está configurada para fuentes de datos de aplicaciones que pueden contener una gran cantidad de registros (por ejemplo, para tablas de aplicaciones transaccionales).

> [!NOTE]
> La función `ORDEBY` en sí no se puede traducir a una consulta directa a la base de datos. Por lo tanto, una fuente de datos de ER que contiene esta función no se puede consultar. Tampoco se puede utilizar en el ámbito de las funciones de ER, como [FILTER](er-functions-list-filter.md) y [ALLITEMSQUERY](er-functions-list-allitemsquery.md), donde solo se pueden utilizar fuentes de datos consultables.

Para más detalles, consulte el [ejemplo 3](#example-3) y [ejemplo 4](#example-4).

### <a name="comparability"></a>Comparabilidad

Debido a que el motor de la base de datos SQL y el servidor de aplicaciones de Finanzas pueden usar un valor de clasificación diferente para un solo carácter, el resultado de clasificación de la misma lista de registros puede diferir cuando un campo [Cadena](er-formula-supported-data-types-primitive.md#string) se utiliza para ordenar. Para obtener más información, consulte [ejemplo 5](#example-5).

## <a name="example-1-in-memory-default-execution"></a><a name="example-1"></a>Ejemplo 1: ejecución predeterminada en memoria

Si especifica el origen de datos **DS** del tipo *Campo calculado* y contiene la expresión `SPLIT ("C|B|A", "|")`, la expresión `FIRST( ORDERBY( DS, DS. Value)).Value` devuelve el valor de texto **"A"**.

## <a name="example-2-in-memory-explicit-execution"></a><a name="example-2"></a>Ejemplo 2: ejecución explícita en memoria

Cuando **Proveedor** se configura como origen de datos de ER del tipo *Registros de tabla* que hace referencia a la tabla **VendTable**, la expresión `ORDERBY (Vendor, Vendor.'name()')` y la expresión `ORDERBY ("InMemory", Vendor, Vendor.'name()')` devuelven una lista de proveedores que se clasifica por nombre en orden ascendente.

Cuando se configura la expresión `ORDERBY ("Query", Vendor, Vendor.'name()')` en el diseñador de mapeo de modelos ER, ocurre un [error](er-components-inspections.md#i8) de validación en tiempo de diseño, porque la ruta `Vendor.'name()'` hace referencia a un método de aplicación que tiene una lógica que no se puede traducir a una consulta de base de datos directa.

## <a name="example-3-database-query"></a><a name="example-3"></a>Ejemplo 3: consulta de base de datos

Si **TaxTransaction** se configura como una fuente de datos ER del tipo *Registros de tabla* que se refiere a la tabla **TaxTrans**, la expresión `ORDERBY ("Query", TaxTransaction, TaxTransaction.TaxCode)` ordena los registros en el nivel de la base de datos de la aplicación y devuelve una lista de transacciones de impuestos que se ordena por código de impuestos en orden ascendente.

## <a name="example-4-queryable-data-sources"></a><a name="example-4"></a>Ejemplo 4: fuentes de datos consultables

Si **TaxTransaction** se configura como una fuente de datos ER del tipo *Registros de tabla* que se refiere a la tabla **TaxTrans**, la fuente de datos de ER **TaxTransactionFiltered** se puede configurar para que contenga la expresión `FILTER(TaxTransaction, TaxCode="VAT19")`, que obtendrá las transacciones para un código de impuestos específico. Porque la fuente de datos de ER configurada **TaxTransactionFiltered** es consultable, la expresión `ORDERBY ("Query", TaxTransactionFiltered, TaxTransactionFiltered.TransDate)` se puede configurar para devolver la lista de transacciones de impuestos filtradas que se ordena por fecha de transacción en orden ascendente.

Si configura **TaxTransactionOrdered** como una fuente de datos ER del tipo *campo calculado* que contiene la expresión `ORDERBY ("Query", TaxTransaction, TaxTransaction.TransDate)` y una fuente de datos ER del tipo *campo calculado* que contiene la expresión `FILTER(TaxTransactionOrdered, TaxCode="VAT19")`, se produce un [error](er-components-inspections.md#i18) de validación en tiempo de diseño en el diseñador de asignación de modelos de ER. Este error ocurre porque el primer argumento de [FILTER](er-functions-list-filter.md#usage-notes) debe hacer referencia a una fuente de datos de ER consultable, pero la fuente de datos **TaxTransactionOrdered** que contiene la función `ORDERBY` no es consultable.

## <a name="example-5-comparability"></a><a name="example-5"></a>Ejemplo 5: Comparabilidad

### <a name="prerequisites"></a>Requisitos previos

1. Introduzca el origen de datos **DS1** de tipo *Campo calculado* que contiene la expresión `SPLIT ("D1|_D2|D3", "|")`.
2. Abra la página **[Valores de dimensión financiera](../../../finance/general-ledger/financial-dimensions.md)** y seleccione la dimensión **CostCenter**.
3. Introduzca los siguientes valores de dimensión: **D1**, **\_D2** y **D3**.

### <a name="sorting-in-memory"></a>Clasificación en memoria

1. Configure el origen de datos **DS2** de tipo *Campo calculado* que contiene la expresión `ORDERBY("InMemory", DS1, DS1.Value)`.
2. Note que la expresión `FIRST(DS2).Value` devuelve el valor del texto **"D1"**, la expresion `INDEX(DS2, COUNT(DS2)).Value` devuelve el valor del texto **"\_D2"** y la expresión `STRINGJOIN(DS2, DS2.Value, "|")` devuelve el valor del texto **"D1\|D3\|\_D2"**.

### <a name="sorting-in-database"></a>Clasificación en la base de datos

1. Introduzca la fuente de datos **DS3** del tipo *Registros de tabla* que hace referencia a la entidad **FinancialDimensionValueEntity**.
2. Configure el origen de datos **DS4** de tipo *Campo calculado* que contiene la expresión `FILTER(DS3, DS3.FinancialDimension="CostCenter")`.
3. Configure el origen de datos **DS5** de tipo *Campo calculado* que contiene la expresión `ORDERBY(DS4, DS4.DimensionValue)`.
4. Note que la expresión `FIRST(DS5).Value` devuelve el valor del texto **"\_D2"**, la expresion `INDEX(DS5, COUNT(DS5)).Value` devuelve el valor del texto **"D3"** y la expresión `STRINGJOIN(DS5, DS5.Value, "|")` devuelve el valor del texto **"\_D2\|D1\|D3"**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
