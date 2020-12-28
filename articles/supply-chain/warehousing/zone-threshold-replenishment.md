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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 6f4ddd03ec16ac43b007b904eb688563735e0941
ms.sourcegitcommit: d9bffbeae2ba14f06294dd275383077d4d65c4fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "4654181"
---
# <a name="zone-threshold-replenishment"></a><span data-ttu-id="91382-104">Reabastecimiento de umbral de zona</span><span class="sxs-lookup"><span data-stu-id="91382-104">Zone threshold replenishment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="91382-105">El reabastecimiento basado en zonas utiliza una estrategia de [reabastecimiento](replenishment.md) mínimo/máximo (mín./máx.), pero evalúa zonas de almacén completas en lugar de solo ubicaciones individuales.</span><span class="sxs-lookup"><span data-stu-id="91382-105">Zone-based replenishment uses a minimum/maximum (min/max) [replenishment](replenishment.md) strategy, but it evaluates whole warehouse zones instead of just individual locations.</span></span> <span data-ttu-id="91382-106">Por lo tanto, los directores de almacén pueden aprender más rápido cuándo se requiere un inventario adicional en una zona de picking.</span><span class="sxs-lookup"><span data-stu-id="91382-106">Therefore, warehouse managers can more quickly learn when additional inventory is required in a picking zone.</span></span>

<span data-ttu-id="91382-107">La configuración de esta característica se asemeja a la configuración del reabastecimiento basado en ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="91382-107">The setup for this feature resembles the setup for location-based replenishment.</span></span> <span data-ttu-id="91382-108">Sin embargo, cuando configura una plantilla para un reabastecimiento mínimo/máximo, también puede especificar si el umbral debe evaluarse por ubicación o por zona.</span><span class="sxs-lookup"><span data-stu-id="91382-108">However, when you set up a template for min/max replenishment, you can also specify whether the threshold should be evaluated per location or per zone.</span></span> <span data-ttu-id="91382-109">Si configura una evaluación basada en zonas, debe agregar zonas específicas a la consulta de selección de zona.</span><span class="sxs-lookup"><span data-stu-id="91382-109">If you set up evaluation that is based on zones, you must add specific zones to the zone selection query.</span></span>

<span data-ttu-id="91382-110">Al igual que el reabastecimiento mínimo/máximo basado en ubicaciones, el reabastecimiento mínimo/máximo basada en zonas se basa en la configuración de un umbral de inventario mínimo que desencadena la creación de un trabajo de reabastecimiento para los artículos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="91382-110">Like location-based min/max replenishment, zone-based min/max replenishment is based the setup of a minimum inventory threshold that triggers the creation of replenishment work for selected items.</span></span> <span data-ttu-id="91382-111">Este trabajo de reabastecimiento aumentará el inventario hasta el umbral máximo especificado para la zona.</span><span class="sxs-lookup"><span data-stu-id="91382-111">This replenishment work will increase inventory up to the specified maximum threshold for the zone.</span></span>

> [!NOTE]
> <span data-ttu-id="91382-112">Los procesos de reabastecimiento de zona para variantes de producto no son compatibles con la versión actual.</span><span class="sxs-lookup"><span data-stu-id="91382-112">Zone replenishment processes for product variants aren't supported in the current release.</span></span>


<span data-ttu-id="91382-113">A diferencia del reabastecimiento mínimo/máximo basado en ubicaciones, el reabastecimiento mínimo/máximo basado en zonas no requiere ubicaciones fijas para evaluar si las ubicaciones deben almacenar un determinado artículo.</span><span class="sxs-lookup"><span data-stu-id="91382-113">Unlike location-based min/max replenishment, zone-based min/max replenishment doesn't require fixed locations to evaluate whether locations should store a specific item.</span></span> <span data-ttu-id="91382-114">Por lo tanto, el reabastecimiento basado en zonas le permite utilizar el reabastecimiento mínimo/máximo incluso si no tiene ubicaciones fijas para cada artículo o variante de artículo en el almacén.</span><span class="sxs-lookup"><span data-stu-id="91382-114">Therefore, zone-based replenishment lets you use min/max replenishment even if you don't have fixed locations for each item or item variant in the warehouse.</span></span> <span data-ttu-id="91382-115">Cuando una cantidad en la zona cae por debajo del umbral mínimo especificado, se crea un trabajo de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="91382-115">When a quantity in the zone falls below the specified minimum threshold, replenishment work is created.</span></span> <span data-ttu-id="91382-116">Las directivas de ubicación determinarán en qué ubicación concreta se debe colocar el inventario.</span><span class="sxs-lookup"><span data-stu-id="91382-116">Location directives will determine which specific location the inventory should be put into.</span></span>

## <a name="turn-on-the-zone-threshold-replenishment-feature"></a><span data-ttu-id="91382-117">Activar la característica de reabastecimiento de umbral de zona</span><span class="sxs-lookup"><span data-stu-id="91382-117">Turn on the Zone threshold replenishment feature</span></span>

<span data-ttu-id="91382-118">Antes de poder usar la característica *Reabastecimiento de umbral de zona*, esta debe estar activada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="91382-118">Before you can use the *Zone threshold replenishment* feature, it must be turned on in your system.</span></span> <span data-ttu-id="91382-119">Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="91382-119">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="91382-120">En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="91382-120">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="91382-121">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="91382-121">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="91382-122">**Nombre de característica:** *Reabastecimiento de umbral de zona*</span><span class="sxs-lookup"><span data-stu-id="91382-122">**Feature name:** *Zone threshold replenishment*</span></span>

## <a name="set-up-zone-based-replenishment"></a><a name="setup"></a><span data-ttu-id="91382-123">Configurar reabastecimiento basado en zonas</span><span class="sxs-lookup"><span data-stu-id="91382-123">Set up zone-based replenishment</span></span>

<span data-ttu-id="91382-124">Para configurar un reabastecimiento basada en zonas, debe configurar varias partes del sistema.</span><span class="sxs-lookup"><span data-stu-id="91382-124">To set up zone-based replenishment, you must configure several parts of the system.</span></span> <span data-ttu-id="91382-125">Esta sección presenta las diversas configuraciones y proporciona valores de datos de demostración que puede introducir si desea trabajar en el escenario al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="91382-125">This section introduces the various settings and provides demo data values that you can enter if you want to work through the scenario at the end of this topic.</span></span>

### <a name="set-up-directive-codes"></a><span data-ttu-id="91382-126">Configurar códigos de directivas</span><span class="sxs-lookup"><span data-stu-id="91382-126">Set up directive codes</span></span>

<span data-ttu-id="91382-127">Los [códigos de directivas](control-warehouse-location-directives.md) le permiten ser más específico cuando define la plantilla de ubicación que se utiliza en una plantilla de trabajo.</span><span class="sxs-lookup"><span data-stu-id="91382-127">[Directive codes](control-warehouse-location-directives.md) let you be more specific when you define the location template that is used in a work template.</span></span> <span data-ttu-id="91382-128">Cada código establece un valor común al que puede hacer referencia cuando configura cada tipo de plantilla.</span><span class="sxs-lookup"><span data-stu-id="91382-128">Each code establishes a common value that you can refer to when you configure each type of template.</span></span>

#### <a name="view-and-edit-directive-codes"></a><span data-ttu-id="91382-129">Ver y editar códigos de directivas</span><span class="sxs-lookup"><span data-stu-id="91382-129">View and edit directive codes</span></span>

