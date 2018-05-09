--- 
title: "Crear el formato para usar archivos de gestión de documentos en las salidas de formato"
description: "En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema, o a un rol de desarrollador de informes electrónicos, puede configurar un formato de informe electrónico (ER) para usar archivos de gestión de documentos (adjuntos) en formato ER."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: a8463427ac5a15b27d4ff81ef5fb6dc59025321a
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---
# <a name="create-format-to-use-document-management-files-in-format-outputs"></a><span data-ttu-id="61897-103">Crear el formato para usar archivos de gestión de documentos en las salidas de formato</span><span class="sxs-lookup"><span data-stu-id="61897-103">Create format to use Document Management files in format outputs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="61897-104">En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema, o a un rol de desarrollador de informes electrónicos, puede configurar un formato de informe electrónico (ER) para usar archivos de gestión de documentos (adjuntos) en formato ER.</span><span class="sxs-lookup"><span data-stu-id="61897-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="61897-105">Estos pasos se pueden llevar a cabo en cualquier empresa.</span><span class="sxs-lookup"><span data-stu-id="61897-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="61897-106">Para completar estos pasos, primero debe completar los pasos en el procedimiento "ER Uso de archivos de gestión de documentos en formatos de salida (Parte 2: Aumentar el modelo de datos)”.</span><span class="sxs-lookup"><span data-stu-id="61897-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 2: Extend data model” procedure.</span></span>

<span data-ttu-id="61897-107">Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="61897-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-format-to-process-invoices"></a><span data-ttu-id="61897-108">Cree un formato para procesar facturas</span><span class="sxs-lookup"><span data-stu-id="61897-108">Create a format to process invoices</span></span>
1. <span data-ttu-id="61897-109">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="61897-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="61897-110">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="61897-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="61897-111">En el árbol, expanda el “Modelo de factura del cliente”.</span><span class="sxs-lookup"><span data-stu-id="61897-111">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="61897-112">En el árbol, seleccione “Modelo de factura de cliente\Modelo de factura de cliente (importación)”.</span><span class="sxs-lookup"><span data-stu-id="61897-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
    * <span data-ttu-id="61897-113">Creará un formato para generar mensajes electrónicos con información sobre cualquier archivo que se haya adjuntado a un pedido de ventas relacionado con una factura que se procese electrónicamente.</span><span class="sxs-lookup"><span data-stu-id="61897-113">You will create a format to generate electronic messages with information about any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
5. <span data-ttu-id="61897-114">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="61897-114">Click Create configuration to open the drop dialog.</span></span>
6. <span data-ttu-id="61897-115">En el campo Nuevo, introduzca "Formato basado en el modelo de datos del modelo de factura de Cliente (cliente)”.</span><span class="sxs-lookup"><span data-stu-id="61897-115">In the New field, enter 'Format based on data model Customer invoice model (custom)'.</span></span>
7. <span data-ttu-id="61897-116">En el campo Nombre, introduzca “Mensaje de ejemplo de factura electrónica”.</span><span class="sxs-lookup"><span data-stu-id="61897-116">In the Name field, type 'Electronic invoice sample message'.</span></span>
    * <span data-ttu-id="61897-117">Mensaje de ejemplo de factura electrónica</span><span class="sxs-lookup"><span data-stu-id="61897-117">Electronic invoice sample message</span></span>  
8. <span data-ttu-id="61897-118">En el campo definición del modelo de Datos, introduzca o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="61897-118">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="61897-119">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="61897-119">InvoiceCustomer</span></span>  
9. <span data-ttu-id="61897-120">Haga clic en Crear configuración.</span><span class="sxs-lookup"><span data-stu-id="61897-120">Click Create configuration.</span></span>

