--- 
title: "Generar una declaración intrastat de la UE"
description: "Este procedimiento le guía por los pasos necesarios para exportar la declaración de Intrastat en el formato de archivo electrónico y obtener una vista previa los datos de la declaración en formato Excel."
author: Anasyash
manager: AnnBe
ms.date: 06/09/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: f74da78232c477224c8fa753e9755b7f9d13174d
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="generate-an-eu-intrastat-declaration"></a><span data-ttu-id="55828-103">Generar una declaración intrastat de la UE</span><span class="sxs-lookup"><span data-stu-id="55828-103">Generate an EU Intrastat declaration</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="55828-104">Este procedimiento le guía por los pasos necesarios para exportar la declaración de Intrastat en el formato de archivo electrónico y obtener una vista previa los datos de la declaración en formato Excel.</span><span class="sxs-lookup"><span data-stu-id="55828-104">This procedure walks you through the steps required to export the Intrastat declaration in the electronic file format and preview the declaration data in an Excel format.</span></span> 

<span data-ttu-id="55828-105">Para poder completar este procedimiento, debe transferir transacciones a intrastat.</span><span class="sxs-lookup"><span data-stu-id="55828-105">Before you can complete this procedure, you must transfer transactions to the Intrastat.</span></span> 

<span data-ttu-id="55828-106">Este procedimiento se creó con los datos de demostración de la empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="55828-106">This procedure was created using the demo data company DEMF.</span></span>


## <a name="import-configurations-with-settings"></a><span data-ttu-id="55828-107">Importar configuraciones con ajustes</span><span class="sxs-lookup"><span data-stu-id="55828-107">Import configurations with settings</span></span>
1. <span data-ttu-id="55828-108">Vaya a Áreas de trabajo > Informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="55828-108">Go to Workspaces > Electronic reporting</span></span>
2. <span data-ttu-id="55828-109">Haga clic en Definir como activo.</span><span class="sxs-lookup"><span data-stu-id="55828-109">Click Set active.</span></span>
3. <span data-ttu-id="55828-110">Haga clic en Repositorios.</span><span class="sxs-lookup"><span data-stu-id="55828-110">Click Repositories.</span></span>
4. <span data-ttu-id="55828-111">Haga clic en Abrir.</span><span class="sxs-lookup"><span data-stu-id="55828-111">Click Open.</span></span>
5. <span data-ttu-id="55828-112">Abra el filtro de columna Nombre de configuración.</span><span class="sxs-lookup"><span data-stu-id="55828-112">Open Configuration name column filter.</span></span>
6. <span data-ttu-id="55828-113">Aplique un filtro en el campo "Nombre de configuración" con un valor de "Intrastat (DE)", mediante el operador de filtro "empieza por".</span><span class="sxs-lookup"><span data-stu-id="55828-113">Apply a filter on the "Configuration name" field, with a value of "Intrastat (DE)", using the "begins with" filter operator.</span></span>
    * <span data-ttu-id="55828-114">Debe seleccionar el nombre de la configuración aplicable para el país de su entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="55828-114">You should select the configuration name applicable for the country of your legal entity.</span></span> <span data-ttu-id="55828-115">Este procedimiento usa la entidad jurídica alemana (DEMF) como ejemplo, por tanto se debe elegir "Intrastat (DE)".</span><span class="sxs-lookup"><span data-stu-id="55828-115">This procedure uses the German legal entity (DEMF) as an example, therefore "Intrastat (DE)" should be chosen.</span></span>  
    * <span data-ttu-id="55828-116">Haga clic en Importar y, a continuación, en Sí.</span><span class="sxs-lookup"><span data-stu-id="55828-116">Click Import and then click Yes.</span></span>  
7. <span data-ttu-id="55828-117">Abra el filtro de columna Nombre de configuración.</span><span class="sxs-lookup"><span data-stu-id="55828-117">Open Configuration name column filter.</span></span>
8. <span data-ttu-id="55828-118">Aplique un filtro en el campo "Nombre de configuración" con un valor de "informe intrastat", mediante el operador de filtro "empieza por".</span><span class="sxs-lookup"><span data-stu-id="55828-118">Apply a filter on the "Configuration name" field, with a value of "intrastat report", using the "begins with" filter operator.</span></span>
    * <span data-ttu-id="55828-119">Haga clic en Importar y, a continuación, en Sí.</span><span class="sxs-lookup"><span data-stu-id="55828-119">Click Import and then click Yes.</span></span>  

