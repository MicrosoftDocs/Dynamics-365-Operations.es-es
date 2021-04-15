---
title: 'Informe electrónico Configurar el formato para contar y sumar (Parte 3: Uso de los cálculos para crear la salida)'
description: Este tema describe cómo configurar un formato de informes electrónicos para realizar recuentos y sumas en función de los datos de la salida de texto ya generados. (Parte 3)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7073539ed4c1d9d5acbb0ca84b43538d87fc8b4b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749006"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-3---use-computations-to-make-the-output"></a><span data-ttu-id="3bdd0-104">Informe electrónico Configurar el formato para contar y sumar (Parte 3: Uso de los cálculos para crear la salida)</span><span class="sxs-lookup"><span data-stu-id="3bdd0-104">ER Configure format to do counting and summing (Part 3 - Use computations to make the output)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3bdd0-105">Los pasos siguientes explican cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos puede configurar un formato de informe electrónico (ER) para que realice el recuento y calcule en función de los datos de la salida de texto ya generada.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="3bdd0-106">Estos pasos se pueden llevar a cabo en cualquier empresa.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="3bdd0-107">Para completar estos pasos, primero debe completar los pasos del procedimiento "ER Configurar el formato para contar y sumar (Parte 2: Configuración de cálculos)".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-107">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 2: Configure computations)" procedure.</span></span>

<span data-ttu-id="3bdd0-108">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="configure-this-report-to-use-counting-and-summing-info"></a><span data-ttu-id="3bdd0-109">Configurar este informe para utilizar la información de recuento y suma</span><span class="sxs-lookup"><span data-stu-id="3bdd0-109">Configure this report to use counting and summing info</span></span>
1. <span data-ttu-id="3bdd0-110">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="3bdd0-111">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="3bdd0-112">En el árbol, expanda "Intrastat modelo".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-112">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="3bdd0-113">En el árbol, expanda "Modelo de Intrastat\Intrastat (DE)".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-113">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="3bdd0-114">En el árbol, seleccione "Modelo de Intrastat\Intrastat (DE)\Intrastat (DE) con recuento & suma".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-114">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="3bdd0-115">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-115">Click Designer.</span></span>
7. <span data-ttu-id="3bdd0-116">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-116">Click the Mapping tab.</span></span>
8. <span data-ttu-id="3bdd0-117">Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-117">Click Add root to open the drop dialog.</span></span>
    * <span data-ttu-id="3bdd0-118">Agregue un nuevo origen de datos para obtener la lista de bloqueos memorizados.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-118">Add a new data source to get the list of memorized blocks.</span></span>  
9. <span data-ttu-id="3bdd0-119">En el árbol, seleccione el apartado "Funciones\Campo calculado".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-119">In the tree, select 'Functions\Calculated field'.</span></span>
10. <span data-ttu-id="3bdd0-120">En el campo Nombre, escriba "$BlocksList".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-120">In the Name field, type '$BlocksList'.</span></span>
    * <span data-ttu-id="3bdd0-121">$BlocksList</span><span class="sxs-lookup"><span data-stu-id="3bdd0-121">$BlocksList</span></span>  
