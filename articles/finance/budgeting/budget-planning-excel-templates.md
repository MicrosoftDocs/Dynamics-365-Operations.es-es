---
title: Plantillas de planificación presupuestaria para Excel
description: Este tema describe cómo crear plantillas de Microsoft Excel que se puedan utilizar con planes presupuestarios.
author: ryansandness
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetPlanSetLayout
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 261794
ms.assetid: 1d8e99c1-b70d-41ba-991e-ab50b16797e0
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 471c719a8e6de0ebe6fcdad0ae222453db841c87
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772108"
---
# <a name="budget-planning-templates-for-excel"></a><span data-ttu-id="bd440-103">Plantillas de planificación presupuestaria para Excel</span><span class="sxs-lookup"><span data-stu-id="bd440-103">Budget planning templates for Excel</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bd440-104">Este tema describe cómo crear plantillas de Microsoft Excel que se puedan utilizar con planes presupuestarios.</span><span class="sxs-lookup"><span data-stu-id="bd440-104">This topic describes how to create Microsoft Excel templates that can be used with budget plans.</span></span>

<span data-ttu-id="bd440-105">Este tema muestra cómo crear plantillas de Excel que se usarán con planes presupuestarios mediante el conjunto de datos de demostración estándar y el inicio de sesión de usuario Admin.</span><span class="sxs-lookup"><span data-stu-id="bd440-105">This topic shows how to create Excel templates that will be used with budget plans using the standard demo data set and the Admin user login.</span></span> <span data-ttu-id="bd440-106">Para obtener más información sobre la planificación presupuestaria, consulte [Visión general de la planificación presupuestaria](budget-planning-overview-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="bd440-106">For more information about budget planning, see [Budget planning overview](budget-planning-overview-configuration.md).</span></span> <span data-ttu-id="bd440-107">También puede seguir el tutorial [Planificación presupuestaria](budget-plan.md) para aprender los principios básicos de la configuración y el uso de módulos.</span><span class="sxs-lookup"><span data-stu-id="bd440-107">You can also follow the [Budget planning](budget-plan.md) tutorial to learn basic module configuration and usage principles.</span></span>

## <a name="generate-a-worksheet-using-budget-plan-document-layout"></a><span data-ttu-id="bd440-108">Generación de una hoja de cálculo mediante el diseño del documento de plan presupuestario</span><span class="sxs-lookup"><span data-stu-id="bd440-108">Generate a worksheet using budget plan document layout</span></span>

<span data-ttu-id="bd440-109">Los documentos de plan presupuestario se pueden ver y editar mediante uno o varios diseños.</span><span class="sxs-lookup"><span data-stu-id="bd440-109">Budget plan documents can be viewed and edited using one or more layouts.</span></span> <span data-ttu-id="bd440-110">Cada diseño puede tener una plantilla de documento de plan presupuestario asociada para ver y editar los datos del plan presupuestario en una hoja de cálculo de Excel.</span><span class="sxs-lookup"><span data-stu-id="bd440-110">Each layout can have an associated budget plan document template to view and edit the budget plan data in an Excel worksheet.</span></span> <span data-ttu-id="bd440-111">En este tema, una plantilla de documento de plan presupuestario se generará empleando una configuración de diseño existente.</span><span class="sxs-lookup"><span data-stu-id="bd440-111">In this topic, a budget plan document template will be generated using an existing layout configuration.</span></span> 

1. <span data-ttu-id="bd440-112">Abra la **Lista de planes presupuestarios** (**Gestión presupuestaria** &gt; **Planes presupuestarios**).</span><span class="sxs-lookup"><span data-stu-id="bd440-112">Open the **Budget plans list** (**Budgeting** &gt; **Budget plans**).</span></span> 
2. <span data-ttu-id="bd440-113">Haga clic en **Nuevo** para crear un documento de plan presupuestario.</span><span class="sxs-lookup"><span data-stu-id="bd440-113">Click **New** to create a new budget plan document.</span></span> 

   <span data-ttu-id="bd440-114">[![Lista de planes presupuestarios](./media/bpt11-1024x552.png)](./media/bpt11.png)</span><span class="sxs-lookup"><span data-stu-id="bd440-114">[![Budget plans list](./media/bpt11-1024x552.png)](./media/bpt11.png)</span></span> 

3. <span data-ttu-id="bd440-115">Emplee la opción de línea **Agregar** para agregar líneas.</span><span class="sxs-lookup"><span data-stu-id="bd440-115">Use the **Add** line option to add lines.</span></span> <span data-ttu-id="bd440-116">Haga clic en **Diseños** para ver la configuración del diseño de documento de plan presupuestario.</span><span class="sxs-lookup"><span data-stu-id="bd440-116">Click **Layouts** to view the budget plan document layout configuration.</span></span> 

   <span data-ttu-id="bd440-117">[![Agregar planes presupuestarios](./media/bpt2-1024x274.png)](./media/bpt2.png)</span><span class="sxs-lookup"><span data-stu-id="bd440-117">[![Budget plans add](./media/bpt2-1024x274.png)](./media/bpt2.png)</span></span> 

<span data-ttu-id="bd440-118">Puede revisar la configuración de diseño y ajustarla según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="bd440-118">You can review the layout configuration and adjust it as needed.</span></span> 
1. <span data-ttu-id="bd440-119">Vaya a **Plantilla** &gt; **Generar** para crear un archivo de Excel para este diseño.</span><span class="sxs-lookup"><span data-stu-id="bd440-119">Go to **Template** &gt; **Generate** to create an Excel file for this layout.</span></span> 
2. <span data-ttu-id="bd440-120">Después de que se cree la plantilla, vaya a **Plantilla** &gt; **Ver** para abrir y revisar la plantilla de documento de plan presupuestario.</span><span class="sxs-lookup"><span data-stu-id="bd440-120">After the template is generated, go to **Template** &gt; **View** to open and review the budget plan document template.</span></span> <span data-ttu-id="bd440-121">Puede guardar el archivo de Excel en la unidad local.</span><span class="sxs-lookup"><span data-stu-id="bd440-121">You can save the Excel file to your local drive.</span></span> 

<span data-ttu-id="bd440-122">[![Guardar como](./media/bpt3-1024x545.png)](./media/bpt3.png)</span><span class="sxs-lookup"><span data-stu-id="bd440-122">[![Save as](./media/bpt3-1024x545.png)](./media/bpt3.png)</span></span>

> [!NOTE] 
> <span data-ttu-id="bd440-123">El diseño de documento del plan presupuestario no se puede editar después de asociarle una plantilla de Excel.</span><span class="sxs-lookup"><span data-stu-id="bd440-123">The Budget plan document layout cannot be edited after an Excel template is associated with it.</span></span> <span data-ttu-id="bd440-124">Para modificar el diseño, elimine el archivo de plantilla de Excel asociado y regenérelo.</span><span class="sxs-lookup"><span data-stu-id="bd440-124">To modify the layout, delete the associated Excel template file and regenerate it.</span></span> <span data-ttu-id="bd440-125">Esto es necesario para mantener sincronizados los campos del diseño y la hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="bd440-125">This is required to keep the fields in the layout and the worksheet synchronized.</span></span> 

<span data-ttu-id="bd440-126">La plantilla de Excel contendrá todos los elementos del diseño de documento de plan presupuestario en los que la columna **Disponible en la hoja de cálculo** se haya definido como Verdadero.</span><span class="sxs-lookup"><span data-stu-id="bd440-126">The Excel template will contain all of the elements from the budget plan document layout, where the **Available in Worksheet** column is set to True.</span></span> <span data-ttu-id="bd440-127">Los elementos superpuestos no están permitidos en la plantilla de Excel.</span><span class="sxs-lookup"><span data-stu-id="bd440-127">Overlapping elements are not allowed in the Excel template.</span></span> <span data-ttu-id="bd440-128">Por ejemplo, si el diseño contiene las columnas Solicitud de primer trimestre, Solicitud de segundo trimestre, Solicitud de tercer trimestre y Solicitud de cuarto trimestre y una columna con el total de las solicitudes que representa una suma de las 4 columnas trimestrales, solo las columnas trimestrales o la columna total estarán disponibles para su empleo en la plantilla de Excel.</span><span class="sxs-lookup"><span data-stu-id="bd440-128">For example, if the layout contains Request Q1, Request Q2, Request Q3, and Request Q4 columns, and a total request column that represents a sum of all 4 quarterly columns, only the quarterly columns or total column is available to be used in the Excel template.</span></span> <span data-ttu-id="bd440-129">El archivo de Excel no puede actualizar las columnas superpuestas durante la actualización porque los datos de la tabla pueden quedar obsoletos e inexactos.</span><span class="sxs-lookup"><span data-stu-id="bd440-129">The Excel file cannot update overlapping columns during the update because data in the table could become out of date and inaccurate.</span></span>

> [!NOTE] 
> <span data-ttu-id="bd440-130">Para evitar posibles problemas con la visualización y edición de los datos del plan presupuestario con Excel, el mismo usuario se debe registrar en Microsoft Dynamics 365 Finance y el conector de datos del complemento de Office para Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="bd440-130">To avoid potential issues with viewing and editing budget plan data using Excel, the same user should be logged into both Microsoft Dynamics 365 Finance and the Microsoft Dynamics Office Add-in Data Connector.</span></span>

## <a name="add-a-header-to-budget-plan-document-template"></a><span data-ttu-id="bd440-131">Agregar un encabezado a la plantilla de documento de plan presupuestario</span><span class="sxs-lookup"><span data-stu-id="bd440-131">Add a header to budget plan document template</span></span>
<span data-ttu-id="bd440-132">Para agregar información de encabezado, seleccione la fila superior en el archivo de Excel e inserte las filas vacías.</span><span class="sxs-lookup"><span data-stu-id="bd440-132">To add header information, select the top row in the Excel file and insert empty rows.</span></span> <span data-ttu-id="bd440-133">Haga clic en **Diseño** en el **Conector de datos** para agregar campos de cabecera al archivo de Excel.</span><span class="sxs-lookup"><span data-stu-id="bd440-133">Click **Design** in the **Data Connector** to add header fields to the Excel file.</span></span>

<span data-ttu-id="bd440-134">En la pestaña **Diseño** haga clic en los campos **Agregar** y seleccione **BudgetPlanHeader** como origen de datos de entidad.</span><span class="sxs-lookup"><span data-stu-id="bd440-134">In the **Design** tab, click **Add** fields, and then select **BudgetPlanHeader** as the entity data source.</span></span>

<span data-ttu-id="bd440-135">Coloque el cursor en la ubicación deseada del archivo de Excel.</span><span class="sxs-lookup"><span data-stu-id="bd440-135">Point the cursor to the desired location in the Excel file.</span></span> <span data-ttu-id="bd440-136">Haga clic en **Agregar etiqueta** para agregar la etiqueta de campo a la ubicación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="bd440-136">Click **Add label** to add the field label to the selected location.</span></span> <span data-ttu-id="bd440-137">Seleccione **Agregar valor** para agregar el campo de valor al lugar seleccionado.</span><span class="sxs-lookup"><span data-stu-id="bd440-137">Select **Add Value** to add the value field to the selected place.</span></span> <span data-ttu-id="bd440-138">Haga clic en **Listo** para cerrar el diseñador.</span><span class="sxs-lookup"><span data-stu-id="bd440-138">Click **Done** to close the designer.</span></span>

## <a name="select-add-valuemediabpt7pngmediabpt7png"></a><span data-ttu-id="bd440-139">[![Seleccionar Agregar valor](./media/bpt7.png)](./media/bpt7.png)</span><span class="sxs-lookup"><span data-stu-id="bd440-139">[![Select Add Value](./media/bpt7.png)](./media/bpt7.png)</span></span>

<a name="add-a-calculated-column-to-budget-plan-document-template-table"></a><span data-ttu-id="bd440-140">Agregue una columna calculada a la tabla de plantillas de documento de plan presupuestario</span><span class="sxs-lookup"><span data-stu-id="bd440-140">Add a calculated column to budget plan document template table</span></span>
--------------------------------------------------------------

<span data-ttu-id="bd440-141">A continuación, las columnas calculadas se agregará a la plantilla de documento de plan presupuestario generada.</span><span class="sxs-lookup"><span data-stu-id="bd440-141">Next, calculated columns will be added to generated budget plan document template.</span></span> <span data-ttu-id="bd440-142">Una columna **Total de la solicitud** que suma las columnas Solicitud de primer trimestre: Solicitud de cuarto trimestre y una columna **Ajuste** que recalcula la columna **Total de la solicitud** con un factor predefinido.</span><span class="sxs-lookup"><span data-stu-id="bd440-142">A **Total request** column, which summarizes Request Q1: Request Q4 columns, and an **Adjustment** column, which recalculates the **Total Request** column by a predefined factor.</span></span>

<span data-ttu-id="bd440-143">Haga clic en **Diseño** en el **Conector de datos** para agregar columnas a la tabla.</span><span class="sxs-lookup"><span data-stu-id="bd440-143">Click **Design** in the **Data connector** to add columns to the table.</span></span> <span data-ttu-id="bd440-144">Haga clic en **Editar** junto al origen de datos **BudgetPlanWorksheet** para comenzar a agregar columnas.</span><span class="sxs-lookup"><span data-stu-id="bd440-144">Click **Edit** next to **BudgetPlanWorksheet** data source to start adding columns.</span></span>

<span data-ttu-id="bd440-145">[![Comenzar a agregar columnas](./media/bpt8-1024x301.png)](./media/bpt8.png)</span><span class="sxs-lookup"><span data-stu-id="bd440-145">[![Start adding columns](./media/bpt8-1024x301.png)](./media/bpt8.png)</span></span> 

<span data-ttu-id="bd440-146">El grupo de campos seleccionado muestra las columnas disponibles en la plantilla.</span><span class="sxs-lookup"><span data-stu-id="bd440-146">The selected field group displays the columns that are available in the template.</span></span> <span data-ttu-id="bd440-147">Haga clic en **Fórmula** para agregar una nueva columna.</span><span class="sxs-lookup"><span data-stu-id="bd440-147">Click **Formula** to add a new column.</span></span> <span data-ttu-id="bd440-148">Designe un nombre a la nueva columna y copie la fórmula en el campo **Fórmula**.</span><span class="sxs-lookup"><span data-stu-id="bd440-148">Name the new column and then paste the formula into the **Formula** field.</span></span> <span data-ttu-id="bd440-149">Haga clic en **Actualizar** para insertar la columna.</span><span class="sxs-lookup"><span data-stu-id="bd440-149">Click **Update** to insert the column.</span></span>

<span data-ttu-id="bd440-150">[![Agregar y insertar columnas](./media/bpt12-1024x565.png)](./media/bpt12.png)</span><span class="sxs-lookup"><span data-stu-id="bd440-150">[![Add and insert column](./media/bpt12-1024x565.png)](./media/bpt12.png)</span></span>

> [!NOTE] 
> <span data-ttu-id="bd440-151">Para definir la fórmula, cree la fórmula en la hoja de cálculo y, a continuación, cópiela en la ventana **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="bd440-151">To define the formula, create the formula in the spreadsheet, and then copy it to the **Design** window.</span></span> <span data-ttu-id="bd440-152">Una tabla enlazada de Finance and Operations normalmente será denominada “AXTable1”.</span><span class="sxs-lookup"><span data-stu-id="bd440-152">A Finance and Operations bound table will typically be named "AXTable1".</span></span> <span data-ttu-id="bd440-153">Por ejemplo, para sumar las columnas Solicitud de primer trimestre : Solicitud de cuarto trimestre en la hoja de cálculo; la fórmula = AxTable1\[Solicitud primer trimestre\]+AxTable1\[Solicitud segundo trimestre\]+AxTable1\[Solicitud tercer trimestre\]+AxTable1\[Solicitud cuarto trimestre\].</span><span class="sxs-lookup"><span data-stu-id="bd440-153">For example, to summarize Request Q1 : Request Q4 columns in the spreadsheet, the formula = AxTable1\[Request Q1\]+AxTable1\[Request Q2\]+AxTable1\[Request Q3\]+AxTable1\[Request Q4\].</span></span>

<span data-ttu-id="bd440-154">Repita estos pasos para insertar la columna **Ajuste**.</span><span class="sxs-lookup"><span data-stu-id="bd440-154">Repeat these steps to insert the **Adjustment** column.</span></span> <span data-ttu-id="bd440-155">Use la fórmula = AxTable1\[Total de la solicitud\]\*$I$1 para esta columna.</span><span class="sxs-lookup"><span data-stu-id="bd440-155">Use formula = AxTable1\[Total request\]\*$I$1 for this column.</span></span> <span data-ttu-id="bd440-156">Esto tomará el valor de la celda I1 y multiplicará los valores de la columna **Total de la solicitud** para calcular los importes de ajuste.</span><span class="sxs-lookup"><span data-stu-id="bd440-156">This will take the value in cell I1 and multiply the values in the **Total request** column to calculate adjustment amounts.</span></span>

<span data-ttu-id="bd440-157">Guarde y cierre el archivo de Excel.</span><span class="sxs-lookup"><span data-stu-id="bd440-157">Save and close the Excel file.</span></span> <span data-ttu-id="bd440-158">En **Diseños** haga clic en clic **Plantilla &gt; Cargar** para cargar la plantilla de Excel guardada que se utilizará para el plan presupuestario.</span><span class="sxs-lookup"><span data-stu-id="bd440-158">In **Layouts**, click **Template &gt; Upload** to upload the saved Excel template to be used for the budget plan.</span></span> 

<span data-ttu-id="bd440-159">[![Cargar plantilla de Excel](./media/bpt10-1024x352.png)](./media/bpt10.png)</span><span class="sxs-lookup"><span data-stu-id="bd440-159">[![Upload Excel template](./media/bpt10-1024x352.png)](./media/bpt10.png)</span></span> 

<span data-ttu-id="bd440-160">Cierre el control deslizante **Diseños**.</span><span class="sxs-lookup"><span data-stu-id="bd440-160">Close the **Layouts** slider.</span></span> <span data-ttu-id="bd440-161">En el documento **Plan presupuestario**, haga clic en **Hoja de cálculo** para ver y editar el documento en Excel.</span><span class="sxs-lookup"><span data-stu-id="bd440-161">In **Budget plan** document, click **Worksheet** to view and edit the document in Excel.</span></span> <span data-ttu-id="bd440-162">Tenga en cuenta que la plantilla de Excel ajustada se usó para crear esta hoja de cálculo de plan presupuestario y las columnas calculadas están actualizadas con las fórmulas que se definieron en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="bd440-162">Note that the adjusted Excel template was used to create this budget plan worksheet and calculated columns are updated using the formulas that were defined in the previous steps.</span></span> 

<span data-ttu-id="bd440-163">[![Ver y editar documento en Excel](./media/bpt111-1024x431.png)](./media/bpt111.png)</span><span class="sxs-lookup"><span data-stu-id="bd440-163">[![View and edit document in Excel](./media/bpt111-1024x431.png)](./media/bpt111.png)</span></span>

## <a name="tips--tricks-for-creating-budget-plan-templates"></a><span data-ttu-id="bd440-164">Trucos para crear plantillas de plan presupuestario</span><span class="sxs-lookup"><span data-stu-id="bd440-164">Tips & tricks for creating budget plan templates</span></span>
### <a name="can-i-add-and-use-additional-data-sources-to-a-budget-plan-template"></a><span data-ttu-id="bd440-165">¿Puedo agregar y utilizar orígenes de datos adicionales para una plantilla de plan presupuestario?</span><span class="sxs-lookup"><span data-stu-id="bd440-165">Can I add and use additional data sources to a budget plan template?</span></span>

<span data-ttu-id="bd440-166">Sí, puede usar el menú **Diseño** para agregar entidades adicionales a la misma o a otras hojas en la plantilla de Excel.</span><span class="sxs-lookup"><span data-stu-id="bd440-166">Yes, you can use the **Design** menu to add additional entities to the same or other sheets in the Excel template.</span></span> <span data-ttu-id="bd440-167">Por ejemplo, puede agregar el origen de datos **BudgetPlanProposedProject** para crear y mantener una lista de proyectos propuestos al mismo tiempo al trabajar con datos del plan presupuestario en Excel.</span><span class="sxs-lookup"><span data-stu-id="bd440-167">For example, you can add the **BudgetPlanProposedProject** data source to create and maintain a list of proposed projects at the same time when working with budget plan data in Excel.</span></span> <span data-ttu-id="bd440-168">Tenga en cuenta que incluir orígenes de datos de gran volumen puede afectar al rendimiento del libro de Excel.</span><span class="sxs-lookup"><span data-stu-id="bd440-168">Note that including high-volume data sources might impact performance of the Excel workbook.</span></span> 

<span data-ttu-id="bd440-169">Puede usar la opción **Filtro** en **Conector de datos** de agregar los filtros deseados a orígenes de datos adicionales.</span><span class="sxs-lookup"><span data-stu-id="bd440-169">You can use the **Filter** option in the **Data Connector** to add desired filters to additional data sources.</span></span>

### <a name="can-i-hide-the-design-option-in-the-data-connector-for-other-users"></a><span data-ttu-id="bd440-170">¿Puedo ocultar la opción Diseño en el Conector de datos para otros usuarios?</span><span class="sxs-lookup"><span data-stu-id="bd440-170">Can I hide the Design option in the Data connector for other users?</span></span>

<span data-ttu-id="bd440-171">Sí, abra las opciones del **Conector de datos** para ocultar la opción **Diseño** de otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="bd440-171">Yes, open the **Data Connector** options to hide the **Design** option from other users.</span></span>

<span data-ttu-id="bd440-172">[![Abrir opciones de conector de datos](./media/bpt13-1024x565.png)](./media/bpt13.png)</span><span class="sxs-lookup"><span data-stu-id="bd440-172">[![Open Data Connector options](./media/bpt13-1024x565.png)](./media/bpt13.png)</span></span>

<span data-ttu-id="bd440-173">Expanda las opciones de **Conector de datos** y desmarque la casilla de verificación **Habilitar diseño**.</span><span class="sxs-lookup"><span data-stu-id="bd440-173">Expand **Data connector options** and clear the **Enable design** check box.</span></span> <span data-ttu-id="bd440-174">Esto ocultará la opción de **Diseño** del **Conector de datos**.</span><span class="sxs-lookup"><span data-stu-id="bd440-174">This will hide the **Design** option from the **Data connector**.</span></span>

<span data-ttu-id="bd440-175">[![Opción de ocultar diseños de conector de datos](./media/bpt14-1024x592.png)](./media/bpt14.png)</span><span class="sxs-lookup"><span data-stu-id="bd440-175">[![Hide Design option from Data connector](./media/bpt14-1024x592.png)](./media/bpt14.png)</span></span>

### <a name="can-i-prevent-users-from-accidently-closing-the-data-connector-while-working-with-data"></a><span data-ttu-id="bd440-176">¿Puedo evitar que los usuarios cierren accidentalmente el Conector de datos mientras trabajan con los datos?</span><span class="sxs-lookup"><span data-stu-id="bd440-176">Can I prevent users from accidently closing the Data connector while working with data?</span></span>

<span data-ttu-id="bd440-177">Es recomendable bloquear la plantilla para evitar que los usuarios la cierren.</span><span class="sxs-lookup"><span data-stu-id="bd440-177">We recommend locking the template to prevent users from closing it.</span></span> <span data-ttu-id="bd440-178">Para activar el bloqueo, haga clic en **Conector de datos**; en la esquina superior derecha aparece una flecha.</span><span class="sxs-lookup"><span data-stu-id="bd440-178">To turn on the lock, click the **Data connector**, in the top right corner an arrow appears.</span></span> 

<span data-ttu-id="bd440-179">[![Activar el bloqueo](./media/bpt15-1024x285.png)](./media/bpt15.png)</span><span class="sxs-lookup"><span data-stu-id="bd440-179">[![Turn on the lock](./media/bpt15-1024x285.png)](./media/bpt15.png)</span></span> 

<span data-ttu-id="bd440-180">Haga clic en la flecha para un menú adicional.</span><span class="sxs-lookup"><span data-stu-id="bd440-180">Click the arrow for an additional menu.</span></span> <span data-ttu-id="bd440-181">Seleccione **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="bd440-181">Select **Lock**.</span></span>

### <a name="select-lockmediabpt16-1024x614pngmediabpt16png"></a><span data-ttu-id="bd440-182">[![Seleccione Bloquear](./media/bpt16-1024x614.png)](./media/bpt16.png)</span><span class="sxs-lookup"><span data-stu-id="bd440-182">[![Select Lock](./media/bpt16-1024x614.png)](./media/bpt16.png)</span></span>

### <a name="can-i-use-other-excel-features-like-cell-formatting-colors-conditional-formatting-and-charts-with-my-budget-plan-templates"></a><span data-ttu-id="bd440-183">¿Puedo usar otras funciones de Excel, como formato de celda, colores, formato condicional y gráficos mis con plantillas del plan presupuestario?</span><span class="sxs-lookup"><span data-stu-id="bd440-183">Can I use other Excel features, like cell formatting, colors, conditional formatting, and charts with my budget plan templates?</span></span>

<span data-ttu-id="bd440-184">Sí, la mayoría de las capacidades estándar de Excel funcionarán en las plantillas de plan presupuestario.</span><span class="sxs-lookup"><span data-stu-id="bd440-184">Yes, most of the standard Excel capabilities will work in budget plan templates.</span></span> <span data-ttu-id="bd440-185">Recomendamos usar la codificación de color para que los usuarios distingan entre las columnas de solo lectura y las editables.</span><span class="sxs-lookup"><span data-stu-id="bd440-185">We recommend using color-coding for users to distinguish between read-only and editable columns.</span></span> <span data-ttu-id="bd440-186">El formato condicional se puede usar para resaltar las áreas problemáticas del presupuesto.</span><span class="sxs-lookup"><span data-stu-id="bd440-186">Conditional formatting can be used to highlight problematic areas of the budget.</span></span> <span data-ttu-id="bd440-187">Los totales de las columnas se pueden mostrar con facilidad mediante las fórmulas estándar de Excel sobre la tabla.</span><span class="sxs-lookup"><span data-stu-id="bd440-187">Column totals can easily be presented by using standard Excel formulas above the table.</span></span>

<span data-ttu-id="bd440-188">También puede crear y usar las tablas dinámicas y gráficos para agrupaciones adicionales y visualizaciones de los datos presupuestarios.</span><span class="sxs-lookup"><span data-stu-id="bd440-188">You can also create and use pivot tables and charts for additional groupings and visualizations of budget data.</span></span> <span data-ttu-id="bd440-189">En la ficha **Datos**, en el grupo **Conexiones**, haga clic en **Actualizar todo** y, a continuación, en **Propiedades de conexión**.</span><span class="sxs-lookup"><span data-stu-id="bd440-189">On the **Data** tab, in the **Connections** group, click **Refresh All**, and then click **Connection Properties**.</span></span> <span data-ttu-id="bd440-190">Haga clic en la pestaña **Uso**. En **Actualización**, seleccione la casilla **Actualizar datos al abrir el archivo**.</span><span class="sxs-lookup"><span data-stu-id="bd440-190">Click the **Usage** tab. Under **Refresh**, select the **Refresh data when opening the file** check box.</span></span> 


