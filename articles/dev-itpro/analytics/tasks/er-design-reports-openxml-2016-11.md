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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 882799e12daf9a3b7b530201c913b8f921fb2ed3
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="design-a-configuration-for-generating-reports-in-openxml-format-for-electronic-reporting-er"></a><span data-ttu-id="c4bfe-103">Diseñar una configuración para generar informes con formato OpenXML para informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="c4bfe-103">Design a configuration for generating reports in OpenXML format for electronic reporting (ER)</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c4bfe-104">En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o desarrollador de informes electrónicos puede crear una nueva configuración de informes electrónicos que contenga una plantilla para generar documentos electrónicos en formato OPENXML.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a template for generating electronic documents in OPENXML format.</span></span> <span data-ttu-id="c4bfe-105">Esta configuración se usará para procesar los pagos de proveedor.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-105">This configuration will be used for processing vendor payments.</span></span>



<span data-ttu-id="c4bfe-106">En este ejemplo, creará una configuración para la empresa de demostración, Litware, Inc. Estos pasos se pueden realizar en empresa GBSI.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in GBSI company.</span></span>



<span data-ttu-id="c4bfe-107">Para completar estos pasos, primero debe completar los pasos del procedimiento Creación y activación de un proveedor de configuraciones.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="c4bfe-108">También debe descargar y guardar el archivo de Microsoft Excel, [Plantilla de informe de pago](https://go.microsoft.com/fwlink/?linkid=862266).</span><span class="sxs-lookup"><span data-stu-id="c4bfe-108">You must also download and save the Microsoft Excel file, [Template of Payment Report](https://go.microsoft.com/fwlink/?linkid=862266).</span></span> 

## <a name="upload-the-payments-data-model-configuration"></a><span data-ttu-id="c4bfe-109">Cargar la configuración del modelo de datos de pagos</span><span class="sxs-lookup"><span data-stu-id="c4bfe-109">Upload the Payments data model configuration</span></span>
1. <span data-ttu-id="c4bfe-110">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="c4bfe-111">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="c4bfe-112">Seleccione el proveedor de la configuración de la empresa de ejemplo, Litware, Inc. Si no ve a este proveedor de configuración, primero debe completar los pasos del procedimiento "Creación y activación de un proveedor de configuraciones".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-112">Select the configuration provider for sample company, Litware, Inc. If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
3. <span data-ttu-id="c4bfe-113">Haga clic en Definir como activo.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-113">Click Set active.</span></span>
4. <span data-ttu-id="c4bfe-114">Haga clic en Repositorios.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-114">Click Repositories.</span></span>
    * <span data-ttu-id="c4bfe-115">Seleccione un repositorio para el tipo de recursos de operaciones, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-115">Select a repository for the Operations Resources type, if available.</span></span> <span data-ttu-id="c4bfe-116">Si está disponible, omita los siguientes pasos acerca de la creación de un nuevo repositorio.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-116">If its available, skip the following steps about creating a new repository.</span></span>  
5. <span data-ttu-id="c4bfe-117">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-117">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="c4bfe-118">En el campo Tipo de repositorio de configuración, escriba "Recursos de Operations".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-118">In the Configuration repository type field, enter 'Operations resources'.</span></span>
7. <span data-ttu-id="c4bfe-119">Haga clic en Crear repositorio.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-119">Click Create repository.</span></span>
8. <span data-ttu-id="c4bfe-120">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="c4bfe-120">Click OK.</span></span>
9. <span data-ttu-id="c4bfe-121">Haga clic en Abrir.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-121">Click Open.</span></span>
10. <span data-ttu-id="c4bfe-122">En el árbol, seleccione "Modelo de pago".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-122">In the tree, select 'Payment model'.</span></span>
11. <span data-ttu-id="c4bfe-123">Haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-123">Click Import.</span></span>
    * <span data-ttu-id="c4bfe-124">Importe este modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-124">Import this data model.</span></span> <span data-ttu-id="c4bfe-125">Se usará como origen de datos en una nueva configuración de formato.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-125">It will be used as a data source in a new format configuration.</span></span> <span data-ttu-id="c4bfe-126">Omita este paso si esta configuración ya se ha importado.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-126">Skip this step if this configuration has been already imported.</span></span>  
12. <span data-ttu-id="c4bfe-127">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-127">Click Yes.</span></span>
13. <span data-ttu-id="c4bfe-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-128">Close the page.</span></span>
14. <span data-ttu-id="c4bfe-129">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-129">Close the page.</span></span>

## <a name="create-a-new-format-configuration"></a><span data-ttu-id="c4bfe-130">Creación de una configuración de formato nueva</span><span class="sxs-lookup"><span data-stu-id="c4bfe-130">Create a new format configuration</span></span>
1. <span data-ttu-id="c4bfe-131">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-131">Click Reporting configurations.</span></span>
2. <span data-ttu-id="c4bfe-132">En el árbol, seleccione "Modelo de pago".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-132">In the tree, select 'Payment model'.</span></span>
3. <span data-ttu-id="c4bfe-133">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-133">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="c4bfe-134">En el campo Nuevo, especifique "Formato basado en modelo de datos PaymentModel".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-134">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
    * <span data-ttu-id="c4bfe-135">Cree un formato que se base en el modelo de datos de PaymentModel.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-135">Create a format that is based on the PaymentModel data model.</span></span>  
5. <span data-ttu-id="c4bfe-136">En el campo Nombre, escriba "Informe de hoja de cálculo de muestra".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-136">In the Name field, type 'Sample worksheet report'.</span></span>
    * <span data-ttu-id="c4bfe-137">Informe de hoja de cálculo de muestra</span><span class="sxs-lookup"><span data-stu-id="c4bfe-137">Sample worksheet report</span></span>  
6. <span data-ttu-id="c4bfe-138">En el campo Descripción, escriba "Informe de hoja de cálculo para pagos de proveedores".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-138">In the Description field, type 'Sample worksheet report for vendors’ payments'.</span></span>
    * <span data-ttu-id="c4bfe-139">Informe de hoja de cálculo para pagos de proveedores.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-139">Sample worksheet report for vendors’ payments.</span></span>  
7. <span data-ttu-id="c4bfe-140">En el campo definición del modelo de Datos, introduzca o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-140">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="c4bfe-141">Seleccione la definición "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-141">Select the 'CustomerCreditTransferInitiation' definition.</span></span>  
8. <span data-ttu-id="c4bfe-142">Haga clic en Crear configuración.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-142">Click Create configuration.</span></span>

## <a name="design-a-new-document-in-openxml-worksheet-format"></a><span data-ttu-id="c4bfe-143">Diseñar un documento nuevo en formato de hoja de cálculo OPENXML</span><span class="sxs-lookup"><span data-stu-id="c4bfe-143">Design a new document in OPENXML worksheet format</span></span>
1. <span data-ttu-id="c4bfe-144">En el árbol, seleccione "Modelo de pago\Informe de hoja de cálculo de muestra".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-144">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
2. <span data-ttu-id="c4bfe-145">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-145">Click Designer.</span></span>
3. <span data-ttu-id="c4bfe-146">En el panel de acciones, haga clic en Importar.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-146">On the Action Pane, click Import.</span></span>
4. <span data-ttu-id="c4bfe-147">Haga clic en Importar desde Excel.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-147">Click Import from Excel.</span></span>
5. <span data-ttu-id="c4bfe-148">Haga clic en Archivos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-148">Click Attachments.</span></span>
    * <span data-ttu-id="c4bfe-149">Adjunte el documento de Excel existente como plantilla.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-149">Attach the existing Excel document as a template.</span></span>  
6. <span data-ttu-id="c4bfe-150">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-150">Click New.</span></span>
7. <span data-ttu-id="c4bfe-151">Haga clic en Archivo.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-151">Click File.</span></span>
    * <span data-ttu-id="c4bfe-152">Señale al archivo de Excel existente.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-152">Point to the existing Excel file.</span></span>  
8. <span data-ttu-id="c4bfe-153">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-153">Close the page.</span></span>
9. <span data-ttu-id="c4bfe-154">En el campo Plantilla, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-154">In the Template field, enter or select a value.</span></span>
    * <span data-ttu-id="c4bfe-155">Seleccione el archivo de Excel adjunto que se usará como plantilla.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-155">Select the attached Excel file to be used as a template.</span></span>  
10. <span data-ttu-id="c4bfe-156">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="c4bfe-156">Click OK.</span></span>
    * <span data-ttu-id="c4bfe-157">Tenga en cuenta que los componentes en formato ER se han creado en el formato de diseño basado en la estructura del documento de MS Excel de referencia (intervalos con nombre).</span><span class="sxs-lookup"><span data-stu-id="c4bfe-157">Note that ER format components have been created in the designing format based on the structure of the referring MS Excel document (named ranges).</span></span>  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a><span data-ttu-id="c4bfe-158">Crear un nuevo origen de datos para calcular totales por códigos de divisa</span><span class="sxs-lookup"><span data-stu-id="c4bfe-158">Create a new data source to calculate totals by currency codes</span></span>
1. <span data-ttu-id="c4bfe-159">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-159">Click the Mapping tab.</span></span>
2. <span data-ttu-id="c4bfe-160">Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-160">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="c4bfe-161">En el árbol, seleccione "Funciones\Agrupar por".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-161">In the tree, select 'Functions\Group by'.</span></span>
4. <span data-ttu-id="c4bfe-162">En el campo Nombre, escriba "PaymentByCurrency".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-162">In the Name field, type 'PaymentByCurrency'.</span></span>
    * <span data-ttu-id="c4bfe-163">PaymentByCurrency</span><span class="sxs-lookup"><span data-stu-id="c4bfe-163">PaymentByCurrency</span></span>  
5. <span data-ttu-id="c4bfe-164">Haga clic en Editar grupo por.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-164">Click Edit group by.</span></span>
6. <span data-ttu-id="c4bfe-165">En el árbol , expanda "modelo".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-165">In the tree, expand 'model'.</span></span>
7. <span data-ttu-id="c4bfe-166">En el árbol, seleccione modelo\Pagos.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-166">In the tree, select 'model\Payments'.</span></span>
8. <span data-ttu-id="c4bfe-167">Haga clic en Agregar campo a.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-167">Click Add field to.</span></span>
9. <span data-ttu-id="c4bfe-168">Haga clic en Elementos para agrupar.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-168">Click What to group.</span></span>
10. <span data-ttu-id="c4bfe-169">En el árbol, expanda modelo\Pagos.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-169">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="c4bfe-170">En el árbol, seleccione "modelo\Pagos\Divisa".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-170">In the tree, select 'model\Payments\Currency'.</span></span>
12. <span data-ttu-id="c4bfe-171">Haga clic en Agregar campo a.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-171">Click Add field to.</span></span>
13. <span data-ttu-id="c4bfe-172">Haga clic en Campos agrupados.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-172">Click Grouped fields.</span></span>
14. <span data-ttu-id="c4bfe-173">En el árbol, seleccione "modelo\Pagos\Importe ordenado(InstructedAmount)".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-173">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
15. <span data-ttu-id="c4bfe-174">Haga clic en Agregar campo a.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-174">Click Add field to.</span></span>
16. <span data-ttu-id="c4bfe-175">Haga clic en Campos de agregación.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-175">Click Aggregation fields.</span></span>
17. <span data-ttu-id="c4bfe-176">En el campo Método, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-176">In the Method field, select an option.</span></span>
    * <span data-ttu-id="c4bfe-177">Seleccione la función de agregación SUMA.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-177">Select the SUM aggregation function.</span></span>  
18. <span data-ttu-id="c4bfe-178">En el campo Nombre, escriba "TotalInstructuredAmount".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-178">In the Name field, type 'TotalInstructuredAmount'.</span></span>
    * <span data-ttu-id="c4bfe-179">TotalInstructuredAmount</span><span class="sxs-lookup"><span data-stu-id="c4bfe-179">TotalInstructuredAmount</span></span>  
19. <span data-ttu-id="c4bfe-180">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-180">Click Save.</span></span>
20. <span data-ttu-id="c4bfe-181">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-181">Close the page.</span></span>
21. <span data-ttu-id="c4bfe-182">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="c4bfe-182">Click OK.</span></span>

## <a name="map-format-components-to-data-sources"></a><span data-ttu-id="c4bfe-183">Asignar componentes de formato a orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="c4bfe-183">Map format components to data sources</span></span>
1. <span data-ttu-id="c4bfe-184">En el árbol , expanda "modelo".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-184">In the tree, expand 'model'.</span></span>
2. <span data-ttu-id="c4bfe-185">En el árbol, expanda modelo\Pagos.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-185">In the tree, expand 'model\Payments'.</span></span>
3. <span data-ttu-id="c4bfe-186">En el árbol, expanda "modelo\Pagos\Parte iniciadora(InitiatingParty)".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-186">In the tree, expand 'model\Payments\Initiating Party(InitiatingParty)'.</span></span>
4. <span data-ttu-id="c4bfe-187">En el árbol, seleccione "modelo\Pagos\Parte iniciadora(InitiatingParty)\Name".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-187">In the tree, select 'model\Payments\Initiating Party(InitiatingParty)\Name'.</span></span>
5. <span data-ttu-id="c4bfe-188">En el árbol, expanda 'Excel\ReportHeader'.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-188">In the tree, expand 'Excel\ReportHeader'.</span></span>
6. <span data-ttu-id="c4bfe-189">En el árbol, seleccione ''Excel\ReportHeader\CompanyName".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-189">In the tree, select 'Excel\ReportHeader\CompanyName'.</span></span>
7. <span data-ttu-id="c4bfe-190">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-190">Click Bind.</span></span>
8. <span data-ttu-id="c4bfe-191">En el árbol, expanda modelo\Pagos\Acreedor.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-191">In the tree, expand 'model\Payments\Creditor'.</span></span>
9. <span data-ttu-id="c4bfe-192">En el árbol, expanda "modelo\Pagos\Acreedor\Identificación".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-192">In the tree, expand 'model\Payments\Creditor\Identification'.</span></span>
10. <span data-ttu-id="c4bfe-193">En el árbol, seleccione "modelo\Pagos\Cuenta de acreedor(Creditor)\Identification\Source ID(SourceID)".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-193">In the tree, select 'model\Payments\Creditor\Identification\Source ID(SourceID)'.</span></span>
11. <span data-ttu-id="c4bfe-194">En el árbol, expanda 'Excel\PaymLines'.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-194">In the tree, expand 'Excel\PaymLines'.</span></span>
12. <span data-ttu-id="c4bfe-195">En el árbol, seleccione ''Excel\PaymLines\VendAccountName".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-195">In the tree, select 'Excel\PaymLines\VendAccountName'.</span></span>
13. <span data-ttu-id="c4bfe-196">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-196">Click Bind.</span></span>
14. <span data-ttu-id="c4bfe-197">En el árbol, seleccione modelo\Pagos\Acreedor\Nombre.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-197">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
15. <span data-ttu-id="c4bfe-198">En el árbol, seleccione ''Excel\PaymLines\VendName".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-198">In the tree, select 'Excel\PaymLines\VendName'.</span></span>
16. <span data-ttu-id="c4bfe-199">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-199">Click Bind.</span></span>
17. <span data-ttu-id="c4bfe-200">En el árbol, expanda “modelo\Pagos\Cuenta de acreedor(CreditorAccount)”.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-200">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
18. <span data-ttu-id="c4bfe-201">En el árbol, expanda “modelo\Pagos\Cuenta de acreedor(CreditorAccount)\Nombre”.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-201">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Name'.</span></span>
19. <span data-ttu-id="c4bfe-202">En el árbol, seleccione ''Excel\PaymLines\Bank".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-202">In the tree, select 'Excel\PaymLines\Bank'.</span></span>
20. <span data-ttu-id="c4bfe-203">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-203">Click Bind.</span></span>
21. <span data-ttu-id="c4bfe-204">En el árbol, seleccione "modelo\Pagos\Agente del acreedor(CreditorAgent)\Número de ruta(RoutingNumber)".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-204">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Routing Number(RoutingNumber)'.</span></span>
22. <span data-ttu-id="c4bfe-205">En el árbol, seleccione ''Excel\PaymLines\RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-205">In the tree, select 'Excel\PaymLines\RoutingNumber'.</span></span>
23. <span data-ttu-id="c4bfe-206">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-206">Click Bind.</span></span>
24. <span data-ttu-id="c4bfe-207">En el árbol, expanda “model\Payments\Creditor Account(CreditorAccount)”.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-207">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
25. <span data-ttu-id="c4bfe-208">En el árbol, expanda “model\Payments\Creditor Account(CreditorAccount)\Identification”.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-208">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)\Identification'.</span></span>
26. <span data-ttu-id="c4bfe-209">En el árbol, seleccione "modelo\Pagos\Cuenta de acreedor(CreditorAccount)\Identification\Número”.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-209">In the tree, select 'model\Payments\Creditor Account(CreditorAccount)\Identification\Number'.</span></span>
27. <span data-ttu-id="c4bfe-210">En el árbol, seleccione ''Excel\PaymLines\AccountNumber".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-210">In the tree, select 'Excel\PaymLines\AccountNumber'.</span></span>
28. <span data-ttu-id="c4bfe-211">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-211">Click Bind.</span></span>
29. <span data-ttu-id="c4bfe-212">En el árbol, seleccione "modelo\Pagos\Importe ordenado(InstructedAmount)".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-212">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
30. <span data-ttu-id="c4bfe-213">En el árbol, seleccione ''Excel\PaymLines\Débito".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-213">In the tree, select 'Excel\PaymLines\Debit'.</span></span>
31. <span data-ttu-id="c4bfe-214">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-214">Click Bind.</span></span>
32. <span data-ttu-id="c4bfe-215">En el árbol, expanda modelo\Pagos\Acreedor.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-215">In the tree, expand 'model\Payments\Creditor'.</span></span>
33. <span data-ttu-id="c4bfe-216">En el árbol, expanda “model\Payments\Creditor Account(CreditorAccount)”.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-216">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
34. <span data-ttu-id="c4bfe-217">En el árbol, expanda “modelo\Pagos\Cuenta de acreedor(CreditorAccount)”.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-217">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
35. <span data-ttu-id="c4bfe-218">En el árbol, seleccione "modelo\Pagos\Divisa".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-218">In the tree, select 'model\Payments\Currency'.</span></span>
36. <span data-ttu-id="c4bfe-219">En el árbol, seleccione ''Excel\PaymLines\Moneda".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-219">In the tree, select 'Excel\PaymLines\Currency'.</span></span>
37. <span data-ttu-id="c4bfe-220">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-220">Click Bind.</span></span>
38. <span data-ttu-id="c4bfe-221">En el árbol, expanda "PaymentByCurrency".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-221">In the tree, expand 'PaymentByCurrency'.</span></span>
39. <span data-ttu-id="c4bfe-222">En el árbol, expanda "PaymentByCurrency\agrupado".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-222">In the tree, expand 'PaymentByCurrency\grouped'.</span></span>
40. <span data-ttu-id="c4bfe-223">En el árbol, seleccione "PaymentByCurrency\agrupado\Divisa".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-223">In the tree, select 'PaymentByCurrency\grouped\Currency'.</span></span>
41. <span data-ttu-id="c4bfe-224">En el árbol, expanda "Excel\SummaryLines".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-224">In the tree, expand 'Excel\SummaryLines'.</span></span>
42. <span data-ttu-id="c4bfe-225">En el árbol, seleccione ''Excel\SummaryLines\SummaryCurrency".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-225">In the tree, select 'Excel\SummaryLines\SummaryCurrency'.</span></span>
43. <span data-ttu-id="c4bfe-226">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-226">Click Bind.</span></span>
44. <span data-ttu-id="c4bfe-227">En el árbol, expanda "PaymentByCurrency\agregado".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-227">In the tree, expand 'PaymentByCurrency\aggregated'.</span></span>
45. <span data-ttu-id="c4bfe-228">En el árbol, seleccione "PaymentByCurrency\agregado\TotalInstructuredAmount".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-228">In the tree, select 'PaymentByCurrency\aggregated\TotalInstructuredAmount'.</span></span>
46. <span data-ttu-id="c4bfe-229">En el árbol, seleccione ''Excel\SummaryLines\SummaryAmount".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-229">In the tree, select 'Excel\SummaryLines\SummaryAmount'.</span></span>
47. <span data-ttu-id="c4bfe-230">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-230">Click Bind.</span></span>
48. <span data-ttu-id="c4bfe-231">En el árbol, seleccione "PaymentByCurrency".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-231">In the tree, select 'PaymentByCurrency'.</span></span>
49. <span data-ttu-id="c4bfe-232">En el árbol, seleccione "Excel\SummaryLines".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-232">In the tree, select 'Excel\SummaryLines'.</span></span>
50. <span data-ttu-id="c4bfe-233">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-233">Click Bind.</span></span>
51. <span data-ttu-id="c4bfe-234">En el árbol, seleccione modelo\Pagos.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-234">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="c4bfe-235">En el árbol, seleccione ''Excel\PaymLines".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-235">In the tree, select 'Excel\PaymLines'.</span></span>
53. <span data-ttu-id="c4bfe-236">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-236">Click Bind.</span></span>
54. <span data-ttu-id="c4bfe-237">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-237">Click Save.</span></span>
55. <span data-ttu-id="c4bfe-238">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-238">Close the page.</span></span>

## <a name="use-the-created-configuration-for-payments-processing"></a><span data-ttu-id="c4bfe-239">Usar la configuración creada para procesar los pagos</span><span class="sxs-lookup"><span data-stu-id="c4bfe-239">Use the created configuration for payments processing</span></span>
1. <span data-ttu-id="c4bfe-240">Haga clic en Cambiar estado.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-240">Click Change status.</span></span>
2. <span data-ttu-id="c4bfe-241">Haga clic en Completar.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-241">Click Complete.</span></span>
3. <span data-ttu-id="c4bfe-242">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="c4bfe-242">Click OK.</span></span>
4. <span data-ttu-id="c4bfe-243">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-243">Close the page.</span></span>
5. <span data-ttu-id="c4bfe-244">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-244">Close the page.</span></span>
6. <span data-ttu-id="c4bfe-245">Vaya a Proveedores > Configuración de pagos > Formas de pago.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-245">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
7. <span data-ttu-id="c4bfe-246">Use el Filtro Rápido para filtrar el campo Método de pago con un valor de "Electronic".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-246">Use the Quick Filter to filter on the Method of payment field with a value of 'Electronic'.</span></span>
    * <span data-ttu-id="c4bfe-247">Electrónica</span><span class="sxs-lookup"><span data-stu-id="c4bfe-247">Electronic</span></span>  
8. <span data-ttu-id="c4bfe-248">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-248">Click Edit.</span></span>
9. <span data-ttu-id="c4bfe-249">Expanda la sección Formatos de archivo.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-249">Expand the File formats section.</span></span>
10. <span data-ttu-id="c4bfe-250">Seleccione Sí en el campo Informes electrónicos genéricos.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-250">Select Yes in the Generic electronic reporting field.</span></span>
11. <span data-ttu-id="c4bfe-251">En el campo Configuración de formato de exportación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-251">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="c4bfe-252">Seleccione la configuración "Informe de hoja de cálculo de muestra”.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-252">Select the ‘Sample worksheet report’ configuration.</span></span>  
12. <span data-ttu-id="c4bfe-253">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-253">Click Save.</span></span>
13. <span data-ttu-id="c4bfe-254">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-254">Close the page.</span></span>

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a><span data-ttu-id="c4bfe-255">Usar la configuración creada para probar el procesamiento de diarios de pago</span><span class="sxs-lookup"><span data-stu-id="c4bfe-255">Use the created configuration for testing of payment journals processing</span></span>
1. <span data-ttu-id="c4bfe-256">Vaya a Proveedores > Pagos > Diario de pagos.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-256">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="c4bfe-257">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-257">Click New.</span></span>
    * <span data-ttu-id="c4bfe-258">Crear un diario de pago nuevo.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-258">Create a new payment journal.</span></span>  
3. <span data-ttu-id="c4bfe-259">En el campo Nombre, escriba "VendPay".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-259">In the Name field, type 'VendPay'.</span></span>
    * <span data-ttu-id="c4bfe-260">VendPay</span><span class="sxs-lookup"><span data-stu-id="c4bfe-260">VendPay</span></span>  
4. <span data-ttu-id="c4bfe-261">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-261">Click Lines.</span></span>
5. <span data-ttu-id="c4bfe-262">En el campo Cuenta, especifique los valores "GB_SI_000001".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-262">In the Account field, specify the values 'GB_SI_000001'.</span></span>
    * <span data-ttu-id="c4bfe-263">GB_SI_000001</span><span class="sxs-lookup"><span data-stu-id="c4bfe-263">GB_SI_000001</span></span>  
6. <span data-ttu-id="c4bfe-264">Establezca Débito en "1000".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-264">Set Debit to '1000'.</span></span>
7. <span data-ttu-id="c4bfe-265">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-265">Click New.</span></span>
8. <span data-ttu-id="c4bfe-266">En el campo Cuenta, especifique los valores "GB_SI_000005".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-266">In the Account field, specify the values 'GB_SI_000005'.</span></span>
    * <span data-ttu-id="c4bfe-267">GB_SI_000005</span><span class="sxs-lookup"><span data-stu-id="c4bfe-267">GB_SI_000005</span></span>  
9. <span data-ttu-id="c4bfe-268">Establezca Débito en "2000".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-268">Set Debit to '2000'.</span></span>
10. <span data-ttu-id="c4bfe-269">En el campo Divisa, escriba "EUR".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-269">In the Currency field, type 'EUR'.</span></span>
    * <span data-ttu-id="c4bfe-270">EUR</span><span class="sxs-lookup"><span data-stu-id="c4bfe-270">EUR</span></span>  
11. <span data-ttu-id="c4bfe-271">En el campo Cuenta de contrapartida, especifique los valores "GBSI OPER".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-271">In the Offset account field, specify the values 'GBSI OPER'.</span></span>
    * <span data-ttu-id="c4bfe-272">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="c4bfe-272">GBSI OPER</span></span>  
12. <span data-ttu-id="c4bfe-273">En el campo Forma de pago, escriba un "Electrónica".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-273">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="c4bfe-274">Electrónica</span><span class="sxs-lookup"><span data-stu-id="c4bfe-274">Electronic</span></span>  
13. <span data-ttu-id="c4bfe-275">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-275">Click Save.</span></span>
14. <span data-ttu-id="c4bfe-276">Haga clic en Generar pagos.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-276">Click Generate payments.</span></span>
15. <span data-ttu-id="c4bfe-277">En el campo Forma de pago, escriba un "Electrónica".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-277">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="c4bfe-278">Electrónica</span><span class="sxs-lookup"><span data-stu-id="c4bfe-278">Electronic</span></span>  
16. <span data-ttu-id="c4bfe-279">En el campo Nombre, escriba "Pagos".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-279">In the File name field, type 'Payments'.</span></span>
    * <span data-ttu-id="c4bfe-280">Por ejemplo, escriba Pagos.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-280">For example, type Payments.</span></span>  
17. <span data-ttu-id="c4bfe-281">En el campo Cuenta bancaria, escriba "GBSI OPER".</span><span class="sxs-lookup"><span data-stu-id="c4bfe-281">In the Bank account field, type 'GBSI OPER'.</span></span>
    * <span data-ttu-id="c4bfe-282">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="c4bfe-282">GBSI OPER</span></span>  
18. <span data-ttu-id="c4bfe-283">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="c4bfe-283">Click OK.</span></span>
19. <span data-ttu-id="c4bfe-284">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="c4bfe-284">Click OK.</span></span>
    * <span data-ttu-id="c4bfe-285">Revise la hoja de trabajo creada, incluidos los detalles de líneas de pago así como los totales para cada código de divisa usado en este mensaje de pago.</span><span class="sxs-lookup"><span data-stu-id="c4bfe-285">Review the created worksheet, including details of payment lines as well as totals for each currency code used in this payment message.</span></span>  


