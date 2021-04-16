---
title: Solucionar problemas de operaciones de inventario
description: Este tema describe cómo solucionar problemas que pueden surgir al trabajar con operaciones de inventario.
author: sherry-zheng
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 24e41e35b3e810c509a16b91fffd1e796ab9d134
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832067"
---
# <a name="troubleshoot-inventory-operations"></a><span data-ttu-id="56858-103">Solucionar problemas de operaciones de inventario</span><span class="sxs-lookup"><span data-stu-id="56858-103">Troubleshoot inventory operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="56858-104">Este tema describe cómo solucionar problemas que pueden surgir al trabajar con operaciones de inventario.</span><span class="sxs-lookup"><span data-stu-id="56858-104">This topic describes how to fix issues that you might encounter while you work with inventory operations.</span></span>

## <a name="i-cant-find-the-workflow-drop-down-dialog-box-for-inventory-journals"></a><span data-ttu-id="56858-105">No encuentro el cuadro de diálogo desplegable "Flujo de trabajo" para los diarios de inventario.</span><span class="sxs-lookup"><span data-stu-id="56858-105">I can't find the "Workflow" drop-down dialog box for inventory journals.</span></span>

### <a name="issue-description"></a><span data-ttu-id="56858-106">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="56858-106">Issue description</span></span>

<span data-ttu-id="56858-107">No encuentra el cuadro de diálogo desplegable **Flujo de trabajo** en la página del diario, o las operaciones de flujo de trabajo relacionadas no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="56858-107">You can't find the **Workflow** drop-down dialog box on the journal page, or related workflow operations aren't available.</span></span>

<span data-ttu-id="56858-108">Este problema puede producirse por tres motivos, como se describe en las siguientes subsecciones.</span><span class="sxs-lookup"><span data-stu-id="56858-108">This issue can occur for three reasons, as described in the following subsections.</span></span>

### <a name="issue-resolution-1"></a><span data-ttu-id="56858-109">Solución del problema 1</span><span class="sxs-lookup"><span data-stu-id="56858-109">Issue resolution 1</span></span>

<span data-ttu-id="56858-110">Si el problema se aplica a todos los usuarios, es posible que se deba a que el flujo de trabajo de aprobación no se ha asignado al nombre del diario.</span><span class="sxs-lookup"><span data-stu-id="56858-110">If the issue applies to all users, it might be occurring because the approval workflow hasn't been assigned to the journal name.</span></span> <span data-ttu-id="56858-111">Para arreglar el problema, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="56858-111">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="56858-112">Vaya a **Gestión del inventario &gt; Configurar &gt; Nombres de diarios &gt; Inventario**.</span><span class="sxs-lookup"><span data-stu-id="56858-112">Go to **Inventory Management &gt; Setup &gt; Journal names &gt; Inventory**.</span></span>
1. <span data-ttu-id="56858-113">En el panel de lista, seleccione un nombre de diario para abrir su configuración.</span><span class="sxs-lookup"><span data-stu-id="56858-113">In the list pane, select a journal name to open its settings.</span></span>
1. <span data-ttu-id="56858-114">En la ficha desplegable **General**, establezca la opción **Flujo de trabajo de aprobación** en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="56858-114">On the **General** FastTab, set the **Approval workflow** option to *Yes*.</span></span> <span data-ttu-id="56858-115">Seleccione **Sí** si se le solicita que confirme el cambio.</span><span class="sxs-lookup"><span data-stu-id="56858-115">If you're prompted to confirm the change, select **Yes**.</span></span>
1. <span data-ttu-id="56858-116">En el campo **Flujo de trabajo**, seleccione el flujo de trabajo que desee usar para el nombre de diario seleccionado.</span><span class="sxs-lookup"><span data-stu-id="56858-116">In the **Workflow** field, select the workflow that you want to use for the selected journal name.</span></span>

