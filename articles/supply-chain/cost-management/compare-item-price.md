---
title: Informe para Comparar precios de almacenamiento de artículos
description: Aprenda a generar un informe para Comparar precios de almacenamiento de artículos y después explorar y/o exportar el resultado.
author: AndersGirke
manager: tfehr
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace, InventItemPriceCompareStorage, InventItemPriceCompareStorageDetailsChart, InventItemPriceCompareStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: f40faa7919e6fb5ce0de2594b3d2f264fe42fa1a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222930"
---
# <a name="compare-item-prices-storage-report"></a><span data-ttu-id="46d6a-103">Informe para Comparar precios de almacenamiento de artículos</span><span class="sxs-lookup"><span data-stu-id="46d6a-103">Compare item prices storage report</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="46d6a-104">Este tema explica cómo ejecutar un informe **Comprar precios de almacenamiento de artículos** y hacer que la salida esté disponible digitalmente, ya sea como una página interactiva en Dynamics 365 Supply Chain Management, o como documento exportado en cualquiera de varios formatos.</span><span class="sxs-lookup"><span data-stu-id="46d6a-104">This topic explains how to run a **Compare item prices storage** report and make the output available digitally, either as an interactive page in Dynamics 365 Supply Chain Management, or as an exported document in any of several formats.</span></span>

<span data-ttu-id="46d6a-105">Cuando vea el informe en su navegador, las columnas y saldos agregados se ajustarán dinámicamente dependiendo de su diseño configurado.</span><span class="sxs-lookup"><span data-stu-id="46d6a-105">When you view the report in your browser, columns and aggregate balances are dynamically adjusted, depending on your configured layout.</span></span> <span data-ttu-id="46d6a-106">Puede ordenar los resultados, filtrarlos, explorarlos en profundidad los datos y más.</span><span class="sxs-lookup"><span data-stu-id="46d6a-106">You can sort the results, filter them, drill down into the data, and more.</span></span>

<span data-ttu-id="46d6a-107">Los resultados del informe se almacenan en la entidad de datos **Comparar precios de artículos**, que le permite filtrar y exportar los resultados a un formato como CSV o Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="46d6a-107">Report results are stored in the **Compare item prices** data entity, which lets you filter and export the results to a format such as CSV or Microsoft Excel.</span></span>

<span data-ttu-id="46d6a-108">El informe **Comparar precios de almacenamiento de artículos** es útil en los casos en que la salida contiene muchas líneas.</span><span class="sxs-lookup"><span data-stu-id="46d6a-108">The **Compare item prices storage** report is helpful in cases where the output contains many lines.</span></span> <span data-ttu-id="46d6a-109">Por ejemplo, la salida contendrá muchas líneas si tiene más de 40.000 artículos con un precio de artículo pendiente en la versión de gestión de costes.</span><span class="sxs-lookup"><span data-stu-id="46d6a-109">For example, the output will contain many lines if you have more than 40,000 items holding a pending item price in the costing version.</span></span>

## <a name="enable-compare-item-prices-storage"></a><span data-ttu-id="46d6a-110">Habilitar comprar precios de almacenamiento de artículos</span><span class="sxs-lookup"><span data-stu-id="46d6a-110">Enable compare item prices storage</span></span>

<span data-ttu-id="46d6a-111">Antes de poder usar esta función debe habilitarla en su sistema.</span><span class="sxs-lookup"><span data-stu-id="46d6a-111">Before you can use this feature, you must enable it on your system.</span></span> <span data-ttu-id="46d6a-112">Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y habilitarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="46d6a-112">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the feature status and enable it if needed.</span></span> <span data-ttu-id="46d6a-113">Aquí, la función aparece como:</span><span class="sxs-lookup"><span data-stu-id="46d6a-113">Here, the feature is listed as:</span></span>

- <span data-ttu-id="46d6a-114">**Módulo** - Gestión de costes</span><span class="sxs-lookup"><span data-stu-id="46d6a-114">**Module** - Cost management</span></span>
- <span data-ttu-id="46d6a-115">**Nombre de la función** - Comparar el precio de almacenamiento del artículo</span><span class="sxs-lookup"><span data-stu-id="46d6a-115">**Feature name** - Compare item price storage</span></span>

