---
title: El recibo de un pedido de compra no incluye todos los cargos
description: El recibo de un pedido de compra no incluye todos los cargos
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: bb567e00ef52269db0dc866148a37c73f0a9827c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477482"
---
# <a name="a-purchase-order-receipt-doesnt-include-all-charges"></a>El recibo de un pedido de compra no incluye todos los cargos

## <a name="symptoms"></a>Síntomas

Cuando recibe una orden de compra, no todos los cargos están incluidos en el recibo.

### <a name="reproduce-the-issue"></a>Reproducir el problema

El siguiente procedimiento muestra una manera de reproducir el problema.

1. En la página **Parámetros de adquisición y abastecimiento**, en la pestaña **Entrega**, asegúrese de que la opción **Generar cargos al recibir el producto** está establecida en *Sí*.
1. Cree un pedido de compra que incluya cargos.
1. Confirme el pedido de compra.
1. Reciba el pedido de compra.
1. Vea el total de recepción y compárelo con el total esperado.
1. Observe que no todos los cargos están incluidos en la recepción del pedido de compra.

## <a name="resolution"></a>Resolución

La resolución depende de la forma en que se hayan configurado los distintos cargos. Para obtener información sobre cómo configurar diversos cargos para cumplir con los requisitos, consulte la siguiente publicación de blog: [Contabilizar cargos varios en la recepción del producto](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).
