---
title: Diseñar la interfaz de ejecución de la planta de producción
description: Este tema describe cómo diseñar el contenido de la interfaz de usuario para cada configuración.
author: johanhoffmann
manager: tfehr
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 81c5c83128bb81523dee6ede549eece7b0d80e30
ms.sourcegitcommit: d9d1ddce6a334ade8b32b5ea3ac4c1e1a8f72715
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2020
ms.locfileid: "4664281"
---
# <a name="design-the-production-floor-execution-interface"></a><span data-ttu-id="34e7c-103">Diseñar la interfaz de ejecución de la planta de producción</span><span class="sxs-lookup"><span data-stu-id="34e7c-103">Design the production floor execution interface</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="34e7c-104">Puede diseñar el contenido de la interfaz de usuario para cada configuración utilizada por la interfaz de ejecución de la planta de producción.</span><span class="sxs-lookup"><span data-stu-id="34e7c-104">You can design the content of the user interface for each configuration used by the production floor execution interface.</span></span> <span data-ttu-id="34e7c-105">Por ejemplo, es posible que los trabajadores de una celda de trabajo necesiten poder abrir las instrucciones de trabajo en el piso de producción, mientras que en otra celda de trabajo, las instrucciones no son necesarias.</span><span class="sxs-lookup"><span data-stu-id="34e7c-105">For example, workers in one work cell might need to be able to open job instructions on the production floor, while in another work cell, instructions are not needed.</span></span> <span data-ttu-id="34e7c-106">En ese caso, se deben crear dos configuraciones, una con un botón para abrir documentos adjuntos y otra sin este botón.</span><span class="sxs-lookup"><span data-stu-id="34e7c-106">In that case, two configurations should be created, one with a button for opening document attachments and one without this button.</span></span>

## <a name="design-a-tab"></a><span data-ttu-id="34e7c-107">Diseñar una pestaña</span><span class="sxs-lookup"><span data-stu-id="34e7c-107">Design a tab</span></span>

<span data-ttu-id="34e7c-108">En la página **Configurar la ejecución del piso de producción**, puede crear y configurar pestañas seleccionando **Fichas de diseño** en el Panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="34e7c-108">On the **Configure production floor execution** page, you can create and configure tabs by selecting **Design tabs** on the Action Pane.</span></span>

<span data-ttu-id="34e7c-109">Cada pestaña está dividida en cuatro secciones, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="34e7c-109">Each tab is divided into four sections, as shown in the following illustration.</span></span>

<span data-ttu-id="34e7c-110">![Diseño de pestaña](media/pfe-tab-layout.png "Diseño de pestaña")</span><span class="sxs-lookup"><span data-stu-id="34e7c-110">![Tab layout](media/pfe-tab-layout.png "Tab layout")</span></span>

<span data-ttu-id="34e7c-111">Los siguientes elementos se muestran en la ilustración:</span><span class="sxs-lookup"><span data-stu-id="34e7c-111">The following elements are shown in the illustration:</span></span>

1. <span data-ttu-id="34e7c-112">Barra de herramientas principal</span><span class="sxs-lookup"><span data-stu-id="34e7c-112">Primary toolbar</span></span>
1. <span data-ttu-id="34e7c-113">Barra de herramientas secundaria</span><span class="sxs-lookup"><span data-stu-id="34e7c-113">Secondary toolbar</span></span>
1. <span data-ttu-id="34e7c-114">Vista principal</span><span class="sxs-lookup"><span data-stu-id="34e7c-114">Main view</span></span>
1. <span data-ttu-id="34e7c-115">Vista detallada</span><span class="sxs-lookup"><span data-stu-id="34e7c-115">Detailed view</span></span>

<span data-ttu-id="34e7c-116">Para crear y configurar una nueva pestaña, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="34e7c-116">To create and configure a new tab, follow these steps:</span></span>

1. <span data-ttu-id="34e7c-117">Vaya a **Control de producción &gt; Ejecución de fabricación &gt; Dispositivo de tarjetas de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="34e7c-117">Go to **Production control &gt; Setup &gt; Manufacturing execution**.</span></span>

