---
title: EUR-00011 Configurar informes de listas de ventas de la UE
description: Esta tarea le guía por una visión general de los requisitos previos necesarios para los Informes de listas de ventas de la UE.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionRepositoryTable, ERSolutionImport, SysQueryForm, SysQueryFieldLookUp,  TaxTable, TaxGroup, TaxItemGroup, TaxCountryRegionParameters, TaxVATNumTable, IntrastatParameters, CustTable, DirPartyQuickCreateForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c312e14247c42acd5e0de5df02833275d9e3a4f1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4407777"
---
# <a name="eur-00011-set-up-eu-sales-list-reporting"></a><span data-ttu-id="4bde3-103">EUR-00011 Configurar informes de listas de ventas de la UE</span><span class="sxs-lookup"><span data-stu-id="4bde3-103">EUR-00011 Set up EU sales list reporting</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4bde3-104">Esta tarea le guía por una visión general de los requisitos previos necesarios para los Informes de listas de ventas de la UE.</span><span class="sxs-lookup"><span data-stu-id="4bde3-104">This task walks you through an overview of the prerequisites required for EU sales list reporting.</span></span> <span data-ttu-id="4bde3-105">Para obtener más información acerca de los informes de la lista de ventas de la UE, incluidos requisitos previos necesarios, remítase a la Ayuda.</span><span class="sxs-lookup"><span data-stu-id="4bde3-105">For more information about EU Sales list reporting, including required prerequisites, refer to Help.</span></span>

<span data-ttu-id="4bde3-106">Esta tarea se aplica a todos los países o regiones europeos.</span><span class="sxs-lookup"><span data-stu-id="4bde3-106">This task applies to all European countries/regions.</span></span> <span data-ttu-id="4bde3-107">La guía se ha creado con la empresa de datos de demostración DEMF y, por tanto, Alemania como país o región nacional de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4bde3-107">The guide was created using the demo data company DEMF and consequently Germany as an exemplar domestic country/region.</span></span> <span data-ttu-id="4bde3-108">La guía también utiliza Portugal como país o región de la UE de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4bde3-108">The guide also uses Portugal as an exemplar EU country/region.</span></span>

<span data-ttu-id="4bde3-109">Estas tareas están destinadas a administradores del sistema.</span><span class="sxs-lookup"><span data-stu-id="4bde3-109">These tasks are intended for system administrators.</span></span>


## <a name="import-electronic-reporting-configurations-for-eu-sales-list-reporting"></a><span data-ttu-id="4bde3-110">Importar las configuraciones de informes electrónicos para informes de listas de ventas de la UE</span><span class="sxs-lookup"><span data-stu-id="4bde3-110">Import electronic reporting configurations for EU sales list reporting</span></span>
1. <span data-ttu-id="4bde3-111">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="4bde3-111">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="4bde3-112">Haga clic en Definir como activo.</span><span class="sxs-lookup"><span data-stu-id="4bde3-112">Click Set active.</span></span>
3. <span data-ttu-id="4bde3-113">Haga clic en Repositorios.</span><span class="sxs-lookup"><span data-stu-id="4bde3-113">Click Repositories.</span></span>
4. <span data-ttu-id="4bde3-114">Haga clic en Abrir.</span><span class="sxs-lookup"><span data-stu-id="4bde3-114">Click Open.</span></span>
5. <span data-ttu-id="4bde3-115">En el panel de acciones, haga clic en Opciones.</span><span class="sxs-lookup"><span data-stu-id="4bde3-115">On the Action Pane, click Options.</span></span>
6. <span data-ttu-id="4bde3-116">Haga clic en Ordenación o filtro avanzado.</span><span class="sxs-lookup"><span data-stu-id="4bde3-116">Click Advanced Filter/Sort.</span></span>
7. <span data-ttu-id="4bde3-117">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="4bde3-117">Click Add.</span></span>
8. <span data-ttu-id="4bde3-118">En el campo Campo, seleccione "Nombre de configuración".</span><span class="sxs-lookup"><span data-stu-id="4bde3-118">In the Field field, select 'Configuration name'.</span></span>
9. <span data-ttu-id="4bde3-119">En el campo Criterios, escriba "Lista de ventas de la UE (DE)".</span><span class="sxs-lookup"><span data-stu-id="4bde3-119">In the Criteria field, type 'EU Sales list (DE)'.</span></span>
10. <span data-ttu-id="4bde3-120">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="4bde3-120">Click OK.</span></span>
11. <span data-ttu-id="4bde3-121">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="4bde3-121">Click Import.</span></span>
12. <span data-ttu-id="4bde3-122">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="4bde3-122">Click Yes.</span></span>
13. <span data-ttu-id="4bde3-123">En el panel de acciones, haga clic en Opciones.</span><span class="sxs-lookup"><span data-stu-id="4bde3-123">On the Action Pane, click Options.</span></span>
14. <span data-ttu-id="4bde3-124">Haga clic en Ordenación o filtro avanzado.</span><span class="sxs-lookup"><span data-stu-id="4bde3-124">Click Advanced Filter/Sort.</span></span>
15. <span data-ttu-id="4bde3-125">Haga clic en Restablecer.</span><span class="sxs-lookup"><span data-stu-id="4bde3-125">Click Reset.</span></span>
16. <span data-ttu-id="4bde3-126">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="4bde3-126">Click Add.</span></span>
17. <span data-ttu-id="4bde3-127">En el campo Campo, seleccione "Nombre de configuración".</span><span class="sxs-lookup"><span data-stu-id="4bde3-127">In the Field field, select 'Configuration name'.</span></span>
18. <span data-ttu-id="4bde3-128">En el campo Criterios, escriba "Lista de ventas de la UE por informe de filas".</span><span class="sxs-lookup"><span data-stu-id="4bde3-128">In the Criteria field, type 'EU Sales list by rows report'.</span></span>
19. <span data-ttu-id="4bde3-129">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="4bde3-129">Click OK.</span></span>
20. <span data-ttu-id="4bde3-130">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="4bde3-130">Click Import.</span></span>
21. <span data-ttu-id="4bde3-131">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="4bde3-131">Click Yes.</span></span>

