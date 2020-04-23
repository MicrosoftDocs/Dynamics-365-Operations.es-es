---
title: Habilitar la impresión de la etiqueta de matrícula
description: En este tema se muestra cómo habilitar la impresión automática de una etiqueta de código de contenedor de envío en serie (SSCC) después de que el último artículo se selecciona del inventario en un proceso de trabajo de selección de ventas.
author: perlynne
manager: tfehr
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysCorpNetPrinterList, WHSParameters, NumberSequenceTableListPage, NumberSequenceDetails, WHSDocumentRoutingLayout, WHSDocumentRouting, WHSRFMenuItem, WHSRFMenu, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 484a1465dd41429fe201de18aac55f118a483cab
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3217020"
---
# <a name="enable-license-plate-label-printing"></a><span data-ttu-id="97fc7-103">Habilitar la impresión de la etiqueta de matrícula</span><span class="sxs-lookup"><span data-stu-id="97fc7-103">Enable license plate label printing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="97fc7-104">En este tema se muestra cómo habilitar la impresión automática de una etiqueta de código de contenedor de envío en serie (SSCC) después de que el último artículo se selecciona del inventario en un proceso de trabajo de selección de ventas.</span><span class="sxs-lookup"><span data-stu-id="97fc7-104">This topic shows how to enable the automatic printing of a Serial shipping container code (SSCC) label after the last item is picked from inventory in a sales picking work process.</span></span> <span data-ttu-id="97fc7-105">Puede ejecutar este procedimiento en la empresa USMF de los datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="97fc7-105">You can run this procedure in demo data company USMF.</span></span> <span data-ttu-id="97fc7-106">Si lo ejecuta mediante sus propios datos, debe tener una secuencia numérica configurada para las matrículas de entidad de almacén.</span><span class="sxs-lookup"><span data-stu-id="97fc7-106">If you're run it using your own data, you need to have a number sequence set up for license plates.</span></span> <span data-ttu-id="97fc7-107">Es necesario configurar una impresora de etiquetas para poder comenzar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="97fc7-107">You need to set up a label printer before you begin this task.</span></span> <span data-ttu-id="97fc7-108">Vaya a Administración de la organización > Configurar > Impresoras de red.</span><span class="sxs-lookup"><span data-stu-id="97fc7-108">Go to Organization administration > Setup > Network printers.</span></span> <span data-ttu-id="97fc7-109">En el panel de acciones, haga clic en Opciones y, a continuación, haga clic en el botón Descargar instalador del agente de ruta de documentos.</span><span class="sxs-lookup"><span data-stu-id="97fc7-109">On the Action pane, click Options, and then click the Download document routing agent installer button.</span></span> <span data-ttu-id="97fc7-110">Ejecute el instalador y asegúrese de que tiene una impresora de red de trabajo establecida en Activa para poder continuar con el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="97fc7-110">Run the installer and make sure that you have a working network printer set to Active before you continue with the procedure.</span></span>


## <a name="set-up-the-gs1-company-prefix"></a><span data-ttu-id="97fc7-111">Configurar el prefijo GS1 de la empresa</span><span class="sxs-lookup"><span data-stu-id="97fc7-111">Set up the GS1 company prefix</span></span>
1. <span data-ttu-id="97fc7-112">Vaya al **Panel de exploración > Módulos > Gestión de almacenes > Configuración > Almacén >Parámetros de gestión de almacenes**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-112">Go to **Navigation pane > Modules > Warehouse management > Setup > Warehouse management parameters**.</span></span>
2. <span data-ttu-id="97fc7-113">En el campo **Prefijo GS1 de la empresa**, escriba las 7 cifras del número GS1 de la empresa.</span><span class="sxs-lookup"><span data-stu-id="97fc7-113">In the **GS1 company prefix** field, enter the 7 numbers for your GS1 company number.</span></span>
3. <span data-ttu-id="97fc7-114">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-114">Select **Save**.</span></span>
4. <span data-ttu-id="97fc7-115">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="97fc7-115">Close the page.</span></span>

