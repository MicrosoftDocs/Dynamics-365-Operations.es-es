---
title: "Informes electrónico para proporcionar el BI de la potencia con datos de las Dynamics 365 para las operaciones"
description: "Este tema explica cómo puede usar su configuración de informes electrónicos (ER) para organizar la transferencia de datos de la instancia de Dynamics 365 for Operations a los servicios de Power BI. Como ejemplo, este tema utiliza transacciones Intrastat como datos empresariales que se deben transferir. La vista de mapa de Power BI usa estos datos de transacción de Intrastat para mostrar una visión para el análisis de actividades de importación/exportación de la empresa en el informe de Power BI."
author: kfend
manager: AnnBe
ms.date: 2016-10-31 13 - 22 - 29
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Operations, Core
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: ed0192c44b6d7e88120c64e539ebb0ac3b379831
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-electronic-reporting-to-provide-power-bi-with-data-from-dynamics-365-for-operations"></a>Informes electrónico para proporcionar el BI de la potencia con datos de las Dynamics 365 para las operaciones

Este tema explica cómo puede usar su configuración de informes electrónicos (ER) para organizar la transferencia de datos de la instancia de Dynamics 365 for Operations a los servicios de Power BI. Como ejemplo, este tema utiliza transacciones Intrastat como datos empresariales que se deben transferir. La vista de mapa de Power BI usa estos datos de transacción de Intrastat para mostrar una visión para el análisis de actividades de importación/exportación de la empresa en el informe de Power BI.

<a name="overview"></a>Visión general
--------

Microsoft Power BI es una recopilación de servicios de desarrollo de programas informáticos, aplicaciones y conectores que funcionan conjuntamente para activar fuentes externas de datos en conocimientos coherentes, visualmente envolventes e interactivos. Los informes electrónicos (ER) permiten a los usuarios de Microsoft Dynamics 365 for Operations configurar fácilmente los orígenes de los datos y organizar la transferencia de datos de Dynamics 365 for Operations a Power BI. Los datos se transfieren como archivos en el formato de la hoja de cálculo de OpenXML (archivo del libro de Microsoft Excel). Los archivos transferidos se almacenan en un Servidor de Microsoft SharePoint que se ha configurado para ese propósito. Los archivos almacenados se usan en Power BI para realizar los informes que contengan las vistas (tablas, gráficos, mapas, etc.). Los informes de Power BI se comparten con usuarios de Power BI, y se accede a ellos desde paneles de Power BI y páginas de Dynamics 365 for Operations. En este tema se describen las siguientes tareas:

-   Configurar Dynamics 365 for Operations.
-   Preparar la configuración del formato de ER para recopilar datos de Dynamics 365 for Operations.
-   Configurar el entorno de ER para transferir datos a Power BI.
-   Usar los datos transferidos para crear un informe de Power BI.
-   Hacer que el informe de Power BI sea accesible en Dynamics 365 for Operations.

## <a name="prerequisites"></a>Requisitos previos
Para completar el ejemplo de este tema, debe tener el acceso siguiente:

-   Acceso a Dynamics 365 for Operations para uno de los roles siguientes:
    -   Desarrollador de informes electrónicos
    -   Consultor funcional de informes electrónicos
    -   Administrador del sistema
-   Acceso al Servidor de SharePoint configurado para su uso con Dynamics 365 for Operations
-   Acceso al marco de trabajo de Power BI

## <a name="configure-document-management-parameters"></a>Confugurar los parámetros de gestión de documentos
1.  En la página de **Parámetros de gestión de documentos**, configure el acceso al Servidor de SharePoint que se usará en la empresa en la que se firman (la empresa DEMF de este ejemplo).
2.  Pruebe la conexión al Servidor de SharePoint para asegurarse de que se le ha concedido el acceso. [página de los formularios document sobre el![] (. /media/ger-power-bi-sharepoint-server-setting-1024x369.png])(. /media/ger-power-bi-sharepoint-server-setting.png)
3.  Abra el sitio de SharePoint configurado. Cree una nueva carpeta donde el ER guardará los archivos Excel que tienen los datos empresariales que los informes de Power BI requieren como origen de los conjuntos de datos de Power BI.
4.  En Dynamics 365 for Operations, en la página **Tipos de documento**, cree un nuevo tipo de documento que se usará para tener acceso a la carpeta de SharePoint que acaba de crear. Escriba **Archivo** en el campo **Grupo** y **SharePoint** en el campo **Ubicación**, y a continuación escriba la dirección de la carpeta de SharePoint. [página de tipos de documentos![] (. /media/ger-power-bi-sharepoint-document-type-1024x485.png])(. /media/ger-power-bi-sharepoint-document-type.png)

