---
title: Configurar la importación de datos de SharePoint
description: En este tema se explica cómo importar datos de Microsoft SharePoint.
author: NickSelin
manager: AnnBe
ms.date: 11/29/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 8053b0316c86c614b87b0e658dffade3a135f2cc
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1552822"
---
# <a name="configure-data-import-from-sharepoint"></a>Configurar la importación de datos de SharePoint

[!include[banner](../includes/banner.md)]

Para importar datos de un archivo entrante mediante el marco de informes electrónicos (ER), debe configurar un formato de ER que admita la importación y luego ejecutar una asignación del modelo del tipo **A destino** que utilice el formato como un origen de datos. Para importar datos, debe navegar hasta el archivo que desee importar. El usuario puede seleccionar manualmente el archivo entrante. Con la nueva capacidad de ER de admitir la importación de datos de Microsoft SharePoint, este proceso se puede configurar de manera automática. Puede usar las configuraciones de ER para realizar la importación de datos de los archivos que se almacenan en las carpetas de Microsoft SharePoint. Este tema explica cómo completar la importación de SharePoint a Microsoft Dynamics 365 for Finance and Operations. Los ejemplos utilizan transacciones del proveedor como datos empresariales.

## <a name="prerequisites"></a>Requisitos previos
Para completar los ejemplos de este tema, debe tener el acceso siguiente:

- Acceso a Finance and Operations para uno de los roles siguientes:

    - Desarrollador de informes electrónicos
    - Consultor funcional de informes electrónicos
    - Administrador del sistema

- Acceda a la instancia de Microsoft SharePoint Server que está configurada para su uso con Finance and Operations.
- Configuraciones del formato y el modelo de ER para pagos 1099.

### <a name="create-required-er-configurations"></a>Crear las configuraciones de ER necesarias
Reproduzca las guías de tareas **Datos de importación de ER de un archivo de Microsoft Excel**, que forman parte del proceso empresarial **7.5.4.3 Adquirir o desarrollar componentes de soluciones y servicios de TI (10677)**. Estas guías de tareas le guiarán por el proceso de diseño y uso de configuraciones de ER para importar de forma interactiva transacciones del proveedor desde archivos de Microsoft Excel. Para obtener más información, consulte [Analizar documentos de entrada enMicrosoft Excel](parse-incoming-documents-excel.md). Cuando haya completado las guías de la tarea, tendrá la siguiente configuración.

#### <a name="er-configurations"></a>Configuraciones ER

- Configuración del modelo de ER, **Modelo de pagos 1099**
- Configuración del formato de ER, **Formato para importar transacciones de los proveedores desde Excel**

![Configuraciones de ER para importar datos de SharePoint](./media/GERImportFromSharePoint-01-Configurations.PNG)

#### <a name="sample-of-the-incoming-file-for-data-import"></a>Ejemplo del archivo entrante para la importación de datos

- Archivo de Excel **1099import-data.xlsx**, con las transacciones del proveedor que deben importarse en Finance and Operations.

![Ejemplo de archivo de Microsoft Excel para importar desde SharePoint](./media/GERImportFromSharePoint-02-Excel.PNG)
    
> [!NOTE]
> El formato para importar transacciones del proveedor se selecciona como la asignación del modelo predeterminado. Por lo tanto, si ejecuta una asignación del modelo del **Modelo de pagos 1099**, y esta asignación del modelo es del tipo **A destino**, la asignación del modelo ejecuta este formato para importar datos desde archivos externos. A continuación, emplea esos datos para actualizar tablas de la aplicación.

