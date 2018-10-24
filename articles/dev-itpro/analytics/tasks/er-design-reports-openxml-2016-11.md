--- 
title: "ER Diseña una configuración para generar informes en formato OPENXML (noviembre de 2016)"
description: "En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o desarrollador de informes electrónicos puede crear una nueva configuración de informes electrónicos que contenga una plantilla para generar documentos electrónicos en formato OPENXML."
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERDataSourceAddDropDialog, ERModelGroupByFunctionEditor, VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 3e6b6b16f202af051ccff02051eb438ea49ff6da
ms.contentlocale: es-es
ms.lasthandoff: 09/14/2018

---
# <a name="er-design-a-configuration-for-generating-reports-in-openxml-format-november-2016"></a><span data-ttu-id="3b9f2-103">ER Diseña una configuración para generar informes en formato OPENXML (noviembre de 2016)</span><span class="sxs-lookup"><span data-stu-id="3b9f2-103">ER Design a configuration for generating reports in OPENXML format (November 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3b9f2-104">En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o desarrollador de informes electrónicos puede crear una nueva configuración de informes electrónicos que contenga una plantilla para generar documentos electrónicos en formato OPENXML.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a template for generating electronic documents in OPENXML format.</span></span> <span data-ttu-id="3b9f2-105">Esta configuración se usará para procesar los pagos de proveedor.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-105">This configuration will be used for processing vendor payments.</span></span>



<span data-ttu-id="3b9f2-106">En este ejemplo, creará una configuración para la empresa de demostración, Litware, Inc. Estos pasos se pueden realizar en empresa GBSI.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in GBSI company.</span></span>



<span data-ttu-id="3b9f2-107">Para completar estos pasos, primero debe completar los pasos del procedimiento Creación y activación de un proveedor de configuraciones.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="3b9f2-108">También debe tener un archivo Excel que se importará el crear la plantilla.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-108">You must also have an Excel file which will be imported when creating the template.</span></span> <span data-ttu-id="3b9f2-109">A este archivo se obtiene acceso desde la [Plantilla de informe de pago](https://go.microsoft.com/fwlink/?linkid=862266).</span><span class="sxs-lookup"><span data-stu-id="3b9f2-109">This file can be accessed from the [Template of Payment Report](https://go.microsoft.com/fwlink/?linkid=862266).</span></span>


## <a name="upload-the-payments-data-model-configuration"></a><span data-ttu-id="3b9f2-110">Cargar la configuración del modelo de datos de pagos</span><span class="sxs-lookup"><span data-stu-id="3b9f2-110">Upload the Payments data model configuration</span></span>
1. <span data-ttu-id="3b9f2-111">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-111">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="3b9f2-112">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-112">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="3b9f2-113">Seleccione el proveedor de la configuración de la empresa de ejemplo, Litware, Inc. Si no ve a este proveedor de configuración, primero debe completar los pasos del procedimiento "Creación y activación de un proveedor de configuraciones".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-113">Select the configuration provider for sample company, Litware, Inc. If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
3. <span data-ttu-id="3b9f2-114">Haga clic en Definir como activo.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-114">Click Set active.</span></span>
4. <span data-ttu-id="3b9f2-115">Haga clic en Repositorios.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-115">Click Repositories.</span></span>
    * <span data-ttu-id="3b9f2-116">Seleccione un repositorio para el tipo de recursos de operaciones, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-116">Select a repository for the Operations Resources type, if available.</span></span> <span data-ttu-id="3b9f2-117">Si está disponible, omita los siguientes pasos acerca de la creación de un nuevo repositorio.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-117">If its available, skip the following steps about creating a new repository.</span></span>  
