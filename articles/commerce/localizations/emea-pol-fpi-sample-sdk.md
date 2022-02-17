---
title: Directrices de implementación para la muestra de integración de la impresora fiscal para Polonia (heredada)
description: Este tema proporciona pautas para implementar la muestra de integración de impresora fiscal para Polonia desde el Kit de desarrollo de software (SDK) para minoristas de Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: 45cae498df8157b9561c54e9859daadcaedd7823
ms.sourcegitcommit: 5cefe7d2a71c6f220190afc3293e33e2b9119685
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2022
ms.locfileid: "8076997"
---
# <a name="deployment-guidelines-for-the-fiscal-printer-integration-sample-for-poland-legacy"></a>Directrices de implementación para la muestra de integración de la impresora fiscal para Polonia (heredada)

[!include[banner](../includes/banner.md)]

Este tema proporciona pautas para implementar la muestra de integración de la impresora fiscal para Polonia desde el kit de desarrollo de software (SDK) para minoristas de Microsoft Dynamics 365 Commerce en una máquina virtual (VM) de desarrollador en Microsoft Dynamics Lifecycle Services (LCS). Para obtener más información sobre este ejemplo de integración fiscal, consulte el [ejemplo de integración de la impresora fiscal para Polonia](emea-pol-fpi-sample.md). 

La muestra de integración fiscal de Polonia forma parte del Retail SDK. Para obtener información sobre cómo instalar y usar el SDK, consulte [Kit de desarrollo de software (SDK) al por menor](../dev-itpro/retail-sdk/retail-sdk-overview.md). Esta muestra consta de extensiones para Commerce Runtime (CRT) y la estación de hardware. Para ejecutar este ejemplo, debe modificar y compilar los proyectos de CRT y la estación de hardware. Le recomendamos que utilice un SDK para minoristas sin modificar para realizar los cambios que se describen en este tema. También le recomendamos que utilice un sistema de control de fuente, como Azure DevOps, donde aún no se han cambiado archivos.

## <a name="development-environment"></a>Entorno de desarrollo

Siga estos pasos para configurar un entorno de desarrollo para que pueda probar y ampliar la muestra.

### <a name="commerce-runtime-extension-components"></a>Componentes de extensión de Commerce Runtime

Los componentes de extensión de CRT se incluyen en el SDK de Retail. Para completar los siguientes procedimientos, abra la solución **CommerceRuntimeSamples.sln** bajo **RetailSdk\\SampleExtensions\\CommerceRuntime**.

1. Encuentre el proyecto **Runtime.Extensions.DocumentProvider.PosnetSample** y compílelo.
2. En la carpeta **Extensions.DocumentProvider.PosnetSample\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample.dll**.
3. Copie el archivo de ensamblado a la carpeta de extensiones de CRT:

    - **Commerce Scale Unit:** Copie el archivo a la carpeta **\\bin\\ext** en la ubicación del sitio de Commerce Scale Unit de Internet Information Services (IIS).
    - **CRT local en Modern POS:** Copie el archivo en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

4. Busque el archivo de configuración de la extensión para CRT:

    - **Commerce Scale Unit:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Commerce Scale Unit.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

5. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample" />
    ```

6. Reinicie el servicio Commerce:

    - **Commerce Scale Unit:** Reinicie el sitio del servicio Commerce desde el Administrador de IIS.
    - **Corredor de clientes:** Termine el proceso de **dllhost.exe** en el Administrador de tareas y luego reinicie Modern POS.

### <a name="hardware-station-extension-components"></a>Componentes de extensiones de la estación de hardware

Los componentes de extensión de la estación de hardware se incluyen en el SDK de Retail. Para completar los siguientes procedimientos, abra la solución **HardwareStationSamples.sln** bajo **RetailSdk\\SampleExtensions\\HardwareStation**.

1. Encuentre el proyecto **HardwareStation.Extension.PosnetThermalFVFiscalPrinterSample** y compílelo.
2. En la carpeta **Extension.Posnet.ThermalFVFiscalPrinterSample\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample.dll**.
3. Copie el archivo de ensamblaje en una máquina de estación de hardware implementada:

    - **Estación de hardware remota:** copie el archivo en la carpeta **bin** en la ubicación del sitio de la estación de hardware IIS. Copie las bibliotecas de controladores de impresora (**libposcmbth.dll**, **libcmbth\_serial.dll** y **cmbth\_pl.lng**).

4. Encuentre el archivo de configuración para las extensiones de la estación de hardware. El archivo se llama **HardwareStation.Extension.config**:

    - **Estación de hardware remota:** El archivo se encuentra en la ubicación del sitio de la estación de hardware IIS.

5. Agregue la siguiente línea a la sección **composition** del archivo de configuración.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample" />
    ```

6. Reinicie el servicio de la estación de hardware:

    - **Estación de hardware remota:** Reinicie el sitio de la estación de hardware desde el Administrador de IIS.

## <a name="production-environment"></a>Entorno de producción

En el procedimiento anterior, habilitó las extensiones que son componentes de la muestra de integración del servicio de integración fiscal. Además, debe seguir estos pasos para crear paquetes desplegables que contengan componentes de Commerce y aplicar esos paquetes en un entorno de producción.

1. Realice los siguientes cambios en los archivos de configuración del paquete en la carpeta **RetailSdk\\Assets**:

    - En los archivos de configuración **commerceruntime.ext.config** y **CommerceRuntime.MPOSOffline.Ext.config**, agregue la siguiente línea a la sección **composition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample" />
        ```

    - En el archivo de configuración **HardwareStation.Extension.config**, agregue la siguiente línea a la sección **composition**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample" />
        ```

