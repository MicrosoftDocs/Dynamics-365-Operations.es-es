---
title: Modificar modelos y asignaciones para generar documentos que tengan datos de la aplicación
description: 'Este tema describe cómo diseñar las configuraciones de los informes para generar un documento electrónico y actualizar datos de la aplicación. (Parte 2: generar documentos).'
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 025429c8e6775d20634703853df04d63c0651b98
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092906"
---
# <a name="modify-models-and-mappings-to-generate-documents-that-have-application-data"></a><span data-ttu-id="3c9c1-104">Modificar modelos y asignaciones para generar documentos que tengan datos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="3c9c1-104">Modify models and mappings to generate documents that have application data</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3c9c1-105">Para completar los pasos de este procedimiento, primero debe completar el procedimiento, "ER: Generar documentos con la actualización de datos de la aplicación (Parte 2: Generar documentos)".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-105">To complete the steps in this procedure, you must first complete the procedure, "ER Generate documents with application data update (Part 2: Generate documents)".</span></span> 

<span data-ttu-id="3c9c1-106">Los pasos de este procedimiento explican cómo diseñar las configuraciones de los informes electrónicos (ER) para generar un documento electrónico y actualizar los datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-106">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document and update application data.</span></span> <span data-ttu-id="3c9c1-107">En este procedimiento, se modificarán las configuraciones de ER para comenzar a utilizarlas para generar documentos electrónicos y actualizar los datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-107">In this procedure, you will modify the ER configurations to start using them to generate electronic documents and update application data.</span></span> <span data-ttu-id="3c9c1-108">Este procedimiento se ha creado para los usuarios con los roles Administrador del sistema o Desarrollador de informes electrónicos asignados.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-108">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="3c9c1-109">Estos pasos se pueden completar mediante el conjunto de datos de DEMF.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-109">These steps can be completed using the DEMF dataset.</span></span>


## <a name="modify-data-model"></a><span data-ttu-id="3c9c1-110">Modificar modelos de datos</span><span class="sxs-lookup"><span data-stu-id="3c9c1-110">Modify data model</span></span>
1. <span data-ttu-id="3c9c1-111">Vaya a Administración de la organización > Informes electrónicos > Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-111">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="3c9c1-112">En el árbol, seleccione "Intrastat (modelo)".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-112">In the tree, select 'Intrastat (model)'.</span></span>
    * <span data-ttu-id="3c9c1-113">Ampliará cómo se usa el modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-113">You will extend how you use the data model.</span></span> <span data-ttu-id="3c9c1-114">Además de usarlo como origen de datos para generar el informe de Intrastat, el modelo de datos se usará para obtener detalles sobre el proceso de generación de informes de Intrastat.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-114">Besides using it as data source to generate the Intrastat report, the data model will be used to collect details about the Intrastat reporting process.</span></span> <span data-ttu-id="3c9c1-115">Los detalles se usarán después para actualizar los datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-115">The details will then be used to update application data.</span></span>   
3. <span data-ttu-id="3c9c1-116">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-116">Click Designer.</span></span>
4. <span data-ttu-id="3c9c1-117">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-117">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="3c9c1-118">En el campo "Nuevo nodo como", escriba "Raíz del modelo".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-118">In the New node as a field, enter 'Model root'.</span></span>
6. <span data-ttu-id="3c9c1-119">En el campo Nombre, escriba "Para actualizar datos de la aplicación".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-119">In the Name field, type 'For application data update'.</span></span>
    * <span data-ttu-id="3c9c1-120">Para la actualización de los datos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="3c9c1-120">For application data update</span></span>  
7. <span data-ttu-id="3c9c1-121">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-121">Click Add.</span></span>
8. <span data-ttu-id="3c9c1-122">En el árbol, seleccione “Para actualizar datos de la aplicación".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-122">In the tree, select 'For application data update'.</span></span>
    * <span data-ttu-id="3c9c1-123">Este nuevo elemento raíz se agrega para especificar el flujo de datos para desplazar datos del informe de Intrastat (usado como origen de datos) a las tablas de la aplicación (el destino de la actualización).</span><span class="sxs-lookup"><span data-stu-id="3c9c1-123">This new root item is added to specify the data flow for moving data from the Intrastat report (used as a data source) to the application tables (the update destination).</span></span> <span data-ttu-id="3c9c1-124">Tenga en cuenta que los distintos elementos raíz se deben utilizar para obtener los datos que se envían al documento de salida y para recopilar datos del documento que se usa para actualizar los datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-124">Note that different root items must be used for getting data that is posted to the outgoing document and for getting data from the document that is used to update application data.</span></span>   
