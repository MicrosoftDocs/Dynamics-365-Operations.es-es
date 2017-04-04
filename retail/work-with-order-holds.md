---
title: Retenciones de pedido
description: Este tema describe los pedidos en espera usando venta minorista y comercio en Dynamics AX.
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 1cb18e3275b8dcdf0a61531ee056995f6e8fbc8d
ms.lasthandoff: 03/31/2017


---

# <a name="order-holds"></a>Retenciones de pedido

Este tema describe los pedidos en espera usando venta minorista y comercio en Dynamics AX.

Un pedido puede estar en espera por varios motivos. Por ejemplo, puede poner un pedido en espera hasta que la dirección o el método de pago de un cliente se pueda comprobar o hasta que un director pueda revisar el límite de crédito del cliente. Durante el proceso de ventas, hay veces en que los pedidos de ventas deben ponerse en espera. Por ejemplo, un pedido de ventas podría ponerse en espera debido a problemas con el pago de un cliente, sospecha de fraude o porque un director debe revisar el pedido. Cuando un pedido de ventas se pone en espera, un código de retención del pedido se asigna al pedido de ventas para indicar el motivo de la retención. Los códigos de bloqueo del pedido de ventas se configuran en ** Ventas y marketing ** &gt; ** la configuración ** &gt; ** los pedidos de ventas ** &gt; ** el pedido mantiene códigos **. Un pedido de ventas se puede poner en espera manualmente a la hora de creación del pedido o posteriormente. Además, un pedido se puede poner en espera automáticamente, en función de las reglas de fraudes. Mientras que un pedido de ventas está en espera, puede que tenga que actualizarlo con más información. También puede que quiera desproteger el pedido de ventas a medida que continúa trabajando en él. Puede confirmar un pedido de ventas, se llega más adelante, e incluso anula el pago y envío de otro usuario mediante el banco de trabajo de bloqueo del pedido (** al por menor y comercio ** &gt; ** los clientes ** &gt; ** los bloqueos del pedido **). Cuando un pedido está listo para completar, debe quitar la retención antes de poder completar el proceso de pedido.


