---
title: La selección posterior no se respeta cuando los pedidos de producción se restablecen mediante un trabajo por lotes
description: Cuando utiliza un trabajo por lotes periódico para restablecer el estado de un pedido de producción, no se respetan las selecciones posteriores.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: e53198f427f4060421a4f0078277682c43db1320
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026875"
---
# <a name="late-selection-isnt-respected-when-production-orders-are-reset-via-a-batch-job"></a>La selección posterior no se respeta cuando los pedidos de producción se restablecen mediante un trabajo por lotes

Número de KB: 4614634

## <a name="symptoms"></a>Síntomas

Cuando utiliza un trabajo por lotes periódico para restablecer el estado de un pedido de producción, no se respetan las selecciones posteriores.

## <a name="resolution"></a>Resolución

El diseño actual no admite el uso de selecciones posteriores para el proceso *Restablecer estado*.
