---
title: Reabastecimiento de umbral de zona
description: El reabastecimiento basado en zonas utiliza una estrategia de reabastecimiento mínimo/máximo (mín./máx.), pero evalúa zonas de almacén completas en lugar de solo ubicaciones individuales. Por lo tanto, los directores de almacén pueden aprender más rápido cuándo se requiere un inventario adicional en una zona de picking.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocDirHint, WHSLocDirTable, WHSRequestType
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 6aaa139fb206c035b25b7056e681d086fde6447f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5245067"
---
# <a name="zone-threshold-replenishment"></a><span data-ttu-id="f35d8-104">Reabastecimiento de umbral de zona</span><span class="sxs-lookup"><span data-stu-id="f35d8-104">Zone threshold replenishment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f35d8-105">El reabastecimiento basado en zonas utiliza una estrategia de [reabastecimiento](replenishment.md) mínimo/máximo (mín./máx.), pero evalúa zonas de almacén completas en lugar de solo ubicaciones individuales.</span><span class="sxs-lookup"><span data-stu-id="f35d8-105">Zone-based replenishment uses a minimum/maximum (min/max) [replenishment](replenishment.md) strategy, but it evaluates whole warehouse zones instead of just individual locations.</span></span> <span data-ttu-id="f35d8-106">Por lo tanto, los directores de almacén pueden aprender más rápido cuándo se requiere un inventario adicional en una zona de picking.</span><span class="sxs-lookup"><span data-stu-id="f35d8-106">Therefore, warehouse managers can more quickly learn when additional inventory is required in a picking zone.</span></span>

<span data-ttu-id="f35d8-107">La configuración de esta característica se asemeja a la configuración del reabastecimiento basado en ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="f35d8-107">The setup for this feature resembles the setup for location-based replenishment.</span></span> <span data-ttu-id="f35d8-108">Sin embargo, cuando configura una plantilla para un reabastecimiento mínimo/máximo, también puede especificar si el umbral debe evaluarse por ubicación o por zona.</span><span class="sxs-lookup"><span data-stu-id="f35d8-108">However, when you set up a template for min/max replenishment, you can also specify whether the threshold should be evaluated per location or per zone.</span></span> <span data-ttu-id="f35d8-109">Si configura una evaluación basada en zonas, debe agregar zonas específicas a la consulta de selección de zona.</span><span class="sxs-lookup"><span data-stu-id="f35d8-109">If you set up evaluation that is based on zones, you must add specific zones to the zone selection query.</span></span>

<span data-ttu-id="f35d8-110">Al igual que el reabastecimiento mínimo/máximo basado en ubicaciones, el reabastecimiento mínimo/máximo basada en zonas se basa en la configuración de un umbral de inventario mínimo que desencadena la creación de un trabajo de reabastecimiento para los artículos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="f35d8-110">Like location-based min/max replenishment, zone-based min/max replenishment is based the setup of a minimum inventory threshold that triggers the creation of replenishment work for selected items.</span></span> <span data-ttu-id="f35d8-111">Este trabajo de reabastecimiento aumentará el inventario hasta el umbral máximo especificado para la zona.</span><span class="sxs-lookup"><span data-stu-id="f35d8-111">This replenishment work will increase inventory up to the specified maximum threshold for the zone.</span></span>

> [!NOTE]
> <span data-ttu-id="f35d8-112">Los procesos de reabastecimiento de zona para variantes de producto no son compatibles con la versión actual.</span><span class="sxs-lookup"><span data-stu-id="f35d8-112">Zone replenishment processes for product variants aren't supported in the current release.</span></span>


<span data-ttu-id="f35d8-113">A diferencia del reabastecimiento mínimo/máximo basado en ubicaciones, el reabastecimiento mínimo/máximo basado en zonas no requiere ubicaciones fijas para evaluar si las ubicaciones deben almacenar un determinado artículo.</span><span class="sxs-lookup"><span data-stu-id="f35d8-113">Unlike location-based min/max replenishment, zone-based min/max replenishment doesn't require fixed locations to evaluate whether locations should store a specific item.</span></span> <span data-ttu-id="f35d8-114">Por lo tanto, el reabastecimiento basado en zonas le permite utilizar el reabastecimiento mínimo/máximo incluso si no tiene ubicaciones fijas para cada artículo o variante de artículo en el almacén.</span><span class="sxs-lookup"><span data-stu-id="f35d8-114">Therefore, zone-based replenishment lets you use min/max replenishment even if you don't have fixed locations for each item or item variant in the warehouse.</span></span> <span data-ttu-id="f35d8-115">Cuando una cantidad en la zona cae por debajo del umbral mínimo especificado, se crea un trabajo de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="f35d8-115">When a quantity in the zone falls below the specified minimum threshold, replenishment work is created.</span></span> <span data-ttu-id="f35d8-116">Las directivas de ubicación determinarán en qué ubicación concreta se debe colocar el inventario.</span><span class="sxs-lookup"><span data-stu-id="f35d8-116">Location directives will determine which specific location the inventory should be put into.</span></span>

## <a name="turn-on-the-zone-threshold-replenishment-feature"></a><span data-ttu-id="f35d8-117">Activar la característica de reabastecimiento de umbral de zona</span><span class="sxs-lookup"><span data-stu-id="f35d8-117">Turn on the Zone threshold replenishment feature</span></span>

<span data-ttu-id="f35d8-118">Antes de poder usar la característica *Reabastecimiento de umbral de zona*, esta debe estar activada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="f35d8-118">Before you can use the *Zone threshold replenishment* feature, it must be turned on in your system.</span></span> <span data-ttu-id="f35d8-119">Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="f35d8-119">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="f35d8-120">En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="f35d8-120">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="f35d8-121">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="f35d8-121">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="f35d8-122">**Nombre de característica:** *Reabastecimiento de umbral de zona*</span><span class="sxs-lookup"><span data-stu-id="f35d8-122">**Feature name:** *Zone threshold replenishment*</span></span>

## <a name="set-up-zone-based-replenishment"></a><a name="setup"></a><span data-ttu-id="f35d8-123">Configurar reabastecimiento basado en zonas</span><span class="sxs-lookup"><span data-stu-id="f35d8-123">Set up zone-based replenishment</span></span>

<span data-ttu-id="f35d8-124">Para configurar un reabastecimiento basada en zonas, debe configurar varias partes del sistema.</span><span class="sxs-lookup"><span data-stu-id="f35d8-124">To set up zone-based replenishment, you must configure several parts of the system.</span></span> <span data-ttu-id="f35d8-125">Esta sección presenta las diversas configuraciones y proporciona valores de datos de demostración que puede introducir si desea trabajar en el escenario al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="f35d8-125">This section introduces the various settings and provides demo data values that you can enter if you want to work through the scenario at the end of this topic.</span></span>

### <a name="set-up-directive-codes"></a><span data-ttu-id="f35d8-126">Configurar códigos de directivas</span><span class="sxs-lookup"><span data-stu-id="f35d8-126">Set up directive codes</span></span>

<span data-ttu-id="f35d8-127">Los [códigos de directivas](control-warehouse-location-directives.md) le permiten ser más específico cuando define la plantilla de ubicación que se utiliza en una plantilla de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f35d8-127">[Directive codes](control-warehouse-location-directives.md) let you be more specific when you define the location template that is used in a work template.</span></span> <span data-ttu-id="f35d8-128">Cada código establece un valor común al que puede hacer referencia cuando configura cada tipo de plantilla.</span><span class="sxs-lookup"><span data-stu-id="f35d8-128">Each code establishes a common value that you can refer to when you configure each type of template.</span></span>