## <a name="design-a-format-to-populate-attachments-into-generating-a-message-in-mime-format"></a><span data-ttu-id="61897-121">Diseñe un formato para rellenar los adjuntos y generar un mensaje en formato MIME</span><span class="sxs-lookup"><span data-stu-id="61897-121">Design a format to populate attachments into generating a message in MIME format</span></span>
1. <span data-ttu-id="61897-122">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="61897-122">Click Designer.</span></span>
2. <span data-ttu-id="61897-123">Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="61897-123">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="61897-124">En el árbol, seleccione XML\Elemento.</span><span class="sxs-lookup"><span data-stu-id="61897-124">In the tree, select 'XML\Element'.</span></span>
4. <span data-ttu-id="61897-125">En el campo Nombre, introduzca "Factura".</span><span class="sxs-lookup"><span data-stu-id="61897-125">In the Name field, type 'Invoice'.</span></span>
    * <span data-ttu-id="61897-126">Factura</span><span class="sxs-lookup"><span data-stu-id="61897-126">Invoice</span></span>  
5. <span data-ttu-id="61897-127">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="61897-127">Click OK.</span></span>
6. <span data-ttu-id="61897-128">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="61897-128">Click Add to open the drop dialog.</span></span>
7. <span data-ttu-id="61897-129">En el árbol, seleccione XML\Atributo.</span><span class="sxs-lookup"><span data-stu-id="61897-129">In the tree, select 'XML\Attribute'.</span></span>
8. <span data-ttu-id="61897-130">En el campo Nombre, introduzca "SalesOrder".</span><span class="sxs-lookup"><span data-stu-id="61897-130">In the Name field, type 'SalesOrder'.</span></span>
    * <span data-ttu-id="61897-131">SalesOrder</span><span class="sxs-lookup"><span data-stu-id="61897-131">SalesOrder</span></span>  
9. <span data-ttu-id="61897-132">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="61897-132">Click OK.</span></span>
10. <span data-ttu-id="61897-133">Haga clic en Agregar atributos.</span><span class="sxs-lookup"><span data-stu-id="61897-133">Click Add Attribute.</span></span>
11. <span data-ttu-id="61897-134">En el campo Nombre, introduzca "InvoiceNumber".</span><span class="sxs-lookup"><span data-stu-id="61897-134">In the Name field, type 'InvoiceNumber'.</span></span>
    * <span data-ttu-id="61897-135">InvoiceNumber</span><span class="sxs-lookup"><span data-stu-id="61897-135">InvoiceNumber</span></span>  
12. <span data-ttu-id="61897-136">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="61897-136">Click OK.</span></span>
13. <span data-ttu-id="61897-137">Haga clic en Agregar atributos.</span><span class="sxs-lookup"><span data-stu-id="61897-137">Click Add Attribute.</span></span>
14. <span data-ttu-id="61897-138">En el campo Nombre, introduzca 'InvoiceAmount'.</span><span class="sxs-lookup"><span data-stu-id="61897-138">In the Name field, type 'InvoiceAmount'.</span></span>
    * <span data-ttu-id="61897-139">InvoiceAmount</span><span class="sxs-lookup"><span data-stu-id="61897-139">InvoiceAmount</span></span>  
15. <span data-ttu-id="61897-140">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="61897-140">Click OK.</span></span>
16. <span data-ttu-id="61897-141">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="61897-141">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="61897-142">En el árbol, seleccione XML\Elemento.</span><span class="sxs-lookup"><span data-stu-id="61897-142">In the tree, select 'XML\Element'.</span></span>
18. <span data-ttu-id="61897-143">En el campo Nombre, introduzca "EnclosedDocs".</span><span class="sxs-lookup"><span data-stu-id="61897-143">In the Name field, type 'EnclosedDocs'.</span></span>
    * <span data-ttu-id="61897-144">EnclosedDocs</span><span class="sxs-lookup"><span data-stu-id="61897-144">EnclosedDocs</span></span>  
