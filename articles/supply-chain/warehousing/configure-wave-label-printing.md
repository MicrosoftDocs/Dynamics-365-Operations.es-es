---
title: Configurar y usar impresión de etiquetas de oleada
description: Este tema describe la impresión de etiquetas de oleada y explica cómo configurarla.
author: GarmMSFT
manager: PJacobse
ms.date: 05/01/2020
ms.topic: configure-wave-label-printing
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveLabel, WHSWaveLabelTemplate, WHSWaveLabelLayoutRow, WHSDocumentRouting, WHSWaveTableListPage, WHSPostMethod, WHSMobileDisplayWaveLabelListLookup, WHSWaveLabelType, WHSWaveLabelTemplateGroup, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: PJacobse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: yyyy-mm-dd
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 1f51ed9f05caede3d4f320ddb6b705e67df9aa1f
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016966"
---
# <a name="set-up-and-use-wave-label-printing"></a><span data-ttu-id="323e2-103">Configurar y usar impresión de etiquetas de oleada</span><span class="sxs-lookup"><span data-stu-id="323e2-103">Set up and use wave label printing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="323e2-104">La impresión de etiquetas de oleada ofrece un enfoque alternativo a la impresión de etiquetas al introducir un método de nuevo paso de oleada que permite crear e imprimir etiquetas directamente desde la plantilla de oleada durante la ejecución de la oleada.</span><span class="sxs-lookup"><span data-stu-id="323e2-104">Wave label printing offers an alternative approach to label printing by introducing a new wave step method that lets you create and print labels directly from the wave template during wave execution.</span></span> <span data-ttu-id="323e2-105">Por lo tanto, las etiquetas ya estarán disponibles antes de que los trabajadores ejecuten la orden de trabajo en un dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="323e2-105">Therefore, the labels will already be available before workers run the work order on a mobile device.</span></span> <span data-ttu-id="323e2-106">Después, los trabajadores pueden adjuntar las etiquetas requeridas durante la recogida en vez de después de esta.</span><span class="sxs-lookup"><span data-stu-id="323e2-106">Workers can then attach the required labels during picking instead of after picking.</span></span>

<span data-ttu-id="323e2-107">La impresión de etiquetas de oleadas utiliza el lenguaje de programación Zebra (ZPL) para crear los diseños de las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="323e2-107">Wave label printing uses Zebra Programming Language (ZPL) to create label layouts.</span></span> <span data-ttu-id="323e2-108">Un diseño de etiqueta se divide en tres secciones (encabezado, cuerpo y pie de página) para permitir etiquetas que tengan una estructura repetitiva.</span><span class="sxs-lookup"><span data-stu-id="323e2-108">A label layout is divided into three sections (header, body, and footer) to allow for labels that have repeating structure.</span></span> <span data-ttu-id="323e2-109">Las plantillas de etiquetas de oleadas le indican al sistema qué diseño de etiqueta usar.</span><span class="sxs-lookup"><span data-stu-id="323e2-109">Wave label templates tell the system which label layout to use.</span></span> <span data-ttu-id="323e2-110">Los usuarios pueden especificar qué impresora se utiliza.</span><span class="sxs-lookup"><span data-stu-id="323e2-110">Users can specify which printer is used.</span></span> <span data-ttu-id="323e2-111">También pueden imprimir etiquetas en varias impresoras al mismo tiempo, según lo requieran.</span><span class="sxs-lookup"><span data-stu-id="323e2-111">They can also print labels on several printers at the same time, as they require.</span></span> <span data-ttu-id="323e2-112">La página **Historial de etiquetas de oleada** muestra un registro de todas las etiquetas que se han creado utilizando esta configuración.</span><span class="sxs-lookup"><span data-stu-id="323e2-112">The **Wave label history** page shows a record of all labels that have been created by using this setup.</span></span>

<span data-ttu-id="323e2-113">Puede imprimir e intercalar etiquetas basadas en encabezados de trabajo, imprimir etiquetas de interrupción por encabezados de trabajo, además de imprimir etiquetas de contenido de contenedor, etiquetas de cajas y otras etiquetas similares.</span><span class="sxs-lookup"><span data-stu-id="323e2-113">You can print and collate labels based on work headers, you can print break labels per work header, and you can print container content labels, case labels, and other similar labels.</span></span>

> [!NOTE]
> <span data-ttu-id="323e2-114">Esta funcionalidad no reemplaza la funcionalidad de impresión de etiquetas existente que se basa en el enrutamiento de documentos.</span><span class="sxs-lookup"><span data-stu-id="323e2-114">This functionality doesn't replace existing label printing functionality that is based on document routing.</span></span>

<span data-ttu-id="323e2-115">La impresión de etiquetas de oleadas ofrece las siguientes mejoras:</span><span class="sxs-lookup"><span data-stu-id="323e2-115">Wave label printing offers the following enhancements:</span></span>

- <span data-ttu-id="323e2-116">Imprimir etiquetas de acuerdo con el número de cajas en una sola línea de trabajo, sin utilizar la creación de contenedores.</span><span class="sxs-lookup"><span data-stu-id="323e2-116">Print labels according to the number of cartons on a single work line, without using containerization.</span></span> <span data-ttu-id="323e2-117">(Una "caja" es una unidad designada en líneas de grupo de secuencia de unidades.)</span><span class="sxs-lookup"><span data-stu-id="323e2-117">(A "carton" is a unit that is designated on unit sequence group lines.)</span></span>
- <span data-ttu-id="323e2-118">Imprimir varias secuencias de etiquetas diferentes (por ejemplo, etiquetas de cajas y pallets).</span><span class="sxs-lookup"><span data-stu-id="323e2-118">Print several different label sequences (for example, carton and pallet labels).</span></span>
- <span data-ttu-id="323e2-119">Incluir la enumeración de etiquetas (por ejemplo, 1/124, 2/124, ... 124/124) y definir el rango de enumeración (por ejemplo, línea de trabajo, línea de carga o envío).</span><span class="sxs-lookup"><span data-stu-id="323e2-119">Include label enumeration (for example, 1/124, 2/124, ... 124/124), and define the range of enumeration (for example, work line, load line, or shipment).</span></span>
- <span data-ttu-id="323e2-120">Crear e imprimir un id. de conocimiento de embarque en las etiquetas antes de que se genere el conocimiento de embarque.</span><span class="sxs-lookup"><span data-stu-id="323e2-120">Create and print a bill of lading ID on labels before the bill of lading is generated.</span></span>
- <span data-ttu-id="323e2-121">Crear un código único de contenedor de envío en serie (SSCC) para cada caja e incluirlo en cada etiqueta.</span><span class="sxs-lookup"><span data-stu-id="323e2-121">Create a unique serial shipping container code (SSCC) for each carton, and include it on each label.</span></span>
- <span data-ttu-id="323e2-122">Crear secuencias numéricos que cumplan con GS1 para id. de conocimiento de embarque y SSCC.</span><span class="sxs-lookup"><span data-stu-id="323e2-122">Create GS1-compliant number sequences for bill of lading IDs and SSCCs.</span></span>
- <span data-ttu-id="323e2-123">Volver a imprimir etiquetas desde dispositivos móviles y el cliente enriquecido.</span><span class="sxs-lookup"><span data-stu-id="323e2-123">Reprint labels from both mobile devices and the rich client.</span></span>
- <span data-ttu-id="323e2-124">Anular las etiquetas (por ejemplo, en escenarios de selección corta) y volver a imprimirlas.</span><span class="sxs-lookup"><span data-stu-id="323e2-124">Void labels (for example, in short pick scenarios), and reprint them.</span></span>
- <span data-ttu-id="323e2-125">Limpiar el historial de etiquetas de oleadas.</span><span class="sxs-lookup"><span data-stu-id="323e2-125">Clean up the wave label history.</span></span>
- <span data-ttu-id="323e2-126">Las mejoras en los diseños de enrutamiento de documentos se comparten entre los diseños de enrutamiento de documentos y los diseños de etiquetas de oleadas.</span><span class="sxs-lookup"><span data-stu-id="323e2-126">Improvements to document routing layouts are shared between document routing layouts and wave label layouts.</span></span> <span data-ttu-id="323e2-127">(Para más información, consulte [Diseño de enrutamiento de documentos para matrículas](../warehousing/document-routing-layout-for-license-plates.md).)</span><span class="sxs-lookup"><span data-stu-id="323e2-127">(For more information, see [Document routing layout for license plates](../warehousing/document-routing-layout-for-license-plates.md).)</span></span>

<span data-ttu-id="323e2-128">Estas mejoras hacen que el etiquetado de cajas antes de la paletización sea más eficiente.</span><span class="sxs-lookup"><span data-stu-id="323e2-128">These enhancements make it more efficient to label cartons before palletization.</span></span> <span data-ttu-id="323e2-129">Benefician especialmente a las empresas que envían a grandes minoristas que confirman automáticamente los recibos de los pedidos escaneando cada caja por separado.</span><span class="sxs-lookup"><span data-stu-id="323e2-129">They especially benefit companies that ship to large retailers that automatically confirm order receipts by scanning each carton separately.</span></span>

> [!NOTE]
> <span data-ttu-id="323e2-130">Puede implementar los escenarios de configuración que se describen en este tema por separado o en combinación, según los requisitos de su negocio.</span><span class="sxs-lookup"><span data-stu-id="323e2-130">You can implement the configuration scenarios that are described in this topic either separately or in combination, depending on your business requirements.</span></span> <span data-ttu-id="323e2-131">Puede diseñar varias plantillas de etiquetas de oleadas que funcionen en secuencia (como se ilustra en el escenario 3).</span><span class="sxs-lookup"><span data-stu-id="323e2-131">You can design several wave label templates that work in sequence (as illustrated in scenario 3).</span></span> <span data-ttu-id="323e2-132">Por ejemplo, puede usar el escenario 1 para imprimir etiquetas de cajas y el escenario 2 para imprimir etiquetas de pallets (si las pallets en existencias varían en tamaño y composición).</span><span class="sxs-lookup"><span data-stu-id="323e2-132">For example, you can use scenario 1 to print carton labels and scenario 2 to print pallet labels (if pallets in stock vary in size and composition).</span></span>

## <a name="turn-on-the-wave-label-printing-feature"></a><span data-ttu-id="323e2-133">Activar la característica de impresión de etiquetas de oleada</span><span class="sxs-lookup"><span data-stu-id="323e2-133">Turn on the Wave label printing feature</span></span>

<span data-ttu-id="323e2-134">Para poder usar la característica *Impresión de etiquetas de oleada* , debe estar activada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="323e2-134">Before you can use the *Wave label printing* feature, it must be turned on in your system.</span></span> <span data-ttu-id="323e2-135">Los administradores pueden usar el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="323e2-135">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="323e2-136">Allí, la característica se enumera de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="323e2-136">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="323e2-137">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="323e2-137">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="323e2-138">**Nombre de la característica:** *Impresión de etiquetas de oleada*</span><span class="sxs-lookup"><span data-stu-id="323e2-138">**Feature name:** *Wave label printing*</span></span>

## <a name="scenario-1-wave-label-printing-where-a-single-wave-label-is-generated"></a><span data-ttu-id="323e2-139">Escenario 1: impresión de etiquetas de oleada donde se genera una única etiqueta de oleada</span><span class="sxs-lookup"><span data-stu-id="323e2-139">Scenario 1: Wave label printing where a single wave label is generated</span></span>

<span data-ttu-id="323e2-140">Este escenario muestra cómo una empresa puede imprimir etiquetas de envío para un gran minorista que confirma automáticamente los recibos de los pedidos escaneando cada caja por separado.</span><span class="sxs-lookup"><span data-stu-id="323e2-140">This scenario shows how a company can print shipping labels for a large retailer that automatically confirms order receipts by scanning each carton separately.</span></span>

<span data-ttu-id="323e2-141">Este escenario muestra el flujo de extremo a extremo.</span><span class="sxs-lookup"><span data-stu-id="323e2-141">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="323e2-142">Hacer que los datos de demostración estén disponibles</span><span class="sxs-lookup"><span data-stu-id="323e2-142">Make demo data available</span></span>

<span data-ttu-id="323e2-143">Para seguir este escenario, los datos de demostración deben estar instalados y debe seleccionar la entidad jurídica **USMF**.</span><span class="sxs-lookup"><span data-stu-id="323e2-143">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-the-wave-label-method-is-available"></a><span data-ttu-id="323e2-144">Asegúrese de que el método de etiqueta de oleada esté disponible</span><span class="sxs-lookup"><span data-stu-id="323e2-144">Make sure that the wave label method is available</span></span>

<span data-ttu-id="323e2-145">Es posible que tenga que regenerar los métodos de proceso de oleada para que el método de impresión de etiquetas de oleadas esté disponible.</span><span class="sxs-lookup"><span data-stu-id="323e2-145">You might have to regenerate the wave process methods to make the wave label printing method available.</span></span>

1. <span data-ttu-id="323e2-146">Vaya a **Gestión de almacenes \> Configuración \> Oleadas \> Métodos de proceso de oleadas**.</span><span class="sxs-lookup"><span data-stu-id="323e2-146">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="323e2-147">Confirme que **waveLabelPrinting** está en la lista.</span><span class="sxs-lookup"><span data-stu-id="323e2-147">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="323e2-148">Si no está, seleccione **Regenerar métodos** en el Panel de acciones para agregarlo.</span><span class="sxs-lookup"><span data-stu-id="323e2-148">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>

### <a name="configure-a-wave-template"></a><span data-ttu-id="323e2-149">Configurar una plantilla de oleada</span><span class="sxs-lookup"><span data-stu-id="323e2-149">Configure a wave template</span></span>

<span data-ttu-id="323e2-150">Las plantillas de oleada le permiten vincular instancias específicas de métodos de oleada a una plantilla de etiqueta de oleada correspondiente.</span><span class="sxs-lookup"><span data-stu-id="323e2-150">Wave templates let you link specific instances of wave methods to a corresponding wave label template.</span></span>

