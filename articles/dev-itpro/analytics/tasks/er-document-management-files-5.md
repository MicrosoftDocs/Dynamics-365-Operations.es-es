---
title: 'Informe electrónico Usar archivos de gestión de documentos en las salidas de formato (Parte 5: Modificación y ejecución del formato)'
description: En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema, o a un rol de desarrollador de informes electrónicos, puede configurar un formato de informe electrónico (ER) para usar archivos de gestión de documentos (adjuntos) en formato ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERComponentTypeDropDialog, ERExpressionDesignerFormula, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba9cc4dcdfcfbc1bdb933336e85da9b4b6d97a40
ms.sourcegitcommit: f5556189a80ad9f23f1af3333837eae034ddb247
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2019
ms.locfileid: "1791865"
---
# <a name="er-use-document-management-files-in-format-outputs-part-5-modify-and-run-format"></a><span data-ttu-id="ace7f-103">Informe electrónico Usar archivos de gestión de documentos en las salidas de formato (Parte 5: Modificación y ejecución del formato)</span><span class="sxs-lookup"><span data-stu-id="ace7f-103">ER Use Document Management files in format outputs (Part 5: Modify and run format)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ace7f-104">En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema, o a un rol de desarrollador de informes electrónicos, puede configurar un formato de informe electrónico (ER) para usar archivos de gestión de documentos (adjuntos) en formato ER.</span><span class="sxs-lookup"><span data-stu-id="ace7f-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="ace7f-105">Estos pasos se pueden llevar a cabo en la empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="ace7f-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="ace7f-106">Para completar estos pasos, primero debe completar los pasos del procedimiento "ER Uso de gestión de documentos en formatos de salida (Parte 4: Ejecutar un formato)”.</span><span class="sxs-lookup"><span data-stu-id="ace7f-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 4: Run format)” procedure.</span></span>

<span data-ttu-id="ace7f-107">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="ace7f-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format"></a><span data-ttu-id="ace7f-108">Modifique el formato para rellenar los adjuntos y generar mensajes en formato binario</span><span class="sxs-lookup"><span data-stu-id="ace7f-108">Modify the format to populate attachments into generating messages in binary format</span></span>
1. <span data-ttu-id="ace7f-109">Vaya a Administración de la organización > Informes electrónicos > Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="ace7f-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="ace7f-110">En el árbol, expanda el “Modelo de factura del cliente”.</span><span class="sxs-lookup"><span data-stu-id="ace7f-110">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="ace7f-111">En el árbol, expanda el “Modelo de factura de cliente\Modelo de factura de cliente (cliente)”.</span><span class="sxs-lookup"><span data-stu-id="ace7f-111">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="ace7f-112">En el árbol, seleccione “Modelo de factura de cliente\Modelo de factura de cliente (importación)\Mensaje de ejemplo de factura electrónica”.</span><span class="sxs-lookup"><span data-stu-id="ace7f-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="ace7f-113">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="ace7f-113">Click Designer.</span></span>
    * <span data-ttu-id="ace7f-114">Se rellenará el mensaje de la factura en un formato generado como archivo XML con codificación UNICODE.</span><span class="sxs-lookup"><span data-stu-id="ace7f-114">You will populate the invoice message in the generating output as an XML file using UNICODE encoding.</span></span>  
6. <span data-ttu-id="ace7f-115">Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="ace7f-115">Click Add root to open the drop dialog.</span></span>
7. <span data-ttu-id="ace7f-116">En el árbol, seleccione Común\Archivo.</span><span class="sxs-lookup"><span data-stu-id="ace7f-116">In the tree, select 'Common\File'.</span></span>
8. <span data-ttu-id="ace7f-117">En el campo Nombre, introduzca "Mensaje Xml".</span><span class="sxs-lookup"><span data-stu-id="ace7f-117">In the Name field, type 'Xml message'.</span></span>
    * <span data-ttu-id="ace7f-118">Mensaje Xml</span><span class="sxs-lookup"><span data-stu-id="ace7f-118">Xml message</span></span>  
