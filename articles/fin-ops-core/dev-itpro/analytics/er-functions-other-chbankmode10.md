---
title: Función CH_BANK_MOD_10 de ER
description: Este tema proporciona información general sobre cómo usar la función CH_BANK_MOD_10 de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: bca82cd596ba1e3ec42b3dba91ee6c4871ff8601
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686867"
---
# <a name="ch_bank_mod_10-er-function"></a>Función CH_BANK_MOD_10 de ER

[!include [banner](../includes/banner.md)]

La función `CH_BANK_MOD_10` devuelve un valor *Cadena* que representa una referencia de acreedor como una expresión MOD10, basada en los dígitos del número de factura especificado.

## <a name="syntax"></a>Sintaxis

```vb
CH_BANK_MOD_10 (invoice number digits)
```

## <a name="arguments"></a>Argumentos

`invoice number digits`: *Cadena*

Un valor de texto que representa los dígitos de un número de factura.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="example"></a>Ejemplo

`CH_BANK_MOD_10 ("VEND-200002")` devuelve **3**.

## <a name="additional-resources"></a>Recursos adicionales

[Otras funciones (específicas de dominio empresarial)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]