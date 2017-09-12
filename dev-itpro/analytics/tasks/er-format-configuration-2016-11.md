--- 
title: "Crear una configuración de formato para informes electrónicos (ER)"
description: "En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede crear una configuración de formato para realizar informes electrónicos."
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 04817d1f1851e43679995641e8b0ff99edaa83ad
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-format-configuration-for-electronic-reporting-er"></a><span data-ttu-id="49555-103">Crear una configuración de formato para informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="49555-103">Create a format configuration for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="49555-104">En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede crear una configuración de formato para realizar informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="49555-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="49555-105">Esta configuración del formato definirá el formato de los documentos electrónicos que se usan para procesar pagos.</span><span class="sxs-lookup"><span data-stu-id="49555-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="49555-106">En este ejemplo, creará una configuración del formato para la empresa de demostración, Litware, Inc. Para completar estos pasos, debe completar primero los pasos del procedimiento "Asignación de modelos a orígenes de datos seleccionados".</span><span class="sxs-lookup"><span data-stu-id="49555-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the “Map model to selected datasources” procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="49555-107">Creación de una configuración de formato nueva</span><span class="sxs-lookup"><span data-stu-id="49555-107">Create a new format configuration</span></span>
1. <span data-ttu-id="49555-108">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="49555-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="49555-109">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="49555-109">Click Reporting configurations.</span></span>
3. <span data-ttu-id="49555-110">En el árbol, seleccione Pagos (modelo simplificado).</span><span class="sxs-lookup"><span data-stu-id="49555-110">In the tree, select 'Payments (simplified model)'.</span></span>
4. <span data-ttu-id="49555-111">Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="49555-111">Click Create configuration to open the drop dialog.</span></span>
5. <span data-ttu-id="49555-112">En el campo Nuevo, especifique "Formato basado en modelo de datos PaymentModel".</span><span class="sxs-lookup"><span data-stu-id="49555-112">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
6. <span data-ttu-id="49555-113">En el campo Nombre, escriba "BACS (ficticio Reino Unido)".</span><span class="sxs-lookup"><span data-stu-id="49555-113">In the Name field, type 'BACS (UK fictitious)'.</span></span>
    * <span data-ttu-id="49555-114">BACS (ficticio Reino Unido)</span><span class="sxs-lookup"><span data-stu-id="49555-114">BACS (UK fictitious)</span></span>  
7. <span data-ttu-id="49555-115">En el campo Descripción, escriba "Formato de pago de proveedor BACS (ficticio Reino Unido)".</span><span class="sxs-lookup"><span data-stu-id="49555-115">In the Description field, type 'BACS vendor payment format (UK fictitious)'.</span></span>
    * <span data-ttu-id="49555-116">Formato de pago de proveedor BACS (ficticio Reino Unido)</span><span class="sxs-lookup"><span data-stu-id="49555-116">BACS vendor payment format (UK fictitious)</span></span>  
    * <span data-ttu-id="49555-117">El proveedor de configuraciones activo se especifica automáticamente aquí.</span><span class="sxs-lookup"><span data-stu-id="49555-117">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="49555-118">Este proveedor podrá mantener esta configuración.</span><span class="sxs-lookup"><span data-stu-id="49555-118">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="49555-119">Otros proveedores podrán usar esta configuración, pero no podrán mantenerla.</span><span class="sxs-lookup"><span data-stu-id="49555-119">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="49555-120">Se puede definir un formato concreto de documento electrónico.</span><span class="sxs-lookup"><span data-stu-id="49555-120">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="49555-121">Deje este campo en blanco si desea seleccionar un formato en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="49555-121">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="49555-122">En el campo definición del modelo de Datos, introduzca o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="49555-122">In the Data model definition field, enter or select a value.</span></span>
9. <span data-ttu-id="49555-123">Haga clic en Crear configuración.</span><span class="sxs-lookup"><span data-stu-id="49555-123">Click Create configuration.</span></span>
    * <span data-ttu-id="49555-124">Se ha creado una nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="49555-124">A new configuration has been created.</span></span> <span data-ttu-id="49555-125">La versión de borrador se puede usar para almacenar el formato de diseño para gestionar documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="49555-125">The draft version can be used to store the design format for managing electronic documents.</span></span>  

