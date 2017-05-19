---
title: "Pedidos de cliente híbridos"
description: "Un pedido híbrido de cliente es pedido único que contiene al mismo tiempo productos que el cliente puede llevarse y otros que pueden recogerse o enviarse después."
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
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 2bc0a8e59075b25ca48b09c1145820a2a604950e
ms.contentlocale: es-es
ms.lasthandoff: 04/25/2017


---

# <a name="hybrid-customer-orders"></a>Pedidos de cliente híbridos

[!include[banner](includes/banner.md)]


Un pedido híbrido de cliente es pedido único que contiene al mismo tiempo productos que el cliente puede llevarse y otros que pueden recogerse o enviarse después.

En Microsoft Dynamics 365 for Operations - Distribuidor, puede seleccionar enviar todos los productos o enviar solo los productos seleccionados de un pedido de cliente. Las líneas de productos marcadas para llevar a cabo se facturan automáticamente después de crear el pedido. Es lo mismo que sucede para un pedido que va a recoger después de crear el pedido. El importe pendiente de pago en pedidos híbridos se determina agregando el porcentaje de depósito en las líneas de recogida y envío de productos con el importe total de las líneas finalizadas. Para los pedidos híbridos, el sistema alterna entre el modo de pedido de cliente y el modo de pago en efectivo sin entrega a domicilio, de la siguiente manera:

-   Si todos los productos del carro se definen como **Ejecutar entrega**, el pedido se gestionará como una transacción al contado sin entrega a domicilio.
-   Si alguna de las líneas del carro está definida como **Recogida** o **Envío**, el pedido será gestionado como una transacción de pedido de cliente.

Si hay una línea del carro definida como **Recoger selección**, **Enviar selección** o **Ejecutar selección**, solo se definirá con ese método de entrega la línea específica del carro. En ese caso, el flujo descendente de la operación continúa de la forma habitual. Sin embargo, si se elige **Recoger selección**, **Enviar selección** o **Ejecutar selección** sin haber seleccionado ninguna línea, se abre una nueva página que enumera todas las líneas del carro. En esa pantalla, puede seleccionar varias líneas inmediatamente para definir el método de entrega. Al utilizar este método para seleccionar líneas, se sustituirá cualquier método de entrega anterior que se hubiera asignado a la línea.

<a name="see-also"></a>Consulte también
--------

[Visión general de pedidos de cliente](customer-orders-overview.md)




