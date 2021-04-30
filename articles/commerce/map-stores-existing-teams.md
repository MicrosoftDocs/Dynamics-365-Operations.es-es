---
title: Asignar tiendas y equipos si estos últimos ya existen en Microsoft Teams
description: Este tema cubre cómo asignar tiendas y equipos correspondientes en la sede de Dynamics 365 Commerce si su organización ya ha creado equipos en Microsoft Teams antes de la integración con Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 5a711c1057b87bd792755ef91a84d1c28879c590
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908504"
---
# <a name="map-stores-and-teams-if-there-are-pre-existing-teams-in-microsoft-teams"></a><span data-ttu-id="2a6e0-103">Asignar tiendas y equipos si estos últimos ya existen en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2a6e0-103">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2a6e0-104">Este tema cubre cómo asignar tiendas y equipos correspondientes en la sede de Dynamics 365 Commerce si su organización ya ha creado equipos en Microsoft Teams antes de la integración con Commerce.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-104">This topic covers how to map stores and corresponding teams in Dynamics 365 Commerce headquarters if your organization has already created teams in Microsoft Teams before Commerce integration.</span></span>

<span data-ttu-id="2a6e0-105">Su organización puede tener equipos creados para algunas o todas sus tiendas antes de integrar Dynamics 365 Commerce y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-105">Your organization may have teams created for some or all of your stores before integrating Dynamics 365 Commerce and Microsoft Teams.</span></span> <span data-ttu-id="2a6e0-106">Si este es el caso, para establecer la sincronización de tareas entre Commerce PDV y Microsoft Teams debe proporcionar la asignación de tiendas y equipo correspondiente en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-106">If this is the case, to establish task synchronization between Commerce POS and Microsoft Teams you must provide the mapping of stores and corresponding team in Commerce headquarters.</span></span>

## <a name="map-stores-and-corresponding-teams-in-commerce-headquarters"></a><span data-ttu-id="2a6e0-107">Asignar tiendas y equipos correspondientes en la sede de Commerce</span><span class="sxs-lookup"><span data-stu-id="2a6e0-107">Map stores and corresponding teams in Commerce headquarters</span></span> 

