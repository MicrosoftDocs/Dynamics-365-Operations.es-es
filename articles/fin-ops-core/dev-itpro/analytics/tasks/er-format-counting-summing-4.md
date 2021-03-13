---
title: 'Informe electrónico Configurar el formato para contar y sumar (Parte 4: Ejecución de formato)'
description: Este tema describe cómo configurar un formato de informes electrónicos para realizar recuentos y sumas en función de los datos de la salida de texto ya generados. (Parte 4)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, IntrastatParameters, Intrastat, InventItemIdLookupSimple, IntrastatCommodityLookup, ERFormatMappingRunLogTable, DocuView
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c5576229e8b81824dff6d0b38b8ab5483e04ade8
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092956"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-4---run-format"></a><span data-ttu-id="8f080-104">Informe electrónico Configurar el formato para contar y sumar (Parte 4: Ejecución de formato)</span><span class="sxs-lookup"><span data-stu-id="8f080-104">ER Configure format to do counting and summing (Part 4 - Run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8f080-105">Los pasos siguientes explican cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos puede configurar un formato de informe electrónico (ER) para que realice el recuento y calcule en función de los datos de la salida de texto ya generada.</span><span class="sxs-lookup"><span data-stu-id="8f080-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="8f080-106">Estos pasos se pueden llevar a cabo en la empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="8f080-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="8f080-107">Para completar estos pasos, primero debe completar los pasos del procedimiento "ER Configurar el formato para contar y sumar (Parte 3: Uso de los cálculos para crear la salida)".</span><span class="sxs-lookup"><span data-stu-id="8f080-107">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 3: Use computations to make the output)" procedure.</span></span>

<span data-ttu-id="8f080-108">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="8f080-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="test-this-configuration-for-generation-of-the-intrastat-reports"></a><span data-ttu-id="8f080-109">Pruebe esta configuración para la generación de los informes Intrastat</span><span class="sxs-lookup"><span data-stu-id="8f080-109">Test this configuration for generation of the Intrastat reports</span></span>
1. <span data-ttu-id="8f080-110">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="8f080-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="8f080-111">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="8f080-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="8f080-112">En el árbol, expanda "Intrastat modelo".</span><span class="sxs-lookup"><span data-stu-id="8f080-112">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="8f080-113">En el árbol, expanda "Modelo de Intrastat\Intrastat (DE)".</span><span class="sxs-lookup"><span data-stu-id="8f080-113">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="8f080-114">En el árbol, seleccione "Modelo de Intrastat\Intrastat (DE)\Intrastat (DE) con recuento & suma".</span><span class="sxs-lookup"><span data-stu-id="8f080-114">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="8f080-115">En el panel de acciones, haga clic en Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="8f080-115">On the Action Pane, click Configurations.</span></span>
7. <span data-ttu-id="8f080-116">Haga clic en Parámetros de usuario.</span><span class="sxs-lookup"><span data-stu-id="8f080-116">Click User parameters.</span></span>
8. <span data-ttu-id="8f080-117">Seleccione Sí en el campo Parámetros de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8f080-117">Select Yes in the Run settings field.</span></span>
9. <span data-ttu-id="8f080-118">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="8f080-118">Click OK.</span></span>
10. <span data-ttu-id="8f080-119">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="8f080-119">Click Edit.</span></span>
11. <span data-ttu-id="8f080-120">Seleccione Sí en el campo Borrador de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8f080-120">Select Yes in the Run Draft field.</span></span>
12. <span data-ttu-id="8f080-121">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="8f080-121">Click Save.</span></span>
13. <span data-ttu-id="8f080-122">Vaya a Impuestos > Configuración > Comercio exterior > Parámetros de comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="8f080-122">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
14. <span data-ttu-id="8f080-123">Expanda la sección Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="8f080-123">Expand the Electronic reporting section.</span></span>
15. <span data-ttu-id="8f080-124">Seleccione la configuración "Intrastat (DE) con recuento & suma".</span><span class="sxs-lookup"><span data-stu-id="8f080-124">Select the "Intrastat (DE) with counting & summing" configuration.</span></span>
16. <span data-ttu-id="8f080-125">Seleccione la configuración "Intrastat (DE) con recuento & suma".</span><span class="sxs-lookup"><span data-stu-id="8f080-125">Select the "Intrastat (DE) with counting & summing" configuration.</span></span>
17. <span data-ttu-id="8f080-126">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="8f080-126">Click Save.</span></span>
18. <span data-ttu-id="8f080-127">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8f080-127">Close the page.</span></span>
19. <span data-ttu-id="8f080-128">Vaya a Impuestos > Declaraciones > Comercio exterior > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="8f080-128">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
20. <span data-ttu-id="8f080-129">Haga clic en Salida.</span><span class="sxs-lookup"><span data-stu-id="8f080-129">Click Output.</span></span>
21. <span data-ttu-id="8f080-130">Haga clic en Informe.</span><span class="sxs-lookup"><span data-stu-id="8f080-130">Click Report.</span></span>
    * <span data-ttu-id="8f080-131">Ejecute el proceso de generación de informes de Intrastat.</span><span class="sxs-lookup"><span data-stu-id="8f080-131">Run the Intrastat report generation process.</span></span>  
22. <span data-ttu-id="8f080-132">En el campo Fecha inicial, defina la fecha en "2000-01-01".</span><span class="sxs-lookup"><span data-stu-id="8f080-132">In the From date field, set the date to '2000-01-01'.</span></span>
    * <span data-ttu-id="8f080-133">Defina las fechas de inicio y fin del período de informes que incluye las existentes en las transacciones del formulario.</span><span class="sxs-lookup"><span data-stu-id="8f080-133">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
23. <span data-ttu-id="8f080-134">En el campo Fecha final, defina la fecha en "2022-12-31".</span><span class="sxs-lookup"><span data-stu-id="8f080-134">In the To date field, set the date to '2022-12-31'.</span></span>
    * <span data-ttu-id="8f080-135">Defina las fechas de inicio y fin del período de informes que incluye las existentes en las transacciones del formulario.</span><span class="sxs-lookup"><span data-stu-id="8f080-135">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
24. <span data-ttu-id="8f080-136">En el campo Dirección, seleccione "Llegadas".</span><span class="sxs-lookup"><span data-stu-id="8f080-136">In the Direction field, select 'Arrivals'.</span></span>
25. <span data-ttu-id="8f080-137">Seleccione Sí en el campo Generar archivo.</span><span class="sxs-lookup"><span data-stu-id="8f080-137">Select Yes in the Generate file field.</span></span>
26. <span data-ttu-id="8f080-138">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="8f080-138">Click OK.</span></span>
    * <span data-ttu-id="8f080-139">Revise la salida creada con las líneas de resumen al final.</span><span class="sxs-lookup"><span data-stu-id="8f080-139">Review the created output with the summary lines in the end.</span></span>  
27. <span data-ttu-id="8f080-140">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="8f080-140">Click New.</span></span>
28. <span data-ttu-id="8f080-141">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8f080-141">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="8f080-142">En el campo Dirección, seleccione "Distribuciones".</span><span class="sxs-lookup"><span data-stu-id="8f080-142">In the Direction field, select 'Dispatches'.</span></span>
30. <span data-ttu-id="8f080-143">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8f080-143">In the Item number field, enter or select a value.</span></span>
31. <span data-ttu-id="8f080-144">En el campo Código Intrastat de la mercancía, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8f080-144">In the Commodity field, enter or select a value.</span></span>
32. <span data-ttu-id="8f080-145">Establezca un Peso de "10".</span><span class="sxs-lookup"><span data-stu-id="8f080-145">Set Weight to '10'.</span></span>
33. <span data-ttu-id="8f080-146">establezca un importe de Factura de "10000"</span><span class="sxs-lookup"><span data-stu-id="8f080-146">Set Invoice amount to '10000'.</span></span>
34. <span data-ttu-id="8f080-147">Establezca un Importe estadístico de "10000"</span><span class="sxs-lookup"><span data-stu-id="8f080-147">Set Statistical amount to '10000'.</span></span>
35. <span data-ttu-id="8f080-148">Haga clic en Salida.</span><span class="sxs-lookup"><span data-stu-id="8f080-148">Click Output.</span></span>
36. <span data-ttu-id="8f080-149">Haga clic en Informe.</span><span class="sxs-lookup"><span data-stu-id="8f080-149">Click Report.</span></span>
37. <span data-ttu-id="8f080-150">En el campo Dirección, seleccione "Distribuciones".</span><span class="sxs-lookup"><span data-stu-id="8f080-150">In the Direction field, select 'Dispatches'.</span></span>
38. <span data-ttu-id="8f080-151">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="8f080-151">Click OK.</span></span>
    * <span data-ttu-id="8f080-152">Revise la salida creada con las líneas de resumen al final.</span><span class="sxs-lookup"><span data-stu-id="8f080-152">Review the created output with the summary lines in the end.</span></span> <span data-ttu-id="8f080-153">Observe que se ha cambiado en comparación con la primera ejecución.</span><span class="sxs-lookup"><span data-stu-id="8f080-153">Note that it has been changed in comparison to the first run.</span></span>  

## <a name="run-this-configuration-in-debug-mode-to-review-the-collected-counting--summing-data"></a><span data-ttu-id="8f080-154">Ejecute esta configuración en modo depuración para revisar los datos recogidos de suma & recuento</span><span class="sxs-lookup"><span data-stu-id="8f080-154">Run this configuration in debug mode to review the collected counting & summing data</span></span>
1. <span data-ttu-id="8f080-155">Vaya a Administración de la organización > Informes electrónicos > Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="8f080-155">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="8f080-156">En el árbol, expanda "Intrastat modelo".</span><span class="sxs-lookup"><span data-stu-id="8f080-156">In the tree, expand 'Intrastat model'.</span></span>
3. <span data-ttu-id="8f080-157">En el árbol, expanda "Modelo de Intrastat\Intrastat (DE)".</span><span class="sxs-lookup"><span data-stu-id="8f080-157">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
4. <span data-ttu-id="8f080-158">En el árbol, seleccione "Modelo de Intrastat\Intrastat (DE)\Intrastat (DE) con recuento & suma".</span><span class="sxs-lookup"><span data-stu-id="8f080-158">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
5. <span data-ttu-id="8f080-159">En el panel de acciones, haga clic en Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="8f080-159">On the Action Pane, click Configurations.</span></span>
6. <span data-ttu-id="8f080-160">Haga clic en Parámetros de usuario.</span><span class="sxs-lookup"><span data-stu-id="8f080-160">Click User parameters.</span></span>
7. <span data-ttu-id="8f080-161">Seleccione Sí en el campo Ejecutar en modo depuración.</span><span class="sxs-lookup"><span data-stu-id="8f080-161">Select Yes in the Run in debug mode field.</span></span>
8. <span data-ttu-id="8f080-162">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="8f080-162">Click OK.</span></span>
9. <span data-ttu-id="8f080-163">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8f080-163">Close the page.</span></span>
10. <span data-ttu-id="8f080-164">Vaya a Impuestos > Declaraciones > Comercio exterior > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="8f080-164">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
11. <span data-ttu-id="8f080-165">Haga clic en Salida.</span><span class="sxs-lookup"><span data-stu-id="8f080-165">Click Output.</span></span>
12. <span data-ttu-id="8f080-166">Haga clic en Informe.</span><span class="sxs-lookup"><span data-stu-id="8f080-166">Click Report.</span></span>
13. <span data-ttu-id="8f080-167">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="8f080-167">Click OK.</span></span>
14. <span data-ttu-id="8f080-168">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8f080-168">Close the page.</span></span>
15. <span data-ttu-id="8f080-169">Vaya a Administración de la organización > Informes electrónicos > Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="8f080-169">Go to Organization administration > Electronic reporting > Configurations.</span></span>
16. <span data-ttu-id="8f080-170">En el árbol, expanda "Intrastat modelo".</span><span class="sxs-lookup"><span data-stu-id="8f080-170">In the tree, expand 'Intrastat model'.</span></span>
17. <span data-ttu-id="8f080-171">En el árbol, expanda "Modelo de Intrastat\Intrastat (DE)".</span><span class="sxs-lookup"><span data-stu-id="8f080-171">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
18. <span data-ttu-id="8f080-172">En el árbol, seleccione "Modelo de Intrastat\Intrastat (DE)\Intrastat (DE) con recuento & suma".</span><span class="sxs-lookup"><span data-stu-id="8f080-172">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
19. <span data-ttu-id="8f080-173">Haga clic en los registros de Depuración.</span><span class="sxs-lookup"><span data-stu-id="8f080-173">Click Debug logs.</span></span>
    * <span data-ttu-id="8f080-174">Tenga en cuenta que se ha creado un registro de depuración para el proceso de ejecución de la configuración seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8f080-174">Note that a debug log record has been created for the execution process of the selected configuration.</span></span>  
20. <span data-ttu-id="8f080-175">Haga clic en Vincular.</span><span class="sxs-lookup"><span data-stu-id="8f080-175">Click Attach.</span></span>
21. <span data-ttu-id="8f080-176">Haga clic en Abrir.</span><span class="sxs-lookup"><span data-stu-id="8f080-176">Click Open.</span></span>
    * <span data-ttu-id="8f080-177">Revise el archivo XML creado que contiene los detalles de recuento y suma obtenidos durante la ejecución de la configuración seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8f080-177">Review the created XML file that contains counting and summing details that were collected during the execution of the selected configuration.</span></span>  

