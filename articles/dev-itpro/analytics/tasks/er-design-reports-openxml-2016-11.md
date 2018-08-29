--- 
title: "Diseñar configuraciones de ER para generar informes en formato OpenXML"
description: "En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o desarrollador de informes electrónicos puede crear una nueva configuración de informes electrónicos que contenga una plantilla para generar documentos electrónicos en formato OPENXML."
author: NickSelin
manager: AnnBe
ms.date: 01/16/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: b42cfe36c57a9526e585bbad0fcd31ff60b90397
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---
# <a name="design-er-configurations-to-generate-reports-in-openxml-format"></a><span data-ttu-id="ed13b-103">Diseñar configuraciones de ER para generar informes en formato OpenXML</span><span class="sxs-lookup"><span data-stu-id="ed13b-103">Design ER configurations to generate reports in OpenXML format</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ed13b-104">En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o desarrollador de informes electrónicos puede crear una nueva configuración de informes electrónicos que contenga una plantilla para generar documentos electrónicos en formato OPENXML.</span><span class="sxs-lookup"><span data-stu-id="ed13b-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a template for generating electronic documents in OPENXML format.</span></span> <span data-ttu-id="ed13b-105">Esta configuración se usará para procesar los pagos de proveedor.</span><span class="sxs-lookup"><span data-stu-id="ed13b-105">This configuration will be used for processing vendor payments.</span></span>



<span data-ttu-id="ed13b-106">En este ejemplo, creará una configuración para la empresa de demostración, Litware, Inc. Estos pasos se pueden realizar en empresa GBSI.</span><span class="sxs-lookup"><span data-stu-id="ed13b-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in GBSI company.</span></span>



<span data-ttu-id="ed13b-107">Para completar estos pasos, primero debe completar los pasos del procedimiento Creación y activación de un proveedor de configuraciones.</span><span class="sxs-lookup"><span data-stu-id="ed13b-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="ed13b-108">También debe descargar y guardar el archivo de Microsoft Excel, [Plantilla de informe de pago](https://go.microsoft.com/fwlink/?linkid=862266).</span><span class="sxs-lookup"><span data-stu-id="ed13b-108">You must also download and save the Microsoft Excel file, [Template of Payment Report](https://go.microsoft.com/fwlink/?linkid=862266).</span></span> 

## <a name="upload-the-payments-data-model-configuration"></a><span data-ttu-id="ed13b-109">Cargar la configuración del modelo de datos de pagos</span><span class="sxs-lookup"><span data-stu-id="ed13b-109">Upload the Payments data model configuration</span></span>
1. <span data-ttu-id="ed13b-110">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="ed13b-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="ed13b-111">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ed13b-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="ed13b-112">Seleccione el proveedor de la configuración de la empresa de ejemplo, Litware, Inc. Si no ve a este proveedor de configuración, primero debe completar los pasos del procedimiento "Creación y activación de un proveedor de configuraciones".</span><span class="sxs-lookup"><span data-stu-id="ed13b-112">Select the configuration provider for sample company, Litware, Inc. If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
3. <span data-ttu-id="ed13b-113">Haga clic en Definir como activo.</span><span class="sxs-lookup"><span data-stu-id="ed13b-113">Click Set active.</span></span>
4. <span data-ttu-id="ed13b-114">Haga clic en Repositorios.</span><span class="sxs-lookup"><span data-stu-id="ed13b-114">Click Repositories.</span></span>
    * <span data-ttu-id="ed13b-115">Seleccione un repositorio para el tipo de recursos de operaciones, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="ed13b-115">Select a repository for the Operations Resources type, if available.</span></span> <span data-ttu-id="ed13b-116">Si está disponible, omita los siguientes pasos acerca de la creación de un nuevo repositorio.</span><span class="sxs-lookup"><span data-stu-id="ed13b-116">If its available, skip the following steps about creating a new repository.</span></span>  