## <a name="design-format-of-electronic-document"></a><span data-ttu-id="49555-126">Diseño del formato de los documentos electrónicos</span><span class="sxs-lookup"><span data-stu-id="49555-126">Design format of electronic document</span></span>
1. <span data-ttu-id="49555-127">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="49555-127">Click Designer.</span></span>
2. <span data-ttu-id="49555-128">Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="49555-128">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="49555-129">En el árbol, seleccione Común\Archivo.</span><span class="sxs-lookup"><span data-stu-id="49555-129">In the tree, select 'Common\File'.</span></span>
4. <span data-ttu-id="49555-130">En el campo Nombre, escriba "Xml".</span><span class="sxs-lookup"><span data-stu-id="49555-130">In the Name field, type 'Xml'.</span></span>
    * <span data-ttu-id="49555-131">XML</span><span class="sxs-lookup"><span data-stu-id="49555-131">Xml</span></span>  
5. <span data-ttu-id="49555-132">En el campo Codificación, escriba "UTF-8".</span><span class="sxs-lookup"><span data-stu-id="49555-132">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="49555-133">UTF-8</span><span class="sxs-lookup"><span data-stu-id="49555-133">UTF-8</span></span>  
6. <span data-ttu-id="49555-134">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-134">Click OK.</span></span>
7. <span data-ttu-id="49555-135">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="49555-135">Click Add to open the drop dialog.</span></span>
8. <span data-ttu-id="49555-136">En el árbol, seleccione XML\Elemento.</span><span class="sxs-lookup"><span data-stu-id="49555-136">In the tree, select 'XML\Element'.</span></span>
9. <span data-ttu-id="49555-137">En el campo Nombre, escriba "Mensaje".</span><span class="sxs-lookup"><span data-stu-id="49555-137">In the Name field, type 'Message'.</span></span>
    * <span data-ttu-id="49555-138">Mensaje</span><span class="sxs-lookup"><span data-stu-id="49555-138">Message</span></span>  
10. <span data-ttu-id="49555-139">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-139">Click OK.</span></span>
11. <span data-ttu-id="49555-140">En el árbol, seleccione 'Xml\Mensaje'.</span><span class="sxs-lookup"><span data-stu-id="49555-140">In the tree, select 'Xml\Message'.</span></span>
12. <span data-ttu-id="49555-141">Haga clic en Agregar elemento.</span><span class="sxs-lookup"><span data-stu-id="49555-141">Click Add Element.</span></span>
13. <span data-ttu-id="49555-142">En el campo Nombre, escriba "ProcessingDate".</span><span class="sxs-lookup"><span data-stu-id="49555-142">In the Name field, type 'ProcessingDate'.</span></span>
    * <span data-ttu-id="49555-143">ProcessingDate</span><span class="sxs-lookup"><span data-stu-id="49555-143">ProcessingDate</span></span>  
14. <span data-ttu-id="49555-144">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-144">Click OK.</span></span>
15. <span data-ttu-id="49555-145">Haga clic en Agregar elemento.</span><span class="sxs-lookup"><span data-stu-id="49555-145">Click Add Element.</span></span>
16. <span data-ttu-id="49555-146">En el campo Nombre, escriba "MessageId".</span><span class="sxs-lookup"><span data-stu-id="49555-146">In the Name field, type 'MessageId'.</span></span>
    * <span data-ttu-id="49555-147">MessageId</span><span class="sxs-lookup"><span data-stu-id="49555-147">MessageId</span></span>  
17. <span data-ttu-id="49555-148">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-148">Click OK.</span></span>
18. <span data-ttu-id="49555-149">Haga clic en Agregar elemento.</span><span class="sxs-lookup"><span data-stu-id="49555-149">Click Add Element.</span></span>
19. <span data-ttu-id="49555-150">En el campo Nombre, escriba "Pagos".</span><span class="sxs-lookup"><span data-stu-id="49555-150">In the Name field, type 'Payments'.</span></span>
    * <span data-ttu-id="49555-151">Pagos</span><span class="sxs-lookup"><span data-stu-id="49555-151">Payments</span></span>  