## <a name="generate-a-compare-item-prices-storage-report"></a><span data-ttu-id="46d6a-116">Generar un informe Comprar precios de almacenamiento de artículo</span><span class="sxs-lookup"><span data-stu-id="46d6a-116">Generate a Compare item prices storage report</span></span>

<span data-ttu-id="46d6a-117">Siga estos pasos para generar y almacenar un informe **Comparar precios de almacenamiento de artículos**:</span><span class="sxs-lookup"><span data-stu-id="46d6a-117">Follow these steps to generate and store a **Compare item prices storage** report:</span></span>

1. <span data-ttu-id="46d6a-118">Vaya a **Gestión de costes > Consultas e informes > Informes de costes predeterminados> Comparación de precios de almacenamiento de artículos**.</span><span class="sxs-lookup"><span data-stu-id="46d6a-118">Go to **Cost management > Inquiries and reports > Predetermined cost reports > Compare item prices storage**.</span></span>

1. <span data-ttu-id="46d6a-119">Seleccione **Nuevo** para abrir el panel **Comparar precios de artículos**.</span><span class="sxs-lookup"><span data-stu-id="46d6a-119">Select **New** to open the **Compare item prices** pane.</span></span> <span data-ttu-id="46d6a-120">Establezca las siguientes opciones para definir qué precios comparar en su informe:</span><span class="sxs-lookup"><span data-stu-id="46d6a-120">Set the following options to define which prices to compare in your report:</span></span>

    - <span data-ttu-id="46d6a-121">En la ficha desplegable **Parámetros**, dele un **Nombre** único al informe y use los campos en las secciones **Precios pendientes a comparar** y **Precios utilizados para comparación** para definir qué precios y fechas comparar.</span><span class="sxs-lookup"><span data-stu-id="46d6a-121">On the **Parameters** FastTab, give the report a unique **Name** and use the fields in the **Pending prices to compare** and **Prices used for comparison** sections to define which prices and dates to compare.</span></span>
    - <span data-ttu-id="46d6a-122">En la ficha desplegable **Registros para incluir**, configure filtros y restricciones para definir qué datos incluir en el informe.</span><span class="sxs-lookup"><span data-stu-id="46d6a-122">On the **Records to include** FastTab, set up filters and constraints to define which data to include in the report.</span></span>
    - <span data-ttu-id="46d6a-123">En la ficha desplegable **Ejecutar en segundo plano**, configure cómo, cuándo y la frecuencia con la que desea generar el informe.</span><span class="sxs-lookup"><span data-stu-id="46d6a-123">On the **Run in the background** FastTab, set up how, when, and the frequency at which you want to generate the report.</span></span>
    > [!NOTE]
    > <span data-ttu-id="46d6a-124">Este informe siempre se ejecuta como parte de un trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="46d6a-124">This report is always executed as part of a batch job.</span></span>

1. <span data-ttu-id="46d6a-125">Seleccione **Aceptar** para aplicar su configuración y cerrar el panel.</span><span class="sxs-lookup"><span data-stu-id="46d6a-125">Select **OK** to apply your settings and close the pane.</span></span>

1. <span data-ttu-id="46d6a-126">Después de completar el trabajo por lotes, aparecerá en la página **Comparar precios de almacenamiento de artículos**.</span><span class="sxs-lookup"><span data-stu-id="46d6a-126">After the batch job is completed, it will be listed on the **Compare item prices storage** page.</span></span> <span data-ttu-id="46d6a-127">Puede tener que actualizar la página para ver el informe.</span><span class="sxs-lookup"><span data-stu-id="46d6a-127">You may need to refresh the page to see the report.</span></span>

## <a name="explore-the-compare-item-prices-storage-report"></a><span data-ttu-id="46d6a-128">Explorar el informe Comprar precios de almacenamiento de artículos</span><span class="sxs-lookup"><span data-stu-id="46d6a-128">Explore the Compare item prices storage report</span></span>

<span data-ttu-id="46d6a-129">Después de generar un informe, puede verlo y explorarlo en cualquier momento de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="46d6a-129">After you've generated a report, you can view and explore it at any time as follows:</span></span>