1. <span data-ttu-id="34e7c-118">Seleccione **Fichas de diseño** en el Panel de acciones para abrir la página **Fichas de diseño**.</span><span class="sxs-lookup"><span data-stu-id="34e7c-118">Select **Design tabs** on the Action Pane to open the **Design tabs** page.</span></span>

    <span data-ttu-id="34e7c-119">![Página de fichas de diseño](media/pfe-design-tabs.png "Página de fichas de diseño")</span><span class="sxs-lookup"><span data-stu-id="34e7c-119">![The Design tabs page](media/pfe-design-tabs.png "The Design tabs page")</span></span>

1. <span data-ttu-id="34e7c-120">En el panel Acciones, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="34e7c-120">Select **New** on the Action Pane.</span></span>

1. <span data-ttu-id="34e7c-121">Realice los siguientes ajustes en el encabezado de la página:</span><span class="sxs-lookup"><span data-stu-id="34e7c-121">Make the following settings in the header of the page:</span></span>

    - <span data-ttu-id="34e7c-122">**Nombre de la pestaña** - Especifique un nombre para la pestaña.</span><span class="sxs-lookup"><span data-stu-id="34e7c-122">**Tab name** - Specify a name for the tab.</span></span>
    - <span data-ttu-id="34e7c-123">**Vista principal** - Seleccione entre las dos listas de trabajos predefinidas (*Trabajos activos* o *Todos los trabajos*).</span><span class="sxs-lookup"><span data-stu-id="34e7c-123">**Main view** - Select between the two pre-defined job lists (*Active jobs* or *All jobs*).</span></span>
    - <span data-ttu-id="34e7c-124">**Vista de detalles** - Seleccione entre un valor en blanco o **Detalles del trabajo**.</span><span class="sxs-lookup"><span data-stu-id="34e7c-124">**Details view** - Select between a blank value or **Job details**.</span></span> <span data-ttu-id="34e7c-125">Si selecciona el valor en blanco, no habrá una vista detallada en la pestaña. Si selecciona **Detalles del trabajo**, la vista detallada contendrá una descripción detallada del trabajo seleccionado en la lista de trabajos en la vista principal.</span><span class="sxs-lookup"><span data-stu-id="34e7c-125">If you select the blank value, there will be no detailed view in the tab. If you select **Job details**, the detailed view will contain a detailed description of the job selected in the job list in the main view.</span></span>

1. <span data-ttu-id="34e7c-126">En la sección **Barra de herramientas principal**, elija qué botones deben estar disponibles en la barra de herramientas principal.</span><span class="sxs-lookup"><span data-stu-id="34e7c-126">In the **Primary toolbar** section, choose which buttons should be available in the primary toolbar.</span></span> <span data-ttu-id="34e7c-127">La columna **Acciones disponibles** muestra una lista de todos los botones que se pueden agregar.</span><span class="sxs-lookup"><span data-stu-id="34e7c-127">The **Available actions** column shows a list of all the buttons that can be added.</span></span> <span data-ttu-id="34e7c-128">Las columnas **Acciones seleccionadas** muestran una lista de todos los botones que están incluidos en la configuración actual.</span><span class="sxs-lookup"><span data-stu-id="34e7c-128">The **Selected actions** columns shows a list of all the buttons that are included in the current configuration.</span></span> <span data-ttu-id="34e7c-129">Utilice los botones entre las columnas para mover los elementos seleccionados entre las columnas según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="34e7c-129">Use the buttons between the columns to move selected items between the columns as needed.</span></span> <span data-ttu-id="34e7c-130">Utilice los botones arriba y abajo junto a la columna **Acciones seleccionadas** para controlar el orden en que se presentan los botones en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="34e7c-130">Use the up and down buttons next to the **Selected actions** column to control the order in which the buttons are presented in the user interface.</span></span>

