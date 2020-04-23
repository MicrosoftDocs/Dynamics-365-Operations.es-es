---
title: Estados de ciclo de vida de solicitud de mantenimiento
description: Este tema describe cómo configurar los estados de ciclo de vida de la solicitud de mantenimiento en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9d1e4412af0619b57467b5bcba75ea7259604d1d
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209016"
---
# <a name="maintenance-request-lifecycle-states"></a><span data-ttu-id="5036e-103">Estados de ciclo de vida de solicitud de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="5036e-103">Maintenance request lifecycle states</span></span>

[!include [banner](../../includes/banner.md)]

 


<span data-ttu-id="5036e-104">Los estados de ciclo de vida de solicitud de mantenimiento definen las etapas por las que puede pasar una solicitud.</span><span class="sxs-lookup"><span data-stu-id="5036e-104">Maintenance request lifecycle states define the stages that a request can go through.</span></span> <span data-ttu-id="5036e-105">Los ejemplos incluyen **Creada**, **Activa** y **Finalizada**.</span><span class="sxs-lookup"><span data-stu-id="5036e-105">Examples include **Created**, **Active**, and **Ended**.</span></span> <span data-ttu-id="5036e-106">Cuando una solicitud de mantenimiento se convierte en una orden de trabajo, el estado del ciclo de vida de la solicitud de mantenimiento se debe actualizar a **Finalizada** o **Cerrada** para indicar que la solicitud de mantenimiento ya no está activa.</span><span class="sxs-lookup"><span data-stu-id="5036e-106">When a maintenance request is converted to a work order, the maintenance request lifecycle state should be updated to **Ended** or **Closed** to indicate that the maintenance request is no longer active.</span></span> <span data-ttu-id="5036e-107">En la página de lista **Todas las solicitudes de mantenimiento**, puede ver todas las solicitudes de mantenimiento, independientemente de su estado de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="5036e-107">On the **All maintenance requests** list page, you can view all maintenance requests, regardless of their lifecycle state.</span></span>

## <a name="set-up-maintenance-request-lifecycle-states"></a><span data-ttu-id="5036e-108">Configurar estados de ciclo de vida de solicitud de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="5036e-108">Set up maintenance request lifecycle states</span></span>

1. <span data-ttu-id="5036e-109">Seleccione **Administración de activos** \> **Configuración** \> **Solicitudes de mantenimiento** \> **Estados de ciclo de vida**.</span><span class="sxs-lookup"><span data-stu-id="5036e-109">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Lifecycle states**.</span></span>
2. <span data-ttu-id="5036e-110">Seleccione **Nuevo** para crear un estado de ciclo de vida de solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="5036e-110">Select **New** to create a maintenance request lifecycle state.</span></span>
3. <span data-ttu-id="5036e-111">En el campo **Estado de ciclo de vida**, especifique un identificador para el estado de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="5036e-111">In the **Lifecycle state** field, enter an ID for the lifecycle state.</span></span>
4. <span data-ttu-id="5036e-112">Escriba un nombre en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="5036e-112">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="5036e-113">En el FastTab **Detalles**, el campo **Modelos de ciclo de vida** muestra el número de modelos de ciclo de vida de solicitud de mantenimiento que utilizan este estado de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="5036e-113">On the **Details** FastTab, the **Lifecycle models** field shows the number of maintenance request lifecycle models that use this lifecycle state.</span></span>