11. <span data-ttu-id="3bdd0-122">Haga clic en Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-122">Click Edit formula.</span></span>
12. <span data-ttu-id="3bdd0-123">En el árbol, seleccione "Funciones de recopilación de datos\COLLECTEDLIST".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-123">In the tree, select 'Data collection functions\COLLECTEDLIST'.</span></span>
13. <span data-ttu-id="3bdd0-124">Haga clic en Agregar función.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-124">Click Add function.</span></span>
14. <span data-ttu-id="3bdd0-125">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-125">Click Add data source.</span></span>
15. <span data-ttu-id="3bdd0-126">En el campo Fórmula, especifique "COLLECTEDLIST('$BlockName',".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-126">In the Formula field, enter 'COLLECTEDLIST('$BlockName', '.</span></span>
    * <span data-ttu-id="3bdd0-127">COLLECTEDLIST('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="3bdd0-127">COLLECTEDLIST('$BlockName',</span></span>  
16. <span data-ttu-id="3bdd0-128">En el campo Fórmula, especifique "COLLECTEDLIST('$BlockName', "\*")".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-128">In the Formula field, enter 'COLLECTEDLIST('$BlockName', "\*")'.</span></span>
    * <span data-ttu-id="3bdd0-129">COLLECTEDLIST('$BlockName', "\*")</span><span class="sxs-lookup"><span data-stu-id="3bdd0-129">COLLECTEDLIST('$BlockName', "\*")</span></span>  
17. <span data-ttu-id="3bdd0-130">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-130">Click Save.</span></span>
    * <span data-ttu-id="3bdd0-131">El patrón "\*" significa que todos los bloqueos se incluirán en la lista de este registro.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-131">The pattern "\*" means that all blocks will be included to the list for this record.</span></span>  
18. <span data-ttu-id="3bdd0-132">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-132">Close the page.</span></span>
19. <span data-ttu-id="3bdd0-133">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3bdd0-133">Click OK.</span></span>
20. <span data-ttu-id="3bdd0-134">Haga clic en la ficha Formato.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-134">Click the Format tab.</span></span>
21. <span data-ttu-id="3bdd0-135">En el árbol, seleccione "Intrastat\Datos".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-135">In the tree, select 'Intrastat\Data'.</span></span>
22. <span data-ttu-id="3bdd0-136">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-136">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="3bdd0-137">En el árbol, seleccione "Texto\Secuencia".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-137">In the tree, select 'Text\Sequence'.</span></span>
24. <span data-ttu-id="3bdd0-138">En el campo Nombre, escriba "Totales por bloqueos".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-138">In the Name field, type 'Totals by blocks'.</span></span>
    * <span data-ttu-id="3bdd0-139">Totales por bloqueos</span><span class="sxs-lookup"><span data-stu-id="3bdd0-139">Totals by blocks</span></span>  
25. <span data-ttu-id="3bdd0-140">En el campo Caracteres especiales, seleccione "Línea nueva - Windows (CR LF)".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-140">In the Special characters field, select 'New line - Windows (CR LF)'.</span></span>
26. <span data-ttu-id="3bdd0-141">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3bdd0-141">Click OK.</span></span>
27. <span data-ttu-id="3bdd0-142">En el árbol, seleccione "Intrastat\Datos\Totales por bloqueos".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-142">In the tree, select 'Intrastat\Data\Totals by blocks'.</span></span>
28. <span data-ttu-id="3bdd0-143">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-143">Click Add to open the drop dialog.</span></span>
29. <span data-ttu-id="3bdd0-144">En el árbol, seleccione "Texto\Cadena".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-144">In the tree, select 'Text\String'.</span></span>
30. <span data-ttu-id="3bdd0-145">En el campo Nombre, escriba "Código de bloqueo".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-145">In the Name field, type 'Block code'.</span></span>
    * <span data-ttu-id="3bdd0-146">Código de bloqueo</span><span class="sxs-lookup"><span data-stu-id="3bdd0-146">Block code</span></span>  
31. <span data-ttu-id="3bdd0-147">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3bdd0-147">Click OK.</span></span>
32. <span data-ttu-id="3bdd0-148">Haga clic en Agregar cadena.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-148">Click Add String.</span></span>
33. <span data-ttu-id="3bdd0-149">En el campo Nombre, escriba "Recuento de líneas".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-149">In the Name field, type 'Lines counting'.</span></span>
    * <span data-ttu-id="3bdd0-150">Recuento de líneas</span><span class="sxs-lookup"><span data-stu-id="3bdd0-150">Lines counting</span></span>  
34. <span data-ttu-id="3bdd0-151">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3bdd0-151">Click OK.</span></span>
35. <span data-ttu-id="3bdd0-152">Haga clic en Agregar cadena.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-152">Click Add String.</span></span>
36. <span data-ttu-id="3bdd0-153">En el campo Nombre, escriba "Importe total".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-153">In the Name field, type 'Total amount'.</span></span>
    * <span data-ttu-id="3bdd0-154">Importe total</span><span class="sxs-lookup"><span data-stu-id="3bdd0-154">Total amount</span></span>  
37. <span data-ttu-id="3bdd0-155">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3bdd0-155">Click OK.</span></span>
38. <span data-ttu-id="3bdd0-156">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-156">Click the Mapping tab.</span></span>
39. <span data-ttu-id="3bdd0-157">En el árbol, seleccione "$BlocksList".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-157">In the tree, select '$BlocksList'.</span></span>
40. <span data-ttu-id="3bdd0-158">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-158">Click Bind.</span></span>
    * <span data-ttu-id="3bdd0-159">Cree una línea de resumen para cada bloqueo memorizado.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-159">Create a summary line for each memorized block.</span></span>  
41. <span data-ttu-id="3bdd0-160">Haga clic en la ficha Formato.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-160">Click the Format tab.</span></span>
42. <span data-ttu-id="3bdd0-161">En el árbol, seleccione "Intrastat\Datos\Totales por bloqueos\Código de bloqueo".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-161">In the tree, select 'Intrastat\Data\Totals by blocks\Block code'.</span></span>
43. <span data-ttu-id="3bdd0-162">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-162">Click the Mapping tab.</span></span>
44. <span data-ttu-id="3bdd0-163">Haga clic en Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-163">Click Edit formula.</span></span>
45. <span data-ttu-id="3bdd0-164">En el campo Fórmula, introduzca '"Id. de bloqueo: " & '.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-164">In the Formula field, enter '"Block id: " & '.</span></span>
    * <span data-ttu-id="3bdd0-165">"Id. de bloqueo: " &</span><span class="sxs-lookup"><span data-stu-id="3bdd0-165">"Block id: " &</span></span>  
46. <span data-ttu-id="3bdd0-166">En el árbol, expanda "$BlocksList".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-166">In the tree, expand '$BlocksList'.</span></span>
47. <span data-ttu-id="3bdd0-167">En el árbol, seleccione "$BlocksList\Value".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-167">In the tree, select '$BlocksList\Value'.</span></span>
48. <span data-ttu-id="3bdd0-168">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-168">Click Add data source.</span></span>
49. <span data-ttu-id="3bdd0-169">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-169">Click Save.</span></span>
50. <span data-ttu-id="3bdd0-170">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-170">Close the page.</span></span>
51. <span data-ttu-id="3bdd0-171">Haga clic en la ficha Formato.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-171">Click the Format tab.</span></span>
52. <span data-ttu-id="3bdd0-172">En el árbol, seleccione "Intrastat\Datos\Totales por bloqueos\Recuento de líneas".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-172">In the tree, select 'Intrastat\Data\Totals by blocks\Lines counting'.</span></span>
53. <span data-ttu-id="3bdd0-173">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-173">Click the Mapping tab.</span></span>
54. <span data-ttu-id="3bdd0-174">Haga clic en Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-174">Click Edit formula.</span></span>
    * <span data-ttu-id="3bdd0-175">Cree la salida para el número de líneas para cada bloqueo que se muestra en este informe.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-175">Create output for the number of lines for each block presented in this report.</span></span>  
55. <span data-ttu-id="3bdd0-176">En el campo Fórmula, introduzca '"Número de líneas en este bloqueo: " & '.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-176">In the Formula field, enter '"Number of lines in this block: " & '.</span></span>
    * <span data-ttu-id="3bdd0-177">"Número de líneas en este bloqueo: " &</span><span class="sxs-lookup"><span data-stu-id="3bdd0-177">"Number of lines in this block: " &</span></span>  
56. <span data-ttu-id="3bdd0-178">En el campo Fórmula, introduzca '"Número de líneas en este bloqueo: " & TEXT('.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-178">In the Formula field, enter '"Number of lines in this block: " & TEXT('.</span></span>
    * <span data-ttu-id="3bdd0-179">"Número de líneas en este bloqueo: " & TEXT(</span><span class="sxs-lookup"><span data-stu-id="3bdd0-179">"Number of lines in this block: " & TEXT(</span></span>  
57. <span data-ttu-id="3bdd0-180">En el árbol, seleccione "Funciones de recopilación de datos\COUNTIFS".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-180">In the tree, select 'Data collection functions\COUNTIFS'.</span></span>
58. <span data-ttu-id="3bdd0-181">Haga clic en Agregar función.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-181">Click Add function.</span></span>
59. <span data-ttu-id="3bdd0-182">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-182">Click Add data source.</span></span>
60. <span data-ttu-id="3bdd0-183">En el campo Fórmula, especifique '"Número de líneas en este bloqueo: " & TEXT(COUNTIFS('$BlockName', '.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-183">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '.</span></span>
    * <span data-ttu-id="3bdd0-184">"Número de líneas en este bloqueo: " & TEXT(COUNTIFS('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="3bdd0-184">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName',</span></span>  
61. <span data-ttu-id="3bdd0-185">En el árbol, expanda "$BlocksList".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-185">In the tree, expand '$BlocksList'.</span></span>
62. <span data-ttu-id="3bdd0-186">En el árbol, seleccione "$BlocksList\Value".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-186">In the tree, select '$BlocksList\Value'.</span></span>
63. <span data-ttu-id="3bdd0-187">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-187">Click Add data source.</span></span>
64. <span data-ttu-id="3bdd0-188">En el campo Fórmula, especifique '"Número de líneas en este bloqueo: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-188">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span></span>
    * <span data-ttu-id="3bdd0-189">"Número de líneas en este bloqueo: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span><span class="sxs-lookup"><span data-stu-id="3bdd0-189">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span></span>  
65. <span data-ttu-id="3bdd0-190">En el árbol, seleccione "$RecName".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-190">In the tree, select '$RecName'.</span></span>
66. <span data-ttu-id="3bdd0-191">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-191">Click Add data source.</span></span>
67. <span data-ttu-id="3bdd0-192">En el campo Fórmula, especifique '"Número de líneas en este bloqueo: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-192">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="3bdd0-193">"Número de líneas en este bloque: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="3bdd0-193">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
68. <span data-ttu-id="3bdd0-194">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-194">Click Save.</span></span>
69. <span data-ttu-id="3bdd0-195">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-195">Close the page.</span></span>
70. <span data-ttu-id="3bdd0-196">Haga clic en la ficha Formato.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-196">Click the Format tab.</span></span>
71. <span data-ttu-id="3bdd0-197">En el árbol, seleccione "Intrastat\Datos\Totales por bloqueos\Importe total".</span><span class="sxs-lookup"><span data-stu-id="3bdd0-197">In the tree, select 'Intrastat\Data\Totals by blocks\Total amount'.</span></span>
72. <span data-ttu-id="3bdd0-198">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-198">Click the Mapping tab.</span></span>
73. <span data-ttu-id="3bdd0-199">Haga clic en Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-199">Click Edit formula.</span></span>
    * <span data-ttu-id="3bdd0-200">Cree la salida que será el total del importe facturado para cada bloqueo que se muestra en este informe.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-200">Create output that will be the total of the invoiced amount for each block presented in this report.</span></span>  
74. <span data-ttu-id="3bdd0-201">En el campo Fórmula, especifique '"Total del importe facturado: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-201">In the Formula field, enter '"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="3bdd0-202">"Total del importe facturado: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="3bdd0-202">"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
75. <span data-ttu-id="3bdd0-203">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-203">Click Save.</span></span>
76. <span data-ttu-id="3bdd0-204">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-204">Close the page.</span></span>
77. <span data-ttu-id="3bdd0-205">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-205">Click Save.</span></span>
78. <span data-ttu-id="3bdd0-206">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3bdd0-206">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]