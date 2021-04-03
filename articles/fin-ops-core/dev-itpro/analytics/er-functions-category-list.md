---
title: Lista de funciones ER en la categoría de lista.
description: Este tema proporciona información sobre las funciones de lista que son compatibles con los informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 04/01/2020
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
ms.openlocfilehash: b98ad6c2c7eb2881ede83b9bd2d02aac71efc4c9
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561695"
---
# <a name="list-of-er-functions-in-the-list-category"></a>Lista de funciones ER en la categoría de lista.

[!include [banner](../includes/banner.md)]

Las funciones de la lista de informes electrónicos (ER) se pueden usar para extraer información y realizar operaciones en las fuentes de datos de *Lista de registros* y tipos de datos *Contenedor (registro)*. Este tema proporciona un resumen de estas funciones.

## <a name="list-of-supported-functions"></a>Lista de funciones permitidas.

| Función | Descripción |
|----------|-------------|
| [AllItems](er-functions-list-allitems.md)                 | Esta función se ejecuta como una selección en memoria. Devuelve un valor aplanado nuevo de *Lista de registros* que consiste en una lista de registros que representa todos los elementos que coinciden con la ruta especificada. |
| [AllItemsQuery](er-functions-list-allitemsquery.md)       | Esta función se ejecuta como consulta SQL combinada. Devuelve un valor aplanado nuevo de *Lista de registros* que consiste en una lista de registros que representa todos los elementos que coinciden con la ruta especificada. |
| [Cuenta](er-functions-list-count.md)                       | Esta función devuelve un valor *Entero* que representa el número de registros en la lista especificada, si la lista no está vacía. Si la lista está vacía, esta función devuelve **0** (cero). |
| [EmptyList](er-functions-list-emptylist.md)               | Esta función devuelve un valor *Lista de registros* vacío mediante la lista especificada como origen para la estructura de la lista.|
| [Enumerar](er-functions-list-enumerate.md)               | Esta función devuelve un valor *Lista de registros* nuevo que consiste en registros enumerados de la lista especificada. |
| [Filtrar](er-functions-list-filter.md)                     | Esta función devuelve la lista especificada como un valor *Lista de registros* después de que se haya cambiado la consulta para que filtre por la condición especificada. |
| [Primera](er-functions-list-first.md)                       | Esta función devuelve el primer registro de la lista especificada como un valor *Contenedor (registro)*, si esa lista no está vacía. Si la lista está vacía, esta función genera una excepción. |
| [FirstOrNull](er-functions-list-firstornull.md)           | Esta función devuelve el primer registro de la lista especificada como un valor *Contenedor (registro)*, si ese registro no está vacío. Si el registro está vacío, esta función devuelve un valor nulo *Contenedor (registro)*. |
| [Índice](er-functions-list-index.md)                       | Esta función devuelve un valor *Contenedor (registro)* que se selecciona utilizando el índice numérico especificado en la lista especificada. Si el índice está fuera del intervalo de los registros de la lista, esta función produce una excepción. |
| [IsEmpty](er-functions-list-isempty.md)                   | Esta función devuelve un valor *Booleano* de **TRUE** si la lista especificada no contiene registros. De lo contrario, la expresión devuelve un valor *Booleano* de **FALSE**. |
| [Lista](er-functions-list-list.md)                         | Esta función devuelve un valor *Lista de registros* nuevo que consiste en una lista nueva creada a partir de los argumentos especificados.|
| [ListDistinct](er-functions-list-listdistinct.md)         | Esta función calcula la expresión especificada como un selector para cada registro de la lista especificada. Devuelve un nuevo valor de *Lista de registros* que contiene un solo registro para cada valor único del selector.|
| [ListJoin](er-functions-list-listjoin.md)                 | Esta función devuelve un valor *Lista de registros* nuevo que representa una lista unida nueva creada a partir de los argumentos especificados.|
| [ListOfFields](er-functions-list-listoffields.md)         | Esta función devuelve un valor *Lista de registros* que se crea en función de la estructura del argumento especificado del tipo *Enumeración* o *Contenedor (registro)*. |
| [ListOfFirstItem](er-functions-list-listoffirstitem.md)   | Esta función devuelve un valor *Lista de registros* que consiste en solo el primer registro de la lista especificada.|
| [OrderBy](er-functions-list-orderby.md)                   | Esta función devuelve la lista especificada como un valor *Lista de registros* después de que se haya ordenado de acuerdo con los argumentos especificados. Estos argumentos se pueden definir como expresiones. |
| [Revertir](er-functions-list-reverse.md)                   | Esta función devuelve la lista especificada como un valor *Lista de registros* en orden inverso. |
| [Dividir](er-functions-list-split.md)                       | Esta función divide la cadena de entrada especificada en subcadenas y devuelve el resultado como un valor *Lista de registros* nuevo. |
| [SplitList](er-functions-list-splitlist.md)               | Esta función divide la lista especificada en sublistas (o lotes), cada uno conteniendo el número de registros especificado. Devuelve luego el resultado como un nuevo valor *Lista de registros* que consiste en los lotes. |
| [SplitListByLimit](er-functions-list-splitlistbylimit.md) | Esta función divide la lista especificada en una nueva lista de sublistas (lotes). El número de registros en cada lote se calcula dinámicamente. La función devuelve luego el resultado como un nuevo valor *Lista de registros* que consiste en los lotes. |
| [StringJoin](er-functions-list-stringjoin.md)             | Esta función devuelve una valor *Cadena* que consta de valores concatenados del campo especificado de la lista especificada. Los valores pueden estar separados por el delimitador especificado. |
| [Lugar](er-functions-list-where.md)                       | Esta función devuelve la lista especificada como un valor *Lista de registros* después de que se haya filtrado de acuerdo con la condición especificada. |

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de los informes electrónicos](general-electronic-reporting.md)

[Diseñador de fórmulas en los informes electrónicos](general-electronic-reporting-formula-designer.md)

[Idioma de fórmulas en los informes electrónicos](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]