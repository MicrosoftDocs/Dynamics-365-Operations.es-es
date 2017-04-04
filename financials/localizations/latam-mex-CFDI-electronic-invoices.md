---
title: "Facturas electrónicas (CFDI)"
description: "Este artículo proporciona información acerca de las facturas electrónicas que su organización puede enviar a la autoridad fiscal mexicana (SAT). Describe el método aprobado actualmente para enviar facturas electrónicas (CFDI), los requisitos para usarlas y la información que incluyen."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EInvoiceCFDIJour_MX, EInvoiceCFDIPACTable_MX, EInvoiceParameters_MX, SalesTable, SalesTablePostings
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 29791
ms.assetid: b6861a2c-c132-48a2-97b5-9cb1020e0512
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: d8b556ba651364e60aad734bffb3b98ebab112ea
ms.lasthandoff: 03/31/2017


---

# <a name="electronic-invoices-cfdi"></a>Facturas electrónicas (CFDI)

Este artículo proporciona información acerca de las facturas electrónicas que su organización puede enviar a la autoridad fiscal mexicana (SAT). Describe el método aprobado actualmente para enviar facturas electrónicas (CFDI), los requisitos para usarlas y la información que incluyen.

Una factura electrónica es un recibo de impuestos digital con validez legal que su organización envía a la autoridad fiscal mexicana (Servicio de Administración Tributaria \[\]SAT). El Microsoft Dynamics 365 para ayuda de las operaciones garantiza que las facturas electrónicas que genera la organización son seguras confidenciales, y auténticas legalmente aceptables. También puede asegurarse de que los estándares internacionales se aplican a las facturas electrónicas. Puede generar una factura electrónica para los siguientes documentos al registrar una transacción:

-   Pedido de ventas
-   Factura de servicios
-   Factura rectificativa
-   Pedido de devolución
-   Factura del proyecto
-   Pedido de ventas de proyecto

## <a name="methods-for-generating-electronic-invoices"></a>Métodos para generar facturas electrónicas
Hay dos métodos para generar facturas electrónicas:

-   ** Las digitales (CFD) de los Comprobantes fiscales de ** – las facturas electrónicas se generan mediante Dynamics 365 para las operaciones. Las facturas luego se comprueban y se certifican mediante un sitio web gubernamental. Finalmente, su organización envíe facturas al SAT. Aunque este método es ahora obsoleto debido a los cambios en la legislación, puede investigar sobre transacciones de CFD generadas previamente en Dynamics 365 para las operaciones.
-   ** Por Internet del de las digitales de los Comprobantes fiscales de CFDI () – ** es el método actual para generar facturas electrónicas en el formato que requiere el SAT. En este método, las facturas se comprobar y certificadas por un proveedor de servicios de la firma digital PAC (). Antes de poder usar el método CFDI para generar facturas electrónicas, su organización debe configurar una conexión de servicio web a un PAC autorizado. Para el método de CFDI, se envía un mensaje de XML de Dynamics 365 para las operaciones al PAC. El PAC valida cada factura, asigna un número de folio y luego incorpora el sello digital que proporcionan las autoridades fiscales de servicio. Después de que el PAC complete el proceso de aprobación, su organización recibe el mensaje XML aprobado y puede enviar la factura al cliente en formato XML o PDF.

> [!NOTE]
>  La integración con el servicio web de PAC no es parte de localización mexicana. Para obtener información sobre cómo personalizar una conexión de servicio web con un PAC, consulte "Personalización de la integración con servicios web de PAC" más adelante en este artículo. El ejemplo siguiente muestra el proceso para generar una factura electrónica usando el método CFDI. ![el proceso de la factura para México](./media/about-electronic-invoices-cfdi.jpg)    

### <a name="requirements-for-using-electronic-invoices"></a>Requisitos para el uso de facturas electrónicas

Para usar facturas electrónicas, su organización debe completar las tareas siguientes:

-   Obtenga la autorización del SAT para usar el método CFDI y adquiera el certificado SAT correspondiente para emitir facturas electrónicas.
-   Obtenga un número de Registro Federal de Contribuyentes (RFC), el número de Clave Única de Registro de Población (CURP) y un número de inscripción estatal del SAT.
-   Contrate un servicio web de PAC. Puede encontrar los servicios de PAC autorizados en el sitio web del SAT. Algunos PACs requieren instalar un certificado adicional para habilitar la conexión entre la instancia de Dynamics 365 para Operationsand el servicio web de PAC.
-   Asegúrese de que los archivos PDF y XML cumplen con los requisitos del SAT. Estos archivos se envían a los clientes como archivos adjuntos a un correo electrónico. El archivo XML generado debe basarse en la definición de esquema XML (XSD) que el SAT ha proporcionado. Debe guardar el archivo XML de cada factura electrónica.
-   Se requiere un identificador de registro de impuestos RFC o CURP para la organización y sus clientes. Asegúrese de completar esta información en la configuración relacionada.
-   Instale el certificado del SAT y del servicio de PAC en el servidor y asegúrese de que el usuario del SERVICIO DE RED tiene los permisos adecuados para las claves privadas.
-   Identifique el servicio web de PAC que use. Haga clic en (** clientes ** &gt; ** facturas ** &gt; ** E- factura ** &gt; ** el PAC considera **). Puede usar la prueba y los entornos de producción si de servicios de PAC tienen en cuenta estos tipos de entornos.
-   Habilite la configuración para enviar mensajes de correo electrónico y defina la plantilla de correo electrónico que usar para transmitir archivos XML y PDF. ** (Haga clic en Administración de organización ** &gt; ** configuración ** &gt; ** parámetros de correo electrónico **).
-   Habilite a la configuración para emitir facturas electrónicas CFDI. Haga clic en (** clientes ** &gt; ** facturas ** &gt; ** E- factura ** &gt; ** parámetros de factura electrónica **).
-   Prepare la integración con el servicio web del PAC.

### <a name="information-that-is-included-in-electronic-invoices"></a>Información que se incluye en facturas electrónicas

En una factura electrónica se incluye la información siguiente:

-   Nombre, dirección y números de registro de impuestos de su organización y el cliente.
-   Número de factura, fecha y nombre de la ciudad donde se ha generado la factura.
-   Número de serie del certificado digital, número de autorización y año en el que se autorizó el certificado.
-   Descripción y cantidad de cada artículo que se incluye en la factura.
-   Precio unitario de cada artículo.
-   El importe que se ha retenido para el impuesto sobre la renta (ISR Impuesto \[\]sobre la renta acerca de Impuesto) y el impuesto sobre el valor añadido (VAT). Para obtener esta información, debe configurar el tipo de impuestos IVA (ISR) o en ** configuración del código de impuestos ** la página (Tax clic ** ** &gt; ** los impuestos indirectos, impuestos ** &gt; ** código de impuestos ** &gt; ** general ** &gt; ** Tax escrito **).
-   Importe total de la transacción de la factura.
-   Nombre, número y fecha del documento de aduanas generado para los artículos importados. Esta información solo está disponible en cada formulario de transacciones de factura mencionado anteriormente.
-   Número de registro de la propiedad si la transacción de la factura incluye servicios de leasing. Esta información solo está disponible en cada formulario de transacciones de factura mencionado anteriormente.
-   Marca digital de la organización.
-   En una versión impresa de CFDI, el código de barras bidimensional.

## <a name="customizing-the-integration-pac-web-services"></a>Personalización de los servicios web de integración del PAC
Según se indica en detalle en el documento de ámbito de localización para México, la integración con servicios web de PAC requiere personalización. Este personalización varía en función de los servicios web de PAC contratados.


