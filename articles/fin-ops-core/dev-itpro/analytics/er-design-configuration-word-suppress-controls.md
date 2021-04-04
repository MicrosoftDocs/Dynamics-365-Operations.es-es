---
title: Suprimir los controles de contenido de Word en los informes generados
description: Este tema explica cómo configurar un formato de informes electrónicos (ER) para generar informes como archivos de Microsoft Word donde se suprimen los controles de contenido.
author: NickSelin
manager: AnnBe
ms.date: 02/11/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: Version 10.0.6
ms.openlocfilehash: 81ad25514154dd8982aa4f849f0b2bfeb85270f7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562127"
---
# <a name="suppress-word-content-controls-in-generated-reports"></a><span data-ttu-id="99809-103">Suprimir los controles de contenido de Word en los informes generados</span><span class="sxs-lookup"><span data-stu-id="99809-103">Suppress Word content controls in generated reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="99809-104">Para generar informes como documentos de Microsoft Word, debe diseñar una plantilla para los informes como documento de Word.</span><span class="sxs-lookup"><span data-stu-id="99809-104">To generate reports as Microsoft Word documents, you must design a template for the reports as a Word document.</span></span> <span data-ttu-id="99809-105">Esta plantilla debe contener controles de contenido de Word como marcadores de posición para los datos que se completarán en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="99809-105">This template must contain Word content controls as placeholders for data that will be filled in at runtime.</span></span> <span data-ttu-id="99809-106">Para utilizar un documento de Word creado como plantilla para sus informes, puede [configurar](er-design-configuration-word.md) una nueva [solución](er-quick-start1-new-solution.md) de [Informes electrónicos (ER)](general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="99809-106">To use the Word document that is created as a template for your reports, you can [configure](er-design-configuration-word.md) a new [Electronic reporting (ER)](general-electronic-reporting.md) [solution](er-quick-start1-new-solution.md).</span></span> <span data-ttu-id="99809-107">La solución debe incluir una [configuración](general-electronic-reporting.md#Configuration) de ER que contenga un componente de [formato](general-electronic-reporting.md#FormatComponentOutbound) de ER.</span><span class="sxs-lookup"><span data-stu-id="99809-107">The solution must include an ER [configuration](general-electronic-reporting.md#Configuration) that contains an ER [format](general-electronic-reporting.md#FormatComponentOutbound) component.</span></span> <span data-ttu-id="99809-108">Este formato de ER debe configurarse para utilizar la plantilla diseñada para la generación de informes.</span><span class="sxs-lookup"><span data-stu-id="99809-108">This ER format must be configured to use the designed template for report generation.</span></span>

<span data-ttu-id="99809-109">En la versión 10.0.6 y posteriores de Dynamics 365 Finance, puede configurar fórmulas en su formato ER para suprimir algunos controles de contenido de Word en los documentos generados.</span><span class="sxs-lookup"><span data-stu-id="99809-109">In version 10.0.6 and later of Dynamics 365 Finance, you can configure formulas in your ER format to suppress some Word content controls in generated documents.</span></span>

<span data-ttu-id="99809-110">Los siguientes pasos explican cómo un usuario asignado a la función de administrador del sistema o consultor funcional de informes electrónicos puede configurar un formato ER que genera informes como archivos de Word y suprime algunos de los controles de contenido en los informes generados que se han configurado mediante una plantilla de Word.</span><span class="sxs-lookup"><span data-stu-id="99809-110">The following steps explain how a user who is assigned to the System administrator or Electronic reporting functional consultant role can configure an ER format that generates reports as Word files and suppresses some of the content controls in the generated reports that have been configured by using a Word template.</span></span>

<span data-ttu-id="99809-111">Estos pasos se pueden llevar a cabo en la empresa GBSI.</span><span class="sxs-lookup"><span data-stu-id="99809-111">These steps can be completed in the GBSI company.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="99809-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="99809-112">Prerequisites</span></span>

<span data-ttu-id="99809-113">Para completar estos pasos, primero debe completar los pasos de las siguientes guías de tarea:</span><span class="sxs-lookup"><span data-stu-id="99809-113">To complete these steps, you must first complete the steps in the following task guides:</span></span>

