--- 
title: "Producir el informe electrónico de contabilidad de libro mayor del producto mexicano versión 1.1"
description: "Esta tarea le muestra todos los pasos necesarios para configurar la generación de archivos XML electrónicos de cuenta contable mediante la herramienta de informes electrónicos."
author: sndray
manager: AnnBe
ms.date: 11/14/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2ef0348c0b3a051de6cbb725efbd8e30e7968bd3
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="produce-mexican-electronic-ledger-accounting-report-version-11"></a><span data-ttu-id="397bc-103">Producir el informe electrónico de contabilidad de libro mayor del producto mexicano versión 1.1</span><span class="sxs-lookup"><span data-stu-id="397bc-103">Produce Mexican electronic ledger accounting report version 1.1</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="397bc-104">Esta tarea le muestra todos los pasos necesarios para configurar la generación de archivos XML electrónicos de cuenta contable mediante la herramienta de informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="397bc-104">This task walks through all necessary steps to configure the generation of electronic ledger accounting XML files by using the Electronic Reporting tool.</span></span> <span data-ttu-id="397bc-105">Puede importar desde el centro de recursos de AX el modelo y los formatos de archivos XML para generar los extractos.</span><span class="sxs-lookup"><span data-stu-id="397bc-105">You can import from the AX resource center the model and formats of XML files to generate the statements.</span></span> 


## <a name="import-a-configuration-including-xml-formats"></a><span data-ttu-id="397bc-106">Importación de una configuración con formatos XML</span><span class="sxs-lookup"><span data-stu-id="397bc-106">Import a configuration including XML formats</span></span>
1. <span data-ttu-id="397bc-107">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="397bc-107">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="397bc-108">En la lista Proveedores de configuración, haga clic en Definir como activo en el cuadro de proveedor de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="397bc-108">In the Configuration providers list, click Set active on the Microsoft provider box.</span></span>
    * <span data-ttu-id="397bc-109">Si el proveedor de Microsoft ya es el proveedor activo, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="397bc-109">If the Microsoft provider is already the active provider, you can skip this step.</span></span>  
3. <span data-ttu-id="397bc-110">En la lista Proveedores de configuración, haga clic en el vínculo Repositorios en el cuadro de proveedor de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="397bc-110">In the Configuration providers list, click the Repositories link on the Microsoft provider box.</span></span>
4. <span data-ttu-id="397bc-111">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="397bc-111">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="397bc-112">Haga clic en Crear un repositorio.</span><span class="sxs-lookup"><span data-stu-id="397bc-112">Click Create a repository.</span></span>
6. <span data-ttu-id="397bc-113">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="397bc-113">In the Name field, type a value.</span></span>
7. <span data-ttu-id="397bc-114">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="397bc-114">In the Description field, type a value.</span></span>
8. <span data-ttu-id="397bc-115">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="397bc-115">Click OK.</span></span>
9. <span data-ttu-id="397bc-116">En la lista, seleccione la configuración que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="397bc-116">In the list, select the configuration that you just created.</span></span>
10. <span data-ttu-id="397bc-117">En el panel de acciones, haga clic en Abrir.</span><span class="sxs-lookup"><span data-stu-id="397bc-117">On the action pane, click Open.</span></span>
11. <span data-ttu-id="397bc-118">En el árbol, seleccione Modelo electrónico de cuenta contable MX.</span><span class="sxs-lookup"><span data-stu-id="397bc-118">In the tree, select 'Electronic ledger accounting model MX'.</span></span>
12. <span data-ttu-id="397bc-119">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="397bc-119">Click Import.</span></span>
13. <span data-ttu-id="397bc-120">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="397bc-120">Click Yes.</span></span>
14. <span data-ttu-id="397bc-121">En el árbol, seleccione Modelo electrónico de cuenta contable MX\Libro mayor auxiliar XML MX.</span><span class="sxs-lookup"><span data-stu-id="397bc-121">In the tree, select 'Electronic ledger accounting model MX\Auxiliary Ledger XML MX'.</span></span>
15. <span data-ttu-id="397bc-122">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="397bc-122">Click Import.</span></span>
16. <span data-ttu-id="397bc-123">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="397bc-123">Click Yes.</span></span>
17. <span data-ttu-id="397bc-124">En el árbol, seleccione Modelo electrónico de cuenta contable MX\Plan contable XML MX.</span><span class="sxs-lookup"><span data-stu-id="397bc-124">In the tree, select 'Electronic ledger accounting model MX\Chart of Account XML MX'.</span></span>
18. <span data-ttu-id="397bc-125">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="397bc-125">Click Import.</span></span>
19. <span data-ttu-id="397bc-126">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="397bc-126">Click Yes.</span></span>
20. <span data-ttu-id="397bc-127">En el árbol, seleccione Modelo electrónico de cuenta contable MX\Diarios XML MX.</span><span class="sxs-lookup"><span data-stu-id="397bc-127">In the tree, select 'Electronic ledger accounting model MX\Journals XML MX'.</span></span>
21. <span data-ttu-id="397bc-128">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="397bc-128">Click Import.</span></span>
22. <span data-ttu-id="397bc-129">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="397bc-129">Click Yes.</span></span>
23. <span data-ttu-id="397bc-130">En el árbol, seleccione Modelo electrónico de cuenta contable MX\Saldo de comprobación XML MX.</span><span class="sxs-lookup"><span data-stu-id="397bc-130">In the tree, select 'Electronic ledger accounting model MX\Trial Balance XML MX'.</span></span>
24. <span data-ttu-id="397bc-131">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="397bc-131">Click Import.</span></span>
25. <span data-ttu-id="397bc-132">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="397bc-132">Click Yes.</span></span>
26. <span data-ttu-id="397bc-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="397bc-133">Close the page.</span></span>
27. <span data-ttu-id="397bc-134">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="397bc-134">Close the page.</span></span>
28. <span data-ttu-id="397bc-135">Haga clic en el cuadro Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="397bc-135">Click the Configurations box.</span></span>
29. <span data-ttu-id="397bc-136">En el árbol, seleccione Modelo electrónico de cuenta contable MX.</span><span class="sxs-lookup"><span data-stu-id="397bc-136">In the tree, select 'Electronic ledger accounting model MX'.</span></span>
30. <span data-ttu-id="397bc-137">En el árbol, expanda "En el árbol, expanda "Modelo electrónico de cuenta contable MX".</span><span class="sxs-lookup"><span data-stu-id="397bc-137">In the tree, expand 'In the treem expand 'Electronic ledger accoutning model MX''.</span></span>
    * <span data-ttu-id="397bc-138">Podrá ver los cuatro (4) formatos XML que importó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="397bc-138">You will be able to see the four (4) XML formats that you previously imported.</span></span>  

