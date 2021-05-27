---
title: Solo se imprime una etiqueta para varios encabezados de trabajo en una sola recepción
description: Solo se imprime una etiqueta para varios encabezados de trabajo en una sola recepción.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8e11dc918eb3c9085018d15b43819522cc8bebe3
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026880"
---
# <a name="only-one-label-is-printed-for-multiple-work-headers-on-a-single-receipt"></a><span data-ttu-id="0d812-103">Solo se imprime una etiqueta para varios encabezados de trabajo en una sola recepción</span><span class="sxs-lookup"><span data-stu-id="0d812-103">Only one label is printed for multiple work headers on a single receipt</span></span>

<span data-ttu-id="0d812-104">Número de KB: 4614667</span><span class="sxs-lookup"><span data-stu-id="0d812-104">KB number: 4614667</span></span>

## <a name="symptoms"></a><span data-ttu-id="0d812-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="0d812-105">Symptoms</span></span>

<span data-ttu-id="0d812-106">Se crean varios encabezados de trabajo para la misma matrícula de destino como parte de un evento de recepción de una sola aplicación de almacén.</span><span class="sxs-lookup"><span data-stu-id="0d812-106">Multiple work headers are created for the same target license plate as part of a single warehouse app receiving event.</span></span> <span data-ttu-id="0d812-107">Sin embargo, solo se imprime una etiqueta de matrícula cuando se recibe el producto.</span><span class="sxs-lookup"><span data-stu-id="0d812-107">However, only one license plate label is printed when the product is received.</span></span>

## <a name="resolution"></a><span data-ttu-id="0d812-108">Resolución</span><span class="sxs-lookup"><span data-stu-id="0d812-108">Resolution</span></span>

<span data-ttu-id="0d812-109">El sistema se está comportando según lo diseñado.</span><span class="sxs-lookup"><span data-stu-id="0d812-109">The system is behaving as designed.</span></span>

<span data-ttu-id="0d812-110">En el diseño actual, siempre se genera una sola etiqueta de matrícula, independientemente del número de combinaciones de encabezado de trabajo y línea de trabajo que existan.</span><span class="sxs-lookup"><span data-stu-id="0d812-110">In the current design, a single license plate label is always generated, regardless of the number of work header and work line combinations that exist.</span></span> <span data-ttu-id="0d812-111">La etiqueta generada incluye la información de una sola combinación.</span><span class="sxs-lookup"><span data-stu-id="0d812-111">The generated label includes the information for only one combination.</span></span>

<span data-ttu-id="0d812-112">Para solucionar este problema, asegúrese de que la creación del encabezado de trabajo siempre esté asignada a una sola matrícula de destino.</span><span class="sxs-lookup"><span data-stu-id="0d812-112">To work around this issue, make sure that work header creation is always mapped to just one target license plate.</span></span>