5. <span data-ttu-id="ed13b-117">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="ed13b-117">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="ed13b-118">En el campo Tipo de repositorio de configuración, escriba "Recursos de Operations".</span><span class="sxs-lookup"><span data-stu-id="ed13b-118">In the Configuration repository type field, enter 'Operations resources'.</span></span>
7. <span data-ttu-id="ed13b-119">Haga clic en Crear repositorio.</span><span class="sxs-lookup"><span data-stu-id="ed13b-119">Click Create repository.</span></span>
8. <span data-ttu-id="ed13b-120">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ed13b-120">Click OK.</span></span>
9. <span data-ttu-id="ed13b-121">Haga clic en Abrir.</span><span class="sxs-lookup"><span data-stu-id="ed13b-121">Click Open.</span></span>
10. <span data-ttu-id="ed13b-122">En el árbol, seleccione "Modelo de pago".</span><span class="sxs-lookup"><span data-stu-id="ed13b-122">In the tree, select 'Payment model'.</span></span>
11. <span data-ttu-id="ed13b-123">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="ed13b-123">Click Import.</span></span>
    * <span data-ttu-id="ed13b-124">Importe este modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="ed13b-124">Import this data model.</span></span> <span data-ttu-id="ed13b-125">Se usará como origen de datos en una nueva configuración de formato.</span><span class="sxs-lookup"><span data-stu-id="ed13b-125">It will be used as a data source in a new format configuration.</span></span> <span data-ttu-id="ed13b-126">Omita este paso si esta configuración ya se ha importado.</span><span class="sxs-lookup"><span data-stu-id="ed13b-126">Skip this step if this configuration has been already imported.</span></span>  
12. <span data-ttu-id="ed13b-127">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="ed13b-127">Click Yes.</span></span>
13. <span data-ttu-id="ed13b-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ed13b-128">Close the page.</span></span>
14. <span data-ttu-id="ed13b-129">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ed13b-129">Close the page.</span></span>

## <a name="create-a-new-format-configuration"></a><span data-ttu-id="ed13b-130">Creación de una configuración de formato nueva</span><span class="sxs-lookup"><span data-stu-id="ed13b-130">Create a new format configuration</span></span>
1. <span data-ttu-id="ed13b-131">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="ed13b-131">Click Reporting configurations.</span></span>
2. <span data-ttu-id="ed13b-132">En el árbol, seleccione "Modelo de pago".</span><span class="sxs-lookup"><span data-stu-id="ed13b-132">In the tree, select 'Payment model'.</span></span>
3. <span data-ttu-id="ed13b-133">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="ed13b-133">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="ed13b-134">En el campo Nuevo, especifique "Formato basado en modelo de datos PaymentModel".</span><span class="sxs-lookup"><span data-stu-id="ed13b-134">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
    * <span data-ttu-id="ed13b-135">Cree un formato que se base en el modelo de datos de PaymentModel.</span><span class="sxs-lookup"><span data-stu-id="ed13b-135">Create a format that is based on the PaymentModel data model.</span></span>  
5. <span data-ttu-id="ed13b-136">En el campo Nombre, escriba "Informe de hoja de cálculo de muestra".</span><span class="sxs-lookup"><span data-stu-id="ed13b-136">In the Name field, type 'Sample worksheet report'.</span></span>
    * <span data-ttu-id="ed13b-137">Informe de hoja de cálculo de muestra</span><span class="sxs-lookup"><span data-stu-id="ed13b-137">Sample worksheet report</span></span>  
6. <span data-ttu-id="ed13b-138">En el campo Descripción, escriba "Informe de hoja de cálculo para pagos de proveedores".</span><span class="sxs-lookup"><span data-stu-id="ed13b-138">In the Description field, type 'Sample worksheet report for vendors’ payments'.</span></span>
    * <span data-ttu-id="ed13b-139">Informe de hoja de cálculo para pagos de proveedores.</span><span class="sxs-lookup"><span data-stu-id="ed13b-139">Sample worksheet report for vendors’ payments.</span></span>  
7. <span data-ttu-id="ed13b-140">En el campo definición del modelo de Datos, introduzca o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ed13b-140">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="ed13b-141">Seleccione la definición "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="ed13b-141">Select the 'CustomerCreditTransferInitiation' definition.</span></span>  
8. <span data-ttu-id="ed13b-142">Haga clic en Crear configuración.</span><span class="sxs-lookup"><span data-stu-id="ed13b-142">Click Create configuration.</span></span>

