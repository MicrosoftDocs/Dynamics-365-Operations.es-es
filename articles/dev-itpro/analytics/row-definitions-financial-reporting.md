---
title: Definiciones de filas en el diseñador de informes financieros
description: Una definición de fila es un componente de informe, o bloque de creación, que especifica el contenido de cada fila de un informe financiero. Una definición de fila se puede combinar con las definiciones de columnas, definiciones de organigramas y definiciones de informes para crear un grupo de bloques de creación que puedan usar varias empresas.
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 68873
ms.assetid: 2fd7b5da-700f-48cb-9003-90c0d82f818f
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5b0b7b715bc2b3b90bcd6620c3fe0ad751313c06
ms.sourcegitcommit: 9b4c3fff2f30006b7bb491ef6ffe89d41bcbfa11
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2019
ms.locfileid: "1863757"
---
# <a name="row-definitions-in-financial-report-designer"></a><span data-ttu-id="30fbf-104">Definiciones de filas en el diseñador de informes financieros</span><span class="sxs-lookup"><span data-stu-id="30fbf-104">Row definitions in financial report designer</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="30fbf-105">Una definición de fila es un componente de informe, o bloque de creación, que especifica el contenido de cada fila de un informe financiero.</span><span class="sxs-lookup"><span data-stu-id="30fbf-105">A row definition is a report component, or building block, that specifies the contents of each row on a financial report.</span></span> <span data-ttu-id="30fbf-106">Una definición de fila se puede combinar con las definiciones de columnas, definiciones de organigramas y definiciones de informes para crear un grupo de bloques de creación que puedan usar varias empresas.</span><span class="sxs-lookup"><span data-stu-id="30fbf-106">A row definition can be combined with column definitions, reporting tree definitions, and report definitions to create a building block group that can be used by multiple companies.</span></span>

## <a name="create-a-row-definition"></a><span data-ttu-id="30fbf-107">Crear una definición de fila</span><span class="sxs-lookup"><span data-stu-id="30fbf-107">Create a row definition</span></span>

