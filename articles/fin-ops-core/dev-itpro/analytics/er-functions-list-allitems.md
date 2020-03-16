---
title: Función ALLITEMS ER
description: En este tema se proporciona información sobre cómo usar la función ALLITEMS de informes electrónicos (ER).
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
ms.openlocfilehash: 3aa226be8bc27817b4369b9e5b24faee8ea52b88
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042237"
---
# <a name="ALLITEMS">Función ALLITEMS ER</a>

[!include [banner](../includes/banner.md)]

La función `ALLITEMS` se ejecuta como una selección en memoria y devuelve un nuevo valor aplanado *Lista de registros* como una lista de registros que representa todos los elementos que coinciden con la ruta especificada.

## <a name="syntax"></a>Sintaxis

```vb
ALLITEMS (path)
```

## <a name="arguments"></a>Argumentos

`path`: *Lista de registros*

La ruta válida de un origen de datos del tipo de datos *Lista de registros*.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

La lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

La ruta se debe definir como ruta válida de un origen de datos a un elemento de origen de datos del tipo de datos de la *Lista de registro*. Elementos de datos como la cadena de ruta y la fecha deberían activar un error en el tiempo de diseño del generador de expresiones de informes electrónicos (ER).

No recomendamos que utilice esta función para orígenes de datos transaccionales que puedan contener un gran volumen de datos. En cambio, considere usar la función [ALLTEMSQUERY ](er-functions-list-allitemsquery.md).

## <a name="example-1"></a>Ejemplo 1

Si introduce `SPLIT("abcdef" , 2)` como fuente de datos **DS**, la expresión `COUNT( ALLITEMS (DS))` devuelve **3**.

## <a name="example-2"></a>Ejemplo 2

Si introduce **Vendedor** como la fuente de datos del tipo de datos *Lista de registros* que se refiere a la tabla de la aplicación VendTable, la expresión `ALLITEMS (Vend.'<Relations'.ContactPerson)` devuelve una lista aplanada de registros que tiene la estructura de tabla **Persona de contacto** y contiene todas las personas de contacto a las que se puede acceder utilizando la relación **ContactPerson.ContactForParty == VendTable.Party**, y eso está disponible para todos los proveedores de la tabla de proveedores referenciada.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)
