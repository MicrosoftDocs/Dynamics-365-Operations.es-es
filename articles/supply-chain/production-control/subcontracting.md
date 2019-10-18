---
title: Subcontratación
description: Este tema le ayudará a compilar un tutorial de subcontratación en la fabricación en Dynamics 365 Supply Chain Management.
author: christophernread
manager: AnnBe
ms.date: 09/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2018-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 83d1d7adf91c246ecad574043cbb60ca260bb328
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249928"
---
# <a name="subcontracting"></a><span data-ttu-id="568fe-103">Subcontratación</span><span class="sxs-lookup"><span data-stu-id="568fe-103">Subcontracting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="568fe-104">Este tema le ayudará a compilar un tutorial de subcontratación en la fabricación en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="568fe-104">This topic will help you build a walkthrough of subcontracting in manufacturing in Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="568fe-105">La primera parte de este tema describe la configuración de los datos.</span><span class="sxs-lookup"><span data-stu-id="568fe-105">The first part of this topic describes the setup of the data.</span></span> <span data-ttu-id="568fe-106">La segunda parte le guía a través de los pasos en el tutorial.</span><span class="sxs-lookup"><span data-stu-id="568fe-106">The second part takes you through the steps in the walkthrough.</span></span>

## <a name="target-audience"></a><span data-ttu-id="568fe-107">Público objetivo</span><span class="sxs-lookup"><span data-stu-id="568fe-107">Target audience</span></span>

<span data-ttu-id="568fe-108">En este tema, aprenderá a configurar la subcontratación en la fabricación.</span><span class="sxs-lookup"><span data-stu-id="568fe-108">In this topic, you will learn how to set up subcontracting in manufacturing.</span></span> <span data-ttu-id="568fe-109">Usará datos existentes en la entidad jurídica de HQUS para realizar la configuración básica de un flujo de actividad de subcontratación.</span><span class="sxs-lookup"><span data-stu-id="568fe-109">You will use existing data in the HQUS legal entity to do the basic setup of a subcontracting activity flow.</span></span> <span data-ttu-id="568fe-110">Los datos de prueba en la entidad jurídica de HQUS incluyen los parámetros de configuración que se han preestablecido para admitir los pasos del tutorial.</span><span class="sxs-lookup"><span data-stu-id="568fe-110">The demo data in the HQUS legal entity includes setup parameters that have been preset to support the steps in the walkthrough.</span></span> <span data-ttu-id="568fe-111">Aunque el tutorial aborda puntos y desafíos del panel de claves para varios roles, lo puede completar el administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="568fe-111">Even though the walkthrough addresses key pain points and challenges for various roles, it can be completed by the system admin.</span></span>

## <a name="demo-scenario"></a><span data-ttu-id="568fe-112">Supuesto de demostración</span><span class="sxs-lookup"><span data-stu-id="568fe-112">Demo scenario</span></span>

<span data-ttu-id="568fe-113">En la entidad jurídica de HQUS, se fabrican altavoces de tecnología avanzada.</span><span class="sxs-lookup"><span data-stu-id="568fe-113">In the HQUS legal entity, high-end speakers are manufactured.</span></span> <span data-ttu-id="568fe-114">Durante el proceso de fabricación, los altavoces pasan por las tres operaciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="568fe-114">During the manufacturing process, speakers go through the following three operations.</span></span>

- <span data-ttu-id="568fe-115">**Pre-ensamblado**: se ensambla la caja acústica del altavoz.</span><span class="sxs-lookup"><span data-stu-id="568fe-115">**Pre-assembly** – The speaker cabinet is assembled.</span></span> <span data-ttu-id="568fe-116">El material para la caja acústica se selecciona en el almacén de material antes de iniciarse la operación.</span><span class="sxs-lookup"><span data-stu-id="568fe-116">The material for the cabinet is picked in the material warehouse before the operation is started.</span></span>
- <span data-ttu-id="568fe-117">**Capa** Después de ensamblar la caja acústica, tiene que revestirse.</span><span class="sxs-lookup"><span data-stu-id="568fe-117">**Coating** – After the speaker cabinet has been assembled, it must be coated.</span></span> <span data-ttu-id="568fe-118">Esta operación la completa un proveedor (subcontratista).</span><span class="sxs-lookup"><span data-stu-id="568fe-118">This operation is completed by a vendor (subcontractor).</span></span> <span data-ttu-id="568fe-119">La caja acústica del altavoz premontado se envía al subcontratista de la capa junto con dos materiales.</span><span class="sxs-lookup"><span data-stu-id="568fe-119">The pre-assembled speaker cabinet is shipped to the coating subcontractor together with two materials.</span></span>
- <span data-ttu-id="568fe-120">**Acabado** Después de que el subcontratista haya puesto una cobertura en la caja acústica del altavoz premontada, esta se devuelve a la entidad jurídica de HQUS de modo que el ensamblado final del orador se pueda completar.</span><span class="sxs-lookup"><span data-stu-id="568fe-120">**Finish** – After the pre-assembled speaker cabinet has been coated by the subcontractor, it's returned to the HQUS legal entity so that final assembly of the speaker can be completed.</span></span>

<span data-ttu-id="568fe-121">La ilustración siguiente muestra las tres operaciones y los materiales que consumen.</span><span class="sxs-lookup"><span data-stu-id="568fe-121">The following illustration shows the three operations and the materials that they consume.</span></span>

![Operaciones de pre-ensamblado, capa, y acabado, y los materiales que consumen.](./media/subcontract01_operations-materials.png)

## <a name="setup"></a><span data-ttu-id="568fe-123">Configuración</span><span class="sxs-lookup"><span data-stu-id="568fe-123">Setup</span></span>

<span data-ttu-id="568fe-124">Antes del inicio del tutorial, debe configurar los datos.</span><span class="sxs-lookup"><span data-stu-id="568fe-124">Before you start the walkthrough, you must set up the data.</span></span>

