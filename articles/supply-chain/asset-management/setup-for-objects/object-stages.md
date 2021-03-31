---
title: Estados de ciclo de vida de activos
description: Este tema explica los estados de ciclo de vida y los modelos de ciclo de vida de activos en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetLifecycleModelStateNext, EntAssetObjectLifecycleState, EntAssetLifecycleStateUpdate, EntAssetObjectLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 64be80777991a9fa674ef494cea103a602c7559f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5230137"
---
# <a name="asset-lifecycle-states"></a><span data-ttu-id="d2687-103">Estados de ciclo de vida de activos</span><span class="sxs-lookup"><span data-stu-id="d2687-103">Asset lifecycle states</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="d2687-104">Este tema explica los estados de ciclo de vida y los modelos de ciclo de vida de activos en Administración de activos.</span><span class="sxs-lookup"><span data-stu-id="d2687-104">This topic explains asset lifecycle states and lifecycle models in Asset Management.</span></span> <span data-ttu-id="d2687-105">Los estados de ciclo de vida de activo se uasn para definir si el activo está activo o inactivo.</span><span class="sxs-lookup"><span data-stu-id="d2687-105">Asset lifecycle states are used to define whether an asset is active or inactive.</span></span> <span data-ttu-id="d2687-106">Por ejemplo, puede configurar los estados del ciclo de vida de activo como **Creado**, **Activo** y **Finalizado**.</span><span class="sxs-lookup"><span data-stu-id="d2687-106">For example, you can set up asset lifecycle states such as **Created**, **Active**, and **Terminated**.</span></span>

> [!NOTE]
> - <span data-ttu-id="d2687-107">Los estados de ciclo de vida de solicitud están vinculados a los estados de ciclo de vida de activo.</span><span class="sxs-lookup"><span data-stu-id="d2687-107">Request lifecycle states are linked to asset lifecycle states.</span></span> <span data-ttu-id="d2687-108">Por lo tanto, cuando una solicitud se cambia a un nuevo estado de ciclo de vida, el activo vinculado a la solicitud se cambia a un nuevo estado de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="d2687-108">Therefore, when a request is changed to a new request lifecycle state, the asset that is attached to the request is changed to a new asset lifecycle state.</span></span> <span data-ttu-id="d2687-109">Por ejemplo, si cambia el estado de ciclo de vida de una solicitud a **Entrante**, el estado de ciclo de vida del activo vinculado se cambia al estado de ciclo de vida seleccionado en el campo **Estado de ciclo de vida de entrada** en el FastTab **Estado del ciclo de vida de activo** de la página **Modelos de estado de ciclo de vida de activo**.</span><span class="sxs-lookup"><span data-stu-id="d2687-109">For example, if the lifecycle state of a request is changed to **Inbound**, the lifecycle state of the attached asset is changed to the lifecycle state that is selected in the **Inbound lifecycle state** field on the **Asset lifecycle state** FastTab of the **Asset lifecycle state models** page.</span></span> 


<span data-ttu-id="d2687-110">Los estados de ciclo de vida de activo se pueden configurar en los modelos de ciclo de vida de activo, donde se pueden definir los estados de ciclo de vida necesasrios para los distintos tipos de activos.</span><span class="sxs-lookup"><span data-stu-id="d2687-110">Asset lifecycle states can be set up in asset lifecycle models, where you can define the required lifecycle states for various types of assets.</span></span> <span data-ttu-id="d2687-111">Primero debe configurar los estados de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="d2687-111">You first set up lifecycle states.</span></span> <span data-ttu-id="d2687-112">A continuación, crea un modelo de ciclo de vida y selecciona los estados de ciclo de vida para este.</span><span class="sxs-lookup"><span data-stu-id="d2687-112">You then create a lifecycle model and select lifecycle states for it.</span></span>

