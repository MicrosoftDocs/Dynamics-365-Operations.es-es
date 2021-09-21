---
title: Error al cambiar el estado de Notificado como terminado a Finalizado
description: Puede recibir un error al cambiar el estado de un pedido de producción de Notificado como terminado a Finalizado. Esta página explica cómo mitigar el problema.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 744637f5cccffe44b85f77c1a9df2034012fac40
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477530"
---
# <a name="error-when-changing-status-of-production-order-from-reported-as-finished-to-end"></a>Error al cambiar el estado del pedido de producción de Notificado como terminado a Finalizado

## <a name="symptoms"></a>Síntomas

Cuando el estado de una orden de producción cambia de Reportado como terminado a Finalizado, recibe uno de los siguientes mensajes de error:

> Actualizar conflicto. El coste estándar no coincide con el valor del inventario financiero después de la actualización.

> Se ha producido un error crítico en la función InventCostMovement.checkVariance.

## <a name="cause"></a>Causa

Este problema se produce porque otro proceso cambió los datos subyacentes. El proceso intentará actualizar los datos hasta cinco veces. Si el conflicto persiste después de cinco intentos, recibirá uno de los mensajes anteriores.

## <a name="resolution"></a>Resolución

Este comportamiento se debe al diseño. Para mitigar el problema, reanude el trabajo por lotes. Debería terminar de funcionar.

Si el trabajo por lotes falla constantemente después de reanudarlo, verifique que la precisión de redondeo para la moneda predeterminada del libro mayor cumpla con el redondeo que se aplica a los valores en la tabla InventSum. Si la precisión de redondeo se ha cambiado a un valor no compatible, probablemente deba volver a cambiarlo a un valor compatible. Buscar **ModifiedDateTime**. En este caso, el valor normalmente mostrará que la precisión de redondeo se cambió recientemente.
