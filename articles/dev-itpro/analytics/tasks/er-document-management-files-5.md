--- 
title: "Modificar y ejecutar formatos para usar archivos de administración de documentos en la salida de ER"
description: "En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema, o a un rol de desarrollador de informes electrónicos, puede configurar un formato de informe electrónico (ER) para usar archivos de gestión de documentos (adjuntos) en formato ER."
author: NickSelin
manager: AnnBe
ms.date: 11/02/2017
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
ms.openlocfilehash: 5effbecf98e633d07f9e5eb22d3df1a12967c1e4
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---
# <a name="modify-and-run-formats-to-use-document-management-files-in-er-output"></a><span data-ttu-id="bfbe2-103">Modificar y ejecutar formatos para usar archivos de administración de documentos en la salida de ER</span><span class="sxs-lookup"><span data-stu-id="bfbe2-103">Modify and run formats to use Document Management files in ER output</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bfbe2-104">En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema, o a un rol de desarrollador de informes electrónicos, puede configurar un formato de informe electrónico (ER) para usar archivos de gestión de documentos (adjuntos) en formato ER.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="bfbe2-105">Estos pasos se pueden llevar a cabo en la empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="bfbe2-106">Para completar estos pasos, primero debe completar los pasos del procedimiento "ER Uso de gestión de documentos en formatos de salida (Parte 4: Ejecutar un formato)”.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 4): Run format” procedure.</span></span>

<span data-ttu-id="bfbe2-107">Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format"></a><span data-ttu-id="bfbe2-108">Modifique el formato para rellenar los adjuntos y generar mensajes en formato binario</span><span class="sxs-lookup"><span data-stu-id="bfbe2-108">Modify the format to populate attachments into generating messages in binary format</span></span>
1. <span data-ttu-id="bfbe2-109">Vaya a Administración de la organización > Informes electrónicos > Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="bfbe2-110">En el árbol, expanda el “Modelo de factura del cliente”.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-110">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="bfbe2-111">En el árbol, expanda el “Modelo de factura de cliente\Modelo de factura de cliente (cliente)”.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-111">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="bfbe2-112">En el árbol, seleccione “Modelo de factura de cliente\Modelo de factura de cliente (importación)\Mensaje de ejemplo de factura electrónica”.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="bfbe2-113">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-113">Click Designer.</span></span>
    * <span data-ttu-id="bfbe2-114">Se rellenará el mensaje de la factura en un formato generado como archivo XML con codificación UNICODE.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-114">You will populate the invoice message in the generating output as an XML file using UNICODE encoding.</span></span>  
6. <span data-ttu-id="bfbe2-115">Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-115">Click Add root to open the drop dialog.</span></span>
7. <span data-ttu-id="bfbe2-116">En el árbol, seleccione Común\Archivo.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-116">In the tree, select 'Common\File'.</span></span>
8. <span data-ttu-id="bfbe2-117">En el campo Nombre, introduzca "Mensaje Xml".</span><span class="sxs-lookup"><span data-stu-id="bfbe2-117">In the Name field, type 'Xml message'.</span></span>
    * <span data-ttu-id="bfbe2-118">Mensaje Xml</span><span class="sxs-lookup"><span data-stu-id="bfbe2-118">Xml message</span></span>  
9. <span data-ttu-id="bfbe2-119">En el campo Codificación, escriba "UTF-8".</span><span class="sxs-lookup"><span data-stu-id="bfbe2-119">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="bfbe2-120">UTF-8</span><span class="sxs-lookup"><span data-stu-id="bfbe2-120">UTF-8</span></span>  
10. <span data-ttu-id="bfbe2-121">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="bfbe2-121">Click OK.</span></span>
    * <span data-ttu-id="bfbe2-122">Configurar el formato de salida como archivo comprimido.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-122">Configure the generating output as a zipped file.</span></span>  