20. <span data-ttu-id="49555-152">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-152">Click OK.</span></span>
21. <span data-ttu-id="49555-153">En el árbol, seleccione 'Xml\Mensaje\Pagos'.</span><span class="sxs-lookup"><span data-stu-id="49555-153">In the tree, select 'Xml\Message\Payments'.</span></span>
22. <span data-ttu-id="49555-154">Haga clic en Agregar elemento.</span><span class="sxs-lookup"><span data-stu-id="49555-154">Click Add Element.</span></span>
23. <span data-ttu-id="49555-155">En el campo Nombre, escriba "Artículo".</span><span class="sxs-lookup"><span data-stu-id="49555-155">In the Name field, type 'Item'.</span></span>
    * <span data-ttu-id="49555-156">Artículo</span><span class="sxs-lookup"><span data-stu-id="49555-156">Item</span></span>  
24. <span data-ttu-id="49555-157">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-157">Click OK.</span></span>
25. <span data-ttu-id="49555-158">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo".</span><span class="sxs-lookup"><span data-stu-id="49555-158">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
26. <span data-ttu-id="49555-159">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="49555-159">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="49555-160">En el árbol, seleccione XML\Atributo.</span><span class="sxs-lookup"><span data-stu-id="49555-160">In the tree, select 'XML\Attribute'.</span></span>
28. <span data-ttu-id="49555-161">En el campo Nombre, escriba "Id".</span><span class="sxs-lookup"><span data-stu-id="49555-161">In the Name field, type 'Id'.</span></span>
    * <span data-ttu-id="49555-162">Id.</span><span class="sxs-lookup"><span data-stu-id="49555-162">Id</span></span>  
29. <span data-ttu-id="49555-163">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-163">Click OK.</span></span>
30. <span data-ttu-id="49555-164">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="49555-164">Click Add to open the drop dialog.</span></span>
31. <span data-ttu-id="49555-165">En el árbol, seleccione XML\Elemento.</span><span class="sxs-lookup"><span data-stu-id="49555-165">In the tree, select 'XML\Element'.</span></span>
32. <span data-ttu-id="49555-166">En el campo Nombre, escriba "Proveedor".</span><span class="sxs-lookup"><span data-stu-id="49555-166">In the Name field, type 'Vendor'.</span></span>
    * <span data-ttu-id="49555-167">Proveedor</span><span class="sxs-lookup"><span data-stu-id="49555-167">Vendor</span></span>  
33. <span data-ttu-id="49555-168">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-168">Click OK.</span></span>
34. <span data-ttu-id="49555-169">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor".</span><span class="sxs-lookup"><span data-stu-id="49555-169">In the tree, select 'Xml\Message\Payments\Item\Vendor'.</span></span>
35. <span data-ttu-id="49555-170">Haga clic en Agregar elemento.</span><span class="sxs-lookup"><span data-stu-id="49555-170">Click Add Element.</span></span>
36. <span data-ttu-id="49555-171">En el campo Nombre, escriba "Nombre".</span><span class="sxs-lookup"><span data-stu-id="49555-171">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="49555-172">Nombre</span><span class="sxs-lookup"><span data-stu-id="49555-172">Name</span></span>  
37. <span data-ttu-id="49555-173">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-173">Click OK.</span></span>
38. <span data-ttu-id="49555-174">Haga clic en Agregar elemento.</span><span class="sxs-lookup"><span data-stu-id="49555-174">Click Add Element.</span></span>
39. <span data-ttu-id="49555-175">En el campo Nombre, escriba "Banco".</span><span class="sxs-lookup"><span data-stu-id="49555-175">In the Name field, type 'Bank'.</span></span>
    * <span data-ttu-id="49555-176">Banco</span><span class="sxs-lookup"><span data-stu-id="49555-176">Bank</span></span>  
