---
title: (RCS) Importar archivos en formato XML con atributos opcionales
description: En este tema se proporciona información acerca de cómo un usuario puede diseñar la configuración del formato de ER para importar archivos en formato XML que contenga atributos opcionales.
author: NickSelin
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ef090270b2e521b870697bb238b50ea92d4f6958
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565695"
---
# <a name="rcs-import-files-in-xml-format-with-optional-attributes"></a><span data-ttu-id="f797d-103">(RCS) Importar archivos en formato XML con atributos opcionales</span><span class="sxs-lookup"><span data-stu-id="f797d-103">(RCS) Import files in XML format with optional attributes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f797d-104">En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede diseñar una configuración de formato de ER para importar archivos en formato XML que contengan atributos opcionales.</span><span class="sxs-lookup"><span data-stu-id="f797d-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can design ER format configuration to import files in XML format containing optional attributes.</span></span> <span data-ttu-id="f797d-105">Para completar estos pasos, primero debe completar los pasos del procedimiento "Creación y activación de un proveedor de configuraciones".</span><span class="sxs-lookup"><span data-stu-id="f797d-105">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span> <span data-ttu-id="f797d-106">Antes de empezar, descargue y guarde localmente el archivo IncomingDocumentToLearnHowToHandleOptionalAttributes.xml del [Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="f797d-106">Before you begin, download and save locally the IncomingDocumentToLearnHowToHandleOptionalAttributes.xml file from [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span>