### <a name="set-up-the-finished-product"></a><span data-ttu-id="568fe-125">Configurar el producto acabado</span><span class="sxs-lookup"><span data-stu-id="568fe-125">Set up the finished product</span></span>

<span data-ttu-id="568fe-126">Este procedimiento lo lleva por el proceso de configuración del producto emitido D8100, “Caja acústica con revestimiento".</span><span class="sxs-lookup"><span data-stu-id="568fe-126">This procedure takes you through the setup of released product D8100, "Coated Cabinet."</span></span>

1. <span data-ttu-id="568fe-127">Seleccione **Gestión de información de productos \> Productos \> Productos emitidos** para abrir la página **Detalles de producto emitido**.</span><span class="sxs-lookup"><span data-stu-id="568fe-127">Select **Product information management \> Products \> Released products** to open the **Released product details** page.</span></span>
2. <span data-ttu-id="568fe-128">En el campo de filtro rápido, escriba **D8100** para encontrar el producto emitido existente.</span><span class="sxs-lookup"><span data-stu-id="568fe-128">In the quick filter field, enter **D8100** to find the existing released product.</span></span>

    ![Filtrado del producto emitido D8100 en la página de Detalles de producto emitido](./media/subcontract02_filtering-released-products.png)

3. <span data-ttu-id="568fe-130">En el panel de acciones, en la pestaña **Ingeniero**, seleccione **Ruta** para abrir la página **Ruta**.</span><span class="sxs-lookup"><span data-stu-id="568fe-130">On the Action Pane, on the **Engineer** tab, select **Route** to open the **Route** page.</span></span>

    <span data-ttu-id="568fe-131">La página **Ruta** muestra las ocho versiones de ruta para el producto emitido D8100.</span><span class="sxs-lookup"><span data-stu-id="568fe-131">The **Route** page shows the eight route versions for released product D8100.</span></span> <span data-ttu-id="568fe-132">Las ocho versiones de ruta se dividen en cuatro ruta en el sitio 1 y el sitio. 5.</span><span class="sxs-lookup"><span data-stu-id="568fe-132">The eight route versions are divided among four routes on site 1 and site 5.</span></span> <span data-ttu-id="568fe-133">La ruta 000400 se utiliza para la gestión de costes, la ruta 00041 se usa cuando la operación de la capa es una operación interna, y la ruta 00042 se usa cuando la operación de la capa es una operación externa.</span><span class="sxs-lookup"><span data-stu-id="568fe-133">Route 000400 is used for costing, route 00041 is used when the Coating operation is an internal operation, and route 00042 is used when the Coating operation is an external operation.</span></span>

    ![Ocho versiones de ruta en la página de la ruta](./media/subcontract03_route-page.png)

4. <span data-ttu-id="568fe-135">En el panel superior, en la cuadrícula **Versiones**, seleccione la versión de ruta **00042** para el sitio **5**.</span><span class="sxs-lookup"><span data-stu-id="568fe-135">In the upper pane, in the **Versions** grid, select route version **00042** for site **5**.</span></span>
5. <span data-ttu-id="568fe-136">En el panel inferior, en la pestaña **Visión general**, seleccione la operación **20** (**Cbnt CtSc**) en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="568fe-136">In the lower pane, on the **Overview** tab, select operation **20** (**Cbnt CtSc**) in the grid.</span></span>

    ![Operación 20 para la versión de ruta 00042 del sitio 5 seleccionado](./media/subcontract04_route-version-operation.png)

6. <span data-ttu-id="568fe-138">Seleccione la ficha **General**.</span><span class="sxs-lookup"><span data-stu-id="568fe-138">Select the **General** tab.</span></span>

    <span data-ttu-id="568fe-139">Observe que el campo **Tipo de ruta** del campo está establecido en **Proveedor**.</span><span class="sxs-lookup"><span data-stu-id="568fe-139">Notice that the field **Route type** field is set to **Vendor**.</span></span> <span data-ttu-id="568fe-140">Este valor indica que la operación 20 (Cbnt CtSc) es una operación subcontratada.</span><span class="sxs-lookup"><span data-stu-id="568fe-140">This value indicates that operation 20 (Cbnt CtSc) is a subcontracted operation.</span></span>

    ![Campo de tipo de ruta establecido en Proveedor en la pestaña General](./media/subcontract05_general-tab.png)

7. <span data-ttu-id="568fe-142">Seleccione la ficha **Requisitos de recursos**.</span><span class="sxs-lookup"><span data-stu-id="568fe-142">Select the **Resource requirements** tab.</span></span>

    <span data-ttu-id="568fe-143">Las capacidades se usarán para buscar un recurso aplicable durante la programación de producción.</span><span class="sxs-lookup"><span data-stu-id="568fe-143">Capabilities will be used to find an applicable resource during production scheduling.</span></span> <span data-ttu-id="568fe-144">Para la operación 20 (Cbnt CtSc), observe que se requiere un recurso que tiene dos capacidades, **Capa** y **Cajas acústicas con revestimiento**.</span><span class="sxs-lookup"><span data-stu-id="568fe-144">For operation 20 (Cbnt CtSc), notice that a resource that has two capabilities, **Coating** and **Coated cabinets**, is required.</span></span>

    ![Capacidades de Capa y cajas acústicas con revestimiento en la ficha de los requisitos de recursos](./media/subcontract06_resource-requirements-tab.png)

8. <span data-ttu-id="568fe-146">Seleccione **Recursos aplicables** para abrir el cuadro de diálogo **Recursos aplicables**.</span><span class="sxs-lookup"><span data-stu-id="568fe-146">Select **Applicable resources** to open the **Applicable resources** dialog box.</span></span>

    <span data-ttu-id="568fe-147">Se encuentran tres recursos que coinciden con los requisitos de origen para la operación.</span><span class="sxs-lookup"><span data-stu-id="568fe-147">Three resources are found that match the resource requirements for the operation.</span></span> <span data-ttu-id="568fe-148">Observe que los recursos 8851 y 8852 son del tipo **Proveedor**.</span><span class="sxs-lookup"><span data-stu-id="568fe-148">Notice that resources 8851 and 8852 are of the **Vendor** type.</span></span>

    ![Tres recursos apropiados en el cuadro de diálogo Recursos aplicables.](./media/subcontract07_applicable-resources-dialog.png)

