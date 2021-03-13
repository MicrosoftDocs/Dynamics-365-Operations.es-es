---
title: Establecer diferentes dimensiones para el embalaje y almacenamiento
description: Este tema muestra cómo especificar para qué proceso (embalaje, almacenamiento o embalaje anidado) se utiliza cada dimensión especificada.
author: mirzaab
manager: tfehr
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPhysDimUOM
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 004d9b4522335b481b640ef0fe35f4db66e3c9f5
ms.sourcegitcommit: b7a7a14f8650913f6797ae1c4a82ad8adfe415fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2021
ms.locfileid: "5078306"
---
# <a name="set-different-dimensions-for-packing-and-storage"></a><span data-ttu-id="e743f-103">Establecer diferentes dimensiones para el embalaje y almacenamiento</span><span class="sxs-lookup"><span data-stu-id="e743f-103">Set different dimensions for packing and storage</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e743f-104">Algunos artículos se empaquetan o almacenan de tal manera que es posible que deba realizar un seguimiento de las dimensiones físicas de manera diferente para cada uno de varios procesos diferentes.</span><span class="sxs-lookup"><span data-stu-id="e743f-104">Some items are packed or stored in such a way that you may need to track physical dimensions differently for each of several different processes.</span></span> <span data-ttu-id="e743f-105">La característica *Dimensiones del producto de embalaje* le permite configurar uno o varios tipos de dimensiones para cada producto.</span><span class="sxs-lookup"><span data-stu-id="e743f-105">The *Packaging product dimensions* feature lets you set up one or several types of dimensions for each product.</span></span> <span data-ttu-id="e743f-106">Cada tipo de dimensión proporciona un conjunto de medidas físicas (peso, ancho, profundidad y altura) y establece el proceso donde se aplican esos valores de medición física.</span><span class="sxs-lookup"><span data-stu-id="e743f-106">Each dimension type provides a set of physical measurements (weight, width, depth, and height), and establishes the process where those physical measurement values apply.</span></span> <span data-ttu-id="e743f-107">Cuando esta función está habilitada, su sistema admitirá los siguientes tipos de dimensiones:</span><span class="sxs-lookup"><span data-stu-id="e743f-107">When this feature is enabled, your system will support the following types of dimensions:</span></span>

- <span data-ttu-id="e743f-108">*Almacenamiento* - Las dimensiones de almacenamiento se utilizan junto con la volumetría de ubicación para determinar cuántos de cada artículo se pueden almacenar en varias ubicaciones de almacén.</span><span class="sxs-lookup"><span data-stu-id="e743f-108">*Storage* - Storage dimensions are used along with location volumetrics to determine how many of each item can be stored in various warehouse locations.</span></span>
- <span data-ttu-id="e743f-109">*Embalaje* - Las dimensiones del embalaje se utilizan durante la colocación en contenedores y el proceso de embalaje manual para determinar cuántos de cada artículo caben en varios tipos de contenedores.</span><span class="sxs-lookup"><span data-stu-id="e743f-109">*Packing* - Packing dimensions are used during containerization and the manual packing process to determine how many of each item will fit in various container types.</span></span>
- <span data-ttu-id="e743f-110">*Embalaje anidado* - Las dimensiones de empaque anidado se utilizan cuando el proceso de empaque contiene múltiples niveles.</span><span class="sxs-lookup"><span data-stu-id="e743f-110">*Nested packing* - Nested packing dimensions are used when the packing process contains multiple levels.</span></span>

<span data-ttu-id="e743f-111">Las dimensiones de *almacenamiento* son compatibles incluso cuando la función *Dimensiones del producto de embalaje* no está habilitada.</span><span class="sxs-lookup"><span data-stu-id="e743f-111">*Storage* dimensions are supported even when the *Packaging product dimensions* feature isn't enabled.</span></span> <span data-ttu-id="e743f-112">Los configura utilizando la página **Dimensión física** en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e743f-112">You set these up using the **Physical dimension** page in Supply Chain Management.</span></span> <span data-ttu-id="e743f-113">Estas dimensiones se utilizan en todos los procesos en los que no se especifican las dimensiones del embalaje y del embalaje anidado.</span><span class="sxs-lookup"><span data-stu-id="e743f-113">These dimensions are used by all processes where the packing and nested packing dimensions aren't specified.</span></span>