5. <span data-ttu-id="3b9f2-118">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-118">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="3b9f2-119">En el campo Tipo de repositorio de configuración, escriba "Recursos de Operations".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-119">In the Configuration repository type field, enter 'Operations resources'.</span></span>
7. <span data-ttu-id="3b9f2-120">Haga clic en Crear repositorio.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-120">Click Create repository.</span></span>
8. <span data-ttu-id="3b9f2-121">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3b9f2-121">Click OK.</span></span>
9. <span data-ttu-id="3b9f2-122">Haga clic en Abrir.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-122">Click Open.</span></span>
10. <span data-ttu-id="3b9f2-123">En el árbol, seleccione "Modelo de pago".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-123">In the tree, select 'Payment model'.</span></span>
11. <span data-ttu-id="3b9f2-124">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-124">Click Import.</span></span>
    * <span data-ttu-id="3b9f2-125">Importe este modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-125">Import this data model.</span></span> <span data-ttu-id="3b9f2-126">Se usará como origen de datos en una nueva configuración de formato.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-126">It will be used as a data source in a new format configuration.</span></span> <span data-ttu-id="3b9f2-127">Omita este paso si esta configuración ya se ha importado.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-127">Skip this step if this configuration has been already imported.</span></span>  
12. <span data-ttu-id="3b9f2-128">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-128">Click Yes.</span></span>
13. <span data-ttu-id="3b9f2-129">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-129">Close the page.</span></span>
14. <span data-ttu-id="3b9f2-130">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-130">Close the page.</span></span>

## <a name="create-a-new-format-configuration"></a><span data-ttu-id="3b9f2-131">Creación de una configuración de formato nueva</span><span class="sxs-lookup"><span data-stu-id="3b9f2-131">Create a new format configuration</span></span>
1. <span data-ttu-id="3b9f2-132">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-132">Click Reporting configurations.</span></span>
2. <span data-ttu-id="3b9f2-133">En el árbol, seleccione "Modelo de pago".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-133">In the tree, select 'Payment model'.</span></span>
3. <span data-ttu-id="3b9f2-134">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-134">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="3b9f2-135">En el campo Nuevo, especifique "Formato basado en modelo de datos PaymentModel".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-135">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
    * <span data-ttu-id="3b9f2-136">Cree un formato que se base en el modelo de datos de PaymentModel.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-136">Create a format that is based on the PaymentModel data model.</span></span>  
5. <span data-ttu-id="3b9f2-137">En el campo Nombre, escriba "Informe de hoja de cálculo de muestra".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-137">In the Name field, type 'Sample worksheet report'.</span></span>
    * <span data-ttu-id="3b9f2-138">Informe de hoja de cálculo de muestra</span><span class="sxs-lookup"><span data-stu-id="3b9f2-138">Sample worksheet report</span></span>  
6. <span data-ttu-id="3b9f2-139">En el campo Descripción, escriba "Informe de hoja de cálculo para pagos de proveedores".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-139">In the Description field, type 'Sample worksheet report for vendors’ payments'.</span></span>
    * <span data-ttu-id="3b9f2-140">Informe de hoja de cálculo para pagos de proveedores.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-140">Sample worksheet report for vendors’ payments.</span></span>  
7. <span data-ttu-id="3b9f2-141">En el campo definición del modelo de Datos, introduzca o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-141">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="3b9f2-142">Seleccione la definición "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-142">Select the 'CustomerCreditTransferInitiation' definition.</span></span>  
8. <span data-ttu-id="3b9f2-143">Haga clic en Crear configuración.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-143">Click Create configuration.</span></span>

## <a name="design-a-new-document-in-openxml-worksheet-format"></a><span data-ttu-id="3b9f2-144">Diseñar un documento nuevo en formato de hoja de cálculo OPENXML</span><span class="sxs-lookup"><span data-stu-id="3b9f2-144">Design a new document in OPENXML worksheet format</span></span>
1. <span data-ttu-id="3b9f2-145">En el árbol, seleccione "Modelo de pago\Informe de hoja de cálculo de muestra".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-145">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
2. <span data-ttu-id="3b9f2-146">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-146">Click Designer.</span></span>
3. <span data-ttu-id="3b9f2-147">En el panel de acciones, haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-147">On the Action Pane, click Import.</span></span>
4. <span data-ttu-id="3b9f2-148">Haga clic en Importar desde Excel.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-148">Click Import from Excel.</span></span>
5. <span data-ttu-id="3b9f2-149">Haga clic en Archivos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-149">Click Attachments.</span></span>
    * <span data-ttu-id="3b9f2-150">Adjunte el documento de Excel existente como plantilla.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-150">Attach the existing Excel document as a template.</span></span>  
