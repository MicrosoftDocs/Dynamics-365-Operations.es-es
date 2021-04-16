---
title: Tutorial de Regression Suite Automation Tool
description: En este tema se muestra cómo usar la Regression Suite Automation Tool (RSAT). Describe varias características y proporciona ejemplos que emplean secuencias de comandos avanzados.
author: robinarh
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.custom: 21761
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 5a9f19168093f24a7f152b2b5b23b3728ca80222
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745174"
---
# <a name="regression-suite-automation-tool-tutorial"></a><span data-ttu-id="5f96e-104">Tutorial de Regression Suite Automation Tool</span><span class="sxs-lookup"><span data-stu-id="5f96e-104">Regression suite automation tool tutorial</span></span>

[!include [banner](../../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="5f96e-105">Utilice las herramientas del navegador de Internet para descargar y guardar esta página en formato pdf.</span><span class="sxs-lookup"><span data-stu-id="5f96e-105">Use your internet browser tools to download and save this page in pdf format.</span></span>

<span data-ttu-id="5f96e-106">Este tutorial le muestra algunas de las características avanzadas de la Regression Suite Automation Tool (RSAT), incluye una asignación de demostración y describe la estrategia y los puntos de aprendizaje clave.</span><span class="sxs-lookup"><span data-stu-id="5f96e-106">This tutorial walks through some of the advanced features of the Regression suite automation tool (RSAT), includes a demo assignment, and describes strategy and key learning points.</span></span>

## <a name="notable-features-of-rsat-and-task-recorder"></a><span data-ttu-id="5f96e-107">Características notables de RSAT y Grabador de tareas</span><span class="sxs-lookup"><span data-stu-id="5f96e-107">Notable Features of RSAT and Task recorder</span></span>

### <a name="validate-a-field-value"></a><span data-ttu-id="5f96e-108">Validar un valor del campo</span><span class="sxs-lookup"><span data-stu-id="5f96e-108">Validate a field value</span></span>

<span data-ttu-id="5f96e-109">RSAT le permite incluir pasos de validación dentro de su caso de prueba para validar los valores esperados.</span><span class="sxs-lookup"><span data-stu-id="5f96e-109">RSAT allows you to include validation steps within your test case to validate expected values.</span></span> <span data-ttu-id="5f96e-110">Para obtener información sobre esta característica, consulte el artículo [Validar valores esperados](rsat-validate-expected.md).</span><span class="sxs-lookup"><span data-stu-id="5f96e-110">For information about this feature, see the article [Validate expected values](rsat-validate-expected.md).</span></span>

<span data-ttu-id="5f96e-111">El siguiente ejemplo muestra cómo puede utilizar esta característica para validar si el inventario disponible es superior a 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="5f96e-111">The following example shows how you can use this feature to validate whether the on-hand inventory is more than 0 (zero).</span></span>

1. <span data-ttu-id="5f96e-112">En los datos de demostración en la empresa **USMF**, cree una grabación de tareas que tenga los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="5f96e-112">In the demo data in the **USMF** company, create a task recording that has the following steps:</span></span>

    1. <span data-ttu-id="5f96e-113">Vaya a **Gestión de información de productos \> Productos \> Productos emitidos**.</span><span class="sxs-lookup"><span data-stu-id="5f96e-113">Go to **Product information management \> Products \> Released products**.</span></span>
    2. <span data-ttu-id="5f96e-114">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="5f96e-114">Use the Quick Filter to find records.</span></span> <span data-ttu-id="5f96e-115">Por ejemplo, aplique un filtro de un valor de **1000** para el campo **Número de artículo**.</span><span class="sxs-lookup"><span data-stu-id="5f96e-115">For example, filter on a value of **1000** for the **Item number** field.</span></span>
    3. <span data-ttu-id="5f96e-116">Seleccione **Inventario disponible**.</span><span class="sxs-lookup"><span data-stu-id="5f96e-116">Select **On-hand inventory**.</span></span>
    4. <span data-ttu-id="5f96e-117">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="5f96e-117">Use the Quick Filter to find records.</span></span> <span data-ttu-id="5f96e-118">Por ejemplo, aplique un filtro de un valor de **1** para el campo **Sitio**.</span><span class="sxs-lookup"><span data-stu-id="5f96e-118">For example, filter on a value of **1** for the **Site** field.</span></span>
    5. <span data-ttu-id="5f96e-119">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="5f96e-119">In the list, mark the selected row.</span></span>
    6. <span data-ttu-id="5f96e-120">Valide que el valor del campo **Total disponible** es **411,0000000000000000**.</span><span class="sxs-lookup"><span data-stu-id="5f96e-120">Validate that the value of the **Total available** field is **411.0000000000000000**.</span></span>

2. <span data-ttu-id="5f96e-121">Guarde la grabación de la tarea como **archivo de grabación sin procesar** y adjúntela a su caso de prueba en Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="5f96e-121">Save the task recording as a **developer recording** and attach it to your test case in Azure Devops.</span></span>
3. <span data-ttu-id="5f96e-122">Agregue el caso de prueba al plan de pruebas, y cargue el caso de prueba en RSAT.</span><span class="sxs-lookup"><span data-stu-id="5f96e-122">Add the test case to the test plan, and load the test case into RSAT.</span></span>
4. <span data-ttu-id="5f96e-123">Abra el archivo de parámetros de Excel y vaya a la pestaña **TestCaseSteps**.</span><span class="sxs-lookup"><span data-stu-id="5f96e-123">Open the Excel parameter file and go to the **TestCaseSteps** tab.</span></span>
5. <span data-ttu-id="5f96e-124">Para validar si el inventario disponible siempre será más de **0**, vaya al paso **Validar total disponible** y cambie su valor de **411** a **0**.</span><span class="sxs-lookup"><span data-stu-id="5f96e-124">To validate whether the inventory on-hand will always be more than **0**, go to the **Validate Total Available** step and change its value from **411** to **0**.</span></span> <span data-ttu-id="5f96e-125">Cambie el valor del campo **Operador** de un signo igual (**=**) a un signo mayor que (**\>**).</span><span class="sxs-lookup"><span data-stu-id="5f96e-125">Change the value of the **Operator** field from an equal sign (**=**) to a greater than sign (**\>**).</span></span>
6. <span data-ttu-id="5f96e-126">Guarde y cierre el archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="5f96e-126">Save and close the Excel parameter file.</span></span>
7. <span data-ttu-id="5f96e-127">Seleccione **Cargar** para guardar los cambios realizados en el archivo de parámetros de Excel en Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="5f96e-127">Select **Upload** to save the changes that you made to the Excel parameter file to Azure DevOps.</span></span>

<span data-ttu-id="5f96e-128">Ahora, si es el valor del campo **Total disponible** para el artículo especificado en el inventario es superior a 0 (cero), las pruebas se aprobarán, independientemente del valor real del inventario disponible.</span><span class="sxs-lookup"><span data-stu-id="5f96e-128">Now, if the value of the **Total Available** field for the specified item in inventory is more than 0 (zero), tests will pass, regardless of the actual on-hand inventory value.</span></span>

### <a name="saved-variables-and-chaining-of-test-cases"></a><span data-ttu-id="5f96e-129">Variables guardadas y encadenamiento de casos de prueba</span><span class="sxs-lookup"><span data-stu-id="5f96e-129">Saved variables and chaining of test cases</span></span>

<span data-ttu-id="5f96e-130">Una característica clave de RSAT es el encadenamiento de casos de prueba, es decir, la capacidad de una prueba para transferir variables a otras pruebas.</span><span class="sxs-lookup"><span data-stu-id="5f96e-130">One of the key features of RSAT is the chaining of test cases, that is, the ability of a test to pass variables to other tests.</span></span> <span data-ttu-id="5f96e-131">Para más información, consulte el artículo [Copiar variables para encadenar casos de prueba](rsat-chain-test-cases.md).</span><span class="sxs-lookup"><span data-stu-id="5f96e-131">For more information, see the article [Copy variables to chain test cases](rsat-chain-test-cases.md).</span></span>

### <a name="derived-test-case"></a><span data-ttu-id="5f96e-132">Caso de prueba derivado</span><span class="sxs-lookup"><span data-stu-id="5f96e-132">Derived test case</span></span>

<span data-ttu-id="5f96e-133">RSAT le permite utilizar la misma grabación de tareas con múltiples casos de prueba, lo que permite que una tarea se ejecute con diferentes configuraciones de datos.</span><span class="sxs-lookup"><span data-stu-id="5f96e-133">RSAT lets you use the same task recording with multiple test cases, enabling a task to run with different data configurations.</span></span> <span data-ttu-id="5f96e-134">Para más información consulte el articulo [Casos de prueba derivados](rsat-derived-test-cases.md).</span><span class="sxs-lookup"><span data-stu-id="5f96e-134">See the article [Derived test cases](rsat-derived-test-cases.md) for more information.</span></span>

### <a name="validate-notifications-and-messages"></a><span data-ttu-id="5f96e-135">Validar notificaciones y mensajes</span><span class="sxs-lookup"><span data-stu-id="5f96e-135">Validate notifications and messages</span></span>

<span data-ttu-id="5f96e-136">Esta característica se puede utilizar para validar si se produjo una acción.</span><span class="sxs-lookup"><span data-stu-id="5f96e-136">This feature can be used to validate whether an action occurred.</span></span> <span data-ttu-id="5f96e-137">Por ejemplo, cuando se crea, estima y inicia una orden de producción, la aplicación muestra un mensaje "Producción – Inicio" para notificarle que se ha iniciado el pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="5f96e-137">For example, when a production order is created, estimated, and then started, the app shows a "Production – Start" message to notify you that the production order has been started.</span></span>

![Notificación Producción – Inicio](./media/use_rsa_tool_05.png)

<span data-ttu-id="5f96e-139">Puede validar este mensaje a través RSAT introduciendo el texto del mensaje en la pestaña **MessageValidation** del archivo de parámetros de Excel para la grabación adecuada.</span><span class="sxs-lookup"><span data-stu-id="5f96e-139">You can validate this message through RSAT by entering the message text on the **MessageValidation** tab of the Excel parameter file for the appropriate recording.</span></span>

![Pestaña Validación de mensaje](./media/use_rsa_tool_06.png)

<span data-ttu-id="5f96e-141">Una vez que se ejecute el caso de prueba, el mensaje del archivo de parámetros de Excel se compara con el mensaje que se muestra.</span><span class="sxs-lookup"><span data-stu-id="5f96e-141">After the test case is run, the message in the Excel parameter file is compared to the message that is shown.</span></span> <span data-ttu-id="5f96e-142">Si los mensajes no coinciden, el caso de prueba fallará.</span><span class="sxs-lookup"><span data-stu-id="5f96e-142">If the messages don't match, the test case will fail.</span></span>

> [!NOTE]
> <span data-ttu-id="5f96e-143">Puede introducir más de un mensaje en la pestaña **MessageValidation** en el archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="5f96e-143">You can enter more than one message on the **MessageValidation** tab in the Excel parameter file.</span></span> <span data-ttu-id="5f96e-144">Los mensajes también pueden ser de error o de advertencia en lugar de mensajes informativos.</span><span class="sxs-lookup"><span data-stu-id="5f96e-144">The messages also can be error or warning messages instead of informational messages.</span></span>

### <a name="snapshot"></a><span data-ttu-id="5f96e-145">Instantánea</span><span class="sxs-lookup"><span data-stu-id="5f96e-145">Snapshot</span></span>

<span data-ttu-id="5f96e-146">Esta característica realiza capturas de pantalla de los pasos que se realizaron durante la grabación de tareas.</span><span class="sxs-lookup"><span data-stu-id="5f96e-146">This feature takes screenshots of the steps that were performed during task recording.</span></span> <span data-ttu-id="5f96e-147">Es útil para fines de auditoría o depuración.</span><span class="sxs-lookup"><span data-stu-id="5f96e-147">It is useful for auditing or debugging purposes.</span></span>

- <span data-ttu-id="5f96e-148">Para utilizar esta característica, abra el archivo **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** en la carpeta de instalación de RSAT (por ejemplo, **C:\\Archivos de programa (x86)\\Regression Suite Automation Tool**) y cambie el valor del siguiente elemento de **falso** a **verdadero**.</span><span class="sxs-lookup"><span data-stu-id="5f96e-148">To use this feature, open the **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** file under the RSAT installation folder (for example, **C:\\Program Files (x86)\\Regression Suite Automation Tool**), and change the value of the following element from **false** to **true**.</span></span>

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

<span data-ttu-id="5f96e-149">Cuando ejecute el caso de prueba, RSAT generará instantáneas (imágenes) de los pasos en la carpeta de reproducción de los casos de prueba en el directorio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5f96e-149">When your run the test case, RSAT will generate snapshots (images) of the steps in the playback folder of the test cases in the working diretory.</span></span> <span data-ttu-id="5f96e-150">Si está utilizando una versión anterior de RSAT, las imágenes se guardan en **C:\\Usuarios\\\<Username\>\\AppData\\Roaming\\Herramienta de regresión\\reproducción** y se crea una carpeta separada para cada caso de prueba que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="5f96e-150">If you are using an older version of RSAT, the images are saved to **C:\\Users\\\<Username\>\\AppData\\Roaming\\regressionTool\\playback**, a separate folder is created for each test case that is run.</span></span>

## <a name="assignment"></a><span data-ttu-id="5f96e-151">Asignación</span><span class="sxs-lookup"><span data-stu-id="5f96e-151">Assignment</span></span>

### <a name="scenario"></a><span data-ttu-id="5f96e-152">Situación</span><span class="sxs-lookup"><span data-stu-id="5f96e-152">Scenario</span></span>

1. <span data-ttu-id="5f96e-153">El diseñador de productos crea un nuevo producto lanzado.</span><span class="sxs-lookup"><span data-stu-id="5f96e-153">The product designer creates a new released product.</span></span>
2. <span data-ttu-id="5f96e-154">El director de producción inicia una orden de producción para llevar el nivel de existencias a dos piezas.</span><span class="sxs-lookup"><span data-stu-id="5f96e-154">The production manager initiates a production order to bring the stock level to two pieces.</span></span>
3. <span data-ttu-id="5f96e-155">La fabricación comienza y termina con el pedido de producción, y verifica que la cantidad disponible es de dos piezas.</span><span class="sxs-lookup"><span data-stu-id="5f96e-155">Manufacturing starts and ends the production order, and verifies that the on-hand quantity is two pieces.</span></span>
4. <span data-ttu-id="5f96e-156">El equipo de ventas recibe un pedido para cuatro piezas del nuevo producto.</span><span class="sxs-lookup"><span data-stu-id="5f96e-156">The sales team receives an order for four pieces of the new product.</span></span> <span data-ttu-id="5f96e-157">Por lo tanto, el equipo de ventas actualia los requisitos netos a través del plan dinámico.</span><span class="sxs-lookup"><span data-stu-id="5f96e-157">Therefore, the sales team updates the net requirements via the dynamic plan.</span></span> <span data-ttu-id="5f96e-158">Puesto que no hay capacidad adicional disponible, la directiva de pedidos predeterminada se establece en "comprar en lugar de fabricar".</span><span class="sxs-lookup"><span data-stu-id="5f96e-158">Because no additional capacity is available, the default order policy is set to "buy instead of make."</span></span> <span data-ttu-id="5f96e-159">Por lo tanto, se crea un pedido de compra planificado.</span><span class="sxs-lookup"><span data-stu-id="5f96e-159">Therefore, a planned purchase order is created.</span></span>
5. <span data-ttu-id="5f96e-160">El comprador agrega un proveedor, consolida el pedido de compra planificado y, a continuación, confirma el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="5f96e-160">The buyer adds a vendor, firms the planned purchase order, and then confirms the purchase order.</span></span>
6. <span data-ttu-id="5f96e-161">Cuando las mercancías que se adquirieron llegan el almacén, el operador de almacén busca el pedido de compra relacionado y recibe las mercancías.</span><span class="sxs-lookup"><span data-stu-id="5f96e-161">When the goods that were purchased arrive at the store, the store operator searches the related purchase order and receives the goods.</span></span> <span data-ttu-id="5f96e-162">Puesto que el pedido está ahora completado, las mercancías se pueden seleccionar y empaquetar con el pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="5f96e-162">Because the order is now completed, goods can be picked and packed against the sales order.</span></span>
7. <span data-ttu-id="5f96e-163">Finance registra la factura de compra y la factura de ventas.</span><span class="sxs-lookup"><span data-stu-id="5f96e-163">Finance posts the purchase invoice and sales invoice.</span></span>

<span data-ttu-id="5f96e-164">En la ilustración siguiente se muestra el flujo para este escenario.</span><span class="sxs-lookup"><span data-stu-id="5f96e-164">The following illustration shows the flow for this scenario.</span></span>

![Flujo para el escenario de demostración](./media/use_rsa_tool_14.png)

<span data-ttu-id="5f96e-166">La siguiente ilustración muestra la jerarquía de procesos empresariales para este escenario en Modelador de procesos empresariales LCS.</span><span class="sxs-lookup"><span data-stu-id="5f96e-166">The following illustration shows the business processes hierarchy for this scenario in the LCS Business Process Modeler.</span></span>

![Procesos empresariales para el escenario de demostración](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a><span data-ttu-id="5f96e-168">Estrategia – Aprendizaje clave</span><span class="sxs-lookup"><span data-stu-id="5f96e-168">Strategy – Key learning</span></span>

### <a name="data"></a><span data-ttu-id="5f96e-169">Datos</span><span class="sxs-lookup"><span data-stu-id="5f96e-169">Data</span></span>

- <span data-ttu-id="5f96e-170">Asegúrese de que tiene volúmenes de datos representativos (una copia de los datos de configuración de producción/dorados más los datos migrados).</span><span class="sxs-lookup"><span data-stu-id="5f96e-170">Make sure that you have representative data volumes (a copy of production/golden configuration data plus migrated data).</span></span>
- <span data-ttu-id="5f96e-171">Cuando genere nuevos datos mediante el grabador de tareas, cree nombres de pruebas que no entren en conflicto con nombres existentes (por ejemplo, utilice un prefijo como **RSATxxx**).</span><span class="sxs-lookup"><span data-stu-id="5f96e-171">When you generate new data via Task recorder, create test names that won't conflict with existing names (for example, use a prefix such as **RSATxxx**).</span></span>
- <span data-ttu-id="5f96e-172">Utilice la Restauración en un momento determinado de Azure para volver a ejecutar pruebas en entornos que no son del nivel 1.</span><span class="sxs-lookup"><span data-stu-id="5f96e-172">Use Azure Point-In-Time restore to rerun tests in non-Tier 1 environments.</span></span>
- <span data-ttu-id="5f96e-173">Aunque puede utilizar las características de Excel **ALEATORIO** y **AHORA** para generar una combinación única, el esfuerzo es considerablemente elevado.</span><span class="sxs-lookup"><span data-stu-id="5f96e-173">Although you can use the **RANDOM** and **NOW** Excel functions to generate a unique combination, the effort is considerably high.</span></span> <span data-ttu-id="5f96e-174">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5f96e-174">Here is an example.</span></span>

    ```Excel
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a><span data-ttu-id="5f96e-175">Grabador de tareas</span><span class="sxs-lookup"><span data-stu-id="5f96e-175">Task recorder</span></span>

- <span data-ttu-id="5f96e-176">Defina los escenarios antes de comenzar la grabación.</span><span class="sxs-lookup"><span data-stu-id="5f96e-176">Define scenarios before you start recording.</span></span> <span data-ttu-id="5f96e-177">Un proyecto bien gestionado tiene escenarios de prueba predefinidos.</span><span class="sxs-lookup"><span data-stu-id="5f96e-177">A well-managed project has predefined test scenarios.</span></span> <span data-ttu-id="5f96e-178">Para crear un caso de prueba, considere cómo de previsible es el resultado de esos escenarios de prueba.</span><span class="sxs-lookup"><span data-stu-id="5f96e-178">To build a test case, consider how predictable the outcome of those test scenarios is.</span></span>
- <span data-ttu-id="5f96e-179">Divida las grabaciones si son realizadas por distintos roles, o si hay un tiempo de espera o un evento externo para el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="5f96e-179">Split recordings if they are performed by different roles, or if there is waiting time or an external event before the next step.</span></span>
- <span data-ttu-id="5f96e-180">Evite seleccionar valores en las listas.</span><span class="sxs-lookup"><span data-stu-id="5f96e-180">Avoid selecting values in lists.</span></span> <span data-ttu-id="5f96e-181">En su lugar, utilice formatos de texto, como **FIFO**, **AudioRM** y **SiteWH**.</span><span class="sxs-lookup"><span data-stu-id="5f96e-181">Instead, use text formats, such as **FIFO**, **AudioRM**, and **SiteWH**.</span></span> <span data-ttu-id="5f96e-182">Cuando seleccione de una lista, se graba la posición del valor de la lista, no el valor en sí.</span><span class="sxs-lookup"><span data-stu-id="5f96e-182">When you select in a list, the position of the value in the list is recorded, not the value itself.</span></span> <span data-ttu-id="5f96e-183">Si los artículos se agregan a esa lista, el puesto de valor puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="5f96e-183">If items are added to that list, the position of the value can change.</span></span> <span data-ttu-id="5f96e-184">Por lo tanto, su grabación utilizará un parámetro diferente, y el resto del escenario podría verse afectado.</span><span class="sxs-lookup"><span data-stu-id="5f96e-184">Therefore, your recording will use a different parameter, and the rest of the scenario might be affected.</span></span>
- <span data-ttu-id="5f96e-185">Piense en el comportamiento de varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="5f96e-185">Think about multi-user behavior.</span></span> <span data-ttu-id="5f96e-186">Por ejemplo, supongamos que su pedido de ventas recién creado no se seleccionará siempre automáticamente.</span><span class="sxs-lookup"><span data-stu-id="5f96e-186">For example, don't assume that your newly created sales order will always be automatically selected.</span></span> <span data-ttu-id="5f96e-187">En su lugar, utilice siempre el filtro para encontrar el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="5f96e-187">Instead, always use the filter to find the correct order.</span></span>
- <span data-ttu-id="5f96e-188">Utilice la característica Copiar en el Grabador de tareas para guardar el nombre de un producto recién creado para que pueda usarse en casos de prueba encadenados.</span><span class="sxs-lookup"><span data-stu-id="5f96e-188">Use the Copy function in Task recorder to save the name of a newly created product so it can be used in chained test cases.</span></span>
- <span data-ttu-id="5f96e-189">Use la característica Validar en el Grabador de tareas para establecer los puntos de control que verifiquen que los pasos se han ejecutado correctamente.</span><span class="sxs-lookup"><span data-stu-id="5f96e-189">Use the Validate function in Task recorder to set checkpoints that verify that steps have been run correctly.</span></span>

### <a name="rsat"></a><span data-ttu-id="5f96e-190">RSAT</span><span class="sxs-lookup"><span data-stu-id="5f96e-190">RSAT</span></span>

- <span data-ttu-id="5f96e-191">Para ejecutar la prueba en otra empresa, puede cambiar la empresa en la pestaña **General** del archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="5f96e-191">To run the test in another company, you can change the company on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="5f96e-192">Asegúrese de que la configuración y los datos estén disponibles en la empresa recién seleccionada.</span><span class="sxs-lookup"><span data-stu-id="5f96e-192">Make sure that settings and data are available in the newly selected company.</span></span>
- <span data-ttu-id="5f96e-193">Puede cambiar el usuario de la prueba en la pestaña **General** del archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="5f96e-193">You can change the test user on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="5f96e-194">Especifique el id. de correo electrónico del usuario que ejecutará el caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="5f96e-194">Specify the email ID of the user who will run the test case.</span></span> <span data-ttu-id="5f96e-195">De esta manera, el caso de prueba se puede ejecutar mediante los permisos de seguridad del usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="5f96e-195">In this way, the test case can be run by using the security permissions of the specified user.</span></span>
- <span data-ttu-id="5f96e-196">Para esperar antes de que se inicie la prueba, puede definir una pausa en la pestaña **General** del archivo de parámetros de Excel.</span><span class="sxs-lookup"><span data-stu-id="5f96e-196">To wait before the test is started, you can define a pause on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="5f96e-197">Esta pausa se puede utilizar en un trabajo por lotes (por ejemplo, si un flujo de trabajo debe ejecutarse antes de que se realice el paso siguiente).</span><span class="sxs-lookup"><span data-stu-id="5f96e-197">This pause can be used in a batch job (for example, if a workflow must be run before the next step can be performed.)</span></span>

## <a name="advanced-scripting"></a><span data-ttu-id="5f96e-198">Secuencia de comandos avanzada</span><span class="sxs-lookup"><span data-stu-id="5f96e-198">Advanced scripting</span></span>

### <a name="cli"></a><span data-ttu-id="5f96e-199">CLI</span><span class="sxs-lookup"><span data-stu-id="5f96e-199">CLI</span></span>

<span data-ttu-id="5f96e-200">RSAT se puede llamar desde una ventana del **Símbolo del sistema** o **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="5f96e-200">RSAT can be called from a **Command Prompt** or **PowerShell** window.</span></span>

> [!NOTE]
> <span data-ttu-id="5f96e-201">Verifique que la variable de entorno **TestRoot** está establecida en la ruta de instalación de RSAT.</span><span class="sxs-lookup"><span data-stu-id="5f96e-201">Verify that the **TestRoot** environment variable is set to the RSAT installation path.</span></span> <span data-ttu-id="5f96e-202">(En Microsoft Windows, abra **Panel de control**, seleccione **Sistema y seguridad \> Sistema \> Configuración del sistema avanzado** y, a continuación, seleccione **Variables de entorno**).</span><span class="sxs-lookup"><span data-stu-id="5f96e-202">(In Microsoft Windows, open **Control Panel**, select **System and Security \> System \> Advanced system settings**, and then select **Environment Variables**.)</span></span>

1. <span data-ttu-id="5f96e-203">Abra una ventana **Símbolo del sistema** o **PowerShell** como administrador.</span><span class="sxs-lookup"><span data-stu-id="5f96e-203">Open a **Command Prompt** or **PowerShell** window as an admin.</span></span>
2. <span data-ttu-id="5f96e-204">Navegue al directorio de instalación de RSAT.</span><span class="sxs-lookup"><span data-stu-id="5f96e-204">Navigate to the RSAT installation directory.</span></span>

    ```Console
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. <span data-ttu-id="5f96e-205">Enumere todos los comandos.</span><span class="sxs-lookup"><span data-stu-id="5f96e-205">List all commands.</span></span>

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

#### <a name=""></a><span data-ttu-id="5f96e-206">?</span><span class="sxs-lookup"><span data-stu-id="5f96e-206">?</span></span>

<span data-ttu-id="5f96e-207">Muestra ayuda sobre todos los comandos disponibles y sus parámetros.</span><span class="sxs-lookup"><span data-stu-id="5f96e-207">Shows help about all available commands and their parameters.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="-optional-parameters"></a><span data-ttu-id="5f96e-208">?: parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="5f96e-208">?: Optional parameters</span></span>

<span data-ttu-id="5f96e-209">`command`; donde ``[command]`` es uno de los comandos especificados a continuación.</span><span class="sxs-lookup"><span data-stu-id="5f96e-209">`command`: Where ``[command]`` is one of the commands specified below.</span></span>

#### <a name="about"></a><span data-ttu-id="5f96e-210">acerca de</span><span class="sxs-lookup"><span data-stu-id="5f96e-210">about</span></span>

<span data-ttu-id="5f96e-211">Muestra la versión actual.</span><span class="sxs-lookup"><span data-stu-id="5f96e-211">Displays the current version.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a><span data-ttu-id="5f96e-212">cls</span><span class="sxs-lookup"><span data-stu-id="5f96e-212">cls</span></span>

<span data-ttu-id="5f96e-213">Borra la pantalla.</span><span class="sxs-lookup"><span data-stu-id="5f96e-213">Clears the screen.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**

#### <a name="download"></a><span data-ttu-id="5f96e-214">descargar</span><span class="sxs-lookup"><span data-stu-id="5f96e-214">download</span></span>

<span data-ttu-id="5f96e-215">Descarga archivos adjuntos para el caso de prueba especificado en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="5f96e-215">Downloads attachments for the specified test case to the output directory.</span></span>
<span data-ttu-id="5f96e-216">Puede usar el comando ``list`` para obtener todos los casos de prueba disponibles.</span><span class="sxs-lookup"><span data-stu-id="5f96e-216">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="5f96e-217">Use cualquier valor de la primera columna como parámetro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="5f96e-217">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[test_case_id] [output_dir]``

##### <a name="download-required-parameters"></a><span data-ttu-id="5f96e-218">descargar: parámetros requeridos</span><span class="sxs-lookup"><span data-stu-id="5f96e-218">download: required parameters</span></span>

+ <span data-ttu-id="5f96e-219">`test_case_id`: representa la identificación del caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="5f96e-219">`test_case_id`: Represents the test case ID.</span></span>
+ <span data-ttu-id="5f96e-220">`output_dir`: representa el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="5f96e-220">`output_dir`: Represents the output directory.</span></span> <span data-ttu-id="5f96e-221">El directorio debe existir.</span><span class="sxs-lookup"><span data-stu-id="5f96e-221">The directory must exist.</span></span>

##### <a name="download-examples"></a><span data-ttu-id="5f96e-222">descargar: ejemplos</span><span class="sxs-lookup"><span data-stu-id="5f96e-222">download: examples</span></span>

`download 123 c:\temp\rsat`

`download 765 c:\rsat\last`

#### <a name="edit"></a><span data-ttu-id="5f96e-223">editar</span><span class="sxs-lookup"><span data-stu-id="5f96e-223">edit</span></span>

<span data-ttu-id="5f96e-224">Le permite abrir el archivo de parámetros en el programa Excel y editarlo.</span><span class="sxs-lookup"><span data-stu-id="5f96e-224">Allows you to open parameters file in Excel program and edit it.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="edit-required-parameters"></a><span data-ttu-id="5f96e-225">editar: parámetros necesarios</span><span class="sxs-lookup"><span data-stu-id="5f96e-225">edit: required parameters</span></span>

+ <span data-ttu-id="5f96e-226">`excel_file`: debe contener una ruta completa a un archivo Excel existente.</span><span class="sxs-lookup"><span data-stu-id="5f96e-226">`excel_file`: Must contain a full path to an existing Excel file.</span></span>

##### <a name="edit-examples"></a><span data-ttu-id="5f96e-227">editar: ejemplos</span><span class="sxs-lookup"><span data-stu-id="5f96e-227">edit: examples</span></span>

`edit c:\RSAT\TestCase_123_Base.xlsx`

`edit e:\temp\TestCase_456_Base.xlsx`

#### <a name="generate"></a><span data-ttu-id="5f96e-228">generar</span><span class="sxs-lookup"><span data-stu-id="5f96e-228">generate</span></span>

<span data-ttu-id="5f96e-229">Genera archivos de ejecución y parámetros de prueba para el caso de prueba especificado en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="5f96e-229">Generates test execution and parameter files for the specified test case in the output directory.</span></span> <span data-ttu-id="5f96e-230">Puede usar el comando ``list`` para obtener todos los casos de prueba disponibles.</span><span class="sxs-lookup"><span data-stu-id="5f96e-230">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="5f96e-231">Use cualquier valor de la primera columna como parámetro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="5f96e-231">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[test_case_id] [output_dir]``

##### <a name="generate-required-parameters"></a><span data-ttu-id="5f96e-232">generar: parámetros requeridos</span><span class="sxs-lookup"><span data-stu-id="5f96e-232">generate: required parameters</span></span>

+ <span data-ttu-id="5f96e-233">`test_case_id`: representa la identificación del caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="5f96e-233">`test_case_id`: Represents the test case ID.</span></span>
+ <span data-ttu-id="5f96e-234">`output_dir`: representa el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="5f96e-234">`output_dir`: Represents the output directory.</span></span> <span data-ttu-id="5f96e-235">El directorio debe existir.</span><span class="sxs-lookup"><span data-stu-id="5f96e-235">The directory must exist.</span></span>

##### <a name="generate-examples"></a><span data-ttu-id="5f96e-236">generar: ejemplos</span><span class="sxs-lookup"><span data-stu-id="5f96e-236">generate: examples</span></span>

`generate 123 c:\temp\rsat`

`generate 765 c:\rsat\last`

#### <a name="generatederived"></a><span data-ttu-id="5f96e-237">generatederived</span><span class="sxs-lookup"><span data-stu-id="5f96e-237">generatederived</span></span>

<span data-ttu-id="5f96e-238">Genera un nuevo caso de prueba, derivado del caso de prueba proporcionado.</span><span class="sxs-lookup"><span data-stu-id="5f96e-238">Generates a new test case, derived from the provided test case.</span></span> <span data-ttu-id="5f96e-239">Puede usar el comando ``list`` para obtener todos los casos de prueba disponibles.</span><span class="sxs-lookup"><span data-stu-id="5f96e-239">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="5f96e-240">Use cualquier valor de la primera columna como parámetro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="5f96e-240">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="generatederived-required-parameters"></a><span data-ttu-id="5f96e-241">generatederived: parámetros requeridos</span><span class="sxs-lookup"><span data-stu-id="5f96e-241">generatederived: required parameters</span></span>

+ <span data-ttu-id="5f96e-242">`parent_test_case_id`: representa la identificación del caso de prueba primario.</span><span class="sxs-lookup"><span data-stu-id="5f96e-242">`parent_test_case_id`: Represents the parent test case ID.</span></span>
+ <span data-ttu-id="5f96e-243">`test_plan_id`: representa la identificación del plan de prueba.</span><span class="sxs-lookup"><span data-stu-id="5f96e-243">`test_plan_id`: Represents the test plan ID.</span></span>
+ <span data-ttu-id="5f96e-244">`test_suite_id`: representa la identificación del conjunto de prueba.</span><span class="sxs-lookup"><span data-stu-id="5f96e-244">`test_suite_id`: Represents the test suite ID.</span></span>

##### <a name="generatederived-examples"></a><span data-ttu-id="5f96e-245">generatederived: ejemplos</span><span class="sxs-lookup"><span data-stu-id="5f96e-245">generatederived: examples</span></span>

`generatederived 123 8901 678`

#### <a name="generatetestonly"></a><span data-ttu-id="5f96e-246">generatetestonly</span><span class="sxs-lookup"><span data-stu-id="5f96e-246">generatetestonly</span></span>

<span data-ttu-id="5f96e-247">Genera solo el archivo de ejecución de prueba para el caso de prueba especificado en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="5f96e-247">Generates only test execution file for the specified test case in the output directory.</span></span> <span data-ttu-id="5f96e-248">Puede usar el comando ``list`` para obtener todos los casos de prueba disponibles.</span><span class="sxs-lookup"><span data-stu-id="5f96e-248">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="5f96e-249">Use cualquier valor de la primera columna como parámetro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="5f96e-249">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[test_case_id] [output_dir]``

##### <a name="generatetestonly-required-parameters"></a><span data-ttu-id="5f96e-250">generatetestonly: parámetros requeridos</span><span class="sxs-lookup"><span data-stu-id="5f96e-250">generatetestonly: required parameters</span></span>

+ <span data-ttu-id="5f96e-251">`test_case_id`: representa la identificación del caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="5f96e-251">`test_case_id`: Represents the test case ID.</span></span>
+ <span data-ttu-id="5f96e-252">`output_dir`: representa el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="5f96e-252">`output_dir`: Represents the output directory.</span></span> <span data-ttu-id="5f96e-253">El directorio debe existir.</span><span class="sxs-lookup"><span data-stu-id="5f96e-253">The directory must exist.</span></span>

##### <a name="generatetestonly-examples"></a><span data-ttu-id="5f96e-254">generatetestonly: ejemplos</span><span class="sxs-lookup"><span data-stu-id="5f96e-254">generatetestonly: examples</span></span>

`generatetestonly 123 c:\temp\rsat`

`generatetestonly 765 c:\rsat\last`

#### <a name="generatetestsuite"></a><span data-ttu-id="5f96e-255">generatetestsuite</span><span class="sxs-lookup"><span data-stu-id="5f96e-255">generatetestsuite</span></span>

<span data-ttu-id="5f96e-256">Genera todos los casos de prueba para el conjunto especificado en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="5f96e-256">Generates all test cases for the specified suite in the output directory.</span></span> <span data-ttu-id="5f96e-257">Puede usar el comando ``listtestsuitenames`` para obtener todos los conjuntos de prueba disponibles.</span><span class="sxs-lookup"><span data-stu-id="5f96e-257">You can use ``listtestsuitenames`` command to get all available test suits.</span></span> <span data-ttu-id="5f96e-258">Use cualquier valor de la primera columna como parámetro **test_suite_name**.</span><span class="sxs-lookup"><span data-stu-id="5f96e-258">Use any value from the column as a **test_suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[test_suite_name] [output_dir]``

##### <a name="generatetestsuite-required-parameters"></a><span data-ttu-id="5f96e-259">generatetestsuite: parámetros requeridos</span><span class="sxs-lookup"><span data-stu-id="5f96e-259">generatetestsuite: required parameters</span></span>

+ <span data-ttu-id="5f96e-260">`test_suite_name`: representa el nombre del conjunto de prueba.</span><span class="sxs-lookup"><span data-stu-id="5f96e-260">`test_suite_name`: Represents the test suite name.</span></span>
+ <span data-ttu-id="5f96e-261">`output_dir`: representa el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="5f96e-261">`output_dir`: Represents the output directory.</span></span> <span data-ttu-id="5f96e-262">El directorio debe existir.</span><span class="sxs-lookup"><span data-stu-id="5f96e-262">The directory must exist.</span></span>

##### <a name="generatetestsuite-examples"></a><span data-ttu-id="5f96e-263">generatetestsuite: ejemplos</span><span class="sxs-lookup"><span data-stu-id="5f96e-263">generatetestsuite: examples</span></span>

`generatetestsuite Tests c:\temp\rsat`

`generatetestsuite Purchase c:\rsat\last`

#### <a name="help"></a><span data-ttu-id="5f96e-264">ayuda</span><span class="sxs-lookup"><span data-stu-id="5f96e-264">help</span></span>

<span data-ttu-id="5f96e-265">Idéntico a [?](#section)</span><span class="sxs-lookup"><span data-stu-id="5f96e-265">Identical to the [?](#section)</span></span> <span data-ttu-id="5f96e-266">comando.</span><span class="sxs-lookup"><span data-stu-id="5f96e-266">command.</span></span>

#### <a name="list"></a><span data-ttu-id="5f96e-267">lista</span><span class="sxs-lookup"><span data-stu-id="5f96e-267">list</span></span>

<span data-ttu-id="5f96e-268">Enumera todos los casos de prueba disponibles.</span><span class="sxs-lookup"><span data-stu-id="5f96e-268">Lists all available test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**

#### <a name="listtestplans"></a><span data-ttu-id="5f96e-269">listtestplans</span><span class="sxs-lookup"><span data-stu-id="5f96e-269">listtestplans</span></span>

<span data-ttu-id="5f96e-270">Enumera todos los planes de prueba disponibles.</span><span class="sxs-lookup"><span data-stu-id="5f96e-270">Lists all available test plans.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**

#### <a name="listtestsuite"></a><span data-ttu-id="5f96e-271">listtestsuite</span><span class="sxs-lookup"><span data-stu-id="5f96e-271">listtestsuite</span></span>

<span data-ttu-id="5f96e-272">Enumera casos de prueba para el conjunto de pruebas especificado.</span><span class="sxs-lookup"><span data-stu-id="5f96e-272">Lists test cases for the specified test suite.</span></span> <span data-ttu-id="5f96e-273">Puede usar el comando ``listtestsuitenames`` para obtener todos los conjuntos de prueba disponibles.</span><span class="sxs-lookup"><span data-stu-id="5f96e-273">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="5f96e-274">Use cualquier valor de la primera columna como parámetro **test_suite_name**.</span><span class="sxs-lookup"><span data-stu-id="5f96e-274">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[suite_name]``

##### <a name="listtestsuite-required-parameters"></a><span data-ttu-id="5f96e-275">listtestsuite: parámetros requeridos</span><span class="sxs-lookup"><span data-stu-id="5f96e-275">listtestsuite: required parameters</span></span>

+ <span data-ttu-id="5f96e-276">`suite_name`: nombre del conjunto deseado.</span><span class="sxs-lookup"><span data-stu-id="5f96e-276">`suite_name`: Name of the desired suite.</span></span>

##### <a name="listtestsuite-examples"></a><span data-ttu-id="5f96e-277">listtestsuite: ejemplos</span><span class="sxs-lookup"><span data-stu-id="5f96e-277">listtestsuite: examples</span></span>

`listtestsuite "sample suite name"`

`listtestsuite NameOfTheSuite`

#### <a name="listtestsuitenames"></a><span data-ttu-id="5f96e-278">listtestsuitenames</span><span class="sxs-lookup"><span data-stu-id="5f96e-278">listtestsuitenames</span></span>

<span data-ttu-id="5f96e-279">Enumera todos los conjuntos de prueba disponibles.</span><span class="sxs-lookup"><span data-stu-id="5f96e-279">Lists all available test suites.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**

#### <a name="playback"></a><span data-ttu-id="5f96e-280">reproducción</span><span class="sxs-lookup"><span data-stu-id="5f96e-280">playback</span></span>

<span data-ttu-id="5f96e-281">Reproduce un caso de prueba usando un archivo Excel.</span><span class="sxs-lookup"><span data-stu-id="5f96e-281">Plays back a test case using an Excel file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[excel_file]``

##### <a name="playback-required-parameters"></a><span data-ttu-id="5f96e-282">playback: parámetros requeridos</span><span class="sxs-lookup"><span data-stu-id="5f96e-282">playback: required parameters</span></span>

+ <span data-ttu-id="5f96e-283">`excel_file`: una ruta completa al archivo Excel.</span><span class="sxs-lookup"><span data-stu-id="5f96e-283">`excel_file`: A full path to the Excel file.</span></span> <span data-ttu-id="5f96e-284">El archivo debe existir.</span><span class="sxs-lookup"><span data-stu-id="5f96e-284">File must exist.</span></span>

##### <a name="playback-examples"></a><span data-ttu-id="5f96e-285">playback: ejemplos</span><span class="sxs-lookup"><span data-stu-id="5f96e-285">playback: examples</span></span>

`playback c:\RSAT\TestCaseParameters\sample1.xlsx`

`playback e:\temp\test.xlsx`

#### <a name="playbackbyid"></a><span data-ttu-id="5f96e-286">playbackbyid</span><span class="sxs-lookup"><span data-stu-id="5f96e-286">playbackbyid</span></span>

<span data-ttu-id="5f96e-287">Reproduce múltiples casos de prueba a la vez.</span><span class="sxs-lookup"><span data-stu-id="5f96e-287">Plays back multiple test cases at once.</span></span> <span data-ttu-id="5f96e-288">Puede usar el comando ``list`` para obtener todos los casos de prueba disponibles.</span><span class="sxs-lookup"><span data-stu-id="5f96e-288">You can use the ``list`` command to get all available test cases.</span></span> <span data-ttu-id="5f96e-289">Use cualquier valor de la primera columna como parámetro **test_case_id**.</span><span class="sxs-lookup"><span data-stu-id="5f96e-289">Use any value from the first column as a **test_case_id** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="playbackbyid-required-parameters"></a><span data-ttu-id="5f96e-290">playbackbyid: parámetros requeridos</span><span class="sxs-lookup"><span data-stu-id="5f96e-290">playbackbyid: required parameters</span></span>

+ <span data-ttu-id="5f96e-291">`test_case_id1`: identificación del caso de prueba existente.</span><span class="sxs-lookup"><span data-stu-id="5f96e-291">`test_case_id1`: ID of exisiting test case.</span></span>
+ <span data-ttu-id="5f96e-292">`test_case_id2`: identificación del caso de prueba existente.</span><span class="sxs-lookup"><span data-stu-id="5f96e-292">`test_case_id2`: ID of exisiting test case.</span></span>
+ <span data-ttu-id="5f96e-293">`test_case_idN`: identificación del caso de prueba existente.</span><span class="sxs-lookup"><span data-stu-id="5f96e-293">`test_case_idN`: ID of exisiting test case.</span></span>

##### <a name="playbackbyid-examples"></a><span data-ttu-id="5f96e-294">playbackbyid: ejemplos</span><span class="sxs-lookup"><span data-stu-id="5f96e-294">playbackbyid: examples</span></span>

`playbackbyid 878`

`playbackbyid 2345 667 135`

#### <a name="playbackmany"></a><span data-ttu-id="5f96e-295">playbackmany</span><span class="sxs-lookup"><span data-stu-id="5f96e-295">playbackmany</span></span>

<span data-ttu-id="5f96e-296">Reproduce muchos casos de prueba a la vez, utilizando archivos de Excel.</span><span class="sxs-lookup"><span data-stu-id="5f96e-296">Plays back many test cases at once, using Excel files.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[excel_file1] [excel_file2] ... [excel_fileN]``

##### <a name="playbackmany-required-parameters"></a><span data-ttu-id="5f96e-297">playbackmany: parámetros requeridos</span><span class="sxs-lookup"><span data-stu-id="5f96e-297">playbackmany: required parameters</span></span>

+ <span data-ttu-id="5f96e-298">`excel_file1`: ruta completa al archivo Excel.</span><span class="sxs-lookup"><span data-stu-id="5f96e-298">`excel_file1`: Full path to the Excel file.</span></span> <span data-ttu-id="5f96e-299">El archivo debe existir.</span><span class="sxs-lookup"><span data-stu-id="5f96e-299">File must exist.</span></span>
+ <span data-ttu-id="5f96e-300">`excel_file2`: ruta completa al archivo Excel.</span><span class="sxs-lookup"><span data-stu-id="5f96e-300">`excel_file2`: Full path to the Excel file.</span></span> <span data-ttu-id="5f96e-301">El archivo debe existir.</span><span class="sxs-lookup"><span data-stu-id="5f96e-301">File must exist.</span></span>
+ <span data-ttu-id="5f96e-302">`excel_fileN`: ruta completa al archivo Excel.</span><span class="sxs-lookup"><span data-stu-id="5f96e-302">`excel_fileN`: Full path to the Excel file.</span></span> <span data-ttu-id="5f96e-303">El archivo debe existir.</span><span class="sxs-lookup"><span data-stu-id="5f96e-303">File must exist.</span></span>

##### <a name="playbackmany-examples"></a><span data-ttu-id="5f96e-304">playbackmany: ejemplos</span><span class="sxs-lookup"><span data-stu-id="5f96e-304">playbackmany: examples</span></span>

`playbackmany c:\RSAT\TestCaseParameters\param1.xlsx`

`playbackmany e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx`

#### <a name="playbacksuite"></a><span data-ttu-id="5f96e-305">playbacksuite</span><span class="sxs-lookup"><span data-stu-id="5f96e-305">playbacksuite</span></span>

<span data-ttu-id="5f96e-306">Reproduce todos los casos de prueba del conjunto de pruebas especificado.</span><span class="sxs-lookup"><span data-stu-id="5f96e-306">Plays back all test cases from the specified test suite.</span></span>
<span data-ttu-id="5f96e-307">Puede usar el comando ``listtestsuitenames`` para obtener todos los conjuntos de prueba disponibles.</span><span class="sxs-lookup"><span data-stu-id="5f96e-307">You can use ``listtestsuitenames`` command to get all available test suites.</span></span> <span data-ttu-id="5f96e-308">Use cualquier valor de la primera columna como parámetro **test_suite_name**.</span><span class="sxs-lookup"><span data-stu-id="5f96e-308">Use any value from first column as **suite_name** parameter.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[suite_name]``

##### <a name="playbacksuite-required-parameters"></a><span data-ttu-id="5f96e-309">playbacksuite: parámetros requeridos</span><span class="sxs-lookup"><span data-stu-id="5f96e-309">playbacksuite: required parameters</span></span>

+ <span data-ttu-id="5f96e-310">`suite_name`: nombre del conjunto deseado.</span><span class="sxs-lookup"><span data-stu-id="5f96e-310">`suite_name`: Name of the desired suite.</span></span>

##### <a name="playbacksuite-examples"></a><span data-ttu-id="5f96e-311">playbacksuite: ejemplos</span><span class="sxs-lookup"><span data-stu-id="5f96e-311">playbacksuite: examples</span></span>

`playbacksuite suiteName`

`playbacksuite sample_suite`

#### <a name="quit"></a><span data-ttu-id="5f96e-312">quit</span><span class="sxs-lookup"><span data-stu-id="5f96e-312">quit</span></span>

<span data-ttu-id="5f96e-313">Cierra la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5f96e-313">Closes the  application.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**

#### <a name="upload"></a><span data-ttu-id="5f96e-314">upload</span><span class="sxs-lookup"><span data-stu-id="5f96e-314">upload</span></span>

<span data-ttu-id="5f96e-315">Carga todos los archivos que pertenecen al conjunto de pruebas o casos de prueba especificados.</span><span class="sxs-lookup"><span data-stu-id="5f96e-315">Uploads all files belonging to the specified test suite or test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``[suite_name] [testcase_id]``

#### <a name="upload-required-parameters"></a><span data-ttu-id="5f96e-316">upload: parámetros requeridos</span><span class="sxs-lookup"><span data-stu-id="5f96e-316">upload: required parameters</span></span>

+ <span data-ttu-id="5f96e-317">`suite_name`: carga todos los archivos que pertenecen al conjunto de pruebas especificado.</span><span class="sxs-lookup"><span data-stu-id="5f96e-317">`suite_name`: All files belonging to the specified test suite will be uploaded.</span></span>
+ <span data-ttu-id="5f96e-318">`testcase_id`: carga todos los archivos que pertenecen al conjunto (o conjuntos) de pruebas especificado(s).</span><span class="sxs-lookup"><span data-stu-id="5f96e-318">`testcase_id`: All files beloning to the specified test case(s) will be uploaded.</span></span>

##### <a name="upload-examples"></a><span data-ttu-id="5f96e-319">upload: ejemplos</span><span class="sxs-lookup"><span data-stu-id="5f96e-319">upload: examples</span></span>

`upload sample_suite`

`upload 123`

`upload 123 456`

#### <a name="uploadrecording"></a><span data-ttu-id="5f96e-320">uploadrecording</span><span class="sxs-lookup"><span data-stu-id="5f96e-320">uploadrecording</span></span>

<span data-ttu-id="5f96e-321">Carga solo el archivo de grabación que pertenece a los casos de prueba especificados.</span><span class="sxs-lookup"><span data-stu-id="5f96e-321">Uploads only recording file belonging to the specified test cases.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[testcase_id]``

##### <a name="uploadrecording-required-parameters"></a><span data-ttu-id="5f96e-322">uploadrecording: parámetros requeridos</span><span class="sxs-lookup"><span data-stu-id="5f96e-322">uploadrecording: required parameters</span></span>

+ <span data-ttu-id="5f96e-323">`testcase_id`: cargará el archivo de grabación que pertenece a los casos de prueba especificados.</span><span class="sxs-lookup"><span data-stu-id="5f96e-323">`testcase_id`: Recording file belonging to the specified test cases will be uploaded.</span></span>

##### <a name="uploadrecording-examples"></a><span data-ttu-id="5f96e-324">uploadrecording: ejemplos</span><span class="sxs-lookup"><span data-stu-id="5f96e-324">uploadrecording: examples</span></span>

`uploadrecording 123`

`uploadrecording 123 456`

#### <a name="usage"></a><span data-ttu-id="5f96e-325">usage</span><span class="sxs-lookup"><span data-stu-id="5f96e-325">usage</span></span>

<span data-ttu-id="5f96e-326">Muestra dos formas de invocar esta aplicación: una con un archivo de configuración predeterminado y otra con un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="5f96e-326">Shows two ways to invoke this application: one using a default setting file, another one providing a setting file.</span></span>

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**

### <a name="windows-powershell-examples"></a><span data-ttu-id="5f96e-327">Ejemplos de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f96e-327">Windows PowerShell examples</span></span>

#### <a name="run-a-test-case-in-a-loop"></a><span data-ttu-id="5f96e-328">Ejecutar un caso de prueba en un bucle</span><span class="sxs-lookup"><span data-stu-id="5f96e-328">Run a test case in a loop</span></span>

<span data-ttu-id="5f96e-329">Tiene una secuencia de comandos de prueba que crea un nuevo cliente.</span><span class="sxs-lookup"><span data-stu-id="5f96e-329">You have a test script that creates a new customer.</span></span> <span data-ttu-id="5f96e-330">Mediante la secuencia de comandos, este caso de prueba se puede ejecutar en un bucle aleatorizando los siguientes datos antes de que se ejecute cada iteración:</span><span class="sxs-lookup"><span data-stu-id="5f96e-330">Via scripting, this test case can be run in a loop by randomizing the following data before each iteration is run:</span></span>

- <span data-ttu-id="5f96e-331">Id. de cliente</span><span class="sxs-lookup"><span data-stu-id="5f96e-331">Customer ID</span></span>
- <span data-ttu-id="5f96e-332">Nombre de cliente</span><span class="sxs-lookup"><span data-stu-id="5f96e-332">Customer name</span></span>
- <span data-ttu-id="5f96e-333">Dirección del cliente</span><span class="sxs-lookup"><span data-stu-id="5f96e-333">Customer address</span></span>

<span data-ttu-id="5f96e-334">El id. del cliente tendrá el formato *ATCUS\<number\>*, donde \<number\> es un valor entre **000000001** y **999999999**.</span><span class="sxs-lookup"><span data-stu-id="5f96e-334">The customer ID will be in the format *ATCUS\<number\>*, where \<number\> is a value between **000000001** and **999999999**.</span></span>

<span data-ttu-id="5f96e-335">El siguiente ejemplo utiliza un parámetro, **start**, para definir el primer número que se usa.</span><span class="sxs-lookup"><span data-stu-id="5f96e-335">The following example uses one parameter, **start**, to define the first number that is used.</span></span> <span data-ttu-id="5f96e-336">Utiliza un segundo parámetro, **nr**, para definir el número de clientes que deben crearse.</span><span class="sxs-lookup"><span data-stu-id="5f96e-336">Is uses a second parameter, **nr**, to define the number of customers that must be created.</span></span> <span data-ttu-id="5f96e-337">Para cada iteración, los parámetros en el archivo de parámetros de Excel se cambian mediante una característica UpdateCustomer.</span><span class="sxs-lookup"><span data-stu-id="5f96e-337">For each iteration, the parameters in the Excel parameter file are changed by using an UpdateCustomer function.</span></span> <span data-ttu-id="5f96e-338">A continuación, la línea de comandos de RSAT se llama en una característica RunTestCase.</span><span class="sxs-lookup"><span data-stu-id="5f96e-338">Then the RSAT command line is called in a RunTestCase function.</span></span>

<span data-ttu-id="5f96e-339">Abra el Entorno de scripting integrado (ISE) de Microsoft Windows PowerShell en modo de administración y pegue el siguiente código en la ventaja que se denomina **Untitled1.ps1**.</span><span class="sxs-lookup"><span data-stu-id="5f96e-339">Open Microsoft Windows PowerShell Integrated Scripting Environment (ISE) in admin mode, and paste the following code into the window that is named **Untitled1.ps1**.</span></span>

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
$excelFilename = "full path to Excel parameter file"
l$sheetName = "DirPartyQuickCreateForm"
for ($i = $start; $i -lt $start + $nr; $i++ )
{
    $CustomerId = $i.ToString("000000000")
    Write-Host "customer : " $CustomerId
    UpdateCustomer $excelFilename $sheetName $CustomerId
    RunTestCase $excelFilename
```

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a><span data-ttu-id="5f96e-340">Ejecutar una secuencia de comandos que depende de los datos de Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="5f96e-340">Run a script that depends on data in Microsoft Dynamics 365</span></span>

<span data-ttu-id="5f96e-341">El siguiente ejemplo utiliza una llamada del protocolo abierto de datos (OData) para encontrar el estado del pedido de un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="5f96e-341">The following example uses an Open Data Protocol (OData) call to find the order status of a purchase order.</span></span> <span data-ttu-id="5f96e-342">Si el estado no se **factura**, puede, por ejemplo, llamar a un caso de prueba de RSAT que registra la factura.</span><span class="sxs-lookup"><span data-stu-id="5f96e-342">If the status isn't **invoiced**, you can, for example, call an RSAT test case that posts the invoice.</span></span>

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


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]