9. <span data-ttu-id="568fe-150">Seleccione **Aceptar** para cerrar el cuadro **Recursos aplicables** y regresar a la página **Ruta**.</span><span class="sxs-lookup"><span data-stu-id="568fe-150">Select **OK** to close the **Applicable resources** dialog box and return to the **Route** page.</span></span>
10. <span data-ttu-id="568fe-151">Cierre la página **Ruta** para volver a la página **Detalles de producto emitido**.</span><span class="sxs-lookup"><span data-stu-id="568fe-151">Close the **Route** page to return to the **Released product details** page.</span></span>

    ![Página de detalles de productos emitidos](./media/subcontract08_released-product-details-page.png)

11. <span data-ttu-id="568fe-153">En el panel de acciones, en la pestaña **Ingeniero**, seleccione **Versiones de L. MAT** para abrir la página **Versiones de L. MAT**.</span><span class="sxs-lookup"><span data-stu-id="568fe-153">On the Action Pane, on the **Engineer** tab, select **BOM versions** to open the **BOM versions** page.</span></span>

    <span data-ttu-id="568fe-154">La página **Versiones de L. MAT** muestra las cuatro versiones de la lista de materiales (L.MAT) del producto emitido D8100.</span><span class="sxs-lookup"><span data-stu-id="568fe-154">The **BOM versions** page shows the four bill of materials (BOM) versions for released product D8100.</span></span> <span data-ttu-id="568fe-155">L.MAT 000040 se utiliza para la gestión de costes y la planificación, L.MAT 000041 se usa si la operación de la capa se realiza internamente, y los L.MAT 000042 y 000043 se usan si se subcontrata la operación de la capa.</span><span class="sxs-lookup"><span data-stu-id="568fe-155">BOM 000040 is used for costing and planning, BOM 000041 is used if the Coating operation is done in-house, and BOMs 000042 and 000043 are used if the Coating operation is subcontracted.</span></span>

    <span data-ttu-id="568fe-156">Tenga en cuenta que el elemento S8050 es un producto del tipo del elemento **Servicio**.</span><span class="sxs-lookup"><span data-stu-id="568fe-156">Notice that item S8050 is a product of the **Service** item type.</span></span> <span data-ttu-id="568fe-157">Este elemento representa el trabajo subcontratado.</span><span class="sxs-lookup"><span data-stu-id="568fe-157">This item represents the subcontracted work.</span></span>

    ![Cuatro versiones de L.MAT en la página de las versiones de L.MAT](./media/subcontract09_bom-versions-page.png)

12. <span data-ttu-id="568fe-159">En la ficha desplegable **Líneas de lista de materiales**, seleccione **Editatr** para abrir el cuadro **Editar línea de L.MAT**.</span><span class="sxs-lookup"><span data-stu-id="568fe-159">On the **Bill of materials lines** FastTab, select **Edit** to open the **Edit BOM line** dialog box.</span></span>

    <span data-ttu-id="568fe-160">Cuando un pedido de producción se crea y se estima para el producto emitido D8100, un pedido de compra se generará automáticamente para el artículo S8050.</span><span class="sxs-lookup"><span data-stu-id="568fe-160">When a production order is created and estimated for released product D8100, a purchase order will be automatically generated for item S8050.</span></span> <span data-ttu-id="568fe-161">Este pedido de compra será vinculado al pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="568fe-161">This purchase order will be linked to the production order.</span></span> <span data-ttu-id="568fe-162">Para que los pedidos de compra se generen automáticamente, el campo **Tipo de línea** se debe establecer en **Proveedor**, y la cuenta del proveedor para el subcontratista se debe seleccionar.</span><span class="sxs-lookup"><span data-stu-id="568fe-162">For purchase orders to be automatically generated, the **Line type** field must be set to **Vendor**, and the vendor account for the subcontractor must be selected.</span></span> <span data-ttu-id="568fe-163">En este caso, la cuenta de proveedor es US-801.</span><span class="sxs-lookup"><span data-stu-id="568fe-163">In this case, the vendor account is US-801.</span></span>

    <span data-ttu-id="568fe-164">Observe que la línea de L.MAT está conectada a la operación de la capa a través del número de operación (en este caso, 20).</span><span class="sxs-lookup"><span data-stu-id="568fe-164">Notice that the BOM line is connected to the Coating operation through the operation number (in this case, 20).</span></span>

    ![Edición del cuadro de diálogo de la línea de L MAT](./media/subcontract10_edit-bom-line-dialog.png)

### <a name="create-a-password-for-warehouse-workers"></a><span data-ttu-id="568fe-166">Crear una contraseña para los trabajadores de almacén</span><span class="sxs-lookup"><span data-stu-id="568fe-166">Create a password for warehouse workers</span></span>

<span data-ttu-id="568fe-167">Debe definir una contraseña para los trabajadores de almacén que usan el dispositivo de mano.</span><span class="sxs-lookup"><span data-stu-id="568fe-167">You must define a password for the warehouse workers who use the hand-held device.</span></span>

1. <span data-ttu-id="568fe-168">Seleccione **Administración de almacenes \> Configuración \> Trabajador** para abrir la página **Usuarios de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="568fe-168">Select **Warehouse management \> Setup \> Worker** to open the **Work users** page.</span></span>
2. <span data-ttu-id="568fe-169">En la ficha desplegable **Usuarios**, seleccione la fila del usuario **51**.</span><span class="sxs-lookup"><span data-stu-id="568fe-169">On the **Users** FastTab, select the row for user **51**.</span></span>

    ![Página de usuario de trabajo](./media/subcontract11_work-users-page.png)

