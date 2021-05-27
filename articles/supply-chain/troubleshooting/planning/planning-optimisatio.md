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
# <a name="planned-purchase-order-is-created-when-a-purchase-exists-within-negative-days"></a>El pedido de compra planificado se crea cuando existe una compra dentro de los días negativos

Número de KB: 4614298

## <a name="symptoms"></a>Síntomas

Si el código de cobertura es *mínimo o máximo*, la optimización de la planificación crea un pedido de compra planificado cuando existe una compra dentro de los días negativos.

## <a name="resolution"></a>Resolución

La optimización de la planificación no admite días negativos. Sin embargo, siempre garantiza que los pedidos planificados no se programarán dentro del plazo de entrega relativo a la fecha actual. Por ejemplo, el plazo de entrega de la compra es de 10 días y se espera que el pedido de compra llegue en ocho días a partir de hoy. En este caso, el pedido de compra se utilizará como suministro para la demanda dentro de cinco días a partir de hoy.

Por lo tanto, le recomendamos que ajuste sus plazos de entrega para cubrir todas (o casi todas) sus situaciones.