1. <span data-ttu-id="46d6a-130">Vaya a **Gestión de costes > Consultas e informes > Informes de costes predeterminados> Comparación de precios de almacenamiento de artículos**.</span><span class="sxs-lookup"><span data-stu-id="46d6a-130">Go to **Cost management > Inquiries and reports > Predetermined cost reports > Compare item prices storage**.</span></span>

1. <span data-ttu-id="46d6a-131">Seleccione un informe de la lista.</span><span class="sxs-lookup"><span data-stu-id="46d6a-131">Select a report from the list.</span></span>

1. <span data-ttu-id="46d6a-132">Realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="46d6a-132">Do one of the following:</span></span>

    - <span data-ttu-id="46d6a-133">Seleccione **Vista general** para obtener una vista general de los resultados de su informe.</span><span class="sxs-lookup"><span data-stu-id="46d6a-133">Select **Overview** to get an overview of your report results.</span></span>
    - <span data-ttu-id="46d6a-134">Seleccione **Ver detalles** para obtener una vista más detallada de su informe</span><span class="sxs-lookup"><span data-stu-id="46d6a-134">Select **View details** to get a more detailed view of your report</span></span>

1. <span data-ttu-id="46d6a-135">Después de que la vista seleccionada se abra, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="46d6a-135">After the selected view opens, you can do the following:</span></span>

    - <span data-ttu-id="46d6a-136">Seleccione casi cualquier encabezado de columna para ordenar o filtrar la tabla por valores en esa columna, al igual que con la mayoría de los formularios estándar en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="46d6a-136">Select almost any column heading to sort or filter the table by values in that column, just as with most standard forms in Supply Chain Management.</span></span> <span data-ttu-id="46d6a-137">Tenga en cuenta que no puede ordenar o filtrar la columna **% de cambio de precio neto** porque es un campo calculado.</span><span class="sxs-lookup"><span data-stu-id="46d6a-137">Note, you can't sort or filter the **Net change price %** column because it's a calculated field.</span></span>
    - <span data-ttu-id="46d6a-138">Seleccione **Visualización de la dimensión** para abrir un panel donde puede elegir qué columna de dimensión incluir en el formulario.</span><span class="sxs-lookup"><span data-stu-id="46d6a-138">Select **Dimension display** to open a pane where you can choose which dimension column to include on the form.</span></span> <span data-ttu-id="46d6a-139">Establezca **Guardar configuración** a **Sí** si desea guardar esta configuración para que se conserve la próxima vez que abra el informe.</span><span class="sxs-lookup"><span data-stu-id="46d6a-139">Set **Save setup** to **Yes** if you'd like to save these settings so they will be preserved the next time you open the report.</span></span> <span data-ttu-id="46d6a-140">Seleccione **Aceptar** para aplicar su configuración y cerrar.</span><span class="sxs-lookup"><span data-stu-id="46d6a-140">Select **OK** to apply your settings and close.</span></span>
    - <span data-ttu-id="46d6a-141">Seleccione cualquier fila en el formulario y luego seleccione **Ver detalles** para ver más información sobre el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="46d6a-141">Select any row in the form and then select **View details** to see more information about the selected item.</span></span> <span data-ttu-id="46d6a-142">Desde aquí podrá explorar en profundidad los datos.</span><span class="sxs-lookup"><span data-stu-id="46d6a-142">You'll be able to drill down into the data from here.</span></span>
    - <span data-ttu-id="46d6a-143">Seleccione cualquier fila en el formulario y seleccione **Ver tabla comparativa** para ver una representación gráfica interactiva de sus resultados en relación con su elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="46d6a-143">Select any row in the form and then select **View comparison chart** to see an interactive graphical representation of your results as they relate to your selected item.</span></span> <span data-ttu-id="46d6a-144">Puede explorar estos resultados seleccionando varios elementos gráficos en el gráfico y la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="46d6a-144">You can explore these results by selecting various graphical elements in the chart and chart legend.</span></span>
    - <span data-ttu-id="46d6a-145">Seleccione cualquier fila en el formulario y luego seleccione **Ver detalles del cálculo** para ver más información sobre los cálculos relacionados con el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="46d6a-145">Select any row in the form and then select **View calculation details** to see more information about calculations related to the selected item.</span></span> <span data-ttu-id="46d6a-146">Desde aquí podrá explorar en profundidad los datos.</span><span class="sxs-lookup"><span data-stu-id="46d6a-146">You'll be able to drill down into the data from here.</span></span>