6. <span data-ttu-id="3b9f2-151">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-151">Click New.</span></span>
7. <span data-ttu-id="3b9f2-152">Haga clic en Archivo.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-152">Click File.</span></span>
    * <span data-ttu-id="3b9f2-153">Señale al archivo de Excel existente.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-153">Point to the existing Excel file.</span></span>  
8. <span data-ttu-id="3b9f2-154">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-154">Close the page.</span></span>
9. <span data-ttu-id="3b9f2-155">En el campo Plantilla, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-155">In the Template field, enter or select a value.</span></span>
    * <span data-ttu-id="3b9f2-156">Seleccione el archivo de Excel adjunto que se usará como plantilla.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-156">Select the attached Excel file to be used as a template.</span></span>  
10. <span data-ttu-id="3b9f2-157">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3b9f2-157">Click OK.</span></span>
    * <span data-ttu-id="3b9f2-158">Tenga en cuenta que los componentes en formato ER se han creado en el formato de diseño basado en la estructura del documento de MS Excel de referencia (intervalos con nombre).</span><span class="sxs-lookup"><span data-stu-id="3b9f2-158">Note that ER format components have been created in the designing format based on the structure of the referring MS Excel document (named ranges).</span></span>  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a><span data-ttu-id="3b9f2-159">Crear un nuevo origen de datos para calcular totales por códigos de divisa</span><span class="sxs-lookup"><span data-stu-id="3b9f2-159">Create a new data source to calculate totals by currency codes</span></span>
1. <span data-ttu-id="3b9f2-160">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-160">Click the Mapping tab.</span></span>
2. <span data-ttu-id="3b9f2-161">Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-161">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="3b9f2-162">En el árbol, seleccione "Funciones\Agrupar por".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-162">In the tree, select 'Functions\Group by'.</span></span>
4. <span data-ttu-id="3b9f2-163">En el campo Nombre, escriba "PaymentByCurrency".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-163">In the Name field, type 'PaymentByCurrency'.</span></span>
    * <span data-ttu-id="3b9f2-164">PaymentByCurrency</span><span class="sxs-lookup"><span data-stu-id="3b9f2-164">PaymentByCurrency</span></span>  
5. <span data-ttu-id="3b9f2-165">Haga clic en Editar grupo por.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-165">Click Edit group by.</span></span>
6. <span data-ttu-id="3b9f2-166">En el árbol , expanda "modelo".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-166">In the tree, expand 'model'.</span></span>
7. <span data-ttu-id="3b9f2-167">En el árbol, seleccione modelo\Pagos.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-167">In the tree, select 'model\Payments'.</span></span>
8. <span data-ttu-id="3b9f2-168">Haga clic en Agregar campo a.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-168">Click Add field to.</span></span>
9. <span data-ttu-id="3b9f2-169">Haga clic en Elementos para agrupar.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-169">Click What to group.</span></span>
10. <span data-ttu-id="3b9f2-170">En el árbol, expanda modelo\Pagos.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-170">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="3b9f2-171">En el árbol, seleccione "modelo\Pagos\Divisa".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-171">In the tree, select 'model\Payments\Currency'.</span></span>
12. <span data-ttu-id="3b9f2-172">Haga clic en Agregar campo a.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-172">Click Add field to.</span></span>
13. <span data-ttu-id="3b9f2-173">Haga clic en Campos agrupados.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-173">Click Grouped fields.</span></span>
14. <span data-ttu-id="3b9f2-174">En el árbol, seleccione "modelo\Pagos\Importe ordenado(InstructedAmount)".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-174">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
15. <span data-ttu-id="3b9f2-175">Haga clic en Agregar campo a.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-175">Click Add field to.</span></span>
16. <span data-ttu-id="3b9f2-176">Haga clic en Campos de agregación.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-176">Click Aggregation fields.</span></span>
17. <span data-ttu-id="3b9f2-177">En el campo Método, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-177">In the Method field, select an option.</span></span>
    * <span data-ttu-id="3b9f2-178">Seleccione la función de agregación SUMA.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-178">Select the SUM aggregation function.</span></span>  
18. <span data-ttu-id="3b9f2-179">En el campo Nombre, escriba "TotalInstructuredAmount".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-179">In the Name field, type 'TotalInstructuredAmount'.</span></span>
    * <span data-ttu-id="3b9f2-180">TotalInstructuredAmount</span><span class="sxs-lookup"><span data-stu-id="3b9f2-180">TotalInstructuredAmount</span></span>  
