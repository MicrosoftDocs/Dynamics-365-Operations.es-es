--- 
title: "Diseñar una configuración para generar informes con formato OpenXML para informes electrónicos (ER)"
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 04def14ddf9b079005bf11acbcaf64b21aa80fdb
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="design-a-configuration-for-generating-reports-in-openxml-format-for-electronic-reporting-er"></a><span data-ttu-id="44691-103">Diseñar una configuración para generar informes con formato OpenXML para informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="44691-103">Design a configuration for generating reports in OpenXML format for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="44691-104">En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o desarrollador de informes electrónicos puede crear una nueva configuración de informes electrónicos que contenga una plantilla para generar documentos electrónicos en formato OPENXML.</span><span class="sxs-lookup"><span data-stu-id="44691-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a template for generating electronic documents in OPENXML format.</span></span> <span data-ttu-id="44691-105">Esta configuración se usará para procesar los pagos de proveedor.</span><span class="sxs-lookup"><span data-stu-id="44691-105">This configuration will be used for processing vendor payments.</span></span>



<span data-ttu-id="44691-106">En este ejemplo, creará una configuración para la empresa de demostración, Litware, Inc. Estos pasos se pueden realizar en empresa GBSI.</span><span class="sxs-lookup"><span data-stu-id="44691-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in GBSI company.</span></span>



<span data-ttu-id="44691-107">Para completar estos pasos, primero debe completar los pasos del procedimiento Creación y activación de un proveedor de configuraciones.</span><span class="sxs-lookup"><span data-stu-id="44691-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="44691-108">También debe tener un archivo Excel que se importará el crear la plantilla.</span><span class="sxs-lookup"><span data-stu-id="44691-108">You must also have an Excel file which will be imported when creating the template.</span></span> <span data-ttu-id="44691-109">A este archivo se puede obtener acceso desde: https://msdynamics.blob.core.windows.net/media/2016/04/SampleVendPaymWsReport.xlsx</span><span class="sxs-lookup"><span data-stu-id="44691-109">This file can be accessed from:  https://msdynamics.blob.core.windows.net/media/2016/04/SampleVendPaymWsReport.xlsx</span></span>


## <a name="upload-the-payments-data-model-configuration"></a><span data-ttu-id="44691-110">Cargar la configuración del modelo de datos de pagos</span><span class="sxs-lookup"><span data-stu-id="44691-110">Upload the Payments data model configuration</span></span>
1. <span data-ttu-id="44691-111">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="44691-111">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="44691-112">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="44691-112">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="44691-113">Seleccione el proveedor de la configuración de la empresa de ejemplo, Litware, Inc. Si no ve a este proveedor de configuración, primero debe completar los pasos del procedimiento "Creación y activación de un proveedor de configuraciones".</span><span class="sxs-lookup"><span data-stu-id="44691-113">Select the configuration provider for sample company, Litware, Inc. If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
3. <span data-ttu-id="44691-114">Haga clic en Definir como activo.</span><span class="sxs-lookup"><span data-stu-id="44691-114">Click Set active.</span></span>
4. <span data-ttu-id="44691-115">Haga clic en Repositorios.</span><span class="sxs-lookup"><span data-stu-id="44691-115">Click Repositories.</span></span>
    * <span data-ttu-id="44691-116">Seleccione un repositorio para el tipo de recursos de operaciones, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="44691-116">Select a repository for the Operations Resources type, if available.</span></span> <span data-ttu-id="44691-117">Si está disponible, omita los siguientes pasos acerca de la creación de un nuevo repositorio.</span><span class="sxs-lookup"><span data-stu-id="44691-117">If its available, skip the following steps about creating a new repository.</span></span>  
