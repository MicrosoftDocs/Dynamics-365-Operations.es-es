---
title: ER Crear una configuración de formato (noviembre de 2016)
description: Este tema explica cómo crear una configuración de formato para informes electrónicos (ER).
author: NickSelin
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9404d1e242c83d2103d1f24c42589c33b9f57f02
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092259"
---
# <a name="er-create-a-format-configuration-november-2016"></a><span data-ttu-id="1110c-103">ER Crear una configuración de formato (noviembre de 2016)</span><span class="sxs-lookup"><span data-stu-id="1110c-103">ER Create a format configuration (November 2016)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1110c-104">En este tema se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede crear una configuración de formato para realizar informes electrónicos (ER).</span><span class="sxs-lookup"><span data-stu-id="1110c-104">This topic explains how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="1110c-105">Esta configuración del formato definirá el formato de los documentos electrónicos que se usan para procesar pagos.</span><span class="sxs-lookup"><span data-stu-id="1110c-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="1110c-106">En este ejemplo, creará una configuración del formato para la empresa de demostración, Litware, Inc. Para completar estos pasos, debe completar primero los pasos del procedimiento "Asignación de modelos a orígenes de datos seleccionados".</span><span class="sxs-lookup"><span data-stu-id="1110c-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the "Map model to selected datasources" procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="1110c-107">Creación de una configuración de formato nueva</span><span class="sxs-lookup"><span data-stu-id="1110c-107">Create a new format configuration</span></span>
1. <span data-ttu-id="1110c-108">Vaya a **Administración de la organización > Espacios de trabajo > Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="1110c-108">Go to **Organization administration > Workspaces > Electronic reporting**.</span></span>
2. <span data-ttu-id="1110c-109">Haga clic en **Configuraciones de informes**.</span><span class="sxs-lookup"><span data-stu-id="1110c-109">Click **Reporting configurations**.</span></span>
3. <span data-ttu-id="1110c-110">En el árbol, seleccione **Pagos (modelo simplificado)**.</span><span class="sxs-lookup"><span data-stu-id="1110c-110">In the tree, select **Payments (simplified model)**.</span></span>
4. <span data-ttu-id="1110c-111">Haga clic en **Crear configuración** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="1110c-111">Click **Create configuration** to open the drop dialog.</span></span>

 > [!NOTE]
 > <span data-ttu-id="1110c-112">Si no ve **Crear configuración**, deberá habilitar el modo de diseño en la página **Parámetros de informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="1110c-112">If you don't see **Create configuration**, you must enable design mode on the **Electronic reporting parameters** page.</span></span> 
 
5. <span data-ttu-id="1110c-113">En el campo **Nuevo**, especifique **Formato basado en modelo de datos PaymentModel**.</span><span class="sxs-lookup"><span data-stu-id="1110c-113">In the **New** field, enter **Format based on data model PaymentModel**.</span></span>
6. <span data-ttu-id="1110c-114">En el campo **Nombre**, escriba **BACS (ficticio Reino Unido)**.</span><span class="sxs-lookup"><span data-stu-id="1110c-114">In the **Name** field, type **BACS (UK fictitious)**.</span></span>
7. <span data-ttu-id="1110c-115">En el campo **Descripción**, escriba **Formato de pago de proveedor BACS (ficticio Reino Unido)**.</span><span class="sxs-lookup"><span data-stu-id="1110c-115">In the **Description** field, type **BACS vendor payment format (UK fictitious)**.</span></span>
    * <span data-ttu-id="1110c-116">El proveedor de configuraciones activo se especifica automáticamente aquí.</span><span class="sxs-lookup"><span data-stu-id="1110c-116">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="1110c-117">Este proveedor podrá mantener esta configuración.</span><span class="sxs-lookup"><span data-stu-id="1110c-117">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="1110c-118">Otros proveedores podrán usar esta configuración, pero no podrán mantenerla.</span><span class="sxs-lookup"><span data-stu-id="1110c-118">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="1110c-119">Se puede definir un formato concreto de documento electrónico.</span><span class="sxs-lookup"><span data-stu-id="1110c-119">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="1110c-120">Deje este campo en blanco si desea seleccionar un formato en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1110c-120">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="1110c-121">En el campo **definición del modelo de Datos**, introduzca o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="1110c-121">In the **Data model definition** field, enter or select a value.</span></span>