9. <span data-ttu-id="ace7f-119">En el campo Codificación, escriba "UTF-8".</span><span class="sxs-lookup"><span data-stu-id="ace7f-119">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="ace7f-120">UTF-8</span><span class="sxs-lookup"><span data-stu-id="ace7f-120">UTF-8</span></span>  
10. <span data-ttu-id="ace7f-121">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ace7f-121">Click OK.</span></span>
    * <span data-ttu-id="ace7f-122">Configurar el formato de salida como archivo comprimido.</span><span class="sxs-lookup"><span data-stu-id="ace7f-122">Configure the generating output as a zipped file.</span></span>  
11. <span data-ttu-id="ace7f-123">Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="ace7f-123">Click Add root to open the drop dialog.</span></span>
12. <span data-ttu-id="ace7f-124">En el árbol, seleccione "Common\Folder".</span><span class="sxs-lookup"><span data-stu-id="ace7f-124">In the tree, select 'Common\Folder'.</span></span>
13. <span data-ttu-id="ace7f-125">En el campo Nombre, introduzca "Formato de salida comprimido".</span><span class="sxs-lookup"><span data-stu-id="ace7f-125">In the Name field, type 'Zip output'.</span></span>
    * <span data-ttu-id="ace7f-126">Código postal generado</span><span class="sxs-lookup"><span data-stu-id="ace7f-126">Zip output</span></span>  
14. <span data-ttu-id="ace7f-127">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ace7f-127">Click OK.</span></span>
15. <span data-ttu-id="ace7f-128">En el árbol, seleccione "Formato de salida comprimido".</span><span class="sxs-lookup"><span data-stu-id="ace7f-128">In the tree, select 'Zip output'.</span></span>
    * <span data-ttu-id="ace7f-129">Agregue adjuntos al archivo comprimido generado como archivos con nombres originales y extensiones.</span><span class="sxs-lookup"><span data-stu-id="ace7f-129">Add attachments to the generating zipped file as files with original names and extensions.</span></span>  
16. <span data-ttu-id="ace7f-130">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="ace7f-130">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="ace7f-131">En el árbol, seleccione Común\Archivo.</span><span class="sxs-lookup"><span data-stu-id="ace7f-131">In the tree, select 'Common\File'.</span></span>
18. <span data-ttu-id="ace7f-132">En el campo Nombre, introduzca "Archivo adjunto".</span><span class="sxs-lookup"><span data-stu-id="ace7f-132">In the Name field, type 'Attached file'.</span></span>
    * <span data-ttu-id="ace7f-133">Archivo adjunto</span><span class="sxs-lookup"><span data-stu-id="ace7f-133">Attached file</span></span>  
19. <span data-ttu-id="ace7f-134">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ace7f-134">Click OK.</span></span>
20. <span data-ttu-id="ace7f-135">En el árbol, seleccione "Formato de salida comprimido\Archivo adjunto".</span><span class="sxs-lookup"><span data-stu-id="ace7f-135">In the tree, select 'Zip output\Attached file'.</span></span>
21. <span data-ttu-id="ace7f-136">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="ace7f-136">Click Add to open the drop dialog.</span></span>
22. <span data-ttu-id="ace7f-137">En el árbol, seleccione 'Text\Base64'.</span><span class="sxs-lookup"><span data-stu-id="ace7f-137">In the tree, select 'Text\Base64'.</span></span>
23. <span data-ttu-id="ace7f-138">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ace7f-138">Click OK.</span></span>

