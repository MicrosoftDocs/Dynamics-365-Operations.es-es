---
title: Configuración de nombres de campo de aplicación en la aplicación de almacén
description: Este tema describe cómo definir y configurar nombres de campo y prioridades de la aplicación de almacén en Dynamics 365 Supply Chain Management.
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: a3251368e92eb2e24eb9e64bb615027d038ff660
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251094"
---
# <a name="configure-app-field-names-in-warehousing-app"></a><span data-ttu-id="ba8d7-103">Configuración de nombres de campo de aplicación en la aplicación de almacén</span><span class="sxs-lookup"><span data-stu-id="ba8d7-103">Configure app field names in Warehousing app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ba8d7-104">Este tema describe cómo definir y configurar nombres de campo y prioridades de la aplicación de almacén en Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-104">This topic describes how to define and configure warehouse app field names and priorities in Dynamics 365 Supply Chain Management.</span></span> 

<span data-ttu-id="ba8d7-105">**Nota**: este tema se aplica a las características de gestión de almacenes.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-105">**Note:** This topic applies to features in Warehouse management.</span></span> <span data-ttu-id="ba8d7-106">No se aplica a las características de gestión del inventario.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-106">It doesn’t apply to features in Inventory management.</span></span> <span data-ttu-id="ba8d7-107">Warehousing es una aplicación que puede usar para realizar tareas de almacén.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-107">Warehousing is an application that you can use to perform warehouse tasks.</span></span> <span data-ttu-id="ba8d7-108">Es posible definir y configurar los nombres de campo que se utilizan en la aplicación, así como configurar la prioridad a la que los nombres de campo se deben asignar.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-108">You can define and configure the field names that are used in the app, as well as configure the priority to which the field names should be assigned.</span></span> <span data-ttu-id="ba8d7-109">Este tema explica cómo definir y configurar estos nombres de campo y prioridades de la aplicación de almacén y cómo se usan en Warehousing.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-109">This topic explains how to define and configure these warehouse app field names and priorities, and how they are used in Warehousing.</span></span> <span data-ttu-id="ba8d7-110">Para obtener información detallada sobre cómo configurar la conexión a Warehousing, consulte el tutorial sobre [Instalación y configuración de Warehousing](install-configure-warehousing-app.md).</span><span class="sxs-lookup"><span data-stu-id="ba8d7-110">For detailed information about how to configure the connection to FWarehousing, refer to the tutorial [Install and configure Warehousing](install-configure-warehousing-app.md).</span></span>

## <a name="configure-warehouse-app-field-names"></a><span data-ttu-id="ba8d7-111">Configurar nombres de campo de la aplicación de almacén</span><span class="sxs-lookup"><span data-stu-id="ba8d7-111">Configure warehouse app field names</span></span>