9. <span data-ttu-id="3c9c1-125">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-125">Click New to open the drop dialog.</span></span>
10. <span data-ttu-id="3c9c1-126">En el campo Nombre, escriba "Encabezado de archivo".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-126">In the Name field, type 'Archive header'.</span></span>
    * <span data-ttu-id="3c9c1-127">Encabezado de archivo</span><span class="sxs-lookup"><span data-stu-id="3c9c1-127">Archive header</span></span>  
11. <span data-ttu-id="3c9c1-128">En el campo Tipo de artículo, seleccione Lista de registros.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-128">In the Item type field, select 'Record list'.</span></span>
12. <span data-ttu-id="3c9c1-129">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-129">Click Add.</span></span>
    * <span data-ttu-id="3c9c1-130">Dado que creará un registro para cada informe de Intrastat que se genere, debe crear un elemento nuevo para eso.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-130">Because you will create a record for each Intrastat report that is generated, you must create a new item for that.</span></span>  
13. <span data-ttu-id="3c9c1-131">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-131">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="3c9c1-132">En el campo Nombre, introduzca "Nombre de archivo".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-132">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="3c9c1-133">Nombre de archivo</span><span class="sxs-lookup"><span data-stu-id="3c9c1-133">File name</span></span>  
15. <span data-ttu-id="3c9c1-134">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-134">In the Item type field, select 'String'.</span></span>
16. <span data-ttu-id="3c9c1-135">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-135">Click Add.</span></span>
17. <span data-ttu-id="3c9c1-136">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-136">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="3c9c1-137">En el campo Nombre, escriba "Número de líneas".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-137">In the Name field, type 'Number of lines'.</span></span>
    * <span data-ttu-id="3c9c1-138">Número de líneas</span><span class="sxs-lookup"><span data-stu-id="3c9c1-138">Number of lines</span></span>  
19. <span data-ttu-id="3c9c1-139">En el campo Tipo de artículo, seleccione "Entero".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-139">In the Item type field, select 'Integer'.</span></span>
20. <span data-ttu-id="3c9c1-140">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-140">Click Add.</span></span>
    * <span data-ttu-id="3c9c1-141">Agregue este artículo para representar el número de transacciones de Intrastat que se registran durante el proceso actual de generación de informes.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-141">Add this item to represent the number of Intrastat transactions that are reported during the current reporting process.</span></span>  
21. <span data-ttu-id="3c9c1-142">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-142">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="3c9c1-143">En el campo Nombre, escriba "Líneas de archivo".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-143">In the Name field, type 'Archive lines'.</span></span>
    * <span data-ttu-id="3c9c1-144">Líneas de archivo</span><span class="sxs-lookup"><span data-stu-id="3c9c1-144">Archive lines</span></span>  
23. <span data-ttu-id="3c9c1-145">En el campo Tipo de artículo, seleccione Lista de registros.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-145">In the Item type field, select 'Record list'.</span></span>
24. <span data-ttu-id="3c9c1-146">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-146">Click Add.</span></span>
    * <span data-ttu-id="3c9c1-147">Agregue este artículo para representar la lista de transacciones de Intrastat que se registran durante el proceso actual de generación de informes.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-147">Add this item to represent the list of Intrastat transactions that are reported during the current reporting process.</span></span>  
25. <span data-ttu-id="3c9c1-148">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-148">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="3c9c1-149">En el campo Nombre, escriba "Importe".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-149">In the Name field, type 'Amount'.</span></span>
    * <span data-ttu-id="3c9c1-150">Importe</span><span class="sxs-lookup"><span data-stu-id="3c9c1-150">Amount</span></span>  
