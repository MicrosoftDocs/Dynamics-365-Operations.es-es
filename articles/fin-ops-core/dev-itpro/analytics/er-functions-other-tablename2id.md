---
title: Función TABLENAME2ID de ER
description: Este tema proporciona información general sobre cómo usar la función TABLENAME2ID de informes electrónicos (ER).
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
ms.openlocfilehash: d9f9e38f46df8a93b5cb16b8d0d5e5afbff8558a
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744008"
---
# <a name="tablename2id-er-function"></a>Función TABLENAME2ID de ER

[!include [banner](../includes/banner.md)]

La función `TABLENAME2ID` devuelve una representación numérica del id. de tabla para el nombre de tabla especificado como un valor de tipo *Entero*.

## <a name="syntax"></a>Sintaxis

```vb
TABLENAME2ID (text)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadena*

Un valor de texto que representa un nombre de tabla válido.

## <a name="return-values"></a>Valores de retorno

*Entero*

El valor numérico resultante.

## <a name="usage-notes"></a>Notas de uso

La ejecución de esta función puede tener diferentes resultados en diferentes instancias de Microsoft Dynamics 365 Finance, aunque se utilice el mismo nombre de empresa.

## <a name="example"></a>Ejemplo

`TABLENAME2ID ("Intrastat")` devuelve **1510**.

## <a name="additional-resources"></a>Recursos adicionales

[Otras funciones (específicas de dominio empresarial)](er-functions-category-other.md)