<span data-ttu-id="91382-130">Para ver o editar sus códigos de directivas, vaya a **Gestión de almacenes \> Configuración \> Códigos de directivas**.</span><span class="sxs-lookup"><span data-stu-id="91382-130">To view or edit your directive codes, go to **Warehouse management \> Setup \> Directive codes**.</span></span>

#### <a name="prepare-demo-data-directive-codes"></a><span data-ttu-id="91382-131">Preparar códigos de directivas de datos de demostración</span><span class="sxs-lookup"><span data-stu-id="91382-131">Prepare demo data directive codes</span></span>

<span data-ttu-id="91382-132">En este ejemplo se muestra cómo preparar un código de directivas.</span><span class="sxs-lookup"><span data-stu-id="91382-132">This example shows how to prepare a directive code.</span></span> <span data-ttu-id="91382-133">Si tiene previsto trabajar en el escenario al final de este tema, utilice los valores de datos de demostración que se proporcionan aquí.</span><span class="sxs-lookup"><span data-stu-id="91382-133">If you're planning to work through the scenario at the end of this topic, use the demo data values that are provided here.</span></span> <span data-ttu-id="91382-134">De lo contrario, utilice sus propios valores.</span><span class="sxs-lookup"><span data-stu-id="91382-134">Otherwise, use your own values.</span></span>

1. <span data-ttu-id="91382-135">Seleccione la entidad jurídica **USMF** para trabajar con los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="91382-135">Select the **USMF** legal entity to work with the demo data.</span></span>
1. <span data-ttu-id="91382-136">Vaya a **Gestión de almacenes \> Configurar \> Códigos de directivas**.</span><span class="sxs-lookup"><span data-stu-id="91382-136">Go to **Warehouse management \> Setup \> Directive codes**.</span></span>
1. <span data-ttu-id="91382-137">En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="91382-137">On the Action Pane, select **New** to add a row to the grid.</span></span>
1. <span data-ttu-id="91382-138">Establezca los siguientes valores en la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="91382-138">In the new row, set the following values:</span></span>

    - <span data-ttu-id="91382-139">**Código de directiva:** _Reabastecimiento de zona_</span><span class="sxs-lookup"><span data-stu-id="91382-139">**Directive code:** _Zone replen_</span></span>
    - <span data-ttu-id="91382-140">**Descripción de la directiva:** _Reabastecimiento de zona_</span><span class="sxs-lookup"><span data-stu-id="91382-140">**Directive description:** _Zone replenishment_</span></span>

1. <span data-ttu-id="91382-141">Seleccione **Guardar** para guardar el nuevo código.</span><span class="sxs-lookup"><span data-stu-id="91382-141">Select **Save** to save the new code.</span></span>

### <a name="set-up-replenishment-templates"></a><span data-ttu-id="91382-142">Configurar plantillas de reabastecimiento</span><span class="sxs-lookup"><span data-stu-id="91382-142">Set up replenishment templates</span></span>

<span data-ttu-id="91382-143">Las [plantillas de reabastecimiento mínimo/máximo](tasks/set-up-min-max-replenishment-process.md) son el mecanismo principal para mantener niveles óptimos en ubicaciones de picking.</span><span class="sxs-lookup"><span data-stu-id="91382-143">[Min/max replenishment templates](tasks/set-up-min-max-replenishment-process.md) are the primary mechanism for maintaining optimal levels in picking locations.</span></span> <span data-ttu-id="91382-144">En estas plantillas, debe configurar las reglas que se utilizarán para reabastecer el inventario en el almacén.</span><span class="sxs-lookup"><span data-stu-id="91382-144">In these templates, you must set up the rules that will be used to replenish inventory in the warehouse.</span></span> <span data-ttu-id="91382-145">El reabastecimiento para la que se pueden usar las plantillas incluye el reabastecimiento basado en zonas.</span><span class="sxs-lookup"><span data-stu-id="91382-145">The replenishment that the templates can be used for includes zone-based replenishment.</span></span>

#### <a name="view-and-edit-replenishment-templates"></a><span data-ttu-id="91382-146">Ver y editar plantillas de reabastecimiento</span><span class="sxs-lookup"><span data-stu-id="91382-146">View and edit replenishment templates</span></span>

<span data-ttu-id="91382-147">Una plantilla de reabastecimiento es un conjunto de reglas que controlan cuándo y cómo se reabastece un ubicación.</span><span class="sxs-lookup"><span data-stu-id="91382-147">A replenishment template is a set of rules that control when and how a location is replenished.</span></span> <span data-ttu-id="91382-148">Seleccione una plantilla para controlar cuándo y cómo se realiza el reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="91382-148">You select a template to control when and how replenishment is done.</span></span> <span data-ttu-id="91382-149">Para ver o editar sus plantillas de reabastecimiento, vaya a **Gestión de almacén \> Configuración \> Reabastecimiento \> Plantillas de reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="91382-149">To view or edit your replenishment templates, go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**.</span></span>

#### <a name="prepare-a-demo-data-replenishment-template"></a><span data-ttu-id="91382-150">Preparar una plantilla de reabastecimiento de datos de demostración</span><span class="sxs-lookup"><span data-stu-id="91382-150">Prepare a demo data replenishment template</span></span>

<span data-ttu-id="91382-151">En este ejemplo se muestra cómo preparar una plantilla de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="91382-151">This example shows how to prepare a replenishment template.</span></span> <span data-ttu-id="91382-152">Si tiene previsto trabajar en el escenario al final de este tema, utilice los valores de datos de demostración que se proporcionan aquí.</span><span class="sxs-lookup"><span data-stu-id="91382-152">If you're planning to work through the scenario at the end of this topic, use the demo data values that are provided here.</span></span> <span data-ttu-id="91382-153">De lo contrario, utilice sus propios valores.</span><span class="sxs-lookup"><span data-stu-id="91382-153">Otherwise, use your own values.</span></span>

1. <span data-ttu-id="91382-154">Seleccione la entidad jurídica **USMF** para trabajar con los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="91382-154">Select the **USMF** legal entity to work with the demo data.</span></span>
1. <span data-ttu-id="91382-155">Vaya a **Administración de almacenes \> Configurar \> Reabastecimiento \> Plantillas de reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="91382-155">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**.</span></span>
1. <span data-ttu-id="91382-156">Seleccione **Editar** para poner la página en modo de edición.</span><span class="sxs-lookup"><span data-stu-id="91382-156">Select **Edit** to put the page into edit mode.</span></span>
1. <span data-ttu-id="91382-157">En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula **Visión general**.</span><span class="sxs-lookup"><span data-stu-id="91382-157">On the Action Pane, select **New** to add a row to the **Overview** grid.</span></span>
1. <span data-ttu-id="91382-158">Establezca los siguientes valores en la fila nueva.</span><span class="sxs-lookup"><span data-stu-id="91382-158">In the new row, set the following values.</span></span> <span data-ttu-id="91382-159">Acepte los valores predeterminados para el resto de campos.</span><span class="sxs-lookup"><span data-stu-id="91382-159">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="91382-160">**Plantilla de reabastecimiento:** _Reabastecimiento mín./máx. de zona_</span><span class="sxs-lookup"><span data-stu-id="91382-160">**Replenish template:** _Zone min/max replen_</span></span>
    - <span data-ttu-id="91382-161">**Descripción:** _Reabastecimiento mín./máx. de zona_</span><span class="sxs-lookup"><span data-stu-id="91382-161">**Description:** _Zone min/max replenishment_</span></span>
    - <span data-ttu-id="91382-162">**Tipo de reabastecimiento:** _Mínimo o máximo_</span><span class="sxs-lookup"><span data-stu-id="91382-162">**Replenishment type:** _Minimum or maximum_</span></span>

