---
title: Introducción al complemento de facturación electrónica para Brasil
description: Este tema proporciona información que le ayudará a comenzar con el complemento de facturación electrónica para Brasil en Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 09/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 0320bd1d9e93cc30ed75f28e387ac2ec8dbfc226
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4962844"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-brazil"></a>Introducción al complemento de facturación electrónica para Brasil 

[!include [banner](../includes/banner.md)]


> [!IMPORTANT]
> El complemento de facturación electrónica para Brasil no admite actualmente todas las funciones que están disponibles en la integración de documentos fiscales incluida en Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management.

Este tema proporciona información que le ayudará a comenzar con el complemento de facturación electrónica para Brasil. Le guía a través de los pasos de configuración que dependen del país o la región en Regulatory Configuration Services (RCS) y en Finance y Supply Chain Management. También lo guía a través del proceso de presentación de un documento fiscal NF-e (Documento fiscal electrónico modelo 55) a través del servicio, y explica cómo revisar los resultados del procesamiento y el estado de los documentos fiscales.

## <a name="prerequisites"></a>Requisitos previos

Antes de completar los pasos de este tema, debe completar los pasos en [Comience con el complemento de facturación electrónica](e-invoicing-get-started.md).

## <a name="rcs-setup"></a>Configuración de RCS

Durante la configuración de RCS, completará estas tareas:

1. Importe la función de facturación electrónica para documentos fiscales NF-e.
2. Revise los formatos de archivo que se requieren para enviar documentos fiscales NF-e para autorización.
3. Revise los formatos de archivo necesarios para solicitar la cancelación de un NF-e aprobado.
4. Configure el evento que se requiere para enviar documentos fiscales NF-e para autorización.
5. Configure el evento necesario para solicitar la cancelación de un NF-e aprobado.
6. Asigne la función de facturación electrónica a un entorno adicional de facturación electrónica.
7. Publicar la función de facturación electrónica.

> [!NOTE]
> "Característica de facturación electrónica" es el nombre genérico del recurso que se configura y publica para consumir el servidor complementario de facturación electrónica. La configuración de la característica de facturación electrónica combina, entre otras cosas, el uso de formatos de configuración de informes electrónicos (ER) para crear archivos de importación y exportación configurables, y el uso de acciones y flujos de acciones para permitir la creación de reglas configurables para enviar solicitudes, importar respuestas y analizar el contenido de la respuesta.

## <a name="import-the-e-invoicing-feature"></a>Importar la función de facturación electrónica

1. Inicie sesión en su cuenta de RCS
2. En el espacio de trabajo **Características de globalización**, en la sección **Características**, seleccione el mosaico **Facturación electrónica**.
3. En la página **Funciones de facturación electrónica**, seleccione **Importar** para importar una característica de facturación electrónica de documento fiscal NF-e del repositorio global.

    ![Botón Importar](media/e-Invoicing-services-get-started-BRA-Select-Import-e-Invoicing-feature.png)

4. Seleccione la función de documento fiscal NF-e y luego seleccione **Importar**.

    ![Importación de la función NF-e](media/e-Invoicing-services-get-started-BRA-Select-Import-NF-e-feature.png)

### <a name="create-a-new-version-of-the-nf-e-fiscal-document-feature"></a>Crear una nueva versión de la función de documento fiscal NF-e

- En la página **Funciones de facturación electrónica**, en la pestaña **Versiones**, seleccione **Nuevo**.

![Agregar una nueva versión de la función de facturación electrónica](media/e-Invoicing-services-get-started-BRA-Select-New-e-Invoicing-feature-version.png)

### <a name="update-the-configuration-version"></a>Actualizar la versión de configuración

