--- 
title: "Importar configuraciones de informes electrónicos desde Lifecycle Services"
description: "En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede importar una nueva versión de una configuración de informe electrónico desde Microsoft Lifecycle Services (LCS)."
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
ms.openlocfilehash: f3b8cdb722cf49194faccc19fbb95265a230d48b
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---
# <a name="import-electronic-reporting-configurations-from-lifecycle-services"></a><span data-ttu-id="25406-103">Importar configuraciones de informes electrónicos desde Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="25406-103">Import Electronic reporting configurations from Lifecycle Services</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="25406-104">En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede importar una nueva versión de una configuración de informe electrónico desde Microsoft Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="25406-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can import a new version of an Electronic reporting (ER) configuration from Microsoft Lifecycle Services (LCS).</span></span>

<span data-ttu-id="25406-105">En este ejemplo, seleccionará la configuración de la versión deseada del ER y la importará a la empresa de demostración, Litware, Inc. Estos pasos se pueden realizar en cualquier empresa a medida que las configuraciones de ER se comparten entre todas las empresas.</span><span class="sxs-lookup"><span data-stu-id="25406-105">In this example, you will select the desired version of the ER configuration and import it for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="25406-106">Para completar estos pasos, primero debe completar los pasos del procedimiento "Cargar una configuración ER en Lifecycle Services".</span><span class="sxs-lookup"><span data-stu-id="25406-106">To complete these steps, you must first complete the steps in the “Upload an ER configuration into Lifecycle Services” procedure.</span></span> <span data-ttu-id="25406-107">También se requiere el acceso a LCS para finalizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="25406-107">Access to LCS is also required for completion of these steps.</span></span>

1. <span data-ttu-id="25406-108">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="25406-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="25406-109">Haga clic en Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="25406-109">Click Configurations.</span></span>

## <a name="delete-a-shared-version-of-data-model-configuration"></a><span data-ttu-id="25406-110">Eliminar una versión compartida de la configuración del modelo de datos</span><span class="sxs-lookup"><span data-stu-id="25406-110">Delete a shared version of data model configuration</span></span>
1. <span data-ttu-id="25406-111">En el árbol, seleccione "Configuración del modelo de ejemplo".</span><span class="sxs-lookup"><span data-stu-id="25406-111">In the tree, select 'Sample model configuration'.</span></span>
    * <span data-ttu-id="25406-112">Se ha creado la primera versión de la configuración del modelo de datos de muestra y se ha publicado en LCS durante el procedimiento "Cargar una configuración ER en Lifecycle Services".</span><span class="sxs-lookup"><span data-stu-id="25406-112">The first version of a sample data model configuration has been created and published to LCS during the “Upload an ER configuration into Lifecycle Services” procedure.</span></span> <span data-ttu-id="25406-113">En este procedimiento, eliminará esta versión de la configuración de ER.</span><span class="sxs-lookup"><span data-stu-id="25406-113">In this procedure, you will delete this version of the ER configuration.</span></span> <span data-ttu-id="25406-114">Esta versión de una configuración de modelo de datos de ejemplo se importará más tarde desde LCS.</span><span class="sxs-lookup"><span data-stu-id="25406-114">This version of a sample data model configuration will be imported later from LCS.</span></span>  
2. <span data-ttu-id="25406-115">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="25406-115">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="25406-116">Seleccione la versión de esta configuración que se encuentra en el estado "Compartido".</span><span class="sxs-lookup"><span data-stu-id="25406-116">Select the version of this configuration that is in the ‘Shared’ status.</span></span> <span data-ttu-id="25406-117">Este estado indica que la configuración se ha publicado en LCS.</span><span class="sxs-lookup"><span data-stu-id="25406-117">This status indicates that the configuration has been published to LCS.</span></span>  
3. <span data-ttu-id="25406-118">Haga clic en Cambiar estado.</span><span class="sxs-lookup"><span data-stu-id="25406-118">Click Change status.</span></span>
4. <span data-ttu-id="25406-119">Haga clic en Interrumpir.</span><span class="sxs-lookup"><span data-stu-id="25406-119">Click Discontinue.</span></span>
    * <span data-ttu-id="25406-120">Cambie el estado de la versión seleccionada de "Compartido" a "Interrumpido" para que esté disponible para la eliminación.</span><span class="sxs-lookup"><span data-stu-id="25406-120">Change the status of the selected version from ‘Shared’ to ‘Discontinued’ to make it available for deletion.</span></span>  