### <a name="issue-resolution-2"></a><span data-ttu-id="56858-117">Solución del problema 2</span><span class="sxs-lookup"><span data-stu-id="56858-117">Issue resolution 2</span></span>

<span data-ttu-id="56858-118">Si su flujo de trabajo utiliza código personalizado, pueden surgir problemas después de actualizar el sistema.</span><span class="sxs-lookup"><span data-stu-id="56858-118">If your workflow uses customized code, issues might occur after you upgrade the system.</span></span> <span data-ttu-id="56858-119">Por ejemplo, en el flujo de trabajo del diario, el botón **Enviar** puede aparecer atenuado, por lo que no puede seleccionarlo para aprobar un envío.</span><span class="sxs-lookup"><span data-stu-id="56858-119">For example, in the journal workflow, the **Submit** button might be grayed out so you can't select it to approve a submission.</span></span>

<span data-ttu-id="56858-120">Si el botón **Enviar** está atenuado, es posible que su flujo de trabajo se haya personalizado, lo que significa que el método del flujo de trabajo, `canSubmitToWorkflow()` en `FormDataUtil`, se ha extendido.</span><span class="sxs-lookup"><span data-stu-id="56858-120">If the **Submit** button is grayed out, your workflow might have been customized, which means the method of the workflow, `canSubmitToWorkflow()` in `FormDataUtil`, has been extended.</span></span> <span data-ttu-id="56858-121">Para solucionar este problema, cambie la forma en que amplía el método del `canSubmitToWorkflow()` para usar la estructura en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="56858-121">To fix this issue, change the way that you extend the method of the `canSubmitToWorkflow()` to use the structure in the following example.</span></span>

```xpp
[ExtensionOf(formStr(InventJournalMovement))]
public final class InventJournalMovement_extension
{
    public boolean canSubmitToWorkflow()
    {
        boolean ret = YourLogicOfCanSubmitToWorkflow();

        return ret;
    }
}
```

### <a name="issue-resolution-3"></a><span data-ttu-id="56858-122">Solución del problema 3</span><span class="sxs-lookup"><span data-stu-id="56858-122">Issue resolution 3</span></span>

<span data-ttu-id="56858-123">Si el problema solo se aplica a algunos usuarios específicos, es posible que esos usuarios no tengan los privilegios de seguridad necesarios para ejecutar operaciones de flujo de trabajo en diarios de inventario.</span><span class="sxs-lookup"><span data-stu-id="56858-123">If the issue applies only to a few specific users, those users might not have the security privileges that are required to run workflow operations on inventory journals.</span></span> <span data-ttu-id="56858-124">Compruebe que cada usuario afectado tenga el privilegio de seguridad *Mantener el flujo de trabajo del diario de inventario*.</span><span class="sxs-lookup"><span data-stu-id="56858-124">Verify that each affected user has the *Maintain inventory journal workflow* security privilege.</span></span> <span data-ttu-id="56858-125">De forma predeterminada, este privilegio se asigna a un deber que tiene el mismo nombre, y ese deber se aplica a los roles *Trabajador de almacén* y *Responsable de almacén*.</span><span class="sxs-lookup"><span data-stu-id="56858-125">By default, this privilege is assigned to a duty that has same name, and that duty is applied to the *Warehouse worker* and *Warehouse manager* roles.</span></span>

## <a name="my-inventory-journal-remains-in-system-locked-status-and-the-workflow-batch-job-doesnt-work"></a><span data-ttu-id="56858-126">Mi diario de inventario permanece en el estado bloqueado por el sistema y el trabajo por lotes del flujo de trabajo no funciona.</span><span class="sxs-lookup"><span data-stu-id="56858-126">My inventory journal remains in system-locked status, and the workflow batch job doesn't work.</span></span>

### <a name="issue-description"></a><span data-ttu-id="56858-127">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="56858-127">Issue description</span></span>

