---
title: Generar el trabajo de picking de inmediato al liberarse la carga
description: Si se debe generar trabajo inmediatamente cuando se libera la carga, debe configurar la plantilla de onda en consecuencia. Esta página le guía a través de los pasos.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: fdeb0b27f4d2c1a2cc9f8e0c4ba537cdce604bd2
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477542"
---
# <a name="picking-work-isnt-generated-immediately-when-outbound-load-is-released"></a>El trabajo de picking no se genera de inmediato al liberarse la carga saliente

## <a name="symptoms"></a>Síntomas

Usted crea una carga de salida utilizando una orden de transferencia o de venta y libera la carga al almacén. Sin embargo, observa que aún no se tiene que generar ningún trabajo de picking.

## <a name="resolution"></a>Resolución

Si se debe generar trabajo inmediatamente cuando se libera la carga, debe configurar la plantilla de onda en consecuencia. En la plantilla de oleada, configure las siguientes opciones para *Sí*:

- Automatizar la creación de oleadas
- Procesar oleada para su liberación al almacén
- Liberación automática de oleada