3. <span data-ttu-id="568fe-171">Seleccione **Restablecer contraseña**.</span><span class="sxs-lookup"><span data-stu-id="568fe-171">Select **Reset password**.</span></span>
4. <span data-ttu-id="568fe-172">En los campos **Contraseña** y **Confirmar contraseñas**, especifique **1**.</span><span class="sxs-lookup"><span data-stu-id="568fe-172">In the **Password** and **Confirm password** fields, enter **1**.</span></span>
5. <span data-ttu-id="568fe-173">Seleccione **Establecer contraseña**.</span><span class="sxs-lookup"><span data-stu-id="568fe-173">Select **Set password**.</span></span>

## <a name="step-by-step-walkthrough"></a><span data-ttu-id="568fe-174">Tutorial paso a paso</span><span class="sxs-lookup"><span data-stu-id="568fe-174">Step-by-step walkthrough</span></span>

<span data-ttu-id="568fe-175">**Escenario y antecedentes**</span><span class="sxs-lookup"><span data-stu-id="568fe-175">**Scenario and background**</span></span>

<span data-ttu-id="568fe-176">Un pedido de producción de 10 piezas se crea para el producto D8100, “Caja acústica con revestimiento”.</span><span class="sxs-lookup"><span data-stu-id="568fe-176">A production order of 10 pieces is created for product D8100, "Coated Cabinet."</span></span> <span data-ttu-id="568fe-177">La capa de las cajas acústicas es una operación subcontratada que se realiza en los locales del proveedor, US-801, Perfect Coating Solutions.</span><span class="sxs-lookup"><span data-stu-id="568fe-177">The coating of the cabinets is a sub-contracted operation that is done at vendor US-801, Perfect Coating Solutions.</span></span> <span data-ttu-id="568fe-178">El pedido de producción está formado por tres operaciones.</span><span class="sxs-lookup"><span data-stu-id="568fe-178">The production order consists of three operations.</span></span> <span data-ttu-id="568fe-179">En la primera operación, la caja acústica se monta previamente como operación interna.</span><span class="sxs-lookup"><span data-stu-id="568fe-179">In the first operation, the cabinet is pre-assembled as an in-house operation.</span></span> <span data-ttu-id="568fe-180">El material para el preensamblado se libera para seleccionar en el almacén de la materia prima.</span><span class="sxs-lookup"><span data-stu-id="568fe-180">The material for the pre-assembly is released for picking in the raw material warehouse.</span></span> <span data-ttu-id="568fe-181">Una vez que el ensamblado previo se ha completado, la caja acústica montada previamente se envía a Perfect Coating Solutions junto con dos materiales necesarios para la operación de la capa.</span><span class="sxs-lookup"><span data-stu-id="568fe-181">After the pre-assembly is completed, the pre-assembled cabinet is sent to Perfect Coating Solutions together with two materials that are required for the Coating operation.</span></span> <span data-ttu-id="568fe-182">Cuando se recibe la caja acústica con revestimiento del proveedor, esta pasa por una operación de ensamblado interna final antes de que se notifique como terminada.</span><span class="sxs-lookup"><span data-stu-id="568fe-182">When the coated cabinet is received back from the vendor, it goes through a final in-house assembly operation before it's reported as finished.</span></span>

1. <span data-ttu-id="568fe-183">Seleccione **Control de producción \> Pedidos de producción \> Todos los pedidos de producción** para abrir la página **Todos los pedidos de producción**.</span><span class="sxs-lookup"><span data-stu-id="568fe-183">Select **Production control \> Production orders \> All production orders** to open the **All production orders** page.</span></span>
2. <span data-ttu-id="568fe-184">En el panel de acciones, seleccione **Nuevo pedido de producción** para abrir el cuadro **Crear orden de producción**.</span><span class="sxs-lookup"><span data-stu-id="568fe-184">On the Action Pane, select **New production order** to open the **Create production order** dialog box.</span></span>

    ![Cuadro de diálogo Crear un pedido de producción](./media/subcontract12_create-production-order-dialog.png)

3. <span data-ttu-id="568fe-186">En el campo **Código de artículo**, seleccione **D8100**.</span><span class="sxs-lookup"><span data-stu-id="568fe-186">In the **Item number** field, select **D8100**.</span></span>
4. <span data-ttu-id="568fe-187">Después de seleccionar el número de elemento, se muestran los campos para las dimensiones del inventario.</span><span class="sxs-lookup"><span data-stu-id="568fe-187">After you select the item number, fields for the inventory dimensions appear.</span></span> <span data-ttu-id="568fe-188">En el campo **Color**, seleccione **Cromo**.</span><span class="sxs-lookup"><span data-stu-id="568fe-188">In the **Color** field, select **Chrome**.</span></span>

    <span data-ttu-id="568fe-189">Un cuadro de mensaje aparece que pregunta si las versiones activas de la lista de materiales y la ruta deben insertarse.</span><span class="sxs-lookup"><span data-stu-id="568fe-189">A message box appears that asks whether the active versions for the BOM and route should be inserted.</span></span>

    ![Cuadro de mensaje](./media/subcontract13_message-box.png)

5. <span data-ttu-id="568fe-191">Seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="568fe-191">Select **Yes**.</span></span> 

    <span data-ttu-id="568fe-192">En el cuadro de diálogo **Crear orden de producción**, las versiones activas de L. MAT y la ruta para el producto D8100 se seleccionan automáticamente en los campos **Número de L.MAT** y **Número de ruta** respectivamente.</span><span class="sxs-lookup"><span data-stu-id="568fe-192">In the **Create production order** dialog box, the active versions of the BOM and route for product D8100 are automatically selected in the **BOM number** and **Route number** fields, respectively.</span></span> <span data-ttu-id="568fe-193">En este caso, se seleccionan L. MAT **000040** y la ruta **000040**.</span><span class="sxs-lookup"><span data-stu-id="568fe-193">In this case, BOM **000040** and route **000040** are selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="568fe-194">Para la L. MAT y la ruta, se usa la versión 000040 para la gestión de costes y la planificación.</span><span class="sxs-lookup"><span data-stu-id="568fe-194">For both the BOM and the route, version 000040 is used for costing and planning.</span></span>

