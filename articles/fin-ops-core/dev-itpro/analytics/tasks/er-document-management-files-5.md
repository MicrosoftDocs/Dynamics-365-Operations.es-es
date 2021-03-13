---
title: 'Informe electrónico Usar archivos de gestión de documentos en las salidas de formato (Parte 5: Modificación y ejecución del formato)'
description: Este tema describe cómo configurar un formato de informes electrónicos (ER) para utilizar archivos de administración de documentos (adjuntos) en la salida de informes electrónicos. (Parte 5)
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
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f96189163d5ecac47ade9f713b3fd689e41352d0
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092497"
---
# <a name="er-use-document-management-files-in-format-outputs-part-5---modify-and-run-format"></a><span data-ttu-id="edbcf-104">Informe electrónico Usar archivos de gestión de documentos en las salidas de formato (Parte 5: Modificación y ejecución del formato)</span><span class="sxs-lookup"><span data-stu-id="edbcf-104">ER Use Document Management files in format outputs (Part 5 - Modify and run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="edbcf-105">En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema, o a un rol de desarrollador de informes electrónicos, puede configurar un formato de informe electrónico (ER) para usar archivos de gestión de documentos (adjuntos) en formato ER.</span><span class="sxs-lookup"><span data-stu-id="edbcf-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="edbcf-106">Estos pasos se pueden llevar a cabo en la empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="edbcf-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="edbcf-107">Para completar estos pasos, primero debe completar los pasos del procedimiento "ER Uso de gestión de documentos en formatos de salida (Parte 4: Ejecutar un formato)”.</span><span class="sxs-lookup"><span data-stu-id="edbcf-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 4: Run format)" procedure.</span></span>

<span data-ttu-id="edbcf-108">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="edbcf-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format"></a><span data-ttu-id="edbcf-109">Modifique el formato para rellenar los adjuntos y generar mensajes en formato binario</span><span class="sxs-lookup"><span data-stu-id="edbcf-109">Modify the format to populate attachments into generating messages in binary format</span></span>
1. <span data-ttu-id="edbcf-110">Vaya a Administración de la organización > Informes electrónicos > Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="edbcf-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="edbcf-111">En el árbol, expanda el “Modelo de factura del cliente”.</span><span class="sxs-lookup"><span data-stu-id="edbcf-111">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="edbcf-112">En el árbol, expanda el “Modelo de factura de cliente\Modelo de factura de cliente (cliente)”.</span><span class="sxs-lookup"><span data-stu-id="edbcf-112">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="edbcf-113">En el árbol, seleccione “Modelo de factura de cliente\Modelo de factura de cliente (importación)\Mensaje de ejemplo de factura electrónica”.</span><span class="sxs-lookup"><span data-stu-id="edbcf-113">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="edbcf-114">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="edbcf-114">Click Designer.</span></span>
    * <span data-ttu-id="edbcf-115">Se rellenará el mensaje de la factura en un formato generado como archivo XML con codificación UNICODE.</span><span class="sxs-lookup"><span data-stu-id="edbcf-115">You will populate the invoice message in the generating output as an XML file using UNICODE encoding.</span></span>  
6. <span data-ttu-id="edbcf-116">Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="edbcf-116">Click Add root to open the drop dialog.</span></span>
7. <span data-ttu-id="edbcf-117">En el árbol, seleccione Común\Archivo.</span><span class="sxs-lookup"><span data-stu-id="edbcf-117">In the tree, select 'Common\File'.</span></span>
8. <span data-ttu-id="edbcf-118">En el campo Nombre, introduzca "Mensaje Xml".</span><span class="sxs-lookup"><span data-stu-id="edbcf-118">In the Name field, type 'Xml message'.</span></span>
    * <span data-ttu-id="edbcf-119">Mensaje Xml</span><span class="sxs-lookup"><span data-stu-id="edbcf-119">Xml message</span></span>  
9. <span data-ttu-id="edbcf-120">En el campo Codificación, escriba "UTF-8".</span><span class="sxs-lookup"><span data-stu-id="edbcf-120">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="edbcf-121">UTF-8</span><span class="sxs-lookup"><span data-stu-id="edbcf-121">UTF-8</span></span>  
10. <span data-ttu-id="edbcf-122">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="edbcf-122">Click OK.</span></span>
    * <span data-ttu-id="edbcf-123">Configurar el formato de salida como archivo comprimido.</span><span class="sxs-lookup"><span data-stu-id="edbcf-123">Configure the generating output as a zipped file.</span></span>  
