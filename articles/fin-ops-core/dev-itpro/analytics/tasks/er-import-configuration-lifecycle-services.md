---
title: Importar una configuración de Lifecycle Services
description: Este tema describe cómo importar una nueva versión de una configuración de informes electrónicos (ER) desde Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
ms.date: 06/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b58ecb8a7d6f52631dbca7642a4acbcf6ff895a3
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270846"
---
# <a name="import-a-configuration-from-lifecycle-services"></a><span data-ttu-id="38fb1-103">Importar una configuración de Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="38fb1-103">Import a configuration from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="38fb1-104">En este tema se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede importar una nueva versión de una [configuración de informe electrónico](../general-electronic-reporting.md#Configuration) desde la [biblioteca de activos de proyectos](../../lifecycle-services/asset-library.md) en Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="38fb1-104">This topic explains how a user in the System administrator or Electronic reporting developer role can import a new version of an [Electronic reporting (ER) configuration](../general-electronic-reporting.md#Configuration) from the [project-level Asset library](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38fb1-105">El uso de (LCS) como repositorio de almacenamiento para las configuraciones de ER se está poniendo [en desuso](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span><span class="sxs-lookup"><span data-stu-id="38fb1-105">The use of LCS as a storage repository for ER configurations is being [deprecated](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span></span> <span data-ttu-id="38fb1-106">Para más ifnormación, vea: [Regulatory Configuration Service (RCS): desactivación del almacenamiento de Lifecycle Services (LCS)](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md).</span><span class="sxs-lookup"><span data-stu-id="38fb1-106">For more information, see [Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) storage deprecation](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md).</span></span>

