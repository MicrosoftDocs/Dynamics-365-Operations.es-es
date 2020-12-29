---
title: Función LIST de ER
description: Este tema proporciona información general sobre cómo usar la función LIST de informes electrónicos (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c7f8e701ec2836206d2299abba5e5b8542b4cf92
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683096"
---
# <a name="list-er-function"></a>Función LIST de ER

[!include [banner](../includes/banner.md)]

La función `LIST` devuelve un valor *Lista de registros* nuevo que consiste en una lista de registros nueva creada a partir de los argumentos especificados.

## <a name="syntax"></a>Sintaxis

```vb
LIST (record 1 [, record 2, …, record N])
```

## <a name="arguments"></a>Argumentos

`record 1`: *Contenedor (registro)*

Una referencia a un origen de datos de tipo de datos *Registro*. Este argumento es obligatorio.

`record N`: *Contenedor (registro)*

Una referencia a un origen de datos de tipo de datos *Registro*. Estos argumentos adicionales son opcionales.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

La lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

La estructura de la lista que se crea contiene solo los campos que se presentan en la estructura de cada registro que se menciona en los argumentos.

## <a name="example"></a>Ejemplo

Especifica el origen de datos **Registro 1** del tipo *Contenedor*. Esta fuente de datos contiene los siguientes campos anidados del *Campo calculado*:

- **Código:** este campo contiene una expresión que devuelve un valor de tipo *Cadena*.
- **Importe:** este campo contiene una expresión que devuelve un valor de tipo *Real*.

Después, especifica el origen de datos **Registro 2** del tipo *Contenedor*. Esta fuente de datos contiene los siguientes campos anidados del *Campo calculado*:

- **Importe:** este campo contiene una expresión que devuelve un valor de tipo *Real*.
- **IsValid:** este campo contiene una expresión que devuelve un valor de tipo *Booleano*.

En este caso, la expresión `LIST('Record 1', 'Record 2')` devuelve una nueva lista que contiene dos registros. La estructura de esta lista consta de un solo campo **Importe** del tipo *Real*, porque este campo es el único campo que se presenta en cada argumento de la función llamada.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)
