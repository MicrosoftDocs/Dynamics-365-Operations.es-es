---
title: Trabajo de picking bloqueado debido a trabajo de reabastecimiento sin terminar
description: El trabajo de picking puede estar bloqueado debido al trabajo de reabastecimiento dependiente. Complete el trabajo de reabastecimiento y luego procese el trabajo de selección.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 53b50d1e3e2d7bb64e78514affe80076ddcb9052
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477570"
---
# <a name="picking-work-cant-be-unblocked-because-of-unfinished-replenishment-work"></a>El trabajo de picking no puede desbloquearse debido al trabajo de reabastecimiento sin terminar

## <a name="symptoms"></a>Síntomas

Cuando se utiliza el reabastecimiento de demanda por oleada, el trabajo de picking puede bloquearse debido al trabajo de reabastecimiento dependiente. Si una ubicación de picking debe reabastecerse para satisfacer la demanda de la orden de origen, el sistema crea tanto el trabajo de reabastecimiento como el trabajo de picking. Sin embargo, bloquea el trabajo de recolección hasta que se completa el trabajo de reabastecimiento y recibe el siguiente mensaje de error:

> No se puede desbloquear el trabajo %1 porque tiene un trabajo de reabastecimiento sin terminar.

## <a name="resolution"></a>Resolución

Este comportamiento es intencional, porque la ubicación de recolección no tendrá suficiente inventario a menos que se complete el trabajo de reabastecimiento. Complete el trabajo de reabastecimiento y luego procese el trabajo de selección.
