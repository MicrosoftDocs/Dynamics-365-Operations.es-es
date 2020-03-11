---
title: Función STRINGJOIN de ER
description: En este tema se proporciona información sobre cómo usar la función STRINGJOIN de informes electrónicos (ER).
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
ms.openlocfilehash: 10a98e98d913b0b4fe36690f7effd5d8d9a3faf4
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041800"
---
# <a name="STRINGJOIN">Función STRINGJOIN de ER</a>

[!include [banner](../includes/banner.md)]

La función `STRINGJOIN` devuelve una valor *Cadena* que consta de valores concatenados del campo especificado de la lista especificada. Los valores pueden estar separados por el delimitador especificado.

## <a name="syntax"></a>Sintaxis

```vb
STRINGJOIN (list, field, delimiter)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

La ruta válida de un origen de datos del tipo de datos *Lista de registros*.

`field`: *Campo*

La ruta válida de un campo del tipo de datos *Cadena* en la lista especificada.

`delimiter`: *Cadena*

Un delimitador que se utiliza para separar subcadenas.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="example"></a>Ejemplo

Si introduce `SPLIT("abc" , 1)` como fuente de datos **DS**, la expresión `STRINGJOIN (DS, DS.Value, "-")` devuelve **"a-b-c"**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)
