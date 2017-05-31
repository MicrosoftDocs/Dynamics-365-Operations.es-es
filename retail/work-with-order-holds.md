---
title: Retenciones de pedido
description: Este tema describe los pedidos en espera usando venta minorista y comercio en Dynamics AX.
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 5e18a488fed92de3278b438af67ae72fdbe229b4
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="order-holds"></a>Retenciones de pedido

[!include[banner](includes/banner.md)]


Este tema describe los pedidos en espera usando venta minorista y comercio en Dynamics AX.

Un pedido puede estar en espera por varios motivos. Por ejemplo, puede poner un pedido en espera hasta que la dirección o el método de pago de un cliente se pueda comprobar o hasta que un director pueda revisar el límite de crédito del cliente. Durante el proceso de ventas, hay veces en que los pedidos de ventas deben ponerse en espera. Por ejemplo, un pedido de ventas podría ponerse en espera debido a problemas con el pago de un cliente, sospecha de fraude o porque un director debe revisar el pedido. Cuando un pedido de ventas se pone en espera, un código de retención del pedido se asigna al pedido de ventas para indicar el motivo de la retención. Los códigos de espera del pedido de ventas se configuran en **Ventas y marketing** &gt; **Configuración** &gt; **Pedidos de ventas** &gt; **Códigos de espera de pedidos**. Un pedido de ventas se puede poner en espera manualmente a la hora de creación del pedido o posteriormente. Además, un pedido se puede poner en espera automáticamente, en función de las reglas de fraudes. Mientras que un pedido de ventas está en espera, puede que tenga que actualizarlo con más información. También puede que quiera desproteger el pedido de ventas a medida que continúa trabajando en él. Puede desproteger un pedido de ventas, volver a protegerlo e incluso anular la desprotección de otro usuario mediante el banco de trabajo de espera del pedido (**Venta minorista y comercio** &gt; **Clientes** &gt; **Pedidos en espera**). Cuando un pedido está listo para completar, debe quitar la retención antes de poder completar el proceso de pedido.




