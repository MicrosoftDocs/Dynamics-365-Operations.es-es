---
title: Implementar unidades de escalado en el perímetro en hardware personalizado mediante LBD
description: Este artículo explica cómo aprovisionar unidades de escalado perimetrales locales mediante el uso de hardware personalizado y la implementación que se basa en datos comerciales locales (LBD).
author: Mirzaab
ms.date: 01/24/2022
ms.topic: article
ms.prod: dynamics-365
ms.service: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 794de8c0d77949789e4046418ac2b55dba1bee02
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882761"
---
# <a name="deploy-edge-scale-units-on-custom-hardware-using-lbd"></a>Implementar unidades de escalado en el perímetro en hardware personalizado mediante LBD

[!include [banner](../includes/banner.md)]

Las unidades de escalado perimetrales juegan un papel importante en la topología híbrida distribuida para la gestión de la cadena de suministro. En la topología híbrida, puede distribuir cargas de trabajo entre su centro de nube de Supply Chain Management y unidades de escalado adicionales en la nube o en el perímetro.

Las unidades de escalado perimetrales se pueden implementar mediante la creación de datos comerciales locales (LBD) [entorno local](../../fin-ops-core/dev-itpro/deployment/on-premises-deployment-landing-page.md) y luego configurándolo para que funcione como una unidad de escala en su topología híbrida distribuida para la gestión de la cadena de suministro. Esto se logra asociando el entorno de LBD local con un entorno de Supply Chain Management en la nube, que se ha configurado para funcionar como un centro de conectividad.  

Este artículo describe cómo configurar un entorno LBD local como una unidad de escala perimetral y luego asociarlo con un centro de conectividad.

## <a name="infrastructure-considerations"></a>Consideraciones sobre la infraestructura

Las unidades de escala perimetral se ejecutan en entornos locales, por lo que los requisitos de infraestructura son bastante similares. Sin embargo, hay ciertas diferencias que deben tenerse en cuenta:

- Las unidades de escala perimetral no utilizan Financial Reporting, por lo que no requieren nodos de Financial Reporting.
- Las cargas de trabajo de fabricación y almacenamiento no requieren un uso intensivo de cómputo, así que considere dimensionar su poder de cómputo para los nodos AOS en consecuencia.

## <a name="deployment-overview"></a>Información general de implementación

Esta es una visión general de los pasos de implementación.

1. **Habilite una ranura LBD en su proyecto LBD en Microsoft Dynamics Lifecycle Services (LCS).**

