---
title: Directrices de implementación para la muestra de integración del servicio fiscal para Austria (heredada)
description: Este artículo proporciona pautas para implementar la muestra de integración de impresora fiscal para Austria desde el Kit de desarrollo de software (SDK) para minoristas de Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 03/04/2022
ms.topic: article
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-03-01
ms.openlocfilehash: 203904f60888464a473cb2997652db497fba6f57
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276112"
---
# <a name="deployment-guidelines-for-the-fiscal-registration-service-integration-sample-for-austria-legacy"></a>Directrices de implementación para la muestra de integración del servicio fiscal para Austria (heredada)

[!include [banner](../includes/banner.md)]

Este artículo proporciona pautas para implementar la muestra de integración del servicio de registro para Austria desde el kit de desarrollo de software (SDK) para minoristas de Microsoft Dynamics 365 Commerce en una máquina virtual (VM) de desarrollador en Microsoft Dynamics Lifecycle Services (LCS). Para obtener más información sobre este ejemplo de integración fiscal, consulte el [ejemplo de integración del servicio de registro fiscal para Austria](emea-aut-fi-sample.md). 

La muestra de integración fiscal de Austria forma parte del Retail SDK. Para obtener información sobre cómo instalar y usar el SDK, consulte [Kit de desarrollo de software (SDK) al por menor](../dev-itpro/retail-sdk/retail-sdk-overview.md). El ejemplo de integración fiscal consta de extensiones para Commerce Runtime (CRT), la estación de hardware y el punto de venta (PDV). Para ejecutar este ejemplo, debe modificar y compilar el CRT, estación de hardware y proyectos de PDV. Le recomendamos que utilice un SDK para minoristas sin modificar para realizar los cambios que se describen en este artículo. También le recomendamos que utilice un sistema de control de fuente, como Azure DevOps, donde aún no se han cambiado archivos.

## <a name="development-environment"></a>Entorno de desarrollo

Siga estos pasos para configurar un entorno de desarrollo para que pueda probar y ampliar la muestra.

### <a name="enable-commerce-runtime-extensions"></a>Habilitar las extensiones de Commerce Runtime

Los componentes de extensión de CRT se incluyen en los ejemplos de CRT. Para completar los siguientes procedimientos, abra la solución **CommerceRuntimeSamples.sln** bajo **RetailSdk\\SampleExtensions\\CommerceRuntime**.

#### <a name="documentproviderefrsample-component"></a>Componente DocumentProvider.EFRSample

1. Encuentre el proyecto **Runtime.Extensions.DocumentProvider.EFRSample** y compílelo.
2. En la carpeta **Runtime.Extensions.DocumentProvider.EFRSample\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.Runtime.DocumentProvider.EFRSample.dll**.
3. Copie el archivo de ensamblado a la carpeta de extensiones de CRT:

    - **Commerce Scale Unit:** Copie el archivo a la carpeta **\\bin\\ext** en la ubicación del sitio de Commerce Scale Unit de Internet Information Services (IIS).
    - **CRT local en Modern POS:** Copie el archivo en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

4. Busque el archivo de configuración de la extensión para CRT:

    - **Commerce Scale Unit:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Commerce Scale Unit.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

5. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EFRSample" />
    ```

#### <a name="documentproviderdatamodelefr-component"></a>Componente DocumentProvider.DataModelEFR

1. Encuentre el proyecto **Runtime.Extensions.DocumentProvider.DataModelEFR** y compílelo.
2. En la carpeta **Runtime.Extensions.DocumentProvider.DataModelEFR\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll**.
3. Copie el archivo de ensamblado a la carpeta de extensiones de CRT:

    - **Commerce Scale Unit:** Copie el archivo a la carpeta **\\bin\\ext** en la ubicación del sitio de Commerce Scale Unit de IIS.
    - **CRT local en Modern POS:** Copie el archivo en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

4. Busque el archivo de configuración de la extensión para CRT:

    - **Commerce Scale Unit:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Commerce Scale Unit.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

5. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR" />
    ```

#### <a name="extension-configuration-file"></a>Archivo de configuración de la extensión

1. Busque el archivo de configuración de la extensión para CRT:

    - **Commerce Scale Unit:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Commerce Scale Unit.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

2. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsAustria" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventAustria" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.XZReportsAustria" />
    ```

### <a name="enable-fiscal-connector-extensions"></a>Habilitar extensiones de conector fiscal

Puede habilitar extensiones de conector fiscal en la [estación de hardware](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-connected-to-the-hardware-station) o el [registro de PDV](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-or-service-in-the-local-network).

#### <a name="enable-hardware-station-extensions"></a>Habilitar extensiones de la estación de hardware

Los componentes de extensión de la estación de hardware se incluyen en los ejemplos de la estación de hardware. Para completar los siguientes procedimientos, abra la solución **HardwareStationSamples.sln** bajo **RetailSdk\\SampleExtensions\\HardwareStation**.

##### <a name="efrsample-component"></a>Componente EFRSample

1. Encuentre el proyecto **HardwareStation.Extension.EFRSample** y compílelo.
2. En la carpeta **Extension.EFRSample\\bin\\Debug**, busque los siguientes archivos de ensamblado:

    - Contoso.Commerce.HardwareStation.EFRSample.dll
    - Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll

3. Copie los archivos de ensamblaje en la carpeta de extensiones de la estación de hardware:

    - **Estación de hardware compartida:** copie los archivos en la carpeta **bin** en la ubicación del sitio de la estación de hardware IIS.
    - **Estación de hardware dedicada en POS moderno:** copie los archivos en la ubicación del agente del cliente de POS de Modern.

4. Encuentre el archivo de configuración de la extensión para las extensiones de la estación de hardware. El archivo se llama **HardwareStation.Extension.config**.

    - **Estación de hardware compartida:** El archivo se encuentra en la ubicación del sitio de la estación de hardware IIS.
    - **Estación de hardware dedicada en POS moderno:** El archivo se encuentra en la ubicación del agente del cliente de POS de Modern.

5. Agregue la siguiente línea a la sección **composition** del archivo de configuración.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.EFRSample.dll" />
    ```

#### <a name="enable-pos-extensions"></a>Habilitar extensiones PDV

La extensión de PDV de muestra se encuentra en la carpeta **src\\FiscalIntegration\\PosFiscalConnectorSample** del repositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/).

Para usar la extensión PDV de muestra en la SDK heredada, siga estos pasos.

1. Copie la carpeta **Pos.Extension** a la carpeta PDV **Extensions** del SDK heredado (por ejemplo, `C:\RetailSDK\src\POS\Extensions`).
1. Cambie el nombre de la copia de la carpeta **Pos.Extension** **PosFiscalConnector**.
1. Elimine las siguientes carpetas y archivos de la carpeta **PosFiscalConnector**:

    - bin
    - DataService
    - devDependencies
    - Bibliotecas
    - obj
    - Contoso.PosFiscalConnectorSample.Pos.csproj
    - RetailServerEdmxModel.g.xml
    - tsconfig.json

1. Abra la solución **CloudPos.sln** o **ModernPos.sln**.
1. En el proyecto **Pos.Extensions**, incluya la carpeta **PosFiscalConnector**.
1. Abra el archivo **extensions.json** y agregue la extensión **PosFiscalConnector**.
1. Build the SDK.

### <a name="enable-modern-pos-extension-components"></a>Habilitar los componentes de la extensión Modern POS

1. Abra la solución **ModernPOS.sln** en **RetailSdk\\POS** y asegúrese de que se pueda compilar sin errores. Además, asegúrese de poder ejecutar Modern POS de Visual Studio usando el comando **Ejecutar**.

    > [!NOTE]
    > Los puntos de venta modernos no deben personalizarse. Debe habilitar el Control de cuentas de usuario (UAC) y debe desinstalar las instancias instaladas previamente de Modern POS según sea necesario.

2. Habilite las extensiones que se van a cargar agregando las siguientes líneas en el archivo **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.AT"
            }
        ]
    }
    ```

    > [!NOTE]
    > Para obtener más información y ejemplos que muestran cómo incluir carpetas de código fuente y habilitar la carga de extensiones, consulte las instrucciones en el archivo readme.md en el proyecto **Pos.Extensions**.

3. Compile la solución.
4. Ejecute Modern POS en el depurador y pruebe la funcionalidad.

### <a name="enable-cloud-pos-extension-components"></a>Habilitar componentes de la extensión Cloud POS

1. Abra la solución **CloudPOS.sln** en **RetailSdk\\POS** y asegúrese de que se pueda compilar sin errores.
2. Habilite las extensiones que se van a cargar agregando las siguientes líneas en el archivo **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.AT"
            }
        ]
    }
    ```

    > [!NOTE]
    > Para obtener más información y ejemplos que muestran cómo incluir carpetas de código fuente y habilitar la carga de extensiones, consulte las instrucciones en el archivo readme.md en el proyecto **Pos.Extensions**.

