---
title: Complemento de visibilidad de inventario
description: Este tema describe cómo instalar y configurar el complemento de visibilidad de inventario para Dynamics 365 Supply Chain Management.
author: sherry-zheng
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: e294ada8dd3e764987aa363adb2614416986575b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821138"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="8da42-103">Complemento de visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="8da42-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

<span data-ttu-id="8da42-104">El complemento de visibilidad de inventario es un microservicio independiente y altamente escalable que permite el seguimiento del inventario disponible en tiempo real, lo que proporciona una vista global de la visibilidad del inventario.</span><span class="sxs-lookup"><span data-stu-id="8da42-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="8da42-105">Toda la información relacionada con el inventario disponible se exporta al servicio casi en tiempo real mediante la integración de SQL de bajo nivel.</span><span class="sxs-lookup"><span data-stu-id="8da42-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="8da42-106">Los sistemas externos acceden al servicio a través de API RESTful para consultar información disponible sobre conjuntos de dimensiones dados, recuperando así una lista de posiciones disponibles disponibles.</span><span class="sxs-lookup"><span data-stu-id="8da42-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="8da42-107">Inventory Visibility es un microservicio construido en Microsoft Dataverse, lo que significa que puede ampliarlo creando Power Apps y aplicando Power BI para proporcionar una funcionalidad personalizada para satisfacer los requisitos de su negocio.</span><span class="sxs-lookup"><span data-stu-id="8da42-107">Inventory Visibility is a microservice built on Microsoft Dataverse, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="8da42-108">También es posible actualizar el índice para realizar consultas de inventario.</span><span class="sxs-lookup"><span data-stu-id="8da42-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="8da42-109">Inventory Visibility ofrece opciones de configuración que le permiten integrarse con varios sistemas de terceros.</span><span class="sxs-lookup"><span data-stu-id="8da42-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="8da42-110">Admite la dimensión de inventario estandarizado, la extensibilidad personalizada y las cantidades calculadas configurables estandarizadas.</span><span class="sxs-lookup"><span data-stu-id="8da42-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="8da42-111">Este tema describe cómo instalar y configurar el complemento de visibilidad de inventario para Dynamics 365 Supply Chain Management y cómo utilizar su interfaz de programación de aplicaciones (API).</span><span class="sxs-lookup"><span data-stu-id="8da42-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="8da42-112">Instalar el complemento de visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="8da42-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="8da42-113">Debe instalar el complemento de visibilidad de inventario mediante Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="8da42-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="8da42-114">LCS es un portal de colaboración que proporciona un entorno y un conjunto de servicios actualizados periódicamente que le ayudan a gestionar el ciclo de vida de la aplicación de sus aplicaciones de Dynamics 365 Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8da42-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="8da42-115">Para obtener más información, consulte [Recursos de Lifecycle Services](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span><span class="sxs-lookup"><span data-stu-id="8da42-115">For more information, see [Lifecycle Services resources](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span></span>

### <a name="prerequisites"></a><span data-ttu-id="8da42-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8da42-116">Prerequisites</span></span>

