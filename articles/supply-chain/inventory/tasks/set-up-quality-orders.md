---
title: "Configuración de pedidos de calidad"
description: "Este procedimiento le muestra cómo habilitar un proceso de administración de calidad donde el inventario entrante se debe examinar inmediatamente después del registro de llegada."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: e44b585c6e6e86d244328e73846a5c91f94233eb
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---
# <a name="set-up-quality-orders"></a><span data-ttu-id="9cf7d-103">Configuración de pedidos de calidad</span><span class="sxs-lookup"><span data-stu-id="9cf7d-103">Set up quality orders</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9cf7d-104">Este procedimiento le muestra cómo habilitar un proceso de administración de calidad donde el inventario entrante se debe examinar inmediatamente después del registro de llegada.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-104">This procedure shows you how to enable a quality management process where incoming inventory must be inspected immediately after arrival registration.</span></span> <span data-ttu-id="9cf7d-105">El procedimiento lo realizará normalmente un gestor de calidad.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-105">The procedure will typically be carried out by a quality manager.</span></span> <span data-ttu-id="9cf7d-106">El proceso incluye la creación de un grupo de calidad para definir los artículos que se van a muestrear y un grupo de pruebas para agrupar las pruebas que deben llevarse a cabo en los artículos del grupo de calidad.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-106">The process includes the creation of a quality group, to define the items that are going to be sampled, and a test group to group the tests that are to be performed on items in the quality group.</span></span> <span data-ttu-id="9cf7d-107">Puede ejecutar esta guía en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-107">You can run this guide in the USMF demo data company.</span></span>


## <a name="enable-quality-management"></a><span data-ttu-id="9cf7d-108">Habilitar la administración de calidad</span><span class="sxs-lookup"><span data-stu-id="9cf7d-108">Enable quality management</span></span>
1. <span data-ttu-id="9cf7d-109">Vaya a Gestión del inventario > Configurar > Parámetros de la gestión de inventario y almacenes.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-109">Go to Inventory management > Setup > Inventory and warehouse management parameters.</span></span>
2. <span data-ttu-id="9cf7d-110">Haga clic en la ficha Administración de calidad.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-110">Click the Quality management tab.</span></span>
3. <span data-ttu-id="9cf7d-111">Defina la opción Usar administración de calidad en Sí.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-111">Set the Use quality management option to Yes.</span></span>
4. <span data-ttu-id="9cf7d-112">Haga clic en Configuración del informe.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-112">Click Report setup.</span></span>
    * <span data-ttu-id="9cf7d-113">En USMF, ya se ha definido la configuración del informe para la administración de calidad.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-113">In USMF, the report setup for quality management is already defined.</span></span> <span data-ttu-id="9cf7d-114">Si no se hiciera esto, agregaría nuevas líneas aquí para los diferentes tipos de informes y seleccionaría el tipo de documento que se utilizará para cada informe.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-114">If this wasn’t done, you’d add new lines here for the different report types, and select the type of document to be used for each report.</span></span>  
5. <span data-ttu-id="9cf7d-115">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-115">Close the page.</span></span>
6. <span data-ttu-id="9cf7d-116">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-116">Close the page.</span></span>

## <a name="create-a-test"></a><span data-ttu-id="9cf7d-117">Crear una prueba</span><span class="sxs-lookup"><span data-stu-id="9cf7d-117">Create a test</span></span>
1. <span data-ttu-id="9cf7d-118">Vaya a Gestión del inventario > Configurar > Control de calidad > Pruebas.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-118">Go to Inventory management > Setup > Quality control > Tests.</span></span>
2. <span data-ttu-id="9cf7d-119">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-119">Click New.</span></span>
3. <span data-ttu-id="9cf7d-120">En el campo Prueba, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-120">In the Test field, type a value.</span></span>
4. <span data-ttu-id="9cf7d-121">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-121">In the Description field, type a value.</span></span>
5. <span data-ttu-id="9cf7d-122">En el campo Tipo, seleccione "Opción".</span><span class="sxs-lookup"><span data-stu-id="9cf7d-122">In the Type field, select 'Option'.</span></span>
    * <span data-ttu-id="9cf7d-123">En este ejemplo, seleccionaremos “Opción”, que permitirá asignar los resultados de prueba en función de los valores predefinidos.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-123">In this example, we'll select "Option" which will make it possible to assign the test results based on pre-defined values.</span></span>  
6. <span data-ttu-id="9cf7d-124">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-124">Click Save.</span></span>
7. <span data-ttu-id="9cf7d-125">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-125">Close the page.</span></span>