1. En la página **Funciones de facturación electrónica**, en la pestaña **Configuraciones**, seleccione **Agregar** o **Eliminar** para administrar las versiones de configuración (configuraciones de formato de archivo ER).

    ![Gestión de configuraciones de funciones de facturación electrónica](media/e-Invoicing-services-get-started-BRA-Manage-e-Invoicing-feature-configurations.png)

    - Cuando crea una nueva versión de la función de documento fiscal NF-e, todas las versiones de configuración (formatos de archivo ER) se heredan de la última versión.
    - Para enviar el documento fiscal NF-e para autorización, se requieren las siguientes versiones de configuración:

        - NFe enviar formato de exportación
        - Importación de mensajes de respuesta NFe
        - Importación del registro de errores de NFe

    - Para enviar la cancelación de NF-e, se requiere la siguiente versión de configuración:

        - NFe cancelar formato de exportación

2. En la lista, seleccione una versión de configuración y luego seleccione **Editar** o **Ver** para abrir la página **Diseñador de formatos**, donde puede editar o ver la configuración.

    ![Abrir la página Diseñador de formato](media/e-Invoicing-services-get-started-BRA-Configuration-ER-fomat-designer.png)

3. Utilice la página **Diseñador de formatos** para editar o ver las configuraciones de archivo del formato ER. Para obtener más información, consulte [Crear configuraciones de documentos electrónicos](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration).

    ![Página de diseñador de formato](media/e-Invoicing-services-get-started-BRA-ER-Format-designer.png)

### <a name="manage-the-e-invoicing-feature-setups"></a>Administrar las configuraciones de la función de facturación electrónica

- En la página **Funciones de facturación electrónica**, en la pestaña **Configuraciones**, seleccione **Agregar** o **Eliminar** para administrar las configuraciones de la función de facturación electrónica (es decir, eventos NF-e).

![Administrar las configuraciones de la función de facturación electrónica](media/e-Invoicing-services-get-started-BRA-Manage-e-Invoicing-feature-setup.png)

Cuando crea una nueva versión de la función de documento fiscal NF-e que se deriva de otra función de facturación electrónica, todas las configuraciones de funciones (eventos NF-e) se heredan de la última versión.

Para enviar los documentos fiscales NF-e para autorización, se necesita la configuración de la característica **Enviar**.

Para enviar la cancelación de NF-e, se necesita la configuración de la característica **Cancelación**.

#### <a name="configure-the-submit-feature-setup"></a>Configurar la configuración de la función Enviar

1. En la página **Funciones de facturación electrónica**, en la pestaña **Configuraciones**, en la columna **Configuración de funciones**, seleccione **Enviar**.
2. Seleccione **Editar**.

    ![Editar la configuración de características de facturación electrónica](media/e-Invoicing-services-get-started-BRA-Edit-e-Invoicing-feature-setup.png)

3. En la página **Configuración de la versión de función**, seleccione la pestaña **Acciones** para gestionar la lista de acciones.

    ![Pestaña Acciones](media/e-Invoicing-services-get-started-BRA-Select-Actions.png)

4. Revise las acciones que se requieren para enviar un NF-e para autorización.

    | Id. de acción | Nombre de acción                  | Descripción de la acción                                                |
    |-----------|------------------------------|-------------------------------------------------------------------|
    | 1         | Transformar documento           | Cree el archivo XML NF-e para enviarlo.                          |
    | 2         | Firmar documento                | Aplicar el certificado digital al archivo XML.                    |
    | 3         | Llamar al servicio SEFAZ brasileño | Envíe el archivo XML firmado a los servicios web para su autorización. |
    | 4         | Respuesta del proceso             | Obtenga la respuesta del servicio web.                                     |
    | 5         | Transformar documento           | Analizar el contenido del archivo que se recibe como respuesta.     |
    | 6         | Transformar documento           | Cree el archivo XML para consultar el estado del envío.    |
    | 7         | Llamar al servicio SEFAZ brasileño | Envíe el archivo XML que solicita el estado de envío.          |
    | 8         | Respuesta del proceso             | Obtenga la respuesta del servicio web.                                     |