11. <span data-ttu-id="edbcf-124">Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="edbcf-124">Click Add root to open the drop dialog.</span></span>
12. <span data-ttu-id="edbcf-125">En el árbol, seleccione "Common\Folder".</span><span class="sxs-lookup"><span data-stu-id="edbcf-125">In the tree, select 'Common\Folder'.</span></span>
13. <span data-ttu-id="edbcf-126">En el campo Nombre, introduzca "Formato de salida comprimido".</span><span class="sxs-lookup"><span data-stu-id="edbcf-126">In the Name field, type 'Zip output'.</span></span>
    * <span data-ttu-id="edbcf-127">Código postal generado</span><span class="sxs-lookup"><span data-stu-id="edbcf-127">Zip output</span></span>  
14. <span data-ttu-id="edbcf-128">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="edbcf-128">Click OK.</span></span>
15. <span data-ttu-id="edbcf-129">En el árbol, seleccione "Formato de salida comprimido".</span><span class="sxs-lookup"><span data-stu-id="edbcf-129">In the tree, select 'Zip output'.</span></span>
    * <span data-ttu-id="edbcf-130">Agregue adjuntos al archivo comprimido generado como archivos con nombres originales y extensiones.</span><span class="sxs-lookup"><span data-stu-id="edbcf-130">Add attachments to the generating zipped file as files with original names and extensions.</span></span>  
16. <span data-ttu-id="edbcf-131">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="edbcf-131">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="edbcf-132">En el árbol, seleccione Común\Archivo.</span><span class="sxs-lookup"><span data-stu-id="edbcf-132">In the tree, select 'Common\File'.</span></span>
18. <span data-ttu-id="edbcf-133">En el campo Nombre, introduzca "Archivo adjunto".</span><span class="sxs-lookup"><span data-stu-id="edbcf-133">In the Name field, type 'Attached file'.</span></span>
    * <span data-ttu-id="edbcf-134">Archivo adjunto</span><span class="sxs-lookup"><span data-stu-id="edbcf-134">Attached file</span></span>  
19. <span data-ttu-id="edbcf-135">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="edbcf-135">Click OK.</span></span>
20. <span data-ttu-id="edbcf-136">En el árbol, seleccione "Formato de salida comprimido\Archivo adjunto".</span><span class="sxs-lookup"><span data-stu-id="edbcf-136">In the tree, select 'Zip output\Attached file'.</span></span>
21. <span data-ttu-id="edbcf-137">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="edbcf-137">Click Add to open the drop dialog.</span></span>
22. <span data-ttu-id="edbcf-138">En el árbol, seleccione 'Text\Base64'.</span><span class="sxs-lookup"><span data-stu-id="edbcf-138">In the tree, select 'Text\Base64'.</span></span>
23. <span data-ttu-id="edbcf-139">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="edbcf-139">Click OK.</span></span>

