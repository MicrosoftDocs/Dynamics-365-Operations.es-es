---
title: Configurar el espacio de trabajo móvil de gestión de activos
description: Este tema describe cómo configurar Microsoft Dynamics 365 Supply Chain Management y la aplicación móvil Finance and Operations (Dynamics 365) para ejecutar un espacio de trabajo móvil de administración de activos que los trabajadores pueden usar para realizar tareas de administración de activos.
author: johanhoffmann
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-22
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: bc170df2fc58ae6b42fbc8834caad0bb7cd16f69
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837786"
---
# <a name="set-up-the-asset-management-mobile-workspace"></a><span data-ttu-id="8b6a0-103">Configurar el espacio de trabajo móvil de gestión de activos</span><span class="sxs-lookup"><span data-stu-id="8b6a0-103">Set up the Asset management mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8b6a0-104">Este tema describe cómo configurar Microsoft Dynamics 365 Supply Chain Management y la aplicación móvil Finance and Operations (Dynamics 365) para ejecutar un espacio de trabajo móvil de **administración de activos** que los trabajadores pueden usar para realizar tareas de administración de activos.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-104">This topic describes how to set up Microsoft Dynamics 365 Supply Chain Management and the Finance and Operations (Dynamics 365) mobile app to run an **Asset management** mobile workspace that workers can use to perform asset management tasks.</span></span>

## <a name="set-up-maintenance-worker-users-in-supply-chain-management"></a><span data-ttu-id="8b6a0-105">Configurar usuarios de trabajadores de mantenimiento en Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="8b6a0-105">Set up maintenance worker users in Supply Chain Management</span></span>

<span data-ttu-id="8b6a0-106">Para cada usuario que requiera acceso al espacio de trabajo móvil de **gestión de activos**, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-106">For each user that requires access to the **Asset management** mobile workspace, follow these steps.</span></span>

1. <span data-ttu-id="8b6a0-107">En Supply Chain Management, vaya a **Recursos humanos \> Trabajadores** y asegúrese de que exista un registro de trabajador para el usuario que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-107">In Supply Chain Management, go to **Human resources \> Workers**, and make sure that a worker record exists for the user that you want to set up.</span></span> <span data-ttu-id="8b6a0-108">Cree un nuevo registro de trabajador según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-108">Create a new worker record as required.</span></span>
1. <span data-ttu-id="8b6a0-109">Vaya a **Gestión de activos \> Configuración \> Trabajadores \> Trabajadores** y asegúrese de que el registro de trabajador que identificó (o creó) en el paso anterior esté asignado a un registro de trabajador de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-109">Go to **Asset management \> Setup \> Workers \> Workers**, and make sure that the worker record that you identified (or created) in the previous step is mapped to a maintenance worker record.</span></span> <span data-ttu-id="8b6a0-110">Cree un nuevo registro de trabajador de mantenimiento según sea necesario y establezca el campo **Trabajador** en el registro de trabajador del paso anterior.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-110">Create a new maintenance worker record as required, and set the **Worker** field to the worker record from the previous step.</span></span>
1. <span data-ttu-id="8b6a0-111">Vaya a **Gestión de activos \> Configuración \> Trabajadores \> Grupos de trabajador de mantenimiento** y asegúrese de que el registro de trabajador de mantenimiento que identificó (o creó) en el paso anterior pertenezca a un grupo de trabajador de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-111">Go to **Asset management \> Setup \> Workers \> Maintenance worker groups**, and make sure that the maintenance worker record that you identified (or created) in the previous step belongs to a maintenance worker group.</span></span>
1. <span data-ttu-id="8b6a0-112">Vaya a **Administración del sistema \> Usuarios > Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-112">Go to **System administration \> Users**.</span></span>
1. <span data-ttu-id="8b6a0-113">Seleccione el usuario correspondiente en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-113">Select the relevant user in the grid.</span></span>
1. <span data-ttu-id="8b6a0-114">En la ficha desplegable **Detalles de usuario**, establezca el campo **Persona** en la cuenta de trabajador que desea asociar con la cuenta de usuario actual.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-114">On the **User Details** FastTab, set the **Person** field to the worker account that you want to associate with the current user account.</span></span> <span data-ttu-id="8b6a0-115">Esta cuenta de trabajador debe ser el registro de trabajador que identificó (o creó) en el paso 1 y que se asignó a un registro de trabajador de mantenimiento en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-115">This worker account should be the worker record that you identified (or created) in step 1 and mapped to a maintenance worker record in step 2.</span></span>

