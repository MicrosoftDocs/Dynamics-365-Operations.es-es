---
title: Ejemplo de integración de impresora fiscal para Polonia
description: Este tema proporciona una visión general del ejemplo de integración fiscal para Polonia en Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-2-1
ms.openlocfilehash: 1b3d7d59494b215ae47f710e200e7e0c57e4ca29
ms.sourcegitcommit: 0d2de52e12fdb9928556d37a4813a67b303695dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2021
ms.locfileid: "7944874"
---
# <a name="fiscal-printer-integration-sample-for-poland"></a>Ejemplo de integración de impresora fiscal para Polonia

[!include[banner](../includes/banner.md)]

Este tema proporciona una visión general del ejemplo de integración fiscal para Polonia en Microsoft Dynamics 365 Commerce.

La funcionalidad de Dynamics 365 Commerce para Polonia incluye una integración de muestra del punto de venta (POS) con una impresora fiscal. La muestra extiende la [funcionalidad de integración fiscal](fiscal-integration-for-retail-channel.md) y admite el protocolo POSNET THERMAL HD 2.02 para impresoras fiscales de [Posnet Polska SA.](https://www.posnet.com.pl) La muestra permite la comunicación con una impresora fiscal que está conectada a través de un puerto COM mediante un controlador de software nativo. Se implementó y probó utilizando un emulador de software que Posnet proporcionó para la impresora fiscal Posnet Thermal HD FV EJ. La muestra se proporciona en forma de código fuente y es parte del kit de desarrollo de software (SDK) de Retail.

Microsoft no publica ningún hardware, software o documentación de Posnet. Para obtener información sobre cómo obtener la impresora fiscal y operarla, comuníquese con [Posnet Polska S.A.](https://www.posnet.com.pl)

## <a name="scenarios"></a>Situaciones

Los siguientes escenarios están cubiertos por la muestra de integración de impresoras fiscales para Polonia:

- Escenarios de ventas:

    - Imprima un recibo fiscal para ventas y devoluciones en efectivo y transporte.
    - Capture una respuesta de la impresora fiscal y almacénela en la base de datos del canal.
    - Impuestos:

        - Asignar a los códigos de impuestos de la impresora fiscal (departamentos).
        - Transfiera los datos impositivos asignados a la impresora fiscal.

    - Pagos:

        - Mapa de los métodos de pago de la impresora fiscal.
        - Imprima pagos en un recibo fiscal.
        - Imprimir información de cambio.

    - Imprimir descuentos de línea.
    - Tarjetas regalo:

        - Excluya una línea de tarjeta de regalo emitida / recargada de un recibo fiscal de una venta.
        - Imprima un pago que utilice una tarjeta de regalo como método de pago habitual.

    - Imprima recibos fiscales para operaciones de pedidos de clientes:

        - No se imprime un recibo fiscal para el depósito de un pedido de cliente.
        - Imprima un recibo fiscal para las líneas para llevar de un pedido de cliente híbrido.
        - Imprima un recibo fiscal para la operación de recolección de un pedido de cliente.
        - Imprima un recibo fiscal para una orden de devolución.

    - Imprima la [información del cliente](emea-pol-customer-information.md) que se especifica para una transacción de venta en un recibo fiscal. Un ejemplo de esta información es el número de IVA del cliente.

- Extractos de fin de día (informes fiscal X y fiscal Z).
- Manejo de errores, como las siguientes opciones:

    - Vuelva a intentar el registro fiscal si es posible hacerlo, por ejemplo, si la impresora fiscal no está conectada, no está lista o no responde, la impresora no tiene papel o hay un atasco de papel.
    - Posponer registro fiscal.
    - Omita el registro fiscal o marque la transacción como registrada e incluya códigos de información para capturar el motivo del error e información adicional.
    - Compruebe la disponibilidad de la impresora fiscal antes de que se abra una nueva transacción de venta o se finalice una transacción de venta.

### <a name="gift-cards"></a>Tarjetas regalo

El ejemplo de integración de la impresora fiscal implementa las siguientes reglas relacionadas con las tarjetas de regalo:

- Excluya las líneas de ventas relacionadas con las operaciones *Emitir tarjeta de regalo* y *Agregar a la tarjeta de regalo* del recibo fiscal.
- No imprima un recibo fiscal si solo consta de líneas de tarjetas de regalo.
- Deduzca la cantidad total de tarjetas de regalo que se emiten o recargan en una transacción de las líneas de pago del recibo fiscal.
- Guarde los ajustes calculados de las líneas de pago en la base de datos del canal con una referencia a una transacción fiscal correspondiente.
- El pago con tarjeta de regalo se considera un pago regular.

### <a name="customer-deposits-and-customer-order-deposits"></a>Depósitos de clientes y depósitos de pedidos de clientes

El ejemplo de integración de la impresora fiscal implementa las siguientes reglas relacionadas con los depósitos de clientes y depósitos de órdenes de clientes:

- No imprima un recibo fiscal si una transacción es un depósito de un cliente.
- No imprima un recibo fiscal si una transacción contiene solo un depósito de pedido de cliente o un reembolso de depósito de pedido de cliente.
- Imprima el monto del depósito pagado anteriormente en un recibo fiscal para una operación de recolección de pedidos de un cliente.
- Reste el monto del depósito del pedido del cliente de las líneas de pago cuando se crea un pedido híbrido del cliente.
- Guarde los ajustes calculados de las líneas de pago en la base de datos del canal con una referencia a una transacción fiscal para un pedido de cliente híbrido.

### <a name="limitations-of-the-sample"></a>Limitaciones de la muestra

- La impresora fiscal solo admite escenarios en los que el impuesto sobre las ventas está incluido en el precio. Por lo tanto, la opción **El precio incluye el impuesto a las ventas** debe establecerse en **Sí** tanto para tiendas como para clientes.
- Los informes diarios (fiscal X y fiscal Z) se imprimen utilizando el formato *Informe de turno*.
- La impresión de un código de barras en los recibos fiscales se considera una personalización potencial, porque esta función no es compatible con los formatos incrustados y solo se puede implementar mediante el uso del informe personalizable **Superformato**.
- La impresora fiscal no admite transacciones mixtas. La opción **Prohibir mezclar ventas y devoluciones en un solo recibo** debe establecerse en **Sí** en perfiles de funcionalidad POS.

## <a name="set-up-fiscal-integration-for-poland"></a>Configurar integración fiscal para Polonia

La muestra de integración de impresora fiscal para Polonia se basa en la [funcionalidad de integración fiscal](fiscal-integration-for-retail-channel.md) y es parte del SDK de Retail. La muestra se encuentra en la carpeta **src\\FiscalIntegration\\Posnet** del repositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (por ejemplo, [la muestra en la versión/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Posnet)). La muestra [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) de un proveedor de documentos fiscales, que es una extensión de Commerce Runtime (CRT) y un conector fiscal, que es una extensión de Commerce Hardware Station. Para obtener más información sobre cómo usar el SDK de Retail, consulte [Arquitectura de SDK minorista](../dev-itpro/retail-sdk/retail-sdk-overview.md) y [Configurar una canalización de compilación para el SDK de empaquetado independiente](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Debido a las limitaciones del [nuevo modelo de empaquetado y extensión independiente](../dev-itpro/build-pipeline.md), actualmente no se puede utilizar para esta muestra de integración fiscal. Debe utilizar la versión anterior de Retail SDK en una máquina virtual (VM) de desarrollador en Microsoft Dynamics Lifecycle Services (LCS). Para más información, vea [Directrices de implementación para la muestra de integración de la impresora fiscal para Polonia (heredada)](emea-pol-fpi-sample-sdk.md).
>
> El soporte para el nuevo modelo de extensión y empaquetado independiente para muestras de integración fiscal está previsto para versiones posteriores.

Complete los pasos de configuración de la integración fiscal como se describe en [Configurar la integración fiscal para los canales comerciales](setting-up-fiscal-integration-for-retail-channel.md).

1. [Configuración de un proceso de registro fiscal](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Además, tome nota de la configuración del proceso de registro fiscal que es [específico para esta muestra de integración de la impresora fiscal](#set-up-the-registration-process).
1. [Establecimiento de la configuración de tratamiento de errores](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Configuración de informes X/Z fiscales de PDV](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
1. [Habilitar la ejecución manual del registro fisca postpuesto](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Configurar los componentes de canal](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Configuración del proceso de registro fiscal

Para habilitar el proceso de registro, siga estos pasos para configurar Commerce Headquarters. Para obtener más información, consulte [Configurar la integración fiscal para los canales de Commerce](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Descargue los archivos de configuración para el proveedor de documentos fiscales y el conector fiscal:

    1. Abra el respositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Seleccione una versión de rama de lanzamiento correcta de acuerdo con su SDK/versión de la aplicación (por ejemplo, **[lanzamiento/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Abra **src \> FiscalIntegration \> Posnet**.
    1. Descargue el archivo de configuración del proveedor de documentos fiscales en **CommerceRuntime \> DocumentProvider.PosnetSample \> Configuration \> DocumentProviderPosnetSample.xml** (por ejemplo, [el archivo para la versión/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Posnet/CommerceRuntime/DocumentProvider.PosnetSample/Configuration/DocumentProviderPosnetSample.xml)).
    1. Descargue el archivo de configuración del conector fiscal en **HardwareStation \> ThermalDeviceSample \> Configuration \> ConnectorPosnetThermalFVEJ.xml** (por ejemplo, [el archivo para la versión/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Posnet/HardwareStation/ThermalDeviceSample/Configuration/ConnectorPosnetThermalFVEJ.xml)).

    > [!WARNING]
    > Debido a las limitaciones del [nuevo modelo de empaquetado y extensión independiente](../dev-itpro/build-pipeline.md), actualmente no se puede utilizar para esta muestra de integración fiscal. Debe utilizar la versión anterior de Retail SDK en una máquina virtual (VM) de desarrollador en LCS. Los archivos de configuración para esta muestra de integración fiscal se encuentran en las siguientes carpetas del Retail SDK en una VM de desarrollador en LCS:
    >
    > - **Archivo de configuración de proveedor de documento fiscal:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extension.DocumentProvider.PosnetSample\\Configuration\\DocumentProviderPosnetSample.xml
    > - **Archivo de configuración del conector fiscal:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.Posnet.ThermalDeviceSample\\Configuration\\ConnectorPosnetThermalFVEJ.xml
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

- **Mapeo de tasas de impuesto al valor agregado (IVA)** - La asignación de valores porcentuales de impuestos que se configuran para los códigos de impuestos sobre las ventas a las tasas de IVA específicas de la impresora fiscal. Aquí está la asignación predeterminada:

    ```
    0 : 23.00 ; 1 : 8.00 ; 2 : 5.00 ; 3 : 0.00
    ```

    El primer componente de cada par representa un número de tasa de IVA que se configura en la impresora fiscal. El segundo componente representa la tasa de IVA correspondiente. Para obtener más información sobre la configuración de la tasa de IVA de la impresora fiscal, consulte la documentación del controlador POSNET.

- **Mapeo de tipo de licitación** - El mapeo de los métodos de pago que están configurados para la tienda a los formatos de pago que admite la impresora fiscal. Aquí está la asignación predeterminada:

    ```
    0 : 0 ; 1 : 0 ; 2 : 2 ; 3 : 2 ; 4 : 0 ; 5 : 0 ; 6 : 0 ; 7 : 2 ; 8 : 0
    ```

    El primer componente de cada par representa un método de pago configurado para la tienda. El segundo componente representa el formato de pago correspondiente que es compatible con la impresora fiscal. Para obtener más información sobre los formularios de pago que admite la impresora fiscal, consulte la documentación del controlador POSNET. Debe modificar la asignación de muestra de acuerdo con los métodos de pago que están configurados en su aplicación.

#### <a name="fiscal-connector-settings"></a>Configuración del conector fiscal

La siguiente configuración se incluye en la configuración del conector fiscal que se proporciona como parte de la muestra de integración fiscal:

- **Cadena de conexión** - Una cadena que describe los detalles de la conexión al dispositivo en un formato compatible con el controlador. Para obtener más información, consulte la documentación del controlador POSNET.
- **Sincronización de fecha y hora** - Un valor que especifica si la fecha y la hora de la impresora deben sincronizarse con la estación de hardware conectada.
- **Tiempo de espera de dispositivo** - La cantidad de tiempo, en milisegundos, que el conductor esperará una respuesta del dispositivo. Para obtener más información, consulte la documentación del controlador POSNET.

### <a name="configure-channel-components"></a>Configurar los componentes de canal

> [!WARNING]
> Debido a las limitaciones del [nuevo modelo de empaquetado y extensión independiente](../dev-itpro/build-pipeline.md), actualmente no se puede utilizar para esta muestra de integración fiscal. Debe utilizar la versión anterior de Retail SDK en una máquina virtual (VM) de desarrollador en LCS. Para más información, vea [Directrices de implementación para la muestra de integración de la impresora fiscal para Polonia (heredada)](emea-pol-fpi-sample-sdk.md).
>
> El soporte para el nuevo modelo de extensión y empaquetado independiente para muestras de integración fiscal está previsto para versiones posteriores.

#### <a name="set-up-the-development-environment"></a>Configurar el entorno de desarrollo

Para configurar un entorno de desarrollo para probar y ampliar la muestra, siga estos pasos.

1. Clonar o descargar el repositorio de [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions). Seleccione una versión de rama de lanzamiento correcta de acuerdo con su SDK/versión de la aplicación. Para más información, vea [Descargar muestras y paquetes de referencia del SDK de Retail desde GitHub y NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Abra la solución de integración de impresora fiscal en **Dynamics365Commerce.Solutions\\FiscalIntegration\\Posnet\\Posnet.sln** y compílela.
1. Instale las extensiones de CRT:

    1. Busque el instalador de extensiones de CRT:

        - **Commerce Scale Unit:** En la carpeta **Posnet\\ScaleUnit\\ScaleUnit.Posnet.Installer\\bin\\Debug\\net461**, busque el instalador **ScaleUnit.Posnet.Installer**.
        - **CRT local en Modern POS:** En la carpeta **Posnet\\ModernPOS\\ModernPOS.Posnet.Installer\\bin\\Debug\\net461**, busque el instalador **ModernPOS.Posnet.Installer**.

    1. Inicie el instalador de extensiones de CRT desde la línea de comandos:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.Posnet.Installer.exe install --verbosity 0
            ```

        - **CRT local en Modern POS:**

            ```Console
            ModernPOS.Posnet.Installer.exe install --verbosity 0
            ```

1. Instale las extensiones de la estación de hardware:

    1. En la carpeta **Posnet\\HardwareStation\\HardwareStation.PosnetThermalFVFiscalPrinter.Installer\\bin\\Debug\\net461** carpeta, busque el instalador **HardwareStation.PosnetThermalFVFiscalPrinter.Installer**.
    1. Inicie el instalador de extensiones desde la línea de comandos:

        ```Console
        HardwareStation.PosnetThermalFVFiscalPrinter.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Entorno de producción

Siga los pasos en [Configurar una canalización de compilación para una muestra de integración fiscal](fiscal-integration-sample-build-pipeline.md) para generar y lanzar la unidad de escala en la nube y los paquetes implementables de autoservicio para la muestra de integración fiscal. El archivo YAML de plantilla **Posnet build-pipeline.yml** se puede encontrar en la carpeta **Pipeline\\YAML_Files** del repositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-extensions"></a>Diseño de las extensiones

La muestra de integración de impresora fiscal para Polonia se basa en la [funcionalidad de integración fiscal](fiscal-integration-for-retail-channel.md) y es parte del SDK de Retail. La muestra se encuentra en la carpeta **src\\FiscalIntegration\\Posnet** del repositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (por ejemplo, [la muestra en la versión/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Posnet)). La muestra [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) de un proveedor de documentos fiscales, que es una extensión de CRT y un conector fiscal, que es una extensión de Commerce Hardware Station. Para obtener más información sobre cómo usar el SDK de Retail, consulte [Arquitectura de SDK minorista](../dev-itpro/retail-sdk/retail-sdk-overview.md) y [Configurar una canalización de compilación para el SDK de empaquetado independiente](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Debido a las limitaciones del [nuevo modelo de empaquetado y extensión independiente](../dev-itpro/build-pipeline.md), actualmente no se puede utilizar para esta muestra de integración fiscal. Debe utilizar la versión anterior de Retail SDK en una máquina virtual (VM) de desarrollador en LCS. Para más información, vea [Directrices de implementación para la muestra de integración de la impresora fiscal para Polonia (heredada)](emea-pol-fpi-sample-sdk.md). El soporte para el nuevo modelo de extensión y empaquetado independiente para muestras de integración fiscal está previsto para versiones posteriores.

### <a name="commerce-runtime-extension-design"></a>Diseño de extensión de Commerce Runtime

El propósito de la extensión que es un proveedor de documentos fiscales es generar documentos específicos de la impresora y manejar respuestas desde la impresora fiscal. Esta extensión genera un conjunto de comandos específicos de la impresora en formato de notación de objetos JavaScript (JSON) que están definidos por la especificación POSNET 19-3678.

#### <a name="request-handler"></a>Manejador de solicitudes

El gestor de solicitudes **DocumentProviderPosnetProtocol** es el punto de entrada de la solicitud para generar documentos desde la impresora fiscal.

El controlador se hereda de la interfaz **INamedRequestHandler**. El método **HandlerName** es responsable de devolver el nombre del controlador. El nombre del controlador debe coincidir con el nombre del proveedor de documentos del conector que se especifica en la sede de Comercio.

El conector admite las siguientes solicitudes:

- **GetFiscalDocumentDocumentProviderRequest** - Esta solicitud contiene información sobre qué documento se debe generar. Devuelve un documento específico de la impresora que debe registrarse en la impresora fiscal.
- **GetSupportedRegistrableEventsDocumentProviderRequest** - Esta solicitud devuelve la lista de eventos a los que suscribirse. Actualmente, se admiten los siguientes eventos: ventas, impresión del informe X e impresión del informe Z.

#### <a name="configuration"></a>Configuración

El archivo de configuración para el proveedor de documentos fiscales se encuentra en **src\\FiscalIntegration\\Posnet\\CommerceRuntime\\DocumentProvider.PosnetSample\\Configuration\\DocumentProviderPosnetSample.xml** en el repositorio de [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). El propósito del archivo es permitir que la configuración del proveedor de documentos fiscales se configure desde la sede de Comercio. El formato de archivo está alineado con los requisitos para la configuración de integración fiscal.

### <a name="hardware-station-extension-design"></a>Diseño de extensiones de la estación de hardware

El propósito de la extensión que es un conector fiscal es comunicarse con la impresora fiscal. Esta extensión llama a las funciones del controlador POSNET para enviar comandos que la extensión CRT genera a la impresora fiscal. También maneja errores de dispositivo.

#### <a name="request-handler"></a>Manejador de solicitudes

El gestor de solicitudes **FiscalPrinterHandler** es el punto de entrada para gestionar las solicitudes al dispositivo periférico fiscal.

El controlador se hereda de la interfaz **INamedRequestHandler**. El método **HandlerName** es responsable de devolver el nombre del controlador. El nombre del controlador debe coincidir con el nombre del conector fiscal que se especifica en la sede de Commerce.

El conector admite las siguientes solicitudes:

- **SubmitDocumentFiscalDeviceRequest** - Esta solicitud envía documentos a las impresoras y devuelve la respuesta de la impresora fiscal.
- **IsReadyFiscalDeviceRequest** - Esta solicitud se utiliza para una verificación de estado del dispositivo.
- **InitializeFiscalDeviceRequest** - Esta solicitud se utiliza para inicializar la impresora.

#### <a name="configuration"></a>Configuración

El archivo de configuración para el conector fiscal se encuentra en **src\\FiscalIntegration\\Posnet\\HardwareStation\\ThermalDeviceSample\\Configuration\\ConnectorPosnetThermalFVEJ.xml** en el repositorio de [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). El propósito del archivo es permitir la configuración del conector fiscal desde la sede de Comercio. El formato de archivo está alineado con los requisitos para la configuración de integración fiscal.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
