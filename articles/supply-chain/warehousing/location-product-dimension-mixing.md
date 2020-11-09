---
title: Combinación de dimensiones de producto de ubicación
description: Este tema proporciona información acerca de la combinación de dimensiones de producto de ubicación. Esta funcionalidad de perfil de ubicación ayuda a mejorar la administración de ubicación cuando se utilizan variantes de productos o productos que tienen dimensiones, como en la industria de la moda. Le permite decidir si las configuraciones, colores, estilos y tallas se pueden mezclar para un perfil de ubicación específico, o si solo una de estas dimensiones o una combinación de ellas se puede colocar en la misma ubicación.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 73519f3fe79d3d7d917d3044255f735640b8ccfd
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017170"
---
# <a name="location-product-dimension-mixing"></a><span data-ttu-id="d0354-105">Combinación de dimensiones de producto de ubicación</span><span class="sxs-lookup"><span data-stu-id="d0354-105">Location product dimension mixing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d0354-106">La combinación de dimensiones de producto de ubicación es una funcionalidad de perfil de ubicación que le ayuda a mejorar la administración de ubicación cuando se utilizan variantes de productos o productos que tienen dimensiones, como en la industria de la moda.</span><span class="sxs-lookup"><span data-stu-id="d0354-106">Location product dimension mixing is location profile functionality that helps improve location management when product variants or products that have dimensions are used, such as in the fashion industry.</span></span> <span data-ttu-id="d0354-107">Le permite decidir si las configuraciones, colores, estilos y tallas se pueden mezclar para un perfil de ubicación específico, o si solo una de estas dimensiones o una combinación de ellas se puede colocar en la misma ubicación.</span><span class="sxs-lookup"><span data-stu-id="d0354-107">It lets you decide whether configurations, colors, styles, and sizes can be mixed for a specific location profile, or whether just one of these dimensions or a combination of them can be put to the same location.</span></span>

## <a name="turn-on-the-location-product-dimension-mixing-feature"></a><span data-ttu-id="d0354-108">Active la función de combinación de dimensiones de producto de ubicación</span><span class="sxs-lookup"><span data-stu-id="d0354-108">Turn on the Location product dimension mixing feature</span></span>

<span data-ttu-id="d0354-109">Antes de que pueda usar la combinación de dimensiones de producto de ubicación, debe activar la función en su sistema.</span><span class="sxs-lookup"><span data-stu-id="d0354-109">Before you can use location product dimension mixing, the feature must be turned on in your system.</span></span> <span data-ttu-id="d0354-110">Los administradores pueden usar el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="d0354-110">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="d0354-111">Allí, la característica se enumera de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="d0354-111">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="d0354-112">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="d0354-112">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="d0354-113">**Nombre de la función:** *Combinación de dimensiones de producto de ubicación*</span><span class="sxs-lookup"><span data-stu-id="d0354-113">**Feature name:** *Location product dimension mixing*</span></span>

## <a name="setup"></a><span data-ttu-id="d0354-114">Configurar</span><span class="sxs-lookup"><span data-stu-id="d0354-114">Setup</span></span>

<span data-ttu-id="d0354-115">Cada ubicación en el almacén requiere un perfil de ubicación asociado que describa las propiedades de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="d0354-115">Every location in the warehouse needs to have a location profile associated with it that describes the properties of the location.</span></span> <span data-ttu-id="d0354-116">Por lo tanto, todas las ubicaciones que usan el mismo perfil de ubicación podrán permitir la mezcla de dimensiones del producto después de que se haya configurado.</span><span class="sxs-lookup"><span data-stu-id="d0354-116">Therefore, all locations that use the same location profile will be able to allow product dimension mixing after it has been set up.</span></span>

### <a name="configure-location-profiles-to-allow-product-dimension-mixing"></a><span data-ttu-id="d0354-117">Configurar perfiles de ubicación para permitir la mezcla de dimensiones del producto</span><span class="sxs-lookup"><span data-stu-id="d0354-117">Configure location profiles to allow product dimension mixing</span></span>

1. <span data-ttu-id="d0354-118">Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Perfiles de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="d0354-118">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="d0354-119">En la lista de perfiles de ubicación, seleccione **GRANEL**.</span><span class="sxs-lookup"><span data-stu-id="d0354-119">In the list of location profiles, select **BULK**.</span></span>
1. <span data-ttu-id="d0354-120">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d0354-120">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="d0354-121">En la ficha desplegable **General** , configure la opción **Habilitar la combinación específica de dimensiones de producto de ubicación** en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="d0354-121">On the **General** FastTab, set the **Enable location product dimension specific mixing** option to *Yes*.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d0354-122">Puede establecer esta opción en *Sí* solo si la opción **Permitir elementos mixtos** está establecida en *No*.</span><span class="sxs-lookup"><span data-stu-id="d0354-122">You can set this option to *Yes* only if the **Allow mixed items** option is set to *No*.</span></span>