5. <span data-ttu-id="44691-118">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="44691-118">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="44691-119">En el campo Tipo de repositorio de configuración, escriba "Recursos de Operations".</span><span class="sxs-lookup"><span data-stu-id="44691-119">In the Configuration repository type field, enter 'Operations resources'.</span></span>
7. <span data-ttu-id="44691-120">Haga clic en Crear repositorio.</span><span class="sxs-lookup"><span data-stu-id="44691-120">Click Create repository.</span></span>
8. <span data-ttu-id="44691-121">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="44691-121">Click OK.</span></span>
9. <span data-ttu-id="44691-122">Haga clic en Abrir.</span><span class="sxs-lookup"><span data-stu-id="44691-122">Click Open.</span></span>
10. <span data-ttu-id="44691-123">En el árbol, seleccione "Modelo de pago".</span><span class="sxs-lookup"><span data-stu-id="44691-123">In the tree, select 'Payment model'.</span></span>
11. <span data-ttu-id="44691-124">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="44691-124">Click Import.</span></span>
    * <span data-ttu-id="44691-125">Importe este modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="44691-125">Import this data model.</span></span> <span data-ttu-id="44691-126">Se usará como origen de datos en una nueva configuración de formato.</span><span class="sxs-lookup"><span data-stu-id="44691-126">It will be used as a data source in a new format configuration.</span></span> <span data-ttu-id="44691-127">Omita este paso si esta configuración ya se ha importado.</span><span class="sxs-lookup"><span data-stu-id="44691-127">Skip this step if this configuration has been already imported.</span></span>  
12. <span data-ttu-id="44691-128">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="44691-128">Click Yes.</span></span>
13. <span data-ttu-id="44691-129">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="44691-129">Close the page.</span></span>
14. <span data-ttu-id="44691-130">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="44691-130">Close the page.</span></span>

## <a name="create-a-new-format-configuration"></a><span data-ttu-id="44691-131">Creación de una configuración de formato nueva</span><span class="sxs-lookup"><span data-stu-id="44691-131">Create a new format configuration</span></span>
1. <span data-ttu-id="44691-132">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="44691-132">Click Reporting configurations.</span></span>
2. <span data-ttu-id="44691-133">En el árbol, seleccione "Modelo de pago".</span><span class="sxs-lookup"><span data-stu-id="44691-133">In the tree, select 'Payment model'.</span></span>
3. <span data-ttu-id="44691-134">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="44691-134">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="44691-135">En el campo Nuevo, especifique "Formato basado en modelo de datos PaymentModel".</span><span class="sxs-lookup"><span data-stu-id="44691-135">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
    * <span data-ttu-id="44691-136">Cree un formato que se base en el modelo de datos de PaymentModel.</span><span class="sxs-lookup"><span data-stu-id="44691-136">Create a format that is based on the PaymentModel data model.</span></span>  
5. <span data-ttu-id="44691-137">En el campo Nombre, escriba "Informe de hoja de cálculo de muestra".</span><span class="sxs-lookup"><span data-stu-id="44691-137">In the Name field, type 'Sample worksheet report'.</span></span>
    * <span data-ttu-id="44691-138">Informe de hoja de cálculo de muestra</span><span class="sxs-lookup"><span data-stu-id="44691-138">Sample worksheet report</span></span>  
6. <span data-ttu-id="44691-139">En el campo Descripción, escriba "Informe de hoja de cálculo para pagos de proveedores".</span><span class="sxs-lookup"><span data-stu-id="44691-139">In the Description field, type 'Sample worksheet report for vendors’ payments'.</span></span>
    * <span data-ttu-id="44691-140">Informe de hoja de cálculo para pagos de proveedores.</span><span class="sxs-lookup"><span data-stu-id="44691-140">Sample worksheet report for vendors’ payments.</span></span>  
7. <span data-ttu-id="44691-141">En el campo definición del modelo de Datos, introduzca o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="44691-141">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="44691-142">Seleccione la definición "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="44691-142">Select the 'CustomerCreditTransferInitiation' definition.</span></span>  
8. <span data-ttu-id="44691-143">Haga clic en Crear configuración.</span><span class="sxs-lookup"><span data-stu-id="44691-143">Click Create configuration.</span></span>

## <a name="design-a-new-document-in-openxml-worksheet-format"></a><span data-ttu-id="44691-144">Diseñar un documento nuevo en formato de hoja de cálculo OPENXML</span><span class="sxs-lookup"><span data-stu-id="44691-144">Design a new document in OPENXML worksheet format</span></span>
1. <span data-ttu-id="44691-145">En el árbol, seleccione "Modelo de pago\Informe de hoja de cálculo de muestra".</span><span class="sxs-lookup"><span data-stu-id="44691-145">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
2. <span data-ttu-id="44691-146">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="44691-146">Click Designer.</span></span>
3. <span data-ttu-id="44691-147">En el panel de acciones, haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="44691-147">On the Action Pane, click Import.</span></span>
4. <span data-ttu-id="44691-148">Haga clic en Importar desde Excel.</span><span class="sxs-lookup"><span data-stu-id="44691-148">Click Import from Excel.</span></span>
5. <span data-ttu-id="44691-149">Haga clic en Archivos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="44691-149">Click Attachments.</span></span>
    * <span data-ttu-id="44691-150">Adjunte el documento de Excel existente como plantilla.</span><span class="sxs-lookup"><span data-stu-id="44691-150">Attach the existing Excel document as a template.</span></span>  
