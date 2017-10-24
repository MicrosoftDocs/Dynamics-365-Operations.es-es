---
title: "Facturas electrónicas (CFDI)"
description: "Este artículo proporciona información acerca de las facturas electrónicas que su organización puede enviar a la autoridad fiscal mexicana (SAT). Describe el método aprobado actualmente para enviar facturas electrónicas (CFDI), los requisitos para usarlas y la información que incluyen."
author: sndray
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EInvoiceCFDIJour_MX, EInvoiceCFDIPACTable_MX, EInvoiceParameters_MX, SalesTable, SalesTablePostings
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 29791
ms.assetid: b6861a2c-c132-48a2-97b5-9cb1020e0512
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7db17961d232724297bee6621b1f2270f2451db3
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="electronic-invoices-cfdi"></a>Facturas electrónicas (CFDI)

[!include[banner](../includes/banner.md)]


Este artículo proporciona información acerca de las facturas electrónicas que su organización puede enviar a la autoridad fiscal mexicana (SAT). Describe el método aprobado actualmente para enviar facturas electrónicas (CFDI), los requisitos para usarlas y la información que incluyen.

Una factura electrónica es un recibo de impuestos digital aceptado legalmente que la organización envía a la autoridad fiscal mexicana (Servicio de Administración Tributaria \[SAT\]). Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition ayuda a garantizar que las facturas electrónicas que su organización genera son seguras, confidenciales, auténticas y legalmente aceptables. También puede asegurarse de que los estándares internacionales se aplican a las facturas electrónicas. Puede generar una factura electrónica para los siguientes documentos al registrar una transacción:

-   Pedido de ventas
-   Factura de servicios
-   Factura rectificativa
-   Pedido de devolución
-   Factura del proyecto
-   Pedido de ventas de proyecto

## <a name="methods-for-generating-electronic-invoices"></a>Métodos para generar facturas electrónicas
Hay dos métodos para generar facturas electrónicas:

-   **Comprobantes fiscales digitales (CFD)**: las facturas electrónicas se generan mediante Finance and Operations. Las facturas luego se comprueban y se certifican mediante un sitio web gubernamental. Por último, su organización envía las facturas al SAT. Aunque este método está obsoleto ahora debido a cambios en la legislación, puede investigar las transacciones CFD que se han generado anteriormente en Finance and Operations.
-   **Comprobantes fiscales digitales por internet (CFDI)**: este es el método actual para generar facturas electrónicas en el formato que el SAT exige. En este método, las facturas son verificadas y certificadas por un proveedor digital de servicios de firma (PAC). Antes de poder usar el método CFDI para generar facturas electrónicas, su organización debe configurar una conexión de servicio web a un PAC autorizado. Para el método CFDI, se envía un mensaje XML desde Finance and Operations al PAC. El PAC valida cada factura, asigna un número de folio y luego incorpora el sello digital que proporcionan las autoridades fiscales de servicio. Después de que el PAC complete el proceso de aprobación, su organización recibe el mensaje XML aprobado y puede enviar la factura al cliente en formato XML o PDF.

> [!NOTE]
>  La integración con el servicio web del PAC no es parte de localización mexicana. Para obtener información sobre cómo personalizar una conexión de servicio web con un PAC, consulte "Personalización de la integración con servicios web de PAC" más adelante en este artículo. 

El ejemplo siguiente muestra el proceso para generar una factura electrónica usando el método CFDI. ![El proceso de factura electrónica para México](./media/about-electronic-invoices-cfdi.jpg "Proceso de generación de facturación electrónica para el método de CFDI")    

### <a name="requirements-for-using-electronic-invoices"></a>Requisitos para el uso de facturas electrónicas

Para usar facturas electrónicas, su organización debe completar las tareas siguientes:

