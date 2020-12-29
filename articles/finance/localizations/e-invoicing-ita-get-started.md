---
title: Introducción al complemento de facturación electrónica para Italia
description: Este tema proporciona información que le ayudará a comenzar con el complemento de facturación electrónica para Italia en Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management.
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
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: c513141f820c95fe3842478361693701f1e3641b
ms.sourcegitcommit: f860ac2b18f6bbbfc4a46b497baec2477105b116
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2020
ms.locfileid: "4447783"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-italy"></a>Introducción al complemento de facturación electrónica para Italia

[!include [banner](../includes/banner.md)]


> [!IMPORTANT]
> Es posible que el complemento de facturación electrónica para Italia no admita actualmente todas las funciones que están disponibles para las facturas electrónicas en Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management. 

Este tema proporciona información que le ayudará a comenzar con el complemento de facturación electrónica para Italia. Le guía a través de los pasos de configuración que dependen del país o la región en Regulatory Configuration Services (RCS) y Finance. También le guía a través del proceso de envío de facturas electrónicas que se generan en el formato **FatturaPA** específico de Italia a través del servicio y explica cómo revisar los resultados del procesamiento.

## <a name="prerequisites"></a>Requisitos previos

Antes de completar los pasos de este tema, debe completar los pasos en [Comience con el complemento de facturación electrónica](e-invoicing-get-started.md).

## <a name="rcs-setup"></a>Configuración de RCS

Durante la configuración de RCS, completará estas tareas:

1. Importar la función de facturación electrónica para la exportación de facturas electrónicas de clientes en el formato **FatturaPA**.
2. Revisar las configuraciones de formato necesarias para generar, enviar y recibir respuestas sobre facturas electrónicas.
3. Configurar los eventos que soportan los escenarios de envío de facturas electrónicas.
4. Publicar la función de facturación electrónica.

> [!NOTE]
> "Característica de facturación electrónica" es el nombre genérico del recurso que se configura y publica para consumir el servidor complementario de facturación electrónica. En este caso, la exportación de facturas electrónicas de clientes es la característica de facturación electrónica que va a configurar.

## <a name="import-the-e-invoicing-feature"></a>Importar la función de facturación electrónica

1. Inicie sesión en su cuenta de RCS.
2. En el espacio de trabajo **Características de globalización**, en la sección **Características**, seleccione el mosaico **Facturación electrónica**.
3. En la página **Funciones de facturación electrónica**, seleccione **Importar** para importar la característica de facturación electrónica del repositorio global.

    > [!NOTE]
    > Si no ve la lista de funciones disponibles, seleccione **Sincronizar**. 

4. Seleccione la función **Exportación de facturas electrónicas (IT)** y luego seleccione **Importar**.

![Importación de la función de exportación de facturas electrónicas (IT)](media/e-Invoicing-services-get-started-ITA-Select-Import-e-Invoicing-feature.png)

Cuando importa la función **Exportación de facturas electrónicas (IT)** del repositorio global, también se importan todas las configuraciones que se describen en las siguientes secciones.

## <a name="create-a-new-version-of-the-e-invoices-export-it-feature"></a>Crear una nueva versión de la función Exportación de facturas electrónicas (IT)

1. En la página **Funciones de facturación electrónica**, en la pestaña **Versiones**, seleccione **Nuevo**. 

    ![Agregar una nueva versión de la función de facturación electrónica](media/e-Invoicing-services-get-started-ITA-Select-New-e-Invoicing-feature-version.png)

    A continuación, configurará los formatos de informes electrónicos (ER) asociados con la función de facturación electrónica.

2. En la pestaña **Configuraciones**, seleccione **Agregar** para gestionar las versiones de configuración.

    ![Gestión de versiones de configuración de la función de facturación electrónica](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-configurations.png)

    En este paso, está agregando y configurando los formatos ER de diferentes archivos que se utilizan para exportar facturas electrónicas italianas. Para las facturas electrónicas italianas de FatturaPA, utilice las siguientes configuraciones estándar o las configuraciones personalizadas reales que utiliza para la facturación electrónica:

    - Factura de ventas (IT)
    - Factura de proyecto (IT)

    Cuando crea una función de facturación electrónica que se deriva de otra función de facturación electrónica, todos los formatos de ER se heredan de la función original.

3. Seleccione una configuración de archivo de formato ER específico.
4. Seleccione **Editar** o **Ver** para abrir la página **Diseñador de formatos**.

    ![Abrir la página Diseñador de formato](media/e-Invoicing-services-get-started-ITA-Configuration-ER-format-designer.png)