6. <span data-ttu-id="568fe-195">En el campo **Sitio**, seleccione **5**.</span><span class="sxs-lookup"><span data-stu-id="568fe-195">In the **Site** field, select **5**.</span></span>
7. <span data-ttu-id="568fe-196">En el campo **Almacén**, seleccione **51**.</span><span class="sxs-lookup"><span data-stu-id="568fe-196">In the **Warehouse** field, select **51**.</span></span>
8. <span data-ttu-id="568fe-197">En los campos **Número de L. MAT** y **Número de ruta**, cambie el valor que se ha seleccionado automáticamente para **000042**.</span><span class="sxs-lookup"><span data-stu-id="568fe-197">In the **BOM number** and **Route number** fields, change the value that was automatically selected to **000042**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="568fe-198">Para la L. MAT y la ruta, la versión 000042 se utiliza para subcontratar la capa de la caja acústica con el proveedor US-801.</span><span class="sxs-lookup"><span data-stu-id="568fe-198">For both the BOM and the route, version 000042 is used to subcontract the coating of the cabinet to vendor US-801.</span></span>

    ![Valores establecidos en el cuadro de diálogo Crear pedido de producción](./media/subcontract14_create-production-order-dialog-set.png)

9. <span data-ttu-id="568fe-200">Seleccione **Crear** para crear el pedido de producción y regresar a la página **Todos los pedidos de producción**.</span><span class="sxs-lookup"><span data-stu-id="568fe-200">Select **Create** to create the production order and return to the **All production orders** page.</span></span>

    ![Nuevo pedido de producción en la página Todos los pedidos de producción](./media/subcontract15_new-production-order.png)

10. <span data-ttu-id="568fe-202">En el panel de acciones, en la ficha **Pedido de producción**, seleccione **Estimación** para abrir el cuadro **Estimación**.</span><span class="sxs-lookup"><span data-stu-id="568fe-202">On the Action Pane, on the **Production order** tab, select **Estimate** to open the **Estimate** dialog box.</span></span>

    ![Cuadro de diálogo Estimación](./media/subcontract16_estimate-dialog.png)

11. <span data-ttu-id="568fe-204">Seleccione **Aceptar** para confirmar la estimación y regresar a la página **Todos los pedidos de producción**.</span><span class="sxs-lookup"><span data-stu-id="568fe-204">Select **OK** to confirm the estimate and return to the **All production orders** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="568fe-205">Cuando se estima el pedido de producción, el pedido de compra del artículo de servicio S8050 se genera para el proveedor US-801.</span><span class="sxs-lookup"><span data-stu-id="568fe-205">When the production order is estimated, the purchase order for service item S8050 is generated for vendor US-801.</span></span>

12. <span data-ttu-id="568fe-206">En el panel de acciones, en la pestaña **pedido de producción**, seleccione **L. MAT** para abrir la página **L. MAT**, donde puede ver las líneas de L. MAT para el pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="568fe-206">On the Action Pane, on the **Production order** tab, select **BOM** to open the **BOM** page, where you can view the BOM lines for the production order.</span></span>

    <span data-ttu-id="568fe-207">Para el artículo de servicio S8050, observe que se hace referencia al pedido de compra que se ha generado cuando se estimó al pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="568fe-207">For service item S8050, notice that there is a reference to the purchase order that was generated when the production order was estimated.</span></span>

    ![Líneas de L. MAT del pedido de producción en la página de L. MAT](./media/subcontract17_production-order-bom-lines.png)

13. <span data-ttu-id="568fe-209">Cierre la página **L. MAT** para regresar a la página **Todos los pedidos de producción**.</span><span class="sxs-lookup"><span data-stu-id="568fe-209">Close the **BOM** page to return to the **All production orders** page.</span></span>
14. <span data-ttu-id="568fe-210">En el panel de acciones, en la ficha **Programación**, seleccione **Programar trabajos** para abrir el cuadro de diálogo **Programación de trabajos**.</span><span class="sxs-lookup"><span data-stu-id="568fe-210">On the Action Pane, on the **Schedule** tab, select **Schedule jobs** to open the **Job scheduling** dialog box.</span></span>
15. <span data-ttu-id="568fe-211">Especifique los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="568fe-211">Specify the following values:</span></span>

    - <span data-ttu-id="568fe-212">En el campo **Dirección de programación**, seleccione **Remitir a partir de hoy**.</span><span class="sxs-lookup"><span data-stu-id="568fe-212">In the **Scheduling direction** field, select **Forward from tomorrow**.</span></span>
    - <span data-ttu-id="568fe-213">Establezca la opción **Capacidad limitada** a **Sí**.</span><span class="sxs-lookup"><span data-stu-id="568fe-213">Set the **Finite capacity** option to **Yes**.</span></span>

    ![Cuadro de diálogo Programación de trabajos](./media/subcontract18_job-scheduling-dialog.png)

16. <span data-ttu-id="568fe-215">Seleccione **Aceptar** para cerrar el cuadro **Programación de trabajos** y regresar a la página **Todos los pedidos de producción**.</span><span class="sxs-lookup"><span data-stu-id="568fe-215">Select **OK** to close the **Job scheduling** dialog box and return to the **All production orders** page.</span></span>
17. <span data-ttu-id="568fe-216">En el panel de acciones, en la pestaña **Programación**, seleccione **Gantt** para abrir la página **Diagrama de Gantt - vista de recursos**.</span><span class="sxs-lookup"><span data-stu-id="568fe-216">On the Action Pane, on the **Schedule** tab, select **Gantt** to open the **Gantt chart - Resource view** page.</span></span>

    <span data-ttu-id="568fe-217">El gráfico de Gantt proporciona una visión general visual de cómo los trabajos de producción se programan en los recursos.</span><span class="sxs-lookup"><span data-stu-id="568fe-217">The Gantt chart provides a visual overview of how the production jobs are scheduled on the resources.</span></span> <span data-ttu-id="568fe-218">Observe que la operación de capa externa consta de tres trabajos: un trabajo de proceso, un trabajo de transporte, y un trabajo de tiempo en cola.</span><span class="sxs-lookup"><span data-stu-id="568fe-218">Notice that the external Coating operation consists of three jobs: a process job, a transport job, and a queue time job.</span></span>

    ![Diagrama de Gantt en el gráfico de Gantt - página de la vista de recursos](./media/subcontract19_gantt-chart.png)

