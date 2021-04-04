---
title: Función WHERE de ER
description: Este tema proporciona información general sobre cómo usar la función WHERE de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: ca218f87eb1f9235ab475809fbbdfecf3fe0c7fb
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566051"
---
# <a name="where-er-function"></a>Función WHERE de ER

[!include [banner](../includes/banner.md)]

La función `WHERE` devuelve la lista especificada como un valor *Lista de registros* después de que se haya filtrado de acuerdo con la condición especificada.

## <a name="syntax"></a>Sintaxis

```vb
WHERE (list, condition)
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

Esta función difiere de la función [FILTER](er-functions-list-filter.md), ya que la condición especificada se aplica a cualquier origen de datos de Informes electrónicos (ER) del tipo *Lista de registros* que esté presente en la memoria.

Si los argumentos configurados para esta función (`list` y `condition`) permiten que esta solicitud se traduzca para la llamada directa de SQL, aparecerá un mensaje de advertencia en tiempo de diseño. Este mensaje informa al usuario que el rendimiento podría mejorar si la función [FILTER](er-functions-list-filter.md) se usa en lugar de `WHERE`.

## <a name="example-1"></a>Ejemplo 1

Si **Proveedor** se configura como origen de datos de ER que hace referencia a la tabla VendTable, la expresión `WHERE (Vendors, Vendors.VendGroup = "40")` devuelve una lista solo de proveedores que pertenece al grupo de proveedores 40.

## <a name="example-2"></a>Ejemplo 2

Si especifica el origen de datos **DS** para el tipo *Campo calculado* y este contiene la expresión `SPLIT ("A|B|C", "|")`, la expresión `WHERE( DS, DS.Value = "B")` devuelve una lista de solo un registro que contiene el texto **"B"** en el campo **Valor**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]