1. <span data-ttu-id="91382-163">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="91382-163">Select **Save**.</span></span>
1. <span data-ttu-id="91382-164">Mientras la nueva fila sigue seleccionada en la cuadrícula **Visión general**, seleccione **Nuevo** encima de la cuadrícula **Detalles de la plantilla de reabastecimiento** para agregar una fila asociada a la plantilla de reabastecimiento *Reabastecimiento mín./máx. de zona* que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="91382-164">While the new row is still selected in the **Overview** grid, select **New** above the **Replenishment Template Details** grid to add a row that is associated with the *Zone Min/Max replen* replenishment template that you just created.</span></span>
1. <span data-ttu-id="91382-165">Establezca los siguientes valores en la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="91382-165">In the new row, set the following values:</span></span>

    - <span data-ttu-id="91382-166">**Número de secuencia:** Introduzca _1_.</span><span class="sxs-lookup"><span data-stu-id="91382-166">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="91382-167">**Descripción:** Introduzca _Reabastecimiento de zona de picking_.</span><span class="sxs-lookup"><span data-stu-id="91382-167">**Description:** Enter _Pick zone replenishment_.</span></span>
    - <span data-ttu-id="91382-168">**Unidad de reabastecimiento:** Seleccione _ea_.</span><span class="sxs-lookup"><span data-stu-id="91382-168">**Replenishment unit:** Select _ea_.</span></span>
    - <span data-ttu-id="91382-169">**Tipo de solicitud**: deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="91382-169">**Request type:** Leave this field blank.</span></span>
    - <span data-ttu-id="91382-170">**Código de directiva**: este campo vincula la plantilla de reabastecimiento con una directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="91382-170">**Directive code:** This field links the replenishment template with a location directive.</span></span> <span data-ttu-id="91382-171">Seleccione el código de la directiva de datos de demostración que creó anteriormente (_Reabastecimiento de zona_).</span><span class="sxs-lookup"><span data-stu-id="91382-171">Select the demo data directive code that you created earlier (_Zone replen_).</span></span>
    - <span data-ttu-id="91382-172">**Plantilla de trabajo**: deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="91382-172">**Work template:** Leave this field blank.</span></span>
    - <span data-ttu-id="91382-173">**Cantidad mínima:** Este campo establece la cantidad a la que se desencadenará el reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="91382-173">**Minimum quantity:** This field sets the quantity that replenishment will be triggered at.</span></span> <span data-ttu-id="91382-174">Introduzca _50_.</span><span class="sxs-lookup"><span data-stu-id="91382-174">Enter _50_.</span></span>
    - <span data-ttu-id="91382-175">**Cantidad máxima:** Este campo establece la cantidad máxima de un artículo que puede estar presente en una zona.</span><span class="sxs-lookup"><span data-stu-id="91382-175">**Maximum quantity:** This field sets the maximum quantity of an item that can be present in a zone.</span></span> <span data-ttu-id="91382-176">El trabajo de reabastecimiento generado aumentará el inventario a esta cantidad.</span><span class="sxs-lookup"><span data-stu-id="91382-176">Generated replenishment work will increase inventory to this quantity.</span></span> <span data-ttu-id="91382-177">Introduzca _150_.</span><span class="sxs-lookup"><span data-stu-id="91382-177">Enter _150_.</span></span>
    - <span data-ttu-id="91382-178">**Unidad:** Este campo establece la unidad para los valores mínimo y máximo.</span><span class="sxs-lookup"><span data-stu-id="91382-178">**Unit:** This field sets the unit for the minimum and maximum values.</span></span> <span data-ttu-id="91382-179">Seleccione _ea_.</span><span class="sxs-lookup"><span data-stu-id="91382-179">Select _ea_.</span></span>
    - <span data-ttu-id="91382-180">**Incremento de la demanda:** Seleccione _Redondear_.</span><span class="sxs-lookup"><span data-stu-id="91382-180">**Demand increment:** Select _Round up_.</span></span>
    - <span data-ttu-id="91382-181">**Reabastecer solo ubicaciones fijas vacías:** marque esta casilla.</span><span class="sxs-lookup"><span data-stu-id="91382-181">**Replenish empty fixed locations:** Select this check box.</span></span>
    - <span data-ttu-id="91382-182">**Reabastecer solo ubicaciones fijas:** desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="91382-182">**Replenish only fixed locations:** Clear this check box.</span></span>
    - <span data-ttu-id="91382-183">**Modo de consulta del producto:** seleccione _Consulta del producto_.</span><span class="sxs-lookup"><span data-stu-id="91382-183">**Product query mode:** Select _Product query_.</span></span>
    - <span data-ttu-id="91382-184">**Alcance del umbral de reabastecimiento:** este campo define si la plantilla debe evaluar por zona o por ubicación específica.</span><span class="sxs-lookup"><span data-stu-id="91382-184">**Replenishment threshold scope:** This field defines whether the template should evaluate by zone or by specific location.</span></span> <span data-ttu-id="91382-185">Seleccione _Zona_.</span><span class="sxs-lookup"><span data-stu-id="91382-185">Select _Zone_.</span></span>
    - <span data-ttu-id="91382-186">**Almacén:** seleccione _61_.</span><span class="sxs-lookup"><span data-stu-id="91382-186">**Warehouse:** Select _61_.</span></span>

1. <span data-ttu-id="91382-187">Seleccione **Seleccionar productos** encima de la cuadrícula **Detalles de plantilla de reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="91382-187">Select **Select products** above the **Replenishment Template Details** grid.</span></span>
1. <span data-ttu-id="91382-188">En el cuadro de diálogo **Consulta de producto**, en la pestaña **Intervalo**, seleccione **Agregar** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="91382-188">In the **Product query** dialog box, on the **Range** tab, select **Add** to add a row to the grid.</span></span>
1. <span data-ttu-id="91382-189">Establezca los siguientes valores en la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="91382-189">In the new row, set the following values:</span></span>

    - <span data-ttu-id="91382-190">**Tabla:** _Artículos_</span><span class="sxs-lookup"><span data-stu-id="91382-190">**Table:** _Items_</span></span>
    - <span data-ttu-id="91382-191">**Tabla derivada:** _Artículos_</span><span class="sxs-lookup"><span data-stu-id="91382-191">**Derived table:** _Items_</span></span>
    - <span data-ttu-id="91382-192">**Campo:** _Número de artículo_</span><span class="sxs-lookup"><span data-stu-id="91382-192">**Field:** _Item number_</span></span>
    - <span data-ttu-id="91382-193">**Criterios**: _A0001_</span><span class="sxs-lookup"><span data-stu-id="91382-193">**Criteria:** _A0001_</span></span>

