---
title: "Organizar los componentes del informe en el diseñador de informes"
description: "Una vez ha diseñado los bloques de creación y los informes generados, resulta útil organizar estos objetos para que los usuarios los encuentren más fácilmente. En este artículo se explica cómo organizar los informes existentes, los bloques de creación y los objetos en el diseñador de informes."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 59161
ms.assetid: 32e728c5-3b06-4049-8070-ade01e951d49
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 7207febc58dbab1df5551ae0f74ad74d9ced8e56
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="organize-report-components-in-report-designer"></a><span data-ttu-id="46320-104">Organizar los componentes del informe en el diseñador de informes</span><span class="sxs-lookup"><span data-stu-id="46320-104">Organize report components in report designer</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="46320-105">Una vez ha diseñado los bloques de creación y los informes generados, resulta útil organizar estos objetos para que los usuarios los encuentren más fácilmente.</span><span class="sxs-lookup"><span data-stu-id="46320-105">After you've designed building blocks and generated reports, it's helpful to organize these objects so that they are easier for users to locate.</span></span> <span data-ttu-id="46320-106">En este artículo se explica cómo organizar los informes existentes, los bloques de creación y los objetos en el diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="46320-106">This article explains how to organize existing reports, building blocks, and objects in report designer.</span></span>

<span data-ttu-id="46320-107">Puede cambiar el nombre de carpetas, informes, bloques de creación y otros objetos en el diseñador de informes para ayudar a organizar sus archivos.</span><span class="sxs-lookup"><span data-stu-id="46320-107">You can rename folders, reports, building blocks, and other objects in report designer to help organize your files.</span></span> <span data-ttu-id="46320-108">En función del tipo de objeto al que quiere cambiar el nombre, puede que tenga que actualizar las asociaciones con ese objeto.</span><span class="sxs-lookup"><span data-stu-id="46320-108">Depending on the type of object that you rename, you might have to update associations with that object.</span></span>

## <a name="rename-a-folder-or-building-block-in-report-designer"></a><span data-ttu-id="46320-109">Cambiar el nombre de una carpeta o un bloque de creación en el diseñador de informes</span><span class="sxs-lookup"><span data-stu-id="46320-109">Rename a folder or building block in Report Designer</span></span>
<span data-ttu-id="46320-110">En el diseñador de informes, puede cambiar el nombre de carpetas, definiciones de informes, definiciones de columnas y definiciones de organigramas.</span><span class="sxs-lookup"><span data-stu-id="46320-110">In Report Designer, you can rename folders, report definitions, row definitions, column definitions, and reporting tree definitions.</span></span> <span data-ttu-id="46320-111">**Nota:** Al cambiar el nombre de un bloque de creación, debe actualizar las definiciones de informes que utilizan el bloque de creación.</span><span class="sxs-lookup"><span data-stu-id="46320-111">**Note:** When you rename a building block, you must update any reporting definitions that use the building block.</span></span> <span data-ttu-id="46320-112">De lo contrario, no se puede generar un nuevo informe.</span><span class="sxs-lookup"><span data-stu-id="46320-112">Otherwise, a new report can't be generated.</span></span>

### <a name="rename-a-folder-or-building-block-in-report-designer"></a><span data-ttu-id="46320-113">Cambiar el nombre de una carpeta o un bloque de creación en el diseñador de informes</span><span class="sxs-lookup"><span data-stu-id="46320-113">Rename a folder or building block in Report Designer</span></span>

1.  <span data-ttu-id="46320-114">En el diseñador de informes, use el panel de navegación para buscar la carpeta o el objeto a los que desee cambiar el nombre.</span><span class="sxs-lookup"><span data-stu-id="46320-114">In Report Designer, use the navigation pane to locate the folder or object to rename.</span></span>
2.  <span data-ttu-id="46320-115">Haga clic con el botón secundario en la carpeta o en el informe y, a continuación, haga clic en **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="46320-115">Right-click the folder or object, and then click **Rename**.</span></span> <span data-ttu-id="46320-116">El campo **Nombre** en el panel de navegación pasa a estar activo.</span><span class="sxs-lookup"><span data-stu-id="46320-116">The **Name** field in the navigation pane becomes available.</span></span>
3.  <span data-ttu-id="46320-117">Escriba un nuevo nombre y luego presione Intro.</span><span class="sxs-lookup"><span data-stu-id="46320-117">Type a new name, and then press Enter.</span></span>
4.  <span data-ttu-id="46320-118">Si el bloque de creación es una definición de fila, definición de columna o definición de organigrama, debe actualizar otros bloques de creación asociados a él.</span><span class="sxs-lookup"><span data-stu-id="46320-118">If the building block is a row definition, column definition, or reporting tree definition, you must update other building blocks that are associated with it.</span></span> <span data-ttu-id="46320-119">Haga clic con el botón secundario en el bloque de creación al que le cambió el nombre en el paso 3, seleccione **Asociaciones** y, a continuación seleccione un elemento en la lista para actualizarlo.</span><span class="sxs-lookup"><span data-stu-id="46320-119">Right-click the building block that you renamed in step 3, select **Associations**, and then select an item in the list to update it.</span></span>
5.  <span data-ttu-id="46320-120">Repita el paso 4 hasta que todos los elementos asociados se actualizan.</span><span class="sxs-lookup"><span data-stu-id="46320-120">Repeat step 4 until all associated items are updated.</span></span>

