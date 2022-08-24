---
title: Funcionalidad de caja registradora para Noruega
description: Este artículo proporciona una descripción general de la función de caja registradora que está disponible para Noruega en Microsoft Dynamics 365 Commerce y proporciona pautas para configurar la funcionalidad.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-10-31
ms.openlocfilehash: 42eda805646dbb30b40528254a3137102e3075e4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292746"
---
# <a name="cash-register-functionality-for-norway"></a>Funcionalidad de caja registradora para Noruega

[!include[banner](../includes/banner.md)]

Este artículo proporciona una descripción general de la función de caja registradora que está disponible para Noruega en Dynamics 365 Commerce. También proporciona pautas para configurar la funcionalidad. La funcionalidad consta de las siguientes partes:

- Funciones comunes de punto de venta (POS) que están disponibles para clientes en todos los países o regiones. Los ejemplos incluyen una opción que le permite evitar que se imprima una copia de un recibo más de una vez.
- Funciones específicas de Noruega, como firmas digitales para transacciones de ventas.

## <a name="overview-of-cash-register-functionality-for-norway"></a>Información general sobre la funcionalidad de caja registradora para Noruega

### <a name="common-pos-features"></a>Funciones de PDV comunes

Para obtener información sobre las funciones de POS que están disponibles para los clientes en todos los países o regiones, consulte [Recursos de ayuda para Dynamics 365 Retail](../index.md).

Las siguientes funciones de localización de puntos de venta que se implementaron anteriormente y se pusieron a disposición de los clientes en todos los países o regiones ahora se pueden usar específicamente para Noruega:

- **Imprima campos de texto en un recibo en un tamaño de letra grande.** Puede usar el parámetro **Tamaño de fuente** en el diseñador de formato de recibo para especificar que se debe usar el tamaño de fuente grande para un campo en el formato de recibo. (El tamaño de fuente grande es aproximadamente el doble del tamaño de fuente habitual). Por ejemplo, puede utilizar este parámetro para imprimir el indicador "Copiar" en una copia de un recibo en caracteres grandes.
- **Registre la impresión de copias de recibos en el registro de eventos de auditoría de PDV.** Puede usar el parámetro **Auditoría** en el perfil de funcionalidad de POS para permitir la impresión de copias de recibos y el registro de otros eventos de auditoría de POS. Los eventos de auditoría se registran en la base de datos del canal y en la Sede. Puede ver los eventos de auditoría en la página **Eventos de auditoría**.
- **Evite que se imprima una copia de un recibo más de una vez.** Cuando el parámetro **Auditoría** en el perfil de funcionalidad POS está habilitado, el permiso **Permitir la impresión de copias de recibos** del PDV controla si se pueden imprimir copias de los recibos. También hay una opción que le permite evitar que se imprima una copia de un recibo más de una vez.

Además, se implementó la siguiente función POS para Noruega, pero se puso a disposición de los clientes en todos los países o regiones:

- **Registre eventos adicionales en el registro de eventos de auditoría de POS.** Si el parámetro **Auditoría** del perfil de funcionalidad de PDV está habilitado, los siguientes eventos se registran en el registro de eventos de auditoría de POS:

    - Comprobaciones de precio
    - Anulaciones de impuestos
    - Correcciones a cantidades de línea
    - Borrar transacciones de la base de datos del canal

### <a name="norway-specific-pos-features"></a>Funciones de PDV específicas de Noruega

Las siguientes funciones de POS específicas de Noruega están habilitadas cuando el parámetro **Código ISO** del perfil de funcionalidad de PDV se establece en **No**.

#### <a name="digital-signing-of-sales-transactions"></a>Firma digital de transacciones comerciales

Cada transacción de venta está firmada digitalmente. La firma se crea y registra en el diario de transacciones de POS al mismo tiempo que se finaliza la transacción. La firma también está disponible en el diario que se exporta para fines de auditoría.

