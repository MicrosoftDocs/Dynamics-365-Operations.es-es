---
title: Directrices de implementación para la muestra de integración de la unidad de control para Suecia (heredada)
description: Este artículo proporciona pautas para implementar la muestra de integración de la unidad de control para Suecia desde Retail SDK
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: 05a49de43282c449c7b99072d8ac3ac4a5f2a67f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870556"
---
# <a name="deployment-guidelines-for-the-control-unit-integration-sample-for-sweden-legacy"></a>Directrices de implementación para la muestra de integración de la unidad de control para Suecia (heredada)

[!include [banner](../includes/banner.md)]

Este artículo proporciona pautas para implementar la muestra de integración de la unidad de control para Suecia desde el kit de desarrollo de software (SDK) para minoristas en una máquina virtual (VM) de desarrollador en Microsoft Dynamics Lifecycle Services (LCS). Para obtener más información sobre este ejemplo de integración fiscal, consulte [Ejemplo de integración de la unidad de control para Suecia](emea-swe-fi-sample.md). 

La muestra de integración fiscal de Suecia forma parte del Retail SDK. Para obtener información sobre cómo instalar y usar el SDK, consulte [Kit de desarrollo de software (SDK) al por menor](../dev-itpro/retail-sdk/retail-sdk-overview.md). Esta muestra consta de extensiones para Commerce Runtime (CRT), la estación de hardware y punto de venta (PDV). Para ejecutar este ejemplo, debe modificar y compilar el CRT, estación de hardware y proyectos de PDV. Le recomendamos que utilice un SDK para minoristas sin modificar para realizar los cambios que se describen en este artículo. También le recomendamos que utilice un sistema de control de fuente, como Azure DevOps, donde aún no se han cambiado archivos.

## <a name="development-environment"></a>Entorno de desarrollo

Siga estos pasos para configurar un entorno de desarrollo para que pueda probar y ampliar la muestra.

### <a name="enable-crt-extensions"></a>Permitir extensiones CRT

Los componentes de extensión de CRT se incluyen en los ejemplos de CRT. Para completar los siguientes procedimientos, abra la solución **CommerceRuntimeSamples.sln** bajo **RetailSdk\\SampleExtensions\\CommerceRuntime**.

#### <a name="documentprovidercleancashsample-component"></a>Componente DocumentProvider.CleanCashSample

1. Encuentre el proyecto **Runtime.Extensions.DocumentProvider.CleanCashSample** y compílelo.
2. En la carpeta **Runtime.Extensions.DocumentProvider.CleanCashSample\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll**.
3. Copie el archivo de ensamblado a la carpeta de extensiones de CRT:

    - **Commerce Scale Unit:** Copie el archivo a la carpeta **\\bin\\ext** en la ubicación del sitio de Commerce Scale Unit de Internet Information Services (IIS).
    - **CRT local en Modern POS:** Copie el archivo en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

4. Busque el archivo de configuración de la extensión para CRT:

    - **Commerce Scale Unit:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Commerce Scale Unit.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

5. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    ```

#### <a name="extension-configuration-file"></a>Archivo de configuración de la extensión

1. Busque el archivo de configuración de la extensión para CRT:

    - **Commerce Scale Unit:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Commerce Scale Unit.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

2. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

### <a name="enable-hardware-station-extensions"></a>Habilitar extensiones de la estación de hardware

Los componentes de extensión de la estación de hardware se incluyen en los ejemplos de la estación de hardware. Para completar los siguientes procedimientos, abra la solución **HardwareStationSamples.sln** bajo **RetailSdk\\SampleExtensions\\HardwareStation**.

#### <a name="cleancash-component"></a>Componente CleanCash

1. Encuentre el proyecto **HardwareStation.Extension.CleanCashSample** y compílelo.
2. En la carpeta **Extension.CleanCashSample\\bin\\Debug**, busque los archivos de ensamblado **Contoso.Commerce.HardwareStation.CleanCashSample.dll** y **Interop.CleanCash\_1\_1.dll**.
3. Copie los archivos de ensamblaje en la carpeta de extensiones de la estación de hardware:

    - **Estación de hardware compartida:** copie los archivos en la carpeta **bin** en la ubicación del sitio de la estación de hardware IIS.
    - **Estación de hardware dedicada en POS moderno:** copie los archivos en la ubicación del agente del cliente de POS de Modern.

4. Encuentre el archivo de configuración de la extensión para las extensiones de la estación de hardware. El archivo se llama **HardwareStation.Extension.config**.

    - **Estación de hardware compartida:** El archivo se encuentra en la ubicación del sitio de la estación de hardware IIS.
    - **Estación de hardware dedicada en POS moderno:** El archivo se encuentra en la ubicación del agente del cliente de POS de Modern.

5. Agregue la siguiente línea a la sección **composition** del archivo de configuración.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
    ```