11. <span data-ttu-id="bfbe2-123">Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-123">Click Add root to open the drop dialog.</span></span>
12. <span data-ttu-id="bfbe2-124">En el árbol, seleccione "Common\Folder".</span><span class="sxs-lookup"><span data-stu-id="bfbe2-124">In the tree, select 'Common\Folder'.</span></span>
13. <span data-ttu-id="bfbe2-125">En el campo Nombre, introduzca "Formato de salida comprimido".</span><span class="sxs-lookup"><span data-stu-id="bfbe2-125">In the Name field, type 'Zip output'.</span></span>
    * <span data-ttu-id="bfbe2-126">Código postal generado</span><span class="sxs-lookup"><span data-stu-id="bfbe2-126">Zip output</span></span>  
14. <span data-ttu-id="bfbe2-127">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="bfbe2-127">Click OK.</span></span>
15. <span data-ttu-id="bfbe2-128">En el árbol, seleccione "Formato de salida comprimido".</span><span class="sxs-lookup"><span data-stu-id="bfbe2-128">In the tree, select 'Zip output'.</span></span>
    * <span data-ttu-id="bfbe2-129">Agregue adjuntos al archivo comprimido generado como archivos con nombres originales y extensiones.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-129">Add attachments to the generating zipped file as files with original names and extensions.</span></span>  
16. <span data-ttu-id="bfbe2-130">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-130">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="bfbe2-131">En el árbol, seleccione Común\Archivo.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-131">In the tree, select 'Common\File'.</span></span>
18. <span data-ttu-id="bfbe2-132">En el campo Nombre, introduzca "Archivo adjunto".</span><span class="sxs-lookup"><span data-stu-id="bfbe2-132">In the Name field, type 'Attached file'.</span></span>
    * <span data-ttu-id="bfbe2-133">Archivo adjunto</span><span class="sxs-lookup"><span data-stu-id="bfbe2-133">Attached file</span></span>  
19. <span data-ttu-id="bfbe2-134">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="bfbe2-134">Click OK.</span></span>
20. <span data-ttu-id="bfbe2-135">En el árbol, seleccione "Formato de salida comprimido\Archivo adjunto".</span><span class="sxs-lookup"><span data-stu-id="bfbe2-135">In the tree, select 'Zip output\Attached file'.</span></span>
21. <span data-ttu-id="bfbe2-136">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-136">Click Add to open the drop dialog.</span></span>
22. <span data-ttu-id="bfbe2-137">En el árbol, seleccione 'Text\Base64'.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-137">In the tree, select 'Text\Base64'.</span></span>
23. <span data-ttu-id="bfbe2-138">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="bfbe2-138">Click OK.</span></span>

