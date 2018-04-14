--- 
title: "Producir el informe electrónico de contabilidad de libro mayor del producto mexicano versión 1.1"
description: "Esta tarea le muestra todos los pasos necesarios para configurar la generación de archivos XML electrónicos de cuenta contable mediante la herramienta de informes electrónicos."
author: sndray
manager: AnnBe
ms.date: 10/31/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 3804e79910ab11e22464daee4e268ba540f559bd
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="produce-mexican-electronic-ledger-accounting-report-version-11"></a><span data-ttu-id="defc9-103">Producir el informe electrónico de contabilidad de libro mayor del producto mexicano versión 1.1</span><span class="sxs-lookup"><span data-stu-id="defc9-103">Produce Mexican electronic ledger accounting report version 1.1</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="defc9-104">Esta tarea le muestra todos los pasos necesarios para configurar la generación de archivos XML electrónicos de cuenta contable mediante la herramienta de informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="defc9-104">This task walks through all necessary steps to configure the generation of electronic ledger accounting XML files by using the Electronic Reporting tool.</span></span> <span data-ttu-id="defc9-105">Puede importar desde el centro de recursos de AX el modelo y los formatos de archivos XML para generar los extractos.</span><span class="sxs-lookup"><span data-stu-id="defc9-105">You can import from the AX resource center the model and formats of XML files to generate the statements.</span></span> 


## <a name="import-a-configuration-including-xml-formats"></a><span data-ttu-id="defc9-106">Importación de una configuración con formatos XML</span><span class="sxs-lookup"><span data-stu-id="defc9-106">Import a configuration including XML formats</span></span>
1. <span data-ttu-id="defc9-107">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="defc9-107">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="defc9-108">En la lista Proveedores de configuración, haga clic en Definir como activo en el cuadro de proveedor de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="defc9-108">In the Configuration providers list, click Set active on the Microsoft provider box.</span></span>
    * <span data-ttu-id="defc9-109">Si el proveedor de Microsoft ya es el proveedor activo, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="defc9-109">If the Microsoft provider is already the active provider, you can skip this step.</span></span>  
3. <span data-ttu-id="defc9-110">En la lista Proveedores de configuración, haga clic en el vínculo Repositorios en el cuadro de proveedor de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="defc9-110">In the Configuration providers list, click the Repositories link on the Microsoft provider box.</span></span>
4. <span data-ttu-id="defc9-111">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="defc9-111">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="defc9-112">Haga clic en Crear un repositorio.</span><span class="sxs-lookup"><span data-stu-id="defc9-112">Click Create a repository.</span></span>
6. <span data-ttu-id="defc9-113">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="defc9-113">In the Name field, type a value.</span></span>
7. <span data-ttu-id="defc9-114">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="defc9-114">In the Description field, type a value.</span></span>
8. <span data-ttu-id="defc9-115">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="defc9-115">Click OK.</span></span>
9. <span data-ttu-id="defc9-116">En la lista, seleccione la configuración que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="defc9-116">In the list, select the configuration that you just created.</span></span>
10. <span data-ttu-id="defc9-117">En el panel de acciones, haga clic en Abrir.</span><span class="sxs-lookup"><span data-stu-id="defc9-117">On the action pane, click Open.</span></span>
11. <span data-ttu-id="defc9-118">En el árbol, seleccione Modelo electrónico de cuenta contable MX.</span><span class="sxs-lookup"><span data-stu-id="defc9-118">In the tree, select 'Electronic ledger accounting model MX'.</span></span>
12. <span data-ttu-id="defc9-119">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="defc9-119">Click Import.</span></span>
13. <span data-ttu-id="defc9-120">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="defc9-120">Click Yes.</span></span>
14. <span data-ttu-id="defc9-121">En el árbol, seleccione Modelo electrónico de cuenta contable MX\Libro mayor auxiliar XML MX.</span><span class="sxs-lookup"><span data-stu-id="defc9-121">In the tree, select 'Electronic ledger accounting model MX\Auxiliary Ledger XML MX'.</span></span>
15. <span data-ttu-id="defc9-122">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="defc9-122">Click Import.</span></span>
16. <span data-ttu-id="defc9-123">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="defc9-123">Click Yes.</span></span>
17. <span data-ttu-id="defc9-124">En el árbol, seleccione Modelo electrónico de cuenta contable MX\Plan contable XML MX.</span><span class="sxs-lookup"><span data-stu-id="defc9-124">In the tree, select 'Electronic ledger accounting model MX\Chart of Account XML MX'.</span></span>
18. <span data-ttu-id="defc9-125">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="defc9-125">Click Import.</span></span>
19. <span data-ttu-id="defc9-126">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="defc9-126">Click Yes.</span></span>
20. <span data-ttu-id="defc9-127">En el árbol, seleccione Modelo electrónico de cuenta contable MX\Diarios XML MX.</span><span class="sxs-lookup"><span data-stu-id="defc9-127">In the tree, select 'Electronic ledger accounting model MX\Journals XML MX'.</span></span>
21. <span data-ttu-id="defc9-128">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="defc9-128">Click Import.</span></span>
22. <span data-ttu-id="defc9-129">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="defc9-129">Click Yes.</span></span>
23. <span data-ttu-id="defc9-130">En el árbol, seleccione Modelo electrónico de cuenta contable MX\Saldo de comprobación XML MX.</span><span class="sxs-lookup"><span data-stu-id="defc9-130">In the tree, select 'Electronic ledger accounting model MX\Trial Balance XML MX'.</span></span>
24. <span data-ttu-id="defc9-131">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="defc9-131">Click Import.</span></span>
25. <span data-ttu-id="defc9-132">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="defc9-132">Click Yes.</span></span>
26. <span data-ttu-id="defc9-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="defc9-133">Close the page.</span></span>
27. <span data-ttu-id="defc9-134">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="defc9-134">Close the page.</span></span>
28. <span data-ttu-id="defc9-135">Haga clic en el cuadro Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="defc9-135">Click the Configurations box.</span></span>
29. <span data-ttu-id="defc9-136">En el árbol, seleccione Modelo electrónico de cuenta contable MX.</span><span class="sxs-lookup"><span data-stu-id="defc9-136">In the tree, select 'Electronic ledger accounting model MX'.</span></span>
30. <span data-ttu-id="defc9-137">En el árbol, expanda "En el árbol, expanda "Modelo electrónico de cuenta contable MX".</span><span class="sxs-lookup"><span data-stu-id="defc9-137">In the tree, expand 'In the tree expand 'Electronic ledger accounting model MX''.</span></span>
    * <span data-ttu-id="defc9-138">Podrá ver los cuatro (4) formatos XML que importó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="defc9-138">You will be able to see the four (4) XML formats that you previously imported.</span></span>  