1. <span data-ttu-id="d2687-113">Seleccione **Administración de activos** \> **Configuración** \> **Activos** \> **Estados de ciclo de vida**.</span><span class="sxs-lookup"><span data-stu-id="d2687-113">Select **Asset management** \> **Setup** \> **Assets** \> **Lifecycle states**.</span></span>
2. <span data-ttu-id="d2687-114">Seleccione **Nuevo** para crear un nuevo estado de ciclo de vida de activo.</span><span class="sxs-lookup"><span data-stu-id="d2687-114">Select **New** to create a new asset lifecycle state.</span></span>
3. <span data-ttu-id="d2687-115">En el campo **Estado de ciclo de vida**, especifique el id. de estado de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="d2687-115">In the **Lifecycle state** field, enter the lifecycle state ID.</span></span>
4. <span data-ttu-id="d2687-116">En el campo **Nombre**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="d2687-116">In the **Name** field, enter a description.</span></span>

    <span data-ttu-id="d2687-117">El campo **Modelos de ciclo de vida** muestra el número de modelos de ciclo de vida de activo que usan el estado de ciclo de vida de activo.</span><span class="sxs-lookup"><span data-stu-id="d2687-117">The **Lifecycle models** field shows the number of asset lifecycle models that use the asset lifecycle state.</span></span>

5. <span data-ttu-id="d2687-118">Establezca la opción **Activo** en **Sí** si este estado de ciclo de vida es una estado de ciclo de vida activo (es decir, si se pueden crear órdenes de trabajo para los activos que se encuentran en este estado de ciclo de vida).</span><span class="sxs-lookup"><span data-stu-id="d2687-118">Set the **Active** option to **Yes** if this lifecycle state should be an active lifecycle state (in other words, if work orders can be created for assets that are in this lifecycle state).</span></span>
6. <span data-ttu-id="d2687-119">Establezca la opción **Eliminar líneas abiertas del calendario** en **Sí** si se deben eliminar las líneas abiertas del calendario de activos que tengan un estado de ciclo de vida de activo **Creado** cuando se encuentren en este estado de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="d2687-119">Set the **Delete open calendar lines** option to **Yes** if open asset calendar lines that have an asset lifecycle state of **Created** should be deleted when they are in this lifecycle state.</span></span> <span data-ttu-id="d2687-120">Esta opción resulta útil si desea limpiar las programaciones de mantenimiento abiertas que ya no sean relevantes para el activo (por ejemplo, si el activo ya no está activo).</span><span class="sxs-lookup"><span data-stu-id="d2687-120">This setting is useful if you want to clean up any open maintenance schedules that are no longer relevant for the asset (for example, if the asset is no longer active).</span></span>

> [!NOTE]
> <span data-ttu-id="d2687-121">Los estados de ciclo de vida de activo, los modelos de ciclo de vida de activo y los tipos de activo están relacionados.</span><span class="sxs-lookup"><span data-stu-id="d2687-121">Asset lifecycle states, asset lifecycle models, and asset types are related.</span></span> <span data-ttu-id="d2687-122">Se usan de la misma forma que los estados de ciclo de vida de orden de trabajo, los modelos de ciclo de vida de orden de trabajo y los tipos de orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d2687-122">They are used in the same way as work order lifecycle states, work order lifecycle models, and work order types.</span></span> 


<span data-ttu-id="d2687-123">Una vez que haya creado los estados de ciclo de vida de activo necesarios, puede configurar los estados de ciclo de vida en los modelos de ciclo de vida de activo.</span><span class="sxs-lookup"><span data-stu-id="d2687-123">After you've created the required asset lifecycle states, you can set up lifecycle states in asset lifecycle models.</span></span>

1. <span data-ttu-id="d2687-124">Seleccione **Administración de activos** \> **Configuración** \> **Activos** \> **Modelos de ciclo de vida**.</span><span class="sxs-lookup"><span data-stu-id="d2687-124">Select **Asset management** \> **Setup** \> **assets** \> **lifecycle models**.</span></span>
2. <span data-ttu-id="d2687-125">Seleccione **Nuevo** para crear un nuevo modelo de ciclo de vida de activo.</span><span class="sxs-lookup"><span data-stu-id="d2687-125">Select **New** to create a new asset lifecycle model.</span></span>
3. <span data-ttu-id="d2687-126">En el campo **Modelo de ciclo de vida**, especifique el id. de modelo de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="d2687-126">In the **Lifecycle model** field, enter the lifecycle model ID.</span></span>
4. <span data-ttu-id="d2687-127">En el campo **Nombre**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="d2687-127">In the **Name** field, enter a description.</span></span>

    <span data-ttu-id="d2687-128">El campo **Estados de ciclo de vida** muestra el número de estados de ciclo de vida de activo seleccionados en el modelo de ciclo de vida de activo.</span><span class="sxs-lookup"><span data-stu-id="d2687-128">The **Lifecycle states** field shows the number of asset lifecycle states that are selected in the asset lifecycle model.</span></span> <span data-ttu-id="d2687-129">El campo **Tipos de activo** muestra el número de tipos de activo que utilizan el modelo de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="d2687-129">The **Asset types** field shows the number of asset types that use the lifecycle model.</span></span>