1. <span data-ttu-id="91382-194">Seleccione **Aceptar** para guardar su consulta y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="91382-194">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="91382-195">Seleccione **Seleccionar zonas para reabastecer** encima de la cuadrícula **Detalles de plantilla de reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="91382-195">Select **Select zones to replenish** above the **Replenishment Template Details** grid.</span></span>
1. <span data-ttu-id="91382-196">En el cuadro de diálogo **Consulta de zona**, en la pestaña **Intervalo**, agregue una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="91382-196">In the **Zone query** dialog box, on the **Range** tab, add a row to the grid.</span></span>
1. <span data-ttu-id="91382-197">Establezca los siguientes valores en la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="91382-197">In the new row, set the following values:</span></span>

    - <span data-ttu-id="91382-198">**Tabla:** _Zona de almacén_</span><span class="sxs-lookup"><span data-stu-id="91382-198">**Table:** _Warehouse zone_</span></span>
    - <span data-ttu-id="91382-199">**Tabla derivada:** _Zona de almacén_</span><span class="sxs-lookup"><span data-stu-id="91382-199">**Derived table:** _Warehouse zone_</span></span>
    - <span data-ttu-id="91382-200">**Campo**: _ID de zona_</span><span class="sxs-lookup"><span data-stu-id="91382-200">**Field:** _Zone ID_</span></span>
    - <span data-ttu-id="91382-201">**Criterios:** _FLOOR_</span><span class="sxs-lookup"><span data-stu-id="91382-201">**Criteria:** _FLOOR_</span></span>

1. <span data-ttu-id="91382-202">Seleccione **Aceptar** para guardar su consulta y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="91382-202">Select **OK** to save your query and close the dialog box.</span></span>

### <a name="set-up-location-directives"></a><span data-ttu-id="91382-203">Configurar directivas de ubicación</span><span class="sxs-lookup"><span data-stu-id="91382-203">Set up location directives</span></span>

<span data-ttu-id="91382-204">A diferencia del reabastecimiento mín./máx. basada en ubicaciones, el reabastecimiento mín./máx. basado en zonas requiere que configure las directivas de ubicación de selección y las directivas de ubicación, porque el sistema evalúa toda la zona en lugar de solo la ubicación de selección para el trabajo de salida.</span><span class="sxs-lookup"><span data-stu-id="91382-204">Unlike location-based min/max replenishment, zone-based min/max replenishment requires that you set up both pick location directives and put location directives, because the system evaluates the whole zone instead of just the pick location for outbound work.</span></span>

#### <a name="view-and-edit-location-directives"></a><span data-ttu-id="91382-205">Ver y editar directivas de ubicación</span><span class="sxs-lookup"><span data-stu-id="91382-205">View and edit location directives</span></span>

<span data-ttu-id="91382-206">Para ver o editar sus directivas de ubicación, vaya a **Gestión de almacenes \> Configuración \> Directivas de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="91382-206">To view or edit your location directives, go to **Warehouse management \> Setup \> Location directives**.</span></span>

<span data-ttu-id="91382-207">Para ver ejemplos que muestran cómo usar la configuración para crear las directivas de ubicación de selección y las directivas de ubicación requeridas, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="91382-207">For examples that show how to use the settings to create the required pick location directives and put location directives, see the next section.</span></span>

#### <a name="prepare-demo-data-location-directives"></a><span data-ttu-id="91382-208">Preparar directivas de ubicación de datos de demostración</span><span class="sxs-lookup"><span data-stu-id="91382-208">Prepare demo data location directives</span></span>

<span data-ttu-id="91382-209">Para preparar datos de demostración para que puedan usarse en el escenario al final de este tema, debe crear dos directivas de ubicación: una para selección y otra para colocación.</span><span class="sxs-lookup"><span data-stu-id="91382-209">To prepare demo data so that it can be used in the scenario at the end of this topic, you must create two location directives: one for pick and one for put.</span></span>

##### <a name="create-a-replenishment-pick-directive"></a><span data-ttu-id="91382-210">Crear una directiva de selección de reabastecimiento</span><span class="sxs-lookup"><span data-stu-id="91382-210">Create a replenishment pick directive</span></span>

1. <span data-ttu-id="91382-211">Seleccione la entidad jurídica **USMF** para trabajar con los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="91382-211">Select the **USMF** legal entity to work with the demo data.</span></span>
1. <span data-ttu-id="91382-212">Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="91382-212">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="91382-213">En el panel izquierdo, establezca el campo **Tipo de orden de trabajo** en _Reabastecimiento_.</span><span class="sxs-lookup"><span data-stu-id="91382-213">In the left pane, set the **Work order type** field to _Replenishment_.</span></span>
1. <span data-ttu-id="91382-214">En el panel de acciones, seleccione **Nuevo** para crear una nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="91382-214">On the Action Pane, select **New** to create a new directive.</span></span>
1. <span data-ttu-id="91382-215">Establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="91382-215">Set the following values:</span></span>

    - <span data-ttu-id="91382-216">**Número de secuencia:** acepte el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="91382-216">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="91382-217">**Nombre:** introduzca _Selección de zona_.</span><span class="sxs-lookup"><span data-stu-id="91382-217">**Name:** Enter _Zone pick_.</span></span>
    - <span data-ttu-id="91382-218">**Tipo de trabajo**: seleccione _Selección_.</span><span class="sxs-lookup"><span data-stu-id="91382-218">**Work type:** Select _Pick_.</span></span>
    - <span data-ttu-id="91382-219">**Sitio:** seleccione _6_.</span><span class="sxs-lookup"><span data-stu-id="91382-219">**Site:** Select _6_.</span></span>
    - <span data-ttu-id="91382-220">**Almacén:** seleccione _61_.</span><span class="sxs-lookup"><span data-stu-id="91382-220">**Warehouse:** Select _61_.</span></span>
    - <span data-ttu-id="91382-221">**Código de directiva:** deje en blanco este campo.</span><span class="sxs-lookup"><span data-stu-id="91382-221">**Directive code:** Leave this field blank.</span></span>
    - <span data-ttu-id="91382-222">**Varios SKU:** establezca esta opción en _No_.</span><span class="sxs-lookup"><span data-stu-id="91382-222">**Multi SKU:** Set this option to _No_.</span></span>

1. <span data-ttu-id="91382-223">Seleccione **Guardar** para crear una directiva que tenga la configuración que ha configurado hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="91382-223">Select **Save** to create a directive that has the settings that you've configured so far.</span></span>
1. <span data-ttu-id="91382-224">En la ficha desplegable **Líneas**, seleccione **Nuevo** para agregar una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="91382-224">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="91382-225">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="91382-225">On the new line, set the following values:</span></span>

    - <span data-ttu-id="91382-226">**Número de secuencia:** Introduzca _1_.</span><span class="sxs-lookup"><span data-stu-id="91382-226">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="91382-227">**Cantidad inicial**: introduzca _0_.</span><span class="sxs-lookup"><span data-stu-id="91382-227">**From quantity:** Enter _0_.</span></span>
    - <span data-ttu-id="91382-228">**Cantidad final**: introduzca _10000000_.</span><span class="sxs-lookup"><span data-stu-id="91382-228">**To quantity:** Enter _10000000_.</span></span>
    - <span data-ttu-id="91382-229">**Unidad:** deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="91382-229">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="91382-230">**Cantidad para localizar:** seleccione _Ninguna_.</span><span class="sxs-lookup"><span data-stu-id="91382-230">**Locate quantity:** Select _None_.</span></span>
    - <span data-ttu-id="91382-231">**Restringir por unidad:** desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="91382-231">**Restrict by unit:** Clear this check box.</span></span>
    - <span data-ttu-id="91382-232">**Redondear por arriba a unidad:** desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="91382-232">**Round up to unit:** Clear this check box.</span></span>
    - <span data-ttu-id="91382-233">**Localizar cantidad de embalaje:** desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="91382-233">**Locate packing quantity:** Clear this check box.</span></span>
    - <span data-ttu-id="91382-234">**Permitir división:** seleccione esta casilla.</span><span class="sxs-lookup"><span data-stu-id="91382-234">**Allow split:** Select this check box.</span></span>

