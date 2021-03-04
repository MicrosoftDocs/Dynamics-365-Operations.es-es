---
title: Introducción al complemento de facturación electrónica
description: Este tema proporciona información que le ayudará a comenzar con el complemento de facturación electrónica en Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 10/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 7b2a3aae43d42060c7fcd9e1ea3db814fc5d8f22
ms.sourcegitcommit: f860ac2b18f6bbbfc4a46b497baec2477105b116
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2020
ms.locfileid: "4447787"
---
# <a name="get-started-with-the-electronic-invoicing-add-on"></a>Introducción al complemento de facturación electrónica

[!include [banner](../includes/banner.md)]

Este tema proporciona información que le ayudará a comenzar con el complemento de facturación electrónica. Primero, le guía a través de los pasos de configuración en Microsoft Dynamics Lifecycle Services (LCS), Regulatory Configuration Services (RCS) y Dynamics 365 Finance. A continuación, describe el proceso para enviar documentos a través del servicio utilizando Dynamics 365 Finance o Dynamics 365 Supply Chain Management. También aprenderá a interpretar los registros de envío.

## <a name="availability"></a>Disponibilidad

El complemento de facturación electrónica está disponible inicialmente para varios países. El complemento admite la creación de facturas electrónicas y el envío de los siguientes documentos comerciales:

| País o región  | Documento empresarial                          |
|-----------------|--------------------------------------------|
| Austria         | Facturas de ventas y proyectos                 |
| Bélgica         | Facturas de ventas y proyectos                 |
| Brasil          | Modelo de documento fiscal electrónico 55 (NF-e) |
| Dinamarca         | Facturas de ventas y proyectos                 |
| Estonia         | Facturas de ventas y proyectos                 |
| Finlandia         | Facturas de ventas y proyectos                 |
| Francia          | Facturas de ventas y proyectos                 |
| Alemania         | Facturas de ventas y proyectos                 |
| Italia           | Facturas de ventas y proyectos                 |
| México          | Factura CFDI                               |
| Países Bajos     | Facturas de ventas y proyectos                 |
| Noruega          | Facturas de ventas y proyectos                 |
| España           | Facturas de ventas y proyectos                 |
| Europa          | Facturas de ventas y proyectos PEPPOL          |
    
## <a name="licensing"></a>Licencias

Puede utilizar el complemento de facturación electrónica con su licencia actual. No se requieren licencias adicionales para utilizar el servicio.

## <a name="prerequisites"></a>Requisitos previos

Antes de que pueda completar los pasos en este tema, debe tener los siguientes requisitos previos:

- Acceso a su cuenta de LCS.
- Un proyecto de implementación de LCS que incluye Finance o Supply Chain Management versión 10.0.13 o posterior.
- Acceso a su cuenta de RCS.
- Active la función de globalización para su cuenta RCS a través del módulo **Gestión de funciones**. Para más información, consulte [Regulatory Configuration Services (RCS): características de globalización](rcs-globalization-feature.md)
- Cree un recurso de almacén de claves y una cuenta de almacenamiento en Azure. Para más información, vea [Crear cuenta de almacenamiento de Azure y Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).

## <a name="overview"></a>Información general

La siguiente ilustración muestra los cinco pasos principales que completará en este tema.

![Descripción general de los cinco pasos de este tema](media/e-invoicing-services-get-started-overview-5-steps.png)

1. **Configuración de recursos de Azure:** configure Azure Storage y la carga de certificados digitales en Azure Key Vault.
2. **Configuración de LCS:** instale el complemento para microservicios.
3. **Configuración de RCS:** configure el entorno, el acceso de los usuarios y las funciones de facturación electrónica.
4. **Configuración del cliente:** configure la conexión entre el cliente y el complemento de facturación electrónica, y desactive las funciones antiguas para enviar y recibir respuestas para documentos electrónicos.
5. **Enviar facturas:** envíe documentos electrónicos a través del complemento de facturación electrónica y reciba respuestas.

> [!NOTE]
> Algunos pasos de configuración de este tema son comunes y no dependen del país ni de la región. Los pasos y los procedimientos de configuración que son específicos del país o región se describen en los temas específicos del país o región.

## <a name="lcs-setup"></a>Configuración de LCS

