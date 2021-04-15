---
title: Configurar campos para la aplicación móvil Gestión de almacenes
description: Este tema describe cómo definir y configurar nombres de campo y prioridades de los campos mostrados en la aplicación móvil Warehouse Management.
author: MarkusFogelberg
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c6ed726536085b836f4014c59ea8df4755577ab5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808831"
---
# <a name="configure-fields-for-the-warehouse-management-mobile-app"></a><span data-ttu-id="91900-103">Configurar campos para la aplicación móvil Gestión de almacenes</span><span class="sxs-lookup"><span data-stu-id="91900-103">Configure fields for the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="91900-104">Este tema describe cómo definir y configurar nombres de campo y prioridades de los campos mostrados en la aplicación móvil Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="91900-104">This topic describes how to define and configure names and priorities of fields shown in the Warehouse Management mobile app.</span></span>

> [!NOTE]
> <span data-ttu-id="91900-105">Este tema se aplica a las funciones de gestión de almacenes.</span><span class="sxs-lookup"><span data-stu-id="91900-105">This topic applies to features in Warehouse management.</span></span> <span data-ttu-id="91900-106">No se aplica a las características de gestión del inventario.</span><span class="sxs-lookup"><span data-stu-id="91900-106">It doesn’t apply to features in Inventory management.</span></span> <span data-ttu-id="91900-107">La aplicación móvil Warehouse Management es una aplicación que puede usar para realizar tareas de almacén.</span><span class="sxs-lookup"><span data-stu-id="91900-107">The Warehouse Management mobile app is an application that you can use to perform warehouse tasks.</span></span> <span data-ttu-id="91900-108">Es posible definir y configurar los nombres de campo que se utilizan en la aplicación, así como configurar la prioridad a la que los nombres de campo se deben asignar.</span><span class="sxs-lookup"><span data-stu-id="91900-108">You can define and configure the field names that are used in the app, as well as configure the priority to which the field names should be assigned.</span></span> <span data-ttu-id="91900-109">Este tema explica cómo definir y configurar estos nombres de campo y prioridades de la aplicación móvil Warehouse Management y cómo se usan.</span><span class="sxs-lookup"><span data-stu-id="91900-109">This topic explains how to define and configure these Warehouse Management mobile app field names and priorities, and how they are used.</span></span>

## <a name="configure-warehouse-app-field-names"></a><span data-ttu-id="91900-110">Configurar nombres de campo de la aplicación de almacén</span><span class="sxs-lookup"><span data-stu-id="91900-110">Configure warehouse app field names</span></span>