1. **Configure e implemente un entorno LBD con una base de datos *vacía*.**

    Utilice LCS para implementar el entorno LBD con la topología más reciente y una base de datos vacía. Para obtener más información, consulte la sección [Configurar e implementar un entorno LBD con una base de datos vacía](#set-up-deploy) más adelante en este artículo. Debe utilizar la versión 10.0.21 o posterior de Supply Chain Management en todos los entornos de centros de conectividad y unidades de escalado.

1. **Cargue los paquetes de destino en los activos del proyecto LBD en LCS.**

    Prepare paquetes de aplicaciones, plataformas y personalización que utilice en el centro de conectividad y la unidad de escala perimetral. Para obtener más información, consulte la sección [Cargar los paquetes de destino en los activos del proyecto LBD en LCS](#upload-packages) más adelante en este artículo.

1. **Dar servicio al entorno LBD con los paquetes de destino.**

    Este paso garantiza que se implementen la misma compilación y personalizaciones en el centro de conectividad y el radio. Para obtener más información, consulte la sección [Dar servicio al entorno LBD con paquetes de destino](#service-target-packages) más adelante en este artículo.

1. **Complete la configuración de la unidad de escalado y la asignación de carga de trabajo.**

    Para obtener más información, consulte la sección [Asignar su unidad de escala de borde LBD a un centro de conectividad](#assign-edge-to-hub) más adelante en este artículo.

En las secciones restantes de este artículo se proporcionan más detalles acerca de cómo completar estos pasos.

## <a name="set-up-and-deploy-an-lbd-environment-with-an-empty-database"></a><a name="set-up-deploy"></a>Configure e implemente un entorno LBD con una base de datos vacía.

Este paso crea un entorno funcional LBD. Sin embargo, el entorno no tiene necesariamente las mismas versiones de plataforma y aplicación que el entorno del centro de conectividad. Además, todavía le faltan las personalizaciones y aún no se ha habilitado para funcionar como una unidad de escalado.

1. Siga las instrucciones en [Configurar e implementar entornos locales (Platform update 41 y posteriores)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md). Debe utilizar la versión 10.0.21 o posterior de Supply Chain Management en todos los entornos de centros de conectividad y unidades de escalado. Además, debe utilizar la versión 2.12.0 o posterior de los scripts de infraestructura. 

    > [!IMPORTANT]
    > Leer el resto de esta sección **antes** de completar los pasos de ese artículo.

1. Antes de describir su configuración en la infraestructura\\ConfigTemplate.xml, ejecute el siguiente script:

    ```powershell
    .\Configure-ScriptsForEdgeScaleUnits.ps1 -ConfigurationFilePath .\ConfigTemplate.xml
    ```

    > [!NOTE]
    > Este script eliminará cualquier configuración que no sea necesaria para implementar unidades de escalado perimetrales.

1. Configure una base de datos que contenga datos vacíos, como se describe en [Configurar bases de datos](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb). Utilice el archivo data.bak vacío para este paso.
1. Una vez que haya completado el paso [Configurar bases de datos](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb), ejecute el siguiente script para configurar la base de datos de Scale Unit Alm Orchestrator.

    > [!NOTE]
    > No configure la base de datos de Financial Reporting durante el paso [Configurar bases de datos](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb).

    ```powershell
    .\Initialize-Database.ps1 -ConfigurationFilePath .\ConfigTemplate.xml -ComponentName EdgeScaleUnit
    ```

    El script Initialize-Database.ps1 realiza las siguientes acciones:

    1. Crea una base de datos vacía que se llame **ScaleUnitAlmDb**.
    2. Asigne los usuarios a los roles de la base de datos, según la siguiente tabla.

        | Usuario            | Tipo | Rol de base de datos |
        |-----------------|------|---------------|
        | svc-LocalAgent$ | gMSA | db\_owner     |

1. Siga las instrucciones de [Configurar e implementar entornos locales (Platform update 41 y posteriores)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md).
1. Una vez que haya completado el paso [Configurar AD FS](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb), siga estos pasos:

    1. Cree una nueva aplicación de Servicios de federación de Active Directory (AD FS) que permita que el servicio Alm Orchestration se comunique con su Application Object Server (AOS).

        ```powershell
        # Host URL is your DNS record\host name for accessing the AOS
        .\Create-ADFSServerApplicationForEdgeScaleUnits.ps1 -ConfigurationFilePath .\ConfigTemplate.xml -HostUrl 'https://ax.d365ffo.onprem.contoso.com'
        ```

    1. Cree una nueva aplicación de Azure Active Directory (Azure AD) que permita que el servicio Alm Orchestration se comunique con el servicio de gestión de unidades de escala.

        ```powershell
        # Example .\Create-SumAADApplication.ps1 -ConfigurationFilePath ..\ConfigTemplate.xml -TenantId '6240a19e-86f1-41af-91ab-dbe29dbcfb95' -ApplicationDisplayName 'EdgeAgent-SUMCommunication-EN01'
        .\Create-SumAADApplication.ps1 -ConfigurationFilePath '<Path of the ConfigTemplate.xml file>' `
                                       -TenantId '<ID of the tenant where your cloud hub is deployed>' `
                                       -ApplicationDisplayName '<Whichever name you want the Azure AD app to have>'
        ```

1. Siga las instrucciones de [Configurar e implementar entornos locales (Platform update 41 y posteriores)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md). Cuando deba ingresar la configuración para el agente local, asegúrese de habilitar las características de unidades de escala perimetral y proporcionar todos los parámetros requeridos.

    ![Habilitar características de unidad de escala perimetral](media/EnableEdgeScaleUnitFeatures.png "Habilitar características de unidad de escala perimetral.")

1. Antes de implementar su entorno desde LCS, configure el script previo a la implementación. Para más información, consulte [Scripts para fases previas y posteriores a la implementación de agente local](../../fin-ops-core/dev-itpro/lifecycle-services/pre-post-scripts.md).

    1. Copie el script Configure-CloudAndEdge.ps1 de la carpeta **ScaleUnit** en **Scripts de infraestructura** a la carpeta **Scripts** en el recurso compartido de almacenamiento de archivos del agente que se configuró en el entorno. Una ruta típica es \\\\lbdiscsi01\\agent\\Scripts.
    2. Cree el script **PreDeployment.ps1** que invocará los scripts utilizando los parámetros requeridos. La secuencia de comandos previa a la implementación debe colocarse en la carpeta **Scripts** en el recurso compartido de almacenamiento de archivos del agente. De lo contrario, no se puede ejecutar. Una ruta típica es \\\\lbdiscsi01\\agent\\Scripts\\PreDeployment.ps1.

        El contenido del script PreDeployment.ps1 se parecerá al siguiente ejemplo.

        ```powershell
        $agentShare = '\\lbdiscsi01\agent'
        
        Write-Output "AgentShare is set to $agentShare" 
        . $PSScriptRoot\Configure-CloudAndEdge.ps1 -AgentShare $agentShare -InstanceId '@A'
        ```

        > [!NOTE]
        > El parámetro InstanceId debe tener solo dos caracteres. El primer carácter es @ y el segundo puede ser cualquier letra mayúscula del alfabeto inglés.
        >
        > - Valores válidos:
        >   - @D
        >   - @X
        > - Valores no válidos:
        >   - @a
        >   - @4
        >   - @#

1. Implemente el entorno utilizando la topología base más reciente disponible.
1. Una vez implementado su entorno, siga estos pasos:

    1. Ejecute los siguientes comandos SQL en su base de datos empresarial (AXDB).

        ```sql
        ALTER TABLE dbo.NUMBERSEQUENCETABLE ENABLE CHANGE_TRACKING WITH (TRACK_COLUMNS_UPDATED = ON)
        delete from NumberSequenceTable
        delete from NumberSequenceReference
        delete from NumberSequenceScope
        delete from FeatureManagementMetadata
        delete from FeatureManagementState
        delete from SysFeatureStateV0
        ```

    1. Aumente la sesión por lotes máxima simultánea a un valor superior a 4.

        ```sql
        Update batchserverconfig set maxbatchsessions = '<Replace with number of concurrent batch tasks you want>'
        ```

    1. Verifique que el seguimiento de cambios se haya habilitado en su base de datos comercial (AXDB).

        1. Abra SQL Server Management Studio (SSMS).
        1. Mantenga seleccionado (o haga clic con el botón derecho) su base de datos empresarial (AXDB) y luego seleccione **Propiedades**.
        1. En la ventana que aparece, seleccione **Change Tracking** y realice los siguientes ajustes:

            - **Change Tracking:** *True*
            - **Periodo de retención:** *7*
            - **Unidades de retención:** *Días*
            - **Limpieza automática:** *True*

    1. Agregue el ID de la aplicación AD FS que creó anteriormente (mediante el script Create-ADFSServerApplicationForEdgeScaleUnits.ps1) a la tabla de aplicaciones de Azure AD en su unidad de escala. Puede completar este paso manualmente a través de la interfaz de usuario (UI). Alternativamente, puede completarlo a través de la base de datos utilizando el siguiente script.

        ```sql
        DECLARE @ALMOrchestratorId NVARCHAR(76) = '<Replace with the ADFS Application ID created in a previous step>';

        IF NOT EXISTS (SELECT TOP 1 1 FROM SysAADClientTable WHERE AADClientId = @ALMOrchestratorId)
        BEGIN
            INSERT INTO SysAADClientTable (AADClientId, UserId, Name, ModifiedBy, CreatedBy)
            VALUES (@ALMOrchestratorId, 'ScaleUnitManagement', 'Scale Unit Management', 'Admin', 'Admin');
        END
        ```

## <a name="set-up-an-azure-key-vault-and-an-azure-ad-application-to-enable-communication-between-scale-units"></a><a name="set-up-keyvault"></a>Configure un almacén de claves de Azure y una aplicación de Azure AD para permitir la comunicación entre unidades de escala

1. Una vez implementado su entorno, cree una aplicación de Azure AD adicional para permitir una comunicación fiable entre su centro de conectividad y la unidad de escala.

    ```powershell
    .\Create-SpokeToHubAADApplication.ps1 -ConfigurationFilePath '<Path of the ConfigTemplate.xml file>' `
                                          -TenantId '<ID of the tenant where your cloud hub is deployed>' `
                                          -ApplicationDisplayName '<Whichever name you want the Azure AD app to have>'
    ```

1. Después de crear la aplicación, debe crear un secreto de cliente y guardar la información en un almacén de claves de Azure. Además, debe otorgar acceso a la aplicación de Azure AD que se creó, para que pueda recuperar los secretos que están almacenados en el almacén de claves. Para su comodidad, el siguiente script realizará automáticamente todas las acciones necesarias.

    ```powershell
    .\Create-SpokeToHubAADAppSecrets.ps1 -ConfigurationFilePath '<Path of the ConfigTemplate.xml file>' `
                                         -TenantId '<ID of the tenant where your cloud hub is deployed>' `
                                         -SubscriptionName '<Any subscription within your tenant>' `
                                         -ResourceGroupName '<Any resource group within your subscription>' `
                                         -KeyVaultName '<Any key vault within your resource group>' `
                                         -Location '<Any Azure location where Azure Key Vault is available>' `
                                         -LCSEnvironmentId '<The LCS environment ID of your deployed scale unit>' `
    ```

    > [!NOTE]
    > Si no hay almacén de claves que tenga el valor **KeyVaultName** expecificado, el script crea uno automáticamente.

1. Añada el ID de la aplicación de Azure AD que acaba de crear (al usar el script Create-SpokeToHubAADApplication.ps1) a la tabla de aplicaciones de Azure AD en su centro de conectividad. Puede completar este paso manualmente a través de la interfaz de usuario (UI).

## <a name="upload-target-packages-into-lbd-project-assets-in-lcs"></a><a name="upload-packages"></a>Cargue los paquetes de destino en los activos del proyecto LBD en LCS.

Este paso prepara la versión de la aplicación, la versión de la plataforma y las personalizaciones que se transferirán al entorno de su unidad de escalado LBD.

1. Cargue el mismo paquete combinado de aplicación/plataforma que se aplicó al entorno del centro de conectividad en la biblioteca de activos del proyecto local de LCS.
1. Consiga una copia del paquete implementable personalizado que se aplicó al entorno del centro de conectividad y cárguelo en la biblioteca de activos del proyecto local de LCS.

## <a name="service-the-lbd-environment-with-target-packages"></a><a name="service-target-packages"></a>Dar servicio al entorno LBD con los paquetes de destino

Este paso alinea la versión de la aplicación, la versión de la plataforma y las personalizaciones en su unidad de escalado LBD con el centro de conectividad.

1. Realice el mantenimiento del entorno LBD con el paquete combinado de aplicación/plataforma que cargó en el paso anterior.
1. Realice el mantenimiento del entorno implementable LBD personalizado que cargó en el paso anterior.

    ![Aplicar actualizaciones en LCS.](media/cloud_edge-LBD-LCS-ServiceLBDEnv1.png "Aplicar actualizaciones en LCS")

    ![Seleccionar su paquete de personalización.](media/cloud_edge-LBD-LCS-ServiceLBDEnv2.png "Seleccione su paquete de personalización")

## <a name="assign-your-lbd-edge-scale-unit-to-a-hub"></a><a name="assign-edge-to-hub"></a>Asigne su unidad de escalado perimetral LBD a un centro de conectividad

Configure y administre su unidad de escala perimetral a través del Portal de administración de unidades de escala. Para más información, vea [Administre cargas de trabajo y unidades de escala mediante el portal Scale Unit Manager](./cloud-edge-landing-page.md#scale-unit-manager-portal).

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