## <a name="configure-general-ledger-parameters-for-electronic-reporting-mapping"></a><span data-ttu-id="defc9-139">Configuración de parámetros de contabilidad general para asignar informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="defc9-139">Configure general ledger parameters for electronic reporting mapping</span></span>
1. <span data-ttu-id="defc9-140">Vaya a Contabilidad general > Configuración de contabilidad > Parámetros de Contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="defc9-140">Go to General ledger > Ledger setup > General ledger parameters.</span></span>
2. <span data-ttu-id="defc9-141">En el campo Saldo de comprobación, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="defc9-141">In the Trial balance field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="defc9-142">En la lista, seleccione el formato XML de saldo de comprobación.</span><span class="sxs-lookup"><span data-stu-id="defc9-142">In the list, select the Trial Balance XML format</span></span>
4. <span data-ttu-id="defc9-143">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="defc9-143">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="defc9-144">En el campo Libro mayor auxiliar, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="defc9-144">In the Auxiliary ledger field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="defc9-145">En la lista, seleccione el formato XML de libro mayor auxiliar.</span><span class="sxs-lookup"><span data-stu-id="defc9-145">In the list, select the Auxiliary ledger XML format</span></span>
7. <span data-ttu-id="defc9-146">En el campo Movimientos contables, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="defc9-146">In the Ledger entries field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="defc9-147">En la lista, seleccione el formato XML para diarios.</span><span class="sxs-lookup"><span data-stu-id="defc9-147">In the list, select the Journal XML format</span></span>
9. <span data-ttu-id="defc9-148">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="defc9-148">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="defc9-149">En el campo Plan contable, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="defc9-149">In the Chart of accounts field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="defc9-150">En la lista, seleccione el formato XML para plan de cuentas.</span><span class="sxs-lookup"><span data-stu-id="defc9-150">In the list, select the Chart of Account XML format.</span></span>
12. <span data-ttu-id="defc9-151">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="defc9-151">Click Save.</span></span>

## <a name="generate-xml-files"></a><span data-ttu-id="defc9-152">Generación de archivos XML</span><span class="sxs-lookup"><span data-stu-id="defc9-152">Generate XML files</span></span>
1. <span data-ttu-id="defc9-153">Vaya Contabilidad general > Consultas e informes > Informes de contabilidad > Extracto electrónico de cuenta contable.</span><span class="sxs-lookup"><span data-stu-id="defc9-153">Go to General ledger > Inquiries and reports > Ledger reports > Electronic ledger accounting statement.</span></span>
2. <span data-ttu-id="defc9-154">En el campo Grupo de cuentas de consolidación de SAT, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="defc9-154">In the SAT consolidation account group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="defc9-155">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="defc9-155">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="defc9-156">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="defc9-156">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="defc9-157">En el campo Período, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="defc9-157">In the Period field, enter a date.</span></span>
6. <span data-ttu-id="defc9-158">Active o desactive la opción Saldo de comprobación</span><span class="sxs-lookup"><span data-stu-id="defc9-158">Check or uncheck the Trial Balance option</span></span>
    * <span data-ttu-id="defc9-159">Esta opción genera los archivos XML del plan contable y el saldo de comprobación.</span><span class="sxs-lookup"><span data-stu-id="defc9-159">This option generates the Chart of Account and Trial Balance XML files.</span></span>  
7. <span data-ttu-id="defc9-160">Active o desactive la casilla Movimientos contables.</span><span class="sxs-lookup"><span data-stu-id="defc9-160">Select or clear the Ledger entries check box.</span></span>
8. <span data-ttu-id="defc9-161">Active o desactive la casilla Libro mayor auxiliar.</span><span class="sxs-lookup"><span data-stu-id="defc9-161">Select or clear the Auxiliary ledger check box.</span></span>
9. <span data-ttu-id="defc9-162">En el campo Tipo de solicitud, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="defc9-162">In the Request type field, select an option.</span></span>
10. <span data-ttu-id="defc9-163">En el campo Número de pedido, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="defc9-163">In the Order number field, type a value.</span></span>
11. <span data-ttu-id="defc9-164">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="defc9-164">Click OK.</span></span>


