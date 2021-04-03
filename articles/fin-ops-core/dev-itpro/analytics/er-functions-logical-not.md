---
title: Función NOT de ER
description: Este tema proporciona información general sobre cómo usar la función NOT de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 9b55b3d8930ece7e2f2925579821ca88749801f7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565889"
---
# <a name="not-er-function"></a>Función NOT de ER

[!include [banner](../includes/banner.md)]

La función `NOT` devuelve el valor lógico invertido de la condición especificada como un valor *Booleano*.

## <a name="syntax"></a>Sintaxis

```vb
NOT (condition)
```

## <a name="arguments"></a>Argumentos

`condition`: *Booleano*

Una expresión condicional válida que debe revertirse.

## <a name="return-values"></a>Valores de retorno

*Booleano*

El valor *Booleano* resultante.

## <a name="example"></a>Ejemplo

`NOT (TRUE)` devuelve **FALSE**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones lógicas](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]