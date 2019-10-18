---
title: Utilizar tutorial Regression Suite Automation Tool
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
ms.openlocfilehash: cf3ca501efb4e540994b01e651eee5b8aab4ddbc
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2191095"
---
# <a name="use-the-regression-suite-automation-tool-tutorial"></a><span data-ttu-id="6bdf1-104">Utilizar el tutorial Regression Suite Automation Tool</span><span class="sxs-lookup"><span data-stu-id="6bdf1-104">Use the Regression suite automation tool tutorial</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="6bdf1-105">Utilice las herramientas del navegador de Internet para descargar y guardar esta página en formato pdf.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-105">Use your internet browser tools to download and save this page in pdf format.</span></span> 

<span data-ttu-id="6bdf1-106">Este tutorial le muestra algunas de las características avanzadas de la Regression Suite Automation Tool (RSAT), incluye una asignación de demostración y describe la estrategia y los puntos de aprendizaje clave.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-106">This tutorial walks through some of the advanced features of the Regression suite automation tool (RSAT), includes a demo assignment, and describes strategy and key learning points.</span></span>

## <a name="features-of-rsattask-recorder"></a><span data-ttu-id="6bdf1-107">Características de RSAT/Grabador de tareas</span><span class="sxs-lookup"><span data-stu-id="6bdf1-107">Features of RSAT/Task recorder</span></span>

### <a name="validate-a-field-value"></a><span data-ttu-id="6bdf1-108">Validar un valor del campo</span><span class="sxs-lookup"><span data-stu-id="6bdf1-108">Validate a field value</span></span>

