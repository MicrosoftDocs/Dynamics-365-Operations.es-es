---
title: Configuración de Finance Insights - antes de la versión 10.0.19
description: Este tema explica los pasos de configuración que permitirán que su sistema utilice las capacidades que están disponibles en Finance Insights antes de la versión 10.0.19.
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
ms.openlocfilehash: 6b578962839a34a1e2ce0311f7d8e7ee57a10927
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6357447"
---
# <a name="configuration-for-finance-insights-for-private-preview-preview---before-version-10019"></a>Configuración de Finance insights para la versión preliminar privada (versión preliminar): antes de la versión 10.0.19

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> Los siguientes procedimientos para configurar Finance Insights son válidos para Microsoft Dynamics 365 Finance antes de la versión 10.0.19. Para configurar Finance insights en la versión 10.0.20 y posteriores, consulte [Configuración de Finance Insights (versión preliminar): versiones 10.0.20 y posteriores](configure-for-fin-insites-PubPrvw.md).

Finance Insights combina la funcionalidad de Microsoft Dynamics 365 Finance con Microsoft Dataverse, Azure y AI Builder para proporcionar potentes herramientas de pronóstico para su organización. Este tema explica los pasos de configuración que permitirán que su sistema utilice las capacidades que están disponibles en Finance Insights.

## <a name="deploy-dynamics-365-finance"></a>Implementar Dynamics 365 Finance

implemente los entornos siguiendo estos pasos.

1. En Microsoft Dynamics Lifecycle Services (LCS), cree o actualice un entorno de Dynamics 365 Finance. El entorno requiere la versión de la aplicación 10.0.11/Actualización de plataforma 35 o posterior.
2. El entorno debe ser un entorno de alta disponibilidad (HA) en espacio aislado. (Este tipo de entorno también se conoce como entorno de nivel 2). Para obtener más información, consulte [Planificación de entornos](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).
3. Si está configurando Finance Insights en un entorno de espacio aislado, es posible que deba copiar los datos de producción en ese entorno para que funcionen las predicciones. El modelo de predicción utiliza varios años de datos para generar predicciones. Los datos de la demostración de Contoso no contienen suficientes datos históricos para entrenar adecuadamente el modelo de predicción. 

## <a name="configure-dataverse"></a>Configurar Dataverse

Utilice los siguientes pasos para configurar Dataverse para Finance Insights.

1. Abra la página del entorno en LCS y verifique que la sección **Integración de Power Platform** ya está configurada.
    1. Si ya está configurada, el nombre del entorno de Dataverse vinculado al entorno de Dynamics 365 Finance debe enumerarse. Copie el nombre del entorno de Dataverse.
    2. Si no está configurado, siga estos pasos:
        1. Seleccione e botón **Configuración** en la sección de integración de Power Platform. Puede llevar hasta una hora configurar el entorno.
        2. Si ya está configurado correctamente el entorno de Dataverse, el nombre del entorno de Dataverse vinculado al entorno de Dynamics 365 Finance debe enumerarse. Copie el nombre del entorno de Dataverse.
> [!NOTE]
> Después de completar la configuración del entorno, **NO** seleccione el botón **Vincular a CDS para aplicaciones**. Esto no es necesario para Finance Insights y deshabilitará la capacidad de completar los complementos de entorno requeridos en LCS.

