---
title: Realizar un seguimiento de la ejecución de los formatos de ER para solucionar problemas de rendimiento
description: Este artículo proporciona información acerca de cómo utilizar la función de seguimiento del rendimiento en los informes electrónicos (ER) para solucionar problemas de rendimiento.
author: NickSelin
ms.date: 06/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 4ea6901f8d9632b021c35b9ee899385e688fc77e
ms.sourcegitcommit: 3289478a05040910f356baf1995ce0523d347368
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2022
ms.locfileid: "9108868"
---
# <a name="trace-the-execution-of-er-formats-to-troubleshoot-performance-issues"></a>Seguir la ejecución de formatos de ER para solucionar problemas de rendimiento

[!include[banner](../includes/banner.md)]

Como parte del proceso de diseño de las configuraciones de informes electrónicos (ER) para generar documentos electrónicos, se define el método que se usa para sacar datos de la aplicación y para introducirlos en la salida se ha generado. La función de seguimiento del rendimiento de ER ayuda a reducir significativamente el tiempo y el coste implicados al recopilar los detalles de la ejecución del formato de ER y utilizarlos para solucionar problemas de rendimiento. Este tutorial proporciona instrucciones acerca de cómo realizar seguimientos de rendimiento para los formatos de ER ejecutados y cómo utilizar la información de estos seguimientos para ayudar a mejorar el rendimiento.

## <a name="prerequisites"></a>Requisitos previos

Para completar los ejemplos de este tutorial, debe tener el acceso siguiente:

- Acceso a uno de los roles siguientes:

    - Desarrollador de informes electrónicos
    - Consultor funcional de informes electrónicos
    - Administrador del sistema

- Acceso a la instancia de los Regulatory Configuration Services (RCS) que se ha aprovisionado para el mismo que el arrendatario de la aplicación, para uno de los roles siguientes:

    - Desarrollador de informes electrónicos
    - Consultor funcional de informes electrónicos
    - Administrador del sistema

Debe descargar y también almacenar localmente los archivos siguientes.

