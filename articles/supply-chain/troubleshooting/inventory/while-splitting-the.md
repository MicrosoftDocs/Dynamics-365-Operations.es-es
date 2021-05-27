---
title: Cuando se divide una cantidad con peso capturado, se utiliza la cantidad mínima en lugar de la cantidad nominal
description: Cuando una cantidad con peso capturado se divide en lotes, el campo Cant. picking utiliza la cantidad mínima establecida para el artículo, no la cantidad nominal.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 185365ced5c4516d8fcdbdca88794d0078615888
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026890"
---
# <a name="when-a-catch-weight-quantity-is-split-minimum-quantity-is-used-instead-of-nominal-quantity"></a><span data-ttu-id="be3f9-103">Cuando se divide una cantidad con peso capturado, se utiliza la cantidad mínima en lugar de la cantidad nominal</span><span class="sxs-lookup"><span data-stu-id="be3f9-103">When a catch-weight quantity is split, minimum quantity is used instead of nominal quantity</span></span>

<span data-ttu-id="be3f9-104">Número de KB: 4612073</span><span class="sxs-lookup"><span data-stu-id="be3f9-104">KB number: 4612073</span></span>

## <a name="symptoms"></a><span data-ttu-id="be3f9-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="be3f9-105">Symptoms</span></span>

<span data-ttu-id="be3f9-106">Cuando una cantidad con peso capturado se divide en lotes, el campo **Cant. picking** utiliza la cantidad mínima establecida para el artículo, no la cantidad nominal.</span><span class="sxs-lookup"><span data-stu-id="be3f9-106">When a catch-weight quantity is being split into batches, the **Pick qty** field uses the minimum quantity that is set for the item, not the nominal quantity.</span></span>

## <a name="resolution"></a><span data-ttu-id="be3f9-107">Resolución</span><span class="sxs-lookup"><span data-stu-id="be3f9-107">Resolution</span></span>

<span data-ttu-id="be3f9-108">El sistema se está comportando según lo diseñado.</span><span class="sxs-lookup"><span data-stu-id="be3f9-108">The system is behaving as designed.</span></span> <span data-ttu-id="be3f9-109">El sistema utiliza la configuración de cantidad mínima de cada artículo para la selección.</span><span class="sxs-lookup"><span data-stu-id="be3f9-109">The system uses each item's minimum quantity setup for picking.</span></span>
