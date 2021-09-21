---
title: El nombre de entrega no se sincroniza después de cambiar la dirección de entrega de un pedido de compra.
description: Después de cambiar la dirección de entrega en el encabezado de un pedido de compra, no se sincroniza el nombre de entrega
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
ms.openlocfilehash: 588d1ef6250d249aa4fc9da4f5125e9a34c0255f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477492"
---
# <a name="the-delivery-name-isnt-synced-after-changing-a-purchase-order-delivery-address"></a>El nombre de entrega no se sincroniza después de cambiar la dirección de entrega de un pedido de compra.

## <a name="symptoms"></a>Síntomas

La dirección en el encabezado de un pedido de compra se actualiza a una dirección que no es una dirección de entrega. Aunque la dirección se actualiza en el pedido de compra, el nombre de entrega no se actualiza según la dirección actualizada.

## <a name="resolution"></a>Resolución

Este comportamiento se debe al diseño. La dirección seleccionada debe clasificarse como dirección de entrega. De lo contrario, el nombre de entrega no se actualiza en función de la dirección seleccionada.
