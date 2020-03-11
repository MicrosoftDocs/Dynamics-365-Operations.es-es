---
title: Función UPPER de ER
description: Este tema proporciona información general sobre cómo usar la función UPPER de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 77854d645ba5b65a2819437af510fcd67be6d99d
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040949"
---
# <a name="UPPER">Función UPPER de ER</a>

[!include [banner](../includes/banner.md)]

La función `UPPER` devuelve la cadena de texto especificada como un valor de tipo *Cadena* después de convertirla a letras mayúsculas.

## <a name="syntax"></a>Sintaxis

```vb
UPPER (text )
```

## <a name="arguments"></a>Argumentos

`text`: *Cadena*

La ruta válida de un origen de datos de tipo *Cadena*.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="example"></a>Ejemplo

`UPPER ("Sample")` devuelve **"SAMPLE"**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)
