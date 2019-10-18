---
title: Mejoras en el seguimiento de los resultados de informes de ER generados y su comparación con valores de línea base
description: En este tema se proporciona información sobre cómo se ha mejorado la característica de la línea base de ER en la versión 10.0.3 de Microsoft Dynamics 365 for Finance and Operations (junio de 2019).
author: NickSelin
manager: AnnBe
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: a260be0f8659106907b26bf69bee3b33b09d0c24
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181344"
---
# <a name="improvements-in-tracing-the-results-of-generated-er-reports-and-comparing-them-with-baseline-values"></a><span data-ttu-id="86713-103">Mejoras en el seguimiento de los resultados de informes de ER generados y su comparación con valores de línea base</span><span class="sxs-lookup"><span data-stu-id="86713-103">Improvements in tracing the results of generated ER reports and comparing them with baseline values</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="86713-104">En este tema se describe el primer conjunto de mejoras que se han hecho en la característica de línea base del marco de informes electrónicos (ER).</span><span class="sxs-lookup"><span data-stu-id="86713-104">This topic describes the first set of improvements that have been made to the baseline feature of the Electronic reporting (ER) framework.</span></span> <span data-ttu-id="86713-105">Estas mejoras están disponibles en la versión 10.0.3 de Microsoft Dynamics 365 for Finance and Operations (junio de 2019) y posteriores.</span><span class="sxs-lookup"><span data-stu-id="86713-105">These improvements are available in Microsoft Dynamics 365 for Finance and Operations version 10.0.3 (June 2019) and later.</span></span>

## <a name="automate-the-setting-of-baseline-rules"></a><span data-ttu-id="86713-106">Automatizar la configuración de reglas de línea base</span><span class="sxs-lookup"><span data-stu-id="86713-106">Automate the setting of baseline rules</span></span>

