---
title: Función MOD_97 de ER
description: Este tema proporciona información general sobre cómo usar la función MOD_97 de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 618cb2b101dd0b1c91b3b1538ef3f87c21e4a70a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563351"
---
# <a name="mod_97-er-function"></a>Función MOD_97 de ER

[!include [banner](../includes/banner.md)]

La función `MOD_97` devuelve un valor *Cadena* que representa una referencia de acreedor como una expresión MOD97, basada en los dígitos del número de factura especificado.

## <a name="syntax"></a>Sintaxis

```vb
MOD_97 (invoice number digits)
```

## <a name="arguments"></a>Argumentos

`invoice number digits`: *Cadena*

Un valor de texto que representa los dígitos de un número de factura.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="example"></a>Ejemplo

`MOD_97 ("VEND-200002")` devuelve **"20000285"**.

## <a name="additional-resources"></a>Recursos adicionales

[Otras funciones (específicas de dominio empresarial)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]