--- 
title: "Cargar configuraciones de informes electrónicos en Lifecycle Services"
description: "En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede crear una configuración nueva de informes electrónicos y cargarla en Microsoft Lifecycle Services (LCS)."
author: NickSelin
manager: AnnBe
ms.date: 05/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 6aa6bf7e08285d18210741ba6618878955009280
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---
# <a name="upload-electronic-reporting-configurations-into-lifecycle-services"></a><span data-ttu-id="5bc48-103">Cargar configuraciones de informes electrónicos en Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="5bc48-103">Upload Electronic reporting configurations into Lifecycle Services</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5bc48-104">En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede crear una configuración nueva de informes electrónicos y cargarla en Microsoft Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="5bc48-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration and upload it into Microsoft Lifecycle Services (LCS).</span></span>

<span data-ttu-id="5bc48-105">En este ejemplo, creará una configuración y la subira a LCS para la empresa de demostración, Litware, Inc. Estos pasos se pueden realizar en cualquier empresa a medida que las configuraciones de ER se comparten entre las empresas.</span><span class="sxs-lookup"><span data-stu-id="5bc48-105">In this example, you will create a configuration and upload it to LCS for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="5bc48-106">Para completar estos pasos, primero debe completar los pasos del procedimiento Creación y activación de un proveedor de configuraciones.</span><span class="sxs-lookup"><span data-stu-id="5bc48-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="5bc48-107">También se requiere el acceso a LCS para finalizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="5bc48-107">Access to LCS is also required for completion of these steps.</span></span>

1. <span data-ttu-id="5bc48-108">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="5bc48-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="5bc48-109">Seleccione "Litware, Inc."</span><span class="sxs-lookup"><span data-stu-id="5bc48-109">Select ‘Litware, Inc.’</span></span> <span data-ttu-id="5bc48-110">y establézcala como activa.</span><span class="sxs-lookup"><span data-stu-id="5bc48-110">and set it as active.</span></span>
3. <span data-ttu-id="5bc48-111">Haga clic en Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="5bc48-111">Click Configurations.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="5bc48-112">Creación de un nuevo modelo de configuración de datos</span><span class="sxs-lookup"><span data-stu-id="5bc48-112">Create a new data model configuration</span></span>
1. <span data-ttu-id="5bc48-113">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="5bc48-113">Click Create configuration to open the drop dialog.</span></span>
    * <span data-ttu-id="5bc48-114">Creará una configuración que contenga un modelo de datos de muestra para los documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="5bc48-114">You will create a configuration that contains a sample data model for electronic documents.</span></span> <span data-ttu-id="5bc48-115">Esta configuración del modelo de datos se cargará en LCS más adelante.</span><span class="sxs-lookup"><span data-stu-id="5bc48-115">This data model configuration will be uploaded into LCS later.</span></span>  
2. <span data-ttu-id="5bc48-116">En el campo Nombre, escriba "Configuración del modelo de ejemplo".</span><span class="sxs-lookup"><span data-stu-id="5bc48-116">In the Name field, type 'Sample model configuration'.</span></span>
    * <span data-ttu-id="5bc48-117">Configuración del modelo de ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bc48-117">Sample model configuration</span></span>  
3. <span data-ttu-id="5bc48-118">En el campo Descripción, escriba "Configuración del modelo de ejemplo".</span><span class="sxs-lookup"><span data-stu-id="5bc48-118">In the Description field, type 'Sample model configuration'.</span></span>
    * <span data-ttu-id="5bc48-119">Configuración del modelo de ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bc48-119">Sample model configuration</span></span>  
4. <span data-ttu-id="5bc48-120">Haga clic en Crear configuración.</span><span class="sxs-lookup"><span data-stu-id="5bc48-120">Click Create configuration.</span></span>
5. <span data-ttu-id="5bc48-121">Haga clic en Diseñador de modelo.</span><span class="sxs-lookup"><span data-stu-id="5bc48-121">Click Model designer.</span></span>
6. <span data-ttu-id="5bc48-122">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="5bc48-122">Click New.</span></span>
7. <span data-ttu-id="5bc48-123">En el campo Nombre, escriba "Punto de entrada".</span><span class="sxs-lookup"><span data-stu-id="5bc48-123">In the Name field, type 'Entry point'.</span></span>
    * <span data-ttu-id="5bc48-124">Punto de entrada</span><span class="sxs-lookup"><span data-stu-id="5bc48-124">Entry point</span></span>  