#### <a name="view-and-edit-directive-codes"></a><span data-ttu-id="f35d8-129">Ver y editar códigos de directivas</span><span class="sxs-lookup"><span data-stu-id="f35d8-129">View and edit directive codes</span></span>

<span data-ttu-id="f35d8-130">Para ver o editar sus códigos de directivas, vaya a **Gestión de almacenes \> Configuración \> Códigos de directivas**.</span><span class="sxs-lookup"><span data-stu-id="f35d8-130">To view or edit your directive codes, go to **Warehouse management \> Setup \> Directive codes**.</span></span>

#### <a name="prepare-demo-data-directive-codes"></a><span data-ttu-id="f35d8-131">Preparar códigos de directivas de datos de demostración</span><span class="sxs-lookup"><span data-stu-id="f35d8-131">Prepare demo data directive codes</span></span>

<span data-ttu-id="f35d8-132">En este ejemplo se muestra cómo preparar un código de directivas.</span><span class="sxs-lookup"><span data-stu-id="f35d8-132">This example shows how to prepare a directive code.</span></span> <span data-ttu-id="f35d8-133">Si tiene previsto trabajar en el escenario al final de este tema, utilice los valores de datos de demostración que se proporcionan aquí.</span><span class="sxs-lookup"><span data-stu-id="f35d8-133">If you're planning to work through the scenario at the end of this topic, use the demo data values that are provided here.</span></span> <span data-ttu-id="f35d8-134">De lo contrario, utilice sus propios valores.</span><span class="sxs-lookup"><span data-stu-id="f35d8-134">Otherwise, use your own values.</span></span>

1. <span data-ttu-id="f35d8-135">Seleccione la entidad jurídica **USMF** para trabajar con los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="f35d8-135">Select the **USMF** legal entity to work with the demo data.</span></span>
1. <span data-ttu-id="f35d8-136">Vaya a **Gestión de almacenes \> Configurar \> Códigos de directivas**.</span><span class="sxs-lookup"><span data-stu-id="f35d8-136">Go to **Warehouse management \> Setup \> Directive codes**.</span></span>
1. <span data-ttu-id="f35d8-137">En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="f35d8-137">On the Action Pane, select **New** to add a row to the grid.</span></span>
1. <span data-ttu-id="f35d8-138">Establezca los siguientes valores en la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="f35d8-138">In the new row, set the following values:</span></span>

    - <span data-ttu-id="f35d8-139">**Código de directiva:** _Reabastecimiento de zona_</span><span class="sxs-lookup"><span data-stu-id="f35d8-139">**Directive code:** _Zone replen_</span></span>
    - <span data-ttu-id="f35d8-140">**Descripción de la directiva:** _Reabastecimiento de zona_</span><span class="sxs-lookup"><span data-stu-id="f35d8-140">**Directive description:** _Zone replenishment_</span></span>

1. <span data-ttu-id="f35d8-141">Seleccione **Guardar** para guardar el nuevo código.</span><span class="sxs-lookup"><span data-stu-id="f35d8-141">Select **Save** to save the new code.</span></span>

### <a name="set-up-replenishment-templates"></a><span data-ttu-id="f35d8-142">Configurar plantillas de reabastecimiento</span><span class="sxs-lookup"><span data-stu-id="f35d8-142">Set up replenishment templates</span></span>

<span data-ttu-id="f35d8-143">Las [plantillas de reabastecimiento mínimo/máximo](tasks/set-up-min-max-replenishment-process.md) son el mecanismo principal para mantener niveles óptimos en ubicaciones de picking.</span><span class="sxs-lookup"><span data-stu-id="f35d8-143">[Min/max replenishment templates](tasks/set-up-min-max-replenishment-process.md) are the primary mechanism for maintaining optimal levels in picking locations.</span></span> <span data-ttu-id="f35d8-144">En estas plantillas, debe configurar las reglas que se utilizarán para reabastecer el inventario en el almacén.</span><span class="sxs-lookup"><span data-stu-id="f35d8-144">In these templates, you must set up the rules that will be used to replenish inventory in the warehouse.</span></span> <span data-ttu-id="f35d8-145">El reabastecimiento para la que se pueden usar las plantillas incluye el reabastecimiento basado en zonas.</span><span class="sxs-lookup"><span data-stu-id="f35d8-145">The replenishment that the templates can be used for includes zone-based replenishment.</span></span>

#### <a name="view-and-edit-replenishment-templates"></a><span data-ttu-id="f35d8-146">Ver y editar plantillas de reabastecimiento</span><span class="sxs-lookup"><span data-stu-id="f35d8-146">View and edit replenishment templates</span></span>

<span data-ttu-id="f35d8-147">Una plantilla de reabastecimiento es un conjunto de reglas que controlan cuándo y cómo se reabastece un ubicación.</span><span class="sxs-lookup"><span data-stu-id="f35d8-147">A replenishment template is a set of rules that control when and how a location is replenished.</span></span> <span data-ttu-id="f35d8-148">Seleccione una plantilla para controlar cuándo y cómo se realiza el reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="f35d8-148">You select a template to control when and how replenishment is done.</span></span> <span data-ttu-id="f35d8-149">Para ver o editar sus plantillas de reabastecimiento, vaya a **Gestión de almacén \> Configuración \> Reabastecimiento \> Plantillas de reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="f35d8-149">To view or edit your replenishment templates, go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**.</span></span>

#### <a name="prepare-a-demo-data-replenishment-template"></a><span data-ttu-id="f35d8-150">Preparar una plantilla de reabastecimiento de datos de demostración</span><span class="sxs-lookup"><span data-stu-id="f35d8-150">Prepare a demo data replenishment template</span></span>

<span data-ttu-id="f35d8-151">En este ejemplo se muestra cómo preparar una plantilla de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="f35d8-151">This example shows how to prepare a replenishment template.</span></span> <span data-ttu-id="f35d8-152">Si tiene previsto trabajar en el escenario al final de este tema, utilice los valores de datos de demostración que se proporcionan aquí.</span><span class="sxs-lookup"><span data-stu-id="f35d8-152">If you're planning to work through the scenario at the end of this topic, use the demo data values that are provided here.</span></span> <span data-ttu-id="f35d8-153">De lo contrario, utilice sus propios valores.</span><span class="sxs-lookup"><span data-stu-id="f35d8-153">Otherwise, use your own values.</span></span>

