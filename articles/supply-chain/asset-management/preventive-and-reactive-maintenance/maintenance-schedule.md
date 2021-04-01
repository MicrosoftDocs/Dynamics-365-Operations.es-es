---
title: Programa de mantenimiento
description: En este tema se explica el programa de mantenimiento en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectCalendarCreateWO, EntAssetObjectCalendarListPagePoolsOpen, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePreviewPart, EntAssetObjectCalendarEdit, EntAssetObjectCalendarAdjust, EntAssetObjectCalendarDiscard, EntAssetObjectCalendarInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 89938a4c5fd9a520c6582215a438670f73085228
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5252951"
---
# <a name="maintenance-schedule"></a><span data-ttu-id="3c558-103">Programa de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="3c558-103">Maintenance schedule</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="3c558-104">El programa de mantenimiento contiene una lista de todos los planes de mantenimiento preventivo, solicitudes de mantenimiento y rondas de mantenimiento que se van a realizar. Puede que algunas líneas de programación se hayan convertido en órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3c558-104">The maintenance schedule contains a list of all the expected preventive maintenance plans, maintenance requests, and maintenance rounds to be carried out. Some schedule lines may have been converted to work orders.</span></span>

<span data-ttu-id="3c558-105">Las cuatro vistas del programa de mantenimiento son ligeramente diferentes, según las líneas del programa de mantenimiento que desee ver.</span><span class="sxs-lookup"><span data-stu-id="3c558-105">The four maintenance schedule views are slightly different, depending on which maintenance schedule lines you want to see.</span></span>

| <span data-ttu-id="3c558-106">Elemento de menú</span><span class="sxs-lookup"><span data-stu-id="3c558-106">Menu item</span></span>                  | <span data-ttu-id="3c558-107">Descripción del contenido</span><span class="sxs-lookup"><span data-stu-id="3c558-107">Description of contents</span></span>                                                                                                                                             |
|----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="3c558-108">Todo el programa de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="3c558-108">All maintenance schedule</span></span>       | <span data-ttu-id="3c558-109">Se muestran todas las líneas del programa de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="3c558-109">All maintenance schedule lines are shown.</span></span>     |
| <span data-ttu-id="3c558-110">Mi programación de activos</span><span class="sxs-lookup"><span data-stu-id="3c558-110">My asset schedule</span></span>        | <span data-ttu-id="3c558-111">En esta lista se muestran todas las líneas del programa de mantenimiento que contienen activos instalados en ubicaciones técnicas con las que está relacionado como trabajador (configuradas en [Trabajadores y grupos de trabajadores de mantenimiento](../setup-for-objects/workers-and-worker-groups.md)).</span><span class="sxs-lookup"><span data-stu-id="3c558-111">All maintenance schedule lines containing assets installed on functional locations to which you are related as a worker (set up in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md)) are shown in this list.</span></span> |
| <span data-ttu-id="3c558-112">Abrir líneas del programa de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="3c558-112">Open maintenance schedule lines</span></span> | <span data-ttu-id="3c558-113">En esta lista se muestran las líneas del programa de mantenimiento con el estado "Creado" (lo que significa que aún no se han convertido en una orden de trabajo o se han descartado).</span><span class="sxs-lookup"><span data-stu-id="3c558-113">Maintenance schedule lines with status "Created" - meaning they have not yet been converted to a work order or discarded - are shown in this list.</span></span>                                            |
| <span data-ttu-id="3c558-114">Abrir grupos de programas de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="3c558-114">Open maintenance schedule pools</span></span> | <span data-ttu-id="3c558-115">En esta lista se muestran las líneas del programa de mantenimiento relacionadas con un conjunto de órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3c558-115">Maintenance schedule lines related to a work order pool are shown in this list.</span></span>                                                                                                                  |

>[!NOTE]
><span data-ttu-id="3c558-116">Si una línea del programa de mantenimiento se incluye en varios grupos de órdenes de trabajo (consulte [Grupos de órdenes de trabajo](../work-orders/work-order-pools.md)), se muestra un registro para cada grupo en **Grupos del programa de mantenimiento abiertos**.</span><span class="sxs-lookup"><span data-stu-id="3c558-116">If a maintenance schedule line is included in several work order pools (refer to [Work order pools](../work-orders/work-order-pools.md)), one record is shown for each pool in **Open maintenance schedule pools**.</span></span> <span data-ttu-id="3c558-117">Esto se hace para optimizar las opciones de filtrado en grupos de órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3c558-117">This is done to optimize filtering options on work order pools.</span></span>

<span data-ttu-id="3c558-118">Para abrir un programa de mantenimiento:</span><span class="sxs-lookup"><span data-stu-id="3c558-118">To open a maintenance schedule:</span></span>

1. <span data-ttu-id="3c558-119">Haga clic en **Administración de activos** > **Común** > **Programa de mantenimiento** > **Todo el programa de mantenimiento** o **Líneas del programa de mantenimiento abiertas** o **Grupos del programa de mantenimiento abiertos**.</span><span class="sxs-lookup"><span data-stu-id="3c558-119">Click **Asset management** > **Common** > **Maintenance schedule** > **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools**.</span></span>

2. <span data-ttu-id="3c558-120">Para actualizar el programa de mantenimiento, haga clic en **Plan de mantenimiento** o **Rondas de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="3c558-120">To update the maintenance schedule, click **Maintenance plan** or **Maintenance rounds**.</span></span> 

