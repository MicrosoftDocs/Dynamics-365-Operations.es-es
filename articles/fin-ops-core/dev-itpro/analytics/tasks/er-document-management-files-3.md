---
title: 'Informe electrónico Usar archivos de gestión de documentos en las salidas de formato (Parte 3: Creación del formato)'
description: Este tema describe cómo configurar un formato de informes electrónicos para utilizar archivos de administración de documentos en la salida de informes electrónicos. (Parte 3)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1ec1ebc15cd980734aebec63d6758404868c1e36
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559758"
---
# <a name="er-use-document-management-files-in-format-outputs-part-3---create-format"></a><span data-ttu-id="3f6f6-104">Informe electrónico Usar archivos de gestión de documentos en las salidas de formato (Parte 3: Creación del formato)</span><span class="sxs-lookup"><span data-stu-id="3f6f6-104">ER Use Document Management files in format outputs (Part 3 - Create format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3f6f6-105">En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema, o a un rol de desarrollador de informes electrónicos, puede configurar un formato de informe electrónico (ER) para usar archivos de gestión de documentos (adjuntos) en formato ER.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="3f6f6-106">Estos pasos se pueden llevar a cabo en cualquier empresa.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="3f6f6-107">Para completar estos pasos, primero debe completar los pasos en el procedimiento "ER Uso de archivos de gestión de documentos en formatos de salida (Parte 2: Aumentar el modelo de datos)”.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 2: Extend data model" procedure.</span></span>

<span data-ttu-id="3f6f6-108">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-format-to-process-invoices"></a><span data-ttu-id="3f6f6-109">Cree un formato para procesar facturas</span><span class="sxs-lookup"><span data-stu-id="3f6f6-109">Create a format to process invoices</span></span>
1. <span data-ttu-id="3f6f6-110">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="3f6f6-111">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="3f6f6-112">En el árbol, expanda el “Modelo de factura del cliente”.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-112">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="3f6f6-113">En el árbol, seleccione “Modelo de factura de cliente\Modelo de factura de cliente (importación)”.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-113">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
    * <span data-ttu-id="3f6f6-114">Creará un formato para generar mensajes electrónicos con información sobre cualquier archivo que se haya adjuntado a un pedido de ventas relacionado con una factura que se procese electrónicamente.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-114">You will create a format to generate electronic messages with information about any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
5. <span data-ttu-id="3f6f6-115">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-115">Click Create configuration to open the drop dialog.</span></span>
6. <span data-ttu-id="3f6f6-116">En el campo Nuevo, introduzca "Formato basado en el modelo de datos del modelo de factura de Cliente (cliente)”.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-116">In the New field, enter 'Format based on data model Customer invoice model (custom)'.</span></span>
7. <span data-ttu-id="3f6f6-117">En el campo Nombre, introduzca “Mensaje de ejemplo de factura electrónica”.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-117">In the Name field, type 'Electronic invoice sample message'.</span></span>
    * <span data-ttu-id="3f6f6-118">Mensaje de ejemplo de factura electrónica</span><span class="sxs-lookup"><span data-stu-id="3f6f6-118">Electronic invoice sample message</span></span>  
8. <span data-ttu-id="3f6f6-119">En el campo definición del modelo de Datos, introduzca o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-119">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="3f6f6-120">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="3f6f6-120">InvoiceCustomer</span></span>  
9. <span data-ttu-id="3f6f6-121">Haga clic en Crear configuración.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-121">Click Create configuration.</span></span>

## <a name="design-a-format-to-populate-attachments-into-generating-a-message-in-mime-format"></a><span data-ttu-id="3f6f6-122">Diseñe un formato para rellenar los adjuntos y generar un mensaje en formato MIME</span><span class="sxs-lookup"><span data-stu-id="3f6f6-122">Design a format to populate attachments into generating a message in MIME format</span></span>
1. <span data-ttu-id="3f6f6-123">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-123">Click Designer.</span></span>
2. <span data-ttu-id="3f6f6-124">Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-124">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="3f6f6-125">En el árbol, seleccione XML\Elemento.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-125">In the tree, select 'XML\Element'.</span></span>
4. <span data-ttu-id="3f6f6-126">En el campo Nombre, introduzca "Factura".</span><span class="sxs-lookup"><span data-stu-id="3f6f6-126">In the Name field, type 'Invoice'.</span></span>
    * <span data-ttu-id="3f6f6-127">Factura</span><span class="sxs-lookup"><span data-stu-id="3f6f6-127">Invoice</span></span>  
5. <span data-ttu-id="3f6f6-128">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3f6f6-128">Click OK.</span></span>
6. <span data-ttu-id="3f6f6-129">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-129">Click Add to open the drop dialog.</span></span>
7. <span data-ttu-id="3f6f6-130">En el árbol, seleccione XML\Atributo.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-130">In the tree, select 'XML\Attribute'.</span></span>
8. <span data-ttu-id="3f6f6-131">En el campo Nombre, introduzca "SalesOrder".</span><span class="sxs-lookup"><span data-stu-id="3f6f6-131">In the Name field, type 'SalesOrder'.</span></span>
    * <span data-ttu-id="3f6f6-132">SalesOrder</span><span class="sxs-lookup"><span data-stu-id="3f6f6-132">SalesOrder</span></span>  
