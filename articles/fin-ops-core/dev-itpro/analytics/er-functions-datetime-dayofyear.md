---
title: Función DAYOFYEAR ER
description: Este tema proporciona información general sobre cómo usar la función DATEOFYEAR de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: b9b937e7fae3e90d1a87196fab653dfac8e94179
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682398"
---
# <a name="dayofyear-er-function"></a><span data-ttu-id="335f1-103">Función DAYOFYEAR ER</span><span class="sxs-lookup"><span data-stu-id="335f1-103">DAYOFYEAR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="335f1-104">La función `DAYOFYEAR` devuelve un valor *Entero* que representa el número de días entre el 1 de enero y la fecha especificada.</span><span class="sxs-lookup"><span data-stu-id="335f1-104">The `DAYOFYEAR` function returns an *Integer* value that represents the number of days between January 1 and the specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="335f1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="335f1-105">Syntax</span></span>

```vb
DAYOFYEAR (date) as Integer
```

## <a name="arguments"></a><span data-ttu-id="335f1-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="335f1-106">Arguments</span></span>

<span data-ttu-id="335f1-107">`date`: *Fecha*</span><span class="sxs-lookup"><span data-stu-id="335f1-107">`date`: *Date*</span></span>

<span data-ttu-id="335f1-108">Un valor de fecha que representa la fecha a usar para el cálculo del número de días.</span><span class="sxs-lookup"><span data-stu-id="335f1-108">A date value that represents the date to use for the calculation of the number of days.</span></span>

## <a name="return-values"></a><span data-ttu-id="335f1-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="335f1-109">Return values</span></span>

<span data-ttu-id="335f1-110">*Entero*</span><span class="sxs-lookup"><span data-stu-id="335f1-110">*Integer*</span></span>

<span data-ttu-id="335f1-111">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="335f1-111">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="335f1-112">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="335f1-112">Example 1</span></span>

<span data-ttu-id="335f1-113">`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` devuelve **61**.</span><span class="sxs-lookup"><span data-stu-id="335f1-113">`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` returns **61**.</span></span>

## <a name="example-2"></a><span data-ttu-id="335f1-114">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="335f1-114">Example 2</span></span>

<span data-ttu-id="335f1-115">`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` devuelve **1**.</span><span class="sxs-lookup"><span data-stu-id="335f1-115">`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="335f1-116">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="335f1-116">Additional resources</span></span>

[<span data-ttu-id="335f1-117">Funciones de fecha y de tiempo</span><span class="sxs-lookup"><span data-stu-id="335f1-117">Date and time functions</span></span>](er-functions-category-datetime.md)
