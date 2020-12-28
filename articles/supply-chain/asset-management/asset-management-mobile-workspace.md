---
title: Espacio de trabajo móvil de gestión de activos
description: Este tema proporciona información acerca del espacio de trabajo móvil de gestión de activos.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.dyn365.ops.version: 10.0.5
ms.search.validFrom: 2019-08-31
ms.openlocfilehash: 525f21d076027f1bf339e59fd0e346706044839c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436681"
---
# <a name="asset-management-mobile-workspace"></a><span data-ttu-id="72126-103">Espacio de trabajo móvil de gestión de activos</span><span class="sxs-lookup"><span data-stu-id="72126-103">Asset management mobile workspace</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="72126-104">Este tema proporciona información acerca del espacio de trabajo móvil de gestión de activos.</span><span class="sxs-lookup"><span data-stu-id="72126-104">This topic provides information about the Asset management mobile workspace.</span></span> <span data-ttu-id="72126-105">Este espacio de trabajo permite a los usuarios ver y crear solicitudes de mantenimiento y órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="72126-105">This workspace lets users view and create maintenance requests and work orders.</span></span> <span data-ttu-id="72126-106">Los usuarios también pueden ver los trabajos de órdenes de trabajo asignadas en una vista de calendario o de lista.</span><span class="sxs-lookup"><span data-stu-id="72126-106">Users can also view the assigned work order jobs in a calendar or list view.</span></span> <span data-ttu-id="72126-107">Los activos y ubicaciones funcionales también se pueden ver y buscar.</span><span class="sxs-lookup"><span data-stu-id="72126-107">Assets and functional locations can also be viewed and searched for.</span></span>


## <a name="overview"></a><span data-ttu-id="72126-108">Visión general</span><span class="sxs-lookup"><span data-stu-id="72126-108">Overview</span></span>

<span data-ttu-id="72126-109">Administración de activos es un módulo avanzado para gestionar activos y trabajos de órdenes de trabajo en Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="72126-109">Asset Management is an advanced module for managing assets and work order jobs in Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="72126-110">El espacio de trabajo móvil **Administración de activos** permite a los usuarios ver rápidamente trabajos asignados del pedido de trabajo en el dispositivo móvil de su elección.</span><span class="sxs-lookup"><span data-stu-id="72126-110">The **Asset management** mobile workspace lets users quickly view assigned work order jobs on the mobile device of their choice.</span></span> <span data-ttu-id="72126-111">Los usuarios también pueden crear y gestionar solicitudes de mantenimiento, actualizar estados del ciclo de vida y ver detalles de la ubicación técnica y los activos mediante el dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="72126-111">Users can also create and manage maintenance requests, update lifecycle state, and view asset and functional location details by using their mobile device.</span></span>

<span data-ttu-id="72126-112">En concreto, el espacio de trabajo móvil **Gestión de activos** permite a los usuarios realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="72126-112">Specifically, the **Asset management** mobile workspace lets users perform these tasks:</span></span>

- <span data-ttu-id="72126-113">Crear, ver, y editar solicitudes de mantenimiento, realizar una foto o asociar una imagen existente a la solicitud de mantenimiento, cambiar el estado de ciclo de vida de la solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="72126-113">Create, view, and edit maintenance requests, take a photo or attach an existing image to the maintenance request, change the maintenance request lifecycle state.</span></span> 
- <span data-ttu-id="72126-114">Crear, ver, y editar órdenes de trabajo, realizar una foto o asociar una imagen existente a la orden de trabajo, cambiar el estado de ciclo de vida de la orden de trabajo, ver trabajos de órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="72126-114">Create, view, and edit work orders, take a photo or attach an existing image to the work order, change the work order lifecycle state, view work order jobs.</span></span>
- <span data-ttu-id="72126-115">Ver trabajos de órdenes de trabajo asignadas en una vista de calendario.</span><span class="sxs-lookup"><span data-stu-id="72126-115">View assigned work order jobs in a calendar view.</span></span>
- <span data-ttu-id="72126-116">Crear, ver, y editar trabajo de la orden de trabajo, actualizara contadores de activos, ver listas de comprobación de mantenimiento, ver y editar las notas de trabajo de la orden de trabajo, ver las herramientas necesarias para el trabajo de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="72126-116">Create, view, and edit work order job, update asset counters, view maintenance checklist, view and edit work order job notes, view the tools required for the work order job.</span></span>
- <span data-ttu-id="72126-117">Ver o buscar un activo específico o una ubicación técnica.</span><span class="sxs-lookup"><span data-stu-id="72126-117">View or search for a specific asset or functional location.</span></span>


