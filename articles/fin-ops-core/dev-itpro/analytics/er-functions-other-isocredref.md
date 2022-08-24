---
title: Función ISOCREDREF de ER
description: En este artículo se proporciona información sobre cómo usar la función ISOCREDREF de informes electrónicos (ER).
author: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 189843d608cc00ac51a284b163553da6d821150e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277598"
---
# <a name="isocredref-er-function"></a>Función ISOCREDREF de ER

[!include [banner](../includes/banner.md)]

La función `ISOCREDREF` devuelve un valor *Cadena* que representa una referencia de acreedor de la Organización Internacional de Normalización (ISO), basada en los dígitos y los símbolos alfabéticos del número de factura especificado.

## <a name="syntax"></a>Sintaxis

```vb
ISOCREDREF (invoice number digits)
```

## <a name="arguments"></a>Argumentos

`invoice number digits`: *Cadena*

Un valor de texto que representa los dígitos de un número de factura.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

> [!NOTE] 
> Para anular símbolos de los alfabetos que no son compatibles con ISO, el argumento `invoice number digits` se debe traducir antes de que se pase a esta función.

## <a name="example"></a>Ejemplo

`ISOCredRef ("VEND-200002")` devuelve **"RF23VEND-200002"**.

## <a name="additional-resources"></a>Recursos adicionales

[Otras funciones (específicas de dominio empresarial)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