5. <span data-ttu-id="d2687-130">En el FastTab **Estados de ciclo de vida**, seleccione los estados de ciclo de vida de activo que se deben incluir en el modelo de ciclo de vida de activo:</span><span class="sxs-lookup"><span data-stu-id="d2687-130">On the **Lifecycle states** FastTab, select the asset lifecycle states that should be included in the asset lifecycle model:</span></span>

    - <span data-ttu-id="d2687-131">Para usar un estado de ciclo de vida para el modelo, selecciónelo en la sección **Estados de ciclo de vida restantes** y seleccione el botón de la flecha derecha ![Flecha derecha](media/15-setup-for-objects.png) para moverlo a la sección **Estados del ciclo de vida seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="d2687-131">To use a lifecycle state for the model, select it in the **Lifecycle states remaining** section, and then select the right arrow button ![Right arrow](media/15-setup-for-objects.png) to move it to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="d2687-132">Para usar todos los estados de ciclo de vida disponibles para el modelo, seleccione el botón **Todos los estados de ciclo de vida disponibles** ![Todos los estados de ciclo de vida disponibles](media/20-setup-for-objects.png).</span><span class="sxs-lookup"><span data-stu-id="d2687-132">To use all the available lifecycle states for the model, select the **All available lifecycle states** button ![All available lifecycle states](media/20-setup-for-objects.png).</span></span> <span data-ttu-id="d2687-133">Todos los estados de ciclo de vida se transfieren a la sección **Estados de ciclo de vida seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="d2687-133">All lifecycle states are transferred to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="d2687-134">Para quitar un estado de ciclo de vida del modelo, selecciónelo en la sección **Estados de ciclo de vida seleccionados** y seleccione el botón de la flecha izquierda ![Flecha izquierda](media/16-setup-for-objects.png) para moverlo a la sección **Estados del ciclo de vida restantes**.</span><span class="sxs-lookup"><span data-stu-id="d2687-134">To remove a lifecycle state from the model, select it in the **lifecycle states selected** section, and then select the left arrow button ![Left arrow](media/16-setup-for-objects.png) to move it to the **Lifecycle states remaining** section.</span></span>

6. <span data-ttu-id="d2687-135">Seleccione **Actualizaciones de estado de ciclo de vida** para definir los estados de ciclo de vida de activo que pueden seguir un estado de ciclo de vida seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d2687-135">Select **Lifecycle state updates** to define the asset lifecycle states that can follow a selected lifecycle state.</span></span>
7. <span data-ttu-id="d2687-136">Use el FastTab **Estado de activo** si administra activos que recibe para su reparación.</span><span class="sxs-lookup"><span data-stu-id="d2687-136">You use the **Asset state** FastTab if you handle assets that you receive for repair.</span></span> <span data-ttu-id="d2687-137">En la sección **Entrante/saliente**, puede seleccionar estados de ciclo de vida de activo para indicar el flujo de trabajo de un activo que recibe para reparación.</span><span class="sxs-lookup"><span data-stu-id="d2687-137">In the **Inbound/outbound** section, you can select asset lifecycle states to indicate the workflow of an asset that you receive for repair.</span></span> <span data-ttu-id="d2687-138">Si ofrece activos de préstamo a los clientes o departamentos, en la sección **Préstamo** puede seleccionar estados de ciclo de vida de activos de préstamo.</span><span class="sxs-lookup"><span data-stu-id="d2687-138">If you offer loan assets to customers or departments, in the **Loan** section, you can select lifecycle states for loan assets.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]