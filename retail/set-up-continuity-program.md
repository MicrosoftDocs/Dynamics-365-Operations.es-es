---
title: Configurar un programa de continuidad para un centro de llamadas
description: "En este artículo se describe cómo configurar un programa de continuidad para un centro de llamadas."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 16081
ms.assetid: 426a9be7-a931-4780-b372-e06f6083dd60
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: e32961f2a0e0e41715d98075cbc5777d256eb187
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-a-continuity-program-for-a-call-center"></a>Configurar un programa de continuidad para un centro de llamadas

[!include[banner](includes/banner.md)]


En este artículo se describe cómo configurar un programa de continuidad para un centro de llamadas.

En un programa de continuidad, también conocido como un programa de pedidos recurrentes, los clientes reciben envíos regulares de productos en función de una programación predefinida. Cada envío puede contener un producto diferente, como en el caso de un club del libro del mes, o se puede enviar repetidamente el mismo producto. Para configurar un programa de continuidad, debe completar las tareas siguientes:

1.  Establecer los parámetros de continuidad en la página **Parámetros del centro de llamadas**.
2.  Cree un programa de continuidad que especifique detalles como el multivencimiento, la sincronización de los envíos, y si la facturación se realiza por adelantado. También debe agregar una lista de productos incluidos en el programa de continuidad. Cada producto recibe un número de identificación de evento que se asigna de forma secuencial, empezando por 1. Los identificadores de evento determinan el orden en que se envían los productos.
    -   Si los clientes reciben un producto diferente en cada envío, los productos se envían en orden secuencial, en función de sus identificadores de evento y comenzando por el evento actual.
    -   Si los clientes reciben el mismo producto en cada envío, la lista solo contiene un producto con un id. de evento. El mismo evento se produce repetidamente. Puede especificar cuántas veces se repite cada evento.

3.  Cree un producto principal que represente el programa de continuidad que creó en la tarea 2. Si agrega este producto a un pedido de ventas, se abre la página **Continuidad**. Puede usar esa página para crear el pedido de continuidad real. El producto principal no especifica los productos individuales que el cliente recibe en cada envío.

Una vez haya configurado un programa de continuidad como se describe anteriormente, puede crear un pedido de continuidad para un cliente. Es posible que también tenga que realizar las siguientes tareas de mantenimiento adicionales.

-   **Actualizar el período del evento de continuidad actual**: configure un trabajo por lotes que indique al sistema cuál es el período actual del evento.
-   **Crear pedidos secundarios de continuidad**: cree pedidos secundarios de pedidos de continuidad principales.
-   **Procesar pagos de continuidad**: procese facturación y notificaciones para los pagos asociados a los pedidos de ventas de continuidad.
-   **Ampliar líneas de continuidad** (si es necesario): amplíe el número de veces que un evento de continuidad se puede repetir. La periodicidad de los envíos se puede ampliar más allá de límites que se establecieron en el campo **Umbral de repetición de continuidad** en los parámetros del centro de llamadas
-   **Realizar una actualización de continuidad** (si es necesario) : sincronice los cambios entre el programa de continuidad y los pedidos de ventas principales de continuidad.
-   **Cerrar pedidos y líneas principales de continuidad**: cierre pedidos de continuidad.





