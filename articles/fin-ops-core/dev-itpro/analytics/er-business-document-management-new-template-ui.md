---
title: Nueva interfaz de usuario de documentos en la gestión de documentos empresariales
description: Este tema proporciona información sobre cómo usar la nueva interfaz de usuario de documentos (UI) en la función de gestión de documentos comerciales del marco de informes electrónicos (ER).
author: v-anamir
manager: AnnBe
ms.date: 05/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-anamir
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 015b595f85397fc1cf2c0368814ddc0369176f82
ms.sourcegitcommit: 71ec2f48185b8104ca52ff70df52263ce5f87f26
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "3893204"
---
# <a name="new-document-user-interface-in-business-document-management"></a><span data-ttu-id="8e2c9-103">Nueva interfaz de usuario de documentos en la gestión de documentos empresariales</span><span class="sxs-lookup"><span data-stu-id="8e2c9-103">New document user interface in Business document management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8e2c9-104">La gestión de documentos empresariales aprovecha el marco de ER y permite a los usuarios empresariales editar plantillas de documentos empresariales mediante el servicio de Microsoft 365 o la aplicación de escritorio de Microsoft Office apropiada.</span><span class="sxs-lookup"><span data-stu-id="8e2c9-104">Business document management lets business users edit business document templates by using a Microsoft 365 service or the appropriate Microsoft Office desktop application.</span></span> <span data-ttu-id="8e2c9-105">Las ediciones pueden incluir cambios de diseño o nuevas implementaciones, o los usuarios pueden agregar marcadores de posición para incluir datos adicionales sin tener que cambiar el código fuente.</span><span class="sxs-lookup"><span data-stu-id="8e2c9-105">Edits might include design changes or new deployments, or users might add placeholders to include additional data without having to change the source code.</span></span> <span data-ttu-id="8e2c9-106">Para obtener más información sobre cómo trabajar con la gestión de documentos empresariales, vea [Resumen de gestión de documentos comerciales](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="8e2c9-106">For more information about how to work with Business document management, see [Business document management overview](er-business-document-management.md).</span></span>

<span data-ttu-id="8e2c9-107">La nueva interfaz de usuario del documento (UI) es más clara y más cómoda de usar.</span><span class="sxs-lookup"><span data-stu-id="8e2c9-107">The new document user interface (UI) is clearer and more comfortable to use.</span></span> <span data-ttu-id="8e2c9-108">El área **Documento empresarial** muestra solo las plantillas que están disponibles para el proveedor actual.</span><span class="sxs-lookup"><span data-stu-id="8e2c9-108">The **Business document** area shows only the templates that are available for the current provider.</span></span>

<span data-ttu-id="8e2c9-109">El botón **Nuevo documento** permite a los usuarios crear y editar una plantilla en una configuración de formato de informes electrónicos (ER) proporcionada por otro proveedor.</span><span class="sxs-lookup"><span data-stu-id="8e2c9-109">The **New document** button lets users create and edit a template in an Electronic reporting (ER) format configuration that is provided by another provider.</span></span> <span data-ttu-id="8e2c9-110">En el ejemplo de este tema, el proveedor es Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8e2c9-110">In the example in this topic, the provider is Microsoft.</span></span>

## <a name="make-the-new-document-ui-in-business-document-management-available"></a><span data-ttu-id="8e2c9-111">Poner a disposición la nueva interfaz de usuario de documentos en la gestión de documentos empresariales</span><span class="sxs-lookup"><span data-stu-id="8e2c9-111">Make the new document UI in Business document management available</span></span>

<span data-ttu-id="8e2c9-112">Para comenzar a utilizar la nueva interfaz de usuario de documentos en la gestión de documentos empresariales, debe activar la característica **Experiencia de interfaz de usuario similar a oficina para la gestión de documentos empresariales** en el espacio de trabajo **Administración de características**.</span><span class="sxs-lookup"><span data-stu-id="8e2c9-112">To start to use the new document UI in Business document management, you must turn on the **Office-like UI experience for Business document management** feature in the **Feature management** workspace.</span></span>

<span data-ttu-id="8e2c9-113">Siga estos pasos para activar esta función para todas las entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="8e2c9-113">Follow these steps to turn on this feature for all legal entities.</span></span>

1. <span data-ttu-id="8e2c9-114">En el espacio de trabajo **Administración de características**, en la pestaña **Nuevo**, seleccione la característica **Experiencia de IU similar a oficina para la gestión de documentos empresariales** en la lista.</span><span class="sxs-lookup"><span data-stu-id="8e2c9-114">In the **Feature management** workspace, on the **New** tab, select the **Office-like UI experience for Business document management** feature in the list.</span></span>
2. <span data-ttu-id="8e2c9-115">Seleccione **Habilitar ahora** para activar la característica seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8e2c9-115">Select **Enable now** to turn on the selected feature.</span></span>
3. <span data-ttu-id="8e2c9-116">Actualice la página para obtener acceso a la característica nueva.</span><span class="sxs-lookup"><span data-stu-id="8e2c9-116">Refresh the page to access the new feature.</span></span>