### <a name="enable-modern-pos-extension-components"></a>Habilitar los componentes de la extensión Modern POS

1. Abra la solución **ModernPOS.sln** en **RetailSdk\\POS** y asegúrese de que se pueda compilar sin errores. Además, asegúrese de poder ejecutar Modern POS de Visual Studio usando el comando **Ejecutar**.

    > [!NOTE]
    > Los puntos de venta modernos no deben personalizarse. Debe habilitar el Control de cuentas de usuario (UAC) y debe desinstalar las instancias instaladas previamente de Modern POS según sea necesario.

2. Habilite las extensiones que se deben cargar agregando las siguientes líneas en el archivo **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
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
2. Habilite las extensiones que se deben cargar agregando las siguientes líneas en el archivo **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

    > [!NOTE]
    > Para obtener más información y ejemplos que muestran cómo incluir carpetas de código fuente y habilitar la carga de extensiones, consulte las instrucciones en el archivo readme.md en el proyecto **Pos.Extensions**.

3. Compile la solución.
4. Ejecute la solución utilizando el comando **Ejecutar** y siguiendo los pasos del manual Retail SDK.

## <a name="production-environment"></a>Entorno de producción

El procedimiento anterior habilita las extensiones que son componentes de la muestra de integración de la unidad de control. Además, debe seguir estos pasos para crear paquetes desplegables que contengan componentes de Commerce y aplicar esos paquetes en un entorno de producción.

1. Realice los siguientes cambios en los archivos de configuración del paquete en la carpeta **RetailSdk\\Assets**:

    - En los archivos de configuración **commerceruntime.ext.config** y **CommerceRuntime.MPOSOffline.Ext.config**, agregue las siguientes líneas a la sección **composition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
        ```

    - En el archivo de configuración **HardwareStation.Extension.config**, agregue la siguiente línea a la sección **composition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
        ```

2. Realice los siguientes cambios en el archivo de configuración de personalización del paquete **Ajustes de personalización** en la carpeta **BuildTools**:

    - Agregue la siguiente línea para incluir las extensiones CRT en los paquetes desplegables.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll" />
        ```

    - Agregue las siguientes líneas para incluir la extensión de la estación de hardware en los paquetes desplegables.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.CleanCashSample.dll" />
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Interop.CleanCash_1_1.dll" />
        ```