5. <span data-ttu-id="5036e-114">En el FastTab **General**, establezca la opción **Activa** en **Sí** si una solicitud de mantenimiento está activa cuando se encuentra en este estado de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="5036e-114">On the **General** FastTab, set the **Active** option to **Yes** if a maintenance request should be active while it's in this lifecycle state.</span></span>
6. <span data-ttu-id="5036e-115">Establezca la opción **Establecer el final real** en **Sí** si se deben introducir una fecha y hora finales reales automáticamente en una solicitud de mantenimiento que se encuentre en este estado de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="5036e-115">Set he **Set actual end** option to **Yes** if an actual end date and time should automatically be entered on a maintenance request that is in this lifecycle state.</span></span>
7. <span data-ttu-id="5036e-116">Establezca la opción **Crear orden de trabajo** en **Sí** si se puede crear una orden de trabajo a partir de una solicitud de mantenimiento que se encuentre en este estado de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="5036e-116">Set the **Create work order** option to **Yes** if a work order can be created from a maintenance request that is in this lifecycle state.</span></span>
8. <span data-ttu-id="5036e-117">Establezca la opción **Eliminar** en **Sí** si una solicitud de mantenimiento se puede eliminar siempre que se encuentre en este estado de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="5036e-117">Set the **Delete** option to **Yes** if a maintenance request can be deleted while it's in this lifecycle state.</span></span>
9. <span data-ttu-id="5036e-118">En el FastTab **Actualizar**, las opciones **Entrante** y **Saliente** de la sección **Activo** son relevantes si usa la reparación interna. Establezca la opción adecuada en **Sí** si se debe actualizar automáticamente el estado de ciclo de vida de los activos seleccionados en una solicitud de mantenimiento a **Entrante** o **Saliente** cuando el estado de ciclo de vida de la solicitud de mantenimiento de dicha solicitud de mantenimiento se establece en **Entrante** o **Saliente**.</span><span class="sxs-lookup"><span data-stu-id="5036e-118">On the **Update** FastTab, the **Inbound** and **Outbound** options in the **Asset** section are relevant if you use depot repair.cSet the appropriate option to **Yes** if the asset lifecycle state of assets that are selected on a maintenance request should automatically be updated to **Inbound** or **Outbound** when the maintenance request lifecycle state of that maintenance request is set to **Inbound** or **Outbound**.</span></span>

<span data-ttu-id="5036e-119">La ilustración siguiente muestra un ejemplo de la página **Estados de ciclo de vida de solicitud de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="5036e-119">The follow illustration shows an example of the **Maintenance request lifecycle states** page.</span></span>

![Página de estados de ciclo de vida de solicitud de mantenimiento](media/02-setup-for-requests.png)

> [!NOTE]
> <span data-ttu-id="5036e-121">Los estados de ciclo de vida de solicitud de mantenimiento, los grupos de estados de ciclo de vida y sus tipos están relacionados con (y se usan del mismo modo que) los estados de ciclo de vida de la orden de trabajo, los grupos de estados de ciclo de vida y sus tipos.</span><span class="sxs-lookup"><span data-stu-id="5036e-121">Maintenance request lifecycle states, lifecycle state groups, and types are related to, and used in the same way as, work order lifecycle states, lifecycle state groups, and types.</span></span> 

## <a name="set-up-maintenance-request-lifecycle-models"></a><span data-ttu-id="5036e-122">Configurar modelos de ciclo de vida de solicitud de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="5036e-122">Set up maintenance request lifecycle models</span></span>

<span data-ttu-id="5036e-123">Una vez que haya creado los estados de ciclo de vida necesarios para sus solicitudes de mantenimiento, pueden dividirse en grupos de estados de ciclo de vida o modelos de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="5036e-123">After you've created the lifecycle states that are required for your maintenance requests, they can be divided into lifecycle state groups, or lifecycle models.</span></span> <span data-ttu-id="5036e-124">Los modelos de ciclo de vida de solicitud de mantenimiento se usan para crear el flujo que se puede usar para los diferentes tipos de solicitudes de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="5036e-124">Maintenance request lifecycle models are used to create the flow that can be used for different types of maintenance requests.</span></span> <span data-ttu-id="5036e-125">Como mínimo, debe crearse un modelo de ciclo de vida de solicitud de mantenimiento estándar.</span><span class="sxs-lookup"><span data-stu-id="5036e-125">At a minimum, one standard maintenance request lifecycle model should be created.</span></span>

1. <span data-ttu-id="5036e-126">Seleccione **Administración de activos** \> **Configuración** \> **Solicitudes de mantenimiento** \> **Modelos de ciclo de vida**.</span><span class="sxs-lookup"><span data-stu-id="5036e-126">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Lifecycle models**.</span></span>
2. <span data-ttu-id="5036e-127">Seleccione **Nuevo** para crear un modelo de ciclo de vida de solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="5036e-127">Select **New** to create a maintenance request lifecycle model.</span></span>
3. <span data-ttu-id="5036e-128">En el campo **Modelo de ciclo de vida**, especifique un identificador para el modelo de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="5036e-128">In the **Lifecycle model** field, enter an ID for the lifecycle model.</span></span>
4. <span data-ttu-id="5036e-129">Escriba un nombre en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="5036e-129">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="5036e-130">En el FastTab **Detalles**, **Estados de ciclo de vida** muestra el número de estados de ciclo de vida seleccionados en este modelo de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="5036e-130">On the **Details** FastTab, the **Lifecycle states** shows the number of lifecycle states that are selected in this lifecycle model.</span></span> <span data-ttu-id="5036e-131">El campo **Tipos de solicitud de mantenimiento** muestra el número de tipos de solicitud de mantenimiento que utilizan este modelo de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="5036e-131">The **Maintenance request types** field shows the number of maintenance request types that use this lifecycle model.</span></span>