## <a name="set-up-sales-tax-codes-for-eu-sales-list-reporting"></a><span data-ttu-id="4bde3-132">Configurar códigos de impuestos para informes de listas de ventas de la UE</span><span class="sxs-lookup"><span data-stu-id="4bde3-132">Set up sales tax codes for EU sales list reporting</span></span>
1. <span data-ttu-id="4bde3-133">Vaya a Impuestos > Impuestos indirectos > Impuestos > Códigos de impuestos.</span><span class="sxs-lookup"><span data-stu-id="4bde3-133">Go to Tax > Indirect taxes > Sales tax > Sales tax codes.</span></span>
2. <span data-ttu-id="4bde3-134">Use un filtro rápido para filtrar el campo Código de impuestos con un valor de "VAT19".</span><span class="sxs-lookup"><span data-stu-id="4bde3-134">Use the Quick Filter to filter on the Sales tax code field with a value of 'VAT19'.</span></span>
3. <span data-ttu-id="4bde3-135">Expanda la sección Configuración del informe.</span><span class="sxs-lookup"><span data-stu-id="4bde3-135">Expand the Report setup section.</span></span>
    * <span data-ttu-id="4bde3-136">Compruebe que la selección excluida se establece en No.</span><span class="sxs-lookup"><span data-stu-id="4bde3-136">Verify that the Excluded selection is set to No.</span></span>  
    * <span data-ttu-id="4bde3-137">Es posible que tenga que desbloquear la guía de tareas para cambiar esta configuración.</span><span class="sxs-lookup"><span data-stu-id="4bde3-137">You may need to unlock the task guide to change this setting.</span></span>  

