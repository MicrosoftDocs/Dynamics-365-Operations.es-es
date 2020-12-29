---
title: Agregar nuevos campos a una plantilla de documento empresarial en Microsoft Excel
description: En este tema se proporciona información acerca de cómo agregar nuevos campos a una plantilla de documento empresarial en Microsoft Excel mediante la característica de gestión de documentos empresariales.
author: NickSelin
manager: AnnBe
ms.date: 11/15/2019
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
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: fcfbcb021b192cef75d59b0db1796e994f3dc27d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681385"
---
# <a name="add-new-fields-to-a-business-document-template-in-microsoft-excel"></a><span data-ttu-id="71ae5-103">Agregar nuevos campos a una plantilla de documento empresarial en Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="71ae5-103">Add new fields to a business document template in Microsoft Excel</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="71ae5-104">Puede agregar nuevos campos a una plantilla que se usa para generar documentos empresariales en formato Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="71ae5-104">You can add new fields to a template that is used to generate business documents in Microsoft Excel format.</span></span> <span data-ttu-id="71ae5-105">Estos campos se pueden agregar como marcadores de posición que se utilizan para rellenar documentos generados con la información necesaria de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="71ae5-105">These fields can be added as placeholders that are used to fill generated documents with required information from the application.</span></span> <span data-ttu-id="71ae5-106">Para cada campo que agregue, también puede especificar un enlace a los orígenes de datos, a fin de especificar qué datos de la aplicación se introducirán en el campo cuando la plantilla se use para generar documentos empresariales.</span><span class="sxs-lookup"><span data-stu-id="71ae5-106">For every field that you add, you can also specify a binding to the data sources, to specify what application data will be entered in the field when the template is used to generate business documents.</span></span>

<span data-ttu-id="71ae5-107">Para obtener más información acerca de esta característica, complete el ejemplo de este tema.</span><span class="sxs-lookup"><span data-stu-id="71ae5-107">To learn more about this feature, complete the example in this topic.</span></span> <span data-ttu-id="71ae5-108">Este ejemplo muestra cómo actualizar una plantilla para rellenar los campos en formularios de facturas de servicios que se generan.</span><span class="sxs-lookup"><span data-stu-id="71ae5-108">This example shows how to update a template to fill in the fields in free text invoice forms that are generated.</span></span>

## <a name="configure-business-document-management-to-edit-templates"></a><span data-ttu-id="71ae5-109">Configurar la gestión de documentos empresariales para editar plantillas</span><span class="sxs-lookup"><span data-stu-id="71ae5-109">Configure Business document management to edit templates</span></span>

<span data-ttu-id="71ae5-110">Puesto que la gestión de documentos empresariales (BDM) se basa en el marco [Visión general de los informes electrónicos (ER)](general-electronic-reporting.md), debe configurar los parámetros necesarios de ER y BDM antes de poder empezar a trabajar con BDM.</span><span class="sxs-lookup"><span data-stu-id="71ae5-110">Because Business document management (BDM) is built on top of the [Electronic reporting (ER) overview](general-electronic-reporting.md) framework, you must configure the required ER and BDM parameters before you can start to work with BDM.</span></span>

1.  <span data-ttu-id="71ae5-111">Inicie sesión en la instancia de Microsoft Dynamics 365 Finance como administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="71ae5-111">Sign in to the instance of Microsoft Dynamics 365 Finance as the system administrator.</span></span>
2.  <span data-ttu-id="71ae5-112">Complete los siguientes pasos del ejemplo en el tema [Visión general de la gestión de documentos empresariales](er-business-document-management.md):</span><span class="sxs-lookup"><span data-stu-id="71ae5-112">Complete the following steps of the example in the [Business document management overview](er-business-document-management.md) topic:</span></span>

    1.  <span data-ttu-id="71ae5-113">Configure los parámetros de ER.</span><span class="sxs-lookup"><span data-stu-id="71ae5-113">Configure ER parameters.</span></span>
    2.  <span data-ttu-id="71ae5-114">Active BDM.</span><span class="sxs-lookup"><span data-stu-id="71ae5-114">Turn on BDM.</span></span>

<span data-ttu-id="71ae5-115">Ahora puede empezar a usar BDM para editar plantillas de documentos empresariales.</span><span class="sxs-lookup"><span data-stu-id="71ae5-115">You can now start to use BDM to edit business document templates.</span></span>