9. <span data-ttu-id="3f6f6-133">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3f6f6-133">Click OK.</span></span>
10. <span data-ttu-id="3f6f6-134">Haga clic en Agregar atributos.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-134">Click Add Attribute.</span></span>
11. <span data-ttu-id="3f6f6-135">En el campo Nombre, introduzca "InvoiceNumber".</span><span class="sxs-lookup"><span data-stu-id="3f6f6-135">In the Name field, type 'InvoiceNumber'.</span></span>
    * <span data-ttu-id="3f6f6-136">InvoiceNumber</span><span class="sxs-lookup"><span data-stu-id="3f6f6-136">InvoiceNumber</span></span>  
12. <span data-ttu-id="3f6f6-137">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3f6f6-137">Click OK.</span></span>
13. <span data-ttu-id="3f6f6-138">Haga clic en Agregar atributos.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-138">Click Add Attribute.</span></span>
14. <span data-ttu-id="3f6f6-139">En el campo Nombre, introduzca 'InvoiceAmount'.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-139">In the Name field, type 'InvoiceAmount'.</span></span>
    * <span data-ttu-id="3f6f6-140">InvoiceAmount</span><span class="sxs-lookup"><span data-stu-id="3f6f6-140">InvoiceAmount</span></span>  
15. <span data-ttu-id="3f6f6-141">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3f6f6-141">Click OK.</span></span>
16. <span data-ttu-id="3f6f6-142">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-142">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="3f6f6-143">En el árbol, seleccione XML\Elemento.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-143">In the tree, select 'XML\Element'.</span></span>
18. <span data-ttu-id="3f6f6-144">En el campo Nombre, introduzca "EnclosedDocs".</span><span class="sxs-lookup"><span data-stu-id="3f6f6-144">In the Name field, type 'EnclosedDocs'.</span></span>
    * <span data-ttu-id="3f6f6-145">EnclosedDocs</span><span class="sxs-lookup"><span data-stu-id="3f6f6-145">EnclosedDocs</span></span>  
19. <span data-ttu-id="3f6f6-146">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3f6f6-146">Click OK.</span></span>
20. <span data-ttu-id="3f6f6-147">En el árbol, seleccione “Invoice\EnclosedDocs”.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-147">In the tree, select 'Invoice\EnclosedDocs'.</span></span>
21. <span data-ttu-id="3f6f6-148">Haga clic en Agregar elemento.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-148">Click Add Element.</span></span>
22. <span data-ttu-id="3f6f6-149">En el campo Nombre, introduzca "Documento".</span><span class="sxs-lookup"><span data-stu-id="3f6f6-149">In the Name field, type 'Document'.</span></span>
    * <span data-ttu-id="3f6f6-150">Documento</span><span class="sxs-lookup"><span data-stu-id="3f6f6-150">Document</span></span>  
23. <span data-ttu-id="3f6f6-151">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3f6f6-151">Click OK.</span></span>
24. <span data-ttu-id="3f6f6-152">En el árbol, seleccione “Invoice\EnclosedDocs\Document”.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-152">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
25. <span data-ttu-id="3f6f6-153">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-153">Click Add to open the drop dialog.</span></span>
26. <span data-ttu-id="3f6f6-154">En el árbol, seleccione XML\Atributo.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-154">In the tree, select 'XML\Attribute'.</span></span>
27. <span data-ttu-id="3f6f6-155">En el campo Nombre, introduzca "FileName".</span><span class="sxs-lookup"><span data-stu-id="3f6f6-155">In the Name field, type 'FileName'.</span></span>
    * <span data-ttu-id="3f6f6-156">FileName</span><span class="sxs-lookup"><span data-stu-id="3f6f6-156">FileName</span></span>  
28. <span data-ttu-id="3f6f6-157">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3f6f6-157">Click OK.</span></span>
29. <span data-ttu-id="3f6f6-158">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-158">Click Add to open the drop dialog.</span></span>
30. <span data-ttu-id="3f6f6-159">En el árbol, seleccione XML\Elemento.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-159">In the tree, select 'XML\Element'.</span></span>
31. <span data-ttu-id="3f6f6-160">En el campo Nombre, introduzca "FileContent".</span><span class="sxs-lookup"><span data-stu-id="3f6f6-160">In the Name field, type 'FileContent'.</span></span>
    * <span data-ttu-id="3f6f6-161">FileContent</span><span class="sxs-lookup"><span data-stu-id="3f6f6-161">FileContent</span></span>  
