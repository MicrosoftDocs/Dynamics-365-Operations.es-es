---
title: Ejemplo de integración de servicio de registro fiscal para Alemania
description: Este tema proporciona una visión general del ejemplo de integración fiscal para Alemania en Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 03/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2020-5-29
ms.openlocfilehash: 65315a9fd6bc1af26bc225220e096aee4da09be2
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2022
ms.locfileid: "8388168"
---
# <a name="fiscal-registration-service-integration-sample-for-germany"></a>Ejemplo de integración de servicio de registro fiscal para Alemania

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

Este tema proporciona una visión general del ejemplo de integración fiscal para Alemania en Microsoft Dynamics 365 Commerce.

Para cumplir con los requisitos fiscales locales para las cajas registradoras en Alemania, la funcionalidad de Microsoft Dynamics 365 Commerce para Alemania incluye una integración de muestra del punto de venta (POS) con un servicio de registro fiscal externo. La muestra extiende la [funcionalidad de integración fiscal](fiscal-integration-for-retail-channel.md). Se basa en el [EFR (Registro Fiscal Electrónico)](https://www.efsta.eu/de/fiskalloesungen/deutschland) solución de [EFSTA](https://www.efsta.eu/de/) y habilita la comunicación con el servicio EFR a través del protocolo HTTPS. El servicio EFR debe estar alojado en la estación de hardware minorista o en un equipo separado al que se pueda conectar desde la estación de hardware. La muestra se proporciona en forma de código fuente y es parte del kit de desarrollo de software (SDK) de Retail.

Microsoft no publica ningún hardware, software o documentación de EFSTA. Para obtener información sobre cómo obtener la solución EFR y operarla, comuníquese con [EFSTA](https://www.efsta.eu/de/kontakt/kontakt).

## <a name="scenarios"></a>Situaciones

Los siguientes escenarios están cubiertos por la muestra de integración de servicio de registro fiscal para Alemania.

### <a name="sales-operations"></a>Operaciones de ventas

- **Registro de ventas y devoluciones cash-and-carry en el servicio de registro fiscal:**

    El registro de operaciones de venta incluye los siguientes pasos:

    1. Registro del inicio de la transacción

        El inicio de cada transacción se registra en un elemento técnico de seguridad (TSE) que está conectado al servicio EFR. Como resultado del registro, un TSE asigna un ID de transacción (TID).

    2. Registro del fin de la transacción

        Cuando se concluye una transacción en el POS, se registra utilizando el mismo TID que se asignó durante el registro del inicio de la transacción. En ese momento, se envían los datos detallados de la transacción al servicio de registro fiscal. Estos datos incluyen información de la línea de ventas e información sobre descuentos, pagos e impuestos.

    3. Capturar una respuesta del servicio de registro fiscal

        Los datos de seguridad se reciben de un TSE como parte de una respuesta y se guardan en la transacción en la base de datos del canal. Los datos de seguridad constan de la siguiente información:

        - TID
        - Fecha y hora del inicio de la transacción
        - Fecha y hora del fin de la transacción
        - Contador de firmas
        - Comprobar valor
        - Número de serie de TSE

- **Registro de pedidos de clientes en el servicio de registro fiscal:** El proceso de registro es el mismo que el proceso para las ventas y devoluciones de cash-and-carry.
- **Registro de operaciones que implican tarjetas regalo y depósitos:** El proceso de registro es el mismo que el proceso para las ventas y devoluciones de cash-and-carry.

#### <a name="notifying-users-about-fiscal-registration-failures"></a>Notificar a los usuarios sobre fallas en el registro fiscal

Hay dos formas en que el servicio de registro fiscal puede notificar a los usuarios sobre fallas ocurridas durante el registro fiscal:

- Imprima información adicional de la respuesta en el campo **Mensaje de información** en los recibos.
- Mostrar notificaciones del servicio fiscal como mensajes de usuario en el TPV.

    > [!NOTE]
    > Este mecanismo de notificación requiere que el parámetro **Mostrar notificaciones de registro fiscal** de la página **Perfiles técnicos de conector** esté activado.

#### <a name="printing-receipts"></a>Impresión de recibos

La impresión de recibos es obligatoria en Alemania. Todos los recibos deben contener al menos la siguiente información:

- Nombre y dirección de la empresa
- Información sobre los bienes, incluidos sus precios y cantidades
- Información sobre los pagos que se recibieron
- Información sobre impuestos, incluidos los montos totales por tasa impositiva
- Datos de seguridad:

    - TID
    - Fecha y hora del inicio de la transacción
    - Fecha y hora del fin de la transacción
    - Contador de firmas
    - Comprobar valor
    - Número de serie de TSE

- Mensaje informativo

> [!NOTE]
> También se puede imprimir un código QR en los recibos. Aunque el código QR es opcional, es muy recomendable. Para obtener más información sobre cómo obtener un código QR como parte de una respuesta del servicio de registro fiscal, consulte el documento "Guía de EFR \[DE\]" que se publica en el sitio web [Documentación EFSTA](https://public.efsta.net/efr/).
>
> El campo **Mensaje de información** de los recibos muestra una notificación del servicio de registro fiscal. Por ejemplo, si un dispositivo de firma está averiado, se puede imprimir un texto especial en un recibo.

#### <a name="voided-suspended-and-recalled-transactions"></a>Transacciones vacías, supendidas y recuperadas

- Una transacción anulada se registra como una solicitud para terminar una transacción en el servicio de registro fiscal.
- Una transacción suspendida se registra como una solicitud para terminar una transacción en el servicio de registro fiscal.
- La recuperación de una transacción suspendida se registra como el inicio de una nueva transacción en el servicio de registro fiscal.

### <a name="non-sales-transactions-and-shift-closing"></a>Transacciones no comerciales y cierre de turnos

Las siguientes transacciones que no son de venta se registran como operaciones no fiscales en el servicio de registro fiscal mediante la etiqueta **NFS**:

- Declarar importe inicial
- Entrada flotante
- Supresión de forma de pago
- Ingreso seguro
- Ingreso bancario
- Cuentas de ingresos
- Cuentas de gastos

La operación **Cerrar turno** también se registra como operación no fiscal en el servicio de registro fiscal mediante la etiqueta **NFS**.

### <a name="data-export-and-audit"></a>Exportación de datos y auditoría

Todas las transacciones deben estar firmadas por un TSE para garantizar su integridad, autenticidad e integridad, y para ayudar a prevenir la manipulación de los datos registrados.

> [!WARNING]
> Solo se puede utilizar un TSE certificado. Para obtener información sobre los tipos y modelos de TSE compatibles con la solución EFR, consulte el documento "Guía de EFR \[DE\]" que se publica en el sitio web [Documentación EFSTA](https://public.efsta.net/efr/). Para obtener información sobre cómo elegir y obtener un TSE, comuníquese con [EFSTA](https://www.efsta.eu/at/kontakt).

Las regulaciones en Alemania requieren soporte para la exportación DSFinV-K. La exportación de DSFinV-K se puede activar en la solución EFR. Para obtener más información sobre la exportación DSFinV-K, consulte el documento "Guía de EFR \[DE\]" que se publica en el sitio web [Documentación EFSTA](https://public.efsta.net/efr/).

### <a name="limitations-of-the-sample"></a>Limitaciones de la muestra

El servicio de registro fiscal solo admite escenarios en los que el impuesto sobre las ventas está incluido en los precios. Por lo tanto, la opción **Los precios incluyen el impuesto a las ventas** debe establecerse en **Sí** tanto para tiendas como para clientes.

El servicio fiscal no admite situaciones en las que se aplica más de un código de impuesto sobre las ventas a la misma línea de transacción.

El marco de integración fiscal no admite cotizaciones de ventas. Por tanto, esas operaciones no están registradas en el servicio fiscal.

## <a name="set-up-commerce-for-germany"></a>Configurar Commerce para Alemania

Esta sección describe la configuración de comercio que es específica y recomendada para Alemania. Para obtener más información sobre la configuración, consulte la [página principal de Commerce](../index.md).

Para utilizar la funcionalidad específica de Alemania, debe especificar la siguiente configuración.

- En la dirección principal de la entidad jurídica, establezca el campo **País o región** en **DEU** (Alemania).
- En el perfil de funcionalidad POS de cada tienda ubicada en Alemania, configure el campo **Código ISO** como **DE** (Alemania).

También debe especificar la siguiente configuración para Alemania. Asegúrese de ejecutar los trabajos de distribución adecuados después de completar la configuración.

### <a name="set-up-vat-per-german-requirements"></a>Configurar el IVA según los requisitos de Alemania

Debe crear códigos de impuestos, grupos de impuestos y grupos de impuestos de artículo para los grupos de impuestos de artículos. También debe configurar la información de impuestos sobre las ventas para productos y servicios. Para obtener más información sobre cómo configurar y usar características de impuestos, consulte [Introducción a los impuestos](../../finance/general-ledger/indirect-taxes-overview.md).

En los recibos de ventas, puede imprimir un código abreviado para un código de impuesto sobre las ventas (por ejemplo, "A" o "B"). Para que esta funcionalidad esté disponible, configure el campo **Código para impresión** campo en la página **Códigos de impuestos sobre las ventas**.

### <a name="set-up-stores"></a>Configurar tiendas

Sobre la página **Todas las tiendas**, actualice los detalles de la tienda. En concreto, configurar los siguientes parámetros:

- En el campo **Grupo de impuestos**, especifique el grupo de impuestos que se debe usar para las ventas para el cliente predeterminado.
- Establezca la opción **Los precios incluyen impuestos** en **Sí**.
- Establezca el campo **Nombre** en el nombre de la empresa. Este cambio ayuda a garantizar que el nombre de la empresa aparezca en un recibo de compra. Alternativamente, puede agregar el nombre de la empresa al diseño del recibo de venta como texto de formato libre.
- Establezca el campo **Número de identificación fiscal (TIN)** en el número de identificación de la empresa. Este cambio ayuda a garantizar que el número de identificación de la empresa aparezca en un recibo de compra. Alternativamente, puede agregar el número de identificación de la empresa al diseño del recibo de venta como texto de formato libre.

### <a name="set-up-functionality-profiles"></a>Configuración de perfiles de funcionalidad

Configuración de perfiles de funcionalidad de PDV. Sobre la ficha desplegable **Numeración de recibos**, configure la numeración de recibos creando o actualizando registros para los tipos de transacciones de recibos **Rebaja**, **Órdenes de venta** y **Regreso**.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Configure campos personalizados para que se puedan usar en formatos de recibo para recibos de ventas

Puede configurar el texto del idioma y los campos personalizados que se utilizan en los formatos de recibo de POS. La empresa predeterminada del usuario que crea la configuración del recibo debe ser la misma entidad legal donde se crea la configuración del texto del idioma. Alternativamente, los textos en el mismo idioma deben crearse tanto en la empresa predeterminada del usuario como en la entidad legal de la tienda para la que se creó la configuración.

Sobre la página **Texto de idioma**, agregue los siguientes registros para las etiquetas de los campos personalizados para diseños de recibos. Tenga en cuenta que los valores **ID de idioma**, **ID de texto** y **Texto** que se muestran en la tabla son solo ejemplos. Puede cambiarlos fácilmente para satisfacer sus necesidades. Sin embargo, los valores **ID de texto** que use deben ser únicos y deben ser iguales o mayores que 900001.

Agregue las siguientes etiquetas POS a la sección **POS** de la página **Texto de idioma**.

| Id. del idioma | Id. de texto | Texto                                  |
|-------------|---------|---------------------------------------|
| en-US       | 900001  | Código QR                               |
| en-US       | 900002  | Id. de transacción                        |
| en-US       | 900003  | Código de impresión de impuestos minoristas                 |
| en-US       | 900004  | Importe de impuestos (ventas)                    |
| en-US       | 900005  | Base impositiva (ventas)                     |
| en-US       | 900006  | Fecha y hora de inicio de la transacción           |
| en-US       | 900007  | Fecha y hora de finalización de la transacción             |
| en-US       | 900008  | Número de serie del elemento de seguridad |
| en-US       | 900009  | Contador de firmas                     |
| en-US       | 900010  | Comprobar valor                           |
| en-US       | 900011  | Mensaje de información                          |

Sobre la página **Campos personalizados**, agregue los siguientes registros para los campos personalizados para diseños de recibos. Tenga en cuenta que los valores **ID de texto de subtítulo** deben corresponder a los valores de **ID de texto** que especificó en la página **Texto de idioma**.

| Name                            | Tipo    | Id. de texto de leyenda |
|---------------------------------|---------|-----------------|
| QRCODE\_DE                      | Recepción | 900001          |
| TRANSACTIONID\_DE               | Recepción | 900002          |
| RETAILPRINTCODE\_DE             | Recepción | 900003          |
| SALESTAXAMOUNT\_DE              | Recepción | 900004          |
| SALESTAXBASIS\_DE               | Recepción | 900005          |
| TRANSACTIONSTARTDATETIME\_DE    | Recepción | 900006          |
| TRANSACTIONENDDATETIME\_DE      | Recepción | 900007          |
| SECURITYELEMENTSERIALNUMBER\_DE | Recepción | 900008          |
| SIGNCOUNTER\_DE                 | Recepción | 900009          |
| SIGN\_DE                        | Recepción | 900010          |
| INFOMESSAGE\_DE                 | Recepción | 900011          |

> [!NOTE]
> Es importante que especifique los nombres de campo personalizados correctos, como se indica en la tabla anterior. Un nombre de campo personalizado incorrecto hará que falten datos en los recibos.

### <a name="configure-receipt-formats"></a>Configurar formatos de recibo

Para cada formato de recibo que es requerido, cambie el valor del campo **Comportamiento de impresión** a **Imprimir siempre**.

En el diseñador de formato de recibo, agregue los siguientes campos personalizados a las secciones de recibos correspondientes. Tenga en cuenta que los nombres de los campos corresponden a los textos de idioma que definió en la sección anterior.

- **Encabezamiento:** agregue los siguientes campos:

    - Los campos **Nombre de la tienda** y **Número de identificación de impuestos**, que se utilizan para imprimir el nombre de la empresa y el número de identificación en los recibos. Alternativamente, puede agregar el nombre de la empresa y el número de identificación al diseño como texto de formato libre.
    - Los campos **Dirección de la tienda**, **Fecha**, **Tiempo 24H**, **Número de recibo** y **Número de registro**.

- **Líneas:** agregue los siguientes campos:

    - Campo **Nombre del artículo**
    - Campo **Cant.**
    - Campo **Precio total con impuestos**
    - Campo **Código de impresión de impuestos minoristas**, que se utiliza para imprimir el código abreviado que corresponde al código de impuesto sobre las ventas que se aplica al artículo

- **Pie de página:** agregue los siguientes campos:

    - Campos de pago, para que se impriman los importes de pago de cada método de pago. Por ejemplo, agregue los campos **Nombre de licitación** y **Monto de la licitación** a una línea del diseño.
    - Campos del grupo de campos **Desglose de impuestos**. Todos los campos de este grupo de campos deben imprimirse en una línea separada.

        - El campo **Identificación del impuesto**, que es un campo estándar que permite imprimir un resumen de impuestos sobre las ventas para cada código de impuestos sobre las ventas. El campo se agrega a una nueva línea.
        - El campo **Porcentaje de impuestos**, que es un campo estándar que se utiliza para imprimir la tasa impositiva efectiva para el código de impuesto sobre las ventas.
        - El campo **Base impositiva (ventas)**, que se utiliza para imprimir el monto total de ventas en efectivo para el código de impuestos. Se excluyen las operaciones de prepago y tarjetas regalo.
        - El campo **Importe de impuestos (ventas)**, que se utiliza para imprimir el monto de impuestos del recibo para las ventas en efectivo para el código de impuestos.
        - El campo **Código de impresión de impuestos minoristas**, que se utiliza para imprimir el código abreviado que corresponde al código de impuesto sobre las ventas.

    - Campos que contienen datos de transacciones seguras que devuelve el servicio de registro fiscal:

        - Campo **Id. de transacción**, que identifica el número de la transacción en efectivo en el servicio de registro fiscal
        - Campo **Fecha/hora de inicio de la transacción**
        - Campo **Fecha/hora de fin de la transacción**
        - Campo **Número de serie del elemento de seguridad**
        - Campo **Contador de firmas**
        - Campo **Comprobar valor**
        - Campo **Código QR**, que se utiliza para imprimir la referencia a la transacción en efectivo registrada en forma de un código QR

        > [!NOTE]
        > El valor **Código QR** se recupera de la respuesta del registro fiscal. EFR devuelve un código QR en su respuesta solo si el valor del campo **Atributos** en la configuración EFR se describe en la documentación de EFSTA. El formato del código QR en el campo **Atributos** en la configuración EFR debe establecerse en **BMP**.

    - Campo **Mensaje de información** para poder mostrar los mensajes de notificación del servicio de registro fiscal en los recibos. Por ejemplo, si un dispositivo de firma está averiado, se puede imprimir un texto especial en un recibo.

Para obtener más información sobre cómo trabajar con formatos de recibo, consulte [Configurar y diseñar formatos de recibos](../receipt-templates-printing.md).

## <a name="set-up-fiscal-integration-for-germany"></a>Configurar integración fiscal para Alemania

La muestra de integración de servicio de registro para Alemania se basa en la [funcionalidad de integración fiscal](fiscal-integration-for-retail-channel.md) y es parte del SDK de Retail. La muestra se encuentra en la carpeta **src\\FiscalIntegration\\Efr** del repositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (por ejemplo, [la muestra en la versión/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). La muestra [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) de un proveedor de documentos fiscales, que es una extensión de Commerce Runtime (CRT) y un conector fiscal, que es una extensión de Commerce Hardware Station. Para obtener más información sobre cómo usar el SDK de Retail, consulte [Arquitectura de SDK minorista](../dev-itpro/retail-sdk/retail-sdk-overview.md) y [Configurar una canalización de compilación para el SDK de empaquetado independiente](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Debido a las limitaciones del [nuevo modelo de empaquetado y extensión independiente](../dev-itpro/build-pipeline.md), actualmente no se puede utilizar para esta muestra de integración fiscal. Debe utilizar la versión anterior de Retail SDK en una máquina virtual (VM) de desarrollador en Microsoft Dynamics Lifecycle Services (LCS). Para más información, vea [Directrices de implementación para la muestra de integración fiscal para Alemania (heredada)](emea-deu-fi-sample-sdk.md).
>
> El soporte para el nuevo modelo de extensión y empaquetado independiente para muestras de integración fiscal está previsto para versiones posteriores.

Complete los pasos de configuración de la integración fiscal como se describe en [Configurar la integración fiscal para los canales comerciales](setting-up-fiscal-integration-for-retail-channel.md):

1. [Configuración de un proceso de registro fiscal](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Además, tome nota de la configuración del proceso de registro fiscal que es [específico para esta muestra de integración de servicio de registro fiscal](#set-up-the-registration-process).
1. [Establecimiento de la configuración de tratamiento de errores](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

    > [!WARNING]
    > Es posible que las capacidades de manejo de errores del marco de integración fiscal no estén completamente alineadas con las regulaciones fiscales locales.
    >
    > - Le recomendamos que deje la opción **Continuar en caso de error** en la página **Proceso de registro fiscal** desactivada, porque todas las transacciones deben registrarse correctamente, incluso si el primer intento de registro fiscal no tuvo éxito.
    > - Antes de activar la opción **Omitir** o **Marcar como registrado** de la página **Proceso de registro fiscal**, debe discutir estos cambios en el proceso de registro fiscal con su asesor fiscal o la oficina fiscal local.

1. [Habilitar la ejecución manual del registro fisca postpuesto](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Configurar los componentes de canal](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Configuración del proceso de registro fiscal

Para habilitar el proceso de registro, siga estos pasos para configurar Commerce Headquarters. Para obtener más información, consulte [Configurar la integración fiscal para los canales de Commerce](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Descargue los archivos de configuración para el proveedor de documentos fiscales y el conector fiscal:

    1. Abra el respositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Seleccione una versión de rama de lanzamiento correcta de acuerdo con su SDK/versión de la aplicación (por ejemplo, **[lanzamiento/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Abra **src \> FiscalIntegration \> Efr**.
    1. Descargue el archivo de configuración del proveedor de documentos fiscales en **Configurations \> DocumentProviders \> DocumentProviderFiscalEFRSampleGermany.xml** (por ejemplo, [el archivo para lanzamiento/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/DocumentProviders/DocumentProviderFiscalEFRSampleGermany.xml)).
    1. Descargue el archivo de configuración del conector fiscal en **Configuraciones \> Conectores \> ConnectorEFRSample.xml** (por ejemplo, [el archivo para lanzamiento/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/Connectors/ConnectorEFRSample.xml)).

    > [!WARNING]
    > Debido a las limitaciones del [nuevo modelo de empaquetado y extensión independiente](../dev-itpro/build-pipeline.md), actualmente no se puede utilizar para esta muestra de integración fiscal. Debe utilizar la versión anterior de Retail SDK en una máquina virtual (VM) de desarrollador en LCS. Los archivos de configuración para esta muestra de integración fiscal se encuentran en las siguientes carpetas del Retail SDK en una VM de desarrollador en LCS:
    >
    > - **Archivo de configuración de proveedor de documento fiscal:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.EFRSample\\Configuration\\DocumentProviderFiscalEFRSampleGermany.xml
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

- **Mapeo de tipo de licitación** - El mapeo de los métodos de pago a los valores del atributo **PayG** (grupo de pago) en las solicitudes que se envían al servicio fiscal. Aquí está la asignación predeterminada:

    ```
    1: 0; 2: 1; 3: 3; 4: 8; 5: 2; 6: 0; 7: 7; 8: 6; 9: 0; 10: 8; 11: 1
    ```

    El primer componente de cada par representa un método de pago configurado para la tienda. El segundo componente representa el grupo de pago correspondiente que es compatible con el servicio de registro fiscal EFR. Para obtener más información sobre los grupos de pago que EFR admite para Alemania, consulte la [Referencia EFR](https://public.efsta.net/efr/).

    La asignación de ejemplo de métodos de pago se corresponde con los métodos de pago de la tienda que están configurados en los datos de demostración estándar.

    | Método de pago | Nombre de método de pago |
    |----------------|---------------------|
    | 1              | Efectivo                |
    | 2              | Comprobar               |
    | 3              | Tarjeta                |
    | 4              | Cuenta de cliente    |
    | 5              | Otra               |
    | 6              | Divisa            |
    | 7              | Comprobante             |
    | 8              | Tarjeta regalo           |
    | 9              | Quitar forma de pago/flotante |
    | 10             | Tarjetas de fidelización       |
    | 11             | Cheques no locales    |

    Por lo tanto, debe modificar la asignación de muestra de acuerdo con los métodos de pago que están configurados en su aplicación.

- **Incluir datos del cliente** - Si este parámetro está activado, las solicitudes al servicio fiscal contendrán información del cliente, como nombres y direcciones, en los casos en que se agregue un cliente a una transacción.
- **Mapeo de tasas de impuesto al valor agregado (IVA)** - El mapeo de los valores porcentuales de impuestos que se configuran para los códigos de impuestos sobre las ventas a los valores de **TaxG** (grupo de impuestos) en las solicitudes que se envían al servicio fiscal. Aquí está la asignación predeterminada:

    ```
    A: 19.00; B: 7.00; C: 10.70; D: 5.50; E: 0.00
    ```

    El primer componente de cada par representa un grupo de impuestos de IVA que es compatible con el servicio de registro fiscal EFR. El segundo componente representa la tasa de IVA correspondiente. Para obtener más información sobre los grupos de impuestos del IVA que EFR admite para Alemania, consulte la [Referencia EFR](https://public.efsta.net/efr/).

- **Grupo fiscal para tarjetas regalo y depósitos** - El valor del atributo **TaxG** en las solicitudes que se envían al servicio fiscal, en base a operaciones que involucran tarjetas regalo o depósitos. Aquí está la asignación predeterminada:

    ```
    G
    ```

- **Grupo fiscal exento de IVA** - El valor del atributo **TaxG** en las solicitudes que se envían al servicio fiscal, con base en operaciones que se encuentran exentas de obligaciones tributarias. Aquí está la asignación predeterminada:

    ```
    F
    ```

> [!NOTE]
> La configuración de impuestos en la asignación de datos predeterminada es responsable de hacer coincidir la configuración de impuestos en el sistema y los grupos de impuestos en el servicio EFR. Los grupos de impuestos se pueden imprimir en los recibos solo si el campo **Código para imprimir** se establece en la página **Códigos de impuestos sobre las ventas**.

#### <a name="fiscal-connector-settings"></a>Configuración del conector fiscal

La siguiente configuración se incluye en la configuración del conector fiscal que se proporciona como parte de la muestra de integración fiscal:

- **Dirección de punto final** - La URL del servicio de registro fiscal.
- **Tiempo de espera** - La cantidad de tiempo, en milisegundos, que el conector fiscal esperará una respuesta del servicio de registro fiscal.
- **Mostrar notificaciones de registro fiscal** - Esta bandera controla si las notificaciones que devuelve el servicio de registro fiscal deben mostrarse al operador.

### <a name="configure-channel-components"></a>Configurar los componentes de canal

> [!WARNING]
> Debido a las limitaciones del [nuevo modelo de empaquetado y extensión independiente](../dev-itpro/build-pipeline.md), actualmente no se puede utilizar para esta muestra de integración fiscal. Debe utilizar la versión anterior de Retail SDK en una máquina virtual (VM) de desarrollador en LCS. Para más información, vea [Directrices de implementación para la muestra de integración fiscal para Alemania (heredada)](emea-deu-fi-sample-sdk.md).
>
> El soporte para el nuevo modelo de extensión y empaquetado independiente para muestras de integración fiscal está previsto para versiones posteriores.

#### <a name="set-up-the-development-environment"></a>Configurar el entorno de desarrollo

Para configurar un entorno de desarrollo para probar y ampliar la muestra, siga estos pasos.

1. Clonar o descargar el repositorio de [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions). Seleccione una versión de rama de lanzamiento correcta de acuerdo con su SDK/versión de la aplicación. Para más información, vea [Descargar muestras y paquetes de referencia del SDK de Retail desde GitHub y NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Abra la solución EFR en **Dynamics365Commerce.Solutions\\FiscalIntegration\\Efr\\EFR.sln** y compílela.
1. Instalar las extensiones de Commerce Runtime:

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

La muestra de integración de servicio de registro para Alemania se basa en la [funcionalidad de integración fiscal](fiscal-integration-for-retail-channel.md) y es parte del SDK de Retail. La muestra se encuentra en la carpeta **src\\FiscalIntegration\\Efr** del repositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (por ejemplo, [la muestra en la versión/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). La muestra [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) de un proveedor de documentos fiscales, que es una extensión de CRT y un conector fiscal, que es una extensión de Commerce Hardware Station. Para obtener más información sobre cómo usar el SDK de Retail, consulte [Arquitectura de SDK minorista](../dev-itpro/retail-sdk/retail-sdk-overview.md) y [Configurar una canalización de compilación para el SDK de empaquetado independiente](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Debido a las limitaciones del [nuevo modelo de empaquetado y extensión independiente](../dev-itpro/build-pipeline.md), actualmente no se puede utilizar para esta muestra de integración fiscal. Debe utilizar la versión anterior de Retail SDK en una máquina virtual (VM) de desarrollador en LCS. Para más información, vea [Directrices de implementación para la muestra de integración fiscal para Alemania (heredada)](emea-deu-fi-sample-sdk.md). El soporte para el nuevo modelo de extensión y empaquetado independiente para muestras de integración fiscal está previsto para versiones posteriores.

### <a name="crt-extension-design"></a>Diseño de la extensión CRT

El propósito de la extensión que es un proveedor de documentos fiscales es generar documentos específicos del servicio y manejar respuestas desde el servicio de registro fiscal.

#### <a name="request-handler"></a>Manejador de solicitudes

Hay un solo gestor de solicitudes para el proveedor de documentos, **DocumentProviderEFRFiscalDEU**. Este controlador se utiliza para generar documentos fiscales para el servicio de registro fiscal. Se hereda de la interfaz **INamedRequestHandler**. El método **HandlerName** es responsable de devolver el nombre del controlador. El nombre del controlador debe coincidir con el nombre del proveedor de documentos del conector que se especifica en la sede de Comercio.

El conector admite las siguientes solicitudes:

- **GetFiscalDocumentDocumentProviderRequest** - Esta solicitud contiene información sobre qué documento se debe generar. Devuelve un documento específico del servicio que debe registrarse en el servicio de registro fiscal.
- **GetFiscalTransactionExtendedDataDocumentProviderRequest** - Esta solicitud devuelve la respuesta junto con datos extendidos.

#### <a name="configuration"></a>Configuración

El archivo de configuración para el proveedor de documentos fiscales se encuentra en **src\\FiscalIntegration\\Efr\\Configurations\\DocumentProviders\\DocumentProviderFiscalEFRSampleGermany.xml** en el repositorio de [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). El propósito del archivo es permitir que la configuración del proveedor de documentos fiscales se configure desde la sede de Comercio. El formato de archivo está alineado con los requisitos para la configuración de integración fiscal.

### <a name="hardware-station-extension-design"></a>Diseño de extensiones de la estación de hardware

El propósito de la extensión que es un conector fiscal es comunicarse con el servicio de registro fiscal.

La extensión de la estación de hardware es **HardwareStation.Extension.EFRSample**. Usa el protocolo HTTP para enviar documentos que la extensión CRT genera en el servicio de registro fiscal. También maneja las respuestas que se reciben del servicio de registro fiscal.

#### <a name="request-handler"></a>Manejador de solicitudes

El manejador de solicitudes **EFRHandler** es el punto de entrada para manejar las solicitudes al servicio de registro fiscal. Este controlador se hereda de la interfaz **INamedRequestHandler**. El método **HandlerName** es responsable de devolver el nombre del controlador. El nombre del controlador debe coincidir con el nombre del conector fiscal que se especifica en la sede de Commerce.

El conector admite las siguientes solicitudes:

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