- [<span data-ttu-id="99809-114">Diseñar una configuración para generar informes en formato OPENXML</span><span class="sxs-lookup"><span data-stu-id="99809-114">Design a configuration for generating reports in OPENXML format</span></span>](./tasks/er-design-reports-openxml-2016-11.md)
- [<span data-ttu-id="99809-115">Reutilizar configuraciones de ER con plantillas de Excel para generar informes en formato Word</span><span class="sxs-lookup"><span data-stu-id="99809-115">Re-use ER configurations with Excel templates to generate reports in Word format</span></span>](./tasks/er-design-configuration-word-2016-11.md)

<span data-ttu-id="99809-116">Cuando complete los pasos de estas guías de tareas, se preparan los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="99809-116">When you complete the steps of these task guides, the following items are prepared:</span></span>

- <span data-ttu-id="99809-117">Un formato ER **Informe de hoja de trabajo de muestra** que está configurado para generar un documento en formato Word</span><span class="sxs-lookup"><span data-stu-id="99809-117">A **Sample worksheet report** ER format that is configured to generate a document in Word format</span></span>
- <span data-ttu-id="99809-118">Una versión en [borrador](general-electronic-reporting.md#component-versioning) del formato ER **Informe de hoja de trabajo de muestra** marcada como **Ejecutable**</span><span class="sxs-lookup"><span data-stu-id="99809-118">A [draft](general-electronic-reporting.md#component-versioning) version of the **Sample worksheet report** ER format that is marked as **Runnable**</span></span>
- <span data-ttu-id="99809-119">Un método de pago **Electrónico** que está configurado para utilizar el formato ER **Informe de hoja de trabajo de muestra** para el procesamiento de pagos de proveedores</span><span class="sxs-lookup"><span data-stu-id="99809-119">An **Electronic** method of payments that is configured to use the **Sample worksheet report** ER format for vendor payment processing</span></span>

<span data-ttu-id="99809-120">También debe descargar y guardar la siguiente plantilla siguientes para el informe de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="99809-120">You must also download and save the following template for the sample report:</span></span>

- [<span data-ttu-id="99809-121">Plantilla enlazada 2 de informes de pago (SampleVendPaymDocReportBounded2.docx)</span><span class="sxs-lookup"><span data-stu-id="99809-121">Bounded Template 2 of Payment Report (SampleVendPaymDocReportBounded2.docx)</span></span>](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded2.docx)

## <a name="review-the-downloaded-word-template"></a><a id="tag-control"></a><span data-ttu-id="99809-122">Revisar la plantilla de Word descargada</span><span class="sxs-lookup"><span data-stu-id="99809-122">Review the downloaded Word template</span></span>

1. <span data-ttu-id="99809-123">En la aplicación de escritorio de Word, abra el archivo de plantilla **SampleVendPaymDocReportBounded2.docx** que descargó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="99809-123">In the Word desktop application, open the **SampleVendPaymDocReportBounded2.docx** template file that you downloaded earlier.</span></span>
2. <span data-ttu-id="99809-124">Verifique que el archivo de plantilla contenga una sección de resumen que muestre los importes de pago totales para cada código de divisa que se haya cumplido en los pagos procesados.</span><span class="sxs-lookup"><span data-stu-id="99809-124">Verify that the template file contains a summary section that shows the total payment amounts for every currency code that has been met in the processed payments.</span></span>

    - <span data-ttu-id="99809-125">La sección de resumen reside en una tabla separada del documento de Word.</span><span class="sxs-lookup"><span data-stu-id="99809-125">The summary section resides in a separate table of the Word document.</span></span>
    - <span data-ttu-id="99809-126">La primera fila de esta tabla contiene los encabezados de las columnas de la tabla como encabezado de sección.</span><span class="sxs-lookup"><span data-stu-id="99809-126">The first row of this table holds the table columns headings as the section header.</span></span>
    - <span data-ttu-id="99809-127">La segunda fila de esta tabla contiene el control de contenido repetido como detalles de la sección.</span><span class="sxs-lookup"><span data-stu-id="99809-127">The second row of this table holds the repeating content control as the section details.</span></span>
    - <span data-ttu-id="99809-128">Este control de contenido se asigna al campo **SummaryLines** de la parte XML personalizada del **Informe** .</span><span class="sxs-lookup"><span data-stu-id="99809-128">This content control is mapped to the **SummaryLines** field of the **Report** custom XML part.</span></span>
    - <span data-ttu-id="99809-129">Según esta asignación, el control de contenido se asocia con el elemento **SummaryLines** del formato ER editable.</span><span class="sxs-lookup"><span data-stu-id="99809-129">Based on this mapping, the content control is associated with the **SummaryLines** element of the editable ER format.</span></span>

    > [!NOTE]
    > <span data-ttu-id="99809-130">El control de contenido repetido está etiquetado con la clave **SummaryLines** que coincide con el campo de la parte XML personalizada a la que se ha asignado.</span><span class="sxs-lookup"><span data-stu-id="99809-130">The repeating content control is tagged by the **SummaryLines** key that matches the field of the custom XML part that it has been mapped to.</span></span>

    ![Diseño de plantilla de Word](./media/er-design-configuration-word-suppress-controls-image1.gif)

## <a name="select-the-existing-er-report-configuration"></a><span data-ttu-id="99809-132">Seleccione la configuración existente del informe ER</span><span class="sxs-lookup"><span data-stu-id="99809-132">Select the existing ER report configuration</span></span>

<span data-ttu-id="99809-133">Para los siguientes pasos, reutilizará la configuración de ER existente que configuró cuando completó los pasos en las guías de tareas mencionadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="99809-133">For the following steps, you will reuse the existing ER configuration that you configured when you completed the steps in the previously mentioned task guides.</span></span>

1. <span data-ttu-id="99809-134">Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="99809-134">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="99809-135">Seleccione **Configuraciones de informes**.</span><span class="sxs-lookup"><span data-stu-id="99809-135">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="99809-136">En la página **Configuraciones**, en el árbol de configuraciones, expanda **Modelo de pago** y seleccione **Informe de hoja de cálculo de muestra**.</span><span class="sxs-lookup"><span data-stu-id="99809-136">On the **Configurations** page, in the configuration tree, expand **Payment model**, and select **Sample worksheet report**.</span></span>
4. <span data-ttu-id="99809-137">Seleccione **Diseñador** para editar la versión preliminar del formato ER seleccionado.</span><span class="sxs-lookup"><span data-stu-id="99809-137">Select **Designer** to edit the draft version of the selected ER format.</span></span>

## <a name="replace-the-current-template-with-the-new-template"></a><span data-ttu-id="99809-138">Sustituya la plantilla actual por la nueva plantilla</span><span class="sxs-lookup"><span data-stu-id="99809-138">Replace the current template with the new template</span></span>

<span data-ttu-id="99809-139">Actualmente, el archivo SampleVendPaymDocReportBounded.docx se utiliza como plantilla para producir la salida en formato de Word.</span><span class="sxs-lookup"><span data-stu-id="99809-139">Currently, the SampleVendPaymDocReportBounded.docx file is used as a template to generate the output in Word format.</span></span> <span data-ttu-id="99809-140">En los pasos siguientes, sustituirá esta plantilla de Word con la nueva plantilla de Word SampleVendPaymDocReportBounded2.docx que descargó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="99809-140">In the following steps, you will replace this Word template with the new Word template, SampleVendPaymDocReportBounded2.docx, that you downloaded earlier.</span></span>

1. <span data-ttu-id="99809-141">En la página **Diseñador de formato**, seleccione **Archivos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="99809-141">On the **Format designer** page, select **Attachments**.</span></span>
2. <span data-ttu-id="99809-142">En la página **Archivos adjuntos**, seleccione **Eliminar** para eliminar la plantilla existente.</span><span class="sxs-lookup"><span data-stu-id="99809-142">On the **Attachments** page, select **Delete** to remove the existing template.</span></span>
3. <span data-ttu-id="99809-143">Seleccione **Sí** para confirmar el borrado.</span><span class="sxs-lookup"><span data-stu-id="99809-143">Select **Yes** to confirm the deletion.</span></span>
4. <span data-ttu-id="99809-144">Seleccione **Nuevo** \> **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="99809-144">Select **New** \> **File**.</span></span>
5. <span data-ttu-id="99809-145">Seleccione **Examinar** y luego busque y seleccione el archivo **SSampleVendPaymDocReportBounded2.docx** que descargó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="99809-145">Select **Browse**, and browse to and select the **SampleVendPaymDocReportBounded2.docx** file that you downloaded earlier.</span></span>
6. <span data-ttu-id="99809-146">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="99809-146">Select **OK**.</span></span>
7. <span data-ttu-id="99809-147">Cierre la página **Archivos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="99809-147">Close the **Attachments** page.</span></span>
8. <span data-ttu-id="99809-148">En la página **Diseñador de formatos**, en el campo **Plantilla**, introduzca o seleccione el archivo **SampleVendPaymDocReportBounded2.docx**.</span><span class="sxs-lookup"><span data-stu-id="99809-148">On the **Format designer** page, in the **Template** field, enter or select the **SampleVendPaymDocReportBounded2.docx** file.</span></span>

## <a name="run-the-format-to-create-word-output"></a><span data-ttu-id="99809-149">Ejecutar el formato para crear una salida en Word</span><span class="sxs-lookup"><span data-stu-id="99809-149">Run the format to create Word output</span></span>

1. <span data-ttu-id="99809-150">Vaya a **Proveedores** \> **Pagos** \> **Diario de pagos**.</span><span class="sxs-lookup"><span data-stu-id="99809-150">Go to **Accounts payable** \> **Payments** \> **Payment journal**.</span></span>
2. <span data-ttu-id="99809-151">En la página **Pagos a proveedores**, en la pestaña **Lista**, seleccione todos los pagos.</span><span class="sxs-lookup"><span data-stu-id="99809-151">On the **Vendor payments** page, on the **List** tab, select all the payments.</span></span>
3. <span data-ttu-id="99809-152">Seleccione **Estado de pago** \> **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="99809-152">Select **Payment status** \> **None**.</span></span>
4. <span data-ttu-id="99809-153">Seleccione **Generar pagos**.</span><span class="sxs-lookup"><span data-stu-id="99809-153">Select **Generate payments**.</span></span>
5. <span data-ttu-id="99809-154">En el campo **Método de pago**, seleccione **Electrónico**.</span><span class="sxs-lookup"><span data-stu-id="99809-154">In the **Method of payment** field, select **Electronic**.</span></span>
6. <span data-ttu-id="99809-155">En el campo **Cuenta bancaria**, seleccione **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="99809-155">In the **Bank account** field, select **GBSI OPER**.</span></span>
7. <span data-ttu-id="99809-156">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="99809-156">Select **OK**.</span></span>
8. <span data-ttu-id="99809-157">En el cuadro de diálogo **Parámetros de informes electrónicos**, seleccione **Aceptar** y analice la salida generada.</span><span class="sxs-lookup"><span data-stu-id="99809-157">In the **Electronic report parameters** dialog box, select **OK**, and analyze the generated output.</span></span>

    ![Pagos para procesar en la página Pagos a proveedores](./media/er-design-configuration-word-suppress-controls-image2.gif)

    <span data-ttu-id="99809-159">La salida se presenta en formato Word y contiene la sección de resumen.</span><span class="sxs-lookup"><span data-stu-id="99809-159">The output is presented in Word format and contains the summary section.</span></span>

## <a name="configure-the-editable-format-to-suppress-the-summary-section"></a><a id="configure-to-suppress-control"></a><span data-ttu-id="99809-160">Configure el formato editable para suprimir la sección de resumen</span><span class="sxs-lookup"><span data-stu-id="99809-160">Configure the editable format to suppress the summary section</span></span>

<span data-ttu-id="99809-161">Si desea suprimir la sección de resumen en un documento generado, según la solicitud de un usuario que ejecuta este formato ER, debe modificar el formato ER editable.</span><span class="sxs-lookup"><span data-stu-id="99809-161">If you want to suppress the summary section in a generated document, based on the request of a user who runs this ER format, you must modify the editable ER format.</span></span>

1. <span data-ttu-id="99809-162">Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos** y abra la versión de borrador el formato ER para editarla.</span><span class="sxs-lookup"><span data-stu-id="99809-162">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**, and open the draft version of the ER format for editing.</span></span>
2. <span data-ttu-id="99809-163">Seleccione **Configuraciones de informes**.</span><span class="sxs-lookup"><span data-stu-id="99809-163">Select **Reporting configurations**.</span></span> 
3. <span data-ttu-id="99809-164">En la página **Configuraciones**, en el árbol de configuraciones, expanda **Modelo de pago** \> **Informe de hoja de cálculo de muestra**.</span><span class="sxs-lookup"><span data-stu-id="99809-164">On the **Configurations** page, in the configuration tree, expand **Payment model** \> **Sample worksheet report**.</span></span>
4. <span data-ttu-id="99809-165">Seleccione **Diseñador**.</span><span class="sxs-lookup"><span data-stu-id="99809-165">Select **Designer**.</span></span>
5. <span data-ttu-id="99809-166">En la página **Diseñador de formatos**, expanda **Word** y seleccione **SummaryLines**.</span><span class="sxs-lookup"><span data-stu-id="99809-166">On the **Format designer** page, expand **Word**, and select **SummaryLines**.</span></span>
6. <span data-ttu-id="99809-167">En la pestaña **Cartografía**, agregue una nueva fuente de datos para preguntar al usuario, en tiempo de ejecución, si la sección de resumen debe suprimirse:</span><span class="sxs-lookup"><span data-stu-id="99809-167">On the **Mapping** tab, add a new data source to ask the user, at runtime, whether the summary section should be suppressed:</span></span>

    1. <span data-ttu-id="99809-168">Seleccione **Agregar raíz**.</span><span class="sxs-lookup"><span data-stu-id="99809-168">Select **Add root**.</span></span>
    2. <span data-ttu-id="99809-169">En el cuadro de diálogo **Agregar origen de datos**, seleccione **Parámetro de entrada general\de usuario** para abrir el cuadro de diálogo **Propiedades del origen de datos del 'Parámetro de entrada del usuario'**.</span><span class="sxs-lookup"><span data-stu-id="99809-169">In the **Add data source** dialog box, select **General\User input parameter** to open the **'User input parameter' data source properties** dialog box.</span></span>
    3. <span data-ttu-id="99809-170">En el campo **Nombre**, especifique **uipSuppress**.</span><span class="sxs-lookup"><span data-stu-id="99809-170">In the **Name** field, enter **uipSuppress**.</span></span>
    4. <span data-ttu-id="99809-171">En el campo **Etiqueta**, introduzca **Suprimir la sección de resumen**.</span><span class="sxs-lookup"><span data-stu-id="99809-171">In the **Label** field, enter **Suppress summary section**.</span></span>
    5. <span data-ttu-id="99809-172">En el campo **Nombre del tipo de datos de operaciones**, seleccione o introduzca **NoYes**.</span><span class="sxs-lookup"><span data-stu-id="99809-172">In the **Operations data type name** field, select or enter **NoYes**.</span></span>
    6. <span data-ttu-id="99809-173">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="99809-173">Select **OK**.</span></span>

7. <span data-ttu-id="99809-174">Agregue un nuevo origen de datos de tipo **NoYes** de enumeración de aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="99809-174">Add a new data source of the **NoYes** application enumeration type:</span></span>

    1. <span data-ttu-id="99809-175">Seleccione **Agregar raíz**.</span><span class="sxs-lookup"><span data-stu-id="99809-175">Select **Add root**.</span></span>
    2. <span data-ttu-id="99809-176">En el cuadro de diálogo **Agregar origen de datos**, seleccione **Dynamics 365 for Operations\Enumeración** para abrir el cuadro de diálogo **Propiedades del origen de datos 'Enumeración'**.</span><span class="sxs-lookup"><span data-stu-id="99809-176">In the **Add data source** dialog box, select **Dynamics 365 for Operations\Enumeration** to open the **'Enumeration' data source properties** dialog box.</span></span>
    3. <span data-ttu-id="99809-177">En el campo **Nombre**, especifique **enumNoYes**.</span><span class="sxs-lookup"><span data-stu-id="99809-177">In the **Name** field, enter **enumNoYes**.</span></span>
    4. <span data-ttu-id="99809-178">En el campo **Etiqueta**, introduzca **Opciones de supresión**.</span><span class="sxs-lookup"><span data-stu-id="99809-178">In the **Label** field, enter **Suppress options**.</span></span>
    5. <span data-ttu-id="99809-179">En el campo **Nombre del tipo de datos de operaciones**, seleccione o introduzca **NoYes**.</span><span class="sxs-lookup"><span data-stu-id="99809-179">In the **Operations data type name** field, select or enter **NoYes**.</span></span>
    6. <span data-ttu-id="99809-180">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="99809-180">Select **OK**.</span></span>

8. <span data-ttu-id="99809-181">Para el elemento de formato seleccionado **SummaryLines**, configure la fórmula para especificar cuándo se debe suprimir el control de contenido de Word asociado con el elemento de formato seleccionado:</span><span class="sxs-lookup"><span data-stu-id="99809-181">For the selected **SummaryLines** format element, configure the formula to specify when the Word content control that is associated with the selected format element should be suppressed:</span></span>

    1. <span data-ttu-id="99809-182">En la pestaña **Cartografía**, en la sección **Eliminado**, seleccione **Editar** para abrir la página **[Diseñador de fórmulas](general-electronic-reporting-formula-designer.md)**.</span><span class="sxs-lookup"><span data-stu-id="99809-182">On the **Mapping** tab, in the **Removed** section, select **Edit** to open the **[Formula designer](general-electronic-reporting-formula-designer.md)** page.</span></span>
    2. <span data-ttu-id="99809-183">En el campo **Fórmula**, introduzca la fórmula `uipSuppress = enumNoYes.Yes`.</span><span class="sxs-lookup"><span data-stu-id="99809-183">In the **Formula** field, enter the formula `uipSuppress = enumNoYes.Yes`.</span></span>
    3. <span data-ttu-id="99809-184">Seleccione **Guardar** y cierre la página **Diseñador de fórmula**.</span><span class="sxs-lookup"><span data-stu-id="99809-184">Select **Save**, and close the **Formula designer** page.</span></span>

        > [!NOTE]
        > <span data-ttu-id="99809-185">Esta fórmula se aplicará a un documento generado **después de ejecutarse todos los demás elementos de formato**.</span><span class="sxs-lookup"><span data-stu-id="99809-185">This formula will be applied to a generated document **after all other format elements are run**.</span></span> <span data-ttu-id="99809-186">Para aplicar esta fórmula, un control de contenido de Word etiquetado como elemento de formato para el que está configurada la fórmula (**SummaryLines** en este caso) se encuentra en un documento generado.</span><span class="sxs-lookup"><span data-stu-id="99809-186">To apply this formula, a Word content control that is tagged as a format element that the formula is configured for (**SummaryLines** in this case) is found in a generated document.</span></span> <span data-ttu-id="99809-187">Luego, ese control de contenido se elimina por completo, junto con la fila de la tabla de Word que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="99809-187">That content control is then completely removed, together with the row in the Word table that holds it.</span></span> <span data-ttu-id="99809-188">La fila de detalles de la sección de resumen se elimina del documento generado.</span><span class="sxs-lookup"><span data-stu-id="99809-188">The details row of the summary section is removed from the generated document.</span></span>
        >
        > <span data-ttu-id="99809-189">En tiempo de diseño, puede configurar la fórmula **Eliminado** para un elemento de formato, aunque ningún control de contenido en la plantilla de Word que está utilizando tenga una etiqueta que coincide con el nombre de un elemento de formato para el que la propiedad **Remoto** está configurada.</span><span class="sxs-lookup"><span data-stu-id="99809-189">At design time, you might configure the **Removed** formula for a format element, even though no content control in the Word template that you're using has a tag that matches the name of a format element that the **Removed** property is configured for.</span></span> <span data-ttu-id="99809-190">Cuando valida el formato en el momento del diseño, recibe una [advertencia](er-components-inspections.md#i14) sobre esta incoherencia.</span><span class="sxs-lookup"><span data-stu-id="99809-190">When you validate the format at design time, you receive a [warning](er-components-inspections.md#i14) about this inconsistency.</span></span>
        >
        > <span data-ttu-id="99809-191">En tiempo de ejecución, se lanza una excepción si ningún control de contenido en la plantilla de Word que está usando tiene una etiqueta que coincide con el nombre de un elemento de formato para el que está configurada la propiedad **Eliminado**.</span><span class="sxs-lookup"><span data-stu-id="99809-191">At runtime, an exception is thrown if no content control in the Word template that you're using has a tag that matches the name of a format element that the **Removed** property is configured for.</span></span>

    4. <span data-ttu-id="99809-192">En la pestaña **Asignación**, en la sección **Eliminado**, establezca la opción **Con primario** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="99809-192">On the **Mapping** tab, in the **Removed** section, set the **With parent** option to **Yes**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="99809-193">Debe configurar esta opción en **Sí** para eliminar toda la tabla de Word como objeto principal de la fila que contiene los detalles de la sección de resumen.</span><span class="sxs-lookup"><span data-stu-id="99809-193">You must set this option to **Yes** to remove the whole Word table as the parent object of the row that holds the summary section details.</span></span> <span data-ttu-id="99809-194">Si configura esta opción en **No**, la fila del encabezado de la sección permanece en el documento generado.</span><span class="sxs-lookup"><span data-stu-id="99809-194">If you set this option to **No**, the section header row remains in the generated document.</span></span>

9. <span data-ttu-id="99809-195">Seleccione **Guardar** para guardar los cambios del formato editable.</span><span class="sxs-lookup"><span data-stu-id="99809-195">Select **Save** to save your changes to the editable format.</span></span>

    ![Salida generada en formato Word](./media/er-design-configuration-word-suppress-controls-image3.gif)

## <a name="run-the-modified-format-to-create-word-output"></a><span data-ttu-id="99809-197">Ejecutar el formato modificado para crear una salida en Word</span><span class="sxs-lookup"><span data-stu-id="99809-197">Run the modified format to create Word output</span></span>

1. <span data-ttu-id="99809-198">Vaya a **Proveedores** \> **Pagos** \> **Diario de pagos**.</span><span class="sxs-lookup"><span data-stu-id="99809-198">Go to **Accounts payable** \> **Payments** \> **Payment journal**.</span></span>
2. <span data-ttu-id="99809-199">Seleccione el diario de pagos que creó y luego seleccione **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="99809-199">Select the payment journal that you created, and then select **Lines**.</span></span>
3. <span data-ttu-id="99809-200">En la página **Pagos a proveedores**, seleccione todas las filas y luego seleccione **Estado de pago** \> **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="99809-200">On the **Vendor payments** page, select all the rows, and then select **Payment status** \> **None**.</span></span>
4. <span data-ttu-id="99809-201">Seleccione **Generar pagos**.</span><span class="sxs-lookup"><span data-stu-id="99809-201">Select **Generate payments**.</span></span>
5. <span data-ttu-id="99809-202">En el campo **Método de pago**, seleccione **Electrónico**.</span><span class="sxs-lookup"><span data-stu-id="99809-202">In the **Method of payment** field, select **Electronic**.</span></span>
6. <span data-ttu-id="99809-203">En el campo **Cuenta bancaria**, seleccione **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="99809-203">In the **Bank account** field, select **GBSI OPER**.</span></span>
7. <span data-ttu-id="99809-204">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="99809-204">Select **OK**.</span></span>
8. <span data-ttu-id="99809-205">En el cuadro de diálogo **Parámetros de informes electrónicos**, en el campo **Suprimir la sección de resumen**, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="99809-205">In the **Electronic report parameters** dialog box, in the **Suppress summary section** field, select **Yes**.</span></span>
9. <span data-ttu-id="99809-206">Seleccione **Aceptar** y analice la salida generada.</span><span class="sxs-lookup"><span data-stu-id="99809-206">Select **OK**, and analyze the generated output.</span></span>

    ![Salida generada en formato Word](./media/er-design-configuration-word-suppress-controls-image4.gif)

    <span data-ttu-id="99809-208">Observe que la salida no contiene la sección de resumen, porque se ha suprimido.</span><span class="sxs-lookup"><span data-stu-id="99809-208">Notice that the output doesn't contain the summary section, because it has been suppressed.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="99809-209">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="99809-209">Additional resources</span></span>

- [<span data-ttu-id="99809-210">Diseñar una configuración para generar informes en formato OPENXML</span><span class="sxs-lookup"><span data-stu-id="99809-210">Design a configuration for generating reports in OPENXML format</span></span>](./tasks/er-design-reports-openxml-2016-11.md)
- [<span data-ttu-id="99809-211">Diseñar una nueva configuración de ER para generar informes en formato Word</span><span class="sxs-lookup"><span data-stu-id="99809-211">Design a new ER configuration to generate reports in Word format</span></span>](er-design-configuration-word.md)
- [<span data-ttu-id="99809-212">Reutilizar configuraciones de ER con plantillas de Excel para generar informes en formato Word</span><span class="sxs-lookup"><span data-stu-id="99809-212">Re-use ER configurations with Excel templates to generate reports in Word format</span></span>](./tasks/er-design-configuration-word-2016-11.md)
- [<span data-ttu-id="99809-213">Inspeccionar el componente ER configurado para evitar problemas de runtime</span><span class="sxs-lookup"><span data-stu-id="99809-213">Inspect the configured ER component to prevent runtime issues</span></span>](er-components-inspections.md#i14)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]