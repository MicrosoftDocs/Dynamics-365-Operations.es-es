---
title: Ejemplo de integración de servicio de registro para Austria
description: Este tema proporciona una visión general del ejemplo de integración fiscal para Austria en Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: f03eab49f0abfc8a279ea43f69fa2ac0100bd34a
ms.sourcegitcommit: 0d2de52e12fdb9928556d37a4813a67b303695dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2021
ms.locfileid: "7945048"
---
# <a name="fiscal-registration-service-integration-sample-for-austria"></a>Ejemplo de integración de servicio de registro para Austria

[!include[banner](../includes/banner.md)]

Este tema proporciona una visión general del ejemplo de integración fiscal para Austria en Microsoft Dynamics 365 Commerce.

Para cumplir con los requisitos fiscales locales para las cajas registradoras en Austria, la funcionalidad de Dynamics 365 Retail para Austria incluye una integración de muestra del punto de venta (POS) con un servicio de registro fiscal externo. La muestra extiende la [funcionalidad de integración fiscal](fiscal-integration-for-retail-channel.md). Se basa en el [EFR (Registro Fiscal Electrónico)](https://www.efsta.eu/at/fiskalloesungen/oesterreich) solución de [EFSTA](https://www.efsta.eu/at/) y habilita la comunicación con el servicio EFR a través del protocolo HTTPS. El servicio EFR debe estar alojado en la estación de hardware minorista o en una máquina separada a la que se pueda conectar desde la estación de hardware. La muestra se proporciona en forma de código fuente y es parte del kit de desarrollo de software (SDK) de Retail.

Microsoft no publica ningún hardware, software o documentación de EFSTA. Para obtener información sobre cómo obtener la solución EFR y operarla, comuníquese con [EFSTA](https://www.efsta.eu/at/kontakt).

## <a name="scenarios"></a>Situaciones

Los siguientes escenarios están cubiertos por la muestra de integración de servicio de registro fiscal para Austria:

- Registro de transacciones en efectivo en el servicio de registro fiscal:

    - Envíe los datos detallados de la transacción al servicio de registro fiscal. Estos datos incluyen información de la línea de ventas e información sobre descuentos, pagos e impuestos.
    - Obtenga una respuesta del servicio de registro fiscal. Esta respuesta incluye una firma digital y un enlace a la transacción registrada.
    - Registre impuestos y asócielos con los códigos de impuestos del servicio de registro fiscal.
    - Imprima el código QR de una transacción registrada en el recibo.

- Registro de operaciones de tarjetas regalo y depósitos de clientes como transacciones no monetarias en el servicio de registro fiscal:

    - Emitir o agregar dinero a una tarjeta regalo.
    - Registrar un depósito de cuenta de cliente.
    - Registrar un depósito de orden de cliente.

- Registro de transacciones y eventos no de ventas como transacciones no monetarias en el servicio de registro fiscal:

    - Turno abierto y turno cerrado
    - Importe inicial, entrada flotante y eliminación de licitación
    - Reemplazar precio
    - Anulación de impuestos
    - Imprimir copia de recibo
    - Categoría abierta
    - Imprimir informe X
    - Imprimir informe Z

- Impresión de extractos al final del día (informes X / Z) que tienen campos específicos de Austria:

    - Número total de productos o servicios que se entregaron a los clientes
    - Desglose de ventas por tipo impositivo
    - Desglose de pagos por cajero / operador de caja registradora
    - Descuentos y devoluciones de precios que reducen las ventas diarias
    - Ventas cero (obsequios)

- Manejo de errores, como las siguientes opciones:

    - Vuelva a intentar el registro fiscal si es posible hacerlo, por ejemplo, si el servicio de registro fiscal no está disponible, no está listo o no responde.
    - Posponer registro fiscal.
    - Omita el registro fiscal o marque la transacción como registrada e incluya códigos de información para capturar el motivo del error e información adicional.
    - Compruebe la disponibilidad del servicio de registro fiscal antes de que se abra una nueva transacción de venta o se finalice una transacción de venta.

### <a name="gift-cards"></a>Tarjetas regalo

El ejemplo de integración del servicio de registro fiscal implementa las siguientes reglas relacionadas con las tarjetas de regalo:

- Excluya las líneas de ventas relacionadas con las operaciones *Emitir tarjeta de regalo* y *Agregar a la tarjeta de regalo* de una transacción en efectivo. En lugar de registrar esas líneas como parte de una transacción en efectivo, regístrelas como una transacción separada que no sea en efectivo en el servicio de registro fiscal.
- No imprima un desglose del grupo impositivo y un código QR en un recibo si el recibo consta solo de líneas de tarjetas de regalo.
- Imprima la cantidad total de tarjetas de regalo que se emiten o recargan en una transacción por separado del monto de la transacción en efectivo en el recibo.
- Guarde los ajustes calculados de las líneas de pago en la base de datos del canal con una referencia a una transacción fiscal correspondiente.
- El pago con tarjeta de regalo se considera un pago regular.

### <a name="customer-deposits-and-customer-order-deposits"></a>Depósitos de clientes y depósitos de pedidos de clientes

El ejemplo de integración del servicio de registro fiscal implementa las siguientes reglas relacionadas con los depósitos de clientes y depósitos de órdenes de clientes:

- Registre una transacción que no sea en efectivo si una transacción es un depósito de un cliente.
- Registre una transacción que no sea en efectivo si una transacción contiene solo un depósito de pedido de cliente o un reembolso de depósito de pedido de cliente.
- Reste el monto del depósito del pedido del cliente de las líneas de pago cuando se crea un pedido híbrido del cliente.
- Guarde los ajustes calculados de las líneas de pago en la base de datos del canal con una referencia a una transacción fiscal para un pedido de cliente híbrido.

### <a name="limitations-of-the-sample"></a>Limitaciones de la muestra

El servicio de registro fiscal solo admite escenarios en los que el impuesto sobre las ventas está incluido en el precio. Por lo tanto, la opción **El precio incluye el impuesto a las ventas** debe establecerse en **Sí** tanto para tiendas como para clientes.

## <a name="set-up-commerce-for-austria"></a>Configurar Commerce para Austria

Esta sección describe la configuración de comercio que es específica y recomendada para Austria. Para obtener más información sobre la configuración, consulte [Página de inicio de Commerce](../index.md).

Para utilizar la funcionalidad específica de Austria, debe especificar la siguiente configuración:

- En la dirección principal de la entidad jurídica, establezca el campo **País o región** en **AUT** (Austria).
- En el perfil de funcionalidad POS de cada tienda ubicada en Austria, configure el campo **Código ISO** como **AT** (Austria).

También debe especificar la siguiente configuración para Austria. Tenga en cuenta que debe ejecutar los trabajos de distribución adecuados después de completar la configuración.

### <a name="set-up-vat-per-austrian-requirements"></a>Configurar el IVA según los requisitos austriacos

Debe crear códigos de impuestos, grupos de impuestos y grupos de impuestos de artículo para los grupos de impuestos de artículos. También debe configurar la información de impuestos sobre las ventas para productos y servicios. Para obtener más información sobre cómo configurar y usar características de impuestos, consulte [Introducción a los impuestos](../../finance/general-ledger/indirect-taxes-overview.md).

En los recibos de ventas, puede imprimir un código abreviado para un código de impuesto sobre las ventas (por ejemplo, "A" o "B"). Para que esta funcionalidad esté disponible, configure el campo **Imprimir codigo** campo en la página **Códigos de impuestos sobre las ventas**.

### <a name="set-up-stores"></a>Configurar tiendas

Sobre la página **Todas las tiendas**, actualice los detalles de la tienda. En concreto, configurar los siguientes parámetros:

- En el campo **Grupo de impuestos**, especifique el grupo de impuestos que se debe usar para las ventas para el cliente predeterminado.
- Establezca la opción **Los precios incluyen impuestos** en **Sí**.
- Establezca el campo **Nombre** en el nombre de la empresa. Este cambio ayuda a garantizar que el nombre de la empresa aparezca en un recibo de compra. Alternativamente, puede agregar el nombre de la empresa al diseño del recibo de venta como texto de formato libre.
- Establezca el campo **Número de identificación fiscal (TIN)** en el número de identificación de la empresa. Este cambio ayuda a garantizar que el número de identificación de la empresa aparezca en un recibo de compra. Alternativamente, puede agregar el número de identificación de la empresa al diseño del recibo de venta como texto de formato libre.

### <a name="set-up-functionality-profiles"></a>Configuración de perfiles de funcionalidad

Configuración de perfiles de funcionalidad de PDV:

- Sobre la ficha desplegable **Numeración de recibos**, configure la numeración de recibos creando o actualizando registros para los tipos de transacciones de recibos **Rebaja**, **Órdenes de venta** y **Regreso**.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Configure campos personalizados para que se puedan usar en formatos de recibo para recibos de ventas

Puede configurar el texto del idioma y los campos personalizados que se utilizan en los formatos de recibo de POS. La empresa predeterminada del usuario que crea la configuración del recibo debe ser la misma entidad legal donde se crea la configuración del texto del idioma. Alternativamente, los textos en el mismo idioma deben crearse tanto en la empresa predeterminada del usuario como en la entidad legal de la tienda para la que se creó la configuración.

Sobre la página **Texto de idioma**, agregue los siguientes registros para las etiquetas de los campos personalizados para diseños de recibos. Tenga en cuenta que los valores **ID de idioma**, **ID de texto** y **Texto** que se muestran en la tabla son solo ejemplos. Puede cambiarlos fácilmente para satisfacer sus necesidades. Sin embargo, los valores **ID de texto** que use deben ser únicos y deben ser iguales o mayores que 900001.

Agregue las siguientes etiquetas POS a la sección **POS** de la página **Texto de idioma** de la tabla:

| Id. del idioma | Id. de texto | Texto                      |
|-------------|---------|---------------------------|
| en-US       | 900001  | Código QR                   |
| en-US       | 900002  | Número continuo         |
| en-US       | 900003  | Código de impresión de impuestos minoristas     |
| en-US       | 900004  | Total (ventas)             |
| en-US       | 900005  | Impuestos totales (ventas)         |
| en-US       | 900006  | Total con impuestos (ventas) |
| en-US       | 900007  | Importe de impuestos (ventas)        |
| en-US       | 900008  | Base impositiva (ventas)         |

Sobre la página **Campos personalizados**, agregue los siguientes registros para los campos personalizados para diseños de recibos. Tenga en cuenta que los valores **ID de texto de subtítulo** deben corresponder a los valores de **ID de texto** que especificó en la página **Texto de idioma**:

| Name                 | Tipo    | Id. de texto de leyenda |
|----------------------|---------|-----------------|
| QRCODE               | Recepción | 900001          |
| CONTINUOUSNUMBER     | Recepción | 900002          |
| RETAILPRINTCODE      | Recepción | 900003          |
| SALESTOTAL           | Recepción | 900004          |
| SALESTOTALTAX        | Recepción | 900005          |
| SALESTOTALINCLUDETAX | Recepción | 900006          |
| SALESTAXAMOUNT       | Recepción | 900007          |
| SALESTAXBASIS        | Recepción | 900008          |

> [!NOTE]
> Es importante que especifique los nombres de campo personalizados correctos, como se indica en la tabla anterior. Un nombre de campo personalizado incorrecto hará que falten datos en los recibos.

### <a name="configure-receipt-formats"></a>Configurar formatos de recibo

Para cada formato de recibo requerido, cambie el valor del campo **Comportamiento de impresión** a **Imprimir siempre**.

En el diseñador de formato de recibo, agregue los siguientes campos personalizados a las secciones de recibos correspondientes. Tenga en cuenta que los nombres de los campos corresponden a los textos de idioma que definió en la sección anterior.

- **Encabezamiento:** agregue los siguientes campos:

    - Los campos **Nombre de la tienda** y **Número de identificación de impuestos**, que se utilizan para imprimir el nombre de la empresa y el número de identidad en los recibos. Alternativamente, puede agregar el nombre de la empresa y el número de identidad al diseño como texto de formato libre.
    - Los campos **Dirección de la tienda**, **Fecha**, **Tiempo 24H**, **Número de recibo** y **Número de registro**.
    - Los campos **Número continuo**, para identificar el número de la transacción en efectivo en el servicio de registro fiscal.

- **Líneas:** agregue los siguientes campos:

    - **Nombre del artículo**.
    - **Cant.**
    - **Precio total con impuestos**.
    - **Código de impresión de impuestos minoristas**, que se utiliza para imprimir el código abreviado que corresponde al código de impuesto sobre las ventas que se aplica al artículo.

- **Pie de página:** agregue los siguientes campos:

    - Campos de pago, para que se impriman los importes de pago de cada método de pago. Por ejemplo, agregue los campos **Nombre de licitación** y **Monto de la licitación** a una línea del diseño.
    - Grupo de campos **Total de ventas**:

        - El campo **Ventas totales**, que se utiliza para imprimir el monto total de venta en efectivo del recibo. El importe excluye impuestos. Se excluyen las operaciones de prepago y tarjetas regalo.
        - El campo **Impuestos totales incluidos**, que se utiliza para imprimir el monto total de venta en efectivo del recibo. El importe incluye impuestos. Se excluyen las operaciones de prepago y tarjetas regalo.
        - El campo **Impuestos totales**, que se utiliza para imprimir el monto total de impuestos para ventas en efectivo. Se excluyen las operaciones de prepago y tarjetas regalo.

    - Grupo de campos **Desglose de impuestos**. Todos los campos de este grupo de campos deben imprimirse en una línea separada.

        - El campo **Identificación del impuesto**, que es un campo estándar que permite imprimir un resumen de impuestos sobre las ventas para cada código de impuestos sobre las ventas. El campo se agrega a una nueva línea.
        - El campo **Porcentaje de impuestos**, que es un campo estándar que se utiliza para imprimir la tasa impositiva efectiva para el código de impuesto sobre las ventas.
        - El campo **Base impositiva (ventas)**, que se utiliza para imprimir el monto total de ventas en efectivo para el código de impuestos. Se excluyen las operaciones de prepago y tarjetas regalo.
        - El campo **Importe de impuestos (ventas)**, que se utiliza para imprimir el monto de impuestos del recibo para las ventas en efectivo para el código de impuestos.
        - El campo **Código de impresión de impuestos minoristas**, que se utiliza para imprimir el código abreviado que corresponde al código de impuesto sobre las ventas.

    - El campo **Código QR**, que se utiliza para imprimir la referencia a la transacción en efectivo registrada en forma de código QR.

        > [!NOTE]
        > El valor **Código QR** se recupera de la respuesta del registro fiscal. EFR devuelve un código QR en su respuesta solo si el valor del campo **Atributos** en la configuración EFR se describe en la documentación de EFSTA. El formato del código QR en el campo **Atributos** en la configuración EFR debe establecerse en **BMP**.

Para obtener más información sobre cómo trabajar con formatos de recibo, consulte [Configurar y diseñar formatos de recibos](../receipt-templates-printing.md).

## <a name="set-up-fiscal-integration-for-austria"></a>Configurar integración fiscal para Austria

La muestra de integración de servicio de registro para Austria se basa en la [funcionalidad de integración fiscal](fiscal-integration-for-retail-channel.md) y es parte del SDK de Retail. La muestra se encuentra en la carpeta **src\\FiscalIntegration\\Efr** del repositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (por ejemplo, [la muestra en la versión/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). La muestra [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) de un proveedor de documentos fiscales, que es una extensión de Commerce Runtime (CRT) y un conector fiscal, que es una extensión de Commerce Hardware Station. Para obtener más información sobre cómo usar el SDK de Retail, consulte [Arquitectura de SDK minorista](../dev-itpro/retail-sdk/retail-sdk-overview.md) y [Configurar una canalización de compilación para el SDK de empaquetado independiente](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Debido a las limitaciones del [nuevo modelo de empaquetado y extensión independiente](../dev-itpro/build-pipeline.md), actualmente no se puede utilizar para esta muestra de integración fiscal. Debe utilizar la versión anterior de Retail SDK en una máquina virtual (VM) de desarrollador en Microsoft Dynamics Lifecycle Services (LCS). Para más información, vea [Directrices de implementación para la muestra de integración fiscal para Austria (heredada)](emea-aut-fi-sample-sdk.md). El soporte para el nuevo modelo de extensión y empaquetado independiente para muestras de integración fiscal está previsto para versiones posteriores.

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
    1. Abra **Configuraciones \> DocumentProviders** y descargue los archivos de configuración del proveedor de documentos fiscales: **DocumentProviderFiscalEFRSampleAustria.xml** y **DocumentProviderNonFiscalEFRSampleAustria.xml** (por ejemplo, [la ubicación de los archivos para su lanzamiento/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr/Configurations/DocumentProviders)).
    1. Descargue el archivo de configuración del conector fiscal en **Configuraciones \> Conectores \> ConnectorEFRSample.xml** (por ejemplo, [el archivo para lanzamiento/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/Connectors/ConnectorEFRSample.xml)).

    > [!WARNING]
    > Debido a las limitaciones del [nuevo modelo de empaquetado y extensión independiente](../dev-itpro/build-pipeline.md), actualmente no se puede utilizar para esta muestra de integración fiscal. Debe utilizar la versión anterior de Retail SDK en una máquina virtual (VM) de desarrollador en LCS. Los archivos de configuración para esta muestra de integración fiscal se encuentran en las siguientes carpetas del Retail SDK en una VM de desarrollador en LCS:
    >
    > - **Archivos de configuración del proveedor de documentos fiscales:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.EFRSample\\Configuration
    > - **Archivo de configuración del conector fiscal:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.EFRSample\\Configuration
    > 
    > El soporte para el nuevo modelo de extensión y empaquetado independiente para muestras de integración fiscal está previsto para versiones posteriores.

1. Vaya a **Retail y Commerce \> Configuración de sede central \> Parámetros \> Parámetros compartidos de Commerce**. En la pestaña **General**, configure la opción **Habilitar integración fiscal** en **Sí**.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Integración fiscal \> Proveedores de documentos fiscales** y cargue los archivos de configuración del proveedor de documentos fiscales que descargó antes.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Integración fiscal \> Conectores fiscales** y cargue el archivo de configuración del conector fiscal que descargó antes.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Integración fiscal \> Perfiles funcionales del conector**. Cree dos nuevos perfiles funcionales de conector, uno para cada proveedor de documentos fiscales que cargó anteriormente, y seleccione el conector fiscal que cargó anteriormente. Actualice la [configuración de mapeo de datos](#default-data-mapping) según sea necesario.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Integración fiscal \> Perfiles técnicos del conector**. Cree un nuevo perfil técnico de conector y seleccione el conector fiscal que cargó anteriormente. Actualice la [configuración del conector](#fiscal-connector-settings) según sea necesario.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Integración fiscal \> Grupos de conector fiscal**. Cree dos nuevos grupos de conectores fiscales, uno para cada perfil funcional de conector que creó anteriormente.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Integración fiscal \> Procesos de registro fiscal**. Cree un nuevo proceso de registro fiscal y dos pasos del proceso de registro fiscal, y seleccione los grupos de conectores fiscales que creó anteriormente.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> Perfiles de PDV \> Perfiles de funcionalidad**. Seleccione un perfil de funcionalidad que esté vinculado a la tienda donde se debe activar el proceso de registro. Sobre la ficha desplegable **Proceso de registro fiscal**, seleccione el proceso de registro fiscal que creó anteriormente. Para habilitar el registro de eventos no fiscales en el TPV, en la ficha desplegable **Funciones**, debajo de **PDV**, seleccione la opción **Auditoría** como **Sí**.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> Perfiles de PDV \> Perfiles de hardware**. Seleccione un perfil de hardware que esté vinculado a la estación de hardware a la que se conectará la impresora fiscal. Sobre la ficha desplegable **Periféricos fiscales**, seleccione el perfil técnico del conector que creó anteriormente.
1. Abra la programación de distribución (**Retail y Commerce \> TI de Retail y Commerce \> Programación de distribución**) y seleccione los trabajos **1070** y **1090** para transferir los datos a la base de datos del canal.

#### <a name="default-data-mapping"></a>Asignación de datos predeterminada

La siguiente asignación de datos predeterminada se incluye en la configuración del proveedor de documentos fiscales que se proporciona como parte de la muestra de integración fiscal:

- **Mapeo de tasas de impuesto al valor agregado (IVA)** - El mapeo de los valores porcentuales de impuestos que se configuran para los códigos de impuestos sobre las ventas a los valores de **TaxG** (grupo de impuestos) en las solicitudes que se envían al servicio fiscal. Aquí está la asignación predeterminada:

    ```
    A: 20.00; B: 10.00; C: 13.00; D: 0.00; E: 19.00; F: 7.00
    ```

    El primer componente de cada par representa un grupo de impuestos de IVA que es compatible con el servicio de registro fiscal EFR. El segundo componente representa la tasa de IVA correspondiente. Para obtener más información sobre los grupos de impuestos del IVA que EFR admite para Austria, consulte la [Referencia EFR](https://public.efsta.net/efr/).

#### <a name="fiscal-connector-settings"></a>Configuración del conector fiscal

La siguiente configuración se incluye en la configuración del conector fiscal que se proporciona como parte de la muestra de integración fiscal:

- **Dirección de punto final** - La URL del servicio de registro fiscal.
- **Tiempo de espera del dispositivo** - La cantidad de tiempo, en milisegundos, que el conector fiscal esperará una respuesta del servicio de registro fiscal.
- **Mostrar notificaciones de registro fiscal** - Esta bandera controla si las notificaciones que devuelve el servicio de registro fiscal deben mostrarse al operador.

### <a name="configure-channel-components"></a>Configurar los componentes de canal

> [!WARNING]
> Debido a las limitaciones del [nuevo modelo de empaquetado y extensión independiente](../dev-itpro/build-pipeline.md), actualmente no se puede utilizar para esta muestra de integración fiscal. Debe utilizar la versión anterior de Retail SDK en una máquina virtual (VM) de desarrollador en LCS. Para más información, vea [Directrices de implementación para la muestra de integración fiscal para Austria (heredada)](emea-aut-fi-sample-sdk.md).
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

1. Instale las extensiones de la estación de hardware:

    1. En la carpeta **Efr\\HardwareStation\\HardwareStation.EFR.Installer\\bin\\Debug\\net461**, busque el instalador **HardwareStation.EFR.Installer**.
    1. Inicie el instalador de extensiones desde la línea de comandos.

        ```Console
        HardwareStation.EFR.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Entorno de producción

Siga los pasos en [Configurar una canalización de compilación para una muestra de integración fiscal](fiscal-integration-sample-build-pipeline.md) para generar y lanzar la unidad de escala en la nube y los paquetes implementables de autoservicio para la muestra de integración fiscal. El archivo YAML de plantilla **EFR build-pipeline.yml** se puede encontrar en la carpeta **Pipeline\\YAML_Files** del repositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-extensions"></a>Diseño de las extensiones

La muestra de integración de servicio de registro para Austria se basa en la [funcionalidad de integración fiscal](fiscal-integration-for-retail-channel.md) y es parte del SDK de Retail. La muestra se encuentra en la carpeta **src\\FiscalIntegration\\Efr** del repositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (por ejemplo, [la muestra en la versión/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). La muestra [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) de un proveedor de documentos fiscales, que es una extensión de CRT y un conector fiscal, que es una extensión de Commerce Hardware Station. Para obtener más información sobre cómo usar el SDK de Retail, consulte [Arquitectura de SDK minorista](../dev-itpro/retail-sdk/retail-sdk-overview.md) y [Configurar una canalización de compilación para el SDK de empaquetado independiente](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Debido a las limitaciones del [nuevo modelo de empaquetado y extensión independiente](../dev-itpro/build-pipeline.md), actualmente no se puede utilizar para esta muestra de integración fiscal. Debe utilizar la versión anterior de Retail SDK en una máquina virtual (VM) de desarrollador en LCS. Para más información, vea [Directrices de implementación para la muestra de integración fiscal para Austria (heredada)](emea-aut-fi-sample-sdk.md). El soporte para el nuevo modelo de extensión y empaquetado independiente para muestras de integración fiscal está previsto para versiones posteriores.

### <a name="commerce-runtime-extension-design"></a>Diseño de extensión de Commerce Runtime

El propósito de la extensión que es un proveedor de documentos fiscales es generar documentos específicos del servicio y manejar respuestas desde el servicio de registro fiscal.

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

Los archivos de configuración para el proveedor de documentos fiscales se encuentran en la carpeta **src\\FiscalIntegration\\Efr\\Configurations\\DocumentProviders** del repositorio de [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/):

- **DocumentProviderFiscalEFRSampleAustria** - El archivo de configuración del proveedor de documentos fiscales para documentos fiscales.
- **DocumentProviderNonFiscalEFRSampleAustria** – El archivo de configuración del proveedor de documentos no fiscales para documentos fiscales.

El propósito de estos archivos es permitir que la configuración del proveedor de documentos fiscales se configure desde la sede de Comercio. El formato de archivo está alineado con los requisitos para la configuración de integración fiscal.

### <a name="hardware-station-extension-design"></a>Diseño de extensiones de la estación de hardware

El propósito de la extensión que es un conector fiscal es comunicarse con el servicio de registro fiscal. La extensión de la estación de hardware utiliza el protocolo HTTP para enviar documentos que genera la extensión de CRT al servicio de registro fiscal. También maneja las respuestas que se reciben del servicio de registro fiscal.

#### <a name="request-handler"></a>Manejador de solicitudes

El manejador de solicitudes **EFRHandler** es el punto de entrada para manejar las solicitudes al servicio de registro fiscal.

El controlador se hereda de la interfaz **INamedRequestHandler**. El método **HandlerName** es responsable de devolver el nombre del controlador. El nombre del controlador debe coincidir con el nombre del conector fiscal que se especifica en la sede de Commerce.

El conector fiscal admite las siguientes solicitudes:

- **SubmitDocumentFiscalDeviceRequest** - Esta solicitud envía documentos al servicio de registro fiscal y devuelve una respuesta de ella.
- **IsReadyFiscalDeviceRequest** - Esta solicitud se utiliza para una verificación del servicio de registro fiscal.
- **InitializeFiscalDeviceRequest** - Esta solicitud se utiliza para inicializar el servicio de registro fiscal.

#### <a name="configuration"></a>Configuración

El archivo de configuración para el conector fiscal se encuentra en **src\\FiscalIntegration\\Efr\\Configurations\\Connectors\\ConnectorEFRSample.xml** en el repositorio de [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). El propósito del archivo es permitir la configuración del conector fiscal desde la sede de Comercio. El formato de archivo está alineado con los requisitos para la configuración de integración fiscal.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
