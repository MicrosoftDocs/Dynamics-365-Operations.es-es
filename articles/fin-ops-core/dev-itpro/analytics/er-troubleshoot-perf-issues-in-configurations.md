---
title: Solución de problemas de rendimiento en configuraciones de ER
description: Este tema explica cómo encontrar y solucionar problemas de rendimiento en configuraciones de informes electrónicos (ER).
author: NickSelin
ms.date: 06/08/2021
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
ms.openlocfilehash: d77c2aad904ba911ac19009d6a981ea4153aaa48
ms.sourcegitcommit: 60afcd85b3b5b9e5e8981ebbb57c0161cf05e54b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2021
ms.locfileid: "6216874"
---
# <a name="troubleshooting-performance-issues-in-er-configurations"></a><span data-ttu-id="b506f-103">Solución de problemas de rendimiento en configuraciones de ER</span><span class="sxs-lookup"><span data-stu-id="b506f-103">Troubleshooting performance issues in ER configurations</span></span>

<span data-ttu-id="b506f-104">Este tema explica cómo encontrar y solucionar problemas de rendimiento en [configuraciones](general-electronic-reporting.md#Configuration) de [informes electrónicos](general-electronic-reporting.md) (ER).</span><span class="sxs-lookup"><span data-stu-id="b506f-104">This topic explains how to find and solve performance issues in [Electronic reporting](general-electronic-reporting.md) (ER) [configurations](general-electronic-reporting.md#Configuration).</span></span>

<span data-ttu-id="b506f-105">Normalmente, la investigación del rendimiento consta de varios pasos.</span><span class="sxs-lookup"><span data-stu-id="b506f-105">Typically, performance investigation consists of several steps.</span></span>

1. <span data-ttu-id="b506f-106">[Recopilar](#collecting-data) datos.</span><span class="sxs-lookup"><span data-stu-id="b506f-106">[Collect](#collecting-data) data.</span></span>
2. <span data-ttu-id="b506f-107">Analizar los datos recopilados.</span><span class="sxs-lookup"><span data-stu-id="b506f-107">Analyze the collected data.</span></span>
3. <span data-ttu-id="b506f-108">Según los resultados del análisis, utilizar configuraciones ER para [hacer cambios](#making-changes) o decidir recopilar más datos.</span><span class="sxs-lookup"><span data-stu-id="b506f-108">Based on the results of the analysis, use ER configurations to [make changes](#making-changes), or decide to collect more data.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b506f-109">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="b506f-109">Troubleshooting</span></span>

### <a name="analyze-execution-time"></a><span data-ttu-id="b506f-110">Analizar el tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b506f-110">Analyze execution time</span></span>

<span data-ttu-id="b506f-111">El tiempo de ejecución puede depender de factores impredecibles, como otras tareas que se ejecutan en el mismo entorno y el almacenamiento en caché que utiliza datos cuando se llama por primera vez.</span><span class="sxs-lookup"><span data-stu-id="b506f-111">Execution time can depend on unpredictable factors, such as other tasks that are running in the same environment and caching that uses data when it's called for the first time.</span></span> <span data-ttu-id="b506f-112">Por lo tanto, debe repetir la ejecución y la medición varias veces.</span><span class="sxs-lookup"><span data-stu-id="b506f-112">Therefore, you should repeat the execution and measurement several times.</span></span>

<span data-ttu-id="b506f-113">A veces, los problemas de rendimiento no se deben a una configuración de formato ER que se utiliza para generar informes.</span><span class="sxs-lookup"><span data-stu-id="b506f-113">Sometimes, performance issues aren't caused by an ER format configuration that is used for reporting.</span></span> <span data-ttu-id="b506f-114">En cambio, son causados por el código X ++ que se usa para abrir esa configuración de formato ER.</span><span class="sxs-lookup"><span data-stu-id="b506f-114">Instead, they are caused by the X++ code that is used to open that ER format configuration.</span></span>

1. <span data-ttu-id="b506f-115">Tanto en el [Centro de Acción](#infolog-time) como en el [registro de eventos](#event-log-time), mire el tiempo de ejecución del informe.</span><span class="sxs-lookup"><span data-stu-id="b506f-115">In either the [Action center](#infolog-time) or the [event log](#event-log-time), look at the execution time of the report.</span></span>
2. <span data-ttu-id="b506f-116">Compare el tiempo de ejecución del informe con el tiempo total de ejecución en el escenario.</span><span class="sxs-lookup"><span data-stu-id="b506f-116">Compare the execution time of the report with the total execution time in the scenario.</span></span>
3. <span data-ttu-id="b506f-117">Si el tiempo de ejecución del informe es mucho menor que el tiempo total de ejecución, considere la cantidad de datos que procesa el informe:</span><span class="sxs-lookup"><span data-stu-id="b506f-117">If the execution time of the report is much less than the total execution time, consider the amount of data that the report processes:</span></span>

    - <span data-ttu-id="b506f-118">Si el informe procesa una pequeña cantidad de datos, el problema puede implicar el tiempo de carga de la configuración.</span><span class="sxs-lookup"><span data-stu-id="b506f-118">If the report processes a small amount of data, the issue might involve the loading time of the configuration.</span></span>
    - <span data-ttu-id="b506f-119">Si el informe procesa una gran cantidad de datos, el problema puede implicar el preprocesamiento de X++.</span><span class="sxs-lookup"><span data-stu-id="b506f-119">If the report processes a large amount of data, the issue might involve preprocessing X++.</span></span> <span data-ttu-id="b506f-120">Usar el [Analizador de seguimiento](#analyze-trace-parser-trace) para analizar este caso.</span><span class="sxs-lookup"><span data-stu-id="b506f-120">Use [Trace parser](#analyze-trace-parser-trace) to analyze this case.</span></span>

    <span data-ttu-id="b506f-121">Para otros casos, consulte las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="b506f-121">For other cases, see the next sections.</span></span>

4. <span data-ttu-id="b506f-122">Ejecute varias pruebas que involucren diferentes cantidades de datos para determinar cómo el tiempo de ejecución depende de la cantidad de datos.</span><span class="sxs-lookup"><span data-stu-id="b506f-122">Run multiple tests that involve different amounts of data to determine how the execution time depends on the amount of data.</span></span>

### <a name="analyze-trace-parser-traces"></a><a name="analyze-trace-parser-trace"></a><span data-ttu-id="b506f-123">Analizar seguimientos de Trace Parser</span><span class="sxs-lookup"><span data-stu-id="b506f-123">Analyze Trace parser traces</span></span>

<span data-ttu-id="b506f-124">Prepare un pequeño ejemplo o recopile varios seguimientos durante partes aleatorias de la generación del informe.</span><span class="sxs-lookup"><span data-stu-id="b506f-124">Prepare a small example, or collect several traces during random parts of the report generation.</span></span>

<span data-ttu-id="b506f-125">Entonces, en [Trace Parser](#trace-parser), realice un análisis estándar de abajo hacia arriba y responda las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="b506f-125">Then, in [Trace parser](#trace-parser), do a standard bottom-to-up analysis, and answer the following questions:</span></span>

- <span data-ttu-id="b506f-126">¿Cuáles son los mejores métodos en términos de consumo de tiempo?</span><span class="sxs-lookup"><span data-stu-id="b506f-126">What are the top methods in terms of time consumption?</span></span>
- <span data-ttu-id="b506f-127">¿Qué parte del tiempo total utilizan esos métodos?</span><span class="sxs-lookup"><span data-stu-id="b506f-127">What part of the overall time do those methods use?</span></span>

<span data-ttu-id="b506f-128">Responda las mismas preguntas para consultas.</span><span class="sxs-lookup"><span data-stu-id="b506f-128">Answer the same questions for queries.</span></span>

<span data-ttu-id="b506f-129">Si ve que los métodos tienen el prefijo "ER", continúe con la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="b506f-129">If you see that methods are prefixed with "ER," move on to the next section.</span></span>

<span data-ttu-id="b506f-130">Si ve que los métodos o consultas se originaron en el conjunto de aplicaciones, considere optimizaciones genéricas (por ejemplo, cree índices).</span><span class="sxs-lookup"><span data-stu-id="b506f-130">If you see that methods or queries originated in the application suite, consider generic optimizations (for example, create indexes).</span></span>

<span data-ttu-id="b506f-131">Analiza el número de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b506f-131">Analyze the number of calls.</span></span> <span data-ttu-id="b506f-132">Si el número es significativamente mayor de lo esperado, considere almacenar en caché los nodos correspondientes de la configuración.</span><span class="sxs-lookup"><span data-stu-id="b506f-132">If the number is significantly higher than expected, consider caching the corresponding nodes of the configuration.</span></span>

### <a name="analyze-database-calls"></a><a name="analyze-database-calls"></a><span data-ttu-id="b506f-133">Analizar llamadas a la base de datos</span><span class="sxs-lookup"><span data-stu-id="b506f-133">Analyze database calls</span></span>

<span data-ttu-id="b506f-134">Prepare un ejemplo que tenga una pequeña cantidad de datos, para que pueda recopilar un [Seguimiento de ER](#electronic-reporting-traces).</span><span class="sxs-lookup"><span data-stu-id="b506f-134">Prepare an example that has a small amount of data, so that you can collect an [ER trace](#electronic-reporting-traces).</span></span>

<span data-ttu-id="b506f-135">Luego, abra el seguimiento en el diseñador de asignación del modelo ER y mire en la parte inferior de la página.</span><span class="sxs-lookup"><span data-stu-id="b506f-135">Then open the trace in the ER model mapping designer, and look at the bottom of the page.</span></span> <span data-ttu-id="b506f-136">Responda a las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="b506f-136">Answer the following questions:</span></span>

- <span data-ttu-id="b506f-137">¿Existe alguna duplicación de consultas?</span><span class="sxs-lookup"><span data-stu-id="b506f-137">Is there any query duplication?</span></span> <span data-ttu-id="b506f-138">Si existe, considere una de las siguientes correcciones:</span><span class="sxs-lookup"><span data-stu-id="b506f-138">If there is, consider one of the following fixes:</span></span>

    - <span data-ttu-id="b506f-139">[Usar almacenamiento en caché](#use-caching) si cree que hay varias llamadas dentro de un registro primario.</span><span class="sxs-lookup"><span data-stu-id="b506f-139">[Use caching](#use-caching) if you think that there are several calls inside one parent record.</span></span>
    - <span data-ttu-id="b506f-140">[Utilice un campo calculado parametrizado almacenado en caché](#cached-parameterized) si cree que hay llamadas al mismo registro dentro de diferentes registros.</span><span class="sxs-lookup"><span data-stu-id="b506f-140">[Use a cached, parameterized calculated field](#cached-parameterized) if you think that there are calls to the same record inside different records.</span></span>
    - <span data-ttu-id="b506f-141">[Usar un origen de datos **JOIN**](#use-join-datasource) si tiene que leer un número considerable de registros diferentes de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="b506f-141">[Use a **JOIN** data source](#use-join-datasource) if you have to read to a substantial number of different records from a database.</span></span>

- <span data-ttu-id="b506f-142">¿El número de consultas y registros obtenidos corresponde a la cantidad total de datos?</span><span class="sxs-lookup"><span data-stu-id="b506f-142">Does the number of queries and fetched records correspond to the overall amount of data?</span></span> <span data-ttu-id="b506f-143">Por ejemplo, si un documento tiene 10 líneas, ¿las estadísticas muestran que el informe extrae 10 líneas o 1000 líneas?</span><span class="sxs-lookup"><span data-stu-id="b506f-143">For example, if a document has 10 lines, do the statistics show that the report extracts 10 lines or 1,000 lines?</span></span> <span data-ttu-id="b506f-144">Si tiene una cantidad considerable de registros recuperados, considere una de las siguientes correcciones:</span><span class="sxs-lookup"><span data-stu-id="b506f-144">If you have a substantial number of fetched records, consider one of the following fixes:</span></span>

    - <span data-ttu-id="b506f-145">[Utilizar la función **FILTER** en lugar de la función **WHERE**](#filter) para procesar datos del lado de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b506f-145">[Use the **FILTER** function instead of the **WHERE** function](#filter) to process data on the SQL Server side.</span></span>
    - <span data-ttu-id="b506f-146">Utilice el almacenamiento en caché para evitar obtener los mismos datos.</span><span class="sxs-lookup"><span data-stu-id="b506f-146">Use caching to avoid fetching the same data.</span></span>
    - <span data-ttu-id="b506f-147">[Utilizar funciones de datos recopilados](#collected-data) para evitar obtener los mismos datos para el resumen.</span><span class="sxs-lookup"><span data-stu-id="b506f-147">[Use collected data functions](#collected-data) to avoid fetching the same data for summarization.</span></span>

### <a name="analyze-perfview-traces"></a><span data-ttu-id="b506f-148">Analizar seguimientos de PerfView</span><span class="sxs-lookup"><span data-stu-id="b506f-148">Analyze PerfView traces</span></span>

<span data-ttu-id="b506f-149">[PerfView](#perfview) es una herramienta para desarrolladores experimentados.</span><span class="sxs-lookup"><span data-stu-id="b506f-149">[PerfView](#perfview) is a tool for experienced developers.</span></span> <span data-ttu-id="b506f-150">Para obtener información más detallada sobre los siguientes pasos, consulte [Conceptos básicos sobre la investigación del tiempo del reloj de pared](https://channel9.msdn.com/Series/PerfView-Tutorial/Tutorial-12-Wall-Clock-Time-Investigation-Basics).</span><span class="sxs-lookup"><span data-stu-id="b506f-150">For more detailed information about the following steps, see [Wall Clock Time Investigation Basics](https://channel9.msdn.com/Series/PerfView-Tutorial/Tutorial-12-Wall-Clock-Time-Investigation-Basics).</span></span>

1. <span data-ttu-id="b506f-151">Recoge un seguimiento usando el tiempo de subproceso.</span><span class="sxs-lookup"><span data-stu-id="b506f-151">Collect a trace by using thread time.</span></span>
2. <span data-ttu-id="b506f-152">Incluya solo pilas que usen **runUnattended**, para filtrar solo el subproceso que tiene ejecución de configuración.</span><span class="sxs-lookup"><span data-stu-id="b506f-152">Include only stacks that use **runUnattended**, to filter only the thread that has configuration execution.</span></span> <span data-ttu-id="b506f-153">(Agregar **runUnattended** al cuadro de entrada **IncPats**.)</span><span class="sxs-lookup"><span data-stu-id="b506f-153">(Add **runUnattended** to the **IncPats** input box.)</span></span>
3. <span data-ttu-id="b506f-154">Plegar toda la CPU, la red y el tiempo bloqueado.</span><span class="sxs-lookup"><span data-stu-id="b506f-154">Fold all CPU, network, and blocked time.</span></span>
4. <span data-ttu-id="b506f-155">Cargar [Ajustes preestablecidos de ER para PerfView](https://download.microsoft.com/download/2/d/0/2d037b0f-ffd1-4d65-b64f-fcdf51f2c81f/ER_PerfViewPresets.xml).</span><span class="sxs-lookup"><span data-stu-id="b506f-155">Load [ER presets for PerfView](https://download.microsoft.com/download/2/d/0/2d037b0f-ffd1-4d65-b64f-fcdf51f2c81f/ER_PerfViewPresets.xml).</span></span>
5. <span data-ttu-id="b506f-156">Seleccione **ER** \> **Otro preajuste**.</span><span class="sxs-lookup"><span data-stu-id="b506f-156">Select **ER** \> **Other preset**.</span></span>
6. <span data-ttu-id="b506f-157">Mire los nombres:</span><span class="sxs-lookup"><span data-stu-id="b506f-157">Look at the names:</span></span>

    - <span data-ttu-id="b506f-158">Probablemente verá el código de la plataforma que consume más tiempo.</span><span class="sxs-lookup"><span data-stu-id="b506f-158">You will probably see the platform code that consumes the most time.</span></span>
    - <span data-ttu-id="b506f-159">Puede tocar dos veces (o hacer doble clic) y subir a través de **callees**.</span><span class="sxs-lookup"><span data-stu-id="b506f-159">You can double-tap (or double-click) and go up through **callees**.</span></span>

        <span data-ttu-id="b506f-160">Si encuentra clases que tienen el prefijo "ERExpression" y si son funciones relacionadas con fórmulas, puede adivinar el nombre de la función según el nombre de la clase y puede consultar el repositorio de ER para ver los atributos.</span><span class="sxs-lookup"><span data-stu-id="b506f-160">If you find classes that have the prefix "ERExpression," and if they are functions that are related to formulas, you can guess the function name based on the class name, and you can look at the ER repo to view the attributes.</span></span>

### <a name="fixes"></a><span data-ttu-id="b506f-161">Correcciones</span><span class="sxs-lookup"><span data-stu-id="b506f-161">Fixes</span></span>

- <span data-ttu-id="b506f-162">Si ve que las consultas consumen la mayor parte del tiempo de CPU, intente reducir la cantidad de consultas:</span><span class="sxs-lookup"><span data-stu-id="b506f-162">If you see that most of the CPU time is consumed by queries, try to reduce the number of queries:</span></span>

    - <span data-ttu-id="b506f-163">[Revisar el seguimiento de ER](#analyze-database-calls) para consultas duplicadas.</span><span class="sxs-lookup"><span data-stu-id="b506f-163">[Review the ER trace](#analyze-database-calls) for duplicated queries.</span></span>
    - <span data-ttu-id="b506f-164">Vea cuántos registros se obtienen y evalúe cuántos datos deberían obtenerse teóricamente.</span><span class="sxs-lookup"><span data-stu-id="b506f-164">See how many records are fetched, and evaluate how much data should theoretically be fetched.</span></span>

- <span data-ttu-id="b506f-165">Si ve que la mayor parte del tiempo de CPU lo consumen las funciones que se utilizan, intente encontrar el lugar en la configuración que consume más recursos.</span><span class="sxs-lookup"><span data-stu-id="b506f-165">If you see that most of the CPU time is consumed by the functions that are used, try to find the place in the configuration that consumes the most resources.</span></span>
- <span data-ttu-id="b506f-166">Si ve que la mayor parte del tiempo de la CPU lo consumen las funciones de recopilación de datos, considere reemplazarlas con *SQL group by* en el lado de asignación del modelo.</span><span class="sxs-lookup"><span data-stu-id="b506f-166">If you see that most of the CPU time is consumed by data collection functions, consider replacing them with *SQL group by* on the model mapping side.</span></span>

### <a name="collecting-data"></a><a name="collecting-data"></a><span data-ttu-id="b506f-167">Recopilación de datos</span><span class="sxs-lookup"><span data-stu-id="b506f-167">Collecting data</span></span>

<span data-ttu-id="b506f-168">Dependiendo de su entorno, hay varias formas de recopilar los datos disponibles:</span><span class="sxs-lookup"><span data-stu-id="b506f-168">Depending on your environment, there are several ways to collect available data:</span></span>

- <span data-ttu-id="b506f-169">Obtenga el tiempo total de ejecución:</span><span class="sxs-lookup"><span data-stu-id="b506f-169">Get the total running time:</span></span>

    - <span data-ttu-id="b506f-170">Desde el centro de actividades</span><span class="sxs-lookup"><span data-stu-id="b506f-170">From the Action center</span></span>
    - <span data-ttu-id="b506f-171">Desde el registro de eventos</span><span class="sxs-lookup"><span data-stu-id="b506f-171">From the event log</span></span>

- <span data-ttu-id="b506f-172">Perfile la ejecución:</span><span class="sxs-lookup"><span data-stu-id="b506f-172">Profile the execution:</span></span>

    - <span data-ttu-id="b506f-173">Mediante el uso de herramientas de ER</span><span class="sxs-lookup"><span data-stu-id="b506f-173">By using ER tools</span></span>
    - <span data-ttu-id="b506f-174">Utilizando Trace parser</span><span class="sxs-lookup"><span data-stu-id="b506f-174">By using Trace parser</span></span>
    - <span data-ttu-id="b506f-175">Utilizando PerfView</span><span class="sxs-lookup"><span data-stu-id="b506f-175">By using PerfView</span></span>

#### <a name="collecting-data-in-a-production-environment"></a><span data-ttu-id="b506f-176">Recopilando datos en un entorno de producción</span><span class="sxs-lookup"><span data-stu-id="b506f-176">Collecting data in a production environment</span></span>

<span data-ttu-id="b506f-177">A veces, los problemas solo se pueden reproducir en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="b506f-177">Sometimes, issues can be reproduced only in a production environment.</span></span> <span data-ttu-id="b506f-178">Los datos se pueden recopilar de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="b506f-178">Data can be collected in the following ways:</span></span>

- <span data-ttu-id="b506f-179">Usando seguimientos [Trace parser](../perf-test/trace-trace-tutorial.md)</span><span class="sxs-lookup"><span data-stu-id="b506f-179">By using [Trace parser](../perf-test/trace-trace-tutorial.md) traces</span></span>
- <span data-ttu-id="b506f-180">Mediante el uso de seguimiento de [Ejecución de ER](trace-execution-er-troubleshoot-perf.md)</span><span class="sxs-lookup"><span data-stu-id="b506f-180">By using [ER execution](trace-execution-er-troubleshoot-perf.md) traces</span></span>
- <span data-ttu-id="b506f-181">Utilizando el tiempo total de ejecución</span><span class="sxs-lookup"><span data-stu-id="b506f-181">By using the total execution time</span></span>

#### <a name="collecting-data-in-a-development-environment"></a><span data-ttu-id="b506f-182">Recopilando datos en un entorno de desarrollo</span><span class="sxs-lookup"><span data-stu-id="b506f-182">Collecting data in a development environment</span></span>

<span data-ttu-id="b506f-183">Además de las herramientas que se pueden utilizar en un entorno de producción, existen varias herramientas que se pueden utilizar en un entorno de desarrollo:</span><span class="sxs-lookup"><span data-stu-id="b506f-183">In addition to the tools that can be used in a production environment, there are several tools that you can use in a development environment:</span></span>

- <span data-ttu-id="b506f-184">Registro de eventos (Microsoft-Dynamics-ElectronicReporting).</span><span class="sxs-lookup"><span data-stu-id="b506f-184">Event log (Microsoft-Dynamics-ElectronicReporting).</span></span> <span data-ttu-id="b506f-185">Este registro puede darle el tiempo total de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b506f-185">This log can give you the total execution time.</span></span>
- <span data-ttu-id="b506f-186">Herramientas de .NET comunes, como PerfView.</span><span class="sxs-lookup"><span data-stu-id="b506f-186">Common .NET tools, such as PerfView.</span></span>

<span data-ttu-id="b506f-187">Además, un entorno de desarrollo le brinda más flexibilidad para experimentar.</span><span class="sxs-lookup"><span data-stu-id="b506f-187">Additionally, a development environment gives you more flexibility to experiment.</span></span> <span data-ttu-id="b506f-188">Por ejemplo, puede desactivar partes de los informes para ver cómo se ve afectado el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b506f-188">For example, you can turn off parts of reports to see how the execution time is affected.</span></span>

### <a name="tools"></a><a name="tools"></a><span data-ttu-id="b506f-189">Herramientas</span><span class="sxs-lookup"><span data-stu-id="b506f-189">Tools</span></span>

#### <a name="execution-time-in-the-action-center"></a><a name="infolog-time"></a><span data-ttu-id="b506f-190">Tiempo de ejecución en el centro de actividades</span><span class="sxs-lookup"><span data-stu-id="b506f-190">Execution time in the Action center</span></span>

<span data-ttu-id="b506f-191">ER puede mostrar el tiempo de ejecución de la configuración en el Centro de actividades.</span><span class="sxs-lookup"><span data-stu-id="b506f-191">ER can show the execution time of the configuration in the Action center.</span></span> <span data-ttu-id="b506f-192">Esta opción funciona solo para un usuario específico y una empresa específica, y solo para sesiones interactivas.</span><span class="sxs-lookup"><span data-stu-id="b506f-192">This option works only for a specific user and a specific company, and only for interactive sessions.</span></span> <span data-ttu-id="b506f-193">Para que esta función esté disponible, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b506f-193">To make this feature available, follow these steps.</span></span>

1. <span data-ttu-id="b506f-194">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="b506f-194">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="b506f-195">En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Configuración avanzada**, seleccione **Parámetros de usuario**.</span><span class="sxs-lookup"><span data-stu-id="b506f-195">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="b506f-196">En el cuadro de diálogo **Parámetros de usuario**, establezca la opción **Mostrar tiempo de creación de archivo** a **Sí**.</span><span class="sxs-lookup"><span data-stu-id="b506f-196">In the **User parameters** dialog box, set the **Show file generation time** option to **Yes**.</span></span>

#### <a name="execution-time-in-the-event-log"></a><a name="event-log-time"></a><span data-ttu-id="b506f-197">Tiempo de ejecución en el registro de eventos</span><span class="sxs-lookup"><span data-stu-id="b506f-197">Execution time in the event log</span></span>

1. <span data-ttu-id="b506f-198">Abra el visor de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="b506f-198">Open Windows Event Viewer.</span></span>
2. <span data-ttu-id="b506f-199">Bajo **Registros de aplicaciones y servicios**, abra **Microsoft-Dynamics-ElectronicReporting/Operational**.</span><span class="sxs-lookup"><span data-stu-id="b506f-199">Under **Applications and Services logs**, open **Microsoft-Dynamics-ElectronicReporting/Operational**.</span></span>
3. <span data-ttu-id="b506f-200">Busque eventos **FormatMapingRun**, donde **EventID=2**, porque estos eventos contienen la información sobre el tiempo transcurrido.</span><span class="sxs-lookup"><span data-stu-id="b506f-200">Look for **FormatMapingRun** events where **EventID=2**, because these events contain the information about elapsed time.</span></span>

#### <a name="trace-parser-traces"></a><a name="trace-parser"></a><span data-ttu-id="b506f-201">Seguimientos de Trace Parser</span><span class="sxs-lookup"><span data-stu-id="b506f-201">Trace parser traces</span></span> 

<span data-ttu-id="b506f-202">Debido a que ER está implementado en X++, puede utilizar herramientas comunes de X++ para analizar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="b506f-202">Because ER is implemented in X++, you can use common X++ tools to analyze performance.</span></span> <span data-ttu-id="b506f-203">Para más información, consulte [Realizar seguimientos mediante Trace parser](../perf-test/trace-trace-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="b506f-203">For more information, see [Take traces by using Trace parser](../perf-test/trace-trace-tutorial.md).</span></span>

<span data-ttu-id="b506f-204">Hay algunas limitaciones para este enfoque.</span><span class="sxs-lookup"><span data-stu-id="b506f-204">There are a few limitations to this approach.</span></span> <span data-ttu-id="b506f-205">Debido a que parte de ER se implementa en C#, no todos los detalles estarán disponibles.</span><span class="sxs-lookup"><span data-stu-id="b506f-205">Because part of ER is implemented in C#, not all the details will be available.</span></span> <span data-ttu-id="b506f-206">Sin embargo, puede ver los detalles del uso de datos.</span><span class="sxs-lookup"><span data-stu-id="b506f-206">However, you can view the data usage details.</span></span> <span data-ttu-id="b506f-207">Además, las ejecuciones de informes largas pueden superar las limitaciones de almacenamiento de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b506f-207">Additionally, long report runs can exceed trace storage limitations.</span></span>

#### <a name="er-traces"></a><a name="electronic-reporting-traces"></a><span data-ttu-id="b506f-208">Seguimientos de ER</span><span class="sxs-lookup"><span data-stu-id="b506f-208">ER traces</span></span>

<span data-ttu-id="b506f-209">ER puede recopilar sus propios seguimientos y tiene herramientas de visualización y análisis para esos seguimientos.</span><span class="sxs-lookup"><span data-stu-id="b506f-209">ER can collect its own traces, and it has visualization and analysis tools for those traces.</span></span> <span data-ttu-id="b506f-210">Para obtener más información, vea [Realizar un seguimiento de la ejecución de los formatos de ER para solucionar problemas de rendimiento](trace-execution-er-troubleshoot-perf.md).</span><span class="sxs-lookup"><span data-stu-id="b506f-210">For more information, see [Trace the execution of ER formats to troubleshoot performance issues](trace-execution-er-troubleshoot-perf.md).</span></span>

#### <a name="perfview"></a><a name="perfview"></a><span data-ttu-id="b506f-211">PerfView</span><span class="sxs-lookup"><span data-stu-id="b506f-211">PerfView</span></span>

<span data-ttu-id="b506f-212">Debido a que tanto X++ como ER se implementan sobre la plataforma .NET, puede usar herramientas .NET comunes.</span><span class="sxs-lookup"><span data-stu-id="b506f-212">Because both X++ and ER are implemented on top of the .NET platform, you can use common .NET tools.</span></span> <span data-ttu-id="b506f-213">Por ejemplo, puede utilizar la herramienta gratuita [PerfView](https://github.com/Microsoft/perfview).</span><span class="sxs-lookup"><span data-stu-id="b506f-213">For example, you can use the free [PerfView](https://github.com/Microsoft/perfview) tool.</span></span>

<span data-ttu-id="b506f-214">También puede recopilar datos desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="b506f-214">You can also collect data from the command line.</span></span> <span data-ttu-id="b506f-215">Por ejemplo, el siguiente script de Windows PowerShell recopila el tiempo de ejecución hasta que se detiene la ejecución de cualquier formato en la máquina.</span><span class="sxs-lookup"><span data-stu-id="b506f-215">For example, the following Windows PowerShell script collects the execution time until any format execution is stopped on the machine.</span></span>

```powershell
c:\programs\PerfView collect "e:\traces\$(date -format "ddMMyyyy_hhmm").etl" `
    -CircularMB:20000 -ThreadTime `
    -NoNGenRundown `
    -StopOnEtwEvent:Microsoft-Dynamics-ElectronicReporting/FormatMappingRun/Stop
```

<span data-ttu-id="b506f-216">Hay algunas limitaciones para este enfoque.</span><span class="sxs-lookup"><span data-stu-id="b506f-216">There are a few limitations to this approach.</span></span> <span data-ttu-id="b506f-217">Debe tener acceso de administrador para la máquina.</span><span class="sxs-lookup"><span data-stu-id="b506f-217">You must have administrative access to the machine.</span></span> <span data-ttu-id="b506f-218">Además, debe ser un desarrollador experimentado, porque hay una curva de aprendizaje pronunciada.</span><span class="sxs-lookup"><span data-stu-id="b506f-218">Additionally, you must be an experienced developer, because there is a steep learning curve.</span></span>

### <a name="making-changes"></a><a name="making-changes"></a><span data-ttu-id="b506f-219">Realización de cambios</span><span class="sxs-lookup"><span data-stu-id="b506f-219">Making changes</span></span>

#### <a name="use-caching"></a><a name="use-caching"></a><span data-ttu-id="b506f-220">Usar almacenamiento en caché</span><span class="sxs-lookup"><span data-stu-id="b506f-220">Use caching</span></span>

<span data-ttu-id="b506f-221">Aunque el almacenamiento en caché reduce la cantidad de tiempo que se requiere para recuperar datos nuevamente, consume memoria.</span><span class="sxs-lookup"><span data-stu-id="b506f-221">Although caching reduces the amount of time that is required to fetch data again, it costs memory.</span></span> <span data-ttu-id="b506f-222">Utilice el almacenamiento en caché en los casos en que la cantidad de datos obtenidos no sea muy grande.</span><span class="sxs-lookup"><span data-stu-id="b506f-222">Use caching in cases where the amount of fetched data isn't very large.</span></span> <span data-ttu-id="b506f-223">Para obtener más información y un ejemplo que muestra cómo utilizar el almacenamiento en caché, consulte [Mejorar el seguimiento del modelo en función de la información del seguimiento de ejecución](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace).</span><span class="sxs-lookup"><span data-stu-id="b506f-223">For more information and an example that shows how to use caching, see [Improve the model mapping based on information from the execution trace](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace).</span></span>

#### <a name="use-a-cached-parameterized-calculated-field"></a><a name="cached-parameterized"></a><span data-ttu-id="b506f-224">Utilice un campo calculado parametrizado almacenado en caché</span><span class="sxs-lookup"><span data-stu-id="b506f-224">Use a cached, parameterized calculated field</span></span>

<span data-ttu-id="b506f-225">A veces, los valores deben buscarse repetidamente.</span><span class="sxs-lookup"><span data-stu-id="b506f-225">Sometimes, values must be looked up repeatedly.</span></span> <span data-ttu-id="b506f-226">Los ejemplos incluyen nombres de cuentas y números de cuentas.</span><span class="sxs-lookup"><span data-stu-id="b506f-226">Examples include account names and account numbers.</span></span> <span data-ttu-id="b506f-227">Para ayudar a ahorrar tiempo, puede crear un campo calculado que tenga parámetros en el nivel superior y luego agregar el campo a la caché.</span><span class="sxs-lookup"><span data-stu-id="b506f-227">To help save time, you can create a calculated field that has parameters on the top level, and then add the field to the cache.</span></span>

<span data-ttu-id="b506f-228">Le recomendamos que utilice este enfoque solo cuando el tamaño de los datos en caché sea pequeño.</span><span class="sxs-lookup"><span data-stu-id="b506f-228">We recommend that you use this approach only when the size of the cached data is small.</span></span> <span data-ttu-id="b506f-229">Para más información, consulte [Mejorar el rendimiento de las soluciones de ER agregando orígenes de datos de CAMPO CALCULADO parametrizados](er-calculated-field-ds-performance.md).</span><span class="sxs-lookup"><span data-stu-id="b506f-229">For more information, see [Improve the performance of ER solutions by adding parameterized CALCULATED FIELD data sources](er-calculated-field-ds-performance.md).</span></span>

#### <a name="use-a-join-data-source"></a><a name="use-join-datasource"></a><span data-ttu-id="b506f-230">Uso de un origen de datos JOIN</span><span class="sxs-lookup"><span data-stu-id="b506f-230">Use a JOIN data source</span></span>

<span data-ttu-id="b506f-231">Un origen de datos **JOIN** permite que una consulta obtenga varios registros conectados.</span><span class="sxs-lookup"><span data-stu-id="b506f-231">A **JOIN** data source enables several connected records to be fetched by one query.</span></span> <span data-ttu-id="b506f-232">No es necesario utilizar una consulta separada para obtener cada registro conectado.</span><span class="sxs-lookup"><span data-stu-id="b506f-232">A separate query doesn't have to be used to fetch each connected record.</span></span> <span data-ttu-id="b506f-233">Por ejemplo, si tiene 1000 líneas y obtiene datos de artículo para cada línea por relación, tendrá 1001 consultas (= 1000 + 1).</span><span class="sxs-lookup"><span data-stu-id="b506f-233">For example, if you have 1,000 lines, and you fetch item data for each line by relation, you will have 1,001 queries (= 1,000 + 1).</span></span> <span data-ttu-id="b506f-234">Si usa un origen de datos **JOIN**, utilizará solo una consulta para obtener los mismos datos.</span><span class="sxs-lookup"><span data-stu-id="b506f-234">If you use a **JOIN** data source, you will use only one query to fetch the same data.</span></span> <span data-ttu-id="b506f-235">Para obtener más información, consulte [Usar los orígenes de datos de JOIN en asignaciones de modelos de ER para obtener datos de varias tablas de aplicación](er-join-data-sources.md)</span><span class="sxs-lookup"><span data-stu-id="b506f-235">For more information, see [Use JOIN data sources in ER model mappings to get data from multiple application tables](er-join-data-sources.md).</span></span>

#### <a name="use-the-filter-function-instead-of-the-where-function"></a><a name="filter"></a><span data-ttu-id="b506f-236">Utilice la función FILTER en lugar de la función WHERE</span><span class="sxs-lookup"><span data-stu-id="b506f-236">Use the FILTER function instead of the WHERE function</span></span>

<span data-ttu-id="b506f-237">La función **[FILTER](er-functions-list-filter.md)** ejecuta condiciones en SQL Server, mientras que la función **WHERE** obtiene todos los datos de la lista, un registro a la vez, y aplica la condición para cada registro.</span><span class="sxs-lookup"><span data-stu-id="b506f-237">The **[FILTER](er-functions-list-filter.md)** function runs conditions on SQL Server, whereas the **WHERE** function fetches all data from the list, one record at a time, and applies the condition for each record.</span></span> <span data-ttu-id="b506f-238">Por ejemplo, desea seleccionar un registro de 1000 registros.</span><span class="sxs-lookup"><span data-stu-id="b506f-238">For example, you want to select one record out of 1,000 records.</span></span> <span data-ttu-id="b506f-239">Si utiliza **WHERE**, se recuperarán los 1000 registros.</span><span class="sxs-lookup"><span data-stu-id="b506f-239">If you use **WHERE**, all 1,000 records will be fetched.</span></span> <span data-ttu-id="b506f-240">Sin embargo, si usa **FILTER**, se obtendrá exactamente un registro.</span><span class="sxs-lookup"><span data-stu-id="b506f-240">However, if you use **FILTER**, exactly one record will be fetched.</span></span> <span data-ttu-id="b506f-241">**FILTER** también puede usar índices en el lado de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b506f-241">**FILTER** can also use indexes on the database side.</span></span>

#### <a name="using-collected-data-functions-or-an-accumulated-data-data-source"></a><a name="collected-data"></a><span data-ttu-id="b506f-242">Uso de funciones de datos recopilados o un origen de datos de datos acumulados</span><span class="sxs-lookup"><span data-stu-id="b506f-242">Using collected data functions or an accumulated data data source</span></span>

<span data-ttu-id="b506f-243">Si su configuración tiene un componente *group by* que resume los datos obtenidos previamente por informe, el componente recuperará todos los datos nuevamente.</span><span class="sxs-lookup"><span data-stu-id="b506f-243">If your configuration has a *group by* component that summarizes previously fetched data by report, the component will fetch all the data again.</span></span> <span data-ttu-id="b506f-244">Al utilizar las funciones de datos recopilados, habilita a ER para acumular datos durante la primera búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b506f-244">By using collected data functions, you enable ER to accumulate data during the first fetch.</span></span> <span data-ttu-id="b506f-245">Para más información, consulte [ER Configurar el formato para contar y sumar](tasks/er-format-counting-summing-2.md).</span><span class="sxs-lookup"><span data-stu-id="b506f-245">For more information, see [ER Configure format to do counting and summing](tasks/er-format-counting-summing-2.md).</span></span>

#### <a name="rewrite-parts-of-the-configuration-in-x"></a><span data-ttu-id="b506f-246">Reescribir partes de la configuración en X++</span><span class="sxs-lookup"><span data-stu-id="b506f-246">Rewrite parts of the configuration in X++</span></span>

<span data-ttu-id="b506f-247">ER admite métodos de llamada de tablas y clases, incluidas las extensiones.</span><span class="sxs-lookup"><span data-stu-id="b506f-247">ER supports calling methods of tables and classes, including extensions.</span></span> <span data-ttu-id="b506f-248">Considere la posibilidad de reescribir partes de la asignación del modelo en X++ para ayudar a mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="b506f-248">Consider rewriting parts of the model mapping in X++ to help improve performance.</span></span>

<span data-ttu-id="b506f-249">ER puede consumir datos de las siguientes fuentes:</span><span class="sxs-lookup"><span data-stu-id="b506f-249">ER can consume data from the following sources:</span></span>

- <span data-ttu-id="b506f-250">Clases (orígenes de datos **objeto** y **clase**)</span><span class="sxs-lookup"><span data-stu-id="b506f-250">Classes (**object** and **class** data sources)</span></span>
- <span data-ttu-id="b506f-251">Tablas (orígenes de datos **mesa** y **registros de la tabla**)</span><span class="sxs-lookup"><span data-stu-id="b506f-251">Tables (**table** and **table records** data sources)</span></span>

<span data-ttu-id="b506f-252">La [API de ER](er-apis-app73.md#how-to-access-internal-x-objects-by-using-erobjectsfactory) también proporciona una forma de enviar datos precalculados desde el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="b506f-252">The [ER API](er-apis-app73.md#how-to-access-internal-x-objects-by-using-erobjectsfactory) also provides a way to send precalculated data from the calling code.</span></span> <span data-ttu-id="b506f-253">El paquete de aplicaciones contiene numerosos ejemplos de este enfoque.</span><span class="sxs-lookup"><span data-stu-id="b506f-253">The application suite contains numerous examples of this approach.</span></span>
