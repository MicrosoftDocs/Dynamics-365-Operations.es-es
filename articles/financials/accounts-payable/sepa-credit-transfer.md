---
title: "Visión general de transferencias de crédito SEPA"
description: "Este artículo proporciona información general acerca las transferencias de crédito ISO 20022, que incluyen las transferencias de crédito de la Zona Única de Pagos en Euros (SEPA) y cualquier otro pago electrónico para proveedores. La transferencia de crédito SEPA es un tipo específico de pago (en euros) de una empresa o un individuo a otra empresa o individuo. El tema también explica cómo configurar y transmitir un archivo de pago de transferencia de crédito."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendInvoice, LedgerJournalTransVendPaym, VendPaymMode
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 11124
ms.assetid: 36b0f870-16d4-4bbb-8da5-e747e69b970d
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 1aa70dea3b0e7056afbdba96f4475c3e7e71f57c
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="sepa-credit-transfer-overview"></a>Visión general de transferencias de crédito SEPA

[!include [banner](../includes/banner.md)]

Este artículo proporciona información general acerca las transferencias de crédito ISO 20022, que incluyen las transferencias de crédito de la Zona Única de Pagos en Euros (SEPA) y cualquier otro pago electrónico para proveedores. La transferencia de crédito SEPA es un tipo específico de pago (en euros) de una empresa o un individuo a otra empresa o individuo. El tema también explica cómo configurar y transmitir un archivo de pago de transferencia de crédito.

## <a name="what-is-a-credit-transfer-message"></a>¿Qué es un mensaje de transferencia de crédito?
El mensaje de transferencia de crédito es una solicitud que la parte que inicia (la empresa) envía para mover fondos de su propia cuenta a un acreedor. Hay muchas implementaciones específicas del país/región y del banco de los mensajes de transferencia de crédito. Algunos de ellas se utilizan dentro de un país o región, y algunas se están convirtiendo en estándares. El estándar global ISO 20022 y sus mensajes de inicio, como la transferencia de crédito, están bien establecidos. La ilustración siguiente muestra las relaciones y el alcance de los mensajes seleccionados de transferencia de crédito. 
![Transferencia de crédito](./media/credit-transfer.jpg) Mensajes de transferencia de crédito 

## <a name="what-are-iso-20022-and-sepa-payments"></a>¿Qué son los pagos ISO 20022 y SEPA?
La Zona única de Pagos en Euros (SEPA) lo establece la Comisión Europea y dicta que todos los pagos electrónicos se consideran como nacionales, independientemente del país o región donde se encuentren el individuo, la empresa o la organización y el banco. No hay diferencia entre los pagos nacionales y transfronterizos. SEPA incluye a los 28 estados miembros de la Unión Europea (UE), además de Islandia, Liechtenstein, Noruega, Suiza, Mónaco y San Marino. SEPA ayuda a formar un mercado único para las transacciones de pago en el Área Económica Europea (AEE). En última instancia, se espera que SEPA reduzca el número de formatos de pago con los que deben trabajar los bancos, las empresas y las personas. La Comisión Europea estableció la base jurídica para pagos SEPA a través de la Directiva sobre servicios de pago (PSD). El Consejo de Pagos Europeo (EPC) admite SEPA con las siguientes actividades:

-   Establece los estándares para pagos electrónicos SEPA mediante el formato XML de esquema de mensajes del sector financiero universal ISO 20022.
-   Establece reglas y directrices sobre la gestión de los pagos en euros.

El EPC, que consta de bancos europeos, desarrolla marcos técnicos y comerciales para los instrumentos de pago SEPA. Se usan tres tipos de pagos SEPA:

-   Transferencias de crédito
-   Domiciliaciones bancarias
-   Tarjetas

## <a name="what-is-a-sepa-credit-transfer"></a>¿Qué es una transferencia de crédito SEPA?
La transferencia de crédito SEPA es un pago de una empresa o un individuo a otra empresa o individuo. Los pagos deben realizarse en euros y deben incluir el número internacional de cuenta bancaria (IBAN) y el código identificador del banco (BIC) para ambas partes. (El Bic también se conoce como el código Society for Worldwide Interbank Financial Telecommunication \[SWIFT\]). Además, los costes de transacción se deben compartir entre las dos partes. Las transferencias de crédito que se producen entre partes deben usar archivos XML que cumplen los estándares de procesamiento de pago ISO 20022 y el formato XML, según lo especificado por el EPC.

## <a name="how-is-a-credit-transfer-implemented"></a>¿Cómo se implementa una transferencia de crédito?
El formato de pago de transferencia de crédito de los países europeos se implementa mediante la funcionalidad Informes electrónicos (ER) y Formas de pago en Microsoft Dynamics 365 for Finance and Operations. Algunos formatos de transferencia de crédito que se usan en otras regiones siguen utilizando el antiguo marco de pago. Entre otros muchos formatos, hay doce formatos de archivo de transferencia de crédito ISO 20022 disponibles. Estos formatos de exportación se adaptan al estándar de SEPA XML ISO 20022. Se utilizan para generar las transferencias de pago que no son en Euros para los países o las regiones donde se usan y los pagos en Euros como se especifica en la versión 8.2 del reglamento del esquema de transferencia de crédito SEPA que EPC emite. Para poder implementar las transferencias de crédito, debe ponerse en contacto con su banco para obtener el software que se requiere para cargar archivos de banca electrónica. Usará ese software para transferir archivos XML que contienen pedidos de pagos al banco.

