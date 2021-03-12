---
title: Reabastecimiento según la capacidad de la ubicación
description: Este tema proporciona información sobre la característica Reabastecimiento según la capacidad de la ubicación. Esta característica permite crear todo el trabajo de reabastecimiento que se requerirá para el día y administra la disponibilidad de ese trabajo de reabastecimiento para garantizar que la ubicación de picking no se quede sin inventario ni supere la capacidad.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocationLimit
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 3f94053920b475ef9190b5ac65a5f9ca01dcd4a1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996132"
---
# <a name="replenishment-over-location-capacity"></a><span data-ttu-id="bb1b5-104">Reabastecimiento según la capacidad de la ubicación</span><span class="sxs-lookup"><span data-stu-id="bb1b5-104">Replenishment over location capacity</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bb1b5-105">Algunos almacenes de gran volumen o con espacio limitado deben enviar más cantidad de un artículo en un día de lo que cabe en el lugar de picking.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-105">Some high-volume or space-constrained warehouses must ship more quantity of an item in a day than will fit in the picking location.</span></span> <span data-ttu-id="bb1b5-106">La característica *Reabastecimiento según la capacidad de la ubicación* permite crear todo el trabajo de reabastecimiento que se requerirá para el día y administra la disponibilidad de ese trabajo de reabastecimiento para garantizar que la ubicación de picking no se quede sin inventario ni supere la capacidad.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-106">The *Replenishment over location capacity* feature enables all replenishment work that will be required for the day to be created and manages availability of that replenishment work to ensure that the picking location neither runs out of inventory nor goes above capacity.</span></span>

<span data-ttu-id="bb1b5-107">La característica permite que se cree más trabajo de reabastecimiento de lo que cabe en una ubicación, y bloquea el trabajo de reabastecimiento cuando la ubicación está llena.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-107">The feature enables more replenishment work to be created than will fit in a location, and it blocks replenishment work from being completed when the location is full.</span></span> <span data-ttu-id="bb1b5-108">A medida que el inventario en la ubicación de picking desciende por debajo de un umbral configurable, se pone a disposición más trabajo de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-108">As inventory in the picking location drops below a configurable threshold, more replenishment work is made available.</span></span>

## <a name="turn-on-the-replenishment-over-location-capacity-feature"></a><span data-ttu-id="bb1b5-109">Activar la característica Reabastecimiento según la capacidad de la ubicación</span><span class="sxs-lookup"><span data-stu-id="bb1b5-109">Turn on the Replenishment over location capacity feature</span></span>

