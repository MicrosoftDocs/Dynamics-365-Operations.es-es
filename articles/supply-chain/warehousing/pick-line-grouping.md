---
title: Picking de agrupación de líneas
description: Este tema proporciona una descripción general de la agrupación de líneas de selección.
author: Mirzaab
manager: tfehr
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: b3497d43a500898207ed5154721ee0e3a327fb93
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017745"
---
# <a name="pick-line-grouping"></a><span data-ttu-id="30c1f-103">Picking de agrupación de líneas</span><span class="sxs-lookup"><span data-stu-id="30c1f-103">Pick line grouping</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="30c1f-104">En la agrupación de líneas de selección, varias líneas de trabajo que tienen el mismo artículo y ubicación se pueden combinar en una sola selección que se presenta al usuario en un dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="30c1f-104">In pick line grouping, multiple work lines that have the same item and location can be combined into a single pick that is presented to the user on a mobile device.</span></span> <span data-ttu-id="30c1f-105">Esto permite que los trabajadores del almacén puedan recibir las instrucciones más eficaces posibles, pero también se mantiene la separación requerida de líneas de trabajo en el sistema (por ejemplo, para diferentes contenedores y pedidos).</span><span class="sxs-lookup"><span data-stu-id="30c1f-105">Therefore, warehouse workers can receive the most efficient instructions that are possible, but the required separation of work lines in the system is also maintained (for example, for different containers and orders).</span></span>

## <a name="set-up-pick-line-grouping"></a><span data-ttu-id="30c1f-106">Configurar la agrupación de líneas de selección</span><span class="sxs-lookup"><span data-stu-id="30c1f-106">Set up pick line grouping</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="30c1f-107">Crear un elemento de menú del dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="30c1f-107">Create a mobile device menu item</span></span>

1. <span data-ttu-id="30c1f-108">Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Elementos del menú del dispositivo móvil** y cree un elemento de menú nuevo denominado **Selección de línea de grupo de ventas: dirigida por el usuario**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-108">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items** , and create a new menu item that is named **Sales group line picking – User directed**.</span></span>
2. <span data-ttu-id="30c1f-109">En **Elementos de menú del dispositivo móvil** , establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="30c1f-109">Under **Mobile device menu items** , set the following values:</span></span>

    - <span data-ttu-id="30c1f-110">En el campo **Nombre del elemento del menú** , especifique **Selección de ventas: línea de grupo**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-110">In the **Menu item name** field, enter **Sales Pick - Group line**.</span></span>
    - <span data-ttu-id="30c1f-111">En el campo **Título** , especifique **Selección de ventas: línea de grupo**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-111">In the **Title** field, enter **Sales Pick - Group line**.</span></span>
    - <span data-ttu-id="30c1f-112">En el campo **Modo** , seleccione **Trabajo**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-112">In the **Mode** field, select **Work**.</span></span>
    - <span data-ttu-id="30c1f-113">Establezca la opción **Usar trabajo existente** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-113">Set the **Use existing work** option to **Yes**.</span></span>

3. <span data-ttu-id="30c1f-114">En la ficha rápida **General** puede establecer los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="30c1f-114">On the **General** FastTab, you can set the following values:</span></span>

    - <span data-ttu-id="30c1f-115">En el campo **Dirigido por** , seleccione **Dirigido por el usuario**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-115">In the **Directed by** field, select **User directed**.</span></span>
    - <span data-ttu-id="30c1f-116">Seleccione la opción **Generar matrícula de entidad de almacén** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-116">Set the **Generate license plate** option to **Yes**.</span></span>
    - <span data-ttu-id="30c1f-117">Establezca la opción **Selección de grupo** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-117">Set the **Group pick** option to **Yes**.</span></span>

4. <span data-ttu-id="30c1f-118">En la ficha rápida **Clases de trabajo** , siga estos pasos para configurar las clases de trabajo válidas para el elemento de menú del dispositivo móvil:</span><span class="sxs-lookup"><span data-stu-id="30c1f-118">On the **Work classes** FastTab, follow these steps to configure the valid work classes for the mobile device menu item:</span></span>

    1. <span data-ttu-id="30c1f-119">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-119">Select **New**.</span></span>
    2. <span data-ttu-id="30c1f-120">En el campo **Identificador de la clase de trabajo** , seleccione **Ventas** o **Selección de pedidos de ventas** en función del almacén que vaya a utilizar.</span><span class="sxs-lookup"><span data-stu-id="30c1f-120">In the **Work class ID** field, select **Sales** or **SO Pick** , depending on the warehouse that you will use.</span></span>
    3. <span data-ttu-id="30c1f-121">En el campo **Tipo de orden de trabajo** , seleccione **Pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-121">In the **Work order type** field, select **Sales orders**.</span></span>