19. <span data-ttu-id="3b9f2-181">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-181">Click Save.</span></span>
20. <span data-ttu-id="3b9f2-182">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-182">Close the page.</span></span>
21. <span data-ttu-id="3b9f2-183">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3b9f2-183">Click OK.</span></span>

## <a name="map-format-components-to-data-sources"></a><span data-ttu-id="3b9f2-184">Asignar componentes de formato a orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="3b9f2-184">Map format components to data sources</span></span>
1. <span data-ttu-id="3b9f2-185">En el árbol , expanda "modelo".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-185">In the tree, expand 'model'.</span></span>
2. <span data-ttu-id="3b9f2-186">En el árbol, expanda modelo\Pagos.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-186">In the tree, expand 'model\Payments'.</span></span>
3. <span data-ttu-id="3b9f2-187">En el árbol, expanda "modelo\Pagos\Parte iniciadora(InitiatingParty)".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-187">In the tree, expand 'model\Payments\Initiating Party(InitiatingParty)'.</span></span>
4. <span data-ttu-id="3b9f2-188">En el árbol, seleccione "modelo\Pagos\Parte iniciadora(InitiatingParty)\Name".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-188">In the tree, select 'model\Payments\Initiating Party(InitiatingParty)\Name'.</span></span>
5. <span data-ttu-id="3b9f2-189">En el árbol, expanda 'Excel\ReportHeader'.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-189">In the tree, expand 'Excel\ReportHeader'.</span></span>
6. <span data-ttu-id="3b9f2-190">En el árbol, seleccione ''Excel\ReportHeader\CompanyName".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-190">In the tree, select 'Excel\ReportHeader\CompanyName'.</span></span>
7. <span data-ttu-id="3b9f2-191">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-191">Click Bind.</span></span>
8. <span data-ttu-id="3b9f2-192">En el árbol, expanda modelo\Pagos\Acreedor.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-192">In the tree, expand 'model\Payments\Creditor'.</span></span>
9. <span data-ttu-id="3b9f2-193">En el árbol, expanda "modelo\Pagos\Acreedor\Identificación".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-193">In the tree, expand 'model\Payments\Creditor\Identification'.</span></span>
10. <span data-ttu-id="3b9f2-194">En el árbol, seleccione "modelo\Pagos\Cuenta de acreedor(Creditor)\Identification\Source ID(SourceID)".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-194">In the tree, select 'model\Payments\Creditor\Identification\Source ID(SourceID)'.</span></span>
11. <span data-ttu-id="3b9f2-195">En el árbol, expanda 'Excel\PaymLines'.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-195">In the tree, expand 'Excel\PaymLines'.</span></span>
12. <span data-ttu-id="3b9f2-196">En el árbol, seleccione ''Excel\PaymLines\VendAccountName".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-196">In the tree, select 'Excel\PaymLines\VendAccountName'.</span></span>
13. <span data-ttu-id="3b9f2-197">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-197">Click Bind.</span></span>
14. <span data-ttu-id="3b9f2-198">En el árbol, seleccione modelo\Pagos\Acreedor\Nombre.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-198">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
15. <span data-ttu-id="3b9f2-199">En el árbol, seleccione ''Excel\PaymLines\VendName".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-199">In the tree, select 'Excel\PaymLines\VendName'.</span></span>
16. <span data-ttu-id="3b9f2-200">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-200">Click Bind.</span></span>
17. <span data-ttu-id="3b9f2-201">En el árbol, expanda “modelo\Pagos\Cuenta de acreedor(CreditorAccount)”.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-201">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
18. <span data-ttu-id="3b9f2-202">En el árbol, expanda “modelo\Pagos\Cuenta de acreedor(CreditorAccount)\Nombre”.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-202">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Name'.</span></span>
19. <span data-ttu-id="3b9f2-203">En el árbol, seleccione ''Excel\PaymLines\Bank".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-203">In the tree, select 'Excel\PaymLines\Bank'.</span></span>
20. <span data-ttu-id="3b9f2-204">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-204">Click Bind.</span></span>
21. <span data-ttu-id="3b9f2-205">En el árbol, seleccione "modelo\Pagos\Agente del acreedor(CreditorAgent)\Número de ruta(RoutingNumber)".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-205">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Routing Number(RoutingNumber)'.</span></span>
22. <span data-ttu-id="3b9f2-206">En el árbol, seleccione ''Excel\PaymLines\RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-206">In the tree, select 'Excel\PaymLines\RoutingNumber'.</span></span>
23. <span data-ttu-id="3b9f2-207">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-207">Click Bind.</span></span>
24. <span data-ttu-id="3b9f2-208">En el árbol, expanda “model\Payments\Creditor Account(CreditorAccount)”.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-208">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
25. <span data-ttu-id="3b9f2-209">En el árbol, expanda “model\Payments\Creditor Account(CreditorAccount)\Identification”.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-209">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)\Identification'.</span></span>
26. <span data-ttu-id="3b9f2-210">En el árbol, seleccione "modelo\Pagos\Cuenta de acreedor(CreditorAccount)\Identification\Número”.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-210">In the tree, select 'model\Payments\Creditor Account(CreditorAccount)\Identification\Number'.</span></span>
27. <span data-ttu-id="3b9f2-211">En el árbol, seleccione ''Excel\PaymLines\AccountNumber".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-211">In the tree, select 'Excel\PaymLines\AccountNumber'.</span></span>
28. <span data-ttu-id="3b9f2-212">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-212">Click Bind.</span></span>
29. <span data-ttu-id="3b9f2-213">En el árbol, seleccione "modelo\Pagos\Importe ordenado(InstructedAmount)".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-213">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
30. <span data-ttu-id="3b9f2-214">En el árbol, seleccione ''Excel\PaymLines\Débito".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-214">In the tree, select 'Excel\PaymLines\Debit'.</span></span>
31. <span data-ttu-id="3b9f2-215">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-215">Click Bind.</span></span>
32. <span data-ttu-id="3b9f2-216">En el árbol, expanda modelo\Pagos\Acreedor.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-216">In the tree, expand 'model\Payments\Creditor'.</span></span>
33. <span data-ttu-id="3b9f2-217">En el árbol, expanda “model\Payments\Creditor Account(CreditorAccount)”.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-217">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
34. <span data-ttu-id="3b9f2-218">En el árbol, expanda “modelo\Pagos\Cuenta de acreedor(CreditorAccount)”.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-218">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
35. <span data-ttu-id="3b9f2-219">En el árbol, seleccione "modelo\Pagos\Divisa".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-219">In the tree, select 'model\Payments\Currency'.</span></span>
36. <span data-ttu-id="3b9f2-220">En el árbol, seleccione ''Excel\PaymLines\Moneda".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-220">In the tree, select 'Excel\PaymLines\Currency'.</span></span>
37. <span data-ttu-id="3b9f2-221">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-221">Click Bind.</span></span>
38. <span data-ttu-id="3b9f2-222">En el árbol, expanda "PaymentByCurrency".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-222">In the tree, expand 'PaymentByCurrency'.</span></span>
39. <span data-ttu-id="3b9f2-223">En el árbol, expanda "PaymentByCurrency\agrupado".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-223">In the tree, expand 'PaymentByCurrency\grouped'.</span></span>
40. <span data-ttu-id="3b9f2-224">En el árbol, seleccione "PaymentByCurrency\agrupado\Divisa".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-224">In the tree, select 'PaymentByCurrency\grouped\Currency'.</span></span>
41. <span data-ttu-id="3b9f2-225">En el árbol, expanda "Excel\SummaryLines".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-225">In the tree, expand 'Excel\SummaryLines'.</span></span>
42. <span data-ttu-id="3b9f2-226">En el árbol, seleccione ''Excel\SummaryLines\SummaryCurrency".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-226">In the tree, select 'Excel\SummaryLines\SummaryCurrency'.</span></span>
43. <span data-ttu-id="3b9f2-227">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-227">Click Bind.</span></span>
44. <span data-ttu-id="3b9f2-228">En el árbol, expanda "PaymentByCurrency\agregado".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-228">In the tree, expand 'PaymentByCurrency\aggregated'.</span></span>
45. <span data-ttu-id="3b9f2-229">En el árbol, seleccione "PaymentByCurrency\agregado\TotalInstructuredAmount".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-229">In the tree, select 'PaymentByCurrency\aggregated\TotalInstructuredAmount'.</span></span>
46. <span data-ttu-id="3b9f2-230">En el árbol, seleccione ''Excel\SummaryLines\SummaryAmount".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-230">In the tree, select 'Excel\SummaryLines\SummaryAmount'.</span></span>
47. <span data-ttu-id="3b9f2-231">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-231">Click Bind.</span></span>
48. <span data-ttu-id="3b9f2-232">En el árbol, seleccione "PaymentByCurrency".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-232">In the tree, select 'PaymentByCurrency'.</span></span>
49. <span data-ttu-id="3b9f2-233">En el árbol, seleccione "Excel\SummaryLines".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-233">In the tree, select 'Excel\SummaryLines'.</span></span>
50. <span data-ttu-id="3b9f2-234">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-234">Click Bind.</span></span>
51. <span data-ttu-id="3b9f2-235">En el árbol, seleccione modelo\Pagos.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-235">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="3b9f2-236">En el árbol, seleccione ''Excel\PaymLines".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-236">In the tree, select 'Excel\PaymLines'.</span></span>
53. <span data-ttu-id="3b9f2-237">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-237">Click Bind.</span></span>
54. <span data-ttu-id="3b9f2-238">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-238">Click Save.</span></span>
55. <span data-ttu-id="3b9f2-239">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-239">Close the page.</span></span>

