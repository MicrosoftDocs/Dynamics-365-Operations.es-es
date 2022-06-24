---
title: Ejemplo de integración de servicio de registro fiscal para la República Checa
description: Este artículo proporciona una visión general del ejemplo de integración fiscal para la República Checa en Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 03/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-4-1
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: d255b03242a4cb7a72cef1e8e6fab901ecf953e6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8910507"
---
# <a name="fiscal-registration-service-integration-sample-for-the-czech-republic"></a>Ejemplo de integración de servicio de registro fiscal para la República Checa

[!include[banner](../includes/banner.md)]

Este artículo proporciona una visión general del ejemplo de integración fiscal para la República Checa en Microsoft Dynamics 365 Commerce.

Para cumplir con los requisitos fiscales locales para las cajas registradoras en la República Checa, la funcionalidad de Dynamics 365 Commerce para la República Checa incluye una integración de muestra del punto de venta (POS) con un servicio de registro fiscal externo. La muestra extiende la [funcionalidad de integración fiscal](fiscal-integration-for-retail-channel.md). Se basa en el [EFR (Registro Fiscal Electrónico)](https://efsta.org/sicherheitsloesungen/) solución de [EFSTA](https://efsta.org/) y habilita la comunicación con el servicio EFR a través del protocolo HTTPS. El servicio EFR asegura el Registro Electrónico de Ventas (EET - Elektronická proof tržeb), es decir, la transmisión en línea de los datos de ventas a un servicio web fiscal de las autoridades fiscales.

El servicio EFR debe estar alojado en la estación de hardware de Commerce o en una máquina separada a la que se pueda conectar desde la estación de hardware. La muestra se proporciona en forma de código fuente y es parte del kit de desarrollo de software (SDK) de Retail.

Microsoft no publica ningún hardware, software o documentación de EFSTA. Para obtener información sobre cómo obtener la solución EFR y operarla, comuníquese con [EFSTA](https://efsta.org/kontakt/).

## <a name="scenarios"></a>Situaciones

Los siguientes escenarios están cubiertos por la muestra de integración de servicio de registro fiscal para la República Checa.

- Registro de transacciones en efectivo en el servicio de registro fiscal.

    - Envíe los datos detallados de la transacción al servicio de registro fiscal. Estos datos incluyen información de la línea de ventas e información sobre descuentos, pagos e impuestos. El servicio de registro fiscal envía además los datos al servicio web de las autoridades fiscales y recibe una confirmación que incluye el código de identificación fiscal de la transacción.
    - Obtenga una respuesta del servicio de registro fiscal. Esta respuesta incluye datos fiscales como el código de identificación fiscal y el código de seguridad de la transacción, etc.
    - Imprima los datos fiscales para una transacción registrada en el recibo.

- Registro de operaciones de tarjetas regalo y depósitos de clientes en el servicio de registro fiscal.

    - Emitir o agregar dinero a una tarjeta regalo.
    - Registrar un depósito de cuenta de cliente.
    - Cree un pedido de cliente y registre un depósito para el pedido.
    - Edite un pedido de cliente y reemplace el depósito para el pedido.
    - Cancele un pedido de cliente y reembolse el depósito para el pedido.

- Manejo de errores, como las siguientes opciones.

    - Vuelva a intentar el registro fiscal si es posible hacerlo, por ejemplo, si el servicio de registro fiscal no está disponible, no está listo o no responde.
    - Posponer registro fiscal.
    - Omita el registro fiscal o marque la transacción como registrada e incluya códigos de información para capturar el motivo del error e información adicional.
    - Compruebe la disponibilidad del servicio de registro fiscal antes de que se abra una nueva transacción de venta o se finalice una transacción de venta.

### <a name="gift-cards"></a>Tarjetas regalo

El ejemplo de integración del servicio de registro fiscal implementa las siguientes reglas relacionadas con las tarjetas de regalo.

- Líneas de venta relacionadas con las operaciones *Emitir tarjeta de regalo* o *Agregar a la tarjeta de regalo* en una transacción de venta se marcan con un atributo especial cuando la transacción se registra en el servicio de registro fiscal.
- Un pago con tarjeta regalo se considera un pago regular y se marca con un atributo especial cuando la transacción se registra en el servicio de registro fiscal.

### <a name="customer-account-deposits-and-customer-order-deposits"></a>Depósitos de cuentas de clientes y depósitos de pedidos de clientes

El ejemplo de integración del servicio de registro fiscal implementa las siguientes reglas relacionadas con los depósitos de cuentas de clientes y depósitos de órdenes de clientes.

- Una transacción relacionada con un depósito en la cuenta de un cliente o el depósito de un pedido de un cliente se registra en el servicio de registro fiscal como una transacción de una sola línea y se marca con un atributo especial. El grupo de IVA de depósito se especifica en esta línea.
- Cuando se crea un pedido de cliente híbrido, es decir, un pedido de cliente que contiene productos que pueden ser realizados fuera de la tienda por el cliente, así como productos que serán recogidos o enviados posteriormente, la transacción se registra en el servicio de registro fiscal. contiene líneas para los productos que se realizan, así como una línea para el depósito del pedido.
- Un pago de una cuenta de cliente se considera un pago regular y se marca con un atributo especial cuando la transacción se registra en el servicio de registro fiscal.
- El monto del depósito del pedido del cliente que se aplica a una operación seleccionar de un pedido del cliente se considera un pago regular y se marca con un atributo especial cuando la transacción se registra en el servicio de registro fiscal.

### <a name="offline-registration"></a>Registro sin conexión

Si el servicio de registro fiscal no puede transmitir los datos de la transacción al servicio web fiscal de las autoridades fiscales (por ejemplo, debido al tiempo de espera de respuesta) y no recibe una confirmación del servicio web (es decir, el código de identificación fiscal de la transacción), genera una firma local para la transacción y la incluye y un código de error especial en la respuesta. El servicio de registro fiscal reenvía las transacciones en el orden original en segundo plano tan pronto como se restablece la conexión de red.

### <a name="limitations-of-the-sample"></a>Limitaciones de la muestra

El servicio de registro fiscal solo admite escenarios en los que el impuesto sobre las ventas está incluido en el precio. Por lo tanto, la opción **El precio incluye el impuesto a las ventas** debe establecerse en **Sí** tanto para tiendas como para clientes.

## <a name="set-up-commerce-for-the-czech-republic"></a>Configurar la localización de Commerce para la República Checa

Esta sección describe la configuración de comercio que es específica y recomendada para la República Checa. - Para obtener más información, consulte la [página principal de Commerce](../index.md).

Para utilizar la funcionalidad específica de la República Checa, debe especificar la siguiente configuración.

- En la dirección principal de la entidad jurídica, establezca el campo **País o región** en **CZE** (República Checa).
- En el perfil de funcionalidad POS de cada tienda ubicada en la República Checa, configure el campo **Código ISO** como **CZ** (República Checa).

También debe especificar la siguiente configuración para la República Checa. Tenga en cuenta que debe ejecutar los trabajos de distribución adecuados después de completar la configuración.

### <a name="set-up-vat-per-czech-republic-requirements"></a>Configurar el IVA según los requisitos de la República Checa


Debe crear códigos de impuestos, grupos de impuestos y grupos de impuestos de artículo para los grupos de impuestos de artículos. También debe configurar la información de impuestos sobre las ventas para productos y servicios. Para obtener más información sobre cómo configurar y usar características de impuestos, consulte [Introducción a los impuestos](../../finance/general-ledger/indirect-taxes-overview.md).

### <a name="set-up-stores"></a>Configurar tiendas

Sobre la página **Todas las tiendas**, actualice los detalles de la tienda. En concreto, configurar los siguientes parámetros.

- En el campo **Grupo de impuestos**, especifique el grupo de impuestos que se debe usar para las ventas para el cliente predeterminado.
- Establezca la opción **Los precios incluyen impuestos** en **Sí**.
- Establezca el campo **Nombre** en el nombre de la empresa. Este cambio ayuda a garantizar que el nombre de la empresa aparezca en un recibo de compra. Alternativamente, puede agregar el nombre de la empresa al diseño del recibo de venta como texto de formato libre.
- Establezca el campo **Número de identificación fiscal (TIN)** en el número de identificación de la empresa. Este cambio ayuda a garantizar que el número de identificación de la empresa aparezca en un recibo de compra. Alternativamente, puede agregar el número de identificación de la empresa al diseño del recibo de venta como texto de formato libre.

### <a name="set-up-functionality-profiles"></a>Configuración de perfiles de funcionalidad

Configuración de perfiles de funcionalidad de PDV.

- Sobre la ficha desplegable **Numeración de recibos**, configure la numeración de recibos creando o actualizando registros para los tipos de transacciones de recibos **Rebaja**, **Órdenes de venta** y **Regreso**.

### <a name="set-up-registration-numbers"></a>Configure los números de registro

1. Vaya a **Administración de la organización \> Libreta de direcciones global \> Tipos de registro \> Tipos de registro**. Crear un nuevo tipo de registro. Especifique el campo **País o región** como **CZE** (República Checa) y hacerlo restringido a Organización.
2. Vaya a **Administración de la organización \> Libreta de direcciones global \> Tipos de registro \> Categorías de registro**. Cree una categoría de registro nueva. Seleccione el tipo de registro del paso anterior y configure la **Categoría de registro** como **ID de local comercial**.
3. Vaya a **Administración de la organización \> Organizaciones \> Unidades operativas**. Para cada tienda ubicada en la República Checa, seleccione la unidad relacionada con la tienda. En la ficha desplegable **Dirección**, seleccione la lista desplegable **Más opciones** y luego seleccione **Avanzado**. 
4. En la página abierta **Administrar direcciones**, debe especificar la siguiente configuración.

    - En la ficha desplegable **Dirección**, establezca el campo **País o región** en **CZE**.
    - En la ficha despelgable **Identificación de Registro**, cree un nuevo registro. Seleccione el tipo de registro creado antes y establezca el número de registro.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Configure campos personalizados para que se puedan usar en formatos de recibo para recibos de ventas

Puede configurar el texto del idioma y los campos personalizados que se utilizan en los formatos de recibo de POS. La empresa predeterminada del usuario que crea la configuración del recibo debe ser la misma entidad legal donde se crea la configuración del texto del idioma. Alternativamente, los textos en el mismo idioma deben crearse tanto en la empresa predeterminada del usuario como en la entidad legal de la tienda para la que se creó la configuración.

Sobre la página **Texto de idioma**, agregue los siguientes registros para las etiquetas de los campos personalizados para diseños de recibos. Tenga en cuenta que los valores **ID de idioma**, **ID de texto** y **Texto** que se muestran en la tabla son solo ejemplos. Puede cambiarlos fácilmente para satisfacer sus necesidades. Sin embargo, los valores **ID de texto** que use deben ser únicos y deben ser iguales o mayores que 900001.

Agregue las siguientes etiquetas POS a la sección **POS** de la página **Texto de idioma** de la tabla:

| Id. del idioma | Id. de texto | Texto                   |
|-------------|---------|------------------------|
| en-US       | 900001  | ID provozovny/pokladny |
| en-US       | 900002  | BKP                    |
| en-US       | 900003  | PKP                    |
| en-US       | 900004  | FIK                    |
| en-US       | 900005  | Información                   |
| en-US       | 900006  | Número de secuencia        |

Sobre la página **Campos personalizados**, agregue los siguientes registros para los campos personalizados para diseños de recibos. Tenga en cuenta que los valores **ID de texto de subtítulo** deben corresponder a los valores de **ID de texto** que especificó en la página **Texto de idioma**:

| Name                 | Tipo    | Id. de texto de leyenda |
|----------------------|---------|-----------------|
| TLT                  | Recepción | 900001          |
| SEC                  | Recepción | 900002          |
| SIGN                 | Recepción | 900003          |
| FISCAL               | Recepción | 900004          |
| INFO                 | Recepción | 900005          |
| CONTINUOUSNUMBER     | Recepción | 900006          |

> [!NOTE]
> Es importante que especifique los nombres de campo personalizados correctos, como se indica en la tabla anterior. Un nombre de campo personalizado incorrecto hará que falten datos en los recibos.

### <a name="configure-receipt-formats"></a>Configurar formatos de recibo

Para cada formato de recibo requerido, cambie el valor del campo **Comportamiento de impresión** a **Imprimir siempre**.

En el diseñador de formato de recibo, agregue los siguientes campos personalizados a las secciones de recibos correspondientes. Tenga en cuenta que los nombres de los campos corresponden a los textos de idioma que definió en la sección anterior.

- **Encabezamiento:** agregue los siguientes campos.

    - **Nombre de la tienda** y **Número de identificación de impuestos**: estos campos se utilizan para imprimir el nombre de la empresa y el número de identidad en los recibos. Alternativamente, puede agregar el nombre de la empresa y el número de identidad al diseño como texto de formato libre.
    - **Dirección de la tienda**, **Fecha**, **Tiempo 24H**, **Número de recibo** y **Número de registro**.
    - **Número continuo**: este campo identifica el número de la transacción en efectivo en el servicio de registro fiscal.

- **Líneas:** agregue los siguientes campos.

    - **Nombre del artículo**
    - **Cant.**
    - **Precio total con impuestos**

- **Pie de página:** agregue los siguientes campos.

    - Campos de pago, para que se impriman los importes de pago de cada método de pago. Por ejemplo, agregue los campos **Nombre de licitación** y **Monto de la licitación** a una línea del diseño.
    - **ID provozovny / pokladny** : este campo imprime los identificadores del local comercial y la caja registradora.
    - **BKP** : este campo imprime el código de seguridad del contribuyente que le asigna el servicio de registro fiscal.
    - **FIK** : este campo imprime el código de identificación fiscal de la transacción que es asignado por el servicio web de las autoridades fiscales en caso de registro en línea exitoso.
    - **PKP** : este campo imprime el código de firma del contribuyente que genera el servicio de registro fiscal en caso de registro fuera de línea.
    - **Información** : este campo imprime la información adicional del servicio de registro fiscal.

Para obtener más información sobre cómo trabajar con formatos de recibo, consulte [Configurar y diseñar formatos de recibos](../receipt-templates-printing.md).

## <a name="set-up-fiscal-integration-for-the-czech-republic"></a>Configurar la integración fiscal para la República Checa

La muestra de integración de servicio de registro para la República Checa se basa en la [funcionalidad de integración fiscal](fiscal-integration-for-retail-channel.md) y es parte del SDK de Retail. La muestra se encuentra en la carpeta **src\\FiscalIntegration\\Efr** del repositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (por ejemplo, [la muestra en la versión/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). La muestra [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) de un proveedor de documentos fiscales, que es una extensión de Commerce Runtime (CRT) y un conector fiscal, que es una extensión de Commerce Hardware Station. Para obtener más información sobre cómo usar el SDK de Retail, consulte [Arquitectura de SDK minorista](../dev-itpro/retail-sdk/retail-sdk-overview.md) y [Configurar una canalización de compilación para el SDK de empaquetado independiente](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Debido a las limitaciones del [nuevo modelo de empaquetado y extensión independiente](../dev-itpro/build-pipeline.md), actualmente no se puede utilizar para esta muestra de integración fiscal. Debe utilizar la versión anterior de Retail SDK en una máquina virtual (VM) de desarrollador en Microsoft Dynamics Lifecycle Services (LCS). Para más información, vea [Directrices de implementación para la muestra de integración fiscal para la República Checa (heredada)](emea-cze-fi-sample-sdk.md).
>
> El soporte para el nuevo modelo de extensión y empaquetado independiente para muestras de integración fiscal está previsto para versiones posteriores.

Complete los pasos de configuración de la integración fiscal como se describe en [Configurar la integración fiscal para los canales comerciales](setting-up-fiscal-integration-for-retail-channel.md):

1. [Configuración de un proceso de registro fiscal](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Además, tome nota de la configuración del proceso de registro fiscal que es [específico para esta muestra de integración de servicio de registro fiscal](#set-up-the-registration-process).
1. [Establecimiento de la configuración de tratamiento de errores](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Habilitar la ejecución manual del registro fisca postpuesto](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Configurar los componentes de canal](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Configuración del proceso de registro fiscal

Para habilitar el proceso de registro, siga estos pasos para configurar Commerce Headquarters. Para obtener más información, consulte [Configurar la integración fiscal para los canales de Commerce](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Descargue los archivos de configuración para el proveedor de documentos fiscales y el conector fiscal:

    1. Abra el respositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Seleccione una versión de rama de lanzamiento correcta de acuerdo con su SDK/versión de la aplicación (por ejemplo, **[lanzamiento/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Abra **src \> FiscalIntegration \> Efr**.
    1. Descargue el archivo de configuración del proveedor de documentos fiscales en **Configurations \> DocumentProviders \> DocumentProviderFiscalEFRSampleCzech.xml** (por ejemplo, [el archivo para lanzamiento/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/DocumentProviders/DocumentProviderFiscalEFRSampleCzech.xml)).
    1. Descargue el archivo de configuración del conector fiscal en **Configuraciones \> Conectores \> ConnectorEFRSample.xml** (por ejemplo, [el archivo para lanzamiento/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/Connectors/ConnectorEFRSample.xml)).

    > [!WARNING]
    > Debido a las limitaciones del [nuevo modelo de empaquetado y extensión independiente](../dev-itpro/build-pipeline.md), actualmente no se puede utilizar para esta muestra de integración fiscal. Debe utilizar la versión anterior de Retail SDK en una máquina virtual (VM) de desarrollador en LCS. Los archivos de configuración para esta muestra de integración fiscal se encuentran en las siguientes carpetas del Retail SDK en una VM de desarrollador en LCS:
    >
    > - **Archivo de configuración de proveedor de documento fiscal:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.EFRSample\\Configuration\\DocumentProviderFiscalEFRSampleCzech.xml
    > - **Archivo de configuración del conector fiscal:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.EFRSample\\Configuration\\ConnectorEFRSample.xml
    > 
    > El soporte para el nuevo modelo de extensión y empaquetado independiente para muestras de integración fiscal está previsto para versiones posteriores.

1. Vaya a **Retail y Commerce \> Configuración de sede central \> Parámetros \> Parámetros compartidos de Commerce**. En la pestaña **General**, configure la opción **Habilitar integración fiscal** en **Sí**.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Integración fiscal \> Proveedores de documentos fiscales** y cargue el archivo de configuración del proveedor de documentos fiscales que descargó antes.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Integración fiscal \> Conectores fiscales** y cargue el archivo de configuración del conector fiscal que descargó antes.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Integración fiscal \> Perfiles funcionales del conector**. Cree un nuevo perfil funcional del conector. Seleccione el proveedor de documentos y el conector que cargó anteriormente. Actualice la [configuración de mapeo de datos](#default-data-mapping) según sea necesario.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Integración fiscal \> Perfiles técnicos del conector**. Cree un nuevo perfil técnico de conector y seleccione el conector fiscal que cargó anteriormente. Actualice la [configuración del conector](#fiscal-connector-settings) según sea necesario.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Integración fiscal \> Grupos de conector fiscal**. Cree un nuevo grupo de conectores fiscales para el perfil funcional de conector que creó anteriormente.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Integración fiscal \> Procesos de registro fiscal**. Cree un nuevo proceso de registro fiscal y un paso de proceso de registro fiscal, y seleccione el grupo de conectores fiscales que creó anteriormente.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> Perfiles de PDV \> Perfiles de funcionalidad**. Seleccione un perfil de funcionalidad que esté vinculado a la tienda donde se debe activar el proceso de registro. Sobre la ficha desplegable **Proceso de registro fiscal**, seleccione el proceso de registro fiscal que creó anteriormente.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> Perfiles de PDV \> Perfiles de hardware**. Seleccione un perfil de hardware que esté vinculado a la estación de hardware a la que se conectará la impresora fiscal. Sobre la ficha desplegable **Periféricos fiscales**, seleccione el perfil técnico del conector que creó anteriormente.
1. Abra la programación de distribución (**Retail y Commerce \> TI de Retail y Commerce \> Programación de distribución**) y seleccione los trabajos **1070** y **1090** para transferir los datos a la base de datos del canal.

#### <a name="default-data-mapping"></a>Asignación de datos predeterminada

La siguiente asignación de datos predeterminada se incluye en la configuración del proveedor de documentos fiscales que se proporciona como parte de la muestra de integración fiscal:

- **Mapeo de tasas de impuesto al valor agregado (IVA)** - El mapeo de los valores porcentuales de impuestos que se configuran para los códigos de impuestos sobre las ventas a los valores de **TaxG** (grupo de impuestos) en las solicitudes que se envían al servicio fiscal. Aquí está la asignación predeterminada:

    ```
    A: 21.00; B: 15.00; C: 10.00; Z: 0.00
    ```

    El primer componente de cada par representa un grupo de impuestos de IVA que es compatible con el servicio de registro fiscal EFR. El segundo componente representa la tasa de IVA correspondiente. Para obtener más información sobre los grupos de impuestos del IVA que EFR admite para la República Checa, consulte la [Referencia EFR](https://public.efsta.net/efr/).

- **Asignación de grupo de IVA predeterminado** - Cualquier importe de IVA que no se pueda asignar a uno de los grupos de IVA predeterminados se atribuirá al grupo de IVA predeterminado (básico). Aquí está la asignación predeterminada:

    ```
    A
    ```

- **Asignación de grupos de IVA de depósito** - Los importes de depósito de cliente y los importes de depósito de pedido de cliente se atribuirán al grupo de IVA de depósito. Aquí está la asignación predeterminada:

    ```
    Z
    ```

#### <a name="fiscal-connector-settings"></a>Configuración del conector fiscal

La siguiente configuración se incluye en la configuración del conector fiscal que se proporciona como parte de la muestra de integración fiscal:

- **Dirección de punto final** - La URL del servicio de registro fiscal.
- **Tiempo de espera** - La cantidad de tiempo, en milisegundos, que el conector fiscal esperará una respuesta del servicio de registro fiscal.

### <a name="configure-channel-components"></a>Configurar los componentes de canal

> [!WARNING]
> Debido a las limitaciones del [nuevo modelo de empaquetado y extensión independiente](../dev-itpro/build-pipeline.md), actualmente no se puede utilizar para esta muestra de integración fiscal. Debe utilizar la versión anterior de Retail SDK en una máquina virtual (VM) de desarrollador en LCS. Para más información, vea [Directrices de implementación para la muestra de integración fiscal para la República Checa (heredada)](emea-cze-fi-sample-sdk.md).
>
> El soporte para el nuevo modelo de extensión y empaquetado independiente para muestras de integración fiscal está previsto para versiones posteriores.

#### <a name="set-up-the-development-environment"></a>Configurar el entorno de desarrollo

Para configurar un entorno de desarrollo para probar y ampliar la muestra, siga estos pasos.

1. Clonar o descargar el repositorio de [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions). Seleccione una versión de rama de lanzamiento correcta de acuerdo con su SDK/versión de la aplicación. Para más información, vea [Descargar muestras y paquetes de referencia del SDK de Retail desde GitHub y NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Abra la solución EFR en **Dynamics365Commerce.Solutions\\FiscalIntegration\\Efr\\EFR.sln** y compílela.
1. Instale las extensiones de CRT:

    1. Busque el instalador de extensiones de CRT:

        - **Commerce Scale Unit:** En la carpeta **Efr\\ScaleUnit\\ScaleUnit.EFR.Installer\\bin\\Debug\\net461**, busque el instalador **ScaleUnit.EFR.Installer**.
        - **CRT local en Modern POS:** En la carpeta **Efr\\ModernPOS\\ModernPOS.EFR.Installer\\bin\\Debug\\net461**, busque el instalador **ModernPOS.EFR.Installer**.

    1. Inicie el instalador de extensiones de CRT desde la línea de comandos:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.EFR.Installer.exe install --verbosity 0
            ```

        - **CRT local en Modern POS:**

            ```Console
            ModernPOS.EFR.Installer.exe install --verbosity 0
            ```

1. Instalar extensiones de conector fiscal:

    Puede instalar extensiones de conector fiscal en la [estación de hardware](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-connected-to-the-hardware-station) o el [registro de PDV](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-or-service-in-the-local-network).

    1. Instale las extensiones de la estación de hardware:

        1. En la carpeta **Efr\\HardwareStation\\HardwareStation.EFR.Installer\\bin\\Debug\\net461**, busque el instalador **HardwareStation.EFR.Installer**.
        1. Inicie el instalador de la extensión desde la línea de comandos ejecutando el siguiente comando.

            ```Console
            HardwareStation.EFR.Installer.exe install --verbosity 0
            ```

    1. Instale las extensiones de PDV:

        1. Abra la solución de muestra del conector fiscal PDV en **Dynamics365Commerce.Solutions\\FiscalIntegration\\PosFiscalConnectorSample\\Contoso.PosFiscalConnectorSample.sln** y construirlo.
        1. En la carpeta **PosFiscalConnectorSample\\StoreCommerce.Installer\\bin\\Debug\\net461**, encuentre el instalador **Contoso.PosFiscalConnectorSample.StoreCommerce.Installer**.
        1. Inicie el instalador de la extensión desde la línea de comandos ejecutando el siguiente comando.

            ```Console
            Contoso.PosFiscalConnectorSample.StoreCommerce.Installer.exe install --verbosity 0
            ```

#### <a name="production-environment"></a>Entorno de producción

Siga los pasos en [Configurar una canalización de compilación para una muestra de integración fiscal](fiscal-integration-sample-build-pipeline.md) para generar y lanzar la unidad de escala en la nube y los paquetes implementables de autoservicio para la muestra de integración fiscal. El archivo YAML de plantilla **EFR build-pipeline.yml** se puede encontrar en la carpeta **Pipeline\\YAML_Files** del repositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-extensions"></a>Diseño de las extensiones

La muestra de integración de servicio de registro para la República Checa se basa en la [funcionalidad de integración fiscal](fiscal-integration-for-retail-channel.md) y es parte del SDK de Retail. La muestra se encuentra en la carpeta **src\\FiscalIntegration\\Efr** del repositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (por ejemplo, [la muestra en la versión/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). La muestra [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) de un proveedor de documentos fiscales, que es una extensión de CRT y un conector fiscal, que es una extensión de Commerce Hardware Station. Para obtener más información sobre cómo usar el SDK de Retail, consulte [Arquitectura de SDK minorista](../dev-itpro/retail-sdk/retail-sdk-overview.md) y [Configurar una canalización de compilación para el SDK de empaquetado independiente](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Debido a las limitaciones del [nuevo modelo de empaquetado y extensión independiente](../dev-itpro/build-pipeline.md), actualmente no se puede utilizar para esta muestra de integración fiscal. Debe utilizar la versión anterior de Retail SDK en una máquina virtual (VM) de desarrollador en LCS. Para más información, vea [Directrices de implementación para la muestra de integración fiscal para la República Checa (heredada)](emea-cze-fi-sample-sdk.md). El soporte para el nuevo modelo de extensión y empaquetado independiente para muestras de integración fiscal está previsto para versiones posteriores.

### <a name="commerce-runtime-extension-design"></a>Diseño de extensión de Commerce Runtime

El propósito de la extensión que es un proveedor de documentos fiscales es generar documentos específicos del servicio y manejar respuestas desde el servicio de registro fiscal.

#### <a name="request-handler"></a>Manejador de solicitudes

Hay un solo manejador de solicitudes **DocumentProviderEFRFiscalCZE** para proveedor de documentos, que se utiliza para generar documentos fiscales para el servicio de registro fiscal.

Este controlador se hereda de la interfaz **INamedRequestHandler**. El método **HandlerName** es responsable de devolver el nombre del controlador. El nombre del controlador debe coincidir con el nombre del proveedor de documentos del conector que se especifica en la sede de Comercio.

El conector admite las siguientes solicitudes.

- **GetFiscalDocumentDocumentProviderRequest** - Esta solicitud contiene información sobre qué documento se debe generar. Devuelve un documento específico del servicio que debe registrarse en el servicio de registro fiscal.
- **GetSupportedRegistrableEventsDocumentProviderRequest** - Esta solicitud devuelve la lista de eventos a los que suscribirse. Actualmente, se admiten los siguientes eventos: ventas, depósitos en cuentas de clientes y depósitos en pedidos de clientes.
- **GetFiscalRegisterResponseToSaveDocumentProviderRequest** - Esta solicitud devuelve la respuesta del servicio de registro fiscal. Esta respuesta se serializa para formar una cadena de modo que esté lista para ser guardada.

#### <a name="configuration"></a>Configuración

El archivo de configuración para el proveedor de documentos fiscales se encuentra en **src\\FiscalIntegration\\Efr\\Configurations\\DocumentProviders\\DocumentProviderFiscalEFRSampleCzech.xml** en el repositorio de [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). El propósito del archivo es permitir que la configuración del proveedor de documentos fiscales se configure desde la sede de Comercio. El formato de archivo está alineado con los requisitos para la configuración de integración fiscal.

### <a name="hardware-station-extension-design"></a>Diseño de extensiones de la estación de hardware

El propósito de la extensión que es un conector fiscal es comunicarse con el servicio de registro fiscal. La extensión de la estación de hardware utiliza el protocolo HTTP para enviar documentos que genera la extensión de CRT al servicio de registro fiscal. También maneja las respuestas que se reciben del servicio de registro fiscal.

#### <a name="request-handler"></a>Manejador de solicitudes

El manejador de solicitudes **EFRHandler** es el punto de entrada para manejar las solicitudes al servicio de registro fiscal.

El controlador se hereda de la interfaz **INamedRequestHandler**. El método **HandlerName** es responsable de devolver el nombre del controlador. El nombre del controlador debe coincidir con el nombre del conector fiscal que se especifica en la sede de Commerce.

El conector admite las siguientes solicitudes.

- **SubmitDocumentFiscalDeviceRequest** - Esta solicitud envía documentos al servicio de registro fiscal y devuelve una respuesta de ella.
- **IsReadyFiscalDeviceRequest** - Esta solicitud se utiliza para una verificación del servicio de registro fiscal.
- **InitializeFiscalDeviceRequest** - Esta solicitud se utiliza para inicializar el servicio de registro fiscal.

#### <a name="configuration"></a>Configuración

El archivo de configuración para el conector fiscal se encuentra en **src\\FiscalIntegration\\Efr\\Configurations\\Connectors\\ConnectorEFRSample.xml** en el repositorio de [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). El propósito del archivo es permitir la configuración del conector fiscal desde la sede de Comercio. El formato de archivo está alineado con los requisitos para la configuración de integración fiscal.

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

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