<span data-ttu-id="bb1b5-110">Para que esta característica esté disponible, active las siguientes características en [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (en este orden):</span><span class="sxs-lookup"><span data-stu-id="bb1b5-110">To make this feature available, turn on the following features in [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (in this order):</span></span>

1. <span data-ttu-id="bb1b5-111">Bloqueo de trabajo en toda la organización</span><span class="sxs-lookup"><span data-stu-id="bb1b5-111">Organization-wide work blocking</span></span>
1. <span data-ttu-id="bb1b5-112">Reabastecimiento según la capacidad de la ubicación</span><span class="sxs-lookup"><span data-stu-id="bb1b5-112">Replenishment over location capacity</span></span>

## <a name="set-up-the-feature-for-the-example-scenario"></a><span data-ttu-id="bb1b5-113">Configure la función para el escenario de ejemplo</span><span class="sxs-lookup"><span data-stu-id="bb1b5-113">Set up the feature for the example scenario</span></span>

<span data-ttu-id="bb1b5-114">Esta sección proporciona pautas y un ejemplo que muestra cómo configurar la característica Control de calidad y preparar datos de muestra para el escenario de ejemplo que se proporciona más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-114">This section provides guidelines and an example that shows how to set up this feature and prepare sample data for the example scenario that is provided later in this topic.</span></span>

### <a name="enable-sample-data"></a><span data-ttu-id="bb1b5-115">Habilitar datos de muestra</span><span class="sxs-lookup"><span data-stu-id="bb1b5-115">Enable sample data</span></span>

<span data-ttu-id="bb1b5-116">Para trabajar en el [escenario de ejemplo](#example-scenario) mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) estándar.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-116">To work through the [example scenario](#example-scenario) by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="bb1b5-117">Además, también debe seleccionar la entidad legal **USMF** antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-117">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

### <a name="location-profile"></a><span data-ttu-id="bb1b5-118">Perfil de ubicación</span><span class="sxs-lookup"><span data-stu-id="bb1b5-118">Location profile</span></span>

<span data-ttu-id="bb1b5-119">Habilite la funcionalidad de reposición según la capacidad en el perfil de ubicación.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-119">Enable the replenish over capacity functionality on the location profile.</span></span>

1. <span data-ttu-id="bb1b5-120">Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Perfiles de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-120">Go to **Warehouse management \> Setup \> Warehouse \> Locations profiles**.</span></span>
1. <span data-ttu-id="bb1b5-121">En el panel izquierdo, seleccione **PICK-06**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-121">In the left pane, select **PICK-06**.</span></span>
1. <span data-ttu-id="bb1b5-122">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-122">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="bb1b5-123">En la ficha desplegable **Reabastecimiento**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="bb1b5-123">On the **Replenishment** FastTab, set the following values:</span></span>

    - <span data-ttu-id="bb1b5-124">**Exceder la capacidad de ubicación**: *Sí*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-124">**Exceed Location Capacity:** *Yes*</span></span>

        <span data-ttu-id="bb1b5-125">Cuando está habilitada, la capacidad máxima de la ubicación podrá superarse por el trabajo de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-125">When enabled, the maximum capacity of the location will be allowed to be exceeded by replenishment work.</span></span> <span data-ttu-id="bb1b5-126">Esto también habilita otros campos en la ficha desplegable **Reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-126">This also enables other fields on the **Replenishment** FastTab.</span></span>

    - <span data-ttu-id="bb1b5-127">**Tipo de umbral de disponibilidad de trabajo**: *Cantidad*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-127">**Work availability threshold type:** *Quantity*</span></span>

        <span data-ttu-id="bb1b5-128">Este campo define el método que se utiliza para determinar cuándo se debe liberar más trabajo.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-128">This field defines the method that is used to determine when more work should be released.</span></span> <span data-ttu-id="bb1b5-129">Puede despachar según la cantidad o un porcentaje:</span><span class="sxs-lookup"><span data-stu-id="bb1b5-129">You can release by either quantity or a percentage:</span></span>

        - <span data-ttu-id="bb1b5-130">*Porcentaje*: seleccione esta opción para usar el porcentaje de capacidad que se basa en los límites de existencias o en la volumetría.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-130">*Percent* – Select this option to use percentage capacity that is based on stocking limits or volumetrics.</span></span> <span data-ttu-id="bb1b5-131">Al seleccionar esta opción, se habilita el campo **Porcentaje de desbordamiento** y deshabilita los dos campos relacionados con la cantidad, **Cantidad de desbordamiento** y **Unidad de desbordamiento**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-131">Selecting this option enables the **Overflow percentage** field, and disables the two quantity related fields,  **Overflow quantity** and **Overflow unit**.</span></span>

            <span data-ttu-id="bb1b5-132">Puede usar esta opción si las ubicaciones de picking usan volumetría.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-132">You can use this option if the picking locations use volumetrics.</span></span>

            <span data-ttu-id="bb1b5-133">Si esta opción está seleccionada, configure el campo **Porcentaje de desbordamiento** en el porcentaje en el que se pondrá a disposición más trabajo de reposición.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-133">If this option is selected, set the **Overflow percentage** field to the percentage at which more replenishment work will be made available.</span></span>

        - <span data-ttu-id="bb1b5-134">*Cantidad*: seleccione esta opción para usar un valor de cantidad específico.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-134">*Quantity* – Select this option to use a specific quantity value.</span></span> <span data-ttu-id="bb1b5-135">Al seleccionar esta opción, se deshabilita el campo **Porcentaje de desbordamiento** y se habilita los dos campos relacionados con la cantidad, **Cantidad de desbordamiento** y **Unidad de desbordamiento**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-135">Selecting this option disables the **Overflow percentage** field and enables **Overflow quantity** and **Overflow unit** fields.</span></span>

            <span data-ttu-id="bb1b5-136">Use esta opción cuando no esté utilizando los volúmenes para las ubicaciones que se están reabasteciendo, o cuando tenga cantidades consistentes en las que desea que se lleve más inventario a la ubicación.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-136">Use this option when you aren't using volumetrics for the locations that are being replenished, or when you have consistent quantities at which you want more inventory to be brought to the location.</span></span>

           <span data-ttu-id="bb1b5-137">Si esta opción está seleccionada, configure los campos **Cantidad de desbordamiento** y **Unidad de desbordamiento** en la cantidad y la unidad en la que se pondrá a disposición más trabajo de reposición.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-137">If this option is selected, set the **Overflow quantity** and **Overflow unit** fields to the quantity and unit at which more replenishment work will be made available.</span></span>

    - <span data-ttu-id="bb1b5-138">**Cantidad de desbordamiento:** *0,65*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-138">**Overflow quantity:** *0.65*</span></span>

        <span data-ttu-id="bb1b5-139">Este campo define la cantidad a la que se desborda la ubicación.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-139">This field defines the quantity at which the location overflows.</span></span>

        <span data-ttu-id="bb1b5-140">El trabajo estará disponible siempre que la suma de la cantidad disponible en la ubicación y la cantidad de trabajo estén por debajo de este valor.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-140">Work will be available whenever the sum of the on-hand quantity in the location and the work quantity is below this value.</span></span> <span data-ttu-id="bb1b5-141">Cualquier trabajo de reabastecimiento por encima de este valor se desbloqueará manualmente.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-141">Any replenishment work above this value will be blocked and must be manually unblocked.</span></span>

        <span data-ttu-id="bb1b5-142">Los límites de inventario de ubicación se consideran cuando se calcula la cantidad de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-142">Location stocking limits are considered when the work quantity is calculated.</span></span>

    - <span data-ttu-id="bb1b5-143">**Unidad de desbordamiento**: *PL*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-143">**Overflow unit:** *PL*</span></span>

        <span data-ttu-id="bb1b5-144">Este campo define la unidad que está asociada con la cantidad de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-144">This field defines the unit that is associated with the overflow quantity.</span></span>

        <span data-ttu-id="bb1b5-145">En este caso, habrá más trabajo de reabastecimiento cuando la ubicación llegue a 0,65 pallets (PL).</span><span class="sxs-lookup"><span data-stu-id="bb1b5-145">In this case, more replenishment work will be made available when the location gets down to 0.65 pallet (PL).</span></span>

    - <span data-ttu-id="bb1b5-146">**Porcentaje de desbordamiento**</span><span class="sxs-lookup"><span data-stu-id="bb1b5-146">**Overflow percentage**</span></span>

        <span data-ttu-id="bb1b5-147">Este campo define el porcentaje al que se desborda la ubicación.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-147">This field defines the percentage at which the location overflows.</span></span>

        <span data-ttu-id="bb1b5-148">El trabajo estará disponible siempre que la suma de la cantidad disponible en la ubicación y la cantidad de trabajo estén por debajo de este porcentaje.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-148">Work will be available whenever the sum of the on-hand quantity in the location and the work quantity is below this percentage.</span></span> <span data-ttu-id="bb1b5-149">Cualquier porcentaje de cantidad de trabajo de reabastecimiento por encima de este valor se bloqueará y deberá desbloquearse manualmente.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-149">Any replenishment work quantity percentage above this value will be blocked and must be manually unblocked.</span></span>

        <span data-ttu-id="bb1b5-150">Los límites de inventario de ubicación se consideran cuando se calcula el porcentaje de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-150">Location stocking limits are considered when the work quantity percentage is calculated.</span></span> <span data-ttu-id="bb1b5-151">Si no se definen límites de inventario de ubicación, el porcentaje de cantidad de trabajo se calculará por volumen si las restricciones de volumen se definen en el perfil de ubicación.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-151">If no location stocking limits are defined, the work quantity percentage is calculated by volume if volume constraints are defined for the location profile.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bb1b5-152">Si está utilizando los datos de demostración para la entidad jurídica **USMF** y previamente se ha activado la característica *Posición de matrícula de entidad de almacén de almacén de ubicación*, debe desactivar la configuración **Habilitar el posicionamiento de matrícula de entidad de almacén** para el perfil de ubicación **A GRANEL-06** para completar los pasos móviles en el escenario de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-152">If you're using the demo data for the **USMF** legal entity and previously turned on the *Location license plate positioning* feature, you must turn off the **Enable license plate positioning** setting for the **BULK-06** location profile to complete the mobile steps in the example scenario.</span></span>

### <a name="wave-step-code"></a><span data-ttu-id="bb1b5-153">Código de paso de oleada</span><span class="sxs-lookup"><span data-stu-id="bb1b5-153">Wave step code</span></span>

> [!NOTE]
> <span data-ttu-id="bb1b5-154">Para configurar un código de paso de oleada como se describe aquí, es posible que primero deba usar [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para activar la característica que se llama *Código de paso de oleada de toda la organización*.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-154">To set up a wave step code as described here, you might first have to use [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn on the feature that is named *Organization wide wave step code*.</span></span>

1. <span data-ttu-id="bb1b5-155">Vaya a **Administración de almacenes \> Configuración \> Oleadas \> Códigos de paso de oleada**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-155">Go to **Warehouse Management \> Setup \> Waves \> Wave step codes**.</span></span>
1. <span data-ttu-id="bb1b5-156">Seleccione **Nuevo** y establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="bb1b5-156">Select **New**, and set the following values:</span></span>

    - <span data-ttu-id="bb1b5-157">**Código de paso de oleada**: *Reabast.*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-157">**Wave step code:** *Replen*</span></span>
    - <span data-ttu-id="bb1b5-158">**Descripción de paso de oleada**: *Reabastecimiento*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-158">**Wave step description:** *Replenishment*</span></span>
    - <span data-ttu-id="bb1b5-159">**Tipo de paso de oleada**: *Reabastecimiento*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-159">**Wave step type:** *Replenishment*</span></span>

1. <span data-ttu-id="bb1b5-160">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-160">Select **Save**.</span></span>

### <a name="replenishment-template"></a><span data-ttu-id="bb1b5-161">Plantilla de reabastecimiento</span><span class="sxs-lookup"><span data-stu-id="bb1b5-161">Replenishment template</span></span>

<span data-ttu-id="bb1b5-162">Las plantillas de reabastecimiento son un conjunto de reglas que controlan cuándo y cómo se reabastece un ubicación.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-162">Replenishment templates are a set of rules that control when and how a location is replenished.</span></span>

1. <span data-ttu-id="bb1b5-163">Vaya a **Administración de almacenes \> Configurar \> Reabastecimiento \> Plantillas de reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-163">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**.</span></span>
1. <span data-ttu-id="bb1b5-164">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-164">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="bb1b5-165">En la sección **Visión general**, seleccione la línea donde el campo **Reabastecer plantilla** se establece en *Solicitar reposición*.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-165">In the **Overview** section, select the line where the **Replenish template** field is set to *Demand replenish*.</span></span>
1. <span data-ttu-id="bb1b5-166">Establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="bb1b5-166">Set the following values:</span></span>

    - <span data-ttu-id="bb1b5-167">**Código de paso de oleada**: *Reabast.*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-167">**Wave step code:** *Replen*</span></span>
    - <span data-ttu-id="bb1b5-168">**Permitir demanda de oleadas para usar cantidades sin reservar:** *sí*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-168">**Allow wave demand to use unreserved quantities:** *Yes*</span></span>

1. <span data-ttu-id="bb1b5-169">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-169">Select **Save**.</span></span>

### <a name="wave-template"></a><span data-ttu-id="bb1b5-170">Plantilla de oleada</span><span class="sxs-lookup"><span data-stu-id="bb1b5-170">Wave template</span></span>

1. <span data-ttu-id="bb1b5-171">Vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-171">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="bb1b5-172">En el panel izquierdo, establezca el campo **Tipo de plantilla de oleada** en *Envío*.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-172">In the left pane, set the **Wave template type** field to *Shipping*.</span></span>
1. <span data-ttu-id="bb1b5-173">Seleccione la plantilla **Envío 61** en la lista.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-173">Select template **61 Shipping** in the list.</span></span>
1. <span data-ttu-id="bb1b5-174">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-174">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="bb1b5-175">En la ficha desplegable **General**, establezca la opción **Automatizar liberación de trabajo de reabastecimiento** en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-175">On the **General** FastTab, set the **Automate replenishment work release** option to *Yes*.</span></span>

    <span data-ttu-id="bb1b5-176">Establezca esta opción en *Sí* para crear trabajo de reabastecimiento basado en demandas y libérelo automáticamente.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-176">Set this option to *Yes* to create demand-based replenishment work and release it automatically.</span></span> <span data-ttu-id="bb1b5-177">Debe agregar el método de oleada de reabastecimiento en la plantilla de oleada, y crear una plantilla de reabastecimiento del tipo **Demanda de oleadas**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-177">You must add the replenishment wave method to the wave template and create a replenishment template of the **Wave demand** type.</span></span> <span data-ttu-id="bb1b5-178">Configure una plantilla de reabastecimiento en la página **Plantillas de reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-178">Set up a replenishment template on the **Replenishment templates** page.</span></span> <span data-ttu-id="bb1b5-179">Para configurar una plantilla de reabastecimiento, debe agregar el método de reposición a la plantilla de onda.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-179">To set up a replenishment template, you must add the replenish method to the wave template.</span></span>

1. <span data-ttu-id="bb1b5-180">Sobre la ficha desplegable **Métodos**, en la columna **Métodos seleccionados**, busque la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="bb1b5-180">On the **Methods** FastTab, in the **Selected methods** column, find the following line:</span></span>

    - <span data-ttu-id="bb1b5-181">**Nombre del método**: *reabastecer*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-181">**Method name:** *replenish*</span></span>
    - <span data-ttu-id="bb1b5-182">**Nombre**: *Reabastecimiento*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-182">**Name:** *Replenishment*</span></span>

1. <span data-ttu-id="bb1b5-183">Establezca el campo **Código de paso de oleada** para esta línea a *Reabast.*.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-183">Set the **Wave step code** field for this line to *Replen*.</span></span>
1. <span data-ttu-id="bb1b5-184">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-184">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="bb1b5-185">Supuesto de ejemplo</span><span class="sxs-lookup"><span data-stu-id="bb1b5-185">Example scenario</span></span>

<span data-ttu-id="bb1b5-186">Después de haber puesto a disposición todos los datos de ejemplo descritos anteriormente y configurarlos, puede trabajar en este escenario para probar la característica *Reabastecimiento según la capacidad de la ubicación*.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-186">After you've made all the previously described sample data available and set it up, you can work through this scenario to try out the *Replenishment over location capacity* feature.</span></span> <span data-ttu-id="bb1b5-187">Los valores que se muestran en este escenario suponen que está trabajando con los datos de demostración estándar, que seleccionó la entidad jurídica **USMF** y que preparó los registros de ejemplo que se describen anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-187">The values that are shown in this scenario assume that you're working with the standard demo data, that you selected the **USMF** legal entity, and that you prepared the sample records that are described earlier in this topic.</span></span> <span data-ttu-id="bb1b5-188">Este escenario también sirve como ejemplo que muestra cómo se puede usar la característica en una configuración de producción.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-188">This scenario also serves as an example that shows how the feature can be used in a production setting.</span></span>

### <a name="create-replenishment-work"></a><span data-ttu-id="bb1b5-189">Crear trabajo de reabastecimiento</span><span class="sxs-lookup"><span data-stu-id="bb1b5-189">Create replenishment work</span></span>

#### <a name="create-sales-order-1"></a><span data-ttu-id="bb1b5-190">Crear pedido de ventas 1</span><span class="sxs-lookup"><span data-stu-id="bb1b5-190">Create sales order 1</span></span>

1. <span data-ttu-id="bb1b5-191">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-191">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="bb1b5-192">En el panel de acciones, seleccione **Nuevo** para abrir el cuadro de diálogo para crear un nuevo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-192">On the Action Pane, select **New** to open a dialog box for creating a new sales order.</span></span>
1. <span data-ttu-id="bb1b5-193">En el cuadro de diálogo, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="bb1b5-193">In the dialog box, set the following values:</span></span>

    - <span data-ttu-id="bb1b5-194">**Cuenta de cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-194">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="bb1b5-195">**Almacén**: *61*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-195">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="bb1b5-196">Seleccione **Aceptar** para crear el pedido de ventas y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-196">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="bb1b5-197">Se abre el nuevo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-197">The new sales order is opened.</span></span> <span data-ttu-id="bb1b5-198">Incluye una nueva línea vacía en la ficha desplegable **Líneas de pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-198">It includes a new, empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="bb1b5-199">En esta línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="bb1b5-199">On this line, set the following values:</span></span>

    - <span data-ttu-id="bb1b5-200">**Código de artículo:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-200">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="bb1b5-201">**Cantidad:** *40*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-201">**Quantity:** *40*</span></span>

1. <span data-ttu-id="bb1b5-202">En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Inventario \> Reserva**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-202">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="bb1b5-203">En la página **Reserva**, seleccione **Reservar lote**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-203">On the **Reservation** page, select **Reserve lot**.</span></span>
1. <span data-ttu-id="bb1b5-204">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-204">Close the page.</span></span>
1. <span data-ttu-id="bb1b5-205">En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-205">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="bb1b5-206">Recibirá mensajes informativos que muestra el id. de oleada y el id. de envío que se crearon.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-206">You receive informational messages that show the wave and shipment IDs that were created.</span></span> <span data-ttu-id="bb1b5-207">También se crea una oleada de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-207">A replenishment wave is also created.</span></span>

    <span data-ttu-id="bb1b5-208">También recibe un mensaje de advertencia que dice: "El Id. de trabajo XXXX no se puede desbloquear porque tiene un trabajo de reabastecimiento sin terminar".</span><span class="sxs-lookup"><span data-stu-id="bb1b5-208">You also receive a warning message that states, "Work ID XXXX cannot be unblocked because it has unfinished replenishment work."</span></span>

#### <a name="create-sales-order-2"></a><span data-ttu-id="bb1b5-209">Crear pedido de ventas 2</span><span class="sxs-lookup"><span data-stu-id="bb1b5-209">Create sales order 2</span></span>

1. <span data-ttu-id="bb1b5-210">En la página **Todos los pedidos de ventas**, en el panel Acciones, seleccione **Nuevo** para abrir el cuadro de diálogo para crear un nuevo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-210">On the **All sales orders**, page, on the Action Pane, select **New** to open a dialog box for creating a new sales order.</span></span>
1. <span data-ttu-id="bb1b5-211">En el cuadro de diálogo, establezca el valor siguiente:</span><span class="sxs-lookup"><span data-stu-id="bb1b5-211">In the dialog box, set the following value:</span></span>

    - <span data-ttu-id="bb1b5-212">**Cuenta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-212">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="bb1b5-213">**Almacén**: *61*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-213">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="bb1b5-214">Seleccione **Aceptar** para crear el pedido de ventas y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-214">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="bb1b5-215">Se abre el nuevo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-215">The new sales order is opened.</span></span> <span data-ttu-id="bb1b5-216">Incluye una nueva línea vacía en la ficha desplegable **Líneas de pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-216">It includes a new, empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="bb1b5-217">En esta línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="bb1b5-217">On this line, set the following values:</span></span>

    - <span data-ttu-id="bb1b5-218">**Código de artículo:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-218">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="bb1b5-219">**Cantidad:** *60*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-219">**Quantity:** *60*</span></span>

1. <span data-ttu-id="bb1b5-220">En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Inventario \> Reserva**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-220">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="bb1b5-221">En la página **Reserva**, seleccione **Reservar lote**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-221">On the **Reservation** page, select **Reserve lot**.</span></span>
1. <span data-ttu-id="bb1b5-222">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-222">Close the page.</span></span>
1. <span data-ttu-id="bb1b5-223">En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-223">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="bb1b5-224">Recibirá mensajes informativos que muestra el id. de oleada y el id. de envío que se crearon.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-224">You receive informational messages that show the wave and shipment IDs that were created.</span></span> <span data-ttu-id="bb1b5-225">También se crea una oleada de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-225">A replenishment wave is also created.</span></span>

    <span data-ttu-id="bb1b5-226">También recibe un mensaje de advertencia que dice: "El Id. de trabajo XXXX no se puede desbloquear porque tiene un trabajo de reabastecimiento sin terminar".</span><span class="sxs-lookup"><span data-stu-id="bb1b5-226">You also receive a warning message that states, "Work ID XXXX cannot be unblocked because it has unfinished replenishment work."</span></span>

#### <a name="create-sales-order-3"></a><span data-ttu-id="bb1b5-227">Crear pedido de ventas 3</span><span class="sxs-lookup"><span data-stu-id="bb1b5-227">Create sales order 3</span></span>

1. <span data-ttu-id="bb1b5-228">En la página **Todos los pedidos de ventas**, en el panel Acciones, seleccione **Nuevo** para abrir el cuadro de diálogo para crear un nuevo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-228">On the **All sales orders** page, on the Action Pane, select **New** to open a dialog box for creating a new sales order.</span></span>
1. <span data-ttu-id="bb1b5-229">En el cuadro de diálogo, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="bb1b5-229">In the dialog box, set the following values:</span></span>

    - <span data-ttu-id="bb1b5-230">**Cuenta de cliente:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-230">**Customer account:** *US-004*</span></span>
    - <span data-ttu-id="bb1b5-231">**Almacén**: *61*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-231">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="bb1b5-232">Seleccione **Aceptar** para crear el pedido de ventas y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-232">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="bb1b5-233">Se abre el nuevo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-233">The new sales order is opened.</span></span> <span data-ttu-id="bb1b5-234">Incluye una nueva línea vacía en la ficha desplegable **Líneas de pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-234">It includes a new, empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="bb1b5-235">En esta línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="bb1b5-235">On this line, set the following values:</span></span>

    - <span data-ttu-id="bb1b5-236">**Código de artículo:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-236">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="bb1b5-237">**Cantidad:** *30*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-237">**Quantity:** *30*</span></span>

1. <span data-ttu-id="bb1b5-238">En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Inventario \> Reserva**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-238">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="bb1b5-239">En la página **Reserva**, seleccione **Reservar lote**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-239">On the **Reservation** page, select **Reserve lot**.</span></span>
1. <span data-ttu-id="bb1b5-240">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-240">Close the page.</span></span>
1. <span data-ttu-id="bb1b5-241">En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-241">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="bb1b5-242">Recibirá mensajes informativos que muestra el id. de oleada y el id. de envío que se crearon.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-242">You receive informational messages that show the wave and shipment IDs that were created.</span></span> <span data-ttu-id="bb1b5-243">También se crea una oleada de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-243">A replenishment wave is also created.</span></span>

    <span data-ttu-id="bb1b5-244">También recibe un mensaje de advertencia que dice: "El Id. de trabajo XXXX no se puede desbloquear porque tiene un trabajo de reabastecimiento sin terminar".</span><span class="sxs-lookup"><span data-stu-id="bb1b5-244">You also receive a warning message that states, "Work ID XXXX cannot be unblocked because it has unfinished replenishment work."</span></span>

#### <a name="view-work-details"></a><span data-ttu-id="bb1b5-245">Ver los detalles de trabajo</span><span class="sxs-lookup"><span data-stu-id="bb1b5-245">View work details</span></span>

1. <span data-ttu-id="bb1b5-246">Vaya a **Gestión de almacenes \> Trabajo \> Detalles de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-246">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="bb1b5-247">En la sección **Visión general**, filtre la columna **Almacén** para el almacén *61*.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-247">In the **Overview** section, filter the **Warehouse** column for warehouse *61*.</span></span>
1. <span data-ttu-id="bb1b5-248">Debería ver que se crearon siete identificadores de trabajo para los tres pedidos de venta de demanda.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-248">You should see that seven work IDs were created for the three demand sales orders.</span></span>

    - <span data-ttu-id="bb1b5-249">Tres de los siete identificadores tiene un valor **Tipo de orden de trabajo** de *Reabastecimiento* y cuatro tienen un valor **Tipo de orden de trabajo** de *Pedidos de venta*.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-249">Three of the seven work IDs have a **Work order type** value of *Replenishment*, and four have a **Work order type** value of *Sales orders*.</span></span>
    - <span data-ttu-id="bb1b5-250">Los tres identificadores de trabajo que tienen un valor **Tipo de orden de trabajo** de *Reabastecimiento* tienen las mismas ubicaciones de *Picking* y *Colocación* en la sección **Líneas**:</span><span class="sxs-lookup"><span data-stu-id="bb1b5-250">All three work IDs that have a **Work order type** value of *Replenishment* have the same *Pick* and *Put* locations in the **Lines** section:</span></span>

        - <span data-ttu-id="bb1b5-251">**Picking**: *02A01R5S1B*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-251">**Pick:** *02A01R5S1B*</span></span>
        - <span data-ttu-id="bb1b5-252">**Colocación**: *06A01R2S1B*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-252">**Put:** *06A01R2S1B*</span></span>

    - <span data-ttu-id="bb1b5-253">Se crearon dos identificadores de trabajo para el pedido de cliente 1.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-253">Two work IDs were created for sales order 1.</span></span>

1. <span data-ttu-id="bb1b5-254">Anote los identificadores de trabajo para los pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-254">Make a note of the work IDs for the sales orders.</span></span>

<span data-ttu-id="bb1b5-255">Dependiendo de las cantidades disponibles, las cantidades de trabajo que se crean pueden variar ligeramente.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-255">Depending on your on-hand quantities, the work quantities that are created might vary slightly.</span></span> <span data-ttu-id="bb1b5-256">Sin embargo, en general, los encabezados de trabajo que se crean deben coincidir con este ejemplo de escenario.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-256">However, overall, the work headers that are created should match this scenario example.</span></span>

#### <a name="on-hand-inventory-license-plate-id"></a><span data-ttu-id="bb1b5-257">Identificador de matrícula de inventario disponible</span><span class="sxs-lookup"><span data-stu-id="bb1b5-257">On-hand inventory license plate ID</span></span>

<span data-ttu-id="bb1b5-258">Más adelante en este escenario, usará la aplicación de almacén (o un emulador), donde debe identificar la placa de licencia para completar los escenarios de recolección y reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-258">Later in this scenario, you will use the warehouse app (or an emulator), where you must identify the license plate to complete the picking and replenishment scenarios.</span></span>

<span data-ttu-id="bb1b5-259">Para encontrar los identificadores de matrícula de licencia que necesitará más adelante, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-259">To find the license plate IDs that you will need later, follow these steps.</span></span>

1. <span data-ttu-id="bb1b5-260">Vaya a **Gestión de inventario \> Consultas e informes \> Inventario disponible**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-260">Go to **Inventory management \> Inquiries and reports \> On-hand list**.</span></span>
1. <span data-ttu-id="bb1b5-261">Seleccione le botón **Mostrar filtros** para abrir el panel de filtro.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-261">Select the **Show filters** button to open the filter pane.</span></span>
1. <span data-ttu-id="bb1b5-262">Especifique los siguientes criterios de filtrado para obtener las placas para el escenario.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-262">Enter the following filtering criteria to get the license plates for the scenario.</span></span> <span data-ttu-id="bb1b5-263">Utilice el filtro *empieza con*.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-263">Use the *begins with* filter.</span></span>

    - <span data-ttu-id="bb1b5-264">**Código de artículo:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-264">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="bb1b5-265">**Almacén**: *61*</span><span class="sxs-lookup"><span data-stu-id="bb1b5-265">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="bb1b5-266">Seleccionar **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-266">Select **Apply**.</span></span>
1. <span data-ttu-id="bb1b5-267">En el panel Acciones, seleccione **Dimensiones**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-267">On the Action Pane, select **Dimensions**.</span></span>
1. <span data-ttu-id="bb1b5-268">En el cuadro de diálogo **Visualización de dimensiones**, en la sección **Dimensiones de almacenamiento**, seleccione todos los valores.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-268">In the **Dimensions display** dialog box, in the **Storage Dimensions** section, select all the values.</span></span>
1. <span data-ttu-id="bb1b5-269">En la sección **Transacciones**, seleccione **Número de artículo** y **Cantidad \<\> 0**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-269">In the **Transactions** section, select **Item number** and **Quantity \<\> 0**.</span></span>
1. <span data-ttu-id="bb1b5-270">Cuando haya terminado, seleccione **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-270">When you've finished, select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="bb1b5-271">La cuadrícula **Disponible** muestra los números de matrícula de entidad de almacén para el artículo *T0100* en cada ubicación.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-271">The **On-hand** grid shows the license plate numbers for item *T0100* in each location.</span></span> <span data-ttu-id="bb1b5-272">Tome nota de la matricula de entidad que se encuentra en cada ubicación, ya que necesitará esta información más adelante.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-272">Make a note of the license plate that is in each location, because you will need this information later.</span></span>
1. <span data-ttu-id="bb1b5-273">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-273">Close the page.</span></span>

### <a name="process-steps"></a><span data-ttu-id="bb1b5-274">Pasos del proceso</span><span class="sxs-lookup"><span data-stu-id="bb1b5-274">Process steps</span></span>

<span data-ttu-id="bb1b5-275">Realizará el reabastecimiento de la ubicación del almacén para los dos primeros identificadores de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-275">You will perform the warehouse location replenishment for the first two work IDs.</span></span> <span data-ttu-id="bb1b5-276">El trabajo en el tercer trabajo de reabastecimiento se bloqueará hasta que el nivel de inventario en la ubicación de picking caiga por debajo del umbral.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-276">Work on the third replenishment work will be blocked until the inventory level in the picking location falls below the threshold.</span></span>

#### <a name="replenishment"></a><span data-ttu-id="bb1b5-277">Reabastecimiento</span><span class="sxs-lookup"><span data-stu-id="bb1b5-277">Replenishment</span></span>

1. <span data-ttu-id="bb1b5-278">Inicie sesión en la aplicación de almacén como un usuario en el almacén *61*.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-278">Sign in to the warehouse app as a user in warehouse *61*.</span></span> <span data-ttu-id="bb1b5-279">(Escriba *61* como el identificador de usuario y *1* como la contraseña).</span><span class="sxs-lookup"><span data-stu-id="bb1b5-279">(Enter *61* as the user ID and *1* as the password.)</span></span>
1. <span data-ttu-id="bb1b5-280">Vaya a **Inventario \> Reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-280">Go to **Inventory \> Replenishment**.</span></span>

    <span data-ttu-id="bb1b5-281">Se le solicitará que complete el primer trabajo de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-281">You're prompted to complete the first replenishment work.</span></span> <span data-ttu-id="bb1b5-282">Se muestran el número de artículo, la cantidad y la ubicación de selección.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-282">The item number, quantity, and location to pick from are shown.</span></span>

1. <span data-ttu-id="bb1b5-283">En el campo **LP**, especifique el número de matrícula de entidad de almacén para la ubicación que se muestra.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-283">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="bb1b5-284">Seleccione el botón **Aceptar** (símbolo de marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="bb1b5-284">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="bb1b5-285">El sistema genera un número de matrícula de entidad de almacén para la matrícula de entidad de almacén para el artículo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-285">The system generates a target license plate number for the new license plate for the picked item.</span></span>

1. <span data-ttu-id="bb1b5-286">Seleccione **Aceptar** para confirmar el valor.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-286">Select **OK** to confirm the value.</span></span>

    <span data-ttu-id="bb1b5-287">Se muestra el trabajo Colocar que indica al usuario que coloque la matrícula de entidad de almacén de destino en la ubicación de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-287">Put work is shown that instructs the user to put the target license plate into the replenishment location.</span></span> <span data-ttu-id="bb1b5-288">La ubicación *Colocar* debe ser **06A01R2S1B**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-288">The *Put* location should be **06A01R2S1B**.</span></span>

1. <span data-ttu-id="bb1b5-289">Confirme los detalles de la colocación y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-289">Confirm the put details, and select **OK**.</span></span>

    <span data-ttu-id="bb1b5-290">Recibirá un mensaje de "Trabajo completado" y se mostrarán los detalles de la próxima tarea de selección de reabastecimiento: el número de artículo, la cantidad y la ubicación para elegir.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-290">You receive a "Work Completed" message, and the details of the next replenishment pick task are shown: the item number, quantity, and location to pick from.</span></span> <span data-ttu-id="bb1b5-291">La ubicación de picking será la misma que la primera ubicación de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-291">The picking location will be the same as the first replenishment location.</span></span> <span data-ttu-id="bb1b5-292">Por lo tanto, la matrícula de entidad de almacén tendrá el mismo identificador que se utilizó para la primera tarea de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-292">Therefore, the license plate will have the same license plate ID that was used for the first replenishment work task.</span></span>

1. <span data-ttu-id="bb1b5-293">Repita los pasos anteriores para completar el trabajo de reabastecimiento para la segunda tarea de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-293">Repeat the preceding steps to complete the replenishment work for the second work task.</span></span> <span data-ttu-id="bb1b5-294">La cantidad y la matrícula de entidad de almacén de destino serán diferentes de la cantidad y la matrícula de entidad de almacén de destino para la primera tarea de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-294">The quantity and target license plate will differ from the quantity and target license plate for the first work task.</span></span>

<span data-ttu-id="bb1b5-295">Después de completar el segundo trabajo de reabastecimiento, recibirá un mensaje de "Trabajo completado".</span><span class="sxs-lookup"><span data-stu-id="bb1b5-295">After the second replenishment work is completed, you receive a "Work Completed" message.</span></span> <span data-ttu-id="bb1b5-296">El dispositivo móvil también le informa de que no hay trabajo disponible, a pesar de que queda algo de trabajo de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-296">The mobile device also informs you that there is no work available, even though some replenishment work remains.</span></span> <span data-ttu-id="bb1b5-297">Este comportamiento se produce porque el trabajo de reabastecimiento tiene un estado de disponibilidad de *Retenido* y por lo tanto está marcado como **Bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-297">This behavior occurs because the replenishment work has an availability status of *Held* and is therefore marked as **Blocked**.</span></span>

<span data-ttu-id="bb1b5-298">El estado *Retenido* se desencadenó porque el perfil de ubicación para la ubicación de picking a la que se asigna el trabajo tiene un valor de **Cantidad de desbordamiento** de *0,65 PL*.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-298">The *Held* status was triggered because the location profile for the picking location that the work is being assigned to has an **Overflow quantity** value of *0.65 PL*.</span></span> <span data-ttu-id="bb1b5-299">Las dos tareas de trabajo de reabastecimiento anteriores llenaron la ubicación casi hasta su límite de desbordamiento para el artículo *T0100*.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-299">The two previous replenishment work tasks filled the location almost to its overflow limit for item *T0100*.</span></span> <span data-ttu-id="bb1b5-300">(La conversión de unidades para el artículo es *1 PL = 100 ea*). Por lo tanto, el trabajo de reabastecimiento restante provocaría que la ubicación exceda su límite de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-300">(The unit conversion for the item is *1 PL = 100 ea*.) Therefore, the remaining replenishment work would cause the location to exceed its overflow limit.</span></span>

<span data-ttu-id="bb1b5-301">Hasta que se seleccione suficiente inventario en la ubicación para colocarlo por debajo del umbral de liberación de trabajo en el elemento del menú del dispositivo móvil, este trabajo de reabastecimiento permanecerá bloqueado.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-301">Until enough inventory is picked from the location to bring it below the work release threshold on the mobile device menu item, this replenishment work will remain blocked.</span></span>

#### <a name="sales-order-pick"></a><span data-ttu-id="bb1b5-302">Picking de pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="bb1b5-302">Sales order pick</span></span>

<span data-ttu-id="bb1b5-303">Antes de que se pueda completar la tarea de reabastecimiento restante, la ubicación de picking debe agotarse del inventario a un nivel donde el trabajo de reabastecimiento restante se pueda desbloquear.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-303">Before the remaining replenishment work task can be completed, the picking location must be depleted of inventory to a level where the remaining replenishment work can be unblocked.</span></span> <span data-ttu-id="bb1b5-304">Es decir, la suma de la cantidad de inventario disponible en la ubicación y la cantidad de reabastecimiento no puede exceder el valor **Cantidad de desbordamiento**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-304">In other words, the sum of the quantity of on-hand inventory in the location and the replenishment quantity can't exceed the **Overflow quantity** value.</span></span> <span data-ttu-id="bb1b5-305">Cuando esta suma es menor que la cantidad de desbordamiento, el trabajo de reabastecimiento restante se desbloqueará.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-305">When this sum is less than the overflow quantity, the remaining replenishment work will be unblocked.</span></span>

1. <span data-ttu-id="bb1b5-306">Inicie sesión en la aplicación de almacén como un usuario en el almacén *61*.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-306">Sign in to the warehouse app as a user in warehouse *61*.</span></span> <span data-ttu-id="bb1b5-307">(Escriba *61* como el identificador de usuario y *1* como la contraseña).</span><span class="sxs-lookup"><span data-stu-id="bb1b5-307">(Enter *61* as the user ID and *1* as the password.)</span></span>
1. <span data-ttu-id="bb1b5-308">Vaya a **Salida \> Selección de ventas**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-308">Go to **Outbound \> Sales Picking**.</span></span>
1. <span data-ttu-id="bb1b5-309">Especifique el primer identificador de trabajo para el pedido de cliente 1.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-309">Enter the first work ID for sales order 1.</span></span>

    <span data-ttu-id="bb1b5-310">Consulte los identificadores para los pedidos de ventas que anotó anteriormente, en la página **Detalles del trabajo**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-310">Refer to the work IDs for sales orders that you made a note of earlier, on the **Work details** page.</span></span> <span data-ttu-id="bb1b5-311">El identificador de trabajo que estableció aquí generará trabajo de selección para una cantidad de 10 ea desde dos ubicaciones separadas.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-311">The work ID that you enter here will generate pick work for a quantity of 10 ea from two separate locations.</span></span>

1. <span data-ttu-id="bb1b5-312">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-312">Select **OK**.</span></span>

    <span data-ttu-id="bb1b5-313">La página **Pedidos de venta: Pick** muestra el número de artículo, la cantidad y la ubicación donde seleccionar para la primera ubicación.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-313">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from for the first location.</span></span>

1. <span data-ttu-id="bb1b5-314">En el campo **LP**, especifique el número de matrícula de entidad de almacén para la ubicación que se muestra.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-314">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="bb1b5-315">Seleccione el botón **Aceptar** (símbolo de marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="bb1b5-315">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="bb1b5-316">La página **Pedidos de venta: Pick** muestra el número de artículo, la cantidad y la ubicación donde seleccionar para la siguiente ubicación.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-316">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from for the next location.</span></span>

1. <span data-ttu-id="bb1b5-317">En el campo **LP**, especifique el número de matrícula de entidad de almacén para la ubicación que se muestra.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-317">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="bb1b5-318">Seleccione el botón **Aceptar** (símbolo de marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="bb1b5-318">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="bb1b5-319">La página **Pedidos de venta: Colocar** le indica que guarde ambos trabajos de selección completados en la ubicación de almacenamiento provisional saliente.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-319">The **Sales orders: Put** page instructs you to put away both the completed picking works to the outbound staging location.</span></span>

1. <span data-ttu-id="bb1b5-320">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-320">Select **OK**.</span></span>

    <span data-ttu-id="bb1b5-321">Recibe un mensaje "Trabajo completado".</span><span class="sxs-lookup"><span data-stu-id="bb1b5-321">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="bb1b5-322">Especifique el segundo identificador de trabajo para el pedido de cliente 1.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-322">Enter the second work ID for sales order 1.</span></span>

    <span data-ttu-id="bb1b5-323">Solo hay una tarea de selección para este identificador de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-323">There is only one pick task for this work ID.</span></span>

1. <span data-ttu-id="bb1b5-324">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-324">Select **OK**.</span></span>

    <span data-ttu-id="bb1b5-325">La página **Pedidos de venta: Pick** muestra el número de artículo, la cantidad y la ubicación donde seleccionar.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-325">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from.</span></span>

1. <span data-ttu-id="bb1b5-326">En el campo **LP**, especifique el número de matrícula de entidad de almacén para la ubicación que se muestra.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-326">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>

    <span data-ttu-id="bb1b5-327">La matrícula de entidad de almacén que especifique será una de las matrículas de entidad de almacén generadas por el sistema de las tareas de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-327">The license plate that you specify will be one of the system-generated license plates from the replenishment work tasks.</span></span> <span data-ttu-id="bb1b5-328">Para asegurarse de capturar el identificador correcto de la matrícula de entidad de almacén, verifique el inventario en la página **Lista disponible** para el artículo, la ubicación y la cantidad.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-328">To make sure that you capture the correct license plate ID, check the inventory on the **On-hand list** page for the item, location, and quantity.</span></span>

1. <span data-ttu-id="bb1b5-329">Seleccione el botón **Aceptar** (símbolo de marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="bb1b5-329">Select the **OK** button (check mark symbol).</span></span>
1. <span data-ttu-id="bb1b5-330">Confirme las instrucciones para la tarea de colocación en la ubicación de almacenamiento provisional saliente.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-330">Confirm the instructions for the put task to the outbound staging location.</span></span>
1. <span data-ttu-id="bb1b5-331">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-331">Select **OK**.</span></span>

    <span data-ttu-id="bb1b5-332">Recibe un mensaje "Trabajo completado".</span><span class="sxs-lookup"><span data-stu-id="bb1b5-332">You receive a "Work Completed" message.</span></span>

<span data-ttu-id="bb1b5-333">Se ha bloqueado la selección del pedido de ventas 2 porque la tarea de reabastecimiento a la que está vinculada no está completa.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-333">Sales order 2 is blocked from picking because the replenishment task that it's linked to isn't completed.</span></span> <span data-ttu-id="bb1b5-334">Actualmente, todavía hay una cantidad de 30 ea en la ubicación de picking, y la cantidad de reabastecimiento para el pedido de cliente 2 es 60 ea.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-334">Currently, there is still a quantity of 30 ea in the picking location, and the replenishment quantity for sales order 2 is 60 ea.</span></span> <span data-ttu-id="bb1b5-335">La suma del inventario disponible y el inventario de reposición (90 ea) excede la cantidad de desbordamiento de 0,65 PL (o 65 ea).</span><span class="sxs-lookup"><span data-stu-id="bb1b5-335">The sum of the on-hand inventory and the replenishment inventory (90 ea) exceeds the overflow quantity of 0.65 PL (or 65 ea).</span></span> <span data-ttu-id="bb1b5-336">Antes de que se pueda completar el trabajo de reposición, se debe seleccionar el pedido de ventas 3.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-336">Before the replenishment work can be completed, sales order 3 must be picked.</span></span>

1. <span data-ttu-id="bb1b5-337">Especifique el identificador de trabajo para el pedido de ventas 3.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-337">Enter the work ID for sales order 3.</span></span>

    <span data-ttu-id="bb1b5-338">Solo hay una tarea de selección para este identificador de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-338">There is only one pick task for this work ID.</span></span>

1. <span data-ttu-id="bb1b5-339">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-339">Select **OK**.</span></span>

    <span data-ttu-id="bb1b5-340">La página **Pedidos de venta: Pick** muestra el número de artículo, la cantidad y la ubicación donde seleccionar.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-340">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from.</span></span>

1. <span data-ttu-id="bb1b5-341">En el campo **LP**, especifique el número de matrícula de entidad de almacén para la ubicación que se muestra.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-341">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>

    <span data-ttu-id="bb1b5-342">La matrícula de entidad de almacén que especifique será una de las matrículas de entidad de almacén generadas por el sistema de las tareas de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-342">The license plate that you specify will be one of the system-generated license plates from the replenishment work tasks.</span></span> <span data-ttu-id="bb1b5-343">Para asegurarse de capturar el identificador correcto de la matrícula de entidad de almacén, verifique el inventario en la página **Lista disponible** para el artículo, la ubicación y la cantidad.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-343">To make sure that you capture the correct license plate ID, check the inventory on the **On-hand list** page for the item, location, and quantity.</span></span>

1. <span data-ttu-id="bb1b5-344">Seleccione el botón **Aceptar** (símbolo de marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="bb1b5-344">Select the **OK** button (check mark symbol).</span></span>
1. <span data-ttu-id="bb1b5-345">Confirme las instrucciones para la tarea de colocación en la ubicación de almacenamiento provisional saliente.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-345">Confirm the instructions for the put task to the outbound staging location.</span></span>
1. <span data-ttu-id="bb1b5-346">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-346">Select **OK**.</span></span>

    <span data-ttu-id="bb1b5-347">Recibe un mensaje "Trabajo completado".</span><span class="sxs-lookup"><span data-stu-id="bb1b5-347">You receive a "Work Completed" message.</span></span>

<span data-ttu-id="bb1b5-348">Tan pronto como la suma de la cantidad disponible en la ubicación de picking y la cantidad de reabastecimiento esté por debajo del umbral, podrá procesar el trabajo de reabastecimiento restante.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-348">As soon as the sum of the on-hand quantity in the picking location and the replenishment quantity is below the threshold, you will be able to process the remaining replenishment work.</span></span>

<span data-ttu-id="bb1b5-349">Vuelva a la página **Detalles del trabajo** y observe que la disponibilidad del trabajo de reabastecimiento para la pieza final de reabastecimiento (para el pedido de cliente 2) es *Abierto*, porque ahora hay suficiente espacio en la ubicación para aceptar el reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-349">Return to the **Work details** page, and notice that the replenishment work availability for the final piece of replenishment (for sales order 2) is *Open*, because there is now enough space in the location to accept the replenishment.</span></span>

<span data-ttu-id="bb1b5-350">Ahora puede procesar este trabajo de reabastecimiento a través del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-350">You can now process this replenishment work via the mobile device.</span></span>

1. <span data-ttu-id="bb1b5-351">Vaya a **Inventario \> Reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-351">Go to **Inventory \> Replenishment**.</span></span>

    <span data-ttu-id="bb1b5-352">Se le solicitará que complete el trabajo de reabastecimiento restante.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-352">You're prompted to complete the remaining replenishment work.</span></span> <span data-ttu-id="bb1b5-353">Se muestran el número de artículo, la cantidad y la ubicación de selección.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-353">The item number, quantity, and location to pick from are shown.</span></span>

1. <span data-ttu-id="bb1b5-354">En el campo **LP**, especifique el número de matrícula de entidad de almacén para la ubicación que se muestra.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-354">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="bb1b5-355">Seleccione el botón **Aceptar** (símbolo de marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="bb1b5-355">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="bb1b5-356">El sistema genera un número de matrícula de entidad de almacén para la matrícula de entidad de almacén para el artículo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-356">The system generates a target license plate number for the new license plate for the picked item.</span></span>

1. <span data-ttu-id="bb1b5-357">Seleccione **Aceptar** para confirmar el valor.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-357">Select **OK** to confirm the value.</span></span>

    <span data-ttu-id="bb1b5-358">Se muestra el trabajo Colocar que indica al usuario que coloque la matrícula de entidad de almacén de destino en la ubicación de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-358">Put work is shown that instructs the user to put the target license plate into the replenishment location.</span></span> <span data-ttu-id="bb1b5-359">La ubicación *Colocar* debe ser **06A01R2S1B**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-359">The *Put* location should be **06A01R2S1B**.</span></span>

1. <span data-ttu-id="bb1b5-360">Confirme los detalles de la colocación y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-360">Confirm the put details, and select **OK**.</span></span>

    <span data-ttu-id="bb1b5-361">Recibirá los mensajes "Trabajo completado" y "No hay trabajo disponible".</span><span class="sxs-lookup"><span data-stu-id="bb1b5-361">You receive "Work Completed" and "No Work Available" messages.</span></span>

<span data-ttu-id="bb1b5-362">Ahora puede seleccionar el pedido de ventas 2.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-362">You can now pick sales order 2.</span></span> <span data-ttu-id="bb1b5-363">Se desbloqueó cuando se completó el trabajo de reabastecimiento vinculado al pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-363">It became unblocked when the replenishment work that is linked to the sales order was completed.</span></span>

1. <span data-ttu-id="bb1b5-364">Especifique el identificador de trabajo para el pedido de ventas 2.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-364">Enter the work ID for sales order 2.</span></span>

    <span data-ttu-id="bb1b5-365">Solo hay una tarea de selección para este identificador de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-365">There is only one pick task for this work ID.</span></span>

1. <span data-ttu-id="bb1b5-366">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-366">Select **OK**.</span></span>

    <span data-ttu-id="bb1b5-367">La página **Pedidos de venta: Pick** muestra el número de artículo, la cantidad y la ubicación donde seleccionar.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-367">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from.</span></span>

1. <span data-ttu-id="bb1b5-368">En el campo **LP**, especifique el número de matrícula de entidad de almacén para la ubicación que se muestra.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-368">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>

    <span data-ttu-id="bb1b5-369">La matrícula de entidad de almacén que especifique será una de las matrículas de entidad de almacén generadas por el sistema desde la tareas de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-369">The license plate that you specify will be the system-generated license plate from the replenishment work task.</span></span> <span data-ttu-id="bb1b5-370">Para asegurarse de capturar el identificador correcto de la matrícula de entidad de almacén, verifique el inventario en la página **Lista disponible** para el artículo, la ubicación y la cantidad.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-370">To make sure that you capture the correct license plate ID, check the inventory on the **On-hand list** page for the item, location, and quantity.</span></span>

1. <span data-ttu-id="bb1b5-371">Seleccione el botón **Aceptar** (símbolo de marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="bb1b5-371">Select the **OK** button (check mark symbol).</span></span>
1. <span data-ttu-id="bb1b5-372">Confirme las instrucciones para la tarea de colocación en la ubicación de almacenamiento provisional saliente.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-372">Confirm the instructions for the put task to the outbound staging location.</span></span>
1. <span data-ttu-id="bb1b5-373">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-373">Select **OK**.</span></span>

    <span data-ttu-id="bb1b5-374">Recibe un mensaje "Trabajo completado".</span><span class="sxs-lookup"><span data-stu-id="bb1b5-374">You receive a "Work Completed" message.</span></span>

## <a name="notes-and-tips"></a><span data-ttu-id="bb1b5-375">Notas y consejos</span><span class="sxs-lookup"><span data-stu-id="bb1b5-375">Notes and tips</span></span>

- <span data-ttu-id="bb1b5-376">Esta funcionalidad funciona con todo tipo de reabastecimiento: demanda de oleadas, mínimo/máximo, demanda de carga y slotting.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-376">This functionality works with all types of replenishment: wave demand, min/max, load demand, and slotting.</span></span>
- <span data-ttu-id="bb1b5-377">Puede anular manualmente la disponibilidad de trabajo de reabastecimiento para cada encabezado de trabajo desde la página **Detalles del trabajo** si quiere.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-377">You can manually override the replenishment work availability for each work header from the **Work details** page if you want.</span></span>
- <span data-ttu-id="bb1b5-378">Cuando el sistema establece la disponibilidad de trabajo de reabastecimiento, considera cualquier inventario que ya esté en la ubicación antes de que se complete cualquier trabajo.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-378">When the system sets the replenishment work availability, it considers any inventory that is already in the location before any work is completed</span></span>
- <span data-ttu-id="bb1b5-379">Cada pieza de trabajo de pedido de ventas está vinculada a un trabajo de reabastecimiento específico.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-379">Each piece of sales order work is linked to a specific replenishment work.</span></span> <span data-ttu-id="bb1b5-380">No hay funcionalidad de disponibilidad de trabajo de ventas correspondiente.</span><span class="sxs-lookup"><span data-stu-id="bb1b5-380">There is no corresponding sales work availability functionality.</span></span>
