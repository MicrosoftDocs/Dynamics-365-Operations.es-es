---
title: Función ORDERBY de ER
description: En este tema se proporciona información sobre cómo usar la función ORDERBY de informes electrónicos (ER).
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
ms.openlocfilehash: 5a995713a795b3f24a4fcfadcc4be596e932a22c
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564175"
---
# <a name="orderby-er-function"></a>Función ORDERBY de ER

[!include [banner](../includes/banner.md)]

La función `ORDERBY` devuelve la lista especificada como un valor *Lista de registros* después de que se haya ordenado de acuerdo con los argumentos especificados. Estos argumentos se pueden definir como expresiones.

## <a name="syntax"></a>Sintaxis

```vb
ORDERBY (list , expression 1[, expression 2, …, expression N])
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

La ruta válida de un origen de datos del tipo de datos *Lista de registros*.

`expression 1`: *Campo*

La ruta válida de un campo del origen de datos al que hace referencia el argumento `list` de la función llamada. El campo referenciado debe ser un campo del tipo de datos primitivo. Este argumento es obligatorio.

`expression N`: *Campo*

La ruta válida de un campo del origen de datos al que hace referencia el argumento `list` de la función llamada. El campo referenciado debe ser un campo del tipo de datos primitivo. Estos argumentos adicionales son opcionales.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

La lista de registros resultante.

## <a name="example-1"></a>Ejemplo 1

Si especifica el origen de datos **DS** del tipo *Campo calculado* y contiene la expresión `SPLIT ("C|B|A", "|")`, la expresión `FIRST( ORDERBY( DS, DS. Value)).Value` devuelve el valor de texto **"A"**.

## <a name="example-2"></a>Ejemplo 2

Cuando **Proveedor** se configura como origen de datos de ER que hace referencia a la tabla VendTable, la expresión `ORDERBY (Vendors, Vendors.'name()')` devuelva la lista de proveedores que se clasifica por nombre en orden ascendente.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]