Solo se firman transacciones para ventas al contado. A continuación, se muestran algunos ejemplos de transacciones que están excluidas del proceso de firma:

- Prepagos (depósito de cuenta de cliente)
- Pagos anticipados de pedidos de venta (depósito de pedidos de clientes)
- Emitir una tarjeta regalo
- Transacciones que no son de venta (entrada flotante, eliminación de licitación, etc.)

Los datos firmados son una cadena de texto que consta de los siguientes campos de datos. Los campos de datos están separados por punto y coma.

1. Firma previa para el mismo PDV (se usa un cero \[**0**\] para la primera transacción).
2. Fecha de transacción
3. Hora de la transacción
4. Número de transacción secuencial firmado
5. Importe de la transacción con impuestos incluidos
6. Importe de la transacción sin impuestos

El proceso de firma digital utiliza una clave RSA de 1024 bits que tiene una función hash SHA-1 (RSA-SHA1-1024). Para la firma se utiliza un certificado que está instalado en Commerce Scale Unit. El identificador único del certificado (huella) se registra junto con la firma.

La firma se almacena en la base de datos de la tienda y la base de datos de la sede (HQ) junto con los datos de la transacción. Puede ver la firma de transacción junto con los datos de transacciones usados para generarla en la ficha desplegable **Transacciones fiscales** de la página **Transacciones de tienda**.

#### <a name="receipts"></a>Recepciones

Los recibos para Noruega pueden incluir información adicional que se implementó mediante el uso de campos personalizados:

- **Título del recibo** - Puede agregar un campo a un diseño de formato de recibo para identificar el tipo de recibo. Por ejemplo, un recibo de venta incluirá el texto "Recibo de venta".
- **Número secuencial de la transacción firmada** - El número secuencial de una transacción firmada puede aparecer en el recibo para asociar un recibo impreso con una firma digital en la base de datos.
- **Totales de recibos** - Los campos personalizados para los totales de los recibos excluyen los importes que no son ventas de los importes totales de la transacción. Los montos de no ventas incluyen montos para las siguientes operaciones:

    - Prepagos (depósito de cuenta de cliente)
    - Pagos anticipados de pedidos de venta (depósito de pedidos de clientes)
    - Emitir una tarjeta regalo
    - Agregar fondos a una tarjeta regalo

#### <a name="x-and-z-reports"></a>Informes X y Z

La información que se incluye en los informes X y Z se basa en los requisitos noruegos. Por ejemplo, los montos de **Ventas totales en efectivo** incluyen solo los montos de las transacciones de ventas en efectivo y excluyen las operaciones de emisión de tarjetas de regalo y los prepagos. Las ventas totales en efectivo también se enumeran por grupo de artículos y método de pago. Además, los importes acumulativos de **Gran total de ventas** y **Gran rendimiento total** se mantienen e imprimen.

#### <a name="saf-t-cash-register-audit-file"></a>Archivo de auditoría de caja registradora SAF-T

Puede exportar el diario de transacciones de POS en el formato predefinido de caja registradora de archivo de auditoría estándar: impuestos (SAF-T). El archivo de auditoría incluye información sobre la organización, datos maestros relevantes (como grupos de artículos, artículos y códigos de impuestos), datos de transacciones de ventas en efectivo junto con firmas para esas transacciones, datos de eventos no relacionados con ventas y datos de informes de fin de fecha.

El archivo de auditoría se puede exportar para los siguientes escenarios:

- Por tienda
- Todas las tiendas
- Por terminal
- Todos los terminales

También puede enviar un informe de una entidad jurídica en nombre de otra entidad jurídica. En este caso, debe ejecutar la exportación desde la entidad jurídica operativa y especificar la entidad jurídica informante como remitente del informe.

El formato de caja registradora SAF-T se implementa en la sede mediante [informes electrónicos](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md). 

## <a name="setting-up-commerce-for-norway"></a>Configuración de Commerce para Noruega

