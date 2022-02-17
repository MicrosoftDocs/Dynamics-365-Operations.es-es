---
title: Ejemplo de integración de impresora fiscal para Italia
description: Este tema proporciona una visión general del ejemplo de integración fiscal para Italia en Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2018-11-1
ms.openlocfilehash: 02226fd9f2c92db2518ca48baefb680a3d2f0ac1
ms.sourcegitcommit: 5cefe7d2a71c6f220190afc3293e33e2b9119685
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2022
ms.locfileid: "8076912"
---
# <a name="fiscal-printer-integration-sample-for-italy"></a>Ejemplo de integración de impresora fiscal para Italia

[!include[banner](../includes/banner.md)]

Este tema proporciona una visión general del ejemplo de integración fiscal para Italia en Microsoft Dynamics 365 Commerce.

La funcionalidad de Comercio para Italia incluye una integración de muestra del punto de venta (POS) con una impresora fiscal. La muestra extiende la [funcionalidad de integración fiscal](fiscal-integration-for-retail-channel.md) para que funcione con las impresoras de Epson [serie Epson FP-90III](https://www.epson.it/products/sd/pos-printer/epson-fp-90iii-series) y permite la comunicación con una impresora fiscal en el modo de servidor web a través del servicio web EpsonFPMate utilizando Fiscal ePOS-Print API. La muestra solo admite el modo Registratore Telematico (RT). La muestra se proporciona en forma de código fuente y es parte del kit de desarrollo de software (SDK) de Retail.

Microsoft no publica ningún hardware, software o documentación de Epson. Para obtener información sobre cómo obtener la impresora fiscal y operarla, comuníquese con [Epson Italia S.p.A](https://www.epson.it)

## <a name="scenarios"></a>Situaciones

Los siguientes escenarios están cubiertos por la muestra de integración de impresoras fiscales para Italia:

- Escenarios de ventas:

    - Imprima un recibo fiscal para ventas y devoluciones en efectivo y transporte.
    - Capture una respuesta de la impresora fiscal y almacénela en la base de datos del canal.
    - Impuestos:

        - Asignar a los códigos de impuestos de la impresora fiscal (departamentos).
        - Transfiera los datos impositivos asignados a la impresora fiscal.
        - Imprima impuestos en un recibo fiscal.

    - Pagos:

        - Mapa de los métodos de pago de la impresora fiscal.
        - Imprima pagos en un recibo fiscal.
        - Imprimir información de cambio.

    - Imprimir descuentos de línea.
    - Tarjetas regalo:

        - Excluya una línea de tarjeta de regalo emitida/recargada de un recibo fiscal de una venta.
        - Imprima un pago que utilice una tarjeta de regalo como método de pago habitual.

    - Imprima recibos fiscales para operaciones de pedidos de clientes:

        - No se imprime un recibo fiscal para el depósito de un pedido de cliente.
        - Imprima un recibo fiscal para las líneas para llevar de un pedido de cliente híbrido.
        - Imprima un recibo fiscal para la operación de recolección de un pedido de cliente.
        - Imprima un recibo fiscal para una orden de devolución.

    - Imprima un código de barras para el número de recibo en un recibo fiscal.
    - Imprima la [información del cliente](emea-ita-customer-information.md) que se especifica para una transacción de venta en un recibo fiscal. Un ejemplo de esta información es el código de lotería del cliente. 

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
- Los informes diarios (fiscal X y fiscal Z) se imprimen utilizando el formato integrado en el firmware de la impresora fiscal.
- La impresora fiscal no admite transacciones mixtas. La opción **Prohibir mezclar ventas y devoluciones en un solo recibo** debe establecerse en **Sí** en perfiles de funcionalidad POS.
- El ejemplo admite la integración solo con una impresora fiscal que funciona en el modo Registratore Telematico (RT)).

## <a name="set-up-fiscal-integration-for-italy"></a>Configurar integración fiscal para Italia

La muestra de integración de impresora fiscal para Italia se basa en la [funcionalidad de integración fiscal](fiscal-integration-for-retail-channel.md) y es parte del SDK de Retail. La muestra se encuentra en la carpeta **src\\FiscalIntegration\\EpsonFP90IIISample** del repositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (por ejemplo, [la muestra en la versión/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/EpsonFP90IIISample)). La muestra [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) de un proveedor de documentos fiscales, que es una extensión de Commerce Runtime (CRT) y un conector fiscal, que es una extensión de Commerce Hardware Station. Para obtener más información sobre cómo usar el SDK de Retail, consulte [Arquitectura de SDK minorista](../dev-itpro/retail-sdk/retail-sdk-overview.md) y [Configurar una canalización de compilación para el SDK de empaquetado independiente](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Debido a las limitaciones del [nuevo modelo de empaquetado y extensión independiente](../dev-itpro/build-pipeline.md), actualmente no se puede utilizar para esta muestra de integración fiscal. Debe utilizar la versión anterior de Retail SDK en una máquina virtual (VM) de desarrollador en Microsoft Dynamics Lifecycle Services (LCS). Para más información, vea [Directrices de implementación para la muestra de integración de la impresora fiscal para Italia (heredada)](emea-ita-fpi-sample-sdk.md).
>
> El soporte para el nuevo modelo de extensión y empaquetado independiente para muestras de integración fiscal está previsto para versiones posteriores.

Complete los pasos de configuración de la integración fiscal como se describe en [Configurar la integración fiscal para los canales comerciales](setting-up-fiscal-integration-for-retail-channel.md).

1. [Configuración de un proceso de registro fiscal](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Además, tome nota de la configuración del proceso de registro fiscal que es [específico para esta muestra de integración de la impresora fiscal](#set-up-the-registration-process).
1. [Configuración de textos fiscales para descuentos](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-texts-for-discounts).
1. [Establecimiento de la configuración de tratamiento de errores](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Configuración de informes X/Z fiscales de PDV](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
1. [Habilitar la ejecución manual del registro fisca postpuesto](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Configurar la funcionalidad para la gestión de la información del cliente en POS](emea-ita-customer-information.md#setup).
1. [Configurar los componentes de canal](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Configuración del proceso de registro fiscal

Para habilitar el proceso de registro, siga estos pasos para configurar Commerce Headquarters. Para obtener más información, consulte [Configurar la integración fiscal para los canales de Commerce](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Descargue los archivos de configuración para el proveedor de documentos fiscales y el conector fiscal:

    1. Abra el respositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Seleccione una versión de rama de lanzamiento correcta de acuerdo con su SDK/versión de la aplicación (por ejemplo, **[lanzamiento/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Abra **src \> FiscalIntegration \> EpsonFP90IIISample**.
    1. Descargue el archivo de configuración del proveedor de documentos fiscales en **CommerceRuntime \> DocumentProvider.EpsonFP90IIISample \> Configuration \> DocumentProviderEpsonFP90IIISample.xml** (por ejemplo, [el archivo para la versión/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/EpsonFP90IIISample/CommerceRuntime/DocumentProvider.EpsonFP90IIISample/Configuration/DocumentProviderEpsonFP90IIISample.xml)).
    1. Descargue el archivo de configuración del conector fiscal en **HardwareStation \> EpsonFP90IIIFiscalDeviceSample \> Configuration \> ConnectorEpsonFP90IIISample.xml** (por ejemplo, [el archivo para la versión/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/EpsonFP90IIISample/HardwareStation/EpsonFP90IIIFiscalDeviceSample/Configuration/ConnectorEpsonFP90IIISample.xml).

    > [!WARNING]
    > Debido a las limitaciones del [nuevo modelo de empaquetado y extensión independiente](../dev-itpro/build-pipeline.md), actualmente no se puede utilizar para esta muestra de integración fiscal. Debe utilizar la versión anterior de Retail SDK en una máquina virtual (VM) de desarrollador en LCS. Los archivos de configuración para esta muestra de integración fiscal se encuentran en las siguientes carpetas del Retail SDK en una VM de desarrollador en LCS:
    >
    > - **Archivo de configuración de proveedor de documento fiscal:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extension.DocumentProvider.EpsonFP90IIISample\\Configuration\\DocumentProviderEpsonFP90IIISample.xml
    > - **Archivo de configuración del conector fiscal:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.EpsonFP90IIIFiscalDeviceSample\\Configuration\\ConnectorEpsonFP90IIISample.xml
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

- **Mapeo de tipo de licitación** - El mapeo de los métodos de pago que están configurados para la tienda a los tipos de pago que admite la impresora fiscal. El siguiente ejemplo muestra la asignación predeterminada.

    ```JSON
    {"PaymentMethods": [
        {"StorePaymentMethod":"1", "PrinterPaymentType":"0", "PrinterPaymentIndex":"00"},
        {"StorePaymentMethod":"3", "PrinterPaymentType":"2", "PrinterPaymentIndex":"00"},
        {"StorePaymentMethod":"4", "PrinterPaymentType":"2", "PrinterPaymentIndex":"01"},
        {"StorePaymentMethod":"6", "PrinterPaymentType":"0", "PrinterPaymentIndex":"01"},
        {"StorePaymentMethod":"8", "PrinterPaymentType":"6", "PrinterPaymentIndex":"01"}
        ],
        "DepositPaymentMethod": {"PrinterPaymentType":"2", "PrinterPaymentIndex":"00"}}
    ```

    Esta es una explicación de los atributos de esta asignación:

    - **StorePaymentMethod** es un método de pago configurado para la tienda en **Comercio minorista \> Configuración de canal \> Métodos de pago \> Métodos de pago**.
    - **PrinterPaymentType** y **PrinterPaymentIndex** son el tipo de pago y el índice correspondientes que se definen en la documentación de la impresora fiscal Epson.
    - **DepositPaymentMethod** se utiliza para especificar el tipo de pago y el índice de una impresora para la parte del monto de retiro del pedido del cliente que se liquida con el depósito del pedido del cliente.

    La siguiente tabla muestra cómo el mapeo de muestra de los métodos de pago se corresponde con los métodos de pago de la tienda que están configurados en los datos de demostración estándar.

    | Método de pago | Nombre de método de pago |
    |----------------|---------------------|
    | 1              | Efectivo                |
    | 3              | Tarjeta                |
    | 4              | Cuenta de cliente    |
    | 6              | Divisa            |
    | 8              | Tarjeta regalo           |

    Debe modificar la asignación de muestra de acuerdo con los métodos de pago que están configurados en su aplicación.

- **Tipo de código de barras para el número de recibo** - El tipo de código de barras que se utiliza para mostrar un número de recibo en un recibo fiscal. La asignación predeterminada es **CODE128**.
- **Imprimir datos fiscales en el encabezado del recibo** - Si este parámetro está activado, la información de la tienda se imprimirá en el recibo fiscal. Esta información incluye el nombre, la dirección y el número de identificación fiscal de la tienda, y el nombre del cajero.
- **Mapeo del departamento de impresores fiscales** - El mapeo de los departamentos de la imprenta fiscal a las tasas del impuesto al valor agregado (IVA), las naturalezas exentas de IVA y los tipos de productos. El siguiente ejemplo muestra la asignación predeterminada.

    ```JSON
    {"Departments": [
        {"VATRate":"2200", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"01"},
        {"VATRate":"2200", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"02"},
        {"VATRate":"1000", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"03"},
        {"VATRate":"1000", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"04"},
        {"VATRate":"0500", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"05"},
        {"VATRate":"0500", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"06"},
        {"VATRate":"0400", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"07"},
        {"VATRate":"0400", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"08"},
        {"VATRate":"0000", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"09"},
        {"VATRate":"0000", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"10"},
        {"VATRate":"0000", "VATExemptNature":"NS", "ProductType":"0", "DepartmentNumber":"99"}]}
    ```

    Esta es una explicación de los atributos de esta asignación:

    - **VATRate** es una tasa de IVA admitida que se configura como un código de impuesto sobre las ventas. El valor en el mapeo tiene dos lugares decimales pero ningún separador decimal. Por ejemplo, **2200** representa el 22 por ciento y **1000** representa el 10 por ciento.
    - **VATExemptNature** es aplicable solo en los casos en que la tasa de IVA es 0 (cero), incluidos los casos en los que no hay impuestos. Actualmente, **VATExemptNature** es compatible solo con tarjetas de regalo, y el valor en el mapeo debe corresponder al valor de la propiedad **VATExemptNatureForGiftCard** en el archivo de configuración XML.
    - **ProductType** es el tipo de producto. Un valor de **0** representa productos y un valor de **1** representa servicios.
    - **DepartmentNumber** es el número del departamento que está configurado en la impresora y que corresponde a los tres atributos anteriores.

    Debe modificar el mapeo de muestra de acuerdo con las tasas de IVA que están configuradas en su aplicación y los departamentos correspondientes que están configurados en su impresora fiscal.

- **Naturaleza exenta de IVA para tarjeta regalo** - La exención de IVA que debe aplicarse cuando se emite o recarga una tarjeta regalo. El valor debe corresponder a alguna entrada en el mapeo del departamento de impresión fiscal. La asignación predeterminada es **NS**.
- **Habilitar elementos gratuitos** - Si este parámetro está activado, el tipo de ajuste de descuento especial *omaggio* para artículos que tienen un descuento del 100 por ciento está habilitado.
- **Código de información para el origen de la devolución** - El código de información que se utiliza para capturar el origen de una transacción de devolución si no se proporciona el recibo de venta original. Este parámetro se utiliza junto con los parámetros **Código de información para la fecha de venta original** y **Mapeo de origen de retorno** para generar un mensaje correcto en el recibo fiscal sobre el origen de una transacción de devolución si no existe una transacción de venta original. 

    Este código de información debe configurarse para que el usuario pueda seleccionar o ingresar uno de los posibles orígenes de las devoluciones en sus tiendas. Por ejemplo, se puede configurar como una lista de subcódigos (como **Regreso del sitio** o **Regreso del quiosco**). El parámetro **Mapeo de origen de retorno** luego se usa para traducir el valor del código de información en un comando para la impresora fiscal.

    El código de información que se selecciona para **Código de información para el origen de la devolución** debe configurarse como un código de información obligatorio que se activa una vez por transacción de venta. Debe asignarse como código de información **Devolver producto** en el perfil de funcionalidad POS, de modo que se active cuando la operación **Devolver producto** se ejecuta.

    No se especifica ningún valor predeterminado para esta asignación. Debe seleccionar un código de información que esté configurado en su aplicación.

- **Código de información para la fecha de ventas original** - El código de información que se utiliza para capturar la fecha de venta original de una transacción de devolución si no se proporciona el recibo de venta original. Este parámetro se utiliza junto con los parámetros **Código de información para orgen de devolución** y **Mapeo de origen de retorno** para generar un mensaje correcto en el recibo fiscal sobre el origen de una transacción de devolución si no existe una transacción de venta original.

    El código de información debe configurarse para que el campo **Tipo de entrada** está configurado en **Fecha**. Debe configurarse como un código de información obligatorio que se activa una vez por transacción de venta. También debe asignarse como **Código de información vinculado** para el código de información que se selecciona para el parámetro **Código de información para el origen de la devolución**, de modo que los dos códigos de información se disparen uno tras otro.

    No se especifica ningún valor predeterminado para esta asignación. Debe seleccionar un código de información que esté configurado en su aplicación.

- **Asignación de origen de devolución** - La asignación de orígenes de devolución que se utiliza para capturar el origen de una transacción de devolución si no se proporciona el recibo de venta original. Este parámetro se utiliza junto con los parámetros **Código de información para origen de devolución** y **Código de información para fecha de venta original** para generar un mensaje correcto en el recibo fiscal sobre el origen de una transacción de devolución si no existe una transacción de venta original. El siguiente ejemplo muestra la asignación predeterminada.

    ```JSON
    {"ReturnOrigins": [
        {"ReturnOrigin":"1", "PrinterReturnOrigin":"POS"},
        {"ReturnOrigin":"2", "PrinterReturnOrigin":"ND"}
        ],
        "PrinterReturnOriginWithoutFiscalData":"POS"}
    ```

    Esta es una explicación de los atributos de esta asignación:

    - **ReturnOrigin** es uno de los posibles orígenes de las devoluciones en sus tiendas. El valor debe corresponder a un valor del parámetro **Código de información para el origen de la devolución**.
    - **PrinterReturnOrigin** es uno de los orígenes de devolución que acepta la imprenta fiscal (**POS**, **VR** o **ND**).
    - **PrinterReturnOriginWithoutFiscalData** es el origen de devolución que acepta la impresora fiscal y que corresponde a una transacción de devolución que está vinculada a una transacción de venta original que no tiene datos fiscales vinculados, porque no se registró a través de una impresora fiscal. En este caso, la fecha de venta original se identifica como la fecha de la transacción de venta original.

Las siguientes asignaciones de datos predeterminadas están obsoletas y se conservan solo por compatibilidad con versiones anteriores:

- Mapeo de códigos de impuesto al valor agregado (IVA)
- Tipo de pago de depósito

#### <a name="fiscal-connector-settings"></a>Configuración del conector fiscal

La siguiente configuración se incluye en la configuración del conector fiscal que se proporciona como parte de la muestra de integración fiscal:

- **Dirección de punto final** - La URL de la impresora.
- **Sincronización de fecha y hora** - Un valor que especifica si la fecha y la hora de la impresora deben sincronizarse con la estación de hardware conectada.

### <a name="configure-channel-components"></a>Configurar los componentes de canal

> [!WARNING]
> Debido a las limitaciones del [nuevo modelo de empaquetado y extensión independiente](../dev-itpro/build-pipeline.md), actualmente no se puede utilizar para esta muestra de integración fiscal. Debe utilizar la versión anterior de Retail SDK en una máquina virtual (VM) de desarrollador en LCS. Para más información, vea [Directrices de implementación para la muestra de integración de la impresora fiscal para Italia (heredada)](emea-ita-fpi-sample-sdk.md).
>
> El soporte para el nuevo modelo de extensión y empaquetado independiente para muestras de integración fiscal está previsto para versiones posteriores.

#### <a name="set-up-the-development-environment"></a>Configurar el entorno de desarrollo

Para configurar un entorno de desarrollo para probar y ampliar la muestra, siga estos pasos.

1. Clonar o descargar el repositorio de [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions). Seleccione una versión de rama de lanzamiento correcta de acuerdo con su SDK/versión de la aplicación. Para más información, vea [Descargar muestras y paquetes de referencia del SDK de Retail desde GitHub y NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Abra la solución de integración de impresora fiscal en **Dynamics365Commerce.Solutions\\FiscalIntegration\\EpsonFP90IIISample\\EpsonFP90IIISample.sln** y compílela.
1. Instale las extensiones de CRT:

    1. Busque el instalador de extensiones de CRT:

        - **Commerce Scale Unit:** En la carpeta **EpsonFP90IIISample\\ScaleUnit\\ScaleUnit.EpsonFP90III.Installer\\bin\\Debug\\net461**, busque el instalador **ScaleUnit.EpsonFP90III.Installer**.
        - **CRT local en Modern POS:** En la carpeta **EpsonFP90IIISample\\ModernPOS\\ModernPOS.EpsonFP90III.Installer\\bin\\Debug\\net461**, busque el instalador **ModernPOS.EpsonFP90III.Installer**.

    1. Inicie el instalador de extensiones de CRT desde la línea de comandos:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.EpsonFP90III.Installer.exe install --verbosity 0
            ```

        - **CRT local en Modern POS:**

            ```Console
            ModernPOS.EpsonFP90III.Installer.exe install --verbosity 0
            ```

1. Instale las extensiones de la estación de hardware:

    1. En la carpeta **EpsonFP90IIISample\\HardwareStation\\HardwareStation.EpsonFP90III.Installer\\bin\\Debug\\net461**, busque el instalador **HardwareStation.EpsonFP90III.Installer**.
    1. Inicie el instalador de extensiones desde la línea de comandos:

        ```Console
        HardwareStation.EpsonFP90III.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Entorno de producción

Siga los pasos en [Configurar una canalización de compilación para una muestra de integración fiscal](fiscal-integration-sample-build-pipeline.md) para generar y lanzar la unidad de escala en la nube y los paquetes implementables de autoservicio para la muestra de integración fiscal. El archivo YAML de plantilla **EpsonFP90III build-pipeline.yml** se puede encontrar en la carpeta **Pipeline\\YAML_Files** del repositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-extensions"></a>Diseño de las extensiones

La muestra de integración de impresora fiscal para Italia se basa en la [funcionalidad de integración fiscal](fiscal-integration-for-retail-channel.md) y es parte del SDK de Retail. La muestra se encuentra en la carpeta **src\\FiscalIntegration\\EpsonFP90IIISample** del repositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (por ejemplo, [la muestra en la versión/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/EpsonFP90IIISample)). La muestra [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) de un proveedor de documentos fiscales, que es una extensión de CRT y un conector fiscal, que es una extensión de Commerce Hardware Station. Para obtener más información sobre cómo usar el SDK de Retail, consulte [Arquitectura de SDK minorista](../dev-itpro/retail-sdk/retail-sdk-overview.md) y [Configurar una canalización de compilación para el SDK de empaquetado independiente](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Debido a las limitaciones del [nuevo modelo de empaquetado y extensión independiente](../dev-itpro/build-pipeline.md), actualmente no se puede utilizar para esta muestra de integración fiscal. Debe utilizar la versión anterior de Retail SDK en una máquina virtual (VM) de desarrollador en LCS. Para más información, vea [Directrices de implementación para la muestra de integración de la impresora fiscal para Italia (heredada)](emea-ita-fpi-sample-sdk.md). El soporte para el nuevo modelo de extensión y empaquetado independiente para muestras de integración fiscal está previsto para versiones posteriores.

### <a name="commerce-runtime-extension-design"></a>Diseño de extensión de Commerce Runtime

El propósito de la extensión que es un proveedor de documentos fiscales es generar documentos específicos de la impresora y manejar respuestas desde la impresora fiscal.

#### <a name="request-handler"></a>Manejador de solicitudes

El gestor de solicitudes **DocumentProviderEpsonFP90III** es el punto de entrada de la solicitud para generar documentos desde la impresora fiscal.

El controlador se hereda de la interfaz **INamedRequestHandler**. El método **HandlerName** es responsable de devolver el nombre del controlador. El nombre del controlador debe coincidir con el nombre del proveedor de documentos del conector que se especifica en la sede de Comercio.

El conector admite las siguientes solicitudes:

- **GetFiscalDocumentDocumentProviderRequest** - Esta solicitud contiene información sobre qué documento se debe generar. Devuelve un documento específico de la impresora que debe registrarse en la impresora fiscal.
- **GetSupportedRegistrableEventsDocumentProviderRequest** - Esta solicitud devuelve la lista de eventos a los que suscribirse. Actualmente, se admiten los siguientes eventos: ventas, impresión del informe X e impresión del informe Z.

#### <a name="configuration"></a>Configuración

El archivo de configuración para el proveedor de documentos fiscales se encuentra en **src\\FiscalIntegration\\EpsonFP90IIISample\\CommerceRuntime\\DocumentProvider.EpsonFP90IIISample\\Configuration\\DocumentProviderEpsonFP90IIISample.xml** en el repositorio de [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). El propósito del archivo es permitir que la configuración del proveedor de documentos se configure desde la sede de Comercio. El formato de archivo está alineado con los requisitos para la configuración de integración fiscal.

### <a name="hardware-station-extension-design"></a>Diseño de extensiones de la estación de hardware

El propósito de la extensión que es un conector fiscal es comunicarse con la impresora fiscal. Esta extensión usa el protocolo HTTP para enviar documentos que la extensión CRT genera a la impresora fiscal. También maneja las respuestas que se reciben de la impresora fiscal.

#### <a name="request-handler"></a>Manejador de solicitudes

El gestor de solicitudes **EpsonFP90IIISample** es el punto de entrada para gestionar las solicitudes al dispositivo periférico fiscal.

El controlador se hereda de la interfaz **INamedRequestHandler**. El método **HandlerName** es responsable de devolver el nombre del controlador. El nombre del controlador debe coincidir con el nombre del conector fiscal que se especifica en la sede de Commerce.

El conector admite las siguientes solicitudes:

- **SubmitDocumentFiscalDeviceRequest** - Esta solicitud envía documentos a las impresoras y devuelve la respuesta de la impresora fiscal.
- **IsReadyFiscalDeviceRequest** - Esta solicitud se utiliza para una verificación de estado del dispositivo.
- **InitializeFiscalDeviceRequest** - Esta solicitud se utiliza para inicializar la impresora.

#### <a name="configuration"></a>Configuración

El archivo de configuración para el conector fiscal se encuentra en **src\\FiscalIntegration\\EpsonFP90IIISample\\HardwareStation\\EpsonFP90IIIFiscalDeviceSample\\Configuration\\ConnectorEpsonFP90IIISample.xml** en el repositorio de [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). El propósito del archivo es permitir la configuración para el conector fiscal desde la sede de Commerce. El formato de archivo está alineado con los requisitos para la configuración de integración fiscal.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
