---
title: Función EMPTYRECORD de ER
description: En este tema se proporciona información sobre cómo usar la función EMPTYRECORD de informes electrónicos (ER).
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
ms.openlocfilehash: 2e46fcef3d53483b782ac39a0661fc0edc8d861c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743959"
---
# <a name="emptyrecord-er-function"></a>Función EMPTYRECORD de ER

[!include [banner](../includes/banner.md)]

La función `EMPTYRECORD` devuelve un valor nulo de tipo *Contenedor (registro)* que tiene la misma estructura que la lista de registros o el registro especificados.

## <a name="syntax"></a>Sintaxis

```vb
EMPTYRECORD (list)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros* o *Contenedor (registro)*

La ruta válida de un origen de datos de tipo *Lista de registros* o *Contenedor (registro)*.

## <a name="return-values"></a>Valores de retorno

*Contenedor (registro)*

El valor de registro resultante.

## <a name="usage-notes"></a>Notas de uso

> [!NOTE] 
> Un registro nulo es un registro donde todos los campos tienen un valor vacío. Un valor vacío es **0** (cero) para números, una cadena vacía para las cadenas, y así sucesivamente.

## <a name="example"></a>Ejemplo

`EMPTYRECORD (SPLIT ("abc", 1))` devuelve un nuevo registro vacío que tiene la misma estructura que la lista que devuelve la función `SPLIT` utilizada. Para obtener más información, consulte [SPLIT](er-functions-list-split.md)

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de registro](er-functions-category-record.md)
