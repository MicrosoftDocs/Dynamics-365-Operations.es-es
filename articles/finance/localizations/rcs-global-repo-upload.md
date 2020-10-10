---
title: Crear configuraciones de ER en RCS y cargarlas en el repositorio global
description: Este tema explica cómo crear una configuración de informes electrónicos (ER) en Regulatory Configuration Service (RCS) de Microsoft y cargarla al repositorio global.
author: JaneA07
manager: AnnBe
ms.date: 09/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 5b2b8f35b9931f8fd1824c20e9045da68af33ad5
ms.sourcegitcommit: 91e101d7a51a8b63bd196ec80e9224e5e6e6fc95
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "3834242"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a><span data-ttu-id="defa1-103">Crear configuraciones en Regulatory Configuration Services (RCS) y cargarlas en el repositorio global</span><span class="sxs-lookup"><span data-stu-id="defa1-103">Create ER configurations in Regulatory Configuration Services (RCS) and upload them to the Global repository</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="defa1-104">Puede usar Regulatory Configuration Services (RCS) de Microsoft para diseñar configuraciones de informes electrónicos (ER) y luego publicarlas, de forma que se puedan usar en su organización.</span><span class="sxs-lookup"><span data-stu-id="defa1-104">You can use Microsoft Regulatory Configuration Services (RCS) to design Electronic reporting (ER) configurations and publish them so that they can be used in your organization.</span></span>

<span data-ttu-id="defa1-105">Los siguientes procedimientos explican cómo un usuario en el rol de Administrador del sistema o Desarrollador de informes electrónicos puede crear una versión derivada de una configuración de ER que se haya configurado en una instancia de RCS y luego cargar la configuración derivada al repositorio global.</span><span class="sxs-lookup"><span data-stu-id="defa1-105">The following procedures explain how a user in the System Administrator or Electronic Reporting Developer role can create a derived version of an ER configuration that has been configured in an RCS instance, and then upload the derived configuration to the Global repository.</span></span> 

<span data-ttu-id="defa1-106">Para poder completar estos procedimientos, primero debe completar los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="defa1-106">Before you can complete those procedures, you must complete the following prerequisites:</span></span>

