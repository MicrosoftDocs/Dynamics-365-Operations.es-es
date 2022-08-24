---
title: Función TABLENAME2ID de ER
description: En este artículo se proporciona información sobre cómo usar la función TABLENAME2ID de informes electrónicos (ER).
author: kfend
ms.date: 12/12/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: fe7ed336f2264e15e0a8a7305e1bcebb75b2cd07
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268068"
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
