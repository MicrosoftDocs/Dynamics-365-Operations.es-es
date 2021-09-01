---
title: Solucionar problemas de reabastecimiento de almacenes
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con reabastecimiento de almacenes en Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 251dc174d52d754a0c488d5becf63f1a43f9bd30034036d10086c9803060b5a0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6758409"
---
# <a name="troubleshoot-warehouse-replenishment"></a>Solucionar problemas de reabastecimiento de almacenes

[!include [banner](../includes/banner.md)]

Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con reabastecimiento de almacenes en Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-work-1-cannot-be-unblocked-because-it-has-unfinished-replenishment-work"></a>Recibo el siguiente mensaje de error: "El Id. de trabajo %1 no se puede desbloquear porque tiene un trabajo de reabastecimiento sin terminar".

### <a name="issue-description"></a>Descripción del problema

El trabajo de picking está bloqueado debido al trabajo de reabastecimiento dependiente.

### <a name="issue-resolution"></a>Solución del problema

Cuando utiliza el reabastecimiento de demanda de oleada, si una ubicación de picking debe reabastecerse para satisfacer la demanda de la orden de origen, el sistema crea tanto el trabajo de reabastecimiento como el trabajo de picking. Sin embargo, bloquea el trabajo de picking hasta que se completa el trabajo de reabastecimiento. Este comportamiento es intencional, porque la ubicación de recolección no tendrá suficiente inventario a menos que se complete el trabajo de reabastecimiento. Complete el trabajo de reabastecimiento y luego procese el trabajo de selección.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]