---
title: Cargar una configuración en Lifecycle Services
description: En este tema se explica cómo crear una nueva configuración de Informes electrónicos (ER) y subirla a Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
ms.date: 06/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 41a8fcf2592bde4901aba703e0cd124b1155dac6
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270568"
---
# <a name="upload-a-configuration-into-lifecycle-services"></a><span data-ttu-id="7b895-103">Cargar una configuración en Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="7b895-103">Upload a configuration into Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7b895-104">En este tema se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede cargar una nueva versión de una [configuración de informe electrónico](../general-electronic-reporting.md#Configuration) y cargarla en la [biblioteca de activos de proyectos](../../lifecycle-services/asset-library.md) en Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="7b895-104">This topic explains how a user in the System administrator or Electronic reporting developer role can create a new [Electronic reporting (ER) configuration](../general-electronic-reporting.md#Configuration) and upload it into the [project-level Asset library](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7b895-105">El uso de (LCS) como repositorio de almacenamiento para las configuraciones de ER se está poniendo [en desuso](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span><span class="sxs-lookup"><span data-stu-id="7b895-105">The use of LCS as a storage repository for ER configurations is being [deprecated](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span></span> <span data-ttu-id="7b895-106">Para más ifnormación, vea: [Regulatory Configuration Service (RCS): desactivación del almacenamiento de Lifecycle Services (LCS)](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md).</span><span class="sxs-lookup"><span data-stu-id="7b895-106">For more information, see [Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) storage deprecation](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md).</span></span>