6. <span data-ttu-id="44691-151">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="44691-151">Click New.</span></span>
7. <span data-ttu-id="44691-152">Haga clic en Archivo.</span><span class="sxs-lookup"><span data-stu-id="44691-152">Click File.</span></span>
    * <span data-ttu-id="44691-153">Señale al archivo de Excel existente.</span><span class="sxs-lookup"><span data-stu-id="44691-153">Point to the existing Excel file.</span></span>  
8. <span data-ttu-id="44691-154">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="44691-154">Close the page.</span></span>
9. <span data-ttu-id="44691-155">En el campo Plantilla, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="44691-155">In the Template field, enter or select a value.</span></span>
    * <span data-ttu-id="44691-156">Seleccione el archivo de Excel adjunto que se usará como plantilla.</span><span class="sxs-lookup"><span data-stu-id="44691-156">Select the attached Excel file to be used as a template.</span></span>  
10. <span data-ttu-id="44691-157">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="44691-157">Click OK.</span></span>
    * <span data-ttu-id="44691-158">Tenga en cuenta que los componentes en formato ER se han creado en el formato de diseño basado en la estructura del documento de MS Excel de referencia (intervalos con nombre).</span><span class="sxs-lookup"><span data-stu-id="44691-158">Note that ER format components have been created in the designing format based on the structure of the referring MS Excel document (named ranges).</span></span>  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a><span data-ttu-id="44691-159">Crear un nuevo origen de datos para calcular totales por códigos de divisa</span><span class="sxs-lookup"><span data-stu-id="44691-159">Create a new data source to calculate totals by currency codes</span></span>
1. <span data-ttu-id="44691-160">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="44691-160">Click the Mapping tab.</span></span>
2. <span data-ttu-id="44691-161">Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="44691-161">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="44691-162">En el árbol, seleccione "Funciones\Agrupar por".</span><span class="sxs-lookup"><span data-stu-id="44691-162">In the tree, select 'Functions\Group by'.</span></span>
4. <span data-ttu-id="44691-163">En el campo Nombre, escriba "PaymentByCurrency".</span><span class="sxs-lookup"><span data-stu-id="44691-163">In the Name field, type 'PaymentByCurrency'.</span></span>
    * <span data-ttu-id="44691-164">PaymentByCurrency</span><span class="sxs-lookup"><span data-stu-id="44691-164">PaymentByCurrency</span></span>  
