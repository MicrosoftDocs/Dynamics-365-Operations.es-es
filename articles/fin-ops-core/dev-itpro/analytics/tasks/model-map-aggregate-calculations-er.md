---
title: Usar las configuraciones de asignación de modelo para cálculos agregados en el nivel de la base de datos
description: Este tema describe cómo diseñar una nueva configuración de asignación de modelo de informes electrónicos y utilizar las funciones de ER integradas para realizar cálculos agregados eficientes.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6a392697f6b91bc6555d0d72d09ecd7da32e1a3f
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5094274"
---
# <a name="use-model-mapping-configurations-for-aggregate-calculations-at-the-database-level"></a><span data-ttu-id="7a842-103">Usar las configuraciones de asignación de modelo para cálculos agregados en el nivel de la base de datos</span><span class="sxs-lookup"><span data-stu-id="7a842-103">Use model mapping configurations for aggregate calculations at the database level</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7a842-104">Este procedimiento proporciona información acerca de cómo diseñar una nueva configuración de asignación de modelo de informes electrónicos (ER) y utilizar las funciones de ER integradas para realizar cálculos agregados eficientes.</span><span class="sxs-lookup"><span data-stu-id="7a842-104">This procedure provides information about how to design a new Electronic reporting (ER) model mapping configuration and use built-in ER functions for efficient aggregate calculations.</span></span> <span data-ttu-id="7a842-105">En este procedimiento, creará una configuración para la empresa de ejemplo Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="7a842-105">In this procedure you will create a configuration for the sample company, Litware, Inc.</span></span> 

<span data-ttu-id="7a842-106">Este procedimiento se ha creado para los usuarios con los roles Administrador del sistema o Desarrollador de informes electrónicos asignados.</span><span class="sxs-lookup"><span data-stu-id="7a842-106">This procedure is created for users with the assigned role of System administrator or Electronic reporting developer.</span></span> <span data-ttu-id="7a842-107">Estos pasos se pueden completar mediante cualquier conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="7a842-107">These steps can be completed using any dataset.</span></span>

 <span data-ttu-id="7a842-108">Para completar estos pasos, primero debe completar los pasos del procedimiento “ER mejora la eficiencia de los cálculos globales efectuándolos en el nivel de la base de datos (Parte 1: Preparación de las configuraciones)”.</span><span class="sxs-lookup"><span data-stu-id="7a842-108">To complete these steps, you must first complete the steps in the procedure, "ER improves the efficiency of aggregate calculations by performing them on database level (Part 1: Prepare configurations)."</span></span>

1. <span data-ttu-id="7a842-109">Vaya a Administración de la organización > Informes electrónicos > Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="7a842-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="7a842-110">En el árbol, expanda "Intrastat modelo".</span><span class="sxs-lookup"><span data-stu-id="7a842-110">In the tree, expand 'Intrastat model'.</span></span>
3. <span data-ttu-id="7a842-111">En el árbol, seleccione 'Intrastat model\Intrastat sample mapping'.</span><span class="sxs-lookup"><span data-stu-id="7a842-111">In the tree, select 'Intrastat model\Intrastat sample mapping'.</span></span>
4. <span data-ttu-id="7a842-112">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="7a842-112">Click Designer.</span></span>
5. <span data-ttu-id="7a842-113">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="7a842-113">Click Designer.</span></span>
6. <span data-ttu-id="7a842-114">En el árbol, seleccione "Dynamics 365 for Operations\Registros de tabla".</span><span class="sxs-lookup"><span data-stu-id="7a842-114">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
7. <span data-ttu-id="7a842-115">Haga clic en Agregar raíz.</span><span class="sxs-lookup"><span data-stu-id="7a842-115">Click Add root.</span></span>
    * <span data-ttu-id="7a842-116">Agregar un nuevo origen de datos que representa los registros que desea agrupar.</span><span class="sxs-lookup"><span data-stu-id="7a842-116">Add a new data source representing records you want to group.</span></span>  
8. <span data-ttu-id="7a842-117">En el campo Nombre, escriba "Transacciones".</span><span class="sxs-lookup"><span data-stu-id="7a842-117">In the Name field, type 'Transactions'.</span></span>
    * <span data-ttu-id="7a842-118">Transacciones</span><span class="sxs-lookup"><span data-stu-id="7a842-118">Transactions</span></span>  