## <a name="configure-access-to-sharepoint-for-file-storage"></a>Configurar el acceso a SharePoint para el almacenamiento de archivos
Para almacenar archivos electrónicos de informes en una ubicación de SharePoint, debe configurar el acceso a la instancia de SharePoint Server que usará la empresa actual. En este ejemplo, la empresa es USMF. Para obtener instrucciones, consulte [Configurar el almacenamiento de SharePoint](../../fin-and-ops/organization-administration/configure-document-management.md#configure-sharepoint-storage).

1. Complete los pasos indicados en [Configurar el almacenamiento de SharePoint](../../fin-and-ops/organization-administration/configure-document-management.md#configure-sharepoint-storage).
2. Abra el sitio de SharePoint configurado.
3. Cree las carpetas siguientes en las que los archivos electrónicos entrantes de informe de errores se pueden almacenar:

     - Origen de la importación de los archivos (principal) (ejemplo que se muestra en captura de pantalla de abajo)
     - Origen de la importación de los archivos (alternativa)

    ![Origen de la importación de los archivos (principal)](./media/GERImportFromSharePoint-04-SharePointFolder1.png)

4. (Opcional) Cree las carpetas siguientes en las que los archivos se pueden almacenar después de la importación. 

    - Carpeta de archivos archivados - esta carpeta sería para los archivos importados correctamente.
    - Carpeta de archivos con advertencia - esta carpeta sería para los archivos importados con una advertencia.
    - Carpeta de archivos con error - esta carpeta sería para los archivos importados con error.

4. En Finance and Operations vaya a **Administración de la organización > administración de documentos > tipos de documento**.
5. Cree los siguientes tipos de documentos que se usarán para obtener acceso a las carpetas de SharePoint que acaba de crear. Para obtener instrucciones, consulte [Configurar tipos de documentos](../../fin-and-ops/organization-administration/configure-document-management.md#configure-document-types).

|Tipo de documento       | Grupo              | Ubicación      | Carpeta SharePoint      |
|--------------------|--------------------|---------------|------------------------|
|SP principal             |Archivo                |SharePoint     |Origen de la importación de los archivos (principal)|
|SP alternativo             |Archivo                |SharePoint     |Origen de la importación de los archivos (alternativa)|
|Archivo SP             |Archivo                |SharePoint     |Carpeta de archivos archivados|
|Advertencia de SP             |Archivo                |SharePoint     |Carpeta de archivos con advertencias|
|Error de SP             |Archivo                |SharePoint     |Carpeta de archivos con errores|

![Configuración de SharePoint – nuevo tipo de documento](./media/GERImportFromSharePoint-06-SharePointDocumentTypesSetup.png)

## <a name="configure-er-sources-for-the-er-format"></a>Configurar fuentes de ER para el formato de ER
1. Haga clic en **Administración de la organización** \> **Informes electrónicos** \> **Trabajos de informes electrónicos**.
2. En la página **Origen de informes electrónicos**, configure los archivos de origen para la importación de datos mediante el formato de ER configurado.
3. Defina una máscara de nombre de archivo, de manera que solo se importen los archivos con la extensión .xlsx. La máscara de nombre de archivo es opcional y se utiliza solo cuando se ha definido. Solo puede definir una máscara para cada formato de ER.
4. Cambie **Ordenar archivos antes de importar** a **No ordenar**, si hay muchos archivos para importar y el orden de la importación no es importante.
5. Seleccione todas las carpetas de SharePoint que creó anteriormente.

    [![Configuración de origen de archivos de ER](./media/GERImportFromSharePoint-07-FormatSourceSetup.PNG)](./media/GERImportFromSharePoint-07-FormatSourceSetup.PNG)

> [!NOTE]
> - El *origen* de ER se define individualmente para cada empresa de aplicaciones. En cambio, las *configuraciones* de ER se comparten entre las empresas.
> - Cuando elimina una configuración de origen de ER para un formato de ER, también se eliminan todos los estados de los archivos conectados por confirmación (véase más abajo).

## <a name="review-the-files-states-for-the-er-format"></a>Revise los estados de los archivos para el formato de ER
1. En la página **Origen de informes electrónicos**, seleccione **Estados de archivo para los orígenes** para revisar el contenido de los orígenes de archivo configurados para el formato de ER actual.
2. En la sección **Archivos**, revise la lista de archivos. Esta lista muestra lo siguiente:

    - Archivos de origen que son aplicables, en función de la máscara de nombre de archivo (si se define una máscara de nombre de archivo) y que están listos para la importación de datos. Para estos archivos, la sección **Registro de los orígenes para el formato de importación** está en blanco.
    - Archivos importados anteriormente. Para cada uno de estos archivos, en la sección **Registro de los orígenes para el formato de importación**, puede revisar el historial de importación de este archivo.

También puede abrir la página **Estados de archivo para los orígenes** seleccionando **Administración de la organización** \> **Informes electrónicos** \> **Estados de archivo para los orígenes**. En este caso, la página ofrece información sobre los orígenes de archivo para todos los formatos de ER para los que se han configurado los orígenes de archivo en la empresa en la que está registrado actualmente.

## <a name="import-data-from-excel-files-that-are-in-a-sharepoint-folder"></a>Importar datos de los archivos Excel que están en una carpeta de SharePoint
1. En SharePoint, cargue el archivo de Microsoft Excel **1099import-data.xlsx** que contiene transacciones de proveedores en la carpeta de SharePoint **Origen de la importación de los archivos (principal)** que creó anteriormente.

    [![SharePoint contenido – archivo Microsoft Excel para importar](./media/GERImportFromSharePoint-08-UploadFile.png)](./media/GERImportFromSharePoint-08-UploadFile.png)

2. En Finance and Operations, en la página **Estados de archivo para los orígenes**, seleccione **Actualizar** para actualizar la página. Tenga en cuenta que el archivo de Excel que se cargó en SharePoint  aparecía en esta página con el estado **Preparado**. Actualmente se admiten los siguientes estados:

    - **Preparado** - Asignado automáticamente para cada nuevo archivo en una carpeta de SharePoint. Este estado significa que el archivo está listo para la importación.
    - **Importando** - Asignado automáticamente por un informe de ER cuando el archivo se bloquea mediante el proceso de importación para evitar su uso por otros procesos (si muchos de ellos se están ejecutando simultáneamente).
    - **Importado** - Asignado automáticamente por un informe de ER cuando la importación del archivo se completa correctamente. Este estado significa que el archivo importado se ha eliminado desde el origen de archivos configurado (carpeta de SharePoint).
    - **Fallido** - Asignado automáticamente por un informe de ER cuando la importación del archivo se completa con errores o excepciones.
    - **En espera** - Asignado manualmente por el usuario en esta página. Este estado significa que el archivo no se importará por ahora. Este estado se puede utilizar para posponer la importación de algunos archivos.

    [![Página de estados de archivo de ER para los orígenes seleccionados](./media/GERImportFromSharePoint-09-FileStatesForm.png)](./media/GERImportFromSharePoint-09-FileStatesForm.png)

## <a name="import-data-from-sharepoint-files"></a>Importar datos desde archivos SharePoint
1. Abra el árbol de configuraciones de ER, seleccione el **Modelo de sueldo 1099** y amplíe la lista de componentes del modelo de ER.
2. Seleccione el nombre de la asignación de modelo para abrir la lista de asignaciones de modelo de la configuración seleccionada del modelo de ER.

    [![Página de estados de archivo de ER para los orígenes seleccionados](./media/GERImportFromSharePoint-10-SelectModelMapping.PNG)](./media/GERImportFromSharePoint-10-SelectModelMapping.PNG)

3. Seleccione **Ejecutar** para ejecutar la asignación de modelo seleccionado. Puesto que configuró los orígenes de archivo para el formato de ER, puede cambiar la configuración de la opción **Origen de archivo** si es preciso. Si conserva el configuración de esta opción, los archivos .xslx se importan desde los orígenes configurados (las carpetas de SharePoint, en este ejemplo).

    En este ejemplo, está importando un único archivo. Sin embargo, si hay varios archivos, se seleccionan para importarlos en el orden en el que se han agregado a la carpeta de SharePoint. Cada ejecución de un formato de ER se importa un único archivo seleccionado.

    [![Ejecutar asignación de modelo de ER](./media/GERImportFromSharePoint-11-RunModelMapping.PNG)](./media/GERImportFromSharePoint-11-RunModelMapping.PNG)

4. La asignación de modelo puede ejecutarse automáticamente en modo de lote. En este caso, cada vez que un lote ejecuta este formato de ER, se importa un único archivo desde las fuentes de archivo configuradas.

    Cuando se importa un archivo con éxito de la carpeta de SharePoint, se elimina de esa carpeta y se pasa a la carpeta para los archivos importados con éxito o a la carpeta de los archivos importados con avisos. Si no se mueve a la carpeta para los archivos fallidos o permanece en esta carpeta si la carpeta para los archivos fallidos no se ha configurado. 

5. Introduzca el Id. de asiento, como **V-00001** y, a continuación, seleccione **Aceptar**.

    [![Ejecutar asignación de modelo de ER](./media/GERImportFromSharePoint-12-ModelMappingRunFinished.PNG)](./media/GERImportFromSharePoint-12-ModelMappingRunFinished.PNG)

6. En la página **Estados de archivo para los orígenes**, seleccione **Actualizar** para actualizar la página.

    [![Página de estados de archivo de ER para los orígenes seleccionados](./media/GERImportFromSharePoint-13-FileStatesForm.PNG)](./media/GERImportFromSharePoint-13-FileStatesForm.PNG)

7. En la sección **Archivos**, revise la lista de archivos. La sección **Registro de los orígenes para el formato de importación** proporciona el historial de importación del archivo de Excel. Dado que este archivo se importó correctamente, se marca como **Eliminado** en la carpeta de SharePoint.
8. Revise la carpeta de SharePoint **Origen de la importación de los archivos (principal)**. Los archivos de Excel que se importaron correctamente se han eliminado de esta carpeta.
9. En Finance and Operations, seleccione **Proveedores** \> **Tareas periódicas** \> **Impuesto 1099** \> **Liquidación del proveedor para 1099**.
10. En los campos **Fecha inicial** y **Fecha final**, introduzca los valores adecuados. A continuación, seleccione **Transacciones 1099 manuales**.

    Las transacciones del proveedor que se importaron de los archivos de Excel en SharePoint para el asiento **V-00001** están presentes en la página.

    [![Página de transacciones del proveedor 1099](./media/GERImportFromSharePoint-14-ImportedTransactions.PNG)](./media/GERImportFromSharePoint-14-ImportedTransactions.PNG)

## <a name="prepare-an-excel-file-for-import"></a>Preparar un archivo de Excel para importación
1. Abra el archivo de Excel que utilizó anteriormente. En la fila 3 columna 1, agregue un código de proveedor que no exista en la aplicación. Agregue más información del proveedor falsa a la fila.

    [![Ejemplo de archivo de Microsoft Excel para importar desde SharePoint](./media/GERImportFromSharePoint-15-Excel.PNG)](./media/GERImportFromSharePoint-15-Excel.PNG)

2. Cargue el archivo de Excel actualizado que contenga transacciones de proveedores en la carpeta de SharePoint **Origen de la importación de los archivos (principal)**.
3. En Finance and Operations, abra el árbol de configuraciones de ER, seleccione el **Modelo de sueldo 1099** y amplíe la lista de componentes del modelo de ER.
4. Seleccione el nombre de la asignación de modelo para actualizar la asignación de modelo de manera que el código de proveedor incorrecto se considere un error durante el proceso de importación de datos.
5. Seleccione **Diseñador**.
6. En la pestaña **Validaciones**, debe cambiar la acción de posvalidación para la regla de validación que se configuró para evaluar si la cuenta de proveedor que se importa existe en la aplicación. Actualice el valor del campo **Acción de posvalidación** a **Detener ejecución**, guarde los cambios y cierre la página.

    [![Página de diseñador de asignación de modelos de ER](./media/GERImportFromSharePoint-16-UpdateModelMapping.PNG)](./media/GERImportFromSharePoint-16-UpdateModelMapping.PNG)

7. Guarde sus cambios y cierre el diseñador de asignación de modelos de ER.
8. Seleccione **Ejecutar** para ejecutar la asignación de modelo de ER modificado.
9. Introduzca el Id. de asiento, como **V-00002** y, a continuación, seleccione **Aceptar**.

    Tenga en cuenta que el registro de información contiene una notificación que informa de que hay un archivo en la carpeta de SharePoint que contiene una cuenta de proveedor incorrecta y no se puede importar.

    [![Ejecutar asignación de modelo de ER](./media/GERImportFromSharePoint-17-ModelMappingRunFinished.PNG)](./media/GERImportFromSharePoint-17-ModelMappingRunFinished.PNG)

10. En la página **Estados de archivo para los orígenes**, seleccione **Actualizar** y, a continuación, en la sección **Archivos**, revise la lista de archivos.

    [![Página de estados de archivo de ER para los orígenes seleccionados](./media/GERImportFromSharePoint-18-FileStatesForm.PNG)](./media/GERImportFromSharePoint-18-FileStatesForm.PNG)

   La sección **Registro de los orígenes para el formato de importación** indica que el proceso de importación ha fallado y que el archivo se encuentra todavía en la carpeta de SharePoint de archivos con error (la casilla **Eliminado** no está seleccionada). Si arregla este archivo en SharePoint agregando el código de proveedor correspondiente y después lo mueve a la carpeta (principal) de SharePoint del origen de la importación de los archivos, puede importar el archivo de nuevo.

11. En Finance and Operations, seleccione **Proveedores** \> **Tareas periódicas** \> **Impuesto 1099** \> **Liquidación del proveedor para 1099**, introduzca los valores adecuados en los campos **Fecha inicial** y **Fecha final** y, a continuación, seleccione **Transacciones 1099 manuales**.

    Solo están disponibles las transacciones para el asiento V-00001. No están disponibles las transacciones para el asiento V-00002 aunque se ha encontrado el error para la última transacción importada en el archivo de Excel.
