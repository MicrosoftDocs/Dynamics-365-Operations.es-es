---
title: Configurar avisos de fraude
description: "En este tema se explica cómo configurar reglas para avisar a los representantes de servicio al cliente de la existencia de información potencialmente fraudulenta al procesar pedidos. También puede definir códigos específicos que puede usar para poner en espera los pedidos sospechosos automática o manualmente."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: fabb7ee23e90feca818bebfa29c7048987193e4c
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-fraud-alerts"></a>Configurar avisos de fraude

En este tema se explica cómo configurar reglas para avisar a los representantes de servicio al cliente de la existencia de información potencialmente fraudulenta al procesar pedidos. También puede definir códigos específicos que puede usar para poner en espera los pedidos sospechosos automática o manualmente. 

Antes de configurar y usar reglas de comprobación de fraudes, debe habilitar la comprobación de fraudes y definir los valores básicos de comprobación de fraudes en los parámetros del centro de llamadas. Existen dos tipos de reglas de fraude:

-   **Reglas estáticas** usa un valor específico, como un número de teléfono que está en la lista negra.
-   **Reglas dinámicas** puede estar compuesto de variables y de condiciones.

Antes de crear una regla dinámica, debe crear las variables y condiciones que definen a quién se aplica la regla y cuándo se debe aplicar la regla. Por ejemplo, desea crear una regla para requerir que cuando el cliente 1202 realice un pedido de ventas por valor de 1.000,00 o más, el pedido de ventas se deba poner en espera hasta que se pueda comprobar el pago del cliente. En este caso, las variables son el cliente 1202 y un total de 1.000,00 del pedido. La condición especifica de que si el cliente 1202 configura un pedido, y el importe total del pedido es igual a o mayor de 1.000,00, el pedido de ventas debe estar en espera hasta que el pago del cliente pueda ser verificado.


