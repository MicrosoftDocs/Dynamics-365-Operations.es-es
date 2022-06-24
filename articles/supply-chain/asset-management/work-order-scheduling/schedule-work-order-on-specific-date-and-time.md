---
title: Programar orden de trabajo en una fecha y hora específicas
description: En este artículo se explica cómo programar una orden de trabajo en una fecha y hora específicas en Administración de activos.
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ec7e300f60f76aaa467238d7a2c2a199fdeafeed
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857935"
---
# <a name="schedule-work-order-on-specific-date-and-time"></a>Programar orden de trabajo en una fecha y hora específicas

[!include [banner](../../includes/banner.md)]

 

Si una orden de trabajo se debe programar en una fecha *y* hora específicas, puede anular el proceso de programación estándar en Administración de activos y crear una programación específica para una orden de trabajo.

1. Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.

2. En la lista de órdenes de trabajo, haga clic en el identificador de la orden de trabajo en la columna **Orden de trabajo**.

3. Haga clic en **Editar**.

4. En la ficha desplegable **Encabezado de la orden de trabajo**, inserte las fechas y las horas de inicio y finalización específicas en los campos **Inicio previsto** y **Finalización prevista**.

    ![Figura 1.](media/05-work-order-scheduling.png)

5. En la pestaña **General**, haga clic en **Programación** para usar el proceso de programación estándar, o haga clic en **Distribuir** si desea asignar la orden de trabajo para un trabajador específico.

6. Para anular cualquier reserva de capacidad existente a fin de garantizar que la orden de trabajo se programa en el período previsto, haga las selecciones como se muestra en la siguiente ilustración en el cuadro de diálogo **Programar orden de trabajo** > sección **Capacidad limitada**. Esto significa que el proceso de programación ignorará reservas de capacidad existentes porque la orden de trabajo debe comenzar en la hora de inicio prevista.

    ![Figura 2.](media/06-work-order-scheduling.png)

7. Haga clic en **Aceptar** para comenzar la programación.

8. Si el proceso de programación da lugar a reservas dobles, verá un mensaje en la pantalla y podrá ajustar las órdenes de trabajo relacionadas.

>[!NOTE]
>Para programar un trabajador de mantenimiento para la orden de trabajo, dicho trabajador de mantenimiento debe estar disponible en la fecha y hora iniciales previstas. La disponibilidad del trabajador se configura en el [calendario del trabajador](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md). 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]