---
title: Cargar una configuración en Lifecycle Services
description: En este tema se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede crear una nueva versión de una configuración de informe electrónico y cargarla en desde Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 09/14/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c43bad3ee2530a454de718a0a7da4d1e468a4af4
ms.sourcegitcommit: 9857d5cbdc0ab2fc9db049ac5ad118fc2b29bedc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "3810700"
---
# <a name="upload-a-configuration-into-lifecycle-services"></a><span data-ttu-id="b62e7-103">Cargar una configuración en Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="b62e7-103">Upload a configuration into Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b62e7-104">En este tema se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede cargar una nueva versión de una [configuración de informe electrónico](../general-electronic-reporting.md#Configuration) y cargarla en la [biblioteca de activos de proyectos](../../lifecycle-services/asset-library.md) en Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="b62e7-104">This topic explains how a user in the System administrator or Electronic reporting developer role can create a new [Electronic reporting (ER) configuration](../general-electronic-reporting.md#Configuration) and upload it into the [project-level Asset library](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="b62e7-105">En este ejemplo, creará una configuración y la cargará a LCS para la empresa de demostración que se llama Litware, Inc. Estos pasos se pueden completarse en cualquier empresa porque las configuraciones de ER se comparten entre las empresas.</span><span class="sxs-lookup"><span data-stu-id="b62e7-105">In this example, you will create a configuration and upload it into LCS for a sample company that is named Litware, Inc. These steps can be completed in any company, because ER configurations are shared among companies.</span></span> <span data-ttu-id="b62e7-106">Para completar estos pasos, primero debe completar los pasos en [Crear proveedores de configuración y marcarlos como activos](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="b62e7-106">To complete these steps, you must first complete the steps in [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="b62e7-107">También se requiere acceso a LCS.</span><span class="sxs-lookup"><span data-stu-id="b62e7-107">Access to LCS is also required.</span></span>

1. <span data-ttu-id="b62e7-108">Inicie sesión a la aplicación mediante uno de los roles siguientes:</span><span class="sxs-lookup"><span data-stu-id="b62e7-108">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="b62e7-109">Desarrollador de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="b62e7-109">Electronic reporting developer</span></span>
    - <span data-ttu-id="b62e7-110">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="b62e7-110">System administrator</span></span>

2. <span data-ttu-id="b62e7-111">Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-111">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="b62e7-112">Seleccione **Litware, Inc.** y márquela como **Activa**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-112">Select **Litware, Inc.**, and mark it as **Active**.</span></span>
4. <span data-ttu-id="b62e7-113">Seleccione **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-113">Select **Configurations**.</span></span>