<span data-ttu-id="ba8d7-112">Cuando se usa Warehousing en el dispositivo móvil, puede configurar cómo los metadatos se deben mostrar en su dispositivo en la página **Nombres de campo de aplicación de almacén**.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-112">When you use Warehousing on your mobile device, you can configure how metadata should be displayed on your device on the **Warehouse app field names** page.</span></span> <span data-ttu-id="ba8d7-113">En una nueva empresa, seleccione **Crear configuración predeterminada** para generar todos los nombres de campo que se usarán en los flujos de trabajo del dispositivo móvil de almacén y, a continuación, para asignarles un modo y un tipo de entrada preferidos.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-113">In a new company, select **Create default setup** to generate all field names that will be used in the warehouse mobile device workflows, and then assign a preferred input mode and input type to them.</span></span> <span data-ttu-id="ba8d7-114">Una vez que haya generado todos los nombres de campo, puede seleccionar las siguientes opciones de entrada.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-114">After you have generated all field names, you can select the following input options.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba8d7-115">Opción</span><span class="sxs-lookup"><span data-stu-id="ba8d7-115">Option</span></span></th>
<th><span data-ttu-id="ba8d7-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba8d7-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ba8d7-117">Modo de entrada preferido</span><span class="sxs-lookup"><span data-stu-id="ba8d7-117">Preferred input mode</span></span></td>
<td><span data-ttu-id="ba8d7-118">Esta opción define si un campo de detección o un campo de entrada manual se debe mostrar para el nombre del campo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-118">This option defines whether a scanning field or a manual entry input field should be shown for the selected field name.</span></span> <span data-ttu-id="ba8d7-119">Esto resulta útil para distinguir campos en función de si los códigos de barras se usan para el campo.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-119">This is useful to distinguish fields depending on if barcodes are used for the field.</span></span> <span data-ttu-id="ba8d7-120"><strong>Nota:</strong> Para los nombres de campo con el modo de entrada preferido establecido como <strong>Exploración</strong>, puede especificar información manualmente si el código de barras es ilegible o está dañado.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-120"><strong>Note:</strong> For field names with preferred input mode set to <strong>Scanning</strong>, you can enter information manually if the barcode is unreadable or damaged.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ba8d7-121">Tipo de entrada</span><span class="sxs-lookup"><span data-stu-id="ba8d7-121">Input type</span></span></td>
<td><span data-ttu-id="ba8d7-122">Esta opción define qué tipo de entrada se va a utilizar para el nombre del campo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-122">This option defines what input type should be used for the selected field name.</span></span> <span data-ttu-id="ba8d7-123">Las opciones disponibles son cuatro:</span><span class="sxs-lookup"><span data-stu-id="ba8d7-123">Four options are available:</span></span>
<ul>
<li><span data-ttu-id="ba8d7-124"><strong>Selección</strong> - contiene una lista de opciones entre las que elegir.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-124"><strong>Selection</strong> - Contains a list of options to choose from.</span></span> <span data-ttu-id="ba8d7-125">Los nombres de campo con esta opción no se pueden editar.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-125">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="ba8d7-126"><strong>Fecha</strong> - los nombres de campos especificados como fecha muestran un formato de fecha con la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-126"><strong>Date</strong> - Field names specified as date will show a date format with the label.</span></span> <span data-ttu-id="ba8d7-127">Esto ayuda a los trabajadores del almacén a ver en qué formato deben especificar la fecha.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-127">This helps warehouse workers see in which format to enter the date.</span></span> <span data-ttu-id="ba8d7-128">Los nombres de campo con esta opción no se pueden editar.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-128">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="ba8d7-129"><strong>Alfa</strong> - si se selecciona, el teclado del dispositivo se usará al especificar la información manualmente en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-129"><strong>Alpha</strong> - If selected, the device keyboard will be used when entering information manually in the app.</span></span> <span data-ttu-id="ba8d7-130">La experiencia de teclado se puede modificar en función de qué dispositivo se usa.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-130">The keyboard experience can be changed depending on which device is used.</span></span></li>
<li><span data-ttu-id="ba8d7-131"><strong>Numérico</strong> - para los nombres de campo que usan solo entradas numéricas, puede seleccionar esta opción para mostrar un teclado numérico personalizado con el campo de entrada en lugar del teclado del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-131"><strong>Numeric</strong> - For field names that use numeric input only, you can select this option to display a custom numeric keypad with the input field instead of the device keyboard.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configure-warehouse-app-field-priority"></a><span data-ttu-id="ba8d7-132">Configurar la prioridad de campo de aplicación de almacén</span><span class="sxs-lookup"><span data-stu-id="ba8d7-132">Configure warehouse app field priority</span></span>

