---
title: Implementar unidades de escalado en el perímetro en hardware personalizado mediante LBD (vista previa)
description: Este tema explica cómo aprovisionar unidades de escalado perimetrales locales mediante el uso de hardware personalizado y la implementación que se basa en datos comerciales locales (LBD).
author: cabeln
ms.date: 04/22/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: cabeln
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 0ebbdaab9d6f040497d3158db2712e102b6e9aa8
ms.sourcegitcommit: 1e5a46271bf7fae2f958d2b1b666a8d2583e04a8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2021
ms.locfileid: "7678990"
---
# <a name="deploy-edge-scale-units-on-custom-hardware-using-lbd-preview"></a>Implementar unidades de escalado en el perímetro en hardware personalizado mediante LBD (vista previa)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)] <!--KFM: Until 11/1/2021 -->

Las unidades de escalado perimetrales juegan un papel importante en la topología híbrida distribuida para la gestión de la cadena de suministro. En la topología híbrida, puede distribuir cargas de trabajo entre su centro de nube de Supply Chain Management y unidades de escalado adicionales en la nube o en el perímetro.

Las unidades de escalado perimetrales se pueden implementar mediante la creación de datos comerciales locales (LBD) [entorno local](../../fin-ops-core/dev-itpro/deployment/on-premises-deployment-landing-page.md) y luego configurándolo para que funcione como una unidad de escala en su topología híbrida distribuida para la gestión de la cadena de suministro. Esto se logra asociando el entorno de LBD local con un entorno de Supply Chain Management en la nube, que se ha configurado para funcionar como un centro de conectividad.  