1. <span data-ttu-id="d0354-123">En la ficha desplegable **Combinación de dimensión de producto permitida** , establezca la opción **Talla** en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="d0354-123">On the **Allowed product dimension mixing** FastTab, set the **Size** option to *Yes*.</span></span> <span data-ttu-id="d0354-124">En el escenario que se describe en este tema, la combinación solo se puede hacer para productos que tienen diferentes dimensiones de **Talla**.</span><span class="sxs-lookup"><span data-stu-id="d0354-124">In the scenario that is described in this topic, mixing can be done only for products that have different **Size** dimensions.</span></span> <span data-ttu-id="d0354-125">Sin embargo, hay otras opciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="d0354-125">However, other options are also available.</span></span>
1. <span data-ttu-id="d0354-126">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d0354-126">Select **Save**.</span></span>

### <a name="create-a-new-product-master-and-product-variants"></a><span data-ttu-id="d0354-127">Crear un producto maestro nuevo y variantes de producto</span><span class="sxs-lookup"><span data-stu-id="d0354-127">Create a new product master and product variants</span></span>

1. <span data-ttu-id="d0354-128">Vaya a **Gestión de información de productos \> Productos \> Productos maestros**.</span><span class="sxs-lookup"><span data-stu-id="d0354-128">Go to **Product information management \> Products \> Product masters**.</span></span>
1. <span data-ttu-id="d0354-129">En el Panel de acciones, seleccione **Nuevo** para crear un producto maestro.</span><span class="sxs-lookup"><span data-stu-id="d0354-129">On the Action Pane, select **New** to create a product master.</span></span>
1. <span data-ttu-id="d0354-130">En el cuadro de diálogo **Nuevo producto** , establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="d0354-130">In the **New product** dialog box, set the following values:</span></span>

    - <span data-ttu-id="d0354-131">**Tipo de producto:** *Artículo*</span><span class="sxs-lookup"><span data-stu-id="d0354-131">**Product type:** *Item*</span></span>
    - <span data-ttu-id="d0354-132">**Subtipo de producto:** *Producto maestro*</span><span class="sxs-lookup"><span data-stu-id="d0354-132">**Product subtype:** *Product master*</span></span>
    - <span data-ttu-id="d0354-133">**Número de producto:** *B0001*</span><span class="sxs-lookup"><span data-stu-id="d0354-133">**Product number:** *B0001*</span></span>
    - <span data-ttu-id="d0354-134">**Nombre de producto:** *B0001 Talla*</span><span class="sxs-lookup"><span data-stu-id="d0354-134">**Product name:** *B0001 Size*</span></span>
    - <span data-ttu-id="d0354-135">**Grupo de dimensiones de producto:** *Talla*</span><span class="sxs-lookup"><span data-stu-id="d0354-135">**Product dimension group:** *Size*</span></span>
    - <span data-ttu-id="d0354-136">**Tecnología de configuración:** *Variante predefinida*</span><span class="sxs-lookup"><span data-stu-id="d0354-136">**Configuration technology:** *Predefined variant*</span></span>

1. <span data-ttu-id="d0354-137">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d0354-137">Select **OK**.</span></span>
1. <span data-ttu-id="d0354-138">En la página **Detalles de producto** , en la ficha desplegable **General** , establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="d0354-138">On the **Product details** page, on the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="d0354-139">**Generar variantes automáticamente:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="d0354-139">**Generate variants automatically:** *Yes*</span></span>
    - <span data-ttu-id="d0354-140">**Grupo de talla:** *CASUALDHIR*</span><span class="sxs-lookup"><span data-stu-id="d0354-140">**Size group:** *CASUALDHIR*</span></span>

1. <span data-ttu-id="d0354-141">Para ver las variantes predefinidas, en el Panel de acciones, seleccione **Variantes del producto**.</span><span class="sxs-lookup"><span data-stu-id="d0354-141">To view the predefined variants, on the Action Pane, select **Product variants**.</span></span>

    <span data-ttu-id="d0354-142">Aparecerá la página **Variantes del producto** la página con una lista de variantes de la configuración del grupo de tallas.</span><span class="sxs-lookup"><span data-stu-id="d0354-142">The **Product variants** page appears and shows a list of variants from the configuration of the size group.</span></span>

### <a name="release-products-to-the-usmf-company"></a><span data-ttu-id="d0354-143">Lanzar productos a la empresa USMF</span><span class="sxs-lookup"><span data-stu-id="d0354-143">Release products to the USMF company</span></span>

