---
title: Una de las líneas ya se encuentra en una carga
description: Esta página explica por qué puede haber recibido el error "Una de las líneas ya está cargada. No se pudo entregar al almacén "y cómo resolver el problema.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0bdfaed005b9c58f7bd5f87dd6dffe648de47261
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477574"
---
# <a name="one-of-the-lines-is-already-on-a-load"></a>Una de las líneas ya se encuentra en una carga

## <a name="symptoms"></a>Síntomas

Al trabajar con construcción de carga y envíos, es posible que reciba el siguiente mensaje de error:

> Una de las líneas ya se encuentra en una carga. No se puede liberar al almacén.

Si crea cargas manualmente, o si configura el proceso de modo que las cargas ya estén creadas antes de que se produzca la entrada de la línea de la orden de venta, se supone que la liberación posterior se realizará manualmente y que se utilizarán la ruta y la clasificación de la carga. .

En otro escenario posible, está intentando hacer una liberación automática al almacén, pero el proceso de oleada no pudo crear trabajo. Por lo tanto, se sigue creando un envío o carga abiertos. Este envío o carga abiertos bloquea los intentos posteriores de liberar automáticamente el pedido hasta que elimine el envío o la carga abiertos, o reprocese manualmente la ola.

## <a name="resolution"></a>Resolución

Puede liberar desde la página de órdenes de venta, o la liberación automática puede realizarse desde la página de liberación de órdenes de venta, solo si no existe carga antes de la liberación al almacén. La carga se creará automáticamente después de que se procese la ola.