1. Realice los siguientes cambios en el archivo de configuración de personalización del paquete **Ajustes de personalización** en la carpeta **BuildTools**:

    - Agregue la siguiente línea para incluir la extensión CRT en los paquetes desplegables.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample.dll"/>
        ```

    - Agregue la siguiente línea para incluir la extensión de la estación de hardware en los paquetes desplegables.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample.dll"/>
        ```

1. Inicie el símbolo del sistema de MSBuild para la utilidad Visual Studio y ejecute **msbuild** en la carpeta Retail SDK para crear paquetes implementables.
1. Aplique los paquetes a través de LCS o manualmente. Para obtener más información, consulte [Crear paquetes implementables](../dev-itpro/retail-sdk/retail-sdk-packaging.md).

## <a name="design-of-extensions"></a>Diseño de las extensiones

La muestra de integración de impresora fiscal para Polonia se basa en la [funcionalidad de integración fiscal](fiscal-integration-for-retail-channel.md). Para obtener más información acerca del diseño de la solución de integración fiscal, consulte [Visión general de un diseño de ejemplo de integración fiscal](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

### <a name="commerce-runtime-extension-design"></a>Diseño de extensión de Commerce Runtime

El propósito de la extensión que es un proveedor de documentos fiscales es generar documentos específicos de la impresora y manejar respuestas desde la impresora fiscal.

La extensión CRT es **Runtime.Extensions.DocumentProvider.PosnetSample**. Esta extensión genera un conjunto de comandos específicos de la impresora en formato de notación de objetos JavaScript (JSON) que están definidos por la especificación POSNET 19-3678.

Para obtener más información sobre el diseño de la solución de integración fiscal, consulte [Proceso de registro fiscal y ejemplos fiscales de la integración de los dispositivos y servicios fiscales](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

#### <a name="request-handler"></a>Manejador de solicitudes

El gestor de solicitudes **DocumentProviderPosnetProtocol** es el punto de entrada de la solicitud para generar documentos desde la impresora fiscal.

El controlador se hereda de la interfaz **INamedRequestHandler**. El método **HandlerName** es responsable de devolver el nombre del controlador. El nombre del controlador debe coincidir con el nombre del proveedor de documentos del conector que se especifica en la sede de Comercio.

El conector admite las siguientes solicitudes:

- **GetFiscalDocumentDocumentProviderRequest** - Esta solicitud contiene información sobre qué documento se debe generar. Devuelve un documento específico de la impresora que debe registrarse en la impresora fiscal.
- **GetSupportedRegistrableEventsDocumentProviderRequest** - Esta solicitud devuelve la lista de eventos a los que suscribirse. Actualmente, se admiten los siguientes eventos: ventas, impresión del informe X e impresión del informe Z.

#### <a name="configuration"></a>Configuración

El archivo de configuración se encuentra en la carpeta **Configuración** del proyecto de extensión. El propósito del archivo es permitir que la configuración del proveedor de documentos se configure desde la sede de Comercio. El formato de archivo está alineado con los requisitos para la configuración de integración fiscal. Se agregan los siguientes parámetros:

- Asignación de tasas de IVA
- Asignación de tipos de forma de pago
- Tipo de pago de depósito

### <a name="hardware-station-extension-design"></a>Diseño de extensiones de la estación de hardware

El propósito de la extensión que es un conector fiscal es comunicarse con la impresora fiscal.

La extensión de la estación de hardware es **HardwareStation.Extension.PosnetThermalFVFiscalPrinterSample**. Esta extensión llama a las funciones del controlador POSNET para enviar comandos que la extensión CRT genera a la impresora fiscal. También maneja errores de dispositivo.

#### <a name="request-handler"></a>Manejador de solicitudes

El gestor de solicitudes **FiscalPrinterHandler** es el punto de entrada para gestionar las solicitudes al dispositivo periférico fiscal.

El controlador se hereda de la interfaz **INamedRequestHandler**. El método **HandlerName** es responsable de devolver el nombre del controlador. El nombre del controlador debe coincidir con el nombre del conector fiscal que se especifica en la sede de Commerce.

El conector admite las siguientes solicitudes:

- **SubmitDocumentFiscalDeviceRequest** - Esta solicitud envía documentos a las impresoras y devuelve la respuesta de la impresora fiscal.
- **IsReadyFiscalDeviceRequest** - Esta solicitud se utiliza para una verificación de estado del dispositivo.
- **InitializeFiscalDeviceRequest** - Esta solicitud se utiliza para inicializar la impresora.

#### <a name="configuration"></a>Configuración

El archivo de configuración se encuentra en la carpeta **Configuración** del proyecto de extensión. El propósito del archivo es permitir la configuración para el conector fiscal desde la sede de Commerce. El formato de archivo está alineado con los requisitos para la configuración de integración fiscal. Se agregan los siguientes parámetros:

- **Cadena de conexión** - Una cadena que describe los detalles de la conexión al dispositivo en un formato compatible con el controlador. Para obtener más información, consulte la documentación del controlador POSNET.
- **Sincronización de fecha y hora** - Un valor que especifica si la fecha y la hora de la impresora deben sincronizarse con la estación de hardware conectada.
- **Tiempo de espera de dispositivo** - La cantidad de tiempo, en milisegundos, que el conductor esperará una respuesta del dispositivo. Para obtener más información, consulte la documentación del controlador POSNET.