27. <span data-ttu-id="3c9c1-151">En el campo Tipo de artículo, seleccione Real.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-151">In the Item type field, select 'Real'.</span></span>
28. <span data-ttu-id="3c9c1-152">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-152">Click Add.</span></span>
29. <span data-ttu-id="3c9c1-153">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-153">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="3c9c1-154">En el campo Nombre, escriba “Id. de reg. de materiales”.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-154">In the Name field, type 'Commodity rec id'.</span></span>
    * <span data-ttu-id="3c9c1-155">Id. de reg de mercancías</span><span class="sxs-lookup"><span data-stu-id="3c9c1-155">Commodity rec id</span></span>  
31. <span data-ttu-id="3c9c1-156">En el campo Tipo de artículo, seleccione "Int64".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-156">In the Item type field, select 'Int64'.</span></span>
32. <span data-ttu-id="3c9c1-157">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-157">Click Add.</span></span>
33. <span data-ttu-id="3c9c1-158">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-158">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="3c9c1-159">En el campo Nombre, escriba "Número de elemento".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-159">In the Name field, type 'Item number'.</span></span>
    * <span data-ttu-id="3c9c1-160">código de artículo</span><span class="sxs-lookup"><span data-stu-id="3c9c1-160">Item number</span></span>  
35. <span data-ttu-id="3c9c1-161">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-161">In the Item type field, select 'String'.</span></span>
36. <span data-ttu-id="3c9c1-162">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-162">Click Add.</span></span>
37. <span data-ttu-id="3c9c1-163">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-163">Click Save.</span></span>
38. <span data-ttu-id="3c9c1-164">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-164">Close the page.</span></span>

## <a name="modify-model-mapping"></a><span data-ttu-id="3c9c1-165">Modificar asignación de modelos</span><span class="sxs-lookup"><span data-stu-id="3c9c1-165">Modify model mapping</span></span>
1. <span data-ttu-id="3c9c1-166">En el árbol, expanda "Intrastat (modelo)".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-166">In the tree, expand 'Intrastat (model)'.</span></span>
2. <span data-ttu-id="3c9c1-167">En el árbol, seleccione "Intrastat (modelo)\Intrastat (asignación)".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-167">In the tree, select 'Intrastat (model)\Intrastat (mapping)'.</span></span>
    * <span data-ttu-id="3c9c1-168">Permite modificar la asignación del modelo existente para comenzar a utilizarlo para la actualización de los datos de la aplicación y para archivar los detalles de informes de Intrastat.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-168">Modify the existing model mapping to start using it for  the application data update and to archive Intrastat reporting details.</span></span>  
3. <span data-ttu-id="3c9c1-169">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-169">Click Designer.</span></span>
4. <span data-ttu-id="3c9c1-170">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-170">Click New.</span></span>
5. <span data-ttu-id="3c9c1-171">En el campo Nombre, escriba "Actualizar archivado".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-171">In the Name field, type 'Update archive'.</span></span>
    * <span data-ttu-id="3c9c1-172">Actualizar archivo</span><span class="sxs-lookup"><span data-stu-id="3c9c1-172">Update archive</span></span>  
6. <span data-ttu-id="3c9c1-173">En el campo Dirección, seleccione "A destino".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-173">In the Direction field, select 'To destination'.</span></span>
7. <span data-ttu-id="3c9c1-174">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-174">Click Save.</span></span>
    * <span data-ttu-id="3c9c1-175">Esta nueva asignación especifica el flujo de datos para desplazar datos (detalles del informe de Intrastat) desde el modelo de datos a las tablas de la aplicación (el destino de la actualización).</span><span class="sxs-lookup"><span data-stu-id="3c9c1-175">This new mapping specifies the data flow for moving data (Intrastat reporting details) from the data model to the application tables (the update destination).</span></span> <span data-ttu-id="3c9c1-176">Tenga en cuenta que los diferentes elementos raíz del modelo se deben utilizar para recopilar datos de la aplicación para el proceso de generación de informes y después usar los datos del modelo para la actualización de los datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-176">Note that different model's root items must be used to get data from the application for the reporting process and then use the data from data model for the application data update.</span></span>   
8. <span data-ttu-id="3c9c1-177">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-177">Click Designer.</span></span>
9. <span data-ttu-id="3c9c1-178">En el árbol, seleccione "Modelo de datos\Modelo de datos".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-178">In the tree, select 'Data model\Data model'.</span></span>
    * <span data-ttu-id="3c9c1-179">Agregar el origen de los datos necesario.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-179">Add the required data source.</span></span> <span data-ttu-id="3c9c1-180">Este es el modelo de datos que contiene los detalles de las transacciones de intrastat registradas que deben archivarse.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-180">This is the data model that contains details of the reported Intrastat transactions that must be archived.</span></span>  