8. <span data-ttu-id="5bc48-125">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="5bc48-125">Click Add.</span></span>
9. <span data-ttu-id="5bc48-126">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="5bc48-126">Click Save.</span></span>
10. <span data-ttu-id="5bc48-127">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5bc48-127">Close the page.</span></span>
11. <span data-ttu-id="5bc48-128">Haga clic en Cambiar estado.</span><span class="sxs-lookup"><span data-stu-id="5bc48-128">Click Change status.</span></span>
12. <span data-ttu-id="5bc48-129">Haga clic en Completar.</span><span class="sxs-lookup"><span data-stu-id="5bc48-129">Click Complete.</span></span>
13. <span data-ttu-id="5bc48-130">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="5bc48-130">Click OK.</span></span>

## <a name="register-a-new--repository"></a><span data-ttu-id="5bc48-131">Registrar uno nuevo repositorio</span><span class="sxs-lookup"><span data-stu-id="5bc48-131">Register a new  repository</span></span>
1. <span data-ttu-id="5bc48-132">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5bc48-132">Close the page.</span></span>
2. <span data-ttu-id="5bc48-133">Haga clic en Repositorios.</span><span class="sxs-lookup"><span data-stu-id="5bc48-133">Click Repositories.</span></span>
    * <span data-ttu-id="5bc48-134">Esto le permite abrir la lista de repositorios para el proveedor de configuración Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="5bc48-134">This enables you to open the list of repositories for the Litware, Inc. configuration provider.</span></span>  
3. <span data-ttu-id="5bc48-135">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="5bc48-135">Click Add to open the drop dialog.</span></span>
    * <span data-ttu-id="5bc48-136">Esto le permite agregar un nuevo repositorio.</span><span class="sxs-lookup"><span data-stu-id="5bc48-136">This allows you to add a new repository.</span></span>  
4. <span data-ttu-id="5bc48-137">En el campo Repositorio de configuración, seleccione LCS.</span><span class="sxs-lookup"><span data-stu-id="5bc48-137">In the Configuration repository type field, select LCS.</span></span>
5. <span data-ttu-id="5bc48-138">Haga clic en Crear repositorio.</span><span class="sxs-lookup"><span data-stu-id="5bc48-138">Click Create repository.</span></span>
6. <span data-ttu-id="5bc48-139">En el campo Proyecto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="5bc48-139">In the Project field, enter or select a value.</span></span>
    * <span data-ttu-id="5bc48-140">Seleccione el proyecto de LCS que desee.</span><span class="sxs-lookup"><span data-stu-id="5bc48-140">Select the desired LCS project.</span></span> <span data-ttu-id="5bc48-141">Debe tener acceso al proyecto.</span><span class="sxs-lookup"><span data-stu-id="5bc48-141">You must have access to the project.</span></span>  
7. <span data-ttu-id="5bc48-142">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="5bc48-142">Click OK.</span></span>
    * <span data-ttu-id="5bc48-143">Complete una nueva entrada de repositorio.</span><span class="sxs-lookup"><span data-stu-id="5bc48-143">Complete a new repository entry.</span></span>  
8. <span data-ttu-id="5bc48-144">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="5bc48-144">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="5bc48-145">Seleccione el registro de repositorio LCS.</span><span class="sxs-lookup"><span data-stu-id="5bc48-145">Select the LCS repository record.</span></span>  
    * <span data-ttu-id="5bc48-146">Tenga en cuenta que un repositorio registrado está marcado por el proveedor actual, lo que significa que solo las configuraciones propiedad del proveedor se pueden colocar en este repositorio y, por tanto, cargar en el proyecto de LCS seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5bc48-146">Note that a registered repository is marked by the current provider meaning that the only configurations owned by that provider can be placed to this repository and, consequently, uploaded into the selected LCS project.</span></span>  
9. <span data-ttu-id="5bc48-147">Haga clic en Abrir.</span><span class="sxs-lookup"><span data-stu-id="5bc48-147">Click Open.</span></span>
    * <span data-ttu-id="5bc48-148">Abra el repositorio para ver la lista de configuraciones de ER.</span><span class="sxs-lookup"><span data-stu-id="5bc48-148">Open the repository to view the list of ER configurations.</span></span> <span data-ttu-id="5bc48-149">Estará vacío si este proyecto no se ha usado todavía para la distribución de las configuraciones de ER.</span><span class="sxs-lookup"><span data-stu-id="5bc48-149">It will be empty if this project has not yet been used for ER configurations sharing.</span></span>  
10. <span data-ttu-id="5bc48-150">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5bc48-150">Close the page.</span></span>
11. <span data-ttu-id="5bc48-151">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5bc48-151">Close the page.</span></span>

