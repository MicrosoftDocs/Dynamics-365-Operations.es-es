---
title: Modificar modelos y asignaciones para generar documentos que tengan datos de la aplicación
description: 'Para completar los pasos de este procedimiento, primero debe completar el procedimiento, "ER: Generar documentos con la actualización de datos de la aplicación (Parte 2 - Generar documentos)".'
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a4546de2c5c1773aadce0ec084ee7058ff2ae153
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141888"
---
# <a name="modify-models-and-mappings-to-generate-documents-that-have-application-data"></a><span data-ttu-id="acf58-103">Modificar modelos y asignaciones para generar documentos que tengan datos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="acf58-103">Modify models and mappings to generate documents that have application data</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="acf58-104">Para completar los pasos de este procedimiento, primero debe completar el procedimiento, "ER: Generar documentos con la actualización de datos de la aplicación (Parte 2: Generar documentos)".</span><span class="sxs-lookup"><span data-stu-id="acf58-104">To complete the steps in this procedure, you must first complete the procedure, "ER Generate documents with application data update (Part 2: Generate documents)".</span></span> 

<span data-ttu-id="acf58-105">Los pasos de este procedimiento explican cómo diseñar las configuraciones de los informes electrónicos (ER) para generar un documento electrónico y actualizar los datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="acf58-105">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document and update application data.</span></span> <span data-ttu-id="acf58-106">En este procedimiento, se modificarán las configuraciones de ER para comenzar a utilizarlas para generar documentos electrónicos y actualizar los datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="acf58-106">In this procedure, you will modify the ER configurations to start using them to generate electronic documents and update application data.</span></span> <span data-ttu-id="acf58-107">Este procedimiento se ha creado para los usuarios con los roles Administrador del sistema o Desarrollador de informes electrónicos asignados.</span><span class="sxs-lookup"><span data-stu-id="acf58-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="acf58-108">Estos pasos se pueden completar mediante el conjunto de datos de DEMF.</span><span class="sxs-lookup"><span data-stu-id="acf58-108">These steps can be completed using the DEMF dataset.</span></span>


## <a name="modify-data-model"></a><span data-ttu-id="acf58-109">Modificar modelos de datos</span><span class="sxs-lookup"><span data-stu-id="acf58-109">Modify data model</span></span>
1. <span data-ttu-id="acf58-110">Vaya a Administración de la organización > Informes electrónicos > Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="acf58-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="acf58-111">En el árbol, seleccione "Intrastat (modelo)".</span><span class="sxs-lookup"><span data-stu-id="acf58-111">In the tree, select 'Intrastat (model)'.</span></span>
    * <span data-ttu-id="acf58-112">Ampliará cómo se usa el modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="acf58-112">You will extend how you use the data model.</span></span> <span data-ttu-id="acf58-113">Además de usarlo como origen de datos para generar el informe de Intrastat, el modelo de datos se usará para obtener detalles sobre el proceso de generación de informes de Intrastat.</span><span class="sxs-lookup"><span data-stu-id="acf58-113">Besides using it as data source to generate the Intrastat report, the data model will be used to collect details about the Intrastat reporting process.</span></span> <span data-ttu-id="acf58-114">Los detalles se usarán después para actualizar los datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="acf58-114">The details will then be used to update application data.</span></span>   
3. <span data-ttu-id="acf58-115">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="acf58-115">Click Designer.</span></span>
4. <span data-ttu-id="acf58-116">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="acf58-116">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="acf58-117">En el campo "Nuevo nodo como", escriba "Raíz del modelo".</span><span class="sxs-lookup"><span data-stu-id="acf58-117">In the New node as a field, enter 'Model root'.</span></span>
6. <span data-ttu-id="acf58-118">En el campo Nombre, escriba "Para actualizar datos de la aplicación".</span><span class="sxs-lookup"><span data-stu-id="acf58-118">In the Name field, type 'For application data update'.</span></span>
    * <span data-ttu-id="acf58-119">Para la actualización de los datos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="acf58-119">For application data update</span></span>  