<span data-ttu-id="56858-128">Uno de sus diarios de inventario está bloqueado por alguna operación y no se libera.</span><span class="sxs-lookup"><span data-stu-id="56858-128">One of your inventory journals is locked by some operation and isn't being released.</span></span> <span data-ttu-id="56858-129">Por ejemplo, si se produce un error desconocido durante la publicación (que es una operación de bloqueo del sistema), el diario puede permanecer en estado de bloqueado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="56858-129">For example, if an unknown error occurs during posting (which is a system lock operation), the journal might remain in system-locked status.</span></span> <span data-ttu-id="56858-130">En este caso, el controlador de elementos de trabajo de flujo de trabajo generará un error mientras bloquea la validación.</span><span class="sxs-lookup"><span data-stu-id="56858-130">In this case, the workflow work item handler will throw an error while it does lock validation.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="56858-131">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="56858-131">Issue resolution</span></span>

<span data-ttu-id="56858-132">Inicie sesión en la instancia de SQL Server para Supply Chain Management y compruebe si **InventJournalTable.SystemBlocked** se establece en *1*.</span><span class="sxs-lookup"><span data-stu-id="56858-132">Sign in to the SQL Server instance for Supply Chain Management, and check whether **InventJournalTable.SystemBlocked** is set to *1*.</span></span> <span data-ttu-id="56858-133">Si es así, asegúrese de que el diario no esté en estado bloqueado y luego restablezca **InventJournalTable.SystemBlocked** en *0*.</span><span class="sxs-lookup"><span data-stu-id="56858-133">If it is, make sure that the journal should not be in locked status, and then reset **InventJournalTable.SystemBlocked** to *0*.</span></span>

## <a name="my-inventory-journal-workflow-is-never-completed-and-the-journal-cant-be-edited-or-posted"></a><span data-ttu-id="56858-134">El flujo de trabajo de mi diario de inventario nunca se completa y el diario no se puede editar ni publicar.</span><span class="sxs-lookup"><span data-stu-id="56858-134">My inventory journal workflow is never completed, and the journal can't be edited or posted.</span></span>

### <a name="issue-description"></a><span data-ttu-id="56858-135">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="56858-135">Issue description</span></span>

<span data-ttu-id="56858-136">Después de enviar un flujo de trabajo de aprobación de diario, el procesamiento del flujo de trabajo deja de responder y no puede editar ni procesar sus diarios.</span><span class="sxs-lookup"><span data-stu-id="56858-136">After you submit a journal approval workflow, workflow processing stops responding, and you can't edit or process your journals.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="56858-137">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="56858-137">Issue resolution</span></span>

<span data-ttu-id="56858-138">Hay varias razones por las que es posible que no se complete el procesamiento del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="56858-138">There are several reasons why workflow processing might not be completed.</span></span> <span data-ttu-id="56858-139">Compruebe los siguientes problemas:</span><span class="sxs-lookup"><span data-stu-id="56858-139">Check for the following issues:</span></span>