1. <span data-ttu-id="34e7c-131">En la sección **Barra de herramientas** **secundaria**, elija qué botones deben estar disponibles en la barra de herramientas secundaria.</span><span class="sxs-lookup"><span data-stu-id="34e7c-131">In the **Secondary** **toolbar** section, choose which buttons should be available in the secondary toolbar.</span></span> <span data-ttu-id="34e7c-132">La columna **Acciones disponibles** muestra una lista de todos los botones que se pueden agregar.</span><span class="sxs-lookup"><span data-stu-id="34e7c-132">The **Available actions** column shows a list of all the buttons that can be added.</span></span> <span data-ttu-id="34e7c-133">Las columnas **Acciones seleccionadas** muestran una lista de todos los botones que están incluidos en la configuración actual.</span><span class="sxs-lookup"><span data-stu-id="34e7c-133">The **Selected actions** columns shows a list of all the buttons that are included in the current configuration.</span></span> <span data-ttu-id="34e7c-134">Utilice los botones entre las columnas para mover los elementos seleccionados entre las columnas según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="34e7c-134">Use the buttons between the columns to move selected items between the columns as needed.</span></span> <span data-ttu-id="34e7c-135">Utilice los botones arriba y abajo junto a la columna **Acciones seleccionadas** para controlar el orden en que se presentan los botones en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="34e7c-135">Use the up and down buttons next to the **Selected actions** column to control the order in which the buttons are presented in the user interface.</span></span>

## <a name="associate-a-tab-with-a-configuration"></a><span data-ttu-id="34e7c-136">Asociar una pestaña a una configuración</span><span class="sxs-lookup"><span data-stu-id="34e7c-136">Associate a tab with a configuration</span></span>

<span data-ttu-id="34e7c-137">Una vez que haya diseñado todas las pestañas que necesita, puede asociarlas con una configuración.</span><span class="sxs-lookup"><span data-stu-id="34e7c-137">After you designed all the tabs you need, you can associate them with a configuration.</span></span>

1. <span data-ttu-id="34e7c-138">Vaya a **Control de producción &gt; Configuración &gt; Configurar ejecución de planta de producción**.</span><span class="sxs-lookup"><span data-stu-id="34e7c-138">Go to **Production control &gt; Setup &gt; Configure production floor execution**.</span></span>

    <span data-ttu-id="34e7c-139">![Configurar la ejecución de planta de producción](media/pfe-config-prod-floor-execution.png "Configurar la ejecución de planta de producción")</span><span class="sxs-lookup"><span data-stu-id="34e7c-139">![Configure production floor execution](media/pfe-config-prod-floor-execution.png "Configure production floor execution")</span></span>

1. <span data-ttu-id="34e7c-140">En la ficha desplegable **Selección de ficha**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="34e7c-140">On the **Tab selection** FastTab, select **Add**.</span></span>

1. <span data-ttu-id="34e7c-141">Se agrega una nueva fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="34e7c-141">A new row is added to the grid.</span></span> <span data-ttu-id="34e7c-142">Para esta nueva fila, seleccione el nombre de una pestaña que desea agregar a la configuración.</span><span class="sxs-lookup"><span data-stu-id="34e7c-142">For this new row, select the name of a tab that you want to add to the configuration.</span></span>

1. <span data-ttu-id="34e7c-143">Continúe agregando pestañas adicionales según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="34e7c-143">Continue to add additional tabs as needed.</span></span>

1. <span data-ttu-id="34e7c-144">Utilice los botones **Subir** y **Bajar** de la barra de herramientas para organizar las pestañas según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="34e7c-144">Use the **Move up** and **Move down** buttons on the toolbar to arrange the tabs as needed.</span></span> <span data-ttu-id="34e7c-145">Las pestañas se mostrarán de izquierda a derecha en el orden que se muestra en la captura de pantalla anterior (la pestaña en la parte superior se muestra a la izquierda).</span><span class="sxs-lookup"><span data-stu-id="34e7c-145">The tabs will be displayed from left to right in the order shown in the above screenshot (the tab at the top is shown on the left).</span></span>