5. <span data-ttu-id="25406-121">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="25406-121">Click OK.</span></span>
6. <span data-ttu-id="25406-122">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="25406-122">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="25406-123">Seleccione la versión de esta configuración que tiene un estado de "Interrumpido".</span><span class="sxs-lookup"><span data-stu-id="25406-123">Select the version of this configuration that has a status of ‘Discontinued’.</span></span>  
7. <span data-ttu-id="25406-124">Haga clic Eliminar.</span><span class="sxs-lookup"><span data-stu-id="25406-124">Click Delete.</span></span>
8. <span data-ttu-id="25406-125">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="25406-125">Click Yes.</span></span>
    * <span data-ttu-id="25406-126">Tenga en cuenta que solo la versión de borrador 2 de la configuración del modelo de datos seleccionada está disponible.</span><span class="sxs-lookup"><span data-stu-id="25406-126">Note that the only draft version 2 of the selected data model configuration is available.</span></span>  
9. <span data-ttu-id="25406-127">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="25406-127">Close the page.</span></span>

## <a name="import-a-shared-version-of-data-model-configuration-from-lcs"></a><span data-ttu-id="25406-128">Importar una versión compartida de la configuración del modelo de datos de LCS</span><span class="sxs-lookup"><span data-stu-id="25406-128">Import a shared version of data model configuration from LCS</span></span>
1. <span data-ttu-id="25406-129">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="25406-129">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="25406-130">Abra la lista de repositorios para "Litware, Inc.".</span><span class="sxs-lookup"><span data-stu-id="25406-130">Open the list of repositories for the ‘Litware, Inc.’</span></span> <span data-ttu-id="25406-131">Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="25406-131">configuration provider.</span></span>  
2. <span data-ttu-id="25406-132">Haga clic en Repositorios.</span><span class="sxs-lookup"><span data-stu-id="25406-132">Click Repositories.</span></span>
3. <span data-ttu-id="25406-133">Haga clic en Abrir.</span><span class="sxs-lookup"><span data-stu-id="25406-133">Click Open.</span></span>
    * <span data-ttu-id="25406-134">Seleccione el repositorio de LCS y ábralo.</span><span class="sxs-lookup"><span data-stu-id="25406-134">Select the LCS repository and open it.</span></span>  
4. <span data-ttu-id="25406-135">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="25406-135">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="25406-136">Seleccionar la primera versión de "Configuración del modelo de ejemplo" en la lista de versiones.</span><span class="sxs-lookup"><span data-stu-id="25406-136">Select the first version of the 'Sample model configuration' in the versions list.</span></span>  
5. <span data-ttu-id="25406-137">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="25406-137">Click Import.</span></span>
6. <span data-ttu-id="25406-138">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="25406-138">Click Yes.</span></span>
    * <span data-ttu-id="25406-139">Confirme la importación de la versión seleccionada desde LCS.</span><span class="sxs-lookup"><span data-stu-id="25406-139">Confirm the import of the selected version from LCS .</span></span>  
    * <span data-ttu-id="25406-140">Tenga en cuenta que el mensaje de información (que se encuentra encima del formulario) confirma la finalización correcta de la importación de la versión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="25406-140">Note that the information message (above the form) confirms the successful completion of the import of the selected version.</span></span>  
7. <span data-ttu-id="25406-141">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="25406-141">Close the page.</span></span>
8. <span data-ttu-id="25406-142">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="25406-142">Close the page.</span></span>
9. <span data-ttu-id="25406-143">Haga clic en Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="25406-143">Click Configurations.</span></span>
10. <span data-ttu-id="25406-144">En el árbol, seleccione "Configuración del modelo de ejemplo".</span><span class="sxs-lookup"><span data-stu-id="25406-144">In the tree, select 'Sample model configuration'.</span></span>
11. <span data-ttu-id="25406-145">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="25406-145">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="25406-146">Seleccione la versión de esta configuración que tiene un estado de "Compartido".</span><span class="sxs-lookup"><span data-stu-id="25406-146">Select the version of this configuration that has a status of ‘Shared’.</span></span>  
    * <span data-ttu-id="25406-147">Tenga en cuenta que la versión compartida 1 de la configuración del modelo de datos seleccionada está disponible ahora también.</span><span class="sxs-lookup"><span data-stu-id="25406-147">Note that the shared version 1 of the selected data model configuration is available now as well.</span></span>  