## <a name="configure-er-parameters"></a>Configurar los parámetros de ER
1.  En el área de trabajo de **Informes electrónicos**, haga clic en el vínculo de **Parámetros de informes electrónicos**.
2.  En la ficha **Datos adjuntos**, seleccione el tipo de documento **Archivo** para todos los campos.
3.  En el área de trabajo de **Informes electrónicos**, active al proveedor requerido haciendo clic en **Establecer como activo**. Para obtener más información, consulte la guía de tareas **Seleccionar proveedor de servicios ER**.

## <a name="use-an-er-data-model-as-the-source-of-data"></a>Use un modelo de datos de ER como origen de datos
Debe tener un modelo de datos de ER como origen de los datos empresariales que se usarán en los informes de Power BI. Este modelo de datos se carga desde el almacén de configuraciones de ER. Para obtener más información, consulte [Descargar las configuraciones de informes electrónicos de servicios del ciclo de vida](download-electronic-reporting-configuration-lcs.md), o consulte la guía de tareas **Importación de una configuración ER de Lifecycle Services**. Seleccione **Intrastat **como modelo de datos que se cargará desde el almacén de las configuraciones de ER seleccionado. (En este ejemplo, la versión 1 del modelo se usa). A continuación puede tener acceso ** Intrastat ** a la configuración de modelo del ER ** en las configuraciones ** la página. [página de la configuración![] (. /media/ger-power-bi-data-model-1024x371.png])(. /media/ger-power-bi-data-model.png)