1. <span data-ttu-id="f35d8-154">Seleccione la entidad jurídica **USMF** para trabajar con los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="f35d8-154">Select the **USMF** legal entity to work with the demo data.</span></span>
1. <span data-ttu-id="f35d8-155">Vaya a **Administración de almacenes \> Configurar \> Reabastecimiento \> Plantillas de reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="f35d8-155">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**.</span></span>
1. <span data-ttu-id="f35d8-156">Seleccione **Editar** para poner la página en modo de edición.</span><span class="sxs-lookup"><span data-stu-id="f35d8-156">Select **Edit** to put the page into edit mode.</span></span>
1. <span data-ttu-id="f35d8-157">En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula **Visión general**.</span><span class="sxs-lookup"><span data-stu-id="f35d8-157">On the Action Pane, select **New** to add a row to the **Overview** grid.</span></span>
1. <span data-ttu-id="f35d8-158">Establezca los siguientes valores en la fila nueva.</span><span class="sxs-lookup"><span data-stu-id="f35d8-158">In the new row, set the following values.</span></span> <span data-ttu-id="f35d8-159">Acepte los valores predeterminados para el resto de campos.</span><span class="sxs-lookup"><span data-stu-id="f35d8-159">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="f35d8-160">**Plantilla de reabastecimiento:** _Reabastecimiento mín./máx. de zona_</span><span class="sxs-lookup"><span data-stu-id="f35d8-160">**Replenish template:** _Zone min/max replen_</span></span>
    - <span data-ttu-id="f35d8-161">**Descripción:** _Reabastecimiento mín./máx. de zona_</span><span class="sxs-lookup"><span data-stu-id="f35d8-161">**Description:** _Zone min/max replenishment_</span></span>
    - <span data-ttu-id="f35d8-162">**Tipo de reabastecimiento:** _Mínimo o máximo_</span><span class="sxs-lookup"><span data-stu-id="f35d8-162">**Replenishment type:** _Minimum or maximum_</span></span>

1. <span data-ttu-id="f35d8-163">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f35d8-163">Select **Save**.</span></span>
1. <span data-ttu-id="f35d8-164">Mientras la nueva fila sigue seleccionada en la cuadrícula **Visión general**, seleccione **Nuevo** encima de la cuadrícula **Detalles de la plantilla de reabastecimiento** para agregar una fila asociada a la plantilla de reabastecimiento *Reabastecimiento mín./máx. de zona* que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="f35d8-164">While the new row is still selected in the **Overview** grid, select **New** above the **Replenishment Template Details** grid to add a row that is associated with the *Zone Min/Max replen* replenishment template that you just created.</span></span>
1. <span data-ttu-id="f35d8-165">Establezca los siguientes valores en la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="f35d8-165">In the new row, set the following values:</span></span>

    - <span data-ttu-id="f35d8-166">**Número de secuencia:** Introduzca _1_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-166">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="f35d8-167">**Descripción:** Introduzca _Reabastecimiento de zona de picking_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-167">**Description:** Enter _Pick zone replenishment_.</span></span>
    - <span data-ttu-id="f35d8-168">**Unidad de reabastecimiento:** Seleccione _ea_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-168">**Replenishment unit:** Select _ea_.</span></span>
    - <span data-ttu-id="f35d8-169">**Tipo de solicitud**: deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="f35d8-169">**Request type:** Leave this field blank.</span></span>
    - <span data-ttu-id="f35d8-170">**Código de directiva**: este campo vincula la plantilla de reabastecimiento con una directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="f35d8-170">**Directive code:** This field links the replenishment template with a location directive.</span></span> <span data-ttu-id="f35d8-171">Seleccione el código de la directiva de datos de demostración que creó anteriormente (_Reabastecimiento de zona_).</span><span class="sxs-lookup"><span data-stu-id="f35d8-171">Select the demo data directive code that you created earlier (_Zone replen_).</span></span>
    - <span data-ttu-id="f35d8-172">**Plantilla de trabajo**: deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="f35d8-172">**Work template:** Leave this field blank.</span></span>
    - <span data-ttu-id="f35d8-173">**Cantidad mínima:** Este campo establece la cantidad a la que se desencadenará el reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="f35d8-173">**Minimum quantity:** This field sets the quantity that replenishment will be triggered at.</span></span> <span data-ttu-id="f35d8-174">Introduzca _50_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-174">Enter _50_.</span></span>
    - <span data-ttu-id="f35d8-175">**Cantidad máxima:** Este campo establece la cantidad máxima de un artículo que puede estar presente en una zona.</span><span class="sxs-lookup"><span data-stu-id="f35d8-175">**Maximum quantity:** This field sets the maximum quantity of an item that can be present in a zone.</span></span> <span data-ttu-id="f35d8-176">El trabajo de reabastecimiento generado aumentará el inventario a esta cantidad.</span><span class="sxs-lookup"><span data-stu-id="f35d8-176">Generated replenishment work will increase inventory to this quantity.</span></span> <span data-ttu-id="f35d8-177">Introduzca _150_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-177">Enter _150_.</span></span>
    - <span data-ttu-id="f35d8-178">**Unidad:** Este campo establece la unidad para los valores mínimo y máximo.</span><span class="sxs-lookup"><span data-stu-id="f35d8-178">**Unit:** This field sets the unit for the minimum and maximum values.</span></span> <span data-ttu-id="f35d8-179">Seleccione _ea_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-179">Select _ea_.</span></span>
    - <span data-ttu-id="f35d8-180">**Incremento de la demanda:** Seleccione _Redondear_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-180">**Demand increment:** Select _Round up_.</span></span>
    - <span data-ttu-id="f35d8-181">**Reabastecer solo ubicaciones fijas vacías:** marque esta casilla.</span><span class="sxs-lookup"><span data-stu-id="f35d8-181">**Replenish empty fixed locations:** Select this check box.</span></span>
    - <span data-ttu-id="f35d8-182">**Reabastecer solo ubicaciones fijas:** desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="f35d8-182">**Replenish only fixed locations:** Clear this check box.</span></span>
    - <span data-ttu-id="f35d8-183">**Modo de consulta del producto:** seleccione _Consulta del producto_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-183">**Product query mode:** Select _Product query_.</span></span>
    - <span data-ttu-id="f35d8-184">**Alcance del umbral de reabastecimiento:** este campo define si la plantilla debe evaluar por zona o por ubicación específica.</span><span class="sxs-lookup"><span data-stu-id="f35d8-184">**Replenishment threshold scope:** This field defines whether the template should evaluate by zone or by specific location.</span></span> <span data-ttu-id="f35d8-185">Seleccione _Zona_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-185">Select _Zone_.</span></span>
    - <span data-ttu-id="f35d8-186">**Almacén:** seleccione _61_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-186">**Warehouse:** Select _61_.</span></span>

1. <span data-ttu-id="f35d8-187">Seleccione **Seleccionar productos** encima de la cuadrícula **Detalles de plantilla de reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="f35d8-187">Select **Select products** above the **Replenishment Template Details** grid.</span></span>
1. <span data-ttu-id="f35d8-188">En el cuadro de diálogo **Consulta de producto**, en la pestaña **Intervalo**, seleccione **Agregar** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="f35d8-188">In the **Product query** dialog box, on the **Range** tab, select **Add** to add a row to the grid.</span></span>
1. <span data-ttu-id="f35d8-189">Establezca los siguientes valores en la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="f35d8-189">In the new row, set the following values:</span></span>

    - <span data-ttu-id="f35d8-190">**Tabla:** _Artículos_</span><span class="sxs-lookup"><span data-stu-id="f35d8-190">**Table:** _Items_</span></span>
    - <span data-ttu-id="f35d8-191">**Tabla derivada:** _Artículos_</span><span class="sxs-lookup"><span data-stu-id="f35d8-191">**Derived table:** _Items_</span></span>
    - <span data-ttu-id="f35d8-192">**Campo:** _Número de artículo_</span><span class="sxs-lookup"><span data-stu-id="f35d8-192">**Field:** _Item number_</span></span>
    - <span data-ttu-id="f35d8-193">**Criterios**: _A0001_</span><span class="sxs-lookup"><span data-stu-id="f35d8-193">**Criteria:** _A0001_</span></span>