1. <span data-ttu-id="d0354-144">En el panel de acciones, seleccione **Lanzar productos**.</span><span class="sxs-lookup"><span data-stu-id="d0354-144">On the Action Pane, select **Release products**.</span></span>
1. <span data-ttu-id="d0354-145">En la página **Seleccione productos para lanzar** , confirme que el número de producto *B0001* está en la lista y luego seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d0354-145">On the **Select products to release** page, confirm that product number *B0001* is in the list, and then select **Next**.</span></span>
1. <span data-ttu-id="d0354-146">Seleccione **Siguiente** para confirmar las variantes del producto a lanzar.</span><span class="sxs-lookup"><span data-stu-id="d0354-146">Select **Next** to confirm the product variants to release.</span></span>
1. <span data-ttu-id="d0354-147">En la página **Seleccione empresas para lanzar a** , seleccione *USMF* y luego seleccione **Siguiente** para confirmar la selección.</span><span class="sxs-lookup"><span data-stu-id="d0354-147">On the **Select companies to release to** page, select *USMF* , and then select **Next** to confirm the selection.</span></span>
1. <span data-ttu-id="d0354-148">En la página **Confirmar selección** , seleccione **Terminar** para completar el lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="d0354-148">On the **Confirm selection** page, select **Finish** to complete the release.</span></span>

    <span data-ttu-id="d0354-149">Recibe un mensaje "Operación completada".</span><span class="sxs-lookup"><span data-stu-id="d0354-149">You receive an "Operation completed" message.</span></span>

### <a name="update-a-released-product-in-the-usmf-company"></a><span data-ttu-id="d0354-150">Actualizar un producto lanzado en la compañía USMF</span><span class="sxs-lookup"><span data-stu-id="d0354-150">Update a released product in the USMF company</span></span>

1. <span data-ttu-id="d0354-151">Asegúrese de haber iniciado sesión en la empresa **USMF**.</span><span class="sxs-lookup"><span data-stu-id="d0354-151">Make sure that you're signed in to the **USMF** company.</span></span>
1. <span data-ttu-id="d0354-152">Vaya a **Gestión de información de productos \> Productos \> Productos lanzados** para terminar de crear el producto lanzado.</span><span class="sxs-lookup"><span data-stu-id="d0354-152">Go to **Product information management \> Products \> Released products** to finish creating the released product.</span></span>
1. <span data-ttu-id="d0354-153">Encuentre y seleccione el número de artículo *B0001* para abrir la página **Detalles del producto lanzado**.</span><span class="sxs-lookup"><span data-stu-id="d0354-153">Find and select item number *B0001* to open the **Released product details** page.</span></span>
1. <span data-ttu-id="d0354-154">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d0354-154">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="d0354-155">En la ficha desplegable **General** , asegúrese de que el campo **Grupo de modelo de artículo** se establece en *FIFO*.</span><span class="sxs-lookup"><span data-stu-id="d0354-155">On the **General** FastTab, make sure that the **Item model group** field is set to *FIFO*.</span></span>
1. <span data-ttu-id="d0354-156">En el panel Acciones, en la pestaña **Producto** del grupo **Configurar** , seleccione **Grupos de dimensión**.</span><span class="sxs-lookup"><span data-stu-id="d0354-156">On the Action Pane, on the **Product** tab, in the **Set up** group, select **Dimension groups**.</span></span>
1. <span data-ttu-id="d0354-157">Establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="d0354-157">Set the following values:</span></span>

    - <span data-ttu-id="d0354-158">**Grupo de dimensiones de almacenamiento:** *Almacén*</span><span class="sxs-lookup"><span data-stu-id="d0354-158">**Storage dimension group:** *Ware*</span></span>
    - <span data-ttu-id="d0354-159">**Grupo de dimensiones de seguimiento:** *Ninguno*</span><span class="sxs-lookup"><span data-stu-id="d0354-159">**Tracking dimension group:** *None*</span></span>

