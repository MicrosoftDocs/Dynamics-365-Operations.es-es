---
title: Importar archivos en formato XML con atributos opcionales
description: En este tema se proporciona información sobre el diseño de formatos de ER que especifican atributos XML para analizar documentos electrónicos entrantes en formato XML.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 5e2989906c5aa3ead9e46b8ed5333e880e5cf1c6
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769956"
---
# <a name="import-files-in-xml-format-with-optional-attributes"></a><span data-ttu-id="21bd9-103">Importar archivos en formato XML con atributos opcionales</span><span class="sxs-lookup"><span data-stu-id="21bd9-103">Import files in XML format with optional attributes</span></span>

<span data-ttu-id="21bd9-104">Puede diseñar formatos de informes electrónicos (ER) para analizar documentos electrónicos entrantes en formato XML.</span><span class="sxs-lookup"><span data-stu-id="21bd9-104">You can design Electronic reporting (ER) formats to parse incoming electronic documents in XML format.</span></span> <span data-ttu-id="21bd9-105">Algunos atributos de elementos XML se pueden especificar en formato de ER diseñados como opcionales.</span><span class="sxs-lookup"><span data-stu-id="21bd9-105">Certain attributes of XML elements can be specified in designed ER format as optional.</span></span> <span data-ttu-id="21bd9-106">Le permitirá gestionar correctamente archivos entrantes con y sin estos atributos XML.</span><span class="sxs-lookup"><span data-stu-id="21bd9-106">It will allow you to handle incoming files with and without such XML attributes properly.</span></span> <span data-ttu-id="21bd9-107">Puede usar el contenido de estos archivos para actualizar datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="21bd9-107">You can then use the content from these files to update application data.</span></span>