1. <span data-ttu-id="f35d8-194">Seleccione **Aceptar** para guardar su consulta y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f35d8-194">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="f35d8-195">Seleccione **Seleccionar zonas para reabastecer** encima de la cuadrícula **Detalles de plantilla de reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="f35d8-195">Select **Select zones to replenish** above the **Replenishment Template Details** grid.</span></span>
1. <span data-ttu-id="f35d8-196">En el cuadro de diálogo **Consulta de zona**, en la pestaña **Intervalo**, agregue una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="f35d8-196">In the **Zone query** dialog box, on the **Range** tab, add a row to the grid.</span></span>
1. <span data-ttu-id="f35d8-197">Establezca los siguientes valores en la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="f35d8-197">In the new row, set the following values:</span></span>

    - <span data-ttu-id="f35d8-198">**Tabla:** _Zona de almacén_</span><span class="sxs-lookup"><span data-stu-id="f35d8-198">**Table:** _Warehouse zone_</span></span>
    - <span data-ttu-id="f35d8-199">**Tabla derivada:** _Zona de almacén_</span><span class="sxs-lookup"><span data-stu-id="f35d8-199">**Derived table:** _Warehouse zone_</span></span>
    - <span data-ttu-id="f35d8-200">**Campo**: _ID de zona_</span><span class="sxs-lookup"><span data-stu-id="f35d8-200">**Field:** _Zone ID_</span></span>
    - <span data-ttu-id="f35d8-201">**Criterios:** _FLOOR_</span><span class="sxs-lookup"><span data-stu-id="f35d8-201">**Criteria:** _FLOOR_</span></span>

1. <span data-ttu-id="f35d8-202">Seleccione **Aceptar** para guardar su consulta y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f35d8-202">Select **OK** to save your query and close the dialog box.</span></span>

### <a name="set-up-location-directives"></a><span data-ttu-id="f35d8-203">Configurar directivas de ubicación</span><span class="sxs-lookup"><span data-stu-id="f35d8-203">Set up location directives</span></span>

<span data-ttu-id="f35d8-204">A diferencia del reabastecimiento mín./máx. basada en ubicaciones, el reabastecimiento mín./máx. basado en zonas requiere que configure las directivas de ubicación de selección y las directivas de ubicación, porque el sistema evalúa toda la zona en lugar de solo la ubicación de selección para el trabajo de salida.</span><span class="sxs-lookup"><span data-stu-id="f35d8-204">Unlike location-based min/max replenishment, zone-based min/max replenishment requires that you set up both pick location directives and put location directives, because the system evaluates the whole zone instead of just the pick location for outbound work.</span></span>

#### <a name="view-and-edit-location-directives"></a><span data-ttu-id="f35d8-205">Ver y editar directivas de ubicación</span><span class="sxs-lookup"><span data-stu-id="f35d8-205">View and edit location directives</span></span>

<span data-ttu-id="f35d8-206">Para ver o editar sus directivas de ubicación, vaya a **Gestión de almacenes \> Configuración \> Directivas de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="f35d8-206">To view or edit your location directives, go to **Warehouse management \> Setup \> Location directives**.</span></span>

<span data-ttu-id="f35d8-207">Para ver ejemplos que muestran cómo usar la configuración para crear las directivas de ubicación de selección y las directivas de ubicación requeridas, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="f35d8-207">For examples that show how to use the settings to create the required pick location directives and put location directives, see the next section.</span></span>

#### <a name="prepare-demo-data-location-directives"></a><span data-ttu-id="f35d8-208">Preparar directivas de ubicación de datos de demostración</span><span class="sxs-lookup"><span data-stu-id="f35d8-208">Prepare demo data location directives</span></span>

<span data-ttu-id="f35d8-209">Para preparar datos de demostración para que puedan usarse en el escenario al final de este tema, debe crear dos directivas de ubicación: una para selección y otra para colocación.</span><span class="sxs-lookup"><span data-stu-id="f35d8-209">To prepare demo data so that it can be used in the scenario at the end of this topic, you must create two location directives: one for pick and one for put.</span></span>

##### <a name="create-a-replenishment-pick-directive"></a><span data-ttu-id="f35d8-210">Crear una directiva de selección de reabastecimiento</span><span class="sxs-lookup"><span data-stu-id="f35d8-210">Create a replenishment pick directive</span></span>

1. <span data-ttu-id="f35d8-211">Seleccione la entidad jurídica **USMF** para trabajar con los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="f35d8-211">Select the **USMF** legal entity to work with the demo data.</span></span>
1. <span data-ttu-id="f35d8-212">Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="f35d8-212">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="f35d8-213">En el panel izquierdo, establezca el campo **Tipo de orden de trabajo** en _Reabastecimiento_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-213">In the left pane, set the **Work order type** field to _Replenishment_.</span></span>
1. <span data-ttu-id="f35d8-214">En el panel de acciones, seleccione **Nuevo** para crear una nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="f35d8-214">On the Action Pane, select **New** to create a new directive.</span></span>
1. <span data-ttu-id="f35d8-215">Establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="f35d8-215">Set the following values:</span></span>

    - <span data-ttu-id="f35d8-216">**Número de secuencia:** acepte el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f35d8-216">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="f35d8-217">**Nombre:** introduzca _Selección de zona_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-217">**Name:** Enter _Zone pick_.</span></span>
    - <span data-ttu-id="f35d8-218">**Tipo de trabajo**: seleccione _Selección_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-218">**Work type:** Select _Pick_.</span></span>
    - <span data-ttu-id="f35d8-219">**Sitio:** seleccione _6_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-219">**Site:** Select _6_.</span></span>
    - <span data-ttu-id="f35d8-220">**Almacén:** seleccione _61_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-220">**Warehouse:** Select _61_.</span></span>
    - <span data-ttu-id="f35d8-221">**Código de directiva:** deje en blanco este campo.</span><span class="sxs-lookup"><span data-stu-id="f35d8-221">**Directive code:** Leave this field blank.</span></span>
    - <span data-ttu-id="f35d8-222">**Varios SKU:** establezca esta opción en _No_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-222">**Multi SKU:** Set this option to _No_.</span></span>

1. <span data-ttu-id="f35d8-223">Seleccione **Guardar** para crear una directiva que tenga la configuración que ha configurado hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="f35d8-223">Select **Save** to create a directive that has the settings that you've configured so far.</span></span>
1. <span data-ttu-id="f35d8-224">En la ficha desplegable **Líneas**, seleccione **Nuevo** para agregar una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="f35d8-224">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="f35d8-225">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="f35d8-225">On the new line, set the following values:</span></span>

    - <span data-ttu-id="f35d8-226">**Número de secuencia:** Introduzca _1_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-226">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="f35d8-227">**Cantidad inicial**: introduzca _0_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-227">**From quantity:** Enter _0_.</span></span>
    - <span data-ttu-id="f35d8-228">**Cantidad final**: introduzca _10000000_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-228">**To quantity:** Enter _10000000_.</span></span>
    - <span data-ttu-id="f35d8-229">**Unidad:** deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="f35d8-229">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="f35d8-230">**Cantidad para localizar:** seleccione _Ninguna_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-230">**Locate quantity:** Select _None_.</span></span>
    - <span data-ttu-id="f35d8-231">**Restringir por unidad:** desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="f35d8-231">**Restrict by unit:** Clear this check box.</span></span>
    - <span data-ttu-id="f35d8-232">**Redondear por arriba a unidad:** desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="f35d8-232">**Round up to unit:** Clear this check box.</span></span>
    - <span data-ttu-id="f35d8-233">**Localizar cantidad de embalaje:** desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="f35d8-233">**Locate packing quantity:** Clear this check box.</span></span>
    - <span data-ttu-id="f35d8-234">**Permitir división:** seleccione esta casilla.</span><span class="sxs-lookup"><span data-stu-id="f35d8-234">**Allow split:** Select this check box.</span></span>