## <a name="import-er-solutions-that-contain-a-template"></a><span data-ttu-id="71ae5-116">Importar soluciones de ER que contienen una plantilla</span><span class="sxs-lookup"><span data-stu-id="71ae5-116">Import ER solutions that contain a template</span></span>

<span data-ttu-id="71ae5-117">El ejemplo de este procedimiento emplea la solución de ER publicada oficialmente.</span><span class="sxs-lookup"><span data-stu-id="71ae5-117">The example in this procedure uses the officially published ER solution.</span></span> <span data-ttu-id="71ae5-118">Debe importar las configuraciones de ER de esta solución en su instancia actual de Finance.</span><span class="sxs-lookup"><span data-stu-id="71ae5-118">You must import the ER configurations of this solution into your current instance of Finance.</span></span>

<span data-ttu-id="71ae5-119">La configuración del formato de ER **Factura de servicios (Excel)** de esta solución contiene la plantilla de documento empresarial en formato Excel que se puede editar mediante BDM.</span><span class="sxs-lookup"><span data-stu-id="71ae5-119">The **Free text invoice (Excel)** ER format configuration of this solution contains the business document template in Excel format that can be edited by using BDM.</span></span> <span data-ttu-id="71ae5-120">Importe la última versión de esta configuración del formato de ER desde Microsoft Dynamics Lifecycle Service (LCS).</span><span class="sxs-lookup"><span data-stu-id="71ae5-120">Import the latest version of this ER format configuration from Microsoft Dynamics Lifecycle Service (LCS).</span></span> <span data-ttu-id="71ae5-121">El modelo de datos de ER correspondiente y las configuraciones de asignación de modelo de ER se importarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="71ae5-121">The corresponding ER data model and ER model mapping configurations will be imported automatically.</span></span>

