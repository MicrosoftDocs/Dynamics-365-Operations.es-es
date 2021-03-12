---
title: Actualizar la estructura de una plantilla de documento empresarial
description: Este tema explica cómo actualizar la estructura de una plantilla de documento empresarial mediante la función de administración de documentos empresariales.
author: NickSelin
manager: AnnBe
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-12-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: cb0188e372b5f6275472cf040d10bb796eed1858
ms.sourcegitcommit: 95d2fc0fa7d17d3a96f7969f12c985b018b4ff94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "4728098"
---
# <a name="update-the-structure-of-a-business-document-template"></a><span data-ttu-id="1ec80-103">Actualizar la estructura de una plantilla de documento empresarial</span><span class="sxs-lookup"><span data-stu-id="1ec80-103">Update the structure of a business document template</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="1ec80-104">En el panel **Estructura de la plantilla** del editor de plantillas [Gestión de documentos empresariales](er-business-document-management.md), puede modificar una plantilla de documento empresarial [agregando nuevos campos](er-bdm-add-field-to-excel-template.md) a una plantilla en Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="1ec80-104">In the **Template structure** pane of the [Business document management](er-business-document-management.md) template editor, you can modify a business document template by [adding new fields](er-bdm-add-field-to-excel-template.md) to a template in Microsoft Excel.</span></span> <span data-ttu-id="1ec80-105">La estructura de la plantilla se actualiza automáticamente en Dynamics 365 Finance, de modo que refleje los cambios que realizó en el panel **Estructura de la plantilla**.</span><span class="sxs-lookup"><span data-stu-id="1ec80-105">The structure of the template is then automatically updated in Dynamics 365 Finance, so that it reflects the changes that you made in the **Template structure** pane.</span></span>

<span data-ttu-id="1ec80-106">También puede modificar una plantilla utilizando la funcionalidad en línea de Office 365.</span><span class="sxs-lookup"><span data-stu-id="1ec80-106">You can also modify a template by using Office 365 online functionality.</span></span> <span data-ttu-id="1ec80-107">Por ejemplo, puede agregar un nuevo elemento con nombre, como una imagen o una forma, a la hoja de trabajo editable.</span><span class="sxs-lookup"><span data-stu-id="1ec80-107">For example, you can add a new named item, such as a picture or shape, to the editable worksheet.</span></span> <span data-ttu-id="1ec80-108">En este caso, la estructura de la plantilla no se actualiza automáticamente en Finance y el elemento que agregó no aparece en el panel **Estructura de la plantilla**.</span><span class="sxs-lookup"><span data-stu-id="1ec80-108">In this case, the structure of the template isn't automatically updated in Finance, and the item that you added doesn't appear in the **Template structure** pane.</span></span> <span data-ttu-id="1ec80-109">Actualice manualmente la estructura de la plantilla en Finance seleccionando **Estructura de actualización** en la página del editor de plantillas.</span><span class="sxs-lookup"><span data-stu-id="1ec80-109">Manually update the template structure in Finance by selecting **Update structure** on the template editor page.</span></span>

<span data-ttu-id="1ec80-110">Para obtener más información acerca de esta característica, complete el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1ec80-110">For more information about this feature, complete the following example.</span></span>

## <a name="example-update-the-structure-of-a-business-document-template"></a><span data-ttu-id="1ec80-111">Ejemplo: Actualizar la estructura de una plantilla de documento empresarial</span><span class="sxs-lookup"><span data-stu-id="1ec80-111">Example: Update the structure of a business document template</span></span>

<span data-ttu-id="1ec80-112">Este ejemplo muestra cómo un administrador del sistema puede actualizar la estructura de una plantilla de documento empresarial en Finance después de modificar la plantilla en Office Online.</span><span class="sxs-lookup"><span data-stu-id="1ec80-112">This example shows how a system administrator can update the structure of a business document template in Finance after the template is modified in Office Online.</span></span> <span data-ttu-id="1ec80-113">Las siguientes secciones explican los pasos involucrados.</span><span class="sxs-lookup"><span data-stu-id="1ec80-113">The following sections explain the steps that are involved.</span></span>

### <a name="prepare-a-business-document-template-for-editing"></a><span data-ttu-id="1ec80-114">Prepare una plantilla de documento empresarial para editar</span><span class="sxs-lookup"><span data-stu-id="1ec80-114">Prepare a business document template for editing</span></span>