40. <span data-ttu-id="49555-177">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-177">Click OK.</span></span>
41. <span data-ttu-id="49555-178">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor\Banco".</span><span class="sxs-lookup"><span data-stu-id="49555-178">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank'.</span></span>
42. <span data-ttu-id="49555-179">Haga clic en Agregar elemento.</span><span class="sxs-lookup"><span data-stu-id="49555-179">Click Add Element.</span></span>
43. <span data-ttu-id="49555-180">En el campo Nombre, especifique "RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="49555-180">In the Name field, type 'RoutingNumber'.</span></span>
    * <span data-ttu-id="49555-181">RoutingNumber</span><span class="sxs-lookup"><span data-stu-id="49555-181">RoutingNumber</span></span>  
44. <span data-ttu-id="49555-182">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-182">Click OK.</span></span>
45. <span data-ttu-id="49555-183">Haga clic en Agregar elemento.</span><span class="sxs-lookup"><span data-stu-id="49555-183">Click Add Element.</span></span>
46. <span data-ttu-id="49555-184">En el campo Nombre, escriba "AccountNumber".</span><span class="sxs-lookup"><span data-stu-id="49555-184">In the Name field, type 'AccountNumber'.</span></span>
    * <span data-ttu-id="49555-185">AccountNumber</span><span class="sxs-lookup"><span data-stu-id="49555-185">AccountNumber</span></span>  
47. <span data-ttu-id="49555-186">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-186">Click OK.</span></span>
48. <span data-ttu-id="49555-187">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor".</span><span class="sxs-lookup"><span data-stu-id="49555-187">In the tree, select 'Xml\Message\Payments\Item\Vendor'.</span></span>
49. <span data-ttu-id="49555-188">Haga clic en Copiar.</span><span class="sxs-lookup"><span data-stu-id="49555-188">Click Copy.</span></span>
50. <span data-ttu-id="49555-189">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo".</span><span class="sxs-lookup"><span data-stu-id="49555-189">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
51. <span data-ttu-id="49555-190">Haga clic en Pegar.</span><span class="sxs-lookup"><span data-stu-id="49555-190">Click Paste.</span></span>
52. <span data-ttu-id="49555-191">En el campo Nombre, escriba "Pagador".</span><span class="sxs-lookup"><span data-stu-id="49555-191">In the Name field, type 'Payer'.</span></span>
    * <span data-ttu-id="49555-192">Pagador</span><span class="sxs-lookup"><span data-stu-id="49555-192">Payer</span></span>  
53. <span data-ttu-id="49555-193">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo".</span><span class="sxs-lookup"><span data-stu-id="49555-193">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
54. <span data-ttu-id="49555-194">Haga clic en Agregar elemento.</span><span class="sxs-lookup"><span data-stu-id="49555-194">Click Add Element.</span></span>
55. <span data-ttu-id="49555-195">En el campo Nombre, escriba "Divisa".</span><span class="sxs-lookup"><span data-stu-id="49555-195">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="49555-196">Divisa</span><span class="sxs-lookup"><span data-stu-id="49555-196">Currency</span></span>  
56. <span data-ttu-id="49555-197">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-197">Click OK.</span></span>
57. <span data-ttu-id="49555-198">Haga clic en Agregar elemento.</span><span class="sxs-lookup"><span data-stu-id="49555-198">Click Add Element.</span></span>
58. <span data-ttu-id="49555-199">En el campo Nombre, escriba "Descripción".</span><span class="sxs-lookup"><span data-stu-id="49555-199">In the Name field, type 'Description'.</span></span>
    * <span data-ttu-id="49555-200">Descripción</span><span class="sxs-lookup"><span data-stu-id="49555-200">Description</span></span>  
59. <span data-ttu-id="49555-201">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-201">Click OK.</span></span>
60. <span data-ttu-id="49555-202">Haga clic en Agregar elemento.</span><span class="sxs-lookup"><span data-stu-id="49555-202">Click Add Element.</span></span>
61. <span data-ttu-id="49555-203">En el campo Nombre, escriba "TransDate".</span><span class="sxs-lookup"><span data-stu-id="49555-203">In the Name field, type 'TransDate'.</span></span>
    * <span data-ttu-id="49555-204">TransDate</span><span class="sxs-lookup"><span data-stu-id="49555-204">TransDate</span></span>  