2. Abra el [Centro de administración de Power Platform](https://admin.powerplatform.microsoft.com/) y siga estos pasos para crear un nuevo entorno de Dataverse en el mismo inquilino de Active Directory:

    1. Abra la página **Entornos**.

        [![Página de entornos.](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)

    2. Seleccione el entorno de Dataverse creado anteriormente y luego seleccione **Configuración**.
    3. Seleccione **Recursos \> Todas las configuraciones heredadas**.
    4. En la barra de navegación superior, seleccione **Configuración** y luego seleccione **Personalizaciones**.
    5. Seleccione **Recursos para desarrolladores**.
    6. Copie el valor del **Id. de organización de Dataverse**.
    7. En la barra de direcciones del navegador, anote la URL de la organización de Dataverse. Por ejemplo, la URL puede ser `https://org42b2b3d3.crm.dynamics.com`.

3. Si planea usar la función Previsiones de flujo de efectivo o Previsiones de presupuesto, siga estos pasos para actualizar el límite de anotaciones para su organización a al menos 50 megabytes (MB):

    1. Abra el [portal de Power Apps](https://make.powerapps.com).
    2. Seleccione el entorno que acaba de crear y luego seleccione **Configuración avanzada**.
    3. Seleccione **Configuración \> Configuración de correo electrónico**.
    4. Cambie el valor del campo **Tamaño máximo de archivo** a **51.200**. (El valor se expresa en kilobytes \[KB\]).
    5. Seleccione **Aceptar** para guardar los cambios.

## <a name="configure-the-azure-setup"></a>Configurar los ajustes de Azure

### <a name="enter-the-dataverse-directory-id-and-the-users-azure-ad-object-id"></a>Introduzca el id. de directorio de Dataverse y el id. de objeto de Azure AD de usuario

1. Especifique el id. de directorio de Dataverse:

    1. Abra el [Azure Portal](https://portal.azure.com).
    2. Inicie sesión con el id. de usuario que se utilizó para crear el entorno de Dataverse.
    3. Ir a **Azure Active Directory**.
    4. Copie el valor del **Id. de inquilino**.

2. Especifique el id. de objeto de Azure Active Directory (Azure AD) del usuario.

    1. En el [Portal de Azure](https://portal.azure.com), vaya a **Usuarios** y busque al usuario por dirección de correo electrónico.
    2. Seleccione el nombre del usuario.
    3. Copie el valor del **Id. de objeto**.

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a>Use Azure Cloud Shell para configurar los recursos de Data Lake de Finance Insights

# <a name="use-a-windows-powershell-script"></a>[Utilizar un script de Windows PowerShell](#tab/use-a-powershell-script)

Se ha proporcionado un script de Windows PowerShell para que pueda configurar fácilmente los recursos de Azure que se describen en [Configurar la exportación a Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md). Si prefiere realizar la configuración manual, omita este procedimiento y continúe con el procedimiento de la sección [Configuración manual](#manual-setup).

> [!NOTE]
> Siga los pasos que se describen a continuación para ejecutar el script de PowerShell. Es posible que la opción "Probarlo" de la CLI de Azure o la ejecución del script en su PC no funcionen.

Siga estos pasos para configurar Azure mediante el script de Windows PowerShell. Debe tener derechos para crear un grupo de recursos de Azure, recursos de Azure y una aplicación de Azure AD. Para obtener información sobre los permisos necesarios, consulte [Comprobar los permisos de Azure AD](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).

1. En [Azure Portal](https://portal.azure.com), vaya a su suscripción de Azure de destino. Seleccione el botón **Cloud Shell** a la derecha del campo **Buscar**.
2. Seleccione **PowerShell**.
3. Cree almacenamiento, si se le solicita que lo haga.
4. Vaya a la pestaña **CLI de Azure** y seleccione **Copiar**.  
5. Abra el Bloc de notas y pegue el script de PowerShell. Guarde el archivo como ConfigureDataLake.ps1.
6. Suba el script de Windows PowerShell a la sesión usando la opción de menú para cargar en Cloud Shell.
7. Ejecute el script .\ConfigureDataLake.ps1.
8. Siga las instrucciones para ejecutar el script.
9. Utilice la información de la salida del script para instalar el complemento **Exportar a Data Lake** en LCS.
10. Utilice la información de la salida del script para habilitar el almacén de entidades en la página **Conexiones de datos** de Finance (**Administración del sistema \> Parámetros del sistema \> Conexiones de datos**).

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

1. En su máquina local, seleccione el menú **Inicio** y busque **powershell**.
2. Seleccione y mantenga pulsado (o haga clic derecho) en **Windows PowerShell** y luego seleccione **Ejecutar como administrador**.
3. Ejecute el siguiente comando para instalar el módulo **AzureAD**.

    `Install-Module -Name AzureAD`

4. Si se requiere un proveedor NuGet para continuar, seleccione **Y** para instalarlo.
5. Si aparece el mensaje "Repositorio no confiable", seleccione **Y** continuar.
6. Para cada aplicación que deba agregarse, ejecute los siguientes comandos para agregar la aplicación a Azure AD. Cuando se le solicite, inicie sesión como administrador de Azure AD.

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a>Crear recursos de Azure

> [!NOTE]
> Asegúrese de crear los siguientes recursos en la misma instancia de Azure AD que el entorno de Dataverse. No puede usar recursos de una instancia de Azure AD diferente.

1. Cree una nueva cuenta de almacenamiento:

    1. En [Azure Portal](https://portal.azure.com), cree una cuenta de almacenamiento.
    2. En el cuadro de diálogo **Crear cuenta de almacenamiento**, establezca los siguientes campo:

        - **Ubicación**: seleccione el centro de datos donde se encuentra su entorno.
        - **Rendimiento**: es recomendable seleccionar **Estándar**.
        - **Tipo de cuenta**: debe elegir **StorageV2**.

    3. En el cuadro de diálogo **Opciones avanzadas**, para la opción **Data Lake Storage Gen2**, seleccione **Habilitar** en la característica **Espacios de nombres jerárquicos**. Si desactiva esta característica, no puede emplear datos que las aplicaciones de Finance and Operations escriben utilizando servicios como flujos de datos de Power BI.
    4. Seleccione **Revisar y crear**. Cuando se complete la implementación, el nuevo recurso se mostrará en Azure Portal.
    5. Vaya a la cuenta de almacenamiento que creó.
    6. En el menú izquierdo, seleccione **Claves de acceso**.
    7. Copie y guarde la cadena de conexión para **Key1** o **Key2**.
    8. Copie y guarde el nombre de la cuenta de almacenamiento.

2. Cree un nuevo almacén de claves:

    1. En [Azure Portal](https://portal.azure.com), cree un almacén de claves.
    2. En el cuadro de diálogo **Crear almacén de claves**, en el campo **Ubicación**, seleccione el centro de datos donde se encuentra su entorno.
    3. Una vez creado el almacén de claves, selecciónelo en la lista y luego seleccione **Secretos**.
    4. Seleccione **Generar/Importar**.
    5. En el cuadro de diálogo **Crear un secreto**, en el campo **Opciones de carga**, seleccione **Manual**.
    6. Introduzca un nombre para el secreto. Anote el nombre, porque tendrá que proporcionarlo más tarde.
    7. En el campo **Valor**, introduzca la cadena de conexión que obtuvo de la cuenta de almacenamiento en el procedimiento anterior.
    8. Seleccione **Habilitar** y, a continuación, seleccione **Crear**. El secreto se crea y se agrega a Key Vault.
    9. Vaya a la **Descripción general de Key Vault** y anote el nombre DNS.

3. Cree y registre una aplicación de Azure AD:

    1. En [Azure Portal](https://portal.azure.com), vaya a **Azure Active Directory** y luego seleccione **Registros de aplicaciones**.
    2. Seleccione **Registro de nueva aplicación** y configure los siguientes campos:

        - **Nombre**: especifique el nombre de la aplicación.
        - **Tipo de aplicacion**: seleccione **API web**.
        - **Redirigir la configuración de URI**: introduzca la URL de su instancia de Dynamics 365, como `https://yourdynamicsinstance.dynamics.com/auth`.

    3. Vaya a la aplicación que acaba de crear, copie y guarde su valor de **Id. de la aplicación (cliente)**. Tendrá que proporcionar este valor más adelante, cuando configure el almacén de claves.
    4. Vaya a **Permisos de API** y siga estos pasos:

        1. Seleccione **Agregar un permiso**.
        2. Seleccione **Azure Key Vault**.
        3. Después de seleccionar los permisos delegados, seleccione **usuario\_interpretación**.
        4. Seleccione **Agregar permisos**.

    5. En el menú de la aplicación, seleccione **Certificados\&secretos** y luego siga estos pasos para crear secretos de Key Vault:

        1. Seleccione **Nuevo secreto de cliente**.
        2. En el campo **Descripción de clave**, escriba un nombre.
        3. Seleccione una duración y luego seleccione **Agregar**. Se genera un secreto en el campo **Valor**.
        4. Copie y guarde el valor secreto.

4. Cree secretos de Key Vault:

    1. Vaya al almacén de claves que creó anteriormente y seleccione **Secretos**.
    2. Para cada nombre secreto de la siguiente tabla, siga estos pasos:

        1. Seleccione **Generar/Importar**.
        2. En el cuadro de diálogo **Crear un secreto**, en el campo **Opciones de carga**, seleccione **Manual**.
        3. Cree el nombre secreto y el valor desde la siguiente tabla.
        4. Seleccione **Habilitar** y, a continuación, seleccione **Crear**. El secreto se crea y se agrega a Key Vault.

        | Nombre secreto                       | Valor secreto                                                                                |
        |-----------------------------------|---------------------------------------------------------------------------------------------|
        | app-id                            | El id. de la aplicación que creó anteriormente                                      |
        | app-secret                        | El secreto de cliente que guardó anteriormente                                                    |
        | storage-account-name              | El nombre de la cuenta de almacenamiento que creó anteriormente, como **storageaccount1**       |
        | storage-account-connection-string | La cadena de conexión que copió de la página **Claves de acceso** de la cuenta de almacenamiento |

5. Autorice a la aplicación a acceder al almacén de claves:

    1. En [Azure Portal](https://portal.azure.com), abra el almacén de claves que creó anteriormente.
    2. Seleccione las políticas de acceso.
    3. Para cada aplicación de la siguiente tabla, siga estos pasos:

        1. Seleccione **Agregar política de acceso** para crear una directiva de acceso.
        2. En el campo **Permisos secretos**, seleccione los permisos en la siguiente tabla.
        3. En el campo **Seleccionar principal**, busque el nombre para mostrar de la aplicación en la siguiente tabla.
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

        1. Seleccione el rol en la siguiente tabla.
        2. Deje el campo **Asignar acceso a** establecido en **Entidad de servicio, grupo o usuario de Azure AD**.
        3. En el campo **Seleccionar**, introduzca la aplicación desde la siguiente tabla.
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



## <a name="configure-the-data-lake"></a>Configurar el lago de datos

Siga estos pasos para usar LCS para agregar el complemento de Azure Data Lake al entorno.

1. Inicie sesión en LCS y luego, donde el nombre del entorno en el lado derecho de la página, seleccione **Todos los detalles**.
2. En la sección **Complementos de entorno**, seleccione **Instalar un nuevo complemento**.
3. Seleccione el complemento **Exportar a Data Lake**.
4. Introduzca los valores siguientes.

    | Valor                                                              | Descripción |
    |--------------------------------------------------------------------|-------------|
    | Id. de inquilino de la suscripción de Azure donde se encuentra Key Vault | El id. de inquilino donde se encuentran la cuenta de almacenamiento, las aplicaciones y los almacenes de claves. Para encontrar este valor, abra [Azure Portal](https://portal.azure.com), vaya a **Azure Active Directory** y copie el valor de **Id. de inquilino**. |
    | Proporcione el nombre DNS de su almacén de claves                             | El nombre DNS del almacén de claves, como `https://customkeyvault.vault.azure.net/`. (Este valor coincide con el nombre DNS que se utiliza en el almacén de entidades). |
    | Proporcione el secreto que contiene el nombre de la cuenta de almacenamiento   | **storage-account-name** |
    | Nombre secreto para el id. de la aplicación que se utilizará para acceder a Data Lake          | **app-id** |
    | Nombre secreto que se utilizará con el id. de la aplicación                                 | **app-secret** |

5. Acepte los términos y seleccione **Instalar**.

El complemento se instalará en unos minutos.

## <a name="configure-ai-builder"></a>Configurar AI Builder

1. Inicie sesión en LCS y abra la página **Detalles del entorno**.
2. Desplácese a la sección **Complementos del entorno**. Debería ver los complementos que ya están instalados en este entorno. Si el complemento **Exportar a Data Lake** no está entre ellos, configure este complemento.
3. Seleccione el complemento **Obtener información**.
4. En la página de detalles del complemento **Obtener información**, introduzca los siguientes valores.

    | Valor                                                    | Descripción |
    |----------------------------------------------------------|-------------|
    | URL de la organización CDS                                     | La URL de la organización de Dataverse copiada de lo anterior. |
    | Id. de organización CDS                                               | Ei id. de la organización de Dataverse copiado de lo anterior. |
5. Habiite **Este es el entorno de CDS predeterminado para el inquilino**.

El complemento puede tardar varios minutos en instalarse.
    
## <a name="configure-the-entity-store"></a>Configurar el almacén de entidades

Siga estos pasos para configurar el almacén de entidades en su entorno de Finance.

1. Vaya a **Administración del sistema \> Configuración \> Parámetros del sistema \> Conexiones de datos**.
2. Configure los siguientes campos de Key Vault:

    - **Id. de la aplicación (cliente)**: introduzca el id. de cliente de la aplicación que creó anteriormente.
    - **Secreto de la aplicación**: introduzca el secreto que guardó para la aplicación que creó anteriormente.
    - **Nombre DNS**: puede encontrar el nombre del sistema de nombres de dominio (DNS) en la página de detalles de la aplicación que creó anteriormente.
    - **Nombre secreto**: introduzca **storage-account-connection-string**.
3. Habilite **Habilitar integración de Data Lake**.
4. Seleccione **Probar Azure Key Vault** y verifique que no haya errores.
5. Seleccione **Probar amacenamiento de Azure** y verifique que no haya errores.

## <a name="feedback-and-support"></a>Comentarios y soporte técnico

Envíe un correo electrónico a [Información sobre pagos de clientes (Vista previa)](mailto:fiap@microsoft.com) si está interesado en proporcionar comentarios o necesita ayuda.

## <a name="privacy-notice"></a>Aviso de privacidad

Las versiones preliminares (1) pueden utilizar menos privacidad y menos medidas de seguridad que el servicio Dynamics 365 Finance and Operations, (2) no están incluidas en el acuerdo de nivel de servicio para este servicio, (3) no deben utilizarse para procesar datos personales u otros datos que estén sujetos a requisitos de cumplimiento legal o reglamentario, y (4) disponen de soporte limitado.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
