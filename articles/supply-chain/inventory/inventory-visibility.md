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
ms.openlocfilehash: d09c7be5de75511b10d7a69d4b8ac12917b0dbe8
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910434"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="9dea7-103">Complemento de visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="9dea7-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9dea7-104">El complemento de visibilidad de inventario es un microservicio independiente y altamente escalable que permite el seguimiento del inventario disponible en tiempo real, lo que proporciona una vista global de la visibilidad del inventario.</span><span class="sxs-lookup"><span data-stu-id="9dea7-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="9dea7-105">Toda la información relacionada con el inventario disponible se exporta al servicio casi en tiempo real mediante la integración de SQL de bajo nivel.</span><span class="sxs-lookup"><span data-stu-id="9dea7-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="9dea7-106">Los sistemas externos acceden al servicio a través de API RESTful para consultar información disponible sobre conjuntos de dimensiones dados, recuperando así una lista de posiciones disponibles disponibles.</span><span class="sxs-lookup"><span data-stu-id="9dea7-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="9dea7-107">Inventory Visibility es un microservicio construido en Microsoft Dataverse, lo que significa que puede ampliarlo creando Power Apps y aplicando Power BI para proporcionar una funcionalidad personalizada para satisfacer los requisitos de su negocio.</span><span class="sxs-lookup"><span data-stu-id="9dea7-107">Inventory Visibility is a microservice built on Microsoft Dataverse, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="9dea7-108">También es posible actualizar el índice para realizar consultas de inventario.</span><span class="sxs-lookup"><span data-stu-id="9dea7-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="9dea7-109">Inventory Visibility ofrece opciones de configuración que le permiten integrarse con varios sistemas de terceros.</span><span class="sxs-lookup"><span data-stu-id="9dea7-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="9dea7-110">Admite la dimensión de inventario estandarizado, la extensibilidad personalizada y las cantidades calculadas configurables estandarizadas.</span><span class="sxs-lookup"><span data-stu-id="9dea7-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="9dea7-111">Este tema describe cómo instalar y configurar el complemento de visibilidad de inventario para Dynamics 365 Supply Chain Management y cómo utilizar su interfaz de programación de aplicaciones (API).</span><span class="sxs-lookup"><span data-stu-id="9dea7-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="9dea7-112">Instalar el complemento de visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="9dea7-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="9dea7-113">Debe instalar el complemento de visibilidad de inventario mediante Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="9dea7-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="9dea7-114">LCS es un portal de colaboración que proporciona un entorno y un conjunto de servicios actualizados periódicamente que le ayudan a gestionar el ciclo de vida de la aplicación de sus aplicaciones de Dynamics 365 Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9dea7-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="9dea7-115">Para obtener más información, consulte [Recursos de Lifecycle Services](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).</span><span class="sxs-lookup"><span data-stu-id="9dea7-115">For more information, see [Lifecycle Services resources](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).</span></span>

### <a name="prerequisites"></a><span data-ttu-id="9dea7-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9dea7-116">Prerequisites</span></span>

