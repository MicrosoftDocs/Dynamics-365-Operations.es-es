---
title: Usar el espacio de trabajo móvil de gestión de activos
description: Este tema proporciona información acerca del espacio de trabajo móvil de gestión de activos.
author: josaw1
manager: tfehr
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.dyn365.ops.version: 10.0.5
ms.search.validFrom: 2019-08-31
ms.openlocfilehash: afda807714f14efb1cbab4ecfdd273aac52f4558
ms.sourcegitcommit: 995c678b4715be267f1f97148902a6b3dde3bcab
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "5033161"
---
# <a name="use-the-asset-management-mobile-workspace"></a><span data-ttu-id="091c8-103">Usar el espacio de trabajo móvil de gestión de activos</span><span class="sxs-lookup"><span data-stu-id="091c8-103">Use the Asset management mobile workspace</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="091c8-104">Este tema proporciona información acerca del espacio de trabajo móvil de **Administración de activos**.</span><span class="sxs-lookup"><span data-stu-id="091c8-104">This topic provides information about the **Asset management** mobile workspace.</span></span> <span data-ttu-id="091c8-105">Este espacio de trabajo permite a los usuarios ver y crear solicitudes de mantenimiento y órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="091c8-105">This workspace lets users view and create maintenance requests and work orders.</span></span> <span data-ttu-id="091c8-106">Los usuarios también pueden ver los trabajos de órdenes de trabajo asignadas en una vista de calendario o de lista.</span><span class="sxs-lookup"><span data-stu-id="091c8-106">Users can also view the assigned work order jobs in a calendar or list view.</span></span> <span data-ttu-id="091c8-107">Los activos y ubicaciones funcionales también se pueden ver y buscar.</span><span class="sxs-lookup"><span data-stu-id="091c8-107">Assets and functional locations can also be viewed and searched for.</span></span>

## <a name="overview"></a><span data-ttu-id="091c8-108">Visión general</span><span class="sxs-lookup"><span data-stu-id="091c8-108">Overview</span></span>

<span data-ttu-id="091c8-109">Administración de activos es un módulo avanzado para gestionar activos y trabajos de órdenes de trabajo en Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="091c8-109">Asset Management is an advanced module for managing assets and work order jobs in Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="091c8-110">El espacio de trabajo móvil **Administración de activos** permite a los usuarios ver rápidamente trabajos asignados del pedido de trabajo en el dispositivo móvil de su elección.</span><span class="sxs-lookup"><span data-stu-id="091c8-110">The **Asset management** mobile workspace lets users quickly view assigned work order jobs on the mobile device of their choice.</span></span> <span data-ttu-id="091c8-111">Los usuarios también pueden crear y gestionar solicitudes de mantenimiento, actualizar estados del ciclo de vida y ver detalles de la ubicación técnica y los activos mediante el dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="091c8-111">Users can also create and manage maintenance requests, update lifecycle state, and view asset and functional location details by using their mobile device.</span></span>

<span data-ttu-id="091c8-112">En concreto, el espacio de trabajo móvil **Gestión de activos** permite a los usuarios realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="091c8-112">Specifically, the **Asset management** mobile workspace lets users perform these tasks:</span></span>

- <span data-ttu-id="091c8-113">Crear, ver, y editar solicitudes de mantenimiento, realizar una foto o asociar una imagen existente a la solicitud de mantenimiento, cambiar el estado de ciclo de vida de la solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="091c8-113">Create, view, and edit maintenance requests, take a photo or attach an existing image to the maintenance request, change the maintenance request lifecycle state.</span></span> 
- <span data-ttu-id="091c8-114">Crear, ver, y editar órdenes de trabajo, realizar una foto o asociar una imagen existente a la orden de trabajo, cambiar el estado de ciclo de vida de la orden de trabajo, ver trabajos de órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="091c8-114">Create, view, and edit work orders, take a photo or attach an existing image to the work order, change the work order lifecycle state, view work order jobs.</span></span>
- <span data-ttu-id="091c8-115">Ver trabajos de órdenes de trabajo asignadas en una vista de calendario.</span><span class="sxs-lookup"><span data-stu-id="091c8-115">View assigned work order jobs in a calendar view.</span></span>
- <span data-ttu-id="091c8-116">Crear, ver, y editar trabajo de la orden de trabajo, actualizara contadores de activos, ver listas de comprobación de mantenimiento, ver y editar las notas de trabajo de la orden de trabajo, ver las herramientas necesarias para el trabajo de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="091c8-116">Create, view, and edit work order job, update asset counters, view maintenance checklist, view and edit work order job notes, view the tools required for the work order job.</span></span>
- <span data-ttu-id="091c8-117">Ver o buscar un activo específico o una ubicación técnica.</span><span class="sxs-lookup"><span data-stu-id="091c8-117">View or search for a specific asset or functional location.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="091c8-118">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="091c8-118">Prerequisites</span></span>