## <a name="setup-the-sscc-license-plate-number-sequence"></a><span data-ttu-id="97fc7-116">Configurar la secuencia de la matrícula de entidad de almacén de SSCC</span><span class="sxs-lookup"><span data-stu-id="97fc7-116">Setup the SSCC license plate number sequence</span></span>
1. <span data-ttu-id="97fc7-117">Vaya al **panel de navegación > Módulos > Administración de la organización > Secuencias numéricas > Secuencias numéricas**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-117">Go to **Navigation pane > Modules > Organization administration > Number sequences > Number sequences**.</span></span>
2. <span data-ttu-id="97fc7-118">En el campo **Área**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="97fc7-118">In the **Area** field, select an option.</span></span>
3. <span data-ttu-id="97fc7-119">En el campo **Referencia**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="97fc7-119">In the **Reference** field, select an option.</span></span>
4. <span data-ttu-id="97fc7-120">En el campo **Empresa**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="97fc7-120">In the **Company** field, type a value.</span></span>
5. <span data-ttu-id="97fc7-121">Expanda la sección **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-121">Expand the **Segments** section.</span></span>
6. <span data-ttu-id="97fc7-122">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-122">Select **Edit**.</span></span>
7. <span data-ttu-id="97fc7-123">En la tabla de **Segmentos**, seleccione la primera fila</span><span class="sxs-lookup"><span data-stu-id="97fc7-123">In the **Segments** table, select the first row</span></span>
8. <span data-ttu-id="97fc7-124">Seleccione **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-124">Select **Remove**.</span></span>
9. <span data-ttu-id="97fc7-125">Seleccione **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-125">Select **Remove**.</span></span>
10. <span data-ttu-id="97fc7-126">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-126">Select **Save**.</span></span>
11. <span data-ttu-id="97fc7-127">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="97fc7-127">Close the page.</span></span>

## <a name="create-the-document-route-layout"></a><span data-ttu-id="97fc7-128">Crear el diseño de la ruta de documentos</span><span class="sxs-lookup"><span data-stu-id="97fc7-128">Create the document route layout</span></span>
1. <span data-ttu-id="97fc7-129">Vaya a **Panel de exploración > Módulos > Gestión de almacenes > Configurar > Ruta de documentos > Diseños de ruta de documentos**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-129">Go to **Navigation pane > Modules > Warehouse management > Setup > Document routing > Document routing layouts**.</span></span> <span data-ttu-id="97fc7-130">Habilite la configuración de SSCC.</span><span class="sxs-lookup"><span data-stu-id="97fc7-130">Enable the SSCC layout.</span></span>  
2. <span data-ttu-id="97fc7-131">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-131">Select **New**.</span></span>
3. <span data-ttu-id="97fc7-132">En el campo **Id. de diseño**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="97fc7-132">In the **Layout ID** field, type a value.</span></span>
4. <span data-ttu-id="97fc7-133">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="97fc7-133">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="97fc7-134">Seleccione **Insertar al final del texto**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-134">Select **Insert at end of text**.</span></span>
6. <span data-ttu-id="97fc7-135">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-135">Select **Save**.</span></span>
7. <span data-ttu-id="97fc7-136">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="97fc7-136">Close the page.</span></span>

## <a name="set-up-the-document-routing"></a><span data-ttu-id="97fc7-137">Configurar la ruta de documentos</span><span class="sxs-lookup"><span data-stu-id="97fc7-137">Set up the document routing</span></span>
1. <span data-ttu-id="97fc7-138">Vaya a **Panel de exploración > Módulos > Gestión de almacenes > Configurar > Ruta de documentos > Ruta de documentos**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-138">Go to **Navigation pane > Modules > Warehouse management > Setup > Document routing > Document routing**.</span></span>
2. <span data-ttu-id="97fc7-139">En el campo **Tipo de pedido de trabajo**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="97fc7-139">In the **Work order type** field, select an option.</span></span>
3. <span data-ttu-id="97fc7-140">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-140">Select **New**.</span></span>
4. <span data-ttu-id="97fc7-141">En el campo **Almacén**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="97fc7-141">In the **Warehouse** field, type a value.</span></span>
5. <span data-ttu-id="97fc7-142">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="97fc7-142">In the **Name** field, type a value.</span></span>
6. <span data-ttu-id="97fc7-143">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-143">Select **New**.</span></span>
7. <span data-ttu-id="97fc7-144">En el campo **Id. de diseño**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="97fc7-144">In the **Layout ID** field, enter or select a value.</span></span>
8. <span data-ttu-id="97fc7-145">En el campo **Nombre**, especifique el nombre de la impresora que desee utilizar.</span><span class="sxs-lookup"><span data-stu-id="97fc7-145">In the **Name** field, enter the printer name that you want to use.</span></span>
9. <span data-ttu-id="97fc7-146">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-146">Select **Save**.</span></span>
10. <span data-ttu-id="97fc7-147">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="97fc7-147">Close the page.</span></span>

