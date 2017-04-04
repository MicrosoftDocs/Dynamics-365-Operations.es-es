---
title: "Visión general de transferencias de crédito SEPA"
description: "Este artículo proporciona información general acerca ISO 20022 transferencias de crédito, que incluyen las transferencias de crédito (SEPA) de la Zona Única de Pagos en Euros y cualquier otro pago electrónico para proveedores. Una transferencia de crédito SEPA es un tipo específico de pago en euros a partir de un empresa o persona a otra empresa o persona. El tema también se explica cómo configurar y transmitir un archivo de pago de transferencia de crédito."
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTransVendInvoice, LedgerJournalTransVendPaym, VendPaymMode
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 11124
ms.assetid: 36b0f870-16d4-4bbb-8da5-e747e69b970d
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 848df5e3898f37284d7746c59bff8b38d35ac883
ms.lasthandoff: 03/31/2017


---

# <a name="sepa-credit-transfer-overview"></a>Visión general de transferencias de crédito SEPA

Este artículo proporciona información general acerca ISO 20022 transferencias de crédito, que incluyen las transferencias de crédito (SEPA) de la Zona Única de Pagos en Euros y cualquier otro pago electrónico para proveedores. Una transferencia de crédito SEPA es un tipo específico de pago en euros a partir de un empresa o persona a otra empresa o persona. El tema también se explica cómo configurar y transmitir un archivo de pago de transferencia de crédito.

