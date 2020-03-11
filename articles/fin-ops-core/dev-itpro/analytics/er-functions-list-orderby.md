---
title: Función ORDERBY de ER
description: En este tema se proporciona información sobre cómo usar la función ORDERBY de informes electrónicos (ER).
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
ms.openlocfilehash: 0a6b5cddc325625dc5b3d677ffcc1da1f8b829cd
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041961"
---
# <a name="ORDERBY">Función ORDERBY de ER</a>

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
