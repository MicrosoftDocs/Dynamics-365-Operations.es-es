---
title: Función FILTER de ER
description: Este tema proporciona información general sobre cómo usar la función FILTER de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: d281fe710381b0ecb075a0d9281d46bd6edf987d
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745306"
---
# <a name="filter-er-function"></a>Función FILTER de ER

[!include [banner](../includes/banner.md)]

La función `FILTER` devuelve la lista especificada como un valor *Lista de registros* después de que se haya cambiado la consulta para que filtre por la condición especificada.

## <a name="syntax"></a>Sintaxis

```vb
FILTER (list, condition)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

La ruta válida de un origen de datos del tipo de datos *Lista de registros*.

`condition`: *Booleano*

Una expresión condicional válida que se utiliza para filtrar registros de la lista especificada.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

La lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

Esta función difiere de la función [DONDE](er-functions-list-where.md), ya que la condición especificada se aplica a cualquier origen de datos de Informes electrónicos (ER) del tipo *Registros de la tabla* a nivel de la base de datos. La lista y la condición se pueden definir mediante tablas y relaciones.

Si uno o ambos argumentos configurados para esta función (`list` y `condition`) no permite que esta solicitud se traduzca para la llamada directa de SQL, se produce una excepción en tiempo de diseño. Esta excepción informa al usuario que `list` o `condition` no se pueden usar para consultar la base de datos.

## <a name="example-1"></a>Ejemplo 1

Si **Proveedor** se configura como origen de datos de ER que hace referencia a la tabla VendTable, la expresión `FILTER (Vendors, Vendors.VendGroup = "40")` devuelve una lista solo de proveedores que pertenece al grupo de proveedores 40.

## <a name="example-2"></a>Ejemplo 2

Si **Proveedor** se configura como origen de datos de ER que hace referencia a la tabla VendTable, y **si parmVendorBankGroup** que está configurado como un origen de datos de ER que devuelve un valor del tipo de datos *Cadena*, la expresión `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` devuelve una lista solo de cuentas de proveedores que pertenecen a un grupo bancario específico.

## <a name="example-3"></a>Ejemplo 3

Especifica un origen de datos **DS** del tipo *Campo calculado* y contiene la expresión `SPLIT ("A,B,C", ",")`. Luego especifica otra expresión, `FILTER( DS, DS.Value = "B")`. Cuando intenta guardar esta expresión en el diseñador de fórmulas de ER, se produce la siguiente excepción: "Error de validación: la expresión de lista de la función FILTER no es consultable".

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)
