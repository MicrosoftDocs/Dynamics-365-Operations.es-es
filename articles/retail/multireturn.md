---
title: Devolver artículos a través de múltiples pedidos y facturas de clientes
description: En este tema se describe la funcionalidad que permite devoluciones a través de múltiples pedidos y facturas de clientes en Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 03/05/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: c201311028b11121d626e93859a2b98497c047d1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565309"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a>Devolver artículos a través de múltiples pedidos y facturas de clientes

[!include [banner](includes/banner.md)]


En la versión 10.0 de Dynamics 365 for Finance and Operations, se pueden hacer devoluciones a través de múltiples pedidos y facturas, mientras que en las versiones anteriores a la 10.0, las devoluciones solo se podían procesar mediante una única factura al mismo tiempo. 

## <a name="configure-retail-to-support-returns-across-multiple-customer-order-and-invoices"></a>Configure Retail para admitir devoluciones a través de múltiples pedidos y facturas de clientes

1. Vaya a **Parámetros de Retail \> Pedidos de cliente**.
1. Active el parámetro **Permitir devoluciones para múltiples pedidos**. 

## <a name="process-returns"></a>Procesar devoluciones

Después de que el parámetro se active y los cambios se sincronicen en las tiendas, el cajero de la tienda puede seleccionar múltiples pedidos de ventas a un cliente para su devolución.

Cuando se seleccionan los pedidos, se mostrará una lista de todos los productos que se pueden devolver en todas las facturas para los pedidos. El cajero puede seleccionar los productos que se van a devolver. Se creará un único pedido de devolución para todos los productos seleccionados.
