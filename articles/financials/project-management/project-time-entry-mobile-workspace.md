---
title: Espacio de trabajo móvil de entrada de tiempo de proyecto
description: Este tema proporciona información acerca del espacio de trabajo móvil de entrada de horas del proyecto. Este espacio de trabajo permite a los usuarios especificar y guardar la hora en un proyecto mediante el dispositivo móvil.
author: KimANelson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 272101
ms.assetid: 4505f021-b9bb-4b87-be24-6bf0bd88ee60
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: e671fe6e7c99bfb6d66f3b00560c3b0c404d2343
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "333010"
---
# <a name="project-time-entry-mobile-workspace"></a><span data-ttu-id="249db-104">Espacio de trabajo móvil de entrada de tiempo de proyecto</span><span class="sxs-lookup"><span data-stu-id="249db-104">Project time entry mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="249db-105">Este tema proporciona información acerca del espacio de trabajo móvil **Entrada de tiempo del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="249db-105">This topic provides information about the **Project time entry** mobile workspace.</span></span> <span data-ttu-id="249db-106">Este espacio de trabajo permite a los usuarios especificar y guardar la hora en un proyecto mediante el dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="249db-106">This workspace lets users enter and save time against a project by using their mobile device.</span></span>

<span data-ttu-id="249db-107">Este espacio de trabajo móvil se debe usar con la aplicación Microsoft Dynamics 365 for Unified Operations mobile.</span><span class="sxs-lookup"><span data-stu-id="249db-107">This mobile workspace is intended to be used with the Microsoft Dynamics 365 for Unified Operations mobile app.</span></span> 

## <a name="overview"></a><span data-ttu-id="249db-108">Información general</span><span class="sxs-lookup"><span data-stu-id="249db-108">Overview</span></span>
<span data-ttu-id="249db-109">Como parte de su trabajo diario, los recursos de proyecto están a menudo in situ o de viaje.</span><span class="sxs-lookup"><span data-stu-id="249db-109">As part of their daily work, project resources are often on-site or traveling.</span></span> <span data-ttu-id="249db-110">El espacio de trabajo móvil **Entrada de horas del proyecto** permite a los usuarios especificar su tiempo facturable o no facturable relativo a un proyecto, en el dispositivo móvil de su elección.</span><span class="sxs-lookup"><span data-stu-id="249db-110">The **Project time entry** mobile workspace lets users enter their billable or non-billable time against a project on the mobile device of their choice.</span></span> <span data-ttu-id="249db-111">Por lo tanto, los recursos de proyecto pueden registrar las entradas de horas en cualquier momento y cualquier lugar.</span><span class="sxs-lookup"><span data-stu-id="249db-111">Therefore, project resources can record time entries anytime and anywhere.</span></span> <span data-ttu-id="249db-112">También se pueden ver las entradas de horas que ya se han registrado.</span><span class="sxs-lookup"><span data-stu-id="249db-112">They can also view time entries that have already been recorded.</span></span> 

<span data-ttu-id="249db-113">Específicamente, en el espacio de trabajo móvil **Entrada de tiempo del proyecto**, los usuarios pueden realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="249db-113">Specifically, in the **Project time entry** mobile workspace, users can perform these tasks:</span></span>