## <a name="create-test-variables-to-define-the-way-test-results-are-recorded"></a><span data-ttu-id="9cf7d-126">Crear variables de prueba para definir la manera en la que se registran los resultados de prueba</span><span class="sxs-lookup"><span data-stu-id="9cf7d-126">Create Test variables to define the way test results are recorded</span></span>
1. <span data-ttu-id="9cf7d-127">Vaya a Gestión del inventario > Configurar > Control de calidad > Variables de prueba.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-127">Go to Inventory management > Setup > Quality control > Test variables.</span></span>
2. <span data-ttu-id="9cf7d-128">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-128">Click New.</span></span>
3. <span data-ttu-id="9cf7d-129">En el campo Variable, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-129">In the Variable field, type a value.</span></span>
4. <span data-ttu-id="9cf7d-130">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-130">In the Description field, type a value.</span></span>
5. <span data-ttu-id="9cf7d-131">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-131">Click Save.</span></span>
6. <span data-ttu-id="9cf7d-132">Haga clic en los resultados.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-132">Click Outcomes.</span></span>
7. <span data-ttu-id="9cf7d-133">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-133">Click New.</span></span>
8. <span data-ttu-id="9cf7d-134">En el campo Resultado, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-134">In the Outcome field, type a value.</span></span>
9. <span data-ttu-id="9cf7d-135">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-135">In the Description field, type a value.</span></span>
10. <span data-ttu-id="9cf7d-136">En el campo Estado del resultado, seleccione "Aprobado".</span><span class="sxs-lookup"><span data-stu-id="9cf7d-136">In the Outcome status field, select 'Pass'.</span></span>
11. <span data-ttu-id="9cf7d-137">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-137">Click Save.</span></span>
12. <span data-ttu-id="9cf7d-138">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-138">Click New.</span></span>
13. <span data-ttu-id="9cf7d-139">En el campo Resultado, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-139">In the Outcome field, type a value.</span></span>
14. <span data-ttu-id="9cf7d-140">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-140">In the Description field, type a value.</span></span>
15. <span data-ttu-id="9cf7d-141">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-141">Click Save.</span></span>
16. <span data-ttu-id="9cf7d-142">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-142">Close the page.</span></span>
17. <span data-ttu-id="9cf7d-143">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-143">Close the page.</span></span>

## <a name="set-up-item-sampling"></a><span data-ttu-id="9cf7d-144">Configurar el muestreo de artículos</span><span class="sxs-lookup"><span data-stu-id="9cf7d-144">Set up item sampling</span></span>
1. <span data-ttu-id="9cf7d-145">Vaya a Gestión del inventario > Configurar > Control de calidad > Muestreo de artículos.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-145">Go to Inventory management > Setup > Quality control > Item sampling.</span></span>
2. <span data-ttu-id="9cf7d-146">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-146">Click New.</span></span>
3. <span data-ttu-id="9cf7d-147">En el campo Muestreo de artículos, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-147">In the Item sampling field, type a value.</span></span>
4. <span data-ttu-id="9cf7d-148">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-148">In the Description field, type a value.</span></span>
5. <span data-ttu-id="9cf7d-149">En el campo Valor, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-149">In the Value field, enter a number.</span></span>
    * <span data-ttu-id="9cf7d-150">Este valor está relacionado con la especificación de cantidad seleccionada en el campo adyacente.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-150">This value relates to the Quantity specification that’s selected in the adjacent field.</span></span>  
6. <span data-ttu-id="9cf7d-151">Expanda o contraiga la sección Procesar.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-151">Expand or collapse the Process section.</span></span>
7. <span data-ttu-id="9cf7d-152">Active o desactive la casilla Bloqueo completo..</span><span class="sxs-lookup"><span data-stu-id="9cf7d-152">Select or clear the Full blocking check box.</span></span>
    * <span data-ttu-id="9cf7d-153">Si selecciona esta opción, se bloquea la cantidad total del lote o de la línea de pedido si se produce un error en una prueba.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-153">If you select this option, the whole lot or order line quantity is blocked if a test is failed.</span></span> <span data-ttu-id="9cf7d-154">Si no la selecciona, solo se bloquean los artículos del pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-154">If you don't select it, only the items in the quality order are blocked.</span></span>  
8. <span data-ttu-id="9cf7d-155">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-155">Click Save.</span></span>
9. <span data-ttu-id="9cf7d-156">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-156">Close the page.</span></span>

