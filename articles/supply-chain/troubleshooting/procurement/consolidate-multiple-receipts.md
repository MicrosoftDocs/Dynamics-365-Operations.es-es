---
title: No puede consolidar varias recepciones de productos en un solo pedido de compra
description: No puede consolidar múltiples recepciones de productos en un solo pedido de compra si las diferentes líneas de recepciones de productos tienen fechas contables distintas.
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
ms.openlocfilehash: 485306279281ceb55a140526f4216af35574af42
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477493"
---
# <a name="you-cant-consolidate-multiple-product-receipts-into-a-single-purchase-order"></a>No puede consolidar varias recepciones de productos en un solo pedido de compra

## <a name="symptoms"></a>Síntomas

No puede consolidar múltiples recepciones de productos en un solo pedido de compra si las diferentes líneas de recepciones de productos tienen fechas contables distintas.

## <a name="resolution"></a>Resolución

En versiones anteriores de Dynamics 365 Supply Chain Management se permitía la consolidación en esta situación. Sin embargo, esta práctica es propensa a errores. La fecha contable en las líneas de pedido de compra que se crean no debe diferir de la fecha contable en las líneas de recepción de productos a partir de las cuales se crearon esas líneas de pedido de compra. (La fecha contable en las líneas del pedido de compra coincide con la fecha contable en el encabezado del pedido de compra). Por lo tanto, ya no se permite la consolidación de múltiples recepciones de productos en un solo pedido de compra.

La fecha contable se usa, por ejemplo, para reservas presupuestarias y reserva de gasto. Por lo tanto, debe conservarse durante la transición de la recepción del producto al pedido de compra.
