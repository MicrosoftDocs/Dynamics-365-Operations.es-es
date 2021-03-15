---
title: Introducción al complemento de facturación electrónica para México
description: Este tema proporciona información que le ayudará a comenzar con el complemento de facturación electrónica para México en Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
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
ms.openlocfilehash: d91f377af2514af932ea585adb75a56bdee13871
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988496"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-mexico"></a>Introducción al complemento de facturación electrónica para México

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> Es posible que el complemento de facturación electrónica para México no admita actualmente todas las funciones que están disponibles en el documento Comprobante Fiscal Digital por Internet (CFDI) y en la integración relacionada que está integrada en Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management.

Este tema proporciona información que le ayudará a comenzar con el complemento de facturación electrónica para México. Le guía a través de los pasos de configuración que dependen del país o la región en Regulatory Configuration Services (RCS) y Finance. También lo guía a través de los pasos que debe seguir en Finance para enviar facturas CFDI a través del servicio y explica cómo revisar los resultados del procesamiento y el estado de las facturas CFDI.

## <a name="prerequisites"></a>Requisitos previos

Antes de completar los pasos de este tema, debe completar los pasos en [Comience con el complemento de facturación electrónica](e-invoicing-get-started.md).

## <a name="rcs-setup"></a>Configuración de RCS

Durante la configuración de RCS, completará estas tareas:

1. Importe la función de facturación electrónica para procesar facturas CFDI.
2. Revise las configuraciones de formato necesarias para generar, enviar y recibir respuestas sobre facturas CFDI y para enviar y recibir respuestas sobre cancelaciones.
3. Configure los eventos que soportan los escenarios de envío de facturas CFDI.
4. Publique la función de facturación electrónica para facturas CFDI.

> [!NOTE]
> "Característica de facturación electrónica" es el nombre genérico del recurso que se configura y publica para consumir el servidor complementario de facturación electrónica. En este caso, las facturas CFDI (MX) son la función de facturación electrónica que configurará.

## <a name="import-the-e-invoicing-feature"></a>Importar la función de facturación electrónica

1. Inicie sesión en su cuenta de RCS.
2. En el espacio de trabajo **Características de globalización**, en la sección **Características**, seleccione el mosaico **Facturación electrónica**.
3. En la página **Funciones de facturación electrónica**, seleccione **Importar** para importar la característica **Facturas CFDI (MX)** del repositorio global.

    > [!NOTE]
    > Si no ve la función en la lista, seleccione **Sincronizar** y luego repita el paso 3.

![Importación de la función de facturas CFDI (MX)](media/e-Invoicing-services-get-started-MEX-Select-Import-CFDI-feature.png)

Cuando importa la característica **Facturas CFDI (MX)** del repositorio global, también se importan todas las configuraciones de características, incluidas las configuraciones y acciones.

### <a name="create-a-new-version-of-the-cfdi-invoices-mx-feature"></a>Cree una nueva versión de la función de facturas CFDI (MX)

Puede crear una nueva versión si, por ejemplo, se deben actualizar las URL. Para más información, vea [CFDI de facturación electrónica](tasks/mx-00010-e-invoicing-cfdi.md).

- En la página **Funciones de facturación electrónica**, en la pestaña **Versiones**, seleccione **Nuevo**.

![Agregar una nueva versión de la función de facturación electrónica](media/e-Invoicing-services-get-started-MEX-Select-New-e-Invoicing-feature.png)

### <a name="update-the-configuration-version"></a>Actualizar la versión de configuración

1. En la página **Funciones de facturación electrónica**, en la pestaña **Configuraciones**, seleccione **Agregar** o **Eliminar** para administrar las versiones de configuración (configuraciones de formato de archivo ER).

    ![Gestión de configuraciones de funciones de facturación electrónica](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Configurations.png)

    Cuando crea una nueva versión, todas las configuraciones se heredan de la última versión publicada. Para procesar facturas CFDI, se requieren las siguientes configuraciones:

    - Factura CFDI (BusinessDocumentService)
    - Importación de mensajes de respuesta CFDI
    - Importación del registro de errores de CFDI
    - Solicitud de cancelación de CFDI (MX) (BusinessDocumentService)
    - Factura CFDI (BusinessDocumentService)

2. En la lista, seleccione una versión de configuración y luego seleccione **Editar** o **Ver** para abrir la página **Diseñador de formatos**, donde puede editar o ver la configuración.

    ![Abrir la página Diseñador de formato](media/e-Invoicing-services-get-started-MEX-Configuration-ER-format-designer.png)