## <a name="create-a-quality-group"></a><span data-ttu-id="9cf7d-157">Crear un grupo de calidad</span><span class="sxs-lookup"><span data-stu-id="9cf7d-157">Create a quality group</span></span>
1. <span data-ttu-id="9cf7d-158">Vaya a Gestión del inventario > Configurar > Control de calidad > Grupos de calidad.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-158">Go to Inventory management > Setup > Quality control > Quality groups.</span></span>
2. <span data-ttu-id="9cf7d-159">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-159">Click New.</span></span>
3. <span data-ttu-id="9cf7d-160">En el campo Grupo de calidad, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-160">In the Quality group field, type a value.</span></span>
    * <span data-ttu-id="9cf7d-161">Use un nombre descriptivo que le ayude a identificar qué clase de artículos contendrá el grupo (sus criterios de muestreo).</span><span class="sxs-lookup"><span data-stu-id="9cf7d-161">Use a descriptive name to help you identify which kind of items the group will contain (your sampling criteria).</span></span>  
4. <span data-ttu-id="9cf7d-162">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-162">In the Description field, type a value.</span></span>
5. <span data-ttu-id="9cf7d-163">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-163">Click Save.</span></span>
6. <span data-ttu-id="9cf7d-164">Haga clic en Agregar artículos.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-164">Click Add items.</span></span>
7. <span data-ttu-id="9cf7d-165">Seleccione la fila Código de artículo</span><span class="sxs-lookup"><span data-stu-id="9cf7d-165">Select the Item number row</span></span>
    * <span data-ttu-id="9cf7d-166">En este ejemplo, el filtrado se ejecutará en función del número de artículo.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-166">In this example the filtering will be run based on  the item number.</span></span>  
8. <span data-ttu-id="9cf7d-167">En el campo Criterios, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-167">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="9cf7d-168">Por ejemplo, escriba T\* para filtrar en los números de artículo que empiecen por T.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-168">For example, type T\* to filter on the item numbers that start with T.</span></span>  
9. <span data-ttu-id="9cf7d-169">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="9cf7d-169">Click OK.</span></span>
10. <span data-ttu-id="9cf7d-170">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="9cf7d-170">Click OK.</span></span>
11. <span data-ttu-id="9cf7d-171">Haga clic en Grupos de calidad de artículos.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-171">Click Item quality groups.</span></span>
12. <span data-ttu-id="9cf7d-172">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-172">Close the page.</span></span>
13. <span data-ttu-id="9cf7d-173">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-173">Close the page.</span></span>

## <a name="create-a-test-group"></a><span data-ttu-id="9cf7d-174">Crear un grupo de pruebas</span><span class="sxs-lookup"><span data-stu-id="9cf7d-174">Create a test group</span></span>
1. <span data-ttu-id="9cf7d-175">Vaya a Gestión del inventario > Configurar > Control de calidad > Grupos de prueba.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-175">Go to Inventory management > Setup > Quality control > Test groups.</span></span>
2. <span data-ttu-id="9cf7d-176">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-176">Click New.</span></span>
3. <span data-ttu-id="9cf7d-177">En el campo Grupo de prueba, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-177">In the Test group field, type a value.</span></span>
    * <span data-ttu-id="9cf7d-178">Asigne un nombre al grupo de pruebas que le ayude a recordar qué clase de pruebas se están ejecutando y con qué grupo de calidad deben estar asociadas.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-178">Give the Test group a name that will help you remember what kind of tests are being run, and which quality group it should be associated with.</span></span> <span data-ttu-id="9cf7d-179">Por ejemplo, si se va a usar con un grupo de calidad que seleccione los artículos que empiecen por “T”, podría llamarlo “T- pruebas de artículo”.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-179">For example, it it’s to be used with a quality group that selects items starting with “T”, you could call it “T-item tests”.</span></span>  
4. <span data-ttu-id="9cf7d-180">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-180">In the Description field, type a value.</span></span>
5. <span data-ttu-id="9cf7d-181">En el campo de muestreo de artículos, seleccione la línea de muestreo de artículos que ha creado antes.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-181">In the Item sampling field, select the item sampling line that you created before.</span></span>
6. <span data-ttu-id="9cf7d-182">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-182">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="9cf7d-183">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-183">Click Add.</span></span>
8. <span data-ttu-id="9cf7d-184">En el campo Número de secuencia, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-184">In the Sequence number field, enter a number.</span></span>
9. <span data-ttu-id="9cf7d-185">En el campo Prueba, seleccione la prueba que ha creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-185">In the Test field, select the test that you created earlier.</span></span>
10. <span data-ttu-id="9cf7d-186">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-186">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="9cf7d-187">Haga clic en la pestaña Prueba.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-187">Click the Test tab.</span></span>
12. <span data-ttu-id="9cf7d-188">En el campo Variable, seleccione la variable de prueba que ha creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-188">In the Variable field, select the test variable that you created before</span></span>
13. <span data-ttu-id="9cf7d-189">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-189">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="9cf7d-190">En el campo Resultado predeterminado, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-190">In the Default outcome field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="9cf7d-191">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-191">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="9cf7d-192">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-192">Click Save.</span></span>
17. <span data-ttu-id="9cf7d-193">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-193">Close the page.</span></span>

