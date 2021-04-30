---
title: Interfaz de usuario estilo Microsoft Office en la Administración de documentos empresariales
description: Este tema explica cómo usar la nueva interfaz de usuario de documentos en la función de Administración de documentos empresariales del marco de informes electrónicos (ER).
author: v-anamir
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-anamir
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e6c5081f71a18dfac83b7aea950395436b42f50e
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881045"
---
# <a name="microsoft-office-style-user-interface-in-business-document-management"></a><span data-ttu-id="68356-103">Interfaz de usuario estilo Microsoft Office en la Administración de documentos empresariales</span><span class="sxs-lookup"><span data-stu-id="68356-103">Microsoft Office-style user interface in Business document management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="68356-104">La gestión de documentos empresariales aprovecha el marco de ER y permite a los usuarios empresariales editar plantillas de documentos empresariales mediante el servicio de Microsoft 365 o la aplicación de escritorio de Microsoft Office apropiada.</span><span class="sxs-lookup"><span data-stu-id="68356-104">Business document management lets business users edit business document templates by using a Microsoft 365 service or the appropriate Microsoft Office desktop application.</span></span> <span data-ttu-id="68356-105">Las ediciones pueden incluir cambios de diseño o nuevas implementaciones, o los usuarios pueden agregar marcadores de posición para incluir datos adicionales sin tener que cambiar el código fuente.</span><span class="sxs-lookup"><span data-stu-id="68356-105">Edits might include design changes or new deployments, or users might add placeholders to include additional data without having to change the source code.</span></span> <span data-ttu-id="68356-106">Para obtener más información sobre cómo trabajar con la gestión de documentos empresariales, vea [Resumen de gestión de documentos comerciales](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="68356-106">For more information about how to work with Business document management, see [Business document management overview](er-business-document-management.md).</span></span>

<span data-ttu-id="68356-107">La nueva interfaz de usuario (UI) es más clara y más cómoda de usar.</span><span class="sxs-lookup"><span data-stu-id="68356-107">The new user interface (UI) is clearer and more comfortable to use.</span></span> <span data-ttu-id="68356-108">El área **Documento empresarial** muestra solo las plantillas que están disponibles para el proveedor actual.</span><span class="sxs-lookup"><span data-stu-id="68356-108">The **Business document** area shows only the templates that are available for the current provider.</span></span> <span data-ttu-id="68356-109">En la interfaz de usuario anterior, la pestaña **Plantilla** incluía todas las plantillas que estaban disponibles para cualquier proveedor.</span><span class="sxs-lookup"><span data-stu-id="68356-109">In the previous UI, the **Template** tab listed all the templates that were available for any providers.</span></span> <span data-ttu-id="68356-110">También mostraba todas las plantillas que fueron creadas y editadas por cualquier usuario que tuviera el mismo rol.</span><span class="sxs-lookup"><span data-stu-id="68356-110">It also showed all the templates that were created and edited by any user who had the same role.</span></span>

<span data-ttu-id="68356-111">Puede usar el botón **Nuevo documento** para crear y editar una plantilla en una configuración de formato de informes electrónicos (ER) proporcionada por otro proveedor.</span><span class="sxs-lookup"><span data-stu-id="68356-111">You can use the **New document** button to create and edit a template in an Electronic reporting (ER) format configuration that is provided by another provider.</span></span> <span data-ttu-id="68356-112">En el ejemplo de este tema, el proveedor es Microsoft.</span><span class="sxs-lookup"><span data-stu-id="68356-112">In the example in this topic, the provider is Microsoft.</span></span> <span data-ttu-id="68356-113">Alternativamente, puede crear una plantilla cargando su propia plantilla en formato Excel.</span><span class="sxs-lookup"><span data-stu-id="68356-113">Alternatively, you can create a template by uploading your own template in Excel format.</span></span>


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWAVQg]

