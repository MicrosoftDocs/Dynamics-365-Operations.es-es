---
title: Automatización de procesos
description: En este tema se ofrece información sobre cómo la automatización de procesos permite una programación sencilla de los procesos que ejecutará el servidor de lotes.
author: RyanCCarlson2
manager: tonyafehr
ms.date: 06/24/2020
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
ms.openlocfilehash: 2ab4e7510ff98b9fbf0223096b905e9de47f52e1
ms.sourcegitcommit: 1833c1e07a32c8ad41e4a1516e78100ae04a2156
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "3508194"
---
# <a name="process-automation"></a><span data-ttu-id="ba0c3-103">Automatización de procesos</span><span class="sxs-lookup"><span data-stu-id="ba0c3-103">Process automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="ba0c3-104">La automatización de procesos permite una programación sencilla de los procesos que ejecutará el servidor de lotes.</span><span class="sxs-lookup"><span data-stu-id="ba0c3-104">Process automation allows simple scheduling of processes that will be run by the batch server.</span></span> <span data-ttu-id="ba0c3-105">La vista actualizada del calendario del trabajo programado permite a los usuarios finales ver y realizar acciones sobre el trabajo programado y completado.</span><span class="sxs-lookup"><span data-stu-id="ba0c3-105">The updated calendar view of the scheduled work allows end users to view and take action on scheduled and completed work.</span></span>

## <a name="administration"></a><span data-ttu-id="ba0c3-106">Administración</span><span class="sxs-lookup"><span data-stu-id="ba0c3-106">Administration</span></span>

<span data-ttu-id="ba0c3-107">La página de administración central para todas las automatizaciones de procesos se encuentra en el módulo de Gestión del sistema en el menú **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="ba0c3-107">The central administration page for all process automations is found in the System Administration module under the **Setup** menu.</span></span> <span data-ttu-id="ba0c3-108">En esta página se mostrarán todos los procesos automatizados (serie) que se configuran en el sistema.</span><span class="sxs-lookup"><span data-stu-id="ba0c3-108">This page will list all automated processes (series) that are set up in the system.</span></span> <span data-ttu-id="ba0c3-109">También le permitirá agregar nuevas automatizaciones de procesos directamente desde esta página.</span><span class="sxs-lookup"><span data-stu-id="ba0c3-109">It will also allow you to add new process automations directly from this page.</span></span> <span data-ttu-id="ba0c3-110">Después de configurar una serie, puede administrar cada serie de esta lista.</span><span class="sxs-lookup"><span data-stu-id="ba0c3-110">After a series is set up, you can manage each series from this list.</span></span> <span data-ttu-id="ba0c3-111">Puede optar por editar la serie completa, eliminarla, ver todas las repeticiones en una vista de lista o deshabilitar la serie si desea pausar el trabajo programado durante un período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="ba0c3-111">You can chose to edit the entire series, delete it, view all occurrences in a list view, or disable the series if you would like to pause the scheduled work for a period of time.</span></span> 

## <a name="calendar-view"></a><span data-ttu-id="ba0c3-112">Vista de calendario</span><span class="sxs-lookup"><span data-stu-id="ba0c3-112">Calendar view</span></span> 
<span data-ttu-id="ba0c3-113">Uno de las principales ventajas de la automatización de procesos es la capacidad de ver el trabajo programado en una vista de calendario sencilla.</span><span class="sxs-lookup"><span data-stu-id="ba0c3-113">One of the key benefits of process automation is the ability to see the scheduled work in a simple calendar view.</span></span>  <span data-ttu-id="ba0c3-114">Esta vista le permite ver de una vez el trabajo para una semana.</span><span class="sxs-lookup"><span data-stu-id="ba0c3-114">This view allows you to see work for a week at a time.</span></span> <span data-ttu-id="ba0c3-115">Verá esta vista en el lado derecho de la página **Automatización de procesos**.</span><span class="sxs-lookup"><span data-stu-id="ba0c3-115">You will see this view on the right side of the **Process automation** page.</span></span> <span data-ttu-id="ba0c3-116">Se rellenará con el trabajo programado para la serie seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ba0c3-116">It will be populated with the scheduled work for the selected series.</span></span> 

<span data-ttu-id="ba0c3-117">[![Calendario de automatización de procesos](./media/CalendarView2.png)](./media/CalendarView2.png)</span><span class="sxs-lookup"><span data-stu-id="ba0c3-117">[![Process automation calendar](./media/CalendarView2.png)](./media/CalendarView2.png)</span></span>

## <a name="occurrence-changes"></a><span data-ttu-id="ba0c3-118">Cambios de repetición</span><span class="sxs-lookup"><span data-stu-id="ba0c3-118">Occurrence changes</span></span>
<span data-ttu-id="ba0c3-119">Cada repetición puede modificarse sin afectar otras repeticiones definidas por la serie que las originó.</span><span class="sxs-lookup"><span data-stu-id="ba0c3-119">Each occurrence can be modified without impacting other occurrences defined by the series that originated them.</span></span> <span data-ttu-id="ba0c3-120">Las repeticiones de trabajo programado se pueden editar desde la vista de calendario seleccionando el botón **Ver o editar** y seleccionando **Repetición**.</span><span class="sxs-lookup"><span data-stu-id="ba0c3-120">Occurrences of scheduled work can be edited from the calendar view by selecting the **View/Edit** button and selecting **Occurrence**.</span></span> <span data-ttu-id="ba0c3-121">Esto le permite acceder a todas las configuraciones que se muestran originalmente en el asistente para la configuración de la serie y le brinda la posibilidad de realizar un cambio único para la repetición seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ba0c3-121">This allows you access to all the settings originally shown in the series setup wizard and provides the ability to make a one-off change for the selected occurrence.</span></span> <span data-ttu-id="ba0c3-122">Una repetición de trabajo programado también se puede desactivar seleccionando el botón **Deshabilitar** de la vista de calendario.</span><span class="sxs-lookup"><span data-stu-id="ba0c3-122">An occurrence of scheduled work can also be turned off by selecting the **Disable** button from the calendar view.</span></span> 

## <a name="developer-documentation"></a><span data-ttu-id="ba0c3-123">Documentación del desarrollador</span><span class="sxs-lookup"><span data-stu-id="ba0c3-123">Developer documentation</span></span> 
<span data-ttu-id="ba0c3-124">Actualmente se está escribiendo la documentación del desarrollador para permitir a los desarrolladores ampliar el marco de automatización de procesos.</span><span class="sxs-lookup"><span data-stu-id="ba0c3-124">Developer documentation is currently being written to allow developers to extend the process automation framework.</span></span> <span data-ttu-id="ba0c3-125">Esta documentación brindará información sobre cómo puede crear procesos personalizados que necesitan ser ejecutados por el servidor por lotes programado con el asistente de automatización de procesos y que aparecen automáticamente en la vista de calendario.</span><span class="sxs-lookup"><span data-stu-id="ba0c3-125">This documentation will provide information about how you can create custom processes that you require to be run by the batch server scheduled with the process automation wizard and appear in the calendar view automatically.</span></span>