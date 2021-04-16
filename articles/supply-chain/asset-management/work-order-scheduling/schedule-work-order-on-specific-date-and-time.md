---
title: Programar orden de trabajo en una fecha y hora específicas
description: En este tema se explica cómo programar una orden de trabajo en una fecha y hora específicas en Administración de activos.
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
ms.openlocfilehash: 827f4ca16341d29413f1b1d928965aa1919abf59
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822524"
---
# <a name="schedule-work-order-on-specific-date-and-time"></a><span data-ttu-id="65c48-103">Programar orden de trabajo en una fecha y hora específicas</span><span class="sxs-lookup"><span data-stu-id="65c48-103">Schedule work order on specific date and time</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="65c48-104">Si una orden de trabajo se debe programar en una fecha *y* hora específicas, puede anular el proceso de programación estándar en Administración de activos y crear una programación específica para una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="65c48-104">If a work order must be scheduled on a specific date *and* time, you can override the standard scheduling process in Asset Management and create a specific schedule for a work order.</span></span>

1. <span data-ttu-id="65c48-105">Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.</span><span class="sxs-lookup"><span data-stu-id="65c48-105">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="65c48-106">En la lista de órdenes de trabajo, haga clic en el identificador de la orden de trabajo en la columna **Orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="65c48-106">In the work order list, click on the Work order ID in the **Work order** column.</span></span>

3. <span data-ttu-id="65c48-107">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="65c48-107">Click **Edit**.</span></span>

4. <span data-ttu-id="65c48-108">En la ficha desplegable **Encabezado de la orden de trabajo**, inserte las fechas y las horas de inicio y finalización específicas en los campos **Inicio previsto** y **Finalización prevista**.</span><span class="sxs-lookup"><span data-stu-id="65c48-108">On the **Work order header** FastTab, insert start and end dates and times in the **Expected start** and **Expected end** fields.</span></span>

    ![Figura 1](media/05-work-order-scheduling.png)

5. <span data-ttu-id="65c48-110">En la pestaña **General**, haga clic en **Programación** para usar el proceso de programación estándar, o haga clic en **Distribuir** si desea asignar la orden de trabajo para un trabajador específico.</span><span class="sxs-lookup"><span data-stu-id="65c48-110">On the **General** tab, click **Schedule** to use the standard scheduling process, or click **Dispatch** if you want to assign the work order to a specific worker.</span></span>

6. <span data-ttu-id="65c48-111">Para anular cualquier reserva de capacidad existente a fin de garantizar que la orden de trabajo se programa en el período previsto, haga las selecciones como se muestra en la siguiente ilustración en el cuadro de diálogo **Programar orden de trabajo** > sección **Capacidad limitada**.</span><span class="sxs-lookup"><span data-stu-id="65c48-111">In order to override any existing capacity reservations to ensure that the work order is scheduled in the expected period, make the selections as shown in the figure below in the **Schedule work order** dialog > **Finite capacity** section.</span></span> <span data-ttu-id="65c48-112">Esto significa que el proceso de programación ignorará reservas de capacidad existentes porque la orden de trabajo debe comenzar en la hora de inicio prevista.</span><span class="sxs-lookup"><span data-stu-id="65c48-112">This means that the scheduling process will ignore existing capacity reservations because the work order must start on the expected start time.</span></span>

    ![Figura 2](media/06-work-order-scheduling.png)

7. <span data-ttu-id="65c48-114">Haga clic en **Aceptar** para comenzar la programación.</span><span class="sxs-lookup"><span data-stu-id="65c48-114">Click **OK** to start scheduling.</span></span>

8. <span data-ttu-id="65c48-115">Si el proceso de programación da lugar a reservas dobles, verá un mensaje en la pantalla y podrá ajustar las órdenes de trabajo relacionadas.</span><span class="sxs-lookup"><span data-stu-id="65c48-115">If the scheduling process results in double bookings, you will see a message on the screen, and you can adjust the related work orders.</span></span>

>[!NOTE]
><span data-ttu-id="65c48-116">Para programar un trabajador de mantenimiento para la orden de trabajo, dicho trabajador de mantenimiento debe estar disponible en la fecha y hora iniciales previstas.</span><span class="sxs-lookup"><span data-stu-id="65c48-116">In order to schedule a maintenance worker for the work order, that maintenance worker must be available at the expected start date and time.</span></span> <span data-ttu-id="65c48-117">La disponibilidad del trabajador se configura en el [calendario del trabajador](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md).</span><span class="sxs-lookup"><span data-stu-id="65c48-117">Worker availability is set up in the [worker calendar](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md).</span></span> 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]