5. <span data-ttu-id="5036e-132">En el FastTab **Estados de ciclo de vida**, seleccione los estados de ciclo de vida que se deben incluir en el modelo de ciclo de vida:</span><span class="sxs-lookup"><span data-stu-id="5036e-132">On the **Lifecycle states** FastTab, select the lifecycle states that should be included in the lifecycle model:</span></span>

    - <span data-ttu-id="5036e-133">Para incluir un estado de ciclo de vida en el modelo de ciclo de vida, selecciónelo en la sección **Estados de ciclo de vida restantes** y seleccione el botón de la ![flecha derecha](media/03-setup-for-requests.png) para moverlo a la sección **Estados del ciclo de vida seleccionados** .</span><span class="sxs-lookup"><span data-stu-id="5036e-133">To include a lifecycle state in the lifecycle model, select it in the **Lifecycle states remaining** section, and then select the right arrow button ![Right arrow](media/03-setup-for-requests.png) to move it to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="5036e-134">Para incluir todos los estados de ciclo de vida disponibles en el modelo de ciclo de vida, seleccione el botón **Seleccionar todos los estados disponibles** ![Seleccionar todos los estados disponibles](media/04-setup-for-requests.png).</span><span class="sxs-lookup"><span data-stu-id="5036e-134">To include all the available lifecycle states in the lifecycle model, select the **Select all available states** button ![Select all available states](media/04-setup-for-requests.png).</span></span> <span data-ttu-id="5036e-135">Todos los estados de ciclo de vida se mueven a la sección **Estados de ciclo de vida seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="5036e-135">All lifecycle states are moved to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="5036e-136">Para quitar un estado de ciclo de vida del modelo de ciclo de vida, selecciónelo en la sección **Estados de ciclo de vida seleccionados** y seleccione el botón de la ![flecha izquierda](media/05-setup-for-requests.png) para moverlo a la sección **Estados del ciclo de vida restantes**.</span><span class="sxs-lookup"><span data-stu-id="5036e-136">To remove a lifecycle state from the lifecycle model, select it in the **Lifecycle states selected** section, and then select the left arrow button ![Left arrow](media/05-setup-for-requests.png) to move it to the **Lifecycle states remaining** section.</span></span>

6. <span data-ttu-id="5036e-137">En el FastTab **General**, los campos de la sección **Actualizaciones** son relevantes si usa la reparación interna.</span><span class="sxs-lookup"><span data-stu-id="5036e-137">On the **General** FastTab, the fields in the **Updates** section are relevant if you use depot repair.</span></span>

    - <span data-ttu-id="5036e-138">En el campo **Estado del ciclo de vida del activo recibido**, seleccione el estado de ciclo de vida del activo al que deben actualizarse automáticamente los activos seleccionados en una solicitud de mantenimiento cuando se reciben para su reparación interna.</span><span class="sxs-lookup"><span data-stu-id="5036e-138">In the **Lifecycle state for asset received** field, select the asset lifecycle state that assets that are selected on a maintenance request should automatically be updated to when they are received for depot repair.</span></span>
    - <span data-ttu-id="5036e-139">En el campo **Estado de ciclo de vida del activo entregado**, seleccione el estado de ciclo de vida del activo al que deben actualizarse automáticamente los activos seleccionados en una solicitud de mantenimiento cuando se devuelven después de su reparación.</span><span class="sxs-lookup"><span data-stu-id="5036e-139">In the **Lifecycle state for asset delivered** field, select the lifecycle state that assets that are selected on a maintenance request should automatically be updated to when they are returned after repair.</span></span>

<span data-ttu-id="5036e-140">La ilustración siguiente muestra un ejemplo de la página **Modelos de ciclo de vida de solicitud de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="5036e-140">The following illustration shows an example of the **Maintenance request lifecycle models** page.</span></span>

![Página de modelos de ciclo de vida de solicitud de mantenimiento](media/06-setup-for-requests.png)