## <a name="design-a-new-document-in-openxml-worksheet-format"></a><span data-ttu-id="ed13b-143">Diseñar un documento nuevo en formato de hoja de cálculo OPENXML</span><span class="sxs-lookup"><span data-stu-id="ed13b-143">Design a new document in OPENXML worksheet format</span></span>
1. <span data-ttu-id="ed13b-144">En el árbol, seleccione "Modelo de pago\Informe de hoja de cálculo de muestra".</span><span class="sxs-lookup"><span data-stu-id="ed13b-144">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
2. <span data-ttu-id="ed13b-145">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="ed13b-145">Click Designer.</span></span>
3. <span data-ttu-id="ed13b-146">En el panel de acciones, haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="ed13b-146">On the Action Pane, click Import.</span></span>
4. <span data-ttu-id="ed13b-147">Haga clic en Importar desde Excel.</span><span class="sxs-lookup"><span data-stu-id="ed13b-147">Click Import from Excel.</span></span>
5. <span data-ttu-id="ed13b-148">Haga clic en Archivos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="ed13b-148">Click Attachments.</span></span>
    * <span data-ttu-id="ed13b-149">Adjunte el documento de Excel existente como plantilla.</span><span class="sxs-lookup"><span data-stu-id="ed13b-149">Attach the existing Excel document as a template.</span></span>  
6. <span data-ttu-id="ed13b-150">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ed13b-150">Click New.</span></span>
7. <span data-ttu-id="ed13b-151">Haga clic en Archivo.</span><span class="sxs-lookup"><span data-stu-id="ed13b-151">Click File.</span></span>
    * <span data-ttu-id="ed13b-152">Señale al archivo de Excel existente.</span><span class="sxs-lookup"><span data-stu-id="ed13b-152">Point to the existing Excel file.</span></span>  
8. <span data-ttu-id="ed13b-153">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ed13b-153">Close the page.</span></span>
9. <span data-ttu-id="ed13b-154">En el campo Plantilla, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ed13b-154">In the Template field, enter or select a value.</span></span>
    * <span data-ttu-id="ed13b-155">Seleccione el archivo de Excel adjunto que se usará como plantilla.</span><span class="sxs-lookup"><span data-stu-id="ed13b-155">Select the attached Excel file to be used as a template.</span></span>  
10. <span data-ttu-id="ed13b-156">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ed13b-156">Click OK.</span></span>
    * <span data-ttu-id="ed13b-157">Tenga en cuenta que los componentes en formato ER se han creado en el formato de diseño basado en la estructura del documento de MS Excel de referencia (intervalos con nombre).</span><span class="sxs-lookup"><span data-stu-id="ed13b-157">Note that ER format components have been created in the designing format based on the structure of the referring MS Excel document (named ranges).</span></span>  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a><span data-ttu-id="ed13b-158">Crear un nuevo origen de datos para calcular totales por códigos de divisa</span><span class="sxs-lookup"><span data-stu-id="ed13b-158">Create a new data source to calculate totals by currency codes</span></span>
1. <span data-ttu-id="ed13b-159">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="ed13b-159">Click the Mapping tab.</span></span>
2. <span data-ttu-id="ed13b-160">Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="ed13b-160">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="ed13b-161">En el árbol, seleccione "Funciones\Agrupar por".</span><span class="sxs-lookup"><span data-stu-id="ed13b-161">In the tree, select 'Functions\Group by'.</span></span>
4. <span data-ttu-id="ed13b-162">En el campo Nombre, escriba "PaymentByCurrency".</span><span class="sxs-lookup"><span data-stu-id="ed13b-162">In the Name field, type 'PaymentByCurrency'.</span></span>
    * <span data-ttu-id="ed13b-163">PaymentByCurrency</span><span class="sxs-lookup"><span data-stu-id="ed13b-163">PaymentByCurrency</span></span>  