3. Utilice la página **Diseñador de formatos** para editar y ver las configuraciones de archivo del formato ER. Para obtener más información, consulte [Crear configuraciones de documentos electrónicos](../../dev-itpro/analytics/electronic-reporting-configuration.md).

    ![Página de diseñador de formato](media/e-Invoicing-services-get-started-MEX-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a>Administrar las configuraciones de la función de facturación electrónica

- En la página **Funciones de facturación electrónica**, en la pestaña **Configuraciones**, seleccione **Agregar**, **Eliminar** o **Editar** para administrar las configuraciones de la función de facturación electrónica.

![Administrar las configuraciones de la función de facturación electrónica](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Setup.png)

Para enviar facturas CFDI para autorización (generar el archivo XML, enviar el archivo XML y procesar la respuesta), se requiere la configuración de función **Factura de venta**.

Para enviar la cancelación de la factura CFDI, se requieren las configuraciones de funciones **Cancelación** y **Cancelar**.

### <a name="configure-the-sales-invoice-feature-setup"></a>Configurar la configuración de la función de factura de ventas

1. En la página **Funciones de facturación electrónica**, en la pestaña **Configuraciones**, en la columna **Configuración de funciones**, seleccione **Factura de venta**.
2. Seleccione **Editar** para configurar las acciones, reglas de aplicabilidad y variables.

    ![Editar la configuración de la función de facturación electrónica](media/e-Invoicing-services-get-started-MEX-Edit-e-Invoicing-feature-setup.png)

3. En la página **Configuración de la versión de función**, seleccione la pestaña **Acciones** para gestionar la lista de acciones. Las acciones definen una lista de operaciones que deben ejecutarse en orden secuencial para lograr la ejecución completa del evento.

    ![Pestaña Acciones](media/e-Invoicing-services-get-started-MEX-Select-Actions.png)

    | Id. de acción | Acción                   | Nombre de acción                                  | Descripción de la acción                                          |
    |-----------|--------------------------|----------------------------------------------|-------------------------------------------------------------|
    | 1         | Transformar documento       | Genere una factura electrónica CFDI sin señal digital | Genere la factura electrónica CFDI.                                |
    | 2         | Firmar documento            | Señal digital                                 | Firme digitalmente la factura electrónica para su envío.                |
    | 3         | Llamar al servicio PAC mexicano | Enviar factura electrónica CFDI                        | El cliente de Windows Communication Foundation (WCF) envía la factura electrónica CFDI. |
    | 4         | Respuesta del proceso         | Analizar la respuesta del servicio web                 | Analice la respuesta del servicio web y devuelva el registro de errores. |

### <a name="set-up-the-url-for-mexican-pac-web-services"></a>Configurar la URL para los servicios web del PAC mexicano 

1. En la página **Configuración de la versión de función**, en la pestaña **Acciones**, en la ficha desplegable **Acciones**, seleccione **Llamar al servicio PAC mexicano**.
2. En la ficha desplegable **Parámetros**, en el campo **Dirección URL**, ingrese la URL del servicio web para el envío de facturas CFDI.

> [!NOTE]
> Siga los mismos pasos para actualizar la URL de la acción **Llamar al servicio PAC mexicano** para las configuraciones de función **Cancelar** y **Solicitud de cancelación**.

## <a name="assign-the-draft-version-to-an-e-invoicing-environment"></a>Asignar la versión borrador a un entorno de facturación electrónica

1. En la página **Funciones de facturación electrónica**, en la pestaña **Entornos**, seleccione **Habilitar**.
2. En el campo **Entorno**, seleccione el entorno.
3. En el campo **Válido desde**, seleccione la fecha en que el nuevo entorno debe entrar en vigencia.
3. Seleccione **Habilitar**.

![Habilitación de un entorno de facturación electrónica](media/e-Invoicing-services-get-started-MEX-Enable-e-Invoicing-Environment.png)

## <a name="change-the-version-status-to-completed"></a>Cambiar el estado de la versión a Completado

1. En la página **Funciones de facturación electrónica**, en la pestaña **Versiones**, seleccione la versión de la función de facturación electrónica que tiene un estado de **Borrador**.
2. Seleccione **Cambiar estado\> Completada**.

## <a name="change-the-version-status-to-published"></a>Cambiar el estado de la versión a Publicado

- En la página **Funciones de facturación electrónica**, en la pestaña **Versiones**, seleccione **Cambiar Estado \> Publicar**.

## <a name="publish-the-e-invoicing-feature"></a>Publicar la función de facturación electrónica

1. En la página **Funciones de facturación electrónica**, seleccione la pestaña **Versiones** para gestionar el estado de la característica **Facturas CFDI (MX)**.
2. Seleccione **Cambiar estado** para cambiar el estado de la función.

![Cambiar el estado de la función de facturación electrónica](media/e-Invoicing-services-get-started-MEX-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing-add-on-integration-in-finance"></a>Configurar la integración del complemento de facturación electrónica en Finance

Para configurar el complemento de facturación electrónica en Finance, completará estas tareas:

1. Importe el modelo de datos ER, el mapeo del modelo de datos ER y los formatos necesarios para las facturas CFDI.
2. Configure tipos de respuesta para actualizar las facturas CFDI. Estos tipos de respuesta se utilizan para la respuesta del servidor del proveedor de certificación autorizado (PAC).

### <a name="import-the-er-data-model-er-data-model-mapping-and-context-configurations-for-cfdi-invoices"></a>Importe el modelo de datos ER, el mapeo del modelo de datos ER y las configuraciones de contexto para facturas CFDI

1. Iniciar sesión en Finance.
2. En el espacio de trabajo **Informes electrónicos**, en la sección **Proveedores de configuración**, seleccione el título **Microsoft**. Asegúrese de que este proveedor de configuración esté establecido en **Activo**. Para obtener más información sobre cómo establecer un proveedor en **Activo**, vea [Crear proveedores de la configuración y marcarlos como activos](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).
3. Seleccione **Repositorios**.
4. Seleccione **Recurso global \> Abierto**.
5. Importe **Modelo de factura**, **Mapeo del modelo de factura**, **Formato de factura CFDI (MX)**, **Formato de solicitud de cancelación de factura CFDI (MX)** y **Formato de cancelación de factura CFDI (MX)**.

### <a name="turn-on-the-feature-for-processing-cfdi-invoices"></a>Activar la función para procesar facturas CFDI

1. Vaya a **Administración de la organización \> Configuración \> Parámetros de documentos electrónicos**.
2. En la pestaña **Características**, seleccione la casilla **Habilitar** en las filas para referencias de características **MX-00010** y **MX-00016**.

![Activar las funciones para procesar facturas CFDI](media/e-Invoicing-services-get-started-MEX-Enable-CFDI-feature.png)

### <a name="import-er-configurations-and-set-up-the-response-types-for-updating-cfdi-invoices"></a>Importar configuraciones de ER y configurar los tipos de respuesta para actualizar las facturas CFDI

#### <a name="import-er-configurations"></a>Importar configuraciones de ER

1. En el espacio de trabajo **Informes electrónicos**, en la sección **Proveedores de configuración**, seleccione el título **Microsoft**.
3. Seleccione **Repositorios**.
4. Seleccione **Recurso global \> Abierto**.
5. Importe el **Modelo de mensaje de respuesta**, la **Importación de registro de errores CFDI (MX)** y la **Importación de mensajes de respuesta CFDI (MX)**.

#### <a name="set-up-the-response-types"></a>Configurar los tipos de respuesta

1. Vaya a **Administración de la organización \> Configuración \> Parámetros de documentos electrónicos**.
2. En la pestaña **Documento electrónico** haga clic en **Agregar**.
3. Ingrese el diario de facturas del cliente y luego, en el campo **Nombre de la tabla**, seleccione la factura del proyecto.
4. Para cada tabla, defina un contexto de documento relacionado:

    - Para **Diario de facturas del cliente**, introduzca **Contexto de la factura del cliente**.
    - Para **Factura del proyecto**, introduzca **Contexto de la factura del proyecto**.

4. Seleccione **Tipos de respuesta** para configurar los tipos de respuesta que pueden devolverse desde el complemento de facturación electrónica e incluirse en un diario de facturas de cliente o factura de proyecto.
5. Seleccione **Nuevo** y, en el campo **Tipo de respuesta**, seleccione **Respuesta**.
6. En el campo **Estado de envío**, seleccione **Pendiente**.
7. En el campo **Mapeo de modelos**, seleccione **Formato de importación del mensaje de respuesta: mapeo del modelo del mensaje de respuesta**.
8. Seleccione **Guardar**.
9. Seleccione **Nuevo** y, en el campo **Tipo de respuesta**, seleccione **ResponseData**.
10. En el campo **Estado de envío**, seleccione **Pendiente**.
11. En el campo **Mapeo de modelos**, seleccione **Formato de importación de datos de respuesta CFDI (detalles) - Importación de datos de respuesta**.
12. Seleccione **Guardar**.

## <a name="process-electronic-invoices-in-finance"></a>Procesar facturas electrónicas en Finance 

Durante el procesamiento de facturas CFDI en Finance a través del complemento Facturación electrónica, puede realizar las siguientes tareas:

- Enviar facturas electrónicas CFDI.
- Ver los registros de ejecución de envíos.
- Presentar la cancelación de una factura CFDI.

### <a name="submit-cfdi-invoices"></a>Enviar facturas electrónicas CFDI

Después de activar la característica **Integración adicional configurable de facturación electrónica**, el proceso **Exportación / Importación factura electrónica** (**Cuentas por cobrar \> Facturas \> Facturas electrónicas**) para enviar facturas CFDI ya no se puede utilizar. Es reemplazado por un nuevo proceso que se llama **Presentar documentos electrónicos**.

> [!NOTE]
> Antes de usar el nuevo proceso **Presentar documentos electrónicos**, verifique que se haya completado la configuración requerida para las facturas electrónicas mexicanas. Para obtener más información acerca de la conversión, consulte [Versión de diseño CFDI 3.3](https://docs.microsoft.com/dynamics365/finance/localizations/latam-mex-cfdi-3-3).

1. Vaya a **Administración de la organización \> Periódico \> Documentos electrónicos \> Presentar documentos electrónicos**.
2. Para el primer envío de cualquier documento, establezca siempre la opción **Reenviar documentos** en **No**. Si debe volver a enviar un documento a través del servicio, configure esta opción en **Sí**.
3. En la ficha desplegable **Registros para incluir**, seleccione **Filtrar** para abrir el cuadro de diálogo **Investigación**, donde puede crear una consulta para seleccionar los documentos para su envío.

![Envío de un documento CFDI](media/e-Invoicing-services-get-started-MEX-Submit-CFDI-document.png)

> [!NOTE]
> Durante su primer intento de enviar un documento a través del servicio, se le pedirá que confirme la conexión con el complemento de facturación electrónica. Seleccione **Haga clic aquí para conectar al servicio de envío de documentos electrónicos**.

### <a name="view-submission-logs"></a>Ver registros de envío

Puede ver los registros de envío de todos los documentos enviados o solo de un documento enviado.

#### <a name="view-all-submission-logs"></a>Ver todos registros de envío

Después de activar la función **Integración adicional configurable de facturación electrónica**, una nueva página está disponible que le permite dar seguimiento al proceso de envío de documentos. Puede utilizar esta página para ver los registros de envío de todos los documentos enviados.

1. Vaya a **Administración de la organización \> Periódico \> Documentos electrónicos \> Registro de envío de documentos electrónicos**.
2. En el campo **Tipo de Documento**, seleccione **Diario de facturas del cliente** para filtrar los documentos electrónicos requeridos.

    ![Seleccionar un tipo de documento para ver los registros de envío](media/e-Invoicing-services-get-started-MEX-Select-document-type-for-viewing-submission-log.png)

3. En el panel de acciones, seleccione **Consultas \> Detalles de envío** para ver los detalles de los registros de ejecución del envío.

    ![Ver los detalles del registro de envío](media/e-Invoicing-services-get-started-MEX-View-submission-log-details.png)

La información en los registros de envío se divide en tres fichas desplegables:

- **Procesamiento de acciones** - Esta ficha desplegable muestra el registro de ejecución de las acciones configuradas en la versión de función que se configuró en RCS. La columna **Estado** muestra si la acción se ejecutó correctamente.
- **Archivos de acción** - Esta ficha desplegable muestra los archivos intermedios que se generaron durante la ejecución de las acciones. Puede seleccionar **Ver** para descargar y ver el archivo.
- **Registro de acciones de procesamiento** - Esta ficha desplegable muestra los resultados de la comunicación entre el complemento de facturación electrónica y el servicio web de destino. También muestra lo que devolvió el procesamiento desde el servicio web. La columna **Código de error** muestra el código de retorno devuelto por el servicio web de autorización.

Cuando se autoriza la factura CFDI presentada, su estado se actualiza a **Aprobado**.

#### <a name="view-submission-logs-from-cfdi-invoices"></a>Ver registros de envío de facturas CFDI

Después de activar la característica **Integración complementaria de facturación electrónica configurable**, también puede ver los registros de envío de las facturas CFDI.

1. Vaya a **Clientes \> Consultas e informes \> CFDI (facturas electrónicas)**.
2. Seleccione una factura CFDI que se envió después de activar la característica **Integración adicional configurable de facturación electrónica**.
3. En el panel de acciones, en la pestaña **Historial**, seleccione **Registro de documento electrónico**.

![Ver registros de envío de facturas CFDI](media/e-Invoicing-services-get-started-MEX-View-submission-log-from-CFDI-invoice.png)

> [!NOTE]
> Para facturas CFDI que se enviaron antes de activar la característica **Integración adicional configurable de facturación electrónica**, el botón **Historial** está disponible. El botón **Historial** no está disponible para facturas CFDI que se enviaron después de activar la característica **Integración adicional configurable de facturación electrónica**.

### <a name="submit-cancellation-of-cfdi-invoices"></a>Presentar la cancelación de facturas CFDI

Después de activar la característica **Integración adicional configurable de facturación electrónica**, el antiguo proceso para cancelar facturas CFDI ya no se puede utilizar. Se reemplaza por un nuevo proceso de cancelación que está integrado en la página **Registro de envío de documentos electrónicos**.

1. Vaya a **Clientes \> Consultas e informes \> CFDI (facturas electrónicas)**.
2. Si la factura CFDI tiene un estado de **Aprobado**, seleccione **Funciones \> Cancelar CFDI**.
3. Vaya a **Administración de la organización \> Periódico \> Documentos electrónicos \> Registro de envío de documentos electrónicos**.
4. Seleccione la factura CFDI y luego seleccione **Funciones \> Enviar envíos relacionados**.
5. Ingrese una descripción para el envío relacionado y luego seleccione **Aceptar**.

#### <a name="view-cancellation-submission-logs"></a>Ver todos registros de envío de cancelación

1. Vaya a **Administración de la organización \> Periódico \> Documentos electrónicos \> Registro de envío de documentos electrónicos**.
2. En el campo **Tipo de Documento**, seleccione **Diario de facturas del cliente** para filtrar solo los documentos de diario de facturas de cliente.
3. Seleccione la factura CFDI y luego, en el Panel de acciones, seleccione **Consultas \> Envío relacionado**.

    La página **Envíos relacionados** muestra todos los envíos relacionados y su estado de envío para una factura CFDI determinada. En la siguiente ilustración, la primera línea representa el envío que solicitó la aprobación de la factura CFDI. La segunda línea representa el envío que canceló esa factura de CFDI.

    ![Ver los registros de envío de cancelación](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log.png)

4. En el panel de acciones, seleccione **Consultas \> Detalles de envío** para ver los detalles de los registros de ejecución del envío.

    ![Ver los detalles del registro de envío de cancelación](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log-details.png)

## <a name="privacy-notice"></a>Aviso de privacidad
Habilitar las funciones MX-00010 y MX-00016 (Factura CFDI y Cancelación de CFDI) puede requerir el envío de datos limitados, que incluyen el ID de registro fiscal de la organización. Este será transmitido a agencias de terceros autorizadas por la autoridad tributaria para propósitos de enviar facturas electrónicas a esta autoridad tributaria en el formato predefinido requerido para la integración con el servicio web del gobierno. Un administrador puede habilitar y deshabilitar las funciones MX-00010 y MX-00016 (Factura CFDI y Cancelación de CFDI) navegando a **Administración de la organización \> Preparar \> Parámetros de documentos electrónicos**. Seleccione la pestaña **Características**, seleccione las filas que contienen las características MX-00010 y MX-00016, y luego haga la selección apropiada. Los datos importados de estos sistemas externos a este servicio en línea de Dynamics 365 están sujetos a nuestra [declaración de privacidad](https://go.microsoft.com/fwlink/?LinkId=512132). Consulte las secciones de Aviso de privacidad en la documentación de funciones específicas de cada país o región para obtener más información.

## <a name="additional-resources"></a>Recursos adicionales

- [Descripción general del complemento de facturación electrónica](e-invoicing-service-overview.md)
- [Introducción al complemento de facturación electrónica](e-invoicing-get-started.md)
- [Configurar el complemento de facturación electrónica](e-invoicing-setup.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]