<span data-ttu-id="86713-107">En el tema [Realizar un seguimiento de los resultados de informe generados y compararlos con valores de línea base](er-trace-reports-compare-baseline.md) se explica cómo configurar el marco de ER para recopilar información sobre ejecuciones del formato de ER y evaluar los resultados de esas ejecuciones.</span><span class="sxs-lookup"><span data-stu-id="86713-107">The [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic explains how to configure the ER framework to collect information about ER format executions and evaluate the results of those executions.</span></span> <span data-ttu-id="86713-108">El ejemplo de este tema muestra los pasos que se debe completar.</span><span class="sxs-lookup"><span data-stu-id="86713-108">The example in this topic shows the steps that must be completed.</span></span>

<span data-ttu-id="86713-109">Estos son algunos de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="86713-109">Here are some of the steps:</span></span>

- <span data-ttu-id="86713-110">Ejecutar un formato de ER para generar un archivo de salida y para almacenar localmente el archivo.</span><span class="sxs-lookup"><span data-stu-id="86713-110">Run an ER format to generate an outbound file, and store the file locally.</span></span>
- <span data-ttu-id="86713-111">Agregar el archivo almacenado localmente como adjunto de la línea base que se agregó para un formato de ER.</span><span class="sxs-lookup"><span data-stu-id="86713-111">Add the locally stored file as an attachment of the baseline that was added for an ER format.</span></span>
- <span data-ttu-id="86713-112">Configurar la regla de línea base para la línea base agregada.</span><span class="sxs-lookup"><span data-stu-id="86713-112">Configure the baseline rule for the added baseline.</span></span> <span data-ttu-id="86713-113">Esta configuración incluye los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="86713-113">This configuration includes the following steps:</span></span>

    - <span data-ttu-id="86713-114">Especificar un elemento del formato de ER que se utiliza para generar un archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="86713-114">Specify an ER format element that is used to generate an outbound file.</span></span>
    - <span data-ttu-id="86713-115">Seleccionar el archivo adjunto que hace referencia al archivo de salida generado.</span><span class="sxs-lookup"><span data-stu-id="86713-115">Select the attachment that refers to the generated outbound file.</span></span>

> [!NOTE]
> <span data-ttu-id="86713-116">Estos pasos debe realizarse manualmente, aunque las nuevas funcionalidades de ER permiten su automatización.</span><span class="sxs-lookup"><span data-stu-id="86713-116">These steps must be done manually, even though the new ER capabilities enable them to be automated.</span></span> <span data-ttu-id="86713-117">Para obtener más información acerca de esta característica, complete el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="86713-117">To learn more about this feature, complete the following example.</span></span>

## <a name="example-automate-the-setting-of-baseline-rules"></a><span data-ttu-id="86713-118">Ejemplo: Automatizar la configuración de reglas de línea base</span><span class="sxs-lookup"><span data-stu-id="86713-118">Example: Automate the setting of baseline rules</span></span>

<span data-ttu-id="86713-119">Para completar los pasos de este ejemplo, primero debe completar los pasos del ejemplo en el tema [Realizar un seguimiento de los resultados de informe generados y compararlos con valores de línea base](er-trace-reports-compare-baseline.md), a través de la sección "Agregar una nueva línea base para un formato de ER designado".</span><span class="sxs-lookup"><span data-stu-id="86713-119">To complete the steps in this example, you must first complete the steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic, up through the "Add a new baseline for a designed ER format" section.</span></span>

### <a name="review-added-baseline"></a><span data-ttu-id="86713-120">Revisar línea base agregada</span><span class="sxs-lookup"><span data-stu-id="86713-120">Review added baseline</span></span>

1. <span data-ttu-id="86713-121">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="86713-121">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="86713-122">Seleccione **Líneas base**.</span><span class="sxs-lookup"><span data-stu-id="86713-122">Select **Baselines**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="86713-123">El botón **Líneas base** en el panel de acciones solo está disponible cuando el parámetro de usuario de ER **Ejecutar en modo depuración** está activado para la empresa actual.</span><span class="sxs-lookup"><span data-stu-id="86713-123">The **Baselines** button on the Action Pane is available only when the **Run in debug mode** ER user parameter is turned on for the current company.</span></span>

<span data-ttu-id="86713-124">Se ha agregado la línea base para el formato seleccionado **Formato para aprender líneas base de ER**, pero las reglas de línea base aún no se han agregado para esta línea base.</span><span class="sxs-lookup"><span data-stu-id="86713-124">The baseline has been added for the selected **Format to learn ER baselines** format, but the baseline rules haven't yet been added for this baseline.</span></span>

<span data-ttu-id="86713-125">![Páginas de líneas base del formato de informes electrónicos](media/GER-BaselineSample-AddBaseline2.PNG "Captura de pantalla de la página de líneas base del formato de informes electrónicos")</span><span class="sxs-lookup"><span data-stu-id="86713-125">![Electronic reporting format baselines page](media/GER-BaselineSample-AddBaseline2.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

### <a name="make-a-new-baseline-rule"></a><span data-ttu-id="86713-126">Crear una nueva regla de línea base</span><span class="sxs-lookup"><span data-stu-id="86713-126">Make a new baseline rule</span></span>

1. <span data-ttu-id="86713-127">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="86713-127">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="86713-128">En el árbol, expanda **Modelo para aprender líneas base de ER**.</span><span class="sxs-lookup"><span data-stu-id="86713-128">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="86713-129">En el árbol, seleccione **Modelo para aprender líneas base de ER\\Formato para aprender líneas base de ER**.</span><span class="sxs-lookup"><span data-stu-id="86713-129">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="86713-130">En la ficha desplegable **Versiones**, seleccione **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="86713-130">On the **Versions** FastTab, select **Run**.</span></span>
5. <span data-ttu-id="86713-131">En el campo **Introducir id.**, introduzca **1**.</span><span class="sxs-lookup"><span data-stu-id="86713-131">In the **Enter Id** field, enter **1**.</span></span>
6. <span data-ttu-id="86713-132">Establezca la opción **Crear archivos de línea base** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="86713-132">Set the **Make baseline files** option to **Yes**.</span></span>
7. <span data-ttu-id="86713-133">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="86713-133">Select **OK**.</span></span>

    <span data-ttu-id="86713-134">![Cuadro de diálogo de parámetros de informes electrónicos](media/GER-BaselineSample-FormatRunToMakeBaselineFile3.PNG "Captura de pantalla del cuadro de diálogo de parámetros de informes electrónicos")</span><span class="sxs-lookup"><span data-stu-id="86713-134">![Electronic report parameters dialog box](media/GER-BaselineSample-FormatRunToMakeBaselineFile3.PNG "Screenshot of the Electronic report parameters dialog box")</span></span>

8. <span data-ttu-id="86713-135">Seleccione **Líneas base**.</span><span class="sxs-lookup"><span data-stu-id="86713-135">Select **Baselines**.</span></span>

    <span data-ttu-id="86713-136">![Páginas de líneas base del formato de informes electrónicos](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Captura de pantalla de la página de líneas base del formato de informes electrónicos")</span><span class="sxs-lookup"><span data-stu-id="86713-136">![Electronic reporting format baselines page](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

    <span data-ttu-id="86713-137">El archivo de salida generado se ha adjuntado automáticamente a la línea base del formato de ER ejecutado.</span><span class="sxs-lookup"><span data-stu-id="86713-137">The generated outbound file has been automatically attached to the baseline of the executed ER format.</span></span> <span data-ttu-id="86713-138">La regla de línea base se ha agregado automáticamente a esta línea base y también contiene la referencia al archivo adjunto.</span><span class="sxs-lookup"><span data-stu-id="86713-138">The baseline rule has been automatically added to this baseline and also contains the reference to the attached file.</span></span>

9. <span data-ttu-id="86713-139">En el campo **Nombre**, especifique **Línea base 1**.</span><span class="sxs-lookup"><span data-stu-id="86713-139">In the **Name** field, enter **Baseline 1**.</span></span>
10. <span data-ttu-id="86713-140">En el campo **Máscara de nombre de archivo**, introduzca **.xml**.</span><span class="sxs-lookup"><span data-stu-id="86713-140">In the **File name mask** field, enter **.xml**.</span></span>
11. <span data-ttu-id="86713-141">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="86713-141">Select **Save**.</span></span>

### <a name="run-the-format"></a><span data-ttu-id="86713-142">Ejecutar el formato</span><span class="sxs-lookup"><span data-stu-id="86713-142">Run the format</span></span>

<span data-ttu-id="86713-143">Ya está listo para completar el resto de pasos del ejemplo del tema [Realizar un seguimiento de los resultados de informe generados y compararlos con valores de línea base](er-trace-reports-compare-baseline.md), empezando por la sección "Ejecutar el formato de ER diseñado y revisar el registro para analizar los resultados".</span><span class="sxs-lookup"><span data-stu-id="86713-143">You're now ready to complete the remaining steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic, starting from the "Run the designed ER format and review the log to analyze the results" section.</span></span>

> [!NOTE]
> <span data-ttu-id="86713-144">Cuando elimine la regla de línea base agregada automáticamente en la ficha desplegable **Líneas base**, los archivos adjuntos a los que se hace referencia no se eliminan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="86713-144">When you delete the automatically added baseline rule on the **Baselines** FastTab, the referenced attachment isn't automatically deleted.</span></span>

## <a name="configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a><span data-ttu-id="86713-145">Configurar la línea base de modo que ignore constantemente las partes que cambian de la salida de ER</span><span class="sxs-lookup"><span data-stu-id="86713-145">Configure the baseline so that it ignores constantly changing parts of the ER output</span></span>

<span data-ttu-id="86713-146">Cuando un formato de ER se haya diseñado para contener información que se cambia cuando se ejecuta el formato, el formato debe requerir el uso de la característica de la línea base de ER para comparar los resultados generados con valores de línea base.</span><span class="sxs-lookup"><span data-stu-id="86713-146">When an ER format has been designed to contain information that is changed when the format is run, the format must be required to use the ER baseline feature to compare the generated results with baseline values.</span></span> <span data-ttu-id="86713-147">Por ejemplo, puede que la información sea la fecha y la hora de procesamiento o el identificador único de un documento generado en distintos formatos (identificador único global \[GUID\], etc.).</span><span class="sxs-lookup"><span data-stu-id="86713-147">For example, the information might be the processing date and time or the unique identifier of a generated document in different formats (globally unique identifier \[GUID\], and so on).</span></span> <span data-ttu-id="86713-148">Las nuevas funcionalidades de ER le permiten configurar la regla de línea base de modo que ignore los elementos que pueden cambiarse de un formato de ER cuando el formato se ejecute con el propósito de comparar valores de línea base con los resultados de la ejecución del formato.</span><span class="sxs-lookup"><span data-stu-id="86713-148">The new ER capabilities let you configure the baseline rule so that it ignores changeable elements of an ER format when the format is run with the purpose of comparing baseline values with the results of the format's execution.</span></span> <span data-ttu-id="86713-149">Para obtener más información acerca de esta característica, complete el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="86713-149">To learn more about this feature, complete the following example.</span></span>

## <a name="example-configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a><span data-ttu-id="86713-150">Ejemplo: Configurar la línea base de modo que ignore constantemente las partes que cambian de la salida de ER</span><span class="sxs-lookup"><span data-stu-id="86713-150">Example: Configure the baseline so that it ignores constantly changing parts of the ER output</span></span>

<span data-ttu-id="86713-151">Para completar los pasos de este ejemplo, primero debe completar los pasos del ejemplo en el tema [Realizar un seguimiento de los resultados de informe generados y compararlos con valores de línea base](er-trace-reports-compare-baseline.md).</span><span class="sxs-lookup"><span data-stu-id="86713-151">To complete the steps in this example, you must first complete the steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic.</span></span>

### <a name="modify-a-configured-er-format"></a><span data-ttu-id="86713-152">Modificar un formato de ER configurado</span><span class="sxs-lookup"><span data-stu-id="86713-152">Modify a configured ER format</span></span>

1. <span data-ttu-id="86713-153">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="86713-153">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="86713-154">En el árbol, expanda **Modelo para aprender líneas base de ER**.</span><span class="sxs-lookup"><span data-stu-id="86713-154">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="86713-155">En el árbol, seleccione **Modelo para aprender líneas base de ER\\Formato para aprender líneas base de ER**.</span><span class="sxs-lookup"><span data-stu-id="86713-155">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="86713-156">Seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="86713-156">Select **Designer**.</span></span>
5. <span data-ttu-id="86713-157">En el árbol, seleccione **Salida\\Documento**.</span><span class="sxs-lookup"><span data-stu-id="86713-157">In the tree, select **Output\\Document**.</span></span>
6. <span data-ttu-id="86713-158">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="86713-158">Select **Add**.</span></span>
7. <span data-ttu-id="86713-159">En el cuadro de diálogo desplegable, en el árbol, seleccione **XML\\Atributo**.</span><span class="sxs-lookup"><span data-stu-id="86713-159">In the drop-down dialog box, in the tree, select **XML\\Attribute**.</span></span>
8. <span data-ttu-id="86713-160">En el campo **Nombre**, introduzca **ProcessingDateTime**.</span><span class="sxs-lookup"><span data-stu-id="86713-160">In the **Name** field, enter **ProcessingDateTime**.</span></span>
9. <span data-ttu-id="86713-161">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="86713-161">Select **OK**.</span></span>
10. <span data-ttu-id="86713-162">En la pestaña **Asignación**, en el árbol, seleccione **Salida\\Documento\\ProcessingDateTime**.</span><span class="sxs-lookup"><span data-stu-id="86713-162">On the **Mapping** tab, in the tree, select **Output\\Document\\ProcessingDateTime**.</span></span>
11. <span data-ttu-id="86713-163">Seleccione **Editar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="86713-163">Select **Edit formula**.</span></span>
12. <span data-ttu-id="86713-164">En el campo **Fórmula**, introduzca la expresión siguiente: **DATETIMEFORMAT(NOW(), "O")**</span><span class="sxs-lookup"><span data-stu-id="86713-164">In the **Formula** field, enter the following expression: **DATETIMEFORMAT(NOW(), "O")**</span></span>
13. <span data-ttu-id="86713-165">Seleccione **Guardar** y, a continuación, seleccione **Prueba**.</span><span class="sxs-lookup"><span data-stu-id="86713-165">Select **Save**, and then select **Test**.</span></span>
14. <span data-ttu-id="86713-166">Seleccione **Prueba** de nuevo para volver a probar la expresión configurada.</span><span class="sxs-lookup"><span data-stu-id="86713-166">Select **Test** again to retest the configured expression.</span></span>

    <span data-ttu-id="86713-167">![Página del diseñador de fórmula](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Captura de pantalla de la página del diseñador de fórmula")</span><span class="sxs-lookup"><span data-stu-id="86713-167">![Formula designer page](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Screenshot of the Formula designer page")</span></span>

    > [!NOTE]
    > <span data-ttu-id="86713-168">La pestaña **Resultado de prueba** muestra que la expresión configurada devuelve un valor de fecha y hora diferente cada vez que se invoca.</span><span class="sxs-lookup"><span data-stu-id="86713-168">The **Test result** tab shows that the configured expression returns a different date and time value whenever it's called.</span></span>

15. <span data-ttu-id="86713-169">Cierre la página **Diseñador de fórmula** y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="86713-169">Close the **Formula designer** page, and then select **Save**.</span></span>

    <span data-ttu-id="86713-170">![Página del diseñador de formato](media/GER-BaselineSample-FormatMappingDesign2.PNG "Captura de pantalla de la página del diseñador de formato")</span><span class="sxs-lookup"><span data-stu-id="86713-170">![Format designer page](media/GER-BaselineSample-FormatMappingDesign2.PNG "Screenshot of the Format designer page")</span></span>

16. <span data-ttu-id="86713-171">Cierre la página **Diseñador de formato**.</span><span class="sxs-lookup"><span data-stu-id="86713-171">Close the **Format designer** page.</span></span>

### <a name="remove-an-existing-baseline-rule"></a><span data-ttu-id="86713-172">Eliminar una regla de línea base existente</span><span class="sxs-lookup"><span data-stu-id="86713-172">Remove an existing baseline rule</span></span>

1. <span data-ttu-id="86713-173">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="86713-173">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="86713-174">Seleccione **Líneas base**.</span><span class="sxs-lookup"><span data-stu-id="86713-174">Select **Baselines**.</span></span>
3. <span data-ttu-id="86713-175">En la lista de líneas base, seleccione la línea base configurada para el formato **Formato para aprender líneas base de ER**.</span><span class="sxs-lookup"><span data-stu-id="86713-175">In the list of baselines, select the baseline that is configured for the **Format to learn ER baselines** format.</span></span>
4. <span data-ttu-id="86713-176">En la ficha desplegable **Líneas base**, seleccione **Eliminar** para eliminar la regla de línea base que configuró anteriormente.</span><span class="sxs-lookup"><span data-stu-id="86713-176">On the **Baselines** FastTab, select **Delete** to remove the baseline rule that you configured earlier.</span></span>

<span data-ttu-id="86713-177">![Páginas de líneas base del formato de informes electrónicos](media/GER-BaselineSample-AddBaseline3.PNG "Captura de pantalla de la página de líneas base del formato de informes electrónicos")</span><span class="sxs-lookup"><span data-stu-id="86713-177">![Electronic reporting format baselines page](media/GER-BaselineSample-AddBaseline3.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

### <a name="define-replacements-for-bindings-of-designed-er-format"></a><span data-ttu-id="86713-178">Definir sustituciones para los enlaces de formato de ER diseñado</span><span class="sxs-lookup"><span data-stu-id="86713-178">Define replacements for bindings of designed ER format</span></span>

1. <span data-ttu-id="86713-179">En la página **Configuraciones**, en la ficha desplegable **Sustituciones**, seleccione **Seleccionar componentes**.</span><span class="sxs-lookup"><span data-stu-id="86713-179">On the **Configurations** page, on the **Replacements** FastTab, select **Select components**.</span></span>
2. <span data-ttu-id="86713-180">En el árbol de componentes del formato, expanda **Salida**, expanda **Salida\\Documento** y active la casilla para **Salida\\Documento\\ProcessingDateTime**.</span><span class="sxs-lookup"><span data-stu-id="86713-180">In the format components tree, expand **Output**, expand **Output\\Document**, and then select the check box for **Output\\Document\\ProcessingDateTime**.</span></span>

    <span data-ttu-id="86713-181">![Cuadro de diálogo Seleccionar componentes](media/GER-BaselineSample-SelectComponentForBindingReplacement.PNG "Captura de pantalla del cuadro de diálogo Seleccionar componentes")</span><span class="sxs-lookup"><span data-stu-id="86713-181">![Select Components dialog box](media/GER-BaselineSample-SelectComponentForBindingReplacement.PNG "Screenshot of the Select Components dialog box")</span></span>

3. <span data-ttu-id="86713-182">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="86713-182">Select **OK**.</span></span>

<span data-ttu-id="86713-183">![Páginas de líneas base del formato de informes electrónicos](media/GER-BaselineSample-AddBaseline4.PNG "Captura de pantalla de la página de líneas base del formato de informes electrónicos")</span><span class="sxs-lookup"><span data-stu-id="86713-183">![Electronic reporting format baselines page](media/GER-BaselineSample-AddBaseline4.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

<span data-ttu-id="86713-184">Se ha agregado el componente del formato de ER seleccioando a la lista de componentes en la ficha desplegable **Sustituciones**.</span><span class="sxs-lookup"><span data-stu-id="86713-184">The selected ER format component has been added to the list of components on the **Replacements** FastTab.</span></span> <span data-ttu-id="86713-185">Cuando el formato de ER de la base se ejecuta en modo de depuración, el enlace del formato para cada componente se sustituirá por el enlace que se muestra en la columna **Enlace** .</span><span class="sxs-lookup"><span data-stu-id="86713-185">When the base ER format is run in debug mode, the format's binding for each component will be replaced by the binding that is shown in the **Binding** column.</span></span> <span data-ttu-id="86713-186">Para cambiar el enlace predeterminado para un componente que se muestra en la ficha desplegable **Sustituciones**, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="86713-186">To change the default binding for a component that is listed on the **Replacements** FastTab, select **Edit**.</span></span>

### <a name="make-a-new-baseline-rule"></a><span data-ttu-id="86713-187">Crear una nueva regla de línea base</span><span class="sxs-lookup"><span data-stu-id="86713-187">Make a new baseline rule</span></span>

<span data-ttu-id="86713-188">Siga los pasos de la sección "Ejemplo: Automatizar la configuración de reglas de línea base" descrita anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="86713-188">Follow the steps in the "Example: Automate the setting of baseline rules" section earlier in this topic.</span></span> <span data-ttu-id="86713-189">Una notificación le advierte que el archivo de salida se ha generado mediante el uso de la configuración de línea base, y que se ha producido una sustitución forzada de los enlaces de formato.</span><span class="sxs-lookup"><span data-stu-id="86713-189">A notification warns you that the outbound file has been generated by using baseline settings, and that a forced replacement of the format bindings has occurred.</span></span>

<span data-ttu-id="86713-190">![Notificación en la página Configuraciones](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Captura de pantalla de la notificación en la página Configuraciones")</span><span class="sxs-lookup"><span data-stu-id="86713-190">![Notification on the Configurations page](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Screenshot of the notification on the Configurations page")</span></span>

### <a name="suppress-warnings-about-the-replacement-of-format-bindings"></a><span data-ttu-id="86713-191">Suprimir avisos sobre la sustitución de enlaces de formato</span><span class="sxs-lookup"><span data-stu-id="86713-191">Suppress warnings about the replacement of format bindings</span></span>

<span data-ttu-id="86713-192">Al configurar determinados parámetros de ER, puede suprimir las notificaciones que advierten sobre la sustitución de enlaces de formato.</span><span class="sxs-lookup"><span data-stu-id="86713-192">By setting specific ER parameters, you can suppress notifications that warn about the replacement of format bindings.</span></span> <span data-ttu-id="86713-193">Esta supresión puede resultar útil cuando los enlaces de formato se reemplazan en un modo desatendido mediante el uso de la Regression Suite Automation Tool.</span><span class="sxs-lookup"><span data-stu-id="86713-193">This suppression can be useful when format bindings are replaced in an unattended mode by using the Regression Suite Automation Tool.</span></span> <span data-ttu-id="86713-194">En este caso, el aviso se puede considerar un error del caso de prueba que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="86713-194">In this case, the warning can be considered a failure of the test case that is running.</span></span>

1. <span data-ttu-id="86713-195">En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, seleccione **Parámetros de usuario**.</span><span class="sxs-lookup"><span data-stu-id="86713-195">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, select **User parameters**.</span></span>
2. <span data-ttu-id="86713-196">Establezca la opción **Suprimir avisos de línea base** en **Sí** y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="86713-196">Set the **Suppress baseline warnings** option to **Yes**, and then select **OK**.</span></span>

<span data-ttu-id="86713-197">![Cuadro de diálogo de parámetros de usuario](media/GER-BaselineSample-ERUserParameters1.png "Captura de pantalla del cuadro de diálogo de parámetros de usuario")</span><span class="sxs-lookup"><span data-stu-id="86713-197">![User parameters dialog box](media/GER-BaselineSample-ERUserParameters1.png "Screenshot of the User parameters dialog box")</span></span>

### <a name="review-the-generated-baseline-file"></a><span data-ttu-id="86713-198">Revisar el archivo de línea base generado</span><span class="sxs-lookup"><span data-stu-id="86713-198">Review the generated baseline file</span></span>

1. <span data-ttu-id="86713-199">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="86713-199">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="86713-200">Seleccione **Líneas base**.</span><span class="sxs-lookup"><span data-stu-id="86713-200">Select **Baselines**.</span></span>
3. <span data-ttu-id="86713-201">Seleccione **Archivos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="86713-201">Select **Attachments**.</span></span>

    <span data-ttu-id="86713-202">![Páginas Archivos adjuntos](media/GER-BaselineSample-AttachedBaselineFile.PNG "Captura de pantalla de la página Archivos adjuntos")</span><span class="sxs-lookup"><span data-stu-id="86713-202">![Attachments page](media/GER-BaselineSample-AttachedBaselineFile.PNG "Screenshot of the Attachments page")</span></span>

    > [!NOTE]
    > <span data-ttu-id="86713-203">El archivo generado contiene texto de fecha y hora de procesamiento (**"#"**) del enlace que se configuró en la regla de línea base agregada, no del enlace del formato.</span><span class="sxs-lookup"><span data-stu-id="86713-203">The generated file contains the processing date and time text (**"#"**) from the binding that was configured in the added baseline rule, not from the format's binding.</span></span>

4. <span data-ttu-id="86713-204">Cierre la página **Archivos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="86713-204">Close the **Attachments** page.</span></span>

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a><span data-ttu-id="86713-205">Ejecutar el formato de ER diseñado y revisar el registro para analizar los resultados</span><span class="sxs-lookup"><span data-stu-id="86713-205">Run the designed ER format and review the log to analyze the results</span></span>

1. <span data-ttu-id="86713-206">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="86713-206">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="86713-207">En el árbol, expanda **Modelo para aprender líneas base de ER**.</span><span class="sxs-lookup"><span data-stu-id="86713-207">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="86713-208">En el árbol, seleccione **Modelo para aprender líneas base de ER\\Formato para aprender líneas base de ER**.</span><span class="sxs-lookup"><span data-stu-id="86713-208">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="86713-209">En la ficha desplegable **Versiones**, seleccione **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="86713-209">On the **Versions** FastTab select **Run**.</span></span>
5. <span data-ttu-id="86713-210">En el campo **Introducir id.**, escriba **1**.</span><span class="sxs-lookup"><span data-stu-id="86713-210">In the **Enter Id** field, type **1**.</span></span>
6. <span data-ttu-id="86713-211">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="86713-211">Select **OK**.</span></span>
7. <span data-ttu-id="86713-212">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configurar registros de depuración**.</span><span class="sxs-lookup"><span data-stu-id="86713-212">Go to **Organization administration** \> **Electronic reporting** \> **Configuration debug logs**.</span></span>

<span data-ttu-id="86713-213">El registro de ejecución contiene información sobre los resultados de la comparación del archivo generado con la línea base configurada.</span><span class="sxs-lookup"><span data-stu-id="86713-213">The execution log contains information about the results of the comparison of the generated file with the configured baseline.</span></span> <span data-ttu-id="86713-214">El registro indica que el archivo generado y la línea base son iguales, aunque el formato ejecutado contiene el enlace para introducir un valor de fecha y hora que cambia constantemente en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="86713-214">The log indicates that the generated file and the baseline are equal, even though the executed format contains the binding to enter a constantly changing date and time value in the outbound file.</span></span>

> [!NOTE]
> <span data-ttu-id="86713-215">Aunque el archivo de salida se haya generado mediante el uso de la configuración de línea base que fuerza la sustitución de los enlaces del formato, no recibe ningún aviso sobre la sustitución.</span><span class="sxs-lookup"><span data-stu-id="86713-215">Although the outbound file has been generated by using baseline settings that force the replacement of the format's bindings, you don't receive any warnings about the replacement.</span></span>

## <a name="exchange-baseline-settings-between-environments"></a><span data-ttu-id="86713-216">Intercambiar configuración de línea base entre entornos</span><span class="sxs-lookup"><span data-stu-id="86713-216">Exchange baseline settings between environments</span></span>

### <a name="export-baseline-settings"></a><span data-ttu-id="86713-217">Exportar configuración de línea base</span><span class="sxs-lookup"><span data-stu-id="86713-217">Export baseline settings</span></span>

<span data-ttu-id="86713-218">Las nuevas funcionalidades de ER le permiten exportar la configuración de línea base para el formato de ER seleccionado desde el entorno actual y almacenarla como archivos XML.</span><span class="sxs-lookup"><span data-stu-id="86713-218">The new ER capabilities let you export baseline settings for the selected ER format from the current environment and store them as XML files.</span></span> 

<span data-ttu-id="86713-219">Para exportar la configuración de línea base, en la página **Líneas base del formato de informes electrónicos**, seleccione **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="86713-219">To export baseline settings, on the **Electronic reporting format baselines** page, select **Export**.</span></span>

### <a name="import-baseline-settings"></a><span data-ttu-id="86713-220">Importar configuración de línea base</span><span class="sxs-lookup"><span data-stu-id="86713-220">Import baseline settings</span></span>

<span data-ttu-id="86713-221">La configuración de línea base exportada se puede importar en un entorno diferente.</span><span class="sxs-lookup"><span data-stu-id="86713-221">Exported baseline settings can be imported into a different environment.</span></span> <span data-ttu-id="86713-222">El entorno se debe importar primero como formato de ER.</span><span class="sxs-lookup"><span data-stu-id="86713-222">The environment must first be imported as an ER format.</span></span> <span data-ttu-id="86713-223">Posteriormente, puede importar la configuración de línea base.</span><span class="sxs-lookup"><span data-stu-id="86713-223">You can then import the baseline settings.</span></span>

<span data-ttu-id="86713-224">Para importar la configuración de línea base desde un archivo XML almacenado localmente, en la página **Líneas base del formato de informes electrónicos**, seleccione **Importar** y seleccione **Examinar** para seleccionar el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="86713-224">To import baseline settings from a locally stored XML file, on the **Electronic reporting format baselines** page, select **Import**, and then select **Browse** to select the XML file.</span></span>

<span data-ttu-id="86713-225">![Cuadro de diálogo Importar configuración de línea base](media/GER-BaselineSample-ImportBaseline1.PNG "Captura de pantalla del cuadro de diálogo Importar configuración de línea base")</span><span class="sxs-lookup"><span data-stu-id="86713-225">![Import baseline settings dialog box](media/GER-BaselineSample-ImportBaseline1.PNG "Screenshot of the Import baseline settings dialog box")</span></span>

<span data-ttu-id="86713-226">Para importar la configuración de línea base de un archivo XML almacenado en Microsoft SharePoint Server, según la configuración actual Administración de documentos y el tipo de documento seleccionado, en la página **Líneas base del formato de informes electrónicos**, seleccione **Importar desde origen**.</span><span class="sxs-lookup"><span data-stu-id="86713-226">To import baseline settings from an XML file that is stored on the Microsoft SharePoint Server, based on the current Document management settings and the selected document type, on the **Electronic reporting format baselines** page, select **Import from source**.</span></span> <span data-ttu-id="86713-227">A continuación, seleccione el tipo de documento y el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="86713-227">Then select the document type and the XML file.</span></span> <span data-ttu-id="86713-228">El tipo de documento requerido para acceder a la carpeta de SharePoint deben configurarse con antelación.</span><span class="sxs-lookup"><span data-stu-id="86713-228">The required document type to access the SharePoint folder must be configured in advance.</span></span>

<span data-ttu-id="86713-229">![Cuadro de diálogo Importar desde origen](media/GER-BaselineSample-ImportBaseline2.PNG "Captura de pantalla del cuadro de diálogo Importar desde origen")</span><span class="sxs-lookup"><span data-stu-id="86713-229">![Import from source dialog box](media/GER-BaselineSample-ImportBaseline2.PNG "Screenshot of the Import from source dialog box")</span></span>

> [!NOTE]
> <span data-ttu-id="86713-230">Puede utilizar el Grabador de tareas para registrar los pasos a fin de seleccionar el tipo de documentos requerido y el nombre de archivo en el cuadro de diálogo **Importar desde origen**.</span><span class="sxs-lookup"><span data-stu-id="86713-230">You can use Task recorder to record the steps for selecting the required document type and the file name in the **Import from source** dialog box.</span></span> <span data-ttu-id="86713-231">De esta manera, puede conservar la configuración de línea base requerida en SharePoint Server e importarla automáticamente mediante la reproducción de una grabación de tareas cuando ejecute pruebas automatizadas usando la Regression Suite Automation Tool.</span><span class="sxs-lookup"><span data-stu-id="86713-231">In this way, you can keep required baseline settings on SharePoint Server and then automatically import them by playing a task recording when you run automated tests by using the Regression Suite Automation Tool.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="86713-232">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="86713-232">Additional resources</span></span>

- [<span data-ttu-id="86713-233">Realizar un seguimiento de los resultados de informe generados y compararlos con valores de línea base</span><span class="sxs-lookup"><span data-stu-id="86713-233">Trace generated report results and compare them with baseline values</span></span>](er-trace-reports-compare-baseline.md)
- [<span data-ttu-id="86713-234">Grabador de tareas</span><span class="sxs-lookup"><span data-stu-id="86713-234">Task recorder</span></span>](../user-interface/task-recorder.md)