## <a name="map-new-format-elements-to-data-model"></a><span data-ttu-id="edbcf-140">Asigne nuevos elementos de formato al modelo de datos</span><span class="sxs-lookup"><span data-stu-id="edbcf-140">Map new format elements to data model</span></span>
1. <span data-ttu-id="edbcf-141">Haga clic en la ficha Asignación.</span><span class="sxs-lookup"><span data-stu-id="edbcf-141">Click the Mapping tab.</span></span>
2. <span data-ttu-id="edbcf-142">En el árbol , expanda "modelo".</span><span class="sxs-lookup"><span data-stu-id="edbcf-142">In the tree, expand 'model'.</span></span>
3. <span data-ttu-id="edbcf-143">En el árbol, expanda el “model\Invoice attachments".</span><span class="sxs-lookup"><span data-stu-id="edbcf-143">In the tree, expand 'model\Invoice attachments'.</span></span>
4. <span data-ttu-id="edbcf-144">En el árbol, seleccione “Formato de salida adjunto\Archivo adjunto\Base64”.</span><span class="sxs-lookup"><span data-stu-id="edbcf-144">In the tree, select 'Zip output\Attached file\Base64'.</span></span>
5. <span data-ttu-id="edbcf-145">En el árbol, seleccione “model\Invoice attachments\File content".</span><span class="sxs-lookup"><span data-stu-id="edbcf-145">In the tree, select 'model\Invoice attachments\File content'.</span></span>
6. <span data-ttu-id="edbcf-146">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="edbcf-146">Click Bind.</span></span>
7. <span data-ttu-id="edbcf-147">En el árbol, seleccione "Formato de salida comprimido\Archivo adjunto".</span><span class="sxs-lookup"><span data-stu-id="edbcf-147">In the tree, select 'Zip output\Attached file'.</span></span>
8. <span data-ttu-id="edbcf-148">Haga clic en Editar nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="edbcf-148">Click Edit filename.</span></span>
9. <span data-ttu-id="edbcf-149">En el árbol , expanda "modelo".</span><span class="sxs-lookup"><span data-stu-id="edbcf-149">In the tree, expand 'model'.</span></span>
10. <span data-ttu-id="edbcf-150">En el árbol, expanda el “model\Invoice attachments".</span><span class="sxs-lookup"><span data-stu-id="edbcf-150">In the tree, expand 'model\Invoice attachments'.</span></span>
11. <span data-ttu-id="edbcf-151">En el árbol, seleccione “model\Facturar adjuntos\Nombre de archivo”.</span><span class="sxs-lookup"><span data-stu-id="edbcf-151">In the tree, select 'model\Invoice attachments\File name'.</span></span>
12. <span data-ttu-id="edbcf-152">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="edbcf-152">Click Add data source.</span></span>
13. <span data-ttu-id="edbcf-153">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="edbcf-153">Click Save.</span></span>
14. <span data-ttu-id="edbcf-154">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="edbcf-154">Close the page.</span></span>
15. <span data-ttu-id="edbcf-155">En el árbol, seleccione “model\Invoice attachments”.</span><span class="sxs-lookup"><span data-stu-id="edbcf-155">In the tree, select 'model\Invoice attachments'.</span></span>
16. <span data-ttu-id="edbcf-156">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="edbcf-156">Click Bind.</span></span>
17. <span data-ttu-id="edbcf-157">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="edbcf-157">Click Save.</span></span>
18. <span data-ttu-id="edbcf-158">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="edbcf-158">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="edbcf-159">Ejecute el informe diseñado para la factura seleccionada</span><span class="sxs-lookup"><span data-stu-id="edbcf-159">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="edbcf-160">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="edbcf-160">Click Run.</span></span>
2. <span data-ttu-id="edbcf-161">Expanda los Registros para incluir la sección ().</span><span class="sxs-lookup"><span data-stu-id="edbcf-161">Expand the Records to include () section.</span></span>
3. <span data-ttu-id="edbcf-162">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="edbcf-162">Click Filter.</span></span>
4. <span data-ttu-id="edbcf-163">Seleccione la fila del diario de facturas de Cliente y el campo de Pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="edbcf-163">Select the row of the Customer invoice journal and the Sales order field.</span></span>
5. <span data-ttu-id="edbcf-164">En el campo Criterios, En el campo de criterios “Pedido de ventas”, introduzca el número de pedido 000148.</span><span class="sxs-lookup"><span data-stu-id="edbcf-164">In the Criteria field, In the criteria "Sales order" field, type the order number 000148.</span></span>
    * <span data-ttu-id="edbcf-165">000148</span><span class="sxs-lookup"><span data-stu-id="edbcf-165">000148</span></span>  
6. <span data-ttu-id="edbcf-166">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="edbcf-166">Click OK.</span></span>
7. <span data-ttu-id="edbcf-167">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="edbcf-167">Click OK.</span></span>
    * <span data-ttu-id="edbcf-168">Revise la salida generada.</span><span class="sxs-lookup"><span data-stu-id="edbcf-168">Review the generated output.</span></span> <span data-ttu-id="edbcf-169">Tenga en cuenta que, además del mensaje de factura en formato XML, se ha creado un archivo único para cada adjunto.</span><span class="sxs-lookup"><span data-stu-id="edbcf-169">Note,that in addition to the invoice message in XML format, a single file has been created for each attachment.</span></span> <span data-ttu-id="edbcf-170">Los archivos adjuntos se rellenan con el formato de salida comprimido en formato binario.</span><span class="sxs-lookup"><span data-stu-id="edbcf-170">The attachment files are populated with the zipped output in binary format.</span></span>  