3. Habilite la extensión POS agregando las siguientes líneas en el archivo **extensions.json** bajo la carpeta **RetailSDK\\POS\\Extensions**.

    ``` json
    {
        "extensionPackages": [
            {
            "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

4. Inicie el símbolo del sistema de MSBuild para la utilidad Visual Studio y ejecute **msbuild** en la carpeta Retail SDK para crear paquetes implementables.
5. Aplique los paquetes a través de LCS o manualmente. Para obtener más información, consulte [Crear paquetes implementables](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
6. Complete todas las tareas de configuración necesarias que se describen en [Configurar la integración con las unidades de control](emea-swe-fi-sample.md#setting-up-the-integration-with-control-units).

## <a name="design-of-the-extensions"></a>Diseño de las extensiones

### <a name="crt-extension-design"></a>Diseño de la extensión CRT

El propósito de la extensión que es un proveedor de documentos fiscales es generar documentos específicos del servicio y manejar respuestas desde la unidad de control.

La extensión CRT es **Runtime.Extensions.DocumentProvider.CleanCashSample**.

Para obtener más información sobre el diseño de la solución de integración fiscal, consulte [Proceso de registro fiscal y ejemplos fiscales de la integración de los dispositivos y servicios fiscales](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

#### <a name="request-handler"></a>Manejador de solicitudes

Hay un solo gestor de solicitudes **DocumentProviderCleanCash** para el proveedor de documentos. Este manejador se utiliza para generar documentos fiscales para la unidad de control.

Este controlador se hereda de la interfaz **INamedRequestHandler**. El método **HandlerName** es responsable de devolver el nombre del controlador. El nombre del controlador debe coincidir con el nombre del proveedor de documentos del conector que se especifica en la sede de Comercio.

El conector admite las siguientes solicitudes:

- **GetFiscalDocumentDocumentProviderRequest** - Esta solicitud contiene información sobre qué documento se debe generar. Devuelve un documento específico del servicio que debe registrarse en la unidad de control.
- **GetSupportedRegistrableEventsDocumentProviderRequest** - Esta solicitud devuelve la lista de eventos a los que suscribirse. Actualmente, se admiten eventos de ventas y eventos de auditoría.

#### <a name="configuration"></a>Configuración

El archivo de configuración **DocumentProviderFiscalCleanCashSample** está en la carpeta **Configuración** del proyecto de extensión. El propósito de este archivo es permitir que la configuración del proveedor de documentos se configure desde la sede de Comercio. El formato de archivo está alineado con los requisitos para la configuración de integración fiscal. Se agregan los siguientes parámetros:

- Asignación de códigos de IVA

### <a name="hardware-station-extension-design"></a>Diseño de extensiones de la estación de hardware

El propósito de la extensión que es un conector fiscal es comunicarse con la unidad de control.

La extensión de la estación de hardware es **HardwareStation.Extension.CleanCashSample**. Utiliza el protocolo HTTP para enviar documentos que la extensión CRT genera a la unidad de control. También maneja las respuestas que se reciben de la unidad de control.

#### <a name="request-handler"></a>Manejador de solicitudes

El manejador de solicitudes **CleanCashHandler** es el punto de entrada para manejar las solicitudes a la unidad de control.

El controlador se hereda de la interfaz **INamedRequestHandler**. El método **HandlerName** es responsable de devolver el nombre del controlador. El nombre del controlador debe coincidir con el nombre del conector fiscal que se especifica en la sede de Commerce.

El conector admite las siguientes solicitudes:

- **SubmitDocumentFiscalDeviceRequest** - Esta solicitud envía documentos a la unidad de control y devuelve una respuesta de ella.
- **IsReadyFiscalDeviceRequest** - Esta solicitud se utiliza para una verificación de estado de la unidad de control.
- **InitializeFiscalDeviceRequest** - Esta solicitud se utiliza para inicializar la unidad de control.

#### <a name="configuration"></a>Configuración

El archivo de configuración está en la carpeta **Configuración** del proyecto de extensión. El propósito del archivo es permitir la configuración del conector fiscal desde la sede de Comercio. El formato de archivo está alineado con los requisitos para la configuración de integración fiscal. Se agregan los siguientes parámetros:

- **Cadena de conexiones** - Los ajustes de conexión de la unidad de control.
- **Se acabó el tiempo** - La cantidad de tiempo, en milisegundos, que el conductor esperará una respuesta de la unidad de control.

## <a name="migrating-from-the-earlier-integration-sample"></a>Migrar desde la muestra de integración anterior

Si está usando la anterior [muestra para la integración de POS con unidades de control para Suecia](retail-sdk-control-unit-sample.md), es posible que deba migrar de él a la muestra de integración actual. Para aceptar el cambio y recibir actualizaciones oportunas para las funciones de Suecia en el futuro, es posible que deba actualizar, realizar ajustes menores en el código y la configuración en las extensiones que creó y reconstruir sus soluciones. No se requieren cambios importantes en la lógica de extensión que creó. La muestra de integración anterior y sus personalizaciones seguirán funcionando si no se realizan cambios por su parte. Por lo tanto, puede planificar, prepararse y hacer la asimilación de su entorno.

### <a name="migration-process"></a>Proceso de migración

La migración de la muestra de integración anterior a la muestra de integración de la unidad de control actual debe basarse en el concepto de una actualización gradual. En otras palabras, todas las oficinas centrales de Comercio y los componentes de Commerce Scale Unit ya deberían estar actualizados antes de comenzar a actualizar los componentes de la estación de POS y hardware.

Para ayudar a prevenir una situación en la que un evento o transacción se firma dos veces (es decir, está firmado tanto por la extensión anterior como por la extensión actual), o donde un evento o transacción no se puede firmar debido a la configuración que falta, recomendamos que apaga todos los dispositivos POS y de la estación de hardware que utilizan la muestra anterior y, a continuación, los actualiza simultáneamente. Esta actualización simultánea se puede realizar, por ejemplo, tienda por tienda actualizando el perfil de funcionalidad de la tienda y el perfil de hardware de la estación de hardware.

El proceso de migración debe constar de los siguientes pasos.

1. Actualice los componentes de la sede de Comercio.
1. Actualice los componentes de Commerce Scale Unit y habilite las extensiones de la muestra actual.
1. Asegúrese de que todas las transacciones sin conexión estén sincronizadas desde dispositivos MPOS habilitados sin conexión.
1. Apague todos los dispositivos que utilizan los componentes de la muestra anterior.
1. Complete todas las tareas de configuración necesarias que se describen en [Configurar la integración con las unidades de control](emea-swe-fi-sample.md#setting-up-the-integration-with-control-units).
1. Actualice los componentes de la estación de hardware y POS, deshabilite las extensiones que son parte de la muestra anterior y habilite las extensiones de la muestra actual.

    > [!NOTE]
    > Dependiendo del tipo de entorno, puede encontrar más detalles técnicos sobre el proceso de migración en la sección [Migración en un entorno de desarrollo](#migration-in-a-development-environment) o la sección [Migración en un entorno de producción](#migration-in-a-production-environment) de este artículo.

### <a name="migration-in-a-development-environment"></a>Migración en un entorno de desarrollo

#### <a name="update-crt"></a>Actualizar CRT

1. Encuentre el proyecto **Runtime.Extensions.DocumentProvider.CleanCashSample** y compílelo.
2. En la carpeta **Runtime.Extensions.DocumentProvider.CleanCashSample\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll**.
3. Copie el archivo de ensamblado a la carpeta de extensiones de CRT:

    - **Commerce Scale Unit:** Copie el archivo a la carpeta **\\bin\\ext** en la ubicación del sitio de Commerce Scale Unit de IIS.
    - **CRT local en Modern POS:** Copie el archivo en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

4. Busque el archivo de configuración de la extensión para CRT:

    - **Commerce Scale Unit:** El archivo se llama **CommerceRuntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Commerce Scale Unit.
    - **CRT local en POS moderno:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la carpeta **bin\\ext** en la ubicación del agente del cliente de CRT local.

    > [!WARNING]
    > **No** edite los archivos CommerceRuntime.config y CommerceRuntime.MPOSOffline.config. Estos archivos no están pensados para ninguna personalización.

5. Busque y elimine la anterior extensión CRT del archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.FiscalRegisterReceiptSample" />
    ```

    > [!WARNING]
    > No complete este paso hasta que actualice todos los dispositivos POS que funcionan con esta instancia de CRT.

