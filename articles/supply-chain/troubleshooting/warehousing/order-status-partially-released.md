---
title: El estado del pedido sigue siendo parcialmente liberado después de facturarlo
description: En algunos casos, el estado de liberación de un pedido de cliente permanece Liberado parcialmente incluso después de que se ha facturado el pedido de cliente. Esta página explica por qué y una posible solución.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 8bfe7ecfd4beb6e77e8dd1e23ccd896d067bdb51
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477534"
---
# <a name="order-status-remains-partially-released-even-after-the-sales-order-is-invoiced"></a>El estado del pedido permanece Liberado parcialmente incluso después de facturar el pedido de cliente.

## <a name="symptoms"></a>Síntomas

Una orden de venta es una orden de entrega, pero uno o más artículos tienen un modo de entrega diferente. Después de facturar el pedido, todavía tiene un estado de liberación de *Liberado parcialmente*.

Por ejemplo, una orden de venta tiene dos artículos: uno para entrega y otro para recolección. Tanto la entrega como la recogida se han realizado. Por tanto, se han facturado ambas líneas. Sin embargo, el estado de la versión todavía se muestra como *Liberado parcialmente*, que es engañoso.

## <a name="workaround"></a>Solución alternativa

El estado de liberación se aplica solo a las líneas de pedido donde los artículos están habilitados para la gestión del almacén. Por lo tanto, el estado de publicación sigue siendo *Liberado parcialmente* en este escenario. Microsoft ha evaluado este problema y ha determinado que es una limitación de funciones. Se podría agregar una extensión como parte del albarán y el proceso de facturación para actualizar el estado de liberación.