9. <span data-ttu-id="1110c-122">Haga clic en **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="1110c-122">Click **Create configuration**.</span></span> <span data-ttu-id="1110c-123">Se ha creado una nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="1110c-123">A new configuration has been created.</span></span> <span data-ttu-id="1110c-124">La versión de borrador se puede usar para almacenar el formato de diseño para gestionar documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="1110c-124">The draft version can be used to store the design format for managing electronic documents.</span></span>  

## <a name="design-the-format-of-an-electronic-document"></a><span data-ttu-id="1110c-125">Diseño del formato de un documento electrónico</span><span class="sxs-lookup"><span data-stu-id="1110c-125">Design the format of an electronic document</span></span>
1. <span data-ttu-id="1110c-126">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="1110c-126">Click **Designer**.</span></span>
2. <span data-ttu-id="1110c-127">Haga clic en **Agregar raíz** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="1110c-127">Click **Add root** to open the drop dialog.</span></span>
3. <span data-ttu-id="1110c-128">En el árbol, seleccione **Común\Archivo**.</span><span class="sxs-lookup"><span data-stu-id="1110c-128">In the tree, select **Common\File**.</span></span>
4. <span data-ttu-id="1110c-129">En el campo **Nombre**, escriba **Xml**.</span><span class="sxs-lookup"><span data-stu-id="1110c-129">In the **Name** field, type **Xml**.</span></span>
5. <span data-ttu-id="1110c-130">En el campo **Codificación**, escriba **UTF-8**.</span><span class="sxs-lookup"><span data-stu-id="1110c-130">In the **Encoding** field, type **UTF-8**.</span></span>
6. <span data-ttu-id="1110c-131">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-131">Click **OK**.</span></span>
7. <span data-ttu-id="1110c-132">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-132">Click **Add**.</span></span>
8. <span data-ttu-id="1110c-133">En el árbol, seleccione **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="1110c-133">In the tree, select **XML\Element**.</span></span>
9. <span data-ttu-id="1110c-134">En el campo **Nombre**, escriba **Mensaje**.</span><span class="sxs-lookup"><span data-stu-id="1110c-134">In the **Name** field, type **Message**.</span></span>
10. <span data-ttu-id="1110c-135">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-135">Click **OK**.</span></span>
11. <span data-ttu-id="1110c-136">En el árbol, seleccione **'Xml\Mensaje**.</span><span class="sxs-lookup"><span data-stu-id="1110c-136">In the tree, select **Xml\Message**.</span></span>
12. <span data-ttu-id="1110c-137">Haga clic en **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="1110c-137">Click **Add Element**.</span></span>
13. <span data-ttu-id="1110c-138">En el campo **Nombre**, escriba **ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="1110c-138">In the **Name** field, type **ProcessingDate**.</span></span>
14. <span data-ttu-id="1110c-139">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-139">Click **OK**.</span></span>
15. <span data-ttu-id="1110c-140">Haga clic en **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="1110c-140">Click **Add Element**.</span></span>
16. <span data-ttu-id="1110c-141">En el campo Nombre, escriba **MessageId**.</span><span class="sxs-lookup"><span data-stu-id="1110c-141">In the Name field, type **MessageId**.</span></span>
17. <span data-ttu-id="1110c-142">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-142">Click **OK**.</span></span>
18. <span data-ttu-id="1110c-143">Haga clic en **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="1110c-143">Click **Add Element**.</span></span>
19. <span data-ttu-id="1110c-144">En el campo **Nombre**, escriba **Pagos**.</span><span class="sxs-lookup"><span data-stu-id="1110c-144">In the **Name** field, type **Payments**.</span></span>
20. <span data-ttu-id="1110c-145">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-145">Click **OK**.</span></span>
21. <span data-ttu-id="1110c-146">En el árbol, seleccione **Xml\Mensaje\Pagos**.</span><span class="sxs-lookup"><span data-stu-id="1110c-146">In the tree, select **Xml\Message\Payments**.</span></span>
22. <span data-ttu-id="1110c-147">Haga clic en **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="1110c-147">Click **Add Element**.</span></span>
23. <span data-ttu-id="1110c-148">En el campo **Nombre**, escriba **Artículo**.</span><span class="sxs-lookup"><span data-stu-id="1110c-148">In the **Name** field, type **Item**.</span></span>
24. <span data-ttu-id="1110c-149">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-149">Click **OK**.</span></span>
25. <span data-ttu-id="1110c-150">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo**.</span><span class="sxs-lookup"><span data-stu-id="1110c-150">In the tree, select **Xml\Message\Payments\Item**.</span></span>
26. <span data-ttu-id="1110c-151">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-151">Click **Add**.</span></span>
27. <span data-ttu-id="1110c-152">En el árbol, seleccione **XML\Atributo**.</span><span class="sxs-lookup"><span data-stu-id="1110c-152">In the tree, select **XML\Attribute**.</span></span>
28. <span data-ttu-id="1110c-153">En el campo Nombre, escriba **Id**.</span><span class="sxs-lookup"><span data-stu-id="1110c-153">In the Name field, type **Id**.</span></span>
29. <span data-ttu-id="1110c-154">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-154">Click **OK**.</span></span>
30. <span data-ttu-id="1110c-155">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-155">Click **Add**.</span></span>
31. <span data-ttu-id="1110c-156">En el árbol, seleccione **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="1110c-156">In the tree, select **XML\Element**.</span></span>
32. <span data-ttu-id="1110c-157">En el campo Nombre, escriba **Proveedor**.</span><span class="sxs-lookup"><span data-stu-id="1110c-157">In the Name field, type **Vendor**.</span></span>
33. <span data-ttu-id="1110c-158">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-158">Click **OK**.</span></span>
34. <span data-ttu-id="1110c-159">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\Proveedor**.</span><span class="sxs-lookup"><span data-stu-id="1110c-159">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
35. <span data-ttu-id="1110c-160">Haga clic en **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="1110c-160">Click **Add Element**.</span></span>
36. <span data-ttu-id="1110c-161">En el campo Nombre, escriba **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="1110c-161">In the Name field, type **Name**.</span></span>
37. <span data-ttu-id="1110c-162">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-162">Click **OK**.</span></span>
38. <span data-ttu-id="1110c-163">Haga clic en **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="1110c-163">Click **Add Element**.</span></span>
39. <span data-ttu-id="1110c-164">En el campo **Nombre**, escriba **Banco**.</span><span class="sxs-lookup"><span data-stu-id="1110c-164">In the **Name** field, type **Bank**.</span></span>
40. <span data-ttu-id="1110c-165">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-165">Click **OK**.</span></span>
41. <span data-ttu-id="1110c-166">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\Proveedor\Banco**.</span><span class="sxs-lookup"><span data-stu-id="1110c-166">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank**.</span></span>
42. <span data-ttu-id="1110c-167">Haga clic en **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="1110c-167">Click **Add Element**.</span></span>
43. <span data-ttu-id="1110c-168">En el campo **Nombre**, especifique **RoutingNumber**</span><span class="sxs-lookup"><span data-stu-id="1110c-168">In the **Name** field, type **RoutingNumber**.</span></span>
44. <span data-ttu-id="1110c-169">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-169">Click **OK**.</span></span>
45. <span data-ttu-id="1110c-170">Haga clic en **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="1110c-170">Click **Add Element**.</span></span>
46. <span data-ttu-id="1110c-171">En el campo **Nombre**, escriba **AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="1110c-171">In the **Name** field, type **AccountNumber**.</span></span>
47. <span data-ttu-id="1110c-172">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-172">Click **OK**.</span></span>
48. <span data-ttu-id="1110c-173">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\Proveedor**.</span><span class="sxs-lookup"><span data-stu-id="1110c-173">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
49. <span data-ttu-id="1110c-174">Haga clic en **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-174">Click **Copy**.</span></span>
50. <span data-ttu-id="1110c-175">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo**.</span><span class="sxs-lookup"><span data-stu-id="1110c-175">In the tree, select **Xml\Message\Payments\Item**.</span></span>
51. <span data-ttu-id="1110c-176">Haga clic en **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-176">Click **Paste**.</span></span>
52. <span data-ttu-id="1110c-177">En el campo **Nombre**, escriba **Pagador**.</span><span class="sxs-lookup"><span data-stu-id="1110c-177">In the **Name** field, type **Payer**.</span></span>
53. <span data-ttu-id="1110c-178">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo**.</span><span class="sxs-lookup"><span data-stu-id="1110c-178">In the tree, select **Xml\Message\Payments\Item**.</span></span>
54. <span data-ttu-id="1110c-179">Haga clic en **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="1110c-179">Click **Add Element**.</span></span>
55. <span data-ttu-id="1110c-180">En el campo **Nombre**, escriba **Divisa**.</span><span class="sxs-lookup"><span data-stu-id="1110c-180">In the **Name** field, type **Currency**.</span></span>
56. <span data-ttu-id="1110c-181">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-181">Click **OK**.</span></span>
57. <span data-ttu-id="1110c-182">Haga clic en **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="1110c-182">Click **Add Element**.</span></span>
58. <span data-ttu-id="1110c-183">En el campo **Nombre**, escriba **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="1110c-183">In the **Name** field, type **Description**.</span></span>
59. <span data-ttu-id="1110c-184">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-184">Click **OK**.</span></span>
60. <span data-ttu-id="1110c-185">Haga clic en **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="1110c-185">Click **Add Element**.</span></span>
61. <span data-ttu-id="1110c-186">En el campo Nombre, escriba **TransDate**.</span><span class="sxs-lookup"><span data-stu-id="1110c-186">In the Name field, type **TransDate**.</span></span>
62. <span data-ttu-id="1110c-187">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-187">Click **OK**.</span></span>
63. <span data-ttu-id="1110c-188">Haga clic en **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="1110c-188">Click **Add Element**.</span></span>
64. <span data-ttu-id="1110c-189">En el campo Nombre, escriba **Importe**.</span><span class="sxs-lookup"><span data-stu-id="1110c-189">In the Name field, type **Amount**.</span></span>
65. <span data-ttu-id="1110c-190">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-190">Click **OK**.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="1110c-191">Preparación de los componentes de formato que asignar a los elementos del modelo de datos</span><span class="sxs-lookup"><span data-stu-id="1110c-191">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="1110c-192">En el árbol, seleccione **Xml\Mensaje\ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="1110c-192">In the tree, select **Xml\Message\ProcessingDate**.</span></span>
2. <span data-ttu-id="1110c-193">Haga clic en **Agregar** para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="1110c-193">Click **Add** to open the drop dialog.</span></span>
3. <span data-ttu-id="1110c-194">En el árbol, seleccione **Texto\DateTime**.</span><span class="sxs-lookup"><span data-stu-id="1110c-194">In the tree, select **Text\DateTime**.</span></span>
4. <span data-ttu-id="1110c-195">En el campo **Formato**, escriba **aaaa-MM-dd**.</span><span class="sxs-lookup"><span data-stu-id="1110c-195">In the **Format** field, type **yyyy-MM-dd**.</span></span>
5. <span data-ttu-id="1110c-196">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-196">Click **OK**.</span></span>
6. <span data-ttu-id="1110c-197">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\TransDate**.</span><span class="sxs-lookup"><span data-stu-id="1110c-197">In the tree, select **Xml\Message\Payments\Item\TransDate**.</span></span>
7. <span data-ttu-id="1110c-198">Haga clic en **Agregar DateTime**.</span><span class="sxs-lookup"><span data-stu-id="1110c-198">Click **Add DateTime**.</span></span>
8. <span data-ttu-id="1110c-199">En el campo **Formato**, escriba **aaaa-MM-dd**.</span><span class="sxs-lookup"><span data-stu-id="1110c-199">In the **Format** field, type **yyyy-MM-dd**.</span></span>
9. <span data-ttu-id="1110c-200">En el campo tipo **DateTime**, seleccione **Fecha**.</span><span class="sxs-lookup"><span data-stu-id="1110c-200">In the **DateTime** type field, select **Date**.</span></span>
10. <span data-ttu-id="1110c-201">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-201">Click **OK**.</span></span>
11. <span data-ttu-id="1110c-202">En el árbol, seleccione **Xml\Mensaje\MessageId**.</span><span class="sxs-lookup"><span data-stu-id="1110c-202">In the tree, select **Xml\Message\MessageId**.</span></span>
12. <span data-ttu-id="1110c-203">Haga clic en **Agregar** para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="1110c-203">Click **Add** to open the drop dialog.</span></span>
13. <span data-ttu-id="1110c-204">En el árbol, seleccione **Texto\Cadena**.</span><span class="sxs-lookup"><span data-stu-id="1110c-204">In the tree, select **Text\String**.</span></span>
14. <span data-ttu-id="1110c-205">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-205">Click **OK**.</span></span>
15. <span data-ttu-id="1110c-206">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\Proveedor\Nombre**.</span><span class="sxs-lookup"><span data-stu-id="1110c-206">In the tree, select **Xml\Message\Payments\Item\Vendor\Name**.</span></span>
16. <span data-ttu-id="1110c-207">Haga clic en **Agregar cadena**.</span><span class="sxs-lookup"><span data-stu-id="1110c-207">Click **Add String**.</span></span>
17. <span data-ttu-id="1110c-208">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-208">Click **OK**.</span></span>
18. <span data-ttu-id="1110c-209">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\Proveedor\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="1110c-209">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.</span></span>
19. <span data-ttu-id="1110c-210">Haga clic en **Agregar cadena**.</span><span class="sxs-lookup"><span data-stu-id="1110c-210">Click **Add String**.</span></span>
20. <span data-ttu-id="1110c-211">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-211">Click **OK**.</span></span>
21. <span data-ttu-id="1110c-212">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\Proveedor\Banco\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="1110c-212">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.</span></span>
22. <span data-ttu-id="1110c-213">Haga clic en **Agregar cadena**.</span><span class="sxs-lookup"><span data-stu-id="1110c-213">Click **Add String**.</span></span>
23. <span data-ttu-id="1110c-214">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-214">Click **OK**.</span></span>
24. <span data-ttu-id="1110c-215">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\Pagador\Nombre**.</span><span class="sxs-lookup"><span data-stu-id="1110c-215">In the tree, select **Xml\Message\Payments\Item\Payer\Name**.</span></span>
25. <span data-ttu-id="1110c-216">Haga clic en **Agregar cadena**.</span><span class="sxs-lookup"><span data-stu-id="1110c-216">Click **Add String**.</span></span>
26. <span data-ttu-id="1110c-217">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-217">Click **OK**.</span></span>
27. <span data-ttu-id="1110c-218">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\Pagador\RoutingNumber**-</span><span class="sxs-lookup"><span data-stu-id="1110c-218">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.</span></span>
28. <span data-ttu-id="1110c-219">Haga clic en **Agregar cadena**.</span><span class="sxs-lookup"><span data-stu-id="1110c-219">Click **Add String**.</span></span>
29. <span data-ttu-id="1110c-220">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-220">Click **OK**.</span></span>
30. <span data-ttu-id="1110c-221">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\Pagador\Banco\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="1110c-221">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.</span></span>
31. <span data-ttu-id="1110c-222">Haga clic en **Agregar cadena**.</span><span class="sxs-lookup"><span data-stu-id="1110c-222">Click **Add String**.</span></span>
32. <span data-ttu-id="1110c-223">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-223">Click **OK**.</span></span>
33. <span data-ttu-id="1110c-224">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\Moneda**.</span><span class="sxs-lookup"><span data-stu-id="1110c-224">In the tree, select **Xml\Message\Payments\Item\Currency**.</span></span>
34. <span data-ttu-id="1110c-225">Haga clic en **Agregar cadena**.</span><span class="sxs-lookup"><span data-stu-id="1110c-225">Click **Add String**.</span></span>
35. <span data-ttu-id="1110c-226">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-226">Click **OK**.</span></span>
36. <span data-ttu-id="1110c-227">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\Descripción**.</span><span class="sxs-lookup"><span data-stu-id="1110c-227">In the tree, select **Xml\Message\Payments\Item\Description**.</span></span>
37. <span data-ttu-id="1110c-228">Haga clic en **Agregar cadena**.</span><span class="sxs-lookup"><span data-stu-id="1110c-228">Click **Add String**.</span></span>
38. <span data-ttu-id="1110c-229">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-229">Click **OK**.</span></span>
39. <span data-ttu-id="1110c-230">En el árbol, seleccione **Xml\Mensaje\Pagos\Artículo\Importe**.</span><span class="sxs-lookup"><span data-stu-id="1110c-230">In the tree, select **Xml\Message\Payments\Item\Amount**.</span></span>
40. <span data-ttu-id="1110c-231">Haga clic en **Agregar cadena**.</span><span class="sxs-lookup"><span data-stu-id="1110c-231">Click **Add String**.</span></span>
41. <span data-ttu-id="1110c-232">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-232">Click **OK**.</span></span>
42. <span data-ttu-id="1110c-233">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1110c-233">Click **Save**.</span></span>
43. <span data-ttu-id="1110c-234">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="1110c-234">Close the page.</span></span>