<span data-ttu-id="21bd9-108">Para obtener más información acerca de esta característica, complete los pasos del tema [(RCS) Importar archivos en formato XML con atributos opcionales](tasks/import-files-xml-format-optional-attributes.md), que forma parte del proceso empresarial 7.5.4.3 Adquirir/Desarrollar componentes de soluciones/servicios de TI (10677).</span><span class="sxs-lookup"><span data-stu-id="21bd9-108">To learn more about this feature, complete the steps in the topic, [(RCS) Import files in XML format with optional attributes](tasks/import-files-xml-format-optional-attributes.md), which is part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process.</span></span> <span data-ttu-id="21bd9-109">Puede descargar esta guía de tareas y los archivos de ejemplo asociados desde el [Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="21bd9-109">You can download this task guide and associated sample files from the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span>


| <span data-ttu-id="21bd9-110">Descripción del contenido</span><span class="sxs-lookup"><span data-stu-id="21bd9-110">Content description</span></span>       | <span data-ttu-id="21bd9-111">Archivo</span><span class="sxs-lookup"><span data-stu-id="21bd9-111">File</span></span>                                                         |
|---------------------------|--------------------------------------------------------------|
| <span data-ttu-id="21bd9-112">Archivo de ejemplo en formato XML</span><span class="sxs-lookup"><span data-stu-id="21bd9-112">Sample file in XML format</span></span> | <span data-ttu-id="21bd9-113">IncomingDocumentToLearnHowToHandleOptionalAttributes.xml</span><span class="sxs-lookup"><span data-stu-id="21bd9-113">IncomingDocumentToLearnHowToHandleOptionalAttributes.xml</span></span>     |
| <span data-ttu-id="21bd9-114">Guía de tareas</span><span class="sxs-lookup"><span data-stu-id="21bd9-114">Task guide</span></span>                | <span data-ttu-id="21bd9-115">RCS Importar archivos en formato XML con atributos opcionales.axtr</span><span class="sxs-lookup"><span data-stu-id="21bd9-115">RCS Import files in XML format with optional attributes.axtr</span></span> |


<span data-ttu-id="21bd9-116">En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede diseñar una configuración de formato de ER para importar archivos en formato XML que contengan atributos opcionales.</span><span class="sxs-lookup"><span data-stu-id="21bd9-116">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can design ER format configuration to import files in XML format containing optional attributes.</span></span> <span data-ttu-id="21bd9-117">Para completar estos pasos, primero debe completar los pasos del procedimiento [Crear proveedores de configuración y marcarlos como activos](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="21bd9-117">To complete these steps, you must first complete the steps in the procedure, [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="21bd9-118">Antes de empezar, descargue y guarde localmente el archivo IncomingDocumentToLearnHowToHandleOptionalAttributes.xml del Centro de descarga de Microsoft (https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="21bd9-118">Before you begin, download and save locally the IncomingDocumentToLearnHowToHandleOptionalAttributes.xml file from Microsoft Download Center (https://go.microsoft.com/fwlink/?linkid=874684 ).</span></span>

1. <span data-ttu-id="21bd9-119">Vaya a **Administración de la organización** > **Espacios de trabajo** > **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-119">Go to **Organization administration** > **Workspaces** > **Electronic reporting**.</span></span>
2. <span data-ttu-id="21bd9-120">Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como **Activo**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-120">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="21bd9-121">Si no ve a este proveedor de configuración, complete los pasos del tema [Crear proveedores de configuración y marcarlos como activos](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="21bd9-121">If you don’t see this configuration provider, complete the steps in the topic, [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
3. <span data-ttu-id="21bd9-122">Haga clic en **Configuraciones de informes**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-122">Click **Reporting configurations**.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="21bd9-123">Creación de un nuevo modelo de configuración de datos</span><span class="sxs-lookup"><span data-stu-id="21bd9-123">Create a new data model configuration</span></span>
1. <span data-ttu-id="21bd9-124">Haga clic en **Crear configuración** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="21bd9-124">Click **Create configuration** to open the drop dialog.</span></span>
2. <span data-ttu-id="21bd9-125">En el campo **Nombre**, escriba 'Modelo para importar el archivo xml'.</span><span class="sxs-lookup"><span data-stu-id="21bd9-125">In the **Name** field, type 'Model to import xml file'.</span></span>
3. <span data-ttu-id="21bd9-126">Haga clic en **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-126">Click **Create configuration**.</span></span>
4. <span data-ttu-id="21bd9-127">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-127">Click **Designer**.</span></span>
5. <span data-ttu-id="21bd9-128">Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="21bd9-128">Click **New** to open the drop dialog.</span></span>
6. <span data-ttu-id="21bd9-129">Escriba 'Raíz' en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-129">In the **Name** field, type 'Root'.</span></span>
7. <span data-ttu-id="21bd9-130">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-130">Click **Add**.</span></span>
8. <span data-ttu-id="21bd9-131">Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="21bd9-131">Click **New** to open the drop dialog.</span></span>
9. <span data-ttu-id="21bd9-132">Escriba 'Lista' en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-132">In the **Name** field, type 'List'.</span></span>
10. <span data-ttu-id="21bd9-133">En el campo **Tipo de artículo**, seleccione **Lista de registros**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-133">In the **Item type** field, select **Record list**.</span></span>
11. <span data-ttu-id="21bd9-134">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-134">Click **Add**.</span></span>
12. <span data-ttu-id="21bd9-135">Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="21bd9-135">Click **New** to open the drop dialog.</span></span>
13. <span data-ttu-id="21bd9-136">En el campo **Nombre**, escriba 'Código'.</span><span class="sxs-lookup"><span data-stu-id="21bd9-136">In the **Name** field, type 'Code'.</span></span>
14. <span data-ttu-id="21bd9-137">En el campo **Tipo de artículo**, seleccione **Cadena**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-137">In the **Item type** field, select **String**.</span></span>
15. <span data-ttu-id="21bd9-138">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-138">Click **Add**.</span></span>
16. <span data-ttu-id="21bd9-139">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-139">Click **Save**.</span></span>
17. <span data-ttu-id="21bd9-140">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="21bd9-140">Close the page.</span></span>
18. <span data-ttu-id="21bd9-141">Haga clic en **Cambiar estado**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-141">Click **Change status**.</span></span>
19. <span data-ttu-id="21bd9-142">Haga clic en **Completar**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-142">Click **Complete**.</span></span>
20. <span data-ttu-id="21bd9-143">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-143">Click **OK**.</span></span>

## <a name="create-a-format-for-data-import"></a><span data-ttu-id="21bd9-144">Crear un formato para la importación de datos</span><span class="sxs-lookup"><span data-stu-id="21bd9-144">Create a format for data import</span></span>
1. <span data-ttu-id="21bd9-145">Haga clic en **Crear configuración** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="21bd9-145">Click **Create configuration** to open the drop dialog.</span></span>
2. <span data-ttu-id="21bd9-146">En el campo **Nuevo**, introduzca 'Formato basado en el modelo de datos del archivo Modelo para importar.xml'.</span><span class="sxs-lookup"><span data-stu-id="21bd9-146">In the **New** field, enter 'Format based on data model Model to import xml file'.</span></span>
3. <span data-ttu-id="21bd9-147">En el campo **Nombre**, escriba 'Formato para importar el archivo xml'.</span><span class="sxs-lookup"><span data-stu-id="21bd9-147">In the **Nam**e field, type 'Format to import xml file'.</span></span> 
4. <span data-ttu-id="21bd9-148">Seleccione **Sí** en el campo **Admite la importación de datos**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-148">Select **Yes** in the **Supports data import** field.</span></span>
5. <span data-ttu-id="21bd9-149">Haga clic en **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-149">Click **Create configuration**.</span></span>

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a><span data-ttu-id="21bd9-150">Diseñar un formato para analizar el archivo de entrada en formato xml</span><span class="sxs-lookup"><span data-stu-id="21bd9-150">Design a format to parse incoming file in xml format</span></span>
1. <span data-ttu-id="21bd9-151">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-151">Click **Designer**.</span></span>
2. <span data-ttu-id="21bd9-152">Haga clic en **Agregar raíz** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="21bd9-152">Click **Add root** to open the drop dialog.</span></span>
3. <span data-ttu-id="21bd9-153">En el árbol, seleccione **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-153">In the tree, select **XML\Element**.</span></span>
4. <span data-ttu-id="21bd9-154">Escriba 'raíz' en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-154">In the **Name** field, type 'root'.</span></span>
5. <span data-ttu-id="21bd9-155">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-155">Click **OK**.</span></span>
6. <span data-ttu-id="21bd9-156">Haga clic en **Agregar** para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="21bd9-156">Click **Add** to open the drop dialog.</span></span>
7. <span data-ttu-id="21bd9-157">En el árbol, seleccione **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-157">In the tree, select **XML\Element**.</span></span>
8. <span data-ttu-id="21bd9-158">En el campo **Nombre**, introduzca 'documento'.</span><span class="sxs-lookup"><span data-stu-id="21bd9-158">In the **Name** field, type 'document'.</span></span>
9. <span data-ttu-id="21bd9-159">En el campo de **Multiplicidad**, seleccione **Uno o varios**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-159">In the **Multiplicity** field, select **One many**.</span></span>
10. <span data-ttu-id="21bd9-160">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-160">Click **OK**.</span></span>
11. <span data-ttu-id="21bd9-161">En el árbol, seleccione **root\document**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-161">In the tree, select **root\document**.</span></span>
12. <span data-ttu-id="21bd9-162">Haga clic en **Agregar** para abrir el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="21bd9-162">Click **Add** to open the drop dialog.</span></span>
13. <span data-ttu-id="21bd9-163">En el árbol, seleccione **XML\Atributo**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-163">In the tree, select **XML\Attribute**.</span></span>
14. <span data-ttu-id="21bd9-164">En el campo **Nombre**, escriba 'id'.</span><span class="sxs-lookup"><span data-stu-id="21bd9-164">In the **Name** field, type 'id'.</span></span>
15. <span data-ttu-id="21bd9-165">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-165">Click **OK**.</span></span>
16. <span data-ttu-id="21bd9-166">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-166">Click **Save**.</span></span>

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a><span data-ttu-id="21bd9-167">Diseñar una asignación de formato para guardar la información analizada al modelo de datos</span><span class="sxs-lookup"><span data-stu-id="21bd9-167">Design a format mapping to save parsed information to data model</span></span>
1.  <span data-ttu-id="21bd9-168">Haga clic en **Asignar formato a modelo**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-168">Click **Map format to model**.</span></span>
2.  <span data-ttu-id="21bd9-169">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-169">Click **New**.</span></span>
3.  <span data-ttu-id="21bd9-170">En el campo **Definición**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="21bd9-170">In the **Definition** field, enter or select a value.</span></span>
4.  <span data-ttu-id="21bd9-171">En el campo **Nombre**, introduzca 'Asignación'.</span><span class="sxs-lookup"><span data-stu-id="21bd9-171">In the **Name** field, type 'Mapping'.</span></span>
5.  <span data-ttu-id="21bd9-172">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-172">Click **Save**.</span></span>
6.  <span data-ttu-id="21bd9-173">Haga clic en **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-173">Click **Designer**.</span></span>
7.  <span data-ttu-id="21bd9-174">En el árbol, expanda **format**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-174">In the tree, expand **format**.</span></span>
8.  <span data-ttu-id="21bd9-175">En el árbol, expanda **format\root: XML Element(root)**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-175">In the tree, expand **format\root: XML Element(root)**.</span></span>
9.  <span data-ttu-id="21bd9-176">En el árbol, seleccione \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="21bd9-176">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="21bd9-177">(documento)\*\*.</span><span class="sxs-lookup"><span data-stu-id="21bd9-177">(document)\*\*.</span></span>
10. <span data-ttu-id="21bd9-178">Haga clic en **Enlazar**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-178">Click **Bind**.</span></span>
11. <span data-ttu-id="21bd9-179">En el árbol, expanda \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="21bd9-179">In the tree, expand \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="21bd9-180">(documento)\*\*.</span><span class="sxs-lookup"><span data-stu-id="21bd9-180">(document)\*\*.</span></span>
12. <span data-ttu-id="21bd9-181">En el árbol, seleccione \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="21bd9-181">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="21bd9-182">(documento)\id\*\*.</span><span class="sxs-lookup"><span data-stu-id="21bd9-182">(document)\id\*\*.</span></span>
13. <span data-ttu-id="21bd9-183">En el árbol, expanda **List = format.root.document**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-183">In the tree, expand **List = format.root.document**.</span></span>
14. <span data-ttu-id="21bd9-184">En el árbol, seleccione **List = format.root.document\Code**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-184">In the tree, select **List = format.root.document\Code**.</span></span>
15. <span data-ttu-id="21bd9-185">Haga clic en **Enlazar**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-185">Click **Bind**.</span></span>
16. <span data-ttu-id="21bd9-186">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-186">Click **Save**.</span></span>
17. <span data-ttu-id="21bd9-187">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="21bd9-187">Close the page.</span></span>

## <a name="run-format-mapping"></a><span data-ttu-id="21bd9-188">Ejecutar asignación de formato</span><span class="sxs-lookup"><span data-stu-id="21bd9-188">Run format mapping</span></span>
1. <span data-ttu-id="21bd9-189">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-189">Click **Run**.</span></span>
2. <span data-ttu-id="21bd9-190">Haga clic en **Examinar** y seleccione el archivo **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-190">Click **Browse** and select the file, **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span></span>
3. <span data-ttu-id="21bd9-191">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-191">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="21bd9-192">El archivo seleccionado no se ha importado ya que el diseño de formato asume la existencia de atributo ‘id’ para el elemento ‘document’, pero el archivo importado no contiene tal atributo.</span><span class="sxs-lookup"><span data-stu-id="21bd9-192">The selected file has not been imported as the format design assumes the existence of ‘id’ attribute for the ‘document’ element, but the imported file contains no such attribute.</span></span>

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a><span data-ttu-id="21bd9-193">Modificar la estructura del formato para gestionar el atributo xml como opcional</span><span class="sxs-lookup"><span data-stu-id="21bd9-193">Modify format structure to handle xml attribute as optional</span></span>
1. <span data-ttu-id="21bd9-194">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="21bd9-194">Close the page.</span></span>
2. <span data-ttu-id="21bd9-195">En el árbol, expanda **root\document**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-195">In the tree, expand **root\document**.</span></span>
3. <span data-ttu-id="21bd9-196">En el árbol, seleccione **root\document\id**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-196">In the tree, select **root\document\id**.</span></span>
4. <span data-ttu-id="21bd9-197">En el campo **Cadena vacía para el atributo que falta**, selección **Sí**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-197">In the **Empty string for missing attribute** field, select **Yes**.</span></span>
5. <span data-ttu-id="21bd9-198">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-198">Click **Save**.</span></span>

## <a name="run-format-mapping-to-test-changes"></a><span data-ttu-id="21bd9-199">Ejecutar asignación de formato para cambios de prueba</span><span class="sxs-lookup"><span data-stu-id="21bd9-199">Run format mapping to test changes</span></span>
1. <span data-ttu-id="21bd9-200">Haga clic en **Asignar formato a modelo**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-200">Click **Map format to model**.</span></span>
2. <span data-ttu-id="21bd9-201">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-201">Click **Run**.</span></span>
3. <span data-ttu-id="21bd9-202">Haga clic en **Examinar** y seleccione el archivo **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-202">Click **Browse** and select the file, **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span></span>
4. <span data-ttu-id="21bd9-203">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="21bd9-203">Click **OK**.</span></span>
5. <span data-ttu-id="21bd9-204">Revise el archivo generado.</span><span class="sxs-lookup"><span data-stu-id="21bd9-204">Review the generated file.</span></span> <span data-ttu-id="21bd9-205">Tenga en cuenta que se ha importado el mismo archivo ya que el diseño de formato ahora considera el atributo ‘id’ para el elemento ‘documento‘ como opcional.</span><span class="sxs-lookup"><span data-stu-id="21bd9-205">Note that same file has been imported as the format design now consider the ‘id’ attribute for the ‘document’ element as optional.</span></span>