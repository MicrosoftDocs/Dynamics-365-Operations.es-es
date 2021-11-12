---
title: Función NEWGUID ER
description: En este tema se proporciona información sobre cómo usar la función NEWGUID de informes electrónicos (ER).
author: NickSelin
ms.date: 09/09/2021
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-09-08
ms.dyn365.ops.version: AX 10.0.23
ms.openlocfilehash: 5856a4d765f5136ecb11a34e0255c1ba88818f2c
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2021
ms.locfileid: "7647956"
---
# <a name="newguid-er-function"></a>Función NEWGUID ER

[!include [banner](../includes/banner.md)]

La función `NEWGUID` genera un nuevo identificador único global (GUID) y lo devuelve como un valor *[GUID](er-formula-supported-data-types-primitive.md#guid)*.

## <a name="syntax"></a>Sintaxis

```vb
NEWGUID ()
```

## <a name="return-values"></a>Valores de retorno

*GUID*

El valor de GUID resultante.

## <a name="example"></a>Ejemplo

`NEWGUID()` siempre devuelve un nuevo valor *GUID*, como **3afcf7ff-af10-ec11-b6e6-000d3a13209e**.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
