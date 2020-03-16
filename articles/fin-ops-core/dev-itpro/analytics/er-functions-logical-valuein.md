---
title: Función VALUEIN de ER
description: Este tema proporciona información general sobre cómo usar la función VALUEIN de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: d0df97234df41d11897473dea4e85354e82d36ec
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041708"
---
# <a name="VALUEIN">Función VALUEIN de ER</a>

[!include [banner](../includes/banner.md)]

La función `VALUEIN` determina si la entrada especificada coincide con algún valor de un elemento específico de la lista especificada. Devuelve un *Booleano* valor de **TRUE** si la entrada especificada coincide con el resultado de ejecutar la expresión especificada para al menos un registro de la lista especificada. De lo contrario, la expresión devuelve un valor *Booleano* de **FALSE**.

## <a name="syntax"></a>Sintaxis

```vb
VALUEIN (input, list, list item expression)
```

## <a name="arguments"></a>Argumentos

`input`: *Campo*

La ruta válida de un elemento de un origen de datos del tipo *Lista de registros*. El valor de este elemento se conciliará.

`list`: *Lista de registros*

La ruta válida de un origen de datos del tipo de datos *Lista de registros*.

`list item expression`: *Booleano*

Un expresión condicional válida que señala o contiene un único campo de la lista especificada que se debe usar para la asignación.

## <a name="return-values"></a>Valores de retorno

*Booleano*

El valor *Booleano* resultante.

## <a name="usage-notes"></a>Notas de uso

En general, la función `VALUEIN` se convierte a un conjunto de condiciones **OR**.

```vb
(input = list.item1.value) OR (input = list.item2.value) OR …
```

En algunos casos, se puede traducir a una instrucción de la base de datos SQL mediante el uso del operador `EXISTS JOIN`.

## <a name="example-1"></a>Ejemplo 1

En su modelo de asignación, define el origen de datos **Lista** del tipo *Campo calculado*. Este origen de datos contiene la expresión `SPLIT ("a,b,c", ",")`.

Cuando se llama a un origen de datos, si se ha configurado como la expresión `VALUEIN ("B", List, List.Value)`, devuelve **TRUE**. En este caso, la función `VALUEIN` se traduce al conjunto de condiciones siguiente: `(("B" = "a") or ("B" = "b") or ("B" = "c"))`, donde `("B" = "b")` es igual a **TRUE**.

Cuando se llama a un origen de datos, si se ha configurado como la expresión `VALUEIN ("B", List, LEFT(List.Value, 0))`, devuelve **FALSE**. En este caso, la función `VALUEIN` se traduce a la condición siguiente: `("B" = "")`, que no es igual a **TRUE**.

El límite superior del número de caracteres en el texto de esta condición es 32 768 caracteres. Por lo tanto, no es necesario crear orígenes de datos que puedan superar este límite en el tiempo de ejecución. Si se supera el límite, la aplicación dejará de ejecutarse, y se generará una excepción. Por ejemplo, esta situación puede producirse si el origen de datos se configura como `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)`, y las listas **List1** y **List2** contienen un gran número de registros.

En algunos casos, la función `VALUEIN` se convierte en una instrucción de una base de datos mediante el operador `EXISTS JOIN`. Este comportamiento aparece cuando se utiliza la función [FILTER](er-functions-list-filter.md) y se cumplen las siguientes condiciones:

- La opción **PEDIR CONSULTA** se desactiva para el origen de datos de la función `VALUEIN` que se refiere a la lista de registros. No se aplicarán condiciones adicionales a este origen de datos en el tiempo de ejecución.
- No se configuran expresiones anidadas para el origen de datos de la función `VALUEIN` que se refiere a la lista de registros.
- Un elemento de lista de la función `VALUEIN` hace referencia a un campo del origen de datos especificado, no una expresión o un método.

Considere usar esta opción en lugar de la función [WHERE](er-functions-list-where.md) que se describe anteriormente en este ejemplo.

## <a name="example-2"></a>Ejemplo 2

Defina los siguientes orígenes de datos en la asignación de su modelo:

- El origen de datos **En** del tipo *Registros de la tabla*. Este origen de datos se refiere a la tabla Intrastat.
- El origen de datos **Puerto** del tipo *Registros de la tabla*. Este origen de datos se refiere a la tabla IntrastatPort.

Cuando se llama a un origen de datos que está configurado como la expresión `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)`, la instrucción SQL siguiente se genera para devolver registros filtrados de la tabla Intrastat.

```vb
select … from Intrastat
exists join TableId from IntrastatPort
where IntrastatPort.PortId = Intrastat.Port
```

Para los campos **dataAreaId** , la instrucción SQL final se genera usando el operador `IN`.

## <a name="example-3"></a>Ejemplo 3

Defina los siguientes orígenes de datos en la asignación de su modelo:

- Agregue el origen de datos **Le** al tipo de datos *Campo calculado*. Este origen de datos contiene la expresión `SPLIT ("DEMF,GBSI,USMF", ",")`.
- El origen de datos **En** del tipo *Registros de la tabla*. Esta fuente de datos se refiere a la tabla Intrastat, y la opción **Entre empresas** está desactivada para ello.

Cuando se llama a un origen de datos que se configuró como la expresión `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)`, la instrucción SQL final contiene la siguiente condición.

```vb
Intrastat.dataAreaId IN ('DEMF', 'GBSI', 'USMF')
```

## <a name="additional-resources"></a>Recursos adicionales

[Funciones lógicas](er-functions-category-logical.md)