5. <span data-ttu-id="ed13b-164">Haga clic en Editar grupo por.</span><span class="sxs-lookup"><span data-stu-id="ed13b-164">Click Edit group by.</span></span>
6. <span data-ttu-id="ed13b-165">En el árbol , expanda "modelo".</span><span class="sxs-lookup"><span data-stu-id="ed13b-165">In the tree, expand 'model'.</span></span>
7. <span data-ttu-id="ed13b-166">En el árbol, seleccione modelo\Pagos.</span><span class="sxs-lookup"><span data-stu-id="ed13b-166">In the tree, select 'model\Payments'.</span></span>
8. <span data-ttu-id="ed13b-167">Haga clic en Agregar campo a.</span><span class="sxs-lookup"><span data-stu-id="ed13b-167">Click Add field to.</span></span>
9. <span data-ttu-id="ed13b-168">Haga clic en Elementos para agrupar.</span><span class="sxs-lookup"><span data-stu-id="ed13b-168">Click What to group.</span></span>
10. <span data-ttu-id="ed13b-169">En el árbol, expanda modelo\Pagos.</span><span class="sxs-lookup"><span data-stu-id="ed13b-169">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="ed13b-170">En el árbol, seleccione "modelo\Pagos\Divisa".</span><span class="sxs-lookup"><span data-stu-id="ed13b-170">In the tree, select 'model\Payments\Currency'.</span></span>
12. <span data-ttu-id="ed13b-171">Haga clic en Agregar campo a.</span><span class="sxs-lookup"><span data-stu-id="ed13b-171">Click Add field to.</span></span>
13. <span data-ttu-id="ed13b-172">Haga clic en Campos agrupados.</span><span class="sxs-lookup"><span data-stu-id="ed13b-172">Click Grouped fields.</span></span>
14. <span data-ttu-id="ed13b-173">En el árbol, seleccione "modelo\Pagos\Importe ordenado(InstructedAmount)".</span><span class="sxs-lookup"><span data-stu-id="ed13b-173">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
15. <span data-ttu-id="ed13b-174">Haga clic en Agregar campo a.</span><span class="sxs-lookup"><span data-stu-id="ed13b-174">Click Add field to.</span></span>
16. <span data-ttu-id="ed13b-175">Haga clic en Campos de agregación.</span><span class="sxs-lookup"><span data-stu-id="ed13b-175">Click Aggregation fields.</span></span>
17. <span data-ttu-id="ed13b-176">En el campo Método, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="ed13b-176">In the Method field, select an option.</span></span>
    * <span data-ttu-id="ed13b-177">Seleccione la función de agregación SUMA.</span><span class="sxs-lookup"><span data-stu-id="ed13b-177">Select the SUM aggregation function.</span></span>  
18. <span data-ttu-id="ed13b-178">En el campo Nombre, escriba "TotalInstructuredAmount".</span><span class="sxs-lookup"><span data-stu-id="ed13b-178">In the Name field, type 'TotalInstructuredAmount'.</span></span>
    * <span data-ttu-id="ed13b-179">TotalInstructuredAmount</span><span class="sxs-lookup"><span data-stu-id="ed13b-179">TotalInstructuredAmount</span></span>  
19. <span data-ttu-id="ed13b-180">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ed13b-180">Click Save.</span></span>
20. <span data-ttu-id="ed13b-181">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ed13b-181">Close the page.</span></span>
21. <span data-ttu-id="ed13b-182">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ed13b-182">Click OK.</span></span>