10. <span data-ttu-id="3c9c1-181">Haga clic en Agregar raíz.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-181">Click Add root.</span></span>
11. <span data-ttu-id="3c9c1-182">En el campo Nombre, escriba "Modelo".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-182">In the Name field, type 'model'.</span></span>
    * <span data-ttu-id="3c9c1-183">modelo</span><span class="sxs-lookup"><span data-stu-id="3c9c1-183">model</span></span>  
12. <span data-ttu-id="3c9c1-184">En el campo de Definición, especifique o seleccione el valor “Para la actualización de datos de la aplicación".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-184">In the Definition field, enter or select the value 'For application data update'.</span></span>
    * <span data-ttu-id="3c9c1-185">Para la actualización de los datos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="3c9c1-185">For application data update</span></span>  
13. <span data-ttu-id="3c9c1-186">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-186">Click OK.</span></span>
14. <span data-ttu-id="3c9c1-187">En el árbol , expanda "modelo".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-187">In the tree, expand 'model'.</span></span>
15. <span data-ttu-id="3c9c1-188">En el árbol, seleccione el apartado "Funciones\Campo calculado".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-188">In the tree, select 'Functions\Calculated field'.</span></span>
16. <span data-ttu-id="3c9c1-189">En el árbol, seleccione "modelo\Encabezado de archivo".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-189">In the tree, select 'model\Archive header'.</span></span>
17. <span data-ttu-id="3c9c1-190">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-190">Click Add.</span></span>
    * <span data-ttu-id="3c9c1-191">Dado que desea enumerar las transacciones de Intrastat registradas para archivar, el origen de datos adecuado se debe suma.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-191">Because you want to enumerate reported Intrastat transactions for archiving, the appropriate data source must be added.</span></span>  
18. <span data-ttu-id="3c9c1-192">En el campo Nombre, escriba "Líneas enumeradas".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-192">In the Name field, type 'Enumerated lines'.</span></span>
    * <span data-ttu-id="3c9c1-193">Líneas enumeradas</span><span class="sxs-lookup"><span data-stu-id="3c9c1-193">Enumerated lines</span></span>  