| Archivo                                  | Contenido                               |
|---------------------------------------|---------------------------------------|
| Seguimiento de rendimiento model.version.1     | [Configuración del modelo datos de ER de ejemplo](https://download.microsoft.com/download/0/a/a/0aa84e48-8040-4c46-b542-e3bf15c9b2ad/Performancetracemodelversion.1.xml)    |
| Seguimiento de rendimiento metadata.version.1  | [Configuración de metadatos de ER de ejemplo](https://download.microsoft.com/download/a/9/3/a937e8c4-1f8a-43e4-83ee-7d599cf7d983/Performancetracemetadataversion.1.xml)      |
| Seguimiento de rendimiento mapping.version.1.1 | [Configuración del modelo de mapeado de ER de ejemplo](https://download.microsoft.com/download/7/7/3/77379bdc-7b22-4cfc-9b64-a9147599f931/Performancetracemappingversion1.1.xml) |
| Seguimiento de rendimiento format.version.1.1  | [Configuración de formato de ER de ejemplo](https://download.microsoft.com/download/8/6/8/868ba581-5a06-459e-b173-fb00f038b37f/Performancetraceformatversion1.1.xml)       |

### <a name="configure-er-parameters"></a>Configurar los parámetros de ER

Cada seguimiento de rendimiento de ER que se genera en la aplicación se almacena como adjunto de la entrada de registro de la ejecución. El marco de gestión de documentos (DM) se usa para administrar estos datos adjuntos. Debe configurar los parámetros de ER por adelantado, para especificar el tipo de documento de DM que se utilizará para adjuntar seguimientos de rendimiento. En el área de trabajo de **Informes electrónicos**, seleccione **Parámetros de informes electrónicos**. A continuación, en la página **Parámetros de informes electrónicos**, en la pestaña **Datos adjuntos**, en el campo **Otros**, seleccione el tipo de documento de DM para utilizar para los seguimientos de rendimiento.

![Página de parámetros de informes electrónicos.](./media/GER-PerfTrace-GER-Parameters-DocumentType.png)

Para estar disponible en el campo búsqueda **Otros**, el tipo de documento del DM debe estar configurado de la forma siguiente en la página **Tipos de documento** (**Administración de la organización \> Gestión de documentos \> Tipos de documento**):

- **Clase:** Adjuntar archivo
- **Grupo:** Archivo

![Página de tipos de documento.](./media/GER-PerfTrace-DM-DocumentType.png)

> [!NOTE]
> El tipo de documento seleccionado debe estar disponible en cada empresa de la instancia actual, ya que los archivos adjuntos de DM son específicos de la empresa.

### <a name="configure-rcs-parameters"></a>Configurar parámetros RCS

Para los seguimientos del rendimiento de ER que se generan se importarán en el RCS para su análisis utilizando el diseñador del formato de ER y el diseñador de la asignación de ER. Dado que los seguimientos de rendimiento de ER se almacenan como adjunto de la entrada de registro de la ejecución relacionada con el formato de ER, debe configurar los parámetros de RCS por adelantado, para especificar el tipo de documento de DM que se utilizará para vincular seguimientos de rendimiento. En la instancia de RCS que se ha aprovisionado para su empresa, en el área de trabajo **Informes electrónicos**, seleccione **Parámetros electrónicos de informes**. A continuación, en la página **Parámetros de informes electrónicos**, en la pestaña **Datos adjuntos**, en el campo **Otros**, seleccione el tipo de documento de DM para utilizar para los seguimientos de rendimiento.

![Página de parámetros de informes electrónicos en RCS.](./media/GER-PerfTrace-RCS-Parameters-DocumentType.png)

Para estar disponible en el campo búsqueda **Otros**, el tipo de documento del DM debe estar configurado de la forma siguiente en la página **Tipos de documento** (**Administración de la organización \> Gestión de documentos \> Tipos de documento**):

- **Clase:** Adjuntar archivo
- **Grupo:** Archivo

## <a name="design-an-er-solution"></a>Diseñar una solución ER

Supongamos que ha empezado a diseñar una nueva solución de ER para generar un nuevo informe que muestra transacciones de proveedor. Actualmente, puede buscar las transacciones de un proveedor seleccionado en la página **Transacciones de proveedor** (vaya **Cuenta a pagar \> Proveedores \> Todos los proveedores**, seleccione un proveedor y, a continuación, en el panel de acciones, en la pestaña **Proveedor**, en el grupo **Transacciones**, seleccione **Transacciones**). Sin embargo, desea tener toda la transacción de proveedor al mismo tiempo en un documento electrónico en formato XML. Esta solución consistirá en varias configuraciones de ER que contienen el modelo de datos requeridos, metadatos, la asignación modelo, y los componentes del formato.

1. Iniciar sesión en la instancia de RCS que se ha aprovisionado para su empresa.
2. En este tutorial, usted creará y modificará las configuraciones de ER necesarias para la empresa de ejemplo, **Litware, Inc.** Por lo tanto, asegúrese de que este proveedor de configuración se han agregado al RCS y se haya seleccionado como activo. Para obtener instrucciones, consulte el procedimiento [Crear los proveedores de la configuración y marcarlos como activo](tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. En el espacio de trabajo **Informe electrónico**, seleccione el mosaico **Configuraciones de informes** .
4. En la página **Configuraciones** importe las configuraciones de ER que ha descargado como requisito previo en el RCS, en el orden siguiente: modelo de datos, metadatos, asignación modelo, formato. Para cada configuración, siga estos pasos:

    1. En el panel Acción, seleccione **Exchange\> Cargar del archivo XML**.
    2. Seleccione **Exploración** para seleccionar el archivo adecuado para la configuración necesaria de ER en formato XML.
    3. Seleccione **Aceptar**.

    ![Página Configuraciones en RCS.](./media/GER-PerfTrace-RCS-ImportedConfigurations.png)

## <a name="run-the-er-solution-to-trace-execution"></a>Ejecute la solución de ER para realizar un seguimiento de la ejecución

Supongamos que haya terminado de diseñar de la primera versión de la solución de ER. Ahora desea probarla en su instancia y analizar el rendimiento de la ejecución.

### <a name="import-an-er-configuration-from-rcs-into-finance-and-operations"></a><a id='import-configuration'></a>Importar configuraciones de ER de RCS a finanzas y operaciones

1. Iniciar sesión en su instancia de aplicación.
2. Para este tutorial, se importarán las configuraciones de la instancia de RCS (donde se diseñan sus componentes de ER) en la instancia (donde las prueba y finalmente usa). Por lo tanto, debe asegurarse de que se hayan preparado todas artefactos necesarios. Para más instrucciones, consulte el procedimiento [Importar configuraciones de informes electrónicos (ER) de Regulatory Configuration Services (RCS)](rcs-download-configurations.md).
3. Siga estos pasos para importar las configuraciones de RCS en la aplicación:

    1. En el espacio de trabajo **Informes electrónicos**, en el mosaico para el proveedor de la configuración **Litware, Inc.**, seleccione **Repositorios**.
    2. En la página **Configuración de repositorio**, seleccione el repositorio existente del tipo **RCS** y después seleccione **Abrir**.
    3. En la ficha desplegable **Configuraciones**, seleccione la configuración **Formato de seguimiento del rendimiento**.
    4. En la ficha desplegable **Versiones**, seleccione la versión **1.1** de la configuración de ER seleccionada y después seleccione **Importar**.

    ![Página de configuración del repositorio.](./media/GER-PerfTrace-GER-ImportedConfigurations.png)

Las versiones correspondientes de la configuración de la asignación del modelo de datos y de modelo se importan automáticamente como requisitos previos para la configuración importada del formato de ER.

### <a name="turn-on-the-er-performance-trace"></a>Activar el seguimiento del rendimiento de ER

1. Vaya a **Administración de la organización \> Informes electrónicos \> Configuraciones**.
2. En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Configuración avanzada**, seleccione **Parámetros de usuario**.
3. En el cuadro **Parámetros de usuario**, en la sección **Seguimiento de la ejecución**, siga estos pasos:

    1. En el campo **Formato de seguimiento de la ejecución**, especifique el formato de rendimiento generado seguido paso a paso que los detalles de la ejecución se deben almacenar en para los artículos del formato y la asignación de ER:

        - **Formato de seguimiento de depuración** - Seleccione este valor si planea ejecutar de forma interactiva un formato ER que tiene un tiempo de ejecución corto. A continuación, se inicia la recopilación de detalles sobre la ejecución del formato ER. Cuando se selecciona este valor, el seguimiento del rendimiento obtiene información sobre el tiempo que se emplea en las acciones siguientes:

            - Ejecutar cada origen de datos en el modelo de mapeado que se usa para obtener datos
            - Procesar cada elemento de formato para introducir datos en la salida que se genera

            Si selecciona el valor **Formato de seguimiento de depuración**, puede analizar el contenido de la traza en el diseñador de operaciones de ER. Allí, puede ver el formato ER o los elementos de mapeo que se mencionan en el seguimiento.

        - **Formato de seguimiento agregado** - Seleccione este valor si planea ejecutar un formato ER que tiene un tiempo de ejecución largo en modo por lotes. A continuación, se inicia la recopilación de detalles agregados sobre la ejecución del formato ER. Cuando se selecciona este valor, el seguimiento del rendimiento obtiene información sobre el tiempo que se emplea en las acciones siguientes:

            - Ejecutar cada origen de datos en el modelo de mapeado que se usa para obtener datos
            - Ejecutar cada origen de datos en el mapeado de formato que se usa para obtener datos
            - Procesar cada elemento de formato para introducir datos en la salida que se genera

            El valor **Formato de seguimiento agregado** está disponible en Microsoft Dynamics 365 Finance versión 10.0.20 y posteriores.

            En el diseñador de formato ER y el diseñador de mapeo del modelo ER, puede ver el tiempo total de ejecución de un solo componente. Además, el seguimiento contiene detalles sobre la ejecución, como el número de ejecuciones y el tiempo mínimo y máximo de una sola ejecución.

            > [!NOTE]
            > Este rastreo se recopila en función de la ruta de los componentes rastreada. Por lo tanto, las estadísticas pueden ser incorrectas cuando un solo componente principal contiene varios componentes secundarios sin nombre o cuando varios componentes secundarios tienen el mismo nombre.

    2. Establezca las siguientes opciones a **Sí** para obtener los detalles específicos de la ejecución de los componentes de la asignación del modelo de ER y el formato de ER:

        - **Obtener estadísticas de consulta** - Cuando esta opción está activada, el seguimiento del rendimiento obtendrá la siguiente información:

            - El número de llamadas de base de datos realizadas por orígenes de datos
            - Números de llamadas duplicadas a la base de datos
            - Detalles de informes SQL que se utilizaron para realizar llamadas de base de datos

        - **Seguimiento de acceso a la caché** Cuando esta opción está activada, el seguimiento del rendimiento obtendrá información acerca del uso de memoria caché de ER de la asignación de modelo.
        - **Acceso de datos de seguimiento** Cuando esta opción está activada, el seguimiento del rendimiento obtendrá información sobre el número de llamadas a la base de datos para los orígenes de datos ejecutados de tipo lista de registro.
        - **Seguimiento de lista de enumeración** Cuando esta opción está activada, el seguimiento del rendimiento obtendrá información sobre el número de registros solicitados desde los orígenes de datos de tipo lista de registro.

    > [!NOTE]
    > Los parámetros en el cuadro **Parámetros de usuario** son específicos al usuario y para la empresa actual.

    ![Cuadro de diálogo parámetros de usuario.](./media/GER-PerfTrace-GER-UserParameters.png)

### <a name="run-the-er-format"></a><a id='run-format'></a>Ejecutar formato del ER

1. Seleccione la compañía **DEMF**.
2. Vaya a **Administración de la organización \> Informes electrónicos \> Configuraciones**.
3. En la página **Configuraciones**, en el árbol de configuración, seleccione el elemento **Formato de seguimiento del rendimiento**.
4. En el panel de acciones, haga clic en **Ejecutar**.

Tenga en cuenta que el archivo que se genera presenta información sobre 265 transacciones para seis proveedores.

## <a name="review-the-execution-trace"></a>Revisar el seguimiento de la ejecución

### <a name="export-the-generated-trace-from-the-application"></a><a id='export-trace'></a>Exporta el seguimiento generado de la aplicación

Para realizar el seguimiento del rendimiento se desemparejan del formato de ER de origen y se pueden serializar a un archivo externo zip.

1. Vaya a **Administración de la organización \> Informes electrónicos \> Configurar registros de depuración**.
2. En la página **Registros de ejecución de informes electrónicos**, en el panel izquierdo, en el campo **Nombre de configuración**, seleccione **Formato de seguimiento del rendimiento** para buscar las entradas de registro que han sido generadas por la ejecución de la configuración **Formato de seguimiento del rendimiento**.
3. Seleccione el botón **Adjuntos** (el símbolo de clip de papel) en la esquina superior derecha de la página o pulse **Ctrl+Shift+A**.

    ![El botón Adjuntos en la página registros de ejecución de informes electrónicos.](./media/GER-PerfTrace-GER-DebugLog.png)

4. En la página **Datos adjuntos para los informes de los registros electrónicos de la ejecución**, en el panel de acciones, seleccione **Abrir** para obtener el seguimiento del rendimiento como archivo zip y para almacenarlo localmente.

    ![Datos adjuntos para los registros electrónicos de informe de la ejecución.](./media/GER-PerfTrace-GER-DebugLog-AttachedTrace.png)

> [!NOTE]
> El seguimiento que se genera tiene una referencia al informe de ER de origen a través de un identificador único del informe en el formato **GUID**. La numeración de la versión de formato no se tiene en cuenta.

Observe que la asociación entre el rendimiento de seguimiento que se ha generado para el formato de ER ejecutado y la asignación de modelo de ER se basa en la raíz descriptor usada y el modelo de datos común. La numeración de la versión de formato y el mapa de modelado no se tienen en cuenta. El valor del indicador **Predeterminado para la distribución de modelo** para la distribución de modelo no se tiene en cuenta.

### <a name="import-the-generated-trace-into-rcs"></a><a id='import-trace'></a>Importar el seguimiento generado a RCS

1. En RCS, en el espacio de trabajo **Informe electrónico**, seleccione el mosaico **Configuraciones de informes**.
2. En la página **Configuraciones**, en el árbol de configuración, expanda el elemento **Modelo de seguimiento del rendimiento** y seleccione el elemento **Formato de seguimiento del rendimiento**.
3. En el panel de acciones, haga clic en **Diseñador**.
4. En la página **Diseñador de formato**, en el panel de acciones seleccione **Seguimiento del rendimiento**.
5. En el cuadro **Valores del resultado de seguimiento del rendimiento**, seleccione **Importar seguimiento del rendimiento**.
6. Seleccione **Examinar**, para seleccionar el archivo zip que exportó anteriormente.
7. Seleccione **Aceptar**.

    ![Cuadro de diálogo de los valores del resultado de seguimiento del rendimiento del RCS.](./media/GER-PerfTrace-RCS-ImportedPerfTrace.png)

### <a name="use-the-performance-trace-for-analysis-in-rcs--format-execution"></a>Usar el seguimiento de rendimiento para el análisis en RCS – Formato de la ejecución

1. En el RCS, en la página **Diseñador de formato**, seleccione **Expandir/contraer** para ampliar el contenido de todos los artículos de formato.

    Observe que la información adicional se mostrará para algunos artículos de formato actual:

    - El tiempo real empleado que se usó para introducir datos en la salida generada mediante el elemento de formato
    - El mismo tiempo expresado como un porcentaje de tiempo total que se ha dedicado a generar toda la salida

    ![Página de diseñador de formato en RCS.](./media/GER-PerfTrace-RCS-TraceInfoInFormat.png)

2. Cierre la página **Diseñador de formato**.

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a><a id='use-trace'></a>Usar el seguimiento de rendimiento para el análisis en RCS – Distribución del modelo

1. En el RCS, en la página **Configuraciones**, en el árbol de configuración, seleccione el elemento **Distribución de seguimiento del rendimiento**.
2. En el panel de acciones, haga clic en **Diseñador**.
3. Seleccione **Diseñador**.
4. En la página **Diseñador de distribución del modelo**, en el panel de acciones seleccione **Seguimiento del rendimiento**.
5. Seleccione el seguimiento que importó anteriormente.
6. Seleccione **Aceptar**.

Observe que la nueva información está disponible para algunos artículos de orígenes de datos de la asignación del modelo actual:

- El tiempo real empleado que se usó para obtener datos mediante el origen de datos
- El mismo tiempo expresado como un porcentaje de tiempo total que se ha dedicado a ejecutar toda la distribución del modelo

Tenga en cuenta que el ER le informa de que la distribución del modelo actual duplica solicitudes de la base de datos mientras se ejecuta el origen de datos de VendTable/\<Relations/VendTrans.VendTable\_AccountNum. Esta duplicación ocurre porque la lista de transacciones de proveedor se llama dos veces para cada registro de proveedor iterado:

- Una llamada se hace para especificar los detalles de cada transacción en el modelo de datos, basándose en las vinculaciones configuradas.
- Una llamada se hace para especificar el número calculado de transacciones por proveedor en el modelo de datos.

![Mensaje sobre solicitudes duplicadas a la base de datos en la página de diseñador de la distribución del modelo en el RCS.](./media/GER-PerfTrace-RCS-TraceInfoInMapping1.png)

El valor **\[Q:530\]** indica que la tabla de VendTrans se llamó a 530 veces para devolver un registro desde esta tabla al origen de datos VendTable/\<Relations/VendTrans.VendTable\_AccountNum. El valor **\[530\]** indica que el origen de datos VendTable/\<Relations/VendTrans.VendTable\_AccountNum se ha llamado 530 veces para devolver un registro de ese origen de datos de y especificar detalles de en el modelo de datos.

Se recomienda que use la caché para el origen de datos VendTable/\<Relations/VendTrans.VendTable\_AccountNum para reducir el número de llamadas que se realizan para obtener los detalles de 265 transacciones y para ayudar a mejorar el rendimiento de la asignación de modelo.

También puede ser útil reducir el número de llamadas que se realizan al origen de datos de LedgerTransTypeList. Este origen de datos se usa para asociar cada valor de la anumeración **LedgerTransType** con su etiqueta. Mediante este origen de datos, puede buscar una etiqueta adecuada y especificarla en el modelo de datos para cada transacción de proveedor. El número actual de llamadas a este origen de datos (9027) es muy alto para 265 transacciones.

![La página de modelo del diseñador de asignación en RCS muestra 9027 llamadas al origen de los datos.](./media/GER-PerfTrace-RCS-TraceInfoInMapping1a.png)

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a>Mejorar la distribución del de modelo según la información de seguimiento de la ejecución

### <a name="modify-the-logic-of-the-model-mapping"></a>Modificar la lógica de la distribución del modelo

1. Siga estos pasos para utilizar la caché y ayudar a evitar llamadas duplicadas a la base de datos:

    1. En el RCS, en la página **Diseñador de la distribución del modelo**, en el panel **Orígenes de datos**, seleccione el elemento **VendTable**.
    2. Seleccione **Memoria caché**.
    3. Expanda el elemento **VendTable**, amplíe la lista de una-a-muchas relaciones para el origen de datos VendTable (el elemento **\<Relaciones** ), y seleccione el elemento **VendTrans.VendTable\_AccountNum**.
    4. Seleccione **Memoria caché**.

    ![Configurar la caché para ayudar a impedir llamadas duplicadas.](./media/GER-PerfTrace-RCS-ChangeMapping-Cache.png)

2. Siga estos pasos para llevar el origen de datos de LedgerTransTypeList al ámbito del origen de datos de VendTable:

    1. En el panel **Tipos de origen de datos**, expanda el elemento **Funciones**, y seleccione el elemento **Campo calculado**.
    2. En el panel **Orígenes de datos**, seleccione el elemento **VendTable**.
    3. Seleccione **Agregar**.
    4. En el campo **Nombre**, especifique **\$TransType**.
    5. Seleccione **Editar fórmula**.
    6. En el campo **Fórmula**, especifique **LedgerTransTypeList**.
    7. Seleccione **Guardar**.
    8. Cierre la página **Editor de la fórmula**.
    9. Haga clic en **Aceptar**.

3. Siga estos pasos para almacenar en la caché del campo **\$TransType**:

    1. Seleccionar el elemento **LedgerTransTypeList**.
    2. Seleccione **Memoria caché**.
    3. Seleccione el elemento **VendTable.\$TransType**.
    4. Seleccione **Memoria caché**.

    ![Configuración de la caché para el campo $TransType.](./media/GER-PerfTrace-RCS-ChangeMapping-Cache2.png)

4. Siga estos pasos para cambiar el campo **\$TransTypeRecord** de modo que empiece para utilizar el campo **\$TransType** almacenado en caché:

    1. En el panel **Orígenes de datos**, expanda el elemento **VendTable**, expanda el elemento **\<Relaciones**, expanda el elemento **VendTrans.VendTable\_AccountNum** y seleccione el elemento **VendTable. VendTrans.VendTable\_AccountNum.\$TransTypeRecord**.
    2. Seleccione **Editar**.
    3. Seleccione **Editar fórmula**.
    4. En el campo **Fórmula**, busque la expresión siguiente:

        FIRSTORNULL (WHERE (LedgerTransTypeList, LedgerTransTypeList.Enum = \@.TransType))

    5. En el campo **Fórmula**, introduzca la expresión siguiente:

        FIRSTORNULL (WHERE (VendTable.'\$TransType', VendTable.'\$TransType'.Enum = \@.TransType)).

    6. Seleccione **Guardar**.
    7. Cierre la página **Editor de la fórmula**.
    8. Seleccione **Aceptar**.

5. Seleccione **Guardar**.
6. Cierre la página **Diseñador de distribución del modelo**.
7. Cierre la página **Distribuciones del modelo**.

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a>Complete la versión modificada de la distribución del modelo de ER

1. En el RCS, en la página **Configuraciones**, en la ficha desplegable **Versiones**, seleccione la versión **1.2** de la configuración del **Seguimiento del rendimiento de la distribución**.
2. Seleccione **Cambiar estado**.
3. Seleccione **Completar**.

### <a name="import-the-modified-er-model-mapping-configuration-from-rcs-into-the-application"></a>Importe la configuración de modificación asignación del modelo de ER de RCS en la aplicación

Repita los pasos de la sección anterior [Importar una configuración de ER desde RCS a finanzas y operaciones](#import-configuration) en este artículo para importar la versión 1.2 de la configuración del **Seguimiento del rendimiento de la distribución**.

## <a name="run-the-modified-er-solution-to-trace-execution"></a>Ejecute la solución modificada de ER para realizar un seguimiento de la ejecución

### <a name="run-the-er-format"></a>Ejecutar formato del ER

Repita los pasos de la sección anterior [Ejecutar formato del ER](#run-format) en este artículo para generar un nuevo seguimiento del rendimiento.

## <a name="work-with-the-execution-trace"></a>Trabajar con el seguimiento de ejecución

### <a name="export-the-generated-trace-from-the-application"></a>Exporta el seguimiento generado de la aplicación

Repita los pasos de la sección anterior [Exportar el seguimiento generado desde la aplicación](#export-trace) en este artículo para guardar localmente un seguimiento del rendimiento nuevo.

### <a name="import-the-generated-trace-into-rcs"></a>Importar el seguimiento generado a RCS

Repita los pasos de la sección anterior [Importar el seguimiento generado a RCS](#import-trace) en este artículo para importar el seguimiento del rendimiento nuevo a RCS.

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a>Usar el seguimiento de rendimiento para el análisis en RCS – Distribución del modelo

Repita los pasos de la sección anterior [Usar el seguimiento del rendimiento para análisis en RCS - Distribución del modelo](#use-trace) en este artículo para analizar el último seguimiento del rendimiento.

Observe que los ajustes que realizó en la distribución de modelo han eliminado las consultas duplicadas en la base de datos. El número de llamadas a las tablas de base de datos y de orígenes de datos para esta distribución de modelo también se ha reducido. Por lo tanto, el rendimiento de la solución completa de ER ha mejorado.

![Seguir la información de la fuente de datos VendTable en la página del diseñador de distribución del modelo en RCS.](./media/GER-PerfTrace-RCS-TraceInfoInMapping2.png)

En la información de seguimiento, el valor **\[12\]** para el origen de datos de VendTable indica que este origen de datos se llamó 12 veces. El valor **\[Q:6\]** indica que seis llamadas se tradujeron en llamadas a la base de datos a la tabla de VendTable. El valor **\[C:6\]** indica que los registros que se recuperarán de la base de datos se almacenaron en caché, y seis otras llamadas se procesaran mediante la memoria caché.

Tenga en cuenta que el número de llamadas de origen de datos de LedgerTransTypeList se ha reducido de 9027 a 240.

![Seguir la información de la fuente de datos LedgerTransTypeList en la página del diseñador de distribución del modelo en RCS.](./media/GER-PerfTrace-RCS-TraceInfoInMapping2a.png)

## <a name="review-the-execution-trace-in-the-application"></a>Revise la ejecución seguida paso a paso en la aplicación

Además del RCS, algunas versiones pueden proporcionar las funciones de la experiencia del diseñador del marco de ER. Estas versiones tienen una opción **Habilitar diseño de modelo** que se puede activar. Puede encontrar esta opción en la pestaña **General** de la página **Parámetros de informes electrónicos**, que puede abrir desde el área de trabajo **Informes electrónico**.

![Habilite la opción del modo de diseño en la página de los parámetros de los informes electrónicos.](./media/GER-PerfTrace-GER-Parameters-DesignMode.png)

Si usa una de estas versiones, puede analizar los detalles de seguimientos generados por rendimiento directamente en la aplicación. No es necesario exportarlas desde la aplicación e importarlas al RCS.

## <a name="review-the-execution-trace-by-using-external-tools"></a>Revisar el seguimiento de ejecución mediante herramientas externas

### <a name="configure-user-parameters"></a>Configurar los parámetros del usuario

1. Vaya a **Administración de la organización \> Informes electrónicos \> Configuraciones**.
2. En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Configuración avanzada**, seleccione **Parámetros de usuario**.
3. En el cuadro **Parámetros de usuario**, en la sección **Seguimiento de la ejecución**, en el campo **Formato de seguimiento de la ejecución**, seleccione **PerfView XML**.

### <a name="run-the-er-format"></a>Ejecutar formato del ER

Repita los pasos de la sección anterior [Ejecutar formato del ER](#run-format) en este artículo para generar un nuevo seguimiento del rendimiento.

Observe que el explorador web proporciona un archivo zip para su descarga. Este archivo contiene el seguimiento del rendimiento en el formato de PerfView. Puede utilizar la herramienta de análisis de rendimiento de PerfView para analizar los detalles de la ejecución del formato de ER.

![Información de seguimiento de rendimiento en formato PerfView.](./media/GER-PerfTrace2-PerfViewTrace1.PNG)

## <a name="use-external-tools-to-review-an-execution-trace-that-includes-database-queries"></a>Utilice herramientas externas para revisar una seguimiento de ejecución que incluya consultas en bases de datos

Debido a mejoras que se han realizado en el marco de ER, el seguimiento del rendimiento que se genera en formato PerfView ofrece ahora más detalles sobre la ejecución del formato de ER. En la versión 10.0.4 de Microsoft Dynamics 365 Finance (julio de 2019), este seguimiento también puede incluir detalles de consultas SQL ejecutadas en la base de datos de aplicaciones.

### <a name="configure-user-parameters"></a>Configurar los parámetros del usuario

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Configuración avanzada**, seleccione **Parámetros de usuario**.
3. En el cuadro **Parámetros de usuario**, en la sección **Seguimiento de la ejecución**, establezca los siguientes parámetros:

    - En el campo **Formato de seguimiento de la ejecución**, seleccione **PerfView XML**.
    - Establezca la opción **Recopilar estadísticas de consulta** en **Sí**.
    - Establezca la opción **Consulta de seguimiento** en **Sí**.

    ![Sección de seguimiento de ejecución, cuadro de diálogo Parámetros de usuario.](./media/GER-PerfTrace2-GER-UserParameters.PNG)

### <a name="run-the-er-format"></a>Ejecutar formato del ER

Repita los pasos de la sección anterior [Ejecutar formato del ER](#run-format) en este artículo para generar un nuevo seguimiento del rendimiento.

Observe que el explorador web proporciona un archivo zip para su descarga. Este archivo contiene el seguimiento del rendimiento en el formato de PerfView. Puede utilizar la herramienta de análisis de rendimiento de PerfView para analizar los detalles de la ejecución del formato de ER. Este seguimiento ahora incluye los detalles del acceso a la base de datos SQL durante la ejecución del formato de ER.

![Información de seguimiento para el formato de ER ejecutado en PerfView.](./media/GER-PerfTrace2-PerfViewTrace2.PNG)

## <a name="additional-resources"></a>Recursos adicionales

- [Visión general de los informes electrónicos](general-electronic-reporting.md)
- [Mejorar el rendimiento de las soluciones de ER agregando orígenes de datos de CAMPO CALCULADO parametrizados](er-calculated-field-ds-performance.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

