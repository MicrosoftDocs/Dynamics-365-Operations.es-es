---
title: 'Configuración de Finance insights para la versión preliminar pública (versión preliminar): versión 10.0.20 y posteriores'
description: Este tema explica cómo configurar su sistema para que utilice las capacidades que están disponibles en Finance Insights para la versión preliminar pública en la versión 10.0.20 y posteriores.
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
ms.search.validFrom: 2021-06-03
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: 613bd4816e2f0c4fbb56cf79779a08c6a09592bd
ms.sourcegitcommit: 655b0e16c7aef6182cd58bc816b901470e1bb2ce
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "6222621"
---
# <a name="configuration-for-finance-insights-for-public-preview-preview---version-10020-and-later"></a><span data-ttu-id="31e1e-103">Configuración de Finance insights para la versión preliminar pública (versión preliminar): versión 10.0.20 y posteriores</span><span class="sxs-lookup"><span data-stu-id="31e1e-103">Configuration for Finance insights for public preview (preview) - version 10.0.20 and later</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="31e1e-104">Finance Insights combina la funcionalidad de Microsoft Dynamics 365 Finance con Dataverse, Azure y AI Builder para proporcionar potentes herramientas de pronóstico para su organización.</span><span class="sxs-lookup"><span data-stu-id="31e1e-104">Finance insights combines functionality from Microsoft Dynamics 365 Finance with Dataverse, Azure, and AI Builder to provide powerful forecasting tools for your organization.</span></span> <span data-ttu-id="31e1e-105">Este tema explica cómo configurar Dynamics 365 Finance versión 10.0.20 para que su sistema pueda utilizar las capacidades que están disponibles en Finance Insights para la versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="31e1e-105">This topic explains how to configure Dynamics 365 Finance version 10.0.20 so that your system can use the capabilities that are available in Finance insights public preview.</span></span>

> [!NOTE]
> <span data-ttu-id="31e1e-106">Los pasos de configuración que se describen en este tema se aplican solo a la versión 10.0.20 y posteriores de Finance.</span><span class="sxs-lookup"><span data-stu-id="31e1e-106">The configuration steps that are described in this topic apply only to Finance version 10.0.20 and later.</span></span> <span data-ttu-id="31e1e-107">Para configurar Finance Insights en la versión 10.0.19 y anteriores, consulte [Configuración de Finance Insights: versiones hasta la 10.0.18](configure-for-fin-insites.md).</span><span class="sxs-lookup"><span data-stu-id="31e1e-107">'To set up Finance insights on version 10.0.19 and earlier, see [Configuration for Finance insights - versions up to 10.0.18](configure-for-fin-insites.md).</span></span>

## <a name="deploy-finance"></a><span data-ttu-id="31e1e-108">Implementar Finance</span><span class="sxs-lookup"><span data-stu-id="31e1e-108">Deploy Finance</span></span>

<span data-ttu-id="31e1e-109">Para implementar los entornos, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="31e1e-109">Follow these steps to deploy the environments.</span></span>

