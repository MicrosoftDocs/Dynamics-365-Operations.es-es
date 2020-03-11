---
title: Usar el tutorial de Regression Suite Automation Tool
description: En este tema se muestra cómo usar la Regression Suite Automation Tool (RSAT). Describe varias características y proporciona ejemplos que emplean secuencias de comandos avanzados.
author: kfend
manager: AnnBe
ms.date: 06/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 21761
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 6cdaa89fb6d50ebaaaefe7f92d7224a1567d17d1
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070829"
---
# <a name="use-the-regression-suite-automation-tool-tutorial"></a><span data-ttu-id="5cde9-104">Utilizar el tutorial Regression Suite Automation Tool</span><span class="sxs-lookup"><span data-stu-id="5cde9-104">Use the Regression suite automation tool tutorial</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="5cde9-105">Utilice las herramientas del navegador de Internet para descargar y guardar esta página en formato pdf.</span><span class="sxs-lookup"><span data-stu-id="5cde9-105">Use your internet browser tools to download and save this page in pdf format.</span></span> 

<span data-ttu-id="5cde9-106">Este tutorial le muestra algunas de las características avanzadas de la Regression Suite Automation Tool (RSAT), incluye una asignación de demostración y describe la estrategia y los puntos de aprendizaje clave.</span><span class="sxs-lookup"><span data-stu-id="5cde9-106">This tutorial walks through some of the advanced features of the Regression suite automation tool (RSAT), includes a demo assignment, and describes strategy and key learning points.</span></span>

## <a name="features-of-rsattask-recorder"></a><span data-ttu-id="5cde9-107">Características de RSAT/Grabador de tareas</span><span class="sxs-lookup"><span data-stu-id="5cde9-107">Features of RSAT/Task recorder</span></span>

### <a name="validate-a-field-value"></a><span data-ttu-id="5cde9-108">Validar un valor del campo</span><span class="sxs-lookup"><span data-stu-id="5cde9-108">Validate a field value</span></span>