1. <span data-ttu-id="91382-235">Seleccione **Guardar** para guardar la nueva línea.</span><span class="sxs-lookup"><span data-stu-id="91382-235">Select **Save** to save the new line.</span></span>
1. <span data-ttu-id="91382-236">Mientras su nueva línea aún está seleccionada en la cuadrícula **Líneas**, seleccione **Nuevo** en la ficha desplegable **Acciones de directiva de ubicación** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="91382-236">While your new line is still selected in the **Lines** grid, select **New** on the **Location Directive Actions** FastTab to add a row to the grid.</span></span>
1. <span data-ttu-id="91382-237">Establezca los siguientes valores en la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="91382-237">In the new row, set the following values:</span></span>

    - <span data-ttu-id="91382-238">**Número de secuencia:** Introduzca _1_.</span><span class="sxs-lookup"><span data-stu-id="91382-238">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="91382-239">**Nombre:** introduzca _Seleccionar desde grandes cantidades_.</span><span class="sxs-lookup"><span data-stu-id="91382-239">**Name:** Enter _Pick from bulk_.</span></span>
    - <span data-ttu-id="91382-240">**Uso de ubicación fija:** seleccione _Ubicaciones fijas y no fijas_.</span><span class="sxs-lookup"><span data-stu-id="91382-240">**Fixed location usage:** Select _Fixed and non-fixed locations_.</span></span>
    - <span data-ttu-id="91382-241">**Permitir inventario negativo**: desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="91382-241">**Allow negative inventory:** Clear this check box.</span></span>
    - <span data-ttu-id="91382-242">**Lote habilitado**: desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="91382-242">**Batch enabled:** Clear this check box.</span></span>
    - <span data-ttu-id="91382-243">**Estrategia:** seleccione _Ninguna_.</span><span class="sxs-lookup"><span data-stu-id="91382-243">**Strategy:** Select _None_.</span></span>

1. <span data-ttu-id="91382-244">Seleccione **Guardar** para guardar la nueva acción.</span><span class="sxs-lookup"><span data-stu-id="91382-244">Select **Save** to save the new action.</span></span>
1. <span data-ttu-id="91382-245">Mientras su nueva acción aún está seleccionada, seleccione **Editar consulta** encima de la cuadrícula **Acciones de directiva de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="91382-245">While your new action still selected, select **Edit query** above the **Location Directive Actions** grid.</span></span>
1. <span data-ttu-id="91382-246">Aparece un cuadro de diálogo de consulta, donde puede seleccionar las ubicaciones desde las que reabastecer.</span><span class="sxs-lookup"><span data-stu-id="91382-246">A query dialog box appears, where you can select the locations to replenish from.</span></span> <span data-ttu-id="91382-247">En la pestaña **Intervalo**, seleccione **Nuevo** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="91382-247">On the **Range** tab, select **Add** to add a row to the grid.</span></span>
1. <span data-ttu-id="91382-248">Establezca los siguientes valores en la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="91382-248">In the new row, set the following values:</span></span>

    - <span data-ttu-id="91382-249">**Tabla**: _Ubicaciones_</span><span class="sxs-lookup"><span data-stu-id="91382-249">**Table:** _Locations_</span></span>
    - <span data-ttu-id="91382-250">**Tabla derivada:** _Ubicaciones_</span><span class="sxs-lookup"><span data-stu-id="91382-250">**Derived table:** _Locations_</span></span>
    - <span data-ttu-id="91382-251">**Campo**: _ID de zona_</span><span class="sxs-lookup"><span data-stu-id="91382-251">**Field:** _Zone ID_</span></span>
    - <span data-ttu-id="91382-252">**Criterios**: _BULK_</span><span class="sxs-lookup"><span data-stu-id="91382-252">**Criteria:** _BULK_</span></span>

1. <span data-ttu-id="91382-253">Seleccione **Aceptar** para guardar su consulta y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="91382-253">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="91382-254">Seleccione **Guardar** para guardar su directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="91382-254">Select **Save** to save your location directive.</span></span>

##### <a name="create-a-replenishment-put-directive"></a><span data-ttu-id="91382-255">Crear una directiva de colocación de reabastecimiento</span><span class="sxs-lookup"><span data-stu-id="91382-255">Create a replenishment put directive</span></span>

1. <span data-ttu-id="91382-256">En la página **Directivas de ubicación**, en el panel izquierdo, asegúrese de que el campo **Tipo de orden de trabajo** sigue seleccionado en _Reabastecimiento_.</span><span class="sxs-lookup"><span data-stu-id="91382-256">On the **Location directives** page, in the left pane, make sure that the **Work order type** field is still set to _Replenishment_.</span></span>
1. <span data-ttu-id="91382-257">En el panel de acciones, seleccione **Nuevo** para crear otra nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="91382-257">On the Action Pane, select **New** to create another new directive.</span></span>
1. <span data-ttu-id="91382-258">Establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="91382-258">Set the following values:</span></span>

    - <span data-ttu-id="91382-259">**Número de secuencia:** acepte el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="91382-259">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="91382-260">**Nombre:** introduzca _Colocación de zona_.</span><span class="sxs-lookup"><span data-stu-id="91382-260">**Name:** Enter _Zone put_.</span></span>
    - <span data-ttu-id="91382-261">**Tipo de orden de trabajo:** seleccione _Colocación_.</span><span class="sxs-lookup"><span data-stu-id="91382-261">**Work order type:** Select _Put_.</span></span>
    - <span data-ttu-id="91382-262">**Sitio:** seleccione _6_.</span><span class="sxs-lookup"><span data-stu-id="91382-262">**Site:** Select _6_.</span></span>
    - <span data-ttu-id="91382-263">**Almacén:** seleccione _61_.</span><span class="sxs-lookup"><span data-stu-id="91382-263">**Warehouse:** Select _61_.</span></span>
    - <span data-ttu-id="91382-264">**Código de directiva:** seleccione _Reabastecimiento de zona_ para vincular esta directiva de ubicación a la plantilla de reabastecimiento que creó anteriormente utilizando el código que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="91382-264">**Directive code:** Select _Zone replen_ to link this location directive with the replenishment template that you created earlier by using the code that you created earlier.</span></span>
    - <span data-ttu-id="91382-265">**Varios SKU:** establezca esta opción en _No_.</span><span class="sxs-lookup"><span data-stu-id="91382-265">**Multi SKU:** Set this option to _No_.</span></span>

