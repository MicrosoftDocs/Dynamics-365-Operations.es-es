---
title: Devolver artículos a través de múltiples pedidos y facturas de clientes
description: En este tema se describe la funcionalidad que permite realizar devoluciones a través de múltiples pedidos y facturas de clientes en Dynamics 365 Commerce.
author: josaw1
ms.date: 08/27/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 4a64794a0e04516441fab628d441640e4d154b8d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796906"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a>Devolver artículos a través de múltiples pedidos y facturas de clientes

[!include [banner](includes/banner.md)]


En este artículo se describen dos características que optimizan las devoluciones de pedidos de clientes en varias facturas. 

## <a name="enable-refunds-over-multiple-captures"></a>Habilitar devoluciones en varias capturas

Esta característica permite varias devoluciones vinculadas con el mismo pedido de cliente. 

1. Vaya al espacio de trabajo **Administración de características** y busque **Habilitar devoluciones en varias capturas**.
2. Seleccione **Habilitar devoluciones en varios pedidos** y luego haga clic en **Habilitar**. 

## <a name="enable-proper-tax-calculation-for-returns-with-partial-quantity"></a>Habilitar el cálculo de impuestos correcto para devoluciones con cantidad parcial

Esta característica garantiza que cuando se devuelve un pedido con varias facturas, los impuestos serán, finalmente, iguales al importe de impuestos cargado originalmente. 

1. Vaya al espacio de trabajo **Administración de características** y busque **Habilitar el cálculo de impuestos correcto para devoluciones con cantidad parcial**.
2. Seleccione **Habilitar el cálculo de impuestos correcto para devoluciones con cantidad parcial** y luego haga clic en **Habilitar**. 


## <a name="process-returns"></a>Procesar devoluciones

Después de que estas características se activen y los cambios se sincronicen en las tiendas, el cajero de la tienda puede seleccionar múltiples pedidos de ventas a un cliente para su devolución.

Cuando se seleccionan los pedidos, se mostrará una lista de todos los productos que se pueden devolver en todas las facturas para los pedidos. El cajero puede seleccionar los productos que se van a devolver. Se creará un único pedido de devolución para todos los productos seleccionados.

Si el pedido se devuelve en su totalidad, la cantidad de impuestos devueltos al cliente será igual a la cantidad de impuestos cargada originalmente.



[!INCLUDE[footer-include](../includes/footer-banner.md)]