---
title: Programar orden de trabajo en una fecha y hora específicas
description: En este tema se explica cómo programar una orden de trabajo en una fecha y hora específicas en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0f818c4c3b669cc94e37cba1e3571c57b5c0dd1b
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887374"
---
# <a name="schedule-work-order-on-specific-date-and-time"></a><span data-ttu-id="84415-103">Programar orden de trabajo en una fecha y hora específicas</span><span class="sxs-lookup"><span data-stu-id="84415-103">Schedule work order on specific date and time</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="84415-104">Si una orden de trabajo se debe programar en una fecha *y* hora específicas, puede anular el proceso de programación estándar en Administración de activos y crear una programación específica para una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="84415-104">If a work order must be scheduled on a specific date *and* time, you can override the standard scheduling process in Asset Management and create a specific schedule for a work order.</span></span>

1. <span data-ttu-id="84415-105">Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.</span><span class="sxs-lookup"><span data-stu-id="84415-105">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="84415-106">En la lista de órdenes de trabajo, haga clic en el identificador de la orden de trabajo en la columna **Orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="84415-106">In the work order list, click on the Work order ID in the **Work order** column.</span></span>

3. <span data-ttu-id="84415-107">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="84415-107">Click **Edit**.</span></span>

4. <span data-ttu-id="84415-108">En la ficha desplegable **Encabezado de la orden de trabajo**, inserte las fechas y las horas de inicio y finalización específicas en los campos **Inicio previsto** y **Finalización prevista**.</span><span class="sxs-lookup"><span data-stu-id="84415-108">On the **Work order header** FastTab, insert start and end dates and times in the **Expected start** and **Expected end** fields.</span></span>

![Figura 1](media/05-work-order-scheduling.png)

5. <span data-ttu-id="84415-110">En la pestaña **General**, haga clic en **Programación** para usar el proceso de programación estándar, o haga clic en **Distribuir** si desea programar la orden de trabajo para un trabajador específico.</span><span class="sxs-lookup"><span data-stu-id="84415-110">On the **General** tab, click **Schedule** to use the standard scheduling process, or click **Dispatch** if you want to schedule the work order to a specific worker.</span></span>

6. <span data-ttu-id="84415-111">Para anular cualquier reserva de capacidad existente a fin de garantizar que la orden de trabajo se programa en el período previsto, haga las selecciones como se muestra en la siguiente ilustración en el cuadro de diálogo **Programar orden de trabajo** > sección **Capacidad limitada**.</span><span class="sxs-lookup"><span data-stu-id="84415-111">In order to override any existing capacity reservations to ensure that the work order is scheduled in the expected period, make the selections as shown in the figure below in the **Schedule work order** dialog > **Finite capacity** section.</span></span> <span data-ttu-id="84415-112">Esto significa que el proceso de programación ignorará reservas de capacidad existentes porque la orden de trabajo debe comenzar en la hora de inicio prevista.</span><span class="sxs-lookup"><span data-stu-id="84415-112">This means that the scheduling process will ignore existing capacity reservations because the work order must start on the expected start time.</span></span>

![Figura 2](media/06-work-order-scheduling.png)

7. <span data-ttu-id="84415-114">Haga clic en **Aceptar** para comenzar la programación.</span><span class="sxs-lookup"><span data-stu-id="84415-114">Click **OK** to start scheduling.</span></span>

8. <span data-ttu-id="84415-115">Si el proceso de programación da lugar a reservas dobles, verá un mensaje en la pantalla y podrá ajustar las órdenes de trabajo relacionadas.</span><span class="sxs-lookup"><span data-stu-id="84415-115">If the scheduling process results in double bookings, you will see a message on the screen, and you can adjust the related work orders.</span></span>

>[!NOTE]
><span data-ttu-id="84415-116">Para programar un trabajador de mantenimiento para la orden de trabajo, dicho trabajador de mantenimiento debe estar disponible en la fecha y hora iniciales previstas.</span><span class="sxs-lookup"><span data-stu-id="84415-116">In order to schedule a maintenance worker for the work order, that maintenance worker must be available at the expected start date and time.</span></span> <span data-ttu-id="84415-117">La disponibilidad del trabajador se configura en el [calendario del trabajador](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md).</span><span class="sxs-lookup"><span data-stu-id="84415-117">Worker availability is set up in the [worker calendar](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md).</span></span> 