### <a name="set-up-a-mobile-device-menu"></a><span data-ttu-id="30c1f-122">Configurar un menú de dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="30c1f-122">Set up a mobile device menu</span></span>

1. <span data-ttu-id="30c1f-123">Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-123">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span> 
1. <span data-ttu-id="30c1f-124">Agregue el elemento de menú que acaba de crear al menú deseado.</span><span class="sxs-lookup"><span data-stu-id="30c1f-124">Add the menu item that you just created to the desired menu.</span></span>

### <a name="set-up-a-work-template"></a><span data-ttu-id="30c1f-125">Configurar una plantilla de trabajo</span><span class="sxs-lookup"><span data-stu-id="30c1f-125">Set up a work template</span></span>

1. <span data-ttu-id="30c1f-126">Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-126">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="30c1f-127">Encuentre la plantilla de trabajo que se debe usar con esta función.</span><span class="sxs-lookup"><span data-stu-id="30c1f-127">Find the work template that should be used with this function.</span></span> <span data-ttu-id="30c1f-128">Para este ejemplo, seleccione la plantilla de trabajo estándar de Contoso, **51 Pick to stage**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-128">For this example, select the standard **51 Pick to stage** Contoso work template.</span></span>
1. <span data-ttu-id="30c1f-129">En el menú, seleccione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-129">On the menu, select **Edit query**.</span></span>
1. <span data-ttu-id="30c1f-130">En la pestaña **Ordenación** , seleccione **Agregar** y, a continuación, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="30c1f-130">On the **Sorting** tab, select **Add** , and then set the following values:</span></span>

    - <span data-ttu-id="30c1f-131">En el campo **Tabla** , seleccione **Transacciones de trabajo temporal**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-131">In the **Table** field, select **Temporary work transactions**.</span></span>
    - <span data-ttu-id="30c1f-132">En el campo **Tabla derivada** , seleccione **Transacciones de trabajo temporal**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-132">In the **Derived table** field, select **Temporary work transactions**.</span></span>
    - <span data-ttu-id="30c1f-133">En el campo **Campo** , seleccione **Número de artículo**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-133">In the **Field** field, select **Item number**.</span></span>
    - <span data-ttu-id="30c1f-134">En el campo **Dirección de búsqueda** , seleccione **Ascendente**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-134">In the **Search direction** field, select **Ascending**.</span></span>

> [!NOTE]
> <span data-ttu-id="30c1f-135">Para que la funcionalidad de agrupación de líneas de selección funcione, las líneas de trabajo deben ordenarse por id. de artículo.</span><span class="sxs-lookup"><span data-stu-id="30c1f-135">For the pick line grouping functionality to work, the work lines must be sorted by item ID.</span></span> <span data-ttu-id="30c1f-136">Si las líneas que tienen los mismos artículos no se secuencian una tras otra, no se agruparán.</span><span class="sxs-lookup"><span data-stu-id="30c1f-136">If lines that have the same items aren't sequenced one after another, they won't be grouped.</span></span>

## <a name="example"></a><span data-ttu-id="30c1f-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="30c1f-137">Example</span></span>

### <a name="create-picking-work"></a><span data-ttu-id="30c1f-138">Crear trabajo de selección</span><span class="sxs-lookup"><span data-stu-id="30c1f-138">Create picking work</span></span>

<span data-ttu-id="30c1f-139">Antes de poder configurar la agrupación de líneas de clúster debe crear un trabajo de salida válido.</span><span class="sxs-lookup"><span data-stu-id="30c1f-139">Before you can set up pick line grouping, you must create some eligible outbound work.</span></span>