## <a name="create-mobile-device-menu"></a><span data-ttu-id="97fc7-148">Crear el menú del dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="97fc7-148">Create mobile device menu</span></span>
1. <span data-ttu-id="97fc7-149">Vaya al **Panel de exploración >Módulos > Administración de módulos > Configuración > Dispositivo móvil > Elementos de menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-149">Go to **Navigation pane > Modules > Warehouse management > Setup > Mobile device > Mobile device menu items**.</span></span>
2. <span data-ttu-id="97fc7-150">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-150">Select **New**.</span></span>
3. <span data-ttu-id="97fc7-151">En el campo **Nombre del elemento de menú**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="97fc7-151">In the **Menu item name** field, type a value.</span></span>
4. <span data-ttu-id="97fc7-152">En el campo **Título**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="97fc7-152">In the **Title** field, type a value.</span></span>
5. <span data-ttu-id="97fc7-153">En el campo **Modo**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="97fc7-153">In the **Mode** field, select an option.</span></span>
6. <span data-ttu-id="97fc7-154">Seleccione **Sí** en el campo **Usar trabajo existente**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-154">Select **Yes** in the **Use existing work** field.</span></span>
7. <span data-ttu-id="97fc7-155">Seleccione **Sí** en el campo **Generar matrícula de entidad de almacén**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-155">Select **Yes** in the **Generate license plate** field.</span></span>
8. <span data-ttu-id="97fc7-156">Expanda la sección **Clases de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-156">Expand the **Work classes** section.</span></span>
9. <span data-ttu-id="97fc7-157">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-157">Select **New**.</span></span>
10. <span data-ttu-id="97fc7-158">En el campo **Identificador de la clase de trabajo**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="97fc7-158">In the **Work class ID** field, type a value.</span></span>
11. <span data-ttu-id="97fc7-159">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-159">Select **Save**.</span></span>
12. <span data-ttu-id="97fc7-160">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="97fc7-160">Close the page.</span></span>
13. <span data-ttu-id="97fc7-161">Vaya al **Panel de exploración >Módulos > Administración de módulos > Configuración > Dispositivo móvil > Menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-161">Go to **navigation pane > Modules > Warehouse management > Setup > Mobile device > Mobile device menu**.</span></span>
14. <span data-ttu-id="97fc7-162">En el árbol, seleccione el elemento de menú que ha creado antes.</span><span class="sxs-lookup"><span data-stu-id="97fc7-162">In the tree, select the menu item that you created before.</span></span>
15. <span data-ttu-id="97fc7-163">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-163">Select **Edit**.</span></span>
16. <span data-ttu-id="97fc7-164">Seleccione la flecha para agregar el elemento de menú al menú.</span><span class="sxs-lookup"><span data-stu-id="97fc7-164">Select the arrow to add the menu item to the menu.</span></span>
17. <span data-ttu-id="97fc7-165">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-165">Select **Save**.</span></span>
18. <span data-ttu-id="97fc7-166">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="97fc7-166">Close the page.</span></span>

## <a name="update-a-work-template"></a><span data-ttu-id="97fc7-167">Actualizar una plantilla de trabajo</span><span class="sxs-lookup"><span data-stu-id="97fc7-167">Update a work template</span></span>
1. <span data-ttu-id="97fc7-168">Vaya al **Panel de exploración > Módulos > Gestión de almacenes > Configuración > Trabajo > Plantillas de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-168">Go to **Navigation pane > Modules > Warehouse management > Setup > Work > Work templates**.</span></span>
2. <span data-ttu-id="97fc7-169">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-169">Select **Edit**.</span></span>
3. <span data-ttu-id="97fc7-170">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-170">Select **New**.</span></span>
4. <span data-ttu-id="97fc7-171">En el campo **Tipo de trabajo**, seleccione **Imprimir**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-171">In the **Work type** field, select **Print**.</span></span>
5. <span data-ttu-id="97fc7-172">En el campo **Identificador de la clase de trabajo**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="97fc7-172">In the **Work class ID** field, enter or select a value.</span></span>
6. <span data-ttu-id="97fc7-173">Seleccione **Subir**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-173">Select **Move up**.</span></span>
7. <span data-ttu-id="97fc7-174">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="97fc7-174">Select **Save**.</span></span>
8. <span data-ttu-id="97fc7-175">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="97fc7-175">Close the page.</span></span>

