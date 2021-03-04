---
title: Configurar informes electrónicos (ER) para proporcionar datos a Power BI
description: Este tema explica cómo puede usar su configuración de informes electrónicos (ER) para organizar la transferencia de datos de la instancia a los servicios de Power BI.
author: NickSelin
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 34d4ad9106b2751c77db4fd03d83932e587a5332
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680129"
---
# <a name="configure-electronic-reporting-er-to-pull-data-into-power-bi"></a>Configurar informes electrónicos (ER) para proporcionar datos a Power BI

[!include [banner](../includes/banner.md)]

Este tema explica cómo puede usar su configuración de informes electrónicos (ER) para organizar la transferencia de datos de la instancia a los servicios de Power BI. Como ejemplo, este tema utiliza transacciones Intrastat como datos empresariales que se deben transferir. La vista de mapa de Power BI usa estos datos de transacción de Intrastat para mostrar una visión para el análisis de actividades de importación/exportación de la empresa en el informe de Power BI.

## <a name="overview"></a>Información general

Microsoft Power BI es una recopilación de servicios de desarrollo de programas informáticos, aplicaciones y conectores que funcionan conjuntamente para activar fuentes externas de datos en conocimientos coherentes, visualmente envolventes e interactivos. Los informes electrónicos (ER) permiten a los usuarios configurar con facilidad orígenes de datos y organizar la transferencia de datos de la aplicación a Power BI. Los datos se transfieren como archivos en el formato de la hoja de cálculo de OpenXML (archivo del libro de Microsoft Excel). Los archivos transferidos se almacenan en un servidor de Microsoft SharePoint Server que se ha configurado para ese propósito. Los archivos almacenados se usan en Power BI para realizar los informes que contengan las vistas (tablas, gráficos, mapas, etc.). Los informes de Power BI se comparten con usuarios de Power BI, y se accede a ellos desde paneles de Power BI y páginas de la aplicación. En este tema se describen las siguientes tareas:

- Configurar Microsoft Dynamics 365 Finance.
- Prepare la configuración del formato de ER para recopilar datos de la aplicación Finance.
- Configurar el entorno de ER para transferir datos a Power BI.
- Usar los datos transferidos para crear un informe de Power BI.
- Haga que el informe de Power BI sea accesible en Finance.

## <a name="prerequisites"></a>Requisitos previos
Para completar el ejemplo de este tema, debe tener el acceso siguiente:

- Acceso para uno de los roles siguientes:

    - Desarrollador de informes electrónicos
    - Consultor funcional de informes electrónicos
    - Administrador del sistema

- Acceso al Servidor de SharePoint configurado para su uso con la aplicación.
- Acceso al marco Power BI

## <a name="configure-document-management-parameters"></a>Confugurar los parámetros de gestión de documentos
1. En la página de **Parámetros de gestión de documentos**, configure el acceso a SharePoint Server que se usará en la empresa en la que se firman (la empresa DEMF de este ejemplo).
2. Pruebe la conexión a SharePoint Server para asegurarse de que se le ha concedido el acceso.

    [![Página Parámetros de gestión de documentos](./media/ger-power-bi-sharepoint-server-setting-1024x369.png)](./media/ger-power-bi-sharepoint-server-setting.png)

3. Abra el sitio de SharePoint configurado. Cree una nueva carpeta donde el ER guardará los archivos Excel que tienen los datos empresariales que los informes de Power BI requieren como origen de los conjuntos de datos de Power BI.
4. En la página **Tipos de documento**, cree un nuevo tipo de documento que se usará para tener acceso a la carpeta de SharePoint que acaba de crear. Escriba **Archivo** en el campo **Grupo** y **SharePoint** en el campo **Ubicación**, y a continuación escriba la dirección de la carpeta de SharePoint.

    [![Página de tipos de documento](./media/ger-power-bi-sharepoint-document-type-1024x485.png)](./media/ger-power-bi-sharepoint-document-type.png)

## <a name="configure-er-parameters"></a>Configurar los parámetros de ER
1. En el área de trabajo de **Informes electrónicos**, haga clic en el vínculo de **Parámetros de informes electrónicos**.
2. En la ficha **Datos adjuntos**, seleccione el tipo de documento **Archivo** para todos los campos.
3. En el área de trabajo de **Informes electrónicos**, active al proveedor requerido haciendo clic en **Establecer como activo**. Para obtener más información, consulte la guía de tareas **Seleccionar proveedor de servicios ER**.