19. <span data-ttu-id="3c9c1-194">Haga clic en Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-194">Click Edit formula.</span></span>
20. <span data-ttu-id="3c9c1-195">En el árbol , seleccione "Lista\ENUMERAR".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-195">In the tree, select 'List\ENUMERATE'.</span></span>
21. <span data-ttu-id="3c9c1-196">Haga clic en Agregar función.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-196">Click Add function.</span></span>
22. <span data-ttu-id="3c9c1-197">En el árbol , expanda "modelo".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-197">In the tree, expand 'model'.</span></span>
23. <span data-ttu-id="3c9c1-198">En el árbol, expanda "modelo\Encabezado de archivo".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-198">In the tree, expand 'model\Archive header'.</span></span>
24. <span data-ttu-id="3c9c1-199">En el árbol, seleccione "modelo\Encabezado de archivo\Líneas de archivo".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-199">In the tree, select 'model\Archive header\Archive lines'.</span></span>
25. <span data-ttu-id="3c9c1-200">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-200">Click Add data source.</span></span>
26. <span data-ttu-id="3c9c1-201">En el campo Fórmula, especifique "ENUMERATE(model.'Archive header'.'Archive lines')".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-201">In the Formula field, enter 'ENUMERATE(model.'Archive header'.'Archive lines')'.</span></span>
    * <span data-ttu-id="3c9c1-202">ENUMERE (modelo. “Encabezado de archivo”. “Líneas del archivo")</span><span class="sxs-lookup"><span data-stu-id="3c9c1-202">ENUMERATE(model.'Archive header'.'Archive lines')</span></span>  
27. <span data-ttu-id="3c9c1-203">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-203">Click Save.</span></span>
28. <span data-ttu-id="3c9c1-204">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-204">Close the page.</span></span>
29. <span data-ttu-id="3c9c1-205">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3c9c1-205">Click OK.</span></span>
30. <span data-ttu-id="3c9c1-206">Haga clic en Agregar destino.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-206">Click Add destination.</span></span>
    * <span data-ttu-id="3c9c1-207">Agregue las tablas de la aplicación como destinos requeridos que necesitan actualizaciones para archivar los detalles de las transacciones de Intrastat registradas.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-207">Add application tables as required destinations that require updates to archive details of reported Intrastat transactions.</span></span>  
31. <span data-ttu-id="3c9c1-208">En el campo Nombre, escriba "Archivo".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-208">In the Name field, type 'Archive'.</span></span>
    * <span data-ttu-id="3c9c1-209">Archivar</span><span class="sxs-lookup"><span data-stu-id="3c9c1-209">Archive</span></span>  
32. <span data-ttu-id="3c9c1-210">En el campo Tabla, escriba "IntrastatArchiveGeneral".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-210">In the Table name field, type 'IntrastatArchiveGeneral'.</span></span>
    * <span data-ttu-id="3c9c1-211">IntrastatArchivoGeneral</span><span class="sxs-lookup"><span data-stu-id="3c9c1-211">IntrastatArchiveGeneral</span></span>  
    * <span data-ttu-id="3c9c1-212">Conserve la acción de registro “Insertar” para poder agregar registros durante el archivado de detalles de cada proceso de generación de informes de Intrastat.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-212">Keep the record action 'Insert' so you can add records during the detail archiving of each Intrastat reporting process.</span></span>  
33. <span data-ttu-id="3c9c1-213">Seleccione Sí en el campo Registrar en registro de información.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-213">Select Yes in the Record infolog field.</span></span>
    * <span data-ttu-id="3c9c1-214">Seleccione Si para obtener información sobre los problemas con la actualización de los datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-214">Select Yes to get information about issues with the application data update.</span></span>  
34. <span data-ttu-id="3c9c1-215">Seleccione Sí en el campo Omitir validación de acciones del registro.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-215">Select Yes in the Skip record action validation field.</span></span>
    * <span data-ttu-id="3c9c1-216">Seleccione Sí para suprimir errores de validación sobre campo vacío de "archivo Intrastat ID“.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-216">Select Yes to suppress validation errors about the empty 'Intrastat archive ID' field.</span></span> <span data-ttu-id="3c9c1-217">Esto se hace después de que se agreguen los registros, en función de la configuración del número de secuencia que esté configurado para esta tabla en el formulario de Parámetros de comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-217">This will be done after records are added, based on the sequence number settings that are configured for this table in the Foreign trade parameters form.</span></span>  
35. <span data-ttu-id="3c9c1-218">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3c9c1-218">Click OK.</span></span>
    * <span data-ttu-id="3c9c1-219">Vincular elementos del origen de datos agregados (el modelo filtrado basado en el elemento raíz seleccionado) con los elementos de destino agregados.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-219">Bind elements of the added data source (the filtered model based on the selected root item) with elements from the added destination.</span></span>  
36. <span data-ttu-id="3c9c1-220">En el árbol, expanda "Archivo".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-220">In the tree, expand 'Archive'.</span></span>
37. <span data-ttu-id="3c9c1-221">En el árbol, expanda "Archivo\<Relaciones".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-221">In the tree, expand 'Archive\<Relations'.</span></span>
38. <span data-ttu-id="3c9c1-222">En el árbol, expanda "Archivo\<Relaciones\DetalleArchivoIntrastat".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-222">In the tree, expand 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
39. <span data-ttu-id="3c9c1-223">En el árbol, seleccione "Archivo\<Relaciones\DetalleArchivoIntrastat\Cantidad(CantidadMST)".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-223">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Amount(AmountMST)'.</span></span>
40. <span data-ttu-id="3c9c1-224">En el árbol, expanda "modelo\Encabezado de archivo\Líneas enumeradas".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-224">In the tree, expand 'model\Archive header\Enumerated lines'.</span></span>
41. <span data-ttu-id="3c9c1-225">En el árbol, expanda "modelo\Encabezado de archivo\Líneas enumeradas\Valor".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-225">In the tree, expand 'model\Archive header\Enumerated lines\Value'.</span></span>
42. <span data-ttu-id="3c9c1-226">En el árbol, seleccione"modelo\Encabezado de archivo\Líneas enumeradas\Valor\Importe".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-226">In the tree, select 'model\Archive header\Enumerated lines\Value\Amount'.</span></span>
43. <span data-ttu-id="3c9c1-227">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-227">Click Bind.</span></span>
44. <span data-ttu-id="3c9c1-228">En el árbol, seleccione “Archivo\<Relaciones\DetalleArchivoIntrastat\Productos(ProductosIntrastat)".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-228">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Commodity(IntrastatCommodity)'.</span></span>
45. <span data-ttu-id="3c9c1-229">En el árbol, seleccione"modelo\Encabezado de archivo\Líneas enumeradas\Valor\Producto Id reg".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-229">In the tree, select 'model\Archive header\Enumerated lines\Value\Commodity rec id'.</span></span>
46. <span data-ttu-id="3c9c1-230">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-230">Click Bind.</span></span>
47. <span data-ttu-id="3c9c1-231">En el árbol, seleccione "Archivo\<Relaciones\DetalleArchivoIntrastat\Numero de elemento(IdElemento)".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-231">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Item number(ItemId)'.</span></span>
48. <span data-ttu-id="3c9c1-232">En el árbol, seleccione"modelo\Encabezado de archivo\Líneas enumeradas\Valor\Número de elemento".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-232">In the tree, select 'model\Archive header\Enumerated lines\Value\Item number'.</span></span>
49. <span data-ttu-id="3c9c1-233">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-233">Click Bind.</span></span>
50. <span data-ttu-id="3c9c1-234">En el árbol, seleccione "Archivo\<Relaciones\DetalleArchivoIntrastat\Numero de línea (NúmeroLínea)".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-234">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Line number(LineNumber)'.</span></span>
51. <span data-ttu-id="3c9c1-235">En el árbol, seleccione "modelo\Encabezado de archivo\Líneas enumeradas\Número".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-235">In the tree, select 'model\Archive header\Enumerated lines\Number'.</span></span>
52. <span data-ttu-id="3c9c1-236">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-236">Click Bind.</span></span>
53. <span data-ttu-id="3c9c1-237">En el árbol, seleccione "Archivo\<Relaciones\DetalleArchivoIntrastat".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-237">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
54. <span data-ttu-id="3c9c1-238">En el árbol, seleccione "modelo\Encabezado de archivo\Líneas enumeradas".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-238">In the tree, select 'model\Archive header\Enumerated lines'.</span></span>
55. <span data-ttu-id="3c9c1-239">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-239">Click Bind.</span></span>
56. <span data-ttu-id="3c9c1-240">En el árbol, seleccione "Archivo\Nombre de archivo(NombreArchivo)".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-240">In the tree, select 'Archive\File name(FileName)'.</span></span>
57. <span data-ttu-id="3c9c1-241">En el árbol, seleccione "modelo\Encabezado de archivo\Nombre de archivo".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-241">In the tree, select 'model\Archive header\File name'.</span></span>
58. <span data-ttu-id="3c9c1-242">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-242">Click Bind.</span></span>
59. <span data-ttu-id="3c9c1-243">En el árbol, seleccione "Archivo\Número de líneas(NúmeroDeLíneas)".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-243">In the tree, select 'Archive\Number of lines(NumberOfLines)'.</span></span>
60. <span data-ttu-id="3c9c1-244">En el árbol, seleccione "modelo\Encabezado de archivo\Número de líneas".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-244">In the tree, select 'model\Archive header\Number of lines'.</span></span>
61. <span data-ttu-id="3c9c1-245">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-245">Click Bind.</span></span>
62. <span data-ttu-id="3c9c1-246">En el árbol, seleccione "Archivo".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-246">In the tree, select 'Archive'.</span></span>
63. <span data-ttu-id="3c9c1-247">En el árbol, seleccione "modelo\Encabezado de archivo".</span><span class="sxs-lookup"><span data-stu-id="3c9c1-247">In the tree, select 'model\Archive header'.</span></span>
64. <span data-ttu-id="3c9c1-248">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-248">Click Bind.</span></span>
65. <span data-ttu-id="3c9c1-249">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-249">Click Save.</span></span>
66. <span data-ttu-id="3c9c1-250">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-250">Close the page.</span></span>
67. <span data-ttu-id="3c9c1-251">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3c9c1-251">Close the page.</span></span>