## <a name="prerequisites"></a><span data-ttu-id="72126-118">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="72126-118">Prerequisites</span></span>

<span data-ttu-id="72126-119">Los requisitos previos varían, en función de la versión de Dynamics 365 Supply Chain Management que se ha implementado para su organización.</span><span class="sxs-lookup"><span data-stu-id="72126-119">The prerequisites vary, based on the version of Dynamics 365 Supply Chain Management that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-supply-chain-management"></a><span data-ttu-id="72126-120">Requisitos previos si usa Microsoft Dynamics 365 Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="72126-120">Prerequisites if you use Microsoft Dynamics 365 Supply Chain Management</span></span> 
<span data-ttu-id="72126-121">Si Microsoft Dynamics 365 Supply Chain Management se ha implementado para su organización, el administrador del sistema debe publicar el espacio de trabajo móvil **Administración de activos**.</span><span class="sxs-lookup"><span data-stu-id="72126-121">If Microsoft Dynamics 365 Supply Chain Management has been deployed for your organization, the system administrator must publish the **Asset management** mobile workspace.</span></span> <span data-ttu-id="72126-122">Para obtener instrucciones, consulte [Publicar un espacio de trabajo móvil](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="72126-122">For instructions, see [Publish a mobile workspace](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span></span>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="72126-123">Descargar e instalar la aplicación móvil</span><span class="sxs-lookup"><span data-stu-id="72126-123">Download and install the mobile app</span></span>
<span data-ttu-id="72126-124">Descargue e instale la aplicación móvil Dynamics 365 for Unified Operations:</span><span class="sxs-lookup"><span data-stu-id="72126-124">Download and install the Dynamics 365 for Unified Operations mobile app:</span></span>

- [<span data-ttu-id="72126-125">Para teléfonos Android</span><span class="sxs-lookup"><span data-stu-id="72126-125">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
- [<span data-ttu-id="72126-126">Para iPhones</span><span class="sxs-lookup"><span data-stu-id="72126-126">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="72126-127">Iniciar sesión en la aplicación móvil</span><span class="sxs-lookup"><span data-stu-id="72126-127">Sign in to the mobile app</span></span>
1. <span data-ttu-id="72126-128">Inicie la aplicación en su dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="72126-128">Start the app on your mobile device.</span></span>

2. <span data-ttu-id="72126-129">Escriba la URL de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="72126-129">Enter your Dynamics 365 URL.</span></span>

3. <span data-ttu-id="72126-130">La primera vez que se inicie sesión, se le solicitará su nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="72126-130">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="72126-131">Escriba sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="72126-131">Enter your credentials.</span></span>

4. <span data-ttu-id="72126-132">Tras iniciar sesión, se mostrarán los espacios de trabajo disponibles para su empresa.</span><span class="sxs-lookup"><span data-stu-id="72126-132">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="72126-133">Tenga en cuenta que si el administrador del sistema publica un nuevo espacio de trabajo más tarde, tendrá que actualizar la lista de espacios de trabajo móviles.</span><span class="sxs-lookup"><span data-stu-id="72126-133">Note that if your system administrator publishes a new workspace later, you'll have to refresh the list of mobile workspaces.</span></span>

![Figura 1](media/am-mobile-01.png)


## <a name="view-assigned-work-order-jobs-in-calendar-view"></a><span data-ttu-id="72126-135">Ver trabajos de órdenes de trabajo asignados en una vista de calendario</span><span class="sxs-lookup"><span data-stu-id="72126-135">View assigned work order jobs in calendar view</span></span>

1. <span data-ttu-id="72126-136">En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.</span><span class="sxs-lookup"><span data-stu-id="72126-136">On your mobile device, open the **Asset management** workspace.</span></span>

2. <span data-ttu-id="72126-137">Seleccione **Mi calendario de trabajos de la orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="72126-137">Select **My work order jobs calendar**.</span></span>

3. <span data-ttu-id="72126-138">Seleccione la fecha para la que desea ver trabajos de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="72126-138">Select the date you want to view work order jobs for.</span></span> <span data-ttu-id="72126-139">En la lista verá el identificador del activo y el identificador de la ubicación técnica de cada trabajo de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="72126-139">In the list, you'll see the asset ID and functional location ID for each work order job.</span></span>

4. <span data-ttu-id="72126-140">Seleccione un trabajo del pedido de trabajo en la lista para ver los detalles de trabajo: detalles de la ubicación técnica y los activos, así como otros vínculos de navegación para ver **Datos adjuntos**, **Listas de comprobación**, **Herramientas**, **Contadores de activos**, **Notas**, **Diarios**.</span><span class="sxs-lookup"><span data-stu-id="72126-140">Select a work order job in the list to see job details: Asset and functional location details as well as other navigation links to view **Attachments**, **Checklists**, **Tools**, **Asset counters**, **Notes**, **Journals**.</span></span>

![Figura 2](media/am-mobile-02.png)


## <a name="create-a-work-order-job"></a><span data-ttu-id="72126-142">Crear un trabajo de una orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="72126-142">Create a work order job</span></span>

1. <span data-ttu-id="72126-143">En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.</span><span class="sxs-lookup"><span data-stu-id="72126-143">On your mobile device, open the **Asset management** workspace.</span></span>

2. <span data-ttu-id="72126-144">Seleccione **Todos los pedidos de trabajo de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="72126-144">Select **All maintenance work orders**.</span></span>

3. <span data-ttu-id="72126-145">Seleccione el pedido de trabajo para el que desea crear un nuevo trabajo de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="72126-145">Select the work order you want to create a new work order job for.</span></span>

4. <span data-ttu-id="72126-146">Seleccione el botón **Agregar línea**.</span><span class="sxs-lookup"><span data-stu-id="72126-146">Select the **Add line** button.</span></span>

5. <span data-ttu-id="72126-147">Seleccione el **Activo** para el que desea crear un nuevo trabajo de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="72126-147">Select the **Asset** you want to create a work order job for.</span></span>

6. <span data-ttu-id="72126-148">Seleccione **Tipo de trabajo de mantenimiento**, **Variante del tipo de trabajo de mantenimiento** y **Comercio**.</span><span class="sxs-lookup"><span data-stu-id="72126-148">Select **Maintenance job type**, **Maintenance job type variant** and **Trade**.</span></span>

7. <span data-ttu-id="72126-149">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="72126-149">Select **Done**.</span></span>

![Figura 3](media/am-mobile-03.png)


## <a name="add-attachment-to-a-work-order-job"></a><span data-ttu-id="72126-151">Agregar datos adjuntos a un trabajo de pedido de trabajo</span><span class="sxs-lookup"><span data-stu-id="72126-151">Add attachment to a work order job</span></span>

1. <span data-ttu-id="72126-152">En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.</span><span class="sxs-lookup"><span data-stu-id="72126-152">On your mobile device, open the **Asset management** workspace.</span></span>

2. <span data-ttu-id="72126-153">Seleccione **Todos los pedidos de trabajo de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="72126-153">Select **All maintenance work orders**.</span></span>

3. <span data-ttu-id="72126-154">Seleccione la orden de trabajo > trabajo de la orden de trabajo al que desea agregar datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="72126-154">Select the work order > work order job you want to add an attachment to.</span></span>
    - <span data-ttu-id="72126-155">Como alternativa, también puede seleccionar **Mi calendario de los trabajos de la orden de trabajo** o **Mi lista de trabajos de la orden de trabajo** en la página principal para navegar a la página **Detalles del trabajo de la orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="72126-155">Alternatively, you can also select **My work order jobs calendar** or **My work order jobs list** on the home page to navigate to the **Work order job details** page.</span></span>

4. <span data-ttu-id="72126-156">Seleccione **Datos adjuntos** en la página **Detalles del trabajo de la orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="72126-156">Select **Attachments** on the **Work order job details** page.</span></span>

5. <span data-ttu-id="72126-157">Se verán los datos adjuntos existentes en el trabajo del pedido de trabajo.</span><span class="sxs-lookup"><span data-stu-id="72126-157">You'll see existing attachments on the work order job.</span></span> <span data-ttu-id="72126-158">Seleccione **Agregar datos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="72126-158">Select **Add attachment**.</span></span>

6. <span data-ttu-id="72126-159">Especifique el **Nombre** y las **Notas** para los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="72126-159">Enter **Name** and **Notes** for the attachment.</span></span>

7. <span data-ttu-id="72126-160">Seleccione **Elegir imagen** para seleccionar una foto de la galería móvil, o **Tomar foto** para tomar una foto.</span><span class="sxs-lookup"><span data-stu-id="72126-160">Select **Choose image** to select a photo from the mobile gallery, or **Take photo** to take a photo.</span></span>

8. <span data-ttu-id="72126-161">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="72126-161">Select **Done**.</span></span>

![Figura 4](media/am-mobile-04.png)


## <a name="view-maintenance-checklist-on-a-work-order-job"></a><span data-ttu-id="72126-163">Ver la lista de comprobación de mantenimiento de un trabajo de una orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="72126-163">View maintenance checklist on a work order job</span></span>

1. <span data-ttu-id="72126-164">En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.</span><span class="sxs-lookup"><span data-stu-id="72126-164">On your mobile device, open the **Asset management** workspace.</span></span>

2. <span data-ttu-id="72126-165">Seleccione **Todos los pedidos de trabajo de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="72126-165">Select **All maintenance work orders**.</span></span>

3. <span data-ttu-id="72126-166">Seleccione la orden de trabajo > trabajo de orden de trabajo para el que desea ver las listas de comprobación.</span><span class="sxs-lookup"><span data-stu-id="72126-166">Select the work order > work order job you want to view checklists for.</span></span>
    - <span data-ttu-id="72126-167">Como alternativa, también puede seleccionar **Mi calendario de los trabajos de la orden de trabajo** o **Mi lista de trabajos de la orden de trabajo** en la página principal para navegar a la página **Detalles del trabajo de la orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="72126-167">Alternatively, you can also select **My work order jobs calendar** or **My work order jobs list** on the home page to navigate to the **work order job details** page.</span></span>

4. <span data-ttu-id="72126-168">Seleccione **Listas de comprobación** en la página **Detalles del trabajo de la orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="72126-168">Select **Checklists** on the **Work order job details** page.</span></span>

5. <span data-ttu-id="72126-169">Se verá una lista de líneas de la lista de comprobación relacionadas con el trabajo de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="72126-169">You'll see a list of checklist lines related to the work order job.</span></span> <span data-ttu-id="72126-170">Seleccione una línea de la lista de comprobación para ver **Instrucciones** y agregar **Notas**.</span><span class="sxs-lookup"><span data-stu-id="72126-170">Select a checklist line to view **Instructions** and add **Notes**.</span></span>

6. <span data-ttu-id="72126-171">Seleccione el botón Atrás (**<**) para volver a la página anterior.</span><span class="sxs-lookup"><span data-stu-id="72126-171">Select the back button (**<**) to return to the previous page.</span></span>

![Figura 5](media/am-mobile-05.png)


## <a name="view-and-update-asset-counters-on-a-work-order-job"></a><span data-ttu-id="72126-173">Ver y actualizar contadores de activos en un trabajo de pedidos de trabajo</span><span class="sxs-lookup"><span data-stu-id="72126-173">View and update asset counters on a work order job</span></span>

1. <span data-ttu-id="72126-174">En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.</span><span class="sxs-lookup"><span data-stu-id="72126-174">On your mobile device, open the **Asset management** workspace.</span></span>

2. <span data-ttu-id="72126-175">Seleccione **Todos los pedidos de trabajo de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="72126-175">Select **All maintenance work orders**.</span></span>

3. <span data-ttu-id="72126-176">Seleccione la orden de trabajo > trabajo de orden de trabajo para el que desea ver los contadores de activos.</span><span class="sxs-lookup"><span data-stu-id="72126-176">Select the work order > work order job you want to view asset counters for.</span></span>
    - <span data-ttu-id="72126-177">Como alternativa, también puede seleccionar **Mi calendario de los trabajos de la orden de trabajo** o **Mi lista de trabajos de la orden de trabajo** en la página principal para navegar a la página **Detalles del trabajo de la orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="72126-177">Alternatively, you can also select **My work order jobs calendar** or **My work order jobs list** on the home page to navigate to the **work order job details** page.</span></span>

4. <span data-ttu-id="72126-178">Seleccione **Contadores de activos** en la página **Detalles del trabajo de la orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="72126-178">Select **Asset counters** on the **Work order job details** page.</span></span>

5. <span data-ttu-id="72126-179">Se verá una lista de contadores de activos relacionados con el trabajo de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="72126-179">You see a list of asset counters related to the work order job.</span></span> <span data-ttu-id="72126-180">Seleccione el icono de lápiz en una línea del contador de activos para actualizar el valor de un contador.</span><span class="sxs-lookup"><span data-stu-id="72126-180">Select the pencil icon on an asset counter line to update the counter value.</span></span>

6. <span data-ttu-id="72126-181">Introduzca un nuevo valor de contador y seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="72126-181">Enter a new counter value, and select **Done**.</span></span>

![Figura 6](media/am-mobile-06.png)


## <a name="register-consumption-on-a-work-order-job"></a><span data-ttu-id="72126-183">Registrar el consumo en un trabajo de orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="72126-183">Register consumption on a work order job</span></span>

1. <span data-ttu-id="72126-184">En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.</span><span class="sxs-lookup"><span data-stu-id="72126-184">On your mobile device, open the **Asset management** workspace.</span></span>

2. <span data-ttu-id="72126-185">Seleccione **Todos los pedidos de trabajo de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="72126-185">Select **All maintenance work orders**.</span></span>

3. <span data-ttu-id="72126-186">Seleccione la orden de trabajo > trabajo de orden de trabajo para el que desea agregar registros de consumo.</span><span class="sxs-lookup"><span data-stu-id="72126-186">Select the work order > work order job you want to add consumtion registrations for.</span></span>
    - <span data-ttu-id="72126-187">Como alternativa, también puede seleccionar **Mi calendario de los trabajos de la orden de trabajo** o **Mi lista de trabajos de la orden de trabajo** en la página principal para navegar a la página **Detalles del trabajo de la orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="72126-187">Alternatively, you can also select **My work order jobs calendar** or **My work order jobs list** on the home page to navigate to the **work order job details** page.</span></span>

4. <span data-ttu-id="72126-188">Seleccione **Diarios** en la página **Detalles del trabajo de la orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="72126-188">Select **Journals** on the **Work order job details** page.</span></span>

5. <span data-ttu-id="72126-189">Seleccione **Agregar horas** para crear registros de horas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="72126-189">Select **Add hours** to create work hour registrations.</span></span>
    1. <span data-ttu-id="72126-190">Seleccionar la **categoría** en la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="72126-190">Select the **Category** from the lookup.</span></span>
    2. <span data-ttu-id="72126-191">En el campo **Horas**, especifique el número de horas de trabajo gastadas en el trabajo de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="72126-191">In the **Hours** field, enter the number of work hours spent on the work order job.</span></span>
    3. <span data-ttu-id="72126-192">Seleccione la **propiedad del línea** adecuada.</span><span class="sxs-lookup"><span data-stu-id="72126-192">Select the appropriate **Line property**.</span></span>
    4. <span data-ttu-id="72126-193">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="72126-193">Select **Done**.</span></span>

6. <span data-ttu-id="72126-194">Seleccione **Agregar artículos** para crear registros de artículos.</span><span class="sxs-lookup"><span data-stu-id="72126-194">Select **Add items** to create item registrations.</span></span>
    1. <span data-ttu-id="72126-195">Seleccione el **Número de artículo** en la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="72126-195">Select the **Item number** from the lookup.</span></span>
    2. <span data-ttu-id="72126-196">Seleccione el **Sitio** en la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="72126-196">Select the **Site** from the lookup.</span></span>
    3. <span data-ttu-id="72126-197">Indique la **cantidad** de artículos consumidos.</span><span class="sxs-lookup"><span data-stu-id="72126-197">Enter the **Quantity** of items consumed.</span></span>
    4. <span data-ttu-id="72126-198">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="72126-198">Select **Done**.</span></span>

7. <span data-ttu-id="72126-199">Seleccione **Agregar gasto** para crear registros de gastos.</span><span class="sxs-lookup"><span data-stu-id="72126-199">Select **Add expense** to create expense registrations.</span></span>
    1. <span data-ttu-id="72126-200">Seleccionar la **categoría** en la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="72126-200">Select the **Category** from the lookup.</span></span>
    2. <span data-ttu-id="72126-201">Escriba la cantidad para el registro de gasto.</span><span class="sxs-lookup"><span data-stu-id="72126-201">Enter the quantity for the expense registration.</span></span>
    3. <span data-ttu-id="72126-202">Seleccione la **divisa de ventas** en la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="72126-202">Select the **Sales currency** from the lookup.</span></span>
    4. <span data-ttu-id="72126-203">Escriba el **Precio de coste** para el registro de gasto.</span><span class="sxs-lookup"><span data-stu-id="72126-203">Enter the **Cost price** for the expense registration.</span></span>
    5. <span data-ttu-id="72126-204">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="72126-204">Select **Done**.</span></span>

![Figura 7](media/am-mobile-07.png)


## <a name="update-lifecycle-state-on-a-work-order"></a><span data-ttu-id="72126-206">Actualizar el estados de ciclo de vida de una orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="72126-206">Update lifecycle state on a work order</span></span>

1. <span data-ttu-id="72126-207">En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.</span><span class="sxs-lookup"><span data-stu-id="72126-207">On your mobile device, open the **Asset management** workspace.</span></span>

2. <span data-ttu-id="72126-208">Seleccione **Todos los pedidos de trabajo de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="72126-208">Select **All maintenance work orders**.</span></span>

3. <span data-ttu-id="72126-209">Seleccione la orden de trabajo para la que desea actualizar el estado de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="72126-209">Select the work order you want to update lifecycle state for.</span></span>

4. <span data-ttu-id="72126-210">Seleccione el botón **Actualizar estado** en la parte inferior de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="72126-210">Select the **Update state** button at the bottom of the screen.</span></span>

5. <span data-ttu-id="72126-211">Seleccione un nuev estado del ciclo de vida de la lista.</span><span class="sxs-lookup"><span data-stu-id="72126-211">Select a new lifecycle state from the list.</span></span>

6. <span data-ttu-id="72126-212">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="72126-212">Select **Done**.</span></span>

![Figura 8](media/am-mobile-08.png)


## <a name="create-a-maintenance-request"></a><span data-ttu-id="72126-214">Crear una solicitud de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="72126-214">Create a maintenance request</span></span>

1. <span data-ttu-id="72126-215">En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.</span><span class="sxs-lookup"><span data-stu-id="72126-215">On your mobile device, open the **Asset management** workspace.</span></span>

2. <span data-ttu-id="72126-216">Seleccione **Todas las solicitudes de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="72126-216">Select **All maintenance requests**.</span></span>

3. <span data-ttu-id="72126-217">Seleccione **Acciones** en la parte inferior de la pantalla, y seleccione **Crear solicitud de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="72126-217">Select **Actions** at the bottom of the screen, and select **Create maintenance request**.</span></span>

4. <span data-ttu-id="72126-218">Si la secuencia numérica está habilitada para las solicitudes de mantenimiento en **Administración de activos**, se oculta el campo **Solicitud de mantenimiento** porque se completa automáticamente. Si el campo **Solicitud de mantenimiento** está visible, especifique un identificador de solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="72126-218">If number sequence is enabled for maintenance requests in **Asset management**, the **Maintenance request** field is hidden because it is automatically filled out. If the **Maintenance request** field is visible, enter a maintenance request ID.</span></span>

5. <span data-ttu-id="72126-219">Seleccione un **Tipo de solicitud de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="72126-219">Select a **Maintenance request type**.</span></span>

6. <span data-ttu-id="72126-220">Especifique una **Descripción** para la solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="72126-220">Enter a **Description** for the maintenance request.</span></span>

7. <span data-ttu-id="72126-221">Seleccionar el **Activo** para el que desea crear la solicitud.</span><span class="sxs-lookup"><span data-stu-id="72126-221">Select the **Asset** you want to create the request for.</span></span>

8. <span data-ttu-id="72126-222">Seleccione el **Nivel de servicio** para la solicitud de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="72126-222">Select the **Service level** for the maintenance request.</span></span>

9. <span data-ttu-id="72126-223">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="72126-223">Select **Done**.</span></span>

![Figura 9](media/am-mobile-09.png)


## <a name="add-attachment-to-a-maintenance-request"></a><span data-ttu-id="72126-225">Agregar datos adjuntos a una solicitud de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="72126-225">Add attachment to a maintenance request</span></span>

1. <span data-ttu-id="72126-226">En su dispositivo móvil, abra el espacio de trabajo **Gestión de activos**.</span><span class="sxs-lookup"><span data-stu-id="72126-226">On your mobile device, open the **Asset management** workspace.</span></span>

2. <span data-ttu-id="72126-227">Seleccione **Todas las solicitudes de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="72126-227">Select **All maintenance requests**.</span></span>

3. <span data-ttu-id="72126-228">Seleccione la solicitud de mantenimiento a la que desea agregar un archivo adjunto.</span><span class="sxs-lookup"><span data-stu-id="72126-228">Select the maintenance request you want to add an attachment to.</span></span>

4. <span data-ttu-id="72126-229">Seleccione **Datos adjuntos** en la parte inferior de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="72126-229">Select **Attachments** at the bottom of the screen.</span></span>

5. <span data-ttu-id="72126-230">Seleccione **Agregar datos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="72126-230">Select **Add attachments**.</span></span>

6. <span data-ttu-id="72126-231">Especifique el **Nombre** y las **Notas** para los datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="72126-231">Enter **Name** and **Notes** for the attachment.</span></span>

7. <span data-ttu-id="72126-232">Seleccione **Elegir imagen** para seleccionar una foto de la galería móvil, o **Tomar foto** para tomar una foto.</span><span class="sxs-lookup"><span data-stu-id="72126-232">Select **Choose image** to select a photo from the mobile gallery, or **Take photo** to take a photo.</span></span>

8. <span data-ttu-id="72126-233">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="72126-233">Select **Done**.</span></span>

![Figura 10](media/am-mobile-10.png)

