---
title: Función SESSIONTODAY ER
description: En este tema se proporciona información sobre cómo usar la función SESSIONTODAY de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: e6ad28e642fcfae3cfa2692a4e41b99fae7fc9df
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561359"
---
# <a name="sessiontoday-er-function"></a>Función SESSIONTODAY ER

[!include [banner](../includes/banner.md)]

La función `SESSIONTODAY` devuelve un valor *Fecha* que representa la fecha actual de la sesión de la aplicación.

## <a name="syntax"></a>Sintaxis

```vb
SESSIONTODAY ()
```

## <a name="return-values"></a>Valores de retorno

*Fecha*

El valor de fecha resultante.

## <a name="example"></a>Ejemplo

`DATEFORMAT (SESSIONTODAY (), "d", "DE")` devuelve la fecha de sesión de la aplicación actual, 24 de diciembre de 2015, como la cadena **"24-12-2015"**, basado en la cultura alemana seleccionada y el formato especificado.

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de fecha y de tiempo](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]