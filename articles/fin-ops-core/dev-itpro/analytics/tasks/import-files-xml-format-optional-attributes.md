---
title: (RCS) Importar archivos en formato XML con atributos opcionales
description: En este tema se proporciona información acerca de cómo un usuario puede diseñar la configuración del formato de ER para importar archivos en formato XML que contenga atributos opcionales.
author: NickSelin
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fc28e9a2170929c6cd8daafd7eae54713cec36ff
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143209"
---
# <a name="rcs-import-files-in-xml-format-with-optional-attributes"></a><span data-ttu-id="86709-103">(RCS) Importar archivos en formato XML con atributos opcionales</span><span class="sxs-lookup"><span data-stu-id="86709-103">(RCS) Import files in XML format with optional attributes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="86709-104">En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede diseñar una configuración de formato de ER para importar archivos en formato XML que contengan atributos opcionales.</span><span class="sxs-lookup"><span data-stu-id="86709-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can design ER format configuration to import files in XML format containing optional attributes.</span></span> <span data-ttu-id="86709-105">Para completar estos pasos, primero debe completar los pasos del procedimiento "Creación y activación de un proveedor de configuraciones".</span><span class="sxs-lookup"><span data-stu-id="86709-105">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span> <span data-ttu-id="86709-106">Antes de empezar, descargue y guarde localmente el archivo IncomingDocumentToLearnHowToHandleOptionalAttributes.xml del [Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="86709-106">Before you begin, download and save locally the IncomingDocumentToLearnHowToHandleOptionalAttributes.xml file from [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span>