-   Obtenga la autorización del SAT para usar el método CFDI y adquiera el certificado SAT correspondiente para emitir facturas electrónicas.
-   Obtenga un número de Registro Federal de Contribuyentes (RFC), el número de Clave Única de Registro de Población (CURP) y un número de inscripción estatal del SAT.
-   Contrate un servicio web de PAC. Puede encontrar los servicios de PAC autorizados en el sitio web del SAT. Algunos PAC requieren instalar un certificado adicional para habilitar la conexión entre su instancia de Finance and Operations y el servicio web de PAC.
-   Asegúrese de que los archivos PDF y XML cumplen con los requisitos del SAT. Estos archivos se envían a los clientes como archivos adjuntos a un correo electrónico. El archivo XML generado debe basarse en la definición de esquema XML (XSD) que el SAT ha proporcionado. Debe guardar el archivo XML de cada factura electrónica.
-   Se requiere un identificador de registro de impuestos RFC o CURP para la organización y sus clientes. Asegúrese de completar esta información en la configuración relacionada.
-   Instale el certificado del SAT y del servicio de PAC en el servidor y asegúrese de que el usuario del SERVICIO DE RED tiene los permisos adecuados para las claves privadas.
-   Identifique el servicio web de PAC que use. (Haga clic en **Clientes** &gt; **Facturas** &gt; **Factura electrónica** &gt; **Cuentas de PAC**). Puede usar entornos de prueba y de producción si sus servicios de PAC admiten estos tipos de entornos.
-   Habilite la configuración para enviar mensajes de correo electrónico y defina la plantilla de correo electrónico que usar para transmitir archivos XML y PDF. (Haga clic en **Administración de la organización** &gt; **Configuración** &gt; **Parámetros del correo electrónico**).
-   Habilite a la configuración para emitir facturas electrónicas CFDI. (Haga clic en **Clientes** &gt; **Facturas** &gt; **Factura electrónica** &gt; **Parámetros de facturas electrónicas**).
-   Prepare la integración con el servicio web del PAC.

### <a name="information-that-is-included-in-electronic-invoices"></a>Información que se incluye en facturas electrónicas

En una factura electrónica se incluye la información siguiente:

-   Nombre, dirección y números de registro de impuestos de su organización y el cliente.
-   Número de factura, fecha y nombre de la ciudad donde se ha generado la factura.
-   Número de serie del certificado digital, número de autorización y año en el que se autorizó el certificado.
-   Descripción y cantidad de cada artículo que se incluye en la factura.
-   Precio unitario de cada artículo.
-   Importe que se ha retenido para el impuesto sobre la renta (\[ISR\]) y el importe del impuesto sobre el valor añadido (IVA). Para obtener esta información, debe configurar el tipo de impuestos (IVA o ISR) en la página **Configuración de códigos de impuestos** (haga clic en **Impuestos** &gt; **Impuestos indirectos, Impuestos** &gt; **Código de impuestos** &gt; **General** &gt; **Tipo de impuestos**).
-   Importe total de la transacción de la factura.
-   Nombre, número y fecha del documento de aduanas generado para los artículos importados. Esta información solo está disponible en cada formulario de transacciones de factura mencionado anteriormente.
-   Número de registro de la propiedad si la transacción de la factura incluye servicios de leasing. Esta información solo está disponible en cada formulario de transacciones de factura mencionado anteriormente.
-   Marca digital de la organización.
-   En una versión impresa de CFDI, el código de barras bidimensional.

## <a name="customizing-the-integration-pac-web-services"></a>Personalización de los servicios web de integración del PAC
Según se indica en detalle en el documento de ámbito de localización para México, la integración con servicios web de PAC requiere personalización. Este personalización varía en función de los servicios web de PAC contratados.

## <a name="additional-resources"></a>Recursos adicionales

- [Crear y registrar una factura de cliente como factura electrónica mediante el método CFDI.](./tasks/mx-00010-e-invoicing-cfdi.md)
- [Visualizar, enviar por correo electrónico, exportar o imprimir una factura electrónica CFDI ya generada según la solicitud de un cliente.](./tasks/mx-00010-inquire-print-electronic-invoice.md)
- [Cancelación de una factura electrónica CFDI](./tasks/mx-00010-cancel-electronic-invoice.md)