1. <span data-ttu-id="d0354-160">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d0354-160">Select **OK**.</span></span>
1. <span data-ttu-id="d0354-161">En el panel Acciones, en la pestaña **Producto** del grupo **Configurar** , seleccione **Jerarquía de reservas**.</span><span class="sxs-lookup"><span data-stu-id="d0354-161">On the Action Pane, on the **Product** tab, in the **Set up** group, select **Reservation hierarchy**.</span></span>
1. <span data-ttu-id="d0354-162">Establezca el campo **Jerarquía de reservas** a *Predeterminado* y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d0354-162">Set the **Reservation hierarchy** field to *Default* , and then select **OK**.</span></span>
1. <span data-ttu-id="d0354-163">En la ficha desplegable **General** , en la sección **Administración** , observe que sus selecciones se han actualizado.</span><span class="sxs-lookup"><span data-stu-id="d0354-163">On the **General** FastTab, in the **Administration** section, notice that your selections have been updated.</span></span>
1. <span data-ttu-id="d0354-164">En la ficha desplegable **Compra** , en el campo **Precio** , introduzca *10*.</span><span class="sxs-lookup"><span data-stu-id="d0354-164">On the **Purchase** FastTab, in the **Price** field, enter *10*.</span></span>
1. <span data-ttu-id="d0354-165">En la ficha desplegable **Gestionar costes** , en el campo **Grupo de artículos** , introduzca *Audio*.</span><span class="sxs-lookup"><span data-stu-id="d0354-165">On the **Manage costs** FastTab, in the **Item group** field, enter *Audio*.</span></span>
1. <span data-ttu-id="d0354-166">En la ficha desplegable **Compra** , en el campo **Precio** , introduzca *10*.</span><span class="sxs-lookup"><span data-stu-id="d0354-166">On the **Purchase** FastTab, in the **Price** field, enter *10*.</span></span>
1. <span data-ttu-id="d0354-167">En la ficha desplegable **Almacén** , en el campo **Identificador de grupo de secuencia de unidad** , introduzca *ea*.</span><span class="sxs-lookup"><span data-stu-id="d0354-167">On the **Warehouse** FastTab, in the **Unit sequence group ID** field, enter *ea*.</span></span>
1. <span data-ttu-id="d0354-168">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d0354-168">Select **Save**.</span></span>

### <a name="create-a-location-directive"></a><span data-ttu-id="d0354-169">Crear una directiva de ubicación</span><span class="sxs-lookup"><span data-stu-id="d0354-169">Create a location directive</span></span>

1. <span data-ttu-id="d0354-170">Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="d0354-170">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="d0354-171">En el panel izquierdo, en el campo **Tipo de orden de trabajo** , seleccione *Pedidos de compra*.</span><span class="sxs-lookup"><span data-stu-id="d0354-171">In the left pane, in the **Work order type** field, select *Purchase orders*.</span></span>
1. <span data-ttu-id="d0354-172">En la lista, seleccione la directiva de ubicación que se denomina *24 PO directo*.</span><span class="sxs-lookup"><span data-stu-id="d0354-172">In the list, select the location directive that is named *24 PO Direct*.</span></span>
1. <span data-ttu-id="d0354-173">En la ficha desplegable **Acciones de directiva de ubicación** , seleccione **Nuevo** para agregar una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="d0354-173">On the **Location Directive Actions** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="d0354-174">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="d0354-174">On the new line, set the following values:</span></span>

    - <span data-ttu-id="d0354-175">**Número de secuencia:** *1*</span><span class="sxs-lookup"><span data-stu-id="d0354-175">**Sequence number:** *1*</span></span>

        <span data-ttu-id="d0354-176">La nueva línea debe estar frente a la línea existente anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d0354-176">The new line should be in front of the previously existing line.</span></span> <span data-ttu-id="d0354-177">Para hacer el cambio, use los botones **Mover arriba** y **Mover abajo** en la barra de herramientas, o cambie el valor **Secuencia de números** de las líneas existentes a *2*.</span><span class="sxs-lookup"><span data-stu-id="d0354-177">To make the change, use the **Move up** and **Move down** buttons on the toolbar, or change the existing line's **Sequence number** value to *2*.</span></span>

    - <span data-ttu-id="d0354-178">**Nombre:** *Poner en perfil de ubicación GRANEL*</span><span class="sxs-lookup"><span data-stu-id="d0354-178">**Name:** *Put to BULK Location profile*</span></span>
    - <span data-ttu-id="d0354-179">**Uso de ubicación fija:** *Ubicaciones fijas y no fijas*</span><span class="sxs-lookup"><span data-stu-id="d0354-179">**Fixed location usage:** *Fixed and non-fixed locations*</span></span>
    - <span data-ttu-id="d0354-180">**Permitir inventario negativo:** *desactive esta casilla de verificación (=No)*</span><span class="sxs-lookup"><span data-stu-id="d0354-180">**Allow negative inventory:** *Clear this check box (=No)*</span></span>
    - <span data-ttu-id="d0354-181">**Lote habilitado:** *desactive esta casilla de verificación (=No)*</span><span class="sxs-lookup"><span data-stu-id="d0354-181">**Batch enabled:** *Clear this check box (=No)*</span></span>
    - <span data-ttu-id="d0354-182">**Estrategia:** *Ninguna*</span><span class="sxs-lookup"><span data-stu-id="d0354-182">**Strategy:** *None*</span></span>

