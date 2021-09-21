---
title: El valor de retraso no se actualiza cuando reprograma un pedido planificado
description: El valor de retraso no se actualiza cuando reprograma un pedido planificado
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 566702913774cf002ab38e367f690a479d968657
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477547"
---
# <a name="the-delay-value-isnt-updated-when-you-reschedule-a-planned-order"></a>El valor de retraso no se actualiza cuando reprograma un pedido planificado

## <a name="symptoms"></a>Síntomas

El valor de retraso no se actualiza cuando reprograma un pedido planificado.

## <a name="resolution"></a>Resolución

Para actualizar el retraso de los pedidos planificados, abra el cuadro de diálogo **Reprogramación** de la orden previsional. En la ficha desplegable **Explosión**, asegúrese de que la opción **Realizar explosión después de reprogramación** está establecida en *Sí*.