Esta sección describe la configuración de comercio que es específica y recomendada para Noruega. Para obtener más información, consulte los [recursosde ayuda de Dynamics 365 Retail](../index.md).

Para utilizar la funcionalidad específica de Noruega, debe completar estas tareas:

- Establezca el campo **País o región** en **NOR** (Noruega) en la dirección principal de la entidad jurídica.
- Establezca el campo **Código ISO** en **NO** (Noruega) en el perfil de funcionalidad ISO de cada tienda ubicada en Noruega.

También debe especificar la siguiente configuración para Noruega.

### <a name="set-up-the-legal-entity"></a>Establezca la entidad jurídica

Asegúrese de especificar el nombre de la entidad jurídica. Este nombre se imprimirá en los informes X y Z.

Además, en la ficha desplegable **Información de cuenta bancaria**, en el campo **Número de ruta**, escriba el número de la organización.

### <a name="set-up-value-added-tax-vat-per-norwegian-requirements"></a>Configure el impuesto al valor agregado (IVA) según los requisitos noruegos


Debe crear códigos de impuestos, grupos de impuestos y grupos de impuestos de artículo para los grupos de impuestos de artículos. También debe configurar la información de impuestos sobre las ventas para productos y servicios. Para obtener más información sobre cómo configurar y usar impuestos, consulte [Introducción a los impuestos](../../finance/general-ledger/indirect-taxes-overview.md).

También debe especificar grupos de impuestos sobre las ventas y habilitar la opción **Los precios incluyen impuestos sobre las ventas** para tiendas ubicadas en Noruega.

### <a name="set-up-functionality-profiles"></a>Configuración de perfiles de funcionalidad

Debe habilitar la auditoría y configurar la numeración de recibos.

### <a name="update-pos-permissions-groups-and-individual-permission-settings-for-store-workers"></a>Actualice los grupos de permisos de POS y la configuración de permisos individuales para los trabajadores de la tienda

Establezca el permiso **Permitir impresión de copia de recibo** en un valor apropiado:

- **Permitir siempre** - El operador puede imprimir una copia de un recibo varias veces.
- **Permitir solo una vez** - El operador puede imprimir una copia de un recibo una sola vez.
- **Permitir solo una vez, y solo si HQ DB está disponible** - El operador puede imprimir una copia de un recibo solo una vez, y solo si la base de datos de la sede está disponible a través de Commerce Data Exchange: servicio en tiempo real, para que el sistema pueda verificar que no se han impreso copias del recibo previamente en ninguna tienda.
- **Nunca** - El operador no puede imprimir una copia de un recibo varias veces.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Configure campos personalizados para que se puedan usar en formatos de recibo para recibos de ventas

Sobre la página **Texto de idioma**, agregue los siguientes registros para las etiquetas de los campos personalizados para diseños de recibos. Tenga en cuenta que los valores **ID de idioma**, **ID de texto** y **Texto** que se muestran en la tabla son solo ejemplos. Puede cambiarlos fácilmente para satisfacer sus necesidades.

| Id. del idioma | Texto                   | Id. de texto |
|-------------|------------------------|---------|
| en-US       | Título del recibo          | 900011  |
| en-US       | Es una tarjeta regalo           | 900012  |
| en-US       | Total (ventas)          | 900013  |
| en-US       | Impuesto total (ventas)      | 900014  |
| en-US       | Total con impuesto (ventas) | 900015  |
| en-US       | Importe de impuestos (ventas)     | 900016  |
| en-US       | Id. de transacción en efectivo    | 900017  |

Sobre la página **Campos personalizados**, agregue los siguientes registros para los campos personalizados para diseños de recibos. Tenga en cuenta que los valores **ID de texto de subtítulo** deben corresponder a los valores de **ID de texto** que especificó en la página **Texto de idioma**.