## <a name="export-the-compare-item-prices-storage-report"></a><span data-ttu-id="46d6a-147">Exportar el informe Comprar precios de almacenamiento de artículos</span><span class="sxs-lookup"><span data-stu-id="46d6a-147">Export the Compare item prices storage report</span></span>

<span data-ttu-id="46d6a-148">Cada informe que genera se almacena en la entidad **Comparar precios de artículos**.</span><span class="sxs-lookup"><span data-stu-id="46d6a-148">Each report that you generate is stored in the **Compare item prices** data entity.</span></span> <span data-ttu-id="46d6a-149">Puede usar las funciones estándar de administración de datos de Supply Chain Management para exportar datos de esta entidad a cualquier formato de datos compatible, incluidos CSV o Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="46d6a-149">You can use the standard data management features of Supply Chain Management to export data from this entity to any supported data format, including CSV or Microsoft Excel.</span></span>

<span data-ttu-id="46d6a-150">El siguiente es un ejemplo de cómo exportar un informe **Comparar precios de almacenamiento de artículos**:</span><span class="sxs-lookup"><span data-stu-id="46d6a-150">The following is an example of how to export a **Compare item prices storage** report:</span></span>

1. <span data-ttu-id="46d6a-151">Vaya a **Administración del sistema > Áreas de trabajo > Administración de datos**.</span><span class="sxs-lookup"><span data-stu-id="46d6a-151">Go to **System administration > Workspaces > Data management**.</span></span>

1. <span data-ttu-id="46d6a-152">Selecciona el botón **Exportar** en la sección **Gestión de datos**.</span><span class="sxs-lookup"><span data-stu-id="46d6a-152">Select the **Export** button in the **Data management** section.</span></span>

1. <span data-ttu-id="46d6a-153">Se abrirá la página **Exportar**, que usará para configurar su trabajo de exportación.</span><span class="sxs-lookup"><span data-stu-id="46d6a-153">The **Export** page opens, which you'll use to set up your export job.</span></span> <span data-ttu-id="46d6a-154">Comience por darle a tu trabajo un **Nombre del grupo**.</span><span class="sxs-lookup"><span data-stu-id="46d6a-154">Start by giving your job a **Group name**.</span></span>

1. <span data-ttu-id="46d6a-155">En la sección **Entidades seleccionadas**, seleccione **Agregar entidad** para abrir un cuadro de diálogo donde puede configurar las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="46d6a-155">In the **Selected entities** section, select **Add entity** to open a dialog box where you can set the following options:</span></span>

    - <span data-ttu-id="46d6a-156">**Nombre de la entidad** - Seleccione **Comparar precios de artículos**.</span><span class="sxs-lookup"><span data-stu-id="46d6a-156">**Entity name** - Select **Compare item prices**.</span></span>
    - <span data-ttu-id="46d6a-157">**Formato de datos objetivo** - Elija el formato al que desea exportar.</span><span class="sxs-lookup"><span data-stu-id="46d6a-157">**Target data format** - Choose the format that you want to export to.</span></span>

1. <span data-ttu-id="46d6a-158">Seleccione **Agregar** para añadir la fila nueva y luego seleccione **Cerrar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="46d6a-158">Select **Add** to add the new row and then select **Close** to close the dialog box.</span></span>

