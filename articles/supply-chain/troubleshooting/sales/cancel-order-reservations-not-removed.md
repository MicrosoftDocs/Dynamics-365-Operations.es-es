---
title: Las reservas no se pueden eliminar al cancelar un pedido
description: No puede cancelar un pedido de venta hasta que el trabajo asociado a él se cancele y se revierta. Para ello, siga estos tres pasos.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a8d947e64568246dba5eff3c21fd3920b6494b73
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477535"
---
# <a name="reservations-cannot-be-removed-when-canceling-an-order"></a>Las reservas no se pueden eliminar al cancelar un pedido

## <a name="symptoms"></a>Síntomas

Si el trabajo está asociado con una orden de venta e intenta cancelar esa orden, recibirá el siguiente mensaje de error:

> Las reservas no se pueden quitar porque hay trabajo creado que depende de ellas.

No puede cancelar el pedido de venta hasta que el trabajo asociado a él se cancele y se revierta. Este requisito se aplica incluso si el trabajo asociado con el pedido de ventas está cerrado.

## <a name="resolution"></a>Resolución

Para solucionar este problema, siga estos pasos:

1. Cancele el trabajo y vuelva a colocar el inventario en la ubicación deseada. Vaya a la carga relevante del pedido de ventas y seleccione **Reducir cantidad seleccionada** en la línea de carga o **Invertir el trabajo** en el panel de acciones.

    Ahora el trabajo tiene el estado *Cancelado* y se crea y procesa automáticamente un nuevo trabajo de movimiento de inventario para volver a colocar el inventario en la ubicación que se describió en el momento de la reversión.

2. Elimina la carga. También se elimina el envío.

3. Ahora debería poder ir al pedido de ventas y cancelarlo.