7. <span data-ttu-id="acf58-120">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="acf58-120">Click Add.</span></span>
8. <span data-ttu-id="acf58-121">En el árbol, seleccione “Para actualizar datos de la aplicación".</span><span class="sxs-lookup"><span data-stu-id="acf58-121">In the tree, select 'For application data update'.</span></span>
    * <span data-ttu-id="acf58-122">Este nuevo elemento raíz se agrega para especificar el flujo de datos para desplazar datos del informe de Intrastat (usado como origen de datos) a las tablas de la aplicación (el destino de la actualización).</span><span class="sxs-lookup"><span data-stu-id="acf58-122">This new root item is added to specify the data flow for moving data from the Intrastat report (used as a data source) to the application tables (the update destination).</span></span> <span data-ttu-id="acf58-123">Tenga en cuenta que los distintos elementos raíz se deben utilizar para obtener los datos que se envían al documento de salida y para recopilar datos del documento que se usa para actualizar los datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="acf58-123">Note that different root items must be used for getting data that is posted to the outgoing document and for getting data from the document that is used to update application data.</span></span>   
9. <span data-ttu-id="acf58-124">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="acf58-124">Click New to open the drop dialog.</span></span>
10. <span data-ttu-id="acf58-125">En el campo Nombre, escriba "Encabezado de archivo".</span><span class="sxs-lookup"><span data-stu-id="acf58-125">In the Name field, type 'Archive header'.</span></span>
    * <span data-ttu-id="acf58-126">Encabezado de archivo</span><span class="sxs-lookup"><span data-stu-id="acf58-126">Archive header</span></span>  
11. <span data-ttu-id="acf58-127">En el campo Tipo de artículo, seleccione Lista de registros.</span><span class="sxs-lookup"><span data-stu-id="acf58-127">In the Item type field, select 'Record list'.</span></span>
12. <span data-ttu-id="acf58-128">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="acf58-128">Click Add.</span></span>
    * <span data-ttu-id="acf58-129">Dado que creará un registro para cada informe de Intrastat que se genere, debe crear un elemento nuevo para eso.</span><span class="sxs-lookup"><span data-stu-id="acf58-129">Because you will create a record for each Intrastat report that is generated, you must create a new item for that.</span></span>  
13. <span data-ttu-id="acf58-130">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="acf58-130">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="acf58-131">En el campo Nombre, introduzca "Nombre de archivo".</span><span class="sxs-lookup"><span data-stu-id="acf58-131">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="acf58-132">Nombre de archivo</span><span class="sxs-lookup"><span data-stu-id="acf58-132">File name</span></span>  
15. <span data-ttu-id="acf58-133">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="acf58-133">In the Item type field, select 'String'.</span></span>
16. <span data-ttu-id="acf58-134">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="acf58-134">Click Add.</span></span>
17. <span data-ttu-id="acf58-135">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="acf58-135">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="acf58-136">En el campo Nombre, escriba "Número de líneas".</span><span class="sxs-lookup"><span data-stu-id="acf58-136">In the Name field, type 'Number of lines'.</span></span>
    * <span data-ttu-id="acf58-137">Número de líneas</span><span class="sxs-lookup"><span data-stu-id="acf58-137">Number of lines</span></span>  
19. <span data-ttu-id="acf58-138">En el campo Tipo de artículo, seleccione "Entero".</span><span class="sxs-lookup"><span data-stu-id="acf58-138">In the Item type field, select 'Integer'.</span></span>
20. <span data-ttu-id="acf58-139">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="acf58-139">Click Add.</span></span>
    * <span data-ttu-id="acf58-140">Agregue este artículo para representar el número de transacciones de Intrastat que se registran durante el proceso actual de generación de informes.</span><span class="sxs-lookup"><span data-stu-id="acf58-140">Add this item to represent the number of Intrastat transactions that are reported during the current reporting process.</span></span>  
21. <span data-ttu-id="acf58-141">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="acf58-141">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="acf58-142">En el campo Nombre, escriba "Líneas de archivo".</span><span class="sxs-lookup"><span data-stu-id="acf58-142">In the Name field, type 'Archive lines'.</span></span>
    * <span data-ttu-id="acf58-143">Líneas de archivo</span><span class="sxs-lookup"><span data-stu-id="acf58-143">Archive lines</span></span>  