1. <span data-ttu-id="46d6a-159">Por lo general, exportará un informe a la vez.</span><span class="sxs-lookup"><span data-stu-id="46d6a-159">Usually you'll export one report at a time.</span></span> <span data-ttu-id="46d6a-160">Para hacer esto, configure un **Filtro** para la fila que acaba de agregar al panel **Consulta**.</span><span class="sxs-lookup"><span data-stu-id="46d6a-160">To do this, set up a **Filter** for the row you just added to the **Inquiry** pane.</span></span> <span data-ttu-id="46d6a-161">Esto le permitirá definir qué informes de la entidad **Comparar precios de artículos** desea incluir en su exportación.</span><span class="sxs-lookup"><span data-stu-id="46d6a-161">This will let you define which reports from the **Compare item prices** entity that you want to include in your export.</span></span> <span data-ttu-id="46d6a-162">Configure las siguientes opciones de filtro para exportar un solo informe:</span><span class="sxs-lookup"><span data-stu-id="46d6a-162">Set the following filter options to export a single report:</span></span>

    - <span data-ttu-id="46d6a-163">En la pestaña **Rango**, seleccione **Agregar** para agregar una nueva fila.</span><span class="sxs-lookup"><span data-stu-id="46d6a-163">On the **Range** tab, select **Add** to add a new row.</span></span>
    - <span data-ttu-id="46d6a-164">Establezca **Tabla** en **Comparar precios de artículos**.</span><span class="sxs-lookup"><span data-stu-id="46d6a-164">Set **Table** to **Compare item prices**.</span></span>
    - <span data-ttu-id="46d6a-165">Establezca **Tabla derivada** en **Comparar precios de artículos**.</span><span class="sxs-lookup"><span data-stu-id="46d6a-165">Set **Derived table** to **Compare item prices**.</span></span>
    - <span data-ttu-id="46d6a-166">Establezca el campo **Campo** al campo por el que desea filtrar.</span><span class="sxs-lookup"><span data-stu-id="46d6a-166">Set **Field** to the field that you want to filter by.</span></span> <span data-ttu-id="46d6a-167">Usualmente usará **Nombre de ejecución** o **Tiempo de ejecución**.</span><span class="sxs-lookup"><span data-stu-id="46d6a-167">Usually you'll use **Execution name** or **Execution time**.</span></span>
    - <span data-ttu-id="46d6a-168">Establezca **Criterios** al valor del campo seleccionado que desea buscar (ya sea el nombre del informe o la hora en que se generó el informe).</span><span class="sxs-lookup"><span data-stu-id="46d6a-168">Set **Criteria** to the value from your selected field that you want to look for (either the name of the report or the time the report was generated).</span></span>
    - <span data-ttu-id="46d6a-169">Si es necesario, agregue más filas a la tabla **Rango** hasta que haya identificado de forma exclusiva el informe que está buscando.</span><span class="sxs-lookup"><span data-stu-id="46d6a-169">If necessary, add more rows to the **Range** table until you have uniquely identified the report that you're looking for.</span></span>

1. <span data-ttu-id="46d6a-170">Seleccione **Aceptar** para guardar su configuración y cerrar.</span><span class="sxs-lookup"><span data-stu-id="46d6a-170">Select **OK** to save your settings and close.</span></span>

1. <span data-ttu-id="46d6a-171">Seleccione **Guardar** para guardar su configuración de exportación.</span><span class="sxs-lookup"><span data-stu-id="46d6a-171">Select **Save** to save your export setup.</span></span>

1. <span data-ttu-id="46d6a-172">Abra la pestaña **Opciones de exportación** y seleccione **Exportar ahora** para generar el archivo de exportación.</span><span class="sxs-lookup"><span data-stu-id="46d6a-172">Open the **Export options** tab and select **Export now** to generate the export file.</span></span>

1. <span data-ttu-id="46d6a-173">Se abrirá la página **Resumen de ejecución**, donde puede ver el estado de su trabajo de exportación y una lista de entidades que se exportaron.</span><span class="sxs-lookup"><span data-stu-id="46d6a-173">The **Execution summary** page opens, where you can see the status of your export job and a list of entities that were exported.</span></span> <span data-ttu-id="46d6a-174">Seleccione la entidad **Comparar precios de artículos** enumerada en el área **Estado de procesamiento de la entidad** y luego seleccione **Descargar archivo** para descargar los datos exportados desde esa entidad.</span><span class="sxs-lookup"><span data-stu-id="46d6a-174">Select the **Compare item prices** entity listed in the **Entity processing status** area and then select **Download file** to download the data exported from that entity.</span></span>

<span data-ttu-id="46d6a-175">Para obtener más información sobre cómo usar la administración de datos para exportar datos, vea [Resumen de trabajos de importación y exportación de datos](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="46d6a-175">For more information about how to use data management to export data, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]