5. <span data-ttu-id="44691-165">Haga clic en Editar grupo por.</span><span class="sxs-lookup"><span data-stu-id="44691-165">Click Edit group by.</span></span>
6. <span data-ttu-id="44691-166">En el árbol , expanda "modelo".</span><span class="sxs-lookup"><span data-stu-id="44691-166">In the tree, expand 'model'.</span></span>
7. <span data-ttu-id="44691-167">En el árbol, seleccione modelo\Pagos.</span><span class="sxs-lookup"><span data-stu-id="44691-167">In the tree, select 'model\Payments'.</span></span>
8. <span data-ttu-id="44691-168">Haga clic en Agregar campo a.</span><span class="sxs-lookup"><span data-stu-id="44691-168">Click Add field to.</span></span>
9. <span data-ttu-id="44691-169">Haga clic en Elementos para agrupar.</span><span class="sxs-lookup"><span data-stu-id="44691-169">Click What to group.</span></span>
10. <span data-ttu-id="44691-170">En el árbol, expanda modelo\Pagos.</span><span class="sxs-lookup"><span data-stu-id="44691-170">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="44691-171">En el árbol, seleccione "modelo\Pagos\Divisa".</span><span class="sxs-lookup"><span data-stu-id="44691-171">In the tree, select 'model\Payments\Currency'.</span></span>
12. <span data-ttu-id="44691-172">Haga clic en Agregar campo a.</span><span class="sxs-lookup"><span data-stu-id="44691-172">Click Add field to.</span></span>
13. <span data-ttu-id="44691-173">Haga clic en Campos agrupados.</span><span class="sxs-lookup"><span data-stu-id="44691-173">Click Grouped fields.</span></span>
14. <span data-ttu-id="44691-174">En el árbol, seleccione "modelo\Pagos\Importe ordenado(InstructedAmount)".</span><span class="sxs-lookup"><span data-stu-id="44691-174">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
15. <span data-ttu-id="44691-175">Haga clic en Agregar campo a.</span><span class="sxs-lookup"><span data-stu-id="44691-175">Click Add field to.</span></span>
16. <span data-ttu-id="44691-176">Haga clic en Campos de agregación.</span><span class="sxs-lookup"><span data-stu-id="44691-176">Click Aggregation fields.</span></span>
17. <span data-ttu-id="44691-177">En el campo Método, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="44691-177">In the Method field, select an option.</span></span>
    * <span data-ttu-id="44691-178">Seleccione la función de agregación SUMA.</span><span class="sxs-lookup"><span data-stu-id="44691-178">Select the SUM aggregation function.</span></span>  
18. <span data-ttu-id="44691-179">En el campo Nombre, escriba "TotalInstructuredAmount".</span><span class="sxs-lookup"><span data-stu-id="44691-179">In the Name field, type 'TotalInstructuredAmount'.</span></span>
    * <span data-ttu-id="44691-180">TotalInstructuredAmount</span><span class="sxs-lookup"><span data-stu-id="44691-180">TotalInstructuredAmount</span></span>  
19. <span data-ttu-id="44691-181">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="44691-181">Click Save.</span></span>
20. <span data-ttu-id="44691-182">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="44691-182">Close the page.</span></span>
21. <span data-ttu-id="44691-183">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="44691-183">Click OK.</span></span>