- <span data-ttu-id="56858-140">Vaya a **Gestión de inventarios &gt; Configuración &gt; Flujos de trabajo de gestión de inventario**, y revise la configuración del flujo de trabajo afectado.</span><span class="sxs-lookup"><span data-stu-id="56858-140">Go to **Inventory management &gt; Setup &gt; Inventory management workflows**, and review the configuration of the affected workflow.</span></span> <span data-ttu-id="56858-141">Para obtener más información, consulte [Flujos de trabajo de aprobación de diario de inventario](inventory-journal-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="56858-141">For more information, see [Inventory journal approval workflows](inventory-journal-workflow.md).</span></span>
- <span data-ttu-id="56858-142">Es posible que el flujo de trabajo encuentre una excepción o un error.</span><span class="sxs-lookup"><span data-stu-id="56858-142">The workflow might be encountering an exception or error.</span></span> <span data-ttu-id="56858-143">Revise el historial de elementos de trabajo del flujo de trabajo afectado para ver si incluye un error de aplicación que finaliza el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="56858-143">Review the work item history of the affected workflow to see whether it includes an application error that terminates the workflow.</span></span>
- <span data-ttu-id="56858-144">El diario de inventario se puede actualizar o editar solo si está aprobado.</span><span class="sxs-lookup"><span data-stu-id="56858-144">The inventory journal can be updated or edited only if it's approved.</span></span> <span data-ttu-id="56858-145">Si la recuperación está activa, puede intentar recuperar el diario.</span><span class="sxs-lookup"><span data-stu-id="56858-145">If recall is active, you can try to recall the journal.</span></span> <span data-ttu-id="56858-146">La ejecución del trabajo por lotes del flujo de trabajo puede suspenderse por varios motivos.</span><span class="sxs-lookup"><span data-stu-id="56858-146">Execution of the workflow batch job might be suspended for multiple reasons.</span></span> <span data-ttu-id="56858-147">Algunas de estas razones pueden deberse al problema del marco del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="56858-147">Some of these reasons might be caused by the workflow framework issue.</span></span>

## <a name="inventory-journal-workflow-conditions-apply-only-at-the-journal-level-not-at-the-line-level"></a><span data-ttu-id="56858-148">Las condiciones del flujo de trabajo del diario de inventario solo se aplican a nivel de diario, no a nivel de línea</span><span class="sxs-lookup"><span data-stu-id="56858-148">Inventory journal workflow conditions apply only at the journal level, not at the line level</span></span>

### <a name="issue-description"></a><span data-ttu-id="56858-149">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="56858-149">Issue description</span></span>

<span data-ttu-id="56858-150">Puede experimentar este problema si, por ejemplo, intenta configurar una condición de flujo de trabajo de diario de inventario en el importe del coste.</span><span class="sxs-lookup"><span data-stu-id="56858-150">You might experience this issue if, for example, you try to set up an inventory journal workflow condition on the cost amount.</span></span> <span data-ttu-id="56858-151">Configura la condición para que el paso 1 se ejecute únicamente cuando el importe del coste sea menor que 100.</span><span class="sxs-lookup"><span data-stu-id="56858-151">You set up the condition so that step 1 is run only when the cost amount is less than 100.</span></span> <span data-ttu-id="56858-152">A continuación, configura otra condición para que el paso 2 se ejecute únicamente cuando el importe del coste sea mayor o igual que 100.</span><span class="sxs-lookup"><span data-stu-id="56858-152">You then set up another condition so that step 2 is run only when the cost amount is more than or equal to 100.</span></span> <span data-ttu-id="56858-153">Luego, cuando se ejecuta el flujo de trabajo, el historial de flujo de trabajo muestra solo una línea y la primera condición siempre se evalúa como *verdadero*, independientemente del valor que se envíe.</span><span class="sxs-lookup"><span data-stu-id="56858-153">Then, when the workflow is run, the workflow history shows only one line, and the first condition is always evaluated as *true*, regardless of the value that is submitted.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="56858-154">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="56858-154">Issue workaround</span></span>

<span data-ttu-id="56858-155">En la versión actual, las condiciones del flujo de trabajo de inventario solo se aplican a nivel de diario, no a nivel de línea.</span><span class="sxs-lookup"><span data-stu-id="56858-155">In the current release, inventory workflow conditions apply only at the journal level, not at the line level.</span></span> <span data-ttu-id="56858-156">Este comportamiento se debe al diseño.</span><span class="sxs-lookup"><span data-stu-id="56858-156">This behavior is by design.</span></span> <span data-ttu-id="56858-157">Le recomendamos que establezca sus criterios de condiciones solo en los atributos de nivel de diario.</span><span class="sxs-lookup"><span data-stu-id="56858-157">We recommend that you set your condition criteria only on journal-level attributes.</span></span>

## <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-filter-results-as-i-expect"></a><span data-ttu-id="56858-158">El panel de filtro de la página Lista disponible no filtra los resultados como esperaba.</span><span class="sxs-lookup"><span data-stu-id="56858-158">The filter pane on the On-hand list page doesn't filter results as I expect.</span></span>

### <a name="issue-description"></a><span data-ttu-id="56858-159">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="56858-159">Issue description</span></span>

<span data-ttu-id="56858-160">Los filtros del panel de filtro de la página **Lista disponible** no filtra los resultados como se espera.</span><span class="sxs-lookup"><span data-stu-id="56858-160">The filters in the filter pane on the **On-hand list** page don't filter results as you expect.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="56858-161">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="56858-161">Issue resolution</span></span>

<span data-ttu-id="56858-162">Este comportamiento se debe al diseño.</span><span class="sxs-lookup"><span data-stu-id="56858-162">This behavior is by design.</span></span>

<span data-ttu-id="56858-163">La página  **Lista disponible** se obtiene de una tabla detallada de inventario disponible que incluye todas las dimensiones disponibles.</span><span class="sxs-lookup"><span data-stu-id="56858-163">The **On-hand list** page is assembled from a detailed on-hand inventory table that includes all available dimensions.</span></span> <span data-ttu-id="56858-164">Sin embargo, la lista en esta página es un resumen.</span><span class="sxs-lookup"><span data-stu-id="56858-164">However, the list on this page is a summary.</span></span> <span data-ttu-id="56858-165">Por lo tanto, podría combinar filas de la tabla de origen agregando valores de acuerdo con las dimensiones que se muestran.</span><span class="sxs-lookup"><span data-stu-id="56858-165">Therefore, it might combine rows from the source table by aggregating values according to the dimensions that are shown.</span></span>

<span data-ttu-id="56858-166">Los filtros que se configuran en el panel de filtro se aplican a la tabla de origen, no a la lista agregada.</span><span class="sxs-lookup"><span data-stu-id="56858-166">Filters that are set up in the filter pane apply to the source table, not to the aggregated list.</span></span> <span data-ttu-id="56858-167">Este comportamiento a veces puede conllevar resultados inesperados, como se muestra en [estos ejemplos](inventory-on-hand-list.md#examples).</span><span class="sxs-lookup"><span data-stu-id="56858-167">This behavior can sometimes produce unexpected results, as shown in [these examples](inventory-on-hand-list.md#examples).</span></span>

<span data-ttu-id="56858-168">Sin embargo, los  [filtros que se proporcionan en la cuadrícula](inventory-on-hand-list.md#grid-filters) *sí* se aplican a la lista agregada.</span><span class="sxs-lookup"><span data-stu-id="56858-168">However, the [filters that are provided in the grid](inventory-on-hand-list.md#grid-filters) *do* apply to the aggregated list.</span></span> <span data-ttu-id="56858-169">Estos filtros incluyen tanto el filtro rápido en la parte superior de la cuadrícula como el filtro para cada encabezado de columna.</span><span class="sxs-lookup"><span data-stu-id="56858-169">These filters include both the QuickFilter at the top of the grid and the filter for each column heading.</span></span>

## <a name="the-unit-and-unit-quantity-arent-working-correctly-in-the-inventory-journal"></a><span data-ttu-id="56858-170">La unidad y la cantidad de unidades no funcionan correctamente en el diario de inventario.</span><span class="sxs-lookup"><span data-stu-id="56858-170">The unit and unit quantity aren't working correctly in the inventory journal.</span></span>

### <a name="issue-description"></a><span data-ttu-id="56858-171">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="56858-171">Issue description</span></span>

<span data-ttu-id="56858-172">Puede encontrar uno o ambos de los siguientes problemas cuando trabaja con unidades y cantidades en un diario de inventario:</span><span class="sxs-lookup"><span data-stu-id="56858-172">You might encounter one or both of the following issues when you work with units and quantities in an inventory journal:</span></span>

- <span data-ttu-id="56858-173">No ve unidades o cantidades de unidades en el diario de inventario mientras se configura una unidad de conversión para el producto liberado y no puede cambiar la unidad en el diario de inventario.</span><span class="sxs-lookup"><span data-stu-id="56858-173">You don't see units or unit quantities in the inventory journal while a unit of conversion is set up for the released product, and you can't change the unit in the inventory journal.</span></span>
- <span data-ttu-id="56858-174">Ve los campos **Cantidad** y **Unidad** en el diario de inventario, pero no ve el campo **Cantidad de unidades**.</span><span class="sxs-lookup"><span data-stu-id="56858-174">You see the **Quantity** and **Unit** fields in the inventory journal, but you don't see the **Unit quantity** field.</span></span> <span data-ttu-id="56858-175">Si cambia la unidad, introduce una cantidad y registra el diario, el diario sigue mostrando la unidad de medida original para esa cantidad.</span><span class="sxs-lookup"><span data-stu-id="56858-175">If you change the unit, enter a quantity, and post the journal, the journal still shows the original unit of measurement for that quantity.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="56858-176">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="56858-176">Issue resolution</span></span>

<span data-ttu-id="56858-177">Para arreglar este problema, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="56858-177">To fix this issue, follow these steps.</span></span>

1. <span data-ttu-id="56858-178">En el espacio de trabajo **Administración de características**, asegúrese de que la característica *Uso de unidad de medida y cantidad de unidad en diarios de inventario* está activada.</span><span class="sxs-lookup"><span data-stu-id="56858-178">In the **Feature management** workspace, make sure that the *Using unit of measure and unit quantity in inventory journals* feature is turned on.</span></span> <span data-ttu-id="56858-179">Esta característica agrega los campos **Unidad** y **Cantidad de unidades** al diario.</span><span class="sxs-lookup"><span data-stu-id="56858-179">This feature adds the **Unit** and **Unit quantity** fields to the journal.</span></span>
1. <span data-ttu-id="56858-180">Una vez activada la característica, use los campos **Cantidad**, **Cantidad de unidades** y **Unidad** de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="56858-180">After the feature is turned on, use the **Quantity**, **Unit quantity**, and **Unit** fields in the following way:</span></span>

    - <span data-ttu-id="56858-181">**Cantidad**: especifique la cantidad utilizando la unidad predeterminada que se define para el producto liberado.</span><span class="sxs-lookup"><span data-stu-id="56858-181">**Quantity** – Specify the quantity by using the default unit that is defined for the released product.</span></span> <span data-ttu-id="56858-182">Sin embargo, la unidad predeterminada en sí no se muestra aquí.</span><span class="sxs-lookup"><span data-stu-id="56858-182">However, the default unit itself isn't shown here.</span></span> <span data-ttu-id="56858-183">Si se configura una conversión entre la unidad predeterminada y la unidad seleccionada en el campo **Unidad**, el campo **Cantidad** se actualiza automáticamente, según las selecciones de los campos **Cantidad de unidades** y **Unidad**.</span><span class="sxs-lookup"><span data-stu-id="56858-183">If a conversion is set up between the default unit and the unit that is selected in the **Unit** field, the **Quantity** field is automatically updated, based on the selections in the **Unit quantity** and **Unit** fields.</span></span>
    - <span data-ttu-id="56858-184">**Cantidad de unidades**: especifique la cantidad empleando la unidad de medida seleccionada en el campo **Unidad**.</span><span class="sxs-lookup"><span data-stu-id="56858-184">**Unit quantity** – Specify the quantity by using the unit that is selected in the **Unit** field.</span></span>
    - <span data-ttu-id="56858-185">**Unidad**: seleccione la unidad para aplicar al valor en el campo **Cantidad de unidades**.</span><span class="sxs-lookup"><span data-stu-id="56858-185">**Unit** – Select the unit to apply to the value in the **Unit quantity** field.</span></span>

## <a name="i-receive-the-following-error-message-maximum-number-of-decimals-for-the-stock-keeping-unit-is-0"></a><span data-ttu-id="56858-186">Recibo el siguiente mensaje de error: "El número máximo de decimales para la referencia de almacén es 0".</span><span class="sxs-lookup"><span data-stu-id="56858-186">I receive the following error message: "Maximum number of decimals for the stock keeping unit is 0."</span></span>

### <a name="issue-description"></a><span data-ttu-id="56858-187">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="56858-187">Issue description</span></span>

<span data-ttu-id="56858-188">Al registrar una transacción de inventario o una reserva de inventario, recibe el siguiente mensaje de error: "El número máximo de decimales para la referencia de almacén es 0".</span><span class="sxs-lookup"><span data-stu-id="56858-188">When you try to post an inventory transaction or an inventory reservation, you receive the following error message: "Maximum number of decimals for the stock keeping unit is 0."</span></span>

<span data-ttu-id="56858-189">Este problema se produce cuando la cantidad de la transacción de inventario se especifica como un valor decimal que está por debajo del nivel de precisión que admite el campo.</span><span class="sxs-lookup"><span data-stu-id="56858-189">This issue occurs when the inventory transaction quantity is specified as a decimal value that is below the level of precision that the field supports.</span></span> <span data-ttu-id="56858-190">Por ejemplo, se ha especificado una cantidad de *0,5* para una transacción de inventario, pero solo se admiten cantidades de enteros.</span><span class="sxs-lookup"><span data-stu-id="56858-190">For example, a quantity of *0.5* has been specified for an inventory transaction, but only integer quantities are supported.</span></span> <span data-ttu-id="56858-191">Por lo tanto, el valor debe ser *1* en lugar de *0,5*.</span><span class="sxs-lookup"><span data-stu-id="56858-191">Therefore, the value should be *1* instead of *0.5*.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="56858-192">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="56858-192">Issue resolution</span></span>

1. <span data-ttu-id="56858-193">Ejecute el siguiente script en su instancia de SQL Server para redondear cantidades en las transacciones de inventario.</span><span class="sxs-lookup"><span data-stu-id="56858-193">Run the following script on your SQL Server instance to round quantities in the inventory transactions.</span></span> <span data-ttu-id="56858-194">Este script corregirá valores en la tabla **inventTrans**.</span><span class="sxs-lookup"><span data-stu-id="56858-194">This script will correct values in the **inventTrans** table.</span></span>

    ```sql
    update it set it.QTY = round(it.qty, decimalPrecisionValue) from inventtrans it where it.DATAAREAID='XXXX' and it.PARTITION=XXXXXX and it.qty <> round(it.qty, decimalPrecisionValue) and exists (select 'x' from INVENTTABLEMODULE a, unitofmeasure b where  a.unitid =b.SYMBOL and a.partition=it.partition and a.PARTITION=b.PARTITION and  MODULETYPE =0 and  b.DECIMALPRECISION=decimalPrecisionValue and a.DATAAREAID='XXXX' and a.ITEMID =it.ITEMID and it.DATAAREAID=a.DATAAREAID)
    ```

1. <span data-ttu-id="56858-195">Ejecute una comprobación de coherencia disponible donde la opción **arreglar error** está activada.</span><span class="sxs-lookup"><span data-stu-id="56858-195">Run an on-hand consistency check where the **fix error** option is turned on.</span></span> <span data-ttu-id="56858-196">Esta comprobación corregirá valores en la tabla **inventSum**.</span><span class="sxs-lookup"><span data-stu-id="56858-196">This check will correct values in the **inventSum** table.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="56858-197">Recomendamos encarecidamente que edite cuidadosamente el script según sea necesario para su entorno, lo pruebe en un entorno de prueba y luego compruebe los datos resultantes antes de ejecutar el script en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="56858-197">We strongly recommend that you carefully edit the script as required for your environment, test it in a test environment, and then check the resulting data before you run the script in a production environment.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]