## <a name="map-format-components-to-data-sources"></a><span data-ttu-id="ed13b-183">Asignar componentes de formato a orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="ed13b-183">Map format components to data sources</span></span>
1. <span data-ttu-id="ed13b-184">En el árbol , expanda "modelo".</span><span class="sxs-lookup"><span data-stu-id="ed13b-184">In the tree, expand 'model'.</span></span>
2. <span data-ttu-id="ed13b-185">En el árbol, expanda modelo\Pagos.</span><span class="sxs-lookup"><span data-stu-id="ed13b-185">In the tree, expand 'model\Payments'.</span></span>
3. <span data-ttu-id="ed13b-186">En el árbol, expanda "modelo\Pagos\Parte iniciadora(InitiatingParty)".</span><span class="sxs-lookup"><span data-stu-id="ed13b-186">In the tree, expand 'model\Payments\Initiating Party(InitiatingParty)'.</span></span>
4. <span data-ttu-id="ed13b-187">En el árbol, seleccione "modelo\Pagos\Parte iniciadora(InitiatingParty)\Name".</span><span class="sxs-lookup"><span data-stu-id="ed13b-187">In the tree, select 'model\Payments\Initiating Party(InitiatingParty)\Name'.</span></span>
5. <span data-ttu-id="ed13b-188">En el árbol, expanda 'Excel\ReportHeader'.</span><span class="sxs-lookup"><span data-stu-id="ed13b-188">In the tree, expand 'Excel\ReportHeader'.</span></span>
6. <span data-ttu-id="ed13b-189">En el árbol, seleccione ''Excel\ReportHeader\CompanyName".</span><span class="sxs-lookup"><span data-stu-id="ed13b-189">In the tree, select 'Excel\ReportHeader\CompanyName'.</span></span>
7. <span data-ttu-id="ed13b-190">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="ed13b-190">Click Bind.</span></span>
8. <span data-ttu-id="ed13b-191">En el árbol, expanda modelo\Pagos\Acreedor.</span><span class="sxs-lookup"><span data-stu-id="ed13b-191">In the tree, expand 'model\Payments\Creditor'.</span></span>
9. <span data-ttu-id="ed13b-192">En el árbol, expanda "modelo\Pagos\Acreedor\Identificación".</span><span class="sxs-lookup"><span data-stu-id="ed13b-192">In the tree, expand 'model\Payments\Creditor\Identification'.</span></span>
10. <span data-ttu-id="ed13b-193">En el árbol, seleccione "modelo\Pagos\Cuenta de acreedor(Creditor)\Identification\Source ID(SourceID)".</span><span class="sxs-lookup"><span data-stu-id="ed13b-193">In the tree, select 'model\Payments\Creditor\Identification\Source ID(SourceID)'.</span></span>
11. <span data-ttu-id="ed13b-194">En el árbol, expanda 'Excel\PaymLines'.</span><span class="sxs-lookup"><span data-stu-id="ed13b-194">In the tree, expand 'Excel\PaymLines'.</span></span>
12. <span data-ttu-id="ed13b-195">En el árbol, seleccione ''Excel\PaymLines\VendAccountName".</span><span class="sxs-lookup"><span data-stu-id="ed13b-195">In the tree, select 'Excel\PaymLines\VendAccountName'.</span></span>
13. <span data-ttu-id="ed13b-196">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="ed13b-196">Click Bind.</span></span>
14. <span data-ttu-id="ed13b-197">En el árbol, seleccione modelo\Pagos\Acreedor\Nombre.</span><span class="sxs-lookup"><span data-stu-id="ed13b-197">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
15. <span data-ttu-id="ed13b-198">En el árbol, seleccione ''Excel\PaymLines\VendName".</span><span class="sxs-lookup"><span data-stu-id="ed13b-198">In the tree, select 'Excel\PaymLines\VendName'.</span></span>
16. <span data-ttu-id="ed13b-199">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="ed13b-199">Click Bind.</span></span>
17. <span data-ttu-id="ed13b-200">En el árbol, expanda “modelo\Pagos\Cuenta de acreedor(CreditorAccount)”.</span><span class="sxs-lookup"><span data-stu-id="ed13b-200">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
18. <span data-ttu-id="ed13b-201">En el árbol, expanda “modelo\Pagos\Cuenta de acreedor(CreditorAccount)\Nombre”.</span><span class="sxs-lookup"><span data-stu-id="ed13b-201">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Name'.</span></span>
19. <span data-ttu-id="ed13b-202">En el árbol, seleccione ''Excel\PaymLines\Bank".</span><span class="sxs-lookup"><span data-stu-id="ed13b-202">In the tree, select 'Excel\PaymLines\Bank'.</span></span>
20. <span data-ttu-id="ed13b-203">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="ed13b-203">Click Bind.</span></span>
21. <span data-ttu-id="ed13b-204">En el árbol, seleccione "modelo\Pagos\Agente del acreedor(CreditorAgent)\Número de ruta(RoutingNumber)".</span><span class="sxs-lookup"><span data-stu-id="ed13b-204">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Routing Number(RoutingNumber)'.</span></span>
22. <span data-ttu-id="ed13b-205">En el árbol, seleccione ''Excel\PaymLines\RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="ed13b-205">In the tree, select 'Excel\PaymLines\RoutingNumber'.</span></span>
23. <span data-ttu-id="ed13b-206">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="ed13b-206">Click Bind.</span></span>
24. <span data-ttu-id="ed13b-207">En el árbol, expanda “model\Payments\Creditor Account(CreditorAccount)”.</span><span class="sxs-lookup"><span data-stu-id="ed13b-207">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
25. <span data-ttu-id="ed13b-208">En el árbol, expanda “model\Payments\Creditor Account(CreditorAccount)\Identification”.</span><span class="sxs-lookup"><span data-stu-id="ed13b-208">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)\Identification'.</span></span>
26. <span data-ttu-id="ed13b-209">En el árbol, seleccione "modelo\Pagos\Cuenta de acreedor(CreditorAccount)\Identification\Número”.</span><span class="sxs-lookup"><span data-stu-id="ed13b-209">In the tree, select 'model\Payments\Creditor Account(CreditorAccount)\Identification\Number'.</span></span>
27. <span data-ttu-id="ed13b-210">En el árbol, seleccione ''Excel\PaymLines\AccountNumber".</span><span class="sxs-lookup"><span data-stu-id="ed13b-210">In the tree, select 'Excel\PaymLines\AccountNumber'.</span></span>
28. <span data-ttu-id="ed13b-211">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="ed13b-211">Click Bind.</span></span>
29. <span data-ttu-id="ed13b-212">En el árbol, seleccione "modelo\Pagos\Importe ordenado(InstructedAmount)".</span><span class="sxs-lookup"><span data-stu-id="ed13b-212">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
30. <span data-ttu-id="ed13b-213">En el árbol, seleccione ''Excel\PaymLines\Débito".</span><span class="sxs-lookup"><span data-stu-id="ed13b-213">In the tree, select 'Excel\PaymLines\Debit'.</span></span>
31. <span data-ttu-id="ed13b-214">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="ed13b-214">Click Bind.</span></span>
32. <span data-ttu-id="ed13b-215">En el árbol, expanda modelo\Pagos\Acreedor.</span><span class="sxs-lookup"><span data-stu-id="ed13b-215">In the tree, expand 'model\Payments\Creditor'.</span></span>
33. <span data-ttu-id="ed13b-216">En el árbol, expanda “model\Payments\Creditor Account(CreditorAccount)”.</span><span class="sxs-lookup"><span data-stu-id="ed13b-216">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
34. <span data-ttu-id="ed13b-217">En el árbol, expanda “modelo\Pagos\Cuenta de acreedor(CreditorAccount)”.</span><span class="sxs-lookup"><span data-stu-id="ed13b-217">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
35. <span data-ttu-id="ed13b-218">En el árbol, seleccione "modelo\Pagos\Divisa".</span><span class="sxs-lookup"><span data-stu-id="ed13b-218">In the tree, select 'model\Payments\Currency'.</span></span>
36. <span data-ttu-id="ed13b-219">En el árbol, seleccione ''Excel\PaymLines\Moneda".</span><span class="sxs-lookup"><span data-stu-id="ed13b-219">In the tree, select 'Excel\PaymLines\Currency'.</span></span>
37. <span data-ttu-id="ed13b-220">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="ed13b-220">Click Bind.</span></span>
38. <span data-ttu-id="ed13b-221">En el árbol, expanda "PaymentByCurrency".</span><span class="sxs-lookup"><span data-stu-id="ed13b-221">In the tree, expand 'PaymentByCurrency'.</span></span>
39. <span data-ttu-id="ed13b-222">En el árbol, expanda "PaymentByCurrency\agrupado".</span><span class="sxs-lookup"><span data-stu-id="ed13b-222">In the tree, expand 'PaymentByCurrency\grouped'.</span></span>
40. <span data-ttu-id="ed13b-223">En el árbol, seleccione "PaymentByCurrency\agrupado\Divisa".</span><span class="sxs-lookup"><span data-stu-id="ed13b-223">In the tree, select 'PaymentByCurrency\grouped\Currency'.</span></span>
41. <span data-ttu-id="ed13b-224">En el árbol, expanda "Excel\SummaryLines".</span><span class="sxs-lookup"><span data-stu-id="ed13b-224">In the tree, expand 'Excel\SummaryLines'.</span></span>
42. <span data-ttu-id="ed13b-225">En el árbol, seleccione ''Excel\SummaryLines\SummaryCurrency".</span><span class="sxs-lookup"><span data-stu-id="ed13b-225">In the tree, select 'Excel\SummaryLines\SummaryCurrency'.</span></span>
43. <span data-ttu-id="ed13b-226">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="ed13b-226">Click Bind.</span></span>
44. <span data-ttu-id="ed13b-227">En el árbol, expanda "PaymentByCurrency\agregado".</span><span class="sxs-lookup"><span data-stu-id="ed13b-227">In the tree, expand 'PaymentByCurrency\aggregated'.</span></span>
45. <span data-ttu-id="ed13b-228">En el árbol, seleccione "PaymentByCurrency\agregado\TotalInstructuredAmount".</span><span class="sxs-lookup"><span data-stu-id="ed13b-228">In the tree, select 'PaymentByCurrency\aggregated\TotalInstructuredAmount'.</span></span>
46. <span data-ttu-id="ed13b-229">En el árbol, seleccione ''Excel\SummaryLines\SummaryAmount".</span><span class="sxs-lookup"><span data-stu-id="ed13b-229">In the tree, select 'Excel\SummaryLines\SummaryAmount'.</span></span>
47. <span data-ttu-id="ed13b-230">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="ed13b-230">Click Bind.</span></span>
48. <span data-ttu-id="ed13b-231">En el árbol, seleccione "PaymentByCurrency".</span><span class="sxs-lookup"><span data-stu-id="ed13b-231">In the tree, select 'PaymentByCurrency'.</span></span>
49. <span data-ttu-id="ed13b-232">En el árbol, seleccione "Excel\SummaryLines".</span><span class="sxs-lookup"><span data-stu-id="ed13b-232">In the tree, select 'Excel\SummaryLines'.</span></span>
50. <span data-ttu-id="ed13b-233">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="ed13b-233">Click Bind.</span></span>
51. <span data-ttu-id="ed13b-234">En el árbol, seleccione modelo\Pagos.</span><span class="sxs-lookup"><span data-stu-id="ed13b-234">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="ed13b-235">En el árbol, seleccione ''Excel\PaymLines".</span><span class="sxs-lookup"><span data-stu-id="ed13b-235">In the tree, select 'Excel\PaymLines'.</span></span>
53. <span data-ttu-id="ed13b-236">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="ed13b-236">Click Bind.</span></span>
54. <span data-ttu-id="ed13b-237">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ed13b-237">Click Save.</span></span>
55. <span data-ttu-id="ed13b-238">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ed13b-238">Close the page.</span></span>