<span data-ttu-id="5cde9-109">Para obtener más información sobre esta característica, consulte [Crear una nueva grabación de tareas que tenga una función Validar](./hol-set-up-regression-suite-automation-tool.md#create-a-new-task-recording-that-has-a-validate-function).</span><span class="sxs-lookup"><span data-stu-id="5cde9-109">For information about this feature, see the [Create a new task recording that has a Validate function](./hol-set-up-regression-suite-automation-tool.md#create-a-new-task-recording-that-has-a-validate-function).</span></span>

### <a name="saved-variable"></a><span data-ttu-id="5cde9-110">Variable guardada</span><span class="sxs-lookup"><span data-stu-id="5cde9-110">Saved variable</span></span>

<span data-ttu-id="5cde9-111">Para obtener más información sobre esta característica, consulte [Modificar una grabación de tareas existente para crear una variable guardada](./hol-set-up-regression-suite-automation-tool.md#modify-an-existing-task-recording-to-create-a-saved-variable).</span><span class="sxs-lookup"><span data-stu-id="5cde9-111">For information about this feature, see the [Modify an existing task recording to create a saved variable](./hol-set-up-regression-suite-automation-tool.md#modify-an-existing-task-recording-to-create-a-saved-variable).</span></span>

### <a name="derived-test-case"></a><span data-ttu-id="5cde9-112">Caso de prueba derivado</span><span class="sxs-lookup"><span data-stu-id="5cde9-112">Derived test case</span></span>

1. <span data-ttu-id="5cde9-113">Abra la Regression Suite Automation Tool (RSAT) y seleccione los casos de prueba que creó en [Configurar e instalar el titular de Regression Suite Automation Tool](./hol-set-up-regression-suite-automation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="5cde9-113">Open Regression suite automation tool (RSAT), and select both the test cases that you created in [Set up and install Regression suite automation tool tutorial](./hol-set-up-regression-suite-automation-tool.md).</span></span>
2. <span data-ttu-id="5cde9-114">Seleccione **Nuevo \> Crear caso de prueba derivado**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-114">Select **New \> Create derived test case**.</span></span>

    ![Comando Crear caso de prueba derivado en el menú Nuevo](./media/use_rsa_tool_01.png)

3. <span data-ttu-id="5cde9-116">Recibe un mensaje que indica que se creará un caso de prueba derivado para cada caso de prueba seleccionado en el conjunto de pruebas actual, y que cada caso de prueba derivado tendrá su propia copia del archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="5cde9-116">You receive a message that states that a derived test case will be created for each selected test case in the current test suite, and that each derived test case will have its own copy of the Excel parameter file.</span></span> <span data-ttu-id="5cde9-117">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-117">Select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5cde9-118">Cuando ejecute un caso de prueba derivado, se utiliza el grabador de tareas de su caso de prueba principal y su propia copia del archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="5cde9-118">When you run a derived test case, it uses the task recording of its parent test case and its own copy of the Excel parameter file.</span></span> <span data-ttu-id="5cde9-119">De esta manera, puede ejecutar la misma prueba con distintos parámetros, sin tener que mantener más de un grabador de tareas.</span><span class="sxs-lookup"><span data-stu-id="5cde9-119">In this way, you can run the same test with different parameters, without having to maintain more than one task recording.</span></span> <span data-ttu-id="5cde9-120">Un caso de prueba derivado no tiene que formar parte del mismo conjunto de pruebas que su caso de prueba principal.</span><span class="sxs-lookup"><span data-stu-id="5cde9-120">A derived test case doesn't have to be part of the same test suite as its parent test case.</span></span>

    ![Cuadro de mensaje](./media/use_rsa_tool_02.png)

    <span data-ttu-id="5cde9-122">Se crean dos casos de prueba derivados adicionales, y la casilla **¿Derivado?** se selecciona para ellos.</span><span class="sxs-lookup"><span data-stu-id="5cde9-122">Two additional derived test cases are created, and the **Derived?** check box is selected for them.</span></span>

    ![Casos de prueba derivados creados](./media/use_rsa_tool_03.png)

    <span data-ttu-id="5cde9-124">Se crea automáticamente un caso de prueba derivado en Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="5cde9-124">A derived test case is automatically created in Azure DevOps.</span></span> <span data-ttu-id="5cde9-125">Es un artículo secundario del caso de prueba **Crear un nuevo producto** y se etiqueta con una palabra clave especial: **RSAT:DerivedTestSteps**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-125">It's a child item of the **Create a new product** test case and is tagged with a special keyword: **RSAT:DerivedTestSteps**.</span></span> <span data-ttu-id="5cde9-126">Estos casos de prueba también se agregan automáticamente al plan de prueba en Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="5cde9-126">These test cases are also automatically added to the test plan in Azure DevOps.</span></span>

    ![Palabra clave RSAT:DerivedTestSteps](./media/use_rsa_tool_04.png)

    > [!NOTE]
    > <span data-ttu-id="5cde9-128">Si, por algún motivo, los casos de prueba derivados que se crean no lo hacen en el orden correcto, vaya a Azure DevOps y reordene los casos de prueba en el conjunto de pruebas, de modo que la RSAT pueda ejecutarlos en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="5cde9-128">If, for any reason, the derived test cases that are created aren't in the correct order, go to Azure DevOps, and reorder the test cases in the test suite, so that RSAT can run them in the correct order.</span></span>

4. <span data-ttu-id="5cde9-129">Seleccione los casos de prueba derivados y, a continuación. seleccione **Editar** para abrir los archivos de parámetros de Excel correspondientes.</span><span class="sxs-lookup"><span data-stu-id="5cde9-129">Select the derived test cases, and then select **Edit** to open the corresponding Excel parameter files.</span></span>
5. <span data-ttu-id="5cde9-130">Edite estos archivos de parámetros de Excel del mismo modo que editó los archivos principales.</span><span class="sxs-lookup"><span data-stu-id="5cde9-130">Edit these Excel parameter files in the same way that you edited the parent files.</span></span> <span data-ttu-id="5cde9-131">Es decir, asegúrese de que el id. de producto esté establecido para que se genere automáticamente.</span><span class="sxs-lookup"><span data-stu-id="5cde9-131">In other words, make sure that the product ID is set so that it's automatically generated.</span></span> <span data-ttu-id="5cde9-132">Asegúrese también de que la variable guardada se copie a los campos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="5cde9-132">Also make sure that the saved variable is copied to the relevant fields.</span></span>
6. <span data-ttu-id="5cde9-133">En la pestaña **General** de ambos archivos de parámetros de Excel, actualice el valor del campo **Empresa** a **USSI**, de modo que los casos de prueba derivados se ejecuten con una entidad jurídica distinta a la del caso de prueba principal.</span><span class="sxs-lookup"><span data-stu-id="5cde9-133">On the **General** tab of both Excel parameter files, update the value of the **Company** field to **USSI**, so that the derived test cases will be run against a different legal entity than the parent test case.</span></span> <span data-ttu-id="5cde9-134">Para ejecutar los casos de prueba con un usuario específico (o el rol asociado a un usuario específico), puede actualizar el valor del campo **Usuario de la prueba**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-134">To run the test cases against a specific user (or the role that is associated with a specific user), you can update the value of the **Test User** field.</span></span>
7. <span data-ttu-id="5cde9-135">Seleccione **Ejecutar** y valide que el producto se crea tanto en la entidad jurídica de USMF y como en la entidad jurídica de USSI.</span><span class="sxs-lookup"><span data-stu-id="5cde9-135">Select **Run**, and validate that the product is created in both the USMF legal entity and the USSI legal entity.</span></span>

### <a name="validate-notifications"></a><span data-ttu-id="5cde9-136">Validar notificaciones</span><span class="sxs-lookup"><span data-stu-id="5cde9-136">Validate notifications</span></span>

<span data-ttu-id="5cde9-137">Esta característica se puede utilizar para validar si se produjo una acción.</span><span class="sxs-lookup"><span data-stu-id="5cde9-137">This feature can be used to validate whether an action occurred.</span></span> <span data-ttu-id="5cde9-138">Por ejemplo, cuando se crea, estima y inicia una orden de producción, la aplicación muestra un mensaje "Producción – Inicio" para notificarle que se ha iniciado el pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="5cde9-138">For example, when a production order is created, estimated, and then started, the app shows a "Production – Start" message to notify you that the production order has been started.</span></span>

![Notificación Producción – Inicio](./media/use_rsa_tool_05.png)

<span data-ttu-id="5cde9-140">Puede validar este mensaje a través RSAT introduciendo el texto del mensaje en la pestaña **MessageValidation** del archivo de parámetros de Excel para la grabación adecuada.</span><span class="sxs-lookup"><span data-stu-id="5cde9-140">You can validate this message through RSAT by entering the message text on the **MessageValidation** tab of the Excel parameter file for the appropriate recording.</span></span>

![Pestaña Validación de mensaje](./media/use_rsa_tool_06.png)

<span data-ttu-id="5cde9-142">Una vez que se ejecute el caso de prueba, el mensaje del archivo de parámetros de Excel se compara con el mensaje que se muestra.</span><span class="sxs-lookup"><span data-stu-id="5cde9-142">After the test case is run, the message in the Excel parameter file is compared to the message that is shown.</span></span> <span data-ttu-id="5cde9-143">Si los mensajes no coinciden, el caso de prueba fallará.</span><span class="sxs-lookup"><span data-stu-id="5cde9-143">If the messages don't match, the test case will fail.</span></span>

> [!NOTE]
> <span data-ttu-id="5cde9-144">Puede introducir más de un mensaje en la pestaña **MessageValidation** en el archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="5cde9-144">You can enter more than one message on the **MessageValidation** tab in the Excel parameter file.</span></span> <span data-ttu-id="5cde9-145">Los mensajes también pueden ser de error o de advertencia en lugar de mensajes informativos.</span><span class="sxs-lookup"><span data-stu-id="5cde9-145">The messages also can be error or warning messages instead of informational messages.</span></span>

### <a name="validate-values-by-using-operators"></a><span data-ttu-id="5cde9-146">Validar valores mediante el uso de operadores</span><span class="sxs-lookup"><span data-stu-id="5cde9-146">Validate values by using operators</span></span>

<span data-ttu-id="5cde9-147">En versiones anteriores de RSAT, podía validar valores solo si un valor de control era igual a un valor esperado.</span><span class="sxs-lookup"><span data-stu-id="5cde9-147">In previous versions of RSAT, you could validate values only if a control value equaled an expected value.</span></span> <span data-ttu-id="5cde9-148">La nueva característica le permite validar que una variable no es igual a, menor que o mayor que un valor especificado.</span><span class="sxs-lookup"><span data-stu-id="5cde9-148">The new feature lets you validate that a variable isn't equal to, is less than, or is more than a specified value.</span></span>

- <span data-ttu-id="5cde9-149">Para utilizar esta característica, abra el archivo **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** en la carpeta de instalación de RSAT (por ejemplo, **C:\\Archivos de programa (x86)\\Regression Suite Automation Tool**) y cambie el valor en el siguiente elemento de **falso** a **verdadero**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-149">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value in the following element from **false** to **true**.</span></span>

    ```xml
    <add key="AddOperatorFieldsToExcelValidation" value="false" />
    ```

    <span data-ttu-id="5cde9-150">En el archivo de parámetros de Excel, aparece un nuevo campo **Operador**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-150">In the Excel parameter file, a new **Operator** field appears.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5cde9-151">Si ha estado utilizando una versión anterior de RSAT, debe generar los nuevos archivos de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="5cde9-151">If you've been using an older version of RSAT, you must generate new Excel parameter files.</span></span>

    ![Campo Operador](./media/use_rsa_tool_07.png)

<span data-ttu-id="5cde9-153">El siguiente ejemplo muestra cómo puede utilizar esta característica para validar si el inventario disponible es superior a 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="5cde9-153">The following example shows how you can use this feature to validate whether the on-hand inventory is more than 0 (zero).</span></span>

1. <span data-ttu-id="5cde9-154">En los datos de demostración en la empresa **USMF**, cree una grabación de tareas que tenga los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="5cde9-154">In the demo data in the **USMF** company, create a task recording that has the following steps:</span></span>

    1. <span data-ttu-id="5cde9-155">Vaya a **Gestión de información de productos \> Productos \> Productos emitidos**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-155">Go to **Product information management \> Products \> Released products**.</span></span>
    2. <span data-ttu-id="5cde9-156">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="5cde9-156">Use the Quick Filter to find records.</span></span> <span data-ttu-id="5cde9-157">Por ejemplo, aplique un filtro de un valor de **1000** para el campo **Número de artículo**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-157">For example, filter on a value of **1000** for the **Item number** field.</span></span>
    3. <span data-ttu-id="5cde9-158">Seleccione **Inventario disponible**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-158">Select **On-hand inventory**.</span></span>
    4. <span data-ttu-id="5cde9-159">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="5cde9-159">Use the Quick Filter to find records.</span></span> <span data-ttu-id="5cde9-160">Por ejemplo, aplique un filtro de un valor de **1** para el campo **Sitio**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-160">For example, filter on a value of **1** for the **Site** field.</span></span>
    5. <span data-ttu-id="5cde9-161">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="5cde9-161">In the list, mark the selected row.</span></span>
    6. <span data-ttu-id="5cde9-162">Valide que el valor del campo **Total disponible** es **411,0000000000000000**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-162">Validate that the value of the **Total available** field is **411.0000000000000000**.</span></span>

2. <span data-ttu-id="5cde9-163">Guarde la grabación de tareas en la biblioteca de BPM en LCS y sincronícela en Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="5cde9-163">Save the task recording to the BPM library in LCS, and sync it to Azure DevOps.</span></span>
3. <span data-ttu-id="5cde9-164">Agregue el caso de prueba al plan de pruebas, y cargue el caso de prueba en RSAT.</span><span class="sxs-lookup"><span data-stu-id="5cde9-164">Add the test case to the test plan, and load the test case into RSAT.</span></span>
4. <span data-ttu-id="5cde9-165">Abra el archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="5cde9-165">Open the Excel parameter file.</span></span> <span data-ttu-id="5cde9-166">En la pestaña **InventOnhandItem**, verá una sección **Validar InventOnhandItem** que incluye un campo **Operador**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-166">On the **InventOnhandItem** tab, you will see a **Validate InventOnhandItem** section that includes an **Operator** field.</span></span>

    ![Campo Operador](./media/use_rsa_tool_08.png)

5. <span data-ttu-id="5cde9-168">Para validar que el inventario disponible será siempre superior a 0, cambie el valor del campo **Valor** de **411** a **0** y el valor del campo **Operador** de un signo igual (**=**) a un signo mayor que (**\>**).</span><span class="sxs-lookup"><span data-stu-id="5cde9-168">To validate whether the inventory on-hand will always be more than 0, change the value of the **Value** field from **411** to **0** and the value of the **Operator** field from an equal sign (**=**) to a greater than sign (**\>**).</span></span>

    ![Valores cambiados de los campos Valor y y Operador](./media/use_rsa_tool_09.png)

6. <span data-ttu-id="5cde9-170">Guarde y cierre el archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="5cde9-170">Save and close the Excel parameter file.</span></span>
7. <span data-ttu-id="5cde9-171">Seleccione **Cargar** para guardar los cambios realizados en el archivo de parámetros de Excel en Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="5cde9-171">Select **Upload** to save the changes that you made to the Excel parameter file to Azure DevOps.</span></span>

<span data-ttu-id="5cde9-172">Ahora, si es el valor del campo **Total disponible** para el artículo especificado en el inventario es superior a 0 (cero), las pruebas se aprobarán, independientemente del valor real del inventario disponible.</span><span class="sxs-lookup"><span data-stu-id="5cde9-172">Now, if the value of the **Total Available** field for the specified item in inventory is more than 0 (zero), tests will pass, regardless of the actual on-hand inventory value.</span></span>

### <a name="generator-logs"></a><span data-ttu-id="5cde9-173">Registros del generador</span><span class="sxs-lookup"><span data-stu-id="5cde9-173">Generator logs</span></span>

<span data-ttu-id="5cde9-174">Esta característica crea una carpeta que contiene los registros de los casos de prueba que se han ejecutado.</span><span class="sxs-lookup"><span data-stu-id="5cde9-174">This feature creates a folder that contains the logs of the test cases that have been run.</span></span>

- <span data-ttu-id="5cde9-175">Para utilizar esta característica, abra el archivo **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** en la carpeta de instalación de RSAT (por ejemplo, **C:\\Archivos de programa (x86)\\Regression Suite Automation Tool**) y cambie el valor en el siguiente elemento de **falso** a **verdadero**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-175">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value in the following element from **false** to **true**.</span></span>

    ```xml
    <add key="LogGeneration" value="false" />
    ```

<span data-ttu-id="5cde9-176">Una vez que se ejecuten los casos de prueba, puede encontrar los archivos de registro en **C:\\Usuarios\\\<Nombre de usuario\>\\AppData\\Roaming\\RegressionTool\\generatorLogs**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-176">After the test cases are run, you can find the log files under **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\generatorLogs**.</span></span>

![Carpeta GeneratorLogs](./media/use_rsa_tool_10.png)

> [!NOTE]
> <span data-ttu-id="5cde9-178">Si había casos de prueba existentes antes de cambiar el valor del archivo .config, los registros no se generarán para aquellos casos de prueba hasta que genere nuevos archivos de ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="5cde9-178">If there were existing test cases before you changed the value in the .config file, logs won't be generated for those test cases until you generate new test execution files.</span></span>
> 
> ![Comando Generar solo archivos Ejecución de texto en el menú Nuevo](./media/use_rsa_tool_11.png)

### <a name="snapshot"></a><span data-ttu-id="5cde9-180">Captura de pantalla</span><span class="sxs-lookup"><span data-stu-id="5cde9-180">Snapshot</span></span>

<span data-ttu-id="5cde9-181">Esta característica realiza capturas de pantalla de los pasos que se realizaron durante la grabación de tareas.</span><span class="sxs-lookup"><span data-stu-id="5cde9-181">This feature takes screenshots of the steps that were performed during task recording.</span></span>

- <span data-ttu-id="5cde9-182">Para utilizar esta característica, abra el archivo **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** en la carpeta de instalación de RSAT (por ejemplo, **C:\\Archivos de programa (x86)\\Regression Suite Automation Tool**) y cambie el valor del siguiente elemento de **falso** a **verdadero**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-182">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value of the following element from **false** to **true**.</span></span>

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

<span data-ttu-id="5cde9-183">En **C:\\Usuarios\\\<Nombre de usuario\>\\AppData\\Roaming\\regressionTool\\reproducción**, se cra una carpeta independiente para cada caso de prueba que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="5cde9-183">Under **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback**, a separate folder is created for each test case that is run.</span></span>

![Carpeta Captura de pantalla para un caso de prueba](./media/use_rsa_tool_12.png)

<span data-ttu-id="5cde9-185">En cada una de estas carpetas, puede encontrar capturas de pantalla de los pasos que se realizaron mientras se ejecutaban los casos de prueba.</span><span class="sxs-lookup"><span data-stu-id="5cde9-185">In each of these folders, you can find snapshots of the steps that were performed while the test cases were run.</span></span>

![Archivos Captura de pantalla](./media/use_rsa_tool_13.png)

## <a name="assignment"></a><span data-ttu-id="5cde9-187">Asignación</span><span class="sxs-lookup"><span data-stu-id="5cde9-187">Assignment</span></span>

### <a name="scenario"></a><span data-ttu-id="5cde9-188">Situación</span><span class="sxs-lookup"><span data-stu-id="5cde9-188">Scenario</span></span>

1. <span data-ttu-id="5cde9-189">El diseñador de productos crea un nuevo producto lanzado.</span><span class="sxs-lookup"><span data-stu-id="5cde9-189">The product designer creates a new released product.</span></span>
2. <span data-ttu-id="5cde9-190">El director de producción inicia una orden de producción para llevar el nivel de existencias a dos piezas.</span><span class="sxs-lookup"><span data-stu-id="5cde9-190">The production manager initiates a production order to bring the stock level to two pieces.</span></span>
3. <span data-ttu-id="5cde9-191">La fabricación comienza y termina con el pedido de producción, y verifica que la cantidad disponible es de dos piezas.</span><span class="sxs-lookup"><span data-stu-id="5cde9-191">Manufacturing starts and ends the production order, and verifies that the on-hand quantity is two pieces.</span></span>
4. <span data-ttu-id="5cde9-192">El equipo de ventas recibe un pedido para cuatro piezas del nuevo producto.</span><span class="sxs-lookup"><span data-stu-id="5cde9-192">The sales team receives an order for four pieces of the new product.</span></span> <span data-ttu-id="5cde9-193">Por lo tanto, el equipo de ventas actualia los requisitos netos a través del plan dinámico.</span><span class="sxs-lookup"><span data-stu-id="5cde9-193">Therefore, the sales team updates the net requirements via the dynamic plan.</span></span> <span data-ttu-id="5cde9-194">Puesto que no hay capacidad adicional disponible, la directiva de pedidos predeterminada se establece en "comprar en lugar de fabricar".</span><span class="sxs-lookup"><span data-stu-id="5cde9-194">Because no additional capacity is available, the default order policy is set to "buy instead of make."</span></span> <span data-ttu-id="5cde9-195">Por lo tanto, se crea un pedido de compra planificado.</span><span class="sxs-lookup"><span data-stu-id="5cde9-195">Therefore, a planned purchase order is created.</span></span>
5. <span data-ttu-id="5cde9-196">El comprador agrega un proveedor, consolida el pedido de compra planificado y, a continuación, confirma el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="5cde9-196">The buyer adds a vendor, firms the planned purchase order, and then confirms the purchase order.</span></span>
6. <span data-ttu-id="5cde9-197">Cuando las mercancías que se adquirieron llegan el almacén, el operador de almacén busca el pedido de compra relacionado y recibe las mercancías.</span><span class="sxs-lookup"><span data-stu-id="5cde9-197">When the goods that were purchased arrive at the store, the store operator searches the related purchase order and receives the goods.</span></span> <span data-ttu-id="5cde9-198">Puesto que el pedido está ahora completado, las mercancías se pueden seleccionar y empaquetar con el pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="5cde9-198">Because the order is now completed, goods can be picked and packed against the sales order.</span></span>
7. <span data-ttu-id="5cde9-199">Finance registra la factura de compra y la factura de ventas.</span><span class="sxs-lookup"><span data-stu-id="5cde9-199">Finance posts the purchase invoice and sales invoice.</span></span>

<span data-ttu-id="5cde9-200">En la ilustración siguiente se muestra el flujo para este escenario.</span><span class="sxs-lookup"><span data-stu-id="5cde9-200">The following illustration shows the flow for this scenario.</span></span>

![Flujo para el escenario de demostración](./media/use_rsa_tool_14.png)

<span data-ttu-id="5cde9-202">En la ilustración siguiente se muestran los procesos empresariales para este escenario en RSAT.</span><span class="sxs-lookup"><span data-stu-id="5cde9-202">The following illustration shows the business processes for this scenario in RSAT.</span></span>

![Procesos empresariales para el escenario de demostración](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a><span data-ttu-id="5cde9-204">Estrategia – Aprendizaje clave</span><span class="sxs-lookup"><span data-stu-id="5cde9-204">Strategy – Key learning</span></span>

### <a name="data"></a><span data-ttu-id="5cde9-205">Datos</span><span class="sxs-lookup"><span data-stu-id="5cde9-205">Data</span></span>

- <span data-ttu-id="5cde9-206">Asegúrese de que tiene volúmenes de datos representativos (una copia de los datos de configuración de producción/dorados más los datos migrados).</span><span class="sxs-lookup"><span data-stu-id="5cde9-206">Make sure that you have representative data volumes (a copy of production/golden configuration data plus migrated data).</span></span>
- <span data-ttu-id="5cde9-207">Cuando genere nuevos datos mediante el grabador de tareas, cree nombres de pruebas que no entren en conflicto con nombres existentes (por ejemplo, utilice un prefijo como **RSATxxx**).</span><span class="sxs-lookup"><span data-stu-id="5cde9-207">When you generate new data via Task recorder, create test names that won't conflict with existing names (for example, use a prefix such as **RSATxxx**).</span></span>
- <span data-ttu-id="5cde9-208">Utilice la Restauración en un momento determinado de Azure para volver a ejecutar pruebas en entornos que no son del nivel 1.</span><span class="sxs-lookup"><span data-stu-id="5cde9-208">Use Azure Point-In-Time restore to rerun tests in non-Tier 1 environments.</span></span>
- <span data-ttu-id="5cde9-209">Aunque puede utilizar las funciones de Excel **ALEATORIO** y **AHORA** para generar una combinación única, el esfuerzo es considerablemente elevado.</span><span class="sxs-lookup"><span data-stu-id="5cde9-209">Although you can use the **RANDOM** and **NOW** Excel functions to generate a unique combination, the effort is considerably high.</span></span> <span data-ttu-id="5cde9-210">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5cde9-210">Here is an example.</span></span>

    ```Excel
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a><span data-ttu-id="5cde9-211">Grabador de tareas</span><span class="sxs-lookup"><span data-stu-id="5cde9-211">Task recorder</span></span>

- <span data-ttu-id="5cde9-212">Defina los escenarios antes de comenzar la grabación.</span><span class="sxs-lookup"><span data-stu-id="5cde9-212">Define scenarios before you start recording.</span></span> <span data-ttu-id="5cde9-213">Un proyecto bien gestionado tiene escenarios de prueba predefinidos.</span><span class="sxs-lookup"><span data-stu-id="5cde9-213">A well-managed project has predefined test scenarios.</span></span> <span data-ttu-id="5cde9-214">Para crear un caso de prueba, considere cómo de previsible es el resultado de esos escenarios de prueba.</span><span class="sxs-lookup"><span data-stu-id="5cde9-214">To build a test case, consider how predictable the outcome of those test scenarios is.</span></span>
- <span data-ttu-id="5cde9-215">Divida las grabaciones si son realizadas por distintos roles, o si hay un tiempo de espera o un evento externo para el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="5cde9-215">Split recordings if they are performed by different roles, or if there is waiting time or an external event before the next step.</span></span>
- <span data-ttu-id="5cde9-216">Evite seleccionar valores en las listas.</span><span class="sxs-lookup"><span data-stu-id="5cde9-216">Avoid selecting values in lists.</span></span> <span data-ttu-id="5cde9-217">En su lugar, utilice formatos de texto, como **FIFO**, **AudioRM** y **SiteWH**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-217">Instead, use text formats, such as **FIFO**, **AudioRM**, and **SiteWH**.</span></span> <span data-ttu-id="5cde9-218">Cuando seleccione de una lista, se graba la posición del valor de la lista, no el valor en sí.</span><span class="sxs-lookup"><span data-stu-id="5cde9-218">When you select in a list, the position of the value in the list is recorded, not the value itself.</span></span> <span data-ttu-id="5cde9-219">Si los artículos se agregan a esa lista, el puesto de valor puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="5cde9-219">If items are added to that list, the position of the value can change.</span></span> <span data-ttu-id="5cde9-220">Por lo tanto, su grabación utilizará un parámetro diferente, y el resto del escenario podría verse afectado.</span><span class="sxs-lookup"><span data-stu-id="5cde9-220">Therefore, your recording will use a different parameter, and the rest of the scenario might be affected.</span></span>
- <span data-ttu-id="5cde9-221">Piense en el comportamiento de varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="5cde9-221">Think about multi-user behavior.</span></span> <span data-ttu-id="5cde9-222">Por ejemplo, supongamos que su pedido de ventas recién creado no se seleccionará siempre automáticamente.</span><span class="sxs-lookup"><span data-stu-id="5cde9-222">For example, don't assume that your newly created sales order will always be automatically selected.</span></span> <span data-ttu-id="5cde9-223">En su lugar, utilice siempre el filtro para encontrar el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="5cde9-223">Instead, always use the filter to find the correct order.</span></span>
- <span data-ttu-id="5cde9-224">Utilice la función Copiar en el Grabador de tareas para guardar el nombre de un producto recién creado para que pueda usarse en casos de prueba encadenados.</span><span class="sxs-lookup"><span data-stu-id="5cde9-224">Use the Copy function in Task recorder to save the name of a newly created product so it can be used in chained test cases.</span></span>
- <span data-ttu-id="5cde9-225">Use la función Validar en el Grabador de tareas para establecer los puntos de control que verifiquen que los pasos se han ejecutado correctamente.</span><span class="sxs-lookup"><span data-stu-id="5cde9-225">Use the Validate function in Task recorder to set checkpoints that verify that steps have been run correctly.</span></span>

### <a name="rsat"></a><span data-ttu-id="5cde9-226">RSAT</span><span class="sxs-lookup"><span data-stu-id="5cde9-226">RSAT</span></span>

- <span data-ttu-id="5cde9-227">Para ejecutar la prueba en otra empresa, puede cambiar la empresa en la pestaña **General** del archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="5cde9-227">To run the test in another company, you can change the company on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="5cde9-228">Asegúrese de que la configuración y los datos estén disponibles en la empresa recién seleccionada.</span><span class="sxs-lookup"><span data-stu-id="5cde9-228">Make sure that settings and data are available in the newly selected company.</span></span>
- <span data-ttu-id="5cde9-229">Puede cambiar el usuario de la prueba en la pestaña **General** del archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="5cde9-229">You can change the test user on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="5cde9-230">Especifique el id. de correo electrónico del usuario que ejecutará el caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="5cde9-230">Specify the email ID of the user who will run the test case.</span></span> <span data-ttu-id="5cde9-231">De esta manera, el caso de prueba se puede ejecutar mediante los permisos de seguridad del usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="5cde9-231">In this way, the test case can be run by using the security permissions of the specified user.</span></span>
- <span data-ttu-id="5cde9-232">Para esperar antes de que se inicie la prueba, puede definir una pausa en la pestaña **General** del archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="5cde9-232">To wait before the test is started, you can define a pause on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="5cde9-233">Esta pausa se puede utilizar en un trabajo por lotes (por ejemplo, si un flujo de trabajo debe ejecutarse antes de que se realice el paso siguiente).</span><span class="sxs-lookup"><span data-stu-id="5cde9-233">This pause can be used in a batch job (for example, if a workflow must be run before the next step can be performed.)</span></span>

## <a name="advanced-scripting"></a><span data-ttu-id="5cde9-234">Secuencia de comandos avanzada</span><span class="sxs-lookup"><span data-stu-id="5cde9-234">Advanced scripting</span></span>

### <a name="cli"></a><span data-ttu-id="5cde9-235">CLI</span><span class="sxs-lookup"><span data-stu-id="5cde9-235">CLI</span></span>

<span data-ttu-id="5cde9-236">RSAT se puede llamar desde una ventana del **Símbolo del sistema** o **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-236">RSAT can be called from a **Command Prompt** or **PowerShell** window.</span></span>

> [!NOTE]
> <span data-ttu-id="5cde9-237">Verifique que la variable de entorno **TestRoot** está establecida en la ruta de instalación de RSAT.</span><span class="sxs-lookup"><span data-stu-id="5cde9-237">Verify that the **TestRoot** environment variable is set to the RSAT installation path.</span></span> <span data-ttu-id="5cde9-238">(En Microsoft Windows, abra **Panel de control**, seleccione **Sistema y seguridad \> Sistema \> Configuración del sistema avanzado** y, a continuación, seleccione **Variables de entorno**).</span><span class="sxs-lookup"><span data-stu-id="5cde9-238">(In Microsoft Windows, open **Control Panel**, select **System and Security \> System \> Advanced system settings**, and then select **Environment Variables**.)</span></span>

1. <span data-ttu-id="5cde9-239">Abra una ventana **Símbolo del sistema** o **PowerShell** como administrador.</span><span class="sxs-lookup"><span data-stu-id="5cde9-239">Open a **Command Prompt** or **PowerShell** window as an admin.</span></span>
2. <span data-ttu-id="5cde9-240">Navegue al directorio de instalación de RSAT.</span><span class="sxs-lookup"><span data-stu-id="5cde9-240">Navigate to the RSAT installation directory.</span></span>

    ```Console
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. <span data-ttu-id="5cde9-241">Enumere todos los comandos.</span><span class="sxs-lookup"><span data-stu-id="5cde9-241">List all commands.</span></span>

    ```Console
    C:\Program Files (x86)\Regression Suite Automation Tool>Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe help

    Usage:
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe command
        or
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe /settings "C:\Path to\file.settings" command

    Available commands:
        ?
        about
        cls
        download
        edit
        generate
        generatederived
        generatetestonly
        generatetestsuite
        help
        list
        listtestplans
        listtestsuite
        listtestsuitenames
        playback
        playbackbyid
        playbackmany
        playbacksuite
        quit
        upload
        uploadrecording
        usage
    ```

#### <a name=""></a><span data-ttu-id="5cde9-242">?</span><span class="sxs-lookup"><span data-stu-id="5cde9-242">?</span></span> 
<span data-ttu-id="5cde9-243">Muestra ayuda sobre todos los comandos disponibles y sus parámetros.</span><span class="sxs-lookup"><span data-stu-id="5cde9-243">Shows help about all available commands and their parameters.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="optional-parameters"></a><span data-ttu-id="5cde9-244">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="5cde9-244">Optional parameters</span></span>

**``command``**


<span data-ttu-id="5cde9-245">Dónde ``[command]`` es uno de los comandos especificados a continuación.</span><span class="sxs-lookup"><span data-stu-id="5cde9-245">Where ``[command]`` is one of the commands specified below.</span></span>


#### <a name="about"></a><span data-ttu-id="5cde9-246">acerca de</span><span class="sxs-lookup"><span data-stu-id="5cde9-246">about</span></span>
<span data-ttu-id="5cde9-247">Muestra la versión actual.</span><span class="sxs-lookup"><span data-stu-id="5cde9-247">Displays the current version.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a><span data-ttu-id="5cde9-248">cls</span><span class="sxs-lookup"><span data-stu-id="5cde9-248">cls</span></span>
<span data-ttu-id="5cde9-249">Borra la pantalla.</span><span class="sxs-lookup"><span data-stu-id="5cde9-249">Clears the screen.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**


#### <a name="download"></a><span data-ttu-id="5cde9-250">descargar</span><span class="sxs-lookup"><span data-stu-id="5cde9-250">download</span></span>
<span data-ttu-id="5cde9-251">Descarga archivos adjuntos para el caso de prueba especificado en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="5cde9-251">Downloads attachments for the specified test case to the output directory.</span></span> <span data-ttu-id="5cde9-252">Puede usar el comando ``list`` para obtener todos los casos de prueba disponibles.</span><span class="sxs-lookup"><span data-stu-id="5cde9-252">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="5cde9-253">Use cualquier valor de la primera columna como parámetro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-253">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="5cde9-254">Parámetros necesarios</span><span class="sxs-lookup"><span data-stu-id="5cde9-254">Required parameters</span></span>
<span data-ttu-id="5cde9-255">**``test_case_id``** Representa la identificación del caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="5cde9-255">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="5cde9-256">**``output_dir``** Representa el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="5cde9-256">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="5cde9-257">El directorio debe existir.</span><span class="sxs-lookup"><span data-stu-id="5cde9-257">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="5cde9-258">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5cde9-258">Examples</span></span>

``download 123 c:\temp\rsat``   
``download 765 c:\rsat\last``


#### <a name="edit"></a><span data-ttu-id="5cde9-259">editar</span><span class="sxs-lookup"><span data-stu-id="5cde9-259">edit</span></span>
<span data-ttu-id="5cde9-260">Le permite abrir el archivo de parámetros en el programa Excel y editarlo.</span><span class="sxs-lookup"><span data-stu-id="5cde9-260">Allows you to open parameters file in Excel program and edit it.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="required-parameters"></a><span data-ttu-id="5cde9-261">Parámetros necesarios</span><span class="sxs-lookup"><span data-stu-id="5cde9-261">Required parameters</span></span>
<span data-ttu-id="5cde9-262">**``excel_file``** Debe contener una ruta completa a un archivo Excel existente.</span><span class="sxs-lookup"><span data-stu-id="5cde9-262">**``excel_file``** Must contain a full path to an existing Excel file.</span></span>

##### <a name="examples"></a><span data-ttu-id="5cde9-263">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5cde9-263">Examples</span></span>
``edit c:\RSAT\TestCase_123_Base.xlsx``  
``edit e:\temp\TestCase_456_Base.xlsx``


#### <a name="generate"></a><span data-ttu-id="5cde9-264">generar</span><span class="sxs-lookup"><span data-stu-id="5cde9-264">generate</span></span>
<span data-ttu-id="5cde9-265">Genera archivos de ejecución y parámetros de prueba para el caso de prueba especificado en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="5cde9-265">Generates test execution and parameter files for the specified test case in the output directory.</span></span>
<span data-ttu-id="5cde9-266">Puede usar el comando ``list`` para obtener todos los casos de prueba disponibles.</span><span class="sxs-lookup"><span data-stu-id="5cde9-266">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="5cde9-267">Use cualquier valor de la primera columna como parámetro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-267">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="5cde9-268">Parámetros necesarios</span><span class="sxs-lookup"><span data-stu-id="5cde9-268">Required parameters</span></span>
<span data-ttu-id="5cde9-269">**``test_case_id``** Representa la identificación del caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="5cde9-269">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="5cde9-270">**``output_dir``** Representa el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="5cde9-270">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="5cde9-271">El directorio debe existir.</span><span class="sxs-lookup"><span data-stu-id="5cde9-271">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="5cde9-272">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5cde9-272">Examples</span></span>
``generate 123 c:\temp\rsat``  
``generate 765 c:\rsat\last``


#### <a name="generatederived"></a><span data-ttu-id="5cde9-273">generatederived</span><span class="sxs-lookup"><span data-stu-id="5cde9-273">generatederived</span></span>
<span data-ttu-id="5cde9-274">Genera un nuevo caso de prueba, derivado del caso de prueba proporcionado.</span><span class="sxs-lookup"><span data-stu-id="5cde9-274">Generates a new test case, derived from the provided test case.</span></span> <span data-ttu-id="5cde9-275">Puede usar el comando ``list`` para obtener todos los casos de prueba disponibles.</span><span class="sxs-lookup"><span data-stu-id="5cde9-275">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="5cde9-276">Use cualquier valor de la primera columna como parámetro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-276">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="required-parameters"></a><span data-ttu-id="5cde9-277">Parámetros necesarios</span><span class="sxs-lookup"><span data-stu-id="5cde9-277">Required parameters</span></span>
<span data-ttu-id="5cde9-278">**``parent_test_case_id``** Representa la identificación del caso de prueba primario.</span><span class="sxs-lookup"><span data-stu-id="5cde9-278">**``parent_test_case_id``** Represents the parent test case ID.</span></span>  
<span data-ttu-id="5cde9-279">**``test_plan_id``** Representa la identificación del plan de prueba</span><span class="sxs-lookup"><span data-stu-id="5cde9-279">**``test_plan_id``** Represents the test plan ID.</span></span>  
<span data-ttu-id="5cde9-280">**``test_suite_id``** Representa la identificación del conjunto de prueba</span><span class="sxs-lookup"><span data-stu-id="5cde9-280">**``test_suite_id``** Represents the test suite ID.</span></span>

##### <a name="examples"></a><span data-ttu-id="5cde9-281">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5cde9-281">Examples</span></span>
``generatederived 123 8901 678``


#### <a name="generatetestonly"></a><span data-ttu-id="5cde9-282">generatetestonly</span><span class="sxs-lookup"><span data-stu-id="5cde9-282">generatetestonly</span></span>
<span data-ttu-id="5cde9-283">Genera solo el archivo de ejecución de prueba para el caso de prueba especificado en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="5cde9-283">Generates only test execution file for the specified test case in the output directory.</span></span> <span data-ttu-id="5cde9-284">Puede usar el comando ``list`` para obtener todos los casos de prueba disponibles.</span><span class="sxs-lookup"><span data-stu-id="5cde9-284">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="5cde9-285">Use cualquier valor de la primera columna como parámetro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-285">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="5cde9-286">Parámetros necesarios</span><span class="sxs-lookup"><span data-stu-id="5cde9-286">Required parameters</span></span>
<span data-ttu-id="5cde9-287">**``test_case_id``** Representa la identificación del caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="5cde9-287">**``test_case_id``** Represents the test case ID.</span></span>  
<span data-ttu-id="5cde9-288">**``output_dir``** Representa el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="5cde9-288">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="5cde9-289">El directorio debe existir.</span><span class="sxs-lookup"><span data-stu-id="5cde9-289">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="5cde9-290">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5cde9-290">Examples</span></span>
``generatetestonly 123 c:\temp\rsat``  
``generatetestonly 765 c:\rsat\last``


#### <a name="generatetestsuite"></a><span data-ttu-id="5cde9-291">generatetestsuite</span><span class="sxs-lookup"><span data-stu-id="5cde9-291">generatetestsuite</span></span>
<span data-ttu-id="5cde9-292">Genera todos los casos de prueba para el conjunto especificado en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="5cde9-292">Generates all test cases for the specified suite in the output directory.</span></span>
<span data-ttu-id="5cde9-293">Puede usar el comando ``listtestsuitenames`` para obtener todos los conjuntos de prueba disponibles.</span><span class="sxs-lookup"><span data-stu-id="5cde9-293">You can use ``listtestsuitenames`` command to get all available test suits.</span></span> <span data-ttu-id="5cde9-294">Use cualquier valor de la primera columna como parámetro **test_suite_name**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-294">Use any value from the column as a **test_suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[test_suite_name] [output_dir]``

##### <a name="required-parameters"></a><span data-ttu-id="5cde9-295">Parámetros necesarios</span><span class="sxs-lookup"><span data-stu-id="5cde9-295">Required parameters</span></span>
<span data-ttu-id="5cde9-296">**``test_suite_name``** Representa el nombre del conjunto de prueba.</span><span class="sxs-lookup"><span data-stu-id="5cde9-296">**``test_suite_name``** Represents the test suite name.</span></span>  
<span data-ttu-id="5cde9-297">**``output_dir``** Representa el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="5cde9-297">**``output_dir``** Represents the output directory.</span></span> <span data-ttu-id="5cde9-298">El directorio debe existir.</span><span class="sxs-lookup"><span data-stu-id="5cde9-298">The directory must exist.</span></span>

##### <a name="examples"></a><span data-ttu-id="5cde9-299">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5cde9-299">Examples</span></span>
``generatetestsuite Tests c:\temp\rsat``   
``generatetestsuite Purchase c:\rsat\last``


#### <a name="help"></a><span data-ttu-id="5cde9-300">ayuda</span><span class="sxs-lookup"><span data-stu-id="5cde9-300">help</span></span>
<span data-ttu-id="5cde9-301">Idéntico a [?](####?)</span><span class="sxs-lookup"><span data-stu-id="5cde9-301">Identical to the [?](####?)</span></span> <span data-ttu-id="5cde9-302">comando</span><span class="sxs-lookup"><span data-stu-id="5cde9-302">command</span></span>


#### <a name="list"></a><span data-ttu-id="5cde9-303">lista</span><span class="sxs-lookup"><span data-stu-id="5cde9-303">list</span></span>
<span data-ttu-id="5cde9-304">Enumera todos los casos de prueba disponibles.</span><span class="sxs-lookup"><span data-stu-id="5cde9-304">Lists all available test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**


#### <a name="listtestplans"></a><span data-ttu-id="5cde9-305">listtestplans</span><span class="sxs-lookup"><span data-stu-id="5cde9-305">listtestplans</span></span>
<span data-ttu-id="5cde9-306">Enumera todos los planes de prueba disponibles.</span><span class="sxs-lookup"><span data-stu-id="5cde9-306">Lists all available test plans.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**


#### <a name="listtestsuite"></a><span data-ttu-id="5cde9-307">listtestsuite</span><span class="sxs-lookup"><span data-stu-id="5cde9-307">listtestsuite</span></span>
<span data-ttu-id="5cde9-308">Enumera casos de prueba para el conjunto de pruebas especificado.</span><span class="sxs-lookup"><span data-stu-id="5cde9-308">Lists test cases for the specified test suite.</span></span> <span data-ttu-id="5cde9-309">Puede usar el comando ``listtestsuitenames`` para obtener todos los conjuntos de prueba disponibles.</span><span class="sxs-lookup"><span data-stu-id="5cde9-309">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="5cde9-310">Use cualquier valor de la primera columna como parámetro **test_suite_name**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-310">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[suite_name]``

##### <a name="required-parameters"></a><span data-ttu-id="5cde9-311">Parámetros necesarios</span><span class="sxs-lookup"><span data-stu-id="5cde9-311">Required parameters</span></span>
<span data-ttu-id="5cde9-312">**``suite_name``** Nombre del conjunto deseado.</span><span class="sxs-lookup"><span data-stu-id="5cde9-312">**``suite_name``** Name of the desired suite.</span></span>

##### <a name="examples"></a><span data-ttu-id="5cde9-313">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5cde9-313">Examples</span></span>
``listtestsuite "sample suite name"``  
``listtestsuite NameOfTheSuite``


#### <a name="listtestsuitenames"></a><span data-ttu-id="5cde9-314">listtestsuitenames</span><span class="sxs-lookup"><span data-stu-id="5cde9-314">listtestsuitenames</span></span>
<span data-ttu-id="5cde9-315">Enumera todos los conjuntos de prueba disponibles.</span><span class="sxs-lookup"><span data-stu-id="5cde9-315">Lists all available test suites.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**


#### <a name="playback"></a><span data-ttu-id="5cde9-316">reproducción</span><span class="sxs-lookup"><span data-stu-id="5cde9-316">playback</span></span>
<span data-ttu-id="5cde9-317">Reproduce un caso de prueba usando un archivo Excel.</span><span class="sxs-lookup"><span data-stu-id="5cde9-317">Plays back a test case using an Excel file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[excel_file]``

##### <a name="required-parameters"></a><span data-ttu-id="5cde9-318">Parámetros necesarios</span><span class="sxs-lookup"><span data-stu-id="5cde9-318">Required parameters</span></span>
<span data-ttu-id="5cde9-319">**``excel_file``** Una ruta completa al archivo Excel.</span><span class="sxs-lookup"><span data-stu-id="5cde9-319">**``excel_file``** A full path to the Excel file.</span></span> <span data-ttu-id="5cde9-320">El archivo debe existir.</span><span class="sxs-lookup"><span data-stu-id="5cde9-320">File must exist.</span></span> 

##### <a name="examples"></a><span data-ttu-id="5cde9-321">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5cde9-321">Examples</span></span>
``
playback c:\RSAT\TestCaseParameters\sample1.xlsx
playback e:\temp\test.xlsx
``


#### <a name="playbackbyid"></a><span data-ttu-id="5cde9-322">playbackbyid</span><span class="sxs-lookup"><span data-stu-id="5cde9-322">playbackbyid</span></span>
<span data-ttu-id="5cde9-323">Reproduce múltiples casos de prueba a la vez.</span><span class="sxs-lookup"><span data-stu-id="5cde9-323">Plays back multiple test cases at once.</span></span>
<span data-ttu-id="5cde9-324">Puede usar el comando ``list`` para obtener todos los casos de prueba disponibles.</span><span class="sxs-lookup"><span data-stu-id="5cde9-324">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="5cde9-325">Use cualquier valor de la primera columna como parámetro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-325">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="required-parameters"></a><span data-ttu-id="5cde9-326">Parámetros necesarios</span><span class="sxs-lookup"><span data-stu-id="5cde9-326">Required parameters</span></span>
<span data-ttu-id="5cde9-327">**``test_case_id1``** Identificación del caso de prueba existente.</span><span class="sxs-lookup"><span data-stu-id="5cde9-327">**``test_case_id1``** ID of exisiting test case.</span></span>  
<span data-ttu-id="5cde9-328">**``test_case_id2``** Identificación del caso de prueba existente.</span><span class="sxs-lookup"><span data-stu-id="5cde9-328">**``test_case_id2``** ID of exisiting test case.</span></span>  
<span data-ttu-id="5cde9-329">**``test_case_idN``** Identificación del caso de prueba existente.</span><span class="sxs-lookup"><span data-stu-id="5cde9-329">**``test_case_idN``** ID of exisiting test case.</span></span>  

##### <a name="examples"></a><span data-ttu-id="5cde9-330">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5cde9-330">Examples</span></span>
``playbackbyid 878``  
``playbackbyid 2345 667 135``


#### <a name="playbackmany"></a><span data-ttu-id="5cde9-331">playbackmany</span><span class="sxs-lookup"><span data-stu-id="5cde9-331">playbackmany</span></span>
<span data-ttu-id="5cde9-332">Reproduce muchos casos de prueba a la vez, utilizando archivos de Excel.</span><span class="sxs-lookup"><span data-stu-id="5cde9-332">Plays back many test cases at once, using Excel files.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[excel_file1] [excel_file2] ... [excel_fileN]``

##### <a name="required-parameters"></a><span data-ttu-id="5cde9-333">Parámetros necesarios</span><span class="sxs-lookup"><span data-stu-id="5cde9-333">Required parameters</span></span>
<span data-ttu-id="5cde9-334">**``excel_file1``** Ruta completa al archivo Excel.</span><span class="sxs-lookup"><span data-stu-id="5cde9-334">**``excel_file1``** Full path to the Excel file.</span></span> <span data-ttu-id="5cde9-335">El archivo debe existir.</span><span class="sxs-lookup"><span data-stu-id="5cde9-335">File must exist.</span></span>  
<span data-ttu-id="5cde9-336">**``excel_file2``** Ruta completa al archivo Excel.</span><span class="sxs-lookup"><span data-stu-id="5cde9-336">**``excel_file2``** Full path to the Excel file.</span></span> <span data-ttu-id="5cde9-337">El archivo debe existir.</span><span class="sxs-lookup"><span data-stu-id="5cde9-337">File must exist.</span></span>  
<span data-ttu-id="5cde9-338">**``excel_fileN``** Ruta completa al archivo Excel.</span><span class="sxs-lookup"><span data-stu-id="5cde9-338">**``excel_fileN``** Full path to the Excel file.</span></span> <span data-ttu-id="5cde9-339">El archivo debe existir.</span><span class="sxs-lookup"><span data-stu-id="5cde9-339">File must exist.</span></span>  

##### <a name="examples"></a><span data-ttu-id="5cde9-340">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5cde9-340">Examples</span></span>
``playbackmany c:\RSAT\TestCaseParameters\param1.xlsx``  
``playbackmany e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx``


#### <a name="playbacksuite"></a><span data-ttu-id="5cde9-341">playbacksuite</span><span class="sxs-lookup"><span data-stu-id="5cde9-341">playbacksuite</span></span>
<span data-ttu-id="5cde9-342">Reproduce todos los casos de prueba del conjunto de pruebas especificado.</span><span class="sxs-lookup"><span data-stu-id="5cde9-342">Plays back all test cases from the specified test suite.</span></span> <span data-ttu-id="5cde9-343">Puede usar el comando ``listtestsuitenames`` para obtener todos los conjuntos de prueba disponibles.</span><span class="sxs-lookup"><span data-stu-id="5cde9-343">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="5cde9-344">Use cualquier valor de la primera columna como parámetro **test_suite_name**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-344">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[suite_name]``

##### <a name="required-parameters"></a><span data-ttu-id="5cde9-345">Parámetros necesarios</span><span class="sxs-lookup"><span data-stu-id="5cde9-345">Required parameters</span></span>
<span data-ttu-id="5cde9-346">**``suite_name``** Nombre del conjunto deseado.</span><span class="sxs-lookup"><span data-stu-id="5cde9-346">**``suite_name``** Name of the desired suite.</span></span>

##### <a name="examples"></a><span data-ttu-id="5cde9-347">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5cde9-347">Examples</span></span>
``playbacksuite suiteName``  
``playbacksuite sample_suite``


#### <a name="quit"></a><span data-ttu-id="5cde9-348">quit</span><span class="sxs-lookup"><span data-stu-id="5cde9-348">quit</span></span>
<span data-ttu-id="5cde9-349">Cierra la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5cde9-349">Closes the  application.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**


#### <a name="upload"></a><span data-ttu-id="5cde9-350">upload</span><span class="sxs-lookup"><span data-stu-id="5cde9-350">upload</span></span>
<span data-ttu-id="5cde9-351">Carga todos los archivos que pertenecen al conjunto de pruebas o casos de prueba especificados.</span><span class="sxs-lookup"><span data-stu-id="5cde9-351">Uploads all files belonging to the specified test suite or test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``[suite_name] [testcase_id]``

#### <a name="required-parameters"></a><span data-ttu-id="5cde9-352">Parámetros necesarios</span><span class="sxs-lookup"><span data-stu-id="5cde9-352">Required parameters</span></span>
<span data-ttu-id="5cde9-353">**``suite_name``** Carga todos los archivos que pertenecen al conjunto de pruebas especificado.</span><span class="sxs-lookup"><span data-stu-id="5cde9-353">**``suite_name``** All files belonging to the specified test suite will be uploaded.</span></span>
<span data-ttu-id="5cde9-354">**``testcase_id``** Carga todos los archivos que pertenecen al conjunto (o conjuntos) de pruebas especificado(s).</span><span class="sxs-lookup"><span data-stu-id="5cde9-354">**``testcase_id``** All files beloning to the specified test case(s) will be uploaded.</span></span>

##### <a name="examples"></a><span data-ttu-id="5cde9-355">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5cde9-355">Examples</span></span>
``upload sample_suite``  
``upload 123``  
``upload 123 456``


#### <a name="uploadrecording"></a><span data-ttu-id="5cde9-356">uploadrecording</span><span class="sxs-lookup"><span data-stu-id="5cde9-356">uploadrecording</span></span>
<span data-ttu-id="5cde9-357">Carga solo el archivo de grabación que pertenece a los casos de prueba especificados.</span><span class="sxs-lookup"><span data-stu-id="5cde9-357">Uploads only recording file belonging to the specified test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[testcase_id]``

##### <a name="required-parameters"></a><span data-ttu-id="5cde9-358">Parámetros necesarios</span><span class="sxs-lookup"><span data-stu-id="5cde9-358">Required parameters</span></span>
<span data-ttu-id="5cde9-359">**``testcase_id``** Cargará el archivo de grabación que pertenece a los casos de prueba especificados.</span><span class="sxs-lookup"><span data-stu-id="5cde9-359">**``testcase_id``** Recording file belonging to the specified test cases will be uploaded.</span></span>

##### <a name="examples"></a><span data-ttu-id="5cde9-360">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5cde9-360">Examples</span></span>
``uploadrecording 123``  
``uploadrecording 123 456``


#### <a name="usage"></a><span data-ttu-id="5cde9-361">usage</span><span class="sxs-lookup"><span data-stu-id="5cde9-361">usage</span></span>
<span data-ttu-id="5cde9-362">Muestra dos formas de invocar esta aplicación: una con un archivo de configuración predeterminado y otra con un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="5cde9-362">Shows two ways to invoke this application: one using a default setting file, another one providing a setting file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**


### <a name="windows-powershell-examples"></a><span data-ttu-id="5cde9-363">Ejemplos de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5cde9-363">Windows PowerShell examples</span></span>

#### <a name="run-a-test-case-in-a-loop"></a><span data-ttu-id="5cde9-364">Ejecutar un caso de prueba en un bucle</span><span class="sxs-lookup"><span data-stu-id="5cde9-364">Run a test case in a loop</span></span>

<span data-ttu-id="5cde9-365">Tiene una secuencia de comandos de prueba que crea un nuevo cliente.</span><span class="sxs-lookup"><span data-stu-id="5cde9-365">You have a test script that creates a new customer.</span></span> <span data-ttu-id="5cde9-366">Mediante la secuencia de comandos, este caso de prueba se puede ejecutar en un bucle aleatorizando los siguientes datos antes de que se ejecute cada iteración:</span><span class="sxs-lookup"><span data-stu-id="5cde9-366">Via scripting, this test case can be run in a loop by randomizing the following data before each iteration is run:</span></span>

- <span data-ttu-id="5cde9-367">Id. de cliente</span><span class="sxs-lookup"><span data-stu-id="5cde9-367">Customer ID</span></span>
- <span data-ttu-id="5cde9-368">Nombre de cliente</span><span class="sxs-lookup"><span data-stu-id="5cde9-368">Customer name</span></span>
- <span data-ttu-id="5cde9-369">Dirección del cliente</span><span class="sxs-lookup"><span data-stu-id="5cde9-369">Customer address</span></span>

<span data-ttu-id="5cde9-370">El id. del cliente tendrá el formato *ATCUS\<number\>*, donde \<number\> es un valor entre **000000001** y **999999999**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-370">The customer ID will be in the format *ATCUS\<number\>*, where \<number\> is a value between **000000001** and **999999999**.</span></span>

<span data-ttu-id="5cde9-371">El siguiente ejemplo utiliza un parámetro, **start**, para definir el primer número que se usa.</span><span class="sxs-lookup"><span data-stu-id="5cde9-371">The following example uses one parameter, **start**, to define the first number that is used.</span></span> <span data-ttu-id="5cde9-372">Utiliza un segundo parámetro, **nr**, para definir el número de clientes que deben crearse.</span><span class="sxs-lookup"><span data-stu-id="5cde9-372">Is uses a second parameter, **nr**, to define the number of customers that must be created.</span></span> <span data-ttu-id="5cde9-373">Para cada iteración, los parámetros en el archivo de parámetros de Excel se cambian mediante una función UpdateCustomer.</span><span class="sxs-lookup"><span data-stu-id="5cde9-373">For each iteration, the parameters in the Excel parameter file are changed by using an UpdateCustomer function.</span></span> <span data-ttu-id="5cde9-374">A continuación, la línea de comandos de RSAT se llama en una función RunTestCase.</span><span class="sxs-lookup"><span data-stu-id="5cde9-374">Then the RSAT command line is called in a RunTestCase function.</span></span>

<span data-ttu-id="5cde9-375">Abra el Entorno de scripting integrado (ISE) de Microsoft Windows PowerShell en modo de administración y pegue el siguiente código en la ventaja que se denomina **Untitled1.ps1**.</span><span class="sxs-lookup"><span data-stu-id="5cde9-375">Open Microsoft Windows PowerShell Integrated Scripting Environment (ISE) in admin mode, and paste the following code into the window that is named **Untitled1.ps1**.</span></span>

```powershell
param ( [int]$start = 1, [int]$nr = 1 )
function UpdateCustomer
{
    param ([string]$paramFilename, [string]$sheetName, [string]$CustId)
    $xl = New-Object -COM "Excel.Application"
    $xl.Visible = $false
    $wb = $xl.Workbooks.Open($paramFilename)
    $ws = $wb.Sheets.Item($sheetName)
    $ws.Cells.Item(3, 2).Value = "ATCUS" + $CustId
    $ws.Cells.Item(4, 2).Value = "Automated Test Customer " + $CustId
    $ws.Cells.Item(8, 2).Value = "Automated Test Street " + $CustId
    $wb.Save()
    $wb.Close()
    $xl.Quit()
    [System.Runtime.Interopservices.Marshal]::ReleaseComObject($xl)
}
function RunTestCase
{
    param ( [string]$filename )
    $cmd = "cd c:\Program Files (x86)\Regression Suite Automation Tool\ &&  "
    $cmd = $cmd + "Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe playback "
    $cmd = $cmd + $filename
    cmd /c $cmd
}
$excelFilename = "full path to excel file parameter file"
l$sheetName = "DirPartyQuickCreateForm"
for ($i = $start; $i -lt $start + $nr; $i++ )
{
    $CustomerId = $i.ToString("000000000")
    Write-Host "customer : " $CustomerId
    UpdateCustomer $excelFilename $sheetName $CustomerId
    RunTestCase $excelFilename
```

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a><span data-ttu-id="5cde9-376">Ejecutar una secuencia de comandos que depende de los datos de Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="5cde9-376">Run a script that depends on data in Microsoft Dynamics 365</span></span>

<span data-ttu-id="5cde9-377">El siguiente ejemplo utiliza una llamada del protocolo abierto de datos (OData) para encontrar el estado del pedido de un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="5cde9-377">The following example uses an Open Data Protocol (OData) call to find the order status of a purchase order.</span></span> <span data-ttu-id="5cde9-378">Si el estado no se **factura**, puede, por ejemplo, llamar a un caso de prueba de RSAT que registra la factura.</span><span class="sxs-lookup"><span data-stu-id="5cde9-378">If the status isn't **invoiced**, you can, for example, call an RSAT test case that posts the invoice.</span></span>

```xpp
function Odata_Get
{
    Param ( [string] $environment, [string] $cmd )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
    $tenant = "your tenant"
    $creds = @{
        grant_type = "client_credentials"
        client_id = "your client application Id"
        client_secret = "your client secret"
        resource = $environment
    }
    $headers = $null
    $bearer = Invoke-RestMethod https://login.microsoftonline.com/$tenant/oauth2/token -Method Post -Body $creds -Headers $headers;
    $headers = @{
        Authorization = "Bearer " + $bearer.access_token
    }
    $Odata_cmd = $environment + '/data/' + $cmd
    return (Invoke-RestMethod -Uri $Odata_cmd -Method Get -Headers $headers -ContentType application/json )
}
function PurchaseOrderStatus
{
    Param ( [string] $environment, [string] $purchaseOrderNumber )
    $cmd = 'PurchaseOrderHeaders?$filter=PurchaseOrderNumber eq '
    $cmd = $cmd + "'" + $purchaseOrderNumber + "'"
    $response = Odata_Get -environment $environment -cmd $cmd
    return $response.value.PurchaseOrderStatus
}
$environment = "https://your environment"
$orderStatus = PurchaseOrderStatus -environment $environment -purchaseOrderNumber '000003'
if ($orderStatus -eq $null) {   write-host 'doesn''t exist'}
elseif ($orderStatus -ne 'invoiced') { RunTestCase "PostInvoice" }
```
