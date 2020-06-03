---
title: Diseñar una configuración para generar documentos en formato Excel
description: Este tema proporciona información sobre cómo diseñar un formato de informe electrónico (ER) para completar una plantilla de Excel y luego generar resultados en forma de documentos en formato Excel.
author: NickSelin
manager: AnnBe
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e889b08f10c5d0c95fed7c9e422340706bdd154a
ms.sourcegitcommit: 67ce81c57194afb26a04ae4c0b7509e0efa32afc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "3375822"
---
# <a name="design-a-configuration-for-generating-documents-in-excel-format"></a><span data-ttu-id="9562a-103">Diseñar una configuración para generar documentos en formato Excel</span><span class="sxs-lookup"><span data-stu-id="9562a-103">Design a configuration for generating documents in Excel format</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="9562a-104">Puede diseñar una configuración de formato de [Informe electrónico (ER)](general-electronic-reporting.md) con un [componente de formato](general-electronic-reporting.md#FormatComponentOutbound) ER que puede configurar para generar un documento resultante en un formato de libro de trabajo de Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="9562a-104">You can design an [Electronic reporting (ER)](general-electronic-reporting.md) format configuration that has an ER [format component](general-electronic-reporting.md#FormatComponentOutbound) that you can configure to generate an outbound document in a Microsoft Excel workbook format.</span></span> <span data-ttu-id="9562a-105">Se deben usar componentes de formato ER específicos para este propósito.</span><span class="sxs-lookup"><span data-stu-id="9562a-105">Specific ER format components must be used for this purpose.</span></span>

