---
title: Configuración de Finance Insights - versión 10.0.20 y posterior
description: Este tema explica cómo configurar su sistema para que utilice las capacidades que están disponibles en Finance Insights en la versión 10.0.20 y posteriores.
author: ShivamPandey-msft
ms.date: 06/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
ROBOTS: noindex,nofollow
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-06-03
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: 61cc002395ac3bc946fa03a04833a7b6d4820194
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2022
ms.locfileid: "8711615"
---
# <a name="configuration-for-finance-insights---version-10020-and-later"></a>Configuración de Finance Insights - versión 10.0.20 y posterior

[!include [banner](../includes/banner.md)]



Finance Insights combina la funcionalidad de Microsoft Dynamics 365 Finance con Dataverse, Azure y AI Builder para proporcionar potentes herramientas de pronóstico para su organización. Este tema explica cómo configurar Dynamics 365 Finance versión 10.0.20 para que su sistema pueda utilizar las capacidades que están disponibles en Finance Insights.

> [!NOTE]
> Los pasos de configuración que se describen en este tema se aplican solo a la versión 10.0.20 y posteriores de Finance. Para configurar Finance Insights en la versión 10.0.19 y anteriores, consulte [Configuración de Finance Insights: versiones hasta la 10.0.19](configure-for-fin-insites.md).

## <a name="deploy-finance"></a>Implementar Finance

Para implementar los entornos, siga estos pasos.

1. En Microsoft Dynamics Lifecycle Services (LCS), cree o actualice un entorno de Finance. El entorno requiere la versión de la aplicación 10.0.20 o posterior de las aplicaciones de Finance and Operations.
2. El entorno debe ser un entorno de alta disponibilidad (HA) en espacio aislado. (Este tipo de entorno también se conoce como entorno de nivel 2). Para obtener más información, consulte [Planificación de entornos](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).
3. Si está configurando Finance Insights en un entorno de espacio aislado, es posible que deba copiar los datos de producción en ese entorno para que funcionen las predicciones. El modelo de predicción utiliza varios años de datos para generar predicciones. Los datos de la demostración de Contoso no contienen suficientes datos históricos para entrenar adecuadamente el modelo de predicción. 

## <a name="configure-dataverse"></a>Configurar Dataverse

Siga estos pasos para configurar Dataverse para Finance Insights.

1. En LCS, abra la página del entorno y verifique que la sección **Integración de Power Platform** ya está configurada.

    - Si ya está configurada, el nombre del entorno de Dataverse vinculado al entorno de Finance debe enumerarse.
    - Si aún no está configurado, siga estos pasos:

        1. En la sección **Integración de Power Platform**, seleccione **Configuración**. La configuración del entorno puede tardar hasta una hora.
        2. Si ya está configurado correctamente el entorno de Dataverse, el nombre del entorno de Dataverse vinculado al entorno de Finance debe enumerarse.

        > [!NOTE]
        > Después de completar la configuración del entorno, **no** seleccione **Enlace a CDS para aplicaciones**. Este botón no es necesario para Finance Insights. Si lo selecciona, no podrá configurar los complementos de entorno necesarios en LCS.

## <a name="configure-azure"></a>Configurar Azure

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a>Use Azure Cloud Shell para configurar los recursos de Data Lake de Finance Insights

# <a name="use-a-windows-powershell-script"></a>[Utilizar un script de Windows PowerShell](#tab/use-a-powershell-script)