1.    <span data-ttu-id="f797d-107">Vaya a **Todos los espacios de trabajo** > **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="f797d-107">Go to **All workspaces** > **Electronic reporting**.</span></span>
2.    <span data-ttu-id="f797d-108">Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como **Activo**.</span><span class="sxs-lookup"><span data-stu-id="f797d-108">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="f797d-109">Si no ve a este proveedor de configuración, complete los pasos del procedimiento [Crear proveedores de configuración y marcarlos como activos](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="f797d-109">If you don't see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span>
3.    <span data-ttu-id="f797d-110">Haga clic en **Configuraciones de informes**.</span><span class="sxs-lookup"><span data-stu-id="f797d-110">Click **Reporting configurations**.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="f797d-111">Creación de un nuevo modelo de configuración de datos</span><span class="sxs-lookup"><span data-stu-id="f797d-111">Create a new data model configuration</span></span>
1.    <span data-ttu-id="f797d-112">Haga clic en **Crear configuración** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="f797d-112">Click **Create configuration** to open the drop dialog.</span></span>
2.    <span data-ttu-id="f797d-113">En el campo **Nombre**, escriba 'Modelo para importar el archivo xml'.</span><span class="sxs-lookup"><span data-stu-id="f797d-113">In the **Name** field, type 'Model to import xml file'.</span></span>
3.    <span data-ttu-id="f797d-114">Haga clic en **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="f797d-114">Click **Create configuration**.</span></span>
4.    <span data-ttu-id="f797d-115">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="f797d-115">Click **Designer**.</span></span>
5.    <span data-ttu-id="f797d-116">Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="f797d-116">Click **New** to open the drop dialog.</span></span>
6.    <span data-ttu-id="f797d-117">Escriba 'Raíz' en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="f797d-117">In the **Name** field, type 'Root'.</span></span>
7.    <span data-ttu-id="f797d-118">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f797d-118">Click **Add**.</span></span>
8.    <span data-ttu-id="f797d-119">Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="f797d-119">Click **New** to open the drop dialog.</span></span>
9.    <span data-ttu-id="f797d-120">Escriba 'Lista' en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="f797d-120">In the **Name** field, type 'List'.</span></span>
10.    <span data-ttu-id="f797d-121">En el campo **Tipo de artículo**, seleccione **Lista de registros**.</span><span class="sxs-lookup"><span data-stu-id="f797d-121">In the **Item type** field, select **Record list**.</span></span>
11.    <span data-ttu-id="f797d-122">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f797d-122">Click **Add**.</span></span>
12.    <span data-ttu-id="f797d-123">Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="f797d-123">Click **New** to open the drop dialog.</span></span>
13.    <span data-ttu-id="f797d-124">En el campo **Nombre**, escriba 'Código'.</span><span class="sxs-lookup"><span data-stu-id="f797d-124">In the **Name** field, type 'Code'.</span></span>
14.    <span data-ttu-id="f797d-125">En el campo **Tipo de artículo**, seleccione **Cadena**.</span><span class="sxs-lookup"><span data-stu-id="f797d-125">In the **Item type** field, select **String**.</span></span>
15.    <span data-ttu-id="f797d-126">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f797d-126">Click **Add**.</span></span>
16.    <span data-ttu-id="f797d-127">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f797d-127">Click **Save**.</span></span>
17.    <span data-ttu-id="f797d-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f797d-128">Close the page.</span></span>
18.    <span data-ttu-id="f797d-129">Haga clic en **Cambiar estado**.</span><span class="sxs-lookup"><span data-stu-id="f797d-129">Click **Change status**.</span></span>
19.    <span data-ttu-id="f797d-130">Haga clic en **Completar**.</span><span class="sxs-lookup"><span data-stu-id="f797d-130">Click **Complete**.</span></span>
20.    <span data-ttu-id="f797d-131">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f797d-131">Click **OK**.</span></span>

## <a name="create-a-format-for-data-import"></a><span data-ttu-id="f797d-132">Crear un formato para la importación de datos</span><span class="sxs-lookup"><span data-stu-id="f797d-132">Create a format for data import</span></span>
1.    <span data-ttu-id="f797d-133">Haga clic en **Crear configuración** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="f797d-133">Click **Create configuration** to open the drop dialog.</span></span>
2.    <span data-ttu-id="f797d-134">En el campo **Nuevo**, introduzca 'Formato basado en el modelo de datos del archivo Modelo para importar.xml'.</span><span class="sxs-lookup"><span data-stu-id="f797d-134">In the **New** field, enter 'Format based on data model Model to import xml file'.</span></span>
3.    <span data-ttu-id="f797d-135">En el campo **Nombre**, escriba 'Formato para importar el archivo xml'.</span><span class="sxs-lookup"><span data-stu-id="f797d-135">In the **Name** field, type 'Format to import xml file'.</span></span>
4.    <span data-ttu-id="f797d-136">Seleccione **Sí** en el campo **Admite la importación de datos**.</span><span class="sxs-lookup"><span data-stu-id="f797d-136">Select **Yes** in the **Supports data import** field.</span></span>
5.    <span data-ttu-id="f797d-137">Haga clic en **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="f797d-137">Click **Create configuration**.</span></span>

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a><span data-ttu-id="f797d-138">Diseñar un formato para analizar el archivo de entrada en formato xml</span><span class="sxs-lookup"><span data-stu-id="f797d-138">Design a format to parse incoming file in xml format</span></span>
1.    <span data-ttu-id="f797d-139">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="f797d-139">Click **Designer**.</span></span>
2.    <span data-ttu-id="f797d-140">Haga clic en **Agregar raíz** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="f797d-140">Click **Add root** to open the drop dialog.</span></span>
3.    <span data-ttu-id="f797d-141">En el árbol, seleccione **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="f797d-141">In the tree, select **XML\Element**.</span></span>
4.    <span data-ttu-id="f797d-142">Escriba 'raíz' en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="f797d-142">In the **Name** field, type 'root'.</span></span>
5.    <span data-ttu-id="f797d-143">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f797d-143">Click **OK**.</span></span>
6.    <span data-ttu-id="f797d-144">Haga clic en **Agregar** para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="f797d-144">Click **Add** to open the drop dialog.</span></span>
7.    <span data-ttu-id="f797d-145">En el árbol, seleccione **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="f797d-145">In the tree, select **XML\Element**.</span></span>
8.    <span data-ttu-id="f797d-146">En el campo **Nombre**, introduzca 'documento'.</span><span class="sxs-lookup"><span data-stu-id="f797d-146">In the **Name** field, type 'document'.</span></span>
9.    <span data-ttu-id="f797d-147">En el campo de **Multiplicidad**, seleccione **Uno o varios**.</span><span class="sxs-lookup"><span data-stu-id="f797d-147">In the **Multiplicity** field, select **One many**.</span></span>
10.    <span data-ttu-id="f797d-148">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f797d-148">Click **OK**.</span></span>
11.    <span data-ttu-id="f797d-149">En el árbol, seleccione **root\document**.</span><span class="sxs-lookup"><span data-stu-id="f797d-149">In the tree, select **root\document**.</span></span>
12.    <span data-ttu-id="f797d-150">Haga clic en **Agregar** para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="f797d-150">Click **Add** to open the drop dialog.</span></span>
13.    <span data-ttu-id="f797d-151">En el árbol, seleccione **XML\Atributo**.</span><span class="sxs-lookup"><span data-stu-id="f797d-151">In the tree, select **XML\Attribute**.</span></span>
14.    <span data-ttu-id="f797d-152">En el campo **Nombre**, escriba 'ID'.</span><span class="sxs-lookup"><span data-stu-id="f797d-152">In the **Name** field, type 'ID'.</span></span>
15.    <span data-ttu-id="f797d-153">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f797d-153">Click **OK**.</span></span>
16.    <span data-ttu-id="f797d-154">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f797d-154">Click **Save**.</span></span>

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a><span data-ttu-id="f797d-155">Diseñar una asignación de formato para guardar la información analizada al modelo de datos</span><span class="sxs-lookup"><span data-stu-id="f797d-155">Design a format mapping to save parsed information to data model</span></span>
1. <span data-ttu-id="f797d-156">Haga clic en **Asignar formato a modelo**.</span><span class="sxs-lookup"><span data-stu-id="f797d-156">Click **Map format to model**.</span></span>
2. <span data-ttu-id="f797d-157">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="f797d-157">Click **New**.</span></span>
3. <span data-ttu-id="f797d-158">En el campo **Definición**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f797d-158">In the **Definition** field, enter or select a value.</span></span>
4. <span data-ttu-id="f797d-159">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f797d-159">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="f797d-160">En el campo **Nombre**, introduzca 'Asignación'.</span><span class="sxs-lookup"><span data-stu-id="f797d-160">In the **Name** field, type 'Mapping'.</span></span>
6. <span data-ttu-id="f797d-161">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f797d-161">Click **Save**.</span></span>
7. <span data-ttu-id="f797d-162">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="f797d-162">Click **Designer**.</span></span>
8. <span data-ttu-id="f797d-163">En el árbol, expanda **format**.</span><span class="sxs-lookup"><span data-stu-id="f797d-163">In the tree, expand **format**.</span></span>
9. <span data-ttu-id="f797d-164">En el árbol, expanda **format\root: XML Element(root)**.</span><span class="sxs-lookup"><span data-stu-id="f797d-164">In the tree, expand **format\root: XML Element(root)**.</span></span>
10.    <span data-ttu-id="f797d-165">En el árbol, seleccione \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="f797d-165">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="f797d-166">(documento)\*\*.</span><span class="sxs-lookup"><span data-stu-id="f797d-166">(document)\*\*.</span></span>
11.    <span data-ttu-id="f797d-167">Haga clic en **Enlazar**.</span><span class="sxs-lookup"><span data-stu-id="f797d-167">Click **Bind**.</span></span>
12.    <span data-ttu-id="f797d-168">En el árbol, expanda \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="f797d-168">In the tree, expand \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="f797d-169">(documento)\*\*.</span><span class="sxs-lookup"><span data-stu-id="f797d-169">(document)\*\*.</span></span>
13.    <span data-ttu-id="f797d-170">En el árbol, seleccione \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="f797d-170">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="f797d-171">(documento)\id\*\*.</span><span class="sxs-lookup"><span data-stu-id="f797d-171">(document)\id\*\*.</span></span>
14.    <span data-ttu-id="f797d-172">En el árbol, expanda **List = format.root.document**.</span><span class="sxs-lookup"><span data-stu-id="f797d-172">In the tree, expand **List = format.root.document**.</span></span>
15.    <span data-ttu-id="f797d-173">En el árbol, seleccione **List = format.root.document\Code**.</span><span class="sxs-lookup"><span data-stu-id="f797d-173">In the tree, select **List = format.root.document\Code**.</span></span>
16.    <span data-ttu-id="f797d-174">Haga clic en **Enlazar**.</span><span class="sxs-lookup"><span data-stu-id="f797d-174">Click **Bind**.</span></span>
17.    <span data-ttu-id="f797d-175">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f797d-175">Click **Save**.</span></span>
18.    <span data-ttu-id="f797d-176">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f797d-176">Close the page.</span></span>
 
## <a name="run-format-mapping"></a><span data-ttu-id="f797d-177">Ejecutar asignación de formato</span><span class="sxs-lookup"><span data-stu-id="f797d-177">Run format mapping</span></span>
1. <span data-ttu-id="f797d-178">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="f797d-178">Click **Run**.</span></span>
2. <span data-ttu-id="f797d-179">Haga clic en **Examinar** y seleccione **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="f797d-179">Click **Browse** and select **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span></span>
3. <span data-ttu-id="f797d-180">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f797d-180">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="f797d-181">El archivo seleccionado no se ha importado ya que el diseño de formato asume la existencia de atributo ‘id’ para el elemento ‘document’, pero el archivo importado no contiene tal atributo.</span><span class="sxs-lookup"><span data-stu-id="f797d-181">The selected file has not been imported as the format design assumes the existence of 'id' attribute for the 'document' element, but the imported file contains no such attribute.</span></span>

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a><span data-ttu-id="f797d-182">Modificar la estructura del formato para gestionar el atributo xml como opcional</span><span class="sxs-lookup"><span data-stu-id="f797d-182">Modify format structure to handle xml attribute as optional</span></span>
1. <span data-ttu-id="f797d-183">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f797d-183">Close the page.</span></span>
2. <span data-ttu-id="f797d-184">En el árbol, expanda **root\document**.</span><span class="sxs-lookup"><span data-stu-id="f797d-184">In the tree, expand **root\document**.</span></span>
3. <span data-ttu-id="f797d-185">En el árbol, seleccione **root\document\id**.</span><span class="sxs-lookup"><span data-stu-id="f797d-185">In the tree, select **root\document\id**.</span></span>
4. <span data-ttu-id="f797d-186">Seleccione **Sí** en el campo **Cadena vacía para el atributo que falta** .</span><span class="sxs-lookup"><span data-stu-id="f797d-186">Select **Yes** in the **Empty string for missing attribute** field.</span></span>
5. <span data-ttu-id="f797d-187">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f797d-187">Click **Save**.</span></span>
 
## <a name="run-format-mapping-to-test-changes"></a><span data-ttu-id="f797d-188">Ejecutar asignación de formato para cambios de prueba</span><span class="sxs-lookup"><span data-stu-id="f797d-188">Run format mapping to test changes</span></span>
1. <span data-ttu-id="f797d-189">Haga clic en **Asignar formato a modelo**.</span><span class="sxs-lookup"><span data-stu-id="f797d-189">Click **Map format to model**.</span></span>
2. <span data-ttu-id="f797d-190">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="f797d-190">Click **Run**.</span></span>
3. <span data-ttu-id="f797d-191">Haga clic en **Examinar** y seleccione el archivo **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="f797d-191">Click **Browse** and select the **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml** file.</span></span>
4. <span data-ttu-id="f797d-192">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f797d-192">Click **OK**.</span></span>
5. <span data-ttu-id="f797d-193">Revise el archivo generado.</span><span class="sxs-lookup"><span data-stu-id="f797d-193">Review the generated file.</span></span> 

> [!NOTE]
> <span data-ttu-id="f797d-194">Se ha importado el mismo archivo ya que el diseño de formato ahora considera el atributo "id" para el elemento "documento" como opcional.</span><span class="sxs-lookup"><span data-stu-id="f797d-194">The same file has been imported as the format design now consider the 'id' attribute for the 'document' element as optional.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]