<span data-ttu-id="9562a-106">Para obtener más información sobre esta función, siga los pasos del tema [Diseñar una configuración para generar informes en formato OPENXML](tasks/er-design-reports-openxml-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="9562a-106">To learn more about this feature, follow the steps in the topic, [Design a configuration for generating reports in OPENXML format](tasks/er-design-reports-openxml-2016-11.md).</span></span>

## <a name="add-a-new-er-format"></a><span data-ttu-id="9562a-107">Agregar un nuevo formato ER</span><span class="sxs-lookup"><span data-stu-id="9562a-107">Add a new ER format</span></span>

<span data-ttu-id="9562a-108">Cuando agrega una nueva configuración de formato ER para generar un documento resultante en un formato de libro de Excel, debe seleccionar el valor **Sobresalir** para el atributo del formato **Tipo de formato** o dejar el atributo **Tipo de formato** en blanco.</span><span class="sxs-lookup"><span data-stu-id="9562a-108">When you add a new ER format configuration to generate an outbound document in an Excel workbook format, you must either select the **Excel** value for the **Format type** attribute of the format or leave the **Format type** attribute blank.</span></span>

- <span data-ttu-id="9562a-109">Si selecciona **Excel**, puede configurar el formato para generar un documento resultante solo en formato Excel.</span><span class="sxs-lookup"><span data-stu-id="9562a-109">If you select **Excel**, you can configure the format to generate an outbound document only in Excel format.</span></span>
- <span data-ttu-id="9562a-110">Si deja el atributo en blanco, puede configurar el formato para generar un documento saliente en cualquier formato que sea compatible con el marco ER.</span><span class="sxs-lookup"><span data-stu-id="9562a-110">If you leave the attribute blank, you can configure the format to generate an outbound document in any format that is supported by the ER framework.</span></span>

<span data-ttu-id="9562a-111">Para configurar el componente de formato ER de la configuración, seleccione **Diseñador** en el panel Acciones y abra el componente de formato ER para editarlo en el diseñador de operaciones ER.</span><span class="sxs-lookup"><span data-stu-id="9562a-111">To configure the ER format component of the configuration, select **Designer** on the Action Pane, and open the ER format component for editing in the ER Operation designer.</span></span>

![Página Configuraciones](./media/er-excel-format-add-format.png)

## <a name="excel-file-component"></a><span data-ttu-id="9562a-113">Componente de archivo de Excel</span><span class="sxs-lookup"><span data-stu-id="9562a-113">Excel file component</span></span>

### <a name="manual-entry"></a><span data-ttu-id="9562a-114">Entrada manual</span><span class="sxs-lookup"><span data-stu-id="9562a-114">Manual entry</span></span>

<span data-ttu-id="9562a-115">Debe agregar un componente **Archivo\\Excel** al formato ER configurado para generar un documento resultante en formato Excel.</span><span class="sxs-lookup"><span data-stu-id="9562a-115">You must add an **Excel\\File** component to the configured ER format to generate an outbound document in Excel format.</span></span>

![Componente Excel\archivo](./media/er-excel-format-add-file-component.png)

<span data-ttu-id="9562a-117">Para especificar el diseño del documento resultante, adjunte un libro de Excel que tenga la extensión .xlsx al componente **Archivo\\Excel** como plantilla para documentos resultantes.</span><span class="sxs-lookup"><span data-stu-id="9562a-117">To specify the layout of the outbound document, attach an Excel workbook that has the .xlsx extension to the **Excel\\File** component as the template for outbound documents.</span></span>

> [!NOTE]
> <span data-ttu-id="9562a-118">Cuando adjunte una plantilla manualmente, debe usar un [tipo de documento](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) que se haya configurado para ese fin en los [parámetros ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).</span><span class="sxs-lookup"><span data-stu-id="9562a-118">When you manually attach a template, you must use a [document type](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) that has been configured for that purpose in the [ER parameters](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).</span></span>

![Adición de un archivo adjunto al componente Excel\archivo](./media/er-excel-format-add-file-component2.png)

<span data-ttu-id="9562a-120">Para especificar cómo se rellenará la plantilla adjunta cuando ejecute el formato ER configurado, debe agregar componentes **Hoja**, **Rango** y **Celda** al componente **Archivo\\Excel**.</span><span class="sxs-lookup"><span data-stu-id="9562a-120">To specify how the attached template will be filled in when you run the configured ER format, you must add nested **Sheet**, **Range**, and **Cell** components to the **Excel\\File** component.</span></span> <span data-ttu-id="9562a-121">Cada componente anidado debe estar asociado con un elemento con nombre de Excel.</span><span class="sxs-lookup"><span data-stu-id="9562a-121">Each nested component must be associated with an Excel named item.</span></span>

### <a name="template-import"></a><span data-ttu-id="9562a-122">Importar plantilla</span><span class="sxs-lookup"><span data-stu-id="9562a-122">Template import</span></span>

<span data-ttu-id="9562a-123">Puede elegir **Importar desde Excel** en la pestaña **Importar** del panel Acciones para importar una nueva plantilla en un formato ER en blanco.</span><span class="sxs-lookup"><span data-stu-id="9562a-123">You can select **Import from Excel** on the **Import** tab of the Action Pane to import a new template into a blank ER format.</span></span> <span data-ttu-id="9562a-124">En este ejemplo, se creará automáticamente un componente **Archivo\\Excel** y se le adjuntará la plantilla importada.</span><span class="sxs-lookup"><span data-stu-id="9562a-124">In this example, an **Excel\\File** component will be created automatically, and the imported template will be attached to it.</span></span> <span data-ttu-id="9562a-125">Todos los componentes de ER necesarios también se crearán automáticamente, en función de la lista de elementos con nombre de Excel que se descubran.</span><span class="sxs-lookup"><span data-stu-id="9562a-125">All required ER components will also be created automatically, based on the list of Excel named items that are discovered.</span></span>

![Selección de Importar desde Excel](./media/er-excel-format-import-template.png)

> [!NOTE]
> <span data-ttu-id="9562a-127">Si quiere crear el elemento opcional **Hoja** en el formato ER editable, establezca la opción **Crear elemento de formato de hoja de Excel** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="9562a-127">If you want to create the optional **Sheet** element in the editable ER format, set the **Create Excel Sheet format element** option to **Yes**.</span></span>

## <a name="sheet-component"></a><span data-ttu-id="9562a-128">Componente de hoja</span><span class="sxs-lookup"><span data-stu-id="9562a-128">Sheet component</span></span>

<span data-ttu-id="9562a-129">El componente **Hoja** indica una hoja de trabajo del libro de Excel adjunto que debe completarse.</span><span class="sxs-lookup"><span data-stu-id="9562a-129">The **Sheet** component indicates a worksheet of the attached Excel workbook that must be filled in.</span></span> <span data-ttu-id="9562a-130">El nombre de la hoja de trabajo de una plantilla de Excel se define en la propiedad **Hoja** de este componente.</span><span class="sxs-lookup"><span data-stu-id="9562a-130">The name of the worksheet in an Excel template is defined in the **Sheet** property of this component.</span></span>

> [!NOTE]
> <span data-ttu-id="9562a-131">Este componente es opcional para los libros de Excel que contienen una sola hoja de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9562a-131">This component is optional for Excel workbooks that contain a single worksheet.</span></span>

<span data-ttu-id="9562a-132">En la pestaña **Asignación** del diseñador de operación ER, puede configurar la propiedad **Habilitado** de un componente **Hoja** para especificar si el componente debe colocarse en un documento generado:</span><span class="sxs-lookup"><span data-stu-id="9562a-132">On the **Mapping** tab of the ER Operation designer, you can configure the **Enabled** property for a **Sheet** component to specify whether the component must be put in a generated document:</span></span>

- <span data-ttu-id="9562a-133">Si una expresión de la propiedad **Habilitado** se configura para devolver **Verdadero** en tiempo de ejecución, o si no hay ninguna expresión configurada, la hoja de trabajo apropiada se colocará en el documento generado.</span><span class="sxs-lookup"><span data-stu-id="9562a-133">If an expression of the **Enabled** property is configured to return **True** at runtime, or if no expression is configured at all, the appropriate worksheet will be put in the generated document.</span></span>
- <span data-ttu-id="9562a-134">Si una expresión de la propiedad **Habilitado** está configurada para devolver **Falso** en tiempo de ejecución, el documento generado no contendrá una hoja de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9562a-134">If an expression of the **Enabled** property is configured to return **False** at runtime, the generated document won't contain a worksheet.</span></span>

![Ejemplo de un componente de hoja](./media/er-excel-format-sheet-component.png)

## <a name="range-component"></a><span data-ttu-id="9562a-136">Componente Rango</span><span class="sxs-lookup"><span data-stu-id="9562a-136">Range component</span></span>

<span data-ttu-id="9562a-137">El componente **Rango** indica un rango de Excel que debe controlarse mediante este componente ER.</span><span class="sxs-lookup"><span data-stu-id="9562a-137">The **Range** component indicates an Excel range that must be controlled by this ER component.</span></span> <span data-ttu-id="9562a-138">El nombre del rango se define en la propiedad **Rango de Excel** de este componente.</span><span class="sxs-lookup"><span data-stu-id="9562a-138">The name of the range is defined in the **Excel range** property of this component.</span></span>

<span data-ttu-id="9562a-139">La propiedad **Dirección de replicación** especifica si el rango se repetirá y cómo lo hará en un documento generado:</span><span class="sxs-lookup"><span data-stu-id="9562a-139">The **Replication direction** property specifies whether and how the range will be repeated in a generated document:</span></span>

- <span data-ttu-id="9562a-140">Si la propiedad **Dirección de replicación** se establece en **Sin replicación**, el rango de Excel apropiado no se repetirá en el documento generado.</span><span class="sxs-lookup"><span data-stu-id="9562a-140">If the **Replication direction** property is set to **No replication**, the appropriate Excel range won't be repeated in the generated document.</span></span>
- <span data-ttu-id="9562a-141">Si la propiedad **Dirección de replicación** se establece en **Vertical**, el rango de Excel apropiado se repetirá en el documento generado.</span><span class="sxs-lookup"><span data-stu-id="9562a-141">If the **Replication direction** property is set to **Vertical**, the appropriate Excel range will be repeated in the generated document.</span></span> <span data-ttu-id="9562a-142">Cada rango replicado se coloca debajo del rango original en una plantilla de Excel.</span><span class="sxs-lookup"><span data-stu-id="9562a-142">Every replicated range is put below the original range in an Excel template.</span></span> <span data-ttu-id="9562a-143">El número de repeticiones se define por el número de registros de un origen de datos del tipo de **Lista de registros** que está vinculado a este componente ER.</span><span class="sxs-lookup"><span data-stu-id="9562a-143">The number of repetitions is defined by the number of records in a data source of the **Record list** type that is bound to this ER component.</span></span>
- <span data-ttu-id="9562a-144">Si la propiedad **Dirección de replicación** se establece en **Horizontal**, el rango de Excel apropiado se repetirá en el documento generado.</span><span class="sxs-lookup"><span data-stu-id="9562a-144">If the **Replication direction** property is set to **Horizontal**, the appropriate Excel range will be repeated in the generated document.</span></span> <span data-ttu-id="9562a-145">Cada rango replicado se coloca a la derecha del rango original en una plantilla de Excel.</span><span class="sxs-lookup"><span data-stu-id="9562a-145">Every replicated range is put to the right of the original range in an Excel template.</span></span> <span data-ttu-id="9562a-146">El número de repeticiones se define por el número de registros de un origen de datos del tipo de **Lista de registros** que está vinculado a este componente ER.</span><span class="sxs-lookup"><span data-stu-id="9562a-146">The number of repetitions is defined by the number of records in a data source of the **Record list** type that is bound to this ER component.</span></span>

<span data-ttu-id="9562a-147">Para obtener más información sobre la replicación horizontal, siga los pasos de [Usar rangos expandibles horizontalmente para agregar columnas dinámicamente en informes de Excel](tasks/er-horizontal-1.md).</span><span class="sxs-lookup"><span data-stu-id="9562a-147">To learn more about horizontal replication, follow the steps in [Use horizontally expandable ranges to dynamically add columns in Excel reports](tasks/er-horizontal-1.md).</span></span>

<span data-ttu-id="9562a-148">El componente **Rango** puede tener otros componentes ER anidados que se usan para introducir valores en los rangos con nombre de Excel apropiados.</span><span class="sxs-lookup"><span data-stu-id="9562a-148">The **Range** component can have other nested ER components that are used to enter values in the appropriate Excel named ranges.</span></span>

- <span data-ttu-id="9562a-149">Si algún componente del grupo **Texto** se usa para introducir valores, el valor se introduce en un rango de Excel como un valor de texto.</span><span class="sxs-lookup"><span data-stu-id="9562a-149">If any component of the **Text** group is used to enter values, the value is entered in an Excel range as a text value.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9562a-150">Use este patrón para formatear los valores introducidos en función de la configuración regional definida en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9562a-150">Use this pattern to format entered values based on the locale that is defined in the application.</span></span>

- <span data-ttu-id="9562a-151">Si el componente **Celda** del grupo **Excel** se usa para Introducir valores, el valor se introduce en un rango de Excel como un valor del tipo de datos que se define mediante el vínculo de ese componente **Celda** (por ejemplo, **Cadena**, **Real** o **Entero**).</span><span class="sxs-lookup"><span data-stu-id="9562a-151">If the **Cell** component of the **Excel** group is used to enter values, the value is entered in an Excel range as a value of the data type that is defined by the binding of that **Cell** component (for example, **String**, **Real**, or **Integer**).</span></span>

    > [!NOTE]
    > <span data-ttu-id="9562a-152">Use este patrón para permitir que la aplicación Excel formatee los valores introducidos en función de la configuración regional del equipo local que abre el documento resultante.</span><span class="sxs-lookup"><span data-stu-id="9562a-152">Use this pattern to enable the Excel application to format entered values based on the locale of the local computer that opens the outbound document.</span></span>

<span data-ttu-id="9562a-153">En la pestaña **Asignación** del diseñador de operación ER, puede configurar la propiedad **Habilitado** de un **Rango** para especificar si el componente debe colocarse en un documento generado:</span><span class="sxs-lookup"><span data-stu-id="9562a-153">On the **Mapping** tab of the ER Operation designer, you can configure the **Enabled** property for a **Range** component to specify whether the component must be put in a generated document:</span></span>

- <span data-ttu-id="9562a-154">Si una expresión de la propiedad **Habilitado** se configura para devolver **Verdadero** en tiempo de ejecución, o si no hay ninguna expresión configurada, el rango apropiado se rellenará en el documento generado.</span><span class="sxs-lookup"><span data-stu-id="9562a-154">If an expression of the **Enabled** property is configured to return **True** at runtime, or if no expression is configured at all, the appropriate range will be filled in in the generated document.</span></span>
- <span data-ttu-id="9562a-155">Si una expresión de la propiedad **Habilitado** se configura para devolver **Falso** en tiempo de ejecución, y si este rango no representa las filas o columnas completas, el rango apropiado no se rellenará en el documento generado.</span><span class="sxs-lookup"><span data-stu-id="9562a-155">If an expression of the **Enabled** property is configured to return **False** at runtime, and if this range doesn't represent the entire rows or columns, the appropriate range won't be filled in in the generated document.</span></span>
- <span data-ttu-id="9562a-156">Si una expresión de la propiedad **Habilitado** se configura para devolver **Falso** en tiempo de ejecución, y si este rango representa las filas o columnas completas, el documento generado contendrá esas filas y columnas como filas y columnas ocultas.</span><span class="sxs-lookup"><span data-stu-id="9562a-156">If an expression of the **Enabled** property is configured to return **False** at runtime, and this range represents the entire rows or columns, the generated document will contain those rows and columns as hidden rows and columns.</span></span>

## <a name="cell-component"></a><span data-ttu-id="9562a-157">Componente Celda</span><span class="sxs-lookup"><span data-stu-id="9562a-157">Cell component</span></span>

<span data-ttu-id="9562a-158">El componente **Celda** se utiliza para rellenar celdas, formas e imágenes con nombre de Excel.</span><span class="sxs-lookup"><span data-stu-id="9562a-158">The **Cell** component is used to fill in Excel named cells, shapes, and pictures.</span></span> <span data-ttu-id="9562a-159">Para indicar un objeto con nombre de Excel que debe rellenarse mediante un completar un componente ER **Celda**, debe especificarse el nombre de ese objeto en la propiedad **Rango de Excel** del componente **Celda**.</span><span class="sxs-lookup"><span data-stu-id="9562a-159">To indicate an Excel named object that must be filled in by a **Cell** ER component, you must specify the name of that object in the **Excel range** property of the **Cell** component.</span></span>

<span data-ttu-id="9562a-160">En la pestaña **Asignación** del diseñador de operación ER, puede configurar la propiedad **Habilitado** de un componente **Celda** para especificar si el objeto debe rellenarse en un documento generado:</span><span class="sxs-lookup"><span data-stu-id="9562a-160">On the **Mapping** tab of the ER Operation designer, you can configure the **Enabled** property for a **Cell** component to specify whether the object must be filled in in a generated document:</span></span>

- <span data-ttu-id="9562a-161">Si una expresión de la propiedad **Habilitado** se configura para devolver **Verdadero** en tiempo de ejecución, o si no hay ninguna expresión configurada, el objeto apropiado se rellenará en el documento generado.</span><span class="sxs-lookup"><span data-stu-id="9562a-161">If an expression of the **Enabled** property is configured to return **True** at runtime, or if no expression is configured at all, the appropriate object will be filled in in the generated document.</span></span> <span data-ttu-id="9562a-162">La vinculación de este componente **Celda** especifica un valor que se coloca en el objeto apropiado.</span><span class="sxs-lookup"><span data-stu-id="9562a-162">The binding of this **Cell** component specifies a value that is put in the appropriate object.</span></span>
- <span data-ttu-id="9562a-163">Si una expresión de la propiedad **Habilitado** está configurada para devolver **Falso** en tiempo de ejecución, el objeto apropiado no se rellenará en el documento generado.</span><span class="sxs-lookup"><span data-stu-id="9562a-163">If an expression of the **Enabled** property is configured to return **False** at runtime, the appropriate object won't be filled in in the generated document.</span></span>

<span data-ttu-id="9562a-164">Cuando un componente **Celda** está configurado para Introducir un valor en una celda, puede vincularse con una fuente de datos que devuelve el valor de un tipo de datos primitivo (por ejemplo, **Cadena**, **Real** o **Entero**).</span><span class="sxs-lookup"><span data-stu-id="9562a-164">When a **Cell** component is configured to enter a value in a cell, it can be bound with a data source that returns the value of a primitive data type (for example, **String**, **Real**, or **Integer**).</span></span> <span data-ttu-id="9562a-165">En este caso, el valor se introduce en la celda como un valor del mismo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="9562a-165">In this case, the value is entered in the cell as a value of the same data type.</span></span>

<span data-ttu-id="9562a-166">Cuando un componente **Celda** está configurado para Introducir un valor en formato de Excel, puede vincularse con un origen de datos que devuelve un valor de un tipo de datos primitivo (por ejemplo, **Cadena**, **Real** o **Entero**).</span><span class="sxs-lookup"><span data-stu-id="9562a-166">When a **Cell** component is configured to enter a value in an Excel shape, it can be bound with a data source that returns a value of a primitive data type (for example, **String**, **Real**, or **Integer**).</span></span> <span data-ttu-id="9562a-167">En este caso, el valor se introduce en la forma de Excel como texto de dicha forma.</span><span class="sxs-lookup"><span data-stu-id="9562a-167">In this case, the value is entered in the Excel shape as the text of that shape.</span></span> <span data-ttu-id="9562a-168">Para valores de tipos de datos que no son **Cadena**, la conversión a texto se realiza automáticamente.</span><span class="sxs-lookup"><span data-stu-id="9562a-168">For values of data types that aren't **String**, the conversion to text is done automatically.</span></span>

> [!NOTE]
> <span data-ttu-id="9562a-169">Puedes configurar un componente **Celda** para rellenar una forma solo en los casos en que se admite una propiedad de texto de forma.</span><span class="sxs-lookup"><span data-stu-id="9562a-169">You can configure a **Cell** component to fill in a shape only in cases where a shape text property is supported.</span></span>

<span data-ttu-id="9562a-170">Cuando un componente **Celda** está configurado para Introducir un valor en una imagen de Excel, puede vincularse con un origen de datos que devuelve un valor del tipo de datos **Contenedor** que representa una imagen en formato binario.</span><span class="sxs-lookup"><span data-stu-id="9562a-170">When a **Cell** component is configured to enter a value in an Excel picture, it can be bound with a data source that returns a value of the **Container** data type that represents an image in binary format.</span></span> <span data-ttu-id="9562a-171">En este caso, el valor se introduce en la imagen de Excel como una imagen.</span><span class="sxs-lookup"><span data-stu-id="9562a-171">In this case, the value is entered in the Excel picture as an image.</span></span>

> [!NOTE]
> <span data-ttu-id="9562a-172">Se considera que cada imagen y forma de Excel está anclada por su esquina superior izquierda a una celda o rango específico de Excel.</span><span class="sxs-lookup"><span data-stu-id="9562a-172">Every Excel picture and shape is considered to be anchored by its upper-left corner to a specific Excel cell or range.</span></span> <span data-ttu-id="9562a-173">Si desea replicar una imagen o forma de Excel, debe configurar la celda o rango al que está anclada como una celda o rango replicados.</span><span class="sxs-lookup"><span data-stu-id="9562a-173">If you want to replicate an Excel picture or shape, you must configure the cell or range that it's anchored to as a replicated cell or range.</span></span>

<span data-ttu-id="9562a-174">Para obtener más información sobre cómo incrustar imágenes y formas, consulte [Incrustar imágenes y formas en documentos que genere utilizando ER](electronic-reporting-embed-images-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="9562a-174">To learn more about how to embed images and shapes, see [Embed images and shapes in documents that you generate by using ER](electronic-reporting-embed-images-shapes.md).</span></span>

## <a name="page-break-component"></a><span data-ttu-id="9562a-175">Componente de salto de página</span><span class="sxs-lookup"><span data-stu-id="9562a-175">Page break component</span></span>

<span data-ttu-id="9562a-176">El componente **PageBreak** obliga a Excel a comenzar una nueva página.</span><span class="sxs-lookup"><span data-stu-id="9562a-176">The **PageBreak** component forces Excel to start a new page.</span></span> <span data-ttu-id="9562a-177">Este componente no es necesario cuando desea utilizar la paginación predeterminada de Excel, pero debe usarla cuando desea que Excel siga su formato ER para estructurar la paginación.</span><span class="sxs-lookup"><span data-stu-id="9562a-177">This component isn't required when you want to use Excel's default paging, but you should use it when you want Excel to follow your ER format to structure paging.</span></span>

## <a name="edit-an-added-er-format"></a><span data-ttu-id="9562a-178">Editar un formato ER agregado</span><span class="sxs-lookup"><span data-stu-id="9562a-178">Edit an added ER format</span></span>

### <a name="update-a-template"></a><span data-ttu-id="9562a-179">Actualizar una plantilla</span><span class="sxs-lookup"><span data-stu-id="9562a-179">Update a template</span></span>

<span data-ttu-id="9562a-180">Puede elegir **Actualizar desde Excel** en la pestaña **Importar** del panel Acciones para importar una plantilla actualizada en un formato ER editable.</span><span class="sxs-lookup"><span data-stu-id="9562a-180">You can select **Update from Excel** on the **Import** tab of the Action Pane to import an updated template into an editable ER format.</span></span> <span data-ttu-id="9562a-181">Durante este proceso, una plantilla del componente **Archivo\\Excel** se reemplazará por una nueva plantilla.</span><span class="sxs-lookup"><span data-stu-id="9562a-181">During this process, a template of the selected **Excel\\File** component will be replaced by a new template.</span></span> <span data-ttu-id="9562a-182">El contenido del formato ER editable se sincronizará con el contenido de la plantilla ER actualizada.</span><span class="sxs-lookup"><span data-stu-id="9562a-182">The content of the editable ER format will be synced with the content of the updated ER template.</span></span>

- <span data-ttu-id="9562a-183">Se creará automáticamente un nuevo componente de formato ER para cada nombre de Excel si el componente de formato ER no se encuentra en el formato editable.</span><span class="sxs-lookup"><span data-stu-id="9562a-183">A new ER format component will automatically be created for every Excel name if the ER format component isn't found in the editable format.</span></span>
- <span data-ttu-id="9562a-184">Todos los componentes del formato ER se eliminarán del formato ER editable si no se encuentra su nombre de Excel apropiado.</span><span class="sxs-lookup"><span data-stu-id="9562a-184">Every ER format component will be deleted from the editable ER format if the appropriate Excel name isn't found for it.</span></span>

> [!NOTE]
> <span data-ttu-id="9562a-185">Establezca la opción **Crear elemento de formato de hoja Excel** en **Sí** cuando quiera crear el elemento opcional **Hoja** en el formato ER editable.</span><span class="sxs-lookup"><span data-stu-id="9562a-185">Set the **Create Excel Sheet format element** option to **Yes** if you want to create the optional **Sheet** element in the editable ER format.</span></span>
>
> <span data-ttu-id="9562a-186">Si el formato ER editable originalmente contenía elementos **Hoja**, se recomienda que configure la opción **Crear elemento de formato de hoja de Excel** en **Sí** cuando importe una plantilla actualizada.</span><span class="sxs-lookup"><span data-stu-id="9562a-186">If the editable ER format originally contained **Sheet** elements, we recommend that you set the **Create Excel Sheet format element** option to **Yes** when you import an updated template.</span></span> <span data-ttu-id="9562a-187">De lo contrario, todos los elementos anidados del elemento **Hoja** original se crearán desde cero.</span><span class="sxs-lookup"><span data-stu-id="9562a-187">Otherwise, all nested elements of the original **Sheet** element will be created from scratch.</span></span> <span data-ttu-id="9562a-188">Por lo tanto, todos los vínculos de los elementos de formato recreados se perderán en el formato ER actualizado.</span><span class="sxs-lookup"><span data-stu-id="9562a-188">Therefore, all bindings of the re-created format elements will be lost in the updated ER format.</span></span>

![Opción Crear elemento de formato de hoja de Excel en el cuadro de diálogo Actualizar desde Excel](./media/er-excel-format-update-template.png)

<span data-ttu-id="9562a-190">Para obtener más información sobre esta función, siga los pasos de [Modificar formatos de informes electrónicos volviendo a aplicar plantillas de Excel](modify-electronic-reporting-format-reapply-excel-template.md).</span><span class="sxs-lookup"><span data-stu-id="9562a-190">To learn more about this feature, follow the steps in [Modify Electronic reporting formats by reapplying Excel templates](modify-electronic-reporting-format-reapply-excel-template.md).</span></span>

## <a name="validate-an-er-format"></a><span data-ttu-id="9562a-191">Validar un formato ER</span><span class="sxs-lookup"><span data-stu-id="9562a-191">Validate an ER format</span></span>

<span data-ttu-id="9562a-192">Cuando valida un formato ER que se puede editar, se realiza una comprobación de coherencia para asegurarse de que el nombre de Excel esté presente en la plantilla de Excel que se utiliza actualmente.</span><span class="sxs-lookup"><span data-stu-id="9562a-192">When you validate an ER format that can be edited, a consistency check is done to make sure that the Excel name is present in the Excel template that is currently used.</span></span> <span data-ttu-id="9562a-193">Se le notificará sobre cualquier incoherencia.</span><span class="sxs-lookup"><span data-stu-id="9562a-193">You will be notified about any inconsistencies.</span></span> <span data-ttu-id="9562a-194">Para algunas incoherencias, se ofrecerá la opción de solucionar problemas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="9562a-194">For some inconsistencies, the option to automatically fix issues will be offered.</span></span>

![Mensaje de error de validación](./media/er-excel-format-validate.png)


## <a name="additional-resources"></a><span data-ttu-id="9562a-196">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9562a-196">Additional resources</span></span>

[<span data-ttu-id="9562a-197">Visión general de los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="9562a-197">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="9562a-198">Diseñar una configuración para generar informes en formato OPENXML</span><span class="sxs-lookup"><span data-stu-id="9562a-198">Design a configuration for generating reports in OPENXML format</span></span>](tasks\er-design-reports-openxml-2016-11.md)

[<span data-ttu-id="9562a-199">Modificar formatos de informes electrónicos al aplicar de nuevo plantillas de Excel</span><span class="sxs-lookup"><span data-stu-id="9562a-199">Modify Electronic reporting formats by reapplying Excel templates</span></span>](modify-electronic-reporting-format-reapply-excel-template.md)

[<span data-ttu-id="9562a-200">Usar rangos expandibles horizontalmente para agregar columnas dinámicamente en informes de Excel</span><span class="sxs-lookup"><span data-stu-id="9562a-200">Use horizontally expandable ranges to dynamically add columns in Excel reports</span></span>](tasks/er-horizontal-1.md)

[<span data-ttu-id="9562a-201">Insertar imágenes y formas en los documentos generados con ER</span><span class="sxs-lookup"><span data-stu-id="9562a-201">Embed images and shapes in documents that you generate by using ER</span></span>](electronic-reporting-embed-images-shapes.md)

[<span data-ttu-id="9562a-202">Configurar informes electrónicos (ER) para proporcionar datos a Power BI</span><span class="sxs-lookup"><span data-stu-id="9562a-202">Configure Electronic reporting (ER) to pull data into Power BI</span></span>](general-electronic-reporting-report-configuration-get-data-powerbi.md)
