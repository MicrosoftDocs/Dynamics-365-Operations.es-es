---
title: Función EMPTYRECORD de ER
description: En este tema se proporciona información sobre cómo usar la función EMPTYRECORD de informes electrónicos (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 5aea5533f5d0530cdc9ccae0b0b8355245599bc77e37fde87a13e8e5a1443695
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6725195"
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]