## <a name="use-an-er-data-model-as-the-source-of-data"></a>Use un modelo de datos de ER como origen de datos
Debe tener un modelo de datos de ER como origen de los datos empresariales que se usarán en los informes de Power BI. Este modelo de datos se carga desde el almacén de configuraciones de ER. Para obtener más información, consulte [Descargar las configuraciones de informes electrónicos de servicios del ciclo de vida](download-electronic-reporting-configuration-lcs.md), o consulte la guía de tareas **Importación de una configuración ER de Lifecycle Services**. Seleccione **Intrastat** como modelo de datos que se cargará desde el almacén de las configuraciones de ER seleccionado. (En este ejemplo se usa la versión 1 del modelo). Después puede tener acceso a la configuración del modelo de ER **Intrastat** en la página **Configuraciones**.

[![Página Configuraciones](./media/ger-power-bi-data-model-1024x371.png)](./media/ger-power-bi-data-model.png)

## <a name="design-an-er-format-configuration"></a>Diseñar una configuración del formato de ER
Debe crear una nueva configuración del formato de ER que use el modelo de datos **Intrastat** como origen de datos empresariales. Esta configuración del formato debe generar resultados de salida como documentos electrónicos en formato OpenXML (archivo de Excel). Para obtener más información, consulte la guía de tareas **Crear una configuración de ER para informes en formato OPENXML**. Asignar un nombre a la nueva configuración de **Actividades de importación / exportación**, como se muestra en la siguiente ilustración. Use el archivo de Excel [Datos de ER: detalles de importación y exportación](https://go.microsoft.com/fwlink/?linkid=845208) como plantilla cuando diseñe el formato de ER. (Para obtener más información sobre cómo importar una plantilla de formato, consulte la guía de tareas.)

[![Configuración de actividades de importación/exportación](media/ger-power-bi-format-configuration.png)](media/ger-power-bi-format-configuration.png)

Para modificar la configuración del formato **Actividades de importación / exportación**, siga estos pasos.

1. Haga clic en **Diseñador**.
2. En la ficha **Formato**, asigne un nombre al elemento del archivo para este formato **Archivo de salida de Excel**.

    [![Elemento de archivo de salida de Excel](./media/ger-power-bi-format-configuration-file-element-name-1024x395.png)](./media/ger-power-bi-format-configuration-file-element-name.png)

3. En la ficha **Asignación**, especifique el nombre del archivo de Excel que se generará siempre que se ejecute este formato. Configurar la expresión relacionada para devolver el valor **Detalles de importación y exportación** (la extensión del nombre de archivo .xlsx se añadirá automáticamente).

    [![Diseñador de formato](./media/ger-power-bi-format-configuration-output-file-name-1024x396.png)](./media/ger-power-bi-format-configuration-output-file-name.png)

4. Agregar un artículo del nuevo origen de datos para este formato. (Esta enumeración se requiere para enlazar datos en el futuro.)

    1. Asignar un nombre al origen de datos **direction\_enum**.
    2. Seleccione **Enumeración del modelo de datos** como el tipo de origen de datos.
    3. Consulte la enumeración del modelo de datos de **Dirección**.

    [![direction_enum](./media/ger-power-bi-format-configuration-mapping-added-enum-1024x454.png)](./media/ger-power-bi-format-configuration-mapping-added-enum.png)

5. Complete el enlazado de los elementos del modelo de datos de **Intrastat** y los elementos del formato diseñado, como se muestra en la siguiente ilustración.

    [![Completar el enlazado](./media/ger-power-bi-format-configuration-mapping-details-1024x454.png)](./media/ger-power-bi-format-configuration-mapping-details.png)

Una vez que se ejecute, el formato de ER genera el resultado de salida en formato Excel. Envía los detalles de las transacciones Intrastat al resultado de salida, y los separa como transacciones que describen actividades de importación o exportación. Haga clic en **Ejecutar** para probar el nuevo formato de ER para la lista de transacciones Intrastat en la página **Intrastat** (**Impuestos** &gt; **Declaraciones** &gt; **Comercio exterior** &gt; **Intrastat**).

[![Página Intrastat](./media/ger-power-bi-format-test-run-transactions-1024x322.png)](./media/ger-power-bi-format-test-run-transactions.png)

Se generará el siguiente resultado de salida. El archivo se denomina **Detalles de importación y exportación.xlsx**, según haya especificado en las configuraciones de formato.

[![Detalles de importación y exportación.xlsx](./media/ger-power-bi-format-test-run-output-1024x472.png)](./media/ger-power-bi-format-test-run-output.png)

## <a name="configure-the-er-destination"></a>Configurar el destino de ER
Debe configurar el marco de ER para enviar el resultado de salida de la nueva configuración del formato de ER de manera especial.

- El resultado de salida se debe enviar a la carpeta del SharePoint Server seleccionado.
- Cada ejecución de la configuración del formato debe crear una versión nueva del mismo archivo de Excel.

En la página **Informes electrónicos** (**Gestión de la organización** &gt; **Informes electrónicos**), haga clic en el elemento **Destino de informe electrónico**, y añada un nuevo destino. En el campo **Referencia**, seleccione la configuración del formato **Actividades de importación / exportación** que creó anteriormente. Siga estos pasos para agregar un nuevo registro de destino de archivo para la referencia.

1. En el campo **Nombre**, escriba el título del destino del archivo.
2. En el campo **Nombre de archivo**, seleccione el nombre **Archivo de salida de Excel** del componente del formato de archivo de Excel.

Haga clic en el botón de **Ajustes** para el nuevo registro de destino. A continuación, en el cuadro de diálogo **Ajustes de destino**, siga estos pasos.

1. En la ficha **Power BI**, establezca la opción **Habilitado** a **Sí**.
2. En el campo **SharePoint**, seleccione el tipo de documento **Compartido** que creó anteriormente.

## <a name="schedule-execution-of-the-configured-er-format"></a>Programe la ejecución del formato de ER configurado
1. En la página **Configuraciones** (**Gestión de la organización** &gt; **Informes electrónicos** &gt; **Configuraciones**), en el árbol de configuraciones, seleccione la configuración de **Actividades de importación / exportación** que creó anteriormente.
2. Cambiar el estado de la versión 1.1 de **Borrador** a **Completado** para hacer que este formato esté disponibles para su uso.

    [![Página Configuraciones](./media/ger-power-bi-format-configuration-complete-1024x401.png)](./media/ger-power-bi-format-configuration-complete.png)

3. Seleccione la versión completada de la configuración de **Actividades de importación / exportación**, y haga clic en **Ejecutar**. Tenga en cuenta que el destino configurado se aplica al resultado de salida que se genera en formato Excel.
4. Configure la opción **Procesamiento por lotes** a **Sí** para ejecutar este informe modo desatendido.
5. Haga clic en **Periodicidad** para programar la frecuencia necesaria de esta ejecución de lotes. La periodicidad define la frecuencia con la que los datos actualizados se transfieren a Power BI.

    [![Cuadro de diálogo Parámetros de notificación electrónica](./media/ger-power-bi-format-configuration-run-to-schedule-1024x413.png)](./media/ger-power-bi-format-configuration-run-to-schedule.png)

6. Una vez se haya configurado, puede encontrar el trabajo de ejecución de informes de ER en la página **Trabajos por lotes** (**Gestión del sistema &gt; Preguntas &gt; Trabajos por lotes**).

    [![Página Trabajos por lotes](./media/ger-power-bi-format-configuration-running-job-1024x410.png)](./media/ger-power-bi-format-configuration-running-job.png)

7. Cuando este trabajo se ejecuta por primera vez, el destino crea un nuevo archivo de Excel con el nombre configurado en la carpeta de SharePoint seleccionada. Por cada hora posterior en la que se ejecuta el trabajo, el destino crea una versión nueva de este archivo de Excel.

    [![Nueva versión del archivo Excel](./media/ger-power-bi-output-file-in-sharepoint-server-folder-2-1024x412.png)](./media/ger-power-bi-output-file-in-sharepoint-server-folder-2.png)

## <a name="create-a-power-bi-dataset-by-using-the-output-result-of-the-er-format"></a>Crear un conjunto de datos de Power BI mediante el resultado de salida de formato de ER
1. Iniciar sesión en Power BI, y abrir un grupo existente de Power BI (área de trabajo) o crear un grupo nuevo. Haga clic en **Agregar** en **Archivos** en la sección **Importar o Conectar a los datos**, o en el símbolo más (**+**) situado al lado de **Conjuntos de datos** del panel izquierdo.

    [![Creación de un conjunto de datos](./media/ger-power-bi-add-dataset-1024x524.png)](./media/ger-power-bi-add-dataset.png)

2. Seleccione la opción **SharePoint - Sitios del equipo** y especifique la ruta del SharePoint Server que utiliza (`https://ax7partner.litware.com` en nuestro ejemplo).
3. Busque la carpeta **/Documentos compartidos/Datos GER/PowerBI** y seleccione el archivo de Excel que ha creado como origen de los datos para el nuevo conjunto de datos de Power BI.

    [![Selección del archivo de Excel](./media/ger-power-bi-add-dataset-select-excel-file-1024x522.png)](./media/ger-power-bi-add-dataset-select-excel-file.png)

4. Haga clic en **Conectar**, y a continuación, haga clic en **Importar**. Se crea un conjunto de datos nuevos que se basa en el archivo de Excel seleccionado. El conjunto de datos también puede añadirse automáticamente al panel recién creado.

    [![Conjunto de datos en el panel](./media/ger-power-bi-added-dataset-1024x489.png)](./media/ger-power-bi-added-dataset.png)

5. Configurar la programación de actualización para que este conjunto de datos pueda forzar una actualización periódica. Las actualizaciones periódicas habilitan el consumo de nuevos datos empresariales que vengan de la ejecución periódica del informe de ER a través de nuevas versiones del archivo de Excel que se crean en el SharePoint Server.

## <a name="create-a-power-bi-report-by-using-the-new-dataset"></a>Crear un informe de Power BI mediante el conjunto de datos nuevos
1. Haga clic en el conjunto de datos de Power BI **Detalles de importación y exportación** que ha creado.
2. Configure la vista. Por ejemplo, seleccione la vista **Mapa lleno**, y configúrelo de la manera siguiente:

    - Asignar el campo de conjunto de datos **CountryOrigin** al campo **Ubicación** de la vista del mapa.
    - Asignar el campo de conjunto de datos **Cantidad** al campo **Saturación de color** de la vista del mapa.
    - Agregar los campos de conjunto de datos de **Actividad** y **Año** a la recopilación de campos de **Filtros** de la vista de mapa.

3. Guarde el informe de Power BI como **Informe de detalles de importación y exportación**.

    [![Informe de detalles de importación y exportación](./media/ger-power-bi-added-report-1024x498.png)](./media/ger-power-bi-added-report.png)

    Tenga en cuenta que el mapa muestra los países/regiones mencionados en el archivo de Excel (Austria y Suiza en este ejemplo). Estos países/regiones se colorean para mostrar la proporción de importes facturados para cada uno.

4. Actualizar la lista de transacciones Intrastat. Se ha añadido la transacción de exportación que se ha originado desde Italia.

    [![Lista de transacciones Intrastat](./media/ger-power-bi-new-run-new-transaction-1024x321.png)](./media/ger-power-bi-new-run-new-transaction.png)

5. Espere para la siguiente ejecución programada del informe de ER y la siguiente actualización programada del conjunto de datos de Power BI. A continuación revise el informe de Power BI (seleccione solo para mostrar las transacciones de importación). El mapa actualizado ahora muestra Italia.

    [![Mapa actualizado](./media/ger-power-bi-new-run-new-map-1024x511.png)](./media/ger-power-bi-new-run-new-map.png)

## <a name="access-power-bi-report-in-finance"></a>Acceder al informe de Power BI en Finance
Configurar la integración con Power BI. Para obtener más información, consulte [Configurar la integración de Power BI para espacios de trabajo](configure-power-bi-integration.md).

1. En la página del área de trabajo de **Informes electrónicos** que admite la integración de Power BI (**Gestión de la organización** &gt; **Áreas de trabajo** &gt; **Área de trabajo de informes electrónicos**), haga clic en **Opciones** &gt; **Abrir catálogo de informes**.
2. Seleccione el informe **Detalles de exportación e importación** de Power BI que ha creado, para mostrar dicho informe como un artículo de acción en la página seleccionada.
3. Haga clic en el elemento de acción para abrir la página que muestra el informe que ha diseñado en Power BI.

    [![Informe de detalles de importación y exportación](./media/ger-power-bi-review-bi-report-in-ax-form-1024x586.png)](./media/ger-power-bi-review-bi-report-in-ax-form.png)

## <a name="additional-resources"></a>Recursos adicionales

[Destinos de informes electrónicos (ER)](electronic-reporting-destinations.md)

[Visión general de los informes electrónicos (ER)](general-electronic-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]