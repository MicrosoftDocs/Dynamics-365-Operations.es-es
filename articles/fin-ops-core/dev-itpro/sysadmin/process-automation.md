---
title: Automatización de procesos
description: En este tema se ofrece información sobre cómo la automatización de procesos permite una programación sencilla de los procesos que ejecutará el servidor de lotes.
author: RyanCCarlson2
manager: tonyafehr
ms.date: 08/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProcessScheduleSeries
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2020-06-30
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: afbef26cb7b37bafb34f12cc20a88fb4aea9f343
ms.sourcegitcommit: ad5b7676fc1213316e478afcffbfaee7d813f3bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "3885260"
---
# <a name="process-automation"></a><span data-ttu-id="7108f-103">Automatización de procesos</span><span class="sxs-lookup"><span data-stu-id="7108f-103">Process automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="7108f-104">La automatización de procesos permite una programación sencilla de los procesos que ejecutará el servidor de lotes.</span><span class="sxs-lookup"><span data-stu-id="7108f-104">Process automation allows simple scheduling of processes that will be run by the batch server.</span></span> <span data-ttu-id="7108f-105">La vista actualizada del calendario del trabajo programado permite a los usuarios finales ver y realizar acciones sobre el trabajo programado y completado.</span><span class="sxs-lookup"><span data-stu-id="7108f-105">The updated calendar view of the scheduled work allows end users to view and take action on scheduled and completed work.</span></span>

## <a name="administration"></a><span data-ttu-id="7108f-106">Administración</span><span class="sxs-lookup"><span data-stu-id="7108f-106">Administration</span></span>

<span data-ttu-id="7108f-107">La página de administración central para todas las automatizaciones de procesos se encuentra en el módulo de Gestión del sistema en el menú **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="7108f-107">The central administration page for all process automations is found in the System Administration module under the **Setup** menu.</span></span> <span data-ttu-id="7108f-108">En esta página se mostrarán todos los procesos automatizados (serie) que se configuran en el sistema.</span><span class="sxs-lookup"><span data-stu-id="7108f-108">This page will list all automated processes (series) that are set up in the system.</span></span> <span data-ttu-id="7108f-109">También le permitirá agregar nuevas automatizaciones de procesos directamente desde esta página.</span><span class="sxs-lookup"><span data-stu-id="7108f-109">It will also allow you to add new process automations directly from this page.</span></span> <span data-ttu-id="7108f-110">Después de configurar una serie, puede administrar cada serie de esta lista.</span><span class="sxs-lookup"><span data-stu-id="7108f-110">After a series is set up, you can manage each series from this list.</span></span> <span data-ttu-id="7108f-111">Puede optar por editar la serie completa, eliminarla, ver todas las repeticiones en una vista de lista o deshabilitar la serie si desea pausar el trabajo programado durante un período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="7108f-111">You can choose to edit the entire series, delete it, view all occurrences in a list view, or disable the series if you would like to pause the scheduled work for a while.</span></span> 

<span data-ttu-id="7108f-112">Cualquier proceso que esté deshabilitado en la administración de características no se mostrará cuando la característica esté deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="7108f-112">Any processes that are disabled in feature management won't show when the feature is disabled.</span></span> <span data-ttu-id="7108f-113">Además, el motor de programación de automatización de procesos no programará ninguna instancia ni procesos en segundo plano para una característica deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="7108f-113">Additionally, the process automation scheduling engine won't schedule any occurrences or background processes for a disabled feature.</span></span> <span data-ttu-id="7108f-114">Si se vuelve a habilitar la característica, las instancias programadas o los procesos en segundo plano del pasado se ejecutarán de inmediato.</span><span class="sxs-lookup"><span data-stu-id="7108f-114">Re-enabling the feature will cause any scheduled occurrences or background processes in the past to run immediately.</span></span>

## <a name="calendar-view"></a><span data-ttu-id="7108f-115">Vista de calendario</span><span class="sxs-lookup"><span data-stu-id="7108f-115">Calendar view</span></span>