<span data-ttu-id="ba8d7-133">En la página **Prioridad de campo de aplicación de almacén**, puede poner nombres de campo en distintos grupos de prioridad.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-133">On the **Warehouse app field priority** page, you can put field names into different priority groups.</span></span> <span data-ttu-id="ba8d7-134">Esto permite decidir qué información se debe mostrar en la página de la tarea principal cuando los trabajadores del almacén realizan tareas mediante la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-134">This makes it possible to decide what information should be displayed on the main task page when warehouse workers perform tasks using the app.</span></span> <span data-ttu-id="ba8d7-135">Si hace clic en **Crear configuración predeterminada**, se generará un conjunto predeterminado de grupos de prioridad.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-135">If you click **Create default setup**, a default set of priority groups will be generated.</span></span> <span data-ttu-id="ba8d7-136">Es posible crear tantos grupos de prioridad según sea necesario, pero solo se mostrarán tres grupos de prioridad en la página de tareas.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-136">It is possible to create as many priority groups as needed, but only three priority groups will be shown on the task page.</span></span> <span data-ttu-id="ba8d7-137">Cuando el sistema envía metadatos a la aplicación, asignará a cada campo una prioridad relativa en función de su grupo de prioridad, y la aplicación mostrará los primeros tres grupos de prioridad contenidos en los metadatos en la página de tareas.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-137">When the system sends metadata to the app, it will assign each field a relative priority depending on its priority group, and the app will display the first three priority groups contained in the metadata on the task page.</span></span> <span data-ttu-id="ba8d7-138">El resto de los metadatos que se desbordan se mostrará en una página de detalles secundaria.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-138">The rest of the overflowing metadata will be displayed on a secondary details page.</span></span> <span data-ttu-id="ba8d7-139">En la tabla siguiente se muestra un ejemplo de cinco grupos de prioridad.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-139">The following table shows an example of five priority groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba8d7-140">Grupo de prioridad</span><span class="sxs-lookup"><span data-stu-id="ba8d7-140">Priority group</span></span></th>
<th><span data-ttu-id="ba8d7-141">Campos asignados</span><span class="sxs-lookup"><span data-stu-id="ba8d7-141">Assigned fields</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> <span data-ttu-id="ba8d7-142">Prioridad 10</span><span class="sxs-lookup"><span data-stu-id="ba8d7-142">Priority 10</span></span></td>
<td><ul>
<li><span data-ttu-id="ba8d7-143">Artículo</span><span class="sxs-lookup"><span data-stu-id="ba8d7-143">Item</span></span></li>
<li><span data-ttu-id="ba8d7-144">Cantidad</span><span class="sxs-lookup"><span data-stu-id="ba8d7-144">Quantity</span></span></li>
<li><span data-ttu-id="ba8d7-145">Unidad de medida</span><span class="sxs-lookup"><span data-stu-id="ba8d7-145">Unit of measure</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="ba8d7-146">Prioridad 20</span><span class="sxs-lookup"><span data-stu-id="ba8d7-146">Priority 20</span></span></td>
<td><ul>
<li><span data-ttu-id="ba8d7-147">Posición del clúster</span><span class="sxs-lookup"><span data-stu-id="ba8d7-147">Cluster position</span></span></li>
<li><span data-ttu-id="ba8d7-148">Clúster</span><span class="sxs-lookup"><span data-stu-id="ba8d7-148">Cluster</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="ba8d7-149">Prioridad 30</span><span class="sxs-lookup"><span data-stu-id="ba8d7-149">Priority 30</span></span></td>
<td><ul>
<li><span data-ttu-id="ba8d7-150">Descripción de artículo</span><span class="sxs-lookup"><span data-stu-id="ba8d7-150">Item description</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="ba8d7-151">Prioridad 40</span><span class="sxs-lookup"><span data-stu-id="ba8d7-151">Priority 40</span></span></td>
<td><ul>
<li><span data-ttu-id="ba8d7-152">Configuración</span><span class="sxs-lookup"><span data-stu-id="ba8d7-152">Configuration</span></span></li>
<li><span data-ttu-id="ba8d7-153">Color</span><span class="sxs-lookup"><span data-stu-id="ba8d7-153">Color</span></span></li>
<li><span data-ttu-id="ba8d7-154">Tamaño</span><span class="sxs-lookup"><span data-stu-id="ba8d7-154">Size</span></span></li>
<li><span data-ttu-id="ba8d7-155">Estilo</span><span class="sxs-lookup"><span data-stu-id="ba8d7-155">Style</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="ba8d7-156">Prioridad 50</span><span class="sxs-lookup"><span data-stu-id="ba8d7-156">Priority 50</span></span></td>
<td><ul>
<li><span data-ttu-id="ba8d7-157">Ubicación</span><span class="sxs-lookup"><span data-stu-id="ba8d7-157">Location</span></span></li>
<li><span data-ttu-id="ba8d7-158">Matrícula de entidad de almacén</span><span class="sxs-lookup"><span data-stu-id="ba8d7-158">License plate</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ba8d7-159">Por ejemplo, cuando un trabajador del almacén realiza una tarea en un dispositivo móvil, si los metadatos que se van a mostrar en la aplicación constan de los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ba8d7-159">For example, when a warehouse worker is performing a task on a mobile device, if the metadata that will be displayed in the app consists of the following fields:</span></span>