## <a name="upload-configuration-into-lcs"></a><span data-ttu-id="5bc48-152">Cargar configuración en LCS</span><span class="sxs-lookup"><span data-stu-id="5bc48-152">Upload configuration into LCS</span></span>
1. <span data-ttu-id="5bc48-153">Haga clic en Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="5bc48-153">Click Configurations.</span></span>
2. <span data-ttu-id="5bc48-154">En el árbol, seleccione "Configuración del modelo de ejemplo".</span><span class="sxs-lookup"><span data-stu-id="5bc48-154">In the tree, select 'Sample model configuration'.</span></span>
    * <span data-ttu-id="5bc48-155">Seleccione una configuración creada que ya se ha completado.</span><span class="sxs-lookup"><span data-stu-id="5bc48-155">Select a created configuration that has been already completed.</span></span>  
3. <span data-ttu-id="5bc48-156">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="5bc48-156">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="5bc48-157">Seleccione la versión de la configuración seleccionada con el estado de “Completado”.</span><span class="sxs-lookup"><span data-stu-id="5bc48-157">Select the version of the selected configuration with the status of ‘Completed’.</span></span>  
4. <span data-ttu-id="5bc48-158">Haga clic en Cambiar estado.</span><span class="sxs-lookup"><span data-stu-id="5bc48-158">Click Change status.</span></span>
5. <span data-ttu-id="5bc48-159">Haga clic en Compartir.</span><span class="sxs-lookup"><span data-stu-id="5bc48-159">Click Share.</span></span>
    * <span data-ttu-id="5bc48-160">El estado de la configuración cambiará de "Completado" a "Compartido" cuando se publique en LCS.</span><span class="sxs-lookup"><span data-stu-id="5bc48-160">The configuration status will change from ‘Completed’ to ‘Shared’ when it is published in LCS.</span></span>  
6. <span data-ttu-id="5bc48-161">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="5bc48-161">Click OK.</span></span>
7. <span data-ttu-id="5bc48-162">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="5bc48-162">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="5bc48-163">Seleccione la versión de configuración con el estado de "Compartido".</span><span class="sxs-lookup"><span data-stu-id="5bc48-163">Select the configuration version with the status of 'Shared'.</span></span>  
    * <span data-ttu-id="5bc48-164">Tenga en cuenta que el estado de la versión seleccionada ha cambiado de "Completado" a "Compartido".</span><span class="sxs-lookup"><span data-stu-id="5bc48-164">Note that the status of the selected version has changed from ‘Completed’ to ‘Shared’.</span></span>  
8. <span data-ttu-id="5bc48-165">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5bc48-165">Close the page.</span></span>
9. <span data-ttu-id="5bc48-166">Haga clic en Repositorios.</span><span class="sxs-lookup"><span data-stu-id="5bc48-166">Click Repositories.</span></span>
    * <span data-ttu-id="5bc48-167">Esto le permite abrir la lista de repositorios para el proveedor de configuración Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="5bc48-167">This enables you to open the list of repositories for the Litware, Inc. configuration provider.</span></span>  
10. <span data-ttu-id="5bc48-168">Haga clic en Abrir.</span><span class="sxs-lookup"><span data-stu-id="5bc48-168">Click Open.</span></span>
    * <span data-ttu-id="5bc48-169">Seleccione el repositorio de LCS y ábralo.</span><span class="sxs-lookup"><span data-stu-id="5bc48-169">Select the LCS repository and open it.</span></span>  
    * <span data-ttu-id="5bc48-170">Tenga en cuenta que la configuración seleccionada se muestra como activo del proyecto de LCS seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5bc48-170">Note that the selected configuration is shown as an asset of the selected LCS project.</span></span>  
    * <span data-ttu-id="5bc48-171">Abra LCS con https://lcs.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="5bc48-171">Open LCS using https://lcs.dynamics.com.</span></span> <span data-ttu-id="5bc48-172">Abra un proyecto que se usó anteriormente para el registro de repositorio, abra "Biblioteca de activos" de este proyecto y expanda el contenido del tipo de activo "Configuración de GER"; la configuración de ER cargada estará disponible.</span><span class="sxs-lookup"><span data-stu-id="5bc48-172">Open a project that was used earlier for repository registration, open the ‘Asset library’ of this project, and expand the content of the ‘GER configuration’ asset type – the uploaded ER configuration will be available.</span></span> <span data-ttu-id="5bc48-173">Tenga en cuenta que la configuración de LCS cargada se puede importar a otra instancia de Microsoft Dynamics 365 for Finance and Operations si los proveedores tienen acceso a este proyecto de LCS.</span><span class="sxs-lookup"><span data-stu-id="5bc48-173">Note that the uploaded LCS configuration can be imported to another Microsoft Dynamics 365 for Finance and Operations instance if providers have access to this LCS project.</span></span>  