<span data-ttu-id="1ec80-115">Complete los siguientes procedimientos en [Descripción general de la gestión de documentos empresariales](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="1ec80-115">Complete the following procedures in [Business document management overview](er-business-document-management.md).</span></span>

1. [<span data-ttu-id="1ec80-116">Configurar los parámetros de ER</span><span class="sxs-lookup"><span data-stu-id="1ec80-116">Configure ER parameters</span></span>](er-business-document-management.md#configure-er-parameters)
2. [<span data-ttu-id="1ec80-117">Importar soluciones de ER</span><span class="sxs-lookup"><span data-stu-id="1ec80-117">Import ER solutions</span></span>](er-business-document-management.md#import-er-solutions)
3. [<span data-ttu-id="1ec80-118">Habilitar la gestión de documentos empresariales</span><span class="sxs-lookup"><span data-stu-id="1ec80-118">Enable Business document management</span></span>](er-business-document-management.md#enable-business-document-management)
4. [<span data-ttu-id="1ec80-119">Configurar parámetros</span><span class="sxs-lookup"><span data-stu-id="1ec80-119">Configure parameters</span></span>](er-business-document-management.md#configure-parameters)

### <a name="edit-a-business-document-template"></a><span data-ttu-id="1ec80-120">Editar una plantilla de documento empresarial</span><span class="sxs-lookup"><span data-stu-id="1ec80-120">Edit a business document template</span></span>

1. <span data-ttu-id="1ec80-121">En el espacio de trabajo de **Gestión de documentos empresariales**, seleccione **Nuevo documento**.</span><span class="sxs-lookup"><span data-stu-id="1ec80-121">In the **Business document management** workspace, select **New document**.</span></span>
2. <span data-ttu-id="1ec80-122">En la página **Crear una nueva plantilla**, seleccione el modelo **Factura de servicios gratuitos (muestra de ER) (Excel)**.</span><span class="sxs-lookup"><span data-stu-id="1ec80-122">On the **Create a new template** page, select the **Free text invoice (ER sample)(Excel)** template.</span></span>
3. <span data-ttu-id="1ec80-123">Seleccione **Crear documento**.</span><span class="sxs-lookup"><span data-stu-id="1ec80-123">Select **Create document**.</span></span>
4. <span data-ttu-id="1ec80-124">En el campo **Título**, introduzca **Muestra FTI Litware**.</span><span class="sxs-lookup"><span data-stu-id="1ec80-124">In the **Title** field, enter **FTI sample Litware**.</span></span>
5. <span data-ttu-id="1ec80-125">Seleccione **Aceptar** para crear una plantilla nueva.</span><span class="sxs-lookup"><span data-stu-id="1ec80-125">Select **OK** to create the new template.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1ec80-126">Si aún no ha iniciado sesión en Office Online se le [dirigirá a la página de inicio de sesión de Office 365](er-business-document-management.md#frequently-asked-questions).</span><span class="sxs-lookup"><span data-stu-id="1ec80-126">If you haven't yet signed in to Office Online, you're [directed to the Office 365 sign-in page](er-business-document-management.md#frequently-asked-questions).</span></span> <span data-ttu-id="1ec80-127">Para volver a su entorno de Finance, seleccione el botón **Atrás** en su navegador.</span><span class="sxs-lookup"><span data-stu-id="1ec80-127">To return to your Finance environment, select the **Back** button in your browser.</span></span>

    <span data-ttu-id="1ec80-128">La nueva plantilla se abre para su edición en el control incrustado de Excel Online en la página del editor de plantillas.</span><span class="sxs-lookup"><span data-stu-id="1ec80-128">The new template is opened for editing in the Excel Online embedded control on the template editor page.</span></span>

<span data-ttu-id="1ec80-129">[![Uso del espacio de trabajo de administración de documentos empresariales para comenzar a editar una plantilla de documento empresarial](./media/er-bdm-update-structure1.gif)](./media/er-bdm-update-structure1.gif)</span><span class="sxs-lookup"><span data-stu-id="1ec80-129">[![Using the Business document management workspace to start to edit a business document template](./media/er-bdm-update-structure1.gif)](./media/er-bdm-update-structure1.gif)</span></span>

### <a name="review-the-current-structure-of-the-editable-template"></a><span data-ttu-id="1ec80-130">Revise la estructura actual de la plantilla editable</span><span class="sxs-lookup"><span data-stu-id="1ec80-130">Review the current structure of the editable template</span></span>

1. <span data-ttu-id="1ec80-131">En Excel Online, en la cinta, en la pestaña **Ver**, en el grupo **Mostrar**, seleccione **Líneas de cuadrícula**.</span><span class="sxs-lookup"><span data-stu-id="1ec80-131">In Excel Online, on the ribbon, on the **View** tab, in the **Show** group, select **Gridlines**.</span></span>
2. <span data-ttu-id="1ec80-132">En la plantilla editable, seleccione el rectángulo sobre el título de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="1ec80-132">In the editable template, select the rectangle above the template title.</span></span> <span data-ttu-id="1ec80-133">Este rectángulo es una imagen que se llama **rptHeaderCompLogo**.</span><span class="sxs-lookup"><span data-stu-id="1ec80-133">This rectangle is a picture that is named **rptHeaderCompLogo**.</span></span>
3. <span data-ttu-id="1ec80-134">Si el panel **Estructura de la plantilla** está oculto, seleccione **Mostrar estructura**.</span><span class="sxs-lookup"><span data-stu-id="1ec80-134">If the **Template structure** pane is hidden, select **Show structure**.</span></span>
4. <span data-ttu-id="1ec80-135">En el panel **Estructura de la plantilla**, expanda **Informe \> Factura \> rptHeader \> rptHeaderPart1**.</span><span class="sxs-lookup"><span data-stu-id="1ec80-135">In the **Template structure** pane, expand **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>
5. <span data-ttu-id="1ec80-136">Observe que, en la estructura de la plantilla en Finance, el elemento **rptHeaderCompLogo** se presenta como un elemento secundario de **Informe \> Factura \> rptHeader \> rptHeaderPart1**.</span><span class="sxs-lookup"><span data-stu-id="1ec80-136">Notice that, in the template structure in Finance, the **rptHeaderCompLogo** item is presented as a child item of **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>

<span data-ttu-id="1ec80-137">[![Usar el espacio de trabajo de administración de documentos empresariales para revisar la estructura actual de una plantilla editable](./media/er-bdm-update-structure2.gif)](./media/er-bdm-update-structure2.gif)</span><span class="sxs-lookup"><span data-stu-id="1ec80-137">[![Using the Business document management workspace to review the current structure of an editable template](./media/er-bdm-update-structure2.gif)](./media/er-bdm-update-structure2.gif)</span></span>

### <a name="update-the-structure-of-a-business-document-template-by-deleting-a-picture"></a><span data-ttu-id="1ec80-138">Actualizar la estructura de una plantilla de documento empresarial eliminando una imagen</span><span class="sxs-lookup"><span data-stu-id="1ec80-138">Update the structure of a business document template by deleting a picture</span></span>

1. <span data-ttu-id="1ec80-139">En Excel Online, en la plantilla editable, seleccione la imagen **rptHeaderCompLogo**.</span><span class="sxs-lookup"><span data-stu-id="1ec80-139">In Excel Online, in the editable template, select the **rptHeaderCompLogo** picture.</span></span>
2. <span data-ttu-id="1ec80-140">Siga uno de estos pasos para eliminar la imagen seleccionada de la plantilla editable:</span><span class="sxs-lookup"><span data-stu-id="1ec80-140">Follow one of these steps to delete the selected picture from the editable template:</span></span>

    - <span data-ttu-id="1ec80-141">Seleccione la tecla **Suprimir** en su teclado.</span><span class="sxs-lookup"><span data-stu-id="1ec80-141">Select the **Delete** key on your keyboard.</span></span>
    - <span data-ttu-id="1ec80-142">Seleccione y mantenga presionada (o haga clic con el botón derecho) en la imagen y luego seleccione **Cortar**.</span><span class="sxs-lookup"><span data-stu-id="1ec80-142">Select and hold (or right-click) the picture, and then select **Cut**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1ec80-143">El elemento **rptHeaderCompLogo** todavía está presente en la estructura de la plantilla en Finance, aunque la imagen ya no se incluye en la plantilla de Excel.</span><span class="sxs-lookup"><span data-stu-id="1ec80-143">The **rptHeaderCompLogo** item is currently still present in the template structure in Finance, even though the picture is no longer included in the Excel template.</span></span>

3. <span data-ttu-id="1ec80-144">Seleccione **Estructura de actualización** para sincronizar la estructura de la plantilla editable en Excel y Finance.</span><span class="sxs-lookup"><span data-stu-id="1ec80-144">Select **Update structure** to sync the structure of the editable template in Excel and Finance.</span></span>
4. <span data-ttu-id="1ec80-145">En el panel **Estructura de la plantilla**, expanda **Informe \> Factura \> rptHeader \> rptHeaderPart1**.</span><span class="sxs-lookup"><span data-stu-id="1ec80-145">In the **Template structure** pane, expand **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>
5. <span data-ttu-id="1ec80-146">Fíjese en que el elemento **rptHeaderCompLogo** ya no se incluye en la estructura de la plantilla en Finance.</span><span class="sxs-lookup"><span data-stu-id="1ec80-146">Notice that the **rptHeaderCompLogo** item is no longer included in the template structure in Finance.</span></span>

<span data-ttu-id="1ec80-147">[![Uso del espacio de trabajo de administración de documentos empresariales para eliminar una imagen de una plantilla de documento empresarial](./media/er-bdm-update-structure3.gif)](./media/er-bdm-update-structure3.gif)</span><span class="sxs-lookup"><span data-stu-id="1ec80-147">[![Using the Business document management workspace to delete a picture from a business document template](./media/er-bdm-update-structure3.gif)](./media/er-bdm-update-structure3.gif)</span></span>

### <a name="update-the-structure-of-a-business-document-template-by-adding-a-picture"></a><span data-ttu-id="1ec80-148">Actualizar la estructura de una plantilla de documento empresarial añadiendo una imagen</span><span class="sxs-lookup"><span data-stu-id="1ec80-148">Update the structure of a business document template by adding a picture</span></span>

1. <span data-ttu-id="1ec80-149">En Excel Online, en la cinta, en la pestaña **Insertar**, en el grupo **Ilustraciones**, seleccione **Imagen**.</span><span class="sxs-lookup"><span data-stu-id="1ec80-149">In Excel Online, on the ribbon, on the **Insert** tab, in the **Illustrations** group, select **Picture**.</span></span>
2. <span data-ttu-id="1ec80-150">Seleccione **Elegir archivo**, busque la imagen que desea agregar, selecciónela y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1ec80-150">Select **Choose file**, browse to the image that you want to add, select it, and then select **OK**.</span></span>
3. <span data-ttu-id="1ec80-151">Seleccione **Insertar**.</span><span class="sxs-lookup"><span data-stu-id="1ec80-151">Select **Insert**.</span></span>
4. <span data-ttu-id="1ec80-152">Mueva la nueva imagen hasta que esté en el lugar correcto.</span><span class="sxs-lookup"><span data-stu-id="1ec80-152">Move the new picture until it's in the correct place.</span></span> <span data-ttu-id="1ec80-153">De forma predeterminada, Excel nombra la imagen.</span><span class="sxs-lookup"><span data-stu-id="1ec80-153">By default, Excel names the picture.</span></span> <span data-ttu-id="1ec80-154">Por ejemplo, podría nombrar la imagen **Imagen 2**.</span><span class="sxs-lookup"><span data-stu-id="1ec80-154">For example, it might name the picture **Picture 2**.</span></span>
5. <span data-ttu-id="1ec80-155">Seleccione **Estructura de actualización** para sincronizar la estructura de la plantilla editable en Excel y Finance.</span><span class="sxs-lookup"><span data-stu-id="1ec80-155">Select **Update structure** to sync the structure of the editable template in Excel and Finance.</span></span>
6. <span data-ttu-id="1ec80-156">En el panel **Estructura de la plantilla**, expanda **Informe \> Factura \> rptHeader \> rptHeaderPart1**.</span><span class="sxs-lookup"><span data-stu-id="1ec80-156">In the **Template structure** pane, expand **Report \> Invoice \> rptHeader \> rptHeaderPart1**.</span></span>
7. <span data-ttu-id="1ec80-157">Fíjese en que la nueva imagen ya se incluye como un elemento en la estructura de la plantilla en Finance.</span><span class="sxs-lookup"><span data-stu-id="1ec80-157">Notice that the new picture is now included as an item in the template structure in Finance.</span></span>

<span data-ttu-id="1ec80-158">[![Uso del espacio de trabajo de administración de documentos empresariales para agregar una imagen a una plantilla de documento empresarial](./media/er-bdm-update-structure4.gif)](./media/er-bdm-update-structure4.gif)</span><span class="sxs-lookup"><span data-stu-id="1ec80-158">[![Using the Business document management workspace to add a picture to a business document template](./media/er-bdm-update-structure4.gif)](./media/er-bdm-update-structure4.gif)</span></span>

## <a name="related-links"></a><span data-ttu-id="1ec80-159">Vínculos relacionados</span><span class="sxs-lookup"><span data-stu-id="1ec80-159">Related links</span></span>

[<span data-ttu-id="1ec80-160">Visión general de los informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="1ec80-160">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="1ec80-161">Visión general de la gestión de documentos empresariales</span><span class="sxs-lookup"><span data-stu-id="1ec80-161">Business document management overview</span></span>](er-business-document-management.md)
