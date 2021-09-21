---
title: La cancelación del resto de la entrega mueve la orden de compra a un estado Confirmado
description: Si se cancela un remanente de entrega en un pedido de compra donde la administración de cambios está activada, el pedido de compra pasa a un estado Confirmado
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 1d8b331bc5699487dff3491d65daa36293f3212f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477536"
---
# <a name="cancelling-delivery-remainder-moves-purchase-order-to-a-confirmed-state"></a>La cancelación del resto de la entrega mueve la orden de compra a un estado Confirmado

## <a name="symptoms"></a>Síntomas

Para un pedido de compra sujeto a la administración de cambios, si el único cambio que se solicita es la cancelación de un remanente de entrega en una o más de las líneas, el pedido de compra pasará directamente al estado *Confirmado* cuando se apruebe, y no se creará ningún diario.

## <a name="resolution"></a>Resolución

La cancelación de un remanente de entrega no afecta el contenido del diario de confirmación. Esta funcionalidad debe usarse cuando la línea se ha recibido parcialmente y la calidad restante debe cancelarse en el paso del proceso después de que se haya confirmado el pedido de compra con el proveedor.

Si esto tuviera que reflejarse en la confirmación del pedido de compra, la cantidad debe ajustarse en la línea del pedido de compra para que se requiera la confirmación. Como alternativa, si no se ha recibido nada en la línea, se puede quitar la cantidad. En este caso, se requerirá una reconfirmación.