## <a name="use-the-created-configuration-for-payments-processing"></a><span data-ttu-id="3b9f2-240">Usar la configuración creada para procesar los pagos</span><span class="sxs-lookup"><span data-stu-id="3b9f2-240">Use the created configuration for payments processing</span></span>
1. <span data-ttu-id="3b9f2-241">Haga clic en Cambiar estado.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-241">Click Change status.</span></span>
2. <span data-ttu-id="3b9f2-242">Haga clic en Completar.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-242">Click Complete.</span></span>
3. <span data-ttu-id="3b9f2-243">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3b9f2-243">Click OK.</span></span>
4. <span data-ttu-id="3b9f2-244">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-244">Close the page.</span></span>
5. <span data-ttu-id="3b9f2-245">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-245">Close the page.</span></span>
6. <span data-ttu-id="3b9f2-246">Vaya a Proveedores > Configuración de pagos > Formas de pago.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-246">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
7. <span data-ttu-id="3b9f2-247">Use el Filtro Rápido para filtrar el campo Método de pago con un valor de "Electronic".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-247">Use the Quick Filter to filter on the Method of payment field with a value of 'Electronic'.</span></span>
    * <span data-ttu-id="3b9f2-248">Electrónica</span><span class="sxs-lookup"><span data-stu-id="3b9f2-248">Electronic</span></span>  
