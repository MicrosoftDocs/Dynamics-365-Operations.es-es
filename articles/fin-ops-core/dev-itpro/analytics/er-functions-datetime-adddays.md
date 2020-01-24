---
title: Función ADDDAYS ER
description: Este tema proporciona información general sobre cómo usar la función ADDDAYS de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dd1290538c506cd0db6eb21a304ff9812c808f17
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916462"
---
# <span data-ttu-id="689cc-103"><a name="ADDDAYS">Función ADDDAYS ER</a></span><span class="sxs-lookup"><span data-stu-id="689cc-103"><a name="ADDDAYS">ADDDAYS ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="689cc-104">La función `ADDDAYS` calcula un valor *Fecha y hora* que es el número especificado de días antes o después de una fecha de inicio especificada.</span><span class="sxs-lookup"><span data-stu-id="689cc-104">The `ADDDAYS` function calculates a *DateTime* value that is the specified number of days before or after a specified start date.</span></span>

## <a name="syntax"></a><span data-ttu-id="689cc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="689cc-105">Syntax</span></span>

```
ADDDAYS (datetime, days)
```

## <a name="arguments"></a><span data-ttu-id="689cc-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="689cc-106">Arguments</span></span>

<span data-ttu-id="689cc-107">`datetime`: *Fecha y hora*</span><span class="sxs-lookup"><span data-stu-id="689cc-107">`datetime`: *DateTime*</span></span>

<span data-ttu-id="689cc-108">Un valor de fecha / hora que representa la fecha de inicio.</span><span class="sxs-lookup"><span data-stu-id="689cc-108">A date/time value that represents the start date.</span></span>

<span data-ttu-id="689cc-109">`days`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="689cc-109">`days`: *Integer*</span></span>

<span data-ttu-id="689cc-110">El número de días antes o después de `datetime`.</span><span class="sxs-lookup"><span data-stu-id="689cc-110">The number of days before or after `datetime`.</span></span>

## <a name="return-values"></a><span data-ttu-id="689cc-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="689cc-111">Return values</span></span>

<span data-ttu-id="689cc-112">*DateTime*</span><span class="sxs-lookup"><span data-stu-id="689cc-112">*DateTime*</span></span>

<span data-ttu-id="689cc-113">El valor de fecha/hora resultante.</span><span class="sxs-lookup"><span data-stu-id="689cc-113">The resulting date/time value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="689cc-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="689cc-114">Usage notes</span></span>

<span data-ttu-id="689cc-115">Un valor positivo para `days` da una fecha futura.</span><span class="sxs-lookup"><span data-stu-id="689cc-115">A positive value for `days` yields a future date.</span></span> <span data-ttu-id="689cc-116">Un valor negativo produce una fecha pasada.</span><span class="sxs-lookup"><span data-stu-id="689cc-116">A negative value yields a past date.</span></span>

## <a name="example-1"></a><span data-ttu-id="689cc-117">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="689cc-117">Example 1</span></span>

<span data-ttu-id="689cc-118">`ADDDAYS (NOW(), 7)` devuelve la fecha y la hora siete días en el futuro.</span><span class="sxs-lookup"><span data-stu-id="689cc-118">`ADDDAYS (NOW(), 7)` returns the date and time seven days in the future.</span></span>

## <a name="example-2"></a><span data-ttu-id="689cc-119">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="689cc-119">Example 2</span></span>

<span data-ttu-id="689cc-120">`ADDDAYS (NOW(), -3)` devuelve la fecha y la hora tres días en el pasado.</span><span class="sxs-lookup"><span data-stu-id="689cc-120">`ADDDAYS (NOW(), -3)` returns the date and time three days in the past.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="689cc-121">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="689cc-121">Additional resources</span></span>

[<span data-ttu-id="689cc-122">Funciones de fecha y de tiempo</span><span class="sxs-lookup"><span data-stu-id="689cc-122">Date and time functions</span></span>](er-functions-category-datetime.md)