1. <span data-ttu-id="f35d8-235">Seleccione **Guardar** para guardar la nueva línea.</span><span class="sxs-lookup"><span data-stu-id="f35d8-235">Select **Save** to save the new line.</span></span>
1. <span data-ttu-id="f35d8-236">Mientras su nueva línea aún está seleccionada en la cuadrícula **Líneas**, seleccione **Nuevo** en la ficha desplegable **Acciones de directiva de ubicación** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="f35d8-236">While your new line is still selected in the **Lines** grid, select **New** on the **Location Directive Actions** FastTab to add a row to the grid.</span></span>
1. <span data-ttu-id="f35d8-237">Establezca los siguientes valores en la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="f35d8-237">In the new row, set the following values:</span></span>

    - <span data-ttu-id="f35d8-238">**Número de secuencia:** Introduzca _1_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-238">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="f35d8-239">**Nombre:** introduzca _Seleccionar desde grandes cantidades_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-239">**Name:** Enter _Pick from bulk_.</span></span>
    - <span data-ttu-id="f35d8-240">**Uso de ubicación fija:** seleccione _Ubicaciones fijas y no fijas_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-240">**Fixed location usage:** Select _Fixed and non-fixed locations_.</span></span>
    - <span data-ttu-id="f35d8-241">**Permitir inventario negativo**: desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="f35d8-241">**Allow negative inventory:** Clear this check box.</span></span>
    - <span data-ttu-id="f35d8-242">**Lote habilitado**: desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="f35d8-242">**Batch enabled:** Clear this check box.</span></span>
    - <span data-ttu-id="f35d8-243">**Estrategia:** seleccione _Ninguna_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-243">**Strategy:** Select _None_.</span></span>

1. <span data-ttu-id="f35d8-244">Seleccione **Guardar** para guardar la nueva acción.</span><span class="sxs-lookup"><span data-stu-id="f35d8-244">Select **Save** to save the new action.</span></span>
1. <span data-ttu-id="f35d8-245">Mientras su nueva acción aún está seleccionada, seleccione **Editar consulta** encima de la cuadrícula **Acciones de directiva de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="f35d8-245">While your new action still selected, select **Edit query** above the **Location Directive Actions** grid.</span></span>
1. <span data-ttu-id="f35d8-246">Aparece un cuadro de diálogo de consulta, donde puede seleccionar las ubicaciones desde las que reabastecer.</span><span class="sxs-lookup"><span data-stu-id="f35d8-246">A query dialog box appears, where you can select the locations to replenish from.</span></span> <span data-ttu-id="f35d8-247">En la pestaña **Intervalo**, seleccione **Nuevo** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="f35d8-247">On the **Range** tab, select **Add** to add a row to the grid.</span></span>
1. <span data-ttu-id="f35d8-248">Establezca los siguientes valores en la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="f35d8-248">In the new row, set the following values:</span></span>

    - <span data-ttu-id="f35d8-249">**Tabla**: _Ubicaciones_</span><span class="sxs-lookup"><span data-stu-id="f35d8-249">**Table:** _Locations_</span></span>
    - <span data-ttu-id="f35d8-250">**Tabla derivada:** _Ubicaciones_</span><span class="sxs-lookup"><span data-stu-id="f35d8-250">**Derived table:** _Locations_</span></span>
    - <span data-ttu-id="f35d8-251">**Campo**: _ID de zona_</span><span class="sxs-lookup"><span data-stu-id="f35d8-251">**Field:** _Zone ID_</span></span>
    - <span data-ttu-id="f35d8-252">**Criterios**: _BULK_</span><span class="sxs-lookup"><span data-stu-id="f35d8-252">**Criteria:** _BULK_</span></span>

1. <span data-ttu-id="f35d8-253">Seleccione **Aceptar** para guardar su consulta y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f35d8-253">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="f35d8-254">Seleccione **Guardar** para guardar su directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="f35d8-254">Select **Save** to save your location directive.</span></span>

##### <a name="create-a-replenishment-put-directive"></a><span data-ttu-id="f35d8-255">Crear una directiva de colocación de reabastecimiento</span><span class="sxs-lookup"><span data-stu-id="f35d8-255">Create a replenishment put directive</span></span>

1. <span data-ttu-id="f35d8-256">En la página **Directivas de ubicación**, en el panel izquierdo, asegúrese de que el campo **Tipo de orden de trabajo** sigue seleccionado en _Reabastecimiento_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-256">On the **Location directives** page, in the left pane, make sure that the **Work order type** field is still set to _Replenishment_.</span></span>
1. <span data-ttu-id="f35d8-257">En el panel de acciones, seleccione **Nuevo** para crear otra nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="f35d8-257">On the Action Pane, select **New** to create another new directive.</span></span>
1. <span data-ttu-id="f35d8-258">Establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="f35d8-258">Set the following values:</span></span>

    - <span data-ttu-id="f35d8-259">**Número de secuencia:** acepte el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f35d8-259">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="f35d8-260">**Nombre:** introduzca _Colocación de zona_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-260">**Name:** Enter _Zone put_.</span></span>
    - <span data-ttu-id="f35d8-261">**Tipo de orden de trabajo:** seleccione _Colocación_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-261">**Work order type:** Select _Put_.</span></span>
    - <span data-ttu-id="f35d8-262">**Sitio:** seleccione _6_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-262">**Site:** Select _6_.</span></span>
    - <span data-ttu-id="f35d8-263">**Almacén:** seleccione _61_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-263">**Warehouse:** Select _61_.</span></span>
    - <span data-ttu-id="f35d8-264">**Código de directiva:** seleccione _Reabastecimiento de zona_ para vincular esta directiva de ubicación a la plantilla de reabastecimiento que creó anteriormente utilizando el código que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f35d8-264">**Directive code:** Select _Zone replen_ to link this location directive with the replenishment template that you created earlier by using the code that you created earlier.</span></span>
    - <span data-ttu-id="f35d8-265">**Varios SKU:** establezca esta opción en _No_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-265">**Multi SKU:** Set this option to _No_.</span></span>

