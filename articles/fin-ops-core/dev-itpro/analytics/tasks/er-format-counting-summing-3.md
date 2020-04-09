---
title: 'Informe electrónico Configurar el formato para contar y sumar (Parte 3: Uso de los cálculos para crear la salida)'
description: Los pasos siguientes explican cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos puede configurar un formato de informe electrónico (ER) para que realice el recuento y calcule en función de los datos de la salida de texto ya generada.
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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e8a4965c07c5a084b21da40667747db36530284c
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141967"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-3---use-computations-to-make-the-output"></a><span data-ttu-id="b6f06-103">Informe electrónico Configurar el formato para contar y sumar (Parte 3: Uso de los cálculos para crear la salida)</span><span class="sxs-lookup"><span data-stu-id="b6f06-103">ER Configure format to do counting and summing (Part 3 - Use computations to make the output)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b6f06-104">Los pasos siguientes explican cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos puede configurar un formato de informe electrónico (ER) para que realice el recuento y calcule en función de los datos de la salida de texto ya generada.</span><span class="sxs-lookup"><span data-stu-id="b6f06-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="b6f06-105">Estos pasos se pueden llevar a cabo en cualquier empresa.</span><span class="sxs-lookup"><span data-stu-id="b6f06-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="b6f06-106">Para completar estos pasos, primero debe completar los pasos del procedimiento "ER Configurar el formato para contar y sumar (Parte 2: Configuración de cálculos)".</span><span class="sxs-lookup"><span data-stu-id="b6f06-106">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 2: Configure computations)" procedure.</span></span>

<span data-ttu-id="b6f06-107">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="b6f06-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="configure-this-report-to-use-counting-and-summing-info"></a><span data-ttu-id="b6f06-108">Configurar este informe para utilizar la información de recuento y suma</span><span class="sxs-lookup"><span data-stu-id="b6f06-108">Configure this report to use counting and summing info</span></span>
1. <span data-ttu-id="b6f06-109">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="b6f06-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="b6f06-110">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="b6f06-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="b6f06-111">En el árbol, expanda "Intrastat modelo".</span><span class="sxs-lookup"><span data-stu-id="b6f06-111">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="b6f06-112">En el árbol, expanda "Modelo de Intrastat\Intrastat (DE)".</span><span class="sxs-lookup"><span data-stu-id="b6f06-112">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="b6f06-113">En el árbol, seleccione "Modelo de Intrastat\Intrastat (DE)\Intrastat (DE) con recuento & suma".</span><span class="sxs-lookup"><span data-stu-id="b6f06-113">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="b6f06-114">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="b6f06-114">Click Designer.</span></span>
7. <span data-ttu-id="b6f06-115">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="b6f06-115">Click the Mapping tab.</span></span>
8. <span data-ttu-id="b6f06-116">Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="b6f06-116">Click Add root to open the drop dialog.</span></span>
    * <span data-ttu-id="b6f06-117">Agregue un nuevo origen de datos para obtener la lista de bloqueos memorizados.</span><span class="sxs-lookup"><span data-stu-id="b6f06-117">Add a new data source to get the list of memorized blocks.</span></span>  
9. <span data-ttu-id="b6f06-118">En el árbol, seleccione el apartado "Funciones\Campo calculado".</span><span class="sxs-lookup"><span data-stu-id="b6f06-118">In the tree, select 'Functions\Calculated field'.</span></span>
10. <span data-ttu-id="b6f06-119">En el campo Nombre, escriba "$BlocksList".</span><span class="sxs-lookup"><span data-stu-id="b6f06-119">In the Name field, type '$BlocksList'.</span></span>
    * <span data-ttu-id="b6f06-120">$BlocksList</span><span class="sxs-lookup"><span data-stu-id="b6f06-120">$BlocksList</span></span>  