1. <span data-ttu-id="d0354-183">Mientras la nueva línea aún está seleccionada, seleccione **Editar consulta** sobre la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="d0354-183">While the new line is still selected, select **Edit query** above the grid.</span></span>
1. <span data-ttu-id="d0354-184">En el cuadro de diálogo de consultas, en la pestaña **Rango** , seleccione **Agregar** para añadir una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="d0354-184">In the query dialog box, on the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="d0354-185">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="d0354-185">On the new line, set the following values:</span></span>

    - <span data-ttu-id="d0354-186">**Tabla** : *Ubicaciones*</span><span class="sxs-lookup"><span data-stu-id="d0354-186">**Table:** *Locations*</span></span>
    - <span data-ttu-id="d0354-187">**Tabla derivada:** *Ubicaciones*</span><span class="sxs-lookup"><span data-stu-id="d0354-187">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="d0354-188">**Campo** : *ID de perfil de ubicación*</span><span class="sxs-lookup"><span data-stu-id="d0354-188">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="d0354-189">**Criterios** : *BULK*</span><span class="sxs-lookup"><span data-stu-id="d0354-189">**Criteria:** *BULK*</span></span>

1. <span data-ttu-id="d0354-190">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d0354-190">Select **OK**.</span></span>
1. <span data-ttu-id="d0354-191">En la página **Directivas de ubicación** , en el panel de acción seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d0354-191">On the **Location directives** page, on the Action Pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="d0354-192">En la ficha desplegable **Acciones de directiva de ubicación** en el campo **Estrategia** , si usa la estrategia de ubicación *Consolidar* , la configuración de la ficha desplegable **Permitir combinación de dimensiones de producto** en los **Perfiles de ubicación** se anulará y los elementos se colocarán en la misma ubicación incluso si la configuración no permite este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="d0354-192">On the **Location Directive Actions** FastTab **Strategy** field, if you use the *Consolidate* location strategy, the setup of the **Allowed product dimension mixing** FastTab on the **Location profiles** will be overridden, and items will be put to the same location even if this behavior isn't allowed by the setup.</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="d0354-193">Crear un elemento de menú del dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="d0354-193">Create a mobile device menu item</span></span>

1. <span data-ttu-id="d0354-194">Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="d0354-194">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="d0354-195">En el Panel de acciones, seleccione **Nuevo** para crear un elemento de menú para usar para ordenar.</span><span class="sxs-lookup"><span data-stu-id="d0354-195">On the Action Pane, select **New** to create a menu item to use for sorting.</span></span>
1. <span data-ttu-id="d0354-196">Establezca los siguientes valores en el encabezado:</span><span class="sxs-lookup"><span data-stu-id="d0354-196">In the header, set the following values:</span></span>

    - <span data-ttu-id="d0354-197">**Nombre del elemento del menú:** *Recepción de línea de pedido*</span><span class="sxs-lookup"><span data-stu-id="d0354-197">**Menu item name:** *PO line receiving*</span></span>
    - <span data-ttu-id="d0354-198">**Título:** *Recepción de línea de pedido*</span><span class="sxs-lookup"><span data-stu-id="d0354-198">**Title:** *PO line receiving*</span></span>
    - <span data-ttu-id="d0354-199">**Modo:** *Trabajo*</span><span class="sxs-lookup"><span data-stu-id="d0354-199">**Mode:** *Work*</span></span>
    - <span data-ttu-id="d0354-200">**Usar trabajo existente:** *No*</span><span class="sxs-lookup"><span data-stu-id="d0354-200">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="d0354-201">En la ficha desplegable **General** , establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="d0354-201">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="d0354-202">**Proceso de creación de trabajo:** *Recepción de línea de pedido de compra y almacenamiento*</span><span class="sxs-lookup"><span data-stu-id="d0354-202">**Work creation process:** *Purchase order line receiving and putaway*</span></span>
    - <span data-ttu-id="d0354-203">**Generar matrícula de entidad de almacén:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="d0354-203">**Generate license plate:** *Yes*</span></span>

1. <span data-ttu-id="d0354-204">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d0354-204">Select **Save**.</span></span>

### <a name="configure-the-mobile-device-menu"></a><span data-ttu-id="d0354-205">Configurar el menú de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="d0354-205">Configure the mobile device menu</span></span>

1. <span data-ttu-id="d0354-206">Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="d0354-206">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="d0354-207">En la lista de menús, seleccione **Entrante**.</span><span class="sxs-lookup"><span data-stu-id="d0354-207">In the list of menus, select **Inbound**.</span></span>
1. <span data-ttu-id="d0354-208">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d0354-208">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="d0354-209">En la lista **Menús disponibles y elementos de menú** , busque y seleccione el elemento de menú **Recepción de línea de pedido**.</span><span class="sxs-lookup"><span data-stu-id="d0354-209">In the **Available Menus And Menu Items** list, find and select the **PO line receiving** menu item.</span></span>
1. <span data-ttu-id="d0354-210">Seleccione el botón de flecha derecha para mover el elemento de menú **Recepción de línea de pedido** a la lista **Estructura del menú**.</span><span class="sxs-lookup"><span data-stu-id="d0354-210">Select the right arrow button to move the **PO line receiving** menu item to the **Menu Structure** list.</span></span> <span data-ttu-id="d0354-211">De esta manera, agrega su nuevo elemento de menú al menú seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d0354-211">In this way, you add your new menu item to the selected menu.</span></span>
1. <span data-ttu-id="d0354-212">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d0354-212">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="d0354-213">Situación</span><span class="sxs-lookup"><span data-stu-id="d0354-213">Scenario</span></span>