3. <span data-ttu-id="3c558-121">Puede editar una línea del programa de mantenimiento seleccionándola y haciendo clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3c558-121">You can edit a maintenance schedule line by selecting it and clicking **Edit**.</span></span> <span data-ttu-id="3c558-122">Por ejemplo, puede actualizar fácilmente el nivel de servicio o el trabajador responsable del trabajo.</span><span class="sxs-lookup"><span data-stu-id="3c558-122">For example, you can easily update the service level or the worker responsible for the job.</span></span> <span data-ttu-id="3c558-123">Solo puede editar las líneas del programa de mantenimiento que aún no se han conectado a una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3c558-123">You can only edit maintenance schedule lines that have not yet been connected to a work order.</span></span>

4. <span data-ttu-id="3c558-124">Puede eliminar una línea del programa de mantenimiento seleccionándola en la página de lista y haciendo clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="3c558-124">You can delete a maintenance schedule line by selecting it in the list page and clicking **Delete**.</span></span>

5. <span data-ttu-id="3c558-125">Puede descartar una línea del programa de mantenimiento seleccionándola en la página de lista y haciendo clic en **Descartar**.</span><span class="sxs-lookup"><span data-stu-id="3c558-125">You can discard a maintenance schedule line by selecting it in the list page and clicking **Discard**.</span></span> <span data-ttu-id="3c558-126">Esta función resulta útil si, por ejemplo, un activo tiene un plan de mantenimiento de 2000 km y un plan de mantenimiento de 10 000 km.</span><span class="sxs-lookup"><span data-stu-id="3c558-126">This function is useful if, for example, an asset has a 2,000 km maintenance plan and a 10,000 km maintenance plan.</span></span> <span data-ttu-id="3c558-127">Después, es posible que desee descartar la línea creada del plan de mantenimiento de 2000 km cuando coincide con 10 000 km, 20 000 km, 30 000 km, etc.</span><span class="sxs-lookup"><span data-stu-id="3c558-127">Then, you may want to discard the line created from the 2,000 km maintenance plan when it coincides with 10,000 km, 20,000 km, 30,000 km, and so on.</span></span> <span data-ttu-id="3c558-128">Si descarta una línea del programa de mantenimiento relacionada con un plan de mantenimiento, esa línea nunca volverá a aparecer cuando se programe ese plan de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="3c558-128">If you discard a maintenance schedule line related to a maintenance plan, that line will never again appear when that maintenance plan is scheduled.</span></span>

6. <span data-ttu-id="3c558-129">Si desea que todas las líneas seleccionadas se incluyan en el mismo conjunto de órdenes de trabajo, puede seleccionar una serie de líneas del programa de mantenimiento en **Todo el programa de mantenimiento** y hacer clic en **Conjunto de órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="3c558-129">You can select a number of maintenance schedule lines in **All maintenance schedule** and click **Work order pool**, if you want all selected lines to be included in the same work order pool.</span></span>

7. <span data-ttu-id="3c558-130">Puede seleccionar una serie de líneas del programa de mantenimiento en **Todo el programa de mantenimiento** o **Líneas del programa de mantenimiento abiertas** o **Grupos del programa de mantenimiento abiertos** y hacer clic en **Ajustar programa** si desea realizar los mismos ajustes en varias líneas.</span><span class="sxs-lookup"><span data-stu-id="3c558-130">You can select a number of maintenance schedule lines in **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools** and click **Adjust schedule** if you want to make the same adjustments on several lines.</span></span> <span data-ttu-id="3c558-131">Puede cambiar las fechas previstas de inicio y finalización, el nivel de servicio y el trabajador o grupo de trabajadores responsable del mantenimiento relacionado con las líneas del programa de mantenimiento seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="3c558-131">You can change expected start and end dates, service level, and the responsible maintenance worker group or responsible maintenance worker related to the selected maintenance schedule lines.</span></span>

- <span data-ttu-id="3c558-132">Si una línea del programa de mantenimiento se ha relacionado con una orden de trabajo, el id. de la orden de trabajo se mostrará en el campo **Orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="3c558-132">When a maintenance schedule line has been related to a work order, the work order ID will be displayed in the **Work order** field.</span></span>  
- <span data-ttu-id="3c558-133">En la vista de detalles **Todos los activos** > ficha desplegable **Planes de mantenimiento del activo**, puede seleccionar los planes de mantenimiento para el activo.</span><span class="sxs-lookup"><span data-stu-id="3c558-133">In **All assets** details view > **Asset maintenance plans** FastTab, you can select maintenance plans for the asset.</span></span> <span data-ttu-id="3c558-134">Más adelante, si elimina una línea del plan de mantenimiento relacionada con un activo en **Todos los activos**, también elimina automáticamente todas las líneas del programa de mantenimiento con el estado "Creado" que se crearon a partir del plan de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="3c558-134">Later, if you delete a maintenance plan line related to an asset in **All assets**, you also automatically delete all maintenance schedule lines with status "Created" that have been created based on that maintenance plan.</span></span> <span data-ttu-id="3c558-135">Consulte también [Crear un activo](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="3c558-135">See also [Create an asset](../objects/create-an-object.md).</span></span>

<span data-ttu-id="3c558-136">La ilustración siguiente muestra la página de lista **Todo el programa de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="3c558-136">The illustration below shows the **All maintenance schedule** list page.</span></span>

![Figura 1](media/16-preventive-maintenance.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]