9. <span data-ttu-id="7a842-119">En el campo Tabla, escriba "Intrastat".</span><span class="sxs-lookup"><span data-stu-id="7a842-119">In the Table field, type 'Intrastat'.</span></span>
    * <span data-ttu-id="7a842-120">intrastat</span><span class="sxs-lookup"><span data-stu-id="7a842-120">Intrastat</span></span>  
10. <span data-ttu-id="7a842-121">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="7a842-121">Click OK.</span></span>
11. <span data-ttu-id="7a842-122">En el árbol, seleccione "Funciones\Agrupar por".</span><span class="sxs-lookup"><span data-stu-id="7a842-122">In the tree, select 'Functions\Group by'.</span></span>
    * <span data-ttu-id="7a842-123">Este tipo de origen de datos se utiliza para especificar un nuevo origen de datos en el tiempo de ejecución para agrupar registros y calcular las agregaciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="7a842-123">This data source type is used to introduce a new data source at run-time to group records and to calculate required aggregations.</span></span>  
12. <span data-ttu-id="7a842-124">Haga clic en Agregar raíz.</span><span class="sxs-lookup"><span data-stu-id="7a842-124">Click Add root.</span></span>
13. <span data-ttu-id="7a842-125">En el campo Nombre, escriba "TransactionsGroups".</span><span class="sxs-lookup"><span data-stu-id="7a842-125">In the Name field, type 'TransactionsGroups'.</span></span>
    * <span data-ttu-id="7a842-126">TransactionsGroups</span><span class="sxs-lookup"><span data-stu-id="7a842-126">TransactionsGroups</span></span>  
14. <span data-ttu-id="7a842-127">Haga clic en Editar grupo por.</span><span class="sxs-lookup"><span data-stu-id="7a842-127">Click Edit group by.</span></span>
15. <span data-ttu-id="7a842-128">En el árbol, seleccione Transacciones.</span><span class="sxs-lookup"><span data-stu-id="7a842-128">In the tree, select 'Transactions'.</span></span>
    * <span data-ttu-id="7a842-129">Seleccione el origen de datos agregado del tipo "Lista de registros" que representa los registros que desea agrupar.</span><span class="sxs-lookup"><span data-stu-id="7a842-129">Select the added data source of the 'Record list' type that represents the records that you want to group.</span></span>  
16. <span data-ttu-id="7a842-130">Haga clic en Agregar campo a.</span><span class="sxs-lookup"><span data-stu-id="7a842-130">Click Add field to.</span></span>
17. <span data-ttu-id="7a842-131">Haga clic en Elementos para agrupar.</span><span class="sxs-lookup"><span data-stu-id="7a842-131">Click What to group.</span></span>
18. <span data-ttu-id="7a842-132">En el árbol, expanda Transacciones.</span><span class="sxs-lookup"><span data-stu-id="7a842-132">In the tree, expand 'Transactions'.</span></span>
19. <span data-ttu-id="7a842-133">En el árbol, seleccione 'Transactions\Direction'.</span><span class="sxs-lookup"><span data-stu-id="7a842-133">In the tree, select 'Transactions\Direction'.</span></span>
20. <span data-ttu-id="7a842-134">Haga clic en Agregar campo a.</span><span class="sxs-lookup"><span data-stu-id="7a842-134">Click Add field to.</span></span>
21. <span data-ttu-id="7a842-135">Haga clic en Campos agrupados.</span><span class="sxs-lookup"><span data-stu-id="7a842-135">Click Grouped fields.</span></span>
    * <span data-ttu-id="7a842-136">Seleccione el campo para especificar el nivel de agrupación.</span><span class="sxs-lookup"><span data-stu-id="7a842-136">Select the field to specify the grouping level.</span></span> <span data-ttu-id="7a842-137">En función de esta selección, el origen de datos devolverá en el tiempo de ejecución tantos grupos de transacciones como códigos de dirección que se deben cumplir en la tabla Intrastat.</span><span class="sxs-lookup"><span data-stu-id="7a842-137">Based on this selection, the data source will return at run-time as many groups of transactions as there are direction codes that will be met in the Intrastat table.</span></span>  
22. <span data-ttu-id="7a842-138">En el árbol, seleccione 'Transactions\Invoice amount(AmountMST)'.</span><span class="sxs-lookup"><span data-stu-id="7a842-138">In the tree, select 'Transactions\Invoice amount(AmountMST)'.</span></span>
    * <span data-ttu-id="7a842-139">Seleccione el campo para especificar el origen del cálculo de agregación.</span><span class="sxs-lookup"><span data-stu-id="7a842-139">Select the field to specify the source for aggregation calculation.</span></span>  