<span data-ttu-id="e743f-114">Las dimensiones de *embalaje* y *embalaje anidado* se configuran utilizando la página **Dimensiones físicas del producto**, que se agrega cuando habilita la característica *Dimensiones del producto de embalaje*.</span><span class="sxs-lookup"><span data-stu-id="e743f-114">*Packing* and *nested packing* dimensions are set up using the **Physical product dimensions** page, which is added when you enable the *Packaging product dimensions* feature.</span></span>
<span data-ttu-id="e743f-115">Este tema proporciona un escenario que ilustra cómo utilizar esta función.</span><span class="sxs-lookup"><span data-stu-id="e743f-115">This topic provides a scenario that illustrates how to use this feature.</span></span>

## <a name="turn-on-the-packaging-product-dimensions-feature"></a><span data-ttu-id="e743f-116">Active la función de dimensiones del producto de embalaje</span><span class="sxs-lookup"><span data-stu-id="e743f-116">Turn on the packaging product dimensions feature</span></span>

<span data-ttu-id="e743f-117">Antes de poder usar esta característica debe estar activada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="e743f-117">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="e743f-118">Los administradores pueden usar el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="e743f-118">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="e743f-119">Allí, la característica se enumera de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="e743f-119">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="e743f-120">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="e743f-120">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="e743f-121">**Nombre de característica:** *Dimensiones del producto de embalaje*</span><span class="sxs-lookup"><span data-stu-id="e743f-121">**Feature name:** *Packaging product dimensions*</span></span>

## <a name="example-scenario"></a><span data-ttu-id="e743f-122">Supuesto de ejemplo</span><span class="sxs-lookup"><span data-stu-id="e743f-122">Example scenario</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="e743f-123">Configuración el escenario</span><span class="sxs-lookup"><span data-stu-id="e743f-123">Set up the scenario</span></span>

<span data-ttu-id="e743f-124">Antes de que pueda ejecutar el escenario de ejemplo, debe preparar su sistema como se describe en esta sección.</span><span class="sxs-lookup"><span data-stu-id="e743f-124">Before you can run the example scenario, you must prepare your system as described in this section.</span></span>

#### <a name="enable-demo-data"></a><span data-ttu-id="e743f-125">Active los datos de demostración</span><span class="sxs-lookup"><span data-stu-id="e743f-125">Enable demo data</span></span>

<span data-ttu-id="e743f-126">Para trabajar en este escenario mediante el uso de los registros y valores de demostración que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) estándar.</span><span class="sxs-lookup"><span data-stu-id="e743f-126">To work through this scenario using the demo records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="e743f-127">Además, también debe seleccionar la entidad legal *USMF* antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="e743f-127">Additionally, you must select the *USMF* legal entity before you begin.</span></span>

#### <a name="add-a-new-physical-dimension-to-a-product"></a><span data-ttu-id="e743f-128">Agregar una nueva dimensión física a un producto</span><span class="sxs-lookup"><span data-stu-id="e743f-128">Add a new physical dimension to a product</span></span>

<span data-ttu-id="e743f-129">Agregue una nueva dimensión física para un producto haciendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e743f-129">Add a new physical dimension for a product by doing the following:</span></span>