6. Registre las extensiones de CRT de ejemplo actuales en el archivo de configuración de extensión agregando las siguientes líneas.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

#### <a name="update-hardware-station"></a>Actualizar la estación de hardware

1. Encuentre el proyecto **HardwareStation.Extension.CleanCashSample** y compílelo.
2. En la carpeta **Extension.CleanCashSample\\bin\\Debug**, busque los archivos de ensamblado **Contoso.Commerce.HardwareStation.CleanCashSample.dll** y **Interop.CleanCash\_1\_1.dll**.
3. Copie los archivos de ensamblaje en la carpeta de extensiones de la estación de hardware:

    - **Estación de hardware compartida:** copie los archivos en la carpeta **bin** en la ubicación del sitio de la estación de hardware IIS.
    - **Estación de hardware dedicada en POS moderno:** copie los archivos en la ubicación del agente del cliente de POS de Modern.

4. Encuentre el archivo de configuración de extensión **HardwareStation.Extension.config**:

    - **Estación de hardware remota:** El archivo se encuentra en la ubicación del sitio de la estación de hardware IIS.
    - **Estación de hardware dedicada en Modern POS:** El archivo se encuentra en la ubicación del agente del cliente de POS de Modern.

    > [!WARNING]
    > **No** edite los archivos CommerceRuntime.config y CommerceRuntime.MPOSOffline.config. Estos archivos no están pensados para ninguna personalización.

5. Busque y elimine la anterior extensión de la estación de hardware del archivo de configuración de extensión.

    # <a name="retail-73-and-earlier"></a>[Retail 7.3 y versiones anteriores](#tab/retail-7-3)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-731-and-later"></a>[Retail 7.3.1 y versiones posteriores](#tab/retail-7-3-1)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-100-and-later"></a>[Retail 10.0 y versiones posteriores](#tab/retail-10-0)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.FiscalRegisterSample" />
    ```
    ---

6. Agregue la siguiente línea a la sección **composition** del archivo de configuración de la extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
    ```

#### <a name="update-modern-pos"></a>Actualizar Modern POS

1. Abra la solución **CloudPOS.sln** bajo **RetailSdk\\POS**.
2. Deshabilite la extensión POS anterior eliminando las siguientes líneas del archivo **extensions.json**.

    ``` json
    {
        "baseUrl": "FiscalRegisterSample"
    }
    ```

2. Habilite la extensión de PDV de ejemplo actual agregando las siguientes líneas en el archivo **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="update-cloud-pos"></a>Actualizar el PDV en la nube

