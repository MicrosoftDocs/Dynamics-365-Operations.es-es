---
title: Devolver artículos a través de múltiples pedidos y facturas de clientes
description: En este artículo se describe la funcionalidad que permite realizar devoluciones a través de múltiples pedidos y facturas de clientes en Dynamics 365 Commerce.
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
ms.openlocfilehash: 65ef700db5a81c49a962fd388af54e7811c088d2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890332"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a>Devolver artículos a través de múltiples pedidos y facturas de clientes

[!include [banner](includes/banner.md)]


Las devoluciones se pueden realizar a través de múltiples pedidos y facturas de clientes. 

## <a name="configure-commerce-to-support-returns-across-multiple-customer-order-and-invoices"></a>Configure Commerce para admitir devoluciones a través de múltiples pedidos y facturas de clientes

1. Vaya a **Parámetros de Commerce \> Pedidos de cliente**.
1. Active el parámetro **Permitir devoluciones para múltiples pedidos**. 

## <a name="process-returns"></a>Procesar devoluciones

Después de que el parámetro se active y los cambios se sincronicen en las tiendas, el cajero de la tienda puede seleccionar múltiples pedidos de ventas a un cliente para su devolución.

Cuando se seleccionan los pedidos, se mostrará una lista de todos los productos que se pueden devolver en todas las facturas para los pedidos. El cajero puede seleccionar los productos que se van a devolver. Se creará un único pedido de devolución para todos los productos seleccionados.