1. Inicie sesión en su cuenta de LCS.
2. Seleccione el icono **Gestión de funciones de vista previa**, y en el grupo de campos **Funciones de vista previa pública**, seleccione **BusinessDocumentSubmission**.
3. Marque el campo **Función de vista previa habilitada**.
4. Seleccione el proyecto de implementación de LCS. Antes de que pueda seleccionar el proyecto, debe estar en funcionamiento.
5. En la ficha desplegable **Complementos de entorno**, seleccione **Instalar un nuevo complemento**.
6. Seleccione **Envío de documentos comerciales**.
7. En el cuadro de diálogo **Complemento de configuración**, en el campo **ID de la aplicación AAD**, ingrese **091c98b0-a1c9-4b02-b62c-7753395ccabe**. Este valor es un valor fijo.
8. En el campo **ID de inquilino de AAD**, ingrese el ID de su cuenta de suscripción de Azure.

    ![Cuadro de diálogo Complemento de configuración de LCS](media/e-invoicing-services-get-started-lcs-addin-setup.png)

9. Seleccione la casilla de verificación para aceptar los términos y condiciones.
10. Seleccione **Instalar**.

## <a name="rcs-setup"></a>Configuración de RCS

Durante la configuración de RCS, completará estas tareas:

1. Configure el almacén de claves en RCS.
2. Configure la integración de RCS con el servidor adicional de facturación electrónica.
3. Cree un entorno complementario de facturación electrónica para su organización.

### <a name="set-up-the-key-vault-in-rcs"></a>Configurar el almacén de claves en RCS

1. Inicie sesión en su cuenta de RCS.
2. En el espacio de trabajo **Características de globalización**, en la sección **Entornos**, seleccione el mosaico **Facturación electrónica**.
3. Seleccione **Entornos de servicio**.

    ![Selección de Entornos de servicio](media/e-invoicing-services-get-started-select-service-environments.png)

> [!NOTE]
> La opción **Aplicaciones conectadas** otorga acceso para la configuración automática del complemento de Facturación electrónica en Finance o Supply Management a través de RCS. Sin embargo, actualmente, esta característica aún está en desarrollo.

4. En el panel Acciones, seleccione **Parámetros de Key Vault**.

    ![Selección del parámetro de Key Vault](media/e-invoicing-services-get-started-select-key-vault-parameters.png)

5. En el Panel de acciones, haga clic en **Nuevo** para agregar un nuevo almacén de claves.
6. En el campo **URI de Key Vault**, ingrese el valor del atributo **Nombre DNS** del recurso de almacén de claves que configuró en Azure. Para obtener información sobre dónde encontrar el valor de **Nombre DNS**, vea [Crear cuenta de almacenamiento de Azure y Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).

    ![Campo URI de Key Vault](media/e-invoicing-services-get-started-enter-key-vault-uri.png)

7. En la ficha desplegable **Certificados**, seleccione **Añadir** para ingresar todos los nombres de certificados digitales y los secretos de la bóveda de claves que se necesitan para establecer conexiones confiables. En la columna **Tipo**, puede especificar si es un Certificado o un Secreto. Ambos conjuntos de valores se configuran en el recurso del almacén de claves en Azure.

    ![Agregar certificados](media/e-invoicing-services-get-started-add-digital-certificates.png)

8. Si la factura específica de su país o región requiere una cadena de certificados para aplicar una firma digital, seleccione **Cadena de certificados** en el Panel de acciones y luego ingrese la secuencia de certificados o secretos del almacén de claves que conforman la cadena.

### <a name="set-up-the-rcs-integration-with-the-electronic-invoicing-add-on-server"></a>Configurar la integración de RCS con el servidor adicional de facturación electrónica

1. En el espacio de trabajo **Características de globalización**, en la sección **Configuración relacionada**, seleccione el vínculo **Parámetros de informes electrónicos**.
2. Seleccione **Haga clic aquí para conectarse a Lifecycle Service**. Si no desea conectarse a LCS, seleccione **Cancelar**.
3. En la pestaña **Servicios de facturación electrónica**, en el campo **URI de extremo de servicio**, ingrese el valor según las geografías disponibles: `https://businessdocumentsubmission.us.operations365.dynamics.com/` o `https://businessdocumentsubmission.eu.operations365.dynamics.com/`.
4. En el campo **ID de aplicación**, verifique que muestra el id. **0cdb527f-a8d1-4bf8-9436-b352c68682b2**. Este valor es un valor fijo.
5. En el campo **ID de entorno de LCS**, ingrese el id. de su cuenta de suscripción de LCS.