<span data-ttu-id="7b895-107">En este ejemplo, creará una configuración y la cargará a LCS para la empresa de demostración que se llama Litware, Inc. Estos pasos se pueden completarse en cualquier empresa porque las configuraciones de ER se comparten entre las empresas.</span><span class="sxs-lookup"><span data-stu-id="7b895-107">In this example, you will create a configuration and upload it into LCS for a sample company that is named Litware, Inc. These steps can be completed in any company, because ER configurations are shared among companies.</span></span> <span data-ttu-id="7b895-108">Para completar estos pasos, primero debe completar los pasos en [Crear proveedores de configuración y marcarlos como activos](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="7b895-108">To complete these steps, you must first complete the steps in [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="7b895-109">También se requiere acceso a LCS.</span><span class="sxs-lookup"><span data-stu-id="7b895-109">Access to LCS is also required.</span></span>

1. <span data-ttu-id="7b895-110">Inicie sesión a la aplicación mediante uno de los roles siguientes:</span><span class="sxs-lookup"><span data-stu-id="7b895-110">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="7b895-111">Desarrollador de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="7b895-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="7b895-112">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="7b895-112">System administrator</span></span>

2. <span data-ttu-id="7b895-113">Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="7b895-113">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="7b895-114">Seleccione **Litware, Inc.** y márquela como **Activa**.</span><span class="sxs-lookup"><span data-stu-id="7b895-114">Select **Litware, Inc.**, and mark it as **Active**.</span></span>
4. <span data-ttu-id="7b895-115">Seleccione **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="7b895-115">Select **Configurations**.</span></span>

<a name="accessconditions"></a>
> [!NOTE]
> <span data-ttu-id="7b895-116">Asegúrese de que el usuario actual de Dynamics 365 Finance es miembro del proyecto LCS que contiene la [biblioteca de activos](../../lifecycle-services/asset-library.md#asset-library-support) que se usa para importar configuraciones de ER.</span><span class="sxs-lookup"><span data-stu-id="7b895-116">Make sure that the current Dynamics 365 Finance user is a member of the LCS project that contains the [Asset library](../../lifecycle-services/asset-library.md#asset-library-support) that is used to import ER configurations.</span></span>
>
> <span data-ttu-id="7b895-117">No puede acceder a un proyecto LCS desde un repositorio de ER que representa un dominio diferente al dominio que se usa en Finance.</span><span class="sxs-lookup"><span data-stu-id="7b895-117">You can't access an LCS project from an ER repository that represents a different domain than the domain that is used in Finance.</span></span> <span data-ttu-id="7b895-118">Si lo intenta, se mostrará una lista vacía de proyectos LCS y no podrá importar configuraciones de ER desde la biblioteca de activos a nivel de proyecto en LCS.</span><span class="sxs-lookup"><span data-stu-id="7b895-118">If you try, an empty list of LCS projects will be shown, and you won't be able to import ER configurations from the project-level Asset library in LCS.</span></span> <span data-ttu-id="7b895-119">Para acceder a las bibliotecas de activos a nivel de proyecto desde un repositorio de ER que se utiliza para importar configuraciones de ER, inicie sesión en Finance utilizando las credenciales de un usuario que pertenezca al inquilino (dominio) para el que se ha aprovisionado la instancia de Finance actual.</span><span class="sxs-lookup"><span data-stu-id="7b895-119">To access project-level Asset libraries from an ER repository that is used to import ER configurations, sign in to Finance by using the credentials of a user who belongs to the tenant (domain) that the current Finance instance has been provisioned for.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="7b895-120">Creación de un nuevo modelo de configuración de datos</span><span class="sxs-lookup"><span data-stu-id="7b895-120">Create a new data model configuration</span></span>

1. <span data-ttu-id="7b895-121">Vaya a **Administración de la organización \> Informes electrónicos \> Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="7b895-121">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="7b895-122">En la página **Configuraciones**, seleccione **Crear configuración** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="7b895-122">On the **Configurations** page, select **Create configuration** to open the drop-down dialog box.</span></span>

    <span data-ttu-id="7b895-123">En este ejemplo, creará una configuración que contenga un modelo de datos de muestra para los documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="7b895-123">In this example, you will create a configuration that contains a sample data model for electronic documents.</span></span> <span data-ttu-id="7b895-124">Esta configuración del modelo de datos se cargará en LCS más adelante.</span><span class="sxs-lookup"><span data-stu-id="7b895-124">This data model configuration will be uploaded into LCS later.</span></span>

3. <span data-ttu-id="7b895-125">En el campo **Nombre**, escriba **Configuración del modelo de ejemplo**.</span><span class="sxs-lookup"><span data-stu-id="7b895-125">In the **Name** field, enter **Sample model configuration**.</span></span>
4. <span data-ttu-id="7b895-126">En el campo **Descripción**, escriba **Configuración del modelo de ejemplo**.</span><span class="sxs-lookup"><span data-stu-id="7b895-126">In the **Description** field, enter **Sample model configuration**.</span></span>
5. <span data-ttu-id="7b895-127">Seleccionar **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="7b895-127">Select **Create configuration**.</span></span>
6. <span data-ttu-id="7b895-128">Seleccione **Diseñador de modelos**.</span><span class="sxs-lookup"><span data-stu-id="7b895-128">Select **Model designer**.</span></span>
7. <span data-ttu-id="7b895-129">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="7b895-129">Select **New**.</span></span>
8. <span data-ttu-id="7b895-130">En el campo **Nombre**, escriba **Punto de entrada**.</span><span class="sxs-lookup"><span data-stu-id="7b895-130">In the **Name** field, enter **Entry point**.</span></span>
9. <span data-ttu-id="7b895-131">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="7b895-131">Select **Add**.</span></span>
10. <span data-ttu-id="7b895-132">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7b895-132">Select **Save**.</span></span>
11. <span data-ttu-id="7b895-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7b895-133">Close the page.</span></span>
12. <span data-ttu-id="7b895-134">Seleccione **Cambiar estado**.</span><span class="sxs-lookup"><span data-stu-id="7b895-134">Select **Change status**.</span></span>
13. <span data-ttu-id="7b895-135">Seleccione **Completar**.</span><span class="sxs-lookup"><span data-stu-id="7b895-135">Select **Complete**.</span></span>
14. <span data-ttu-id="7b895-136">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7b895-136">Select **OK**.</span></span>
15. <span data-ttu-id="7b895-137">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7b895-137">Close the page.</span></span>

## <a name="register-a-new-repository"></a><span data-ttu-id="7b895-138">Registrar uno nuevo repositorio</span><span class="sxs-lookup"><span data-stu-id="7b895-138">Register a new repository</span></span>

1. <span data-ttu-id="7b895-139">Vaya a **Administración de la organización \> Espacios de trabajo \> Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="7b895-139">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>

2. <span data-ttu-id="7b895-140">En la sección **Proveedores de configuración**, seleccione el icono de **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="7b895-140">In the **Configuration providers** section, select the **Litware, Inc.** tile.</span></span>

3. <span data-ttu-id="7b895-141">En el icono **Litware, Inc.**, seleccione **Repositorios**.</span><span class="sxs-lookup"><span data-stu-id="7b895-141">On the **Litware, Inc.** tile, select **Repositories**.</span></span>

    <span data-ttu-id="7b895-142">Ahora puede abrir la lista de repositorios para el proveedor de configuración Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="7b895-142">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

4. <span data-ttu-id="7b895-143">Seleccione **Agregar** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="7b895-143">Select **Add** to open the drop-down dialog box.</span></span>

    <span data-ttu-id="7b895-144">Ahora puede agregar un nuevo repositorio.</span><span class="sxs-lookup"><span data-stu-id="7b895-144">You can now add a new repository.</span></span>

5. <span data-ttu-id="7b895-145">En el campo para especificar el **Repositorio de configuración**, escriba **LCS**.</span><span class="sxs-lookup"><span data-stu-id="7b895-145">In the **Configuration repository enter** field, select **LCS**.</span></span>
6. <span data-ttu-id="7b895-146">Seleccione **Crear repositorio**.</span><span class="sxs-lookup"><span data-stu-id="7b895-146">Select **Create repository**.</span></span>
7. <span data-ttu-id="7b895-147">En el campo **Proyecto**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="7b895-147">In the **Project** field, enter or select a value.</span></span>

    <span data-ttu-id="7b895-148">Para este ejemplo, seleccione el proyecto LCS deseado.</span><span class="sxs-lookup"><span data-stu-id="7b895-148">For this example, select the desired LCS project.</span></span> <span data-ttu-id="7b895-149">Debe tener [acceso](#accessconditions) al proyecto.</span><span class="sxs-lookup"><span data-stu-id="7b895-149">You must have [access](#accessconditions) to the project.</span></span>

8. <span data-ttu-id="7b895-150">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7b895-150">Select **OK**.</span></span>

    <span data-ttu-id="7b895-151">Complete una nueva entrada de repositorio.</span><span class="sxs-lookup"><span data-stu-id="7b895-151">Complete a new repository entry.</span></span>

9. <span data-ttu-id="7b895-152">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7b895-152">In the list, mark the selected row.</span></span>

    <span data-ttu-id="7b895-153">Para este ejemplo, seleccione el registro del repositorio **LCS**.</span><span class="sxs-lookup"><span data-stu-id="7b895-153">For this example, select the **LCS** repository record.</span></span>

    <span data-ttu-id="7b895-154">Tenga en cuenta que un repositorio registrado está marcado por el proveedor actual.</span><span class="sxs-lookup"><span data-stu-id="7b895-154">Note that a registered repository is marked by the current provider.</span></span> <span data-ttu-id="7b895-155">En otras palabras, solo las configuraciones que son propiedad de ese proveedor pueden colocarse en este repositorio y, por lo tanto, cargarse en el proyecto LCS seleccionado.</span><span class="sxs-lookup"><span data-stu-id="7b895-155">In other words, only configurations that are owned by that provider can be put in this repository and therefore uploaded into the selected LCS project.</span></span>

10. <span data-ttu-id="7b895-156">Seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="7b895-156">Select **Open**.</span></span>

    <span data-ttu-id="7b895-157">Abre el repositorio para ver la lista de configuraciones de ER.</span><span class="sxs-lookup"><span data-stu-id="7b895-157">You open the repository to view the list of ER configurations.</span></span> <span data-ttu-id="7b895-158">Si seleccione un proyecto que no ha usado para compartir las configuraciones de ER, la lista estará vacía.</span><span class="sxs-lookup"><span data-stu-id="7b895-158">If the selected project hasn't yet been used for ER configurations sharing, the list will be empty.</span></span>

11. <span data-ttu-id="7b895-159">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7b895-159">Close the page.</span></span>
12. <span data-ttu-id="7b895-160">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7b895-160">Close the page.</span></span>

## <a name="upload-a-configuration-into-lcs"></a><span data-ttu-id="7b895-161">Cargar una configuración en LCS</span><span class="sxs-lookup"><span data-stu-id="7b895-161">Upload a configuration into LCS</span></span>

1. <span data-ttu-id="7b895-162">Vaya a **Administración de la organización \> Informes electrónicos \> Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="7b895-162">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="7b895-163">En la página **Configuraciones**, en el árbol de configuraciones, seleccione **Configuración del modelo de ejemplo**.</span><span class="sxs-lookup"><span data-stu-id="7b895-163">On the **Configurations** page, in the configurations tree, select **Sample model configuration**.</span></span>

    <span data-ttu-id="7b895-164">Debe seleccionar una configuración creada que ya se ha completado.</span><span class="sxs-lookup"><span data-stu-id="7b895-164">You must select a created configuration that has been already completed.</span></span>

3. <span data-ttu-id="7b895-165">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="7b895-165">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="7b895-166">Para este ejemplo, seleccione la versión de la configuración seleccionada que tiene un estado de **Completado**.</span><span class="sxs-lookup"><span data-stu-id="7b895-166">For this example, select the version of the selected configuration that has a status of **Completed**.</span></span>

4. <span data-ttu-id="7b895-167">Seleccione **Cambiar estado**.</span><span class="sxs-lookup"><span data-stu-id="7b895-167">Select **Change status**.</span></span>
5. <span data-ttu-id="7b895-168">Seleccione **Compartir**.</span><span class="sxs-lookup"><span data-stu-id="7b895-168">Select **Share**.</span></span>

    <span data-ttu-id="7b895-169">El estado de la configuración cambia de **Completado** a **Compartido** cuando la configuración se publica en LCS.</span><span class="sxs-lookup"><span data-stu-id="7b895-169">The status of the configuration is changed from **Completed** to **Shared** when the configuration is published in LCS.</span></span>

6. <span data-ttu-id="7b895-170">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7b895-170">Select **OK**.</span></span>
7. <span data-ttu-id="7b895-171">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="7b895-171">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="7b895-172">Para este ejemplo, seleccione la versión de la configuración que tiene un estado de **Compartido**.</span><span class="sxs-lookup"><span data-stu-id="7b895-172">For this example, select the configuration version that has a status of **Shared**.</span></span>

    <span data-ttu-id="7b895-173">Tenga en cuenta que el estado de la versión seleccionada se cambió de **Completado** a **Compartido**.</span><span class="sxs-lookup"><span data-stu-id="7b895-173">Note that the status of the selected version was changed from **Completed** to **Shared**.</span></span>

8. <span data-ttu-id="7b895-174">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7b895-174">Close the page.</span></span>
9. <span data-ttu-id="7b895-175">Seleccione **Repositorios**.</span><span class="sxs-lookup"><span data-stu-id="7b895-175">Select **Repositories**.</span></span>

    <span data-ttu-id="7b895-176">Ahora puede abrir la lista de repositorios para el proveedor de configuración Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="7b895-176">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

10. <span data-ttu-id="7b895-177">Seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="7b895-177">Select **Open**.</span></span>

    <span data-ttu-id="7b895-178">Para este ejemplo, seleccione el repositorio **LCS** y ábralo.</span><span class="sxs-lookup"><span data-stu-id="7b895-178">For this example, select the **LCS** repository, and open it.</span></span>

    <span data-ttu-id="7b895-179">Tenga en cuenta que la configuración seleccionada se muestra como activo del proyecto de LCS seleccionado.</span><span class="sxs-lookup"><span data-stu-id="7b895-179">Notice that the selected configuration is shown as an asset of the selected LCS project.</span></span>

11. <span data-ttu-id="7b895-180">Abra LCS yendo a <https://lcs.dynamics.com>.</span><span class="sxs-lookup"><span data-stu-id="7b895-180">Open LCS by going to <https://lcs.dynamics.com>.</span></span>
12. <span data-ttu-id="7b895-181">Abra un proyecto que se utilizó anteriormente para el registro del repositorio.</span><span class="sxs-lookup"><span data-stu-id="7b895-181">Open a project that was used earlier for repository registration.</span></span>
13. <span data-ttu-id="7b895-182">Abra la biblioteca de activos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7b895-182">Open the Asset library of the project.</span></span>
14. <span data-ttu-id="7b895-183">Seleccione el tipo de activo **Configuración GER**.</span><span class="sxs-lookup"><span data-stu-id="7b895-183">Select the **GER configuration** asset type.</span></span>

    <span data-ttu-id="7b895-184">La configuración de ER que cargó debe aparecer en la lista.</span><span class="sxs-lookup"><span data-stu-id="7b895-184">The ER configuration that you uploaded should be listed.</span></span>

    <span data-ttu-id="7b895-185">Tenga en cuenta que la configuración de LCS cargada se puede importar a otra instancia si los proveedores tienen acceso a este proyecto de LCS.</span><span class="sxs-lookup"><span data-stu-id="7b895-185">Note that the uploaded LCS configuration can be imported into another instance if providers have access to this LCS project.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
