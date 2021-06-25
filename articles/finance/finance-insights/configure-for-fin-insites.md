---
title: Configuración de Finance Insights - hasta la versión 10.0.19
description: Este tema explica los pasos de configuración que permitirán que su sistema utilice las capacidades que están disponibles en Finance Insights hasta la versión 10.0.19.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 6ad06bb6d041fc060b3a99538f6d4d0af333180f
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186429"
---
# <a name="configuration-for-finance-insights-preview"></a><span data-ttu-id="6778b-103">Configuración de Finance Insights (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="6778b-103">Configuration for Finance insights (preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> <span data-ttu-id="6778b-104">Los siguientes procedimientos para configurar Finance Insights son válidos para Microsoft Dynamics 365 Finance hasta la versión 10.0.19.</span><span class="sxs-lookup"><span data-stu-id="6778b-104">The following procedures for setting up Finance insights are valid for Microsoft Dynamics 365 Finance versions up to 10.0.19.</span></span> <span data-ttu-id="6778b-105">Para configurar Finance insights en la versión 10.0.20 y posteriores, consulte [Configuración de Finance Insights (versión preliminar): versiones 10.0.20 y posteriores](configure-for-fin-insites-PubPrvw.md).</span><span class="sxs-lookup"><span data-stu-id="6778b-105">To set up Finance insights on version 10.0.20 and later, see [Configuration for Finance Insights (preview) - versions 10.0.20 and beyond](configure-for-fin-insites-PubPrvw.md).</span></span>

<span data-ttu-id="6778b-106">Finance Insights combina la funcionalidad de Microsoft Dynamics 365 Finance con Microsoft Dataverse, Azure y AI Builder para proporcionar potentes herramientas de pronóstico para su organización.</span><span class="sxs-lookup"><span data-stu-id="6778b-106">Finance insights combines functionality from Microsoft Dynamics 365 Finance with Microsoft Dataverse, Azure, and AI Builder to provide powerful forecasting tools for your organization.</span></span> <span data-ttu-id="6778b-107">Este tema explica los pasos de configuración que permitirán que su sistema utilice las capacidades que están disponibles en Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="6778b-107">This topic explains the configuration steps that will enable your system to use the capabilities that are available in Finance insights.</span></span>

## <a name="deploy-dynamics-365-finance"></a><span data-ttu-id="6778b-108">Implementar Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="6778b-108">Deploy Dynamics 365 Finance</span></span>

<span data-ttu-id="6778b-109">implemente los entornos siguiendo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6778b-109">Deploy the environments by following these steps.</span></span>