-   <span data-ttu-id="ba8d7-160">Artículo</span><span class="sxs-lookup"><span data-stu-id="ba8d7-160">Item</span></span>
-   <span data-ttu-id="ba8d7-161">Cantidad</span><span class="sxs-lookup"><span data-stu-id="ba8d7-161">Quantity</span></span>
-   <span data-ttu-id="ba8d7-162">Unidad de medida</span><span class="sxs-lookup"><span data-stu-id="ba8d7-162">Unit of measure</span></span>
-   <span data-ttu-id="ba8d7-163">Descripción de artículo</span><span class="sxs-lookup"><span data-stu-id="ba8d7-163">Item description</span></span>
-   <span data-ttu-id="ba8d7-164">Tamaño y ubicación</span><span class="sxs-lookup"><span data-stu-id="ba8d7-164">Size and Location</span></span>

<span data-ttu-id="ba8d7-165">En función de la configuración de la prioridad del campo de la aplicación de almacén de la tabla anterior, las 3 filas siguientes de información se mostrarán en la página de tareas:</span><span class="sxs-lookup"><span data-stu-id="ba8d7-165">Based on the warehouse app field priority set up in the table above, the following 3 rows of information will be displayed on the task page:</span></span>

-   <span data-ttu-id="ba8d7-166">Fila 1: artículo, cantidad, unidad de medida</span><span class="sxs-lookup"><span data-stu-id="ba8d7-166">Row 1: Item, Quantity, Unit of measure</span></span>
-   <span data-ttu-id="ba8d7-167">Fila 2: descripción del artículo</span><span class="sxs-lookup"><span data-stu-id="ba8d7-167">Row 2: Item description</span></span>
-   <span data-ttu-id="ba8d7-168">Fila 3: tamaño</span><span class="sxs-lookup"><span data-stu-id="ba8d7-168">Row 3: Size</span></span>

<span data-ttu-id="ba8d7-169">Los metadatos restantes, por ejemplo, ubicación, no se muestran en la página de tareas, pero se mostrarán en una página de detalles.</span><span class="sxs-lookup"><span data-stu-id="ba8d7-169">The remaining metadata, for example, Location, will not be displayed on the task page, but will be displayed on a details page.</span></span> <span data-ttu-id="ba8d7-170">Para obtener más información y ver ejemplos de la interfaz de usuario, consulte el artículo del blog sobre [Finance and Operations - Warehousing](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span><span class="sxs-lookup"><span data-stu-id="ba8d7-170">To learn more and see examples of the user interface, refer to the blog post [Announcing Finance and Operations - Warehousing](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span></span>

<a name="additional-resources"></a><span data-ttu-id="ba8d7-171">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ba8d7-171">Additional resources</span></span>
--------

[<span data-ttu-id="ba8d7-172">Instalar y configurar Microsoft Dynamics 365 for Finance and Operations - Warehousing</span><span class="sxs-lookup"><span data-stu-id="ba8d7-172">Install and configure Microsoft Dynamics 365 for Finance and Operations – Warehousing</span></span>](install-configure-warehousing-app.md)
