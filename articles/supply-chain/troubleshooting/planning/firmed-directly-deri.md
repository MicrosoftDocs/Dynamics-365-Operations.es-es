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
# <a name="directly-derived-firmed-orders-are-processed-by-an-in-review-workflow"></a>Los pedidos confirmados derivados directamente se procesan mediante un flujo de trabajo en revisión

Número de KB: 4612450

## <a name="symptoms"></a>Síntomas

Los pedidos confirmados derivados directamente se procesan mediante un flujo de trabajo cuyo estado es *En revisión*.

## <a name="resolution"></a>Resolución

Cuando se activa el seguimiento de cambios, se asigna el estado *En revisión* a los pedidos confirmados derivados (pedidos de compra subcontratados). Por lo tanto, si se deriva un pedido de compra (un pedido de compra subcontratad), solo se envía a un flujo de trabajo. Si un pedido de compra es un pedido de compra planificad confirmado, se aprueba automáticamente para garantizar que el motor de planificación no cree nuevos pedidos planificados mientras el pedido de compra aún está en en estado *Borrador*.