## <a name="set-up-foreign-trade-parameters"></a><span data-ttu-id="55828-120">Configurar parámetros de comercio exterior</span><span class="sxs-lookup"><span data-stu-id="55828-120">Set up Foreign trade parameters</span></span>
1. <span data-ttu-id="55828-121">Vaya a Impuestos > Configuración > Comercio exterior > Parámetros de comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="55828-121">Go to Tax > Setup > Foreign trade > Foreign trade parameters</span></span>
2. <span data-ttu-id="55828-122">Expanda la sección Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="55828-122">Expand the Electronic reporting section.</span></span>
3. <span data-ttu-id="55828-123">En el campo Asignación de formato de archivo, especifique o seleccione un valor Intrastat (DE).</span><span class="sxs-lookup"><span data-stu-id="55828-123">In the File format mapping field, enter or select a value Intrastat (DE)</span></span>
4. <span data-ttu-id="55828-124">En el campo Asignación de formato de informe, especifique o seleccione un valor para Informe intrastat</span><span class="sxs-lookup"><span data-stu-id="55828-124">In the Report format mapping field, enter or select a value Intrastat report</span></span>
5. <span data-ttu-id="55828-125">Expanda la sección Reglas de redondeo.</span><span class="sxs-lookup"><span data-stu-id="55828-125">Expand the Rounding rules section.</span></span>
    * <span data-ttu-id="55828-126">Debe configurar las reglas de redondeo que son aplicables en su país o región para informes de intrastat.</span><span class="sxs-lookup"><span data-stu-id="55828-126">You should set up rounding rules that are applicable in your country/region for Intrastat reporting.</span></span>  
6. <span data-ttu-id="55828-127">En el campo Regla de redondeo, escriba un número</span><span class="sxs-lookup"><span data-stu-id="55828-127">In the Rounding rule field, enter a number.</span></span>
    * <span data-ttu-id="55828-128">Especifique la precisión del redondeo, por ejemplo, especifique “0,01".</span><span class="sxs-lookup"><span data-stu-id="55828-128">Enter rounding precision, for example, enter '0.01'.</span></span>  
7. <span data-ttu-id="55828-129">En el campo Número de decimales para el importe, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="55828-129">In the Number of decimals for amount field, enter a number.</span></span>
    * <span data-ttu-id="55828-130">Por ejemplo, escribe "2".</span><span class="sxs-lookup"><span data-stu-id="55828-130">For example, enter '2'.</span></span>  
8. <span data-ttu-id="55828-131">En el campo Redondeo inferior a 1 kg, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="55828-131">In the Rounding below 1 kg field, select an option.</span></span>
    * <span data-ttu-id="55828-132">Por ejemplo, seleccione "Redondeo a 1 kg".</span><span class="sxs-lookup"><span data-stu-id="55828-132">For example, select 'Rounding up to 1 kg'.</span></span>  
9. <span data-ttu-id="55828-133">En el campo Regla de redondeo, escriba un número</span><span class="sxs-lookup"><span data-stu-id="55828-133">In the Rounding rule field, enter a number.</span></span>
    * <span data-ttu-id="55828-134">Por ejemplo, especifique "1" para redondear el peso al número entero.</span><span class="sxs-lookup"><span data-stu-id="55828-134">For example, enter '1' for rounding weight to the integer.</span></span>  
10. <span data-ttu-id="55828-135">Expanda la sección Límite mínimo.</span><span class="sxs-lookup"><span data-stu-id="55828-135">Expand the Minimum limit section.</span></span>
11. <span data-ttu-id="55828-136">En el campo Peso, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="55828-136">In the Weight field, enter a number.</span></span>
    * <span data-ttu-id="55828-137">Por ejemplo, especifique "10" como el peso mínimo.</span><span class="sxs-lookup"><span data-stu-id="55828-137">For example, enter '10' as the minimum weight.</span></span>  
