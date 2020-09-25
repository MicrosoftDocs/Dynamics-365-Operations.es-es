---
title: Función NULLCONTAINER de ER
description: Este tema proporciona información general sobre cómo usar la función NULLCONTAINER de informes electrónicos (ER).
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
ms.openlocfilehash: dac6283ec35d3d03f586ca157048bd3ecc4bfa8a
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743936"
---
# <a name="nullcontainer-er-function"></a>Función NULLCONTAINER de ER

[!include [banner](../includes/banner.md)]

La función `NULLCONTAINER` devuelve un valor nulo de tipo *Contenedor (registro)* que tiene la misma estructura que la lista de registros o el registro especificados.

## <a name="syntax"></a>Sintaxis

```vb
NULLCONTAINER (list)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros* o *Contenedor (registro)*

La ruta válida de un origen de datos de tipo *Lista de registros* o *Contenedor (registro)*.

## <a name="return-values"></a>Valores de retorno

*Contenedor (registro)*

El valor de registro resultante.

## <a name="usage-notes"></a>Notas de uso

> [!NOTE] 
> Esta función es obsoleta. Use en su lugar la función `EMPTYRECORD`. Para obtener más información, consulte [EMPTYRECORD](er-functions-record-emptyrecord.md)

## <a name="example"></a>Ejemplo

`NULLCONTAINER (SPLIT ("abc", 1))` devuelve un nuevo registro vacío que tiene la misma estructura que la lista que devuelve la función `SPLIT` utilizada. Para obtener más información, consulte [SPLIT](er-functions-list-split.md)

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de registro](er-functions-category-record.md)