## <a name="set-up-sales-tax-groups-for-eu-sales-list-reporting"></a><span data-ttu-id="4bde3-138">Configurar grupos de impuestos para informes de listas de ventas de la UE</span><span class="sxs-lookup"><span data-stu-id="4bde3-138">Set up sales tax groups for EU sales list reporting</span></span>
1. <span data-ttu-id="4bde3-139">Vaya a Impuestos > Impuestos indirectos > Impuestos > Grupos de impuestos.</span><span class="sxs-lookup"><span data-stu-id="4bde3-139">Go to Tax > Indirect taxes > Sales tax > Sales tax groups.</span></span>
2. <span data-ttu-id="4bde3-140">Use un filtro rápido para filtrar el campo Grupo de impuestos sobre las ventas con un valor de "AR-DOM".</span><span class="sxs-lookup"><span data-stu-id="4bde3-140">Use the Quick Filter to filter on the Sales tax group field with a value of 'AR-DOM'.</span></span>
3. <span data-ttu-id="4bde3-141">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="4bde3-141">Click Edit.</span></span>
4. <span data-ttu-id="4bde3-142">Expanda la sección Configuración.</span><span class="sxs-lookup"><span data-stu-id="4bde3-142">Expand the Setup section.</span></span>
5. <span data-ttu-id="4bde3-143">En la lista, seleccione la primera fila.</span><span class="sxs-lookup"><span data-stu-id="4bde3-143">In the list, select the first row.</span></span>
6. <span data-ttu-id="4bde3-144">Active la casilla Exento.</span><span class="sxs-lookup"><span data-stu-id="4bde3-144">Select the Exempt check box.</span></span>
7. <span data-ttu-id="4bde3-145">En la lista, seleccione la segunda fila.</span><span class="sxs-lookup"><span data-stu-id="4bde3-145">In the list, select the second row.</span></span>
8. <span data-ttu-id="4bde3-146">Active la casilla Exento.</span><span class="sxs-lookup"><span data-stu-id="4bde3-146">Select the Exempt check box.</span></span>
9. <span data-ttu-id="4bde3-147">En la lista, seleccione la tercera fila.</span><span class="sxs-lookup"><span data-stu-id="4bde3-147">In the list, select the third row.</span></span>
10. <span data-ttu-id="4bde3-148">Active la casilla Exento.</span><span class="sxs-lookup"><span data-stu-id="4bde3-148">Select the Exempt check box.</span></span>

## <a name="set-up-item-sales-tax-groups-for-eu-sales-list-reporting"></a><span data-ttu-id="4bde3-149">Configurar grupos de impuestos de artículos para informes de listas de ventas de la UE</span><span class="sxs-lookup"><span data-stu-id="4bde3-149">Set up item sales tax groups for EU sales list reporting</span></span>
1. <span data-ttu-id="4bde3-150">Vaya a Impuestos > Impuestos indirectos > Impuestos > Grupos de impuestos de artículos.</span><span class="sxs-lookup"><span data-stu-id="4bde3-150">Go to Tax > Indirect taxes > Sales tax > Item sales tax groups.</span></span>
2. <span data-ttu-id="4bde3-151">Use un filtro rápido para filtrar por el campo Grupo de impuestos de artículos con un valor de "FULL".</span><span class="sxs-lookup"><span data-stu-id="4bde3-151">Use the Quick Filter to filter on the Item sales tax group field with a value of 'FULL '.</span></span>
    * <span data-ttu-id="4bde3-152">Compruebe que la selección Tipo de notificación se establece en "Artículo".</span><span class="sxs-lookup"><span data-stu-id="4bde3-152">Verify that the Reporting type selection is set to 'Item'.</span></span>  
    * <span data-ttu-id="4bde3-153">Es posible que tenga que desbloquear la guía de tareas para cambiar el valor en este campo.</span><span class="sxs-lookup"><span data-stu-id="4bde3-153">You may need to unlock the task guide to change the value in this field.</span></span>  
3. <span data-ttu-id="4bde3-154">Use un filtro rápido para filtrar por el campo Grupo de impuestos de artículos con un valor de "RED".</span><span class="sxs-lookup"><span data-stu-id="4bde3-154">Use the Quick Filter to filter on the Item sales tax group field with a value of 'RED '.</span></span>
    * <span data-ttu-id="4bde3-155">Compruebe que la selección Tipo de notificación se establece en "Servicio".</span><span class="sxs-lookup"><span data-stu-id="4bde3-155">Verify that the Reporting type selection is set to 'Service'.</span></span>  
    * <span data-ttu-id="4bde3-156">Es posible que tenga que desbloquear la guía de tareas para cambiar el valor en este campo.</span><span class="sxs-lookup"><span data-stu-id="4bde3-156">You may need to unlock the task guide to change the value in this field.</span></span>  