1. <span data-ttu-id="30fbf-108">En el diseñador de informes, en el panel de navegación, haga clic en **Definiciones de las filas**.</span><span class="sxs-lookup"><span data-stu-id="30fbf-108">In Report Designer, in the navigation pane, click **Row Definitions**.</span></span>
2. <span data-ttu-id="30fbf-109">En el menú **Archivo**, haga clic en **Nueva** y, a continuación, haga clic en **Definición de filas**.</span><span class="sxs-lookup"><span data-stu-id="30fbf-109">On the **File** menu, click **New**, and then click **Row Definition**.</span></span> <span data-ttu-id="30fbf-110">Para obtener más información sobre el contenido de cada celda, vea [Modificar las celdas de la definición de filas](modify-row-definition-cells-financial-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="30fbf-110">For more information about the content of each cell, see [Modify row definition cells](modify-row-definition-cells-financial-reporting.md).</span></span>

## <a name="open-a-row-definition"></a><span data-ttu-id="30fbf-111">Abrir una definición de fila</span><span class="sxs-lookup"><span data-stu-id="30fbf-111">Open a row definition</span></span>
1. <span data-ttu-id="30fbf-112">En el diseñador de informes, en el panel de navegación, haga clic en **Definiciones de las filas**.</span><span class="sxs-lookup"><span data-stu-id="30fbf-112">In Report Designer, in the navigation pane, click **Row Definitions**.</span></span>
2. <span data-ttu-id="30fbf-113">Haga doble clic en el nombre de la definición de la fila para abrirla.</span><span class="sxs-lookup"><span data-stu-id="30fbf-113">Double-click the name of the row definition to open.</span></span>
3. <span data-ttu-id="30fbf-114">Para ver los bloques de creación asociados con la definición de filas, haga clic con el botón secundario en la definición de filas y seleccione **Asociaciones**.</span><span class="sxs-lookup"><span data-stu-id="30fbf-114">To view any building blocks that are associated with the row definition, right-click the row definition, and then select **Associations**.</span></span>

## <a name="contents-of-a-row-definition"></a><span data-ttu-id="30fbf-115"> Contenido de una definición de filas</span><span class="sxs-lookup"><span data-stu-id="30fbf-115">Contents of a row definition</span></span>
<span data-ttu-id="30fbf-116">Una definición de fila puede contener hasta 20.000 filas de la dimensión financiera e incluir la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="30fbf-116">A row definition can contain up to 20,000 financial dimension rows and can include the following information:</span></span>

- <span data-ttu-id="30fbf-117">Texto descriptivo que agrega significado al informe creando títulos de sección, líneas y espacios, como **Efectivo** o **Ingresos totales**</span><span class="sxs-lookup"><span data-stu-id="30fbf-117">Descriptive text that adds meaning to the report by creating section headings, lines, and spaces, such as **Cash** or **Total Revenue**</span></span>
- <span data-ttu-id="30fbf-118">Vínculos a datos financieros, que pueden incluir valores de dimensión en Microsoft Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="30fbf-118">Links to financial data, which can include dimension values in the Microsoft Dynamics 365 for Finance and Operations</span></span>

    > [!NOTE]
    > <span data-ttu-id="30fbf-119">Puede configurar una definición de fila para extraer datos del sistema de dimensiones financieras cada vez que se genera el informe.</span><span class="sxs-lookup"><span data-stu-id="30fbf-119">You can set up a row definition to pull data from the financial dimensions system every time that the report is generated.</span></span>

- <span data-ttu-id="30fbf-120">Los totales de filas y las fórmulas que se basan en los datos financieros vinculados</span><span class="sxs-lookup"><span data-stu-id="30fbf-120">Row totals and formulas that are based on the linked financial data</span></span>

<span data-ttu-id="30fbf-121">Normalmente, cada fila en una definición de fila contiene uno de los siguientes tipos de información:</span><span class="sxs-lookup"><span data-stu-id="30fbf-121">Usually, each row in a row definition contains one of the following types of information:</span></span>

- <span data-ttu-id="30fbf-122">Referencias al sistema de las dimensiones financieras</span><span class="sxs-lookup"><span data-stu-id="30fbf-122">References to the financial dimensions system</span></span>
- <span data-ttu-id="30fbf-123">Totales o cálculos que se basan en los datos</span><span class="sxs-lookup"><span data-stu-id="30fbf-123">Totals or calculations that are based on the data</span></span>
- <span data-ttu-id="30fbf-124">Formato</span><span class="sxs-lookup"><span data-stu-id="30fbf-124">Formatting</span></span>

<span data-ttu-id="30fbf-125">Hay dos métodos para escribir información en una definición de fila:</span><span class="sxs-lookup"><span data-stu-id="30fbf-125">There are two methods for entering information in a row definition:</span></span>

- <span data-ttu-id="30fbf-126">Especifique manualmente la información de fila en una nueva definición de fila.</span><span class="sxs-lookup"><span data-stu-id="30fbf-126">Manually enter row information in a new row definition.</span></span> <span data-ttu-id="30fbf-127">Para obtener más información, consulte [Modificar las celdas de la definición de filas](modify-row-definition-cells-financial-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="30fbf-127">For more information, see [Modify row definition cells](modify-row-definition-cells-financial-reporting.md).</span></span>
- <span data-ttu-id="30fbf-128">Utilice el diseñador de informes para extraer información de la fila directamente de las dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="30fbf-128">Use report designer to pull row information directly from the financial dimensions.</span></span> <span data-ttu-id="30fbf-129">Para obtener más información, consulte la sección "Fórmulas/filas/unidades relacionadas" en [Modificar las celdas de la definición de filas](modify-row-definition-cells-financial-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="30fbf-129">For more information, see the "Related formulas/rows/units" section in [Modify row definition cells](modify-row-definition-cells-financial-reporting.md).</span></span>

## <a name="add-dimensions-in-a-row-definition"></a><span data-ttu-id="30fbf-130"> Agregar dimensiones en una definición de filas</span><span class="sxs-lookup"><span data-stu-id="30fbf-130">Add dimensions in a row definition</span></span>
<span data-ttu-id="30fbf-131">Una dimensión es una intersección de datos y de valores.</span><span class="sxs-lookup"><span data-stu-id="30fbf-131">A dimension is an intersection of data and values.</span></span> <span data-ttu-id="30fbf-132">Puede agrupar datos y valores en el diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="30fbf-132">You can group data and values in report designer.</span></span> <span data-ttu-id="30fbf-133">A continuación, puede clasificar y analizar transacciones con más detalle.</span><span class="sxs-lookup"><span data-stu-id="30fbf-133">You can then classify and analyze transactions in more detail.</span></span> <span data-ttu-id="30fbf-134">Puede usar el cuadro de diálogo **Insertar filas desde dimensiones** para agregar varias filas a una definición de fila al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="30fbf-134">You can use the **Insert Rows from Dimensions** dialog box to add multiple rows to a row definition at the same time.</span></span> <span data-ttu-id="30fbf-135">El cuadro de diálogo muestra una columna para cada dimensión.</span><span class="sxs-lookup"><span data-stu-id="30fbf-135">The dialog box displays one column for each dimension.</span></span> <span data-ttu-id="30fbf-136">En la tabla siguiente se describe la información que puede especificar para cada dimensión.</span><span class="sxs-lookup"><span data-stu-id="30fbf-136">The following table describes the information that you can specify for each dimension.</span></span>

| <span data-ttu-id="30fbf-137">Opción</span><span class="sxs-lookup"><span data-stu-id="30fbf-137">Option</span></span>                | <span data-ttu-id="30fbf-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="30fbf-138">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="30fbf-139">Dimensión</span><span class="sxs-lookup"><span data-stu-id="30fbf-139">Dimension</span></span>             | <span data-ttu-id="30fbf-140">El modelo que identifica la dimensión que se agrega a la definición de filas.</span><span class="sxs-lookup"><span data-stu-id="30fbf-140">The pattern that identifies the dimension to add to the row definition.</span></span> <span data-ttu-id="30fbf-141">Este modelo contiene una Y comercial (&) o el signo de número (\#) para cada puesto de las dimensiones.</span><span class="sxs-lookup"><span data-stu-id="30fbf-141">This pattern contains one ampersand (&) or number sign (\#) for each position in the dimensions.</span></span> <span data-ttu-id="30fbf-142">Normalmente, use todos los signos & para la dimensión de la cuenta principal y todos los signos de número para otras dimensiones.</span><span class="sxs-lookup"><span data-stu-id="30fbf-142">Generally, use all ampersands for the Main Account dimension and all number signs for other dimensions.</span></span> |
| <span data-ttu-id="30fbf-143">Inicio de intervalo de dimensión</span><span class="sxs-lookup"><span data-stu-id="30fbf-143">Dimension Range Start</span></span> | <span data-ttu-id="30fbf-144">El primer valor de esta dimensión que se va a agregar a la definición de fila.</span><span class="sxs-lookup"><span data-stu-id="30fbf-144">The first value for this dimension to add to the row definition.</span></span> |
| <span data-ttu-id="30fbf-145">Fin de intervalo de dimensión</span><span class="sxs-lookup"><span data-stu-id="30fbf-145">Dimension Range End</span></span>   | <span data-ttu-id="30fbf-146">El último valor que agregará esta dimensión a la definición de filas.</span><span class="sxs-lookup"><span data-stu-id="30fbf-146">The last value for this dimension to add to the row definition.</span></span> |

<span data-ttu-id="30fbf-147">Para agregar dimensiones a una definición de fila, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="30fbf-147">To add dimensions to a row definition, follow these steps.</span></span>

1. <span data-ttu-id="30fbf-148">En el diseñador del informes, haga clic en **Definiciones de filas** y después abra la definición de fila para modificarla.</span><span class="sxs-lookup"><span data-stu-id="30fbf-148">In Report Designer, click **Row Definitions**, and then open the row definition to modify.</span></span>
2. <span data-ttu-id="30fbf-149">En el menú **Editar** , haga clic en **Insertar filas de dimensiones**.</span><span class="sxs-lookup"><span data-stu-id="30fbf-149">On the **Edit** menu, click **Insert Rows from Dimensions**.</span></span>
3. <span data-ttu-id="30fbf-150">En el cuadro de diálogo **Insertar filas desde dimensiones**, en la fila **Dimensiones**, seleccione la celda en la que la dimensión se transferirá a la definición de filas y, a continuación, haga clic en **Todas &&&**.</span><span class="sxs-lookup"><span data-stu-id="30fbf-150">In the **Insert Rows from Dimensions** dialog box, in the **Dimensions** row, select the cell for the dimension to transfer to the row definition, and then click **All &&&**.</span></span>
4. <span data-ttu-id="30fbf-151">Para limitar la definición de filas a un intervalo específico de valores de dimensión, especifique el valor de dimensión de inicio en la celda **Inicio del intervalo de la dimensión** y después especifique el valor de dimensión final en la celda **Fin del intervalo de la dimensión**.</span><span class="sxs-lookup"><span data-stu-id="30fbf-151">To limit the row definition to a specific range of dimension values, enter the starting dimension value in the **Dimension Range Start** cell, and then enter the ending dimension value in the **Dimension Range End** cell.</span></span> <span data-ttu-id="30fbf-152">Para incluir todos los valores de la dimensión seleccionada, deje estas celdas en blanco.</span><span class="sxs-lookup"><span data-stu-id="30fbf-152">To include all values for the selected dimension, leave these cells empty.</span></span>

    > [!NOTE]
    > <span data-ttu-id="30fbf-153">Según la manera en que la base de datos ERP intercala los datos, es posible que los caracteres comodín (\* o ?) en los intervalos de dimensión no devuelvan todos los resultados esperados.</span><span class="sxs-lookup"><span data-stu-id="30fbf-153">Wildcard characters (\* or ?) in dimension ranges might not return all the results that you want, depending on how the ERP database collates data.</span></span>

5. <span data-ttu-id="30fbf-154">En el campo **Código de la fila de inicio**, especifique el código de la fila del primer valor de dimensión que se agregará a la definición de filas.</span><span class="sxs-lookup"><span data-stu-id="30fbf-154">In the **Starting row code** field, specify the row code for the first dimension value to add to the row definition.</span></span>
6. <span data-ttu-id="30fbf-155">En el campo **Incrementar cada fila en**, especifique el hueco entre los códigos de fila consecutivas.</span><span class="sxs-lookup"><span data-stu-id="30fbf-155">In the **Increment each row by** field, specify the gap between consecutive row codes.</span></span> <span data-ttu-id="30fbf-156">Por ejemplo, si el código de la primera fila es 100 y el valor de incremento es 30, las primeras nuevas filas tienen los códigos 100, 130, 160, 190 y 220.</span><span class="sxs-lookup"><span data-stu-id="30fbf-156">For example, if the first row code is 100, and the increment value is 30, the first new rows have the codes 100, 130, 160, 190, and 220.</span></span> <span data-ttu-id="30fbf-157">Use un valor de incremento que proporcione espacio para insertar nuevas filas de formato y de fórmula.</span><span class="sxs-lookup"><span data-stu-id="30fbf-157">Use an increment value that provides enough space to insert new format and formula rows.</span></span>
7. <span data-ttu-id="30fbf-158">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="30fbf-158">Click **OK**.</span></span> <span data-ttu-id="30fbf-159">Para cada uno de los valores de dimensión seleccionados, se agrega una línea a la definición de filas.</span><span class="sxs-lookup"><span data-stu-id="30fbf-159">For each of the selected dimension values, one line is added to the row definition.</span></span>

## <a name="adjust-rounding-in-a-row-definition"></a><span data-ttu-id="30fbf-160"> Ajuste de redondeo en una definición de filas</span><span class="sxs-lookup"><span data-stu-id="30fbf-160">Adjust rounding in a row definition</span></span>
<span data-ttu-id="30fbf-161">Si tiene un balance de situación donde se redondean los importes, los totales pueden estar desequilibrados.</span><span class="sxs-lookup"><span data-stu-id="30fbf-161">If you have a balance sheet where the amounts are rounded, the totals might not balance.</span></span> <span data-ttu-id="30fbf-162">Este problema puede producirse si, por ejemplo, utiliza la opción de redondeo en un informe de balance de situación y la definición del informe también especifica el redondeo.</span><span class="sxs-lookup"><span data-stu-id="30fbf-162">This issue can occur if, for example, you use the rounding option on a balance sheet report and the report definition also specifies rounding.</span></span> <span data-ttu-id="30fbf-163">Puede utilizar la opción **Ajuste de redondeo** en la definición de filas para equilibrar los importes de los balances de situación.</span><span class="sxs-lookup"><span data-stu-id="30fbf-163">You can use the **Rounding adjustment** option in the row definition to balance the amounts in the balance sheets.</span></span> <span data-ttu-id="30fbf-164">Puede desactivar el redondeo o modificarlo en la pestaña **Configuración** de la definición del informe.</span><span class="sxs-lookup"><span data-stu-id="30fbf-164">You can turn rounding off or modify it on the **Settings** tab of the report definition.</span></span> <span data-ttu-id="30fbf-165">En la siguiente tabla se muestra cómo se redondean los importes.</span><span class="sxs-lookup"><span data-stu-id="30fbf-165">The following table shows how amounts are rounded.</span></span> <span data-ttu-id="30fbf-166">En esta tabla, los totales de las filas 100 y 200 difieren cuando se activa el redondeo.</span><span class="sxs-lookup"><span data-stu-id="30fbf-166">In this table, the totals of rows 100 and 200 differ when rounding is turned on.</span></span>

| <span data-ttu-id="30fbf-167">Código de la fila</span><span class="sxs-lookup"><span data-stu-id="30fbf-167">Row code</span></span> | <span data-ttu-id="30fbf-168">Importes sin redondeo</span><span class="sxs-lookup"><span data-stu-id="30fbf-168">Amounts without rounding</span></span> | <span data-ttu-id="30fbf-169">Importe con redondeo a millares enteros</span><span class="sxs-lookup"><span data-stu-id="30fbf-169">Amount with rounding to whole thousands</span></span> |
|----------|--------------------------|-----------------------------------------|
| <span data-ttu-id="30fbf-170">100</span><span class="sxs-lookup"><span data-stu-id="30fbf-170">100</span></span>      | <span data-ttu-id="30fbf-171">3,600</span><span class="sxs-lookup"><span data-stu-id="30fbf-171">3,600</span></span>                    | <span data-ttu-id="30fbf-172">4</span><span class="sxs-lookup"><span data-stu-id="30fbf-172">4</span></span>                                       |
| <span data-ttu-id="30fbf-173">200</span><span class="sxs-lookup"><span data-stu-id="30fbf-173">200</span></span>      | <span data-ttu-id="30fbf-174">3,700</span><span class="sxs-lookup"><span data-stu-id="30fbf-174">3,700</span></span>                    | <span data-ttu-id="30fbf-175">4</span><span class="sxs-lookup"><span data-stu-id="30fbf-175">4</span></span>                                       |
| <span data-ttu-id="30fbf-176">Total</span><span class="sxs-lookup"><span data-stu-id="30fbf-176">Total</span></span>    | <span data-ttu-id="30fbf-177">7,300</span><span class="sxs-lookup"><span data-stu-id="30fbf-177">7,300</span></span>                    | <span data-ttu-id="30fbf-178">8</span><span class="sxs-lookup"><span data-stu-id="30fbf-178">8</span></span>                                       |

<span data-ttu-id="30fbf-179">Para ajustar el redondeo en un balance de situación, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="30fbf-179">To adjust rounding in a balance sheet, follow these steps.</span></span>

1. <span data-ttu-id="30fbf-180">En el diseñador del informes, haga clic en **Definiciones de filas** y después abra la definición de fila para modificarla.</span><span class="sxs-lookup"><span data-stu-id="30fbf-180">In Report Designer, click **Row Definitions**, and then open the row definition to modify.</span></span>
2. <span data-ttu-id="30fbf-181">En el menú **Editar**, haga clic en **Ajuste de redondeo**.</span><span class="sxs-lookup"><span data-stu-id="30fbf-181">On the **Edit** menu, click **Rounding Adjustment**.</span></span>
3. <span data-ttu-id="30fbf-182">En el cuadro **Ajustes de redondeo**, especifique los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="30fbf-182">In the **Rounding Adjustments** dialog box, enter the following values:</span></span>

    - <span data-ttu-id="30fbf-183">**Fila de ajuste de redondeo:** el código de fila para la fila que se debe ajustar para equilibrar el balance de situación.</span><span class="sxs-lookup"><span data-stu-id="30fbf-183">**Rounding adjustment row** – The row code for the row that should be adjusted to balance the balance sheet.</span></span>
    - <span data-ttu-id="30fbf-184">**Fila de activos totales:** el código de fila para la fila en el balance de situación que contiene los activos totales.</span><span class="sxs-lookup"><span data-stu-id="30fbf-184">**Total assets row** – The row code for the row in the balance sheet that contains the total assets.</span></span>
    - <span data-ttu-id="30fbf-185">**Fila de pasivos totales:** el código de fila para la fila en el balance de situación que contiene los pasivos totales.</span><span class="sxs-lookup"><span data-stu-id="30fbf-185">**Total liabilities and equity row** – The row code for the row in the balance sheet that contains the total liabilities and equity.</span></span>
    - <span data-ttu-id="30fbf-186">**Límite de ajuste del importe**: un número entero positivo que especifica el límite en ajustes automáticos.</span><span class="sxs-lookup"><span data-stu-id="30fbf-186">**Adjustment amount limit** – A positive whole number that specifies the limit on automatic adjustments.</span></span> <span data-ttu-id="30fbf-187">Este importe se compara con el valor absoluto de la diferencia de redondeo real.</span><span class="sxs-lookup"><span data-stu-id="30fbf-187">This amount is compared with the absolute value of the actual rounding difference.</span></span>

    > [!NOTE]
    > <span data-ttu-id="30fbf-188">Estos códigos de fila deben vincularse a los datos financieros.</span><span class="sxs-lookup"><span data-stu-id="30fbf-188">These row codes must be linked to your financial data.</span></span> <span data-ttu-id="30fbf-189">Es decir, la fila debe tener un valor de dimensión en su celda **Vínculo a dimensiones financieras**.</span><span class="sxs-lookup"><span data-stu-id="30fbf-189">In other words, the row must have a dimension value in its **Link to Financial Dimensions** cell.</span></span> <span data-ttu-id="30fbf-190">No **haga** referenceia a una fila de descripción (**DESC**), calculada (**CALC**) o de totales (**TOT**).</span><span class="sxs-lookup"><span data-stu-id="30fbf-190">Do **not** reference a description (**DESC**), calculated (**CALC**), or totaled (**TOT**) row.</span></span>

<span data-ttu-id="30fbf-191">Los importes en el balance de situación se equilibrarán ahora cuando se activa el redondeo.</span><span class="sxs-lookup"><span data-stu-id="30fbf-191">The amounts in your balance sheet will now balance evenly when rounding is turned on.</span></span>

> [!NOTE]
> <span data-ttu-id="30fbf-192">El límite de ajuste se aplica en función de la opción **Precisión de redondeo** especificada para la definición del informe.</span><span class="sxs-lookup"><span data-stu-id="30fbf-192">The adjustment limit is applied based on the **Rounding precision** option that is specified for the report definition.</span></span> <span data-ttu-id="30fbf-193">Por ejemplo, si redondea el informe en millares y especifica **2** en el cuadro **Límite del ajuste de importe**, recibirá un mensaje de advertencia cuando el valor del campo **Fila de ajuste de redondeo** aumenta o disminuye por más de 2.000.</span><span class="sxs-lookup"><span data-stu-id="30fbf-193">For example, if you round your report to thousands and enter **2** in the **Adjustment amount limit** field, you receive a warning message when the value in the **Rounding adjustment row** field increases or decreases by more than 2,000.</span></span>

## <a name="format-row-and-column-text"></a><span data-ttu-id="30fbf-194">Dar formato al texto de la columna y la fila</span><span class="sxs-lookup"><span data-stu-id="30fbf-194">Format row and column text</span></span>
<span data-ttu-id="30fbf-195">Puede personalizar el aspecto de sus informes cambiando fuentes y dando formato al texto.</span><span class="sxs-lookup"><span data-stu-id="30fbf-195">You can customize the appearance of your reports by changing fonts and formatting text.</span></span> <span data-ttu-id="30fbf-196">En las secciones siguientes se explica cómo dar formato al aspecto de filas y columnas en los informes.</span><span class="sxs-lookup"><span data-stu-id="30fbf-196">The following sections explain how to format the appearance of rows and columns on reports.</span></span>

### <a name="manage-font-styles"></a><span data-ttu-id="30fbf-197">Gestionar estilos de fuentes</span><span class="sxs-lookup"><span data-stu-id="30fbf-197">Manage font styles</span></span>

<span data-ttu-id="30fbf-198">Puede crear y modificar estilos de fuente para el informe.</span><span class="sxs-lookup"><span data-stu-id="30fbf-198">You can create and modify font styles for your report.</span></span> <span data-ttu-id="30fbf-199">A continuación, puede aplicar esos estilos al documento o a una fila o columna concreta de un informe.</span><span class="sxs-lookup"><span data-stu-id="30fbf-199">You can then apply those styles to the document, or to a specific row or column on a report.</span></span>

<table>
<tbody>
<tr>
<td><span data-ttu-id="30fbf-200"><strong>Crear un estilo de fuente</strong></span><span class="sxs-lookup"><span data-stu-id="30fbf-200"><strong>Create a font style</strong></span></span></td>
<td>
<ol>
<li><span data-ttu-id="30fbf-201">En el diseñador de informes, en el menú <strong>Formato </strong>, haga clic en <strong>Estilos y formato</strong>.</span><span class="sxs-lookup"><span data-stu-id="30fbf-201">In Report Designer, on the <strong>Format</strong> menu, click <strong>Styles and Formatting</strong>.</span></span></li>
<li><span data-ttu-id="30fbf-202">En el cuadro de diálogo <strong>Estilos y formato</strong>, haga clic en <strong>Nuevo</strong> y especifique un nombre único para el estilo nuevo.</span><span class="sxs-lookup"><span data-stu-id="30fbf-202">In the <strong>Styles and Formatting</strong> dialog box, click <strong>New</strong>, and then enter a unique name for the new style.</span></span></li>
<li><span data-ttu-id="30fbf-203">Seleccione las fuentes y haga clic en <strong>Aceptar</strong>.</span><span class="sxs-lookup"><span data-stu-id="30fbf-203">Make your font selections, and then click <strong>OK</strong>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="30fbf-204"><strong>Modificar un estilo de fuente</strong></span><span class="sxs-lookup"><span data-stu-id="30fbf-204"><strong>Modify a font style</strong></span></span></td>
<td>
<ol>
<li><span data-ttu-id="30fbf-205">En el diseñador de informes, en el menú <strong>Formato </strong>, haga clic en <strong>Estilos y formato</strong>.</span><span class="sxs-lookup"><span data-stu-id="30fbf-205">In Report Designer, on the <strong>Format</strong> menu, click <strong>Styles and Formatting</strong>.</span></span></li>
<li><span data-ttu-id="30fbf-206">En el cuadro de diálogo <strong>Estilos y formato</strong>, seleccione un estilo para modificar y haga clic en <strong>Modificar</strong>.</span><span class="sxs-lookup"><span data-stu-id="30fbf-206">In the <strong>Styles and Formatting</strong> dialog box, select a style to modify, and then click <strong>Modify</strong>.</span></span></li>
<li><span data-ttu-id="30fbf-207">Seleccione las fuentes y haga clic en <strong>Aceptar</strong>.</span><span class="sxs-lookup"><span data-stu-id="30fbf-207">Make your font selections, and then click <strong>OK</strong>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="30fbf-208"><strong>Aplicar un estilo de fuente</strong></span><span class="sxs-lookup"><span data-stu-id="30fbf-208"><strong>Apply a font style</strong></span></span></td>
<td>
<ol>
<li><span data-ttu-id="30fbf-209">En el diseñador de informes, e una definición o definición de columna, o en encabezados y pies de página, seleccione una o más celdas.</span><span class="sxs-lookup"><span data-stu-id="30fbf-209">In Report Designer, in a definition or column definition, or in headers and footers, select one or more cells.</span></span></li>
<li><span data-ttu-id="30fbf-210">En la lista <strong>Estilo</strong> de la barra de herramientas, seleccione un estilo de fuente.</span><span class="sxs-lookup"><span data-stu-id="30fbf-210">In the <strong>Style</strong> list on the toolbar, select a font style.</span></span></li>
</ol>
</td>
</tr>
</tbody>
</table>

### <a name="format-row-text"></a><span data-ttu-id="30fbf-211">Dar formato al texto de la fila</span><span class="sxs-lookup"><span data-stu-id="30fbf-211">Format row text</span></span>

<span data-ttu-id="30fbf-212">El formato que se especifica en la definición de la fila anula el formato que se especifica en la definición de la columna y la definición del informe.</span><span class="sxs-lookup"><span data-stu-id="30fbf-212">The formatting that is specified in the row definition overrides any formatting that is specified in the column definition and the report definition.</span></span> <span data-ttu-id="30fbf-213">Puede modificar el formato de texto mediante los controles de la barra de herramientas de formato.</span><span class="sxs-lookup"><span data-stu-id="30fbf-213">You can modify the text format by using the controls on the formatting toolbar.</span></span> <span data-ttu-id="30fbf-214">Estos controles son estándar de Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="30fbf-214">These controls are standard Microsoft Windows controls.</span></span>

1. <span data-ttu-id="30fbf-215">En el Diseñador de informes, abra la definición de fila que desee modificar.</span><span class="sxs-lookup"><span data-stu-id="30fbf-215">In Report Designer, open the row definition to modify.</span></span>
2. <span data-ttu-id="30fbf-216">Seleccione las celdas a las que desea dar formato.</span><span class="sxs-lookup"><span data-stu-id="30fbf-216">Select the cells to format.</span></span> <span data-ttu-id="30fbf-217">Para seleccionar varias celdas, mantenga presionada la tecla Ctrl mientras selecciona la celda.</span><span class="sxs-lookup"><span data-stu-id="30fbf-217">To select multiple cells, hold down the Ctrl key while you select the cell.</span></span>
3. <span data-ttu-id="30fbf-218">Haga clic en el botón de la barra de herramientas del formato que desea aplicar.</span><span class="sxs-lookup"><span data-stu-id="30fbf-218">Click the toolbar button of the format to apply.</span></span> <span data-ttu-id="30fbf-219">Por ejemplo, para aplicar sangría a una fila, seleccione la fila y luego haga clic en **Aumentar sangría** ![Aumentar sangría](media/indent.gif "Aumentar sangría") en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="30fbf-219">For example, to indent a row, select the row, and then click **Increase Indent** ![Increase Indent](media/indent.gif "Increase Indent") on the toolbar.</span></span>

### <a name="adjust-columns-while-you-design-reports"></a><span data-ttu-id="30fbf-220">Ajustar columnas mientras se diseñan informes</span><span class="sxs-lookup"><span data-stu-id="30fbf-220">Adjust columns while you design reports</span></span>

<span data-ttu-id="30fbf-221">Para facilitar ver las columnas en las que está trabajando en la definición de filas, puede ajustar la anchura de una columna y ocultar además (minimizar) o mostrar columnas en el panel de vista.</span><span class="sxs-lookup"><span data-stu-id="30fbf-221">To make it easier to view the columns that you're working on in the row definition, you can adjust the width of a column, and can also hide (minimize) or show columns in the view pane.</span></span> <span data-ttu-id="30fbf-222">Las modificaciones que realice afectan solo al aspecto en pantalla de las columnas.</span><span class="sxs-lookup"><span data-stu-id="30fbf-222">The modifications that you make affect only the on-screen appearance of the columns.</span></span> <span data-ttu-id="30fbf-223">No afectan al formato de las columnas en los informes.</span><span class="sxs-lookup"><span data-stu-id="30fbf-223">They don't affect the column formatting on reports.</span></span>

### <a name="change-the-width-of-a-column-in-the-view-pane"></a><span data-ttu-id="30fbf-224">Cambiar la anchura de una columna en el panel de vista</span><span class="sxs-lookup"><span data-stu-id="30fbf-224">Change the width of a column in the view pane</span></span>

1. <span data-ttu-id="30fbf-225">En el diseñador de informes, abra la definición de filas para modificarla.</span><span class="sxs-lookup"><span data-stu-id="30fbf-225">In Report Designer, open the row definition to modify.</span></span>
2. <span data-ttu-id="30fbf-226">En el menú **Formato**, seleccione **Anchura de columna**.</span><span class="sxs-lookup"><span data-stu-id="30fbf-226">On the **Format** menu, select **Column Width**.</span></span>
3. <span data-ttu-id="30fbf-227">En el cuadro de diálogo **Ancho de columna**, escriba un valor y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="30fbf-227">In the **Column Width** dialog box, enter a value, and then click **OK**.</span></span> <span data-ttu-id="30fbf-228">De forma alternativa, también puede arrastrar el límite derecho de una celda del encabezado de columna para cambiar el ancho de la columna.</span><span class="sxs-lookup"><span data-stu-id="30fbf-228">Alternatively, you can drag the right boundary of a column heading cell to change the width of the column.</span></span>

### <a name="hide-columns-in-the-view-pane"></a><span data-ttu-id="30fbf-229">Ocultar columnas en el panel de vista</span><span class="sxs-lookup"><span data-stu-id="30fbf-229">Hide columns in the view pane</span></span>

1. <span data-ttu-id="30fbf-230">En el diseñador de informes, abra la definición de filas para modificarla.</span><span class="sxs-lookup"><span data-stu-id="30fbf-230">In Report Designer, open the row definition to modify.</span></span>
2. <span data-ttu-id="30fbf-231">Seleccione las columnas que desea minimizar.</span><span class="sxs-lookup"><span data-stu-id="30fbf-231">Select the column or columns to minimize.</span></span>
3. <span data-ttu-id="30fbf-232">Haga clic con el botón secundario y, a continuación, haga clic en **Ocultar**.</span><span class="sxs-lookup"><span data-stu-id="30fbf-232">Right-click, and then click **Hide**.</span></span>

### <a name="show-all-hidden-columns-in-the-view-pane"></a><span data-ttu-id="30fbf-233">Mostrar todas las columnas ocultas en el panel de vista</span><span class="sxs-lookup"><span data-stu-id="30fbf-233">Show all hidden columns in the view pane</span></span>

1. <span data-ttu-id="30fbf-234">En el diseñador de informes, abra la definición de filas para modificarla.</span><span class="sxs-lookup"><span data-stu-id="30fbf-234">In Report Designer, open the row definition to modify.</span></span>
2. <span data-ttu-id="30fbf-235">Haga clic con el botón secundario en la columna minimizada que desee mostrar y, a continuación, haga clic en **No ocultar**.</span><span class="sxs-lookup"><span data-stu-id="30fbf-235">Right-click the minimized column to display, and then click **Unhide**.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="30fbf-236">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="30fbf-236">Additional resources</span></span>

[<span data-ttu-id="30fbf-237">Informes financieros</span><span class="sxs-lookup"><span data-stu-id="30fbf-237">Financial reporting</span></span>](financial-reporting-intro.md)