23. <span data-ttu-id="acf58-144">En el campo Tipo de artículo, seleccione Lista de registros.</span><span class="sxs-lookup"><span data-stu-id="acf58-144">In the Item type field, select 'Record list'.</span></span>
24. <span data-ttu-id="acf58-145">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="acf58-145">Click Add.</span></span>
    * <span data-ttu-id="acf58-146">Agregue este artículo para representar la lista de transacciones de Intrastat que se registran durante el proceso actual de generación de informes.</span><span class="sxs-lookup"><span data-stu-id="acf58-146">Add this item to represent the list of Intrastat transactions that are reported during the current reporting process.</span></span>  
25. <span data-ttu-id="acf58-147">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="acf58-147">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="acf58-148">En el campo Nombre, escriba "Importe".</span><span class="sxs-lookup"><span data-stu-id="acf58-148">In the Name field, type 'Amount'.</span></span>
    * <span data-ttu-id="acf58-149">Importe</span><span class="sxs-lookup"><span data-stu-id="acf58-149">Amount</span></span>  
27. <span data-ttu-id="acf58-150">En el campo Tipo de artículo, seleccione Real.</span><span class="sxs-lookup"><span data-stu-id="acf58-150">In the Item type field, select 'Real'.</span></span>
28. <span data-ttu-id="acf58-151">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="acf58-151">Click Add.</span></span>
29. <span data-ttu-id="acf58-152">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="acf58-152">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="acf58-153">En el campo Nombre, escriba “Id. de reg. de materiales”.</span><span class="sxs-lookup"><span data-stu-id="acf58-153">In the Name field, type 'Commodity rec id'.</span></span>
    * <span data-ttu-id="acf58-154">Id. de reg de mercancías</span><span class="sxs-lookup"><span data-stu-id="acf58-154">Commodity rec id</span></span>  
31. <span data-ttu-id="acf58-155">En el campo Tipo de artículo, seleccione "Int64".</span><span class="sxs-lookup"><span data-stu-id="acf58-155">In the Item type field, select 'Int64'.</span></span>
32. <span data-ttu-id="acf58-156">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="acf58-156">Click Add.</span></span>
33. <span data-ttu-id="acf58-157">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="acf58-157">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="acf58-158">En el campo Nombre, escriba "Número de elemento".</span><span class="sxs-lookup"><span data-stu-id="acf58-158">In the Name field, type 'Item number'.</span></span>
    * <span data-ttu-id="acf58-159">código de artículo</span><span class="sxs-lookup"><span data-stu-id="acf58-159">Item number</span></span>  
35. <span data-ttu-id="acf58-160">En el campo Tipo de artículo, seleccione Cadena.</span><span class="sxs-lookup"><span data-stu-id="acf58-160">In the Item type field, select 'String'.</span></span>
36. <span data-ttu-id="acf58-161">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="acf58-161">Click Add.</span></span>
37. <span data-ttu-id="acf58-162">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="acf58-162">Click Save.</span></span>
38. <span data-ttu-id="acf58-163">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="acf58-163">Close the page.</span></span>

## <a name="modify-model-mapping"></a><span data-ttu-id="acf58-164">Modificar asignación de modelos</span><span class="sxs-lookup"><span data-stu-id="acf58-164">Modify model mapping</span></span>
1. <span data-ttu-id="acf58-165">En el árbol, expanda "Intrastat (modelo)".</span><span class="sxs-lookup"><span data-stu-id="acf58-165">In the tree, expand 'Intrastat (model)'.</span></span>
2. <span data-ttu-id="acf58-166">En el árbol, seleccione "Intrastat (modelo)\Intrastat (asignación)".</span><span class="sxs-lookup"><span data-stu-id="acf58-166">In the tree, select 'Intrastat (model)\Intrastat (mapping)'.</span></span>
    * <span data-ttu-id="acf58-167">Permite modificar la asignación del modelo existente para comenzar a utilizarlo para la actualización de los datos de la aplicación y para archivar los detalles de informes de Intrastat.</span><span class="sxs-lookup"><span data-stu-id="acf58-167">Modify the existing model mapping to start using it for  the application data update and to archive Intrastat reporting details.</span></span>  
3. <span data-ttu-id="acf58-168">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="acf58-168">Click Designer.</span></span>
4. <span data-ttu-id="acf58-169">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="acf58-169">Click New.</span></span>
5. <span data-ttu-id="acf58-170">En el campo Nombre, escriba "Actualizar archivado".</span><span class="sxs-lookup"><span data-stu-id="acf58-170">In the Name field, type 'Update archive'.</span></span>
    * <span data-ttu-id="acf58-171">Actualizar archivo</span><span class="sxs-lookup"><span data-stu-id="acf58-171">Update archive</span></span>  
