---
title: Invertir el estado de una orden de producción
description: En este tema se describe cómo invertir el estado del pedido de producción.
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdParmStatusDecrease
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 70131
ms.assetid: b1e0df43-b388-4326-8fb7-501f30c89776
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7ca5a62b4509f0c7e49da94128e72eae5f35829e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "367326"
---
# <a name="reverse-the-production-order-status"></a>Invertir el estado de una orden de producción

[!include [banner](../includes/banner.md)]

En este tema se describe cómo invertir el estado del pedido de producción. 

Si invierte el estado de una orden de producción, el pedido y todas las operaciones asociadas a las rutas se revierten a un paso anterior del ciclo de vida de la producción. Por ejemplo, un pedido de producción tiene un estado de **Programado** y lo cambia de nuevo a **Creado**. En este caso, el sistema debe cambiar primero el estado a **Estimado**, que es el estado que precede inmediatamente a **Programado**. Después puede cambiar el estado al estado que desee, **Creado**. **Nota**: si el pedido ha alcanzado el estado **Notificar como terminado**, todavía puede invertirlo a un estado anterior. No obstante, debe volver a ejecutar la estimación y la programación de las operaciones o de los trabajos, o ambos tipos de programación, para actualizar la información del pedido. Este paso es obligatorio, porque las reservas del consumo de artículos restantes y el consumo de recursos de operaciones también se deben restablecer. En el resto de este artículo se explica lo que sucede al invertir el estado de un pedido de producción de las siguientes formas:

-   De **Estimado** a **Creado**
-   De **Programado** a **Estimado**
-   De **Liberado** a **Programado**
-   De **Iniciado** a **Liberado**

## <a name="from-estimated-to-created"></a>De Estimado a Creado
Cuando se invierte el estado de un pedido de producción de **Estimado** a **Creado**, se elimina el consumo de artículos que se calcula para los artículos de la lista de materiales (L. MAT.). Las transacciones de inventario de la línea de producción se eliminan y el campo **Estado de permanencia** en las líneas de L. MAT del pedido de producción se restablecen como **Finalizado**. Cuando se seleccionan las opciones **Compras derivadas** y **Producción derivada**, se eliminan los pedidos de compra o los pedidos de producción subyacentes. Si ha estimado los costes del pedido de producción o ha reservado manualmente los artículos para que se puedan usar en producción, estas transacciones se eliminan.

## <a name="from-scheduled-to-estimated"></a>De Programado a Estimado
Al invertir el estado de un pedido de producción de **Programado** a **Estimado**, las horas y las fechas iniciales y finales programadas se eliminan. Las reservas de capacidad realizadas durante la programación se eliminan, así como los trabajos creados durante la programación de trabajos. Se restablece toda la información registrada acerca de la programación de operaciones y la programación de trabajos en la página **Detalles del pedido de producción**.

## <a name="from-released-to-scheduled"></a>De Liberado a Programado
Al invertir el estado de un pedido de producción de **Liberado** a **Programado**, el único cambio que se produce es el valor del campo de estado.

## <a name="from-started-to-released"></a>De Iniciado a Liberado
Al invertir el estado de un pedido de producción de **Iniciado** a **Liberado**, todos los artículos notificados como terminados se invierten. Si el material se ha seleccionado o las entregas de entrada y salida se han realizado en producción, esta configuración también se invierte. El campo **Estado de permanencia** de las líneas de L. MAT del pedido de producción se cambia de **Finalizado** a **Consumo de materiales**. Si se ha registrado el tiempo o si han notificado las cantidades como terminadas para las operaciones de la ruta de producción, esta configuración se invertirá. El campo **Estado de permanencia** se cambia de **Finalizado** a **Consumo de ruta** en la ruta de producción. Se invierte la configuración de todos los artículos que se registran como en proceso o trabajo en curso. En la página **Detalles del pedido de producción**, se restablecen los campos que muestran una cantidad que se inició o se notificó como terminada. Las fechas para estas transacciones también se restablecen.