1. <span data-ttu-id="f35d8-266">Seleccione **Guardar** para crear una directiva que tenga la configuración que ha configurado hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="f35d8-266">Select **Save** to create a directive that has the settings that you've configured so far.</span></span>
1. <span data-ttu-id="f35d8-267">En la ficha desplegable **Líneas**, seleccione **Nuevo** para agregar una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="f35d8-267">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="f35d8-268">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="f35d8-268">On the new line, set the following values:</span></span>

    - <span data-ttu-id="f35d8-269">**Número de secuencia:** Introduzca _1_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-269">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="f35d8-270">**Cantidad inicial**: introduzca _0_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-270">**From quantity:** Enter _0_.</span></span>
    - <span data-ttu-id="f35d8-271">**Cantidad final**: introduzca _10000000_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-271">**To quantity:** Enter _10000000_.</span></span>
    - <span data-ttu-id="f35d8-272">**Unidad:** deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="f35d8-272">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="f35d8-273">**Cantidad para localizar:** seleccione _Ninguna_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-273">**Locate quantity:** Select _None_.</span></span>
    - <span data-ttu-id="f35d8-274">**Restringir por unidad:** desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="f35d8-274">**Restrict by unit:** Clear this check box.</span></span>
    - <span data-ttu-id="f35d8-275">**Redondear por arriba a unidad:** desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="f35d8-275">**Round up to unit:** Clear this check box.</span></span>
    - <span data-ttu-id="f35d8-276">**Localizar cantidad de embalaje:** desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="f35d8-276">**Locate packing quantity:** Clear this check box.</span></span>
    - <span data-ttu-id="f35d8-277">**Permitir división:** seleccione esta casilla.</span><span class="sxs-lookup"><span data-stu-id="f35d8-277">**Allow split:** Select this check box.</span></span>

1. <span data-ttu-id="f35d8-278">Seleccione **Guardar** para guardar la nueva línea.</span><span class="sxs-lookup"><span data-stu-id="f35d8-278">Select **Save** to save the new line.</span></span>
1. <span data-ttu-id="f35d8-279">Mientras su nueva línea aún está seleccionada en la cuadrícula **Líneas**, seleccione **Nuevo** en la ficha desplegable **Acciones de directiva de ubicación** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="f35d8-279">While your new line is still selected in the **Lines** grid, select **New** on the **Location Directive Actions** FastTab to add a row to the grid.</span></span>
1. <span data-ttu-id="f35d8-280">Establezca los siguientes valores en la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="f35d8-280">In the new row, set the following values:</span></span>

    - <span data-ttu-id="f35d8-281">**Número de secuencia:** Introduzca _1_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-281">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="f35d8-282">**Nombre:** introduzca _Colocación de zona_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-282">**Name:** Enter _Zone put_.</span></span>
    - <span data-ttu-id="f35d8-283">**Uso de ubicación fija:** seleccione _Ubicaciones fijas y no fijas_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-283">**Fixed location usage:** Select _Fixed and non-fixed locations_.</span></span>
    - <span data-ttu-id="f35d8-284">**Permitir inventario negativo**: desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="f35d8-284">**Allow negative inventory:** Clear this check box.</span></span>
    - <span data-ttu-id="f35d8-285">**Lote habilitado**: desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="f35d8-285">**Batch enabled:** Clear this check box.</span></span>
    - <span data-ttu-id="f35d8-286">**Estrategia:** seleccione _Consolidar_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-286">**Strategy:** Select _Consolidate_.</span></span>

1. <span data-ttu-id="f35d8-287">Seleccione **Guardar** para guardar la nueva acción.</span><span class="sxs-lookup"><span data-stu-id="f35d8-287">Select **Save** to save the new action.</span></span>
1. <span data-ttu-id="f35d8-288">Mientras su nueva acción aún está seleccionada, seleccione **Editar consulta** encima de la cuadrícula **Acciones de directiva de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="f35d8-288">While your new action is still selected, select **Edit query** above the **Location Directive Actions** grid.</span></span>
1. <span data-ttu-id="f35d8-289">Aparece un cuadro de diálogo de consulta, donde puede seleccionar la zona a la que reabastecer.</span><span class="sxs-lookup"><span data-stu-id="f35d8-289">A query dialog box appears, where you can select the zone to replenish to.</span></span> <span data-ttu-id="f35d8-290">Esta zona debe ser la misma zona que se especifica en la plantilla de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="f35d8-290">This zone should be the same zone that is specified in the replenishment template.</span></span> <span data-ttu-id="f35d8-291">En la pestaña **Intervalo**, seleccione **Nuevo** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="f35d8-291">On the **Range** tab, select **Add** to add a row to the grid.</span></span>
1. <span data-ttu-id="f35d8-292">Establezca los siguientes valores en la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="f35d8-292">In the new row, set the following values:</span></span>

    - <span data-ttu-id="f35d8-293">**Tabla**: _Ubicaciones_</span><span class="sxs-lookup"><span data-stu-id="f35d8-293">**Table:** _Locations_</span></span>
    - <span data-ttu-id="f35d8-294">**Tabla derivada:** _Ubicaciones_</span><span class="sxs-lookup"><span data-stu-id="f35d8-294">**Derived table:** _Locations_</span></span>
    - <span data-ttu-id="f35d8-295">**Campo**: _ID de zona_</span><span class="sxs-lookup"><span data-stu-id="f35d8-295">**Field:** _Zone ID_</span></span>
    - <span data-ttu-id="f35d8-296">**Criterios:** _FLOOR_</span><span class="sxs-lookup"><span data-stu-id="f35d8-296">**Criteria:** _FLOOR_</span></span>

1. <span data-ttu-id="f35d8-297">Seleccione **Aceptar** para guardar su consulta y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f35d8-297">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="f35d8-298">Seleccione **Guardar** para guardar su directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="f35d8-298">Select **Save** to save your location directive.</span></span>

## <a name="scenario"></a><span data-ttu-id="f35d8-299">Situación</span><span class="sxs-lookup"><span data-stu-id="f35d8-299">Scenario</span></span>

<span data-ttu-id="f35d8-300">En esta sección se proporciona un escenario de muestra que expone cómo trabajar con la característica.</span><span class="sxs-lookup"><span data-stu-id="f35d8-300">This section provides a sample scenario that shows how to work with the feature.</span></span>

### <a name="prepare-the-sample-data-that-is-required-for-the-sample-scenario"></a><span data-ttu-id="f35d8-301">Preparar los datos de muestra necesarios para el escenario de muestra</span><span class="sxs-lookup"><span data-stu-id="f35d8-301">Prepare the sample data that is required for the sample scenario</span></span>

<span data-ttu-id="f35d8-302">Antes de empezar a trabajar en el escenario, debe activar los datos de muestra y configurar la característica como se describe en esta sección y en las secciones anteriores de este tema.</span><span class="sxs-lookup"><span data-stu-id="f35d8-302">Before you start to work through the scenario, you must activate sample data and set up the feature as described in this section and in the previous sections of this topic.</span></span>

#### <a name="use-the-usmf-legal-entity"></a><span data-ttu-id="f35d8-303">Usar la entidad jurídica USMF</span><span class="sxs-lookup"><span data-stu-id="f35d8-303">Use the USMF legal entity</span></span>

<span data-ttu-id="f35d8-304">Para trabajar en el escenario mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) estándar.</span><span class="sxs-lookup"><span data-stu-id="f35d8-304">To work through the scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="f35d8-305">Además, también debe seleccionar la entidad legal **USMF** antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="f35d8-305">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

#### <a name="prepare-additional-sample-data"></a><span data-ttu-id="f35d8-306">Preparar datos de muestra adicionales</span><span class="sxs-lookup"><span data-stu-id="f35d8-306">Prepare additional sample data</span></span>