23. <span data-ttu-id="7a842-140">Haga clic en Agregar campo a.</span><span class="sxs-lookup"><span data-stu-id="7a842-140">Click Add field to.</span></span>
24. <span data-ttu-id="7a842-141">Haga clic en Campos de agregación.</span><span class="sxs-lookup"><span data-stu-id="7a842-141">Click Aggregation fields.</span></span>
25. <span data-ttu-id="7a842-142">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7a842-142">In the list, mark the selected row.</span></span>
26. <span data-ttu-id="7a842-143">En el campo Método, seleccione 'Suma'.</span><span class="sxs-lookup"><span data-stu-id="7a842-143">In the Method field, select 'Sum'.</span></span>
    * <span data-ttu-id="7a842-144">Seleccionar el tipo de agregación.</span><span class="sxs-lookup"><span data-stu-id="7a842-144">Select the aggregation type.</span></span>  
27. <span data-ttu-id="7a842-145">En el campo Nombre, escriba "SumOfAmountMST".</span><span class="sxs-lookup"><span data-stu-id="7a842-145">In the Name field, type 'SumOfAmountMST'.</span></span>
    * <span data-ttu-id="7a842-146">Especifique el nombre de esta agregación en el origen de datos configurado.</span><span class="sxs-lookup"><span data-stu-id="7a842-146">Specify the name of this aggregation in the configured data source.</span></span>  
28. <span data-ttu-id="7a842-147">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="7a842-147">Click Save.</span></span>
    * <span data-ttu-id="7a842-148">Tenga en cuenta que el campo "Ejecución en" indica que esta agrupación se llevará a cabo en el tiempo de ejecución en la base de datos SQL.</span><span class="sxs-lookup"><span data-stu-id="7a842-148">Note that the 'Execution at' field indicates that this grouping will be performed at run-time in the SQL database.</span></span>  