![Introducción de parámetros complementarios de facturación electrónica](media/e-invoicing-services-get-started-enter-e-invoicing-parameters.png)

### <a name="add-an-electronic-invoicing-add-on-environment"></a>Agregar un entorno del complemento de facturación electrónica

Puede crear diferentes entornos para el complemento de facturación electrónica, como entornos de desarrollo, prueba o producción.

1. En el espacio de trabajo **Características de globalización**, en la sección **Entornos**, seleccione el mosaico **Facturación electrónica**.
2. Seleccione **Nuevo** para crear un entorno.
3. En el campo **Cuenta de token SAS de almacenamiento**, ingrese el nombre del secreto del almacén de claves que configuró en el almacén de claves en RCS.

    ![Campo Cuenta de token SAS de almacenamiento](media/e-invoicing-services-get-started-enter-sas-token-secret.png)

4. En la ficha desplegable **Usuarios**, seleccione **Nuevo** para otorgar acceso a los usuarios para este entorno.

    ![Agregar usuarios del servicio](media/e-invoicing-services-get-started-enter-service-users.png)

5. En el panel de acciones, seleccione **Publicar** para publicar el entorno en el servidor del complemento de facturación electrónica.

    ![Botón Publicar](media/e-invoicing-services-get-started-publish-service-environment.png)

### <a name="e-invoicing-feature-setup"></a>Configuración de características de facturación electrónica

"Característica de facturación electrónica" es el nombre genérico del recurso que se configura y publica para consumir el servidor complementario de facturación electrónica. La configuración de la característica de facturación electrónica combina, entre otras cosas, el uso de formatos de configuración de informes electrónicos (ER) para crear archivos de importación y exportación configurables, y el uso de acciones y flujos de acción para permitir la creación de reglas configurables para enviar solicitudes, importar respuestas y analizar el contenido de la respuesta.

Debido a las variaciones en los formatos de facturas y los flujos de acción, la configuración de la función de facturación electrónica depende del país o región.

## <a name="set-up-electronic-invoicing-add-on-integration-in-finance-or-supply-chain-management"></a>Configurar la integración del complemento de facturación electrónica en Finance o Supply Chain Management 

Durante esta configuración, completará las tareas siguientes:

1. Característica de paquete piloto abierto
2. Active la función de integración del complemento de facturación electrónica para habilitar la integración con Finance.
3. Configure la URL del extremo del complemento facturación electrónica.
4. Importe las configuraciones de ER que están relacionadas con la función de facturación electrónica específica del país o región.
5. Active la función de facturación electrónica específica del país o región correspondiente.
6. Importe las configuraciones de ER y configure los tipos de respuesta necesarios para actualizar el documento de factura específico de su país o región como resultado del proceso de envío.

### <a name="open-flighted-feature"></a>Característica de paquete piloto abierto
La función de integración de factura electrónica se habilita a través de tramos. El paquete piloto es un concepto que permite que una función esté ACTIVADA o DESACTIVADA de forma predeterminada. Los siguientes pasos permiten un paquete piloto en un entorno de no producción. 

1. Ejecute el siguiente comando SQL:

    INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BusinessDocumentSubmissionServiceEnabled', 1)
    
    INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('ElectronicInvoicingServiceIntegrationFeature', 1)
    
2. Después de realizar el cambio anterior, realice un IISReset en todos los AOS

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a>Active la función de integración del complemento de facturación electrónica

1. Inicie sesión en Finance o Supply Chain Management.
2. En el espacio de trabajo **Gestión de funciones**, busque la nueva función, **Integración adicional configurable de facturación electrónica**. Si la función aún no se muestra en la página de gestión de funciones, ejecute la función **Buscar actualizaciones**.
3. Seleccione la característica y, a continuación, seleccione **Habilitar ahora**.

### <a name="set-up-the-service-endpoint-url"></a>Configurar la URL del punto de conexión de servicio

1. Vaya a **Administración de la organización \> Configuración \> Parámetros de documentos electrónicos**.
2. En la pestaña **Servicio de envío**, en el campo **URL de extremo de servicio**, ingrese `https://businessdocumentsubmission.us.operations365.dynamics.com/`.
3. En el campo **Entorno**, ingrese el nombre del entorno del complemento de facturación electrónica que creó durante la configuración de RCS.