## <a name="map-new-format-elements-to-data-model"></a><span data-ttu-id="bfbe2-139">Asigne nuevos elementos de formato al modelo de datos</span><span class="sxs-lookup"><span data-stu-id="bfbe2-139">Map new format elements to data model</span></span>
1. <span data-ttu-id="bfbe2-140">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-140">Click the Mapping tab.</span></span>
2. <span data-ttu-id="bfbe2-141">En el árbol , expanda "modelo".</span><span class="sxs-lookup"><span data-stu-id="bfbe2-141">In the tree, expand 'model'.</span></span>
3. <span data-ttu-id="bfbe2-142">En el árbol, expanda el “model\Invoice attachments".</span><span class="sxs-lookup"><span data-stu-id="bfbe2-142">In the tree, expand 'model\Invoice attachments'.</span></span>
4. <span data-ttu-id="bfbe2-143">En el árbol, seleccione “Formato de salida adjunto\Archivo adjunto\Base64”.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-143">In the tree, select 'Zip output\Attached file\Base64'.</span></span>
5. <span data-ttu-id="bfbe2-144">En el árbol, seleccione “model\Invoice attachments\File content".</span><span class="sxs-lookup"><span data-stu-id="bfbe2-144">In the tree, select 'model\Invoice attachments\File content'.</span></span>
6. <span data-ttu-id="bfbe2-145">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-145">Click Bind.</span></span>
7. <span data-ttu-id="bfbe2-146">En el árbol, seleccione "Formato de salida comprimido\Archivo adjunto".</span><span class="sxs-lookup"><span data-stu-id="bfbe2-146">In the tree, select 'Zip output\Attached file'.</span></span>
8. <span data-ttu-id="bfbe2-147">Haga clic en Editar nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-147">Click Edit filename.</span></span>
9. <span data-ttu-id="bfbe2-148">En el árbol , expanda "modelo".</span><span class="sxs-lookup"><span data-stu-id="bfbe2-148">In the tree, expand 'model'.</span></span>
10. <span data-ttu-id="bfbe2-149">En el árbol, expanda el “model\Invoice attachments".</span><span class="sxs-lookup"><span data-stu-id="bfbe2-149">In the tree, expand 'model\Invoice attachments'.</span></span>
11. <span data-ttu-id="bfbe2-150">En el árbol, seleccione “model\Facturar adjuntos\Nombre de archivo”.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-150">In the tree, select 'model\Invoice attachments\File name'.</span></span>
12. <span data-ttu-id="bfbe2-151">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-151">Click Add data source.</span></span>
13. <span data-ttu-id="bfbe2-152">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-152">Click Save.</span></span>
14. <span data-ttu-id="bfbe2-153">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-153">Close the page.</span></span>
15. <span data-ttu-id="bfbe2-154">En el árbol, seleccione “model\Invoice attachments”.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-154">In the tree, select 'model\Invoice attachments'.</span></span>
16. <span data-ttu-id="bfbe2-155">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-155">Click Bind.</span></span>
17. <span data-ttu-id="bfbe2-156">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-156">Click Save.</span></span>
18. <span data-ttu-id="bfbe2-157">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-157">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="bfbe2-158">Ejecute el informe diseñado para la factura seleccionada</span><span class="sxs-lookup"><span data-stu-id="bfbe2-158">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="bfbe2-159">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-159">Click Run.</span></span>
2. <span data-ttu-id="bfbe2-160">Expanda los Registros para incluir la sección ().</span><span class="sxs-lookup"><span data-stu-id="bfbe2-160">Expand the Records to include () section.</span></span>
3. <span data-ttu-id="bfbe2-161">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-161">Click Filter.</span></span>
4. <span data-ttu-id="bfbe2-162">Seleccione la fila del diario de facturas de Cliente y el campo de Pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-162">Select the row of the Customer invoice journal and the Sales order field.</span></span>
5. <span data-ttu-id="bfbe2-163">En el campo Criterios, En el campo de criterios “Pedido de ventas”, introduzca el número de pedido 000148.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-163">In the Criteria field, In the criteria “Sales order” field, type the order number 000148.</span></span>
    * <span data-ttu-id="bfbe2-164">000148</span><span class="sxs-lookup"><span data-stu-id="bfbe2-164">000148</span></span>  
6. <span data-ttu-id="bfbe2-165">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="bfbe2-165">Click OK.</span></span>
7. <span data-ttu-id="bfbe2-166">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="bfbe2-166">Click OK.</span></span>
    * <span data-ttu-id="bfbe2-167">Revise la salida generada.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-167">Review the generated output.</span></span> <span data-ttu-id="bfbe2-168">Tenga en cuenta que, además del mensaje de factura en formato XML, se ha creado un archivo único para cada adjunto.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-168">Note, in addition to the invoice message in XML format, a single file has been created for each attachment.</span></span> <span data-ttu-id="bfbe2-169">Los archivos adjuntos se rellenan con el formato de salida comprimido en formato binario.</span><span class="sxs-lookup"><span data-stu-id="bfbe2-169">The attachment files are populated with the zipped output in binary format.</span></span>  