8. <span data-ttu-id="3b9f2-249">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-249">Click Edit.</span></span>
9. <span data-ttu-id="3b9f2-250">Expanda la sección Formatos de archivo.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-250">Expand the File formats section.</span></span>
10. <span data-ttu-id="3b9f2-251">Seleccione Sí en el campo Informes electrónicos genéricos.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-251">Select Yes in the Generic electronic reporting field.</span></span>
11. <span data-ttu-id="3b9f2-252">En el campo Configuración de formato de exportación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-252">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="3b9f2-253">Seleccione la configuración "Informe de hoja de cálculo de muestra”.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-253">Select the ‘Sample worksheet report’ configuration.</span></span>  
12. <span data-ttu-id="3b9f2-254">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-254">Click Save.</span></span>
13. <span data-ttu-id="3b9f2-255">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-255">Close the page.</span></span>

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a><span data-ttu-id="3b9f2-256">Usar la configuración creada para probar el procesamiento de diarios de pago</span><span class="sxs-lookup"><span data-stu-id="3b9f2-256">Use the created configuration for testing of payment journals processing</span></span>
1. <span data-ttu-id="3b9f2-257">Vaya a Proveedores > Pagos > Diario de pagos.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-257">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="3b9f2-258">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-258">Click New.</span></span>
    * <span data-ttu-id="3b9f2-259">Crear un diario de pago nuevo.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-259">Create a new payment journal.</span></span>  
