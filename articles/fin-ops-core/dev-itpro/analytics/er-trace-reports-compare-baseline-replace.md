---
title: Mejoras en el seguimiento de los resultados de informes de ER generados y su comparación con valores de línea base
description: Este tema describe las mejoras a la función de referencia de ER en la versión 10.0.3 (junio 2019) de Microsoft Dynamics 365 for Finance and Operations.
author: NickSelin
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 483d3ac7cd3192ffd4c785c4031a168af503f087
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5743614"
---
# <a name="improvements-in-tracing-the-results-of-generated-er-reports-and-comparing-them-with-baseline-values"></a><span data-ttu-id="a1016-103">Mejoras en el seguimiento de los resultados de informes de ER generados y su comparación con valores de línea base</span><span class="sxs-lookup"><span data-stu-id="a1016-103">Improvements in tracing the results of generated ER reports and comparing them with baseline values</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="a1016-104">En este tema se describe el primer conjunto de mejoras que se han hecho en la característica de línea base del marco de informes electrónicos (ER).</span><span class="sxs-lookup"><span data-stu-id="a1016-104">This topic describes the first set of improvements that have been made to the baseline feature of the Electronic reporting (ER) framework.</span></span> <span data-ttu-id="a1016-105">Estas mejoras están disponibles en la versión 10.0.3 de Microsoft Dynamics 365 for Finance and Operations (junio de 2019) y posteriores.</span><span class="sxs-lookup"><span data-stu-id="a1016-105">These improvements are available in Microsoft Dynamics 365 for Finance and Operations version 10.0.3 (June 2019) and later.</span></span>

## <a name="automate-the-setting-of-baseline-rules"></a><span data-ttu-id="a1016-106">Automatizar la configuración de reglas de línea base</span><span class="sxs-lookup"><span data-stu-id="a1016-106">Automate the setting of baseline rules</span></span>