3. Compile la solución.
4. Ejecute la solución utilizando el comando **Ejecutar** y siguiendo los pasos del manual Retail SDK.

## <a name="production-environment"></a>Entorno de producción

El procedimiento anterior habilita las extensiones que son componentes de la muestra de integración del servicio de integración fiscal. Además, debe seguir estos pasos para crear paquetes desplegables que contengan componentes de Commerce y aplicar esos paquetes en un entorno de producción.

1. Realice los siguientes cambios en los archivos de configuración del paquete en la carpeta **RetailSdk\\Assets**:

    - En los archivos de configuración **commerceruntime.ext.config** y **CommerceRuntime.MPOSOffline.Ext.config**, agregue las siguientes líneas a la sección **composition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EFRSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR" />
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsAustria" />
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventAustria" />
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.XZReportsAustria" />
        ```

    - En el archivo de configuración **HardwareStation.Extension.config**, agregue la siguiente línea a la sección **composition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.EFRSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR" />
        ```

2. Realice los siguientes cambios en el archivo de configuración de personalización del paquete **Ajustes de personalización** en la carpeta **BuildTools**:

    - Agregue las siguientes líneas para incluir las extensiones CRT en los paquetes desplegables.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.EFRSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll" />
        ```

    - Agregue la siguiente línea para incluir la extensión de la estación de hardware en los paquetes desplegables.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.EFRSample.dll" />
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll" />
        ```

