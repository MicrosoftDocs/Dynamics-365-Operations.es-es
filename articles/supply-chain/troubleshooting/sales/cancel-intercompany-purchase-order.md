---
title: No se puede cancelar un pedido de compra de empresas vinculadas que está vinculado a un pedido de ventas
description: En la versión 10.0.13 y las versiones posteriores de Microsoft Dynamics 365 Supply Chain Management podrá cancelar un pedido de compra de empresas vinculadas que esté vinculado a un pedido de ventas.
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
ms.openlocfilehash: 5041ef377d9bf2c21e191c3cf1950f47eeba8555
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477511"
---
# <a name="cant-cancel-an-intercompany-purchase-order-thats-linked-to-a-sales-order"></a>No se puede cancelar un pedido de compra de empresas vinculadas que está vinculado a un pedido de ventas

## <a name="symptoms"></a>Síntomas

Si intenta cancelar una orden de compra de empresas vinculadas que está vinculada a una orden de venta, es posible que reciba el siguiente mensaje de error:

> No se puede reducir la cantidad, ya que la cantidad de actualización restante cambia el signo.

## <a name="resolution"></a>Resolución

Este problema se corrigió en Microsoft Dynamics 365 Supply Chain Management versión 10.0.13. Desde esta versión y las versiones posteriores podrá cancelar un pedido de compra de empresas vinculadas que esté vinculado a un pedido de ventas.
