---
title: Función TEXT de ER
description: Este tema proporciona información general sobre cómo usar la función TEXT de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: c08aca949ffc7e62009bf3f6c664d96b368f43e7
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040906"
---
# <a name="TEXT">Función TEXT de ER</a>

[!include [banner](../includes/banner.md)]

La función `TEXT` devuelve el número especificado como un valor de tipo *Cadena* después de que se haya convertido en una cadena de texto que se formatea según la configuración regional del servidor de la instancia actual de la aplicación.

## <a name="syntax"></a>Sintaxis

```vb
TEXT (number)
```

## <a name="arguments"></a>Argumentos

`number`: *Entero* o *Real*

Un valor numérico que debe convertirse en una cadena de texto.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

Para los valores del tipo *Real*, la conversión de la cadena está limitada a dos posiciones decimales.

## <a name="example"></a>Ejemplo

Si se define la configuración regional del servidor de la instancia de Microsoft Dynamics 365 Finance como **EN-US**, `TEXT (NOW ())` devuelve la fecha de la sesión de Finance actual, el 17 de diciembre de 2015, como la cadena de texto **"12/17/2015 07:59:23 AM"**. `TEXT (1/3)` devuelve **"0.33"**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)
