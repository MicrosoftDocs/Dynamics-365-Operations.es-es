---
title: No puede facturar un pedido de ventas dirigido al cliente
description: Ya no puede facturar el pedido de ventas original y el pedido de compra de entrega directa original después de habilitar la opción Registrar factura automáticamente.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: SalesEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ab18a2a1dec4b70c55a55637b087c6b11023aa40
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026877"
---
# <a name="you-cant-invoice-a-customer-facing-sales-order"></a>No puede facturar un pedido de ventas dirigido al cliente

Número de KB: 4611793

## <a name="symptoms"></a>Síntomas

Ya no puede facturar el pedido de ventas original y el pedido de compra de entrega directa original después de habilitar la opción **Registrar factura automáticamente** en la página **Empresas vinculadas** de un proveedor.

## <a name="resolution"></a>Resolución

El comportamiento de sincronización para las facturas de pedidos de entrega directa y de empresas vinculadas está controlado y forzado por los parámetros que se describen en [Configuración de parámetros para registrar un pedido de empresas vinculadas](/dynamicsax-2012/appuser-itpro/set-up-parameters-to-post-an-intercompany-order).

Después de establecer esos parámetros, primero debe facturar el pedido de ventas de empresas vinculadas. A continuación, se sincronizarán los pedidos de ventas y los pedidos de compra originales.