1. <span data-ttu-id="323e2-151">Vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**.</span><span class="sxs-lookup"><span data-stu-id="323e2-151">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="323e2-152">Seleccione una plantilla, como **Plantilla predeterminada 62**.</span><span class="sxs-lookup"><span data-stu-id="323e2-152">Select a template, such as **62 Shipping Default**.</span></span>
1. <span data-ttu-id="323e2-153">En la ficha desplegable **Métodos** , mueva el método **Impresión de etiquetas de oleada** a la columna **Métodos seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="323e2-153">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
1. <span data-ttu-id="323e2-154">En la columna **Métodos seleccionados** , seleccione el método **Impresión de etiquetas de oleada** y establezca el campo **Código de paso de oleada** en *Etiqueta de impresión*.</span><span class="sxs-lookup"><span data-stu-id="323e2-154">In the **Selected methods** column, select the **Wave label printing** method, and set its **Wave step code** field to *PrintLabel*.</span></span> <span data-ttu-id="323e2-155">Para obtener más información sobre los códigos de pasos de oleadas, vea [Códigos de paso de oleada](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="323e2-155">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-a-wave-label-layout"></a><span data-ttu-id="323e2-156">Crear un diseño de etiqueta de oleada</span><span class="sxs-lookup"><span data-stu-id="323e2-156">Create a wave label layout</span></span>

<span data-ttu-id="323e2-157">El diseño de la etiqueta controla qué información se imprime en la etiqueta y cómo se dispone. Introduzca aquí el código ZPL que se envía a la impresora.</span><span class="sxs-lookup"><span data-stu-id="323e2-157">The label layout controls what information is printed on the label and how it's laid out. Here, you enter the ZPL code that is sent to the printer.</span></span>

1. <span data-ttu-id="323e2-158">Vaya a **Gestión de almacenes \> Configuración \> Ruta de documentos \> Diseño de etiquetas de oleada**.</span><span class="sxs-lookup"><span data-stu-id="323e2-158">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="323e2-159">Cree un registro que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="323e2-159">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="323e2-160">**Id. de diseño de etiqueta:** *Caja*</span><span class="sxs-lookup"><span data-stu-id="323e2-160">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="323e2-161">**Descripción:** *Caja (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="323e2-161">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="323e2-162">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="323e2-162">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="323e2-163">En el Panel de acciones, seleccione **Configuración de filas de etiquetas de oleadas**.</span><span class="sxs-lookup"><span data-stu-id="323e2-163">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="323e2-164">Aparece la página **Configuración de filas de etiquetas de oleadas**.</span><span class="sxs-lookup"><span data-stu-id="323e2-164">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="323e2-165">Aquí, puede configurar la parte dinámica de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="323e2-165">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="323e2-166">Agregue una fila con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="323e2-166">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="323e2-167">**Id. de fila:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="323e2-167">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="323e2-168">**Nombre de la tabla de filas:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="323e2-168">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="323e2-169">**Posición inicial de fila:** *0*</span><span class="sxs-lookup"><span data-stu-id="323e2-169">**Row start position:** *0*</span></span>

        <span data-ttu-id="323e2-170">Este campo define la posición vertical donde comenzará la fila en la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="323e2-170">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="323e2-171">**Alto de fila:** *0*</span><span class="sxs-lookup"><span data-stu-id="323e2-171">**Row height:** *0*</span></span>

        <span data-ttu-id="323e2-172">Este campo define el alto de cada fila (en puntos), conforme al estándar ZPL.</span><span class="sxs-lookup"><span data-stu-id="323e2-172">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="323e2-173">El alto de la fila es positivo para etiquetas horizontales y negativo para etiquetas verticales.</span><span class="sxs-lookup"><span data-stu-id="323e2-173">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="323e2-174">Como solo hay una fila en este ejemplo, el valor se puede establecer en *0* (cero).</span><span class="sxs-lookup"><span data-stu-id="323e2-174">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="323e2-175">**Filas por página:** *1*</span><span class="sxs-lookup"><span data-stu-id="323e2-175">**Rows per page:** *1*</span></span>

        <span data-ttu-id="323e2-176">Este campo define el número de filas que se pueden imprimir en cada etiqueta.</span><span class="sxs-lookup"><span data-stu-id="323e2-176">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="323e2-177">Esta configuración hará que se imprima una etiqueta ZPL independiente para cada registro en la tabla de etiquetas de oleada.</span><span class="sxs-lookup"><span data-stu-id="323e2-177">This setup will cause a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="323e2-178">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="323e2-178">Close the page.</span></span>
1. <span data-ttu-id="323e2-179">En el panel Acciones, seleccione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="323e2-179">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="323e2-180">En el cuadro de diálogo del editor de consultas, en la pestaña **Intervalo** , seleccione una fila que tenga los siguientes parámetros.</span><span class="sxs-lookup"><span data-stu-id="323e2-180">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="323e2-181">**Tabla:** *Lineas de trabajo*</span><span class="sxs-lookup"><span data-stu-id="323e2-181">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="323e2-182">**Tabla derivada:** *Líneas de trabajo*</span><span class="sxs-lookup"><span data-stu-id="323e2-182">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="323e2-183">**Campo:** *Tipo de trabajo*</span><span class="sxs-lookup"><span data-stu-id="323e2-183">**Field:** *Work type*</span></span>
    - <span data-ttu-id="323e2-184">**Criterios:** *Seleccionar*</span><span class="sxs-lookup"><span data-stu-id="323e2-184">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="323e2-185">Esta consulta garantiza que solo se imprimen líneas de trabajo de tipo recogida en la etiqueta y no en líneas de trabajo del tipo colocación.</span><span class="sxs-lookup"><span data-stu-id="323e2-185">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="323e2-186">Si desea imprimir el id. del conocimiento de embarque, en la pestaña **Combinaciones** , seleccione la tabla **Líneas de trabajo** y vincúlela a la tabla **Envíos**.</span><span class="sxs-lookup"><span data-stu-id="323e2-186">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="323e2-187">Cierre el cuadro de diálogo del editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="323e2-187">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="323e2-188">La ficha desplegable **Diseño de texto de impresora** tiene tres secciones donde puede escribir el código de la impresora: **Sección del encabezado** , **Sección del cuerpo** y **Sección del pie de página**.</span><span class="sxs-lookup"><span data-stu-id="323e2-188">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section** , **Body section** , and **Footer section**.</span></span> <span data-ttu-id="323e2-189">En la **Sección del encabezado** , en el campo **Encabezado de la etiqueta** , introduzca el código para el encabezado requerido.</span><span class="sxs-lookup"><span data-stu-id="323e2-189">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="323e2-190">Por ejemplo, si usa impresoras Zebra, puede usar el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="323e2-190">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. <span data-ttu-id="323e2-191">En la **Sección del cuerpo** , en el campo **Cuerpo de la etiqueta** , introduzca el código ZPL para el cuerpo requerido.</span><span class="sxs-lookup"><span data-stu-id="323e2-191">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="323e2-192">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="323e2-192">Here is an example.</span></span>

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. <span data-ttu-id="323e2-193">En la **Sección del cuerpo** , en el campo **Pie de página de la etiqueta** , introduzca el código ZPL para el pie de página requerido.</span><span class="sxs-lookup"><span data-stu-id="323e2-193">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="323e2-194">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="323e2-194">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="323e2-195">Esta configuración imprimirá una copia de cada etiqueta.</span><span class="sxs-lookup"><span data-stu-id="323e2-195">This setup will print one copy of each label.</span></span> <span data-ttu-id="323e2-196">Si necesita más copias (por ejemplo, una copia para cada lado del pallet), establezca el valor **n** para la sección **\^PQn** en el pie de página para el número requerido de copias.</span><span class="sxs-lookup"><span data-stu-id="323e2-196">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="323e2-197">Por ejemplo, para imprimir cuatro copias de cada etiqueta, especifique **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="323e2-197">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

<span data-ttu-id="323e2-198">Su etiqueta ya está lista para usarse.</span><span class="sxs-lookup"><span data-stu-id="323e2-198">Your label is now ready to use.</span></span>

### <a name="create-a-wave-label-type"></a><span data-ttu-id="323e2-199">Crear un tipo de etiqueta de oleada</span><span class="sxs-lookup"><span data-stu-id="323e2-199">Create a wave label type</span></span>

<span data-ttu-id="323e2-200">Los tipos de etiquetas de oleadas se utilizan para vincular plantillas de etiquetas de oleadas a una unidad en una unidad de líneas de grupo de secuencias.</span><span class="sxs-lookup"><span data-stu-id="323e2-200">Wave label types are used to link wave label templates to a unit on unit sequence group lines.</span></span>

1. <span data-ttu-id="323e2-201">Vaya a **Gestión de almacenes \> Configuración \> Ruta de documentos \> Tipos de etiquetas de oleadas**.</span><span class="sxs-lookup"><span data-stu-id="323e2-201">Go to **Warehouse management \> Setup \> Document routing \> Wave label types**.</span></span>
1. <span data-ttu-id="323e2-202">Agregue un tipo de etiqueta de oleada que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="323e2-202">Add a wave label type that has the following settings:</span></span>

    - <span data-ttu-id="323e2-203">**Tipo de etiqueta:** *Caja*</span><span class="sxs-lookup"><span data-stu-id="323e2-203">**Label type:** *Carton*</span></span>
    - <span data-ttu-id="323e2-204">**Descripción:** *Caja*</span><span class="sxs-lookup"><span data-stu-id="323e2-204">**Description:** *Carton*</span></span>

### <a name="set-up-unit-sequence-groups"></a><span data-ttu-id="323e2-205">Configurar grupos de secuencias de unidades</span><span class="sxs-lookup"><span data-stu-id="323e2-205">Set up unit sequence groups</span></span>

<span data-ttu-id="323e2-206">A continuación, configure el grupo de secuencia de unidades para el tipo de etiqueta de oleada.</span><span class="sxs-lookup"><span data-stu-id="323e2-206">Next, set up the unit sequence group for the wave label type.</span></span>

1. <span data-ttu-id="323e2-207">Vaya a **Gestión de almacenes \> Configuración \> Almacén \> Grupos de secuencias de unidades**.</span><span class="sxs-lookup"><span data-stu-id="323e2-207">Go to **Warehouse management \> Setup \> Warehouse \> Unit sequence groups**.</span></span>
1. <span data-ttu-id="323e2-208">Seleccione el grupo **Ea Box PL**.</span><span class="sxs-lookup"><span data-stu-id="323e2-208">Select the **Ea Box PL** group.</span></span>
1. <span data-ttu-id="323e2-209">En la línea **Caja** establezca el campo **Tipo de nivel de oleada** en *Caja*.</span><span class="sxs-lookup"><span data-stu-id="323e2-209">For the **Box** line, set the **Wave level type** field to *Carton*.</span></span>

### <a name="create-a-wave-label-template"></a><span data-ttu-id="323e2-210">Crear una plantilla de etiqueta de oleada</span><span class="sxs-lookup"><span data-stu-id="323e2-210">Create a wave label template</span></span>

<span data-ttu-id="323e2-211">A continuación, cree la plantilla de etiqueta de oleada para el tipo de etiqueta de oleada.</span><span class="sxs-lookup"><span data-stu-id="323e2-211">Next, create the wave label template for the wave label type.</span></span>

1. <span data-ttu-id="323e2-212">Vaya a **Gestión de almacenes \> Configuración \> Ruta de documentos \> Plantillas de etiqueta de oleada**.</span><span class="sxs-lookup"><span data-stu-id="323e2-212">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="323e2-213">Agregue una plantilla de nivel de oleada y establezca los siguientes valores en el encabezado:</span><span class="sxs-lookup"><span data-stu-id="323e2-213">Add a wave level template, and set the following values in the header:</span></span>

    - <span data-ttu-id="323e2-214">**Nombre de plantilla de etiqueta:** *Etiquetas de caja*</span><span class="sxs-lookup"><span data-stu-id="323e2-214">**Label template name:** *Carton labels*</span></span>
    - <span data-ttu-id="323e2-215">**Descripción:** *Etiquetas de caja*</span><span class="sxs-lookup"><span data-stu-id="323e2-215">**Description:** *Carton labels*</span></span>
    - <span data-ttu-id="323e2-216">**Código de paso de oleada:** *EtiquetaImpresión*</span><span class="sxs-lookup"><span data-stu-id="323e2-216">**Wave step code:** *PrintLabel*</span></span>
    - <span data-ttu-id="323e2-217">**Almacén** : *62*</span><span class="sxs-lookup"><span data-stu-id="323e2-217">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="323e2-218">En la ficha desplegable **General** , establezca el campo **Tipo de etiqueta de oleada** en *Caja de cartón*.</span><span class="sxs-lookup"><span data-stu-id="323e2-218">On the **General** FastTab, set the **Wave label type** field to *Carton*.</span></span>
1. <span data-ttu-id="323e2-219">En la ficha desplegable **Detalles de plantilla de etiqueta de oleada** , agregue una nueva fila que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="323e2-219">On the **Wave label template details** FastTab, add a new row that has the following settings:</span></span>

    - <span data-ttu-id="323e2-220">**Id. de diseño de etiqueta:** *Caja*</span><span class="sxs-lookup"><span data-stu-id="323e2-220">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="323e2-221">**Nombre de la impresora:** seleccione una impresora ZPL adecuada.</span><span class="sxs-lookup"><span data-stu-id="323e2-221">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="323e2-222">**Ejecutar consulta:** *Sí* (Esta configuración es opcional, pero se recomienda para un rendimiento óptimo).</span><span class="sxs-lookup"><span data-stu-id="323e2-222">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="323e2-223">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="323e2-223">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="323e2-224">Opcional: si está configurando un diseño de etiqueta específico del cliente, debe crear una consulta para encontrar la cuenta del cliente.</span><span class="sxs-lookup"><span data-stu-id="323e2-224">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="323e2-225">En la ficha desplegable **Detalles de plantilla de etiqueta de oleada** , seleccione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="323e2-225">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="323e2-226">A continuación, agregue una fila que tenga la siguiente configuración dentro de la pestaña **Intervalo** , en el cuadro de diálogo del editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="323e2-226">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="323e2-227">**Tabla:** *Envíos*</span><span class="sxs-lookup"><span data-stu-id="323e2-227">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="323e2-228">**Tabla derivada:** *Envíos*</span><span class="sxs-lookup"><span data-stu-id="323e2-228">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="323e2-229">**Campo:** *Número de cuenta*</span><span class="sxs-lookup"><span data-stu-id="323e2-229">**Field:** *Account number*</span></span>
    - <span data-ttu-id="323e2-230">**Criterios** introduzca el número de cuenta del cliente pertinente.</span><span class="sxs-lookup"><span data-stu-id="323e2-230">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="323e2-231">Cuando haya terminado, seleccione **Aceptar** para cerrar el cuadro de diálogo del editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="323e2-231">When you've finished, select **OK** to close the query editor dialog box.</span></span>

1. <span data-ttu-id="323e2-232">En el panel de acciones, seleccione **Editar consulta** para abrir el cuadro de diálogo del editor de consultas para la plantilla de etiqueta completa.</span><span class="sxs-lookup"><span data-stu-id="323e2-232">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="323e2-233">En el cuadro de diálogo del editor de consultas, en la pestaña **Ordenación** , seleccione una fila que tenga la siguiente configuración.</span><span class="sxs-lookup"><span data-stu-id="323e2-233">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="323e2-234">**Tabla:** *Lineas de trabajo*</span><span class="sxs-lookup"><span data-stu-id="323e2-234">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="323e2-235">**Tabla derivada:** *Líneas de trabajo*</span><span class="sxs-lookup"><span data-stu-id="323e2-235">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="323e2-236">**Campo:** *id. de línea de carga de referencia (id. de registro)*</span><span class="sxs-lookup"><span data-stu-id="323e2-236">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="323e2-237">**Dirección de búsqueda:** *Ascendente*</span><span class="sxs-lookup"><span data-stu-id="323e2-237">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="323e2-238">Seleccione **Aceptar** para cerrar el cuadro de diálogo del editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="323e2-238">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="323e2-239">Un cuadro de mensaje le solicitará que confirme la operación de restablecimiento de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="323e2-239">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="323e2-240">Seleccione **Sí** para continuar.</span><span class="sxs-lookup"><span data-stu-id="323e2-240">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="323e2-241">En el panel de acciones, seleccione **Grupo de plantillas de etiquetas de oleadas**.</span><span class="sxs-lookup"><span data-stu-id="323e2-241">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="323e2-242">En el cuadro de diálogo **Grupo de plantillas de etiquetas de oleadas** , seleccione la fila donde el campo **Nombre del campo de referencia** está establecido en *Id. de línea de carga de referencia* y luego seleccione la casilla **Id. de compilación de etiqueta** de esta fila.</span><span class="sxs-lookup"><span data-stu-id="323e2-242">In the **Wave label template group** dialog box, select the row where the **Reference field name** field is set to *Reference load line id* , and then select the **Label build ID** check box for this row.</span></span>

    > [!NOTE]
    > <span data-ttu-id="323e2-243">Esta configuración creará una secuencia de etiquetas ("Caja 1 de X") por línea de carga a lo largo de la oleada, con independencia de la configuración de agrupación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="323e2-243">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="323e2-244">Esta secuencia de etiquetas se puede imprimir en el diseño de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="323e2-244">This label sequence can be printed on the label layout.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="323e2-245">Configurar extensiones de secuencias numéricas</span><span class="sxs-lookup"><span data-stu-id="323e2-245">Configure number sequence extensions</span></span>

<span data-ttu-id="323e2-246">Las extensiones de secuencias numéricas controlan el cumplimiento GS1 de secuencias numéricas específicas.</span><span class="sxs-lookup"><span data-stu-id="323e2-246">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="323e2-247">Esta configuración es opcional para el escenario actual.</span><span class="sxs-lookup"><span data-stu-id="323e2-247">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="323e2-248">Para obtener más información e instrucciones de configuración, consulte [Configurar extensiones de secuencias numéricas](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="323e2-248">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="323e2-249">Crear un pedido de ventas y liberarlo en el almacén</span><span class="sxs-lookup"><span data-stu-id="323e2-249">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="323e2-250">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="323e2-250">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="323e2-251">Cree un pedido de ventas con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="323e2-251">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="323e2-252">**Cuenta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="323e2-252">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="323e2-253">**Almacén** : *62*</span><span class="sxs-lookup"><span data-stu-id="323e2-253">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="323e2-254">Agregue dos líneas de pedidos de ventas que tengan la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="323e2-254">Add two sales order lines that have the following settings:</span></span>

    - <span data-ttu-id="323e2-255">Línea de pedido de ventas 1:</span><span class="sxs-lookup"><span data-stu-id="323e2-255">Sales order line 1:</span></span>

        - <span data-ttu-id="323e2-256">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="323e2-256">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="323e2-257">**Cantidad:** *9024*</span><span class="sxs-lookup"><span data-stu-id="323e2-257">**Quantity:** *9024*</span></span>
        - <span data-ttu-id="323e2-258">**Unidad:** *ea* (9024 ea = 376 Caja = 47 PL)</span><span class="sxs-lookup"><span data-stu-id="323e2-258">**Unit:** *ea* (9024 ea = 376 Box = 47 PL)</span></span>

    - <span data-ttu-id="323e2-259">Línea de pedido de ventas 2:</span><span class="sxs-lookup"><span data-stu-id="323e2-259">Sales order line 2:</span></span>

        - <span data-ttu-id="323e2-260">**Código de artículo:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="323e2-260">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="323e2-261">**Cantidad:** *9016*</span><span class="sxs-lookup"><span data-stu-id="323e2-261">**Quantity:** *9016*</span></span>
        - <span data-ttu-id="323e2-262">**Unidad:** *ea* (9016 ea = 322 Caja = 46 PL)</span><span class="sxs-lookup"><span data-stu-id="323e2-262">**Unit:** *ea* (9016 ea = 322 Box = 46 PL)</span></span>

    > [!NOTE]
    > <span data-ttu-id="323e2-263">Los artículos y cantidades que se proporcionan aquí son solo ejemplos.</span><span class="sxs-lookup"><span data-stu-id="323e2-263">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="323e2-264">Deben usar el grupo de secuencias de unidades que ha definido anteriormente, las conversiones de unidades adecuadas de *ea* a *Caja* a *PL* deben definirse para ellas, y deben tener existencias en el almacén *62*.</span><span class="sxs-lookup"><span data-stu-id="323e2-264">They must use the unit sequence group that you defined earlier, appropriate unit conversions from *ea* to *Box* to *PL* must be defined for them, and they must have stock in warehouse *62*.</span></span> <span data-ttu-id="323e2-265">Para más información, consulte [Directivas de unidad de medida y de existencias](unit-measure-stocking-policies.md).</span><span class="sxs-lookup"><span data-stu-id="323e2-265">For more information, see [Unit of measure and stocking policies](unit-measure-stocking-policies.md).</span></span>

1. <span data-ttu-id="323e2-266">Seleccione la línea de pedido de ventas 1.</span><span class="sxs-lookup"><span data-stu-id="323e2-266">Select sales order line 1.</span></span> <span data-ttu-id="323e2-267">A continuación, en la sección **Línea de pedido de ventas** , en el menú **Inventario** , seleccione **Reservas**.</span><span class="sxs-lookup"><span data-stu-id="323e2-267">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="323e2-268">En la página **Reserva** , en el panel de acciones, seleccione **Reservar lote** y después cierre la página.</span><span class="sxs-lookup"><span data-stu-id="323e2-268">On the **Reservation** page, on the Action Pane, select **Reserve lot** , and then close the page.</span></span>
1. <span data-ttu-id="323e2-269">Repita los pasos 4 y 5 para la línea de pedido de ventas 2.</span><span class="sxs-lookup"><span data-stu-id="323e2-269">Repeat steps 4 and 5 for sales order line 2.</span></span>
1. <span data-ttu-id="323e2-270">En el panel de acciones, en la pestaña **Almacén** , seleccione **Liberar al almacén**.</span><span class="sxs-lookup"><span data-stu-id="323e2-270">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="323e2-271">Se producen los eventos siguientes:</span><span class="sxs-lookup"><span data-stu-id="323e2-271">The following events occur:</span></span>

    - <span data-ttu-id="323e2-272">El sistema procesa el envío creado utilizando la plantilla que incluye el paso de impresión de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="323e2-272">The system processes the created shipment by using the template that includes the label printing step.</span></span> <span data-ttu-id="323e2-273">El diseño de la etiqueta se usará para definir el formato de la etiqueta y el resultado será una etiqueta impresa en la impresora que está seleccionada en la plantilla de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="323e2-273">The label layout will be used to define the format of the label, and the result will be a label that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="323e2-274">Las etiquetas de oleadas se generan y se imprimen.</span><span class="sxs-lookup"><span data-stu-id="323e2-274">Wave labels are generated and printed.</span></span> <span data-ttu-id="323e2-275">El número de etiquetas será igual al número de cajas (en este ejemplo, 376 etiquetas de cajas para la línea 1 y 322 etiquetas de cajas para la línea 2).</span><span class="sxs-lookup"><span data-stu-id="323e2-275">The number of labels will equal the number of cartons (in this example, 376 Box labels for line 1 and 322 Box labels for line 2).</span></span>
    - <span data-ttu-id="323e2-276">Se genera un nuevo id. de conocimiento de embarque para los envíos.</span><span class="sxs-lookup"><span data-stu-id="323e2-276">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="323e2-277">Si ha configurado las extensiones de secuencias numéricas, los id. de etiquetas de oleadas seguirán el formato numérico **SSCC-18**.</span><span class="sxs-lookup"><span data-stu-id="323e2-277">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="323e2-278">Puede ver y reimprimir etiquetas de oleada desde las siguientes páginas.</span><span class="sxs-lookup"><span data-stu-id="323e2-278">You can view and reprint wave labels from the following pages.</span></span> <span data-ttu-id="323e2-279">En el panel de acciones de cada página, en la pestaña **Envíos** del grupo **Información relacionada** , seleccione **Etiquetas de oleada**.</span><span class="sxs-lookup"><span data-stu-id="323e2-279">On the Action Pane of each page, on the **Shipments** tab, in the **Related information** group, select **Wave labels**.</span></span>

- <span data-ttu-id="323e2-280">Todos los envíos \> Detalles del envío</span><span class="sxs-lookup"><span data-stu-id="323e2-280">All shipments \> Shipment details</span></span>
- <span data-ttu-id="323e2-281">Todas las cargas \> Detalles de la carga</span><span class="sxs-lookup"><span data-stu-id="323e2-281">All loads \> Load details</span></span>
- <span data-ttu-id="323e2-282">Todas las oleadas</span><span class="sxs-lookup"><span data-stu-id="323e2-282">All waves</span></span>
- <span data-ttu-id="323e2-283">Etiquetas de oleadas</span><span class="sxs-lookup"><span data-stu-id="323e2-283">Wave labels</span></span>
- <span data-ttu-id="323e2-284">Historial de etiquetas de oleada</span><span class="sxs-lookup"><span data-stu-id="323e2-284">Wave label history</span></span>

## <a name="scenario-2-wave-label-printing-for-containerization-without-wave-label-records"></a><span data-ttu-id="323e2-285">Escenario 2: impresión de etiquetas de oleadas para la creación de contenedores (sin registros de etiquetas de oleadas)</span><span class="sxs-lookup"><span data-stu-id="323e2-285">Scenario 2: Wave label printing for containerization (without wave label records)</span></span>

<span data-ttu-id="323e2-286">Este escenario le permite imprimir etiquetas de oleadas cuando usa la creación de contenedores para dividir automáticamente los artículos en cajas y, por tanto, no requieren un registro de etiqueta de oleada.</span><span class="sxs-lookup"><span data-stu-id="323e2-286">This scenario lets you print wave labels when you use containerization to automatically split items into cartons and therefore don't require a wave label record.</span></span> <span data-ttu-id="323e2-287">En este caso, el id. de contenedor actúa como un marcador de posición para el SSCC.</span><span class="sxs-lookup"><span data-stu-id="323e2-287">In this case, the container ID acts as a placeholder for the SSCC.</span></span>

<span data-ttu-id="323e2-288">Estas son las diferencias principales entre este escenario y el escenario 1:</span><span class="sxs-lookup"><span data-stu-id="323e2-288">Here are the main differences between this scenario and scenario 1:</span></span>

- <span data-ttu-id="323e2-289">**Plantillas de etiquetas de oleadas:** no seleccionará un tipo de etiqueta de oleada en la plantilla de etiqueta de oleada, y no necesitará una agrupación de compilaciones de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="323e2-289">**Wave label templates:** You won't select a wave label type on the wave label template, and you won't require a label build grouping.</span></span> <span data-ttu-id="323e2-290">De lo contrario, configurará la plantilla de etiqueta de oleada y la vinculará a la plantilla de oleada de la misma manera que se describe en el escenario 1.</span><span class="sxs-lookup"><span data-stu-id="323e2-290">Otherwise, you will configure the wave label template and link to the wave template in the same way that is described in scenario 1.</span></span> <span data-ttu-id="323e2-291">Debe dejar el tipo de etiqueta de oleada en blanco para evitar que se generen etiquetas de oleadas.</span><span class="sxs-lookup"><span data-stu-id="323e2-291">You must leave the wave label type blank to prevent wave labels from being generated.</span></span>
- <span data-ttu-id="323e2-292">**Diseños de etiquetas de oleadas:** establecerá la configuración de filas de diseño de etiquetas de oleadas para líneas de trabajo en lugar de registros de etiquetas de oleadas.</span><span class="sxs-lookup"><span data-stu-id="323e2-292">**Wave label layouts:** You will configure the wave label layout row settings for work lines instead of wave label records.</span></span> <span data-ttu-id="323e2-293">Debe establecer la configuración de filas para el diseño de la etiqueta utilizando la tabla **WHSWorkLine** en lugar de la tabla **WHSWaveLabel**.</span><span class="sxs-lookup"><span data-stu-id="323e2-293">You must configure the row setting for the label layout by using the **WHSWorkLine** table instead of the **WHSWaveLabel** table.</span></span> <span data-ttu-id="323e2-294">La configuración **Filas por página** controla el número de filas que tendrá la sección del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="323e2-294">The **Rows per page** setting controls the number of rows that the body section will have.</span></span> 

<span data-ttu-id="323e2-295">Esta configuración también es adecuada para escenarios de negocios en los que se empaquetan múltiples artículos diferentes en una caja etiquetada o en un pallet, y este proceso de empaquetado se puede definir por creación de trabajo (por ejemplo, trabajo que se agrupa por envío).</span><span class="sxs-lookup"><span data-stu-id="323e2-295">This configuration is also suitable for business scenarios where multiple different items are packed into one labeled box or into a pallet, and this packing process can be defined by work creation (for example, work that is grouped by shipment).</span></span>

<span data-ttu-id="323e2-296">Este escenario muestra el flujo de extremo a extremo.</span><span class="sxs-lookup"><span data-stu-id="323e2-296">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="323e2-297">Hacer que los datos de demostración estén disponibles</span><span class="sxs-lookup"><span data-stu-id="323e2-297">Make demo data available</span></span>

<span data-ttu-id="323e2-298">Para seguir este escenario, los datos de demostración deben estar instalados y debe seleccionar la entidad jurídica **USMF**.</span><span class="sxs-lookup"><span data-stu-id="323e2-298">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-the-wave-label-method-is-available"></a><span data-ttu-id="323e2-299">Asegúrese de que el método de etiqueta de oleada esté disponible</span><span class="sxs-lookup"><span data-stu-id="323e2-299">Make sure that the wave label method is available</span></span>

<span data-ttu-id="323e2-300">Es posible que tenga que regenerar los métodos de proceso de oleada para que el método de impresión de etiquetas de oleadas esté disponible.</span><span class="sxs-lookup"><span data-stu-id="323e2-300">You might have to regenerate the wave process methods to make the wave label printing method available.</span></span>

1. <span data-ttu-id="323e2-301">Vaya a **Gestión de almacenes \> Configuración \> Oleadas \> Métodos de proceso de oleadas**.</span><span class="sxs-lookup"><span data-stu-id="323e2-301">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="323e2-302">Confirme que **waveLabelPrinting** está en la lista.</span><span class="sxs-lookup"><span data-stu-id="323e2-302">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="323e2-303">Si no está, seleccione **Regenerar métodos** en el Panel de acciones para agregarlo.</span><span class="sxs-lookup"><span data-stu-id="323e2-303">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="323e2-304">Configurar una plantilla de oleada</span><span class="sxs-lookup"><span data-stu-id="323e2-304">Set up a wave template</span></span>

<span data-ttu-id="323e2-305">Las plantillas de oleada le permiten vincular instancias específicas de métodos de oleada a una plantilla de etiqueta de oleada correspondiente.</span><span class="sxs-lookup"><span data-stu-id="323e2-305">Wave templates let you link specific instances of wave methods to a corresponding wave label template.</span></span>

1. <span data-ttu-id="323e2-306">Vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**.</span><span class="sxs-lookup"><span data-stu-id="323e2-306">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="323e2-307">Seleccione una plantilla como **63 Creación de contenedores**.</span><span class="sxs-lookup"><span data-stu-id="323e2-307">Select a template, such as **63 Containerization**.</span></span>
1. <span data-ttu-id="323e2-308">En la ficha desplegable **Métodos** , mueva el método **Impresión de etiquetas de oleada** a la columna **Métodos seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="323e2-308">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
1. <span data-ttu-id="323e2-309">En la columna **Métodos seleccionados** , seleccione el método **Impresión de etiquetas de oleada** y establezca el campo **Código de paso de oleada** en *Etiqueta de impresión*.</span><span class="sxs-lookup"><span data-stu-id="323e2-309">In the **Selected methods** column, select the **Wave label printing** method, and set its **Wave step code** field to *PrintLabel*.</span></span> <span data-ttu-id="323e2-310">Para obtener más información sobre los códigos de pasos de oleadas, vea [Códigos de paso de oleada](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="323e2-310">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-a-wave-label-layout"></a><span data-ttu-id="323e2-311">Crear un diseño de etiqueta de oleada</span><span class="sxs-lookup"><span data-stu-id="323e2-311">Create a wave label layout</span></span>

1. <span data-ttu-id="323e2-312">Vaya a **Gestión de almacenes \> Configuración \> Ruta de documentos \> Diseño de etiquetas de oleada**.</span><span class="sxs-lookup"><span data-stu-id="323e2-312">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="323e2-313">Cree un registro que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="323e2-313">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="323e2-314">**Id. de diseño de etiqueta:** *Caja*</span><span class="sxs-lookup"><span data-stu-id="323e2-314">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="323e2-315">**Descripción:** *Caja (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="323e2-315">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="323e2-316">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="323e2-316">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="323e2-317">En el Panel de acciones, seleccione **Configuración de filas de etiquetas de oleadas**.</span><span class="sxs-lookup"><span data-stu-id="323e2-317">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="323e2-318">Aparece la página **Configuración de filas de etiquetas de oleadas**.</span><span class="sxs-lookup"><span data-stu-id="323e2-318">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="323e2-319">Aquí, puede configurar la parte dinámica de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="323e2-319">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="323e2-320">Agregue una fila con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="323e2-320">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="323e2-321">**Id de fila:** *WorkLine*</span><span class="sxs-lookup"><span data-stu-id="323e2-321">**Row Id:** *WorkLine*</span></span>
    - <span data-ttu-id="323e2-322">**Nombre de la tabla de filas:** *WHSWorkLine*</span><span class="sxs-lookup"><span data-stu-id="323e2-322">**Row table name:** *WHSWorkLine*</span></span>
    - <span data-ttu-id="323e2-323">**Posición inicial de fila:** *500*</span><span class="sxs-lookup"><span data-stu-id="323e2-323">**Row start position:** *500*</span></span>

        <span data-ttu-id="323e2-324">Este campo define la posición vertical donde comenzará la fila en la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="323e2-324">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="323e2-325">**Alto de fila:** *-50*</span><span class="sxs-lookup"><span data-stu-id="323e2-325">**Row height:** *-50*</span></span>

        <span data-ttu-id="323e2-326">Este campo define el alto de cada fila.</span><span class="sxs-lookup"><span data-stu-id="323e2-326">This field defines the height of each row.</span></span> <span data-ttu-id="323e2-327">El alto de la fila es positivo para etiquetas horizontales y negativo para etiquetas verticales.</span><span class="sxs-lookup"><span data-stu-id="323e2-327">The row height is positive for horizontal labels and negative for vertical labels.</span></span>

    - <span data-ttu-id="323e2-328">**Filas por página:** *5*</span><span class="sxs-lookup"><span data-stu-id="323e2-328">**Rows per page:** *5*</span></span>

        <span data-ttu-id="323e2-329">Este campo define el número de filas que se pueden imprimir en cada etiqueta.</span><span class="sxs-lookup"><span data-stu-id="323e2-329">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="323e2-330">Esta configuración imprimirá varias etiquetas ZPL por trabajo, donde cada página puede contener hasta cinco líneas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="323e2-330">This setup will print several ZPL labels per work, where each page can hold up to five work lines.</span></span> <span data-ttu-id="323e2-331">Por ejemplo, si se imprime una etiqueta para un contenedor que tiene 12 líneas, se imprimirán tres etiquetas.</span><span class="sxs-lookup"><span data-stu-id="323e2-331">For example, if a label is printed for a container that has 12 lines, three labels will be printed.</span></span> <span data-ttu-id="323e2-332">Si desea imprimir una etiqueta independiente para cada línea de selección, establezca este valor en *1*.</span><span class="sxs-lookup"><span data-stu-id="323e2-332">If you want to print a separate label for each pick line, set this value to *1*.</span></span>

1. <span data-ttu-id="323e2-333">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="323e2-333">Close the page.</span></span>
1. <span data-ttu-id="323e2-334">En el panel Acciones, seleccione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="323e2-334">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="323e2-335">En el cuadro de diálogo del editor de consultas, en la pestaña **Intervalo** , seleccione una fila que tenga los siguientes parámetros.</span><span class="sxs-lookup"><span data-stu-id="323e2-335">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="323e2-336">**Tabla:** *Lineas de trabajo*</span><span class="sxs-lookup"><span data-stu-id="323e2-336">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="323e2-337">**Tabla derivada:** *Líneas de trabajo*</span><span class="sxs-lookup"><span data-stu-id="323e2-337">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="323e2-338">**Campo:** *Tipo de trabajo*</span><span class="sxs-lookup"><span data-stu-id="323e2-338">**Field:** *Work type*</span></span>
    - <span data-ttu-id="323e2-339">**Criterios:** *Seleccionar*</span><span class="sxs-lookup"><span data-stu-id="323e2-339">**Criteria:** *Pick*</span></span>

1. <span data-ttu-id="323e2-340">Si desea imprimir el id. del conocimiento de embarque, en la pestaña **Combinaciones** , seleccione la tabla **Líneas de trabajo** y vincúlela a la tabla **Envíos**.</span><span class="sxs-lookup"><span data-stu-id="323e2-340">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="323e2-341">Cierre el cuadro de diálogo del editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="323e2-341">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="323e2-342">La ficha desplegable **Diseño de texto de impresora** tiene tres secciones donde puede escribir el código de la impresora: **Sección del encabezado** , **Sección del cuerpo** y **Sección del pie de página**.</span><span class="sxs-lookup"><span data-stu-id="323e2-342">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section** , **Body section** , and **Footer section**.</span></span> <span data-ttu-id="323e2-343">En la **Sección del encabezado** , en el campo **Encabezado de la etiqueta** , introduzca el código para el encabezado requerido.</span><span class="sxs-lookup"><span data-stu-id="323e2-343">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="323e2-344">Por ejemplo, si usa impresoras Zebra, puede usar el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="323e2-344">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkTable.ContainerId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. <span data-ttu-id="323e2-345">En la **Sección del cuerpo** , en el campo **Cuerpo de la etiqueta** , introduzca el código ZPL para el cuerpo requerido.</span><span class="sxs-lookup"><span data-stu-id="323e2-345">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="323e2-346">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="323e2-346">Here is an example.</span></span>

    ```plaintext
    <Row name="WorkLine">
    <Heading>
    //Optional heading for section of rows
    </Heading>
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWorkLine.ItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWorkLine.QtyWork$ ^FS
    </Row>
    ```

1. <span data-ttu-id="323e2-347">En la **Sección del cuerpo** , en el campo **Pie de página de la etiqueta** , introduzca el código ZPL para el pie de página requerido.</span><span class="sxs-lookup"><span data-stu-id="323e2-347">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="323e2-348">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="323e2-348">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="323e2-349">Esta configuración imprimirá una copia de cada etiqueta.</span><span class="sxs-lookup"><span data-stu-id="323e2-349">This setup will print one copy of each label.</span></span> <span data-ttu-id="323e2-350">Si necesita más copias (por ejemplo, una copia para cada lado del pallet), establezca el valor **n** para la sección **\^PQn** en el pie de página para el número requerido de copias.</span><span class="sxs-lookup"><span data-stu-id="323e2-350">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="323e2-351">Por ejemplo, para imprimir cuatro copias de cada etiqueta, especifique **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="323e2-351">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

<span data-ttu-id="323e2-352">Su etiqueta ya está lista para usarse.</span><span class="sxs-lookup"><span data-stu-id="323e2-352">Your label is now ready to use.</span></span>

### <a name="create-a-wave-label-template"></a><span data-ttu-id="323e2-353">Crear una plantilla de etiqueta de oleada</span><span class="sxs-lookup"><span data-stu-id="323e2-353">Create a wave label template</span></span>

1. <span data-ttu-id="323e2-354">Vaya a **Gestión de almacenes \> Configuración \> Ruta de documentos \> Plantillas de etiqueta de oleada**.</span><span class="sxs-lookup"><span data-stu-id="323e2-354">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="323e2-355">Agregue una plantilla de nivel de oleada y establezca los siguientes valores en el encabezado:</span><span class="sxs-lookup"><span data-stu-id="323e2-355">Add a wave level template, and set the following values in the header:</span></span>

    - <span data-ttu-id="323e2-356">**Nombre de plantilla de etiqueta:** *Etiquetas de contenedor*</span><span class="sxs-lookup"><span data-stu-id="323e2-356">**Label template name:** *Container labels*</span></span>
    - <span data-ttu-id="323e2-357">**Descripción:** *Etiquetas de contenedores*</span><span class="sxs-lookup"><span data-stu-id="323e2-357">**Description:** *Container labels*</span></span>
    - <span data-ttu-id="323e2-358">**Código de paso de oleada:** *EtiquetaImpresión*</span><span class="sxs-lookup"><span data-stu-id="323e2-358">**Wave step code:** *PrintLabel*</span></span>
    - <span data-ttu-id="323e2-359">**Almacén** : *63*</span><span class="sxs-lookup"><span data-stu-id="323e2-359">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="323e2-360">En la ficha desplegable **Detalles de plantillas de etiquetas de oleadas** , agregue una fila que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="323e2-360">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="323e2-361">**Id. de diseño de etiquetas:** *Contenedor*</span><span class="sxs-lookup"><span data-stu-id="323e2-361">**Label layout ID:** *Container*</span></span>
    - <span data-ttu-id="323e2-362">**Nombre de la impresora:** seleccione una impresora ZPL adecuada.</span><span class="sxs-lookup"><span data-stu-id="323e2-362">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="323e2-363">**Ejecutar consulta:** *Sí* (Esta configuración es opcional, pero se recomienda para un rendimiento óptimo).</span><span class="sxs-lookup"><span data-stu-id="323e2-363">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="323e2-364">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="323e2-364">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="323e2-365">Opcional: si está configurando un diseño de etiqueta específico del cliente, debe crear una consulta para encontrar la cuenta del cliente.</span><span class="sxs-lookup"><span data-stu-id="323e2-365">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="323e2-366">En la ficha desplegable **Detalles de plantilla de etiqueta de oleada** , seleccione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="323e2-366">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="323e2-367">A continuación, agregue una fila que tenga la siguiente configuración dentro de la pestaña **Intervalo** , en el cuadro de diálogo del editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="323e2-367">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="323e2-368">**Tabla:** *Envíos*</span><span class="sxs-lookup"><span data-stu-id="323e2-368">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="323e2-369">**Tabla derivada:** *Envíos*</span><span class="sxs-lookup"><span data-stu-id="323e2-369">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="323e2-370">**Campo:** *Número de cuenta*</span><span class="sxs-lookup"><span data-stu-id="323e2-370">**Field:** *Account number*</span></span>
    - <span data-ttu-id="323e2-371">**Criterios** introduzca el número de cuenta del cliente pertinente.</span><span class="sxs-lookup"><span data-stu-id="323e2-371">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="323e2-372">Cuando haya terminado, seleccione **Aceptar** para cerrar el cuadro de diálogo del editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="323e2-372">When you've finished, select **OK** to close the query editor dialog box.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="323e2-373">Configurar extensiones de secuencias numéricas</span><span class="sxs-lookup"><span data-stu-id="323e2-373">Configure number sequence extensions</span></span>

<span data-ttu-id="323e2-374">Las extensiones de secuencias numéricas controlan el cumplimiento GS1 de secuencias numéricas específicas.</span><span class="sxs-lookup"><span data-stu-id="323e2-374">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="323e2-375">Esta configuración es opcional para el escenario actual.</span><span class="sxs-lookup"><span data-stu-id="323e2-375">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="323e2-376">Para obtener más información e instrucciones de configuración, consulte [Configurar extensiones de secuencias numéricas](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="323e2-376">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="323e2-377">Crear un pedido de ventas y liberarlo en el almacén</span><span class="sxs-lookup"><span data-stu-id="323e2-377">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="323e2-378">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="323e2-378">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="323e2-379">Cree un pedido de ventas con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="323e2-379">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="323e2-380">**Cuenta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="323e2-380">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="323e2-381">**Almacén** : *63*</span><span class="sxs-lookup"><span data-stu-id="323e2-381">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="323e2-382">Agregar cinco líneas de pedido de ventas:</span><span class="sxs-lookup"><span data-stu-id="323e2-382">Add five sales order lines:</span></span>

    - <span data-ttu-id="323e2-383">Línea de pedido de ventas 1:</span><span class="sxs-lookup"><span data-stu-id="323e2-383">Sales order line 1:</span></span>

        - <span data-ttu-id="323e2-384">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="323e2-384">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="323e2-385">**Cantidad:** *10*</span><span class="sxs-lookup"><span data-stu-id="323e2-385">**Quantity:** *10*</span></span>

    - <span data-ttu-id="323e2-386">Línea de pedido de ventas 2:</span><span class="sxs-lookup"><span data-stu-id="323e2-386">Sales order line 2:</span></span>

        - <span data-ttu-id="323e2-387">**Código de artículo:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="323e2-387">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="323e2-388">**Cantidad:** *20*</span><span class="sxs-lookup"><span data-stu-id="323e2-388">**Quantity:** *20*</span></span>

    - <span data-ttu-id="323e2-389">Línea de pedido de ventas 3:</span><span class="sxs-lookup"><span data-stu-id="323e2-389">Sales order line 3:</span></span>

        - <span data-ttu-id="323e2-390">**Código de artículo:** *L0006*</span><span class="sxs-lookup"><span data-stu-id="323e2-390">**Item number:** *L0006*</span></span>
        - <span data-ttu-id="323e2-391">**Cantidad:** *20*</span><span class="sxs-lookup"><span data-stu-id="323e2-391">**Quantity:** *20*</span></span>

    - <span data-ttu-id="323e2-392">Línea de pedido de ventas 4:</span><span class="sxs-lookup"><span data-stu-id="323e2-392">Sales order line 4:</span></span>

        - <span data-ttu-id="323e2-393">**Código de artículo:** *L0100*</span><span class="sxs-lookup"><span data-stu-id="323e2-393">**Item number:** *L0100*</span></span>
        - <span data-ttu-id="323e2-394">**Cantidad:** *40*</span><span class="sxs-lookup"><span data-stu-id="323e2-394">**Quantity:** *40*</span></span>

    - <span data-ttu-id="323e2-395">Línea de pedido de ventas 5:</span><span class="sxs-lookup"><span data-stu-id="323e2-395">Sales order line 5:</span></span>

        - <span data-ttu-id="323e2-396">**Código de artículo:** *L0101*</span><span class="sxs-lookup"><span data-stu-id="323e2-396">**Item number:** *L0101*</span></span>
        - <span data-ttu-id="323e2-397">**Cantidad:** *50*</span><span class="sxs-lookup"><span data-stu-id="323e2-397">**Quantity:** *50*</span></span>

    > [!NOTE]
    > <span data-ttu-id="323e2-398">Los artículos y cantidades que se proporcionan aquí son solo ejemplos.</span><span class="sxs-lookup"><span data-stu-id="323e2-398">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="323e2-399">Deben tener existencias en el almacén especificado.</span><span class="sxs-lookup"><span data-stu-id="323e2-399">They must have stock in the specified warehouse.</span></span>

1. <span data-ttu-id="323e2-400">Seleccione la línea de pedido de ventas 1.</span><span class="sxs-lookup"><span data-stu-id="323e2-400">Select sales order line 1.</span></span> <span data-ttu-id="323e2-401">A continuación, en la sección **Línea de pedido de ventas** , en el menú **Inventario** , seleccione **Reservas**.</span><span class="sxs-lookup"><span data-stu-id="323e2-401">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="323e2-402">En la página **Reserva** , en el panel de acciones, seleccione **Reservar lote** y después cierre la página.</span><span class="sxs-lookup"><span data-stu-id="323e2-402">On the **Reservation** page, on the Action Pane, select **Reserve lot** , and then close the page.</span></span>
1. <span data-ttu-id="323e2-403">Repita los pasos 4 y 5 para cada línea adicional del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="323e2-403">Repeat steps 4 and 5 for each additional sales order line.</span></span>
1. <span data-ttu-id="323e2-404">En el panel de acciones, en la pestaña **Almacén** , seleccione **Liberar al almacén**.</span><span class="sxs-lookup"><span data-stu-id="323e2-404">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="323e2-405">Se producen los eventos siguientes:</span><span class="sxs-lookup"><span data-stu-id="323e2-405">The following events occur:</span></span>

    - <span data-ttu-id="323e2-406">El sistema procesa el envío creado utilizando la plantilla que incluye el paso de impresión de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="323e2-406">The system processes the created shipment using the template that includes the label printing step.</span></span> <span data-ttu-id="323e2-407">El diseño de etiqueta se usará para definir el formato de la etiqueta y el resultado final será una etiqueta que tiene cinco líneas y que se imprime en la impresora que está seleccionada en la plantilla de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="323e2-407">The label layout will be used to define the format of the label, and the end result will be a label that has five lines and that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="323e2-408">Se genera un nuevo id. de conocimiento de embarque para los envíos.</span><span class="sxs-lookup"><span data-stu-id="323e2-408">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="323e2-409">Si ha configurado las extensiones de secuencias numéricas, los id. de etiquetas de oleadas seguirán el formato numérico **SSCC-18**.</span><span class="sxs-lookup"><span data-stu-id="323e2-409">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="323e2-410">Para volver a imprimir estas etiquetas de oleadas, vaya a **Gestión de almacenes \> Consultas e informes \> Historial de etiquetas de oleada**.</span><span class="sxs-lookup"><span data-stu-id="323e2-410">You can reprint these wave labels by going to **Warehouse management \> Inquiries and reports \> Wave label history**.</span></span>

## <a name="scenario-3-wave-label-printing-for-multi-tiered-labels"></a><span data-ttu-id="323e2-411">Escenario 3: impresión de etiquetas de oleadas para etiquetas de varios niveles</span><span class="sxs-lookup"><span data-stu-id="323e2-411">Scenario 3: Wave label printing for multi-tiered labels</span></span>

<span data-ttu-id="323e2-412">Este escenario muestra cómo utilizar la funcionalidad de impresión de etiquetas de oleada cuando los procesos de almacenamiento requieren varios niveles de etiquetas de envío.</span><span class="sxs-lookup"><span data-stu-id="323e2-412">This scenario shows how to use the wave label printing functionality when the warehousing processes require several tiers of shipping labels.</span></span> <span data-ttu-id="323e2-413">Por ejemplo, es posible que se tengan que imprimir etiquetas independientes para cajas y pallets, y se debe imprimir una etiqueta de interrupción para un envío completo.</span><span class="sxs-lookup"><span data-stu-id="323e2-413">For example, separate labels might have to be printed for cartons and pallets, and a break label might have to be printed for a whole shipment.</span></span> <span data-ttu-id="323e2-414">Las etiquetas de interrupción son un tipo independiente de etiqueta que se puede usar como un divisor entre rollos y contenedores, como las etiquetas para el id. de envío y un código de barras, de modo que las etiquetas pueden ordenarse con facilidad después de su impresión.</span><span class="sxs-lookup"><span data-stu-id="323e2-414">Break labels are a separate type of label that can be used as a divider between rolls and containers, such as labels for the shipment ID and a barcode, so that the labels can easily be sorted after they are printed.</span></span>

<span data-ttu-id="323e2-415">La diferencia principal entre la configuración de este escenario y la configuración del escenario 1, además del hecho de que las etiquetas de interrupción están habilitadas, es que varios tipos de etiquetas de oleadas deben estar asociados con plantillas de etiquetas de oleadas y líneas de grupos de secuencias de unidad.</span><span class="sxs-lookup"><span data-stu-id="323e2-415">The main difference between the configuration of this scenario and the configuration of scenario 1, besides the fact that break labels are enabled, is that multiple wave label types must be associated with wave label templates and unit sequence group lines.</span></span> <span data-ttu-id="323e2-416">Para lograr esta configuración, configure los siguientes elementos para este escenario:</span><span class="sxs-lookup"><span data-stu-id="323e2-416">To accomplish this configuration, you set up the following elements for this scenario:</span></span>

- <span data-ttu-id="323e2-417">**Métodos de procesamiento de oleadas:** marcará el método de etiqueta de oleada como "repetible", lo agregará dos (o más) veces a la plantilla de oleada y establecerá diferentes códigos de paso de oleada.</span><span class="sxs-lookup"><span data-stu-id="323e2-417">**Wave processing methods:** You will mark the wave label method as "repeatable," add it two (or more) times to the wave template, and set different wave step codes.</span></span>
- <span data-ttu-id="323e2-418">**Plantillas de etiquetas de oleadas:** configurará las plantillas de etiquetas de oleadas y las vinculará a la plantilla de oleada.</span><span class="sxs-lookup"><span data-stu-id="323e2-418">**Wave label templates:** You will configure the wave label templates and link them to the wave template.</span></span> <span data-ttu-id="323e2-419">Cada plantilla de etiqueta de oleada tiene su propio tipo de etiqueta de oleada.</span><span class="sxs-lookup"><span data-stu-id="323e2-419">Each wave label template has its own wave label type.</span></span>
- <span data-ttu-id="323e2-420">**Diseños de etiquetas de oleadas:** creará varios diseños de etiquetas de oleadas.</span><span class="sxs-lookup"><span data-stu-id="323e2-420">**Wave label layouts:** You will create multiple wave label layouts.</span></span> <span data-ttu-id="323e2-421">Habrá un diseño de etiqueta independiente para cada "nivel" de etiquetas y también habrá un diseño de etiqueta de interrupción.</span><span class="sxs-lookup"><span data-stu-id="323e2-421">There will be a separate label layout for each "tier" of labels, and there will also be a break label layout.</span></span>

<span data-ttu-id="323e2-422">Este escenario muestra el flujo de extremo a extremo.</span><span class="sxs-lookup"><span data-stu-id="323e2-422">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="323e2-423">Hacer que los datos de demostración estén disponibles</span><span class="sxs-lookup"><span data-stu-id="323e2-423">Make demo data available</span></span>

<span data-ttu-id="323e2-424">Para seguir este escenario, los datos de demostración deben estar instalados y debe seleccionar la entidad jurídica **USMF**.</span><span class="sxs-lookup"><span data-stu-id="323e2-424">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="set-up-a-wave-process-method"></a><span data-ttu-id="323e2-425">Configurar un método de proceso de oleada</span><span class="sxs-lookup"><span data-stu-id="323e2-425">Set up a wave process method</span></span>

1. <span data-ttu-id="323e2-426">Vaya a **Gestión de almacenes \> Configuración \> Oleadas \> Métodos de proceso de oleadas**.</span><span class="sxs-lookup"><span data-stu-id="323e2-426">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="323e2-427">Confirme que **waveLabelPrinting** está en la lista.</span><span class="sxs-lookup"><span data-stu-id="323e2-427">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="323e2-428">Si no está, seleccione **Regenerar métodos** en el Panel de acciones para agregarlo.</span><span class="sxs-lookup"><span data-stu-id="323e2-428">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>
1. <span data-ttu-id="323e2-429">Para el método **waveLabelPrinting** , seleccione la casilla **Convertir método en repetible**.</span><span class="sxs-lookup"><span data-stu-id="323e2-429">For the **waveLabelPrinting** method, select the **Make method repeatable** check box.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="323e2-430">Configurar una plantilla de oleada</span><span class="sxs-lookup"><span data-stu-id="323e2-430">Set up a wave template</span></span>

1. <span data-ttu-id="323e2-431">Vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**.</span><span class="sxs-lookup"><span data-stu-id="323e2-431">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
2. <span data-ttu-id="323e2-432">Seleccione una plantilla, como **Plantilla predeterminada 62**.</span><span class="sxs-lookup"><span data-stu-id="323e2-432">Select a template, such as **62 Shipping Default**.</span></span>
3. <span data-ttu-id="323e2-433">En la ficha desplegable **Métodos** , mueva el método **Impresión de etiquetas de oleada** a la columna **Métodos seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="323e2-433">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
4. <span data-ttu-id="323e2-434">En la columna **Métodos seleccionados** , asigne un valor **Código de paso de oleada** , como *Caja* , al método **Impresión de etiquetas de oleadas**.</span><span class="sxs-lookup"><span data-stu-id="323e2-434">In the **Selected methods** column, assign a **Wave step code** value, such as *Carton* , to the **Wave label printing** method.</span></span> <span data-ttu-id="323e2-435">Para obtener más información sobre los códigos de pasos de oleadas, vea [Códigos de paso de oleada](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="323e2-435">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>
5. <span data-ttu-id="323e2-436">Mueva de nuevo el método **Impresión de etiquetas de oleadas** a la columna **Métodos seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="323e2-436">Move the **Wave label printing** method to the **Selected methods** column a second time.</span></span>
6. <span data-ttu-id="323e2-437">En la columna **Métodos seleccionados** , asigne un valor diferente **Código de paso de oleada** , como *Pallet* , al segundo método método **Impresión de etiquetas de oleadas**.</span><span class="sxs-lookup"><span data-stu-id="323e2-437">In the **Selected methods** column, assign a different **Wave step code** value, such as *Pallet* , to the second **Wave label printing** method.</span></span> <span data-ttu-id="323e2-438">Para obtener más información sobre los códigos de pasos de oleadas, vea [Códigos de paso de oleada](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="323e2-438">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-three-wave-label-layouts"></a><span data-ttu-id="323e2-439">Crear tres diseños de etiquetas de oleadas</span><span class="sxs-lookup"><span data-stu-id="323e2-439">Create three wave label layouts</span></span>

1. <span data-ttu-id="323e2-440">Vaya a **Gestión de almacenes \> Configuración \> Ruta de documentos \> Diseño de etiquetas de oleada**.</span><span class="sxs-lookup"><span data-stu-id="323e2-440">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="323e2-441">Cree un registro que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="323e2-441">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="323e2-442">**Id. de diseño de etiqueta:** *Caja*</span><span class="sxs-lookup"><span data-stu-id="323e2-442">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="323e2-443">**Descripción:** *Caja (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="323e2-443">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="323e2-444">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="323e2-444">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="323e2-445">En el Panel de acciones, seleccione **Configuración de filas de etiquetas de oleadas**.</span><span class="sxs-lookup"><span data-stu-id="323e2-445">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="323e2-446">Aparece la página **Configuración de filas de etiquetas de oleadas**.</span><span class="sxs-lookup"><span data-stu-id="323e2-446">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="323e2-447">Aquí, puede configurar la parte dinámica de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="323e2-447">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="323e2-448">Agregue una fila con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="323e2-448">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="323e2-449">**Id. de fila:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="323e2-449">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="323e2-450">**Nombre de la tabla de filas:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="323e2-450">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="323e2-451">**Posición inicial de fila:** *0*</span><span class="sxs-lookup"><span data-stu-id="323e2-451">**Row start position:** *0*</span></span>

        <span data-ttu-id="323e2-452">Este campo define la posición vertical donde comenzará la fila en la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="323e2-452">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="323e2-453">**Alto de fila:** *0*</span><span class="sxs-lookup"><span data-stu-id="323e2-453">**Row height:** *0*</span></span>

        <span data-ttu-id="323e2-454">Este campo define el alto de cada fila (en puntos), conforme al estándar ZPL.</span><span class="sxs-lookup"><span data-stu-id="323e2-454">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="323e2-455">El alto de la fila es positivo para etiquetas horizontales y negativo para etiquetas verticales.</span><span class="sxs-lookup"><span data-stu-id="323e2-455">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="323e2-456">Como solo hay una fila en este ejemplo, el valor se puede establecer en *0* (cero).</span><span class="sxs-lookup"><span data-stu-id="323e2-456">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="323e2-457">**Filas por página:** *1*</span><span class="sxs-lookup"><span data-stu-id="323e2-457">**Rows per page:** *1*</span></span>

        <span data-ttu-id="323e2-458">Este campo define el número de filas que se pueden imprimir en cada etiqueta.</span><span class="sxs-lookup"><span data-stu-id="323e2-458">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="323e2-459">Esta configuración hará que se imprima una etiqueta ZPL independiente para cada registro en la tabla de etiquetas de oleada.</span><span class="sxs-lookup"><span data-stu-id="323e2-459">This setup will cause a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="323e2-460">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="323e2-460">Close the page.</span></span>
1. <span data-ttu-id="323e2-461">En el panel Acciones, seleccione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="323e2-461">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="323e2-462">En el cuadro de diálogo del editor de consultas, en la pestaña **Intervalo** , seleccione una fila que tenga los siguientes parámetros.</span><span class="sxs-lookup"><span data-stu-id="323e2-462">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="323e2-463">**Tabla:** *Lineas de trabajo*</span><span class="sxs-lookup"><span data-stu-id="323e2-463">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="323e2-464">**Tabla derivada:** *Líneas de trabajo*</span><span class="sxs-lookup"><span data-stu-id="323e2-464">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="323e2-465">**Campo:** *Tipo de trabajo*</span><span class="sxs-lookup"><span data-stu-id="323e2-465">**Field:** *Work type*</span></span>
    - <span data-ttu-id="323e2-466">**Criterios:** *Seleccionar*</span><span class="sxs-lookup"><span data-stu-id="323e2-466">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="323e2-467">Esta consulta garantiza que solo se imprimen líneas de trabajo de tipo recogida en la etiqueta y no en líneas de trabajo del tipo colocación.</span><span class="sxs-lookup"><span data-stu-id="323e2-467">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="323e2-468">Si desea imprimir el id. del conocimiento de embarque, en la pestaña **Combinaciones** , seleccione la tabla **Líneas de trabajo** y vincúlela a la tabla **Envíos**.</span><span class="sxs-lookup"><span data-stu-id="323e2-468">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span> 
1. <span data-ttu-id="323e2-469">Cierre el cuadro de diálogo del editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="323e2-469">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="323e2-470">La ficha desplegable **Diseño de texto de impresora** tiene tres secciones donde puede escribir el código de la impresora: **Sección del encabezado** , **Sección del cuerpo** y **Sección del pie de página**.</span><span class="sxs-lookup"><span data-stu-id="323e2-470">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section** , **Body section** , and **Footer section**.</span></span> <span data-ttu-id="323e2-471">En la **Sección del encabezado** , en el campo **Encabezado de la etiqueta** , introduzca el código para el encabezado requerido.</span><span class="sxs-lookup"><span data-stu-id="323e2-471">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="323e2-472">Por ejemplo, si usa impresoras Zebra, puede usar el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="323e2-472">For example, if you're using Zebra printers, you can use the following code.</span></span>


    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. <span data-ttu-id="323e2-473">En la **Sección del cuerpo** , en el campo **Cuerpo de la etiqueta** , introduzca el código ZPL para el cuerpo requerido.</span><span class="sxs-lookup"><span data-stu-id="323e2-473">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="323e2-474">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="323e2-474">Here is an example.</span></span>

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. <span data-ttu-id="323e2-475">En la **Sección del cuerpo** , en el campo **Pie de página de la etiqueta** , introduzca el código ZPL para el pie de página requerido.</span><span class="sxs-lookup"><span data-stu-id="323e2-475">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="323e2-476">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="323e2-476">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="323e2-477">Esta configuración imprimirá una copia de cada etiqueta.</span><span class="sxs-lookup"><span data-stu-id="323e2-477">This setup will print one copy of each label.</span></span> <span data-ttu-id="323e2-478">Si necesita más copias (por ejemplo, una copia para cada lado del pallet), establezca el valor **n** para la sección **\^PQn** en el pie de página para el número requerido de copias.</span><span class="sxs-lookup"><span data-stu-id="323e2-478">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="323e2-479">Por ejemplo, para imprimir cuatro copias de cada etiqueta, especifique **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="323e2-479">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

1. <span data-ttu-id="323e2-480">La primera etiqueta ya está lista para usarse.</span><span class="sxs-lookup"><span data-stu-id="323e2-480">The first label is now ready to use.</span></span>
1. <span data-ttu-id="323e2-481">Cree un segundo registro de diseño que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="323e2-481">Create a second layout record that has the following settings:</span></span>

    - <span data-ttu-id="323e2-482">**Id. de diseño de etiquetas:** *Pallet*</span><span class="sxs-lookup"><span data-stu-id="323e2-482">**Label layout ID:** *Pallet*</span></span>
    - <span data-ttu-id="323e2-483">**Descripción:** *Pallet*</span><span class="sxs-lookup"><span data-stu-id="323e2-483">**Description:** *Pallet*</span></span>

1. <span data-ttu-id="323e2-484">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="323e2-484">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="323e2-485">En el Panel de acciones, seleccione **Configuración de filas de etiquetas de oleadas**.</span><span class="sxs-lookup"><span data-stu-id="323e2-485">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="323e2-486">Aparece la página **Configuración de filas de etiquetas de oleadas**.</span><span class="sxs-lookup"><span data-stu-id="323e2-486">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="323e2-487">Aquí, puede configurar la parte dinámica de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="323e2-487">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="323e2-488">Agregue una fila con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="323e2-488">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="323e2-489">**Id. de fila:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="323e2-489">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="323e2-490">**Nombre de la tabla de filas:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="323e2-490">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="323e2-491">**Posición inicial de fila:** *0*</span><span class="sxs-lookup"><span data-stu-id="323e2-491">**Row start position:** *0*</span></span>

        <span data-ttu-id="323e2-492">Este campo define la posición vertical donde comenzará la fila en la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="323e2-492">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="323e2-493">**Alto de fila:** *0*</span><span class="sxs-lookup"><span data-stu-id="323e2-493">**Row height:** *0*</span></span>

        <span data-ttu-id="323e2-494">Este campo define el alto de cada fila (en puntos), conforme al estándar ZPL.</span><span class="sxs-lookup"><span data-stu-id="323e2-494">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="323e2-495">El alto de la fila es positivo para etiquetas horizontales y negativo para etiquetas verticales.</span><span class="sxs-lookup"><span data-stu-id="323e2-495">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="323e2-496">Como solo hay una fila en este ejemplo, el valor se puede establecer en *0* (cero).</span><span class="sxs-lookup"><span data-stu-id="323e2-496">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="323e2-497">**Filas por página:** *1*</span><span class="sxs-lookup"><span data-stu-id="323e2-497">**Rows per page:** *1*</span></span>

        <span data-ttu-id="323e2-498">Este campo define el número de filas que se pueden imprimir en cada etiqueta.</span><span class="sxs-lookup"><span data-stu-id="323e2-498">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="323e2-499">Esta configuración causa que se imprima una etiqueta ZPL independiente para cada registro de la tabla de etiquetas de oleadas.</span><span class="sxs-lookup"><span data-stu-id="323e2-499">This setup causes a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="323e2-500">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="323e2-500">Close the page.</span></span>
1. <span data-ttu-id="323e2-501">En el panel Acciones, seleccione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="323e2-501">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="323e2-502">En el cuadro de diálogo del editor de consultas, en la pestaña **Intervalo** , seleccione una fila que tenga los siguientes parámetros.</span><span class="sxs-lookup"><span data-stu-id="323e2-502">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="323e2-503">**Tabla:** *Lineas de trabajo*</span><span class="sxs-lookup"><span data-stu-id="323e2-503">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="323e2-504">**Tabla derivada:** *Líneas de trabajo*</span><span class="sxs-lookup"><span data-stu-id="323e2-504">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="323e2-505">**Campo:** *Tipo de trabajo*</span><span class="sxs-lookup"><span data-stu-id="323e2-505">**Field:** *Work type*</span></span>
    - <span data-ttu-id="323e2-506">**Criterios:** *Seleccionar*</span><span class="sxs-lookup"><span data-stu-id="323e2-506">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="323e2-507">Esta consulta garantiza que solo se imprimen líneas de trabajo de tipo recogida en la etiqueta y no en líneas de trabajo del tipo colocación.</span><span class="sxs-lookup"><span data-stu-id="323e2-507">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="323e2-508">Si desea imprimir el id. del conocimiento de embarque, en la pestaña **Combinaciones** , seleccione la tabla **Líneas de trabajo** y vincúlela a la tabla **Envíos**.</span><span class="sxs-lookup"><span data-stu-id="323e2-508">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="323e2-509">Cierre el cuadro de diálogo del editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="323e2-509">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="323e2-510">La ficha desplegable **Diseño de texto de impresora** tiene tres secciones donde puede escribir el código de la impresora: **Sección del encabezado** , **Sección del cuerpo** y **Sección del pie de página**.</span><span class="sxs-lookup"><span data-stu-id="323e2-510">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section** , **Body section** , and **Footer section**.</span></span> <span data-ttu-id="323e2-511">En la **Sección del encabezado** , en el campo **Encabezado de la etiqueta** , introduzca el código para el encabezado requerido.</span><span class="sxs-lookup"><span data-stu-id="323e2-511">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="323e2-512">Por ejemplo, si usa impresoras Zebra, puede usar el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="323e2-512">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWaveLabel.WaveLabelId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. <span data-ttu-id="323e2-513">En la **Sección del cuerpo** , en el campo **Cuerpo de la etiqueta** , introduzca el código ZPL para el cuerpo requerido.</span><span class="sxs-lookup"><span data-stu-id="323e2-513">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="323e2-514">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="323e2-514">Here is an example.</span></span>

    ```plaintext
    <Row name="WaveLabel">
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWaveLabel.LabelItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWaveLabel.QtyWork$ ^FS
    </Row>
    ```

1. <span data-ttu-id="323e2-515">En la **Sección del cuerpo** , en el campo **Pie de página de la etiqueta** , introduzca el código ZPL para el pie de página requerido.</span><span class="sxs-lookup"><span data-stu-id="323e2-515">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="323e2-516">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="323e2-516">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="323e2-517">Esta configuración imprimirá una copia de cada etiqueta.</span><span class="sxs-lookup"><span data-stu-id="323e2-517">This setup will print one copy of each label.</span></span> <span data-ttu-id="323e2-518">Si necesita más copias (por ejemplo, una copia para cada lado del pallet), establezca el valor **n** para la sección **\^PQn** en el pie de página para el número requerido de copias.</span><span class="sxs-lookup"><span data-stu-id="323e2-518">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="323e2-519">Por ejemplo, para imprimir cuatro copias de cada etiqueta, especifique **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="323e2-519">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

1. <span data-ttu-id="323e2-520">La segunda etiqueta ya está lista para usarse.</span><span class="sxs-lookup"><span data-stu-id="323e2-520">The second label is now ready to use.</span></span>
1. <span data-ttu-id="323e2-521">Cree un tercer registro de diseño que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="323e2-521">Create a third layout record that has the following settings:</span></span>

    - <span data-ttu-id="323e2-522">**Id. de diseño de etiquetas:** *Interrupción*</span><span class="sxs-lookup"><span data-stu-id="323e2-522">**Label layout ID:** *Break*</span></span>
    - <span data-ttu-id="323e2-523">**Descripción:** *Etiqueta de interrupción*</span><span class="sxs-lookup"><span data-stu-id="323e2-523">**Description:** *Break label*</span></span>

1. <span data-ttu-id="323e2-524">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="323e2-524">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="323e2-525">La ficha desplegable **Diseño de texto de impresora** tiene tres secciones donde puede escribir el código de la impresora: **Sección del encabezado** , **Sección del cuerpo** y **Sección del pie de página**.</span><span class="sxs-lookup"><span data-stu-id="323e2-525">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section** , **Body section** , and **Footer section**.</span></span> <span data-ttu-id="323e2-526">En **Sección del encabezado** , en el campo **Encabezado de la etiqueta** , introduzca el código ZPL para el encabezado requerido.</span><span class="sxs-lookup"><span data-stu-id="323e2-526">In the **Header section** section, in the **Label header** field, enter ZPL code for the required header.</span></span> <span data-ttu-id="323e2-527">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="323e2-527">Here is an example.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ```

1. <span data-ttu-id="323e2-528">Esta vez, el cuerpo no es necesario.</span><span class="sxs-lookup"><span data-stu-id="323e2-528">This time, no body is required.</span></span> <span data-ttu-id="323e2-529">Por lo tanto, simplemente introduzca el texto necesario en la **Sección de pie de página**.</span><span class="sxs-lookup"><span data-stu-id="323e2-529">Therefore, just enter the required text in the **Footer section** section.</span></span> <span data-ttu-id="323e2-530">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="323e2-530">Here is an example.</span></span>

    ```plaintext
    ^XZ
    ```

    <span data-ttu-id="323e2-531">La tercera etiqueta ya está lista para usarse.</span><span class="sxs-lookup"><span data-stu-id="323e2-531">The third label is now ready to use.</span></span>

    > [!NOTE]
    > <span data-ttu-id="323e2-532">Esta tercera etiqueta es una etiqueta de interrupción que se utilizará como divisor entre los rollos de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="323e2-532">This third label is a break label that will be used as a divider between label rolls.</span></span>

### <a name="create-two-wave-label-types"></a><span data-ttu-id="323e2-533">Crear dos tipos de etiquetas de oleadas</span><span class="sxs-lookup"><span data-stu-id="323e2-533">Create two wave label types</span></span>

1. <span data-ttu-id="323e2-534">Vaya a **Gestión de almacenes \> Configuración \> Ruta de documentos \> Tipos de etiquetas de oleadas**.</span><span class="sxs-lookup"><span data-stu-id="323e2-534">Go to **Warehouse management \> Setup \> Document routing \> Wave label types**.</span></span>
1. <span data-ttu-id="323e2-535">Cree un registro que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="323e2-535">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="323e2-536">**Tipo de etiqueta:** *Caja*</span><span class="sxs-lookup"><span data-stu-id="323e2-536">**Label type:** *Carton*</span></span>
    - <span data-ttu-id="323e2-537">**Descripción:** *Caja (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="323e2-537">**Description:** *Carton*</span></span>

1. <span data-ttu-id="323e2-538">Cree un segundo registro que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="323e2-538">Create a second record that has the following settings:</span></span>

    - <span data-ttu-id="323e2-539">**Tipo de etiqueta:** *Pallets*</span><span class="sxs-lookup"><span data-stu-id="323e2-539">**Label type:** *Pallet*</span></span>
    - <span data-ttu-id="323e2-540">**Descripción:** *Pallet*</span><span class="sxs-lookup"><span data-stu-id="323e2-540">**Description:** *Pallet*</span></span>

### <a name="set-up-unit-sequence-groups"></a><span data-ttu-id="323e2-541">Configurar grupos de secuencias de unidades</span><span class="sxs-lookup"><span data-stu-id="323e2-541">Set up unit sequence groups</span></span>

1. <span data-ttu-id="323e2-542">Vaya a **Gestión de almacenes \> Configuración \> Almacén \> Grupos de secuencias de unidades**.</span><span class="sxs-lookup"><span data-stu-id="323e2-542">Go to **Warehouse management \> Setup \> Warehouse \> Unit sequence groups**.</span></span>
1. <span data-ttu-id="323e2-543">Seleccione o cree un grupo **Ea Box PL**.</span><span class="sxs-lookup"><span data-stu-id="323e2-543">Select or create an **Ea Box PL** group.</span></span>
1. <span data-ttu-id="323e2-544">En la línea **Caja** establezca el campo **Tipo de nivel de oleada** en *Caja*.</span><span class="sxs-lookup"><span data-stu-id="323e2-544">For the **Box** line, set the **Wave level type** field to *Carton*.</span></span>
1. <span data-ttu-id="323e2-545">En la línea **Ea Box PL** establezca el campo **Tipo de nivel de oleada** en *Pallet*.</span><span class="sxs-lookup"><span data-stu-id="323e2-545">For the **PL** line, set the **Wave level type** field to *Pallet*.</span></span>

### <a name="create-wave-label-templates"></a><span data-ttu-id="323e2-546">Crear plantillas de etiquetas de oleadas</span><span class="sxs-lookup"><span data-stu-id="323e2-546">Create wave label templates</span></span>

1. <span data-ttu-id="323e2-547">Vaya a **Gestión de almacenes \> Configuración \> Ruta de documentos \> Plantillas de etiqueta de oleada**.</span><span class="sxs-lookup"><span data-stu-id="323e2-547">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="323e2-548">Cree una plantilla de etiqueta con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="323e2-548">Create a label template that has the following settings:</span></span>

    - <span data-ttu-id="323e2-549">**Nombre de plantilla de etiqueta:** *Etiquetas de caja*</span><span class="sxs-lookup"><span data-stu-id="323e2-549">**Label template name:** *Carton labels*</span></span>
    - <span data-ttu-id="323e2-550">**Descripción:** *Etiquetas de caja*</span><span class="sxs-lookup"><span data-stu-id="323e2-550">**Description:** *Carton labels*</span></span>
    - <span data-ttu-id="323e2-551">**Código de paso de oleada:** *Caja*</span><span class="sxs-lookup"><span data-stu-id="323e2-551">**Wave step code:** *Carton*</span></span>
    - <span data-ttu-id="323e2-552">**Almacén** : *62*</span><span class="sxs-lookup"><span data-stu-id="323e2-552">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="323e2-553">En la ficha desplegable **General** , en el campo **Tipo de etiqueta de oleada** , seleccione un valor como *Caja*.</span><span class="sxs-lookup"><span data-stu-id="323e2-553">On the **General** FastTab, in the **Wave label type** field, select a value, such as *Carton*.</span></span>
1. <span data-ttu-id="323e2-554">En la ficha desplegable **Detalles de plantillas de etiquetas de oleadas** , agregue una fila que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="323e2-554">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="323e2-555">**Id. de diseño de etiqueta:** *Caja*</span><span class="sxs-lookup"><span data-stu-id="323e2-555">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="323e2-556">**Nombre de la impresora:** seleccione una impresora ZPL adecuada.</span><span class="sxs-lookup"><span data-stu-id="323e2-556">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="323e2-557">**Ejecutar consulta:** *Sí* (Esta configuración es opcional, pero se recomienda para un rendimiento óptimo).</span><span class="sxs-lookup"><span data-stu-id="323e2-557">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="323e2-558">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="323e2-558">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="323e2-559">Opcional: si está configurando un diseño de etiqueta específico del cliente, debe crear una consulta para encontrar la cuenta del cliente.</span><span class="sxs-lookup"><span data-stu-id="323e2-559">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="323e2-560">En la ficha desplegable **Detalles de plantilla de etiqueta de oleada** , seleccione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="323e2-560">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="323e2-561">A continuación, agregue una fila que tenga la siguiente configuración dentro de la pestaña **Intervalo** , en el cuadro de diálogo del editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="323e2-561">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="323e2-562">**Tabla:** *Envíos*</span><span class="sxs-lookup"><span data-stu-id="323e2-562">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="323e2-563">**Tabla derivada:** *Envíos*</span><span class="sxs-lookup"><span data-stu-id="323e2-563">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="323e2-564">**Campo:** *Número de cuenta*</span><span class="sxs-lookup"><span data-stu-id="323e2-564">**Field:** *Account number*</span></span>
    - <span data-ttu-id="323e2-565">**Criterios** introduzca el número de cuenta del cliente pertinente.</span><span class="sxs-lookup"><span data-stu-id="323e2-565">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="323e2-566">Cuando haya terminado, seleccione **Aceptar** para cerrar el cuadro de diálogo del editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="323e2-566">When you've finished, select **OK** to close the query editor dialog box.</span></span>

1. <span data-ttu-id="323e2-567">En el panel de acciones, seleccione **Editar consulta** para abrir el cuadro de diálogo del editor de consultas para la plantilla de etiqueta completa.</span><span class="sxs-lookup"><span data-stu-id="323e2-567">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="323e2-568">En el cuadro de diálogo del editor de consultas, en la pestaña **Ordenación** , seleccione una fila que tenga la siguiente configuración.</span><span class="sxs-lookup"><span data-stu-id="323e2-568">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="323e2-569">**Tabla:** *Lineas de trabajo*</span><span class="sxs-lookup"><span data-stu-id="323e2-569">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="323e2-570">**Tabla derivada:** *Líneas de trabajo*</span><span class="sxs-lookup"><span data-stu-id="323e2-570">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="323e2-571">**Campo:** *id. de línea de carga de referencia (id. de registro)*</span><span class="sxs-lookup"><span data-stu-id="323e2-571">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="323e2-572">**Dirección de búsqueda:** *Ascendente*</span><span class="sxs-lookup"><span data-stu-id="323e2-572">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="323e2-573">Agregue una segunda columna que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="323e2-573">Add a second row that has the following settings:</span></span>

    - <span data-ttu-id="323e2-574">**Tabla:** *Lineas de trabajo*</span><span class="sxs-lookup"><span data-stu-id="323e2-574">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="323e2-575">**Tabla derivada:** *Líneas de trabajo*</span><span class="sxs-lookup"><span data-stu-id="323e2-575">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="323e2-576">**Campo:** *Identificación del envío*</span><span class="sxs-lookup"><span data-stu-id="323e2-576">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="323e2-577">**Dirección de búsqueda:** *Ascendente*</span><span class="sxs-lookup"><span data-stu-id="323e2-577">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="323e2-578">Seleccione **Aceptar** para cerrar el cuadro de diálogo del editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="323e2-578">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="323e2-579">Un cuadro de mensaje le solicitará que confirme la operación de restablecimiento de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="323e2-579">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="323e2-580">Seleccione **Sí** para continuar.</span><span class="sxs-lookup"><span data-stu-id="323e2-580">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="323e2-581">En el panel de acciones, seleccione **Grupo de plantillas de etiquetas de oleadas**.</span><span class="sxs-lookup"><span data-stu-id="323e2-581">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="323e2-582">En el cuadro de diálogo **Grupo de plantillas de etiquetas de oleadas** , en la fila donde el campo **Nombre del campo de referencia** se establece en *Id. del envío* , establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="323e2-582">In the **Wave label template group** dialog box, for the row where the **Reference field name** field is set to *Shipment ID* , set the following values:</span></span>

    - <span data-ttu-id="323e2-583">**Imprimir etiqueta de interrupción:** seleccione esta casilla.</span><span class="sxs-lookup"><span data-stu-id="323e2-583">**Print break label:** Select this check box.</span></span>
    - <span data-ttu-id="323e2-584">**ID de diseño de etiquetas:** seleccione una etiqueta de interrupción.</span><span class="sxs-lookup"><span data-stu-id="323e2-584">**Label layout ID:** Select a break label.</span></span> <span data-ttu-id="323e2-585">(Por ejemplo, seleccione el diseño de la etiqueta *Interrupción* que creó anteriormente en este escenario.)</span><span class="sxs-lookup"><span data-stu-id="323e2-585">(For example, select the *Break* label layout that you created earlier in this scenario.)</span></span>
    - <span data-ttu-id="323e2-586">**Nombre de la impresora:** seleccione la impresora para la etiqueta de interrupción.</span><span class="sxs-lookup"><span data-stu-id="323e2-586">**Printer name:** Select the printer for the break label.</span></span> <span data-ttu-id="323e2-587">(Normalmente, para dividir los rollos de etiquetas, debe seleccionar la misma impresora que está seleccionada en la ficha desplegable **Detalles de plantilla de etiqueta de oleada**.</span><span class="sxs-lookup"><span data-stu-id="323e2-587">(Typically, for the purpose of splitting label rolls, you should select the same printer that is selected on the **Wave label template details** FastTab.</span></span> <span data-ttu-id="323e2-588">Aún así, pueden darse otros escenarios).</span><span class="sxs-lookup"><span data-stu-id="323e2-588">However, other scenarios are possible.)</span></span>

1. <span data-ttu-id="323e2-589">Para la fila donde el campo **Nombre del campo de referencia** se establezca en *Identificador de la referencia de la línea de carga* , seleccione la casilla **Id. de compilación de etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="323e2-589">For the row where the **Reference field name** field is set to *Reference load line id* , select the **Label build ID** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="323e2-590">Esta configuración creará una secuencia de etiquetas ("Caja 1 de X") por línea de carga a lo largo de la oleada, con independencia de la configuración de agrupación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="323e2-590">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="323e2-591">Esta secuencia de etiquetas se puede imprimir en un diseño de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="323e2-591">This label sequence can be printed on a label layout.</span></span> <span data-ttu-id="323e2-592">Además, las etiquetas para diferentes envíos estarán separadas por la etiqueta de interrupción seleccionada.</span><span class="sxs-lookup"><span data-stu-id="323e2-592">Additionally, labels for different shipments will be separated by the selected break label.</span></span>

1. <span data-ttu-id="323e2-593">Seleccione **Aceptar** para cerrar el cuadro de diálogo **Grupo de plantillas de etiquetas de oleadas**.</span><span class="sxs-lookup"><span data-stu-id="323e2-593">Select **OK** to close the **Wave label template group** dialog box.</span></span>
1. <span data-ttu-id="323e2-594">Cree una segunda plantilla de etiqueta con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="323e2-594">Create a second label template that has the following settings:</span></span>

    - <span data-ttu-id="323e2-595">**Nombre de la plantilla de etiqueta:** *Etiquetas de pallet*</span><span class="sxs-lookup"><span data-stu-id="323e2-595">**Label template name:** *Pallet labels*</span></span>
    - <span data-ttu-id="323e2-596">**Descripción:** *Etiquetas de pallet*</span><span class="sxs-lookup"><span data-stu-id="323e2-596">**Description:** *Pallet labels*</span></span>
    - <span data-ttu-id="323e2-597">**Código de paso de oleada:** *Pallet*</span><span class="sxs-lookup"><span data-stu-id="323e2-597">**Wave step code:** *Pallet*</span></span>
    - <span data-ttu-id="323e2-598">**Almacén** : *62*</span><span class="sxs-lookup"><span data-stu-id="323e2-598">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="323e2-599">En la ficha desplegable **General** , en el campo **Tipo de etiqueta de oleada** , seleccione un valor como *Pallet*.</span><span class="sxs-lookup"><span data-stu-id="323e2-599">On the **General** FastTab, in the **Wave label type** field, select a value, such as *Pallet*.</span></span>
1. <span data-ttu-id="323e2-600">En la ficha desplegable **Detalles de plantillas de etiquetas de oleadas** , agregue una fila que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="323e2-600">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="323e2-601">**Id. de diseño de etiquetas:** *Pallet*</span><span class="sxs-lookup"><span data-stu-id="323e2-601">**Label layout ID:** *Pallet*</span></span>
    - <span data-ttu-id="323e2-602">**Nombre de la impresora:** seleccione una impresora ZPL adecuada.</span><span class="sxs-lookup"><span data-stu-id="323e2-602">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="323e2-603">**Ejecutar consulta:** *Sí* (Esta configuración es opcional, pero se recomienda para un rendimiento óptimo).</span><span class="sxs-lookup"><span data-stu-id="323e2-603">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="323e2-604">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="323e2-604">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="323e2-605">Opcional: si está configurando un diseño de etiqueta específico del cliente, debe crear una consulta para encontrar la cuenta del cliente.</span><span class="sxs-lookup"><span data-stu-id="323e2-605">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="323e2-606">En la ficha desplegable **Detalles de plantilla de etiqueta de oleada** , seleccione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="323e2-606">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="323e2-607">A continuación, agregue una fila que tenga la siguiente configuración dentro de la pestaña **Intervalo** , en el cuadro de diálogo del editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="323e2-607">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="323e2-608">**Tabla:** *Envíos*</span><span class="sxs-lookup"><span data-stu-id="323e2-608">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="323e2-609">**Tabla derivada:** *Envíos*</span><span class="sxs-lookup"><span data-stu-id="323e2-609">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="323e2-610">**Campo:** *Número de cuenta*</span><span class="sxs-lookup"><span data-stu-id="323e2-610">**Field:** *Account number*</span></span>
    - <span data-ttu-id="323e2-611">**Criterios** introduzca el número de cuenta del cliente pertinente.</span><span class="sxs-lookup"><span data-stu-id="323e2-611">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="323e2-612">Cuando haya terminado, seleccione **Aceptar** para cerrar el cuadro de diálogo del editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="323e2-612">When you've finished, select **OK** to close the query editor dialog box.</span></span> 

1. <span data-ttu-id="323e2-613">En el panel de acciones, seleccione **Editar consulta** para abrir el cuadro de diálogo del editor de consultas para la plantilla de etiqueta completa.</span><span class="sxs-lookup"><span data-stu-id="323e2-613">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="323e2-614">En el cuadro de diálogo del editor de consultas, en la pestaña **Ordenación** , seleccione una fila que tenga la siguiente configuración.</span><span class="sxs-lookup"><span data-stu-id="323e2-614">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="323e2-615">**Tabla:** *Lineas de trabajo*</span><span class="sxs-lookup"><span data-stu-id="323e2-615">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="323e2-616">**Tabla derivada:** *Líneas de trabajo*</span><span class="sxs-lookup"><span data-stu-id="323e2-616">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="323e2-617">**Campo:** *id. de línea de carga de referencia (id. de registro)*</span><span class="sxs-lookup"><span data-stu-id="323e2-617">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="323e2-618">**Dirección de búsqueda:** *Ascendente*</span><span class="sxs-lookup"><span data-stu-id="323e2-618">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="323e2-619">Agregue una segunda columna que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="323e2-619">Add a second row that has the following settings:</span></span>

    - <span data-ttu-id="323e2-620">**Tabla:** *Lineas de trabajo*</span><span class="sxs-lookup"><span data-stu-id="323e2-620">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="323e2-621">**Tabla derivada:** *Líneas de trabajo*</span><span class="sxs-lookup"><span data-stu-id="323e2-621">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="323e2-622">**Campo:** *Identificación del envío*</span><span class="sxs-lookup"><span data-stu-id="323e2-622">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="323e2-623">**Dirección de búsqueda:** *Ascendente*</span><span class="sxs-lookup"><span data-stu-id="323e2-623">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="323e2-624">Seleccione **Aceptar** para cerrar el cuadro de diálogo del editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="323e2-624">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="323e2-625">Un cuadro de mensaje le solicitará que confirme la operación de restablecimiento de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="323e2-625">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="323e2-626">Seleccione **Sí** para continuar.</span><span class="sxs-lookup"><span data-stu-id="323e2-626">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="323e2-627">En el panel de acciones, seleccione **Grupo de plantillas de etiquetas de oleadas**.</span><span class="sxs-lookup"><span data-stu-id="323e2-627">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="323e2-628">En el cuadro de diálogo **Grupo de plantillas de etiquetas de oleadas** , en la fila donde el campo **Nombre del campo de referencia** se establece en *Id. del envío* , establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="323e2-628">In the **Wave label template group** dialog box, for the row where the **Reference field name** field is set to *Shipment ID* , set the following values:</span></span>

    - <span data-ttu-id="323e2-629">**Imprimir etiqueta de interrupción:** seleccione esta casilla.</span><span class="sxs-lookup"><span data-stu-id="323e2-629">**Print break label:** Select this check box.</span></span>
    - <span data-ttu-id="323e2-630">**ID de diseño de etiquetas:** seleccione una etiqueta de interrupción.</span><span class="sxs-lookup"><span data-stu-id="323e2-630">**Label layout ID:** Select a break label.</span></span> <span data-ttu-id="323e2-631">(Por ejemplo, seleccione el diseño de la etiqueta *Interrupción* que creó anteriormente en este escenario.)</span><span class="sxs-lookup"><span data-stu-id="323e2-631">(For example, select the *Break* label layout that you created earlier in this scenario.)</span></span>
    - <span data-ttu-id="323e2-632">**Nombre de la impresora:** seleccione la impresora para la etiqueta de interrupción.</span><span class="sxs-lookup"><span data-stu-id="323e2-632">**Printer name:** Select the printer for the break label.</span></span> <span data-ttu-id="323e2-633">(Normalmente, para dividir los rollos de etiquetas, debe seleccionar la misma impresora que está seleccionada en la ficha desplegable **Detalles de plantilla de etiqueta de oleada**.</span><span class="sxs-lookup"><span data-stu-id="323e2-633">(Typically, for the purpose of splitting label rolls, you should select the same printer that is selected on the **Wave label template details** FastTab.</span></span> <span data-ttu-id="323e2-634">Aún así, pueden darse otros escenarios).</span><span class="sxs-lookup"><span data-stu-id="323e2-634">However, other scenarios are possible.)</span></span>

1. <span data-ttu-id="323e2-635">Para la fila donde el campo **Nombre del campo de referencia** se establezca en *Identificador de la referencia de la línea de carga* , seleccione la casilla **Id. de compilación de etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="323e2-635">For the row where the **Reference field name** field is set to *Reference load line id* , select the **Label build ID** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="323e2-636">Esta configuración creará una secuencia de etiquetas ("Caja 1 de X") por línea de carga a lo largo de la oleada, con independencia de la configuración de agrupación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="323e2-636">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="323e2-637">Esta secuencia de etiquetas se puede imprimir en un diseño de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="323e2-637">This label sequence can be printed on a label layout.</span></span> <span data-ttu-id="323e2-638">Además, las etiquetas para diferentes envíos estarán separadas por la etiqueta de interrupción seleccionada.</span><span class="sxs-lookup"><span data-stu-id="323e2-638">Additionally, labels for different shipments will be separated by the selected break label.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="323e2-639">Configurar extensiones de secuencias numéricas</span><span class="sxs-lookup"><span data-stu-id="323e2-639">Configure number sequence extensions</span></span>

<span data-ttu-id="323e2-640">Las extensiones de secuencias numéricas controlan el cumplimiento GS1 de secuencias numéricas específicas.</span><span class="sxs-lookup"><span data-stu-id="323e2-640">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="323e2-641">Esta configuración es opcional para el escenario actual.</span><span class="sxs-lookup"><span data-stu-id="323e2-641">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="323e2-642">Para obtener más información e instrucciones de configuración, consulte [Configurar extensiones de secuencias numéricas](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="323e2-642">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="323e2-643">Crear un pedido de ventas y liberarlo en el almacén</span><span class="sxs-lookup"><span data-stu-id="323e2-643">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="323e2-644">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="323e2-644">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="323e2-645">Cree un pedido de ventas con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="323e2-645">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="323e2-646">**Cuenta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="323e2-646">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="323e2-647">**Almacén** : *62*</span><span class="sxs-lookup"><span data-stu-id="323e2-647">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="323e2-648">Agrega dos líneas de pedidos de ventas:</span><span class="sxs-lookup"><span data-stu-id="323e2-648">Add two sales order lines:</span></span>

    - <span data-ttu-id="323e2-649">Línea de pedido de ventas 1:</span><span class="sxs-lookup"><span data-stu-id="323e2-649">Sales order line 1:</span></span>

        - <span data-ttu-id="323e2-650">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="323e2-650">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="323e2-651">**Cantidad:** *9024*</span><span class="sxs-lookup"><span data-stu-id="323e2-651">**Quantity:** *9024*</span></span>
        - <span data-ttu-id="323e2-652">**Unidad:** *ea* (9024 ea = 376 Caja = 47 PL)</span><span class="sxs-lookup"><span data-stu-id="323e2-652">**Unit:** *ea* (9024 ea = 376 Box = 47 PL)</span></span>

    - <span data-ttu-id="323e2-653">Línea de pedido de ventas 2:</span><span class="sxs-lookup"><span data-stu-id="323e2-653">Sales order line 2:</span></span>

        - <span data-ttu-id="323e2-654">**Código de artículo:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="323e2-654">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="323e2-655">**Cantidad:** *9016*</span><span class="sxs-lookup"><span data-stu-id="323e2-655">**Quantity:** *9016*</span></span>
        - <span data-ttu-id="323e2-656">**Unidad:** *ea* (9016 ea = 322 Caja = 46 PL)</span><span class="sxs-lookup"><span data-stu-id="323e2-656">**Unit:** *ea* (9016 ea = 322 Box = 46 PL)</span></span>

    > [!NOTE]
    > <span data-ttu-id="323e2-657">Los artículos y cantidades que se proporcionan aquí son solo ejemplos.</span><span class="sxs-lookup"><span data-stu-id="323e2-657">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="323e2-658">Deben usar el grupo de secuencias de unidades que ha definido anteriormente, las conversiones de unidades adecuadas de *ea* a *Caja* a *PL* deben definirse para ellas, y deben tener existencias en el almacén *62*.</span><span class="sxs-lookup"><span data-stu-id="323e2-658">They must use the unit sequence group that you defined earlier, appropriate unit conversions from *ea* to *Box* to *PL* must be defined for them, and they must have stock in warehouse *62*.</span></span> <span data-ttu-id="323e2-659">Para más información, consulte [Directivas de unidad de medida y de existencias](unit-measure-stocking-policies.md).</span><span class="sxs-lookup"><span data-stu-id="323e2-659">For more information, see [Unit of measure and stocking policies](unit-measure-stocking-policies.md).</span></span>

1. <span data-ttu-id="323e2-660">Seleccione la línea de pedido de ventas 1.</span><span class="sxs-lookup"><span data-stu-id="323e2-660">Select sales order line 1.</span></span> <span data-ttu-id="323e2-661">A continuación, en la sección **Línea de pedido de ventas** , en el menú **Inventario** , seleccione **Reservas**.</span><span class="sxs-lookup"><span data-stu-id="323e2-661">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="323e2-662">En la página **Reserva** , en el panel de acciones, seleccione **Reservar lote** y después cierre la página.</span><span class="sxs-lookup"><span data-stu-id="323e2-662">On the **Reservation** page, on the Action Pane, select **Reserve lot** , and then close the page.</span></span>
1. <span data-ttu-id="323e2-663">Repita los pasos 4 y 5 para la línea de pedido de ventas 2.</span><span class="sxs-lookup"><span data-stu-id="323e2-663">Repeat steps 4 and 5 for sales order line 2.</span></span>
1. <span data-ttu-id="323e2-664">En el panel de acciones, en la pestaña **Almacén** , seleccione **Liberar al almacén**.</span><span class="sxs-lookup"><span data-stu-id="323e2-664">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="323e2-665">Se producen los eventos siguientes:</span><span class="sxs-lookup"><span data-stu-id="323e2-665">The following events occur:</span></span> 

    - <span data-ttu-id="323e2-666">El sistema procesa el envío creado utilizando la plantilla que incluye el paso de impresión de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="323e2-666">The system processes the created shipment by using the template that includes the label printing step.</span></span> <span data-ttu-id="323e2-667">El diseño de la etiqueta se usará para definir el formato de la etiqueta y el resultado será una etiqueta impresa en la impresora que está seleccionada en la plantilla de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="323e2-667">The label layout will be used to define the format of the label, and the result will be a label that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="323e2-668">Las etiquetas de oleadas se generan y se imprimen.</span><span class="sxs-lookup"><span data-stu-id="323e2-668">Wave labels are generated and printed.</span></span> <span data-ttu-id="323e2-669">El número de etiquetas será igual al número de cajas (en este ejemplo, 376 etiquetas de caja para la línea 1, 322 etiquetas de caja para la línea 2, 47 etiquetas de PL para la línea 1, 47 etiquetas de PL para la línea 2 y dos etiquetas de interrupción que tienen el Id. del envío).</span><span class="sxs-lookup"><span data-stu-id="323e2-669">The number of labels will equal the number of cartons (in this example, 376 Box labels for line 1, 322 Box labels for line 2, 47 PL labels for line 1, 47 PL labels for line 2, and two break labels that have the shipment ID).</span></span>
    - <span data-ttu-id="323e2-670">Se genera un nuevo id. de conocimiento de embarque para los envíos.</span><span class="sxs-lookup"><span data-stu-id="323e2-670">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="323e2-671">Si ha configurado las extensiones de secuencias numéricas, los id. de etiquetas de oleadas seguirán el formato numérico **SSCC-18**.</span><span class="sxs-lookup"><span data-stu-id="323e2-671">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="323e2-672">Puede ver y volver a imprimir etiquetas de oleadas desde las siguientes páginas:</span><span class="sxs-lookup"><span data-stu-id="323e2-672">You can view and reprint wave labels from the following pages:</span></span>

- <span data-ttu-id="323e2-673">Todos los envíos \> Detalles del envío</span><span class="sxs-lookup"><span data-stu-id="323e2-673">All shipments \> Shipment details</span></span>
- <span data-ttu-id="323e2-674">Todas las cargas \> Detalles de la carga</span><span class="sxs-lookup"><span data-stu-id="323e2-674">All loads \> Load details</span></span>
- <span data-ttu-id="323e2-675">Todas las oleadas</span><span class="sxs-lookup"><span data-stu-id="323e2-675">All waves</span></span>
- <span data-ttu-id="323e2-676">Etiquetas de oleadas</span><span class="sxs-lookup"><span data-stu-id="323e2-676">Wave labels</span></span>
- <span data-ttu-id="323e2-677">Historial de etiquetas de oleada</span><span class="sxs-lookup"><span data-stu-id="323e2-677">Wave label history</span></span>

<span data-ttu-id="323e2-678">Para la mayoría de estas páginas, puede encontrar la función relevante seleccionando **Etiquetas de oleadas** en el grupo **Información relacionada** de la pestaña del panel de acciones **Envíos**.</span><span class="sxs-lookup"><span data-stu-id="323e2-678">For most of these pages, you can find the relevant function by selecting **Wave labels** in the **Related information** group on the **Shipments** tab of the Action Pane.</span></span>
