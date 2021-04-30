---
title: Reutilizar las configuraciones de ER con plantillas de Excel para generar informes en formato Word
description: Este tema describe cómo los formatos de informe que fueron diseñados para generar informes como libros de Excel pueden configurarse para generar informes como documentos de Word.
author: NickSelin
ms.date: 01/11/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ab4cd4a390782936a74977ac2aef3790aa8ac1af
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891704"
---
# <a name="reuse-er-configurations-with-excel-templates-to-generate-reports-in-word-format"></a><span data-ttu-id="28293-103">Reutilizar las configuraciones de ER con plantillas de Excel para generar informes en formato Word</span><span class="sxs-lookup"><span data-stu-id="28293-103">Reuse ER configurations with Excel templates to generate reports in Word format</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="28293-104">Para generar informes como documentos de Microsoft Word, puede [configurar](../er-design-configuration-word.md) un nuevo [formato](../general-electronic-reporting.md#FormatComponentOutbound) de [informes electrónicos (ER)](../general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="28293-104">To generate reports as Microsoft Word documents, you can [configure](../er-design-configuration-word.md) a new [Electronic reporting (ER)](../general-electronic-reporting.md) [format](../general-electronic-reporting.md#FormatComponentOutbound).</span></span> <span data-ttu-id="28293-105">También puede reutilizar un formato ER que se diseñara originalmente para generar informes como libros de Excel.</span><span class="sxs-lookup"><span data-stu-id="28293-105">Alternatively, you can reuse an ER format that was originally designed to generate reports as Excel workbooks.</span></span> <span data-ttu-id="28293-106">En este caso, debe reemplazar la plantilla de Excel con una plantilla de Word.</span><span class="sxs-lookup"><span data-stu-id="28293-106">In this case, you must replace the Excel template with a Word template.</span></span>

<span data-ttu-id="28293-107">Los siguientes procedimientos muestran cómo un usuario con el rol de administrador del sistema o el rol de desarrollador de informes electrónicos puede configurar un formato ER para generar informes como archivos de Word reutilizando un formato ER que fue diseñado para generar informes como archivos de Excel.</span><span class="sxs-lookup"><span data-stu-id="28293-107">The following procedures show how a user in either the System administrator role or the Electronic reporting developer role can configure an ER format to generate reports as Word files by reusing an ER format that was designed to generate reports as Excel files.</span></span>

<span data-ttu-id="28293-108">Estos procedimientos se pueden llevar a cabo en la empresa GBSI.</span><span class="sxs-lookup"><span data-stu-id="28293-108">These procedures can be completed in the GBSI company.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="28293-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="28293-109">Prerequisites</span></span>

