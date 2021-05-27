---
title: El pedido de compra planificado se crea cuando existe una compra dentro de los días negativos
description: Si el código de cobertura es mínimo o máximo, la optimización de la planificación crea un pedido de compra planificado cuando existe una compra dentro de los días negativos.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo,MpsIntegrationParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 826496c2de956ff949dd79ab8aa643053719bf75
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026887"
---
# <a name="planned-purchase-order-is-created-when-a-purchase-exists-within-negative-days"></a><span data-ttu-id="9929c-103">El pedido de compra planificado se crea cuando existe una compra dentro de los días negativos</span><span class="sxs-lookup"><span data-stu-id="9929c-103">Planned purchase order is created when a purchase exists within negative days</span></span>

<span data-ttu-id="9929c-104">Número de KB: 4614298</span><span class="sxs-lookup"><span data-stu-id="9929c-104">KB number: 4614298</span></span>

## <a name="symptoms"></a><span data-ttu-id="9929c-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="9929c-105">Symptoms</span></span>

<span data-ttu-id="9929c-106">Si el código de cobertura es *mínimo o máximo*, la optimización de la planificación crea un pedido de compra planificado cuando existe una compra dentro de los días negativos.</span><span class="sxs-lookup"><span data-stu-id="9929c-106">If the coverage code is *Min/max*, Planning Optimization creates a planned purchase order when a purchase exists within negative days.</span></span>

## <a name="resolution"></a><span data-ttu-id="9929c-107">Resolución</span><span class="sxs-lookup"><span data-stu-id="9929c-107">Resolution</span></span>

<span data-ttu-id="9929c-108">La optimización de la planificación no admite días negativos.</span><span class="sxs-lookup"><span data-stu-id="9929c-108">Planning Optimization doesn't support negative days.</span></span> <span data-ttu-id="9929c-109">Sin embargo, siempre garantiza que los pedidos planificados no se programarán dentro del plazo de entrega relativo a la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="9929c-109">However, it always ensures that planned orders won't be scheduled within the lead time relative to the current date.</span></span> <span data-ttu-id="9929c-110">Por ejemplo, el plazo de entrega de la compra es de 10 días y se espera que el pedido de compra llegue en ocho días a partir de hoy.</span><span class="sxs-lookup"><span data-stu-id="9929c-110">For example, the purchase lead time is 10 days, and a purchase order is expected to arrive eight days from today.</span></span> <span data-ttu-id="9929c-111">En este caso, el pedido de compra se utilizará como suministro para la demanda dentro de cinco días a partir de hoy.</span><span class="sxs-lookup"><span data-stu-id="9929c-111">In this case, the purchase order will be used as supply for demand that is five days from today.</span></span>

<span data-ttu-id="9929c-112">Por lo tanto, le recomendamos que ajuste sus plazos de entrega para cubrir todas (o casi todas) sus situaciones.</span><span class="sxs-lookup"><span data-stu-id="9929c-112">Therefore, we recommend that you adjust your lead times to cover all (or almost all) of your scenarios.</span></span>
