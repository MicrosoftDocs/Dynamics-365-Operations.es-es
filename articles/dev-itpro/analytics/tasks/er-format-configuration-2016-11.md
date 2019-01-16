--- 
title: "ER Crear una configuración de formato (noviembre de 2016)"
description: "En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede crear una configuración de formato para realizar informes electrónicos."
author: NickSelin
manager: AnnBe
ms.date: 11/27/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 13469aad7fdcefb3a1706eec0527f29968e007eb
ms.openlocfilehash: 10511fe5b936135471b522fc7152a54686a3be87
ms.contentlocale: es-es
ms.lasthandoff: 12/18/2018

---
# <a name="er-create-a-format-configuration-november-2016"></a><span data-ttu-id="a5afd-103">ER Crear una configuración de formato (noviembre de 2016)</span><span class="sxs-lookup"><span data-stu-id="a5afd-103">ER Create a format configuration (November 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a5afd-104">En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede crear una configuración de formato para realizar informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="a5afd-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="a5afd-105">Esta configuración del formato definirá el formato de los documentos electrónicos que se usan para procesar pagos.</span><span class="sxs-lookup"><span data-stu-id="a5afd-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="a5afd-106">En este ejemplo, creará una configuración del formato para la empresa de demostración, Litware, Inc. Para completar estos pasos, debe completar primero los pasos del procedimiento "Asignación de modelos a orígenes de datos seleccionados".</span><span class="sxs-lookup"><span data-stu-id="a5afd-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the “Map model to selected datasources” procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="a5afd-107">Creación de una configuración de formato nueva</span><span class="sxs-lookup"><span data-stu-id="a5afd-107">Create a new format configuration</span></span>
1. <span data-ttu-id="a5afd-108">Vaya a **Administración de la organización > Espacios de trabajo > Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-108">Go to **Organization administration > Workspaces > Electronic reporting**.</span></span>
2. <span data-ttu-id="a5afd-109">Haga clic en **Configuraciones de informes**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-109">Click **Reporting configurations**.</span></span>
3. <span data-ttu-id="a5afd-110">En el árbol, seleccione **Pagos (modelo simplificado)**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-110">In the tree, select **Payments (simplified model)**.</span></span>
4. <span data-ttu-id="a5afd-111">Haga clic en **Crear configuración** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="a5afd-111">Click **Create configuration** to open the drop dialog.</span></span>
 > [!NOTE]
 > <span data-ttu-id="a5afd-112">Si no ve **Crear configuración**, deberá habilitar el modo de diseño en la página **Parámetros de informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-112">If you don't see **Create configuration**, you must enable design mode on the **Electronic reporting parameters** page.</span></span> 
5. <span data-ttu-id="a5afd-113">En el campo **Nuevo**, especifique **Formato basado en modelo de datos PaymentModel**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-113">In the **New** field, enter **Format based on data model PaymentModel**.</span></span>
6. <span data-ttu-id="a5afd-114">En el campo **Nombre**, escriba **BACS (ficticio Reino Unido)**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-114">In the **Name** field, type **BACS (UK fictitious)**.</span></span>
7. <span data-ttu-id="a5afd-115">En el campo **Descripción**, escriba **Formato de pago de proveedor BACS (ficticio Reino Unido)**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-115">In the **Description** field, type **BACS vendor payment format (UK fictitious)**.</span></span>
    * <span data-ttu-id="a5afd-116">El proveedor de configuraciones activo se especifica automáticamente aquí.</span><span class="sxs-lookup"><span data-stu-id="a5afd-116">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="a5afd-117">Este proveedor podrá mantener esta configuración.</span><span class="sxs-lookup"><span data-stu-id="a5afd-117">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="a5afd-118">Otros proveedores podrán usar esta configuración, pero no podrán mantenerla.</span><span class="sxs-lookup"><span data-stu-id="a5afd-118">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="a5afd-119">Se puede definir un formato concreto de documento electrónico.</span><span class="sxs-lookup"><span data-stu-id="a5afd-119">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="a5afd-120">Deje este campo en blanco si desea seleccionar un formato en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a5afd-120">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="a5afd-121">En el campo **definición del modelo de Datos**, introduzca o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a5afd-121">In the **Data model definition** field, enter or select a value.</span></span>
9. <span data-ttu-id="a5afd-122">Haga clic en **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-122">Click **Create configuration**.</span></span> <span data-ttu-id="a5afd-123">Se ha creado una nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="a5afd-123">A new configuration has been created.</span></span> <span data-ttu-id="a5afd-124">La versión de borrador se puede usar para almacenar el formato de diseño para gestionar documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="a5afd-124">The draft version can be used to store the design format for managing electronic documents.</span></span>  
 > [!NOTE]
 > <span data-ttu-id="a5afd-125">Si no ve **Crear configuración**, deberá habilitar el modo de diseño en la página **Parámetros de informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-125">If you don't see **Create configuration**, you must enable design mode on the **Electronic reporting parameters** page.</span></span>