1. <span data-ttu-id="e743f-130">Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.</span><span class="sxs-lookup"><span data-stu-id="e743f-130">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="e743f-131">Seleccione el número con el **número de artículo** *A0001*.</span><span class="sxs-lookup"><span data-stu-id="e743f-131">Select the product with **Item number** *A0001*.</span></span>
1. <span data-ttu-id="e743f-132">En el panel Acciones, abra la pestaña **Administrar inventario** y, en el grupo **Almacén**, seleccione **Dimensiones del producto físicas**.</span><span class="sxs-lookup"><span data-stu-id="e743f-132">On the Action Pane, open the **Manage inventory** tab and, from the **Warehouse** group, select **Physical product dimensions**.</span></span>
1. <span data-ttu-id="e743f-133">Se abrirá la página **Dimensiones del producto físicas**.</span><span class="sxs-lookup"><span data-stu-id="e743f-133">The **Physical product dimensions** page opens.</span></span> <span data-ttu-id="e743f-134">En el panel de acción, seleccione **Nuevo** para agregar una nueva dimensión a la cuadrícula con los siguientes ajustes:</span><span class="sxs-lookup"><span data-stu-id="e743f-134">On the Action Pane, select **New** to add a new dimension to the grid with the following settings:</span></span>
    - <span data-ttu-id="e743f-135">**Tipo de dimensión física** - *Embalaje*</span><span class="sxs-lookup"><span data-stu-id="e743f-135">**Physical dimension type** - *Packing*</span></span>
    - <span data-ttu-id="e743f-136">**Unidad física** - *uds.*</span><span class="sxs-lookup"><span data-stu-id="e743f-136">**Physical unit** - *pcs*</span></span>
    - <span data-ttu-id="e743f-137">**Peso** - *4*</span><span class="sxs-lookup"><span data-stu-id="e743f-137">**Weight** - *4*</span></span>
    - <span data-ttu-id="e743f-138">**Unidad de peso** - *kg*</span><span class="sxs-lookup"><span data-stu-id="e743f-138">**Weight unit** - *kg*</span></span>
    - <span data-ttu-id="e743f-139">**Profundidad** - *3*</span><span class="sxs-lookup"><span data-stu-id="e743f-139">**Depth** - *3*</span></span>
    - <span data-ttu-id="e743f-140">**Altura** - *4*</span><span class="sxs-lookup"><span data-stu-id="e743f-140">**Height** - *4*</span></span>
    - <span data-ttu-id="e743f-141">**Anchura** - *3*</span><span class="sxs-lookup"><span data-stu-id="e743f-141">**Width** - *3*</span></span>
    - <span data-ttu-id="e743f-142">**Largura** - *cm*</span><span class="sxs-lookup"><span data-stu-id="e743f-142">**Length** - *cm*</span></span>
    - <span data-ttu-id="e743f-143">**Unidad de volumen** - *cm3*</span><span class="sxs-lookup"><span data-stu-id="e743f-143">**Volume unit** - *cm3*</span></span>

<span data-ttu-id="e743f-144">El campo **Volumen** se calcula automáticamente en función de sus ajustes de **Profundidad**, **Altura** y **Anchura**.</span><span class="sxs-lookup"><span data-stu-id="e743f-144">The **Volume** field is automatically calculated based on your **Depth**, **Height**, and **Width** settings.</span></span>

#### <a name="create-a-new-container-type"></a><span data-ttu-id="e743f-145">Crear un nuevo tipo de contenedor</span><span class="sxs-lookup"><span data-stu-id="e743f-145">Create a new container type</span></span>

<span data-ttu-id="e743f-146">Vaya a **Gestión de almacenes \> Configuración \> Contenedores \> Tipos de contenedores** y cree un nuevo registro con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="e743f-146">Go to **Warehouse management \> Setup \> Containers \> Container types** and create a new record with the following settings:</span></span>

- <span data-ttu-id="e743f-147">**Código de tipo de contenedor** - *Caja grande*</span><span class="sxs-lookup"><span data-stu-id="e743f-147">**Container type code** - *Short Box*</span></span>
- <span data-ttu-id="e743f-148">**Descripción** - *Caja corta*</span><span class="sxs-lookup"><span data-stu-id="e743f-148">**Description** - *Short Box*</span></span>
- <span data-ttu-id="e743f-149">**Peso neto máximo** - *50*</span><span class="sxs-lookup"><span data-stu-id="e743f-149">**Maximum net weight** - *50*</span></span>
- <span data-ttu-id="e743f-150">**Volumen** - *144*</span><span class="sxs-lookup"><span data-stu-id="e743f-150">**Volume** - *144*</span></span>
- <span data-ttu-id="e743f-151">**Longitud** - *6*</span><span class="sxs-lookup"><span data-stu-id="e743f-151">**Length** - *6*</span></span>
- <span data-ttu-id="e743f-152">**Anchura** - *6*</span><span class="sxs-lookup"><span data-stu-id="e743f-152">**Width** - *6*</span></span>
- <span data-ttu-id="e743f-153">**Altura** - *4*</span><span class="sxs-lookup"><span data-stu-id="e743f-153">**Height** - *4*</span></span>