Se ha proporcionado un script de Windows PowerShell para que pueda configurar fácilmente los recursos de Azure que se describen en [Configurar la exportación a Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md). Si prefiere realizar la configuración manualmente, omita este procedimiento y, en su lugar, complete el procedimiento de la sección [Configuración manual](#manual-setup).

> [!NOTE]
> Utilice el siguiente procedimiento para ejecutar el script de Windows PowerShell. Es posible que la configuración no funcione si utiliza la opción **Probarlo** en la CLI de Azure o si ejecuta el script en su computadora.

Siga estos pasos para usar el script de Windows PowerShell para configurar Azure. Debe tener derechos para crear un grupo de recursos de Azure, recursos de Azure y una aplicación de Azure AD. Para obtener información sobre los permisos necesarios, consulte [Comprobar los permisos de Azure AD](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).

1. En [Azure Portal](https://portal.azure.com), vaya a su suscripción de Azure de destino.
2. Seleccione **Cloud Shell** a la derecha del campo **Buscar**.
3. Seleccione **PowerShell**.
4. Cree almacenamiento si se le solicita que lo haga.
5. En la pestaña **CLI de Azure**, seleccione **Copiar**.
6. En el Bloc de notas, abra un archivo nuevo y péguelo en el script de Windows PowerShell.
7. Guarde el archivo como **ConfigureDataLake.ps1**.
8. Suba el script de Windows PowerShell a la sesión usando la opción de menú para cargar en Cloud Shell.
9. Ejecute el script **.\ConfigureDataLake.ps1**.
10. Siga las instrucciones para ejecutar el script.
11. Utilice la información de la salida del script para instalar el complemento Exportar a Data Lake en LCS.

### <a name="manual-setup"></a>Configuración manual

#### <a name="add-applications-to-the-azure-ad-tenant"></a>Agregar aplicaciones al inquilino de Azure AD

1. En [Azure Portal](https://portal.azure.com), vaya a **Azure Active Directory**.
2. Seleccione **Gestionar \> Aplicaciones empresariales**.
3. Busque las siguientes aplicaciones por id. de aplicación.

    | Solicitud                              | Id. de aplicación                               |
    |------------------------------------------|--------------------------------------|
    | Microservicios de Microsoft Dynamics ERP     | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |
    | CDS de microservicios de Microsoft Dynamics ERP | 703e2651-d3fc-48f5-942c-74274233dba8 |
    | Servicio de autorización de AI Builder         | ad40333e-9910-4b61-b281-e3aeeb8c3ef3 |

Si no puede encontrar ninguna de las aplicaciones anteriores, intente los siguientes pasos.

1. En su equipo local, en el menú **Inicio**, busque **powershell**.
2. Seleccione y mantenga pulsado (o haga clic derecho) en **Windows PowerShell** y luego seleccione **Ejecutar como administrador**.
3. Ejecute el siguiente comando para instalar el módulo **AzureAD**.

    `Install-Module -Name AzureAD`

4. Si se requiere un proveedor NuGet para continuar, seleccione **Y** para instalarlo.
5. Si recibe un mensaje "Repositorio no confiable", seleccione **Y** para continuar.
6. Para cada aplicación que deba agregarse, ejecute los siguientes comandos para agregar la aplicación a Azure AD. Cuando se le solicite, inicie sesión como administrador de Azure AD.

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a>Crear recursos de Azure

> [!NOTE]
> Asegúrese de crear los siguientes recursos en la misma instancia de Azure AD en la que está el entorno de Dataverse. No puede usar recursos de una instancia de Azure AD diferente.

1. Cree una cuenta de almacenamiento:

    1. En [Azure Portal](https://portal.azure.com), cree una cuenta de almacenamiento.
    2. En el cuadro de diálogo **Crear cuenta de almacenamiento**, establezca los siguientes campo:

        - **Ubicación**: seleccione el centro de datos donde se encuentra su entorno.
        - **Rendimiento**: es recomendable seleccionar **Estándar**.
        - **Tipo de cuenta**: debe elegir **StorageV2**.

    3. En el cuadro de diálogo **Opciones avanzadas**, para la opción **Data Lake Storage Gen2**, seleccione **Habilitar** en la característica **Espacios de nombres jerárquicos**. Si no activa esta característica, no puede emplear datos que las aplicaciones de Finanzas y Operaciones escriben utilizando servicios como flujos de datos de Power BI.
    4. Seleccione **Revisar y crear**. Cuando se completa la implementación, el nuevo recurso se muestra en Azure Portal.
    5. Vaya a la cuenta de almacenamiento que creó.
    6. En el menú izquierdo, seleccione **Claves de acceso**.
    7. Copie y guarde el nombre de la cuenta de almacenamiento. Tendrá que proporcionar este valor más adelante, cuando configure los secretos del almacén de claves.

2. Cree un almacén de claves:

    1. En [Azure Portal](https://portal.azure.com), cree un almacén de claves.
    2. En el cuadro de diálogo **Crear almacén de claves**, en el campo **Ubicación**, seleccione el centro de datos donde se encuentra su entorno.
    3. Una vez creado el almacén de claves, vaya a **Descripción general de Key Vault** y copie y guarde el nombre DNS. Tendrá que proporcionar este valor más adelante, cuando configure el complemento Data Lake.

3. Cree y registre una aplicación de Azure AD:

    1. En [Azure Portal](https://portal.azure.com), vaya a **Azure Active Directory** y luego seleccione **Registros de aplicaciones**.
    2. Seleccione **Registro de nueva aplicación** y configure los siguientes campos:

        - **Nombre**: especifique el nombre de la aplicación.
        - **Tipo de aplicacion**: seleccione **API web**.
        - **Redirigir la configuración de URI**: introduzca la URL de su instancia de Dynamics 365, como `https://yourdynamicsinstance.dynamics.com/auth`.

    3. Vaya a la aplicación que acaba de crear, copie y guarde su valor de **Id. de la aplicación (cliente)**. Tendrá que proporcionar este valor más adelante, cuando configure los secretos del almacén de claves.
    4. Vaya a **Permisos de API** y siga estos pasos:

        1. Seleccione **Agregar un permiso**.
        2. Seleccione **Azure Key Vault**.
        3. Después de seleccionar los permisos delegados, seleccione **usuario\_interpretación**.
        4. Seleccione **Agregar permisos**.

    5. En el menú de la aplicación, seleccione **Certificados\&secretos** y luego siga estos pasos para crear secretos de Key Vault:

        1. Seleccione **Nuevo secreto de cliente**.
        2. En el campo **Descripción de clave**, escriba un nombre.
        3. Seleccione una duración y luego seleccione **Agregar**. Se genera un secreto en el campo **Valor**.
        4. Copie y guarde el valor secreto de cliente. Tendrá que proporcionar este valor más adelante, cuando configure los secretos del almacén de claves.

4. Cree secretos de Key Vault:

    1. Vaya al almacén de claves que creó anteriormente y seleccione **Secretos**.
    2. Para cada nombre secreto de la siguiente tabla, siga estos pasos:

        1. Seleccione **Generar/Importar**.
        2. En el cuadro de diálogo **Crear un secreto**, en el campo **Opciones de carga**, seleccione **Manual**.
        3. Cree el nombre secreto y el valor desde la tabla.
        4. Seleccione **Habilitar** y, a continuación, seleccione **Crear**. El secreto se crea y se agrega a Key Vault.

        | Nombre secreto                       | Valor secreto                                                                                 |
        |-----------------------------------|----------------------------------------------------------------------------------------------|
        | app-id                            | El id. de la aplicación que creó anteriormente.                                      |
        | app-secret                        | El secreto de cliente que guardó anteriormente.                                                    |
        | storage-account-name              | El nombre de la cuenta de almacenamiento que creó anteriormente, como **storageaccount1**.       |

5. Autorice a la aplicación a acceder al almacén de claves:

    1. En [Azure Portal](https://portal.azure.com), abra el almacén de claves que creó anteriormente.
    2. Seleccione las políticas de acceso.
    3. Para cada aplicación de la siguiente tabla, siga estos pasos:

        1. Seleccione **Agregar política de acceso** para crear una directiva de acceso.
        2. En el campo **Permisos secretos**, seleccione los permisos en la tabla.
        3. En el campo **Seleccionar principal**, busque el nombre para mostrar de la aplicación en la tabla.
        4. Seleccione **Seleccionar**.
        5. Seleccione **Agregar**.
        6. Seleccione **Guardar**.

        | Solicitud                                              | Permisos |
        |----------------------------------------------------------|-------------|
        | El nombre para mostrar de la nueva aplicación que ha creado | Obtener, lista   |
        | **Microservicios de Microsoft Dynamics ERP**                 | Obtener, lista   |

6. Asignar roles para acceder a la cuenta de almacenamiento:

    1. En [Azure Portal](https://portal.azure.com), abra la cuenta de almacenamiento que creó anteriormente.
    2. Seleccione **Control de acceso (IAM)** y luego seleccione **Asignaciones de roles**.
    3. Seleccione **Agregar, agregar asignación de roles**.
    4. Para cada aplicación de la siguiente tabla, siga estos pasos:

        1. Seleccione el rol de la tabla.
        2. Deje el campo **Asignar acceso a** establecido en **Entidad de servicio, grupo o usuario de Azure AD**.
        3. En el campo **Seleccionar**, introduzca la aplicación desde la tabla.
        4. Seleccione **Guardar**.

        | Solicitud                                              | Función                        |
        |----------------------------------------------------------|-----------------------------|
        | El nombre para mostrar de la nueva aplicación que ha creado | Propietario                       |
        | El nombre para mostrar de la nueva aplicación que ha creado | Contribuyente                 |
        | El nombre para mostrar de la nueva aplicación que ha creado | Colaborador de la cuenta de almacenamiento |
        | El nombre para mostrar de la nueva aplicación que ha creado | Propietario de datos de Storage Blob     |
        | **Servicio de autorización de AI Builder**                     | Lector de datos de Storage Blob    |

# <a name="azure-cli"></a>[Azure CLI](#tab/azure-azure-cli)

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

## <a name="configure-the-export-to-data-lake-add-in"></a>Configurar el complemento Exportar a Data Lake

Siga estos pasos para usar LCS para agregar el complemento Exportar a Data Lake al entorno.

1. Inicie sesión en LCS y luego, donde el nombre del entorno en el lado derecho de la página, seleccione **Todos los detalles**.
2. En la sección **Complementos de entorno**, seleccione **Instalar un nuevo complemento**.
3. Seleccione el complemento **Exportar a Data Lake**.
4. Introduzca los valores siguientes.

    | Valor                                                              | Descripción |
    |--------------------------------------------------------------------|-------------|
    | Id. de inquilino de la suscripción de Azure donde se encuentra Key Vault | El id. de inquilino donde se encuentran la cuenta de almacenamiento, las aplicaciones y los almacenes de claves. Para obtener este valor, abra [Azure Portal](https://portal.azure.com), vaya a **Azure Active Directory** y copie el valor de **Id. de inquilino**. |
    | Proporcione el nombre DNS de su almacén de claves                             | El nombre DNS del almacén de claves, como `https://customkeyvault.vault.azure.net/`. |
    | Proporcione el secreto que contiene el nombre de la cuenta de almacenamiento   | **storage-account-name** |
    | Nombre secreto para el id. de la aplicación que se utilizará para acceder a Data Lake          | **app-id** |
    | Nombre secreto para el secreto del cliente de la aplicación                                  | **app-secret** |

5. Acepte los términos y luego seleccione **Instalar**.

El complemento se instalará en unos minutos.

## <a name="configure-the-finance-insights-add-in"></a>Configurar el complemento Finance Insights

> [!NOTE]
> Si instaló anteriormente el complemento Get insights, desinstálelo antes de completar el siguiente procedimiento.

Siga estos pasos para instalar el complemento Finance Insights.

1. Inicie sesión en LCS y luego, donde el nombre del entorno en el lado derecho de la página, seleccione **Todos los detalles**.
2. En la sección **Complementos de entorno**, seleccione **Instalar un nuevo complemento**.
3. Seleccione el complemento **Finance Insights**.
4. Acepte los términos y luego seleccione **Instalar**.

El complemento puede tardar varios minutos en instalarse.

## <a name="feedback-and-support"></a>Comentarios y soporte técnico

Si está interesado en proporcionar comentarios o si necesita asistencia, envíe un correo elecrónico a [Finance Insights](mailto:fiap@microsoft.com).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