12. <span data-ttu-id="55828-138">En el campo Importe, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="55828-138">In the Amount field, enter a number.</span></span>
    * <span data-ttu-id="55828-139">Por ejemplo, especifique "200" como el importe mínimo.</span><span class="sxs-lookup"><span data-stu-id="55828-139">For example, enter '200' as the minimum amount.</span></span>  
13. <span data-ttu-id="55828-140">En el campo Código Intrastat de la mercancía, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="55828-140">In the Commodity field, enter or select a value.</span></span>

## <a name="set-up-compression-of-intrastat"></a><span data-ttu-id="55828-141">Configurar la compresión de Intrastat</span><span class="sxs-lookup"><span data-stu-id="55828-141">Set up Compression of Intrastat</span></span>
1. <span data-ttu-id="55828-142">Vaya a Impuesto > Configurar > Comercio exterior > Compresión de Intrastat.</span><span class="sxs-lookup"><span data-stu-id="55828-142">Go to Tax > Setup > Foreign trade > Compression of Intrastat.</span></span>
2. <span data-ttu-id="55828-143">Haga clic en Quitar.</span><span class="sxs-lookup"><span data-stu-id="55828-143">Click Remove.</span></span>
3. <span data-ttu-id="55828-144">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="55828-144">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="55828-145">Por ejemplo, seleccione Mercancía en la sección Disponible.</span><span class="sxs-lookup"><span data-stu-id="55828-145">For example, select Commodity in the Available section.</span></span>  
4. <span data-ttu-id="55828-146">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="55828-146">Click Add.</span></span>

## <a name="generate-intrastat-declaration"></a><span data-ttu-id="55828-147">Generar la declaración de Intrastat</span><span class="sxs-lookup"><span data-stu-id="55828-147">Generate Intrastat declaration</span></span>
1. <span data-ttu-id="55828-148">Vaya a Impuestos > Declaraciones > Comercio exterior > Intrastat</span><span class="sxs-lookup"><span data-stu-id="55828-148">Go to Tax > Declarations > Foreign trade > Intrastat</span></span>
2. <span data-ttu-id="55828-149">Haga clic en Validar.</span><span class="sxs-lookup"><span data-stu-id="55828-149">Click Validate.</span></span>
    * <span data-ttu-id="55828-150">La validación se realiza en función del campo Comprobar configuración de la página Parámetros de comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="55828-150">The validation is done according to the Check setup field on the Foreign trade parameters page.</span></span>  
3. <span data-ttu-id="55828-151">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="55828-151">Click OK.</span></span>
4. <span data-ttu-id="55828-152">Haga clic en Actualizar.</span><span class="sxs-lookup"><span data-stu-id="55828-152">Click Update.</span></span>
5. <span data-ttu-id="55828-153">Haga clic en Límite mínimo.</span><span class="sxs-lookup"><span data-stu-id="55828-153">Click Minimum limit.</span></span>
6. <span data-ttu-id="55828-154">En el campo Fecha inicial, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="55828-154">In the Start date field, enter a date.</span></span>
    * <span data-ttu-id="55828-155">Por ejemplo, escriba 1 de enero de 2015.</span><span class="sxs-lookup"><span data-stu-id="55828-155">For example, enter January 1, 2015.</span></span>  
7. <span data-ttu-id="55828-156">Seleccione Sí en el campo Comprimir.</span><span class="sxs-lookup"><span data-stu-id="55828-156">Select Yes in the Compress field.</span></span>
8. <span data-ttu-id="55828-157">En el campo Fecha final, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="55828-157">In the End date field, enter a date.</span></span>
    * <span data-ttu-id="55828-158">Por ejemplo, escriba 31 de enero de 2015.</span><span class="sxs-lookup"><span data-stu-id="55828-158">For example, enter January 31, 2015.</span></span>  