1. Abra la solución **ModernPOS.sln** bajo **RetailSdk\\POS**.
2. Deshabilite la extensión POS anterior eliminando las siguientes líneas del archivo **extensions.json**.

    ``` json
    {
        "baseUrl": "FiscalRegisterSample"
    }
    ```

2. Habilite la extensión de PDV de ejemplo actual agregando las siguientes líneas en el archivo **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

### <a name="migration-in-a-production-environment"></a>Migración en un entorno de producción

#### <a name="update-crt"></a>Actualizar CRT

1. Elimine la anterior extensión de CRT de los archivos de configuración **CommerceRuntime.ext.config** y **CommerceRuntime.MPOSOffline.Ext.config** bajo la carpeta **RetailSdk\\Activos**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.FiscalRegisterReceiptSample" />
    ```

    > [!WARNING]
    > No complete este paso hasta que actualice todos los dispositivos POS que funcionan con esta instancia de CRT.

2. Habiliet las extensiones de CRT de ejemplo anteriores de los archivos de configuración **CommerceRuntime.ext.config** y **CommerceRuntime.MPOSOffline.Ext.config** bajo la carpeta **RetailSdk\\Activos**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

3. En el archivo de configuración de personalización del paquete de **Ajustes de personalización** en la carpeta **BuildTools**, agregue la siguiente línea para incluir la muestra actual de la extensión de CRT en paquetes desplegables.

    ``` xml
    <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll" />
    ```

#### <a name="update-hardware-station"></a>Actualizar la estación de hardware

1. Elimine la anterior extensión de la estación de hardware modificando el archivo de configuración **HardwareStation.Extension.config**.

    # <a name="retail-73-and-earlier"></a>[Retail 7.3 y versiones anteriores](#tab/retail-7-3)

    Quite la siguiente sección de los archivos de configuración **HardwareStation.Shared.config** y **HardwareStation.Dedicated.config**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-731-and-later"></a>[Retail 7.3.1 y versiones posteriores](#tab/retail-7-3-1)

    Quite la siguiente sección del archivo de configuración **HardwareStation.Extension.config**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-100-and-later"></a>[Retail 10.0 y versiones posteriores](#tab/retail-10-0)

    Quite la siguiente sección del archivo de configuración **HardwareStation.Extension.config**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.FiscalRegisterSample" />
    ```
    ---

2. Habilite la extensión de la estación de hardware de muestra actual agregando la siguiente línea a la sección **composition** del archivo de configuración **HardwareStation.Extension.config**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
    ```

3. Realice los siguientes cambios en el archivo de configuración de personalización del paquete **Ajustes de personalización** en la carpeta **BuildTools**:

    - Quite la siguiente línea para excluir la extensión de la estación de hardware anterior de los paquetes desplegables.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample.dll" />
        ```

    - Agregue las siguientes líneas para incluir la extensión de la estación de hardware actual en los paquetes desplegables.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.CleanCashSample.dll" />
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Interop.CleanCash_1_1.dll" />
        ```

#### <a name="update-modern-pos"></a>Actualizar Modern POS

1. Abra la solución **CloudPOS.sln** en **RetailSdk\\POS**.
2. Desactive la extensión POS anterior:

    - En el archivo **tsconfig.json**, agregue la carpeta **FiscalRegisterSample** a la lista de exclusión.
    - Quite las siguientes líneas del archivo **extensions.json** cajo la carpeta **RetailSDK\\POS\\Extensions**.

        ``` json
        {
            "baseUrl": "FiscalRegisterSample"
        }
        ```

3. Habilite la extensión de PDV de ejemplo actual agregando las siguientes líneas en el archivo **extensions.json** bajo la carpeta **RetailSDK\\POS\\Extensions**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="update-cloud-pos"></a>Actualizar el PDV en la nube

1. Abra la solución **ModernPOS.sln** bajo **RetailSdk\\POS**.
2. Desactive la extensión POS anterior:

    - En el archivo **tsconfig.json**, agregue la carpeta **FiscalRegisterSample** a la lista de exclusión.
    - Quite las siguientes líneas del archivo **extensions.json** cajo la carpeta **RetailSDK\\POS\\Extensions**.

        ``` json
        {
            "baseUrl": "FiscalRegisterSample"
        }
        ```

3. Habilite la extensión de PDV de ejemplo actual agregando las siguientes líneas en el archivo **extensions.json** bajo la carpeta **RetailSDK\\POS\\Extensions**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="create-deployable-packages"></a>Crear paquetes implementables

Ejecute **msbuild** para todo Retail SDK para crear paquetes implementables. Aplique los paquetes a través de LCS o manualmente. Para obtener más información, consulte [Paquetes de Retail SDK](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