1. <span data-ttu-id="30c1f-140">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-140">Go to **Sales and Marketing \> Sales orders \> All sales orders**.</span></span>
2. <span data-ttu-id="30c1f-141">Seleccione **Nuevo** para crear un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="30c1f-141">Select **New** to create a sales order.</span></span> 
3. <span data-ttu-id="30c1f-142">En el campo **Cuenta de cliente** , seleccione cualquier cliente.</span><span class="sxs-lookup"><span data-stu-id="30c1f-142">In the **Customer account** field, select any customer.</span></span> 
4. <span data-ttu-id="30c1f-143">En la ficha desplegable **General** , en el campo **Almacén** , seleccione el almacén **51**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-143">On the **General** FastTab, in the **Warehouse** field, select **51**.</span></span> <span data-ttu-id="30c1f-144">A continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-144">Then select **OK**.</span></span>
5. <span data-ttu-id="30c1f-145">En **Líneas de pedido de ventas** , agregue las seis líneas siguientes:</span><span class="sxs-lookup"><span data-stu-id="30c1f-145">Under **Sales order lines** , add the following six lines:</span></span>

    - <span data-ttu-id="30c1f-146">**Línea 1:** en el campo **Número de artículo** , seleccione **M9200**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-146">**Line 1:** In the **Item number** field, select **M9200**.</span></span> <span data-ttu-id="30c1f-147">En el campo **Cantidad** , especifique **3**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-147">In the **Quantity** field, enter **3**.</span></span>
    - <span data-ttu-id="30c1f-148">**Línea 2:** en el campo **Número de artículo** , seleccione **M9201**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-148">**Line 2:** In the **Item number** field, select **M9201**.</span></span> <span data-ttu-id="30c1f-149">En el campo **Cantidad** , especifique **3**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-149">In the **Quantity** field, enter **3**.</span></span> 
    - <span data-ttu-id="30c1f-150">**Línea 3:** en el campo **Número de artículo** , seleccione **M9202**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-150">**Line 3:** In the **Item number** field, select **M9202**.</span></span> <span data-ttu-id="30c1f-151">En el campo **Cantidad** , especifique **2**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-151">In the **Quantity** field, enter **2**.</span></span> 
    - <span data-ttu-id="30c1f-152">**Línea 4:** en el campo **Número de artículo** , seleccione **M9200**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-152">**Line 4:** In the **Item number** field, select **M9200**.</span></span> <span data-ttu-id="30c1f-153">En el campo **Cantidad** , especifique **1**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-153">In the **Quantity** field, enter **1**.</span></span> 
    - <span data-ttu-id="30c1f-154">**Línea 5:** en el campo **Número de artículo** , seleccione **M9200**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-154">**Line 5:** In the **Item number** field, select **M9200**.</span></span> <span data-ttu-id="30c1f-155">En el campo **Cantidad** , especifique **3**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-155">In the **Quantity** field, enter **3**.</span></span>
    - <span data-ttu-id="30c1f-156">**Línea 6:** en el campo **Número de artículo** , seleccione **M9202**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-156">**Line 6:** In the **Item number** field, select **M9202**.</span></span> <span data-ttu-id="30c1f-157">En el campo **Cantidad** , especifique **7**.</span><span class="sxs-lookup"><span data-stu-id="30c1f-157">In the **Quantity** field, enter **7**.</span></span> 

    <span data-ttu-id="30c1f-158">A continuación se muestra un resumen de las cantidades totales para cada artículo:</span><span class="sxs-lookup"><span data-stu-id="30c1f-158">Here is a summary of the total quantities for each item:</span></span>

    - <span data-ttu-id="30c1f-159">**Artículo M9200:** 7 cada uno</span><span class="sxs-lookup"><span data-stu-id="30c1f-159">**Item M9200:** 7 each</span></span>
    - <span data-ttu-id="30c1f-160">**Artículo M9201:** 3 cada uno</span><span class="sxs-lookup"><span data-stu-id="30c1f-160">**Item M9201:** 3 each</span></span>
    - <span data-ttu-id="30c1f-161">**Artículo M9202:** 9 cada uno</span><span class="sxs-lookup"><span data-stu-id="30c1f-161">**Item M9202:** 9 each</span></span>

6. <span data-ttu-id="30c1f-162">Antes de liberar los pedidos al almacén, debe asegurarse de que las ubicaciones de selección tengan suficiente inventario para todos los artículos en todos los pedidos.</span><span class="sxs-lookup"><span data-stu-id="30c1f-162">Before you release the orders to the warehouse, you must make sure that the pick locations have enough inventory for all the items on all the orders.</span></span> <span data-ttu-id="30c1f-163">Revisa la configuración de **Directiva de ubicación** para determinar qué ubicaciones de selección se utilizan para la selección de pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="30c1f-163">Review the **Location directive** setting to determine which picking locations are used for sales order picking.</span></span>
7. <span data-ttu-id="30c1f-164">Reserve el inventario y libérelo en el almacén.</span><span class="sxs-lookup"><span data-stu-id="30c1f-164">Reserve the inventory, and release it to the warehouse.</span></span> <span data-ttu-id="30c1f-165">Se crea un id. de trabajo de seis líneas.</span><span class="sxs-lookup"><span data-stu-id="30c1f-165">A work ID that has six lines is created.</span></span> <span data-ttu-id="30c1f-166">Las líneas se ordenan por número de artículo.</span><span class="sxs-lookup"><span data-stu-id="30c1f-166">The lines are sorted by item number.</span></span>