## <a name="map-format-components-to-data-sources"></a><span data-ttu-id="44691-184">Asignar componentes de formato a orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="44691-184">Map format components to data sources</span></span>
1. <span data-ttu-id="44691-185">En el árbol , expanda "modelo".</span><span class="sxs-lookup"><span data-stu-id="44691-185">In the tree, expand 'model'.</span></span>
2. <span data-ttu-id="44691-186">En el árbol, expanda modelo\Pagos.</span><span class="sxs-lookup"><span data-stu-id="44691-186">In the tree, expand 'model\Payments'.</span></span>
3. <span data-ttu-id="44691-187">En el árbol, expanda "modelo\Pagos\Parte iniciadora(InitiatingParty)".</span><span class="sxs-lookup"><span data-stu-id="44691-187">In the tree, expand 'model\Payments\Initiating Party(InitiatingParty)'.</span></span>
4. <span data-ttu-id="44691-188">En el árbol, seleccione "modelo\Pagos\Parte iniciadora(InitiatingParty)\Name".</span><span class="sxs-lookup"><span data-stu-id="44691-188">In the tree, select 'model\Payments\Initiating Party(InitiatingParty)\Name'.</span></span>
5. <span data-ttu-id="44691-189">En el árbol, expanda 'Excel\ReportHeader'.</span><span class="sxs-lookup"><span data-stu-id="44691-189">In the tree, expand 'Excel\ReportHeader'.</span></span>
6. <span data-ttu-id="44691-190">En el árbol, seleccione ''Excel\ReportHeader\CompanyName".</span><span class="sxs-lookup"><span data-stu-id="44691-190">In the tree, select 'Excel\ReportHeader\CompanyName'.</span></span>
7. <span data-ttu-id="44691-191">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="44691-191">Click Bind.</span></span>
8. <span data-ttu-id="44691-192">En el árbol, expanda modelo\Pagos\Acreedor.</span><span class="sxs-lookup"><span data-stu-id="44691-192">In the tree, expand 'model\Payments\Creditor'.</span></span>
9. <span data-ttu-id="44691-193">En el árbol, expanda "modelo\Pagos\Acreedor\Identificación".</span><span class="sxs-lookup"><span data-stu-id="44691-193">In the tree, expand 'model\Payments\Creditor\Identification'.</span></span>
10. <span data-ttu-id="44691-194">En el árbol, seleccione "modelo\Pagos\Cuenta de acreedor(Creditor)\Identification\Source ID(SourceID)".</span><span class="sxs-lookup"><span data-stu-id="44691-194">In the tree, select 'model\Payments\Creditor\Identification\Source ID(SourceID)'.</span></span>
11. <span data-ttu-id="44691-195">En el árbol, expanda 'Excel\PaymLines'.</span><span class="sxs-lookup"><span data-stu-id="44691-195">In the tree, expand 'Excel\PaymLines'.</span></span>
12. <span data-ttu-id="44691-196">En el árbol, seleccione ''Excel\PaymLines\VendAccountName".</span><span class="sxs-lookup"><span data-stu-id="44691-196">In the tree, select 'Excel\PaymLines\VendAccountName'.</span></span>
13. <span data-ttu-id="44691-197">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="44691-197">Click Bind.</span></span>
14. <span data-ttu-id="44691-198">En el árbol, seleccione modelo\Pagos\Acreedor\Nombre.</span><span class="sxs-lookup"><span data-stu-id="44691-198">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
15. <span data-ttu-id="44691-199">En el árbol, seleccione ''Excel\PaymLines\VendName".</span><span class="sxs-lookup"><span data-stu-id="44691-199">In the tree, select 'Excel\PaymLines\VendName'.</span></span>
16. <span data-ttu-id="44691-200">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="44691-200">Click Bind.</span></span>
17. <span data-ttu-id="44691-201">En el árbol, expanda “modelo\Pagos\Cuenta de acreedor(CreditorAccount)”.</span><span class="sxs-lookup"><span data-stu-id="44691-201">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
18. <span data-ttu-id="44691-202">En el árbol, expanda “modelo\Pagos\Cuenta de acreedor(CreditorAccount)\Nombre”.</span><span class="sxs-lookup"><span data-stu-id="44691-202">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Name'.</span></span>
19. <span data-ttu-id="44691-203">En el árbol, seleccione ''Excel\PaymLines\Bank".</span><span class="sxs-lookup"><span data-stu-id="44691-203">In the tree, select 'Excel\PaymLines\Bank'.</span></span>
20. <span data-ttu-id="44691-204">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="44691-204">Click Bind.</span></span>
21. <span data-ttu-id="44691-205">En el árbol, seleccione "modelo\Pagos\Agente del acreedor(CreditorAgent)\Número de ruta(RoutingNumber)".</span><span class="sxs-lookup"><span data-stu-id="44691-205">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Routing Number(RoutingNumber)'.</span></span>
22. <span data-ttu-id="44691-206">En el árbol, seleccione ''Excel\PaymLines\RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="44691-206">In the tree, select 'Excel\PaymLines\RoutingNumber'.</span></span>
23. <span data-ttu-id="44691-207">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="44691-207">Click Bind.</span></span>
24. <span data-ttu-id="44691-208">En el árbol, expanda “model\Payments\Creditor Account(CreditorAccount)”.</span><span class="sxs-lookup"><span data-stu-id="44691-208">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
25. <span data-ttu-id="44691-209">En el árbol, expanda “model\Payments\Creditor Account(CreditorAccount)\Identification”.</span><span class="sxs-lookup"><span data-stu-id="44691-209">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)\Identification'.</span></span>
26. <span data-ttu-id="44691-210">En el árbol, seleccione "modelo\Pagos\Cuenta de acreedor(CreditorAccount)\Identification\Número”.</span><span class="sxs-lookup"><span data-stu-id="44691-210">In the tree, select 'model\Payments\Creditor Account(CreditorAccount)\Identification\Number'.</span></span>
27. <span data-ttu-id="44691-211">En el árbol, seleccione ''Excel\PaymLines\AccountNumber".</span><span class="sxs-lookup"><span data-stu-id="44691-211">In the tree, select 'Excel\PaymLines\AccountNumber'.</span></span>
28. <span data-ttu-id="44691-212">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="44691-212">Click Bind.</span></span>
29. <span data-ttu-id="44691-213">En el árbol, seleccione "modelo\Pagos\Importe ordenado(InstructedAmount)".</span><span class="sxs-lookup"><span data-stu-id="44691-213">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
30. <span data-ttu-id="44691-214">En el árbol, seleccione ''Excel\PaymLines\Débito".</span><span class="sxs-lookup"><span data-stu-id="44691-214">In the tree, select 'Excel\PaymLines\Debit'.</span></span>
31. <span data-ttu-id="44691-215">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="44691-215">Click Bind.</span></span>
32. <span data-ttu-id="44691-216">En el árbol, expanda modelo\Pagos\Acreedor.</span><span class="sxs-lookup"><span data-stu-id="44691-216">In the tree, expand 'model\Payments\Creditor'.</span></span>
33. <span data-ttu-id="44691-217">En el árbol, expanda “model\Payments\Creditor Account(CreditorAccount)”.</span><span class="sxs-lookup"><span data-stu-id="44691-217">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
34. <span data-ttu-id="44691-218">En el árbol, expanda “modelo\Pagos\Cuenta de acreedor(CreditorAccount)”.</span><span class="sxs-lookup"><span data-stu-id="44691-218">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
35. <span data-ttu-id="44691-219">En el árbol, seleccione "modelo\Pagos\Divisa".</span><span class="sxs-lookup"><span data-stu-id="44691-219">In the tree, select 'model\Payments\Currency'.</span></span>
36. <span data-ttu-id="44691-220">En el árbol, seleccione ''Excel\PaymLines\Moneda".</span><span class="sxs-lookup"><span data-stu-id="44691-220">In the tree, select 'Excel\PaymLines\Currency'.</span></span>
37. <span data-ttu-id="44691-221">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="44691-221">Click Bind.</span></span>
38. <span data-ttu-id="44691-222">En el árbol, expanda "PaymentByCurrency".</span><span class="sxs-lookup"><span data-stu-id="44691-222">In the tree, expand 'PaymentByCurrency'.</span></span>
39. <span data-ttu-id="44691-223">En el árbol, expanda "PaymentByCurrency\agrupado".</span><span class="sxs-lookup"><span data-stu-id="44691-223">In the tree, expand 'PaymentByCurrency\grouped'.</span></span>
40. <span data-ttu-id="44691-224">En el árbol, seleccione "PaymentByCurrency\agrupado\Divisa".</span><span class="sxs-lookup"><span data-stu-id="44691-224">In the tree, select 'PaymentByCurrency\grouped\Currency'.</span></span>
41. <span data-ttu-id="44691-225">En el árbol, expanda "Excel\SummaryLines".</span><span class="sxs-lookup"><span data-stu-id="44691-225">In the tree, expand 'Excel\SummaryLines'.</span></span>
42. <span data-ttu-id="44691-226">En el árbol, seleccione ''Excel\SummaryLines\SummaryCurrency".</span><span class="sxs-lookup"><span data-stu-id="44691-226">In the tree, select 'Excel\SummaryLines\SummaryCurrency'.</span></span>
43. <span data-ttu-id="44691-227">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="44691-227">Click Bind.</span></span>
44. <span data-ttu-id="44691-228">En el árbol, expanda "PaymentByCurrency\agregado".</span><span class="sxs-lookup"><span data-stu-id="44691-228">In the tree, expand 'PaymentByCurrency\aggregated'.</span></span>
45. <span data-ttu-id="44691-229">En el árbol, seleccione "PaymentByCurrency\agregado\TotalInstructuredAmount".</span><span class="sxs-lookup"><span data-stu-id="44691-229">In the tree, select 'PaymentByCurrency\aggregated\TotalInstructuredAmount'.</span></span>
46. <span data-ttu-id="44691-230">En el árbol, seleccione ''Excel\SummaryLines\SummaryAmount".</span><span class="sxs-lookup"><span data-stu-id="44691-230">In the tree, select 'Excel\SummaryLines\SummaryAmount'.</span></span>
47. <span data-ttu-id="44691-231">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="44691-231">Click Bind.</span></span>
48. <span data-ttu-id="44691-232">En el árbol, seleccione "PaymentByCurrency".</span><span class="sxs-lookup"><span data-stu-id="44691-232">In the tree, select 'PaymentByCurrency'.</span></span>
49. <span data-ttu-id="44691-233">En el árbol, seleccione "Excel\SummaryLines".</span><span class="sxs-lookup"><span data-stu-id="44691-233">In the tree, select 'Excel\SummaryLines'.</span></span>
50. <span data-ttu-id="44691-234">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="44691-234">Click Bind.</span></span>
51. <span data-ttu-id="44691-235">En el árbol, seleccione modelo\Pagos.</span><span class="sxs-lookup"><span data-stu-id="44691-235">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="44691-236">En el árbol, seleccione ''Excel\PaymLines".</span><span class="sxs-lookup"><span data-stu-id="44691-236">In the tree, select 'Excel\PaymLines'.</span></span>
53. <span data-ttu-id="44691-237">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="44691-237">Click Bind.</span></span>
54. <span data-ttu-id="44691-238">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="44691-238">Click Save.</span></span>
55. <span data-ttu-id="44691-239">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="44691-239">Close the page.</span></span>

