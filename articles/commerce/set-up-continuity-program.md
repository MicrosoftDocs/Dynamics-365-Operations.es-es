---
title: Configurar programas de continuidad para centros de llamadas
description: En este artículo se describe cómo configurar un programa de continuidad para un centro de llamadas.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 16081
ms.assetid: 426a9be7-a931-4780-b372-e06f6083dd60
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 39c3e6d740bff2af27a2fba2ac4c406c01b43a87218fdc1dcfe094c147cd3de3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716159"
---
# <a name="set-up-continuity-programs-for-call-centers"></a>Configurar programas de continuidad para centros de llamadas

[!include [banner](includes/banner.md)]

En este artículo se describe cómo configurar un programa de continuidad para un centro de llamadas.

En un programa de continuidad, también conocido como un programa de pedidos recurrentes, los clientes reciben envíos regulares de productos en función de una programación predefinida. Cada envío puede contener un producto diferente, como en el caso de un club del libro del mes, o se puede enviar repetidamente el mismo producto. Para configurar un programa de continuidad, debe completar las tareas siguientes:

1. Establecer los parámetros de continuidad en la página **Parámetros del centro de llamadas**.
2. Cree un programa de continuidad que especifique detalles como el multivencimiento, la sincronización de los envíos, y si la facturación se realiza por adelantado. También debe agregar una lista de productos incluidos en el programa de continuidad. Cada producto recibe un número de identificación de evento que se asigna de forma secuencial, empezando por 1. Los identificadores de evento determinan el orden en que se envían los productos.

    - Si los clientes reciben un producto diferente en cada envío, los productos se envían en orden secuencial, en función de sus identificadores de evento y comenzando por el evento actual.
    - Si los clientes reciben el mismo producto en cada envío, la lista solo contiene un producto con un id. de evento. El mismo evento se produce repetidamente. Puede especificar cuántas veces se repite cada evento.

3. Cree un producto principal que represente el programa de continuidad que creó en la tarea 2. Si agrega este producto a un pedido de ventas, se abre la página **Continuidad**. Puede usar esa página para crear el pedido de continuidad real. El producto principal no especifica los productos individuales que el cliente recibe en cada envío.

Una vez haya configurado un programa de continuidad como se describe anteriormente, puede crear un pedido de continuidad para un cliente. Es posible que también tenga que realizar las siguientes tareas de mantenimiento adicionales.

- **Actualizar el período del evento de continuidad actual**: configure un trabajo por lotes que indique al sistema cuál es el período actual del evento.
- **Crear pedidos secundarios de continuidad**: cree pedidos secundarios de pedidos de continuidad principales.
- **Procesar pagos de continuidad**: procese facturación y notificaciones para los pagos asociados a los pedidos de ventas de continuidad.
- **Ampliar líneas de continuidad** (si es necesario): amplíe el número de veces que un evento de continuidad se puede repetir. La periodicidad de los envíos se puede ampliar más allá de límites que se establecieron en el campo **Umbral de repetición de continuidad** en los parámetros del centro de llamadas
- **Realizar una actualización de continuidad** (si es necesario) : sincronice los cambios entre el programa de continuidad y los pedidos de ventas principales de continuidad.
- **Cerrar pedidos y líneas principales de continuidad**: cierre pedidos de continuidad.


[!INCLUDE[footer-include](../includes/footer-banner.md)]