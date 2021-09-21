---
title: El artículo RM no se puede reservar cuando se libera un pedido de producción
description: 'Al liberar una orden de producción, es posible que obtenga el error: "El artículo RM no se pudo reservar por completo". Asegúrese de que la cantidad completa esté disponible o reserve los artículos manualmente.'
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 528895252d661bb012f49190c15853989833064d
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477551"
---
# <a name="item-rm-cant-be-fully-reserved-when-a-production-order-is-released"></a>El artículo RM no se puede reservar por completo cuando se libera un pedido de producción

## <a name="symptoms"></a>Síntomas

Si no todas las partidas de la lista de materiales están disponibles físicamente cuando se libera una orden de producción a un almacén, **Liberar al almacén** la política está establecida en *Requiere reserva completa* en la orden de producción, recibirá el siguiente mensaje de error:

> El artículo RM no se pudo reservar por completo. Asegúrese de que la cantidad completa esté disponible o reserve los artículos manualmente si el campo Reserva en la línea de la lista de materiales está configurado como Manual o Iniciado. No se pudo liberar el pedido al almacén porque no se pudieron reservar determinados materiales.

## <a name="resolution"></a>Resolución

Este comportamiento es por diseño y funciona como se esperaba. Para solucionar este problema, siga las instrucciones proporcionadas en el mensaje de error: "Asegúrese de que la cantidad completa esté disponible o reserve los artículos manualmente si el campo Reserva en la línea de la lista de materiales está configurado como Manual o Iniciado".
