---
title: Directrices de implementación para la muestra de integración de la impresora fiscal para Italia (heredada)
description: Este artículo proporciona pautas para implementar la muestra de integración de impresora fiscal para Italia desde el Kit de desarrollo de software (SDK) para minoristas de Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 03/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-03-01
ms.openlocfilehash: 9e951c1a1ee5c967d2bd67941ff3d19c62b59ba6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279549"
---
# <a name="deployment-guidelines-for-the-fiscal-printer-integration-sample-for-italy-legacy"></a>Directrices de implementación para la muestra de integración de la impresora fiscal para Italia (heredada)

[!include[banner](../includes/banner.md)]

Este artículo proporciona pautas para implementar la muestra de integración de la impresora fiscal para Italia desde el kit de desarrollo de software (SDK) para minoristas de Microsoft Dynamics 365 Commerce en una máquina virtual (VM) de desarrollador en Microsoft Dynamics Lifecycle Services (LCS). Para obtener más información sobre este ejemplo de integración fiscal, consulte el [ejemplo de integración de la impresora fiscal para Italia](emea-ita-fpi-sample.md). 

La muestra de integración fiscal de Italia forma parte del Retail SDK. Para obtener información sobre cómo instalar y usar el SDK, consulte [Kit de desarrollo de software (SDK) al por menor](../dev-itpro/retail-sdk/retail-sdk-overview.md). Esta muestra consta de extensiones para Commerce Runtime (CRT) y la estación de hardware. Para ejecutar este ejemplo, debe modificar y compilar los proyectos de CRT y la estación de hardware. Le recomendamos que utilice un SDK para minoristas sin modificar para realizar los cambios que se describen en este artículo. También le recomendamos que utilice un sistema de control de fuente, como Azure DevOps, donde aún no se han cambiado archivos.

## <a name="development-environment"></a>Entorno de desarrollo

Siga estos pasos para configurar un entorno de desarrollo para que pueda probar y ampliar la muestra.

### <a name="commerce-runtime-extension-components"></a>Componentes de extensión de Commerce Runtime

Los componentes de extensión de CRT se incluyen en el SDK de Retail. Para completar los siguientes procedimientos, abra la solución **CommerceRuntimeSamples.sln** bajo **RetailSdk\\SampleExtensions\\CommerceRuntime**.

1. Encuentre el proyecto **Runtime.Extensions.DocumentProvider.EpsonFP90IIISample** y compílelo.
2. En la carpeta **Extensions.DocumentProvider.EpsonFP90IIISample\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.dll**.
3. Copie el archivo de ensamblado a la carpeta de extensiones de CRT:

    - **Commerce Scale Unit:** Copie el archivo a la carpeta **\\bin\\ext** en la ubicación del sitio de Commerce Scale Unit de Internet Information Services (IIS).
    - **CRT local en Modern POS:** Copie el archivo en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

4. Busque el archivo de configuración de la extensión para CRT:

    - **Commerce Scale Unit:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Commerce Scale Unit.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

5. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample" />
    ```

6. Reinicie Commerce Scale Unit:

    - **Commerce Scale Unit:** Reinicie el sitio de Commerce Scale Unit desde el Administrador de IIS.
    - **Corredor de clientes:** Termine el proceso de **dllhost.exe** en el Administrador de tareas y luego reinicie Modern POS.

### <a name="hardware-station-extension-components"></a>Componentes de extensiones de la estación de hardware

Los componentes de extensión de la estación de hardware se incluyen en el SDK de Retail. Para completar los siguientes procedimientos, abra la solución **HardwareStationSamples.sln** bajo **RetailSdk\\SampleExtensions\\HardwareStation**.

1. Encuentre el proyecto **HardwareStation.Extensions.EpsonFP90IIIFiscalDeviceSample** y compílelo.
2. En la carpeta **Extensions.EpsonFP90IIIFiscalDeviceSample\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample.dll**.
3. Copie el archivo de ensamblaje en una máquina de estación de hardware implementada:

    - **Estación de hardware remota:** copie el archivo en la carpeta **bin** en la ubicación del sitio de la estación de hardware IIS.
    - **Estación de hardware local:** copie el archivo en la ubicación del agente del cliente de Modern POS.

4. Encuentre el archivo de configuración para las extensiones de la estación de hardware. El archivo se llama **HardwareStation.Extension.config**:

    - **Estación de hardware remota:** El archivo se encuentra en la ubicación del sitio de la estación de hardware IIS.
    - **Estación de hardware local:** El archivo se encuentra en la ubicación del agente del cliente de POS de Modern.

5. Agregue la siguiente sección a la sección **composition** del archivo de configuración.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample" />
    ```