1. <span data-ttu-id="91382-266">Seleccione **Guardar** para crear una directiva que tenga la configuración que ha configurado hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="91382-266">Select **Save** to create a directive that has the settings that you've configured so far.</span></span>
1. <span data-ttu-id="91382-267">En la ficha desplegable **Líneas**, seleccione **Nuevo** para agregar una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="91382-267">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="91382-268">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="91382-268">On the new line, set the following values:</span></span>

    - <span data-ttu-id="91382-269">**Número de secuencia:** Introduzca _1_.</span><span class="sxs-lookup"><span data-stu-id="91382-269">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="91382-270">**Cantidad inicial**: introduzca _0_.</span><span class="sxs-lookup"><span data-stu-id="91382-270">**From quantity:** Enter _0_.</span></span>
    - <span data-ttu-id="91382-271">**Cantidad final**: introduzca _10000000_.</span><span class="sxs-lookup"><span data-stu-id="91382-271">**To quantity:** Enter _10000000_.</span></span>
    - <span data-ttu-id="91382-272">**Unidad:** deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="91382-272">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="91382-273">**Cantidad para localizar:** seleccione _Ninguna_.</span><span class="sxs-lookup"><span data-stu-id="91382-273">**Locate quantity:** Select _None_.</span></span>
    - <span data-ttu-id="91382-274">**Restringir por unidad:** desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="91382-274">**Restrict by unit:** Clear this check box.</span></span>
    - <span data-ttu-id="91382-275">**Redondear por arriba a unidad:** desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="91382-275">**Round up to unit:** Clear this check box.</span></span>
    - <span data-ttu-id="91382-276">**Localizar cantidad de embalaje:** desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="91382-276">**Locate packing quantity:** Clear this check box.</span></span>
    - <span data-ttu-id="91382-277">**Permitir división:** seleccione esta casilla.</span><span class="sxs-lookup"><span data-stu-id="91382-277">**Allow split:** Select this check box.</span></span>

1. <span data-ttu-id="91382-278">Seleccione **Guardar** para guardar la nueva línea.</span><span class="sxs-lookup"><span data-stu-id="91382-278">Select **Save** to save the new line.</span></span>
1. <span data-ttu-id="91382-279">Mientras su nueva línea aún está seleccionada en la cuadrícula **Líneas**, seleccione **Nuevo** en la ficha desplegable **Acciones de directiva de ubicación** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="91382-279">While your new line is still selected in the **Lines** grid, select **New** on the **Location Directive Actions** FastTab to add a row to the grid.</span></span>
1. <span data-ttu-id="91382-280">Establezca los siguientes valores en la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="91382-280">In the new row, set the following values:</span></span>

    - <span data-ttu-id="91382-281">**Número de secuencia:** Introduzca _1_.</span><span class="sxs-lookup"><span data-stu-id="91382-281">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="91382-282">**Nombre:** introduzca _Colocación de zona_.</span><span class="sxs-lookup"><span data-stu-id="91382-282">**Name:** Enter _Zone put_.</span></span>
    - <span data-ttu-id="91382-283">**Uso de ubicación fija:** seleccione _Ubicaciones fijas y no fijas_.</span><span class="sxs-lookup"><span data-stu-id="91382-283">**Fixed location usage:** Select _Fixed and non-fixed locations_.</span></span>
    - <span data-ttu-id="91382-284">**Permitir inventario negativo**: desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="91382-284">**Allow negative inventory:** Clear this check box.</span></span>
    - <span data-ttu-id="91382-285">**Lote habilitado**: desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="91382-285">**Batch enabled:** Clear this check box.</span></span>
    - <span data-ttu-id="91382-286">**Estrategia:** seleccione _Consolidar_.</span><span class="sxs-lookup"><span data-stu-id="91382-286">**Strategy:** Select _Consolidate_.</span></span>

1. <span data-ttu-id="91382-287">Seleccione **Guardar** para guardar la nueva acción.</span><span class="sxs-lookup"><span data-stu-id="91382-287">Select **Save** to save the new action.</span></span>
1. <span data-ttu-id="91382-288">Mientras su nueva acción aún está seleccionada, seleccione **Editar consulta** encima de la cuadrícula **Acciones de directiva de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="91382-288">While your new action is still selected, select **Edit query** above the **Location Directive Actions** grid.</span></span>
1. <span data-ttu-id="91382-289">Aparece un cuadro de diálogo de consulta, donde puede seleccionar la zona a la que reabastecer.</span><span class="sxs-lookup"><span data-stu-id="91382-289">A query dialog box appears, where you can select the zone to replenish to.</span></span> <span data-ttu-id="91382-290">Esta zona debe ser la misma zona que se especifica en la plantilla de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="91382-290">This zone should be the same zone that is specified in the replenishment template.</span></span> <span data-ttu-id="91382-291">En la pestaña **Intervalo**, seleccione **Nuevo** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="91382-291">On the **Range** tab, select **Add** to add a row to the grid.</span></span>
1. <span data-ttu-id="91382-292">Establezca los siguientes valores en la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="91382-292">In the new row, set the following values:</span></span>

    - <span data-ttu-id="91382-293">**Tabla**: _Ubicaciones_</span><span class="sxs-lookup"><span data-stu-id="91382-293">**Table:** _Locations_</span></span>
    - <span data-ttu-id="91382-294">**Tabla derivada:** _Ubicaciones_</span><span class="sxs-lookup"><span data-stu-id="91382-294">**Derived table:** _Locations_</span></span>
    - <span data-ttu-id="91382-295">**Campo**: _ID de zona_</span><span class="sxs-lookup"><span data-stu-id="91382-295">**Field:** _Zone ID_</span></span>
    - <span data-ttu-id="91382-296">**Criterios:** _FLOOR_</span><span class="sxs-lookup"><span data-stu-id="91382-296">**Criteria:** _FLOOR_</span></span>

1. <span data-ttu-id="91382-297">Seleccione **Aceptar** para guardar su consulta y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="91382-297">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="91382-298">Seleccione **Guardar** para guardar su directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="91382-298">Select **Save** to save your location directive.</span></span>

## <a name="scenario"></a><span data-ttu-id="91382-299">Situación</span><span class="sxs-lookup"><span data-stu-id="91382-299">Scenario</span></span>

<span data-ttu-id="91382-300">En esta sección se proporciona un escenario de muestra que expone cómo trabajar con la característica.</span><span class="sxs-lookup"><span data-stu-id="91382-300">This section provides a sample scenario that shows how to work with the feature.</span></span>

### <a name="prepare-the-sample-data-that-is-required-for-the-sample-scenario"></a><span data-ttu-id="91382-301">Preparar los datos de muestra necesarios para el escenario de muestra</span><span class="sxs-lookup"><span data-stu-id="91382-301">Prepare the sample data that is required for the sample scenario</span></span>

<span data-ttu-id="91382-302">Antes de empezar a trabajar en el escenario, debe activar los datos de muestra y configurar la característica como se describe en esta sección y en las secciones anteriores de este tema.</span><span class="sxs-lookup"><span data-stu-id="91382-302">Before you start to work through the scenario, you must activate sample data and set up the feature as described in this section and in the previous sections of this topic.</span></span>

#### <a name="use-the-usmf-legal-entity"></a><span data-ttu-id="91382-303">Usar la entidad jurídica USMF</span><span class="sxs-lookup"><span data-stu-id="91382-303">Use the USMF legal entity</span></span>

<span data-ttu-id="91382-304">Para trabajar en el escenario mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) estándar.</span><span class="sxs-lookup"><span data-stu-id="91382-304">To work through the scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="91382-305">Además, también debe seleccionar la entidad legal **USMF** antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="91382-305">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

#### <a name="prepare-additional-sample-data"></a><span data-ttu-id="91382-306">Preparar datos de muestra adicionales</span><span class="sxs-lookup"><span data-stu-id="91382-306">Prepare additional sample data</span></span>