## <a name="create-and-manage-report-groups"></a><span data-ttu-id="46320-121">Crear y gestionar grupos de informes</span><span class="sxs-lookup"><span data-stu-id="46320-121">Create and manage report groups</span></span>
<span data-ttu-id="46320-122">Puede agrupar definiciones de informes para generar varios informes al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="46320-122">You can group report definitions to generate multiple reports at the same time.</span></span> <span data-ttu-id="46320-123">Para crear, modificar, eliminar y generar los grupos de informes, debe tener el rol de diseñador o de administrador.</span><span class="sxs-lookup"><span data-stu-id="46320-123">To create, modify, delete, and generate report groups, you must have the designer or administrator role.</span></span> <span data-ttu-id="46320-124">Los usuarios que tienen el rol de generador pueden generar grupos de informes y también pueden modificar la configuración de definiciones de informes del usuario para los grupos de informes.</span><span class="sxs-lookup"><span data-stu-id="46320-124">Users who have the generator role can generate report groups and can also modify the user report definitions setting for report groups.</span></span>

### <a name="create-a-report-group"></a><span data-ttu-id="46320-125">Crear un grupo de informes</span><span class="sxs-lookup"><span data-stu-id="46320-125">Create a report group</span></span>

1.  <span data-ttu-id="46320-126">En el diseñador de informes, en el panel de navegación, haga clic en **Grupos de informes**.</span><span class="sxs-lookup"><span data-stu-id="46320-126">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2.  <span data-ttu-id="46320-127">En el menú **Archivo**, haga clic en **Nuevo** &gt; **Definición de grupo de informes** para abrir un nuevo grupo de informe en la ventana del visor.</span><span class="sxs-lookup"><span data-stu-id="46320-127">On the **File** menu, click **New** &gt; **Report Group Definition** to open a new report group in the viewer window.</span></span> <span data-ttu-id="46320-128">De forma alternativa, haga clic en el botón **Grupo de informes** ![Grupo de informes](https://i-technet.sec.s-msft.com/dynimg/IC679515.gif "Grupo de informes") de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="46320-128">Alternatively, click the **Report Group** button ![Report Group](https://i-technet.sec.s-msft.com/dynimg/IC679515.gif "Report Group") on the toolbar.</span></span>
3.  <span data-ttu-id="46320-129">Haga clic en la pestaña **Grupo de informes**. Para reemplazar la información sobre las definiciones de informes individuales para la generación de este informe, active la casilla **Eliminar la configuración de empresa, detalles y fecha de las definiciones de informes individuales**.</span><span class="sxs-lookup"><span data-stu-id="46320-129">Click the **Report Group** tab. To override the information on the individual report definitions for the generation of this report, select the **Override company, detail, and date settings from individual report definitions** check box.</span></span> <span data-ttu-id="46320-130">La información sobre el nombre de la empresa, el nivel de detalle, la configuración provisional y la fecha se especifica automáticamente, pero puede realizar actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="46320-130">The company name, detail level, provisional setting, and date information are entered automatically, but you can make updates.</span></span>
4.  <span data-ttu-id="46320-131">Para generar varios informes que muestren las divisas de notificación, active la casilla **Incluir todas las divisas de notificación**.</span><span class="sxs-lookup"><span data-stu-id="46320-131">To generate multiple reports that show the reporting currencies, select the **Include all reporting currencies** check box.</span></span> <span data-ttu-id="46320-132">A continuación, para obtener acceso a varias vistas, haga clic en el botón **Divisa** en el visor de la web al ver el informe.</span><span class="sxs-lookup"><span data-stu-id="46320-132">You can then access multiple views by clicking the **Currency** button in the Web Viewer when you view the report.</span></span>
5.  <span data-ttu-id="46320-133">En el campo **Informes en grupo**, haga clic en **Agregar** para seleccionar los informes que se incluirán en el grupo de informes.</span><span class="sxs-lookup"><span data-stu-id="46320-133">In the **Reports in group** field, click **Add** to select the reports to include in the report group.</span></span> <span data-ttu-id="46320-134">Para seleccionar varios informes en el cuadro de diálogo **Agregar**, mantenga presionada la tecla Ctrl mientras selecciona los informes.</span><span class="sxs-lookup"><span data-stu-id="46320-134">To select multiple reports in the **Add** dialog box, hold down the Ctrl key while you select reports.</span></span> <span data-ttu-id="46320-135">Cuando haya finalizado de seleccionar informes, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="46320-135">When you've finished selecting reports, click **OK**.</span></span>
6.  <span data-ttu-id="46320-136">Haga clic en **Archivo** &gt; **Guardar** para guardar el nuevo grupo de informes.</span><span class="sxs-lookup"><span data-stu-id="46320-136">Click **File** &gt; **Save** to save the new report group.</span></span>

### <a name="modify-a-report-group"></a><span data-ttu-id="46320-137">Modificar un grupo de informes</span><span class="sxs-lookup"><span data-stu-id="46320-137">Modify a report group</span></span>

1.  <span data-ttu-id="46320-138">En el diseñador de informes, en el panel de navegación, haga clic en **Grupos de informes**.</span><span class="sxs-lookup"><span data-stu-id="46320-138">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2.  <span data-ttu-id="46320-139">Haga doble clic en el grupo de informes para modificarlo.</span><span class="sxs-lookup"><span data-stu-id="46320-139">Double-click the report group to modify.</span></span>
3.  <span data-ttu-id="46320-140">En la pestaña **Grupo de informes**, realice los cambios que desee.</span><span class="sxs-lookup"><span data-stu-id="46320-140">On the **Report Group** tab, make the changes that you want.</span></span>
4.  <span data-ttu-id="46320-141">En el menú **Archivo**, haga clic en **Guardar** para guardar el grupo de informes modificado. De forma alternativa, haga clic en el botón **Guardar** ![Guardar](https://i-technet.sec.s-msft.com/dynimg/IC679516.gif "Guardar") de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="46320-141">On the **File** menu, click **Save** to save the modified report group, Alternatively, click the **Save** button ![Save](https://i-technet.sec.s-msft.com/dynimg/IC679516.gif "Save") on the toolbar.</span></span>

<span data-ttu-id="46320-142">**Note:** Si ha programado informes para que se generen en intervalos definidos, puede anular esos ajustes y generar un informe inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="46320-142">**Note:** If you've scheduled reports so that they are generated at set intervals, you can override those settings and generate a report immediately.</span></span>

### <a name="generate-a-report-group-report"></a><span data-ttu-id="46320-143">Generar un informe del grupo de informes</span><span class="sxs-lookup"><span data-stu-id="46320-143">Generate a report group report</span></span>

1.  <span data-ttu-id="46320-144">En el diseñador de informes, en el panel de navegación, haga clic en **Grupos de informes**.</span><span class="sxs-lookup"><span data-stu-id="46320-144">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2.  <span data-ttu-id="46320-145">Abra el grupo de informes que desea generar.</span><span class="sxs-lookup"><span data-stu-id="46320-145">Open the report group to generate.</span></span>
3.  <span data-ttu-id="46320-146">Haga clic en el botón **Generar informe** ![Generar informe](https://i-technet.sec.s-msft.com/dynimg/IC679517.gif "Generar informe") para generar informes.</span><span class="sxs-lookup"><span data-stu-id="46320-146">Click the **Generate Report** button ![Generate Report](https://i-technet.sec.s-msft.com/dynimg/IC679517.gif "Generate Report") to generate reports.</span></span>

### <a name="delete-a-report-group"></a><span data-ttu-id="46320-147">Eliminar un grupo de informes</span><span class="sxs-lookup"><span data-stu-id="46320-147">Delete a report group</span></span>

1.  <span data-ttu-id="46320-148">En el diseñador de informes, en el panel de navegación, haga clic en **Grupos de informes**.</span><span class="sxs-lookup"><span data-stu-id="46320-148">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2.  <span data-ttu-id="46320-149">Haga clic con el botón secundario en el grupo de informes para eliminarlo y, a continuación, seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="46320-149">Right-click the report group to delete, and then select **Delete**.</span></span>
3.  <span data-ttu-id="46320-150">Cuando aparezca un mensaje de confirmación, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="46320-150">When a confirmation message appears, click **Yes**.</span></span>

## <a name="report-group-tab-controls"></a><span data-ttu-id="46320-151">Controles de la pestaña Grupo de informes</span><span class="sxs-lookup"><span data-stu-id="46320-151">Report Group tab controls</span></span>
<span data-ttu-id="46320-152">En la tabla siguiente se describen los controles de la pestaña **Grupo de informes**.</span><span class="sxs-lookup"><span data-stu-id="46320-152">The following table describes the controls on the **Report Group** tab.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46320-153">Control</span><span class="sxs-lookup"><span data-stu-id="46320-153">Control</span></span></th>
<th><span data-ttu-id="46320-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="46320-154">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="46320-155">Anular las configuraciones de la empresa, detalles y fecha de definiciones de informes individuales</span><span class="sxs-lookup"><span data-stu-id="46320-155">Override company, detail, and date settings from individual report definitions</span></span></td>
<td><span data-ttu-id="46320-156">Active esta casilla para anular las definiciones de informes individuales de los informes de este grupo de informes para la generación de estos informes solo.</span><span class="sxs-lookup"><span data-stu-id="46320-156">Select this check box to override individual report definitions of the reports in this report group for the generation of these reports only.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="46320-157">Nombre de empresa</span><span class="sxs-lookup"><span data-stu-id="46320-157">Company name</span></span></td>
<td><span data-ttu-id="46320-158">Seleccione la empresa que desee usar para los informes.</span><span class="sxs-lookup"><span data-stu-id="46320-158">Select the company to use for the reports.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="46320-159">Nivel de detalle</span><span class="sxs-lookup"><span data-stu-id="46320-159">Detail level</span></span></td>
<td><span data-ttu-id="46320-160">Especifique el nivel de detalle que incluyen los informes.</span><span class="sxs-lookup"><span data-stu-id="46320-160">Specify the level of detail that the reports include.</span></span>
<ul>
<li><span data-ttu-id="46320-161"><strong>Financiero</strong>: informe de resumen de alto nivel.</span><span class="sxs-lookup"><span data-stu-id="46320-161"><strong>Financial</strong> − A high-level summary report.</span></span> <span data-ttu-id="46320-162">No puede explorar en profundidad las cuentas y dimensiones, salvo las cuentas y dimensiones que se han agregado a través de un organigrama.</span><span class="sxs-lookup"><span data-stu-id="46320-162">You can&#39;t drill down to accounts and dimensions, except for those accounts and dimensions that have been added through a reporting tree.</span></span></li>
<li><span data-ttu-id="46320-163"><strong>Financiero y contable</strong>: un informe que contiene un resumen de alto nivel y detalles de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="46320-163"><strong>Financial &amp; Account</strong> − A report that contains a high-level summary and account details.</span></span></li>
<li><span data-ttu-id="46320-164"><strong>Financiero, contable y de transacciones</strong>: un informe que contiene un resumen de alto nivel y detalles de transacciones.</span><span class="sxs-lookup"><span data-stu-id="46320-164"><strong>Financial, Account, &amp; Transaction</strong> − A report that contains a high-level summary and transaction details.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="46320-165">Provisional</span><span class="sxs-lookup"><span data-stu-id="46320-165">Provisional</span></span></td>
<td><span data-ttu-id="46320-166">Especifique los tipos de actividad que incluyen los informes.</span><span class="sxs-lookup"><span data-stu-id="46320-166">Specify the types of activity that the reports include.</span></span>
<ul>
<li><span data-ttu-id="46320-167"><strong>Solo actividad registrada:</strong> incluye solo las transacciones y los saldos registrados en los datos financieros.</span><span class="sxs-lookup"><span data-stu-id="46320-167"><strong>Posted activity only</strong> − Include only the transactions and balances that are posted in your financial data.</span></span></li>
<li><span data-ttu-id="46320-168"><strong>Actividad registrada y sin registrar:</strong> incluye todas las transacciones y saldos especificados y registrados en sus datos financieros.</span><span class="sxs-lookup"><span data-stu-id="46320-168"><strong>Posted and unposted activity</strong> − Include all the transactions and balances that are entered and posted in your financial data.</span></span></li>
<li><span data-ttu-id="46320-169"><strong>Solo actividad no registrada:</strong> incluye solo las transacciones especificadas, pero todavía no registradas, en los datos financieros.</span><span class="sxs-lookup"><span data-stu-id="46320-169"><strong>Unposted activity only</strong> − Include only the transactions that are entered, but not yet posted, in your financial data.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="46320-170">Incluir todas las divisas de notificación</span><span class="sxs-lookup"><span data-stu-id="46320-170">Include all reporting currencies</span></span></td>
<td><span data-ttu-id="46320-171">Las divisas de notificación adicionales que se configuran en el sistema de Microsoft Dynamics ERP, aparecen aquí.</span><span class="sxs-lookup"><span data-stu-id="46320-171">Any additional reporting currencies that are configured in your Microsoft Dynamics ERP system are listed here.</span></span> <span data-ttu-id="46320-172">Active esta casilla para generar informes adicionales en las divisas que se indican.</span><span class="sxs-lookup"><span data-stu-id="46320-172">Select this check box to generate additional reports in the currencies that are indicated.</span></span> <span data-ttu-id="46320-173">Para ver estos informes en el Visor web, haga clic en el botón <strong>Divisa</strong> y, a continuación, seleccione una divisa.</span><span class="sxs-lookup"><span data-stu-id="46320-173">To view these reports in the Web Viewer, click the <strong>Currency</strong> button, and then select a currency.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="46320-174">Información sobre fechas que no ha sido guardada con la definición del informe</span><span class="sxs-lookup"><span data-stu-id="46320-174">Date information not saved with report definition</span></span></td>
<td><ul>
<li><span data-ttu-id="46320-175">Periodo base</span><span class="sxs-lookup"><span data-stu-id="46320-175">Base period</span></span></li>
<li><span data-ttu-id="46320-176">Año base</span><span class="sxs-lookup"><span data-stu-id="46320-176">Base year</span></span></li>
<li><span data-ttu-id="46320-177">Período de cobertura</span><span class="sxs-lookup"><span data-stu-id="46320-177">Period covered</span></span></li>
</ul>
<span data-ttu-id="46320-178">Solo la configuración del período de base predeterminado se guarda con la definición del informe.</span><span class="sxs-lookup"><span data-stu-id="46320-178">Only default base period settings are saved with the report definition.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="46320-179">Información sobre fechas que ha sido guardada con la definición del informe</span><span class="sxs-lookup"><span data-stu-id="46320-179">Date information saved with report definition</span></span></td>
<td><ul>
<li><span data-ttu-id="46320-180">Fecha del informe</span><span class="sxs-lookup"><span data-stu-id="46320-180">Report date</span></span></li>
<li><span data-ttu-id="46320-181">Período base predeterminado</span><span class="sxs-lookup"><span data-stu-id="46320-181">Default base period</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="46320-182">Informes en grupo</span><span class="sxs-lookup"><span data-stu-id="46320-182">Reports in group</span></span></td>
<td><span data-ttu-id="46320-183">Agregar, eliminar y reordenar informes en el grupo de informes.</span><span class="sxs-lookup"><span data-stu-id="46320-183">Add, remove, and re-order reports in the report group.</span></span>
<ul>
<li><span data-ttu-id="46320-184">Para agregar definiciones de informe al grupo de informes, haga doble clic en el grupo de informes para abrirlo y luego haga clic en <strong>Agregar</strong>.</span><span class="sxs-lookup"><span data-stu-id="46320-184">To add report definitions to the report group, double-click the report group to open it, and then click <strong>Add</strong>.</span></span> <span data-ttu-id="46320-185">Seleccione los informes que se deben incluir en el grupo de informes y haga clic en <strong>Aceptar</strong>.</span><span class="sxs-lookup"><span data-stu-id="46320-185">Select the reports to include in the report group, and then click <strong>OK</strong>.</span></span></li>
<li><span data-ttu-id="46320-186">Para quitar un informe del grupo de informes, seleccione el informe deseado y haga clic en <strong>Quitar</strong>.</span><span class="sxs-lookup"><span data-stu-id="46320-186">To remove a report from the report group, select it, and then click <strong>Remove</strong>.</span></span></li>
<li><span data-ttu-id="46320-187">Para modificar el orden en que se generan los informes, seleccione un informe en la lista y, a continuación, haga clic en <strong>Mover hacia arriba</strong> o <strong>Mover hacia abajo</strong>.</span><span class="sxs-lookup"><span data-stu-id="46320-187">To modify the order that the reports are generated in, select a report in the list, and then click <strong>Move up</strong> or <strong>Move down</strong>.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a><span data-ttu-id="46320-188">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="46320-188">Additional resources</span></span>
--------

[<span data-ttu-id="46320-189">Informes financieros</span><span class="sxs-lookup"><span data-stu-id="46320-189">Financial reporting</span></span>](financial-reporting-intro.md)