| Name                            | Tipo    | Id. de texto de leyenda |
|---------------------------------|---------|-----------------|
| ReceiptTitle                    | Recepción | 900011          |
| IsGiftCard                      | Recepción | 900012          |
| SalesTotalExt                   | Recepción | 900013          |
| TaxTotalExt                     | Recepción | 900014          |
| TotalWithTaxExt                 | Recepción | 900015          |
| AmountPerTaxExt                 | Recepción | 900016          |
| CashTransactionSequentialNumber | Recepción | 900017          |

> [!NOTE]
> Es importante que especifique los nombres de campo personalizados correctos, como se indica en la tabla anterior. Un nombre de campo personalizado incorrecto hará que falten datos en los recibos.

### <a name="configure-receipt-formats"></a>Configurar formatos de recibo

Para todos los formatos de recibo requerido, cambie el valor del campo **Comportamiento de impresión** a **Imprimir siempre** para el formato de recibo.

En el diseñador de formato de recibo, agregue los siguientes campos personalizados a las secciones de recibos correspondientes. Tenga en cuenta que los nombres de los campos corresponden a los textos de idioma que definió en la sección anterior.

1. Encabezado:

    - **Título del recibo** - Este campo identifica el tipo de recibo.
    - **ID de transacción en efectivo** - Este campo imprime el número secuencial de la transacción en efectivo firmada.

2. Líneas:

    - **Es tarjeta de regalo** - Este campo marca la línea del recibo como relacionada con la operación Emitir tarjeta de regalo o Agregar a tarjeta de regalo.

3. Pie de página:

    - **Ventas totales**: este campo imprime el monto total de venta en efectivo del recibo. El importe excluye impuestos. Se excluyen las operaciones de prepago y tarjetas regalo.
    - **Ventas totales**: este campo imprime el monto total de impuestos para ventas en efectivo. Se excluyen las operaciones de prepago y tarjetas regalo.
    - **Total con impuestos (ventas)**: este campo imprime el monto total de venta en efectivo del recibo. El importe incluye impuestos. Se excluyen las operaciones de prepago y tarjetas regalo.
    - **Importe de impuestos (ventas)**: este campo imprime el monto total de impuestos para ventas en efectivo por código de impuesto. Se excluyen las operaciones de prepago y tarjetas regalo.

Para obtener más información sobre cómo trabajar con formatos de recibo, consulte [Configurar y diseñar formatos de recibos](../receipt-templates-printing.md).

### <a name="configure-the-saf-t-cash-register-export-format"></a>Configurar el formato de exportación de la caja registradora SAF-T

La configuración de la caja registradora SAF-T está disponible para descargar desde Microsoft Dynamics Lifecycle Services (LCS). Para obtener más información, consulte [Importar configuraciones de informes electrónicos](../../fin-ops-core/dev-itpro/analytics/electronic-reporting-import-ger-configurations.md). Debe descargar las siguientes configuraciones:

- **Datos del canal minorista versión.1** - La configuración del modelo de datos.
- **Datos del canal minorista DMM versión.1.14** - La configuración de asignación del modelo de datos.
- **NO SAF T Caja registradora versión.1.20** - La configuración del formato.

Después de importar las configuraciones, en la página **Parámetros de comercio**, en la pestaña **Documentos electronicos**, en el campo **Formato de exportación de caja registradora SAF-T**, seleccione el nombre de la configuración de formato que se importó.

También debe asignar los datos maestros requeridos a códigos estándar SAF-T predefinidos. Para obtener más información, consulte la documentación de la caja registradora SAF-T proporcionada por la Administración Tributaria de Noruega. Para crear el mapeo, debe configurar el nuevo campo **Código de caja registradora SAF-T** en las siguientes páginas:

- Grupos de artículos
- Métodos de pago
- Códigos de impuestos

### <a name="configure-channel-components"></a>Configurar los componentes de canal

Para habilitar la funcionalidad específica de Noruega, debe configurar los componentes del canal. Para obtener más información, consulte las [directrices de implementación](emea-nor-fi-deployment.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