## <a name="use-the-created-configuration-for-payments-processing"></a><span data-ttu-id="44691-240">Usar la configuración creada para procesar los pagos</span><span class="sxs-lookup"><span data-stu-id="44691-240">Use the created configuration for payments processing</span></span>
1. <span data-ttu-id="44691-241">Haga clic en Cambiar estado.</span><span class="sxs-lookup"><span data-stu-id="44691-241">Click Change status.</span></span>
2. <span data-ttu-id="44691-242">Haga clic en Completar.</span><span class="sxs-lookup"><span data-stu-id="44691-242">Click Complete.</span></span>
3. <span data-ttu-id="44691-243">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="44691-243">Click OK.</span></span>
4. <span data-ttu-id="44691-244">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="44691-244">Close the page.</span></span>
5. <span data-ttu-id="44691-245">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="44691-245">Close the page.</span></span>
6. <span data-ttu-id="44691-246">Vaya a Proveedores > Configuración de pagos > Formas de pago.</span><span class="sxs-lookup"><span data-stu-id="44691-246">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
7. <span data-ttu-id="44691-247">Use el Filtro Rápido para filtrar el campo Método de pago con un valor de "Electronic".</span><span class="sxs-lookup"><span data-stu-id="44691-247">Use the Quick Filter to filter on the Method of payment field with a value of 'Electronic'.</span></span>
    * <span data-ttu-id="44691-248">Electrónica</span><span class="sxs-lookup"><span data-stu-id="44691-248">Electronic</span></span>  
