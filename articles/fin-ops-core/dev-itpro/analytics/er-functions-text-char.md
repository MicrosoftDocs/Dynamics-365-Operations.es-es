---
title: Función CHAR de ER
description: Este tema proporciona información general sobre cómo usar la función CHAR de informes electrónicos (ER).
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
ms.openlocfilehash: 7813b0c6002e47aef6a8c119c72728a49584401b
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041246"
---
# <a name="CHAR">Función CHAR de ER</a>

[!include [banner](../includes/banner.md)]

La función `CHAR` devuelve un valor de tipo *Cadena* que presenta un solo carácter al que hace referencia el código numérico de Unicode especificado.

## <a name="syntax"></a>Sintaxis

```vb
CHAR (number)
```

## <a name="arguments"></a>Argumentos

`number`: *Entero*

Un número que corresponde a un único carácter.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

La cadena que esta función devuelve depende de la codificación seleccionada en el elemento de formato **ARCHIVO** principal. Para ver una de lista de codificaciones admitidas, consulte [Clase de codificación](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).

## <a name="example"></a>Ejemplo

`CHAR (255)` devuelve **"ÿ"**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)