6. Reinicie el servicio de la estación de hardware:

    - **Estación de hardware remota:** Reinicie el sitio de la estación de hardware desde el Administrador de IIS.
    - **Estación de hardware local:** Termine el proceso de **dllhost.exe** en el Administrador de tareas y luego reinicie Modern POS.

## <a name="production-environment"></a>Entorno de producción

Para crear paquetes desplegables que contengan componentes de Commerce y aplicar esos paquetes en un entorno de producción, siga estos pasos.

1. Complete los pasos que se describen en la sección [Entorno de desarrollo](#development-environment) anterior en este artículo.
2. Realice los siguientes cambios en los archivos de configuración del paquete en la carpeta **RetailSdk\\Assets**:

    1. En los archivos de configuración **commerceruntime.ext.config** y **CommerceRuntime.MPOSOffline.Ext.config**, agregue la siguiente línea a la sección **composition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample" />
        ```

    1. En el archivo de configuración **HardwareStation.Extension.config**, agregue la siguiente línea a la sección **composition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample" />
        ```

3. Realice los siguientes cambios en el archivo de configuración de personalización del paquete **Ajustes de personalización** en la carpeta **BuildTools**:

    1. Agregue la siguiente línea para incluir la extensión CRT en los paquetes desplegables.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.dll"/>
        ```

    1. Agregue la siguiente línea para incluir la extensión de la estación de hardware en los paquetes desplegables.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample.dll"/>
        ```

4. Realice los siguientes cambios en el archivo **SDK.ModernPos.Shared.csproj** en la carpeta **Packages\_SharedPackagingProjectComponents** para incluir los archivos de recursos para Italia en paquetes desplegables:

    1. Agregue una sección **ItemGroup** que contiene nodos que apuntan a los archivos de recursos para las traducciones deseadas. Asegúrese de especificar los espacios de nombres y los nombres de muestra correctos. El siguiente ejemplo agrega nodos de recursos para las configuraciones regionales **it** y **it-CH**.

        ```xml
        <ItemGroup>
            <ResourcesIt Include="$(SdkReferencesPath)\it\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.resources.dll"/>
            <ResourcesItCh Include="$(SdkReferencesPath)\it-CH\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.resources.dll"/>
        </ItemGroup>
        ```

    1. En la sección **Nombre de destino="CopyPackageFiles"** sección, agregue una línea para cada configuración regional, como se muestra en el siguiente ejemplo.

        ```xml
        <Copy SourceFiles="@(ResourcesIt)" DestinationFolder="$(OutputPath)content.folder\CustomizedFiles\ClientBroker\ext\it" SkipUnchangedFiles="true" />
        <Copy SourceFiles="@(ResourcesItCh)" DestinationFolder="$(OutputPath)content.folder\CustomizedFiles\ClientBroker\ext\it-CH" SkipUnchangedFiles="true" />
        ```

5. Realice los siguientes cambios en el archivo **SDK.RetailServerSetup.proj** en la carpeta **Packages\_SharedPackagingProjectComponents** para incluir los archivos de recursos para Italia en paquetes desplegables:

    1. Agregue una sección **ItemGroup** que contiene nodos que apuntan a los archivos de recursos para las traducciones deseadas. Asegúrese de especificar los espacios de nombres y los nombres de muestra correctos. El siguiente ejemplo agrega nodos de recursos para las configuraciones regionales **it** y **it-CH**.

        ```xml
        <ItemGroup>
            <ResourcesIt Include="$(SdkReferencesPath)\it\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.resources.dll"/>
            <ResourcesItCh Include="$(SdkReferencesPath)\it-CH\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.resources.dll"/>
        </ItemGroup>
        ```

    1. En la sección **Nombre de destino="CopyPackageFiles"** sección, agregue una línea para cada configuración regional, como se muestra en el siguiente ejemplo.

        ``` xml
        <Copy SourceFiles="@(ResourcesIt)" DestinationFolder="$(OutputPath)content.folder\RetailServer\Code\bin\ext\it" SkipUnchangedFiles="true" />
        <Copy SourceFiles="@(ResourcesItCh)" DestinationFolder="$(OutputPath)content.folder\RetailServer\Code\bin\ext\it-CH" SkipUnchangedFiles="true" />
        ```

6. Inicie el símbolo del sistema de MSBuild para la utilidad Visual Studio y luego ejecute **msbuild** en la carpeta Retail SDK para crear paquetes implementables.
7. Aplique los paquetes a través de LCS o manualmente. Para obtener más información, consulte [Crear paquetes implementables](../dev-itpro/retail-sdk/retail-sdk-packaging.md).

## <a name="design-of-extensions"></a>Diseño de las extensiones

### <a name="commerce-runtime-extension-design"></a>Diseño de extensión de Commerce Runtime

El propósito de la extensión que es un proveedor de documentos fiscales es generar documentos específicos de la impresora y manejar respuestas desde la impresora fiscal.

La extensión CRT es **Runtime.Extensions.DocumentProvider.EpsonFP90IIISample**.

Para obtener más información sobre el diseño de la solución de integración fiscal, consulte [Proceso de registro fiscal y ejemplos fiscales de la integración de los dispositivos y servicios fiscales](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

#### <a name="request-handler"></a>Manejador de solicitudes

El gestor de solicitudes **DocumentProviderEpsonFP90III** es el punto de entrada de la solicitud para generar documentos desde la impresora fiscal.

El controlador se hereda de la interfaz **INamedRequestHandler**. El método **HandlerName** es responsable de devolver el nombre del controlador. El nombre del controlador debe coincidir con el nombre del proveedor de documentos del conector que se especifica en la sede de Comercio.

El conector admite las siguientes solicitudes:

- **GetFiscalDocumentDocumentProviderRequest** - Esta solicitud contiene información sobre qué documento se debe generar. Devuelve un documento específico de la impresora que debe registrarse en la impresora fiscal.
- **GetSupportedRegistrableEventsDocumentProviderRequest** - Esta solicitud devuelve la lista de eventos a los que suscribirse. Actualmente, se admiten los siguientes eventos: ventas, impresión del informe X e impresión del informe Z.

#### <a name="configuration"></a>Configuración

El archivo de configuración se encuentra en la carpeta **Configuración** del proyecto de extensión. El propósito del archivo es permitir que la configuración del proveedor de documentos se configure desde la sede de Comercio. El formato de archivo está alineado con los requisitos para la configuración de integración fiscal. Se agregan los siguientes parámetros:

- Asignación de códigos de IVA
- Asignación de tasas de IVA
- Asignación de tipos de forma de pago
- Tipo de código de barras para número de recibo
- Tipo de pago de depósito

### <a name="hardware-station-extension-design"></a>Diseño de extensiones de la estación de hardware

El propósito de la extensión que es un conector fiscal es comunicarse con la impresora fiscal.

La extensión de la estación de hardware es **HardwareStation.Extension.EpsonFP90IIIFiscalDeviceSample**. Esta extensión usa el protocolo HTTP para enviar documentos que la extensión CRT genera a la impresora fiscal. También maneja las respuestas que se reciben de la impresora fiscal.

#### <a name="request-handler"></a>Manejador de solicitudes

El gestor de solicitudes **EpsonFP90IIISample** es el punto de entrada para gestionar las solicitudes al dispositivo periférico fiscal.

El controlador se hereda de la interfaz **INamedRequestHandler**. El método **HandlerName** es responsable de devolver el nombre del controlador. El nombre del controlador debe coincidir con el nombre del conector fiscal que se especifica en la sede de Commerce.

El conector admite las siguientes solicitudes:

- **SubmitDocumentFiscalDeviceRequest** - Esta solicitud envía documentos a las impresoras y devuelve la respuesta de la impresora fiscal.
- **IsReadyFiscalDeviceRequest** - Esta solicitud se utiliza para una verificación de estado del dispositivo.
- **InitializeFiscalDeviceRequest** - Esta solicitud se utiliza para inicializar la impresora.

#### <a name="configuration"></a>Configuración

El archivo de configuración se encuentra en la carpeta **Configuración** del proyecto de extensión. El propósito del archivo es permitir la configuración para el conector fiscal desde la sede de Commerce. El formato de archivo está alineado con los requisitos para la configuración de integración fiscal. Se agregan los siguientes parámetros:

- **Dirección de punto final** - La URL de la impresora.
- **Sincronización de fecha y hora** - Un valor que especifica si la fecha y la hora de la impresora deben sincronizarse con la estación de hardware conectada.