11. <span data-ttu-id="b6f06-121">Haga clic en Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="b6f06-121">Click Edit formula.</span></span>
12. <span data-ttu-id="b6f06-122">En el árbol, seleccione "Funciones de recopilación de datos\COLLECTEDLIST".</span><span class="sxs-lookup"><span data-stu-id="b6f06-122">In the tree, select 'Data collection functions\COLLECTEDLIST'.</span></span>
13. <span data-ttu-id="b6f06-123">Haga clic en Agregar función.</span><span class="sxs-lookup"><span data-stu-id="b6f06-123">Click Add function.</span></span>
14. <span data-ttu-id="b6f06-124">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b6f06-124">Click Add data source.</span></span>
15. <span data-ttu-id="b6f06-125">En el campo Fórmula, especifique "COLLECTEDLIST('$BlockName',".</span><span class="sxs-lookup"><span data-stu-id="b6f06-125">In the Formula field, enter 'COLLECTEDLIST('$BlockName', '.</span></span>
    * <span data-ttu-id="b6f06-126">COLLECTEDLIST('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="b6f06-126">COLLECTEDLIST('$BlockName',</span></span>  
16. <span data-ttu-id="b6f06-127">En el campo Fórmula, especifique "COLLECTEDLIST('$BlockName', "\*")".</span><span class="sxs-lookup"><span data-stu-id="b6f06-127">In the Formula field, enter 'COLLECTEDLIST('$BlockName', "\*")'.</span></span>
    * <span data-ttu-id="b6f06-128">COLLECTEDLIST('$BlockName', "\*")</span><span class="sxs-lookup"><span data-stu-id="b6f06-128">COLLECTEDLIST('$BlockName', "\*")</span></span>  
17. <span data-ttu-id="b6f06-129">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="b6f06-129">Click Save.</span></span>
    * <span data-ttu-id="b6f06-130">El patrón "\*" significa que todos los bloqueos se incluirán en la lista de este registro.</span><span class="sxs-lookup"><span data-stu-id="b6f06-130">The pattern "\*" means that all blocks will be included to the list for this record.</span></span>  
18. <span data-ttu-id="b6f06-131">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b6f06-131">Close the page.</span></span>
19. <span data-ttu-id="b6f06-132">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="b6f06-132">Click OK.</span></span>
20. <span data-ttu-id="b6f06-133">Haga clic en la ficha Formato.</span><span class="sxs-lookup"><span data-stu-id="b6f06-133">Click the Format tab.</span></span>
21. <span data-ttu-id="b6f06-134">En el árbol, seleccione "Intrastat\Datos".</span><span class="sxs-lookup"><span data-stu-id="b6f06-134">In the tree, select 'Intrastat\Data'.</span></span>
22. <span data-ttu-id="b6f06-135">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="b6f06-135">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="b6f06-136">En el árbol, seleccione "Texto\Secuencia".</span><span class="sxs-lookup"><span data-stu-id="b6f06-136">In the tree, select 'Text\Sequence'.</span></span>
24. <span data-ttu-id="b6f06-137">En el campo Nombre, escriba "Totales por bloqueos".</span><span class="sxs-lookup"><span data-stu-id="b6f06-137">In the Name field, type 'Totals by blocks'.</span></span>
    * <span data-ttu-id="b6f06-138">Totales por bloqueos</span><span class="sxs-lookup"><span data-stu-id="b6f06-138">Totals by blocks</span></span>  
25. <span data-ttu-id="b6f06-139">En el campo Caracteres especiales, seleccione "Línea nueva - Windows (CR LF)".</span><span class="sxs-lookup"><span data-stu-id="b6f06-139">In the Special characters field, select 'New line - Windows (CR LF)'.</span></span>
26. <span data-ttu-id="b6f06-140">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="b6f06-140">Click OK.</span></span>
27. <span data-ttu-id="b6f06-141">En el árbol, seleccione "Intrastat\Datos\Totales por bloqueos".</span><span class="sxs-lookup"><span data-stu-id="b6f06-141">In the tree, select 'Intrastat\Data\Totals by blocks'.</span></span>
28. <span data-ttu-id="b6f06-142">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="b6f06-142">Click Add to open the drop dialog.</span></span>
29. <span data-ttu-id="b6f06-143">En el árbol, seleccione "Texto\Cadena".</span><span class="sxs-lookup"><span data-stu-id="b6f06-143">In the tree, select 'Text\String'.</span></span>
30. <span data-ttu-id="b6f06-144">En el campo Nombre, escriba "Código de bloqueo".</span><span class="sxs-lookup"><span data-stu-id="b6f06-144">In the Name field, type 'Block code'.</span></span>
    * <span data-ttu-id="b6f06-145">Código de bloqueo</span><span class="sxs-lookup"><span data-stu-id="b6f06-145">Block code</span></span>  
31. <span data-ttu-id="b6f06-146">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="b6f06-146">Click OK.</span></span>
32. <span data-ttu-id="b6f06-147">Haga clic en Agregar cadena.</span><span class="sxs-lookup"><span data-stu-id="b6f06-147">Click Add String.</span></span>
33. <span data-ttu-id="b6f06-148">En el campo Nombre, escriba "Recuento de líneas".</span><span class="sxs-lookup"><span data-stu-id="b6f06-148">In the Name field, type 'Lines counting'.</span></span>
    * <span data-ttu-id="b6f06-149">Recuento de líneas</span><span class="sxs-lookup"><span data-stu-id="b6f06-149">Lines counting</span></span>  
34. <span data-ttu-id="b6f06-150">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="b6f06-150">Click OK.</span></span>
35. <span data-ttu-id="b6f06-151">Haga clic en Agregar cadena.</span><span class="sxs-lookup"><span data-stu-id="b6f06-151">Click Add String.</span></span>
36. <span data-ttu-id="b6f06-152">En el campo Nombre, escriba "Importe total".</span><span class="sxs-lookup"><span data-stu-id="b6f06-152">In the Name field, type 'Total amount'.</span></span>
    * <span data-ttu-id="b6f06-153">Importe total</span><span class="sxs-lookup"><span data-stu-id="b6f06-153">Total amount</span></span>  
37. <span data-ttu-id="b6f06-154">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="b6f06-154">Click OK.</span></span>
38. <span data-ttu-id="b6f06-155">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="b6f06-155">Click the Mapping tab.</span></span>
39. <span data-ttu-id="b6f06-156">En el árbol, seleccione "$BlocksList".</span><span class="sxs-lookup"><span data-stu-id="b6f06-156">In the tree, select '$BlocksList'.</span></span>
40. <span data-ttu-id="b6f06-157">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="b6f06-157">Click Bind.</span></span>
    * <span data-ttu-id="b6f06-158">Cree una línea de resumen para cada bloqueo memorizado.</span><span class="sxs-lookup"><span data-stu-id="b6f06-158">Create a summary line for each memorized block.</span></span>  
41. <span data-ttu-id="b6f06-159">Haga clic en la ficha Formato.</span><span class="sxs-lookup"><span data-stu-id="b6f06-159">Click the Format tab.</span></span>
42. <span data-ttu-id="b6f06-160">En el árbol, seleccione "Intrastat\Datos\Totales por bloqueos\Código de bloqueo".</span><span class="sxs-lookup"><span data-stu-id="b6f06-160">In the tree, select 'Intrastat\Data\Totals by blocks\Block code'.</span></span>
43. <span data-ttu-id="b6f06-161">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="b6f06-161">Click the Mapping tab.</span></span>
44. <span data-ttu-id="b6f06-162">Haga clic en Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="b6f06-162">Click Edit formula.</span></span>
45. <span data-ttu-id="b6f06-163">En el campo Fórmula, introduzca '"Id. de bloqueo: " & '.</span><span class="sxs-lookup"><span data-stu-id="b6f06-163">In the Formula field, enter '"Block id: " & '.</span></span>
    * <span data-ttu-id="b6f06-164">"Id. de bloqueo: " &</span><span class="sxs-lookup"><span data-stu-id="b6f06-164">"Block id: " &</span></span>  
46. <span data-ttu-id="b6f06-165">En el árbol, expanda "$BlocksList".</span><span class="sxs-lookup"><span data-stu-id="b6f06-165">In the tree, expand '$BlocksList'.</span></span>
47. <span data-ttu-id="b6f06-166">En el árbol, seleccione "$BlocksList\Value".</span><span class="sxs-lookup"><span data-stu-id="b6f06-166">In the tree, select '$BlocksList\Value'.</span></span>
48. <span data-ttu-id="b6f06-167">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b6f06-167">Click Add data source.</span></span>
49. <span data-ttu-id="b6f06-168">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="b6f06-168">Click Save.</span></span>
50. <span data-ttu-id="b6f06-169">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b6f06-169">Close the page.</span></span>
51. <span data-ttu-id="b6f06-170">Haga clic en la ficha Formato.</span><span class="sxs-lookup"><span data-stu-id="b6f06-170">Click the Format tab.</span></span>
52. <span data-ttu-id="b6f06-171">En el árbol, seleccione "Intrastat\Datos\Totales por bloqueos\Recuento de líneas".</span><span class="sxs-lookup"><span data-stu-id="b6f06-171">In the tree, select 'Intrastat\Data\Totals by blocks\Lines counting'.</span></span>
53. <span data-ttu-id="b6f06-172">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="b6f06-172">Click the Mapping tab.</span></span>
54. <span data-ttu-id="b6f06-173">Haga clic en Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="b6f06-173">Click Edit formula.</span></span>
    * <span data-ttu-id="b6f06-174">Cree la salida para el número de líneas para cada bloqueo que se muestra en este informe.</span><span class="sxs-lookup"><span data-stu-id="b6f06-174">Create output for the number of lines for each block presented in this report.</span></span>  
55. <span data-ttu-id="b6f06-175">En el campo Fórmula, introduzca '"Número de líneas en este bloqueo: " & '.</span><span class="sxs-lookup"><span data-stu-id="b6f06-175">In the Formula field, enter '"Number of lines in this block: " & '.</span></span>
    * <span data-ttu-id="b6f06-176">"Número de líneas en este bloqueo: " &</span><span class="sxs-lookup"><span data-stu-id="b6f06-176">"Number of lines in this block: " &</span></span>  
56. <span data-ttu-id="b6f06-177">En el campo Fórmula, introduzca '"Número de líneas en este bloqueo: " & TEXT('.</span><span class="sxs-lookup"><span data-stu-id="b6f06-177">In the Formula field, enter '"Number of lines in this block: " & TEXT('.</span></span>
    * <span data-ttu-id="b6f06-178">"Número de líneas en este bloqueo: " & TEXT(</span><span class="sxs-lookup"><span data-stu-id="b6f06-178">"Number of lines in this block: " & TEXT(</span></span>  
57. <span data-ttu-id="b6f06-179">En el árbol, seleccione "Funciones de recopilación de datos\COUNTIFS".</span><span class="sxs-lookup"><span data-stu-id="b6f06-179">In the tree, select 'Data collection functions\COUNTIFS'.</span></span>
58. <span data-ttu-id="b6f06-180">Haga clic en Agregar función.</span><span class="sxs-lookup"><span data-stu-id="b6f06-180">Click Add function.</span></span>
59. <span data-ttu-id="b6f06-181">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b6f06-181">Click Add data source.</span></span>
60. <span data-ttu-id="b6f06-182">En el campo Fórmula, especifique '"Número de líneas en este bloqueo: " & TEXT(COUNTIFS('$BlockName', '.</span><span class="sxs-lookup"><span data-stu-id="b6f06-182">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '.</span></span>
    * <span data-ttu-id="b6f06-183">"Número de líneas en este bloqueo: " & TEXT(COUNTIFS('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="b6f06-183">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName',</span></span>  
61. <span data-ttu-id="b6f06-184">En el árbol, expanda "$BlocksList".</span><span class="sxs-lookup"><span data-stu-id="b6f06-184">In the tree, expand '$BlocksList'.</span></span>
62. <span data-ttu-id="b6f06-185">En el árbol, seleccione "$BlocksList\Value".</span><span class="sxs-lookup"><span data-stu-id="b6f06-185">In the tree, select '$BlocksList\Value'.</span></span>
63. <span data-ttu-id="b6f06-186">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b6f06-186">Click Add data source.</span></span>
64. <span data-ttu-id="b6f06-187">En el campo Fórmula, especifique '"Número de líneas en este bloqueo: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span><span class="sxs-lookup"><span data-stu-id="b6f06-187">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span></span>
    * <span data-ttu-id="b6f06-188">"Número de líneas en este bloqueo: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span><span class="sxs-lookup"><span data-stu-id="b6f06-188">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span></span>  
65. <span data-ttu-id="b6f06-189">En el árbol, seleccione "$RecName".</span><span class="sxs-lookup"><span data-stu-id="b6f06-189">In the tree, select '$RecName'.</span></span>
66. <span data-ttu-id="b6f06-190">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b6f06-190">Click Add data source.</span></span>
67. <span data-ttu-id="b6f06-191">En el campo Fórmula, especifique '"Número de líneas en este bloqueo: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span><span class="sxs-lookup"><span data-stu-id="b6f06-191">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="b6f06-192">"Número de líneas en este bloque: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="b6f06-192">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
68. <span data-ttu-id="b6f06-193">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="b6f06-193">Click Save.</span></span>
69. <span data-ttu-id="b6f06-194">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b6f06-194">Close the page.</span></span>
70. <span data-ttu-id="b6f06-195">Haga clic en la ficha Formato.</span><span class="sxs-lookup"><span data-stu-id="b6f06-195">Click the Format tab.</span></span>
71. <span data-ttu-id="b6f06-196">En el árbol, seleccione "Intrastat\Datos\Totales por bloqueos\Importe total".</span><span class="sxs-lookup"><span data-stu-id="b6f06-196">In the tree, select 'Intrastat\Data\Totals by blocks\Total amount'.</span></span>
72. <span data-ttu-id="b6f06-197">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="b6f06-197">Click the Mapping tab.</span></span>
73. <span data-ttu-id="b6f06-198">Haga clic en Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="b6f06-198">Click Edit formula.</span></span>
    * <span data-ttu-id="b6f06-199">Cree la salida que será el total del importe facturado para cada bloqueo que se muestra en este informe.</span><span class="sxs-lookup"><span data-stu-id="b6f06-199">Create output that will be the total of the invoiced amount for each block presented in this report.</span></span>  
74. <span data-ttu-id="b6f06-200">En el campo Fórmula, especifique '"Total del importe facturado: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span><span class="sxs-lookup"><span data-stu-id="b6f06-200">In the Formula field, enter '"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="b6f06-201">"Total del importe facturado: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="b6f06-201">"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
75. <span data-ttu-id="b6f06-202">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="b6f06-202">Click Save.</span></span>
76. <span data-ttu-id="b6f06-203">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b6f06-203">Close the page.</span></span>
77. <span data-ttu-id="b6f06-204">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="b6f06-204">Click Save.</span></span>
78. <span data-ttu-id="b6f06-205">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b6f06-205">Close the page.</span></span>