## <a name="use-the-created-configuration-for-payments-processing"></a><span data-ttu-id="ed13b-239">Usar la configuración creada para procesar los pagos</span><span class="sxs-lookup"><span data-stu-id="ed13b-239">Use the created configuration for payments processing</span></span>
1. <span data-ttu-id="ed13b-240">Haga clic en Cambiar estado.</span><span class="sxs-lookup"><span data-stu-id="ed13b-240">Click Change status.</span></span>
2. <span data-ttu-id="ed13b-241">Haga clic en Completar.</span><span class="sxs-lookup"><span data-stu-id="ed13b-241">Click Complete.</span></span>
3. <span data-ttu-id="ed13b-242">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ed13b-242">Click OK.</span></span>
4. <span data-ttu-id="ed13b-243">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ed13b-243">Close the page.</span></span>
5. <span data-ttu-id="ed13b-244">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ed13b-244">Close the page.</span></span>
6. <span data-ttu-id="ed13b-245">Vaya a Proveedores > Configuración de pagos > Formas de pago.</span><span class="sxs-lookup"><span data-stu-id="ed13b-245">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
7. <span data-ttu-id="ed13b-246">Use el Filtro Rápido para filtrar el campo Método de pago con un valor de "Electronic".</span><span class="sxs-lookup"><span data-stu-id="ed13b-246">Use the Quick Filter to filter on the Method of payment field with a value of 'Electronic'.</span></span>
    * <span data-ttu-id="ed13b-247">Electrónica</span><span class="sxs-lookup"><span data-stu-id="ed13b-247">Electronic</span></span>  
