---
title: Los trabajos en curso finalizan cuando se notifica una cantidad parcial en el último trabajo
description: Cuando se usa el dispositivo de tarjeta de trabajo para informar una cantidad parcial en el último trabajo de una orden de producción, todos los trabajos anteriores que tienen el estado En curso se finalizan.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 11511d4ac7524facdd0d647e9bc38fe09c282be1
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477566"
---
# <a name="previous-in-progress-jobs-are-ended-when-reporting-partial-quantity-on-last-job"></a>Los trabajos anteriores en curso finalizan cuando se notifica una cantidad parcial en el último trabajo

## <a name="symptoms"></a>Síntomas

Cuando se usa el dispositivo de tarjeta de trabajo para informar una cantidad parcial en el último trabajo de una orden de producción, todos los trabajos anteriores de ese pedido que tienen el estado En curso se finalizan automáticamente.

## <a name="resolution"></a>Resolución

Este comportamiento se debe al diseño. Sobre la página **Valores predeterminados de órdenes de fabricación**, en la pestaña **Informar como terminado**, hay una opción que se llama **Ruta de la marca final**. Si este tema se establece en *Sí*, se publica un diario de la tarjeta de ruta cuando un trabajador usa el dispositivo de tarjeta de trabajo o el terminal de tarjeta de trabajo para informar la última operación. Este diario marca todas las operaciones como completadas y finaliza todos los trabajos de producción. Cuando la opción **Ruta de la marca final** está configurada en *Sí*, el sistema no tiene en cuenta el estado del trabajo que el trabajador seleccionó cuando informó la última operación. El sistema tampoco considera si el trabajador informa una cantidad total o parcial.