![Ingresar parámetros de servicio](media/e-invoicing-services-get-started-enter-service-endpoint.png)

### <a name="import-the-er-configurations"></a>Importar las configuraciones de ER

Para permitir que los datos comerciales se recopilen y envíen al complemento de facturación electrónica, debe importar el modelo de datos de ER y la configuración del modelo de datos de ER que están relacionados con la función de facturación electrónica específica del país o región que desea utilizar.

1. En el espacio de trabajo **Informes electrónicos**, en la sección **Proveedores de configuración**, seleccione el icono **Microsoft**. Asegúrese de que este proveedor de configuración esté establecido en **Activo**. Para obtener más información sobre cómo establecer un proveedor en **Activo**, vea [Crear proveedores de la configuración y marcarlos como activos](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).
3. Seleccione **Repositorios**.
4. Seleccione **Recurso global** y luego seleccione **Abierto**.
5. En el cuadro de diálogo **Conectarse a Lifecycle Services**, seleccione **Haga clic aquí para conectarse a Lifecycle Service**.
6. Según el país o región donde desee utilizar la función de facturación electrónica, debe importar el modelo de datos, la asignación del modelo de datos y los formatos correspondientes. Para obtener información sobre las configuraciones de ER que debe importar, consulte el tema "Introducción al complemento de facturación electrónica" específico del país o región.
7. Importe el **modelo de contexto de factura de cliente**. Este modelo contiene parámetros adicionales que describen, entre otras cosas, el entorno en Finance que se utiliza para el complemento de facturación electrónica durante el envío de datos comerciales.

### <a name="turn-on-countryregion-specific-e-invoicing-features"></a><a name="region-specific"></a>Activar características de facturación electrónica específicas del país o región

Para activar las funciones de facturación electrónica específicas de cada país o región para que funcionen con el complemento de facturación electrónica, debe activar la función en cada entidad legal donde desee utilizarla. Posteriormente, ya no se puede utilizar la antigua integración de facturación electrónica y se activa la integración con el nuevo complemento de facturación electrónica.

1. Vaya a **Administración de la organización \> Configuración \> Parámetros de documentos electrónicos**.
2. En la pestaña **Características**, en la fila de la función relacionada con la función de facturación electrónica específica de su país o región, seleccione la casilla de verificación en la columna **Habilitado**. Para obtener información sobre qué característica debe activar, consulte el tema "Introducción al complemento de facturación electrónica" específico del país o región.

![Activar la función de facturación electrónica](media/e-invoicing-services-get-started-enable-invoicing-feature.png)

> [!NOTE]
> Si tiene varias entidades legales configuradas para diferentes países o regiones, puede activar la función de facturación electrónica específica del país o región para cada entidad legal.

### <a name="import-er-configurations-and-set-up-the-response-types-to-update-your-countryregion-specific-invoice-document"></a>Importe configuraciones de ER y configure los tipos de respuesta para actualizar el documento de factura específico de su país o región

Si el documento de factura enviado requiere una actualización después de la respuesta del envío a los servicios de autorización del gobierno, debe importar un modelo de datos de ER especial y configuraciones para permitir que se actualice el estado del documento de factura o cualquier otro campo adicional.

1. En el espacio de trabajo **Informes electrónicos**, en la sección **Proveedores de configuración**, seleccione el icono **Microsoft**.
2. Seleccione **Repositorios**.
3. Seleccione **Recurso global** y luego seleccione **Abierto**.
4. Importe **Modelo de mensaje de respuesta**, **Formato de importación de mensajes de respuesta**, **Mapeo del modelo de mensaje de respuesta al destino** y **Formato de importación de contenido de archivo**.
5. Vaya a **Administración de la organización \> Configuración \> Parámetros de documentos electrónicos**.
6. En la pestaña **Documento electrónico**, seleccione **Agregar** para ingresar el nombre de la tabla relacionada con el documento de factura específico de su país o región. Para obtener información sobre qué nombres de tabla debe seleccionar, consulte el tema "Introducción al complemento de facturación electrónica" específico del país o región.
7. Seleccione **Tipos de respuesta** para configurar los tipos de respuesta. Para obtener información sobre qué nombres de tabla debe seleccionar, consulte el tema "Introducción al complemento de facturación electrónica" específico del país o región.