## <a name="what-credit-transfer-formats-are-currently-supported-in-finance-and-operations"></a>¿Qué formatos de transferencia de crédito se admiten actualmente en Finance and Operations?
Debe ir siempre a la biblioteca de activos compartidos de Microsoft Dynamics Lifecycle Services (LCS) y ver la lista más actualizada de archivos disponibles que tienen un tipo de activo de **configuración de GER**. La siguiente sección, “¿Qué tengo que configurar? ”, proporciona un vínculo al tema que explica cómo crear un repositorio de LCS para revisar las configuraciones disponibles e importar las configuraciones seleccionadas.

## <a name="what-do-i-have-to-set-up"></a>¿Qué tengo que configurar?
-   Para poder crear archivos de transferencia de crédito, se debe importar al menos una configuración de transferencia de crédito activa a las configuraciones de ER. Para obtener más información, consulte [Descargar configuraciones de informes electrónicos de Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).
-   Al configurar los métodos de pago Proveedores, seleccione la casilla **Informes electrónicos genéricos** y seleccione el formato de transferencia de crédito adecuado (por ejemplo, **Transferencia de crédito (AT) ISO 20022**) como configuración del formato de exportación.
-   También debe configurar la entidad jurídica y la información de cuenta bancaria en Finance and Operations.
-   Los números de cuenta bancaria, IBAN, y a veces los códigos SWIFT (BIC) u otros id. se requieren para efectuar pagos de transferencia de crédito válidos. Por lo tanto, debe configurarlos para la cuenta bancaria del proveedor y la cuenta bancaria de la organización que está solicitando la transferencia.
-   Se puede requerir información adicional, por ejemplo, los números de impuesto sobre el valor añadido (IVA) de las partes a las que se hace referencia en el mensaje de transferencia de crédito. Esta información se debe configurar para los proveedores y para la entidad jurídica cuando se solicita.
-   Algunas formas de pago de los proveedores, principalmente las formas de pago basadas en ISO 20022, pueden requerir una configuración adicional para **conjuntos de códigos de formato de pago**; por ejemplo **Tipo de servicio** = **SLEV**. Estos códigos se usan como etiquetado adicional para las transacciones de pago durante el procesamiento de pagos. Los valores predeterminados de los códigos de pago, como **Propósito de la categoría**, **Portador del cargo**, **Instrumento local** y **Nivel de servicio** se pueden establecer en dos ubicaciones. El primer lugar es **Encabezado del diario de pago de los proveedores** y el segundo es **Métodos de los proveedores para los pagos**. Al crear las líneas de diario de pago, los valores de código de pago establecidos en el encabezado del diario de pagos se transfieren a una línea de diario, si no se establecen, se usan los valores de formas de pago.

## <a name="what-parameters-are-available-for-generating-credit-transfer-payments"></a>¿Qué parámetros están disponibles para generar los pagos de transferencia de crédito?
La lista de parámetros específicos depende del formato de transferencia de crédito. En la tabla siguiente se muestran los parámetros que están disponibles al generar un archivo de pago de transferencia de crédito ISO 20022 para Alemania en un diario de pago del proveedor. Al usar las opciones disponibles en la pestaña **Ejecutar en segundo plano**, puede ejecutar la generación del pago en el modo de lotes.

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
<li><strong>Con estructura</strong>: seleccione esta opción para usar el formato estructurado cuando una línea de pago se liquida con una factura. Esta opción no está disponible para los formatos de exportación específicos de país o región para Francia, Alemania o Países Bajos.</li>
<li><strong>Sin estructura</strong>: seleccione esta opción para usar el formato sin estructura cuando el pago se liquida con varias facturas. Los números de factura para las facturas liquidadas se concatenan y se usan como información de remesa. De acuerdo con las directrices de ISO 20022, la información de remesa sin estructura se limita a 140 caracteres.</li>
</ul></td>
</tr>
<tr class="even">
<td>Número de facturas</td>
<td>Especifique el número de facturas desde el que se imprime el informe de <strong>aviso de pago</strong>.</td>
</tr>
<tr class="odd">
<td>Número de secuencia</td>
<td>Especifique un número de serie para identificar el archivo. El número de serie se muestra en el informe <strong>Nota adjunta</strong>.</td>
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
El número internacional de cuenta bancaria (IBAN) y el código de identificador del banco (BIC) se usan para identificar las cuentas en muchos países o regiones del mundo. Se incluyen los 34 países/regiones de SEPA. Especifique el BIC en el campo **Código SWIFT** y el IBAN en el campo **IBAN**. Para la cuenta bancaria del acreedor y la cuenta bancaria del cliente, estos campos se encuentran en la ficha desplegable **Identificación adicional** de la pestaña **Cuenta bancaria** de la página **Cuentas bancarias**. El uso de BIC para pagos de SEPA ya no se aplica.

## <a name="how-do-i-transmit-a-payment-file-to-the-bank"></a>¿Cómo transmito un archivo de pago al banco?
Al generar pagos, se genera el archivo de pago y se le pedirá que lo guarde desde el explorador web en cualquier ubicación disponible. El siguiente paso es enviar el archivo XML al banco. Este proceso varía de banco a banco. Siga las instrucciones de su banco para enviar los archivos al banco para procesamiento.




