---
title: Función VALUE ER
description: Este tema proporciona información general sobre cómo usar la función VALUE de informes electrónicos (ER).
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
ms.openlocfilehash: 160dd81baa43702b2deea1e3eea20080fca122ca
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917635"
---
# <a name="VALUE">Función VALUE ER</a>

[!include [banner](../includes/banner.md)]

La función `VALUE` devuelve un valor *Real* que se convierte de la cadena especificada.

## <a name="syntax"></a>Sintaxis

```
VALUE (text)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadena*

Un valor de cadena que debe convertirse en un valor numérico.

## <a name="return-values"></a>Valores de retorno

*Real*

El valor numérico resultante.

## <a name="usage-notes"></a>Notas de uso

Las comas y los caracteres de punto (.) se consideran separadores decimales y los guiones iniciales (-) se usan como signo negativo. Se generará una excepción en el tiempo de ejecución si la cadena especificada contiene otros caracteres no numéricos.

## <a name="example-1"></a>Ejemplo 1

`VALUE ("1 234,56")` genera una excepción.

## <a name="example-2"></a>Ejemplo 2

`VALUE ("1234,56")` devuelve **1234,56**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de conversión de tipos](er-functions-category-type-conversion.md)
