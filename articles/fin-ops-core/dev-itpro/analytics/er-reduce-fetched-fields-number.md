---
title: Mejorar el rendimiento de las soluciones de ER al reducir la cantidad de campos de tabla que se localizan en runtime
description: Este tema explica cómo puede ayudar a mejorar el rendimiento al reducir la cantidad de campos de tabla que se localizan en runtime.
author: NickSelin
ms.date: 05/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: dd192a7718ac4fd8bcb636ede6c005ca29ee5f08
ms.sourcegitcommit: 336a0ad772fb55d52b4dcf2fafaa853632373820
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2022
ms.locfileid: "8811964"
---
# <a name="improve-performance-of-er-solutions-by-reducing-the-number-of-table-fields-that-are-fetched-at-runtime"></a>Mejorar el rendimiento de las soluciones de ER al reducir la cantidad de campos de tabla que se localizan en runtime

[!include[banner](../includes/banner.md)]

Puede diseñar [formatos](er-overview-components.md#format-components-for-outgoing-electronic-documents) de [informes electrónicos](general-electronic-reporting.md) (ER) que generen documentos salientes en varios formatos. Cuando se genera un documento, un formato de ER llama a los orígenes de datos que se configuraron en una [asignación de modelo](er-overview-components.md#model-mapping-component) de ER correspondiente. Para configurar el acceso a las tablas, consultas o entidades de la aplicación para la recuperación del registro, puede usar los orígenes de datos de ER del tipo *Registros de tabla*. Por defecto, un origen de datos del tipo *Registros de tabla* recupera los valores de todos los campos en los registros solicitados. Sin embargo, puede configurar este tipo de origen de datos para que obtenga solo los valores de campo que se requieren para el formato de ER en ejecución. Esta configuración ayuda a reducir el consumo de memoria del servidor de aplicaciones que realiza la recuperación de datos y el posterior almacenamiento en caché de registros.

Para obtener más información sobre cómo limitar la lista de campos obtenidos de fuentes de datos del tipo *Registros de tabla*, complete el ejemplo en este tema.

## <a name="example-reduce-the-number-of-table-fields-that-are-fetched-at-runtime"></a>Ejemplo: reducir la cantidad de campos de tabla que se obtienen en tiempo de ejecución

Los siguientes procedimientos muestran cómo un usuario con el rol de administrador del sistema o desarrollador de informes electrónicos puede configurar una asignación de modelo de ER para que obtenga solo los campos necesarios para ejecutar el formato de ER, para ayudar a reducir el consumo de memoria del servidor de aplicaciones.

Estos procedimientos se pueden llevar a cabo en la empresa **USMF**, en Microsoft Dynamics 365 Finance. No se requiere codificación.

Para completar este ejemplo, debe tener acceso a la empresa **USMF** para uno de los roles siguientes:

- Consultor funcional de informes electrónicos
- Administrador del sistema

En este ejemplo, usará las [configuraciones](general-electronic-reporting.md#Configuration) que se proporcionan para la empresa de ejemplo, **Litware, Inc**. Asegúrese de que está disponible el proveedor de la configuración para la empresa de ejemplo **Litware, Inc.** (`http://www.litware.com`) está en la lista del marco de ER y que está como **Activo**. Si este proveedor de configuración no aparece en la lista o si no está marcado como **Activo**, siga los pasos de [Crear un proveedor de configuración y marcarlo como activo](tasks/er-configuration-provider-mark-it-active-2016-11.md).

### <a name="configure-the-er-framework"></a>Configurar el marco ER

Siga los pasos de [Configurar el marco de ER](er-quick-start2-customize-report.md#ConfigureFramework) para configurar el conjunto mínimo de parámetros de ER. Debe completar esta configuración antes de comenzar a utilizar el marco de ER para modificar los orígenes de datos de la solución de ER proporcionada.

### <a name="import-the-sample-er-configurations"></a>Importar las configuraciones de ER de ejemplo

Si aún no ha completado el ejemplo en el tema [Diseñar una nueva solución de ER para imprimir un informe personalizado](er-quick-start1-new-solution.md), descargue y almacene localmente los archivos XML para las siguientes configuraciones de la solución de ER proporcionada.

| Descripción del contenido            | Nombre de archivo |
|--------------------------------|-----------|
| Configuración del modelo datos de ER    | [Cuestionarios model.version.1.xml](https://download.microsoft.com/download/b/6/3/b633bd34-d200-4422-96d9-8f62eb5218f8/Questionnaires_model.version.1.xml) |
| Configuración de la asignación del modelo ER | [Cuestionarios mapping.version.1.1.xml](https://download.microsoft.com/download/7/b/2/7b258e4e-4bd5-46a4-8114-27419ae4acd8/Questionnaires_mapping.version.1.1.xml) |
| Configuración del formato de ER        | [Cuestionarios format.version.1.1.xml](https://download.microsoft.com/download/1/b/a/1ba39ec2-257a-44d8-972f-25bf7d18fb41/Questionnaires_format.version.1.1.xml) |

Luego, siga estos pasos para cargar las configuraciones de la solución ER provista a su instancia de Finance.

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. Seleccione **Configuraciones de informes**.
3. En la página **Configuraciones**, importe la configuración del modelo de datos de ER.

    1. Seleccione **Intercambiar** y luego seleccione **Cargar desde archivo XML**.
    2. Seleccione **Examinar** y, a continuación, busque y seleccione el archivo **Cuestionarios model.version.1.xml**, y luego seleccione **Aceptar**.

4. Importar la configuración de la asignación del modelo de ER.

    1. Seleccione **Intercambiar** y luego seleccione **Cargar desde archivo XML**.
    2. Seleccione **Examinar** y, a continuación, seleccione el archivo **Cuestionarios mapping.version.1.1.xml** y luego seleccione **Aceptar**.

5. Importe la configuración de formato ER.

    1. Seleccione **Intercambiar** y luego seleccione **Cargar desde archivo XML**.
    2. Seleccione **Examinar** y, a continuación, seleccione el archivo **Cuestionarios format.version.1.1.xml** y luego seleccione **Aceptar**.

6. En el árbol de configuración, expanda **Modelo de cuestionarios**.
7. Revise la lista de configuraciones de ER importadas en el árbol de configuración.

    ![Revisión de la lista de configuraciones de ER importadas en la página Configuraciones.](./media/er-reduce-fetched-fields-number-configurations.png)

### <a name="review-the-provided-er-model-mapping"></a>Revisar la asignación de modelo de ER proporcionada

1. En la página **Configuraciones**, seleccione **Asignación de cuestionarios**.
2. En el panel de acciones, haga clic en **Diseñador**.
3. En la página **Asignación de modelo a origen de datos**, seleccione **Diseñador**.
4. En la página **Diseñador de asignación de modelos**, en el Panel de acciones, seleccione **Vista de grupo** para activar la vista **Grupo**.
5. En el panel **Modelo de datos**, expanda **Cuestionario**.

    Tenga en cuenta que el origen de datos **Cuestionario** se ha configurado para acceder a la tabla de la aplicación `KMCollection`.

6. En el panel **Orígenes de datos**, expanda **Registros de tabla** \> **Cuestionario** \> **Campos**.

    Observe cuántos campos de la tabla de aplicación `KMCollection` están expuestos por el origen de datos **Cuestionario** del tipo *Registros de tabla*.

    ![Revisión de la asignación de modelos proporcionada en la página del diseñador de asignación de modelos cuando la vista de grupo está activada.](./media/er-reduce-fetched-fields-number-mapping1.png)

7. En el panel de acciones, seleccione **Vista de grupo** otra vez para desactivar **Grupo** y luego seleccione **Mostrar todo** \> **Mostrar solo asignados**.

    Observe que algunos campos de la tabla de aplicación `KMCollection` se utilizan para completar la lista de registros **Cuestionario** en el modelo de datos ER:

    - `Active`
    - `Description`
    - `questionMode`
    - `kmCollectionId`

    ![Revisión de la asignación de modelos proporcionada en la página del diseñador de asignación de modelos cuando la vista de grupo está desactivada.](./media/er-reduce-fetched-fields-number-mapping2.png)

### <a name="turn-on-the-er-performance-trace"></a>Activar el seguimiento del rendimiento de ER

Siga los pasos de [Activar el seguimiento de rendimiento de ER](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace) para establecer los parámetros de usuario de ER que permiten rastrear la ejecución de los componentes de ER.

### <a name="run-the-provided-er-format-by-using-the-provided-model-mapping"></a>Ejecutar el formato de ER proporcionado usando el mapeo del modelo proporcionado

Siga los pasos de [Ejecutar un formato diseñado desde ER](er-quick-start1-new-solution.md#RunFormatFromER) para ejecutar el formato de ER provisto para un solo cuestionario desde la página **Configuraciones**.

### <a name="review-the-execution-trace-of-the-first-run"></a>Revise el rastreo de la primera ejecución

1. Vaya a **Administración de la organización** \> **Informes electrónicos \> Configuraciones**.
2. En la página **Configuraciones**, amplíe **Modelo de cuestionarios** y seleccione **Asignación de cuestionarios**.

    > [!NOTE]
    > Los detalles de la ficha desplegable **Versiones** indican que seleccionó la versión de borrador de la configuración **Asignación de cuestionarios**. Por lo tanto, puede modificar el contenido de esta asignación de modelo.

3. En el panel de acciones, haga clic en **Diseñador**.
4. En la página **Asignación de modelo a origen de datos**, seleccione **Diseñador**.
5. En la página **Diseñador de distribución del modelo**, en el panel de acciones seleccione **Seguimiento del rendimiento**.
6. En el cuadro de diálogo **Configuración de resultados de seguimiento de rendimiento**, seleccione el seguimiento que se generó durante la última ejecución de formato.

    ![Selección del seguimiento en el cuadro de diálogo de condiguración de resultados de seguimiento del rendimiento.](./media/er-reduce-fetched-fields-number-select-trace-1.png)

7. Seleccione **Aceptar**. 
8. En la ficha desplegable **Detalles**, filtre la ruta de acceso a **Cuestionario** que apunte al origen de datos **Cuestionario**.
9. Revise los detalles de la consulta de la base de datos que se generó cuando se llamó al origen de datos **Cuestionario**.

    Observe que todos los campos de la tabla de aplicación `KMCollection` se recuperaron en runtime cuando se llamó al origen de datos **Cuestionario**.

    ![Revisión de los detalles de la consulta de la base de datos en la página del diseñador de asignación de modelos.](./media/er-reduce-fetched-fields-number-query1.png)

### <a name="modify-the-provided-er-model-mapping"></a>Modificar la asignación de modelo de ER proporcionada

1. En la página **Diseñador de asignación de modelo**, en el panel **Orígenes de datos**, seleccione el origen de datos **Cuestionario**.
2. En el panel **Orígenes de datos** seleccione **Editar**.
3. En el cuadro de diálogo **Propiedades del origen de datos**, seleccione **Seleccionar campos** para especificar la lista de campos de la tabla de aplicación `KMCollection` que se recuperará en runtime cuando se llame al origen de datos **Cuestionario**.

    ![Seleccione Seleccionar campos en el cuadro de diálogo Propiedades del origen de datos para configurar la lista de campos que se recuperarán de la tabla de aplicación utilizando el origen de datos editable.](./media/er-reduce-fetched-fields-number-select-fields1.png)

4. En la página **Seleccionar campos**, seleccione **Autocompletar**.

    La lista **Campos seleccionados** se completa automáticamente, en función de los artefactos preconfigurados de la asignación del modelo. Todos los campos y relaciones de la tabla a la que se hace referencia que se mencionan en cualquier enlace, fórmula o origen de datos de la asignación del modelo se agregan a la lista.

    ![Configure la lista de campos que se obtendrán de la tabla de la aplicación en la página Seleccionar campos.](./media/er-reduce-fetched-fields-number-select-fields2.png)

5. Seleccione **Guardar** y cierre la página **Seleccionar campos**.
6. Seleccione **Aceptar** para almacenar los cambios que ha realizado en la configuración del origen de datos.
7. En el panel de acciones, seleccione **Mostrar todo**.

    Tenga en cuenta que el origen de datos **Cuestionario** ahora muestra el texto **\<Fields are filtered\>**. Este texto indica que el origen de datos se configuró para obtener un número limitado de campos de la tabla de aplicación referenciada.

    ![Revisión de las asignaciones del modelo actualizado en la página del diseñador de asignación de modelos.](./media/er-reduce-fetched-fields-number-mapping3.png)

8. Seleccione **Guardar** para almacenar los cambios que ha realizado en la asignación de modelo editable.

    > [!NOTE]
    > En tiempo de ejecución, ER analiza las relaciones agregadas y agrega todos los campos que se usan en ellas a la consulta de la base de datos, incluso si esos campos no se agregaron explícitamente a la lista de campos obtenidos en el momento del diseño.

### <a name="run-the-provided-er-format-by-using-the-updated-model-mapping"></a>Ejecutar el formato de ER proporcionado usando el mapeo del modelo actualizado

Siga los pasos de [Ejecutar un formato diseñado desde ER](er-quick-start1-new-solution.md#RunFormatFromER) para ejecutar el formato de ER provisto para un solo cuestionario desde la página **Configuraciones**.

### <a name="review-the-execution-trace-of-the-second-run"></a>Revisar el seguimiento de ejecución de la segunda ejecución

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, amplíe **Modelo de cuestionarios** y seleccione **Asignación de cuestionarios**.
3. En el panel de acciones, haga clic en **Diseñador**.
4. En la página **Asignación de modelo a origen de datos**, seleccione **Diseñador**.
5. En la página **Diseñador de distribución del modelo**, en el panel de acciones seleccione **Seguimiento del rendimiento**.
6. En el cuadro de diálogo **Configuración de resultados de seguimiento de rendimiento**, seleccione el seguimiento que se generó durante la última ejecución de formato.
7. Seleccione **Aceptar**.
8. En la ficha desplegable **Detalles**, filtre la ruta de acceso a **Cuestionario** que apunte al origen de datos **Cuestionario**.
9. Revise los detalles de la consulta de la base de datos que se generó cuando se llamó al origen de datos **Cuestionario**.

    Tenga en cuenta que solo los campos que se requieren para completar el origen de datos se recuperaron en runtime desde la tabla de aplicación `KMCollection` cuando se llamó al origen de datos **Cuestionario**.

    > [!NOTE]
    > Algunos campos, como los campos para el id. de la partición, el id. del área de datos y el id. del registro, se agregan automáticamente mediante el marco Administración de datos de la aplicación Finance.

    ![Revisión de los detalles de la consulta de la base de datos para la asignación de modelo actualizaada en la página del diseñador de asignación de modelos.](./media/er-reduce-fetched-fields-number-query2.png)

Puede utilizar esta técnica para reducir la cantidad de registros obtenidos cuando debe reducir el consumo de memoria mediante la ejecución de la asignación del modelo de ER y el formato de ER.

## <a name="limitations"></a>Limitaciones

Cuando limita el número de campos obtenidos para un origen de datos del tipo *Registros de tabla*, no puede usar los métodos de una tabla de aplicación a la que hace referencial origen de datos, porque los metadatos de la aplicación no proporcionan información sobre los campos de la tabla que se requieren para llamar a esos métodos.

## <a name="usage-notes"></a>Notas de uso

Aunque el comando **Autocompletar** agrega campos automáticamente, no elimina automáticamente los campos agregados previamente, incluso si ya no se usan en enlaces, fórmulas ni fuentes de datos de la asignación del modelo editable.

Cuando selecciona **Autocompletar**, ER analiza los enlaces, las fórmulas y las fuentes de datos que tenía la asignación del modelo editable cuando la abrió para editarla. Si cambia enlaces, fórmulas y orígenes de datos de la asignación de modelo editable y desea utilizar el comando **Autocompletar**, cierre el diseñador de asiganción de modelos y luego vuelva a abrirlo para editar su asignación de modelo. 

## <a name="additional-resources"></a>Recursos adicionales

- [Realizar un seguimiento de la ejecución de los formatos de ER para solucionar problemas de rendimiento](trace-execution-er-troubleshoot-perf.md)
- [Solución de problemas de rendimiento en configuraciones de ER](er-troubleshoot-perf-issues-in-configurations.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