9. <span data-ttu-id="55828-159">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="55828-159">Click OK.</span></span>
10. <span data-ttu-id="55828-160">Haga clic en Actualizar.</span><span class="sxs-lookup"><span data-stu-id="55828-160">Click Update.</span></span>
11. <span data-ttu-id="55828-161">Haga clic en Comprimir.</span><span class="sxs-lookup"><span data-stu-id="55828-161">Click Compress.</span></span>
    * <span data-ttu-id="55828-162">Esta compresión se produce en función de cómo se establece la configuración la Compresión de intrastat.</span><span class="sxs-lookup"><span data-stu-id="55828-162">This compression happens according to how you set the Compression of intrastate settings.</span></span>  
12. <span data-ttu-id="55828-163">En el campo Fecha inicial, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="55828-163">In the Start date field, enter a date.</span></span>
    * <span data-ttu-id="55828-164">Por ejemplo, escriba 1 de enero de 2015.</span><span class="sxs-lookup"><span data-stu-id="55828-164">For example, enter January 1, 2015.</span></span>  
13. <span data-ttu-id="55828-165">En el campo Fecha final, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="55828-165">In the End date field, enter a date.</span></span>
    * <span data-ttu-id="55828-166">Por ejemplo, escriba 31 de enero de 2015.</span><span class="sxs-lookup"><span data-stu-id="55828-166">For example, enter 31st January 2015.</span></span>  
14. <span data-ttu-id="55828-167">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="55828-167">Click OK.</span></span>
15. <span data-ttu-id="55828-168">Haga clic en Actualizar.</span><span class="sxs-lookup"><span data-stu-id="55828-168">Click Update.</span></span>
16. <span data-ttu-id="55828-169">Haga clic en Volver a generar los números de secuencia.</span><span class="sxs-lookup"><span data-stu-id="55828-169">Click Regenerate sequence numbers.</span></span>
17. <span data-ttu-id="55828-170">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="55828-170">Click OK.</span></span>
18. <span data-ttu-id="55828-171">Haga clic en Salida.</span><span class="sxs-lookup"><span data-stu-id="55828-171">Click Output.</span></span>
19. <span data-ttu-id="55828-172">Haga clic en Informe.</span><span class="sxs-lookup"><span data-stu-id="55828-172">Click Report.</span></span>
20. <span data-ttu-id="55828-173">En el campo Fecha inicial, especifique la primera fecha del período de informes.</span><span class="sxs-lookup"><span data-stu-id="55828-173">In the From date field, enter the first date of the reporting period.</span></span>
    * <span data-ttu-id="55828-174">Por ejemplo, establezca la fecha en el 1 de enero de 2015.</span><span class="sxs-lookup"><span data-stu-id="55828-174">For example, set the date to January 1, 2015.</span></span>  
21. <span data-ttu-id="55828-175">Especifique una fecha en el campo Fecha final.</span><span class="sxs-lookup"><span data-stu-id="55828-175">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="55828-176">Por ejemplo, escriba 31 de enero de 2015.</span><span class="sxs-lookup"><span data-stu-id="55828-176">For example, enter January 31, 2015.</span></span>  
22. <span data-ttu-id="55828-177">Seleccione Sí en el campo Generar archivo.</span><span class="sxs-lookup"><span data-stu-id="55828-177">Select Yes in the Generate file field.</span></span>
23. <span data-ttu-id="55828-178">En el campo Nombre de archivo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="55828-178">In the File name field, type a value.</span></span>
24. <span data-ttu-id="55828-179">Seleccione Sí en el campo Generar informe.</span><span class="sxs-lookup"><span data-stu-id="55828-179">Select Yes in the Generate report field.</span></span>
25. <span data-ttu-id="55828-180">En el campo Nombre de archivo del informe, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="55828-180">In the Report file name field, type a value.</span></span>
26. <span data-ttu-id="55828-181">En el campo Dirección, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="55828-181">In the Direction field, select an option.</span></span>
    * <span data-ttu-id="55828-182">Por ejemplo, seleccione "Distribuciones".</span><span class="sxs-lookup"><span data-stu-id="55828-182">For example, select 'Dispatches'.</span></span>  
27. <span data-ttu-id="55828-183">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="55828-183">Click OK.</span></span>