8. <span data-ttu-id="44691-249">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="44691-249">Click Edit.</span></span>
9. <span data-ttu-id="44691-250">Expanda la sección Formatos de archivo.</span><span class="sxs-lookup"><span data-stu-id="44691-250">Expand the File formats section.</span></span>
10. <span data-ttu-id="44691-251">Seleccione Sí en el campo Informes electrónicos genéricos.</span><span class="sxs-lookup"><span data-stu-id="44691-251">Select Yes in the Generic electronic reporting field.</span></span>
11. <span data-ttu-id="44691-252">En el campo Configuración de formato de exportación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="44691-252">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="44691-253">Seleccione la configuración "Informe de hoja de cálculo de muestra”.</span><span class="sxs-lookup"><span data-stu-id="44691-253">Select the ‘Sample worksheet report’ configuration.</span></span>  
12. <span data-ttu-id="44691-254">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="44691-254">Click Save.</span></span>
13. <span data-ttu-id="44691-255">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="44691-255">Close the page.</span></span>

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a><span data-ttu-id="44691-256">Usar la configuración creada para probar el procesamiento de diarios de pago</span><span class="sxs-lookup"><span data-stu-id="44691-256">Use the created configuration for testing of payment journals processing</span></span>
1. <span data-ttu-id="44691-257">Vaya a Proveedores > Pagos > Diario de pagos.</span><span class="sxs-lookup"><span data-stu-id="44691-257">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="44691-258">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="44691-258">Click New.</span></span>
    * <span data-ttu-id="44691-259">Crear un diario de pago nuevo.</span><span class="sxs-lookup"><span data-stu-id="44691-259">Create a new payment journal.</span></span>  
3. <span data-ttu-id="44691-260">En el campo Nombre, escriba "VendPay".</span><span class="sxs-lookup"><span data-stu-id="44691-260">In the Name field, type 'VendPay'.</span></span>
    * <span data-ttu-id="44691-261">VendPay</span><span class="sxs-lookup"><span data-stu-id="44691-261">VendPay</span></span>  
