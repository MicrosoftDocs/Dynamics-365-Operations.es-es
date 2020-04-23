---
title: Crear solicitudes de mantenimiento
description: En este tema se explica cómo crear una solicitud de mantenimiento en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d9a6b4daf1a29b032bb82f46aaabccb2231a83a8
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205239"
---
# <a name="create-maintenance-requests"></a><span data-ttu-id="a703d-103">Crear solicitudes de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="a703d-103">Create maintenance requests</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="a703d-104">Pueden usarse solicitudes de mantenimiento cuando los trabajadores de mantenimiento o los trabajadores de producción detectan que el equipo requiere reparación, y el trabajo de reparación no se puede hacer inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="a703d-104">Maintenance requests can be used if maintenance workers or production workers discover that equipment requires repair, but the repair job can't be done right away.</span></span>

<span data-ttu-id="a703d-105">**Ejemplo:** cuando un trabajador de mantenimiento está realizando una reparación, descubre que hay que realizar el mantenimiento de otro activo en esa misma ubicación.</span><span class="sxs-lookup"><span data-stu-id="a703d-105">**Example:** While a maintenance worker is making a repair, she discovers that another asset at the same location must be serviced.</span></span> <span data-ttu-id="a703d-106">Sin embargo, el trabajador de mantenimiento no tiene ni el tiempo ni las piezas de repuesto necesarias para realizar el trabajo de reparación.</span><span class="sxs-lookup"><span data-stu-id="a703d-106">However, the maintenance worker doesn't have the time or the required spare parts to do the repair job.</span></span> <span data-ttu-id="a703d-107">Así, crea una solicitud de mantenimiento en el activo y especifica una breve descripción del problema.</span><span class="sxs-lookup"><span data-stu-id="a703d-107">Therefore, she creates a maintenance request on the asset and enters a short description of the issue.</span></span>

<span data-ttu-id="a703d-108">La sección **Solicitudes de mantenimiento activas** del panel **Información relacionada** a la derecha de la página **Todos los activos** o **Activos activos** (**Administración de activos** \> **Común** \> **Activos** \> **Todos los activos** o **Activos activos**) muestra las solicitudes de mantenimiento activas vinculados al activo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="a703d-108">The **Active maintenance requests** section of the **Related information** pane on the right side of the **All assets** or **Active assets** page (**Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**) shows the active maintenance requests that are attached to the selected asset.</span></span>

1. <span data-ttu-id="a703d-109">Seleccione **Administración de activos** \> **Común** \> **Solicitudes de mantenimiento** \> **Todas las solicitudes de mantenimiento** o **Solicitudes de mantenimiento activas**.</span><span class="sxs-lookup"><span data-stu-id="a703d-109">Select **Asset management** \> **Common** \> **Maintenance requests** \> **All maintenance requests** or **Active maintenance requests**.</span></span>
2. <span data-ttu-id="a703d-110">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="a703d-110">Select **New**.</span></span>
3. <span data-ttu-id="a703d-111">En el cuadro de diálogo **Crear solicitud**, en el campo **Tipo de solicitud de mantenimiento**, seleccione el tipo de solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="a703d-111">In the **Create request** dialog box, in the **Maintenance request type** field, select the type of maintenance request.</span></span> <span data-ttu-id="a703d-112">Se sugiere un tipo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a703d-112">A default type is suggested.</span></span>
4. <span data-ttu-id="a703d-113">En el campo **Descripción**, escriba un nombre o un título que describa brevemente la solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="a703d-113">In the **Description** field, enter a name or title that briefly describes the maintenance request.</span></span>
5. <span data-ttu-id="a703d-114">En los campos **Ubicación técnica** y **Activo**, seleccione una ubicación técnica o un activo, o una combinación de una ubicación técnica y un activo, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a703d-114">In the **Functional location** and **Asset** fields, select a functional location or an asset, or a combination of a functional location and an asset, as you require.</span></span> <span data-ttu-id="a703d-115">Puede crear una solicitud de mantenimiento sin seleccionar un activo, y el activo se puede agregar posteriormente a la solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="a703d-115">You can create a maintenance request without selecting an asset, and the asset can be added to the maintenance request later.</span></span> <span data-ttu-id="a703d-116">Si el trabajador de mantenimiento que ha iniciado sesión está relacionado con un recurso relacionado con un activo, el campo **Activo** se establece automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a703d-116">If the maintenance worker who is signed in is related to a resource that is related to an asset, the **Asset** field is automatically set.</span></span>

    <span data-ttu-id="a703d-117">Si una solicitud de mantenimiento ya está vinculada al activo seleccionado, aparece una barra de mensajes en la parte superior del cuadro de diálogo **Crear solicitud** para notificarle el identificador de la solicitud de mantenimiento existente.</span><span class="sxs-lookup"><span data-stu-id="a703d-117">If a maintenance request is already attached to the selected asset, a message bar appears at the top of the **Create request** dialog box to notify you about the ID of the existing maintenance request.</span></span> <span data-ttu-id="a703d-118">Una barra de mensajes también le notifica si el activo está cubierto por un acuerdo de garantía.</span><span class="sxs-lookup"><span data-stu-id="a703d-118">A message bar also notifies you if the asset is covered by a warranty agreement.</span></span>

