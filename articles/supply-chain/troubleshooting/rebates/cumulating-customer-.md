---
title: La acumulación de devoluciones de clientes falla cuando se utilizan grupos de devoluciones de artículos
description: Cuando utiliza acuerdos de devoluciones para clientes en combinación con grupos de devolución de artículos, se calculan las devoluciones, pero la acumulación falla.
author: sherry-zheng
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PdsRebateTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 5222d5a52a34ecfa4a1eac96a2cb561f257f17ea
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026871"
---
# <a name="cumulation-of-customer-rebates-fails-when-item-rebate-groups-are-used"></a><span data-ttu-id="b4108-103">La acumulación de devoluciones de clientes falla cuando se utilizan grupos de devoluciones de artículos</span><span class="sxs-lookup"><span data-stu-id="b4108-103">Cumulation of customer rebates fails when item rebate groups are used</span></span>

<span data-ttu-id="b4108-104">Número de KB: 4611372</span><span class="sxs-lookup"><span data-stu-id="b4108-104">KB number: 4611372</span></span>

## <a name="symptoms"></a><span data-ttu-id="b4108-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="b4108-105">Symptoms</span></span>

<span data-ttu-id="b4108-106">Cuando utiliza acuerdos de devoluciones para clientes (del tipo *importe*) en combinación con grupos de devolución de artículos, se calculan las devoluciones, pero la acumulación falla.</span><span class="sxs-lookup"><span data-stu-id="b4108-106">When you use customer rebate agreements (of the *amount* type) in combination with item rebate groups, rebates are calculated, but cumulation fails.</span></span>

## <a name="resolution"></a><span data-ttu-id="b4108-107">Resolución</span><span class="sxs-lookup"><span data-stu-id="b4108-107">Resolution</span></span>

<span data-ttu-id="b4108-108">El sistema se está comportando según lo diseñado.</span><span class="sxs-lookup"><span data-stu-id="b4108-108">The system is behaving as designed.</span></span> <span data-ttu-id="b4108-109">Los grupos de artículos agrupan solo los artículos que tienen la misma condición de umbral.</span><span class="sxs-lookup"><span data-stu-id="b4108-109">Item groups group only items that have the same threshold condition.</span></span> <span data-ttu-id="b4108-110">La condición de devolución (umbral) se establece en función del importe de cada artículo, no del importe acumulado de cualquier artículo del grupo de artículos.</span><span class="sxs-lookup"><span data-stu-id="b4108-110">The rebate condition (threshold) is set against the amount for each item, not against the cumulated amount for any item in the item group.</span></span>