5. Utilice la página **Diseñador de formatos** para editar y ver las configuraciones de archivo del formato ER.

    ![Página de diseñador de formato](media/e-Invoicing-services-get-started-ITA-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a>Administrar las configuraciones de la función de facturación electrónica

- En la página **Funciones de facturación electrónica**, en la pestaña **Configuraciones**, seleccione **Agregar**, **Eliminar** o **Editar** para administrar las configuraciones de la función de facturación electrónica.

![Administrar las configuraciones de la función de facturación electrónica](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-setup.png)

En este paso, configura los eventos que son aplicables a las facturas electrónicas, incluida la generación de los archivos de salida XML en formato **FatturaPA** y firma digital (si se requiere).

### <a name="configure-the-sales-invoice-feature-setup"></a>Configurar la configuración de la función de factura de ventas

1. En la página **Funciones de facturación electrónica**, en la pestaña **Configuraciones**, en la columna **Configuración de funciones**, seleccione **Factura de venta**.
2. Seleccione **Editar**.
3. En la página **Configuración de la versión de función**, seleccione la pestaña **Acciones** para gestionar la lista de acciones. Las acciones definen una lista de operaciones que deben ejecutarse en orden secuencial para lograr la ejecución completa del evento.

    ![Pestaña Acciones](media/e-Invoicing-services-get-started-ITA-Select-Actions.png)

    | Id. de acción | Nombre de acción        | Descripción de la acción                                     |
    |-----------|--------------------|--------------------------------------------------------|
    | 1         | Transformar documento | Cree el archivo XML de factura electrónica en formato **FatturaPA**. |
    | 2         | Firmar documento      | Aplicar una firma digital al archivo XML.             |

4. Seleccione la pestaña **Reglas de aplicabilidad** para ver y mantener las reglas de aplicabilidad. Las reglas de aplicabilidad definen el contexto en el que se ejecutará la acción.

    ![Pestaña Reglas de aplicabilidad](media/e-Invoicing-services-get-started-ITA-Select-Applicability-rules.png)

5. Seleccione la pestaña **Variables** para ver y mantener las variables.

    ![Pestaña Variables](media/e-Invoicing-services-get-started-ITA-Select-Variables.png)

6. Defina las variables públicas necesarias para ejecutar las acciones.

### <a name="configure-the-project-invoice-feature-setup"></a>Configurar la función de factura de proyecto 

Los pasos y ajustes necesarios para configurar la función **Factura de proyecto** son muy similares a los pasos y configuraciones de la configuración de la función **Factura de venta**. Cuando trabaje con facturas de proyectos, consulte los procedimientos para facturas de ventas.

## <a name="assign-the-e-invoicing-feature-to-the-environment"></a>Asignar la función de facturación electrónica al entorno

1. En la página **Funciones de facturación electrónica**, en la pestaña **Entornos**, seleccione **Habilitar**.
2. En el campo **Entorno**, seleccione el entorno.
3. En el campo **Válido desde**, seleccione la fecha en que el nuevo entorno debe entrar en vigencia.
4. Seleccione **Habilitar**. 

![Habilitación del entorno de facturación electrónica](media/e-Invoicing-services-get-started-ITA-Enable-e-Invoicing-environment.png)

## <a name="publish-the-e-invoicing-feature"></a>Publicar la función de facturación electrónica

Puede publicar la función de facturación electrónica cambiando el estado de la versión a **Terminado** o **Publicado**.

### <a name="change-the-version-status-to-completed"></a>Cambiar el estado de la versión a Completado

1. En la página **Funciones de facturación electrónica**, en la pestaña **Versiones**, seleccione la versión de la función de facturación electrónica que tiene un estado de **Borrador**.
2. Seleccione **Cambiar estado\> Completada**. 

### <a name="change-the-version-status-to-published"></a>Cambiar el estado de la versión a Publicado 

1. En la página **Funciones de facturación electrónica**, en la pestaña **Versiones**, seleccione la versión de la función de facturación electrónica que tiene un estado **Completado**.
2. Seleccione **Cambiar estado \> Publicar**.

![Cambiar el estado de la función de facturación electrónica](media/e-Invoicing-services-get-started-ITA-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance"></a>Configurar la integración del complemento de facturación electrónica en Finance

Durante la configuración de Finance, completará estas tareas:

1. Importe el modelo de datos ER, el mapeo del modelo de datos ER y las configuraciones de contexto para facturas electrónicas FatturaPA.
2. Configure el certificado necesario para firmar digitalmente facturas electrónicas italianas.

### <a name="import-the-er-data-model-data-model-mapping-and-formats"></a>Importe el modelo de datos ER, el mapeo del modelo de datos y los formatos

1. En el espacio de trabajo **Informes electrónicos**, verifique que el proveedor de configuración **Servicio de documentos comerciales** está establecido en **Activo**.
2. Seleccione **Repositorios**.
3. Seleccione **Recurso global \> Abierto**.
4. Importar **Modelo de factura**, **Mapeo del modelo de factura** y **Modelo de contexto de factura de cliente**.

#### <a name="turn-on-the-feature-for-exporting-customer-electronic-invoices-for-italy"></a>Active la función para exportar facturas electrónicas de clientes para Italia

1. Vaya a **Administración de la organización \> Configuración \> Parámetros de documentos electrónicos**.
2. En la pestaña **Características**, seleccione la casilla **Habilitar** en la fila de la referencia de característica **IT00036**.

![Activar la función FatturaPA](media/e-Invoicing-services-get-started-ITA-Enable-FatturaPA-feature.png)

#### <a name="configure-electronic-documents"></a>Configurar documentos electrónicos

1. Vaya a **Administración de la organización \> Configuración \> Parámetros de documentos electrónicos**.
2. En la pestaña **Documento electrónico**, seleccione **Agregar** e introduzca las tablas necesarias para generar facturas electrónicas italianas:

    - **Nombre de la tabla**: diario de facturas del cliente
    - **Nombre de la tabla**: factura del proyecto

3. Para cada tabla, defina un contexto de documento relacionado:

    - Para **Diario de facturas del cliente**, seleccione **Contexto de la factura del cliente**.
    - Para **Factura del proyecto**, seleccione **Contexto de la factura del proyecto**.

![Configuración de tipos de respuesta](media/e-Invoicing-services-get-started-ITA-Set-up-response-types.png)

## <a name="electronic-invoice-processing"></a>Procesamiento de facturas electrónicas

Durante el procesamiento en Finance, completará estas tareas:

1. Genere facturas electrónicas italianas a través del complemento de facturación electrónica
2. Ver los registros de ejecución y revisar los resultados del procesamiento.

### <a name="generate-electronic-invoices"></a>Generar facturas electrónicas

Después de activar la función **Integración adicional configurable de facturación electrónica** y activar la característica **IT00036**, el antiguo proceso de Finance para generar facturas electrónicas italianas ya no se puede utilizar. Es reemplazado por un nuevo proceso que se llama **Presentar documentos electrónicos**.

Puede enviar los documentos manualmente, según su demanda de documentos de factura electrónica.

> [!NOTE]
> Antes de continuar, verifique que se haya completado la configuración necesaria para las facturas electrónicas italianas. Para obtener más información, consulte [Facturas electrónicas de cliente](https://docs.microsoft.com/dynamics365/finance/localizations/emea-ita-e-invoices). Tenga en cuenta que algunos de los pasos de configuración que se describen en ese tema pueden no estar disponibles debido a la activación del complemento de facturación electrónica.

1. Vaya a **Administración de la organización \> Periódico \> Documentos electrónicos \> Presentar documentos electrónicos**.
2. Para el primer envío de cualquier documento, establezca la opción **Reenviar documentos** en **No**. Si debe volver a enviar un documento a través del servicio, configure esta opción en **Sí**.
3. En la ficha desplegable **Registros para incluir**, seleccione **Filtrar** para abrir el cuadro de diálogo **Investigación**, donde puede crear una consulta para seleccionar los documentos para su envío.

![Cuadro de diálogo Enviar documentos electrónicos](media/e-Invoicing-services-get-started-ITA-Submission-form.png)

#### <a name="filter-query"></a>Consulta de filtro

1. En el cuadro de diálogo **Investigación**, configure las condiciones de filtrado para facturas de venta y facturas de proyecto, o deje las condiciones en blanco para incluir todas las facturas no enviadas.

    ![Configurar criterios de filtro de envío](media/e-Invoicing-services-get-started-ITA-Set-up-Submission-filter-criteria.png)

2. Seleccione **Aceptar** para cerrar el cuadro de diálogo **Consulta**.
3. Seleccione **Aceptar** para enviar los documentos seleccionados.

> ![NOTA] Durante su primer intento de enviar un documento a través del servicio, se le pedirá que confirme la conexión con el complemento de facturación electrónica. Seleccione **Haga clic aquí para conectar al servicio de envío de documentos electrónicos**.

#### <a name="view-submission-logs"></a>Ver registros de envío

Puede ver los registros de envío de todos los documentos enviados.

1. Vaya a **Administración de la organización \> Periódico \> Documentos electrónicos \> Registro de envío de documentos electrónicos**.
2. En el campo **Tipo de documento**, seleccione **Diario de facturas del cliente** o **Factura de proyecto** para filtrar los documentos electrónicos requeridos.

    ![Seleccionar un tipo de documento para ver los registros de envío](media/e-Invoicing-services-get-started-ITA-Select-Document-type-for-viewing-submission-log.png)

    El valor que se muestra en la columna **Estado de presentación** representa el estado del proceso de envío. Indica si el proceso se ejecutó según lo configurado y si se requieren acciones adicionales.

3. En el panel de acciones, seleccione **Consultas \> Detalles de envío** para ver los detalles de los registros de ejecución del envío.

    ![Ver los detalles del registro de envío](media/e-Invoicing-services-get-started-ITA-View-Submission-log-details.png)

4. En la ficha desplegable **Procesamiento de acciones**, puede ver el registro de ejecución de las acciones configuradas en la versión de función que se configuró en RCS. La columna **Estado** muestra si la acción se ejecutó correctamente.
5. En la ficha desplegable **Archivos de acción**, puede ver los archivos intermedios que se generaron durante la ejecución de las acciones. Puede elegir **Ver** para descargar el archivo XML de salida en formato **FatturaPA** y ver su contenido.

## <a name="related-topics"></a>Temas relacionados

- [Descripción general del complemento de facturación electrónica](e-invoicing-service-overview.md)
- [Introducción al complemento de facturación electrónica](e-invoicing-get-started.md)
- [Configurar el complemento de facturación electrónica](e-invoicing-setup.md)
