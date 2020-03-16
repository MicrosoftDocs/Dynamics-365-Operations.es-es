---
title: Función CONCATENATE de ER
description: En este tema se proporciona información sobre cómo usar la función CONCATENATE de informes electrónicos (ER).
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
ms.openlocfilehash: 04c7b32e2a9578f8864570a552817ec3ce28fa43
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041197"
---
# <a name="CONCATENATE">Función CONCATENATE de ER</a>

[!include [banner](../includes/banner.md)]

La función `CONCATENATE` devuelve todas las cadenas de texto especificadas como un valor de tipo *Cadena* después de unirlas en una sola cadena.

## <a name="syntax"></a>Sintaxis

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a>Argumentos

`text 1`: *Cadena*

Una referencia a un origen de datos del tipo de datos *Cadena*. Este argumento es obligatorio.

`text N`: *Cadena*

Una referencia a un origen de datos del tipo de datos *Cadena*. Estos argumentos adicionales son opcionales.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="example"></a>Ejemplo

`CONCATENATE ("abc", "def")` devuelve **"abcdef"**.

## <a name="usage-notes"></a>Notas de uso

La expresión `"abc" & "def"` también devuelve **"abcdef"**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)