<span data-ttu-id="9dea7-117">Para poder instalar el complemento de visibilidad de inventario, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9dea7-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="9dea7-118">Obtenga un proyecto de implementación de LCS con al menos un entorno implementado.</span><span class="sxs-lookup"><span data-stu-id="9dea7-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="9dea7-119">Asegúrese de que los requisitos previos para configurar complementos proporcionados en [Descripción general de los complementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) ha sido completado.</span><span class="sxs-lookup"><span data-stu-id="9dea7-119">Make sure that the prerequisites for setting up add-ins provided in the [Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) have been completed.</span></span> <span data-ttu-id="9dea7-120">La visibilidad de inventario no requiere vinculación de escritura dual.</span><span class="sxs-lookup"><span data-stu-id="9dea7-120">Inventory Visibility doesn't require dual-write linking.</span></span>
- <span data-ttu-id="9dea7-121">Póngase en contacto con el equipo de visibilidad del inventario en [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para obtener los siguientes tres archivos obligatorios:</span><span class="sxs-lookup"><span data-stu-id="9dea7-121">Contact the Inventory Visibility Team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the following three required files:</span></span>
    - `Inventory Visibility Dataverse Solution.zip`
    - `Inventory Visibility Configuration Trigger.zip`
    - <span data-ttu-id="9dea7-122">`Inventory Visibility Integration.zip` (si la versión de Supply Chain Management que está ejecutando es anterior a la versión 10.0.18)</span><span class="sxs-lookup"><span data-stu-id="9dea7-122">`Inventory Visibility Integration.zip` (if the version of Supply Chain Management that you're running is earlier than version 10.0.18)</span></span>
- <span data-ttu-id="9dea7-123">Siga las instrucciones dadas en [Inicio rápido: registre una aplicación con la plataforma de identidad de Microsoft](/azure/active-directory/develop/quickstart-register-app) para registrar una aplicación y agregar un secreto de cliente a AAD bajo su suscripción azure.</span><span class="sxs-lookup"><span data-stu-id="9dea7-123">Follow the instructions given in [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app) to register an application and add a client secret to AAD under your azure subscription.</span></span>
    - [<span data-ttu-id="9dea7-124">Registrar una aplicación</span><span class="sxs-lookup"><span data-stu-id="9dea7-124">Register an application</span></span>](/azure/active-directory/develop/quickstart-register-app)
    - [<span data-ttu-id="9dea7-125">Agregar un secreto de lciente</span><span class="sxs-lookup"><span data-stu-id="9dea7-125">Add a client secret</span></span>](/azure/active-directory/develop/quickstart-register-app#add-a-certificate)
    - <span data-ttu-id="9dea7-126">El **ID de la aplicación (cliente)**, **Secreto del cliente** e **ID de inquilino** se utilizarán en los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="9dea7-126">The **Application(Client) Id**, **Client Secret** and **Tenant ID** will be used in the following steps.</span></span>

> [!NOTE]
> <span data-ttu-id="9dea7-127">Los países y regiones admitidos actualmente incluyen Canadá, Estados Unidos y la Unión Europea (UE).</span><span class="sxs-lookup"><span data-stu-id="9dea7-127">The currently supported countries and regions include Canada, the United States, and the European Union (EU).</span></span>

<span data-ttu-id="9dea7-128">Si tiene alguna pregunta sobre estos requisitos previos, comuníquese con el equipo de productos de visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="9dea7-128">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a><span data-ttu-id="9dea7-129">Configurar Dataverse</span><span class="sxs-lookup"><span data-stu-id="9dea7-129">Set up Dataverse</span></span>

<span data-ttu-id="9dea7-130">Para configurar Dataverse, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9dea7-130">Follow these steps to set up Dataverse.</span></span>

1. <span data-ttu-id="9dea7-131">Agregue un principio de servicio a su inquilino:</span><span class="sxs-lookup"><span data-stu-id="9dea7-131">Add a service principle to your tenant:</span></span>

    1. <span data-ttu-id="9dea7-132">Instale Azure AD PowerShell Module v2 como se describe en [Instalar Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="9dea7-132">Install Azure AD PowerShell Module v2 as described in [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>
    1. <span data-ttu-id="9dea7-133">Ejecute el siguiente comando de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9dea7-133">Run the following PowerShell command.</span></span>

        ```powershell
        Connect-AzureAD # (open a sign in window and sign in as a tenant user)

        New-AzureADServicePrincipal -AppId "3022308a-b9bd-4a18-b8ac-2ddedb2075e1" -DisplayName "d365-scm-inventoryservice"
        ```

1. <span data-ttu-id="9dea7-134">Cree un usuario de la aplicación para la visibilidad del inventario en Dataverse:</span><span class="sxs-lookup"><span data-stu-id="9dea7-134">Create an application user for Inventory Visibility in Dataverse:</span></span>

    1. <span data-ttu-id="9dea7-135">Abra la URL de su entorno de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9dea7-135">Open the URL of your Dataverse environment.</span></span>
    1. <span data-ttu-id="9dea7-136">Ir **Configuración avanzada \> Sistema \> Seguridad \> Usuarios** y cree un usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9dea7-136">Go to **Advanced Setting \> System \> Security \> Users**, and create an application user.</span></span> <span data-ttu-id="9dea7-137">Use el menú de vista para cambiar la vista de página a **Usuarios de la aplicación**.</span><span class="sxs-lookup"><span data-stu-id="9dea7-137">Use the view menu to change the page view to **Application Users**.</span></span>
    1. <span data-ttu-id="9dea7-138">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="9dea7-138">Select **New**.</span></span> <span data-ttu-id="9dea7-139">Establezca el Id. de aplicación en *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span><span class="sxs-lookup"><span data-stu-id="9dea7-139">Set the application ID to *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span></span> <span data-ttu-id="9dea7-140">(El ID del objeto se cargará automáticamente cuando guarde los cambios). Puede personalizar el nombre.</span><span class="sxs-lookup"><span data-stu-id="9dea7-140">(The object ID will automatically be loaded when you save your changes.) You can customize the name.</span></span> <span data-ttu-id="9dea7-141">Por ejemplo, puede cambiarlo a *Visibilidad de inventario*.</span><span class="sxs-lookup"><span data-stu-id="9dea7-141">For example, you can change it to *Inventory Visibility*.</span></span> <span data-ttu-id="9dea7-142">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9dea7-142">When you've finished, select **Save**.</span></span>
    1. <span data-ttu-id="9dea7-143">Seleccione **Asignar rol** y luego seleccione **Administrador de sistema**.</span><span class="sxs-lookup"><span data-stu-id="9dea7-143">Select **Assign Role**, and then select **System Administrator**.</span></span> <span data-ttu-id="9dea7-144">Si hay un rol que se llama **Usuario de Common Data Service**, selecciónelo también.</span><span class="sxs-lookup"><span data-stu-id="9dea7-144">If there is a role that is named **Common Data Service User**, select it too.</span></span>

    <span data-ttu-id="9dea7-145">Para obtener más información, consulte [Crear un usuario de aplicación](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span><span class="sxs-lookup"><span data-stu-id="9dea7-145">For more information, see [Create an application user](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span></span>

1. <span data-ttu-id="9dea7-146">Si el idioma predeterminado de Dataverse no es **inglés**:</span><span class="sxs-lookup"><span data-stu-id="9dea7-146">If the default language of your Dataverse is not **English**:</span></span>

    1. <span data-ttu-id="9dea7-147">Ir **Configuración avanzada \> Administración \> Idiomas**,</span><span class="sxs-lookup"><span data-stu-id="9dea7-147">Go to **Advanced Setting \> Administration \> Languages**,</span></span>
    1. <span data-ttu-id="9dea7-148">Seleccione **Inglés (LanguageCode = 1033)** y seleccione **Solicitar**.</span><span class="sxs-lookup"><span data-stu-id="9dea7-148">Select **English (LanguageCode=1033)** and select **Apply**.</span></span>

1. <span data-ttu-id="9dea7-149">Importe el archivo `Inventory Visibility Dataverse Solution.zip`, que incluye las entidades relacionadas con la configuración de Dataverse y Power Apps:</span><span class="sxs-lookup"><span data-stu-id="9dea7-149">Import the `Inventory Visibility Dataverse Solution.zip` file, which includes Dataverse configuration related entities and Power Apps:</span></span>

    1. <span data-ttu-id="9dea7-150">Vaya a la página **Soluciones**.</span><span class="sxs-lookup"><span data-stu-id="9dea7-150">Go to the **Solutions** page.</span></span>
    1. <span data-ttu-id="9dea7-151">Seleccione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="9dea7-151">Select **Import**.</span></span>

1. <span data-ttu-id="9dea7-152">Importe el flujo de activación de la actualización de la configuración:</span><span class="sxs-lookup"><span data-stu-id="9dea7-152">Import the configuration upgrade trigger flow:</span></span>

    1. <span data-ttu-id="9dea7-153">Vaya a la página de Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="9dea7-153">Go to the Microsoft Flow page.</span></span>
    1. <span data-ttu-id="9dea7-154">Asegúrese de que la conexión que se denomina *Dataverse (heredado)* existe.</span><span class="sxs-lookup"><span data-stu-id="9dea7-154">Make sure that the connection that is named *Dataverse (legacy)* exists.</span></span> <span data-ttu-id="9dea7-155">(Si no existe, créela).</span><span class="sxs-lookup"><span data-stu-id="9dea7-155">(If it doesn't exist, create it.)</span></span>
    1. <span data-ttu-id="9dea7-156">Importe el archivo `Inventory Visibility Configuration Trigger.zip`.</span><span class="sxs-lookup"><span data-stu-id="9dea7-156">Import the `Inventory Visibility Configuration Trigger.zip` file.</span></span> <span data-ttu-id="9dea7-157">Una vez importado, el disparador aparecerá debajo de **Mis flujos**.</span><span class="sxs-lookup"><span data-stu-id="9dea7-157">After it's imported, the trigger will appear under **My flows**.</span></span>
    1. <span data-ttu-id="9dea7-158">Inicialice las siguientes cuatro variables, según la información del entorno:</span><span class="sxs-lookup"><span data-stu-id="9dea7-158">Initialize the following four variables, based on the environment information:</span></span>

        - <span data-ttu-id="9dea7-159">Id. de inquilino de Azure</span><span class="sxs-lookup"><span data-stu-id="9dea7-159">Azure Tenant ID</span></span>
        - <span data-ttu-id="9dea7-160">Id. de cliente de aplicación de Azure</span><span class="sxs-lookup"><span data-stu-id="9dea7-160">Azure Application Client ID</span></span>
        - <span data-ttu-id="9dea7-161">Secreto de cliente de aplicación de Azure</span><span class="sxs-lookup"><span data-stu-id="9dea7-161">Azure Application Client Secret</span></span>
        - <span data-ttu-id="9dea7-162">Punto de conexión de Visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="9dea7-162">Inventory Visibility Endpoint</span></span>

            <span data-ttu-id="9dea7-163">Para obtener más información sobre esta variable, consulte la sección [Configurar la integración de visibilidad de inventario](#setup-inventory-visibility-integration) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="9dea7-163">For more information about this variable, see the [Set up Inventory Visibility integration](#setup-inventory-visibility-integration) section later in this topic.</span></span>

        <span data-ttu-id="9dea7-164">![Desencadenador de configuración](media/configuration-trigger.png "Desencadenador de configuración")</span><span class="sxs-lookup"><span data-stu-id="9dea7-164">![Configuration trigger](media/configuration-trigger.png "Configuration trigger")</span></span>

    1. <span data-ttu-id="9dea7-165">Seleccione **Encender**.</span><span class="sxs-lookup"><span data-stu-id="9dea7-165">Select **Turn on**.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="9dea7-166">Instalar el complemento</span><span class="sxs-lookup"><span data-stu-id="9dea7-166">Install the add-in</span></span>

<span data-ttu-id="9dea7-167">Para instalar el complemento de visibilidad de inventario, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9dea7-167">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="9dea7-168">Inicie sesión en el portal de [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="9dea7-168">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="9dea7-169">En la página de inicio, seleccione el proyecto donde se implementa su entorno.</span><span class="sxs-lookup"><span data-stu-id="9dea7-169">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="9dea7-170">En la página del proyecto, seleccione el entorno donde desea instalar el complemento.</span><span class="sxs-lookup"><span data-stu-id="9dea7-170">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="9dea7-171">En la página del entorno, desplácese hacia abajo hasta que vea la sección **Complementos de entorno** en la sección **Integración de Power Platform**, donde puede encontrar el nombre del entorno Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9dea7-171">On the environment page, scroll down until you see the **Environment add-ins** section in the **Power Platform integration** section, where you can find the Dataverse environment name.</span></span>
1. <span data-ttu-id="9dea7-172">En la sección **Complementos de entorno**, seleccione **Instalar un nuevo complemento**.</span><span class="sxs-lookup"><span data-stu-id="9dea7-172">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>

    <span data-ttu-id="9dea7-173">![Página de entorno en LCS](media/inventory-visibility-environment.png "Página de entorno en LCS")</span><span class="sxs-lookup"><span data-stu-id="9dea7-173">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>

1. <span data-ttu-id="9dea7-174">Seleccione el vínculo **Instalar un nuevo complemento**.</span><span class="sxs-lookup"><span data-stu-id="9dea7-174">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="9dea7-175">Se abre una lista de complementos disponibles.</span><span class="sxs-lookup"><span data-stu-id="9dea7-175">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="9dea7-176">En la lista, seleccione **Visibilidad de inventario**.</span><span class="sxs-lookup"><span data-stu-id="9dea7-176">Select **Inventory Visibility** in the list.</span></span>
1. <span data-ttu-id="9dea7-177">Ingrese valores para los siguientes campos para su entorno:</span><span class="sxs-lookup"><span data-stu-id="9dea7-177">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="9dea7-178">**ID de aplicación de AAD (cliente)**</span><span class="sxs-lookup"><span data-stu-id="9dea7-178">**AAD application (client) ID**</span></span>
    - <span data-ttu-id="9dea7-179">**Id. de suscriptor de AAD**</span><span class="sxs-lookup"><span data-stu-id="9dea7-179">**AAD tenant ID**</span></span>

    <span data-ttu-id="9dea7-180">![Agregar en la página de configuración](media/inventory-visibility-setup.png "Página de configuración del complemento")</span><span class="sxs-lookup"><span data-stu-id="9dea7-180">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="9dea7-181">Acepte los términos y condiciones seleccionando la casilla de verificación **Términos y Condiciones**.</span><span class="sxs-lookup"><span data-stu-id="9dea7-181">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="9dea7-182">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="9dea7-182">Select **Install**.</span></span> <span data-ttu-id="9dea7-183">El estado del complemento se mostrará como **Instalando**.</span><span class="sxs-lookup"><span data-stu-id="9dea7-183">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="9dea7-184">Cuando haya terminado, actualice la página para ver el cambio de estado a **Instalado**.</span><span class="sxs-lookup"><span data-stu-id="9dea7-184">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="uninstall-the-add-in"></a><a name="uninstall-add-in"></a><span data-ttu-id="9dea7-185">Desinstalar el complemento</span><span class="sxs-lookup"><span data-stu-id="9dea7-185">Uninstall the add-in</span></span>

<span data-ttu-id="9dea7-186">Para desinstalar el complemento, seleccione **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="9dea7-186">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="9dea7-187">Cuando actualice LCS, el complemento de visibilidad de inventario se eliminarán.</span><span class="sxs-lookup"><span data-stu-id="9dea7-187">When you refresh LCS, the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="9dea7-188">El proceso de desinstalación elimina el registro del complemento y también inicia un trabajo para limpiar todos los datos comerciales almacenados en el servicio.</span><span class="sxs-lookup"><span data-stu-id="9dea7-188">The uninstall process removes the add-in registration and also starts a job to clean up all the business data that is stored in the service.</span></span>

## <a name="consume-on-hand-inventory-data-from-supply-chain-management"></a><span data-ttu-id="9dea7-189">Consumir datos de inventario disponibles de Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="9dea7-189">Consume on-hand inventory data from Supply Chain Management</span></span>

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a><span data-ttu-id="9dea7-190">Implementar el paquete de integración de visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="9dea7-190">Deploy the Inventory Visibility integration package</span></span>

<span data-ttu-id="9dea7-191">Si está ejecutando Supply Chain Management versión 10.0.17 o anterior, comuníquese con el equipo de soporte a bordo de Inventory Visibility en [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para obtener el archivo del paquete.</span><span class="sxs-lookup"><span data-stu-id="9dea7-191">If you're running Supply Chain Management version 10.0.17 or earlier, contact the Inventory Visibility on-board support team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the package file.</span></span> <span data-ttu-id="9dea7-192">Luego implemente el paquete en LCS.</span><span class="sxs-lookup"><span data-stu-id="9dea7-192">Then deploy the package in LCS.</span></span>

> [!NOTE]
> <span data-ttu-id="9dea7-193">Si se produce un error de discrepancia de versión durante la implementación, debe importar manualmente el proyecto X ++ a su entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="9dea7-193">If a version mismatch error occurs during deployment, you must manually import the X++ project into your development environment.</span></span> <span data-ttu-id="9dea7-194">Luego, cree el paquete implementable en su entorno de desarrollo e impleméntelo en su entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="9dea7-194">Then create the deployable package in your development environment, and deploy it in your production environment.</span></span>
> 
> <span data-ttu-id="9dea7-195">El código se incluye con Supply Chain Management versión 10.0.18.</span><span class="sxs-lookup"><span data-stu-id="9dea7-195">The code is included with Supply Chain Management version 10.0.18.</span></span> <span data-ttu-id="9dea7-196">Si está ejecutando esa versión o una posterior, la implementación no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="9dea7-196">If you're running that version or later, deployment isn't required.</span></span>

<span data-ttu-id="9dea7-197">Asegúrese de que las siguientes funciones estén activadas en su entorno de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9dea7-197">Make sure that the following features are turned on in your Supply Chain Management environment.</span></span> <span data-ttu-id="9dea7-198">(De forma predeterminada, están activadas).</span><span class="sxs-lookup"><span data-stu-id="9dea7-198">(By default, they are turned on.)</span></span>

| <span data-ttu-id="9dea7-199">Descripción de la característica</span><span class="sxs-lookup"><span data-stu-id="9dea7-199">Feature description</span></span> | <span data-ttu-id="9dea7-200">Versión de código</span><span class="sxs-lookup"><span data-stu-id="9dea7-200">Code version</span></span> | <span data-ttu-id="9dea7-201">Alternar clase</span><span class="sxs-lookup"><span data-stu-id="9dea7-201">Toggle class</span></span> |
|---|---|---|
| <span data-ttu-id="9dea7-202">Habilitar o deshabilitar el uso de dimensiones de inventario en la tabla InventSum</span><span class="sxs-lookup"><span data-stu-id="9dea7-202">Enable or disable using inventory dimensions on InventSum table</span></span> | <span data-ttu-id="9dea7-203">10.0.11</span><span class="sxs-lookup"><span data-stu-id="9dea7-203">10.0.11</span></span> | <span data-ttu-id="9dea7-204">InventUseDimOfInventSumToggle</span><span class="sxs-lookup"><span data-stu-id="9dea7-204">InventUseDimOfInventSumToggle</span></span> |
| <span data-ttu-id="9dea7-205">Habilitar o deshabilitar el uso de dimensiones de inventario en la tabla InventSumDelta</span><span class="sxs-lookup"><span data-stu-id="9dea7-205">Enable or disable using inventory dimensions on InventSumDelta table</span></span> | <span data-ttu-id="9dea7-206">10.0.12</span><span class="sxs-lookup"><span data-stu-id="9dea7-206">10.0.12</span></span> | <span data-ttu-id="9dea7-207">InventUseDimOfInventSumDeltaToggle</span><span class="sxs-lookup"><span data-stu-id="9dea7-207">InventUseDimOfInventSumDeltaToggle</span></span> |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a><span data-ttu-id="9dea7-208">Configurar integración de Visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="9dea7-208">Set up Inventory Visibility integration</span></span>

1. <span data-ttu-id="9dea7-209">En Supply Chain Management, abra el espacio de trabajo **[Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** y active la caracterísica **Integración de visibilidad de inventario**.</span><span class="sxs-lookup"><span data-stu-id="9dea7-209">In Supply Chain Management, open the **[Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** workspace, and turn on the **Inventory Visibility Integration** feature.</span></span>
1. <span data-ttu-id="9dea7-210">Ir **Gestión del inventario \> Configurar \> Parámetros de integración de visibilidad de inventario** e ingrese la URL del entorno en el que está ejecutando Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="9dea7-210">Go to **Inventory Management \> Set up \> Inventory Visibility Integration parameters**, and enter the URL of the environment where you're running Inventory Visibility.</span></span>

    <span data-ttu-id="9dea7-211">Busque la región de Azure de su entorno LCS y luego ingrese la URL.</span><span class="sxs-lookup"><span data-stu-id="9dea7-211">Find your LCS environment's Azure region, and then enter the URL.</span></span> <span data-ttu-id="9dea7-212">La URL tiene el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="9dea7-212">The URL has the following form:</span></span>

    `https://inventoryservice.<RegionShortName>-il301.gateway.prod.island.powerapps.com`

    <span data-ttu-id="9dea7-213">Por ejemplo, si se encuentra en Europa, su entorno tendrá una de las siguientes URL:</span><span class="sxs-lookup"><span data-stu-id="9dea7-213">For example, if you're in Europe, your environment will have one of the following URLs:</span></span>

    - `https://inventoryservice.neu-il301.gateway.prod.island.powerapps.com`
    - `https://inventoryservice.weu-il301.gateway.prod.island.powerapps.com`

    <span data-ttu-id="9dea7-214">Tiene a su disposición las siguientes regiones:</span><span class="sxs-lookup"><span data-stu-id="9dea7-214">The following regions are currently available.</span></span>

    | <span data-ttu-id="9dea7-215">Región de Azure</span><span class="sxs-lookup"><span data-stu-id="9dea7-215">Azure region</span></span> | <span data-ttu-id="9dea7-216">Nombre corto de la región</span><span class="sxs-lookup"><span data-stu-id="9dea7-216">Region short name</span></span> |
    |---|---|
    | <span data-ttu-id="9dea7-217">Este de Australia</span><span class="sxs-lookup"><span data-stu-id="9dea7-217">Australia east</span></span> | <span data-ttu-id="9dea7-218">eau</span><span class="sxs-lookup"><span data-stu-id="9dea7-218">eau</span></span> |
    | <span data-ttu-id="9dea7-219">Sudeste de Australia</span><span class="sxs-lookup"><span data-stu-id="9dea7-219">Australia southeast</span></span> | <span data-ttu-id="9dea7-220">seau</span><span class="sxs-lookup"><span data-stu-id="9dea7-220">seau</span></span> |
    | <span data-ttu-id="9dea7-221">Canadá central</span><span class="sxs-lookup"><span data-stu-id="9dea7-221">Canada central</span></span> | <span data-ttu-id="9dea7-222">cca</span><span class="sxs-lookup"><span data-stu-id="9dea7-222">cca</span></span> |
    | <span data-ttu-id="9dea7-223">Este de Canadá</span><span class="sxs-lookup"><span data-stu-id="9dea7-223">Canada east</span></span> | <span data-ttu-id="9dea7-224">eca</span><span class="sxs-lookup"><span data-stu-id="9dea7-224">eca</span></span> |
    | <span data-ttu-id="9dea7-225">Norte de Europa</span><span class="sxs-lookup"><span data-stu-id="9dea7-225">North Europe</span></span> | <span data-ttu-id="9dea7-226">neu</span><span class="sxs-lookup"><span data-stu-id="9dea7-226">neu</span></span> |
    | <span data-ttu-id="9dea7-227">Europa Occidental</span><span class="sxs-lookup"><span data-stu-id="9dea7-227">West Europe</span></span> | <span data-ttu-id="9dea7-228">weu</span><span class="sxs-lookup"><span data-stu-id="9dea7-228">weu</span></span> |
    | <span data-ttu-id="9dea7-229">Este de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="9dea7-229">East US</span></span> | <span data-ttu-id="9dea7-230">eus</span><span class="sxs-lookup"><span data-stu-id="9dea7-230">eus</span></span> |
    | <span data-ttu-id="9dea7-231">Oeste de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="9dea7-231">West US</span></span> | <span data-ttu-id="9dea7-232">wus</span><span class="sxs-lookup"><span data-stu-id="9dea7-232">wus</span></span> |

1. <span data-ttu-id="9dea7-233">Ir **Gestión del inventario \> Periódico \> Integración de visibilidad de inventario** y habilite el trabajo.</span><span class="sxs-lookup"><span data-stu-id="9dea7-233">Go to **Inventory Management \> Periodic \> Inventory Visibility Integration**, and enable the job.</span></span> <span data-ttu-id="9dea7-234">Todos los eventos de cambio de inventario de Supply Chain Management ahora se publicarán en Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="9dea7-234">All inventory change events from Supply Chain Management will now be posted to Inventory Visibility.</span></span>

## <a name="the-inventory-visibility-add-in-public-api"></a><a name="inventory-visibility-public-api"></a><span data-ttu-id="9dea7-235">API pública de complemento de visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="9dea7-235">The Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="9dea7-236">La API de REST pública del complemento de visibilidad de inventario presenta varios puntos finales específicos para integración.</span><span class="sxs-lookup"><span data-stu-id="9dea7-236">The public REST API of the Inventory Visibility Add-in presents several specific endpoints for integration.</span></span> <span data-ttu-id="9dea7-237">Admite tres tipos principales de interacción:</span><span class="sxs-lookup"><span data-stu-id="9dea7-237">It supports three main interaction types:</span></span>

- <span data-ttu-id="9dea7-238">Publicar cambios de inventario disponible en el complemento desde un sistema externo</span><span class="sxs-lookup"><span data-stu-id="9dea7-238">Posting on-hand inventory changes to the add-in from an external system</span></span>
- <span data-ttu-id="9dea7-239">Consultar cantidades actuales disponibles desde un sistema externo</span><span class="sxs-lookup"><span data-stu-id="9dea7-239">Querying current on-hand quantities from an external system</span></span>
- <span data-ttu-id="9dea7-240">Sincronización automática con el inventario disponible de Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="9dea7-240">Automatic synchronization with Supply Chain Management on-hand inventory</span></span>

<span data-ttu-id="9dea7-241">La sincronización automática no forma parte de la API pública.</span><span class="sxs-lookup"><span data-stu-id="9dea7-241">Automatic synchronization isn't part of the public API.</span></span> <span data-ttu-id="9dea7-242">En su lugar, se maneja en segundo plano para entornos en los que el complemento de visibilidad de inventario está habilitado.</span><span class="sxs-lookup"><span data-stu-id="9dea7-242">Instead, it's handled in the background for environments where the Inventory Visibility Add-in is enabled.</span></span>

### <a name="authentication"></a><a name="inventory-visibility-authentication"></a><span data-ttu-id="9dea7-243">Autentificación</span><span class="sxs-lookup"><span data-stu-id="9dea7-243">Authentication</span></span>

<span data-ttu-id="9dea7-244">El token de seguridad de la plataforma se utiliza para llamar al complemento de visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="9dea7-244">The platform security token is used to call the Inventory Visibility Add-in.</span></span> <span data-ttu-id="9dea7-245">Por lo tanto, debe generar un *token de Azure Active Directory (Azure AD)* usando su aploicación de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9dea7-245">Therefore, you must generate an *Azure Active Directory (Azure AD) token* by using your Azure AD application.</span></span> <span data-ttu-id="9dea7-246">A continuación, debe utilizar el token de Azure AD para obtener el *token de acceso* del servicio de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9dea7-246">You must then use the Azure AD token to get the *access token* from the security service.</span></span>

<span data-ttu-id="9dea7-247">Obtenga un token de servicio de seguridad de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="9dea7-247">Get a security service token by doing the following:</span></span>

1. <span data-ttu-id="9dea7-248">Inicie sesión en Azure Portal y utilícelo para encontrar el `clientId` y el `clientSecret` para su aplicación Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9dea7-248">Sign in to Azure portal and use it to find the `clientId` and `clientSecret` for your Supply Chain Management application.</span></span>
1. <span data-ttu-id="9dea7-249">Busque un token Azure Active Directory (`aadToken`) enviando una solicitud HTTP con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="9dea7-249">Fetch an Azure Active Directory token (`aadToken`) by submitting an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="9dea7-250">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span><span class="sxs-lookup"><span data-stu-id="9dea7-250">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span></span>
    - <span data-ttu-id="9dea7-251">**Método** - `GET`</span><span class="sxs-lookup"><span data-stu-id="9dea7-251">**Method** - `GET`</span></span>
    - <span data-ttu-id="9dea7-252">**Contenido del cuerpo (datos del formulario)**:</span><span class="sxs-lookup"><span data-stu-id="9dea7-252">**Body content (form data)**:</span></span>

        | <span data-ttu-id="9dea7-253">key</span><span class="sxs-lookup"><span data-stu-id="9dea7-253">key</span></span> | <span data-ttu-id="9dea7-254">valor</span><span class="sxs-lookup"><span data-stu-id="9dea7-254">value</span></span> |
        | --- | --- |
        | <span data-ttu-id="9dea7-255">client_id</span><span class="sxs-lookup"><span data-stu-id="9dea7-255">client_id</span></span> | <span data-ttu-id="9dea7-256">${aadAppId}</span><span class="sxs-lookup"><span data-stu-id="9dea7-256">${aadAppId}</span></span> |
        | <span data-ttu-id="9dea7-257">client_secret</span><span class="sxs-lookup"><span data-stu-id="9dea7-257">client_secret</span></span> | <span data-ttu-id="9dea7-258">${aadAppSecret}</span><span class="sxs-lookup"><span data-stu-id="9dea7-258">${aadAppSecret}</span></span> |
        | <span data-ttu-id="9dea7-259">grant_type</span><span class="sxs-lookup"><span data-stu-id="9dea7-259">grant_type</span></span> | <span data-ttu-id="9dea7-260">client_credentials</span><span class="sxs-lookup"><span data-stu-id="9dea7-260">client_credentials</span></span> |
        | <span data-ttu-id="9dea7-261">resource</span><span class="sxs-lookup"><span data-stu-id="9dea7-261">resource</span></span> | <span data-ttu-id="9dea7-262">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="9dea7-262">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
1. <span data-ttu-id="9dea7-263">Debería recibir un `aadToken` en respuesta, que se parece al siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9dea7-263">You should receive an `aadToken` in response, which resembles the following example.</span></span>

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

1. <span data-ttu-id="9dea7-264">Formule una solicitud JSON similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="9dea7-264">Formulate a JSON request that resembles the following:</span></span>

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

    <span data-ttu-id="9dea7-265">Donde:</span><span class="sxs-lookup"><span data-stu-id="9dea7-265">Where:</span></span>
    - <span data-ttu-id="9dea7-266">El valor `client_assertion` debe ser el `aadToken` que recibió en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="9dea7-266">The `client_assertion` value must be the `aadToken` you received in the previous step.</span></span>
    - <span data-ttu-id="9dea7-267">El valor `context` debe ser el ID de entorno en el que desea implementar el complemento.</span><span class="sxs-lookup"><span data-stu-id="9dea7-267">The `context` value must be the environment ID where you want to deploy the add-in.</span></span>
    - <span data-ttu-id="9dea7-268">Configure todos los demás valores como se muestra en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9dea7-268">Set all of other values as shown in the example.</span></span>

1. <span data-ttu-id="9dea7-269">Envíe una solicitud HTTP con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="9dea7-269">Submit an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="9dea7-270">**URL** - `https://securityservice.operations365.dynamics.com/token`</span><span class="sxs-lookup"><span data-stu-id="9dea7-270">**URL** - `https://securityservice.operations365.dynamics.com/token`</span></span>
    - <span data-ttu-id="9dea7-271">**Método** - `POST`</span><span class="sxs-lookup"><span data-stu-id="9dea7-271">**Method** - `POST`</span></span>
    - <span data-ttu-id="9dea7-272">**Encabezado HTTP** - Incluya la versión de API (la clave es `Api-Version` y el valor es `1.0`)</span><span class="sxs-lookup"><span data-stu-id="9dea7-272">**HTTP header** - Include the API version (key is `Api-Version` and value is `1.0`)</span></span>
    - <span data-ttu-id="9dea7-273">**Contenido del cuerpo** - Incluya la solicitud JSON que creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="9dea7-273">**Body content** - Include the JSON request that you created in the previous step.</span></span>

1. <span data-ttu-id="9dea7-274">Obtendrá `access_token` como respuesta.</span><span class="sxs-lookup"><span data-stu-id="9dea7-274">You will get an `access_token` in response.</span></span> <span data-ttu-id="9dea7-275">Esto es lo que necesita como token de portador para llamar a la API de visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="9dea7-275">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="9dea7-276">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9dea7-276">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="sample-request"></a><a name="inventory-visibility-sample-request"></a><span data-ttu-id="9dea7-277">Solicitud de muestra</span><span class="sxs-lookup"><span data-stu-id="9dea7-277">Sample Request</span></span>

<span data-ttu-id="9dea7-278">Para su referencia, aquí hay una solicitud http de muestra, puede usar cualquier herramienta o lenguaje de codificación para enviar esta solicitud, como ``Postman``.</span><span class="sxs-lookup"><span data-stu-id="9dea7-278">For your reference, here is a sample http request, you can use any tools or coding language to send this request, such as  ``Postman``.</span></span>

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "quantities": {
        "pos": {
            "inbound": 5
        }  
    },
    "dimensions": {
        "SizeId": "Small",
        "ColorId": "Red",
        "SiteId": "1",
        "LocationId": "11"
    }
}
```

### <a name="configure-the-inventory-visibility-api"></a><a name="inventory-visibility-configuration"></a><span data-ttu-id="9dea7-279">Configurar la API de visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="9dea7-279">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="9dea7-280">Antes de utilizar el servicio, debe completar las configuraciones descritas en las siguientes subsecciones.</span><span class="sxs-lookup"><span data-stu-id="9dea7-280">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="9dea7-281">La configuración puede variar según los detalles de su entorno.</span><span class="sxs-lookup"><span data-stu-id="9dea7-281">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="9dea7-282">Incluye principalmente cuatro partes:</span><span class="sxs-lookup"><span data-stu-id="9dea7-282">It primarily includes four parts:</span></span>

- [<span data-ttu-id="9dea7-283">Partición</span><span class="sxs-lookup"><span data-stu-id="9dea7-283">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="9dea7-284">Configuraciones de dimensiones</span><span class="sxs-lookup"><span data-stu-id="9dea7-284">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="9dea7-285">Indexación</span><span class="sxs-lookup"><span data-stu-id="9dea7-285">Indexing</span></span>](#indexing)
- [<span data-ttu-id="9dea7-286">Medida personalizada</span><span class="sxs-lookup"><span data-stu-id="9dea7-286">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="9dea7-287">Partición</span><span class="sxs-lookup"><span data-stu-id="9dea7-287">Partitioning</span></span>

<span data-ttu-id="9dea7-288">El particionamiento puede influir significativamente en el rendimiento de la API de visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="9dea7-288">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="9dea7-289">Es una buena idea definir un esquema que permita pequeñas agrupaciones de datos y al mismo tiempo permita consultas de datos significativas.</span><span class="sxs-lookup"><span data-stu-id="9dea7-289">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="9dea7-290">`organizationId` (`dataAreaId` en Supply Chain Management) siempre formará parte de la partición y, de forma predeterminada, la Visibilidad de inventario está configurada para particionar por dimensiones como *Sitio + Ubicación*.</span><span class="sxs-lookup"><span data-stu-id="9dea7-290">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="9dea7-291">Esto significa que el servicio siempre debe consultarse con estas dimensiones definidas en los filtros.</span><span class="sxs-lookup"><span data-stu-id="9dea7-291">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="9dea7-292">*Sitio* y *Ubicación* son dos dimensiones predeterminadas generales en Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="9dea7-292">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="9dea7-293">En Supply Chain Management, esas dimensiones se denominan *Sitio* (`InventSiteId`) y *Almacén* (`InventLocationId`)</span><span class="sxs-lookup"><span data-stu-id="9dea7-293">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="9dea7-294">Configuraciones de dimensiones</span><span class="sxs-lookup"><span data-stu-id="9dea7-294">Dimension configurations</span></span>

<span data-ttu-id="9dea7-295">Inventory Visibility proporcionará una lista de dimensiones predeterminadas generales para permitir la integración del sistema de múltiples fuentes.</span><span class="sxs-lookup"><span data-stu-id="9dea7-295">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="9dea7-296">La siguiente tabla enumera las dimensiones de inventario que serán los nombres de dimensión predeterminados en Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="9dea7-296">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="9dea7-297">Tipo de dimensión</span><span class="sxs-lookup"><span data-stu-id="9dea7-297">Dimension type</span></span> | <span data-ttu-id="9dea7-298">Nombre de dimensión</span><span class="sxs-lookup"><span data-stu-id="9dea7-298">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="9dea7-299">Producto</span><span class="sxs-lookup"><span data-stu-id="9dea7-299">Product</span></span> | `ColorId` |
| <span data-ttu-id="9dea7-300">Producto</span><span class="sxs-lookup"><span data-stu-id="9dea7-300">Product</span></span> | `SizeId` |
| <span data-ttu-id="9dea7-301">Producto</span><span class="sxs-lookup"><span data-stu-id="9dea7-301">Product</span></span> | `StyleId` |
| <span data-ttu-id="9dea7-302">Producto</span><span class="sxs-lookup"><span data-stu-id="9dea7-302">Product</span></span> | `ConfigId` |
| <span data-ttu-id="9dea7-303">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="9dea7-303">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="9dea7-304">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="9dea7-304">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="9dea7-305">Ubicación</span><span class="sxs-lookup"><span data-stu-id="9dea7-305">Location</span></span> | `LocationId` |
| <span data-ttu-id="9dea7-306">Ubicación</span><span class="sxs-lookup"><span data-stu-id="9dea7-306">Location</span></span> | `SiteId` |
| <span data-ttu-id="9dea7-307">Estado de inventario</span><span class="sxs-lookup"><span data-stu-id="9dea7-307">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="9dea7-308">Específico del almacén</span><span class="sxs-lookup"><span data-stu-id="9dea7-308">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="9dea7-309">Específico del almacén</span><span class="sxs-lookup"><span data-stu-id="9dea7-309">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="9dea7-310">Específico del almacén</span><span class="sxs-lookup"><span data-stu-id="9dea7-310">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="9dea7-311">El tipo de dimensión enumerado en la tabla anterior es solo para referencia.</span><span class="sxs-lookup"><span data-stu-id="9dea7-311">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="9dea7-312">No es necesario definir el tipo de dimensión en Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="9dea7-312">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="9dea7-313">Si existe una dimensión personalizada y necesita fluir a un valor predeterminado cuando la usa Inventory Visibility, puede configurar el nombre de la **Dimensión personalizada** en Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="9dea7-313">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="9dea7-314">Los sistemas externos acceden a la visibilidad del inventario a través de API RESTful que permiten consultar información disponible sobre conjuntos de dimensiones dados.</span><span class="sxs-lookup"><span data-stu-id="9dea7-314">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="9dea7-315">Para la integración, Inventory Visibility le permite configurar el *origen de datos del canal externo* y la dimensión de origen en las *dimensiones objetivo* de Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="9dea7-315">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="9dea7-316">Las dimensiones de destino deben ser una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="9dea7-316">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="9dea7-317">Dimensiones predeterminadas en visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="9dea7-317">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="9dea7-318">Dimensiones personalizadas</span><span class="sxs-lookup"><span data-stu-id="9dea7-318">Custom dimensions</span></span>

<span data-ttu-id="9dea7-319">El propósito de la configuración de dimensiones es estandarizar la integración de múltiples sistemas para la consulta de dimensiones y el evento de publicación con dimensiones.</span><span class="sxs-lookup"><span data-stu-id="9dea7-319">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="9dea7-320">Indexación</span><span class="sxs-lookup"><span data-stu-id="9dea7-320">Indexing</span></span>

<span data-ttu-id="9dea7-321">La mayoría de las veces, la consulta de inventario disponible no solo estará en el nivel "total" más alto, sino que es posible que desee ver los resultados agregados según las dimensiones del inventario.</span><span class="sxs-lookup"><span data-stu-id="9dea7-321">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="9dea7-322">La visibilidad de inventario proporciona flexibilidad al permitirle configurar los índices, que se basan en la dimensión o la combinación de las dimensiones.</span><span class="sxs-lookup"><span data-stu-id="9dea7-322">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="9dea7-323">Actualmente, solo puede configurar índices hasta un máximo de cinco.</span><span class="sxs-lookup"><span data-stu-id="9dea7-323">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="9dea7-324">Debe considerar cuidadosamente qué dimensión o combinación de dimensiones utilizará antes de la implementación para asegurarse de que satisfará sus necesidades comerciales.</span><span class="sxs-lookup"><span data-stu-id="9dea7-324">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="9dea7-325">Por ejemplo, si desea consultar productos de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="9dea7-325">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="9dea7-326">Consultar el producto agregado disponible por dimensiones *Color* y *Talla*.</span><span class="sxs-lookup"><span data-stu-id="9dea7-326">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="9dea7-327">En algunos casos, solo desea consultar el producto en total.</span><span class="sxs-lookup"><span data-stu-id="9dea7-327">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="9dea7-328">Tendría dos índices definidos de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="9dea7-328">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="9dea7-329">El corchete vacío se agregará según el ID del producto dentro de la partición.</span><span class="sxs-lookup"><span data-stu-id="9dea7-329">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="9dea7-330">La indexación define cómo puede agrupar sus resultados en función de la configuración de consulta `groupBy`.</span><span class="sxs-lookup"><span data-stu-id="9dea7-330">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="9dea7-331">En este caso, si no define valores para `groupBy`, obtendrá totales por `productid`.</span><span class="sxs-lookup"><span data-stu-id="9dea7-331">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="9dea7-332">De lo contrario, si define `groupBy` como `groupBy=ColorId&groupBy=SizeId`, obtendrá varias líneas devueltas, según las diferentes combinaciones de colores y tamaños en el sistema.</span><span class="sxs-lookup"><span data-stu-id="9dea7-332">Otherwise, if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="9dea7-333">Puede poner sus criterios de consulta en el cuerpo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="9dea7-333">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="9dea7-334">Aquí hay una consulta de muestra sobre el producto con combinación de color y tamaño.</span><span class="sxs-lookup"><span data-stu-id="9dea7-334">Here is a sample query on the product with color and size combination.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct1", "MyProduct2"],
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

<span data-ttu-id="9dea7-335">Para el campo `filters`, actualmente solo `ProductId` admite varios valores.</span><span class="sxs-lookup"><span data-stu-id="9dea7-335">For the `filters` field, currently only `ProductId` supports multiple values.</span></span> <span data-ttu-id="9dea7-336">Si `ProductId` es una matriz vacía, se consultarán todos los productos.</span><span class="sxs-lookup"><span data-stu-id="9dea7-336">If the `ProductId` is an empty array, all products will be queried.</span></span>

#### <a name="custom-measurement"></a><span data-ttu-id="9dea7-337">Medida personalizada</span><span class="sxs-lookup"><span data-stu-id="9dea7-337">Custom measurement</span></span>

<span data-ttu-id="9dea7-338">Las cantidades de medición predeterminadas están vinculadas a Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9dea7-338">The default measurement quantities are linked to Supply Chain Management.</span></span> <span data-ttu-id="9dea7-339">Sin embargo, es posible que desee tener una cantidad que se componga de una combinación de las medidas predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="9dea7-339">However, you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="9dea7-340">Para hacer esto, puede tener una configuración de cantidades personalizadas, que se agregarán a la salida de las consultas disponibles.</span><span class="sxs-lookup"><span data-stu-id="9dea7-340">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="9dea7-341">La funcionalidad simplemente le permite definir un conjunto de medidas que se agregarán, y / o un conjunto de medidas que se restarán, a partir de la medida personalizada.</span><span class="sxs-lookup"><span data-stu-id="9dea7-341">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="9dea7-342">Por ejemplo, con la siguiente condición de consulta, configurará la cantidad de medida personalizada como `MyCustomAvailableforReservation` para ser consumido por el sistema de consumo.</span><span class="sxs-lookup"><span data-stu-id="9dea7-342">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

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



| <span data-ttu-id="9dea7-343">Sistema de consumo</span><span class="sxs-lookup"><span data-stu-id="9dea7-343">Consumption system</span></span> | <span data-ttu-id="9dea7-344">Medidas calculadas</span><span class="sxs-lookup"><span data-stu-id="9dea7-344">Calculated measurers</span></span> | <span data-ttu-id="9dea7-345">Origen de datos</span><span class="sxs-lookup"><span data-stu-id="9dea7-345">Data source</span></span> | <span data-ttu-id="9dea7-346">Modificador</span><span class="sxs-lookup"><span data-stu-id="9dea7-346">Modifier</span></span> | <span data-ttu-id="9dea7-347">Tipo de cálculo del modificador</span><span class="sxs-lookup"><span data-stu-id="9dea7-347">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="9dea7-348">Adición</span><span class="sxs-lookup"><span data-stu-id="9dea7-348">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="9dea7-349">Adición</span><span class="sxs-lookup"><span data-stu-id="9dea7-349">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="9dea7-350">Resta</span><span class="sxs-lookup"><span data-stu-id="9dea7-350">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="9dea7-351">Adición</span><span class="sxs-lookup"><span data-stu-id="9dea7-351">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="9dea7-352">Resta</span><span class="sxs-lookup"><span data-stu-id="9dea7-352">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="9dea7-353">Adición</span><span class="sxs-lookup"><span data-stu-id="9dea7-353">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="9dea7-354">Adición</span><span class="sxs-lookup"><span data-stu-id="9dea7-354">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="9dea7-355">Resta</span><span class="sxs-lookup"><span data-stu-id="9dea7-355">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="9dea7-356">Resta</span><span class="sxs-lookup"><span data-stu-id="9dea7-356">Subtraction</span></span> |

<span data-ttu-id="9dea7-357">Con eso, la consulta sobre la cantidad de medición personalizada devolverá el siguiente resultado.</span><span class="sxs-lookup"><span data-stu-id="9dea7-357">With that, the query on the custom measurement quantity will return the following output.</span></span>

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

<span data-ttu-id="9dea7-358">La salida `MyCustomAvailableforReservation` se basa en la configuración de cálculo en las medidas personalizadas como:</span><span class="sxs-lookup"><span data-stu-id="9dea7-358">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="9dea7-359">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="9dea7-359">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="9dea7-360">Publicar cambios disponibles</span><span class="sxs-lookup"><span data-stu-id="9dea7-360">Posting on-hand changes</span></span>

<span data-ttu-id="9dea7-361">La URL exacta en la que se publicará el evento dependerá de su región geográfica.</span><span class="sxs-lookup"><span data-stu-id="9dea7-361">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="9dea7-362">Tomará la forma:</span><span class="sxs-lookup"><span data-stu-id="9dea7-362">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="9dea7-363">Cuando se autentica, esta URL se puede utilizar junto con el método HTTP `POST` para enviar eventos de cambio disponibles al servicio.</span><span class="sxs-lookup"><span data-stu-id="9dea7-363">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="9dea7-364">Se usa un encabezado especial para comunicarse con los servicios de Dynamics 365 a través de solicitudes HTTP, que denota el Id. De entorno de la instancia de Supply Chain Management a la que están vinculados los datos.</span><span class="sxs-lookup"><span data-stu-id="9dea7-364">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="9dea7-365">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9dea7-365">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="9dea7-366">Publicación de cambios disponibles ejemplo de consulta 1</span><span class="sxs-lookup"><span data-stu-id="9dea7-366">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="9dea7-367">Este ejemplo muestra un escenario en el que establecerá la configuración de dimensión en Power Apps.</span><span class="sxs-lookup"><span data-stu-id="9dea7-367">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="9dea7-368">Utilice la siguiente consulta para configurar la asignación de dimensiones en Power Apps:</span><span class="sxs-lookup"><span data-stu-id="9dea7-368">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="9dea7-369">Ahora puede especificar `dimensionDataSource` y usar dimensiones personalizadas en sus consultas.</span><span class="sxs-lookup"><span data-stu-id="9dea7-369">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="9dea7-370">El sistema convertirá automáticamente las dimensiones personalizadas en dimensiones base.</span><span class="sxs-lookup"><span data-stu-id="9dea7-370">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="9dea7-371">Publicación de cambios disponibles ejemplo de consulta 2</span><span class="sxs-lookup"><span data-stu-id="9dea7-371">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="9dea7-372">Este ejemplo muestra un escenario en el que no se establecen asignaciones para la configuración de dimensión en Power Apps, por lo que la publicación también debe usar las dimensiones base.</span><span class="sxs-lookup"><span data-stu-id="9dea7-372">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="9dea7-373">Todas las dimensiones deben ser dimensiones base cuando el campo `dimensionDataSource` es nulo, vacío o espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="9dea7-373">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

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

#### <a name="json-document-field-properties"></a><span data-ttu-id="9dea7-374">Propiedades de campo de documento JSON</span><span class="sxs-lookup"><span data-stu-id="9dea7-374">JSON document field properties</span></span>

<span data-ttu-id="9dea7-375">Los campos de los ejemplos de consultas JSON proporcionados anteriormente tienen las propiedades enumeradas en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="9dea7-375">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="9dea7-376">Id. del campo</span><span class="sxs-lookup"><span data-stu-id="9dea7-376">Field ID</span></span> | <span data-ttu-id="9dea7-377">Descripción</span><span class="sxs-lookup"><span data-stu-id="9dea7-377">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="9dea7-378">Un ID único para el evento de cambio específico.</span><span class="sxs-lookup"><span data-stu-id="9dea7-378">A unique ID for the specific change event.</span></span> <span data-ttu-id="9dea7-379">Este ID se utiliza para garantizar que si la comunicación con el servicio falla durante la publicación, volver a enviar el evento no resultará en que el mismo evento se cuente dos veces en el sistema.</span><span class="sxs-lookup"><span data-stu-id="9dea7-379">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="9dea7-380">El identificador de la organización vinculada al evento.</span><span class="sxs-lookup"><span data-stu-id="9dea7-380">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="9dea7-381">Esto se asigna a las organizaciones de Supply Chain Management o los ID de área de datos.</span><span class="sxs-lookup"><span data-stu-id="9dea7-381">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="9dea7-382">El identificador del producto en cuestión.</span><span class="sxs-lookup"><span data-stu-id="9dea7-382">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="9dea7-383">La cantidad por la que se debe cambiar el producto disponible.</span><span class="sxs-lookup"><span data-stu-id="9dea7-383">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="9dea7-384">Si, por ejemplo, se añadieran 10 bagels nuevos a un estante, este valor sería 10.</span><span class="sxs-lookup"><span data-stu-id="9dea7-384">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="9dea7-385">Si luego se sacaran 3 bagels del estante o se vendieran, este valor sería -3.</span><span class="sxs-lookup"><span data-stu-id="9dea7-385">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="9dea7-386">La fuente de datos de las dimensiones utilizadas en la consulta y el evento de cambio de publicación.</span><span class="sxs-lookup"><span data-stu-id="9dea7-386">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="9dea7-387">Si especifica la fuente de datos, puede utilizar las dimensiones personalizadas de la fuente de datos especificada.</span><span class="sxs-lookup"><span data-stu-id="9dea7-387">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="9dea7-388">Con la configuración de dimensión, Inventory Visibility puede asignar las dimensiones personalizadas a las dimensiones predeterminadas generales.</span><span class="sxs-lookup"><span data-stu-id="9dea7-388">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="9dea7-389">Si no se especifica `dimensionDataSource`, solo puede utilizar las dimensiones predeterminadas generales en sus consultas.</span><span class="sxs-lookup"><span data-stu-id="9dea7-389">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="9dea7-390">Una bolsa dinámica de pares clave / valor.</span><span class="sxs-lookup"><span data-stu-id="9dea7-390">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="9dea7-391">Estos se asignarán a algunas de las dimensiones en Supply Chain Management, pero también puede agregar dimensiones personalizadas (como *Origen*) que puede indicar si el evento provenía de Supply Chain Management o de un sistema externo.</span><span class="sxs-lookup"><span data-stu-id="9dea7-391">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="9dea7-392">Consultando la corriente disponible</span><span class="sxs-lookup"><span data-stu-id="9dea7-392">Querying current on-hand</span></span>

<span data-ttu-id="9dea7-393">El punto final para consultar el actual disponible tendrá una URL similar:</span><span class="sxs-lookup"><span data-stu-id="9dea7-393">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="9dea7-394">Se consultará con el método HTTP `POST`.</span><span class="sxs-lookup"><span data-stu-id="9dea7-394">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="9dea7-395">Ejemplo 1 de consulta actual disponible</span><span class="sxs-lookup"><span data-stu-id="9dea7-395">Current on-hand query example 1</span></span>

<span data-ttu-id="9dea7-396">Este ejemplo muestra un escenario en el que ya ha completado la configuración de dimensión en Power Apps.</span><span class="sxs-lookup"><span data-stu-id="9dea7-396">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="9dea7-397">Utilice la siguiente consulta para configurar la asignación de dimensiones en Power Apps:</span><span class="sxs-lookup"><span data-stu-id="9dea7-397">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="9dea7-398">Ahora puede especificar `dimensionDataSource` y usar dimensiones personalizadas en sus consultas.</span><span class="sxs-lookup"><span data-stu-id="9dea7-398">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="9dea7-399">El sistema convertirá automáticamente las dimensiones personalizadas en dimensiones base.</span><span class="sxs-lookup"><span data-stu-id="9dea7-399">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="9dea7-400">Puede especificar `DimensionDataSource` en `filters` y especificar dimensiones personalizadas en `filters` y `groupByValues`.</span><span class="sxs-lookup"><span data-stu-id="9dea7-400">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="9dea7-401">El sistema convertirá automáticamente las dimensiones personalizadas en dimensiones base.</span><span class="sxs-lookup"><span data-stu-id="9dea7-401">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="9dea7-402">Ejemplo 2 de consulta actual disponible</span><span class="sxs-lookup"><span data-stu-id="9dea7-402">Current on-hand query example 2</span></span>

<span data-ttu-id="9dea7-403">Este ejemplo muestra un escenario en el que no se establecen asignaciones para la configuración de dimensión en Power Apps, por lo que la publicación también debe usar las dimensiones base.</span><span class="sxs-lookup"><span data-stu-id="9dea7-403">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="9dea7-404">Todas las dimensiones deben ser dimensiones base cuando el campo `dimensionDataSource`, bajo `filters`, es nulo, vacío o espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="9dea7-404">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

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

#### <a name="example-return-result"></a><span data-ttu-id="9dea7-405">Resultado devuelto de ejemplo</span><span class="sxs-lookup"><span data-stu-id="9dea7-405">Example return result</span></span>

<span data-ttu-id="9dea7-406">Las consultas que se muestran en los ejemplos anteriores podrían devolver un resultado como este.</span><span class="sxs-lookup"><span data-stu-id="9dea7-406">The queries shown in the previous examples could return a result like this.</span></span>

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

<span data-ttu-id="9dea7-407">Tenga en cuenta que los campos de cantidades están estructurados como un diccionario de medidas y sus valores asociados.</span><span class="sxs-lookup"><span data-stu-id="9dea7-407">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]