> [!NOTE]
> <span data-ttu-id="8b6a0-116">Los permisos de usuario y los roles de seguridad se aplican a las funciones del espacio de trabajo móvil de **gestión de activos** tal como se aplican a las funciones de la interfaz de usuario de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-116">User permissions and security roles apply to the features of the **Asset management** mobile workspace just as they apply to the features of the Supply Chain Management user interface.</span></span> <span data-ttu-id="8b6a0-117">Por lo tanto, cada usuario que configure para acceder al espacio de trabajo móvil de **gestión de activos** debe tener los roles de seguridad necesarios para realizar operaciones similares directamente en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-117">Therefore, every user that you set up to access the **Asset management** mobile workspace must have the security roles that are required to perform similar operations directly in Supply Chain Management.</span></span>

## <a name="publish-the-asset-management-mobile-workspace"></a><span data-ttu-id="8b6a0-118">Publicación del espacio de trabajo móvil de gestión de activos</span><span class="sxs-lookup"><span data-stu-id="8b6a0-118">Publish the Asset management mobile workspace</span></span>

<span data-ttu-id="8b6a0-119">Para que las funciones de gestión de activos estén disponibles en la aplicación móvil de Finance and Operations (Dynamics 365), debe publicar el espacio de trabajo móvil de **Gestión de activos**.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-119">To make asset management features available in the Finance and Operations (Dynamics 365) mobile app, you must publish the **Asset management** mobile workspace.</span></span>

1. <span data-ttu-id="8b6a0-120">En Supply Chain Management, seleccione el botón **Configuraciones** (el símbolo del engranaje en la esquina superior derecha) y luego seleccione **Aplicación movil** en el menú.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-120">In Supply Chain Management, select the **Settings** button (the gear symbol in upper-right corner), and then select **Mobile app** on the menu.</span></span>
1. <span data-ttu-id="8b6a0-121">En el cuadro de diálogo **Administrar aplicación móvil**, busque el icono de **Gestión de activos**.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-121">In the **Manage mobile app** dialog box, find the **Asset Management** tile.</span></span> <span data-ttu-id="8b6a0-122">Si contiene el texto "En metadatos, no publicado", el espacio de trabajo aún no se ha publicado.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-122">If it contains the text "In metadata - not published," the workspace hasn't yet been published.</span></span> <span data-ttu-id="8b6a0-123">Si contiene el texto "En metadatos: publicado", el espacio de trabajo ya se ha publicado y puede omitir el resto de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-123">If it contains the text "In metadata - published," the workspace has already been published, and you can skip the rest of this procedure.</span></span>

    <span data-ttu-id="8b6a0-124">![Cuadro de diálogo Administrar aplicación móvil](media/mobile-workspaces.png "Cuadro de diálogo Administrar aplicación móvil")</span><span class="sxs-lookup"><span data-stu-id="8b6a0-124">![Manage mobile app dialog box](media/mobile-workspaces.png "Manage mobile app dialog box")</span></span>

1. <span data-ttu-id="8b6a0-125">Seleccione el icono **Gestión de activos** y luego seleccione **Publicar** en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-125">Select the **Asset Management** tile, and then select **Publish** on the toolbar.</span></span> <span data-ttu-id="8b6a0-126">Después de unos segundos, debería recibir una notificación que indica que el espacio de trabajo se ha publicado correctamente.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-126">After a few seconds, you should receive a notification that states that the workspace has been successfully published.</span></span> <span data-ttu-id="8b6a0-127">Además, el texto del icono debería cambiar a "En metadatos: publicado".</span><span class="sxs-lookup"><span data-stu-id="8b6a0-127">Additionally, the text on the tile should change to "In metadata - published."</span></span>

## <a name="install-and-set-up-the-finance-and-operations-dynamics-365-mobile-app"></a><span data-ttu-id="8b6a0-128">Instale y configure la aplicación móvil Finance and Operations (Dynamics 365)</span><span class="sxs-lookup"><span data-stu-id="8b6a0-128">Install and set up the Finance and Operations (Dynamics 365) mobile app</span></span>

