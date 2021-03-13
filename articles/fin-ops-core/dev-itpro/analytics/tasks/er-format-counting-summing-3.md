---
title: 'Informe electrónico Configurar el formato para contar y sumar (Parte 3: Uso de los cálculos para crear la salida)'
description: Este tema describe cómo configurar un formato de informes electrónicos para realizar recuentos y sumas en función de los datos de la salida de texto ya generados. (Parte 3)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4a69dd28051d8e98643eb95c663525075bed8dec
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092981"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-3---use-computations-to-make-the-output"></a><span data-ttu-id="e6c96-104">Informe electrónico Configurar el formato para contar y sumar (Parte 3: Uso de los cálculos para crear la salida)</span><span class="sxs-lookup"><span data-stu-id="e6c96-104">ER Configure format to do counting and summing (Part 3 - Use computations to make the output)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e6c96-105">Los pasos siguientes explican cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos puede configurar un formato de informe electrónico (ER) para que realice el recuento y calcule en función de los datos de la salida de texto ya generada.</span><span class="sxs-lookup"><span data-stu-id="e6c96-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="e6c96-106">Estos pasos se pueden llevar a cabo en cualquier empresa.</span><span class="sxs-lookup"><span data-stu-id="e6c96-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="e6c96-107">Para completar estos pasos, primero debe completar los pasos del procedimiento "ER Configurar el formato para contar y sumar (Parte 2: Configuración de cálculos)".</span><span class="sxs-lookup"><span data-stu-id="e6c96-107">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 2: Configure computations)" procedure.</span></span>

<span data-ttu-id="e6c96-108">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="e6c96-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="configure-this-report-to-use-counting-and-summing-info"></a><span data-ttu-id="e6c96-109">Configurar este informe para utilizar la información de recuento y suma</span><span class="sxs-lookup"><span data-stu-id="e6c96-109">Configure this report to use counting and summing info</span></span>
1. <span data-ttu-id="e6c96-110">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="e6c96-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="e6c96-111">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="e6c96-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="e6c96-112">En el árbol, expanda "Intrastat modelo".</span><span class="sxs-lookup"><span data-stu-id="e6c96-112">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="e6c96-113">En el árbol, expanda "Modelo de Intrastat\Intrastat (DE)".</span><span class="sxs-lookup"><span data-stu-id="e6c96-113">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="e6c96-114">En el árbol, seleccione "Modelo de Intrastat\Intrastat (DE)\Intrastat (DE) con recuento & suma".</span><span class="sxs-lookup"><span data-stu-id="e6c96-114">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="e6c96-115">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="e6c96-115">Click Designer.</span></span>
7. <span data-ttu-id="e6c96-116">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="e6c96-116">Click the Mapping tab.</span></span>
8. <span data-ttu-id="e6c96-117">Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="e6c96-117">Click Add root to open the drop dialog.</span></span>
    * <span data-ttu-id="e6c96-118">Agregue un nuevo origen de datos para obtener la lista de bloqueos memorizados.</span><span class="sxs-lookup"><span data-stu-id="e6c96-118">Add a new data source to get the list of memorized blocks.</span></span>  
9. <span data-ttu-id="e6c96-119">En el árbol, seleccione el apartado "Funciones\Campo calculado".</span><span class="sxs-lookup"><span data-stu-id="e6c96-119">In the tree, select 'Functions\Calculated field'.</span></span>
10. <span data-ttu-id="e6c96-120">En el campo Nombre, escriba "$BlocksList".</span><span class="sxs-lookup"><span data-stu-id="e6c96-120">In the Name field, type '$BlocksList'.</span></span>
    * <span data-ttu-id="e6c96-121">$BlocksList</span><span class="sxs-lookup"><span data-stu-id="e6c96-121">$BlocksList</span></span>  