<span data-ttu-id="d0354-214">Este escenario de demostración muestra cómo se pueden colocar dos variantes de producto diferentes en la misma ubicación cuando el perfil de ubicación no permite elementos mixtos, pero la función *Combinación de dimensiones de producto de ubicación* está habilitada.</span><span class="sxs-lookup"><span data-stu-id="d0354-214">This demo scenario shows how two different product variants can be put to the same location when the location profile doesn't allow for mixed items, but the *Location product dimension mixing* feature is enabled.</span></span> <span data-ttu-id="d0354-215">En este caso, utilizará la variante **Talla** como criterio.</span><span class="sxs-lookup"><span data-stu-id="d0354-215">In this case, you will use the **Size** variant as the criterion.</span></span>

<span data-ttu-id="d0354-216">Antes de comenzar, asegúrese de que haya ubicaciones vacías en el almacén *24* que usan el perfil de ubicación *GRANEL*.</span><span class="sxs-lookup"><span data-stu-id="d0354-216">Before you begin, make sure that there are empty locations in warehouse *24* that use the *BULK* location profile.</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="d0354-217">Crear un pedido de compra</span><span class="sxs-lookup"><span data-stu-id="d0354-217">Create a purchase order</span></span>

<span data-ttu-id="d0354-218">Creará un pedido de compra que tiene tres líneas: dos líneas para el mismo número de producto pero variantes de **Talla** distintas y una tercera línea para un producto diferente que no tiene variantes.</span><span class="sxs-lookup"><span data-stu-id="d0354-218">You will create a purchase order that has three lines: two lines for the same product number but different **Size** variants, and a third line for a different product that has no variants.</span></span>

1. <span data-ttu-id="d0354-219">Vaya a **Proveedores \> Pedidos de compra \> Todos los pedidos de compra**.</span><span class="sxs-lookup"><span data-stu-id="d0354-219">Go to **Accounts payable \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="d0354-220">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="d0354-220">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="d0354-221">En el cuadro de diálogo **Crear pedido de compras** , establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="d0354-221">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="d0354-222">**Cuenta del proveedor:** *1001*</span><span class="sxs-lookup"><span data-stu-id="d0354-222">**Vendor account:** *1001*</span></span>
    - <span data-ttu-id="d0354-223">**Almacén** : *24*</span><span class="sxs-lookup"><span data-stu-id="d0354-223">**Warehouse:** *24*</span></span>

1. <span data-ttu-id="d0354-224">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d0354-224">Select **OK**.</span></span>
1. <span data-ttu-id="d0354-225">Se crea el pedido de compra y se agrega una nueva línea en la ficha desplegable **Líneas de pedido de compra**.</span><span class="sxs-lookup"><span data-stu-id="d0354-225">The purchase order is created, and a new line is added on the **Purchase order lines** FastTab.</span></span> <span data-ttu-id="d0354-226">Anote el número del pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="d0354-226">Make a note of the purchase order number.</span></span>
1. <span data-ttu-id="d0354-227">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="d0354-227">On the new line, set the following values:</span></span>

    - <span data-ttu-id="d0354-228">**Código de artículo:** *B0001*</span><span class="sxs-lookup"><span data-stu-id="d0354-228">**Item number:** *B0001*</span></span>
    - <span data-ttu-id="d0354-229">**Talla** *L*</span><span class="sxs-lookup"><span data-stu-id="d0354-229">**Size** *L*</span></span>
    - <span data-ttu-id="d0354-230">**Cantidad:** *2*</span><span class="sxs-lookup"><span data-stu-id="d0354-230">**Quantity:** *2*</span></span>

1. <span data-ttu-id="d0354-231">Seleccione **Agregar línea** encima de la cuadrícula para agregar una segunda línea de pedido de compra y establecer los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="d0354-231">Select **Add line** above the grid to add a second purchase order line, and set the following values:</span></span>

    - <span data-ttu-id="d0354-232">**Código de artículo:** *B0001*</span><span class="sxs-lookup"><span data-stu-id="d0354-232">**Item number:** *B0001*</span></span>
    - <span data-ttu-id="d0354-233">**Talla** *XL*</span><span class="sxs-lookup"><span data-stu-id="d0354-233">**Size** *XL*</span></span>
    - <span data-ttu-id="d0354-234">**Cantidad:** *2*</span><span class="sxs-lookup"><span data-stu-id="d0354-234">**Quantity:** *2*</span></span>

