---
title: Los pedidos confirmados derivados directamente se procesan mediante un flujo de trabajo en revisión
description: Los pedidos confirmados derivados directamente se procesan mediante un flujo de trabajo cuyo estado es "en revisión".
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: d54985707d82df2b947a7cb615fc25f90aa31702
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026889"
---
# <a name="directly-derived-firmed-orders-are-processed-by-an-in-review-workflow"></a><span data-ttu-id="3f026-103">Los pedidos confirmados derivados directamente se procesan mediante un flujo de trabajo en revisión</span><span class="sxs-lookup"><span data-stu-id="3f026-103">Directly derived firmed orders are processed by an in-review workflow</span></span>

<span data-ttu-id="3f026-104">Número de KB: 4612450</span><span class="sxs-lookup"><span data-stu-id="3f026-104">KB number: 4612450</span></span>

## <a name="symptoms"></a><span data-ttu-id="3f026-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="3f026-105">Symptoms</span></span>

<span data-ttu-id="3f026-106">Los pedidos confirmados derivados directamente se procesan mediante un flujo de trabajo cuyo estado es *En revisión*.</span><span class="sxs-lookup"><span data-stu-id="3f026-106">Directly derived firmed orders are processed by a workflow that has a status of *In-review*.</span></span>

## <a name="resolution"></a><span data-ttu-id="3f026-107">Resolución</span><span class="sxs-lookup"><span data-stu-id="3f026-107">Resolution</span></span>

<span data-ttu-id="3f026-108">Cuando se activa el seguimiento de cambios, se asigna el estado *En revisión* a los pedidos confirmados derivados (pedidos de compra subcontratados).</span><span class="sxs-lookup"><span data-stu-id="3f026-108">When change tracking is enabled, a status of *In-review* is assigned to firmed derived orders (subcontract purchase orders).</span></span> <span data-ttu-id="3f026-109">Por lo tanto, si se deriva un pedido de compra (un pedido de compra subcontratad), solo se envía a un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3f026-109">Therefore, if a purchase order is derived (a subcontract purchase order), it's only submitted to a workflow.</span></span> <span data-ttu-id="3f026-110">Si un pedido de compra es un pedido de compra planificad confirmado, se aprueba automáticamente para garantizar que el motor de planificación no cree nuevos pedidos planificados mientras el pedido de compra aún está en en estado *Borrador*.</span><span class="sxs-lookup"><span data-stu-id="3f026-110">If a purchase order is a firmed planned purchase order, it's automatically approved to ensure that the planning engine doesn't create new planned orders while the purchase order is still in *Draft* status.</span></span>