## <a name="define-when-quality-orders-will-be-created"></a><span data-ttu-id="9cf7d-194">Definir cuándo se crearán los pedidos de calidad</span><span class="sxs-lookup"><span data-stu-id="9cf7d-194">Define when quality orders will be created</span></span>
1. <span data-ttu-id="9cf7d-195">Vaya a Gestión del inventario > Configurar > Control de calidad > Asociaciones de calidad.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-195">Go to Inventory management > Setup > Quality control > Quality associations.</span></span>
2. <span data-ttu-id="9cf7d-196">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-196">Click New.</span></span>
3. <span data-ttu-id="9cf7d-197">En el campo Tipo de referencia, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-197">In the Reference type field, select an option.</span></span>
4. <span data-ttu-id="9cf7d-198">En el campo Código de artículo, seleccione "Grupo".</span><span class="sxs-lookup"><span data-stu-id="9cf7d-198">In the Item code field, select 'Group'.</span></span>
    * <span data-ttu-id="9cf7d-199">En este ejemplo, seleccionaremos “Grupo” y utilizaremos el grupo de calidad que creamos antes.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-199">In this example, we’ll select "Group" and use the quality group we created before.</span></span> <span data-ttu-id="9cf7d-200">También puede establecer esto en “Tabla” para especificar los artículos manualmente o para seleccionar “Todos” con el fin de agregar todos los artículos al pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-200">You could also set this to "Table" to specify the items manually, or select "All" to add all items to the quality order.</span></span>  
5. <span data-ttu-id="9cf7d-201">En el campo Artículo, seleccione el grupo de calidad que ha creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-201">In the Item field, select the quality group that you created before.</span></span>
    * <span data-ttu-id="9cf7d-202">Las opciones disponibles en el campo Artículo dependen de lo que se establezca en el campo Código de artículo.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-202">The options available in the Item field depend on what you set in the Item code field.</span></span>  
6. <span data-ttu-id="9cf7d-203">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-203">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="9cf7d-204">Expanda o contraiga la sección Procesar.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-204">Expand or collapse the Process section.</span></span>
8. <span data-ttu-id="9cf7d-205">En el campo Tipo de evento, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-205">In the Event type field, select an option.</span></span>
    * <span data-ttu-id="9cf7d-206">Este es el evento que desencadena la prueba.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-206">This is the event that triggers the test.</span></span> <span data-ttu-id="9cf7d-207">Las opciones disponibles aquí dependen de qué proceso ha seleccionado en el campo Tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-207">The options available here depend on which process you selected in the Reference type field.</span></span>  
9. <span data-ttu-id="9cf7d-208">En el campo Ejecución, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-208">In the Execution field, select an option.</span></span>
10. <span data-ttu-id="9cf7d-209">Expanda o contraiga la sección Proceso de pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-209">Expand or collapse the Quality order process section.</span></span>
11. <span data-ttu-id="9cf7d-210">En el campo Bloqueo de eventos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-210">In the Event blocking field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="9cf7d-211">Este campo muestra la lista de procesos que es posible bloquear si el pedido de calidad aún está abierto.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-211">This field shows the list of processes that it’s possible to block if the quality order is still open.</span></span> <span data-ttu-id="9cf7d-212">Las opciones dependen de su elección en el campo Tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-212">The options depend on what you selected in the Event type field.</span></span>  
12. <span data-ttu-id="9cf7d-213">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-213">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="9cf7d-214">Esto estará en función de los valores seleccionados anteriores.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-214">This will be depending on the previous selected values.</span></span> <span data-ttu-id="9cf7d-215">Seleccione si los siguientes procesos deben bloquearse mientras haya pedidos de calidad abiertos vinculados a una línea de documento de origen.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-215">Select if the following processes must be blocked while having open quality orders linked to a source document line.</span></span>  
13. <span data-ttu-id="9cf7d-216">Expanda o contraiga la sección Especificaciones.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-216">Expand or collapse the Specifications section.</span></span>
14. <span data-ttu-id="9cf7d-217">En el campo Grupo de prueba, seleccione el grupo de prueba que ha creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-217">In the Test group field, select the test group that you created before.</span></span>
15. <span data-ttu-id="9cf7d-218">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-218">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="9cf7d-219">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-219">Click Save.</span></span>
17. <span data-ttu-id="9cf7d-220">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9cf7d-220">Close the page.</span></span>