11. <span data-ttu-id="e6c96-122">Haga clic en Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="e6c96-122">Click Edit formula.</span></span>
12. <span data-ttu-id="e6c96-123">En el árbol, seleccione "Funciones de recopilación de datos\COLLECTEDLIST".</span><span class="sxs-lookup"><span data-stu-id="e6c96-123">In the tree, select 'Data collection functions\COLLECTEDLIST'.</span></span>
13. <span data-ttu-id="e6c96-124">Haga clic en Agregar función.</span><span class="sxs-lookup"><span data-stu-id="e6c96-124">Click Add function.</span></span>
14. <span data-ttu-id="e6c96-125">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e6c96-125">Click Add data source.</span></span>
15. <span data-ttu-id="e6c96-126">En el campo Fórmula, especifique "COLLECTEDLIST('$BlockName',".</span><span class="sxs-lookup"><span data-stu-id="e6c96-126">In the Formula field, enter 'COLLECTEDLIST('$BlockName', '.</span></span>
    * <span data-ttu-id="e6c96-127">COLLECTEDLIST('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="e6c96-127">COLLECTEDLIST('$BlockName',</span></span>  
16. <span data-ttu-id="e6c96-128">En el campo Fórmula, especifique "COLLECTEDLIST('$BlockName', "\*")".</span><span class="sxs-lookup"><span data-stu-id="e6c96-128">In the Formula field, enter 'COLLECTEDLIST('$BlockName', "\*")'.</span></span>
    * <span data-ttu-id="e6c96-129">COLLECTEDLIST('$BlockName', "\*")</span><span class="sxs-lookup"><span data-stu-id="e6c96-129">COLLECTEDLIST('$BlockName', "\*")</span></span>  
17. <span data-ttu-id="e6c96-130">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="e6c96-130">Click Save.</span></span>
    * <span data-ttu-id="e6c96-131">El patrón "\*" significa que todos los bloqueos se incluirán en la lista de este registro.</span><span class="sxs-lookup"><span data-stu-id="e6c96-131">The pattern "\*" means that all blocks will be included to the list for this record.</span></span>  
18. <span data-ttu-id="e6c96-132">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e6c96-132">Close the page.</span></span>
19. <span data-ttu-id="e6c96-133">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="e6c96-133">Click OK.</span></span>
20. <span data-ttu-id="e6c96-134">Haga clic en la ficha Formato.</span><span class="sxs-lookup"><span data-stu-id="e6c96-134">Click the Format tab.</span></span>
21. <span data-ttu-id="e6c96-135">En el árbol, seleccione "Intrastat\Datos".</span><span class="sxs-lookup"><span data-stu-id="e6c96-135">In the tree, select 'Intrastat\Data'.</span></span>
22. <span data-ttu-id="e6c96-136">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="e6c96-136">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="e6c96-137">En el árbol, seleccione "Texto\Secuencia".</span><span class="sxs-lookup"><span data-stu-id="e6c96-137">In the tree, select 'Text\Sequence'.</span></span>
24. <span data-ttu-id="e6c96-138">En el campo Nombre, escriba "Totales por bloqueos".</span><span class="sxs-lookup"><span data-stu-id="e6c96-138">In the Name field, type 'Totals by blocks'.</span></span>
    * <span data-ttu-id="e6c96-139">Totales por bloqueos</span><span class="sxs-lookup"><span data-stu-id="e6c96-139">Totals by blocks</span></span>  
25. <span data-ttu-id="e6c96-140">En el campo Caracteres especiales, seleccione "Línea nueva - Windows (CR LF)".</span><span class="sxs-lookup"><span data-stu-id="e6c96-140">In the Special characters field, select 'New line - Windows (CR LF)'.</span></span>
26. <span data-ttu-id="e6c96-141">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="e6c96-141">Click OK.</span></span>
27. <span data-ttu-id="e6c96-142">En el árbol, seleccione "Intrastat\Datos\Totales por bloqueos".</span><span class="sxs-lookup"><span data-stu-id="e6c96-142">In the tree, select 'Intrastat\Data\Totals by blocks'.</span></span>
28. <span data-ttu-id="e6c96-143">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="e6c96-143">Click Add to open the drop dialog.</span></span>
29. <span data-ttu-id="e6c96-144">En el árbol, seleccione "Texto\Cadena".</span><span class="sxs-lookup"><span data-stu-id="e6c96-144">In the tree, select 'Text\String'.</span></span>
30. <span data-ttu-id="e6c96-145">En el campo Nombre, escriba "Código de bloqueo".</span><span class="sxs-lookup"><span data-stu-id="e6c96-145">In the Name field, type 'Block code'.</span></span>
    * <span data-ttu-id="e6c96-146">Código de bloqueo</span><span class="sxs-lookup"><span data-stu-id="e6c96-146">Block code</span></span>  
31. <span data-ttu-id="e6c96-147">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="e6c96-147">Click OK.</span></span>
32. <span data-ttu-id="e6c96-148">Haga clic en Agregar cadena.</span><span class="sxs-lookup"><span data-stu-id="e6c96-148">Click Add String.</span></span>
33. <span data-ttu-id="e6c96-149">En el campo Nombre, escriba "Recuento de líneas".</span><span class="sxs-lookup"><span data-stu-id="e6c96-149">In the Name field, type 'Lines counting'.</span></span>
    * <span data-ttu-id="e6c96-150">Recuento de líneas</span><span class="sxs-lookup"><span data-stu-id="e6c96-150">Lines counting</span></span>  
34. <span data-ttu-id="e6c96-151">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="e6c96-151">Click OK.</span></span>
35. <span data-ttu-id="e6c96-152">Haga clic en Agregar cadena.</span><span class="sxs-lookup"><span data-stu-id="e6c96-152">Click Add String.</span></span>
36. <span data-ttu-id="e6c96-153">En el campo Nombre, escriba "Importe total".</span><span class="sxs-lookup"><span data-stu-id="e6c96-153">In the Name field, type 'Total amount'.</span></span>
    * <span data-ttu-id="e6c96-154">Importe total</span><span class="sxs-lookup"><span data-stu-id="e6c96-154">Total amount</span></span>  
37. <span data-ttu-id="e6c96-155">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="e6c96-155">Click OK.</span></span>
38. <span data-ttu-id="e6c96-156">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="e6c96-156">Click the Mapping tab.</span></span>
39. <span data-ttu-id="e6c96-157">En el árbol, seleccione "$BlocksList".</span><span class="sxs-lookup"><span data-stu-id="e6c96-157">In the tree, select '$BlocksList'.</span></span>
40. <span data-ttu-id="e6c96-158">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="e6c96-158">Click Bind.</span></span>
    * <span data-ttu-id="e6c96-159">Cree una línea de resumen para cada bloqueo memorizado.</span><span class="sxs-lookup"><span data-stu-id="e6c96-159">Create a summary line for each memorized block.</span></span>  
41. <span data-ttu-id="e6c96-160">Haga clic en la ficha Formato.</span><span class="sxs-lookup"><span data-stu-id="e6c96-160">Click the Format tab.</span></span>
42. <span data-ttu-id="e6c96-161">En el árbol, seleccione "Intrastat\Datos\Totales por bloqueos\Código de bloqueo".</span><span class="sxs-lookup"><span data-stu-id="e6c96-161">In the tree, select 'Intrastat\Data\Totals by blocks\Block code'.</span></span>
43. <span data-ttu-id="e6c96-162">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="e6c96-162">Click the Mapping tab.</span></span>
44. <span data-ttu-id="e6c96-163">Haga clic en Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="e6c96-163">Click Edit formula.</span></span>
45. <span data-ttu-id="e6c96-164">En el campo Fórmula, introduzca '"Id. de bloqueo: " & '.</span><span class="sxs-lookup"><span data-stu-id="e6c96-164">In the Formula field, enter '"Block id: " & '.</span></span>
    * <span data-ttu-id="e6c96-165">"Id. de bloqueo: " &</span><span class="sxs-lookup"><span data-stu-id="e6c96-165">"Block id: " &</span></span>  
46. <span data-ttu-id="e6c96-166">En el árbol, expanda "$BlocksList".</span><span class="sxs-lookup"><span data-stu-id="e6c96-166">In the tree, expand '$BlocksList'.</span></span>
47. <span data-ttu-id="e6c96-167">En el árbol, seleccione "$BlocksList\Value".</span><span class="sxs-lookup"><span data-stu-id="e6c96-167">In the tree, select '$BlocksList\Value'.</span></span>
48. <span data-ttu-id="e6c96-168">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e6c96-168">Click Add data source.</span></span>
49. <span data-ttu-id="e6c96-169">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="e6c96-169">Click Save.</span></span>
50. <span data-ttu-id="e6c96-170">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e6c96-170">Close the page.</span></span>
51. <span data-ttu-id="e6c96-171">Haga clic en la ficha Formato.</span><span class="sxs-lookup"><span data-stu-id="e6c96-171">Click the Format tab.</span></span>
52. <span data-ttu-id="e6c96-172">En el árbol, seleccione "Intrastat\Datos\Totales por bloqueos\Recuento de líneas".</span><span class="sxs-lookup"><span data-stu-id="e6c96-172">In the tree, select 'Intrastat\Data\Totals by blocks\Lines counting'.</span></span>
53. <span data-ttu-id="e6c96-173">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="e6c96-173">Click the Mapping tab.</span></span>
54. <span data-ttu-id="e6c96-174">Haga clic en Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="e6c96-174">Click Edit formula.</span></span>
    * <span data-ttu-id="e6c96-175">Cree la salida para el número de líneas para cada bloqueo que se muestra en este informe.</span><span class="sxs-lookup"><span data-stu-id="e6c96-175">Create output for the number of lines for each block presented in this report.</span></span>  
55. <span data-ttu-id="e6c96-176">En el campo Fórmula, introduzca '"Número de líneas en este bloqueo: " & '.</span><span class="sxs-lookup"><span data-stu-id="e6c96-176">In the Formula field, enter '"Number of lines in this block: " & '.</span></span>
    * <span data-ttu-id="e6c96-177">"Número de líneas en este bloqueo: " &</span><span class="sxs-lookup"><span data-stu-id="e6c96-177">"Number of lines in this block: " &</span></span>  
56. <span data-ttu-id="e6c96-178">En el campo Fórmula, introduzca '"Número de líneas en este bloqueo: " & TEXT('.</span><span class="sxs-lookup"><span data-stu-id="e6c96-178">In the Formula field, enter '"Number of lines in this block: " & TEXT('.</span></span>
    * <span data-ttu-id="e6c96-179">"Número de líneas en este bloqueo: " & TEXT(</span><span class="sxs-lookup"><span data-stu-id="e6c96-179">"Number of lines in this block: " & TEXT(</span></span>  
57. <span data-ttu-id="e6c96-180">En el árbol, seleccione "Funciones de recopilación de datos\COUNTIFS".</span><span class="sxs-lookup"><span data-stu-id="e6c96-180">In the tree, select 'Data collection functions\COUNTIFS'.</span></span>
58. <span data-ttu-id="e6c96-181">Haga clic en Agregar función.</span><span class="sxs-lookup"><span data-stu-id="e6c96-181">Click Add function.</span></span>
59. <span data-ttu-id="e6c96-182">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e6c96-182">Click Add data source.</span></span>
60. <span data-ttu-id="e6c96-183">En el campo Fórmula, especifique '"Número de líneas en este bloqueo: " & TEXT(COUNTIFS('$BlockName', '.</span><span class="sxs-lookup"><span data-stu-id="e6c96-183">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '.</span></span>
    * <span data-ttu-id="e6c96-184">"Número de líneas en este bloqueo: " & TEXT(COUNTIFS('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="e6c96-184">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName',</span></span>  
61. <span data-ttu-id="e6c96-185">En el árbol, expanda "$BlocksList".</span><span class="sxs-lookup"><span data-stu-id="e6c96-185">In the tree, expand '$BlocksList'.</span></span>
62. <span data-ttu-id="e6c96-186">En el árbol, seleccione "$BlocksList\Value".</span><span class="sxs-lookup"><span data-stu-id="e6c96-186">In the tree, select '$BlocksList\Value'.</span></span>
63. <span data-ttu-id="e6c96-187">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e6c96-187">Click Add data source.</span></span>
64. <span data-ttu-id="e6c96-188">En el campo Fórmula, especifique '"Número de líneas en este bloqueo: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span><span class="sxs-lookup"><span data-stu-id="e6c96-188">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span></span>
    * <span data-ttu-id="e6c96-189">"Número de líneas en este bloqueo: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span><span class="sxs-lookup"><span data-stu-id="e6c96-189">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span></span>  
65. <span data-ttu-id="e6c96-190">En el árbol, seleccione "$RecName".</span><span class="sxs-lookup"><span data-stu-id="e6c96-190">In the tree, select '$RecName'.</span></span>
66. <span data-ttu-id="e6c96-191">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e6c96-191">Click Add data source.</span></span>
67. <span data-ttu-id="e6c96-192">En el campo Fórmula, especifique '"Número de líneas en este bloqueo: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span><span class="sxs-lookup"><span data-stu-id="e6c96-192">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="e6c96-193">"Número de líneas en este bloque: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="e6c96-193">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
68. <span data-ttu-id="e6c96-194">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="e6c96-194">Click Save.</span></span>
69. <span data-ttu-id="e6c96-195">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e6c96-195">Close the page.</span></span>
70. <span data-ttu-id="e6c96-196">Haga clic en la ficha Formato.</span><span class="sxs-lookup"><span data-stu-id="e6c96-196">Click the Format tab.</span></span>
71. <span data-ttu-id="e6c96-197">En el árbol, seleccione "Intrastat\Datos\Totales por bloqueos\Importe total".</span><span class="sxs-lookup"><span data-stu-id="e6c96-197">In the tree, select 'Intrastat\Data\Totals by blocks\Total amount'.</span></span>
72. <span data-ttu-id="e6c96-198">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="e6c96-198">Click the Mapping tab.</span></span>
73. <span data-ttu-id="e6c96-199">Haga clic en Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="e6c96-199">Click Edit formula.</span></span>
    * <span data-ttu-id="e6c96-200">Cree la salida que será el total del importe facturado para cada bloqueo que se muestra en este informe.</span><span class="sxs-lookup"><span data-stu-id="e6c96-200">Create output that will be the total of the invoiced amount for each block presented in this report.</span></span>  
74. <span data-ttu-id="e6c96-201">En el campo Fórmula, especifique '"Total del importe facturado: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span><span class="sxs-lookup"><span data-stu-id="e6c96-201">In the Formula field, enter '"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="e6c96-202">"Total del importe facturado: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="e6c96-202">"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
75. <span data-ttu-id="e6c96-203">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="e6c96-203">Click Save.</span></span>
76. <span data-ttu-id="e6c96-204">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e6c96-204">Close the page.</span></span>
77. <span data-ttu-id="e6c96-205">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="e6c96-205">Click Save.</span></span>
78. <span data-ttu-id="e6c96-206">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e6c96-206">Close the page.</span></span>

