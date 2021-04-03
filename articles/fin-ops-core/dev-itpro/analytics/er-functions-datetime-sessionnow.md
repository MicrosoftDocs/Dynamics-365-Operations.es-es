---
title: Función SESSIONNOW ER
description: En este tema se proporciona información sobre cómo usar la función SESSIONNOW de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: a79e8055a4b5025e1b1c4ab91875cf165fa8b354
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563409"
---
# <a name="sessionnow-er-function"></a><span data-ttu-id="bac60-103">Función SESSIONNOW ER</span><span class="sxs-lookup"><span data-stu-id="bac60-103">SESSIONNOW ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bac60-104">La función `SESSIONNOW` devuelve un valor *Fecha y hora* que representa la fecha y hora actuales de la sesión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bac60-104">The `SESSIONNOW` function returns a *DateTime* value that represents the current application session date and time.</span></span>

## <a name="syntax"></a><span data-ttu-id="bac60-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bac60-105">Syntax</span></span>

```vb
SESSIONNOW ()
```

## <a name="return-values"></a><span data-ttu-id="bac60-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="bac60-106">Return values</span></span>

<span data-ttu-id="bac60-107">*DateTime*</span><span class="sxs-lookup"><span data-stu-id="bac60-107">*DateTime*</span></span>

<span data-ttu-id="bac60-108">El valor de fecha/hora resultante.</span><span class="sxs-lookup"><span data-stu-id="bac60-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="bac60-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bac60-109">Example</span></span>

<span data-ttu-id="bac60-110">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` devuelve la fecha/hora de sesión de la aplicación actual, 24 de diciembre de 2015, como la cadena **"24.12.2015"**, basado en la cultura alemana seleccionada y el formato especificado.</span><span class="sxs-lookup"><span data-stu-id="bac60-110">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returns the current application session date/time value, December 24, 2015, as **"24.12.2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bac60-111">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="bac60-111">Additional resources</span></span>

[<span data-ttu-id="bac60-112">Funciones de fecha y de tiempo</span><span class="sxs-lookup"><span data-stu-id="bac60-112">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]