## <a name="set-up-countryregion-parameters-for-eu-sales-list-reporting"></a><span data-ttu-id="4bde3-157">Configurar parámetros de país o región para informes de listas de ventas de la UE</span><span class="sxs-lookup"><span data-stu-id="4bde3-157">Set up country/region parameters for EU sales list reporting</span></span>
1. <span data-ttu-id="4bde3-158">Vaya a Impuestos > Configuración > Impuestos > Parámetros por país o región.</span><span class="sxs-lookup"><span data-stu-id="4bde3-158">Go to Tax > Setup > Sales tax > Country/region parameters.</span></span>
2. <span data-ttu-id="4bde3-159">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="4bde3-159">Click New.</span></span>
3. <span data-ttu-id="4bde3-160">En el campo País/región, escriba "PRT".</span><span class="sxs-lookup"><span data-stu-id="4bde3-160">In the Country/region field, type 'PRT'.</span></span>
4. <span data-ttu-id="4bde3-161">En el campo Impuestos, escriba "PT".</span><span class="sxs-lookup"><span data-stu-id="4bde3-161">In the Sales tax field, type 'PT'.</span></span>

## <a name="create-tax-exempt-numbers"></a><span data-ttu-id="4bde3-162">Crear números de exención fiscal</span><span class="sxs-lookup"><span data-stu-id="4bde3-162">Create tax exempt numbers</span></span>
1. <span data-ttu-id="4bde3-163">Vaya a Impuestos > Configuración > Impuestos > Números de identificación fiscal.</span><span class="sxs-lookup"><span data-stu-id="4bde3-163">Go to Tax > Setup > Sales tax > Tax exempt numbers.</span></span>
2. <span data-ttu-id="4bde3-164">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="4bde3-164">Click New.</span></span>
3. <span data-ttu-id="4bde3-165">En el campo País/región, escriba "PRT".</span><span class="sxs-lookup"><span data-stu-id="4bde3-165">In the Country/region field, type 'PRT'.</span></span>
4. <span data-ttu-id="4bde3-166">En el campo NIF, escriba "PT12345".</span><span class="sxs-lookup"><span data-stu-id="4bde3-166">In the Tax exempt number field, type 'PT12345'.</span></span>

## <a name="set-up-eu-sales-list-reporting-parameters"></a><span data-ttu-id="4bde3-167">Configurar parámetros de informes de listas de ventas de la UE</span><span class="sxs-lookup"><span data-stu-id="4bde3-167">Set up EU sales list reporting parameters</span></span>
1. <span data-ttu-id="4bde3-168">Vaya a Impuestos > Configuración > Comercio exterior > Parámetros de comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="4bde3-168">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
2. <span data-ttu-id="4bde3-169">Haga clic en la ficha Lista de ventas de la UE.</span><span class="sxs-lookup"><span data-stu-id="4bde3-169">Click the EU sales list tab.</span></span>
3. <span data-ttu-id="4bde3-170">Seleccione Sí en el campo Transferir compras.</span><span class="sxs-lookup"><span data-stu-id="4bde3-170">Select Yes in the Transfer purchases field.</span></span>
4. <span data-ttu-id="4bde3-171">Expanda la sección Reglas de redondeo.</span><span class="sxs-lookup"><span data-stu-id="4bde3-171">Expand the Rounding rules section.</span></span>
5. <span data-ttu-id="4bde3-172">Establezca la regla de redondeo en "0,1".</span><span class="sxs-lookup"><span data-stu-id="4bde3-172">Set Rounding rule to '0.1'.</span></span>
6. <span data-ttu-id="4bde3-173">Seleccione Sí en el campo Usar valor mínimo.</span><span class="sxs-lookup"><span data-stu-id="4bde3-173">Select Yes in the Use minimum value field.</span></span>
7. <span data-ttu-id="4bde3-174">En el campo Número de decimales, escriba "2".</span><span class="sxs-lookup"><span data-stu-id="4bde3-174">In the Number of decimals field, enter '2'.</span></span>
8. <span data-ttu-id="4bde3-175">Expanda la sección Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="4bde3-175">Expand the Electronic reporting section.</span></span>
9. <span data-ttu-id="4bde3-176">En el campo Asignación de formato de archivo, seleccione "Lista de ventas de la UE (DE)".</span><span class="sxs-lookup"><span data-stu-id="4bde3-176">In the File format mapping field, select 'EU Sales list (DE)'.</span></span>
10. <span data-ttu-id="4bde3-177">En el campo Asignación de formato de informe, seleccione "Lista de ventas de la UE por informe de filas".</span><span class="sxs-lookup"><span data-stu-id="4bde3-177">In the Report format mapping field, select 'EU Sales list by rows report'.</span></span>
11. <span data-ttu-id="4bde3-178">Haga clic en la ficha Propiedades de país/región.</span><span class="sxs-lookup"><span data-stu-id="4bde3-178">Click the Country/region properties tab.</span></span>
    * <span data-ttu-id="4bde3-179">Compruebe que el campo Tipo de país/región está establecido en "Nacional" para País o región DEU.</span><span class="sxs-lookup"><span data-stu-id="4bde3-179">Verify that the Country/region type field is set to 'Domestic' for Country/region DEU.</span></span>  
    * <span data-ttu-id="4bde3-180">Es posible que tenga que desbloquear la guía de tareas para cambiar el valor en este campo.</span><span class="sxs-lookup"><span data-stu-id="4bde3-180">You may need to unlock the task guide to change the value in this field.</span></span>  