<a name="accessconditions"></a>
> [!NOTE]
> <span data-ttu-id="b62e7-114">Asegúrese de que el usuario actual de Dynamics 365 Finance es miembro del proyecto LCS que contiene la [biblioteca de activos](../../lifecycle-services/asset-library.md#asset-library-support) que se usa para importar configuraciones de ER.</span><span class="sxs-lookup"><span data-stu-id="b62e7-114">Make sure that the current Dynamics 365 Finance user is a member of the LCS project that contains the [Asset library](../../lifecycle-services/asset-library.md#asset-library-support) that is used to import ER configurations.</span></span>
>
> <span data-ttu-id="b62e7-115">No puede acceder a un proyecto LCS desde un repositorio de ER que representa un dominio diferente al dominio que se usa en Finance.</span><span class="sxs-lookup"><span data-stu-id="b62e7-115">You can't access an LCS project from an ER repository that represents a different domain than the domain that is used in Finance.</span></span> <span data-ttu-id="b62e7-116">Si lo intenta, se mostrará una lista vacía de proyectos LCS y no podrá importar configuraciones de ER desde la biblioteca de activos a nivel de proyecto en LCS.</span><span class="sxs-lookup"><span data-stu-id="b62e7-116">If you try, an empty list of LCS projects will be shown, and you won't be able to import ER configurations from the project-level Asset library in LCS.</span></span> <span data-ttu-id="b62e7-117">Para acceder a las bibliotecas de activos a nivel de proyecto desde un repositorio de ER que se utiliza para importar configuraciones de ER, inicie sesión en Finance utilizando las credenciales de un usuario que pertenezca al inquilino (dominio) para el que se ha aprovisionado la instancia de Finance actual.</span><span class="sxs-lookup"><span data-stu-id="b62e7-117">To access project-level Asset libraries from an ER repository that is used to import ER configurations, sign in to Finance by using the credentials of a user who belongs to the tenant (domain) that the current Finance instance has been provisioned for.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="b62e7-118">Creación de un nuevo modelo de configuración de datos</span><span class="sxs-lookup"><span data-stu-id="b62e7-118">Create a new data model configuration</span></span>

1. <span data-ttu-id="b62e7-119">Vaya a **Administración de la organización \> Informes electrónicos \> Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-119">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="b62e7-120">En la página **Configuraciones**, seleccione **Crear configuración** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="b62e7-120">On the **Configurations** page, select **Create configuration** to open the drop-down dialog box.</span></span>

    <span data-ttu-id="b62e7-121">En este ejemplo, creará una configuración que contenga un modelo de datos de muestra para los documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="b62e7-121">In this example, you will create a configuration that contains a sample data model for electronic documents.</span></span> <span data-ttu-id="b62e7-122">Esta configuración del modelo de datos se cargará en LCS más adelante.</span><span class="sxs-lookup"><span data-stu-id="b62e7-122">This data model configuration will be uploaded into LCS later.</span></span>

3. <span data-ttu-id="b62e7-123">En el campo **Nombre**, escriba **Configuración del modelo de ejemplo**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-123">In the **Name** field, enter **Sample model configuration**.</span></span>
4. <span data-ttu-id="b62e7-124">En el campo **Descripción**, escriba **Configuración del modelo de ejemplo**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-124">In the **Description** field, enter **Sample model configuration**.</span></span>
5. <span data-ttu-id="b62e7-125">Seleccionar **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-125">Select **Create configuration**.</span></span>
6. <span data-ttu-id="b62e7-126">Seleccione **Diseñador de modelos**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-126">Select **Model designer**.</span></span>
7. <span data-ttu-id="b62e7-127">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-127">Select **New**.</span></span>
8. <span data-ttu-id="b62e7-128">En el campo **Nombre**, escriba **Punto de entrada**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-128">In the **Name** field, enter **Entry point**.</span></span>
9. <span data-ttu-id="b62e7-129">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-129">Select **Add**.</span></span>
10. <span data-ttu-id="b62e7-130">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-130">Select **Save**.</span></span>
11. <span data-ttu-id="b62e7-131">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b62e7-131">Close the page.</span></span>
12. <span data-ttu-id="b62e7-132">Seleccione **Cambiar estado**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-132">Select **Change status**.</span></span>
13. <span data-ttu-id="b62e7-133">Seleccione **Completar**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-133">Select **Complete**.</span></span>
14. <span data-ttu-id="b62e7-134">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-134">Select **OK**.</span></span>
15. <span data-ttu-id="b62e7-135">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b62e7-135">Close the page.</span></span>

## <a name="register-a-new-repository"></a><span data-ttu-id="b62e7-136">Registrar uno nuevo repositorio</span><span class="sxs-lookup"><span data-stu-id="b62e7-136">Register a new repository</span></span>

1. <span data-ttu-id="b62e7-137">Vaya a **Administración de la organización \> Espacios de trabajo \> Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-137">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>

2. <span data-ttu-id="b62e7-138">En la sección **Proveedores de configuración**, seleccione el icono de **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-138">In the **Configuration providers** section, select the **Litware, Inc.** tile.</span></span>

3. <span data-ttu-id="b62e7-139">En el icono **Litware, Inc.**, seleccione **Repositorios**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-139">On the **Litware, Inc.** tile, select **Repositories**.</span></span>

    <span data-ttu-id="b62e7-140">Ahora puede abrir la lista de repositorios para el proveedor de configuración Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="b62e7-140">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

4. <span data-ttu-id="b62e7-141">Seleccione **Agregar** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="b62e7-141">Select **Add** to open the drop-down dialog box.</span></span>

    <span data-ttu-id="b62e7-142">Ahora puede agregar un nuevo repositorio.</span><span class="sxs-lookup"><span data-stu-id="b62e7-142">You can now add a new repository.</span></span>

5. <span data-ttu-id="b62e7-143">En el campo para especificar el **Repositorio de configuración**, escriba **LCS**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-143">In the **Configuration repository enter** field, select **LCS**.</span></span>
6. <span data-ttu-id="b62e7-144">Seleccione **Crear repositorio**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-144">Select **Create repository**.</span></span>
7. <span data-ttu-id="b62e7-145">En el campo **Proyecto**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="b62e7-145">In the **Project** field, enter or select a value.</span></span>

    <span data-ttu-id="b62e7-146">Para este ejemplo, seleccione el proyecto LCS deseado.</span><span class="sxs-lookup"><span data-stu-id="b62e7-146">For this example, select the desired LCS project.</span></span> <span data-ttu-id="b62e7-147">Debe tener [acceso](#accessconditions) al proyecto.</span><span class="sxs-lookup"><span data-stu-id="b62e7-147">You must have [access](#accessconditions) to the project.</span></span>

8. <span data-ttu-id="b62e7-148">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-148">Select **OK**.</span></span>

    <span data-ttu-id="b62e7-149">Complete una nueva entrada de repositorio.</span><span class="sxs-lookup"><span data-stu-id="b62e7-149">Complete a new repository entry.</span></span>

9. <span data-ttu-id="b62e7-150">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b62e7-150">In the list, mark the selected row.</span></span>

    <span data-ttu-id="b62e7-151">Para este ejemplo, seleccione el registro del repositorio **LCS**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-151">For this example, select the **LCS** repository record.</span></span>

    <span data-ttu-id="b62e7-152">Tenga en cuenta que un repositorio registrado está marcado por el proveedor actual.</span><span class="sxs-lookup"><span data-stu-id="b62e7-152">Note that a registered repository is marked by the current provider.</span></span> <span data-ttu-id="b62e7-153">En otras palabras, solo las configuraciones que son propiedad de ese proveedor pueden colocarse en este repositorio y, por lo tanto, cargarse en el proyecto LCS seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b62e7-153">In other words, only configurations that are owned by that provider can be put in this repository and therefore uploaded into the selected LCS project.</span></span>

10. <span data-ttu-id="b62e7-154">Seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-154">Select **Open**.</span></span>

    <span data-ttu-id="b62e7-155">Abre el repositorio para ver la lista de configuraciones de ER.</span><span class="sxs-lookup"><span data-stu-id="b62e7-155">You open the repository to view the list of ER configurations.</span></span> <span data-ttu-id="b62e7-156">Si seleccione un proyecto que no ha usado para compartir las configuraciones de ER, la lista estará vacía.</span><span class="sxs-lookup"><span data-stu-id="b62e7-156">If the selected project hasn't yet been used for ER configurations sharing, the list will be empty.</span></span>

11. <span data-ttu-id="b62e7-157">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b62e7-157">Close the page.</span></span>
12. <span data-ttu-id="b62e7-158">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b62e7-158">Close the page.</span></span>

## <a name="upload-a-configuration-into-lcs"></a><span data-ttu-id="b62e7-159">Cargar una configuración en LCS</span><span class="sxs-lookup"><span data-stu-id="b62e7-159">Upload a configuration into LCS</span></span>

1. <span data-ttu-id="b62e7-160">Vaya a **Administración de la organización \> Informes electrónicos \> Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-160">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="b62e7-161">En la página **Configuraciones**, en el árbol de configuraciones, seleccione **Configuración del modelo de ejemplo**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-161">On the **Configurations** page, in the configurations tree, select **Sample model configuration**.</span></span>

    <span data-ttu-id="b62e7-162">Debe seleccionar una configuración creada que ya se ha completado.</span><span class="sxs-lookup"><span data-stu-id="b62e7-162">You must select a created configuration that has been already completed.</span></span>

3. <span data-ttu-id="b62e7-163">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="b62e7-163">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="b62e7-164">Para este ejemplo, seleccione la versión de la configuración seleccionada que tiene un estado de **Completado**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-164">For this example, select the version of the selected configuration that has a status of **Completed**.</span></span>

4. <span data-ttu-id="b62e7-165">Seleccione **Cambiar estado**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-165">Select **Change status**.</span></span>
5. <span data-ttu-id="b62e7-166">Seleccione **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-166">Select **Share**.</span></span>

    <span data-ttu-id="b62e7-167">El estado de la configuración cambia de **Completado** a **Compartido** cuando la configuración se publica en LCS.</span><span class="sxs-lookup"><span data-stu-id="b62e7-167">The status of the configuration is changed from **Completed** to **Shared** when the configuration is published in LCS.</span></span>

6. <span data-ttu-id="b62e7-168">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-168">Select **OK**.</span></span>
7. <span data-ttu-id="b62e7-169">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="b62e7-169">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="b62e7-170">Para este ejemplo, seleccione la versión de la configuración que tiene un estado de **Compartido**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-170">For this example, select the configuration version that has a status of **Shared**.</span></span>

    <span data-ttu-id="b62e7-171">Tenga en cuenta que el estado de la versión seleccionada se cambió de **Completado** a **Compartido**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-171">Note that the status of the selected version was changed from **Completed** to **Shared**.</span></span>

8. <span data-ttu-id="b62e7-172">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b62e7-172">Close the page.</span></span>
9. <span data-ttu-id="b62e7-173">Seleccione **Repositorios**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-173">Select **Repositories**.</span></span>

    <span data-ttu-id="b62e7-174">Ahora puede abrir la lista de repositorios para el proveedor de configuración Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="b62e7-174">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

10. <span data-ttu-id="b62e7-175">Seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-175">Select **Open**.</span></span>

    <span data-ttu-id="b62e7-176">Para este ejemplo, seleccione el repositorio **LCS** y ábralo.</span><span class="sxs-lookup"><span data-stu-id="b62e7-176">For this example, select the **LCS** repository, and open it.</span></span>

    <span data-ttu-id="b62e7-177">Tenga en cuenta que la configuración seleccionada se muestra como activo del proyecto de LCS seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b62e7-177">Notice that the selected configuration is shown as an asset of the selected LCS project.</span></span>

11. <span data-ttu-id="b62e7-178">Abra LCS yendo a <https://lcs.dynamics.com>.</span><span class="sxs-lookup"><span data-stu-id="b62e7-178">Open LCS by going to <https://lcs.dynamics.com>.</span></span>
12. <span data-ttu-id="b62e7-179">Abra un proyecto que se utilizó anteriormente para el registro del repositorio.</span><span class="sxs-lookup"><span data-stu-id="b62e7-179">Open a project that was used earlier for repository registration.</span></span>
13. <span data-ttu-id="b62e7-180">Abra la biblioteca de activos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b62e7-180">Open the Asset library of the project.</span></span>
14. <span data-ttu-id="b62e7-181">Seleccione el tipo de activo **Configuración GER**.</span><span class="sxs-lookup"><span data-stu-id="b62e7-181">Select the **GER configuration** asset type.</span></span>

    <span data-ttu-id="b62e7-182">La configuración de ER que cargó debe aparecer en la lista.</span><span class="sxs-lookup"><span data-stu-id="b62e7-182">The ER configuration that you uploaded should be listed.</span></span>

    <span data-ttu-id="b62e7-183">Tenga en cuenta que la configuración de LCS cargada se puede importar a otra instancia si los proveedores tienen acceso a este proyecto de LCS.</span><span class="sxs-lookup"><span data-stu-id="b62e7-183">Note that the uploaded LCS configuration can be imported into another instance if providers have access to this LCS project.</span></span>