1.    <span data-ttu-id="86709-107">Vaya a **Todos los espacios de trabajo** > **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="86709-107">Go to **All workspaces** > **Electronic reporting**.</span></span>
2.    <span data-ttu-id="86709-108">Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como **Activo**.</span><span class="sxs-lookup"><span data-stu-id="86709-108">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="86709-109">Si no ve a este proveedor de configuración, complete los pasos del procedimiento [Crear proveedores de configuración y marcarlos como activos](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="86709-109">If you don't see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span>
3.    <span data-ttu-id="86709-110">Haga clic en **Configuraciones de informes**.</span><span class="sxs-lookup"><span data-stu-id="86709-110">Click **Reporting configurations**.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="86709-111">Creación de un nuevo modelo de configuración de datos</span><span class="sxs-lookup"><span data-stu-id="86709-111">Create a new data model configuration</span></span>
1.    <span data-ttu-id="86709-112">Haga clic en **Crear configuración** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="86709-112">Click **Create configuration** to open the drop dialog.</span></span>
2.    <span data-ttu-id="86709-113">En el campo **Nombre**, escriba 'Modelo para importar el archivo xml'.</span><span class="sxs-lookup"><span data-stu-id="86709-113">In the **Name** field, type 'Model to import xml file'.</span></span>
3.    <span data-ttu-id="86709-114">Haga clic en **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="86709-114">Click **Create configuration**.</span></span>
4.    <span data-ttu-id="86709-115">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="86709-115">Click **Designer**.</span></span>
5.    <span data-ttu-id="86709-116">Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="86709-116">Click **New** to open the drop dialog.</span></span>
6.    <span data-ttu-id="86709-117">Escriba 'Raíz' en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="86709-117">In the **Name** field, type 'Root'.</span></span>
7.    <span data-ttu-id="86709-118">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="86709-118">Click **Add**.</span></span>
8.    <span data-ttu-id="86709-119">Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="86709-119">Click **New** to open the drop dialog.</span></span>
9.    <span data-ttu-id="86709-120">Escriba 'Lista' en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="86709-120">In the **Name** field, type 'List'.</span></span>
10.    <span data-ttu-id="86709-121">En el campo **Tipo de artículo**, seleccione **Lista de registros**.</span><span class="sxs-lookup"><span data-stu-id="86709-121">In the **Item type** field, select **Record list**.</span></span>
11.    <span data-ttu-id="86709-122">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="86709-122">Click **Add**.</span></span>
12.    <span data-ttu-id="86709-123">Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="86709-123">Click **New** to open the drop dialog.</span></span>
13.    <span data-ttu-id="86709-124">En el campo **Nombre**, escriba 'Código'.</span><span class="sxs-lookup"><span data-stu-id="86709-124">In the **Name** field, type 'Code'.</span></span>
14.    <span data-ttu-id="86709-125">En el campo **Tipo de artículo**, seleccione **Cadena**.</span><span class="sxs-lookup"><span data-stu-id="86709-125">In the **Item type** field, select **String**.</span></span>
15.    <span data-ttu-id="86709-126">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="86709-126">Click **Add**.</span></span>
16.    <span data-ttu-id="86709-127">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="86709-127">Click **Save**.</span></span>
17.    <span data-ttu-id="86709-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="86709-128">Close the page.</span></span>
18.    <span data-ttu-id="86709-129">Haga clic en **Cambiar estado**.</span><span class="sxs-lookup"><span data-stu-id="86709-129">Click **Change status**.</span></span>
19.    <span data-ttu-id="86709-130">Haga clic en **Completar**.</span><span class="sxs-lookup"><span data-stu-id="86709-130">Click **Complete**.</span></span>
20.    <span data-ttu-id="86709-131">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="86709-131">Click **OK**.</span></span>

## <a name="create-a-format-for-data-import"></a><span data-ttu-id="86709-132">Crear un formato para la importación de datos</span><span class="sxs-lookup"><span data-stu-id="86709-132">Create a format for data import</span></span>
1.    <span data-ttu-id="86709-133">Haga clic en **Crear configuración** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="86709-133">Click **Create configuration** to open the drop dialog.</span></span>
2.    <span data-ttu-id="86709-134">En el campo **Nuevo**, introduzca 'Formato basado en el modelo de datos del archivo Modelo para importar.xml'.</span><span class="sxs-lookup"><span data-stu-id="86709-134">In the **New** field, enter 'Format based on data model Model to import xml file'.</span></span>
3.    <span data-ttu-id="86709-135">En el campo **Nombre**, escriba 'Formato para importar el archivo xml'.</span><span class="sxs-lookup"><span data-stu-id="86709-135">In the **Name** field, type 'Format to import xml file'.</span></span>
4.    <span data-ttu-id="86709-136">Seleccione **Sí** en el campo **Admite la importación de datos**.</span><span class="sxs-lookup"><span data-stu-id="86709-136">Select **Yes** in the **Supports data import** field.</span></span>
5.    <span data-ttu-id="86709-137">Haga clic en **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="86709-137">Click **Create configuration**.</span></span>

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a><span data-ttu-id="86709-138">Diseñar un formato para analizar el archivo de entrada en formato xml</span><span class="sxs-lookup"><span data-stu-id="86709-138">Design a format to parse incoming file in xml format</span></span>
1.    <span data-ttu-id="86709-139">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="86709-139">Click **Designer**.</span></span>
2.    <span data-ttu-id="86709-140">Haga clic en **Agregar raíz** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="86709-140">Click **Add root** to open the drop dialog.</span></span>
3.    <span data-ttu-id="86709-141">En el árbol, seleccione **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="86709-141">In the tree, select **XML\Element**.</span></span>
4.    <span data-ttu-id="86709-142">Escriba 'raíz' en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="86709-142">In the **Name** field, type 'root'.</span></span>
5.    <span data-ttu-id="86709-143">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="86709-143">Click **OK**.</span></span>
6.    <span data-ttu-id="86709-144">Haga clic en **Agregar** para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="86709-144">Click **Add** to open the drop dialog.</span></span>
7.    <span data-ttu-id="86709-145">En el árbol, seleccione **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="86709-145">In the tree, select **XML\Element**.</span></span>
8.    <span data-ttu-id="86709-146">En el campo **Nombre**, introduzca 'documento'.</span><span class="sxs-lookup"><span data-stu-id="86709-146">In the **Name** field, type 'document'.</span></span>
9.    <span data-ttu-id="86709-147">En el campo de **Multiplicidad**, seleccione **Uno o varios**.</span><span class="sxs-lookup"><span data-stu-id="86709-147">In the **Multiplicity** field, select **One many**.</span></span>
10.    <span data-ttu-id="86709-148">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="86709-148">Click **OK**.</span></span>
11.    <span data-ttu-id="86709-149">En el árbol, seleccione **root\document**.</span><span class="sxs-lookup"><span data-stu-id="86709-149">In the tree, select **root\document**.</span></span>
12.    <span data-ttu-id="86709-150">Haga clic en **Agregar** para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="86709-150">Click **Add** to open the drop dialog.</span></span>
13.    <span data-ttu-id="86709-151">En el árbol, seleccione **XML\Atributo**.</span><span class="sxs-lookup"><span data-stu-id="86709-151">In the tree, select **XML\Attribute**.</span></span>
14.    <span data-ttu-id="86709-152">En el campo **Nombre**, escriba 'ID'.</span><span class="sxs-lookup"><span data-stu-id="86709-152">In the **Name** field, type 'ID'.</span></span>
15.    <span data-ttu-id="86709-153">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="86709-153">Click **OK**.</span></span>
16.    <span data-ttu-id="86709-154">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="86709-154">Click **Save**.</span></span>

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a><span data-ttu-id="86709-155">Diseñar una asignación de formato para guardar la información analizada al modelo de datos</span><span class="sxs-lookup"><span data-stu-id="86709-155">Design a format mapping to save parsed information to data model</span></span>
1. <span data-ttu-id="86709-156">Haga clic en **Asignar formato a modelo**.</span><span class="sxs-lookup"><span data-stu-id="86709-156">Click **Map format to model**.</span></span>
2. <span data-ttu-id="86709-157">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="86709-157">Click **New**.</span></span>
3. <span data-ttu-id="86709-158">En el campo **Definición**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="86709-158">In the **Definition** field, enter or select a value.</span></span>
4. <span data-ttu-id="86709-159">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="86709-159">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="86709-160">En el campo **Nombre**, introduzca 'Asignación'.</span><span class="sxs-lookup"><span data-stu-id="86709-160">In the **Name** field, type 'Mapping'.</span></span>
6. <span data-ttu-id="86709-161">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="86709-161">Click **Save**.</span></span>
7. <span data-ttu-id="86709-162">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="86709-162">Click **Designer**.</span></span>
8. <span data-ttu-id="86709-163">En el árbol, expanda **format**.</span><span class="sxs-lookup"><span data-stu-id="86709-163">In the tree, expand **format**.</span></span>
9. <span data-ttu-id="86709-164">En el árbol, expanda **format\root: XML Element(root)**.</span><span class="sxs-lookup"><span data-stu-id="86709-164">In the tree, expand **format\root: XML Element(root)**.</span></span>
10.    <span data-ttu-id="86709-165">En el árbol, seleccione \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="86709-165">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="86709-166">(documento)\*\*.</span><span class="sxs-lookup"><span data-stu-id="86709-166">(document)\*\*.</span></span>
11.    <span data-ttu-id="86709-167">Haga clic en **Enlazar**.</span><span class="sxs-lookup"><span data-stu-id="86709-167">Click **Bind**.</span></span>
12.    <span data-ttu-id="86709-168">En el árbol, expanda \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="86709-168">In the tree, expand \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="86709-169">(documento)\*\*.</span><span class="sxs-lookup"><span data-stu-id="86709-169">(document)\*\*.</span></span>
13.    <span data-ttu-id="86709-170">En el árbol, seleccione \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="86709-170">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="86709-171">(documento)\id\*\*.</span><span class="sxs-lookup"><span data-stu-id="86709-171">(document)\id\*\*.</span></span>
14.    <span data-ttu-id="86709-172">En el árbol, expanda **List = format.root.document**.</span><span class="sxs-lookup"><span data-stu-id="86709-172">In the tree, expand **List = format.root.document**.</span></span>
15.    <span data-ttu-id="86709-173">En el árbol, seleccione **List = format.root.document\Code**.</span><span class="sxs-lookup"><span data-stu-id="86709-173">In the tree, select **List = format.root.document\Code**.</span></span>
16.    <span data-ttu-id="86709-174">Haga clic en **Enlazar**.</span><span class="sxs-lookup"><span data-stu-id="86709-174">Click **Bind**.</span></span>
17.    <span data-ttu-id="86709-175">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="86709-175">Click **Save**.</span></span>
18.    <span data-ttu-id="86709-176">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="86709-176">Close the page.</span></span>
 
## <a name="run-format-mapping"></a><span data-ttu-id="86709-177">Ejecutar asignación de formato</span><span class="sxs-lookup"><span data-stu-id="86709-177">Run format mapping</span></span>
1. <span data-ttu-id="86709-178">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="86709-178">Click **Run**.</span></span>
2. <span data-ttu-id="86709-179">Haga clic en **Examinar** y seleccione **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="86709-179">Click **Browse** and select **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span></span>
3. <span data-ttu-id="86709-180">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="86709-180">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="86709-181">El archivo seleccionado no se ha importado ya que el diseño de formato asume la existencia de atributo ‘id’ para el elemento ‘document’, pero el archivo importado no contiene tal atributo.</span><span class="sxs-lookup"><span data-stu-id="86709-181">The selected file has not been imported as the format design assumes the existence of 'id' attribute for the 'document' element, but the imported file contains no such attribute.</span></span>

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a><span data-ttu-id="86709-182">Modificar la estructura del formato para gestionar el atributo xml como opcional</span><span class="sxs-lookup"><span data-stu-id="86709-182">Modify format structure to handle xml attribute as optional</span></span>
1. <span data-ttu-id="86709-183">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="86709-183">Close the page.</span></span>
2. <span data-ttu-id="86709-184">En el árbol, expanda **root\document**.</span><span class="sxs-lookup"><span data-stu-id="86709-184">In the tree, expand **root\document**.</span></span>
3. <span data-ttu-id="86709-185">En el árbol, seleccione **root\document\id**.</span><span class="sxs-lookup"><span data-stu-id="86709-185">In the tree, select **root\document\id**.</span></span>
4. <span data-ttu-id="86709-186">Seleccione **Sí** en el campo **Cadena vacía para el atributo que falta** .</span><span class="sxs-lookup"><span data-stu-id="86709-186">Select **Yes** in the **Empty string for missing attribute** field.</span></span>
5. <span data-ttu-id="86709-187">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="86709-187">Click **Save**.</span></span>
 
## <a name="run-format-mapping-to-test-changes"></a><span data-ttu-id="86709-188">Ejecutar asignación de formato para cambios de prueba</span><span class="sxs-lookup"><span data-stu-id="86709-188">Run format mapping to test changes</span></span>
1. <span data-ttu-id="86709-189">Haga clic en **Asignar formato a modelo**.</span><span class="sxs-lookup"><span data-stu-id="86709-189">Click **Map format to model**.</span></span>
2. <span data-ttu-id="86709-190">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="86709-190">Click **Run**.</span></span>
3. <span data-ttu-id="86709-191">Haga clic en **Examinar** y seleccione el archivo **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="86709-191">Click **Browse** and select the **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml** file.</span></span>
4. <span data-ttu-id="86709-192">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="86709-192">Click **OK**.</span></span>
5. <span data-ttu-id="86709-193">Revise el archivo generado.</span><span class="sxs-lookup"><span data-stu-id="86709-193">Review the generated file.</span></span> 

> [!NOTE]
> <span data-ttu-id="86709-194">Se ha importado el mismo archivo ya que el diseño de formato ahora considera el atributo "id" para el elemento "documento" como opcional.</span><span class="sxs-lookup"><span data-stu-id="86709-194">The same file has been imported as the format design now consider the 'id' attribute for the 'document' element as optional.</span></span>