18. <span data-ttu-id="568fe-220">Cierre la página **Diagrama de Gantt - vista de recursos** para regresar a la página **Todos los pedidos de producción**.</span><span class="sxs-lookup"><span data-stu-id="568fe-220">Close the **Gantt chart - Resource view** page to return to the **All production orders** page.</span></span>
19. <span data-ttu-id="568fe-221">En el panel de acciones, en la ficha **Pedido de producción**, seleccione **Liberar** para abrir el cuadro **Liberar**.</span><span class="sxs-lookup"><span data-stu-id="568fe-221">On the Action Pane, on the **Production order** tab, select **Release** to open the **Release** dialog box.</span></span>

    ![Cuadro de diálogo Liberar](./media/subcontract20_release-dialog.png)

20. <span data-ttu-id="568fe-223">Seleccione **Aceptar** para cerrar el cuadro de diálogo **Liberar**.</span><span class="sxs-lookup"><span data-stu-id="568fe-223">Select **OK** to close the **Release** dialog box.</span></span>
21. <span data-ttu-id="568fe-224">Seleccione **Control de producción \> Tareas periódicas \> Liberar al almacén \> Liberación automática de L. MAT. y líneas de fórmula** para abrir el cuadro de diálogo **Liberación automática de L. MAT. y líneas de fórmula**.</span><span class="sxs-lookup"><span data-stu-id="568fe-224">Select **Production control \> Periodic tasks \> Release to warehouse \> Automatic release of BOM and formula lines** to open the **Automatic release of BOM and formula lines** dialog box.</span></span>

    ![Cuadro de diálogo Liberación automática de L. MAT. y líneas de fórmula](./media/subcontract21_auto-release-bom-formula-lines-dialog.png)

22. <span data-ttu-id="568fe-226">Seleccione **Aceptar** para ejecutar el trabajo de liberación automática de L. MAT y líneas de fórmula.</span><span class="sxs-lookup"><span data-stu-id="568fe-226">Select **OK** to run the Automatic release of BOM and formula lines job.</span></span>

    <span data-ttu-id="568fe-227">Este trabajo libera el trabajo de selección de materias primas al almacén.</span><span class="sxs-lookup"><span data-stu-id="568fe-227">This job releases pick work for raw materials to the warehouse.</span></span>

23. <span data-ttu-id="568fe-228">Seleccione **Control de producción \> Pedidos de producción \> Todos los pedidos de producción** para abrir la página **Todos los pedidos de producción**.</span><span class="sxs-lookup"><span data-stu-id="568fe-228">Select **Production control \> Production orders \> All production orders** to open the **All production orders** page.</span></span>
24. <span data-ttu-id="568fe-229">Use el campo de filtro rápido para seleccionar el pedido de producción en el que ha estado trabajando.</span><span class="sxs-lookup"><span data-stu-id="568fe-229">Use the quick filter field to select the production order that you've been working on.</span></span>
25. <span data-ttu-id="568fe-230">En el panel de acciones, en la pestaña **Almacén**, seleccione **Detalles del trabajo** para abrir la página **Trabajo**.</span><span class="sxs-lookup"><span data-stu-id="568fe-230">On the Action Pane, on the **Warehouse** tab, select **Work details** to open the **Work** page.</span></span>

    <span data-ttu-id="568fe-231">Observe que la página muestra dos conjuntos de trabajos para la selección de la materia prima.</span><span class="sxs-lookup"><span data-stu-id="568fe-231">Notice that the page shows two sets of work for raw material picking.</span></span> <span data-ttu-id="568fe-232">El primer trabajo es para los materiales M8100 y M8101.</span><span class="sxs-lookup"><span data-stu-id="568fe-232">The first work is for materials M8100 and M8101.</span></span> <span data-ttu-id="568fe-233">Estos materiales los consume la operación 10.</span><span class="sxs-lookup"><span data-stu-id="568fe-233">These materials are consumed by operation 10.</span></span> <span data-ttu-id="568fe-234">El segundo trabajo es para los materiales M8202 y M8250.</span><span class="sxs-lookup"><span data-stu-id="568fe-234">The second work is for materials M8202 and M8250.</span></span> <span data-ttu-id="568fe-235">Estos materiales los consume la operación 20, que es la operación subcontratada.</span><span class="sxs-lookup"><span data-stu-id="568fe-235">These materials are consumed by operation 20, which is the subcontracted operation.</span></span>

    ![Dos conjuntos de trabajos para la selección de la materia prima en la página Trabajo](./media/subcontract22_work-page.png)

26. <span data-ttu-id="568fe-237">Inicie la aplicación del almacén para procesar el trabajo del almacén para la operación 10.</span><span class="sxs-lookup"><span data-stu-id="568fe-237">Start the warehouse app to process the warehouse work for operation 10.</span></span>

    <!-- TBD – screen shots for processing pick work for the materials. -->