### <a name="run-the-mobile-device-flow"></a><span data-ttu-id="30c1f-167">Ejecutar el flujo del dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="30c1f-167">Run the mobile device flow</span></span>

1. <span data-ttu-id="30c1f-168">En el dispositivo móvil, seleccione el menú que incluye el nuevo elemento de menú del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="30c1f-168">On the mobile device, select the menu that includes the new mobile device menu item.</span></span>
1. <span data-ttu-id="30c1f-169">Seleccione el elemento de menú **Selección de ventas: línea de grupo** e inicie la selección.</span><span class="sxs-lookup"><span data-stu-id="30c1f-169">Select the **Sales Pick – Group line** menu item, and initiate the pick.</span></span>

    <span data-ttu-id="30c1f-170">Después de seleccionar el menú e introducir el id. de trabajo, verá el paso de selección en el que se agrupan todas las líneas de selección para el artículo M9200.</span><span class="sxs-lookup"><span data-stu-id="30c1f-170">After you select the menu and enter the work ID, you see the pick step where all pick lines for item M9200 are grouped.</span></span> <span data-ttu-id="30c1f-171">Recibe una instrucción para elegir 7 cada uno del artículo M9200.</span><span class="sxs-lookup"><span data-stu-id="30c1f-171">You receive an instruction to pick 7 each of item M9200.</span></span>

1. <span data-ttu-id="30c1f-172">Confirme el paso de selección.</span><span class="sxs-lookup"><span data-stu-id="30c1f-172">Confirm the pick step.</span></span> 
1. <span data-ttu-id="30c1f-173">Vaya a la pantalla de cliente del trabajo en curso y observe que las tres líneas de selección para el artículo M9200 se cerraron simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="30c1f-173">Go to the client screen of the work in process, and notice that all three pick lines for item M9200 were closed simultaneously.</span></span>

    <span data-ttu-id="30c1f-174">Se presenta la línea de trabajo 4.</span><span class="sxs-lookup"><span data-stu-id="30c1f-174">Work line 4 is presented.</span></span>

1. <span data-ttu-id="30c1f-175">Confirme el paso de selección.</span><span class="sxs-lookup"><span data-stu-id="30c1f-175">Confirm the pick step.</span></span>

    <span data-ttu-id="30c1f-176">El último paso de selección en el dispositivo móvil agrega las dos últimas líneas de selección de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="30c1f-176">The last pick step on the mobile device aggregates the last two pick lines from the work order.</span></span>

1. <span data-ttu-id="30c1f-177">Complete el paso de selección para 9 cada uno del artículo M9202.</span><span class="sxs-lookup"><span data-stu-id="30c1f-177">Complete the pick step for 9 each of item M9202.</span></span>
1. <span data-ttu-id="30c1f-178">Confirme el paso de colocación y cualquier par adicional de selección/colocación para completar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="30c1f-178">Confirm the put step and any additional pick/put pairs to complete the work.</span></span>

> [!NOTE]
> - <span data-ttu-id="30c1f-179">Las líneas de trabajo solo se pueden agrupar si están en secuencia.</span><span class="sxs-lookup"><span data-stu-id="30c1f-179">Work lines can be grouped only if they are in sequence.</span></span>
> - <span data-ttu-id="30c1f-180">No se admite la siguiente funcionalidad:</span><span class="sxs-lookup"><span data-stu-id="30c1f-180">The following functionality isn't supported:</span></span>
>
>    - <span data-ttu-id="30c1f-181">Artículos con peso capturado.</span><span class="sxs-lookup"><span data-stu-id="30c1f-181">Catch-weight items.</span></span> <span data-ttu-id="30c1f-182">Si hay artículos con peso capturado en el trabajo, recibirá un mensaje de error antes de iniciar la selección.</span><span class="sxs-lookup"><span data-stu-id="30c1f-182">If there are any catch-weight items on the work, you receive an error message before you start to pick.</span></span>
>    - <span data-ttu-id="30c1f-183">Selección de piezas.</span><span class="sxs-lookup"><span data-stu-id="30c1f-183">Piece picking.</span></span>
>    - <span data-ttu-id="30c1f-184">Líneas de trabajo que tienen trabajo de reabastecimiento sin terminar.</span><span class="sxs-lookup"><span data-stu-id="30c1f-184">Work lines that have unfinished replenishment work.</span></span>
>    - <span data-ttu-id="30c1f-185">Selección en exceso.</span><span class="sxs-lookup"><span data-stu-id="30c1f-185">Over-picking.</span></span>
>    - <span data-ttu-id="30c1f-186">Selección corta con reasignación de artículos</span><span class="sxs-lookup"><span data-stu-id="30c1f-186">Short picking with item reallocation</span></span>