#### <a name="set-up-the-url-for-sefaz-web-services"></a>Configurar la URL para los servicios web SEFAZ 

1. En la página **Configuración de la versión de función**, en la pestaña **Acciones**, en la ficha desplegable **Acciones**, seleccione **Llamar al servicio SEFAZ brasileño** (id. de acción **3**).
2. En la ficha desplegable **Parámetros**, en el campo **Dirección URL**, ingrese la URL del servicio web SEFAZ para el envío de NF-e.
3. En la ficha desplegable **Acciones**, seleccione **Llamar al servicio SEFAZ brasileño** (id. de acción **7**).
4. En la ficha desplegable **Parámetros**, en el campo **Dirección URL**, ingrese la URL del servicio web SEFAZ para el envío de NF-e.

#### <a name="configure-the-cancellation-feature-setup"></a>Configurar la función de cancelación

1. En la página **Funciones de facturación electrónica**, en la pestaña **Configuraciones**, en la columna **Configuración de funciones**, seleccione **Cancelación**.
2. Seleccione **Editar**.
3. En la página **Configuración de la versión de función**, seleccione la pestaña **Acciones** para gestionar la lista de acciones.
4. Revise las acciones necesarias para solicitar la cancelación de un NF-e aprobado.

    | Id. de acción | Nombre de acción                  | Descripción de la acción                                               |
    |-----------|------------------------------|------------------------------------------------------------------|
    | 1         | Transformar documento           | Cree el archivo XML de cancelación de NF-e para enviarlo.            |
    | 2         | Firmar documento                | Aplicar el certificado digital al archivo XML.                   |
    | 3         | Llamar al servicio SEFAZ brasileño | Envíe el archivo XML firmado a los servicios web para su cancelación. |
    | 4         | Respuesta del proceso             | Obtenga la respuesta del servicio web.                                    |

#### <a name="set-up-the-url-for-sefaz-web-services"></a>Configurar la URL para los servicios web SEFAZ

1. En la página **Configuración de la versión de función**, en la pestaña **Acciones**, en la ficha desplegable **Acciones**, seleccione **Llamar al servicio SEFAZ brasileño** (id. de acción **3**).
2. En la ficha desplegable **Parámetros**, en el campo **Dirección URL**, ingrese la URL del servicio web SEFAZ para la cancelación de un NF-e aprobado.

### <a name="make-an-e-invoicing-environment-available-and-assign-a-draft-version"></a>Ponga a disposición un entorno de facturación electrónica y asigne una versión borrador

1. En la página **Funciones de facturación electrónica**, en la pestaña **Entornos**, seleccione **Habilitar**.
2. En el campo **Entorno**, seleccione el entorno.
3. En el campo **Válido desde**, seleccione la fecha en que el nuevo entorno debe entrar en vigencia.
4. Seleccione **Habilitar**.

![Habilitación de un entorno de facturación electrónica](media/e-Invoicing-services-get-started-BRA-Enable-e-Invoicing-environment.png)

### <a name="change-the-status-to-completed"></a>Cambiar el estado a Completado

1. En la página **Funciones de facturación electrónica**, en la pestaña **Versiones**, seleccione la versión de la función de facturación electrónica que tiene un estado de **Borrador**.
2. Seleccione **Cambiar estado\> Completada**.

### <a name="change-the-status-to-publish"></a>Cambiar el estado a Publicar

1. En la página **Funciones de facturación electrónica**, en la pestaña **Versiones**, seleccione la versión de la función de facturación electrónica que tiene un estado **Completado**.
2. Seleccione **Cambiar estado \> Publicar**.