27. <span data-ttu-id="568fe-238">Seleccione **Control de producción \> Pedidos de producción \> Todos los pedidos de producción** para abrir la página **Todos los pedidos de producción**.</span><span class="sxs-lookup"><span data-stu-id="568fe-238">Select **Production control \> Production orders \> All production orders** to open the **All production orders** page.</span></span>
28. <span data-ttu-id="568fe-239">Use el campo de filtro rápido para seleccionar el pedido de producción en el que ha estado trabajando.</span><span class="sxs-lookup"><span data-stu-id="568fe-239">Use the quick filter field to select the production order that you've been working on.</span></span>
29. <span data-ttu-id="568fe-240">En el panel de acciones, en la ficha **Pedido de producción**, seleccione **Inicio** para abrir el cuadro **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="568fe-240">On the Action Pane, on the **Production order** tab, select **Start** to open the **Start** dialog box.</span></span>
30. <span data-ttu-id="568fe-241">En la ficha **General**, especifique los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="568fe-241">On the **General** tab, specify the following values:</span></span>

    - <span data-ttu-id="568fe-242">En el campo **Desde n.º oper.**</span><span class="sxs-lookup"><span data-stu-id="568fe-242">In the **From Oper. No.**</span></span> <span data-ttu-id="568fe-243">seleccione **10**.</span><span class="sxs-lookup"><span data-stu-id="568fe-243">field, select **10**.</span></span>
    - <span data-ttu-id="568fe-244">En el campo **Hasta n.º oper.**</span><span class="sxs-lookup"><span data-stu-id="568fe-244">In the **To Oper. No.**</span></span> <span data-ttu-id="568fe-245">seleccione **10**.</span><span class="sxs-lookup"><span data-stu-id="568fe-245">field, select **10**.</span></span>

    ![Valores definidos en la ficha General](./media/subcontract23_start-dialog.png)

31. <span data-ttu-id="568fe-247">Seleccione **Aceptar** para cerrar el cuadro **Inicio** y regresar a la página **Todos los pedidos de producción**.</span><span class="sxs-lookup"><span data-stu-id="568fe-247">Select **OK** to close the **Start** dialog box and return to the **All production orders** page.</span></span>

    <span data-ttu-id="568fe-248">Tenga en cuenta que el estado del pedido de producción ahora es **Iniciado**.</span><span class="sxs-lookup"><span data-stu-id="568fe-248">Notice that the status of the production order is now **Started**.</span></span> <span data-ttu-id="568fe-249">El material para la operación 10 es consumido por un registro automático del diario de lista de selección.</span><span class="sxs-lookup"><span data-stu-id="568fe-249">The materials for operation 10 are consumed by an automatic posting of the picking list journal.</span></span> <span data-ttu-id="568fe-250">El consumo de tiempo para la operación 10 se indica mediante un registro automático de un diario de tarjeta de ruta.</span><span class="sxs-lookup"><span data-stu-id="568fe-250">Time consumption for operation 10 is accounted for by an automatic posting of a route card journal.</span></span>

32. <span data-ttu-id="568fe-251">Inicie la aplicación del almacén para procesar el trabajo del almacén para la operación 20.</span><span class="sxs-lookup"><span data-stu-id="568fe-251">Start the warehouse app to process the warehouse work for operation 20.</span></span>

    <!-- TBD – screen shots for processing pick work for the materials. -->

33. <span data-ttu-id="568fe-252">En el panel de acciones, en la ficha **Pedido de producción**, seleccione **Inicio** para abrir el cuadro **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="568fe-252">On the Action Pane, on the **Production order** tab, select **Start** to open the **Start** dialog box.</span></span>
34. <span data-ttu-id="568fe-253">En la ficha **General**, especifique los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="568fe-253">On the **General** tab, specify the following values:</span></span>

    - <span data-ttu-id="568fe-254">En el campo **Desde n.º oper.**</span><span class="sxs-lookup"><span data-stu-id="568fe-254">In the **From Oper. No.**</span></span> <span data-ttu-id="568fe-255">seleccione **20**.</span><span class="sxs-lookup"><span data-stu-id="568fe-255">field, select **20**.</span></span>
    - <span data-ttu-id="568fe-256">En el campo **Hasta n.º oper.**</span><span class="sxs-lookup"><span data-stu-id="568fe-256">In the **To Oper. No.**</span></span> <span data-ttu-id="568fe-257">seleccione **20**.</span><span class="sxs-lookup"><span data-stu-id="568fe-257">field, select **20**.</span></span>
    - <span data-ttu-id="568fe-258">En el campo **Cantidad**, especifique **10**.</span><span class="sxs-lookup"><span data-stu-id="568fe-258">In the **Quantity** field, enter **10**.</span></span>
    - <span data-ttu-id="568fe-259">Establezca la opción **Registrar ahora la lista de selección** en **No**.</span><span class="sxs-lookup"><span data-stu-id="568fe-259">Set the **Post picking list now** option to **No**.</span></span>

    ![Valores definidos en la ficha General](./media/subcontract24_general-tab.png)

35. <span data-ttu-id="568fe-261">Seleccione **Aceptar** para cerrar el cuadro **Inicio** y regresar a la página **Todos los pedidos de producción**.</span><span class="sxs-lookup"><span data-stu-id="568fe-261">Select **OK** to close the **Start** dialog box and return to the **All production orders** page.</span></span>

    <span data-ttu-id="568fe-262">Se crea una lista de selección para los materiales que se utilizan para la operación de la capa, y para el artículo de servicio.</span><span class="sxs-lookup"><span data-stu-id="568fe-262">A picking list is created for the materials that are used for the Coating operation, and for the service item.</span></span> <span data-ttu-id="568fe-263">El artículo de servicio representa el coste de la operación subcontratada.</span><span class="sxs-lookup"><span data-stu-id="568fe-263">The service item represents the cost of the subcontracted operation.</span></span>

36. <span data-ttu-id="568fe-264">En el panel de acciones, en la pestaña **Ver**, seleccione **Lista de selección** para abrir la página **Lista de selección**.</span><span class="sxs-lookup"><span data-stu-id="568fe-264">On the Action Pane, on the **View** tab, select **Picking list** to open the **Picking list** page.</span></span>
37. <span data-ttu-id="568fe-265">Seleccione la lista de selección que no está registrada, y seleccione el número de diario para ver las líneas de diario.</span><span class="sxs-lookup"><span data-stu-id="568fe-265">Select the picking list that isn't posted, and then select the journal number to view the journal lines.</span></span>

    ![Líneas del diario en la página lista de selección](./media/subcontract25_picking-list.png)