<span data-ttu-id="91900-111">Cuando se usa Warehousing en el dispositivo móvil, puede configurar cómo los metadatos se deben mostrar en su dispositivo en la página **Nombres de campo de aplicación de almacén**.</span><span class="sxs-lookup"><span data-stu-id="91900-111">When you use Warehousing on your mobile device, you can configure how metadata should be displayed on your device on the **Warehouse app field names** page.</span></span> <span data-ttu-id="91900-112">En una nueva empresa, seleccione **Crear configuración predeterminada** para generar todos los nombres de campo que se usarán en los flujos de trabajo del dispositivo móvil de almacén y, a continuación, para asignarles un modo y un tipo de entrada preferidos.</span><span class="sxs-lookup"><span data-stu-id="91900-112">In a new company, select **Create default setup** to generate all field names that will be used in the warehouse mobile device workflows, and then assign a preferred input mode and input type to them.</span></span> <span data-ttu-id="91900-113">Una vez que haya generado todos los nombres de campo, puede seleccionar las siguientes opciones de entrada.</span><span class="sxs-lookup"><span data-stu-id="91900-113">After you have generated all field names, you can select the following input options.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91900-114">Opción</span><span class="sxs-lookup"><span data-stu-id="91900-114">Option</span></span></th>
<th><span data-ttu-id="91900-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="91900-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="91900-116">Modo de entrada preferido</span><span class="sxs-lookup"><span data-stu-id="91900-116">Preferred input mode</span></span></td>
<td><span data-ttu-id="91900-117">Esta opción define si un campo de detección o un campo de entrada manual se debe mostrar para el nombre del campo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="91900-117">This option defines whether a scanning field or a manual entry input field should be shown for the selected field name.</span></span> <span data-ttu-id="91900-118">Esto resulta útil para distinguir campos en función de si los códigos de barras se usan para el campo.</span><span class="sxs-lookup"><span data-stu-id="91900-118">This is useful to distinguish fields depending on if barcodes are used for the field.</span></span> <span data-ttu-id="91900-119"><strong>Nota:</strong> Para los nombres de campo con el modo de entrada preferido establecido como <strong>Exploración</strong>, puede especificar información manualmente si el código de barras es ilegible o está dañado.</span><span class="sxs-lookup"><span data-stu-id="91900-119"><strong>Note:</strong> For field names with preferred input mode set to <strong>Scanning</strong>, you can enter information manually if the barcode is unreadable or damaged.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="91900-120">Tipo de entrada</span><span class="sxs-lookup"><span data-stu-id="91900-120">Input type</span></span></td>
<td><span data-ttu-id="91900-121">Esta opción define qué tipo de entrada se va a utilizar para el nombre del campo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="91900-121">This option defines what input type should be used for the selected field name.</span></span> <span data-ttu-id="91900-122">Las opciones disponibles son cuatro:</span><span class="sxs-lookup"><span data-stu-id="91900-122">Four options are available:</span></span>
<ul>
<li><span data-ttu-id="91900-123"><strong>Selección</strong> - contiene una lista de opciones entre las que elegir.</span><span class="sxs-lookup"><span data-stu-id="91900-123"><strong>Selection</strong> - Contains a list of options to choose from.</span></span> <span data-ttu-id="91900-124">Los nombres de campo con esta opción no se pueden editar.</span><span class="sxs-lookup"><span data-stu-id="91900-124">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="91900-125"><strong>Fecha</strong> - los nombres de campos especificados como fecha muestran un formato de fecha con la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="91900-125"><strong>Date</strong> - Field names specified as date will show a date format with the label.</span></span> <span data-ttu-id="91900-126">Esto ayuda a los trabajadores del almacén a ver en qué formato deben especificar la fecha.</span><span class="sxs-lookup"><span data-stu-id="91900-126">This helps warehouse workers see in which format to enter the date.</span></span> <span data-ttu-id="91900-127">Los nombres de campo con esta opción no se pueden editar.</span><span class="sxs-lookup"><span data-stu-id="91900-127">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="91900-128"><strong>Alfa</strong> - si se selecciona, el teclado del dispositivo se usará al especificar la información manualmente en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="91900-128"><strong>Alpha</strong> - If selected, the device keyboard will be used when entering information manually in the app.</span></span> <span data-ttu-id="91900-129">La experiencia de teclado se puede modificar en función de qué dispositivo se usa.</span><span class="sxs-lookup"><span data-stu-id="91900-129">The keyboard experience can be changed depending on which device is used.</span></span></li>
<li><span data-ttu-id="91900-130"><strong>Numérico</strong> - para los nombres de campo que usan solo entradas numéricas, puede seleccionar esta opción para mostrar un teclado numérico personalizado con el campo de entrada en lugar del teclado del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="91900-130"><strong>Numeric</strong> - For field names that use numeric input only, you can select this option to display a custom numeric keypad with the input field instead of the device keyboard.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configure-warehouse-app-field-priority"></a><span data-ttu-id="91900-131">Configurar la prioridad de campo de aplicación de almacén</span><span class="sxs-lookup"><span data-stu-id="91900-131">Configure warehouse app field priority</span></span>