8. <span data-ttu-id="ed13b-248">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="ed13b-248">Click Edit.</span></span>
9. <span data-ttu-id="ed13b-249">Expanda la sección Formatos de archivo.</span><span class="sxs-lookup"><span data-stu-id="ed13b-249">Expand the File formats section.</span></span>
10. <span data-ttu-id="ed13b-250">Seleccione Sí en el campo Informes electrónicos genéricos.</span><span class="sxs-lookup"><span data-stu-id="ed13b-250">Select Yes in the Generic electronic reporting field.</span></span>
11. <span data-ttu-id="ed13b-251">En el campo Configuración de formato de exportación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ed13b-251">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="ed13b-252">Seleccione la configuración "Informe de hoja de cálculo de muestra”.</span><span class="sxs-lookup"><span data-stu-id="ed13b-252">Select the ‘Sample worksheet report’ configuration.</span></span>  
12. <span data-ttu-id="ed13b-253">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ed13b-253">Click Save.</span></span>
13. <span data-ttu-id="ed13b-254">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ed13b-254">Close the page.</span></span>

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a><span data-ttu-id="ed13b-255">Usar la configuración creada para probar el procesamiento de diarios de pago</span><span class="sxs-lookup"><span data-stu-id="ed13b-255">Use the created configuration for testing of payment journals processing</span></span>
1. <span data-ttu-id="ed13b-256">Vaya a Proveedores > Pagos > Diario de pagos.</span><span class="sxs-lookup"><span data-stu-id="ed13b-256">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="ed13b-257">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ed13b-257">Click New.</span></span>
    * <span data-ttu-id="ed13b-258">Crear un diario de pago nuevo.</span><span class="sxs-lookup"><span data-stu-id="ed13b-258">Create a new payment journal.</span></span>  
3. <span data-ttu-id="ed13b-259">En el campo Nombre, escriba "VendPay".</span><span class="sxs-lookup"><span data-stu-id="ed13b-259">In the Name field, type 'VendPay'.</span></span>
    * <span data-ttu-id="ed13b-260">VendPay</span><span class="sxs-lookup"><span data-stu-id="ed13b-260">VendPay</span></span>  