29. <span data-ttu-id="7a842-149">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7a842-149">Close the page.</span></span>
30. <span data-ttu-id="7a842-150">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="7a842-150">Click OK.</span></span>
31. <span data-ttu-id="7a842-151">En el árbol, expanda 'Totals'.</span><span class="sxs-lookup"><span data-stu-id="7a842-151">In the tree, expand 'Totals'.</span></span>
32. <span data-ttu-id="7a842-152">En el árbol, expanda 'TransactionsGroups'.</span><span class="sxs-lookup"><span data-stu-id="7a842-152">In the tree, expand 'TransactionsGroups'.</span></span>
33. <span data-ttu-id="7a842-153">En el árbol, expanda 'TransactionsGroups\aggregated'.</span><span class="sxs-lookup"><span data-stu-id="7a842-153">In the tree, expand 'TransactionsGroups\aggregated'.</span></span>
34. <span data-ttu-id="7a842-154">En el árbol, seleccione 'TransactionsGroups\aggregated\SumOfAmountMST'.</span><span class="sxs-lookup"><span data-stu-id="7a842-154">In the tree, select 'TransactionsGroups\aggregated\SumOfAmountMST'.</span></span>
35. <span data-ttu-id="7a842-155">En el árbol, seleccione 'Totals\Total invoice value(TotalInvoiceValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded')'.</span><span class="sxs-lookup"><span data-stu-id="7a842-155">In the tree, select 'Totals\Total invoice value(TotalInvoiceValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded')'.</span></span>
36. <span data-ttu-id="7a842-156">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="7a842-156">Click Bind.</span></span>
    * <span data-ttu-id="7a842-157">Basándose en este valor, este origen de datos calculará la suma de los valores del campo “AmountMST” para cada grupo de transacciones.</span><span class="sxs-lookup"><span data-stu-id="7a842-157">Based on this setting, this data source will calculate the sum of values of the 'AmountMST' field for each groups of transactions.</span></span> <span data-ttu-id="7a842-158">Este cálculo de agregaciones estará disponible como artículo TransactionsGroups.aggregated.TotalAmount.</span><span class="sxs-lookup"><span data-stu-id="7a842-158">This aggregation calculation will be available as TransactionsGroups.aggregated.TotalAmount item.</span></span>  
37. <span data-ttu-id="7a842-159">En el árbol, expanda 'TransactionsGroups'.</span><span class="sxs-lookup"><span data-stu-id="7a842-159">In the tree, expand 'TransactionsGroups'.</span></span>
38. <span data-ttu-id="7a842-160">En el árbol, seleccione 'TransactionsGroups'.</span><span class="sxs-lookup"><span data-stu-id="7a842-160">In the tree, select 'TransactionsGroups'.</span></span>
39. <span data-ttu-id="7a842-161">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="7a842-161">Click Edit.</span></span>
40. <span data-ttu-id="7a842-162">Haga clic en Editar grupo por.</span><span class="sxs-lookup"><span data-stu-id="7a842-162">Click Edit group by.</span></span>
41. <span data-ttu-id="7a842-163">En el árbol, expanda Transacciones.</span><span class="sxs-lookup"><span data-stu-id="7a842-163">In the tree, expand 'Transactions'.</span></span>
42. <span data-ttu-id="7a842-164">En el árbol, seleccione 'Transactions\Invoice amount(AmountMST)'.</span><span class="sxs-lookup"><span data-stu-id="7a842-164">In the tree, select 'Transactions\Invoice amount(AmountMST)'.</span></span>
43. <span data-ttu-id="7a842-165">Haga clic en Agregar campo a.</span><span class="sxs-lookup"><span data-stu-id="7a842-165">Click Add field to.</span></span>
44. <span data-ttu-id="7a842-166">Haga clic en Campos de agregación.</span><span class="sxs-lookup"><span data-stu-id="7a842-166">Click Aggregation fields.</span></span>
45. <span data-ttu-id="7a842-167">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7a842-167">In the list, mark the selected row.</span></span>
46. <span data-ttu-id="7a842-168">En el campo Método, seleccione 'Máx'.</span><span class="sxs-lookup"><span data-stu-id="7a842-168">In the Method field, select 'Max'.</span></span>
47. <span data-ttu-id="7a842-169">En el campo Nombre, escriba 'MaxOfAmountMST'.</span><span class="sxs-lookup"><span data-stu-id="7a842-169">In the Name field, type 'MaxOfAmountMST'.</span></span>
48. <span data-ttu-id="7a842-170">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="7a842-170">Click Save.</span></span>
    * <span data-ttu-id="7a842-171">Actualmente, la ejecución de los orígenes de datos GROUPBY se puede traducir al nivel de la base de datos SQL con algunas limitaciones.</span><span class="sxs-lookup"><span data-stu-id="7a842-171">Currently, the execution of GROUPBY data sources can be translated to the SQL database level with some limitations.</span></span> <span data-ttu-id="7a842-172">La traducción se puede efectuar para los orígenes del tipo "Lista de registros" o los orígenes de datos representados como expresión usando la función FILTRO.</span><span class="sxs-lookup"><span data-stu-id="7a842-172">Translation can be done for either data sources of the 'Record list' type or data sources represented as an expression using the FILTER function.</span></span> <span data-ttu-id="7a842-173">También se puede realizar cuando la única la agregación se configura para un solo campo de los registros de agrupación.</span><span class="sxs-lookup"><span data-stu-id="7a842-173">It can also be done when the only one aggregation is configured for a single field of the grouping records.</span></span>  
    * <span data-ttu-id="7a842-174">Tenga en cuenta que aunque más de una agregación se configuró para el campo de AmountMST, el campo "Ejecución en" sigue indicando que esta agrupación se realizará en el tiempo de ejecución en la base de datos SQL.</span><span class="sxs-lookup"><span data-stu-id="7a842-174">Note that even though more than one aggregation was configured for the AmountMST field, the 'Execution at' field still indicates that this grouping will be performed at run-time in the SQL database.</span></span> <span data-ttu-id="7a842-175">Esto se debe a que una sola agregación está enlazada al artículo del modelo de datos y se usará en el tiempo de ejecución para extraer datos de este origen de datos.</span><span class="sxs-lookup"><span data-stu-id="7a842-175">This is because only one aggregation is bound to the data model item and will be used at run-time to pull data from this data source.</span></span>  
49. <span data-ttu-id="7a842-176">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7a842-176">Close the page.</span></span>
50. <span data-ttu-id="7a842-177">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="7a842-177">Click OK.</span></span>
51. <span data-ttu-id="7a842-178">En el árbol, expanda 'TransactionsGroups'.</span><span class="sxs-lookup"><span data-stu-id="7a842-178">In the tree, expand 'TransactionsGroups'.</span></span>
52. <span data-ttu-id="7a842-179">En el árbol, expanda 'TransactionsGroups\aggregated'.</span><span class="sxs-lookup"><span data-stu-id="7a842-179">In the tree, expand 'TransactionsGroups\aggregated'.</span></span>
53. <span data-ttu-id="7a842-180">En el árbol, expanda 'TransactionsGroups\aggregated\MaxOfAmountMST'.</span><span class="sxs-lookup"><span data-stu-id="7a842-180">In the tree, select 'TransactionsGroups\aggregated\MaxOfAmountMST'.</span></span>
54. <span data-ttu-id="7a842-181">En el árbol, seleccione 'Totals\Total statistical value(TotalStatisticalValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$StatisticalValueRounded')'.</span><span class="sxs-lookup"><span data-stu-id="7a842-181">In the tree, select 'Totals\Total statistical value(TotalStatisticalValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$StatisticalValueRounded')'.</span></span>
55. <span data-ttu-id="7a842-182">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="7a842-182">Click Bind.</span></span>
56. <span data-ttu-id="7a842-183">En el árbol, expanda 'TransactionsGroups'.</span><span class="sxs-lookup"><span data-stu-id="7a842-183">In the tree, expand 'TransactionsGroups'.</span></span>
57. <span data-ttu-id="7a842-184">En el árbol, seleccione 'TransactionsGroups'.</span><span class="sxs-lookup"><span data-stu-id="7a842-184">In the tree, select 'TransactionsGroups'.</span></span>
58. <span data-ttu-id="7a842-185">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="7a842-185">Click Edit.</span></span>
59. <span data-ttu-id="7a842-186">Haga clic en Editar grupo por.</span><span class="sxs-lookup"><span data-stu-id="7a842-186">Click Edit group by.</span></span>
    * <span data-ttu-id="7a842-187">Tenga en cuenta que el campo "Ejecución en" indica que esta agrupación se realizará en la memoria del tiempo de ejecución porque las dos agregaciones del mismo campo están vinculadas a los artículos de modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="7a842-187">Note that the 'Execution at' field indicates that this grouping will be performed at run-time in memory because both aggregations of the same field are bound to the data model items.</span></span>   
60. <span data-ttu-id="7a842-188">En la lista, active o desactive todas las filas.</span><span class="sxs-lookup"><span data-stu-id="7a842-188">In the list, mark or unmark all rows.</span></span>
61. <span data-ttu-id="7a842-189">Haga clic Eliminar.</span><span class="sxs-lookup"><span data-stu-id="7a842-189">Click Delete.</span></span>
62. <span data-ttu-id="7a842-190">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="7a842-190">Click Yes.</span></span>
63. <span data-ttu-id="7a842-191">Haga clic Eliminar.</span><span class="sxs-lookup"><span data-stu-id="7a842-191">Click Delete.</span></span>
64. <span data-ttu-id="7a842-192">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="7a842-192">Click Yes.</span></span>
65. <span data-ttu-id="7a842-193">Haga clic en Agregar campo a.</span><span class="sxs-lookup"><span data-stu-id="7a842-193">Click Add field to.</span></span>
66. <span data-ttu-id="7a842-194">Haga clic en Elementos para agrupar.</span><span class="sxs-lookup"><span data-stu-id="7a842-194">Click What to group.</span></span>
67. <span data-ttu-id="7a842-195">En el árbol, expanda 'Commodity record(Intrastat)'.</span><span class="sxs-lookup"><span data-stu-id="7a842-195">In the tree, expand 'Commodity record(Intrastat)'.</span></span>
68. <span data-ttu-id="7a842-196">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="7a842-196">Click Save.</span></span>
    * <span data-ttu-id="7a842-197">Tenga en cuenta que el campo "Ejecución en" indica que esta agrupación se llevará a cabo en la memoria del tiempo de ejecución aunque no haya agregaciones definidas y el origen de datos seleccionado del tipo "Registros de tabla” haga referencia a la misma tabla de "Intrastat".</span><span class="sxs-lookup"><span data-stu-id="7a842-197">Note that the 'Execution at' field indicates that this grouping will be performed at run-time in memory even though there are no aggregations defined and the selected data source of 'Table records' type refers to the same 'Intrastat' table.</span></span> <span data-ttu-id="7a842-198">Esto se debe a que el origen de datos contiene algunos campos calculados que no se pueden traducir aún al nivel de la base de datos SQL.</span><span class="sxs-lookup"><span data-stu-id="7a842-198">This is because the data source contains some calculated fields which can't yet be translated to the SQL database level.</span></span>  

