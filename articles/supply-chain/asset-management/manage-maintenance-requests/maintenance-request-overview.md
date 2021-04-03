---
title: Solicitudes de mantenimiento
description: Este tema proporciona una visión general de la gestión de solicitudes de mantenimiento en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetRequestTable, EntAssetRequestWorkspace, EntAssetRequestActivePart, EntAssetRequestWorkOrderActive, EntAssetRequestType, EntAssetRequestTableCreateWO, EntAssetRequestTableLookup, EntAssetRequestTableActivePart, EntAssetMobileRequestDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d81fed34c1eb9ff0347c67086ceb08c038d8eb08
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253383"
---
# <a name="maintenance-requests"></a><span data-ttu-id="a951d-103">Solicitudes de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="a951d-103">Maintenance requests</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="a951d-104">Las solicitudes de mantenimiento son las notas o declaraciones que se crean para notificar a un administrador o planificador sobre un activo que requiere un trabajo de mantenimiento o de reparación, sin crear una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a951d-104">Maintenance requests are notes or declarations that are created to notify a manager or planner that an asset might require a maintenance or repair job, but without creating a work order.</span></span> <span data-ttu-id="a951d-105">Si el contenido de una solicitud de mantenimiento se considera válido, se puede crear una orden de trabajo a partir de la solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="a951d-105">If the contents of a maintenance request are considered valid, a work order can then be created based on the maintenance request.</span></span>

<span data-ttu-id="a951d-106">Las solicitudes de mantenimiento se pueden crear para cualquier activo en Administración de activos.</span><span class="sxs-lookup"><span data-stu-id="a951d-106">Maintenance requests can be created for any asset in Asset Management.</span></span> <span data-ttu-id="a951d-107">Se pueden crear distintos tipos de solicitudes de mantenimiento, en función de cómo las utilice la empresa.</span><span class="sxs-lookup"><span data-stu-id="a951d-107">Various types of maintenance requests can be created, depending on how your company uses maintenance requests.</span></span> <span data-ttu-id="a951d-108">A continuación se incluyen algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="a951d-108">Here are some examples:</span></span>

- <span data-ttu-id="a951d-109">Solicitudes de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="a951d-109">Maintenance requests</span></span>
- <span data-ttu-id="a951d-110">Notas</span><span class="sxs-lookup"><span data-stu-id="a951d-110">Notes</span></span>
- <span data-ttu-id="a951d-111">Correcciones o mejoras</span><span class="sxs-lookup"><span data-stu-id="a951d-111">Corrections or enhancements</span></span>
- <span data-ttu-id="a951d-112">Inversiones</span><span class="sxs-lookup"><span data-stu-id="a951d-112">Investments</span></span>
- <span data-ttu-id="a951d-113">Reparación interna (este tipo se usa cuando se reciben activos de otra ubicación para poder realizar un trabajo de mantenimiento o reparación y después se devuelve el activo cuando el trabajo se ha completado).</span><span class="sxs-lookup"><span data-stu-id="a951d-113">Depot repair (This type is used when you receive assets from another location so that you can do a maintenance or repair job, and you then return the asset after the job is completed.)</span></span>

## <a name="view-maintenance-requests"></a><span data-ttu-id="a951d-114">Ver solicitudes de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="a951d-114">View maintenance requests</span></span>

<span data-ttu-id="a951d-115">Para ver las solicitudes de mantenimiento, seleccione **Administración de activos** \> **Común** \> **Solicitudes de mantenimiento** \> **Todas las solicitudes de mantenimiento**, **Solicitudes de mantenimiento activas** o **Mis solicitudes de mantenimiento de ubicación funcional**.</span><span class="sxs-lookup"><span data-stu-id="a951d-115">To view maintenance requests, select **Asset management** \> **Common** \> **Maintenance requests** \> **All maintenance requests**, **Active maintenance requests**, or **My functional location maintenance requests**.</span></span> <span data-ttu-id="a951d-116">Cada página de lista muestra la información relacionada con una solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="a951d-116">Each list page shows some of the information that is related to a maintenance request.</span></span>

![Ver solicitudes de mantenimiento](media/01-manage-maintenance-requests.png)

> [!NOTE]
> <span data-ttu-id="a951d-118">Use la página de lista **Mis solicitudes de mantenimiento de ubicación funcional** para ver una lista de las solicitudes de mantenimiento que contienen ubicaciones funcionales con las que está relacionado como trabajador o los activos que están instalados en ubicaciones funcionales con las que está relacionado como trabajador.</span><span class="sxs-lookup"><span data-stu-id="a951d-118">Use the **My functional location maintenance requests** list page to view a list of maintenance requests that contain either functional locations that you're related to as a worker or assets that are installed on functional locations that you're related to as a worker.</span></span> <span data-ttu-id="a951d-119">(Para obtener información sobre cómo configurar ubicaciones funcionales en trabajadores de mantenimiento, consulte [Trabajadores de mantenimiento y grupos de trabajadores](../setup-for-objects/workers-and-worker-groups.md)).</span><span class="sxs-lookup"><span data-stu-id="a951d-119">(For information about how to set up functional locations on maintenance workers, see [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).)</span></span>
> 
> <span data-ttu-id="a951d-120">Aunque hay información de cuenta de cliente disponible en Administración de servicios de activos (mantenimiento externo), no está disponible en Administración de activos (mantenimiento interno).</span><span class="sxs-lookup"><span data-stu-id="a951d-120">Although customer account information is available in Asset Service Management (external maintenance), it isn't available in Asset Management (internal maintenance).</span></span>