<span data-ttu-id="091c8-119">Antes de que pueda usar el espacio de trabajo móvil de **Administración de activos**, su administrador debe configurar las cuentas de usuario y trabajador requeridas, y publicar el espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="091c8-119">Before you can use the **Asset management** mobile workspace, your admin must set up the required user and worker accounts, and publish the workspace.</span></span> <span data-ttu-id="091c8-120">Para obtener más información, consulte [Configurar el espacio de trabajo móvil de Administración de activos](set-up-asset-management-mobile.md).</span><span class="sxs-lookup"><span data-stu-id="091c8-120">For more information, see [Set up the Asset management mobile workspace](set-up-asset-management-mobile.md).</span></span>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="091c8-121">Descargar e instalar la aplicación móvil</span><span class="sxs-lookup"><span data-stu-id="091c8-121">Download and install the mobile app</span></span>

<span data-ttu-id="091c8-122">Descargue e instale la aplicación móvil Dynamics 365 for Unified Operations:</span><span class="sxs-lookup"><span data-stu-id="091c8-122">Download and install the Dynamics 365 for Unified Operations mobile app:</span></span>

- [<span data-ttu-id="091c8-123">Para teléfonos Android</span><span class="sxs-lookup"><span data-stu-id="091c8-123">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
- [<span data-ttu-id="091c8-124">Para iPhones</span><span class="sxs-lookup"><span data-stu-id="091c8-124">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="091c8-125">Iniciar sesión en la aplicación móvil</span><span class="sxs-lookup"><span data-stu-id="091c8-125">Sign in to the mobile app</span></span>

1. <span data-ttu-id="091c8-126">Inicie la aplicación en su dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="091c8-126">Start the app on your mobile device.</span></span>

1. <span data-ttu-id="091c8-127">Escriba la URL de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="091c8-127">Enter your Dynamics 365 URL.</span></span>

1. <span data-ttu-id="091c8-128">La primera vez que se inicie sesión, se le solicitará su nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="091c8-128">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="091c8-129">Escriba sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="091c8-129">Enter your credentials.</span></span>

1. <span data-ttu-id="091c8-130">Tras iniciar sesión, se mostrarán los espacios de trabajo disponibles para su empresa.</span><span class="sxs-lookup"><span data-stu-id="091c8-130">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="091c8-131">Tenga en cuenta que si el administrador del sistema publica un nuevo espacio de trabajo más tarde, tendrá que actualizar la lista de espacios de trabajo móviles.</span><span class="sxs-lookup"><span data-stu-id="091c8-131">Note that if your system administrator publishes a new workspace later, you'll have to refresh the list of mobile workspaces.</span></span>

    <span data-ttu-id="091c8-132">![Seleccionar un espacio de trabajo](media/am-mobile-01.png "Seleccionar un espacio de trabajo")</span><span class="sxs-lookup"><span data-stu-id="091c8-132">![Select a workspace](media/am-mobile-01.png "Select a workspace")</span></span>

## <a name="view-assigned-work-order-jobs-in-calendar-view"></a><span data-ttu-id="091c8-133">Ver trabajos de órdenes de trabajo asignados en una vista de calendario</span><span class="sxs-lookup"><span data-stu-id="091c8-133">View assigned work order jobs in calendar view</span></span>

1. <span data-ttu-id="091c8-134">En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.</span><span class="sxs-lookup"><span data-stu-id="091c8-134">On your mobile device, open the **Asset management** workspace.</span></span>

1. <span data-ttu-id="091c8-135">Seleccione **Mi calendario de trabajos de la orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="091c8-135">Select **My work order jobs calendar**.</span></span>

1. <span data-ttu-id="091c8-136">Seleccione la fecha para la que desea ver trabajos de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="091c8-136">Select the date you want to view work order jobs for.</span></span> <span data-ttu-id="091c8-137">En la lista verá el identificador del activo y el identificador de la ubicación técnica de cada trabajo de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="091c8-137">In the list, you'll see the asset ID and functional location ID for each work order job.</span></span>

1. <span data-ttu-id="091c8-138">Seleccione un trabajo del pedido de trabajo en la lista para ver los detalles de trabajo: detalles de la ubicación técnica y los activos, así como otros vínculos de navegación para ver **Datos adjuntos**, **Listas de comprobación**, **Herramientas**, **Contadores de activos**, **Notas**, **Diarios**.</span><span class="sxs-lookup"><span data-stu-id="091c8-138">Select a work order job in the list to see job details: Asset and functional location details as well as other navigation links to view **Attachments**, **Checklists**, **Tools**, **Asset counters**, **Notes**, **Journals**.</span></span>

    <span data-ttu-id="091c8-139">![Ver trabajos de órdenes de trabajo asignados en una vista de calendario](media/am-mobile-02.png "Ver trabajos de órdenes de trabajo asignados en una vista de calendario")</span><span class="sxs-lookup"><span data-stu-id="091c8-139">![View assigned work order jobs in calendar view](media/am-mobile-02.png "View assigned work order jobs in calendar view")</span></span>

## <a name="create-a-work-order-job"></a><span data-ttu-id="091c8-140">Crear un trabajo de una orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="091c8-140">Create a work order job</span></span>

1. <span data-ttu-id="091c8-141">En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.</span><span class="sxs-lookup"><span data-stu-id="091c8-141">On your mobile device, open the **Asset management** workspace.</span></span>

1. <span data-ttu-id="091c8-142">Seleccione **Todos los pedidos de trabajo de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="091c8-142">Select **All maintenance work orders**.</span></span>

1. <span data-ttu-id="091c8-143">Seleccione el pedido de trabajo para el que desea crear un nuevo trabajo de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="091c8-143">Select the work order you want to create a new work order job for.</span></span>

1. <span data-ttu-id="091c8-144">Seleccione el botón **Agregar línea**.</span><span class="sxs-lookup"><span data-stu-id="091c8-144">Select the **Add line** button.</span></span>

1. <span data-ttu-id="091c8-145">Seleccione el **Activo** para el que desea crear un nuevo trabajo de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="091c8-145">Select the **Asset** you want to create a work order job for.</span></span>

1. <span data-ttu-id="091c8-146">Seleccione **Tipo de trabajo de mantenimiento**, **Variante del tipo de trabajo de mantenimiento** y **Comercio**.</span><span class="sxs-lookup"><span data-stu-id="091c8-146">Select **Maintenance job type**, **Maintenance job type variant** and **Trade**.</span></span>

1. <span data-ttu-id="091c8-147">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="091c8-147">Select **Done**.</span></span>

    <span data-ttu-id="091c8-148">![La pantalla Agregar línea](media/am-mobile-03.png "La pantalla Agregar línea")</span><span class="sxs-lookup"><span data-stu-id="091c8-148">![The Add line screen](media/am-mobile-03.png "The Add line screen")</span></span>


## <a name="add-attachment-to-a-work-order-job"></a><span data-ttu-id="091c8-149">Agregar datos adjuntos a un trabajo de pedido de trabajo</span><span class="sxs-lookup"><span data-stu-id="091c8-149">Add attachment to a work order job</span></span>

1. <span data-ttu-id="091c8-150">En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.</span><span class="sxs-lookup"><span data-stu-id="091c8-150">On your mobile device, open the **Asset management** workspace.</span></span>

1. <span data-ttu-id="091c8-151">Seleccione **Todos los pedidos de trabajo de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="091c8-151">Select **All maintenance work orders**.</span></span>

1. <span data-ttu-id="091c8-152">Seleccione la orden de trabajo > trabajo de la orden de trabajo al que desea agregar datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="091c8-152">Select the work order > work order job you want to add an attachment to.</span></span>
    - <span data-ttu-id="091c8-153">Como alternativa, también puede seleccionar **Mi calendario de los trabajos de la orden de trabajo** o **Mi lista de trabajos de la orden de trabajo** en la página principal para navegar a la página **Detalles del trabajo de la orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="091c8-153">Alternatively, you can also select **My work order jobs calendar** or **My work order jobs list** on the home page to navigate to the **Work order job details** page.</span></span>

1. <span data-ttu-id="091c8-154">Seleccione **Datos adjuntos** en la página **Detalles del trabajo de la orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="091c8-154">Select **Attachments** on the **Work order job details** page.</span></span>

1. <span data-ttu-id="091c8-155">Se verán los datos adjuntos existentes en el trabajo del pedido de trabajo.</span><span class="sxs-lookup"><span data-stu-id="091c8-155">You'll see existing attachments on the work order job.</span></span> <span data-ttu-id="091c8-156">Seleccione **Agregar datos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="091c8-156">Select **Add attachment**.</span></span>

1. <span data-ttu-id="091c8-157">Especifique el **Nombre** y las **Notas** para los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="091c8-157">Enter **Name** and **Notes** for the attachment.</span></span>

1. <span data-ttu-id="091c8-158">Seleccione **Elegir imagen** para seleccionar una foto de la galería móvil, o **Tomar foto** para tomar una foto.</span><span class="sxs-lookup"><span data-stu-id="091c8-158">Select **Choose image** to select a photo from the mobile gallery, or **Take photo** to take a photo.</span></span>

1. <span data-ttu-id="091c8-159">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="091c8-159">Select **Done**.</span></span>

    <span data-ttu-id="091c8-160">![Ver y agregar archivos adjuntos para un trabajo de una orden de trabajo](media/am-mobile-04.png "Ver y agregar archivos adjuntos para un trabajo de una orden de trabajo")</span><span class="sxs-lookup"><span data-stu-id="091c8-160">![View and add attachments for a work order job](media/am-mobile-04.png "View and add attachments for a work order job")</span></span>

## <a name="view-maintenance-checklist-on-a-work-order-job"></a><span data-ttu-id="091c8-161">Ver la lista de comprobación de mantenimiento de un trabajo de una orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="091c8-161">View maintenance checklist on a work order job</span></span>

1. <span data-ttu-id="091c8-162">En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.</span><span class="sxs-lookup"><span data-stu-id="091c8-162">On your mobile device, open the **Asset management** workspace.</span></span>

1. <span data-ttu-id="091c8-163">Seleccione **Todos los pedidos de trabajo de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="091c8-163">Select **All maintenance work orders**.</span></span>

1. <span data-ttu-id="091c8-164">Seleccione la orden de trabajo > trabajo de orden de trabajo para el que desea ver las listas de comprobación.</span><span class="sxs-lookup"><span data-stu-id="091c8-164">Select the work order > work order job you want to view checklists for.</span></span>
    - <span data-ttu-id="091c8-165">Como alternativa, también puede seleccionar **Mi calendario de los trabajos de la orden de trabajo** o **Mi lista de trabajos de la orden de trabajo** en la página principal para navegar a la página **Detalles del trabajo de la orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="091c8-165">Alternatively, you can also select **My work order jobs calendar** or **My work order jobs list** on the home page to navigate to the **work order job details** page.</span></span>

1. <span data-ttu-id="091c8-166">Seleccione **Listas de comprobación** en la página **Detalles del trabajo de la orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="091c8-166">Select **Checklists** on the **Work order job details** page.</span></span>

1. <span data-ttu-id="091c8-167">Se verá una lista de líneas de la lista de comprobación relacionadas con el trabajo de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="091c8-167">You'll see a list of checklist lines related to the work order job.</span></span> <span data-ttu-id="091c8-168">Seleccione una línea de la lista de comprobación para ver **Instrucciones** y agregar **Notas**.</span><span class="sxs-lookup"><span data-stu-id="091c8-168">Select a checklist line to view **Instructions** and add **Notes**.</span></span>

1. <span data-ttu-id="091c8-169">Seleccione el botón Atrás (**<**) para volver a la página anterior.</span><span class="sxs-lookup"><span data-stu-id="091c8-169">Select the back button (**<**) to return to the previous page.</span></span>

    <span data-ttu-id="091c8-170">![Lista de comprobación de mantenimiento y detalles de la línea](media/am-mobile-05.png "Lista de comprobación de mantenimiento y detalles de la línea")</span><span class="sxs-lookup"><span data-stu-id="091c8-170">![Maintenance checklist and line details](media/am-mobile-05.png "Maintenance checklist and line details")</span></span>

## <a name="view-and-update-asset-counters-on-a-work-order-job"></a><span data-ttu-id="091c8-171">Ver y actualizar contadores de activos en un trabajo de pedidos de trabajo</span><span class="sxs-lookup"><span data-stu-id="091c8-171">View and update asset counters on a work order job</span></span>

1. <span data-ttu-id="091c8-172">En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.</span><span class="sxs-lookup"><span data-stu-id="091c8-172">On your mobile device, open the **Asset management** workspace.</span></span>

1. <span data-ttu-id="091c8-173">Seleccione **Todos los pedidos de trabajo de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="091c8-173">Select **All maintenance work orders**.</span></span>

1. <span data-ttu-id="091c8-174">Seleccione la orden de trabajo > trabajo de orden de trabajo para el que desea ver los contadores de activos.</span><span class="sxs-lookup"><span data-stu-id="091c8-174">Select the work order > work order job you want to view asset counters for.</span></span>
    - <span data-ttu-id="091c8-175">Como alternativa, también puede seleccionar **Mi calendario de los trabajos de la orden de trabajo** o **Mi lista de trabajos de la orden de trabajo** en la página principal para navegar a la página **Detalles del trabajo de la orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="091c8-175">Alternatively, you can also select **My work order jobs calendar** or **My work order jobs list** on the home page to navigate to the **work order job details** page.</span></span>

1. <span data-ttu-id="091c8-176">Seleccione **Contadores de activos** en la página **Detalles del trabajo de la orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="091c8-176">Select **Asset counters** on the **Work order job details** page.</span></span>

1. <span data-ttu-id="091c8-177">Se verá una lista de contadores de activos relacionados con el trabajo de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="091c8-177">You see a list of asset counters related to the work order job.</span></span> <span data-ttu-id="091c8-178">Seleccione el icono de lápiz en una línea del contador de activos para actualizar el valor de un contador.</span><span class="sxs-lookup"><span data-stu-id="091c8-178">Select the pencil icon on an asset counter line to update the counter value.</span></span>

1. <span data-ttu-id="091c8-179">Introduzca un nuevo valor de contador y seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="091c8-179">Enter a new counter value, and select **Done**.</span></span>

    <span data-ttu-id="091c8-180">![Ver y actualizar los contadores de activos](media/am-mobile-06.png "Ver y actualizar los contadores de activos")</span><span class="sxs-lookup"><span data-stu-id="091c8-180">![View and update asset counters](media/am-mobile-06.png "View and update asset counters")</span></span>

## <a name="register-consumption-on-a-work-order-job"></a><span data-ttu-id="091c8-181">Registrar el consumo en un trabajo de orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="091c8-181">Register consumption on a work order job</span></span>

1. <span data-ttu-id="091c8-182">En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.</span><span class="sxs-lookup"><span data-stu-id="091c8-182">On your mobile device, open the **Asset management** workspace.</span></span>

1. <span data-ttu-id="091c8-183">Seleccione **Todos los pedidos de trabajo de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="091c8-183">Select **All maintenance work orders**.</span></span>

1. <span data-ttu-id="091c8-184">Seleccione la orden de trabajo > trabajo de orden de trabajo para el que desea agregar registros de consumo.</span><span class="sxs-lookup"><span data-stu-id="091c8-184">Select the work order > work order job you want to add consumption registrations for.</span></span>
    - <span data-ttu-id="091c8-185">Como alternativa, también puede seleccionar **Mi calendario de los trabajos de la orden de trabajo** o **Mi lista de trabajos de la orden de trabajo** en la página principal para navegar a la página **Detalles del trabajo de la orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="091c8-185">Alternatively, you can also select **My work order jobs calendar** or **My work order jobs list** on the home page to navigate to the **work order job details** page.</span></span>

1. <span data-ttu-id="091c8-186">Seleccione **Diarios** en la página **Detalles del trabajo de la orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="091c8-186">Select **Journals** on the **Work order job details** page.</span></span>

1. <span data-ttu-id="091c8-187">Seleccione **Agregar horas** para crear registros de horas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="091c8-187">Select **Add hours** to create work hour registrations.</span></span>
    1. <span data-ttu-id="091c8-188">Seleccionar la **categoría** en la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="091c8-188">Select the **Category** from the lookup.</span></span>
    1. <span data-ttu-id="091c8-189">En el campo **Horas**, especifique el número de horas de trabajo gastadas en el trabajo de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="091c8-189">In the **Hours** field, enter the number of work hours spent on the work order job.</span></span>
    1. <span data-ttu-id="091c8-190">Seleccione la **propiedad del línea** adecuada.</span><span class="sxs-lookup"><span data-stu-id="091c8-190">Select the appropriate **Line property**.</span></span>
    1. <span data-ttu-id="091c8-191">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="091c8-191">Select **Done**.</span></span>

1. <span data-ttu-id="091c8-192">Seleccione **Agregar artículos** para crear registros de artículos.</span><span class="sxs-lookup"><span data-stu-id="091c8-192">Select **Add items** to create item registrations.</span></span>
    1. <span data-ttu-id="091c8-193">Seleccione el **Número de artículo** en la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="091c8-193">Select the **Item number** from the lookup.</span></span>
    1. <span data-ttu-id="091c8-194">Seleccione el **Sitio** en la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="091c8-194">Select the **Site** from the lookup.</span></span>
    1. <span data-ttu-id="091c8-195">Indique la **cantidad** de artículos consumidos.</span><span class="sxs-lookup"><span data-stu-id="091c8-195">Enter the **Quantity** of items consumed.</span></span>
    1. <span data-ttu-id="091c8-196">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="091c8-196">Select **Done**.</span></span>

1. <span data-ttu-id="091c8-197">Seleccione **Agregar gasto** para crear registros de gastos.</span><span class="sxs-lookup"><span data-stu-id="091c8-197">Select **Add expense** to create expense registrations.</span></span>
    1. <span data-ttu-id="091c8-198">Seleccionar la **categoría** en la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="091c8-198">Select the **Category** from the lookup.</span></span>
    1. <span data-ttu-id="091c8-199">Escriba la cantidad para el registro de gasto.</span><span class="sxs-lookup"><span data-stu-id="091c8-199">Enter the quantity for the expense registration.</span></span>
    1. <span data-ttu-id="091c8-200">Seleccione la **divisa de ventas** en la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="091c8-200">Select the **Sales currency** from the lookup.</span></span>
    1. <span data-ttu-id="091c8-201">Escriba el **Precio de coste** para el registro de gasto.</span><span class="sxs-lookup"><span data-stu-id="091c8-201">Enter the **Cost price** for the expense registration.</span></span>
    1. <span data-ttu-id="091c8-202">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="091c8-202">Select **Done**.</span></span>

    <span data-ttu-id="091c8-203">![Actualizar un diario de órdenes de trabajo](media/am-mobile-07.png "Actualizar un diario de órdenes de trabajo")</span><span class="sxs-lookup"><span data-stu-id="091c8-203">![Update a work order journal](media/am-mobile-07.png "Update a work order journal")</span></span>

## <a name="update-lifecycle-state-on-a-work-order"></a><span data-ttu-id="091c8-204">Actualizar el estados de ciclo de vida de una orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="091c8-204">Update lifecycle state on a work order</span></span>

1. <span data-ttu-id="091c8-205">En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.</span><span class="sxs-lookup"><span data-stu-id="091c8-205">On your mobile device, open the **Asset management** workspace.</span></span>

1. <span data-ttu-id="091c8-206">Seleccione **Todos los pedidos de trabajo de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="091c8-206">Select **All maintenance work orders**.</span></span>

1. <span data-ttu-id="091c8-207">Seleccione la orden de trabajo para la que desea actualizar el estado de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="091c8-207">Select the work order you want to update lifecycle state for.</span></span>

1. <span data-ttu-id="091c8-208">Seleccione el botón **Actualizar estado** en la parte inferior de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="091c8-208">Select the **Update state** button at the bottom of the screen.</span></span>

1. <span data-ttu-id="091c8-209">Seleccione un nuev estado del ciclo de vida de la lista.</span><span class="sxs-lookup"><span data-stu-id="091c8-209">Select a new lifecycle state from the list.</span></span>

1. <span data-ttu-id="091c8-210">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="091c8-210">Select **Done**.</span></span>

    <span data-ttu-id="091c8-211">![Actualizar el estados de ciclo de vida de una orden de trabajo](media/am-mobile-08.png "Actualizar el estados de ciclo de vida de una orden de trabajo")</span><span class="sxs-lookup"><span data-stu-id="091c8-211">![Update lifecycle state on a work order](media/am-mobile-08.png "Update lifecycle state on a work order")</span></span>

## <a name="create-a-maintenance-request"></a><span data-ttu-id="091c8-212">Crear una solicitud de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="091c8-212">Create a maintenance request</span></span>

1. <span data-ttu-id="091c8-213">En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.</span><span class="sxs-lookup"><span data-stu-id="091c8-213">On your mobile device, open the **Asset management** workspace.</span></span>

1. <span data-ttu-id="091c8-214">Seleccione **Todas las solicitudes de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="091c8-214">Select **All maintenance requests**.</span></span>

1. <span data-ttu-id="091c8-215">Seleccione **Acciones** en la parte inferior de la pantalla, y seleccione **Crear solicitud de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="091c8-215">Select **Actions** at the bottom of the screen, and select **Create maintenance request**.</span></span>

1. <span data-ttu-id="091c8-216">Si la secuencia numérica está habilitada para las solicitudes de mantenimiento en **Administración de activos**, se oculta el campo **Solicitud de mantenimiento** porque se completa automáticamente. Si el campo **Solicitud de mantenimiento** está visible, especifique un identificador de solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="091c8-216">If number sequence is enabled for maintenance requests in **Asset management**, the **Maintenance request** field is hidden because it is automatically filled out. If the **Maintenance request** field is visible, enter a maintenance request ID.</span></span>

1. <span data-ttu-id="091c8-217">Seleccione un **Tipo de solicitud de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="091c8-217">Select a **Maintenance request type**.</span></span>

1. <span data-ttu-id="091c8-218">Especifique una **Descripción** para la solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="091c8-218">Enter a **Description** for the maintenance request.</span></span>

1. <span data-ttu-id="091c8-219">Seleccionar el **Activo** para el que desea crear la solicitud.</span><span class="sxs-lookup"><span data-stu-id="091c8-219">Select the **Asset** you want to create the request for.</span></span>

1. <span data-ttu-id="091c8-220">Seleccione el **Nivel de servicio** para la solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="091c8-220">Select the **Service level** for the maintenance request.</span></span>

1. <span data-ttu-id="091c8-221">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="091c8-221">Select **Done**.</span></span>

    <span data-ttu-id="091c8-222">![Crear una solicitud de mantenimiento](media/am-mobile-09.png "Crear una solicitud de mantenimiento")</span><span class="sxs-lookup"><span data-stu-id="091c8-222">![Create a maintenance request](media/am-mobile-09.png "Create a maintenance request")</span></span>

## <a name="add-attachment-to-a-maintenance-request"></a><span data-ttu-id="091c8-223">Agregar datos adjuntos a una solicitud de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="091c8-223">Add attachment to a maintenance request</span></span>

1. <span data-ttu-id="091c8-224">En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.</span><span class="sxs-lookup"><span data-stu-id="091c8-224">On your mobile device, open the **Asset management** workspace.</span></span>

1. <span data-ttu-id="091c8-225">Seleccione **Todas las solicitudes de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="091c8-225">Select **All maintenance requests**.</span></span>

1. <span data-ttu-id="091c8-226">Seleccione la solicitud de mantenimiento a la que desea agregar un archivo adjunto.</span><span class="sxs-lookup"><span data-stu-id="091c8-226">Select the maintenance request you want to add an attachment to.</span></span>

1. <span data-ttu-id="091c8-227">Seleccione **Datos adjuntos** en la parte inferior de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="091c8-227">Select **Attachments** at the bottom of the screen.</span></span>

1. <span data-ttu-id="091c8-228">Seleccione **Agregar datos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="091c8-228">Select **Add attachments**.</span></span>

1. <span data-ttu-id="091c8-229">Especifique el **Nombre** y las **Notas** para los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="091c8-229">Enter **Name** and **Notes** for the attachment.</span></span>

1. <span data-ttu-id="091c8-230">Seleccione **Elegir imagen** para seleccionar una foto de la galería móvil o **Tomar foto** para tomar una foto.</span><span class="sxs-lookup"><span data-stu-id="091c8-230">Select **Choose image** to select a photo from the mobile gallery or **Take photo** to take a photo.</span></span>

1. <span data-ttu-id="091c8-231">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="091c8-231">Select **Done**.</span></span>

    <span data-ttu-id="091c8-232">![Agregar un archivo adjunto a una solicitud de mantenimiento](media/am-mobile-10.png "Agregar un archivo adjunto a una solicitud de mantenimiento")</span><span class="sxs-lookup"><span data-stu-id="091c8-232">![Add an attachment to a maintenance request](media/am-mobile-10.png "Add an attachment to a maintenance request")</span></span>