32. <span data-ttu-id="3f6f6-162">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3f6f6-162">Click OK.</span></span>
33. <span data-ttu-id="3f6f6-163">En el árbol, seleccione “Invoice\EnclosedDocs\Document\FileContent”.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-163">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent'.</span></span>
34. <span data-ttu-id="3f6f6-164">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-164">Click Add to open the drop dialog.</span></span>
35. <span data-ttu-id="3f6f6-165">En el árbol, seleccione 'Text\Base64'.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-165">In the tree, select 'Text\Base64'.</span></span>
36. <span data-ttu-id="3f6f6-166">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3f6f6-166">Click OK.</span></span>

## <a name="map-format-elements-to-data-model-as-data-source"></a><span data-ttu-id="3f6f6-167">Asigne elementos de formato al modelo de datos como origen de datos </span><span class="sxs-lookup"><span data-stu-id="3f6f6-167">Map format elements to data model as data source</span></span>
1. <span data-ttu-id="3f6f6-168">En el árbol, seleccione “Invoice\SalesOrder”.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-168">In the tree, select 'Invoice\SalesOrder'.</span></span>
2. <span data-ttu-id="3f6f6-169">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-169">Click the Mapping tab.</span></span>
3. <span data-ttu-id="3f6f6-170">En el árbol , expanda "modelo".</span><span class="sxs-lookup"><span data-stu-id="3f6f6-170">In the tree, expand 'model'.</span></span>
4. <span data-ttu-id="3f6f6-171">En el árbol, seleccione “model\Sales order number(SalesId)".</span><span class="sxs-lookup"><span data-stu-id="3f6f6-171">In the tree, select 'model\Sales order number(SalesId)'.</span></span>
5. <span data-ttu-id="3f6f6-172">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-172">Click Bind.</span></span>
6. <span data-ttu-id="3f6f6-173">En el árbol, seleccione “Invoice\InvoiceNumber”.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-173">In the tree, select 'Invoice\InvoiceNumber'.</span></span>
7. <span data-ttu-id="3f6f6-174">En el árbol, expanda "model\Base invoice(InvoiceBase)".</span><span class="sxs-lookup"><span data-stu-id="3f6f6-174">In the tree, expand 'model\Base invoice(InvoiceBase)'.</span></span>
8. <span data-ttu-id="3f6f6-175">En el árbol, seleccione “model\Base invoice(InvoiceBase)\Invoice number(Id)”.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-175">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice number(Id)'.</span></span>
9. <span data-ttu-id="3f6f6-176">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-176">Click Bind.</span></span>
10. <span data-ttu-id="3f6f6-177">En el árbol, seleccione “Invoice\InvoiceAmount".</span><span class="sxs-lookup"><span data-stu-id="3f6f6-177">In the tree, select 'Invoice\InvoiceAmount'.</span></span>
11. <span data-ttu-id="3f6f6-178">En el árbol, seleccione “model\Base invoice(InvoiceBase)\Invoice amount(Amount)”.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-178">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice amount(Amount)'.</span></span>
12. <span data-ttu-id="3f6f6-179">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-179">Click Bind.</span></span>
13. <span data-ttu-id="3f6f6-180">En el árbol, expanda el “model\Invoice attachments".</span><span class="sxs-lookup"><span data-stu-id="3f6f6-180">In the tree, expand 'model\Invoice attachments'.</span></span>
14. <span data-ttu-id="3f6f6-181">En el árbol, seleccione “model\Invoice attachments\File content".</span><span class="sxs-lookup"><span data-stu-id="3f6f6-181">In the tree, select 'model\Invoice attachments\File content'.</span></span>
15. <span data-ttu-id="3f6f6-182">En el árbol, seleccione “Invoice\EnclosedDocs\Document\FileContent\Base64”.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-182">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent\Base64'.</span></span>
16. <span data-ttu-id="3f6f6-183">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-183">Click Bind.</span></span>
17. <span data-ttu-id="3f6f6-184">En el árbol, seleccione “model\Facturar adjuntos\Nombre de archivo”.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-184">In the tree, select 'model\Invoice attachments\File name'.</span></span>
18. <span data-ttu-id="3f6f6-185">En el árbol, seleccione “Invoice\EnclosedDocs\Document\FileName”.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-185">In the tree, select 'Invoice\EnclosedDocs\Document\FileName'.</span></span>
19. <span data-ttu-id="3f6f6-186">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-186">Click Bind.</span></span>
20. <span data-ttu-id="3f6f6-187">En el árbol, seleccione “model\Invoice attachments”.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-187">In the tree, select 'model\Invoice attachments'.</span></span>
21. <span data-ttu-id="3f6f6-188">En el árbol, seleccione “Invoice\EnclosedDocs\Document”.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-188">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
22. <span data-ttu-id="3f6f6-189">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-189">Click Bind.</span></span>
23. <span data-ttu-id="3f6f6-190">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-190">Click Save.</span></span>
24. <span data-ttu-id="3f6f6-191">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3f6f6-191">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]