3. <span data-ttu-id="3b9f2-260">En el campo Nombre, escriba "VendPay".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-260">In the Name field, type 'VendPay'.</span></span>
    * <span data-ttu-id="3b9f2-261">VendPay</span><span class="sxs-lookup"><span data-stu-id="3b9f2-261">VendPay</span></span>  
4. <span data-ttu-id="3b9f2-262">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-262">Click Lines.</span></span>
5. <span data-ttu-id="3b9f2-263">En el campo Cuenta, especifique los valores "GB_SI_000001".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-263">In the Account field, specify the values 'GB_SI_000001'.</span></span>
    * <span data-ttu-id="3b9f2-264">GB_SI_000001</span><span class="sxs-lookup"><span data-stu-id="3b9f2-264">GB_SI_000001</span></span>  
6. <span data-ttu-id="3b9f2-265">Establezca Débito en "1000".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-265">Set Debit to '1000'.</span></span>
7. <span data-ttu-id="3b9f2-266">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-266">Click New.</span></span>
8. <span data-ttu-id="3b9f2-267">En el campo Cuenta, especifique los valores "GB_SI_000005".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-267">In the Account field, specify the values 'GB_SI_000005'.</span></span>
    * <span data-ttu-id="3b9f2-268">GB_SI_000005</span><span class="sxs-lookup"><span data-stu-id="3b9f2-268">GB_SI_000005</span></span>  
9. <span data-ttu-id="3b9f2-269">Establezca Débito en "2000".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-269">Set Debit to '2000'.</span></span>
10. <span data-ttu-id="3b9f2-270">En el campo Divisa, escriba "EUR".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-270">In the Currency field, type 'EUR'.</span></span>
    * <span data-ttu-id="3b9f2-271">EUR</span><span class="sxs-lookup"><span data-stu-id="3b9f2-271">EUR</span></span>  
11. <span data-ttu-id="3b9f2-272">En el campo Cuenta de contrapartida, especifique los valores "GBSI OPER".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-272">In the Offset account field, specify the values 'GBSI OPER'.</span></span>
    * <span data-ttu-id="3b9f2-273">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="3b9f2-273">GBSI OPER</span></span>  
12. <span data-ttu-id="3b9f2-274">En el campo Forma de pago, escriba un "Electrónica".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-274">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="3b9f2-275">Electrónica</span><span class="sxs-lookup"><span data-stu-id="3b9f2-275">Electronic</span></span>  
13. <span data-ttu-id="3b9f2-276">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-276">Click Save.</span></span>
14. <span data-ttu-id="3b9f2-277">Haga clic en Generar pagos.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-277">Click Generate payments.</span></span>
15. <span data-ttu-id="3b9f2-278">En el campo Forma de pago, escriba un "Electrónica".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-278">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="3b9f2-279">Electrónica</span><span class="sxs-lookup"><span data-stu-id="3b9f2-279">Electronic</span></span>  
16. <span data-ttu-id="3b9f2-280">En el campo Nombre, escriba "Pagos".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-280">In the File name field, type 'Payments'.</span></span>
    * <span data-ttu-id="3b9f2-281">Por ejemplo, escriba Pagos.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-281">For example, type Payments.</span></span>  
17. <span data-ttu-id="3b9f2-282">En el campo Cuenta bancaria, escriba "GBSI OPER".</span><span class="sxs-lookup"><span data-stu-id="3b9f2-282">In the Bank account field, type 'GBSI OPER'.</span></span>
    * <span data-ttu-id="3b9f2-283">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="3b9f2-283">GBSI OPER</span></span>  
18. <span data-ttu-id="3b9f2-284">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3b9f2-284">Click OK.</span></span>
19. <span data-ttu-id="3b9f2-285">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3b9f2-285">Click OK.</span></span>
    * <span data-ttu-id="3b9f2-286">Revise la hoja de trabajo creada, incluidos los detalles de líneas de pago así como los totales para cada código de divisa usado en este mensaje de pago.</span><span class="sxs-lookup"><span data-stu-id="3b9f2-286">Review the created worksheet, including details of payment lines as well as totals for each currency code used in this payment message.</span></span>  