<span data-ttu-id="71ae5-122">Para obtener más información acerca de cómo importar configuraciones de ER, consulte [Gestionar el ciclo de vida de la configuración de ER](general-electronic-reporting-manage-configuration-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="71ae5-122">For more information about how to import ER configurations, see [Manage the ER configuration lifecycle](general-electronic-reporting-manage-configuration-lifecycle.md).</span></span>

![Página Biblioteca de activos compartidos de LCS](./media/BDM-AddFldExcel-LCS.png)

### <a name="edit-the-er-solution-template"></a><span data-ttu-id="71ae5-124">Editar la plantilla de la solución de ER</span><span class="sxs-lookup"><span data-stu-id="71ae5-124">Edit the ER solution template</span></span>

1.  <span data-ttu-id="71ae5-125">Inicie sesión como usuario que tiene acceso al espacio de trabajo de la **gestión de documentos empresariales**.</span><span class="sxs-lookup"><span data-stu-id="71ae5-125">Sign in as a user who has access to the **Business document management** workspace.</span></span>
2.  <span data-ttu-id="71ae5-126">Abra el espacio de trabajo de la **gestión de documentos empresariales**.</span><span class="sxs-lookup"><span data-stu-id="71ae5-126">Open the **Business document management** workspace.</span></span>

    ![Espacio de trabajo de la gestión de documentos empresariales](./media/BDM-AddFldExcel-Workspace.png)

3.  <span data-ttu-id="71ae5-128">En la cuadrícula, seleccione la plantilla **Factura de servicios (Excel)**.</span><span class="sxs-lookup"><span data-stu-id="71ae5-128">In the grid, select the **Free text invoice (Excel)** template.</span></span>
4.  <span data-ttu-id="71ae5-129">En el panel derecho, seleccione **Nueva plantilla** para crear una nueva plantilla basada en la plantilla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="71ae5-129">In the right pane, select **New template** to create a new template that is based on the selected template.</span></span>
5.  <span data-ttu-id="71ae5-130">En el campo **Título**, introduzca **Factura de servicios (Excel) Contoso** como título de la nueva plantilla.</span><span class="sxs-lookup"><span data-stu-id="71ae5-130">In the **Title** field, enter **Free text invoice (Excel) Contoso** as the title of the new template.</span></span>
6.  <span data-ttu-id="71ae5-131">Seleccione **Aceptar** para confirmar el inicio del proceso de edición.</span><span class="sxs-lookup"><span data-stu-id="71ae5-131">Select **OK** to confirm the start of the editing process.</span></span>

<span data-ttu-id="71ae5-132">Aparece la página del editor de plantillas de BDM.</span><span class="sxs-lookup"><span data-stu-id="71ae5-132">The BDM template editor page appears.</span></span> <span data-ttu-id="71ae5-133">Puede usar Microsoft 365 para editar en línea la plantilla seleccionada en el control incrustado.</span><span class="sxs-lookup"><span data-stu-id="71ae5-133">You can use Microsoft 365 to edit the selected template online in the embedded control.</span></span>

![Página del editor de plantillas de BDM](./media/BDM-AddFldExcel-EditableTemplate.png)

### <a name="add-the-label-for-a-new-field-to-the-template"></a><span data-ttu-id="71ae5-135">Agregar la etiqueta para un nuevo campo a la plantilla</span><span class="sxs-lookup"><span data-stu-id="71ae5-135">Add the label for a new field to the template</span></span>

1.  <span data-ttu-id="71ae5-136">En la página del editor de plantillas de BDM, en la cinta de opciones de Excel, en la pestaña **Ver**, seleccione las casillas **Encabezados y líneas de cuadrícula** para la plantilla de Excel editable.</span><span class="sxs-lookup"><span data-stu-id="71ae5-136">On the BDM template editor page, on the Excel ribbon, on the **View** tab, select the **Headings and Gridlines** check boxes for the editable Excel template.</span></span>

    ![Casillas de encabezados y líneas de cuadrícula seleccionadas](./media/BDM-AddFldExcel-EditableTemplate2.png)

2.  <span data-ttu-id="71ae5-138">Seleccione las celdas **E8:F8**.</span><span class="sxs-lookup"><span data-stu-id="71ae5-138">Select cells **E8:F8**.</span></span>
3.  <span data-ttu-id="71ae5-139">En la cinta de opciones de Excel, en la pestaña **Inicio**, seleccione **Combinar y centrar** para combinar las celdas seleccionadas en una nueva celda **E8:F8** combinada.</span><span class="sxs-lookup"><span data-stu-id="71ae5-139">On the Excel ribbon, on the **Home** tab, select **Merge & Center** to merge the selected cells into a new merged **E8:F8** cell.</span></span>
4.  <span data-ttu-id="71ae5-140">En la celda combinada **E8:F8**, introduzca la **URL**.</span><span class="sxs-lookup"><span data-stu-id="71ae5-140">In the merged cell **E8:F8**, enter **URL**.</span></span>
5.  <span data-ttu-id="71ae5-141">Seleccione la celda combinada **E7:F7**, seleccione **Copiar formato** y luego seleccione la celda combinada **E8:F8** para aplicarle formato de la misma manera que la celda combinada **E7:F7**.</span><span class="sxs-lookup"><span data-stu-id="71ae5-141">Select merged cell **E7:F7**, select **Format painter**, and then select merged cell **E8:F8** to format it in the same way as merged cell **E7:F7**.</span></span>

    ![Nuevo etiqueta de campo agregada a la plantilla](./media/BDM-AddFldExcel-EditableTemplate3.png)

### <a name="format-the-template-to-reserve-space-for-a-new-field"></a><span data-ttu-id="71ae5-143">Aplicar formato a la plantilla para reservar espacio para un nuevo campo</span><span class="sxs-lookup"><span data-stu-id="71ae5-143">Format the template to reserve space for a new field</span></span>

1.  <span data-ttu-id="71ae5-144">En la página del editor de plantillas de BDM, seleccione la celda combinada **G8:H8**.</span><span class="sxs-lookup"><span data-stu-id="71ae5-144">On the BDM template editor page, select merged cell **G8:H8**.</span></span>
2.  <span data-ttu-id="71ae5-145">En la cinta de opciones de Excel, en la pestaña **Inicio**, seleccione **Combinar y centrar** para combinar las celdas seleccionadas en una nueva celda **G8:H8** combinada.</span><span class="sxs-lookup"><span data-stu-id="71ae5-145">On the Excel ribbon, on the **Home** tab, select **Merge & Center** to merge the selected cells into a new merged **G8:H8** cell.</span></span>
3.  <span data-ttu-id="71ae5-146">Seleccione la celda combinada **G7:H7**, seleccione **Copiar formato** y luego seleccione la celda combinada **G8:H8** para aplicarle formato de la misma manera que la celda combinada **G7:H7**.</span><span class="sxs-lookup"><span data-stu-id="71ae5-146">Select merged cell **G7:H7**, select **Format painter**, and then select merged cell **G8:H8** to format it in the same way as merged cell **G7:H7**.</span></span>

    ![Espacio reservado para el nuevo campo](./media/BDM-AddFldExcel-EditableTemplate4.png)

4.  <span data-ttu-id="71ae5-148">En el campo **Nombre**, seleccione **CompanyInfo**.</span><span class="sxs-lookup"><span data-stu-id="71ae5-148">In the **Name** box field, select **CompanyInfo**.</span></span>

    <span data-ttu-id="71ae5-149">El intervalo **CompanyInfo** de la plantilla de Excel actual contiene todos los campos que se utilizan para rellenar el encabezado de un informe generado con los detalles de la empresa actual como parte vendedora.</span><span class="sxs-lookup"><span data-stu-id="71ae5-149">The **CompanyInfo** range of the current Excel template holds all the fields that are used to fill the header of a generated report with the details of the current company as a seller party.</span></span>

    ![Intervalo CompanyInfo seleccionado](./media/BDM-AddFldExcel-SelectCompanyInfoRange.png)

### <a name="add-a-new-field-to-the-template"></a><span data-ttu-id="71ae5-151">Agregar un nuevo campo a la plantilla</span><span class="sxs-lookup"><span data-stu-id="71ae5-151">Add a new field to the template</span></span>

1.  <span data-ttu-id="71ae5-152">En la página **Editor de plantilla de BDM**, en el panel de acciones, seleccione **Mostrar formato**.</span><span class="sxs-lookup"><span data-stu-id="71ae5-152">On the **BDM template editor** page, on the Action Pane, select **Show format**.</span></span>
2.  <span data-ttu-id="71ae5-153">En el panel **Estructura de la plantilla**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="71ae5-153">In the **Template structure** pane, select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="71ae5-154">Debe ajustar la sección de la plantilla que desea utilizar como un nuevo campo.</span><span class="sxs-lookup"><span data-stu-id="71ae5-154">You must adjust the section of the template that you want to use as a new field.</span></span> <span data-ttu-id="71ae5-155">Ya hizo este ajuste al aplicar formato a la celda combinada **G8:H8**.</span><span class="sxs-lookup"><span data-stu-id="71ae5-155">You already made this adjustment by formatting merged cell **G8:H8**.</span></span>

    ![Agregando un nuevo campo a la plantilla](./media/BDM-AddFldExcel-AddCell.png)

3.  <span data-ttu-id="71ae5-157">Seleccione **Excel\Celda** para agregar un nuevo campo como celda en la plantilla.</span><span class="sxs-lookup"><span data-stu-id="71ae5-157">Select **Excel\Cell** to add a new field as a cell in the template.</span></span>

    <span data-ttu-id="71ae5-158">Puede seleccionar **Excel\Intervalo** si desea agregar un nuevo intervalo a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="71ae5-158">You can select **Excel\Range** if you want to add a new range to the template.</span></span> <span data-ttu-id="71ae5-159">El intervalo que se introduce puede contener múltiples celdas.</span><span class="sxs-lookup"><span data-stu-id="71ae5-159">The range that is entered can contain multiple cells.</span></span> <span data-ttu-id="71ae5-160">Puede agregar estas celdas más adelante.</span><span class="sxs-lookup"><span data-stu-id="71ae5-160">You can add these cells later.</span></span>
    
    <span data-ttu-id="71ae5-161">Tenga en cuenta que el componente de la plantilla **CompanyInfo** se selecciona automáticamente en el panel **Estructura de la plantilla**, ya que es el componente principal más adecuado de la estructura de la plantilla actual para el campo que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="71ae5-161">Notice that the **CompanyInfo** template component, is automatically selected in the **Template structure** pane, because it's the most suitable parent component in the current template structure for the field that you're adding.</span></span>
    
4.  <span data-ttu-id="71ae5-162">En el campo **Intervalo de Excel**, introduzca **CompanyURL_Value**.</span><span class="sxs-lookup"><span data-stu-id="71ae5-162">In the **Excel range** field, enter **CompanyURL_Value**.</span></span>
5.  <span data-ttu-id="71ae5-163">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="71ae5-163">Select **OK**.</span></span>

    ![Campo CompanyURL_Value agregado a la estructura de la plantilla](./media/BDM-AddFldExcel-EditableTemplate5.png)

6.  <span data-ttu-id="71ae5-165">En el panel **Estructura de la plantilla**, seleccione los puntos suspensivos (...) y, a continuación, seleccione **Mostrar enlaces**.</span><span class="sxs-lookup"><span data-stu-id="71ae5-165">In the **Template structure** pane, select the ellipsis button (...), and then select **Show bindings**.</span></span>

    ![Mostrar enlaces seleccionados](./media/BDM-AddFldExcel-ShowBindings.png)

    <span data-ttu-id="71ae5-167">El panel **Estructura de la plantilla** ahora muestra los orígenes de datos disponibles en el formato de ER subyacente.</span><span class="sxs-lookup"><span data-stu-id="71ae5-167">The **Template structure** pane now shows the data sources that are available in the underlying ER format.</span></span>

7.  <span data-ttu-id="71ae5-168">Seleccione **CompanyInfo_Value** como el campo que tiene previsto enlazar a un origen de datos del formato de ER subyacente.</span><span class="sxs-lookup"><span data-stu-id="71ae5-168">Select **CompanyInfo_Value** as the field that you plan to bind to a data source of the underlying ER format.</span></span>
8.  <span data-ttu-id="71ae5-169">En la sección **Orígenes de datos** del panel **Estructura de la plantilla**, expanda **Modelo \> InvoiceBase \> CompanyInfo**.</span><span class="sxs-lookup"><span data-stu-id="71ae5-169">In the **Data sources** section of the **Template structure** pane, expand **Model \> InvoiceBase \> CompanyInfo**.</span></span>
9.  <span data-ttu-id="71ae5-170">En **CompanyInfo**, seleccione el elemento **WebsiteURI**.</span><span class="sxs-lookup"><span data-stu-id="71ae5-170">Under **CompanyInfo**, select the **WebsiteURI** item.</span></span>

    ![Elemento WebsiteURI seleccionado](./media/BDM-AddFldExcel-BindURL.png)

10. <span data-ttu-id="71ae5-172">Seleccione **Enlazar**.</span><span class="sxs-lookup"><span data-stu-id="71ae5-172">Select **Bind**.</span></span>
11. <span data-ttu-id="71ae5-173">En el panel **Estructura de la plantilla**, seleccione **Guardar** y luego cierre la página del editor de la plantilla de BDM.</span><span class="sxs-lookup"><span data-stu-id="71ae5-173">In the **Template structure** pane, select **Save**, and then close the BDM template editor page.</span></span>

<span data-ttu-id="71ae5-174">En el espacio de trabajo **Gestión de documentos empresariales**, la pestaña **Plantilla** en el panel derecho muestra la plantilla actualizada.</span><span class="sxs-lookup"><span data-stu-id="71ae5-174">In the **Business document management** workspace, the **Template** tab in the right pane shows the updated template.</span></span> <span data-ttu-id="71ae5-175">En la cuadrícula, tenga en cuenta que el campo **Estado** para la plantilla editada se ha cambiado a **Borrador** y el campo **Revisión** dejará de estar en blanco.</span><span class="sxs-lookup"><span data-stu-id="71ae5-175">In the grid, notice that the **Status** field for the edited template has been changed to **Draft**, and the **Revision** field is no longer blank.</span></span> <span data-ttu-id="71ae5-176">Estos cambios indican que se ha iniciado el proceso de edición de esta plantilla.</span><span class="sxs-lookup"><span data-stu-id="71ae5-176">These changes indicate that the process of editing this template has been started.</span></span>

![Plantilla editada en el espacio de trabajo de Gestión de documentos empresariales](./media/BDM-AddFldExcel-Workspace2.png)

## <a name="review-company-settings"></a><span data-ttu-id="71ae5-178">Revisar configuración de empresa</span><span class="sxs-lookup"><span data-stu-id="71ae5-178">Review company settings</span></span>

1.  <span data-ttu-id="71ae5-179">Vaya a **Administración de la organización \> Organizaciones \> Entidades jurídicas**.</span><span class="sxs-lookup"><span data-stu-id="71ae5-179">Go to **Organization administration \> Organizations \> Legal entities**.</span></span>
2.  <span data-ttu-id="71ae5-180">En la ficha desplegable **Información de contacto**, compruebe que está introducida la dirección URL de la empresa.</span><span class="sxs-lookup"><span data-stu-id="71ae5-180">On the **Contact information** FastTab, verify that the company URL is entered.</span></span>

![Dirección URL de la empresa introducida en la página de Entidades jurídicas](./media/BDM-AddFldExcel-CompanyInfo.png)

## <a name="generate-business-documents-to-test-the-updated-template"></a><span data-ttu-id="71ae5-182">Generar documentos empresariales para probar la plantilla actualizada</span><span class="sxs-lookup"><span data-stu-id="71ae5-182">Generate business documents to test the updated template</span></span>

1.  <span data-ttu-id="71ae5-183">En la aplicación, cambie la empresa a **USMF** y vaya a **Clientes \> Facturas \> Todas las facturas de servicios**.</span><span class="sxs-lookup"><span data-stu-id="71ae5-183">In the application, change the company to **USMF**, and go to **Accounts receivable \> Invoices \> All free text invoices**.</span></span>
2.  <span data-ttu-id="71ae5-184">Seleccione la factura **FTI-00000002** y, a continuación, seleccione **Gestión de impresión**.</span><span class="sxs-lookup"><span data-stu-id="71ae5-184">Select invoice **FTI-00000002**, and then select **Print management**.</span></span>
3.  <span data-ttu-id="71ae5-185">En el panel izquierdo, expanda **Módulo - Clientes \> Documentos \> Factura de servicios**.</span><span class="sxs-lookup"><span data-stu-id="71ae5-185">In the left pane, expand **Module - accounts receivable \> Documents \> Free text invoice**.</span></span>
4.  <span data-ttu-id="71ae5-186">En **Factura de servicios**, seleccione el nivel **Documento original** para especificar el ámbito de las facturas para procesar.</span><span class="sxs-lookup"><span data-stu-id="71ae5-186">Under **Free text invoice**, select the **Original document** level to specify the scope of invoices for processing.</span></span>
5.  <span data-ttu-id="71ae5-187">En el panel derecho, en el campo **Formato del informe**, seleccione la plantilla **Factura de servicios (Excel) Contoso** para el nivel del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="71ae5-187">In the right pane, in the **Report format** field, select the **Free text invoice (Excel) Contoso** template for the specified document level.</span></span>

    ![Plantilla Factura de servicio (Excel) Contoso seleccionada](./media/BDM-AddFldExcel-PrintMngtSetting.png)

6.  <span data-ttu-id="71ae5-189">Presione **Esc** para cerrar la página actual.</span><span class="sxs-lookup"><span data-stu-id="71ae5-189">Press **Esc** to close the current page.</span></span>
7.  <span data-ttu-id="71ae5-190">Seleccionar **Impresión \> Seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="71ae5-190">Select **Print \> Selected**.</span></span>
8.  <span data-ttu-id="71ae5-191">Descargue el documento generado y ábralo en Excel.</span><span class="sxs-lookup"><span data-stu-id="71ae5-191">Download the generated document, and open it in Excel.</span></span>

    ![Factura de servicios en Excel](./media/BDM-AddFldExcel-PreviewReport.png)

<span data-ttu-id="71ae5-193">La plantilla modificada se usa para generar el informe de facturas de servicios para el artículo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="71ae5-193">The modified template is used to generate the free text invoice report for the selected item.</span></span> <span data-ttu-id="71ae5-194">Para analizar cómo este informe se ve afectado por los cambios que hace en la plantilla, ejecute el informe en una sesión de la aplicación inmediatamente después de cambiar la plantilla en otra sesión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="71ae5-194">To analyze how this report is affected by changes that you make to the template, run the report in one application session immediately after you change the template in another application session.</span></span>

## <a name="related-links"></a><span data-ttu-id="71ae5-195">Vínculos relacionados</span><span class="sxs-lookup"><span data-stu-id="71ae5-195">Related links</span></span>

[<span data-ttu-id="71ae5-196">Visión general de los informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="71ae5-196">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="71ae5-197">Visión general de la gestión de documentos empresariales</span><span class="sxs-lookup"><span data-stu-id="71ae5-197">Business document management overview</span></span>](er-business-document-management.md)

[<span data-ttu-id="71ae5-198">Diseñar una configuración para generar informes en formato OPENXML</span><span class="sxs-lookup"><span data-stu-id="71ae5-198">Design a configuration for generating reports in OPENXML format</span></span>](tasks/er-design-reports-openxml-2016-11.md)
