---
title: Solución de problemas de rendimiento en configuraciones de ER
description: Este artículo explica cómo encontrar y solucionar problemas de rendimiento en configuraciones de informes electrónicos (ER).
author: NickSelin
ms.date: 05/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner, ERFormatMappingRunJobTable, ERParameters, ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: maximbel
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 28ff68309bad7a6c1b6009ba03ef4b20aceb5194
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847351"
---
# <a name="troubleshooting-performance-issues-in-er-configurations"></a>Solución de problemas de rendimiento en configuraciones de ER

Este artículo explica cómo encontrar y solucionar problemas de rendimiento en [configuraciones](general-electronic-reporting.md#Configuration) de [informes electrónicos](general-electronic-reporting.md) (ER).

Normalmente, la investigación del rendimiento consta de varios pasos.

1. [Recopilar](#collecting-data) datos.
2. Analizar los datos recopilados.
3. Según los resultados del análisis, utilizar configuraciones ER para [hacer cambios](#making-changes) o decidir recopilar más datos.

## <a name="troubleshooting"></a>Solución de problemas

### <a name="analyze-execution-time"></a>Analizar el tiempo de ejecución

El tiempo de ejecución puede depender de factores impredecibles, como otras tareas que se ejecutan en el mismo entorno y el almacenamiento en caché que utiliza datos cuando se llama por primera vez. Por lo tanto, debe repetir la ejecución y la medición varias veces.

A veces, los problemas de rendimiento no se deben a una configuración de formato ER que se utiliza para generar informes. En cambio, son causados por el código X ++ que se usa para abrir esa configuración de formato ER.

1. Tanto en el [Centro de Acción](#infolog-time) como en el [registro de eventos](#event-log-time), mire el tiempo de ejecución del informe.
2. Compare el tiempo de ejecución del informe con el tiempo total de ejecución en el escenario.
3. Si el tiempo de ejecución del informe es mucho menor que el tiempo total de ejecución, considere la cantidad de datos que procesa el informe:

    - Si el informe procesa una pequeña cantidad de datos, el problema puede implicar el tiempo de carga de la configuración.
    - Si el informe procesa una gran cantidad de datos, el problema puede implicar el preprocesamiento de X++. Usar el [Analizador de seguimiento](#analyze-trace-parser-trace) para analizar este caso.

    Para otros casos, consulte las siguientes secciones.

4. Ejecute varias pruebas que involucren diferentes cantidades de datos para determinar cómo el tiempo de ejecución depende de la cantidad de datos.

### <a name="analyze-trace-parser-traces"></a><a name="analyze-trace-parser-trace"></a>Analizar seguimientos de Trace Parser

Prepare un pequeño ejemplo o recopile varios seguimientos durante partes aleatorias de la generación del informe.

Entonces, en [Analizador de seguimiento](#trace-parser), realice un análisis estándar de abajo hacia arriba y responda las siguientes preguntas:

- ¿Cuáles son los mejores métodos en términos de consumo de tiempo?
- ¿Qué parte del tiempo total utilizan esos métodos?

Responda las mismas preguntas para consultas.

Si ve que los métodos tienen el prefijo "ER", continúe con la siguiente sección.

Si ve que los métodos o consultas se originaron en el conjunto de aplicaciones, considere optimizaciones genéricas (por ejemplo, cree índices).

Analiza el número de llamadas. Si el número es significativamente mayor de lo esperado, considere almacenar en caché los nodos correspondientes de la configuración.

### <a name="analyze-database-calls"></a><a name="analyze-database-calls"></a>Analizar llamadas a la base de datos

Prepare un ejemplo que tenga una pequeña cantidad de datos, para que pueda recopilar un [Seguimiento de ER](#electronic-reporting-traces).

Luego, abra el seguimiento en el diseñador de asignación del modelo ER y mire en la parte inferior de la página. Responda a las siguientes preguntas:

- ¿Existe alguna duplicación de consultas? Si existe, considere una de las siguientes correcciones:

    - [Usar almacenamiento en caché](#use-caching) si cree que hay varias llamadas dentro de un registro primario.
    - [Utilice un campo calculado parametrizado almacenado en caché](#cached-parameterized) si cree que hay llamadas al mismo registro dentro de diferentes registros.
    - [Usar un origen de datos **JOIN**](#use-join-datasource) si tiene que leer un número considerable de registros diferentes de una base de datos.

- ¿El número de consultas y registros obtenidos corresponde a la cantidad total de datos? Por ejemplo, si un documento tiene 10 líneas, ¿las estadísticas muestran que el informe extrae 10 líneas o 1000 líneas? Si tiene una cantidad considerable de registros recuperados, considere una de las siguientes correcciones:

    - [Utilice la función **FILTRO** en lugar de la función **DONDE**](#filter) para procesar datos del lado de Microsoft SQL Server.
    - Utilice el almacenamiento en caché para evitar obtener los mismos datos.
    - [Utilizar funciones de datos recopilados](#collected-data) para evitar obtener los mismos datos para el resumen.

### <a name="analyze-perfview-traces"></a>Analizar seguimientos de PerfView

[PerfView](#perfview) es una herramienta para desarrolladores experimentados. Para obtener información más detallada sobre los siguientes pasos, consulte [Conceptos básicos sobre la investigación del tiempo del reloj de pared](https://channel9.msdn.com/Series/PerfView-Tutorial/Tutorial-12-Wall-Clock-Time-Investigation-Basics).

1. Recoge un seguimiento usando el tiempo de subproceso.
2. Incluya solo pilas que usen **runUnattended**, para filtrar solo el subproceso que tiene ejecución de configuración. (Agregar **runUnattended** al cuadro de entrada **IncPats**.)
3. Plegar toda la CPU, la red y el tiempo bloqueado.
4. Cargar [Ajustes preestablecidos de ER para PerfView](https://download.microsoft.com/download/2/d/0/2d037b0f-ffd1-4d65-b64f-fcdf51f2c81f/ER_PerfViewPresets.xml).
5. Seleccione **ER** \> **Otro preajuste**.
6. Mire los nombres:

    - Probablemente verá el código de la plataforma que consume más tiempo.
    - Puede tocar dos veces (o hacer doble clic) y subir a través de **callees**.

        Si encuentra clases que tienen el prefijo "ERExpression" y si son funciones relacionadas con fórmulas, puede adivinar el nombre de la función según el nombre de la clase y puede consultar el repositorio de ER para ver los atributos.

### <a name="fixes"></a>Correcciones

- Si ve que las consultas consumen la mayor parte del tiempo de CPU, intente reducir la cantidad de consultas:

    - [Revisar el seguimiento de ER](#analyze-database-calls) para consultas duplicadas.
    - Vea cuántos registros se obtienen y evalúe cuántos datos deberían obtenerse teóricamente.

- Si ve que la mayor parte del tiempo de CPU lo consumen las funciones que se utilizan, intente encontrar el lugar en la configuración que consume más recursos.
- Si ve que la mayor parte del tiempo de la CPU lo consumen las funciones de recopilación de datos, considere reemplazarlas con *SQL group by* en el lado de asignación del modelo.

### <a name="collecting-data"></a><a name="collecting-data"></a>Recopilación de datos

Dependiendo de su entorno, hay varias formas de recopilar los datos disponibles:

- Obtenga el tiempo total de ejecución:

    - Desde el centro de actividades
    - Desde el registro de eventos

- Perfile la ejecución:

    - Mediante el uso de herramientas de ER
    - Utilizando Trace parser
    - Utilizando PerfView

#### <a name="collecting-data-in-a-production-environment"></a>Recopilando datos en un entorno de producción

A veces, los problemas solo se pueden reproducir en un entorno de producción. Los datos se pueden recopilar de las maneras siguientes:

- Usando seguimientos [Trace parser](../perf-test/trace-trace-tutorial.md)
- Mediante el uso de seguimiento de [Ejecución de ER](trace-execution-er-troubleshoot-perf.md)
- Utilizando el tiempo total de ejecución

#### <a name="collecting-data-in-a-development-environment"></a>Recopilando datos en un entorno de desarrollo

Además de las herramientas que se pueden utilizar en un entorno de producción, existen varias herramientas que se pueden utilizar en un entorno de desarrollo:

- Registro de eventos (Microsoft-Dynamics-ElectronicReporting). Este registro puede darle el tiempo total de ejecución.
- Herramientas de .NET comunes, como PerfView.

Además, un entorno de desarrollo le brinda más flexibilidad para experimentar. Por ejemplo, puede desactivar partes de los informes para ver cómo se ve afectado el tiempo de ejecución.

### <a name="tools"></a><a name="tools"></a>Herramientas

#### <a name="execution-time-in-the-action-center"></a><a name="infolog-time"></a>Tiempo de ejecución en el centro de actividades

ER puede mostrar el tiempo de ejecución de la configuración en el Centro de actividades. Esta opción funciona solo para un usuario específico y una empresa específica, y solo para sesiones interactivas. Para que esta función esté disponible, siga estos pasos.

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Configuración avanzada**, seleccione **Parámetros de usuario**.
3. En el cuadro de diálogo **Parámetros de usuario**, establezca la opción **Mostrar tiempo de creación de archivo** a **Sí**.

#### <a name="execution-time-in-the-event-log"></a><a name="event-log-time"></a>Tiempo de ejecución en el registro de eventos

1. Abra el visor de eventos de Windows.
2. Bajo **Registros de aplicaciones y servicios**, abra **Microsoft-Dynamics-ElectronicReporting/Operational**.
3. Busque eventos **FormatMapingRun**, donde **EventID=2**, porque estos eventos contienen la información sobre el tiempo transcurrido.

#### <a name="trace-parser-traces"></a><a name="trace-parser"></a>Seguimientos de Trace Parser 

Debido a que ER está implementado en X++, puede utilizar herramientas comunes de X++ para analizar el rendimiento. Para más información, consulte [Realizar seguimientos mediante Trace parser](../perf-test/trace-trace-tutorial.md).

Hay algunas limitaciones para este enfoque. Debido a que parte de ER se implementa en C#, no todos los detalles estarán disponibles. Sin embargo, puede ver los detalles del uso de datos. Además, las ejecuciones de informes largas pueden superar las limitaciones de almacenamiento de seguimiento.

#### <a name="er-traces"></a><a name="electronic-reporting-traces"></a>Seguimientos de ER

ER puede recopilar sus propios seguimientos y tiene herramientas de visualización y análisis para esos seguimientos. Para obtener más información, vea [Realizar un seguimiento de la ejecución de los formatos de ER para solucionar problemas de rendimiento](trace-execution-er-troubleshoot-perf.md).

#### <a name="perfview"></a><a name="perfview"></a>PerfView

Debido a que tanto X++ como ER se implementan sobre la plataforma .NET, puede usar herramientas .NET comunes. Por ejemplo, puede utilizar la herramienta gratuita [PerfView](https://github.com/Microsoft/perfview).

También puede recopilar datos desde la línea de comandos. Por ejemplo, el siguiente script de Windows PowerShell recopila el tiempo de ejecución hasta que se detiene la ejecución de cualquier formato en la máquina.

```powershell
c:\programs\PerfView collect "e:\traces\$(date -format "ddMMyyyy_hhmm").etl" `
    -CircularMB:20000 -ThreadTime `
    -NoNGenRundown `
    -StopOnEtwEvent:Microsoft-Dynamics-ElectronicReporting/FormatMappingRun/Stop
```

Hay algunas limitaciones para este enfoque. Debe tener acceso de administrador para la máquina. Además, debe ser un desarrollador experimentado, porque hay una curva de aprendizaje pronunciada.

### <a name="making-changes"></a><a name="making-changes"></a>Realización de cambios

#### <a name="use-caching"></a><a name="use-caching"></a>Usar almacenamiento en caché

Aunque el almacenamiento en caché reduce la cantidad de tiempo que se requiere para recuperar datos nuevamente, consume memoria. Utilice el almacenamiento en caché en los casos en que la cantidad de datos obtenidos no sea muy grande. Para obtener más información y un ejemplo que muestra cómo utilizar el almacenamiento en caché, consulte [Mejorar el seguimiento del modelo en función de la información del seguimiento de ejecución](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace).

#### <a name="reduce-volume-of-data-fetched"></a><a name="reduce-fetched-data"></a>Reducir el volumen de datos obtenidos

Puede reducir el consumo de memoria para el almacenamiento en caché limitando la cantidad de campos de los registros de una tabla de aplicación que se obtendrán en tiempo de ejecución. En este caso, obtendrá solo los valores de campos de una tabla de aplicación que necesite en su asignación de modelo de ER. No se recuperarán otros campos de esa tabla. Por lo tanto, se reduce el volumen de memoria que se requiere para almacenar en caché los registros obtenidos. Para más información, consulte [Mejorar el rendimiento de las soluciones de ER al reducir la cantidad de campos de tabla que se localizan en runtime](er-reduce-fetched-fields-number.md).

#### <a name="use-a-cached-parameterized-calculated-field"></a><a name="cached-parameterized"></a>Utilice un campo calculado parametrizado almacenado en caché

A veces, los valores deben buscarse repetidamente. Los ejemplos incluyen nombres de cuentas y números de cuentas. Para ayudar a ahorrar tiempo, puede crear un campo calculado que tenga parámetros en el nivel superior y luego agregar el campo a la caché.

Le recomendamos que utilice este enfoque solo cuando el tamaño de los datos en caché sea pequeño. Para más información, consulte [Mejorar el rendimiento de las soluciones de ER agregando orígenes de datos de CAMPO CALCULADO parametrizados](er-calculated-field-ds-performance.md).

#### <a name="use-a-join-data-source"></a><a name="use-join-datasource"></a>Uso de un origen de datos JOIN

Un origen de datos **JOIN** permite que una consulta obtenga varios registros conectados. No es necesario utilizar una consulta separada para obtener cada registro conectado. Por ejemplo, si tiene 1000 líneas y obtiene datos de artículo para cada línea por relación, tendrá 1001 consultas (= 1000 + 1). Si usa un origen de datos **JOIN**, utilizará solo una consulta para obtener los mismos datos. Para obtener más información, consulte [Usar los orígenes de datos de JOIN en asignaciones de modelos de ER para obtener datos de varias tablas de aplicación](er-join-data-sources.md)

#### <a name="use-the-filter-function-instead-of-the-where-function"></a><a name="filter"></a>Utilice la función FILTER en lugar de la función WHERE

La función **[FILTER](er-functions-list-filter.md)** ejecuta condiciones en SQL Server, mientras que la función **WHERE** obtiene todos los datos de la lista, un registro a la vez, y aplica la condición para cada registro. Por ejemplo, desea seleccionar un registro de 1000 registros. Si utiliza **WHERE**, se recuperarán los 1000 registros. Sin embargo, si usa **FILTER**, se obtendrá exactamente un registro. **FILTER** también puede usar índices en el lado de la base de datos.

#### <a name="using-collected-data-functions-or-an-accumulated-data-data-source"></a><a name="collected-data"></a>Uso de funciones de datos recopilados o un origen de datos de datos acumulados

Si su configuración tiene un componente *group by* que resume los datos obtenidos previamente por informe, el componente recuperará todos los datos nuevamente. Al utilizar las funciones de datos recopilados, habilita a ER para acumular datos durante la primera búsqueda. Para más información, consulte [ER Configurar el formato para contar y sumar](tasks/er-format-counting-summing-2.md).

#### <a name="rewrite-parts-of-the-configuration-in-x"></a>Reescribir partes de la configuración en X++

ER admite métodos de llamada de tablas y clases, incluidas las extensiones. Considere la posibilidad de reescribir partes de la asignación del modelo en X++ para ayudar a mejorar el rendimiento.

ER puede consumir datos de las siguientes fuentes:

- Clases (orígenes de datos **objeto** y **clase**)
- Tablas (orígenes de datos **mesa** y **registros de la tabla**)

La [Interfaz de programación de aplicaciones (API) de ER](er-apis-app73.md#how-to-access-internal-x-objects-by-using-erobjectsfactory) también proporciona una forma de enviar datos precalculados desde el código de llamada. El paquete de aplicaciones contiene numerosos ejemplos de este enfoque.
