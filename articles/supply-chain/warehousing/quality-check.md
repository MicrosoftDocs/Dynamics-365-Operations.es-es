---
title: Control de calidad
description: Este tema proporciona información acerca de la característica Control de calidad. Esta característica permite que los trabajadores del almacén realicen verificaciones rápidas de calidad mientras reciben artículos en la zona del muelle de llegada.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: c270426a228ac58652f1f60d6fe99d4886071fa6
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2020
ms.locfileid: "3621447"
---
# <a name="quality-check"></a><span data-ttu-id="382f0-104">Control de calidad</span><span class="sxs-lookup"><span data-stu-id="382f0-104">Quality check</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="382f0-105">La característica *Control de calidad* permite que los trabajadores del almacén realicen verificaciones rápidas de calidad mientras reciben artículos en la zona del muelle de llegada.</span><span class="sxs-lookup"><span data-stu-id="382f0-105">The *Quality check* feature lets warehouse workers do quick spot checks for quality while they receive items to the inbound dock area.</span></span> <span data-ttu-id="382f0-106">Estas comprobaciones puntuales son ventajosas cuando los trabajadores inspeccionan el embalaje u otras partes fácilmente reconocibles de un artículo.</span><span class="sxs-lookup"><span data-stu-id="382f0-106">These spot checks are beneficial when workers inspect packaging or other easily recognizable parts of an item.</span></span> <span data-ttu-id="382f0-107">La característica guía a los trabajadores a echar un vistazo rápido para ver si algo está obviamente defectuoso o dañado antes de almacenar el inventario en su ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="382f0-107">The feature guides workers to take a quick look to see whether anything is obviously faulty or damaged before they stock the inventory in its putaway location.</span></span>

<span data-ttu-id="382f0-108">Esta característica es una alternativa al proceso de control de calidad estándar.</span><span class="sxs-lookup"><span data-stu-id="382f0-108">This feature is an alternative to the standard quality check process.</span></span> <span data-ttu-id="382f0-109">Ofrece más flexibilidad y un procesamiento más rápido.</span><span class="sxs-lookup"><span data-stu-id="382f0-109">It offers more flexibility and faster processing.</span></span>

<span data-ttu-id="382f0-110">Cuando utiliza esta función, el control de llegada y calidad se realiza de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="382f0-110">When you use this feature, the arrival and quality check occur in the following way:</span></span>

1. <span data-ttu-id="382f0-111">Cuando llega un envío, un trabajador del almacén registra la llegada.</span><span class="sxs-lookup"><span data-stu-id="382f0-111">When a shipment arrives, a warehouse worker registers the arrival.</span></span> <span data-ttu-id="382f0-112">El trabajador también escanea una matrícula de entidad de almacén para registrar la ubicación.</span><span class="sxs-lookup"><span data-stu-id="382f0-112">The worker also scans a license plate to register the location.</span></span>
1. <span data-ttu-id="382f0-113">El trabajador realiza un rápido control de calidad y registra el resultado (aprobado o no) para esa matrícula de entidad de almacén.</span><span class="sxs-lookup"><span data-stu-id="382f0-113">The worker does a quick quality check and records the result (pass or fail) for that license plate.</span></span>
1. <span data-ttu-id="382f0-114">Se produce una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="382f0-114">One of the following actions occurs:</span></span>

    - <span data-ttu-id="382f0-115">Si se pasa el control de calidad, la matrícula de entidad de almacén se acepta y se lleva a un lugar de recepción, como de costumbre.</span><span class="sxs-lookup"><span data-stu-id="382f0-115">If the quality check is passed, the license plate is accepted and guided to a receiving location, as usual.</span></span>
    - <span data-ttu-id="382f0-116">Si falla el control de calidad, la matrícula de entidad de almacén se rechaza y el trabajo de almacenamiento existente para ello se redirige a una ubicación alternativa para su posterior inspección.</span><span class="sxs-lookup"><span data-stu-id="382f0-116">If the quality check is failed, the license plate is rejected, and existing putaway work for it is redirected to an alternate location for further inspection.</span></span> <span data-ttu-id="382f0-117">Se crea un nuevo pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="382f0-117">A new quality order is created.</span></span> <span data-ttu-id="382f0-118">Para ver el pedido de calidad creado a partir del control de calidad con error, vaya a **Gestión de inventarios \> Tareas periódicas \> Administración de la calidad \> Pedidos de calidad**.</span><span class="sxs-lookup"><span data-stu-id="382f0-118">To view the quality order that is created from the failed quality check, go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>

<span data-ttu-id="382f0-119">Este proceso también se puede configurar para que todas las matrículas de entidad escaneadas se desvíen inmediatamente a la ubicación del control de calidad.</span><span class="sxs-lookup"><span data-stu-id="382f0-119">This process can also be set up so that all scanned license plates are immediately diverted to the quality check location.</span></span>

## <a name="turn-on-the-quality-check-feature"></a><span data-ttu-id="382f0-120">Active la función de control de calidad</span><span class="sxs-lookup"><span data-stu-id="382f0-120">Turn on the Quality check feature</span></span>

<span data-ttu-id="382f0-121">Antes de poder usar la característica *Control de calidad*, debe estar activada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="382f0-121">Before you can use the *Quality check* feature, it must be turned on in your system.</span></span> <span data-ttu-id="382f0-122">Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="382f0-122">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="382f0-123">En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="382f0-123">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="382f0-124">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="382f0-124">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="382f0-125">**Nombre de la característica**: *Control de calidad*</span><span class="sxs-lookup"><span data-stu-id="382f0-125">**Feature name:** *Quality check*</span></span>

## <a name="set-up-the-feature-for-the-example-scenario"></a><span data-ttu-id="382f0-126">Configure la función para el escenario de ejemplo</span><span class="sxs-lookup"><span data-stu-id="382f0-126">Set up the feature for the example scenario</span></span>

<span data-ttu-id="382f0-127">Esta sección proporciona pautas y un ejemplo que muestra cómo configurar la característica *Control de calidad* y preparar datos de muestra para el escenario de ejemplo que se proporciona más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="382f0-127">This section provides guidelines and an example that shows how to set up the *Quality check* feature and prepare sample data for the example scenario that is provided later in this topic.</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="382f0-128">Hacer que los datos de muestra estén disponibles</span><span class="sxs-lookup"><span data-stu-id="382f0-128">Make sample data available</span></span>