<span data-ttu-id="91900-132">En la página **Prioridad de campo de aplicación de almacén**, puede poner nombres de campo en distintos grupos de prioridad.</span><span class="sxs-lookup"><span data-stu-id="91900-132">On the **Warehouse app field priority** page, you can put field names into different priority groups.</span></span> <span data-ttu-id="91900-133">Esto permite decidir qué información se debe mostrar en la página de la tarea principal cuando los trabajadores del almacén realizan tareas mediante la aplicación.</span><span class="sxs-lookup"><span data-stu-id="91900-133">This makes it possible to decide what information should be displayed on the main task page when warehouse workers perform tasks using the app.</span></span> <span data-ttu-id="91900-134">Si hace clic en **Crear configuración predeterminada**, se generará un conjunto predeterminado de grupos de prioridad.</span><span class="sxs-lookup"><span data-stu-id="91900-134">If you click **Create default setup**, a default set of priority groups will be generated.</span></span> <span data-ttu-id="91900-135">Es posible crear tantos grupos de prioridad según sea necesario, pero solo se mostrarán tres grupos de prioridad en la página de tareas.</span><span class="sxs-lookup"><span data-stu-id="91900-135">It is possible to create as many priority groups as needed, but only three priority groups will be shown on the task page.</span></span> <span data-ttu-id="91900-136">Cuando el sistema envía metadatos a la aplicación, asignará a cada campo una prioridad relativa en función de su grupo de prioridad, y la aplicación mostrará los primeros tres grupos de prioridad contenidos en los metadatos en la página de tareas.</span><span class="sxs-lookup"><span data-stu-id="91900-136">When the system sends metadata to the app, it will assign each field a relative priority depending on its priority group, and the app will display the first three priority groups contained in the metadata on the task page.</span></span> <span data-ttu-id="91900-137">El resto de los metadatos que se desbordan se mostrará en una página de detalles secundaria.</span><span class="sxs-lookup"><span data-stu-id="91900-137">The rest of the overflowing metadata will be displayed on a secondary details page.</span></span> <span data-ttu-id="91900-138">En la tabla siguiente se muestra un ejemplo de cinco grupos de prioridad.</span><span class="sxs-lookup"><span data-stu-id="91900-138">The following table shows an example of five priority groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91900-139">Grupo de prioridad</span><span class="sxs-lookup"><span data-stu-id="91900-139">Priority group</span></span></th>
<th><span data-ttu-id="91900-140">Campos asignados</span><span class="sxs-lookup"><span data-stu-id="91900-140">Assigned fields</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> <span data-ttu-id="91900-141">Prioridad 10</span><span class="sxs-lookup"><span data-stu-id="91900-141">Priority 10</span></span></td>
<td><ul>
<li><span data-ttu-id="91900-142">Artículo</span><span class="sxs-lookup"><span data-stu-id="91900-142">Item</span></span></li>
<li><span data-ttu-id="91900-143">Cantidad</span><span class="sxs-lookup"><span data-stu-id="91900-143">Quantity</span></span></li>
<li><span data-ttu-id="91900-144">Unidad de medida</span><span class="sxs-lookup"><span data-stu-id="91900-144">Unit of measure</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="91900-145">Prioridad 20</span><span class="sxs-lookup"><span data-stu-id="91900-145">Priority 20</span></span></td>
<td><ul>
<li><span data-ttu-id="91900-146">Posición del clúster</span><span class="sxs-lookup"><span data-stu-id="91900-146">Cluster position</span></span></li>
<li><span data-ttu-id="91900-147">Clúster</span><span class="sxs-lookup"><span data-stu-id="91900-147">Cluster</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="91900-148">Prioridad 30</span><span class="sxs-lookup"><span data-stu-id="91900-148">Priority 30</span></span></td>
<td><ul>
<li><span data-ttu-id="91900-149">Descripción de artículo</span><span class="sxs-lookup"><span data-stu-id="91900-149">Item description</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="91900-150">Prioridad 40</span><span class="sxs-lookup"><span data-stu-id="91900-150">Priority 40</span></span></td>
<td><ul>
<li><span data-ttu-id="91900-151">Configuración</span><span class="sxs-lookup"><span data-stu-id="91900-151">Configuration</span></span></li>
<li><span data-ttu-id="91900-152">Color</span><span class="sxs-lookup"><span data-stu-id="91900-152">Color</span></span></li>
<li><span data-ttu-id="91900-153">Tamaño</span><span class="sxs-lookup"><span data-stu-id="91900-153">Size</span></span></li>
<li><span data-ttu-id="91900-154">Estilo</span><span class="sxs-lookup"><span data-stu-id="91900-154">Style</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="91900-155">Prioridad 50</span><span class="sxs-lookup"><span data-stu-id="91900-155">Priority 50</span></span></td>
<td><ul>
<li><span data-ttu-id="91900-156">Ubicación</span><span class="sxs-lookup"><span data-stu-id="91900-156">Location</span></span></li>
<li><span data-ttu-id="91900-157">Matrícula de entidad de almacén</span><span class="sxs-lookup"><span data-stu-id="91900-157">License plate</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="91900-158">Por ejemplo, cuando un trabajador del almacén realiza una tarea en un dispositivo móvil, si los metadatos que se van a mostrar en la aplicación constan de los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="91900-158">For example, when a warehouse worker is performing a task on a mobile device, if the metadata that will be displayed in the app consists of the following fields:</span></span>

