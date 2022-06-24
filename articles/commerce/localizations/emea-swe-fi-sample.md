---
title: Muestra de integración de unidad de control para Suecia
description: Este artículo proporciona una visión general del ejemplo de integración fiscal para Suecia en Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-10-08
ms.openlocfilehash: 11ce0b146f2e64092b0d03dc7416660d76380cd0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885411"
---
# <a name="control-unit-integration-sample-for-sweden"></a>Muestra de integración de unidad de control para Suecia

[!include [banner](../includes/banner.md)]

Este artículo proporciona una visión general del ejemplo de integración fiscal para Suecia en Microsoft Dynamics 365 Commerce.

> [!NOTE]
> Esta funcionalidad de integración fiscal de muestra reemplaza la anterior [muestra para la integración de POS con unidades de control para Suecia](retail-sdk-control-unit-sample.md). La muestra anterior no aprovecha el [marco de integración fiscal](./fiscal-integration-for-retail-channel.md) y quedará obsoleto en actualizaciones posteriores. Para obtener información sobre cómo migrar de la muestra anterior a la muestra que corresponde a Dynamics 365 Commerce versión **10.0.22 y anteriores**, vea [Migrar desde la muestra de integración anterior](emea-swe-fi-sample-sdk.md#migrating-from-the-earlier-integration-sample).

La funcionalidad de Comercio para Suecia incluye una integración de muestra del punto de venta (POS) con dispositivos fiscales específicos de Suecia que se conocen como *unidades de control*. Esta muestra extiende la [funcionalidad de integración fiscal](fiscal-integration-for-retail-channel.md). Se supone que una unidad de control está conectada físicamente a una estación de hardware con la que está emparejado el POS. Como ejemplo, esta muestra utiliza la interfaz de programación de aplicaciones (API) del [tipo CleanCash A](https://www.retailinnovation.se/produkter) unidad de control de Retail Innovation HTT AB. Se utiliza la versión 1.1.4 de la API CleanCash.

La muestra se proporciona en forma de código fuente y es parte del kit de desarrollo de software (SDK) de Retail.

Microsoft no publica ningún hardware, software o documentación de Retail Innovation HTT AB. Para obtener información sobre cómo obtener la unidad de control y operarla, comuníquese con [Innovación minorista HTT AB](https://www.retailinnovation.se/).

## <a name="scenarios"></a>Situaciones

La muestra de integración de la unidad de control para Suecia incluye las siguientes capacidades:

- Las ventas, devoluciones y copias de recibos se registran automáticamente en una unidad de control que está conectada a la estación de hardware que está emparejada con el POS.
- El código de control y el número de fabricación de la unidad de control para una transacción registrada se capturan de la unidad de control y se guardan en la transacción. Estos datos también se conocen como *respuesta fiscal*. La respuesta fiscal se puede ver en la página **Transacciones de la tienda**.
- Los campos personalizados para el código de control y el número de fabricación de la unidad de control se pueden agregar a un diseño de recibo. De esa manera, puede imprimir la respuesta fiscal de una transacción en un recibo.
- La respuesta fiscal para una transacción se muestra en el informe de canal **Revista electrónica (Suecia)**.
- Hay varias opciones de manejo de errores disponibles. A continuación, encontrará algunos ejemplos:

    - Vuelva a intentar el registro fiscal, si es posible. Puede volver a intentar el registro fiscal si, por ejemplo, la unidad de control no está conectada, no está lista o no responde.
    - Posponer registro fiscal.
    - Omita el registro fiscal o marque la transacción como registrada e incluya códigos de información para capturar el motivo del error e información adicional.
    - Verifique la disponibilidad de la unidad de control antes de que se abra una nueva transacción de venta o se finalice una transacción de venta.

### <a name="limitations-of-the-sample"></a>Limitaciones de la muestra

La muestra de integración de la unidad de control para Suecia no admite actualmente escenarios de pedidos de clientes.

## <a name="setting-up-the-integration-with-control-units"></a>Configurar la integración de POS con unidades de control

Para obtener más información sobre la configuración necesaria para Suecia, consulte [Establecimiento de Commerce para Suecia](./emea-swe-cash-registers.md#setting-up-commerce-for-sweden).

### <a name="configuring-swedenspecific-receipts"></a>Configuración de recibos específicos de Suecia

#### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Configure campos personalizados para que se puedan usar en formatos de recibo para recibos de ventas

Puede configurar el texto del idioma y los campos personalizados que se utilizan en los formatos de recibo de POS. La empresa predeterminada del usuario que crea la configuración del recibo debe ser la misma entidad legal donde se crea la configuración del texto del idioma. Alternativamente, los textos en el mismo idioma deben crearse tanto en la empresa predeterminada del usuario como en la entidad legal de la tienda para la que se creó la configuración.

Sobre la página **Texto de idioma**, agregue los siguientes registros para las etiquetas de los campos personalizados para diseños de recibos. Tenga en cuenta que los valores **ID de idioma**, **ID de texto** y **Texto** que se muestran en la tabla son solo ejemplos. Puede cambiarlos fácilmente para satisfacer sus necesidades. Sin embargo, los valores **ID de texto** que use deben ser únicos y deben ser iguales o mayores que 900001.

Agregue las siguientes etiquetas POS en la sección **POS** de la página **Texto de idioma**.

| Id. del idioma | Id. de texto | Texto                  |
|-------------|---------|-----------------------|
| en-US       | 900001  | Registrar el código de control |
| en-US       | 900002  | Registrar dispositivo       |

Sobre la página **Campos personalizados**, agregue los siguientes registros para los campos personalizados para diseños de recibos. Tenga en cuenta que los valores **ID de texto de subtítulo** deben corresponder a los valores de **ID de texto** que especificó en la página **Texto de idioma**.

| Name                         | Tipo    | Id. de texto de leyenda |
|------------------------------|---------|-----------------|
| SE_FISCALREGISTERCONTROLCODE | Recepción | 900001          |
| SE_FISCALREGISTERID          | Recepción | 900002          |

> [!NOTE]
> Es importante que especifique los nombres de campo personalizados correctos, como se indica en la tabla anterior. Un nombre de campo personalizado incorrecto hará que falten datos en los recibos.

#### <a name="configure-receipt-formats"></a>Configurar formatos de recibo

Para cada formato de recibo que es requerido, cambie el valor del campo **Comportamiento de impresión** a **Imprimir siempre**.

En el diseñador de formato de recibo, agregue los siguientes campos personalizados a la sección **Pie de página**. Tenga en cuenta que los nombres de los campos corresponden a los textos de idioma que definió en la sección anterior de este artículo.

- **Registrar código de control** - Este campo imprime el código de control.
- **Registrar dispositivo** - Este campo imprime el número de fabricación de la unidad de control.

Para obtener más información sobre cómo trabajar con formatos de recibo, consulte [Plantillas e impresión de recibos](../receipt-templates-printing.md).

### <a name="set-up-fiscal-integration-for-sweden"></a>Configurar integración fiscal para Suecia

La muestra de integración de la unidad de control para Suecia se basa en la [funcionalidad de integración fiscal](fiscal-integration-for-retail-channel.md) y es parte del SDK de Retail. La muestra se encuentra en la carpeta **src\\FiscalIntegration\\CleanCash** del repositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (por ejemplo, [la muestra en la versión/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/CleanCash)). La muestra [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) de un proveedor de documentos fiscales, que es una extensión de Commerce Runtime (CRT) y un conector fiscal, que es una extensión de Commerce Hardware Station. Para obtener más información sobre cómo usar el SDK de Retail, consulte [Arquitectura de SDK minorista](../dev-itpro/retail-sdk/retail-sdk-overview.md) y [Configurar una canalización de compilación para el SDK de empaquetado independiente](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Debido a las limitaciones del [nuevo modelo de empaquetado y extensión independiente](../dev-itpro/build-pipeline.md), actualmente no se puede utilizar para esta muestra de integración fiscal. Debe utilizar la versión anterior de Retail SDK en una máquina virtual (VM) de desarrollador en Microsoft Dynamics Lifecycle Services (LCS). Para más información, vea [Directrices de implementación para la muestra de integración de la unidad de control para Suecia (heredada)](emea-swe-fi-sample-sdk.md).
>
> El soporte para el nuevo modelo de extensión y empaquetado independiente para muestras de integración fiscal está previsto para versiones posteriores.

Complete los pasos de configuración de la integración fiscal como se describe en [Configurar la integración fiscal para los canales comerciales](setting-up-fiscal-integration-for-retail-channel.md).

1. [Configuración de un proceso de registro fiscal](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Además, tome nota de la configuración del proceso de registro fiscal que es [específico para esta muestra de integración de la unidad de control](#set-up-the-registration-process).
1. [Establecimiento de la configuración de tratamiento de errores](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Habilitar la ejecución manual del registro fisca postpuesto](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Configurar los componentes de canal](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Configuración del proceso de registro fiscal

Para habilitar el proceso de registro, siga estos pasos para configurar Commerce Headquarters. Para obtener más información, consulte [Configurar la integración fiscal para los canales de Commerce](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Descargue los archivos de configuración para el proveedor de documentos fiscales y el conector fiscal:

    1. Abra el respositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Seleccione una versión de rama de lanzamiento correcta de acuerdo con su SDK/versión de la aplicación (por ejemplo, **[lanzamiento/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Abra **src \> FiscalIntegration \> CleanCash**.
    1. Descargue el archivo de configuración del proveedor de documentos fiscales en **CommerceRuntime \> DocumentProvider.CleanCashSample \> Configuration \> DocumentProviderFiscalCleanCashSample.xml** (por ejemplo, [el archivo para la versión/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/CleanCash/CommerceRuntime/DocumentProvider.CleanCashSample/Configuration/DocumentProviderFiscalCleanCashSample.xml)).
    1. Descargue el archivo de configuración del conector fiscal en **HardwareStation \> Connector.CleanCashSample \> Configuration \> ConnectorCleanCashSample.xml** (por ejemplo, [el archivo para la versión/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/CleanCash/HardwareStation/Connector.CleanCashSample/Configuration/ConnectorCleanCashSample.xml)).

    > [!WARNING]
    > Debido a las limitaciones del [nuevo modelo de empaquetado y extensión independiente](../dev-itpro/build-pipeline.md), actualmente no se puede utilizar para esta muestra de integración fiscal. Debe utilizar la versión anterior de Retail SDK en una máquina virtual (VM) de desarrollador en LCS. Los archivos de configuración para esta muestra de integración fiscal se encuentran en las siguientes carpetas del Retail SDK en una VM de desarrollador en LCS:
    >
    > - **Archivo de configuración de proveedor de documento fiscal:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.CleanCashSample\\Configuration\\DocumentProviderFiscalCleanCashSample.xml
    > - **Archivo de configuración del conector fiscal:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.CleanCashSample\\Configuration\\ConnectorCleanCashSample.xml
    > 
    > El soporte para el nuevo modelo de extensión y empaquetado independiente para muestras de integración fiscal está previsto para versiones posteriores.

1. Vaya a **Retail y Commerce \> Configuración de sede central \> Parámetros \> Parámetros compartidos de Commerce**. En la pestaña **General**, configure la opción **Habilitar integración fiscal** en **Sí**.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Integración fiscal \> Proveedores de documentos fiscales** y cargue el archivo de configuración del proveedor de documentos fiscales que descargó antes.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Integración fiscal \> Conectores fiscales** y cargue el archivo de configuración del conector fiscal que descargó antes.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Integración fiscal \> Perfiles funcionales del conector**. Cree un nuevo perfil funcional del conector. Seleccione el proveedor de documentos y el conector que cargó anteriormente. Actualice la [configuración de mapeo de datos](#default-data-mapping) según sea necesario.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Integración fiscal \> Perfiles técnicos del conector**. Cree un nuevo perfil técnico de conector y seleccione el conector fiscal que cargó anteriormente. Actualice la [configuración del conector](#fiscal-connector-settings) según sea necesario.
6. Vaya a **Retail y Commerce \> Configuración de canal \> Integración fiscal \> Grupos de conector fiscal**. Cree un nuevo grupo de conectores fiscales para el perfil funcional de conector que creó anteriormente.
7. Vaya a **Retail y Commerce \> Configuración de canal \> Integración fiscal \> Procesos de registro fiscal**. Cree un nuevo proceso de registro fiscal y un paso de proceso de registro fiscal, y seleccione el grupo de conectores fiscales que creó anteriormente.
8. Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> Perfiles de PDV \> Perfiles de funcionalidad**. Seleccione un perfil de funcionalidad que esté vinculado a la tienda donde se debe activar el proceso de registro. Sobre la ficha desplegable **Proceso de registro fiscal**, seleccione el proceso de registro fiscal que creó anteriormente.
9. Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> Perfiles de PDV \> Perfiles de hardware**. Seleccione un perfil de hardware que esté vinculado a la estación de hardware a la que se conectará la impresora fiscal. Sobre la ficha desplegable **Periféricos fiscales**, seleccione el perfil técnico del conector que creó anteriormente.
10. Abra la programación de distribución (**Retail y Commerce \> TI de Retail y Commerce \> Programación de distribución**) y seleccione los trabajos **1070** y **1090** para transferir los datos a la base de datos del canal.

#### <a name="default-data-mapping"></a>Asignación de datos predeterminada

La siguiente asignación de datos predeterminada se incluye en la configuración del proveedor de documentos fiscales que se proporciona como parte de la muestra de integración fiscal:

- **Asignación de códigos de impuesto al valor agregado (IVA)** - Esta asignación establece los códigos de impuesto al valor agregado (IVA) específicos del dispositivo a los códigos de impuesto a las ventas correspondientes. La asignación del código de IVA debe tener el siguiente formato:

    ```
    1 : code1 ; 2 : code2
    ```

    A continuación aparece una explicación de este formato:

    - *1* y *2* son códigos de IVA específicos del dispositivo.
    - Se utiliza un punto y coma (;) como separador.
    - *código1* y *código2* son códigos de impuestos sobre las ventas que se configuran en la sede de Comercio. Debe modificar la asignación de muestra de acuerdo con los códigos de impuestos que están configurados en su aplicación.

    Las unidades de control admiten hasta cuatro códigos de IVA diferentes. Por lo tanto, la asignación del código de IVA se puede configurar de la siguiente manera:

    ```
    1 : code1 ; 2 : code2 ; 3 : code3 ; 4 : code4
    ```

    > [!NOTE]
    > Se pueden asignar varios códigos de impuestos sobre las ventas al mismo código de IVA específico del dispositivo.

#### <a name="fiscal-connector-settings"></a>Configuración del conector fiscal

La siguiente configuración se incluye en la configuración del conector fiscal que se proporciona como parte de la muestra de integración fiscal:

- **Cadena de conexiones** - Los ajustes de conexión de la unidad de control.
- **Se acabó el tiempo** - La cantidad de tiempo, en milisegundos, que el conductor esperará una respuesta de la unidad de control.

### <a name="configure-channel-components"></a>Configurar los componentes de canal

> [!WARNING]
> Debido a las limitaciones del [nuevo modelo de empaquetado y extensión independiente](../dev-itpro/build-pipeline.md), actualmente no se puede utilizar para esta muestra de integración fiscal. Debe utilizar la versión anterior de Retail SDK en una máquina virtual (VM) de desarrollador en LCS. Para más información, vea [Directrices de implementación para la muestra de integración de la unidad de control para Suecia (heredada)](emea-swe-fi-sample-sdk.md).
>
> El soporte para el nuevo modelo de extensión y empaquetado independiente para muestras de integración fiscal está previsto para versiones posteriores.

#### <a name="set-up-the-development-environment"></a>Configurar el entorno de desarrollo

Para configurar un entorno de desarrollo para probar y ampliar la muestra, siga estos pasos.

1. Clonar o descargar el repositorio de [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions). Seleccione una versión de rama de lanzamiento correcta de acuerdo con su SDK/versión de la aplicación. Para más información, vea [Descargar muestras y paquetes de referencia del SDK de Retail desde GitHub y NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Abra la solución de integración de la unidad de control en **Dynamics365Commerce.Solutions\\FiscalIntegration\\CleanCash\\CleanCash.sln** y compílela.
1. Instale las extensiones de CRT:

    1. Busque el instalador de extensiones de CRT:

        - **Commerce Scale Unit:** En la carpeta **CleanCash\\ScaleUnit\\ScaleUnit.CleanCash.Installer\\bin\\Debug\\net461**, busque el instalador **ScaleUnit.CleanCash.Installer**.
        - **CRT local en Modern POS:** En la carpeta **CleanCash\\ModernPOS\\ModernPOS.CleanCash.Installer\\bin\\Debug\\net461**, busque el instalador **ModernPOS.CleanCash.Installer**.

    2. Inicie el instalador de extensiones de CRT desde la línea de comandos:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.CleanCash.Installer.exe install --verbosity 0
            ```

        - **CRT local en Modern POS:**

            ```Console
            ModernPOS.CleanCash.Installer.exe install --verbosity 0
            ```

1. Instale las extensiones de la estación de hardware:

    1. En la carpeta **CleanCash\\HardwareStation\\HardwareStation.CleanCash.Installer\\bin\\Debug\\net461**, busque el instalador **HardwareStation.CleanCash.Installer**.
    1. Inicie el instalador de extensiones desde la línea de comandos:

        ```Console
        HardwareStation.CleanCash.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Entorno de producción

Siga los pasos en [Configurar una canalización de compilación para una muestra de integración fiscal](fiscal-integration-sample-build-pipeline.md) para generar y lanzar la unidad de escala en la nube y los paquetes implementables de autoservicio para la muestra de integración fiscal. El archivo YAML de plantilla **CleanCash build-pipeline.yml** se puede encontrar en la carpeta **Pipeline\\YAML_Files** del repositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-the-extensions"></a>Diseño de las extensiones

La muestra de integración de la unidad de control para Suecia se basa en la [funcionalidad de integración fiscal](fiscal-integration-for-retail-channel.md) y es parte del SDK de Retail. La muestra se encuentra en la carpeta **src\\FiscalIntegration\\CleanCash** del repositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (por ejemplo, [la muestra en la versión/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/CleanCash)). La muestra [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) de un proveedor de documentos fiscales, que es una extensión de CRT y un conector fiscal, que es una extensión de Commerce Hardware Station. Para obtener más información sobre cómo usar el SDK de Retail, consulte [Arquitectura de SDK minorista](../dev-itpro/retail-sdk/retail-sdk-overview.md) y [Configurar una canalización de compilación para el SDK de empaquetado independiente](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Debido a las limitaciones del [nuevo modelo de empaquetado y extensión independiente](../dev-itpro/build-pipeline.md), actualmente no se puede utilizar para esta muestra de integración fiscal. Debe utilizar la versión anterior de Retail SDK en una máquina virtual (VM) de desarrollador en LCS. Para más información, vea [Directrices de implementación para la muestra de integración de la unidad de control para Suecia (heredada)](emea-swe-fi-sample-sdk.md). El soporte para el nuevo modelo de extensión y empaquetado independiente para muestras de integración fiscal está previsto para versiones posteriores.

### <a name="crt-extension-design"></a>Diseño de la extensión CRT

El propósito de la extensión que es un proveedor de documentos fiscales es generar documentos específicos del servicio y manejar respuestas desde la unidad de control.

#### <a name="request-handler"></a>Manejador de solicitudes

Hay un solo gestor de solicitudes **DocumentProviderCleanCash** para el proveedor de documentos. Este manejador se utiliza para generar documentos fiscales para la unidad de control.

Este controlador se hereda de la interfaz **INamedRequestHandler**. El método **HandlerName** es responsable de devolver el nombre del controlador. El nombre del controlador debe coincidir con el nombre del proveedor de documentos del conector que se especifica en la sede de Comercio.

El conector admite las siguientes solicitudes:

- **GetFiscalDocumentDocumentProviderRequest** - Esta solicitud contiene información sobre qué documento se debe generar. Devuelve un documento específico del servicio que debe registrarse en la unidad de control.
- **GetSupportedRegistrableEventsDocumentProviderRequest** - Esta solicitud devuelve la lista de eventos a los que suscribirse. Actualmente, se admiten eventos de ventas y eventos de auditoría.

#### <a name="configuration"></a>Configuración

El archivo de configuración para el proveedor de documentos fiscales se encuentra en **src\\FiscalIntegration\\CleanCash\\CommerceRuntime\\DocumentProvider.CleanCashSample\\Configuration\\DocumentProviderFiscalCleanCashSample.xml** en el repositorio de [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). El propósito de este archivo es permitir que la configuración del proveedor de documentos se configure desde la sede de Comercio. El formato de archivo está alineado con los requisitos para la configuración de integración fiscal.

### <a name="hardware-station-extension-design"></a>Diseño de extensiones de la estación de hardware

El propósito de la extensión que es un conector fiscal es comunicarse con la unidad de control. Utiliza el protocolo HTTP para enviar documentos que la extensión CRT genera a la unidad de control. También maneja las respuestas que se reciben de la unidad de control.

#### <a name="request-handler"></a>Manejador de solicitudes

El manejador de solicitudes **CleanCashHandler** es el punto de entrada para manejar las solicitudes a la unidad de control.

El controlador se hereda de la interfaz **INamedRequestHandler**. El método **HandlerName** es responsable de devolver el nombre del controlador. El nombre del controlador debe coincidir con el nombre del conector fiscal que se especifica en la sede de Commerce.

El conector admite las siguientes solicitudes:

- **SubmitDocumentFiscalDeviceRequest** - Esta solicitud envía documentos a la unidad de control y devuelve una respuesta de ella.
- **IsReadyFiscalDeviceRequest** - Esta solicitud se utiliza para una verificación de estado de la unidad de control.
- **InitializeFiscalDeviceRequest** - Esta solicitud se utiliza para inicializar la unidad de control.

#### <a name="configuration"></a>Configuración

El archivo de configuración para el conector fiscal se encuentra en **src\\FiscalIntegration\\CleanCash\\HardwareStation\\Connector.CleanCashSample\\Configuration\\ConnectorCleanCashSample.xml** en el repositorio de [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). El propósito del archivo es permitir la configuración del conector fiscal desde la sede de Comercio. El formato de archivo está alineado con los requisitos para la configuración de integración fiscal.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