6. <span data-ttu-id="acf58-172">En el campo Dirección, seleccione "A destino".</span><span class="sxs-lookup"><span data-stu-id="acf58-172">In the Direction field, select 'To destination'.</span></span>
7. <span data-ttu-id="acf58-173">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="acf58-173">Click Save.</span></span>
    * <span data-ttu-id="acf58-174">Esta nueva asignación especifica el flujo de datos para desplazar datos (detalles del informe de Intrastat) desde el modelo de datos a las tablas de la aplicación (el destino de la actualización).</span><span class="sxs-lookup"><span data-stu-id="acf58-174">This new mapping specifies the data flow for moving data (Intrastat reporting details) from the data model to the application tables (the update destination).</span></span> <span data-ttu-id="acf58-175">Tenga en cuenta que los diferentes elementos raíz del modelo se deben utilizar para recopilar datos de la aplicación para el proceso de generación de informes y después usar los datos del modelo para la actualización de los datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="acf58-175">Note that different model's root items must be used to get data from the application for the reporting process and then use the data from data model for the application data update.</span></span>   
8. <span data-ttu-id="acf58-176">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="acf58-176">Click Designer.</span></span>
9. <span data-ttu-id="acf58-177">En el árbol, seleccione "Modelo de datos\Modelo de datos".</span><span class="sxs-lookup"><span data-stu-id="acf58-177">In the tree, select 'Data model\Data model'.</span></span>
    * <span data-ttu-id="acf58-178">Agregar el origen de los datos necesario.</span><span class="sxs-lookup"><span data-stu-id="acf58-178">Add the required data source.</span></span> <span data-ttu-id="acf58-179">Este es el modelo de datos que contiene los detalles de las transacciones de intrastat registradas que deben archivarse.</span><span class="sxs-lookup"><span data-stu-id="acf58-179">This is the data model that contains details of the reported Intrastat transactions that must be archived.</span></span>  
10. <span data-ttu-id="acf58-180">Haga clic en Agregar raíz.</span><span class="sxs-lookup"><span data-stu-id="acf58-180">Click Add root.</span></span>
11. <span data-ttu-id="acf58-181">En el campo Nombre, escriba "Modelo".</span><span class="sxs-lookup"><span data-stu-id="acf58-181">In the Name field, type 'model'.</span></span>
    * <span data-ttu-id="acf58-182">modelo</span><span class="sxs-lookup"><span data-stu-id="acf58-182">model</span></span>  
12. <span data-ttu-id="acf58-183">En el campo de Definición, especifique o seleccione el valor “Para la actualización de datos de la aplicación".</span><span class="sxs-lookup"><span data-stu-id="acf58-183">In the Definition field, enter or select the value 'For application data update'.</span></span>
    * <span data-ttu-id="acf58-184">Para la actualización de los datos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="acf58-184">For application data update</span></span>  
13. <span data-ttu-id="acf58-185">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="acf58-185">Click OK.</span></span>
14. <span data-ttu-id="acf58-186">En el árbol , expanda "modelo".</span><span class="sxs-lookup"><span data-stu-id="acf58-186">In the tree, expand 'model'.</span></span>
15. <span data-ttu-id="acf58-187">En el árbol, seleccione el apartado "Funciones\Campo calculado".</span><span class="sxs-lookup"><span data-stu-id="acf58-187">In the tree, select 'Functions\Calculated field'.</span></span>
16. <span data-ttu-id="acf58-188">En el árbol, seleccione "modelo\Encabezado de archivo".</span><span class="sxs-lookup"><span data-stu-id="acf58-188">In the tree, select 'model\Archive header'.</span></span>
17. <span data-ttu-id="acf58-189">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="acf58-189">Click Add.</span></span>
    * <span data-ttu-id="acf58-190">Dado que desea enumerar las transacciones de Intrastat registradas para archivar, el origen de datos adecuado se debe suma.</span><span class="sxs-lookup"><span data-stu-id="acf58-190">Because you want to enumerate reported Intrastat transactions for archiving, the appropriate data source must be added.</span></span>  