<span data-ttu-id="6bdf1-109">Para obtener más información sobre esta característica, consulte [Crear una nueva grabación de tareas que tenga una función Validar](./hol-set-up-regression-suite-automation-tool.md#create-a-new-task-recording-that-has-a-validate-function).</span><span class="sxs-lookup"><span data-stu-id="6bdf1-109">For information about this feature, see the [Create a new task recording that has a Validate function](./hol-set-up-regression-suite-automation-tool.md#create-a-new-task-recording-that-has-a-validate-function).</span></span>

### <a name="saved-variable"></a><span data-ttu-id="6bdf1-110">Variable guardada</span><span class="sxs-lookup"><span data-stu-id="6bdf1-110">Saved variable</span></span>

<span data-ttu-id="6bdf1-111">Para obtener más información sobre esta característica, consulte [Modificar una grabación de tareas existente para crear una variable guardada](./hol-set-up-regression-suite-automation-tool.md#modify-an-existing-task-recording-to-create-a-saved-variable).</span><span class="sxs-lookup"><span data-stu-id="6bdf1-111">For information about this feature, see the [Modify an existing task recording to create a saved variable](./hol-set-up-regression-suite-automation-tool.md#modify-an-existing-task-recording-to-create-a-saved-variable).</span></span>

### <a name="derived-test-case"></a><span data-ttu-id="6bdf1-112">Caso de prueba derivado</span><span class="sxs-lookup"><span data-stu-id="6bdf1-112">Derived test case</span></span>

1. <span data-ttu-id="6bdf1-113">Abra la Regression Suite Automation Tool (RSAT) y seleccione los casos de prueba que creó en [Configurar e instalar Regression Suite Automation Tool](./hol-set-up-regression-suite-automation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="6bdf1-113">Open Regression suite automation tool (RSAT), and select both the test cases that you created in [Set up and install Regression suite automation tool](./hol-set-up-regression-suite-automation-tool.md).</span></span>
2. <span data-ttu-id="6bdf1-114">Seleccione **Nuevo \> Crear caso de prueba derivado**.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-114">Select **New \> Create derived test case**.</span></span>

    ![Comando Crear caso de prueba derivado en el menú Nuevo](./media/use_rsa_tool_01.png)

3. <span data-ttu-id="6bdf1-116">Recibe un mensaje que indica que se creará un caso de prueba derivado para cada caso de prueba seleccionado en el conjunto de pruebas actual, y que cada caso de prueba derivado tendrá su propia copia del archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-116">You receive a message that states that a derived test case will be created for each selected test case in the current test suite, and that each derived test case will have its own copy of the Excel parameter file.</span></span> <span data-ttu-id="6bdf1-117">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-117">Select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6bdf1-118">Cuando ejecute un caso de prueba derivado, se utiliza el grabador de tareas de su caso de prueba principal y su propia copia del archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-118">When you run a derived test case, it uses the task recording of its parent test case and its own copy of the Excel parameter file.</span></span> <span data-ttu-id="6bdf1-119">De esta manera, puede ejecutar la misma prueba con distintos parámetros, sin tener que mantener más de un grabador de tareas.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-119">In this way, you can run the same test with different parameters, without having to maintain more than one task recording.</span></span> <span data-ttu-id="6bdf1-120">Un caso de prueba derivado no tiene que formar parte del mismo conjunto de pruebas que su caso de prueba principal.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-120">A derived test case doesn't have to be part of the same test suite as its parent test case.</span></span>

    ![Cuadro de mensaje](./media/use_rsa_tool_02.png)

    <span data-ttu-id="6bdf1-122">Se crean dos casos de prueba derivados adicionales, y la casilla **¿Derivado?** se selecciona para ellos.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-122">Two additional derived test cases are created, and the **Derived?** check box is selected for them.</span></span>

    ![Casos de prueba derivados creados](./media/use_rsa_tool_03.png)

    <span data-ttu-id="6bdf1-124">Se crea automáticamente un caso de prueba derivado en Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-124">A derived test case is automatically created in Azure DevOps.</span></span> <span data-ttu-id="6bdf1-125">Es un artículo secundario del caso de prueba **Crear un nuevo producto** y se etiqueta con una palabra clave especial: **RSAT:DerivedTestSteps**.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-125">It's a child item of the **Create a new product** test case and is tagged with a special keyword: **RSAT:DerivedTestSteps**.</span></span> <span data-ttu-id="6bdf1-126">Estos casos de prueba también se agregan automáticamente al plan de prueba en Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-126">These test cases are also automatically added to the test plan in Azure DevOps.</span></span>

    ![Palabra clave RSAT:DerivedTestSteps](./media/use_rsa_tool_04.png)

    > [!NOTE]
    > <span data-ttu-id="6bdf1-128">Si, por algún motivo, los casos de prueba derivados que se crean no lo hacen en el orden correcto, vaya a Azure DevOps y reordene los casos de prueba en el conjunto de pruebas, de modo que la RSAT pueda ejecutarlos en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-128">If, for any reason, the derived test cases that are created aren't in the correct order, go to Azure DevOps, and reorder the test cases in the test suite, so that RSAT can run them in the correct order.</span></span>

4. <span data-ttu-id="6bdf1-129">Seleccione los casos de prueba derivados y, a continuación. seleccione **Editar** para abrir los archivos de parámetros de Excel correspondientes.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-129">Select the derived test cases, and then select **Edit** to open the corresponding Excel parameter files.</span></span>
5. <span data-ttu-id="6bdf1-130">Edite estos archivos de parámetros de Excel del mismo modo que editó los archivos principales.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-130">Edit these Excel parameter files in the same way that you edited the parent files.</span></span> <span data-ttu-id="6bdf1-131">Es decir, asegúrese de que el id. de producto esté establecido para que se genere automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-131">In other words, make sure that the product ID is set so that it's automatically generated.</span></span> <span data-ttu-id="6bdf1-132">Asegúrese también de que la variable guardada se copie a los campos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-132">Also make sure that the saved variable is copied to the relevant fields.</span></span>
6. <span data-ttu-id="6bdf1-133">En la pestaña **General** de ambos archivos de parámetros de Excel, actualice el valor del campo **Empresa** a **USSI**, de modo que los casos de prueba derivados se ejecuten con una entidad jurídica distinta a la del caso de prueba principal.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-133">On the **General** tab of both Excel parameter files, update the value of the **Company** field to **USSI**, so that the derived test cases will be run against a different legal entity than the parent test case.</span></span> <span data-ttu-id="6bdf1-134">Para ejecutar los casos de prueba con un usuario específico (o el rol asociado a un usuario específico), puede actualizar el valor del campo **Usuario de la prueba**.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-134">To run the test cases against a specific user (or the role that is associated with a specific user), you can update the value of the **Test User** field.</span></span>
7. <span data-ttu-id="6bdf1-135">Seleccione **Ejecutar** y valide que el producto se crea tanto en la entidad jurídica de USMF y como en la entidad jurídica de USSI.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-135">Select **Run**, and validate that the product is created in both the USMF legal entity and the USSI legal entity.</span></span>

### <a name="validate-notifications"></a><span data-ttu-id="6bdf1-136">Validar notificaciones</span><span class="sxs-lookup"><span data-stu-id="6bdf1-136">Validate notifications</span></span>

<span data-ttu-id="6bdf1-137">Esta característica se puede utilizar para validar si se produjo una acción.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-137">This feature can be used to validate whether an action occurred.</span></span> <span data-ttu-id="6bdf1-138">Por ejemplo, cuando se crea, estima y inicia una orden de producción, la aplicación muestra un mensaje "Producción – Inicio" para notificarle que se ha iniciado el pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-138">For example, when a production order is created, estimated, and then started, the app shows a "Production – Start" message to notify you that the production order has been started.</span></span>

![Notificación Producción – Inicio](./media/use_rsa_tool_05.png)

<span data-ttu-id="6bdf1-140">Puede validar este mensaje a través RSAT introduciendo el texto del mensaje en la pestaña **MessageValidation** del archivo de parámetros de Excel para la grabación adecuada.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-140">You can validate this message through RSAT by entering the message text on the **MessageValidation** tab of the Excel parameter file for the appropriate recording.</span></span>

![Pestaña Validación de mensaje](./media/use_rsa_tool_06.png)

<span data-ttu-id="6bdf1-142">Una vez que se ejecute el caso de prueba, el mensaje del archivo de parámetros de Excel se compara con el mensaje que se muestra.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-142">After the test case is run, the message in the Excel parameter file is compared to the message that is shown.</span></span> <span data-ttu-id="6bdf1-143">Si los mensajes no coinciden, el caso de prueba fallará.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-143">If the messages don't match, the test case will fail.</span></span>

> [!NOTE]
> <span data-ttu-id="6bdf1-144">Puede introducir más de un mensaje en la pestaña **MessageValidation** en el archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-144">You can enter more than one message on the **MessageValidation** tab in the Excel parameter file.</span></span> <span data-ttu-id="6bdf1-145">Los mensajes también pueden ser de error o de advertencia en lugar de mensajes informativos.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-145">The messages also can be error or warning messages instead of informational messages.</span></span>

### <a name="validate-values-by-using-operators"></a><span data-ttu-id="6bdf1-146">Validar valores mediante el uso de operadores</span><span class="sxs-lookup"><span data-stu-id="6bdf1-146">Validate values by using operators</span></span>

<span data-ttu-id="6bdf1-147">En versiones anteriores de RSAT, podía validar valores solo si un valor de control era igual a un valor esperado.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-147">In previous versions of RSAT, you could validate values only if a control value equaled an expected value.</span></span> <span data-ttu-id="6bdf1-148">La nueva característica le permite validar que una variable no es igual a, menor que o mayor que un valor especificado.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-148">The new feature lets you validate that a variable isn't equal to, is less than, or is more than a specified value.</span></span>

- <span data-ttu-id="6bdf1-149">Para utilizar esta característica, abra el archivo **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** en la carpeta de instalación de RSAT (por ejemplo, **C:\\Archivos de programa (x86)\\Regression Suite Automation Tool**) y cambie el valor en el siguiente elemento de **falso** a **verdadero**.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-149">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value in the following element from **false** to **true**.</span></span>

    ```
    <add key="AddOperatorFieldsToExcelValidation" value="false" />
    ```

    <span data-ttu-id="6bdf1-150">En el archivo de parámetros de Excel, aparece un nuevo campo **Operador**.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-150">In the Excel parameter file, a new **Operator** field appears.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6bdf1-151">Si ha estado utilizando una versión anterior de RSAT, debe generar los nuevos archivos de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-151">If you've been using an older version of RSAT, you must generate new Excel parameter files.</span></span>

    ![Campo Operador](./media/use_rsa_tool_07.png)

<span data-ttu-id="6bdf1-153">El siguiente ejemplo muestra cómo puede utilizar esta característica para validar si el inventario disponible es superior a 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="6bdf1-153">The following example shows how you can use this feature to validate whether the on-hand inventory is more than 0 (zero).</span></span>

1. <span data-ttu-id="6bdf1-154">En los datos de demostración en la empresa **USMF**, cree una grabación de tareas que tenga los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="6bdf1-154">In the demo data in the **USMF** company, create a task recording that has the following steps:</span></span>

    1. <span data-ttu-id="6bdf1-155">Vaya a **Gestión de información de productos \> Productos \> Productos emitidos**.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-155">Go to **Product information management \> Products \> Released products**.</span></span>
    2. <span data-ttu-id="6bdf1-156">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-156">Use the Quick Filter to find records.</span></span> <span data-ttu-id="6bdf1-157">Por ejemplo, aplique un filtro de un valor de **1000** para el campo **Número de artículo**.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-157">For example, filter on a value of **1000** for the **Item number** field.</span></span>
    3. <span data-ttu-id="6bdf1-158">Seleccione **Inventario disponible**.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-158">Select **On-hand inventory**.</span></span>
    4. <span data-ttu-id="6bdf1-159">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-159">Use the Quick Filter to find records.</span></span> <span data-ttu-id="6bdf1-160">Por ejemplo, aplique un filtro de un valor de **1** para el campo **Sitio**.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-160">For example, filter on a value of **1** for the **Site** field.</span></span>
    5. <span data-ttu-id="6bdf1-161">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-161">In the list, mark the selected row.</span></span>
    6. <span data-ttu-id="6bdf1-162">Valide que el valor del campo **Total disponible** es **411,0000000000000000**.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-162">Validate that the value of the **Total available** field is **411.0000000000000000**.</span></span>

2. <span data-ttu-id="6bdf1-163">Guarde la grabación de tareas en la biblioteca de BPM en LCS y sincronícela en Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-163">Save the task recording to the BPM library in LCS, and sync it to Azure DevOps.</span></span>
3. <span data-ttu-id="6bdf1-164">Agregue el caso de prueba al plan de pruebas, y cargue el caso de prueba en RSAT.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-164">Add the test case to the test plan, and load the test case into RSAT.</span></span>
4. <span data-ttu-id="6bdf1-165">Abra el archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-165">Open the Excel parameter file.</span></span> <span data-ttu-id="6bdf1-166">En la pestaña **InventOnhandItem**, verá una sección **Validar InventOnhandItem** que incluye un campo **Operador**.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-166">On the **InventOnhandItem** tab, you will see a **Validate InventOnhandItem** section that includes an **Operator** field.</span></span>

    ![Campo Operador](./media/use_rsa_tool_08.png)

5. <span data-ttu-id="6bdf1-168">Para validar que el inventario disponible será siempre superior a 0, cambie el valor del campo **Valor** de **411** a **0** y el valor del campo **Operador** de un signo igual (**=**) a un signo mayor que (**\>**).</span><span class="sxs-lookup"><span data-stu-id="6bdf1-168">To validate whether the inventory on-hand will always be more than 0, change the value of the **Value** field from **411** to **0** and the value of the **Operator** field from an equal sign (**=**) to a greater than sign (**\>**).</span></span>

    ![Valores cambiados de los campos Valor y y Operador](./media/use_rsa_tool_09.png)

6. <span data-ttu-id="6bdf1-170">Guarde y cierre el archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-170">Save and close the Excel parameter file.</span></span>
7. <span data-ttu-id="6bdf1-171">Seleccione **Cargar** para guardar los cambios realizados en el archivo de parámetros de Excel en Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-171">Select **Upload** to save the changes that you made to the Excel parameter file to Azure DevOps.</span></span>

<span data-ttu-id="6bdf1-172">Ahora, si es el valor del campo **Total disponible** para el artículo especificado en el inventario es superior a 0 (cero), las pruebas se aprobarán, independientemente del valor real del inventario disponible.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-172">Now, if the value of the **Total Available** field for the specified item in inventory is more than 0 (zero), tests will pass, regardless of the actual on-hand inventory value.</span></span>

### <a name="generator-logs"></a><span data-ttu-id="6bdf1-173">Registros del generador</span><span class="sxs-lookup"><span data-stu-id="6bdf1-173">Generator logs</span></span>

<span data-ttu-id="6bdf1-174">Esta característica crea una carpeta que contiene los registros de los casos de prueba que se han ejecutado.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-174">This feature creates a folder that contains the logs of the test cases that have been run.</span></span>

- <span data-ttu-id="6bdf1-175">Para utilizar esta característica, abra el archivo **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** en la carpeta de instalación de RSAT (por ejemplo, **C:\\Archivos de programa (x86)\\Regression Suite Automation Tool**) y cambie el valor en el siguiente elemento de **falso** a **verdadero**.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-175">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value in the following element from **false** to **true**.</span></span>

    ```
    <add key="LogGeneration" value="false" />
    ```

<span data-ttu-id="6bdf1-176">Una vez que se ejecuten los casos de prueba, puede encontrar los archivos de registro en **C:\\Usuarios\\\<Nombre de usuario\>\\AppData\\Roaming\\RegressionTool\\generatorLogs**.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-176">After the test cases are run, you can find the log files under **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\generatorLogs**.</span></span>

![Carpeta GeneratorLogs](./media/use_rsa_tool_10.png)

> [!NOTE]
> <span data-ttu-id="6bdf1-178">Si había casos de prueba existentes antes de cambiar el valor del archivo .config, los registros no se generarán para aquellos casos de prueba hasta que genere nuevos archivos de ejecución de pruebas.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-178">If there were existing test cases before you changed the value in the .config file, logs won't be generated for those test cases until you generate new test execution files.</span></span>
> 
> ![Comando Generar solo archivos Ejecución de texto en el menú Nuevo](./media/use_rsa_tool_11.png)

### <a name="snapshot"></a><span data-ttu-id="6bdf1-180">Captura de pantalla</span><span class="sxs-lookup"><span data-stu-id="6bdf1-180">Snapshot</span></span>

<span data-ttu-id="6bdf1-181">Esta característica realiza capturas de pantalla de los pasos que se realizaron durante la grabación de tareas.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-181">This feature takes screenshots of the steps that were performed during task recording.</span></span>

- <span data-ttu-id="6bdf1-182">Para utilizar esta característica, abra el archivo **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** en la carpeta de instalación de RSAT (por ejemplo, **C:\\Archivos de programa (x86)\\Regression Suite Automation Tool**) y cambie el valor del siguiente elemento de **falso** a **verdadero**.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-182">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value of the following element from **false** to **true**.</span></span>

    ```
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

<span data-ttu-id="6bdf1-183">En **C:\\Usuarios\\\<Nombre de usuario\>\\AppData\\Roaming\\regressionTool\\reproducción**, se cra una carpeta independiente para cada caso de prueba que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-183">Under **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback**, a separate folder is created for each test case that is run.</span></span>

![Carpeta Captura de pantalla para un caso de prueba](./media/use_rsa_tool_12.png)

<span data-ttu-id="6bdf1-185">En cada una de estas carpetas, puede encontrar capturas de pantalla de los pasos que se realizaron mientras se ejecutaban los casos de prueba.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-185">In each of these folders, you can find snapshots of the steps that were performed while the test cases were run.</span></span>

![Archivos Captura de pantalla](./media/use_rsa_tool_13.png)

## <a name="assignment"></a><span data-ttu-id="6bdf1-187">Asignación</span><span class="sxs-lookup"><span data-stu-id="6bdf1-187">Assignment</span></span>

### <a name="scenario"></a><span data-ttu-id="6bdf1-188">Situación</span><span class="sxs-lookup"><span data-stu-id="6bdf1-188">Scenario</span></span>

1. <span data-ttu-id="6bdf1-189">El diseñador de productos crea un nuevo producto lanzado.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-189">The product designer creates a new released product.</span></span>
2. <span data-ttu-id="6bdf1-190">El director de producción inicia una orden de producción para llevar el nivel de existencias a dos piezas.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-190">The production manager initiates a production order to bring the stock level to two pieces.</span></span>
3. <span data-ttu-id="6bdf1-191">La fabricación comienza y termina con el pedido de producción, y verifica que la cantidad disponible es de dos piezas.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-191">Manufacturing starts and ends the production order, and verifies that the on-hand quantity is two pieces.</span></span>
4. <span data-ttu-id="6bdf1-192">El equipo de ventas recibe un pedido para cuatro piezas del nuevo producto.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-192">The sales team receives an order for four pieces of the new product.</span></span> <span data-ttu-id="6bdf1-193">Por lo tanto, el equipo de ventas actualia los requisitos netos a través del plan dinámico.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-193">Therefore, the sales team updates the net requirements via the dynamic plan.</span></span> <span data-ttu-id="6bdf1-194">Puesto que no hay capacidad adicional disponible, la directiva de pedidos predeterminada se establece en "comprar en lugar de fabricar".</span><span class="sxs-lookup"><span data-stu-id="6bdf1-194">Because no additional capacity is available, the default order policy is set to "buy instead of make."</span></span> <span data-ttu-id="6bdf1-195">Por lo tanto, se crea un pedido de compra planificado.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-195">Therefore, a planned purchase order is created.</span></span>
5. <span data-ttu-id="6bdf1-196">El comprador agrega un proveedor, consolida el pedido de compra planificado y, a continuación, confirma el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-196">The buyer adds a vendor, firms the planned purchase order, and then confirms the purchase order.</span></span>
6. <span data-ttu-id="6bdf1-197">Cuando las mercancías que se adquirieron llegan el almacén, el operador de almacén busca el pedido de compra relacionado y recibe las mercancías.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-197">When the goods that were purchased arrive at the store, the store operator searches the related purchase order and receives the goods.</span></span> <span data-ttu-id="6bdf1-198">Puesto que el pedido está ahora completado, las mercancías se pueden seleccionar y empaquetar con el pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-198">Because the order is now completed, goods can be picked and packed against the sales order.</span></span>
7. <span data-ttu-id="6bdf1-199">Finance registra la factura de compra y la factura de ventas.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-199">Finance posts the purchase invoice and sales invoice.</span></span>

<span data-ttu-id="6bdf1-200">En la ilustración siguiente se muestra el flujo para este escenario.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-200">The following illustration shows the flow for this scenario.</span></span>

![Flujo para el escenario de demostración](./media/use_rsa_tool_14.png)

<span data-ttu-id="6bdf1-202">En la ilustración siguiente se muestran los procesos empresariales para este escenario en RSAT.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-202">The following illustration shows the business processes for this scenario in RSAT.</span></span>

![Procesos empresariales para el escenario de demostración](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a><span data-ttu-id="6bdf1-204">Estrategia – Aprendizaje clave</span><span class="sxs-lookup"><span data-stu-id="6bdf1-204">Strategy – Key learning</span></span>

### <a name="data"></a><span data-ttu-id="6bdf1-205">Datos</span><span class="sxs-lookup"><span data-stu-id="6bdf1-205">Data</span></span>

- <span data-ttu-id="6bdf1-206">Asegúrese de que tiene volúmenes de datos representativos (una copia de los datos de configuración de producción/dorados más los datos migrados).</span><span class="sxs-lookup"><span data-stu-id="6bdf1-206">Make sure that you have representative data volumes (a copy of production/golden configuration data plus migrated data).</span></span>
- <span data-ttu-id="6bdf1-207">Cuando genere nuevos datos mediante el grabador de tareas, cree nombres de pruebas que no entren en conflicto con nombres existentes (por ejemplo, utilice un prefijo como **RSATxxx**).</span><span class="sxs-lookup"><span data-stu-id="6bdf1-207">When you generate new data via Task recorder, create test names that won't conflict with existing names (for example, use a prefix such as **RSATxxx**).</span></span>
- <span data-ttu-id="6bdf1-208">Utilice la Restauración en un momento determinado de Azure para volver a ejecutar pruebas en entornos que no son del nivel 1.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-208">Use Azure Point-In-Time restore to rerun tests in non-Tier 1 environments.</span></span>
- <span data-ttu-id="6bdf1-209">Aunque puede utilizar las funciones de Excel **ALEATORIO** y **AHORA** para generar una combinación única, el esfuerzo es considerablemente elevado.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-209">Although you can use the **RANDOM** and **NOW** Excel functions to generate a unique combination, the effort is considerably high.</span></span> <span data-ttu-id="6bdf1-210">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-210">Here is an example.</span></span>

    ```
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a><span data-ttu-id="6bdf1-211">Grabador de tareas</span><span class="sxs-lookup"><span data-stu-id="6bdf1-211">Task recorder</span></span>

- <span data-ttu-id="6bdf1-212">Defina los escenarios antes de comenzar la grabación.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-212">Define scenarios before you start recording.</span></span> <span data-ttu-id="6bdf1-213">Un proyecto bien gestionado tiene escenarios de prueba predefinidos.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-213">A well-managed project has predefined test scenarios.</span></span> <span data-ttu-id="6bdf1-214">Para crear un caso de prueba, considere cómo de previsible es el resultado de esos escenarios de prueba.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-214">To build a test case, consider how predictable the outcome of those test scenarios is.</span></span>
- <span data-ttu-id="6bdf1-215">Divida las grabaciones si son realizadas por distintos roles, o si hay un tiempo de espera o un evento externo para el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-215">Split recordings if they are performed by different roles, or if there is waiting time or an external event before the next step.</span></span>
- <span data-ttu-id="6bdf1-216">Evite seleccionar valores en las listas.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-216">Avoid selecting values in lists.</span></span> <span data-ttu-id="6bdf1-217">En su lugar, utilice formatos de texto, como **FIFO**, **AudioRM** y **SiteWH**.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-217">Instead, use text formats, such as **FIFO**, **AudioRM**, and **SiteWH**.</span></span> <span data-ttu-id="6bdf1-218">Cuando seleccione de una lista, se graba la posición del valor de la lista, no el valor en sí.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-218">When you select in a list, the position of the value in the list is recorded, not the value itself.</span></span> <span data-ttu-id="6bdf1-219">Si los artículos se agregan a esa lista, el puesto de valor puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-219">If items are added to that list, the position of the value can change.</span></span> <span data-ttu-id="6bdf1-220">Por lo tanto, su grabación utilizará un parámetro diferente, y el resto del escenario podría verse afectado.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-220">Therefore, your recording will use a different parameter, and the rest of the scenario might be affected.</span></span>
- <span data-ttu-id="6bdf1-221">Piense en el comportamiento de varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-221">Think about multi-user behavior.</span></span> <span data-ttu-id="6bdf1-222">Por ejemplo, supongamos que su pedido de ventas recién creado no se seleccionará siempre automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-222">For example, don't assume that your newly created sales order will always be automatically selected.</span></span> <span data-ttu-id="6bdf1-223">En su lugar, utilice siempre el filtro para encontrar el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-223">Instead, always use the filter to find the correct order.</span></span>
- <span data-ttu-id="6bdf1-224">Utilice la función Copiar en el Grabador de tareas para guardar el nombre de un producto recién creado para que pueda usarse en casos de prueba encadenados.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-224">Use the Copy function in Task recorder to save the name of a newly created product so it can be used in chained test cases.</span></span>
- <span data-ttu-id="6bdf1-225">Use la función Validar en el Grabador de tareas para establecer los puntos de control que verifiquen que los pasos se han ejecutado correctamente.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-225">Use the Validate function in Task recorder to set checkpoints that verify that steps have been run correctly.</span></span>

### <a name="rsat"></a><span data-ttu-id="6bdf1-226">RSAT</span><span class="sxs-lookup"><span data-stu-id="6bdf1-226">RSAT</span></span>

- <span data-ttu-id="6bdf1-227">Para ejecutar la prueba en otra empresa, puede cambiar la empresa en la pestaña **General** del archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-227">To run the test in another company, you can change the company on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="6bdf1-228">Asegúrese de que la configuración y los datos estén disponibles en la empresa recién seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-228">Make sure that settings and data are available in the newly selected company.</span></span>
- <span data-ttu-id="6bdf1-229">Puede cambiar el usuario de la prueba en la pestaña **General** del archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-229">You can change the test user on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="6bdf1-230">Especifique el id. de correo electrónico del usuario que ejecutará el caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-230">Specify the email ID of the user who will run the test case.</span></span> <span data-ttu-id="6bdf1-231">De esta manera, el caso de prueba se puede ejecutar mediante los permisos de seguridad del usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-231">In this way, the test case can be run by using the security permissions of the specified user.</span></span>
- <span data-ttu-id="6bdf1-232">Para esperar antes de que se inicie la prueba, puede definir una pausa en la pestaña **General** del archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-232">To wait before the test is started, you can define a pause on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="6bdf1-233">Esta pausa se puede utilizar en un trabajo por lotes (por ejemplo, si un flujo de trabajo debe ejecutarse antes de que se realice el paso siguiente).</span><span class="sxs-lookup"><span data-stu-id="6bdf1-233">This pause can be used in a batch job (for example, if a workflow must be run before the next step can be performed.)</span></span>

## <a name="advanced-scripting"></a><span data-ttu-id="6bdf1-234">Secuencia de comandos avanzada</span><span class="sxs-lookup"><span data-stu-id="6bdf1-234">Advanced scripting</span></span>

### <a name="command-line"></a><span data-ttu-id="6bdf1-235">Línea de comandos</span><span class="sxs-lookup"><span data-stu-id="6bdf1-235">Command line</span></span>

<span data-ttu-id="6bdf1-236">RSAT se puede llamar desde una ventana **Símbolo del sistema**.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-236">RSAT can be called from a **Command Prompt** window.</span></span>

> [!NOTE]
> <span data-ttu-id="6bdf1-237">Verifique que la variable de entorno **TestRoot** está establecida en la ruta de instalación de RSAT.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-237">Verify that the **TestRoot** environment variable is set to the RSAT installation path.</span></span> <span data-ttu-id="6bdf1-238">(En Microsoft Windows, abra **Panel de control**, seleccione **Sistema y seguridad \> Sistema \> Configuración del sistema avanzado** y, a continuación, seleccione **Variables de entorno**).</span><span class="sxs-lookup"><span data-stu-id="6bdf1-238">(In Microsoft Windows, open **Control Panel**, select **System and Security \> System \> Advanced system settings**, and then select **Environment Variables**.)</span></span>

1. <span data-ttu-id="6bdf1-239">Abra una ventana **Símbolo del sistema** como administrador.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-239">Open a **Command Prompt** window as an admin.</span></span>
2. <span data-ttu-id="6bdf1-240">Ejecute la herramienta desde el directorio de instalación.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-240">Run the tool from the installation directory.</span></span>

    ```
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. <span data-ttu-id="6bdf1-241">Enumere todos los comandos.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-241">List all commands.</span></span>

    ```
    C:\Program Files (x86)\Regression Suite Automation Tool>Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe help

    Usage:
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe command
        or
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe /settings "C:\Path to\file.settings" command

    Available commands:
        list
        listtestsuite suite_name
        download test_case_id output_dir
        generate test_case_id output_dir
        generatederived parent_test_case_id test_plan_id test_suite_id
        generatetestonly test_case_id output_dir
        edit excel_file
        playback excel_file
        playbackmany excel_file1 [excel_file2 [.. excel_fileN]]
        playbackbyid test_case_id1 [test_case_id2 [.. test_case_idN]]
        playbacksuite suite_name
        clear
        help
        about
        quit
    ```

### <a name="windows-powershell-examples"></a><span data-ttu-id="6bdf1-242">Ejemplos de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6bdf1-242">Windows PowerShell examples</span></span>

#### <a name="run-a-test-case-in-a-loop"></a><span data-ttu-id="6bdf1-243">Ejecutar un caso de prueba en un bucle</span><span class="sxs-lookup"><span data-stu-id="6bdf1-243">Run a test case in a loop</span></span>

<span data-ttu-id="6bdf1-244">Tiene una secuencia de comandos de prueba que crea un nuevo cliente.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-244">You have a test script that creates a new customer.</span></span> <span data-ttu-id="6bdf1-245">Mediante la secuencia de comandos, este caso de prueba se puede ejecutar en un bucle aleatorizando los siguientes datos antes de que se ejecute cada iteración:</span><span class="sxs-lookup"><span data-stu-id="6bdf1-245">Via scripting, this test case can be run in a loop by randomizing the following data before each iteration is run:</span></span>

- <span data-ttu-id="6bdf1-246">Id. de cliente</span><span class="sxs-lookup"><span data-stu-id="6bdf1-246">Customer ID</span></span>
- <span data-ttu-id="6bdf1-247">Nombre de cliente</span><span class="sxs-lookup"><span data-stu-id="6bdf1-247">Customer name</span></span>
- <span data-ttu-id="6bdf1-248">Dirección del cliente</span><span class="sxs-lookup"><span data-stu-id="6bdf1-248">Customer address</span></span>

<span data-ttu-id="6bdf1-249">El id. del cliente tendrá el formato *ATCUS\<number\>*, donde \<number\> es un valor entre **000000001** y **999999999**.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-249">The customer ID will be in the format *ATCUS\<number\>*, where \<number\> is a value between **000000001** and **999999999**.</span></span>

<span data-ttu-id="6bdf1-250">El siguiente ejemplo utiliza un parámetro, **start**, para definir el primer número que se usa.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-250">The following example uses one parameter, **start**, to define the first number that is used.</span></span> <span data-ttu-id="6bdf1-251">Utiliza un segundo parámetro, **nr**, para definir el número de clientes que deben crearse.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-251">Is uses a second parameter, **nr**, to define the number of customers that must be created.</span></span> <span data-ttu-id="6bdf1-252">Para cada iteración, los parámetros en el archivo de parámetros de Excel se cambian mediante una función UpdateCustomer.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-252">For each iteration, the parameters in the Excel parameter file are changed by using an UpdateCustomer function.</span></span> <span data-ttu-id="6bdf1-253">A continuación, la línea de comandos de RSAT se llama en una función RunTestCase.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-253">Then the RSAT command line is called in a RunTestCase function.</span></span>

<span data-ttu-id="6bdf1-254">Abra el Entorno de scripting integrado (ISE) de Microsoft Windows PowerShell en modo de administración y pegue el siguiente código en la ventaja que se denomina **Untitled1.ps1**.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-254">Open Microsoft Windows PowerShell Integrated Scripting Environment (ISE) in admin mode, and paste the following code into the window that is named **Untitled1.ps1**.</span></span>

```
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

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a><span data-ttu-id="6bdf1-255">Ejecutar una secuencia de comandos que depende de los datos de Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="6bdf1-255">Run a script that depends on data in Microsoft Dynamics 365</span></span>

<span data-ttu-id="6bdf1-256">El siguiente ejemplo utiliza una llamada del protocolo abierto de datos (OData) para encontrar el estado del pedido de un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-256">The following example uses an Open Data Protocol (OData) call to find the order status of a purchase order.</span></span> <span data-ttu-id="6bdf1-257">Si el estado no se **factura**, puede, por ejemplo, llamar a un caso de prueba de RSAT que registra la factura.</span><span class="sxs-lookup"><span data-stu-id="6bdf1-257">If the status isn't **invoiced**, you can, for example, call an RSAT test case that posts the invoice.</span></span>

```
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