6. <span data-ttu-id="a703d-119">En el campo **Nivel de servicio**, seleccione un nivel de servicio que indique la urgencia de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="a703d-119">In the **Service level** field, select a service level that indicates the urgency of the request.</span></span>
7. <span data-ttu-id="a703d-120">Si ha seleccionado un activo en el paso 5, puede usar los campos **Síntoma del error**, **Área del error** y **Tipo de error** para crear un registro de error.</span><span class="sxs-lookup"><span data-stu-id="a703d-120">If you selected an asset in step 5, you can use the **Fault symptom**, **Fault area**, and **Fault type** fields to create a fault registration.</span></span>
8. <span data-ttu-id="a703d-121">Si la solicitud de mantenimiento ha provocado el tiempo de inactividad de mantenimiento, especifique la fecha y la hora iniciales del tiempo de inactividad.</span><span class="sxs-lookup"><span data-stu-id="a703d-121">If the maintenance request has caused maintenance downtime, enter the start date and time of the downtime.</span></span>

    <span data-ttu-id="a703d-122">Se establece automáticamente el campo **Iniciado por** en su nombre.</span><span class="sxs-lookup"><span data-stu-id="a703d-122">The **Started by** field is automatically set to your name.</span></span>

10. <span data-ttu-id="a703d-123">El campo **Inicio real** se establece automáticamente en la fecha y la hora actuales.</span><span class="sxs-lookup"><span data-stu-id="a703d-123">The **Actual start** field is automatically set to the current date and time.</span></span> <span data-ttu-id="a703d-124">Sin embargo, puede cambiar el valor si es necesario.</span><span class="sxs-lookup"><span data-stu-id="a703d-124">However, you can change the value as you require.</span></span>
11. <span data-ttu-id="a703d-125">En el campo **Notas**, especifique las notas adicionales necesarias.</span><span class="sxs-lookup"><span data-stu-id="a703d-125">In the **Notes** field, enter any additional notes that are required.</span></span>
12. <span data-ttu-id="a703d-126">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a703d-126">Select **OK**.</span></span>

![Crear solicitud de mantenimiento](media/03-manage-maintenance-requests.png)

## <a name="subsequent-processing-of-maintenance-requests"></a><span data-ttu-id="a703d-128">Procesamiento posterior de solicitudes de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="a703d-128">Subsequent processing of maintenance requests</span></span>