18. <span data-ttu-id="acf58-191">En el campo Nombre, escriba "Líneas enumeradas".</span><span class="sxs-lookup"><span data-stu-id="acf58-191">In the Name field, type 'Enumerated lines'.</span></span>
    * <span data-ttu-id="acf58-192">Líneas enumeradas</span><span class="sxs-lookup"><span data-stu-id="acf58-192">Enumerated lines</span></span>  
19. <span data-ttu-id="acf58-193">Haga clic en Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="acf58-193">Click Edit formula.</span></span>
20. <span data-ttu-id="acf58-194">En el árbol , seleccione "Lista\ENUMERAR".</span><span class="sxs-lookup"><span data-stu-id="acf58-194">In the tree, select 'List\ENUMERATE'.</span></span>
21. <span data-ttu-id="acf58-195">Haga clic en Agregar función.</span><span class="sxs-lookup"><span data-stu-id="acf58-195">Click Add function.</span></span>
22. <span data-ttu-id="acf58-196">En el árbol , expanda "modelo".</span><span class="sxs-lookup"><span data-stu-id="acf58-196">In the tree, expand 'model'.</span></span>
23. <span data-ttu-id="acf58-197">En el árbol, expanda "modelo\Encabezado de archivo".</span><span class="sxs-lookup"><span data-stu-id="acf58-197">In the tree, expand 'model\Archive header'.</span></span>
24. <span data-ttu-id="acf58-198">En el árbol, seleccione "modelo\Encabezado de archivo\Líneas de archivo".</span><span class="sxs-lookup"><span data-stu-id="acf58-198">In the tree, select 'model\Archive header\Archive lines'.</span></span>
25. <span data-ttu-id="acf58-199">Haga clic en Agregar origen de datos.</span><span class="sxs-lookup"><span data-stu-id="acf58-199">Click Add data source.</span></span>
26. <span data-ttu-id="acf58-200">En el campo Fórmula, especifique "ENUMERATE(model.'Archive header'.'Archive lines')".</span><span class="sxs-lookup"><span data-stu-id="acf58-200">In the Formula field, enter 'ENUMERATE(model.'Archive header'.'Archive lines')'.</span></span>
    * <span data-ttu-id="acf58-201">ENUMERE (modelo. “Encabezado de archivo”. “Líneas del archivo")</span><span class="sxs-lookup"><span data-stu-id="acf58-201">ENUMERATE(model.'Archive header'.'Archive lines')</span></span>  
27. <span data-ttu-id="acf58-202">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="acf58-202">Click Save.</span></span>
28. <span data-ttu-id="acf58-203">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="acf58-203">Close the page.</span></span>
29. <span data-ttu-id="acf58-204">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="acf58-204">Click OK.</span></span>
30. <span data-ttu-id="acf58-205">Haga clic en Agregar destino.</span><span class="sxs-lookup"><span data-stu-id="acf58-205">Click Add destination.</span></span>
    * <span data-ttu-id="acf58-206">Agregue las tablas de la aplicación como destinos requeridos que necesitan actualizaciones para archivar los detalles de las transacciones de Intrastat registradas.</span><span class="sxs-lookup"><span data-stu-id="acf58-206">Add application tables as required destinations that require updates to archive details of reported Intrastat transactions.</span></span>  
31. <span data-ttu-id="acf58-207">En el campo Nombre, escriba "Archivo".</span><span class="sxs-lookup"><span data-stu-id="acf58-207">In the Name field, type 'Archive'.</span></span>
    * <span data-ttu-id="acf58-208">Archivar</span><span class="sxs-lookup"><span data-stu-id="acf58-208">Archive</span></span>  
32. <span data-ttu-id="acf58-209">En el campo Tabla, escriba "IntrastatArchiveGeneral".</span><span class="sxs-lookup"><span data-stu-id="acf58-209">In the Table name field, type 'IntrastatArchiveGeneral'.</span></span>
    * <span data-ttu-id="acf58-210">IntrastatArchivoGeneral</span><span class="sxs-lookup"><span data-stu-id="acf58-210">IntrastatArchiveGeneral</span></span>  
    * <span data-ttu-id="acf58-211">Conserve la acción de registro “Insertar” para poder agregar registros durante el archivado de detalles de cada proceso de generación de informes de Intrastat.</span><span class="sxs-lookup"><span data-stu-id="acf58-211">Keep the record action 'Insert' so you can add records during the detail archiving of each Intrastat reporting process.</span></span>  
33. <span data-ttu-id="acf58-212">Seleccione Sí en el campo Registrar en registro de información.</span><span class="sxs-lookup"><span data-stu-id="acf58-212">Select Yes in the Record infolog field.</span></span>
    * <span data-ttu-id="acf58-213">Seleccione Si para obtener información sobre los problemas con la actualización de los datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="acf58-213">Select Yes to get information about issues with the application data update.</span></span>  
34. <span data-ttu-id="acf58-214">Seleccione Sí en el campo Omitir validación de acciones del registro.</span><span class="sxs-lookup"><span data-stu-id="acf58-214">Select Yes in the Skip record action validation field.</span></span>
    * <span data-ttu-id="acf58-215">Seleccione Sí para suprimir errores de validación sobre campo vacío de "archivo Intrastat ID“.</span><span class="sxs-lookup"><span data-stu-id="acf58-215">Select Yes to suppress validation errors about the empty 'Intrastat archive ID' field.</span></span> <span data-ttu-id="acf58-216">Esto se hace después de que se agreguen los registros, en función de la configuración del número de secuencia que esté configurado para esta tabla en el formulario de Parámetros de comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="acf58-216">This will be done after records are added, based on the sequence number settings that are configured for this table in the Foreign trade parameters form.</span></span>  
35. <span data-ttu-id="acf58-217">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="acf58-217">Click OK.</span></span>
    * <span data-ttu-id="acf58-218">Vincular elementos del origen de datos agregados (el modelo filtrado basado en el elemento raíz seleccionado) con los elementos de destino agregados.</span><span class="sxs-lookup"><span data-stu-id="acf58-218">Bind elements of the added data source (the filtered model based on the selected root item) with elements from the added destination.</span></span>  
36. <span data-ttu-id="acf58-219">En el árbol, expanda "Archivo".</span><span class="sxs-lookup"><span data-stu-id="acf58-219">In the tree, expand 'Archive'.</span></span>
37. <span data-ttu-id="acf58-220">En el árbol, expanda "Archivo\<Relaciones".</span><span class="sxs-lookup"><span data-stu-id="acf58-220">In the tree, expand 'Archive\<Relations'.</span></span>
38. <span data-ttu-id="acf58-221">En el árbol, expanda "Archivo\<Relaciones\DetalleArchivoIntrastat".</span><span class="sxs-lookup"><span data-stu-id="acf58-221">In the tree, expand 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
39. <span data-ttu-id="acf58-222">En el árbol, seleccione "Archivo\<Relaciones\DetalleArchivoIntrastat\Cantidad(CantidadMST)".</span><span class="sxs-lookup"><span data-stu-id="acf58-222">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Amount(AmountMST)'.</span></span>
40. <span data-ttu-id="acf58-223">En el árbol, expanda "modelo\Encabezado de archivo\Líneas enumeradas".</span><span class="sxs-lookup"><span data-stu-id="acf58-223">In the tree, expand 'model\Archive header\Enumerated lines'.</span></span>
41. <span data-ttu-id="acf58-224">En el árbol, expanda "modelo\Encabezado de archivo\Líneas enumeradas\Valor".</span><span class="sxs-lookup"><span data-stu-id="acf58-224">In the tree, expand 'model\Archive header\Enumerated lines\Value'.</span></span>
42. <span data-ttu-id="acf58-225">En el árbol, seleccione"modelo\Encabezado de archivo\Líneas enumeradas\Valor\Importe".</span><span class="sxs-lookup"><span data-stu-id="acf58-225">In the tree, select 'model\Archive header\Enumerated lines\Value\Amount'.</span></span>
43. <span data-ttu-id="acf58-226">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="acf58-226">Click Bind.</span></span>
44. <span data-ttu-id="acf58-227">En el árbol, seleccione “Archivo\<Relaciones\DetalleArchivoIntrastat\Productos(ProductosIntrastat)".</span><span class="sxs-lookup"><span data-stu-id="acf58-227">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Commodity(IntrastatCommodity)'.</span></span>
45. <span data-ttu-id="acf58-228">En el árbol, seleccione"modelo\Encabezado de archivo\Líneas enumeradas\Valor\Producto Id reg".</span><span class="sxs-lookup"><span data-stu-id="acf58-228">In the tree, select 'model\Archive header\Enumerated lines\Value\Commodity rec id'.</span></span>
46. <span data-ttu-id="acf58-229">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="acf58-229">Click Bind.</span></span>
47. <span data-ttu-id="acf58-230">En el árbol, seleccione "Archivo\<Relaciones\DetalleArchivoIntrastat\Numero de elemento(IdElemento)".</span><span class="sxs-lookup"><span data-stu-id="acf58-230">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Item number(ItemId)'.</span></span>
48. <span data-ttu-id="acf58-231">En el árbol, seleccione"modelo\Encabezado de archivo\Líneas enumeradas\Valor\Número de elemento".</span><span class="sxs-lookup"><span data-stu-id="acf58-231">In the tree, select 'model\Archive header\Enumerated lines\Value\Item number'.</span></span>
49. <span data-ttu-id="acf58-232">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="acf58-232">Click Bind.</span></span>
50. <span data-ttu-id="acf58-233">En el árbol, seleccione "Archivo\<Relaciones\DetalleArchivoIntrastat\Numero de línea (NúmeroLínea)".</span><span class="sxs-lookup"><span data-stu-id="acf58-233">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Line number(LineNumber)'.</span></span>
51. <span data-ttu-id="acf58-234">En el árbol, seleccione "modelo\Encabezado de archivo\Líneas enumeradas\Número".</span><span class="sxs-lookup"><span data-stu-id="acf58-234">In the tree, select 'model\Archive header\Enumerated lines\Number'.</span></span>
52. <span data-ttu-id="acf58-235">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="acf58-235">Click Bind.</span></span>
53. <span data-ttu-id="acf58-236">En el árbol, seleccione "Archivo\<Relaciones\DetalleArchivoIntrastat".</span><span class="sxs-lookup"><span data-stu-id="acf58-236">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
54. <span data-ttu-id="acf58-237">En el árbol, seleccione "modelo\Encabezado de archivo\Líneas enumeradas".</span><span class="sxs-lookup"><span data-stu-id="acf58-237">In the tree, select 'model\Archive header\Enumerated lines'.</span></span>
55. <span data-ttu-id="acf58-238">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="acf58-238">Click Bind.</span></span>
56. <span data-ttu-id="acf58-239">En el árbol, seleccione "Archivo\Nombre de archivo(NombreArchivo)".</span><span class="sxs-lookup"><span data-stu-id="acf58-239">In the tree, select 'Archive\File name(FileName)'.</span></span>
57. <span data-ttu-id="acf58-240">En el árbol, seleccione "modelo\Encabezado de archivo\Nombre de archivo".</span><span class="sxs-lookup"><span data-stu-id="acf58-240">In the tree, select 'model\Archive header\File name'.</span></span>
58. <span data-ttu-id="acf58-241">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="acf58-241">Click Bind.</span></span>
59. <span data-ttu-id="acf58-242">En el árbol, seleccione "Archivo\Número de líneas(NúmeroDeLíneas)".</span><span class="sxs-lookup"><span data-stu-id="acf58-242">In the tree, select 'Archive\Number of lines(NumberOfLines)'.</span></span>
60. <span data-ttu-id="acf58-243">En el árbol, seleccione "modelo\Encabezado de archivo\Número de líneas".</span><span class="sxs-lookup"><span data-stu-id="acf58-243">In the tree, select 'model\Archive header\Number of lines'.</span></span>
61. <span data-ttu-id="acf58-244">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="acf58-244">Click Bind.</span></span>
62. <span data-ttu-id="acf58-245">En el árbol, seleccione "Archivo".</span><span class="sxs-lookup"><span data-stu-id="acf58-245">In the tree, select 'Archive'.</span></span>
63. <span data-ttu-id="acf58-246">En el árbol, seleccione "modelo\Encabezado de archivo".</span><span class="sxs-lookup"><span data-stu-id="acf58-246">In the tree, select 'model\Archive header'.</span></span>
64. <span data-ttu-id="acf58-247">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="acf58-247">Click Bind.</span></span>
65. <span data-ttu-id="acf58-248">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="acf58-248">Click Save.</span></span>
66. <span data-ttu-id="acf58-249">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="acf58-249">Close the page.</span></span>
67. <span data-ttu-id="acf58-250">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="acf58-250">Close the page.</span></span>