<span data-ttu-id="28293-110">Para completar estos procedimientos, primero debe seguir los pasos en [Diseñar una configuración de ER para generar informes en formato OPENXML](er-design-reports-openxml-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="28293-110">To complete these procedures, you must first follow the steps in the [Design a configuration for generating reports in OPENXML format](er-design-reports-openxml-2016-11.md) task guide.</span></span>

<span data-ttu-id="28293-111">También debe descargar y guardar de forma local las plantillas siguientes para el informe de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="28293-111">You must also download and locally save the following templates for the sample report:</span></span>

- [<span data-ttu-id="28293-112">Plantilla de informe de pago (SampleVendPaymDocReport.docx)</span><span class="sxs-lookup"><span data-stu-id="28293-112">Template of Payment Report (SampleVendPaymDocReport.docx)</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)
- [<span data-ttu-id="28293-113">Plantilla enlazada de pago (SampleVendPaymDocReportBounded.docx)</span><span class="sxs-lookup"><span data-stu-id="28293-113">Bounded Template of Payment Report (SampleVendPaymDocReportBounded.docx)</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)

<span data-ttu-id="28293-114">Estos procedimientos son para una característica que se agregó en la versión 1611 (noviembre de 2016) de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="28293-114">These procedures are for a feature that was added in Dynamics 365 for Operations version 1611 (November 2016).</span></span>

## <a name="select-the-existing-er-report-configuration"></a><span data-ttu-id="28293-115">Seleccione la configuración existente del informe ER</span><span class="sxs-lookup"><span data-stu-id="28293-115">Select the existing ER report configuration</span></span>

1. <span data-ttu-id="28293-116">En Dynamics 365 Finance vaya a **Administración de la organización** \> **Espacioes de trabajo** \> **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="28293-116">In Dynamics 365 Finance, go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="28293-117">Asegúrese de que el proveedor de la configuración **Litware, Inc.** está marcado como **Activo**.</span><span class="sxs-lookup"><span data-stu-id="28293-117">Make sure that the **Litware, Inc.** configuration provider is selected as **Active**.</span></span> <span data-ttu-id="28293-118">Si no es así, siga los pasos de la guía de tareas [Crear proveedores de configuración y marcarlos como activos](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="28293-118">If it isn't, follow the steps in the [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md) task guide.</span></span>
3. <span data-ttu-id="28293-119">Seleccione **Configuraciones de informes**.</span><span class="sxs-lookup"><span data-stu-id="28293-119">Select **Reporting configurations**.</span></span> <span data-ttu-id="28293-120">Reutilizará la configuración actual de ER que se diseñó para generar la salida de informes en formato de OPENXML.</span><span class="sxs-lookup"><span data-stu-id="28293-120">You will reuse the existing ER configuration that was designed to generate the report output in OPENXML format.</span></span>
4. <span data-ttu-id="28293-121">En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de pago** y seleccione **Informe de hoja de cálculo de muestra**.</span><span class="sxs-lookup"><span data-stu-id="28293-121">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and select **Sample worksheet report**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="28293-122">La versión en borrador del formato ER seleccionado se puede editar en la ficha desplegable **Versiones**.</span><span class="sxs-lookup"><span data-stu-id="28293-122">The draft version of the selected ER format can be edited on the **Versions** FastTab.</span></span>

5. <span data-ttu-id="28293-123">Seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="28293-123">Select **Designer**.</span></span>
6. <span data-ttu-id="28293-124">En la página **Diseñador de formatos**, observe que el título del elemento de formato raíz indica que se está utilizando actualmente una plantilla de Excel.</span><span class="sxs-lookup"><span data-stu-id="28293-124">On the **Format designer** page, notice that the title of the root format element indicates that an Excel template is currently used.</span></span>

![Seleccionar la configuración existente](../media/er-design-configuration-word-2016-11-image01.gif)

## <a name="review-the-downloaded-word-template"></a><span data-ttu-id="28293-126">Revisar la plantilla de Word descargada</span><span class="sxs-lookup"><span data-stu-id="28293-126">Review the downloaded Word template</span></span>

1. <span data-ttu-id="28293-127">En la aplicación de escritorio de Word, abra el archivo de plantilla **SampleVendPaymDocReport.docx** que descargó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="28293-127">In the Word desktop application, open the **SampleVendPaymDocReport.docx** template file that you downloaded earlier.</span></span>
2. <span data-ttu-id="28293-128">Verifique que la plantilla solo contiene el diseño del documento que desea generar como ER de salida.</span><span class="sxs-lookup"><span data-stu-id="28293-128">Verify that the template contains only the layout of the document that you want to generate as ER output.</span></span>

![El diseño de la plantilla de Word en la aplicación de escritorio](../media/er-design-configuration-word-2016-11-image02.png)

## <a name="replace-the-excel-template-with-the-word-template-and-add-a-custom-xml-part"></a><span data-ttu-id="28293-130">Reemplazar la plantilla de Excel con la plantilla de Word y agregar un elemento XML personalizado</span><span class="sxs-lookup"><span data-stu-id="28293-130">Replace the Excel template with the Word template and add a custom XML part</span></span>

<span data-ttu-id="28293-131">Actualmente, el documento de Excel se utiliza como plantilla para producir un resultado en formato de OPENXML.</span><span class="sxs-lookup"><span data-stu-id="28293-131">Currently, the Excel document is used as a template to generate the output in OPENXML format.</span></span> <span data-ttu-id="28293-132">Sustituirá esta plantilla con el archivo de plantilla de Word SampleVendPaymDocReport.docx que se descargó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="28293-132">You will replace this template with the SampleVendPaymDocReport.docx Word template file that you downloaded earlier.</span></span> <span data-ttu-id="28293-133">También extenderá la plantilla de Word agregando un elemento XML personalizado.</span><span class="sxs-lookup"><span data-stu-id="28293-133">You will also extend the Word template by adding a custom XML part.</span></span>

1. <span data-ttu-id="28293-134">En Finance, en la página **Diseñador de formato**, en la pestaña **Formato**, seleccione **Archivos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="28293-134">In Finance, on the **Format designer** page, on the **Format** tab, select **Attachments**.</span></span>
2. <span data-ttu-id="28293-135">En la página **Archivos adjuntos**, seleccione **Eliminar** para eliminar la plantilla de Excel existente.</span><span class="sxs-lookup"><span data-stu-id="28293-135">On the **Attachments** page, select **Delete** to remove the existing Excel template.</span></span> <span data-ttu-id="28293-136">Seleccione **Sí** para confirmar el cambio.</span><span class="sxs-lookup"><span data-stu-id="28293-136">Select **Yes** to confirm the change.</span></span>
3. <span data-ttu-id="28293-137">Seleccione **Nuevo** \> **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="28293-137">Select **New** \> **File**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="28293-138">Debe seleccionar un tipo de documento que se haya [configurado](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) en los parámetros de ER para almacenar plantillas de formatos ER.</span><span class="sxs-lookup"><span data-stu-id="28293-138">You must select a document type that has been [configured](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) in the ER parameters to store templates of ER formats.</span></span>

4. <span data-ttu-id="28293-139">Seleccione **Examinar** y luego busque y seleccione el archivo **SampleVendPaymDocReport.docx** que descargó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="28293-139">Select **Browse**, and then browse to and select the **SampleVendPaymDocReport.docx** file that you downloaded earlier.</span></span>
5. <span data-ttu-id="28293-140">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="28293-140">Select **OK**.</span></span>
6. <span data-ttu-id="28293-141">Cierre la página **Archivos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="28293-141">Close the **Attachments** page.</span></span>
7. <span data-ttu-id="28293-142">En la página **Diseñador de formato**, en el campo **Plantilla**, introduzca o seleccione el archivo **SampleVendPaymDocReport.docx** para usar esa plantilla de Word en lugar de la plantilla de Excel que se usó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="28293-142">On the **Format designer** page, in the **Template** field, enter or select the **SampleVendPaymDocReport.docx** file to use that Word template instead of the Excel template that was previously used.</span></span>
8. <span data-ttu-id="28293-143">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="28293-143">Select **Save**.</span></span>

    <span data-ttu-id="28293-144">Además de almacenar cambios de configuración, la acción **Guardar** actualiza la plantilla de Word adjunta.</span><span class="sxs-lookup"><span data-stu-id="28293-144">In addition to storing configuration changes, the **Save** action updates the attached Word template.</span></span> <span data-ttu-id="28293-145">La estructura jerárquica del formato diseñado se agrega al documento de Word adjunto como un nuevo elemento XML personalizado con el nombre **Informe**.</span><span class="sxs-lookup"><span data-stu-id="28293-145">The hierarchical structure of the designed format is added to the attached Word document as a new custom XML part that is named **Report**.</span></span> <span data-ttu-id="28293-146">La plantilla de Word adjunta contiene el diseño del documento que se generará como salida de ER y la estructura de datos que el ER introducirá en esta plantilla en runtime.</span><span class="sxs-lookup"><span data-stu-id="28293-146">The attached Word template contains the layout of the document that will be generated as ER output and the structure of data that ER will enter in that template at runtime.</span></span>

9. <span data-ttu-id="28293-147">Observe que el título del elemento de formato raíz indica que se está utilizando actualmente una plantilla de Word.</span><span class="sxs-lookup"><span data-stu-id="28293-147">Notice that the title of the root format element indicates that a Word template is currently used.</span></span>

    ![Reemplazar la plantilla de Excel con la plantilla de Word y agregar un elemento XML personalizado](../media/er-design-configuration-word-2016-11-image03.gif)

10. <span data-ttu-id="28293-149">En la pestaña **Formato**, seleccione **Adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="28293-149">On the **Format** tab, select **Attachments**.</span></span>

<span data-ttu-id="28293-150">Ahora puede asignar los elementos del elemento XML personalizado **Informe** a los controles de contenido del documento de Word.</span><span class="sxs-lookup"><span data-stu-id="28293-150">You can now map the elements of the **Report** custom XML part to the content controls of the Word document.</span></span>

<span data-ttu-id="28293-151">Si está familiarizado con el proceso de diseñar documentos de Word como formularios que contienen [controles de contenido](/office/client-developer/word/content-controls-in-word) asignados a elementos de [elementos XML personalizados](/visualstudio/vsto/custom-xml-parts-overview?view=vs-2019), complete todos los pasos en el siguiente procedimiento para crear el documento.</span><span class="sxs-lookup"><span data-stu-id="28293-151">If you're familiar with the process of designing Word documents as forms that contain [content controls](/office/client-developer/word/content-controls-in-word) that are mapped to elements of [custom XML parts](/visualstudio/vsto/custom-xml-parts-overview?view=vs-2019), complete all steps in the next procedure to create the document.</span></span> <span data-ttu-id="28293-152">Para obtener más información, consulte [Crear formularios que los usuarios pueden rellenar o imprimir en Word](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b).</span><span class="sxs-lookup"><span data-stu-id="28293-152">For more information, see [Create forms that users complete or print in Words](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b).</span></span> <span data-ttu-id="28293-153">En caso contrario, omita el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="28293-153">Otherwise, skip the next procedure.</span></span>

## <a name="get-a-word-document-that-has-a-custom-xml-part-and-do-data-mapping"></a><a id='get-word-doc'></a><span data-ttu-id="28293-154">Obtener un documento de Word que tenga un elemento XML personalizado y realizar la asignación de datos</span><span class="sxs-lookup"><span data-stu-id="28293-154">Get a Word document that has a custom XML part and do data mapping</span></span>

1. <span data-ttu-id="28293-155">En Finance, en la página **Archivos adjuntos**, seleccione **Abrir** para descargar la plantilla seleccionada de Finance y almacenarla localmente como un documento de Word.</span><span class="sxs-lookup"><span data-stu-id="28293-155">In Finance, on the **Attachments** page, select **Open** to download the selected template from Finance and store it locally as a Word document.</span></span>
3. <span data-ttu-id="28293-156">En la aplicación de escritorio de Word, abra el documento que acaba de descargar.</span><span class="sxs-lookup"><span data-stu-id="28293-156">In the Word desktop application, open the document that you just downloaded.</span></span>
4. <span data-ttu-id="28293-157">En la pestaña **Desarrollador**, seleccione **Panel de asignación XML**.</span><span class="sxs-lookup"><span data-stu-id="28293-157">On the **Developer** tab, select **XML Mapping Pane**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="28293-158">Si la pestaña **Desarrollador** no aparece en la cinta de opciones, personalícela para agregarla.</span><span class="sxs-lookup"><span data-stu-id="28293-158">If the **Developer** tab doesn't appear on the ribbon, customize the ribbon to add it.</span></span>

5. <span data-ttu-id="28293-159">En el panel **Asignación XML**, en el campo **Elemento XML personalizado**, seleccione el elemento XML personalizado **Informe**.</span><span class="sxs-lookup"><span data-stu-id="28293-159">In the **XML Mapping** pane, in the **Custom XML Part** field, select the **Report** custom XML part.</span></span>
6. <span data-ttu-id="28293-160">Asigne los elementos del elemento XML personalizado **Informe** seleccionado y los controles de contenido del documento de Word.</span><span class="sxs-lookup"><span data-stu-id="28293-160">Map the elements of the selected **Report** custom XML part and the content controls of the Word document.</span></span>
7. <span data-ttu-id="28293-161">Guarde el documento de Word actualizado localmente como **SampleVendPaymDocReportBounded.docx**.</span><span class="sxs-lookup"><span data-stu-id="28293-161">Save the updated Word document locally as **SampleVendPaymDocReportBounded.docx**.</span></span>

## <a name="review-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a><span data-ttu-id="28293-162">Revisar la plantilla de Word donde el elemento XML personalizado se asigna a los controles de contenido</span><span class="sxs-lookup"><span data-stu-id="28293-162">Review the Word template where the custom XML part is mapped to content controls</span></span>

1. <span data-ttu-id="28293-163">En la aplicación de escritorio de Word, abra el archivo de plantilla **SampleVendPaymDocReportBounded.docx**.</span><span class="sxs-lookup"><span data-stu-id="28293-163">In the Word desktop application, open the **SampleVendPaymDocReportBounded.docx** template file.</span></span>
2. <span data-ttu-id="28293-164">Verifique que la plantilla contiene el diseño del documento que desea generar como ER de salida.</span><span class="sxs-lookup"><span data-stu-id="28293-164">Verify that the template contains the layout of the document that you want to generate as ER output.</span></span> <span data-ttu-id="28293-165">Los controles de contenido que se utilizan como marcadores de posición para los datos que ER introducirá en esta plantilla en runtime se basan en las asignaciones que se configuran entre los elementos del elemento XML personalizado **Informe** y los controles de contenido del documento de Word.</span><span class="sxs-lookup"><span data-stu-id="28293-165">The content controls that are used as placeholders for data that ER will enter in this template at runtime are based on the mappings that are configured between elements of the **Report** custom XML part and the content controls of the Word document.</span></span>

![Vista previa de la plantilla de Word en la aplicación de escritorio](../media/er-design-configuration-word-2016-11-image04.png)

## <a name="upload-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a><span data-ttu-id="28293-167">Cargar la plantilla de Word donde el elemento XML personalizado se asigna a los controles de contenido</span><span class="sxs-lookup"><span data-stu-id="28293-167">Upload the Word template where the custom XML part is mapped to content controls</span></span>

1. <span data-ttu-id="28293-168">En Finance, en la página **Archivos adjuntos**, seleccione **Eliminar** para eliminar la plantilla de Word que no tiene asignaciones entre los elementos del elemento XML personalizado **Informe** y los controles de contenido.</span><span class="sxs-lookup"><span data-stu-id="28293-168">In Finance, on the **Attachments** page, select **Delete** to remove the Word template that has no mappings between elements of the **Report** custom XML part and content controls.</span></span> <span data-ttu-id="28293-169">Seleccione **Sí** para confirmar el cambio.</span><span class="sxs-lookup"><span data-stu-id="28293-169">Select **Yes** to confirm the change.</span></span>
2. <span data-ttu-id="28293-170">Seleccione **Nuevo** \> **Archivo** para agregar un nuevo archivo de plantilla que contiene asignaciones entre elementos del elemento XML personalizado **Informe** y los controles de contenido.</span><span class="sxs-lookup"><span data-stu-id="28293-170">Select **New** \> **File** to add a new template file that contains mappings between elements of the **Report** custom XML part and content controls.</span></span>

    > [!NOTE]
    > <span data-ttu-id="28293-171">Debe seleccionar un tipo de documento que se haya [configurado](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) en los parámetros de ER para almacenar plantillas de formatos ER.</span><span class="sxs-lookup"><span data-stu-id="28293-171">You must select a document type that has been [configured](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) in the ER parameters to store templates of ER formats.</span></span>

3. <span data-ttu-id="28293-172">Seleccione **Examinar** y luego busque y seleccione el archivo **SampleVendPaymDocReportBounded.docx** que descargó o preparó completando el procedimiento en la sección [Obtener un Word que tenga un elemento XML personalizado y realizar la asignación de datos](#get-word-doc).</span><span class="sxs-lookup"><span data-stu-id="28293-172">Select **Browse**, and then browse to and select the **SampleVendPaymDocReportBounded.docx** file that you downloaded or prepared by completing the procedure in the [Get a Word that has a custom XML part to do data mapping](#get-word-doc) section.</span></span>
4. <span data-ttu-id="28293-173">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="28293-173">Select **OK**.</span></span>
5. <span data-ttu-id="28293-174">Cierre la página **Archivos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="28293-174">Close the **Attachments** page.</span></span>
6. <span data-ttu-id="28293-175">En la página **Diseñador de formato**, en el campo **Plantilla**, seleccione el documento que acaba de descargar.</span><span class="sxs-lookup"><span data-stu-id="28293-175">On the **Format designer** page, in the **Template** field, select the document that you just downloaded.</span></span>
7. <span data-ttu-id="28293-176">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="28293-176">Select **Save**.</span></span>
8. <span data-ttu-id="28293-177">Cierre la página **Diseñador de formato**.</span><span class="sxs-lookup"><span data-stu-id="28293-177">Close the **Format designer** page.</span></span>

## <a name="mark-the-configured-format-as-runnable"></a><span data-ttu-id="28293-178">Marcar el formato configurado como ejecutable</span><span class="sxs-lookup"><span data-stu-id="28293-178">Mark the configured format as runnable</span></span>

<span data-ttu-id="28293-179">Para ejecutar la versión de borrador del formato editable, debe hacerlo [ejecutable](../er-quick-start2-customize-report.md#MarkFormatRunnable).</span><span class="sxs-lookup"><span data-stu-id="28293-179">To run the draft version of the editable format, you must make it [runnable](../er-quick-start2-customize-report.md#MarkFormatRunnable).</span></span>

1. <span data-ttu-id="28293-180">En Finance, en la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Configuración avanzada**, seleccione **Parámetros de usuario**.</span><span class="sxs-lookup"><span data-stu-id="28293-180">In Finance, on the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
2. <span data-ttu-id="28293-181">En el cuadro de diálogo **Parámetros de usuario**, establezca la opción **Ejecutar configuración** en **Sí** y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="28293-181">In the **User parameters** dialog box, set the **Run settings** option to **Yes**, and then select **OK**.</span></span>
3. <span data-ttu-id="28293-182">Seleccione **Editar** para hacer que la página actual sea editable, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="28293-182">Select **Edit** to make the current page editable, as required.</span></span>
4. <span data-ttu-id="28293-183">Para la configuración **Informe de hoja de cálculo de muestra** seleccionada actualmente, establezca la opción **Ejecutar borrador** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="28293-183">For the currently selected **Sample worksheet report** configuration, set the **Run Draft** option to **Yes**.</span></span>
5. <span data-ttu-id="28293-184">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="28293-184">Select **Save**.</span></span>

## <a name="run-the-format-to-create-output-in-word-format"></a><span data-ttu-id="28293-185">Ejecutar el formato para crear una salida en formato Word</span><span class="sxs-lookup"><span data-stu-id="28293-185">Run the format to create output in Word format</span></span>

1. <span data-ttu-id="28293-186">En Finance, vaya a **Proveedores** \> **Pagos** \> **Diario de pagos**.</span><span class="sxs-lookup"><span data-stu-id="28293-186">In Finance, go to **Accounts payable** \> **Payments** \> **Payment journal**.</span></span>
2. <span data-ttu-id="28293-187">En un diario de pagos que introdujera anteriormente, seleccione **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="28293-187">In a payment journal that you entered earlier, select **Lines**.</span></span>
3. <span data-ttu-id="28293-188">En la página **Pagos a proveedores**, seleccione todas las filas de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="28293-188">On the **Vendor payments** page, select all rows in the grid.</span></span>
4. <span data-ttu-id="28293-189">Seleccione **Estado de pago** \> **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="28293-189">Select **Payment status** \> **None**.</span></span>

    ![Pagos para procesar en la página Pagos a proveedores](../media/er-design-configuration-word-2016-11-image05.png)

5. <span data-ttu-id="28293-191">En el panel de acciones, seleccione **Generar pagos**.</span><span class="sxs-lookup"><span data-stu-id="28293-191">On the Action Pane, select **Generate payments**.</span></span>
6. <span data-ttu-id="28293-192">En el cuadro de diálogo que aparece, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="28293-192">In the dialog box that appears, follow these steps:</span></span>

    1. <span data-ttu-id="28293-193">En el campo **Método de pago**, seleccione **Electrónico**.</span><span class="sxs-lookup"><span data-stu-id="28293-193">In the **Method of payment** field, select **Electronic**.</span></span>
    2. <span data-ttu-id="28293-194">En el campo **Cuenta bancaria**, seleccione **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="28293-194">In the **Bank account** field, select **GBSI OPER**.</span></span>
    3. <span data-ttu-id="28293-195">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="28293-195">Select **OK**.</span></span>

7. <span data-ttu-id="28293-196">En el cuadro de diálogo **Parámetros de informes electrónicos**, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="28293-196">In the **Electronic report parameters** dialog box, select **OK**.</span></span>
8. <span data-ttu-id="28293-197">La salida creada se presenta en formato de Word y contiene los detalles de los pagos procesados.</span><span class="sxs-lookup"><span data-stu-id="28293-197">The generated output is presented in Word format and contains the details of the processed payments.</span></span> <span data-ttu-id="28293-198">Analice la salida generada.</span><span class="sxs-lookup"><span data-stu-id="28293-198">Analyze the generated output.</span></span>

    ![Salida generada en formato Word](../media/er-design-configuration-word-2016-11-image06.png)

## <a name="additional-resources"></a><span data-ttu-id="28293-200">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="28293-200">Additional resources</span></span>

- [<span data-ttu-id="28293-201">Diseñar una nueva configuración de ER para generar informes en formato Word</span><span class="sxs-lookup"><span data-stu-id="28293-201">Design a new ER configuration to generate reports in Word format</span></span>](../er-design-configuration-word.md)
- [<span data-ttu-id="28293-202">Insertar imágenes y formas en los documentos generados con ER</span><span class="sxs-lookup"><span data-stu-id="28293-202">Embed images and shapes in documents that you generate by using ER</span></span>](../electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]