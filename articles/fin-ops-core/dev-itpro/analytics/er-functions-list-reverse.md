---
title: Función REVERSE de ER
description: Este tema proporciona información general sobre cómo usar la función REVERSE de informes electrónicos (ER).
author: NickSelin
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
ms.openlocfilehash: 746a736c8797c1c1c5bd71d7d803be4212984595
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755213"
---
# <a name="reverse-er-function"></a>Función REVERSE de ER

[!include [banner](../includes/banner.md)]

La función `REVERSE` devuelve la lista especificada como un valor *Lista de registros* en orden inverso.

## <a name="syntax"></a>Sintaxis

```vb
REVERSE (list)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

La ruta válida de un origen de datos del tipo de datos *Lista de registros*.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

La lista de registros resultante.

## <a name="example-1"></a>Ejemplo 1

Si especifica el origen de datos **DS** del tipo *Campo calculado* y contiene la expresión `SPLIT ("C|B|A", "|")`, la expresión `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` devuelve el valor de texto **"C"**.

## <a name="example-2"></a>Ejemplo 2

Cuando **Proveedor** se configura como origen de datos de ER que hace referencia a la tabla VendTable, la expresión `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` devuelva la lista de proveedores que se clasifica por nombre en orden descendente.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]