12. <span data-ttu-id="4bde3-181">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="4bde3-181">Click New.</span></span>
13. <span data-ttu-id="4bde3-182">En el campo País/región, escriba "PRT".</span><span class="sxs-lookup"><span data-stu-id="4bde3-182">In the Country/region field, type 'PRT'.</span></span>
14. <span data-ttu-id="4bde3-183">En el campo Código intrastat, escriba "PT".</span><span class="sxs-lookup"><span data-stu-id="4bde3-183">In the Intrastat code field, type 'PT'.</span></span>
15. <span data-ttu-id="4bde3-184">En el campo Tipo de país/región, seleccione "UE".</span><span class="sxs-lookup"><span data-stu-id="4bde3-184">In the Country/region type field, select 'EU'.</span></span>
16. <span data-ttu-id="4bde3-185">Haga clic en la ficha Secuencias numéricas.</span><span class="sxs-lookup"><span data-stu-id="4bde3-185">Click the Number sequences tab.</span></span>
    * <span data-ttu-id="4bde3-186">Compruebe que hay un Código de secuencia numérica especificado para la referencia "Lista de ventas de la UE".</span><span class="sxs-lookup"><span data-stu-id="4bde3-186">Verify that a Number sequence code is specified for the Reference 'EU sales list'.</span></span>  

## <a name="create-a-customer-for-eu-sales-list-reporting-demo-purposes"></a><span data-ttu-id="4bde3-187">Crear un cliente para fines de demostración de informes de lista de ventas de la UE</span><span class="sxs-lookup"><span data-stu-id="4bde3-187">Create a customer for EU sales list reporting demo purposes</span></span>
1. <span data-ttu-id="4bde3-188">Vaya a Clientes > Clientes > Todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="4bde3-188">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="4bde3-189">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="4bde3-189">Click New.</span></span>
3. <span data-ttu-id="4bde3-190">En el campo Cuenta de cliente, escriba "PRT-001".</span><span class="sxs-lookup"><span data-stu-id="4bde3-190">In the Customer account field, type 'PRT-001'.</span></span>
4. <span data-ttu-id="4bde3-191">En el campo Nombre, escriba "Un cliente de Portugal".</span><span class="sxs-lookup"><span data-stu-id="4bde3-191">In the Name field, type 'A customer from Portugal'.</span></span>
5. <span data-ttu-id="4bde3-192">En el campo Grupo de clientes seleccione "10".</span><span class="sxs-lookup"><span data-stu-id="4bde3-192">In the Customer group field, select '10'.</span></span>
6. <span data-ttu-id="4bde3-193">En el campo Grupo de impuestos, seleccione "AR-DOM".</span><span class="sxs-lookup"><span data-stu-id="4bde3-193">In the Sales tax group field, select 'AR-DOM'.</span></span>
7. <span data-ttu-id="4bde3-194">En el campo NIF, seleccione "PT12345".</span><span class="sxs-lookup"><span data-stu-id="4bde3-194">In the Tax exempt number field, select 'PT12345'.</span></span>
8. <span data-ttu-id="4bde3-195">En el campo País/región, escriba "PRT".</span><span class="sxs-lookup"><span data-stu-id="4bde3-195">In the Country/region field, type 'PRT'.</span></span>
9. <span data-ttu-id="4bde3-196">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="4bde3-196">Click Save.</span></span>

