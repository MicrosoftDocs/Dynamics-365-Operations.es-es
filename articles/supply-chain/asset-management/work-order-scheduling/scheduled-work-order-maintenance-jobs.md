---
title: Trabajos de mantenimiento de órdenes de trabajo programados
description: En este tema se explican los trabajos de mantenimiento de órdenes de trabajo programadas en Administración de activos.
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
ms.openlocfilehash: 4b3cc32d6ff263967c1ee843702c28968219ac33
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887191"
---
# <a name="scheduled-work-order-maintenance-jobs"></a><span data-ttu-id="12bfd-103">Trabajos de mantenimiento de órdenes de trabajo programados</span><span class="sxs-lookup"><span data-stu-id="12bfd-103">Scheduled work order maintenance jobs</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="12bfd-104">La página **Trabajos de mantenimiento de órdenes de trabajo programadas** se utiliza para obtener una visión general de las órdenes de trabajo asignadas a un recurso.</span><span class="sxs-lookup"><span data-stu-id="12bfd-104">The **Scheduled work order maintenance jobs** page is used to get an overview of the work orders allocated to a resource.</span></span> <span data-ttu-id="12bfd-105">Las órdenes de trabajo mediante los tipos de recursos "Recursos Humanos", "Herramienta" "Máquina" se muestran en la lista.</span><span class="sxs-lookup"><span data-stu-id="12bfd-105">Work orders using resource types "Human resources", "Tool", and "Machine" are shown in the list.</span></span> <span data-ttu-id="12bfd-106">La lista se puede utilizar para obtener una visión general de las órdenes de trabajo asignadas a un recurso específico.</span><span class="sxs-lookup"><span data-stu-id="12bfd-106">The list can be used to get an overview of work orders allocated to a specific resource.</span></span> <span data-ttu-id="12bfd-107">También puede usarla para buscar rápidamente una orden de trabajo asignada a un trabajador de mantenimiento que, por ejemplo, llamó esta mañana para decir que estaba enfermo y, a continuación, asignar rápidamente el trabajo a otro trabajador de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="12bfd-107">You can also use it to quickly find a work order allocated to a maintenance worker who, for example, called in sick this morning, and then quickly allocate another maintenance worker to the job.</span></span>

## <a name="view-scheduled-work-order-maintenance-jobs"></a><span data-ttu-id="12bfd-108">Ver trabajos de mantenimiento de órdenes de trabajo programadas</span><span class="sxs-lookup"><span data-stu-id="12bfd-108">View scheduled work order maintenance jobs</span></span>

1. <span data-ttu-id="12bfd-109">Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Trabajos de mantenimiento de órdenes de trabajo activas programadas**.</span><span class="sxs-lookup"><span data-stu-id="12bfd-109">Click **Asset management** > **Common** > **Work orders** > **Scheduled work order maintenance jobs**.</span></span> <span data-ttu-id="12bfd-110">Verá una lista de todas las órdenes de trabajo establecidas para el estado de ciclo de vida "Programada" o "En curso" de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="12bfd-110">You see a list of all work orders set to work order lifecycle state "Scheduled" or "In progress".</span></span>

2. <span data-ttu-id="12bfd-111">Puede ordenar la lista, por ejemplo, por trabajador de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="12bfd-111">You can sort the list, for example, by maintenance worker.</span></span> <span data-ttu-id="12bfd-112">También puede utilizar el filtro para restringir la lista a órdenes de trabajo asignadas a un determinado recurso o trabajador de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="12bfd-112">You can also use the filter to limit the list to display work orders allocated to a specific resource or maintenance worker.</span></span>

3. <span data-ttu-id="12bfd-113">Puede ver notas en la orden de trabajo y, si procede, agregar nuevas notas seleccionando una tarea de la orden de trabajo en la lista y haciendo clic en **Notas**.</span><span class="sxs-lookup"><span data-stu-id="12bfd-113">You can see notes on the work order and, if required, add new notes by selecting the work order job in the list and clicking **Notes**.</span></span>

4. <span data-ttu-id="12bfd-114">Si desea asignar un trabajador de mantenimiento a una orden de trabajo, seleccione la orden de trabajo en la lista y haga clic en **Orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="12bfd-114">If you want to allocate one maintenance worker to a work order, select the work order in the list, and click **Work order**.</span></span>

5. <span data-ttu-id="12bfd-115">Se abre la página **Orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="12bfd-115">The **Work order** page opens.</span></span> <span data-ttu-id="12bfd-116">Haga clic en **Distribuir** para programar la orden de trabajo a un determinado trabajador de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="12bfd-116">Click **Dispatch** to schedule the work order to a specific maintenance worker.</span></span>

>[!NOTE]
><span data-ttu-id="12bfd-117">Obtenga más información sobre la programación de varias órdenes de trabajo o de una orden de trabajo en [Programar órdenes de trabajo](../work-order-scheduling/schedule-work-orders.md) y [Distribuir orden de trabajo](../work-order-scheduling/dispatch-work-order.md).</span><span class="sxs-lookup"><span data-stu-id="12bfd-117">Read more about scheduling several work orders or one work order in [Schedule work orders](../work-order-scheduling/schedule-work-orders.md) and [Dispatch work order](../work-order-scheduling/dispatch-work-order.md).</span></span>

<span data-ttu-id="12bfd-118">La ilustración siguiente muestra un ejemplo de la página **Trabajos de mantenimiento de órdenes de trabajo programadas**.</span><span class="sxs-lookup"><span data-stu-id="12bfd-118">The figure below shows an example of the **Scheduled work order maintenance jobs** page.</span></span>

![Figura 1](media/07-work-order-scheduling.png)