4. <span data-ttu-id="ed13b-261">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="ed13b-261">Click Lines.</span></span>
5. <span data-ttu-id="ed13b-262">En el campo Cuenta, especifique los valores "GB_SI_000001".</span><span class="sxs-lookup"><span data-stu-id="ed13b-262">In the Account field, specify the values 'GB_SI_000001'.</span></span>
    * <span data-ttu-id="ed13b-263">GB_SI_000001</span><span class="sxs-lookup"><span data-stu-id="ed13b-263">GB_SI_000001</span></span>  
6. <span data-ttu-id="ed13b-264">Establezca Débito en "1000".</span><span class="sxs-lookup"><span data-stu-id="ed13b-264">Set Debit to '1000'.</span></span>
7. <span data-ttu-id="ed13b-265">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ed13b-265">Click New.</span></span>
8. <span data-ttu-id="ed13b-266">En el campo Cuenta, especifique los valores "GB_SI_000005".</span><span class="sxs-lookup"><span data-stu-id="ed13b-266">In the Account field, specify the values 'GB_SI_000005'.</span></span>
    * <span data-ttu-id="ed13b-267">GB_SI_000005</span><span class="sxs-lookup"><span data-stu-id="ed13b-267">GB_SI_000005</span></span>  
9. <span data-ttu-id="ed13b-268">Establezca Débito en "2000".</span><span class="sxs-lookup"><span data-stu-id="ed13b-268">Set Debit to '2000'.</span></span>
10. <span data-ttu-id="ed13b-269">En el campo Divisa, escriba "EUR".</span><span class="sxs-lookup"><span data-stu-id="ed13b-269">In the Currency field, type 'EUR'.</span></span>
    * <span data-ttu-id="ed13b-270">EUR</span><span class="sxs-lookup"><span data-stu-id="ed13b-270">EUR</span></span>  
11. <span data-ttu-id="ed13b-271">En el campo Cuenta de contrapartida, especifique los valores "GBSI OPER".</span><span class="sxs-lookup"><span data-stu-id="ed13b-271">In the Offset account field, specify the values 'GBSI OPER'.</span></span>
    * <span data-ttu-id="ed13b-272">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="ed13b-272">GBSI OPER</span></span>  
12. <span data-ttu-id="ed13b-273">En el campo Forma de pago, escriba un "Electrónica".</span><span class="sxs-lookup"><span data-stu-id="ed13b-273">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="ed13b-274">Electrónica</span><span class="sxs-lookup"><span data-stu-id="ed13b-274">Electronic</span></span>  
13. <span data-ttu-id="ed13b-275">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ed13b-275">Click Save.</span></span>
14. <span data-ttu-id="ed13b-276">Haga clic en Generar pagos.</span><span class="sxs-lookup"><span data-stu-id="ed13b-276">Click Generate payments.</span></span>
15. <span data-ttu-id="ed13b-277">En el campo Forma de pago, escriba un "Electrónica".</span><span class="sxs-lookup"><span data-stu-id="ed13b-277">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="ed13b-278">Electrónica</span><span class="sxs-lookup"><span data-stu-id="ed13b-278">Electronic</span></span>  
16. <span data-ttu-id="ed13b-279">En el campo Nombre, escriba "Pagos".</span><span class="sxs-lookup"><span data-stu-id="ed13b-279">In the File name field, type 'Payments'.</span></span>
    * <span data-ttu-id="ed13b-280">Por ejemplo, escriba Pagos.</span><span class="sxs-lookup"><span data-stu-id="ed13b-280">For example, type Payments.</span></span>  
17. <span data-ttu-id="ed13b-281">En el campo Cuenta bancaria, escriba "GBSI OPER".</span><span class="sxs-lookup"><span data-stu-id="ed13b-281">In the Bank account field, type 'GBSI OPER'.</span></span>
    * <span data-ttu-id="ed13b-282">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="ed13b-282">GBSI OPER</span></span>  
18. <span data-ttu-id="ed13b-283">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ed13b-283">Click OK.</span></span>
19. <span data-ttu-id="ed13b-284">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ed13b-284">Click OK.</span></span>
    * <span data-ttu-id="ed13b-285">Revise la hoja de trabajo creada, incluidos los detalles de líneas de pago así como los totales para cada código de divisa usado en este mensaje de pago.</span><span class="sxs-lookup"><span data-stu-id="ed13b-285">Review the created worksheet, including details of payment lines as well as totals for each currency code used in this payment message.</span></span>  