## <a name="what-is-a-credit-transfer-message"></a>¿Qué es un mensaje de transferencia de crédito?
El mensaje de transferencia de crédito es una solicitud que una parte que inicia (la empresa) envía a los fondos de movimiento de su propia cuenta a un acreedor. Hay muchas implementaciones específicas del país/región específicas y negocios de los mensajes de transferencia de crédito. Algunos de ellos se utilizan dentro de un país o región, y algunas son normas que se convierten. Estándar global liquidará ISO es 20022 y los mensajes de liberación, como transferencia de crédito. La ilustración siguiente muestra las relaciones y el alcance de los mensajes seleccionado de transferencia de crédito. 
mensajes\[/caption\]de transferencia de crédito](./media/credit-transfer.jpg) del tansfer de crédito![ 

## <a name="what-are-iso-20022-and-sepa-payments"></a>¿Cuáles son pagos de ISO 20022 y de SEPA?
La Zona única de Pagos en Euros (SEPA) lo establece la Comisión Europea y dicta que todos los pagos electrónicos se consideran como nacionales, independientemente del país o región donde se encuentren el individuo, la empresa o la organización y el banco. No existe ninguna diferencia entre los pagos nacionales y los pagos fronterizos. El SEPA 28 incluye los estados miembros de la Unión Europea (EU), y también Islandia, Liechtenstein, Noruega, Suiza, y, Mónaco San Marino. SEPA ayuda a formar un mercado único para las transacciones de pago en el Área Económica Europea (AEE). En última instancia, se espera que SEPA reduzca el número de formatos de pago con los que deben trabajar los bancos, las empresas y las personas. La Comisión Europea estableció la base jurídica para pagos SEPA a través de la Directiva sobre servicios de pago (PSD). El Consejo de Pagos Europeo (EPC) admite SEPA con las siguientes actividades:

-   Establece los estándares para pagos electrónicos SEPA mediante el formato XML de esquema de mensajes del sector financiero universal ISO 20022.
-   Establece reglas y directrices sobre la gestión de los pagos en euros.

El EPC, que consta de bancos europeos, desarrolla marcos técnicos y comerciales para los instrumentos de pago SEPA. Se usan tres tipos de pagos SEPA:

-   Transferencias de crédito
-   Domiciliaciones bancarias
-   Tarjetas

## <a name="what-is-a-sepa-credit-transfer"></a>¿Qué es una transferencia de crédito SEPA?
La transferencia de crédito SEPA es un pago de una empresa o un individuo a otra empresa o individuo. Los pagos deben realizarse en euros y deben incluir el número internacional de cuenta bancaria (IBAN) y el código identificador del banco (BIC) para ambas partes. (El Bic también se conoce como la Sociedad para el código SWIFT \[\] de las Comunicaciones Financieras Interbancarias Internacionales). Además, los costes de transacción se deben compartir entre dos partes. Las transferencias de crédito que se producen entre partes deben usar archivos XML que cumplen los estándares de procesamiento de pago ISO 20022 y el formato XML, según lo especificado por el EPC.

## <a name="how-is-a-credit-transfer-implemented"></a>¿Cómo se implementa una transferencia de crédito?
El formato de pago de transferencia de crédito para países europeos se implementa y (ER) mediante la funcionalidad electrónicos de formas de pago que informen de Dynamics 365 para las operaciones. Algunos formatos de transferencia de crédito que todavía se usan en otras regiones utilizan el antiguo marco de pago. Especifique otros muchos formatos, hay doce ISO 20022 formatos de archivo de transferencia de crédito disponibles. Estos formatos de exportación se adaptan a estándar de SEPA XML ISO 20022. Se utilizan para generar las transferencias de pago de fuera del Euro para los países o las regiones donde se usan y los pagos Euro como se especifica en la versión 8.2 de reglamento del esquema de transferencia de crédito SEPA EPC que libera. Antes de implementar las transferencias de crédito, debe ponerse en contacto con su banco para obtener el software necesario para cargar archivos de banca electrónica. Use el software para transferir archivos XML que contienen pedidos de pago al banco.

## <a name="what-credit-transfer-formats-are-currently-supported-in-dynamics-365-for-operations"></a>¿Qué transferencia de crédito da formato se admite actualmente en Dynamics 365 para las operaciones?
Debe ir a la biblioteca compartida activas de los servicios (LCS) del ciclo de vida de Microsoft Dynamics y ver siempre la lista más actualizada de archivos disponible de los que tiene un tipo de activo ** configuración de GER **. ¿La siguiente sección, “qué que tengo configurar? ”, proporciona un vínculo al tema que se explica cómo crear un repositorio de CD para revisar las configuraciones disponibles y las configuraciones seleccionadas importación.

## <a name="what-do-i-have-to-set-up"></a>¿Qué tengo que configurar?
-   Para poder crear archivos de transferencia de crédito, al menos una configuración activa de transferencia de crédito se debe importar en la configuración del ER. Para obtener instrucciones, consulte [las configuraciones electrónicas de informes de la descarga de servicios] del ciclo de vida (https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).
-   Cuando configure las formas de pago de proveedores, seleccione ** informe de errores electrónico genérico ** la casilla, y seleccione el formato apropiado de transferencia de crédito (por ejemplo, ** transferencia de crédito de 20022 (ISO) EN **) como configuración del formato de exportación.
-   También debe configurar la entidad jurídica y la información de cuentas bancarias en Dynamics 365 para las operaciones.
-   Los números de cuenta bancaria, IBANs, y a veces los códigos SWIFT (BICs) u otros id. se requieren para efectuar pagos de transferencia de crédito válidos. Por lo tanto, debe configurarlos para la cuenta bancaria del proveedor y el banco para la organización a la que está solicitando la transferencia.
-   La información adicional se puede requerir por ejemplo, los números de (VAT) el impuesto sobre el valor añadido para las partes que se hace referencia en el mensaje de transferencia de crédito. Esta información se debe configurar para los proveedores y para la entidad jurídica cuando ha solicitado.
-   Algunas formas de pago de los proveedores, principalmente ISO 20022 según las formas de pago, puede requerir la configuración adicional para ** los códigos de formato de pago **, por ejemplo ** tipo de servicio ** = ** SLEV **. Estos códigos se usan como etiquetado adicional para las transacciones de pago durante el procesamiento de pagos. Los valores predeterminados de los códigos de pago, como ** propósito de la categoría, ** ** de transportista de gasto, ** ** instrumento local ** y ** nivel de servicio ** se pueden liquidar en dos ubicaciones. El primer lugar es ** encabezado del diario de pago de los proveedores ** y el segundo es ** los métodos de los proveedores para los pagos **. Acerca de las líneas de diario de pago creación, los valores de código de pago establecidos en encabezado del diario de pagos se transfieren a una línea de diario, si no liquidadas, los valores de formas de pago se usan.

## <a name="what-parameters-are-available-for-generating-credit-transfer-payments"></a>¿Qué parámetros están disponibles para generar pagos de transferencia de crédito?
La lista de parámetros específicos depende del formato de transferencia de crédito. En la tabla siguiente se muestran los parámetros que están disponibles cuando se genera un archivo de pago de transferencia de crédito ISO 20022 para Alemania en un diario de pago. Mediante las opciones disponibles en ** ejecución en segundo plano ** la ficha, puede ejecutar la generación de pago en modo de lotes.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Campo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Reserva por lotes</td>
<td>Active esta casilla para incluir la etiqueta de reserva por lotes en el archivo XML.</td>
</tr>
<tr class="even">
<td>Fecha de procesamiento</td>
<td>Especifique la fecha en la que el banco debe procesar los pagos.</td>
</tr>
<tr class="odd">
<td>Formato</td>
<td>Seleccione el formato para información de remesa, en función de los requisitos de su país o región o banco:
<ul>
<li><strong>Strd</strong> – Seleccione esta opción para usar el formato estructurado cuando una línea de pago se liquida con la factura. Esta opción no está disponible para los formatos de exportación específicas del país/región para Francia, Alemania, o los Países Bajos.</li>
<li><strong>Sin estructura</strong>: seleccione esta opción para usar el formato sin estructura cuando el pago se liquida con varias facturas. Los números de factura para las facturas liquidadas se concatenan y se usan como información de remesa. De acuerdo con ISO informes 20022, información no estructurada de la remesa se limitan a 140 caracteres.</li>
</ul></td>
</tr>
<tr class="even">
<td>Número de facturas</td>
<td>Especifique el número de facturas de las <strong>Aviso de pago</strong> que el informe se imprime.</td>
</tr>
<tr class="odd">
<td>Número de secuencia</td>
<td>Especifique un número de serie para identificar el archivo. El número de secuencia aparece en <strong>Asistencia de la nota</strong> el informe.</td>
</tr>
<tr class="even">
<td>Imprimir nota adjunta</td>
<td>Active esta casilla para imprimir el informe <strong>Nota adjunta</strong>.</td>
</tr>
<tr class="odd">
<td>Imprimir informe de control</td>
<td>Active esta casilla para imprimir un informe que contiene la información de pago.</td>
</tr>
<tr class="even">
<td>Imprimir carta de presentación</td>
<td>Seleccione esta casilla para imprimir el informe <strong>Aviso de pago</strong>.</td>
</tr>
</tbody>
</table>

## <a name="what-are-ibans-and-bics"></a>¿Cuáles son los IBAN y los BIC?
El número internacional de cuenta bancaria (IBAN) y el código (BIC) del identificador del banco se usan para identificar cualquier cuenta en muchos países o regiones de todo el mundo. Estos incluyen los 34 países/regiones de SEPA. Especifique el Bic en ** código SWIFT ** colocan en y IBAN ** IBAN ** el campo. Para ambos la cuenta bancaria acreedor y la cuenta bancaria del cliente, estos campos están ubicadas en ** identificación adicional ** en la ficha desplegable ** cuenta bancaria ** la ficha ** las cuentas bancarias ** de la página. El uso BIC para pagos de SEPA no se aplica más.

## <a name="how-do-i-transmit-a-payment-file-to-the-bank"></a>¿Cómo transmito un archivo de pago al banco?
Al generar pagos, se genera el archivo de pago, y se le guardarlo de su explorador Web a cualquier ubicación disponible. El siguiente paso es enviar el archivo XML al banco. Este proceso varía de banco a banco. Siga las instrucciones de su banco para enviar los archivos al banco para procesamiento.


