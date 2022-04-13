---
title: Registros de grupos y cálculos agregados mediante fuentes de datos GROUPBY
description: En este tema se explica cómo puede usar orígenes de datos de tipo GROUPBY en informes electrónicos (ER).
author: NickSelin
ms.date: 03/18/2022
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
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3b79dfe62122a031ae9ed7f51ea7ff578cd47358
ms.sourcegitcommit: c0f7ee7f8837fec881e97b2a3f12e7f63cf96882
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2022
ms.locfileid: "8462308"
---
# <a name="group-records-and-aggregate-calculations-by-using-groupby-data-sources"></a>Registros de grupos y cálculos agregados mediante fuentes de datos GROUPBY

[!include[banner](../includes/banner.md)]

Al configurar las asignaciones o los formatos de [modelos electrónicos (ER)](general-electronic-reporting.md), puede [agregar](#AddMmDataSource2) los orígenes de datos requeridos del tipo **GroupBy**.

En tiempo de diseño, un origen de datos **GroupBy** se configura para identificar los siguientes elementos:

- Un [origen de datos base](#BaseDataSource) que contiene registros que se agruparán en tiempo de ejecución
- [Agrupación de campos](#GroupingFields) del origen de datos base, que se utilizará para la agrupación de registros en tiempo de ejecución
- [Funciones agregadas](#AggregateFunctions) que especifican los cálculos agregados que se realizarán para cada grupo descubierto en tiempo de ejecución

En tiempo de ejecución, un origen de datos configurado **GroupBy** agrupa los registros que tienen los mismos valores en los campos de agrupación y luego devuelve una lista de registros. Cada registro representa un solo grupo. Para cada grupo, la fuente de datos expone los valores de campo por los que se agruparon los registros iniciales, los valores de las funciones agregadas calculadas y la lista de registros de la fuente de datos base que pertenece al grupo.

## <a name="aggregate-functions"></a><a name="AggregateFunctions"></a>Funciones de agregado

En tiempo de ejecución, cada cálculo agregado se realiza para cada grupo de registros. Este cálculo se realiza utilizando el valor de un solo campo o una expresión en los registros de una fuente de datos que se seleccionó para agrupar en la fuente de datos editable del tipo **GroupBy**. Actualmente se admiten los siguientes tipos de funciones de agregados:

- **AVG** – Esta función devuelve el promedio de los valores en un grupo. Solo se puede utilizar con campos numéricos.
- **COUNT** – Esta función devuelve el número de elementos que se encontraron en un grupo.
- **Min** – Esta función devuelve el valor mínimo entre los valores de un grupo.
- **Max** – Esta función devuelve el valor máximo entre los valores de un grupo.
- **SUM** – Esta función devuelve la suma de todos los valores en un grupo. Solo se puede utilizar con campos numéricos.

## <a name="execution-location"></a><a name="ExecutionLocation"></a>Ubicación de ejecución

Cuando edita un origen de datos **GroupBy** y especifica el origen de datos base que contiene los registros que se deben agrupar, el sistema detecta automáticamente la [ubicación](#ExecutionLocation) más eficiente para la ejecución de ese origen de datos **GroupBy**. Si el origen de datos base es [consultable](er-functions-list-filter.md#usage-notes) (es decir, si se puede ejecutar a nivel de la base de datos), la base de datos de la aplicación también se especifica como la ubicación de ejecución del origen de datos editable **GroupBy**. De lo contrario, la memoria del servidor de aplicaciones se especifica como la ubicación de ejecución.

Puede cambiar manualmente la ubicación de ejecución detectada automáticamente seleccionando la ubicación aplicable a la fuente de datos configurada. Si la ubicación de ejecución que se selecciona no es aplicable, se inicia un [error de validacion](er-components-inspections.md#i5) en tiempo de diseño.

> [!TIP]
> Le recomendamos que utilice la ubicación de la base de datos para agrupar fuentes de datos que exponen una gran cantidad de registros.

## <a name="memory-consumption"></a><a name="MemoryConsumption"></a>Consumo de memoria

Por defecto, si un origen de datos **GroupBy** se ejecuta en memoria, la memoria del servidor de aplicaciones se utiliza para almacenar registros de la fuente de datos base que pertenece a cada grupo descubierto como registros de un solo grupo. Para ayudar a reducir el consumo de memoria, puede suprimir el almacenamiento de registros para orígenes de datos **GroupBy** si se configuraron para calcular solo funciones agregadas y los registros de su grupo no se usan en tiempo de ejecución. Para reducir el consumo de memoria de esta manera, habilite la característica **Reduzca el uso de memoria en ER cuando la agrupación de registros solo se usa para calcular agregaciones** en el espacio de trabajo **Gestión de características**.

## <a name="alternatives"></a><a name="Alternatives"></a>Alternativas

Se pueden calcular agregaciones similares usando [diferentes](er-data-collection-data-sources.md#if-i-have-to-calculate-running-totals-and-collect-data-what-is-the-difference-between-using-a-data-collection-data-source-and-using-the-built-in-data-collection-functions) tipos de fuentes de datos o funciones integradas de ER.

Para obtener más información sobre esta funcionalidad, complete el siguiente ejemplo.

## <a name="example-use-a-groupby-data-source-for-aggregate-calculations-and-record-grouping"></a><a name="Example"></a>Ejemplo: usar una fuente de datos GROUPBY para cálculos agregados y agrupación de registros

Este ejemplo muestra cómo un usuario con la función de Administrador del sistema o Consultor funcional de informes electrónicos puede configurar una asignación de modelo de ER que tiene un origen de datos **GROUPBY** que se utiliza para calcular funciones agregadas y agrupar registros. Este mapeo de modelos se utiliza para imprimir el informe de control cuando se genera la declaración de Intrastat. Ese informe le permite revisar las transacciones de Intrastat informadas.

Los procedimientos de este ejemplo se pueden completar en la empresa **DEMF** en Microsoft Dynamics 365 Finance. 

### <a name="prepare-sample-data"></a>Preparar datos de muestra

Asegúrese de tener transacciones Intrastat de las que informar en la página **Intrastat**. Debe tener transacciones para diferentes códigos de transporte, porque agrupará las transacciones por el campo **Transporte** en este ejemplo.

![Preparación de transacciones Intrastat en la página Intrastat.](./media/er-groupby-data-sources-prepare-transactions.png)

### <a name="configure-the-er-framework"></a>Configurar el marco ER

Siga los pasos de [Configurar el marco de ER](er-quick-start2-customize-report.md#ConfigureFramework) para configurar el conjunto mínimo de parámetros de ER. Debe completar esta configuración antes de comenzar a utilizar el marco ER para diseñar una asignación de modelo ER.

### <a name="import-the-standard-er-format-configuration"></a>Importar configuraciones del formato estándar de ER

Siga los pasos de [Importar la configuración de formato estándar de ER](er-quick-start2-customize-report.md#ImportERSolution1) para agregar las configuraciones de ER estándar a su instancia actual de Dynamics 365 Finance. Importar la versión 1 de la configuración del **modelo intrastat** desde el repositorio.

### <a name="create-a-custom-data-model-configuration"></a>Crear una configuración de modelo de datos personalizada

Siga los pasos en [Agregar una configuración de modelo de datos personalizada](er-quick-start3-customize-report.md#add-a-custom-data-model-configuration) para agregar manualmente una nueva configuración del modelo de datos de ER del **Modelo Intrastat (Litware)** que se deriva de la configuración del **modelo Intrastat** importado.

### <a name="configure-a-custom-data-model-component"></a>Configurar un componente del modelo de datos personalizado

Siga estos pasos para realizar los cambios necesarios en el modelo de datos derivado **Modelo Intrastat (Litware)**, de modo que pueda usarse para exponer códigos de transporte que tengan los detalles requeridos.

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuraciones, seleccione **Modelo instrastat (Litware)**.
3. Seleccione **Diseñador**.
4. En la página **Diseñador de modelo de datos**, en el árbol del modelo, seleccione **Intrastat**.
5. Seleccione **Nuevo** para agregar un nuevo nodo anidado para el nodo seleccionado **Intrastat**. En el cuadro de diálogo desplegable para agregar un nodo de modelo de datos, siga estos pasos:

    1. En el campo **Nombre**, especifique **Transporte**.
    2. En el campo **Tipo de artículo**, seleccione **Lista de registros**.
    3. Seleccione **Agregar** para agregar el nuevo nodo.

6. Seleccione **Nuevo** para agregar un nuevo nodo anidado para el nodo **Transporte** que acaba de agregar. En el cuadro de diálogo desplegable para agregar un nodo de modelo de datos, siga estos pasos:

    1. En el campo **Nombre**, escriba **Código**.
    2. En el campo **Tipo de artículo**, seleccione **Cadena**.
    3. Seleccione **Agregar** para agregar el nuevo nodo.

7. Seleccione **Nuevo** para agregar otro nuevo nodo anidado para el nodo **Transporte**. En el cuadro de diálogo desplegable para agregar un nodo de modelo de datos, siga estos pasos:

    1. En el campo **Nombre**, introduzca **TotalInvoicedAmount**.
    2. En el campo **Tipo de artículo**, seleccione **Real**.
    3. Seleccione **Agregar** para agregar el nuevo nodo.

8. Seleccione **Nuevo** para agregar otro nuevo nodo anidado para el nodo **Transporte**. En el cuadro de diálogo desplegable para agregar un nodo de modelo de datos, siga estos pasos:

    1. En el campo **Nombre**, introduzca **NumberOfTransactions**.
    2. En el campo **Tipo de artículo**, seleccione **Entero**.
    3. Seleccione **Agregar** para agregar el nuevo nodo.

9. Seleccione **Nuevo** para agregar otro nuevo nodo anidado para el nodo **Transporte**. En el cuadro de diálogo desplegable para agregar un nodo de modelo de datos, siga estos pasos:

    1. En el campo **Nombre**, introduzca **Transacción**.
    2. En el campo **Tipo de artículo**, seleccione **Lista de registros**.
    3. Seleccione **Agregar** para agregar el nuevo nodo.

10. Para el nodo **Transacción** que acaba de agregar, en la ficha desplegable **Nodo**, seleccione **Cambiar la referencia del artículo**.
11. En el cuadro de diálogo **Cambiar la referencia del artículo**, en el árbol del modelo de datos, seleccione **CommodityRecord**. A continuación seleccione **Aceptar**.

![Modelo de datos configurado en el diseñador de modelo de datos de ER.](./media/er-groupby-data-sources-configure-data-model.png)

### <a name="complete-the-design-of-a-custom-data-model"></a>Completar el diseño de un modelo de datos personalizado

Siga los pasos en [Completar el diseño del modelo de datos](er-quick-start3-customize-report.md#add-a-custom-data-model-configuration) para completar el diseño del modelo de datos derivado **Modelo Intrastat (Litware)**.

### <a name="create-a-new-model-mapping-configuration"></a>Crear una nueva configuración de asignación de modelo

Siga los pasos en [Crear una nueva configuración de asignación de modelo](er-quick-start1-new-solution.md#CreateModelMapping) para agregar manualmente una nueva configuración de asignación del modelo ER **Asignación de ejemplo Intrastat** que se deriva de la configuración del **modelo Intrastat (Litware)**.

### <a name="add-a-new-model-mapping-component"></a>Agregar un nuevo componente de asignación de modelo

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuraciones, expanda la configuración **Modelo de intrastat**.
3. Seleccione la configuración **Asignación de muestra de Intrastat**.
4. Seleccione **Diseñador** para abrir la lista de asignaciones.
5. Seleccione **Borrar** para eliminar el componente de asignación existente.
6. Seleccione **Nuevo** para agregar un nuevo componente de asignación.
7. En el campo **Definición**, seleccione **Intrastat**.
8. En el campo **Nombre**, escriba **Asignación Intrastat**.
9. Seleccione **Diseñador** para configurar la nueva asignación.

### <a name="design-the-added-model-mapping-component"></a>Diseñar el componente de asignación de modelo agregado

#### <a name="add-a-data-source-to-access-an-application-table"></a><a name="AddMmDataSource1"></a>Agregar un origen de datos para acceder a una tabla de aplicación

Configure un origen de datos para acceder a las tablas de la aplicación que contienen los detalles de las transacciones Intrastat.

1. En la página **Diseñador de asignación de modelo**, en el panel **Tipos de origen de datos**, seleccione **Dynamics 365 for Operations\\Registros de tabla**.
2. En el panel **Orígenes de datos**, seleccione **Añadir raíz** para agregar una nueva fuente de datos que se usará para acceder a la tabla **Intrastat**. Cada registro en la tabla **Intrastat** representa una única transacción de Intrastat.
3. En el cuadro de diálogo **Propiedades del origen de datos**, en el campo **Nombre**, introduzca **Transacción**.
4. En el campo **Tabla**, escriba **Intrastat**.
5. Seleccione **Aceptar** para agregar el nuevo origen de datos.

#### <a name="add-a-data-source-to-group-intrastat-transactions"></a><a name="AddMmDataSource2"></a>Agregue una fuente de datos para agrupar transacciones de Intrastat

Configurar un origen de datos **GroupBy** para agrupar transacciones Intrastat y calcular funciones agregadas.

1. En la página **Diseñador de asignación de modelo**, en el panel **Tipos de origen de datos**, seleccione **Funciones\\Agrupar por**.
2. En el panel **Orígenes de datos**, seleccione **Añadir raíz** para agregar una nueva fuente de datos que se usará para agrupar las transacciones Intrastat y calcular las funciones de agregado.
3. En el cuadro de diálogo **Propiedades del origen de datos**, en el campo **Nombre**, introduzca **TransportRecord**.
4. Seleccione **Editar grupo por** para configurar las condiciones de agrupación.
5. En la página **Editar parámetros de 'Agrupar por'**, en la lista de fuentes de datos en el panel derecho, seleccione el origen de datos **Transacción** y expandirlo.
6. Seleccione **Agregar campo a \> Que agrupar** para indicar que el origen de datos **Transacción** se selecciona como el <a name="BaseDataSource">origen de datos base</a> para el origen de datos **GroupBy** configurado. Los registros del origen de datos **Transacción** se agruparán y los valores de campo de esta fuente de datos se utilizarán para cálculos en funciones agregadas.
7. Seleccione el campo **Transacción\Transporte** y, a continuación, seleccione **Agregar campo a \> Campo agrupado** para indicar que el campo del origen de datos **Transporte** base se selecciona como el <a name="GroupingFields">criterio de agrupación</a> para el origen de datos configurado **GroupBy**. En otras palabras, los registros del origen de datos **Transacción** se agrupará en función del valor del campo **Transporte**. Cada registro del origen de datos configurado **GroupBy** representará un único código de transporte que se ha encontrado en los registros de la fuente de datos base.
8. Seleccione el campo **Transacción\AmountMST** y luego siga estos pasos:

    1. Seleccione **Agregar campo a \> Campos agregados** para indicar que una <a name="AggregateFunctions">función agregada</a> será calculada para este campo.
    2. En el panel **Agregaciones**, en el registro que se ha agregado para el campo seleccionado **Transacción\AmountMST**, en el campo **Método**, seleccione la función **Suma**.
    3. En el campo opcional **Nombre**, introduzca **TotalInvoicedAmount**.

    Estos ajustes especifican que, para cada grupo de transporte, el importe total del campo **Transacción\AmountMST** se calculará.

9. Seleccione el campo **Transacción\RecId** y luego siga estos pasos:

    1. Seleccione **Agregar campo a \> Campos agregados** para indicar que una función agregada será calculada para este campo.
    2. En el panel **Agregaciones**, en el registro que se ha agregado para el campo seleccionado **Transacción\RecId**, en el campo **Método**, seleccione la función **Count**.
    3. En el campo opcional **Nombre**, introduzca **NumberOfTransactions**.

    Estos ajustes especifican que, para cada grupo de transporte, se calculará el número de transacciones del grupo.

10. Seleccione **Guardar**.
11. Revise los parámetros de <a name="ExecutionLocation">ejecución</a> del origen de datos editable. Debe darse cuenta de que **Detección automática** ha sido seleccionado automáticamente en el campo **Lugar de ejecución** y el campo **Ejecución en** campo contiene el valor **SQL**. Estos ajustes especifican que el origen de datos base seleccionado **Transacción** es actualmente consultable y puede ejecutar el origen de datos editable **GroupBy** a nivel de base de datos.
12. Abra la búsqueda del campo **Lugar de ejecución** para revisar la lista de valores disponibles. Tenga en cuenta que puede seleccionar **Consulta** o **En memoria** para forzar que el origen de datos **GroupBy** se ejecute en el nivel de la base de datos o en la memoria del servidor de aplicaciones.
13. Selecione **Guardar** y cierre la página **Editar parámetros 'Agrupar por'**.
14. Seleccione **OK** para completar la configuración del origen de datos **GroupBy**.

#### <a name="bind-the-groupby-data-source-to-data-model-fields"></a><a name="AddMmBindings"></a>Enlazar el origen de datos GroupBy a campos de modelo de datos

Enlace el origen de datos configurado a los campos del modelo de datos para especificar cómo se completará el modelo de datos con los datos de la aplicación en tiempo de ejecución.

1. En la página **Diseñador de asignación de modelo**, en el panel **Modelo de datos**, expanda el nodo **Transporte**.
2. En el panel **Fuentes de datos**, expanda la fuente de datos **TransportRecord**.
3. Agregue un enlace para exponer la lista de grupos de transporte descubiertos:

    1. En el panel **Modelo de datos**, seleccione el elemnto **Transporte**.
    2. En el panel **Fuentes de datos**, seleccione la fuente de datos **TransportRecord**.
    3. Seleccione **Enlazar**.

4. Agregue un enlace para exponer el código de transporte de cada grupo de transporte descubierto:

    1. Seleccione el elemento de modelo de datos **Transport.Code**.
    2. Seleccione el campo agrupado **TransportRecord.grouped.TransportMode**.
    3. Seleccione **Enlazar**.

5. Agregue un enlace para exponer los valores de las funciones agregadas calculadas para cada grupo de transporte descubierto:

    1. Seleccione el elemento de modelo de datos **Transport.NumberOfTransactions**.
    2. Seleccione el campo agregado **TransportRecord.aggregated.NumberOfTransactions**.
    3. Seleccione **Enlazar**.
    4. Seleccione el elemento de modelo de datos **Transport.TotalInvoicedAmount**.
    5. Seleccione el campo agregado **TransportRecord.aggregated.TotalInvoicedAmount**.
    6. Seleccione **Enlazar**.

6. Agregue un enlace para exponer los registros de transacciones que pertenecen a cada grupo de transporte descubierto:

    1. Seleccione el elemento de modelo de datos **Transport.Transaction**.
    2. Seleccione el campo **TransportRecord.líneas**.
    3. Seleccione **Enlazar**.

    Puede continuar configurando enlaces para los elementos anidados del elemento de modelo de datos **Transporte.Transacción** y el campo de fuente de datos **TransportRecord.líneas** para exponer, en tiempo de ejecución, los detalles de las transacciones de Intrastat que pertenecen a cada grupo de transporte descubierto.

![Asignación de datos configurada en el diseñador de asignación de modelo de ER.](./media/er-groupby-data-sources-configure-model-mapping.png)

### <a name="debug-the-added-model-mapping-component"></a>Depurar el componente de asignación de modelo agregado

Use el [depurador de la fuente de datos ER](er-debug-data-sources.md) para probar el mapeo del modelo configurado.

1. En la página **Diseñador de asignación de modelo**, seleccione **Iniciar depuración**.
2. En la página **Depurar orígenes de datos** en el panel de la izquierda, seleccione la fuente de datos **TransportRecord** y luego seleccione **Leer todos los registros**.
3. Expanda el origen de datos **TransportRecord** y después siga estos pasos:

    1. Seleccione el origen de datos **TransportRecord.grouped.TransportMode**.
    2. Seleccione **Obtener valor**.
    3. Seleccione el origen de datos **TransportRecord.grouped.NumberOfTransactions**.
    4. Seleccione **Obtener valor**.
    5. Seleccione el origen de datos **TransportRecord.grouped.TotalInvoicedAmount**.
    6. Seleccione **Obtener valor**.

4. En el panel derecho, seleccione **Expandir todo**.

La fuente de datos **TransportRecord** expone dos registros y presenta dos códigos de transporte. Para cada código de transporte se calcula el número de transacciones y el importe total facturado.

> [!NOTE]
> El enfoque de "lectura perezosa" se utiliza cuando un origen de datos **GroupBy** se llama para optimizar las llamadas a la base de datos. Por lo tanto, algunos de los valores de campo en un origen de datos **GroupBy** se calcula en el depurador de origen de datos de ER solo cuando están vinculados a campos de modelo de datos.

![Resultados de la depuración del origen de datos en la página Depurar orígenes de datos.](./media/er-groupby-data-sources-debug-datasource.png)

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="is-there-any-way-to-calculate-grand-totals-when-the-group-totals-are-calculated"></a>¿Hay alguna forma de calcular los totales generales cuando se calculan los totales del grupo?

Sí. Para calcular los totales generales, configure otro origen de datos **GroupBy** donde el origen **GroupBy** que configuró previamente se utiliza como origen de datos base. La siguiente ilustración muestra la fuente de datos **Totales** del tipo **GroupBy** que se utiliza para calcular la función agregada **SUMA**, basada en la agregación **SUMA** del origen de datos **TransportRecord** del tipo **GroupBy**.

![Calcula el total del origen de datos en el diseñador de asignación de modelo de ER.](./media/er-groupby-data-sources-configure-model-mapping2.png)

La siguiente ilustración muestra los resultados de la depuración de fuente de datos **Totales**.

![Resultados de la depuración del origen de datos Totales en la página Depurar orígenes de datos.](./media/er-groupby-data-sources-debug-datasource2.png)

## <a name="additional-resources"></a>Recursos adicionales

- [Visión general de los informes electrónicos](general-electronic-reporting.md)
- [Depurar las fuentes de datos de un formato ER ejecutado para analizar el flujo de datos y la transformación](er-debug-data-sources.md)
- [Utilizar orígenes de datos de RECOPILACIÓN DE DATOS en formatos de informes electrónicos](er-data-collection-data-sources.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
