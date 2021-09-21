---
title: No se puede cancelar la reserva de inventario en una línea de pedido de venta
description: Si hay trabajo abierto contra una línea de ventas e intenta anular la reserva de inventario en la línea, recibe un error. Complete o elimine el trabajo para liberar la reserva.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 1a042065dc4cd637aff58e55cf16179b7022f6ca
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477533"
---
# <a name="cant-unreserve-inventory-on-a-sales-order-line"></a>No se puede cancelar la reserva de inventario en una línea de pedido de venta

## <a name="symptoms"></a>Síntomas

Si hay trabajo abierto contra una línea de pedido de ventas e intenta anular la reserva de inventario en esa línea, recibe el siguiente mensaje de error:

> Las reservas no se pueden quitar porque hay trabajo creado que depende de ellas.

## <a name="resolution"></a>Resolución

Investigar si existe trabajo de grupo de empaque abierto para llevar el artículo de una estación de empaque a otra ubicación (como *Baydoor*). Revise los registros en las páginas **Registro del historial de creación de trabajos** y **Detalles del trabajo** para determinar qué está reservando físicamente el inventario, y luego completar o eliminar el trabajo para liberar la reserva.