<span data-ttu-id="8da42-117">Para poder instalar el complemento de visibilidad de inventario, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8da42-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="8da42-118">Obtenga un proyecto de implementación de LCS con al menos un entorno implementado.</span><span class="sxs-lookup"><span data-stu-id="8da42-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="8da42-119">Asegúrese de que los requisitos previos para configurar complementos proporcionados en [Descripción general de los complementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) ha sido completado.</span><span class="sxs-lookup"><span data-stu-id="8da42-119">Make sure that the prerequisites for setting up add-ins provided in the [Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) have been completed.</span></span> <span data-ttu-id="8da42-120">La visibilidad de inventario no requiere vinculación de escritura dual.</span><span class="sxs-lookup"><span data-stu-id="8da42-120">Inventory Visibility doesn't require dual-write linking.</span></span>
- <span data-ttu-id="8da42-121">Póngase en contacto con el equipo de visibilidad del inventario en [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para obtener los siguientes tres archivos obligatorios:</span><span class="sxs-lookup"><span data-stu-id="8da42-121">Contact the Inventory Visibility Team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the following three required files:</span></span>

    - `Inventory Visibility Dataverse Solution.zip`
    - `Inventory Visibility Configuration Trigger.zip`
    - <span data-ttu-id="8da42-122">`Inventory Visibility Integration.zip` (si la versión de Supply Chain Management que está ejecutando es anterior a la versión 10.0.18)</span><span class="sxs-lookup"><span data-stu-id="8da42-122">`Inventory Visibility Integration.zip` (if the version of Supply Chain Management that you're running is earlier than version 10.0.18)</span></span>

> [!NOTE]
> <span data-ttu-id="8da42-123">Los países y regiones admitidos actualmente incluyen Canadá, Estados Unidos y la Unión Europea (UE).</span><span class="sxs-lookup"><span data-stu-id="8da42-123">The currently supported countries and regions include Canada, the United States, and the European Union (EU).</span></span>

<span data-ttu-id="8da42-124">Si tiene alguna pregunta sobre estos requisitos previos, comuníquese con el equipo de productos de visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="8da42-124">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a><span data-ttu-id="8da42-125">Configurar Dataverse</span><span class="sxs-lookup"><span data-stu-id="8da42-125">Set up Dataverse</span></span>

<span data-ttu-id="8da42-126">Para configurar Dataverse, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8da42-126">Follow these steps to set up Dataverse.</span></span>

1. <span data-ttu-id="8da42-127">Agregue un principio de servicio a su inquilino:</span><span class="sxs-lookup"><span data-stu-id="8da42-127">Add a service principle to your tenant:</span></span>

    1. <span data-ttu-id="8da42-128">Instale Azure AD PowerShell Module v2 como se describe en [Instalar Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="8da42-128">Install Azure AD PowerShell Module v2 as described in [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
    1. <span data-ttu-id="8da42-129">Ejecute el siguiente comando de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8da42-129">Run the following PowerShell command.</span></span>

        ```powershell
        Connect-AzureAD # (open a sign in window and sign in as a tenant user)

        New-AzureADServicePrincipal -AppId "3022308a-b9bd-4a18-b8ac-2ddedb2075e1" -DisplayName "d365-scm-inventoryservice"
        ```

1. <span data-ttu-id="8da42-130">Cree un usuario de la aplicación para la visibilidad del inventario en Dataverse:</span><span class="sxs-lookup"><span data-stu-id="8da42-130">Create an application user for Inventory Visibility in Dataverse:</span></span>

    1. <span data-ttu-id="8da42-131">Abra la URL de su entorno de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="8da42-131">Open the URL of your Dataverse environment.</span></span>
    1. <span data-ttu-id="8da42-132">Ir **Configuración avanzada \> Sistema \> Seguridad \> Usuarios** y cree un usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8da42-132">Go to **Advanced Setting \> System \> Security \> Users**, and create an application user.</span></span> <span data-ttu-id="8da42-133">Use el menú de vista para cambiar la vista de página a **Usuarios de la aplicación**.</span><span class="sxs-lookup"><span data-stu-id="8da42-133">Use the view menu to change the page view to **Application Users**.</span></span>
    1. <span data-ttu-id="8da42-134">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="8da42-134">Select **New**.</span></span> <span data-ttu-id="8da42-135">Establezca el Id. de aplicación en *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span><span class="sxs-lookup"><span data-stu-id="8da42-135">Set the application ID to *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span></span> <span data-ttu-id="8da42-136">(El ID del objeto se cargará automáticamente cuando guarde los cambios). Puede personalizar el nombre.</span><span class="sxs-lookup"><span data-stu-id="8da42-136">(The object ID will automatically be loaded when you save your changes.) You can customize the name.</span></span> <span data-ttu-id="8da42-137">Por ejemplo, puede cambiarlo a *Visibilidad de inventario*.</span><span class="sxs-lookup"><span data-stu-id="8da42-137">For example, you can change it to *Inventory Visibility*.</span></span> <span data-ttu-id="8da42-138">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8da42-138">When you've finished, select **Save**.</span></span>
    1. <span data-ttu-id="8da42-139">Seleccione **Asignar rol** y luego seleccione **Administrador de sistema**.</span><span class="sxs-lookup"><span data-stu-id="8da42-139">Select **Assign Role**, and then select **System Administrator**.</span></span> <span data-ttu-id="8da42-140">Si hay un rol que se llama **Usuario de Common Data Service**, selecciónelo también.</span><span class="sxs-lookup"><span data-stu-id="8da42-140">If there is a role that is named **Common Data Service User**, select it too.</span></span>

    <span data-ttu-id="8da42-141">Para obtener más información, consulte [Crear un usuario de aplicación](https://docs.microsoft.com/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span><span class="sxs-lookup"><span data-stu-id="8da42-141">For more information, see [Create an application user](https://docs.microsoft.com/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span></span>

1. <span data-ttu-id="8da42-142">Importe el archivo `Inventory Visibility Dataverse Solution.zip`, que incluye las entidades relacionadas con la configuración de Dataverse y Power Apps:</span><span class="sxs-lookup"><span data-stu-id="8da42-142">Import the `Inventory Visibility Dataverse Solution.zip` file, which includes Dataverse configuration related entities and Power Apps:</span></span>

    1. <span data-ttu-id="8da42-143">Vaya a la página **Soluciones**.</span><span class="sxs-lookup"><span data-stu-id="8da42-143">Go to the **Solutions** page.</span></span>
    1. <span data-ttu-id="8da42-144">Seleccione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="8da42-144">Select **Import**.</span></span>

1. <span data-ttu-id="8da42-145">Importe el flujo de activación de la actualización de la configuración:</span><span class="sxs-lookup"><span data-stu-id="8da42-145">Import the configuration upgrade trigger flow:</span></span>

    1. <span data-ttu-id="8da42-146">Vaya a la página de Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="8da42-146">Go to the Microsoft Flow page.</span></span>
    1. <span data-ttu-id="8da42-147">Asegúrese de que la conexión que se denomina *Dataverse (heredado)* existe.</span><span class="sxs-lookup"><span data-stu-id="8da42-147">Make sure that the connection that is named *Dataverse (legacy)* exists.</span></span> <span data-ttu-id="8da42-148">(Si no existe, créela).</span><span class="sxs-lookup"><span data-stu-id="8da42-148">(If it doesn't exist, create it.)</span></span>
    1. <span data-ttu-id="8da42-149">Importe el archivo `Inventory Visibility Configuration Trigger.zip`.</span><span class="sxs-lookup"><span data-stu-id="8da42-149">Import the `Inventory Visibility Configuration Trigger.zip` file.</span></span> <span data-ttu-id="8da42-150">Una vez importado, el disparador aparecerá debajo de **Mis flujos**.</span><span class="sxs-lookup"><span data-stu-id="8da42-150">After it's imported, the trigger will appear under **My flows**.</span></span>
    1. <span data-ttu-id="8da42-151">Inicialice las siguientes cuatro variables, según la información del entorno:</span><span class="sxs-lookup"><span data-stu-id="8da42-151">Initialize the following four variables, based on the environment information:</span></span>

        - <span data-ttu-id="8da42-152">Id. de inquilino de Azure</span><span class="sxs-lookup"><span data-stu-id="8da42-152">Azure Tenant ID</span></span>
        - <span data-ttu-id="8da42-153">Id. de cliente de aplicación de Azure</span><span class="sxs-lookup"><span data-stu-id="8da42-153">Azure Application Client ID</span></span>
        - <span data-ttu-id="8da42-154">Secreto de cliente de aplicación de Azure</span><span class="sxs-lookup"><span data-stu-id="8da42-154">Azure Application Client Secret</span></span>
        - <span data-ttu-id="8da42-155">Punto de conexión de Visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="8da42-155">Inventory Visibility Endpoint</span></span>

            <span data-ttu-id="8da42-156">Para obtener más información sobre esta variable, consulte la sección [Configurar la integración de visibilidad de inventario](#setup-inventory-visibility-integration) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="8da42-156">For more information about this variable, see the [Set up Inventory Visibility integration](#setup-inventory-visibility-integration) section later in this topic.</span></span>

        <span data-ttu-id="8da42-157">![Desencadenador de configuración](media/configuration-trigger.png "Desencadenador de configuración")</span><span class="sxs-lookup"><span data-stu-id="8da42-157">![Configuration trigger](media/configuration-trigger.png "Configuration trigger")</span></span>

    1. <span data-ttu-id="8da42-158">Seleccione **Encender**.</span><span class="sxs-lookup"><span data-stu-id="8da42-158">Select **Turn on**.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="8da42-159">Instalar el complemento</span><span class="sxs-lookup"><span data-stu-id="8da42-159">Install the add-in</span></span>

<span data-ttu-id="8da42-160">Para instalar el complemento de visibilidad de inventario, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8da42-160">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="8da42-161">Inicie sesión en el portal de [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="8da42-161">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="8da42-162">En la página de inicio, seleccione el proyecto donde se implementa su entorno.</span><span class="sxs-lookup"><span data-stu-id="8da42-162">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="8da42-163">En la página del proyecto, seleccione el entorno donde desea instalar el complemento.</span><span class="sxs-lookup"><span data-stu-id="8da42-163">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="8da42-164">En la página del entorno, desplácese hacia abajo hasta que vea la sección **Complementos de entorno** en la sección **Integración de Power Platform**, donde puede encontrar el nombre del entorno Dataverse.</span><span class="sxs-lookup"><span data-stu-id="8da42-164">On the environment page, scroll down until you see the **Environment add-ins** section in the **Power Platform integration** section, where you can find the Dataverse environment name.</span></span>
1. <span data-ttu-id="8da42-165">En la sección **Complementos de entorno**, seleccione **Instalar un nuevo complemento**.</span><span class="sxs-lookup"><span data-stu-id="8da42-165">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>

    <span data-ttu-id="8da42-166">![Página de entorno en LCS](media/inventory-visibility-environment.png "Página de entorno en LCS")</span><span class="sxs-lookup"><span data-stu-id="8da42-166">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>

1. <span data-ttu-id="8da42-167">Seleccione el vínculo **Instalar un nuevo complemento**.</span><span class="sxs-lookup"><span data-stu-id="8da42-167">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="8da42-168">Se abre una lista de complementos disponibles.</span><span class="sxs-lookup"><span data-stu-id="8da42-168">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="8da42-169">En la lista, seleccione **Visibilidad de inventario**.</span><span class="sxs-lookup"><span data-stu-id="8da42-169">Select **Inventory Visibility** in the list.</span></span>
1. <span data-ttu-id="8da42-170">Ingrese valores para los siguientes campos para su entorno:</span><span class="sxs-lookup"><span data-stu-id="8da42-170">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="8da42-171">**ID de aplicación de AAD (cliente)**</span><span class="sxs-lookup"><span data-stu-id="8da42-171">**AAD application (client) ID**</span></span>
    - <span data-ttu-id="8da42-172">**Id. de suscriptor de AAD**</span><span class="sxs-lookup"><span data-stu-id="8da42-172">**AAD tenant ID**</span></span>

    <span data-ttu-id="8da42-173">![Agregar en la página de configuración](media/inventory-visibility-setup.png "Página de configuración del complemento")</span><span class="sxs-lookup"><span data-stu-id="8da42-173">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="8da42-174">Acepte los términos y condiciones seleccionando la casilla de verificación **Términos y Condiciones**.</span><span class="sxs-lookup"><span data-stu-id="8da42-174">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="8da42-175">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="8da42-175">Select **Install**.</span></span> <span data-ttu-id="8da42-176">El estado del complemento se mostrará como **Instalando**.</span><span class="sxs-lookup"><span data-stu-id="8da42-176">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="8da42-177">Cuando haya terminado, actualice la página para ver el cambio de estado a **Instalado**.</span><span class="sxs-lookup"><span data-stu-id="8da42-177">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="uninstall-the-add-in"></a><a name="uninstall-add-in"></a><span data-ttu-id="8da42-178">Desinstalar el complemento</span><span class="sxs-lookup"><span data-stu-id="8da42-178">Uninstall the add-in</span></span>

<span data-ttu-id="8da42-179">Para desinstalar el complemento, seleccione **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="8da42-179">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="8da42-180">Cuando actualice LCS, el complemento de visibilidad de inventario se eliminarán.</span><span class="sxs-lookup"><span data-stu-id="8da42-180">When you refresh LCS, the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="8da42-181">El proceso de desinstalación elimina el registro del complemento y también inicia un trabajo para limpiar todos los datos comerciales almacenados en el servicio.</span><span class="sxs-lookup"><span data-stu-id="8da42-181">The uninstall process removes the add-in registration and also starts a job to clean up all the business data that is stored in the service.</span></span>

## <a name="consume-on-hand-inventory-data-from-supply-chain-management"></a><span data-ttu-id="8da42-182">Consumir datos de inventario disponibles de Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="8da42-182">Consume on-hand inventory data from Supply Chain Management</span></span>

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a><span data-ttu-id="8da42-183">Implementar el paquete de integración de visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="8da42-183">Deploy the Inventory Visibility integration package</span></span>

<span data-ttu-id="8da42-184">Si está ejecutando Supply Chain Management versión 10.0.17 o anterior, comuníquese con el equipo de soporte a bordo de Inventory Visibility en [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para obtener el archivo del paquete.</span><span class="sxs-lookup"><span data-stu-id="8da42-184">If you're running Supply Chain Management version 10.0.17 or earlier, contact the Inventory Visibility on-board support team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the package file.</span></span> <span data-ttu-id="8da42-185">Luego implemente el paquete en LCS.</span><span class="sxs-lookup"><span data-stu-id="8da42-185">Then deploy the package in LCS.</span></span>

> [!NOTE]
> <span data-ttu-id="8da42-186">Si se produce un error de discrepancia de versión durante la implementación, debe importar manualmente el proyecto X ++ a su entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="8da42-186">If a version mismatch error occurs during deployment, you must manually import the X++ project into your development environment.</span></span> <span data-ttu-id="8da42-187">Luego, cree el paquete implementable en su entorno de desarrollo e impleméntelo en su entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="8da42-187">Then create the deployable package in your development environment, and deploy it in your production environment.</span></span>
> 
> <span data-ttu-id="8da42-188">El código se incluye con Supply Chain Management versión 10.0.18.</span><span class="sxs-lookup"><span data-stu-id="8da42-188">The code is included with Supply Chain Management version 10.0.18.</span></span> <span data-ttu-id="8da42-189">Si está ejecutando esa versión o una posterior, la implementación no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="8da42-189">If you're running that version or later, deployment isn't required.</span></span>

<span data-ttu-id="8da42-190">Asegúrese de que las siguientes funciones estén activadas en su entorno de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8da42-190">Make sure that the following features are turned on in your Supply Chain Management environment.</span></span> <span data-ttu-id="8da42-191">(De forma predeterminada, están activadas).</span><span class="sxs-lookup"><span data-stu-id="8da42-191">(By default, they are turned on.)</span></span>

| <span data-ttu-id="8da42-192">Descripción de la característica</span><span class="sxs-lookup"><span data-stu-id="8da42-192">Feature description</span></span> | <span data-ttu-id="8da42-193">Versión de código</span><span class="sxs-lookup"><span data-stu-id="8da42-193">Code version</span></span> | <span data-ttu-id="8da42-194">Alternar clase</span><span class="sxs-lookup"><span data-stu-id="8da42-194">Toggle class</span></span> |
|---|---|---|
| <span data-ttu-id="8da42-195">Habilitar o deshabilitar el uso de dimensiones de inventario en la tabla InventSum</span><span class="sxs-lookup"><span data-stu-id="8da42-195">Enable or disable using inventory dimensions on InventSum table</span></span> | <span data-ttu-id="8da42-196">10.0.11</span><span class="sxs-lookup"><span data-stu-id="8da42-196">10.0.11</span></span> | <span data-ttu-id="8da42-197">InventUseDimOfInventSumToggle</span><span class="sxs-lookup"><span data-stu-id="8da42-197">InventUseDimOfInventSumToggle</span></span> |
| <span data-ttu-id="8da42-198">Habilitar o deshabilitar el uso de dimensiones de inventario en la tabla InventSumDelta</span><span class="sxs-lookup"><span data-stu-id="8da42-198">Enable or disable using inventory dimensions on InventSumDelta table</span></span> | <span data-ttu-id="8da42-199">10.0.12</span><span class="sxs-lookup"><span data-stu-id="8da42-199">10.0.12</span></span> | <span data-ttu-id="8da42-200">InventUseDimOfInventSumDeltaToggle</span><span class="sxs-lookup"><span data-stu-id="8da42-200">InventUseDimOfInventSumDeltaToggle</span></span> |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a><span data-ttu-id="8da42-201">Configurar integración de Visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="8da42-201">Set up Inventory Visibility integration</span></span>

1. <span data-ttu-id="8da42-202">En Supply Chain Management, abra el espacio de trabajo **[Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** y active la caracterísica **Integración de visibilidad de inventario**.</span><span class="sxs-lookup"><span data-stu-id="8da42-202">In Supply Chain Management, open the **[Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** workspace, and turn on the **Inventory Visibility Integration** feature.</span></span>
1. <span data-ttu-id="8da42-203">Ir **Gestión del inventario \> Configurar \> Parámetros de integración de visibilidad de inventario** e ingrese la URL del entorno en el que está ejecutando Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="8da42-203">Go to **Inventory Management \> Set up \> Inventory Visibility Integration parameters**, and enter the URL of the environment where you're running Inventory Visibility.</span></span>

    <span data-ttu-id="8da42-204">Busque la región de Azure de su entorno LCS y luego ingrese la URL.</span><span class="sxs-lookup"><span data-stu-id="8da42-204">Find your LCS environment's Azure region, and then enter the URL.</span></span> <span data-ttu-id="8da42-205">La URL tiene el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="8da42-205">The URL has the following form:</span></span>

    `https://inventoryservice.<RegionShortName>-il301.gateway.prod.island.powerapps.com/`

    <span data-ttu-id="8da42-206">Por ejemplo, si se encuentra en Europa, su entorno tendrá una de las siguientes URL:</span><span class="sxs-lookup"><span data-stu-id="8da42-206">For example, if you're in Europe, your environment will have one of the following URLs:</span></span>

    - `https://inventoryservice.neu-il301.gateway.prod.island.powerapps.com/`
    - `https://inventoryservice.weu-il301.gateway.prod.island.powerapps.com/`

    <span data-ttu-id="8da42-207">Tiene a su disposición las siguientes regiones:</span><span class="sxs-lookup"><span data-stu-id="8da42-207">The following regions are currently available.</span></span>

    | <span data-ttu-id="8da42-208">Región de Azure</span><span class="sxs-lookup"><span data-stu-id="8da42-208">Azure region</span></span> | <span data-ttu-id="8da42-209">Nombre corto de la región</span><span class="sxs-lookup"><span data-stu-id="8da42-209">Region short name</span></span> |
    |---|---|
    | <span data-ttu-id="8da42-210">Este de Australia</span><span class="sxs-lookup"><span data-stu-id="8da42-210">Australia east</span></span> | <span data-ttu-id="8da42-211">eau</span><span class="sxs-lookup"><span data-stu-id="8da42-211">eau</span></span> |
    | <span data-ttu-id="8da42-212">Sudeste de Australia</span><span class="sxs-lookup"><span data-stu-id="8da42-212">Australia southeast</span></span> | <span data-ttu-id="8da42-213">seau</span><span class="sxs-lookup"><span data-stu-id="8da42-213">seau</span></span> |
    | <span data-ttu-id="8da42-214">Canadá central</span><span class="sxs-lookup"><span data-stu-id="8da42-214">Canada central</span></span> | <span data-ttu-id="8da42-215">cca</span><span class="sxs-lookup"><span data-stu-id="8da42-215">cca</span></span> |
    | <span data-ttu-id="8da42-216">Este de Canadá</span><span class="sxs-lookup"><span data-stu-id="8da42-216">Canada east</span></span> | <span data-ttu-id="8da42-217">eca</span><span class="sxs-lookup"><span data-stu-id="8da42-217">eca</span></span> |
    | <span data-ttu-id="8da42-218">Norte de Europa</span><span class="sxs-lookup"><span data-stu-id="8da42-218">North Europe</span></span> | <span data-ttu-id="8da42-219">neu</span><span class="sxs-lookup"><span data-stu-id="8da42-219">neu</span></span> |
    | <span data-ttu-id="8da42-220">Europa Occidental</span><span class="sxs-lookup"><span data-stu-id="8da42-220">West Europe</span></span> | <span data-ttu-id="8da42-221">weu</span><span class="sxs-lookup"><span data-stu-id="8da42-221">weu</span></span> |
    | <span data-ttu-id="8da42-222">Este de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="8da42-222">East US</span></span> | <span data-ttu-id="8da42-223">eus</span><span class="sxs-lookup"><span data-stu-id="8da42-223">eus</span></span> |
    | <span data-ttu-id="8da42-224">Oeste de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="8da42-224">West US</span></span> | <span data-ttu-id="8da42-225">wus</span><span class="sxs-lookup"><span data-stu-id="8da42-225">wus</span></span> |

1. <span data-ttu-id="8da42-226">Ir **Gestión del inventario \> Periódico \> Integración de visibilidad de inventario** y habilite el trabajo.</span><span class="sxs-lookup"><span data-stu-id="8da42-226">Go to **Inventory Management \> Periodic \> Inventory Visibility Integration**, and enable the job.</span></span> <span data-ttu-id="8da42-227">Todos los eventos de cambio de inventario de Supply Chain Management ahora se publicarán en Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="8da42-227">All inventory change events from Supply Chain Management will now be posted to Inventory Visibility.</span></span>

## <a name="the-inventory-visibility-add-in-public-api"></a><a name="inventory-visibility-public-api"></a><span data-ttu-id="8da42-228">API pública de complemento de visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="8da42-228">The Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="8da42-229">La API de REST pública del complemento de visibilidad de inventario presenta varios puntos finales específicos para integración.</span><span class="sxs-lookup"><span data-stu-id="8da42-229">The public REST API of the Inventory Visibility Add-in presents several specific endpoints for integration.</span></span> <span data-ttu-id="8da42-230">Admite tres tipos principales de interacción:</span><span class="sxs-lookup"><span data-stu-id="8da42-230">It supports three main interaction types:</span></span>

- <span data-ttu-id="8da42-231">Publicar cambios de inventario disponible en el complemento desde un sistema externo</span><span class="sxs-lookup"><span data-stu-id="8da42-231">Posting on-hand inventory changes to the add-in from an external system</span></span>
- <span data-ttu-id="8da42-232">Consultar cantidades actuales disponibles desde un sistema externo</span><span class="sxs-lookup"><span data-stu-id="8da42-232">Querying current on-hand quantities from an external system</span></span>
- <span data-ttu-id="8da42-233">Sincronización automática con el inventario disponible de Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="8da42-233">Automatic synchronization with Supply Chain Management on-hand inventory</span></span>

<span data-ttu-id="8da42-234">La sincronización automática no forma parte de la API pública.</span><span class="sxs-lookup"><span data-stu-id="8da42-234">Automatic synchronization isn't part of the public API.</span></span> <span data-ttu-id="8da42-235">En su lugar, se maneja en segundo plano para entornos en los que el complemento de visibilidad de inventario está habilitado.</span><span class="sxs-lookup"><span data-stu-id="8da42-235">Instead, it's handled in the background for environments where the Inventory Visibility Add-in is enabled.</span></span>

### <a name="authentication"></a><a name="inventory-visibility-authentication"></a><span data-ttu-id="8da42-236">Autentificación</span><span class="sxs-lookup"><span data-stu-id="8da42-236">Authentication</span></span>

<span data-ttu-id="8da42-237">El token de seguridad de la plataforma se utiliza para llamar al complemento de visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="8da42-237">The platform security token is used to call the Inventory Visibility Add-in.</span></span> <span data-ttu-id="8da42-238">Por lo tanto, debe generar un *token de Azure Active Directory (Azure AD)* usando su aploicación de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8da42-238">Therefore, you must generate an *Azure Active Directory (Azure AD) token* by using your Azure AD application.</span></span> <span data-ttu-id="8da42-239">A continuación, debe utilizar el token de Azure AD para obtener el *token de acceso* del servicio de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8da42-239">You must then use the Azure AD token to get the *access token* from the security service.</span></span>

<span data-ttu-id="8da42-240">Obtenga un token de servicio de seguridad de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="8da42-240">Get a security service token by doing the following:</span></span>

1. <span data-ttu-id="8da42-241">Inicie sesión en Azure Portal y utilícelo para encontrar el `clientId` y el `clientSecret` para su aplicación Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8da42-241">Sign in to Azure portal and use it to find the `clientId` and `clientSecret` for your Supply Chain Management application.</span></span>
1. <span data-ttu-id="8da42-242">Busque un token Azure Active Directory (`aadToken`) enviando una solicitud HTTP con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="8da42-242">Fetch an Azure Active Directory token (`aadToken`) by submitting an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="8da42-243">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span><span class="sxs-lookup"><span data-stu-id="8da42-243">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span></span>
    - <span data-ttu-id="8da42-244">**Método** - `GET`</span><span class="sxs-lookup"><span data-stu-id="8da42-244">**Method** - `GET`</span></span>
    - <span data-ttu-id="8da42-245">**Contenido del cuerpo (datos del formulario)**:</span><span class="sxs-lookup"><span data-stu-id="8da42-245">**Body content (form data)**:</span></span>

        | <span data-ttu-id="8da42-246">key</span><span class="sxs-lookup"><span data-stu-id="8da42-246">key</span></span> | <span data-ttu-id="8da42-247">valor</span><span class="sxs-lookup"><span data-stu-id="8da42-247">value</span></span> |
        | --- | --- |
        | <span data-ttu-id="8da42-248">client_id</span><span class="sxs-lookup"><span data-stu-id="8da42-248">client_id</span></span> | <span data-ttu-id="8da42-249">${aadAppId}</span><span class="sxs-lookup"><span data-stu-id="8da42-249">${aadAppId}</span></span> |
        | <span data-ttu-id="8da42-250">client_secret</span><span class="sxs-lookup"><span data-stu-id="8da42-250">client_secret</span></span> | <span data-ttu-id="8da42-251">${aadAppSecret}</span><span class="sxs-lookup"><span data-stu-id="8da42-251">${aadAppSecret}</span></span> |
        | <span data-ttu-id="8da42-252">grant_type</span><span class="sxs-lookup"><span data-stu-id="8da42-252">grant_type</span></span> | <span data-ttu-id="8da42-253">client_credentials</span><span class="sxs-lookup"><span data-stu-id="8da42-253">client_credentials</span></span> |
        | <span data-ttu-id="8da42-254">resource</span><span class="sxs-lookup"><span data-stu-id="8da42-254">resource</span></span> | <span data-ttu-id="8da42-255">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="8da42-255">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
1. <span data-ttu-id="8da42-256">Debería recibir un `aadToken` en respuesta, que se parece al siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8da42-256">You should receive an `aadToken` in response, which resembles the following example.</span></span>

    ```json
    {
    "token_type": "Bearer",
    "expires_in": "3599",
    "ext_expires_in": "3599",
    "expires_on": "1610466645",
    "not_before": "1610462745",
    "resource": "0cdb527f-a8d1-4bf8-9436-b352c68682b2",
    "access_token": "eyJ0eX...8WQ"
    }
    ```

1. <span data-ttu-id="8da42-257">Formule una solicitud JSON similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="8da42-257">Formulate a JSON request that resembles the following:</span></span>

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{Your_AADToken}",
        "scope":"https://inventoryservice.operations365.dynamics.com/.default",
        "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
        "context_type": "finops-env"
    }
    ```

    <span data-ttu-id="8da42-258">Donde:</span><span class="sxs-lookup"><span data-stu-id="8da42-258">Where:</span></span>
    - <span data-ttu-id="8da42-259">El valor `client_assertion` debe ser el `aadToken` que recibió en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="8da42-259">The `client_assertion` value must be the `aadToken` you received in the previous step.</span></span>
    - <span data-ttu-id="8da42-260">El valor `context` debe ser el ID de entorno en el que desea implementar el complemento.</span><span class="sxs-lookup"><span data-stu-id="8da42-260">The `context` value must be the environment ID where you want to deploy the add-in.</span></span>
    - <span data-ttu-id="8da42-261">Configure todos los demás valores como se muestra en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8da42-261">Set all of other values as shown in the example.</span></span>

1. <span data-ttu-id="8da42-262">Envíe una solicitud HTTP con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="8da42-262">Submit an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="8da42-263">**URL** - `https://securityservice.operations365.dynamics.com/token`</span><span class="sxs-lookup"><span data-stu-id="8da42-263">**URL** - `https://securityservice.operations365.dynamics.com/token`</span></span>
    - <span data-ttu-id="8da42-264">**Método** - `POST`</span><span class="sxs-lookup"><span data-stu-id="8da42-264">**Method** - `POST`</span></span>
    - <span data-ttu-id="8da42-265">**Encabezado HTTP** - Incluya la versión de API (la clave es `Api-Version` y el valor es `1.0`)</span><span class="sxs-lookup"><span data-stu-id="8da42-265">**HTTP header** - Include the API version (key is `Api-Version` and value is `1.0`)</span></span>
    - <span data-ttu-id="8da42-266">**Contenido del cuerpo** - Incluya la solicitud JSON que creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="8da42-266">**Body content** - Include the JSON request that you created in the previous step.</span></span>

1. <span data-ttu-id="8da42-267">Obtendrá `access_token` como respuesta.</span><span class="sxs-lookup"><span data-stu-id="8da42-267">You will get an `access_token` in response.</span></span> <span data-ttu-id="8da42-268">Esto es lo que necesita como token de portador para llamar a la API de visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="8da42-268">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="8da42-269">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8da42-269">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="configure-the-inventory-visibility-api"></a><a name="inventory-visibility-configuration"></a><span data-ttu-id="8da42-270">Configurar la API de visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="8da42-270">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="8da42-271">Antes de utilizar el servicio, debe completar las configuraciones descritas en las siguientes subsecciones.</span><span class="sxs-lookup"><span data-stu-id="8da42-271">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="8da42-272">La configuración puede variar según los detalles de su entorno.</span><span class="sxs-lookup"><span data-stu-id="8da42-272">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="8da42-273">Incluye principalmente cuatro partes:</span><span class="sxs-lookup"><span data-stu-id="8da42-273">It primarily includes four parts:</span></span>

- [<span data-ttu-id="8da42-274">Partición</span><span class="sxs-lookup"><span data-stu-id="8da42-274">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="8da42-275">Configuraciones de dimensiones</span><span class="sxs-lookup"><span data-stu-id="8da42-275">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="8da42-276">Indexación</span><span class="sxs-lookup"><span data-stu-id="8da42-276">Indexing</span></span>](#indexing)
- [<span data-ttu-id="8da42-277">Medida personalizada</span><span class="sxs-lookup"><span data-stu-id="8da42-277">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="8da42-278">Partición</span><span class="sxs-lookup"><span data-stu-id="8da42-278">Partitioning</span></span>

<span data-ttu-id="8da42-279">El particionamiento puede influir significativamente en el rendimiento de la API de visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="8da42-279">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="8da42-280">Es una buena idea definir un esquema que permita pequeñas agrupaciones de datos y al mismo tiempo permita consultas de datos significativas.</span><span class="sxs-lookup"><span data-stu-id="8da42-280">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="8da42-281">`organizationId` (`dataAreaId` en Supply Chain Management) siempre formará parte de la partición y, de forma predeterminada, la Visibilidad de inventario está configurada para particionar por dimensiones como *Sitio + Ubicación*.</span><span class="sxs-lookup"><span data-stu-id="8da42-281">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="8da42-282">Esto significa que el servicio siempre debe consultarse con estas dimensiones definidas en los filtros.</span><span class="sxs-lookup"><span data-stu-id="8da42-282">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="8da42-283">*Sitio* y *Ubicación* son dos dimensiones predeterminadas generales en Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="8da42-283">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="8da42-284">En Supply Chain Management, esas dimensiones se denominan *Sitio* (`InventSiteId`) y *Almacén* (`InventLocationId`)</span><span class="sxs-lookup"><span data-stu-id="8da42-284">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="8da42-285">Configuraciones de dimensiones</span><span class="sxs-lookup"><span data-stu-id="8da42-285">Dimension configurations</span></span>

<span data-ttu-id="8da42-286">Inventory Visibility proporcionará una lista de dimensiones predeterminadas generales para permitir la integración del sistema de múltiples fuentes.</span><span class="sxs-lookup"><span data-stu-id="8da42-286">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="8da42-287">La siguiente tabla enumera las dimensiones de inventario que serán los nombres de dimensión predeterminados en Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="8da42-287">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="8da42-288">Tipo de dimensión</span><span class="sxs-lookup"><span data-stu-id="8da42-288">Dimension type</span></span> | <span data-ttu-id="8da42-289">Nombre de dimensión</span><span class="sxs-lookup"><span data-stu-id="8da42-289">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="8da42-290">Producto</span><span class="sxs-lookup"><span data-stu-id="8da42-290">Product</span></span> | `ColorId` |
| <span data-ttu-id="8da42-291">Producto</span><span class="sxs-lookup"><span data-stu-id="8da42-291">Product</span></span> | `SizeId` |
| <span data-ttu-id="8da42-292">Producto</span><span class="sxs-lookup"><span data-stu-id="8da42-292">Product</span></span> | `StyleId` |
| <span data-ttu-id="8da42-293">Producto</span><span class="sxs-lookup"><span data-stu-id="8da42-293">Product</span></span> | `ConfigId` |
| <span data-ttu-id="8da42-294">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="8da42-294">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="8da42-295">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="8da42-295">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="8da42-296">Ubicación</span><span class="sxs-lookup"><span data-stu-id="8da42-296">Location</span></span> | `LocationId` |
| <span data-ttu-id="8da42-297">Ubicación</span><span class="sxs-lookup"><span data-stu-id="8da42-297">Location</span></span> | `SiteId` |
| <span data-ttu-id="8da42-298">Estado de inventario</span><span class="sxs-lookup"><span data-stu-id="8da42-298">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="8da42-299">Específico del almacén</span><span class="sxs-lookup"><span data-stu-id="8da42-299">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="8da42-300">Específico del almacén</span><span class="sxs-lookup"><span data-stu-id="8da42-300">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="8da42-301">Específico del almacén</span><span class="sxs-lookup"><span data-stu-id="8da42-301">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="8da42-302">El tipo de dimensión enumerado en la tabla anterior es solo para referencia.</span><span class="sxs-lookup"><span data-stu-id="8da42-302">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="8da42-303">No es necesario definir el tipo de dimensión en Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="8da42-303">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="8da42-304">Si existe una dimensión personalizada y necesita fluir a un valor predeterminado cuando la usa Inventory Visibility, puede configurar el nombre de la **Dimensión personalizada** en Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="8da42-304">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="8da42-305">Los sistemas externos acceden a la visibilidad del inventario a través de API RESTful que permiten consultar información disponible sobre conjuntos de dimensiones dados.</span><span class="sxs-lookup"><span data-stu-id="8da42-305">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="8da42-306">Para la integración, Inventory Visibility le permite configurar el *origen de datos del canal externo* y la dimensión de origen en las *dimensiones objetivo* de Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="8da42-306">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="8da42-307">Las dimensiones de destino deben ser una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="8da42-307">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="8da42-308">Dimensiones predeterminadas en visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="8da42-308">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="8da42-309">Dimensiones personalizadas</span><span class="sxs-lookup"><span data-stu-id="8da42-309">Custom dimensions</span></span>

<span data-ttu-id="8da42-310">El propósito de la configuración de dimensiones es estandarizar la integración de múltiples sistemas para la consulta de dimensiones y el evento de publicación con dimensiones.</span><span class="sxs-lookup"><span data-stu-id="8da42-310">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="8da42-311">Indexación</span><span class="sxs-lookup"><span data-stu-id="8da42-311">Indexing</span></span>

<span data-ttu-id="8da42-312">La mayoría de las veces, la consulta de inventario disponible no solo estará en el nivel "total" más alto, sino que es posible que desee ver los resultados agregados según las dimensiones del inventario.</span><span class="sxs-lookup"><span data-stu-id="8da42-312">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="8da42-313">La visibilidad de inventario proporciona flexibilidad al permitirle configurar los índices, que se basan en la dimensión o la combinación de las dimensiones.</span><span class="sxs-lookup"><span data-stu-id="8da42-313">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="8da42-314">Actualmente, solo puede configurar índices hasta un máximo de cinco.</span><span class="sxs-lookup"><span data-stu-id="8da42-314">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="8da42-315">Debe considerar cuidadosamente qué dimensión o combinación de dimensiones utilizará antes de la implementación para asegurarse de que satisfará sus necesidades comerciales.</span><span class="sxs-lookup"><span data-stu-id="8da42-315">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="8da42-316">Por ejemplo, si desea consultar productos de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8da42-316">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="8da42-317">Consultar el producto agregado disponible por dimensiones *Color* y *Talla*.</span><span class="sxs-lookup"><span data-stu-id="8da42-317">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="8da42-318">En algunos casos, solo desea consultar el producto en total.</span><span class="sxs-lookup"><span data-stu-id="8da42-318">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="8da42-319">Tendría dos índices definidos de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8da42-319">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="8da42-320">El corchete vacío se agregará según el ID del producto dentro de la partición.</span><span class="sxs-lookup"><span data-stu-id="8da42-320">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="8da42-321">La indexación define cómo puede agrupar sus resultados en función de la configuración de consulta `groupBy`.</span><span class="sxs-lookup"><span data-stu-id="8da42-321">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="8da42-322">En este caso, si no define valores para `groupBy`, obtendrá totales por `productid`.</span><span class="sxs-lookup"><span data-stu-id="8da42-322">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="8da42-323">De lo contrario, si define `groupBy` como `groupBy=ColorId&groupBy=SizeId`, obtendrá varias líneas devueltas, según las diferentes combinaciones de colores y tamaños en el sistema.</span><span class="sxs-lookup"><span data-stu-id="8da42-323">Otherwise, if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="8da42-324">Puede poner sus criterios de consulta en el cuerpo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="8da42-324">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="8da42-325">Aquí hay una consulta de muestra sobre el producto con combinación de color y tamaño.</span><span class="sxs-lookup"><span data-stu-id="8da42-325">Here is a sample query on the product with color and size combination.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="custom-measurement"></a><span data-ttu-id="8da42-326">Medida personalizada</span><span class="sxs-lookup"><span data-stu-id="8da42-326">Custom measurement</span></span>

<span data-ttu-id="8da42-327">Las cantidades de medición predeterminadas están vinculadas a Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8da42-327">The default measurement quantities are linked to Supply Chain Management.</span></span> <span data-ttu-id="8da42-328">Sin embargo, es posible que desee tener una cantidad que se componga de una combinación de las medidas predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="8da42-328">However, you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="8da42-329">Para hacer esto, puede tener una configuración de cantidades personalizadas, que se agregarán a la salida de las consultas disponibles.</span><span class="sxs-lookup"><span data-stu-id="8da42-329">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="8da42-330">La funcionalidad simplemente le permite definir un conjunto de medidas que se agregarán, y / o un conjunto de medidas que se restarán, a partir de la medida personalizada.</span><span class="sxs-lookup"><span data-stu-id="8da42-330">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="8da42-331">Por ejemplo, con la siguiente condición de consulta, configurará la cantidad de medida personalizada como `MyCustomAvailableforReservation` para ser consumido por el sistema de consumo.</span><span class="sxs-lookup"><span data-stu-id="8da42-331">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]

```



| <span data-ttu-id="8da42-332">Sistema de consumo</span><span class="sxs-lookup"><span data-stu-id="8da42-332">Consumption system</span></span> | <span data-ttu-id="8da42-333">Medidas calculadas</span><span class="sxs-lookup"><span data-stu-id="8da42-333">Calculated measurers</span></span> | <span data-ttu-id="8da42-334">Origen de datos</span><span class="sxs-lookup"><span data-stu-id="8da42-334">Data source</span></span> | <span data-ttu-id="8da42-335">Modificador</span><span class="sxs-lookup"><span data-stu-id="8da42-335">Modifier</span></span> | <span data-ttu-id="8da42-336">Tipo de cálculo del modificador</span><span class="sxs-lookup"><span data-stu-id="8da42-336">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="8da42-337">Adición</span><span class="sxs-lookup"><span data-stu-id="8da42-337">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="8da42-338">Adición</span><span class="sxs-lookup"><span data-stu-id="8da42-338">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="8da42-339">Resta</span><span class="sxs-lookup"><span data-stu-id="8da42-339">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="8da42-340">Adición</span><span class="sxs-lookup"><span data-stu-id="8da42-340">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="8da42-341">Resta</span><span class="sxs-lookup"><span data-stu-id="8da42-341">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="8da42-342">Adición</span><span class="sxs-lookup"><span data-stu-id="8da42-342">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="8da42-343">Adición</span><span class="sxs-lookup"><span data-stu-id="8da42-343">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="8da42-344">Resta</span><span class="sxs-lookup"><span data-stu-id="8da42-344">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="8da42-345">Resta</span><span class="sxs-lookup"><span data-stu-id="8da42-345">Subtraction</span></span> |

<span data-ttu-id="8da42-346">Con eso, la consulta sobre la cantidad de medición personalizada devolverá el siguiente resultado.</span><span class="sxs-lookup"><span data-stu-id="8da42-346">With that, the query on the custom measurement quantity will return the following output.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

<span data-ttu-id="8da42-347">La salida `MyCustomAvailableforReservation` se basa en la configuración de cálculo en las medidas personalizadas como:</span><span class="sxs-lookup"><span data-stu-id="8da42-347">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="8da42-348">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="8da42-348">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="8da42-349">Publicar cambios disponibles</span><span class="sxs-lookup"><span data-stu-id="8da42-349">Posting on-hand changes</span></span>

<span data-ttu-id="8da42-350">La URL exacta en la que se publicará el evento dependerá de su región geográfica.</span><span class="sxs-lookup"><span data-stu-id="8da42-350">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="8da42-351">Tomará la forma:</span><span class="sxs-lookup"><span data-stu-id="8da42-351">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="8da42-352">Cuando se autentica, esta URL se puede utilizar junto con el método HTTP `POST` para enviar eventos de cambio disponibles al servicio.</span><span class="sxs-lookup"><span data-stu-id="8da42-352">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="8da42-353">Se usa un encabezado especial para comunicarse con los servicios de Dynamics 365 a través de solicitudes HTTP, que denota el Id. De entorno de la instancia de Supply Chain Management a la que están vinculados los datos.</span><span class="sxs-lookup"><span data-stu-id="8da42-353">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="8da42-354">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8da42-354">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="8da42-355">Publicación de cambios disponibles ejemplo de consulta 1</span><span class="sxs-lookup"><span data-stu-id="8da42-355">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="8da42-356">Este ejemplo muestra un escenario en el que establecerá la configuración de dimensión en Power Apps.</span><span class="sxs-lookup"><span data-stu-id="8da42-356">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="8da42-357">Utilice la siguiente consulta para configurar la asignación de dimensiones en Power Apps:</span><span class="sxs-lookup"><span data-stu-id="8da42-357">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="8da42-358">Ahora puede especificar `dimensionDataSource` y usar dimensiones personalizadas en sus consultas.</span><span class="sxs-lookup"><span data-stu-id="8da42-358">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="8da42-359">El sistema convertirá automáticamente las dimensiones personalizadas en dimensiones base.</span><span class="sxs-lookup"><span data-stu-id="8da42-359">The system will automatically convert custom dimensions to base dimensions.</span></span>

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensionDataSource": "pos",
    "dimensions": {
        "PosSizeId": "Large",
        "PosColorId": "Red",
        "PosSiteId": "2",
        "PosLocationId": "21"
    }
}
```

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="8da42-360">Publicación de cambios disponibles ejemplo de consulta 2</span><span class="sxs-lookup"><span data-stu-id="8da42-360">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="8da42-361">Este ejemplo muestra un escenario en el que no se establecen asignaciones para la configuración de dimensión en Power Apps, por lo que la publicación también debe usar las dimensiones base.</span><span class="sxs-lookup"><span data-stu-id="8da42-361">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="8da42-362">Todas las dimensiones deben ser dimensiones base cuando el campo `dimensionDataSource` es nulo, vacío o espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="8da42-362">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensions": {
        "SizeId": "Large",
        "ColorId": "Red",
        "SiteId": "2",
        "LocationId": "21"
    }
}
```

#### <a name="json-document-field-properties"></a><span data-ttu-id="8da42-363">Propiedades de campo de documento JSON</span><span class="sxs-lookup"><span data-stu-id="8da42-363">JSON document field properties</span></span>

<span data-ttu-id="8da42-364">Los campos de los ejemplos de consultas JSON proporcionados anteriormente tienen las propiedades enumeradas en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="8da42-364">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="8da42-365">Id. del campo</span><span class="sxs-lookup"><span data-stu-id="8da42-365">Field ID</span></span> | <span data-ttu-id="8da42-366">Descripción</span><span class="sxs-lookup"><span data-stu-id="8da42-366">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="8da42-367">Un ID único para el evento de cambio específico.</span><span class="sxs-lookup"><span data-stu-id="8da42-367">A unique ID for the specific change event.</span></span> <span data-ttu-id="8da42-368">Este ID se utiliza para garantizar que si la comunicación con el servicio falla durante la publicación, volver a enviar el evento no resultará en que el mismo evento se cuente dos veces en el sistema.</span><span class="sxs-lookup"><span data-stu-id="8da42-368">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="8da42-369">El identificador de la organización vinculada al evento.</span><span class="sxs-lookup"><span data-stu-id="8da42-369">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="8da42-370">Esto se asigna a las organizaciones de Supply Chain Management o los ID de área de datos.</span><span class="sxs-lookup"><span data-stu-id="8da42-370">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="8da42-371">El identificador del producto en cuestión.</span><span class="sxs-lookup"><span data-stu-id="8da42-371">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="8da42-372">La cantidad por la que se debe cambiar el producto disponible.</span><span class="sxs-lookup"><span data-stu-id="8da42-372">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="8da42-373">Si, por ejemplo, se añadieran 10 bagels nuevos a un estante, este valor sería 10.</span><span class="sxs-lookup"><span data-stu-id="8da42-373">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="8da42-374">Si luego se sacaran 3 bagels del estante o se vendieran, este valor sería -3.</span><span class="sxs-lookup"><span data-stu-id="8da42-374">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="8da42-375">La fuente de datos de las dimensiones utilizadas en la consulta y el evento de cambio de publicación.</span><span class="sxs-lookup"><span data-stu-id="8da42-375">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="8da42-376">Si especifica la fuente de datos, puede utilizar las dimensiones personalizadas de la fuente de datos especificada.</span><span class="sxs-lookup"><span data-stu-id="8da42-376">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="8da42-377">Con la configuración de dimensión, Inventory Visibility puede asignar las dimensiones personalizadas a las dimensiones predeterminadas generales.</span><span class="sxs-lookup"><span data-stu-id="8da42-377">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="8da42-378">Si no se especifica `dimensionDataSource`, solo puede utilizar las dimensiones predeterminadas generales en sus consultas.</span><span class="sxs-lookup"><span data-stu-id="8da42-378">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="8da42-379">Una bolsa dinámica de pares clave / valor.</span><span class="sxs-lookup"><span data-stu-id="8da42-379">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="8da42-380">Estos se asignarán a algunas de las dimensiones en Supply Chain Management, pero también puede agregar dimensiones personalizadas (como *Origen*) que puede indicar si el evento provenía de Supply Chain Management o de un sistema externo.</span><span class="sxs-lookup"><span data-stu-id="8da42-380">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="8da42-381">Consultando la corriente disponible</span><span class="sxs-lookup"><span data-stu-id="8da42-381">Querying current on-hand</span></span>

<span data-ttu-id="8da42-382">El punto final para consultar el actual disponible tendrá una URL similar:</span><span class="sxs-lookup"><span data-stu-id="8da42-382">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="8da42-383">Se consultará con el método HTTP `POST`.</span><span class="sxs-lookup"><span data-stu-id="8da42-383">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="8da42-384">Ejemplo 1 de consulta actual disponible</span><span class="sxs-lookup"><span data-stu-id="8da42-384">Current on-hand query example 1</span></span>

<span data-ttu-id="8da42-385">Este ejemplo muestra un escenario en el que ya ha completado la configuración de dimensión en Power Apps.</span><span class="sxs-lookup"><span data-stu-id="8da42-385">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="8da42-386">Utilice la siguiente consulta para configurar la asignación de dimensiones en Power Apps:</span><span class="sxs-lookup"><span data-stu-id="8da42-386">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="8da42-387">Ahora puede especificar `dimensionDataSource` y usar dimensiones personalizadas en sus consultas.</span><span class="sxs-lookup"><span data-stu-id="8da42-387">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="8da42-388">El sistema convertirá automáticamente las dimensiones personalizadas en dimensiones base.</span><span class="sxs-lookup"><span data-stu-id="8da42-388">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="8da42-389">Puede especificar `DimensionDataSource` en `filters` y especificar dimensiones personalizadas en `filters` y `groupByValues`.</span><span class="sxs-lookup"><span data-stu-id="8da42-389">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="8da42-390">El sistema convertirá automáticamente las dimensiones personalizadas en dimensiones base.</span><span class="sxs-lookup"><span data-stu-id="8da42-390">The system will automatically convert custom dimensions to base dimensions.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "DimensionDataSource": ["Pos"],
        "PosLocationId": ["21"],
        "PosSiteId": ["2"],
        "PosColorId": ["Red"]
    },
    "groupByValues": [
        "PosSizeId",
        "PosColorId"
    ],
    "returnNegative": true
}
```

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="8da42-391">Ejemplo 2 de consulta actual disponible</span><span class="sxs-lookup"><span data-stu-id="8da42-391">Current on-hand query example 2</span></span>

<span data-ttu-id="8da42-392">Este ejemplo muestra un escenario en el que no se establecen asignaciones para la configuración de dimensión en Power Apps, por lo que la publicación también debe usar las dimensiones base.</span><span class="sxs-lookup"><span data-stu-id="8da42-392">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="8da42-393">Todas las dimensiones deben ser dimensiones base cuando el campo `dimensionDataSource`, bajo `filters`, es nulo, vacío o espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="8da42-393">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="example-return-result"></a><span data-ttu-id="8da42-394">Resultado devuelto de ejemplo</span><span class="sxs-lookup"><span data-stu-id="8da42-394">Example return result</span></span>

<span data-ttu-id="8da42-395">Las consultas que se muestran en los ejemplos anteriores podrían devolver un resultado como este.</span><span class="sxs-lookup"><span data-stu-id="8da42-395">The queries shown in the previous examples could return a result like this.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

<span data-ttu-id="8da42-396">Tenga en cuenta que los campos de cantidades están estructurados como un diccionario de medidas y sus valores asociados.</span><span class="sxs-lookup"><span data-stu-id="8da42-396">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