19. <span data-ttu-id="61897-145">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="61897-145">Click OK.</span></span>
20. <span data-ttu-id="61897-146">En el árbol, seleccione “Invoice\EnclosedDocs”.</span><span class="sxs-lookup"><span data-stu-id="61897-146">In the tree, select 'Invoice\EnclosedDocs'.</span></span>
21. <span data-ttu-id="61897-147">Haga clic en Agregar elemento.</span><span class="sxs-lookup"><span data-stu-id="61897-147">Click Add Element.</span></span>
22. <span data-ttu-id="61897-148">En el campo Nombre, introduzca "Documento".</span><span class="sxs-lookup"><span data-stu-id="61897-148">In the Name field, type 'Document'.</span></span>
    * <span data-ttu-id="61897-149">Documento</span><span class="sxs-lookup"><span data-stu-id="61897-149">Document</span></span>  
23. <span data-ttu-id="61897-150">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="61897-150">Click OK.</span></span>
24. <span data-ttu-id="61897-151">En el árbol, seleccione “Invoice\EnclosedDocs\Document”.</span><span class="sxs-lookup"><span data-stu-id="61897-151">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
25. <span data-ttu-id="61897-152">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="61897-152">Click Add to open the drop dialog.</span></span>
26. <span data-ttu-id="61897-153">En el árbol, seleccione XML\Atributo.</span><span class="sxs-lookup"><span data-stu-id="61897-153">In the tree, select 'XML\Attribute'.</span></span>
27. <span data-ttu-id="61897-154">En el campo Nombre, introduzca "FileName".</span><span class="sxs-lookup"><span data-stu-id="61897-154">In the Name field, type 'FileName'.</span></span>
    * <span data-ttu-id="61897-155">FileName</span><span class="sxs-lookup"><span data-stu-id="61897-155">FileName</span></span>  
28. <span data-ttu-id="61897-156">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="61897-156">Click OK.</span></span>
29. <span data-ttu-id="61897-157">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="61897-157">Click Add to open the drop dialog.</span></span>
30. <span data-ttu-id="61897-158">En el árbol, seleccione XML\Elemento.</span><span class="sxs-lookup"><span data-stu-id="61897-158">In the tree, select 'XML\Element'.</span></span>
31. <span data-ttu-id="61897-159">En el campo Nombre, introduzca "FileContent".</span><span class="sxs-lookup"><span data-stu-id="61897-159">In the Name field, type 'FileContent'.</span></span>
    * <span data-ttu-id="61897-160">FileContent</span><span class="sxs-lookup"><span data-stu-id="61897-160">FileContent</span></span>  
32. <span data-ttu-id="61897-161">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="61897-161">Click OK.</span></span>
33. <span data-ttu-id="61897-162">En el árbol, seleccione “Invoice\EnclosedDocs\Document\FileContent”.</span><span class="sxs-lookup"><span data-stu-id="61897-162">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent'.</span></span>
34. <span data-ttu-id="61897-163">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="61897-163">Click Add to open the drop dialog.</span></span>
35. <span data-ttu-id="61897-164">En el árbol, seleccione 'Text\Base64'.</span><span class="sxs-lookup"><span data-stu-id="61897-164">In the tree, select 'Text\Base64'.</span></span>
36. <span data-ttu-id="61897-165">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="61897-165">Click OK.</span></span>