## <a name="design-an-er-format-configuration"></a>Diseñar una configuración del formato de ER
Debe crear una nueva configuración del formato de ER que use el modelo de datos **Intrastat** como origen de datos empresariales. Esta configuración del formato debe generar resultados de salida como documentos electrónicos en formato OpenXML (archivo de Excel). Para obtener más información, consulte la guía de tareas **Crear una configuración de ER para informes en formato OPENXML**. Asignar un nombre a la nueva configuración de **Actividades de importación / exportación**, como se muestra en la siguiente ilustración. Use el archivo de Excel [Datos de ER: detalles de importación y exportación](https://go.microsoft.com/fwlink/?linkid=845208) como plantilla cuando diseñe el formato de ER. (Para obtener más información sobre cómo importar una plantilla de formato, juegue la guía de la tarea.) [] configuración de las actividades de importación o la exportación![medios (/) ger-power-bi-format-configuration.png]medios (/) ger-power-bi-format-configuration.png ** para modificar las actividades de importación o la exportación ** de formato a la configuración, siga estos pasos.

1.  Haga clic en **Diseñador**.
2.  En la ficha **Formato**, asigne un nombre al elemento del archivo para este formato **Archivo de salida de Excel**. [artículo del archivo![salida![Excel (]. /media/ger-power-bi-format-configuration-file-element-name-1024x395.png])(. /media/ger-power-bi-format-configuration-file-element-name.png)
3.  En la ficha **Asignación**, especifique el nombre del archivo de Excel que se generará siempre que se ejecute este formato. Configurar la expresión relacionada para devolver el valor **Detalles de importación y exportación** (la extensión del nombre de archivo .xlsx se añadirá automáticamente). [![Format designer](./media/ger-power-bi-format-configuration-output-file-name-1024x396.png)](./media/ger-power-bi-format-configuration-output-file-name.png)
4.  Agregar un artículo del nuevo origen de datos para este formato. (Esta enumeración se requiere para enlazar datos en el futuro.)
    1.  Denomina el origen de datos ** enumeración\_de la dirección **.
    2.  Seleccione **Enumeración del modelo de datos** como el tipo de origen de datos.
    3.  Consulte la enumeración del modelo de datos de **Dirección**.

    [enumeración\_de la dirección![] (. /media/ger-power-bi-format-configuration-mapping-added-enum-1024x454.png])(. /media/ger-power-bi-format-configuration-mapping-added-enum.png)
5.  Complete el enlazado de los elementos del modelo de datos de **Intrastat** y los elementos del formato diseñado, como se muestra en la siguiente ilustración. [![que completa el atascamiento] (. /media/ger-power-bi-format-configuration-mapping-details-1024x454.png])(. /media/ger-power-bi-format-configuration-mapping-details.png)

Una vez que se ejecute, el formato de ER genera el resultado de salida en formato Excel. Envía los detalles de las transacciones Intrastat al resultado de salida, y los separa como transacciones que describen actividades de importación o exportación. Haga clic en ejecución ** ** para probar el nuevo formato de ER para la lista de transacciones Intrastat en ** Intrastat ** la página (Tax ** ** &gt; ** declaraciones ** &gt; ** comercio exterior ** &gt; ** Intrastat **). [página![Intrastat (]. /media/ger-power-bi-format-test-run-transactions-1024x322.png])(. Se genera /media/ger-power-bi-format-test-run-transactions.png) el resultado del siguiente resultado. El archivo se denomina **Detalles de importación y exportación.xlsx**, según haya especificado en las configuraciones de formato. [importación y exportación details.xlsx de![] (. /media/ger-power-bi-format-test-run-output-1024x472.png])(. /media/ger-power-bi-format-test-run-output.png)

## <a name="configure-the-er-destination"></a>Configurar el destino de ER
Debe configurar el marco de ER para enviar el resultado de salida de la nueva configuración del formato de ER de manera especial.

-   El resultado de salida se debe enviar a la carpeta del Servidor de SharePoint seleccionado.
-   Cada ejecución de la configuración del formato debe crear una versión nueva del mismo archivo de Excel.

En ** informe de errores electrónico ** la página (** Administración de organización ** &gt; ** informe de errores electrónico **), haga clic en ** destino electrónico del informe de errores ** el artículo, y agregar un nuevo destino. En el campo **Referencia**, seleccione la configuración del formato **Actividades de importación / exportación** que creó anteriormente. Siga estos pasos para agregar un nuevo registro de destino de archivo para la referencia.

1.  En el campo **Nombre**, escriba el título del destino del archivo.
2.  En el campo **Nombre de archivo**, seleccione el nombre **Archivo de salida de Excel** del componente del formato de archivo de Excel.

Haga clic en el botón de **Ajustes** para el nuevo registro de destino. A continuación, en el cuadro de diálogo **Ajustes de destino**, siga estos pasos.

1.  En la ficha **Power BI**, establezca la opción **Habilitado** a **Sí**.
2.  En el campo **SharePoint**, seleccione el tipo de documento **Compartido** que creó anteriormente.

## <a name="schedule-execution-of-the-configured-er-format"></a>Programe la ejecución del formato de ER configurado
** En las configuraciones ** pagine (** Administración de organización ** &gt; ** informe de errores electrónico ** &gt; ** las configuraciones **), en el árbol de las configuraciones, seleccione ** las actividades de importación o la exportación ** la configuración que ha creado anterior. Cambiar el estado de la versión 1.1 de **Borrador** a **Completado** para hacer que este formato esté disponibles para su uso. [página de la configuración![] (. /media/ger-power-bi-format-configuration-complete-1024x401.png])(. /media/ger-power-bi-format-configuration-complete.png) Seleccionar la versión completado ** las actividades de importación o la exportación ** de la configuración, haga clic en ejecución ** **. Tenga en cuenta que el destino configurado se aplica al resultado de salida que se genera en formato Excel. Configure la opción **Procesamiento por lotes** a **Sí** para ejecutar este informe modo desatendido. Haga clic en **Periodicidad** para programar la frecuencia necesaria de esta ejecución de lotes. La periodicidad define la frecuencia con la que los datos actualizados se transfieren de Dynamics 365 for Operations a Power BI. [cuadro de diálogo electrónico de los parámetros del informe![] (. /media/ger-power-bi-format-configuration-run-to-schedule-1024x413.png])(. /media/ger-power-bi-format-configuration-run-to-schedule.png) Después de haber configurado, puede encontrar el trabajo de ejecución de informes del ER ** en los trabajos por lotes ** la página (** los trabajos por lotes de las preguntas de administración &gt; del &gt; sistema **). [página de los trabajos por lotes de![] (. /media/ger-power-bi-format-configuration-running-job-1024x410.png])(. /media/ger-power-bi-format-configuration-running-job.png) Cuando el trabajo se ejecuta por primera vez, el destino cree un nuevo archivo de Excel con el nombre configurado en la carpeta seleccionado de SharePoint. Por cada hora posterior en la que se ejecuta el trabajo, el destino crea una versión nueva de este archivo de Excel. [nueva versión![del archivo de Excel (]. /media/ger-power-bi-output-file-in-sharepoint-server-folder-2-1024x412.png])(. /media/ger-power-bi-output-file-in-sharepoint-server-folder-2.png)

## <a name="create-a-power-bi-dataset-by-using-the-output-result-of-the-er-format"></a>Crear un conjunto de datos de Power BI mediante el resultado de salida de formato de ER
Iniciar sesión en Power BI, y abrir un grupo existente de Power BI (área de trabajo) o crear un grupo nuevo. O bien haga clic ** agregue ** en ** los archivos en ** ** la importación o conectarse a los datos ** la sección, o haga clic en el signo más (**+**) situado junto a ** de los conjuntos de datos ** en el panel izquierdo. [![que crea un conjunto de datos (]. /media/ger-power-bi-add-dataset-1024x524.png])(. /media/ger-power-bi-add-dataset.png) ** Seleccionar los sitios Web del grupo de SharePoint ** la opción y, a continuación especifique la ruta de SharePoint Server que utiliza (** https://ax7partner.spoppe.com** en nuestro ejemplo). A continuación busque la carpeta **/Documentos compartidos/Datos GER/PowerBI**, y seleccione el archivo de Excel que ha creado como origen de los datos para el nuevo conjunto de datos de Power BI. [![que selecciona el archivo de Excel (]. /media/ger-power-bi-add-dataset-select-excel-file-1024x522.png])(. Haga clic en /media/ger-power-bi-add-dataset-select-excel-file.png) ** conectar **, haga clic en ** ** importación. Se crea un conjunto de datos nuevos que se basa en el archivo de Excel seleccionado. El conjunto de datos también puede añadirse automáticamente al panel recién creado. [conjunto de datos de![en el panel] (. /media/ger-power-bi-added-dataset-1024x489.png])(. /media/ger-power-bi-added-dataset.png) Configure la programación de actualización para que este conjunto de datos forzar una actualización periódica. Las actualizaciones periódicas habilitan el consumo de nuevos datos empresariales que vengan de Dynamics 365 for Operations a través de la ejecución periódica del informe de ER a través de nuevas versiones del archivo de Excel que se crean en el Servidor de SharePoint.

## <a name="create-a-power-bi-report-by-using-the-new-dataset"></a>Crear un informe de Power BI mediante el conjunto de datos nuevos
Para crear un nuevo informe de Power BI, haga clic en el conjunto de datos de Power BI **Detalles de importación y exportación** que ha creado. A continuación configure la vista. Por ejemplo, seleccione la vista **Mapa lleno**, y configúrelo de la manera siguiente:

-   Asignar el campo de conjunto de datos **CountryOrigin** al campo **Ubicación** de la vista del mapa.
-   Asignar el campo de conjunto de datos **Cantidad** al campo **Saturación de color** de la vista del mapa.
-   Agregar los campos de conjunto de datos de **Actividad** y **Año** a la recopilación de campos de **Filtros** de la vista de mapa.

Guarde el informe de Power BI como **Informe de detalles de importación y exportación**. [importación![y de detalles de exportación] (. /media/ger-power-bi-added-report-1024x498.png])(. Nota de /media/ger-power-bi-added-report.png) que el mapa muestra los países/regiones mencionados en el archivo de Excel (Austria y Suiza en este ejemplo). Estos países/regiones se colorean para mostrar la proporción de importes facturados para cada uno. Actualizar la lista de transacciones Intrastat. Se ha añadido la transacción de exportación que se ha originado desde Italia. [transacciones intrastat![que aparecen] (. /media/ger-power-bi-new-run-new-transaction-1024x321.png])(. Espera de /media/ger-power-bi-new-run-new-transaction.png) para la siguiente ejecución programada del informe de ER y actualización después programada del conjunto de datos de Power BI. A continuación revise el informe de Power BI (seleccione solo para mostrar las transacciones de importación). El mapa actualizado ahora muestra Italia. mapa actualizado [] (![. /media/ger-power-bi-new-run-new-map-1024x511.png])(. /media/ger-power-bi-new-run-new-map.png)

## <a name="access-power-bi-report-in-dynamics-365-for-operations"></a>Acceda al informe de Power BI en Dynamics 365 for Operations
Configure la integración entre Dynamics 365 for Operations y Power BI. Para obtener más información, consulte [Integración de configuración de Power BI para las áreas de trabajo](configure-power-bi-integration.md). En ** informe de errores electrónico ** la página de área de trabajo que admite la integración de Power BI (** Administración de organización ** &gt; ** las áreas de trabajo ** &gt; ** área de trabajo electrónica de informes **), haga clic ** opciones ** &gt; ** catálogo abierto ** del informe. Seleccione el informe **Detalles de exportación e importación** de Power BI que ha creado, para mostrar dicho informe como un artículo de acción en la página seleccionada. Haga clic en el elemento de acción para abrir la página de Dynamics 365 for Operations que muestra el informe que ha diseñado en Power BI. [importación![y de detalles de exportación] (. /media/ger-power-bi-review-bi-report-in-ax-form-1024x586.png])(. /media/ger-power-bi-review-bi-report-in-ax-form.png)

<a name="see-also"></a>Consulte también
--------

[Destinos de informes electrónicos](electronic-reporting-destinations.md)

[Visión general de los informes electrónicos](general-electronic-reporting.md)