<span data-ttu-id="68356-114">El vídeo [Crear un nuevo documento comercial utilizando la gestión de documentos comerciales](https://youtu.be/gAIYl-mM_pw) (mostrado arriba) está incluido en la [lista de reproducción de Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible en YouTube.</span><span class="sxs-lookup"><span data-stu-id="68356-114">The [Create a new business document using Business document management](https://youtu.be/gAIYl-mM_pw) video (shown above) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

## <a name="make-the-new-document-ui-in-business-document-management-available"></a><span data-ttu-id="68356-115">Poner a disposición la nueva interfaz de usuario de documentos en la gestión de documentos empresariales</span><span class="sxs-lookup"><span data-stu-id="68356-115">Make the new document UI in Business document management available</span></span>

<span data-ttu-id="68356-116">Para comenzar a utilizar la nueva interfaz de usuario de documentos en la gestión de documentos empresariales, debe activar la característica **Experiencia de interfaz de usuario similar a oficina para la gestión de documentos empresariales** en el espacio de trabajo **Administración de características**.</span><span class="sxs-lookup"><span data-stu-id="68356-116">To start to use the new document UI in Business document management, you must turn on the **Office-like UI experience for Business document management** feature in the **Feature management** workspace.</span></span>

<span data-ttu-id="68356-117">Siga estos pasos para activar esta función para todas las entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="68356-117">Follow these steps to turn on this feature for all legal entities.</span></span>

1. <span data-ttu-id="68356-118">En el espacio de trabajo **Administración de características**, en la pestaña **Todo**, seleccione la característica **Experiencia de IU similar a oficina para la gestión de documentos empresariales** en la lista.</span><span class="sxs-lookup"><span data-stu-id="68356-118">In the **Feature management** workspace, on the **All** tab, select the **Office-like UI experience for Business document management** feature in the list.</span></span>
2. <span data-ttu-id="68356-119">Seleccione **Habilitar ahora** para activar la característica seleccionada.</span><span class="sxs-lookup"><span data-stu-id="68356-119">Select **Enable now** to turn on the selected feature.</span></span>
3. <span data-ttu-id="68356-120">Actualice la página para obtener acceso a la característica nueva.</span><span class="sxs-lookup"><span data-stu-id="68356-120">Refresh the page to access the new feature.</span></span>

## <a name="edit-templates-that-are-owned-by-other-providers"></a><span data-ttu-id="68356-121">Editar plantillas propiedad de otros proveedores</span><span class="sxs-lookup"><span data-stu-id="68356-121">Edit templates that are owned by other providers</span></span>

1. <span data-ttu-id="68356-122">En el espacio de trabajo de **Gestión de documentos empresariales**, seleccione **Nuevo documento**.</span><span class="sxs-lookup"><span data-stu-id="68356-122">In the **Business document management** workspace, select **New document**.</span></span>

    ![Espacio de trabajo de la gestión de documentos empresariales](./media/BDM_overview_new_template1.png)

2. <span data-ttu-id="68356-124">En la pestaña **Seleccionar**, seleccione el documento para usar como plantilla y luego seleccione **Crear documento**.</span><span class="sxs-lookup"><span data-stu-id="68356-124">On the **Select** tab, select the document to use as a template, and then select **Create document**.</span></span>

    ![Cuadro de diálogo Documentos empresariales](./media/BDM_overview_new_template2.png)

3. <span data-ttu-id="68356-126">En el nuevo cuadro de diálogo, en el campo **Título**, cambie el título según lo requiera.</span><span class="sxs-lookup"><span data-stu-id="68356-126">In the new dialog box, in the **Title** field, change the title as you require.</span></span> <span data-ttu-id="68356-127">El texto del título se usa para asignar un nombre a la nueva configuración del formato de ER que se crea automáticamente.</span><span class="sxs-lookup"><span data-stu-id="68356-127">The title text is used to name the new ER format configuration that is automatically created.</span></span> <span data-ttu-id="68356-128">La versión del borrador de esta configuración (**Copia de informe FTI de cliente (GER)**) incluirá la plantilla editada y se usará para ejecutar este formato de ER para el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="68356-128">The draft version of this configuration (**Customer FTI report (GER) Copy**) will contain the edited template and will be used to run this ER format for the current user.</span></span> <span data-ttu-id="68356-129">La plantilla original no modificada de la configuración del formato básico de ER se usará para ejecutar este formato de ER para los otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="68356-129">The original template from the base ER format configuration will be used to run this ER format for every other user.</span></span>
4. <span data-ttu-id="68356-130">En el campo **Nombre**, cambie el nombre de la primera revisión de la plantilla editable que se creará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="68356-130">In the **Name** field, change the name of the first revision of the editable template that will be automatically created.</span></span>
5. <span data-ttu-id="68356-131">En el campo **Comentario**, actualice los comentarios para la revisión de la plantilla editable que se creará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="68356-131">In the **Comment** field, update the remarks for the revision of the editable template that will be automatically created.</span></span>
6. <span data-ttu-id="68356-132">Seleccione **Aceptar** para confirmar el inicio del proceso de edición.</span><span class="sxs-lookup"><span data-stu-id="68356-132">Select **OK** to confirm the start of the editing process.</span></span>

    ![Cuadro de diálogo Creación de documentos](./media/BDM_overview_new_template3.png)

<span data-ttu-id="68356-134">El botón **Nuevo documento** se usa para crear y editar una plantilla en una configuración de formato ER proporcionada por otro proveedor.</span><span class="sxs-lookup"><span data-stu-id="68356-134">The **New document** button is used to create and edit a template in an ER format configuration that is provided by another provider.</span></span> <span data-ttu-id="68356-135">En el ejemplo, el proveedor es Microsoft.</span><span class="sxs-lookup"><span data-stu-id="68356-135">In this example, the provider is Microsoft.</span></span> <span data-ttu-id="68356-136">Cuando seleccione **Nuevo documento**, verá todas las plantillas que poseen los proveedores actuales y otros proveedores.</span><span class="sxs-lookup"><span data-stu-id="68356-136">When you select **New document**, you can view all the templates that are owned by current and other providers.</span></span> <span data-ttu-id="68356-137">Después de seleccionar la plantilla, se abrirá para editarla.</span><span class="sxs-lookup"><span data-stu-id="68356-137">After you select the template, it's opened for editing.</span></span> <span data-ttu-id="68356-138">La plantilla editada se almacenará en una nueva configuración del formato de ER que se genera automáticamente.</span><span class="sxs-lookup"><span data-stu-id="68356-138">The edited template will then be stored in a new ER format configuration that is automatically generated.</span></span>

## <a name="upload-a-template-that-uses-an-existing-excel-format"></a><span data-ttu-id="68356-139">Cargue una plantilla que use un formato de Excel existente</span><span class="sxs-lookup"><span data-stu-id="68356-139">Upload a template that uses an existing Excel format</span></span>
<span data-ttu-id="68356-140">Siga estos pasos para proporcionar la información requerida antes de cargar una plantilla.</span><span class="sxs-lookup"><span data-stu-id="68356-140">Follow these steps to provide required information before you upload a template.</span></span>

1. <span data-ttu-id="68356-141">En el espacio de trabajo de **Gestión de documentos empresariales**, seleccione **Nuevo documento**.</span><span class="sxs-lookup"><span data-stu-id="68356-141">In the **Business document management** workspace, select **New document**.</span></span>

    ![Espacio de trabajo de la gestión de documentos empresariales](./media/BDM_overview_new_template1.png)
    
2. <span data-ttu-id="68356-143">En la página **Crear una nueva plantilla**, en la pestaña **Subir**, en la pestaña **Plantilla**, seleccione **Navegar** para buscar y seleccionar el archivo de Excel que desea utilizar como plantilla.</span><span class="sxs-lookup"><span data-stu-id="68356-143">On the **Create a new template** page, on the **Upload** tab, on the **Template** tab, select **Browse** to find and select the Excel file that you want to use as a template.</span></span> <span data-ttu-id="68356-144">En la sección **Plantilla**, los campos **Título** y **Descripción** se completan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="68356-144">In the **Template** section, the **Title** and **Description** fields are automatically filled in.</span></span> <span data-ttu-id="68356-145">Especifican el nombre y la descripción de la nueva configuración de formato ER que se crea automáticamente.</span><span class="sxs-lookup"><span data-stu-id="68356-145">They specify the name and description of the new ER format configuration that is automatically created.</span></span> <span data-ttu-id="68356-146">Si es necesario, puede editar estos campos.</span><span class="sxs-lookup"><span data-stu-id="68356-146">You can edit these fields as you require.</span></span>
3. <span data-ttu-id="68356-147">En la sección **Tipo de Documento**, en el campo **Nombre**, especifique el tipo de documento comercial.</span><span class="sxs-lookup"><span data-stu-id="68356-147">In the **Document Type** section, in the **Name** field, specify the type of business document.</span></span> <span data-ttu-id="68356-148">Este valor se utilizará para buscar la fuente de datos correcta (es decir, la configuración del modelo ER).</span><span class="sxs-lookup"><span data-stu-id="68356-148">This value will be used to search the correct data source (that is, the ER model configuration).</span></span>

    ![Pestaña Plantilla](./media/BDM_overview_new_UI_import_21.jpg)

4. <span data-ttu-id="68356-150">En la pestaña **Fuente de datos**, en la ficha desplegable **Filtro**, seleccione **Aplicar filtro**.</span><span class="sxs-lookup"><span data-stu-id="68356-150">On the **Data source** tab, on the **Filter** FastTab, select **Apply filter**.</span></span> <span data-ttu-id="68356-151">En la sección **Fuente de datos**, el campo **Nombre** se rellena automáticamente o puede seleccionar manualmente un valor.</span><span class="sxs-lookup"><span data-stu-id="68356-151">In the **Data source** section, the **Name** field is automatically filled in, or you can manually select a value.</span></span> <span data-ttu-id="68356-152">Puede utilizar el filtro para buscar el nombre de fuente de datos adecuado por nombre, descripción, código de país o región y tipo de documento comercial.</span><span class="sxs-lookup"><span data-stu-id="68356-152">You can use the filter to search for the appropriate data source name by name, description, country/region code, and business document type.</span></span>

    ![Pestaña Origen de datos](./media/BDM_overview_new_UI_import_31.jpg)
    
    > [!NOTE]
    > <span data-ttu-id="68356-154">La ficha desplegable **Filtro** se utiliza para buscar la fuente de datos correcta (es decir, la configuración del modelo ER).</span><span class="sxs-lookup"><span data-stu-id="68356-154">The **Filter** FastTab is used to search the correct data source (that is, the ER model configuration).</span></span> <span data-ttu-id="68356-155">Puede editar todos los campos de filtro para encontrar la fuente de datos más adecuada para el documento que está cargando.</span><span class="sxs-lookup"><span data-stu-id="68356-155">You can edit all filter fields to find the most appropriate data source for the document that you're uploading.</span></span>
    > 
    > <span data-ttu-id="68356-156">Las condiciones de la ficha desplegable **Filtro** se utilizan como condiciones **O**.</span><span class="sxs-lookup"><span data-stu-id="68356-156">The conditions on the **Filter** FastTab are used as **OR** conditions.</span></span>
    
5. <span data-ttu-id="68356-157">En la pestaña **Asignación**, seleccione **Detectar automáticamente**.</span><span class="sxs-lookup"><span data-stu-id="68356-157">On the **Mapping** tab, select **Auto detect**.</span></span> <span data-ttu-id="68356-158">El campo **Definición raíz** se rellena automáticamente, o puede seleccionar manualmente un valor.</span><span class="sxs-lookup"><span data-stu-id="68356-158">The **Root definition** field is automatically filled in, or you can manually select a value.</span></span> <span data-ttu-id="68356-159">Esta pestaña muestra el mapeo final para los elementos de la plantilla y el modelo.</span><span class="sxs-lookup"><span data-stu-id="68356-159">This tab shows the end mapping for the elements from the template and the model.</span></span>

    ![Pestaña Asignación](./media/BDM_overview_new_UI_import_41.jpg)
    
   > [!NOTE]
   > <span data-ttu-id="68356-161">La asignación en la sección **Estructura de la plantilla** utiliza la coincidencia completa de las etiquetas o descripciones en la fuente de datos en el idioma del usuario y en el nombre de la celda en la plantilla.</span><span class="sxs-lookup"><span data-stu-id="68356-161">The mapping in the **Template structure** section uses the full match of the labels or descriptions in the data source in the user's language, and in the cell name in the template.</span></span>

6. <span data-ttu-id="68356-162">Seleccione **Crear documento** para confirmar que desea crear una plantilla e iniciar el proceso de edición.</span><span class="sxs-lookup"><span data-stu-id="68356-162">Select **Create document** to confirm that you want to create a template and start the editing process.</span></span>

<span data-ttu-id="68356-163">Para más información, vea [Resumen de gestión de documentos empresariales](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="68356-163">For more information, see [Business document management overview](er-business-document-management.md).</span></span>

<span data-ttu-id="68356-164">Si no hay un proveedor de informes electrónicos, puede crear uno.</span><span class="sxs-lookup"><span data-stu-id="68356-164">If there isn't a provider in Electronic reporting, you can create one.</span></span> <span data-ttu-id="68356-165">Si no hay un proveedor activo, puede seleccionar activar uno.</span><span class="sxs-lookup"><span data-stu-id="68356-165">If there's no active provider, you can select to activate one.</span></span>

- <span data-ttu-id="68356-166">Para crear un proveedor, cambie el nombre del proveedor en el campo **Nombre**, actualice la dirección de Internet del nuevo proveedor en el campo **Dirección de Internet** y seleccione **Aceptar** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="68356-166">To create a provider, change the name of the provider in the **Name** field, update the internet address of the new provider in the **Internet address** field, and select **OK** to confirm.</span></span>

    ![Crear nuevo proveedor en BDM](./media/bdm_create_provider.png)
    
- <span data-ttu-id="68356-168">Para activar el proveedor existente, elija el nombre del proveedor en el campo **Proveedor de configuración** y seleccione **Aceptar** para configurar el proveedor como activo.</span><span class="sxs-lookup"><span data-stu-id="68356-168">To activate existing provider, choose the name of the provider in the **Configuration provider** field, and select **OK** to set provider as active.</span></span>

    ![Activar proveedor en BDM](./media/bdm_choose_provider.png)

> [!NOTE]
> <span data-ttu-id="68356-170">Cada plantilla BDM hace referencia al proveedor como autor de la configuración.</span><span class="sxs-lookup"><span data-stu-id="68356-170">Each BDM template refers to the provider as the author of the configuration.</span></span> <span data-ttu-id="68356-171">Es por eso que se requiere un proveedor activo para la plantilla.</span><span class="sxs-lookup"><span data-stu-id="68356-171">This is why an active provider is required for the template.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