<span data-ttu-id="a951d-121">Para abrir la vista de detalles de un registro, en la página de lista **Todas las solicitudes de mantenimiento** , en la vista de cuadrícula, seleccione un vínculo en la columna **Solicitud de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="a951d-121">To open the details view of a record, on the **All maintenance requests** list page, in the grid view, select a link in the **Maintenance request** column.</span></span>

![Ver detalles de la solicitud de mantenimiento](media/02-manage-maintenance-requests.png)

<span data-ttu-id="a951d-123">Los botones del panel de acciones se organizan en fichas.</span><span class="sxs-lookup"><span data-stu-id="a951d-123">The buttons on the Action Pane are organized on tabs.</span></span> <span data-ttu-id="a951d-124">La tabla siguiente describe brevemente los botones relacionados con Administración de activos.</span><span class="sxs-lookup"><span data-stu-id="a951d-124">The following table briefly describes the buttons that are related to Asset Management.</span></span>

| <span data-ttu-id="a951d-125">Nombre del botón</span><span class="sxs-lookup"><span data-stu-id="a951d-125">Button name</span></span>                      | <span data-ttu-id="a951d-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="a951d-126">Description</span></span> |
|----------------------------------|-------------|
| <span data-ttu-id="a951d-127">Editar</span><span class="sxs-lookup"><span data-stu-id="a951d-127">Edit</span></span>                             | <span data-ttu-id="a951d-128">Editar la solicitud de mantenimiento seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a951d-128">Edit the selected maintenance request.</span></span> |
| <span data-ttu-id="a951d-129">Nueva</span><span class="sxs-lookup"><span data-stu-id="a951d-129">New</span></span>                              | <span data-ttu-id="a951d-130">Crear una nueva solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="a951d-130">Create a new maintenance request.</span></span> |
| <span data-ttu-id="a951d-131">Borrar</span><span class="sxs-lookup"><span data-stu-id="a951d-131">Delete</span></span>                           | <span data-ttu-id="a951d-132">Eliminar la solicitud de mantenimiento seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a951d-132">Delete the selected maintenance request.</span></span> |
| <span data-ttu-id="a951d-133">Grupo de órdenes de trabajo</span><span class="sxs-lookup"><span data-stu-id="a951d-133">Work order pool</span></span>                  | <span data-ttu-id="a951d-134">Conectar la solicitud de mantenimiento seleccionada a un grupo de órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a951d-134">Connect the selected maintenance request to a work order pool.</span></span> |
| <span data-ttu-id="a951d-135">Orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="a951d-135">Work order</span></span>                       | <span data-ttu-id="a951d-136">Crear una orden de trabajo a partir de la solicitud de mantenimiento seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a951d-136">Create a work order, based on the selected maintenance request.</span></span> |
| <span data-ttu-id="a951d-137">Defecto de activo</span><span class="sxs-lookup"><span data-stu-id="a951d-137">Asset fault</span></span>                      | <span data-ttu-id="a951d-138">Haga click en **Defectos de activo**, donde puede crear un registro de defectos para la solicitud de mantenimiento seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a951d-138">Click **Asset faults**, where you can create a fault registration on the selected maintenance request.</span></span> |
| <span data-ttu-id="a951d-139">Órdenes de trabajo</span><span class="sxs-lookup"><span data-stu-id="a951d-139">Work orders</span></span>                      | <span data-ttu-id="a951d-140">Muestra una lista de todas las órdenes de trabajo que están conectadas a la solicitud de mantenimiento seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a951d-140">Show a list of all work orders that are connected to the selected maintenance request.</span></span> |
| <span data-ttu-id="a951d-141">Actualizar estado de solicitud de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="a951d-141">Update maintenance request state</span></span> | <span data-ttu-id="a951d-142">Actualizar el estado de la solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="a951d-142">Update the maintenance request state.</span></span> |
| <span data-ttu-id="a951d-143">Registro de estado de ciclo de vida</span><span class="sxs-lookup"><span data-stu-id="a951d-143">Lifecycle state log</span></span>              | <span data-ttu-id="a951d-144">Ver un registro que muestre los estados de ciclo de vida de la solicitud de mantenimiento seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a951d-144">View a log that shows the lifecycle states of the selected maintenance request.</span></span> |
| <span data-ttu-id="a951d-145">Detalles de solicitud de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="a951d-145">Maintenance request details</span></span>      | <span data-ttu-id="a951d-146">Imprimir un informe que muestre los detalles de la solicitud de mantenimiento seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a951d-146">Print a report that shows details of the selected maintenance request.</span></span> |
| <span data-ttu-id="a951d-147">Enviar activo en préstamo</span><span class="sxs-lookup"><span data-stu-id="a951d-147">Send loan asset</span></span>                  | <span data-ttu-id="a951d-148">Seleccione un activo en préstamo que debe ser una sustitución temporal del activo seleccionado en la solicitud de mantenimiento seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a951d-148">Select a loan asset that should be a temporary replacement for the asset that is selected on the selected maintenance request.</span></span> |
| <span data-ttu-id="a951d-149">Devolver activo en préstamo</span><span class="sxs-lookup"><span data-stu-id="a951d-149">Return loan asset</span></span>                | <span data-ttu-id="a951d-150">Registrar el activo en préstamo como devuelto.</span><span class="sxs-lookup"><span data-stu-id="a951d-150">Register the loan asset as returned.</span></span> |



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]