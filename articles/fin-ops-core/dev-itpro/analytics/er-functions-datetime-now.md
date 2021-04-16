---
title: Función NOW ER
description: Este tema proporciona información general sobre cómo usar la función NOW de informes electrónicos (ER).
author: NickSelin
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
ms.openlocfilehash: c93aa2a0e3f6aa07ab9e843d3c5f11c5265e8c40
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746876"
---
# <a name="now-er-function"></a><span data-ttu-id="d8867-103">Función NOW ER</span><span class="sxs-lookup"><span data-stu-id="d8867-103">NOW ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d8867-104">La función `NOW` devuelve un valor *Fecha y hora* que representa la fecha y hora actuales del servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d8867-104">The `NOW` function returns a *DateTime* value that represents the current application server date and time.</span></span>

## <a name="syntax"></a><span data-ttu-id="d8867-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8867-105">Syntax</span></span>

```vb
NOW ()
```

## <a name="return-values"></a><span data-ttu-id="d8867-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="d8867-106">Return values</span></span>

<span data-ttu-id="d8867-107">*DateTime*</span><span class="sxs-lookup"><span data-stu-id="d8867-107">*DateTime*</span></span>

<span data-ttu-id="d8867-108">El valor de fecha/hora resultante.</span><span class="sxs-lookup"><span data-stu-id="d8867-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="d8867-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d8867-109">Example</span></span>

<span data-ttu-id="d8867-110">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` devuelve la fecha/hora del servidor actual, 24 de diciembre de 2015, como **“24-12-2015”**, basado en el formato personalizado especificado.</span><span class="sxs-lookup"><span data-stu-id="d8867-110">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returns the current application server date/time value, December 24, 2015, as **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d8867-111">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d8867-111">Additional resources</span></span>

[<span data-ttu-id="d8867-112">Funciones de fecha y de tiempo</span><span class="sxs-lookup"><span data-stu-id="d8867-112">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]