1. <span data-ttu-id="d0354-235">Seleccione **Agregar línea** para agregar una tercera línea de pedido de compra y establecer los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="d0354-235">Select **Add line** to add a third purchase order line, and set the following values:</span></span>

    - <span data-ttu-id="d0354-236">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="d0354-236">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="d0354-237">**Cantidad:** *1*</span><span class="sxs-lookup"><span data-stu-id="d0354-237">**Quantity:** *1*</span></span>

<span data-ttu-id="d0354-238">1.Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d0354-238">1.Select **Save**.</span></span>

### <a name="receive-purchase-order-lines-in-the-warehouse-app"></a><span data-ttu-id="d0354-239">Reciba líneas de pedido de compra en la aplicación de almacén</span><span class="sxs-lookup"><span data-stu-id="d0354-239">Receive purchase order lines in the warehouse app</span></span>

1. <span data-ttu-id="d0354-240">Inicie sesión en la aplicación de almacén como un usuario habilitado para el almacén *24*.</span><span class="sxs-lookup"><span data-stu-id="d0354-240">Sign in to the warehouse app as a user who is enabled for warehouse *24*.</span></span>
1. <span data-ttu-id="d0354-241">Seleccione el menú **Entrante**.</span><span class="sxs-lookup"><span data-stu-id="d0354-241">Select the **Inbound** menu.</span></span>
1. <span data-ttu-id="d0354-242">Seleccione **Recepción de línea de pedido**.</span><span class="sxs-lookup"><span data-stu-id="d0354-242">Select **PO Line receiving**.</span></span>
1. <span data-ttu-id="d0354-243">Seleccione el campo **PONUM** e introduzca el número de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="d0354-243">Select the **PONUM** field, and then enter the purchase order number.</span></span>
1. <span data-ttu-id="d0354-244">Confirme su entrada seleccionando el botón de confirmación (✔) en la parte inferior de la página.</span><span class="sxs-lookup"><span data-stu-id="d0354-244">Confirm your entry by selecting the confirm button ( ✔ ) at the bottom of the page.</span></span>
1. <span data-ttu-id="d0354-245">Introduzca el número de línea del pedido de compra que se está recibiendo.</span><span class="sxs-lookup"><span data-stu-id="d0354-245">Enter the line number from the purchase order that is being received.</span></span> <span data-ttu-id="d0354-246">Selecciona el campo **LINENUM** y luego use el teclado numérico para introducir *1*.</span><span class="sxs-lookup"><span data-stu-id="d0354-246">Select the **LINENUM** field, and then use the number pad to enter *1*.</span></span>
1. <span data-ttu-id="d0354-247">Confirme su entrada.</span><span class="sxs-lookup"><span data-stu-id="d0354-247">Confirm your entry.</span></span>
1. <span data-ttu-id="d0354-248">Especifique la cantidad a recibir.</span><span class="sxs-lookup"><span data-stu-id="d0354-248">Enter the quantity to receive.</span></span> <span data-ttu-id="d0354-249">Seleccione el signo más ( **+** ) dos veces para aumentar el valor en el campo **Cantidad** a *2*.</span><span class="sxs-lookup"><span data-stu-id="d0354-249">Select the plus sign ( **+** ) button two times to increase the value in the **Qty** field to *2*.</span></span>
1. <span data-ttu-id="d0354-250">Registre su entrada seleccionando el botón (✔) en la parte inferior de la página, y luego confirme su entrada seleccionando el botón (✔) nuevamente.</span><span class="sxs-lookup"><span data-stu-id="d0354-250">Register your entry by selecting the button ( ✔ ) at the bottom of the page, and then confirm your entry by selecting the button ( ✔ ) again.</span></span>
1. <span data-ttu-id="d0354-251">Ver la información en la página **Órdenes de compra: Colocar**.</span><span class="sxs-lookup"><span data-stu-id="d0354-251">View the information on the **Purchase orders: Put** page.</span></span> <span data-ttu-id="d0354-252">Esta página muestra el trabajo que se ha creado para el almacenamiento (Trabajo 1).</span><span class="sxs-lookup"><span data-stu-id="d0354-252">This page shows the work that has been created for the put-away (Work 1).</span></span>

    <span data-ttu-id="d0354-253">La ubicación donde se guardará el artículo recibido, la matrícula de entidad, el artículo, el tamaño y la cantidad de la tarea **Recibiendo pedido** muestran las tareas que acaba de completar.</span><span class="sxs-lookup"><span data-stu-id="d0354-253">The location where the received item will be put away, the license plate, the item, the size, and the quantity of the **PO Line receiving** task that you just completed are shown.</span></span>

