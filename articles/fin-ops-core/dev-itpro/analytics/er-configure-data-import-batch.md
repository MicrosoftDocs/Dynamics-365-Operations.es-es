---
title: Importar datos de archivos seleccionados manualmente en el modo por lotes
description: Este artículo explica cómo importar datos de archivos seleccionados manualmente en modo por lotes.
author: kfend
ms.date: 01/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2022-01-01
ms.dyn365.ops.version: Release 10.0.25
ms.custom: 220314
ms.assetid: ''
ms.search.form: ERSolutionTable, ERImportFormatSourceTable, ERWorkspace
ms.openlocfilehash: 21a2ab5f0eb07dda92baf9cc04ee36caeff8b4ec
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288240"
---
# <a name="import-data-from-manually-selected-files-in-batch-mode"></a>Importar datos de archivos seleccionados manualmente en el modo por lotes

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

Para usar el marco de [informes electrónicos (ER)](general-electronic-reporting.md) para importar datos de archivos entrantes seleccionados manualmente en modo por lotes, configure un [formato](er-overview-components.md#format-component) ER que soporte la importación. Luego ejecute una [asignación de modelos](er-overview-components.md#model-mapping-component) del tipo **A destino** que utiliza ese formato como fuente de datos. Para importar datos, navegue hasta el archivo que desee importar y selecciónelo manualmente. 

La nueva capacidad de ER que admite la importación de datos en modo pro lotes permite configurar este proceso de manera automática. Puede usar las configuraciones de ER para realizar la importación de datos mediante la programación de un nuevo trabajo por lotes desde la interfaz de usuario (IU) de ER.

Este artículo explica cómo completar la importación de datos de archivos seleccionados manualmente en modo por lotes. Los ejemplos utilizan transacciones del proveedor como datos empresariales. Los pasos de estos ejemplos se pueden completar en la empresa **USMF**. No se requiere codificación.

## <a name="prerequisites"></a>Requisitos previos

Para completar los ejemplos de este artículo, debe tener el acceso siguiente:

- Uno de los roles siguientes:

    - Desarrollador de informes electrónicos
    - Consultor funcional de informes electrónicos
    - Administrador del sistema

- Configuraciones del formato y el modelo de ER para pagos 1099

### <a name="create-the-required-er-configurations"></a>Crear las configuraciones de ER necesarias

Para crear las configuraciones de ER requeridas y obtener otros requisitos previos, siga uno de estos pasos:

- Reproduzca las guías de tareas **Datos de importación de ER de un archivo de Microsoft Excel**, que forman parte del proceso empresarial **7.5.4.3 Adquirir o desarrollar componentes de soluciones y servicios de TI (10677)**. Estas guías de tareas le guiarán por el proceso de diseño y uso de configuraciones de ER que importan de forma interactiva transacciones del proveedor desde archivos de Microsoft Excel. Para obtener más información, consulte [Analizar documentos de entrada en formato Excel](parse-incoming-documents-excel.md).
- Complete los ejemplos de [Configurar la importación de datos desde SharePoint](er-configure-data-import-sharepoint.md). Estos ejemplos le guiarán por el proceso de diseño y uso de configuraciones de ER que importan de forma interactiva transacciones del proveedor desde archivos de Microsoft Excel que están almacenadas en una carpeta de SharePoint.

### <a name="download-the-required-er-configurations"></a>Descargar las configuraciones de ER necesarias

1. Descargue y almacene localmente las siguientes configuraciones de ER.

    | Descripción del contenido | Archivo |
    |---------------------|------|
    | Configuración del modelo de datos de ER del **Modelo de pago 1099** | [1099model.xml](https://download.microsoft.com/download/b/d/9/bd9e8373-d558-4ab8-aa9b-31981adc97ea/1099model.xml) |
    | Configuración del formato de ER **para importar transacciones de los proveedores (Excel)** | [1099format-import-from-excel.xml](https://download.microsoft.com/download/b/3/8/b38faf0a-fbaf-4e9e-84c2-dedae7464880/1099format-import-from-excel.xml) |

2. Utilice la opción de ER [Cargar desde archivo XML](er-defer-sequence-element.md#import-the-sample-er-configurations) para importar las configuraciones de ER descargadas a su instancia de Dynamics 365 Finance en el siguiente orden:

    1. Configuración del modelo datos de ER
    2. Configuración del formato de ER

### <a name="download-the-required-excel-files"></a>Descargar los archivos de Excel requeridos

- Descargue el siguiente conjunto de datos de muestra y guárdelo localmente.

    | Descripción del contenido | Archivo |
    |---------------------|------|
    | Archivo **1099import-data.xlsx** de entrada que contiene datos de ejemplo para importar | [1099import-data.xlsx](https://download.microsoft.com/download/f/f/4/ff4dbce9-8364-4391-adee-877945ff01f7/1099import-data.xlsx) |

### <a name="review-the-prerequisites"></a>Revisar los requisitos previos

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, revise la solución ER preparada para la importación de datos en modo por lotes.
3. Reviser la configuración del formato **para importar transacciones de los proveedores (Excel)**

    - El componente de formato de esta configuración está diseñado para analizar un archivo de Excel entrante.
    - El componente de asignación de modelos de esta configuración se utiliza para completar el modelo de datos base mediante el uso de datos del archivo de Excel analizado.

    ![Configuración del formato ER para importar datos en modo por lotes desde la interfaz de usuario de ER.](./media/er-configure-data-import-batch-configurations-1.png)

4. Revise la configuración del modelo de datos del **Modelo de pago 1099**.

    - El componente de modelo de esta vonfiguración representa la estructura del modelo de datos que se usa para pasar datos entre componentes de ER en ejecución.
    - El componente de asignación de modelos de esta configuración se usa para extraer datos del componente de formato ejecutado y luego actualizar las tablas de la aplicación.

    ![Configuración del modelo de datos de ER para importar datos en modo por lotes desde la interfaz de usuario de ER.](./media/er-configure-data-import-batch-configurations-2.png)

5. Abra el archivo **1099import-data.xlsx** en Excel.

    ![Ejemplo de archivo de Excel con datos para importar en modo por lotes.](./media/er-configure-data-import-batch-excel-content.png)

## <a name="enable-batch-data-import-for-er-from-the-ui"></a>Habilite la importación de datos por lotes para ER desde la interfaz de usuario

1. Vaya a **Administración del sistema** \> **Espacios de trabajo** \> **Administración de características**.
2. En el espacio de trabajo **Gestión de características**, seleccione la función **Ejecutar la importación de ER de documentos cargados manualmente en lote** y, a continuación, seleccione **Habilitado ahora**.

## <a name="import-data-from-manually-selected-excel-files"></a>Importar datos de archivos de Excel seleccionados manualmente

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, seleccione la configuración del modelo de datos **Modelo de pagos 1099**.
3. En la ficha desplesgalbe **Componentes de configuración**, seleccione el enlace **Para la importación de transacciones manuales 1099**.
4. En la página **Mapeo de modelo a fuente de datos**, la asignación del modelo **Para la importación de transacciones manuales 1099** está preseleccionada. Seleccione **Ejecutar**.
5. En la ficha **Parámetros**, seleccione **Examinar**. Busque y seleccione el archivo **1099import-data.xlsx** y luego seleccione **Aceptar**.
6. En el campo **Introducir id. de vale**, introduzca **V-00001**.
7. En la ficha **Ejecutar en segundo plano**, establezca la opción **Procesamiento por lotes** en **Sí**.

    Note que el campo **Descripción de la tarea** se establece en **Ejecución del mapeo del modelo 'Para la importación de transacciones manuales 1099', configuración 'Modelo de pagos 1099'**. Este valor indica que la ejecución del mapeo del modelo seleccionado se programará como un nuevo trabajo por lotes.

    ![Especificar detalles de la importación de datos en modo por lotes en el cuadro de diálogo Parámetros del informe electrónico.](./media/er-configure-data-import-batch-execution-parameters.png)

8. Seleccione **Aceptar**. Un mensaje le notifica que se ha programado un nuevo trabajo por lotes.

    ![Mensaje sobre un nuevo trabajo por lotes programado en la página de asignación del modelo a la fuente de datos.](./media/er-configure-data-import-batch-scheduled-job-info.png)

## <a name="review-the-data-import-results-on-the-batch-job-page"></a>Revise los resultados de la importación de datos en la página de trabajo por lotes

1. Vaya **Común** \> **Consultas** \> **Trabajos por lotes** \> **Mis trabajos por lotes**.
2. En la página **Trabajo por lotes**, filtre la lista de trabajos por lotes para encontrar el lote programado y luego selecciónelo.
3. Seleccione el **Id. del trabajo** enlace para revisar los detalles del trabajo.
4. En la ficha desplegable **Tareas por lotes**, seleccione **Registro**.

    ![Botón de registro en la página de trabajo por lotes.](./media/er-configure-data-import-batch-scheduled-job-record.png)

5. Revise los detalles de ejecución.

    ![Registro de ejecución del trabajo por lotes programado en la página Trabajo por lotes.](./media/er-configure-data-import-batch-scheduled-job-log.png)

## <a name="change-the-data-import-parameters"></a>Cambiar los parámetros de importación de datos

Después de programar su lote y mientras aún no se haya ejecutado, puede cambiar los parámetros de la importación de datos programada.

1. Vaya **Común** \> **Consultas** \> **Trabajos por lotes** \> **Mis trabajos por lotes**.
2. En la página **Trabajo por lotes**, filtre la lista de trabajos por lotes para encontrar el lote programado y luego selecciónelo.
3. Seleccione **Cambiar estado**.
4. En el cuadro de diálogo **Seleccionar nuevo estado**, seleccione **Retener** y luego **Aceptar**.
5. Seleccione el enlace **Id. del trabajo** para acceder a los detalles del trabajo.
6. En la ficha desplegable **Tareas por lotes**, seleccione **Parámetros**.
7. En el cuadro de diálogo **Parámetros de informes electrónicos**, siga estos pasos:

    1. Seleccione **Navegar** para seleccionar el archivo alternativo para la importación de datos.
    2. Seleccione **Ingrese la identificación del cupón** para cambiar el número de comprobante para importar transacciones de proveedor.

        ![Cambiar los parámetros de la importación de datos para el trabajo por lotes programado en el cuadro de diálogo Parámetros del informe electrónico.](./media/er-configure-data-import-batch-scheduled-job-parameters.png)

    3. Seleccione **Aceptar**.

8. Asegúrese de que el lote aún esté seleccionado y luego seleccione **Cambiar Estado** de nuevo.
9. En el cuadro de diálogo **Seleccionar nuevo estado**, seleccione **En espera** y luego **Aceptar**.

## <a name="review-the-data-import-results-on-the-er-source-page"></a>Revise los resultados de la importación de datos en la página de origen ER

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Trabajos de informes electrónicos**.
2. Seleccione el registro **Para importar transacciones de proveedores (Excel)** que se creó automáticamente durante la importación de datos.

    ![Registro para la configuración Para importar transacciones de proveedores (Excel) en la página Fuente de informes electrónicos.](./media/er-configure-data-import-batch-files-source-1.png)

3. Seleccione **Estados de archivo para los orígenes**.
4. En las fichas desplegables **Archivos** y **Registros de origen para el formato de importación**, revise los detalles de importación.
5. En la ficha desplegable **Archivos**, seleccione el registro. Observe que el archivo importado se adjunta a este registro.

    ![Archivo importado adjunto al registro en los estados del archivo para la página de fuentes.](./media/er-configure-data-import-batch-files-source-2.png)

6. Seleccione **Archivos adjuntos** para revisar el archivo importado.

    ![Archivo importado en la página de vista de documento.](./media/er-configure-data-import-batch-files-source-3.png)

    > [!TIP]
    > Para mantener estos archivos adjuntos, el marco ER utiliza un tipo de documento que se [establece](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) para la empresa actual en el campo **Otros** de los parámetros de ER.

## <a name="review-the-data-import-results-on-the-vendor-settlement-for-1099s-page"></a>Revise los resultados de la importación de datos en la página Liquidación de proveedores para 1099s

1. Vaya a **Proveedores** \> **Tareas periódicas** \> **Impuesto 1099** \> **Liquidación del proveedor por 1099s**.
2. En el campo **Fecha inicial**, escriba **12/31/2017** (31 de diciembre de 2017).
3. Seleccione **Transacciones 1099 manuales**.

    ![Transacciones de proveedores importados en la página de transacciones de Tax 1099.](./media/er-configure-data-import-batch-imported-data.png)

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de los informes electrónicos](general-electronic-reporting.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
