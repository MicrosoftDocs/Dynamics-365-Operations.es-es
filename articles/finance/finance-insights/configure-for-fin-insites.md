---
title: Configuración de Finance Insights (versión preliminar)
description: Este tema explica los pasos de configuración que permitirán que su sistema utilice las capacidades que están disponibles en Finance Insights.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: bb887bbff5eb5b92f588d3fa966ea204633575db
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115641"
---
# <a name="configuration-for-finance-insights-preview"></a><span data-ttu-id="10c1d-103">Configuración de Finance Insights (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="10c1d-103">Configuration for Finance insights (preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="10c1d-104">Finance Insights combina la funcionalidad de Microsoft Dynamics 365 Finance con Microsoft Dataverse, Azure y AI Builder para proporcionar potentes herramientas de pronóstico para su organización.</span><span class="sxs-lookup"><span data-stu-id="10c1d-104">Finance insights combines functionality from Microsoft Dynamics 365 Finance with Microsoft Dataverse, Azure, and AI Builder to provide powerful forecasting tools for your organization.</span></span> <span data-ttu-id="10c1d-105">Este tema explica los pasos de configuración que permitirán que su sistema utilice las capacidades que están disponibles en Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="10c1d-105">This topic explains the configuration steps that will enable your system to use the capabilities that are available in Finance insights.</span></span>

## <a name="deploy-dynamics-365-finance"></a><span data-ttu-id="10c1d-106">Implementar Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="10c1d-106">Deploy Dynamics 365 Finance</span></span>

<span data-ttu-id="10c1d-107">implemente los entornos siguiendo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="10c1d-107">Deploy the environments by following these steps.</span></span>