### <a name="edit-templates-that-are-owned-by-other-providers"></a><span data-ttu-id="8e2c9-117">Editar plantillas propiedad de otros proveedores</span><span class="sxs-lookup"><span data-stu-id="8e2c9-117">Edit templates that are owned by other providers</span></span>

1. <span data-ttu-id="8e2c9-118">En el espacio de trabajo de **Gestión de documentos empresariales**, seleccione **Nuevo documento**.</span><span class="sxs-lookup"><span data-stu-id="8e2c9-118">In the **Business document management** workspace, select **New document**.</span></span>

    ![Espacio de trabajo de la gestión de documentos empresariales](./media/BDM_overview_new_template1.png)

2. <span data-ttu-id="8e2c9-120">En el cuadro de diálogo, seleccione el documento para usar como plantilla y luego seleccione **Crear documento**.</span><span class="sxs-lookup"><span data-stu-id="8e2c9-120">In the dialog box, select the document to use as a template, and then select **Create document**.</span></span>

    ![Cuadro de diálogo Documentos empresariales](./media/BDM_overview_new_template2.png)

3. <span data-ttu-id="8e2c9-122">En el nuevo cuadro de diálogo, en el campo **Título**, cambie el título según lo requiera.</span><span class="sxs-lookup"><span data-stu-id="8e2c9-122">In the new dialog box, in the **Title** field, change the title as you require.</span></span> <span data-ttu-id="8e2c9-123">El texto del título se usa para asignar un nombre a la nueva configuración del formato de ER que se crea automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8e2c9-123">The title text is used to name the new ER format configuration that is automatically created.</span></span> <span data-ttu-id="8e2c9-124">La versión del borrador de esta configuración (**Copia de informe FTI de cliente (GER)**) incluirá la plantilla editada y se usará para ejecutar este formato de ER para el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="8e2c9-124">The draft version of this configuration (**Customer FTI report (GER) Copy**) will contain the edited template and will be used to run this ER format for the current user.</span></span> <span data-ttu-id="8e2c9-125">La plantilla original no modificada de la configuración del formato básico de ER se usará para ejecutar este formato de ER para los otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="8e2c9-125">The original template from the base ER format configuration will be used to run this ER format for every other user.</span></span>
4. <span data-ttu-id="8e2c9-126">En el campo **Nombre**, cambie el nombre de la primera revisión de la plantilla editable que se creará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8e2c9-126">In the **Name** field, change the name of the first revision of the editable template that will be automatically created.</span></span>
5. <span data-ttu-id="8e2c9-127">En el campo **Comentario**, actualice los comentarios para la revisión de la plantilla editable que se creará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8e2c9-127">In the **Comment** field, update the remarks for the revision of the editable template that will be automatically created.</span></span>
6. <span data-ttu-id="8e2c9-128">Seleccione **Aceptar** para confirmar el inicio del proceso de edición.</span><span class="sxs-lookup"><span data-stu-id="8e2c9-128">Select **OK** to confirm the start of the editing process.</span></span>

    ![Cuadro de diálogo Creación de documentos](./media/BDM_overview_new_template3.png)

<span data-ttu-id="8e2c9-130">El botón **Nuevo documento** se usa para crear y editar una plantilla en una configuración de formato ER proporcionada por otro proveedor.</span><span class="sxs-lookup"><span data-stu-id="8e2c9-130">The **New document** button is used to create and edit a template in an ER format configuration that is provided by another provider.</span></span> <span data-ttu-id="8e2c9-131">En el ejemplo, el proveedor es Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8e2c9-131">In this example, the provider is Microsoft.</span></span> <span data-ttu-id="8e2c9-132">Cuando seleccione **Nuevo documento**, verá todas las plantillas que poseen los proveedores actuales y otros proveedores.</span><span class="sxs-lookup"><span data-stu-id="8e2c9-132">When you select **New document**, you can view all the templates that are owned by current and other providers.</span></span> <span data-ttu-id="8e2c9-133">Después de seleccionar la plantilla, se abrirá para editarla.</span><span class="sxs-lookup"><span data-stu-id="8e2c9-133">After you select the template, it's opened for editing.</span></span> <span data-ttu-id="8e2c9-134">La plantilla editada se almacenará en una nueva configuración del formato de ER que se genera automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8e2c9-134">The edited template will then be stored in a new ER format configuration that is automatically generated.</span></span>

<span data-ttu-id="8e2c9-135">Para más información, vea [Resumen de gestión de documentos empresariales](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="8e2c9-135">For more information, see [Business document management overview](er-business-document-management.md).</span></span>