4. <span data-ttu-id="44691-262">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="44691-262">Click Lines.</span></span>
5. <span data-ttu-id="44691-263">En el campo Cuenta, especifique los valores "GB_SI_000001".</span><span class="sxs-lookup"><span data-stu-id="44691-263">In the Account field, specify the values 'GB_SI_000001'.</span></span>
    * <span data-ttu-id="44691-264">GB_SI_000001</span><span class="sxs-lookup"><span data-stu-id="44691-264">GB_SI_000001</span></span>  
6. <span data-ttu-id="44691-265">Establezca Débito en "1000".</span><span class="sxs-lookup"><span data-stu-id="44691-265">Set Debit to '1000'.</span></span>
7. <span data-ttu-id="44691-266">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="44691-266">Click New.</span></span>
8. <span data-ttu-id="44691-267">En el campo Cuenta, especifique los valores "GB_SI_000005".</span><span class="sxs-lookup"><span data-stu-id="44691-267">In the Account field, specify the values 'GB_SI_000005'.</span></span>
    * <span data-ttu-id="44691-268">GB_SI_000005</span><span class="sxs-lookup"><span data-stu-id="44691-268">GB_SI_000005</span></span>  
9. <span data-ttu-id="44691-269">Establezca Débito en "2000".</span><span class="sxs-lookup"><span data-stu-id="44691-269">Set Debit to '2000'.</span></span>
10. <span data-ttu-id="44691-270">En el campo Divisa, escriba "EUR".</span><span class="sxs-lookup"><span data-stu-id="44691-270">In the Currency field, type 'EUR'.</span></span>
    * <span data-ttu-id="44691-271">EUR</span><span class="sxs-lookup"><span data-stu-id="44691-271">EUR</span></span>  
11. <span data-ttu-id="44691-272">En el campo Cuenta de contrapartida, especifique los valores "GBSI OPER".</span><span class="sxs-lookup"><span data-stu-id="44691-272">In the Offset account field, specify the values 'GBSI OPER'.</span></span>
    * <span data-ttu-id="44691-273">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="44691-273">GBSI OPER</span></span>  
12. <span data-ttu-id="44691-274">En el campo Forma de pago, escriba un "Electrónica".</span><span class="sxs-lookup"><span data-stu-id="44691-274">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="44691-275">Electrónica</span><span class="sxs-lookup"><span data-stu-id="44691-275">Electronic</span></span>  
13. <span data-ttu-id="44691-276">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="44691-276">Click Save.</span></span>
14. <span data-ttu-id="44691-277">Haga clic en Generar pagos.</span><span class="sxs-lookup"><span data-stu-id="44691-277">Click Generate payments.</span></span>
15. <span data-ttu-id="44691-278">En el campo Forma de pago, escriba un "Electrónica".</span><span class="sxs-lookup"><span data-stu-id="44691-278">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="44691-279">Electrónica</span><span class="sxs-lookup"><span data-stu-id="44691-279">Electronic</span></span>  
16. <span data-ttu-id="44691-280">En el campo Nombre, escriba "Pagos".</span><span class="sxs-lookup"><span data-stu-id="44691-280">In the File name field, type 'Payments'.</span></span>
    * <span data-ttu-id="44691-281">Por ejemplo, escriba Pagos.</span><span class="sxs-lookup"><span data-stu-id="44691-281">For example, type Payments.</span></span>  
17. <span data-ttu-id="44691-282">En el campo Cuenta bancaria, escriba "GBSI OPER".</span><span class="sxs-lookup"><span data-stu-id="44691-282">In the Bank account field, type 'GBSI OPER'.</span></span>
    * <span data-ttu-id="44691-283">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="44691-283">GBSI OPER</span></span>  
18. <span data-ttu-id="44691-284">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="44691-284">Click OK.</span></span>
19. <span data-ttu-id="44691-285">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="44691-285">Click OK.</span></span>
    * <span data-ttu-id="44691-286">Revise la hoja de trabajo creada, incluidos los detalles de líneas de pago así como los totales para cada código de divisa usado en este mensaje de pago.</span><span class="sxs-lookup"><span data-stu-id="44691-286">Review the created worksheet, including details of payment lines as well as totals for each currency code used in this payment message.</span></span>  


