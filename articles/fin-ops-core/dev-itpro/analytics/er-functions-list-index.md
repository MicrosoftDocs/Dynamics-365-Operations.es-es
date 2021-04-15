---
title: Función INDEX de ER
description: Este tema proporciona información general sobre cómo usar la función INDEX de informes electrónicos (ER).
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
ms.openlocfilehash: 14f10359a3f20fb9d23639babce764b9ef64243d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750469"
---
# <a name="index-er-function"></a>Función INDEX de ER

[!include [banner](../includes/banner.md)]

La función `INDEX` devuelve un valor *Contenedor (registro)* que se selecciona utilizando el índice numérico especificado en la lista especificada. Si el índice está fuera del intervalo para los registros de la lista, se produce una excepción.

## <a name="syntax"></a>Sintaxis

```vb
INDEX (list, index)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

La ruta válida de un origen de datos del tipo de datos *Lista de registros*.

`index`: *Entero*

Un índice numérico que indica la posición del registro deseado en la lista especificada.

## <a name="return-values"></a>Valores de retorno

*Contenedor (registro)*

El valor de registro resultante.

## <a name="example-1"></a>Ejemplo 1

Si especifica el origen de datos **DS** para el tipo *Campo calculado* y este contiene la expresión `SPLIT ("A|B|C", "|")`, la expresión `DS.Value` devuelve el valor de texto **"B"** para el segundo registro de esta lista de registros. La expresión `INDEX (SPLIT ("A|B|C", "|"), 2).Value` también devuelve el valor del texto **"B"**.

## <a name="example-2"></a>Ejemplo 2

Si especifica el origen de datos **DS** del tipo *Campo calculado* y contiene la expresión `SPLIT ("A|B|C", "|")`, la expresión `INDEX (SPLIT ("A|B|C", "|"), 4).Value` lanza una excepción en tiempo de ejecución.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]