- <span data-ttu-id="defa1-107">Acceda a una instancia RCS.</span><span class="sxs-lookup"><span data-stu-id="defa1-107">Access an RCS instance.</span></span>
- <span data-ttu-id="defa1-108">Cree un proveedor de configuración activo.</span><span class="sxs-lookup"><span data-stu-id="defa1-108">Create an active configuration provider.</span></span> <span data-ttu-id="defa1-109">Para obtener más información, consulte [Crear proveedores de la configuración y marcarlos como activos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="defa1-109">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

<span data-ttu-id="defa1-110">También debe asegurarse de que se aprovisione un entorno RCS para su empresa.</span><span class="sxs-lookup"><span data-stu-id="defa1-110">You must also make sure that an RCS environment is provisioned for your company.</span></span>

1. <span data-ttu-id="defa1-111">En una aplicación de Finance and Operations, vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="defa1-111">In a Finance and Operations app, go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="defa1-112">Si no está aprovisionado ningún entorno RCS en la empresa, seleccione **Regulatory services: configuración externa** y luego siga las instrucciones para aprovisionar uno.</span><span class="sxs-lookup"><span data-stu-id="defa1-112">If no RCS environment is provisioned for your company, select **Regulatory services – Configuration external**, and then follow the instructions to provision one.</span></span>

<span data-ttu-id="defa1-113">Si ya se ha aprovisionado un entorno RCS para su empresa, use la URL de la página para acceder a él seleccionando la opción de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="defa1-113">If an RCS environment has been already provisioned for your company, use the page URL to access it by selecting the sign-in option.</span></span>

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a><span data-ttu-id="defa1-114">Crear una versión derivada de una configuración en RCS</span><span class="sxs-lookup"><span data-stu-id="defa1-114">Create a derived version of a configuration in RCS</span></span>

1. <span data-ttu-id="defa1-115">En el espacio de trabajo **Informes electrónicos**, verifique tener un proveedor de configuración activo para su organización.</span><span class="sxs-lookup"><span data-stu-id="defa1-115">In the **Electronic reporting** workspace, verify that you have an active configuration provider for your organization.</span></span> 
2. <span data-ttu-id="defa1-116">Seleccione **Configuraciones de informes**.</span><span class="sxs-lookup"><span data-stu-id="defa1-116">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="defa1-117">Seleccione la configuración de la que desea derivar una nueva versión.</span><span class="sxs-lookup"><span data-stu-id="defa1-117">Select the configuration that you want to derive a new version from.</span></span> <span data-ttu-id="defa1-118">Puede utilizar el campo de filtro que hay sobre el árbol para precisar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="defa1-118">You can use the filter field above the tree to narrow your search.</span></span>
4. <span data-ttu-id="defa1-119">Seleccione **Crear configuración** \> **Derivar del nombre**.</span><span class="sxs-lookup"><span data-stu-id="defa1-119">Select **Create configuration** \> **Derive from Name**.</span></span>
5. <span data-ttu-id="defa1-120">Introduzca un nombre y una descripción, y luego seleccione **Crear configuración** para crear una nueva versión derivada.</span><span class="sxs-lookup"><span data-stu-id="defa1-120">Enter a name and description, and then select **Create configuration** to create a new derived version.</span></span>
6. <span data-ttu-id="defa1-121">Seleccione la configuración recién derivada, agregue una descripción de la versión y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="defa1-121">Select the newly derived configuration, add a description of the version, and then select **OK**.</span></span> <span data-ttu-id="defa1-122">El estado de la configuración se cambia a **Completado**.</span><span class="sxs-lookup"><span data-stu-id="defa1-122">The status of the configuration to is changed to **Completed**.</span></span>

![Nueva versión de configuración en RCS](media/RCS_CompleteConfig.JPG)

> [!NOTE]
> <span data-ttu-id="defa1-124">Cuando se cambia el estado de la configuración, es posible que reciba un mensaje de error de validación relacionado con las aplicaciones conectadas.</span><span class="sxs-lookup"><span data-stu-id="defa1-124">When the configuration status is changed, you might receive a validation error message that is related to the connected applications.</span></span> <span data-ttu-id="defa1-125">Para desactivar la validación, en el Panel de acciones de la pestaña **Configuraciones**, seleccione **Parámetros de usuario** y luego establezca la opción **Omitir validación en el cambio de estado y reorganización de la configuración** en **Sí**</span><span class="sxs-lookup"><span data-stu-id="defa1-125">To turn off the validation, on the Action Pane on the **Configurations** tab, select **User parameters**, and then set the **Skip validation at configuration's status change and rebase** option to **Yes**</span></span> 

## <a name="upload-a-configuration-to-the-global-repository"></a><span data-ttu-id="defa1-126">Cargar una configuración al repositorio global</span><span class="sxs-lookup"><span data-stu-id="defa1-126">Upload a configuration to the Global repository</span></span>

<span data-ttu-id="defa1-127">Para compartir una configuración nueva o derivada con su organización, puede subirla al repositorio global.</span><span class="sxs-lookup"><span data-stu-id="defa1-127">To share a new or derived configuration with your organization, you can upload it to the Global repository.</span></span>

1. <span data-ttu-id="defa1-128">Seleccione la versión completa de la configuración y luego seleccione **Cargar al repositorio**.</span><span class="sxs-lookup"><span data-stu-id="defa1-128">Select the completed version of the configuration, and then select **Upload into repository**.</span></span>
2. <span data-ttu-id="defa1-129">Seleccione la opción **Global (Microsoft)** y luego seleccione **Cargar**.</span><span class="sxs-lookup"><span data-stu-id="defa1-129">Select the **Global (Microsoft)** option, and then select **Upload**.</span></span>

    ![Cargar en opciones de repositorio](media/RCS_Upload_to_GlobalRepo_options.JPG)

3. <span data-ttu-id="defa1-131">En el cuadro de mensaje de confirmación, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="defa1-131">In the confirmation message box, select **Yes**.</span></span> 
4. <span data-ttu-id="defa1-132">Actualice la descripción de la versión según sea necesario y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="defa1-132">Update the description of the version as required, and then select **OK**.</span></span> 

<span data-ttu-id="defa1-133">El estado de la configuración se actualiza a **Compartir**, y la configuración se carga en el repositorio global.</span><span class="sxs-lookup"><span data-stu-id="defa1-133">The status of the configuration is updated to **Share**, and the configuration is uploaded to the Global repository.</span></span> <span data-ttu-id="defa1-134">A partir de ahí, puede trabajar con ella de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="defa1-134">From there, you can work with it in the following ways:</span></span>

- <span data-ttu-id="defa1-135">Impórtela a su instancia de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="defa1-135">Import it into your Dynamics 365 instance.</span></span> <span data-ttu-id="defa1-136">Para obtener más información, consulte [Importar configuraciones (ER) desde RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).</span><span class="sxs-lookup"><span data-stu-id="defa1-136">For more information, see [(ER) Import configurations from RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).</span></span>
- <span data-ttu-id="defa1-137">Compártalo con un tercero o una organización externa, consulte [Configuraciones de informes electrónicos (ER) de uso compartido de RCS con organizaciones externas](rcs-global-repo-share-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="defa1-137">Share it with a third party or an external organization, see [RCS Share Electronic reporting (ER) configurations with external organizations](rcs-global-repo-share-configuration.md)</span></span>

    ![Versión de configuración de Intrastat Contoso derivada en el repositorio global](media/RCS_Config_upload_GlobalRepo.JPG)

## <a name="delete-a-configuration-from-the-global-repository"></a><span data-ttu-id="defa1-139">Eliminar una configuración del repositorio global</span><span class="sxs-lookup"><span data-stu-id="defa1-139">Delete a configuration from the Global repository</span></span>
<span data-ttu-id="defa1-140">Complete los siguientes pasos para eliminar una configuración creada por su organización.</span><span class="sxs-lookup"><span data-stu-id="defa1-140">Complete the following steps to delete a configuration that your organization has created.</span></span>

1. <span data-ttu-id="defa1-141">En el espacio de trabajo **Informes electrónicos**, compruebe que su proveedor de configuración esté **Activo**.</span><span class="sxs-lookup"><span data-stu-id="defa1-141">In the **Electronic reporting** workspace, verify that your configuration provider is **Active**.</span></span> <span data-ttu-id="defa1-142">Para obtener más información, consulte [Crear proveedores de la configuración y marcarlos como activos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="defa1-142">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
2. <span data-ttu-id="defa1-143">En el proveedor de configuración activo, seleccione **repositorio**.</span><span class="sxs-lookup"><span data-stu-id="defa1-143">On your active configuration provider, select **repository**.</span></span>
3. <span data-ttu-id="defa1-144">Seleccione el tipo de repositorio **Global** y después seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="defa1-144">Select the repository type **Global**, and select **Open**.</span></span>
4. <span data-ttu-id="defa1-145">En la ficha desplegable **Filtrar**, busque la configuración que desea eliminar mediante la funcionalidad de **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="defa1-145">On the **Filter** FastTab, find the configuration that you want to delete by using the **Filter** functionality.</span></span>
5. <span data-ttu-id="defa1-146">En la ficha desplegable **Versión**, seleccione la versión de la configuración que desea eliminar y, a continuación, seleccione **Eliminar**:</span><span class="sxs-lookup"><span data-stu-id="defa1-146">On the **Version** FastTab, select the version of the configuration that you want to delete, and then select **Delete**:</span></span>

    ![Eliminar una configuración del repositorio global](media/RCS_Delete_from_GlobalRepo.JPG)

6. <span data-ttu-id="defa1-148">En el cuadro de mensaje de confirmación, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="defa1-148">In the confirmation message box, select **Yes**.</span></span>

    ![Eliminar el mensaje de confirmación de una versión de configuración](media/RCS_Delete_from_GlobalRepo_Msg.JPG)
 
<span data-ttu-id="defa1-150">Se elimina la versión de configuración y se muestra un mensaje de confirmación.</span><span class="sxs-lookup"><span data-stu-id="defa1-150">The configuration version is deleted, and confirmation message is shown.</span></span> 

> [!NOTE]
> <span data-ttu-id="defa1-151">Las configuraciones solo las puede eliminar el proveedor de configuración que las creó.</span><span class="sxs-lookup"><span data-stu-id="defa1-151">Configurations can only be deleted by the Configuration provider that created them.</span></span> <span data-ttu-id="defa1-152">Si la configuración se ha compartido con otra organización, será necesario dejar de compartir la configuración antes de eliminarla.</span><span class="sxs-lookup"><span data-stu-id="defa1-152">If the configuration has been shared with another organization, the configuration will need to be unshared before you delete it.</span></span>
 