Las unidades de escalado perimetrales están actualmente en vista previa. Por lo tanto, puede utilizar un entorno de este tipo solo de acuerdo con los [términos de vista previa](https://aka.ms/scmcnepreviewterms).

Este tema describe cómo configurar un entorno LBD local como una unidad de escala perimetral y luego asociarlo con un centro de conectividad.

## <a name="deployment-overview"></a>Información general de implementación

Esta es una visión general de los pasos de implementación.

1. **Habilite una ranura LBD en su proyecto LBD en Microsoft Dynamics Lifecycle Services (LCS).**

    Durante la vista previa, las unidades de escalado perimetrales LBD se dirigen a los clientes LBD existentes. Se proporcionará un espacio limitado de espacio aislado LBD adicional de 60 días solo en situaciones específicas de los clientes.

1. **Configure e implemente un entorno LBD con una base de datos *vacía*.**

    Utilice LCS para implementar el entorno LBD con la topología más reciente y una base de datos vacía. Para obtener más información, consulte la sección [Configurar e implementar un entorno LBD con una base de datos vacía](#set-up-deploy) más adelante en este tema. Debe utilizar la versión 10.0.19 de Supply Chain Management con la actualización de la plataforma 43 o superior en todos los entornos de centros de conectividad y unidades de escalado.

1. **Cargue los paquetes de destino en los activos del proyecto LBD en LCS.**

    Prepare paquetes de aplicaciones, plataformas y personalización que utilice en el centro de conectividad y la unidad de escala perimetral. Para obtener más información, consulte la sección [Cargar los paquetes de destino en los activos del proyecto LBD en LCS](#upload-packages) más adelante en este tema.

1. **Dar servicio al entorno LBD con los paquetes de destino.**

    Este paso garantiza que se implementen la misma compilación y personalizaciones en el centro de conectividad y el radio. Para obtener más información, consulte la sección [Dar servicio al entorno LBD con paquetes de destino](#service-target-packages) más adelante en este tema.

1. **Complete la configuración de la unidad de escalado y la asignación de carga de trabajo.**

    Para obtener más información, consulte la sección [Asignar su unidad de escala de borde LBD a un centro de conectividad](#assign-edge-to-hub) más adelante en este tema.

En las secciones restantes de este tema se proporcionan más detalles acerca de cómo completar estos pasos.

## <a name="set-up-and-deploy-an-lbd-environment-with-an-empty-database"></a><a name="set-up-deploy"></a>Configure e implemente un entorno LBD con una base de datos vacía.

Este paso crea un entorno funcional LBD. Sin embargo, el entorno no tiene necesariamente las mismas versiones de plataforma y aplicación que el entorno del centro de conectividad. Además, todavía le faltan las personalizaciones y aún no se ha habilitado para funcionar como una unidad de escalado.

1. Siga las instrucciones en [Configurar e implementar entornos locales (Platform update 41 y posteriores)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md). Debe utilizar la versión 10.0.19 de Supply Chain Management con la actualización de la plataforma 43 o superior en todos los entornos de centros de conectividad y unidades de escalado

    > [!IMPORTANT]
    > Leer el resto de esta sección **antes** de completar los pasos de ese tema.

1. Antes de describir su configuración en la infraestructura\\ConfigTemplate.xml, ejecute el siguiente script:

    ```powershell
    .\Configure-ScriptsForEdgeScaleUnits.ps1 -ConfigurationFilePath .\ConfigTemplate.xml
    ```

    > [!NOTE]
    > Este script eliminará cualquier configuración que no sea necesaria para implementar unidades de escalado perimetrales.

1. Configure una base de datos que contenga datos vacíos, como se describe en [Configurar bases de datos](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb). Utilice el archivo data.bak vacío para este paso.
1. Configure el script previo a la implementación. Para más información, consulte [Scripts para fases previas y posteriores a la implementación de agente local](../../fin-ops-core/dev-itpro/lifecycle-services/pre-post-scripts.md).

    1. Copie el contenido de la carpeta **ScaleUnit** en **Scripts de infraestructura** a la carpeta **Scripts** en el recurso compartido de almacenamiento de archivos del agente que se configuró en el entorno. Una ruta típica es \\\\lbdiscsi01\\agent\\Scripts.
    2. Cree el script **PreDeployment.ps1** que invocará los scripts utilizando los parámetros requeridos. La secuencia de comandos previa a la implementación debe colocarse en la carpeta **Scripts** en el recurso compartido de almacenamiento de archivos del agente. De lo contrario, no se puede ejecutar. Una ruta típica es \\\\lbdiscsi01\\agent\\Scripts\\PreDeployment.ps1.

        El contenido del script PreDeployment.ps1 se parecerá al siguiente ejemplo.

        ```powershell
        $agentShare = '\\lbdiscsi01\agent'
        
        Write-Output "AgentShare is set to $agentShare" 
        & $agentShare\Scripts\Configure-CloudandEdge.ps1 -AgentShare $agentShare -InstanceId '@A' -DatabaseServer 'lbdsqla01.contoso.com' -DatabaseName 'AXDB'
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

## <a name="upload-target-packages-into-lbd-project-assets-in-lcs"></a><a name="upload-packages"></a>Cargue los paquetes de destino en los activos del proyecto LBD en LCS.

Este paso prepara la versión de la aplicación, la versión de la plataforma y las personalizaciones que se transferirán al entorno de su unidad de escalado LBD.

1. Cargue el mismo paquete combinado de aplicación/plataforma que se aplicó al entorno del centro de conectividad en la biblioteca de activos del proyecto local de LCS.
1. Consiga una copia del paquete implementable personalizado que se aplicó al entorno del centro de conectividad y cárguelo en la biblioteca de activos del proyecto local de LCS.

## <a name="service-the-lbd-environment-with-target-packages"></a><a name="service-target-packages"></a>Dar servicio al entorno LBD con los paquetes de destino

Este paso alinea la versión de la aplicación, la versión de la plataforma y las personalizaciones en su unidad de escalado LBD con el centro de conectividad.

1. Realice el mantenimiento del entorno LBD con el paquete combinado de aplicación/plataforma que cargó en el paso anterior.
1. Realice el mantenimiento del entorno implementable LBD personalizado que cargó en el paso anterior.

    ![Seleccionar Mantener > Aplicar actualizaciones en LCS.](media/cloud_edge-LBD-LCS-ServiceLBDEnv1.png "Seleccione Mantener > Aplicar actualizaciones en LCS")

    ![Seleccionar su paquete de personalización.](media/cloud_edge-LBD-LCS-ServiceLBDEnv2.png "Seleccione su paquete de personalización")

## <a name="assign-your-lbd-edge-scale-unit-to-a-hub"></a><a name="assign-edge-to-hub"></a>Asigne su unidad de escalado perimetral LBD a un centro de conectividad

Mientras que las unidades de escalado perimetral todavía están en vista previa, debe usar las [herramientas de configuración e implementación de unidades de escalado](https://github.com/microsoft/SCMScaleUnitDevTools) que están disponibles en GitHub para asignar su unidad de escalado perimetral LBD a un centro de conectividad. El proceso permite que una configuración LBD funcione como una unidad de escalado perimetral y la asocia con el centro de conectividad. El proceso es similar a la configuración de un entorno de desarrollo one-box.

1. Descargue la última versión de [SCMScaleUnitDevTools](https://github.com/microsoft/SCMScaleUnitDevTools/releases) y descomprima el contenido del archivo.
1. Cree una copia del archivo `UserConfig.sample.xml` y nómbrelo `UserConfig.xml`.
1. Cree una aplicación de Microsoft Azure Active Directory (Azure AD) en su inquilino Azure AD, como se menciona en la [Guía de implementación para unidades de escala y cargas de trabajo](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide#aad-application-registrations).
    1. Una vez creado, navegue hasta el formulario de aplicaciones Azure AD (SysAADClientTable) en su centro de conectividad.
    1. Cree una nueva entrada y establezca el **Id. de cliente** como el id. de la aplicación que creó. Configure el **Nombre** en *ScaleUnits* y el **Id. de usuario** en *Admin*.

1. Cree una aplicación de Servicio de federación de Active Directory (AD FS) como se menciona en la [Guía de implementación para cargas de trabajo y unidades de escalado](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide#adfs-application-registrations).
    1. Una vez creado, navegue hasta el formulario de aplicaciones Azure AD (SysAADClientTable) en su unidad de escalado perimetral.
    1. Cree una nueva entrada y establezca el **Id. de cliente** como el id. de la aplicación que creó. Configure el **id. de usuario** en *Admin*.

1. Modifique el archivo `UserConfig.xml`.
    1. En la sección `InterAOSAADConfiguration`, introduzca la información de la aplicación Azure AD que creó anteriormente.
        - En el elemento `AppId`, introduzca el id. de la aplicación de Azure.
        - En el elemento `AppSecret`, introduzca el secreto de la aplicación de Azure.
        - El elemento `Authority` debe contener la URL que especifica la autoridad de seguridad de su inquilino.

        ```xml
        <InterAOSAADConfiguration>
            <AppId>8dab14f6-97b1-48e3-b51b-350b45f6ede5</AppId>
            <AppSecret>k6em-_7.lopty56TGUedDTVhtER-j_6anY1</AppSecret>
            <Authority>https://login.windows.net/contoso.onmicrosoft.com</Authority>
        </InterAOSAADConfiguration>
        ```

    1. Bajo la sección `ScaleUnitConfiguration`, para la primera `ScaleUnitInstance`, modifique la sección `AuthConfiguration`.
        - En el elemento `AppId`, introduzca el id. de la aplicación de Azure.
        - En el elemento `AppSecret`, introduzca el secreto de la aplicación de Azure.
        - El elemento `Authority` debe contener la URL que especifica la autoridad de seguridad de su inquilino.

        ```xml
        <AuthConfiguration>
            <AppId>8dab14f6-97b1-48e3-b51b-350b45f6ede5</AppId>
            <AppSecret>k6em-_7.lopdz.6d3DTVOtf9Lo-j_6anY1</AppSecret>
            <Authority>https://login.windows.net/contoso.onmicrosoft.com</Authority>
        </AuthConfiguration>
        ```

    1. Además, establezca los siguientes valores para esta misma `ScaleUnitInstance`:
        - En el elemento `Domain`, especifique la URL de su centro de conectividad. Por ejemplo: `https://cloudhub.sandbox.operations.dynamics.com/`
        - En el elemento `EnvironmentType`, asegúrese de que está establecido el valor `LCSHosted`.

    1. Bajo la sección `ScaleUnitConfiguration`, para la segunda `ScaleUnitInstance`, modifique la sección `AuthConfiguration`.
        - En el elemento `AppId`, introduzca el id. de la aplicación de AD FS.
        - En el elemento `AppSecret`, introduzca el secreto de la aplicación de ADFS.
        - El elemento `Authority` debe contener la URL de su instancia de AD FS.

        ```xml
        <AuthConfiguration>
            <AppId>26b16f25-21d8-4d36-987b-62df292895aa</AppId>
            <AppSecret>iZFfObgI6lLtY9kEbBjEFV98NqI5_YZ0e5SBcWER</AppSecret>
            <Authority>https://adfs.contoso.com/adfs</Authority>
        </AuthConfiguration>
        ```

    1. Además, establezca los siguientes valores para esta misma `ScaleUnitInstance`:
        - En el elemento `Domain`, especifique la URL de su unidad de escalado perimetral. Por ejemplo: https://ax.contoso.com/
        - En el elemento `EnvironmentType`, asegúrese de que está establecido el valor LBD.
        - En el elemento `ScaleUnitId`, introduzca el mismo valor que especificó para `InstanceId` al configurar el script de preimplementación `Configure-CloudandEdge.ps1`.

        > [!NOTE]
        > Si no usa el id. predeterminado (@A), asegúrese de actualizar ScaleUnitId para cada ConfiguredWorkload configurada en la sección Cargas de trabajo.

1. Abra PowerShell y navegue hasta la carpeta que contiene el archivo `UserConfig.xml`.

1. Ejecute la herramienta con este comando.

    ```powershell
    .\CLI.exe
    ```

    > [!NOTE]
    > Después de cada acción, tendrá que volver a iniciar la herramienta.

1. En la herramienta, seleccione **2. Preparar entornos para la instalación de cargas de trabajo**. A continuación ejecute los siguientes pasos:
    1. Seleccione **1. Preparar el centro de conectividad**.
    1. Seleccione **2. Preparar la unidad de escalado**.

    > [!NOTE]
    > Si no está ejecutando este comando desde una instalación limpia y falla, realice las siguientes acciones:
    >
    > - Elimine todas las carpetas de la carpeta `aos-storage` (excepto para `GACAssemblies`).
    > - Ejecute el siguiente comando SQL en su base de datos empresarial (AXDB):
    >
    > ```sql 
    > delete from storagefoler
    > ```

1. Ejecute los siguientes comandos SQL en su base de datos empresarial (AXDB):

    ```sql
    delete from FEATUREMANAGEMENTMETADATA
    delete from FEATUREMANAGEMENTSTATE
    delete from NUMBERSEQUENCESCOPE
    ```

1. Verifique que el seguimiento de cambios se haya habilitado en su base de datos comercial (AXDB)
    1. Ejecute SQL Server Management Studio (SSMS).
    1. Haga clic con el botón derecho en la base de datos de su empresa (AXDB) y seleccione propiedades.
    1. En la ventana que se abre, seleccione **Change Tracking** y realice los siguientes ajustes:

        - **Change Tracking:** *True*
        - **Periodo de retención:** *7*
        - **Unidades de retención:** *Días*
        - **Limpieza automática:** *True*

1. En la herramienta, seleccione **3. Instalar cargas de trabajo**. A continuación ejecute los siguientes pasos:
    1. Seleccione **1. Instalar en centro de conectividad**.
    1. Seleccione **2. Instalar en unidad de escalado**.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