1. <span data-ttu-id="d0354-254">Confirme el trabajo de ubicación.</span><span class="sxs-lookup"><span data-stu-id="d0354-254">Confirm the put-away work.</span></span>
1. <span data-ttu-id="d0354-255">Repita los pasos del 4 al 11 para la línea del pedido de compra 2.</span><span class="sxs-lookup"><span data-stu-id="d0354-255">Repeat the steps 4 through 11 for the purchase order line 2.</span></span> <span data-ttu-id="d0354-256">Sin embargo, en el paso 8, especifique una cantidad de *1*.</span><span class="sxs-lookup"><span data-stu-id="d0354-256">However, in step 8, specify a quantity of *1*.</span></span>

    <span data-ttu-id="d0354-257">Se crea un nuevo trabajo de guardado (Trabajo 2) para la misma ubicación que el Trabajo 1.</span><span class="sxs-lookup"><span data-stu-id="d0354-257">New put-away work (Work 2) is created for the same location as Work 1.</span></span>

1. <span data-ttu-id="d0354-258">Repita los pasos del 4 al 11 de nuevo para la línea del pedido de compra 2.</span><span class="sxs-lookup"><span data-stu-id="d0354-258">Repeat the steps 4 through 11 again for purchase order line 2.</span></span> <span data-ttu-id="d0354-259">Sin embargo, en el paso 8, especifique una cantidad restante de *1*.</span><span class="sxs-lookup"><span data-stu-id="d0354-259">In step 8, specify the remaining quantity of *1*.</span></span>

    <span data-ttu-id="d0354-260">Se crea un nuevo trabajo de guardado (Trabajo 3) para la misma ubicación que el Trabajo 1 y el Trabajo 2.</span><span class="sxs-lookup"><span data-stu-id="d0354-260">New put-away work (Work 3) is created for the same location as Work 1 and Work 2.</span></span> <span data-ttu-id="d0354-261">Este comportamiento se produce porque se usa la estrategia directiva de ubicación de *Consolidar* y la ficha desplegable **Permitir combinación de dimensiones de producto** en la configuración *Granel* de **Perfiles de ubicación** permite a la variante **Talla** combinarse en una ubicación.</span><span class="sxs-lookup"><span data-stu-id="d0354-261">This behavior occurs because the *Consolidate* location directive strategy is used, and the **Allowed product dimension mixing** FastTab on the *Bulk* **Location profiles** setup allows the **Size** variant to be mixed on a location.</span></span>

1. <span data-ttu-id="d0354-262">Repita los pasos del 4 al 11 para la línea del pedido de compra 3.</span><span class="sxs-lookup"><span data-stu-id="d0354-262">Repeat the steps 4 through 11 for purchase order line 3.</span></span> <span data-ttu-id="d0354-263">En el paso 8, especifique una cantidad de *1* para el número de artículo *A0001*.</span><span class="sxs-lookup"><span data-stu-id="d0354-263">In step 8, specify a quantity of *1* for item number *A0001*.</span></span>

    <span data-ttu-id="d0354-264">Se crea un nuevo trabajo de almacenamiento (Trabajo 4) para una ubicación diferente a la ubicación que se utiliza para las líneas de pedido de compra 1 y 2.</span><span class="sxs-lookup"><span data-stu-id="d0354-264">New put-away work (Work 4) is created for a different location than the location that is used for purchase order lines 1 and 2.</span></span> <span data-ttu-id="d0354-265">Este comportamiento se produce porque el perfil de ubicación no permite productos mixtos, pero sí permite dimensiones mixtas del mismo producto maestro.</span><span class="sxs-lookup"><span data-stu-id="d0354-265">This behavior occurs because the location profile doesn't allow for mixed products, but it does allow for mixed dimensions of the same product master.</span></span>

1. <span data-ttu-id="d0354-266">Seleccione el botón Menú en la parte superior de la página (a veces denominado hamburguesa o botón de hamburguesa) y luego seleccione **Cancelar** para salir **Recibiendo línea de pedido de compras**.</span><span class="sxs-lookup"><span data-stu-id="d0354-266">Select the Menu button at the top of the page (sometimes referred to as the hamburger or the hamburger button), and then select **Cancel** to exit **PO Line receiving**.</span></span>

> [!TIP]
> <span data-ttu-id="d0354-267">Puede repetir este escenario, pero esta vez, establezca **Talla** - *No* en la ficha desplegable **Permitir la combinación de dimensiones del producto** en *GRANEL* de **Perfiles de ubicación** , de modo que ninguna de las dimensiones del producto se pueda combinar.</span><span class="sxs-lookup"><span data-stu-id="d0354-267">You can repeat this scenario, but this time, set **Size** - *No* under the **Allow product dimension mixing** FastTab on the *BULK* **Location profiles** , so that none of the product dimensions can be mixed.</span></span> <span data-ttu-id="d0354-268">En este caso, cuando reciba el pedido de compra, cada variante de producto se colocará en una nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="d0354-268">In this case, when you receive the purchase order, each product variant will be put to a new location.</span></span>