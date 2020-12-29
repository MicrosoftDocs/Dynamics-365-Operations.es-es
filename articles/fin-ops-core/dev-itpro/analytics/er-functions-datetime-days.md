---
title: Función DAYS ER
description: Este tema proporciona información general sobre cómo usar la función DAYS de informes electrónicos (ER).
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
ms.openlocfilehash: 66398e624e4b9d69d4dc3ccf3ee8f97758f4f861
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682350"
---
# <a name="days-er-function"></a><span data-ttu-id="7ad07-103">Función DAYS ER</span><span class="sxs-lookup"><span data-stu-id="7ad07-103">DAYS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7ad07-104">La función `DAYS` devuelve un valor *Entero* que representa el número de días entre una fecha especificada y una segunda fecha especificada.</span><span class="sxs-lookup"><span data-stu-id="7ad07-104">The `DAYS` function returns an *Integer* value that represents the number of days between one specified date and a second specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="7ad07-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ad07-105">Syntax</span></span>

```vb
DAYS (date 1, date 2) as Integer
```

## <a name="arguments"></a><span data-ttu-id="7ad07-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7ad07-106">Arguments</span></span>

<span data-ttu-id="7ad07-107">`date 1`: *Fecha*</span><span class="sxs-lookup"><span data-stu-id="7ad07-107">`date 1`: *Date*</span></span>

<span data-ttu-id="7ad07-108">Un valor de fecha que representa la fecha de inicio para el cálculo del número de días.</span><span class="sxs-lookup"><span data-stu-id="7ad07-108">A date value that represents the start date for the calculation of the number of days.</span></span>

<span data-ttu-id="7ad07-109">`date 2`: *Fecha*</span><span class="sxs-lookup"><span data-stu-id="7ad07-109">`date 2`: *Date*</span></span>

<span data-ttu-id="7ad07-110">Un valor de fecha que representa la fecha final para el cálculo del número de días.</span><span class="sxs-lookup"><span data-stu-id="7ad07-110">A date value that represents the end date for the calculation of the number of days.</span></span>

## <a name="return-values"></a><span data-ttu-id="7ad07-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="7ad07-111">Return values</span></span>

<span data-ttu-id="7ad07-112">*Entero*</span><span class="sxs-lookup"><span data-stu-id="7ad07-112">*Integer*</span></span>

<span data-ttu-id="7ad07-113">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="7ad07-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="7ad07-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="7ad07-114">Usage notes</span></span>

<span data-ttu-id="7ad07-115">La función `DAYS` devuelve un valor positivo cuando la primera fecha es posterior a la segunda fecha, devuelve **0** (cero) cuando la primera fecha es igual a la segunda fecha y devuelve un valor negativo cuando la primera fecha es anterior a la segunda fecha.</span><span class="sxs-lookup"><span data-stu-id="7ad07-115">The `DAYS` function returns a positive value when the first date is later than the second date, it returns **0** (zero) when the first date equals the second date, and it returns a negative value when the first date is earlier than the second date.</span></span>

## <a name="example"></a><span data-ttu-id="7ad07-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7ad07-116">Example</span></span>

<span data-ttu-id="7ad07-117">`DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` devuelve **-1**.</span><span class="sxs-lookup"><span data-stu-id="7ad07-117">`DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` returns **-1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7ad07-118">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="7ad07-118">Additional resources</span></span>

[<span data-ttu-id="7ad07-119">Funciones de fecha y de tiempo</span><span class="sxs-lookup"><span data-stu-id="7ad07-119">Date and time functions</span></span>](er-functions-category-datetime.md)