#### <a name="create-a-container-group"></a><span data-ttu-id="e743f-154">Crear un grupo de contenedores</span><span class="sxs-lookup"><span data-stu-id="e743f-154">Create a container group</span></span>

<span data-ttu-id="e743f-155">Vaya a **Gestión de almacenes \> Configuración \> Contenedores \> Grupos de contenedores** y cree un nuevo registro con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="e743f-155">Go to **Warehouse management \> Setup \> Containers \> Container groups** and create a new record with the following settings:</span></span>

- <span data-ttu-id="e743f-156">**ID de grupo de contenedores** - *Caja corta*</span><span class="sxs-lookup"><span data-stu-id="e743f-156">**Container group ID** - *Short Box*</span></span>
- <span data-ttu-id="e743f-157">**Descripción** - *Caja corta*</span><span class="sxs-lookup"><span data-stu-id="e743f-157">**Description** - *Short Box*</span></span>

<span data-ttu-id="e743f-158">Añada una nueva línea en la sección **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="e743f-158">Add a new line to the **Details** section.</span></span> <span data-ttu-id="e743f-159">Ajuste el **Tipo de contenedor** en *Caja corta*.</span><span class="sxs-lookup"><span data-stu-id="e743f-159">Set the **Container type** to *Short Box*.</span></span>

#### <a name="set-up-a-container-build-template"></a><span data-ttu-id="e743f-160">Configurar una plantilla de creación de contenedores</span><span class="sxs-lookup"><span data-stu-id="e743f-160">Set up a container build template</span></span>

<span data-ttu-id="e743f-161">Vaya a **Gestión de almacén \> Configuración \> Contenedores \> Plantillas de planificación de contenedores** y seleccione **Cajas**.</span><span class="sxs-lookup"><span data-stu-id="e743f-161">Go to **Warehouse management \> Setup \> Containers \> Container build templates** and select **Boxes**.</span></span> <span data-ttu-id="e743f-162">Cambiar el **ID de grupo de contenedores** a *Caja corta*.</span><span class="sxs-lookup"><span data-stu-id="e743f-162">Change the **Container group ID** to *Short Box*.</span></span>

### <a name="run-the-scenario"></a><span data-ttu-id="e743f-163">Ejecute el escenario</span><span class="sxs-lookup"><span data-stu-id="e743f-163">Run the scenario</span></span>

<span data-ttu-id="e743f-164">Una vez que haya preparado su sistema como se describe en la sección anterior, estará listo para ejecutar el escenario como se describe en la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="e743f-164">After you have prepared your system as described in the previous section, you are ready to run the scenario as described in the next section.</span></span>

#### <a name="create-a-sales-order-and-create-a-shipment"></a><span data-ttu-id="e743f-165">Cree una orden de venta y un envío</span><span class="sxs-lookup"><span data-stu-id="e743f-165">Create a sales order and create a shipment</span></span>

<span data-ttu-id="e743f-166">En este proceso, creará un envío basado en las dimensiones de *embalaje* del artículo, para las cuales la altura es menor que 3.</span><span class="sxs-lookup"><span data-stu-id="e743f-166">In this process you will create a shipment based on the item *packing* dimensions, for which the height is less than 3.</span></span>

1. <span data-ttu-id="e743f-167">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="e743f-167">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="e743f-168">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="e743f-168">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="e743f-169">En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="e743f-169">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="e743f-170">**Cuenta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="e743f-170">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="e743f-171">**Almacén**: *63*</span><span class="sxs-lookup"><span data-stu-id="e743f-171">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="e743f-172">Seleccione **Aceptar** para crear el pedido de ventas y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e743f-172">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="e743f-173">Se abre el nuevo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="e743f-173">The new sales order is opened.</span></span> <span data-ttu-id="e743f-174">Debe incluir una nueva línea vacía en la cuadrícula en la ficha desplegable **Líneas de pedido de venta**.</span><span class="sxs-lookup"><span data-stu-id="e743f-174">It should include a new, empty line in the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="e743f-175">En esta línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="e743f-175">On this line, set the following values:</span></span>

    - <span data-ttu-id="e743f-176">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="e743f-176">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="e743f-177">**Cantidad:** *5*</span><span class="sxs-lookup"><span data-stu-id="e743f-177">**Quantity:** *5*</span></span>