62. <span data-ttu-id="49555-205">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-205">Click OK.</span></span>
63. <span data-ttu-id="49555-206">Haga clic en Agregar elemento.</span><span class="sxs-lookup"><span data-stu-id="49555-206">Click Add Element.</span></span>
64. <span data-ttu-id="49555-207">En el campo Nombre, escriba "Importe".</span><span class="sxs-lookup"><span data-stu-id="49555-207">In the Name field, type 'Amount'.</span></span>
    * <span data-ttu-id="49555-208">Importe</span><span class="sxs-lookup"><span data-stu-id="49555-208">Amount</span></span>  
65. <span data-ttu-id="49555-209">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-209">Click OK.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="49555-210">Preparación de los componentes de formato que asignar a los elementos del modelo de datos</span><span class="sxs-lookup"><span data-stu-id="49555-210">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="49555-211">En el árbol, seleccione "Xml\Mensaje\ProcessingDate".</span><span class="sxs-lookup"><span data-stu-id="49555-211">In the tree, select 'Xml\Message\ProcessingDate'.</span></span>
2. <span data-ttu-id="49555-212">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="49555-212">Click Add to open the drop dialog.</span></span>
3. <span data-ttu-id="49555-213">En el árbol, seleccione "Texto\DateTime".</span><span class="sxs-lookup"><span data-stu-id="49555-213">In the tree, select 'Text\DateTime'.</span></span>
4. <span data-ttu-id="49555-214">En el campo Formato, escriba "aaaa-MM-dd".</span><span class="sxs-lookup"><span data-stu-id="49555-214">In the Format field, type 'yyyy-MM-dd'.</span></span>
    * <span data-ttu-id="49555-215">dd/mm/aaaa</span><span class="sxs-lookup"><span data-stu-id="49555-215">yyyy-MM-dd</span></span>  
5. <span data-ttu-id="49555-216">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-216">Click OK.</span></span>
6. <span data-ttu-id="49555-217">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\TransDate".</span><span class="sxs-lookup"><span data-stu-id="49555-217">In the tree, select 'Xml\Message\Payments\Item\TransDate'.</span></span>
7. <span data-ttu-id="49555-218">Haga clic en DateTime.</span><span class="sxs-lookup"><span data-stu-id="49555-218">Click Add DateTime.</span></span>
8. <span data-ttu-id="49555-219">En el campo Formato, escriba "aaaa-MM-dd".</span><span class="sxs-lookup"><span data-stu-id="49555-219">In the Format field, type 'yyyy-MM-dd'.</span></span>
    * <span data-ttu-id="49555-220">dd/mm/aaaa</span><span class="sxs-lookup"><span data-stu-id="49555-220">yyyy-MM-dd</span></span>  