1. <span data-ttu-id="31e1e-110">En Microsoft Dynamics Lifecycle Services (LCS), cree o actualice un entorno de Finance.</span><span class="sxs-lookup"><span data-stu-id="31e1e-110">In Microsoft Dynamics Lifecycle Services (LCS), create or update a Finance environment.</span></span> <span data-ttu-id="31e1e-111">El entorno requiere la versión de la aplicación 10.0.20 o posterior de las aplicaciones de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="31e1e-111">The environment requires app version 10.0.20 or later of Finance and Operations apps.</span></span>
2. <span data-ttu-id="31e1e-112">El entorno debe ser un entorno de alta disponibilidad (HA) en espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="31e1e-112">The environment must be a high-availability (HA) environment in Sandbox.</span></span> <span data-ttu-id="31e1e-113">(Este tipo de entorno también se conoce como entorno de nivel 2). Para obtener más información, consulte [Planificación de entornos](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="31e1e-113">(This type of environment is also known as a Tier-2 environment.) For more information, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
3. <span data-ttu-id="31e1e-114">Si está configurando Finance Insights en un entorno de espacio aislado, es posible que deba copiar los datos de producción en ese entorno para que funcionen las predicciones.</span><span class="sxs-lookup"><span data-stu-id="31e1e-114">If you are configuring Finance insights in a Sandbox environment, you might need to copy production data to that environment for predictions to work.</span></span> <span data-ttu-id="31e1e-115">El modelo de predicción utiliza varios años de datos para generar predicciones.</span><span class="sxs-lookup"><span data-stu-id="31e1e-115">The prediction model uses multiple years of data to build predictions.</span></span> <span data-ttu-id="31e1e-116">Los datos de la demostración de Contoso no contienen suficientes datos históricos para entrenar adecuadamente el modelo de predicción.</span><span class="sxs-lookup"><span data-stu-id="31e1e-116">The Contoso demo data doesn’t contain enough historical data to train the prediction model adequately.</span></span> 

## <a name="configure-dataverse"></a><span data-ttu-id="31e1e-117">Configurar Dataverse</span><span class="sxs-lookup"><span data-stu-id="31e1e-117">Configure Dataverse</span></span>

<span data-ttu-id="31e1e-118">Siga estos pasos para configurar Dataverse para Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="31e1e-118">Follow these steps to configure Dataverse for Finance insights.</span></span>

1. <span data-ttu-id="31e1e-119">En LCS, abra la página del entorno y verifique que la sección **Integración de Power Platform** ya está configurada.</span><span class="sxs-lookup"><span data-stu-id="31e1e-119">In LCS, open the environment page, and verify that the **Power Platform Integration** section is already set up.</span></span>

    - <span data-ttu-id="31e1e-120">Si ya está configurada, el nombre del entorno de Dataverse vinculado al entorno de Finance debe enumerarse.</span><span class="sxs-lookup"><span data-stu-id="31e1e-120">If it's already set up, the Dataverse environment name that is linked to the Finance environment should be listed.</span></span>
    - <span data-ttu-id="31e1e-121">Si aún no está configurado, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="31e1e-121">If it isn't yet set up, follow these steps:</span></span>

        1. <span data-ttu-id="31e1e-122">En la sección **Integración de Power Platform**, seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-122">In the **Power Platform Integration** section, select **Setup**.</span></span> <span data-ttu-id="31e1e-123">La configuración del entorno puede tardar hasta una hora.</span><span class="sxs-lookup"><span data-stu-id="31e1e-123">Setup of the environment might take up to an hour.</span></span>
        2. <span data-ttu-id="31e1e-124">Si ya está configurado correctamente el entorno de Dataverse, el nombre del entorno de Dataverse vinculado al entorno de Finance debe enumerarse.</span><span class="sxs-lookup"><span data-stu-id="31e1e-124">If the Dataverse environment is successfully set up, the Dataverse environment name that is linked to the Finance environment should be listed.</span></span>

        > [!NOTE]
        > <span data-ttu-id="31e1e-125">Después de completar la configuración del entorno, **no** seleccione **Enlace a CDS para aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-125">After you complete the environment setup, do **not** select **Link to CDS for Apps**.</span></span> <span data-ttu-id="31e1e-126">Este botón no es necesario para Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="31e1e-126">This button isn't required for Finance insights.</span></span> <span data-ttu-id="31e1e-127">Si lo selecciona, no podrá configurar los complementos de entorno necesarios en LCS.</span><span class="sxs-lookup"><span data-stu-id="31e1e-127">If you select it, you won't be able to configure the required environment add-ins in LCS.</span></span>

## <a name="configure-azure"></a><span data-ttu-id="31e1e-128">Configurar Azure</span><span class="sxs-lookup"><span data-stu-id="31e1e-128">Configure Azure</span></span>

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a><span data-ttu-id="31e1e-129">Use Azure Cloud Shell para configurar los recursos de Data Lake de Finance Insights</span><span class="sxs-lookup"><span data-stu-id="31e1e-129">Use Azure Cloud Shell to set up Finance insights Data Lake resources</span></span>

# <a name="use-a-windows-powershell-script"></a>[<span data-ttu-id="31e1e-130">Utilizar un script de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="31e1e-130">Use a Windows PowerShell script</span></span>](#tab/use-a-powershell-script)

<span data-ttu-id="31e1e-131">Se ha proporcionado un script de Windows PowerShell para que pueda configurar fácilmente los recursos de Azure que se describen en [Configurar la exportación a Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="31e1e-131">A Windows PowerShell script has been provided so that you can easily set up the Azure resources that are described in [Configure export to Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span></span> <span data-ttu-id="31e1e-132">Si prefiere realizar la configuración manualmente, omita este procedimiento y, en su lugar, complete el procedimiento de la sección [Configuración manual](#manual-setup).</span><span class="sxs-lookup"><span data-stu-id="31e1e-132">If you prefer to do the setup manually, skip this procedure, and complete the procedure in the [Manual setup](#manual-setup) section instead.</span></span>

> [!NOTE]
> <span data-ttu-id="31e1e-133">Utilice el siguiente procedimiento para ejecutar el script de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="31e1e-133">Use the following procedure to run the Windows PowerShell script.</span></span> <span data-ttu-id="31e1e-134">Es posible que la configuración no funcione si utiliza la opción **Probarlo** en la CLI de Azure o si ejecuta el script en su computadora.</span><span class="sxs-lookup"><span data-stu-id="31e1e-134">The setup might not work if you use the **Try it** option in Azure CLI or if you run the script on your computer.</span></span>

<span data-ttu-id="31e1e-135">Siga estos pasos para usar el script de Windows PowerShell para configurar Azure.</span><span class="sxs-lookup"><span data-stu-id="31e1e-135">Follow these steps to use the Windows PowerShell script to configure Azure.</span></span> <span data-ttu-id="31e1e-136">Debe tener derechos para crear un grupo de recursos de Azure, recursos de Azure y una aplicación de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="31e1e-136">You must have rights to create an Azure resource group, Azure resources, and an Azure AD application.</span></span> <span data-ttu-id="31e1e-137">Para obtener información sobre los permisos necesarios, consulte [Comprobar los permisos de Azure AD](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span><span class="sxs-lookup"><span data-stu-id="31e1e-137">For information about the required permissions, see [Check Azure AD permissions](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span></span>

1. <span data-ttu-id="31e1e-138">En [Azure Portal](https://portal.azure.com), vaya a su suscripción de Azure de destino.</span><span class="sxs-lookup"><span data-stu-id="31e1e-138">In the [Azure portal](https://portal.azure.com), go to your target Azure subscription.</span></span>
2. <span data-ttu-id="31e1e-139">Seleccione **Cloud Shell** a la derecha del campo **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-139">Select **Cloud Shell** to the right of the **Search** field.</span></span>
3. <span data-ttu-id="31e1e-140">Seleccione **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-140">Select **PowerShell**.</span></span>
4. <span data-ttu-id="31e1e-141">Cree almacenamiento si se le solicita que lo haga.</span><span class="sxs-lookup"><span data-stu-id="31e1e-141">Create storage if you're prompted to create it.</span></span>
5. <span data-ttu-id="31e1e-142">En la pestaña **CLI de Azure**, seleccione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-142">On the **Azure CLI** tab, select **Copy**.</span></span>
6. <span data-ttu-id="31e1e-143">En el Bloc de notas, abra un archivo nuevo y péguelo en el script de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="31e1e-143">In Notepad, open a new file, and paste in the Windows PowerShell script.</span></span>
7. <span data-ttu-id="31e1e-144">Guarde el archivo como **ConfigureDataLake.ps1**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-144">Save the file as **ConfigureDataLake.ps1**.</span></span>
8. <span data-ttu-id="31e1e-145">Suba el script de Windows PowerShell a la sesión usando la opción de menú para cargar en Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="31e1e-145">Upload the Windows PowerShell script to the session by using the menu option for upload in Cloud Shell.</span></span>
9. <span data-ttu-id="31e1e-146">Ejecute el script **.\ConfigureDataLake.ps1**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-146">Run the **.\ConfigureDataLake.ps1** script.</span></span>
10. <span data-ttu-id="31e1e-147">Siga las instrucciones para ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="31e1e-147">Follow the prompts to run the script.</span></span>
11. <span data-ttu-id="31e1e-148">Utilice la información de la salida del script para instalar el complemento Exportar a Data Lake en LCS.</span><span class="sxs-lookup"><span data-stu-id="31e1e-148">Use the information from the script output to install the Export to Data Lake add-in in LCS.</span></span>

### <a name="manual-setup"></a><span data-ttu-id="31e1e-149">Configuración manual</span><span class="sxs-lookup"><span data-stu-id="31e1e-149">Manual setup</span></span>

#### <a name="add-applications-to-the-azure-ad-tenant"></a><span data-ttu-id="31e1e-150">Agregar aplicaciones al inquilino de Azure AD</span><span class="sxs-lookup"><span data-stu-id="31e1e-150">Add applications to the Azure AD tenant</span></span>

1. <span data-ttu-id="31e1e-151">En [Azure Portal](https://portal.azure.com), vaya a **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-151">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**.</span></span>
2. <span data-ttu-id="31e1e-152">Seleccione **Gestionar \> Aplicaciones empresariales**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-152">Select **Manage \> Enterprise applications**.</span></span>
3. <span data-ttu-id="31e1e-153">Busque las siguientes aplicaciones por id. de aplicación.</span><span class="sxs-lookup"><span data-stu-id="31e1e-153">Search for the following applications by app ID.</span></span>

    | <span data-ttu-id="31e1e-154">Solicitud</span><span class="sxs-lookup"><span data-stu-id="31e1e-154">Application</span></span>                              | <span data-ttu-id="31e1e-155">Id. de aplicación</span><span class="sxs-lookup"><span data-stu-id="31e1e-155">App ID</span></span>                               |
    |------------------------------------------|--------------------------------------|
    | <span data-ttu-id="31e1e-156">Microservicios de Microsoft Dynamics ERP</span><span class="sxs-lookup"><span data-stu-id="31e1e-156">Microsoft Dynamics ERP Microservices</span></span>     | <span data-ttu-id="31e1e-157">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="31e1e-157">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
    | <span data-ttu-id="31e1e-158">CDS de microservicios de Microsoft Dynamics ERP</span><span class="sxs-lookup"><span data-stu-id="31e1e-158">Microsoft Dynamics ERP Microservices CDS</span></span> | <span data-ttu-id="31e1e-159">703e2651-d3fc-48f5-942c-74274233dba8</span><span class="sxs-lookup"><span data-stu-id="31e1e-159">703e2651-d3fc-48f5-942c-74274233dba8</span></span> |
    | <span data-ttu-id="31e1e-160">Servicio de autorización de AI Builder</span><span class="sxs-lookup"><span data-stu-id="31e1e-160">AI Builder Authorization Service</span></span>         | <span data-ttu-id="31e1e-161">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span><span class="sxs-lookup"><span data-stu-id="31e1e-161">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span></span> |

<span data-ttu-id="31e1e-162">Si no puede encontrar ninguna de las aplicaciones anteriores, intente los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="31e1e-162">If you can't find any of the preceding applications, try the following steps.</span></span>

1. <span data-ttu-id="31e1e-163">En su equipo local, en el menú **Inicio**, busque **powershell**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-163">On your local computer, on the **Start** menu, search for **powershell**.</span></span>
2. <span data-ttu-id="31e1e-164">Seleccione y mantenga pulsado (o haga clic derecho) en **Windows PowerShell** y luego seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-164">Select and hold (or right-click) **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="31e1e-165">Ejecute el siguiente comando para instalar el módulo **AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-165">Run the following command to install the **AzureAD** module.</span></span>

    `Install-Module -Name AzureAD`

4. <span data-ttu-id="31e1e-166">Si se requiere un proveedor NuGet para continuar, seleccione **Y** para instalarlo.</span><span class="sxs-lookup"><span data-stu-id="31e1e-166">If a NuGet provider is required to continue, select **Y** to install it.</span></span>
5. <span data-ttu-id="31e1e-167">Si recibe un mensaje "Repositorio no confiable", seleccione **Y** para continuar.</span><span class="sxs-lookup"><span data-stu-id="31e1e-167">If you receive an "Untrusted repository" message, select **Y** to continue.</span></span>
6. <span data-ttu-id="31e1e-168">Para cada aplicación que deba agregarse, ejecute los siguientes comandos para agregar la aplicación a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="31e1e-168">For each application that must be added, run the following commands to add the application to Azure AD.</span></span> <span data-ttu-id="31e1e-169">Cuando se le solicite, inicie sesión como administrador de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="31e1e-169">When you're prompted, sign in as the Azure AD administrator.</span></span>

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a><span data-ttu-id="31e1e-170">Crear recursos de Azure</span><span class="sxs-lookup"><span data-stu-id="31e1e-170">Create Azure resources</span></span>

> [!NOTE]
> <span data-ttu-id="31e1e-171">Asegúrese de crear los siguientes recursos en la misma instancia de Azure AD en la que está el entorno de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="31e1e-171">Make sure that you create the following resources in the same Azure AD instance that the Dataverse environment is in.</span></span> <span data-ttu-id="31e1e-172">No puede usar recursos de una instancia de Azure AD diferente.</span><span class="sxs-lookup"><span data-stu-id="31e1e-172">You can't use resources from a different Azure AD instance.</span></span>

1. <span data-ttu-id="31e1e-173">Cree una cuenta de almacenamiento:</span><span class="sxs-lookup"><span data-stu-id="31e1e-173">Create a storage account:</span></span>

    1. <span data-ttu-id="31e1e-174">En [Azure Portal](https://portal.azure.com), cree una cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="31e1e-174">In the [Azure portal](https://portal.azure.com), create a storage account.</span></span>
    2. <span data-ttu-id="31e1e-175">En el cuadro de diálogo **Crear cuenta de almacenamiento**, establezca los siguientes campo:</span><span class="sxs-lookup"><span data-stu-id="31e1e-175">In the **Create storage account** dialog box, set the following fields:</span></span>

        - <span data-ttu-id="31e1e-176">**Ubicación**: seleccione el centro de datos donde se encuentra su entorno.</span><span class="sxs-lookup"><span data-stu-id="31e1e-176">**Location** – Select the data center where your environment is located.</span></span>
        - <span data-ttu-id="31e1e-177">**Rendimiento**: es recomendable seleccionar **Estándar**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-177">**Performance** – We recommend that you select **Standard**.</span></span>
        - <span data-ttu-id="31e1e-178">**Tipo de cuenta**: debe elegir **StorageV2**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-178">**Account kind** – You must select **StorageV2**.</span></span>

    3. <span data-ttu-id="31e1e-179">En el cuadro de diálogo **Opciones avanzadas**, para la opción **Data Lake Storage Gen2**, seleccione **Habilitar** en la característica **Espacios de nombres jerárquicos**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-179">In the **Advanced options** dialog box, for the **Data Lake storage Gen2** option, select **Enable** under the **Hierarchical namespaces** feature.</span></span> <span data-ttu-id="31e1e-180">Si no activa esta característica, no puede emplear datos que las aplicaciones de Finance and Operations escriben utilizando servicios como flujos de datos de Power BI.</span><span class="sxs-lookup"><span data-stu-id="31e1e-180">If you don't enable this feature, you can't consume data that Finance and Operations apps write by using services such as Power BI data flows.</span></span>
    4. <span data-ttu-id="31e1e-181">Seleccione **Revisar y crear**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-181">Select **Review and create**.</span></span> <span data-ttu-id="31e1e-182">Cuando se completa la implementación, el nuevo recurso se muestra en Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="31e1e-182">When the deployment is completed, the new resource is shown in the Azure portal.</span></span>
    5. <span data-ttu-id="31e1e-183">Vaya a la cuenta de almacenamiento que creó.</span><span class="sxs-lookup"><span data-stu-id="31e1e-183">Go to the storage account that you created.</span></span>
    6. <span data-ttu-id="31e1e-184">En el menú izquierdo, seleccione **Claves de acceso**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-184">On the left menu, select **Access keys**.</span></span>
    7. <span data-ttu-id="31e1e-185">Copie y guarde el nombre de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="31e1e-185">Copy and save the name of the storage account.</span></span> <span data-ttu-id="31e1e-186">Tendrá que proporcionar este valor más adelante, cuando configure los secretos del almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="31e1e-186">You will have to provide this value later, when you set up key vault secrets.</span></span>

2. <span data-ttu-id="31e1e-187">Cree un almacén de claves:</span><span class="sxs-lookup"><span data-stu-id="31e1e-187">Create a key vault:</span></span>

    1. <span data-ttu-id="31e1e-188">En [Azure Portal](https://portal.azure.com), cree un almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="31e1e-188">In the [Azure portal](https://portal.azure.com), create a key vault.</span></span>
    2. <span data-ttu-id="31e1e-189">En el cuadro de diálogo **Crear almacén de claves**, en el campo **Ubicación**, seleccione el centro de datos donde se encuentra su entorno.</span><span class="sxs-lookup"><span data-stu-id="31e1e-189">In the **Create key vault** dialog box, in the **Location** field, select the data center where your environment is located.</span></span>
    3. <span data-ttu-id="31e1e-190">Una vez creado el almacén de claves, vaya a **Descripción general de Key Vault** y copie y guarde el nombre DNS.</span><span class="sxs-lookup"><span data-stu-id="31e1e-190">After key vault is created, go to **Key Vault Overview**, and copy and save the DNS name.</span></span> <span data-ttu-id="31e1e-191">Tendrá que proporcionar este valor más adelante, cuando configure el complemento Data Lake.</span><span class="sxs-lookup"><span data-stu-id="31e1e-191">You will have to provide this value later, when you set up the Data Lake add-in.</span></span>

3. <span data-ttu-id="31e1e-192">Cree y registre una aplicación de Azure AD:</span><span class="sxs-lookup"><span data-stu-id="31e1e-192">Create and register an Azure AD application:</span></span>

    1. <span data-ttu-id="31e1e-193">En [Azure Portal](https://portal.azure.com), vaya a **Azure Active Directory** y luego seleccione **Registros de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-193">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and then select **App registrations**.</span></span>
    2. <span data-ttu-id="31e1e-194">Seleccione **Registro de nueva aplicación** y configure los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="31e1e-194">Select **New application registration**, and set the following fields:</span></span>

        - <span data-ttu-id="31e1e-195">**Nombre**: especifique el nombre de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="31e1e-195">**Name** – Enter the name of the app.</span></span>
        - <span data-ttu-id="31e1e-196">**Tipo de aplicacion**: seleccione **API web**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-196">**Application type** – Select **Web API**.</span></span>
        - <span data-ttu-id="31e1e-197">**Redirigir la configuración de URI**: introduzca la URL de su instancia de Dynamics 365, como `https://yourdynamicsinstance.dynamics.com/auth`.</span><span class="sxs-lookup"><span data-stu-id="31e1e-197">**Redirect URI setup** – Enter the URL for your Dynamics 365 instance, such as `https://yourdynamicsinstance.dynamics.com/auth`.</span></span>

    3. <span data-ttu-id="31e1e-198">Vaya a la aplicación que acaba de crear, copie y guarde su valor de **Id. de la aplicación (cliente)**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-198">Go to the app that you just created, and copy and save its **Application (client) ID** value.</span></span> <span data-ttu-id="31e1e-199">Tendrá que proporcionar este valor más adelante, cuando configure los secretos del almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="31e1e-199">You will have to provide this value later, when you set up key vault secrets.</span></span>
    4. <span data-ttu-id="31e1e-200">Vaya a **Permisos de API** y siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="31e1e-200">Go to **API permissions**, and follow these steps:</span></span>

        1. <span data-ttu-id="31e1e-201">Seleccione **Agregar un permiso**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-201">Select **Add a permission**.</span></span>
        2. <span data-ttu-id="31e1e-202">Seleccione **Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-202">Select **Azure Key vault**.</span></span>
        3. <span data-ttu-id="31e1e-203">Después de seleccionar los permisos delegados, seleccione **usuario\_interpretación**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-203">After you select delegated permissions, select **user\_impersonation**.</span></span>
        4. <span data-ttu-id="31e1e-204">Seleccione **Agregar permisos**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-204">Select **Add permissions**.</span></span>

    5. <span data-ttu-id="31e1e-205">En el menú de la aplicación, seleccione **Certificados\&secretos** y luego siga estos pasos para crear secretos de Key Vault:</span><span class="sxs-lookup"><span data-stu-id="31e1e-205">On the menu for the app, select **Certificates \& secrets**, and then follow these steps to create Key Vault secrets:</span></span>

        1. <span data-ttu-id="31e1e-206">Seleccione **Nuevo secreto de cliente**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-206">Select **New client secret**.</span></span>
        2. <span data-ttu-id="31e1e-207">En el campo **Descripción de clave**, escriba un nombre.</span><span class="sxs-lookup"><span data-stu-id="31e1e-207">In the **Key Description** field, enter a name.</span></span>
        3. <span data-ttu-id="31e1e-208">Seleccione una duración y luego seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-208">Select a duration, and then select **Add**.</span></span> <span data-ttu-id="31e1e-209">Se genera un secreto en el campo **Valor**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-209">A secret is generated in the **Value** field.</span></span>
        4. <span data-ttu-id="31e1e-210">Copie y guarde el valor secreto de cliente.</span><span class="sxs-lookup"><span data-stu-id="31e1e-210">Copy and save the client secret value.</span></span> <span data-ttu-id="31e1e-211">Tendrá que proporcionar este valor más adelante, cuando configure los secretos del almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="31e1e-211">You will have to provide this value later, when you set up key vault secrets.</span></span>

4. <span data-ttu-id="31e1e-212">Cree secretos de Key Vault:</span><span class="sxs-lookup"><span data-stu-id="31e1e-212">Create Key Vault secrets:</span></span>

    1. <span data-ttu-id="31e1e-213">Vaya al almacén de claves que creó anteriormente y seleccione **Secretos**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-213">Go to the key vault that you created earlier, and select **Secrets**.</span></span>
    2. <span data-ttu-id="31e1e-214">Para cada nombre secreto de la siguiente tabla, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="31e1e-214">For each secret name in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="31e1e-215">Seleccione **Generar/Importar**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-215">Select **Generate/Import**.</span></span>
        2. <span data-ttu-id="31e1e-216">En el cuadro de diálogo **Crear un secreto**, en el campo **Opciones de carga**, seleccione **Manual**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-216">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
        3. <span data-ttu-id="31e1e-217">Cree el nombre secreto y el valor desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="31e1e-217">Create the secret name and value from the table.</span></span>
        4. <span data-ttu-id="31e1e-218">Seleccione **Habilitar** y, a continuación, seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-218">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="31e1e-219">El secreto se crea y se agrega a Key Vault.</span><span class="sxs-lookup"><span data-stu-id="31e1e-219">The secret is created and added to Key Vault.</span></span>

        | <span data-ttu-id="31e1e-220">Nombre secreto</span><span class="sxs-lookup"><span data-stu-id="31e1e-220">Secret name</span></span>                       | <span data-ttu-id="31e1e-221">Valor secreto</span><span class="sxs-lookup"><span data-stu-id="31e1e-221">Secret value</span></span>                                                                                 |
        |-----------------------------------|----------------------------------------------------------------------------------------------|
        | <span data-ttu-id="31e1e-222">app-id</span><span class="sxs-lookup"><span data-stu-id="31e1e-222">app-id</span></span>                            | <span data-ttu-id="31e1e-223">El id. de la aplicación que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="31e1e-223">The app ID of the application that you created earlier.</span></span>                                      |
        | <span data-ttu-id="31e1e-224">app-secret</span><span class="sxs-lookup"><span data-stu-id="31e1e-224">app-secret</span></span>                        | <span data-ttu-id="31e1e-225">El secreto de cliente que guardó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="31e1e-225">The client secret that you saved earlier.</span></span>                                                    |
        | <span data-ttu-id="31e1e-226">storage-account-name</span><span class="sxs-lookup"><span data-stu-id="31e1e-226">storage-account-name</span></span>              | <span data-ttu-id="31e1e-227">El nombre de la cuenta de almacenamiento que creó anteriormente, como **storageaccount1**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-227">The name of the storage account that you created earlier, such as **storageaccount1**.</span></span>       |

5. <span data-ttu-id="31e1e-228">Autorice a la aplicación a acceder al almacén de claves:</span><span class="sxs-lookup"><span data-stu-id="31e1e-228">Authorize the application to access the key vault:</span></span>

    1. <span data-ttu-id="31e1e-229">En [Azure Portal](https://portal.azure.com), abra el almacén de claves que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="31e1e-229">In the [Azure portal](https://portal.azure.com), open the key vault that you created earlier.</span></span>
    2. <span data-ttu-id="31e1e-230">Seleccione las políticas de acceso.</span><span class="sxs-lookup"><span data-stu-id="31e1e-230">Select the access policies.</span></span>
    3. <span data-ttu-id="31e1e-231">Para cada aplicación de la siguiente tabla, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="31e1e-231">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="31e1e-232">Seleccione **Agregar política de acceso** para crear una directiva de acceso.</span><span class="sxs-lookup"><span data-stu-id="31e1e-232">Select **Add Access Policy** to create an access policy.</span></span>
        2. <span data-ttu-id="31e1e-233">En el campo **Permisos secretos**, seleccione los permisos en la tabla.</span><span class="sxs-lookup"><span data-stu-id="31e1e-233">In the **Secret permissions** field, select the permissions from the table.</span></span>
        3. <span data-ttu-id="31e1e-234">En el campo **Seleccionar principal**, busque el nombre para mostrar de la aplicación en la tabla.</span><span class="sxs-lookup"><span data-stu-id="31e1e-234">In the **Select principal** field, search for the application display name from the table.</span></span>
        4. <span data-ttu-id="31e1e-235">Seleccione **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-235">Select **Select**.</span></span>
        5. <span data-ttu-id="31e1e-236">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-236">Select **Add**.</span></span>
        6. <span data-ttu-id="31e1e-237">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-237">Select **Save**.</span></span>

        | <span data-ttu-id="31e1e-238">Solicitud</span><span class="sxs-lookup"><span data-stu-id="31e1e-238">Application</span></span>                                              | <span data-ttu-id="31e1e-239">Permisos</span><span class="sxs-lookup"><span data-stu-id="31e1e-239">Permissions</span></span> |
        |----------------------------------------------------------|-------------|
        | <span data-ttu-id="31e1e-240">El nombre para mostrar de la nueva aplicación que ha creado</span><span class="sxs-lookup"><span data-stu-id="31e1e-240">The display name of the new application that you created</span></span> | <span data-ttu-id="31e1e-241">Obtener, lista</span><span class="sxs-lookup"><span data-stu-id="31e1e-241">Get, List</span></span>   |
        | <span data-ttu-id="31e1e-242">**Microservicios de Microsoft Dynamics ERP**</span><span class="sxs-lookup"><span data-stu-id="31e1e-242">**Microsoft Dynamics ERP Microservices**</span></span>                 | <span data-ttu-id="31e1e-243">Obtener, lista</span><span class="sxs-lookup"><span data-stu-id="31e1e-243">Get, List</span></span>   |

6. <span data-ttu-id="31e1e-244">Asignar roles para acceder a la cuenta de almacenamiento:</span><span class="sxs-lookup"><span data-stu-id="31e1e-244">Assign roles to access the storage account:</span></span>

    1. <span data-ttu-id="31e1e-245">En [Azure Portal](https://portal.azure.com), abra la cuenta de almacenamiento que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="31e1e-245">In the [Azure portal](https://portal.azure.com), open the storage account that you created earlier.</span></span>
    2. <span data-ttu-id="31e1e-246">Seleccione **Control de acceso (IAM)** y luego seleccione **Asignaciones de roles**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-246">Select **Access Control (IAM)**, and then select **Role Assignments**.</span></span>
    3. <span data-ttu-id="31e1e-247">Seleccione **Agregar, agregar asignación de roles**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-247">Select **Add, Add Role Assignment**.</span></span>
    4. <span data-ttu-id="31e1e-248">Para cada aplicación de la siguiente tabla, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="31e1e-248">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="31e1e-249">Seleccione el rol de la tabla.</span><span class="sxs-lookup"><span data-stu-id="31e1e-249">Select the role from the table.</span></span>
        2. <span data-ttu-id="31e1e-250">Deje el campo **Asignar acceso a** establecido en **Entidad de servicio, grupo o usuario de Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-250">Leave the **Assign access to** field set to **Azure AD user, group, or service principal**.</span></span>
        3. <span data-ttu-id="31e1e-251">En el campo **Seleccionar**, introduzca la aplicación desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="31e1e-251">In the **Select** field, enter the application from the table.</span></span>
        4. <span data-ttu-id="31e1e-252">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-252">Select **Save**.</span></span>

        | <span data-ttu-id="31e1e-253">Solicitud</span><span class="sxs-lookup"><span data-stu-id="31e1e-253">Application</span></span>                                              | <span data-ttu-id="31e1e-254">Función</span><span class="sxs-lookup"><span data-stu-id="31e1e-254">Role</span></span>                        |
        |----------------------------------------------------------|-----------------------------|
        | <span data-ttu-id="31e1e-255">El nombre para mostrar de la nueva aplicación que ha creado</span><span class="sxs-lookup"><span data-stu-id="31e1e-255">The display name of the new application that you created</span></span> | <span data-ttu-id="31e1e-256">Propietario</span><span class="sxs-lookup"><span data-stu-id="31e1e-256">Owner</span></span>                       |
        | <span data-ttu-id="31e1e-257">El nombre para mostrar de la nueva aplicación que ha creado</span><span class="sxs-lookup"><span data-stu-id="31e1e-257">The display name of the new application that you created</span></span> | <span data-ttu-id="31e1e-258">Contribuyente</span><span class="sxs-lookup"><span data-stu-id="31e1e-258">Contributor</span></span>                 |
        | <span data-ttu-id="31e1e-259">El nombre para mostrar de la nueva aplicación que ha creado</span><span class="sxs-lookup"><span data-stu-id="31e1e-259">The display name of the new application that you created</span></span> | <span data-ttu-id="31e1e-260">Colaborador de la cuenta de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="31e1e-260">Storage Account Contributor</span></span> |
        | <span data-ttu-id="31e1e-261">El nombre para mostrar de la nueva aplicación que ha creado</span><span class="sxs-lookup"><span data-stu-id="31e1e-261">The display name of the new application that you created</span></span> | <span data-ttu-id="31e1e-262">Propietario de datos de Storage Blob</span><span class="sxs-lookup"><span data-stu-id="31e1e-262">Storage Blob Data Owner</span></span>     |
        | <span data-ttu-id="31e1e-263">**Servicio de autorización de AI Builder**</span><span class="sxs-lookup"><span data-stu-id="31e1e-263">**AI Builder Authorization Service**</span></span>                     | <span data-ttu-id="31e1e-264">Lector de datos de Storage Blob</span><span class="sxs-lookup"><span data-stu-id="31e1e-264">Storage Blob Data Reader</span></span>    |

# <a name="azure-cli"></a>[<span data-ttu-id="31e1e-265">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="31e1e-265">Azure CLI</span></span>](#tab/azure-azure-cli)

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

## <a name="configure-the-export-to-data-lake-add-in"></a><span data-ttu-id="31e1e-266">Configurar el complemento Exportar a Data Lake</span><span class="sxs-lookup"><span data-stu-id="31e1e-266">Configure the Export to Data Lake add-in</span></span>

<span data-ttu-id="31e1e-267">Siga estos pasos para usar LCS para agregar el complemento Exportar a Data Lake al entorno.</span><span class="sxs-lookup"><span data-stu-id="31e1e-267">Follow these steps to use LCS to add the Export to Data Lake add-in to the environment.</span></span>

1. <span data-ttu-id="31e1e-268">Inicie sesión en LCS y luego, donde el nombre del entorno en el lado derecho de la página, seleccione **Todos los detalles**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-268">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="31e1e-269">En la sección **Complementos de entorno**, seleccione **Instalar un nuevo complemento**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-269">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="31e1e-270">Seleccione el complemento **Exportar a Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-270">Select the **Export to Data Lake** add-in.</span></span>
4. <span data-ttu-id="31e1e-271">Introduzca los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="31e1e-271">Enter the following values.</span></span>

    | <span data-ttu-id="31e1e-272">Valor</span><span class="sxs-lookup"><span data-stu-id="31e1e-272">Value</span></span>                                                              | <span data-ttu-id="31e1e-273">Descripción</span><span class="sxs-lookup"><span data-stu-id="31e1e-273">Description</span></span> |
    |--------------------------------------------------------------------|-------------|
    | <span data-ttu-id="31e1e-274">Id. de inquilino de la suscripción de Azure donde se encuentra Key Vault</span><span class="sxs-lookup"><span data-stu-id="31e1e-274">Tenant ID of the Azure Subscription where the Key Vault is located</span></span> | <span data-ttu-id="31e1e-275">El id. de inquilino donde se encuentran la cuenta de almacenamiento, las aplicaciones y los almacenes de claves.</span><span class="sxs-lookup"><span data-stu-id="31e1e-275">The tenant ID where the storage account, apps, and key vaults are located.</span></span> <span data-ttu-id="31e1e-276">Para obtener este valor, abra [Azure Portal](https://portal.azure.com), vaya a **Azure Active Directory** y copie el valor de **Id. de inquilino**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-276">To obtain this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="31e1e-277">Proporcione el nombre DNS de su almacén de claves</span><span class="sxs-lookup"><span data-stu-id="31e1e-277">Provide the DNS name of your Key Vault</span></span>                             | <span data-ttu-id="31e1e-278">El nombre DNS del almacén de claves, como `https://customkeyvault.vault.azure.net/`.</span><span class="sxs-lookup"><span data-stu-id="31e1e-278">The DNS name of the key vault, such as `https://customkeyvault.vault.azure.net/`.</span></span> |
    | <span data-ttu-id="31e1e-279">Proporcione el secreto que contiene el nombre de la cuenta de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="31e1e-279">Provide the secret that contains the name of the storage account</span></span>   | <span data-ttu-id="31e1e-280">**storage-account-name**</span><span class="sxs-lookup"><span data-stu-id="31e1e-280">**storage-account-name**</span></span> |
    | <span data-ttu-id="31e1e-281">Nombre secreto para el id. de la aplicación que se utilizará para acceder a Data Lake</span><span class="sxs-lookup"><span data-stu-id="31e1e-281">Secret Name for App ID to be used for accessing Data Lake</span></span>          | <span data-ttu-id="31e1e-282">**app-id**</span><span class="sxs-lookup"><span data-stu-id="31e1e-282">**app-id**</span></span> |
    | <span data-ttu-id="31e1e-283">Nombre secreto para el secreto del cliente de la aplicación</span><span class="sxs-lookup"><span data-stu-id="31e1e-283">Secret name for App client secret</span></span>                                  | <span data-ttu-id="31e1e-284">**app-secret**</span><span class="sxs-lookup"><span data-stu-id="31e1e-284">**app-secret**</span></span> |

5. <span data-ttu-id="31e1e-285">Acepte los términos y luego seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-285">Agree to the terms, and then select **Install**.</span></span>

<span data-ttu-id="31e1e-286">El complemento se instalará en unos minutos.</span><span class="sxs-lookup"><span data-stu-id="31e1e-286">The add-in will be installed within a few minutes.</span></span>

## <a name="configure-the-finance-insights-add-in"></a><span data-ttu-id="31e1e-287">Configurar el complemento Finance Insights</span><span class="sxs-lookup"><span data-stu-id="31e1e-287">Configure the Finance insights add-in</span></span>

> [!NOTE]
> <span data-ttu-id="31e1e-288">Si instaló anteriormente el complemento Get insights, desinstálelo antes de completar el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="31e1e-288">If you previously installed the Get insights add-in, uninstall it before you complete the following procedure.</span></span>

<span data-ttu-id="31e1e-289">Siga estos pasos para instalar el complemento Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="31e1e-289">Follow these steps to install the Finance insights add-in.</span></span>

1. <span data-ttu-id="31e1e-290">Inicie sesión en LCS y luego, donde el nombre del entorno en el lado derecho de la página, seleccione **Todos los detalles**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-290">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="31e1e-291">En la sección **Complementos de entorno**, seleccione **Instalar un nuevo complemento**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-291">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="31e1e-292">Seleccione el complemento **Finance Insights**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-292">Select the **Finance insights** add-in.</span></span>
4. <span data-ttu-id="31e1e-293">Acepte los términos y luego seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="31e1e-293">Agree to the terms, and then select **Install**.</span></span>

## <a name="feedback-and-support"></a><span data-ttu-id="31e1e-294">Comentarios y soporte técnico</span><span class="sxs-lookup"><span data-stu-id="31e1e-294">Feedback and support</span></span>

<span data-ttu-id="31e1e-295">Si está interesado en proporcionar comentarios o si necesita asistencia, envíe un correo elecrónico a [Finance Insights (versión preliminar)](mailto:fiap@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="31e1e-295">If you're interested in providing feedback, or if you require support, send an email to [Finance insights (Preview)](mailto:fiap@microsoft.com).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