<span data-ttu-id="7108f-116">Uno de las principales ventajas de la automatización de procesos es la capacidad de ver el trabajo programado en una vista de calendario sencilla.</span><span class="sxs-lookup"><span data-stu-id="7108f-116">One of the key benefits of process automation is the ability to see the scheduled work in a simple calendar view.</span></span>  <span data-ttu-id="7108f-117">Esta vista le permite ver de una vez el trabajo para una semana.</span><span class="sxs-lookup"><span data-stu-id="7108f-117">This view allows you to see work for a week at a time.</span></span> <span data-ttu-id="7108f-118">Verá esta vista en el lado derecho de la página **Automatización de procesos**.</span><span class="sxs-lookup"><span data-stu-id="7108f-118">You'll see this view on the right side of the **Process automation** page.</span></span> <span data-ttu-id="7108f-119">Se rellenará con el trabajo programado para la serie seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7108f-119">It will be populated with the scheduled work for the selected series.</span></span> 

<span data-ttu-id="7108f-120">[![Calendario de automatización de procesos](./media/CalendarView2.png)](./media/CalendarView2.png)</span><span class="sxs-lookup"><span data-stu-id="7108f-120">[![Process automation calendar](./media/CalendarView2.png)](./media/CalendarView2.png)</span></span>

## <a name="occurrence-changes"></a><span data-ttu-id="7108f-121">Cambios de repetición</span><span class="sxs-lookup"><span data-stu-id="7108f-121">Occurrence changes</span></span>

<span data-ttu-id="7108f-122">Cada repetición puede modificarse sin afectar otras repeticiones definidas por la serie que las originó.</span><span class="sxs-lookup"><span data-stu-id="7108f-122">Each occurrence can be modified without impacting other occurrences defined by the series that originated them.</span></span> <span data-ttu-id="7108f-123">Las repeticiones de trabajo programado se pueden editar desde la vista de calendario seleccionando el botón **Ver o editar** y seleccionando **Repetición**.</span><span class="sxs-lookup"><span data-stu-id="7108f-123">Occurrences of scheduled work can be edited from the calendar view by selecting the **View/Edit** button and selecting **Occurrence**.</span></span> <span data-ttu-id="7108f-124">Esta página le permite acceder a todas las configuraciones que se muestran originalmente en el asistente para la configuración de la serie y le brinda la posibilidad de realizar un cambio único para la repetición seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7108f-124">This page allows you access to all the settings originally shown in the series setup wizard and provides the ability to make a one-off change for the selected occurrence.</span></span> <span data-ttu-id="7108f-125">Una repetición de trabajo programado también se puede desactivar seleccionando el botón **Deshabilitar** de la vista de calendario.</span><span class="sxs-lookup"><span data-stu-id="7108f-125">An occurrence of scheduled work can also be turned off by selecting the **Disable** button from the calendar view.</span></span>

## <a name="developer-documentation"></a><span data-ttu-id="7108f-126">Documentación del desarrollador</span><span class="sxs-lookup"><span data-stu-id="7108f-126">Developer documentation</span></span>

<span data-ttu-id="7108f-127">El marco de automatización de procesos permite a los desarrolladores ampliar el marco de automatización de procesos.</span><span class="sxs-lookup"><span data-stu-id="7108f-127">The process automation framework allows developers to extend the process automation framework.</span></span> <span data-ttu-id="7108f-128">La documentación del [Marco de automatización de procesos](../process-automation/process-automation-framework.md) proporciona información sobre cómo puede crear procesos personalizados que deben ser ejecutados por el servidor por lotes programado con el asistente de automatización de procesos y que aparecen automáticamente en la vista de calendario.</span><span class="sxs-lookup"><span data-stu-id="7108f-128">The [Process automation framework](../process-automation/process-automation-framework.md) documentation provides information about how you can create custom processes that you require to be run by the batch server scheduled with the process automation wizard and appear in the calendar view automatically.</span></span>