-   <span data-ttu-id="91900-159">Artículo</span><span class="sxs-lookup"><span data-stu-id="91900-159">Item</span></span>
-   <span data-ttu-id="91900-160">Cantidad</span><span class="sxs-lookup"><span data-stu-id="91900-160">Quantity</span></span>
-   <span data-ttu-id="91900-161">Unidad de medida</span><span class="sxs-lookup"><span data-stu-id="91900-161">Unit of measure</span></span>
-   <span data-ttu-id="91900-162">Descripción de artículo</span><span class="sxs-lookup"><span data-stu-id="91900-162">Item description</span></span>
-   <span data-ttu-id="91900-163">Tamaño y ubicación</span><span class="sxs-lookup"><span data-stu-id="91900-163">Size and Location</span></span>

<span data-ttu-id="91900-164">En función de la configuración de la prioridad del campo de la aplicación de almacén de la tabla anterior, las 3 filas siguientes de información se mostrarán en la página de tareas:</span><span class="sxs-lookup"><span data-stu-id="91900-164">Based on the warehouse app field priority set up in the table above, the following 3 rows of information will be displayed on the task page:</span></span>

-   <span data-ttu-id="91900-165">Fila 1: artículo, cantidad, unidad de medida</span><span class="sxs-lookup"><span data-stu-id="91900-165">Row 1: Item, Quantity, Unit of measure</span></span>
-   <span data-ttu-id="91900-166">Fila 2: descripción del artículo</span><span class="sxs-lookup"><span data-stu-id="91900-166">Row 2: Item description</span></span>
-   <span data-ttu-id="91900-167">Fila 3: tamaño</span><span class="sxs-lookup"><span data-stu-id="91900-167">Row 3: Size</span></span>

<span data-ttu-id="91900-168">Los metadatos restantes, por ejemplo, ubicación, no se muestran en la página de tareas, pero se mostrarán en una página de detalles.</span><span class="sxs-lookup"><span data-stu-id="91900-168">The remaining metadata, for example, Location, will not be displayed on the task page, but will be displayed on a details page.</span></span> <span data-ttu-id="91900-169">Para obtener más información y ver ejemplos de la interfaz de usuario, consulte el artículo del blog [Presentando Finance and Operations - Warehousing](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span><span class="sxs-lookup"><span data-stu-id="91900-169">To learn more and see examples of the user interface, refer to the blog post [Announcing Finance and Operations - Warehousing](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span></span>

<a name="additional-resources"></a><span data-ttu-id="91900-170">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="91900-170">Additional resources</span></span>
--------

[<span data-ttu-id="91900-171">Instalar y conectar la aplicación móvil Gestión de almacenes</span><span class="sxs-lookup"><span data-stu-id="91900-171">Install and connect the Warehouse Management mobile app</span></span>](../warehousing/install-configure-warehouse-management-app.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]