38. <span data-ttu-id="568fe-267">En el panel de acciones, seleccione **Imprimir** \> **Informe de lista de selección** para abrir el cuadro de diálogo **Informe de lista de selección**.</span><span class="sxs-lookup"><span data-stu-id="568fe-267">On the Action Pane, select **Print** \> **Picking list report** to open the **Picking list report** dialog box.</span></span>
39. <span data-ttu-id="568fe-268">Establezca la opción **Utilizar diseño de nota de entrega** a **Sí**.</span><span class="sxs-lookup"><span data-stu-id="568fe-268">Set the **Use delivery note layout** option to **Yes**.</span></span>

    ![Cuadro de diálogo Informe Lista de selección](./media/subcontract26_picking-list-report-dialog.png)

40. <span data-ttu-id="568fe-270">Seleccione **Aceptar** para generar un informe de **lista de selección**.</span><span class="sxs-lookup"><span data-stu-id="568fe-270">Select **OK** to generate a **Picking list** report.</span></span>

    <span data-ttu-id="568fe-271">En este caso, una nota de entrega de proveedor se imprime desde el diario de lista de selección de producción.</span><span class="sxs-lookup"><span data-stu-id="568fe-271">In this case, a vendor delivery note is printed from the production picking list journal.</span></span> <span data-ttu-id="568fe-272">La nota de entrega especifica los materiales que se envían al proveedor que realizará la operación de capa.</span><span class="sxs-lookup"><span data-stu-id="568fe-272">The delivery note specifies the materials that are shipped to the vendor who will do the Coating operation.</span></span>

    ![Informe de lista de selección](./media/subcontract27_picking-list-report.png)

41. <span data-ttu-id="568fe-274">Cierre el informe **lista de selección** para volver a la página **lista de selección**.</span><span class="sxs-lookup"><span data-stu-id="568fe-274">Close the **Picking list** report to return to the **Picking list** page.</span></span>
42. <span data-ttu-id="568fe-275">En el panel de acciones, seleccione **Registrar** para abrir el cuadro de diálogo **Registrar diario**.</span><span class="sxs-lookup"><span data-stu-id="568fe-275">On the Action Pane, select **Post** to open the **Post journal** dialog box.</span></span>

    ![Cuadro de diálogo Registrar diario](./media/subcontract28_post-journal-dialog.png)

43. <span data-ttu-id="568fe-277">Seleccione **Aceptar** para cerrar el cuadro de diálogo **Registrar diario**.</span><span class="sxs-lookup"><span data-stu-id="568fe-277">Select **OK** to close the **Post journal** dialog box.</span></span>
44. <span data-ttu-id="568fe-278">Abra el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="568fe-278">Open the purchase order.</span></span>

    ![Página Pedido de compra](./media/subcontract29_purchase-order-page.png)

45. <span data-ttu-id="568fe-280">En el panel de acciones, en la pestaña **Compra**, seleccione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="568fe-280">On the Action Pane, on the **Purchase** tab, select **Confirm**.</span></span>
46. <span data-ttu-id="568fe-281">Seleccione **Registrar** para abrir el cuadro de diálogo **Registrar diario**.</span><span class="sxs-lookup"><span data-stu-id="568fe-281">Select **Post** to open the **Post journal** dialog box.</span></span>
47. <span data-ttu-id="568fe-282">Seleccione **Aceptar** para cerrar el cuadro de diálogo **Registrar diario** y regresar a la página **Pedido de compra**.</span><span class="sxs-lookup"><span data-stu-id="568fe-282">Select **OK** to close the **Post journal** dialog box and return to the **Purchase order** page.</span></span>
48. <span data-ttu-id="568fe-283">Cambie el precio unitario de **33** a **40**.</span><span class="sxs-lookup"><span data-stu-id="568fe-283">Change the unit price from **33** to **40**.</span></span>

    ![Precio por unidad cambiado en la página del pedido de compra](./media/subcontract30_unit-price.png)

49. <span data-ttu-id="568fe-285">Confirme el pedido de compra de nuevo.</span><span class="sxs-lookup"><span data-stu-id="568fe-285">Confirm the purchase order again.</span></span>
50. <span data-ttu-id="568fe-286">Recepción de producto.</span><span class="sxs-lookup"><span data-stu-id="568fe-286">Product receipt.</span></span>

    ![Cuadro de diálogo Registro de recepción de productos](./media/subcontract31_posting-product-receipt-dialog.png)

51. <span data-ttu-id="568fe-288">Factura de compra.</span><span class="sxs-lookup"><span data-stu-id="568fe-288">Purchase invoice.</span></span>
52. <span data-ttu-id="568fe-289">Actualizar el estado de conciliación.</span><span class="sxs-lookup"><span data-stu-id="568fe-289">Update the match status.</span></span>

    ![Página de factura del proveedor](./media/subcontract32_vendor-invoice-page.png)

53. <span data-ttu-id="568fe-291">Notificar como terminado.</span><span class="sxs-lookup"><span data-stu-id="568fe-291">Report as finished.</span></span>

    ![Cuadro de diálogo Notificar como terminado](./media/subcontract33_report-as-finished-dialog.png)

54. <span data-ttu-id="568fe-293">Fin.</span><span class="sxs-lookup"><span data-stu-id="568fe-293">End.</span></span>

    ![Cuadro de diálogo Fin](./media/subcontract34_end-dialog.png)

55. <span data-ttu-id="568fe-295">Comparación del coste.</span><span class="sxs-lookup"><span data-stu-id="568fe-295">Cost comparison.</span></span>

    ![Gráficos de comparación del coste](./media/subcontract35_cost-comparison-charts.png)

<span data-ttu-id="568fe-297">Configuración que falta en datos.</span><span class="sxs-lookup"><span data-stu-id="568fe-297">Missing setup in data.</span></span>