1. <span data-ttu-id="8b6a0-129">Vaya a una de las siguientes tiendas de aplicaciones para instalar la aplicación **Microsoft Finance and Operations (Dynamics 365)** en su dispositivo móvil:</span><span class="sxs-lookup"><span data-stu-id="8b6a0-129">Go to one of the following app stores to install the **Microsoft Finance and Operations (Dynamics 365)** app on your mobile device:</span></span>

    - [<span data-ttu-id="8b6a0-130">Para dispositivos Google Android</span><span class="sxs-lookup"><span data-stu-id="8b6a0-130">For Google Android devices</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
    - [<span data-ttu-id="8b6a0-131">Para dispositivos Apple iOS</span><span class="sxs-lookup"><span data-stu-id="8b6a0-131">For Apple iOS devices</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

1. <span data-ttu-id="8b6a0-132">Abra la aplicación Finance and Operations (Dynamics 365).</span><span class="sxs-lookup"><span data-stu-id="8b6a0-132">Open the Finance and Operations (Dynamics 365) app.</span></span> <span data-ttu-id="8b6a0-133">Debería aparecer la página de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-133">The sign-in page should appear.</span></span> <span data-ttu-id="8b6a0-134">En el campo **Iniciar sesión**, ingrese su URL de Supply Chain Management o seleccione una URL reciente en la lista **Entornos recientes** y luego toque **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-134">In the **Sign in** field, enter your Supply Chain Management URL, or select a recent URL in the **Recent environments** list, and then tap **Connect**.</span></span>

    <span data-ttu-id="8b6a0-135">![Página de inicio de sesión](media/mobile-app-sign-in.png "Página de inicio de sesión")</span><span class="sxs-lookup"><span data-stu-id="8b6a0-135">![Sign-in page](media/mobile-app-sign-in.png "Sign-in page")</span></span>

1. <span data-ttu-id="8b6a0-136">Si se le solicita que confirme la conexión, seleccione la casilla de verificación **Entendido** y luego toque **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-136">If you're prompted to confirm the connection, select the **I understand** check box, and then tap **Connect**.</span></span>
1. <span data-ttu-id="8b6a0-137">En la página **Elegir una cuenta**, use su cuenta de Microsoft para iniciar sesión en la aplicación móvil.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-137">On the **Pick an account** page, use your Microsoft account to sign in to the mobile application.</span></span>

    <span data-ttu-id="8b6a0-138">Aparecerá la página **Espacios de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-138">The **Workspaces** page appears.</span></span> <span data-ttu-id="8b6a0-139">Enumera todos los espacios de trabajo móviles que ha publicado su instancia de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-139">It lists every mobile workspace that has been published by your Supply Chain Management instance.</span></span>

    <span data-ttu-id="8b6a0-140">![Lista de espacios de trabajo](media/mobile-app-workspaces.png "Lista de espacios de trabajo")</span><span class="sxs-lookup"><span data-stu-id="8b6a0-140">![List of workspaces](media/mobile-app-workspaces.png "List of workspaces")</span></span>

1. <span data-ttu-id="8b6a0-141">Si debe cambiar la entidad legal (empresa), toque el botón Menú (a veces denominado hamburguesa o botón de hamburguesa) en la esquina superior izquierda, y luego toque **Cambiar empresa**.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-141">If you must change the legal entity (company), tap the Menu button (sometimes referred to as the hamburger or the hamburger button) in the upper-left corner, and then tap **Change company**.</span></span>

    <span data-ttu-id="8b6a0-142">![Cambio de entidad jurídica](media/mobile-app-change-comp.png "Cambio de entidad jurídica")</span><span class="sxs-lookup"><span data-stu-id="8b6a0-142">![Changing the legal entity](media/mobile-app-change-comp.png "Changing the legal entity")</span></span>

1. <span data-ttu-id="8b6a0-143">En la página **Espacios de trabajo**, seleccione el espacio de trabajo con el que desea trabajar para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="8b6a0-143">On the **Workspaces** page, select the workspace that you want to work with to open it.</span></span>

    <span data-ttu-id="8b6a0-144">![Espacio de trabajo móvil de gestión de activos](media/mobile-app-asset-workspace.png "Espacio de trabajo móvil de gestión de activos")</span><span class="sxs-lookup"><span data-stu-id="8b6a0-144">![Asset management mobile workspace](media/mobile-app-asset-workspace.png "Asset management mobile workspace")</span></span>

## <a name="work-with-the-asset-management-mobile-workspace"></a><span data-ttu-id="8b6a0-145">Trabajo con el espacio de trabajo móvil de administración de activos</span><span class="sxs-lookup"><span data-stu-id="8b6a0-145">Work with the Asset management mobile workspace</span></span>

<span data-ttu-id="8b6a0-146">Para obtener más información sobre cómo trabajar con el espacio de trabajo **Administración de activos**, consulte [Uso del espacio de trabajo móvil de administración de activos](asset-management-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="8b6a0-146">For more information about how to work with the **Asset management** mobile workspace, see [Use the Asset management mobile workspace](asset-management-mobile-workspace.md).</span></span>

<span data-ttu-id="8b6a0-147">Para obtener más información sobre la aplicación móvil Finance and Operations (Dynamics 365), consulte la [Página de inicio de la aplicación móvil](../../fin-ops-core/dev-itpro/mobile-apps/Mobile-app-home-page.md).</span><span class="sxs-lookup"><span data-stu-id="8b6a0-147">For more information about the Finance and Operations (Dynamics 365) mobile app, see the [Mobile app home page](../../fin-ops-core/dev-itpro/mobile-apps/Mobile-app-home-page.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]