-   <span data-ttu-id="249db-114">Para cualquier fecha seleccionada, especifique el número de horas empleadas en una tarea específica.</span><span class="sxs-lookup"><span data-stu-id="249db-114">For any selected date, enter the number of hours that you spent on a specific task.</span></span>
-   <span data-ttu-id="249db-115">Busque por nombre del proyecto o el cliente para encontrar el proyecto para el que debe especificar las horas.</span><span class="sxs-lookup"><span data-stu-id="249db-115">Search by project name or customer to find the project to enter time for.</span></span>
-   <span data-ttu-id="249db-116">Especifique la categoría y la actividad de las horas empleadas.</span><span class="sxs-lookup"><span data-stu-id="249db-116">Specify the category and activity for the time that you spent.</span></span>
-   <span data-ttu-id="249db-117">Registre la hora como facturable o no facturable para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="249db-117">Record the time as billable or non-billable for the project.</span></span>
-   <span data-ttu-id="249db-118">También puede especificar cualquier comentario externo o interno.</span><span class="sxs-lookup"><span data-stu-id="249db-118">Optionally enter any external or internal comments.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="249db-119">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="249db-119">Prerequisites</span></span>
<span data-ttu-id="249db-120">Los requisitos previos varían, en función de la versión de Microsoft Dynamics 365 que se ha implementado para su organización.</span><span class="sxs-lookup"><span data-stu-id="249db-120">The prerequisites differ, based on the version of Microsoft Dynamics 365 that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations"></a><span data-ttu-id="249db-121">Requisitos previos si usa Microsoft Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="249db-121">Prerequisites if you use Microsoft Dynamics 365 for Finance and Operations</span></span>
<span data-ttu-id="249db-122">Si Microsoft Dynamics 365 for Finance and Operations se ha implementado para su organización, el administrador del sistema debe publicar el espacio de trabajo móvil **Entrada de tiempo del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="249db-122">If Microsoft Dynamics 365 for Finance and Operations has been deployed for your organization, the system administrator must publish the **Project time entry** mobile workspace.</span></span> <span data-ttu-id="249db-123">Para obtener instrucciones, consulte [Publicar un espacio de trabajo móvil](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="249db-123">For instructions, see [Publish a mobile workspace](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a><span data-ttu-id="249db-124">Los requisitos previos si usa Microsoft Dynamics 365 for Operations versión 1611 con la actualización de plataforma 3 o posterior</span><span class="sxs-lookup"><span data-stu-id="249db-124">Prerequisites if you use Microsoft Dynamics 365 for Operations version 1611 with platform update 3 or later</span></span>
<span data-ttu-id="249db-125">Si se ha implementado Microsoft Dynamics 365 for Operations versión 1611 con actualización de plataforma 3 o posterior en su organización, el administrador del sistema debe cumplir los requisitos siguientes.</span><span class="sxs-lookup"><span data-stu-id="249db-125">If Microsoft Dynamics 365 for Operations version 1611 with platform update 3 or later has been deployed for your organization, the system administrator must complete the following prerequisites.</span></span> 

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="249db-126">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="249db-126">Prerequisite</span></span></th>
<th><span data-ttu-id="249db-127">Función</span><span class="sxs-lookup"><span data-stu-id="249db-127">Role</span></span></th>
<th><span data-ttu-id="249db-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="249db-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">

<td><span data-ttu-id="249db-129">Implementar 4018050 KB.</span><span class="sxs-lookup"><span data-stu-id="249db-129">Implement KB 4018050.</span></span></td>
<td><span data-ttu-id="249db-130">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="249db-130">System administrator</span></span></td>
<td><span data-ttu-id="249db-131">KB 4018050 es una sustitución de actualización o de metadatos X++ que contiene el espacio de trabajo móvil <strong>Entrada de horas del proyecto</strong>.</span><span class="sxs-lookup"><span data-stu-id="249db-131">KB 4018050 is an X++ update or metadata hotfix that contains the <strong>Project time entry</strong> mobile workspace.</span></span> <span data-ttu-id="249db-132">Para implementar KB 4018050, el administrador del sistema debe seguir estos pasos.</span><span class="sxs-lookup"><span data-stu-id="249db-132">To implement KB 4018050, your system administrator must follow these steps.</span></span>
<ol>
<li><span data-ttu-id="249db-133"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Descargar la revisión de metadatos de Microsoft Dynamics Lifecycle Services (LCS)</a>.</span><span class="sxs-lookup"><span data-stu-id="249db-133"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Download the metadata hotfix from Microsoft Dynamics Lifecycle Services (LCS)</a>.</span></span></li>
<li><span data-ttu-id="249db-134"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Instalar la revisión de metadatos</a>.</span><span class="sxs-lookup"><span data-stu-id="249db-134"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Install the metadata hotfix</a>.</span></span></li>
<li><span data-ttu-id="249db-135"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Crear un paquete desplegable</a> que contenga los modelos <strong>ApplicationSuite</strong> y <strong>ProjectMobile</strong> y luego cargar el paquete desplegable en LCS.</span><span class="sxs-lookup"><span data-stu-id="249db-135"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Create a deployable package</a> that contains the <strong>ApplicationSuite</strong> and <strong>ProjectMobile</strong> models, and then upload the deployable package to LCS.</span></span></li>
<li><span data-ttu-id="249db-136"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Aplicar el paquete implementable</a>.</span><span class="sxs-lookup"><span data-stu-id="249db-136"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Apply the deployable package</a>.</span></span></li>

</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="249db-137">Publique el espacio de trabajo móvil <strong>Entrada de tiempo del proyecto</strong>.</span><span class="sxs-lookup"><span data-stu-id="249db-137">Publish the <strong>Project time entry</strong> mobile workspace.</span></span></td>
<td><span data-ttu-id="249db-138">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="249db-138">System administrator</span></span></td>
<td><span data-ttu-id="249db-139">Consulte <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publicar un espacio de trabajo móvil</a>.</span><span class="sxs-lookup"><span data-stu-id="249db-139">See <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="249db-140">Descargar e instalar la aplicación móvil</span><span class="sxs-lookup"><span data-stu-id="249db-140">Download and install the mobile app</span></span>

<span data-ttu-id="249db-141">Descargue e instale la aplicación móvil Dynamics 365 for Unified Operations:</span><span class="sxs-lookup"><span data-stu-id="249db-141">Download and install the Dynamics 365 for Unified Operations mobile app:</span></span>

-   [<span data-ttu-id="249db-142">Para teléfonos Android</span><span class="sxs-lookup"><span data-stu-id="249db-142">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="249db-143">Para iPhones</span><span class="sxs-lookup"><span data-stu-id="249db-143">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="249db-144">Iniciar sesión en la aplicación móvil</span><span class="sxs-lookup"><span data-stu-id="249db-144">Sign in to the mobile app</span></span>
1.  <span data-ttu-id="249db-145">Inicie la aplicación en su dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="249db-145">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="249db-146">Escriba la URL de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="249db-146">Enter your Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="249db-147">La primera vez que se inicie sesión, se le solicitará su nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="249db-147">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="249db-148">Escriba sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="249db-148">Enter your credentials.</span></span>
4.  <span data-ttu-id="249db-149">Tras iniciar sesión, se mostrarán los espacios de trabajo disponibles para su empresa.</span><span class="sxs-lookup"><span data-stu-id="249db-149">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="249db-150">Tenga en cuenta que si el administrador del sistema publica un nuevo espacio de trabajo más tarde, tendrá que actualizar la lista de espacios de trabajo móviles.</span><span class="sxs-lookup"><span data-stu-id="249db-150">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

<span data-ttu-id="249db-151">[![Toque la pantalla para actualizar](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="249db-151">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="enter-time-by-using-the-project-time-entry-mobile-workspace"></a><span data-ttu-id="249db-152">Especifique las horas mediante el espacio de trabajo móvil de entrada de horas del proyecto</span><span class="sxs-lookup"><span data-stu-id="249db-152">Enter time by using the Project time entry mobile workspace</span></span>
1.  <span data-ttu-id="249db-153">En el dispositivo móvil, seleccione el espacio de trabajo **Entrada de horas del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="249db-153">On your mobile device, select the **Project time entry** workspace.</span></span>
2.  <span data-ttu-id="249db-154">Seleccione **Entrada de horas**</span><span class="sxs-lookup"><span data-stu-id="249db-154">Select **Time entry**.</span></span> <span data-ttu-id="249db-155">Se muestran las fechas de calendario de la semana actual.</span><span class="sxs-lookup"><span data-stu-id="249db-155">The calendar dates for the current week are shown.</span></span>
3.  <span data-ttu-id="249db-156">Para una fecha seleccionada, seleccione **Acciones** &gt; **Nueva entrada**.</span><span class="sxs-lookup"><span data-stu-id="249db-156">For a selected date, select **Actions** &gt; **New entry**.</span></span>
4.  <span data-ttu-id="249db-157">Escriba la cantidad de horas que deben registrarse.</span><span class="sxs-lookup"><span data-stu-id="249db-157">Enter the number of hours to record.</span></span>
5.  <span data-ttu-id="249db-158">Seleccione el proyecto de la entrada de horas.</span><span class="sxs-lookup"><span data-stu-id="249db-158">Select the project for the time entry.</span></span> <span data-ttu-id="249db-159">Una lista muestra los proyectos que están cargados en su aplicación para su uso sin conexión.</span><span class="sxs-lookup"><span data-stu-id="249db-159">A list shows the projects that are loaded into your app for offline use.</span></span> <span data-ttu-id="249db-160">Hay 50 artículos cargados de forma predeterminada, pero un desarrollador puede cambiar este número.</span><span class="sxs-lookup"><span data-stu-id="249db-160">By default, 50 items are loaded, but a developer can change this number.</span></span> <span data-ttu-id="249db-161">Para obtener más información, consulte [Plataforma móvil](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span><span class="sxs-lookup"><span data-stu-id="249db-161">For more information, see [Mobile platform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span></span>
6.  <span data-ttu-id="249db-162">Si el proyecto no está en la lista, seleccione **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="249db-162">If your project isn't in the list, select **Search**.</span></span> <span data-ttu-id="249db-163">Busque por su nombre, o cambie a la búsqueda al nombre del proyecto o el cliente.</span><span class="sxs-lookup"><span data-stu-id="249db-163">Search by name, or switch to search by project name or customer.</span></span>
7.  <span data-ttu-id="249db-164">Permite seleccionar una categoría.</span><span class="sxs-lookup"><span data-stu-id="249db-164">Select a category.</span></span> <span data-ttu-id="249db-165">Una lista muestra las categorías que están cargadas en su aplicación para su uso sin conexión.</span><span class="sxs-lookup"><span data-stu-id="249db-165">A list shows the categories that are loaded into your app for offline use.</span></span> <span data-ttu-id="249db-166">Hay 50 artículos cargados de forma predeterminada, pero un desarrollador puede cambiar este número.</span><span class="sxs-lookup"><span data-stu-id="249db-166">By default, 50 items are loaded, but a developer can change this number.</span></span> <span data-ttu-id="249db-167">Para obtener más información, consulte [Plataforma móvil](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span><span class="sxs-lookup"><span data-stu-id="249db-167">For more information, see [Mobile platform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span></span>
8.  <span data-ttu-id="249db-168">Si la categoría no está en la lista, seleccione **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="249db-168">If your category isn't in the list, select **Search**.</span></span> <span data-ttu-id="249db-169">Busque por categoría o cambie a buscar por nombre de categoría.</span><span class="sxs-lookup"><span data-stu-id="249db-169">Search by category, or switch to search by category name.</span></span>
9.  <span data-ttu-id="249db-170">Seleccione una actividad.</span><span class="sxs-lookup"><span data-stu-id="249db-170">Select an activity.</span></span> <span data-ttu-id="249db-171">Una lista muestra las actividades que están cargadas en su aplicación para su uso sin conexión.</span><span class="sxs-lookup"><span data-stu-id="249db-171">A list shows the activities that are loaded into your app for offline use.</span></span> <span data-ttu-id="249db-172">Hay 50 artículos cargados de forma predeterminada, pero un desarrollador puede cambiar este número.</span><span class="sxs-lookup"><span data-stu-id="249db-172">By default, 50 items are loaded, but a developer can change this number.</span></span> <span data-ttu-id="249db-173">Para obtener más información, consulte [Plataforma móvil](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span><span class="sxs-lookup"><span data-stu-id="249db-173">For more information, see [Mobile platform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span></span>
10. <span data-ttu-id="249db-174">Si la actividad no está en la lista, seleccione **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="249db-174">If your activity isn't in the list, select **Search**.</span></span> <span data-ttu-id="249db-175">Busque por número de actividad o cambie a buscar por propósito.</span><span class="sxs-lookup"><span data-stu-id="249db-175">Search by activity number, or switch to search by purpose.</span></span>

11. <span data-ttu-id="249db-176">Seleccione la propiedad del línea.</span><span class="sxs-lookup"><span data-stu-id="249db-176">Select the line property.</span></span>
12. <span data-ttu-id="249db-177">Opcional: puede especificar cualquier comentario externo o interno.</span><span class="sxs-lookup"><span data-stu-id="249db-177">Optional: Enter any external and internal comments.</span></span>
13. <span data-ttu-id="249db-178">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="249db-178">Select **Done**.</span></span>