1. <span data-ttu-id="e743f-178">En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Inventario \> Reserva**.</span><span class="sxs-lookup"><span data-stu-id="e743f-178">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="e743f-179">En la página **Reserva**, en el Panel de acciones, seleccione **Reservar lote** para reservar inventario.</span><span class="sxs-lookup"><span data-stu-id="e743f-179">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="e743f-180">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e743f-180">Close the page.</span></span>
1. <span data-ttu-id="e743f-181">En el panel de acciones, abra la pestaña **Almacén**, seleccione **Liberar al almacén** para crear un trabajo para el almacén.</span><span class="sxs-lookup"><span data-stu-id="e743f-181">On the Action Pane, open the **Warehouse** tab and select **Release to warehouse** to create work for the warehouse.</span></span>
1. <span data-ttu-id="e743f-182">En la ficha desplegable **Líneas de pedido de ventas**, seleccione **Almacén \> Detalles de envío**.</span><span class="sxs-lookup"><span data-stu-id="e743f-182">On the **Sales order lines** FastTab, select **Warehouse \> Shipment details**.</span></span>
1. <span data-ttu-id="e743f-183">En el Panel acciones, abra la pestaña **Transporte** y seleccione **Ver contenedores**.</span><span class="sxs-lookup"><span data-stu-id="e743f-183">On the Action Pane, open the **Transportation** tab and select **View containers**.</span></span> <span data-ttu-id="e743f-184">Confirme que el artículo se colocó en contenedores en los dos contendores *Caja corta*.</span><span class="sxs-lookup"><span data-stu-id="e743f-184">Confirm that the item was containerized into the two *Short Box* containers.</span></span>

#### <a name="place-an-item-into-storage"></a><span data-ttu-id="e743f-185">Coloque un artículo en almacenamiento</span><span class="sxs-lookup"><span data-stu-id="e743f-185">Place an item into storage</span></span>

1. <span data-ttu-id="e743f-186">Abra el dispositivo móvil, inicie sesión en el almacén 63 y vaya a **Inventario \> Ajustar en**.</span><span class="sxs-lookup"><span data-stu-id="e743f-186">Open the mobile device, sign in to warehouse 63 and go to **Inventory \> Adjust In**.</span></span>
1. <span data-ttu-id="e743f-187">Introducir **Loc** = *SHORT-01*.</span><span class="sxs-lookup"><span data-stu-id="e743f-187">Enter **Loc** = *SHORT-01*.</span></span> <span data-ttu-id="e743f-188">Haga una nueva placa con **Artículo** = *A0001* y **Cantidad** = *1 ud.*.</span><span class="sxs-lookup"><span data-stu-id="e743f-188">Make a new license plate with **Item** = *A0001* and **Quantity** = *1 pcs*.</span></span>
1. <span data-ttu-id="e743f-189">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e743f-189">Select **OK**.</span></span> <span data-ttu-id="e743f-190">Recibirá el error "La ubicación SHORT-01 falló porque el elemento A0001 no encaja en las dimensiones especificadas de la ubicación".</span><span class="sxs-lookup"><span data-stu-id="e743f-190">You will receive the error "Location SHORT-01 failed because item A0001 does not fit in location's specified dimensions."</span></span> <span data-ttu-id="e743f-191">Esto es porque las dimensiones del *almacenamiento* de tipo del producto son mayores que las dimensiones especificadas en el perfil de ubicación.</span><span class="sxs-lookup"><span data-stu-id="e743f-191">This is because the *Storage* type dimensions of the product are larger than the dimensions specified on the location profile.</span></span>