<span data-ttu-id="2a6e0-108">Para asignar tiendas y equipos correspondientes en la sede de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-108">To map stores and corresponding teams in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="2a6e0-109">Vaya a **Administración del sistema \> Espacio de trabajo \> Administración de datos**.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-109">Go to **System Administration \> Workspace \> Data management**.</span></span>
1. <span data-ttu-id="2a6e0-110">Seleccione **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-110">Select **Export**.</span></span> 
1. <span data-ttu-id="2a6e0-111">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-111">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="2a6e0-112">En **Nombre del grupo**, introduzca "Exportar asignación de Teams".</span><span class="sxs-lookup"><span data-stu-id="2a6e0-112">Under **Group name**, enter "Export Teams mapping".</span></span>
1. <span data-ttu-id="2a6e0-113">En la ficha desplegable **Entidades seleccionadas**, seleccione **Agregar entidad**.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-113">On the **Selected entities** FastTab, select **Add entity**.</span></span> <span data-ttu-id="2a6e0-114">Aparece el cuadro **Agregar entidad**.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-114">The **Add entity** dialog box appears.</span></span>  
1. <span data-ttu-id="2a6e0-115">En la lista desplegable **Nombre de la entidad**, seleccione **Asignación de Teams entre origen y equipo**.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-115">In the **Entity name** drop-down list, select **Teams mapping between source and team**.</span></span>
1. <span data-ttu-id="2a6e0-116">En la lista desplegable **Formato de datos de destino**, seleccione **CSV**.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-116">In the **Target data format** drop-down list, select **CSV**.</span></span>
1. <span data-ttu-id="2a6e0-117">Seleccione **Agregar** y, a continuación, **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-117">Select **Add**, and then select **Close**.</span></span>
1. <span data-ttu-id="2a6e0-118">En la parte superior izquierda debajo del Panel de acciones, seleccione **Exportar ahora**.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-118">On the top left under the Action Pane, select **Export now**.</span></span>
1. <span data-ttu-id="2a6e0-119">En **Estado de procesamiento de la entidad**, seleccione **Descargar archivo**.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-119">Under **Entity processing status**, select **Download file**.</span></span>
1. <span data-ttu-id="2a6e0-120">En el archivo CSV exportado, introduzca valores para **SOURCETYPE**, **SOURCEID**, y **TEAMID** como sigue:</span><span class="sxs-lookup"><span data-stu-id="2a6e0-120">In the exported CSV file, enter values for **SOURCETYPE**, **SOURCEID**, and **TEAMID** as follows:</span></span>
    - <span data-ttu-id="2a6e0-121">Para **SOURCETYPE**, introduzca "RetailStore".</span><span class="sxs-lookup"><span data-stu-id="2a6e0-121">For **SOURCETYPE**, enter "RetailStore".</span></span> 
    - <span data-ttu-id="2a6e0-122">Para **SOURCEID**, introduzca el número de la tienda (por ejemplo, "000135" para la tienda de San Francisco).</span><span class="sxs-lookup"><span data-stu-id="2a6e0-122">For **SOURCEID**, enter the store number (for example, "000135" for the San Francisco store).</span></span> <span data-ttu-id="2a6e0-123">Puede encontrar los números de las tiendas en **Retail y Commerce \> Canales \> Tiendas**.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-123">You can find store numbers at **Retail and Commerce \> Channels \> Stores**.</span></span>
    - <span data-ttu-id="2a6e0-124">Para **TEAMID**, introduzca el identificador de equipo correspondiente de Microsoft Teams (por ejemplo, "5f8bc92b-6aa8-451e-85d1-3949c01ddc6c").</span><span class="sxs-lookup"><span data-stu-id="2a6e0-124">For **TEAMID**, enter the corresponding team ID from Microsoft Teams (for example, "5f8bc92b-6aa8-451e-85d1-3949c01ddc6c").</span></span> <span data-ttu-id="2a6e0-125">Puede encontrar la información de identificación del equipo en [admin.teams.microsoft.com](https://admin.teams.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="2a6e0-125">You can find team ID information at [admin.teams.microsoft.com](https://admin.teams.microsoft.com).</span></span>
1. <span data-ttu-id="2a6e0-126">Guarde el archivo CSV en su máquina local.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-126">Save the CSV file to your local machine.</span></span>
1. <span data-ttu-id="2a6e0-127">Vaya a **Administración del sistema \> Espacio de trabajo \> Administración de datos** y después seleccione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-127">Go to **System Administration \> Workspace \> Data management**, and then select **Import**.</span></span>
1. <span data-ttu-id="2a6e0-128">En la ficha desplegable **Entidades seleccionadas**, seleccione **Agregar archivo**.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-128">On the **Selected entities** FastTab, select **Add file**.</span></span> <span data-ttu-id="2a6e0-129">Aparece el cuadro **Agregar archivo**.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-129">The **Add file** dialog box appears.</span></span>
1. <span data-ttu-id="2a6e0-130">En la lista desplegable **Nombre de la entidad**, seleccione **Asignación de Teams entre origen y equipo**.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-130">In the **Entity name** drop-down list, select **Teams mapping between source and team**.</span></span>
1. <span data-ttu-id="2a6e0-131">En la lista desplegable **Formato de datos de origen**, seleccione **CSV**.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-131">In the **Source data format** drop-down list, select **CSV**.</span></span>
1. <span data-ttu-id="2a6e0-132">Seleccione **Cargar y agregar**, seleccione el archivo CSV que guardó anteriormente y luego seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-132">Select **Upload and add**, select the CSV file that you saved previously, and then select **Open**.</span></span>
1. <span data-ttu-id="2a6e0-133">En el cuadro de diálogo **Agregar archivo**, seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-133">In the **Add file** dialog box, select **Close**.</span></span>
1. <span data-ttu-id="2a6e0-134">En el panel de acciones, seleccione **Guardar** y luego seleccione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-134">On the Action Pane, select **Save** , and then select **Import**.</span></span>

<span data-ttu-id="2a6e0-135">La siguiente imagen de ejemplo muestra el grupo **Exportar asignación de equipos** en Commerce con elementos de **Agregar entidad** y los encabezados del archivo CSV exportado resaltados.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-135">The following example image shows the **Export teams mapping** group in Commerce with **Add entity** elements and the exported CSV file headers highlighted.</span></span>

![Exportar asignación de equipos en Commerce con elementos de agregar entidad y los encabezados del archivo CSV exportado resaltados](media/d365-commerce-data-mgmt-export-entity.png)

> [!NOTE]
> <span data-ttu-id="2a6e0-137">Después de completar los pasos anteriores, siga los pasos en [Sincronizar la gestión de tareas entre Microsoft Teams y PDV](synchronize-tasks-teams-pos.md) para sincronizar la gestión de tareas.</span><span class="sxs-lookup"><span data-stu-id="2a6e0-137">After you complete the preceeding steps, follow the steps in [Synchronize task management between Microsoft Teams and POS](synchronize-tasks-teams-pos.md) to synchronize task management.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="2a6e0-138">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2a6e0-138">Additional resources</span></span>

[<span data-ttu-id="2a6e0-139">Información general sobre integración de Dynamics 365 Commerce y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2a6e0-139">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="2a6e0-140">Habilitar la integración de Dynamics 365 Commerce y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2a6e0-140">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="2a6e0-141">Aprovisionar Microsoft Teams desde Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="2a6e0-141">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="2a6e0-142">Sincronizar la gestión de tareas entre Microsoft Teams y Dynamics 365 Commerce PDV</span><span class="sxs-lookup"><span data-stu-id="2a6e0-142">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="2a6e0-143">Administrar roles de usuario en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2a6e0-143">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="2a6e0-144">Preguntas frecuentes de la integración de Dynamics 365 Commerce y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2a6e0-144">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