![Publicar la función de facturación electrónica](media/e-Invoicing-services-get-started-BRA-Publish-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing-add-on-integration-in-finance-or-supply-chain-management"></a>Configurar la integración del complemento de facturación electrónica en Finance o Supply Chain Management

Durante la configuración, completará estas tareas:

1. Active la función NF-e Federal para Brasil.
2. Importe el modelo de datos ER específico, el mapeo del modelo de datos ER y los formatos necesarios para los documentos fiscales NF-e.
3. Importe la configuración de ER y configure los tipos de respuesta necesarios para actualizar el estado del documento fiscal después del resultado del proceso de envío.

### <a name="turn-on-the-nf-e-federal-feature-for-brazil"></a>Activar la función NF-e Federal para Brasil

1. Vaya a **Administración de la organización \> Configuración \> Parámetros de documentos electrónicos**.
2. En la pestaña **Características**, seleccione la casilla **Habilitar** en la fila de la referencia de característica **BR00053**.

### <a name="import-the-er-data-model-mapping-required-for-nf-e-fiscal-documents"></a>Importe el mapeo del modelo de datos ER requerido para los documentos fiscales NF-e

1. Iniciar sesión en Finance.
2. En el espacio de trabajo **Informes electrónicos**, en la sección **Proveedores de configuración**, seleccione el icono **Microsoft**. Asegúrese de que este proveedor de configuración esté establecido en **Activo**. Para obtener más información sobre cómo establecer un proveedor en **Activo**, vea [Crear proveedores de la configuración y marcarlos como activos](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).
3. Seleccione **Repositorios**.
4. Seleccione **Recurso global \> Abierto**.
5. Importe las configuraciones de **Mapeo de documentos fiscales**.

### <a name="import-er-configurations-and-set-up-the-response-types-for-fiscal-documents"></a>Importar configuraciones de ER y configurar los tipos de respuesta para documentos fiscales

1. En el espacio de trabajo **Informes electrónicos**, en la sección **Proveedores de configuración**, seleccione el icono **Microsoft**.
2. Seleccione **Repositorios**.
3. Seleccione **Recurso global \> Abierto**.
4. Importe **Importación de registro de errores NF-e (BR)**, **Formato de importación de datos de respuesta NF-e (BR)** e **Importación de mensajes de respuesta NF-e (BR)**.
5. Vaya a **Administración de la organización \> Configuración \> Parámetros de documentos electrónicos**.
6. En la pestaña **Documento electrónico** haga clic en **Agregar**.
6. En el campo **Nombre de la tabla**, ingrese **Encabezado del documento fiscal**.
7. En el campo **Contexto del documento**, seleccione **Modelo de contexto de factura de cliente: contexto de documento fiscal**.
8. Seleccione **Tipos de respuesta**.
9. Seleccione **Nuevo** y, en el campo **Tipo de respuesta**, seleccione **Respuesta**.
10. En el campo **Estado de envío**, seleccione **Pendiente**.
11. En el campo **Mapeo de modelos**, seleccione **Formato de importación del mensaje de respuesta: mapeo del modelo del mensaje de respuesta**.
12. Seleccione **Guardar**.
13. Seleccione **Nuevo** y, en el campo **Tipo de respuesta**, introduzca **ResponseData**.
14. En el campo **Estado de envío**, seleccione **Pendiente**.
15. En el campo **Mapeo de modelos**, seleccione **Formato de importación de datos de respuesta NFe - Importación de datos de respuesta**.
16. Seleccione **Guardar**.

## <a name="electronic-invoice-processing"></a>Procesamiento de facturas electrónicas

Durante el procesamiento en Finance, completará estas tareas:

1. Enviar un documento fiscal a través del complemento de facturación electrónica.
2. Ver los registros de ejecución de envío y revisar los resultados del procesamiento.
3. Enviar la cancelación de un documento fiscal a través del complemento de facturación electrónica.

### <a name="submit-nf-e-fiscal-documents-for-sefaz-authorization"></a>Presentar documentos fiscales NF-e para la autorización SEFAZ 

Después de activar la característica **Integración adicional configurable de facturación electrónica**, el proceso antiguo para enviar documentos fiscales NF-e para su autorización (**Exportar/Importar proceso de NF-e**) ya no se puede utilizar. Es reemplazado por un nuevo proceso que se llama **Presentar documentos electrónicos**.

> [!NOTE]
> Antes de continuar, asegúrese de tener uno o más documentos fiscales de cliente modelo 55 que fueron emitidos por el establecimiento fiscal del cliente. La dirección de estos documentos fiscales debe establecerse en **Saliente** y el estado debe ser **Creado**. Para más información, vea [Emitir documento fiscal de cliente (Brasil)](https://docs.microsoft.com/dynamics365/finance/localizations/tasks/br-00038-issuing-customer-fiscal-document).

1. Vaya a **Administración de la organización \> Periódico \> Documentos electrónicos \> Presentar documentos electrónicos**.
2. Para el primer envío de cualquier documento, establezca siempre la opción **Reenviar documentos** en **No**. Si debe volver a enviar un documento a través del servicio, configure esta opción en **Sí**.
3. En la ficha desplegable **Registros para incluir**, seleccione **Filtrar** para abrir el cuadro de diálogo **Investigación**, donde puede crear una consulta para seleccionar los documentos para su envío.
4. En la ficha **Intervalo**, seleccione **Agregar**.
5. En el campo **Tabla**, seleccione **Encabezado del documento fiscal**.
6. En el campo **Tabla derivada**, seleccione **Encabezado del documento fiscal**.
6. En el campo **Campo**, seleccione **Número**.
7. En el campo **Criterios**, ingrese el número del documento fiscal que se debe presentar.
8. Seleccione **Aceptar** para cerrar el cuadro de diálogo **Consulta**.
8. Seleccione **Aceptar** para enviar los documentos seleccionados.

> [!NOTE]
> Durante su primer intento de enviar un documento a través del servicio, se le pedirá que confirme la conexión con el complemento de facturación electrónica. Seleccione **Haga clic aquí para conectar al servicio de envío de documentos electrónicos**.

### <a name="view-all-submission-logs"></a>Ver todos registros de envío

Después de activar la función **Integración adicional configurable de facturación electrónica**, una nueva página está disponible que le permite dar seguimiento al proceso de envío de documentos. Puede utilizar esta página para ver los registros de envío de todos los documentos enviados.

1. Vaya a **Administración de la organización \> Periódico \> Documentos electrónicos \> Registro de envío de documentos electrónicos**.
2. En el campo **Tipo de Documento**, seleccione **Encabezado del documento fiscal** para filtrar solo por documentos fiscales.
3. En el panel de acciones, seleccione **Consultas \> Detalles de envío** para ver los detalles de los registros de ejecución del envío.

![Ver los detalles del registro de envío](media/e-Invoicing-services-get-started-BRA-View-Submission-log-details.png)

> [!NOTE] 
> Para los documentos fiscales NF-e, la columna **Código de error** muestra el código de retorno devuelto por los servicio web SEFAZ.

### <a name="view-submission-logs-through-the-fiscal-document-page"></a>Ver registros de envío a través de la página del documento fiscal

Después de activar la característica **Integración complementaria de facturación electrónica configurable**, también puede ver los registros de envío a través de la página del documento fiscal.

1. Vaya a **Libro mayor \> Consultas e informes \> Documentos fiscales \> Todos los documentos fiscales**.
2. Seleccione un documento fiscal que se envió previamente a través del complemento Facturación electrónica.
3. En el panel de acciones, en la pestaña **Federal NF-e**, seleccione **Registro de documento electrónico**.

![Ver registros de envío desde la página del documento fiscal](media/e-Invoicing-services-get-started-BRA-View-Submission-log-from-Fiscal-document-viewer.png)

### <a name="submit-approved-nf-e-fiscal-documents-for-sefaz-cancellation"></a>Presentar documentos fiscales NF-e aprobados para la cancelación SEFAZ

Después de activar la característica **Integración adicional configurable de facturación electrónica**, el antiguo proceso para cancelar documentos fiscales NF-e ya no se puede utilizar. Se reemplaza por un nuevo proceso de cancelación que está integrado en la página **Registro de envío de documentos electrónicos**.

> [!NOTE]
> Asegúrese de haber ejecutado la cancelación del documento fiscal del cliente para un documento fiscal NF-e aprobado. Para más información, vea [Cancelar documento fiscal de cliente (Brasil)](https://docs.microsoft.com/dynamics365/finance/localizations/latam-bra-cancel-customer-fiscal-documents).

1. Vaya a **Administración de la organización \> Periódico \> Documentos electrónicos \> Registro de envío de documentos electrónicos**.
2. Seleccione el documento fiscal y luego seleccione **Funciones \> Enviar envíos relacionados**.
3. Ingrese una descripción para el envío relacionado y luego seleccione **Aceptar**.

### <a name="view-cancellation-submission-logs"></a>Ver todos registros de envío de cancelación

1. Vaya a **Administración de la organización \> Periódico \> Documentos electrónicos \> Registro de envío de documentos electrónicos**.
2. En el campo **Tipo de Documento**, seleccione **Encabezado del documento fiscal** para filtrar solo por documentos fiscales.
3. Seleccione el documento fiscal y luego, en el Panel de acciones, seleccione **Consultas \> Envío relacionado**.

    Las presentaciones relacionadas son presentaciones relacionadas con una presentación principal que se realizó primero. Por ejemplo, la presentación que autoriza una NF-e específica es la presentación principal. La presentación que solicita la cancelación del mismo NF-e en SEFAZ es una presentación relacionada. Existe solo porque solicita la cancelación del trabajo que se realizó a través de otro envío.

    La página **Envíos relacionados** muestra todos los envíos relacionados y su estado de envío para un documento fiscal determinado. En la siguiente ilustración, la primera línea representa el envío que solicitó la aprobación del documento fiscal. La segunda línea representa el envío que canceló ese documento fiscal.

    ![Ver los registros de envío de cancelación](media/e-Invoicing-services-get-started-BRA-View-Cancellation-Submission-log.png)

4. En el panel de acciones, seleccione **Consultas \> Detalles de envío** para ver los detalles de los registros de ejecución del envío.

    ![Ver los detalles del registro de envío de cancelación](media/e-Invoicing-services-get-started-BRA-View-Cancellation-Submission-log-details.png)

## <a name="privacy-notice"></a>Aviso de privacidad
Habilitar la función BR-00053 (NF-e Federal) puede requerir el envío de datos limitados, que incluyen el ID de registro fiscal de la organización. Este será transmitido a agencias de terceros autorizadas por la autoridad tributaria para propósitos de enviar facturas electrónicas a esta autoridad tributaria en el formato predefinido requerido para la integración con el servicio web del gobierno. Un administrador puede habilitar y deshabilitar la función BR-00053 (NF-e Federal) navegando a **Administración de la organización \> Configuración \> Parámetros de documentos electrónicos**. Seleccione la pestaña **Características**, seleccione la fila que contiene la característica BR-00053 y luego haga la selección apropiada. Los datos importados de estos sistemas externos a este servicio en línea de Dynamics 365 están sujetos a nuestra [declaración de privacidad](https://go.microsoft.com/fwlink/?LinkId=512132). Consulte las secciones de Aviso de privacidad en la documentación de funciones específicas de cada país o región para obtener más información.


## <a name="additional-resources"></a>Recursos adicionales

- [Descripción general del complemento de facturación electrónica](e-invoicing-service-overview.md)
- [Introducción al complemento de facturación electrónica](e-invoicing-get-started.md)
- [Configurar el complemento de facturación electrónica](e-invoicing-setup.md)