![Configuración de tipos de respuesta](media/e-invoicing-services-get-started-set-up-response-types.png)

## <a name="e-invoicing-feature-names-by-country"></a>Nombres de las funciones de facturación electrónica por país 
La siguiente tabla describe otras funciones de facturación electrónica disponibles para descargar desde el repositorio global de informes electrónicos para generar facturas electrónicas.
En RCS, puede descargar las funciones de facturación electrónica que se enumeran en esta tabla, las configuraciones de ER y las configuraciones de funciones de facturación electrónica disponibles.
En Finance, puede habilitar las referencias de funciones relacionadas en la página **Parámetros de documentos electrónicos** para emitir facturas electrónicas para estos países. Para obtener más información, consulte la sección [Activar las funciones de facturación electrónica específicas de cada país o región](#region-specific) anteriormente en este tema.

| Nombre de característica                      | Descripción                                 | Configuraciones ER                                                                                                  | Configuraciones                                                                                                                                                         | País o región  | Referencia de la característica      |
|-----------------------------------|---------------------------------------------|--------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|------------------------|
| Facturas electrónicas para Austria (AT) | Facturas de ventas y proyectos para Austria      | - Factura de ventas OIOUBL <br>- Factura del proyecto OIOUBL <br>- Nota de abono de ventas OIOUBL <br>- Nota de abono de proyecto OIOUBL | - Generación de facturas de venta (AT) <br>- Generación de facturas de proyecto (AT) <br>- Generación de notas de crédito de ventas (AT) <br>- Generación de notas de crédito de proyecto (AT)         | Austria         | EUR-00023              |
| Factura electrónica para Bélgica (BE)   | Facturas de ventas y proyectos para Bélgica      | - Factura de ventas UBL BE <br>- Factura de proyecto UBL BE <br>- Nota de abono de proyecto UBL BE <br>- Nota de abono de ventas UBL BE | - Generación de facturas de venta (BE)<br>- Generación de facturas de proyecto (BE) <br>- Generación de notas de crédito de ventas (BE) <br>- Generación de notas de crédito de proyecto (BE)         | Bélgica         | EUR-00023              |
| Factura electrónica para Dinamarca (DK)    | Facturas de ventas y proyectos para Dinamarca      | - Factura de ventas OIOUBL <br>- Factura del proyecto OIOUBL <br>- Nota de abono de ventas OIOUBL <br>- Nota de abono de proyecto OIOUBL | - Generación de facturas de venta (DK) <br>- Generación de facturas de proyecto (DK) <br>- Generación de notas de crédito de ventas (DK)<br>- Generación de notas de crédito de proyecto (DK)         | Dinamarca         | EUR-00023<br> DK-00001 |
| Factura electrónica para Países Bajos (NL)     | Facturas de ventas y proyectos para Países Bajos  | - Factura de ventas UBL NL <br>- Factura de proyecto UBL NL <br>- Nota de abono de ventas UBL NL <br>- Nota de abono de proyecto UBL NL | - Generación de facturas de venta (NL) <br> - Generación de facturas de proyecto (NL) <br> - Generación de notas de crédito de ventas (NL) <br>- Generación de notas de crédito de proyecto (NL)          | Países Bajos | EUR-00023              |
| Factura electrónica para Estonia (EE)  | Facturas de ventas y proyectos para Estonia      | - Factura de ventas (EE) <br> - Factura de proyecto (EE)                                                                     | - Generación de facturas de venta (EE) <br>- Generación de facturas de proyecto (EE)                                                                                           | Estonia         | EUR-00023              |
| Factura electrónica para Finlandia (FI)   | Facturas de ventas y proyectos para Finlandia      | - Factura de ventas (FI) <br>- Generación de facturas de proyecto (FI)                                                          | - Generación de facturas de venta (FI) <br>- Generación de facturas de proyecto (FI)                                                                                           | Finlandia         | EUR-00023              |
| Factura electrónica para Francia (FR)    | Facturas de ventas y proyectos para Francia    | - Factura de ventas UBL FR <br> - Factura de proyecto UBL FR <br> - Nota de abono de ventas UBL FR <br>- Nota de abono de proyecto UBL FR | - Generación de facturas de venta (FR) <br> - Generación de facturas de proyecto (FR) <br>- Generación de notas de crédito de ventas (FR) <br>- Generación de notas de crédito de proyecto (FR)         | Francia          | EUR-00023              |
| Factura electrónica para Alemania (DE)    | Facturas de ventas y proyectos para Alemania      |- Factura de ventas (DE) <br> - Factura de proyecto <DE>                                                                     | - Generación de facturas de venta (DE) <br>- Generación de facturas de proyecto (DE)                                                                                           | Alemania         | EUR-00023              |
| Factura electrónica para Noruega (NO) | Facturas de ventas y proyectos para Noruega       | - Factura de ventas OIOUBL <br>- Factura del proyecto OIOUBL <br>- Nota de abono de ventas OIOUBL <br>- Nota de abono de proyecto OIOUBL | - Generación de facturas de venta (NO) <br>- Generación de facturas de proyecto (NO) <br>- Generación de notas de crédito de ventas (NO) <br>- Generación de notas de crédito de proyecto (NO)          | Noruega          | EUR-00023<br> NO-00010 |
| Factura electrónica para España (ES)   | Facturas de ventas y proyectos para España        | - Factura de ventas (ES) <br>- Factura de proyecto (ES)                                                                     | - Generación de facturas de venta (ES) <br>- Generación de facturas de proyecto (ES)                                                                                           | España           | EUR-00023 <br>ES-00025 |
| Factura electrónica para Italia (IT)   | Facturas de ventas y proyectos para Italia        | - (Vista previa) Factura de venta (IT) <br> - Factura de proyecto (IT)                                                           | - Factura de ventas <br> - Factura de proyecto                                                                                                                           | Italia           | EUR-00023 <br>IT-00036 |
| Factura electrónica PEPPOL         | Generación de factura de ventas y proyectos PEPPOL | - Factura de ventas PEPPOL <br>- Factura de proyecto PEPPOL <br>- Nota de crédito de ventas PEPPOL <br> - Nota de crédito de proyecto PEPPOL | - Generación de facturas de venta PEPPOL <br>- Generación de facturas de proyecto PEPPOL <br>- Generación de notas de crédito de ventas PEPPOL <br>- Generación de notas de crédito de proyecto PEPPOL |                 | EUR-00023              |


## <a name="electronic-invoice-processing-in-finance-and-supply-chain-management"></a>Procesamiento de facturas electrónicas en Finance y Supply Chain Management

Durante el procesamiento, completará estas tareas:

1. Enviar un documento comercial (factura) a través del complemento de facturación electrónica.
2. Ver los registros de ejecución de envíos.

### <a name="submit-business-documents"></a>Enviar documentos empresariales

Durante el proceso de envío regular, la comunicación entre el cliente y el complemento de facturación electrónica es bidireccional. El propósito es realizar dos tareas principales durante el envío de documentos electrónicos:

1. Envíe todos los documentos electrónicos que estén pendientes de envío por parte de Finance, que tengan el estado correcto de envío y cumplan con los criterios de selección.
2. Importar, en Finance, la respuesta que devuelve el complemento de facturación electrónica para documentos electrónicos enviados anteriormente. Después de la importación, las respuestas se analizan y el estado de los documentos comerciales se actualiza en consecuencia.

Puede enviar documentos comerciales de forma manual o según los requisitos de su horario.

1. Vaya a **Administración de la organización \> Periódico \> Documentos electrónicos \> Presentar documentos electrónicos**.
2. Para el primer envío de cualquier documento, establezca siempre la opción **Reenviar documentos** en **No**. Si debe volver a enviar un documento a través del servicio, configure esta opción en **Sí**.
3. En la ficha desplegable **Registros para incluir**, seleccione **Filtrar** para abrir el cuadro de diálogo **Investigación**, donde puede crear una consulta para seleccionar los documentos para su envío.

![Cuadro de diálogo Enviar documentos electrónicos](media/e-invoicing-services-get-started-submission-form.png)

### <a name="filter-query"></a>Consulta de filtro

1. En el cuadro de diálogo **Consulta**, en la pestaña **Rango**, introduzca los criterios de filtrado mediante los campos **Tabla**, **Tabla derivada**, **Campo** y **Criterios**.
2. Seleccione **Agregar** para agregar tantos criterios adicionales como necesite para seleccionar los documentos comerciales.

    ![Configurar criterios de filtro de envío](media/e-invoicing-services-get-started-set-up-submission-filter-criteria.png)

3. Seleccione **Aceptar** para cerrar el cuadro de diálogo **Consulta**.
4. Seleccione **Aceptar** para enviar los documentos comerciales seleccionados al complemento de facturación electrónica.

    > [!NOTE]
    > Durante su primer intento de enviar un documento a través del servicio, se le pedirá que confirme la conexión con el complemento de facturación electrónica. Seleccione **Haga clic aquí para conectar al servicio de envío de documentos electrónicos**.
    >
    > ![Cuadro de mensaje Conectar al servicio de envío de documentos electrónicos](media/e-invoicing-services-get-started-dialog-form-connect-e-Invoicing-services.png)
    >
    > Si la conexión es exitosa, recibirá un mensaje de confirmación.
    >
    > ![Confirmación de conexión al complemento de facturación electrónica](media/e-invoicing-services-get-started-confirmation-connection-e-invoicing-services.png)

5. Cierre el cuadro de diálogo.

> [!NOTE]
> Después de cada envío, el Centro de actividades muestra el número de documentos enviados.
>
> ![Mensajes del centro de acción](media/e-invoicing-services-get-started-view-action-center-messages.png)

### <a name="submission-by-batch"></a>Envío por lote

En lugar de enviar documentos manualmente, puede automatizar el proceso de envío y ejecutarlo en segundo plano, según una frecuencia configurada de ejecución por lotes.

1. En el cuadro de diálogo **Enviar documentos electrónicos**, en la ficha desplegable **Ejecutar en segundo plano**, configure la opción **Procesamiento por lotes** como **Sí**.
2. En la pestaña **Periodicidad**, configure la frecuencia de procesamiento por lotes.

![Configurar el envío por lotes](media/e-invoicing-services-get-started-set-up-submission-batch.png)

### <a name="view-all-submission-logs"></a>Ver todos registros de envío

1. Vaya a **Administración de la organización \> Periódico \> Documentos electrónicos \> Registro de envío de documentos electrónicos**.
2. En el campo **Tipo de Documento**, seleccione el tipo de documento por el que filtrar.

    ![Seleccionar el tipo de documento para ver los registros de envío](media/e-invoicing-services-get-started-select-document-type-for-viewing-submission-log.png)

    > [!IMPORTANT]
    > El valor que se muestra en la columna **Estado de presentación** representa el estado relacionado con la finalización del proceso de envío en sí. Indica si el flujo de acciones que está configurado en RCS se ejecutó hasta el final, independientemente de si el documento electrónico fue aprobado o rechazado. El valor de la columna **Estado de presentación** no representa el estado del documento enviado. Puede ver el estado del documento enviado (es decir, si el documento fue aprobado o rechazado) en la ficha desplegable **Registro de acciones de procesamiento** en los detalles del registro de envío, como se describe a continuación.

3. En el panel de acciones, seleccione **Consultas \> Detalles del envío**.
4. Vea los detalles del registro de envío.

    ![Detalles del registro de envío](media/e-invoicing-services-get-started-view-submission-log-form.png)

Los resultados que se muestran en el registro de envío dependen de cómo se configuró la función de facturación electrónica en RCS. Sin embargo, independientemente de la configuración, el registro de envío siempre tiene tres fichas desplegables:

- **Procesamiento de acciones** - Esta ficha desplegable muestra el registro de ejecución de las acciones configuradas en la versión de función que se configuró en RCS. La columna **Estado** muestra si la acción se ejecutó correctamente.
- **Archivos de acción** - Esta ficha desplegable muestra los archivos intermedios que se generaron durante la ejecución de las acciones. Puede seleccionar **Ver** para descargar el archivo y ver su contenido.
- **Registro de acciones de procesamiento** - Esta ficha desplegable muestra los resultados de la comunicación entre el complemento de facturación electrónica y el servicio web de destino. También muestra lo que devolvió el procesamiento del servicio web.

## <a name="related-topics"></a>Temas relacionados

- [Descripción general del complemento de facturación electrónica](e-invoicing-service-overview.md)
- [Introducción al complemento de facturación electrónica para Brasil](e-invoicing-bra-get-started.md)
- [Introducción al complemento de facturación electrónica para México](e-invoicing-mex-get-started.md)
- [Introducción al complemento de facturación electrónica para Italia](e-invoicing-ita-get-started.md)
- [Configurar el complemento de facturación electrónica](e-invoicing-setup.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]