1. <span data-ttu-id="6778b-110">En Microsoft Dynamics Lifecycle Services (LCS), cree o actualice un entorno de Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="6778b-110">In Microsoft Dynamics Lifecycle Services (LCS), create or update a Dynamics 365 Finance environment.</span></span> <span data-ttu-id="6778b-111">El entorno requiere la versión de la aplicación 10.0.11/Actualización de plataforma 35 o posterior.</span><span class="sxs-lookup"><span data-stu-id="6778b-111">The environment requires app version 10.0.11/Platform update 35 or later.</span></span>
2. <span data-ttu-id="6778b-112">El entorno debe ser un entorno de alta disponibilidad (HA) en espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="6778b-112">The environment must be a high-availability (HA) environment in Sandbox.</span></span> <span data-ttu-id="6778b-113">(Este tipo de entorno también se conoce como entorno de nivel 2). Para obtener más información, consulte [Planificación de entornos](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="6778b-113">(This type of environment is also known as a Tier-2 environment.) For more information, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
3. <span data-ttu-id="6778b-114">Si está configurando Finance Insights en un entorno de espacio aislado, es posible que deba copiar los datos de producción en ese entorno para que funcionen las predicciones.</span><span class="sxs-lookup"><span data-stu-id="6778b-114">If you are configuring Finance insights in a Sandbox environment, you might need to copy production data to that environment for predictions to work.</span></span> <span data-ttu-id="6778b-115">El modelo de predicción utiliza varios años de datos para generar predicciones.</span><span class="sxs-lookup"><span data-stu-id="6778b-115">The prediction model uses multiple years of data to build predictions.</span></span> <span data-ttu-id="6778b-116">Los datos de la demostración de Contoso no contienen suficientes datos históricos para entrenar adecuadamente el modelo de predicción.</span><span class="sxs-lookup"><span data-stu-id="6778b-116">The Contoso demo data doesn’t contain enough historical data to train the prediction model adequately.</span></span> 

## <a name="configure-dataverse"></a><span data-ttu-id="6778b-117">Configurar Dataverse</span><span class="sxs-lookup"><span data-stu-id="6778b-117">Configure Dataverse</span></span>

<span data-ttu-id="6778b-118">Utilice los siguientes pasos para configurar Dataverse para Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="6778b-118">Use the following steps to configure Dataverse for Finance insights.</span></span>

1. <span data-ttu-id="6778b-119">Abra la página del entorno en LCS y verifique que la sección **Integración de Power Platform** ya está configurada.</span><span class="sxs-lookup"><span data-stu-id="6778b-119">Open the environment page in LCS and verify that the **Power Platform Integration** section is already setup.</span></span>
    1. <span data-ttu-id="6778b-120">Si ya está configurada, el nombre del entorno de Dataverse vinculado al entorno de Dynamics 365 Finance debe enumerarse.</span><span class="sxs-lookup"><span data-stu-id="6778b-120">If it is already set up, the Dataverse environment name linked to the Dynamics 365 Finance Environment should be listed.</span></span> <span data-ttu-id="6778b-121">Copie el nombre del entorno de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="6778b-121">Copy the Dataverse environment name.</span></span>
    2. <span data-ttu-id="6778b-122">Si no está configurado, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6778b-122">If it is not set up, follow these steps:</span></span>
        1. <span data-ttu-id="6778b-123">Seleccione e botón **Configuración** en la sección de integración de Power Platform.</span><span class="sxs-lookup"><span data-stu-id="6778b-123">Select the **Setup** button in the Power Platform Integration section.</span></span> <span data-ttu-id="6778b-124">Puede llevar hasta una hora configurar el entorno.</span><span class="sxs-lookup"><span data-stu-id="6778b-124">It may take up to an hour for the environment to be set up.</span></span>
        2. <span data-ttu-id="6778b-125">Si ya está configurado correctamente el entorno de Dataverse, el nombre del entorno de Dataverse vinculado al entorno de Dynamics 365 Finance debe enumerarse.</span><span class="sxs-lookup"><span data-stu-id="6778b-125">If the Dataverse environment is successfully set up, the Dataverse environment name linked to the Dynamics 365 Finance Environment should be listed.</span></span> <span data-ttu-id="6778b-126">Copie el nombre del entorno de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="6778b-126">Copy the Dataverse environment name.</span></span>
> [!NOTE]
> <span data-ttu-id="6778b-127">Después de completar la configuración del entorno, **NO** seleccione el botón **Vincular a CDS para aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="6778b-127">After completing the environment set up, **DO NOT** select the **Link to CDS for Apps** button.</span></span> <span data-ttu-id="6778b-128">Esto no es necesario para Finance Insights y deshabilitará la capacidad de completar los complementos de entorno requeridos en LCS.</span><span class="sxs-lookup"><span data-stu-id="6778b-128">This is not needed for Finance Insights and will disable the ability to complete the required Environment Add-ins in LCS.</span></span>

2. <span data-ttu-id="6778b-129">Abra el [Centro de administración de Power Platform](https://admin.powerplatform.microsoft.com/) y siga estos pasos para crear un nuevo entorno de Dataverse en el mismo inquilino de Active Directory:</span><span class="sxs-lookup"><span data-stu-id="6778b-129">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com/), and follow these steps to create a new Dataverse environment in the same Active Directory tenant:</span></span>

    1. <span data-ttu-id="6778b-130">Abra la página **Entornos**.</span><span class="sxs-lookup"><span data-stu-id="6778b-130">Open the **Environments** page.</span></span>

        <span data-ttu-id="6778b-131">[![Página de entornos](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span><span class="sxs-lookup"><span data-stu-id="6778b-131">[![Environments page](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span></span>

    2. <span data-ttu-id="6778b-132">Seleccione el entorno de Dataverse creado anteriormente y luego seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="6778b-132">Select the Dataverse environment created above and then select **Settings**.</span></span>
    3. <span data-ttu-id="6778b-133">Seleccione **Recursos \> Todas las configuraciones heredadas**.</span><span class="sxs-lookup"><span data-stu-id="6778b-133">Select **Resources \> All Legacy Settings**.</span></span>
    4. <span data-ttu-id="6778b-134">En la barra de navegación superior, seleccione **Configuración** y luego seleccione **Personalizaciones**.</span><span class="sxs-lookup"><span data-stu-id="6778b-134">On the top navigation bar, select **Settings**, and then select **Customizations**.</span></span>
    5. <span data-ttu-id="6778b-135">Seleccione **Recursos para desarrolladores**.</span><span class="sxs-lookup"><span data-stu-id="6778b-135">Select **Developer Resources**.</span></span>
    6. <span data-ttu-id="6778b-136">Copie el valor del **Id. de organización de Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="6778b-136">Copy the **Dataverse organization ID** value.</span></span>
    7. <span data-ttu-id="6778b-137">En la barra de direcciones del navegador, anote la URL de la organización de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="6778b-137">In the browser's address bar, make a note of the URL for the Dataverse organization.</span></span> <span data-ttu-id="6778b-138">Por ejemplo, la URL puede ser `https://org42b2b3d3.crm.dynamics.com`.</span><span class="sxs-lookup"><span data-stu-id="6778b-138">For example, the URL might be `https://org42b2b3d3.crm.dynamics.com`.</span></span>

3. <span data-ttu-id="6778b-139">Si planea usar la función Previsiones de flujo de efectivo o Previsiones de presupuesto, siga estos pasos para actualizar el límite de anotaciones para su organización a al menos 50 megabytes (MB):</span><span class="sxs-lookup"><span data-stu-id="6778b-139">If you plan to use the Cash flow forecasts or Budget forecasts feature, follow these steps to update the annotation limit for your organization to at least 50 megabytes (MB):</span></span>

    1. <span data-ttu-id="6778b-140">Abra el [portal de Power Apps](https://make.powerapps.com).</span><span class="sxs-lookup"><span data-stu-id="6778b-140">Open the [Power Apps portal](https://make.powerapps.com).</span></span>
    2. <span data-ttu-id="6778b-141">Seleccione el entorno que acaba de crear y luego seleccione **Configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="6778b-141">Select the environment that you just created, and then select **Advanced settings**.</span></span>
    3. <span data-ttu-id="6778b-142">Seleccione **Configuración \> Configuración de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="6778b-142">Select **Settings \> Email Configuration**.</span></span>
    4. <span data-ttu-id="6778b-143">Cambie el valor del campo **Tamaño máximo de archivo** a **51.200**.</span><span class="sxs-lookup"><span data-stu-id="6778b-143">Change the value of the **Maximum file size** field to **51,200**.</span></span> <span data-ttu-id="6778b-144">(El valor se expresa en kilobytes \[KB\]).</span><span class="sxs-lookup"><span data-stu-id="6778b-144">(The value is expressed in kilobytes \[KB\].)</span></span>
    5. <span data-ttu-id="6778b-145">Seleccione **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="6778b-145">Select **OK** to save your changes.</span></span>

## <a name="configure-the-azure-setup"></a><span data-ttu-id="6778b-146">Configurar los ajustes de Azure</span><span class="sxs-lookup"><span data-stu-id="6778b-146">Configure the Azure setup</span></span>

### <a name="enter-the-dataverse-directory-id-and-the-users-azure-ad-object-id"></a><span data-ttu-id="6778b-147">Introduzca el id. de directorio de Dataverse y el id. de objeto de Azure AD de usuario</span><span class="sxs-lookup"><span data-stu-id="6778b-147">Enter the Dataverse directory ID and the user's Azure AD object ID</span></span>

1. <span data-ttu-id="6778b-148">Especifique el id. de directorio de Dataverse:</span><span class="sxs-lookup"><span data-stu-id="6778b-148">Enter the Dataverse directory ID:</span></span>

    1. <span data-ttu-id="6778b-149">Abra el [Azure Portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="6778b-149">Open the [Azure portal](https://portal.azure.com).</span></span>
    2. <span data-ttu-id="6778b-150">Inicie sesión con el id. de usuario que se utilizó para crear el entorno de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="6778b-150">Sign in by using the user ID that was used to create the Dataverse environment.</span></span>
    3. <span data-ttu-id="6778b-151">Ir a **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="6778b-151">Go to **Azure Active Directory**.</span></span>
    4. <span data-ttu-id="6778b-152">Copie el valor del **Id. de inquilino**.</span><span class="sxs-lookup"><span data-stu-id="6778b-152">Copy the **Tenant ID** value.</span></span>

2. <span data-ttu-id="6778b-153">Especifique el id. de objeto de Azure Active Directory (Azure AD) del usuario.</span><span class="sxs-lookup"><span data-stu-id="6778b-153">Enter the user's Azure Active Directory (Azure AD) object ID:</span></span>

    1. <span data-ttu-id="6778b-154">En el [Portal de Azure](https://portal.azure.com), vaya a **Usuarios** y busque al usuario por dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6778b-154">In the [Azure portal](https://portal.azure.com), go to **Users**, and search for the user by email address.</span></span>
    2. <span data-ttu-id="6778b-155">Seleccione el nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="6778b-155">Select the user's name.</span></span>
    3. <span data-ttu-id="6778b-156">Copie el valor del **Id. de objeto**.</span><span class="sxs-lookup"><span data-stu-id="6778b-156">Copy the **Object ID** value.</span></span>

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a><span data-ttu-id="6778b-157">Use Azure Cloud Shell para configurar los recursos de Data Lake de Finance Insights</span><span class="sxs-lookup"><span data-stu-id="6778b-157">Use Azure Cloud Shell to set up Finance insights Data Lake resources</span></span>

# <a name="use-a-windows-powershell-script"></a>[<span data-ttu-id="6778b-158">Utilizar un script de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6778b-158">Use a Windows PowerShell script</span></span>](#tab/use-a-powershell-script)

<span data-ttu-id="6778b-159">Se ha proporcionado un script de Windows PowerShell para que pueda configurar fácilmente los recursos de Azure que se describen en [Configurar la exportación a Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="6778b-159">A Windows PowerShell script has been provided, so that you can easily set up the Azure resources that are described in [Configure export to Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span></span> <span data-ttu-id="6778b-160">Si prefiere realizar la configuración manual, omita este procedimiento y continúe con el procedimiento de la sección [Configuración manual](#manual-setup).</span><span class="sxs-lookup"><span data-stu-id="6778b-160">If you prefer to do manual setup, skip this procedure, and continue with the procedure in the [Manual setup](#manual-setup) section.</span></span>

> [!NOTE]
> <span data-ttu-id="6778b-161">Siga los pasos que se describen a continuación para ejecutar el script de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6778b-161">Follow the steps below to run the PowerShell script.</span></span> <span data-ttu-id="6778b-162">Es posible que la opción "Probarlo" de la CLI de Azure o la ejecución del script en su PC no funcionen.</span><span class="sxs-lookup"><span data-stu-id="6778b-162">The Azure CLI "Try it" option, or running the script on your PC may not work.</span></span>

<span data-ttu-id="6778b-163">Siga estos pasos para configurar Azure mediante el script de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6778b-163">Follow these steps to configure Azure by using the Windows PowerShell script.</span></span> <span data-ttu-id="6778b-164">Debe tener derechos para crear un grupo de recursos de Azure, recursos de Azure y una aplicación de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6778b-164">You must have rights to create an Azure resource group, Azure resources, and an Azure AD application.</span></span> <span data-ttu-id="6778b-165">Para obtener información sobre los permisos necesarios, consulte [Comprobar los permisos de Azure AD](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span><span class="sxs-lookup"><span data-stu-id="6778b-165">For information about the required permissions, see [Check Azure AD permissions](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span></span>

1. <span data-ttu-id="6778b-166">En [Azure Portal](https://portal.azure.com), vaya a su suscripción de Azure de destino.</span><span class="sxs-lookup"><span data-stu-id="6778b-166">In the [Azure portal](https://portal.azure.com), go to your target Azure subscription.</span></span> <span data-ttu-id="6778b-167">Seleccione el botón **Cloud Shell** a la derecha del campo **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="6778b-167">Select the **Cloud Shell** button to the right of the **Search** field.</span></span>
2. <span data-ttu-id="6778b-168">Seleccione **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="6778b-168">Select **PowerShell**.</span></span>
3. <span data-ttu-id="6778b-169">Cree almacenamiento, si se le solicita que lo haga.</span><span class="sxs-lookup"><span data-stu-id="6778b-169">Create storage if you're prompted to do so.</span></span>
4. <span data-ttu-id="6778b-170">Vaya a la pestaña **CLI de Azure** y seleccione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="6778b-170">Go to the **Azure CLI** tab and select **Copy**.</span></span>  
5. <span data-ttu-id="6778b-171">Abra el Bloc de notas y pegue el script de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6778b-171">Open Notepad and paste the PowerShell script.</span></span> <span data-ttu-id="6778b-172">Guarde el archivo como ConfigureDataLake.ps1.</span><span class="sxs-lookup"><span data-stu-id="6778b-172">Save the file as ConfigureDataLake.ps1.</span></span>
6. <span data-ttu-id="6778b-173">Suba el script de Windows PowerShell a la sesión usando la opción de menú para cargar en Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="6778b-173">Upload the Windows PowerShell script to the session using the menu option for upload in Cloud Shell.</span></span>
7. <span data-ttu-id="6778b-174">Ejecute el script .\ConfigureDataLake.ps1.</span><span class="sxs-lookup"><span data-stu-id="6778b-174">Run the script .\ConfigureDataLake.ps1.</span></span>
8. <span data-ttu-id="6778b-175">Siga las instrucciones para ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="6778b-175">Follow the prompts to run the script.</span></span>
9. <span data-ttu-id="6778b-176">Utilice la información de la salida del script para instalar el complemento **Exportar a Data Lake** en LCS.</span><span class="sxs-lookup"><span data-stu-id="6778b-176">Use the information from the script output to install the **Export to Data Lake** add-in in LCS.</span></span>
10. <span data-ttu-id="6778b-177">Utilice la información de la salida del script para habilitar el almacén de entidades en la página **Conexiones de datos** de Finance (**Administración del sistema \> Parámetros del sistema \> Conexiones de datos**).</span><span class="sxs-lookup"><span data-stu-id="6778b-177">Use the information from the script output to enable the entity store on the **Data connections** page in Finance (**System administration \> System parameters \> Data connections**).</span></span>

### <a name="manual-setup"></a><span data-ttu-id="6778b-178">Configuración manual</span><span class="sxs-lookup"><span data-stu-id="6778b-178">Manual setup</span></span>

#### <a name="add-applications-to-the-azure-ad-tenant"></a><span data-ttu-id="6778b-179">Agregar aplicaciones al inquilino de Azure AD</span><span class="sxs-lookup"><span data-stu-id="6778b-179">Add applications to the Azure AD tenant</span></span>

1. <span data-ttu-id="6778b-180">En [Azure Portal](https://portal.azure.com), vaya a **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="6778b-180">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**.</span></span>
2. <span data-ttu-id="6778b-181">Seleccione **Gestionar \> Aplicaciones empresariales**.</span><span class="sxs-lookup"><span data-stu-id="6778b-181">Select **Manage \> Enterprise applications**.</span></span>
3. <span data-ttu-id="6778b-182">Busque las siguientes aplicaciones por id. de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6778b-182">Search for the following applications by app ID.</span></span>

    | <span data-ttu-id="6778b-183">Solicitud</span><span class="sxs-lookup"><span data-stu-id="6778b-183">Application</span></span>                              | <span data-ttu-id="6778b-184">Id. de aplicación</span><span class="sxs-lookup"><span data-stu-id="6778b-184">App ID</span></span>                               |
    |------------------------------------------|--------------------------------------|
    | <span data-ttu-id="6778b-185">Microservicios de Microsoft Dynamics ERP</span><span class="sxs-lookup"><span data-stu-id="6778b-185">Microsoft Dynamics ERP Microservices</span></span>     | <span data-ttu-id="6778b-186">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="6778b-186">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
    | <span data-ttu-id="6778b-187">CDS de microservicios de Microsoft Dynamics ERP</span><span class="sxs-lookup"><span data-stu-id="6778b-187">Microsoft Dynamics ERP Microservices CDS</span></span> | <span data-ttu-id="6778b-188">703e2651-d3fc-48f5-942c-74274233dba8</span><span class="sxs-lookup"><span data-stu-id="6778b-188">703e2651-d3fc-48f5-942c-74274233dba8</span></span> |
    | <span data-ttu-id="6778b-189">Servicio de autorización de AI Builder</span><span class="sxs-lookup"><span data-stu-id="6778b-189">AI Builder Authorization Service</span></span>         | <span data-ttu-id="6778b-190">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span><span class="sxs-lookup"><span data-stu-id="6778b-190">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span></span> |

<span data-ttu-id="6778b-191">Si no puede encontrar ninguna de las aplicaciones anteriores, intente los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="6778b-191">If you can't find any of the preceding applications, try the following steps.</span></span>

1. <span data-ttu-id="6778b-192">En su máquina local, seleccione el menú **Inicio** y busque **powershell**.</span><span class="sxs-lookup"><span data-stu-id="6778b-192">On your local machine, select the **Start** menu, and search for **powershell**.</span></span>
2. <span data-ttu-id="6778b-193">Seleccione y mantenga pulsado (o haga clic derecho) en **Windows PowerShell** y luego seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="6778b-193">Select and hold (or right-click) **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="6778b-194">Ejecute el siguiente comando para instalar el módulo **AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="6778b-194">Run the following command to install the **AzureAD** module.</span></span>

    `Install-Module -Name AzureAD`

4. <span data-ttu-id="6778b-195">Si se requiere un proveedor NuGet para continuar, seleccione **Y** para instalarlo.</span><span class="sxs-lookup"><span data-stu-id="6778b-195">If a NuGet provider is required to continue, select **Y** to install it.</span></span>
5. <span data-ttu-id="6778b-196">Si aparece el mensaje "Repositorio no confiable", seleccione **Y** continuar.</span><span class="sxs-lookup"><span data-stu-id="6778b-196">If an "Untrusted repository" message appears, select **Y** to continue.</span></span>
6. <span data-ttu-id="6778b-197">Para cada aplicación que deba agregarse, ejecute los siguientes comandos para agregar la aplicación a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6778b-197">For each application that must be added, run the following commands to add the application to Azure AD.</span></span> <span data-ttu-id="6778b-198">Cuando se le solicite, inicie sesión como administrador de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6778b-198">When you're prompted, sign in as the Azure AD administrator.</span></span>

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a><span data-ttu-id="6778b-199">Crear recursos de Azure</span><span class="sxs-lookup"><span data-stu-id="6778b-199">Create Azure resources</span></span>

> [!NOTE]
> <span data-ttu-id="6778b-200">Asegúrese de crear los siguientes recursos en la misma instancia de Azure AD que el entorno de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="6778b-200">Make sure that you create the following resources in the same Azure AD instance as the Dataverse environment.</span></span> <span data-ttu-id="6778b-201">No puede usar recursos de una instancia de Azure AD diferente.</span><span class="sxs-lookup"><span data-stu-id="6778b-201">You can't use resources from a different Azure AD instance.</span></span>

1. <span data-ttu-id="6778b-202">Cree una nueva cuenta de almacenamiento:</span><span class="sxs-lookup"><span data-stu-id="6778b-202">Create a new storage account:</span></span>

    1. <span data-ttu-id="6778b-203">En [Azure Portal](https://portal.azure.com), cree una cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="6778b-203">In the [Azure portal](https://portal.azure.com), create a storage account.</span></span>
    2. <span data-ttu-id="6778b-204">En el cuadro de diálogo **Crear cuenta de almacenamiento**, establezca los siguientes campo:</span><span class="sxs-lookup"><span data-stu-id="6778b-204">In the **Create storage account** dialog box, set the following fields:</span></span>

        - <span data-ttu-id="6778b-205">**Ubicación**: seleccione el centro de datos donde se encuentra su entorno.</span><span class="sxs-lookup"><span data-stu-id="6778b-205">**Location** – Select the data center where your environment is located.</span></span>
        - <span data-ttu-id="6778b-206">**Rendimiento**: es recomendable seleccionar **Estándar**.</span><span class="sxs-lookup"><span data-stu-id="6778b-206">**Performance** – We recommend that you select **Standard**.</span></span>
        - <span data-ttu-id="6778b-207">**Tipo de cuenta**: debe elegir **StorageV2**.</span><span class="sxs-lookup"><span data-stu-id="6778b-207">**Account kind** – You must select **StorageV2**.</span></span>

    3. <span data-ttu-id="6778b-208">En el cuadro de diálogo **Opciones avanzadas**, para la opción **Data Lake Storage Gen2**, seleccione **Habilitar** en la característica **Espacios de nombres jerárquicos**.</span><span class="sxs-lookup"><span data-stu-id="6778b-208">In the **Advanced options** dialog box, for the **Data Lake storage Gen2** option, select **Enable** under the **Hierarchical namespaces** feature.</span></span> <span data-ttu-id="6778b-209">Si desactiva esta característica, no puede emplear datos que las aplicaciones de Finance and Operations escriben utilizando servicios como flujos de datos de Power BI.</span><span class="sxs-lookup"><span data-stu-id="6778b-209">If you disable this feature, you can't consume data that Finance and Operations apps write by using services such as Power BI data flows.</span></span>
    4. <span data-ttu-id="6778b-210">Seleccione **Revisar y crear**.</span><span class="sxs-lookup"><span data-stu-id="6778b-210">Select **Review and create**.</span></span> <span data-ttu-id="6778b-211">Cuando se complete la implementación, el nuevo recurso se mostrará en Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="6778b-211">When the deployment is completed, the new resource will be shown in the Azure portal.</span></span>
    5. <span data-ttu-id="6778b-212">Vaya a la cuenta de almacenamiento que creó.</span><span class="sxs-lookup"><span data-stu-id="6778b-212">Go to the storage account that you created.</span></span>
    6. <span data-ttu-id="6778b-213">En el menú izquierdo, seleccione **Claves de acceso**.</span><span class="sxs-lookup"><span data-stu-id="6778b-213">On the left menu, select **Access keys**.</span></span>
    7. <span data-ttu-id="6778b-214">Copie y guarde la cadena de conexión para **Key1** o **Key2**.</span><span class="sxs-lookup"><span data-stu-id="6778b-214">Copy and save the connection string for either **Key1** or **Key2**.</span></span>
    8. <span data-ttu-id="6778b-215">Copie y guarde el nombre de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="6778b-215">Copy and save the storage account name.</span></span>

2. <span data-ttu-id="6778b-216">Cree un nuevo almacén de claves:</span><span class="sxs-lookup"><span data-stu-id="6778b-216">Create a new key vault:</span></span>

    1. <span data-ttu-id="6778b-217">En [Azure Portal](https://portal.azure.com), cree un almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="6778b-217">In the [Azure portal](https://portal.azure.com), create a key vault.</span></span>
    2. <span data-ttu-id="6778b-218">En el cuadro de diálogo **Crear almacén de claves**, en el campo **Ubicación**, seleccione el centro de datos donde se encuentra su entorno.</span><span class="sxs-lookup"><span data-stu-id="6778b-218">In the **Create key vault** dialog box, in the **Location** field, select the data center where your environment is located.</span></span>
    3. <span data-ttu-id="6778b-219">Una vez creado el almacén de claves, selecciónelo en la lista y luego seleccione **Secretos**.</span><span class="sxs-lookup"><span data-stu-id="6778b-219">After key vault is created, select it in the list, and then select **Secrets**.</span></span>
    4. <span data-ttu-id="6778b-220">Seleccione **Generar/Importar**.</span><span class="sxs-lookup"><span data-stu-id="6778b-220">Select **Generate/Import**.</span></span>
    5. <span data-ttu-id="6778b-221">En el cuadro de diálogo **Crear un secreto**, en el campo **Opciones de carga**, seleccione **Manual**.</span><span class="sxs-lookup"><span data-stu-id="6778b-221">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
    6. <span data-ttu-id="6778b-222">Introduzca un nombre para el secreto.</span><span class="sxs-lookup"><span data-stu-id="6778b-222">Enter a name for the secret.</span></span> <span data-ttu-id="6778b-223">Anote el nombre, porque tendrá que proporcionarlo más tarde.</span><span class="sxs-lookup"><span data-stu-id="6778b-223">Make a note of the name, because you will have to provide it later.</span></span>
    7. <span data-ttu-id="6778b-224">En el campo **Valor**, introduzca la cadena de conexión que obtuvo de la cuenta de almacenamiento en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="6778b-224">In the **Value** field, enter the connection string that you obtained from the storage account in the previous procedure.</span></span>
    8. <span data-ttu-id="6778b-225">Seleccione **Habilitar** y, a continuación, seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="6778b-225">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="6778b-226">El secreto se crea y se agrega a Key Vault.</span><span class="sxs-lookup"><span data-stu-id="6778b-226">The secret is created and added to Key Vault.</span></span>
    9. <span data-ttu-id="6778b-227">Vaya a la **Descripción general de Key Vault** y anote el nombre DNS.</span><span class="sxs-lookup"><span data-stu-id="6778b-227">Go to the **Key Vault Overview**, and make a note of the DNS name.</span></span>

3. <span data-ttu-id="6778b-228">Cree y registre una aplicación de Azure AD:</span><span class="sxs-lookup"><span data-stu-id="6778b-228">Create and register an Azure AD application:</span></span>

    1. <span data-ttu-id="6778b-229">En [Azure Portal](https://portal.azure.com), vaya a **Azure Active Directory** y luego seleccione **Registros de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="6778b-229">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and then select **App registrations**.</span></span>
    2. <span data-ttu-id="6778b-230">Seleccione **Registro de nueva aplicación** y configure los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="6778b-230">Select **New application registration**, and set the following fields:</span></span>

        - <span data-ttu-id="6778b-231">**Nombre**: especifique el nombre de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6778b-231">**Name** – Enter the name of the app.</span></span>
        - <span data-ttu-id="6778b-232">**Tipo de aplicacion**: seleccione **API web**.</span><span class="sxs-lookup"><span data-stu-id="6778b-232">**Application type** – Select **Web API**.</span></span>
        - <span data-ttu-id="6778b-233">**Redirigir la configuración de URI**: introduzca la URL de su instancia de Dynamics 365, como `https://yourdynamicsinstance.dynamics.com/auth`.</span><span class="sxs-lookup"><span data-stu-id="6778b-233">**Redirect URI setup** – Enter the URL for your Dynamics 365 instance, such as, `https://yourdynamicsinstance.dynamics.com/auth`.</span></span>

    3. <span data-ttu-id="6778b-234">Vaya a la aplicación que acaba de crear, copie y guarde su valor de **Id. de la aplicación (cliente)**.</span><span class="sxs-lookup"><span data-stu-id="6778b-234">Go to the app that you just created, and copy and save its **Application (client) ID** value.</span></span> <span data-ttu-id="6778b-235">Tendrá que proporcionar este valor más adelante, cuando configure el almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="6778b-235">You will have to provide this value later, when you set up the key vault.</span></span>
    4. <span data-ttu-id="6778b-236">Vaya a **Permisos de API** y siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6778b-236">Go to **API permissions**, and follow these steps:</span></span>

        1. <span data-ttu-id="6778b-237">Seleccione **Agregar un permiso**.</span><span class="sxs-lookup"><span data-stu-id="6778b-237">Select **Add a permission**.</span></span>
        2. <span data-ttu-id="6778b-238">Seleccione **Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="6778b-238">Select **Azure Key vault**.</span></span>
        3. <span data-ttu-id="6778b-239">Después de seleccionar los permisos delegados, seleccione **usuario\_interpretación**.</span><span class="sxs-lookup"><span data-stu-id="6778b-239">After you select delegated permissions, select **user\_impersonation**.</span></span>
        4. <span data-ttu-id="6778b-240">Seleccione **Agregar permisos**.</span><span class="sxs-lookup"><span data-stu-id="6778b-240">Select **Add permissions**.</span></span>

    5. <span data-ttu-id="6778b-241">En el menú de la aplicación, seleccione **Certificados\&secretos** y luego siga estos pasos para crear secretos de Key Vault:</span><span class="sxs-lookup"><span data-stu-id="6778b-241">On the menu for the app, select **Certificates \& secrets**, and then follow these steps to create Key Vault secrets:</span></span>

        1. <span data-ttu-id="6778b-242">Seleccione **Nuevo secreto de cliente**.</span><span class="sxs-lookup"><span data-stu-id="6778b-242">Select **New client secret**.</span></span>
        2. <span data-ttu-id="6778b-243">En el campo **Descripción de clave**, escriba un nombre.</span><span class="sxs-lookup"><span data-stu-id="6778b-243">In the **Key Description** field, enter a name.</span></span>
        3. <span data-ttu-id="6778b-244">Seleccione una duración y luego seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6778b-244">Select a duration, and then select **Add**.</span></span> <span data-ttu-id="6778b-245">Se genera un secreto en el campo **Valor**.</span><span class="sxs-lookup"><span data-stu-id="6778b-245">A secret is generated in the **Value** field.</span></span>
        4. <span data-ttu-id="6778b-246">Copie y guarde el valor secreto.</span><span class="sxs-lookup"><span data-stu-id="6778b-246">Copy and save the secret value.</span></span>

4. <span data-ttu-id="6778b-247">Cree secretos de Key Vault:</span><span class="sxs-lookup"><span data-stu-id="6778b-247">Create Key Vault secrets:</span></span>

    1. <span data-ttu-id="6778b-248">Vaya al almacén de claves que creó anteriormente y seleccione **Secretos**.</span><span class="sxs-lookup"><span data-stu-id="6778b-248">Go to the key vault that you created earlier, and select **Secrets**.</span></span>
    2. <span data-ttu-id="6778b-249">Para cada nombre secreto de la siguiente tabla, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6778b-249">For each secret name in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="6778b-250">Seleccione **Generar/Importar**.</span><span class="sxs-lookup"><span data-stu-id="6778b-250">Select **Generate/Import**.</span></span>
        2. <span data-ttu-id="6778b-251">En el cuadro de diálogo **Crear un secreto**, en el campo **Opciones de carga**, seleccione **Manual**.</span><span class="sxs-lookup"><span data-stu-id="6778b-251">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
        3. <span data-ttu-id="6778b-252">Cree el nombre secreto y el valor desde la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="6778b-252">Create the secret name and value from the following table.</span></span>
        4. <span data-ttu-id="6778b-253">Seleccione **Habilitar** y, a continuación, seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="6778b-253">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="6778b-254">El secreto se crea y se agrega a Key Vault.</span><span class="sxs-lookup"><span data-stu-id="6778b-254">The secret is created and added to Key Vault.</span></span>

        | <span data-ttu-id="6778b-255">Nombre secreto</span><span class="sxs-lookup"><span data-stu-id="6778b-255">Secret name</span></span>                       | <span data-ttu-id="6778b-256">Valor secreto</span><span class="sxs-lookup"><span data-stu-id="6778b-256">Secret value</span></span>                                                                                |
        |-----------------------------------|---------------------------------------------------------------------------------------------|
        | <span data-ttu-id="6778b-257">app-id</span><span class="sxs-lookup"><span data-stu-id="6778b-257">app-id</span></span>                            | <span data-ttu-id="6778b-258">El id. de la aplicación que creó anteriormente</span><span class="sxs-lookup"><span data-stu-id="6778b-258">The app ID of the application that you created earlier</span></span>                                      |
        | <span data-ttu-id="6778b-259">app-secret</span><span class="sxs-lookup"><span data-stu-id="6778b-259">app-secret</span></span>                        | <span data-ttu-id="6778b-260">El secreto de cliente que guardó anteriormente</span><span class="sxs-lookup"><span data-stu-id="6778b-260">The client secret that you saved earlier</span></span>                                                    |
        | <span data-ttu-id="6778b-261">storage-account-name</span><span class="sxs-lookup"><span data-stu-id="6778b-261">storage-account-name</span></span>              | <span data-ttu-id="6778b-262">El nombre de la cuenta de almacenamiento que creó anteriormente, como **storageaccount1**</span><span class="sxs-lookup"><span data-stu-id="6778b-262">The name of the storage account that you created earlier, such as **storageaccount1**</span></span>       |
        | <span data-ttu-id="6778b-263">storage-account-connection-string</span><span class="sxs-lookup"><span data-stu-id="6778b-263">storage-account-connection-string</span></span> | <span data-ttu-id="6778b-264">La cadena de conexión que copió de la página **Claves de acceso** de la cuenta de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="6778b-264">The connection string that you copied from the **Access keys** page for the storage account</span></span> |

5. <span data-ttu-id="6778b-265">Autorice a la aplicación a acceder al almacén de claves:</span><span class="sxs-lookup"><span data-stu-id="6778b-265">Authorize the application to access the key vault:</span></span>

    1. <span data-ttu-id="6778b-266">En [Azure Portal](https://portal.azure.com), abra el almacén de claves que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6778b-266">In the [Azure portal](https://portal.azure.com), open the key vault that you created earlier.</span></span>
    2. <span data-ttu-id="6778b-267">Seleccione las políticas de acceso.</span><span class="sxs-lookup"><span data-stu-id="6778b-267">Select the access policies.</span></span>
    3. <span data-ttu-id="6778b-268">Para cada aplicación de la siguiente tabla, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6778b-268">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="6778b-269">Seleccione **Agregar política de acceso** para crear una directiva de acceso.</span><span class="sxs-lookup"><span data-stu-id="6778b-269">Select **Add Access Policy** to create an access policy.</span></span>
        2. <span data-ttu-id="6778b-270">En el campo **Permisos secretos**, seleccione los permisos en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="6778b-270">In the **Secret permissions** field, select the permissions from the following table.</span></span>
        3. <span data-ttu-id="6778b-271">En el campo **Seleccionar principal**, busque el nombre para mostrar de la aplicación en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="6778b-271">In the **Select principal** field, search for the application display name from the following table.</span></span>
        4. <span data-ttu-id="6778b-272">Seleccione **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="6778b-272">Select **Select**.</span></span>
        5. <span data-ttu-id="6778b-273">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6778b-273">Select **Add**.</span></span>
        6. <span data-ttu-id="6778b-274">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6778b-274">Select **Save**.</span></span>

        | <span data-ttu-id="6778b-275">Solicitud</span><span class="sxs-lookup"><span data-stu-id="6778b-275">Application</span></span>                                              | <span data-ttu-id="6778b-276">Permisos</span><span class="sxs-lookup"><span data-stu-id="6778b-276">Permissions</span></span> |
        |----------------------------------------------------------|-------------|
        | <span data-ttu-id="6778b-277">El nombre para mostrar de la nueva aplicación que ha creado</span><span class="sxs-lookup"><span data-stu-id="6778b-277">The display name of the new application that you created</span></span> | <span data-ttu-id="6778b-278">Obtener, lista</span><span class="sxs-lookup"><span data-stu-id="6778b-278">Get, List</span></span>   |
        | <span data-ttu-id="6778b-279">**Microservicios de Microsoft Dynamics ERP**</span><span class="sxs-lookup"><span data-stu-id="6778b-279">**Microsoft Dynamics ERP Microservices**</span></span>                 | <span data-ttu-id="6778b-280">Obtener, lista</span><span class="sxs-lookup"><span data-stu-id="6778b-280">Get, List</span></span>   |

6. <span data-ttu-id="6778b-281">Asignar roles para acceder a la cuenta de almacenamiento:</span><span class="sxs-lookup"><span data-stu-id="6778b-281">Assign roles to access the storage account:</span></span>

    1. <span data-ttu-id="6778b-282">En [Azure Portal](https://portal.azure.com), abra la cuenta de almacenamiento que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6778b-282">In the [Azure portal](https://portal.azure.com), open the storage account that you created earlier.</span></span>
    2. <span data-ttu-id="6778b-283">Seleccione **Control de acceso (IAM)** y luego seleccione **Asignaciones de roles**.</span><span class="sxs-lookup"><span data-stu-id="6778b-283">Select **Access Control (IAM)**, and then select **Role Assignments**.</span></span>
    3. <span data-ttu-id="6778b-284">Seleccione **Agregar, agregar asignación de roles**.</span><span class="sxs-lookup"><span data-stu-id="6778b-284">Select **Add, Add Role Assignment**.</span></span>
    4. <span data-ttu-id="6778b-285">Para cada aplicación de la siguiente tabla, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6778b-285">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="6778b-286">Seleccione el rol en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="6778b-286">Select the role from the following table.</span></span>
        2. <span data-ttu-id="6778b-287">Deje el campo **Asignar acceso a** establecido en **Entidad de servicio, grupo o usuario de Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="6778b-287">Leave the **Assign access to** field set to **Azure AD user, group, or service principal**.</span></span>
        3. <span data-ttu-id="6778b-288">En el campo **Seleccionar**, introduzca la aplicación desde la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="6778b-288">In the **Select** field, enter the application from the following table.</span></span>
        4. <span data-ttu-id="6778b-289">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6778b-289">Select **Save**.</span></span>

        | <span data-ttu-id="6778b-290">Solicitud</span><span class="sxs-lookup"><span data-stu-id="6778b-290">Application</span></span>                                              | <span data-ttu-id="6778b-291">Función</span><span class="sxs-lookup"><span data-stu-id="6778b-291">Role</span></span>                        |
        |----------------------------------------------------------|-----------------------------|
        | <span data-ttu-id="6778b-292">El nombre para mostrar de la nueva aplicación que ha creado</span><span class="sxs-lookup"><span data-stu-id="6778b-292">The display name of the new application that you created</span></span> | <span data-ttu-id="6778b-293">Propietario</span><span class="sxs-lookup"><span data-stu-id="6778b-293">Owner</span></span>                       |
        | <span data-ttu-id="6778b-294">El nombre para mostrar de la nueva aplicación que ha creado</span><span class="sxs-lookup"><span data-stu-id="6778b-294">The display name of the new application that you created</span></span> | <span data-ttu-id="6778b-295">Contribuyente</span><span class="sxs-lookup"><span data-stu-id="6778b-295">Contributor</span></span>                 |
        | <span data-ttu-id="6778b-296">El nombre para mostrar de la nueva aplicación que ha creado</span><span class="sxs-lookup"><span data-stu-id="6778b-296">The display name of the new application that you created</span></span> | <span data-ttu-id="6778b-297">Colaborador de la cuenta de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="6778b-297">Storage Account Contributor</span></span> |
        | <span data-ttu-id="6778b-298">El nombre para mostrar de la nueva aplicación que ha creado</span><span class="sxs-lookup"><span data-stu-id="6778b-298">The display name of the new application that you created</span></span> | <span data-ttu-id="6778b-299">Propietario de datos de Storage Blob</span><span class="sxs-lookup"><span data-stu-id="6778b-299">Storage Blob Data Owner</span></span>     |
        | <span data-ttu-id="6778b-300">**Servicio de autorización de AI Builder**</span><span class="sxs-lookup"><span data-stu-id="6778b-300">**AI Builder Authorization Service**</span></span>                     | <span data-ttu-id="6778b-301">Lector de datos de Storage Blob</span><span class="sxs-lookup"><span data-stu-id="6778b-301">Storage Blob Data Reader</span></span>    |

# <a name="azure-cli"></a>[<span data-ttu-id="6778b-302">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="6778b-302">Azure CLI</span></span>](#tab/azure-azure-cli)

```
function New-FinanceDataLakeAzureResources {
    Assert-ScriptSetup

    $ClientAppName = 'Finance Data Lake Application'
    $DefaultSecretExpiryInYear = 1
    $MicrosoftDynamicsERPMicroservicesAppId = '0cdb527f-a8d1-4bf8-9436-b352c68682b2'
    $MicrosoftDynamicsERPMicroservicesCDSAppId = '703e2651-d3fc-48f5-942c-74274233dba8'
    $AIBuilderAuthorizationServiceAppId = 'ad40333e-9910-4b61-b281-e3aeeb8c3ef3'
    $KeyVaultServicePrincipalAppId = 'cfa8b339-82a2-471a-a3c9-0fc0be7a4093'
    $GraphServicePrincipalAppId = '00000003-0000-0000-c000-000000000000'

    Import-Module AzureAD.Standard.Preview
    $connectAzureADParameters = @{ 'Identity' = $true; 'TenantId' = $env:ACC_TID }
    $azContext = AzureAD.Standard.Preview\Connect-AzureAD @connectAzureADParameters
    $userContext = ConvertFrom-Json ((az ad signed-in-user show) -join '')
    $user = Get-AzureADUser -Filter ("UserPrincipalName eq '" + $userContext.UserPrincipalName + "'")

    Set-AzureSubscription
    
    $resourceGroup = $null
    $ResourceGroupName = 'D365FinanceInsightsDataLake'
    $ResourceGroupNameSuffix = ''
    $FullResourceGroupName = ''
    Write-Output ("The default Azure Resource Group name is '{0}'" -f $ResourceGroupName)
    while (-not ($resourceGroup)) {
        $ResourceGroupNameSuffix = (Read-Host -Prompt "Enter optional Azure Resource Group name suffix: (leave blank for no suffix)")
        if ([string]::IsNullOrWhitespace($ResourceGroupNameSuffix))
        {
            $FullResourceGroupName = $ResourceGroupName
        }
        else
        {
            if ($ResourceGroupNameSuffix -notmatch "^[A-Za-z0-9]+$") {
                Write-Warning "The Azure Resource Group name suffix can only include alphanumeric characters."
                continue
            }

            if ($ResourceGroupNameSuffix.Length -gt 60) {
                Write-Warning "The Azure Resource Group name suffix cannot be longer than 60 characters."
                continue
            }

            $FullResourceGroupName = $ResourceGroupName + $ResourceGroupNameSuffix
        }
        
        $resourceGroup = Get-AzResourceGroup -Name $FullResourceGroupName -ErrorAction SilentlyContinue

        if (-not ($resourceGroup)) {
            Write-Output ("Your new Azure Resource Group name is '{0}'" -f $FullResourceGroupName)
            $resourceLocation = ''
            $azResourceLocations = (Get-AzLocation | Select-Object Location).Location
            while ([string]::IsNullOrWhitespace($resourceLocation) -or (-not ($resourceLocation -in $azResourceLocations))) {
                $resourceLocation = (Read-Host -Prompt "Enter the location in which to create the Azure Resource Group: ('help' to see values)")
                if ($resourceLocation -eq 'help') {
                    Write-Output ("List of available regions is '{0}'" -f ($azResourceLocations -join ','))
                }
                elseif ([string]::IsNullOrWhitespace($resourceLocation) -or (-not ($resourceLocation -in $azResourceLocations)))
                {
                    Write-Warning ("The provided location is not available for resource group. List of available regions is '{0}'" -f ($azResourceLocations -join ','))
                }
            }
            $resourceGroup = New-AzResourceGroup -Name $FullResourceGroupName -Location $resourceLocation
            Write-Output ("Created Azure Resource Group '{0}'" -f $resourceGroup.ResourceGroupName)
        }
        else {
            Write-Output ("Found Azure Resource Group '{0}'" -f ($resourceGroup.ResourceGroupName))
        }
    }

    Write-Output '================================================================================='
    $MicrosoftDynamicsERPMicroservicesAppObjectId = Create-ADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesAppId
    Create-ADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesCDSAppId | Out-Null
    $aibuilderAuthorizationServiceObjectId = Create-ADServicePrincipal -AppId $AIBuilderAuthorizationServiceAppId
    Write-Output ('=================================================================================')

    $clientAppSPN = Get-AzureADServicePrincipal -Filter ("DisplayName eq '" + $ClientAppName + "'")
    if (-not ($clientAppSPN)) {
        $keyVaultPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $KeyVaultServicePrincipalAppId + "'")
        if (-not $keyVaultPrincipal)
        {
            New-AzureADServicePrincipal -AppId $KeyVaultServicePrincipalAppId | Format-Table -AutoSize
            Write-Output "Added Key Vault principal to AAD"
            $keyVaultPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $KeyVaultServicePrincipalAppId + "'")
        }
        $keyVaultAccess = New-Object -TypeName "Microsoft.Open.AzureAD.Model.RequiredResourceAccess"
        $keyVaultAccess.ResourceAppId = $keyVaultPrincipal.AppId
        $keyVaultAccess.ResourceAccess = (New-Object -TypeName "microsoft.open.azuread.model.resourceAccess" -ArgumentList $keyVaultPrincipal.Oauth2Permissions.Id, "Scope")

        $graphPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $GraphServicePrincipalAppId + "'")
        if (-not $graphPrincipal)
        {
            New-AzureADServicePrincipal -AppId $GraphServicePrincipalAppId | Format-Table -AutoSize
            Write-Output "Added Graph principal to AAD"
            $graphPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $GraphServicePrincipalAppId + "'")
        }
        $userRead = $graphPrincipal.Oauth2Permissions | Where-Object { $_.Type -eq "User" -and $_.Value -eq "User.Read" }
        $graphAccess = New-Object -TypeName "Microsoft.Open.AzureAD.Model.RequiredResourceAccess"
        $graphAccess.ResourceAppId = $graphPrincipal.AppId
        $graphAccess.ResourceAccess = (New-Object -TypeName "microsoft.open.azuread.model.resourceAccess" -ArgumentList $userRead.Id, "Scope")

        $clientApp = New-AzureADApplication -DisplayName $ClientAppName -RequiredResourceAccess @($keyVaultAccess, $graphAccess)
        $clientAppSPN = New-AzureADServicePrincipal -AppId $clientApp.AppId -Tags @($ClientAppName)
        $clientAppId = $clientApp.AppId
        Write-Output ('Created App Registration "' + $ClientAppName + '" with Application Id: ' + $clientAppId)
    }
    else {
        $clientApp = Get-AzureADApplication -Filter ("DisplayName eq '" + $ClientAppName + "'")
        $clientAppId = $clientApp.AppId
        Write-Output ('Found App Registration "' + $ClientAppName + '" with Application Id: ' + $clientAppId)
    }
            
    $clientAppSecretCredential = New-AzureADApplicationPasswordCredential -ObjectId $clientApp.ObjectId -CustomKeyIdentifier "ClientAppAccessKey" -EndDate (get-date).AddYears($DefaultSecretExpiryInYear)
    $ClientAppSecret = $clientAppSecretCredential.Value
    $clientAppSpId = $clientAppSPN.ObjectId

    Write-Output ('Generated application secret: ' + $ClientAppSecret)
    Write-Output '================================================================================='

    $templateObject = ConvertFrom-Json $azureTemplate -AsHashtable
    $templateObject.{$schema} = "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#"
    Write-Output 'Provisioning Azure resources. This may take a few minutes.'
    try {
        $deployment = New-AzResourceGroupDeployment -ResourceGroupName $FullResourceGroupName -TemplateObject $templateObject -aibuilderAppObjectId $aibuilderAuthorizationServiceObjectId -clientAppId $clientAppId -clientAppSecret $ClientAppSecret -clientAppSpObjectId  $clientAppSpId -microserviceSpObjectId $MicrosoftDynamicsERPMicroservicesAppObjectId -userSpObjectId $user.ObjectId -Force -ErrorAction Stop
    }
    catch {
        $ErrorMessage = $_.Exception.Message
        if ($ErrorMessage.Contains("not allowed to be updated"))
        {
            Write-Error ($ErrorMessage)
            Write-Warning "Some items in the existing resource group $FullResourceGroupName could not be updated. To resolve the issue, remove the existing resource group $FullResourceGroupName and run the script again."
        }
        else {
            throw
        }

    }
    if ($deployment.ProvisioningState -eq 'Succeeded') {
        Write-Output "Successfully deployed the following resources to Azure:"
        Write-Output ("  Key Vault:                         " + $deployment.Outputs.keyVaultName.Value)
        Write-Output ("  Storage Account:                   " + $deployment.Outputs.storageAccountName.Value)
        
        $keyVault = Get-AzKeyVault -VaultName $deployment.Outputs.keyVaultName.Value
        $tenantId = (Get-AzContext).Tenant.Id

        Write-Output "Values for LCS Data Lake Add-In:"
        Write-Output ("  Tenant ID:                         " + $tenantId)
        Write-Output ("  DNS Name:                          " + $keyVault.VaultUri)
        Write-Output "  Storage account secret name:       storage-account-name"
        Write-Output "  Application ID secret name:        app-id"
        Write-Output "  Application Secret secret name:    app-secret"
        Write-Warning "Copy this information for the LCS Add-in for easy access. Azure Cloud Shell will eventually time out and close."

        Write-Output '================================================================================='
        Write-Output "Values for System parameters > Data connections:"
        Write-Output ("  Application ID:                    " + $clientAppId)
        Write-Output ("  Application Secret:                " + $ClientAppSecret)
        Write-Output ("  DNS name:                          " + $keyVault.VaultUri)
        Write-Output "  Secret name:                       storage-account-connection-string"
        Write-Warning "Copy this information for the System parameters for easy access. Azure Cloud Shell will eventually time out and close."
    }
    else {
        Write-Output ("Provisioning Azure resources failed with the following state: " + $deployment.ProvisioningState)
        Write-Output ("Some of the resources may have been created in resource group: " + $FullResourceGroupName)
    }
}

function Assert-ScriptSetup {
    if ($PSVersionTable.PSEdition -ne 'Core' -or -not $env:ACC_TID) { 
        throw "This script needs to be uploaded and run from Azure Cloud Shell (PowerShell)." 
    }
    
    if ((Get-AzContext) -eq $null -and (Connect-AzAccount) -eq $null) {
        throw 'Unable to connect to Azure account.'
    }
}

function Set-AzureSubscription {
    $azSubscription = $null
    while (-not ($azSubscription)) {
        $subscriptionId = (Read-Host -Prompt "Enter the Azure Subscription ID: (leave blank for default)")
        if ([string]::IsNullOrWhitespace($subscriptionId)){
            break
        }
        elseif (-not [guid]::TryParse($subscriptionId, $([ref][guid]::Empty))) {
                Write-Warning "Azure Subscription ID must be a valid GUID."
                continue
        }

        $azSubscription = Select-AzSubscription -SubscriptionId $subscriptionId
    }
}

function Create-ADServicePrincipal {
    param (
        [string] $AppId
    )

    $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AppId + "'")
    if (-not $service) {
        New-AzureADServicePrincipal -AppId $AppId | Out-Null
        $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AppId + "'")
        Write-Host ("Added AAD Enterprise Application {0} with Application ID {1}" -f $service.DisplayName,$AppId)
    }
    else {
        Write-Host ("Found AAD Enterprise Application {0} with Application ID {1}" -f $service.DisplayName,$AppId)
    }

    return $service.ObjectId
}

$azureTemplate = @"
{
    "contentVersion": "1.0.0.0",
    "parameters": {
      "aibuilderAppObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of the AI Builder application."
        }
      },
      "clientAppId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the application ID of client application."
        }
      },
      "clientAppSecret": {
        "type": "String",
        "metadata": {
          "description": "Specifies the Azure App ID client secret to in azure key vault."
        }
      },
      "clientAppSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of a client application service principal."
        }
      },
      "userSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of tenant admin service principal."
        }
      },
      "microserviceSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of Microsoft Dynamics ERP Microservices service principal."
        }
      },
      "storageAccountType": {
        "type": "string",
        "defaultValue": "Standard_LRS",
        "allowedValues": [
          "Standard_LRS",
          "Standard_GRS",
          "Standard_ZRS",
          "Premium_LRS"
        ],
        "metadata": {
          "description": "Storage Account type"
        }
      }
    },
    "variables": {
      "storageAccountApiVersion": "2019-06-01",
      "keyVaultApiVersion": "2018-02-14",
      "secretsPermissions": [
        "list",
        "get"
      ],
      "location": "[resourceGroup().location]",
      "storageAccountName": "[concat('store', uniquestring(resourceGroup().id))]",
      "keyVaultName": "[concat('keyvault', uniquestring(resourceGroup().id))]",
      "owner": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '8e3af657-a8ff-443c-a75c-2fe8c4bcb635')]",
      "contributor": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', 'b24988ac-6180-42a0-ab88-20f7382dd24c')]",
      "storageAccountContributor": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '17d1049b-9a84-46fb-8f53-869881c3d3ab')]",
      "storageBlobDataOwner": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', 'b7e6dc6d-f1e8-4753-8033-0f276bb0955b')]",
      "storageBlobDataReader": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '2a2b9908-6ea1-4ae2-8e65-a410df84e7d1')]"
    },
    "resources": [
      {
        "type": "Microsoft.Storage/storageAccounts",
        "apiVersion": "[variables('storageAccountApiVersion')]",
        "name": "[variables('storageAccountName')]",
        "location": "[variables('location')]",
        "sku": {
          "name": "[parameters('storageAccountType')]"
        },
        "kind": "StorageV2",
        "properties": {
          "accessTier": "Hot",
          "supportsHttpsTrafficOnly": true,
          "isHnsEnabled": true
        },
        "resources": [
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'1')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('owner')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'2')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('contributor')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'3')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageAccountContributor')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'4')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageBlobDataOwner')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'5')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageBlobDataReader')]",
              "principalId": "[parameters('aibuilderAppObjectId')]"
            }
          }
        ]
      },
      {
        "type": "Microsoft.KeyVault/vaults",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "name": "[variables('keyVaultName')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.Storage/storageAccounts', variables('storageAccountName'))]"
        ],
        "tags": {
        },
        "properties": {
          "enabledForDeployment": false,
          "enabledForTemplateDeployment": false,
          "enabledForDiskEncryption": false,
          "enableRbacAuthorization": false,
          "accessPolicies": [
            {
              "objectId": "[parameters('clientAppSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            },
            {
              "objectId": "[parameters('microserviceSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            },
            {
              "objectId": "[parameters('userSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            }
          ],
          "tenantId": "[subscription().tenantId]",
          "sku": {
            "name": "Standard",
            "family": "A"
          },
          "enableSoftDelete": false,
          "networkAcls": {
            "defaultAction": "Allow",
            "bypass": "AzureServices"
          }
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'app-id')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[parameters('clientAppId')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'app-secret')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[parameters('clientAppSecret')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'storage-account-name')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[variables('storageAccountName')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'storage-account-connection-string')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[concat('DefaultEndpointsProtocol=https;AccountName=', variables('storageAccountName'), ';AccountKey=', listKeys(resourceId('Microsoft.Storage/storageAccounts', variables('storageAccountName')), variables('storageAccountApiVersion')).keys[0].value, ';EndpointSuffix=core.windows.net')]"
        }
      }
    ],
    "outputs": {
      "storageAccountName": {
        "type": "string",
        "value": "[variables('storageAccountName')]"
      },
      "keyVaultName": {
        "type": "string",
        "value": "[variables('keyVaultName')]"
      }
    }
  }
"@

try {
  Start-Transcript -path (Join-Path $HOME Provision-FinInsights-Azure.log)
  New-FinanceDataLakeAzureResources
}
catch {
  Write-Error $_.Exception.Message

  if ($PSItem.Exception.StackTrace -ne $null)
  {
      Write-Warning $_.Exception.StackTrace
  }

  $inner = $_.Exception.InnerException
  while ($null -ne $inner) {
    Write-Output 'Inner Exception:'
    Write-Error $_.Exception.Message
    Write-Warning $_.Exception.StackTrace
    $inner = $inner.InnerException
  }
}
finally {
  Stop-Transcript
}

```
---



## <a name="configure-the-data-lake"></a><span data-ttu-id="6778b-303">Configurar el lago de datos</span><span class="sxs-lookup"><span data-stu-id="6778b-303">Configure the data lake</span></span>

<span data-ttu-id="6778b-304">Siga estos pasos para usar LCS para agregar el complemento de Azure Data Lake al entorno.</span><span class="sxs-lookup"><span data-stu-id="6778b-304">Follow these steps to use LCS to add the Azure Data Lake add-in to the environment.</span></span>

1. <span data-ttu-id="6778b-305">Inicie sesión en LCS y luego, donde el nombre del entorno en el lado derecho de la página, seleccione **Todos los detalles**.</span><span class="sxs-lookup"><span data-stu-id="6778b-305">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="6778b-306">En la sección **Complementos de entorno**, seleccione **Instalar un nuevo complemento**.</span><span class="sxs-lookup"><span data-stu-id="6778b-306">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="6778b-307">Seleccione el complemento **Exportar a Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="6778b-307">Select the **Export to Data Lake** add-in.</span></span>
4. <span data-ttu-id="6778b-308">Introduzca los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="6778b-308">Enter the following values.</span></span>

    | <span data-ttu-id="6778b-309">Valor</span><span class="sxs-lookup"><span data-stu-id="6778b-309">Value</span></span>                                                              | <span data-ttu-id="6778b-310">Descripción</span><span class="sxs-lookup"><span data-stu-id="6778b-310">Description</span></span> |
    |--------------------------------------------------------------------|-------------|
    | <span data-ttu-id="6778b-311">Id. de inquilino de la suscripción de Azure donde se encuentra Key Vault</span><span class="sxs-lookup"><span data-stu-id="6778b-311">Tenant ID of the Azure Subscription where the Key Vault is located</span></span> | <span data-ttu-id="6778b-312">El id. de inquilino donde se encuentran la cuenta de almacenamiento, las aplicaciones y los almacenes de claves.</span><span class="sxs-lookup"><span data-stu-id="6778b-312">The tenant ID where the storage account, apps, and key vaults are located.</span></span> <span data-ttu-id="6778b-313">Para encontrar este valor, abra [Azure Portal](https://portal.azure.com), vaya a **Azure Active Directory** y copie el valor de **Id. de inquilino**.</span><span class="sxs-lookup"><span data-stu-id="6778b-313">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="6778b-314">Proporcione el nombre DNS de su almacén de claves</span><span class="sxs-lookup"><span data-stu-id="6778b-314">Provide the DNS name of your Key Vault</span></span>                             | <span data-ttu-id="6778b-315">El nombre DNS del almacén de claves, como `https://customkeyvault.vault.azure.net/`.</span><span class="sxs-lookup"><span data-stu-id="6778b-315">The DNS name of the key vault, such as `https://customkeyvault.vault.azure.net/`.</span></span> <span data-ttu-id="6778b-316">(Este valor coincide con el nombre DNS que se utiliza en el almacén de entidades).</span><span class="sxs-lookup"><span data-stu-id="6778b-316">(This value matches the DNS name that is used in the entity store.)</span></span> |
    | <span data-ttu-id="6778b-317">Proporcione el secreto que contiene el nombre de la cuenta de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="6778b-317">Provide the secret that contains the name of the storage account</span></span>   | <span data-ttu-id="6778b-318">**storage-account-name**</span><span class="sxs-lookup"><span data-stu-id="6778b-318">**storage-account-name**</span></span> |
    | <span data-ttu-id="6778b-319">Nombre secreto para el id. de la aplicación que se utilizará para acceder a Data Lake</span><span class="sxs-lookup"><span data-stu-id="6778b-319">Secret Name for App ID to be used for accessing Data Lake</span></span>          | <span data-ttu-id="6778b-320">**app-id**</span><span class="sxs-lookup"><span data-stu-id="6778b-320">**app-id**</span></span> |
    | <span data-ttu-id="6778b-321">Nombre secreto que se utilizará con el id. de la aplicación</span><span class="sxs-lookup"><span data-stu-id="6778b-321">Secret name to be used with App ID</span></span>                                 | <span data-ttu-id="6778b-322">**app-secret**</span><span class="sxs-lookup"><span data-stu-id="6778b-322">**app-secret**</span></span> |

5. <span data-ttu-id="6778b-323">Acepte los términos y seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="6778b-323">Agree to the terms, and select **Install**.</span></span>

<span data-ttu-id="6778b-324">El complemento se instalará en unos minutos.</span><span class="sxs-lookup"><span data-stu-id="6778b-324">The add-in will be installed within a few minutes.</span></span>

## <a name="configure-ai-builder"></a><span data-ttu-id="6778b-325">Configurar AI Builder</span><span class="sxs-lookup"><span data-stu-id="6778b-325">Configure AI Builder</span></span>

1. <span data-ttu-id="6778b-326">Inicie sesión en LCS y abra la página **Detalles del entorno**.</span><span class="sxs-lookup"><span data-stu-id="6778b-326">Sign in to LCS, and open the **Environment details** page.</span></span>
2. <span data-ttu-id="6778b-327">Desplácese a la sección **Complementos del entorno**.</span><span class="sxs-lookup"><span data-stu-id="6778b-327">Scroll to the **Environment add-ins** section.</span></span> <span data-ttu-id="6778b-328">Debería ver los complementos que ya están instalados en este entorno.</span><span class="sxs-lookup"><span data-stu-id="6778b-328">You should see the add-ins that are already installed in this environment.</span></span> <span data-ttu-id="6778b-329">Si el complemento **Exportar a Data Lake** no está entre ellos, configure este complemento.</span><span class="sxs-lookup"><span data-stu-id="6778b-329">If the **Export to Data Lake** add-in isn't among them, configure this add-in.</span></span>
3. <span data-ttu-id="6778b-330">Seleccione el complemento **Obtener información**.</span><span class="sxs-lookup"><span data-stu-id="6778b-330">Select the **Get insights** add-in.</span></span>
4. <span data-ttu-id="6778b-331">En la página de detalles del complemento **Obtener información**, introduzca los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="6778b-331">On the **Get insights** add-in details page, enter the following values.</span></span>

    | <span data-ttu-id="6778b-332">Valor</span><span class="sxs-lookup"><span data-stu-id="6778b-332">Value</span></span>                                                    | <span data-ttu-id="6778b-333">Descripción</span><span class="sxs-lookup"><span data-stu-id="6778b-333">Description</span></span> |
    |----------------------------------------------------------|-------------|
    | <span data-ttu-id="6778b-334">URL de la organización CDS</span><span class="sxs-lookup"><span data-stu-id="6778b-334">CDS Organization URL</span></span>                                     | <span data-ttu-id="6778b-335">La URL de la organización de Dataverse copiada de lo anterior.</span><span class="sxs-lookup"><span data-stu-id="6778b-335">The Dataverse organization URL copied from above.</span></span> |
    | <span data-ttu-id="6778b-336">Id. de organización CDS</span><span class="sxs-lookup"><span data-stu-id="6778b-336">CDS Org ID</span></span>                                               | <span data-ttu-id="6778b-337">Ei id. de la organización de Dataverse copiado de lo anterior.</span><span class="sxs-lookup"><span data-stu-id="6778b-337">The Dataverse organization ID copied from above.</span></span> |
5. <span data-ttu-id="6778b-338">Habiite **Este es el entorno de CDS predeterminado para el inquilino**.</span><span class="sxs-lookup"><span data-stu-id="6778b-338">Enable **Is this the default environment for you Tenant**.</span></span>
    
## <a name="configure-the-entity-store"></a><span data-ttu-id="6778b-339">Configurar el almacén de entidades</span><span class="sxs-lookup"><span data-stu-id="6778b-339">Configure the entity store</span></span>

<span data-ttu-id="6778b-340">Siga estos pasos para configurar el almacén de entidades en su entorno de Finance.</span><span class="sxs-lookup"><span data-stu-id="6778b-340">Follow these steps to set up the entity store in your Finance environment.</span></span>

1. <span data-ttu-id="6778b-341">Vaya a **Administración del sistema \> Configuración \> Parámetros del sistema \> Conexiones de datos**.</span><span class="sxs-lookup"><span data-stu-id="6778b-341">Go to **System administration \> Setup \> System parameters \> Data connections**.</span></span>
2. <span data-ttu-id="6778b-342">Configure los siguientes campos de Key Vault:</span><span class="sxs-lookup"><span data-stu-id="6778b-342">Set the following key vault fields:</span></span>

    - <span data-ttu-id="6778b-343">**Id. de la aplicación (cliente)**: introduzca el id. de cliente de la aplicación que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6778b-343">**Application (client) ID** – Enter the application client ID that you created earlier.</span></span>
    - <span data-ttu-id="6778b-344">**Secreto de la aplicación**: introduzca el secreto que guardó para la aplicación que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6778b-344">**Application Secret** – Enter the secret that you saved for the application that you created earlier.</span></span>
    - <span data-ttu-id="6778b-345">**Nombre DNS**: puede encontrar el nombre del sistema de nombres de dominio (DNS) en la página de detalles de la aplicación que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6778b-345">**DNS name** – You can find the Domain Name System (DNS) name on the application details page for the application that you created earlier.</span></span>
    - <span data-ttu-id="6778b-346">**Nombre secreto**: introduzca **storage-account-connection-string**.</span><span class="sxs-lookup"><span data-stu-id="6778b-346">**Secret name** – Enter **storage-account-connection-string**.</span></span>
3. <span data-ttu-id="6778b-347">Habilite **Habilitar integración de Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="6778b-347">Enable **Enable Data Lake integration**.</span></span>
4. <span data-ttu-id="6778b-348">Seleccione **Probar Azure Key Vault** y verifique que no haya errores.</span><span class="sxs-lookup"><span data-stu-id="6778b-348">Select **Test Azure Key Vault** and verify there are no errors.</span></span>
5. <span data-ttu-id="6778b-349">Seleccione **Probar amacenamiento de Azure** y verifique que no haya errores.</span><span class="sxs-lookup"><span data-stu-id="6778b-349">Select **Test Azure storage** and verify there are no errors.</span></span>

## <a name="feedback-and-support"></a><span data-ttu-id="6778b-350">Comentarios y soporte técnico</span><span class="sxs-lookup"><span data-stu-id="6778b-350">Feedback and support</span></span>

<span data-ttu-id="6778b-351">Envíe un correo electrónico a [Información sobre pagos de clientes (Vista previa)](mailto:fiap@microsoft.com) si está interesado en proporcionar comentarios o necesita ayuda.</span><span class="sxs-lookup"><span data-stu-id="6778b-351">Please send an email to [Customer payment insights (Preview)](mailto:fiap@microsoft.com) if you are interested in providing feedback or need support.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="6778b-352">Aviso de privacidad</span><span class="sxs-lookup"><span data-stu-id="6778b-352">Privacy notice</span></span>

<span data-ttu-id="6778b-353">Las versiones preliminares (1) pueden utilizar menos privacidad y menos medidas de seguridad que el servicio Dynamics 365 Finance and Operations, (2) no están incluidas en el acuerdo de nivel de servicio para este servicio, (3) no deben utilizarse para procesar datos personales u otros datos que estén sujetos a requisitos de cumplimiento legal o reglamentario, y (4) disponen de soporte limitado.</span><span class="sxs-lookup"><span data-stu-id="6778b-353">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