9. <span data-ttu-id="49555-221">En el campo tipo DateTime, seleccione "Fecha".</span><span class="sxs-lookup"><span data-stu-id="49555-221">In the DateTime type field, select 'Date'.</span></span>
10. <span data-ttu-id="49555-222">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-222">Click OK.</span></span>
11. <span data-ttu-id="49555-223">En el árbol, seleccione "Xml\Mensaje\MessageId".</span><span class="sxs-lookup"><span data-stu-id="49555-223">In the tree, select 'Xml\Message\MessageId'.</span></span>
12. <span data-ttu-id="49555-224">Haga clic en Agregar para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="49555-224">Click Add to open the drop dialog.</span></span>
13. <span data-ttu-id="49555-225">En el árbol, seleccione "Texto\Cadena".</span><span class="sxs-lookup"><span data-stu-id="49555-225">In the tree, select 'Text\String'.</span></span>
14. <span data-ttu-id="49555-226">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-226">Click OK.</span></span>
15. <span data-ttu-id="49555-227">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor\Nombre".</span><span class="sxs-lookup"><span data-stu-id="49555-227">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name'.</span></span>
16. <span data-ttu-id="49555-228">Haga clic en Agregar cadena.</span><span class="sxs-lookup"><span data-stu-id="49555-228">Click Add String.</span></span>
17. <span data-ttu-id="49555-229">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-229">Click OK.</span></span>
18. <span data-ttu-id="49555-230">En el árbol, seleccione 'Xml\Mensaje\Pagos\Artículo\Proveedor\RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="49555-230">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber'.</span></span>
19. <span data-ttu-id="49555-231">Haga clic en Agregar cadena.</span><span class="sxs-lookup"><span data-stu-id="49555-231">Click Add String.</span></span>
20. <span data-ttu-id="49555-232">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-232">Click OK.</span></span>
21. <span data-ttu-id="49555-233">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor\Banco\AccountNumber".</span><span class="sxs-lookup"><span data-stu-id="49555-233">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\AccountNumber'.</span></span>
22. <span data-ttu-id="49555-234">Haga clic en Agregar cadena.</span><span class="sxs-lookup"><span data-stu-id="49555-234">Click Add String.</span></span>
23. <span data-ttu-id="49555-235">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-235">Click OK.</span></span>
24. <span data-ttu-id="49555-236">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Pagador\Nombre".</span><span class="sxs-lookup"><span data-stu-id="49555-236">In the tree, select 'Xml\Message\Payments\Item\Payer\Name'.</span></span>
25. <span data-ttu-id="49555-237">Haga clic en Agregar cadena.</span><span class="sxs-lookup"><span data-stu-id="49555-237">Click Add String.</span></span>
26. <span data-ttu-id="49555-238">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-238">Click OK.</span></span>
27. <span data-ttu-id="49555-239">En el árbol, seleccione 'Xml\Mensaje\Pagos\Artículo\Pagador\RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="49555-239">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\RoutingNumber'.</span></span>
28. <span data-ttu-id="49555-240">Haga clic en Agregar cadena.</span><span class="sxs-lookup"><span data-stu-id="49555-240">Click Add String.</span></span>
29. <span data-ttu-id="49555-241">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-241">Click OK.</span></span>
30. <span data-ttu-id="49555-242">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Pagador\Banco\AccountNumber".</span><span class="sxs-lookup"><span data-stu-id="49555-242">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\AccountNumber'.</span></span>
31. <span data-ttu-id="49555-243">Haga clic en Agregar cadena.</span><span class="sxs-lookup"><span data-stu-id="49555-243">Click Add String.</span></span>
32. <span data-ttu-id="49555-244">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-244">Click OK.</span></span>
33. <span data-ttu-id="49555-245">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Moneda".</span><span class="sxs-lookup"><span data-stu-id="49555-245">In the tree, select 'Xml\Message\Payments\Item\Currency'.</span></span>
34. <span data-ttu-id="49555-246">Haga clic en Agregar cadena.</span><span class="sxs-lookup"><span data-stu-id="49555-246">Click Add String.</span></span>
35. <span data-ttu-id="49555-247">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-247">Click OK.</span></span>
36. <span data-ttu-id="49555-248">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Descripción".</span><span class="sxs-lookup"><span data-stu-id="49555-248">In the tree, select 'Xml\Message\Payments\Item\Description'.</span></span>
37. <span data-ttu-id="49555-249">Haga clic en Agregar cadena.</span><span class="sxs-lookup"><span data-stu-id="49555-249">Click Add String.</span></span>
38. <span data-ttu-id="49555-250">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-250">Click OK.</span></span>
39. <span data-ttu-id="49555-251">En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Importe".</span><span class="sxs-lookup"><span data-stu-id="49555-251">In the tree, select 'Xml\Message\Payments\Item\Amount'.</span></span>
40. <span data-ttu-id="49555-252">Haga clic en Agregar cadena.</span><span class="sxs-lookup"><span data-stu-id="49555-252">Click Add String.</span></span>
41. <span data-ttu-id="49555-253">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="49555-253">Click OK.</span></span>
42. <span data-ttu-id="49555-254">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="49555-254">Click Save.</span></span>
43. <span data-ttu-id="49555-255">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="49555-255">Close the page.</span></span>