## <a name="map-format-elements-to-data-model-as-data-source"></a><span data-ttu-id="61897-166">Asigne elementos de formato al modelo de datos como origen de datos </span><span class="sxs-lookup"><span data-stu-id="61897-166">Map format elements to data model as data source</span></span>
1. <span data-ttu-id="61897-167">En el árbol, seleccione “Invoice\SalesOrder”.</span><span class="sxs-lookup"><span data-stu-id="61897-167">In the tree, select 'Invoice\SalesOrder'.</span></span>
2. <span data-ttu-id="61897-168">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="61897-168">Click the Mapping tab.</span></span>
3. <span data-ttu-id="61897-169">En el árbol , expanda "modelo".</span><span class="sxs-lookup"><span data-stu-id="61897-169">In the tree, expand 'model'.</span></span>
4. <span data-ttu-id="61897-170">En el árbol, seleccione “model\Sales order number(SalesId)".</span><span class="sxs-lookup"><span data-stu-id="61897-170">In the tree, select 'model\Sales order number(SalesId)'.</span></span>
5. <span data-ttu-id="61897-171">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="61897-171">Click Bind.</span></span>
6. <span data-ttu-id="61897-172">En el árbol, seleccione “Invoice\InvoiceNumber”.</span><span class="sxs-lookup"><span data-stu-id="61897-172">In the tree, select 'Invoice\InvoiceNumber'.</span></span>
7. <span data-ttu-id="61897-173">En el árbol, expanda "model\Base invoice(InvoiceBase)".</span><span class="sxs-lookup"><span data-stu-id="61897-173">In the tree, expand 'model\Base invoice(InvoiceBase)'.</span></span>
8. <span data-ttu-id="61897-174">En el árbol, seleccione “model\Base invoice(InvoiceBase)\Invoice number(Id)”.</span><span class="sxs-lookup"><span data-stu-id="61897-174">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice number(Id)'.</span></span>
9. <span data-ttu-id="61897-175">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="61897-175">Click Bind.</span></span>
10. <span data-ttu-id="61897-176">En el árbol, seleccione “Invoice\InvoiceAmount".</span><span class="sxs-lookup"><span data-stu-id="61897-176">In the tree, select 'Invoice\InvoiceAmount'.</span></span>
11. <span data-ttu-id="61897-177">En el árbol, seleccione “model\Base invoice(InvoiceBase)\Invoice amount(Amount)”.</span><span class="sxs-lookup"><span data-stu-id="61897-177">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice amount(Amount)'.</span></span>
12. <span data-ttu-id="61897-178">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="61897-178">Click Bind.</span></span>
13. <span data-ttu-id="61897-179">En el árbol, expanda el “model\Invoice attachments".</span><span class="sxs-lookup"><span data-stu-id="61897-179">In the tree, expand 'model\Invoice attachments'.</span></span>
14. <span data-ttu-id="61897-180">En el árbol, seleccione “model\Invoice attachments\File content".</span><span class="sxs-lookup"><span data-stu-id="61897-180">In the tree, select 'model\Invoice attachments\File content'.</span></span>
15. <span data-ttu-id="61897-181">En el árbol, seleccione “Invoice\EnclosedDocs\Document\FileContent\Base64”.</span><span class="sxs-lookup"><span data-stu-id="61897-181">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent\Base64'.</span></span>
16. <span data-ttu-id="61897-182">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="61897-182">Click Bind.</span></span>
17. <span data-ttu-id="61897-183">En el árbol, seleccione “model\Facturar adjuntos\Nombre de archivo”.</span><span class="sxs-lookup"><span data-stu-id="61897-183">In the tree, select 'model\Invoice attachments\File name'.</span></span>
18. <span data-ttu-id="61897-184">En el árbol, seleccione “Invoice\EnclosedDocs\Document\FileName”.</span><span class="sxs-lookup"><span data-stu-id="61897-184">In the tree, select 'Invoice\EnclosedDocs\Document\FileName'.</span></span>
19. <span data-ttu-id="61897-185">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="61897-185">Click Bind.</span></span>
20. <span data-ttu-id="61897-186">En el árbol, seleccione “model\Invoice attachments”.</span><span class="sxs-lookup"><span data-stu-id="61897-186">In the tree, select 'model\Invoice attachments'.</span></span>
21. <span data-ttu-id="61897-187">En el árbol, seleccione “Invoice\EnclosedDocs\Document”.</span><span class="sxs-lookup"><span data-stu-id="61897-187">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
22. <span data-ttu-id="61897-188">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="61897-188">Click Bind.</span></span>
23. <span data-ttu-id="61897-189">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="61897-189">Click Save.</span></span>
24. <span data-ttu-id="61897-190">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="61897-190">Close the page.</span></span>