## <a name="configure-general-ledger-parameters-for-electronic-reporting-mapping"></a><span data-ttu-id="397bc-139">Configuración de parámetros de contabilidad general para asignar informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="397bc-139">Configure general ledger parameters for electronic reporting mapping</span></span>
1. <span data-ttu-id="397bc-140">Vaya a Contabilidad general > Configuración de contabilidad > Parámetros de Contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="397bc-140">Go to General ledger > Ledger setup > General ledger parameters.</span></span>
2. <span data-ttu-id="397bc-141">En el campo Saldo de comprobación, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="397bc-141">In the Trial balance field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="397bc-142">En la lista, seleccione el formato XML de saldo de comprobación.</span><span class="sxs-lookup"><span data-stu-id="397bc-142">In the list, select the Trial Balance XML format</span></span>
4. <span data-ttu-id="397bc-143">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="397bc-143">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="397bc-144">En el campo Libro mayor auxiliar, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="397bc-144">In the Auxiliary ledger field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="397bc-145">En la lista, seleccione el formato XML de libro mayor auxiliar.</span><span class="sxs-lookup"><span data-stu-id="397bc-145">In the list, selecy the Auxiliary ledger XML format</span></span>
7. <span data-ttu-id="397bc-146">En el campo Movimientos contables, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="397bc-146">In the Ledger entries field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="397bc-147">En la lista, seleccione el formato XML para diarios.</span><span class="sxs-lookup"><span data-stu-id="397bc-147">In the list, select the Journal XML format</span></span>
9. <span data-ttu-id="397bc-148">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="397bc-148">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="397bc-149">En el campo Plan contable, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="397bc-149">In the Chart of accounts field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="397bc-150">En la lista, seleccione el formato XML para plan de cuentas.</span><span class="sxs-lookup"><span data-stu-id="397bc-150">In the list, select the Chart of Account XML format.</span></span>
12. <span data-ttu-id="397bc-151">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="397bc-151">Click Save.</span></span>

## <a name="generate-xml-files"></a><span data-ttu-id="397bc-152">Generación de archivos XML</span><span class="sxs-lookup"><span data-stu-id="397bc-152">Generate XML files</span></span>
1. <span data-ttu-id="397bc-153">Vaya Contabilidad general > Consultas e informes > Informes de contabilidad > Extracto electrónico de cuenta contable.</span><span class="sxs-lookup"><span data-stu-id="397bc-153">Go to General ledger > Inquiries and reports > Ledger reports > Electronic ledger accounting statement.</span></span>
2. <span data-ttu-id="397bc-154">En el campo Grupo de cuentas de consolidación de SAT, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="397bc-154">In the SAT consolidation account group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="397bc-155">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="397bc-155">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="397bc-156">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="397bc-156">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="397bc-157">En el campo Período, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="397bc-157">In the Period field, enter a date.</span></span>
6. <span data-ttu-id="397bc-158">Active o desactive la opción Saldo de comprobación.</span><span class="sxs-lookup"><span data-stu-id="397bc-158">Check or uncheck the Trial Balance opcion</span></span>
    * <span data-ttu-id="397bc-159">Esta opción genera los archivos XML del plan contable y el saldo de comprobación.</span><span class="sxs-lookup"><span data-stu-id="397bc-159">This option generates the Chart of Account and Trial Balance XML files.</span></span>  
7. <span data-ttu-id="397bc-160">Active o desactive la casilla Movimientos contables.</span><span class="sxs-lookup"><span data-stu-id="397bc-160">Select or clear the Ledger entries check box.</span></span>
8. <span data-ttu-id="397bc-161">Active o desactive la casilla Libro mayor auxiliar.</span><span class="sxs-lookup"><span data-stu-id="397bc-161">Select or clear the Auxiliary ledger check box.</span></span>
9. <span data-ttu-id="397bc-162">En el campo Tipo de solicitud, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="397bc-162">In the Request type field, select an option.</span></span>
10. <span data-ttu-id="397bc-163">En el campo Número de pedido, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="397bc-163">In the Order number field, type a value.</span></span>
11. <span data-ttu-id="397bc-164">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="397bc-164">Click OK.</span></span>