## <a name="design-the-format-of-an-electronic-document"></a><span data-ttu-id="a5afd-126">Diseño del formato de un documento electrónico</span><span class="sxs-lookup"><span data-stu-id="a5afd-126">Design the format of an electronic document</span></span>
1. <span data-ttu-id="a5afd-127">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-127">Click **Designer**.</span></span>
2. <span data-ttu-id="a5afd-128">Haga clic en **Agregar raíz** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="a5afd-128">Click **Add root** to open the drop dialog.</span></span>
3. <span data-ttu-id="a5afd-129">En el árbol, seleccione **Común\Archivo**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-129">In the tree, select **Common\File**.</span></span>
4. <span data-ttu-id="a5afd-130">En el campo **Nombre**, escriba **Xml**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-130">In the **Name** field, type **Xml**.</span></span>
5. <span data-ttu-id="a5afd-131">En el campo **Codificación**, escriba **UTF-8**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-131">In the **Encoding** field, type **UTF-8**.</span></span>
6. <span data-ttu-id="a5afd-132">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-132">Click **OK**.</span></span>
7. <span data-ttu-id="a5afd-133">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-133">Click **Add**.</span></span>
8. <span data-ttu-id="a5afd-134">En el árbol, seleccione **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-134">In the tree, select **XML\Element**.</span></span>
9. <span data-ttu-id="a5afd-135">En el campo **Nombre**, escriba **Mensaje**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-135">In the **Name** field, type **Message**.</span></span>
10. <span data-ttu-id="a5afd-136">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-136">Click **OK**.</span></span>
11. <span data-ttu-id="a5afd-137">En el árbol, seleccione **'Xml\Mensaje**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-137">In the tree, select **Xml\Message**.</span></span>
12. <span data-ttu-id="a5afd-138">Haga clic en **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-138">Click **Add Element**.</span></span>
13. <span data-ttu-id="a5afd-139">En el campo **Nombre**, escriba **ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-139">In the **Name** field, type **ProcessingDate**.</span></span>
14. <span data-ttu-id="a5afd-140">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-140">Click **OK**.</span></span>
15. <span data-ttu-id="a5afd-141">Haga clic en **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-141">Click **Add Element**.</span></span>
16. <span data-ttu-id="a5afd-142">En el campo Nombre, escriba **MessageId**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-142">In the Name field, type **MessageId**.</span></span>
17. <span data-ttu-id="a5afd-143">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-143">Click **OK**.</span></span>
18. <span data-ttu-id="a5afd-144">Haga clic en **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-144">Click **Add Element**.</span></span>
19. <span data-ttu-id="a5afd-145">En el campo **Nombre**, escriba **Pagos**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-145">In the **Name** field, type **Payments**.</span></span>
20. <span data-ttu-id="a5afd-146">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-146">Click **OK**.</span></span>
21. <span data-ttu-id="a5afd-147">En el árbol, seleccione **Xml\Mensaje\Pagos**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-147">In the tree, select **Xml\Message\Payments**.</span></span>
22. <span data-ttu-id="a5afd-148">Haga clic en **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-148">Click **Add Element**.</span></span>
23. <span data-ttu-id="a5afd-149">En el campo **Nombre**, escriba **Artículo**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-149">In the **Name** field, type **Item**.</span></span>
24. <span data-ttu-id="a5afd-150">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-150">Click **OK**.</span></span>
25. <span data-ttu-id="a5afd-151">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-151">In the tree, select **Xml\Message\Payments\Item**.</span></span>
26. <span data-ttu-id="a5afd-152">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-152">Click **Add**.</span></span>
27. <span data-ttu-id="a5afd-153">En el árbol, seleccione **XML\Atributo**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-153">In the tree, select **XML\Attribute**.</span></span>
28. <span data-ttu-id="a5afd-154">En el campo Nombre, escriba **Id**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-154">In the Name field, type **Id**.</span></span>
29. <span data-ttu-id="a5afd-155">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-155">Click **OK**.</span></span>
30. <span data-ttu-id="a5afd-156">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-156">Click **Add**.</span></span>
31. <span data-ttu-id="a5afd-157">En el árbol, seleccione **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-157">In the tree, select **XML\Element**.</span></span>
32. <span data-ttu-id="a5afd-158">En el campo Nombre, escriba **Proveedor**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-158">In the Name field, type **Vendor**.</span></span>
33. <span data-ttu-id="a5afd-159">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-159">Click **OK**.</span></span>
34. <span data-ttu-id="a5afd-160">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\Proveedor**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-160">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
35. <span data-ttu-id="a5afd-161">Haga clic en **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-161">Click **Add Element**.</span></span>
36. <span data-ttu-id="a5afd-162">En el campo Nombre, escriba **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-162">In the Name field, type **Name**.</span></span>
37. <span data-ttu-id="a5afd-163">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-163">Click **OK**.</span></span>
38. <span data-ttu-id="a5afd-164">Haga clic en **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-164">Click **Add Element**.</span></span>
39. <span data-ttu-id="a5afd-165">En el campo **Nombre**, escriba **Banco**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-165">In the **Name** field, type **Bank**.</span></span>
40. <span data-ttu-id="a5afd-166">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-166">Click **OK**.</span></span>
41. <span data-ttu-id="a5afd-167">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\Proveedor\Banco**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-167">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank**.</span></span>
42. <span data-ttu-id="a5afd-168">Haga clic en **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-168">Click **Add Element**.</span></span>
43. <span data-ttu-id="a5afd-169">En el campo **Nombre**, especifique **RoutingNumber**</span><span class="sxs-lookup"><span data-stu-id="a5afd-169">In the **Name** field, type **RoutingNumber**.</span></span>
44. <span data-ttu-id="a5afd-170">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-170">Click **OK**.</span></span>
45. <span data-ttu-id="a5afd-171">Haga clic en **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-171">Click **Add Element**.</span></span>
46. <span data-ttu-id="a5afd-172">En el campo **Nombre**, escriba **AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-172">In the **Name** field, type **AccountNumber**.</span></span>
47. <span data-ttu-id="a5afd-173">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-173">Click **OK**.</span></span>
48. <span data-ttu-id="a5afd-174">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\Proveedor**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-174">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
49. <span data-ttu-id="a5afd-175">Haga clic en **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-175">Click **Copy**.</span></span>
50. <span data-ttu-id="a5afd-176">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-176">In the tree, select **Xml\Message\Payments\Item**.</span></span>
51. <span data-ttu-id="a5afd-177">Haga clic en **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-177">Click **Paste**.</span></span>
52. <span data-ttu-id="a5afd-178">En el campo **Nombre**, escriba **Pagador**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-178">In the **Name** field, type **Payer**.</span></span>
53. <span data-ttu-id="a5afd-179">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-179">In the tree, select **Xml\Message\Payments\Item**.</span></span>
54. <span data-ttu-id="a5afd-180">Haga clic en **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-180">Click **Add Element**.</span></span>
55. <span data-ttu-id="a5afd-181">En el campo **Nombre**, escriba **Divisa**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-181">In the **Name** field, type **Currency**.</span></span>
56. <span data-ttu-id="a5afd-182">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-182">Click **OK**.</span></span>
57. <span data-ttu-id="a5afd-183">Haga clic en **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-183">Click **Add Element**.</span></span>
58. <span data-ttu-id="a5afd-184">En el campo **Nombre**, escriba **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-184">In the **Name** field, type **Description**.</span></span>
59. <span data-ttu-id="a5afd-185">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-185">Click **OK**.</span></span>
60. <span data-ttu-id="a5afd-186">Haga clic en **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-186">Click **Add Element**.</span></span>
61. <span data-ttu-id="a5afd-187">En el campo Nombre, escriba **TransDate**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-187">In the Name field, type **TransDate**.</span></span>
62. <span data-ttu-id="a5afd-188">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-188">Click **OK**.</span></span>
63. <span data-ttu-id="a5afd-189">Haga clic en **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-189">Click **Add Element**.</span></span>
64. <span data-ttu-id="a5afd-190">En el campo Nombre, escriba **Importe**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-190">In the Name field, type **Amount**.</span></span>
65. <span data-ttu-id="a5afd-191">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-191">Click **OK**.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="a5afd-192">Preparación de los componentes de formato que asignar a los elementos del modelo de datos</span><span class="sxs-lookup"><span data-stu-id="a5afd-192">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="a5afd-193">En el árbol, seleccione **Xml\Mensaje\ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-193">In the tree, select **Xml\Message\ProcessingDate**.</span></span>
2. <span data-ttu-id="a5afd-194">Haga clic en **Agregar** para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="a5afd-194">Click **Add** to open the drop dialog.</span></span>
3. <span data-ttu-id="a5afd-195">En el árbol, seleccione **Texto\DateTime**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-195">In the tree, select **Text\DateTime**.</span></span>
4. <span data-ttu-id="a5afd-196">En el campo **Formato**, escriba **aaaa-MM-dd**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-196">In the **Format** field, type **yyyy-MM-dd**.</span></span>
5. <span data-ttu-id="a5afd-197">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-197">Click **OK**.</span></span>
6. <span data-ttu-id="a5afd-198">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\TransDate**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-198">In the tree, select **Xml\Message\Payments\Item\TransDate**.</span></span>
7. <span data-ttu-id="a5afd-199">Haga clic en **Agregar DateTime**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-199">Click **Add DateTime**.</span></span>
8. <span data-ttu-id="a5afd-200">En el campo **Formato**, escriba **aaaa-MM-dd**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-200">In the **Format** field, type **yyyy-MM-dd**.</span></span>
9. <span data-ttu-id="a5afd-201">En el campo tipo **DateTime**, seleccione **Fecha**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-201">In the **DateTime** type field, select **Date**.</span></span>
10. <span data-ttu-id="a5afd-202">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-202">Click **OK**.</span></span>
11. <span data-ttu-id="a5afd-203">En el árbol, seleccione **Xml\Mensaje\MessageId**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-203">In the tree, select **Xml\Message\MessageId**.</span></span>
12. <span data-ttu-id="a5afd-204">Haga clic en **Agregar** para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="a5afd-204">Click **Add** to open the drop dialog.</span></span>
13. <span data-ttu-id="a5afd-205">En el árbol, seleccione **Texto\Cadena**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-205">In the tree, select **Text\String**.</span></span>
14. <span data-ttu-id="a5afd-206">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-206">Click **OK**.</span></span>
15. <span data-ttu-id="a5afd-207">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\Proveedor\Nombre**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-207">In the tree, select **Xml\Message\Payments\Item\Vendor\Name**.</span></span>
16. <span data-ttu-id="a5afd-208">Haga clic en **Agregar cadena**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-208">Click **Add String**.</span></span>
17. <span data-ttu-id="a5afd-209">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-209">Click **OK**.</span></span>
18. <span data-ttu-id="a5afd-210">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\Proveedor\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-210">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.</span></span>
19. <span data-ttu-id="a5afd-211">Haga clic en **Agregar cadena**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-211">Click **Add String**.</span></span>
20. <span data-ttu-id="a5afd-212">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-212">Click **OK**.</span></span>
21. <span data-ttu-id="a5afd-213">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\Proveedor\Banco\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-213">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.</span></span>
22. <span data-ttu-id="a5afd-214">Haga clic en **Agregar cadena**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-214">Click **Add String**.</span></span>
23. <span data-ttu-id="a5afd-215">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-215">Click **OK**.</span></span>
24. <span data-ttu-id="a5afd-216">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\Pagador\Nombre**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-216">In the tree, select **Xml\Message\Payments\Item\Payer\Name**.</span></span>
25. <span data-ttu-id="a5afd-217">Haga clic en **Agregar cadena**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-217">Click **Add String**.</span></span>
26. <span data-ttu-id="a5afd-218">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-218">Click **OK**.</span></span>
27. <span data-ttu-id="a5afd-219">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\Pagador\RoutingNumber**-</span><span class="sxs-lookup"><span data-stu-id="a5afd-219">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.</span></span>
28. <span data-ttu-id="a5afd-220">Haga clic en **Agregar cadena**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-220">Click **Add String**.</span></span>
29. <span data-ttu-id="a5afd-221">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-221">Click **OK**.</span></span>
30. <span data-ttu-id="a5afd-222">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\Pagador\Banco\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-222">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.</span></span>
31. <span data-ttu-id="a5afd-223">Haga clic en **Agregar cadena**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-223">Click **Add String**.</span></span>
32. <span data-ttu-id="a5afd-224">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-224">Click **OK**.</span></span>
33. <span data-ttu-id="a5afd-225">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\Moneda**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-225">In the tree, select **Xml\Message\Payments\Item\Currency**.</span></span>
34. <span data-ttu-id="a5afd-226">Haga clic en **Agregar cadena**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-226">Click **Add String**.</span></span>
35. <span data-ttu-id="a5afd-227">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-227">Click **OK**.</span></span>
36. <span data-ttu-id="a5afd-228">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\Descripción**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-228">In the tree, select **Xml\Message\Payments\Item\Description**.</span></span>
37. <span data-ttu-id="a5afd-229">Haga clic en **Agregar cadena**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-229">Click **Add String**.</span></span>
38. <span data-ttu-id="a5afd-230">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-230">Click **OK**.</span></span>
39. <span data-ttu-id="a5afd-231">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\Importe**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-231">In the tree, select **Xml\Message\Payments\Item\Amount**.</span></span>
40. <span data-ttu-id="a5afd-232">Haga clic en **Agregar cadena**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-232">Click **Add String**.</span></span>
41. <span data-ttu-id="a5afd-233">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-233">Click **OK**.</span></span>
42. <span data-ttu-id="a5afd-234">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a5afd-234">Click **Save**.</span></span>
43. <span data-ttu-id="a5afd-235">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a5afd-235">Close the page.</span></span>


