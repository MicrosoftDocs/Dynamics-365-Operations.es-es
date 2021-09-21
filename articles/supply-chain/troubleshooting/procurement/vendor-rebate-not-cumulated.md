---
title: Una devolución de proveedor no se acumula según las facturas
description: Una devolución de proveedor no se acumula según las facturas
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
ms.openlocfilehash: 9d4596a7351969bf181982a24ea1dcc6f5732831
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477567"
---
# <a name="a-vendor-rebate-isnt-cumulated-based-on-invoices"></a>Una devolución de proveedor no se acumula según las facturas

## <a name="symptoms"></a>Síntomas

Si las facturas que se registran tienen diferentes fechas de vencimiento, esas facturas no se reflejan en las devoluciones de proveedores que se generan a partir de ellas.

## <a name="resolution"></a>Resolución

La fecha de vencimiento al calcular el reembolso del proveedor. Considere la posibilidad de personalizar el sistema para que la fecha de vencimiento y la relación con la factura sean más evidentes con respecto al reembolso real del proveedor.