<span data-ttu-id="a1016-107">En el tema [Realizar un seguimiento de los resultados de informe generados y compararlos con valores de línea base](er-trace-reports-compare-baseline.md) se explica cómo configurar el marco de ER para recopilar información sobre ejecuciones del formato de ER y evaluar los resultados de esas ejecuciones.</span><span class="sxs-lookup"><span data-stu-id="a1016-107">The [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic explains how to configure the ER framework to collect information about ER format executions and evaluate the results of those executions.</span></span> <span data-ttu-id="a1016-108">El ejemplo de este tema muestra los pasos que se debe completar.</span><span class="sxs-lookup"><span data-stu-id="a1016-108">The example in this topic shows the steps that must be completed.</span></span>

<span data-ttu-id="a1016-109">Estos son algunos de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a1016-109">Here are some of the steps:</span></span>

- <span data-ttu-id="a1016-110">Ejecutar un formato de ER para generar un archivo de salida y para almacenar localmente el archivo.</span><span class="sxs-lookup"><span data-stu-id="a1016-110">Run an ER format to generate an outbound file, and store the file locally.</span></span>
- <span data-ttu-id="a1016-111">Agregar el archivo almacenado localmente como adjunto de la línea base que se agregó para un formato de ER.</span><span class="sxs-lookup"><span data-stu-id="a1016-111">Add the locally stored file as an attachment of the baseline that was added for an ER format.</span></span>
- <span data-ttu-id="a1016-112">Configurar la regla de línea base para la línea base agregada.</span><span class="sxs-lookup"><span data-stu-id="a1016-112">Configure the baseline rule for the added baseline.</span></span> <span data-ttu-id="a1016-113">Esta configuración incluye los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="a1016-113">This configuration includes the following steps:</span></span>

    - <span data-ttu-id="a1016-114">Especificar un elemento del formato de ER que se utiliza para generar un archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="a1016-114">Specify an ER format element that is used to generate an outbound file.</span></span>
    - <span data-ttu-id="a1016-115">Seleccionar el archivo adjunto que hace referencia al archivo de salida generado.</span><span class="sxs-lookup"><span data-stu-id="a1016-115">Select the attachment that refers to the generated outbound file.</span></span>

> [!NOTE]
> <span data-ttu-id="a1016-116">Estos pasos debe realizarse manualmente, aunque las nuevas funcionalidades de ER permiten su automatización.</span><span class="sxs-lookup"><span data-stu-id="a1016-116">These steps must be done manually, even though the new ER capabilities enable them to be automated.</span></span> <span data-ttu-id="a1016-117">Para obtener más información acerca de esta característica, complete el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a1016-117">To learn more about this feature, complete the following example.</span></span>

## <a name="example-automate-the-setting-of-baseline-rules"></a><span data-ttu-id="a1016-118">Ejemplo: Automatizar la configuración de reglas de línea base</span><span class="sxs-lookup"><span data-stu-id="a1016-118">Example: Automate the setting of baseline rules</span></span>

<span data-ttu-id="a1016-119">Para completar los pasos de este ejemplo, primero debe completar los pasos del ejemplo en el tema [Realizar un seguimiento de los resultados de informe generados y compararlos con valores de línea base](er-trace-reports-compare-baseline.md), a través de la sección "Agregar una nueva línea base para un formato de ER designado".</span><span class="sxs-lookup"><span data-stu-id="a1016-119">To complete the steps in this example, you must first complete the steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic, up through the "Add a new baseline for a designed ER format" section.</span></span>

### <a name="review-added-baseline"></a><span data-ttu-id="a1016-120">Revisar línea base agregada</span><span class="sxs-lookup"><span data-stu-id="a1016-120">Review added baseline</span></span>

1. <span data-ttu-id="a1016-121">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="a1016-121">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="a1016-122">Seleccione **Líneas base**.</span><span class="sxs-lookup"><span data-stu-id="a1016-122">Select **Baselines**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a1016-123">El botón **Líneas base** en el panel de acciones solo está disponible cuando el parámetro de usuario de ER **Ejecutar en modo depuración** está activado para la empresa actual.</span><span class="sxs-lookup"><span data-stu-id="a1016-123">The **Baselines** button on the Action Pane is available only when the **Run in debug mode** ER user parameter is turned on for the current company.</span></span>

<span data-ttu-id="a1016-124">Se ha agregado la línea base para el formato seleccionado **Formato para aprender líneas base de ER**, pero las reglas de línea base aún no se han agregado para esta línea base.</span><span class="sxs-lookup"><span data-stu-id="a1016-124">The baseline has been added for the selected **Format to learn ER baselines** format, but the baseline rules haven't yet been added for this baseline.</span></span>

<span data-ttu-id="a1016-125">![Página de líneas base del formato de los informes electrónicos, aún sin reglas](media/GER-BaselineSample-AddBaseline2.PNG "Captura de pantalla de la página de líneas base del formato de los informes electrónicos")</span><span class="sxs-lookup"><span data-stu-id="a1016-125">![Electronic reporting format baselines page, no rules yet](media/GER-BaselineSample-AddBaseline2.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

### <a name="make-a-new-baseline-rule"></a><span data-ttu-id="a1016-126">Crear una nueva regla de línea base</span><span class="sxs-lookup"><span data-stu-id="a1016-126">Make a new baseline rule</span></span>

1. <span data-ttu-id="a1016-127">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="a1016-127">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="a1016-128">En el árbol, expanda **Modelo para aprender líneas base de ER**.</span><span class="sxs-lookup"><span data-stu-id="a1016-128">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="a1016-129">En el árbol, seleccione **Modelo para aprender líneas base de ER\\Formato para aprender líneas base de ER**.</span><span class="sxs-lookup"><span data-stu-id="a1016-129">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="a1016-130">En la ficha desplegable **Versiones**, seleccione **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="a1016-130">On the **Versions** FastTab, select **Run**.</span></span>
5. <span data-ttu-id="a1016-131">En el campo **Introducir id.**, introduzca **1**.</span><span class="sxs-lookup"><span data-stu-id="a1016-131">In the **Enter Id** field, enter **1**.</span></span>
6. <span data-ttu-id="a1016-132">Establezca la opción **Crear archivos de línea base** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="a1016-132">Set the **Make baseline files** option to **Yes**.</span></span>
7. <span data-ttu-id="a1016-133">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1016-133">Select **OK**.</span></span>
8. <span data-ttu-id="a1016-134">Seleccione **Líneas base**.</span><span class="sxs-lookup"><span data-stu-id="a1016-134">Select **Baselines**.</span></span>

    <span data-ttu-id="a1016-135">![Página de líneas base del formato de los informes electrónicos, líneas base seleccionadas](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Captura de pantalla de la página de líneas base del formato de los informes electrónicos")</span><span class="sxs-lookup"><span data-stu-id="a1016-135">![Electronic reporting format baselines page, baselines selected](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

    <span data-ttu-id="a1016-136">El archivo de salida generado se ha adjuntado automáticamente a la línea base del formato de ER ejecutado.</span><span class="sxs-lookup"><span data-stu-id="a1016-136">The generated outbound file has been automatically attached to the baseline of the executed ER format.</span></span> <span data-ttu-id="a1016-137">La regla de línea base se ha agregado automáticamente a esta línea base y también contiene la referencia al archivo adjunto.</span><span class="sxs-lookup"><span data-stu-id="a1016-137">The baseline rule has been automatically added to this baseline and also contains the reference to the attached file.</span></span>

9. <span data-ttu-id="a1016-138">En el campo **Nombre**, especifique **Línea base 1**.</span><span class="sxs-lookup"><span data-stu-id="a1016-138">In the **Name** field, enter **Baseline 1**.</span></span>
10. <span data-ttu-id="a1016-139">En el campo **Máscara de nombre de archivo**, introduzca **.xml**.</span><span class="sxs-lookup"><span data-stu-id="a1016-139">In the **File name mask** field, enter **.xml**.</span></span>
11. <span data-ttu-id="a1016-140">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a1016-140">Select **Save**.</span></span>

### <a name="run-the-format"></a><span data-ttu-id="a1016-141">Ejecutar el formato</span><span class="sxs-lookup"><span data-stu-id="a1016-141">Run the format</span></span>

<span data-ttu-id="a1016-142">Ya está listo para completar el resto de pasos del ejemplo del tema [Realizar un seguimiento de los resultados de informe generados y compararlos con valores de línea base](er-trace-reports-compare-baseline.md), empezando por la sección "Ejecutar el formato de ER diseñado y revisar el registro para analizar los resultados".</span><span class="sxs-lookup"><span data-stu-id="a1016-142">You're now ready to complete the remaining steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic, starting from the "Run the designed ER format and review the log to analyze the results" section.</span></span>

> [!NOTE]
> <span data-ttu-id="a1016-143">Cuando elimine la regla de línea base agregada automáticamente en la ficha desplegable **Líneas base**, los archivos adjuntos a los que se hace referencia no se eliminan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a1016-143">When you delete the automatically added baseline rule on the **Baselines** FastTab, the referenced attachment isn't automatically deleted.</span></span>

## <a name="configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a><span data-ttu-id="a1016-144">Configurar la línea base de modo que ignore constantemente las partes que cambian de la salida de ER</span><span class="sxs-lookup"><span data-stu-id="a1016-144">Configure the baseline so that it ignores constantly changing parts of the ER output</span></span>

<span data-ttu-id="a1016-145">Cuando un formato de ER se haya diseñado para contener información que se cambia cuando se ejecuta el formato, el formato debe requerir el uso de la característica de la línea base de ER para comparar los resultados generados con valores de línea base.</span><span class="sxs-lookup"><span data-stu-id="a1016-145">When an ER format has been designed to contain information that is changed when the format is run, the format must be required to use the ER baseline feature to compare the generated results with baseline values.</span></span> <span data-ttu-id="a1016-146">Por ejemplo, puede que la información sea la fecha y la hora de procesamiento o el identificador único de un documento generado en distintos formatos (identificador único global \[GUID\], etc.).</span><span class="sxs-lookup"><span data-stu-id="a1016-146">For example, the information might be the processing date and time or the unique identifier of a generated document in different formats (globally unique identifier \[GUID\], and so on).</span></span> <span data-ttu-id="a1016-147">Las nuevas funcionalidades de ER le permiten configurar la regla de línea base de modo que ignore los elementos que pueden cambiarse de un formato de ER cuando el formato se ejecute con el propósito de comparar valores de línea base con los resultados de la ejecución del formato.</span><span class="sxs-lookup"><span data-stu-id="a1016-147">The new ER capabilities let you configure the baseline rule so that it ignores changeable elements of an ER format when the format is run with the purpose of comparing baseline values with the results of the format's execution.</span></span> <span data-ttu-id="a1016-148">Para obtener más información acerca de esta característica, complete el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a1016-148">To learn more about this feature, complete the following example.</span></span>

## <a name="example-configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a><span data-ttu-id="a1016-149">Ejemplo: Configurar la línea base de modo que ignore constantemente las partes que cambian de la salida de ER</span><span class="sxs-lookup"><span data-stu-id="a1016-149">Example: Configure the baseline so that it ignores constantly changing parts of the ER output</span></span>

<span data-ttu-id="a1016-150">Para completar los pasos de este ejemplo, primero debe completar los pasos del ejemplo en el tema [Realizar un seguimiento de los resultados de informe generados y compararlos con valores de línea base](er-trace-reports-compare-baseline.md).</span><span class="sxs-lookup"><span data-stu-id="a1016-150">To complete the steps in this example, you must first complete the steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic.</span></span>

### <a name="modify-a-configured-er-format"></a><span data-ttu-id="a1016-151">Modificar un formato de ER configurado</span><span class="sxs-lookup"><span data-stu-id="a1016-151">Modify a configured ER format</span></span>

1. <span data-ttu-id="a1016-152">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="a1016-152">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="a1016-153">En el árbol, expanda **Modelo para aprender líneas base de ER**.</span><span class="sxs-lookup"><span data-stu-id="a1016-153">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="a1016-154">En el árbol, seleccione **Modelo para aprender líneas base de ER\\Formato para aprender líneas base de ER**.</span><span class="sxs-lookup"><span data-stu-id="a1016-154">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="a1016-155">Seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="a1016-155">Select **Designer**.</span></span>
5. <span data-ttu-id="a1016-156">En el árbol, seleccione **Salida\\Documento**.</span><span class="sxs-lookup"><span data-stu-id="a1016-156">In the tree, select **Output\\Document**.</span></span>
6. <span data-ttu-id="a1016-157">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a1016-157">Select **Add**.</span></span>
7. <span data-ttu-id="a1016-158">En el cuadro de diálogo desplegable, en el árbol, seleccione **XML\\Atributo**.</span><span class="sxs-lookup"><span data-stu-id="a1016-158">In the drop-down dialog box, in the tree, select **XML\\Attribute**.</span></span>
8. <span data-ttu-id="a1016-159">En el campo **Nombre**, introduzca **ProcessingDateTime**.</span><span class="sxs-lookup"><span data-stu-id="a1016-159">In the **Name** field, enter **ProcessingDateTime**.</span></span>
9. <span data-ttu-id="a1016-160">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1016-160">Select **OK**.</span></span>
10. <span data-ttu-id="a1016-161">En la pestaña **Asignación**, en el árbol, seleccione **Salida\\Documento\\ProcessingDateTime**.</span><span class="sxs-lookup"><span data-stu-id="a1016-161">On the **Mapping** tab, in the tree, select **Output\\Document\\ProcessingDateTime**.</span></span>
11. <span data-ttu-id="a1016-162">Seleccione **Editar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="a1016-162">Select **Edit formula**.</span></span>
12. <span data-ttu-id="a1016-163">En el campo **Fórmula**, introduzca la expresión siguiente: **DATETIMEFORMAT(NOW(), "O")**</span><span class="sxs-lookup"><span data-stu-id="a1016-163">In the **Formula** field, enter the following expression: **DATETIMEFORMAT(NOW(), "O")**</span></span>
13. <span data-ttu-id="a1016-164">Seleccione **Guardar** y, a continuación, seleccione **Prueba**.</span><span class="sxs-lookup"><span data-stu-id="a1016-164">Select **Save**, and then select **Test**.</span></span>
14. <span data-ttu-id="a1016-165">Seleccione **Prueba** de nuevo para volver a probar la expresión configurada.</span><span class="sxs-lookup"><span data-stu-id="a1016-165">Select **Test** again to retest the configured expression.</span></span>

    <span data-ttu-id="a1016-166">![Página del diseñador de fórmulas](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Captura de pantalla de la página del diseñador de fórmulas")</span><span class="sxs-lookup"><span data-stu-id="a1016-166">![Formula designer page](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Screenshot of the Formula designer page")</span></span>

    > [!NOTE]
    > <span data-ttu-id="a1016-167">La pestaña **Resultado de prueba** muestra que la expresión configurada devuelve un valor de fecha y hora diferente cada vez que se invoca.</span><span class="sxs-lookup"><span data-stu-id="a1016-167">The **Test result** tab shows that the configured expression returns a different date and time value whenever it's called.</span></span>

15. <span data-ttu-id="a1016-168">Cierre la página **Diseñador de fórmula** y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a1016-168">Close the **Formula designer** page, and then select **Save**.</span></span>

    <span data-ttu-id="a1016-169">![Página de diseñador de formato](media/GER-BaselineSample-FormatMappingDesign2.PNG "Captura de pantalla de la página del diseñador de formatos")</span><span class="sxs-lookup"><span data-stu-id="a1016-169">![Format designer page](media/GER-BaselineSample-FormatMappingDesign2.PNG "Screenshot of the Format designer page")</span></span>

16. <span data-ttu-id="a1016-170">Cierre la página **Diseñador de formato**.</span><span class="sxs-lookup"><span data-stu-id="a1016-170">Close the **Format designer** page.</span></span>

### <a name="remove-an-existing-baseline-rule"></a><span data-ttu-id="a1016-171">Eliminar una regla de línea base existente</span><span class="sxs-lookup"><span data-stu-id="a1016-171">Remove an existing baseline rule</span></span>

1. <span data-ttu-id="a1016-172">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="a1016-172">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="a1016-173">Seleccione **Líneas base**.</span><span class="sxs-lookup"><span data-stu-id="a1016-173">Select **Baselines**.</span></span>
3. <span data-ttu-id="a1016-174">En la lista de líneas base, seleccione la línea base configurada para el formato **Formato para aprender líneas base de ER**.</span><span class="sxs-lookup"><span data-stu-id="a1016-174">In the list of baselines, select the baseline that is configured for the **Format to learn ER baselines** format.</span></span>
4. <span data-ttu-id="a1016-175">En la ficha desplegable **Líneas base**, seleccione **Eliminar** para eliminar la regla de línea base que configuró anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a1016-175">On the **Baselines** FastTab, select **Delete** to remove the baseline rule that you configured earlier.</span></span>

<span data-ttu-id="a1016-176">![Página de líneas base del formato de los informes electrónicos, eliminado](media/GER-BaselineSample-AddBaseline3.PNG "Captura de pantalla de la página de líneas base del formato de los informes electrónicos")</span><span class="sxs-lookup"><span data-stu-id="a1016-176">![Electronic reporting format baselines page, deleted](media/GER-BaselineSample-AddBaseline3.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

### <a name="define-replacements-for-bindings-of-designed-er-format"></a><span data-ttu-id="a1016-177">Definir sustituciones para los enlaces de formato de ER diseñado</span><span class="sxs-lookup"><span data-stu-id="a1016-177">Define replacements for bindings of designed ER format</span></span>

1. <span data-ttu-id="a1016-178">En la página **Configuraciones**, en la ficha desplegable **Sustituciones**, seleccione **Seleccionar componentes**.</span><span class="sxs-lookup"><span data-stu-id="a1016-178">On the **Configurations** page, on the **Replacements** FastTab, select **Select components**.</span></span>
2. <span data-ttu-id="a1016-179">En el árbol de componentes del formato, expanda **Salida**, expanda **Salida\\Documento** y active la casilla para **Salida\\Documento\\ProcessingDateTime**.</span><span class="sxs-lookup"><span data-stu-id="a1016-179">In the format components tree, expand **Output**, expand **Output\\Document**, and then select the check box for **Output\\Document\\ProcessingDateTime**.</span></span>
3. <span data-ttu-id="a1016-180">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1016-180">Select **OK**.</span></span>

<span data-ttu-id="a1016-181">![Página de líneas base del formato de los informes electrónicos, componentes](media/GER-BaselineSample-AddBaseline4.PNG "Captura de pantalla de la página de líneas base del formato de los informes electrónicos")</span><span class="sxs-lookup"><span data-stu-id="a1016-181">![Electronic reporting format baselines page, components](media/GER-BaselineSample-AddBaseline4.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

<span data-ttu-id="a1016-182">Se ha agregado el componente del formato de ER seleccioando a la lista de componentes en la ficha desplegable **Sustituciones**.</span><span class="sxs-lookup"><span data-stu-id="a1016-182">The selected ER format component has been added to the list of components on the **Replacements** FastTab.</span></span> <span data-ttu-id="a1016-183">Cuando el formato de ER de la base se ejecuta en modo de depuración, el enlace del formato para cada componente se sustituirá por el enlace que se muestra en la columna **Enlace** .</span><span class="sxs-lookup"><span data-stu-id="a1016-183">When the base ER format is run in debug mode, the format's binding for each component will be replaced by the binding that is shown in the **Binding** column.</span></span> <span data-ttu-id="a1016-184">Para cambiar el enlace predeterminado para un componente que se muestra en la ficha desplegable **Sustituciones**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a1016-184">To change the default binding for a component that is listed on the **Replacements** FastTab, select **Edit**.</span></span>

### <a name="make-a-new-baseline-rule"></a><span data-ttu-id="a1016-185">Crear una nueva regla de línea base</span><span class="sxs-lookup"><span data-stu-id="a1016-185">Make a new baseline rule</span></span>

<span data-ttu-id="a1016-186">Siga los pasos de la sección "Ejemplo: Automatizar la configuración de reglas de línea base" descrita anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="a1016-186">Follow the steps in the "Example: Automate the setting of baseline rules" section earlier in this topic.</span></span> <span data-ttu-id="a1016-187">Una notificación le advierte que el archivo de salida se ha generado mediante el uso de la configuración de línea base, y que se ha producido una sustitución forzada de los enlaces de formato.</span><span class="sxs-lookup"><span data-stu-id="a1016-187">A notification warns you that the outbound file has been generated by using baseline settings, and that a forced replacement of the format bindings has occurred.</span></span>

<span data-ttu-id="a1016-188">![Notificación en la página de configuración](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Captura de pantalla de la notificación en la página Configuraciones")</span><span class="sxs-lookup"><span data-stu-id="a1016-188">![Notification on the Configurations page](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Screenshot of the notification on the Configurations page")</span></span>

### <a name="suppress-warnings-about-the-replacement-of-format-bindings"></a><span data-ttu-id="a1016-189">Suprimir avisos sobre la sustitución de enlaces de formato</span><span class="sxs-lookup"><span data-stu-id="a1016-189">Suppress warnings about the replacement of format bindings</span></span>

<span data-ttu-id="a1016-190">Al configurar determinados parámetros de ER, puede suprimir las notificaciones que advierten sobre la sustitución de enlaces de formato.</span><span class="sxs-lookup"><span data-stu-id="a1016-190">By setting specific ER parameters, you can suppress notifications that warn about the replacement of format bindings.</span></span> <span data-ttu-id="a1016-191">Esta supresión puede resultar útil cuando los enlaces de formato se reemplazan en un modo desatendido mediante el uso de la Regression Suite Automation Tool.</span><span class="sxs-lookup"><span data-stu-id="a1016-191">This suppression can be useful when format bindings are replaced in an unattended mode by using the Regression Suite Automation Tool.</span></span> <span data-ttu-id="a1016-192">En este caso, el aviso se puede considerar un error del caso de prueba que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="a1016-192">In this case, the warning can be considered a failure of the test case that is running.</span></span>

1. <span data-ttu-id="a1016-193">En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, seleccione **Parámetros de usuario**.</span><span class="sxs-lookup"><span data-stu-id="a1016-193">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, select **User parameters**.</span></span>
2. <span data-ttu-id="a1016-194">Establezca la opción **Suprimir avisos de línea base** en **Sí** y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1016-194">Set the **Suppress baseline warnings** option to **Yes**, and then select **OK**.</span></span>

### <a name="review-the-generated-baseline-file"></a><span data-ttu-id="a1016-195">Revisar el archivo de línea base generado</span><span class="sxs-lookup"><span data-stu-id="a1016-195">Review the generated baseline file</span></span>

1. <span data-ttu-id="a1016-196">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="a1016-196">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="a1016-197">Seleccione **Líneas base**.</span><span class="sxs-lookup"><span data-stu-id="a1016-197">Select **Baselines**.</span></span>
3. <span data-ttu-id="a1016-198">Seleccione **Archivos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="a1016-198">Select **Attachments**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="a1016-199">El archivo generado contiene texto de fecha y hora de procesamiento (**"#"**) del enlace que se configuró en la regla de línea base agregada, no del enlace del formato.</span><span class="sxs-lookup"><span data-stu-id="a1016-199">The generated file contains the processing date and time text (**"#"**) from the binding that was configured in the added baseline rule, not from the format's binding.</span></span>
    
4. <span data-ttu-id="a1016-200">Cierre la página **Archivos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="a1016-200">Close the **Attachments** page.</span></span>

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a><span data-ttu-id="a1016-201">Ejecutar el formato de ER diseñado y revisar el registro para analizar los resultados</span><span class="sxs-lookup"><span data-stu-id="a1016-201">Run the designed ER format and review the log to analyze the results</span></span>

1. <span data-ttu-id="a1016-202">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="a1016-202">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="a1016-203">En el árbol, expanda **Modelo para aprender líneas base de ER**.</span><span class="sxs-lookup"><span data-stu-id="a1016-203">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="a1016-204">En el árbol, seleccione **Modelo para aprender líneas base de ER\\Formato para aprender líneas base de ER**.</span><span class="sxs-lookup"><span data-stu-id="a1016-204">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="a1016-205">En la ficha desplegable **Versiones**, seleccione **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="a1016-205">On the **Versions** FastTab select **Run**.</span></span>
5. <span data-ttu-id="a1016-206">En el campo **Introducir id.**, escriba **1**.</span><span class="sxs-lookup"><span data-stu-id="a1016-206">In the **Enter Id** field, type **1**.</span></span>
6. <span data-ttu-id="a1016-207">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1016-207">Select **OK**.</span></span>
7. <span data-ttu-id="a1016-208">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configurar registros de depuración**.</span><span class="sxs-lookup"><span data-stu-id="a1016-208">Go to **Organization administration** \> **Electronic reporting** \> **Configuration debug logs**.</span></span>

<span data-ttu-id="a1016-209">El registro de ejecución contiene información sobre los resultados de la comparación del archivo generado con la línea base configurada.</span><span class="sxs-lookup"><span data-stu-id="a1016-209">The execution log contains information about the results of the comparison of the generated file with the configured baseline.</span></span> <span data-ttu-id="a1016-210">El registro indica que el archivo generado y la línea base son iguales, aunque el formato ejecutado contiene el enlace para introducir un valor de fecha y hora que cambia constantemente en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="a1016-210">The log indicates that the generated file and the baseline are equal, even though the executed format contains the binding to enter a constantly changing date and time value in the outbound file.</span></span>

> [!NOTE]
> <span data-ttu-id="a1016-211">Aunque el archivo de salida se haya generado mediante el uso de la configuración de línea base que fuerza la sustitución de los enlaces del formato, no recibe ningún aviso sobre la sustitución.</span><span class="sxs-lookup"><span data-stu-id="a1016-211">Although the outbound file has been generated by using baseline settings that force the replacement of the format's bindings, you don't receive any warnings about the replacement.</span></span>

## <a name="exchange-baseline-settings-between-environments"></a><span data-ttu-id="a1016-212">Intercambiar configuración de línea base entre entornos</span><span class="sxs-lookup"><span data-stu-id="a1016-212">Exchange baseline settings between environments</span></span>

### <a name="export-baseline-settings"></a><span data-ttu-id="a1016-213">Exportar configuración de línea base</span><span class="sxs-lookup"><span data-stu-id="a1016-213">Export baseline settings</span></span>

<span data-ttu-id="a1016-214">Las nuevas funcionalidades de ER le permiten exportar la configuración de línea base para el formato de ER seleccionado desde el entorno actual y almacenarla como archivos XML.</span><span class="sxs-lookup"><span data-stu-id="a1016-214">The new ER capabilities let you export baseline settings for the selected ER format from the current environment and store them as XML files.</span></span> 

<span data-ttu-id="a1016-215">Para exportar la configuración de línea base, en la página **Líneas base del formato de informes electrónicos**, seleccione **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="a1016-215">To export baseline settings, on the **Electronic reporting format baselines** page, select **Export**.</span></span>

### <a name="import-baseline-settings"></a><span data-ttu-id="a1016-216">Importar configuración de línea base</span><span class="sxs-lookup"><span data-stu-id="a1016-216">Import baseline settings</span></span>

<span data-ttu-id="a1016-217">La configuración de línea base exportada se puede importar en un entorno diferente.</span><span class="sxs-lookup"><span data-stu-id="a1016-217">Exported baseline settings can be imported into a different environment.</span></span> <span data-ttu-id="a1016-218">El entorno se debe importar primero como formato de ER.</span><span class="sxs-lookup"><span data-stu-id="a1016-218">The environment must first be imported as an ER format.</span></span> <span data-ttu-id="a1016-219">Posteriormente, puede importar la configuración de línea base.</span><span class="sxs-lookup"><span data-stu-id="a1016-219">You can then import the baseline settings.</span></span>

<span data-ttu-id="a1016-220">Para importar la configuración de línea base desde un archivo XML almacenado localmente, en la página **Líneas base del formato de informes electrónicos**, seleccione **Importar** y seleccione **Examinar** para seleccionar el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="a1016-220">To import baseline settings from a locally stored XML file, on the **Electronic reporting format baselines** page, select **Import**, and then select **Browse** to select the XML file.</span></span>

<span data-ttu-id="a1016-221">![Importar el cuadro de diálogo de la configuración de la línea base](media/GER-BaselineSample-ImportBaseline1.PNG "Captura de pantalla del cuadro de diálogo Importar configuración de líneas de base")</span><span class="sxs-lookup"><span data-stu-id="a1016-221">![Import baseline settings dialog box](media/GER-BaselineSample-ImportBaseline1.PNG "Screenshot of the Import baseline settings dialog box")</span></span>

<span data-ttu-id="a1016-222">Para importar la configuración de línea base de un archivo XML almacenado en Microsoft SharePoint Server, según la configuración actual Administración de documentos y el tipo de documento seleccionado, en la página **Líneas base del formato de informes electrónicos**, seleccione **Importar desde origen**.</span><span class="sxs-lookup"><span data-stu-id="a1016-222">To import baseline settings from an XML file that is stored on the Microsoft SharePoint Server, based on the current Document management settings and the selected document type, on the **Electronic reporting format baselines** page, select **Import from source**.</span></span> <span data-ttu-id="a1016-223">A continuación, seleccione el tipo de documento y el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="a1016-223">Then select the document type and the XML file.</span></span> <span data-ttu-id="a1016-224">El tipo de documento requerido para acceder a la carpeta de SharePoint deben configurarse con antelación.</span><span class="sxs-lookup"><span data-stu-id="a1016-224">The required document type to access the SharePoint folder must be configured in advance.</span></span>

<span data-ttu-id="a1016-225">![Importación del cuadro de diálogo de origen](media/GER-BaselineSample-ImportBaseline2.PNG "Captura de pantalla del cuadro de diálogo Importar del origen")</span><span class="sxs-lookup"><span data-stu-id="a1016-225">![Import from source dialog box](media/GER-BaselineSample-ImportBaseline2.PNG "Screenshot of the Import from source dialog box")</span></span>

> [!NOTE]
> <span data-ttu-id="a1016-226">Puede utilizar el Grabador de tareas para registrar los pasos a fin de seleccionar el tipo de documentos requerido y el nombre de archivo en el cuadro de diálogo **Importar desde origen**.</span><span class="sxs-lookup"><span data-stu-id="a1016-226">You can use Task recorder to record the steps for selecting the required document type and the file name in the **Import from source** dialog box.</span></span> <span data-ttu-id="a1016-227">De esta manera, puede conservar la configuración de línea base requerida en SharePoint Server e importarla automáticamente mediante la reproducción de una grabación de tareas cuando ejecute pruebas automatizadas usando la Regression Suite Automation Tool.</span><span class="sxs-lookup"><span data-stu-id="a1016-227">In this way, you can keep required baseline settings on SharePoint Server and then automatically import them by playing a task recording when you run automated tests by using the Regression Suite Automation Tool.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a1016-228">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a1016-228">Additional resources</span></span>

- [<span data-ttu-id="a1016-229">Realizar un seguimiento de los resultados de informe generados y compararlos con valores de línea base</span><span class="sxs-lookup"><span data-stu-id="a1016-229">Trace generated report results and compare them with baseline values</span></span>](er-trace-reports-compare-baseline.md)
- [<span data-ttu-id="a1016-230">Recursos del Grabador de tareas</span><span class="sxs-lookup"><span data-stu-id="a1016-230">Task recorder resources</span></span>](../user-interface/task-recorder.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]