<span data-ttu-id="f35d8-307">Después de haber seleccionado la entidad jurídica **USMF**, agregue los datos de muestra adicionales que se requieren, como se describe en la sección [Configurar reabastecimiento basado en zonas](#setup) que aparece anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="f35d8-307">After you've selected the **USMF** legal entity, add the additional sample data that is required, as described in the [Set up zone-based replenishment](#setup) section earlier in this topic.</span></span>

#### <a name="check-your-on-hand-inventory"></a><span data-ttu-id="f35d8-308">Comprobar el inventario disponible</span><span class="sxs-lookup"><span data-stu-id="f35d8-308">Check your on-hand inventory</span></span>

<span data-ttu-id="f35d8-309">Siga estos pasos para asegurarse de que su sistema incluya suficiente inventario para admitir el escenario de muestra.</span><span class="sxs-lookup"><span data-stu-id="f35d8-309">Follow these steps to make sure that your system includes enough inventory to support the sample scenario.</span></span>

1. <span data-ttu-id="f35d8-310">Asegúrese de que haya inventario disponible para el artículo *A0001* en dos ubicaciones diferentes en la zona de selección (*FLOOR*) que se especifica en la plantilla de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="f35d8-310">Make sure that there is on-hand inventory for item *A0001* at two different locations in the pick zone (*FLOOR*) that is specified in the replenishment template.</span></span> <span data-ttu-id="f35d8-311">Sin embargo, el inventario total debe ser inferior a la cantidad mínima requerida (*50*) que se especifica en la plantilla de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="f35d8-311">However, the total inventory should be less than the required minimum quantity (*50*) that is specified on the replenishment template.</span></span> <span data-ttu-id="f35d8-312">De esta manera, puede simular cómo se realiza el cálculo para toda la zona en lugar de solo para una única ubicación.</span><span class="sxs-lookup"><span data-stu-id="f35d8-312">In this way, you can simulate how the calculation occurs for the whole zone instead of just for a single location.</span></span> <span data-ttu-id="f35d8-313">**Utilice cualquiera de los procesos del almacén para ajustar el inventario según sea necesario.**</span><span class="sxs-lookup"><span data-stu-id="f35d8-313">**Use any of the warehouse processes to adjust inventory as required.**</span></span>
1. <span data-ttu-id="f35d8-314">Asegúrese de que haya suficiente inventario para el artículo *A0001* en una ubicación de almacenaje que se especifica en la directiva de ubicación de selección de zona donde el trabajo de reabastecimiento debe seleccionar los artículos del id. de zona *BULK*.</span><span class="sxs-lookup"><span data-stu-id="f35d8-314">Make sure that there is enough inventory for item *A0001* at a bulk location that is specified in the zone pick location directive where the replenishment work should pick the items from zone ID *BULK*.</span></span> <span data-ttu-id="f35d8-315">El inventario total debe ser superior a la cantidad máxima requerida (*150*) que se especifica en la plantilla de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="f35d8-315">The total inventory must be more than the required maximum quantity (*150*) that is specified in the replenishment template.</span></span>
1. <span data-ttu-id="f35d8-316">Opcional pero recomendado: siga estos pasos para crear un diario de ajuste de inventario:</span><span class="sxs-lookup"><span data-stu-id="f35d8-316">Optional but recommended: Follow these steps to create an inventory adjustment journal:</span></span>

    1. <span data-ttu-id="f35d8-317">Vaya a **Gestión del inventario \> Movimientos de diario \> Artículos \> Ajuste de inventario**.</span><span class="sxs-lookup"><span data-stu-id="f35d8-317">Go to **Inventory management \> Journal entries \> Items \> Inventory adjustment**.</span></span>
    1. <span data-ttu-id="f35d8-318">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="f35d8-318">Select **New**.</span></span>
    1. <span data-ttu-id="f35d8-319">En el cuadro de diálogo **Crear diario de inventario**, en el campo **Almacén**, seleccione *61*.</span><span class="sxs-lookup"><span data-stu-id="f35d8-319">In the **Create inventory journal** dialog box, in the **Warehouse** field, select *61*.</span></span>
    1. <span data-ttu-id="f35d8-320">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f35d8-320">Select **OK**.</span></span>
    1. <span data-ttu-id="f35d8-321">En la ficha desplegable **Líneas de diario**, use el botón **Nuevo** para agregar tres líneas a la cuadrícula y establecer los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="f35d8-321">On the **Journal lines** FastTab, use the **New** button to add three lines to the grid, and set the following values.</span></span> <span data-ttu-id="f35d8-322">Una vez que haya terminado de configurar cada línea, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f35d8-322">After you've finished setting up each line, select **Save**.</span></span>

        - <span data-ttu-id="f35d8-323">**Línea 1:**</span><span class="sxs-lookup"><span data-stu-id="f35d8-323">**Line 1:**</span></span>

            - <span data-ttu-id="f35d8-324">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="f35d8-324">**Item number:** *A0001*</span></span>
            - <span data-ttu-id="f35d8-325">**Sitio**: *6*</span><span class="sxs-lookup"><span data-stu-id="f35d8-325">**Site:** *6*</span></span>
            - <span data-ttu-id="f35d8-326">**Almacén**: *61*</span><span class="sxs-lookup"><span data-stu-id="f35d8-326">**Warehouse:** *61*</span></span>
            - <span data-ttu-id="f35d8-327">**Ubicación:** *02A01R1S1B*</span><span class="sxs-lookup"><span data-stu-id="f35d8-327">**Location:** *02A01R1S1B*</span></span>
            - <span data-ttu-id="f35d8-328">**Matrícula:** seleccione una matrícula existente en la lista o cree una nueva matrícula.</span><span class="sxs-lookup"><span data-stu-id="f35d8-328">**License plate:** Select an existing license plate in the list, or create a new license plate.</span></span>
            - <span data-ttu-id="f35d8-329">**Cantidad:** *1000*</span><span class="sxs-lookup"><span data-stu-id="f35d8-329">**Quantity:** *1000*</span></span>

        - <span data-ttu-id="f35d8-330">**Línea 2:**</span><span class="sxs-lookup"><span data-stu-id="f35d8-330">**Line 2:**</span></span>

            - <span data-ttu-id="f35d8-331">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="f35d8-331">**Item number:** *A0001*</span></span>
            - <span data-ttu-id="f35d8-332">**Sitio**: *6*</span><span class="sxs-lookup"><span data-stu-id="f35d8-332">**Site:** *6*</span></span>
            - <span data-ttu-id="f35d8-333">**Almacén**: *61*</span><span class="sxs-lookup"><span data-stu-id="f35d8-333">**Warehouse:** *61*</span></span>
            - <span data-ttu-id="f35d8-334">**Ubicación:** *07A01R2S1B*</span><span class="sxs-lookup"><span data-stu-id="f35d8-334">**Location:** *07A01R2S1B*</span></span>
            - <span data-ttu-id="f35d8-335">**Matrícula:** seleccione una matrícula existente en la lista o cree una nueva matrícula.</span><span class="sxs-lookup"><span data-stu-id="f35d8-335">**License plate:** Select an existing license plate in the list, or create a new license plate.</span></span>
            - <span data-ttu-id="f35d8-336">**Cantidad:** *15*</span><span class="sxs-lookup"><span data-stu-id="f35d8-336">**Quantity:** *15*</span></span>

        - <span data-ttu-id="f35d8-337">**Línea 3:**</span><span class="sxs-lookup"><span data-stu-id="f35d8-337">**Line 3:**</span></span>

            - <span data-ttu-id="f35d8-338">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="f35d8-338">**Item number:** *A0001*</span></span>
            - <span data-ttu-id="f35d8-339">**Sitio**: *6*</span><span class="sxs-lookup"><span data-stu-id="f35d8-339">**Site:** *6*</span></span>
            - <span data-ttu-id="f35d8-340">**Almacén**: *61*</span><span class="sxs-lookup"><span data-stu-id="f35d8-340">**Warehouse:** *61*</span></span>
            - <span data-ttu-id="f35d8-341">**Ubicación:** *07A01R1S1B*</span><span class="sxs-lookup"><span data-stu-id="f35d8-341">**Location:** *07A01R1S1B*</span></span>
            - <span data-ttu-id="f35d8-342">**Matrícula:** seleccione una matrícula existente en la lista o cree una nueva matrícula.</span><span class="sxs-lookup"><span data-stu-id="f35d8-342">**License plate:** Select an existing license plate in the list, or create a new license plate.</span></span>
            - <span data-ttu-id="f35d8-343">**Cantidad:** *10*</span><span class="sxs-lookup"><span data-stu-id="f35d8-343">**Quantity:** *10*</span></span>

    1. <span data-ttu-id="f35d8-344">En el panel de acciones, seleccione **Validar**.</span><span class="sxs-lookup"><span data-stu-id="f35d8-344">On the Action Pane, select **Validate**.</span></span> <span data-ttu-id="f35d8-345">Corrija los errores que se encuentren antes de avanzar al siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="f35d8-345">Address any errors that are found before you move on to the next step.</span></span>
    1. <span data-ttu-id="f35d8-346">En el panel de acciones, seleccione **Registrar** para registrar el inventario en el almacén.</span><span class="sxs-lookup"><span data-stu-id="f35d8-346">On the Action Pane, select **Post** to post the inventory to the warehouse.</span></span>

### <a name="sample-scenario-run-zone-based-minmax-replenishment"></a><span data-ttu-id="f35d8-347">Escenario de muestra: Ejecutar reabastecimiento mín./máx. basado en zonas</span><span class="sxs-lookup"><span data-stu-id="f35d8-347">Sample scenario: Run zone-based min/max replenishment</span></span>

<span data-ttu-id="f35d8-348">Una vez que todos los datos de muestra de requisitos previos estén en su lugar, puede desencadenar el reabastecimiento siguiendo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f35d8-348">After all the prerequisite sample data is in place, you can trigger replenishment by following these steps.</span></span>

1. <span data-ttu-id="f35d8-349">Vaya a **Gestión de almacenes \> Reabastecimiento \> Reabastecimientos**.</span><span class="sxs-lookup"><span data-stu-id="f35d8-349">Go to **Warehouse management \> Replenishment \> Replenishments**.</span></span>
1. <span data-ttu-id="f35d8-350">En el cuadro de diálogo **Reabastecimiento**, en la ficha desplegable **Registros a incluir**, seleccione **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="f35d8-350">In the **Replenishment** dialog box, on the **Records to include** FastTab, select **Filter**.</span></span>
1. <span data-ttu-id="f35d8-351">En el cuadro de diálogo **Consulta**, en la pestaña **Intervalo**, edite la fila de la tabla predeterminada de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f35d8-351">In the **Inquiry** dialog box, on the **Range** tab, edit the default table row in the following way:</span></span>

    - <span data-ttu-id="f35d8-352">**Tabla:** seleccione _Plantillas de reabastecimiento_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-352">**Table:** Select _Replenishment templates_.</span></span>
    - <span data-ttu-id="f35d8-353">**Tabla derivada:** seleccione _Plantillas de reabastecimiento_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-353">**Derived table:** Select _Replenishment templates_.</span></span>
    - <span data-ttu-id="f35d8-354">**Campo:** seleccione _Plantilla de reabastecimiento_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-354">**Field:** Select _Replenishment template_.</span></span>
    - <span data-ttu-id="f35d8-355">**Criterios:** seleccione _Reabastecimiento mín./máx. de zonas_.</span><span class="sxs-lookup"><span data-stu-id="f35d8-355">**Criteria:** Select _Zone min/max replen_.</span></span> <span data-ttu-id="f35d8-356">Esta plantilla de reabastecimiento es la plantilla de reabastecimiento que creó mientras preparaba los datos de demostración para este escenario.</span><span class="sxs-lookup"><span data-stu-id="f35d8-356">This replenishment template is the replenishment template that you created while you were preparing the demo data for this scenario.</span></span>

1. <span data-ttu-id="f35d8-357">Seleccione **Aceptar** para guardar la consulta y vuelva al cuadro de diálogo **Reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="f35d8-357">Select **OK** to save the query and go back to the **Replenishment** dialog box.</span></span>
1. <span data-ttu-id="f35d8-358">Seleccione **Aceptar** para ejecutar la plantilla de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="f35d8-358">Select **OK** to run the replenishment template.</span></span>

<span data-ttu-id="f35d8-359">El trabajo de reabastecimiento ahora se crea para seleccionar el inventario desde la zona *BULK* y reabastecerlo en la zona *FLOOR*.</span><span class="sxs-lookup"><span data-stu-id="f35d8-359">Replenishment work is now created to pick inventory from the *BULK* zone and replenish it to the *FLOOR* zone.</span></span>

## <a name="notes-and-tips"></a><span data-ttu-id="f35d8-360">Notas y consejos</span><span class="sxs-lookup"><span data-stu-id="f35d8-360">Notes and tips</span></span>

<span data-ttu-id="f35d8-361">Aquí se muestran algunas notas y consejos para trabajar con la característica:</span><span class="sxs-lookup"><span data-stu-id="f35d8-361">Here are a few notes and tips for working with the feature:</span></span>

- <span data-ttu-id="f35d8-362">Para configurar el trabajo de reabastecimiento que va a la zona deseada, puede vincular las líneas de la plantilla de reabastecimiento y las directivas de ubicación de cualquiera de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="f35d8-362">To set up replenishment work that goes to the desired zone, you can link the replenishment template lines and location directives in either of the following ways:</span></span>

    - <span data-ttu-id="f35d8-363">Edite la consulta del encabezado de la directiva de ubicación y filtre las líneas de la plantilla de reabastecimiento seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="f35d8-363">Edit the location directive header query, and filter the selected replenishment template lines.</span></span>
    - <span data-ttu-id="f35d8-364">Utilice un código de directiva en la línea de la plantilla de reabastecimiento, y haga que coincida con la directiva de ubicación de colocación.</span><span class="sxs-lookup"><span data-stu-id="f35d8-364">Use a directive code on the replenishment template line, and match it to the put location directive.</span></span>

- <span data-ttu-id="f35d8-365">Si está utilizando ubicaciones dinámicas, se creará un trabajo de reabastecimiento para la primera ubicación disponible o para una ubicación que ya contiene inventario, si la acción de directiva de ubicación está configurada para usar la estrategia **Consolidar**.</span><span class="sxs-lookup"><span data-stu-id="f35d8-365">If you're using dynamic locations, replenishment work will be created either for the first available location or for a location that already contains inventory, if the location directive action is set up to use the **Consolidate** strategy.</span></span>
- <span data-ttu-id="f35d8-366">Si utiliza ubicaciones fijas en lugar de zonas, debe usar el [reabastecimiento mín./máx. estándar](tasks/set-up-min-max-replenishment-process.md).</span><span class="sxs-lookup"><span data-stu-id="f35d8-366">If you're using fixed locations instead of zones, you should use [standard min/max replenishment](tasks/set-up-min-max-replenishment-process.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]