<span data-ttu-id="38fb1-107">En este ejemplo, seleccionará la configuración de la versión deseada del ER y la importará a la empresa de ejemplo que se llama Litware, Inc. Estos pasos se pueden realizar en cualquier empresa porque las configuraciones de ER se comparten entre todas las empresas.</span><span class="sxs-lookup"><span data-stu-id="38fb1-107">In this example, you will select the desired version of the ER configuration and import it for a sample company that is named Litware, Inc. These steps can be completed in any company, because ER configurations are shared among companies.</span></span> <span data-ttu-id="38fb1-108">Para completar estos pasos, primero debe completar los pasos del procedimiento [Cargar una configuración ER en Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span><span class="sxs-lookup"><span data-stu-id="38fb1-108">To complete these steps, you must first complete the steps in [Upload a configuration into Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span></span> <span data-ttu-id="38fb1-109">También se requiere acceso a LCS.</span><span class="sxs-lookup"><span data-stu-id="38fb1-109">Access to LCS is also required.</span></span>

1. <span data-ttu-id="38fb1-110">Inicie sesión a la aplicación mediante uno de los roles siguientes:</span><span class="sxs-lookup"><span data-stu-id="38fb1-110">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="38fb1-111">Desarrollador de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="38fb1-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="38fb1-112">Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="38fb1-112">System administrator</span></span>

2. <span data-ttu-id="38fb1-113">Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="38fb1-113">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="38fb1-114">Seleccione **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="38fb1-114">Select **Configurations**.</span></span>

<a name="accessconditions"></a>
> [!NOTE]
> <span data-ttu-id="38fb1-115">Asegúrese de que el usuario actual de Dynamics 365 Finance es miembro del proyecto LCS que contiene la biblioteca de activos al que el usuario desea [acceder](../../lifecycle-services/asset-library.md#asset-library-support) para importar configuraciones de ER.</span><span class="sxs-lookup"><span data-stu-id="38fb1-115">Make sure that the current Dynamics 365 Finance user is a member of the LCS project that contains the Asset library that the user wants to [access](../../lifecycle-services/asset-library.md#asset-library-support) to import ER configurations.</span></span>
>
> <span data-ttu-id="38fb1-116">No puede acceder a un proyecto LCS desde un repositorio de ER que representa un dominio diferente al dominio que se usa en Finance.</span><span class="sxs-lookup"><span data-stu-id="38fb1-116">You can't access an LCS project from an ER repository that represents a different domain than the domain that is used in Finance.</span></span> <span data-ttu-id="38fb1-117">Si lo intenta, se mostrará una lista vacía de proyectos LCS y no podrá importar configuraciones de ER desde la biblioteca de activos a nivel de proyecto en LCS.</span><span class="sxs-lookup"><span data-stu-id="38fb1-117">If you try, an empty list of LCS projects will be shown, and you won't be able to import ER configurations from the project-level Asset library in LCS.</span></span> <span data-ttu-id="38fb1-118">Para acceder a las bibliotecas de activos a nivel de proyecto desde un repositorio de ER que se utiliza para importar configuraciones de ER, inicie sesión en Finance utilizando las credenciales de un usuario que pertenezca al inquilino (dominio) para el que se ha aprovisionado la instancia de Finance actual.</span><span class="sxs-lookup"><span data-stu-id="38fb1-118">To access project-level Asset libraries from an ER repository that is used to import ER configurations, sign in to Finance by using the credentials of a user who belongs to the tenant (domain) that the current Finance instance has been provisioned for.</span></span>

## <a name="delete-a-shared-version-of-a-data-model-configuration"></a><span data-ttu-id="38fb1-119">Eliminar una versión compartida de la configuración del modelo de datos</span><span class="sxs-lookup"><span data-stu-id="38fb1-119">Delete a shared version of a data model configuration</span></span>

1. <span data-ttu-id="38fb1-120">En la página **Configuraciones**, en el árbol de configuraciones, seleccione **Configuración del modelo de ejemplo**.</span><span class="sxs-lookup"><span data-stu-id="38fb1-120">On the **Configurations** page, in the configurations tree, select **Sample model configuration**.</span></span>

    <span data-ttu-id="38fb1-121">Se ha creado la primera versión de la configuración del modelo de datos de muestra y se ha publicado en LCS cuando completó los pasos en [Cargar una configuración ER en Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span><span class="sxs-lookup"><span data-stu-id="38fb1-121">You created the first version of a sample data model configuration and published it to LCS when you completed the steps in [Upload a configuration into Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span></span> <span data-ttu-id="38fb1-122">En este procedimiento, eliminará esta versión de la configuración de ER.</span><span class="sxs-lookup"><span data-stu-id="38fb1-122">In this procedure, you will delete that version of the ER configuration.</span></span> <span data-ttu-id="38fb1-123">Luego, importará esa versión de LCS más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="38fb1-123">You will then import that version from LCS later in this topic.</span></span>

2. <span data-ttu-id="38fb1-124">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="38fb1-124">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="38fb1-125">Para este ejemplo, seleccione la versión de la configuración que tiene un estado de **Compartido**.</span><span class="sxs-lookup"><span data-stu-id="38fb1-125">For this example, select the version of the configuration that has a status of **Shared**.</span></span> <span data-ttu-id="38fb1-126">Este estado indica que la configuración se ha publicado en LCS.</span><span class="sxs-lookup"><span data-stu-id="38fb1-126">This status indicates that the configuration has been published to LCS.</span></span>

3. <span data-ttu-id="38fb1-127">Seleccione **Cambiar estado**.</span><span class="sxs-lookup"><span data-stu-id="38fb1-127">Select **Change status**.</span></span>
4. <span data-ttu-id="38fb1-128">Seleccione **Interrumpir**.</span><span class="sxs-lookup"><span data-stu-id="38fb1-128">Select **Discontinue**.</span></span>

    <span data-ttu-id="38fb1-129">Al cambiar el estado de la versión seleccionada de **Compartido** a **Interrumpido**, hace que la versión esté disponible para la eliminación.</span><span class="sxs-lookup"><span data-stu-id="38fb1-129">By changing the status of the selected version from **Shared** to **Discontinued**, you make the version available for deletion.</span></span>

5. <span data-ttu-id="38fb1-130">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="38fb1-130">Select **OK**.</span></span>
6. <span data-ttu-id="38fb1-131">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="38fb1-131">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="38fb1-132">Para este ejemplo, seleccione la versión de la configuración que tiene un estado de **Interrumpido**.</span><span class="sxs-lookup"><span data-stu-id="38fb1-132">For this example, select the version of the configuration that has a status of **Discontinued**.</span></span>

7. <span data-ttu-id="38fb1-133">Seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="38fb1-133">Select **Delete**.</span></span>
8. <span data-ttu-id="38fb1-134">Seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="38fb1-134">Select **Yes**.</span></span>

    <span data-ttu-id="38fb1-135">Tenga en cuenta que solo la versión de borrador 2 de la configuración del modelo de datos seleccionada está ahora disponible.</span><span class="sxs-lookup"><span data-stu-id="38fb1-135">Notice that the only draft version 2 of the selected data model configuration is now available.</span></span>

9. <span data-ttu-id="38fb1-136">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="38fb1-136">Close the page.</span></span>

## <a name="import-a-shared-version-of-a-data-model-configuration-from-lcs"></a><span data-ttu-id="38fb1-137">Importar una versión compartida de la configuración del modelo de datos de LCS</span><span class="sxs-lookup"><span data-stu-id="38fb1-137">Import a shared version of a data model configuration from LCS</span></span>

1. <span data-ttu-id="38fb1-138">Vaya a **Administración de la organización \> Espacios de trabajo \> Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="38fb1-138">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>

2. <span data-ttu-id="38fb1-139">En la sección **Proveedores de configuración**, seleccione el icono de **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="38fb1-139">In the **Configuration providers** section, select the **Litware, Inc.** tile.</span></span>

3. <span data-ttu-id="38fb1-140">En el icono **Litware, Inc.**, seleccione **Repositorios**.</span><span class="sxs-lookup"><span data-stu-id="38fb1-140">On the **Litware, Inc.** tile, select **Repositories**.</span></span>

    <span data-ttu-id="38fb1-141">Ahora puede abrir la lista de repositorios para el proveedor de configuración Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="38fb1-141">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

4. <span data-ttu-id="38fb1-142">Seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="38fb1-142">Select **Open**.</span></span>

    <span data-ttu-id="38fb1-143">Para este ejemplo, seleccione el repositorio **LCS** y ábralo.</span><span class="sxs-lookup"><span data-stu-id="38fb1-143">For this example, select the **LCS** repository, and open it.</span></span> <span data-ttu-id="38fb1-144">Debe tener [acceso](#accessconditions) al proyecto LCS y a la biblioteca de activos a la que accede el repositorio ER seleccionado.</span><span class="sxs-lookup"><span data-stu-id="38fb1-144">You must have [access](#accessconditions) to the LCS project and to the Asset library that is accessed by the selected ER repository.</span></span>

5. <span data-ttu-id="38fb1-145">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="38fb1-145">In the list, mark the selected row.</span></span>

    <span data-ttu-id="38fb1-146">Para este ejemplo, seleccione la primera versión de **Configuración del modelo de ejemplo** en la lista de versiones.</span><span class="sxs-lookup"><span data-stu-id="38fb1-146">For this example, select the first version of **Sample model configuration** in the version list.</span></span>

6. <span data-ttu-id="38fb1-147">Seleccione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="38fb1-147">Select **Import**.</span></span>
7. <span data-ttu-id="38fb1-148">Seleccione **Sí** para confirmar la importación de la versión seleccionada de LCS.</span><span class="sxs-lookup"><span data-stu-id="38fb1-148">Select **Yes** to confirm the import of the selected version from LCS.</span></span>

    <span data-ttu-id="38fb1-149">Un mensaje informativo confirma que la versión seleccionada se importó correctamente.</span><span class="sxs-lookup"><span data-stu-id="38fb1-149">An informational message confirms that the selected version was successfully imported.</span></span>

8. <span data-ttu-id="38fb1-150">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="38fb1-150">Close the page.</span></span>
9. <span data-ttu-id="38fb1-151">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="38fb1-151">Close the page.</span></span>
10. <span data-ttu-id="38fb1-152">Seleccione **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="38fb1-152">Select **Configurations**.</span></span>
11. <span data-ttu-id="38fb1-153">En el árbol, seleccione **Configuración del modelo de ejemplo**.</span><span class="sxs-lookup"><span data-stu-id="38fb1-153">In the tree, select **Sample model configuration**.</span></span>
12. <span data-ttu-id="38fb1-154">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="38fb1-154">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="38fb1-155">Para este ejemplo, seleccione la versión de la configuración que tiene un estado de **Compartido**.</span><span class="sxs-lookup"><span data-stu-id="38fb1-155">For this example, select the version of the configuration that has a status of **Shared**.</span></span>

    <span data-ttu-id="38fb1-156">Tenga en cuenta que la versión compartida 1 de la configuración del modelo de datos seleccionada está disponible ahora también.</span><span class="sxs-lookup"><span data-stu-id="38fb1-156">Notice that shared version 1 of the selected data model configuration is also available now.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