1. <span data-ttu-id="10c1d-108">En Microsoft Dynamics Lifecycle Services (LCS), cree o actualice un entorno de Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="10c1d-108">In Microsoft Dynamics Lifecycle Services (LCS), create or update a Dynamics 365 Finance environment.</span></span> <span data-ttu-id="10c1d-109">El entorno requiere la versión de la aplicación 10.0.11/Actualización de plataforma 35 o posterior.</span><span class="sxs-lookup"><span data-stu-id="10c1d-109">The environment requires app version 10.0.11/Platform update 35 or later.</span></span>
2. <span data-ttu-id="10c1d-110">El entorno debe ser un entorno de alta disponibilidad (HA) en espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="10c1d-110">The environment must be a high-availability (HA) environment in Sandbox.</span></span> <span data-ttu-id="10c1d-111">(Este tipo de entorno también se conoce como entorno de nivel 2). Para obtener más información, consulte [Planificación de entornos](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="10c1d-111">(This type of environment is also known as a Tier-2 environment.) For more information, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
3. <span data-ttu-id="10c1d-112">Si usa datos de demostración de Contoso, necesitará datos de ejemplo adicionales para usar las características de predicciones de pago del cliente, previsiones de flujo de efectivo y previsiones de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="10c1d-112">If you're using Contoso demo data, you will require additional sample data to use the Customer payment predictions, Cash flow forecasts, and Budget forecasts features.</span></span> 

## <a name="configure-dataverse"></a><span data-ttu-id="10c1d-113">Configurar Dataverse</span><span class="sxs-lookup"><span data-stu-id="10c1d-113">Configure Dataverse</span></span>

<span data-ttu-id="10c1d-114">Puede completar los pasos de configuración manual que siguen o puede acelerar el proceso de configuración mediante el script de Windows PowerShell que se proporciona.</span><span class="sxs-lookup"><span data-stu-id="10c1d-114">You can complete the manual configuration steps that follow, or you can speed up the configuration process by using the Windows PowerShell script that is provided.</span></span> <span data-ttu-id="10c1d-115">Cuando la secuencia de comandos de PowerShell haya terminado de ejecutarse, le proporcionará valores que podrá utilizar para configurar Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="10c1d-115">When the PowerShell script has finished running, it will give you values to use to configure Finance insights.</span></span> 

> [!NOTE]
> <span data-ttu-id="10c1d-116">Abra PowerShell en su PC para ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="10c1d-116">Open PowerShell on your PC to run the script.</span></span> <span data-ttu-id="10c1d-117">Es posible que necesite la versión 5 de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="10c1d-117">You may need PowerShell version 5.</span></span> <span data-ttu-id="10c1d-118">Es posible que la opción de Microsoft Azure CLI "Probarlo" no funcione.</span><span class="sxs-lookup"><span data-stu-id="10c1d-118">The Microsoft Azure CLI "Try it" option may not work.</span></span>

# <a name="manual-configuration-steps"></a>[<span data-ttu-id="10c1d-119">Pasos de configuración manual</span><span class="sxs-lookup"><span data-stu-id="10c1d-119">Manual configuration steps</span></span>](#tab/configuration-steps)

1. <span data-ttu-id="10c1d-120">Abra el [Centro de administración de Power Platform](https://admin.powerplatform.microsoft.com/) y siga estos pasos para crear un nuevo entorno de Dataverse en el mismo inquilino de Active Directory:</span><span class="sxs-lookup"><span data-stu-id="10c1d-120">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com/), and follow these steps to create a new Dataverse environment in the same Active Directory tenant:</span></span>

    1. <span data-ttu-id="10c1d-121">Abra la página **Entornos**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-121">Open the **Environments** page.</span></span>

        <span data-ttu-id="10c1d-122">[![Página de entornos](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span><span class="sxs-lookup"><span data-stu-id="10c1d-122">[![Environments page](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span></span>

    2. <span data-ttu-id="10c1d-123">Seleccione **Nuevo entorno**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-123">Select **New environment**.</span></span>
    3. <span data-ttu-id="10c1d-124">En el campo **Tipo**, seleccione **Espacio aislado**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-124">In the **Type** field, select **Sandbox**.</span></span>
    4. <span data-ttu-id="10c1d-125">Establezca la opción **Crear base de datos** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-125">Set the **Create Database** option to **Yes**.</span></span>
    5. <span data-ttu-id="10c1d-126">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-126">Select **Next**.</span></span>
    6. <span data-ttu-id="10c1d-127">Seleccione el idioma y la divisa de su organización.</span><span class="sxs-lookup"><span data-stu-id="10c1d-127">Select the language and currency for your organization.</span></span>
    7. <span data-ttu-id="10c1d-128">Acepte los valores predeterminados del resto de campos.</span><span class="sxs-lookup"><span data-stu-id="10c1d-128">Accept the default values for the other fields.</span></span>
    8. <span data-ttu-id="10c1d-129">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-129">Select **Save**.</span></span>
    9. <span data-ttu-id="10c1d-130">Actualice la página **Entornos**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-130">Refresh the **Environments** page.</span></span>
    10. <span data-ttu-id="10c1d-131">Espere hasta que el valor del campo **Estado** se actualice a **Listo**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-131">Wait until the value of the **State** field is updated to **Ready**.</span></span>
    11. <span data-ttu-id="10c1d-132">Anote el id. de organización de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="10c1d-132">Make a note of the Dataverse organization ID.</span></span>
    12. <span data-ttu-id="10c1d-133">Seleccione el entorno y luego seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-133">Select the environment, and then select **Settings**.</span></span>
    13. <span data-ttu-id="10c1d-134">Seleccione **Recursos \> Todas las configuraciones heredadas**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-134">Select **Resources \> All Legacy Settings**.</span></span>
    14. <span data-ttu-id="10c1d-135">En la barra de navegación superior, seleccione **Configuración** y luego seleccione **Personalizaciones**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-135">On the top navigation bar, select **Settings**, and then select **Customizations**.</span></span>
    15. <span data-ttu-id="10c1d-136">Seleccione **Recursos para desarrolladores**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-136">Select **Developer Resources**.</span></span>
    16. <span data-ttu-id="10c1d-137">Seleccione el campo **Id. de información de referencia de instancia** con el valor de id. de organización de Dataverse que anotó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="10c1d-137">Set the **Instance Reference Information ID** field to the Dataverse organization ID value that you made a note of earlier.</span></span>
    17. <span data-ttu-id="10c1d-138">En la barra de direcciones del navegador, anote la URL de la organización de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="10c1d-138">In the browser's address bar, make a note of the URL for the Dataverse organization.</span></span> <span data-ttu-id="10c1d-139">Por ejemplo, la URL puede ser `https://org42b2b3d3.crm.dynamics.com`.</span><span class="sxs-lookup"><span data-stu-id="10c1d-139">For example, the URL might be `https://org42b2b3d3.crm.dynamics.com`.</span></span>

2. <span data-ttu-id="10c1d-140">Si planea usar la función Previsiones de flujo de efectivo o Previsiones de presupuesto, siga estos pasos para actualizar el límite de anotaciones para su organización a al menos 50 megabytes (MB):</span><span class="sxs-lookup"><span data-stu-id="10c1d-140">If you plan to use the Cash flow forecasts or Budget forecasts feature, follow these steps to update the annotation limit for your organization to at least 50 megabytes (MB):</span></span>

    1. <span data-ttu-id="10c1d-141">Abra el [portal de Power Apps](https://make.powerapps.com).</span><span class="sxs-lookup"><span data-stu-id="10c1d-141">Open the [Power Apps portal](https://make.powerapps.com).</span></span>
    2. <span data-ttu-id="10c1d-142">Seleccione el entorno que acaba de crear y luego seleccione **Configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-142">Select the environment that you just created, and then select **Advanced settings**.</span></span>
    3. <span data-ttu-id="10c1d-143">Seleccione **Configuración \> Configuración de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-143">Select **Settings \> Email Configuration**.</span></span>
    4. <span data-ttu-id="10c1d-144">Cambie el valor del campo **Tamaño máximo de archivo** a **51.200**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-144">Change the value of the **Maximum file size** field to **51,200**.</span></span> <span data-ttu-id="10c1d-145">(El valor se expresa en kilobytes \[KB\]).</span><span class="sxs-lookup"><span data-stu-id="10c1d-145">(The value is expressed in kilobytes \[KB\].)</span></span>
    5. <span data-ttu-id="10c1d-146">Seleccione **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="10c1d-146">Select **OK** to save your changes.</span></span>

# <a name="windows-powershell-configuration-script"></a>[<span data-ttu-id="10c1d-147">Script de configuración de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="10c1d-147">Windows PowerShell configuration script</span></span>](#tab/powershell-configuration-script)

```azurecli-interactive
Write-Output 'The following modules need to be present for execution of this script:'
Write-Output '  Microsoft.PowerApps.Administration.PowerShell'
Write-Output '  Microsoft.PowerApps.PowerShell'
Write-Output '  Microsoft.Xrm.Tooling.CrmConnector.PowerShell'

try {
    $moduleConsent = Read-Host 'Is it ok to install or update these modules as needed? (yes/no)'
    if ($moduleConsent -ne 'yes' -and $moduleConsent -ne 'y') {
        Write-Warning 'User declined to install required modules.'
        return
    }

    $module = 'Microsoft.PowerApps.Administration.PowerShell'
    if (-not (Get-InstalledModule -Name $module -MinimumVersion '2.0.61' -ErrorAction SilentlyContinue)) {
        Install-Module -Name $module -MinimumVersion '2.0.61' -Force
        Write-Output ('Installed {0} module.' -f $module)
    }
    else {
        Write-Output ('{0} module found.' -f $module)
    }

    $module = 'Microsoft.PowerApps.PowerShell'
    if (-not (Get-InstalledModule -Name $module -MinimumVersion '1.0.9' -ErrorAction SilentlyContinue)) {
        Install-Module -Name $module -MinimumVersion '1.0.9' -AllowClobber -Force
        Write-Output ('Installed {0} module.' -f $module)
    }
    else {
        Write-Output ('{0} module found.' -f $module)
    }

    $module = 'Microsoft.Xrm.Tooling.CrmConnector.PowerShell'
    if (-not (Get-InstalledModule -Name $module -MinimumVersion '3.3.0.892' -ErrorAction SilentlyContinue)) {
        Install-Module -Name $module -MinimumVersion '3.3.0.892' -Force
        Write-Output ('Installed {0} module.' -f $module)
    }
    else {
        Write-Output ('{0} module found.' -f $module)
    }

    Write-Output '================================================================================='

    $useMfa = $false
    $useMfaPrompt = Read-Host "Does your organization require the use of multi-factor authentication? (yes/no)"
    if ($useMfaPrompt -eq 'yes' -or $useMfaPrompt -eq 'y') {
        $useMfa = $true
    }
    if(-not $useMfa) {
        $credential = Get-Credential -Message 'Power Apps Credential'
    }

    $orgFriendlyName = Read-Host "Enter the name of the CDS Organization to use or create: (blank for 'FinanceInsightsOrg')"
    if ($orgFriendlyName.Trim() -eq '') {
        $orgFriendlyName = 'FinanceInsightsOrg'
    }

    $isDefaultOrgPrompt = Read-Host ("Is '" + $orgFriendlyName + "' the default organization for your tenant? (yes/no)")
    if ($isDefaultOrgPrompt -eq 'yes' -or $isDefaultOrgPrompt -eq 'y') {
        $isDefaultOrg = $true
    }

    if ($credential) {
        Add-PowerAppsAccount -Username $credential.UserName -Password $credential.Password
    }
    else {
        Add-PowerAppsAccount
    }

    if ($isDefaultOrg) {
        $orgMatch = ('(default)')
        $environment = (Get-AdminPowerAppEnvironment | Where-Object { $_.IsDefault -eq $true })
    }
    else {
        $orgMatch = ('{0} (*)' -f $orgFriendlyName)
        $environment = (Get-AdminPowerAppEnvironment | Where-Object { ($_.IsDefault -eq $false -and ($_.DisplayName -eq $orgFriendlyName -or $_.DisplayName -like $orgMatch)) })
    }

    $getCrmOrgParams = @{ 'OnlineType' = 'Office365' }
    if ($credential) {
        $getCrmOrgParams.Credential = $credential
    }

    if ($null -eq $environment) {
        Write-Output '================================================================================='
        Write-Output 'PowerApps environment not found. A new one will be provisioned.'

        $invalid = 'invalid'

        $location = $invalid
        $cdsLocations = (Get-AdminPowerAppEnvironmentLocations | Select-Object LocationName).LocationName
        while (-not ($location -in $cdsLocations)) {
            $location = (Read-Host -Prompt "Enter the location in which to create the new PowerApps environment: ('help' to see values)")
            if ($location -eq 'help') {
                $cdsLocations
            }
        }

        $currency = $invalid
        $cdsCurrencies = (Get-AdminPowerAppCdsDatabaseCurrencies -Location $location | Select-Object CurrencyName).CurrencyName
        while ($currency -ne '' -and -not ($currency -in $cdsCurrencies)) {
            $currency = (Read-Host -Prompt "Enter the currency to use for the new PowerApps environment: ('help' to see values, blank for default)")
            if ($currency -eq 'help') {
                $cdsCurrencies
            }
        }

        $language = $invalid
        $cdsLanguages = (Get-AdminPowerAppCdsDatabaseLanguages -Location $location | Select-Object LanguageName, LanguageDisplayName)
        while ($language -ne '' -and -not ($language -in $cdsLanguages.LanguageName)) {
            $language = (Read-Host -Prompt "Enter the language name to use for the new PowerApps environment: ('help' to see values, blank for default)")
            if ($language -eq 'help') {
                $cdsLanguages | Format-Table -Property LanguageName, LanguageDisplayName
            }
        }

        Write-Output 'Provisioning PowerApps environment. This may take several minutes.'

        $sleep = 15

        $envParams = @{ 'DisplayName' = $orgFriendlyName; 'EnvironmentSku' = 'Sandbox'; 'ProvisionDatabase' = $true; 'Location' = $location; 'WaitUntilFinished' = $true }
        if ($language.Trim() -ne '') {
            $envParams.LanguageName = $language
        }
        if ($currency.Trim() -ne '') {
            $envParams.CurrencyName = $currency
        }
        $newEnvResult = New-AdminPowerAppEnvironment @envParams
        if (($null -eq $newEnvResult) -or ($newEnvResult.CommonDataServiceDatabaseProvisioningState -ne 'Succeeded')) {
            Write-Warning 'Failed to create to PowerApps environment'
            if ($null -ne $newEnvResult) {
                $newEnvResult
            }
        }
        else {
            $environment = $null
            $retryCount = 0
            while (($null -eq $environment) -and ($retryCount -lt 5)) {
                Start-Sleep -Seconds $sleep
                $environment = (Get-AdminPowerAppEnvironment | Where-Object { ($_.DisplayName -like $orgMatch) })
            }
            Write-Output ("Provisioned PowerApps environment with name: '" + $environment.DisplayName + "'")
        }

        Write-Output 'Waiting for CDS organization provisioning. This may take several minutes.'
        if (-not $credential) {
            $sleep = 120
            Write-Output 'You may be prompted for credentials multiple times while checking the status of the provisioning.'
        }

        while ($null -eq $crmOrg) {
            Start-Sleep -Seconds $sleep
            $crmOrg = (Get-CrmOrganizations @getCrmOrgParams) | Where-Object { $_.FriendlyName -eq $orgFriendlyName }
        }
    }
    else {
        $crmOrgs = Get-CrmOrganizations @getCrmOrgParams
        if ($UseDefaultOrganization -eq $true) {
            $crmOrg = $crmOrgs | Where-Object { $_.FriendlyName -match $orgMatch }
        }
        else {
            $crmOrg = $crmOrgs | Where-Object { $_.FriendlyName -eq $orgFriendlyName }
        }
    }

    Write-Output '================================================================================='
    Write-Output 'Values for PowerAI LCS Add-In:'
    Write-Output ("  CDS organization url:             " + $crmOrg.WebApplicationUrl)
    Write-Output ("  CDS organization ID:              " + $crmOrg.OrganizationId)
}
catch {
    Write-Error $_.Exception.Message
    Write-Warning $_.Exception.StackTrace
    $inner = $_.Exception.InnerException
    while ($null -ne $inner) {
        Write-Output 'Inner Exception:'
        Write-Error $_.Exception.Message
        Write-Warning $_.Exception.StackTrace
        $inner = $inner.InnerException
    }
}
```
---

## <a name="configure-the-azure-setup"></a><span data-ttu-id="10c1d-148">Configurar los ajustes de Azure</span><span class="sxs-lookup"><span data-stu-id="10c1d-148">Configure the Azure setup</span></span>

### <a name="enter-the-dataverse-directory-id-and-the-users-azure-ad-object-id"></a><span data-ttu-id="10c1d-149">Introduzca el id. de directorio de Dataverse y el id. de objeto de Azure AD de usuario</span><span class="sxs-lookup"><span data-stu-id="10c1d-149">Enter the Dataverse directory ID and the user's Azure AD object ID</span></span>

1. <span data-ttu-id="10c1d-150">Especifique el id. de directorio de Dataverse:</span><span class="sxs-lookup"><span data-stu-id="10c1d-150">Enter the Dataverse directory ID:</span></span>

    1. <span data-ttu-id="10c1d-151">Abra el [Azure Portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="10c1d-151">Open the [Azure portal](https://portal.azure.com).</span></span>
    2. <span data-ttu-id="10c1d-152">Inicie sesión con el id. de usuario que se utilizó para crear el entorno de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="10c1d-152">Sign in by using the user ID that was used to create the Dataverse environment.</span></span>
    3. <span data-ttu-id="10c1d-153">Ir a **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-153">Go to **Azure Active Directory**.</span></span>
    4. <span data-ttu-id="10c1d-154">Copie el valor del **Id. de inquilino**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-154">Copy the **Tenant ID** value.</span></span>

2. <span data-ttu-id="10c1d-155">Especifique el id. de objeto de Azure Active Directory (Azure AD) del usuario.</span><span class="sxs-lookup"><span data-stu-id="10c1d-155">Enter the user's Azure Active Directory (Azure AD) object ID:</span></span>

    1. <span data-ttu-id="10c1d-156">En el [Portal de Azure](https://portal.azure.com), vaya a **Usuarios** y busque al usuario por dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="10c1d-156">In the [Azure portal](https://portal.azure.com), go to **Users**, and search for the user by email address.</span></span>
    2. <span data-ttu-id="10c1d-157">Seleccione el nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="10c1d-157">Select the user's name.</span></span>
    3. <span data-ttu-id="10c1d-158">Copie el valor del **Id. de objeto**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-158">Copy the **Object ID** value.</span></span>

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a><span data-ttu-id="10c1d-159">Use Azure Cloud Shell para configurar los recursos de Data Lake de Finance Insights</span><span class="sxs-lookup"><span data-stu-id="10c1d-159">Use Azure Cloud Shell to set up Finance insights Data Lake resources</span></span>

# <a name="use-a-windows-powershell-script"></a>[<span data-ttu-id="10c1d-160">Utilizar un script de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="10c1d-160">Use a Windows PowerShell script</span></span>](#tab/use-a-powershell-script)

<span data-ttu-id="10c1d-161">Se ha proporcionado un script de Windows PowerShell para que pueda configurar fácilmente los recursos de Azure que se describen en [Configurar la exportación a Azure Data Lake](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/configure-export-data-lake).</span><span class="sxs-lookup"><span data-stu-id="10c1d-161">A Windows PowerShell script has been provided, so that you can easily set up the Azure resources that are described in [Configure export to Azure Data Lake](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/configure-export-data-lake).</span></span> <span data-ttu-id="10c1d-162">Si prefiere realizar la configuración manual, omita este procedimiento y continúe con el procedimiento de la sección [Configuración manual](#manual-setup).</span><span class="sxs-lookup"><span data-stu-id="10c1d-162">If you prefer to do manual setup, skip this procedure, and continue with the procedure in the [Manual setup](#manual-setup) section.</span></span>

> [!NOTE]
> <span data-ttu-id="10c1d-163">Siga los pasos que se describen a continuación para ejecutar el script de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="10c1d-163">Follow the steps below to run the PowerShell script.</span></span> <span data-ttu-id="10c1d-164">Es posible que la opción "Probarlo" de la CLI de Azure o la ejecución del script en su PC no funcionen.</span><span class="sxs-lookup"><span data-stu-id="10c1d-164">The Azure CLI "Try it" option, or running the script on your PC may not work.</span></span>

<span data-ttu-id="10c1d-165">Siga estos pasos para configurar Azure mediante el script de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="10c1d-165">Follow these steps to configure Azure by using the Windows PowerShell script.</span></span> <span data-ttu-id="10c1d-166">Debe tener derechos para crear un grupo de recursos de Azure, recursos de Azure y una aplicación de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="10c1d-166">You must have rights to create an Azure resource group, Azure resources, and an Azure AD application.</span></span> <span data-ttu-id="10c1d-167">Para obtener información sobre los permisos necesarios, consulte [Comprobar los permisos de Azure AD](https://docs.microsoft.com/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span><span class="sxs-lookup"><span data-stu-id="10c1d-167">For information about the required permissions, see [Check Azure AD permissions](https://docs.microsoft.com/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span></span>

1. <span data-ttu-id="10c1d-168">En [Azure Portal](https://portal.azure.com), vaya a su suscripción de Azure de destino.</span><span class="sxs-lookup"><span data-stu-id="10c1d-168">In the [Azure portal](https://portal.azure.com), go to your target Azure subscription.</span></span> <span data-ttu-id="10c1d-169">Seleccione el botón **Cloud Shell** a la derecha del campo **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-169">Select the **Cloud Shell** button to the right of the **Search** field.</span></span>
2. <span data-ttu-id="10c1d-170">Seleccione **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-170">Select **PowerShell**.</span></span>
3. <span data-ttu-id="10c1d-171">Cree almacenamiento, si se le solicita que lo haga.</span><span class="sxs-lookup"><span data-stu-id="10c1d-171">Create storage, if you're prompted to do so.</span></span> <span data-ttu-id="10c1d-172">Luego, cargue el script de Windows PowerShell en la sesión.</span><span class="sxs-lookup"><span data-stu-id="10c1d-172">Then upload the Windows PowerShell script to the session.</span></span>
4. <span data-ttu-id="10c1d-173">Ejecute el script.</span><span class="sxs-lookup"><span data-stu-id="10c1d-173">Run the script.</span></span>
5. <span data-ttu-id="10c1d-174">Siga las instrucciones para ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="10c1d-174">Follow the prompts to run the script.</span></span>
6. <span data-ttu-id="10c1d-175">Utilice la información de la salida del script para instalar el complemento **Exportar a Data Lake** en LCS.</span><span class="sxs-lookup"><span data-stu-id="10c1d-175">Use the information from the script output to install the **Export to Data Lake** add-in in LCS.</span></span>
7. <span data-ttu-id="10c1d-176">Utilice la información de la salida del script para habilitar el almacén de entidades en la página **Conexiones de datos** de Finance (**Administración del sistema \> Parámetros del sistema \> Conexiones de datos**).</span><span class="sxs-lookup"><span data-stu-id="10c1d-176">Use the information from the script output to enable the entity store on the **Data connections** page in Finance (**System administration \> System parameters \> Data connections**).</span></span>

### <a name="manual-setup"></a><span data-ttu-id="10c1d-177">Configuración manual</span><span class="sxs-lookup"><span data-stu-id="10c1d-177">Manual setup</span></span>

#### <a name="add-applications-to-the-azure-ad-tenant"></a><span data-ttu-id="10c1d-178">Agregar aplicaciones al inquilino de Azure AD</span><span class="sxs-lookup"><span data-stu-id="10c1d-178">Add applications to the Azure AD tenant</span></span>

1. <span data-ttu-id="10c1d-179">En [Azure Portal](https://portal.azure.com), vaya a **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-179">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**.</span></span>
2. <span data-ttu-id="10c1d-180">Seleccione **Gestionar \> Aplicaciones empresariales**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-180">Select **Manage \> Enterprise applications**.</span></span>
3. <span data-ttu-id="10c1d-181">Busque las siguientes aplicaciones por id. de aplicación.</span><span class="sxs-lookup"><span data-stu-id="10c1d-181">Search for the following applications by app ID.</span></span>

    | <span data-ttu-id="10c1d-182">Solicitud</span><span class="sxs-lookup"><span data-stu-id="10c1d-182">Application</span></span>                              | <span data-ttu-id="10c1d-183">Id. de aplicación</span><span class="sxs-lookup"><span data-stu-id="10c1d-183">App ID</span></span>                               |
    |------------------------------------------|--------------------------------------|
    | <span data-ttu-id="10c1d-184">Microservicios de Microsoft Dynamics ERP</span><span class="sxs-lookup"><span data-stu-id="10c1d-184">Microsoft Dynamics ERP Microservices</span></span>     | <span data-ttu-id="10c1d-185">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="10c1d-185">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
    | <span data-ttu-id="10c1d-186">CDS de microservicios de Microsoft Dynamics ERP</span><span class="sxs-lookup"><span data-stu-id="10c1d-186">Microsoft Dynamics ERP Microservices CDS</span></span> | <span data-ttu-id="10c1d-187">703e2651-d3fc-48f5-942c-74274233dba8</span><span class="sxs-lookup"><span data-stu-id="10c1d-187">703e2651-d3fc-48f5-942c-74274233dba8</span></span> |
    | <span data-ttu-id="10c1d-188">Servicio de autorización de AI Builder</span><span class="sxs-lookup"><span data-stu-id="10c1d-188">AI Builder Authorization Service</span></span>         | <span data-ttu-id="10c1d-189">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span><span class="sxs-lookup"><span data-stu-id="10c1d-189">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span></span> |

<span data-ttu-id="10c1d-190">Si no puede encontrar ninguna de las aplicaciones anteriores, intente los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="10c1d-190">If you can't find any of the preceding applications, try the following steps.</span></span>

1. <span data-ttu-id="10c1d-191">En su máquina local, seleccione el menú **Inicio** y busque **powershell**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-191">On your local machine, select the **Start** menu, and search for **powershell**.</span></span>
2. <span data-ttu-id="10c1d-192">Seleccione y mantenga pulsado (o haga clic derecho) en **Windows PowerShell** y luego seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-192">Select and hold (or right-click) **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="10c1d-193">Ejecute el siguiente comando para instalar el módulo **AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-193">Run the following command to install the **AzureAD** module.</span></span>

    `Install-Module -Name AzureAD`

4. <span data-ttu-id="10c1d-194">Si se requiere un proveedor NuGet para continuar, seleccione **Y** para instalarlo.</span><span class="sxs-lookup"><span data-stu-id="10c1d-194">If a NuGet provider is required to continue, select **Y** to install it.</span></span>
5. <span data-ttu-id="10c1d-195">Si aparece el mensaje "Repositorio no confiable", seleccione **Y** continuar.</span><span class="sxs-lookup"><span data-stu-id="10c1d-195">If an "Untrusted repository" message appears, select **Y** to continue.</span></span>
6. <span data-ttu-id="10c1d-196">Para cada aplicación que deba agregarse, ejecute los siguientes comandos para agregar la aplicación a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="10c1d-196">For each application that must be added, run the following commands to add the application to Azure AD.</span></span> <span data-ttu-id="10c1d-197">Cuando se le solicite, inicie sesión como administrador de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="10c1d-197">When you're prompted, sign in as the Azure AD administrator.</span></span>

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a><span data-ttu-id="10c1d-198">Crear recursos de Azure</span><span class="sxs-lookup"><span data-stu-id="10c1d-198">Create Azure resources</span></span>

> [!NOTE]
> <span data-ttu-id="10c1d-199">Asegúrese de crear los siguientes recursos en la misma instancia de Azure AD que el entorno de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="10c1d-199">Make sure that you create the following resources in the same Azure AD instance as the Dataverse environment.</span></span> <span data-ttu-id="10c1d-200">No puede usar recursos de una instancia de Azure AD diferente.</span><span class="sxs-lookup"><span data-stu-id="10c1d-200">You can't use resources from a different Azure AD instance.</span></span>

1. <span data-ttu-id="10c1d-201">Cree una nueva cuenta de almacenamiento:</span><span class="sxs-lookup"><span data-stu-id="10c1d-201">Create a new storage account:</span></span>

    1. <span data-ttu-id="10c1d-202">En [Azure Portal](https://portal.azure.com), cree una cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="10c1d-202">In the [Azure portal](https://portal.azure.com), create a storage account.</span></span>
    2. <span data-ttu-id="10c1d-203">En el cuadro de diálogo **Crear cuenta de almacenamiento**, establezca los siguientes campo:</span><span class="sxs-lookup"><span data-stu-id="10c1d-203">In the **Create storage account** dialog box, set the following fields:</span></span>

        - <span data-ttu-id="10c1d-204">**Ubicación**: seleccione el centro de datos donde se encuentra su entorno.</span><span class="sxs-lookup"><span data-stu-id="10c1d-204">**Location** – Select the data center where your environment is located.</span></span>
        - <span data-ttu-id="10c1d-205">**Rendimiento**: es recomendable seleccionar **Estándar**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-205">**Performance** – We recommend that you select **Standard**.</span></span>
        - <span data-ttu-id="10c1d-206">**Tipo de cuenta**: debe elegir **StorageV2**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-206">**Account kind** – You must select **StorageV2**.</span></span>

    3. <span data-ttu-id="10c1d-207">En el cuadro de diálogo **Opciones avanzadas**, para la opción **Data Lake Storage Gen2**, seleccione **Habilitar** en la característica **Espacios de nombres jerárquicos**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-207">In the **Advanced options** dialog box, for the **Data Lake storage Gen2** option, select **Enable** under the **Hierarchical namespaces** feature.</span></span> <span data-ttu-id="10c1d-208">Si desactiva esta característica, no puede emplear datos que las aplicaciones de Finance and Operations escriben utilizando servicios como flujos de datos de Power BI.</span><span class="sxs-lookup"><span data-stu-id="10c1d-208">If you disable this feature, you can't consume data that Finance and Operations apps write by using services such as Power BI data flows.</span></span>
    4. <span data-ttu-id="10c1d-209">Seleccione **Revisar y crear**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-209">Select **Review and create**.</span></span> <span data-ttu-id="10c1d-210">Cuando se complete la implementación, el nuevo recurso se mostrará en Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="10c1d-210">When the deployment is completed, the new resource will be shown in the Azure portal.</span></span>
    5. <span data-ttu-id="10c1d-211">Vaya a la cuenta de almacenamiento que creó.</span><span class="sxs-lookup"><span data-stu-id="10c1d-211">Go to the storage account that you created.</span></span>
    6. <span data-ttu-id="10c1d-212">En el menú izquierdo, seleccione **Claves de acceso**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-212">On the left menu, select **Access keys**.</span></span>
    7. <span data-ttu-id="10c1d-213">Copie y guarde la cadena de conexión para **Key1** o **Key2**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-213">Copy and save the connection string for either **Key1** or **Key2**.</span></span>
    8. <span data-ttu-id="10c1d-214">Copie y guarde el nombre de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="10c1d-214">Copy and save the storage account name.</span></span>

2. <span data-ttu-id="10c1d-215">Cree un nuevo almacén de claves:</span><span class="sxs-lookup"><span data-stu-id="10c1d-215">Create a new key vault:</span></span>

    1. <span data-ttu-id="10c1d-216">En [Azure Portal](https://portal.azure.com), cree un almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="10c1d-216">In the [Azure portal](https://portal.azure.com), create a key vault.</span></span>
    2. <span data-ttu-id="10c1d-217">En el cuadro de diálogo **Crear almacén de claves**, en el campo **Ubicación**, seleccione el centro de datos donde se encuentra su entorno.</span><span class="sxs-lookup"><span data-stu-id="10c1d-217">In the **Create key vault** dialog box, in the **Location** field, select the data center where your environment is located.</span></span>
    3. <span data-ttu-id="10c1d-218">Una vez creado el almacén de claves, selecciónelo en la lista y luego seleccione **Secretos**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-218">After key vault is created, select it in the list, and then select **Secrets**.</span></span>
    4. <span data-ttu-id="10c1d-219">Seleccione **Generar/Importar**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-219">Select **Generate/Import**.</span></span>
    5. <span data-ttu-id="10c1d-220">En el cuadro de diálogo **Crear un secreto**, en el campo **Opciones de carga**, seleccione **Manual**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-220">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
    6. <span data-ttu-id="10c1d-221">Introduzca un nombre para el secreto.</span><span class="sxs-lookup"><span data-stu-id="10c1d-221">Enter a name for the secret.</span></span> <span data-ttu-id="10c1d-222">Anote el nombre, porque tendrá que proporcionarlo más tarde.</span><span class="sxs-lookup"><span data-stu-id="10c1d-222">Make a note of the name, because you will have to provide it later.</span></span>
    7. <span data-ttu-id="10c1d-223">En el campo **Valor**, introduzca la cadena de conexión que obtuvo de la cuenta de almacenamiento en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="10c1d-223">In the **Value** field, enter the connection string that you obtained from the storage account in the previous procedure.</span></span>
    8. <span data-ttu-id="10c1d-224">Seleccione **Habilitar** y, a continuación, seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-224">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="10c1d-225">El secreto se crea y se agrega a Key Vault.</span><span class="sxs-lookup"><span data-stu-id="10c1d-225">The secret is created and added to Key Vault.</span></span>
    9. <span data-ttu-id="10c1d-226">Vaya a la **Descripción general de Key Vault** y anote el nombre DNS.</span><span class="sxs-lookup"><span data-stu-id="10c1d-226">Go to the **Key Vault Overview**, and make a note of the DNS name.</span></span>

3. <span data-ttu-id="10c1d-227">Cree y registre una aplicación de Azure AD:</span><span class="sxs-lookup"><span data-stu-id="10c1d-227">Create and register an Azure AD application:</span></span>

    1. <span data-ttu-id="10c1d-228">En [Azure Portal](https://portal.azure.com), vaya a **Azure Active Directory** y luego seleccione **Registros de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-228">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and then select **App registrations**.</span></span>
    2. <span data-ttu-id="10c1d-229">Seleccione **Registro de nueva aplicación** y configure los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="10c1d-229">Select **New application registration**, and set the following fields:</span></span>

        - <span data-ttu-id="10c1d-230">**Nombre**: especifique el nombre de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="10c1d-230">**Name** – Enter the name of the app.</span></span>
        - <span data-ttu-id="10c1d-231">**Tipo de aplicacion**: seleccione **API web**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-231">**Application type** – Select **Web API**.</span></span>
        - <span data-ttu-id="10c1d-232">**Redirigir la configuración de URI**: introduzca la URL de su instancia de Dynamics 365, como `https://yourdynamicsinstance.dynamics.com/auth`.</span><span class="sxs-lookup"><span data-stu-id="10c1d-232">**Redirect URI setup** – Enter the URL for your Dynamics 365 instance, such as, `https://yourdynamicsinstance.dynamics.com/auth`.</span></span>

    3. <span data-ttu-id="10c1d-233">Vaya a la aplicación que acaba de crear, copie y guarde su valor de **Id. de la aplicación (cliente)**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-233">Go to the app that you just created, and copy and save its **Application (client) ID** value.</span></span> <span data-ttu-id="10c1d-234">Tendrá que proporcionar este valor más adelante, cuando configure el almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="10c1d-234">You will have to provide this value later, when you set up the key vault.</span></span>
    4. <span data-ttu-id="10c1d-235">Vaya a **Permisos de API** y siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="10c1d-235">Go to **API permissions**, and follow these steps:</span></span>

        1. <span data-ttu-id="10c1d-236">Seleccione **Agregar un permiso**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-236">Select **Add a permission**.</span></span>
        2. <span data-ttu-id="10c1d-237">Seleccione **Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-237">Select **Azure Key vault**.</span></span>
        3. <span data-ttu-id="10c1d-238">Después de seleccionar los permisos delegados, seleccione **usuario\_interpretación**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-238">After you select delegated permissions, select **user\_impersonation**.</span></span>
        4. <span data-ttu-id="10c1d-239">Seleccione **Agregar permisos**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-239">Select **Add permissions**.</span></span>

    5. <span data-ttu-id="10c1d-240">En el menú de la aplicación, seleccione **Certificados\&secretos** y luego siga estos pasos para crear secretos de Key Vault:</span><span class="sxs-lookup"><span data-stu-id="10c1d-240">On the menu for the app, select **Certificates \& secrets**, and then follow these steps to create Key Vault secrets:</span></span>

        1. <span data-ttu-id="10c1d-241">Seleccione **Nuevo secreto de cliente**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-241">Select **New client secret**.</span></span>
        2. <span data-ttu-id="10c1d-242">En el campo **Descripción de clave**, escriba un nombre.</span><span class="sxs-lookup"><span data-stu-id="10c1d-242">In the **Key Description** field, enter a name.</span></span>
        3. <span data-ttu-id="10c1d-243">Seleccione una duración y luego seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-243">Select a duration, and then select **Add**.</span></span> <span data-ttu-id="10c1d-244">Se genera un secreto en el campo **Valor**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-244">A secret is generated in the **Value** field.</span></span>
        4. <span data-ttu-id="10c1d-245">Copie y guarde el valor secreto.</span><span class="sxs-lookup"><span data-stu-id="10c1d-245">Copy and save the secret value.</span></span>

4. <span data-ttu-id="10c1d-246">Cree secretos de Key Vault:</span><span class="sxs-lookup"><span data-stu-id="10c1d-246">Create Key Vault secrets:</span></span>

    1. <span data-ttu-id="10c1d-247">Vaya al almacén de claves que creó anteriormente y seleccione **Secretos**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-247">Go to the key vault that you created earlier, and select **Secrets**.</span></span>
    2. <span data-ttu-id="10c1d-248">Para cada nombre secreto de la siguiente tabla, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="10c1d-248">For each secret name in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="10c1d-249">Seleccione **Generar/Importar**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-249">Select **Generate/Import**.</span></span>
        2. <span data-ttu-id="10c1d-250">En el cuadro de diálogo **Crear un secreto**, en el campo **Opciones de carga**, seleccione **Manual**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-250">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
        3. <span data-ttu-id="10c1d-251">Cree el nombre secreto y el valor desde la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="10c1d-251">Create the secret name and value from the following table.</span></span>
        4. <span data-ttu-id="10c1d-252">Seleccione **Habilitar** y, a continuación, seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-252">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="10c1d-253">El secreto se crea y se agrega a Key Vault.</span><span class="sxs-lookup"><span data-stu-id="10c1d-253">The secret is created and added to Key Vault.</span></span>

        | <span data-ttu-id="10c1d-254">Nombre secreto</span><span class="sxs-lookup"><span data-stu-id="10c1d-254">Secret name</span></span>                       | <span data-ttu-id="10c1d-255">Valor secreto</span><span class="sxs-lookup"><span data-stu-id="10c1d-255">Secret value</span></span>                                                                                |
        |-----------------------------------|---------------------------------------------------------------------------------------------|
        | <span data-ttu-id="10c1d-256">app-id</span><span class="sxs-lookup"><span data-stu-id="10c1d-256">app-id</span></span>                            | <span data-ttu-id="10c1d-257">El id. de la aplicación que creó anteriormente</span><span class="sxs-lookup"><span data-stu-id="10c1d-257">The app ID of the application that you created earlier</span></span>                                      |
        | <span data-ttu-id="10c1d-258">app-secret</span><span class="sxs-lookup"><span data-stu-id="10c1d-258">app-secret</span></span>                        | <span data-ttu-id="10c1d-259">El secreto de cliente que guardó anteriormente</span><span class="sxs-lookup"><span data-stu-id="10c1d-259">The client secret that you saved earlier</span></span>                                                    |
        | <span data-ttu-id="10c1d-260">storage-account-name</span><span class="sxs-lookup"><span data-stu-id="10c1d-260">storage-account-name</span></span>              | <span data-ttu-id="10c1d-261">El nombre de la cuenta de almacenamiento que creó anteriormente, como **storageaccount1**</span><span class="sxs-lookup"><span data-stu-id="10c1d-261">The name of the storage account that you created earlier, such as **storageaccount1**</span></span>       |
        | <span data-ttu-id="10c1d-262">storage-account-connection-string</span><span class="sxs-lookup"><span data-stu-id="10c1d-262">storage-account-connection-string</span></span> | <span data-ttu-id="10c1d-263">La cadena de conexión que copió de la página **Claves de acceso** de la cuenta de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="10c1d-263">The connection string that you copied from the **Access keys** page for the storage account</span></span> |

5. <span data-ttu-id="10c1d-264">Autorice a la aplicación a acceder al almacén de claves:</span><span class="sxs-lookup"><span data-stu-id="10c1d-264">Authorize the application to access the key vault:</span></span>

    1. <span data-ttu-id="10c1d-265">En [Azure Portal](https://portal.azure.com), abra el almacén de claves que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="10c1d-265">In the [Azure portal](https://portal.azure.com), open the key vault that you created earlier.</span></span>
    2. <span data-ttu-id="10c1d-266">Seleccione las políticas de acceso.</span><span class="sxs-lookup"><span data-stu-id="10c1d-266">Select the access policies.</span></span>
    3. <span data-ttu-id="10c1d-267">Para cada aplicación de la siguiente tabla, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="10c1d-267">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="10c1d-268">Seleccione **Agregar política de acceso** para crear una directiva de acceso.</span><span class="sxs-lookup"><span data-stu-id="10c1d-268">Select **Add Access Policy** to create an access policy.</span></span>
        2. <span data-ttu-id="10c1d-269">En el campo **Permisos secretos**, seleccione los permisos en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="10c1d-269">In the **Secret permissions** field, select the permissions from the following table.</span></span>
        3. <span data-ttu-id="10c1d-270">En el campo **Seleccionar principal**, busque el nombre para mostrar de la aplicación en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="10c1d-270">In the **Select principal** field, search for the application display name from the following table.</span></span>
        4. <span data-ttu-id="10c1d-271">Seleccione **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-271">Select **Select**.</span></span>
        5. <span data-ttu-id="10c1d-272">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-272">Select **Add**.</span></span>
        6. <span data-ttu-id="10c1d-273">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-273">Select **Save**.</span></span>

        | <span data-ttu-id="10c1d-274">Solicitud</span><span class="sxs-lookup"><span data-stu-id="10c1d-274">Application</span></span>                                              | <span data-ttu-id="10c1d-275">Permisos</span><span class="sxs-lookup"><span data-stu-id="10c1d-275">Permissions</span></span> |
        |----------------------------------------------------------|-------------|
        | <span data-ttu-id="10c1d-276">El nombre para mostrar de la nueva aplicación que ha creado</span><span class="sxs-lookup"><span data-stu-id="10c1d-276">The display name of the new application that you created</span></span> | <span data-ttu-id="10c1d-277">Obtener, lista</span><span class="sxs-lookup"><span data-stu-id="10c1d-277">Get, List</span></span>   |
        | <span data-ttu-id="10c1d-278">**Microservicios de Microsoft Dynamics ERP**</span><span class="sxs-lookup"><span data-stu-id="10c1d-278">**Microsoft Dynamics ERP Microservices**</span></span>                 | <span data-ttu-id="10c1d-279">Obtener, lista</span><span class="sxs-lookup"><span data-stu-id="10c1d-279">Get, List</span></span>   |

6. <span data-ttu-id="10c1d-280">Asignar roles para acceder a la cuenta de almacenamiento:</span><span class="sxs-lookup"><span data-stu-id="10c1d-280">Assign roles to access the storage account:</span></span>

    1. <span data-ttu-id="10c1d-281">En [Azure Portal](https://portal.azure.com), abra la cuenta de almacenamiento que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="10c1d-281">In the [Azure portal](https://portal.azure.com), open the storage account that you created earlier.</span></span>
    2. <span data-ttu-id="10c1d-282">Seleccione **Control de acceso (IAM)** y luego seleccione **Asignaciones de roles**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-282">Select **Access Control (IAM)**, and then select **Role Assignments**.</span></span>
    3. <span data-ttu-id="10c1d-283">Seleccione **Agregar, agregar asignación de roles**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-283">Select **Add, Add Role Assignment**.</span></span>
    4. <span data-ttu-id="10c1d-284">Para cada aplicación de la siguiente tabla, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="10c1d-284">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="10c1d-285">Seleccione el rol en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="10c1d-285">Select the role from the following table.</span></span>
        2. <span data-ttu-id="10c1d-286">Deje el campo **Asignar acceso a** establecido en **Entidad de servicio, grupo o usuario de Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-286">Leave the **Assign access to** field set to **Azure AD user, group, or service principal**.</span></span>
        3. <span data-ttu-id="10c1d-287">En el campo **Seleccionar**, introduzca la aplicación desde la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="10c1d-287">In the **Select** field, enter the application from the following table.</span></span>
        4. <span data-ttu-id="10c1d-288">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-288">Select **Save**.</span></span>

        | <span data-ttu-id="10c1d-289">Solicitud</span><span class="sxs-lookup"><span data-stu-id="10c1d-289">Application</span></span>                                              | <span data-ttu-id="10c1d-290">Función</span><span class="sxs-lookup"><span data-stu-id="10c1d-290">Role</span></span>                        |
        |----------------------------------------------------------|-----------------------------|
        | <span data-ttu-id="10c1d-291">El nombre para mostrar de la nueva aplicación que ha creado</span><span class="sxs-lookup"><span data-stu-id="10c1d-291">The display name of the new application that you created</span></span> | <span data-ttu-id="10c1d-292">Propietario</span><span class="sxs-lookup"><span data-stu-id="10c1d-292">Owner</span></span>                       |
        | <span data-ttu-id="10c1d-293">El nombre para mostrar de la nueva aplicación que ha creado</span><span class="sxs-lookup"><span data-stu-id="10c1d-293">The display name of the new application that you created</span></span> | <span data-ttu-id="10c1d-294">Contribuyente</span><span class="sxs-lookup"><span data-stu-id="10c1d-294">Contributor</span></span>                 |
        | <span data-ttu-id="10c1d-295">El nombre para mostrar de la nueva aplicación que ha creado</span><span class="sxs-lookup"><span data-stu-id="10c1d-295">The display name of the new application that you created</span></span> | <span data-ttu-id="10c1d-296">Colaborador de la cuenta de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="10c1d-296">Storage Account Contributor</span></span> |
        | <span data-ttu-id="10c1d-297">El nombre para mostrar de la nueva aplicación que ha creado</span><span class="sxs-lookup"><span data-stu-id="10c1d-297">The display name of the new application that you created</span></span> | <span data-ttu-id="10c1d-298">Propietario de datos de Storage Blob</span><span class="sxs-lookup"><span data-stu-id="10c1d-298">Storage Blob Data Owner</span></span>     |
        | <span data-ttu-id="10c1d-299">**Servicio de autorización de AI Builder**</span><span class="sxs-lookup"><span data-stu-id="10c1d-299">**AI Builder Authorization Service**</span></span>                     | <span data-ttu-id="10c1d-300">Lector de datos de Storage Blob</span><span class="sxs-lookup"><span data-stu-id="10c1d-300">Storage Blob Data Reader</span></span>    |

# <a name="azure-cli"></a>[<span data-ttu-id="10c1d-301">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="10c1d-301">Azure CLI</span></span>](#tab/azure-azure-cli)

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

## <a name="configure-the-entity-store"></a><span data-ttu-id="10c1d-302">Configurar el almacén de entidades</span><span class="sxs-lookup"><span data-stu-id="10c1d-302">Configure the entity store</span></span>

<span data-ttu-id="10c1d-303">Siga estos pasos para configurar el almacén de entidades en su entorno de Finance.</span><span class="sxs-lookup"><span data-stu-id="10c1d-303">Follow these steps to set up the entity store in your Finance environment.</span></span>

1. <span data-ttu-id="10c1d-304">Vaya a **Administración del sistema \> Configuración \> Parámetros del sistema \> Conexiones de datos**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-304">Go to **System administration \> Setup \> System parameters \> Data connections**.</span></span>
2. <span data-ttu-id="10c1d-305">Establezca la opción **Habilitar la integración de Data Lake** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-305">Set the **Enable Data Lake integration** option to **Yes**.</span></span>
3. <span data-ttu-id="10c1d-306">Configure los siguientes campos de Key Vault:</span><span class="sxs-lookup"><span data-stu-id="10c1d-306">Set the following Key Vault fields:</span></span>

    - <span data-ttu-id="10c1d-307">**Id. de la aplicación (cliente)**: introduzca el id. de cliente de la aplicación que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="10c1d-307">**Application (client) ID** – Enter the application client ID that you created earlier.</span></span>
    - <span data-ttu-id="10c1d-308">**Secreto de la aplicación**: introduzca el secreto que guardó para la aplicación que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="10c1d-308">**Application Secret** – Enter the secret that you saved for the application that you created earlier.</span></span>
    - <span data-ttu-id="10c1d-309">**Nombre DNS**: puede encontrar el nombre del sistema de nombres de dominio (DNS) en la página de detalles de la aplicación que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="10c1d-309">**DNS name** – You can find the Domain Name System (DNS) name on the application details page for the application that you created earlier.</span></span>
    - <span data-ttu-id="10c1d-310">**Nombre secreto**: introduzca **storage-account-connection-string**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-310">**Secret name** – Enter **storage-account-connection-string**.</span></span>

## <a name="configure-the-data-lake"></a><span data-ttu-id="10c1d-311">Configurar el lago de datos</span><span class="sxs-lookup"><span data-stu-id="10c1d-311">Configure the data lake</span></span>

<span data-ttu-id="10c1d-312">Siga estos pasos para usar LCS para agregar el complemento de Azure Data Lake al entorno.</span><span class="sxs-lookup"><span data-stu-id="10c1d-312">Follow these steps to use LCS to add the Azure Data Lake add-in to the environment.</span></span>

1. <span data-ttu-id="10c1d-313">Inicie sesión en LCS y luego, donde el nombre del entorno en el lado derecho de la página, seleccione **Todos los detalles**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-313">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="10c1d-314">En la sección **Complementos de entorno**, seleccione **Instalar un nuevo complemento**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-314">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="10c1d-315">Seleccione el complemento **Exportar a Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-315">Select the **Export to Data Lake** add-in.</span></span>
4. <span data-ttu-id="10c1d-316">Introduzca los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="10c1d-316">Enter the following values.</span></span>

    | <span data-ttu-id="10c1d-317">Valor</span><span class="sxs-lookup"><span data-stu-id="10c1d-317">Value</span></span>                                                              | <span data-ttu-id="10c1d-318">Descripción</span><span class="sxs-lookup"><span data-stu-id="10c1d-318">Description</span></span> |
    |--------------------------------------------------------------------|-------------|
    | <span data-ttu-id="10c1d-319">Id. de inquilino de la suscripción de Azure donde se encuentra Key Vault</span><span class="sxs-lookup"><span data-stu-id="10c1d-319">Tenant ID of the Azure Subscription where the Key Vault is located</span></span> | <span data-ttu-id="10c1d-320">El id. de inquilino donde se encuentran la cuenta de almacenamiento, las aplicaciones y los almacenes de claves.</span><span class="sxs-lookup"><span data-stu-id="10c1d-320">The tenant ID where the storage account, apps, and key vaults are located.</span></span> <span data-ttu-id="10c1d-321">Para encontrar este valor, abra [Azure Portal](https://portal.azure.com), vaya a **Azure Active Directory** y copie el valor de **Id. de inquilino**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-321">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="10c1d-322">Proporcione el nombre DNS de su almacén de claves</span><span class="sxs-lookup"><span data-stu-id="10c1d-322">Provide the DNS name of your Key Vault</span></span>                             | <span data-ttu-id="10c1d-323">El nombre DNS del almacén de claves, como `https://customkeyvault.vault.azure.net/`.</span><span class="sxs-lookup"><span data-stu-id="10c1d-323">The DNS name of the key vault, such as `https://customkeyvault.vault.azure.net/`.</span></span> <span data-ttu-id="10c1d-324">(Este valor coincide con el nombre DNS que se utiliza en el almacén de entidades).</span><span class="sxs-lookup"><span data-stu-id="10c1d-324">(This value matches the DNS name that is used in the entity store.)</span></span> |
    | <span data-ttu-id="10c1d-325">Proporcione el secreto que contiene el nombre de la cuenta de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="10c1d-325">Provide the secret that contains the name of the storage account</span></span>   | <span data-ttu-id="10c1d-326">**storage-account-name**</span><span class="sxs-lookup"><span data-stu-id="10c1d-326">**storage-account-name**</span></span> |
    | <span data-ttu-id="10c1d-327">Nombre secreto para el id. de la aplicación que se utilizará para acceder a Data Lake</span><span class="sxs-lookup"><span data-stu-id="10c1d-327">Secret Name for App ID to be used for accessing Data Lake</span></span>          | <span data-ttu-id="10c1d-328">**app-id**</span><span class="sxs-lookup"><span data-stu-id="10c1d-328">**app-id**</span></span> |
    | <span data-ttu-id="10c1d-329">Nombre secreto que se utilizará con el id. de la aplicación</span><span class="sxs-lookup"><span data-stu-id="10c1d-329">Secret name to be used with App ID</span></span>                                 | <span data-ttu-id="10c1d-330">**app-secret**</span><span class="sxs-lookup"><span data-stu-id="10c1d-330">**app-secret**</span></span> |

5. <span data-ttu-id="10c1d-331">Acepte los términos y seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-331">Agree to the terms, and select **Install**.</span></span>

<span data-ttu-id="10c1d-332">El complemento se instalará en unos minutos.</span><span class="sxs-lookup"><span data-stu-id="10c1d-332">The add-in will be installed within a few minutes.</span></span>

## <a name="configure-ai-builder"></a><span data-ttu-id="10c1d-333">Configurar AI Builder</span><span class="sxs-lookup"><span data-stu-id="10c1d-333">Configure AI Builder</span></span>

1. <span data-ttu-id="10c1d-334">Inicie sesión en LCS y abra la página **Detalles del entorno**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-334">Sign in to LCS, and open the **Environment details** page.</span></span>
2. <span data-ttu-id="10c1d-335">Desplácese a la sección **Complementos del entorno**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-335">Scroll to the **Environment add-ins** section.</span></span> <span data-ttu-id="10c1d-336">Debería ver los complementos que ya están instalados en este entorno.</span><span class="sxs-lookup"><span data-stu-id="10c1d-336">You should see the add-ins that are already installed in this environment.</span></span> <span data-ttu-id="10c1d-337">Si el complemento **Exportar a Data Lake** no está entre ellos, configure este complemento.</span><span class="sxs-lookup"><span data-stu-id="10c1d-337">If the **Export to Data Lake** add-in isn't among them, configure this add-in.</span></span>
3. <span data-ttu-id="10c1d-338">Seleccione el complemento **Obtener información**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-338">Select the **Get insights** add-in.</span></span>
4. <span data-ttu-id="10c1d-339">En la página de detalles del complemento **Obtener información**, introduzca los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="10c1d-339">On the **Get insights** add-in details page, enter the following values.</span></span>

    | <span data-ttu-id="10c1d-340">Valor</span><span class="sxs-lookup"><span data-stu-id="10c1d-340">Value</span></span>                                                    | <span data-ttu-id="10c1d-341">Descripción</span><span class="sxs-lookup"><span data-stu-id="10c1d-341">Description</span></span> |
    |----------------------------------------------------------|-------------|
    | <span data-ttu-id="10c1d-342">URL de la organización CDS</span><span class="sxs-lookup"><span data-stu-id="10c1d-342">CDS Organization URL</span></span>                                     | <span data-ttu-id="10c1d-343">URL de la organización de Dataverse de la instancia Dataverse.</span><span class="sxs-lookup"><span data-stu-id="10c1d-343">The Dataverse organization URL of the Dataverse instance.</span></span> <span data-ttu-id="10c1d-344">Para encontrar este valor, abra el [Portal de Power Apps](https://make.powerapps.com), seleccione el botón **Configuración** (símbolo de engranaje) en la esquina superior derecha, seleccione **Configuración avanzada** y copie la URL.</span><span class="sxs-lookup"><span data-stu-id="10c1d-344">To find this value, open the [Power Apps portal](https://make.powerapps.com), select the **Settings** button (gear symbol) in the upper-right upper corner, select **Advanced settings**, and copy the URL.</span></span> <span data-ttu-id="10c1d-345">(La URL termina con "dynamics.com").</span><span class="sxs-lookup"><span data-stu-id="10c1d-345">(The URL ends with "dynamics.com.")</span></span> |
    | <span data-ttu-id="10c1d-346">Id. de organización CDS</span><span class="sxs-lookup"><span data-stu-id="10c1d-346">CDS Org ID</span></span>                                               | <span data-ttu-id="10c1d-347">El id. de entorno de la instancia de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="10c1d-347">The environment ID of the Dataverse instance.</span></span> <span data-ttu-id="10c1d-348">Para encontrar este valor, abra el [Portal de Power Apps](https://make.powerapps.com), seleccione el botón **Configuración** (símbolo de engranaje) en la esquina superior derecha, seleccione **Personalizaciones \> Recursos de desarrollador \> Información de referencia de instancia** y copie el valor **Id.**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-348">To find this value, open the [Power Apps portal](https://make.powerapps.com), select the **Settings** button (gear symbol) in the upper-right upper corner, select **Customizations \> Developer resources \> Instance Reference Information**, and copy the **ID** value.</span></span> |
    | <span data-ttu-id="10c1d-349">Id. de inquilino de CDS (Id. de directorio de AAD)</span><span class="sxs-lookup"><span data-stu-id="10c1d-349">CDS Tenant ID (Directory ID from AAD)</span></span>               | <span data-ttu-id="10c1d-350">El id. de inquilino de la instancia de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="10c1d-350">The tenant ID of the Dataverse instance.</span></span> <span data-ttu-id="10c1d-351">Para encontrar este valor, abra [Azure Portal](https://portal.azure.com), vaya a **Azure Active Directory** y copie el valor de **Id. de inquilino**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-351">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="10c1d-352">Proporcione el id. del objeto de usuario que tenga el rol de administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="10c1d-352">Provide user object ID who has system administrator role</span></span> | <span data-ttu-id="10c1d-353">El id. de objeto de usuario de Azure AD del usuario en Dataverse.</span><span class="sxs-lookup"><span data-stu-id="10c1d-353">The Azure AD user object ID of the user in Dataverse.</span></span> <span data-ttu-id="10c1d-354">Este usuario debe ser un administrador del sistema de la instancia de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="10c1d-354">This user must be a system administrator of the Dataverse instance.</span></span> <span data-ttu-id="10c1d-355">Para encontrar este valor, abra [Azure Portal](https://portal.azure.com), vaya a **Azure Active Directory\> Usuarios**, seleccione el usuario y luego, en la sección **Identidad**, copie el valor del **Id. de objeto**.</span><span class="sxs-lookup"><span data-stu-id="10c1d-355">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory \> Users**, select the user, and then, in the **Identity** section, copy the **Object ID** value.</span></span> |
    | <span data-ttu-id="10c1d-356">¿Es este el entorno de CDS predeterminado para el inquilino?</span><span class="sxs-lookup"><span data-stu-id="10c1d-356">Is this the default CDS environment for the tenant?</span></span>      | <span data-ttu-id="10c1d-357">Si la instancia de Dataverse fue la primera instancia de producción que se creó, seleccione esta casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="10c1d-357">If the Dataverse instance was the first production instance that was created, select this check box.</span></span> <span data-ttu-id="10c1d-358">Si la instancia de Dataverse se creó manualmente, desactive esta casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="10c1d-358">If the Dataverse instance was manually created, clear this check box.</span></span> |

## <a name="feedback-and-support"></a><span data-ttu-id="10c1d-359">Comentarios y soporte técnico</span><span class="sxs-lookup"><span data-stu-id="10c1d-359">Feedback and support</span></span>

<span data-ttu-id="10c1d-360">Envíe un correo electrónico a [Información sobre pagos de clientes (Vista previa)](mailto:fiap@microsoft.com) si está interesado en proporcionar comentarios o necesita ayuda.</span><span class="sxs-lookup"><span data-stu-id="10c1d-360">Please send an email to [Customer payment insights (Preview)](mailto:fiap@microsoft.com) if you are interested in providing feedback or need support.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="10c1d-361">Aviso de privacidad</span><span class="sxs-lookup"><span data-stu-id="10c1d-361">Privacy notice</span></span>

<span data-ttu-id="10c1d-362">Las versiones preliminares (1) pueden utilizar menos privacidad y menos medidas de seguridad que el servicio Dynamics 365 Finance and Operations, (2) no están incluidas en el acuerdo de nivel de servicio para este servicio, (3) no deben utilizarse para procesar datos personales u otros datos que estén sujetos a requisitos de cumplimiento legal o reglamentario, y (4) disponen de soporte limitado.</span><span class="sxs-lookup"><span data-stu-id="10c1d-362">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>
