---
title: Hybrid customer orders
description: "Un pedido de cliente como es un pedido único, que contiene los productos que se pueden realizar de la tienda durante el cliente, así como los productos que se cogidos enviados o más adelante."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261164
ms.assetid: 9d99a5b9-4662-499a-bece-3ea1d6092934
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 1ddfc050cef94f4a31f5858b84c89eadfa726b95
ms.lasthandoff: 03/31/2017


---

# <a name="hybrid-customer-orders"></a>Hybrid customer orders

Un pedido de cliente como es un pedido único, que contiene los productos que se pueden realizar de la tienda durante el cliente, así como los productos que se cogidos enviados o más adelante.

En Microsoft Dynamics 365 para las operaciones (al por menor, puede seleccionar realiza todos los productos o realiza los productos seleccionados para un pedido de cliente. Las líneas de productos marcadas como realizan automáticamente se facturan después de que se cree el pedido, ésta de forma similar son los mismos para un pedido que se debe realizarse después de que se cree el pedido. El importe debido en pedidos híbridas se determina a agregar el porcentaje de depósito en las líneas de productos de la selección y de envío con el importe completo de las líneas de finalización. Para pedidos híbridas, el sistema alternará entre el modo de entrega del cliente y el modo de las tiendas de ventas al contado modo siguiente:

-   Si todos los productos del carro se establecen ** realice la entrega **, el pedido se gestionará como una transacción de las tiendas de ventas al contado.
-   Si o todas las líneas en el carro se establecen a o ** ** selección o ** entrega de envío **, el pedido se gestionará como una transacción de pedido de cliente.

Si se selecciona una línea del carro y ** selección seleccionada, ** ** envío seleccionado, o ** ** Carry out ** seleccionada está seleccionada, solo la línea específica del carro se liquida con ese método de entrega. En ese caso, el flujo en sentido descendente desde la operación continúa como de costumbre. Sin embargo, si la selección ** ** seleccionado, ** envío seleccionado, o ** ** Carry out ** seleccionada se selecciona sin una línea del carro que es seleccionada, una nueva página abre que muestra todas las líneas del carro. En esa pantalla, puede seleccionar varias líneas inmediatamente para establecer el método de entrega. Cuando usa un método para seleccionar las líneas, cualquier método de entrega anterior que se haya asignado a la línea se sobrescribirá.

<a name="see-also"></a>Consulte también
--------

[] Visión general de los pedidos de cliente (customer-orders-overview.md)