<span data-ttu-id="382f0-129">Para trabajar en el [escenario de ejemplo](#example-scenario) mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) estándar.</span><span class="sxs-lookup"><span data-stu-id="382f0-129">To work through the [example scenario](#example-scenario) by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="382f0-130">Además, también debe seleccionar la entidad legal **USMF** antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="382f0-130">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

### <a name="quality-check-template"></a><a name="quality-template"></a><span data-ttu-id="382f0-131">Plantilla de control de calidad</span><span class="sxs-lookup"><span data-stu-id="382f0-131">Quality check template</span></span>

<span data-ttu-id="382f0-132">La plantilla de control de calidad define las reglas para realizar controles rápidos de calidad en el momento de la recepción.</span><span class="sxs-lookup"><span data-stu-id="382f0-132">The quality check template defines the rules for doing quick spot checks for quality at the time of receiving.</span></span>

1. <span data-ttu-id="382f0-133">Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de control de calidad**.</span><span class="sxs-lookup"><span data-stu-id="382f0-133">Go to **Warehouse management \> Setup \> Work \> Quality check template**.</span></span>
1. <span data-ttu-id="382f0-134">Seleccione **Nuevo** para agregar una plantilla a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="382f0-134">Select **New** to add a template to the grid.</span></span>
1. <span data-ttu-id="382f0-135">Establezca los siguientes valores para definir la plantilla nueva:</span><span class="sxs-lookup"><span data-stu-id="382f0-135">Set the following values to define the new template:</span></span>

    - <span data-ttu-id="382f0-136">**Nombre de la plantilla de control de calidad**: *Comprobación de muelle*</span><span class="sxs-lookup"><span data-stu-id="382f0-136">**Quality check template name:** *Dock check*</span></span>

        <span data-ttu-id="382f0-137">Especifique un nombre que identifique las políticas aplicadas para esta plantilla.</span><span class="sxs-lookup"><span data-stu-id="382f0-137">Enter a name that identifies the policies applied for this template.</span></span>

    - <span data-ttu-id="382f0-138">**Política de aceptación**: *Preguntar al usuario*</span><span class="sxs-lookup"><span data-stu-id="382f0-138">**Acceptance policy:** *Prompt user*</span></span>

        <span data-ttu-id="382f0-139">Especifique si se debe solicitar a los usuarios que acepten o rechacen la calidad del inventario mientras procesan el trabajo, o si la calidad debe rechazarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="382f0-139">Specify whether users should be prompted to accept or reject the quality of the inventory while they process the work, or whether the quality should automatically be rejected.</span></span> <span data-ttu-id="382f0-140">Las opciones disponibles son *Rechazo automático* y *Preguntar al usuario*.</span><span class="sxs-lookup"><span data-stu-id="382f0-140">The available options are *Auto reject* and *Prompt user*.</span></span>

    - <span data-ttu-id="382f0-141">**Directiva de procesamiento de calidad**: *Crear orden de calidad*</span><span class="sxs-lookup"><span data-stu-id="382f0-141">**Quality processing policy:** *Create quality order*</span></span>

        <span data-ttu-id="382f0-142">Seleccionar la directiva que se utilizará cuando se rechaza la calidad del inventario.</span><span class="sxs-lookup"><span data-stu-id="382f0-142">Select the policy that should be used when the quality of the inventory is rejected.</span></span> <span data-ttu-id="382f0-143">Las siguientes opciones están disponibles:</span><span class="sxs-lookup"><span data-stu-id="382f0-143">The following options are available:</span></span>

        - <span data-ttu-id="382f0-144">*Crear solo trabajo*: simplemente se crea trabajo para facilitar el movimiento del inventario.</span><span class="sxs-lookup"><span data-stu-id="382f0-144">*Create work only* – Just create work to facilitate inventory movement.</span></span>
        - <span data-ttu-id="382f0-145">*Crear pedido de calidad*: crear un pedido de calidad para facilitar las pruebas de calidad.</span><span class="sxs-lookup"><span data-stu-id="382f0-145">*Create quality order* – Create a quality order to facilitate quality tests.</span></span>

    - <span data-ttu-id="382f0-146">**Grupo de prueba**: *Recinto*</span><span class="sxs-lookup"><span data-stu-id="382f0-146">**Test group:** *Enclosure*</span></span>

        <span data-ttu-id="382f0-147">Especifique el grupo de prueba que se debe usar en el pedido de calidad que se crea.</span><span class="sxs-lookup"><span data-stu-id="382f0-147">Specify the test group that should be used in the quality order that is created.</span></span> <span data-ttu-id="382f0-148">Los grupos de prueba se configuran en el módulo **Gestión de inventarios**.</span><span class="sxs-lookup"><span data-stu-id="382f0-148">Test groups are set up in the **Inventory management** module.</span></span>

        <span data-ttu-id="382f0-149">Deje desactivada la opción **Texto destructivo** para el grupo de prueba.</span><span class="sxs-lookup"><span data-stu-id="382f0-149">Leave the **Destructive text** option turned off for the test group.</span></span> <span data-ttu-id="382f0-150">Esta opción define si la muestra debe destruirse como parte de las pruebas del grupo de pruebas.</span><span class="sxs-lookup"><span data-stu-id="382f0-150">This option defines whether the sample will be destroyed as part of the tests in the test group.</span></span> <span data-ttu-id="382f0-151">Si se utiliza la prueba destructiva, el sistema genera una transacción de inventario cuando se crea el pedido de calidad para un artículo.</span><span class="sxs-lookup"><span data-stu-id="382f0-151">If a destructive test is used, the system generates an inventory transaction when a quality order is created for an item.</span></span> <span data-ttu-id="382f0-152">La nueva transacción de inventario predice la reducción del inventario para la cantidad de la prueba.</span><span class="sxs-lookup"><span data-stu-id="382f0-152">The new inventory transaction predicts the inventory reduction for the test quantity.</span></span> <span data-ttu-id="382f0-153">La reducción del inventario se produce cuando se completa el pedido de calidad a través del paso de validación.</span><span class="sxs-lookup"><span data-stu-id="382f0-153">The inventory reduction occurs when the quality order is completed through the validation step.</span></span> <span data-ttu-id="382f0-154">La transacción de inventario se identifica como pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="382f0-154">The inventory transaction is identified as a quality order.</span></span>

### <a name="work-class--quality-check"></a><a name="work-class"></a><span data-ttu-id="382f0-155">Clase de trabajo: control de calidad</span><span class="sxs-lookup"><span data-stu-id="382f0-155">Work class – Quality check</span></span>

<span data-ttu-id="382f0-156">Las clases de trabajo se usan para dirigir y/o para limitar el tipo de líneas de pedido de trabajo que un trabajador de almacén puede procesar en un dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="382f0-156">Work classes are used to direct and/or limit the type of work order lines that warehouse workers can process on a mobile device.</span></span>

1. <span data-ttu-id="382f0-157">Vaya a **Gestión de almacenes \> Configurar \> Trabajo \> Clases de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="382f0-157">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="382f0-158">Seleccione **Nuevo** para crear una clase de trabajo.</span><span class="sxs-lookup"><span data-stu-id="382f0-158">Select **New** to create a work class.</span></span>
1. <span data-ttu-id="382f0-159">Establezca los siguientes valores en el encabezado:</span><span class="sxs-lookup"><span data-stu-id="382f0-159">In the header, set the following values:</span></span>

    - <span data-ttu-id="382f0-160">**Id. de la clase de trabajo**: *Control de calidad*</span><span class="sxs-lookup"><span data-stu-id="382f0-160">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="382f0-161">Especifique un nombre que identifique la clase de trabajo.</span><span class="sxs-lookup"><span data-stu-id="382f0-161">Enter a name that identifies the work class.</span></span>

    - <span data-ttu-id="382f0-162">**Descripción**: *Control de calidad*</span><span class="sxs-lookup"><span data-stu-id="382f0-162">**Description:** *QC Check*</span></span>

        <span data-ttu-id="382f0-163">Escriba una breve descripción que indique para qué se utiliza la clase de trabajo.</span><span class="sxs-lookup"><span data-stu-id="382f0-163">Enter a short description that indicates what the work class is used for.</span></span>

    - <span data-ttu-id="382f0-164">**Tipo de orden de trabajo**: *Calidad en control de calidad*</span><span class="sxs-lookup"><span data-stu-id="382f0-164">**Work order type:** *Quality in quality check*</span></span>

        <span data-ttu-id="382f0-165">Seleccione el tipo de orden de trabajo que crea la clase de trabajo.</span><span class="sxs-lookup"><span data-stu-id="382f0-165">Select the type of work order that is created by the work class.</span></span> <span data-ttu-id="382f0-166">Cuando configure el trabajo de control de calidad, seleccione siempre *Calidad en control de calidad*.</span><span class="sxs-lookup"><span data-stu-id="382f0-166">When you set up quality control work, always select *Quality in quality check*.</span></span>

1. <span data-ttu-id="382f0-167">En la ficha desplegable **Tipos de ubicación de colocación válidos**, deje el campo **Tipo de ubicación** en blanco.</span><span class="sxs-lookup"><span data-stu-id="382f0-167">On the **Valid put location types** FastTab, leave the **Location type** field blank.</span></span>

    <span data-ttu-id="382f0-168">Si selecciona un tipo de ubicación, limita las ubicaciones donde se pueden colocar los artículos después de que se seleccionan.</span><span class="sxs-lookup"><span data-stu-id="382f0-168">If you select a location type, you limit the locations where items can be put after they are picked.</span></span> <span data-ttu-id="382f0-169">El capo se usa cuando una directiva de ubicación intenta resolver la ubicación, o si un trabajador del almacén especifica manualmente la ubicación para el elemento de menú del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="382f0-169">This field is used when a location directive tries to resolve the location, or when a warehouse worker manually specifies the location for the mobile device menu item.</span></span>

<span data-ttu-id="382f0-170">Para obtener más información sobre las clases de trabajo y cómo crearlas, vea [Crear una clase de trabajo](tasks/create-work-class.md).</span><span class="sxs-lookup"><span data-stu-id="382f0-170">For more information about work classes and how to create them, see [Create a work class](tasks/create-work-class.md).</span></span>

### <a name="work-template"></a><span data-ttu-id="382f0-171">Plantilla de trabajo</span><span class="sxs-lookup"><span data-stu-id="382f0-171">Work template</span></span>

<span data-ttu-id="382f0-172">La página Plantillas de trabajo le permite definir las operaciones de trabajo que se deben realizar en el almacén.</span><span class="sxs-lookup"><span data-stu-id="382f0-172">Work templates let you define the work operations that must be performed in the warehouse.</span></span> <span data-ttu-id="382f0-173">Normalmente, las operaciones de trabajo del almacén constan de un par de acciones: un trabajador de almacén recoge inventario disponible en una ubicación y después pone el inventario seleccionado en otra ubicación.</span><span class="sxs-lookup"><span data-stu-id="382f0-173">Typically, warehouse work operations consist of a pair of actions: a warehouse worker picks on-hand inventory up in one location and then puts the picked inventory down in another location.</span></span> <span data-ttu-id="382f0-174">Una plantilla de trabajo para el control de calidad define las operaciones de trabajo para realizar controles de calidad.</span><span class="sxs-lookup"><span data-stu-id="382f0-174">A work template for quality control defines the work operations for doing quality checks.</span></span>

#### <a name="purchase-orders"></a><span data-ttu-id="382f0-175">Pedidos de compra</span><span class="sxs-lookup"><span data-stu-id="382f0-175">Purchase orders</span></span>

1. <span data-ttu-id="382f0-176">Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="382f0-176">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="382f0-177">En el encabezado, establezca el campo **Tipo de orden de trabajo** en *Pedidos de compra*.</span><span class="sxs-lookup"><span data-stu-id="382f0-177">In the header, set the **Work order type** field to *Purchase orders*.</span></span>
1. <span data-ttu-id="382f0-178">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="382f0-178">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="382f0-179">Seleccione una plantilla de trabajo que incluya un paso de control de calidad.</span><span class="sxs-lookup"><span data-stu-id="382f0-179">Select a work template that should include a quality check step.</span></span> <span data-ttu-id="382f0-180">En la sección **Visión general**, en el campo **Plantilla de trabajo**, seleccione *Recibo de 51 PO*.</span><span class="sxs-lookup"><span data-stu-id="382f0-180">In the **Overview** section, in the **Work template** field, select *51 PO Receipt*.</span></span>
1. <span data-ttu-id="382f0-181">En la sección **Detalles de plantilla de trabajo**, observe que la cuadrícula tiene dos líneas existentes: una para *Recoger* y otra para *Colocar*.</span><span class="sxs-lookup"><span data-stu-id="382f0-181">In the **Work template details** section, notice that the grid has two existing lines: one for *Pick* and one for *Put*.</span></span>
1. <span data-ttu-id="382f0-182">En la sección **Detalles de plantilla de trabajo**, seleccione **Nuevo** para agregar una fila para el control de calidad a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="382f0-182">In the **Work template details** section, select **New** to add a row for quality control to the grid.</span></span> <span data-ttu-id="382f0-183">Tenga en cuenta que el campo **Número de línea** para la nueva línea se establece en *3*.</span><span class="sxs-lookup"><span data-stu-id="382f0-183">Notice that the **Line number** field for the new line is set to *3*.</span></span>
1. <span data-ttu-id="382f0-184">En la nueva línea, establezca los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="382f0-184">On the new line, set the following values.</span></span> <span data-ttu-id="382f0-185">Acepte los valores predeterminados del resto de campos.</span><span class="sxs-lookup"><span data-stu-id="382f0-185">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="382f0-186">**Tipo de trabajo**: *Control de calidad*</span><span class="sxs-lookup"><span data-stu-id="382f0-186">**Work type:** *Quality check*</span></span>
    - <span data-ttu-id="382f0-187">**Id. de la clase de trabajo**: *Compra*</span><span class="sxs-lookup"><span data-stu-id="382f0-187">**Work class ID:** *Purchase*</span></span>
    - <span data-ttu-id="382f0-188">**Nombre de la plantilla de control de calidad**: *Comprobación de muelle*</span><span class="sxs-lookup"><span data-stu-id="382f0-188">**Quality check template name:** *Dock check*</span></span>

        <span data-ttu-id="382f0-189">Seleccione el identificador único de la clase de trabajo.</span><span class="sxs-lookup"><span data-stu-id="382f0-189">Select the unique ID for the work class.</span></span> <span data-ttu-id="382f0-190">Usa este valor para configurar los elementos de menú en el dispositivo móvil y los tipos de trabajo que estos elementos de menú pueden procesar.</span><span class="sxs-lookup"><span data-stu-id="382f0-190">You use this value to configure the menu items on the mobile device and the types of work that those menu items can process.</span></span>

1. <span data-ttu-id="382f0-191">En el panel Acciones, seleccione **Guardar** para guardar su trabajo hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="382f0-191">On the Action Pane, select **Save** to save your work so far.</span></span>

    <span data-ttu-id="382f0-192">Recibirá un mensaje informativo que dice: "No válido: el control de calidad debe realizarse directamente después de una selección".</span><span class="sxs-lookup"><span data-stu-id="382f0-192">You receive an informational message that states, "Invalid - Quality check must come directly after a pick."</span></span> <span data-ttu-id="382f0-193">Por lo tanto, debe cambiar el valor **Número de línea** para la línea que acaba de agregar.</span><span class="sxs-lookup"><span data-stu-id="382f0-193">Therefore, you must change the **Line number** value for the line that you just added.</span></span>

1. <span data-ttu-id="382f0-194">Siga estos pasos para cambiar el valor **Número de línea** para la nueva línea:</span><span class="sxs-lookup"><span data-stu-id="382f0-194">Follow these steps to change the **Line number** value for the new line:</span></span>

    1. <span data-ttu-id="382f0-195">En la sección **Detalles de plantilla de trabajo**, seleccione la línea donde el campo **Tipo de trabajo** se establece en *Control de calidad*.</span><span class="sxs-lookup"><span data-stu-id="382f0-195">In the **Work template details** section, select the line where the **Work type** field is set to *Quality check*.</span></span>
    2. <span data-ttu-id="382f0-196">Seleccione el botón **Ascender** o **Descender** para mover la línea *Control de calidad* para que esté después de la línea *Recoger*.</span><span class="sxs-lookup"><span data-stu-id="382f0-196">Select the **Move up** or **Move down** button to move the *Quality check* line so that it's after the *Pick* line.</span></span>

1. <span data-ttu-id="382f0-197">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="382f0-197">On the Action Pane, select **Save**.</span></span>

#### <a name="quality-in-quality-check"></a><span data-ttu-id="382f0-198">Calidad en control de calidad</span><span class="sxs-lookup"><span data-stu-id="382f0-198">Quality in quality check</span></span>

<span data-ttu-id="382f0-199">A continuación, cree una plantilla de trabajo para el control de calidad.</span><span class="sxs-lookup"><span data-stu-id="382f0-199">Next, create a work template for the quality check.</span></span>

1. <span data-ttu-id="382f0-200">En el encabezado de la página **Plantillas de trabajo**, cambie el valor de **Tipo de orden de trabajo** a *Calidad en control de calidad*.</span><span class="sxs-lookup"><span data-stu-id="382f0-200">In the header of the **Work templates** page, change the value of the **Work order type** field to *Quality in quality check*.</span></span>
1. <span data-ttu-id="382f0-201">En el panel Acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula en la sección **Visión general**.</span><span class="sxs-lookup"><span data-stu-id="382f0-201">On the Action Pane, select **New** to add a row to the grid in the **Overview** section.</span></span>
1. <span data-ttu-id="382f0-202">Establezca los siguientes valores en la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="382f0-202">In the new row, set the following values:</span></span>

    - <span data-ttu-id="382f0-203">**Plantilla de trabajo**: *Control de calidad 51*</span><span class="sxs-lookup"><span data-stu-id="382f0-203">**Work template:** *51 Quality Check*</span></span>

        <span data-ttu-id="382f0-204">Especifique un nombre para la plantilla.</span><span class="sxs-lookup"><span data-stu-id="382f0-204">Enter a name for the template.</span></span>

    - <span data-ttu-id="382f0-205">**Descripción de plantilla de trabajo**: *Control de calidad 51*</span><span class="sxs-lookup"><span data-stu-id="382f0-205">**Work template description:** *51 Quality Check*</span></span>

1. <span data-ttu-id="382f0-206">En el panel Acciones, seleccione **Guardar** para tener disponible la sección **Detalles de plantilla de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="382f0-206">On the Action Pane, select **Save** to make the **Work template details** section available.</span></span>
1. <span data-ttu-id="382f0-207">Mientras la nueva plantilla todavía está seleccionada en la sección **Visión general**, seleccione **Nuevo** en la sección **Detalles de la plantilla de trabajo** para agregar una fila a la cuadrícula allí.</span><span class="sxs-lookup"><span data-stu-id="382f0-207">While the new template is still selected in the **Overview** section, select **New** in the **Work template details** section to add a row to the grid there.</span></span>
1. <span data-ttu-id="382f0-208">Establezca los siguientes valores en la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="382f0-208">In the new row, set the following values:</span></span>

    - <span data-ttu-id="382f0-209">**Tipo de trabajo**: *Recoger*</span><span class="sxs-lookup"><span data-stu-id="382f0-209">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="382f0-210">**Id. de la clase de trabajo**: *Control de calidad*</span><span class="sxs-lookup"><span data-stu-id="382f0-210">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="382f0-211">Seleccione el nombre de la [clase de trabajo](#work-class) que creó anteriormente para el trabajo de control de calidad.</span><span class="sxs-lookup"><span data-stu-id="382f0-211">Select the name of the [work class](#work-class) that you created earlier for quality control work.</span></span>

1. <span data-ttu-id="382f0-212">En la sección **Detalles de la plantilla de trabajo**, vuelva a seleccionar **Nuevo** para agregar otra fila.</span><span class="sxs-lookup"><span data-stu-id="382f0-212">In the **Work template details** section, select **New** again to add another row.</span></span>
1. <span data-ttu-id="382f0-213">Establezca los siguientes valores en la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="382f0-213">In the new row, set the following values:</span></span>

    - <span data-ttu-id="382f0-214">**Tipo de trabajo**: *Ubicar*</span><span class="sxs-lookup"><span data-stu-id="382f0-214">**Work type:** *Put*</span></span>
    - <span data-ttu-id="382f0-215">**Id. de la clase de trabajo**: *Control de calidad*</span><span class="sxs-lookup"><span data-stu-id="382f0-215">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="382f0-216">Seleccione el nombre de la [clase de trabajo](#work-class) que creó anteriormente para el trabajo de control de calidad.</span><span class="sxs-lookup"><span data-stu-id="382f0-216">Select the name of the [work class](#work-class) that you created earlier for quality control work.</span></span>

1. <span data-ttu-id="382f0-217">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="382f0-217">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="382f0-218">Para obtener más información sobre las plantillas de trabajo, consulte [Controlar el trabajo de almacén con plantillas de trabajo y directivas de ubicación](control-warehouse-location-directives.md).</span><span class="sxs-lookup"><span data-stu-id="382f0-218">For more information about work templates, see [Control warehouse work by using work templates and location directives](control-warehouse-location-directives.md)</span></span>

### <a name="location-directive--quality-failures"></a><span data-ttu-id="382f0-219">Directiva de ubicación: Fallos de calidad</span><span class="sxs-lookup"><span data-stu-id="382f0-219">Location directive – Quality failures</span></span>

<span data-ttu-id="382f0-220">Las directivas de ubicación son reglas que ayudan a identifica las ubicaciones de picking y de colocación para el movimiento de inventario.</span><span class="sxs-lookup"><span data-stu-id="382f0-220">Location directives are rules that help identify pick and put locations for inventory movement.</span></span> <span data-ttu-id="382f0-221">Por ejemplo, en una transacción de pedido de ventas, una directiva de ubicación determina dónde se hará el picking de los artículos y dónde se colocarán los artículos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="382f0-221">For example, in a sales order transaction, a location directive determines where the items will be picked and where the picked items will be put.</span></span> <span data-ttu-id="382f0-222">Debe configurar una regla de directiva de ubicación para definir cómo se manejarán los controles de calidad con error.</span><span class="sxs-lookup"><span data-stu-id="382f0-222">You must configure a location directive rule to define how failed quality checks will be handled.</span></span>

1. <span data-ttu-id="382f0-223">Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="382f0-223">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="382f0-224">En el panel izquierdo, configure el campo **Tipo de orden de trabajo** en *Pedidos de compra* para trabajar con directivas de ubicación de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="382f0-224">In the left pane, set the **Work order type** field to *Purchase orders* to work with location directives of that type.</span></span>
1. <span data-ttu-id="382f0-225">En el panel Acciones, seleccione **Nuevo** para crear una directiva para controles de calidad.</span><span class="sxs-lookup"><span data-stu-id="382f0-225">On the Action Pane, select **New** to create a location directive for quality checks.</span></span>
1. <span data-ttu-id="382f0-226">Establezca los siguientes valores en el encabezado:</span><span class="sxs-lookup"><span data-stu-id="382f0-226">In the header, set the following values:</span></span>

    - <span data-ttu-id="382f0-227">**Número de secuencia:** acepte el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="382f0-227">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="382f0-228">**Nombre**: *51 a calidad*</span><span class="sxs-lookup"><span data-stu-id="382f0-228">**Name:** *51 To Quality*</span></span>

1. <span data-ttu-id="382f0-229">En la ficha desplegable **Directivas generales**, establezca los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="382f0-229">On the **Location directives** FastTab, set the following values.</span></span> <span data-ttu-id="382f0-230">Acepte los valores predeterminados del resto de campos.</span><span class="sxs-lookup"><span data-stu-id="382f0-230">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="382f0-231">**Tipo de trabajo**: *Ubicar*</span><span class="sxs-lookup"><span data-stu-id="382f0-231">**Work type:** *Put*</span></span>
    - <span data-ttu-id="382f0-232">**Sitio**: *5*</span><span class="sxs-lookup"><span data-stu-id="382f0-232">**Site:** *5*</span></span>
    - <span data-ttu-id="382f0-233">**Almacén**: *51*</span><span class="sxs-lookup"><span data-stu-id="382f0-233">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="382f0-234">En el panel Acciones, seleccione **Guardar** para guardar la directiva y que la ficha desplegable **Líneas** esté disponible.</span><span class="sxs-lookup"><span data-stu-id="382f0-234">On the Action Pane select **Save** to save your directive and make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="382f0-235">En la ficha desplegable **Líneas**, seleccione **Nuevo** para agregar una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="382f0-235">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="382f0-236">En la nueva línea, establezca los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="382f0-236">On the new line, set the following values.</span></span> <span data-ttu-id="382f0-237">Acepte los valores predeterminados del resto de campos.</span><span class="sxs-lookup"><span data-stu-id="382f0-237">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="382f0-238">**Cantidad inicial**: *1*</span><span class="sxs-lookup"><span data-stu-id="382f0-238">**From quantity:** *1*</span></span>
    - <span data-ttu-id="382f0-239">**Cantidad final**: *1000000*</span><span class="sxs-lookup"><span data-stu-id="382f0-239">**To quantity:** *1000000*</span></span>

1. <span data-ttu-id="382f0-240">En el panel Acciones, seleccione **Guardar** para guardar la línea nueva y que la ficha desplegable **Acciones de directiva de ubicación** esté disponible.</span><span class="sxs-lookup"><span data-stu-id="382f0-240">On the Action Pane, select **Save** to save the new line and make the **Location directive actions** FastTab available.</span></span>
1. <span data-ttu-id="382f0-241">Mientras la nueva línea todavía está seleccionada en la ficha desplegable **Líneas**, seleccione **Nuevo** en la ficha desplegable **Ubicación de acciones de directiva** para agregar una fila a la cuadrícula allí, para que pueda configurar una acción para la línea.</span><span class="sxs-lookup"><span data-stu-id="382f0-241">While the new line is still selected on the **Lines** FastTab, select **New** on the **Location directive actions** FastTab to add a row to the grid there, so that you can set up an action for the line.</span></span>
1. <span data-ttu-id="382f0-242">En la nueva fila, establezca el campo **Nombre** en *Calidad*.</span><span class="sxs-lookup"><span data-stu-id="382f0-242">In the new row, set the **Name** field to *Quality*.</span></span> <span data-ttu-id="382f0-243">Acepte los valores predeterminados del resto de campos.</span><span class="sxs-lookup"><span data-stu-id="382f0-243">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="382f0-244">En el panel Acciones, seleccione **Guardar** para tener disponible el botón **Editar consulta** en la ficha desplegable **Acciones de directiva de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="382f0-244">On the Action Pane, select **Save** to make the **Edit query** button on the **Location directive actions** FastTab available.</span></span>
1. <span data-ttu-id="382f0-245">Si bien la línea que acaba de agregar todavía está seleccionada en la ficha desplegable **Ubicación de las acciones de directiva**, seleccione **Editar consulta**, para abrir un cuadro de diálogo donde puede editar la consulta de la acción.</span><span class="sxs-lookup"><span data-stu-id="382f0-245">While the line that you just added is still selected on the **Location directive actions** FastTab, select **Edit query** to open a dialog box where you can edit the query for the action.</span></span>
1. <span data-ttu-id="382f0-246">En la pestaña **Intervalo**, seleccione **Agregar** para agregar una fila a la consulta.</span><span class="sxs-lookup"><span data-stu-id="382f0-246">On the **Range** tab, select **Add** to add a row to the query.</span></span>
1. <span data-ttu-id="382f0-247">Establezca los siguientes valores en la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="382f0-247">In the new row, set the following values:</span></span>

    - <span data-ttu-id="382f0-248">**Tabla**: *Ubicaciones*</span><span class="sxs-lookup"><span data-stu-id="382f0-248">**Table:** *Locations*</span></span>
    - <span data-ttu-id="382f0-249">**Tabla derivada:** *Ubicaciones*</span><span class="sxs-lookup"><span data-stu-id="382f0-249">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="382f0-250">**Campo:** *Ubicación*</span><span class="sxs-lookup"><span data-stu-id="382f0-250">**Field:** *Location*</span></span>
    - <span data-ttu-id="382f0-251">**Criterios**: *QMS*</span><span class="sxs-lookup"><span data-stu-id="382f0-251">**Criteria:** *QMS*</span></span>

    <span data-ttu-id="382f0-252">La ubicación *QMS* es una ubicación de almacén de calidad.</span><span class="sxs-lookup"><span data-stu-id="382f0-252">The *QMS* location is a warehouse location for quality.</span></span>

1. <span data-ttu-id="382f0-253">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="382f0-253">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="382f0-254">Ahora debe cambiar la secuencia de las directivas de ubicación de pedidos de compra para el almacén *51*.</span><span class="sxs-lookup"><span data-stu-id="382f0-254">You must now change the sequence of purchase order location directives for warehouse *51*.</span></span> <span data-ttu-id="382f0-255">Guardar la nueva directiva de ubicación *51 a Calidad*, actualice la página y seleccione la directiva de ubicación en la lista.</span><span class="sxs-lookup"><span data-stu-id="382f0-255">Save the new *51 To Quality* location directive, refresh the page, and select the location directive in the list.</span></span> <span data-ttu-id="382f0-256">Luego use los botones **Ascender** y **Descender** en el panel Acciones para colocar la directiva de ubicación para el almacén *51* en el siguiente orden.</span><span class="sxs-lookup"><span data-stu-id="382f0-256">Then use the **Move up** and **Move down** buttons on the Action Pane to put the location directive for warehouse *51* in the following order.</span></span> <span data-ttu-id="382f0-257">(Antes de seleccionar **Ascender** o **Descender**, debe seleccionar una directiva de ubicación en la lista).</span><span class="sxs-lookup"><span data-stu-id="382f0-257">(Before you select **Move up** or **Move down**, you must select a location directive in the list.)</span></span>

    1. <span data-ttu-id="382f0-258">51 a Calidad</span><span class="sxs-lookup"><span data-stu-id="382f0-258">51 To Quality</span></span>
    2. <span data-ttu-id="382f0-259">51 PO directo</span><span class="sxs-lookup"><span data-stu-id="382f0-259">51 PO Direct</span></span>
    3. <span data-ttu-id="382f0-260">51 QMS</span><span class="sxs-lookup"><span data-stu-id="382f0-260">51 QMS</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="382f0-261">Elementos de menú del dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="382f0-261">Mobile device menu items</span></span>

<span data-ttu-id="382f0-262">Configure un elemento de menú para que los dispositivos móviles puedan realizar la función **Control de calidad**.</span><span class="sxs-lookup"><span data-stu-id="382f0-262">Configure a menu item so that mobile devices can perform the **Quality Check** function.</span></span>

#### <a name="purchase-putaway"></a><span data-ttu-id="382f0-263">Ubicación de compra</span><span class="sxs-lookup"><span data-stu-id="382f0-263">Purchase putaway</span></span>

1. <span data-ttu-id="382f0-264">Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="382f0-264">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="382f0-265">En la lista, seleccione el elemento de menú **Ubicación de compra**.</span><span class="sxs-lookup"><span data-stu-id="382f0-265">In the list, select the **Purchase put-away** menu item.</span></span>
1. <span data-ttu-id="382f0-266">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="382f0-266">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="382f0-267">En la sección **Clases de trabajo**, seleccione **Nuevo** para agregar una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="382f0-267">In the **Work classes** section, select **New** to add a row to the grid.</span></span>
1. <span data-ttu-id="382f0-268">Establezca los siguientes valores en la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="382f0-268">In the new row, set the following values:</span></span>

    - <span data-ttu-id="382f0-269">**Id. de la clase de trabajo**: *Control de calidad*</span><span class="sxs-lookup"><span data-stu-id="382f0-269">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="382f0-270">Especifique el nombre de la [clase de trabajo](#work-class) que creó anteriormente para el trabajo de control de calidad.</span><span class="sxs-lookup"><span data-stu-id="382f0-270">Enter the name of the [work class](#work-class) that you created earlier for quality control work.</span></span>

    - <span data-ttu-id="382f0-271">**Tipo de orden de trabajo**: *Calidad en control de calidad*</span><span class="sxs-lookup"><span data-stu-id="382f0-271">**Work order type:** *Quality in quality check*</span></span>

1. <span data-ttu-id="382f0-272">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="382f0-272">On the Action Pane, select **Save**.</span></span>

#### <a name="purchase-order-line-receiving"></a><span data-ttu-id="382f0-273">Recepción de línea del pedido de compra</span><span class="sxs-lookup"><span data-stu-id="382f0-273">Purchase order line receiving</span></span>

1. <span data-ttu-id="382f0-274">Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="382f0-274">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="382f0-275">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="382f0-275">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="382f0-276">Establezca los siguientes valores en el encabezado:</span><span class="sxs-lookup"><span data-stu-id="382f0-276">In the header, set the following values:</span></span>

    - <span data-ttu-id="382f0-277">**Nombre del elemento del menú:** *Recepción de línea de pedido*</span><span class="sxs-lookup"><span data-stu-id="382f0-277">**Menu item name:** *PO line receiving*</span></span>
    - <span data-ttu-id="382f0-278">**Título:** *Recepción de línea de pedido*</span><span class="sxs-lookup"><span data-stu-id="382f0-278">**Title:** *PO line receiving*</span></span>
    - <span data-ttu-id="382f0-279">**Modo:** *Trabajo*</span><span class="sxs-lookup"><span data-stu-id="382f0-279">**Mode:** *Work*</span></span>
    - <span data-ttu-id="382f0-280">**Usar trabajo existente:** *No*</span><span class="sxs-lookup"><span data-stu-id="382f0-280">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="382f0-281">En la ficha desplegable **General**, establezca los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="382f0-281">On the **General** FastTab, set the following values.</span></span> <span data-ttu-id="382f0-282">Acepte los valores predeterminados del resto de campos.</span><span class="sxs-lookup"><span data-stu-id="382f0-282">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="382f0-283">**Proceso de creación de trabajo** *Recepción y colocación de línea de pedido de compra*</span><span class="sxs-lookup"><span data-stu-id="382f0-283">**Work creation process:** *Purchase order line receiving and put away*</span></span>
    - <span data-ttu-id="382f0-284">**Generar matrícula de entidad de almacén:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="382f0-284">**Generate license plate:** *Yes*</span></span>
    - <span data-ttu-id="382f0-285">**Plantilla de trabajo:**: *Recepción de 51 PO*</span><span class="sxs-lookup"><span data-stu-id="382f0-285">**Work template:** *51 PO Receipt*</span></span>

1. <span data-ttu-id="382f0-286">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="382f0-286">On the Action Pane, select **Save**.</span></span>

#### <a name="add-the-menu-item-to-a-mobile-device-menu"></a><span data-ttu-id="382f0-287">Agregar el elemento de menú a un menú de dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="382f0-287">Add the menu item to a mobile device menu</span></span>

1. <span data-ttu-id="382f0-288">Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="382f0-288">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="382f0-289">En el panel de la izquierda, selección el menú **Entrada**.</span><span class="sxs-lookup"><span data-stu-id="382f0-289">In the left pane, select the **Inbound** menu.</span></span>
1. <span data-ttu-id="382f0-290">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="382f0-290">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="382f0-291">En la columna **Menús disponibles y elementos de menú**, seleccione el nuevo elemento de menú **Recepción de línea de pedido**.</span><span class="sxs-lookup"><span data-stu-id="382f0-291">In the **Available menus and menu items** column, select the new **PO line receiving** menu item.</span></span>
1. <span data-ttu-id="382f0-292">Seleccione el botón de flecha derecha para mover **Recepción de línea de pedido+** a la columna **Estructura del menú**.</span><span class="sxs-lookup"><span data-stu-id="382f0-292">Select the right arrow button to move **PO line receiving** to the **Menu structure** column.</span></span>
1. <span data-ttu-id="382f0-293">En la columna **Estructura del menú**, seleccione **Recepción de línea de pedido** y luego seleccione el botón de flecha hacia arriba o hacia abajo para mover el elemento del menú a la posición deseada en el menú del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="382f0-293">In the **Menu structure** column, select **PO line receiving**, and then select the up arrow or down arrow button to move the menu item to the desired position on the mobile device menu.</span></span>
1. <span data-ttu-id="382f0-294">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="382f0-294">On the Action Pane, select **Save**.</span></span>

## <a name="example-scenario"></a><a name="example-scenario"></a><span data-ttu-id="382f0-295">Supuesto de ejemplo</span><span class="sxs-lookup"><span data-stu-id="382f0-295">Example scenario</span></span>

<span data-ttu-id="382f0-296">Después de haber puesto a disposición todos los datos de ejemplo descritos anteriormente y configurarlos, puede trabajar en este escenario para probar la característica *Control de calidad*.</span><span class="sxs-lookup"><span data-stu-id="382f0-296">After you've made all the previously described sample data available and set it up, you can work through this scenario to try out the *Quality check* feature.</span></span> <span data-ttu-id="382f0-297">Los valores que se muestran en este escenario suponen que está trabajando con los datos de demostración estándar, que seleccionó la entidad jurídica **USMF** y que preparó los registros de ejemplo que se describen anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="382f0-297">The values that are shown in this scenario assume that you're working with the standard demo data, that you selected the **USMF** legal entity, and that you prepared the sample records that are described earlier in this topic.</span></span> <span data-ttu-id="382f0-298">Este escenario también sirve como ejemplo que muestra cómo se puede usar la característica en una configuración de producción.</span><span class="sxs-lookup"><span data-stu-id="382f0-298">This scenario also serves as an example that shows how the feature can be used in a production setting.</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="382f0-299">Crear un pedido de compra</span><span class="sxs-lookup"><span data-stu-id="382f0-299">Create a purchase order</span></span>

1. <span data-ttu-id="382f0-300">Vaya a **Adquisición y abastecimiento \> Pedidos de compra \> Todos los pedidos de compra**.</span><span class="sxs-lookup"><span data-stu-id="382f0-300">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="382f0-301">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="382f0-301">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="382f0-302">En el cuadro de diálogo **Crear pedido de compras**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="382f0-302">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="382f0-303">**Cuenta del proveedor:** *104*</span><span class="sxs-lookup"><span data-stu-id="382f0-303">**Vendor account:** *104*</span></span>
    - <span data-ttu-id="382f0-304">**Almacén**: *51*</span><span class="sxs-lookup"><span data-stu-id="382f0-304">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="382f0-305">Seleccione **Aceptar** para crear el nuevo cuadro de diálogo y abrir el nuevo pedido de compras.</span><span class="sxs-lookup"><span data-stu-id="382f0-305">Select **OK** to close the dialog box and open the new purchase order.</span></span>
1. <span data-ttu-id="382f0-306">En la ficha desplegable **Líneas de pedido de ventas**, la cuadrícula contiene una nueva línea vacía.</span><span class="sxs-lookup"><span data-stu-id="382f0-306">On the **Purchase order lines** FastTab, the grid contains a new, blank line.</span></span> <span data-ttu-id="382f0-307">En esta línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="382f0-307">On this line, set the following values:</span></span>

    - <span data-ttu-id="382f0-308">**Código de artículo:** *M9203*</span><span class="sxs-lookup"><span data-stu-id="382f0-308">**Item number:** *M9203*</span></span>
    - <span data-ttu-id="382f0-309">**Cantidad:** *3*</span><span class="sxs-lookup"><span data-stu-id="382f0-309">**Quantity:** *3*</span></span>
    - <span data-ttu-id="382f0-310">**Unidad:** *PL*</span><span class="sxs-lookup"><span data-stu-id="382f0-310">**Unit:** *PL*</span></span>

1. <span data-ttu-id="382f0-311">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="382f0-311">On the Action Pane, select **Save**.</span></span>

### <a name="process-quality-check-receiving"></a><span data-ttu-id="382f0-312">Proceso de control de calidad de recepción</span><span class="sxs-lookup"><span data-stu-id="382f0-312">Process quality check receiving</span></span>

<span data-ttu-id="382f0-313">Una vez que se ha creado el pedido de compra, se puede recibir utilizando el elemento de menú **Recepción de línea de pedido** y la característica *Control de calidad*.</span><span class="sxs-lookup"><span data-stu-id="382f0-313">After the purchase order has been created, it can be received by using the **PO line receiving** menu item and the functionality of the *Quality check* feature.</span></span>

#### <a name="receive-pallet-1"></a><span data-ttu-id="382f0-314">Recibir pallet1</span><span class="sxs-lookup"><span data-stu-id="382f0-314">Receive pallet 1</span></span>

1. <span data-ttu-id="382f0-315">Inicie sesión en la aplicación de almacén como un usuario en el almacén *51*.</span><span class="sxs-lookup"><span data-stu-id="382f0-315">Sign in to the warehouse app as a user for warehouse *51*.</span></span> <span data-ttu-id="382f0-316">(Escriba *51* como el identificador de usuario y *1* como la contraseña).</span><span class="sxs-lookup"><span data-stu-id="382f0-316">(Enter *51* as the user ID and *1* as the password.)</span></span>
1. <span data-ttu-id="382f0-317">Vaya a **Entrante \> Recepción de línea de pedido**.</span><span class="sxs-lookup"><span data-stu-id="382f0-317">Go to **Inbound \> PO line receiving**.</span></span>
1. <span data-ttu-id="382f0-318">En el campo **PONUM**, introduzca el número de orden de compra.</span><span class="sxs-lookup"><span data-stu-id="382f0-318">In the **PONUM** field, enter the purchase order number.</span></span>
1. <span data-ttu-id="382f0-319">Confirme el número pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="382f0-319">Confirm the purchase order number.</span></span>
1. <span data-ttu-id="382f0-320">En el capo **LINENO**, escriba el número de la línea de pedido de compra que se está recibiendo.</span><span class="sxs-lookup"><span data-stu-id="382f0-320">In the **LINENUM** field, enter the number of the purchase order line that is being received.</span></span> <span data-ttu-id="382f0-321">Debido a que el pedido solo tiene una línea en este escenario, especificará *1* en el campo **LINENO** para cada paso de recepción.</span><span class="sxs-lookup"><span data-stu-id="382f0-321">Because the order has only one line in this scenario, you will enter *1* in the **LINENUM** field for each receiving step.</span></span>
1. <span data-ttu-id="382f0-322">Confirmar el número de línea.</span><span class="sxs-lookup"><span data-stu-id="382f0-322">Confirm the line number.</span></span>
1. <span data-ttu-id="382f0-323">En el campo **CANT.**, indique la cantidad a recibir.</span><span class="sxs-lookup"><span data-stu-id="382f0-323">In the **QTY** field, enter the quantity to receive.</span></span> <span data-ttu-id="382f0-324">Debido a que el pedido de compra es para tres pallets (*PL*) en este escenario, y hay tres pasos de recepción, ingresará *1* en el camp **CANT.** para cada paso de recepción.</span><span class="sxs-lookup"><span data-stu-id="382f0-324">Because the purchase order is for three pallets (*PL*) in this scenario, and there are three receiving steps, you will enter *1* in the **QTY** field for each receiving step.</span></span>
1. <span data-ttu-id="382f0-325">Confirme la cantidad.</span><span class="sxs-lookup"><span data-stu-id="382f0-325">Confirm the quantity.</span></span>

    <span data-ttu-id="382f0-326">La página **Control de calidad** que aparece no tiene campos de entrada.</span><span class="sxs-lookup"><span data-stu-id="382f0-326">The **Quality check** page that appears has no entry fields.</span></span> <span data-ttu-id="382f0-327">Solo tiene el botón de confirmación (marca de verificación) en la parte inferior y el botón Menú (**≡**) en la parte superior.</span><span class="sxs-lookup"><span data-stu-id="382f0-327">It has only the confirmation (check mark) button at the bottom and the Menu button (**≡**) at the top.</span></span> <span data-ttu-id="382f0-328">(El botón Menú a veces se denomina hamburguesa o botón de hamburguesa). Para acelerar el proceso de control de calidad, cuando el pallet pase el control de calidad, el usuario simplemente confirma la página **Control de calidad**.</span><span class="sxs-lookup"><span data-stu-id="382f0-328">(The Menu button is sometimes referred to as the hamburger or the hamburger button.) To expedite the quality check process, when the pallet passes the quality check, the user just confirms the **Quality check** page.</span></span>

    <span data-ttu-id="382f0-329">![Página Control de calidad](media/quality-check.png "Página Control de calidad")</span><span class="sxs-lookup"><span data-stu-id="382f0-329">![Quality check page](media/quality-check.png "Quality check page")</span></span>

1. <span data-ttu-id="382f0-330">Seleccione el botón de confirmación para pasar el control de calidad para el pallet 1 desde la línea 1.</span><span class="sxs-lookup"><span data-stu-id="382f0-330">Select the confirmation button to pass the quality check for pallet 1 from line 1.</span></span>

    <span data-ttu-id="382f0-331">La página **Pedidos de compra: colocar** que aparece muestra detalles del trabajo de colocación:</span><span class="sxs-lookup"><span data-stu-id="382f0-331">The **Purchase orders: Put** page that appears shows details of the put work:</span></span>

    - <span data-ttu-id="382f0-332">**UBI.**: la ubicación determinada por el sistema.</span><span class="sxs-lookup"><span data-stu-id="382f0-332">**LOC:** The system determined location</span></span>

        <span data-ttu-id="382f0-333">Esta ubicación es la ubicación de almacenamiento designada para recibir el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="382f0-333">This location is the designated putaway location for purchase order receiving.</span></span>

    - <span data-ttu-id="382f0-334">**LP**: el identificador de la matricula de entidad generado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="382f0-334">**LP:** The system-generated License plate ID</span></span>
    - <span data-ttu-id="382f0-335">**Artículo**: *M9203*</span><span class="sxs-lookup"><span data-stu-id="382f0-335">**Item:** *M9203*</span></span>
    - <span data-ttu-id="382f0-336">**Cant.**: *1 PL: 100 ea*</span><span class="sxs-lookup"><span data-stu-id="382f0-336">**Qty:** *1 PL: 100 ea*</span></span>

    <span data-ttu-id="382f0-337">La descripción del artículo también se muestra.</span><span class="sxs-lookup"><span data-stu-id="382f0-337">The item description is also shown.</span></span>

1. <span data-ttu-id="382f0-338">Confirme el trabajo de ubicación.</span><span class="sxs-lookup"><span data-stu-id="382f0-338">Confirm the putaway work.</span></span>

    <span data-ttu-id="382f0-339">En la página **Tarea** para la línea de pedido de compra, recibirá un mensaje de "Trabajo completado".</span><span class="sxs-lookup"><span data-stu-id="382f0-339">On the **Task** page for purchase order line receiving, you receive a "Work Completed" message.</span></span> <span data-ttu-id="382f0-340">El campo **LINENO** está disponible para que pueda comenzar a recibir el siguiente pallet.</span><span class="sxs-lookup"><span data-stu-id="382f0-340">The **LINENUM** field is available so that you can start to receive the next pallet.</span></span>

#### <a name="receive-pallet-2"></a><span data-ttu-id="382f0-341">Recibir pallet2</span><span class="sxs-lookup"><span data-stu-id="382f0-341">Receive pallet 2</span></span>

<span data-ttu-id="382f0-342">Para este escenario, el pallet 2 será rechazado.</span><span class="sxs-lookup"><span data-stu-id="382f0-342">For this scenario, pallet 2 will be rejected.</span></span>

1. <span data-ttu-id="382f0-343">En campo **LINENO**, especifique *1* y confirme el número de línea.</span><span class="sxs-lookup"><span data-stu-id="382f0-343">In the **LINENUM** field, enter *1*, and confirm the line number.</span></span>
1. <span data-ttu-id="382f0-344">El campo **CANT.** está ahora disponible.</span><span class="sxs-lookup"><span data-stu-id="382f0-344">The **QTY** field is now available.</span></span> <span data-ttu-id="382f0-345">Escriba *1* y confirme la cantidad.</span><span class="sxs-lookup"><span data-stu-id="382f0-345">Enter *1*, and confirm the quantity.</span></span>

    <span data-ttu-id="382f0-346">Aparece la página **Control de calidad**.</span><span class="sxs-lookup"><span data-stu-id="382f0-346">The **Quality check** page appears.</span></span> <span data-ttu-id="382f0-347">Para este recibo, el pallet será rechazado por calidad y se colocará en la ubicación de calidad *QMS*.</span><span class="sxs-lookup"><span data-stu-id="382f0-347">For this receipt, the pallet will be rejected for quality, and it will be put into the *QMS* quality location.</span></span>

1. <span data-ttu-id="382f0-348">Seleccione el botón Menú (**≡**) en la parte superior de la página y luego, en el menú, seleccione **Rechazar**.</span><span class="sxs-lookup"><span data-stu-id="382f0-348">Select the Menu button (**≡**) at the top of the page, and then, on the menu, select **Reject**.</span></span>
1. <span data-ttu-id="382f0-349">En la página **Tarea** que aparece, especifique **QMS** como la ubicación de *Colocar* para enviar el pallet para una inspección más detallada.</span><span class="sxs-lookup"><span data-stu-id="382f0-349">On the **Task** page that appears, enter **QMS** as the *Put* location to send the pallet to for further inspection.</span></span>

    <span data-ttu-id="382f0-350">La página **Calidad en control de calidad: colocar** que aparece muestra detalles del trabajo de colocación:</span><span class="sxs-lookup"><span data-stu-id="382f0-350">The **Quality in quality check: Put** page that appears shows details of the put work:</span></span>

    - <span data-ttu-id="382f0-351">**UBI.**: *QMS*</span><span class="sxs-lookup"><span data-stu-id="382f0-351">**LOC:** *QMS*</span></span>

        <span data-ttu-id="382f0-352">Esta ubicación es la ubicación de almacenamiento designada para recibir la calidad rechazada.</span><span class="sxs-lookup"><span data-stu-id="382f0-352">This location is the designated putaway location for rejected quality receiving.</span></span>

    - <span data-ttu-id="382f0-353">**LP**: el identificador de la matricula de entidad generado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="382f0-353">**LP:** The system-generated License plate ID</span></span>
    - <span data-ttu-id="382f0-354">**Artículo**: *M9203*</span><span class="sxs-lookup"><span data-stu-id="382f0-354">**Item:** *M9203*</span></span>
    - <span data-ttu-id="382f0-355">**Cant.**: *1 PL: 100 ea*</span><span class="sxs-lookup"><span data-stu-id="382f0-355">**Qty:** *1 PL: 100 ea*</span></span>

    <span data-ttu-id="382f0-356">La descripción del artículo también se muestra.</span><span class="sxs-lookup"><span data-stu-id="382f0-356">The item description is also shown.</span></span>

1. <span data-ttu-id="382f0-357">Confirme el trabajo de ubicación.</span><span class="sxs-lookup"><span data-stu-id="382f0-357">Confirm the putaway work.</span></span>

    <span data-ttu-id="382f0-358">En la página **Tarea** para la línea de pedido de compra, recibirá un mensaje de "Trabajo completado".</span><span class="sxs-lookup"><span data-stu-id="382f0-358">On the **Task** page for purchase order line receiving, you receive a "Work Completed" message.</span></span> <span data-ttu-id="382f0-359">El campo **LINENO** está disponible para que pueda comenzar a recibir el siguiente pallet.</span><span class="sxs-lookup"><span data-stu-id="382f0-359">The **LINENUM** field is available so that you can start to receive the next pallet.</span></span>

<span data-ttu-id="382f0-360">Ahora ha completado el control de calidad y ha creado un pedido de calidad para el pallet rechazado.</span><span class="sxs-lookup"><span data-stu-id="382f0-360">You've now completed the quality check and created a quality order for the rejected pallet.</span></span> <span data-ttu-id="382f0-361">Para ver el pedido de calidad que se ha creado a partir del control de calidad con error, vaya a **Gestión de inventarios \> Tareas periódicas \> Administración de la calidad \> Pedidos de calidad**.</span><span class="sxs-lookup"><span data-stu-id="382f0-361">To view the order that was created, go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>

<span data-ttu-id="382f0-362">Las pruebas de pedidos de calidad ahora se pueden procesar.</span><span class="sxs-lookup"><span data-stu-id="382f0-362">Quality order testing can now be processed.</span></span> <span data-ttu-id="382f0-363">Las pruebas de calidad no están cubiertas en este tema.</span><span class="sxs-lookup"><span data-stu-id="382f0-363">Quality testing isn't covered in this topic.</span></span>

<span data-ttu-id="382f0-364">Para obtener más información acerca de la administración de calidad, consulte [Visión general de la Administración de calidad](../inventory/enable-quality-management.md).</span><span class="sxs-lookup"><span data-stu-id="382f0-364">For more information about quality management, see [Quality management overview](../inventory/enable-quality-management.md)</span></span>

#### <a name="receive-pallet-3"></a><span data-ttu-id="382f0-365">Recibir pallet3</span><span class="sxs-lookup"><span data-stu-id="382f0-365">Receive pallet 3</span></span>

<span data-ttu-id="382f0-366">Para este escenario, el pallet 3 será aceptado.</span><span class="sxs-lookup"><span data-stu-id="382f0-366">For this scenario, pallet 3 will be accepted.</span></span>

1. <span data-ttu-id="382f0-367">En campo **LINENO**, especifique *1* y confirme el número de línea.</span><span class="sxs-lookup"><span data-stu-id="382f0-367">In the **LINENUM** field, enter *1*, and confirm the line number.</span></span>
1. <span data-ttu-id="382f0-368">El campo **CANT.** está ahora disponible.</span><span class="sxs-lookup"><span data-stu-id="382f0-368">The **QTY** field is now available.</span></span> <span data-ttu-id="382f0-369">Escriba *1* y confirme la cantidad.</span><span class="sxs-lookup"><span data-stu-id="382f0-369">Enter *1*, and confirm the quantity.</span></span>

    <span data-ttu-id="382f0-370">Aparece la página **Control de calidad**.</span><span class="sxs-lookup"><span data-stu-id="382f0-370">The **Quality check** page appears.</span></span> <span data-ttu-id="382f0-371">Para este recibo, el pallet será aceptado por calidad y se colocará en la ubicación de colocación masiva.</span><span class="sxs-lookup"><span data-stu-id="382f0-371">For this receipt, the pallet will be accepted for quality, and it will be put into a bulk putaway location.</span></span>

1. <span data-ttu-id="382f0-372">Seleccione el botón de confirmación para pasar el control de calidad.</span><span class="sxs-lookup"><span data-stu-id="382f0-372">Select the confirmation button to pass the quality check.</span></span>

    <span data-ttu-id="382f0-373">La página **Pedidos de compra: colocar** que aparece muestra detalles del trabajo de colocación:</span><span class="sxs-lookup"><span data-stu-id="382f0-373">The **Purchase orders: Put** page that appears shows details of the put work:</span></span>

    - <span data-ttu-id="382f0-374">**UBI.**: la ubicación determinada por el sistema.</span><span class="sxs-lookup"><span data-stu-id="382f0-374">**LOC:** The system determined location</span></span>

        <span data-ttu-id="382f0-375">Esta ubicación es la ubicación de almacenamiento designada para recibir el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="382f0-375">This location is the designated putaway location for purchase order receiving.</span></span>

    - <span data-ttu-id="382f0-376">**LP**: el identificador de la matricula de entidad generado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="382f0-376">**LP:** The system-generated License plate ID</span></span>
    - <span data-ttu-id="382f0-377">**Artículo**: *M9203*</span><span class="sxs-lookup"><span data-stu-id="382f0-377">**Item:** *M9203*</span></span>
    - <span data-ttu-id="382f0-378">**Cant.**: *1 PL: 100 ea*</span><span class="sxs-lookup"><span data-stu-id="382f0-378">**Qty:** *1 PL: 100 ea*</span></span>

    <span data-ttu-id="382f0-379">La descripción del artículo también se muestra.</span><span class="sxs-lookup"><span data-stu-id="382f0-379">The item description is also shown.</span></span>

1. <span data-ttu-id="382f0-380">Confirme el trabajo de ubicación.</span><span class="sxs-lookup"><span data-stu-id="382f0-380">Confirm the putaway work.</span></span>

    <span data-ttu-id="382f0-381">En la página **Tarea** para la línea de pedido de compra, recibirá un mensaje de "Trabajo completado".</span><span class="sxs-lookup"><span data-stu-id="382f0-381">On the **Task** page for purchase order line receiving, you receive a "Work Completed" message.</span></span> <span data-ttu-id="382f0-382">El campo **LINENO** está disponible para que pueda comenzar a recibir el siguiente pallet.</span><span class="sxs-lookup"><span data-stu-id="382f0-382">The **LINENUM** field is available so that you can start to receive the next pallet.</span></span>

1. <span data-ttu-id="382f0-383">Seleccione el botón Menú (**≡**) en la parte superior de la página y luego, en el menú, seleccione **Cancelar** para regresar al menú.</span><span class="sxs-lookup"><span data-stu-id="382f0-383">Select the Menu button (**≡**) at the top of the page, and then, on the menu, select **Cancel** to return to the menu.</span></span>

<span data-ttu-id="382f0-384">Ahora puede cerrar la aplicación móvil.</span><span class="sxs-lookup"><span data-stu-id="382f0-384">You can now close the mobile app.</span></span>