<span data-ttu-id="91382-307">Después de haber seleccionado la entidad jurídica **USMF**, agregue los datos de muestra adicionales que se requieren, como se describe en la sección [Configurar reabastecimiento basado en zonas](#setup) que aparece anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="91382-307">After you've selected the **USMF** legal entity, add the additional sample data that is required, as described in the [Set up zone-based replenishment](#setup) section earlier in this topic.</span></span>

#### <a name="check-your-on-hand-inventory"></a><span data-ttu-id="91382-308">Comprobar el inventario disponible</span><span class="sxs-lookup"><span data-stu-id="91382-308">Check your on-hand inventory</span></span>

<span data-ttu-id="91382-309">Siga estos pasos para asegurarse de que su sistema incluya suficiente inventario para admitir el escenario de muestra.</span><span class="sxs-lookup"><span data-stu-id="91382-309">Follow these steps to make sure that your system includes enough inventory to support the sample scenario.</span></span>

1. <span data-ttu-id="91382-310">Asegúrese de que haya inventario disponible para el artículo *A0001* en dos ubicaciones diferentes en la zona de selección (*FLOOR*) que se especifica en la plantilla de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="91382-310">Make sure that there is on-hand inventory for item *A0001* at two different locations in the pick zone (*FLOOR*) that is specified in the replenishment template.</span></span> <span data-ttu-id="91382-311">Sin embargo, el inventario total debe ser inferior a la cantidad mínima requerida (*50*) que se especifica en la plantilla de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="91382-311">However, the total inventory should be less than the required minimum quantity (*50*) that is specified on the replenishment template.</span></span> <span data-ttu-id="91382-312">De esta manera, puede simular cómo se realiza el cálculo para toda la zona en lugar de solo para una única ubicación.</span><span class="sxs-lookup"><span data-stu-id="91382-312">In this way, you can simulate how the calculation occurs for the whole zone instead of just for a single location.</span></span> <span data-ttu-id="91382-313">**Utilice cualquiera de los procesos del almacén para ajustar el inventario según sea necesario.**</span><span class="sxs-lookup"><span data-stu-id="91382-313">**Use any of the warehouse processes to adjust inventory as required.**</span></span>
1. <span data-ttu-id="91382-314">Asegúrese de que haya suficiente inventario para el artículo *A0001* en una ubicación de almacenaje que se especifica en la directiva de ubicación de selección de zona donde el trabajo de reabastecimiento debe seleccionar los artículos del id. de zona *BULK*.</span><span class="sxs-lookup"><span data-stu-id="91382-314">Make sure that there is enough inventory for item *A0001* at a bulk location that is specified in the zone pick location directive where the replenishment work should pick the items from zone ID *BULK*.</span></span> <span data-ttu-id="91382-315">El inventario total debe ser superior a la cantidad máxima requerida (*150*) que se especifica en la plantilla de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="91382-315">The total inventory must be more than the required maximum quantity (*150*) that is specified in the replenishment template.</span></span>
1. <span data-ttu-id="91382-316">Opcional pero recomendado: siga estos pasos para crear un diario de ajuste de inventario:</span><span class="sxs-lookup"><span data-stu-id="91382-316">Optional but recommended: Follow these steps to create an inventory adjustment journal:</span></span>

    1. <span data-ttu-id="91382-317">Vaya a **Gestión del inventario \> Movimientos de diario \> Artículos \> Ajuste de inventario**.</span><span class="sxs-lookup"><span data-stu-id="91382-317">Go to **Inventory management \> Journal entries \> Items \> Inventory adjustment**.</span></span>
    1. <span data-ttu-id="91382-318">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="91382-318">Select **New**.</span></span>
    1. <span data-ttu-id="91382-319">En el cuadro de diálogo **Crear diario de inventario**, en el campo **Almacén**, seleccione *61*.</span><span class="sxs-lookup"><span data-stu-id="91382-319">In the **Create inventory journal** dialog box, in the **Warehouse** field, select *61*.</span></span>
    1. <span data-ttu-id="91382-320">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="91382-320">Select **OK**.</span></span>
    1. <span data-ttu-id="91382-321">En la ficha desplegable **Líneas de diario**, use el botón **Nuevo** para agregar tres líneas a la cuadrícula y establecer los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="91382-321">On the **Journal lines** FastTab, use the **New** button to add three lines to the grid, and set the following values.</span></span> <span data-ttu-id="91382-322">Una vez que haya terminado de configurar cada línea, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="91382-322">After you've finished setting up each line, select **Save**.</span></span>

        - <span data-ttu-id="91382-323">**Línea 1:**</span><span class="sxs-lookup"><span data-stu-id="91382-323">**Line 1:**</span></span>

            - <span data-ttu-id="91382-324">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="91382-324">**Item number:** *A0001*</span></span>
            - <span data-ttu-id="91382-325">**Sitio**: *6*</span><span class="sxs-lookup"><span data-stu-id="91382-325">**Site:** *6*</span></span>
            - <span data-ttu-id="91382-326">**Almacén**: *61*</span><span class="sxs-lookup"><span data-stu-id="91382-326">**Warehouse:** *61*</span></span>
            - <span data-ttu-id="91382-327">**Ubicación:** *02A01R1S1B*</span><span class="sxs-lookup"><span data-stu-id="91382-327">**Location:** *02A01R1S1B*</span></span>
            - <span data-ttu-id="91382-328">**Matrícula:** seleccione una matrícula existente en la lista o cree una nueva matrícula.</span><span class="sxs-lookup"><span data-stu-id="91382-328">**License plate:** Select an existing license plate in the list, or create a new license plate.</span></span>
            - <span data-ttu-id="91382-329">**Cantidad:** *1000*</span><span class="sxs-lookup"><span data-stu-id="91382-329">**Quantity:** *1000*</span></span>

        - <span data-ttu-id="91382-330">**Línea 2:**</span><span class="sxs-lookup"><span data-stu-id="91382-330">**Line 2:**</span></span>

            - <span data-ttu-id="91382-331">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="91382-331">**Item number:** *A0001*</span></span>
            - <span data-ttu-id="91382-332">**Sitio**: *6*</span><span class="sxs-lookup"><span data-stu-id="91382-332">**Site:** *6*</span></span>
            - <span data-ttu-id="91382-333">**Almacén**: *61*</span><span class="sxs-lookup"><span data-stu-id="91382-333">**Warehouse:** *61*</span></span>
            - <span data-ttu-id="91382-334">**Ubicación:** *07A01R2S1B*</span><span class="sxs-lookup"><span data-stu-id="91382-334">**Location:** *07A01R2S1B*</span></span>
            - <span data-ttu-id="91382-335">**Matrícula:** seleccione una matrícula existente en la lista o cree una nueva matrícula.</span><span class="sxs-lookup"><span data-stu-id="91382-335">**License plate:** Select an existing license plate in the list, or create a new license plate.</span></span>
            - <span data-ttu-id="91382-336">**Cantidad:** *15*</span><span class="sxs-lookup"><span data-stu-id="91382-336">**Quantity:** *15*</span></span>

        - <span data-ttu-id="91382-337">**Línea 3:**</span><span class="sxs-lookup"><span data-stu-id="91382-337">**Line 3:**</span></span>

            - <span data-ttu-id="91382-338">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="91382-338">**Item number:** *A0001*</span></span>
            - <span data-ttu-id="91382-339">**Sitio**: *6*</span><span class="sxs-lookup"><span data-stu-id="91382-339">**Site:** *6*</span></span>
            - <span data-ttu-id="91382-340">**Almacén**: *61*</span><span class="sxs-lookup"><span data-stu-id="91382-340">**Warehouse:** *61*</span></span>
            - <span data-ttu-id="91382-341">**Ubicación:** *07A01R1S1B*</span><span class="sxs-lookup"><span data-stu-id="91382-341">**Location:** *07A01R1S1B*</span></span>
            - <span data-ttu-id="91382-342">**Matrícula:** seleccione una matrícula existente en la lista o cree una nueva matrícula.</span><span class="sxs-lookup"><span data-stu-id="91382-342">**License plate:** Select an existing license plate in the list, or create a new license plate.</span></span>
            - <span data-ttu-id="91382-343">**Cantidad:** *10*</span><span class="sxs-lookup"><span data-stu-id="91382-343">**Quantity:** *10*</span></span>

    1. <span data-ttu-id="91382-344">En el panel de acciones, seleccione **Validar**.</span><span class="sxs-lookup"><span data-stu-id="91382-344">On the Action Pane, select **Validate**.</span></span> <span data-ttu-id="91382-345">Corrija los errores que se encuentren antes de avanzar al siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="91382-345">Address any errors that are found before you move on to the next step.</span></span>
    1. <span data-ttu-id="91382-346">En el panel de acciones, seleccione **Registrar** para registrar el inventario en el almacén.</span><span class="sxs-lookup"><span data-stu-id="91382-346">On the Action Pane, select **Post** to post the inventory to the warehouse.</span></span>

### <a name="sample-scenario-run-zone-based-minmax-replenishment"></a><span data-ttu-id="91382-347">Escenario de muestra: Ejecutar reabastecimiento mín./máx. basado en zonas</span><span class="sxs-lookup"><span data-stu-id="91382-347">Sample scenario: Run zone-based min/max replenishment</span></span>

<span data-ttu-id="91382-348">Una vez que todos los datos de muestra de requisitos previos estén en su lugar, puede desencadenar el reabastecimiento siguiendo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="91382-348">After all the prerequisite sample data is in place, you can trigger replenishment by following these steps.</span></span>

1. <span data-ttu-id="91382-349">Vaya a **Gestión de almacenes \> Reabastecimiento \> Reabastecimientos**.</span><span class="sxs-lookup"><span data-stu-id="91382-349">Go to **Warehouse management \> Replenishment \> Replenishments**.</span></span>
1. <span data-ttu-id="91382-350">En el cuadro de diálogo **Reabastecimiento**, en la ficha desplegable **Registros a incluir**, seleccione **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="91382-350">In the **Replenishment** dialog box, on the **Records to include** FastTab, select **Filter**.</span></span>
1. <span data-ttu-id="91382-351">En el cuadro de diálogo **Consulta**, en la pestaña **Intervalo**, edite la fila de la tabla predeterminada de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="91382-351">In the **Inquiry** dialog box, on the **Range** tab, edit the default table row in the following way:</span></span>

    - <span data-ttu-id="91382-352">**Tabla:** seleccione _Plantillas de reabastecimiento_.</span><span class="sxs-lookup"><span data-stu-id="91382-352">**Table:** Select _Replenishment templates_.</span></span>
    - <span data-ttu-id="91382-353">**Tabla derivada:** seleccione _Plantillas de reabastecimiento_.</span><span class="sxs-lookup"><span data-stu-id="91382-353">**Derived table:** Select _Replenishment templates_.</span></span>
    - <span data-ttu-id="91382-354">**Campo:** seleccione _Plantilla de reabastecimiento_.</span><span class="sxs-lookup"><span data-stu-id="91382-354">**Field:** Select _Replenishment template_.</span></span>
    - <span data-ttu-id="91382-355">**Criterios:** seleccione _Reabastecimiento mín./máx. de zonas_.</span><span class="sxs-lookup"><span data-stu-id="91382-355">**Criteria:** Select _Zone min/max replen_.</span></span> <span data-ttu-id="91382-356">Esta plantilla de reabastecimiento es la plantilla de reabastecimiento que creó mientras preparaba los datos de demostración para este escenario.</span><span class="sxs-lookup"><span data-stu-id="91382-356">This replenishment template is the replenishment template that you created while you were preparing the demo data for this scenario.</span></span>

1. <span data-ttu-id="91382-357">Seleccione **Aceptar** para guardar la consulta y vuelva al cuadro de diálogo **Reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="91382-357">Select **OK** to save the query and go back to the **Replenishment** dialog box.</span></span>
1. <span data-ttu-id="91382-358">Seleccione **Aceptar** para ejecutar la plantilla de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="91382-358">Select **OK** to run the replenishment template.</span></span>

<span data-ttu-id="91382-359">El trabajo de reabastecimiento ahora se crea para seleccionar el inventario desde la zona *BULK* y reabastecerlo en la zona *FLOOR*.</span><span class="sxs-lookup"><span data-stu-id="91382-359">Replenishment work is now created to pick inventory from the *BULK* zone and replenish it to the *FLOOR* zone.</span></span>

## <a name="notes-and-tips"></a><span data-ttu-id="91382-360">Notas y consejos</span><span class="sxs-lookup"><span data-stu-id="91382-360">Notes and tips</span></span>

<span data-ttu-id="91382-361">Aquí se muestran algunas notas y consejos para trabajar con la característica:</span><span class="sxs-lookup"><span data-stu-id="91382-361">Here are a few notes and tips for working with the feature:</span></span>

- <span data-ttu-id="91382-362">Para configurar el trabajo de reabastecimiento que va a la zona deseada, puede vincular las líneas de la plantilla de reabastecimiento y las directivas de ubicación de cualquiera de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="91382-362">To set up replenishment work that goes to the desired zone, you can link the replenishment template lines and location directives in either of the following ways:</span></span>

    - <span data-ttu-id="91382-363">Edite la consulta del encabezado de la directiva de ubicación y filtre las líneas de la plantilla de reabastecimiento seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="91382-363">Edit the location directive header query, and filter the selected replenishment template lines.</span></span>
    - <span data-ttu-id="91382-364">Utilice un código de directiva en la línea de la plantilla de reabastecimiento, y haga que coincida con la directiva de ubicación de colocación.</span><span class="sxs-lookup"><span data-stu-id="91382-364">Use a directive code on the replenishment template line, and match it to the put location directive.</span></span>

- <span data-ttu-id="91382-365">Si está utilizando ubicaciones dinámicas, se creará un trabajo de reabastecimiento para la primera ubicación disponible o para una ubicación que ya contiene inventario, si la acción de directiva de ubicación está configurada para usar la estrategia **Consolidar**.</span><span class="sxs-lookup"><span data-stu-id="91382-365">If you're using dynamic locations, replenishment work will be created either for the first available location or for a location that already contains inventory, if the location directive action is set up to use the **Consolidate** strategy.</span></span>
- <span data-ttu-id="91382-366">Si utiliza ubicaciones fijas en lugar de zonas, debe usar el [reabastecimiento mín./máx. estándar](tasks/set-up-min-max-replenishment-process.md).</span><span class="sxs-lookup"><span data-stu-id="91382-366">If you're using fixed locations instead of zones, you should use [standard min/max replenishment](tasks/set-up-min-max-replenishment-process.md).</span></span>