3. Inicie el símbolo del sistema de MSBuild para la utilidad Visual Studio y ejecute **msbuild** en la carpeta Retail SDK para crear paquetes implementables.
4. Aplique los paquetes a través de LCS o manualmente. Para obtener más información, consulte [Crear paquetes implementables](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
5. Complete todas las tareas de configuración necesarias que se describen en [Configurar Commerce para Austria](emea-aut-fi-sample.md#set-up-commerce-for-austria).

## <a name="design-of-extensions"></a>Diseño de las extensiones

La muestra de integración de servicio de registro para Austria se basa en la [funcionalidad de integración fiscal](fiscal-integration-for-retail-channel.md). Para obtener más información acerca del diseño de la solución de integración fiscal, consulte [Visión general de un diseño de ejemplo de integración fiscal](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

### <a name="commerce-runtime-extension-design"></a>Diseño de extensión de Commerce Runtime

El propósito de la extensión que es un proveedor de documentos fiscales es generar documentos específicos del servicio y manejar respuestas desde el servicio de registro fiscal.

La extensión CRT es **Runtime.Extensions.DocumentProvider.EFRSample**.

#### <a name="request-handler"></a>Manejador de solicitudes

Hay dos controladores de solicitudes para proveedores de documentos:

- **DocumentProviderEFRFiscalAUT** – Este manejador se utiliza para generar documentos fiscales para el servicio de registro fiscal.
- **DocumentProviderEFRNonFiscalAUT** – Este manejador se utiliza para generar documentos no fiscales para el servicio de registro fiscal.

Estos controladores se heredan de la interfaz **INamedRequestHandler**. El método **HandlerName** es responsable de devolver el nombre del controlador. El nombre del controlador debe coincidir con el nombre del proveedor de documentos del conector que se especifica en la sede de Comercio.

El conector admite las siguientes solicitudes:

- **GetFiscalDocumentDocumentProviderRequest** - Esta solicitud contiene información sobre qué documento se debe generar. Devuelve un documento específico del servicio que debe registrarse en el servicio de registro fiscal.
- **GetNonFiscalDocumentDocumentProviderRequest** – Esta solicitud contiene información sobre qué documento no fiscal se debe generar. Devuelve un documento específico del servicio que debe registrarse en el servicio de registro fiscal.
- **GetSupportedRegistrableEventsDocumentProviderRequest** - Esta solicitud devuelve la lista de eventos a los que suscribirse. Actualmente, se admiten los siguientes eventos: ventas, impresión del informe X, impresión del informe Z, depósitos de cuentas de clientes, depósitos de pedidos de clientes, eventos de auditoría y transacciones sin ventas.
- **GetFiscalRegisterResponseToSaveDocumentProviderRequest** - Esta solicitud devuelve la respuesta del servicio de registro fiscal. Esta respuesta se serializa para formar una cadena de modo que esté lista para ser guardada.

#### <a name="configuration"></a>Configuración

Los archivos de configuración se encuentran en la carpeta **Configuración** del proyecto de extensión:

- **DocumentProviderFiscalEFRSampleAustria** - Para documentos fiscales.
- **DocumentProviderNonFiscalEFRSampleAustria** - Para documentos no fiscales.

El propósito de estos archivos es permitir que la configuración del proveedor de documentos se configure desde la sede de Commerce. El formato de archivo está alineado con los requisitos para la configuración de integración fiscal. Se agrega el siguiente parámetro:

- Asignación de tasas de IVA

### <a name="hardware-station-extension-design"></a>Diseño de extensiones de la estación de hardware

El propósito de la extensión del conector fiscal es comunicarse con el servicio de registro fiscal. La extensión de la estación de hardware se llama **HardwareStation.Extension.EFRSample**. Usa el protocolo HTTP o HTTPS para enviar documentos que la extensión CRT genera en el servicio de registro fiscal. También maneja las respuestas que se reciben del servicio de registro fiscal.

#### <a name="request-handler"></a>Manejador de solicitudes

El manejador de solicitudes **EFRHandler** es el punto de entrada para manejar las solicitudes al servicio de registro fiscal.

El controlador se hereda de la interfaz **INamedRequestHandler**. El método **HandlerName** es responsable de devolver el nombre del controlador. El nombre del controlador debe coincidir con el nombre del conector fiscal que se especifica en la sede de Commerce.

El conector admite las siguientes solicitudes:

- **SubmitDocumentFiscalDeviceRequest** - Esta solicitud envía documentos al servicio de registro fiscal y devuelve una respuesta de ella.
- **IsReadyFiscalDeviceRequest** - Esta solicitud se utiliza para una verificación del servicio de registro fiscal.
- **InitializeFiscalDeviceRequest** - Esta solicitud se utiliza para inicializar el servicio de registro fiscal.

#### <a name="configuration"></a>Configuración

El archivo de configuración se encuentra en la carpeta **Configuración** del proyecto de extensión. El propósito del archivo es permitir la configuración del conector fiscal desde la sede de Comercio. El formato de archivo está alineado con los requisitos para la configuración de integración fiscal. Se agregan los siguientes parámetros:

- **Dirección de punto final** - La URL del servicio de registro fiscal.
- **Tiempo de espera** - La cantidad de tiempo, en milisegundos, que el controlador esperará una respuesta del servicio de registro fiscal.

### <a name="pos-fiscal-connector-extension-design"></a>Diseño de la extensión del conector fiscal del PDV

El propósito de la extensión del conector fiscal PDV es comunicarse con el servicio de registro fiscal del PDV. Utiliza el protocolo HTTPS para la comunicación.

#### <a name="fiscal-connector-factory"></a>Fábrica del conector fiscal

La fábrica de conectores fiscales asigna el nombre del conector a la implementación del conector fiscal y se encuentra en el archivo **Pos. Extensión\\Connectors\\FiscalConnectorFactory.ts**. El nombre del conector debe coincidir con el nombre del conector fiscal que se especifica en la sede de Commerce.

#### <a name="efr-fiscal-connector"></a>Conector fiscal EFR

El conector fiscal EFR se encuentra en el archivo **Pos.Extension\\Connectors\\Efr\\EfrFiscalConnector.ts**. Implementa la interfaz **IFiscalConnector** que admite las siguientes solicitudes:

- **FiscalRegisterSubmitDocumentClientRequest** - Esta solicitud envía documentos al servicio de registro fiscal y devuelve una respuesta de ella.
- **FiscalRegisterIsReadyClientRequest** - Esta solicitud se utiliza para una verificación del servicio de registro fiscal.
- **FiscalRegisterInitializeClientRequest** - Esta solicitud se utiliza para inicializar el servicio de registro fiscal.

#### <a name="configuration"></a>Configuración

El archivo de configuración se encuentra en la carpeta **src\\FiscalIntegration\\Efr\\Configuraciones\\Conectores** del repositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). El propósito del archivo es permitir la configuración del conector fiscal desde la sede de Comercio. El formato de archivo está alineado con los requisitos para la configuración de integración fiscal. Se agregan los siguientes parámetros:

- **Dirección de punto final** - La URL del servicio de registro fiscal.
- **Tiempo de espera** - La cantidad de tiempo, en milisegundos, que el conector esperará una respuesta del servicio de registro fiscal.