<span data-ttu-id="a703d-129">Una vez creada una solicitud de mantenimiento, y antes de convertirla en una orden de trabajo, hay que actualizar diversos datos.</span><span class="sxs-lookup"><span data-stu-id="a703d-129">After a maintenance request is created, but before it's converted to a work order, various information should be updated on it.</span></span> <span data-ttu-id="a703d-130">Generalmente esta tarea la completa un planificador u otro empleado administrativo.</span><span class="sxs-lookup"><span data-stu-id="a703d-130">Typically, a planner or another administrative employee completes this task.</span></span>

- <span data-ttu-id="a703d-131">En **Todas las solicitudes de mantenimiento** o en la página **Solicitudes de mantenimiento activas**, seleccione la solicitud de trabajo y, a continuación seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a703d-131">On the **All maintenance requests** or **Active maintenance requests** page, select the request to work with, and then select **Edit**.</span></span>

<span data-ttu-id="a703d-132">En la vista de detalles puede actualizar diversos datos.</span><span class="sxs-lookup"><span data-stu-id="a703d-132">In the details view, you can update various information.</span></span> <span data-ttu-id="a703d-133">A continuación se incluyen algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="a703d-133">Here are some examples:</span></span>

- <span data-ttu-id="a703d-134">Seleccione y compruebe el activo.</span><span class="sxs-lookup"><span data-stu-id="a703d-134">Select and verify the asset.</span></span> <span data-ttu-id="a703d-135">Si tiene que seleccionar un activo diferente más tarde, puede establecer la opción **Activo comprobado** en **No**.</span><span class="sxs-lookup"><span data-stu-id="a703d-135">If you must select a different asset later, you can set the **Asset verified** option to **No**.</span></span>
- <span data-ttu-id="a703d-136">Seleccione un grupo de trabajadores de mantenimiento responsable o un trabajador de mantenimiento responsable.</span><span class="sxs-lookup"><span data-stu-id="a703d-136">Select a responsible maintenance worker group and/or a responsible maintenance worker.</span></span> <span data-ttu-id="a703d-137">Para obtener más información sobre la configuración necesaria, consulte [Trabajadores de mantenimiento responsables](../setup-for-maintenance-requests/responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="a703d-137">For more information about the required setup, see [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md).</span></span>
- <span data-ttu-id="a703d-138">Seleccione un tipo de trabajo de mantenimiento y, si esta información es relevante, elija una variante y un oficio de trabajo de mantenimiento relacionados.</span><span class="sxs-lookup"><span data-stu-id="a703d-138">Select a maintenance job type and, if this information is relevant, a related maintenance job variant and a job trade.</span></span>
- <span data-ttu-id="a703d-139">En los campos **Latitud** y **Longitud**, especifique las coordenadas geográficas.</span><span class="sxs-lookup"><span data-stu-id="a703d-139">In the **Latitude** and **Longitude** fields, enter geographic coordinates.</span></span> <span data-ttu-id="a703d-140">Las coordenadas que se agreguen a una solicitud de mantenimiento se transferirán automáticamente a una orden de trabajo relacionada.</span><span class="sxs-lookup"><span data-stu-id="a703d-140">Any coordinates that are added to a maintenance request are automatically transferred to a related work order.</span></span> 

![Actualizar solicitud de mantenimiento](media/04-manage-maintenance-requests.png)

> [!NOTE]
> <span data-ttu-id="a703d-142">Si selecciona un activo al crear una solicitud de mantenimiento, puede agregar un error a activo.</span><span class="sxs-lookup"><span data-stu-id="a703d-142">If you select an asset when you create a maintenance request, you can add one fault to the asset.</span></span> <span data-ttu-id="a703d-143">Una vez creada la solicitud de mantenimiento, puede agregar más errores si es necesario.</span><span class="sxs-lookup"><span data-stu-id="a703d-143">After the maintenance request has been created, you can add more faults, as you require.</span></span> <span data-ttu-id="a703d-144">Para agregar errores, seleccione **Error de activo** en la página **Todas las solicitudes de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="a703d-144">To add faults, select **Asset fault** on the **All maintenance requests** page.</span></span>