## <a name="map-new-format-elements-to-data-model"></a><span data-ttu-id="ace7f-139">Asigne nuevos elementos de formato al modelo de datos</span><span class="sxs-lookup"><span data-stu-id="ace7f-139">Map new format elements to data model</span></span>
1. <span data-ttu-id="ace7f-140">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="ace7f-140">Click the Mapping tab.</span></span>
2. <span data-ttu-id="ace7f-141">En el árbol , expanda "modelo".</span><span class="sxs-lookup"><span data-stu-id="ace7f-141">In the tree, expand 'model'.</span></span>
3. <span data-ttu-id="ace7f-142">En el árbol, expanda el “model\Invoice attachments".</span><span class="sxs-lookup"><span data-stu-id="ace7f-142">In the tree, expand 'model\Invoice attachments'.</span></span>
4. <span data-ttu-id="ace7f-143">En el árbol, seleccione “Formato de salida adjunto\Archivo adjunto\Base64”.</span><span class="sxs-lookup"><span data-stu-id="ace7f-143">In the tree, select 'Zip output\Attached file\Base64'.</span></span>
5. <span data-ttu-id="ace7f-144">En el árbol, seleccione “model\Invoice attachments\File content".</span><span class="sxs-lookup"><span data-stu-id="ace7f-144">In the tree, select 'model\Invoice attachments\File content'.</span></span>
6. <span data-ttu-id="ace7f-145">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="ace7f-145">Click Bind.</span></span>
7. <span data-ttu-id="ace7f-146">En el árbol, seleccione "Formato de salida comprimido\Archivo adjunto".</span><span class="sxs-lookup"><span data-stu-id="ace7f-146">In the tree, select 'Zip output\Attached file'.</span></span>
8. <span data-ttu-id="ace7f-147">Haga clic en Editar nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="ace7f-147">Click Edit filename.</span></span>
9. <span data-ttu-id="ace7f-148">En el árbol , expanda "modelo".</span><span class="sxs-lookup"><span data-stu-id="ace7f-148">In the tree, expand 'model'.</span></span>
10. <span data-ttu-id="ace7f-149">En el árbol, expanda el “model\Invoice attachments".</span><span class="sxs-lookup"><span data-stu-id="ace7f-149">In the tree, expand 'model\Invoice attachments'.</span></span>
11. <span data-ttu-id="ace7f-150">En el árbol, seleccione “model\Facturar adjuntos\Nombre de archivo”.</span><span class="sxs-lookup"><span data-stu-id="ace7f-150">In the tree, select 'model\Invoice attachments\File name'.</span></span>
12. <span data-ttu-id="ace7f-151">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ace7f-151">Click Add data source.</span></span>
13. <span data-ttu-id="ace7f-152">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ace7f-152">Click Save.</span></span>
14. <span data-ttu-id="ace7f-153">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ace7f-153">Close the page.</span></span>
15. <span data-ttu-id="ace7f-154">En el árbol, seleccione “model\Invoice attachments”.</span><span class="sxs-lookup"><span data-stu-id="ace7f-154">In the tree, select 'model\Invoice attachments'.</span></span>
16. <span data-ttu-id="ace7f-155">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="ace7f-155">Click Bind.</span></span>
17. <span data-ttu-id="ace7f-156">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ace7f-156">Click Save.</span></span>
18. <span data-ttu-id="ace7f-157">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ace7f-157">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="ace7f-158">Ejecute el informe diseñado para la factura seleccionada</span><span class="sxs-lookup"><span data-stu-id="ace7f-158">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="ace7f-159">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="ace7f-159">Click Run.</span></span>
2. <span data-ttu-id="ace7f-160">Expanda los Registros para incluir la sección ().</span><span class="sxs-lookup"><span data-stu-id="ace7f-160">Expand the Records to include () section.</span></span>
3. <span data-ttu-id="ace7f-161">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="ace7f-161">Click Filter.</span></span>
4. <span data-ttu-id="ace7f-162">Seleccione la fila del diario de facturas de Cliente y el campo de Pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="ace7f-162">Select the row of the Customer invoice journal and the Sales order field.</span></span>
5. <span data-ttu-id="ace7f-163">En el campo Criterios, En el campo de criterios “Pedido de ventas”, introduzca el número de pedido 000148.</span><span class="sxs-lookup"><span data-stu-id="ace7f-163">In the Criteria field, In the criteria “Sales order” field, type the order number 000148.</span></span>
    * <span data-ttu-id="ace7f-164">000148</span><span class="sxs-lookup"><span data-stu-id="ace7f-164">000148</span></span>  
6. <span data-ttu-id="ace7f-165">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ace7f-165">Click OK.</span></span>
7. <span data-ttu-id="ace7f-166">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ace7f-166">Click OK.</span></span>
    * <span data-ttu-id="ace7f-167">Revise la salida generada.</span><span class="sxs-lookup"><span data-stu-id="ace7f-167">Review the generated output.</span></span> <span data-ttu-id="ace7f-168">Tenga en cuenta que, además del mensaje de factura en formato XML, se ha creado un archivo único para cada adjunto.</span><span class="sxs-lookup"><span data-stu-id="ace7f-168">Note,that in addition to the invoice message in XML format, a single file has been created for each attachment.</span></span> <span data-ttu-id="ace7f-169">Los archivos adjuntos se rellenan con el formato de salida comprimido en formato binario.</span><span class="sxs-lookup"><span data-stu-id="ace7f-169">The attachment files are populated with the zipped output in binary format.</span></span>  

